---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Object
ms.openlocfilehash: 5d4a27f1a1949056ca63b9b6a2340bf1226592e0
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219215"
---
# <span data-ttu-id="1aa30-103">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="1aa30-103">Measure-Object</span></span>

## <span data-ttu-id="1aa30-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1aa30-104">SYNOPSIS</span></span>
<span data-ttu-id="1aa30-105">Berechnet die numerischen Eigenschaften von Objekten und die Zeichen, Wörter und Zeilen in Zeichenfolgenobjekten, z. B. Textdateien.</span><span class="sxs-lookup"><span data-stu-id="1aa30-105">Calculates the numeric properties of objects, and the characters, words, and lines in string objects, such as files of text.</span></span>

## <span data-ttu-id="1aa30-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1aa30-106">SYNTAX</span></span>

### <span data-ttu-id="1aa30-107">Genericmeasure (Standard)</span><span class="sxs-lookup"><span data-stu-id="1aa30-107">GenericMeasure (Default)</span></span>

```
Measure-Object [-InputObject <PSObject>] [[-Property] <String[]>] [-Sum] [-Average] [-Maximum] [-Minimum]
 [<CommonParameters>]
```

### <span data-ttu-id="1aa30-108">Textmeasure</span><span class="sxs-lookup"><span data-stu-id="1aa30-108">TextMeasure</span></span>

```
Measure-Object [-InputObject <PSObject>] [[-Property] <String[]>] [-Line] [-Word] [-Character]
 [-IgnoreWhiteSpace] [<CommonParameters>]
```

## <span data-ttu-id="1aa30-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1aa30-109">DESCRIPTION</span></span>

<span data-ttu-id="1aa30-110">Das- `Measure-Object` Cmdlet berechnet die Eigenschaftswerte bestimmter Objekttypen.</span><span class="sxs-lookup"><span data-stu-id="1aa30-110">The `Measure-Object` cmdlet calculates the property values of certain types of object.</span></span>
<span data-ttu-id="1aa30-111">`Measure-Object` führt abhängig von den Parametern im Befehl drei Arten von Messungen aus.</span><span class="sxs-lookup"><span data-stu-id="1aa30-111">`Measure-Object` performs three types of measurements, depending on the parameters in the command.</span></span>

<span data-ttu-id="1aa30-112">Das- `Measure-Object` Cmdlet führt Berechnungen für die Eigenschaftswerte von Objekten aus.</span><span class="sxs-lookup"><span data-stu-id="1aa30-112">The `Measure-Object` cmdlet performs calculations on the property values of objects.</span></span> <span data-ttu-id="1aa30-113">Sie können `Measure-Object` zum zählen von Objekten oder zum zählen von Objekten mit einer angegebenen **Eigenschaft** verwenden.</span><span class="sxs-lookup"><span data-stu-id="1aa30-113">You can use `Measure-Object` to count objects or count objects with a specified **Property**.</span></span> <span data-ttu-id="1aa30-114">Sie können auch verwenden `Measure-Object` , um die **Mindest** - **, höchst** -, **Summen** -, **Standardabweichung** und den **Durchschnitt** numerischer Werte zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="1aa30-114">You can also use `Measure-Object` to calculate the **Minimum** , **Maximum** , **Sum** , **StandardDeviation** and **Average** of numeric values.</span></span> <span data-ttu-id="1aa30-115">Bei **Zeichen** folgen Objekten können Sie auch verwenden, `Measure-Object` um die Anzahl der Zeilen, Wörter und Zeichen zu zählen.</span><span class="sxs-lookup"><span data-stu-id="1aa30-115">For **String** objects, you can also use `Measure-Object` to count the number of lines, words, and characters.</span></span>

## <span data-ttu-id="1aa30-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1aa30-116">EXAMPLES</span></span>

### <span data-ttu-id="1aa30-117">Beispiel 1: zählen der Dateien und Ordner in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="1aa30-117">Example 1: Count the files and folders in a directory</span></span>

<span data-ttu-id="1aa30-118">Mit diesem Befehl werden die Dateien und Ordner im aktuellen Verzeichnis gezählt.</span><span class="sxs-lookup"><span data-stu-id="1aa30-118">This command counts the files and folders in the current directory.</span></span>

```powershell
Get-ChildItem | Measure-Object
```

### <span data-ttu-id="1aa30-119">Beispiel 2: Messen der Dateien in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="1aa30-119">Example 2: Measure the files in a directory</span></span>

<span data-ttu-id="1aa30-120">Mit diesem Befehl werden die **Mindest** -, **höchst** -und **Summen** Werte der Größe aller Dateien im aktuellen Verzeichnis und die durchschnittliche Größe einer Datei im Verzeichnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1aa30-120">This command displays the **Minimum** , **Maximum** , and **Sum** of the sizes of all files in the current directory, and the average size of a file in the directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Property length -Minimum -Maximum -Average
```

### <span data-ttu-id="1aa30-121">Beispiel 3: Messen von Text in einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="1aa30-121">Example 3: Measure text in a text file</span></span>

<span data-ttu-id="1aa30-122">Mit diesem Befehl wird die Anzahl der Zeichen, Wörter und Zeilen in der Datei „Text.txt“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1aa30-122">This command displays the number of characters, words, and lines in the Text.txt file.</span></span>
<span data-ttu-id="1aa30-123">Ohne den **RAW** -Parameter gibt `Get-Content` die Datei als Array von Zeilen aus.</span><span class="sxs-lookup"><span data-stu-id="1aa30-123">Without the **Raw** parameter, `Get-Content` outputs the file as an array of lines.</span></span>

<span data-ttu-id="1aa30-124">Der erste Befehl verwendet `Set-Content` , um einer Datei einen Standardtext hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1aa30-124">The first command uses `Set-Content` to add some default text to a file.</span></span>

```powershell
"One", "Two", "Three", "Four" | Set-Content -Path C:\Temp\tmp.txt
Get-Content C:\Temp\tmp.txt | Measure-Object -Character -Line -Word
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    4     4         15
```

### <span data-ttu-id="1aa30-125">Beispiel 4: Messen von Objekten, die eine angegebene Eigenschaft enthalten</span><span class="sxs-lookup"><span data-stu-id="1aa30-125">Example 4: Measure objects containing a specified Property</span></span>

<span data-ttu-id="1aa30-126">In diesem Beispiel wird die Anzahl der Objekte mit einer **Display Name** -Eigenschaft gezählt.</span><span class="sxs-lookup"><span data-stu-id="1aa30-126">This example counts the number of objects that have a **DisplayName** property.</span></span> <span data-ttu-id="1aa30-127">Die ersten beiden Befehle rufen alle Dienste und Prozesse auf dem lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="1aa30-127">The first two commands retrieve all the services and processes on the local machine.</span></span> <span data-ttu-id="1aa30-128">Mit dem dritten Befehl wird die kombinierte Anzahl von Diensten und Prozessen gezählt.</span><span class="sxs-lookup"><span data-stu-id="1aa30-128">The third command counts the combined number of services and processes.</span></span> <span data-ttu-id="1aa30-129">Der letzte Befehl kombiniert die beiden Auflistungen und leitet das Ergebnis an `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="1aa30-129">The last command combines the two collections and pipes the result to `Measure-Object`.</span></span>

<span data-ttu-id="1aa30-130">Das **System. Diagnostics. Process** -Objekt verfügt nicht über eine **Display Name** -Eigenschaft und wird von der endgültigen Anzahl ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="1aa30-130">The **System.Diagnostics.Process** object does not have a **DisplayName** property, and is left out of the final count.</span></span>

```powershell
$services = Get-Service
$processes = Get-Process
$services + $processes | Measure-Object
$services + $processes | Measure-Object -Property DisplayName
```

```Output
Count    : 682
Average  :
Sum      :
Maximum  :
Minimum  :
Property :

Count    : 290
Average  :
Sum      :
Maximum  :
Minimum  :
Property : DisplayName
```

### <span data-ttu-id="1aa30-131">Beispiel 5: Messen des Inhalts einer CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="1aa30-131">Example 5: Measure the contents of a CSV file</span></span>

<span data-ttu-id="1aa30-132">Mit diesem Befehl wird die durchschnittliche Betriebszugehörigkeit der Mitarbeiter eines Unternehmens berechnet.</span><span class="sxs-lookup"><span data-stu-id="1aa30-132">This command calculates the average years of service of the employees of a company.</span></span>

<span data-ttu-id="1aa30-133">Bei der `ServiceYrs.csv` Datei handelt es sich um eine CSV-Datei, die die Mitarbeiternummer und Dienstjahre jedes Mitarbeiters enthält.</span><span class="sxs-lookup"><span data-stu-id="1aa30-133">The `ServiceYrs.csv` file is a CSV file that contains the employee number and years of service of each employee.</span></span> <span data-ttu-id="1aa30-134">Die erste Zeile in der Tabelle ist eine Kopfzeile von **EmpNo** , **years**.</span><span class="sxs-lookup"><span data-stu-id="1aa30-134">The first row in the table is a header row of **EmpNo** , **Years**.</span></span>

<span data-ttu-id="1aa30-135">Wenn Sie verwenden `Import-Csv` , um die Datei zu importieren, ist das Ergebnis ein **pscustomobject** mit den Note-Eigenschaften **EmpNo** und **years**.</span><span class="sxs-lookup"><span data-stu-id="1aa30-135">When you use `Import-Csv` to import the file, the result is a **PSCustomObject** with note properties of **EmpNo** and **Years**.</span></span>
<span data-ttu-id="1aa30-136">Sie können verwenden, `Measure-Object` um die Werte dieser Eigenschaften genau wie jede andere Eigenschaft eines Objekts zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="1aa30-136">You can use `Measure-Object` to calculate the values of these properties, just like any other property of an object.</span></span>

```powershell
Import-Csv d:\test\serviceyrs.csv | Measure-Object -Property years -Minimum -Maximum -Average
```

### <span data-ttu-id="1aa30-137">Beispiel 6: Messen von booleschen Werten</span><span class="sxs-lookup"><span data-stu-id="1aa30-137">Example 6: Measure Boolean values</span></span>

<span data-ttu-id="1aa30-138">In diesem Beispiel wird veranschaulicht, wie `Measure-Object` boolesche Werte von gemessen werden können.</span><span class="sxs-lookup"><span data-stu-id="1aa30-138">This example demonstrates how the `Measure-Object` can measure Boolean values.</span></span>
<span data-ttu-id="1aa30-139">In diesem Fall wird die **boolesche** Eigenschaft **psiscontainer** verwendet, um das Vorkommen von Ordnern (vs. Dateien) im aktuellen Verzeichnis zu messen.</span><span class="sxs-lookup"><span data-stu-id="1aa30-139">In this case, it uses the **PSIsContainer** **Boolean** property to measure the incidence of folders (vs. files) in the current directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Property psiscontainer -Maximum -Sum -Minimum -Average
```

```Output
Count             : 126
Average           : 0.0634920634920635
Sum               : 8
Maximum           : 1
Minimum           : 0
StandardDeviation :
Property          : PSIsContainer
```

### <span data-ttu-id="1aa30-140">Beispiel 7: Messen von Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="1aa30-140">Example 7: Measure strings</span></span>

<span data-ttu-id="1aa30-141">Im folgenden Beispiel wird die Anzahl der Zeilen, zuerst eine einzelne Zeichenfolge, und dann für mehrere Zeichen folgen gemessen.</span><span class="sxs-lookup"><span data-stu-id="1aa30-141">The following example measures the number of lines, first a single string, then across several strings.</span></span> <span data-ttu-id="1aa30-142">Das Zeilen Umleitungs Zeichen trennt Zeichen folgen <code>\`n</code> in mehrere Zeilen.</span><span class="sxs-lookup"><span data-stu-id="1aa30-142">The newline character <code>\`n</code> separates strings into multiple lines.</span></span>

```powershell
# The newline character `n separates the string into separate lines, as shown in the output.
"One`nTwo`nThree"
"One`nTwo`nThree" | Measure-Object -Line
```

```Output
One
Two
Three


Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The first string counts as a single line.
# The second string is separated into two lines by the newline character.
"One", "Two`nThree" | Measure-Object -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The Word switch counts the number of words in each InputObject
# Each InputObject is treated as a single line.
"One, Two", "Three", "Four Five" | Measure-Object -Word -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3     5
```

## <span data-ttu-id="1aa30-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1aa30-143">PARAMETERS</span></span>

### <span data-ttu-id="1aa30-144">-Durchschnitt</span><span class="sxs-lookup"><span data-stu-id="1aa30-144">-Average</span></span>

<span data-ttu-id="1aa30-145">Gibt an, dass das Cmdlet den Durchschnittswert der angegebenen Eigenschaften anzeigt.</span><span class="sxs-lookup"><span data-stu-id="1aa30-145">Indicates that the cmdlet displays the average value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1aa30-146">-Zeichen</span><span class="sxs-lookup"><span data-stu-id="1aa30-146">-Character</span></span>

<span data-ttu-id="1aa30-147">Gibt an, dass das Cmdlet die Anzahl der Zeichen in den Eingabe Objekten zählt.</span><span class="sxs-lookup"><span data-stu-id="1aa30-147">Indicates that the cmdlet counts the number of characters in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="1aa30-148">Die Anzahl von **Wort** -, **char** -und **zeilenswitches** *in* jedem Eingabe Objekt sowie über alle Eingabe Objekte *hinweg* .</span><span class="sxs-lookup"><span data-stu-id="1aa30-148">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="1aa30-149">Siehe Beispiel 7.</span><span class="sxs-lookup"><span data-stu-id="1aa30-149">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1aa30-150">-IgnoreWhitespace</span><span class="sxs-lookup"><span data-stu-id="1aa30-150">-IgnoreWhiteSpace</span></span>

<span data-ttu-id="1aa30-151">Gibt an, dass das Cmdlet Leerraum in der Zeichen Anzahl ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1aa30-151">Indicates that the cmdlet ignores white space in character counts.</span></span>
<span data-ttu-id="1aa30-152">Leerzeichen werden standardmäßig nicht ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1aa30-152">By default, white space is not ignored.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1aa30-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1aa30-153">-InputObject</span></span>

<span data-ttu-id="1aa30-154">Gibt die Objekte an, die gemessen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1aa30-154">Specifies the objects to be measured.</span></span>
<span data-ttu-id="1aa30-155">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1aa30-155">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="1aa30-156">Wenn Sie den **Inputobject** -Parameter mit verwenden `Measure-Object` , anstatt Befehls Ergebnisse an zu übergeben `Measure-Object` , wird der **Inputobject** -Wert als einzelnes Objekt behandelt.</span><span class="sxs-lookup"><span data-stu-id="1aa30-156">When you use the **InputObject** parameter with `Measure-Object`, instead of piping command results to `Measure-Object`, the **InputObject** value is treated as a single object.</span></span>

<span data-ttu-id="1aa30-157">Es wird empfohlen, `Measure-Object` in der Pipeline zu verwenden, wenn Sie eine Auflistung von Objekten basierend darauf messen möchten, ob die Objekte über bestimmte Werte in definierten Eigenschaften verfügen.</span><span class="sxs-lookup"><span data-stu-id="1aa30-157">It is recommended that you use `Measure-Object` in the pipeline if you want to measure a collection of objects based on whether the objects have specific values in defined properties.</span></span>

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

### <span data-ttu-id="1aa30-158">-Zeile</span><span class="sxs-lookup"><span data-stu-id="1aa30-158">-Line</span></span>

<span data-ttu-id="1aa30-159">Gibt an, dass das Cmdlet die Anzahl der Zeilen in den Eingabe Objekten zählt.</span><span class="sxs-lookup"><span data-stu-id="1aa30-159">Indicates that the cmdlet counts the number of lines in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="1aa30-160">Die Anzahl von **Wort** -, **char** -und **zeilenswitches** *in* jedem Eingabe Objekt sowie über alle Eingabe Objekte *hinweg* .</span><span class="sxs-lookup"><span data-stu-id="1aa30-160">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="1aa30-161">Siehe Beispiel 7.</span><span class="sxs-lookup"><span data-stu-id="1aa30-161">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1aa30-162">-Maximum</span><span class="sxs-lookup"><span data-stu-id="1aa30-162">-Maximum</span></span>

<span data-ttu-id="1aa30-163">Gibt an, dass das Cmdlet den maximalen Wert der angegebenen Eigenschaften anzeigt.</span><span class="sxs-lookup"><span data-stu-id="1aa30-163">Indicates that the cmdlet displays the maximum value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1aa30-164">-Minimal</span><span class="sxs-lookup"><span data-stu-id="1aa30-164">-Minimum</span></span>

<span data-ttu-id="1aa30-165">Gibt an, dass das Cmdlet den minimalen Wert der angegebenen Eigenschaften anzeigt.</span><span class="sxs-lookup"><span data-stu-id="1aa30-165">Indicates that the cmdlet displays the minimum value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1aa30-166">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1aa30-166">-Property</span></span>

<span data-ttu-id="1aa30-167">Gibt eine oder mehrere Eigenschaften an, die gemessen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1aa30-167">Specifies one or more properties to measure.</span></span> <span data-ttu-id="1aa30-168">Wenn Sie keine weiteren Measures angeben, `Measure-Object` zählt die Objekte mit den von Ihnen angegebenen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="1aa30-168">If you do not specify any other measures, `Measure-Object` counts the objects that have the properties you specify.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="1aa30-169">-Sum</span><span class="sxs-lookup"><span data-stu-id="1aa30-169">-Sum</span></span>

<span data-ttu-id="1aa30-170">Gibt an, dass das Cmdlet die Summe der Werte der angegebenen Eigenschaften anzeigt.</span><span class="sxs-lookup"><span data-stu-id="1aa30-170">Indicates that the cmdlet displays the sum of the values of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1aa30-171">-Word</span><span class="sxs-lookup"><span data-stu-id="1aa30-171">-Word</span></span>

<span data-ttu-id="1aa30-172">Gibt an, dass das Cmdlet die Anzahl der Wörter in den Eingabe Objekten zählt.</span><span class="sxs-lookup"><span data-stu-id="1aa30-172">Indicates that the cmdlet counts the number of words in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="1aa30-173">Die Anzahl von **Wort** -, **char** -und **zeilenswitches** *in* jedem Eingabe Objekt sowie über alle Eingabe Objekte *hinweg* .</span><span class="sxs-lookup"><span data-stu-id="1aa30-173">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="1aa30-174">Siehe Beispiel 7.</span><span class="sxs-lookup"><span data-stu-id="1aa30-174">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1aa30-175">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1aa30-175">CommonParameters</span></span>

<span data-ttu-id="1aa30-176">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1aa30-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1aa30-177">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1aa30-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1aa30-178">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1aa30-178">INPUTS</span></span>

### <span data-ttu-id="1aa30-179">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="1aa30-179">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1aa30-180">Sie können Objekte über die Pipeline an übergeben `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="1aa30-180">You can pipe objects to `Measure-Object`.</span></span>

