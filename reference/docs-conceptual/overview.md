---
ms.date: 05/22/2020
keywords: powershell,cmdlet
title: Was ist PowerShell?
description: Dieser Artikel stellt eine Einführung in die PowerShell-Skriptumgebung und ihre Features dar.
ms.openlocfilehash: 91fc580af9a3adf43a24c40b4aaf3f1843882705
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500775"
---
# <a name="what-is-powershell"></a><span data-ttu-id="27919-104">Was ist PowerShell?</span><span class="sxs-lookup"><span data-stu-id="27919-104">What is PowerShell?</span></span>

<span data-ttu-id="27919-105">PowerShell ist ein Framework zur plattformübergreifenden Aufgabenautomatisierung und Konfigurationsverwaltung und besteht aus einer Befehlszeilenshell und Skriptsprache.</span><span class="sxs-lookup"><span data-stu-id="27919-105">PowerShell is a cross-platform task automation and configuration management framework, consisting of a command-line shell and scripting language.</span></span> <span data-ttu-id="27919-106">Im Gegensatz zu den meisten Shells, bei denen Text akzeptiert und zurückgegeben wird, basiert PowerShell auf der .NET Common Language Runtime (CLR) und akzeptiert und gibt .NET-Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="27919-106">Unlike most shells, which accept and return text, PowerShell is built on top of the .NET Common Language Runtime (CLR), and accepts and returns .NET objects.</span></span> <span data-ttu-id="27919-107">Diese grundlegende Änderung bringt völlig neue Tools und Methoden für die Automatisierung mit sich.</span><span class="sxs-lookup"><span data-stu-id="27919-107">This fundamental change brings entirely new tools and methods for automation.</span></span>

