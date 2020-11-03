---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/group-object?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Group-Object
ms.openlocfilehash: f430dd1f9d9f820dda88ba5ad40023650204604d
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219396"
---
# <span data-ttu-id="3b77e-103">Group-Object</span><span class="sxs-lookup"><span data-stu-id="3b77e-103">Group-Object</span></span>

## <span data-ttu-id="3b77e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3b77e-104">SYNOPSIS</span></span>
<span data-ttu-id="3b77e-105">Gruppiert Objekte, die den gleichen Wert für die angegebenen Eigenschaften enthalten.</span><span class="sxs-lookup"><span data-stu-id="3b77e-105">Groups objects that contain the same value for specified properties.</span></span>

## <span data-ttu-id="3b77e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3b77e-106">SYNTAX</span></span>

### <span data-ttu-id="3b77e-107">Hash Tabelle</span><span class="sxs-lookup"><span data-stu-id="3b77e-107">HashTable</span></span>

```
Group-Object [-NoElement] [-AsHashTable] [-AsString] [-InputObject <PSObject>]
 [[-Property] <Object[]>] [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="3b77e-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3b77e-108">DESCRIPTION</span></span>

<span data-ttu-id="3b77e-109">Das- `Group-Object` Cmdlet zeigt Objekte in Gruppen basierend auf dem Wert einer angegebenen Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="3b77e-109">The `Group-Object` cmdlet displays objects in groups based on the value of a specified property.</span></span>
<span data-ttu-id="3b77e-110">`Group-Object` gibt eine Tabelle mit einer Zeile für jeden Eigenschafts Wert und eine Spalte zurück, die die Anzahl der Elemente mit diesem Wert anzeigt.</span><span class="sxs-lookup"><span data-stu-id="3b77e-110">`Group-Object` returns a table with one row for each property value and a column that displays the number of items with that value.</span></span>

<span data-ttu-id="3b77e-111">Wenn Sie mehr als eine Eigenschaft angeben, werden `Group-Object` diese zuerst nach den Werten der ersten Eigenschaft und dann innerhalb jeder Eigenschaften Gruppe nach dem Wert der nächsten Eigenschaft gruppiert.</span><span class="sxs-lookup"><span data-stu-id="3b77e-111">If you specify more than one property, `Group-Object` first groups them by the values of the first property, and then, within each property group, it groups by the value of the next property.</span></span>

## <span data-ttu-id="3b77e-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3b77e-112">EXAMPLES</span></span>

### <span data-ttu-id="3b77e-113">Beispiel 1: Gruppieren von Dateien nach Erweiterung</span><span class="sxs-lookup"><span data-stu-id="3b77e-113">Example 1: Group files by extension</span></span>

<span data-ttu-id="3b77e-114">In diesem Beispiel werden die Dateien unter rekursiv abgerufen `$PSHOME` und nach der Dateinamenerweiterung gruppiert.</span><span class="sxs-lookup"><span data-stu-id="3b77e-114">This example recursively gets the files under `$PSHOME` and groups them by file name extension.</span></span> <span data-ttu-id="3b77e-115">Die Ausgabe wird an das `Sort-Object` Cmdlet gesendet, das Sie nach den für die angegebene Erweiterung gefundenen Anzahl Dateien sortiert.</span><span class="sxs-lookup"><span data-stu-id="3b77e-115">The output is sent to the `Sort-Object` cmdlet, which sorts them by the count files found for the given extension.</span></span> <span data-ttu-id="3b77e-116">Der leere **Name** stellt Verzeichnisse dar.</span><span class="sxs-lookup"><span data-stu-id="3b77e-116">The empty **Name** represents directories.</span></span>

<span data-ttu-id="3b77e-117">In diesem Beispiel wird der **noelement** -Parameter verwendet, um die Member der Gruppe auszulassen.</span><span class="sxs-lookup"><span data-stu-id="3b77e-117">This example uses the **NoElement** parameter to omit the members of the group.</span></span>

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

### <span data-ttu-id="3b77e-118">Beispiel 2: Gruppieren von ganzen Zahlen nach Wahrscheinlichkeit und Evens</span><span class="sxs-lookup"><span data-stu-id="3b77e-118">Example 2: Group integers by odds and evens</span></span>

<span data-ttu-id="3b77e-119">In diesem Beispiel wird gezeigt, wie Skriptblöcke als Wert des **Property** -Parameters verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3b77e-119">This example shows how to use script blocks as the value of the **Property** parameter.</span></span> <span data-ttu-id="3b77e-120">Dieser Befehl zeigt die ganzen Zahlen von 1 bis 20 an, gruppiert nach Wahrscheinlichkeit und sogar.</span><span class="sxs-lookup"><span data-stu-id="3b77e-120">This command displays the integers from 1 to 20, grouped by odds and even.</span></span>

```powershell
1..20 | Group-Object -Property {$_ % 2}
```

```Output
Count Name                      Group
----- ----                      -----
   10 0                         {2, 4, 6, 8...}
   10 1                         {1, 3, 5, 7...}