## <span data-ttu-id="1aa30-181">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1aa30-181">OUTPUTS</span></span>

### <span data-ttu-id="1aa30-182">Microsoft. PowerShell. Commands. genericmessreinfo</span><span class="sxs-lookup"><span data-stu-id="1aa30-182">Microsoft.PowerShell.Commands.GenericMeasureInfo</span></span>

### <span data-ttu-id="1aa30-183">Microsoft. PowerShell. Commands. textmess reinfo</span><span class="sxs-lookup"><span data-stu-id="1aa30-183">Microsoft.PowerShell.Commands.TextMeasureInfo</span></span>

<span data-ttu-id="1aa30-184">Wenn Sie den **Word** -Parameter verwenden, wird `Measure-Object` ein **textmessreinfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1aa30-184">If you use the **Word** parameter, `Measure-Object` returns a **TextMeasureInfo** object.</span></span>
<span data-ttu-id="1aa30-185">Andernfalls wird ein **genericmessreinfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1aa30-185">Otherwise, it returns a **GenericMeasureInfo** object.</span></span>

## <span data-ttu-id="1aa30-186">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1aa30-186">NOTES</span></span>

## <span data-ttu-id="1aa30-187">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1aa30-187">RELATED LINKS</span></span>

[<span data-ttu-id="1aa30-188">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="1aa30-188">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="1aa30-189">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="1aa30-189">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="1aa30-190">Group-Object</span><span class="sxs-lookup"><span data-stu-id="1aa30-190">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="1aa30-191">New-Object</span><span class="sxs-lookup"><span data-stu-id="1aa30-191">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="1aa30-192">Select-Object</span><span class="sxs-lookup"><span data-stu-id="1aa30-192">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="1aa30-193">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="1aa30-193">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="1aa30-194">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="1aa30-194">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="1aa30-195">Where-Object</span><span class="sxs-lookup"><span data-stu-id="1aa30-195">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
