---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 8a79dcf9c2af7aed0c52c361467cab23f880a893
ms.sourcegitcommit: fb9bafd041e3615b9dc9fb77c9245581b705cd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2020
ms.locfileid: "99603513"
---
# <span data-ttu-id="cf72b-102">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="cf72b-102">ForEach-Object</span></span>

## <span data-ttu-id="cf72b-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="cf72b-103">Synopsis</span></span>
<span data-ttu-id="cf72b-104">Führt einen Vorgang für jedes Element in einer Auflistung von Eingabeobjekten aus.</span><span class="sxs-lookup"><span data-stu-id="cf72b-104">Performs an operation against each item in a collection of input objects.</span></span>

## <span data-ttu-id="cf72b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf72b-105">Syntax</span></span>

### <span data-ttu-id="cf72b-106">Scriptblockset (Standard)</span><span class="sxs-lookup"><span data-stu-id="cf72b-106">ScriptBlockSet (Default)</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cf72b-107">Propertyandmethodset</span><span class="sxs-lookup"><span data-stu-id="cf72b-107">PropertyAndMethodSet</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cf72b-108">Parallelparameterset</span><span class="sxs-lookup"><span data-stu-id="cf72b-108">ParallelParameterSet</span></span>

```
ForEach-Object -Parallel <scriptblock> [-InputObject <PSObject>] [-ThrottleLimit <int>]
[-UseNewRunspace] [-TimeoutSeconds <int>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cf72b-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cf72b-109">Description</span></span>

<span data-ttu-id="cf72b-110">Das- `ForEach-Object` Cmdlet führt einen Vorgang für jedes Element in einer Auflistung von Eingabe Objekten aus.</span><span class="sxs-lookup"><span data-stu-id="cf72b-110">The `ForEach-Object` cmdlet performs an operation on each item in a collection of input objects.</span></span> <span data-ttu-id="cf72b-111">Die Eingabe Objekte können an das Cmdlet weitergeleitet oder mithilfe des **Inputobject** -Parameters angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-111">The input objects can be piped to the cmdlet or specified by using the **InputObject** parameter.</span></span>

<span data-ttu-id="cf72b-112">Ab Windows PowerShell 3,0 gibt es zwei verschiedene Möglichkeiten, einen Befehl zu erstellen `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="cf72b-112">Starting in Windows PowerShell 3.0, there are two different ways to construct a `ForEach-Object` command.</span></span>

- <span data-ttu-id="cf72b-113">**Skriptblock**.</span><span class="sxs-lookup"><span data-stu-id="cf72b-113">**Script block**.</span></span> <span data-ttu-id="cf72b-114">Sie können einen Skriptblock verwenden, um den Vorgang anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cf72b-114">You can use a script block to specify the operation.</span></span> <span data-ttu-id="cf72b-115">Verwenden Sie innerhalb des Skript Blocks die- `$_` Variable, um das aktuelle-Objekt darzustellen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-115">Within the script block, use the `$_` variable to represent the current object.</span></span> <span data-ttu-id="cf72b-116">Der Skriptblock ist der Wert des **Process**-Parameters.</span><span class="sxs-lookup"><span data-stu-id="cf72b-116">The script block is the value of the **Process** parameter.</span></span> <span data-ttu-id="cf72b-117">Der Skriptblock kann beliebige PowerShell-Skripts enthalten.</span><span class="sxs-lookup"><span data-stu-id="cf72b-117">The script block can contain any PowerShell script.</span></span>

  <span data-ttu-id="cf72b-118">Der folgende Befehl ruft beispielsweise den Wert der **ProcessName**-Eigenschaft der einzelnen Prozesse auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="cf72b-118">For example, the following command gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object {$_.ProcessName}`

  <span data-ttu-id="cf72b-119">`ForEach-Object` unterstützt `begin` die `process` Blöcke, und, `end` wie in [about_functions](about/about_functions.md#piping-objects-to-functions)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cf72b-119">`ForEach-Object` supports the `begin`, `process`, and `end` blocks as described in [about_functions](about/about_functions.md#piping-objects-to-functions).</span></span>

  > [!NOTE]
  > <span data-ttu-id="cf72b-120">Die Skriptblöcke werden im Gültigkeitsbereich des Aufrufers ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-120">The script blocks run in the caller's scope.</span></span> <span data-ttu-id="cf72b-121">Daher haben die Blöcke Zugriff auf Variablen in diesem Bereich und können neue Variablen erstellen, die in diesem Bereich beibehalten werden, nachdem das Cmdlet abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="cf72b-121">Therefore the blocks have access to variables in that scope and can create new variables that persist in that scope after the cmdlet completes.</span></span>

- <span data-ttu-id="cf72b-122">**Operation-Anweisung**.</span><span class="sxs-lookup"><span data-stu-id="cf72b-122">**Operation statement**.</span></span> <span data-ttu-id="cf72b-123">Sie können auch eine Vorgangs Anweisung schreiben, die in natürlicher Sprache sehr viel ähnlicher ist.</span><span class="sxs-lookup"><span data-stu-id="cf72b-123">You can also write an operation statement, which is much more like natural language.</span></span> <span data-ttu-id="cf72b-124">Sie können die Vorgangsanweisung verwenden, um einen Eigenschaftenwert anzugeben oder eine Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-124">You can use the operation statement to specify a property value or call a method.</span></span> <span data-ttu-id="cf72b-125">Vorgangsanweisungen wurden in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-125">Operation statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="cf72b-126">Der folgende Befehl ruft beispielsweise ebenfalls den Wert der **ProcessName**-Eigenschaft der einzelnen Prozesse auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="cf72b-126">For example, the following command also gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object ProcessName`

