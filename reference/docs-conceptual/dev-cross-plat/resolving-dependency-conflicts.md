---
title: Auflösen von Abhängigkeitskonflikten bei der Modulassembly in PowerShell
description: Wenn Sie ein binäres PowerShell-Modul in C# schreiben, ist es normal, zur Bereitstellung von Funktionalität Abhängigkeiten von anderen Paketen oder Bibliotheken zu nutzen.
ms.date: 06/25/2020
ms.custom: rjmholt
ms.openlocfilehash: 93bb39bdd440c7f97c27aa81e68f68331569b69e
ms.sourcegitcommit: 2fc6ee49a70bda4c59135136bd5cc7782836a124
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94810401"
---
# <a name="resolving-powershell-module-assembly-dependency-conflicts"></a><span data-ttu-id="ea89e-103">Lösen von Abhängigkeitskonflikten bei der Modulassembly in PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea89e-103">Resolving PowerShell module assembly dependency conflicts</span></span>

<span data-ttu-id="ea89e-104">Wenn Sie ein binäres PowerShell-Modul in C# schreiben, ist es normal, zur Bereitstellung von Funktionalität Abhängigkeiten von anderen Paketen oder Bibliotheken zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-104">When writing a binary PowerShell module in C#, it's natural to take dependencies on other packages or libraries to provide functionality.</span></span> <span data-ttu-id="ea89e-105">Die Nutzung von Abhängigkeiten von anderen Bibliotheken ist für die Wiederverwendung von Code wünschenswert.</span><span class="sxs-lookup"><span data-stu-id="ea89e-105">Taking dependencies on other libraries is desirable for code reuse.</span></span> <span data-ttu-id="ea89e-106">PowerShell lädt Assemblys immer in denselben Kontext.</span><span class="sxs-lookup"><span data-stu-id="ea89e-106">PowerShell always loads assemblies into the same context.</span></span> <span data-ttu-id="ea89e-107">Dies stellt Probleme dar, wenn die Abhängigkeiten eines Moduls mit bereits geladenen DLLs in Konflikt stehen und die Verwendung von zwei anderweitig nicht zusammengehörigen Modulen in derselben PowerShell-Sitzung verhindern.</span><span class="sxs-lookup"><span data-stu-id="ea89e-107">This presents issues when a module's dependencies conflict with already-loaded DLLs and may prevent using two otherwise unrelated modules in the same PowerShell session.</span></span>

<span data-ttu-id="ea89e-108">Wenn dieses Problem auftritt, wird eine Fehlermeldung wie diese angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ea89e-108">If you've had this problem, you've seen an error message like this:</span></span>

![Fehlermeldung zu Konflikt beim Laden von Assemblys](./media/resolving-dependency-conflicts/moduleconflict.png)

<span data-ttu-id="ea89e-110">In diesem Artikel werden einige Möglichkeiten erläutert, wie Abhängigkeitskonflikte in PowerShell auftreten und Probleme durch Abhängigkeitskonflikte behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="ea89e-110">This article looks at some of the ways dependency conflicts occur in PowerShell and ways to mitigate dependency conflict issues.</span></span> <span data-ttu-id="ea89e-111">Auch wenn Sie kein Modulentwickler sind, finden Sie hier einige Tipps, die Ihnen bei Abhängigkeitskonflikten in von Ihnen verwendeten Modulen helfen können.</span><span class="sxs-lookup"><span data-stu-id="ea89e-111">Even if you're not a module author, there are some tricks in here that might help you with dependency conflicts occurring in modules that you use.</span></span>

## <a name="why-do-dependency-conflicts-occur"></a><span data-ttu-id="ea89e-112">Warum treten Abhängigkeitskonflikte auf?</span><span class="sxs-lookup"><span data-stu-id="ea89e-112">Why do dependency conflicts occur?</span></span>

