---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Object
ms.openlocfilehash: 594837b2f85f4d5d5d4125d3f7c63ad2c8a16153
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596559"
---
# <span data-ttu-id="52bfd-102">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="52bfd-102">Measure-Object</span></span>

## <span data-ttu-id="52bfd-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="52bfd-103">SYNOPSIS</span></span>
<span data-ttu-id="52bfd-104">Berechnet die numerischen Eigenschaften von Objekten und die Zeichen, Wörter und Zeilen in Zeichenfolgenobjekten, z. B. Textdateien.</span><span class="sxs-lookup"><span data-stu-id="52bfd-104">Calculates the numeric properties of objects, and the characters, words, and lines in string objects, such as files of text.</span></span>

## <span data-ttu-id="52bfd-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="52bfd-105">SYNTAX</span></span>

### <span data-ttu-id="52bfd-106">Genericmeasure (Standard)</span><span class="sxs-lookup"><span data-stu-id="52bfd-106">GenericMeasure (Default)</span></span>

```
Measure-Object [[-Property] <PSPropertyExpression[]>] [-InputObject <PSObject>] [-StandardDeviation]
 [-Sum] [-AllStats] [-Average] [-Maximum] [-Minimum] [<CommonParameters>]
```

### <span data-ttu-id="52bfd-107">Textmeasure</span><span class="sxs-lookup"><span data-stu-id="52bfd-107">TextMeasure</span></span>

```
Measure-Object [[-Property] <PSPropertyExpression[]>] [-InputObject <PSObject>] [-Line] [-Word]
 [-Character] [-IgnoreWhiteSpace] [<CommonParameters>]
```

## <span data-ttu-id="52bfd-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="52bfd-108">DESCRIPTION</span></span>

<span data-ttu-id="52bfd-109">Das- `Measure-Object` Cmdlet berechnet die Eigenschaftswerte bestimmter Objekttypen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-109">The `Measure-Object` cmdlet calculates the property values of certain types of object.</span></span>
<span data-ttu-id="52bfd-110">`Measure-Object` führt abhängig von den Parametern im Befehl drei Arten von Messungen aus.</span><span class="sxs-lookup"><span data-stu-id="52bfd-110">`Measure-Object` performs three types of measurements, depending on the parameters in the command.</span></span>

<span data-ttu-id="52bfd-111">Das- `Measure-Object` Cmdlet führt Berechnungen für die Eigenschaftswerte von Objekten aus.</span><span class="sxs-lookup"><span data-stu-id="52bfd-111">The `Measure-Object` cmdlet performs calculations on the property values of objects.</span></span> <span data-ttu-id="52bfd-112">Sie können `Measure-Object` zum zählen von Objekten oder zum zählen von Objekten mit einer angegebenen **Eigenschaft** verwenden.</span><span class="sxs-lookup"><span data-stu-id="52bfd-112">You can use `Measure-Object` to count objects or count objects with a specified **Property**.</span></span> <span data-ttu-id="52bfd-113">Sie können auch verwenden `Measure-Object` , um die **Mindest**- **, höchst**-, **Summen**-, **Standardabweichung** und den **Durchschnitt** numerischer Werte zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-113">You can also use `Measure-Object` to calculate the **Minimum**, **Maximum**, **Sum**, **StandardDeviation** and **Average** of numeric values.</span></span> <span data-ttu-id="52bfd-114">Bei **Zeichen** folgen Objekten können Sie auch verwenden, `Measure-Object` um die Anzahl der Zeilen, Wörter und Zeichen zu zählen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-114">For **String** objects, you can also use `Measure-Object` to count the number of lines, words, and characters.</span></span>

## <span data-ttu-id="52bfd-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="52bfd-115">EXAMPLES</span></span>

### <span data-ttu-id="52bfd-116">Beispiel 1: zählen der Dateien und Ordner in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="52bfd-116">Example 1: Count the files and folders in a directory</span></span>

<span data-ttu-id="52bfd-117">Mit diesem Befehl werden die Dateien und Ordner im aktuellen Verzeichnis gezählt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-117">This command counts the files and folders in the current directory.</span></span>

```powershell
Get-ChildItem | Measure-Object
```

### <span data-ttu-id="52bfd-118">Beispiel 2: Messen der Dateien in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="52bfd-118">Example 2: Measure the files in a directory</span></span>

