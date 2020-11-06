---
description: Sowohl ganzzahlige als auch echte numerische Literale können über Typ-und Multiplikator-Suffixe verfügen.
Locale: en-US
ms.date: 04/09/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen zu numerischen Literalen
ms.openlocfilehash: dc1a55dbec1f0de99e06011645e6884b37480233
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354828"
---
# <a name="about-numeric-literals"></a><span data-ttu-id="cae67-103">Informationen zu numerischen Literalen</span><span class="sxs-lookup"><span data-stu-id="cae67-103">About numeric literals</span></span>

<span data-ttu-id="cae67-104">Es gibt zwei Arten numerischer Literale: Integer und Real.</span><span class="sxs-lookup"><span data-stu-id="cae67-104">There are two kinds of numeric literals: integer and real.</span></span> <span data-ttu-id="cae67-105">Beide können über Typ-und Multiplikator-Suffixe verfügen.</span><span class="sxs-lookup"><span data-stu-id="cae67-105">Both can have type and multiplier suffixes.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="cae67-106">Ganzzahlenliteral</span><span class="sxs-lookup"><span data-stu-id="cae67-106">Integer literals</span></span>

<span data-ttu-id="cae67-107">Ganzzahlige Literale können in Dezimal-oder hexadezimal Notation geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="cae67-107">Integer literals can be written in decimal or hexadecimal notation.</span></span> <span data-ttu-id="cae67-108">Hexadezimal literalen wird das Präfix vorangestellt `0x` , um Sie von Dezimalzahlen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="cae67-108">Hexadecimal literals are prefixed with `0x` to distinguish them from decimal numbers.</span></span>

<span data-ttu-id="cae67-109">Ganzzahlige Literale können ein Typsuffix und ein Multiplikator-Suffix aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cae67-109">Integer literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="cae67-110">Suffix</span><span class="sxs-lookup"><span data-stu-id="cae67-110">Suffix</span></span> |            <span data-ttu-id="cae67-111">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="cae67-111">Meaning</span></span>             |          <span data-ttu-id="cae67-112">Hinweis</span><span class="sxs-lookup"><span data-stu-id="cae67-112">Note</span></span>           |
| ------ | ------------------------------ | ----------------------- |
| <span data-ttu-id="cae67-113">j</span><span class="sxs-lookup"><span data-stu-id="cae67-113">y</span></span>      | <span data-ttu-id="cae67-114">Byte-Datentyp mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="cae67-114">signed byte data type</span></span>          | <span data-ttu-id="cae67-115">In PowerShell 6,2 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="cae67-115">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="cae67-116">uy</span><span class="sxs-lookup"><span data-stu-id="cae67-116">uy</span></span>     | <span data-ttu-id="cae67-117">Datentyp ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="cae67-117">unsigned byte data type</span></span>        | <span data-ttu-id="cae67-118">In PowerShell 6,2 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="cae67-118">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="cae67-119">s</span><span class="sxs-lookup"><span data-stu-id="cae67-119">s</span></span>      | <span data-ttu-id="cae67-120">short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="cae67-120">short data type</span></span>                | <span data-ttu-id="cae67-121">In PowerShell 6,2 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="cae67-121">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="cae67-122">USA</span><span class="sxs-lookup"><span data-stu-id="cae67-122">us</span></span>     | <span data-ttu-id="cae67-123">Short-Datentyp ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="cae67-123">unsigned short data type</span></span>       | <span data-ttu-id="cae67-124">In PowerShell 6,2 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="cae67-124">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="cae67-125">l</span><span class="sxs-lookup"><span data-stu-id="cae67-125">l</span></span>      | <span data-ttu-id="cae67-126">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="cae67-126">long data type</span></span>                 |                         |
| <span data-ttu-id="cae67-127">u</span><span class="sxs-lookup"><span data-stu-id="cae67-127">u</span></span>      | <span data-ttu-id="cae67-128">Ganzzahl ohne Vorzeichen int-oder Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="cae67-128">unsigned int or long data type</span></span> | <span data-ttu-id="cae67-129">In PowerShell 6,2 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="cae67-129">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="cae67-130">nützlichen</span><span class="sxs-lookup"><span data-stu-id="cae67-130">ul</span></span>     | <span data-ttu-id="cae67-131">Long-Datentyp ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="cae67-131">unsigned long data type</span></span>        | <span data-ttu-id="cae67-132">In PowerShell 6,2 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="cae67-132">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="cae67-133">kb</span><span class="sxs-lookup"><span data-stu-id="cae67-133">kb</span></span>     | <span data-ttu-id="cae67-134">KB-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="cae67-134">kilobyte multiplier</span></span>            |                         |
| <span data-ttu-id="cae67-135">mb</span><span class="sxs-lookup"><span data-stu-id="cae67-135">mb</span></span>     | <span data-ttu-id="cae67-136">Megabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="cae67-136">megabyte multiplier</span></span>            |                         |
| <span data-ttu-id="cae67-137">GB</span><span class="sxs-lookup"><span data-stu-id="cae67-137">gb</span></span>     | <span data-ttu-id="cae67-138">Gigabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="cae67-138">gigabyte multiplier</span></span>            |                         |
| <span data-ttu-id="cae67-139">t</span><span class="sxs-lookup"><span data-stu-id="cae67-139">tb</span></span>     | <span data-ttu-id="cae67-140">Terabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="cae67-140">terabyte multiplier</span></span>            |                         |
| <span data-ttu-id="cae67-141">PB</span><span class="sxs-lookup"><span data-stu-id="cae67-141">pb</span></span>     | <span data-ttu-id="cae67-142">Peer tabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="cae67-142">petabyte multiplier</span></span>            |                         |