<span data-ttu-id="ea89e-113">In .NET treten Abhängigkeitskonflikte auf, wenn zwei Versionen der gleichen Assembly in denselben _Assemblyladekontext_ geladen werden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-113">In .NET, dependency conflicts occur when two versions of the same assembly are loaded into the same _Assembly Load Context_.</span></span> <span data-ttu-id="ea89e-114">Dieser Begriff bedeutet auf verschiedenen .NET-Plattformen jeweils etwas anderes, worauf [später](#powershell-and-net) eingegangen wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-114">This term means slightly different things on different .NET platforms, which is covered [later](#powershell-and-net).</span></span> <span data-ttu-id="ea89e-115">Dieser Konflikt ist ein verbreitetes Problem, das in jeder Software auftritt, in der Abhängigkeiten mit Versionsangabe zum Einsatz kommen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-115">This conflict is a common problem that occurs in any software where versioned dependencies are used.</span></span> <span data-ttu-id="ea89e-116">Da es keine einfachen Lösungen gibt und viele Frameworks zur Auflösung von Abhängigkeiten versuchen, das Problem auf unterschiedliche Weise zu lösen, wird diese Situation oft als „Abhängigkeitshölle“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ea89e-116">Because there are no simple solutions, and because many dependency-resolution frameworks try to solve the problem in different ways, this situation is often called "dependency hell".</span></span>

<span data-ttu-id="ea89e-117">Zu den Konfliktproblemen kommt die Tatsache hinzu, dass ein Projekt fast nie absichtlich oder direkt von zwei Versionen derselben Abhängigkeit abhängt.</span><span class="sxs-lookup"><span data-stu-id="ea89e-117">Conflict issues are compounded by the fact that a project almost never deliberately or directly depends on two versions of the same dependency.</span></span> <span data-ttu-id="ea89e-118">Stattdessen hat das Projekt zwei oder mehr Abhängigkeiten, die jeweils eine andere Version derselben Abhängigkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="ea89e-118">Instead, the project has two or more dependencies that each require a different version of the same dependency.</span></span>

<span data-ttu-id="ea89e-119">Angenommen, Ihre .NET-Anwendung `DuckBuilder` weist zwei Abhängigkeiten auf, um Teile ihrer Funktionalität zu erfüllen, und sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ea89e-119">For example, say your .NET application, `DuckBuilder`, brings in two dependencies, to perform parts of its functionality and looks like this:</span></span>

![Zwei Abhängigkeiten von DuckBuilder beruhen auf verschiedenen Versionen von Newtonsoft.Json](./media/resolving-dependency-conflicts/dep-conflict.jpg)

<span data-ttu-id="ea89e-121">Da sowohl `Contoso.ZipTools` als auch `Fabrikam.FileHelpers` von verschiedenen Versionen von `Newtonsoft.Json` abhängen, kann es je nachdem, wie die einzelnen Abhängigkeiten geladen werden, zu einem Abhängigkeitskonflikt kommen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-121">Because `Contoso.ZipTools` and `Fabrikam.FileHelpers` both depend on different versions of `Newtonsoft.Json`, there may be a dependency conflict depending on how each dependency is loaded.</span></span>

### <a name="conflicting-with-powershells-dependencies"></a><span data-ttu-id="ea89e-122">Konflikt mit PowerShell-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="ea89e-122">Conflicting with PowerShell's dependencies</span></span>

<span data-ttu-id="ea89e-123">In PowerShell wird das Problem des Abhängigkeitskonflikts noch verstärkt, da PowerShell-Module und die Abhängigkeiten von PowerShell selbst in denselben gemeinsamen Kontext geladen werden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-123">In PowerShell, the dependency conflict issue is magnified because PowerShell modules and PowerShell's own dependencies are loaded into the same shared context.</span></span> <span data-ttu-id="ea89e-124">Das bedeutet, dass die PowerShell-Engine und alle geladenen PowerShell-Module keine in Konflikt stehenden Abhängigkeiten aufweisen dürfen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-124">This means the PowerShell engine and all loaded PowerShell modules must not have conflicting dependencies.</span></span> <span data-ttu-id="ea89e-125">Ein klassisches Beispiel hierfür ist `Newtonsoft.Json`:</span><span class="sxs-lookup"><span data-stu-id="ea89e-125">A classic example of this is `Newtonsoft.Json`:</span></span>

![Das Modul FictionalTools hängt von einer neueren Version von Newtonsoft.Json als PowerShell ab.](./media/resolving-dependency-conflicts/engine-conflict.jpg)

<span data-ttu-id="ea89e-127">Bei diesem Beispiel hängt das Modul `FictionalTools` von der `Newtonsoft.Json`-Version `12.0.3` ab, die eine neuere Version von `Newtonsoft.Json` als `11.0.2` ist, die in der Beispiel-PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ea89e-127">In this example, the module `FictionalTools` depends on `Newtonsoft.Json` version `12.0.3`, which is a newer version of `Newtonsoft.Json` than `11.0.2` that ships in the example PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="ea89e-128">Dies ist ein Beispiel, und PowerShell 7 wird zurzeit mit `Newtonsoft.Json 12.0.3` zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="ea89e-128">This is an example and PowerShell 7 currently ships with `Newtonsoft.Json 12.0.3`.</span></span>

<span data-ttu-id="ea89e-129">Da das Modul von einer neueren Version der Assembly abhängt, akzeptiert es nicht die bereits von PowerShell geladene Version.</span><span class="sxs-lookup"><span data-stu-id="ea89e-129">Because the module depends on a newer version of the assembly, it won't accept the version that PowerShell already has loaded.</span></span> <span data-ttu-id="ea89e-130">Da PowerShell jedoch schon eine Version der Assembly geladen hat, kann das Modul seine eigene Version nicht über den herkömmlichen Lademechanismus laden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-130">But because PowerShell has already loaded a version of the assembly, the module can't load its own version using the conventional load mechanism.</span></span>

### <a name="conflicting-with-another-modules-dependencies"></a><span data-ttu-id="ea89e-131">Konflikt mit den Abhängigkeiten eines anderen Moduls</span><span class="sxs-lookup"><span data-stu-id="ea89e-131">Conflicting with another module's dependencies</span></span>

<span data-ttu-id="ea89e-132">Ein weiteres verbreitetes Szenario in PowerShell ist, dass ein Modul geladen wird, das von einer Version einer Assembly abhängt, und dann später ein weiteres Modul geladen wird, das von einer anderen Version dieser Assembly abhängt.</span><span class="sxs-lookup"><span data-stu-id="ea89e-132">Another common scenario in PowerShell is that a module is loaded that depends on one version of an assembly, and then another module is loaded later that depends on a different version of that assembly.</span></span>

<span data-ttu-id="ea89e-133">Das sieht dann oft wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ea89e-133">This often looks like the following:</span></span>

![Zwei PowerShell-Module erfordern unterschiedliche Versionen der Abhängigkeit Microsoft.Extensions.Logging](./media/resolving-dependency-conflicts/mod-conflict.jpg)

<span data-ttu-id="ea89e-135">In diesem Fall erfordert das Modul `FictionalTools` eine neuere Version von `Microsoft.Extensions.Logging` als das Modul `FilesystemManager`.</span><span class="sxs-lookup"><span data-stu-id="ea89e-135">In this case, the `FictionalTools` module requires a newer version of `Microsoft.Extensions.Logging` than the `FilesystemManager` module.</span></span>

<span data-ttu-id="ea89e-136">Stellen Sie sich vor, dass diese Module ihre Abhängigkeiten laden, indem Sie die abhängigen Assemblys im gleichen Verzeichnis wie die Stammmodulassembly platzieren.</span><span class="sxs-lookup"><span data-stu-id="ea89e-136">Imagine these modules load their dependencies by placing the dependency assemblies in the same directory as the root module assembly.</span></span> <span data-ttu-id="ea89e-137">Dies ermöglicht .NET, sie implizit anhand ihres Namens zu laden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-137">This allows .NET to implicitly load them by name.</span></span> <span data-ttu-id="ea89e-138">Wenn wir PowerShell 7 (auf .NET Core 3.1) ausführen, können wir `FictionalTools` ohne Probleme laden und ausführen und dann `FilesystemManager` laden und ausführen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-138">If we're running PowerShell 7 (on top of .NET Core 3.1), we can load and run `FictionalTools`, then load and run `FilesystemManager` without issue.</span></span> <span data-ttu-id="ea89e-139">Wenn wir jedoch in einer neuen Sitzung `FilesystemManager` laden und ausführen und dann `FictionalTools` laden, erhalten wir eine `FileLoadException` für den Befehl `FictionalTools`, weil er eine neuere Version von `Microsoft.Extensions.Logging` erfordert als die geladene.</span><span class="sxs-lookup"><span data-stu-id="ea89e-139">However, in a new session, if we load and run `FilesystemManager`, then load `FictionalTools`, we get a `FileLoadException` from the `FictionalTools` command because it requires a newer version of `Microsoft.Extensions.Logging` than the one loaded.</span></span>
<span data-ttu-id="ea89e-140">`FictionalTools` kann die benötigte Version nicht laden, weil bereits eine Assembly mit dem gleichen Namen geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="ea89e-140">`FictionalTools` can't load the version needed because an assembly of the same name has already been loaded.</span></span>

## <a name="powershell-and-net"></a><span data-ttu-id="ea89e-141">PowerShell und .NET</span><span class="sxs-lookup"><span data-stu-id="ea89e-141">PowerShell and .NET</span></span>

<span data-ttu-id="ea89e-142">PowerShell wird auf der .NET-Plattform ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ea89e-142">PowerShell runs on the .NET platform.</span></span> <span data-ttu-id="ea89e-143">.NET ist letztendlich für das Auflösen und Laden von Abhängigkeiten von Assemblys verantwortlich. Daher müssen wir verstehen, wie .NET hier vorgeht, um Abhängigkeitskonflikte zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-143">NET is ultimately responsible for resolving and loading assembly dependencies, so we must understand how .NET operates here to understand dependency conflicts.</span></span>

<span data-ttu-id="ea89e-144">Wir müssen uns auch der Tatsache stellen, dass verschiedene Versionen von PowerShell in verschiedenen .NET-Implementierungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-144">We must also confront the fact that different versions of PowerShell run on different .NET implementations.</span></span> <span data-ttu-id="ea89e-145">Im Allgemeinen wird PowerShell bis Version 5.1 in .NET Framework ausgeführt, während PowerShell ab Version 6 in .NET Core ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-145">In general, PowerShell 5.1 and below run on .NET Framework, while PowerShell 6 and above run on .NET Core.</span></span> <span data-ttu-id="ea89e-146">Diese beiden Implementierungen von .NET laden und behandeln Assemblys anders.</span><span class="sxs-lookup"><span data-stu-id="ea89e-146">These two implementations of .NET load and handle assemblies differently.</span></span>
<span data-ttu-id="ea89e-147">Das bedeutet, dass die Lösung von Abhängigkeitskonflikten je nach zugrunde liegender .NET-Plattform variieren kann.</span><span class="sxs-lookup"><span data-stu-id="ea89e-147">This means that resolving dependency conflicts can vary depending on the underlying .NET platform.</span></span>

### <a name="assembly-load-contexts"></a><span data-ttu-id="ea89e-148">Assemblyladekontexte</span><span class="sxs-lookup"><span data-stu-id="ea89e-148">Assembly Load Contexts</span></span>

<span data-ttu-id="ea89e-149">In .NET ist ein _Assemblyladekontext_ (Assembly Load Context, ALC) ein Laufzeitnamespace, in den Assemblys geladen werden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-149">In .NET, an _Assembly Load Context_ (ALC) that is a runtime namespace into which assemblies are loaded.</span></span> <span data-ttu-id="ea89e-150">Die Assemblynamen müssen eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="ea89e-150">The assemblies' names must be unique.</span></span> <span data-ttu-id="ea89e-151">Dieses Konzept ermöglicht in jedem ALC das eindeutige Auflösen von Assemblys anhand des Namens.</span><span class="sxs-lookup"><span data-stu-id="ea89e-151">This concept allows assemblies to be uniquely resolved by name in each ALC.</span></span>

### <a name="assembly-reference-loading-in-net"></a><span data-ttu-id="ea89e-152">Laden von Assemblyverweisen in .NET</span><span class="sxs-lookup"><span data-stu-id="ea89e-152">Assembly reference loading in .NET</span></span>

<span data-ttu-id="ea89e-153">Die Semantik des Ladens von Assemblys hängt sowohl von der .NET-Implementierung (.NET Core gegenüber .NET Framework) als auch von der .NET-API ab, die zum Laden einer bestimmten Assembly verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-153">The semantics of assembly loading depend on both the .NET implementation (.NET Core vs .NET Framework) and the .NET API used to load a particular assembly.</span></span> <span data-ttu-id="ea89e-154">Anstatt hier ins Detail zu gehen, gibt es Links im Abschnitt [Weitere nützliche Informationen](#further-reading), die sehr detailliert darauf eingehen, wie das Laden von .NET Assemblys in den einzelnen .NET-Implementierungen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ea89e-154">Rather than go into detail here, there are links in the [Further reading](#further-reading) section that go into great detail on how .NET assembly loading works in each .NET implementation.</span></span>

<span data-ttu-id="ea89e-155">In diesem Artikel werden die folgenden Mechanismen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="ea89e-155">In this article we'll refer to the following mechanisms:</span></span>

- <span data-ttu-id="ea89e-156">Implizites Laden von Assemblys (tatsächlich `Assembly.Load(AssemblyName)`), wenn .NET implizit versucht, eine Assembly anhand des Namens über einen statischen Assemblyverweis in .NET-Code zu laden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-156">Implicit assembly loading (effectively `Assembly.Load(AssemblyName)`), when .NET implicitly tries to load an assembly by name from a static assembly reference in .NET code.</span></span>
- <span data-ttu-id="ea89e-157">`Assembly.LoadFrom()`, eine Plug-In-orientierte Lade-API, die Handler zur Auflösung von Abhängigkeiten der geladenen DLL hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="ea89e-157">`Assembly.LoadFrom()`, a plugin-oriented loading API that adds handlers to resolve dependencies of the loaded DLL.</span></span> <span data-ttu-id="ea89e-158">Diese Methode kann Abhängigkeiten ggf. nicht wie gewünscht auflösen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-158">This method may not resolve dependencies the way we want.</span></span>
- <span data-ttu-id="ea89e-159">`Assembly.LoadFile()`, eine einfache Lade-API, die nur die angeforderte Assembly laden soll und keinerlei Abhängigkeiten behandelt.</span><span class="sxs-lookup"><span data-stu-id="ea89e-159">`Assembly.LoadFile()`, a basic loading API intended to load only the assembly asked for and does not handle any dependencies.</span></span>

### <a name="differences-in-net-framework-vs-net-core"></a><span data-ttu-id="ea89e-160">Unterschiede in .NET Framework gegenüber .NET Core</span><span class="sxs-lookup"><span data-stu-id="ea89e-160">Differences in .NET Framework vs .NET Core</span></span>

<span data-ttu-id="ea89e-161">Die Funktionsweise dieser APIs hat sich zwischen .NET Core und .NET Framework geringfügig geändert, weshalb es sich lohnt, sich die aufgeführten [Links](#further-reading) anzusehen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-161">The way these APIs work has changed in subtle ways between .NET Core and .NET Framework, so it's worth reading through the included [links](#further-reading).</span></span> <span data-ttu-id="ea89e-162">Vor allem haben sich die Assemblyladekontexte und andere Mechanismen zur Auflösung von Assemblys zwischen .NET Framework und .NET Core geändert.</span><span class="sxs-lookup"><span data-stu-id="ea89e-162">Importantly, Assembly Load Contexts and other assembly resolution mechanisms have changed between .NET Framework and .NET Core.</span></span>

<span data-ttu-id="ea89e-163">.NET Framework bietet insbesondere die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="ea89e-163">In particular, .NET Framework has the following features:</span></span>

- <span data-ttu-id="ea89e-164">Den globalen Assemblycache für die computerweite Assemblyauflösung</span><span class="sxs-lookup"><span data-stu-id="ea89e-164">The Global Assembly Cache, for machine-wide assembly resolution</span></span>
- <span data-ttu-id="ea89e-165">Anwendungsdomänen, die wie prozessinterne Sandboxes zur Isolierung von Assemblys funktionieren, aber auch eine Serialisierungsebene aufweisen, die es zu beachten gilt</span><span class="sxs-lookup"><span data-stu-id="ea89e-165">Application Domains, which work like in-process sandboxes for assembly isolation, but also present a serialization layer to contend with</span></span>
- <span data-ttu-id="ea89e-166">Ein eingeschränktes Modell für Assemblyladekontexte, das [hier](/dotnet/framework/deployment/best-practices-for-assembly-loading) eingehend erläutert wird und einen festen Satz von Assemblyladekontexten mit jeweils eigenem Verhalten aufweist:</span><span class="sxs-lookup"><span data-stu-id="ea89e-166">A limited assembly load context model, explained in depth [here](/dotnet/framework/deployment/best-practices-for-assembly-loading), that has a fixed set of assembly load contexts, each with their own behavior:</span></span>
  - <span data-ttu-id="ea89e-167">Der Standardladekontext, in den Assemblys standardmäßig geladen werden</span><span class="sxs-lookup"><span data-stu-id="ea89e-167">The default load context, where assemblies are loaded by default</span></span>
  - <span data-ttu-id="ea89e-168">Der Kontext „Laden aus“ zum manuellen Laden von Assemblys zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ea89e-168">The load-from context, for loading assemblies manually at runtime</span></span>
  - <span data-ttu-id="ea89e-169">Der reine Reflexionskontext zum sicheren Laden von Assemblys, um Ihre Metadaten zu lesen, ohne sie zu ausführen</span><span class="sxs-lookup"><span data-stu-id="ea89e-169">The reflection-only context, for safely loading assemblies to read their metadata without running them</span></span>
  - <span data-ttu-id="ea89e-170">Das geheimnisvolle „Nichts“, in dem sich mit `Assembly.LoadFile(string path)` und `Assembly.Load(byte[] asmBytes)` geladene Assemblys befinden</span><span class="sxs-lookup"><span data-stu-id="ea89e-170">The mysterious void that assemblies loaded with `Assembly.LoadFile(string path)` and `Assembly.Load(byte[] asmBytes)` live in</span></span>

<span data-ttu-id="ea89e-171">In .NET Core (und ab .NET 5) wurde dieses komplexe Modell durch ein einfacheres ersetzt:</span><span class="sxs-lookup"><span data-stu-id="ea89e-171">.NET Core (and .NET 5+) has replaced this complexity with a simpler model:</span></span>

- <span data-ttu-id="ea89e-172">Kein globaler Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="ea89e-172">No Global Assembly Cache.</span></span> <span data-ttu-id="ea89e-173">Anwendungen bringen alle eigene Abhängigkeiten ein.</span><span class="sxs-lookup"><span data-stu-id="ea89e-173">Applications bring all their own dependencies.</span></span> <span data-ttu-id="ea89e-174">Dadurch wird ein externer Faktor für die Auflösung von Abhängigkeiten in Anwendungen beseitigt, sodass die Auflösung von Abhängigkeiten reproduzierbarer wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-174">This removes an external factor for dependency resolution in applications, making dependency resolution more reproducible.</span></span>
  <span data-ttu-id="ea89e-175">PowerShell, als Plug-In-Host, erschwert dies für Module geringfügig.</span><span class="sxs-lookup"><span data-stu-id="ea89e-175">PowerShell, as the plugin host, complicates this slightly for modules.</span></span> <span data-ttu-id="ea89e-176">Seine Abhängigkeiten in `$PSHOME` gelten für alle Module.</span><span class="sxs-lookup"><span data-stu-id="ea89e-176">Its dependencies in `$PSHOME` are shared with all modules.</span></span>
- <span data-ttu-id="ea89e-177">Nur eine Anwendungsdomäne und keine Möglichkeit, neue zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-177">Only one Application Domain, and no ability to create new ones.</span></span> <span data-ttu-id="ea89e-178">Das Konzept der Anwendungsdomäne wird im .NET Core ausschließlich als globaler Zustand des .NET-Prozesses beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ea89e-178">The Application Domain concept is maintained in .NET Core purely to be the global state of the .NET process.</span></span>
- <span data-ttu-id="ea89e-179">Ein neues, erweiterbares Modell für den Assemblyladekontext (ALC).</span><span class="sxs-lookup"><span data-stu-id="ea89e-179">A new, extensible Assembly Load Context model.</span></span> <span data-ttu-id="ea89e-180">Der Assemblyauflösung kann ein Namespace hinzugefügt werden, indem sie in einem neuen ALC abgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-180">Assembly resolution can be namespaced by putting it in a new ALC.</span></span> <span data-ttu-id="ea89e-181">.NET Core-Prozesse beginnen mit einem einzelnen Standard-ALC, in den alle Assemblys geladen werden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-181">.NET Core processes begin with a single default ALC into which all assemblies are loaded.</span></span> <span data-ttu-id="ea89e-182">(mit Ausnahme derjenigen, die mit `Assembly.LoadFile(string)` und `Assembly.Load(byte[])` geladen wurden) Der Prozess kann jedoch eigene benutzerdefinierte ALCs mit eigener Ladelogik erstellen und definieren.</span><span class="sxs-lookup"><span data-stu-id="ea89e-182">(except for those loaded with `Assembly.LoadFile(string)` and `Assembly.Load(byte[])`) But the process can create and define its own custom ALCs with its own loading logic.</span></span> <span data-ttu-id="ea89e-183">Beim Laden einer Assembly ist der erste ALC, in den sie geladen wird, für die Auflösung ihrer Abhängigkeiten verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="ea89e-183">When an assembly is loaded, the first ALC it is loaded into is responsible for resolving its dependencies.</span></span> <span data-ttu-id="ea89e-184">Dies schafft Möglichkeiten zur Implementierung leistungsstarker .NET-Plug-In-Lademechanismen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-184">This creates opportunities to implement powerful .NET plugin loading mechanisms.</span></span>

<span data-ttu-id="ea89e-185">Bei beiden Implementierungen werden Assemblys verzögert geladen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-185">In both implementations, assemblies are loaded lazily.</span></span> <span data-ttu-id="ea89e-186">Das bedeutet, dass sie geladen werden, wenn eine Methode, die ihren Typ erfordert, zum ersten Mal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-186">This means that they are loaded when a method requiring their type is run for the first time.</span></span>

<span data-ttu-id="ea89e-187">Hier sind zum Beispiel zwei Versionen desselben Codes, die eine Abhängigkeit zu unterschiedlichen Zeiten laden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-187">For example, here are two versions of the same code that load a dependency at different times.</span></span>

<span data-ttu-id="ea89e-188">Die erste lädt ihre Abhängigkeit immer dann, wenn `Program.GetRange()` aufgerufen wird, weil der Abhängigkeitsverweis lexikalisch innerhalb der Methode vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="ea89e-188">The first always loads its dependency when `Program.GetRange()` is called, because the dependency reference is lexically present within the method:</span></span>

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetRange(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library will be loaded when GetRange is run
                // because the dependency call occurs directly within the method
                DependencyApi.Use();
            }

            list.Add(i);
        }
        return list;
    }
}
```

<span data-ttu-id="ea89e-189">Die zweite lädt ihre Abhängigkeit nur, wenn der Parameter `limit` mindestens 20 beträgt, aufgrund der internen Dereferenzierung durch eine Methode:</span><span class="sxs-lookup"><span data-stu-id="ea89e-189">The second will load its dependency only if the `limit` parameter is 20 or more, because of the internal indirection through a method:</span></span>

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetNumbers(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library is only referenced within
                // the UseDependencyApi() method,
                // so will only be loaded when limit >= 20
                UseDependencyApi();
            }

            list.Add(i);
        }
        return list;
    }

    private static void UseDependencyApi()
    {
        // Once UseDependencyApi() is called, Dependency.Library is loaded
        DependencyApi.Use();
    }
}
```