```

### <span data-ttu-id="3b77e-121">Beispiel 3: Gruppieren von Ereignisprotokoll Ereignissen nach EntryType</span><span class="sxs-lookup"><span data-stu-id="3b77e-121">Example 3: Group event log events by EntryType</span></span>

<span data-ttu-id="3b77e-122">In diesem Beispiel werden die 1.000 letzten Einträge im System Ereignisprotokoll angezeigt, gruppiert nach **entryType**.</span><span class="sxs-lookup"><span data-stu-id="3b77e-122">This example displays the 1,000 most recent entries in the System event log, grouped by **EntryType**.</span></span>

<span data-ttu-id="3b77e-123">In der Ausgabe stellt die Spalte " **count** " die Anzahl der Einträge in jeder Gruppe dar.</span><span class="sxs-lookup"><span data-stu-id="3b77e-123">In the output, the **Count** column represents the number of entries in each group.</span></span> <span data-ttu-id="3b77e-124">Die **Name** -Spalte stellt die **eventType** -Werte dar, die eine Gruppe definieren.</span><span class="sxs-lookup"><span data-stu-id="3b77e-124">The **Name** column represents the **EventType** values that define a group.</span></span> <span data-ttu-id="3b77e-125">Die Spalte " **Group** " stellt die Objekte in jeder Gruppe dar.</span><span class="sxs-lookup"><span data-stu-id="3b77e-125">The **Group** column represents the objects in each group.</span></span>

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

### <span data-ttu-id="3b77e-126">Beispiel 4: Gruppieren von Prozessen nach Prioritäts Klasse</span><span class="sxs-lookup"><span data-stu-id="3b77e-126">Example 4: Group processes by priority class</span></span>

<span data-ttu-id="3b77e-127">In diesem Beispiel werden die Auswirkungen des **noelement** -Parameters veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3b77e-127">This example demonstrates the effect of the **NoElement** parameter.</span></span> <span data-ttu-id="3b77e-128">Diese Befehle gruppieren die Prozesse auf dem Computer nach Prioritätsklasse.</span><span class="sxs-lookup"><span data-stu-id="3b77e-128">These commands group the processes on the computer by priority class.</span></span>

<span data-ttu-id="3b77e-129">Der erste Befehl verwendet das `Get-Process` Cmdlet, um die Prozesse auf dem Computer zu erhalten, und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="3b77e-129">The first command uses the `Get-Process` cmdlet to get the processes on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="3b77e-130">`Group-Object`gruppiert die Objekte nach dem Wert der **PriorityClass** -Eigenschaft des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="3b77e-130">`Group-Object`groups the objects by the value of the **PriorityClass** property of the process.</span></span>

<span data-ttu-id="3b77e-131">Im zweiten Beispiel wird der **noelement** -Parameter verwendet, um die Member der Gruppe aus der Ausgabe auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="3b77e-131">The second example uses the **NoElement** parameter to eliminate the members of the group from the output.</span></span> <span data-ttu-id="3b77e-132">Das Ergebnis ist eine Tabelle, die nur den Wert für die **Anzahl** und den **Namen** der Eigenschaft hat.</span><span class="sxs-lookup"><span data-stu-id="3b77e-132">The result is a table with only the **Count** and **Name** property value.</span></span>

<span data-ttu-id="3b77e-133">Die Ergebnisse werden in der folgenden Beispielausgabe gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3b77e-133">The results are shown in the following sample output.</span></span>

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

### <span data-ttu-id="3b77e-134">Beispiel 5: Gruppieren von Prozessen nach Name</span><span class="sxs-lookup"><span data-stu-id="3b77e-134">Example 5: Group processes by name</span></span>

<span data-ttu-id="3b77e-135">Im folgenden Beispiel wird verwendet `Group-Object` , um mehrere Instanzen von Prozessen zu gruppieren, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3b77e-135">The following example uses `Group-Object` to group multiple instances of processes running on the local computer.</span></span> <span data-ttu-id="3b77e-136">`Where-Object` zeigt Prozesse mit mehr als einer Instanz an.</span><span class="sxs-lookup"><span data-stu-id="3b77e-136">`Where-Object` displays processes with more than one instance.</span></span>

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

### <span data-ttu-id="3b77e-137">Beispiel 6: Gruppieren von Objekten in einer Hash Tabelle</span><span class="sxs-lookup"><span data-stu-id="3b77e-137">Example 6: Group objects in a hash table</span></span>

<span data-ttu-id="3b77e-138">In diesem Beispiel werden die **ashashtable** -und **AsString** -Parameter verwendet, um die Gruppen in einer Hash Tabelle als eine Auflistung von Schlüssel-Wert-Paaren zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="3b77e-138">This example uses the **AsHashTable** and **AsString** parameters to return the groups in a hash table, as a collection of key-value pairs.</span></span>

<span data-ttu-id="3b77e-139">In der resultierenden Hashtabelle ist jeder Eigenschaftswert ein Schlüssel und die Gruppenelemente sind die Werte.</span><span class="sxs-lookup"><span data-stu-id="3b77e-139">In the resulting hash table, each property value is a key, and the group elements are the values.</span></span>
<span data-ttu-id="3b77e-140">Da jeder Schlüssel eine Eigenschaft des Hashtabellenobjekts ist, können Sie die Werte mithilfe der punktierten Schreibweise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3b77e-140">Because each key is a property of the hash table object, you can use dot notation to display the values.</span></span>

<span data-ttu-id="3b77e-141">Der erste Befehl ruft die `Get` `Set` Cmdlets und in der Sitzung ab, gruppiert Sie nach Verb, gibt die Gruppen als Hash Tabelle zurück und speichert die Hash Tabelle in der `$A` Variablen.</span><span class="sxs-lookup"><span data-stu-id="3b77e-141">The first command gets the `Get` and `Set` cmdlets in the session, groups them by verb, returns the groups as a hash table, and saves the hash table in the `$A` variable.</span></span>

<span data-ttu-id="3b77e-142">Mit dem zweiten Befehl wird die Hash Tabelle in angezeigt `$A` .</span><span class="sxs-lookup"><span data-stu-id="3b77e-142">The second command displays the hash table in `$A`.</span></span> <span data-ttu-id="3b77e-143">Es gibt zwei Schlüssel-Wert-Paare, eine für die `Get` Cmdlets und eine für die `Set` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3b77e-143">There are two key-value pairs, one for the `Get` cmdlets and one for the `Set` cmdlets.</span></span>

<span data-ttu-id="3b77e-144">Der dritte Befehl verwendet die Punkt Notation, `$A.Get` um die Werte der **Get** -Taste in anzuzeigen `$A` .</span><span class="sxs-lookup"><span data-stu-id="3b77e-144">The third command uses dot notation, `$A.Get` to display the values of the **Get** key in `$A`.</span></span> <span data-ttu-id="3b77e-145">Die Werte sind **cmdletinfo** -Objekte.</span><span class="sxs-lookup"><span data-stu-id="3b77e-145">The values are **CmdletInfo** object.</span></span> <span data-ttu-id="3b77e-146">Der **AsString** -Parameter konvertiert die Objekte in den Gruppen nicht in Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="3b77e-146">The **AsString** parameter doesn't convert the objects in the groups to strings.</span></span>

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
CommandType     Name                               Version    Source
-----------     ----                               -------    ------
Cmdlet          Get-Acl                            6.1.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Alias                          6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-AuthenticodeSignature          6.1.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-ChildItem                      6.1.0.0    Microsoft.PowerShell.Management
...
```