<span data-ttu-id="cae67-143">Der Typ eines ganzzahligen Literals wird durch seinen Wert, das Typsuffix und das numerische Multiplikator-Suffix bestimmt.</span><span class="sxs-lookup"><span data-stu-id="cae67-143">The type of an integer literal is determined by its value, the type suffix, and the numeric multiplier suffix.</span></span>

<span data-ttu-id="cae67-144">Für ein Ganzzahlliteral ohne Typsuffix:</span><span class="sxs-lookup"><span data-stu-id="cae67-144">For an integer literal with no type suffix:</span></span>

- <span data-ttu-id="cae67-145">Wenn der Wert durch den Typ dargestellt werden kann `[int]` , ist dies der Typ.</span><span class="sxs-lookup"><span data-stu-id="cae67-145">If the value can be represented by type `[int]`, that is its type.</span></span>
- <span data-ttu-id="cae67-146">Andernfalls, wenn der Wert durch den Typ dargestellt werden kann `[long]` , ist dies der Typ.</span><span class="sxs-lookup"><span data-stu-id="cae67-146">Otherwise, if the value can be represented by type `[long]`, that is its type.</span></span>
- <span data-ttu-id="cae67-147">Andernfalls, wenn der Wert durch den Typ dargestellt werden kann `[decimal]` , ist dies der Typ.</span><span class="sxs-lookup"><span data-stu-id="cae67-147">Otherwise, if the value can be represented by type `[decimal]`, that is its type.</span></span>
- <span data-ttu-id="cae67-148">Andernfalls wird Sie durch den-Typ dargestellt `[double]` .</span><span class="sxs-lookup"><span data-stu-id="cae67-148">Otherwise, it is represented by type `[double]`.</span></span>

<span data-ttu-id="cae67-149">Für ein Ganzzahlliteral mit einem Typsuffix:</span><span class="sxs-lookup"><span data-stu-id="cae67-149">For an integer literal with a type suffix:</span></span>

- <span data-ttu-id="cae67-150">Wenn das Typsuffix ist `u` und der Wert durch den Typ dargestellt werden kann, `[uint]` ist sein Typ `[uint]` .</span><span class="sxs-lookup"><span data-stu-id="cae67-150">If the type suffix is `u` and the value can be represented by type `[uint]` then its type is `[uint]`.</span></span>
- <span data-ttu-id="cae67-151">Wenn das Typsuffix ist `u` und der Wert durch den Typ dargestellt werden kann, `[ulong]` ist sein Typ `[ulong]` .</span><span class="sxs-lookup"><span data-stu-id="cae67-151">If the type suffix is `u` and the value can be represented by type `[ulong]` then its type is `[ulong]`.</span></span>
- <span data-ttu-id="cae67-152">Wenn der Wert durch den angegebenen Typ dargestellt werden kann, ist dieser Typ.</span><span class="sxs-lookup"><span data-stu-id="cae67-152">If its value can be represented by type specified then that is its type.</span></span>
- <span data-ttu-id="cae67-153">Andernfalls ist dieses Literale falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="cae67-153">Otherwise, that literal is malformed.</span></span>

