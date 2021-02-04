---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 842d4ea92f60a92fddcddea11bb8155c708ac192
ms.sourcegitcommit: fa1a84c81e15f1ffac962110b0b4c850c1b173a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "99495957"
---
# <span data-ttu-id="d1e85-102">Get-Random</span><span class="sxs-lookup"><span data-stu-id="d1e85-102">Get-Random</span></span>

## <span data-ttu-id="d1e85-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d1e85-103">SYNOPSIS</span></span>
<span data-ttu-id="d1e85-104">Ruft eine Zufallszahl ab oder wählt Objekte nach dem Zufallsprinzip aus einer Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="d1e85-104">Gets a random number, or selects objects randomly from a collection.</span></span>

## <span data-ttu-id="d1e85-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d1e85-105">SYNTAX</span></span>

### <span data-ttu-id="d1e85-106">Randomnummeriparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="d1e85-106">RandomNumberParameterSet (Default)</span></span>

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [-Count <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="d1e85-107">Randomlistitemparameterset</span><span class="sxs-lookup"><span data-stu-id="d1e85-107">RandomListItemParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="d1e85-108">Shuffleparameterset</span><span class="sxs-lookup"><span data-stu-id="d1e85-108">ShuffleParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Shuffle] [<CommonParameters>]
```

## <span data-ttu-id="d1e85-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d1e85-109">DESCRIPTION</span></span>

<span data-ttu-id="d1e85-110">Mit dem- `Get-Random` Cmdlet wird eine zufällig ausgewählte Zahl abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d1e85-110">The `Get-Random` cmdlet gets a randomly selected number.</span></span> <span data-ttu-id="d1e85-111">Wenn Sie eine Auflistung von-Objekten an senden `Get-Random` , ruft Sie mindestens ein zufällig ausgewähltes Objekt aus der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="d1e85-111">If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.</span></span>

<span data-ttu-id="d1e85-112">Ohne Parameter oder Eingaben gibt ein `Get-Random` Befehl eine zufällig ausgewählte 32-Bit-Ganzzahl ohne Vorzeichen zwischen 0 (null) und **Int32. MaxValue** ( `0x7FFFFFFF` , `2,147,483,647` ) zurück.</span><span class="sxs-lookup"><span data-stu-id="d1e85-112">Without parameters or input, a `Get-Random` command returns a randomly selected 32-bit unsigned integer between 0 (zero) and **Int32.MaxValue** (`0x7FFFFFFF`, `2,147,483,647`).</span></span>

<span data-ttu-id="d1e85-113">Standardmäßig `Get-Random` generiert kryptografisch sichere Zufälligkeit mithilfe der [randomnumgenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="d1e85-113">By default, `Get-Random` generates cryptographically secure randomness using the [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) class.</span></span>

<span data-ttu-id="d1e85-114">Sie können die Parameter von verwenden, `Get-Random` um die Mindest-und Höchstwerte, die Anzahl der von einer Auflistung zurückgegebenen Objekte oder eine Seed-Nummer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d1e85-114">You can use the parameters of `Get-Random` to specify the minimum and maximum values, the number of objects returned from a collection, or a seed number.</span></span>

> [!CAUTION]
> <span data-ttu-id="d1e85-115">Das Festlegen des Seed führt absichtlich zu einem nicht zufälligen, wiederholbaren Verhalten.</span><span class="sxs-lookup"><span data-stu-id="d1e85-115">Setting the seed deliberately results in non-random, repeatable behavior.</span></span> <span data-ttu-id="d1e85-116">Es sollte nur verwendet werden, wenn versucht wird, das Verhalten zu reproduzieren, z. b. beim Debuggen oder Analysieren eines Skripts, das `Get-Random` Befehle enthält</span><span class="sxs-lookup"><span data-stu-id="d1e85-116">It should only be used when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>
>
> <span data-ttu-id="d1e85-117">Dieser Ausgangswert wird für den aktuellen Befehl und für alle nachfolgenden `Get-Random` Befehle in der aktuellen Sitzung verwendet, bis Sie **setseed** erneut verwenden oder die Sitzung schließen.</span><span class="sxs-lookup"><span data-stu-id="d1e85-117">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="d1e85-118">Der Ausgangswert kann nicht auf seinen Standardwert zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="d1e85-118">You can't reset the seed to its default value.</span></span>

## <span data-ttu-id="d1e85-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d1e85-119">EXAMPLES</span></span>

### <span data-ttu-id="d1e85-120">Beispiel 1: erhalten einer zufälligen Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="d1e85-120">Example 1: Get a random integer</span></span>

<span data-ttu-id="d1e85-121">Dieser Befehl ruft eine zufällige Ganzzahl zwischen 0 (null) und **Int32. MaxValue** ab.</span><span class="sxs-lookup"><span data-stu-id="d1e85-121">This command gets a random integer between 0 (zero) and **Int32.MaxValue**.</span></span>

```powershell
Get-Random
```

```Output
3951433
```

### <span data-ttu-id="d1e85-122">Beispiel 2: erhalten einer zufälligen Ganzzahl zwischen 0 und 99</span><span class="sxs-lookup"><span data-stu-id="d1e85-122">Example 2: Get a random integer between 0 and 99</span></span>

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### <span data-ttu-id="d1e85-123">Beispiel 3: erhalten einer zufälligen Ganzzahl zwischen-100 und 99</span><span class="sxs-lookup"><span data-stu-id="d1e85-123">Example 3: Get a random integer between -100 and 99</span></span>

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### <span data-ttu-id="d1e85-124">Beispiel 4: erhalten einer zufälligen Gleit Komma Zahl</span><span class="sxs-lookup"><span data-stu-id="d1e85-124">Example 4: Get a random floating-point number</span></span>

<span data-ttu-id="d1e85-125">Dieser Befehl ruft eine zufällige Gleitkommazahl ab, die größer oder gleich 10.7 und kleiner als 20.92 ist.</span><span class="sxs-lookup"><span data-stu-id="d1e85-125">This command gets a random floating-point number greater than or equal to 10.7 and less than 20.92.</span></span>

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### <span data-ttu-id="d1e85-126">Beispiel 5: erhalten einer zufälligen Ganzzahl aus einem Array</span><span class="sxs-lookup"><span data-stu-id="d1e85-126">Example 5: Get a random integer from an array</span></span>

<span data-ttu-id="d1e85-127">Dieser Befehl ruft eine zufällig ausgewählte Zahl aus dem angegebenen Array ab.</span><span class="sxs-lookup"><span data-stu-id="d1e85-127">This command gets a randomly selected number from the specified array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### <span data-ttu-id="d1e85-128">Beispiel 6: erhalten mehrerer zufälliger ganzzahlige Zahlen aus einem Array</span><span class="sxs-lookup"><span data-stu-id="d1e85-128">Example 6: Get several random integers from an array</span></span>

<span data-ttu-id="d1e85-129">Dieser Befehl ruft drei zufällig ausgewählte Zahlen in zufälliger Reihenfolge aus einem Array ab.</span><span class="sxs-lookup"><span data-stu-id="d1e85-129">This command gets three randomly selected numbers in random order from an array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### <span data-ttu-id="d1e85-130">Beispiel 7: Randomisieren einer gesamten Sammlung</span><span class="sxs-lookup"><span data-stu-id="d1e85-130">Example 7: Randomize an entire collection</span></span>

<span data-ttu-id="d1e85-131">Ab PowerShell 7,1 können Sie den **shuffle** -Parameter verwenden, um die gesamte Auflistung in zufälliger Reihenfolge zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d1e85-131">Starting in PowerShell 7.1, you can use the **Shuffle** parameter to return the entire collection in a random order.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Shuffle
```

```Output
2
3
5
1
8
13
```

### <span data-ttu-id="d1e85-132">Beispiel 8: erhalten eines zufälligen nicht numerischen Werts</span><span class="sxs-lookup"><span data-stu-id="d1e85-132">Example 8: Get a random non-numeric value</span></span>

<span data-ttu-id="d1e85-133">Dieser Befehl gibt einen zufälligen Wert aus einer nicht numerischen Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="d1e85-133">This command returns a random value from a non-numeric collection.</span></span>

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### <span data-ttu-id="d1e85-134">Beispiel 9: Verwenden des setseed-Parameters</span><span class="sxs-lookup"><span data-stu-id="d1e85-134">Example 9: Use the SetSeed parameter</span></span>

<span data-ttu-id="d1e85-135">Dieses Beispiel zeigt die Auswirkungen der Verwendung des **SetSeed**-Parameters.</span><span class="sxs-lookup"><span data-stu-id="d1e85-135">This example shows the effect of using the **SetSeed** parameter.</span></span>

<span data-ttu-id="d1e85-136">Da **setseed** nicht zufälliges Verhalten erzeugt, wird es normalerweise nur zum Reproduzieren von Ergebnissen verwendet, z. b. beim Debuggen oder Analysieren eines Skripts.</span><span class="sxs-lookup"><span data-stu-id="d1e85-136">Because **SetSeed** produces non-random behavior, it's typically used only to reproduce results, such as when debugging or analyzing a script.</span></span>

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