<span data-ttu-id="52bfd-119">Mit diesem Befehl werden die **Mindest**-, **höchst**-und **Summen** Werte der Größe aller Dateien im aktuellen Verzeichnis und die durchschnittliche Größe einer Datei im Verzeichnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-119">This command displays the **Minimum**, **Maximum**, and **Sum** of the sizes of all files in the current directory, and the average size of a file in the directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Property length -Minimum -Maximum -Average
```

### <span data-ttu-id="52bfd-120">Beispiel 3: Messen von Text in einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="52bfd-120">Example 3: Measure text in a text file</span></span>

<span data-ttu-id="52bfd-121">Mit diesem Befehl wird die Anzahl der Zeichen, Wörter und Zeilen in der Datei „Text.txt“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-121">This command displays the number of characters, words, and lines in the Text.txt file.</span></span>
<span data-ttu-id="52bfd-122">Ohne den **RAW** -Parameter gibt `Get-Content` die Datei als Array von Zeilen aus.</span><span class="sxs-lookup"><span data-stu-id="52bfd-122">Without the **Raw** parameter, `Get-Content` outputs the file as an array of lines.</span></span>

<span data-ttu-id="52bfd-123">Der erste Befehl verwendet `Set-Content` , um einer Datei einen Standardtext hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-123">The first command uses `Set-Content` to add some default text to a file.</span></span>

```powershell
"One", "Two", "Three", "Four" | Set-Content -Path C:\Temp\tmp.txt
Get-Content C:\Temp\tmp.txt | Measure-Object -Character -Line -Word
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    4     4         15
```

### <span data-ttu-id="52bfd-124">Beispiel 4: Messen von Objekten, die eine angegebene Eigenschaft enthalten</span><span class="sxs-lookup"><span data-stu-id="52bfd-124">Example 4: Measure objects containing a specified Property</span></span>

<span data-ttu-id="52bfd-125">In diesem Beispiel wird die Anzahl der Objekte mit einer **Display Name** -Eigenschaft gezählt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-125">This example counts the number of objects that have a **DisplayName** property.</span></span> <span data-ttu-id="52bfd-126">Die ersten beiden Befehle rufen alle Dienste und Prozesse auf dem lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="52bfd-126">The first two commands retrieve all the services and processes on the local machine.</span></span> <span data-ttu-id="52bfd-127">Mit dem dritten Befehl wird die kombinierte Anzahl von Diensten und Prozessen gezählt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-127">The third command counts the combined number of services and processes.</span></span> <span data-ttu-id="52bfd-128">Der letzte Befehl kombiniert die beiden Auflistungen und leitet das Ergebnis an `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="52bfd-128">The last command combines the two collections and pipes the result to `Measure-Object`.</span></span>

<span data-ttu-id="52bfd-129">Das **System. Diagnostics. Process** -Objekt verfügt nicht über eine **Display Name** -Eigenschaft und wird von der endgültigen Anzahl ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-129">The **System.Diagnostics.Process** object does not have a **DisplayName** property, and is left out of the final count.</span></span>

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

### <span data-ttu-id="52bfd-130">Beispiel 5: Messen des Inhalts einer CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="52bfd-130">Example 5: Measure the contents of a CSV file</span></span>

<span data-ttu-id="52bfd-131">Mit diesem Befehl wird die durchschnittliche Betriebszugehörigkeit der Mitarbeiter eines Unternehmens berechnet.</span><span class="sxs-lookup"><span data-stu-id="52bfd-131">This command calculates the average years of service of the employees of a company.</span></span>

<span data-ttu-id="52bfd-132">Bei der `ServiceYrs.csv` Datei handelt es sich um eine CSV-Datei, die die Mitarbeiternummer und Dienstjahre jedes Mitarbeiters enthält.</span><span class="sxs-lookup"><span data-stu-id="52bfd-132">The `ServiceYrs.csv` file is a CSV file that contains the employee number and years of service of each employee.</span></span> <span data-ttu-id="52bfd-133">Die erste Zeile in der Tabelle ist eine Kopfzeile von **EmpNo**, **years**.</span><span class="sxs-lookup"><span data-stu-id="52bfd-133">The first row in the table is a header row of **EmpNo**, **Years**.</span></span>

<span data-ttu-id="52bfd-134">Wenn Sie verwenden `Import-Csv` , um die Datei zu importieren, ist das Ergebnis ein **pscustomobject** mit den Note-Eigenschaften **EmpNo** und **years**.</span><span class="sxs-lookup"><span data-stu-id="52bfd-134">When you use `Import-Csv` to import the file, the result is a **PSCustomObject** with note properties of **EmpNo** and **Years**.</span></span>
<span data-ttu-id="52bfd-135">Sie können verwenden, `Measure-Object` um die Werte dieser Eigenschaften genau wie jede andere Eigenschaft eines Objekts zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-135">You can use `Measure-Object` to calculate the values of these properties, just like any other property of an object.</span></span>

```powershell
Import-Csv d:\test\serviceyrs.csv | Measure-Object -Property years -Minimum -Maximum -Average
```

### <span data-ttu-id="52bfd-136">Beispiel 6: Messen von booleschen Werten</span><span class="sxs-lookup"><span data-stu-id="52bfd-136">Example 6: Measure Boolean values</span></span>

<span data-ttu-id="52bfd-137">In diesem Beispiel wird veranschaulicht, wie `Measure-Object` boolesche Werte von gemessen werden können.</span><span class="sxs-lookup"><span data-stu-id="52bfd-137">This example demonstrates how the `Measure-Object` can measure Boolean values.</span></span>
<span data-ttu-id="52bfd-138">In diesem Fall wird die **boolesche** Eigenschaft **psiscontainer** verwendet, um das Vorkommen von Ordnern (vs. Dateien) im aktuellen Verzeichnis zu messen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-138">In this case, it uses the **PSIsContainer** **Boolean** property to measure the incidence of folders (vs. files) in the current directory.</span></span>

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

### <span data-ttu-id="52bfd-139">Beispiel 7: Messen von Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="52bfd-139">Example 7: Measure strings</span></span>

<span data-ttu-id="52bfd-140">Im folgenden Beispiel wird die Anzahl der Zeilen, zuerst eine einzelne Zeichenfolge, und dann für mehrere Zeichen folgen gemessen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-140">The following example measures the number of lines, first a single string, then across several strings.</span></span> <span data-ttu-id="52bfd-141">Das Zeilen Umleitungs Zeichen trennt Zeichen folgen <code>\`n</code> in mehrere Zeilen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-141">The newline character <code>\`n</code> separates strings into multiple lines.</span></span>

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

### <span data-ttu-id="52bfd-142">Beispiel 8: Messen aller Werte</span><span class="sxs-lookup"><span data-stu-id="52bfd-142">Example 8: Measure all the values</span></span>

<span data-ttu-id="52bfd-143">Ab PowerShell 6 können Sie mit dem **allstats** -Parameter von `Measure-Object` alle Statistiken gleichzeitig messen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-143">Beginning in PowerShell 6, the **AllStats** parameter of `Measure-Object` allows you to measure all the statistics together.</span></span>

```powershell
1..5 | Measure-Object -AllStats
```

```output
Count             : 5
Average           : 3
Sum               : 15
Maximum           : 5
Minimum           : 1
StandardDeviation : 1.58113883008419
Property          :
```

### <span data-ttu-id="52bfd-144">Beispiel 9: Messen der Verwendung von ScriptBlock-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="52bfd-144">Example 9: Measure using scriptblock properties</span></span>

<span data-ttu-id="52bfd-145">Ab PowerShell 6 `Measure-Object` unterstützt **ScriptBlock** -Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="52bfd-145">Beginning in PowerShell 6, `Measure-Object` supports **ScriptBlock** properties.</span></span> <span data-ttu-id="52bfd-146">Im folgenden Beispiel wird veranschaulicht, wie mit einer **ScriptBlock** -Eigenschaft die Größe aller Dateien in einem Verzeichnis festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="52bfd-146">The following example demonstrates how to use a **ScriptBlock** property to determine the size, in MegaBytes, of all the files in a directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Sum {$_.Length/1MB}
```

### <span data-ttu-id="52bfd-147">Beispiel 10: Messen von Hash Tabellen</span><span class="sxs-lookup"><span data-stu-id="52bfd-147">Example 10: Measure hashtables</span></span>

<span data-ttu-id="52bfd-148">Ab PowerShell 6 `Measure-Object` unterstützt die Messung von **Hash Tabellen** Eingaben.</span><span class="sxs-lookup"><span data-stu-id="52bfd-148">Beginning in PowerShell 6, `Measure-Object` supports measurement of **hashtable** input.</span></span> <span data-ttu-id="52bfd-149">Im folgenden Beispiel wird der größte Wert für den `num` Schlüssel von 3 **Hash Tabelle** -Objekten bestimmt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-149">The following example determines the largest value for the `num` key of 3 **hashtable** objects.</span></span>

