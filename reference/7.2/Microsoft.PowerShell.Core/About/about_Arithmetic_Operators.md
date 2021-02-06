---
description: Beschreibt die Operatoren, die Arithmetik in PowerShell ausführen.
Locale: en-US
ms.date: 10/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arithmetic_operators?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arithmetic_Operators
ms.openlocfilehash: 174b3cb72f6b5eb1cc39c4974613d9b9c8dd81a7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604864"
---
# <a name="about-arithmetic-operators"></a><span data-ttu-id="cbf00-103">Über arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="cbf00-103">About Arithmetic Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="cbf00-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cbf00-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="cbf00-105">Beschreibt die Operatoren, die Arithmetik in PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-105">Describes the operators that perform arithmetic in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="cbf00-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cbf00-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="cbf00-107">Arithmetische Operatoren berechnen numerische Werte.</span><span class="sxs-lookup"><span data-stu-id="cbf00-107">Arithmetic operators calculate numeric values.</span></span> <span data-ttu-id="cbf00-108">Sie können einen oder mehrere arithmetische Operatoren verwenden, um Werte hinzuzufügen, zu subtrahieren, zu multiplizieren und aufzuteilen und den Rest (Modulus) einer Divisions Operation zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-108">You can use one or more arithmetic operators to add, subtract, multiply, and divide values, and to calculate the remainder (modulus) of a division operation.</span></span>

<span data-ttu-id="cbf00-109">Außerdem arbeiten der Additions Operator ( `+` ) und der Multiplikations Operator ( `*` ) auch mit Zeichen folgen, Arrays und Hash Tabellen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-109">In addition, the addition operator (`+`) and multiplication operator (`*`) also operate on strings, arrays, and hash tables.</span></span> <span data-ttu-id="cbf00-110">Der Additions Operator verkettet die Eingabe.</span><span class="sxs-lookup"><span data-stu-id="cbf00-110">The addition operator concatenates the input.</span></span> <span data-ttu-id="cbf00-111">Der Multiplikations Operator gibt mehrere Kopien der Eingabe zurück.</span><span class="sxs-lookup"><span data-stu-id="cbf00-111">The multiplication operator returns multiple copies of the input.</span></span> <span data-ttu-id="cbf00-112">Objekttypen können sogar in einer arithmetischen Anweisung gemischt werden.</span><span class="sxs-lookup"><span data-stu-id="cbf00-112">You can even mix object types in an arithmetic statement.</span></span> <span data-ttu-id="cbf00-113">Die Methode, die zum Auswerten der Anweisung verwendet wird, wird durch den Typ des äußersten linken Objekts im Ausdruck bestimmt.</span><span class="sxs-lookup"><span data-stu-id="cbf00-113">The method that is used to evaluate the statement is determined by the type of the leftmost object in the expression.</span></span>

<span data-ttu-id="cbf00-114">Ab PowerShell 2,0 arbeiten alle arithmetischen Operatoren mit 64-Bit-Zahlen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-114">Beginning in PowerShell 2.0, all arithmetic operators work on 64-bit numbers.</span></span>

<span data-ttu-id="cbf00-115">Beginnend mit PowerShell 3,0 werden die `-shr` (Umschalt-Right) und `-shl` (shift-left) hinzugefügt, um bitweise Arithmetik in PowerShell zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-115">Beginning in PowerShell 3.0, the `-shr` (shift-right) and `-shl` (shift-left) are added to support bitwise arithmetic in PowerShell.</span></span>

<span data-ttu-id="cbf00-116">PowerShell unterstützt die folgenden arithmetischen Operatoren:</span><span class="sxs-lookup"><span data-stu-id="cbf00-116">PowerShell supports the following arithmetic operators:</span></span>

|<span data-ttu-id="cbf00-117">Operator</span><span class="sxs-lookup"><span data-stu-id="cbf00-117">Operator</span></span>|<span data-ttu-id="cbf00-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cbf00-118">Description</span></span>                       |<span data-ttu-id="cbf00-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cbf00-119">Example</span></span>                      |
|--------|----------------------------------|-----------------------------|
| +      |<span data-ttu-id="cbf00-120">Fügt ganze Zahlen hinzu. verkettet</span><span class="sxs-lookup"><span data-stu-id="cbf00-120">Adds integers; concatenates</span></span>       |`6 + 2`                      |
|        |<span data-ttu-id="cbf00-121">Zeichen folgen, Arrays und Hash Tabellen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-121">strings, arrays, and hash tables.</span></span> |`"file" + "name"`            |
|        |                                  |`@(1, "one") + @(2.0, "two")`|
|        |                                  |`@{"one" = 1} + @{"two" = 2}`|
| -      |<span data-ttu-id="cbf00-122">Subtrahiert einen Wert von einem anderen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-122">Subtracts one value from another</span></span>  |`6 - 2`                      |
|        |<span data-ttu-id="cbf00-123">value</span><span class="sxs-lookup"><span data-stu-id="cbf00-123">value</span></span>                             |                             |
| -      |<span data-ttu-id="cbf00-124">Gibt eine Zahl als negative Zahl an.</span><span class="sxs-lookup"><span data-stu-id="cbf00-124">Makes a number a negative number</span></span>  |`-6`                         |
|        |                                  |`(Get-Date).AddDays(-1)`     |
| *      |<span data-ttu-id="cbf00-125">Zahlen multiplizieren oder Zeichen folgen kopieren</span><span class="sxs-lookup"><span data-stu-id="cbf00-125">Multiply numbers or copy strings</span></span>  |`6 * 2`                      |
|        |<span data-ttu-id="cbf00-126">und Arrays die angegebene Zahl.</span><span class="sxs-lookup"><span data-stu-id="cbf00-126">and arrays the specified number</span></span>   |`@("!") * 4`                 |
|        |<span data-ttu-id="cbf00-127">von Zeiten.</span><span class="sxs-lookup"><span data-stu-id="cbf00-127">of times.</span></span>                         |`"!" * 3`                    |
| /      |<span data-ttu-id="cbf00-128">Dividiert zwei Werte.</span><span class="sxs-lookup"><span data-stu-id="cbf00-128">Divides two values.</span></span>               |`6 / 2`                      |
| %      |<span data-ttu-id="cbf00-129">Modulus-gibt den Rest von</span><span class="sxs-lookup"><span data-stu-id="cbf00-129">Modulus - returns the remainder of</span></span>|`7 % 2`                      |
|        |<span data-ttu-id="cbf00-130">ein Divisions Vorgang.</span><span class="sxs-lookup"><span data-stu-id="cbf00-130">a division operation.</span></span>             |                             |
|<span data-ttu-id="cbf00-131">-Band</span><span class="sxs-lookup"><span data-stu-id="cbf00-131">-band</span></span>   |<span data-ttu-id="cbf00-132">Bitweises AND</span><span class="sxs-lookup"><span data-stu-id="cbf00-132">Bitwise AND</span></span>                       |`5 -band 3`                  |
|<span data-ttu-id="cbf00-133">-bnot</span><span class="sxs-lookup"><span data-stu-id="cbf00-133">-bnot</span></span>   |<span data-ttu-id="cbf00-134">Bitweises NOT</span><span class="sxs-lookup"><span data-stu-id="cbf00-134">Bitwise NOT</span></span>                       |`-bnot 5`                    |
|<span data-ttu-id="cbf00-135">-Bor</span><span class="sxs-lookup"><span data-stu-id="cbf00-135">-bor</span></span>    |<span data-ttu-id="cbf00-136">Bitweises OR</span><span class="sxs-lookup"><span data-stu-id="cbf00-136">Bitwise OR</span></span>                        |`5 -bor 0x03`                |
|<span data-ttu-id="cbf00-137">-bxor</span><span class="sxs-lookup"><span data-stu-id="cbf00-137">-bxor</span></span>   |<span data-ttu-id="cbf00-138">Bitweises XOR</span><span class="sxs-lookup"><span data-stu-id="cbf00-138">Bitwise XOR</span></span>                       |`5 -bxor 3`                  |
|<span data-ttu-id="cbf00-139">-SHL</span><span class="sxs-lookup"><span data-stu-id="cbf00-139">-shl</span></span>    |<span data-ttu-id="cbf00-140">Verschiebt Bits nach links</span><span class="sxs-lookup"><span data-stu-id="cbf00-140">Shifts bits to the left</span></span>           |`102 -shl 2`                 |
|<span data-ttu-id="cbf00-141">-SHR</span><span class="sxs-lookup"><span data-stu-id="cbf00-141">-shr</span></span>    |<span data-ttu-id="cbf00-142">Verschiebt Bits nach rechts.</span><span class="sxs-lookup"><span data-stu-id="cbf00-142">Shifts bits to the right</span></span>          |`102 -shr 2`                 |

<span data-ttu-id="cbf00-143">Die bitweisen Operatoren können nur für ganzzahlige Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cbf00-143">The bitwise operators only work on integer types.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="cbf00-144">Operator Rangfolge</span><span class="sxs-lookup"><span data-stu-id="cbf00-144">OPERATOR PRECEDENCE</span></span>

<span data-ttu-id="cbf00-145">PowerShell verarbeitet arithmetische Operatoren in der folgenden Reihenfolge:</span><span class="sxs-lookup"><span data-stu-id="cbf00-145">PowerShell processes arithmetic operators in the following order:</span></span>

|<span data-ttu-id="cbf00-146">Rangfolge</span><span class="sxs-lookup"><span data-stu-id="cbf00-146">Precedence</span></span>|<span data-ttu-id="cbf00-147">Operator</span><span class="sxs-lookup"><span data-stu-id="cbf00-147">Operator</span></span>          |<span data-ttu-id="cbf00-148">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cbf00-148">Description</span></span>                            |
|----------|------------------|---------------------------------------|
|<span data-ttu-id="cbf00-149">1</span><span class="sxs-lookup"><span data-stu-id="cbf00-149">1</span></span>         | `()`             |<span data-ttu-id="cbf00-150">Klammern</span><span class="sxs-lookup"><span data-stu-id="cbf00-150">Parentheses</span></span>                            |
|<span data-ttu-id="cbf00-151">2</span><span class="sxs-lookup"><span data-stu-id="cbf00-151">2</span></span>         | `-`              |<span data-ttu-id="cbf00-152">Für eine negative Zahl oder einen unären Operator</span><span class="sxs-lookup"><span data-stu-id="cbf00-152">For a negative number or unary operator</span></span>|
|<span data-ttu-id="cbf00-153">3</span><span class="sxs-lookup"><span data-stu-id="cbf00-153">3</span></span>         | <span data-ttu-id="cbf00-154">`*`, `/`, `%`</span><span class="sxs-lookup"><span data-stu-id="cbf00-154">`*`, `/`, `%`</span></span>    |<span data-ttu-id="cbf00-155">Für Multiplikation und Division</span><span class="sxs-lookup"><span data-stu-id="cbf00-155">For multiplication and division</span></span>        |
|<span data-ttu-id="cbf00-156">4</span><span class="sxs-lookup"><span data-stu-id="cbf00-156">4</span></span>         | <span data-ttu-id="cbf00-157">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="cbf00-157">`+`, `-`</span></span>         |<span data-ttu-id="cbf00-158">Für Addition und Subtraktion</span><span class="sxs-lookup"><span data-stu-id="cbf00-158">For addition and subtraction</span></span>           |
|<span data-ttu-id="cbf00-159">5</span><span class="sxs-lookup"><span data-stu-id="cbf00-159">5</span></span>         | <span data-ttu-id="cbf00-160">`-band`, `-bnot`</span><span class="sxs-lookup"><span data-stu-id="cbf00-160">`-band`, `-bnot`</span></span> |<span data-ttu-id="cbf00-161">Für bitweise Operationen</span><span class="sxs-lookup"><span data-stu-id="cbf00-161">For bitwise operations</span></span>                 |
|<span data-ttu-id="cbf00-162">5</span><span class="sxs-lookup"><span data-stu-id="cbf00-162">5</span></span>         | <span data-ttu-id="cbf00-163">`-bor`, `-bxor`</span><span class="sxs-lookup"><span data-stu-id="cbf00-163">`-bor`, `-bxor`</span></span>  |<span data-ttu-id="cbf00-164">Für bitweise Operationen</span><span class="sxs-lookup"><span data-stu-id="cbf00-164">For bitwise operations</span></span>                 |
|<span data-ttu-id="cbf00-165">5</span><span class="sxs-lookup"><span data-stu-id="cbf00-165">5</span></span>         | <span data-ttu-id="cbf00-166">`-shr`, `-shl`</span><span class="sxs-lookup"><span data-stu-id="cbf00-166">`-shr`, `-shl`</span></span>   |<span data-ttu-id="cbf00-167">Für bitweise Operationen</span><span class="sxs-lookup"><span data-stu-id="cbf00-167">For bitwise operations</span></span>                 |

<span data-ttu-id="cbf00-168">PowerShell verarbeitet die Ausdrücke von links nach rechts gemäß den Rang Folge Regeln.</span><span class="sxs-lookup"><span data-stu-id="cbf00-168">PowerShell processes the expressions from left to right according to the precedence rules.</span></span> <span data-ttu-id="cbf00-169">Die folgenden Beispiele zeigen die Auswirkung der Rang folgen Regeln:</span><span class="sxs-lookup"><span data-stu-id="cbf00-169">The following examples show the effect of the precedence rules:</span></span>

|<span data-ttu-id="cbf00-170">expression</span><span class="sxs-lookup"><span data-stu-id="cbf00-170">Expression</span></span> |<span data-ttu-id="cbf00-171">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cbf00-171">Result</span></span>|
|-----------|------|
|`3+6/3*4`  |`11`  |
|`3+6/(3*4)`|`3.5` |
|`(3+6)/3*4`|`12`  |

<span data-ttu-id="cbf00-172">Die Reihenfolge, in der PowerShell Ausdrücke auswertet, kann sich von anderen Programmier-und Skriptsprachen unterscheiden, die Sie verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="cbf00-172">The order in which PowerShell evaluates expressions might differ from other programming and scripting languages that you have used.</span></span> <span data-ttu-id="cbf00-173">Im folgenden Beispiel wird eine komplizierte Zuweisungsanweisung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cbf00-173">The following example shows a complicated assignment statement.</span></span>

```powershell
$a = 0
$b = @(1,2)
$c = @(-1,-2)

$b[$a] = $c[$a++]
```

<span data-ttu-id="cbf00-174">In diesem Beispiel wird der Ausdruck `$a++` vor ausgewertet `$b[$a]` .</span><span class="sxs-lookup"><span data-stu-id="cbf00-174">In this example, the expression `$a++` is evaluated before `$b[$a]`.</span></span>
<span data-ttu-id="cbf00-175">Beim Auswerten `$a++` von wird der Wert von geändert `$a` , nachdem er in der-Anweisung verwendet `$c[$a++]` wurde, aber bevor er in verwendet wird `$b[$a]` .</span><span class="sxs-lookup"><span data-stu-id="cbf00-175">Evaluating `$a++` changes the value of `$a` after it is used in the statement `$c[$a++]`; but, before it is used in `$b[$a]`.</span></span> <span data-ttu-id="cbf00-176">Die- `$a` Variable `$b[$a]` in `1` ist, nicht `0` . Daher weist die-Anweisung einen Wert zu `$b[1]` , nicht zu `$b[0]` .</span><span class="sxs-lookup"><span data-stu-id="cbf00-176">The variable `$a` in `$b[$a]` equals `1`, not `0`; so, the statement assigns a value to `$b[1]`, not `$b[0]`.</span></span>

<span data-ttu-id="cbf00-177">Der obige Code entspricht:</span><span class="sxs-lookup"><span data-stu-id="cbf00-177">The above code is equivalent to:</span></span>

```powershell
$a = 0
$b = @(1,2)
$c = @(-1,-2)

$tmp = $c[$a]
$a = $a + 1
$b[$a] = $tmp
```

## <a name="division-and-rounding"></a><span data-ttu-id="cbf00-178">Division und Rundung</span><span class="sxs-lookup"><span data-stu-id="cbf00-178">DIVISION AND ROUNDING</span></span>

<span data-ttu-id="cbf00-179">Wenn der Quotienten einer Divisions Operation eine ganze Zahl ist, rundet PowerShell den Wert auf die nächste ganze Zahl auf.</span><span class="sxs-lookup"><span data-stu-id="cbf00-179">When the quotient of a division operation is an integer, PowerShell rounds the value to the nearest integer.</span></span> <span data-ttu-id="cbf00-180">Wenn der Wert ist `.5` , wird der Wert auf die nächste gerade ganze Zahl gerundet.</span><span class="sxs-lookup"><span data-stu-id="cbf00-180">When the value is `.5`, it rounds to the nearest even integer.</span></span>

<span data-ttu-id="cbf00-181">Das folgende Beispiel zeigt die Auswirkung der Rundung auf die nächste gerade ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="cbf00-181">The following example shows the effect of rounding to the nearest even integer.</span></span>

|<span data-ttu-id="cbf00-182">expression</span><span class="sxs-lookup"><span data-stu-id="cbf00-182">Expression</span></span>      |<span data-ttu-id="cbf00-183">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cbf00-183">Result</span></span>|
|----------------|------|
|`[int]( 5 / 2 )`|`2`   |
|`[int]( 7 / 2 )`|`4`   |

<span data-ttu-id="cbf00-184">Beachten Sie, dass **_5/2_ = 2,5** auf **2** gerundet wird.</span><span class="sxs-lookup"><span data-stu-id="cbf00-184">Notice how **_5/2_ = 2.5** gets rounded to **2**.</span></span> <span data-ttu-id="cbf00-185">**_7/2_ = 3,5** wird jedoch auf **4** gerundet.</span><span class="sxs-lookup"><span data-stu-id="cbf00-185">But, **_7/2_ = 3.5** gets rounded to **4**.</span></span>

<span data-ttu-id="cbf00-186">Sie können die- `[Math]` Klasse verwenden, um ein anderes Rundungs Verhalten zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-186">You can use the `[Math]` class to get different rounding behavior.</span></span>

|                          <span data-ttu-id="cbf00-187">expression</span><span class="sxs-lookup"><span data-stu-id="cbf00-187">Expression</span></span>                          | <span data-ttu-id="cbf00-188">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cbf00-188">Result</span></span> |
| ------------------------------------------------------------ | ------ |
| `[int][Math]::Round(5 / 2,[MidpointRounding]::AwayFromZero)` | `3`    |
| `[int][Math]::Ceiling(5 / 2)`                                | `3`    |
| `[int][Math]::Floor(5 / 2)`                                  | `2`    |

<span data-ttu-id="cbf00-189">Weitere Informationen finden Sie unter der [Math. Round](/dotnet/api/system.math.round) -Methode.</span><span class="sxs-lookup"><span data-stu-id="cbf00-189">For more information, see the [Math.Round](/dotnet/api/system.math.round) method.</span></span>

## <a name="adding-and-multiplying-non-numeric-types"></a><span data-ttu-id="cbf00-190">Hinzufügen und Multiplizieren von nicht numerischen Typen</span><span class="sxs-lookup"><span data-stu-id="cbf00-190">ADDING AND MULTIPLYING NON-NUMERIC TYPES</span></span>

<span data-ttu-id="cbf00-191">Sie können Zahlen, Zeichen folgen, Arrays und Hash Tabellen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-191">You can add numbers, strings, arrays, and hash tables.</span></span> <span data-ttu-id="cbf00-192">Und Sie können Zahlen, Zeichen folgen und Arrays multiplizieren.</span><span class="sxs-lookup"><span data-stu-id="cbf00-192">And, you can multiply numbers, strings, and arrays.</span></span> <span data-ttu-id="cbf00-193">Hash Tabellen können jedoch nicht multipliziert werden.</span><span class="sxs-lookup"><span data-stu-id="cbf00-193">However, you cannot multiply hash tables.</span></span>

<span data-ttu-id="cbf00-194">Wenn Sie Zeichen folgen, Arrays oder Hash Tabellen hinzufügen, werden die Elemente verkettet.</span><span class="sxs-lookup"><span data-stu-id="cbf00-194">When you add strings, arrays, or hash tables, the elements are concatenated.</span></span> <span data-ttu-id="cbf00-195">Wenn Sie Auflistungen (z. b. Arrays oder Hash Tabellen) verketten, wird ein neues-Objekt erstellt, das die Objekte aus beiden Auflistungen enthält.</span><span class="sxs-lookup"><span data-stu-id="cbf00-195">When you concatenate collections, such as arrays or hash tables, a new object is created that contains the objects from both collections.</span></span> <span data-ttu-id="cbf00-196">Wenn Sie versuchen, Hash Tabellen mit demselben Schlüssel zu verketten, schlägt der Vorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="cbf00-196">If you try to concatenate hash tables that have the same key, the operation fails.</span></span>

<span data-ttu-id="cbf00-197">Beispielsweise werden mit den folgenden Befehlen zwei Arrays erstellt und dann hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="cbf00-197">For example, the following commands create two arrays and then add them:</span></span>

```powershell
$a = 1,2,3
$b = "A","B","C"
$a + $b
```

```output
1
2
3
A
B
C
```

<span data-ttu-id="cbf00-198">Sie können auch arithmetische Operationen für Objekte unterschiedlicher Typen durchführen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-198">You can also perform arithmetic operations on objects of different types.</span></span>
<span data-ttu-id="cbf00-199">Der von PowerShell ausgeführten Vorgang wird durch den Microsoft .net Frameworktyp des äußersten linken Objekts im Vorgang bestimmt.</span><span class="sxs-lookup"><span data-stu-id="cbf00-199">The operation that PowerShell performs is determined by the Microsoft .NET Framework type of the leftmost object in the operation.</span></span> <span data-ttu-id="cbf00-200">PowerShell versucht, alle Objekte im Vorgang in den .NET Framework Typ des ersten Objekts zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="cbf00-200">PowerShell tries to convert all the objects in the operation to the .NET Framework type of the first object.</span></span> <span data-ttu-id="cbf00-201">Wenn die Objekte erfolgreich umgerechnet werden, wird der entsprechende Vorgang für den .NET Framework Typ des ersten Objekts ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cbf00-201">If it succeeds in converting the objects, it performs the operation appropriate to the .NET Framework type of the first object.</span></span> <span data-ttu-id="cbf00-202">Wenn ein Objekt nicht konvertiert werden kann, schlägt der Vorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="cbf00-202">If it fails to convert any of the objects, the operation fails.</span></span>

<span data-ttu-id="cbf00-203">In den folgenden Beispielen wird die Verwendung der Additions-und Multiplikations Operatoren veranschaulicht. in Vorgängen, die unterschiedliche Objekttypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="cbf00-203">The following examples demonstrate the use of the addition and multiplication operators; in operations that include different object types.</span></span> <span data-ttu-id="cbf00-204">Angenommen `$array = 1,2,3` :</span><span class="sxs-lookup"><span data-stu-id="cbf00-204">Assume `$array = 1,2,3`:</span></span>

|<span data-ttu-id="cbf00-205">expression</span><span class="sxs-lookup"><span data-stu-id="cbf00-205">Expression</span></span>       |<span data-ttu-id="cbf00-206">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cbf00-206">Result</span></span>                 |
|-----------------|-----------------------|
|`"file" + 16`    |`file16`               |
|`$array + 16`    |<span data-ttu-id="cbf00-207">`1`,`2`,`3`,`16`</span><span class="sxs-lookup"><span data-stu-id="cbf00-207">`1`,`2`,`3`,`16`</span></span>       |
|`$array + "file"`|<span data-ttu-id="cbf00-208">`1`,`2`,`3`,`file`</span><span class="sxs-lookup"><span data-stu-id="cbf00-208">`1`,`2`,`3`,`file`</span></span>     |
|`$array * 2`     |<span data-ttu-id="cbf00-209">`1`,`2`,`3`,`1`,`2`,`3`</span><span class="sxs-lookup"><span data-stu-id="cbf00-209">`1`,`2`,`3`,`1`,`2`,`3`</span></span>|
|`"file" * 3`     |`filefilefile`         |

<span data-ttu-id="cbf00-210">Da die Methode, die zum Auswerten von-Anweisungen verwendet wird, durch das äußteste-Objekt bestimmt wird, sind Addition und Multiplikation in PowerShell nicht streng kommutativ.</span><span class="sxs-lookup"><span data-stu-id="cbf00-210">Because the method that is used to evaluate statements is determined by the leftmost object, addition and multiplication in PowerShell are not strictly commutative.</span></span> <span data-ttu-id="cbf00-211">Beispielsweise ist `(a + b)` nicht immer gleich `(b + a)` , und `(ab)` ist nicht immer gleich `(ba)` .</span><span class="sxs-lookup"><span data-stu-id="cbf00-211">For example, `(a + b)` does not always equal `(b + a)`, and `(ab)` does not always equal `(ba)`.</span></span>

<span data-ttu-id="cbf00-212">Die folgenden Beispiele veranschaulichen dieses Prinzip:</span><span class="sxs-lookup"><span data-stu-id="cbf00-212">The following examples demonstrate this principle:</span></span>

|<span data-ttu-id="cbf00-213">expression</span><span class="sxs-lookup"><span data-stu-id="cbf00-213">Expression</span></span>   |<span data-ttu-id="cbf00-214">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cbf00-214">Result</span></span>                                               |
|-------------|-----------------------------------------------------|
|`"file" + 16`|`file16`                                             |
|`16 + "file"`|`Cannot convert value "file" to type "System.Int32".`|
|             |`Error: "Input string was not in a correct format."` |
|             |`At line:1 char:1`                                   |
|             |<span data-ttu-id="cbf00-215">+ 16 + "Datei" "</span><span class="sxs-lookup"><span data-stu-id="cbf00-215">+ 16 + "file"\`</span></span>                                       |

<span data-ttu-id="cbf00-216">Bei Hash Tabellen handelt es sich um einen etwas anderen Fall.</span><span class="sxs-lookup"><span data-stu-id="cbf00-216">Hash tables are a slightly different case.</span></span> <span data-ttu-id="cbf00-217">Sie können Hash Tabellen einer anderen Hash Tabelle hinzufügen, solange die hinzugefügten Hash Tabellen nicht über doppelte Schlüssel verfügen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-217">You can add hash tables to another hash table, as long as, the added hash tables don't have duplicate keys.</span></span>

<span data-ttu-id="cbf00-218">Im folgenden Beispiel wird gezeigt, wie Hash Tabellen einander hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cbf00-218">The following example show how to add hash tables to each other.</span></span>

```powershell
$hash1 = @{a=1; b=2; c=3}
$hash2 = @{c1="Server01"; c2="Server02"}
$hash1 + $hash2
```

```output
Name                           Value
----                           -----
c2                             Server02
a                              1
b                              2
c1                             Server01
c                              3
```

<span data-ttu-id="cbf00-219">Im folgenden Beispiel wird ein Fehler ausgelöst, da einer der Schlüssel in beiden Hash Tabellen dupliziert wird.</span><span class="sxs-lookup"><span data-stu-id="cbf00-219">The following example throws an error because one of the keys is duplicated in both hash tables.</span></span>

```powershell
$hash1 = @{a=1; b=2; c=3}
$hash2 = @{c1="Server01"; c="Server02"}
$hash1 + $hash2
```

```output
Item has already been added. Key in dictionary: 'c'  Key being added: 'c'
At line:3 char:1
+ $hash1 + $hash2
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (:) [], ArgumentException
    + FullyQualifiedErrorId : System.ArgumentException
```

<span data-ttu-id="cbf00-220">Außerdem können Sie einem Array eine Hash Tabelle hinzufügen. Außerdem wird die gesamte Hash Tabelle zu einem Element im Array.</span><span class="sxs-lookup"><span data-stu-id="cbf00-220">Also, you can add a hash table to an array; and, the entire hash table becomes an item in the array.</span></span>

```powershell
$array1 = @(0, "Hello World", [datetime]::Now)
$hash1 = @{a=1; b=2}
$array2 = $array1 + $hash1
$array2
```

```output
0
Hello World

Monday, June 12, 2017 3:05:46 PM

Key   : a
Value : 1
Name  : a

Key   : b
Value : 2
Name  : b
```

<span data-ttu-id="cbf00-221">Es ist jedoch nicht möglich, einer Hash Tabelle einen anderen Typ hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-221">However, you cannot add any other type to a hash table.</span></span>

```powershell
$hash1 + 2
```

```output
A hash table can only be added to another hash table.
At line:3 char:1
+ $hash1 + 2
```

<span data-ttu-id="cbf00-222">Obwohl die Additions Operatoren sehr nützlich sind, verwenden Sie die Zuweisungs Operatoren zum Hinzufügen von Elementen zu Hash Tabellen und Arrays.</span><span class="sxs-lookup"><span data-stu-id="cbf00-222">Although the addition operators are very useful, use the assignment operators to add elements to hash tables and arrays.</span></span> <span data-ttu-id="cbf00-223">Weitere Informationen finden Sie unter [about_assignment_operators](about_Assignment_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="cbf00-223">For more information see [about_assignment_operators](about_Assignment_Operators.md).</span></span> <span data-ttu-id="cbf00-224">In den folgenden Beispielen wird der `+=` Zuweisungs Operator zum Hinzufügen von Elementen zu einem Array verwendet:</span><span class="sxs-lookup"><span data-stu-id="cbf00-224">The following examples use the `+=` assignment operator to add items to an array:</span></span>

```powershell
$array = @()
(0..9).foreach{ $array += $_ }
$array
```

```output
0
1
2
```

## <a name="type-conversion-to-accommodate-result"></a><span data-ttu-id="cbf00-225">Typkonvertierung, um das Ergebnis zu erfüllen</span><span class="sxs-lookup"><span data-stu-id="cbf00-225">TYPE CONVERSION TO ACCOMMODATE RESULT</span></span>

<span data-ttu-id="cbf00-226">PowerShell wählt automatisch den .NET Framework numerischen Typ aus, der das Ergebnis am besten ausdrückt, ohne die Genauigkeit zu verlieren.</span><span class="sxs-lookup"><span data-stu-id="cbf00-226">PowerShell automatically selects the .NET Framework numeric type that best expresses the result without losing precision.</span></span> <span data-ttu-id="cbf00-227">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cbf00-227">For example:</span></span>

```powershell
2 + 3.1

(2). GetType().FullName
(2 + 3.1).GetType().FullName
```

```output
5.1
System.Int32
System.Double
```

<span data-ttu-id="cbf00-228">Wenn das Ergebnis eines Vorgangs für den Typ zu groß ist, wird der Ergebnistyp um das Ergebnis erweitert, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="cbf00-228">If the result of an operation is too large for the type, the type of the result is widened to accommodate the result, as in the following example:</span></span>

```powershell
(512MB).GetType().FullName
(512MB * 512MB).GetType().FullName
```

```output
System.Int32
System.Double
```

<span data-ttu-id="cbf00-229">Der Ergebnistyp ist nicht notwendigerweise identisch mit einem der Operanden.</span><span class="sxs-lookup"><span data-stu-id="cbf00-229">The type of the result will not necessarily be the same as one of the operands.</span></span> <span data-ttu-id="cbf00-230">Im folgenden Beispiel kann der negative Wert nicht in eine ganze Zahl ohne Vorzeichen umgewandelt werden, und die Ganzzahl ohne Vorzeichen ist zu groß, um in umgewandelt zu werden `Int32` :</span><span class="sxs-lookup"><span data-stu-id="cbf00-230">In the following example, the negative value cannot be cast to an unsigned integer, and the unsigned integer is too large to be cast to `Int32`:</span></span>

```powershell
([int32]::minvalue + [uint32]::maxvalue).gettype().fullname
```

```output
System.Int64
```

<span data-ttu-id="cbf00-231">In diesem Beispiel `Int64` kann beide Typen aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-231">In this example, `Int64` can accommodate both types.</span></span>

<span data-ttu-id="cbf00-232">Der `System.Decimal` Typ ist eine Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="cbf00-232">The `System.Decimal` type is an exception.</span></span> <span data-ttu-id="cbf00-233">Wenn einer der beiden Operanden den Decimal-Typ aufweist, ist das Ergebnis vom Decimal-Typ.</span><span class="sxs-lookup"><span data-stu-id="cbf00-233">If either operand has the Decimal type, the result will be of the Decimal type.</span></span> <span data-ttu-id="cbf00-234">Wenn das Ergebnis für den Decimal-Typ zu groß ist, wird es nicht in double umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="cbf00-234">If the result is too large for the Decimal type, it will not be cast to Double.</span></span> <span data-ttu-id="cbf00-235">Stattdessen wird ein Fehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="cbf00-235">Instead, an error results.</span></span>

|<span data-ttu-id="cbf00-236">expression</span><span class="sxs-lookup"><span data-stu-id="cbf00-236">Expression</span></span>               |<span data-ttu-id="cbf00-237">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cbf00-237">Result</span></span>                                         |
|-------------------------|-----------------------------------------------|
|`[Decimal]::maxvalue`    |`79228162514264337593543950335`                |
|`[Decimal]::maxvalue + 1`|`Value was either too large or too small for a`|
|                         |`Decimal.`                                     |

## <a name="arithmetic-operators-and-variables"></a><span data-ttu-id="cbf00-238">arithmetische Operatoren und Variablen</span><span class="sxs-lookup"><span data-stu-id="cbf00-238">ARITHMETIC OPERATORS AND VARIABLES</span></span>

<span data-ttu-id="cbf00-239">Sie können auch arithmetische Operatoren mit Variablen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cbf00-239">You can also use arithmetic operators with variables.</span></span> <span data-ttu-id="cbf00-240">Die Operatoren wirken sich auf die Werte der Variablen aus.</span><span class="sxs-lookup"><span data-stu-id="cbf00-240">The operators act on the values of the variables.</span></span> <span data-ttu-id="cbf00-241">Die folgenden Beispiele veranschaulichen die Verwendung arithmetischer Operatoren mit Variablen:</span><span class="sxs-lookup"><span data-stu-id="cbf00-241">The following examples demonstrate the use of arithmetic operators with variables:</span></span>

| <span data-ttu-id="cbf00-242">expression</span><span class="sxs-lookup"><span data-stu-id="cbf00-242">Expression</span></span>                                    |<span data-ttu-id="cbf00-243">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cbf00-243">Result</span></span>      |
|-----------------------------------------------|------------|
|`$intA = 6`<br/>`$intB = 4`<br/>`$intA + $intB`|`10`        |
|`$a = "Power"`<br/>`$b = "Shell"`<br/>`$a + $b`|`PowerShell`|

## <a name="arithmetic-operators-and-commands"></a><span data-ttu-id="cbf00-244">arithmetische Operatoren und Befehle</span><span class="sxs-lookup"><span data-stu-id="cbf00-244">ARITHMETIC OPERATORS AND COMMANDS</span></span>

<span data-ttu-id="cbf00-245">In der Regel verwenden Sie die arithmetischen Operatoren in Ausdrücken mit Zahlen, Zeichen folgen und Arrays.</span><span class="sxs-lookup"><span data-stu-id="cbf00-245">Typically, you use the arithmetic operators in expressions with numbers, strings, and arrays.</span></span> <span data-ttu-id="cbf00-246">Sie können jedoch auch arithmetische Operatoren mit den Objekten verwenden, die von Befehlen zurückgegeben werden, sowie mit den Eigenschaften dieser Objekte.</span><span class="sxs-lookup"><span data-stu-id="cbf00-246">However, you can also use arithmetic operators with the objects that commands return and with the properties of those objects.</span></span>

<span data-ttu-id="cbf00-247">In den folgenden Beispielen wird gezeigt, wie die arithmetischen Operatoren in Ausdrücken mit PowerShell-Befehlen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="cbf00-247">The following examples show how to use the arithmetic operators in expressions with PowerShell commands:</span></span>

```powershell
(get-date) + (new-timespan -day 1)
```

<span data-ttu-id="cbf00-248">Der Klammer Operator erzwingt die Auswertung des `get-date` Cmdlets und die Auswertung des `new-timespan -day 1` Cmdlet-Ausdrucks in dieser Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="cbf00-248">The parenthesis operator forces the evaluation of the `get-date` cmdlet and the evaluation of the `new-timespan -day 1` cmdlet expression, in that order.</span></span> <span data-ttu-id="cbf00-249">Beide Ergebnisse werden dann mit dem- `+` Operator hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cbf00-249">Both results are then added using the `+` operator.</span></span>

```powershell
Get-Process | Where-Object { ($_.ws * 2) -gt 50mb }
```

```output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
   1896      39    50968      30620   264 1,572.55   1104 explorer
  12802      78   188468      81032   753 3,676.39   5676 OUTLOOK
    660       9    36168      26956   143    12.20    988 PowerShell
    561      14     6592      28144   110 1,010.09    496 services
   3476      80    34664      26092   234 ...45.69    876 svchost
    967      30    58804      59496   416   930.97   2508 WINWORD
```

<span data-ttu-id="cbf00-250">Im obigen Ausdruck wird jeder Prozess Arbeitsbereich ( `$_.ws` ) mit multipliziert, `2` und das Ergebnis wird mit verglichen, `50mb` um festzustellen, ob es größer als das ist.</span><span class="sxs-lookup"><span data-stu-id="cbf00-250">In the above expression, each process working space (`$_.ws`) is multiplied by `2`; and, the result, compared against `50mb` to see if it is greater than that.</span></span>

## <a name="bitwise-operators"></a><span data-ttu-id="cbf00-251">Bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="cbf00-251">Bitwise Operators</span></span>

<span data-ttu-id="cbf00-252">PowerShell unterstützt die standardmäßigen bitweisen Operatoren, einschließlich bitweiser and ( `-bAnd` ), der inklusiven und exklusiven bitweisen OR-Operatoren ( `-bOr` and `-bXor` ) und bitweises NOT ( `-bNot` ).</span><span class="sxs-lookup"><span data-stu-id="cbf00-252">PowerShell supports the standard bitwise operators, including bitwise-AND (`-bAnd`), the inclusive and exclusive bitwise-OR operators (`-bOr` and `-bXor`), and bitwise-NOT (`-bNot`).</span></span>

<span data-ttu-id="cbf00-253">Beginnend mit PowerShell 2,0 arbeiten alle bitweisen Operatoren mit 64-Bit-Ganzzahlen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-253">Beginning in PowerShell 2.0, all bitwise operators work with 64-bit integers.</span></span>

<span data-ttu-id="cbf00-254">Beginnend mit PowerShell 3,0 werden die `-shr` (Umschalt-Right) und `-shl` (shift-left) eingeführt, um bitweise Arithmetik in PowerShell zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-254">Beginning in PowerShell 3.0, the `-shr` (shift-right) and `-shl` (shift-left) are introduced to support bitwise arithmetic in PowerShell.</span></span>

<span data-ttu-id="cbf00-255">PowerShell unterstützt die folgenden bitweisen Operatoren.</span><span class="sxs-lookup"><span data-stu-id="cbf00-255">PowerShell supports the following bitwise operators.</span></span>

| <span data-ttu-id="cbf00-256">Operator</span><span class="sxs-lookup"><span data-stu-id="cbf00-256">Operator</span></span> | <span data-ttu-id="cbf00-257">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cbf00-257">Description</span></span>            | <span data-ttu-id="cbf00-258">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="cbf00-258">Expression</span></span>   | <span data-ttu-id="cbf00-259">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cbf00-259">Result</span></span> |
| -------- | ---------------------- | ------------ | ------ |
| `-band`  | <span data-ttu-id="cbf00-260">Bitweises AND</span><span class="sxs-lookup"><span data-stu-id="cbf00-260">Bitwise AND</span></span>            | `10 -band 3` | <span data-ttu-id="cbf00-261">2</span><span class="sxs-lookup"><span data-stu-id="cbf00-261">2</span></span>      |
| `-bor`   | <span data-ttu-id="cbf00-262">Bitweises OR (inklusiv)</span><span class="sxs-lookup"><span data-stu-id="cbf00-262">Bitwise OR (inclusive)</span></span> | `10 -bor 3`  | <span data-ttu-id="cbf00-263">11</span><span class="sxs-lookup"><span data-stu-id="cbf00-263">11</span></span>     |
| `-bxor`  | <span data-ttu-id="cbf00-264">Bitweises OR (exklusiv)</span><span class="sxs-lookup"><span data-stu-id="cbf00-264">Bitwise OR (exclusive)</span></span> | `10 -bxor 3` | <span data-ttu-id="cbf00-265">9</span><span class="sxs-lookup"><span data-stu-id="cbf00-265">9</span></span>      |
| `-bnot`  | <span data-ttu-id="cbf00-266">Bitweises NOT</span><span class="sxs-lookup"><span data-stu-id="cbf00-266">Bitwise NOT</span></span>            | `-bNot 10`   | <span data-ttu-id="cbf00-267">-11</span><span class="sxs-lookup"><span data-stu-id="cbf00-267">-11</span></span>    |
| `-shl`   | <span data-ttu-id="cbf00-268">UMSCHALT nach links</span><span class="sxs-lookup"><span data-stu-id="cbf00-268">Shift-left</span></span>             | `102 -shl 2` | <span data-ttu-id="cbf00-269">408</span><span class="sxs-lookup"><span data-stu-id="cbf00-269">408</span></span>    |
| `-shr`   | <span data-ttu-id="cbf00-270">Shift-right</span><span class="sxs-lookup"><span data-stu-id="cbf00-270">Shift-right</span></span>            | `102 -shr 1` | <span data-ttu-id="cbf00-271">51</span><span class="sxs-lookup"><span data-stu-id="cbf00-271">51</span></span>     |

<span data-ttu-id="cbf00-272">Bitweise Operatoren agieren auf das binäre Format eines-Werts.</span><span class="sxs-lookup"><span data-stu-id="cbf00-272">Bitwise operators act on the binary format of a value.</span></span> <span data-ttu-id="cbf00-273">Beispielsweise ist die bitstruktur für die Zahl 10 00001010 (basierend auf 1 Byte), und die bitstruktur für die Zahl 3 ist 00000011.</span><span class="sxs-lookup"><span data-stu-id="cbf00-273">For example, the bit structure for the number 10 is 00001010 (based on 1 byte), and the bit structure for the number 3 is 00000011.</span></span> <span data-ttu-id="cbf00-274">Wenn Sie einen bitweisen Operator zum Vergleichen von 10 mit 3 verwenden, werden die einzelnen Bits in jedem Byte verglichen.</span><span class="sxs-lookup"><span data-stu-id="cbf00-274">When you use a bitwise operator to compare 10 to 3, the individual bits in each byte are compared.</span></span>

<span data-ttu-id="cbf00-275">In einer bitweisen and-Operation wird das resultierende Bit nur dann auf 1 festgelegt, wenn beide Eingabe Bits 1 sind.</span><span class="sxs-lookup"><span data-stu-id="cbf00-275">In a bitwise AND operation, the resulting bit is set to 1 only when both input bits are 1.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bAND
0010      ( 2)
```

<span data-ttu-id="cbf00-276">Bei einem bitweisen OR-Vorgang (inklusiv) wird das resultierende Bit auf 1 festgelegt, wenn entweder oder beide Eingabe Bits 1 sind.</span><span class="sxs-lookup"><span data-stu-id="cbf00-276">In a bitwise OR (inclusive) operation, the resulting bit is set to 1 when either or both input bits are 1.</span></span> <span data-ttu-id="cbf00-277">Das resultierende Bit wird nur dann auf 0 festgelegt, wenn beide Eingabe Bits auf 0 festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="cbf00-277">The resulting bit is set to 0 only when both input bits are set to 0.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bOR (inclusive)
1011      (11)
```

<span data-ttu-id="cbf00-278">Bei einem bitweisen OR-Vorgang (exklusiv) wird das resultierende Bit nur dann auf 1 festgelegt, wenn ein Eingabe Bit 1 ist.</span><span class="sxs-lookup"><span data-stu-id="cbf00-278">In a bitwise OR (exclusive) operation, the resulting bit is set to 1 only when one input bit is 1.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bXOR (exclusive)
1001      ( 9)
```

<span data-ttu-id="cbf00-279">Der bitweise NOT-Operator ist ein unärer Operator, der das binäre Komplement des Werts erzeugt.</span><span class="sxs-lookup"><span data-stu-id="cbf00-279">The bitwise NOT operator is a unary operator that produces the binary complement of the value.</span></span> <span data-ttu-id="cbf00-280">Ein Bit von 1 wird auf 0 festgelegt, und ein Bit von 0 wird auf 1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cbf00-280">A bit of 1 is set to 0 and a bit of 0 is set to 1.</span></span>

<span data-ttu-id="cbf00-281">Beispielsweise ist das binäre Komplement von 0-1, die maximale Ganzzahl ohne Vorzeichen (0xFFFFFFFF) und das binäre Komplement von-1 0.</span><span class="sxs-lookup"><span data-stu-id="cbf00-281">For example, the binary complement of 0 is -1, the maximum unsigned integer (0xffffffff), and the binary complement of -1 is 0.</span></span>

```powershell
-bNot 10
```

```Output
-11
```

```
0000 0000 0000 1010  (10)
------------------------- bNOT
1111 1111 1111 0101  (-11, xfffffff5)
```

<span data-ttu-id="cbf00-282">Bei einem bitweisen Shift-Left-Vorgang werden alle Bits "n" nach links verschoben, wobei "n" der Wert des rechten Operanden ist.</span><span class="sxs-lookup"><span data-stu-id="cbf00-282">In a bitwise shift-left operation, all bits are moved "n" places to the left, where "n" is the value of the right operand.</span></span> <span data-ttu-id="cbf00-283">An dieser Stelle wird ein NULL-Wert eingefügt.</span><span class="sxs-lookup"><span data-stu-id="cbf00-283">A zero is inserted in the ones place.</span></span>

<span data-ttu-id="cbf00-284">Wenn der linke Operand ein ganzzahliger Wert (32 Bit) ist, bestimmen die unteren 5 Bits des rechten Operanden, wie viele Bits des linken Operanden verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="cbf00-284">When the left operand is an Integer (32-bit) value, the lower 5 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

<span data-ttu-id="cbf00-285">Wenn der linke Operand ein Long (64-Bit)-Wert ist, bestimmen die unteren 6 Bits des rechten Operanden, wie viele Bits des linken Operanden verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="cbf00-285">When the left operand is a Long (64-bit) value, the lower 6 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

|<span data-ttu-id="cbf00-286">expression</span><span class="sxs-lookup"><span data-stu-id="cbf00-286">Expression</span></span> |<span data-ttu-id="cbf00-287">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cbf00-287">Result</span></span>|<span data-ttu-id="cbf00-288">Binäres Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cbf00-288">Binary Result</span></span>|
|-----------|------|-------------|
|`21 -shl 0`|<span data-ttu-id="cbf00-289">21</span><span class="sxs-lookup"><span data-stu-id="cbf00-289">21</span></span>    |<span data-ttu-id="cbf00-290">0001 0101</span><span class="sxs-lookup"><span data-stu-id="cbf00-290">0001 0101</span></span>    |
|`21 -shl 1`|<span data-ttu-id="cbf00-291">42</span><span class="sxs-lookup"><span data-stu-id="cbf00-291">42</span></span>    |<span data-ttu-id="cbf00-292">0010 1010</span><span class="sxs-lookup"><span data-stu-id="cbf00-292">0010 1010</span></span>    |
|`21 -shl 2`|<span data-ttu-id="cbf00-293">84</span><span class="sxs-lookup"><span data-stu-id="cbf00-293">84</span></span>    |<span data-ttu-id="cbf00-294">0101 0100</span><span class="sxs-lookup"><span data-stu-id="cbf00-294">0101 0100</span></span>    |

<span data-ttu-id="cbf00-295">Bei einem bitweisen shift-right-Vorgang werden alle Bits "n" nach rechts verschoben, wobei "n" durch den rechten Operanden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cbf00-295">In a bitwise shift-right operation, all bits are moved "n" places to the right, where "n" is specified by the right operand.</span></span> <span data-ttu-id="cbf00-296">Der SHIFT-RIGHT-Operator (-SHR) Fügt am äußersten linken Speicherort eine NULL ein, wenn ein positiver oder nicht signierter Wert nach rechts verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="cbf00-296">The shift-right operator (-shr) inserts a zero in the left-most place when shifting a positive or unsigned value to the right.</span></span>

<span data-ttu-id="cbf00-297">Wenn der linke Operand ein ganzzahliger Wert (32 Bit) ist, bestimmen die unteren 5 Bits des rechten Operanden, wie viele Bits des linken Operanden verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="cbf00-297">When the left operand is an Integer (32-bit) value, the lower 5 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

<span data-ttu-id="cbf00-298">Wenn der linke Operand ein Long (64-Bit)-Wert ist, bestimmen die unteren 6 Bits des rechten Operanden, wie viele Bits des linken Operanden verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="cbf00-298">When the left operand is a Long (64-bit) value, the lower 6 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

|<span data-ttu-id="cbf00-299">expression</span><span class="sxs-lookup"><span data-stu-id="cbf00-299">Expression</span></span>              |<span data-ttu-id="cbf00-300">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cbf00-300">Result</span></span>      |<span data-ttu-id="cbf00-301">Binary</span><span class="sxs-lookup"><span data-stu-id="cbf00-301">Binary</span></span>     |<span data-ttu-id="cbf00-302">Hex</span><span class="sxs-lookup"><span data-stu-id="cbf00-302">Hex</span></span>         |
|------------------------|------------|-----------|------------|
|`21 -shr 0`             | <span data-ttu-id="cbf00-303">21</span><span class="sxs-lookup"><span data-stu-id="cbf00-303">21</span></span>         | <span data-ttu-id="cbf00-304">0001 0101</span><span class="sxs-lookup"><span data-stu-id="cbf00-304">0001 0101</span></span> | <span data-ttu-id="cbf00-305">0x15</span><span class="sxs-lookup"><span data-stu-id="cbf00-305">0x15</span></span>       |
|`21 -shr 1`             | <span data-ttu-id="cbf00-306">10</span><span class="sxs-lookup"><span data-stu-id="cbf00-306">10</span></span>         | <span data-ttu-id="cbf00-307">0000 1010</span><span class="sxs-lookup"><span data-stu-id="cbf00-307">0000 1010</span></span> | <span data-ttu-id="cbf00-308">0x0A</span><span class="sxs-lookup"><span data-stu-id="cbf00-308">0x0A</span></span>       |
|`21 -shr 2`             | <span data-ttu-id="cbf00-309">5</span><span class="sxs-lookup"><span data-stu-id="cbf00-309">5</span></span>          | <span data-ttu-id="cbf00-310">0000 0101</span><span class="sxs-lookup"><span data-stu-id="cbf00-310">0000 0101</span></span> | <span data-ttu-id="cbf00-311">0x05</span><span class="sxs-lookup"><span data-stu-id="cbf00-311">0x05</span></span>       |
|`21 -shr 31`            | <span data-ttu-id="cbf00-312">0</span><span class="sxs-lookup"><span data-stu-id="cbf00-312">0</span></span>          | <span data-ttu-id="cbf00-313">0000 0000</span><span class="sxs-lookup"><span data-stu-id="cbf00-313">0000 0000</span></span> | <span data-ttu-id="cbf00-314">0x00</span><span class="sxs-lookup"><span data-stu-id="cbf00-314">0x00</span></span>       |
|`21 -shr 32`            | <span data-ttu-id="cbf00-315">21</span><span class="sxs-lookup"><span data-stu-id="cbf00-315">21</span></span>         | <span data-ttu-id="cbf00-316">0001 0101</span><span class="sxs-lookup"><span data-stu-id="cbf00-316">0001 0101</span></span> | <span data-ttu-id="cbf00-317">0x15</span><span class="sxs-lookup"><span data-stu-id="cbf00-317">0x15</span></span>       |
|`21 -shr 64`            | <span data-ttu-id="cbf00-318">21</span><span class="sxs-lookup"><span data-stu-id="cbf00-318">21</span></span>         | <span data-ttu-id="cbf00-319">0001 0101</span><span class="sxs-lookup"><span data-stu-id="cbf00-319">0001 0101</span></span> | <span data-ttu-id="cbf00-320">0x15</span><span class="sxs-lookup"><span data-stu-id="cbf00-320">0x15</span></span>       |
|`21 -shr 65`            | <span data-ttu-id="cbf00-321">10</span><span class="sxs-lookup"><span data-stu-id="cbf00-321">10</span></span>         | <span data-ttu-id="cbf00-322">0000 1010</span><span class="sxs-lookup"><span data-stu-id="cbf00-322">0000 1010</span></span> | <span data-ttu-id="cbf00-323">0x0A</span><span class="sxs-lookup"><span data-stu-id="cbf00-323">0x0A</span></span>       |
|`21 -shr 66`            | <span data-ttu-id="cbf00-324">5</span><span class="sxs-lookup"><span data-stu-id="cbf00-324">5</span></span>          | <span data-ttu-id="cbf00-325">0000 0101</span><span class="sxs-lookup"><span data-stu-id="cbf00-325">0000 0101</span></span> | <span data-ttu-id="cbf00-326">0x05</span><span class="sxs-lookup"><span data-stu-id="cbf00-326">0x05</span></span>       |
|`[int]::MaxValue -shr 1`| <span data-ttu-id="cbf00-327">1073741823</span><span class="sxs-lookup"><span data-stu-id="cbf00-327">1073741823</span></span> |           | <span data-ttu-id="cbf00-328">0x3fffffff</span><span class="sxs-lookup"><span data-stu-id="cbf00-328">0x3FFFFFFF</span></span> |
|`[int]::MinValue -shr 1`| <span data-ttu-id="cbf00-329">-1073741824</span><span class="sxs-lookup"><span data-stu-id="cbf00-329">-1073741824</span></span>|           | <span data-ttu-id="cbf00-330">0xC0000000</span><span class="sxs-lookup"><span data-stu-id="cbf00-330">0xC0000000</span></span> |
|`-1 -shr 1`             | <span data-ttu-id="cbf00-331">-1</span><span class="sxs-lookup"><span data-stu-id="cbf00-331">-1</span></span>         |           | <span data-ttu-id="cbf00-332">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="cbf00-332">0xFFFFFFFF</span></span> |

## <a name="see-also"></a><span data-ttu-id="cbf00-333">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="cbf00-333">SEE ALSO</span></span>

- [<span data-ttu-id="cbf00-334">about_arrays</span><span class="sxs-lookup"><span data-stu-id="cbf00-334">about_arrays</span></span>](about_Arrays.md)
- [<span data-ttu-id="cbf00-335">about_assignment_operators</span><span class="sxs-lookup"><span data-stu-id="cbf00-335">about_assignment_operators</span></span>](about_Assignment_Operators.md)
- [<span data-ttu-id="cbf00-336">about_comparison_operators</span><span class="sxs-lookup"><span data-stu-id="cbf00-336">about_comparison_operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="cbf00-337">about_hash_tables</span><span class="sxs-lookup"><span data-stu-id="cbf00-337">about_hash_tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="cbf00-338">about_operators</span><span class="sxs-lookup"><span data-stu-id="cbf00-338">about_operators</span></span>](about_Operators.md)
- [<span data-ttu-id="cbf00-339">about_variables</span><span class="sxs-lookup"><span data-stu-id="cbf00-339">about_variables</span></span>](about_Variables.md)
- [<span data-ttu-id="cbf00-340">Get-Date</span><span class="sxs-lookup"><span data-stu-id="cbf00-340">Get-Date</span></span>](xref:Microsoft.PowerShell.Utility.Get-Date)
- [<span data-ttu-id="cbf00-341">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="cbf00-341">New-TimeSpan</span></span>](xref:Microsoft.PowerShell.Utility.New-TimeSpan)
