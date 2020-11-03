---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 5a1a53c2b312ef36c80ecfb2a771d2fee2ebea7f
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "93219887"
---
# <span data-ttu-id="1803d-103">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="1803d-103">ForEach-Object</span></span>

## <span data-ttu-id="1803d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1803d-104">SYNOPSIS</span></span>
<span data-ttu-id="1803d-105">Führt einen Vorgang für jedes Element in einer Auflistung von Eingabeobjekten aus.</span><span class="sxs-lookup"><span data-stu-id="1803d-105">Performs an operation against each item in a collection of input objects.</span></span>

## <span data-ttu-id="1803d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1803d-106">SYNTAX</span></span>

### <span data-ttu-id="1803d-107">Scriptblockset (Standard)</span><span class="sxs-lookup"><span data-stu-id="1803d-107">ScriptBlockSet (Default)</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1803d-108">Propertyandmethodset</span><span class="sxs-lookup"><span data-stu-id="1803d-108">PropertyAndMethodSet</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1803d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1803d-109">DESCRIPTION</span></span>

<span data-ttu-id="1803d-110">Das- `ForEach-Object` Cmdlet führt einen Vorgang für jedes Element in einer Auflistung von Eingabe Objekten aus.</span><span class="sxs-lookup"><span data-stu-id="1803d-110">The `ForEach-Object` cmdlet performs an operation on each item in a collection of input objects.</span></span> <span data-ttu-id="1803d-111">Die Eingabe Objekte können an das Cmdlet weitergeleitet oder mithilfe des **Inputobject** -Parameters angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1803d-111">The input objects can be piped to the cmdlet or specified by using the **InputObject** parameter.</span></span>

<span data-ttu-id="1803d-112">Ab Windows PowerShell 3,0 gibt es zwei verschiedene Möglichkeiten, einen Befehl zu erstellen `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="1803d-112">Starting in Windows PowerShell 3.0, there are two different ways to construct a `ForEach-Object` command.</span></span>

- <span data-ttu-id="1803d-113">**Skriptblock**.</span><span class="sxs-lookup"><span data-stu-id="1803d-113">**Script block**.</span></span> <span data-ttu-id="1803d-114">Sie können einen Skriptblock verwenden, um den Vorgang anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1803d-114">You can use a script block to specify the operation.</span></span> <span data-ttu-id="1803d-115">Verwenden Sie innerhalb des Skript Blocks die- `$_` Variable, um das aktuelle-Objekt darzustellen.</span><span class="sxs-lookup"><span data-stu-id="1803d-115">Within the script block, use the `$_` variable to represent the current object.</span></span> <span data-ttu-id="1803d-116">Der Skriptblock ist der Wert des **Process** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="1803d-116">The script block is the value of the **Process** parameter.</span></span> <span data-ttu-id="1803d-117">Der Skriptblock kann beliebige PowerShell-Skripts enthalten.</span><span class="sxs-lookup"><span data-stu-id="1803d-117">The script block can contain any PowerShell script.</span></span>

  <span data-ttu-id="1803d-118">Der folgende Befehl ruft beispielsweise den Wert der **ProcessName** -Eigenschaft der einzelnen Prozesse auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="1803d-118">For example, the following command gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object {$_.ProcessName}`

  <span data-ttu-id="1803d-119">`ForEach-Object` unterstützt `begin` die `process` Blöcke, und, `end` wie in [about_functions](about/about_functions.md#piping-objects-to-functions)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1803d-119">`ForEach-Object` supports the `begin`, `process`, and `end` blocks as described in [about_functions](about/about_functions.md#piping-objects-to-functions).</span></span>

  > [!NOTE]
  > <span data-ttu-id="1803d-120">Die Skriptblöcke werden im Gültigkeitsbereich des Aufrufers ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1803d-120">The script blocks run in the caller's scope.</span></span> <span data-ttu-id="1803d-121">Daher haben die Blöcke Zugriff auf Variablen in diesem Bereich und können neue Variablen erstellen, die in diesem Bereich beibehalten werden, nachdem das Cmdlet abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1803d-121">Therefore the blocks have access to variables in that scope and can create new variables that persist in that scope after the cmdlet completes.</span></span>

- <span data-ttu-id="1803d-122">**Operation-Anweisung**.</span><span class="sxs-lookup"><span data-stu-id="1803d-122">**Operation statement**.</span></span> <span data-ttu-id="1803d-123">Sie können auch eine Vorgangs Anweisung schreiben, die in natürlicher Sprache sehr viel ähnlicher ist.</span><span class="sxs-lookup"><span data-stu-id="1803d-123">You can also write an operation statement, which is much more like natural language.</span></span> <span data-ttu-id="1803d-124">Sie können die Vorgangsanweisung verwenden, um einen Eigenschaftenwert anzugeben oder eine Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="1803d-124">You can use the operation statement to specify a property value or call a method.</span></span> <span data-ttu-id="1803d-125">Vorgangsanweisungen wurden in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1803d-125">Operation statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="1803d-126">Der folgende Befehl ruft beispielsweise ebenfalls den Wert der **ProcessName** -Eigenschaft der einzelnen Prozesse auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="1803d-126">For example, the following command also gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object ProcessName`

## <span data-ttu-id="1803d-127">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1803d-127">EXAMPLES</span></span>

### <span data-ttu-id="1803d-128">Beispiel 1: Teilen von ganzen Zahlen in einem Array</span><span class="sxs-lookup"><span data-stu-id="1803d-128">Example 1: Divide integers in an array</span></span>

<span data-ttu-id="1803d-129">In diesem Beispiel wird ein Array von drei ganzen Zahlen angenommen, und jedes dieser Elemente wird durch 1024 dividiert.</span><span class="sxs-lookup"><span data-stu-id="1803d-129">This example takes an array of three integers and divides each one of them by 1024.</span></span>

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### <span data-ttu-id="1803d-130">Beispiel 2: erhalten der Länge aller Dateien in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="1803d-130">Example 2: Get the length of all the files in a directory</span></span>

<span data-ttu-id="1803d-131">In diesem Beispiel werden die Dateien und Verzeichnisse im PowerShell-Installationsverzeichnis verarbeitet `$PSHOME` .</span><span class="sxs-lookup"><span data-stu-id="1803d-131">This example processes the files and directories in the PowerShell installation directory `$PSHOME`.</span></span>

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

<span data-ttu-id="1803d-132">Wenn das Objekt kein Verzeichnis ist, ruft der Skriptblock den Namen der Datei ab, teilt den Wert der **length** -Eigenschaft durch 1024 und fügt ein Leerzeichen ("") hinzu, um es vom nächsten Eintrag zu trennen.</span><span class="sxs-lookup"><span data-stu-id="1803d-132">If the object is not a directory, the script block gets the name of the file, divides the value of its **Length** property by 1024, and adds a space (" ") to separate it from the next entry.</span></span> <span data-ttu-id="1803d-133">Mit dem-Cmdlet wird die **psiscontainer** -Eigenschaft verwendet, um zu bestimmen, ob ein Objekt ein Verzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="1803d-133">The cmdlet uses the **PSISContainer** property to determine whether an object is a directory.</span></span>

### <span data-ttu-id="1803d-134">Beispiel 3: Arbeiten mit den neuesten System Ereignissen</span><span class="sxs-lookup"><span data-stu-id="1803d-134">Example 3: Operate on the most recent System events</span></span>

<span data-ttu-id="1803d-135">In diesem Beispiel werden die 1000 aktuellsten Ereignisse aus dem System Ereignisprotokoll in eine Textdatei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="1803d-135">This example write the 1000 most recent events from the System event log to a text file.</span></span> <span data-ttu-id="1803d-136">Die aktuelle Zeit wird vor und nach der Verarbeitung der Ereignisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1803d-136">The current time is displayed before and after processing the events.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

<span data-ttu-id="1803d-137">`Get-EventLog` Ruft die 1000 aktuellsten Ereignisse aus dem System Ereignisprotokoll ab und speichert Sie in der `$Events` Variablen.</span><span class="sxs-lookup"><span data-stu-id="1803d-137">`Get-EventLog` gets the 1000 most recent events from the System event log and stores them in the `$Events` variable.</span></span> <span data-ttu-id="1803d-138">`$Events` wird dann an das `ForEach-Object` Cmdlet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="1803d-138">`$Events` is then piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="1803d-139">Der **Begin** -Parameter zeigt das aktuelle Datum und die Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="1803d-139">The **Begin** parameter displays the current date and time.</span></span> <span data-ttu-id="1803d-140">Als Nächstes verwendet der **Process** -Parameter das `Out-File` -Cmdlet, um eine Textdatei mit dem Namen events.txt zu erstellen, und speichert die Message-Eigenschaft der einzelnen Ereignisse in dieser Datei.</span><span class="sxs-lookup"><span data-stu-id="1803d-140">Next, the **Process** parameter uses the `Out-File` cmdlet to create a text file that is named events.txt and stores the message property of each of the events in that file.</span></span> <span data-ttu-id="1803d-141">Schließlich wird der **End** -Parameter verwendet, um das Datum und die Uhrzeit anzuzeigen, zu denen die gesamte Verarbeitung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1803d-141">Last, the **End** parameter is used to display the date and time after all of the processing has completed.</span></span>

### <span data-ttu-id="1803d-142">Beispiel 4: Ändern des Werts eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="1803d-142">Example 4: Change the value of a Registry key</span></span>

<span data-ttu-id="1803d-143">In diesem Beispiel wird der Wert des **remotePath** -Registrierungs Eintrags in allen unter Schlüsseln unter dem `HKCU:\Network` Schlüssel in Großbuchstaben geändert.</span><span class="sxs-lookup"><span data-stu-id="1803d-143">This example changes the value of the **RemotePath** registry entry in all of the subkeys under the `HKCU:\Network` key to uppercase text.</span></span>

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

<span data-ttu-id="1803d-144">Sie können dieses Format verwenden,um die Form oder den Inhalt eines Registrierungseintragswerts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1803d-144">You can use this format to change the form or content of a registry entry value.</span></span>

<span data-ttu-id="1803d-145">Jeder Unterschlüssel im **Network** -Schlüssel stellt ein zugeordnetes Netzwerklaufwerk dar, das bei der Anmeldung neu verbunden wird.</span><span class="sxs-lookup"><span data-stu-id="1803d-145">Each subkey in the **Network** key represents a mapped network drive that will reconnect at logon.</span></span>
<span data-ttu-id="1803d-146">Der **RemotePath** -Eintrag enthält den UNC-Pfad des verbundenen Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="1803d-146">The **RemotePath** entry contains the UNC path of the connected drive.</span></span> <span data-ttu-id="1803d-147">Wenn Sie z. b. das Laufwerk E: zu `\\Server\Share` zuordnen, wird ein **e** -Unterschlüssel von `HKCU:\Network` und der Wert des **remotePath** -Registrierungs Eintrags im **E** -Unterschlüssel ist `\\Server\Share` .</span><span class="sxs-lookup"><span data-stu-id="1803d-147">For example, if you map the E: drive to `\\Server\Share`, there will be an **E** subkey of `HKCU:\Network` and the value of the **RemotePath** registry entry in the **E** subkey is `\\Server\Share`.</span></span>

<span data-ttu-id="1803d-148">Der Befehl verwendet das `Get-ItemProperty` Cmdlet, um alle untergeordneten Schlüssel des **Netzwerk** Schlüssels zu erhalten, und das `Set-ItemProperty` Cmdlet, um den Wert des **remotePath** -Registrierungs Eintrags in jedem Schlüssel zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1803d-148">The command uses the `Get-ItemProperty` cmdlet to get all of the subkeys of the **Network** key and the `Set-ItemProperty` cmdlet to change the value of the **RemotePath** registry entry in each key.</span></span>
<span data-ttu-id="1803d-149">Im- `Set-ItemProperty` Befehl ist der Pfad der Wert der **pspath** -Eigenschaft des Registrierungsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="1803d-149">In the `Set-ItemProperty` command, the path is the value of the **PSPath** property of the registry key.</span></span> <span data-ttu-id="1803d-150">Dies ist eine Eigenschaft des Microsoft .NET Framework-Objekts, das den Registrierungsschlüssel darstellt, nicht einen Registrierungs Eintrag.</span><span class="sxs-lookup"><span data-stu-id="1803d-150">This is a property of the Microsoft .NET Framework object that represents the registry key, not a registry entry.</span></span> <span data-ttu-id="1803d-151">Der Befehl verwendet die **touppermethode ()** des **remotePath** -Werts, bei der es sich um eine Zeichenfolge (REG_SZ) handelt.</span><span class="sxs-lookup"><span data-stu-id="1803d-151">The command uses the **ToUpper()** method of the **RemotePath** value, which is a string (REG_SZ).</span></span>

<span data-ttu-id="1803d-152">Da `Set-ItemProperty` die-Eigenschaft jedes Schlüssels ändert, ist das `ForEach-Object` Cmdlet für den Zugriff auf die-Eigenschaft erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1803d-152">Because `Set-ItemProperty` is changing the property of each key, the `ForEach-Object` cmdlet is required to access the property.</span></span>

### <span data-ttu-id="1803d-153">Beispiel 5: Verwenden der automatischen $NULL Variablen</span><span class="sxs-lookup"><span data-stu-id="1803d-153">Example 5: Use the $Null automatic variable</span></span>

<span data-ttu-id="1803d-154">In diesem Beispiel wird gezeigt, wie die `$Null` Automatische Variable an das `ForEach-Object` Cmdlet weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="1803d-154">This example shows the effect of piping the `$Null` automatic variable to the `ForEach-Object` cmdlet.</span></span>

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

<span data-ttu-id="1803d-155">Da PowerShell NULL als expliziten Platzhalter behandelt, `ForEach-Object` generiert das Cmdlet einen Wert für `$Null` , genau wie bei anderen Objekten, die an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="1803d-155">Because PowerShell treats null as an explicit placeholder, the `ForEach-Object` cmdlet generates a value for `$Null`, just as it does for other objects that you pipe to it.</span></span>

### <span data-ttu-id="1803d-156">Beispiel 6: erhalten von Eigenschafts Werten</span><span class="sxs-lookup"><span data-stu-id="1803d-156">Example 6: Get property values</span></span>

<span data-ttu-id="1803d-157">In diesem Beispiel wird der Wert der **path** -Eigenschaft aller installierten PowerShell-Module mithilfe des **Mitgliedschafts Namen** -Parameters des `ForEach-Object` Cmdlets abgerufen.</span><span class="sxs-lookup"><span data-stu-id="1803d-157">This example gets the value of the **Path** property of all installed PowerShell modules by using the **MemberName** parameter of the `ForEach-Object` cmdlet.</span></span>

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

<span data-ttu-id="1803d-158">Der zweite Befehl entspricht dem ersten.</span><span class="sxs-lookup"><span data-stu-id="1803d-158">The second command is equivalent to the first.</span></span> <span data-ttu-id="1803d-159">Er verwendet den `Foreach` Alias des `ForEach-Object` Cmdlets und lässt den Namen des **Mitgliedsnamen** -Parameters aus, der optional ist.</span><span class="sxs-lookup"><span data-stu-id="1803d-159">It uses the `Foreach` alias of the `ForEach-Object` cmdlet and omits the name of the **MemberName** parameter, which is optional.</span></span>

<span data-ttu-id="1803d-160">Das `ForEach-Object` Cmdlet ist für das Abrufen von Eigenschafts Werten sehr nützlich, da es den Wert abruft, ohne den Typ zu ändern, im Gegensatz zu den **Format** -Cmdlets oder dem `Select-Object` Cmdlet, die den Eigenschafts Werttyp ändern.</span><span class="sxs-lookup"><span data-stu-id="1803d-160">The `ForEach-Object` cmdlet is very useful for getting property values, because it gets the value without changing the type, unlike the **Format** cmdlets or the `Select-Object` cmdlet, which change the property value type.</span></span>

### <span data-ttu-id="1803d-161">Beispiel 7: Aufteilen von Modulnamen in Komponentennamen</span><span class="sxs-lookup"><span data-stu-id="1803d-161">Example 7: Split module names into component names</span></span>

<span data-ttu-id="1803d-162">Diese Beispiele zeigen drei Möglichkeiten, zwei durch Punkte getrennte Modulnamen in Ihre Komponentennamen aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="1803d-162">This examples shows three ways to split two dot-separated module names into their component names.</span></span>

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

<span data-ttu-id="1803d-163">Die Befehle rufen die **Split** Methode von Zeichenfolgen auf.</span><span class="sxs-lookup"><span data-stu-id="1803d-163">The commands call the **Split** method of strings.</span></span> <span data-ttu-id="1803d-164">Die drei Befehle verwenden unterschiedliche Syntax, sind aber äquivalent und austauschbar.</span><span class="sxs-lookup"><span data-stu-id="1803d-164">The three commands use different syntax, but they are equivalent and interchangeable.</span></span>

<span data-ttu-id="1803d-165">Der erste Befehl verwendet die herkömmliche Syntax, die einen Skriptblock und den aktuellen Objekt Operator enthält `$_` .</span><span class="sxs-lookup"><span data-stu-id="1803d-165">The first command uses the traditional syntax, which includes a script block and the current object operator `$_`.</span></span> <span data-ttu-id="1803d-166">Es verwendet die Punktsyntax zum Angeben der Methode und die Klammern, um das Trennzeichenargument einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1803d-166">It uses the dot syntax to specify the method and parentheses to enclose the delimiter argument.</span></span>

<span data-ttu-id="1803d-167">Der zweite Befehl verwendet den **MemberName** -Parameter, um die **Split** -Methode anzugeben,und den **ArgumentName** -Parameter, um den Punkt („.“) als das Teilungstrennzeichen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1803d-167">The second command uses the **MemberName** parameter to specify the **Split** method and the **ArgumentName** parameter to identify the dot (".") as the split delimiter.</span></span>

<span data-ttu-id="1803d-168">Der dritte Befehl verwendet den **foreach** -Alias des `ForEach-Object` Cmdlets und lässt die Namen der Parameter " **Membership Name** " und "Argument **List** " aus, die optional sind.</span><span class="sxs-lookup"><span data-stu-id="1803d-168">The third command uses the **Foreach** alias of the `ForEach-Object` cmdlet and omits the names of the **MemberName** and **ArgumentList** parameters, which are optional.</span></span>

### <span data-ttu-id="1803d-169">Beispiel 8: Verwenden von ForEach-Object mit zwei Skript Blöcken</span><span class="sxs-lookup"><span data-stu-id="1803d-169">Example 8: Using ForEach-Object with two script blocks</span></span>

<span data-ttu-id="1803d-170">In diesem Beispiel übergeben wir zwei Skriptblöcke in der gleichen Weise.</span><span class="sxs-lookup"><span data-stu-id="1803d-170">In this example we pass two script blocks positionally.</span></span> <span data-ttu-id="1803d-171">Alle Skriptblöcke werden an den **Prozess** Parameter gebunden.</span><span class="sxs-lookup"><span data-stu-id="1803d-171">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="1803d-172">Sie werden jedoch so behandelt, als würden Sie an den **Begin** -und den **Process** -Parameter übermittelt.</span><span class="sxs-lookup"><span data-stu-id="1803d-172">However, they are treated as if they had been passed to the **Begin** and **Process** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### <span data-ttu-id="1803d-173">Beispiel 9: Verwenden von ForEach-Object mit mehr als zwei Skript Blöcken</span><span class="sxs-lookup"><span data-stu-id="1803d-173">Example 9: Using ForEach-Object with more than two script blocks</span></span>

<span data-ttu-id="1803d-174">In diesem Beispiel übergeben wir zwei Skriptblöcke in der gleichen Weise.</span><span class="sxs-lookup"><span data-stu-id="1803d-174">In this example we pass two script blocks positionally.</span></span> <span data-ttu-id="1803d-175">Alle Skriptblöcke werden an den **Prozess** Parameter gebunden.</span><span class="sxs-lookup"><span data-stu-id="1803d-175">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="1803d-176">Sie werden jedoch so behandelt, als wären Sie an die **Begin** -, **Process** -und **End** -Parameter übergebenen.</span><span class="sxs-lookup"><span data-stu-id="1803d-176">However, they are treated as if they had been passed to the **Begin** , **Process** , and **End** parameters.</span></span>

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
> <span data-ttu-id="1803d-177">Der erste Skriptblock wird immer dem Block zugeordnet `begin` , der letzte Block wird dem `end` Block zugeordnet, und die Blöcke dazwischen werden alle dem `process` Block zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1803d-177">The first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

### <span data-ttu-id="1803d-178">Beispiel 10: Ausführen mehrerer Skriptblöcke für jedes Pipeline Element</span><span class="sxs-lookup"><span data-stu-id="1803d-178">Example 10: Run multiple script blocks for each pipeline item</span></span>

<span data-ttu-id="1803d-179">Wie im vorherigen Beispiel gezeigt, werden mehrere Skriptblöcke, die mit dem **Process** -Parameter übergeben wurden, den **Begin** -und **End** -Parametern zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1803d-179">As shown in the previous example, multiple script blocks passed using the **Process** parameter get mapped to the **Begin** and **End** parameters.</span></span> <span data-ttu-id="1803d-180">Um diese Zuordnung zu vermeiden, müssen Sie explizite Werte für die **Begin** -und **End** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="1803d-180">To avoid this mapping, you must provide explicit values for the **Begin** and **End** parameters.</span></span>

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

## <span data-ttu-id="1803d-181">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1803d-181">PARAMETERS</span></span>

### <span data-ttu-id="1803d-182">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="1803d-182">-ArgumentList</span></span>

<span data-ttu-id="1803d-183">Gibt ein Array von Argumenten für einen Methoden aufzurufenden an.</span><span class="sxs-lookup"><span data-stu-id="1803d-183">Specifies an array of arguments to a method call.</span></span> <span data-ttu-id="1803d-184">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="1803d-184">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="1803d-185">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1803d-185">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="1803d-186">-BEGIN</span><span class="sxs-lookup"><span data-stu-id="1803d-186">-Begin</span></span>

<span data-ttu-id="1803d-187">Gibt einen Skriptblock an, der ausgeführt wird, bevor dieses Cmdlet Eingabe Objekte verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="1803d-187">Specifies a script block that runs before this cmdlet processes any input objects.</span></span> <span data-ttu-id="1803d-188">Dieser Skriptblock wird nur einmal für die gesamte Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1803d-188">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="1803d-189">Weitere Informationen zum- `begin` Block finden Sie unter [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="1803d-189">For more information about the `begin` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

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

### <span data-ttu-id="1803d-190">-Ende</span><span class="sxs-lookup"><span data-stu-id="1803d-190">-End</span></span>

<span data-ttu-id="1803d-191">Gibt einen Skriptblock an, der ausgeführt wird, nachdem dieses Cmdlet alle Eingabe Objekte verarbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="1803d-191">Specifies a script block that runs after this cmdlet processes all input objects.</span></span> <span data-ttu-id="1803d-192">Dieser Skriptblock wird nur einmal für die gesamte Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1803d-192">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="1803d-193">Weitere Informationen zum- `end` Block finden Sie unter [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="1803d-193">For more information about the `end` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

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

### <span data-ttu-id="1803d-194">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1803d-194">-InputObject</span></span>

<span data-ttu-id="1803d-195">Gibt die Eingabeobjekte an.</span><span class="sxs-lookup"><span data-stu-id="1803d-195">Specifies the input objects.</span></span> <span data-ttu-id="1803d-196">`ForEach-Object` führt den Skriptblock oder die Vorgangs Anweisung für jedes Eingabe Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="1803d-196">`ForEach-Object` runs the script block or operation statement on each input object.</span></span> <span data-ttu-id="1803d-197">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1803d-197">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="1803d-198">Wenn Sie den **Inputobject** -Parameter mit verwenden `ForEach-Object` , anstatt Befehls Ergebnisse an zu übergeben `ForEach-Object` , wird der **Inputobject** -Wert als einzelnes Objekt behandelt.</span><span class="sxs-lookup"><span data-stu-id="1803d-198">When you use the **InputObject** parameter with `ForEach-Object`, instead of piping command results to `ForEach-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="1803d-199">Dies gilt auch, wenn der Wert eine Auflistung ist, die das Ergebnis eines Befehls ist, z `-InputObject (Get-Process)` . b..</span><span class="sxs-lookup"><span data-stu-id="1803d-199">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span>
<span data-ttu-id="1803d-200">Da **Inputobject** keine einzelnen Eigenschaften aus einem Array oder einer Auflistung von Objekten zurückgeben kann, empfiehlt es sich, wenn Sie verwenden, `ForEach-Object` um Vorgänge für eine Auflistung von Objekten für Objekte mit spezifischen Werten in definierten Eigenschaften auszuführen, `ForEach-Object` wie in den Beispielen in diesem Thema gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1803d-200">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that if you use `ForEach-Object` to perform operations on a collection of objects for those objects that have specific values in defined properties, you use `ForEach-Object` in the pipeline, as shown in the examples in this topic.</span></span>

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

### <span data-ttu-id="1803d-201">-Mitgliedsname</span><span class="sxs-lookup"><span data-stu-id="1803d-201">-MemberName</span></span>

<span data-ttu-id="1803d-202">Gibt die abzurufende Eigenschaft oder die aufzurufende Methode an.</span><span class="sxs-lookup"><span data-stu-id="1803d-202">Specifies the property to get or the method to call.</span></span>

<span data-ttu-id="1803d-203">Platzhalter Zeichen sind zulässig, funktionieren jedoch nur, wenn die resultierende Zeichenfolge in einen eindeutigen Wert aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="1803d-203">Wildcard characters are permitted, but work only if the resulting string resolves to a unique value.</span></span>
<span data-ttu-id="1803d-204">Wenn Sie z. b. Ausführen `Get-Process | ForEach -MemberName *Name` und mehr als ein Element mit einem Namen vorhanden ist, der den Zeichen folgen Namen enthält, z. b. die Eigenschaften **ProcessName** und **Name** , schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="1803d-204">If, for example, you run `Get-Process | ForEach -MemberName *Name`, and more than one member exists with a name that contains the string Name, such as the **ProcessName** and **Name** properties, the command fails.</span></span>

<span data-ttu-id="1803d-205">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1803d-205">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="1803d-206">-Prozess</span><span class="sxs-lookup"><span data-stu-id="1803d-206">-Process</span></span>

<span data-ttu-id="1803d-207">Gibt den Vorgang an, der für jedes Eingabeobjekt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1803d-207">Specifies the operation that is performed on each input object.</span></span> <span data-ttu-id="1803d-208">Dieser Skriptblock wird für jedes Objekt in der Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1803d-208">This script block is run for every object in the pipeline.</span></span> <span data-ttu-id="1803d-209">Weitere Informationen zum- `process` Block finden Sie unter [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="1803d-209">For more information about the `process` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

<span data-ttu-id="1803d-210">Wenn Sie dem **Prozess** Parameter mehrere Skriptblöcke bereitstellen, wird der erste Skriptblock immer dem Block zugeordnet `begin` .</span><span class="sxs-lookup"><span data-stu-id="1803d-210">When you provide multiple script blocks to the **Process** parameter, the first script block is always mapped to the `begin` block.</span></span> <span data-ttu-id="1803d-211">Wenn nur zwei Skriptblöcke vorhanden sind, wird der zweite Block dem Block zugeordnet `process` .</span><span class="sxs-lookup"><span data-stu-id="1803d-211">If there are only two script blocks, the second block is mapped to the `process` block.</span></span> <span data-ttu-id="1803d-212">Wenn es drei oder mehr Skriptblöcke gibt, wird der erste Skriptblock immer dem `begin` Block zugeordnet, der letzte Block wird dem Block zugeordnet `end` , und die Blöcke dazwischen werden alle dem `process` Block zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1803d-212">If there are three or more script blocks, first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

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

### <span data-ttu-id="1803d-213">-Restingscripts</span><span class="sxs-lookup"><span data-stu-id="1803d-213">-RemainingScripts</span></span>

<span data-ttu-id="1803d-214">Gibt alle Skriptblöcke an, die nicht vom **Prozess** Parameter übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="1803d-214">Specifies all script blocks that are not taken by the **Process** parameter.</span></span>

<span data-ttu-id="1803d-215">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1803d-215">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="1803d-216">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1803d-216">-Confirm</span></span>

<span data-ttu-id="1803d-217">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="1803d-217">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1803d-218">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1803d-218">-WhatIf</span></span>

<span data-ttu-id="1803d-219">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1803d-219">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1803d-220">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1803d-220">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1803d-221">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1803d-221">CommonParameters</span></span>

<span data-ttu-id="1803d-222">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1803d-222">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1803d-223">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1803d-223">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1803d-224">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1803d-224">INPUTS</span></span>

### <span data-ttu-id="1803d-225">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="1803d-225">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1803d-226">Sie können jedes beliebige Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="1803d-226">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="1803d-227">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1803d-227">OUTPUTS</span></span>

### <span data-ttu-id="1803d-228">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="1803d-228">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1803d-229">Dieses Cmdlet gibt Objekte zurück, die von der Eingabe bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="1803d-229">This cmdlet returns objects that are determined by the input.</span></span>

## <span data-ttu-id="1803d-230">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1803d-230">NOTES</span></span>

- <span data-ttu-id="1803d-231">Das- `ForEach-Object` Cmdlet funktioniert ähnlich wie die **foreach** -Anweisung, mit dem Unterschied, dass Sie Eingaben nicht an eine **foreach** -Anweisung übergeben können.</span><span class="sxs-lookup"><span data-stu-id="1803d-231">The `ForEach-Object` cmdlet works much like the **Foreach** statement, except that you cannot pipe input to a **Foreach** statement.</span></span> <span data-ttu-id="1803d-232">Weitere Informationen zur **foreach** -Anweisung finden Sie unter [about_Foreach](./About/about_Foreach.md).</span><span class="sxs-lookup"><span data-stu-id="1803d-232">For more information about the **Foreach** statement, see [about_Foreach](./About/about_Foreach.md).</span></span>

- <span data-ttu-id="1803d-233">Ab PowerShell 4,0 `Where` wurden-und-Methoden für die Verwendung mit-Auflistungen `ForEach` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1803d-233">Starting in PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span> <span data-ttu-id="1803d-234">Weitere Informationen zu diesen neuen Methoden finden Sie hier [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="1803d-234">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="1803d-235">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1803d-235">RELATED LINKS</span></span>

[<span data-ttu-id="1803d-236">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="1803d-236">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="1803d-237">Where-Object</span><span class="sxs-lookup"><span data-stu-id="1803d-237">Where-Object</span></span>](Where-Object.md)

[<span data-ttu-id="1803d-238">Group-Object</span><span class="sxs-lookup"><span data-stu-id="1803d-238">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="1803d-239">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="1803d-239">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="1803d-240">New-Object</span><span class="sxs-lookup"><span data-stu-id="1803d-240">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="1803d-241">Select-Object</span><span class="sxs-lookup"><span data-stu-id="1803d-241">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="1803d-242">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="1803d-242">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="1803d-243">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="1803d-243">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