## <a name="real-literals"></a><span data-ttu-id="cae67-154">Real-Literale</span><span class="sxs-lookup"><span data-stu-id="cae67-154">Real literals</span></span>

<span data-ttu-id="cae67-155">Echte Literale können nur in Dezimal Schreibweise geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="cae67-155">Real literals can only be written in decimal notation.</span></span> <span data-ttu-id="cae67-156">Diese Notation kann nach einem Dezimaltrennzeichen und wissenschaftlicher Schreibweise nach Komma Werten mit einem exponentiellen Teil enthalten.</span><span class="sxs-lookup"><span data-stu-id="cae67-156">This notation can include fractional values following a decimal point and scientific notation using an exponential part.</span></span>

<span data-ttu-id="cae67-157">Der exponentielle Teil enthält ein "e", gefolgt von einem optionalen Vorzeichen (+/-) und einer Zahl, die den Exponenten darstellt.</span><span class="sxs-lookup"><span data-stu-id="cae67-157">The exponential part includes an 'e' followed by an optional sign (+/-) and a number representing the exponent.</span></span> <span data-ttu-id="cae67-158">Beispielsweise ist der Literalwert mit `1e2` dem numerischen Wert 100.</span><span class="sxs-lookup"><span data-stu-id="cae67-158">For example, the literal value `1e2` equals the numeric value 100.</span></span>

<span data-ttu-id="cae67-159">Echte Literale können ein Typsuffix und ein Multiplikator-Suffix aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cae67-159">Real literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="cae67-160">Suffix</span><span class="sxs-lookup"><span data-stu-id="cae67-160">Suffix</span></span> |       <span data-ttu-id="cae67-161">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="cae67-161">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="cae67-162">T</span><span class="sxs-lookup"><span data-stu-id="cae67-162">d</span></span>      | <span data-ttu-id="cae67-163">decimal-Datentyp</span><span class="sxs-lookup"><span data-stu-id="cae67-163">decimal data type</span></span>   |
| <span data-ttu-id="cae67-164">kb</span><span class="sxs-lookup"><span data-stu-id="cae67-164">kb</span></span>     | <span data-ttu-id="cae67-165">KB-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="cae67-165">kilobyte multiplier</span></span> |
| <span data-ttu-id="cae67-166">mb</span><span class="sxs-lookup"><span data-stu-id="cae67-166">mb</span></span>     | <span data-ttu-id="cae67-167">Megabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="cae67-167">megabyte multiplier</span></span> |
| <span data-ttu-id="cae67-168">GB</span><span class="sxs-lookup"><span data-stu-id="cae67-168">gb</span></span>     | <span data-ttu-id="cae67-169">Gigabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="cae67-169">gigabyte multiplier</span></span> |
| <span data-ttu-id="cae67-170">t</span><span class="sxs-lookup"><span data-stu-id="cae67-170">tb</span></span>     | <span data-ttu-id="cae67-171">Terabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="cae67-171">terabyte multiplier</span></span> |
| <span data-ttu-id="cae67-172">PB</span><span class="sxs-lookup"><span data-stu-id="cae67-172">pb</span></span>     | <span data-ttu-id="cae67-173">Peer tabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="cae67-173">petabyte multiplier</span></span> |

<span data-ttu-id="cae67-174">Es gibt zwei Arten von echtem Literalen: Double und Decimal.</span><span class="sxs-lookup"><span data-stu-id="cae67-174">There are two kinds of real literal: double and decimal.</span></span> <span data-ttu-id="cae67-175">Diese werden durch das Fehlen oder vorhanden sein des Suffixes Decimal angegeben.</span><span class="sxs-lookup"><span data-stu-id="cae67-175">These are indicated by the absence or presence, respectively, of decimal-type suffix.</span></span> <span data-ttu-id="cae67-176">PowerShell unterstützt keine Literale Darstellung eines `[float]` Werts.</span><span class="sxs-lookup"><span data-stu-id="cae67-176">PowerShell does not support a literal representation of a `[float]` value.</span></span> <span data-ttu-id="cae67-177">Ein Double Real-Literale weist den Typ auf `[double]` .</span><span class="sxs-lookup"><span data-stu-id="cae67-177">A double real literal has type `[double]`.</span></span> <span data-ttu-id="cae67-178">Ein tatsächliches Dezimaltrennzeichen weist den Typ auf `[decimal]` .</span><span class="sxs-lookup"><span data-stu-id="cae67-178">A decimal real literal has type `[decimal]`.</span></span>
<span data-ttu-id="cae67-179">Nachfolgende Nullen im Bruchteil eines Dezimal-Real-Literals sind signifikant.</span><span class="sxs-lookup"><span data-stu-id="cae67-179">Trailing zeros in the fraction part of a decimal real literal are significant.</span></span>