## <span data-ttu-id="3b77e-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3b77e-147">PARAMETERS</span></span>

### <span data-ttu-id="3b77e-148">-Ashashtable</span><span class="sxs-lookup"><span data-stu-id="3b77e-148">-AsHashTable</span></span>

<span data-ttu-id="3b77e-149">Gibt an, dass dieses Cmdlet die Gruppe als Hash Tabelle zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3b77e-149">Indicates that this cmdlet returns the group as a hash table.</span></span> <span data-ttu-id="3b77e-150">Die Schlüssel der Hashtabelle sind die Eigenschaftswerte, nach denen die Objekte gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="3b77e-150">The keys of the hash table are the property values by which the objects are grouped.</span></span> <span data-ttu-id="3b77e-151">Die Werte der Hashtabelle sind die Objekte, die diesen Eigenschaftswert aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3b77e-151">The values of the hash table are the objects that have that property value.</span></span>

<span data-ttu-id="3b77e-152">Der **ashashtable** -Parameter gibt allein jede Hash Tabelle zurück, in der jeder Schlüssel eine Instanz des gruppierten Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="3b77e-152">By itself, the **AsHashTable** parameter returns each hash table in which each key is an instance of the grouped object.</span></span> <span data-ttu-id="3b77e-153">Bei Verwendung mit dem **AsString** -Parameter sind die Schlüssel in der Hash Tabelle Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="3b77e-153">When used with the **AsString** parameter, the keys in the hash table are strings.</span></span>

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

