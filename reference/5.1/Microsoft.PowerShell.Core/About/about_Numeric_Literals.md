---
description: Sowohl ganzzahlige als auch echte numerische Literale können über Typ-und Multiplikator-Suffixe verfügen.
Locale: en-US
ms.date: 04/09/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen zu numerischen Literalen
ms.openlocfilehash: 99fa8c1a751551d028fe6df0b0cec94e07f19c59
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224959"
---
# <a name="about-numeric-literals"></a><span data-ttu-id="07333-103">Informationen zu numerischen Literalen</span><span class="sxs-lookup"><span data-stu-id="07333-103">About numeric literals</span></span>

<span data-ttu-id="07333-104">Es gibt zwei Arten numerischer Literale: Integer und Real.</span><span class="sxs-lookup"><span data-stu-id="07333-104">There are two kinds of numeric literals: integer and real.</span></span> <span data-ttu-id="07333-105">Beide können über Typ-und Multiplikator-Suffixe verfügen.</span><span class="sxs-lookup"><span data-stu-id="07333-105">Both can have type and multiplier suffixes.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="07333-106">Ganzzahlenliteral</span><span class="sxs-lookup"><span data-stu-id="07333-106">Integer literals</span></span>

<span data-ttu-id="07333-107">Ganzzahlige Literale können in Dezimal-oder hexadezimal Notation geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="07333-107">Integer literals can be written in decimal or hexadecimal notation.</span></span> <span data-ttu-id="07333-108">Hexadezimal literalen wird das Präfix vorangestellt `0x` , um Sie von Dezimalzahlen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="07333-108">Hexadecimal literals are prefixed with `0x` to distinguish them from decimal numbers.</span></span>

<span data-ttu-id="07333-109">Ganzzahlige Literale können ein Typsuffix und ein Multiplikator-Suffix aufweisen.</span><span class="sxs-lookup"><span data-stu-id="07333-109">Integer literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="07333-110">Suffix</span><span class="sxs-lookup"><span data-stu-id="07333-110">Suffix</span></span> |       <span data-ttu-id="07333-111">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="07333-111">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="07333-112">l</span><span class="sxs-lookup"><span data-stu-id="07333-112">l</span></span>      | <span data-ttu-id="07333-113">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="07333-113">long data type</span></span>      |
| <span data-ttu-id="07333-114">kb</span><span class="sxs-lookup"><span data-stu-id="07333-114">kb</span></span>     | <span data-ttu-id="07333-115">KB-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="07333-115">kilobyte multiplier</span></span> |
| <span data-ttu-id="07333-116">mb</span><span class="sxs-lookup"><span data-stu-id="07333-116">mb</span></span>     | <span data-ttu-id="07333-117">Megabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="07333-117">megabyte multiplier</span></span> |
| <span data-ttu-id="07333-118">GB</span><span class="sxs-lookup"><span data-stu-id="07333-118">gb</span></span>     | <span data-ttu-id="07333-119">Gigabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="07333-119">gigabyte multiplier</span></span> |
| <span data-ttu-id="07333-120">t</span><span class="sxs-lookup"><span data-stu-id="07333-120">tb</span></span>     | <span data-ttu-id="07333-121">Terabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="07333-121">terabyte multiplier</span></span> |
| <span data-ttu-id="07333-122">PB</span><span class="sxs-lookup"><span data-stu-id="07333-122">pb</span></span>     | <span data-ttu-id="07333-123">Peer tabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="07333-123">petabyte multiplier</span></span> |

<span data-ttu-id="07333-124">Der Typ eines ganzzahligen Literals wird durch seinen Wert, das Typsuffix und das numerische Multiplikator-Suffix bestimmt.</span><span class="sxs-lookup"><span data-stu-id="07333-124">The type of an integer literal is determined by its value, the type suffix, and the numeric multiplier suffix.</span></span>

<span data-ttu-id="07333-125">Für ein Ganzzahlliteral ohne Typsuffix:</span><span class="sxs-lookup"><span data-stu-id="07333-125">For an integer literal with no type suffix:</span></span>