```powershell
@{num=3}, @{num=4}, @{num=5} | Measure-Object -Maximum Num
```

```output
Count             : 3
Average           :
Sum               :
Maximum           : 5
Minimum           :
StandardDeviation :
Property          : num
```

### <span data-ttu-id="52bfd-150">Beispiel 11: Messen der Standard Abweichung</span><span class="sxs-lookup"><span data-stu-id="52bfd-150">Example 11: Measure the Standard Deviation</span></span>

<span data-ttu-id="52bfd-151">Ab PowerShell 6 `Measure-Object` unterstützt den- `-StandardDeviation` Parameter.</span><span class="sxs-lookup"><span data-stu-id="52bfd-151">Beginning in PowerShell 6, `Measure-Object` supports the `-StandardDeviation` parameter.</span></span> <span data-ttu-id="52bfd-152">Im folgenden Beispiel wird die *Standardabweichung* für die CPU ermittelt, die von allen Prozessen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="52bfd-152">The following example determines the *standard deviation* for the CPU used by all processes.</span></span> <span data-ttu-id="52bfd-153">Eine große Abweichung würde auf eine kleine Anzahl von Prozessen hindeuten, die die meiste CPU verbrauchen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-153">A large deviation would indicate a small number of processes consuming the most CPU.</span></span>

```powershell
Get-Process | Measure-Object -Average -StandardDeviation CPU
```

```output
Count             : 303
Average           : 163.032384488449
Sum               :
Maximum           :
Minimum           :
StandardDeviation : 859.444048419069
Property          : CPU
```

### <span data-ttu-id="52bfd-154">Beispiel 12: Messen mithilfe von Platzhaltern</span><span class="sxs-lookup"><span data-stu-id="52bfd-154">Example 12: Measure using wildcards</span></span>

<span data-ttu-id="52bfd-155">Ab PowerShell 6 `Measure-Object` unterstützt die Messung von Objekten mithilfe von Platzhaltern in Eigenschaftsnamen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-155">Beginning in PowerShell 6, `Measure-Object` supports measurement of objects by using wildcards in property names.</span></span> <span data-ttu-id="52bfd-156">Im folgenden Beispiel wird die maximale Anzahl von auslagerungsauslagerungsarbeitsspeicher für eine Reihe von Prozessen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-156">The following example determines the maximum of any type of paged memory usage among a set of processes.</span></span>

```powershell
Get-Process | Measure-Object -Maximum *paged*memory*size
```

```output
Count             : 303
Average           :
Sum               :
Maximum           : 735784
Minimum           :
StandardDeviation :
Property          : NonpagedSystemMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 352104448
Minimum           :
StandardDeviation :
Property          : PagedMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 2201968
Minimum           :
StandardDeviation :
Property          : PagedSystemMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 719032320
Minimum           :
StandardDeviation :
Property          : PeakPagedMemorySize
```

## <span data-ttu-id="52bfd-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="52bfd-157">PARAMETERS</span></span>

### <span data-ttu-id="52bfd-158">-Durchschnitt</span><span class="sxs-lookup"><span data-stu-id="52bfd-158">-Average</span></span>

<span data-ttu-id="52bfd-159">Gibt an, dass das Cmdlet den Durchschnittswert der angegebenen Eigenschaften anzeigt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-159">Indicates that the cmdlet displays the average value of the specified properties.</span></span>

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

### <span data-ttu-id="52bfd-160">-Zeichen</span><span class="sxs-lookup"><span data-stu-id="52bfd-160">-Character</span></span>

<span data-ttu-id="52bfd-161">Gibt an, dass das Cmdlet die Anzahl der Zeichen in den Eingabe Objekten zählt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-161">Indicates that the cmdlet counts the number of characters in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="52bfd-162">Die Anzahl von **Wort**-, **char** -und **zeilenswitches** *in* jedem Eingabe Objekt sowie über alle Eingabe Objekte *hinweg* .</span><span class="sxs-lookup"><span data-stu-id="52bfd-162">The **Word**, **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="52bfd-163">Siehe Beispiel 7.</span><span class="sxs-lookup"><span data-stu-id="52bfd-163">See Example 7.</span></span>

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

### <span data-ttu-id="52bfd-164">-IgnoreWhitespace</span><span class="sxs-lookup"><span data-stu-id="52bfd-164">-IgnoreWhiteSpace</span></span>

<span data-ttu-id="52bfd-165">Gibt an, dass das Cmdlet Leerraum in der Zeichen Anzahl ignoriert.</span><span class="sxs-lookup"><span data-stu-id="52bfd-165">Indicates that the cmdlet ignores white space in character counts.</span></span>
<span data-ttu-id="52bfd-166">Leerzeichen werden standardmäßig nicht ignoriert.</span><span class="sxs-lookup"><span data-stu-id="52bfd-166">By default, white space is not ignored.</span></span>

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

### <span data-ttu-id="52bfd-167">-InputObject</span><span class="sxs-lookup"><span data-stu-id="52bfd-167">-InputObject</span></span>

<span data-ttu-id="52bfd-168">Gibt die Objekte an, die gemessen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-168">Specifies the objects to be measured.</span></span>
<span data-ttu-id="52bfd-169">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="52bfd-169">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="52bfd-170">Wenn Sie den **Inputobject** -Parameter mit verwenden `Measure-Object` , anstatt Befehls Ergebnisse an zu übergeben `Measure-Object` , wird der **Inputobject** -Wert als einzelnes Objekt behandelt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-170">When you use the **InputObject** parameter with `Measure-Object`, instead of piping command results to `Measure-Object`, the **InputObject** value is treated as a single object.</span></span>

<span data-ttu-id="52bfd-171">Es wird empfohlen, `Measure-Object` in der Pipeline zu verwenden, wenn Sie eine Auflistung von Objekten basierend darauf messen möchten, ob die Objekte über bestimmte Werte in definierten Eigenschaften verfügen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-171">It is recommended that you use `Measure-Object` in the pipeline if you want to measure a collection of objects based on whether the objects have specific values in defined properties.</span></span>

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

### <span data-ttu-id="52bfd-172">-Zeile</span><span class="sxs-lookup"><span data-stu-id="52bfd-172">-Line</span></span>

<span data-ttu-id="52bfd-173">Gibt an, dass das Cmdlet die Anzahl der Zeilen in den Eingabe Objekten zählt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-173">Indicates that the cmdlet counts the number of lines in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="52bfd-174">Die Anzahl von **Wort**-, **char** -und **zeilenswitches** *in* jedem Eingabe Objekt sowie über alle Eingabe Objekte *hinweg* .</span><span class="sxs-lookup"><span data-stu-id="52bfd-174">The **Word**, **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="52bfd-175">Siehe Beispiel 7.</span><span class="sxs-lookup"><span data-stu-id="52bfd-175">See Example 7.</span></span>

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

### <span data-ttu-id="52bfd-176">-Maximum</span><span class="sxs-lookup"><span data-stu-id="52bfd-176">-Maximum</span></span>

<span data-ttu-id="52bfd-177">Gibt an, dass das Cmdlet den maximalen Wert der angegebenen Eigenschaften anzeigt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-177">Indicates that the cmdlet displays the maximum value of the specified properties.</span></span>

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

### <span data-ttu-id="52bfd-178">-Minimal</span><span class="sxs-lookup"><span data-stu-id="52bfd-178">-Minimum</span></span>

<span data-ttu-id="52bfd-179">Gibt an, dass das Cmdlet den minimalen Wert der angegebenen Eigenschaften anzeigt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-179">Indicates that the cmdlet displays the minimum value of the specified properties.</span></span>

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

### <span data-ttu-id="52bfd-180">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="52bfd-180">-Property</span></span>

<span data-ttu-id="52bfd-181">Gibt eine oder mehrere Eigenschaften an, die gemessen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-181">Specifies one or more properties to measure.</span></span> <span data-ttu-id="52bfd-182">Wenn Sie keine weiteren Measures angeben, `Measure-Object` zählt die Objekte mit den von Ihnen angegebenen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="52bfd-182">If you do not specify any other measures, `Measure-Object` counts the objects that have the properties you specify.</span></span>

<span data-ttu-id="52bfd-183">Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="52bfd-183">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="52bfd-184">Die berechnete Eigenschaft muss ein Skriptblock sein.</span><span class="sxs-lookup"><span data-stu-id="52bfd-184">The calculated property must be a script block.</span></span> <span data-ttu-id="52bfd-185">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="52bfd-185">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.PSPropertyExpression[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="52bfd-186">-Standardabweichung</span><span class="sxs-lookup"><span data-stu-id="52bfd-186">-StandardDeviation</span></span>

<span data-ttu-id="52bfd-187">Gibt an, dass das Cmdlet die Standardabweichung der Werte der angegebenen Eigenschaften anzeigt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-187">Indicates that the cmdlet displays the standard deviation of the values of the specified properties.</span></span>

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

### <span data-ttu-id="52bfd-188">-Sum</span><span class="sxs-lookup"><span data-stu-id="52bfd-188">-Sum</span></span>

<span data-ttu-id="52bfd-189">Gibt an, dass das Cmdlet die Summe der Werte der angegebenen Eigenschaften anzeigt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-189">Indicates that the cmdlet displays the sum of the values of the specified properties.</span></span>

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

### <span data-ttu-id="52bfd-190">-Allstats</span><span class="sxs-lookup"><span data-stu-id="52bfd-190">-AllStats</span></span>

<span data-ttu-id="52bfd-191">Gibt an, dass das Cmdlet alle Statistiken der angegebenen Eigenschaften anzeigt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-191">Indicates that the cmdlet displays all the statistics of the specified properties.</span></span>

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

### <span data-ttu-id="52bfd-192">-Word</span><span class="sxs-lookup"><span data-stu-id="52bfd-192">-Word</span></span>

<span data-ttu-id="52bfd-193">Gibt an, dass das Cmdlet die Anzahl der Wörter in den Eingabe Objekten zählt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-193">Indicates that the cmdlet counts the number of words in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="52bfd-194">Die Anzahl von **Wort**-, **char** -und **zeilenswitches** *in* jedem Eingabe Objekt sowie über alle Eingabe Objekte *hinweg* .</span><span class="sxs-lookup"><span data-stu-id="52bfd-194">The **Word**, **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="52bfd-195">Siehe Beispiel 7.</span><span class="sxs-lookup"><span data-stu-id="52bfd-195">See Example 7.</span></span>

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

### <span data-ttu-id="52bfd-196">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="52bfd-196">CommonParameters</span></span>

<span data-ttu-id="52bfd-197">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="52bfd-197">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="52bfd-198">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="52bfd-198">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="52bfd-199">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="52bfd-199">INPUTS</span></span>

### <span data-ttu-id="52bfd-200">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="52bfd-200">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="52bfd-201">Sie können Objekte über die Pipeline an übergeben `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="52bfd-201">You can pipe objects to `Measure-Object`.</span></span>

## <span data-ttu-id="52bfd-202">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="52bfd-202">OUTPUTS</span></span>

### <span data-ttu-id="52bfd-203">Microsoft. PowerShell. Commands. genericmessreinfo</span><span class="sxs-lookup"><span data-stu-id="52bfd-203">Microsoft.PowerShell.Commands.GenericMeasureInfo</span></span>

### <span data-ttu-id="52bfd-204">Microsoft. PowerShell. Commands. textmess reinfo</span><span class="sxs-lookup"><span data-stu-id="52bfd-204">Microsoft.PowerShell.Commands.TextMeasureInfo</span></span>

<span data-ttu-id="52bfd-205">Wenn Sie den **Word** -Parameter verwenden, wird `Measure-Object` ein **textmessreinfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="52bfd-205">If you use the **Word** parameter, `Measure-Object` returns a **TextMeasureInfo** object.</span></span>
<span data-ttu-id="52bfd-206">Andernfalls wird ein **genericmessreinfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="52bfd-206">Otherwise, it returns a **GenericMeasureInfo** object.</span></span>

## <span data-ttu-id="52bfd-207">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="52bfd-207">NOTES</span></span>

## <span data-ttu-id="52bfd-208">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="52bfd-208">RELATED LINKS</span></span>

[<span data-ttu-id="52bfd-209">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="52bfd-209">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="52bfd-210">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="52bfd-210">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="52bfd-211">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="52bfd-211">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="52bfd-212">Group-Object</span><span class="sxs-lookup"><span data-stu-id="52bfd-212">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="52bfd-213">New-Object</span><span class="sxs-lookup"><span data-stu-id="52bfd-213">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="52bfd-214">Select-Object</span><span class="sxs-lookup"><span data-stu-id="52bfd-214">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="52bfd-215">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="52bfd-215">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="52bfd-216">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="52bfd-216">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="52bfd-217">Where-Object</span><span class="sxs-lookup"><span data-stu-id="52bfd-217">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