<!-- removing images until we can get replacements
:::row:::
   :::column span="":::
      Windows
      [![PowerShell on Windows](media/overview/windows-desktop-660.gif)](media/overview/windows-desktop.gif#lightbox)
      [Install on Windows](install/installing-powershell-core-on-windows.md)
   :::column-end:::
   :::column span="":::
      Linux
      [![PowerShell on Linux](media/overview/linux-desktop-660.gif)](media/overview/linux-desktop.gif#lightbox)
      [Install on Linux](install/installing-powershell-core-on-linux.md)
   :::column-end:::
   :::column span="":::
      macOS
      [![PowerShell on macOS](media/overview/macos-desktop-660.gif)](media/overview/macos-desktop.gif#lightbox)
      [Install on macOS](install/installing-powershell-core-on-macos.md)
   :::column-end:::
:::row-end:::
-->

## <a name="output-is-object-based"></a><span data-ttu-id="27919-108">Die Ausgabe ist objektbasiert</span><span class="sxs-lookup"><span data-stu-id="27919-108">Output is object-based</span></span>

<span data-ttu-id="27919-109">Im Gegensatz zu herkömmlichen Befehlszeilenschnittstellen sind PowerShell-Cmdlets für den Umgang mit Objekten entworfen.</span><span class="sxs-lookup"><span data-stu-id="27919-109">Unlike traditional command-line interfaces, PowerShell cmdlets are designed to deal with objects.</span></span>
<span data-ttu-id="27919-110">Ein Objekt setzt sich aus strukturierten Informationen zusammen und ist mehr als nur die Zeichenfolge, die auf dem Bildschirm erscheint.</span><span class="sxs-lookup"><span data-stu-id="27919-110">An object is structured information that is more than just the string of characters appearing on the screen.</span></span> <span data-ttu-id="27919-111">Die Befehlsausgabe umfasst immer zusätzliche Informationen, die Sie bei Bedarf nutzen können.</span><span class="sxs-lookup"><span data-stu-id="27919-111">Command output always carries extra information that you can use if you need it.</span></span>

<span data-ttu-id="27919-112">Wenn Sie in schon mal ein Textverarbeitungsprogramm zum Verarbeiten von Daten verwendet haben, werden Sie das abweichende Verhalten der Daten in PowerShell bemerken.</span><span class="sxs-lookup"><span data-stu-id="27919-112">If you've used text-processing tools to process data in the past, you'll find that they behave differently when used in PowerShell.</span></span> <span data-ttu-id="27919-113">In den meisten Fällen benötigen Sie kein Textverarbeitungsprogramm, um bestimmte Informationen zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="27919-113">In most cases, you don't need text-processing tools to extract specific information.</span></span> <span data-ttu-id="27919-114">Sie greifen mit der standardmäßigen PowerShell-Objektsyntax direkt auf Teile der Daten zu.</span><span class="sxs-lookup"><span data-stu-id="27919-114">You directly access portions of the data using standard PowerShell object syntax.</span></span>

## <a name="the-command-family-is-extensible"></a><span data-ttu-id="27919-115">Die Befehlsfamilie ist erweiterbar</span><span class="sxs-lookup"><span data-stu-id="27919-115">The command family is extensible</span></span>

<span data-ttu-id="27919-116">Schnittstellen wie `cmd.exe` bieten keine Möglichkeit zur direkten Erweiterung des integrierten Befehlssatzes.</span><span class="sxs-lookup"><span data-stu-id="27919-116">Interfaces such as `cmd.exe` don't provide a way for you to directly extend the built-in command set.</span></span> <span data-ttu-id="27919-117">Sie können externe Befehlszeilentools erstellen, die in `cmd.exe` ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="27919-117">You can create external command-line tools that run in `cmd.exe`.</span></span> <span data-ttu-id="27919-118">Aber diese externen Tools umfassen keine Dienste wie z.B. eine integrierte Hilfe.</span><span class="sxs-lookup"><span data-stu-id="27919-118">But these external tools don't have services, such as Help integration.</span></span> <span data-ttu-id="27919-119">`cmd.exe` weiß nicht automatisch, dass es sich bei diesen externen Tools um gültige Befehle handelt.</span><span class="sxs-lookup"><span data-stu-id="27919-119">`cmd.exe` doesn't automatically know that these external tools are valid commands.</span></span>

<span data-ttu-id="27919-120">Die Befehle in PowerShell werden als _Cmdlets_ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="27919-120">The commands in PowerShell are known as _cmdlets_ .</span></span> <span data-ttu-id="27919-121">Sie können jedes Cmdlet einzeln verwenden, aber deren Leistungsfähigkeit wird freigesetzt, wenn Sie diese kombinieren, um komplexe Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="27919-121">You can use each cmdlet separately, but their power is realized when you combine them to perform complex tasks.</span></span> <span data-ttu-id="27919-122">Ähnlich wie viele Shells ermöglicht PowerShell Ihnen Zugriff auf das Dateisystem auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="27919-122">Like many shells, PowerShell gives you access to the file system on the computer.</span></span> <span data-ttu-id="27919-123">Mit PowerShell- _Anbietern_ haben Sie die Möglichkeit, auf andere Datenspeicher, etwa die Registrierung und den Zertifikatspeicher, so einfach zuzugreifen wie auf das Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="27919-123">PowerShell _providers_ enable you to access other data stores, such as the registry and the certificate stores, as easily as you access the file system.</span></span>

<span data-ttu-id="27919-124">Mithilfe von kompiliertem Code oder Skripts können Sie eigene Cmdlets und Funktionsmodule erstellen.</span><span class="sxs-lookup"><span data-stu-id="27919-124">You can create your own cmdlet and function modules using compiled code or scripts.</span></span> <span data-ttu-id="27919-125">Mit Modulen können der Shell Cmdlets und Anbieter hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="27919-125">Modules can add cmdlets and providers to the shell.</span></span> <span data-ttu-id="27919-126">PowerShell bietet außerdem Unterstützung für Skripts, analog zu UNIX-Shellskripts und `cmd.exe`-Batchdateien.</span><span class="sxs-lookup"><span data-stu-id="27919-126">PowerShell also supports scripts that are analogous to UNIX shell scripts and `cmd.exe` batch files.</span></span>

## <a name="support-for-command-aliases"></a><span data-ttu-id="27919-127">Unterstützung für Befehlsaliase</span><span class="sxs-lookup"><span data-stu-id="27919-127">Support for command aliases</span></span>

<span data-ttu-id="27919-128">PowerShell unterstützt Aliase, um mit alternativen Namen auf Befehle zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="27919-128">PowerShell supports aliases to refer to commands by alternate names.</span></span> <span data-ttu-id="27919-129">Durch Aliase können Benutzer mit Erfahrung in anderen Shell-Umgebungen gängige Befehlsnamen, die sie bereits kennen, für ähnliche Vorgänge in PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="27919-129">Aliasing allows users with experience in other shells to use common command names that they already know for similar operations in PowerShell.</span></span>

<span data-ttu-id="27919-130">Bei der Aliasverwendung wird einem Befehl ein neuer Name zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="27919-130">Aliasing associates a new name with another command.</span></span> <span data-ttu-id="27919-131">Beispielsweise umfasst PowerShell eine interne Funktion namens `Clear-Host`, mit der das Ausgabefenster gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="27919-131">For example, PowerShell has an internal function named `Clear-Host` that clears the output window.</span></span> <span data-ttu-id="27919-132">Sie können an einer Eingabeaufforderung entweder `cls` oder den Alias `clear` eingeben.</span><span class="sxs-lookup"><span data-stu-id="27919-132">You can type either the `cls` or `clear` alias at a command prompt.</span></span> <span data-ttu-id="27919-133">PowerShell interpretiert diese Aliase und führt die Funktion `Clear-Host` aus.</span><span class="sxs-lookup"><span data-stu-id="27919-133">PowerShell interprets these aliases and runs the `Clear-Host` function.</span></span>

<span data-ttu-id="27919-134">Dieses Feature unterstützt Benutzer beim Erlernen von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27919-134">This feature helps users to learn PowerShell.</span></span> <span data-ttu-id="27919-135">Zunächst beherrschen die meisten `cmd.exe`- und Unix-Benutzer ein großes Repertoire an Befehlen, deren Namen sie bereits kennen.</span><span class="sxs-lookup"><span data-stu-id="27919-135">First, most `cmd.exe` and Unix users have a large repertoire of commands that users already know by name.</span></span> <span data-ttu-id="27919-136">Die PowerShell-Äquivalente führen möglicherweise nicht zu identischen Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="27919-136">The PowerShell equivalents may not produce identical results.</span></span> <span data-ttu-id="27919-137">Dennoch sind die Ergebnisse ähnlich genug, um Benutzern das Arbeiten ohne Kenntnis der PowerShell-Befehlsnamen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="27919-137">However, the results are close enough that users can do work without knowing the PowerShell command name.</span></span> <span data-ttu-id="27919-138">Das „Muskelgedächtnis“ ist eine weitere Quelle für Frustrationen beim Erlernen einer neuen Befehlsshell.</span><span class="sxs-lookup"><span data-stu-id="27919-138">"Muscle memory" is another major source of frustration when learning a new command shell.</span></span> <span data-ttu-id="27919-139">Wenn Sie seit Jahren `cmd.exe` verwenden, geben Sie möglicherweise reflexartig den Befehl `cls` ein, um den Bildschirm zu löschen.</span><span class="sxs-lookup"><span data-stu-id="27919-139">If you have used `cmd.exe` for years, you might reflexively type the `cls` command to clear the screen.</span></span> <span data-ttu-id="27919-140">Ohne den Alias für `Clear-Host` erhalten Sie eine Fehlermeldung und wissen nicht, wie Sie zum Löschen der Ausgabe vorgehen müssen.</span><span class="sxs-lookup"><span data-stu-id="27919-140">Without the alias for `Clear-Host`, you receive an error message and won't know what to do to clear the output.</span></span>

## <a name="powershell-handles-console-input-and-display"></a><span data-ttu-id="27919-141">PowerShell verarbeitet Konsoleneingabe und Anzeige</span><span class="sxs-lookup"><span data-stu-id="27919-141">PowerShell handles console input and display</span></span>

<span data-ttu-id="27919-142">Wenn Sie einen Befehl eingeben, verarbeitet PowerShell die Befehlszeileneingabe immer sofort.</span><span class="sxs-lookup"><span data-stu-id="27919-142">When you type a command, PowerShell always processes the command-line input directly.</span></span> <span data-ttu-id="27919-143">PowerShell formatiert darüber hinaus die Ausgabe, die auf dem Bildschirm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="27919-143">PowerShell also formats the output that you see on the screen.</span></span> <span data-ttu-id="27919-144">Dieser Unterschied ist wesentlich, weil dadurch die Arbeit für jedes Cmdlet verringert wird.</span><span class="sxs-lookup"><span data-stu-id="27919-144">This difference is significant because it reduces the work required of each cmdlet.</span></span> <span data-ttu-id="27919-145">Es wird sichergestellt, dass Sie Aufgaben mit beliebigen Cmdlets immer gleich ausführen können.</span><span class="sxs-lookup"><span data-stu-id="27919-145">It ensures that you can always do things the same way with any cmdlet.</span></span> <span data-ttu-id="27919-146">Cmdlet-Entwickler müssen keinen Code schreiben, mit dem die Befehlszeilenargumente analysiert oder die Ausgabe formatiert wird.</span><span class="sxs-lookup"><span data-stu-id="27919-146">Cmdlet developers don't need to write code to parse the command-line arguments or format the output.</span></span>

<span data-ttu-id="27919-147">Herkömmliche Befehlszeilentools haben eigene Schemas zum Anfordern und Anzeigen von Hilfe.</span><span class="sxs-lookup"><span data-stu-id="27919-147">Traditional command-line tools have their own schemes for requesting and displaying Help.</span></span> <span data-ttu-id="27919-148">Einige Befehlszeilentools verwenden `/?` zum Aufrufen der Hilfe, während andere `-?`, `/H` oder `//` verwenden.</span><span class="sxs-lookup"><span data-stu-id="27919-148">Some command-line tools use `/?` to trigger the Help display; others use `-?`, `/H`, or even `//`.</span></span> <span data-ttu-id="27919-149">Bei einigen wird Hilfe in einem Fenster auf der grafischen Benutzeroberfläche und nicht in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27919-149">Some will display Help in a GUI window, rather than in the console display.</span></span> <span data-ttu-id="27919-150">Wenn Sie den falschen Parameter verwenden, ignoriert das Tool möglicherweise Ihre Eingabe und beginnt damit, automatisch einen Task auszuführen.</span><span class="sxs-lookup"><span data-stu-id="27919-150">If you use the wrong parameter, the tool might ignore what you typed and begin executing a task automatically.</span></span>
<span data-ttu-id="27919-151">Da PowerShell die Befehlszeile automatisch analysiert und verarbeitet, bedeutet der Parameter `-?` immer „Hilfe für diesen Befehl anzeigen“.</span><span class="sxs-lookup"><span data-stu-id="27919-151">Since PowerShell automatically parses and processes the command line, the `-?` parameter always means "show me Help for this command".</span></span>

> [!NOTE]
> <span data-ttu-id="27919-152">Wenn Sie eine grafische Anwendung in PowerShell ausführen, wird das Fenster für die Anwendung geöffnet.</span><span class="sxs-lookup"><span data-stu-id="27919-152">If you run a graphic application in PowerShell, the window for the application opens.</span></span>
> <span data-ttu-id="27919-153">PowerShell greift nur beim Verarbeiten der angegebenen Befehlszeileneingabe oder zur Ausgabe der Anwendungsergebnisse im Konsolenfenster ein.</span><span class="sxs-lookup"><span data-stu-id="27919-153">PowerShell intervenes only when processing the command-line input you supply or the application output returned to the console window.</span></span> <span data-ttu-id="27919-154">PowerShell hat keinen Einfluss darauf, wie die Anwendung intern arbeitet.</span><span class="sxs-lookup"><span data-stu-id="27919-154">It does not affect how the application works internally.</span></span>

## <a name="powershell-has-a-pipeline"></a><span data-ttu-id="27919-155">Die PowerShell-Pipeline</span><span class="sxs-lookup"><span data-stu-id="27919-155">PowerShell has a pipeline</span></span>

<span data-ttu-id="27919-156">Pipelines sind wohl das wertvollste Konzept, das Befehlszeilenschnittstellen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="27919-156">Pipelines are arguably the most valuable concept used in command-line interfaces.</span></span> <span data-ttu-id="27919-157">Bei richtigem Einsatz verringern Pipelines den Aufwand durch die Verwendung von komplexen Befehlen und erleichtern es, den Ablauf zu sehen.</span><span class="sxs-lookup"><span data-stu-id="27919-157">When used properly, pipelines reduce the effort of using complex commands and make it easier to see the flow of work.</span></span> <span data-ttu-id="27919-158">Jeder Befehl in einer Pipeline gibt seine Ausgabe Element für Element an den nächsten Befehl weiter.</span><span class="sxs-lookup"><span data-stu-id="27919-158">Each command in a pipeline passes its output, item by item, to the next command.</span></span> <span data-ttu-id="27919-159">Befehle müssen jeweils nur ein Element zurzeit verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="27919-159">Commands don't have to handle more than one item at a time.</span></span> <span data-ttu-id="27919-160">Das Ergebnis ist eine verringerte Ressourcennutzung und die Möglichkeit, die Ausgabe unmittelbar zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="27919-160">The result is reduced resource consumption and the ability to get output immediately.</span></span>

<span data-ttu-id="27919-161">Die Notation für Pipelines ist der Notation in anderen Shells ähnlich.</span><span class="sxs-lookup"><span data-stu-id="27919-161">The notation used for pipelines is similar to the notation used in other shells.</span></span> <span data-ttu-id="27919-162">Auf den ersten Blick ist es möglicherweise nicht offensichtlich, wie sich Pipelines in PowerShell unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="27919-162">At first glance, it may not be apparent how pipelines are different in PowerShell.</span></span> <span data-ttu-id="27919-163">Obwohl Text auf dem Bildschirm angezeigt wird, leitet PowerShell Objekte und keinen Text zwischen Befehlen weiter.</span><span class="sxs-lookup"><span data-stu-id="27919-163">Although you see text on the screen, PowerShell pipes objects, not text, between commands.</span></span>

<span data-ttu-id="27919-164">Wenn Sie beispielsweise das Cmdlet `Out-Host` zum Erzwingen einer seitenweisen Anzeige der Ausgabe eines anderen Befehls verwenden, sieht die Ausgabe wie der normale auf dem Bildschirm gezeigte Text aus, der in Seiten unterteilt ist:</span><span class="sxs-lookup"><span data-stu-id="27919-164">For example, if you use the `Out-Host` cmdlet to force a page-by-page display of output from another command, the output looks just like the normal text displayed on the screen, broken up into pages:</span></span>

```powershell
Get-ChildItem | Out-Host -Paging
```

```Output
    Directory: /mnt/c/Git/PS-Docs/PowerShell-Docs/reference/7.0/Microsoft.PowerShell.Core

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----          05/22/2020    08:30                About
-----          05/20/2020    14:36           9044 Add-History.md
-----          05/20/2020    14:36          12227 Clear-History.md
-----          05/20/2020    14:36           3566 Clear-Host.md
-----          05/20/2020    14:36          29087 Connect-PSSession.md
-----          05/20/2020    14:36           5705 Debug-Job.md
-----          05/20/2020    14:36           3515 Disable-ExperimentalFeature.md
-----          05/20/2020    14:36          25531 Disable-PSRemoting.md
-----          05/20/2020    14:36           7852 Disable-PSSessionConfiguration.md
-----          05/20/2020    14:36          25355 Disconnect-PSSession.md
-----          05/20/2020    14:36           3491 Enable-ExperimentalFeature.md
-----          05/20/2020    14:36          13310 Enable-PSRemoting.md
-----          05/20/2020    14:36           8401 Enable-PSSessionConfiguration.md
-----          05/20/2020    14:36           9531 Enter-PSHostProcess.md
...
<SPACE> next page; <CR> next line; Q quit
```

<span data-ttu-id="27919-165">Durch die Einteilung in Seiten wird auch die CPU-Auslastung reduziert, da die Verarbeitung an das Cmdlet `Out-Host` übertragen wird, wenn eine vollständige Seite für die Anzeige bereit ist.</span><span class="sxs-lookup"><span data-stu-id="27919-165">Paging also reduces CPU utilization because processing transfers to the `Out-Host` cmdlet when it has a complete page ready to display.</span></span> <span data-ttu-id="27919-166">Die Cmdlets, die sich in der Pipeline davor befinden, unterbrechen die Ausführung, bis die nächste Seite der Ausgabe verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="27919-166">The cmdlets that precede it in the pipeline pause execution until the next page of output is available.</span></span>

### <a name="objects-in-the-pipeline"></a><span data-ttu-id="27919-167">Objekte in der Pipeline</span><span class="sxs-lookup"><span data-stu-id="27919-167">Objects in the pipeline</span></span>

<span data-ttu-id="27919-168">Wenn Sie ein Cmdlet in PowerShell ausführen, sehen Sie eine Textausgabe, da es erforderlich ist, Objekte in einem Konsolenfenster als Text darzustellen.</span><span class="sxs-lookup"><span data-stu-id="27919-168">When you run a cmdlet in PowerShell, you see text output because it is necessary to represent objects as text in a console window.</span></span> <span data-ttu-id="27919-169">Die Textausgabe enthält möglicherweise nicht alle Eigenschaften des Objekts, das ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="27919-169">The text output may not display all of the properties of the object being output.</span></span>

<span data-ttu-id="27919-170">Betrachten Sie beispielsweise das Cmdlet `Get-Location`.</span><span class="sxs-lookup"><span data-stu-id="27919-170">For example, consider the `Get-Location` cmdlet.</span></span> <span data-ttu-id="27919-171">Die Textausgabe ist eine Zusammenfassung der Informationen, keine vollständige Darstellung des Objekts, das von `Get-Location` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="27919-171">The text output is a summary of information, not a complete representation of the object returned by `Get-Location`.</span></span> <span data-ttu-id="27919-172">Die Überschrift in der Ausgabe wird durch den Prozess hinzugefügt, der die Daten für die Anzeige auf dem Bildschirm formatiert.</span><span class="sxs-lookup"><span data-stu-id="27919-172">The heading in the output is added by the process that formats the data for onscreen display.</span></span>

```powershell
Get-Location
```

```Output
Path
----
C:\
```

<span data-ttu-id="27919-173">Wenn Sie die Ausgabe an das Cmdlet `Get-Member` weiterleiten, werden Informationen über das Objekt angezeigt, das von `Get-Location` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="27919-173">Piping the output to the `Get-Member` cmdlet displays information about the object returned by `Get-Location`.</span></span>

```powershell
Get-Location | Get-Member
```

```Output
   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Equals       Method     bool Equals(System.Object obj)
GetHashCode  Method     int GetHashCode()
GetType      Method     type GetType()
ToString     Method     string ToString()
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   string Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {get;}
ProviderPath Property   string ProviderPath {get;}
```

<span data-ttu-id="27919-174">`Get-Location` gibt ein **PathInfo** -Objekt zurück, das den aktuellen Pfad und andere Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="27919-174">`Get-Location` returns a **PathInfo** object that contains the current path and other information.</span></span>

## <a name="built-in-help-system"></a><span data-ttu-id="27919-175">Integriertes Hilfesystem</span><span class="sxs-lookup"><span data-stu-id="27919-175">Built-in help system</span></span>

<span data-ttu-id="27919-176">Ähnlich wie bei `man`-Seiten, umfasst PowerShell ausführliche Hilfeartikel, in denen die Konzepte von PowerShell und die Befehlssyntax erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="27919-176">Similar to Unix `man` pages, PowerShell includes detailed help articles that explain PowerShell concepts and command syntax.</span></span> <span data-ttu-id="27919-177">Verwenden Sie das Cmdlet [Get-Help][], um diese Artikel über die Eingabeaufforderung anzuzeigen. Sie können aber auch die zuletzt aktualisierten Versionen dieser Artikel in der PowerShell-Dokumentation online anzeigen.</span><span class="sxs-lookup"><span data-stu-id="27919-177">Use the [Get-Help][] cmdlet to display these articles at the command prompt or view the most recently updated versions of these articles in the PowerShell documentation online.</span></span>

## <a name="next-steps"></a><span data-ttu-id="27919-178">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="27919-178">Next steps</span></span>

<span data-ttu-id="27919-179">Weitere Informationen zu PowerShell erhalten Sie im Abschnitt **Erlernen von PowerShell** auf dieser Website.</span><span class="sxs-lookup"><span data-stu-id="27919-179">To learn more about PowerShell, see the **Learning PowerShell** section of this site.</span></span>

<!-- link references -->

[Get-Help]: /powershell/module/microsoft.powershell.core/Get-Help
