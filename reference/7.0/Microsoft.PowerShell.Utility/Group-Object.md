---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/group-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Group-Object
ms.openlocfilehash: aa97115217be5363e2f81e87c4d6ce7e03c453a4
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219276"
---
# <span data-ttu-id="dcb93-103">Group-Object</span><span class="sxs-lookup"><span data-stu-id="dcb93-103">Group-Object</span></span>

## <span data-ttu-id="dcb93-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="dcb93-104">SYNOPSIS</span></span>
<span data-ttu-id="dcb93-105">Gruppiert Objekte, die den gleichen Wert für die angegebenen Eigenschaften enthalten.</span><span class="sxs-lookup"><span data-stu-id="dcb93-105">Groups objects that contain the same value for specified properties.</span></span>

## <span data-ttu-id="dcb93-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dcb93-106">SYNTAX</span></span>

### <span data-ttu-id="dcb93-107">Hash Tabelle</span><span class="sxs-lookup"><span data-stu-id="dcb93-107">HashTable</span></span>

```
Group-Object [-NoElement] [-AsHashTable] [-AsString] [-InputObject <PSObject>]
 [[-Property] <Object[]>] [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="dcb93-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dcb93-108">DESCRIPTION</span></span>

<span data-ttu-id="dcb93-109">Das- `Group-Object` Cmdlet zeigt Objekte in Gruppen basierend auf dem Wert einer angegebenen Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="dcb93-109">The `Group-Object` cmdlet displays objects in groups based on the value of a specified property.</span></span>
<span data-ttu-id="dcb93-110">`Group-Object` gibt eine Tabelle mit einer Zeile für jeden Eigenschafts Wert und eine Spalte zurück, die die Anzahl der Elemente mit diesem Wert anzeigt.</span><span class="sxs-lookup"><span data-stu-id="dcb93-110">`Group-Object` returns a table with one row for each property value and a column that displays the number of items with that value.</span></span>

<span data-ttu-id="dcb93-111">Wenn Sie mehr als eine Eigenschaft angeben, werden `Group-Object` diese zuerst nach den Werten der ersten Eigenschaft und dann innerhalb jeder Eigenschaften Gruppe nach dem Wert der nächsten Eigenschaft gruppiert.</span><span class="sxs-lookup"><span data-stu-id="dcb93-111">If you specify more than one property, `Group-Object` first groups them by the values of the first property, and then, within each property group, it groups by the value of the next property.</span></span>

<span data-ttu-id="dcb93-112">Ab PowerShell 7 `Group-Object` können die **CaseSensitive** -und **ashashtable** -Parameter kombiniert werden, um eine Hash Tabelle mit Berücksichtigung von Groß-und Kleinschreibung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dcb93-112">Beginning in PowerShell 7, `Group-Object` can combine the **CaseSensitive** and **AsHashtable** parameters to create a case-sensitive hash table.</span></span> <span data-ttu-id="dcb93-113">In den Hash Tabellen Schlüsseln werden Vergleiche unter Berücksichtigung der Groß-und Kleinschreibung verwendet und ein **System. Collections. Hashtable** -Objekt ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="dcb93-113">The hash table keys use case-sensitive comparisons and output a **System.Collections.Hashtable** object.</span></span>

## <span data-ttu-id="dcb93-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="dcb93-114">EXAMPLES</span></span>

### <span data-ttu-id="dcb93-115">Beispiel 1: Gruppieren von Dateien nach Erweiterung</span><span class="sxs-lookup"><span data-stu-id="dcb93-115">Example 1: Group files by extension</span></span>

<span data-ttu-id="dcb93-116">In diesem Beispiel werden die Dateien unter rekursiv abgerufen `$PSHOME` und nach der Dateinamenerweiterung gruppiert.</span><span class="sxs-lookup"><span data-stu-id="dcb93-116">This example recursively gets the files under `$PSHOME` and groups them by file name extension.</span></span> <span data-ttu-id="dcb93-117">Die Ausgabe wird an das `Sort-Object` Cmdlet gesendet, das Sie nach den für die angegebene Erweiterung gefundenen Anzahl Dateien sortiert.</span><span class="sxs-lookup"><span data-stu-id="dcb93-117">The output is sent to the `Sort-Object` cmdlet, which sorts them by the count files found for the given extension.</span></span> <span data-ttu-id="dcb93-118">Der leere **Name** stellt Verzeichnisse dar.</span><span class="sxs-lookup"><span data-stu-id="dcb93-118">The empty **Name** represents directories.</span></span>

<span data-ttu-id="dcb93-119">In diesem Beispiel wird der **noelement** -Parameter verwendet, um die Member der Gruppe auszulassen.</span><span class="sxs-lookup"><span data-stu-id="dcb93-119">This example uses the **NoElement** parameter to omit the members of the group.</span></span>

```powershell
$files = Get-ChildItem -Path $PSHOME -Recurse
$files | Group-Object -Property extension -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count Name
----- ----
  365 .xml
  231 .cdxml
  197
  169 .ps1xml
  142 .txt
  114 .psd1
   63 .psm1
   49 .xsd
   36 .dll
   15 .mfl
   15 .mof