<span data-ttu-id="cae67-180">Wenn der Wert der Ziffern von Exponent-Part in einem `[double]` echten literalen kleiner als der unterstützte Mindestwert ist, ist der Wert dieses `[double]` echten Literals 0.</span><span class="sxs-lookup"><span data-stu-id="cae67-180">If the value of exponent-part's digits in a `[double]` real literal is less than the minimum supported, the value of that `[double]` real literal is 0.</span></span> <span data-ttu-id="cae67-181">Wenn der Wert der Ziffern von Exponent-Part in einem `[decimal]` echten literalen kleiner als der unterstützte Mindestwert ist, ist dieses Literalformat falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="cae67-181">If the value of exponent-part's digits in a `[decimal]` real literal is less than the minimum supported, that literal is malformed.</span></span> <span data-ttu-id="cae67-182">Wenn der Wert der Ziffern Exponent-Part in einem `[double]` oder einem `[decimal]` realen Literalwert größer als der maximal unterstützte Wert ist, ist dieses Literalformat falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="cae67-182">If the value of exponent-part's digits in a `[double]` or `[decimal]` real literal is greater than the maximum supported, that literal is malformed.</span></span>

> [!NOTE]
> <span data-ttu-id="cae67-183">Die Syntax ermöglicht einem Double Real-literalen das Suffix long-Type.</span><span class="sxs-lookup"><span data-stu-id="cae67-183">The syntax permits a double real literal to have a long-type suffix.</span></span>
> <span data-ttu-id="cae67-184">PowerShell behandelt diesen Fall als Ganzzahlliteral, dessen Wert durch den Typ dargestellt wird `[long]` .</span><span class="sxs-lookup"><span data-stu-id="cae67-184">PowerShell treats this case as an integer literal whose value is represented by type `[long]`.</span></span> <span data-ttu-id="cae67-185">Diese Funktion wurde aus Gründen der Abwärtskompatibilität mit früheren Versionen von PowerShell beibehalten.</span><span class="sxs-lookup"><span data-stu-id="cae67-185">This feature has been retained for backwards compatibility with earlier versions of PowerShell.</span></span> <span data-ttu-id="cae67-186">Programmierer werden jedoch davon abgeraten, ganzzahlige Literale dieses Formulars zu verwenden, da Sie den tatsächlichen Wert des Literale leicht verdecken können.</span><span class="sxs-lookup"><span data-stu-id="cae67-186">However, programmers are discouraged from using integer literals of this form as they can easily obscure the literal's actual value.</span></span> <span data-ttu-id="cae67-187">Hat z. b. den `1.2L` Wert 1, den `1.2345e1L` Wert 12 und `1.2345e-5L` den Wert 0, von denen keiner sofort ersichtlich ist.</span><span class="sxs-lookup"><span data-stu-id="cae67-187">For example, `1.2L` has value 1, `1.2345e1L` has value 12, and `1.2345e-5L` has value 0, none of which are immediately obvious.</span></span>

## <a name="numeric-multipliers"></a><span data-ttu-id="cae67-188">Numerische Multiplikatoren</span><span class="sxs-lookup"><span data-stu-id="cae67-188">Numeric multipliers</span></span>

<span data-ttu-id="cae67-189">Aus praktischen Gründen können ganzzahlige und echte Literale einen numerischen Multiplikator enthalten, der einen der häufig verwendeten Kräfte von 2 angibt.</span><span class="sxs-lookup"><span data-stu-id="cae67-189">For convenience, integer and real literals can contain a numeric multiplier, which indicates one of a set of commonly used powers of 2.</span></span> <span data-ttu-id="cae67-190">Der numerische Multiplikator kann in einer beliebigen Kombination aus Groß-oder Kleinbuchstaben geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="cae67-190">The numeric multiplier can be written in any combination of upper or lowercase letters.</span></span>

<span data-ttu-id="cae67-191">Die Multiplikator-Suffixe können in Kombination mit den `u` `ul` -,-und- `l` typsuffixen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cae67-191">The multiplier suffixes can be used in combination with the `u`, `ul`, and `l` type suffixes.</span></span>

