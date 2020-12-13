---
ms.date: 09/13/2016
ms.topic: reference
title: Hinzufügen von Aliasen, Platzhaltererweiterung und Hilfe zu Cmdlet-Parametern
description: Hinzufügen von Aliasen, Platzhaltererweiterung und Hilfe zu Cmdlet-Parametern
ms.openlocfilehash: f0f07796370b4613b1ca0ad17b16c6598bfa438d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660651"
---
# <a name="adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters"></a><span data-ttu-id="76b0f-103">Hinzufügen von Aliasen, Platzhaltererweiterung und Hilfe zu Cmdlet-Parametern</span><span class="sxs-lookup"><span data-stu-id="76b0f-103">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>

<span data-ttu-id="76b0f-104">In diesem Abschnitt wird beschrieben, wie Aliase, Platzhalter Erweiterung und Hilfe Meldungen den Parametern des Stop-Proc-Cmdlets hinzugefügt werden (siehe [Erstellen eines Cmdlets, das das System ändert](./creating-a-cmdlet-that-modifies-the-system.md)).</span><span class="sxs-lookup"><span data-stu-id="76b0f-104">This section describes how to add aliases, wildcard expansion, and Help messages to the parameters of the Stop-Proc cmdlet (described in [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md)).</span></span>

