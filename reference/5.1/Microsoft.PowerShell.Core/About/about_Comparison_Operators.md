---
description: Beschreibt die Operatoren, die Werte in PowerShell vergleichen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: b6076e20ad3ecbe9f2def157bb20bdb3bee5b7ad
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224532"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="2106a-104">Informationen zu Vergleichs Operatoren</span><span class="sxs-lookup"><span data-stu-id="2106a-104">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="2106a-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2106a-105">Short description</span></span>
<span data-ttu-id="2106a-106">Beschreibt die Operatoren, die Werte in PowerShell vergleichen.</span><span class="sxs-lookup"><span data-stu-id="2106a-106">Describes the operators that compare values in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="2106a-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2106a-107">Long description</span></span>

<span data-ttu-id="2106a-108">Mit Vergleichs Operatoren können Sie Bedingungen zum Vergleichen von Werten und suchen von Werten angeben, die den angegebenen Mustern entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2106a-108">Comparison operators let you specify conditions for comparing values and finding values that match specified patterns.</span></span> <span data-ttu-id="2106a-109">Wenn Sie einen Vergleichs Operator verwenden möchten, geben Sie die Werte, die Sie miteinander vergleichen möchten, mit einem Operator an, der diese Werte trennt.</span><span class="sxs-lookup"><span data-stu-id="2106a-109">To use a comparison operator, specify the values that you want to compare together with an operator that separates these values.</span></span>

<span data-ttu-id="2106a-110">PowerShell umfasst die folgenden Vergleichs Operatoren:</span><span class="sxs-lookup"><span data-stu-id="2106a-110">PowerShell includes the following comparison operators:</span></span>

| <span data-ttu-id="2106a-111">type</span><span class="sxs-lookup"><span data-stu-id="2106a-111">Type</span></span>        | <span data-ttu-id="2106a-112">Operatoren</span><span class="sxs-lookup"><span data-stu-id="2106a-112">Operators</span></span>    | <span data-ttu-id="2106a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2106a-113">Description</span></span>                                 |
| ----------- | ------------ | --------------------------------------------|
| <span data-ttu-id="2106a-114">Gleichheit</span><span class="sxs-lookup"><span data-stu-id="2106a-114">Equality</span></span>    | <span data-ttu-id="2106a-115">-eq</span><span class="sxs-lookup"><span data-stu-id="2106a-115">-eq</span></span>          | <span data-ttu-id="2106a-116">Ist gleich</span><span class="sxs-lookup"><span data-stu-id="2106a-116">equals</span></span>                                      |
|             | <span data-ttu-id="2106a-117">-ne</span><span class="sxs-lookup"><span data-stu-id="2106a-117">-ne</span></span>          | <span data-ttu-id="2106a-118">ungleich</span><span class="sxs-lookup"><span data-stu-id="2106a-118">not equals</span></span>                                  |
|             | <span data-ttu-id="2106a-119">-gt</span><span class="sxs-lookup"><span data-stu-id="2106a-119">-gt</span></span>          | <span data-ttu-id="2106a-120">Größer als</span><span class="sxs-lookup"><span data-stu-id="2106a-120">greater than</span></span>                                |
|             | <span data-ttu-id="2106a-121">-ge</span><span class="sxs-lookup"><span data-stu-id="2106a-121">-ge</span></span>          | <span data-ttu-id="2106a-122">Größer als oder gleich</span><span class="sxs-lookup"><span data-stu-id="2106a-122">greater than or equal</span></span>                       |
|             | <span data-ttu-id="2106a-123">-lt</span><span class="sxs-lookup"><span data-stu-id="2106a-123">-lt</span></span>          | <span data-ttu-id="2106a-124">Kleiner als</span><span class="sxs-lookup"><span data-stu-id="2106a-124">less than</span></span>                                   |
|             | <span data-ttu-id="2106a-125">-le</span><span class="sxs-lookup"><span data-stu-id="2106a-125">-le</span></span>          | <span data-ttu-id="2106a-126">Kleiner als oder gleich</span><span class="sxs-lookup"><span data-stu-id="2106a-126">less than or equal</span></span>                          |
|             |              |                                             |
| <span data-ttu-id="2106a-127">Matching</span><span class="sxs-lookup"><span data-stu-id="2106a-127">Matching</span></span>    | <span data-ttu-id="2106a-128">-like</span><span class="sxs-lookup"><span data-stu-id="2106a-128">-like</span></span>        | <span data-ttu-id="2106a-129">Gibt "true" zurück, wenn die Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2106a-129">Returns true when string matches wildcard</span></span>   |
|             |              | <span data-ttu-id="2106a-130">pattern</span><span class="sxs-lookup"><span data-stu-id="2106a-130">pattern</span></span>                                     |
|             | <span data-ttu-id="2106a-131">-notlike</span><span class="sxs-lookup"><span data-stu-id="2106a-131">-notlike</span></span>     | <span data-ttu-id="2106a-132">Gibt true zurück, wenn die Zeichenfolge nicht entspricht.</span><span class="sxs-lookup"><span data-stu-id="2106a-132">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="2106a-133">Platzhalter Muster</span><span class="sxs-lookup"><span data-stu-id="2106a-133">wildcard pattern</span></span>                            |
|             | <span data-ttu-id="2106a-134">-match</span><span class="sxs-lookup"><span data-stu-id="2106a-134">-match</span></span>       | <span data-ttu-id="2106a-135">Gibt true zurück, wenn die Zeichenfolge dem regulären Ausdruck entspricht</span><span class="sxs-lookup"><span data-stu-id="2106a-135">Returns true when string matches regex</span></span>      |
|             |              | <span data-ttu-id="2106a-136">Bau $Matches enthält übereinstimmende Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="2106a-136">pattern; $matches contains matching strings</span></span> |
|             | <span data-ttu-id="2106a-137">-notmatch</span><span class="sxs-lookup"><span data-stu-id="2106a-137">-notmatch</span></span>    | <span data-ttu-id="2106a-138">Gibt true zurück, wenn die Zeichenfolge nicht entspricht.</span><span class="sxs-lookup"><span data-stu-id="2106a-138">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="2106a-139">Regex-Muster; $Matches enthält Übereinstimmungen.</span><span class="sxs-lookup"><span data-stu-id="2106a-139">regex pattern; $matches contains matching</span></span>   |
|             |              | <span data-ttu-id="2106a-140">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="2106a-140">strings</span></span>                                     |
|             |              |                                             |
| <span data-ttu-id="2106a-141">Containment</span><span class="sxs-lookup"><span data-stu-id="2106a-141">Containment</span></span> | <span data-ttu-id="2106a-142">-contains</span><span class="sxs-lookup"><span data-stu-id="2106a-142">-contains</span></span>    | <span data-ttu-id="2106a-143">Gibt true zurück, wenn der Verweis Wert enthalten ist</span><span class="sxs-lookup"><span data-stu-id="2106a-143">Returns true when reference value contained</span></span> |
|             |              | <span data-ttu-id="2106a-144">in einer Sammlung</span><span class="sxs-lookup"><span data-stu-id="2106a-144">in a collection</span></span>                             |
|             | <span data-ttu-id="2106a-145">-notcontains</span><span class="sxs-lookup"><span data-stu-id="2106a-145">-notcontains</span></span> | <span data-ttu-id="2106a-146">Gibt true zurück, wenn der Verweis Wert nicht</span><span class="sxs-lookup"><span data-stu-id="2106a-146">Returns true when reference value not</span></span>       |
|             |              | <span data-ttu-id="2106a-147">in einer Auflistung enthalten</span><span class="sxs-lookup"><span data-stu-id="2106a-147">contained in a collection</span></span>                   |
|             | <span data-ttu-id="2106a-148">-in</span><span class="sxs-lookup"><span data-stu-id="2106a-148">-in</span></span>          | <span data-ttu-id="2106a-149">Gibt true zurück, wenn der Testwert in einer</span><span class="sxs-lookup"><span data-stu-id="2106a-149">Returns true when test value contained in a</span></span> |
|             |              | <span data-ttu-id="2106a-150">collection</span><span class="sxs-lookup"><span data-stu-id="2106a-150">collection</span></span>                                  |
|             | <span data-ttu-id="2106a-151">-NOTIN</span><span class="sxs-lookup"><span data-stu-id="2106a-151">-notin</span></span>       | <span data-ttu-id="2106a-152">Gibt true zurück, wenn der Testwert nicht enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="2106a-152">Returns true when test value not contained</span></span>  |
|             |              | <span data-ttu-id="2106a-153">in einer Sammlung</span><span class="sxs-lookup"><span data-stu-id="2106a-153">in a collection</span></span>                             |
|             |              |                                             |
| <span data-ttu-id="2106a-154">Ersetzung</span><span class="sxs-lookup"><span data-stu-id="2106a-154">Replacement</span></span> | <span data-ttu-id="2106a-155">-Replace</span><span class="sxs-lookup"><span data-stu-id="2106a-155">-replace</span></span>     | <span data-ttu-id="2106a-156">Ersetzt ein Zeichen folgen Muster</span><span class="sxs-lookup"><span data-stu-id="2106a-156">Replaces a string pattern</span></span>                   |
|             |              |                                             |
| <span data-ttu-id="2106a-157">type</span><span class="sxs-lookup"><span data-stu-id="2106a-157">Type</span></span>        | <span data-ttu-id="2106a-158">-ist</span><span class="sxs-lookup"><span data-stu-id="2106a-158">-is</span></span>          | <span data-ttu-id="2106a-159">Gibt "true" zurück, wenn beide Objekte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="2106a-159">Returns true if both object are the same</span></span>    |
|             |              | <span data-ttu-id="2106a-160">type</span><span class="sxs-lookup"><span data-stu-id="2106a-160">type</span></span>                                        |
|             | <span data-ttu-id="2106a-161">-IsNot</span><span class="sxs-lookup"><span data-stu-id="2106a-161">-isnot</span></span>       | <span data-ttu-id="2106a-162">Gibt "true" zurück, wenn die Objekte nicht gleich sind.</span><span class="sxs-lookup"><span data-stu-id="2106a-162">Returns true if the objects are not the same</span></span>|
|             |              | <span data-ttu-id="2106a-163">type</span><span class="sxs-lookup"><span data-stu-id="2106a-163">type</span></span>                                        |

<span data-ttu-id="2106a-164">Standardmäßig wird bei allen Vergleichs Operatoren die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="2106a-164">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="2106a-165">Um bei einem Vergleichs Operator die Groß-/Kleinschreibung zu beachten, stellen Sie dem Operator Namen eine vor `c` .</span><span class="sxs-lookup"><span data-stu-id="2106a-165">To make a comparison operator case-sensitive, precede the operator name with a `c`.</span></span> <span data-ttu-id="2106a-166">Beispielsweise ist die Version von mit Beachtung der Groß-/Kleinschreibung `-eq` `-ceq` .</span><span class="sxs-lookup"><span data-stu-id="2106a-166">For example, the case-sensitive version of `-eq` is `-ceq`.</span></span> <span data-ttu-id="2106a-167">Um die Groß-/Kleinschreibung explizit explizit zu machen, stellen Sie dem-Operator eine vor `i` .</span><span class="sxs-lookup"><span data-stu-id="2106a-167">To make the case-insensitivity explicit, precede the operator with an `i`.</span></span> <span data-ttu-id="2106a-168">Beispielsweise ist die Version von, bei der die Groß-/Kleinschreibung nicht beachtet `-eq` wird `-ieq`</span><span class="sxs-lookup"><span data-stu-id="2106a-168">For example, the explicitly case-insensitive version of `-eq` is `-ieq`.</span></span>

<span data-ttu-id="2106a-169">Wenn die Eingabe für einen Operator ein skalarer Wert ist, geben Vergleichs Operatoren einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="2106a-169">When the input to an operator is a scalar value, comparison operators return a Boolean value.</span></span> <span data-ttu-id="2106a-170">Wenn die Eingabe eine Auflistung von Werten ist, geben die Vergleichs Operatoren alle übereinstimmenden Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="2106a-170">When the input is a collection of values, the comparison operators return any matching values.</span></span> <span data-ttu-id="2106a-171">Wenn keine Übereinstimmungen in einer Auflistung vorhanden sind, geben Vergleichs Operatoren ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="2106a-171">If there are no matches in a collection, comparison operators return an empty array.</span></span>

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

<span data-ttu-id="2106a-172">Die Ausnahmen sind die Containment-Operatoren, die in-Operatoren und die Typoperatoren, die immer einen **booleschen** Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="2106a-172">The exceptions are the containment operators, the In operators, and the type operators, which always return a **Boolean** value.</span></span>

> [!NOTE]
> <span data-ttu-id="2106a-173">Wenn Sie einen Wert mit vergleichen müssen, `$null` sollten Sie `$null` auf der linken Seite des Vergleichs platzieren.</span><span class="sxs-lookup"><span data-stu-id="2106a-173">If you need to compare a value to `$null` you should put `$null` on the left-hand side of the comparison.</span></span> <span data-ttu-id="2106a-174">Wenn Sie `$null` mit einem **Objekt []** vergleichen, ist das Ergebnis " **false** ", da das Vergleichs Objekt ein Array ist.</span><span class="sxs-lookup"><span data-stu-id="2106a-174">When you compare `$null` to an **Object[]** the result is **False** because the comparison object is an array.</span></span> <span data-ttu-id="2106a-175">Wenn Sie ein Array mit vergleichen `$null` , filtert der Vergleich alle `$null` im Array gespeicherten Werte heraus.</span><span class="sxs-lookup"><span data-stu-id="2106a-175">When you compare an array to `$null`, the comparison filters out any `$null` values stored in the array.</span></span> <span data-ttu-id="2106a-176">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2106a-176">For example:</span></span>
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

### <a name="equality-operators"></a><span data-ttu-id="2106a-177">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="2106a-177">Equality Operators</span></span>

<span data-ttu-id="2106a-178">Die Gleichheits Operatoren ( `-eq` , `-ne` ) geben den Wert true oder die Übereinstimmungen zurück, wenn mindestens ein Eingabe Wert mit dem angegebenen Muster identisch ist.</span><span class="sxs-lookup"><span data-stu-id="2106a-178">The equality operators (`-eq`, `-ne`) return a value of TRUE or the matches when one or more of the input values is identical to the specified pattern.</span></span> <span data-ttu-id="2106a-179">Das gesamte Muster muss mit einem ganzen Wert identisch sein.</span><span class="sxs-lookup"><span data-stu-id="2106a-179">The entire pattern must match an entire value.</span></span>

<span data-ttu-id="2106a-180">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2106a-180">Example:</span></span>

#### <a name="-eq"></a><span data-ttu-id="2106a-181">-eq</span><span class="sxs-lookup"><span data-stu-id="2106a-181">-eq</span></span>

<span data-ttu-id="2106a-182">Description: entspricht.</span><span class="sxs-lookup"><span data-stu-id="2106a-182">Description: Equal to.</span></span> <span data-ttu-id="2106a-183">Schließt einen identischen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="2106a-183">Includes an identical value.</span></span>

<span data-ttu-id="2106a-184">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2106a-184">Example:</span></span>

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

#### <a name="-ne"></a><span data-ttu-id="2106a-185">-ne</span><span class="sxs-lookup"><span data-stu-id="2106a-185">-ne</span></span>

<span data-ttu-id="2106a-186">Description: nicht gleich.</span><span class="sxs-lookup"><span data-stu-id="2106a-186">Description: Not equal to.</span></span> <span data-ttu-id="2106a-187">Enthält einen anderen Wert.</span><span class="sxs-lookup"><span data-stu-id="2106a-187">Includes a different value.</span></span>

<span data-ttu-id="2106a-188">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2106a-188">Example:</span></span>

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

#### <a name="-gt"></a><span data-ttu-id="2106a-189">-gt</span><span class="sxs-lookup"><span data-stu-id="2106a-189">-gt</span></span>

<span data-ttu-id="2106a-190">Beschreibung: größer als.</span><span class="sxs-lookup"><span data-stu-id="2106a-190">Description: Greater-than.</span></span>

<span data-ttu-id="2106a-191">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2106a-191">Example:</span></span>

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> <span data-ttu-id="2106a-192">Dies sollte nicht mit `>` dem Operator "größer als" in vielen anderen Programmiersprachen verwechselt werden.</span><span class="sxs-lookup"><span data-stu-id="2106a-192">This should not to be confused with `>`, the greater-than operator in many other programming languages.</span></span> <span data-ttu-id="2106a-193">In PowerShell `>` wird für die Umleitung verwendet.</span><span class="sxs-lookup"><span data-stu-id="2106a-193">In PowerShell, `>` is used for redirection.</span></span> <span data-ttu-id="2106a-194">Weitere Informationen finden Sie unter [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span><span class="sxs-lookup"><span data-stu-id="2106a-194">For more information, see [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span></span>

#### <a name="-ge"></a><span data-ttu-id="2106a-195">-ge</span><span class="sxs-lookup"><span data-stu-id="2106a-195">-ge</span></span>

<span data-ttu-id="2106a-196">Description: größer als oder gleich.</span><span class="sxs-lookup"><span data-stu-id="2106a-196">Description: Greater-than or equal to.</span></span>

<span data-ttu-id="2106a-197">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2106a-197">Example:</span></span>

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

#### <a name="-lt"></a><span data-ttu-id="2106a-198">-lt</span><span class="sxs-lookup"><span data-stu-id="2106a-198">-lt</span></span>

<span data-ttu-id="2106a-199">Beschreibung: kleiner als.</span><span class="sxs-lookup"><span data-stu-id="2106a-199">Description: Less-than.</span></span>

<span data-ttu-id="2106a-200">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2106a-200">Example:</span></span>

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

#### <a name="-le"></a><span data-ttu-id="2106a-201">-le</span><span class="sxs-lookup"><span data-stu-id="2106a-201">-le</span></span>

<span data-ttu-id="2106a-202">Description: kleiner als oder gleich.</span><span class="sxs-lookup"><span data-stu-id="2106a-202">Description: Less-than or equal to.</span></span>

<span data-ttu-id="2106a-203">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2106a-203">Example:</span></span>

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

### <a name="matching-operators"></a><span data-ttu-id="2106a-204">Vergleichs Operatoren</span><span class="sxs-lookup"><span data-stu-id="2106a-204">Matching Operators</span></span>

<span data-ttu-id="2106a-205">Die LIKE-Operatoren ( `-like` und `-notlike` ) suchen nach Elementen, die einem angegebenen Muster unter Verwendung von Platzhalter Ausdrücken entsprechen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="2106a-205">The like operators (`-like` and `-notlike`) find elements that match or do not match a specified pattern using wildcard expressions.</span></span>

<span data-ttu-id="2106a-206">Die Syntax ist:</span><span class="sxs-lookup"><span data-stu-id="2106a-206">The syntax is:</span></span>

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

<span data-ttu-id="2106a-207">Die Vergleichs Operatoren ( `-match` und `-notmatch` ) suchen nach Elementen, die einem angegebenen Muster entsprechen oder nicht mit regulären Ausdrücken identisch sind.</span><span class="sxs-lookup"><span data-stu-id="2106a-207">The match operators (`-match` and `-notmatch`) find elements that match or do not match a specified pattern using regular expressions.</span></span>

<span data-ttu-id="2106a-208">Die Match-Operatoren füllen die `$Matches` Automatische Variable auf, wenn die Eingabe (das linke Argument) für den Operator ein einzelnes skalares Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="2106a-208">The match operators populate the `$Matches` automatic variable when the input (the left-side argument) to the operator is a single scalar object.</span></span> <span data-ttu-id="2106a-209">Wenn die Eingabe Skalar ist, `-match` geben die `-notmatch` Operatoren und einen booleschen Wert zurück und legen den Wert der `$Matches` automatischen Variablen auf die übereinstimmenden Komponenten des Arguments fest.</span><span class="sxs-lookup"><span data-stu-id="2106a-209">When the input is scalar, the `-match` and `-notmatch` operators return a Boolean value and set the value of the `$Matches` automatic variable to the matched components of the argument.</span></span>

<span data-ttu-id="2106a-210">Die Syntax ist:</span><span class="sxs-lookup"><span data-stu-id="2106a-210">The syntax is:</span></span>

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

#### <a name="-like"></a><span data-ttu-id="2106a-211">-like</span><span class="sxs-lookup"><span data-stu-id="2106a-211">-like</span></span>

<span data-ttu-id="2106a-212">Description: Match mit dem Platzhalter Zeichen ( \* ).</span><span class="sxs-lookup"><span data-stu-id="2106a-212">Description: Match using the wildcard character (\*).</span></span>

<span data-ttu-id="2106a-213">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2106a-213">Example:</span></span>

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

#### <a name="-notlike"></a><span data-ttu-id="2106a-214">-notlike</span><span class="sxs-lookup"><span data-stu-id="2106a-214">-notlike</span></span>

<span data-ttu-id="2106a-215">Beschreibung: entspricht nicht der Verwendung des Platzhalter Zeichens ( \* ).</span><span class="sxs-lookup"><span data-stu-id="2106a-215">Description: Does not match using the wildcard character (\*).</span></span>

<span data-ttu-id="2106a-216">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2106a-216">Example:</span></span>

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a><span data-ttu-id="2106a-217">-match</span><span class="sxs-lookup"><span data-stu-id="2106a-217">-match</span></span>

<span data-ttu-id="2106a-218">Description: entspricht einer Zeichenfolge unter Verwendung regulärer Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="2106a-218">Description: Matches a string using regular expressions.</span></span> <span data-ttu-id="2106a-219">Wenn die Eingabe Skalar ist, füllt Sie die `$Matches` Automatische Variable auf.</span><span class="sxs-lookup"><span data-stu-id="2106a-219">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="2106a-220">Wenn es sich bei der Eingabe um eine Auflistung handelt, `-match` `-notmatch` geben die Operatoren und die übereinstimmenden Member dieser Auflistung zurück, aber der Operator füllt nicht die `$Matches` Variable auf.</span><span class="sxs-lookup"><span data-stu-id="2106a-220">If the input is a collection, the `-match` and `-notmatch` operators return the matching members of that collection, but the operator does not populate the `$Matches` variable.</span></span>

<span data-ttu-id="2106a-221">Der folgende Befehl übermittelt z. b. eine Auflistung von Zeichen folgen an den- `-match` Operator.</span><span class="sxs-lookup"><span data-stu-id="2106a-221">For example, the following command submits a collection of strings to the `-match` operator.</span></span> <span data-ttu-id="2106a-222">Der- `-match` Operator gibt die Elemente in der Auflistung zurück, die mit identisch sind.</span><span class="sxs-lookup"><span data-stu-id="2106a-222">The `-match` operator returns the items in the collection that match.</span></span> <span data-ttu-id="2106a-223">Die automatische Variable wird nicht aufgefüllt `$Matches` .</span><span class="sxs-lookup"><span data-stu-id="2106a-223">It does not populate the `$Matches` automatic variable.</span></span>

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

<span data-ttu-id="2106a-224">Im Gegensatz dazu übermittelt der folgende Befehl eine einzelne Zeichenfolge an den- `-match` Operator.</span><span class="sxs-lookup"><span data-stu-id="2106a-224">In contrast, the following command submits a single string to the `-match` operator.</span></span> <span data-ttu-id="2106a-225">Der `-match` -Operator gibt einen booleschen Wert zurück und füllt die `$Matches` Automatische Variable auf.</span><span class="sxs-lookup"><span data-stu-id="2106a-225">The `-match` operator returns a Boolean value and populates the `$Matches` automatic variable.</span></span> <span data-ttu-id="2106a-226">Die `$Matches` Automatische Variable ist eine **Hash Tabelle**.</span><span class="sxs-lookup"><span data-stu-id="2106a-226">The `$Matches` automatic variable is a **Hashtable**.</span></span> <span data-ttu-id="2106a-227">Wenn keine Gruppierung oder Erfassung verwendet wird, wird nur ein Schlüssel aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="2106a-227">If no grouping or capturing is used, only one key is populated.</span></span>
<span data-ttu-id="2106a-228">Der `0` Schlüssel stellt den gesamten Text dar, der abgeglichen wurde.</span><span class="sxs-lookup"><span data-stu-id="2106a-228">The `0` key represents all text that was matched.</span></span> <span data-ttu-id="2106a-229">Weitere Informationen zum Gruppieren und erfassen mithilfe regulärer Ausdrücke finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2106a-229">For more information about grouping and capturing using regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

<span data-ttu-id="2106a-230">Beachten Sie unbedingt, dass die `$Matches` Hash Tabelle nur das erste Vorkommen eines übereinstimmenden Musters enthält.</span><span class="sxs-lookup"><span data-stu-id="2106a-230">It is important to note that the `$Matches` hashtable will only contain the first occurrence of any matching pattern.</span></span>

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> <span data-ttu-id="2106a-231">Der `0` Schlüssel ist eine **ganze** Zahl.</span><span class="sxs-lookup"><span data-stu-id="2106a-231">The `0` key is an **Integer**.</span></span> <span data-ttu-id="2106a-232">Sie können eine beliebige **Hash Tabellen** Methode verwenden, um auf den gespeicherten Wert zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="2106a-232">You can use any **Hashtable** method to access the value stored.</span></span>
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

<span data-ttu-id="2106a-233">Der `-notmatch` Operator füllt die `$Matches` Automatische Variable auf, wenn die Eingabe Skalar ist, und das Ergebnis ist false, d. h., wenn eine Entsprechung erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="2106a-233">The `-notmatch` operator populates the `$Matches` automatic variable when the input is scalar and the result is False, that it, when it detects a match.</span></span>

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

#### <a name="-notmatch"></a><span data-ttu-id="2106a-234">-notmatch</span><span class="sxs-lookup"><span data-stu-id="2106a-234">-notmatch</span></span>

<span data-ttu-id="2106a-235">Beschreibung: stimmt nicht mit einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2106a-235">Description: Does not match a string.</span></span> <span data-ttu-id="2106a-236">Verwendet reguläre Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="2106a-236">Uses regular expressions.</span></span> <span data-ttu-id="2106a-237">Wenn die Eingabe Skalar ist, füllt Sie die `$Matches` Automatische Variable auf.</span><span class="sxs-lookup"><span data-stu-id="2106a-237">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="2106a-238">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2106a-238">Example:</span></span>

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

### <a name="containment-operators"></a><span data-ttu-id="2106a-239">Containment-Operatoren</span><span class="sxs-lookup"><span data-stu-id="2106a-239">Containment Operators</span></span>

<span data-ttu-id="2106a-240">Die Containment-Operatoren ( `-contains` und `-notcontains` ) ähneln den Gleichheits Operatoren.</span><span class="sxs-lookup"><span data-stu-id="2106a-240">The containment operators (`-contains` and `-notcontains`) are similar to the equality operators.</span></span> <span data-ttu-id="2106a-241">Der Containment-Operator gibt jedoch immer einen booleschen Wert zurück, auch wenn die Eingabe eine Auflistung ist.</span><span class="sxs-lookup"><span data-stu-id="2106a-241">However, the containment operators always return a Boolean value, even when the input is a collection.</span></span>

<span data-ttu-id="2106a-242">Außerdem geben die Einschluss Operatoren im Gegensatz zu den Gleichheits Operatoren einen Wert zurück, sobald Sie die erste Übereinstimmung erkennen.</span><span class="sxs-lookup"><span data-stu-id="2106a-242">Also, unlike the equality operators, the containment operators return a value as soon as they detect the first match.</span></span> <span data-ttu-id="2106a-243">Die Gleichheits Operatoren Werten alle Eingaben aus und geben dann alle Übereinstimmungen in der Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="2106a-243">The equality operators evaluate all input and then return all the matches in the collection.</span></span>

#### <a name="-contains"></a><span data-ttu-id="2106a-244">-contains</span><span class="sxs-lookup"><span data-stu-id="2106a-244">-contains</span></span>

<span data-ttu-id="2106a-245">Description: Containment-Operator.</span><span class="sxs-lookup"><span data-stu-id="2106a-245">Description: Containment operator.</span></span> <span data-ttu-id="2106a-246">Gibt an, ob eine Auflistung von Verweis Werten einen einzelnen Testwert enthält.</span><span class="sxs-lookup"><span data-stu-id="2106a-246">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="2106a-247">Gibt immer einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="2106a-247">Always returns a Boolean value.</span></span> <span data-ttu-id="2106a-248">Gibt nur dann true zurück, wenn der Testwert genau mit mindestens einem der Verweis Werte übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="2106a-248">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="2106a-249">Wenn der Testwert eine Auflistung ist, verwendet der enthält-Operator Verweis Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="2106a-249">When the test value is a collection, the Contains operator uses reference equality.</span></span> <span data-ttu-id="2106a-250">Sie gibt nur dann true zurück, wenn einer der Verweis Werte dieselbe Instanz des Test Wert Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="2106a-250">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="2106a-251">In einer sehr großen Auflistung gibt der `-contains` Operator Ergebnisse schneller zurück, als der Operator gleich ist.</span><span class="sxs-lookup"><span data-stu-id="2106a-251">In a very large collection, the `-contains` operator returns results quicker than the equal to operator.</span></span>

<span data-ttu-id="2106a-252">Syntax:</span><span class="sxs-lookup"><span data-stu-id="2106a-252">Syntax:</span></span>

`<Reference-values> -contains <Test-value>`

<span data-ttu-id="2106a-253">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2106a-253">Examples:</span></span>

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

#### <a name="-notcontains"></a><span data-ttu-id="2106a-254">-notcontains</span><span class="sxs-lookup"><span data-stu-id="2106a-254">-notcontains</span></span>

<span data-ttu-id="2106a-255">Description: Containment-Operator.</span><span class="sxs-lookup"><span data-stu-id="2106a-255">Description: Containment operator.</span></span> <span data-ttu-id="2106a-256">Gibt an, ob eine Auflistung von Verweis Werten einen einzelnen Testwert enthält.</span><span class="sxs-lookup"><span data-stu-id="2106a-256">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="2106a-257">Gibt immer einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="2106a-257">Always returns a Boolean value.</span></span> <span data-ttu-id="2106a-258">Gibt true zurück, wenn der Testwert keine exakten Übereinstimmungen für mindestens einen der Verweis Werte ist.</span><span class="sxs-lookup"><span data-stu-id="2106a-258">Returns TRUE when the test value is not an exact matches for at least one of the reference values.</span></span>

<span data-ttu-id="2106a-259">Wenn der Testwert eine Auflistung ist, verwendet der Notare-Operator Verweis Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="2106a-259">When the test value is a collection, the NotContains operator uses reference equality.</span></span>

<span data-ttu-id="2106a-260">Syntax:</span><span class="sxs-lookup"><span data-stu-id="2106a-260">Syntax:</span></span>

`<Reference-values> -notcontains <Test-value>`

<span data-ttu-id="2106a-261">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2106a-261">Examples:</span></span>

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

#### <a name="-in"></a><span data-ttu-id="2106a-262">-in</span><span class="sxs-lookup"><span data-stu-id="2106a-262">-in</span></span>

<span data-ttu-id="2106a-263">Description: in-Operator.</span><span class="sxs-lookup"><span data-stu-id="2106a-263">Description: In operator.</span></span> <span data-ttu-id="2106a-264">Gibt an, ob ein Testwert in einer Auflistung von Verweis Werten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2106a-264">Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="2106a-265">Gibt immer als booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="2106a-265">Always return as Boolean value.</span></span> <span data-ttu-id="2106a-266">Gibt nur dann true zurück, wenn der Testwert genau mit mindestens einem der Verweis Werte übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="2106a-266">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="2106a-267">Wenn der Testwert eine Auflistung ist, verwendet der in-Operator Verweis Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="2106a-267">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="2106a-268">Sie gibt nur dann true zurück, wenn einer der Verweis Werte dieselbe Instanz des Test Wert Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="2106a-268">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="2106a-269">Der `-in` Operator wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2106a-269">The `-in` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="2106a-270">Syntax:</span><span class="sxs-lookup"><span data-stu-id="2106a-270">Syntax:</span></span>

`<Test-value> -in <Reference-values>`

<span data-ttu-id="2106a-271">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2106a-271">Examples:</span></span>

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

#### <a name="-notin"></a><span data-ttu-id="2106a-272">-NOTIN</span><span class="sxs-lookup"><span data-stu-id="2106a-272">-notin</span></span>

<span data-ttu-id="2106a-273">Description: gibt an, ob ein Testwert in einer Auflistung von Verweis Werten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2106a-273">Description: Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="2106a-274">Gibt immer einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="2106a-274">Always returns a Boolean value.</span></span> <span data-ttu-id="2106a-275">Gibt true zurück, wenn der Testwert keine genaue Entsprechung für mindestens einen der Verweis Werte ist.</span><span class="sxs-lookup"><span data-stu-id="2106a-275">Returns TRUE when the test value is not an exact match for at least one of the reference values.</span></span>

<span data-ttu-id="2106a-276">Wenn der Testwert eine Auflistung ist, verwendet der in-Operator Verweis Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="2106a-276">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="2106a-277">Sie gibt nur dann true zurück, wenn einer der Verweis Werte dieselbe Instanz des Test Wert Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="2106a-277">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="2106a-278">Der `-notin` Operator wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2106a-278">The `-notin` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="2106a-279">Syntax:</span><span class="sxs-lookup"><span data-stu-id="2106a-279">Syntax:</span></span>

`<Test-value> -notin <Reference-values>`

<span data-ttu-id="2106a-280">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2106a-280">Examples:</span></span>

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

### <a name="replacement-operator"></a><span data-ttu-id="2106a-281">Ersatz Operator</span><span class="sxs-lookup"><span data-stu-id="2106a-281">Replacement Operator</span></span>

<span data-ttu-id="2106a-282">Der- `-replace` Operator ersetzt den gesamten oder einen Teil eines Werts durch den angegebenen Wert mithilfe regulärer Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="2106a-282">The `-replace` operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="2106a-283">Sie können den- `-replace` Operator für viele Verwaltungsaufgaben verwenden, z. b. das Umbenennen von Dateien.</span><span class="sxs-lookup"><span data-stu-id="2106a-283">You can use the `-replace` operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="2106a-284">Der folgende Befehl ändert z. b. die Dateinamen Erweiterungen aller txt-Dateien in. log:</span><span class="sxs-lookup"><span data-stu-id="2106a-284">For example, the following command changes the file name extensions of all .txt files to .log:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

<span data-ttu-id="2106a-285">Die Syntax des- `-replace` Operators lautet wie folgt, wobei der `<original>` Platzhalter die zu ersetzenden Zeichen darstellt und der `<substitute>` Platzhalter die Zeichen darstellt, die Sie ersetzen:</span><span class="sxs-lookup"><span data-stu-id="2106a-285">The syntax of the `-replace` operator is as follows, where the `<original>` placeholder represents the characters to be replaced, and the `<substitute>` placeholder represents the characters that will replace them:</span></span>

`<input> <operator> <original>, <substitute>`

<span data-ttu-id="2106a-286">Standardmäßig `-replace` wird bei dem Operator die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="2106a-286">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="2106a-287">Verwenden Sie, um die Groß-/Kleinschreibung zu beachten `-creplace`</span><span class="sxs-lookup"><span data-stu-id="2106a-287">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="2106a-288">Verwenden Sie, um die Groß-/Kleinschreibung explizit zu Unternehmen `-ireplace` .</span><span class="sxs-lookup"><span data-stu-id="2106a-288">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="2106a-289">Betrachten Sie die folgenden Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2106a-289">Consider the following examples:</span></span>

```powershell
PS> "book" -replace "B", "C"
```

```Output
Cook
```

```powershell
"book" -ireplace "B", "C"
```

```Output
Cook
```

```powershell
"book" -creplace "B", "C"
```

```Output
book
```

<span data-ttu-id="2106a-290">Es ist auch möglich, reguläre Ausdrücke zum dynamischen Ersetzen von Text mithilfe von Erfassungs Gruppen und Ersetzungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2106a-290">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="2106a-291">Weitere Informationen finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2106a-291">For more information, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

#### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="2106a-292">Ersetzungen in regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="2106a-292">Substitutions in Regular Expressions</span></span>

<span data-ttu-id="2106a-293">Außerdem kann in der Zeichenfolge auf Erfassungs Gruppen verwiesen werden \<substitute\> .</span><span class="sxs-lookup"><span data-stu-id="2106a-293">Additionally, capturing groups can be referenced in the \<substitute\> string.</span></span>
<span data-ttu-id="2106a-294">Dies erfolgt mithilfe des `$` Zeichens vor dem Gruppen Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="2106a-294">This is done by using the `$` character before the group identifier.</span></span>

<span data-ttu-id="2106a-295">Zwei Möglichkeiten, auf Erfassungs Gruppen zu verweisen, sind nach **Nummer** und **Name** .</span><span class="sxs-lookup"><span data-stu-id="2106a-295">Two of the ways to reference capturing groups is by **Number** and by **Name**</span></span>

- <span data-ttu-id="2106a-296">Nach **Zahlen** -
   Erfassungs Gruppen werden von links nach rechts nummeriert.</span><span class="sxs-lookup"><span data-stu-id="2106a-296">By **Number** -
Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  "John D. Smith" -replace "(\w+) (\w+)\. (\w+)", '$1.$2.$3@contoso.com'
  ```

  ```Output
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="2106a-297">Nach **Namen** -
   können Sie auch nach Namen Erfassungs Gruppen referenziert werden.</span><span class="sxs-lookup"><span data-stu-id="2106a-297">By **Name** -
Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  "CONTOSO\Administrator" -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  ```

  ```Output
  FABRIKOM\Administrator
  ```

> [!WARNING]
> <span data-ttu-id="2106a-298">Da das `$` Zeichen bei der Zeichen folgen Erweiterung verwendet wird, müssen Sie Literalzeichenfolgen mit Ersetzung verwenden oder das `$` Zeichen mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="2106a-298">Since the `$` character is used in string expansion, you will need to use literal strings with substitution, or escape the `$` character.</span></span>
>
> ```powershell
> 'Hello World' -replace '(\w+) \w+', "`$1 Universe"
> ```
>
> ```Output
> Hello Universe
> ```
>
> <span data-ttu-id="2106a-299">Da das `$` Zeichen in der Ersetzung verwendet wird, müssen Sie außerdem alle Instanzen in der Zeichenfolge mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="2106a-299">Additionally, since the `$` character is used in substitution, you will need to escape any instances in your string.</span></span>
>
> ```powershell
> '5.72' -replace '(.+)', '$$$1'
> ```
>
> ```Output
> $5.72
> ```

<span data-ttu-id="2106a-300">Weitere Informationen finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md) und Ersetzungen [in regulären Ausdrücken](/dotnet/standard/base-types/substitutions-in-regular-expressions) .</span><span class="sxs-lookup"><span data-stu-id="2106a-300">To learn more see [about_Regular_Expressions](about_Regular_Expressions.md) and [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions)</span></span>

### <a name="type-comparison"></a><span data-ttu-id="2106a-301">Typvergleich</span><span class="sxs-lookup"><span data-stu-id="2106a-301">Type comparison</span></span>

<span data-ttu-id="2106a-302">Die typvergleichs Operatoren ( `-is` und `-isnot` ) werden verwendet, um zu bestimmen, ob es sich bei einem Objekt um einen bestimmten Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="2106a-302">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

#### <a name="-is"></a><span data-ttu-id="2106a-303">-ist</span><span class="sxs-lookup"><span data-stu-id="2106a-303">-is</span></span>

<span data-ttu-id="2106a-304">Syntax:</span><span class="sxs-lookup"><span data-stu-id="2106a-304">Syntax:</span></span>

`<object> -is <type reference>`

<span data-ttu-id="2106a-305">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2106a-305">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

#### <a name="-isnot"></a><span data-ttu-id="2106a-306">-IsNot</span><span class="sxs-lookup"><span data-stu-id="2106a-306">-isnot</span></span>

<span data-ttu-id="2106a-307">Syntax:</span><span class="sxs-lookup"><span data-stu-id="2106a-307">Syntax:</span></span>

`<object> -isnot <type reference>`

<span data-ttu-id="2106a-308">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2106a-308">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a><span data-ttu-id="2106a-309">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="2106a-309">SEE ALSO</span></span>

- [<span data-ttu-id="2106a-310">about_Operators</span><span class="sxs-lookup"><span data-stu-id="2106a-310">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="2106a-311">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="2106a-311">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="2106a-312">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="2106a-312">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="2106a-313">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="2106a-313">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="2106a-314">ForEach-Objekt</span><span class="sxs-lookup"><span data-stu-id="2106a-314">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="2106a-315">Where-Object</span><span class="sxs-lookup"><span data-stu-id="2106a-315">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