### <span data-ttu-id="3b77e-154">-AsString</span><span class="sxs-lookup"><span data-stu-id="3b77e-154">-AsString</span></span>

<span data-ttu-id="3b77e-155">Gibt an, dass dieses Cmdlet die Hash Tabellenschlüssel in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3b77e-155">Indicates that this cmdlet converts the hash table keys to strings.</span></span> <span data-ttu-id="3b77e-156">Standardmäßig sind die Schlüssel in der Hashtabelle Instanzen des gruppierten Objekts.</span><span class="sxs-lookup"><span data-stu-id="3b77e-156">By default, the hash table keys are instances of the grouped object.</span></span> <span data-ttu-id="3b77e-157">Dieser Parameter ist nur gültig, wenn er mit dem **ashashtable** -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3b77e-157">This parameter is valid only when used with the **AsHashTable** parameter.</span></span>

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

### <span data-ttu-id="3b77e-158">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="3b77e-158">-CaseSensitive</span></span>

<span data-ttu-id="3b77e-159">Gibt an, dass mit diesem Cmdlet die Groß-/Kleinschreibung berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="3b77e-159">Indicates that this cmdlet makes the grouping case-sensitive.</span></span> <span data-ttu-id="3b77e-160">Ohne diesen Parameter können die Eigenschaftswerte von Objekten in einer Gruppe groß- oder kleingeschrieben sein.</span><span class="sxs-lookup"><span data-stu-id="3b77e-160">Without this parameter, the property values of objects in a group might have different cases.</span></span>

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

### <span data-ttu-id="3b77e-161">-Kultur</span><span class="sxs-lookup"><span data-stu-id="3b77e-161">-Culture</span></span>

<span data-ttu-id="3b77e-162">Gibt die Kultur an, die beim Vergleichen von Zeichenfolgen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3b77e-162">Specifies the culture to use when comparing strings.</span></span>

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

### <span data-ttu-id="3b77e-163">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3b77e-163">-InputObject</span></span>

<span data-ttu-id="3b77e-164">Gibt die zu gruppierenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="3b77e-164">Specifies the objects to group.</span></span> <span data-ttu-id="3b77e-165">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3b77e-165">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="3b77e-166">Wenn Sie den **Inputobject** -Parameter verwenden, um eine Auflistung von Objekten an zu senden `Group-Object` , `Group-Object` empfängt ein Objekt, das die Auflistung darstellt.</span><span class="sxs-lookup"><span data-stu-id="3b77e-166">When you use the **InputObject** parameter to submit a collection of objects to `Group-Object`, `Group-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="3b77e-167">Daher erstellt es eine einzelne Gruppe mit diesem Objekt als Member.</span><span class="sxs-lookup"><span data-stu-id="3b77e-167">As a result, it creates a single group with that object as its member.</span></span>