- <span data-ttu-id="07333-126">Wenn der Wert durch den Typ dargestellt werden kann `[int]` , ist dies der Typ.</span><span class="sxs-lookup"><span data-stu-id="07333-126">If the value can be represented by type `[int]`, that is its type.</span></span>
- <span data-ttu-id="07333-127">Andernfalls, wenn der Wert durch den Typ dargestellt werden kann `[long]` , ist dies der Typ.</span><span class="sxs-lookup"><span data-stu-id="07333-127">Otherwise, if the value can be represented by type `[long]`, that is its type.</span></span>
- <span data-ttu-id="07333-128">Andernfalls, wenn der Wert durch den Typ dargestellt werden kann `[decimal]` , ist dies der Typ.</span><span class="sxs-lookup"><span data-stu-id="07333-128">Otherwise, if the value can be represented by type `[decimal]`, that is its type.</span></span>
- <span data-ttu-id="07333-129">Andernfalls wird Sie durch den-Typ dargestellt `[double]` .</span><span class="sxs-lookup"><span data-stu-id="07333-129">Otherwise, it is represented by type `[double]`.</span></span>

<span data-ttu-id="07333-130">Für ein Ganzzahlliteral mit einem Typsuffix:</span><span class="sxs-lookup"><span data-stu-id="07333-130">For an integer literal with a type suffix:</span></span>

- <span data-ttu-id="07333-131">Wenn das Typsuffix ist `u` und der Wert durch den Typ dargestellt werden kann, `[int]` ist sein Typ `[int]` .</span><span class="sxs-lookup"><span data-stu-id="07333-131">If the type suffix is `u` and the value can be represented by type `[int]` then its type is `[int]`.</span></span>
- <span data-ttu-id="07333-132">Wenn das Typsuffix ist `u` und der Wert durch den Typ dargestellt werden kann, `[long]` ist sein Typ `[long]` .</span><span class="sxs-lookup"><span data-stu-id="07333-132">If the type suffix is `u` and the value can be represented by type `[long]` then its type is `[long]`.</span></span>
- <span data-ttu-id="07333-133">Wenn der Wert durch den angegebenen Typ dargestellt werden kann, ist dieser Typ.</span><span class="sxs-lookup"><span data-stu-id="07333-133">If its value can be represented by type specified then that is its type.</span></span>
- <span data-ttu-id="07333-134">Andernfalls ist dieses Literale falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="07333-134">Otherwise, that literal is malformed.</span></span>

## <a name="real-literals"></a><span data-ttu-id="07333-135">Real-Literale</span><span class="sxs-lookup"><span data-stu-id="07333-135">Real literals</span></span>

<span data-ttu-id="07333-136">Echte Literale können nur in Dezimal Schreibweise geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="07333-136">Real literals can only be written in decimal notation.</span></span> <span data-ttu-id="07333-137">Diese Notation kann nach einem Dezimaltrennzeichen und wissenschaftlicher Schreibweise nach Komma Werten mit einem exponentiellen Teil enthalten.</span><span class="sxs-lookup"><span data-stu-id="07333-137">This notation can include fractional values following a decimal point and scientific notation using an exponential part.</span></span>

<span data-ttu-id="07333-138">Der exponentielle Teil enthält ein "e", gefolgt von einem optionalen Vorzeichen (+/-) und einer Zahl, die den Exponenten darstellt.</span><span class="sxs-lookup"><span data-stu-id="07333-138">The exponential part includes an 'e' followed by an optional sign (+/-) and a number representing the exponent.</span></span> <span data-ttu-id="07333-139">Beispielsweise ist der Literalwert mit `1e2` dem numerischen Wert 100.</span><span class="sxs-lookup"><span data-stu-id="07333-139">For example, the literal value `1e2` equals the numeric value 100.</span></span>