- <span data-ttu-id="cf72b-127">**Parallel ausgeführten Skriptblock**.</span><span class="sxs-lookup"><span data-stu-id="cf72b-127">**Parallel running script block**.</span></span> <span data-ttu-id="cf72b-128">Ab PowerShell 7,0 ist ein Dritter Parametersatz verfügbar, der jeden Skriptblock parallel ausführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-128">Beginning with PowerShell 7.0, a third parameter set is available that runs each script block in parallel.</span></span> <span data-ttu-id="cf72b-129">Der **throttlelimit** -Parameter schränkt die Anzahl paralleler Skripts ein, die gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-129">The **ThrottleLimit** parameter limits the number of parallel scripts running at a time.</span></span> <span data-ttu-id="cf72b-130">Verwenden Sie wie zuvor die- `$_` Variable, um das aktuelle Eingabe Objekt im Skriptblock darzustellen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-130">As before, use the `$_` variable to represent the current input object in the script block.</span></span> <span data-ttu-id="cf72b-131">Verwenden Sie das- `$using:` Schlüsselwort, um Variablen Verweise an das laufende Skript zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="cf72b-131">Use the `$using:` keyword to pass variable references to the running script.</span></span>

  <span data-ttu-id="cf72b-132">In PowerShell 7 wird ein neuer Runspace für jede Schleifen Iteration erstellt, um eine maximale Isolation sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-132">In PowerShell 7, a new runspace is created for each loop iteration to ensure maximum isolation.</span></span>
  <span data-ttu-id="cf72b-133">Dabei kann es sich um eine große Leistung und einen Ressourcen Treffer handeln, wenn die Arbeit, die Sie ausführen, im Vergleich zum Erstellen neuer Runspaces gering ist, oder wenn viele Iterationen eine bedeutende Arbeit ausführen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-133">This can be a large performance and resource hit if the work you are doing is small compared to creating new runspaces or if there are a lot of iterations performing significant work.</span></span> <span data-ttu-id="cf72b-134">Ab PowerShell 7,1 werden Runspaces aus einem Runspace-Pool standardmäßig wieder verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf72b-134">As of PowerShell 7.1, runspaces from a runspace pool are reused by default.</span></span> <span data-ttu-id="cf72b-135">Die Größe des Runspace-Pools wird durch den **throttlelimit** -Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="cf72b-135">The runspace pool size is specified by the **ThrottleLimit** parameter.</span></span> <span data-ttu-id="cf72b-136">Die standardmäßige Runspace-Poolgröße ist 5.</span><span class="sxs-lookup"><span data-stu-id="cf72b-136">The default runspace pool size is 5.</span></span> <span data-ttu-id="cf72b-137">Mit dem Schalter **usenewrunspace** können Sie immer noch einen neuen Runspace für jede Iterationen erstellen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-137">You can still create a new runspace for each iteration using the **UseNewRunspace** switch.</span></span>

  <span data-ttu-id="cf72b-138">Standardmäßig verwenden die parallelen Scriptblocks das aktuelle Arbeitsverzeichnis des Aufrufers, der die parallelen Aufgaben gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="cf72b-138">By default, the parallel scriptblocks use the current working directory of the caller that started the parallel tasks.</span></span>

  <span data-ttu-id="cf72b-139">Fehler ohne Abbruch werden in den Cmdlet-Fehler Datenstrom geschrieben, da Sie in parallel ausgeführten Scriptblocks auftreten.</span><span class="sxs-lookup"><span data-stu-id="cf72b-139">Non-terminating errors are written to the cmdlet error stream as they occur in parallel running scriptblocks.</span></span> <span data-ttu-id="cf72b-140">Da die Ausführungsreihenfolge paralleler Scriptblocks nicht bestimmt werden kann, ist die Reihenfolge, in der Fehler im Fehler Datenstrom angezeigt werden, zufällig.</span><span class="sxs-lookup"><span data-stu-id="cf72b-140">Because parallel scriptblock execution order cannot be determined, the order in which errors appear in the error stream is random.</span></span> <span data-ttu-id="cf72b-141">Ebenso werden Nachrichten, die in andere Datenströme wie Warnung, ausführlich oder Informationen geschrieben werden, in einer unbestimmten Reihenfolge in diese Datenströme geschrieben.</span><span class="sxs-lookup"><span data-stu-id="cf72b-141">Likewise, messages written to other data streams, like warning, verbose, or information are written to those data streams in an indeterminate order.</span></span>

  <span data-ttu-id="cf72b-142">Beim Beenden von Fehlern, z. b. Ausnahmen, wird die einzelne parallele Instanz der Scriptblocks beendet, in denen Sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="cf72b-142">Terminating errors, such as exceptions, terminate the individual parallel instance of the scriptblocks in which they occur.</span></span> <span data-ttu-id="cf72b-143">Ein Beendigungs Fehler in einem Scriptblocks führt möglicherweise nicht zum Beenden des `Foreach-Object` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="cf72b-143">A terminating error in one scriptblocks may not cause the termination of the `Foreach-Object` cmdlet.</span></span> <span data-ttu-id="cf72b-144">Die anderen Skriptblöcke, die parallel ausgeführt werden, werden weiterhin ausgeführt, es sei denn, Sie stoßen auch auf einen Beendigungs Fehler.</span><span class="sxs-lookup"><span data-stu-id="cf72b-144">The other scriptblocks, running in parallel, continue to run unless they also encounter a terminating error.</span></span> <span data-ttu-id="cf72b-145">Der Abbruch Fehler wird in den Fehler Datenstrom als **ErrorRecord** mit der **fullyqualifiederrorid** von geschrieben `PSTaskException` .</span><span class="sxs-lookup"><span data-stu-id="cf72b-145">The terminating error is written to the error data stream as an **ErrorRecord** with a **FullyQualifiedErrorId** of `PSTaskException`.</span></span>
  <span data-ttu-id="cf72b-146">Fehler beim Beenden können mithilfe von PowerShell-try/catch-oder Trap-Blöcken in Fehler ohne Abbruch konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-146">Terminating errors can be converted to non-terminating errors using PowerShell try/catch or trap blocks.</span></span>

## <span data-ttu-id="cf72b-147">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cf72b-147">Examples</span></span>

### <span data-ttu-id="cf72b-148">Beispiel 1: Teilen von ganzen Zahlen in einem Array</span><span class="sxs-lookup"><span data-stu-id="cf72b-148">Example 1: Divide integers in an array</span></span>

<span data-ttu-id="cf72b-149">In diesem Beispiel wird ein Array von drei ganzen Zahlen angenommen, und jedes dieser Elemente wird durch 1024 dividiert.</span><span class="sxs-lookup"><span data-stu-id="cf72b-149">This example takes an array of three integers and divides each one of them by 1024.</span></span>

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### <span data-ttu-id="cf72b-150">Beispiel 2: erhalten der Länge aller Dateien in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="cf72b-150">Example 2: Get the length of all the files in a directory</span></span>

<span data-ttu-id="cf72b-151">In diesem Beispiel werden die Dateien und Verzeichnisse im PowerShell-Installationsverzeichnis verarbeitet `$PSHOME` .</span><span class="sxs-lookup"><span data-stu-id="cf72b-151">This example processes the files and directories in the PowerShell installation directory `$PSHOME`.</span></span>

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

<span data-ttu-id="cf72b-152">Wenn das Objekt kein Verzeichnis ist, ruft der Skriptblock den Namen der Datei ab, teilt den Wert der **length** -Eigenschaft durch 1024 und fügt ein Leerzeichen ("") hinzu, um es vom nächsten Eintrag zu trennen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-152">If the object is not a directory, the script block gets the name of the file, divides the value of its **Length** property by 1024, and adds a space (" ") to separate it from the next entry.</span></span> <span data-ttu-id="cf72b-153">Mit dem-Cmdlet wird die **psiscontainer** -Eigenschaft verwendet, um zu bestimmen, ob ein Objekt ein Verzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="cf72b-153">The cmdlet uses the **PSISContainer** property to determine whether an object is a directory.</span></span>