<span data-ttu-id="ea89e-190">Dies ist eine bewährte Methode, da sie E/A-Vorgänge im Arbeitsspeicher und Dateisystem minimiert und die Ressourcen effizienter nutzt.</span><span class="sxs-lookup"><span data-stu-id="ea89e-190">This is a good practice since it minimizes the memory and filesystem I/O and uses the resources more efficiently.</span></span> <span data-ttu-id="ea89e-191">Der unglückliche Nebeneffekt ist allerdings, dass wir nicht wissen, dass die Assembly nicht geladen wird, bis wir den Codepfad erreichen, der versucht, die Assembly zu laden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-191">The unfortunate a side effect of this is that we won't know that the assembly fails to load until we reach the code path that tries to load the assembly.</span></span>

<span data-ttu-id="ea89e-192">Sie kann auch eine zeitabhängige Bedingung für Assemblyladekonflikte schaffen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-192">It can also create a timing condition for assembly load conflicts.</span></span> <span data-ttu-id="ea89e-193">Wenn zwei Teile desselben Programms versuchen, verschiedene Versionen desselben Assemblys zu laden, hängt die geladene Version davon ab, welcher Codepfad zuerst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-193">If two parts of the same program try to load different versions of the same assembly, the version loaded depends on which code path is run first.</span></span>

<span data-ttu-id="ea89e-194">Für PowerShell bedeutet dies, dass die folgenden Faktoren einen Assemblyladekonflikt beeinflussen können:</span><span class="sxs-lookup"><span data-stu-id="ea89e-194">For PowerShell, this means that the following factors can affect an assembly load conflict:</span></span>

- <span data-ttu-id="ea89e-195">Welches Modul wurde zuerst geladen?</span><span class="sxs-lookup"><span data-stu-id="ea89e-195">Which module was loaded first?</span></span>
- <span data-ttu-id="ea89e-196">Wurde der Codepfad ausgeführt, der die Abhängigkeitsbibliothek verwendet?</span><span class="sxs-lookup"><span data-stu-id="ea89e-196">Was the code path that uses the dependency library run?</span></span>
- <span data-ttu-id="ea89e-197">Lädt PowerShell eine in Konflikt stehende Abhängigkeit beim Start oder nur unter bestimmten Codepfaden?</span><span class="sxs-lookup"><span data-stu-id="ea89e-197">Does PowerShell load a conflicting dependency at startup or only under certain code paths?</span></span>

## <a name="quick-fixes-and-their-limitations"></a><span data-ttu-id="ea89e-198">Schnellkorrekturen und ihre Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ea89e-198">Quick fixes and their limitations</span></span>

<span data-ttu-id="ea89e-199">In einigen Fällen ist es möglich, kleine Anpassungen an Ihrem Modul vorzunehmen und Dinge mit minimalem Aufwand zu korrigieren.</span><span class="sxs-lookup"><span data-stu-id="ea89e-199">In some cases, it's possible to make small adjustments to your module and fix things with minimal effort.</span></span> <span data-ttu-id="ea89e-200">Aber diese Lösungen sind in der Regel mit Vorbehalt zu genießen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-200">But these solutions tend to come with caveats.</span></span> <span data-ttu-id="ea89e-201">Sie können sich zwar für Ihr Modul eignen, funktionieren aber nicht für jedes Modul.</span><span class="sxs-lookup"><span data-stu-id="ea89e-201">While they may apply to your module, they won't work for every module.</span></span>

### <a name="change-your-dependency-version"></a><span data-ttu-id="ea89e-202">Ändern der Abhängigkeitsversion</span><span class="sxs-lookup"><span data-stu-id="ea89e-202">Change your dependency version</span></span>

<span data-ttu-id="ea89e-203">Der einfachste Weg, Abhängigkeitskonflikte zu vermeiden, ist, sich auf eine Abhängigkeit zu einigen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-203">The simplest way to avoid dependency conflicts is to agree on a dependency.</span></span> <span data-ttu-id="ea89e-204">Dies ist möglicherweise in folgenden Fällen möglich:</span><span class="sxs-lookup"><span data-stu-id="ea89e-204">This may be possible when:</span></span>

- <span data-ttu-id="ea89e-205">Ihr Konflikt besteht in einer direkten Abhängigkeit Ihres Moduls, und Sie kontrollieren die Version.</span><span class="sxs-lookup"><span data-stu-id="ea89e-205">Your conflict is with a direct dependency of your module and you control the version.</span></span>
- <span data-ttu-id="ea89e-206">Ihr Konflikt besteht in einer indirekten Abhängigkeit, aber Sie können Ihre direkten Abhängigkeiten so konfigurieren, dass Sie eine funktionsfähige Version der indirekten Abhängigkeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-206">Your conflict is with an indirect dependency, but you can configure your direct dependencies to use a workable indirect dependency version.</span></span>
- <span data-ttu-id="ea89e-207">Sie kennen die in Konflikt stehende Version und können sich darauf verlassen, dass sie sich nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="ea89e-207">You know the conflicting version and can rely on it not changing.</span></span>

<span data-ttu-id="ea89e-208">Das Paket `Newtonsoft.Json` ist ein gutes Beispiel für dieses letzte Szenario.</span><span class="sxs-lookup"><span data-stu-id="ea89e-208">The `Newtonsoft.Json` package is a good example of this last scenario.</span></span> <span data-ttu-id="ea89e-209">Es hat eine Abhängigkeit von mindestens PowerShell 6 und wird in Windows PowerShell nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ea89e-209">This is a dependency of PowerShell 6 and above, and isn't used in Windows PowerShell.</span></span> <span data-ttu-id="ea89e-210">Eine einfache Methode zur Lösung von Versionsverwaltungskonflikten besteht also darin, die niedrigste Version von `Newtonsoft.Json` in allen PowerShell-Versionen zu verwenden, auf die Sie abzielen möchten.</span><span class="sxs-lookup"><span data-stu-id="ea89e-210">Meaning a simple way to resolve versioning conflicts is to target the lowest version of `Newtonsoft.Json` across the PowerShell versions you wish to target.</span></span>

<span data-ttu-id="ea89e-211">Beispielsweise verwenden PowerShell 6.2.6 und PowerShell 7.0.2 derzeit beide die `Newtonsoft.Json`-Version 12.0.3.</span><span class="sxs-lookup"><span data-stu-id="ea89e-211">For example, PowerShell 6.2.6 and PowerShell 7.0.2 both currently use `Newtonsoft.Json` version 12.0.3.</span></span> <span data-ttu-id="ea89e-212">Um also ein auf Windows PowerShell, PowerShell 6 und PowerShell 7 abzielendes Modul zu erstellen, würden Sie `Newtonsoft.Json 12.0.3` als Abhängigkeit anvisieren und in Ihr erstelltes Modul aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-212">So, to create a module targeting Windows PowerShell, PowerShell 6, and PowerShell 7, you would target `Newtonsoft.Json 12.0.3` as a dependency and include it in your built module.</span></span> <span data-ttu-id="ea89e-213">Wenn das Modul in PowerShell 6 oder 7 geladen wird, ist die eigene Assembly `Newtonsoft.Json` von PowerShell bereits geladen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-213">When the module is loaded in PowerShell 6 or 7, PowerShell's own `Newtonsoft.Json` assembly is already loaded.</span></span> <span data-ttu-id="ea89e-214">Außerdem handelt es sich mindestens um die für Ihr Modul erforderliche Version, sodass die Auflösung erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="ea89e-214">Also, it is at least the version required for your module, so resolution succeeds.</span></span> <span data-ttu-id="ea89e-215">In Windows PowerShell ist die Assembly nicht bereits in PowerShell vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-215">In Windows PowerShell, the assembly isn't already present in PowerShell.</span></span> <span data-ttu-id="ea89e-216">Daher wird sie stattdessen aus Ihrem Modulordner geladen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-216">So, it's loaded from your module folder instead.</span></span>

<span data-ttu-id="ea89e-217">Im Allgemeinen sollte NuGet, wenn auf ein konkretes PowerShell-Paket wie `Microsoft.PowerShell.Sdk` oder `System.Management.Automation` abgezielt wird, in der Lage sein, die richtigen erforderlichen Abhängigkeitsversionen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-217">Generally, when targeting a concrete PowerShell package, like `Microsoft.PowerShell.Sdk` or `System.Management.Automation`, NuGet should be able to resolve the right dependency versions required.</span></span> <span data-ttu-id="ea89e-218">Das Abzielen auf Windows PowerShell und PowerShell-Version 6 wird schwieriger, da Sie zwischen dem Abzielen auf mehrere Frameworks oder `PowerShellStandard.Library` wählen müssen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-218">Targeting both Windows PowerShell and PowerShell 6+ becomes more difficult because you must choose between targeting multiple frameworks or `PowerShellStandard.Library`.</span></span>

<span data-ttu-id="ea89e-219">Zu den Umständen, unter denen das Festlegen auf eine gemeinsame Abhängigkeitsversion nicht funktioniert, gehören u. a.:</span><span class="sxs-lookup"><span data-stu-id="ea89e-219">Circumstances where pinning to a common dependency version won't work include:</span></span>

- <span data-ttu-id="ea89e-220">Der Konflikt besteht in einer indirekten Abhängigkeit, und keine Ihrer Abhängigkeiten kann so konfiguriert werden, dass eine gemeinsame Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-220">The conflict is with an indirect dependency, and none of your dependencies can be configured to use a common version.</span></span>
- <span data-ttu-id="ea89e-221">Die andere Abhängigkeitsversion wird sich wahrscheinlich häufig ändern, sodass die Einigung auf eine gemeinsame Version nur eine kurzfristige Lösung ist.</span><span class="sxs-lookup"><span data-stu-id="ea89e-221">The other dependency version is likely to change often, so settling on a common version is only a short-term fix.</span></span>

### <a name="add-an-assemblyresolve-event-handler-to-create-a-dynamic-binding-redirect"></a><span data-ttu-id="ea89e-222">Hinzufügen eines AssemblyResolve-Ereignishandlers zum Erstellen einer dynamischen Bindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="ea89e-222">Add an AssemblyResolve event handler to create a dynamic binding redirect</span></span>

<span data-ttu-id="ea89e-223">Mitunter ist es nicht möglich oder zu schwierig, die eigene Abhängigkeitsversion zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ea89e-223">Sometimes changing your own dependency version isn't possible or is too difficult.</span></span> <span data-ttu-id="ea89e-224">Eine andere Möglichkeit besteht darin, eine dynamische Bindungsumleitung einzurichten, indem ein Ereignishandler für das `AssemblyResolve`-Ereignis registriert wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-224">Another option is to set up a dynamic binding redirect by registering an event handler for the `AssemblyResolve` event.</span></span>

<span data-ttu-id="ea89e-225">Wie bei einer statischen Bindungsumleitung geht es darum, alle Consumer einer Abhängigkeit zu zwingen, dieselbe konkrete Assembly zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-225">As with a static binding redirect, the point is to force all consumers of a dependency to use the same actual assembly.</span></span> <span data-ttu-id="ea89e-226">Sie fangen Aufrufe zum Laden der Abhängigkeit ab und leiten sie immer auf die gewünschte Version um.</span><span class="sxs-lookup"><span data-stu-id="ea89e-226">You intercept calls to load the dependency and always redirect them to the version you want.</span></span>

<span data-ttu-id="ea89e-227">Das sieht etwa wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ea89e-227">This looks something like this:</span></span>

```csharp
// Register the event handler as early as you can in your code.
// A good option is to use the IModuleAssemblyInitializer interface
// that PowerShell provides to run code early on when your module is loaded.

// This class will be instantiated on module import and the OnImport() method run.
// Make sure that:
//  - the class is public
//  - the class has a public, parameterless constructor
//  - the class implements IModuleAssemblyInitializer
public class MyModuleInitializer : IModuleAssemblyInitializer
{
    public void OnImport()
    {
        AppDomain.CurrentDomain.AssemblyResolve += DependencyResolution.ResolveNewtonsoftJson;
    }
}

// Clean up the event handler when the the module is removed
// to prevent memory leaks.
//
// Like IModuleAssemblyInitializer, IModuleAssemblyCleanup allows
// you to register code to run when a module is removed (with Remove-Module).
// Make sure it is also public with a public parameterless contructor
// and implements IModuleAssemblyCleanup.
public class MyModuleCleanup : IModuleAssemblyCleanup
{
    public void OnRemove()
    {
        AppDomain.CurrentDomain.AssemblyResolve -= DependencyResolution.ResolveNewtonsoftJson;
    }
}

internal static class DependencyResolution
{
    private static readonly string s_modulePath = Path.GetDirectoryName(
        Assembly.GetExecutingAssembly().Location);

    public static Assembly ResolveNewtonsoftJson(object sender, ResolveEventArgs args)
    {
        // Parse the assembly name
        var assemblyName = new AssemblyName(args.Name);

        // We only want to handle the dependency we care about.
        // In this example it's Newtonsoft.Json.
        if (!assemblyName.Name.Equals("Newtonsoft.Json"))
        {
            return null;
        }

        // Generally the version of the dependency you want to load is the higher one,
        // since it's the most likely to be compatible with all dependent assemblies.
        // The logic here assumes our module always has the version we want to load.
        // Also note the use of Assembly.LoadFrom() here rather than Assembly.LoadFile().
        return Assembly.LoadFrom(Path.Combine(s_modulePath, "Newtonsoft.Json.dll"));
    }
}
```

<span data-ttu-id="ea89e-228">Technisch gesehen können Sie einen Skriptblock in PowerShell registrieren, um ein `AssemblyResolve`-Ereignis zu behandeln, aber:</span><span class="sxs-lookup"><span data-stu-id="ea89e-228">You can technically register a scriptblock within PowerShell to handle an `AssemblyResolve` event, but:</span></span>