### <a name="multiplier-examples"></a><span data-ttu-id="cae67-192">Multiplikator-Beispiele</span><span class="sxs-lookup"><span data-stu-id="cae67-192">Multiplier examples</span></span>

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

## <a name="numeric-type-accelerators"></a><span data-ttu-id="cae67-193">Numerische typacceleratoren</span><span class="sxs-lookup"><span data-stu-id="cae67-193">Numeric type accelerators</span></span>

<span data-ttu-id="cae67-194">PowerShell unterstützt die folgenden typacceleratoren:</span><span class="sxs-lookup"><span data-stu-id="cae67-194">PowerShell supports the following type accelerators:</span></span>

| <span data-ttu-id="cae67-195">Accelerator</span><span class="sxs-lookup"><span data-stu-id="cae67-195">Accelerator</span></span> |         <span data-ttu-id="cae67-196">Hinweis</span><span class="sxs-lookup"><span data-stu-id="cae67-196">Note</span></span>         |           <span data-ttu-id="cae67-197">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cae67-197">Description</span></span>            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | <span data-ttu-id="cae67-198">Byte (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="cae67-198">Byte (unsigned)</span></span>                  |
| `[sbyte]`   |                      | <span data-ttu-id="cae67-199">Byte (signiert)</span><span class="sxs-lookup"><span data-stu-id="cae67-199">Byte (signed)</span></span>                    |
| `[Int16]`   |                      | <span data-ttu-id="cae67-200">16-Bit-Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="cae67-200">16-bit integer</span></span>                   |
| `[short]`   | <span data-ttu-id="cae67-201">Alias für `[int16]`</span><span class="sxs-lookup"><span data-stu-id="cae67-201">alias for `[int16]`</span></span>  | <span data-ttu-id="cae67-202">16-Bit-Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="cae67-202">16-bit integer</span></span>                   |
| `[UInt16]`  |                      | <span data-ttu-id="cae67-203">16-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="cae67-203">16-bit integer (unsigned)</span></span>        |
| `[ushort]`  | <span data-ttu-id="cae67-204">Alias für `[uint16]`</span><span class="sxs-lookup"><span data-stu-id="cae67-204">alias for `[uint16]`</span></span> | <span data-ttu-id="cae67-205">16-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="cae67-205">16-bit integer (unsigned)</span></span>        |
| `[Int32]`   |                      | <span data-ttu-id="cae67-206">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="cae67-206">32-bit integer</span></span>                   |
| `[int]`     | <span data-ttu-id="cae67-207">Alias für `[int32]`</span><span class="sxs-lookup"><span data-stu-id="cae67-207">alias for `[int32]`</span></span>  | <span data-ttu-id="cae67-208">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="cae67-208">32-bit integer</span></span>                   |
| `[UInt32]`  |                      | <span data-ttu-id="cae67-209">32-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="cae67-209">32-bit integer (unsigned)</span></span>        |
| `[uint]`    | <span data-ttu-id="cae67-210">Alias für `[uint32]`</span><span class="sxs-lookup"><span data-stu-id="cae67-210">alias for `[uint32]`</span></span> | <span data-ttu-id="cae67-211">32-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="cae67-211">32-bit integer (unsigned)</span></span>        |
| `[Int64]`   |                      | <span data-ttu-id="cae67-212">64-Bit-Integer</span><span class="sxs-lookup"><span data-stu-id="cae67-212">64-bit integer</span></span>                   |
| `[long]`    | <span data-ttu-id="cae67-213">Alias für `[int64]`</span><span class="sxs-lookup"><span data-stu-id="cae67-213">alias for `[int64]`</span></span>  | <span data-ttu-id="cae67-214">64-Bit-Integer</span><span class="sxs-lookup"><span data-stu-id="cae67-214">64-bit integer</span></span>                   |
| `[UInt64]`  |                      | <span data-ttu-id="cae67-215">64-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="cae67-215">64-bit integer (unsigned)</span></span>        |
| `[ulong]`   | <span data-ttu-id="cae67-216">Alias für `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="cae67-216">alias for `[uint64]`</span></span> | <span data-ttu-id="cae67-217">64-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="cae67-217">64-bit integer (unsigned)</span></span>        |
| `[bigint]`  |                      | <span data-ttu-id="cae67-218">Siehe [BigInteger-Struktur][bigint]</span><span class="sxs-lookup"><span data-stu-id="cae67-218">See [BigInteger Struct][bigint]</span></span>  |
| `[single]`  |                      | <span data-ttu-id="cae67-219">Gleit Komma mit einfacher Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="cae67-219">Single precision floating point</span></span>  |
| `[float]`   | <span data-ttu-id="cae67-220">Alias für `[single]`</span><span class="sxs-lookup"><span data-stu-id="cae67-220">alias for `[single]`</span></span> | <span data-ttu-id="cae67-221">Gleit Komma mit einfacher Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="cae67-221">Single precision floating point</span></span>  |
| `[double]`  |                      | <span data-ttu-id="cae67-222">Gleit Komma Wert mit doppelter Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="cae67-222">Double precision floating point</span></span>  |
| `[decimal]` |                      | <span data-ttu-id="cae67-223">128-Bit-Gleit Komma Zahl</span><span class="sxs-lookup"><span data-stu-id="cae67-223">128-bit floating point</span></span>           |

> [!NOTE]
> <span data-ttu-id="cae67-224">Die folgenden typacceleratoren wurden in PowerShell 6,2 hinzugefügt: `[short]` , `[ushort]` , `[uint]` , `[ulong]` .</span><span class="sxs-lookup"><span data-stu-id="cae67-224">The following type accelerators were added in PowerShell 6.2: `[short]`, `[ushort]`, `[uint]`, `[ulong]`.</span></span>

### <a name="working-with-other-numeric-types"></a><span data-ttu-id="cae67-225">Arbeiten mit anderen numerischen Typen</span><span class="sxs-lookup"><span data-stu-id="cae67-225">Working with other numeric types</span></span>

<span data-ttu-id="cae67-226">Um mit allen anderen numerischen Typen arbeiten zu können, müssen Sie Type Accelerators verwenden, was nicht ohne Probleme.</span><span class="sxs-lookup"><span data-stu-id="cae67-226">To work with any other numeric types you must use type accelerators, which is not without some problems.</span></span> <span data-ttu-id="cae67-227">Beispielsweise werden hohe ganzzahlige Werte immer als Double analysiert, bevor Sie in einen anderen Typ umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="cae67-227">For example, high integer values are always parsed as double before being cast to any other type.</span></span>

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

<span data-ttu-id="cae67-228">Der Wert wird zuerst als Double analysiert und verliert die Genauigkeit in den höheren Bereichen.</span><span class="sxs-lookup"><span data-stu-id="cae67-228">The value is parsed as a double first, losing precision in the higher ranges.</span></span>
<span data-ttu-id="cae67-229">Um dieses Problem zu vermeiden, geben Sie Werte als Zeichen folgen ein, und konvertieren Sie Sie dann:</span><span class="sxs-lookup"><span data-stu-id="cae67-229">To avoid this problem, enter values as strings and then convert them:</span></span>

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

## <a name="examples"></a><span data-ttu-id="cae67-230">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cae67-230">Examples</span></span>

<span data-ttu-id="cae67-231">Die folgende Tabelle enthält einige Beispiele für numerische Literale und listet deren Typ und Wert auf:</span><span class="sxs-lookup"><span data-stu-id="cae67-231">The following table contains several examples of numeric literals and lists their type and value:</span></span>

|  <span data-ttu-id="cae67-232">Number</span><span class="sxs-lookup"><span data-stu-id="cae67-232">Number</span></span>  |  <span data-ttu-id="cae67-233">Typ</span><span class="sxs-lookup"><span data-stu-id="cae67-233">Type</span></span>   |    <span data-ttu-id="cae67-234">Wert</span><span class="sxs-lookup"><span data-stu-id="cae67-234">Value</span></span>     |
| -------: | ------- | -----------: |
|      <span data-ttu-id="cae67-235">100</span><span class="sxs-lookup"><span data-stu-id="cae67-235">100</span></span> | <span data-ttu-id="cae67-236">Int32</span><span class="sxs-lookup"><span data-stu-id="cae67-236">Int32</span></span>   |          <span data-ttu-id="cae67-237">100</span><span class="sxs-lookup"><span data-stu-id="cae67-237">100</span></span> |
|     <span data-ttu-id="cae67-238">100 d</span><span class="sxs-lookup"><span data-stu-id="cae67-238">100D</span></span> | <span data-ttu-id="cae67-239">Decimal</span><span class="sxs-lookup"><span data-stu-id="cae67-239">Decimal</span></span> |          <span data-ttu-id="cae67-240">100</span><span class="sxs-lookup"><span data-stu-id="cae67-240">100</span></span> |
|     <span data-ttu-id="cae67-241">100 l</span><span class="sxs-lookup"><span data-stu-id="cae67-241">100l</span></span> | <span data-ttu-id="cae67-242">Int64</span><span class="sxs-lookup"><span data-stu-id="cae67-242">Int64</span></span>   |          <span data-ttu-id="cae67-243">100</span><span class="sxs-lookup"><span data-stu-id="cae67-243">100</span></span> |
|    <span data-ttu-id="cae67-244">100 UL</span><span class="sxs-lookup"><span data-stu-id="cae67-244">100uL</span></span> | <span data-ttu-id="cae67-245">UInt64</span><span class="sxs-lookup"><span data-stu-id="cae67-245">UInt64</span></span>  |          <span data-ttu-id="cae67-246">100</span><span class="sxs-lookup"><span data-stu-id="cae67-246">100</span></span> |
|    <span data-ttu-id="cae67-247">100 US-</span><span class="sxs-lookup"><span data-stu-id="cae67-247">100us</span></span> | <span data-ttu-id="cae67-248">UInt16</span><span class="sxs-lookup"><span data-stu-id="cae67-248">UInt16</span></span>  |          <span data-ttu-id="cae67-249">100</span><span class="sxs-lookup"><span data-stu-id="cae67-249">100</span></span> |
|    <span data-ttu-id="cae67-250">100 uy</span><span class="sxs-lookup"><span data-stu-id="cae67-250">100uy</span></span> | <span data-ttu-id="cae67-251">Byte</span><span class="sxs-lookup"><span data-stu-id="cae67-251">Byte</span></span>    |          <span data-ttu-id="cae67-252">100</span><span class="sxs-lookup"><span data-stu-id="cae67-252">100</span></span> |
|     <span data-ttu-id="cae67-253">100 y</span><span class="sxs-lookup"><span data-stu-id="cae67-253">100y</span></span> | <span data-ttu-id="cae67-254">SByte</span><span class="sxs-lookup"><span data-stu-id="cae67-254">SByte</span></span>   |          <span data-ttu-id="cae67-255">100</span><span class="sxs-lookup"><span data-stu-id="cae67-255">100</span></span> |
|      <span data-ttu-id="cae67-256">1E2</span><span class="sxs-lookup"><span data-stu-id="cae67-256">1e2</span></span> | <span data-ttu-id="cae67-257">Double</span><span class="sxs-lookup"><span data-stu-id="cae67-257">Double</span></span>  |          <span data-ttu-id="cae67-258">100</span><span class="sxs-lookup"><span data-stu-id="cae67-258">100</span></span> |
|     <span data-ttu-id="cae67-259">1. E2</span><span class="sxs-lookup"><span data-stu-id="cae67-259">1.e2</span></span> | <span data-ttu-id="cae67-260">Double</span><span class="sxs-lookup"><span data-stu-id="cae67-260">Double</span></span>  |          <span data-ttu-id="cae67-261">100</span><span class="sxs-lookup"><span data-stu-id="cae67-261">100</span></span> |
|    <span data-ttu-id="cae67-262">0x1e2</span><span class="sxs-lookup"><span data-stu-id="cae67-262">0x1e2</span></span> | <span data-ttu-id="cae67-263">Int32</span><span class="sxs-lookup"><span data-stu-id="cae67-263">Int32</span></span>   |          <span data-ttu-id="cae67-264">482</span><span class="sxs-lookup"><span data-stu-id="cae67-264">482</span></span> |
|   <span data-ttu-id="cae67-265">0x1e2l</span><span class="sxs-lookup"><span data-stu-id="cae67-265">0x1e2L</span></span> | <span data-ttu-id="cae67-266">Int64</span><span class="sxs-lookup"><span data-stu-id="cae67-266">Int64</span></span>   |          <span data-ttu-id="cae67-267">482</span><span class="sxs-lookup"><span data-stu-id="cae67-267">482</span></span> |
|   <span data-ttu-id="cae67-268">0x1e2d</span><span class="sxs-lookup"><span data-stu-id="cae67-268">0x1e2D</span></span> | <span data-ttu-id="cae67-269">Int32</span><span class="sxs-lookup"><span data-stu-id="cae67-269">Int32</span></span>   |         <span data-ttu-id="cae67-270">7725</span><span class="sxs-lookup"><span data-stu-id="cae67-270">7725</span></span> |
|     <span data-ttu-id="cae67-271">482d</span><span class="sxs-lookup"><span data-stu-id="cae67-271">482D</span></span> | <span data-ttu-id="cae67-272">Decimal</span><span class="sxs-lookup"><span data-stu-id="cae67-272">Decimal</span></span> |          <span data-ttu-id="cae67-273">482</span><span class="sxs-lookup"><span data-stu-id="cae67-273">482</span></span> |
|    <span data-ttu-id="cae67-274">482gb</span><span class="sxs-lookup"><span data-stu-id="cae67-274">482gb</span></span> | <span data-ttu-id="cae67-275">Int64</span><span class="sxs-lookup"><span data-stu-id="cae67-275">Int64</span></span>   | <span data-ttu-id="cae67-276">517543559168</span><span class="sxs-lookup"><span data-stu-id="cae67-276">517543559168</span></span> |
| <span data-ttu-id="cae67-277">0x1e2lgb</span><span class="sxs-lookup"><span data-stu-id="cae67-277">0x1e2lgb</span></span> | <span data-ttu-id="cae67-278">Int64</span><span class="sxs-lookup"><span data-stu-id="cae67-278">Int64</span></span>   | <span data-ttu-id="cae67-279">517543559168</span><span class="sxs-lookup"><span data-stu-id="cae67-279">517543559168</span></span> |

### <a name="commands-that-look-like-numeric-literals"></a><span data-ttu-id="cae67-280">Befehle, die wie numerische Literale aussehen</span><span class="sxs-lookup"><span data-stu-id="cae67-280">Commands that look like numeric literals</span></span>

<span data-ttu-id="cae67-281">Jeder Befehl, der einem numerischen Literalzeichen ähnelt, muss mit dem-Operator aufgerufen werden ( `&` ). andernfalls wird er als eine Zahl des zugeordneten Typs interpretiert.</span><span class="sxs-lookup"><span data-stu-id="cae67-281">Any command that looks like a numeric literal must be executed using the the call operator (`&`), otherwise it is interpreted as a number of the associated type.</span></span>

### <a name="access-properties-and-methods-of-numeric-objects"></a><span data-ttu-id="cae67-282">Zugreifen auf Eigenschaften und Methoden numerischer Objekte</span><span class="sxs-lookup"><span data-stu-id="cae67-282">Access properties and methods of numeric objects</span></span>

<span data-ttu-id="cae67-283">Wenn Sie auf ein Member eines numerischen Literals zugreifen müssen, gibt es Fälle, in denen Sie das Literale in Klammern einschließen müssen.</span><span class="sxs-lookup"><span data-stu-id="cae67-283">To access a member of a numeric literal, there are cases when you need to enclose the literal in parentheses.</span></span>

- <span data-ttu-id="cae67-284">Das Literale weist keinen Dezimaltrennzeichen auf.</span><span class="sxs-lookup"><span data-stu-id="cae67-284">The literal does not have a decimal point</span></span>
- <span data-ttu-id="cae67-285">Das Literale weist keine Ziffern nach dem Dezimaltrennzeichen auf.</span><span class="sxs-lookup"><span data-stu-id="cae67-285">The literal does not have any digits following the decimal point</span></span>
- <span data-ttu-id="cae67-286">Das Literale weist kein Suffix auf.</span><span class="sxs-lookup"><span data-stu-id="cae67-286">The literal does not have a suffix</span></span>

<span data-ttu-id="cae67-287">Im folgenden Beispiel tritt beispielsweise ein Fehler auf:</span><span class="sxs-lookup"><span data-stu-id="cae67-287">For example, the following example fails:</span></span>

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

<span data-ttu-id="cae67-288">Die folgenden Beispiele funktionieren:</span><span class="sxs-lookup"><span data-stu-id="cae67-288">The following examples work:</span></span>

```
PS> 2uL.GetType().Name
UInt64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

<span data-ttu-id="cae67-289">Die ersten beiden Beispiele funktionieren, ohne dass der Literalwert in Klammern eingeschlossen wird, da der PowerShell-Parser ermitteln kann, wo das numerische Literale endet und die **GetType** -Methode gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="cae67-289">The first two examples work without enclosing the literal value in parentheses because the PowerShell parser can determine where the numeric literal ends and the **GetType** method starts.</span></span>

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger
