---
description: Beschreibt die Operatoren, die Werte in PowerShell vergleichen.
Locale: en-US
ms.date: 12/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: ba671ae51d458a2e0074a85d4de859795c20a3d5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97069902"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="97b03-103">Informationen zu Vergleichs Operatoren</span><span class="sxs-lookup"><span data-stu-id="97b03-103">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="97b03-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97b03-104">Short description</span></span>
<span data-ttu-id="97b03-105">Beschreibt die Operatoren, die Werte in PowerShell vergleichen.</span><span class="sxs-lookup"><span data-stu-id="97b03-105">Describes the operators that compare values in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="97b03-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97b03-106">Long description</span></span>

<span data-ttu-id="97b03-107">Mit Vergleichs Operatoren können Sie Bedingungen zum Vergleichen von Werten und suchen von Werten angeben, die den angegebenen Mustern entsprechen.</span><span class="sxs-lookup"><span data-stu-id="97b03-107">Comparison operators let you specify conditions for comparing values and finding values that match specified patterns.</span></span> <span data-ttu-id="97b03-108">Wenn Sie einen Vergleichs Operator verwenden möchten, geben Sie die Werte, die Sie miteinander vergleichen möchten, mit einem Operator an, der diese Werte trennt.</span><span class="sxs-lookup"><span data-stu-id="97b03-108">To use a comparison operator, specify the values that you want to compare together with an operator that separates these values.</span></span>

<span data-ttu-id="97b03-109">PowerShell umfasst die folgenden Vergleichs Operatoren:</span><span class="sxs-lookup"><span data-stu-id="97b03-109">PowerShell includes the following comparison operators:</span></span>

| <span data-ttu-id="97b03-110">type</span><span class="sxs-lookup"><span data-stu-id="97b03-110">Type</span></span>        | <span data-ttu-id="97b03-111">Operatoren</span><span class="sxs-lookup"><span data-stu-id="97b03-111">Operators</span></span>    | <span data-ttu-id="97b03-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97b03-112">Description</span></span>                                 |
| ----------- | ------------ | --------------------------------------------|
| <span data-ttu-id="97b03-113">Gleichheit</span><span class="sxs-lookup"><span data-stu-id="97b03-113">Equality</span></span>    | <span data-ttu-id="97b03-114">-eq</span><span class="sxs-lookup"><span data-stu-id="97b03-114">-eq</span></span>          | <span data-ttu-id="97b03-115">equals</span><span class="sxs-lookup"><span data-stu-id="97b03-115">equals</span></span>                                      |
|             | <span data-ttu-id="97b03-116">-ne</span><span class="sxs-lookup"><span data-stu-id="97b03-116">-ne</span></span>          | <span data-ttu-id="97b03-117">ungleich</span><span class="sxs-lookup"><span data-stu-id="97b03-117">not equals</span></span>                                  |
|             | <span data-ttu-id="97b03-118">-gt</span><span class="sxs-lookup"><span data-stu-id="97b03-118">-gt</span></span>          | <span data-ttu-id="97b03-119">Größer als</span><span class="sxs-lookup"><span data-stu-id="97b03-119">greater than</span></span>                                |
|             | <span data-ttu-id="97b03-120">-ge</span><span class="sxs-lookup"><span data-stu-id="97b03-120">-ge</span></span>          | <span data-ttu-id="97b03-121">Größer als oder gleich</span><span class="sxs-lookup"><span data-stu-id="97b03-121">greater than or equal</span></span>                       |
|             | <span data-ttu-id="97b03-122">-lt</span><span class="sxs-lookup"><span data-stu-id="97b03-122">-lt</span></span>          | <span data-ttu-id="97b03-123">Kleiner als</span><span class="sxs-lookup"><span data-stu-id="97b03-123">less than</span></span>                                   |
|             | <span data-ttu-id="97b03-124">-le</span><span class="sxs-lookup"><span data-stu-id="97b03-124">-le</span></span>          | <span data-ttu-id="97b03-125">Kleiner als oder gleich</span><span class="sxs-lookup"><span data-stu-id="97b03-125">less than or equal</span></span>                          |
|             |              |                                             |
| <span data-ttu-id="97b03-126">Matching</span><span class="sxs-lookup"><span data-stu-id="97b03-126">Matching</span></span>    | <span data-ttu-id="97b03-127">-like</span><span class="sxs-lookup"><span data-stu-id="97b03-127">-like</span></span>        | <span data-ttu-id="97b03-128">Gibt "true" zurück, wenn die Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="97b03-128">Returns true when string matches wildcard</span></span>   |
|             |              | <span data-ttu-id="97b03-129">pattern</span><span class="sxs-lookup"><span data-stu-id="97b03-129">pattern</span></span>                                     |
|             | <span data-ttu-id="97b03-130">-notlike</span><span class="sxs-lookup"><span data-stu-id="97b03-130">-notlike</span></span>     | <span data-ttu-id="97b03-131">Gibt true zurück, wenn die Zeichenfolge nicht entspricht.</span><span class="sxs-lookup"><span data-stu-id="97b03-131">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="97b03-132">Platzhalter Muster</span><span class="sxs-lookup"><span data-stu-id="97b03-132">wildcard pattern</span></span>                            |
|             | <span data-ttu-id="97b03-133">-match</span><span class="sxs-lookup"><span data-stu-id="97b03-133">-match</span></span>       | <span data-ttu-id="97b03-134">Gibt true zurück, wenn die Zeichenfolge dem regulären Ausdruck entspricht</span><span class="sxs-lookup"><span data-stu-id="97b03-134">Returns true when string matches regex</span></span>      |
|             |              | <span data-ttu-id="97b03-135">Bau $Matches enthält übereinstimmende Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="97b03-135">pattern; $matches contains matching strings</span></span> |
|             | <span data-ttu-id="97b03-136">-notmatch</span><span class="sxs-lookup"><span data-stu-id="97b03-136">-notmatch</span></span>    | <span data-ttu-id="97b03-137">Gibt true zurück, wenn die Zeichenfolge nicht entspricht.</span><span class="sxs-lookup"><span data-stu-id="97b03-137">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="97b03-138">Regex-Muster; $Matches enthält Übereinstimmungen.</span><span class="sxs-lookup"><span data-stu-id="97b03-138">regex pattern; $matches contains matching</span></span>   |
|             |              | <span data-ttu-id="97b03-139">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="97b03-139">strings</span></span>                                     |
|             |              |                                             |
| <span data-ttu-id="97b03-140">Containment</span><span class="sxs-lookup"><span data-stu-id="97b03-140">Containment</span></span> | <span data-ttu-id="97b03-141">-contains</span><span class="sxs-lookup"><span data-stu-id="97b03-141">-contains</span></span>    | <span data-ttu-id="97b03-142">Gibt true zurück, wenn der Verweis Wert enthalten ist</span><span class="sxs-lookup"><span data-stu-id="97b03-142">Returns true when reference value contained</span></span> |
|             |              | <span data-ttu-id="97b03-143">in einer Sammlung</span><span class="sxs-lookup"><span data-stu-id="97b03-143">in a collection</span></span>                             |
|             | <span data-ttu-id="97b03-144">-notcontains</span><span class="sxs-lookup"><span data-stu-id="97b03-144">-notcontains</span></span> | <span data-ttu-id="97b03-145">Gibt true zurück, wenn der Verweis Wert nicht</span><span class="sxs-lookup"><span data-stu-id="97b03-145">Returns true when reference value not</span></span>       |
|             |              | <span data-ttu-id="97b03-146">in einer Auflistung enthalten</span><span class="sxs-lookup"><span data-stu-id="97b03-146">contained in a collection</span></span>                   |
|             | <span data-ttu-id="97b03-147">-in</span><span class="sxs-lookup"><span data-stu-id="97b03-147">-in</span></span>          | <span data-ttu-id="97b03-148">Gibt true zurück, wenn der Testwert in einer</span><span class="sxs-lookup"><span data-stu-id="97b03-148">Returns true when test value contained in a</span></span> |
|             |              | <span data-ttu-id="97b03-149">collection</span><span class="sxs-lookup"><span data-stu-id="97b03-149">collection</span></span>                                  |
|             | <span data-ttu-id="97b03-150">-NOTIN</span><span class="sxs-lookup"><span data-stu-id="97b03-150">-notin</span></span>       | <span data-ttu-id="97b03-151">Gibt true zurück, wenn der Testwert nicht enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="97b03-151">Returns true when test value not contained</span></span>  |
|             |              | <span data-ttu-id="97b03-152">in einer Sammlung</span><span class="sxs-lookup"><span data-stu-id="97b03-152">in a collection</span></span>                             |
|             |              |                                             |
| <span data-ttu-id="97b03-153">Ersetzung</span><span class="sxs-lookup"><span data-stu-id="97b03-153">Replacement</span></span> | <span data-ttu-id="97b03-154">-Replace</span><span class="sxs-lookup"><span data-stu-id="97b03-154">-replace</span></span>     | <span data-ttu-id="97b03-155">Ersetzt ein Zeichen folgen Muster</span><span class="sxs-lookup"><span data-stu-id="97b03-155">Replaces a string pattern</span></span>                   |
|             |              |                                             |
| <span data-ttu-id="97b03-156">type</span><span class="sxs-lookup"><span data-stu-id="97b03-156">Type</span></span>        | <span data-ttu-id="97b03-157">-ist</span><span class="sxs-lookup"><span data-stu-id="97b03-157">-is</span></span>          | <span data-ttu-id="97b03-158">Gibt "true" zurück, wenn beide Objekte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="97b03-158">Returns true if both object are the same</span></span>    |
|             |              | <span data-ttu-id="97b03-159">type</span><span class="sxs-lookup"><span data-stu-id="97b03-159">type</span></span>                                        |
|             | <span data-ttu-id="97b03-160">-IsNot</span><span class="sxs-lookup"><span data-stu-id="97b03-160">-isnot</span></span>       | <span data-ttu-id="97b03-161">Gibt "true" zurück, wenn die Objekte nicht gleich sind.</span><span class="sxs-lookup"><span data-stu-id="97b03-161">Returns true if the objects are not the same</span></span>|
|             |              | <span data-ttu-id="97b03-162">type</span><span class="sxs-lookup"><span data-stu-id="97b03-162">type</span></span>                                        |

<span data-ttu-id="97b03-163">Standardmäßig wird bei allen Vergleichs Operatoren die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="97b03-163">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="97b03-164">Um bei einem Vergleichs Operator die Groß-/Kleinschreibung zu beachten, stellen Sie dem Operator Namen eine vor `c` .</span><span class="sxs-lookup"><span data-stu-id="97b03-164">To make a comparison operator case-sensitive, precede the operator name with a `c`.</span></span> <span data-ttu-id="97b03-165">Beispielsweise ist die Version von mit Beachtung der Groß-/Kleinschreibung `-eq` `-ceq` .</span><span class="sxs-lookup"><span data-stu-id="97b03-165">For example, the case-sensitive version of `-eq` is `-ceq`.</span></span> <span data-ttu-id="97b03-166">Um die Groß-/Kleinschreibung explizit explizit zu machen, stellen Sie dem-Operator eine vor `i` .</span><span class="sxs-lookup"><span data-stu-id="97b03-166">To make the case-insensitivity explicit, precede the operator with an `i`.</span></span> <span data-ttu-id="97b03-167">Beispielsweise ist die Version von, bei der die Groß-/Kleinschreibung nicht beachtet `-eq` wird `-ieq`</span><span class="sxs-lookup"><span data-stu-id="97b03-167">For example, the explicitly case-insensitive version of `-eq` is `-ieq`.</span></span>