### <span data-ttu-id="cf72b-154">Beispiel 3: Arbeiten mit den neuesten System Ereignissen</span><span class="sxs-lookup"><span data-stu-id="cf72b-154">Example 3: Operate on the most recent System events</span></span>

<span data-ttu-id="cf72b-155">In diesem Beispiel werden die 1000 aktuellsten Ereignisse aus dem System Ereignisprotokoll in eine Textdatei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="cf72b-155">This example writes the 1000 most recent events from the System event log to a text file.</span></span> <span data-ttu-id="cf72b-156">Die aktuelle Zeit wird vor und nach der Verarbeitung der Ereignisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-156">The current time is displayed before and after processing the events.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

<span data-ttu-id="cf72b-157">`Get-EventLog` Ruft die 1000 aktuellsten Ereignisse aus dem System Ereignisprotokoll ab und speichert Sie in der `$Events` Variablen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-157">`Get-EventLog` gets the 1000 most recent events from the System event log and stores them in the `$Events` variable.</span></span> <span data-ttu-id="cf72b-158">`$Events` wird dann an das `ForEach-Object` Cmdlet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="cf72b-158">`$Events` is then piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="cf72b-159">Der **Begin**-Parameter zeigt das aktuelle Datum und die Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="cf72b-159">The **Begin** parameter displays the current date and time.</span></span> <span data-ttu-id="cf72b-160">Als Nächstes verwendet der **Process** -Parameter das `Out-File` -Cmdlet, um eine Textdatei mit dem Namen events.txt zu erstellen, und speichert die Message-Eigenschaft der einzelnen Ereignisse in dieser Datei.</span><span class="sxs-lookup"><span data-stu-id="cf72b-160">Next, the **Process** parameter uses the `Out-File` cmdlet to create a text file that is named events.txt and stores the message property of each of the events in that file.</span></span> <span data-ttu-id="cf72b-161">Schließlich wird der **End**-Parameter verwendet, um das Datum und die Uhrzeit anzuzeigen, zu denen die gesamte Verarbeitung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="cf72b-161">Last, the **End** parameter is used to display the date and time after all of the processing has completed.</span></span>

### <span data-ttu-id="cf72b-162">Beispiel 4: Ändern des Werts eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="cf72b-162">Example 4: Change the value of a Registry key</span></span>

<span data-ttu-id="cf72b-163">In diesem Beispiel wird der Wert des **remotePath** -Registrierungs Eintrags in allen unter Schlüsseln unter dem `HKCU:\Network` Schlüssel in Großbuchstaben geändert.</span><span class="sxs-lookup"><span data-stu-id="cf72b-163">This example changes the value of the **RemotePath** registry entry in all of the subkeys under the `HKCU:\Network` key to uppercase text.</span></span>

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

<span data-ttu-id="cf72b-164">Sie können dieses Format verwenden,um die Form oder den Inhalt eines Registrierungseintragswerts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cf72b-164">You can use this format to change the form or content of a registry entry value.</span></span>

<span data-ttu-id="cf72b-165">Jeder Unterschlüssel im **Netzwerk** Schlüssel stellt ein zugeordnetes Netzwerklaufwerk dar, das bei der Anmeldung erneut eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-165">Each subkey in the **Network** key represents a mapped network drive that reconnects at sign on.</span></span> <span data-ttu-id="cf72b-166">Der **RemotePath**-Eintrag enthält den UNC-Pfad des verbundenen Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="cf72b-166">The **RemotePath** entry contains the UNC path of the connected drive.</span></span> <span data-ttu-id="cf72b-167">Wenn Sie z. b. das Laufwerk e: zu zuordnen `\\Server\Share` , wird ein **e** -Unterschlüssel in erstellt, `HKCU:\Network` wobei der Registrierungs Wert **remotePath** auf festgelegt ist `\\Server\Share` .</span><span class="sxs-lookup"><span data-stu-id="cf72b-167">For example, if you map the E: drive to `\\Server\Share`, an **E** subkey is created in `HKCU:\Network` with the **RemotePath** registry value set to `\\Server\Share`.</span></span>

<span data-ttu-id="cf72b-168">Der Befehl verwendet das `Get-ItemProperty` Cmdlet, um alle untergeordneten Schlüssel des **Netzwerk** Schlüssels zu erhalten, und das `Set-ItemProperty` Cmdlet, um den Wert des **remotePath** -Registrierungs Eintrags in jedem Schlüssel zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cf72b-168">The command uses the `Get-ItemProperty` cmdlet to get all of the subkeys of the **Network** key and the `Set-ItemProperty` cmdlet to change the value of the **RemotePath** registry entry in each key.</span></span>
<span data-ttu-id="cf72b-169">Im- `Set-ItemProperty` Befehl ist der Pfad der Wert der **pspath** -Eigenschaft des Registrierungsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="cf72b-169">In the `Set-ItemProperty` command, the path is the value of the **PSPath** property of the registry key.</span></span> <span data-ttu-id="cf72b-170">Dies ist eine Eigenschaft des Microsoft .NET Framework-Objekts, das den Registrierungsschlüssel darstellt, nicht einen Registrierungs Eintrag.</span><span class="sxs-lookup"><span data-stu-id="cf72b-170">This is a property of the Microsoft .NET Framework object that represents the registry key, not a registry entry.</span></span> <span data-ttu-id="cf72b-171">Der Befehl verwendet die **touppermethode ()** des **remotePath** -Werts, bei der es sich um eine Zeichenfolge (REG_SZ) handelt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-171">The command uses the **ToUpper()** method of the **RemotePath** value, which is a string (REG_SZ).</span></span>

<span data-ttu-id="cf72b-172">Da `Set-ItemProperty` die-Eigenschaft jedes Schlüssels ändert, ist das `ForEach-Object` Cmdlet für den Zugriff auf die-Eigenschaft erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cf72b-172">Because `Set-ItemProperty` is changing the property of each key, the `ForEach-Object` cmdlet is required to access the property.</span></span>

### <span data-ttu-id="cf72b-173">Beispiel 5: Verwenden der automatischen $NULL Variablen</span><span class="sxs-lookup"><span data-stu-id="cf72b-173">Example 5: Use the $Null automatic variable</span></span>

<span data-ttu-id="cf72b-174">In diesem Beispiel wird gezeigt, wie die `$Null` Automatische Variable an das `ForEach-Object` Cmdlet weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="cf72b-174">This example shows the effect of piping the `$Null` automatic variable to the `ForEach-Object` cmdlet.</span></span>

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

<span data-ttu-id="cf72b-175">Da PowerShell NULL als expliziten Platzhalter behandelt, `ForEach-Object` generiert das Cmdlet einen Wert für `$Null` , genau wie bei anderen Objekten, die an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-175">Because PowerShell treats null as an explicit placeholder, the `ForEach-Object` cmdlet generates a value for `$Null`, just as it does for other objects that you pipe to it.</span></span>

### <span data-ttu-id="cf72b-176">Beispiel 6: erhalten von Eigenschafts Werten</span><span class="sxs-lookup"><span data-stu-id="cf72b-176">Example 6: Get property values</span></span>

<span data-ttu-id="cf72b-177">In diesem Beispiel wird der Wert der **path** -Eigenschaft aller installierten PowerShell-Module mithilfe des **Mitgliedschafts Namen** -Parameters des `ForEach-Object` Cmdlets abgerufen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-177">This example gets the value of the **Path** property of all installed PowerShell modules by using the **MemberName** parameter of the `ForEach-Object` cmdlet.</span></span>

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

<span data-ttu-id="cf72b-178">Der zweite Befehl entspricht dem ersten.</span><span class="sxs-lookup"><span data-stu-id="cf72b-178">The second command is equivalent to the first.</span></span> <span data-ttu-id="cf72b-179">Er verwendet den `Foreach` Alias des `ForEach-Object` Cmdlets und lässt den Namen des **Mitgliedsnamen** -Parameters aus, der optional ist.</span><span class="sxs-lookup"><span data-stu-id="cf72b-179">It uses the `Foreach` alias of the `ForEach-Object` cmdlet and omits the name of the **MemberName** parameter, which is optional.</span></span>

<span data-ttu-id="cf72b-180">Das- `ForEach-Object` Cmdlet ist nützlich zum Abrufen von Eigenschafts Werten, da es den Wert abruft, ohne den Typ zu ändern, im Gegensatz zu den **Format** -Cmdlets oder dem `Select-Object` Cmdlet, die den Eigenschafts Werttyp ändern.</span><span class="sxs-lookup"><span data-stu-id="cf72b-180">The `ForEach-Object` cmdlet is useful for getting property values, because it gets the value without changing the type, unlike the **Format** cmdlets or the `Select-Object` cmdlet, which change the property value type.</span></span>

### <span data-ttu-id="cf72b-181">Beispiel 7: Aufteilen von Modulnamen in Komponentennamen</span><span class="sxs-lookup"><span data-stu-id="cf72b-181">Example 7: Split module names into component names</span></span>

<span data-ttu-id="cf72b-182">Dieses Beispiel zeigt drei Möglichkeiten, zwei durch Punkte getrennte Modulnamen in Ihre Komponentennamen aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-182">This example shows three ways to split two dot-separated module names into their component names.</span></span>

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

<span data-ttu-id="cf72b-183">Die Befehle rufen die **Split** Methode von Zeichenfolgen auf.</span><span class="sxs-lookup"><span data-stu-id="cf72b-183">The commands call the **Split** method of strings.</span></span> <span data-ttu-id="cf72b-184">Die drei Befehle verwenden unterschiedliche Syntax, sind aber äquivalent und austauschbar.</span><span class="sxs-lookup"><span data-stu-id="cf72b-184">The three commands use different syntax, but they are equivalent and interchangeable.</span></span>

<span data-ttu-id="cf72b-185">Der erste Befehl verwendet die herkömmliche Syntax, die einen Skriptblock und den aktuellen Objekt Operator enthält `$_` .</span><span class="sxs-lookup"><span data-stu-id="cf72b-185">The first command uses the traditional syntax, which includes a script block and the current object operator `$_`.</span></span> <span data-ttu-id="cf72b-186">Es verwendet die Punktsyntax zum Angeben der Methode und die Klammern, um das Trennzeichenargument einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-186">It uses the dot syntax to specify the method and parentheses to enclose the delimiter argument.</span></span>

<span data-ttu-id="cf72b-187">Der zweite Befehl verwendet den **MemberName**-Parameter, um die **Split**-Methode anzugeben,und den **ArgumentName**-Parameter, um den Punkt („.“) als das Teilungstrennzeichen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="cf72b-187">The second command uses the **MemberName** parameter to specify the **Split** method and the **ArgumentName** parameter to identify the dot (".") as the split delimiter.</span></span>

<span data-ttu-id="cf72b-188">Der dritte Befehl verwendet den **foreach** -Alias des `ForEach-Object` Cmdlets und lässt die Namen der Parameter " **Membership Name** " und "Argument **List** " aus, die optional sind.</span><span class="sxs-lookup"><span data-stu-id="cf72b-188">The third command uses the **Foreach** alias of the `ForEach-Object` cmdlet and omits the names of the **MemberName** and **ArgumentList** parameters, which are optional.</span></span>

### <span data-ttu-id="cf72b-189">Beispiel 8: Verwenden von ForEach-Object mit zwei Skript Blöcken</span><span class="sxs-lookup"><span data-stu-id="cf72b-189">Example 8: Using ForEach-Object with two script blocks</span></span>

<span data-ttu-id="cf72b-190">In diesem Beispiel übergeben wir zwei Skriptblöcke in der gleichen Weise.</span><span class="sxs-lookup"><span data-stu-id="cf72b-190">In this example, we pass two script blocks positionally.</span></span> <span data-ttu-id="cf72b-191">Alle Skriptblöcke werden an den **Prozess** Parameter gebunden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-191">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="cf72b-192">Sie werden jedoch so behandelt, als würden Sie an den **Begin** -und den **Process** -Parameter übermittelt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-192">However, they are treated as if they had been passed to the **Begin** and **Process** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### <span data-ttu-id="cf72b-193">Beispiel 9: Verwenden von ForEach-Object mit mehr als zwei Skript Blöcken</span><span class="sxs-lookup"><span data-stu-id="cf72b-193">Example 9: Using ForEach-Object with more than two script blocks</span></span>

<span data-ttu-id="cf72b-194">In diesem Beispiel übergeben wir zwei Skriptblöcke in der gleichen Weise.</span><span class="sxs-lookup"><span data-stu-id="cf72b-194">In this example, we pass two script blocks positionally.</span></span> <span data-ttu-id="cf72b-195">Alle Skriptblöcke werden an den **Prozess** Parameter gebunden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-195">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="cf72b-196">Sie werden jedoch so behandelt, als wären Sie an die **Begin**-, **Process**-und **End** -Parameter übergebenen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-196">However, they are treated as if they had been passed to the **Begin**, **Process**, and **End** parameters.</span></span>

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
> <span data-ttu-id="cf72b-197">Der erste Skriptblock wird immer dem Block zugeordnet `begin` , der letzte Block wird dem `end` Block zugeordnet, und die Blöcke dazwischen werden alle dem `process` Block zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="cf72b-197">The first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

### <span data-ttu-id="cf72b-198">Beispiel 10: Ausführen mehrerer Skriptblöcke für jedes Pipeline Element</span><span class="sxs-lookup"><span data-stu-id="cf72b-198">Example 10: Run multiple script blocks for each pipeline item</span></span>

<span data-ttu-id="cf72b-199">Wie im vorherigen Beispiel gezeigt, werden mehrere Skriptblöcke, die mit dem **Process** -Parameter übergeben wurden, den **Begin** -und **End** -Parametern zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="cf72b-199">As shown in the previous example, multiple script blocks passed using the **Process** parameter get mapped to the **Begin** and **End** parameters.</span></span> <span data-ttu-id="cf72b-200">Um diese Zuordnung zu vermeiden, müssen Sie explizite Werte für die **Begin** -und **End** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="cf72b-200">To avoid this mapping, you must provide explicit values for the **Begin** and **End** parameters.</span></span>

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

### <span data-ttu-id="cf72b-201">Beispiel 11: Ausführen eines langsamen Skripts in parallelen Batches</span><span class="sxs-lookup"><span data-stu-id="cf72b-201">Example 11: Run slow script in parallel batches</span></span>

<span data-ttu-id="cf72b-202">In diesem Beispiel wird ein einfacher Skriptblock ausgeführt, der eine Zeichenfolge auswertet und eine Sekunde aufsperrt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-202">This example runs a simple script block that evaluates a string and sleeps for one second.</span></span>

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

<span data-ttu-id="cf72b-203">Der Wert des **throttlelimit** -Parameters ist auf 4 festgelegt, sodass die Eingabe in Batches von vier verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="cf72b-203">The **ThrottleLimit** parameter value is set to 4 so that the input is processed in batches of four.</span></span>
<span data-ttu-id="cf72b-204">Das- `$using:` Schlüsselwort wird verwendet, um die `$Message` Variable an jeden parallelen Skriptblock zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="cf72b-204">The `$using:` keyword is used to pass the `$Message` variable into each parallel script block.</span></span>

### <span data-ttu-id="cf72b-205">Beispiel 12: paralleles Abrufen von Protokoll Einträgen</span><span class="sxs-lookup"><span data-stu-id="cf72b-205">Example 12: Retrieve log entries in parallel</span></span>

<span data-ttu-id="cf72b-206">In diesem Beispiel werden 50.000-Protokolleinträge aus fünf Systemprotokollen auf einem lokalen Windows-Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-206">This example retrieves 50,000 log entries from 5 system logs on a local Windows machine.</span></span>

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

<span data-ttu-id="cf72b-207">Der Parameter **Parallel** gibt den Skriptblock an, der für jeden Eingabeprotokollnamen parallel ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cf72b-207">The **Parallel** parameter specifies the script block that is run in parallel for each input log name.</span></span> <span data-ttu-id="cf72b-208">Der **throttlelimit** -Parameter stellt sicher, dass alle fünf Skriptblöcke zur gleichen Zeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-208">The **ThrottleLimit** parameter ensures that all five script blocks run at the same time.</span></span>

### <span data-ttu-id="cf72b-209">Beispiel 13: parallele Ausführen als Auftrag</span><span class="sxs-lookup"><span data-stu-id="cf72b-209">Example 13: Run in parallel as a job</span></span>

<span data-ttu-id="cf72b-210">In diesem Beispiel wird ein einfacher Skriptblock parallel ausgeführt, wobei jeweils zwei Hintergrund Aufträge erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-210">This example runs a simple script block in parallel, creating two background jobs at a time.</span></span>

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

<span data-ttu-id="cf72b-211">die- `$job` Variable empfängt das Auftrags Objekt, das Ausgabedaten sammelt und den ausgegebene Status überwacht.</span><span class="sxs-lookup"><span data-stu-id="cf72b-211">the `$job` variable receives the job object that collects output data and monitors running state.</span></span>
<span data-ttu-id="cf72b-212">Das Auftrags Objekt wird `Receive-Job` mit dem **Wait** -Schalter Parameter an weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="cf72b-212">The job object is piped to `Receive-Job` with the **Wait** switch parameter.</span></span> <span data-ttu-id="cf72b-213">Und damit wird die Ausgabe an die Konsole gestreamt, so als ob auch `ForEach-Object -Parallel` ohne **AsJob** ausgeführt würde.</span><span class="sxs-lookup"><span data-stu-id="cf72b-213">And this streams output to the console, just as if `ForEach-Object -Parallel` was run without **AsJob**.</span></span>

### <span data-ttu-id="cf72b-214">Beispiel 14: Verwenden von Verweisen auf Thread sichere Variablen</span><span class="sxs-lookup"><span data-stu-id="cf72b-214">Example 14: Using thread safe variable references</span></span>

<span data-ttu-id="cf72b-215">In diesem Beispiel werden Skriptblöcke parallel aufgerufen, um eindeutig benannte Prozess Objekte zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-215">This example invokes script blocks in parallel to collect uniquely named Process objects.</span></span>

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

<span data-ttu-id="cf72b-216">Eine einzelne Instanz eines **ConcurrentDictionary** -Objekts wird an jeden Skriptblock zum Erfassen der Objekte übermittelt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-216">A single instance of a **ConcurrentDictionary** object is passed to each script block to collect the objects.</span></span> <span data-ttu-id="cf72b-217">Da das **ConcurrentDictionary** Thread sicher ist, kann es sicher von jedem parallelen Skript geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-217">Since the **ConcurrentDictionary** is thread safe, it is safe to be modified by each parallel script.</span></span> <span data-ttu-id="cf72b-218">Ein nicht Thread sicheres Objekt, wie z. b **. System. Collections. Generic. Dictionary**, kann hier nicht sicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-218">A non-thread-safe object, such as **System.Collections.Generic.Dictionary**, would not be safe to use here.</span></span>

> [!NOTE]
> <span data-ttu-id="cf72b-219">Dieses Beispiel ist eine sehr ineffiziente Verwendung des **parallelen** Parameters.</span><span class="sxs-lookup"><span data-stu-id="cf72b-219">This example is a very inefficient use of **Parallel** parameter.</span></span> <span data-ttu-id="cf72b-220">Das Skript fügt das Eingabe Objekt einfach einem gleichzeitigen Wörterbuch Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="cf72b-220">The script simply adds the input object to a concurrent dictionary object.</span></span> <span data-ttu-id="cf72b-221">Der Aufwand für das Aufrufen der einzelnen Skripts in einem separaten Thread ist trivial.</span><span class="sxs-lookup"><span data-stu-id="cf72b-221">It is trivial and not worth the overhead of invoking each script in a separate thread.</span></span> <span data-ttu-id="cf72b-222">Die normale Ausführung `ForEach-Object` ohne den **parallelen** Switch ist viel effizienter und schneller.</span><span class="sxs-lookup"><span data-stu-id="cf72b-222">Running `ForEach-Object` normally without the **Parallel** switch is much more efficient and faster.</span></span> <span data-ttu-id="cf72b-223">Dieses Beispiel soll lediglich veranschaulichen, wie Thread sichere Variablen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-223">This example is only intended to demonstrate how to use thread safe variables.</span></span>