### <span data-ttu-id="d1e85-137">Beispiel 10: Zufalls Dateien erhalten</span><span class="sxs-lookup"><span data-stu-id="d1e85-137">Example 10: Get random files</span></span>

<span data-ttu-id="d1e85-138">Mit diesen Befehlen wird eine zufällig ausgewählte Stichprobe von 50 Dateien vom `C:` Laufwerk des lokalen Computers erhalten.</span><span class="sxs-lookup"><span data-stu-id="d1e85-138">These commands get a randomly selected sample of 50 files from the `C:` drive of the local computer.</span></span>

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### <span data-ttu-id="d1e85-139">Beispiel 11: rollengerechte Würfel</span><span class="sxs-lookup"><span data-stu-id="d1e85-139">Example 11: Roll fair dice</span></span>

<span data-ttu-id="d1e85-140">In diesem Beispiel wird eine faire 1200-fache-Zeit ausgegeben, und die Ergebnisse werden gezählt.</span><span class="sxs-lookup"><span data-stu-id="d1e85-140">This example rolls a fair die 1200 times and counts the outcomes.</span></span> <span data-ttu-id="d1e85-141">Der erste Befehl `ForEach-Object` wiederholt den Aufrufen `Get-Random` von aus den weitergeleiteten Zahlen (1-6).</span><span class="sxs-lookup"><span data-stu-id="d1e85-141">The first command, `ForEach-Object` repeats the call to `Get-Random` from the piped in numbers (1-6).</span></span> <span data-ttu-id="d1e85-142">Die Ergebnisse werden nach ihrem Wert gruppiert `Group-Object` und als Tabelle mit formatiert `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="d1e85-142">The results are grouped by their value with `Group-Object` and formatted as a table with `Select-Object`.</span></span>

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

### <span data-ttu-id="d1e85-143">Beispiel 12: Verwenden des count-Parameters</span><span class="sxs-lookup"><span data-stu-id="d1e85-143">Example 12: Use the Count parameter</span></span>

<span data-ttu-id="d1e85-144">Sie können jetzt den **count** -Parameter verwenden, ohne Objekte an zu übergeben `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="d1e85-144">You can now use the **Count** parameter without piping objects to `Get-Random`.</span></span>
<span data-ttu-id="d1e85-145">Im folgenden Beispiel werden drei Zufallszahlen abgerufen, die kleiner als 10 sind.</span><span class="sxs-lookup"><span data-stu-id="d1e85-145">The following example gets three random numbers less than 10.</span></span>

```powershell
Get-Random -Count 3 -Maximum 10
```

```Output
9
0
8
```

### <span data-ttu-id="d1e85-146">Beispiel 13: Verwenden Sie den Inputobject-Parameter mit einer leeren Zeichenfolge oder $NULL</span><span class="sxs-lookup"><span data-stu-id="d1e85-146">Example 13: Use the InputObject parameter with an empty string or $null</span></span>

<span data-ttu-id="d1e85-147">In diesem Beispiel gibt der **Inputobject** -Parameter ein Array an, das eine leere Zeichenfolge ( `''` ) und enthält `$null` .</span><span class="sxs-lookup"><span data-stu-id="d1e85-147">In this example, the **InputObject** parameter specifies an array that contains an empty string (`''`) and `$null`.</span></span>

```powershell
Get-Random -InputObject @('a','',$null)
```

<span data-ttu-id="d1e85-148">`Get-Random` Gibt entweder eine `a` leere Zeichenfolge oder zurück `$null` .</span><span class="sxs-lookup"><span data-stu-id="d1e85-148">`Get-Random` will return either `a`, empty string, or `$null`.</span></span> <span data-ttu-id="d1e85-149">Der leere Eintrag wird als leere Zeile angezeigt und `$null` kehrt zu einer PowerShell-Eingabeaufforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="d1e85-149">The empty sting displays as a blank line and `$null` returns to a PowerShell prompt.</span></span>