...
```

### <span data-ttu-id="dcb93-120">Beispiel 2: Gruppieren von ganzen Zahlen nach Wahrscheinlichkeit und Evens</span><span class="sxs-lookup"><span data-stu-id="dcb93-120">Example 2: Group integers by odds and evens</span></span>

<span data-ttu-id="dcb93-121">In diesem Beispiel wird gezeigt, wie Skriptblöcke als Wert des **Property** -Parameters verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dcb93-121">This example shows how to use script blocks as the value of the **Property** parameter.</span></span> <span data-ttu-id="dcb93-122">Dieser Befehl zeigt die ganzen Zahlen von 1 bis 20 an, gruppiert nach Wahrscheinlichkeit und sogar.</span><span class="sxs-lookup"><span data-stu-id="dcb93-122">This command displays the integers from 1 to 20, grouped by odds and even.</span></span>

```powershell
1..20 | Group-Object -Property {$_ % 2}
```

```Output
Count Name                      Group
----- ----                      -----
   10 0                         {2, 4, 6, 8...}
   10 1                         {1, 3, 5, 7...}
```

### <span data-ttu-id="dcb93-123">Beispiel 3: Gruppieren von Ereignisprotokoll Ereignissen nach EntryType</span><span class="sxs-lookup"><span data-stu-id="dcb93-123">Example 3: Group event log events by EntryType</span></span>

<span data-ttu-id="dcb93-124">In diesem Beispiel werden die 1.000 letzten Einträge im System Ereignisprotokoll angezeigt, gruppiert nach **entryType**.</span><span class="sxs-lookup"><span data-stu-id="dcb93-124">This example displays the 1,000 most recent entries in the System event log, grouped by **EntryType**.</span></span>

<span data-ttu-id="dcb93-125">In der Ausgabe stellt die Spalte " **count** " die Anzahl der Einträge in jeder Gruppe dar.</span><span class="sxs-lookup"><span data-stu-id="dcb93-125">In the output, the **Count** column represents the number of entries in each group.</span></span> <span data-ttu-id="dcb93-126">Die **Name** -Spalte stellt die **eventType** -Werte dar, die eine Gruppe definieren.</span><span class="sxs-lookup"><span data-stu-id="dcb93-126">The **Name** column represents the **EventType** values that define a group.</span></span> <span data-ttu-id="dcb93-127">Die Spalte " **Group** " stellt die Objekte in jeder Gruppe dar.</span><span class="sxs-lookup"><span data-stu-id="dcb93-127">The **Group** column represents the objects in each group.</span></span>

```powershell
Get-WinEvent -LogName System -MaxEvents 1000 | Group-Object -Property LevelDisplayName
```

```Output
Count Name          Group
----- ----          -----
  153 Error         {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  722 Information   {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  125 Warning       {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
```

### <span data-ttu-id="dcb93-128">Beispiel 4: Gruppieren von Prozessen nach Prioritäts Klasse</span><span class="sxs-lookup"><span data-stu-id="dcb93-128">Example 4: Group processes by priority class</span></span>

<span data-ttu-id="dcb93-129">In diesem Beispiel werden die Auswirkungen des **noelement** -Parameters veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="dcb93-129">This example demonstrates the effect of the **NoElement** parameter.</span></span> <span data-ttu-id="dcb93-130">Diese Befehle gruppieren die Prozesse auf dem Computer nach Prioritätsklasse.</span><span class="sxs-lookup"><span data-stu-id="dcb93-130">These commands group the processes on the computer by priority class.</span></span>

<span data-ttu-id="dcb93-131">Der erste Befehl verwendet das `Get-Process` Cmdlet, um die Prozesse auf dem Computer zu erhalten, und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="dcb93-131">The first command uses the `Get-Process` cmdlet to get the processes on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="dcb93-132">`Group-Object`gruppiert die Objekte nach dem Wert der **PriorityClass** -Eigenschaft des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="dcb93-132">`Group-Object`groups the objects by the value of the **PriorityClass** property of the process.</span></span>

<span data-ttu-id="dcb93-133">Im zweiten Beispiel wird der **noelement** -Parameter verwendet, um die Member der Gruppe aus der Ausgabe auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="dcb93-133">The second example uses the **NoElement** parameter to eliminate the members of the group from the output.</span></span> <span data-ttu-id="dcb93-134">Das Ergebnis ist eine Tabelle, die nur den Wert für die **Anzahl** und den **Namen** der Eigenschaft hat.</span><span class="sxs-lookup"><span data-stu-id="dcb93-134">The result is a table with only the **Count** and **Name** property value.</span></span>

<span data-ttu-id="dcb93-135">Die Ergebnisse werden in der folgenden Beispielausgabe gezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcb93-135">The results are shown in the following sample output.</span></span>

```powershell
Get-Process | Group-Object -Property PriorityClass
```

```Output
Count Name         Group
----- ----         -----
   55 Normal       {System.Diagnostics.Process (AdtAgent), System.Diagnosti...
    1              {System.Diagnostics.Process (Idle)}
    3 High         {System.Diagnostics.Process (Newproc), System.Diagnostic...
    2 BelowNormal  {System.Diagnostics.Process (winperf),
```

```powershell
Get-Process | Group-Object -Property PriorityClass -NoElement
```

```Output
Count Name
----- ----
   55 Normal
    1
    3 High
    2 BelowNormal
```

### <span data-ttu-id="dcb93-136">Beispiel 5: Gruppieren von Prozessen nach Name</span><span class="sxs-lookup"><span data-stu-id="dcb93-136">Example 5: Group processes by name</span></span>

<span data-ttu-id="dcb93-137">Im folgenden Beispiel wird verwendet `Group-Object` , um mehrere Instanzen von Prozessen zu gruppieren, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="dcb93-137">The following example uses `Group-Object` to group multiple instances of processes running on the local computer.</span></span> <span data-ttu-id="dcb93-138">`Where-Object` zeigt Prozesse mit mehr als einer Instanz an.</span><span class="sxs-lookup"><span data-stu-id="dcb93-138">`Where-Object` displays processes with more than one instance.</span></span>

```powershell
Get-Process | Group-Object -Property Name -NoElement | Where-Object {$_.Count -gt 1}
```

```Output
Count Name
----- ----
2     csrss
5     svchost
2     winlogon
2     wmiprvse
```

### <span data-ttu-id="dcb93-139">Beispiel 6: Gruppieren von Objekten in einer Hash Tabelle</span><span class="sxs-lookup"><span data-stu-id="dcb93-139">Example 6: Group objects in a hash table</span></span>

<span data-ttu-id="dcb93-140">In diesem Beispiel werden die **ashashtable** -und **AsString** -Parameter verwendet, um die Gruppen in einer Hash Tabelle als eine Auflistung von Schlüssel-Wert-Paaren zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="dcb93-140">This example uses the **AsHashTable** and **AsString** parameters to return the groups in a hash table, as a collection of key-value pairs.</span></span>

<span data-ttu-id="dcb93-141">In der resultierenden Hashtabelle ist jeder Eigenschaftswert ein Schlüssel und die Gruppenelemente sind die Werte.</span><span class="sxs-lookup"><span data-stu-id="dcb93-141">In the resulting hash table, each property value is a key, and the group elements are the values.</span></span>
<span data-ttu-id="dcb93-142">Da jeder Schlüssel eine Eigenschaft des Hashtabellenobjekts ist, können Sie die Werte mithilfe der punktierten Schreibweise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="dcb93-142">Because each key is a property of the hash table object, you can use dot notation to display the values.</span></span>

<span data-ttu-id="dcb93-143">Der erste Befehl ruft die `Get` `Set` Cmdlets und in der Sitzung ab, gruppiert Sie nach Verb, gibt die Gruppen als Hash Tabelle zurück und speichert die Hash Tabelle in der `$A` Variablen.</span><span class="sxs-lookup"><span data-stu-id="dcb93-143">The first command gets the `Get` and `Set` cmdlets in the session, groups them by verb, returns the groups as a hash table, and saves the hash table in the `$A` variable.</span></span>

<span data-ttu-id="dcb93-144">Mit dem zweiten Befehl wird die Hash Tabelle in angezeigt `$A` .</span><span class="sxs-lookup"><span data-stu-id="dcb93-144">The second command displays the hash table in `$A`.</span></span> <span data-ttu-id="dcb93-145">Es gibt zwei Schlüssel-Wert-Paare, eine für die `Get` Cmdlets und eine für die `Set` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="dcb93-145">There are two key-value pairs, one for the `Get` cmdlets and one for the `Set` cmdlets.</span></span>

<span data-ttu-id="dcb93-146">Der dritte Befehl verwendet die Punkt Notation, `$A.Get` um die Werte der **Get** -Taste in anzuzeigen `$A` .</span><span class="sxs-lookup"><span data-stu-id="dcb93-146">The third command uses dot notation, `$A.Get` to display the values of the **Get** key in `$A`.</span></span> <span data-ttu-id="dcb93-147">Die Werte sind **cmdletinfo** -Objekte.</span><span class="sxs-lookup"><span data-stu-id="dcb93-147">The values are **CmdletInfo** object.</span></span> <span data-ttu-id="dcb93-148">Der **AsString** -Parameter konvertiert die Objekte in den Gruppen nicht in Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="dcb93-148">The **AsString** parameter doesn't convert the objects in the groups to strings.</span></span>

```powershell
$A = Get-Command Get-*, Set-* -CommandType cmdlet | Group-Object -Property Verb -AsHashTable -AsString
$A
```

```Output
Name     Value
----     -----
Get      {Get-Acl, Get-Alias, Get-AppLockerFileInformation, Get-AppLockerPolicy...}
Set      {Set-Acl, Set-Alias, Set-AppBackgroundTaskResourcePolicy, Set-AppLockerPolicy...}
```

```powershell
$A.Get
```

```Output
CommandType     Name                                Version    Source
-----------     ----                                -------    ------
Cmdlet          Get-Acl                             7.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Alias                           7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-AppLockerFileInformation        2.0.0.0    AppLocker
Cmdlet          Get-AppLockerPolicy                 2.0.0.0    AppLocker
...
```

### <span data-ttu-id="dcb93-149">Beispiel 7: Erstellen einer Hash Tabelle mit Berücksichtigung von Groß-und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="dcb93-149">Example 7: Create a case-sensitive hash table</span></span>

<span data-ttu-id="dcb93-150">Dieses Beispiel kombiniert die **CaseSensitive** -und **ashashtable** -Parameter, um eine Hash Tabelle mit Berücksichtigung von Groß-und Kleinschreibung zu erstellen</span><span class="sxs-lookup"><span data-stu-id="dcb93-150">This example combines the **CaseSensitive** and **AsHashTable** parameters to create a case-sensitive hash table.</span></span> <span data-ttu-id="dcb93-151">Die Dateien im Beispiel weisen die Erweiterungen `.txt` und auf `.TXT` .</span><span class="sxs-lookup"><span data-stu-id="dcb93-151">The files in the example have extensions of `.txt` and `.TXT`.</span></span>

```powershell
$hash = Get-ChildItem -Path C:\Files | Group-Object -Property Extension -CaseSensitive -AsHashTable
$hash
```

```Output
Name           Value
----           -----
.TXT           {C:\Files\File7.TXT, C:\Files\File8.TXT, C:\Files\File9.TXT}
.txt           {C:\Files\file1.txt, C:\Files\file2.txt, C:\Files\file3.txt}
```

<span data-ttu-id="dcb93-152">Die `$hash` Variable speichert das **System. Collections. Hashtable** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="dcb93-152">The `$hash` variable stores the **System.Collections.Hashtable** object.</span></span> <span data-ttu-id="dcb93-153">`Get-ChildItem` Ruft die Dateinamen aus dem `C:\Files` Verzeichnis ab und sendet die **System. IO. FileInfo** -Objekte über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="dcb93-153">`Get-ChildItem` gets the file names from the `C:\Files` directory and sends the **System.IO.FileInfo** objects down the pipeline.</span></span> <span data-ttu-id="dcb93-154">`Group-Object` gruppiert die Objekte mithilfe der **Eigenschafts** Wert **Erweiterung**.</span><span class="sxs-lookup"><span data-stu-id="dcb93-154">`Group-Object` groups the objects using the **Property** value **Extension**.</span></span> <span data-ttu-id="dcb93-155">Mit den Parametern **CaseSensitive** und **ashashtable** wird die Hash Tabelle erstellt, und die Schlüssel werden mit den Schlüsseln groß-und Kleinschreibung unterschieden `.txt` `.TXT` .</span><span class="sxs-lookup"><span data-stu-id="dcb93-155">The **CaseSensitive** and **AsHashTable** parameters create the hash table and the keys are grouped using the case-sensitive keys `.txt` and `.TXT`.</span></span>

## <span data-ttu-id="dcb93-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dcb93-156">PARAMETERS</span></span>

### <span data-ttu-id="dcb93-157">-Ashashtable</span><span class="sxs-lookup"><span data-stu-id="dcb93-157">-AsHashTable</span></span>

<span data-ttu-id="dcb93-158">Gibt an, dass dieses Cmdlet die Gruppe als Hash Tabelle zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="dcb93-158">Indicates that this cmdlet returns the group as a hash table.</span></span> <span data-ttu-id="dcb93-159">Die Schlüssel der Hashtabelle sind die Eigenschaftswerte, nach denen die Objekte gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="dcb93-159">The keys of the hash table are the property values by which the objects are grouped.</span></span> <span data-ttu-id="dcb93-160">Die Werte der Hashtabelle sind die Objekte, die diesen Eigenschaftswert aufweisen.</span><span class="sxs-lookup"><span data-stu-id="dcb93-160">The values of the hash table are the objects that have that property value.</span></span>

<span data-ttu-id="dcb93-161">Der **ashashtable** -Parameter gibt allein jede Hash Tabelle zurück, in der jeder Schlüssel eine Instanz des gruppierten Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="dcb93-161">By itself, the **AsHashTable** parameter returns each hash table in which each key is an instance of the grouped object.</span></span> <span data-ttu-id="dcb93-162">Bei Verwendung mit dem **AsString** -Parameter sind die Schlüssel in der Hash Tabelle Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="dcb93-162">When used with the **AsString** parameter, the keys in the hash table are strings.</span></span>

<span data-ttu-id="dcb93-163">Wenn Sie in PowerShell 7 die Unterscheidung nach Groß-/Kleinschreibung beachten möchten, schließen Sie **CaseSensitive** und **ashashtable** in Ihren Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="dcb93-163">Beginning in PowerShell 7, to create case-sensitive hash tables, include **CaseSensitive** and **AsHashtable** in your command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: AHT

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dcb93-164">-AsString</span><span class="sxs-lookup"><span data-stu-id="dcb93-164">-AsString</span></span>

<span data-ttu-id="dcb93-165">Gibt an, dass dieses Cmdlet die Hash Tabellenschlüssel in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="dcb93-165">Indicates that this cmdlet converts the hash table keys to strings.</span></span> <span data-ttu-id="dcb93-166">Standardmäßig sind die Schlüssel in der Hashtabelle Instanzen des gruppierten Objekts.</span><span class="sxs-lookup"><span data-stu-id="dcb93-166">By default, the hash table keys are instances of the grouped object.</span></span> <span data-ttu-id="dcb93-167">Dieser Parameter ist nur gültig, wenn er mit dem **ashashtable** -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dcb93-167">This parameter is valid only when used with the **AsHashTable** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dcb93-168">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="dcb93-168">-CaseSensitive</span></span>

<span data-ttu-id="dcb93-169">Gibt an, dass mit diesem Cmdlet die Groß-/Kleinschreibung berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="dcb93-169">Indicates that this cmdlet makes the grouping case-sensitive.</span></span> <span data-ttu-id="dcb93-170">Ohne diesen Parameter können die Eigenschaftswerte von Objekten in einer Gruppe groß- oder kleingeschrieben sein.</span><span class="sxs-lookup"><span data-stu-id="dcb93-170">Without this parameter, the property values of objects in a group might have different cases.</span></span>

<span data-ttu-id="dcb93-171">Wenn Sie in PowerShell 7 die Unterscheidung nach Groß-/Kleinschreibung beachten möchten, schließen Sie **CaseSensitive** und **ashashtable** in Ihren Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="dcb93-171">Beginning in PowerShell 7, to create case-sensitive hash tables, include **CaseSensitive** and **AsHashtable** in your command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dcb93-172">-Kultur</span><span class="sxs-lookup"><span data-stu-id="dcb93-172">-Culture</span></span>

<span data-ttu-id="dcb93-173">Gibt die Kultur an, die beim Vergleichen von Zeichenfolgen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="dcb93-173">Specifies the culture to use when comparing strings.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dcb93-174">-InputObject</span><span class="sxs-lookup"><span data-stu-id="dcb93-174">-InputObject</span></span>

<span data-ttu-id="dcb93-175">Gibt die zu gruppierenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="dcb93-175">Specifies the objects to group.</span></span> <span data-ttu-id="dcb93-176">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dcb93-176">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="dcb93-177">Wenn Sie den **Inputobject** -Parameter verwenden, um eine Auflistung von Objekten an zu senden `Group-Object` , `Group-Object` empfängt ein Objekt, das die Auflistung darstellt.</span><span class="sxs-lookup"><span data-stu-id="dcb93-177">When you use the **InputObject** parameter to submit a collection of objects to `Group-Object`, `Group-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="dcb93-178">Daher erstellt es eine einzelne Gruppe mit diesem Objekt als Member.</span><span class="sxs-lookup"><span data-stu-id="dcb93-178">As a result, it creates a single group with that object as its member.</span></span>

<span data-ttu-id="dcb93-179">Um die Objekte in einer Auflistung zu gruppieren, übergeben Sie die Objekte über die Pipeline an `Group-Object` .</span><span class="sxs-lookup"><span data-stu-id="dcb93-179">To group the objects in a collection, pipe the objects to `Group-Object`.</span></span>

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

### <span data-ttu-id="dcb93-180">-Noelement</span><span class="sxs-lookup"><span data-stu-id="dcb93-180">-NoElement</span></span>

<span data-ttu-id="dcb93-181">Gibt an, dass dieses Cmdlet die Mitglieder einer Gruppe aus den Ergebnissen auslässt.</span><span class="sxs-lookup"><span data-stu-id="dcb93-181">Indicates that this cmdlet omits the members of a group from the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dcb93-182">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dcb93-182">-Property</span></span>

<span data-ttu-id="dcb93-183">Gibt die Eigenschaften für die Gruppierung an.</span><span class="sxs-lookup"><span data-stu-id="dcb93-183">Specifies the properties for grouping.</span></span> <span data-ttu-id="dcb93-184">Die Objekte werden basierend auf dem Wert der angegebenen Eigenschaft in Gruppen angeordnet.</span><span class="sxs-lookup"><span data-stu-id="dcb93-184">The objects are arranged into groups based on the value of the specified property.</span></span>

<span data-ttu-id="dcb93-185">Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="dcb93-185">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="dcb93-186">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="dcb93-186">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="dcb93-187">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="dcb93-187">Valid key-value pairs are:</span></span>

- <span data-ttu-id="dcb93-188">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="dcb93-188">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="dcb93-189">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="dcb93-189">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dcb93-190">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dcb93-190">CommonParameters</span></span>

<span data-ttu-id="dcb93-191">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dcb93-191">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dcb93-192">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dcb93-192">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dcb93-193">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="dcb93-193">INPUTS</span></span>

### <span data-ttu-id="dcb93-194">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="dcb93-194">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="dcb93-195">Sie können jedes beliebige Objekt an die Pipeline übergeben `Group-Object` .</span><span class="sxs-lookup"><span data-stu-id="dcb93-195">You can pipe any object to `Group-Object`.</span></span>

## <span data-ttu-id="dcb93-196">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="dcb93-196">OUTPUTS</span></span>

### <span data-ttu-id="dcb93-197">Microsoft. PowerShell. Commands. groupInfo oder System. Collections. Hashtable</span><span class="sxs-lookup"><span data-stu-id="dcb93-197">Microsoft.PowerShell.Commands.GroupInfo or System.Collections.Hashtable</span></span>

<span data-ttu-id="dcb93-198">Wenn Sie den **ashashtable** -Parameter verwenden, `Group-Object` gibt ein **Hashtable** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="dcb93-198">When you use the **AsHashTable** parameter, `Group-Object` returns a **Hashtable** object.</span></span>
<span data-ttu-id="dcb93-199">Andernfalls wird ein **groupInfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dcb93-199">Otherwise, it returns a **GroupInfo** object.</span></span>

## <span data-ttu-id="dcb93-200">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="dcb93-200">NOTES</span></span>

<span data-ttu-id="dcb93-201">Sie können den **GroupBy** -Parameter der Formatierungs-Cmdlets, z `Format-Table` . b. und `Format-List` , verwenden, um-Objekte zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="dcb93-201">You can use the **GroupBy** parameter of the formatting cmdlets, such as `Format-Table` and `Format-List`, to group objects.</span></span> <span data-ttu-id="dcb93-202">Anders als bei `Group-Object` , das eine einzelne Tabelle mit einer Zeile für jeden Eigenschafts Wert erstellt, erstellen die **GroupBy** -Parameter eine Tabelle für jeden Eigenschafts Wert mit einer Zeile für jedes Element, das über den Eigenschafts Wert verfügt.</span><span class="sxs-lookup"><span data-stu-id="dcb93-202">Unlike `Group-Object`, which creates a single table with a row for each property value, the **GroupBy** parameters create a table for each property value with a row for each item that has the property value.</span></span>

<span data-ttu-id="dcb93-203">`Group-Object` erfordert nicht, dass die gruppierten Objekte denselben Microsoft .net Kerntyp haben.</span><span class="sxs-lookup"><span data-stu-id="dcb93-203">`Group-Object` doesn't require that the objects being grouped are of the same Microsoft .NET Core type.</span></span> <span data-ttu-id="dcb93-204">Beim Gruppieren von Objekten unterschiedlicher .net Core-Typen `Group-Object` verwendet die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="dcb93-204">When grouping objects of different .NET Core types, `Group-Object` uses the following rules:</span></span>

- <span data-ttu-id="dcb93-205">Die gleichen Eigenschaftsnamen und-Typen.</span><span class="sxs-lookup"><span data-stu-id="dcb93-205">Same Property Names and Types.</span></span>

  <span data-ttu-id="dcb93-206">Wenn die Objekte über eine Eigenschaft mit dem angegebenen Namen verfügen und die Eigenschaftswerte denselben .net Core-Typ aufweisen, werden die Eigenschaftswerte mithilfe derselben Regeln gruppiert, die für Objekte desselben Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dcb93-206">If the objects have a property with the specified name, and the property values have the same .NET Core type, the property values are grouped by using the same rules that would be used for objects of the same type.</span></span>

- <span data-ttu-id="dcb93-207">Dieselben Eigenschaftsnamen, verschiedene Typen.</span><span class="sxs-lookup"><span data-stu-id="dcb93-207">Same Property Names, Different Types.</span></span>

  <span data-ttu-id="dcb93-208">Wenn die Objekte über eine Eigenschaft mit dem angegebenen Namen verfügen, aber die Eigenschaftswerte einen anderen .net Core-Typ in unterschiedlichen Objekten aufweisen, `Group-Object` verwendet den .net Core-Typ des ersten Vorkommens der Eigenschaft als .net Core-Typ für die Eigenschaften Gruppe.</span><span class="sxs-lookup"><span data-stu-id="dcb93-208">If the objects have a property with the specified name, but the property values have a different .NET Core type in different objects, `Group-Object` uses the .NET Core type of the first occurrence of the property as the .NET Core type for that property group.</span></span> <span data-ttu-id="dcb93-209">Wenn ein Objekt eine Eigenschaft mit einem anderen Typ aufweist, wird der Eigenschaftswert in den Typ für diese Gruppe konvertiert.</span><span class="sxs-lookup"><span data-stu-id="dcb93-209">When an object has a property with a different type, the property value is converted to the type for that group.</span></span> <span data-ttu-id="dcb93-210">Wenn die Typkonvertierung fehlschlägt, ist das Objekt nicht in der Gruppe enthalten.</span><span class="sxs-lookup"><span data-stu-id="dcb93-210">If the type conversion fails, the object isn't included in the group.</span></span>

- <span data-ttu-id="dcb93-211">Fehlende Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="dcb93-211">Missing Properties.</span></span>

  <span data-ttu-id="dcb93-212">Objekte, die über keine angegebene Eigenschaft verfügen, können nicht gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="dcb93-212">Objects that don't have a specified property can't be grouped.</span></span> <span data-ttu-id="dcb93-213">Nicht gruppierte Objekte werden in der endgültigen **groupInfo** -Objekt Ausgabe in einer Gruppe mit dem Namen angezeigt `AutomationNull.Value` .</span><span class="sxs-lookup"><span data-stu-id="dcb93-213">Objects that aren't grouped appear in the final **GroupInfo** object output in a group named `AutomationNull.Value`.</span></span>

## <span data-ttu-id="dcb93-214">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="dcb93-214">RELATED LINKS</span></span>

[<span data-ttu-id="dcb93-215">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="dcb93-215">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="dcb93-216">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="dcb93-216">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="dcb93-217">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="dcb93-217">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="dcb93-218">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="dcb93-218">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="dcb93-219">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="dcb93-219">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="dcb93-220">New-Object</span><span class="sxs-lookup"><span data-stu-id="dcb93-220">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="dcb93-221">Select-Object</span><span class="sxs-lookup"><span data-stu-id="dcb93-221">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="dcb93-222">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="dcb93-222">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="dcb93-223">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="dcb93-223">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="dcb93-224">Where-Object</span><span class="sxs-lookup"><span data-stu-id="dcb93-224">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