### <span data-ttu-id="cf72b-224">Beispiel 15: Schreiben von Fehlern mit paralleler Ausführung</span><span class="sxs-lookup"><span data-stu-id="cf72b-224">Example 15: Writing errors with parallel execution</span></span>

<span data-ttu-id="cf72b-225">In diesem Beispiel wird parallel in den Fehler Datenstrom geschrieben, wobei die Reihenfolge der geschriebenen Fehler zufällig ist.</span><span class="sxs-lookup"><span data-stu-id="cf72b-225">This example writes to the error stream in parallel, where the order of written errors is random.</span></span>

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

### <span data-ttu-id="cf72b-226">Beispiel 16: Beenden von Fehlern bei der parallelen Ausführung</span><span class="sxs-lookup"><span data-stu-id="cf72b-226">Example 16: Terminating errors in parallel execution</span></span>

<span data-ttu-id="cf72b-227">In diesem Beispiel wird ein Beendigungs Fehler in einem parallel ausgeführten ScriptBlock veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cf72b-227">This example demonstrates a terminating error in one parallel running scriptblock.</span></span>

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

<span data-ttu-id="cf72b-228">`Output: 3` wird nie geschrieben, da der parallele ScriptBlock für diese Iterationen beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="cf72b-228">`Output: 3` is never written because the parallel scriptblock for that iteration was terminated.</span></span>

## <span data-ttu-id="cf72b-229">Parameter</span><span class="sxs-lookup"><span data-stu-id="cf72b-229">Parameters</span></span>

### <span data-ttu-id="cf72b-230">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="cf72b-230">-ArgumentList</span></span>

<span data-ttu-id="cf72b-231">Gibt ein Array von Argumenten für einen Methoden aufzurufenden an.</span><span class="sxs-lookup"><span data-stu-id="cf72b-231">Specifies an array of arguments to a method call.</span></span> <span data-ttu-id="cf72b-232">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="cf72b-232">For more information about the behavior of **ArgumentList**, see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="cf72b-233">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-233">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="cf72b-234">-BEGIN</span><span class="sxs-lookup"><span data-stu-id="cf72b-234">-Begin</span></span>

<span data-ttu-id="cf72b-235">Gibt einen Skriptblock an, der ausgeführt wird, bevor dieses Cmdlet Eingabe Objekte verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="cf72b-235">Specifies a script block that runs before this cmdlet processes any input objects.</span></span> <span data-ttu-id="cf72b-236">Dieser Skriptblock wird nur einmal für die gesamte Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-236">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="cf72b-237">Weitere Informationen zum- `begin` Block finden Sie unter [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="cf72b-237">For more information about the `begin` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

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

### <span data-ttu-id="cf72b-238">-Ende</span><span class="sxs-lookup"><span data-stu-id="cf72b-238">-End</span></span>

<span data-ttu-id="cf72b-239">Gibt einen Skriptblock an, der ausgeführt wird, nachdem dieses Cmdlet alle Eingabe Objekte verarbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="cf72b-239">Specifies a script block that runs after this cmdlet processes all input objects.</span></span> <span data-ttu-id="cf72b-240">Dieser Skriptblock wird nur einmal für die gesamte Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-240">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="cf72b-241">Weitere Informationen zum- `end` Block finden Sie unter [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="cf72b-241">For more information about the `end` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

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

### <span data-ttu-id="cf72b-242">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cf72b-242">-InputObject</span></span>