<span data-ttu-id="97b03-168">Wenn die Eingabe für einen Operator ein skalarer Wert ist, geben Vergleichs Operatoren einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="97b03-168">When the input to an operator is a scalar value, comparison operators return a Boolean value.</span></span> <span data-ttu-id="97b03-169">Wenn die Eingabe eine Auflistung von Werten ist, geben die Vergleichs Operatoren alle übereinstimmenden Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="97b03-169">When the input is a collection of values, the comparison operators return any matching values.</span></span> <span data-ttu-id="97b03-170">Wenn keine Übereinstimmungen in einer Auflistung vorhanden sind, geben Vergleichs Operatoren ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="97b03-170">If there are no matches in a collection, comparison operators return an empty array.</span></span>

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

<span data-ttu-id="97b03-171">Die Ausnahmen sind die Containment-Operatoren, die in-Operatoren und die Typoperatoren, die immer einen **booleschen** Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="97b03-171">The exceptions are the containment operators, the In operators, and the type operators, which always return a **Boolean** value.</span></span>

> [!NOTE]
> <span data-ttu-id="97b03-172">Wenn Sie einen Wert mit vergleichen müssen, `$null` sollten Sie `$null` auf der linken Seite des Vergleichs platzieren.</span><span class="sxs-lookup"><span data-stu-id="97b03-172">If you need to compare a value to `$null` you should put `$null` on the left-hand side of the comparison.</span></span> <span data-ttu-id="97b03-173">Wenn Sie `$null` mit einem **Objekt []** vergleichen, ist das Ergebnis " **false** ", da das Vergleichs Objekt ein Array ist.</span><span class="sxs-lookup"><span data-stu-id="97b03-173">When you compare `$null` to an **Object[]** the result is **False** because the comparison object is an array.</span></span> <span data-ttu-id="97b03-174">Wenn Sie ein Array mit vergleichen `$null` , filtert der Vergleich alle `$null` im Array gespeicherten Werte heraus.</span><span class="sxs-lookup"><span data-stu-id="97b03-174">When you compare an array to `$null`, the comparison filters out any `$null` values stored in the array.</span></span> <span data-ttu-id="97b03-175">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97b03-175">For example:</span></span>
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

## <a name="equality-operators"></a><span data-ttu-id="97b03-176">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="97b03-176">Equality operators</span></span>

<span data-ttu-id="97b03-177">Die Gleichheits Operatoren ( `-eq` , `-ne` ) geben den Wert true oder die Übereinstimmungen zurück, wenn mindestens ein Eingabe Wert mit dem angegebenen Muster identisch ist.</span><span class="sxs-lookup"><span data-stu-id="97b03-177">The equality operators (`-eq`, `-ne`) return a value of TRUE or the matches when one or more of the input values is identical to the specified pattern.</span></span> <span data-ttu-id="97b03-178">Das gesamte Muster muss mit einem ganzen Wert identisch sein.</span><span class="sxs-lookup"><span data-stu-id="97b03-178">The entire pattern must match an entire value.</span></span>

<span data-ttu-id="97b03-179">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97b03-179">Example:</span></span>

### <a name="-eq"></a><span data-ttu-id="97b03-180">-eq</span><span class="sxs-lookup"><span data-stu-id="97b03-180">-eq</span></span>

<span data-ttu-id="97b03-181">Description: entspricht.</span><span class="sxs-lookup"><span data-stu-id="97b03-181">Description: Equal to.</span></span> <span data-ttu-id="97b03-182">Schließt einen identischen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="97b03-182">Includes an identical value.</span></span>

<span data-ttu-id="97b03-183">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97b03-183">Example:</span></span>

```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2
PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```

### <a name="-ne"></a><span data-ttu-id="97b03-184">-ne</span><span class="sxs-lookup"><span data-stu-id="97b03-184">-ne</span></span>

<span data-ttu-id="97b03-185">Description: nicht gleich.</span><span class="sxs-lookup"><span data-stu-id="97b03-185">Description: Not equal to.</span></span> <span data-ttu-id="97b03-186">Enthält einen anderen Wert.</span><span class="sxs-lookup"><span data-stu-id="97b03-186">Includes a different value.</span></span>

<span data-ttu-id="97b03-187">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97b03-187">Example:</span></span>

```powershell
PS> "abc" -ne "def"
True

PS> "abc" -ne "abc"
False

PS> "abc" -ne "abc", "def"
True

PS> "abc", "def" -ne "abc"
def
```

### <a name="-gt"></a><span data-ttu-id="97b03-188">-gt</span><span class="sxs-lookup"><span data-stu-id="97b03-188">-gt</span></span>

<span data-ttu-id="97b03-189">Beschreibung: größer als.</span><span class="sxs-lookup"><span data-stu-id="97b03-189">Description: Greater-than.</span></span>