<span data-ttu-id="76b0f-105">Dieses Cmdlet Stop-Proc versucht, Prozesse zu unterbinden, die mithilfe des Get-Proc-Cmdlets abgerufen werden (siehe [Erstellen des ersten Cmdlets](./creating-a-cmdlet-without-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="76b0f-105">This Stop-Proc cmdlet attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="76b0f-106">Definieren des Cmdlets</span><span class="sxs-lookup"><span data-stu-id="76b0f-106">Defining the Cmdlet</span></span>

<span data-ttu-id="76b0f-107">Der erste Schritt bei der Cmdlet-Erstellung ist die Benennung des Cmdlets und das Deklarieren der .NET-Klasse, die das Cmdlet implementiert.</span><span class="sxs-lookup"><span data-stu-id="76b0f-107">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="76b0f-108">Da Sie ein Cmdlet schreiben, um das System zu ändern, sollte es entsprechend benannt werden.</span><span class="sxs-lookup"><span data-stu-id="76b0f-108">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="76b0f-109">Da dieses Cmdlet System Prozesse stoppt, wird das Verb "Stopp", das von der [System. Management. Automation. verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) -Klasse definiert wird, mit dem Substantiv "proc" verwendet, um den Prozess anzugeben.</span><span class="sxs-lookup"><span data-stu-id="76b0f-109">Because this cmdlet stops system processes, it uses the verb "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate process.</span></span> <span data-ttu-id="76b0f-110">Weitere Informationen zu genehmigten Cmdlet-Verben finden Sie unter [Cmdlet-Verb Namen](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="76b0f-110">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="76b0f-111">Der folgende Code stellt die Klassendefinition für dieses Stop-Proc-Cmdlet dar.</span><span class="sxs-lookup"><span data-stu-id="76b0f-111">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="76b0f-112">Definieren von Parametern für die System Änderung</span><span class="sxs-lookup"><span data-stu-id="76b0f-112">Defining Parameters for System Modification</span></span>

<span data-ttu-id="76b0f-113">Ihr Cmdlet muss Parameter definieren, die Systemänderungen und Benutzer Feedback unterstützen.</span><span class="sxs-lookup"><span data-stu-id="76b0f-113">Your cmdlet needs to define parameters that support system modifications and user feedback.</span></span> <span data-ttu-id="76b0f-114">Mit dem-Cmdlet sollte ein `Name` Parameter oder eine Entsprechung definiert werden, damit das Cmdlet das System mit einer bestimmten Art von Bezeichner ändern kann.</span><span class="sxs-lookup"><span data-stu-id="76b0f-114">The cmdlet should define a `Name` parameter or equivalent so that the cmdlet will be able to modify the system by some sort of identifier.</span></span> <span data-ttu-id="76b0f-115">Außerdem sollte mit dem-Cmdlet der `Force` -Parameter und der-Parameter definiert werden `PassThru` .</span><span class="sxs-lookup"><span data-stu-id="76b0f-115">In addition, the cmdlet should define the `Force` and `PassThru` parameters.</span></span> <span data-ttu-id="76b0f-116">Weitere Informationen zu diesen Parametern finden Sie unter [Erstellen eines Cmdlets, das das System ändert](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="76b0f-116">For more information about these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="defining-a-parameter-alias"></a><span data-ttu-id="76b0f-117">Definieren eines parameteralias</span><span class="sxs-lookup"><span data-stu-id="76b0f-117">Defining a Parameter Alias</span></span>

<span data-ttu-id="76b0f-118">Ein parameteralias kann ein alternativer Name oder ein gut definierter Kurzname mit einem oder zwei Buchstaben für einen Cmdlet-Parameter sein.</span><span class="sxs-lookup"><span data-stu-id="76b0f-118">A parameter alias can be an alternate name or a well-defined 1-letter or 2-letter short name for a cmdlet parameter.</span></span> <span data-ttu-id="76b0f-119">In beiden Fällen besteht das Ziel der Verwendung von Aliasen darin, den Benutzereintrag von der Befehlszeile aus zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="76b0f-119">In both cases, the goal of using aliases is to simplify user entry from the command line.</span></span> <span data-ttu-id="76b0f-120">Windows PowerShell unterstützt Parameter Aliase über das [System. Management. Automation. Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) -Attribut, das die Deklarations Syntax [Alias ()] verwendet.</span><span class="sxs-lookup"><span data-stu-id="76b0f-120">Windows PowerShell supports parameter aliases through the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, which uses the declaration syntax [Alias()].</span></span>

<span data-ttu-id="76b0f-121">Der folgende Code zeigt, wie dem-Parameter ein Alias hinzugefügt wird `Name` .</span><span class="sxs-lookup"><span data-stu-id="76b0f-121">The following code shows how an alias is added to the `Name` parameter.</span></span>

```csharp
/// <summary>
/// Specify the mandatory Name parameter used to identify the
/// processes to be stopped.
/// </summary>
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true,
           HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
)]
[Alias("ProcessName")]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;
```

<span data-ttu-id="76b0f-122">Zusätzlich zur Verwendung des [System. Management. Automation. Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) -Attributs führt die Windows PowerShell-Laufzeit eine partielle namens Übereinstimmung aus, auch wenn keine Aliase angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="76b0f-122">In addition to using the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, the Windows PowerShell runtime performs partial name matching, even if no aliases are specified.</span></span> <span data-ttu-id="76b0f-123">Wenn das Cmdlet z. b. über einen `FileName` Parameter verfügt und der einzige Parameter ist, der mit beginnt `F` , kann der Benutzer `Filename` , `Filenam` , `File` , oder eingeben `Fi` `F` und den Eintrag weiterhin als Parameter erkennen `FileName` .</span><span class="sxs-lookup"><span data-stu-id="76b0f-123">For example, if your cmdlet has a `FileName` parameter and that is the only parameter that starts with `F`, the user could enter `Filename`, `Filenam`, `File`, `Fi`, or `F` and still recognize the entry as the `FileName` parameter.</span></span>

## <a name="creating-help-for-parameters"></a><span data-ttu-id="76b0f-124">Erstellen von Hilfe für Parameter</span><span class="sxs-lookup"><span data-stu-id="76b0f-124">Creating Help for Parameters</span></span>

<span data-ttu-id="76b0f-125">Mit Windows PowerShell können Sie Hilfe für Cmdlet-Parameter erstellen.</span><span class="sxs-lookup"><span data-stu-id="76b0f-125">Windows PowerShell allows you to create Help for cmdlet parameters.</span></span> <span data-ttu-id="76b0f-126">Verwenden Sie dies für alle Parameter, die für die Systemänderung und das Benutzer Feedback verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="76b0f-126">Do this for any parameter used for system modification and user feedback.</span></span> <span data-ttu-id="76b0f-127">Für jeden Parameter zur Unterstützung der Hilfe können Sie das `HelpMessage` Attribute-Schlüsselwort in der [System. Management. Automation. Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) -Attribut Deklaration festlegen.</span><span class="sxs-lookup"><span data-stu-id="76b0f-127">For each parameter to support Help, you can set the `HelpMessage` attribute keyword in the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="76b0f-128">Dieses Schlüsselwort definiert den Text, der dem Benutzer zur Unterstützung bei der Verwendung des-Parameters angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="76b0f-128">This keyword defines the text to display to the user for assistance in using the parameter.</span></span> <span data-ttu-id="76b0f-129">Sie können auch das- `HelpMessageBaseName` Schlüsselwort festlegen, um den Basis Namen einer Ressource zu identifizieren, die für die Nachricht verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="76b0f-129">You can also set the `HelpMessageBaseName` keyword to identify the base name of a resource to use for the message.</span></span> <span data-ttu-id="76b0f-130">Wenn Sie dieses Schlüsselwort festlegen, müssen Sie auch das- `HelpMessageResourceId` Schlüsselwort festlegen, um den Ressourcen Bezeichner anzugeben.</span><span class="sxs-lookup"><span data-stu-id="76b0f-130">If you set this keyword, you must also set the `HelpMessageResourceId` keyword to specify the resource identifier.</span></span>

<span data-ttu-id="76b0f-131">Der folgende Code aus diesem Stop-Proc Cmdlet definiert das `HelpMessage` Attribut Schlüsselwort für den `Name` Parameter.</span><span class="sxs-lookup"><span data-stu-id="76b0f-131">The following code from this Stop-Proc cmdlet defines the `HelpMessage` attribute keyword for the `Name` parameter.</span></span>

```csharp
/// <summary>
/// Specify the mandatory Name parameter used to identify the
/// processes to be stopped.
/// </summary>
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true,
           HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
)]
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="76b0f-132">Überschreiben einer Eingabe Verarbeitungsmethode</span><span class="sxs-lookup"><span data-stu-id="76b0f-132">Overriding an Input Processing Method</span></span>

<span data-ttu-id="76b0f-133">Ihr Cmdlet muss eine Eingabe Verarbeitungsmethode überschreiben, meistens handelt es sich hierbei um [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span><span class="sxs-lookup"><span data-stu-id="76b0f-133">Your cmdlet must override an input processing method, most often this will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="76b0f-134">Wenn Sie das System ändern, sollte das Cmdlet die Methoden " [System. Management. Automation. Cmdlet. schuldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) " und " [System. Management. Automation. Cmdlet.-dcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) " anrufen, damit der Benutzer Feedback bereitstellen kann, bevor eine Änderung vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="76b0f-134">When modifying the system, the cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to allow the user to provide feedback before a change is made.</span></span> <span data-ttu-id="76b0f-135">Weitere Informationen zu diesen Methoden finden Sie unter [Erstellen eines Cmdlets, das das System ändert](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="76b0f-135">For more information about these methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="supporting-wildcard-expansion"></a><span data-ttu-id="76b0f-136">Unterstützung für Platzhalter</span><span class="sxs-lookup"><span data-stu-id="76b0f-136">Supporting Wildcard Expansion</span></span>

<span data-ttu-id="76b0f-137">Um die Auswahl mehrerer Objekte zu ermöglichen, kann das Cmdlet die Klassen " [System. Management. Automation. wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) " und " [System. Management. Automation. wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions) " verwenden, um die Unterstützung für Platzhalter Erweiterungen für Parameter Eingaben bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="76b0f-137">To allow the selection of multiple objects, your cmdlet can use the [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) and [System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions) classes to provide wildcard expansion support for parameter input.</span></span> <span data-ttu-id="76b0f-138">Beispiele für Platzhalter Muster sind LSA \*, \* txt und [a-c] \* .</span><span class="sxs-lookup"><span data-stu-id="76b0f-138">Examples of wildcard patterns are lsa\*, \*.txt, and [a-c]\*.</span></span> <span data-ttu-id="76b0f-139">Verwenden Sie das backanführungs Zeichen (') als Escapezeichen, wenn das Muster ein Zeichen enthält, das buchstäblich verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="76b0f-139">Use the back-quote character (\`) as an escape character when the pattern contains a character that should be used literally.</span></span>

<span data-ttu-id="76b0f-140">Platzhalter Erweiterungen von Datei-und Pfadnamen sind Beispiele für gängige Szenarien, in denen das Cmdlet möglicherweise die Unterstützung von Pfad Eingaben zulässt, wenn die Auswahl mehrerer Objekte erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="76b0f-140">Wildcard expansions of file and path names are examples of common scenarios where the cmdlet may want to allow support for path inputs when the selection of multiple objects is required.</span></span> <span data-ttu-id="76b0f-141">Häufig wird das Dateisystem angezeigt, in dem ein Benutzer alle Dateien im aktuellen Ordner anzeigen möchte.</span><span class="sxs-lookup"><span data-stu-id="76b0f-141">A common case is in the file system, where a user wants to see all files residing in the current folder.</span></span>

<span data-ttu-id="76b0f-142">Sie sollten eine angepasste Platzhalter Muster Vergleichs Implementierung nur selten benötigen.</span><span class="sxs-lookup"><span data-stu-id="76b0f-142">You should need a customized wildcard pattern matching implementation only rarely.</span></span> <span data-ttu-id="76b0f-143">In diesem Fall sollte Ihr Cmdlet entweder die vollständige POSIX 1003,2-und 3,13-Spezifikation für die Platzhalter Erweiterung oder die folgende vereinfachte Teilmenge unterstützen:</span><span class="sxs-lookup"><span data-stu-id="76b0f-143">In this case, your cmdlet should support either the full POSIX 1003.2, 3.13 specification for wildcard expansion or the following simplified subset:</span></span>

- <span data-ttu-id="76b0f-144">**Fragezeichen (?).**</span><span class="sxs-lookup"><span data-stu-id="76b0f-144">**Question mark (?).**</span></span> <span data-ttu-id="76b0f-145">Entspricht einem beliebigen Zeichen an der angegebenen Position.</span><span class="sxs-lookup"><span data-stu-id="76b0f-145">Matches any character at the specified location.</span></span>

- <span data-ttu-id="76b0f-146">**Sternchen ( \* ).**</span><span class="sxs-lookup"><span data-stu-id="76b0f-146">**Asterisk (\*).**</span></span> <span data-ttu-id="76b0f-147">Entspricht 0 (null) oder mehr Zeichen, beginnend an der angegebenen Position.</span><span class="sxs-lookup"><span data-stu-id="76b0f-147">Matches zero or more characters starting at the specified location.</span></span>

- <span data-ttu-id="76b0f-148">**Öffnende eckige Klammer ([).**</span><span class="sxs-lookup"><span data-stu-id="76b0f-148">**Open bracket ([).**</span></span> <span data-ttu-id="76b0f-149">Führt einen Muster Klammer Ausdruck ein, der Zeichen oder einen Zeichenbereich enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="76b0f-149">Introduces a pattern bracket expression that can contain characters or a range of characters.</span></span> <span data-ttu-id="76b0f-150">Wenn ein Bereich erforderlich ist, wird ein Bindestrich (-) verwendet, um den Bereich anzugeben.</span><span class="sxs-lookup"><span data-stu-id="76b0f-150">If a range is required, a hyphen (-) is used to indicate the range.</span></span>

- <span data-ttu-id="76b0f-151">**Schließende Klammer (]).**</span><span class="sxs-lookup"><span data-stu-id="76b0f-151">**Close bracket (]).**</span></span> <span data-ttu-id="76b0f-152">Beendet einen Muster Klammer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="76b0f-152">Ends a pattern bracket expression.</span></span>

- <span data-ttu-id="76b0f-153">**Escape-Escapezeichen (').**</span><span class="sxs-lookup"><span data-stu-id="76b0f-153">**Back-quote escape character (\`).**</span></span> <span data-ttu-id="76b0f-154">Gibt an, dass das nächste Zeichen wörtlich genommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="76b0f-154">Indicates that the next character should be taken literally.</span></span> <span data-ttu-id="76b0f-155">Beachten Sie, dass bei der Angabe des backanführungs Zeichens von der Befehlszeile aus (im Gegensatz zur programmgesteuerten Angabe) das Escapezeichen für das Back-End zweimal angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="76b0f-155">Be aware that when specifying the back-quote character from the command line (as opposed to specifying it programmatically), the back-quote escape character must be specified twice.</span></span>

> [!NOTE]
> <span data-ttu-id="76b0f-156">Weitere Informationen zu Platzhalter Mustern finden Sie [unter unterstützen von Platzhaltern in Cmdlet-Parametern](./supporting-wildcard-characters-in-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="76b0f-156">For more information about wildcard patterns, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).</span></span>

<span data-ttu-id="76b0f-157">Der folgende Code zeigt, wie Sie Platzhalter Optionen festlegen und das Platzhalter Muster definieren, das zum Auflösen des- `Name` Parameters für dieses Cmdlet verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="76b0f-157">The following code shows how to set wildcard options and define the wildcard pattern used for resolving the `Name` parameter for this cmdlet.</span></span>

```csharp
WildcardOptions options = WildcardOptions.IgnoreCase |
                          WildcardOptions.Compiled;
WildcardPattern wildcard = new WildcardPattern(name,options);
```

<span data-ttu-id="76b0f-158">Der folgende Code zeigt, wie Sie überprüfen, ob der Prozess Name mit dem definierten Platzhalter Muster übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="76b0f-158">The following code shows how to test whether the process name matches the defined wildcard pattern.</span></span> <span data-ttu-id="76b0f-159">Beachten Sie, dass in diesem Fall, wenn der Prozess Name nicht mit dem Muster identisch ist, das Cmdlet fortgesetzt wird, um den nächsten Prozessnamen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="76b0f-159">Notice that, in this case, if the process name does not match the pattern, the cmdlet continues on to get the next process name.</span></span>

```csharp
if (!wildcard.IsMatch(processName))
{
  continue;
}
```

## <a name="code-sample"></a><span data-ttu-id="76b0f-160">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="76b0f-160">Code Sample</span></span>

<span data-ttu-id="76b0f-161">Den gesamten c#-Beispielcode finden Sie unter [StopProcessSample03 Sample](./stopprocesssample03-sample.md).</span><span class="sxs-lookup"><span data-stu-id="76b0f-161">For the complete C# sample code, see [StopProcessSample03 Sample](./stopprocesssample03-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="76b0f-162">Definieren von Objekttypen und Formatierung</span><span class="sxs-lookup"><span data-stu-id="76b0f-162">Define Object Types and Formatting</span></span>

<span data-ttu-id="76b0f-163">Windows PowerShell übergibt Informationen zwischen Cmdlets mithilfe von .NET-Objekten.</span><span class="sxs-lookup"><span data-stu-id="76b0f-163">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="76b0f-164">Folglich muss ein Cmdlet möglicherweise seinen eigenen Typ definieren, oder das Cmdlet muss möglicherweise einen vorhandenen Typ erweitern, der von einem anderen Cmdlet bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="76b0f-164">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="76b0f-165">Weitere Informationen zum Definieren neuer Typen oder zum Erweitern vorhandener Typen finden Sie unter [Erweitern von Objekttypen und Formatierung](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="76b0f-165">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="76b0f-166">Cmdlet wird aufgebaut</span><span class="sxs-lookup"><span data-stu-id="76b0f-166">Building the Cmdlet</span></span>

<span data-ttu-id="76b0f-167">Nachdem ein Cmdlet implementiert wurde, muss es über ein Windows PowerShell-Snap-in in Windows PowerShell registriert werden.</span><span class="sxs-lookup"><span data-stu-id="76b0f-167">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="76b0f-168">Weitere Informationen zum Registrieren von Cmdlets finden [Sie unter Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="76b0f-168">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="76b0f-169">Testen des Cmdlets</span><span class="sxs-lookup"><span data-stu-id="76b0f-169">Testing the Cmdlet</span></span>

<span data-ttu-id="76b0f-170">Wenn das Cmdlet bei Windows PowerShell registriert wurde, können Sie es in der Befehlszeile testen.</span><span class="sxs-lookup"><span data-stu-id="76b0f-170">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="76b0f-171">Testen Sie nun das Cmdlet "Sample Stop-Proc".</span><span class="sxs-lookup"><span data-stu-id="76b0f-171">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="76b0f-172">Weitere Informationen zur Verwendung von Cmdlets über die Befehlszeile finden Sie unter [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="76b0f-172">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="76b0f-173">Starten Sie Windows PowerShell, und verwenden Sie Stop-Proc, um einen Prozess mit dem ProcessName-Alias für den Parameter zu unterbinden `Name` .</span><span class="sxs-lookup"><span data-stu-id="76b0f-173">Start Windows PowerShell and use Stop-Proc to stop a process using the ProcessName alias for the `Name` parameter.</span></span>

    ```powershell
    PS> stop-proc -ProcessName notepad
    ```

    <span data-ttu-id="76b0f-174">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76b0f-174">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (3496)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="76b0f-175">Legen Sie den folgenden Eintrag in der Befehlszeile ab.</span><span class="sxs-lookup"><span data-stu-id="76b0f-175">Make the following entry on the command line.</span></span> <span data-ttu-id="76b0f-176">Da der Name-Parameter obligatorisch ist, werden Sie dazu aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="76b0f-176">Because the Name parameter is mandatory, you are prompted for it.</span></span> <span data-ttu-id="76b0f-177">Eingabe von "!?"</span><span class="sxs-lookup"><span data-stu-id="76b0f-177">Entering "!?"</span></span> <span data-ttu-id="76b0f-178">Ruft den Hilfetext auf, der dem-Parameter zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="76b0f-178">brings up the help text associated with the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

    <span data-ttu-id="76b0f-179">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76b0f-179">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    (Type !? for Help.)
    Name[0]: !?
    The name of one or more processes to stop. Wildcards are permitted.
    Name[0]: notepad
    ```

- <span data-ttu-id="76b0f-180">Führen Sie nun den folgenden Eintrag aus, um alle Prozesse anzuhalten, die dem Platzhalter Muster "\* Note \* " entsprechen.</span><span class="sxs-lookup"><span data-stu-id="76b0f-180">Now make the following entry to stop all processes that match the wildcard pattern "\*note\*".</span></span> <span data-ttu-id="76b0f-181">Sie werden dazu aufgefordert, jeden Prozess anzuhalten, der mit dem Muster übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="76b0f-181">You are prompted before stopping each process that matches the pattern.</span></span>

    ```powershell
    PS> stop-proc -Name *note*
    ```

    <span data-ttu-id="76b0f-182">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76b0f-182">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (1112)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

    <span data-ttu-id="76b0f-183">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76b0f-183">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTEM (3712)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

    <span data-ttu-id="76b0f-184">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76b0f-184">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTE (3592)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="76b0f-185">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76b0f-185">See Also</span></span>

[<span data-ttu-id="76b0f-186">Erstellen Sie ein Cmdlet, das das System ändert.</span><span class="sxs-lookup"><span data-stu-id="76b0f-186">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="76b0f-187">Erstellen eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="76b0f-187">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="76b0f-188">[Erweitern von Objekttypen und Formatierung](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="76b0f-188">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="76b0f-189">[Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="76b0f-189">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="76b0f-190">Unterstützen von Platzhaltern in Cmdlet-Parametern</span><span class="sxs-lookup"><span data-stu-id="76b0f-190">Supporting Wildcards in Cmdlet Parameters</span></span>](./supporting-wildcard-characters-in-cmdlet-parameters.md)

[<span data-ttu-id="76b0f-191">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="76b0f-191">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