<span data-ttu-id="cf72b-243">Gibt die Eingabeobjekte an.</span><span class="sxs-lookup"><span data-stu-id="cf72b-243">Specifies the input objects.</span></span> <span data-ttu-id="cf72b-244">`ForEach-Object` führt den Skriptblock oder die Vorgangs Anweisung für jedes Eingabe Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="cf72b-244">`ForEach-Object` runs the script block or operation statement on each input object.</span></span> <span data-ttu-id="cf72b-245">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-245">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="cf72b-246">Wenn Sie den **Inputobject** -Parameter mit verwenden `ForEach-Object` , anstatt Befehls Ergebnisse an zu übergeben `ForEach-Object` , wird der **Inputobject** -Wert als einzelnes Objekt behandelt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-246">When you use the **InputObject** parameter with `ForEach-Object`, instead of piping command results to `ForEach-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="cf72b-247">Dies gilt auch, wenn der Wert eine Auflistung ist, die das Ergebnis eines Befehls ist, z `-InputObject (Get-Process)` . b..</span><span class="sxs-lookup"><span data-stu-id="cf72b-247">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span>
<span data-ttu-id="cf72b-248">Da **Inputobject** keine einzelnen Eigenschaften aus einem Array oder einer Auflistung von Objekten zurückgeben kann, empfiehlt es sich, wenn Sie verwenden, `ForEach-Object` um Vorgänge für eine Auflistung von Objekten für Objekte mit spezifischen Werten in definierten Eigenschaften auszuführen, `ForEach-Object` wie in den Beispielen in diesem Thema gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-248">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that if you use `ForEach-Object` to perform operations on a collection of objects for those objects that have specific values in defined properties, you use `ForEach-Object` in the pipeline, as shown in the examples in this topic.</span></span>

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

### <span data-ttu-id="cf72b-249">-Mitgliedsname</span><span class="sxs-lookup"><span data-stu-id="cf72b-249">-MemberName</span></span>

<span data-ttu-id="cf72b-250">Gibt die abzurufende Eigenschaft oder die aufzurufende Methode an.</span><span class="sxs-lookup"><span data-stu-id="cf72b-250">Specifies the property to get or the method to call.</span></span>

<span data-ttu-id="cf72b-251">Platzhalter Zeichen sind zulässig, funktionieren jedoch nur, wenn die resultierende Zeichenfolge in einen eindeutigen Wert aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="cf72b-251">Wildcard characters are permitted, but work only if the resulting string resolves to a unique value.</span></span>
<span data-ttu-id="cf72b-252">Wenn Sie z. b `Get-Process | ForEach -MemberName *Name` . ausführen, stimmt das Platzhalter Muster mit mehr als einem Member überein, wodurch der Befehl fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-252">For example, if you run `Get-Process | ForEach -MemberName *Name`, the wildcard pattern matches more than one member causing the command to fail.</span></span>

<span data-ttu-id="cf72b-253">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-253">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="cf72b-254">-Prozess</span><span class="sxs-lookup"><span data-stu-id="cf72b-254">-Process</span></span>

<span data-ttu-id="cf72b-255">Gibt den Vorgang an, der für jedes Eingabeobjekt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cf72b-255">Specifies the operation that is performed on each input object.</span></span> <span data-ttu-id="cf72b-256">Dieser Skriptblock wird für jedes Objekt in der Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-256">This script block is run for every object in the pipeline.</span></span> <span data-ttu-id="cf72b-257">Weitere Informationen zum- `process` Block finden Sie unter [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="cf72b-257">For more information about the `process` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

<span data-ttu-id="cf72b-258">Wenn Sie dem **Prozess** Parameter mehrere Skriptblöcke bereitstellen, wird der erste Skriptblock immer dem Block zugeordnet `begin` .</span><span class="sxs-lookup"><span data-stu-id="cf72b-258">When you provide multiple script blocks to the **Process** parameter, the first script block is always mapped to the `begin` block.</span></span> <span data-ttu-id="cf72b-259">Wenn nur zwei Skriptblöcke vorhanden sind, wird der zweite Block dem Block zugeordnet `process` .</span><span class="sxs-lookup"><span data-stu-id="cf72b-259">If there are only two script blocks, the second block is mapped to the `process` block.</span></span> <span data-ttu-id="cf72b-260">Wenn es drei oder mehr Skriptblöcke gibt, wird der erste Skriptblock immer dem `begin` Block zugeordnet, der letzte Block wird dem Block zugeordnet `end` , und die Blöcke dazwischen werden alle dem `process` Block zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="cf72b-260">If there are three or more script blocks, first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

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

### <span data-ttu-id="cf72b-261">-Restingscripts</span><span class="sxs-lookup"><span data-stu-id="cf72b-261">-RemainingScripts</span></span>

<span data-ttu-id="cf72b-262">Gibt alle Skriptblöcke an, die nicht vom **Prozess** Parameter übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-262">Specifies all script blocks that are not taken by the **Process** parameter.</span></span>

<span data-ttu-id="cf72b-263">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-263">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="cf72b-264">-Parallel</span><span class="sxs-lookup"><span data-stu-id="cf72b-264">-Parallel</span></span>

<span data-ttu-id="cf72b-265">Gibt den Skriptblock an, der für die parallele Verarbeitung von Eingabe Objekten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cf72b-265">Specifies the script block to be used for parallel processing of input objects.</span></span> <span data-ttu-id="cf72b-266">Geben Sie einen Skriptblock ein, der den Vorgang beschreibt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-266">Enter a script block that describes the operation.</span></span>

<span data-ttu-id="cf72b-267">Dieser Parameter wurde in PowerShell 7,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-267">This parameter was introduced in PowerShell 7.0.</span></span>

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

### <span data-ttu-id="cf72b-268">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="cf72b-268">-ThrottleLimit</span></span>

<span data-ttu-id="cf72b-269">Gibt an, wie viele Skriptblöcke parallel ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-269">Specifies the number of script blocks that in parallel.</span></span> <span data-ttu-id="cf72b-270">Eingabe Objekte werden blockiert, bis die Anzahl der ausgefallenen Skriptblöcke unter den **throttlelimit** fällt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-270">Input objects are blocked until the running script block count falls below the **ThrottleLimit**.</span></span> <span data-ttu-id="cf72b-271">Der Standardwert ist `5`.</span><span class="sxs-lookup"><span data-stu-id="cf72b-271">The default value is `5`.</span></span>

<span data-ttu-id="cf72b-272">Dieser Parameter wurde in PowerShell 7,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-272">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cf72b-273">-TimeoutSeconds</span><span class="sxs-lookup"><span data-stu-id="cf72b-273">-TimeoutSeconds</span></span>

<span data-ttu-id="cf72b-274">Gibt die Anzahl der Sekunden an, die gewartet werden soll, bis alle Eingaben parallel verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-274">Specifies the number of seconds to wait for all input to be processed in parallel.</span></span> <span data-ttu-id="cf72b-275">Nach der angegebenen Timeout Zeit werden alle laufenden Skripts angehalten.</span><span class="sxs-lookup"><span data-stu-id="cf72b-275">After the specified timeout time, all running scripts are stopped.</span></span> <span data-ttu-id="cf72b-276">Und alle verbleibenden zu verarbeitenden Eingabe Objekte werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="cf72b-276">And any remaining input objects to be processed are ignored.</span></span> <span data-ttu-id="cf72b-277">Der Standardwert `0` deaktiviert den Timeout und `ForEach-Object -Parallel` kann unbegrenzt ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-277">Default value of `0` disables the timeout, and `ForEach-Object -Parallel` can run indefinitely.</span></span> <span data-ttu-id="cf72b-278">Wenn <kbd></kbd>Sie + in der Befehlszeile STRG<kbd>C</kbd> eingeben, wird ein laufender `ForEach-Object -Parallel` Befehl beendet.</span><span class="sxs-lookup"><span data-stu-id="cf72b-278">Typing <kbd>Ctrl</kbd>+<kbd>C</kbd> at the command line stops a running `ForEach-Object -Parallel` command.</span></span> <span data-ttu-id="cf72b-279">Dieser Parameter kann nicht zusammen mit dem **AsJob** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-279">This parameter cannot be used along with the **AsJob** parameter.</span></span>

<span data-ttu-id="cf72b-280">Dieser Parameter wurde in PowerShell 7,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-280">This parameter was introduced in PowerShell 7.0.</span></span>

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

### <span data-ttu-id="cf72b-281">-Usenewrunspace</span><span class="sxs-lookup"><span data-stu-id="cf72b-281">-UseNewRunspace</span></span>

<span data-ttu-id="cf72b-282">Bewirkt, dass der parallele Aufruf einen neuen Runspace für jede Schleifen Iteration erstellt, anstatt Runspaces aus dem Runspace-Pool wieder zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-282">Causes the parallel invocation to create a new runspace for every loop iteration instead of reusing runspaces from the runspace pool.</span></span>

<span data-ttu-id="cf72b-283">Dieser Parameter wurde in PowerShell 7,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-283">This parameter was introduced in PowerShell 7.1</span></span>

```yml
Type: SwitchParameter
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cf72b-284">-AsJob</span><span class="sxs-lookup"><span data-stu-id="cf72b-284">-AsJob</span></span>

<span data-ttu-id="cf72b-285">Bewirkt, dass der parallele Aufruf als PowerShell-Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cf72b-285">Causes the parallel invocation to run as a PowerShell job.</span></span> <span data-ttu-id="cf72b-286">Anstelle der Ausgabe der ausgelaufenden Skriptblöcke wird ein einzelnes Auftrags Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cf72b-286">A single job object is returned instead of output from the running script blocks.</span></span> <span data-ttu-id="cf72b-287">Das Job-Objekt enthält untergeordnete Aufträge für jeden parallelen Skriptblock, der ausführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-287">The job object contains child jobs for each parallel script block that runs.</span></span> <span data-ttu-id="cf72b-288">Das Auftrags Objekt kann von allen PowerShell-Auftrags-Cmdlets verwendet werden, um den Status der Ausführung und das Abrufen von Daten zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-288">The job object can be used by all PowerShell job cmdlets, to monitor running state and retrieve data.</span></span>

<span data-ttu-id="cf72b-289">Dieser Parameter wurde in PowerShell 7,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-289">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cf72b-290">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cf72b-290">-Confirm</span></span>

<span data-ttu-id="cf72b-291">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="cf72b-291">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cf72b-292">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cf72b-292">-WhatIf</span></span>