- <span data-ttu-id="ea89e-229">Ein `AssemblyResolve`-Ereignis kann in jedem Thread ausgelöst werden, was etwas ist, womit PowerShell nicht umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="ea89e-229">An `AssemblyResolve` event may be triggered on any thread, something that PowerShell will be unable to handle.</span></span>
- <span data-ttu-id="ea89e-230">Selbst wenn Ereignisse im richtigen Thread verarbeitet werden, bedeutet das Eingrenzungskonzept von PowerShell, dass der Skriptblock des Ereignishandlers sorgfältig geschrieben werden muss, um nicht von außerhalb definierten Variablen abhängig zu sein.</span><span class="sxs-lookup"><span data-stu-id="ea89e-230">Even when events are handled on the right thread, PowerShell's scoping concepts mean that the event handler scriptblock must be written carefully to not depend on variables defined outside it.</span></span>

<span data-ttu-id="ea89e-231">Es gibt Situationen, in denen das Umleiten zu einer gemeinsamen Version nicht funktioniert:</span><span class="sxs-lookup"><span data-stu-id="ea89e-231">There are situations where redirecting to a common version won't work:</span></span>

- <span data-ttu-id="ea89e-232">Wenn die Abhängigkeit Breaking Changes zwischen Versionen vorgenommen hat oder abhängiger Code sich auf eine Funktionalität stützt, die in der Version, zu der Sie umleiten, nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ea89e-232">When the dependency has made breaking changes between versions, or when dependent code relies on a functionality otherwise not available in the version you redirect to.</span></span>
- <span data-ttu-id="ea89e-233">Wenn Ihr Modul nicht vor der in Konflikt stehenden Abhängigkeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-233">When your module isn't loaded before the conflicting dependency.</span></span> <span data-ttu-id="ea89e-234">Wenn Sie einen `AssemblyResolve`-Ereignishandler registrieren, nachdem die Abhängigkeit geladen wurde, wird er nie ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ea89e-234">If you register an `AssemblyResolve` event handler after the dependency has been loaded, it will never be fired.</span></span> <span data-ttu-id="ea89e-235">Wenn Sie versuchen, Abhängigkeitskonflikte mit einem anderen Modul zu verhindern, kann dies problematisch sein, da das andere Modul möglicherweise zuerst geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-235">If you're trying to prevent dependency conflicts with another module, this may be an issue, since the other module may be loaded first.</span></span>

### <a name="use-the-dependency-out-of-process"></a><span data-ttu-id="ea89e-236">Verwenden der Abhängigkeiten außerhalb des Prozesses</span><span class="sxs-lookup"><span data-stu-id="ea89e-236">Use the dependency out of process</span></span>

<span data-ttu-id="ea89e-237">Diese Lösung eignet sich eher für Modulbenutzer als Modulentwickler.</span><span class="sxs-lookup"><span data-stu-id="ea89e-237">This solution is more for module users than module authors.</span></span> <span data-ttu-id="ea89e-238">Sie kommt zum Einsatz, wenn Sie mit einem Modul konfrontiert werden, das aufgrund eines bestehenden Abhängigkeitskonflikts nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ea89e-238">This is a solution to use when confronted with a module that won't work due to an existing dependency conflict.</span></span>

<span data-ttu-id="ea89e-239">Abhängigkeitskonflikte treten auf, weil zwei Versionen der gleichen Assembly in denselben .NET-Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-239">Dependency conflicts occur because two versions of the same assembly are loaded into the same .NET process.</span></span> <span data-ttu-id="ea89e-240">Eine einfache Lösung besteht darin, sie in verschiedene Prozesse zu laden, solange Sie die Funktionalität von beiden noch gemeinsam nutzen können.</span><span class="sxs-lookup"><span data-stu-id="ea89e-240">A simple solution is to load them into different processes, as long as you can still use the functionality from both together.</span></span>

<span data-ttu-id="ea89e-241">PowerShell bietet dazu mehrere Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="ea89e-241">In PowerShell, there are several ways to achieve this:</span></span>

- <span data-ttu-id="ea89e-242">Aufrufen von PowerShell als Teilprozess</span><span class="sxs-lookup"><span data-stu-id="ea89e-242">Invoke PowerShell as a subprocess</span></span>

  <span data-ttu-id="ea89e-243">Eine einfache Möglichkeit, einen PowerShell-Befehl außerhalb des aktuellen Prozesses auszuführen, besteht darin, einfach direkt mit dem Befehlsaufruf einen neuen PowerShell-Prozess zu starten:</span><span class="sxs-lookup"><span data-stu-id="ea89e-243">A simple way to run a PowerShell command out of the current process is to just start a new PowerShell process directly with the command call:</span></span>

  ```powershell
  pwsh -c 'Invoke-ConflictingCommand'
  ```

  <span data-ttu-id="ea89e-244">Die Haupteinschränkung ist hierbei, dass die Umstrukturierung des Ergebnisses schwieriger oder fehleranfälliger sein kann als bei anderen Optionen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-244">The main limitation here is that restructuring the result can be trickier or more error prone than other options.</span></span>

- <span data-ttu-id="ea89e-245">Das PowerShell-Auftragssystem</span><span class="sxs-lookup"><span data-stu-id="ea89e-245">The PowerShell job system</span></span>

  <span data-ttu-id="ea89e-246">Das PowerShell-Auftragssystem führt auch Befehle außerhalb des Prozesses aus, indem es Befehle an einen neuen PowerShell-Prozess sendet und die Ergebnisse zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="ea89e-246">The PowerShell job system also runs commands out of process, by sending commands to a new PowerShell process and returning the results:</span></span>

  ```powershell
  $result = Start-Job { Invoke-ConflictingCommand } | Receive-Job -Wait
  ```

  <span data-ttu-id="ea89e-247">In diesem Fall müssen Sie nur sicher sein, dass alle Variablen und Zustände korrekt übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-247">In this case, you just need to be sure that any variables and state are passed in correctly.</span></span>

  <span data-ttu-id="ea89e-248">Das Auftragssystem kann auch bei der Ausführung kleiner Befehle etwas umständlich sein.</span><span class="sxs-lookup"><span data-stu-id="ea89e-248">The job system can also be slightly cumbersome when running small commands.</span></span>

- <span data-ttu-id="ea89e-249">PowerShell-Remoting</span><span class="sxs-lookup"><span data-stu-id="ea89e-249">PowerShell remoting</span></span>

  <span data-ttu-id="ea89e-250">Falls verfügbar, kann PowerShell-Remoting eine nützliche Möglichkeit sein, Befehle außerhalb des Prozesses auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-250">When it's available, PowerShell remoting can be a useful way to run commands out of process.</span></span> <span data-ttu-id="ea89e-251">Mit Remoting können Sie eine neue **PSSession** in einem neuen Prozess erstellen, seine Befehle über PowerShell-Remoting aufrufen und die Ergebnisse dann lokal mit den anderen Modulen verwenden, die die in Konflikt stehenden Abhängigkeiten enthalten.</span><span class="sxs-lookup"><span data-stu-id="ea89e-251">With remoting, you can create a fresh **PSSession** in a new process, call its commands over PowerShell remoting, then use the results locally with the other modules containing the conflicting dependencies.</span></span>

  <span data-ttu-id="ea89e-252">Ein Beispiel kann wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="ea89e-252">An example might look like this:</span></span>

  ```powershell
  # Create a local PowerShell session
  # where the module with conflicting assemblies will be loaded
  $s = New-PSSession

  # Import the module with the conflicting dependency via remoting,
  # exposing the commands locally
  Import-Module -PSSession $s -Name ConflictingModule

  # Run a command from the module with the conflicting dependencies
  Invoke-ConflictingCommand
  ```

- <span data-ttu-id="ea89e-253">Implizites Remoting zu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea89e-253">Implicit remoting to Windows PowerShell</span></span>

  <span data-ttu-id="ea89e-254">Eine weitere Option in PowerShell 7 ist die Verwendung des Flags `-UseWindowsPowerShell` für `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="ea89e-254">Another option in PowerShell 7 is to use the `-UseWindowsPowerShell` flag on `Import-Module`.</span></span> <span data-ttu-id="ea89e-255">Dadurch wird das Modul über eine lokale Remotingsitzung in Windows PowerShell importiert:</span><span class="sxs-lookup"><span data-stu-id="ea89e-255">This will import the module through a local remoting session into Windows PowerShell:</span></span>

  ```powershell
  Import-Module -Name ConflictingModule -UseWindowsPowerShell
  ```

  <span data-ttu-id="ea89e-256">Beachten Sie, dass Module mit Windows PowerShell möglicherweise nicht oder anders funktionieren.</span><span class="sxs-lookup"><span data-stu-id="ea89e-256">Be aware that modules may not work with, or work differently with Windows PowerShell.</span></span>

#### <a name="when-out-of-process-invocation-should-not-be-used"></a><span data-ttu-id="ea89e-257">Wann der Aufruf außerhalb des Prozesses nicht verwendet werden sollte</span><span class="sxs-lookup"><span data-stu-id="ea89e-257">When out-of-process invocation should not be used</span></span>

<span data-ttu-id="ea89e-258">Als Entwickler eines Moduls ist es schwierig, den Aufruf von Befehlen außerhalb des Prozesses in ein Modul zu integrieren, und es können Randfälle auftreten, die Probleme verursachen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-258">As a module author, out-of-process command invocation is difficult to bake into a module and may have edge cases that cause issues.</span></span> <span data-ttu-id="ea89e-259">Insbesondere Remoting und Aufträge sind möglicherweise nicht in allen Umgebungen verfügbar, in denen Ihr Modul funktionieren muss.</span><span class="sxs-lookup"><span data-stu-id="ea89e-259">In particular, remoting and jobs may not be available in all environments where your module needs to work.</span></span> <span data-ttu-id="ea89e-260">Das allgemeine Prinzip, die Implementierung aus dem Prozess herauszulösen und zuzulassen, dass das PowerShell-Modul ein schlankerer Client ist, kann jedoch weiterhin zutreffen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-260">However, the general principle of moving the implementation out of process and allowing the PowerShell module to be a thinner client, may still be applicable.</span></span>

<span data-ttu-id="ea89e-261">Für Modulbenutzer gibt es Fälle, in denen der prozessexterne Aufruf nicht funktioniert:</span><span class="sxs-lookup"><span data-stu-id="ea89e-261">As a module user, there are cases where out-of-process invocation won't work:</span></span>

- <span data-ttu-id="ea89e-262">Wenn PowerShell-Remoting nicht verfügbar ist, weil Sie keine Berechtigungen zu seiner Verwendung haben oder es nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ea89e-262">When PowerShell remoting is unavailable because you don't have privileges to use it or it is not enabled.</span></span>
- <span data-ttu-id="ea89e-263">Wenn ein bestimmter .NET-Typ von der Ausgabe als Eingabe für eine Methode oder einen anderen Befehl benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-263">When a particular .NET type is needed from output as input to a method or another command.</span></span>
  <span data-ttu-id="ea89e-264">Befehle, die über PowerShell-Remoting ausgeführt werden, geben deserialisierte Objekte anstelle stark typisierter .NET-Objekte aus.</span><span class="sxs-lookup"><span data-stu-id="ea89e-264">Commands running over PowerShell remoting emit deserialized objects rather than strongly-typed .NET objects.</span></span> <span data-ttu-id="ea89e-265">Dies bedeutet, dass Methodenaufrufe und stark typisierte APIs nicht mit der Ausgabe von Befehlen funktionieren, die über Remoting importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-265">This means that method calls and strongly typed APIs do not work with the output of commands imported over remoting.</span></span>

## <a name="more-robust-solutions"></a><span data-ttu-id="ea89e-266">Stabilere Lösungen</span><span class="sxs-lookup"><span data-stu-id="ea89e-266">More robust solutions</span></span>

<span data-ttu-id="ea89e-267">In allen vorherigen Lösungen gab es Szenarien und Module, die nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="ea89e-267">The previous solutions all had scenarios and modules that don't work.</span></span> <span data-ttu-id="ea89e-268">Sie haben aber auch den Vorzug, dass sie relativ einfach ordnungsgemäß zu implementieren sind.</span><span class="sxs-lookup"><span data-stu-id="ea89e-268">However, they also have the virtue of being relatively simple to implement correctly.</span></span> <span data-ttu-id="ea89e-269">Die folgenden Lösungen sind zwar stabiler, erfordern aber einen größeren Aufwand, um sie einwandfrei zu implementieren, und können mitunter zu heiklen Fehlern führen, wenn sie nicht sorgfältig geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-269">The following solutions are more robust, but require more effort to implement correctly and can introduce subtle bugs if not written carefully.</span></span>

### <a name="loading-through-net-core-assembly-load-contexts"></a><span data-ttu-id="ea89e-270">Laden über .NET Core-Assemblyladekontexte</span><span class="sxs-lookup"><span data-stu-id="ea89e-270">Loading through .NET Core Assembly Load Contexts</span></span>

<span data-ttu-id="ea89e-271">[Assemblyladekontexte](/dotnet/api/system.runtime.loader.assemblyloadcontext) (ALCs) als implementierbare API wurden in .NET Core 1.0 eingeführt, um speziell der Notwendigkeit Rechnung zu tragen, mehrere Versionen derselben Assembly in dieselbe Laufzeit zu laden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-271">[Assembly Load Contexts](/dotnet/api/system.runtime.loader.assemblyloadcontext) (ALCs) as an implementable API were introduced in .NET Core 1.0 to specifically address the need to load multiple versions of the same assembly into the same runtime.</span></span>

<span data-ttu-id="ea89e-272">In .NET Core und .NET 5 stellen sie die stabilste Lösung für das Problem des Ladens in Konflikt stehender Versionen einer Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="ea89e-272">Within .NET Core and .NET 5, they offer the most robust solution to the problem of loading conflicting versions of an assembly.</span></span> <span data-ttu-id="ea89e-273">Benutzerdefinierte ALCs sind jedoch in .NET Framework nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ea89e-273">However, custom ALCs are not available in .NET Framework.</span></span> <span data-ttu-id="ea89e-274">Dies bedeutet, dass diese Lösung nur ab PowerShell 6 funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ea89e-274">This means that this solution only works in PowerShell 6 and above.</span></span>

<span data-ttu-id="ea89e-275">Derzeit ist das beste Beispiel für die Verwendung eines ALC zur Isolierung von Abhängigkeiten in PowerShell in PowerShell Editor Services der Sprachserver für die PowerShell-Erweiterung für Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="ea89e-275">Currently, the best example of using an ALC for dependency isolation in PowerShell is in PowerShell Editor Services, the language server for the PowerShell extension for Visual Studio Code.</span></span> <span data-ttu-id="ea89e-276">Ein [ALC wird verwendet](https://github.com/PowerShell/PowerShellEditorServices/blob/master/src/PowerShellEditorServices.Hosting/Internal/PsesLoadContext.cs), um zu verhindern, dass die eigenen Abhängigkeiten von PowerShell Editor Services mit denen in PowerShell-Modulen in Konflikt geraten.</span><span class="sxs-lookup"><span data-stu-id="ea89e-276">An [ALC is used](https://github.com/PowerShell/PowerShellEditorServices/blob/master/src/PowerShellEditorServices.Hosting/Internal/PsesLoadContext.cs) to prevent PowerShell Editor Services' own dependencies from clashing with those in PowerShell modules.</span></span>

<span data-ttu-id="ea89e-277">Die Implementierung der Modulabhängigkeitsisolation mit einem ALC ist konzeptionell schwierig, doch wir werden dazu ein Minimalbeispiel durchgehen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-277">Implementing module dependency isolation with an ALC is conceptually difficult, but we will work through a minimal example.</span></span> <span data-ttu-id="ea89e-278">Stellen Sie sich vor, wir haben ein einfaches Modul, das nur für den Einsatz in PowerShell 7 vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="ea89e-278">Imagine we have a simple module that is only intended to work in PowerShell 7.</span></span>
<span data-ttu-id="ea89e-279">Der Quellcode ist wie folgt organisiert:</span><span class="sxs-lookup"><span data-stu-id="ea89e-279">The source code is organized as follows:</span></span>

```
+ AlcModule.psd1
+ src/
    + TestAlcModuleCommand.cs
    + AlcModule.csproj
```

<span data-ttu-id="ea89e-280">Die Cmdlet-Implementierung sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ea89e-280">The cmdlet implementation looks like this:</span></span>

```csharp
using Shared.Dependency;

namespace AlcModule
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            // Here's where our dependency gets used
            Dependency.Use();
            // Something trivial to make our cmdlet do *something*
            WriteObject("done!");
        }
    }
}
```

<span data-ttu-id="ea89e-281">Das (stark vereinfachte) Manifest sieht so aus:</span><span class="sxs-lookup"><span data-stu-id="ea89e-281">The (heavily simplified) manifest, looks like this:</span></span>

```powershell
@{
    Author = 'Me'
    ModuleVersion = '0.0.1'
    RootModule = 'AlcModule.dll'
    CmdletsToExport = @('Test-AlcModule')
    PowerShellVersion = '7.0'
}
```

<span data-ttu-id="ea89e-282">Und `csproj` sieht so aus:</span><span class="sxs-lookup"><span data-stu-id="ea89e-282">And the `csproj` looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="ea89e-283">Wenn wir dieses Modul erstellen, hat die generierte Ausgabe das folgende Layout:</span><span class="sxs-lookup"><span data-stu-id="ea89e-283">When we build this module, the generated output has the following layout:</span></span>

```
AlcModule/
  + AlcModule.psd1
  + AlcModule.dll
  + Shared.Dependency.dll
```

<span data-ttu-id="ea89e-284">Bei diesem Beispiel liegt unser Problem in der `Shared.Dependency.dll` Assembly, d. h. in unserer imaginären in Konflikt stehenden Abhängigkeit.</span><span class="sxs-lookup"><span data-stu-id="ea89e-284">In this example, our problem is in the `Shared.Dependency.dll` assembly, which is our imaginary conflicting dependency.</span></span> <span data-ttu-id="ea89e-285">Das ist die Abhängigkeit, die wir hinter einem ALC ansiedeln müssen, damit wir die modulspezifische Version verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ea89e-285">This is the dependency that we need to put behind an ALC so that we can use the module-specific version.</span></span>

<span data-ttu-id="ea89e-286">Wir müssen das Modul so neu gestalten, dass Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="ea89e-286">We need to re-engineer the module so that:</span></span>

- <span data-ttu-id="ea89e-287">Modulabhängigkeiten werden nur in unseren benutzerdefinierten ALC geladen und nicht in den ALC von PowerShell, sodass es zu keinem Konflikt kommen kann.</span><span class="sxs-lookup"><span data-stu-id="ea89e-287">Module dependencies are only loaded into our custom ALC, and not into PowerShell's ALC, so there can be no conflict.</span></span> <span data-ttu-id="ea89e-288">Da wir unserem Projekt immer mehr Abhängigkeiten hinzufügen, möchten wir außerdem nicht ständig weiteren Code hinzufügen, damit das Laden weiterhin funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ea89e-288">Moreover, as we add more dependencies to our project, we don't want to continuously add more code to keep loading working.</span></span> <span data-ttu-id="ea89e-289">Stattdessen wünschen wir uns wiederverwendbare, generische Logik zur Abhängigkeitsauflösung.</span><span class="sxs-lookup"><span data-stu-id="ea89e-289">Instead, we want reusable, generic dependency resolution logic.</span></span>
- <span data-ttu-id="ea89e-290">Das Laden des Moduls funktioniert in PowerShell weiterhin wie gewohnt.</span><span class="sxs-lookup"><span data-stu-id="ea89e-290">Loading the module still works as normal in PowerShell.</span></span> <span data-ttu-id="ea89e-291">Cmdlets und andere Typen, die das PowerShell-Modulsystem benötigt, sind im eigenen ALC von PowerShell definiert.</span><span class="sxs-lookup"><span data-stu-id="ea89e-291">Cmdlets and other types that the PowerShell module system needs are defined within PowerShell's own ALC.</span></span>

<span data-ttu-id="ea89e-292">Um diese beiden Anforderungen zu vereinbaren, müssen wir unser Modul in zwei Assemblys aufteilen:</span><span class="sxs-lookup"><span data-stu-id="ea89e-292">To mediate these two requirements, we must break up our module into two assemblies:</span></span>

- <span data-ttu-id="ea89e-293">Eine Assembly mit Cmdlets, `AlcModule.Cmdlets.dll`, die Definitionen aller Typen enthält, welche das PowerShell-Modulsystem benötigt, um das Modul ordnungsgemäß zu laden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-293">A cmdlets assembly, `AlcModule.Cmdlets.dll`, that contains definitions of all the types that PowerShell's module system needs to load our module correctly.</span></span> <span data-ttu-id="ea89e-294">Dabei handelt es sich um alle Implementierungen der Basisklasse `Cmdlet` und der Klasse, die `IModuleAssemblyInitializer` implementiert, die wiederum den Ereignishandler für `AssemblyLoadContext.Default.Resolving` zum ordnungsgemäßen Laden von `AlcModule.Engine.dll` über unseren benutzerdefinierten ALC einrichtet.</span><span class="sxs-lookup"><span data-stu-id="ea89e-294">Namely, any implementations of the `Cmdlet` base class and the class that implements `IModuleAssemblyInitializer`, which sets up the event handler for `AssemblyLoadContext.Default.Resolving` to properly load `AlcModule.Engine.dll` through our custom ALC.</span></span> <span data-ttu-id="ea89e-295">Da PowerShell 7 Typen, die in anderen ALCs geladenen Assemblys definiert sind, absichtlich ausblendet, müssen alle Typen, die PowerShell öffentlich verfügbar gemacht werden sollen, ebenfalls hier definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-295">Since PowerShell 7 deliberately hides types defined in assemblies loaded in other ALCs, any types that are meant to be publicly exposed to PowerShell must also be defined here.</span></span> <span data-ttu-id="ea89e-296">Schließlich muss unsere benutzerdefinierte ALC-Definition in dieser Assembly definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-296">Finally, our custom ALC definition needs to be defined in this assembly.</span></span> <span data-ttu-id="ea89e-297">Darüber hinaus sollte sich in dieser Assembly so wenig Code wie möglich befinden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-297">Beyond that, as little code as possible should live in this assembly.</span></span>
- <span data-ttu-id="ea89e-298">Eine Assembly für die Engine, `AlcModule.Engine.dll`, die die tatsächliche Implementierung des Moduls übernimmt.</span><span class="sxs-lookup"><span data-stu-id="ea89e-298">An engine assembly, `AlcModule.Engine.dll`, that handles the actual implementation of the module.</span></span>
  <span data-ttu-id="ea89e-299">Typen davon sind im ALC von PowerShell verfügbar, aber sie wird zunächst über unseren benutzerdefinierten ALC geladen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-299">Types from this are available in the PowerShell ALC, but it will initially be loaded through our custom ALC.</span></span> <span data-ttu-id="ea89e-300">Ihre Abhängigkeiten werden nur in den benutzerdefinierten ALC geladen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-300">Its dependencies are only loaded into the custom ALC.</span></span> <span data-ttu-id="ea89e-301">Dieser wird faktisch zu einer _Brücke_ zwischen den beiden ALCs.</span><span class="sxs-lookup"><span data-stu-id="ea89e-301">Effectively, this becomes a _bridge_ between the two ALCs.</span></span>

<span data-ttu-id="ea89e-302">Mit diesem Brückenkonzept sieht unsere neue Situation bei Assemblys so aus:</span><span class="sxs-lookup"><span data-stu-id="ea89e-302">Using this bridge concept, our new assembly situation looks like this:</span></span>

![Diagramm mit „AlcModule.Engine.dll“ als Brücke zwischen den beiden ALCs](./media/resolving-dependency-conflicts/alc-diagram.jpg)

<span data-ttu-id="ea89e-304">Um sicherzustellen, dass die Standardlogik des ALC zur Prüfung auf Abhängigkeiten nicht die in den benutzerdefinierten ALC zu ladenden Abhängigkeiten auflöst, müssen wir diese beiden Teile des Moduls in verschiedenen Verzeichnissen trennen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-304">To make sure the default ALC's dependency probing logic does not resolve the dependencies to be loaded into the custom ALC, we need to separate these two parts of the module in different directories.</span></span> <span data-ttu-id="ea89e-305">Das neue Modullayout hat die folgende Struktur:</span><span class="sxs-lookup"><span data-stu-id="ea89e-305">The new module layout has the following structure:</span></span>

```
AlcModule/
  AlcModule.Cmdlets.dll
  AlcModule.psd1
  Dependencies/
  | + AlcModule.Engine.dll
  | + Shared.Dependency.dll
```

<span data-ttu-id="ea89e-306">Um zu sehen, wie sich die Implementierung ändert, beginnen wir mit der Implementierung von `AlcModule.Engine.dll`:</span><span class="sxs-lookup"><span data-stu-id="ea89e-306">To see how the implementation changes, we'll start with the implementation of `AlcModule.Engine.dll`:</span></span>

```csharp
using Shared.Dependency;

namespace AlcModule.Engine
{
    public class AlcEngine
    {
        public static void Use()
        {
            Dependency.Use();
        }
    }
}
```

<span data-ttu-id="ea89e-307">Dies ist ein einfacher Container für die Abhängigkeit `Shared.Dependency.dll`. Sie sollten ihn jedoch als die .NET-API für Ihre Funktionalität betrachten, die von den Cmdlets in der anderen Assembly für PowerShell umschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-307">This is a simple container for the dependency, `Shared.Dependency.dll`, but you should think of it as the .NET API for your functionality that the cmdlets in the other assembly wrap for PowerShell.</span></span>

<span data-ttu-id="ea89e-308">Das Cmdlet in `AlcModule.Cmdlets.dll` sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ea89e-308">The cmdlet in `AlcModule.Cmdlets.dll` looks like this:</span></span>

```csharp
// Reference our module's Engine implementation here
using AlcModule.Engine;

namespace AlcModule.Cmdlets
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            AlcEngine.Use();
            WriteObject("done!");
        }
    }
}
```

<span data-ttu-id="ea89e-309">Wenn wir an diesem Punkt **AlcModule** laden und `Test-AlcModule` ausführen würden, erhielten wir eine `FileNotFoundException`, wenn der Standard-ALC versucht, `Alc.Engine.dll` zu laden, um `EndProcessing()` auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-309">At this point, if we were to load **AlcModule** and run `Test-AlcModule`, we get a `FileNotFoundException` when the default ALC tries to load `Alc.Engine.dll` to run `EndProcessing()`.</span></span> <span data-ttu-id="ea89e-310">Das ist gut, da es bedeutet, dass der Standard-ALC die Abhängigkeiten, die wir ausblenden möchten, nicht finden kann.</span><span class="sxs-lookup"><span data-stu-id="ea89e-310">This is good, since it means the default ALC can't find the dependencies we want to hide.</span></span>

<span data-ttu-id="ea89e-311">Jetzt müssen wir `AlcModule.Cmdlets.dll` Code hinzufügen, damit die DLL weiß, wie `AlcModule.Engine.dll` aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="ea89e-311">Now we need to add code to `AlcModule.Cmdlets.dll` so that it knows how to resolve `AlcModule.Engine.dll`.</span></span> <span data-ttu-id="ea89e-312">Zuerst müssen wir unseren benutzerdefinierten ALC definieren, der Assemblys im Verzeichnis `Dependencies` unseres Moduls auflöst:</span><span class="sxs-lookup"><span data-stu-id="ea89e-312">First we must define our custom ALC that will resolve assemblies from our module's `Dependencies` directory:</span></span>

```csharp
namespace AlcModule.Cmdlets
{
    internal class AlcModuleAssemblyLoadContext : AssemblyLoadContext
    {
        private readonly string _dependencyDirPath;

        public AlcModuleAssemblyLoadContext(string dependencyDirPath)
        {
            _dependencyDirPath = dependencyDirPath;
        }

        protected override Assembly Load(AssemblyName assemblyName)
        {
            // We do the simple logic here of
            // looking for an assembly of the given name
            // in the configured dependency directory
            string assemblyPath = Path.Combine(
                _dependencyDirPath,
                $"{assemblyName.Name}.dll");

            // The ALC must use inherited methods to load assemblies
            // Assembly.Load*() won't work here
            return LoadFromAssemblyPath(assemblyPath);
        }
    }
}
```

<span data-ttu-id="ea89e-313">Dann müssen wir unseren benutzerdefinierten ALC mit dem Ereignis `Resolving` des Standard-ALC verbinden, das die ALC-Version des Ereignisses `AssemblyResolve` in Anwendungsdomänen ist.</span><span class="sxs-lookup"><span data-stu-id="ea89e-313">Then we need to hook up our custom ALC to the default ALC's `Resolving` event, which is the ALC version of the `AssemblyResolve` event on Application Domains.</span></span> <span data-ttu-id="ea89e-314">Dieses Ereignis wird ausgelöst, um nach `AlcModule.Engine.dll` zu suchen, wenn `EndProcessing()` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-314">This event is fired to find `AlcModule.Engine.dll` when `EndProcessing()` is called.</span></span>

```csharp
namespace AlcModule.Cmdlets
{
    public class AlcModuleResolveEventHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // Get the path of the dependency directory.
        // In this case we find it relative to the AlcModule.Cmdlets.dll location
        private static readonly string s_dependencyDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        private static readonly AlcModuleAssemblyLoadContext s_dependencyAlc = new AlcModuleAssemblyLoadContext(s_dependencyDirPath);

        public void OnImport()
        {
            // Add the Resolving event handler here
            AssemblyLoadContext.Default.Resolving += ResolveAlcEngine;
        }

        public void OnRemove()
        {
          // Remove the Resolving event handler here
          AssemblyLoadContext.Default.Resolving -= ResolveAlcEngine;
        }

        private static Assembly ResolveAlcEngine(
            AssemblyLoadContext defaultAlc,
            AssemblyName assemblyToResolve)
        {
            // We only want to resolve the Alc.Engine.dll assembly here.
            // Because this will be loaded into the custom ALC,
            // all of *its* dependencies will be resolved
            // by the logic we defined for that ALC's implementation.
            //
            // Note that we are safe in our assumption that the name is enough
            // to distinguish our assembly here,
            // since it's unique to our module.
            // There should be no other AlcModule.Engine.dll on the system.
            if (!assemblyToResolve.Name.Equals("AlcModule.Engine"))
            {
                return null;
            }

            // Allow our ALC to handle the directory discovery concept
            //
            // This is where Alc.Engine.dll is loaded into our custom ALC
            // and then passed through into PowerShell's ALC,
            // becoming the bridge between both
            return s_dependencyAlc.LoadFromAssemblyName(assemblyToResolve);
        }
    }
}
```

<span data-ttu-id="ea89e-315">Schauen Sie sich bei der neuen Implementierung die Reihenfolge der Aufrufe an, die beim Laden und Ausführen von `Test-AlcModule` des Moduls erfolgt:</span><span class="sxs-lookup"><span data-stu-id="ea89e-315">With the new implementation, take a look at the sequence of calls that occurs when the module is loaded and `Test-AlcModule` is run:</span></span>

![Sequenzdiagramm der Aufrufe, die den benutzerdefinierten ALC zum Laden von Abhängigkeiten verwenden](./media/resolving-dependency-conflicts/alc-sequence.png)

<span data-ttu-id="ea89e-317">Die folgenden Punkte sind wichtig:</span><span class="sxs-lookup"><span data-stu-id="ea89e-317">Some points of interest are:</span></span>

- <span data-ttu-id="ea89e-318">Der `IModuleAssemblyInitializer` wird zuerst ausgeführt, wenn das Modul das `Resolving`-Ereignis lädt und festlegt.</span><span class="sxs-lookup"><span data-stu-id="ea89e-318">The `IModuleAssemblyInitializer` is run first when the module loads and sets the `Resolving` event.</span></span>
- <span data-ttu-id="ea89e-319">Die Abhängigkeiten werden erst geladen, nachdem `Test-AlcModule` ausgeführt und seine `EndProcessing()`-Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ea89e-319">We don't load the dependencies until `Test-AlcModule` is run and its `EndProcessing()` method is called.</span></span>
- <span data-ttu-id="ea89e-320">Wenn `EndProcessing()` aufgerufen wird, kann der Standard-ALC `AlcModule.Engine.dll` nicht finden und löst das `Resolving`-Ereignis aus.</span><span class="sxs-lookup"><span data-stu-id="ea89e-320">When `EndProcessing()` is called, the default ALC fails to find `AlcModule.Engine.dll` and fires the `Resolving` event.</span></span>
- <span data-ttu-id="ea89e-321">Unser Ereignishandler verknüpft den benutzerdefinierten ALC mit dem Standard-ALC und lädt nur `AlcModule.Engine.dll`.</span><span class="sxs-lookup"><span data-stu-id="ea89e-321">Our event handler hooks up the custom ALC to the default ALC and loads `AlcModule.Engine.dll` only.</span></span>
- <span data-ttu-id="ea89e-322">Wenn `AlcEngine.Use()` innerhalb von `AlcModule.Engine.dll` aufgerufen wird, greift der benutzerdefinierte ALC erneut ein, um `Shared.Dependency.dll` aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-322">When `AlcEngine.Use()` is called within `AlcModule.Engine.dll`, the custom ALC again kicks in to resolve `Shared.Dependency.dll`.</span></span> <span data-ttu-id="ea89e-323">Insbesondere lädt er stets _unsere_ `Shared.Dependency.dll`, da sie nie mit irgendetwas im Standard-ALC in Konflikt gerät und nur unser Verzeichnis `Dependencies` durchsucht.</span><span class="sxs-lookup"><span data-stu-id="ea89e-323">Specifically, it always loads _our_ `Shared.Dependency.dll` since it never conflicts with anything in the default ALC and only looks in our `Dependencies` directory.</span></span>

<span data-ttu-id="ea89e-324">Beim Zusammenstellen der Implementierung sieht unser neues Quellcodelayout wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ea89e-324">Assembling the implementation, our new source code layout looks like this:</span></span>

```
+ AlcModule.psd1
+ src/
  + AlcModule.Cmdlets/
  | + AlcModule.Cmdlets.csproj
  | + TestAlcModuleCommand.cs
  | + AlcModuleAssemblyLoadContext.cs
  | + AlcModuleInitializer.cs
  |
  + AlcModule.Engine/
  | + AlcModule.Engine.csproj
  | + AlcEngine.cs
```

<span data-ttu-id="ea89e-325">„AlcModule.Cmdlets.csproj“ sieht so aus:</span><span class="sxs-lookup"><span data-stu-id="ea89e-325">AlcModule.Cmdlets.csproj looks like:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <ProjectReference Include="..\AlcModule.Engine\AlcModule.Engine.csproj" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="ea89e-326">„AlcModule.Engine.csproj“ sieht so aus:</span><span class="sxs-lookup"><span data-stu-id="ea89e-326">AlcModule.Engine.csproj looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="ea89e-327">Wenn wir also das Modul erstellen, ist unsere Strategie wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ea89e-327">So, when we build the module, our strategy is:</span></span>

- <span data-ttu-id="ea89e-328">`AlcModule.Engine` erstellen</span><span class="sxs-lookup"><span data-stu-id="ea89e-328">Build `AlcModule.Engine`</span></span>
- <span data-ttu-id="ea89e-329">`AlcModule.Cmdlets` erstellen</span><span class="sxs-lookup"><span data-stu-id="ea89e-329">Build `AlcModule.Cmdlets`</span></span>
- <span data-ttu-id="ea89e-330">Alles aus `AlcModule.Engine` in das Verzeichnis `Dependencies` kopieren und uns merken, was wir kopiert haben</span><span class="sxs-lookup"><span data-stu-id="ea89e-330">Copy everything from `AlcModule.Engine` into the `Dependencies` directory, and remember what we copied</span></span>
- <span data-ttu-id="ea89e-331">Alles aus `AlcModule.Cmdlets`, das nicht in `AlcModule.Engine` enthalten war, in das Basismodulverzeichnis kopieren</span><span class="sxs-lookup"><span data-stu-id="ea89e-331">Copy everything from `AlcModule.Cmdlets` that wasn't in `AlcModule.Engine` into the base module directory</span></span>

<span data-ttu-id="ea89e-332">Da das Modullayout hierbei so entscheidend für die Trennung von Abhängigkeiten ist, hier ein Buildskript, das im Quellstammverzeichnis zu verwenden ist:</span><span class="sxs-lookup"><span data-stu-id="ea89e-332">Since the module layout here is so crucial to dependency separation, here's a build script to use from the source root:</span></span>

```powershell
param(
    # The .NET build configuration
    [ValidateSet('Debug', 'Release')]
    [string]
    $Configuration = 'Debug'
)

# Convenient reusable constants
$mod = "AlcModule"
$netcore = "netcoreapp3.1"
$copyExtensions = @('.dll', '.pdb')

# Source code locations
$src = "$PSScriptRoot/src"
$engineSrc = "$src/$mod.Engine"
$cmdletsSrc = "$src/$mod.Cmdlets"

# Generated output locations
$outDir = "$PSScriptRoot/out/$mod"
$outDeps = "$outDir/Dependencies"

# Build AlcModule.Engine
Push-Location $engineSrc
dotnet publish -c $Configuration
Pop-Location

# Build AlcModule.Cmdlets
Push-Location $cmdletsSrc
dotnet publish -c $Configuration
Pop-Location

# Ensure out directory exists and is clean
Remove-Item -Path $outDir -Recurse -ErrorAction Ignore
New-Item -Path $outDir -ItemType Directory
New-Item -Path $outDeps -ItemType Directory

# Copy manifest
Copy-Item -Path "$PSScriptRoot/$mod.psd1"

# Copy each Engine asset and remember it
$deps = [System.Collections.Generic.Hashtable[string]]::new()
Get-ChildItem -Path "$engineSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { $_.Extension -in $copyExtensions } |
    ForEach-Object { [void]$deps.Add($_.Name); Copy-Item -Path $_.FullName -Destination $outDeps }

# Now copy each Cmdlets asset, not taking any found in Engine
Get-ChildItem -Path "$cmdletsSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { -not $deps.Contains($_.Name) -and $_.Extension -in $copyExtensions } |
    ForEach-Object { Copy-Item -Path $_.FullName -Destination $outDir }
```

<span data-ttu-id="ea89e-333">Schließlich haben wir eine allgemeine Möglichkeit, einen Assemblyladekontext zum Isolieren der Abhängigkeiten unseres Moduls zu verwenden, der über längere Zeit stabil bleibt, sobald weitere Abhängigkeiten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-333">Finally, we have a general way to use an Assembly Load Context to isolate our module's dependencies that remains robust over time as more dependencies are added.</span></span>

<span data-ttu-id="ea89e-334">Ein ausführlicheres Beispiel finden Sie in diesem [GitHub-Repository](https://github.com/rjmholt/ModuleDependencyIsolationExample).</span><span class="sxs-lookup"><span data-stu-id="ea89e-334">For a more detailed example, go to this [GitHub repository](https://github.com/rjmholt/ModuleDependencyIsolationExample).</span></span> <span data-ttu-id="ea89e-335">Dieses Beispiel veranschaulicht, wie ein Modul zur Verwendung eines ALC migriert werden kann, wobei dieses Modul in .NET Framework weiterhin funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ea89e-335">This example demonstrates how to migrate a module to use an ALC, while keeping that module working in .NET Framework.</span></span> <span data-ttu-id="ea89e-336">Außerdem wird gezeigt, wie .NET Standard und PowerShell Standard zur Vereinfachung der Kernimplementierung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ea89e-336">It also show how to use .NET Standard and PowerShell Standard to simplify the core implementation.</span></span>

### <a name="assembly-resolve-handler-for-side-by-side-loading-with-assemblyloadfile"></a><span data-ttu-id="ea89e-337">Auflösungshandler für Assemblys für paralleles Laden mit `Assembly.LoadFile()`</span><span class="sxs-lookup"><span data-stu-id="ea89e-337">Assembly resolve handler for side-by-side loading with `Assembly.LoadFile()`</span></span>

<span data-ttu-id="ea89e-338">Eine andere, vermutlich einfachere Möglichkeit, das parallele Laden von Assemblys zu erreichen, besteht darin, ein `AssemblyResolve` Ereignis mit `Assembly.LoadFile()` zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="ea89e-338">Another, possibly simpler, way to achieve side-by-side assembly loading is to hook up an `AssemblyResolve` event to `Assembly.LoadFile()`.</span></span> <span data-ttu-id="ea89e-339">Die Verwendung von `Assembly.LoadFile()` hat den Vorteil, dass sie die am einfachsten zu implementierende Lösung ist und sowohl mit .NET Core als auch .NET Framework funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ea89e-339">Using `Assembly.LoadFile()` has the advantage of being the simplest solution to implement and works with both .NET Core and .NET Framework.</span></span>

<span data-ttu-id="ea89e-340">Um dies zu veranschaulichen, werfen wir einen Blick auf ein kurzes Beispiel einer Implementierung, die Ideen aus unserem Beispiel der dynamischen Bindungsumleitung und dem obigen Beispiel des Assemblyladekontexts miteinander kombiniert.</span><span class="sxs-lookup"><span data-stu-id="ea89e-340">To show this, let's take a look at a quick example of an implementation that combines ideas from our dynamic binding redirect example, and the Assembly Load Context example above.</span></span>

<span data-ttu-id="ea89e-341">Wir nennen dieses Modul **LoadFileModule**, das den trivialen Befehl `Test-LoadFile [-Path] <path>` aufweist.</span><span class="sxs-lookup"><span data-stu-id="ea89e-341">We'll call this module **LoadFileModule**, which has a trivial command `Test-LoadFile [-Path] <path>`.</span></span> <span data-ttu-id="ea89e-342">Dieses Modul verwendet eine Abhängigkeit von der Assembly `CsvHelper` (Version 15.0.5).</span><span class="sxs-lookup"><span data-stu-id="ea89e-342">This module takes a dependency on the `CsvHelper` assembly (version 15.0.5).</span></span>

<span data-ttu-id="ea89e-343">Wie beim ALC-Modul müssen wird das Modul zuerst in zwei Teile trennen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-343">As with the ALC module, we must first split up the module into two pieces.</span></span>

<span data-ttu-id="ea89e-344">Der erste Teil übernimmt die eigentliche Implementierung, `LoadFileModule.Engine`:</span><span class="sxs-lookup"><span data-stu-id="ea89e-344">The first part does the actual implementation, `LoadFileModule.Engine`:</span></span>

```csharp
using CsvHelper;