<span data-ttu-id="3b77e-168">Um die Objekte in einer Auflistung zu gruppieren, übergeben Sie die Objekte über die Pipeline an `Group-Object` .</span><span class="sxs-lookup"><span data-stu-id="3b77e-168">To group the objects in a collection, pipe the objects to `Group-Object`.</span></span>

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

### <span data-ttu-id="3b77e-169">-Noelement</span><span class="sxs-lookup"><span data-stu-id="3b77e-169">-NoElement</span></span>

<span data-ttu-id="3b77e-170">Gibt an, dass dieses Cmdlet die Mitglieder einer Gruppe aus den Ergebnissen auslässt.</span><span class="sxs-lookup"><span data-stu-id="3b77e-170">Indicates that this cmdlet omits the members of a group from the results.</span></span>

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

### <span data-ttu-id="3b77e-171">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3b77e-171">-Property</span></span>

<span data-ttu-id="3b77e-172">Gibt die Eigenschaften für die Gruppierung an.</span><span class="sxs-lookup"><span data-stu-id="3b77e-172">Specifies the properties for grouping.</span></span> <span data-ttu-id="3b77e-173">Die Objekte werden basierend auf dem Wert der angegebenen Eigenschaft in Gruppen angeordnet.</span><span class="sxs-lookup"><span data-stu-id="3b77e-173">The objects are arranged into groups based on the value of the specified property.</span></span>

<span data-ttu-id="3b77e-174">Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="3b77e-174">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="3b77e-175">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="3b77e-175">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="3b77e-176">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="3b77e-176">Valid key-value pairs are:</span></span>

- <span data-ttu-id="3b77e-177">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="3b77e-177">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="3b77e-178">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="3b77e-178">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="3b77e-179">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3b77e-179">CommonParameters</span></span>

<span data-ttu-id="3b77e-180">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3b77e-180">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3b77e-181">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3b77e-181">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3b77e-182">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3b77e-182">INPUTS</span></span>

### <span data-ttu-id="3b77e-183">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="3b77e-183">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="3b77e-184">Sie können jedes beliebige Objekt an die Pipeline übergeben `Group-Object` .</span><span class="sxs-lookup"><span data-stu-id="3b77e-184">You can pipe any object to `Group-Object`.</span></span>

## <span data-ttu-id="3b77e-185">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3b77e-185">OUTPUTS</span></span>

### <span data-ttu-id="3b77e-186">Microsoft. PowerShell. Commands. groupInfo oder System. Collections. Hashtable</span><span class="sxs-lookup"><span data-stu-id="3b77e-186">Microsoft.PowerShell.Commands.GroupInfo or System.Collections.Hashtable</span></span>

<span data-ttu-id="3b77e-187">Wenn Sie den **ashashtable** -Parameter verwenden, `Group-Object` gibt ein **Hashtable** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="3b77e-187">When you use the **AsHashTable** parameter, `Group-Object` returns a **Hashtable** object.</span></span>
<span data-ttu-id="3b77e-188">Andernfalls wird ein **groupInfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3b77e-188">Otherwise, it returns a **GroupInfo** object.</span></span>

## <span data-ttu-id="3b77e-189">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3b77e-189">NOTES</span></span>

<span data-ttu-id="3b77e-190">Sie können den **GroupBy** -Parameter der Formatierungs-Cmdlets, z `Format-Table` . b. und `Format-List` , verwenden, um-Objekte zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="3b77e-190">You can use the **GroupBy** parameter of the formatting cmdlets, such as `Format-Table` and `Format-List`, to group objects.</span></span> <span data-ttu-id="3b77e-191">Anders als bei `Group-Object` , das eine einzelne Tabelle mit einer Zeile für jeden Eigenschafts Wert erstellt, erstellen die **GroupBy** -Parameter eine Tabelle für jeden Eigenschafts Wert mit einer Zeile für jedes Element, das über den Eigenschafts Wert verfügt.</span><span class="sxs-lookup"><span data-stu-id="3b77e-191">Unlike `Group-Object`, which creates a single table with a row for each property value, the **GroupBy** parameters create a table for each property value with a row for each item that has the property value.</span></span>