<span data-ttu-id="97b03-190">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97b03-190">Example:</span></span>

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> <span data-ttu-id="97b03-191">Dies sollte nicht mit `>` dem Operator "größer als" in vielen anderen Programmiersprachen verwechselt werden.</span><span class="sxs-lookup"><span data-stu-id="97b03-191">This should not to be confused with `>`, the greater-than operator in many other programming languages.</span></span> <span data-ttu-id="97b03-192">In PowerShell `>` wird für die Umleitung verwendet.</span><span class="sxs-lookup"><span data-stu-id="97b03-192">In PowerShell, `>` is used for redirection.</span></span> <span data-ttu-id="97b03-193">Weitere Informationen finden Sie unter [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span><span class="sxs-lookup"><span data-stu-id="97b03-193">For more information, see [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span></span>

### <a name="-ge"></a><span data-ttu-id="97b03-194">-ge</span><span class="sxs-lookup"><span data-stu-id="97b03-194">-ge</span></span>

<span data-ttu-id="97b03-195">Description: größer als oder gleich.</span><span class="sxs-lookup"><span data-stu-id="97b03-195">Description: Greater-than or equal to.</span></span>

<span data-ttu-id="97b03-196">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97b03-196">Example:</span></span>

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

### <a name="-lt"></a><span data-ttu-id="97b03-197">-lt</span><span class="sxs-lookup"><span data-stu-id="97b03-197">-lt</span></span>

<span data-ttu-id="97b03-198">Beschreibung: kleiner als.</span><span class="sxs-lookup"><span data-stu-id="97b03-198">Description: Less-than.</span></span>

<span data-ttu-id="97b03-199">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97b03-199">Example:</span></span>

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

### <a name="-le"></a><span data-ttu-id="97b03-200">-le</span><span class="sxs-lookup"><span data-stu-id="97b03-200">-le</span></span>

<span data-ttu-id="97b03-201">Description: kleiner als oder gleich.</span><span class="sxs-lookup"><span data-stu-id="97b03-201">Description: Less-than or equal to.</span></span>

<span data-ttu-id="97b03-202">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97b03-202">Example:</span></span>

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

## <a name="matching-operators"></a><span data-ttu-id="97b03-203">Vergleichs Operatoren</span><span class="sxs-lookup"><span data-stu-id="97b03-203">Matching operators</span></span>

<span data-ttu-id="97b03-204">Die LIKE-Operatoren ( `-like` und `-notlike` ) suchen nach Elementen, die einem angegebenen Muster unter Verwendung von Platzhalter Ausdrücken entsprechen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="97b03-204">The like operators (`-like` and `-notlike`) find elements that match or do not match a specified pattern using wildcard expressions.</span></span>

<span data-ttu-id="97b03-205">Die Syntax ist:</span><span class="sxs-lookup"><span data-stu-id="97b03-205">The syntax is:</span></span>

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

<span data-ttu-id="97b03-206">Die Vergleichs Operatoren ( `-match` und `-notmatch` ) suchen nach Elementen, die einem angegebenen Muster entsprechen oder nicht mit regulären Ausdrücken identisch sind.</span><span class="sxs-lookup"><span data-stu-id="97b03-206">The match operators (`-match` and `-notmatch`) find elements that match or do not match a specified pattern using regular expressions.</span></span>

<span data-ttu-id="97b03-207">Die Match-Operatoren füllen die `$Matches` Automatische Variable auf, wenn die Eingabe (das linke Argument) für den Operator ein einzelnes skalares Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="97b03-207">The match operators populate the `$Matches` automatic variable when the input (the left-side argument) to the operator is a single scalar object.</span></span> <span data-ttu-id="97b03-208">Wenn die Eingabe Skalar ist, `-match` geben die `-notmatch` Operatoren und einen booleschen Wert zurück und legen den Wert der `$Matches` automatischen Variablen auf die übereinstimmenden Komponenten des Arguments fest.</span><span class="sxs-lookup"><span data-stu-id="97b03-208">When the input is scalar, the `-match` and `-notmatch` operators return a Boolean value and set the value of the `$Matches` automatic variable to the matched components of the argument.</span></span>

<span data-ttu-id="97b03-209">Die Syntax ist:</span><span class="sxs-lookup"><span data-stu-id="97b03-209">The syntax is:</span></span>

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

### <a name="-like"></a><span data-ttu-id="97b03-210">-like</span><span class="sxs-lookup"><span data-stu-id="97b03-210">-like</span></span>

<span data-ttu-id="97b03-211">Description: Match mit dem Platzhalter Zeichen ( \* ).</span><span class="sxs-lookup"><span data-stu-id="97b03-211">Description: Match using the wildcard character (\*).</span></span>

<span data-ttu-id="97b03-212">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97b03-212">Example:</span></span>

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

### <a name="-notlike"></a><span data-ttu-id="97b03-213">-notlike</span><span class="sxs-lookup"><span data-stu-id="97b03-213">-notlike</span></span>

<span data-ttu-id="97b03-214">Beschreibung: entspricht nicht der Verwendung des Platzhalter Zeichens ( \* ).</span><span class="sxs-lookup"><span data-stu-id="97b03-214">Description: Does not match using the wildcard character (\*).</span></span>

<span data-ttu-id="97b03-215">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97b03-215">Example:</span></span>

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a><span data-ttu-id="97b03-216">-match</span><span class="sxs-lookup"><span data-stu-id="97b03-216">-match</span></span>

<span data-ttu-id="97b03-217">Description: entspricht einer Zeichenfolge unter Verwendung regulärer Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="97b03-217">Description: Matches a string using regular expressions.</span></span> <span data-ttu-id="97b03-218">Wenn die Eingabe Skalar ist, füllt Sie die `$Matches` Automatische Variable auf.</span><span class="sxs-lookup"><span data-stu-id="97b03-218">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="97b03-219">Wenn es sich bei der Eingabe um eine Auflistung handelt, `-match` `-notmatch` geben die Operatoren und die übereinstimmenden Member dieser Auflistung zurück, aber der Operator füllt nicht die `$Matches` Variable auf.</span><span class="sxs-lookup"><span data-stu-id="97b03-219">If the input is a collection, the `-match` and `-notmatch` operators return the matching members of that collection, but the operator does not populate the `$Matches` variable.</span></span>

<span data-ttu-id="97b03-220">Der folgende Befehl übermittelt z. b. eine Auflistung von Zeichen folgen an den- `-match` Operator.</span><span class="sxs-lookup"><span data-stu-id="97b03-220">For example, the following command submits a collection of strings to the `-match` operator.</span></span> <span data-ttu-id="97b03-221">Der- `-match` Operator gibt die Elemente in der Auflistung zurück, die mit identisch sind.</span><span class="sxs-lookup"><span data-stu-id="97b03-221">The `-match` operator returns the items in the collection that match.</span></span> <span data-ttu-id="97b03-222">Die automatische Variable wird nicht aufgefüllt `$Matches` .</span><span class="sxs-lookup"><span data-stu-id="97b03-222">It does not populate the `$Matches` automatic variable.</span></span>

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

<span data-ttu-id="97b03-223">Im Gegensatz dazu übermittelt der folgende Befehl eine einzelne Zeichenfolge an den- `-match` Operator.</span><span class="sxs-lookup"><span data-stu-id="97b03-223">In contrast, the following command submits a single string to the `-match` operator.</span></span> <span data-ttu-id="97b03-224">Der `-match` -Operator gibt einen booleschen Wert zurück und füllt die `$Matches` Automatische Variable auf.</span><span class="sxs-lookup"><span data-stu-id="97b03-224">The `-match` operator returns a Boolean value and populates the `$Matches` automatic variable.</span></span> <span data-ttu-id="97b03-225">Die `$Matches` Automatische Variable ist eine **Hash Tabelle**.</span><span class="sxs-lookup"><span data-stu-id="97b03-225">The `$Matches` automatic variable is a **Hashtable**.</span></span> <span data-ttu-id="97b03-226">Wenn keine Gruppierung oder Erfassung verwendet wird, wird nur ein Schlüssel aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="97b03-226">If no grouping or capturing is used, only one key is populated.</span></span>
<span data-ttu-id="97b03-227">Der `0` Schlüssel stellt den gesamten Text dar, der abgeglichen wurde.</span><span class="sxs-lookup"><span data-stu-id="97b03-227">The `0` key represents all text that was matched.</span></span> <span data-ttu-id="97b03-228">Weitere Informationen zum Gruppieren und erfassen mithilfe regulärer Ausdrücke finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="97b03-228">For more information about grouping and capturing using regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

<span data-ttu-id="97b03-229">Beachten Sie unbedingt, dass die `$Matches` Hash Tabelle nur das erste Vorkommen eines übereinstimmenden Musters enthält.</span><span class="sxs-lookup"><span data-stu-id="97b03-229">It is important to note that the `$Matches` hashtable will only contain the first occurrence of any matching pattern.</span></span>

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> <span data-ttu-id="97b03-230">Der `0` Schlüssel ist eine **ganze** Zahl.</span><span class="sxs-lookup"><span data-stu-id="97b03-230">The `0` key is an **Integer**.</span></span> <span data-ttu-id="97b03-231">Sie können eine beliebige **Hash Tabellen** Methode verwenden, um auf den gespeicherten Wert zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="97b03-231">You can use any **Hashtable** method to access the value stored.</span></span>
>
> ```powershell
> PS> "Good Dog" -match "Dog"
> True
>
> PS> $Matches[0]
> Dog
>
> PS> $Matches.Item(0)
> Dog
>
> PS> $Matches.0
> Dog
> ```

<span data-ttu-id="97b03-232">Der `-notmatch` Operator füllt die `$Matches` Automatische Variable auf, wenn die Eingabe Skalar ist, und das Ergebnis ist false, d. h., wenn eine Entsprechung erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="97b03-232">The `-notmatch` operator populates the `$Matches` automatic variable when the input is scalar and the result is False, that it, when it detects a match.</span></span>

```powershell
PS> "Sunday" -notmatch "rain"
True

PS> $matches
PS>

PS> "Sunday" -notmatch "day"
False

PS> $matches

Name                           Value
----                           -----
0                              day
```

### <a name="-notmatch"></a><span data-ttu-id="97b03-233">-notmatch</span><span class="sxs-lookup"><span data-stu-id="97b03-233">-notmatch</span></span>

<span data-ttu-id="97b03-234">Beschreibung: stimmt nicht mit einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="97b03-234">Description: Does not match a string.</span></span> <span data-ttu-id="97b03-235">Verwendet reguläre Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="97b03-235">Uses regular expressions.</span></span> <span data-ttu-id="97b03-236">Wenn die Eingabe Skalar ist, füllt Sie die `$Matches` Automatische Variable auf.</span><span class="sxs-lookup"><span data-stu-id="97b03-236">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="97b03-237">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97b03-237">Example:</span></span>

```powershell
PS> "Sunday" -notmatch "sun"
False

PS> $matches
Name Value
---- -----
0    sun

PS> "Sunday", "Monday" -notmatch "sun"
Monday
```

## <a name="containment-operators"></a><span data-ttu-id="97b03-238">Containment-Operatoren</span><span class="sxs-lookup"><span data-stu-id="97b03-238">Containment operators</span></span>

<span data-ttu-id="97b03-239">Die Containment-Operatoren ( `-contains` und `-notcontains` ) ähneln den Gleichheits Operatoren.</span><span class="sxs-lookup"><span data-stu-id="97b03-239">The containment operators (`-contains` and `-notcontains`) are similar to the equality operators.</span></span> <span data-ttu-id="97b03-240">Der Containment-Operator gibt jedoch immer einen booleschen Wert zurück, auch wenn die Eingabe eine Auflistung ist.</span><span class="sxs-lookup"><span data-stu-id="97b03-240">However, the containment operators always return a Boolean value, even when the input is a collection.</span></span>

<span data-ttu-id="97b03-241">Außerdem geben die Einschluss Operatoren im Gegensatz zu den Gleichheits Operatoren einen Wert zurück, sobald Sie die erste Übereinstimmung erkennen.</span><span class="sxs-lookup"><span data-stu-id="97b03-241">Also, unlike the equality operators, the containment operators return a value as soon as they detect the first match.</span></span> <span data-ttu-id="97b03-242">Die Gleichheits Operatoren Werten alle Eingaben aus und geben dann alle Übereinstimmungen in der Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="97b03-242">The equality operators evaluate all input and then return all the matches in the collection.</span></span>

### <a name="-contains"></a><span data-ttu-id="97b03-243">-contains</span><span class="sxs-lookup"><span data-stu-id="97b03-243">-contains</span></span>

<span data-ttu-id="97b03-244">Description: Containment-Operator.</span><span class="sxs-lookup"><span data-stu-id="97b03-244">Description: Containment operator.</span></span> <span data-ttu-id="97b03-245">Gibt an, ob eine Auflistung von Verweis Werten einen einzelnen Testwert enthält.</span><span class="sxs-lookup"><span data-stu-id="97b03-245">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="97b03-246">Gibt immer einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="97b03-246">Always returns a Boolean value.</span></span> <span data-ttu-id="97b03-247">Gibt nur dann true zurück, wenn der Testwert genau mit mindestens einem der Verweis Werte übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="97b03-247">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="97b03-248">Wenn der Testwert eine Auflistung ist, verwendet der enthält-Operator Verweis Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="97b03-248">When the test value is a collection, the Contains operator uses reference equality.</span></span> <span data-ttu-id="97b03-249">Sie gibt nur dann true zurück, wenn einer der Verweis Werte dieselbe Instanz des Test Wert Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="97b03-249">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="97b03-250">In einer sehr großen Auflistung gibt der `-contains` Operator Ergebnisse schneller zurück, als der Operator gleich ist.</span><span class="sxs-lookup"><span data-stu-id="97b03-250">In a very large collection, the `-contains` operator returns results quicker than the equal to operator.</span></span>

<span data-ttu-id="97b03-251">Syntax:</span><span class="sxs-lookup"><span data-stu-id="97b03-251">Syntax:</span></span>

`<Reference-values> -contains <Test-value>`

<span data-ttu-id="97b03-252">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="97b03-252">Examples:</span></span>

```powershell
PS> "abc", "def" -contains "def"
True

PS> "Windows", "PowerShell" -contains "Shell"
False  #Not an exact match

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $DomainServers -contains $thisComputer
True

PS> "abc", "def", "ghi" -contains "abc", "def"
False

PS> $a = "abc", "def"
PS> "abc", "def", "ghi" -contains $a
False
PS> $a, "ghi" -contains $a
True
```

### <a name="-notcontains"></a><span data-ttu-id="97b03-253">-notcontains</span><span class="sxs-lookup"><span data-stu-id="97b03-253">-notcontains</span></span>

<span data-ttu-id="97b03-254">Description: Containment-Operator.</span><span class="sxs-lookup"><span data-stu-id="97b03-254">Description: Containment operator.</span></span> <span data-ttu-id="97b03-255">Gibt an, ob eine Auflistung von Verweis Werten einen einzelnen Testwert enthält.</span><span class="sxs-lookup"><span data-stu-id="97b03-255">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="97b03-256">Gibt immer einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="97b03-256">Always returns a Boolean value.</span></span> <span data-ttu-id="97b03-257">Gibt true zurück, wenn der Testwert keine exakten Übereinstimmungen für mindestens einen der Verweis Werte ist.</span><span class="sxs-lookup"><span data-stu-id="97b03-257">Returns TRUE when the test value is not an exact matches for at least one of the reference values.</span></span>

<span data-ttu-id="97b03-258">Wenn der Testwert eine Auflistung ist, verwendet der Notare-Operator Verweis Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="97b03-258">When the test value is a collection, the NotContains operator uses reference equality.</span></span>

<span data-ttu-id="97b03-259">Syntax:</span><span class="sxs-lookup"><span data-stu-id="97b03-259">Syntax:</span></span>

`<Reference-values> -notcontains <Test-value>`

<span data-ttu-id="97b03-260">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="97b03-260">Examples:</span></span>

```powershell
PS> "Windows", "PowerShell" -notcontains "Shell"
True  #Not an exact match

# Get cmdlet parameters, but exclude common parameters
function get-parms ($cmdlet)
{
    $Common = "Verbose", "Debug", "WarningAction", "WarningVariable",
      "ErrorAction", "ErrorVariable", "OutVariable", "OutBuffer"

    $allparms = (Get-Command $Cmdlet).parametersets |
      foreach {$_.Parameters} |
        foreach {$_.Name} | Sort-Object | Get-Unique

    $allparms | where {$Common -notcontains $_ }
}

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $myVerbs = Get-Command -Module MyModule | foreach {$_.verb}
PS> $myVerbs | where {$ApprovedVerbs -notcontains $_}
ForEach
Sort
Tee
Where
```

### <a name="-in"></a><span data-ttu-id="97b03-261">-in</span><span class="sxs-lookup"><span data-stu-id="97b03-261">-in</span></span>

<span data-ttu-id="97b03-262">Description: in-Operator.</span><span class="sxs-lookup"><span data-stu-id="97b03-262">Description: In operator.</span></span> <span data-ttu-id="97b03-263">Gibt an, ob ein Testwert in einer Auflistung von Verweis Werten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="97b03-263">Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="97b03-264">Gibt immer als booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="97b03-264">Always return as Boolean value.</span></span> <span data-ttu-id="97b03-265">Gibt nur dann true zurück, wenn der Testwert genau mit mindestens einem der Verweis Werte übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="97b03-265">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="97b03-266">Wenn der Testwert eine Auflistung ist, verwendet der in-Operator Verweis Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="97b03-266">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="97b03-267">Sie gibt nur dann true zurück, wenn einer der Verweis Werte dieselbe Instanz des Test Wert Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="97b03-267">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="97b03-268">Der `-in` Operator wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="97b03-268">The `-in` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="97b03-269">Syntax:</span><span class="sxs-lookup"><span data-stu-id="97b03-269">Syntax:</span></span>

`<Test-value> -in <Reference-values>`

<span data-ttu-id="97b03-270">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="97b03-270">Examples:</span></span>

```powershell
PS> "def" -in "abc", "def"
True

PS> "Shell" -in "Windows", "PowerShell"
False  #Not an exact match

PS> "Windows" -in "Windows", "PowerShell"
True  #An exact match

PS> "Windows", "PowerShell" -in "Windows", "PowerShell", "ServerManager"
False  #Using reference equality

PS> $a = "Windows", "PowerShell"
PS> $a -in $a, "ServerManager"
True  #Using reference equality

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $thisComputer -in  $domainServers
True
```

### <a name="-notin"></a><span data-ttu-id="97b03-271">-NOTIN</span><span class="sxs-lookup"><span data-stu-id="97b03-271">-notin</span></span>

<span data-ttu-id="97b03-272">Description: gibt an, ob ein Testwert in einer Auflistung von Verweis Werten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="97b03-272">Description: Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="97b03-273">Gibt immer einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="97b03-273">Always returns a Boolean value.</span></span> <span data-ttu-id="97b03-274">Gibt true zurück, wenn der Testwert keine genaue Entsprechung für mindestens einen der Verweis Werte ist.</span><span class="sxs-lookup"><span data-stu-id="97b03-274">Returns TRUE when the test value is not an exact match for at least one of the reference values.</span></span>

<span data-ttu-id="97b03-275">Wenn der Testwert eine Auflistung ist, verwendet der in-Operator Verweis Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="97b03-275">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="97b03-276">Sie gibt nur dann true zurück, wenn einer der Verweis Werte dieselbe Instanz des Test Wert Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="97b03-276">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="97b03-277">Der `-notin` Operator wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="97b03-277">The `-notin` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="97b03-278">Syntax:</span><span class="sxs-lookup"><span data-stu-id="97b03-278">Syntax:</span></span>

`<Test-value> -notin <Reference-values>`

<span data-ttu-id="97b03-279">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="97b03-279">Examples:</span></span>

```powershell
PS> "def" -notin "abc", "def"
False

PS> "ghi" -notin "abc", "def"
True

PS> "Shell" -notin "Windows", "PowerShell"
True  #Not an exact match

PS> "Windows" -notin "Windows", "PowerShell"
False  #An exact match

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $MyVerbs = Get-Command -Module MyModule | foreach {$_.verb}

PS> $MyVerbs | where {$_ -notin $ApprovedVerbs}
ForEach
Sort
Tee
Where
```

## <a name="replacement-operator"></a><span data-ttu-id="97b03-280">Ersatz Operator</span><span class="sxs-lookup"><span data-stu-id="97b03-280">Replacement Operator</span></span>

<span data-ttu-id="97b03-281">Der- `-replace` Operator weist die folgende Syntax auf:</span><span class="sxs-lookup"><span data-stu-id="97b03-281">The `-replace` operator has the following syntax:</span></span>

`<input> -replace <original>, <substitute>`

<span data-ttu-id="97b03-282">Der `<original>` Platzhalter ist ein regulärer Ausdruck, der mit den zu ersetzenden Zeichen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="97b03-282">The `<original>` placeholder is a regular expression matching the characters to be replaced.</span></span> <span data-ttu-id="97b03-283">Der `<substitute>` Platzhalter ist eine Literalzeichenfolge, die Sie ersetzt.</span><span class="sxs-lookup"><span data-stu-id="97b03-283">The `<substitute>` placeholder is a literal string that replaces them.</span></span>

<span data-ttu-id="97b03-284">Der-Operator ersetzt den gesamten oder einen Teil eines Werts durch den angegebenen Wert mithilfe regulärer Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="97b03-284">The operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="97b03-285">Sie können den-Operator für viele Verwaltungsaufgaben verwenden, z. b. das Umbenennen von Dateien.</span><span class="sxs-lookup"><span data-stu-id="97b03-285">You can use the operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="97b03-286">Der folgende Befehl ändert z. b. die Dateinamen Erweiterungen aller `.txt` Dateien in `.log` :</span><span class="sxs-lookup"><span data-stu-id="97b03-286">For example, the following command changes the file name extensions of all `.txt` files to `.log`:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

### <a name="case-sensitive-matches"></a><span data-ttu-id="97b03-287">Übereinstimmungen mit Beachtung der groß-</span><span class="sxs-lookup"><span data-stu-id="97b03-287">Case-sensitive matches</span></span>

<span data-ttu-id="97b03-288">Standardmäßig `-replace` wird bei dem Operator die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="97b03-288">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="97b03-289">Verwenden Sie, um die Groß-/Kleinschreibung zu beachten `-creplace`</span><span class="sxs-lookup"><span data-stu-id="97b03-289">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="97b03-290">Verwenden Sie, um die Groß-/Kleinschreibung explizit zu Unternehmen `-ireplace` .</span><span class="sxs-lookup"><span data-stu-id="97b03-290">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="97b03-291">Betrachten Sie die folgenden Beispiele:</span><span class="sxs-lookup"><span data-stu-id="97b03-291">Consider the following examples:</span></span>

```powershell
PS> "book" -replace "B", "C"
Cook
```

```powershell
PS> "book" -ireplace "B", "C"
Cook
```

```powershell
PS> "book" -creplace "B", "C"
book
```

### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="97b03-292">Ersetzungen in regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="97b03-292">Substitutions in regular expressions</span></span>

<span data-ttu-id="97b03-293">Es ist auch möglich, reguläre Ausdrücke zum dynamischen Ersetzen von Text mithilfe von Erfassungs Gruppen und Ersetzungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="97b03-293">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="97b03-294">Auf Erfassungs Gruppen kann in der `<substitute>` Zeichenfolge mit dem Dollarzeichen ( `$` ) vor der Gruppen Kennung verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="97b03-294">Capture groups can be referenced in the `<substitute>` string using the dollar sign (`$`) character before the group identifier.</span></span>

<span data-ttu-id="97b03-295">Auf Erfassungs Gruppen kann nach **Nummer** oder **Name** verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="97b03-295">Capture groups can be referenced by **Number** or **Name**</span></span>

- <span data-ttu-id="97b03-296">Nach **Zahlen** Erfassungs Gruppen werden von links nach rechts nummeriert.</span><span class="sxs-lookup"><span data-stu-id="97b03-296">By **Number** - Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  PS> "John D. Smith" -replace "(\w+) (\w+)\. (\w+)", '$1.$2.$3@contoso.com'
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="97b03-297">Nach **Namen** können auch nach Namen Erfassungs Gruppen verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="97b03-297">By **Name** - Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  PS> "CONTOSO\Administrator" -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  FABRIKAM\Administrator
  ```

> [!WARNING]
> <span data-ttu-id="97b03-298">Da das `$` Zeichen bei der Zeichen folgen Erweiterung verwendet wird, müssen Sie Literalzeichenfolgen oder das `$` Zeichen mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="97b03-298">Since the `$` character is used in string expansion, you must use literal strings or escape the `$` character.</span></span>
>
> ```powershell
> PS> 'Hello World' -replace '(\w+) \w+', "`$1 Universe"
> Hello Universe
> ```
>
> <span data-ttu-id="97b03-299">Da das `$` Zeichen in der Ersetzung verwendet wird, müssen Sie außerdem alle Instanzen in der Zeichenfolge mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="97b03-299">Additionally, since the `$` character is used in substitution, you must escape any instances in your string.</span></span>
>
> ```powershell
> PS> '5.72' -replace '(.+)', '$$$1'
> $5.72
> ```

<span data-ttu-id="97b03-300">Weitere Informationen finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md) und Ersetzungen [in regulären Ausdrücken](/dotnet/standard/base-types/substitutions-in-regular-expressions) .</span><span class="sxs-lookup"><span data-stu-id="97b03-300">To learn more see [about_Regular_Expressions](about_Regular_Expressions.md) and [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions)</span></span>

### <a name="substituting-in-a-collection"></a><span data-ttu-id="97b03-301">Ersetzen in einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="97b03-301">Substituting in a collection</span></span>

<span data-ttu-id="97b03-302">Wenn der `<input>` für den `-replace` Operator eine Auflistung ist, wendet PowerShell die Ersetzung auf jeden Wert in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="97b03-302">When the `<input>` to the `-replace` operator is a collection, PowerShell applies the replacement to every value in the collection.</span></span> <span data-ttu-id="97b03-303">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97b03-303">For example:</span></span>

```powershell
"B1","B2","B3","B4","B5" -replace "B", 'a'
a1
a2
a3
a4
a5
```

## <a name="type-comparison"></a><span data-ttu-id="97b03-304">Typvergleich</span><span class="sxs-lookup"><span data-stu-id="97b03-304">Type comparison</span></span>

<span data-ttu-id="97b03-305">Die typvergleichs Operatoren ( `-is` und `-isnot` ) werden verwendet, um zu bestimmen, ob es sich bei einem Objekt um einen bestimmten Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="97b03-305">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

### <a name="-is"></a><span data-ttu-id="97b03-306">-ist</span><span class="sxs-lookup"><span data-stu-id="97b03-306">-is</span></span>

<span data-ttu-id="97b03-307">Syntax:</span><span class="sxs-lookup"><span data-stu-id="97b03-307">Syntax:</span></span>

`<object> -is <type reference>`

<span data-ttu-id="97b03-308">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97b03-308">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

### <a name="-isnot"></a><span data-ttu-id="97b03-309">-IsNot</span><span class="sxs-lookup"><span data-stu-id="97b03-309">-isnot</span></span>

<span data-ttu-id="97b03-310">Syntax:</span><span class="sxs-lookup"><span data-stu-id="97b03-310">Syntax:</span></span>

`<object> -isnot <type reference>`

<span data-ttu-id="97b03-311">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97b03-311">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a><span data-ttu-id="97b03-312">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97b03-312">See also</span></span>

- [<span data-ttu-id="97b03-313">about_Operators</span><span class="sxs-lookup"><span data-stu-id="97b03-313">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="97b03-314">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="97b03-314">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="97b03-315">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="97b03-315">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="97b03-316">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="97b03-316">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="97b03-317">ForEach-Objekt</span><span class="sxs-lookup"><span data-stu-id="97b03-317">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="97b03-318">Where-Object</span><span class="sxs-lookup"><span data-stu-id="97b03-318">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
