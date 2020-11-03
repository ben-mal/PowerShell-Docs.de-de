---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: c45b234445a7bc2b54aefb080d2d3da65433d412
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210759"
---
# <span data-ttu-id="28885-103">Get-Random</span><span class="sxs-lookup"><span data-stu-id="28885-103">Get-Random</span></span>

## <span data-ttu-id="28885-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="28885-104">SYNOPSIS</span></span>
<span data-ttu-id="28885-105">Ruft eine Zufallszahl ab oder wählt Objekte nach dem Zufallsprinzip aus einer Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="28885-105">Gets a random number, or selects objects randomly from a collection.</span></span>

## <span data-ttu-id="28885-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="28885-106">SYNTAX</span></span>

### <span data-ttu-id="28885-107">Randomnummeriparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="28885-107">RandomNumberParameterSet (Default)</span></span>

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [-Count <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="28885-108">Randomlistitemparameterset</span><span class="sxs-lookup"><span data-stu-id="28885-108">RandomListItemParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="28885-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28885-109">DESCRIPTION</span></span>

<span data-ttu-id="28885-110">Mit dem- `Get-Random` Cmdlet wird eine zufällig ausgewählte Zahl abgerufen.</span><span class="sxs-lookup"><span data-stu-id="28885-110">The `Get-Random` cmdlet gets a randomly selected number.</span></span> <span data-ttu-id="28885-111">Wenn Sie eine Auflistung von-Objekten an senden `Get-Random` , ruft Sie mindestens ein zufällig ausgewähltes Objekt aus der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="28885-111">If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.</span></span>

<span data-ttu-id="28885-112">Ohne Parameter oder Eingaben gibt ein `Get-Random` Befehl eine zufällig ausgewählte 32-Bit-Ganzzahl ohne Vorzeichen zwischen 0 (null) und **Int32. MaxValue** ( `0x7FFFFFFF` , `2,147,483,647` ) zurück.</span><span class="sxs-lookup"><span data-stu-id="28885-112">Without parameters or input, a `Get-Random` command returns a randomly selected 32-bit unsigned integer between 0 (zero) and **Int32.MaxValue** (`0x7FFFFFFF`, `2,147,483,647`).</span></span>

<span data-ttu-id="28885-113">Mit den Parametern von können Sie `Get-Random` eine Seed-Nummer, Mindest-und Höchstwerte sowie die Anzahl der von einer gesendeten Auflistung zurückgegebenen Objekte angeben.</span><span class="sxs-lookup"><span data-stu-id="28885-113">You can use the parameters of `Get-Random` to specify a seed number, minimum and maximum values, and the number of objects returned from a submitted collection.</span></span>

## <span data-ttu-id="28885-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="28885-114">EXAMPLES</span></span>

### <span data-ttu-id="28885-115">Beispiel 1: erhalten einer zufälligen Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="28885-115">Example 1: Get a random integer</span></span>

<span data-ttu-id="28885-116">Dieser Befehl ruft eine zufällige Ganzzahl zwischen 0 (null) und **Int32. MaxValue** ab.</span><span class="sxs-lookup"><span data-stu-id="28885-116">This command gets a random integer between 0 (zero) and **Int32.MaxValue** .</span></span>

```powershell
Get-Random
```

```Output
3951433
```

### <span data-ttu-id="28885-117">Beispiel 2: erhalten einer zufälligen Ganzzahl zwischen 0 und 99</span><span class="sxs-lookup"><span data-stu-id="28885-117">Example 2: Get a random integer between 0 and 99</span></span>

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### <span data-ttu-id="28885-118">Beispiel 3: erhalten einer zufälligen Ganzzahl zwischen-100 und 99</span><span class="sxs-lookup"><span data-stu-id="28885-118">Example 3: Get a random integer between -100 and 99</span></span>

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### <span data-ttu-id="28885-119">Beispiel 4: erhalten einer zufälligen Gleit Komma Zahl</span><span class="sxs-lookup"><span data-stu-id="28885-119">Example 4: Get a random floating-point number</span></span>

<span data-ttu-id="28885-120">Dieser Befehl ruft eine zufällige Gleitkommazahl ab, die größer oder gleich 10.7 und kleiner als 20.92 ist.</span><span class="sxs-lookup"><span data-stu-id="28885-120">This command gets a random floating-point number greater than or equal to 10.7 and less than 20.92.</span></span>

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### <span data-ttu-id="28885-121">Beispiel 5: erhalten einer zufälligen Ganzzahl aus einem Array</span><span class="sxs-lookup"><span data-stu-id="28885-121">Example 5: Get a random integer from an array</span></span>

<span data-ttu-id="28885-122">Dieser Befehl ruft eine zufällig ausgewählte Zahl aus dem angegebenen Array ab.</span><span class="sxs-lookup"><span data-stu-id="28885-122">This command gets a randomly selected number from the specified array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### <span data-ttu-id="28885-123">Beispiel 6: erhalten mehrerer zufälliger ganzzahlige Zahlen aus einem Array</span><span class="sxs-lookup"><span data-stu-id="28885-123">Example 6: Get several random integers from an array</span></span>

<span data-ttu-id="28885-124">Dieser Befehl ruft drei zufällig ausgewählte Zahlen in zufälliger Reihenfolge aus einem Array ab.</span><span class="sxs-lookup"><span data-stu-id="28885-124">This command gets three randomly selected numbers in random order from an array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### <span data-ttu-id="28885-125">Beispiel 7: Randomisieren einer gesamten Sammlung</span><span class="sxs-lookup"><span data-stu-id="28885-125">Example 7: Randomize an entire collection</span></span>

<span data-ttu-id="28885-126">Dieser Befehl gibt die gesamte Auflistung in zufälliger Reihenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="28885-126">This command returns the entire collection in random order.</span></span>

<span data-ttu-id="28885-127">Der Wert des **count** -Parameters ist die statische **MaxValue** -Eigenschaft von Integern.</span><span class="sxs-lookup"><span data-stu-id="28885-127">The value of the **Count** parameter is the **MaxValue** static property of integers.</span></span>

<span data-ttu-id="28885-128">Um eine ganze Auflistung in zufälliger Reihenfolge zurückgegeben, geben Sie eine Zahl ein, die größer oder gleich der Anzahl der Objekte in der Auflistung ist.</span><span class="sxs-lookup"><span data-stu-id="28885-128">To return an entire collection in random order, enter any number that is greater than or equal to the number of objects in the collection.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count ([int]::MaxValue)
```

```Output
2
3
5
1
8
13
```

### <span data-ttu-id="28885-129">Beispiel 8: erhalten eines zufälligen nicht numerischen Werts</span><span class="sxs-lookup"><span data-stu-id="28885-129">Example 8: Get a random non-numeric value</span></span>

<span data-ttu-id="28885-130">Dieser Befehl gibt einen zufälligen Wert aus einer nicht numerischen Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="28885-130">This command returns a random value from a non-numeric collection.</span></span>

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### <span data-ttu-id="28885-131">Beispiel 9: Verwenden des setseed-Parameters</span><span class="sxs-lookup"><span data-stu-id="28885-131">Example 9: Use the SetSeed parameter</span></span>

<span data-ttu-id="28885-132">Dieses Beispiel zeigt die Auswirkungen der Verwendung des **SetSeed** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="28885-132">This example shows the effect of using the **SetSeed** parameter.</span></span>

<span data-ttu-id="28885-133">Da **setseed** nicht zufälliges Verhalten erzeugt, wird es normalerweise nur zum Reproduzieren von Ergebnissen verwendet, z. b. beim Debuggen oder Analysieren eines Skripts.</span><span class="sxs-lookup"><span data-stu-id="28885-133">Because **SetSeed** produces non-random behavior, it's typically used only to reproduce results, such as when debugging or analyzing a script.</span></span>

```powershell
# Commands with the default seed are pseudorandom
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

```powershell
# Commands with the same seed are not random
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
```

```Output
74
74
74
```

```powershell
# SetSeed results in a repeatable series
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

### <span data-ttu-id="28885-134">Beispiel 10: Zufalls Dateien erhalten</span><span class="sxs-lookup"><span data-stu-id="28885-134">Example 10: Get random files</span></span>

<span data-ttu-id="28885-135">Mit diesen Befehlen wird eine zufällig ausgewählte Stichprobe von 50 Dateien vom `C:` Laufwerk des lokalen Computers erhalten.</span><span class="sxs-lookup"><span data-stu-id="28885-135">These commands get a randomly selected sample of 50 files from the `C:` drive of the local computer.</span></span>

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### <span data-ttu-id="28885-136">Beispiel 11: rollengerechte Würfel</span><span class="sxs-lookup"><span data-stu-id="28885-136">Example 11: Roll fair dice</span></span>

<span data-ttu-id="28885-137">In diesem Beispiel wird eine faire 1200-fache-Zeit ausgegeben, und die Ergebnisse werden gezählt.</span><span class="sxs-lookup"><span data-stu-id="28885-137">This example rolls a fair die 1200 times and counts the outcomes.</span></span> <span data-ttu-id="28885-138">Der erste Befehl `For-EachObject` wiederholt den Aufrufen `Get-Random` von aus den weitergeleiteten Zahlen (1-6).</span><span class="sxs-lookup"><span data-stu-id="28885-138">The first command, `For-EachObject` repeats the call to `Get-Random` from the piped in numbers (1-6).</span></span> <span data-ttu-id="28885-139">Die Ergebnisse werden nach ihrem Wert gruppiert `Group-Object` und als Tabelle mit formatiert `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="28885-139">The results are grouped by their value with `Group-Object` and formatted as a table with `Select-Object`.</span></span>

```powershell
1..1200 | ForEach-Object {
    1..6 | Get-Random
} | Group-Object | Select-Object Name,Count
```

```Output
Name Count
---- -----
1      206
2      199
3      196
4      226
5      185
6      188
```

### <span data-ttu-id="28885-140">Beispiel 12: Verwenden des count-Parameters</span><span class="sxs-lookup"><span data-stu-id="28885-140">Example 12: Use the Count parameter</span></span>

<span data-ttu-id="28885-141">Sie können jetzt den **count** -Parameter verwenden, ohne Objekte an zu übergeben `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="28885-141">You can now use the **Count** parameter without piping objects to `Get-Random`.</span></span>
<span data-ttu-id="28885-142">Im folgenden Beispiel werden drei Zufallszahlen abgerufen, die kleiner als 10 sind.</span><span class="sxs-lookup"><span data-stu-id="28885-142">The following example gets three random numbers less than 10.</span></span>

```powershell
Get-Random -Count 3 -Maximum 10
```

```Output
9
0
8
```

### <span data-ttu-id="28885-143">Beispiel 13: Verwenden Sie den Inputobject-Parameter mit einer leeren Zeichenfolge oder $NULL</span><span class="sxs-lookup"><span data-stu-id="28885-143">Example 13: Use the InputObject parameter with an empty string or $null</span></span>

<span data-ttu-id="28885-144">In diesem Beispiel gibt der **Inputobject** -Parameter ein Array an, das eine leere Zeichenfolge ( `''` ) und enthält `$null` .</span><span class="sxs-lookup"><span data-stu-id="28885-144">In this example, the **InputObject** parameter specifies an array that contains an empty string (`''`) and `$null`.</span></span>

```powershell
Get-Random -InputObject @('a','',$null)
```

<span data-ttu-id="28885-145">`Get-Random` Gibt entweder eine `a` leere Zeichenfolge oder zurück `$null` .</span><span class="sxs-lookup"><span data-stu-id="28885-145">`Get-Random` will return either `a`, empty string, or `$null`.</span></span> <span data-ttu-id="28885-146">Der leere Eintrag wird als leere Zeile angezeigt und `$null` kehrt zu einer PowerShell-Eingabeaufforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="28885-146">The empty sting displays as a blank line and `$null` returns to a PowerShell prompt.</span></span>

## <span data-ttu-id="28885-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="28885-147">PARAMETERS</span></span>

### <span data-ttu-id="28885-148">-Anzahl</span><span class="sxs-lookup"><span data-stu-id="28885-148">-Count</span></span>

<span data-ttu-id="28885-149">Gibt die Anzahl von zufälligen Objekten oder Ziffern an, die zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="28885-149">Specifies the number of random objects or numbers to return.</span></span> <span data-ttu-id="28885-150">Der Standard ist 1.</span><span class="sxs-lookup"><span data-stu-id="28885-150">The default is 1.</span></span>

<span data-ttu-id="28885-151">Bei Verwendung mit werden `InputObject` **Count** `Get-Random` alle Objekte in zufälliger Reihenfolge zurückgegeben, wenn der Wert von count die Anzahl der Objekte in der Auflistung überschreitet.</span><span class="sxs-lookup"><span data-stu-id="28885-151">When used with `InputObject`, if the value of **Count** exceeds the number of objects in the collection, `Get-Random` returns all of the objects in random order.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28885-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="28885-152">-InputObject</span></span>

<span data-ttu-id="28885-153">Gibt eine Auflistung von Objekten an.</span><span class="sxs-lookup"><span data-stu-id="28885-153">Specifies a collection of objects.</span></span> <span data-ttu-id="28885-154">`Get-Random` Ruft nach dem Zufallsprinzip ausgewählte Objekte in zufälliger Reihenfolge von der Auflistung bis zu der durch **count** angegebenen Zahl ab.</span><span class="sxs-lookup"><span data-stu-id="28885-154">`Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count** .</span></span> <span data-ttu-id="28885-155">Geben Sie die Objekte, eine Variable, die die Objekte enthält, oder einen Befehl oder Ausdruck ein, der die Objekte abruft.</span><span class="sxs-lookup"><span data-stu-id="28885-155">Enter the objects, a variable that contains the objects, or a command or expression that gets the objects.</span></span> <span data-ttu-id="28885-156">Sie können eine Auflistung von-Objekten auch über die Pipeline an senden `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="28885-156">You can also pipe a collection of objects to `Get-Random`.</span></span>

<span data-ttu-id="28885-157">Ab PowerShell 7 akzeptiert der **Inputobject** -Parameter Arrays, die eine leere Zeichenfolge oder enthalten können `$null` .</span><span class="sxs-lookup"><span data-stu-id="28885-157">Beginning in PowerShell 7, the **InputObject** parameter accepts arrays that can contain an empty string or `$null`.</span></span> <span data-ttu-id="28885-158">Das Array kann über die Pipeline oder als **Inputobject** -Parameterwert gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="28885-158">The array can be sent down the pipeline or as an **InputObject** parameter value.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: RandomListItemParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="28885-159">-Maximum</span><span class="sxs-lookup"><span data-stu-id="28885-159">-Maximum</span></span>

<span data-ttu-id="28885-160">Gibt einen maximalen Wert für die Zufallszahl an.</span><span class="sxs-lookup"><span data-stu-id="28885-160">Specifies a maximum value for the random number.</span></span> <span data-ttu-id="28885-161">`Get-Random` Gibt einen Wert zurück, der kleiner als der maximale Wert (nicht gleich) ist.</span><span class="sxs-lookup"><span data-stu-id="28885-161">`Get-Random` returns a value that is less than the maximum (not equal).</span></span> <span data-ttu-id="28885-162">Geben Sie eine ganze Zahl, eine Gleit Komma Zahl mit doppelter Genauigkeit oder ein Objekt ein, das in eine ganze Zahl oder einen Double-Wert konvertiert werden kann, z. b. eine numerische Zeichenfolge ("100").</span><span class="sxs-lookup"><span data-stu-id="28885-162">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span>

<span data-ttu-id="28885-163">Der Wert von **Maximum** muss größer sein als der Wert von **Minimum** (ungleich).</span><span class="sxs-lookup"><span data-stu-id="28885-163">The value of **Maximum** must be greater than (not equal to) the value of **Minimum** .</span></span> <span data-ttu-id="28885-164">Wenn der Wert von **Maximum** oder **Minimum** Maximum eine Gleit Komma Zahl ist, wird `Get-Random` eine nach dem Zufallsprinzip ausgewählte Gleit Komma Zahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="28885-164">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

<span data-ttu-id="28885-165">Auf einem 64-Bit-Computer ist der Standardwert von **Maximum** **Int32. MaxValue** , wenn der Wert von "Minimal" eine 32-Bit- **Ganzzahl** ist.</span><span class="sxs-lookup"><span data-stu-id="28885-165">On a 64-bit computer, if the value of **Minimum** is a 32-bit integer, the default value of **Maximum** is **Int32.MaxValue** .</span></span>

<span data-ttu-id="28885-166">Wenn der Wert von " **Minimal** " ein Double-Wert (eine Gleit Komma Zahl) ist, ist der Standardwert von " **Maximum** " **Double. MaxValue** .</span><span class="sxs-lookup"><span data-stu-id="28885-166">If the value of **Minimum** is a double (a floating-point number), the default value of **Maximum** is **Double.MaxValue** .</span></span> <span data-ttu-id="28885-167">Andernfalls ist der Standardwert **Int32. MaxValue** .</span><span class="sxs-lookup"><span data-stu-id="28885-167">Otherwise, the default value is **Int32.MaxValue** .</span></span>

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28885-168">-Minimal</span><span class="sxs-lookup"><span data-stu-id="28885-168">-Minimum</span></span>

<span data-ttu-id="28885-169">Gibt einen minimalen Wert für die Zufallszahl an.</span><span class="sxs-lookup"><span data-stu-id="28885-169">Specifies a minimum value for the random number.</span></span> <span data-ttu-id="28885-170">Geben Sie eine ganze Zahl, eine Gleit Komma Zahl mit doppelter Genauigkeit oder ein Objekt ein, das in eine ganze Zahl oder einen Double-Wert konvertiert werden kann, z. b. eine numerische Zeichenfolge ("100").</span><span class="sxs-lookup"><span data-stu-id="28885-170">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span> <span data-ttu-id="28885-171">Der Standardwert ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="28885-171">The default value is 0 (zero).</span></span>

<span data-ttu-id="28885-172">Der Wert von **Minimum** muss kleiner sein als der Wert von **Maximum** (ungleich).</span><span class="sxs-lookup"><span data-stu-id="28885-172">The value of **Minimum** must be less than (not equal to) the value of **Maximum** .</span></span> <span data-ttu-id="28885-173">Wenn der Wert von **Maximum** oder **Minimum** Maximum eine Gleit Komma Zahl ist, wird `Get-Random` eine nach dem Zufallsprinzip ausgewählte Gleit Komma Zahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="28885-173">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28885-174">-Setseed</span><span class="sxs-lookup"><span data-stu-id="28885-174">-SetSeed</span></span>

<span data-ttu-id="28885-175">Gibt einen Ausgangswert für den Zufallszahlengenerator an.</span><span class="sxs-lookup"><span data-stu-id="28885-175">Specifies a seed value for the random number generator.</span></span> <span data-ttu-id="28885-176">Dieser Ausgangswert wird für den aktuellen Befehl und für alle nachfolgenden `Get-Random` Befehle in der aktuellen Sitzung verwendet, bis Sie **setseed** erneut verwenden oder die Sitzung schließen.</span><span class="sxs-lookup"><span data-stu-id="28885-176">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="28885-177">Der Ausgangswert kann nicht auf seinen Standardwert zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="28885-177">You can't reset the seed to its default value.</span></span>

<span data-ttu-id="28885-178">Der **setseed** -Parameter ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="28885-178">The **SetSeed** parameter is not required.</span></span> <span data-ttu-id="28885-179">`Get-Random`In der Standardeinstellung verwendet die [randomnumgenerator ()](/dotnet/api/system.security.cryptography.randomnumbergenerator) -Methode, um einen Ausgangswert zu generieren.</span><span class="sxs-lookup"><span data-stu-id="28885-179">By default, `Get-Random` uses the [RandomNumberGenerator()](/dotnet/api/system.security.cryptography.randomnumbergenerator) method to generate a seed value.</span></span> <span data-ttu-id="28885-180">Da **setseed** nicht zufälliges Verhalten zur Folge hat, wird es normalerweise nur verwendet, wenn versucht wird, das Verhalten zu reproduzieren, beispielsweise beim Debuggen oder Analysieren eines Skripts, das- `Get-Random` Befehle enthält.</span><span class="sxs-lookup"><span data-stu-id="28885-180">Because **SetSeed** results in non-random behavior, it's typically used only when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28885-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="28885-181">CommonParameters</span></span>

<span data-ttu-id="28885-182">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="28885-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="28885-183">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="28885-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="28885-184">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="28885-184">INPUTS</span></span>

### <span data-ttu-id="28885-185">System.Object</span><span class="sxs-lookup"><span data-stu-id="28885-185">System.Object</span></span>

<span data-ttu-id="28885-186">Sie können ein oder mehrere-Objekte über die Pipeline übergeben.</span><span class="sxs-lookup"><span data-stu-id="28885-186">You can pipe one or more objects.</span></span> <span data-ttu-id="28885-187">`Get-Random` wählt Werte nach dem Zufallsprinzip aus den weitergeleiteten Objekten aus.</span><span class="sxs-lookup"><span data-stu-id="28885-187">`Get-Random` selects values randomly from the piped objects.</span></span>

## <span data-ttu-id="28885-188">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="28885-188">OUTPUTS</span></span>

### <span data-ttu-id="28885-189">System. Int32, System. Int64, System. Double</span><span class="sxs-lookup"><span data-stu-id="28885-189">System.Int32, System.Int64, System.Double</span></span>

<span data-ttu-id="28885-190">`Get-Random` gibt eine ganze Zahl oder Gleit Komma Zahl oder ein Objekt, das nach dem Zufallsprinzip aus einer gesendeten Auflistung ausgewählt wird, zurück.</span><span class="sxs-lookup"><span data-stu-id="28885-190">`Get-Random` returns an integer or floating-point number, or an object selected randomly from a submitted collection.</span></span>

## <span data-ttu-id="28885-191">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="28885-191">NOTES</span></span>

<span data-ttu-id="28885-192">`Get-Random` legt einen standardseed für jede Sitzung auf der Grundlage der Systemzeit fest, wenn die Sitzung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="28885-192">`Get-Random` sets a default seed for each session based on the system time clock when the session starts.</span></span>

<span data-ttu-id="28885-193">`Get-Random` gibt nicht immer denselben Datentyp wie der Eingabe Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="28885-193">`Get-Random` does not alway return the same data type as the input value.</span></span> <span data-ttu-id="28885-194">In der folgenden Tabelle wird der Ausgabetyp für jeden der numerischen Eingabetypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28885-194">The following table shows the output type for each of the numeric input types.</span></span>

| <span data-ttu-id="28885-195">Eingabetyp</span><span class="sxs-lookup"><span data-stu-id="28885-195">Input Type</span></span> | <span data-ttu-id="28885-196">Ausgabetyp</span><span class="sxs-lookup"><span data-stu-id="28885-196">Output Type</span></span> |
| :--------: | :---------: |
|   <span data-ttu-id="28885-197">SByte</span><span class="sxs-lookup"><span data-stu-id="28885-197">SByte</span></span>    |   <span data-ttu-id="28885-198">Double</span><span class="sxs-lookup"><span data-stu-id="28885-198">Double</span></span>    |
|    <span data-ttu-id="28885-199">Byte</span><span class="sxs-lookup"><span data-stu-id="28885-199">Byte</span></span>    |   <span data-ttu-id="28885-200">Double</span><span class="sxs-lookup"><span data-stu-id="28885-200">Double</span></span>    |
|   <span data-ttu-id="28885-201">Int16</span><span class="sxs-lookup"><span data-stu-id="28885-201">Int16</span></span>    |   <span data-ttu-id="28885-202">Double</span><span class="sxs-lookup"><span data-stu-id="28885-202">Double</span></span>    |
|   <span data-ttu-id="28885-203">UInt16</span><span class="sxs-lookup"><span data-stu-id="28885-203">UInt16</span></span>   |   <span data-ttu-id="28885-204">Double</span><span class="sxs-lookup"><span data-stu-id="28885-204">Double</span></span>    |
|   <span data-ttu-id="28885-205">Int32</span><span class="sxs-lookup"><span data-stu-id="28885-205">Int32</span></span>    |    <span data-ttu-id="28885-206">Int32</span><span class="sxs-lookup"><span data-stu-id="28885-206">Int32</span></span>    |
|   <span data-ttu-id="28885-207">UInt32</span><span class="sxs-lookup"><span data-stu-id="28885-207">UInt32</span></span>   |   <span data-ttu-id="28885-208">Double</span><span class="sxs-lookup"><span data-stu-id="28885-208">Double</span></span>    |
|   <span data-ttu-id="28885-209">Int64</span><span class="sxs-lookup"><span data-stu-id="28885-209">Int64</span></span>    |    <span data-ttu-id="28885-210">Int64</span><span class="sxs-lookup"><span data-stu-id="28885-210">Int64</span></span>    |
|   <span data-ttu-id="28885-211">UInt64</span><span class="sxs-lookup"><span data-stu-id="28885-211">UInt64</span></span>   |   <span data-ttu-id="28885-212">Double</span><span class="sxs-lookup"><span data-stu-id="28885-212">Double</span></span>    |
|   <span data-ttu-id="28885-213">Double</span><span class="sxs-lookup"><span data-stu-id="28885-213">Double</span></span>   |   <span data-ttu-id="28885-214">Double</span><span class="sxs-lookup"><span data-stu-id="28885-214">Double</span></span>    |
|   <span data-ttu-id="28885-215">Single</span><span class="sxs-lookup"><span data-stu-id="28885-215">Single</span></span>   |   <span data-ttu-id="28885-216">Double</span><span class="sxs-lookup"><span data-stu-id="28885-216">Double</span></span>    |

<span data-ttu-id="28885-217">Ab Windows PowerShell 3,0 `Get-Random` unterstützt ganze Zahlen mit 64 Bit.</span><span class="sxs-lookup"><span data-stu-id="28885-217">Beginning in Windows PowerShell 3.0, `Get-Random` supports 64-bit integers.</span></span> <span data-ttu-id="28885-218">In Windows PowerShell 2,0 werden alle Werte in **System. Int32** umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="28885-218">In Windows PowerShell 2.0, all values are cast to **System.Int32** .</span></span>

<span data-ttu-id="28885-219">Ab PowerShell 7 akzeptiert der **Inputobject** -Parameter im **randomlistitemparameterset** -Parametersatz Arrays, die eine leere Zeichenfolge oder enthalten `$null` .</span><span class="sxs-lookup"><span data-stu-id="28885-219">Beginning in PowerShell 7, the **InputObject** parameter in the **RandomListItemParameterSet** parameter set accepts arrays that contain an empty string or `$null`.</span></span> <span data-ttu-id="28885-220">In früheren PowerShell-Versionen hat nur der Parameter " **Maximum** " im Parametersatz " **randomnumparameterset** " eine leere Zeichenfolge oder akzeptiert `$null` .</span><span class="sxs-lookup"><span data-stu-id="28885-220">In earlier PowerShell versions, only the **Maximum** parameter in the **RandomNumberParameterSet** parameter set accepted an empty string or `$null`.</span></span>

## <span data-ttu-id="28885-221">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="28885-221">RELATED LINKS</span></span>