<span data-ttu-id="cf72b-293">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cf72b-293">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="cf72b-294">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-294">The cmdlet is not run.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cf72b-295">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cf72b-295">CommonParameters</span></span>

<span data-ttu-id="cf72b-296">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cf72b-296">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cf72b-297">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cf72b-297">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cf72b-298">Eingaben</span><span class="sxs-lookup"><span data-stu-id="cf72b-298">Inputs</span></span>

### <span data-ttu-id="cf72b-299">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="cf72b-299">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="cf72b-300">Sie können jedes beliebige Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="cf72b-300">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="cf72b-301">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="cf72b-301">Outputs</span></span>

### <span data-ttu-id="cf72b-302">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="cf72b-302">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="cf72b-303">Dieses Cmdlet gibt Objekte zurück, die von der Eingabe bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-303">This cmdlet returns objects that are determined by the input.</span></span>

## <span data-ttu-id="cf72b-304">Notizen</span><span class="sxs-lookup"><span data-stu-id="cf72b-304">Notes</span></span>

- <span data-ttu-id="cf72b-305">Das- `ForEach-Object` Cmdlet funktioniert ähnlich wie die **foreach** -Anweisung, mit dem Unterschied, dass Sie Eingaben nicht an eine **foreach** -Anweisung übergeben können.</span><span class="sxs-lookup"><span data-stu-id="cf72b-305">The `ForEach-Object` cmdlet works much like the **Foreach** statement, except that you cannot pipe input to a **Foreach** statement.</span></span> <span data-ttu-id="cf72b-306">Weitere Informationen zur **foreach** -Anweisung finden Sie unter [about_Foreach](./About/about_Foreach.md).</span><span class="sxs-lookup"><span data-stu-id="cf72b-306">For more information about the **Foreach** statement, see [about_Foreach](./About/about_Foreach.md).</span></span>

- <span data-ttu-id="cf72b-307">Ab PowerShell 4,0 `Where` wurden-und-Methoden für die Verwendung mit-Auflistungen `ForEach` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cf72b-307">Starting in PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span> <span data-ttu-id="cf72b-308">Weitere Informationen zu diesen neuen Methoden finden Sie hier [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="cf72b-308">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

- <span data-ttu-id="cf72b-309">Der `ForEach-Object -Parallel` Parametersatz verwendet die interne PowerShell-API, um jeden Skriptblock auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cf72b-309">The `ForEach-Object -Parallel` parameter set uses PowerShell's internal API to run each script block.</span></span> <span data-ttu-id="cf72b-310">Dies ist deutlich mehr Aufwand als `ForEach-Object` bei der sequenziellen Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="cf72b-310">This is significantly more overhead than running `ForEach-Object` normally with sequential processing.</span></span> <span data-ttu-id="cf72b-311">Es ist wichtig, **parallel** zu verwenden, wenn der mehr Aufwand für die parallele Ausführung im Vergleich zu den vom Skriptblock ausgeführten Arbeiten gering ist.</span><span class="sxs-lookup"><span data-stu-id="cf72b-311">It is important to use **Parallel** where the overhead of running in parallel is small compared to work the script block performs.</span></span> <span data-ttu-id="cf72b-312">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cf72b-312">For example:</span></span>

  - <span data-ttu-id="cf72b-313">Rechenintensive Skripts auf mehr Kern Computern</span><span class="sxs-lookup"><span data-stu-id="cf72b-313">Compute intensive scripts on multi-core machines</span></span>
  - <span data-ttu-id="cf72b-314">Skripts, die Zeit für das warten auf Ergebnisse oder Datei Vorgänge aufwenden</span><span class="sxs-lookup"><span data-stu-id="cf72b-314">Scripts that spend time waiting for results or doing file operations</span></span>

  <span data-ttu-id="cf72b-315">Die Verwendung des **parallel** -Parameters kann bewirken, dass Skripts wesentlich langsamer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-315">Using the **Parallel** parameter can cause scripts to run much slower than normal.</span></span> <span data-ttu-id="cf72b-316">Insbesondere, wenn die parallelen Skripts trivial sind.</span><span class="sxs-lookup"><span data-stu-id="cf72b-316">Especially if the parallel scripts are trivial.</span></span> <span data-ttu-id="cf72b-317">Experimentieren Sie mit **parallel** , um herauszufinden, wo es nützlich sein kann.</span><span class="sxs-lookup"><span data-stu-id="cf72b-317">Experiment with **Parallel** to discover where it can be beneficial.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="cf72b-318">Der `ForEach-Object -Parallel` Parametersatz führt Skriptblöcke parallel in separaten Prozessthreads aus.</span><span class="sxs-lookup"><span data-stu-id="cf72b-318">The `ForEach-Object -Parallel` parameter set runs script blocks in parallel on separate process threads.</span></span> <span data-ttu-id="cf72b-319">Das- `$using:` Schlüsselwort ermöglicht das Übergeben von Variablen verweisen vom Cmdlet-Aufruf Thread an jeden Skriptblock Thread, der ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cf72b-319">The `$using:` keyword allows passing variable references from the cmdlet invocation thread to each running script block thread.</span></span> <span data-ttu-id="cf72b-320">Da die Skriptblöcke in verschiedenen Threads ausgeführt werden, müssen die als Verweis übergebenen Objektvariablen sicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf72b-320">Since the script blocks run in different threads, the object variables passed by reference must be used safely.</span></span> <span data-ttu-id="cf72b-321">Im Allgemeinen ist es sicher, aus referenzierten Objekten zu lesen, die sich nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="cf72b-321">Generally it is safe to read from referenced objects that don't change.</span></span> <span data-ttu-id="cf72b-322">Wenn der Objektstatus jedoch geändert wird, müssen Sie Thread sichere Objekte verwenden, wie z. b. .net **System. Collection. Concurrent** -Typen (siehe Beispiel 11).</span><span class="sxs-lookup"><span data-stu-id="cf72b-322">But if the object state is being modified then you must used thread safe objects, such as .Net **System.Collection.Concurrent** types (See Example 11).</span></span>

## <span data-ttu-id="cf72b-323">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="cf72b-323">Related links</span></span>

[<span data-ttu-id="cf72b-324">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="cf72b-324">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="cf72b-325">Where-Object</span><span class="sxs-lookup"><span data-stu-id="cf72b-325">Where-Object</span></span>](Where-Object.md)

[<span data-ttu-id="cf72b-326">Group-Object</span><span class="sxs-lookup"><span data-stu-id="cf72b-326">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="cf72b-327">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="cf72b-327">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="cf72b-328">New-Object</span><span class="sxs-lookup"><span data-stu-id="cf72b-328">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="cf72b-329">Select-Object</span><span class="sxs-lookup"><span data-stu-id="cf72b-329">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="cf72b-330">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="cf72b-330">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="cf72b-331">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="cf72b-331">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
