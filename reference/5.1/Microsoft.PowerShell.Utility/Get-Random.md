---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 97576832ea851f01b463f63948fbd80028c9a6fb
ms.sourcegitcommit: fa1a84c81e15f1ffac962110b0b4c850c1b173a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "99495841"
---
# <span data-ttu-id="e3058-102">Get-Random</span><span class="sxs-lookup"><span data-stu-id="e3058-102">Get-Random</span></span>

## <span data-ttu-id="e3058-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e3058-103">SYNOPSIS</span></span>
<span data-ttu-id="e3058-104">Ruft eine Zufallszahl ab oder wählt Objekte nach dem Zufallsprinzip aus einer Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="e3058-104">Gets a random number, or selects objects randomly from a collection.</span></span>

## <span data-ttu-id="e3058-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e3058-105">SYNTAX</span></span>

### <span data-ttu-id="e3058-106">Randomnummeriparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="e3058-106">RandomNumberParameterSet (Default)</span></span>

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [<CommonParameters>]
```

### <span data-ttu-id="e3058-107">Randomlistitemparameterset</span><span class="sxs-lookup"><span data-stu-id="e3058-107">RandomListItemParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="e3058-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e3058-108">DESCRIPTION</span></span>

<span data-ttu-id="e3058-109">Mit dem- `Get-Random` Cmdlet wird eine zufällig ausgewählte Zahl abgerufen.</span><span class="sxs-lookup"><span data-stu-id="e3058-109">The `Get-Random` cmdlet gets a randomly selected number.</span></span> <span data-ttu-id="e3058-110">Wenn Sie eine Auflistung von-Objekten an senden `Get-Random` , ruft Sie mindestens ein zufällig ausgewähltes Objekt aus der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="e3058-110">If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.</span></span>

<span data-ttu-id="e3058-111">Ohne Parameter oder Eingaben gibt ein `Get-Random` Befehl eine zufällig ausgewählte 32-Bit-Ganzzahl ohne Vorzeichen zwischen 0 (null) und **Int32. MaxValue** ( `0x7FFFFFFF` , `2,147,483,647` ) zurück.</span><span class="sxs-lookup"><span data-stu-id="e3058-111">Without parameters or input, a `Get-Random` command returns a randomly selected 32-bit unsigned integer between 0 (zero) and **Int32.MaxValue** (`0x7FFFFFFF`, `2,147,483,647`).</span></span>

<span data-ttu-id="e3058-112">Standardmäßig `Get-Random` generiert kryptografisch sichere Zufälligkeit mithilfe der [randomnumgenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="e3058-112">By default, `Get-Random` generates cryptographically secure randomness using the [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) class.</span></span>

<span data-ttu-id="e3058-113">Sie können die Parameter von verwenden, `Get-Random` um die Mindest-und Höchstwerte, die Anzahl der von einer Auflistung zurückgegebenen Objekte oder eine Seed-Nummer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e3058-113">You can use the parameters of `Get-Random` to specify the minimum and maximum values, the number of objects returned from a collection, or a seed number.</span></span>

> [!CAUTION]
> <span data-ttu-id="e3058-114">Das Festlegen des Seed führt absichtlich zu einem nicht zufälligen, wiederholbaren Verhalten.</span><span class="sxs-lookup"><span data-stu-id="e3058-114">Setting the seed deliberately results in non-random, repeatable behavior.</span></span> <span data-ttu-id="e3058-115">Es sollte nur verwendet werden, wenn versucht wird, das Verhalten zu reproduzieren, z. b. beim Debuggen oder Analysieren eines Skripts, das `Get-Random` Befehle enthält</span><span class="sxs-lookup"><span data-stu-id="e3058-115">It should only be used when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>
>
> <span data-ttu-id="e3058-116">Dieser Ausgangswert wird für den aktuellen Befehl und für alle nachfolgenden `Get-Random` Befehle in der aktuellen Sitzung verwendet, bis Sie **setseed** erneut verwenden oder die Sitzung schließen.</span><span class="sxs-lookup"><span data-stu-id="e3058-116">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="e3058-117">Der Ausgangswert kann nicht auf seinen Standardwert zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="e3058-117">You can't reset the seed to its default value.</span></span>

## <span data-ttu-id="e3058-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e3058-118">EXAMPLES</span></span>

### <span data-ttu-id="e3058-119">Beispiel 1: erhalten einer zufälligen Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="e3058-119">Example 1: Get a random integer</span></span>

<span data-ttu-id="e3058-120">Dieser Befehl ruft eine zufällige Ganzzahl zwischen 0 (null) und **Int32. MaxValue** ab.</span><span class="sxs-lookup"><span data-stu-id="e3058-120">This command gets a random integer between 0 (zero) and **Int32.MaxValue**.</span></span>

```powershell
Get-Random
```

```Output
3951433
```

### <span data-ttu-id="e3058-121">Beispiel 2: erhalten einer zufälligen Ganzzahl zwischen 0 und 99</span><span class="sxs-lookup"><span data-stu-id="e3058-121">Example 2: Get a random integer between 0 and 99</span></span>

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### <span data-ttu-id="e3058-122">Beispiel 3: erhalten einer zufälligen Ganzzahl zwischen-100 und 99</span><span class="sxs-lookup"><span data-stu-id="e3058-122">Example 3: Get a random integer between -100 and 99</span></span>

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### <span data-ttu-id="e3058-123">Beispiel 4: erhalten einer zufälligen Gleit Komma Zahl</span><span class="sxs-lookup"><span data-stu-id="e3058-123">Example 4: Get a random floating-point number</span></span>

<span data-ttu-id="e3058-124">Dieser Befehl ruft eine zufällige Gleitkommazahl ab, die größer oder gleich 10.7 und kleiner als 20.92 ist.</span><span class="sxs-lookup"><span data-stu-id="e3058-124">This command gets a random floating-point number greater than or equal to 10.7 and less than 20.92.</span></span>

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### <span data-ttu-id="e3058-125">Beispiel 5: erhalten einer zufälligen Ganzzahl aus einem Array</span><span class="sxs-lookup"><span data-stu-id="e3058-125">Example 5: Get a random integer from an array</span></span>

<span data-ttu-id="e3058-126">Dieser Befehl ruft eine zufällig ausgewählte Zahl aus dem angegebenen Array ab.</span><span class="sxs-lookup"><span data-stu-id="e3058-126">This command gets a randomly selected number from the specified array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### <span data-ttu-id="e3058-127">Beispiel 6: erhalten mehrerer zufälliger ganzzahlige Zahlen aus einem Array</span><span class="sxs-lookup"><span data-stu-id="e3058-127">Example 6: Get several random integers from an array</span></span>

<span data-ttu-id="e3058-128">Dieser Befehl ruft drei zufällig ausgewählte Zahlen in zufälliger Reihenfolge aus einem Array ab.</span><span class="sxs-lookup"><span data-stu-id="e3058-128">This command gets three randomly selected numbers in random order from an array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### <span data-ttu-id="e3058-129">Beispiel 7: Randomisieren einer gesamten Sammlung</span><span class="sxs-lookup"><span data-stu-id="e3058-129">Example 7: Randomize an entire collection</span></span>

<span data-ttu-id="e3058-130">Dieser Befehl gibt die gesamte Auflistung in zufälliger Reihenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="e3058-130">This command returns the entire collection in random order.</span></span>

<span data-ttu-id="e3058-131">Der Wert des **count** -Parameters ist die statische **MaxValue** -Eigenschaft von Integern.</span><span class="sxs-lookup"><span data-stu-id="e3058-131">The value of the **Count** parameter is the **MaxValue** static property of integers.</span></span>

<span data-ttu-id="e3058-132">Um eine ganze Auflistung in zufälliger Reihenfolge zurückgegeben, geben Sie eine Zahl ein, die größer oder gleich der Anzahl der Objekte in der Auflistung ist.</span><span class="sxs-lookup"><span data-stu-id="e3058-132">To return an entire collection in random order, enter any number that is greater than or equal to the number of objects in the collection.</span></span>

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

### <span data-ttu-id="e3058-133">Beispiel 8: erhalten eines zufälligen nicht numerischen Werts</span><span class="sxs-lookup"><span data-stu-id="e3058-133">Example 8: Get a random non-numeric value</span></span>

<span data-ttu-id="e3058-134">Dieser Befehl gibt einen zufälligen Wert aus einer nicht numerischen Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="e3058-134">This command returns a random value from a non-numeric collection.</span></span>

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### <span data-ttu-id="e3058-135">Beispiel 9: Verwenden des setseed-Parameters</span><span class="sxs-lookup"><span data-stu-id="e3058-135">Example 9: Use the SetSeed parameter</span></span>

<span data-ttu-id="e3058-136">Dieses Beispiel zeigt die Auswirkungen der Verwendung des **SetSeed**-Parameters.</span><span class="sxs-lookup"><span data-stu-id="e3058-136">This example shows the effect of using the **SetSeed** parameter.</span></span>

<span data-ttu-id="e3058-137">Da **setseed** nicht zufälliges Verhalten erzeugt, wird es normalerweise nur zum Reproduzieren von Ergebnissen verwendet, z. b. beim Debuggen oder Analysieren eines Skripts.</span><span class="sxs-lookup"><span data-stu-id="e3058-137">Because **SetSeed** produces non-random behavior, it's typically used only to reproduce results, such as when debugging or analyzing a script.</span></span>

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

### <span data-ttu-id="e3058-138">Beispiel 10: Zufalls Dateien erhalten</span><span class="sxs-lookup"><span data-stu-id="e3058-138">Example 10: Get random files</span></span>

<span data-ttu-id="e3058-139">Mit diesen Befehlen wird eine zufällig ausgewählte Stichprobe von 50 Dateien vom `C:` Laufwerk des lokalen Computers erhalten.</span><span class="sxs-lookup"><span data-stu-id="e3058-139">These commands get a randomly selected sample of 50 files from the `C:` drive of the local computer.</span></span>

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### <span data-ttu-id="e3058-140">Beispiel 11: rollengerechte Würfel</span><span class="sxs-lookup"><span data-stu-id="e3058-140">Example 11: Roll fair dice</span></span>

<span data-ttu-id="e3058-141">In diesem Beispiel wird eine faire 1200-fache-Zeit ausgegeben, und die Ergebnisse werden gezählt.</span><span class="sxs-lookup"><span data-stu-id="e3058-141">This example rolls a fair die 1200 times and counts the outcomes.</span></span> <span data-ttu-id="e3058-142">Der erste Befehl `ForEach-Object` wiederholt den Aufrufen `Get-Random` von aus den weitergeleiteten Zahlen (1-6).</span><span class="sxs-lookup"><span data-stu-id="e3058-142">The first command, `ForEach-Object` repeats the call to `Get-Random` from the piped in numbers (1-6).</span></span> <span data-ttu-id="e3058-143">Die Ergebnisse werden nach ihrem Wert gruppiert `Group-Object` und als Tabelle mit formatiert `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="e3058-143">The results are grouped by their value with `Group-Object` and formatted as a table with `Select-Object`.</span></span>

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