namespace LoadFileModule.Engine
{
    public class Runner
    {
        public void Use(string path)
        {
            // Here's where we use the CsvHelper dependency
            using (var reader = new StreamReader(path))
            using (var csvReader = new CsvReader(reader, CultureInfo.InvariantCulture))
            {
                // Imagine we do something useful here...
            }
        }
    }
}
```

<span data-ttu-id="ea89e-345">Der zweite Teil ist, was PowerShell direkt lädt, `LoadFileModule.Cmdlets`.</span><span class="sxs-lookup"><span data-stu-id="ea89e-345">The second part is what PowerShell loads directly, `LoadFileModule.Cmdlets`.</span></span> <span data-ttu-id="ea89e-346">Wir verwenden eine ähnliche Strategie wie das ALC-Modul, bei der Abhängigkeiten in einem separaten Verzeichnis isoliert werden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-346">We use a strategy similar to the ALC module, where we isolate dependencies in a separate directory.</span></span> <span data-ttu-id="ea89e-347">Aber dieses Mal laden wir alle Assemblys mit einem Auflösungsereignis hinein und nicht nur `LoadFileModule.Engine.dll`.</span><span class="sxs-lookup"><span data-stu-id="ea89e-347">But this time, we load all assemblies in with a resolve event rather than just `LoadFileModule.Engine.dll`.</span></span>

```csharp
using LoadFileModule.Engine;

namespace LoadFileModule.Cmdlets
{
    // Actual cmdlet definition
    [Cmdlet(VerbsDiagnostic.Test, "LoadFile")]
    public class TestLoadFileCommand : Cmdlet
    {
        [Parameter(Mandatory = true)]
        public string Path { get; set; }

        protected override void EndProcessing()
        {
            // Here's where we use LoadFileModule.Engine
            new Runner().Use(Path);
        }
    }

    // This class controls our dependency resolution
    public class ModuleContextHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // We catalog our dependencies here to ensure we don't load anything else
        private static IReadOnlyDictionary<string, int> s_dependencies = new Dictionary<string, int>
        {
            { "CsvHelper", 15 },
        };

        // Set up the path to our dependency directory within the module
        private static string s_dependenciesDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        // This makes sure we only try to resolve dependencies when the module is loaded
        private static bool s_engineLoaded = false;

        public void OnImport()
          {
            // Set up our event when the module is loaded
            AppDomain.CurrentDomain.AssemblyResolve += HandleResolveEvent;
        }

        public void OnRemove(PSModuleInfo psModuleInfo)
        {
            // Unset the event when the module is unloaded
            AppDomain.CurrentDomain.AssemblyResolve -= HandleResolveEvent;
        }

        private static Assembly HandleResolveEvent(object sender, ResolveEventArgs args)
        {
            var asmName = new AssemblyName(args.Name);

            // First we want to know if this is the top-level assembly
            if (asmName.Name.Equals("LoadFileModule.Engine"))
            {
                s_engineLoaded = true;
                return Assembly.LoadFile(Path.Combine(s_dependenciesDirPath, "Unrelated.Engine.dll"));
            }

            // Otherwise, if that assembly has been loaded, we must try to resolve its dependencies too
            if (s_engineLoaded
                && s_dependencies.TryGetValue(asmName.Name, out int requiredMajorVersion)
                && asmName.Version.Major == requiredMajorVersion)
            {
                string asmPath = Path.Combine(s_dependenciesDirPath, $"{asmName.Name}.dll");
                return Assembly.LoadFile(asmPath);
            }

            return null;
        }
    }
}
```

<span data-ttu-id="ea89e-348">Abschließend ähnelt das Layout des Moduls auch dem ALC-Modul:</span><span class="sxs-lookup"><span data-stu-id="ea89e-348">Finally, the layout of the module is also similar to the ALC module:</span></span>

```
LoadFileModule/
  + LoadFileModule.Cmdlets.dll
  + LoadFileModule.psd1
  + Dependencies/
  |  + LoadFileModule.Engine.dll
  |  + CsvHelper.dll
