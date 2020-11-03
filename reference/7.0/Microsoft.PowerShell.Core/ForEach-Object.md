---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 8257f1fba2d4367e61121d4876a51197f710da41
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "93219884"
---
# <span data-ttu-id="169ad-103">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="169ad-103">ForEach-Object</span></span>

## <span data-ttu-id="169ad-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="169ad-104">Synopsis</span></span>
<span data-ttu-id="169ad-105">Führt einen Vorgang für jedes Element in einer Auflistung von Eingabeobjekten aus.</span><span class="sxs-lookup"><span data-stu-id="169ad-105">Performs an operation against each item in a collection of input objects.</span></span>

## <span data-ttu-id="169ad-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="169ad-106">Syntax</span></span>

### <span data-ttu-id="169ad-107">Scriptblockset (Standard)</span><span class="sxs-lookup"><span data-stu-id="169ad-107">ScriptBlockSet (Default)</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="169ad-108">Propertyandmethodset</span><span class="sxs-lookup"><span data-stu-id="169ad-108">PropertyAndMethodSet</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="169ad-109">Parallelparameterset</span><span class="sxs-lookup"><span data-stu-id="169ad-109">ParallelParameterSet</span></span>

```
ForEach-Object [-InputObject <PSObject>] -Parallel <ScriptBlock> [-ThrottleLimit <Int32>]
 [-TimeoutSeconds <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="169ad-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="169ad-110">Description</span></span>

<span data-ttu-id="169ad-111">Das- `ForEach-Object` Cmdlet führt einen Vorgang für jedes Element in einer Auflistung von Eingabe Objekten aus.</span><span class="sxs-lookup"><span data-stu-id="169ad-111">The `ForEach-Object` cmdlet performs an operation on each item in a collection of input objects.</span></span> <span data-ttu-id="169ad-112">Die Eingabe Objekte können an das Cmdlet weitergeleitet oder mithilfe des **Inputobject** -Parameters angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-112">The input objects can be piped to the cmdlet or specified by using the **InputObject** parameter.</span></span>

<span data-ttu-id="169ad-113">Ab Windows PowerShell 3,0 gibt es zwei verschiedene Möglichkeiten, einen Befehl zu erstellen `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="169ad-113">Starting in Windows PowerShell 3.0, there are two different ways to construct a `ForEach-Object` command.</span></span>

- <span data-ttu-id="169ad-114">**Skriptblock**.</span><span class="sxs-lookup"><span data-stu-id="169ad-114">**Script block**.</span></span> <span data-ttu-id="169ad-115">Sie können einen Skriptblock verwenden, um den Vorgang anzugeben.</span><span class="sxs-lookup"><span data-stu-id="169ad-115">You can use a script block to specify the operation.</span></span> <span data-ttu-id="169ad-116">Verwenden Sie innerhalb des Skript Blocks die- `$_` Variable, um das aktuelle-Objekt darzustellen.</span><span class="sxs-lookup"><span data-stu-id="169ad-116">Within the script block, use the `$_` variable to represent the current object.</span></span> <span data-ttu-id="169ad-117">Der Skriptblock ist der Wert des **Process** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="169ad-117">The script block is the value of the **Process** parameter.</span></span> <span data-ttu-id="169ad-118">Der Skriptblock kann beliebige PowerShell-Skripts enthalten.</span><span class="sxs-lookup"><span data-stu-id="169ad-118">The script block can contain any PowerShell script.</span></span>

  <span data-ttu-id="169ad-119">Der folgende Befehl ruft beispielsweise den Wert der **ProcessName** -Eigenschaft der einzelnen Prozesse auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="169ad-119">For example, the following command gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object {$_.ProcessName}`

  <span data-ttu-id="169ad-120">`ForEach-Object` unterstützt `begin` die `process` Blöcke, und, `end` wie in [about_functions](about/about_functions.md#piping-objects-to-functions)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="169ad-120">`ForEach-Object` supports the `begin`, `process`, and `end` blocks as described in [about_functions](about/about_functions.md#piping-objects-to-functions).</span></span>

  > [!NOTE]
  > <span data-ttu-id="169ad-121">Die Skriptblöcke werden im Gültigkeitsbereich des Aufrufers ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-121">The script blocks run in the caller's scope.</span></span> <span data-ttu-id="169ad-122">Daher haben die Blöcke Zugriff auf Variablen in diesem Bereich und können neue Variablen erstellen, die in diesem Bereich beibehalten werden, nachdem das Cmdlet abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="169ad-122">Therefore the blocks have access to variables in that scope and can create new variables that persist in that scope after the cmdlet completes.</span></span>

- <span data-ttu-id="169ad-123">**Operation-Anweisung**.</span><span class="sxs-lookup"><span data-stu-id="169ad-123">**Operation statement**.</span></span> <span data-ttu-id="169ad-124">Sie können auch eine Vorgangs Anweisung schreiben, die in natürlicher Sprache sehr viel ähnlicher ist.</span><span class="sxs-lookup"><span data-stu-id="169ad-124">You can also write an operation statement, which is much more like natural language.</span></span> <span data-ttu-id="169ad-125">Sie können die Vorgangsanweisung verwenden, um einen Eigenschaftenwert anzugeben oder eine Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="169ad-125">You can use the operation statement to specify a property value or call a method.</span></span> <span data-ttu-id="169ad-126">Vorgangsanweisungen wurden in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-126">Operation statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="169ad-127">Der folgende Befehl ruft beispielsweise ebenfalls den Wert der **ProcessName** -Eigenschaft der einzelnen Prozesse auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="169ad-127">For example, the following command also gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object ProcessName`

- <span data-ttu-id="169ad-128">**Parallel ausgeführten Skriptblock**.</span><span class="sxs-lookup"><span data-stu-id="169ad-128">**Parallel running script block**.</span></span> <span data-ttu-id="169ad-129">Ab PowerShell 7,0 ist ein Dritter Parametersatz verfügbar, der jeden Skriptblock parallel ausführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-129">Beginning with PowerShell 7.0, a third parameter set is available that runs each script block in parallel.</span></span> <span data-ttu-id="169ad-130">Der **throttlelimit** -Parameter schränkt die Anzahl paralleler Skripts ein, die gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-130">The **ThrottleLimit** parameter limits the number of parallel scripts running at a time.</span></span> <span data-ttu-id="169ad-131">Verwenden Sie wie zuvor die- `$_` Variable, um das aktuelle Eingabe Objekt im Skriptblock darzustellen.</span><span class="sxs-lookup"><span data-stu-id="169ad-131">As before, use the `$_` variable to represent the current input object in the script block.</span></span> <span data-ttu-id="169ad-132">Verwenden Sie das- `$using:` Schlüsselwort, um Variablen Verweise an das laufende Skript zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="169ad-132">Use the `$using:` keyword to pass variable references to the running script.</span></span>

  <span data-ttu-id="169ad-133">In PowerShell 7 wird ein neuer Runspace für jede Schleifen Iteration erstellt, um eine maximale Isolation sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="169ad-133">In PowerShell 7, a new runspace is created for each loop iteration to ensure maximum isolation.</span></span>
  <span data-ttu-id="169ad-134">Dabei kann es sich um eine große Leistung und einen Ressourcen Treffer handeln, wenn die Arbeit, die Sie ausführen, im Vergleich zum Erstellen neuer Runspaces gering ist, oder wenn viele Iterationen eine bedeutende Arbeit ausführen.</span><span class="sxs-lookup"><span data-stu-id="169ad-134">This can be a large performance and resource hit if the work you are doing is small compared to creating new runspaces or if there are a lot of iterations performing significant work.</span></span>

  <span data-ttu-id="169ad-135">Standardmäßig verwenden die parallelen Scriptblocks das aktuelle Arbeitsverzeichnis des Aufrufers, der die parallelen Aufgaben gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="169ad-135">By default, the parallel scriptblocks use the current working directory of the caller that started the parallel tasks.</span></span>

  <span data-ttu-id="169ad-136">Fehler ohne Abbruch werden in den Cmdlet-Fehler Datenstrom geschrieben, da Sie in parallel ausgeführten Scriptblocks auftreten.</span><span class="sxs-lookup"><span data-stu-id="169ad-136">Non-terminating errors are written to the cmdlet error stream as they occur in parallel running scriptblocks.</span></span> <span data-ttu-id="169ad-137">Da die Ausführungsreihenfolge paralleler Scriptblocks nicht bestimmt werden kann, ist die Reihenfolge, in der Fehler im Fehler Datenstrom angezeigt werden, zufällig.</span><span class="sxs-lookup"><span data-stu-id="169ad-137">Because parallel scriptblock execution order cannot be determined, the order in which errors appear in the error stream is random.</span></span> <span data-ttu-id="169ad-138">Ebenso werden Nachrichten, die in andere Datenströme wie Warnung, ausführlich oder Informationen geschrieben werden, in einer unbestimmten Reihenfolge in diese Datenströme geschrieben.</span><span class="sxs-lookup"><span data-stu-id="169ad-138">Likewise, messages written to other data streams, like warning, verbose, or information are written to those data streams in an indeterminate order.</span></span>

  <span data-ttu-id="169ad-139">Beim Beenden von Fehlern, z. b. Ausnahmen, wird die einzelne parallele Instanz der Scriptblocks beendet, in denen Sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="169ad-139">Terminating errors, such as exceptions, terminate the individual parallel instance of the scriptblocks in which they occur.</span></span> <span data-ttu-id="169ad-140">Ein Beendigungs Fehler in einem Scriptblocks führt möglicherweise nicht zum Beenden des `Foreach-Object` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="169ad-140">A terminating error in one scriptblocks may not cause the termination of the `Foreach-Object` cmdlet.</span></span> <span data-ttu-id="169ad-141">Die anderen Skriptblöcke, die parallel ausgeführt werden, werden weiterhin ausgeführt, es sei denn, Sie stoßen auch auf einen Beendigungs Fehler.</span><span class="sxs-lookup"><span data-stu-id="169ad-141">The other scriptblocks, running in parallel, continue to run unless they also encounter a terminating error.</span></span> <span data-ttu-id="169ad-142">Der Abbruch Fehler wird in den Fehler Datenstrom als **ErrorRecord** mit der **fullyqualifiederrorid** von geschrieben `PSTaskException` .</span><span class="sxs-lookup"><span data-stu-id="169ad-142">The terminating error is written to the error data stream as an **ErrorRecord** with a **FullyQualifiedErrorId** of `PSTaskException`.</span></span>
  <span data-ttu-id="169ad-143">Fehler beim Beenden können mithilfe von PowerShell-try/catch-oder Trap-Blöcken in Fehler ohne Abbruch konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-143">Terminating errors can be converted to non-terminating errors using PowerShell try/catch or trap blocks.</span></span>

## <span data-ttu-id="169ad-144">Beispiele</span><span class="sxs-lookup"><span data-stu-id="169ad-144">Examples</span></span>

### <span data-ttu-id="169ad-145">Beispiel 1: Teilen von ganzen Zahlen in einem Array</span><span class="sxs-lookup"><span data-stu-id="169ad-145">Example 1: Divide integers in an array</span></span>

<span data-ttu-id="169ad-146">In diesem Beispiel wird ein Array von drei ganzen Zahlen angenommen, und jedes dieser Elemente wird durch 1024 dividiert.</span><span class="sxs-lookup"><span data-stu-id="169ad-146">This example takes an array of three integers and divides each one of them by 1024.</span></span>

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### <span data-ttu-id="169ad-147">Beispiel 2: erhalten der Länge aller Dateien in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="169ad-147">Example 2: Get the length of all the files in a directory</span></span>

<span data-ttu-id="169ad-148">In diesem Beispiel werden die Dateien und Verzeichnisse im PowerShell-Installationsverzeichnis verarbeitet `$PSHOME` .</span><span class="sxs-lookup"><span data-stu-id="169ad-148">This example processes the files and directories in the PowerShell installation directory `$PSHOME`.</span></span>

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

<span data-ttu-id="169ad-149">Wenn das Objekt kein Verzeichnis ist, ruft der Skriptblock den Namen der Datei ab, teilt den Wert der **length** -Eigenschaft durch 1024 und fügt ein Leerzeichen ("") hinzu, um es vom nächsten Eintrag zu trennen.</span><span class="sxs-lookup"><span data-stu-id="169ad-149">If the object is not a directory, the script block gets the name of the file, divides the value of its **Length** property by 1024, and adds a space (" ") to separate it from the next entry.</span></span> <span data-ttu-id="169ad-150">Mit dem-Cmdlet wird die **psiscontainer** -Eigenschaft verwendet, um zu bestimmen, ob ein Objekt ein Verzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="169ad-150">The cmdlet uses the **PSISContainer** property to determine whether an object is a directory.</span></span>

### <span data-ttu-id="169ad-151">Beispiel 3: Arbeiten mit den neuesten System Ereignissen</span><span class="sxs-lookup"><span data-stu-id="169ad-151">Example 3: Operate on the most recent System events</span></span>

<span data-ttu-id="169ad-152">In diesem Beispiel werden die 1000 aktuellsten Ereignisse aus dem System Ereignisprotokoll in eine Textdatei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="169ad-152">This example writes the 1000 most recent events from the System event log to a text file.</span></span> <span data-ttu-id="169ad-153">Die aktuelle Zeit wird vor und nach der Verarbeitung der Ereignisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="169ad-153">The current time is displayed before and after processing the events.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

<span data-ttu-id="169ad-154">`Get-EventLog` Ruft die 1000 aktuellsten Ereignisse aus dem System Ereignisprotokoll ab und speichert Sie in der `$Events` Variablen.</span><span class="sxs-lookup"><span data-stu-id="169ad-154">`Get-EventLog` gets the 1000 most recent events from the System event log and stores them in the `$Events` variable.</span></span> <span data-ttu-id="169ad-155">`$Events` wird dann an das `ForEach-Object` Cmdlet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="169ad-155">`$Events` is then piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="169ad-156">Der **Begin** -Parameter zeigt das aktuelle Datum und die Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="169ad-156">The **Begin** parameter displays the current date and time.</span></span> <span data-ttu-id="169ad-157">Als Nächstes verwendet der **Process** -Parameter das `Out-File` -Cmdlet, um eine Textdatei mit dem Namen events.txt zu erstellen, und speichert die Message-Eigenschaft der einzelnen Ereignisse in dieser Datei.</span><span class="sxs-lookup"><span data-stu-id="169ad-157">Next, the **Process** parameter uses the `Out-File` cmdlet to create a text file that is named events.txt and stores the message property of each of the events in that file.</span></span> <span data-ttu-id="169ad-158">Schließlich wird der **End** -Parameter verwendet, um das Datum und die Uhrzeit anzuzeigen, zu denen die gesamte Verarbeitung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="169ad-158">Last, the **End** parameter is used to display the date and time after all of the processing has completed.</span></span>

### <span data-ttu-id="169ad-159">Beispiel 4: Ändern des Werts eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="169ad-159">Example 4: Change the value of a Registry key</span></span>

<span data-ttu-id="169ad-160">In diesem Beispiel wird der Wert des **remotePath** -Registrierungs Eintrags in allen unter Schlüsseln unter dem `HKCU:\Network` Schlüssel in Großbuchstaben geändert.</span><span class="sxs-lookup"><span data-stu-id="169ad-160">This example changes the value of the **RemotePath** registry entry in all of the subkeys under the `HKCU:\Network` key to uppercase text.</span></span>

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

<span data-ttu-id="169ad-161">Sie können dieses Format verwenden,um die Form oder den Inhalt eines Registrierungseintragswerts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="169ad-161">You can use this format to change the form or content of a registry entry value.</span></span>

<span data-ttu-id="169ad-162">Jeder Unterschlüssel im **Netzwerk** Schlüssel stellt ein zugeordnetes Netzwerklaufwerk dar, das bei der Anmeldung erneut eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="169ad-162">Each subkey in the **Network** key represents a mapped network drive that reconnects at sign on.</span></span> <span data-ttu-id="169ad-163">Der **RemotePath** -Eintrag enthält den UNC-Pfad des verbundenen Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="169ad-163">The **RemotePath** entry contains the UNC path of the connected drive.</span></span> <span data-ttu-id="169ad-164">Wenn Sie z. b. das Laufwerk e: zu zuordnen `\\Server\Share` , wird ein **e** -Unterschlüssel in erstellt, `HKCU:\Network` wobei der Registrierungs Wert **remotePath** auf festgelegt ist `\\Server\Share` .</span><span class="sxs-lookup"><span data-stu-id="169ad-164">For example, if you map the E: drive to `\\Server\Share`, an **E** subkey is created in `HKCU:\Network` with the **RemotePath** registry value set to `\\Server\Share`.</span></span>

<span data-ttu-id="169ad-165">Der Befehl verwendet das `Get-ItemProperty` Cmdlet, um alle untergeordneten Schlüssel des **Netzwerk** Schlüssels zu erhalten, und das `Set-ItemProperty` Cmdlet, um den Wert des **remotePath** -Registrierungs Eintrags in jedem Schlüssel zu ändern.</span><span class="sxs-lookup"><span data-stu-id="169ad-165">The command uses the `Get-ItemProperty` cmdlet to get all of the subkeys of the **Network** key and the `Set-ItemProperty` cmdlet to change the value of the **RemotePath** registry entry in each key.</span></span>
<span data-ttu-id="169ad-166">Im- `Set-ItemProperty` Befehl ist der Pfad der Wert der **pspath** -Eigenschaft des Registrierungsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="169ad-166">In the `Set-ItemProperty` command, the path is the value of the **PSPath** property of the registry key.</span></span> <span data-ttu-id="169ad-167">Dies ist eine Eigenschaft des Microsoft .NET Framework-Objekts, das den Registrierungsschlüssel darstellt, nicht einen Registrierungs Eintrag.</span><span class="sxs-lookup"><span data-stu-id="169ad-167">This is a property of the Microsoft .NET Framework object that represents the registry key, not a registry entry.</span></span> <span data-ttu-id="169ad-168">Der Befehl verwendet die **touppermethode ()** des **remotePath** -Werts, bei der es sich um eine Zeichenfolge (REG_SZ) handelt.</span><span class="sxs-lookup"><span data-stu-id="169ad-168">The command uses the **ToUpper()** method of the **RemotePath** value, which is a string (REG_SZ).</span></span>

<span data-ttu-id="169ad-169">Da `Set-ItemProperty` die-Eigenschaft jedes Schlüssels ändert, ist das `ForEach-Object` Cmdlet für den Zugriff auf die-Eigenschaft erforderlich.</span><span class="sxs-lookup"><span data-stu-id="169ad-169">Because `Set-ItemProperty` is changing the property of each key, the `ForEach-Object` cmdlet is required to access the property.</span></span>

### <span data-ttu-id="169ad-170">Beispiel 5: Verwenden der automatischen $NULL Variablen</span><span class="sxs-lookup"><span data-stu-id="169ad-170">Example 5: Use the $Null automatic variable</span></span>

<span data-ttu-id="169ad-171">In diesem Beispiel wird gezeigt, wie die `$Null` Automatische Variable an das `ForEach-Object` Cmdlet weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="169ad-171">This example shows the effect of piping the `$Null` automatic variable to the `ForEach-Object` cmdlet.</span></span>

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

<span data-ttu-id="169ad-172">Da PowerShell NULL als expliziten Platzhalter behandelt, `ForEach-Object` generiert das Cmdlet einen Wert für `$Null` , genau wie bei anderen Objekten, die an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="169ad-172">Because PowerShell treats null as an explicit placeholder, the `ForEach-Object` cmdlet generates a value for `$Null`, just as it does for other objects that you pipe to it.</span></span>

### <span data-ttu-id="169ad-173">Beispiel 6: erhalten von Eigenschafts Werten</span><span class="sxs-lookup"><span data-stu-id="169ad-173">Example 6: Get property values</span></span>

<span data-ttu-id="169ad-174">In diesem Beispiel wird der Wert der **path** -Eigenschaft aller installierten PowerShell-Module mithilfe des **Mitgliedschafts Namen** -Parameters des `ForEach-Object` Cmdlets abgerufen.</span><span class="sxs-lookup"><span data-stu-id="169ad-174">This example gets the value of the **Path** property of all installed PowerShell modules by using the **MemberName** parameter of the `ForEach-Object` cmdlet.</span></span>

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

<span data-ttu-id="169ad-175">Der zweite Befehl entspricht dem ersten.</span><span class="sxs-lookup"><span data-stu-id="169ad-175">The second command is equivalent to the first.</span></span> <span data-ttu-id="169ad-176">Er verwendet den `Foreach` Alias des `ForEach-Object` Cmdlets und lässt den Namen des **Mitgliedsnamen** -Parameters aus, der optional ist.</span><span class="sxs-lookup"><span data-stu-id="169ad-176">It uses the `Foreach` alias of the `ForEach-Object` cmdlet and omits the name of the **MemberName** parameter, which is optional.</span></span>

<span data-ttu-id="169ad-177">Das- `ForEach-Object` Cmdlet ist nützlich zum Abrufen von Eigenschafts Werten, da es den Wert abruft, ohne den Typ zu ändern, im Gegensatz zu den **Format** -Cmdlets oder dem `Select-Object` Cmdlet, die den Eigenschafts Werttyp ändern.</span><span class="sxs-lookup"><span data-stu-id="169ad-177">The `ForEach-Object` cmdlet is useful for getting property values, because it gets the value without changing the type, unlike the **Format** cmdlets or the `Select-Object` cmdlet, which change the property value type.</span></span>

### <span data-ttu-id="169ad-178">Beispiel 7: Aufteilen von Modulnamen in Komponentennamen</span><span class="sxs-lookup"><span data-stu-id="169ad-178">Example 7: Split module names into component names</span></span>

<span data-ttu-id="169ad-179">Dieses Beispiel zeigt drei Möglichkeiten, zwei durch Punkte getrennte Modulnamen in Ihre Komponentennamen aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="169ad-179">This example shows three ways to split two dot-separated module names into their component names.</span></span>

```powershell
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object {$_.Split(".")}
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object -MemberName Split -ArgumentList "."
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | Foreach Split "."
```

```Output
Microsoft
PowerShell
Core
Microsoft
PowerShell
Host
```

<span data-ttu-id="169ad-180">Die Befehle rufen die **Split** Methode von Zeichenfolgen auf.</span><span class="sxs-lookup"><span data-stu-id="169ad-180">The commands call the **Split** method of strings.</span></span> <span data-ttu-id="169ad-181">Die drei Befehle verwenden unterschiedliche Syntax, sind aber äquivalent und austauschbar.</span><span class="sxs-lookup"><span data-stu-id="169ad-181">The three commands use different syntax, but they are equivalent and interchangeable.</span></span>

<span data-ttu-id="169ad-182">Der erste Befehl verwendet die herkömmliche Syntax, die einen Skriptblock und den aktuellen Objekt Operator enthält `$_` .</span><span class="sxs-lookup"><span data-stu-id="169ad-182">The first command uses the traditional syntax, which includes a script block and the current object operator `$_`.</span></span> <span data-ttu-id="169ad-183">Es verwendet die Punktsyntax zum Angeben der Methode und die Klammern, um das Trennzeichenargument einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="169ad-183">It uses the dot syntax to specify the method and parentheses to enclose the delimiter argument.</span></span>

<span data-ttu-id="169ad-184">Der zweite Befehl verwendet den **MemberName** -Parameter, um die **Split** -Methode anzugeben,und den **ArgumentName** -Parameter, um den Punkt („.“) als das Teilungstrennzeichen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="169ad-184">The second command uses the **MemberName** parameter to specify the **Split** method and the **ArgumentName** parameter to identify the dot (".") as the split delimiter.</span></span>

<span data-ttu-id="169ad-185">Der dritte Befehl verwendet den **foreach** -Alias des `ForEach-Object` Cmdlets und lässt die Namen der Parameter " **Membership Name** " und "Argument **List** " aus, die optional sind.</span><span class="sxs-lookup"><span data-stu-id="169ad-185">The third command uses the **Foreach** alias of the `ForEach-Object` cmdlet and omits the names of the **MemberName** and **ArgumentList** parameters, which are optional.</span></span>

### <span data-ttu-id="169ad-186">Beispiel 8: Verwenden von ForEach-Object mit zwei Skript Blöcken</span><span class="sxs-lookup"><span data-stu-id="169ad-186">Example 8: Using ForEach-Object with two script blocks</span></span>

<span data-ttu-id="169ad-187">In diesem Beispiel übergeben wir zwei Skriptblöcke in der gleichen Weise.</span><span class="sxs-lookup"><span data-stu-id="169ad-187">In this example, we pass two script blocks positionally.</span></span> <span data-ttu-id="169ad-188">Alle Skriptblöcke werden an den **Prozess** Parameter gebunden.</span><span class="sxs-lookup"><span data-stu-id="169ad-188">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="169ad-189">Sie werden jedoch so behandelt, als würden Sie an den **Begin** -und den **Process** -Parameter übermittelt.</span><span class="sxs-lookup"><span data-stu-id="169ad-189">However, they are treated as if they had been passed to the **Begin** and **Process** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### <span data-ttu-id="169ad-190">Beispiel 9: Verwenden von ForEach-Object mit mehr als zwei Skript Blöcken</span><span class="sxs-lookup"><span data-stu-id="169ad-190">Example 9: Using ForEach-Object with more than two script blocks</span></span>

<span data-ttu-id="169ad-191">In diesem Beispiel übergeben wir zwei Skriptblöcke in der gleichen Weise.</span><span class="sxs-lookup"><span data-stu-id="169ad-191">In this example, we pass two script blocks positionally.</span></span> <span data-ttu-id="169ad-192">Alle Skriptblöcke werden an den **Prozess** Parameter gebunden.</span><span class="sxs-lookup"><span data-stu-id="169ad-192">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="169ad-193">Sie werden jedoch so behandelt, als wären Sie an die **Begin** -, **Process** -und **End** -Parameter übergebenen.</span><span class="sxs-lookup"><span data-stu-id="169ad-193">However, they are treated as if they had been passed to the **Begin** , **Process** , and **End** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process A' }  { 'process B' }  { 'end' }
```

```Output
begin
process A
process B
process A
process B
end
```

> [!NOTE]
> <span data-ttu-id="169ad-194">Der erste Skriptblock wird immer dem Block zugeordnet `begin` , der letzte Block wird dem `end` Block zugeordnet, und die Blöcke dazwischen werden alle dem `process` Block zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="169ad-194">The first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

### <span data-ttu-id="169ad-195">Beispiel 10: Ausführen mehrerer Skriptblöcke für jedes Pipeline Element</span><span class="sxs-lookup"><span data-stu-id="169ad-195">Example 10: Run multiple script blocks for each pipeline item</span></span>

<span data-ttu-id="169ad-196">Wie im vorherigen Beispiel gezeigt, werden mehrere Skriptblöcke, die mit dem **Process** -Parameter übergeben wurden, den **Begin** -und **End** -Parametern zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="169ad-196">As shown in the previous example, multiple script blocks passed using the **Process** parameter get mapped to the **Begin** and **End** parameters.</span></span> <span data-ttu-id="169ad-197">Um diese Zuordnung zu vermeiden, müssen Sie explizite Werte für die **Begin** -und **End** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="169ad-197">To avoid this mapping, you must provide explicit values for the **Begin** and **End** parameters.</span></span>

```powershell
1..2 | ForEach-Object -Begin $null -Process { 'one' }, { 'two' }, { 'three' } -End $null
```

```Output
one
two
three
one
two
three
```

### <span data-ttu-id="169ad-198">Beispiel 11: Ausführen eines langsamen Skripts in parallelen Batches</span><span class="sxs-lookup"><span data-stu-id="169ad-198">Example 11: Run slow script in parallel batches</span></span>

<span data-ttu-id="169ad-199">In diesem Beispiel wird ein einfacher Skriptblock ausgeführt, der eine Zeichenfolge auswertet und eine Sekunde aufsperrt.</span><span class="sxs-lookup"><span data-stu-id="169ad-199">This example runs a simple script block that evaluates a string and sleeps for one second.</span></span>

```powershell
$Message = "Output:"