<span data-ttu-id="07333-140">Echte Literale können ein Typsuffix und ein Multiplikator-Suffix aufweisen.</span><span class="sxs-lookup"><span data-stu-id="07333-140">Real literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="07333-141">Suffix</span><span class="sxs-lookup"><span data-stu-id="07333-141">Suffix</span></span> |       <span data-ttu-id="07333-142">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="07333-142">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="07333-143">T</span><span class="sxs-lookup"><span data-stu-id="07333-143">d</span></span>      | <span data-ttu-id="07333-144">decimal-Datentyp</span><span class="sxs-lookup"><span data-stu-id="07333-144">decimal data type</span></span>   |
| <span data-ttu-id="07333-145">kb</span><span class="sxs-lookup"><span data-stu-id="07333-145">kb</span></span>     | <span data-ttu-id="07333-146">KB-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="07333-146">kilobyte multiplier</span></span> |
| <span data-ttu-id="07333-147">mb</span><span class="sxs-lookup"><span data-stu-id="07333-147">mb</span></span>     | <span data-ttu-id="07333-148">Megabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="07333-148">megabyte multiplier</span></span> |
| <span data-ttu-id="07333-149">GB</span><span class="sxs-lookup"><span data-stu-id="07333-149">gb</span></span>     | <span data-ttu-id="07333-150">Gigabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="07333-150">gigabyte multiplier</span></span> |
| <span data-ttu-id="07333-151">t</span><span class="sxs-lookup"><span data-stu-id="07333-151">tb</span></span>     | <span data-ttu-id="07333-152">Terabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="07333-152">terabyte multiplier</span></span> |
| <span data-ttu-id="07333-153">PB</span><span class="sxs-lookup"><span data-stu-id="07333-153">pb</span></span>     | <span data-ttu-id="07333-154">Peer tabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="07333-154">petabyte multiplier</span></span> |

<span data-ttu-id="07333-155">Es gibt zwei Arten von echtem Literalen: Double und Decimal.</span><span class="sxs-lookup"><span data-stu-id="07333-155">There are two kinds of real literal: double and decimal.</span></span> <span data-ttu-id="07333-156">Diese werden durch das Fehlen oder vorhanden sein des Suffixes Decimal angegeben.</span><span class="sxs-lookup"><span data-stu-id="07333-156">These are indicated by the absence or presence, respectively, of decimal-type suffix.</span></span> <span data-ttu-id="07333-157">PowerShell unterstützt keine Literale Darstellung eines `[float]` Werts.</span><span class="sxs-lookup"><span data-stu-id="07333-157">PowerShell does not support a literal representation of a `[float]` value.</span></span> <span data-ttu-id="07333-158">Ein Double Real-Literale weist den Typ auf `[double]` .</span><span class="sxs-lookup"><span data-stu-id="07333-158">A double real literal has type `[double]`.</span></span> <span data-ttu-id="07333-159">Ein tatsächliches Dezimaltrennzeichen weist den Typ auf `[decimal]` .</span><span class="sxs-lookup"><span data-stu-id="07333-159">A decimal real literal has type `[decimal]`.</span></span>
<span data-ttu-id="07333-160">Nachfolgende Nullen im Bruchteil eines Dezimal-Real-Literals sind signifikant.</span><span class="sxs-lookup"><span data-stu-id="07333-160">Trailing zeros in the fraction part of a decimal real literal are significant.</span></span>

<span data-ttu-id="07333-161">Wenn der Wert der Ziffern von Exponent-Part in einem `[double]` echten literalen kleiner als der unterstützte Mindestwert ist, ist der Wert dieses `[double]` echten Literals 0.</span><span class="sxs-lookup"><span data-stu-id="07333-161">If the value of exponent-part's digits in a `[double]` real literal is less than the minimum supported, the value of that `[double]` real literal is 0.</span></span> <span data-ttu-id="07333-162">Wenn der Wert der Ziffern von Exponent-Part in einem `[decimal]` echten literalen kleiner als der unterstützte Mindestwert ist, ist dieses Literalformat falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="07333-162">If the value of exponent-part's digits in a `[decimal]` real literal is less than the minimum supported, that literal is malformed.</span></span> <span data-ttu-id="07333-163">Wenn der Wert der Ziffern Exponent-Part in einem `[double]` oder einem `[decimal]` realen Literalwert größer als der maximal unterstützte Wert ist, ist dieses Literalformat falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="07333-163">If the value of exponent-part's digits in a `[double]` or `[decimal]` real literal is greater than the maximum supported, that literal is malformed.</span></span>

> [!NOTE]
> <span data-ttu-id="07333-164">Die Syntax ermöglicht einem Double Real-literalen das Suffix long-Type.</span><span class="sxs-lookup"><span data-stu-id="07333-164">The syntax permits a double real literal to have a long-type suffix.</span></span>
> <span data-ttu-id="07333-165">PowerShell behandelt diesen Fall als Ganzzahlliteral, dessen Wert durch den Typ dargestellt wird `[long]` .</span><span class="sxs-lookup"><span data-stu-id="07333-165">PowerShell treats this case as an integer literal whose value is represented by type `[long]`.</span></span> <span data-ttu-id="07333-166">Diese Funktion wurde aus Gründen der Abwärtskompatibilität mit früheren Versionen von PowerShell beibehalten.</span><span class="sxs-lookup"><span data-stu-id="07333-166">This feature has been retained for backwards compatibility with earlier versions of PowerShell.</span></span> <span data-ttu-id="07333-167">Programmierer werden jedoch davon abgeraten, ganzzahlige Literale dieses Formulars zu verwenden, da Sie den tatsächlichen Wert des Literale leicht verdecken können.</span><span class="sxs-lookup"><span data-stu-id="07333-167">However, programmers are discouraged from using integer literals of this form as they can easily obscure the literal's actual value.</span></span> <span data-ttu-id="07333-168">Hat z. b. den `1.2L` Wert 1, den `1.2345e1L` Wert 12 und `1.2345e-5L` den Wert 0, von denen keiner sofort ersichtlich ist.</span><span class="sxs-lookup"><span data-stu-id="07333-168">For example, `1.2L` has value 1, `1.2345e1L` has value 12, and `1.2345e-5L` has value 0, none of which are immediately obvious.</span></span>

## <a name="numeric-multipliers"></a><span data-ttu-id="07333-169">Numerische Multiplikatoren</span><span class="sxs-lookup"><span data-stu-id="07333-169">Numeric multipliers</span></span>

<span data-ttu-id="07333-170">Aus praktischen Gründen können ganzzahlige und echte Literale einen numerischen Multiplikator enthalten, der einen der häufig verwendeten Kräfte von 2 angibt.</span><span class="sxs-lookup"><span data-stu-id="07333-170">For convenience, integer and real literals can contain a numeric multiplier, which indicates one of a set of commonly used powers of 2.</span></span> <span data-ttu-id="07333-171">Der numerische Multiplikator kann in einer beliebigen Kombination aus Groß-oder Kleinbuchstaben geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="07333-171">The numeric multiplier can be written in any combination of upper or lowercase letters.</span></span>

<span data-ttu-id="07333-172">Die Multiplikator-Suffixe können in Kombination mit den `u` `ul` -,-und- `l` typsuffixen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="07333-172">The multiplier suffixes can be used in combination with the `u`, `ul`, and `l` type suffixes.</span></span>

### <a name="multiplier-examples"></a><span data-ttu-id="07333-173">Multiplikator-Beispiele</span><span class="sxs-lookup"><span data-stu-id="07333-173">Multiplier examples</span></span>

```
PS> 1kb
1024

PS> 1.30Dmb
1363148.80

PS> 0x10Gb
17179869184

PS> 1.4e23tb
1.5393162788864E+35

PS> 0x12Lpb
20266198323167232
```

## <a name="numeric-type-accelerators"></a><span data-ttu-id="07333-174">Numerische typacceleratoren</span><span class="sxs-lookup"><span data-stu-id="07333-174">Numeric type accelerators</span></span>

<span data-ttu-id="07333-175">PowerShell unterstützt die folgenden typacceleratoren:</span><span class="sxs-lookup"><span data-stu-id="07333-175">PowerShell supports the following type accelerators:</span></span>

| <span data-ttu-id="07333-176">Accelerator</span><span class="sxs-lookup"><span data-stu-id="07333-176">Accelerator</span></span> |         <span data-ttu-id="07333-177">Hinweis</span><span class="sxs-lookup"><span data-stu-id="07333-177">Note</span></span>         |           <span data-ttu-id="07333-178">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="07333-178">Description</span></span>            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | <span data-ttu-id="07333-179">Byte (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="07333-179">Byte (unsigned)</span></span>                  |
| `[sbyte]`   |                      | <span data-ttu-id="07333-180">Byte (signiert)</span><span class="sxs-lookup"><span data-stu-id="07333-180">Byte (signed)</span></span>                    |
| `[Int16]`   |                      | <span data-ttu-id="07333-181">16-Bit-Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="07333-181">16-bit integer</span></span>                   |
| `[UInt16]`  |                      | <span data-ttu-id="07333-182">16-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="07333-182">16-bit integer (unsigned)</span></span>        |
| `[Int32]`   |                      | <span data-ttu-id="07333-183">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="07333-183">32-bit integer</span></span>                   |
| `[int]`     | <span data-ttu-id="07333-184">Alias für `[int32]`</span><span class="sxs-lookup"><span data-stu-id="07333-184">alias for `[int32]`</span></span>  | <span data-ttu-id="07333-185">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="07333-185">32-bit integer</span></span>                   |
| `[UInt32]`  |                      | <span data-ttu-id="07333-186">32-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="07333-186">32-bit integer (unsigned)</span></span>        |
| `[Int64]`   |                      | <span data-ttu-id="07333-187">64-Bit-Integer</span><span class="sxs-lookup"><span data-stu-id="07333-187">64-bit integer</span></span>                   |
| `[long]`    | <span data-ttu-id="07333-188">Alias für `[int64]`</span><span class="sxs-lookup"><span data-stu-id="07333-188">alias for `[int64]`</span></span>  | <span data-ttu-id="07333-189">64-Bit-Integer</span><span class="sxs-lookup"><span data-stu-id="07333-189">64-bit integer</span></span>                   |
| `[UInt64]`  |                      | <span data-ttu-id="07333-190">64-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="07333-190">64-bit integer (unsigned)</span></span>        |
| `[bigint]`  |                      | <span data-ttu-id="07333-191">Siehe [BigInteger-Struktur][bigint]</span><span class="sxs-lookup"><span data-stu-id="07333-191">See [BigInteger Struct][bigint]</span></span>  |
| `[single]`  |                      | <span data-ttu-id="07333-192">Gleit Komma mit einfacher Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="07333-192">Single precision floating point</span></span>  |
| `[float]`   | <span data-ttu-id="07333-193">Alias für `[single]`</span><span class="sxs-lookup"><span data-stu-id="07333-193">alias for `[single]`</span></span> | <span data-ttu-id="07333-194">Gleit Komma mit einfacher Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="07333-194">Single precision floating point</span></span>  |
| `[double]`  |                      | <span data-ttu-id="07333-195">Gleit Komma Wert mit doppelter Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="07333-195">Double precision floating point</span></span>  |
| `[decimal]` |                      | <span data-ttu-id="07333-196">128-Bit-Gleit Komma Zahl</span><span class="sxs-lookup"><span data-stu-id="07333-196">128-bit floating point</span></span>           |

### <a name="working-with-other-numeric-types"></a><span data-ttu-id="07333-197">Arbeiten mit anderen numerischen Typen</span><span class="sxs-lookup"><span data-stu-id="07333-197">Working with other numeric types</span></span>

<span data-ttu-id="07333-198">Um mit allen anderen numerischen Typen arbeiten zu können, müssen Sie Type Accelerators verwenden, was nicht ohne Probleme.</span><span class="sxs-lookup"><span data-stu-id="07333-198">To work with any other numeric types you must use type accelerators, which is not without some problems.</span></span> <span data-ttu-id="07333-199">Beispielsweise werden hohe ganzzahlige Werte immer als Double analysiert, bevor Sie in einen anderen Typ umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="07333-199">For example, high integer values are always parsed as double before being cast to any other type.</span></span>

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

<span data-ttu-id="07333-200">Der Wert wird zuerst als Double analysiert und verliert die Genauigkeit in den höheren Bereichen.</span><span class="sxs-lookup"><span data-stu-id="07333-200">The value is parsed as a double first, losing precision in the higher ranges.</span></span>
<span data-ttu-id="07333-201">Um dieses Problem zu vermeiden, geben Sie Werte als Zeichen folgen ein, und konvertieren Sie Sie dann:</span><span class="sxs-lookup"><span data-stu-id="07333-201">To avoid this problem, enter values as strings and then convert them:</span></span>

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

## <a name="examples"></a><span data-ttu-id="07333-202">Beispiele</span><span class="sxs-lookup"><span data-stu-id="07333-202">Examples</span></span>

<span data-ttu-id="07333-203">Die folgende Tabelle enthält einige Beispiele für numerische Literale und listet deren Typ und Wert auf:</span><span class="sxs-lookup"><span data-stu-id="07333-203">The following table contains several examples of numeric literals and lists their type and value:</span></span>

|  <span data-ttu-id="07333-204">Number</span><span class="sxs-lookup"><span data-stu-id="07333-204">Number</span></span>  |  <span data-ttu-id="07333-205">type</span><span class="sxs-lookup"><span data-stu-id="07333-205">Type</span></span>   |    <span data-ttu-id="07333-206">Wert</span><span class="sxs-lookup"><span data-stu-id="07333-206">Value</span></span>     |
| -------: | ------- | -----------: |
|      <span data-ttu-id="07333-207">100</span><span class="sxs-lookup"><span data-stu-id="07333-207">100</span></span> | <span data-ttu-id="07333-208">Int32</span><span class="sxs-lookup"><span data-stu-id="07333-208">Int32</span></span>   |          <span data-ttu-id="07333-209">100</span><span class="sxs-lookup"><span data-stu-id="07333-209">100</span></span> |
|     <span data-ttu-id="07333-210">100 d</span><span class="sxs-lookup"><span data-stu-id="07333-210">100D</span></span> | <span data-ttu-id="07333-211">Decimal</span><span class="sxs-lookup"><span data-stu-id="07333-211">Decimal</span></span> |          <span data-ttu-id="07333-212">100</span><span class="sxs-lookup"><span data-stu-id="07333-212">100</span></span> |
|     <span data-ttu-id="07333-213">100 l</span><span class="sxs-lookup"><span data-stu-id="07333-213">100l</span></span> | <span data-ttu-id="07333-214">Int64</span><span class="sxs-lookup"><span data-stu-id="07333-214">Int64</span></span>   |          <span data-ttu-id="07333-215">100</span><span class="sxs-lookup"><span data-stu-id="07333-215">100</span></span> |
|      <span data-ttu-id="07333-216">1E2</span><span class="sxs-lookup"><span data-stu-id="07333-216">1e2</span></span> | <span data-ttu-id="07333-217">Double</span><span class="sxs-lookup"><span data-stu-id="07333-217">Double</span></span>  |          <span data-ttu-id="07333-218">100</span><span class="sxs-lookup"><span data-stu-id="07333-218">100</span></span> |
|     <span data-ttu-id="07333-219">1. E2</span><span class="sxs-lookup"><span data-stu-id="07333-219">1.e2</span></span> | <span data-ttu-id="07333-220">Double</span><span class="sxs-lookup"><span data-stu-id="07333-220">Double</span></span>  |          <span data-ttu-id="07333-221">100</span><span class="sxs-lookup"><span data-stu-id="07333-221">100</span></span> |
|    <span data-ttu-id="07333-222">0x1e2</span><span class="sxs-lookup"><span data-stu-id="07333-222">0x1e2</span></span> | <span data-ttu-id="07333-223">Int32</span><span class="sxs-lookup"><span data-stu-id="07333-223">Int32</span></span>   |          <span data-ttu-id="07333-224">482</span><span class="sxs-lookup"><span data-stu-id="07333-224">482</span></span> |
|   <span data-ttu-id="07333-225">0x1e2l</span><span class="sxs-lookup"><span data-stu-id="07333-225">0x1e2L</span></span> | <span data-ttu-id="07333-226">Int64</span><span class="sxs-lookup"><span data-stu-id="07333-226">Int64</span></span>   |          <span data-ttu-id="07333-227">482</span><span class="sxs-lookup"><span data-stu-id="07333-227">482</span></span> |
|   <span data-ttu-id="07333-228">0x1e2d</span><span class="sxs-lookup"><span data-stu-id="07333-228">0x1e2D</span></span> | <span data-ttu-id="07333-229">Int32</span><span class="sxs-lookup"><span data-stu-id="07333-229">Int32</span></span>   |         <span data-ttu-id="07333-230">7725</span><span class="sxs-lookup"><span data-stu-id="07333-230">7725</span></span> |
|     <span data-ttu-id="07333-231">482d</span><span class="sxs-lookup"><span data-stu-id="07333-231">482D</span></span> | <span data-ttu-id="07333-232">Decimal</span><span class="sxs-lookup"><span data-stu-id="07333-232">Decimal</span></span> |          <span data-ttu-id="07333-233">482</span><span class="sxs-lookup"><span data-stu-id="07333-233">482</span></span> |
|    <span data-ttu-id="07333-234">482gb</span><span class="sxs-lookup"><span data-stu-id="07333-234">482gb</span></span> | <span data-ttu-id="07333-235">Int64</span><span class="sxs-lookup"><span data-stu-id="07333-235">Int64</span></span>   | <span data-ttu-id="07333-236">517543559168</span><span class="sxs-lookup"><span data-stu-id="07333-236">517543559168</span></span> |
| <span data-ttu-id="07333-237">0x1e2lgb</span><span class="sxs-lookup"><span data-stu-id="07333-237">0x1e2lgb</span></span> | <span data-ttu-id="07333-238">Int64</span><span class="sxs-lookup"><span data-stu-id="07333-238">Int64</span></span>   | <span data-ttu-id="07333-239">517543559168</span><span class="sxs-lookup"><span data-stu-id="07333-239">517543559168</span></span> |

### <a name="commands-that-look-like-numeric-literals"></a><span data-ttu-id="07333-240">Befehle, die wie numerische Literale aussehen</span><span class="sxs-lookup"><span data-stu-id="07333-240">Commands that look like numeric literals</span></span>

<span data-ttu-id="07333-241">Jeder Befehl, der einem numerischen Literalzeichen ähnelt, muss mit dem-Operator aufgerufen werden ( `&` ). andernfalls wird er als eine Zahl des zugeordneten Typs interpretiert.</span><span class="sxs-lookup"><span data-stu-id="07333-241">Any command that looks like a numeric literal must be executed using the the call operator (`&`), otherwise it is interpreted as a number of the associated type.</span></span>

### <a name="access-properties-and-methods-of-numeric-objects"></a><span data-ttu-id="07333-242">Zugreifen auf Eigenschaften und Methoden numerischer Objekte</span><span class="sxs-lookup"><span data-stu-id="07333-242">Access properties and methods of numeric objects</span></span>

<span data-ttu-id="07333-243">Wenn Sie auf ein Member eines numerischen Literals zugreifen müssen, gibt es Fälle, in denen Sie das Literale in Klammern einschließen müssen.</span><span class="sxs-lookup"><span data-stu-id="07333-243">To access a member of a numeric literal, there are cases when you need to enclose the literal in parentheses.</span></span>

- <span data-ttu-id="07333-244">Das Literale weist keinen Dezimaltrennzeichen auf.</span><span class="sxs-lookup"><span data-stu-id="07333-244">The literal does not have a decimal point</span></span>
- <span data-ttu-id="07333-245">Das Literale weist keine Ziffern nach dem Dezimaltrennzeichen auf.</span><span class="sxs-lookup"><span data-stu-id="07333-245">The literal does not have any digits following the decimal point</span></span>
- <span data-ttu-id="07333-246">Das Literale weist kein Suffix auf.</span><span class="sxs-lookup"><span data-stu-id="07333-246">The literal does not have a suffix</span></span>

<span data-ttu-id="07333-247">Im folgenden Beispiel tritt beispielsweise ein Fehler auf:</span><span class="sxs-lookup"><span data-stu-id="07333-247">For example, the following example fails:</span></span>

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

<span data-ttu-id="07333-248">Die folgenden Beispiele funktionieren:</span><span class="sxs-lookup"><span data-stu-id="07333-248">The following examples work:</span></span>

```
PS> 2L.GetType().Name
Int64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

<span data-ttu-id="07333-249">Die ersten beiden Beispiele funktionieren, ohne dass der Literalwert in Klammern eingeschlossen wird, da der PowerShell-Parser ermitteln kann, wo das numerische Literale endet und die **GetType** -Methode gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="07333-249">The first two examples work without enclosing the literal value in parentheses because the PowerShell parser can determine where the numeric literal ends and the **GetType** method starts.</span></span>

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger
