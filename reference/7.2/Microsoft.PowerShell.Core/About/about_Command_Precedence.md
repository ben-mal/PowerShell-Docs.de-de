---
description: Beschreibt, wie PowerShell bestimmt, welcher Befehl ausgeführt werden soll.
Locale: en-US
ms.date: 02/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_command_precedence?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Command_Precedence
ms.openlocfilehash: 8b8a27a47c454b59b5dd4bb2d6e8a8cc3cec78c8
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103196244"
---
# <a name="about-command-precedence"></a><span data-ttu-id="7c59d-103">Informationen zur Befehls Rangfolge</span><span class="sxs-lookup"><span data-stu-id="7c59d-103">About Command Precedence</span></span>

## <a name="short-description"></a><span data-ttu-id="7c59d-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c59d-104">Short description</span></span>
<span data-ttu-id="7c59d-105">Beschreibt, wie PowerShell bestimmt, welcher Befehl ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c59d-105">Describes how PowerShell determines which command to run.</span></span>

## <a name="long-description"></a><span data-ttu-id="7c59d-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c59d-106">Long description</span></span>

<span data-ttu-id="7c59d-107">Befehls Rangfolge: Beschreibt, wie PowerShell bestimmt, welcher Befehl ausgeführt werden soll, wenn eine Sitzung mehr als einen Befehl mit demselben Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="7c59d-107">Command precedence describes how PowerShell determines which command to run when a session contains more than one command with the same name.</span></span> <span data-ttu-id="7c59d-108">Befehle in einer Sitzung können ausgeblendet oder durch Befehle mit demselben Namen ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="7c59d-108">Commands within a session can be hidden or replaced by commands with the same name.</span></span> <span data-ttu-id="7c59d-109">In diesem Artikel wird gezeigt, wie Sie ausgeblendete Befehle ausführen und Konflikte mit Befehlsnamen vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7c59d-109">This article shows you how to run hidden commands and how to avoid command-name conflicts.</span></span>

## <a name="command-precedence"></a><span data-ttu-id="7c59d-110">Befehls Rangfolge</span><span class="sxs-lookup"><span data-stu-id="7c59d-110">Command precedence</span></span>

<span data-ttu-id="7c59d-111">Wenn eine PowerShell-Sitzung mehr als einen Befehl mit demselben Namen enthält, bestimmt PowerShell anhand der folgenden Regeln, welcher Befehl ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c59d-111">When a PowerShell session includes more than one command that has the same name, PowerShell determines which command to run by using the following rules.</span></span>

<span data-ttu-id="7c59d-112">Wenn Sie den Pfad zu einem Befehl angeben, führt PowerShell den Befehl an dem Speicherort aus, der durch den Pfad angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7c59d-112">If you specify the path to a command, PowerShell runs the command at the location specified by the path.</span></span>

<span data-ttu-id="7c59d-113">Der folgende Befehl führt beispielsweise das FindDocs.ps1 Skript im Verzeichnis "C: \\ techdocs" aus:</span><span class="sxs-lookup"><span data-stu-id="7c59d-113">For example, the following command runs the FindDocs.ps1 script in the "C:\\TechDocs" directory:</span></span>

```
C:\TechDocs\FindDocs.ps1
```

<span data-ttu-id="7c59d-114">Als Sicherheits Feature führt PowerShell keine ausführbaren (nativen) Befehle (einschließlich PowerShell-Skripts) aus, es sei denn, der Befehl befindet sich in einem Pfad, der in der PATH-Umgebungsvariablen aufgelistet ist, `$env:path` oder es sei denn, Sie geben den Pfad zur Skriptdatei an.</span><span class="sxs-lookup"><span data-stu-id="7c59d-114">As a security feature, PowerShell does not run executable (native) commands, including PowerShell scripts, unless the command is located in a path that is listed in the Path environment variable `$env:path` or unless you specify the path to the script file.</span></span>

<span data-ttu-id="7c59d-115">Zum Ausführen eines Skripts, das sich im aktuellen Verzeichnis befindet, geben Sie den vollständigen Pfad an, oder geben Sie einen Punkt ein, `.\` um das aktuelle Verzeichnis darzustellen.</span><span class="sxs-lookup"><span data-stu-id="7c59d-115">To run a script that is in the current directory, specify the full path, or type a dot `.\` to represent the current directory.</span></span>

<span data-ttu-id="7c59d-116">Wenn Sie z. b. die FindDocs.ps1 Datei im aktuellen Verzeichnis ausführen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7c59d-116">For example, to run the FindDocs.ps1 file in the current directory, type:</span></span>

```
.\FindDocs.ps1
```

### <a name="using-wildcards-in-execution"></a><span data-ttu-id="7c59d-117">Verwenden von Platzhaltern bei der Ausführung</span><span class="sxs-lookup"><span data-stu-id="7c59d-117">Using wildcards in execution</span></span>

<span data-ttu-id="7c59d-118">In der Befehlsausführung können Sie Platzhalter verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c59d-118">You may use wildcards in command execution.</span></span> <span data-ttu-id="7c59d-119">Die Verwendung von Platzhalter Zeichen wird auch als " *glob"* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7c59d-119">Using wildcard characters is also known as *globbing*.</span></span>

<span data-ttu-id="7c59d-120">PowerShell führt eine Datei mit einer Platzhalter Übereinstimmung vor einer Literalübereinstimmung aus.</span><span class="sxs-lookup"><span data-stu-id="7c59d-120">PowerShell executes a file that has a wildcard match, before a literal match.</span></span>

<span data-ttu-id="7c59d-121">Nehmen Sie beispielsweise ein Verzeichnis mit den folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="7c59d-121">For example, consider a directory with the following files:</span></span>

```
Get-ChildItem C:\temp\test


    Directory: C:\temp\test


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        5/20/2019   2:29 PM             28 a.ps1
-a----        5/20/2019   2:29 PM             28 [a1].ps1
```

<span data-ttu-id="7c59d-122">Beide Skriptdateien weisen den gleichen Inhalt auf: `$MyInvocation.MyCommand.Path` .</span><span class="sxs-lookup"><span data-stu-id="7c59d-122">Both script files have the same content: `$MyInvocation.MyCommand.Path`.</span></span>
<span data-ttu-id="7c59d-123">Dieser Befehl zeigt den Namen des Skripts an, das aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7c59d-123">This command displays the name of the script that is invoked.</span></span>

<span data-ttu-id="7c59d-124">Wenn Sie Ausführen `[a1].ps1` , wird die Datei `a.ps1` ausgeführt, auch wenn die Datei `[a1].ps1` eine Literalübereinstimmung ist.</span><span class="sxs-lookup"><span data-stu-id="7c59d-124">When you run `[a1].ps1`, the file `a.ps1` is executed even though the file `[a1].ps1` is a literal match.</span></span>

```powershell
C:\temp\test\[a1].ps1
```

```Output
C:\temp\test\a.ps1
```

<span data-ttu-id="7c59d-125">Löschen Sie nun die `a.ps1` Datei, und versuchen Sie erneut, Sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7c59d-125">Now let's delete the `a.ps1` file and attempt to run it again.</span></span>

```powershell
Remove-Item C:\temp\test\a.ps1
C:\temp\test\[a1].ps1
```

```Output
C:\temp\test\[a1].ps1
```

<span data-ttu-id="7c59d-126">Sie können in der Ausgabe sehen, die `[a1].ps1` dieses Mal ausgeführt wird, da die Literalübereinstimmung für dieses Platzhalter Muster die einzige Datei Übereinstimmung ist.</span><span class="sxs-lookup"><span data-stu-id="7c59d-126">You can see from the output that `[a1].ps1` runs this time because the literal match is the only file match for that wildcard pattern.</span></span>

<span data-ttu-id="7c59d-127">Weitere Informationen zur Verwendung von Platzhaltern in PowerShell finden Sie unter [about_Wildcards](about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="7c59d-127">For more information about how PowerShell uses wildcards, see [about_Wildcards](about_Wildcards.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7c59d-128">Um die Suche auf einen relativen Pfad einzuschränken, müssen Sie dem Skriptnamen den Pfad voranstellen `.\` .</span><span class="sxs-lookup"><span data-stu-id="7c59d-128">To limit the search to a relative path, you must prefix the script name with the `.\` path.</span></span> <span data-ttu-id="7c59d-129">Dies schränkt die Suche nach Befehlen auf Dateien in diesem relativen Pfad ein.</span><span class="sxs-lookup"><span data-stu-id="7c59d-129">This limits the search for commands to files in that relative path.</span></span> <span data-ttu-id="7c59d-130">Ohne dieses Präfix können andere PowerShell-Syntax Konflikte verursachen, und es gibt nur wenige Garantien, dass die Datei gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="7c59d-130">Without this prefix, other PowerShell syntax may conflict and there are few guarantees that the file will be found.</span></span>

<span data-ttu-id="7c59d-131">Wenn Sie keinen Pfad angeben, verwendet PowerShell die folgende Rangfolge, wenn Befehle für alle in der aktuellen Sitzung geladenen Elemente ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="7c59d-131">If you do not specify a path, PowerShell uses the following precedence order when it runs commands for all items loaded in the current session:</span></span>

  1. <span data-ttu-id="7c59d-132">Alias</span><span class="sxs-lookup"><span data-stu-id="7c59d-132">Alias</span></span>
  2. <span data-ttu-id="7c59d-133">Funktion</span><span class="sxs-lookup"><span data-stu-id="7c59d-133">Function</span></span>
  3. <span data-ttu-id="7c59d-134">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7c59d-134">Cmdlet</span></span>
  4. <span data-ttu-id="7c59d-135">Externe ausführbare Dateien (Programme und nicht-PowerShell-Skripts)</span><span class="sxs-lookup"><span data-stu-id="7c59d-135">External executable files (programs and non-PowerShell scripts)</span></span>

<span data-ttu-id="7c59d-136">Wenn Sie "Help" eingeben, sucht PowerShell zunächst nach einem Alias mit dem Namen `help` , dann nach einer Funktion mit dem Namen `Help` und schließlich nach einem Cmdlet mit dem Namen `Help` .</span><span class="sxs-lookup"><span data-stu-id="7c59d-136">Therefore, if you type "help", PowerShell first looks for an alias named `help`, then a function named `Help`, and finally a cmdlet named `Help`.</span></span> <span data-ttu-id="7c59d-137">Er führt das erste gefundene `help` Element aus.</span><span class="sxs-lookup"><span data-stu-id="7c59d-137">It runs the first `help` item that it finds.</span></span>

<span data-ttu-id="7c59d-138">Wenn Ihre Sitzung z. b. ein Cmdlet und eine Funktion enthält, `Get-Map` bei der Sie eingeben, `Get-Map` führt PowerShell die Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="7c59d-138">For example, if your session contains a cmdlet and a function, both named `Get-Map`, when you type `Get-Map`, PowerShell runs the function.</span></span>

> [!NOTE]
> <span data-ttu-id="7c59d-139">Dies gilt nur für geladene Befehle.</span><span class="sxs-lookup"><span data-stu-id="7c59d-139">This only applies to loaded commands.</span></span> <span data-ttu-id="7c59d-140">Wenn eine `build` ausführbare Datei und ein Alias `build` für eine Funktion mit dem Namen `Invoke-Build` innerhalb eines Moduls vorhanden sind, das nicht in die aktuelle Sitzung geladen wird, führt PowerShell `build` stattdessen die ausführbare Datei aus.</span><span class="sxs-lookup"><span data-stu-id="7c59d-140">If there is a `build` executable and an Alias `build` for a function with the name of `Invoke-Build` inside a module that is not loaded into the current session, PowerShell runs the `build` executable instead.</span></span> <span data-ttu-id="7c59d-141">Module werden nicht automatisch geladen, wenn in diesem Fall die externe ausführbare Datei gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="7c59d-141">It does not auto-load modules if it finds the external executable in this case.</span></span> <span data-ttu-id="7c59d-142">Nur wenn keine externe ausführbare Datei gefunden wird, wird ein Alias, eine Funktion oder ein Cmdlet mit dem angegebenen Namen aufgerufen, wodurch das automatische Laden des Moduls ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="7c59d-142">It is only when no external executable is found that an alias, function, or cmdlet with the given name is invoked, thereby triggering auto-loading of its module.</span></span>

<span data-ttu-id="7c59d-143">Wenn die Sitzung Elemente desselben Typs enthält, die denselben Namen aufweisen, führt PowerShell das neuere Element aus.</span><span class="sxs-lookup"><span data-stu-id="7c59d-143">When the session contains items of the same type that have the same name, PowerShell runs the newer item.</span></span>

<span data-ttu-id="7c59d-144">Wenn Sie z. b. ein anderes `Get-Date` Cmdlet aus einem Modul importieren, `Get-Date` führt PowerShell die importierte Version über die systemeigene Version aus, wenn Sie eingeben.</span><span class="sxs-lookup"><span data-stu-id="7c59d-144">For example, if you import another `Get-Date` cmdlet from a module, when you type `Get-Date`, PowerShell runs the imported version over the native one.</span></span>

## <a name="hidden-and-replaced-items"></a><span data-ttu-id="7c59d-145">Ausgeblendete und ersetzte Elemente</span><span class="sxs-lookup"><span data-stu-id="7c59d-145">Hidden and replaced items</span></span>

<span data-ttu-id="7c59d-146">Aufgrund dieser Regeln können Elemente durch Elemente mit dem gleichen Namen ersetzt oder ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c59d-146">As a result of these rules, items can be replaced or hidden by items with the same name.</span></span>

<span data-ttu-id="7c59d-147">Elemente sind "ausgeblendet" oder "Shadowing", wenn Sie weiterhin auf das ursprüngliche Element zugreifen können, z. b. indem Sie den Elementnamen mit einem Modul-oder Snap-in-Namen qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="7c59d-147">Items are "hidden" or "shadowed" if you can still access the original item, such as by qualifying the item name with a module or snap-in name.</span></span>

<span data-ttu-id="7c59d-148">Wenn Sie z. b. eine Funktion importieren, die den gleichen Namen wie ein Cmdlet in der Sitzung hat, ist das Cmdlet ausgeblendet (aber nicht ersetzt), da es aus einem Snap-in oder Modul importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7c59d-148">For example, if you import a function that has the same name as a cmdlet in the session, the cmdlet is hidden (but not replaced) because it was imported from a snap-in or module.</span></span>

<span data-ttu-id="7c59d-149">Elemente werden ersetzt oder überschrieben, wenn Sie nicht mehr auf das ursprüngliche Element zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="7c59d-149">Items are "replaced" or "overwritten" if you can no longer access the original item.</span></span>

<span data-ttu-id="7c59d-150">Wenn Sie z. b. eine Variable importieren, die denselben Namen wie eine Variable in der Sitzung hat, wird die ursprüngliche Variable ersetzt und ist nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7c59d-150">For example, if you import a variable that has the same name as a variable in the session, the original variable is replaced and is no longer accessible.</span></span>
<span data-ttu-id="7c59d-151">Eine Variable kann nicht mit einem Modulnamen qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="7c59d-151">You cannot qualify a variable with a module name.</span></span>

<span data-ttu-id="7c59d-152">Wenn Sie eine Funktion in der Befehlszeile eingeben und dann eine Funktion mit demselben Namen importieren, wird die ursprüngliche Funktion ersetzt und ist nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7c59d-152">Also, if you type a function at the command line and then import a function with the same name, the original function is replaced and is no longer accessible.</span></span>

### <a name="finding-hidden-commands"></a><span data-ttu-id="7c59d-153">Suchen von verdeckten Befehlen</span><span class="sxs-lookup"><span data-stu-id="7c59d-153">Finding hidden commands</span></span>

<span data-ttu-id="7c59d-154">Der **all** -Parameter des [Get-Command-](xref:Microsoft.PowerShell.Core.Get-Command) Cmdlets Ruft alle Befehle mit dem angegebenen Namen ab, auch wenn Sie ausgeblendet oder ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="7c59d-154">The **All** parameter of the [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) cmdlet gets all commands with the specified name, even if they are hidden or replaced.</span></span> <span data-ttu-id="7c59d-155">Ab PowerShell 3,0 ruft standardmäßig nur die Befehle ab, die ausgeführt werden, `Get-Command` Wenn Sie den Befehlsnamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="7c59d-155">Beginning in PowerShell 3.0, by default, `Get-Command` gets only the commands that run when you type the command name.</span></span>

<span data-ttu-id="7c59d-156">In den folgenden Beispielen schließt die Sitzung eine `Get-Date` Funktion und ein [Get-Date-](xref:Microsoft.PowerShell.Utility.Get-Date) Cmdlet ein.</span><span class="sxs-lookup"><span data-stu-id="7c59d-156">In the following examples, the session includes a `Get-Date` function and a [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet.</span></span>

<span data-ttu-id="7c59d-157">Der folgende Befehl ruft den Befehl ab, der ausgeführt wird `Get-Date` , wenn Sie eingeben `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="7c59d-157">The following command gets the `Get-Date` command that runs when you type `Get-Date`.</span></span>