1..8 | ForEach-Object -Parallel {
    "$using:Message $_"
    Start-Sleep 1
} -ThrottleLimit 4
```

```Output
Output: 1
Output: 2
Output: 3
Output: 4
Output: 5
Output: 6
Output: 7
Output: 8
```

<span data-ttu-id="169ad-200">Der Wert des **throttlelimit** -Parameters ist auf 4 festgelegt, sodass die Eingabe in Batches von vier verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="169ad-200">The **ThrottleLimit** parameter value is set to 4 so that the input is processed in batches of four.</span></span>
<span data-ttu-id="169ad-201">Das- `$using:` Schlüsselwort wird verwendet, um die `$Message` Variable an jeden parallelen Skriptblock zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="169ad-201">The `$using:` keyword is used to pass the `$Message` variable into each parallel script block.</span></span>

### <span data-ttu-id="169ad-202">Beispiel 12: paralleles Abrufen von Protokoll Einträgen</span><span class="sxs-lookup"><span data-stu-id="169ad-202">Example 12: Retrieve log entries in parallel</span></span>

<span data-ttu-id="169ad-203">In diesem Beispiel werden 50.000-Protokolleinträge aus fünf Systemprotokollen auf einem lokalen Windows-Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="169ad-203">This example retrieves 50,000 log entries from 5 system logs on a local Windows machine.</span></span>

```powershell
$logNames = 'Security','Application','System','Windows PowerShell','Microsoft-Windows-Store/Operational'

$logEntries = $logNames | ForEach-Object -Parallel {
    Get-WinEvent -LogName $_ -MaxEvents 10000
} -ThrottleLimit 5

$logEntries.Count
```

```Output
50000
```

<span data-ttu-id="169ad-204">Der Parameter **Parallel** gibt den Skriptblock an, der für jeden Eingabeprotokollnamen parallel ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="169ad-204">The **Parallel** parameter specifies the script block that is run in parallel for each input log name.</span></span> <span data-ttu-id="169ad-205">Der **throttlelimit** -Parameter stellt sicher, dass alle fünf Skriptblöcke zur gleichen Zeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-205">The **ThrottleLimit** parameter ensures that all five script blocks run at the same time.</span></span>

### <span data-ttu-id="169ad-206">Beispiel 13: parallele Ausführen als Auftrag</span><span class="sxs-lookup"><span data-stu-id="169ad-206">Example 13: Run in parallel as a job</span></span>

<span data-ttu-id="169ad-207">In diesem Beispiel wird ein einfacher Skriptblock parallel ausgeführt, wobei jeweils zwei Hintergrund Aufträge erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-207">This example runs a simple script block in parallel, creating two background jobs at a time.</span></span>

```powershell
$job = 1..10 | ForEach-Object -Parallel {
    "Output: $_"
    Start-Sleep 1
} -ThrottleLimit 2 -AsJob

$job | Receive-Job -Wait
```

```Output
Output: 1
Output: 2
Output: 3
Output: 4
Output: 5
Output: 6
Output: 7
Output: 8
Output: 9
Output: 10
```

<span data-ttu-id="169ad-208">die- `$job` Variable empfängt das Auftrags Objekt, das Ausgabedaten sammelt und den ausgegebene Status überwacht.</span><span class="sxs-lookup"><span data-stu-id="169ad-208">the `$job` variable receives the job object that collects output data and monitors running state.</span></span>
<span data-ttu-id="169ad-209">Das Auftrags Objekt wird `Receive-Job` mit dem **Wait** -Schalter Parameter an weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="169ad-209">The job object is piped to `Receive-Job` with the **Wait** switch parameter.</span></span> <span data-ttu-id="169ad-210">Und damit wird die Ausgabe an die Konsole gestreamt, so als ob auch `ForEach-Object -Parallel` ohne **AsJob** ausgeführt würde.</span><span class="sxs-lookup"><span data-stu-id="169ad-210">And this streams output to the console, just as if `ForEach-Object -Parallel` was run without **AsJob**.</span></span>

### <span data-ttu-id="169ad-211">Beispiel 14: Verwenden von Verweisen auf Thread sichere Variablen</span><span class="sxs-lookup"><span data-stu-id="169ad-211">Example 14: Using thread safe variable references</span></span>

<span data-ttu-id="169ad-212">In diesem Beispiel werden Skriptblöcke parallel aufgerufen, um eindeutig benannte Prozess Objekte zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="169ad-212">This example invokes script blocks in parallel to collect uniquely named Process objects.</span></span>

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
Get-Process | ForEach-Object -Parallel {
    $dict = $using:threadSafeDictionary
    $dict.TryAdd($_.ProcessName, $_)
}

$threadSafeDictionary["pwsh"]
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     82    82.87     130.85      15.55    2808   2 pwsh
```

<span data-ttu-id="169ad-213">Eine einzelne Instanz eines **ConcurrentDictionary** -Objekts wird an jeden Skriptblock zum Erfassen der Objekte übermittelt.</span><span class="sxs-lookup"><span data-stu-id="169ad-213">A single instance of a **ConcurrentDictionary** object is passed to each script block to collect the objects.</span></span> <span data-ttu-id="169ad-214">Da das **ConcurrentDictionary** Thread sicher ist, kann es sicher von jedem parallelen Skript geändert werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-214">Since the **ConcurrentDictionary** is thread safe, it is safe to be modified by each parallel script.</span></span> <span data-ttu-id="169ad-215">Ein nicht Thread sicheres Objekt, wie z. b **. System. Collections. Generic. Dictionary** , kann hier nicht sicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-215">A non-thread-safe object, such as **System.Collections.Generic.Dictionary** , would not be safe to use here.</span></span>

> [!NOTE]
> <span data-ttu-id="169ad-216">Dieses Beispiel ist eine sehr ineffiziente Verwendung des **parallelen** Parameters.</span><span class="sxs-lookup"><span data-stu-id="169ad-216">This example is a very inefficient use of **Parallel** parameter.</span></span> <span data-ttu-id="169ad-217">Das Skript fügt das Eingabe Objekt einfach einem gleichzeitigen Wörterbuch Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="169ad-217">The script simply adds the input object to a concurrent dictionary object.</span></span> <span data-ttu-id="169ad-218">Der Aufwand für das Aufrufen der einzelnen Skripts in einem separaten Thread ist trivial.</span><span class="sxs-lookup"><span data-stu-id="169ad-218">It is trivial and not worth the overhead of invoking each script in a separate thread.</span></span> <span data-ttu-id="169ad-219">Die normale Ausführung `ForEach-Object` ohne den **parallelen** Switch ist viel effizienter und schneller.</span><span class="sxs-lookup"><span data-stu-id="169ad-219">Running `ForEach-Object` normally without the **Parallel** switch is much more efficient and faster.</span></span> <span data-ttu-id="169ad-220">Dieses Beispiel soll lediglich veranschaulichen, wie Thread sichere Variablen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-220">This example is only intended to demonstrate how to use thread safe variables.</span></span>

### <span data-ttu-id="169ad-221">Beispiel 15: Schreiben von Fehlern mit paralleler Ausführung</span><span class="sxs-lookup"><span data-stu-id="169ad-221">Example 15: Writing errors with parallel execution</span></span>

<span data-ttu-id="169ad-222">In diesem Beispiel wird parallel in den Fehler Datenstrom geschrieben, wobei die Reihenfolge der geschriebenen Fehler zufällig ist.</span><span class="sxs-lookup"><span data-stu-id="169ad-222">This example writes to the error stream in parallel, where the order of written errors is random.</span></span>

```powershell
1..3 | ForEach-Object -Parallel {
    Write-Error "Error: $_"
}
```

```Output
Write-Error: Error: 1
Write-Error: Error: 3
Write-Error: Error: 2
```

### <span data-ttu-id="169ad-223">Beispiel 16: Beenden von Fehlern bei der parallelen Ausführung</span><span class="sxs-lookup"><span data-stu-id="169ad-223">Example 16: Terminating errors in parallel execution</span></span>

<span data-ttu-id="169ad-224">In diesem Beispiel wird ein Beendigungs Fehler in einem parallel ausgeführten ScriptBlock veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="169ad-224">This example demonstrates a terminating error in one parallel running scriptblock.</span></span>

```powershell
1..5 | ForEach-Object -Parallel {
    if ($_ -eq 3)
    {
        throw "Terminating Error: $_"
    }

    Write-Output "Output: $_"
}
```

```Output
Exception: Terminating Error: 3
Output: 1
Output: 4
Output: 2
Output: 5
```

<span data-ttu-id="169ad-225">`Output: 3` wird nie geschrieben, da der parallele ScriptBlock für diese Iterationen beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="169ad-225">`Output: 3` is never written because the parallel scriptblock for that iteration was terminated.</span></span>

## <span data-ttu-id="169ad-226">Parameter</span><span class="sxs-lookup"><span data-stu-id="169ad-226">Parameters</span></span>

### <span data-ttu-id="169ad-227">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="169ad-227">-ArgumentList</span></span>

<span data-ttu-id="169ad-228">Gibt ein Array von Argumenten für einen Methoden aufzurufenden an.</span><span class="sxs-lookup"><span data-stu-id="169ad-228">Specifies an array of arguments to a method call.</span></span> <span data-ttu-id="169ad-229">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="169ad-229">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="169ad-230">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-230">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: PropertyAndMethodSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="169ad-231">-BEGIN</span><span class="sxs-lookup"><span data-stu-id="169ad-231">-Begin</span></span>

<span data-ttu-id="169ad-232">Gibt einen Skriptblock an, der ausgeführt wird, bevor dieses Cmdlet Eingabe Objekte verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="169ad-232">Specifies a script block that runs before this cmdlet processes any input objects.</span></span> <span data-ttu-id="169ad-233">Dieser Skriptblock wird nur einmal für die gesamte Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-233">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="169ad-234">Weitere Informationen zum- `begin` Block finden Sie unter [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="169ad-234">For more information about the `begin` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="169ad-235">-Ende</span><span class="sxs-lookup"><span data-stu-id="169ad-235">-End</span></span>

<span data-ttu-id="169ad-236">Gibt einen Skriptblock an, der ausgeführt wird, nachdem dieses Cmdlet alle Eingabe Objekte verarbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="169ad-236">Specifies a script block that runs after this cmdlet processes all input objects.</span></span> <span data-ttu-id="169ad-237">Dieser Skriptblock wird nur einmal für die gesamte Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-237">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="169ad-238">Weitere Informationen zum- `end` Block finden Sie unter [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="169ad-238">For more information about the `end` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="169ad-239">-InputObject</span><span class="sxs-lookup"><span data-stu-id="169ad-239">-InputObject</span></span>

<span data-ttu-id="169ad-240">Gibt die Eingabeobjekte an.</span><span class="sxs-lookup"><span data-stu-id="169ad-240">Specifies the input objects.</span></span> <span data-ttu-id="169ad-241">`ForEach-Object` führt den Skriptblock oder die Vorgangs Anweisung für jedes Eingabe Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="169ad-241">`ForEach-Object` runs the script block or operation statement on each input object.</span></span> <span data-ttu-id="169ad-242">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-242">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="169ad-243">Wenn Sie den **Inputobject** -Parameter mit verwenden `ForEach-Object` , anstatt Befehls Ergebnisse an zu übergeben `ForEach-Object` , wird der **Inputobject** -Wert als einzelnes Objekt behandelt.</span><span class="sxs-lookup"><span data-stu-id="169ad-243">When you use the **InputObject** parameter with `ForEach-Object`, instead of piping command results to `ForEach-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="169ad-244">Dies gilt auch, wenn der Wert eine Auflistung ist, die das Ergebnis eines Befehls ist, z `-InputObject (Get-Process)` . b..</span><span class="sxs-lookup"><span data-stu-id="169ad-244">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span>
<span data-ttu-id="169ad-245">Da **Inputobject** keine einzelnen Eigenschaften aus einem Array oder einer Auflistung von Objekten zurückgeben kann, empfiehlt es sich, wenn Sie verwenden, `ForEach-Object` um Vorgänge für eine Auflistung von Objekten für Objekte mit spezifischen Werten in definierten Eigenschaften auszuführen, `ForEach-Object` wie in den Beispielen in diesem Thema gezeigt.</span><span class="sxs-lookup"><span data-stu-id="169ad-245">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that if you use `ForEach-Object` to perform operations on a collection of objects for those objects that have specific values in defined properties, you use `ForEach-Object` in the pipeline, as shown in the examples in this topic.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="169ad-246">-Mitgliedsname</span><span class="sxs-lookup"><span data-stu-id="169ad-246">-MemberName</span></span>

<span data-ttu-id="169ad-247">Gibt die abzurufende Eigenschaft oder die aufzurufende Methode an.</span><span class="sxs-lookup"><span data-stu-id="169ad-247">Specifies the property to get or the method to call.</span></span>

<span data-ttu-id="169ad-248">Platzhalter Zeichen sind zulässig, funktionieren jedoch nur, wenn die resultierende Zeichenfolge in einen eindeutigen Wert aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="169ad-248">Wildcard characters are permitted, but work only if the resulting string resolves to a unique value.</span></span>
<span data-ttu-id="169ad-249">Wenn Sie z. b `Get-Process | ForEach -MemberName *Name` . ausführen, stimmt das Platzhalter Muster mit mehr als einem Member überein, wodurch der Befehl fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="169ad-249">For example, if you run `Get-Process | ForEach -MemberName *Name`, the wildcard pattern matches more than one member causing the command to fail.</span></span>

<span data-ttu-id="169ad-250">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-250">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: PropertyAndMethodSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="169ad-251">-Prozess</span><span class="sxs-lookup"><span data-stu-id="169ad-251">-Process</span></span>

<span data-ttu-id="169ad-252">Gibt den Vorgang an, der für jedes Eingabeobjekt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="169ad-252">Specifies the operation that is performed on each input object.</span></span> <span data-ttu-id="169ad-253">Dieser Skriptblock wird für jedes Objekt in der Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-253">This script block is run for every object in the pipeline.</span></span> <span data-ttu-id="169ad-254">Weitere Informationen zum- `process` Block finden Sie unter [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="169ad-254">For more information about the `process` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

<span data-ttu-id="169ad-255">Wenn Sie dem **Prozess** Parameter mehrere Skriptblöcke bereitstellen, wird der erste Skriptblock immer dem Block zugeordnet `begin` .</span><span class="sxs-lookup"><span data-stu-id="169ad-255">When you provide multiple script blocks to the **Process** parameter, the first script block is always mapped to the `begin` block.</span></span> <span data-ttu-id="169ad-256">Wenn nur zwei Skriptblöcke vorhanden sind, wird der zweite Block dem Block zugeordnet `process` .</span><span class="sxs-lookup"><span data-stu-id="169ad-256">If there are only two script blocks, the second block is mapped to the `process` block.</span></span> <span data-ttu-id="169ad-257">Wenn es drei oder mehr Skriptblöcke gibt, wird der erste Skriptblock immer dem `begin` Block zugeordnet, der letzte Block wird dem Block zugeordnet `end` , und die Blöcke dazwischen werden alle dem `process` Block zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="169ad-257">If there are three or more script blocks, first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="169ad-258">-Restingscripts</span><span class="sxs-lookup"><span data-stu-id="169ad-258">-RemainingScripts</span></span>

<span data-ttu-id="169ad-259">Gibt alle Skriptblöcke an, die nicht vom **Prozess** Parameter übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-259">Specifies all script blocks that are not taken by the **Process** parameter.</span></span>

<span data-ttu-id="169ad-260">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-260">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="169ad-261">-Parallel</span><span class="sxs-lookup"><span data-stu-id="169ad-261">-Parallel</span></span>

<span data-ttu-id="169ad-262">Gibt den Skriptblock an, der für die parallele Verarbeitung von Eingabe Objekten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="169ad-262">Specifies the script block to be used for parallel processing of input objects.</span></span> <span data-ttu-id="169ad-263">Geben Sie einen Skriptblock ein, der den Vorgang beschreibt.</span><span class="sxs-lookup"><span data-stu-id="169ad-263">Enter a script block that describes the operation.</span></span>

<span data-ttu-id="169ad-264">Dieser Parameter wurde in PowerShell 7,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-264">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ParallelParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="169ad-265">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="169ad-265">-ThrottleLimit</span></span>

<span data-ttu-id="169ad-266">Gibt an, wie viele Skriptblöcke parallel ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-266">Specifies the number of script blocks that in parallel.</span></span> <span data-ttu-id="169ad-267">Eingabe Objekte werden blockiert, bis die Anzahl der ausgefallenen Skriptblöcke unter den **throttlelimit** fällt.</span><span class="sxs-lookup"><span data-stu-id="169ad-267">Input objects are blocked until the running script block count falls below the **ThrottleLimit**.</span></span> <span data-ttu-id="169ad-268">Der Standardwert ist `5`.</span><span class="sxs-lookup"><span data-stu-id="169ad-268">The default value is `5`.</span></span>

<span data-ttu-id="169ad-269">Dieser Parameter wurde in PowerShell 7,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-269">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="169ad-270">-TimeoutSeconds</span><span class="sxs-lookup"><span data-stu-id="169ad-270">-TimeoutSeconds</span></span>

<span data-ttu-id="169ad-271">Gibt die Anzahl der Sekunden an, die gewartet werden soll, bis alle Eingaben parallel verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-271">Specifies the number of seconds to wait for all input to be processed in parallel.</span></span> <span data-ttu-id="169ad-272">Nach der angegebenen Timeout Zeit werden alle laufenden Skripts angehalten.</span><span class="sxs-lookup"><span data-stu-id="169ad-272">After the specified timeout time, all running scripts are stopped.</span></span> <span data-ttu-id="169ad-273">Und alle verbleibenden zu verarbeitenden Eingabe Objekte werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="169ad-273">And any remaining input objects to be processed are ignored.</span></span> <span data-ttu-id="169ad-274">Der Standardwert `0` deaktiviert den Timeout und `ForEach-Object -Parallel` kann unbegrenzt ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-274">Default value of `0` disables the timeout, and `ForEach-Object -Parallel` can run indefinitely.</span></span> <span data-ttu-id="169ad-275">Wenn <kbd>Ctrl</kbd>Sie + in der Befehlszeile STRG<kbd>C</kbd> eingeben, wird ein laufender `ForEach-Object -Parallel` Befehl beendet.</span><span class="sxs-lookup"><span data-stu-id="169ad-275">Typing <kbd>Ctrl</kbd>+<kbd>C</kbd> at the command line stops a running `ForEach-Object -Parallel` command.</span></span> <span data-ttu-id="169ad-276">Dieser Parameter kann nicht zusammen mit dem **AsJob** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-276">This parameter cannot be used along with the **AsJob** parameter.</span></span>

<span data-ttu-id="169ad-277">Dieser Parameter wurde in PowerShell 7,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-277">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="169ad-278">-AsJob</span><span class="sxs-lookup"><span data-stu-id="169ad-278">-AsJob</span></span>

<span data-ttu-id="169ad-279">Bewirkt, dass der parallele Aufruf als PowerShell-Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="169ad-279">Causes the parallel invocation to run as a PowerShell job.</span></span> <span data-ttu-id="169ad-280">Anstelle der Ausgabe der ausgelaufenden Skriptblöcke wird ein einzelnes Auftrags Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="169ad-280">A single job object is returned instead of output from the running script blocks.</span></span> <span data-ttu-id="169ad-281">Das Job-Objekt enthält untergeordnete Aufträge für jeden parallelen Skriptblock, der ausführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-281">The job object contains child jobs for each parallel script block that runs.</span></span> <span data-ttu-id="169ad-282">Das Auftrags Objekt kann von allen PowerShell-Auftrags-Cmdlets verwendet werden, um den Status der Ausführung und das Abrufen von Daten zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="169ad-282">The job object can be used by all PowerShell job cmdlets, to monitor running state and retrieve data.</span></span>

<span data-ttu-id="169ad-283">Dieser Parameter wurde in PowerShell 7,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-283">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="169ad-284">-Confirm</span><span class="sxs-lookup"><span data-stu-id="169ad-284">-Confirm</span></span>

<span data-ttu-id="169ad-285">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="169ad-285">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="169ad-286">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="169ad-286">-WhatIf</span></span>

<span data-ttu-id="169ad-287">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="169ad-287">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="169ad-288">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="169ad-288">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="169ad-289">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="169ad-289">CommonParameters</span></span>

<span data-ttu-id="169ad-290">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="169ad-290">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="169ad-291">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="169ad-291">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="169ad-292">Eingaben</span><span class="sxs-lookup"><span data-stu-id="169ad-292">Inputs</span></span>

### <span data-ttu-id="169ad-293">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="169ad-293">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="169ad-294">Sie können jedes beliebige Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="169ad-294">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="169ad-295">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="169ad-295">Outputs</span></span>

### <span data-ttu-id="169ad-296">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="169ad-296">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="169ad-297">Dieses Cmdlet gibt Objekte zurück, die von der Eingabe bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-297">This cmdlet returns objects that are determined by the input.</span></span>

## <span data-ttu-id="169ad-298">Notizen</span><span class="sxs-lookup"><span data-stu-id="169ad-298">Notes</span></span>

- <span data-ttu-id="169ad-299">Das- `ForEach-Object` Cmdlet funktioniert ähnlich wie die **foreach** -Anweisung, mit dem Unterschied, dass Sie Eingaben nicht an eine **foreach** -Anweisung übergeben können.</span><span class="sxs-lookup"><span data-stu-id="169ad-299">The `ForEach-Object` cmdlet works much like the **Foreach** statement, except that you cannot pipe input to a **Foreach** statement.</span></span> <span data-ttu-id="169ad-300">Weitere Informationen zur **foreach** -Anweisung finden Sie unter [about_Foreach](./About/about_Foreach.md).</span><span class="sxs-lookup"><span data-stu-id="169ad-300">For more information about the **Foreach** statement, see [about_Foreach](./About/about_Foreach.md).</span></span>

- <span data-ttu-id="169ad-301">Ab PowerShell 4,0 `Where` wurden-und-Methoden für die Verwendung mit-Auflistungen `ForEach` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="169ad-301">Starting in PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span> <span data-ttu-id="169ad-302">Weitere Informationen zu diesen neuen Methoden finden Sie hier [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="169ad-302">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

- <span data-ttu-id="169ad-303">Der `ForEach-Object -Parallel` Parametersatz verwendet die interne PowerShell-API, um jeden Skriptblock auszuführen.</span><span class="sxs-lookup"><span data-stu-id="169ad-303">The `ForEach-Object -Parallel` parameter set uses PowerShell's internal API to run each script block.</span></span> <span data-ttu-id="169ad-304">Dies ist deutlich mehr Aufwand als `ForEach-Object` bei der sequenziellen Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="169ad-304">This is significantly more overhead than running `ForEach-Object` normally with sequential processing.</span></span> <span data-ttu-id="169ad-305">Es ist wichtig, **parallel** zu verwenden, wenn der mehr Aufwand für die parallele Ausführung im Vergleich zu den vom Skriptblock ausgeführten Arbeiten gering ist.</span><span class="sxs-lookup"><span data-stu-id="169ad-305">It is important to use **Parallel** where the overhead of running in parallel is small compared to work the script block performs.</span></span> <span data-ttu-id="169ad-306">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="169ad-306">For example:</span></span>

  - <span data-ttu-id="169ad-307">Rechenintensive Skripts auf mehr Kern Computern</span><span class="sxs-lookup"><span data-stu-id="169ad-307">Compute intensive scripts on multi-core machines</span></span>
  - <span data-ttu-id="169ad-308">Skripts, die Zeit für das warten auf Ergebnisse oder Datei Vorgänge aufwenden</span><span class="sxs-lookup"><span data-stu-id="169ad-308">Scripts that spend time waiting for results or doing file operations</span></span>

  <span data-ttu-id="169ad-309">Die Verwendung des **parallel** -Parameters kann bewirken, dass Skripts wesentlich langsamer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-309">Using the **Parallel** parameter can cause scripts to run much slower than normal.</span></span> <span data-ttu-id="169ad-310">Insbesondere, wenn die parallelen Skripts trivial sind.</span><span class="sxs-lookup"><span data-stu-id="169ad-310">Especially if the parallel scripts are trivial.</span></span> <span data-ttu-id="169ad-311">Experimentieren Sie mit **parallel** , um herauszufinden, wo es nützlich sein kann.</span><span class="sxs-lookup"><span data-stu-id="169ad-311">Experiment with **Parallel** to discover where it can be beneficial.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="169ad-312">Der `ForEach-Object -Parallel` Parametersatz führt Skriptblöcke parallel in separaten Prozessthreads aus.</span><span class="sxs-lookup"><span data-stu-id="169ad-312">The `ForEach-Object -Parallel` parameter set runs script blocks in parallel on separate process threads.</span></span> <span data-ttu-id="169ad-313">Das- `$using:` Schlüsselwort ermöglicht das Übergeben von Variablen verweisen vom Cmdlet-Aufruf Thread an jeden Skriptblock Thread, der ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="169ad-313">The `$using:` keyword allows passing variable references from the cmdlet invocation thread to each running script block thread.</span></span> <span data-ttu-id="169ad-314">Da die Skriptblöcke in verschiedenen Threads ausgeführt werden, müssen die als Verweis übergebenen Objektvariablen sicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="169ad-314">Since the script blocks run in different threads, the object variables passed by reference must be used safely.</span></span> <span data-ttu-id="169ad-315">Im Allgemeinen ist es sicher, aus referenzierten Objekten zu lesen, die sich nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="169ad-315">Generally it is safe to read from referenced objects that don't change.</span></span> <span data-ttu-id="169ad-316">Wenn der Objektstatus jedoch geändert wird, müssen Sie Thread sichere Objekte verwenden, wie z. b. .net **System. Collection. Concurrent** -Typen (siehe Beispiel 11).</span><span class="sxs-lookup"><span data-stu-id="169ad-316">But if the object state is being modified then you must used thread safe objects, such as .Net **System.Collection.Concurrent** types (See Example 11).</span></span>

## <span data-ttu-id="169ad-317">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="169ad-317">Related links</span></span>

[<span data-ttu-id="169ad-318">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="169ad-318">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="169ad-319">Where-Object</span><span class="sxs-lookup"><span data-stu-id="169ad-319">Where-Object</span></span>](Where-Object.md)

[<span data-ttu-id="169ad-320">Group-Object</span><span class="sxs-lookup"><span data-stu-id="169ad-320">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="169ad-321">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="169ad-321">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="169ad-322">New-Object</span><span class="sxs-lookup"><span data-stu-id="169ad-322">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="169ad-323">Select-Object</span><span class="sxs-lookup"><span data-stu-id="169ad-323">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="169ad-324">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="169ad-324">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="169ad-325">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="169ad-325">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