```

<span data-ttu-id="ea89e-349">Mit dieser Struktur unterstützt **LoadFileModule** jetzt das gleichzeitige Laden neben anderen Modulen mit einer Abhängigkeit von **CsvHelper**.</span><span class="sxs-lookup"><span data-stu-id="ea89e-349">With this structure in place, **LoadFileModule** now supports being loaded alongside other modules with a dependency on **CsvHelper**.</span></span>

<span data-ttu-id="ea89e-350">Da unser Handler für **alle** gilt `AssemblyResolve`-Ereignisse in der gesamten Anwendungsdomäne gilt, müssen wir hier einige spezifische Entwurfsentscheidungen treffen:</span><span class="sxs-lookup"><span data-stu-id="ea89e-350">Because our handler applies to **all** `AssemblyResolve` events across the Application Domain, we need to make some specific design choices here:</span></span>

- <span data-ttu-id="ea89e-351">Um das Fenster einzugrenzen, in dem unser Ereignis andere Ladevorgänge beeinträchtigen kann, beginnen wir mit der Behandlung des Ladens allgemeiner Abhängigkeiten erst, nachdem `LoadFileModule.Engine.dll` geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="ea89e-351">To narrow the window in which our event may interfere with other loading, we only start handling general dependency loading after `LoadFileModule.Engine.dll` has been loaded.</span></span>
- <span data-ttu-id="ea89e-352">Wir schieben `LoadFileModule.Engine.dll` in das Verzeichnis „Dependencies“, sodass es durch einen Aufruf von `LoadFile()` und nicht von PowerShell geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-352">We push `LoadFileModule.Engine.dll` out into the Dependencies directory, so that it's loaded by a `LoadFile()` call rather than by PowerShell.</span></span> <span data-ttu-id="ea89e-353">Das bedeutet, dass beim Laden seiner eigenen Abhängigkeiten stets ein `AssemblyResolve`-Ereignis ausgelöst wird, auch wenn eine andere `CsvHelper.dll`-Instanz (zum Beispiel) in PowerShell geladen ist.</span><span class="sxs-lookup"><span data-stu-id="ea89e-353">This means its own dependency loads always raise an `AssemblyResolve` event, even if another `CsvHelper.dll` (for example) is loaded in PowerShell.</span></span>
  <span data-ttu-id="ea89e-354">Dies gibt uns die Möglichkeit, die richtige Abhängigkeit zu finden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-354">This gives us the opportunity to find the correct dependency.</span></span>
- <span data-ttu-id="ea89e-355">Da wir nur die spezifischen Abhängigkeiten für unser Modul auflösen müssen, sind wir gezwungen, ein Wörterbuch der Namen und Versionen der Abhängigkeiten in unseren Handler zu programmieren.</span><span class="sxs-lookup"><span data-stu-id="ea89e-355">Since we must only resolve the specific dependencies for our module, we're forced to code a dictionary of dependency names and versions into our handler.</span></span> <span data-ttu-id="ea89e-356">In unserem besonderen Fall wäre es möglich, die `ResolveEventArgs.RequestingAssembly`-Eigenschaft zu verwenden, um herauszufinden, ob `CsvHelper` von unserem Modul angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="ea89e-356">In our particular case, it would be possible to use the `ResolveEventArgs.RequestingAssembly` property to work out whether `CsvHelper` is being requested by our module.</span></span> <span data-ttu-id="ea89e-357">Aber das funktioniert nicht für Abhängigkeiten von Abhängigkeiten, z. B. wenn `CsvHelper` selbst ein `AssemblyResolve`-Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="ea89e-357">But this doesn't work for dependencies of dependencies; for example, if `CsvHelper` itself raised an `AssemblyResolve` event.</span></span> <span data-ttu-id="ea89e-358">Es gibt andere, anspruchsvollere Möglichkeiten, dies zu tun, wie z. B. den Vergleich angeforderter Anforderungen mit den Metadaten von Assemblys im Verzeichnis `Dependencies`.</span><span class="sxs-lookup"><span data-stu-id="ea89e-358">There are other, harder ways to do this, such as comparing requested assemblies to the metadata of assemblies in the `Dependencies` directory.</span></span> <span data-ttu-id="ea89e-359">Aber in diesem Beispiel haben wir diese Überprüfung expliziter gestaltet, um sowohl das Problem hervorzuheben als auch das Beispiel zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-359">But, in this example, we've made this checking more explicit to both highlight the issue and simplify the example.</span></span>

<span data-ttu-id="ea89e-360">Dies ist der Hauptunterschied zwischen der `LoadFile()`- und ALC-Strategie: Das `AssemblyResolve`-Ereignis muss alle Ladevorgänge in der Anwendungsdomäne abdecken, was es viel schwieriger macht zu verhindern, dass sich unsere Abhängigkeitsauflösung mit anderen Modulen verheddert.</span><span class="sxs-lookup"><span data-stu-id="ea89e-360">This is the key difference between the `LoadFile()` strategy and the ALC strategy: the `AssemblyResolve` event must service all loads in the Application Domain, making it much harder to keep our dependency resolution from being tangled with other modules.</span></span> <span data-ttu-id="ea89e-361">Allerdings macht das Fehlen von ALCs in .NET Framework diese Option nachvollziehbar.</span><span class="sxs-lookup"><span data-stu-id="ea89e-361">However, the lack of ALCs in .NET Framework makes this option worth understanding.</span></span>

### <a name="custom-application-domains"></a><span data-ttu-id="ea89e-362">Benutzerdefinierte Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="ea89e-362">Custom Application Domains</span></span>

<span data-ttu-id="ea89e-363">Die letzte und extremste Option zur Isolierung von Assemblys sind benutzerdefinierte Anwendungsdomänen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-363">The final and most extreme option for assembly isolation is to use custom Application Domains.</span></span>
<span data-ttu-id="ea89e-364">Anwendungsdomänen (im Plural verwendet) sind nur in .NET Framework verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ea89e-364">Application Domains (used in the plural) are only available in .NET Framework.</span></span> <span data-ttu-id="ea89e-365">Sie dienen zur Bereitstellung einer prozessinternen Isolierung zwischen Teilen einer .NET-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ea89e-365">They are used to provide in-process isolation between parts of a .NET application.</span></span> <span data-ttu-id="ea89e-366">Eine ihrer Zwecke ist es, Ladevorgänge von Assemblys innerhalb desselben Prozesses voneinander zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="ea89e-366">One of the uses is to isolate assembly loads from each other within the same process.</span></span>

<span data-ttu-id="ea89e-367">Anwendungsdomänen stellen jedoch Serialisierungsgrenzen dar.</span><span class="sxs-lookup"><span data-stu-id="ea89e-367">However, Application Domains are serialization boundaries.</span></span> <span data-ttu-id="ea89e-368">Objekte in einer Anwendungsdomäne können nicht direkt von Objekten in einer anderen Anwendungsdomäne referenziert und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ea89e-368">Objects in one Application Domain can't be referenced and used directly by objects in another Application Domain.</span></span> <span data-ttu-id="ea89e-369">Sie können dieses Problem durch Implementieren von `MarshalByRefObject` umgehen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-369">You can work around this by implementing `MarshalByRefObject`.</span></span> <span data-ttu-id="ea89e-370">Aber wenn Sie die Typen nicht steuern, was bei Abhängigkeiten oft der Fall ist, ist es nicht möglich, hier eine Implementierung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-370">But when you don't control the types, as is often the case with dependencies, it's not possible to force an implementation here.</span></span> <span data-ttu-id="ea89e-371">Die einzige Lösung besteht darin, große Änderungen an der Architektur vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-371">The only solution is to make large architectural changes.</span></span> <span data-ttu-id="ea89e-372">Die Serialisierungsgrenze hat auch schwerwiegende Auswirkungen auf die Leistung.</span><span class="sxs-lookup"><span data-stu-id="ea89e-372">The serialization boundary also has serious performance implications.</span></span>

<span data-ttu-id="ea89e-373">Da Anwendungsdomänen diese gravierende Einschränkung haben, kompliziert zu implementieren sind und nur in .NET Framework funktionieren, verzichten wir an dieser Stelle auf ein Beispiel ihrer Verwendung.</span><span class="sxs-lookup"><span data-stu-id="ea89e-373">Because Application Domains have this serious limitation, are complicated to implement, and only work in .NET Framework, we won't give an example of how you might use them here.</span></span> <span data-ttu-id="ea89e-374">Obwohl sie als eine Möglichkeit erwähnenswert sind, werden sie nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-374">While they're worth mentioning as a possibility, they're not recommended.</span></span>

<span data-ttu-id="ea89e-375">Wenn Sie daran interessiert sind, eine benutzerdefinierte Anwendungsdomäne zu verwenden, könnten die folgenden Links hilfreich sein:</span><span class="sxs-lookup"><span data-stu-id="ea89e-375">If you're interested in trying to use a custom Application Domain, the following links might help:</span></span>

- [<span data-ttu-id="ea89e-376">Konzeptionelle Dokumentation zu Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="ea89e-376">Conceptual documentation on Application Domains</span></span>](/dotnet/framework/app-domains/application-domains)
- [<span data-ttu-id="ea89e-377">Beispiele für die Verwendung von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="ea89e-377">Examples for using Application Domains</span></span>](/dotnet/framework/app-domains/use)

## <a name="solutions-for-dependency-conflicts-that-dont-work-for-powershell"></a><span data-ttu-id="ea89e-378">Lösungen für Abhängigkeitskonflikte, die für PowerShell nicht funktionieren</span><span class="sxs-lookup"><span data-stu-id="ea89e-378">Solutions for dependency conflicts that don't work for PowerShell</span></span>

<span data-ttu-id="ea89e-379">Schließlich gehen wir auf einige Möglichkeiten ein, die sich bei der Recherche von .NET-Abhängigkeitskonflikten in .NET ergeben und vielversprechend aussehen können, aber sich im Allgemeinen nicht für PowerShell eignen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-379">Finally, we'll address some possibilities that come up when researching .NET dependency conflicts in .NET that can look promising, but generally won't work for PowerShell.</span></span>

<span data-ttu-id="ea89e-380">Diesen Lösungen ist gemein, dass sie Änderungen an Bereitstellungskonfigurationen für eine Umgebung darstellen, in der Sie die Anwendung und möglicherweise den gesamten Computer steuern.</span><span class="sxs-lookup"><span data-stu-id="ea89e-380">These solutions have the common theme that they are changes to deployment configurations for an environment where you control the application and possibly the entire machine.</span></span> <span data-ttu-id="ea89e-381">Diese Lösungen orientieren sich an Szenarien wie Webservern und anderen Anwendungen, die in Serverumgebungen bereitgestellt werden, wobei die Umgebung als Host für die Anwendung vorgesehen ist und vom bereitstellenden Benutzer frei konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ea89e-381">These solutions are oriented toward scenarios like web servers and other applications deployed to server environments, where the environment is intended to host the application and is free to be configured by the deploying user.</span></span> <span data-ttu-id="ea89e-382">Sie neigen auch dazu, sehr stark auf .NET Framework ausgerichtet zu sein, was heißt, dass sie nicht mit PowerShell 6 oder höher funktionieren.</span><span class="sxs-lookup"><span data-stu-id="ea89e-382">They also tend to be very much .NET Framework oriented, meaning they do not work with PowerShell 6 or above.</span></span>

<span data-ttu-id="ea89e-383">Wenn Sie wissen, dass Ihr Modul nur in Windows PowerShell 5.1-Umgebungen verwendet wird, über die Sie die vollständige Kontrolle haben, kann es sich bei einigen dieser Vorschläge um Optionen handeln.</span><span class="sxs-lookup"><span data-stu-id="ea89e-383">If you know that your module is only used in Windows PowerShell 5.1 environments that you have total control over, some of these may be options.</span></span> <span data-ttu-id="ea89e-384">Generell sollten **Module den globalen Computerzustand jedoch nicht so verändern**.</span><span class="sxs-lookup"><span data-stu-id="ea89e-384">In general however, **modules should not modify global machine state like this**.</span></span> <span data-ttu-id="ea89e-385">Dadurch können Konfigurationen beschädigt werden, die Probleme in `powershell.exe`, anderen Modulen oder anderen abhängigen Anwendungen verursachen, die Ihr Modul auf unerwartete Weise fehlschlagen lassen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-385">It can break configurations that cause problems in `powershell.exe`, other modules, or other dependent applications that cause your module to fail in unexpected ways.</span></span>

### <a name="static-binding-redirect-with-appconfig-to-force-using-the-same-dependency-version"></a><span data-ttu-id="ea89e-386">Statische Bindungsumleitung mit „app.config“ zum Erzwingen der Verwendung der gleichen Abhängigkeitsversion</span><span class="sxs-lookup"><span data-stu-id="ea89e-386">Static binding redirect with app.config to force using the same dependency version</span></span>

<span data-ttu-id="ea89e-387">.NET Framework-Anwendungen können die Datei `app.config` nutzen, um einige Verhaltensweisen der Anwendung deklarativ zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ea89e-387">.NET Framework applications can take advantage of an `app.config` file to configure some of the application's behaviors declaratively.</span></span> <span data-ttu-id="ea89e-388">Es ist möglich, den Eintrag `app.config` zu schreiben, der die Assemblybindung konfiguriert, um das Laden von Assemblys zu einer bestimmten Version umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="ea89e-388">It's possible to write an `app.config` entry that configures assembly binding to redirect assembly loading to a particular version.</span></span>

<span data-ttu-id="ea89e-389">Für PowerShell gibt es dabei zwei Probleme:</span><span class="sxs-lookup"><span data-stu-id="ea89e-389">Two issues with this for PowerShell are:</span></span>

- <span data-ttu-id="ea89e-390">.NET Core unterstützt `app.config` nicht, daher gilt diese Lösung nur für `powershell.exe`.</span><span class="sxs-lookup"><span data-stu-id="ea89e-390">.NET Core does not support `app.config`, so this solution only applies to `powershell.exe`.</span></span>
- <span data-ttu-id="ea89e-391">`powershell.exe` ist eine gemeinsam genutzte Anwendung, die sich im Verzeichnis `System32` befindet.</span><span class="sxs-lookup"><span data-stu-id="ea89e-391">`powershell.exe` is a shared application that lives in the `System32` directory.</span></span> <span data-ttu-id="ea89e-392">Es ist wahrscheinlich, dass Ihr Modul auf vielen Systemen nicht in der Lage sein wird, ihren Inhalt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ea89e-392">It's likely that your module won't be able to modify its contents on many systems.</span></span> <span data-ttu-id="ea89e-393">Selbst wenn dies möglich ist, könnte die Änderung von `app.config` eine bestehende Konfiguration beschädigen oder das Laden anderer Module beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-393">Even if it can, modifying the `app.config` could break an existing configuration or affect the loading of other modules.</span></span>

### <a name="setting-codebase-with-appconfig"></a><span data-ttu-id="ea89e-394">Festlegen von `codebase` mit „app.config“</span><span class="sxs-lookup"><span data-stu-id="ea89e-394">Setting `codebase` with app.config</span></span>

<span data-ttu-id="ea89e-395">Aus den gleichen Gründen wird der Versuch, die Einstellung `codebase` in `app.config` zu konfigurieren, in PowerShell-Modulen nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="ea89e-395">For the same reasons, trying to configure the `codebase` setting in `app.config` is not going to work in PowerShell modules.</span></span>

### <a name="installing-dependencies-to-the-global-assembly-cache-gac"></a><span data-ttu-id="ea89e-396">Installieren von Abhängigkeiten im globalen Assemblycache (GAC)</span><span class="sxs-lookup"><span data-stu-id="ea89e-396">Installing dependencies to the Global Assembly Cache (GAC)</span></span>

<span data-ttu-id="ea89e-397">Eine weitere Möglichkeit zur Behebung von Abhängigkeitsversionskonflikten in .NET Framework besteht darin, Abhängigkeiten zum GAC zu installieren, damit verschiedene Versionen parallel aus dem GAC geladen werden können.</span><span class="sxs-lookup"><span data-stu-id="ea89e-397">Another way to resolve dependency version conflicts in .NET Framework is to install dependencies to the GAC, so that different versions can be loaded side-by-side from the GAC.</span></span>

<span data-ttu-id="ea89e-398">Für PowerShell-Module sind hierbei die größten Probleme wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ea89e-398">Again, for PowerShell modules, the chief issues here are:</span></span>

- <span data-ttu-id="ea89e-399">Der GAC gilt nur für .NET Framework und ist daher in PowerShell 6 und höher nicht hilfreich.</span><span class="sxs-lookup"><span data-stu-id="ea89e-399">The GAC only applies to .NET Framework, so this does not help in PowerShell 6 and above.</span></span>
- <span data-ttu-id="ea89e-400">Die Installation von Assemblys in den GAC stellt eine Änderung des globalen Computerzustands dar und kann zu unerwünschten Nebeneffekten in anderen Anwendungen oder bei anderen Modulen führen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-400">Installing assemblies to the GAC is a modification of global machine state and may cause side-effects in other applications or to other modules.</span></span> <span data-ttu-id="ea89e-401">Es kann außerdem schwierig sein, dies korrekt durchzuführen, selbst wenn Ihr Modul über die erforderlichen Zugriffsrechte verfügt.</span><span class="sxs-lookup"><span data-stu-id="ea89e-401">It may also be difficult to do correctly, even when your module has the required access privileges.</span></span> <span data-ttu-id="ea89e-402">Ein Fehler könnte schwerwiegende, computerweite Probleme in anderen .NET-Anwendungen verursachen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-402">Getting it wrong could cause serious, machine-wide issues in other .NET applications.</span></span>

## <a name="further-reading"></a><span data-ttu-id="ea89e-403">Weiterführende Themen</span><span class="sxs-lookup"><span data-stu-id="ea89e-403">Further reading</span></span>

<span data-ttu-id="ea89e-404">Es gibt noch viel mehr Lesestoff zu Abhängigkeitskonflikten bei .NET-Assemblyversionen.</span><span class="sxs-lookup"><span data-stu-id="ea89e-404">There's plenty more to read on .NET assembly version dependency conflicts.</span></span> <span data-ttu-id="ea89e-405">Es folgen einige hilfreiche Ausgangspunkte:</span><span class="sxs-lookup"><span data-stu-id="ea89e-405">Here are some nice jumping off points:</span></span>

- [<span data-ttu-id="ea89e-406">.NET: Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="ea89e-406">.NET: Assemblies in .NET</span></span>](/dotnet/standard/assembly/)
- [<span data-ttu-id="ea89e-407">.NET Core: Ladealgorithmus für verwaltete Assemblys</span><span class="sxs-lookup"><span data-stu-id="ea89e-407">.NET Core: The managed assembly loading algorithm</span></span>](/dotnet/core/dependency-loading/loading-managed)
- [<span data-ttu-id="ea89e-408">.NET Core: Grundlegendes zu System.Runtime.Loader.AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="ea89e-408">.NET Core: Understanding System.Runtime.Loader.AssemblyLoadContext</span></span>](/dotnet/core/dependency-loading/understanding-assemblyloadcontext)
- [<span data-ttu-id="ea89e-409">.NET Core: Erörterung von Lösungen zum parallelen Laden von Assemblys</span><span class="sxs-lookup"><span data-stu-id="ea89e-409">.NET Core: Discussion about side-by-side assembly loading solutions</span></span>](https://github.com/dotnet/runtime/issues/13471)
- [<span data-ttu-id="ea89e-410">.NET Framework: Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="ea89e-410">.NET Framework: Redirecting assembly versions</span></span>](/dotnet/framework/configure-apps/redirect-assembly-versions)
- [<span data-ttu-id="ea89e-411">.NET Framework: Bewährte Methoden für das Laden von Assemblys</span><span class="sxs-lookup"><span data-stu-id="ea89e-411">.NET Framework: Best practices for assembly loading</span></span>](/dotnet/framework/deployment/best-practices-for-assembly-loading)
- [<span data-ttu-id="ea89e-412">.NET Framework: So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="ea89e-412">.NET Framework: How the runtime locates assemblies</span></span>](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)
- [<span data-ttu-id="ea89e-413">.NET Framework: Auflösen von Assemblyladevorgängen</span><span class="sxs-lookup"><span data-stu-id="ea89e-413">.NET Framework: Resolve assembly loads</span></span>](/dotnet/standard/assembly/resolve-loads)
- [<span data-ttu-id="ea89e-414">StackOverflow: Assembly Binding redirect: How and Why?</span><span class="sxs-lookup"><span data-stu-id="ea89e-414">StackOverflow: Assembly binding redirect, how and why?</span></span>](https://stackoverflow.com/questions/43365736/assembly-binding-redirect-how-and-why)
- [<span data-ttu-id="ea89e-415">PowerShell: Erörterung der Implementierung von AssemblyLoadContexts</span><span class="sxs-lookup"><span data-stu-id="ea89e-415">PowerShell: Discussion about implementing AssemblyLoadContexts</span></span>](https://github.com/PowerShell/PowerShell/issues/11571)
- [<span data-ttu-id="ea89e-416">PowerShell: `Assembly.LoadFile()` wird nicht in den standardmäßigen AssemblyLoadContext geladen</span><span class="sxs-lookup"><span data-stu-id="ea89e-416">PowerShell: `Assembly.LoadFile()` doesn't load into default AssemblyLoadContext</span></span>](https://github.com/PowerShell/PowerShell/issues/12052)
- [<span data-ttu-id="ea89e-417">Rick Strahl: When does a .NET assembly dependency get loaded?</span><span class="sxs-lookup"><span data-stu-id="ea89e-417">Rick Strahl: When does a .NET assembly dependency get loaded?</span></span>](https://weblog.west-wind.com/posts/2012/Nov/03/Back-to-Basics-When-does-a-NET-Assembly-Dependency-get-loaded)
- [<span data-ttu-id="ea89e-418">Jon Skeet: Summary of versioning in .NET</span><span class="sxs-lookup"><span data-stu-id="ea89e-418">Jon Skeet: Summary of versioning in .NET</span></span>](https://codeblog.jonskeet.uk/2019/06/30/versioning-limitations-in-net/)
- [<span data-ttu-id="ea89e-419">Nate McMaster: Deep dive into .NET Core primitives</span><span class="sxs-lookup"><span data-stu-id="ea89e-419">Nate McMaster: Deep dive into .NET Core primitives</span></span>](https://natemcmaster.com/blog/2017/12/21/netcore-primitives/)