<span data-ttu-id="3b77e-192">`Group-Object` erfordert nicht, dass die gruppierten Objekte denselben Microsoft .net Kerntyp haben.</span><span class="sxs-lookup"><span data-stu-id="3b77e-192">`Group-Object` doesn't require that the objects being grouped are of the same Microsoft .NET Core type.</span></span> <span data-ttu-id="3b77e-193">Beim Gruppieren von Objekten unterschiedlicher .net Core-Typen `Group-Object` verwendet die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="3b77e-193">When grouping objects of different .NET Core types, `Group-Object` uses the following rules:</span></span>

- <span data-ttu-id="3b77e-194">Die gleichen Eigenschaftsnamen und-Typen.</span><span class="sxs-lookup"><span data-stu-id="3b77e-194">Same Property Names and Types.</span></span>

  <span data-ttu-id="3b77e-195">Wenn die Objekte über eine Eigenschaft mit dem angegebenen Namen verfügen und die Eigenschaftswerte denselben .net Core-Typ aufweisen, werden die Eigenschaftswerte mithilfe derselben Regeln gruppiert, die für Objekte desselben Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3b77e-195">If the objects have a property with the specified name, and the property values have the same .NET Core type, the property values are grouped by using the same rules that would be used for objects of the same type.</span></span>

- <span data-ttu-id="3b77e-196">Dieselben Eigenschaftsnamen, verschiedene Typen.</span><span class="sxs-lookup"><span data-stu-id="3b77e-196">Same Property Names, Different Types.</span></span>

  <span data-ttu-id="3b77e-197">Wenn die Objekte über eine Eigenschaft mit dem angegebenen Namen verfügen, aber die Eigenschaftswerte einen anderen .net Core-Typ in unterschiedlichen Objekten aufweisen, `Group-Object` verwendet den .net Core-Typ des ersten Vorkommens der Eigenschaft als .net Core-Typ für die Eigenschaften Gruppe.</span><span class="sxs-lookup"><span data-stu-id="3b77e-197">If the objects have a property with the specified name, but the property values have a different .NET Core type in different objects, `Group-Object` uses the .NET Core type of the first occurrence of the property as the .NET Core type for that property group.</span></span> <span data-ttu-id="3b77e-198">Wenn ein Objekt eine Eigenschaft mit einem anderen Typ aufweist, wird der Eigenschaftswert in den Typ für diese Gruppe konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3b77e-198">When an object has a property with a different type, the property value is converted to the type for that group.</span></span> <span data-ttu-id="3b77e-199">Wenn die Typkonvertierung fehlschlägt, ist das Objekt nicht in der Gruppe enthalten.</span><span class="sxs-lookup"><span data-stu-id="3b77e-199">If the type conversion fails, the object isn't included in the group.</span></span>

- <span data-ttu-id="3b77e-200">Fehlende Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="3b77e-200">Missing Properties.</span></span>

  <span data-ttu-id="3b77e-201">Objekte, die über keine angegebene Eigenschaft verfügen, können nicht gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="3b77e-201">Objects that don't have a specified property can't be grouped.</span></span> <span data-ttu-id="3b77e-202">Nicht gruppierte Objekte werden in der endgültigen **groupInfo** -Objekt Ausgabe in einer Gruppe mit dem Namen angezeigt `AutomationNull.Value` .</span><span class="sxs-lookup"><span data-stu-id="3b77e-202">Objects that aren't grouped appear in the final **GroupInfo** object output in a group named `AutomationNull.Value`.</span></span>

## <span data-ttu-id="3b77e-203">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3b77e-203">RELATED LINKS</span></span>

[<span data-ttu-id="3b77e-204">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="3b77e-204">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="3b77e-205">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="3b77e-205">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="3b77e-206">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="3b77e-206">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="3b77e-207">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="3b77e-207">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="3b77e-208">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="3b77e-208">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="3b77e-209">New-Object</span><span class="sxs-lookup"><span data-stu-id="3b77e-209">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="3b77e-210">Select-Object</span><span class="sxs-lookup"><span data-stu-id="3b77e-210">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="3b77e-211">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="3b77e-211">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="3b77e-212">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="3b77e-212">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="3b77e-213">Where-Object</span><span class="sxs-lookup"><span data-stu-id="3b77e-213">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