## <span data-ttu-id="d1e85-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d1e85-150">PARAMETERS</span></span>

### <span data-ttu-id="d1e85-151">-Anzahl</span><span class="sxs-lookup"><span data-stu-id="d1e85-151">-Count</span></span>

<span data-ttu-id="d1e85-152">Gibt die Anzahl von zufälligen Objekten oder Ziffern an, die zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d1e85-152">Specifies the number of random objects or numbers to return.</span></span> <span data-ttu-id="d1e85-153">Der Standardwert ist 1.</span><span class="sxs-lookup"><span data-stu-id="d1e85-153">The default is 1.</span></span>

<span data-ttu-id="d1e85-154">Bei Verwendung mit werden `InputObject`  `Get-Random` alle Objekte in zufälliger Reihenfolge zurückgegeben, wenn der Wert von count die Anzahl der Objekte in der Auflistung überschreitet.</span><span class="sxs-lookup"><span data-stu-id="d1e85-154">When used with `InputObject`, if the value of **Count** exceeds the number of objects in the collection, `Get-Random` returns all of the objects in random order.</span></span>

```yaml
Type: System.Int32
Parameter Sets: RandomNumberParameterSet, RandomListItemParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d1e85-155">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d1e85-155">-InputObject</span></span>

<span data-ttu-id="d1e85-156">Gibt eine Auflistung von Objekten an.</span><span class="sxs-lookup"><span data-stu-id="d1e85-156">Specifies a collection of objects.</span></span> <span data-ttu-id="d1e85-157">`Get-Random` Ruft nach dem Zufallsprinzip ausgewählte Objekte in zufälliger Reihenfolge von der Auflistung bis zu der durch **count** angegebenen Zahl ab.</span><span class="sxs-lookup"><span data-stu-id="d1e85-157">`Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count**.</span></span> <span data-ttu-id="d1e85-158">Geben Sie die Objekte, eine Variable, die die Objekte enthält, oder einen Befehl oder Ausdruck ein, der die Objekte abruft.</span><span class="sxs-lookup"><span data-stu-id="d1e85-158">Enter the objects, a variable that contains the objects, or a command or expression that gets the objects.</span></span> <span data-ttu-id="d1e85-159">Sie können eine Auflistung von-Objekten auch über die Pipeline an senden `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="d1e85-159">You can also pipe a collection of objects to `Get-Random`.</span></span>

<span data-ttu-id="d1e85-160">Ab PowerShell 7 akzeptiert der **Inputobject** -Parameter Arrays, die eine leere Zeichenfolge oder enthalten können `$null` .</span><span class="sxs-lookup"><span data-stu-id="d1e85-160">Beginning in PowerShell 7, the **InputObject** parameter accepts arrays that can contain an empty string or `$null`.</span></span> <span data-ttu-id="d1e85-161">Das Array kann über die Pipeline oder als **Inputobject** -Parameterwert gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d1e85-161">The array can be sent down the pipeline or as an **InputObject** parameter value.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: RandomListItemParameterSet, ShuffleParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d1e85-162">-Maximum</span><span class="sxs-lookup"><span data-stu-id="d1e85-162">-Maximum</span></span>

<span data-ttu-id="d1e85-163">Gibt einen maximalen Wert für die Zufallszahl an.</span><span class="sxs-lookup"><span data-stu-id="d1e85-163">Specifies a maximum value for the random number.</span></span> <span data-ttu-id="d1e85-164">`Get-Random` Gibt einen Wert zurück, der kleiner als der maximale Wert (nicht gleich) ist.</span><span class="sxs-lookup"><span data-stu-id="d1e85-164">`Get-Random` returns a value that is less than the maximum (not equal).</span></span> <span data-ttu-id="d1e85-165">Geben Sie eine ganze Zahl, eine Gleit Komma Zahl mit doppelter Genauigkeit oder ein Objekt ein, das in eine ganze Zahl oder einen Double-Wert konvertiert werden kann, z. b. eine numerische Zeichenfolge ("100").</span><span class="sxs-lookup"><span data-stu-id="d1e85-165">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span>

<span data-ttu-id="d1e85-166">Der Wert von **Maximum** muss größer sein als der Wert von **Minimum** (ungleich).</span><span class="sxs-lookup"><span data-stu-id="d1e85-166">The value of **Maximum** must be greater than (not equal to) the value of **Minimum**.</span></span> <span data-ttu-id="d1e85-167">Wenn der Wert von **Maximum** oder  Maximum eine Gleit Komma Zahl ist, wird `Get-Random` eine nach dem Zufallsprinzip ausgewählte Gleit Komma Zahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d1e85-167">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

<span data-ttu-id="d1e85-168">Auf einem 64-Bit-Computer ist der Standardwert von **Maximum** **Int32. MaxValue**, wenn der Wert von "Minimal" eine 32-Bit- **Ganzzahl** ist.</span><span class="sxs-lookup"><span data-stu-id="d1e85-168">On a 64-bit computer, if the value of **Minimum** is a 32-bit integer, the default value of **Maximum** is **Int32.MaxValue**.</span></span>

<span data-ttu-id="d1e85-169">Wenn der Wert von " **Minimal** " ein Double-Wert (eine Gleit Komma Zahl) ist, ist der Standardwert von " **Maximum** " **Double. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="d1e85-169">If the value of **Minimum** is a double (a floating-point number), the default value of **Maximum** is **Double.MaxValue**.</span></span> <span data-ttu-id="d1e85-170">Andernfalls ist der Standardwert **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="d1e85-170">Otherwise, the default value is **Int32.MaxValue**.</span></span>

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

### <span data-ttu-id="d1e85-171">-Minimal</span><span class="sxs-lookup"><span data-stu-id="d1e85-171">-Minimum</span></span>

<span data-ttu-id="d1e85-172">Gibt einen minimalen Wert für die Zufallszahl an.</span><span class="sxs-lookup"><span data-stu-id="d1e85-172">Specifies a minimum value for the random number.</span></span> <span data-ttu-id="d1e85-173">Geben Sie eine ganze Zahl, eine Gleit Komma Zahl mit doppelter Genauigkeit oder ein Objekt ein, das in eine ganze Zahl oder einen Double-Wert konvertiert werden kann, z. b. eine numerische Zeichenfolge ("100").</span><span class="sxs-lookup"><span data-stu-id="d1e85-173">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span> <span data-ttu-id="d1e85-174">Der Standardwert ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="d1e85-174">The default value is 0 (zero).</span></span>

<span data-ttu-id="d1e85-175">Der Wert von **Minimum** muss kleiner sein als der Wert von **Maximum** (ungleich).</span><span class="sxs-lookup"><span data-stu-id="d1e85-175">The value of **Minimum** must be less than (not equal to) the value of **Maximum**.</span></span> <span data-ttu-id="d1e85-176">Wenn der Wert von **Maximum** oder  Maximum eine Gleit Komma Zahl ist, wird `Get-Random` eine nach dem Zufallsprinzip ausgewählte Gleit Komma Zahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d1e85-176">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

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

### <span data-ttu-id="d1e85-177">-Setseed</span><span class="sxs-lookup"><span data-stu-id="d1e85-177">-SetSeed</span></span>

<span data-ttu-id="d1e85-178">Gibt einen Ausgangswert für den Zufallszahlengenerator an.</span><span class="sxs-lookup"><span data-stu-id="d1e85-178">Specifies a seed value for the random number generator.</span></span> <span data-ttu-id="d1e85-179">Wenn Sie **setseed** verwenden, verwendet das Cmdlet die [System. Random](/dotnet/api/system.random) -Methode, um Pseudo Zufalls-Nummern zu generieren, die nicht kryptografisch sicher sind.</span><span class="sxs-lookup"><span data-stu-id="d1e85-179">When you use **SetSeed**, the cmdlet uses the [System.Random](/dotnet/api/system.random) method to generate pseudorandom numbers, which is not cryptographically secure.</span></span>

> [!CAUTION]
> <span data-ttu-id="d1e85-180">Das Festlegen des Seed führt zu einem nicht zufälligen Verhalten.</span><span class="sxs-lookup"><span data-stu-id="d1e85-180">Setting the seed results in non-random behavior.</span></span> <span data-ttu-id="d1e85-181">Es sollte nur verwendet werden, wenn versucht wird, das Verhalten zu reproduzieren, z. b. beim Debuggen oder Analysieren eines Skripts, das `Get-Random` Befehle enthält</span><span class="sxs-lookup"><span data-stu-id="d1e85-181">It should only be used when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>
>
> <span data-ttu-id="d1e85-182">Dieser Ausgangswert wird für den aktuellen Befehl und für alle nachfolgenden `Get-Random` Befehle in der aktuellen Sitzung verwendet, bis Sie **setseed** erneut verwenden oder die Sitzung schließen.</span><span class="sxs-lookup"><span data-stu-id="d1e85-182">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="d1e85-183">Der Ausgangswert kann nicht auf seinen Standardwert zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="d1e85-183">You can't reset the seed to its default value.</span></span>

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

### <span data-ttu-id="d1e85-184">-Shuffle</span><span class="sxs-lookup"><span data-stu-id="d1e85-184">-Shuffle</span></span>

<span data-ttu-id="d1e85-185">Gibt die gesamte Auflistung in einer zufälligen Reihenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="d1e85-185">Returns the entire collection in a randomized order.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ShuffleParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d1e85-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d1e85-186">CommonParameters</span></span>

<span data-ttu-id="d1e85-187">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d1e85-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d1e85-188">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d1e85-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d1e85-189">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d1e85-189">INPUTS</span></span>

### <span data-ttu-id="d1e85-190">System.Object</span><span class="sxs-lookup"><span data-stu-id="d1e85-190">System.Object</span></span>

<span data-ttu-id="d1e85-191">Sie können ein oder mehrere-Objekte über die Pipeline übergeben.</span><span class="sxs-lookup"><span data-stu-id="d1e85-191">You can pipe one or more objects.</span></span> <span data-ttu-id="d1e85-192">`Get-Random` wählt Werte nach dem Zufallsprinzip aus den weitergeleiteten Objekten aus.</span><span class="sxs-lookup"><span data-stu-id="d1e85-192">`Get-Random` selects values randomly from the piped objects.</span></span>

## <span data-ttu-id="d1e85-193">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d1e85-193">OUTPUTS</span></span>

### <span data-ttu-id="d1e85-194">System. Int32, System. Int64, System. Double</span><span class="sxs-lookup"><span data-stu-id="d1e85-194">System.Int32, System.Int64, System.Double</span></span>

<span data-ttu-id="d1e85-195">`Get-Random` gibt eine ganze Zahl oder Gleit Komma Zahl oder ein Objekt, das nach dem Zufallsprinzip aus einer gesendeten Auflistung ausgewählt wird, zurück.</span><span class="sxs-lookup"><span data-stu-id="d1e85-195">`Get-Random` returns an integer or floating-point number, or an object selected randomly from a submitted collection.</span></span>

## <span data-ttu-id="d1e85-196">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d1e85-196">NOTES</span></span>

<span data-ttu-id="d1e85-197">Standardmäßig `Get-Random` generiert kryptografisch sichere Zufälligkeit mithilfe der [randomnumgenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="d1e85-197">By default, `Get-Random` generates cryptographically secure randomness using the [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) class.</span></span>

<span data-ttu-id="d1e85-198">`Get-Random` gibt nicht immer denselben Datentyp wie der Eingabe Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="d1e85-198">`Get-Random` does not alway return the same data type as the input value.</span></span> <span data-ttu-id="d1e85-199">In der folgenden Tabelle wird der Ausgabetyp für jeden der numerischen Eingabetypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d1e85-199">The following table shows the output type for each of the numeric input types.</span></span>

| <span data-ttu-id="d1e85-200">Eingabetyp</span><span class="sxs-lookup"><span data-stu-id="d1e85-200">Input Type</span></span> | <span data-ttu-id="d1e85-201">Ausgabetyp</span><span class="sxs-lookup"><span data-stu-id="d1e85-201">Output Type</span></span> |
| :--------: | :---------: |
|   <span data-ttu-id="d1e85-202">SByte</span><span class="sxs-lookup"><span data-stu-id="d1e85-202">SByte</span></span>    |   <span data-ttu-id="d1e85-203">Double</span><span class="sxs-lookup"><span data-stu-id="d1e85-203">Double</span></span>    |
|    <span data-ttu-id="d1e85-204">Byte</span><span class="sxs-lookup"><span data-stu-id="d1e85-204">Byte</span></span>    |   <span data-ttu-id="d1e85-205">Double</span><span class="sxs-lookup"><span data-stu-id="d1e85-205">Double</span></span>    |
|   <span data-ttu-id="d1e85-206">Int16</span><span class="sxs-lookup"><span data-stu-id="d1e85-206">Int16</span></span>    |   <span data-ttu-id="d1e85-207">Double</span><span class="sxs-lookup"><span data-stu-id="d1e85-207">Double</span></span>    |
|   <span data-ttu-id="d1e85-208">UInt16</span><span class="sxs-lookup"><span data-stu-id="d1e85-208">UInt16</span></span>   |   <span data-ttu-id="d1e85-209">Double</span><span class="sxs-lookup"><span data-stu-id="d1e85-209">Double</span></span>    |
|   <span data-ttu-id="d1e85-210">Int32</span><span class="sxs-lookup"><span data-stu-id="d1e85-210">Int32</span></span>    |    <span data-ttu-id="d1e85-211">Int32</span><span class="sxs-lookup"><span data-stu-id="d1e85-211">Int32</span></span>    |
|   <span data-ttu-id="d1e85-212">UInt32</span><span class="sxs-lookup"><span data-stu-id="d1e85-212">UInt32</span></span>   |   <span data-ttu-id="d1e85-213">Double</span><span class="sxs-lookup"><span data-stu-id="d1e85-213">Double</span></span>    |
|   <span data-ttu-id="d1e85-214">Int64</span><span class="sxs-lookup"><span data-stu-id="d1e85-214">Int64</span></span>    |    <span data-ttu-id="d1e85-215">Int64</span><span class="sxs-lookup"><span data-stu-id="d1e85-215">Int64</span></span>    |
|   <span data-ttu-id="d1e85-216">UInt64</span><span class="sxs-lookup"><span data-stu-id="d1e85-216">UInt64</span></span>   |   <span data-ttu-id="d1e85-217">Double</span><span class="sxs-lookup"><span data-stu-id="d1e85-217">Double</span></span>    |
|   <span data-ttu-id="d1e85-218">Double</span><span class="sxs-lookup"><span data-stu-id="d1e85-218">Double</span></span>   |   <span data-ttu-id="d1e85-219">Double</span><span class="sxs-lookup"><span data-stu-id="d1e85-219">Double</span></span>    |
|   <span data-ttu-id="d1e85-220">Single</span><span class="sxs-lookup"><span data-stu-id="d1e85-220">Single</span></span>   |   <span data-ttu-id="d1e85-221">Double</span><span class="sxs-lookup"><span data-stu-id="d1e85-221">Double</span></span>    |

<span data-ttu-id="d1e85-222">Ab Windows PowerShell 3,0 `Get-Random` unterstützt ganze Zahlen mit 64 Bit.</span><span class="sxs-lookup"><span data-stu-id="d1e85-222">Beginning in Windows PowerShell 3.0, `Get-Random` supports 64-bit integers.</span></span> <span data-ttu-id="d1e85-223">In Windows PowerShell 2,0 werden alle Werte in **System. Int32** umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="d1e85-223">In Windows PowerShell 2.0, all values are cast to **System.Int32**.</span></span>

<span data-ttu-id="d1e85-224">Ab PowerShell 7 akzeptiert der **Inputobject** -Parameter im **randomlistitemparameterset** -Parametersatz Arrays, die eine leere Zeichenfolge oder enthalten `$null` .</span><span class="sxs-lookup"><span data-stu-id="d1e85-224">Beginning in PowerShell 7, the **InputObject** parameter in the **RandomListItemParameterSet** parameter set accepts arrays that contain an empty string or `$null`.</span></span> <span data-ttu-id="d1e85-225">In früheren PowerShell-Versionen hat nur der Parameter " **Maximum** " im Parametersatz " **randomnumparameterset** " eine leere Zeichenfolge oder akzeptiert `$null` .</span><span class="sxs-lookup"><span data-stu-id="d1e85-225">In earlier PowerShell versions, only the **Maximum** parameter in the **RandomNumberParameterSet** parameter set accepted an empty string or `$null`.</span></span>

## <span data-ttu-id="d1e85-226">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d1e85-226">RELATED LINKS</span></span>

[<span data-ttu-id="d1e85-227">System. Security. Cryptography. randomnumgenerator ()</span><span class="sxs-lookup"><span data-stu-id="d1e85-227">System.Security.Cryptography.RandomNumberGenerator()</span></span>](/dotnet/api/system.security.cryptography.randomnumbergenerator)

[<span data-ttu-id="d1e85-228">"Sytem. Random"</span><span class="sxs-lookup"><span data-stu-id="d1e85-228">Sytem.Random</span></span>](/dotnet/api/system.random)