## <span data-ttu-id="e3058-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e3058-144">PARAMETERS</span></span>

### <span data-ttu-id="e3058-145">-Anzahl</span><span class="sxs-lookup"><span data-stu-id="e3058-145">-Count</span></span>

<span data-ttu-id="e3058-146">Gibt die Anzahl von zufälligen Objekten oder Ziffern an, die zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e3058-146">Specifies the number of random objects or numbers to return.</span></span> <span data-ttu-id="e3058-147">Der Standardwert ist 1.</span><span class="sxs-lookup"><span data-stu-id="e3058-147">The default is 1.</span></span>

<span data-ttu-id="e3058-148">Bei Verwendung mit werden `InputObject`  `Get-Random` alle Objekte in zufälliger Reihenfolge zurückgegeben, wenn der Wert von count die Anzahl der Objekte in der Auflistung überschreitet.</span><span class="sxs-lookup"><span data-stu-id="e3058-148">When used with `InputObject`, if the value of **Count** exceeds the number of objects in the collection, `Get-Random` returns all of the objects in random order.</span></span>

```yaml
Type: System.Int32
Parameter Sets: RandomListItemParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3058-149">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e3058-149">-InputObject</span></span>

<span data-ttu-id="e3058-150">Gibt eine Auflistung von Objekten an.</span><span class="sxs-lookup"><span data-stu-id="e3058-150">Specifies a collection of objects.</span></span> <span data-ttu-id="e3058-151">`Get-Random` Ruft nach dem Zufallsprinzip ausgewählte Objekte in zufälliger Reihenfolge von der Auflistung bis zu der durch **count** angegebenen Zahl ab.</span><span class="sxs-lookup"><span data-stu-id="e3058-151">`Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count**.</span></span> <span data-ttu-id="e3058-152">Geben Sie die Objekte, eine Variable, die die Objekte enthält, oder einen Befehl oder Ausdruck ein, der die Objekte abruft.</span><span class="sxs-lookup"><span data-stu-id="e3058-152">Enter the objects, a variable that contains the objects, or a command or expression that gets the objects.</span></span> <span data-ttu-id="e3058-153">Sie können eine Auflistung von-Objekten auch über die Pipeline an senden `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="e3058-153">You can also pipe a collection of objects to `Get-Random`.</span></span>

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

### <span data-ttu-id="e3058-154">-Maximum</span><span class="sxs-lookup"><span data-stu-id="e3058-154">-Maximum</span></span>

<span data-ttu-id="e3058-155">Gibt einen maximalen Wert für die Zufallszahl an.</span><span class="sxs-lookup"><span data-stu-id="e3058-155">Specifies a maximum value for the random number.</span></span> <span data-ttu-id="e3058-156">`Get-Random` Gibt einen Wert zurück, der kleiner als der maximale Wert (nicht gleich) ist.</span><span class="sxs-lookup"><span data-stu-id="e3058-156">`Get-Random` returns a value that is less than the maximum (not equal).</span></span> <span data-ttu-id="e3058-157">Geben Sie eine ganze Zahl, eine Gleit Komma Zahl mit doppelter Genauigkeit oder ein Objekt ein, das in eine ganze Zahl oder einen Double-Wert konvertiert werden kann, z. b. eine numerische Zeichenfolge ("100").</span><span class="sxs-lookup"><span data-stu-id="e3058-157">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span>

<span data-ttu-id="e3058-158">Der Wert von **Maximum** muss größer sein als der Wert von **Minimum** (ungleich).</span><span class="sxs-lookup"><span data-stu-id="e3058-158">The value of **Maximum** must be greater than (not equal to) the value of **Minimum**.</span></span> <span data-ttu-id="e3058-159">Wenn der Wert von **Maximum** oder  Maximum eine Gleit Komma Zahl ist, wird `Get-Random` eine nach dem Zufallsprinzip ausgewählte Gleit Komma Zahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e3058-159">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

<span data-ttu-id="e3058-160">Auf einem 64-Bit-Computer ist der Standardwert von **Maximum** **Int32. MaxValue**, wenn der Wert von "Minimal" eine 32-Bit- **Ganzzahl** ist.</span><span class="sxs-lookup"><span data-stu-id="e3058-160">On a 64-bit computer, if the value of **Minimum** is a 32-bit integer, the default value of **Maximum** is **Int32.MaxValue**.</span></span>

<span data-ttu-id="e3058-161">Wenn der Wert von " **Minimal** " ein Double-Wert (eine Gleit Komma Zahl) ist, ist der Standardwert von " **Maximum** " **Double. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="e3058-161">If the value of **Minimum** is a double (a floating-point number), the default value of **Maximum** is **Double.MaxValue**.</span></span> <span data-ttu-id="e3058-162">Andernfalls ist der Standardwert **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="e3058-162">Otherwise, the default value is **Int32.MaxValue**.</span></span>

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

### <span data-ttu-id="e3058-163">-Minimal</span><span class="sxs-lookup"><span data-stu-id="e3058-163">-Minimum</span></span>

<span data-ttu-id="e3058-164">Gibt einen minimalen Wert für die Zufallszahl an.</span><span class="sxs-lookup"><span data-stu-id="e3058-164">Specifies a minimum value for the random number.</span></span> <span data-ttu-id="e3058-165">Geben Sie eine ganze Zahl, eine Gleit Komma Zahl mit doppelter Genauigkeit oder ein Objekt ein, das in eine ganze Zahl oder einen Double-Wert konvertiert werden kann, z. b. eine numerische Zeichenfolge ("100").</span><span class="sxs-lookup"><span data-stu-id="e3058-165">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span> <span data-ttu-id="e3058-166">Der Standardwert ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="e3058-166">The default value is 0 (zero).</span></span>

<span data-ttu-id="e3058-167">Der Wert von **Minimum** muss kleiner sein als der Wert von **Maximum** (ungleich).</span><span class="sxs-lookup"><span data-stu-id="e3058-167">The value of **Minimum** must be less than (not equal to) the value of **Maximum**.</span></span> <span data-ttu-id="e3058-168">Wenn der Wert von **Maximum** oder  Maximum eine Gleit Komma Zahl ist, wird `Get-Random` eine nach dem Zufallsprinzip ausgewählte Gleit Komma Zahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e3058-168">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

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

### <span data-ttu-id="e3058-169">-Setseed</span><span class="sxs-lookup"><span data-stu-id="e3058-169">-SetSeed</span></span>

<span data-ttu-id="e3058-170">Gibt einen Ausgangswert für den Zufallszahlengenerator an.</span><span class="sxs-lookup"><span data-stu-id="e3058-170">Specifies a seed value for the random number generator.</span></span> <span data-ttu-id="e3058-171">Wenn Sie **setseed** verwenden, verwendet das Cmdlet die [System. Random](/dotnet/api/system.random) -Methode, um Pseudo Zufalls-Nummern zu generieren, die nicht kryptografisch sicher sind.</span><span class="sxs-lookup"><span data-stu-id="e3058-171">When you use **SetSeed**, the cmdlet uses the [System.Random](/dotnet/api/system.random) method to generate pseudorandom numbers, which is not cryptographically secure.</span></span>

> [!CAUTION]
> <span data-ttu-id="e3058-172">Das Festlegen des Seed führt zu einem nicht zufälligen Verhalten.</span><span class="sxs-lookup"><span data-stu-id="e3058-172">Setting the seed results in non-random behavior.</span></span> <span data-ttu-id="e3058-173">Es sollte nur verwendet werden, wenn versucht wird, das Verhalten zu reproduzieren, z. b. beim Debuggen oder Analysieren eines Skripts, das `Get-Random` Befehle enthält</span><span class="sxs-lookup"><span data-stu-id="e3058-173">It should only be used when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>
>
> <span data-ttu-id="e3058-174">Dieser Ausgangswert wird für den aktuellen Befehl und für alle nachfolgenden `Get-Random` Befehle in der aktuellen Sitzung verwendet, bis Sie **setseed** erneut verwenden oder die Sitzung schließen.</span><span class="sxs-lookup"><span data-stu-id="e3058-174">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="e3058-175">Der Ausgangswert kann nicht auf seinen Standardwert zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="e3058-175">You can't reset the seed to its default value.</span></span>

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

### <span data-ttu-id="e3058-176">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e3058-176">CommonParameters</span></span>

<span data-ttu-id="e3058-177">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e3058-177">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e3058-178">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e3058-178">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e3058-179">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e3058-179">INPUTS</span></span>

### <span data-ttu-id="e3058-180">System.Object</span><span class="sxs-lookup"><span data-stu-id="e3058-180">System.Object</span></span>

<span data-ttu-id="e3058-181">Sie können ein oder mehrere-Objekte über die Pipeline übergeben.</span><span class="sxs-lookup"><span data-stu-id="e3058-181">You can pipe one or more objects.</span></span> <span data-ttu-id="e3058-182">`Get-Random` wählt Werte nach dem Zufallsprinzip aus den weitergeleiteten Objekten aus.</span><span class="sxs-lookup"><span data-stu-id="e3058-182">`Get-Random` selects values randomly from the piped objects.</span></span>

## <span data-ttu-id="e3058-183">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e3058-183">OUTPUTS</span></span>

### <span data-ttu-id="e3058-184">System. Int32, System. Int64, System. Double</span><span class="sxs-lookup"><span data-stu-id="e3058-184">System.Int32, System.Int64, System.Double</span></span>

<span data-ttu-id="e3058-185">`Get-Random` gibt eine ganze Zahl oder Gleit Komma Zahl oder ein Objekt, das nach dem Zufallsprinzip aus einer gesendeten Auflistung ausgewählt wird, zurück.</span><span class="sxs-lookup"><span data-stu-id="e3058-185">`Get-Random` returns an integer or floating-point number, or an object selected randomly from a submitted collection.</span></span>

## <span data-ttu-id="e3058-186">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e3058-186">NOTES</span></span>

<span data-ttu-id="e3058-187">Standardmäßig `Get-Random` generiert kryptografisch sichere Zufälligkeit mithilfe der [randomnumgenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="e3058-187">By default, `Get-Random` generates cryptographically secure randomness using the [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) class.</span></span>

<span data-ttu-id="e3058-188">`Get-Random` gibt nicht immer denselben Datentyp wie der Eingabe Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="e3058-188">`Get-Random` does not alway return the same data type as the input value.</span></span> <span data-ttu-id="e3058-189">In der folgenden Tabelle wird der Ausgabetyp für jeden der numerischen Eingabetypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3058-189">The following table shows the output type for each of the numeric input types.</span></span>

| <span data-ttu-id="e3058-190">Eingabetyp</span><span class="sxs-lookup"><span data-stu-id="e3058-190">Input Type</span></span> | <span data-ttu-id="e3058-191">Ausgabetyp</span><span class="sxs-lookup"><span data-stu-id="e3058-191">Output Type</span></span> |
| :--------: | :---------: |
|   <span data-ttu-id="e3058-192">SByte</span><span class="sxs-lookup"><span data-stu-id="e3058-192">SByte</span></span>    |   <span data-ttu-id="e3058-193">Double</span><span class="sxs-lookup"><span data-stu-id="e3058-193">Double</span></span>    |
|    <span data-ttu-id="e3058-194">Byte</span><span class="sxs-lookup"><span data-stu-id="e3058-194">Byte</span></span>    |   <span data-ttu-id="e3058-195">Double</span><span class="sxs-lookup"><span data-stu-id="e3058-195">Double</span></span>    |
|   <span data-ttu-id="e3058-196">Int16</span><span class="sxs-lookup"><span data-stu-id="e3058-196">Int16</span></span>    |   <span data-ttu-id="e3058-197">Double</span><span class="sxs-lookup"><span data-stu-id="e3058-197">Double</span></span>    |
|   <span data-ttu-id="e3058-198">UInt16</span><span class="sxs-lookup"><span data-stu-id="e3058-198">UInt16</span></span>   |   <span data-ttu-id="e3058-199">Double</span><span class="sxs-lookup"><span data-stu-id="e3058-199">Double</span></span>    |
|   <span data-ttu-id="e3058-200">Int32</span><span class="sxs-lookup"><span data-stu-id="e3058-200">Int32</span></span>    |    <span data-ttu-id="e3058-201">Int32</span><span class="sxs-lookup"><span data-stu-id="e3058-201">Int32</span></span>    |
|   <span data-ttu-id="e3058-202">UInt32</span><span class="sxs-lookup"><span data-stu-id="e3058-202">UInt32</span></span>   |   <span data-ttu-id="e3058-203">Double</span><span class="sxs-lookup"><span data-stu-id="e3058-203">Double</span></span>    |
|   <span data-ttu-id="e3058-204">Int64</span><span class="sxs-lookup"><span data-stu-id="e3058-204">Int64</span></span>    |    <span data-ttu-id="e3058-205">Int64</span><span class="sxs-lookup"><span data-stu-id="e3058-205">Int64</span></span>    |
|   <span data-ttu-id="e3058-206">UInt64</span><span class="sxs-lookup"><span data-stu-id="e3058-206">UInt64</span></span>   |   <span data-ttu-id="e3058-207">Double</span><span class="sxs-lookup"><span data-stu-id="e3058-207">Double</span></span>    |
|   <span data-ttu-id="e3058-208">Double</span><span class="sxs-lookup"><span data-stu-id="e3058-208">Double</span></span>   |   <span data-ttu-id="e3058-209">Double</span><span class="sxs-lookup"><span data-stu-id="e3058-209">Double</span></span>    |
|   <span data-ttu-id="e3058-210">Single</span><span class="sxs-lookup"><span data-stu-id="e3058-210">Single</span></span>   |   <span data-ttu-id="e3058-211">Double</span><span class="sxs-lookup"><span data-stu-id="e3058-211">Double</span></span>    |

<span data-ttu-id="e3058-212">Ab Windows PowerShell 3,0 `Get-Random` unterstützt ganze Zahlen mit 64 Bit.</span><span class="sxs-lookup"><span data-stu-id="e3058-212">Beginning in Windows PowerShell 3.0, `Get-Random` supports 64-bit integers.</span></span> <span data-ttu-id="e3058-213">In Windows PowerShell 2,0 werden alle Werte in **System. Int32** umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="e3058-213">In Windows PowerShell 2.0, all values are cast to **System.Int32**.</span></span>

## <span data-ttu-id="e3058-214">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e3058-214">RELATED LINKS</span></span>

[<span data-ttu-id="e3058-215">System. Security. Cryptography. randomnumgenerator ()</span><span class="sxs-lookup"><span data-stu-id="e3058-215">System.Security.Cryptography.RandomNumberGenerator()</span></span>](/dotnet/api/system.security.cryptography.randomnumbergenerator)

[<span data-ttu-id="e3058-216">"Sytem. Random"</span><span class="sxs-lookup"><span data-stu-id="e3058-216">Sytem.Random</span></span>](/dotnet/api/system.random)