```powershell
Get-Command Get-Date
```

```output
CommandType     Name                      ModuleName
-----------     ----                      ----------
Function        Get-Date
```

<span data-ttu-id="7c59d-158">Der folgende Befehl verwendet den **all** -Parameter, um alle Befehle zu erhalten `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="7c59d-158">The following command uses the **All** parameter to get all `Get-Date` commands.</span></span>

```powershell
Get-Command Get-Date -All
```

```output
CommandType     Name                      ModuleName
-----------     ----                      ----------
Function        Get-Date
Cmdlet          Get-Date                  Microsoft.PowerShell.Utility
```

### <a name="running-hidden-commands"></a><span data-ttu-id="7c59d-159">Ausführen von verdeckten Befehlen</span><span class="sxs-lookup"><span data-stu-id="7c59d-159">Running hidden commands</span></span>

<span data-ttu-id="7c59d-160">Sie können bestimmte Befehle ausführen, indem Sie Element Eigenschaften angeben, die den Befehl von anderen Befehlen unterscheiden, die denselben Namen aufweisen können.</span><span class="sxs-lookup"><span data-stu-id="7c59d-160">You can run particular commands by specifying item properties that distinguish the command from other commands that might have the same name.</span></span> <span data-ttu-id="7c59d-161">Mit dieser Methode können Sie einen beliebigen Befehl ausführen, dies ist jedoch besonders nützlich für das Ausführen von ausgeblendeten Befehlen.</span><span class="sxs-lookup"><span data-stu-id="7c59d-161">You can use this method to run any command, but it is especially useful for running hidden commands.</span></span>

#### <a name="qualified-names"></a><span data-ttu-id="7c59d-162">Qualifizierte Namen</span><span class="sxs-lookup"><span data-stu-id="7c59d-162">Qualified names</span></span>

<span data-ttu-id="7c59d-163">Wenn Sie den mit dem Modul gekennzeichneten Namen eines Cmdlets verwenden, können Sie Befehle ausführen, die von einem Element mit dem gleichen Namen ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c59d-163">Using the module-qualified name of a cmdlet allows you to run commands hidden by an item with the same name.</span></span> <span data-ttu-id="7c59d-164">Beispielsweise können Sie das `Get-Date` Cmdlet ausführen, indem Sie es mit dem Modulnamen " **Microsoft. PowerShell. Utility**" qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="7c59d-164">For example, you can run the `Get-Date` cmdlet by qualifying it with its module name **Microsoft.PowerShell.Utility**.</span></span>

<span data-ttu-id="7c59d-165">Verwenden Sie diese bevorzugte Methode, wenn Sie Skripts schreiben, die Sie verteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="7c59d-165">Use this preferred method when writing scripts that you intend to distribute.</span></span> <span data-ttu-id="7c59d-166">Sie können nicht vorhersagen, welche Befehle in der Sitzung vorhanden sein können, in der das Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7c59d-166">You cannot predict which commands might be present in the session in which the script runs.</span></span>

```powershell
New-Alias -Name "Get-Date" -Value "Get-ChildItem"
Microsoft.PowerShell.Utility\Get-Date
```

```output
Tuesday, September 4, 2018 8:17:25 AM
```

<span data-ttu-id="7c59d-167">Um einen Befehl auszuführen, `New-Map` der durch das Modul hinzugefügt wurde `MapFunctions` , verwenden Sie den mit dem Modul qualifizierten Namen:</span><span class="sxs-lookup"><span data-stu-id="7c59d-167">To run a `New-Map` command that was added by the `MapFunctions` module, use its module-qualified name:</span></span>

```powershell
MapFunctions\New-Map
```

<span data-ttu-id="7c59d-168">Um das Modul zu finden, aus dem ein Befehl importiert wurde, verwenden Sie die **ModuleName** -Eigenschaft der Befehle.</span><span class="sxs-lookup"><span data-stu-id="7c59d-168">To find the module from which a command was imported, use the **ModuleName** property of commands.</span></span>

```
(Get-Command <command-name>).ModuleName
```

<span data-ttu-id="7c59d-169">Wenn Sie z. b. die Quelle des `Get-Date` Cmdlets ermitteln möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7c59d-169">For example, to find the source of the `Get-Date` cmdlet, type:</span></span>

```powershell
(Get-Command Get-Date).ModuleName
```

```output
Microsoft.PowerShell.Utility
```

> [!NOTE]
> <span data-ttu-id="7c59d-170">Variablen oder Aliase können nicht qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="7c59d-170">You cannot qualify variables or aliases.</span></span>

#### <a name="call-operator"></a><span data-ttu-id="7c59d-171">Calloperator</span><span class="sxs-lookup"><span data-stu-id="7c59d-171">Call operator</span></span>

<span data-ttu-id="7c59d-172">Sie können auch den-Operator verwenden, um ausgeblendete `Call` `&` Befehle auszuführen, indem Sie Sie mit einem [Get-ChildItem-](xref:Microsoft.PowerShell.Management.Get-ChildItem) Rückruf (Alias ist "dir") `Get-Command` oder [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module)kombinieren.</span><span class="sxs-lookup"><span data-stu-id="7c59d-172">You can also use the `Call` operator `&` to run hidden commands by combining it with a call to [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) (the alias is "dir"), `Get-Command` or [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span></span>

<span data-ttu-id="7c59d-173">Der calloperator führt Zeichen folgen und Skriptblöcke in einem untergeordneten Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="7c59d-173">The call operator executes strings and script blocks in a child scope.</span></span> <span data-ttu-id="7c59d-174">Weitere Informationen finden Sie unter [about_Operators](about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="7c59d-174">For more information, see [about_Operators](about_Operators.md).</span></span>

<span data-ttu-id="7c59d-175">Wenn Sie z. b. eine Funktion mit dem Namen haben, die `Map` von einem Alias mit dem Namen ausgeblendet wird `Map` , verwenden Sie den folgenden Befehl, um die Funktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7c59d-175">For example, if you have a function named `Map` that is hidden by an alias named `Map`, use the following command to run the function.</span></span>

```powershell
&(Get-Command -Name Map -CommandType Function)
```

<span data-ttu-id="7c59d-176">oder</span><span class="sxs-lookup"><span data-stu-id="7c59d-176">or</span></span>

```powershell
&(dir Function:\map)
```

<span data-ttu-id="7c59d-177">Sie können auch den Hidden-Befehl in einer Variablen speichern, um die Benutzerfreundlichkeit zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7c59d-177">You can also save your hidden command in a variable to make it easier to run.</span></span>

<span data-ttu-id="7c59d-178">Der folgende Befehl speichert z `Map` . b. die Funktion in der `$myMap` Variablen und verwendet dann den- `Call` Operator, um Sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7c59d-178">For example, the following command saves the `Map` function in the `$myMap` variable and then uses the `Call` operator to run it.</span></span>

```powershell
$myMap = (Get-Command -Name map -CommandType function)
&($myMap)
```

### <a name="replaced-items"></a><span data-ttu-id="7c59d-179">Ersetzte Elemente</span><span class="sxs-lookup"><span data-stu-id="7c59d-179">Replaced items</span></span>

<span data-ttu-id="7c59d-180">Ein ersetzter Eintrag ist ein Element, auf das Sie nicht mehr zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="7c59d-180">A "replaced" item is one that you can no longer access.</span></span> <span data-ttu-id="7c59d-181">Sie können Elemente ersetzen, indem Sie Elemente desselben Namens aus einem Modul oder Snap-in importieren.</span><span class="sxs-lookup"><span data-stu-id="7c59d-181">You can replace items by importing items of the same name from a module or snap-in.</span></span>

<span data-ttu-id="7c59d-182">Wenn Sie z. b. `Get-Map` in der Sitzung eine Funktion eingeben und eine Funktion mit dem Namen importieren `Get-Map` , ersetzt Sie die ursprüngliche Funktion.</span><span class="sxs-lookup"><span data-stu-id="7c59d-182">For example, if you type a `Get-Map` function in your session, and you import a function called `Get-Map`, it replaces the original function.</span></span> <span data-ttu-id="7c59d-183">Sie können Sie nicht in der aktuellen Sitzung abrufen.</span><span class="sxs-lookup"><span data-stu-id="7c59d-183">You cannot retrieve it in the current session.</span></span>

<span data-ttu-id="7c59d-184">Variablen und Aliase können nicht ausgeblendet werden, da Sie keinen aufrufsoperator oder einen qualifizierten Namen verwenden können, um Sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7c59d-184">Variables and aliases cannot be hidden because you cannot use a call operator or a qualified name to run them.</span></span> <span data-ttu-id="7c59d-185">Wenn Sie Variablen und Aliase aus einem Modul oder Snap-in importieren, werden die Variablen in der Sitzung durch denselben Namen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="7c59d-185">When you import variables and aliases from a module or snap-in, they replace variables in the session with the same name.</span></span>

### <a name="avoiding-name-conflicts"></a><span data-ttu-id="7c59d-186">Vermeiden von Namenskonflikten</span><span class="sxs-lookup"><span data-stu-id="7c59d-186">Avoiding name conflicts</span></span>

<span data-ttu-id="7c59d-187">Die beste Möglichkeit zum Verwalten von Befehlsnamen Konflikten besteht darin, Sie zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="7c59d-187">The best way to manage command name conflicts is to prevent them.</span></span> <span data-ttu-id="7c59d-188">Wenn Sie die Befehle benennen, verwenden Sie einen eindeutigen Namen.</span><span class="sxs-lookup"><span data-stu-id="7c59d-188">When you name your commands, use a unique name.</span></span> <span data-ttu-id="7c59d-189">Fügen Sie z. b. die Initialen oder das Akronym Ihres Firmennamens den Substantiven in ihren Befehlen hinzu.</span><span class="sxs-lookup"><span data-stu-id="7c59d-189">For example, add your initials or company name acronym to the nouns in your commands.</span></span>

<span data-ttu-id="7c59d-190">Wenn Sie Befehle aus einem PowerShell-Modul oder einer anderen Sitzung in die Sitzung importieren, verwenden Sie außerdem den- `Prefix` Parameter von [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) oder</span><span class="sxs-lookup"><span data-stu-id="7c59d-190">Also, when you import commands into your session from a PowerShell module or from another session, use the `Prefix` parameter of the [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) or</span></span>

<span data-ttu-id="7c59d-191">[Import-PSSession-](xref:Microsoft.PowerShell.Utility.Import-PSSession) Cmdlet, um den Substantiven in den Namen der Befehle ein Präfix hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7c59d-191">[Import-PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession) cmdlet to add a prefix to the nouns in the names of commands.</span></span>

<span data-ttu-id="7c59d-192">Beispielsweise werden mit dem folgenden Befehl Konflikte mit dem `Get-Date` - `Set-Date` Cmdlet und dem-Cmdlet vermieden, die in PowerShell enthalten sind, wenn Sie das `DateFunctions` Modul importieren.</span><span class="sxs-lookup"><span data-stu-id="7c59d-192">For example, the following command avoids any conflict with the `Get-Date` and `Set-Date` cmdlets that come with PowerShell when you import the `DateFunctions` module.</span></span>

```powershell
Import-Module -Name DateFunctions -Prefix ZZ
```

<span data-ttu-id="7c59d-193">Weitere Informationen finden Sie `Import-Module` unter und weiter `Import-PSSession` unten.</span><span class="sxs-lookup"><span data-stu-id="7c59d-193">For more information, see `Import-Module` and `Import-PSSession` below.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c59d-194">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="7c59d-194">See also</span></span>

- [<span data-ttu-id="7c59d-195">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="7c59d-195">about_Path_Syntax</span></span>](about_Path_Syntax.md)
- [<span data-ttu-id="7c59d-196">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="7c59d-196">about_Aliases</span></span>](about_Aliases.md)
- [<span data-ttu-id="7c59d-197">about_Functions</span><span class="sxs-lookup"><span data-stu-id="7c59d-197">about_Functions</span></span>](about_Functions.md)
- [<span data-ttu-id="7c59d-198">Alias-Provider</span><span class="sxs-lookup"><span data-stu-id="7c59d-198">Alias-Provider</span></span>](../../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)
- [<span data-ttu-id="7c59d-199">Function-Provider</span><span class="sxs-lookup"><span data-stu-id="7c59d-199">Function-Provider</span></span>](../../Microsoft.PowerShell.Core/About/about_Function_Provider.md)
- [<span data-ttu-id="7c59d-200">Get-Command</span><span class="sxs-lookup"><span data-stu-id="7c59d-200">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)
- [<span data-ttu-id="7c59d-201">Import-Module</span><span class="sxs-lookup"><span data-stu-id="7c59d-201">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)
- [<span data-ttu-id="7c59d-202">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="7c59d-202">Import-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Import-PSSession)

