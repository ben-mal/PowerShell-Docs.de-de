---
description: Beschreibt die Operatoren, die Werte in PowerShell vergleichen.
Locale: en-US
ms.date: 01/20/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: 179798b490855cd463e2348acaf1292f042ba173
ms.sourcegitcommit: 77f6225ab0c8ea9faa1fe46b2ea15c178ec170e3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2021
ms.locfileid: "100500158"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="9eefb-103">Informationen zu Vergleichs Operatoren</span><span class="sxs-lookup"><span data-stu-id="9eefb-103">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="9eefb-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9eefb-104">Short description</span></span>

<span data-ttu-id="9eefb-105">Die Vergleichs Operatoren in PowerShell können entweder zwei Werte vergleichen oder Elemente einer Auflistung mit einem Eingabe Wert filtern.</span><span class="sxs-lookup"><span data-stu-id="9eefb-105">The comparison operators in PowerShell can either compare two values or filter elements of a collection against an input value.</span></span>

## <a name="long-description"></a><span data-ttu-id="9eefb-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9eefb-106">Long description</span></span>

<span data-ttu-id="9eefb-107">Mit Vergleichs Operatoren können Sie Werte vergleichen oder Werte suchen, die den angegebenen Mustern entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9eefb-107">Comparison operators let you compare values or finding values that match specified patterns.</span></span> <span data-ttu-id="9eefb-108">PowerShell umfasst die folgenden Vergleichs Operatoren:</span><span class="sxs-lookup"><span data-stu-id="9eefb-108">PowerShell includes the following comparison operators:</span></span>

|    <span data-ttu-id="9eefb-109">Typ</span><span class="sxs-lookup"><span data-stu-id="9eefb-109">Type</span></span>     |   <span data-ttu-id="9eefb-110">Operator</span><span class="sxs-lookup"><span data-stu-id="9eefb-110">Operator</span></span>   |              <span data-ttu-id="9eefb-111">Vergleichstest</span><span class="sxs-lookup"><span data-stu-id="9eefb-111">Comparison test</span></span>              |
| ----------- | ------------ | ----------------------------------------- |
| <span data-ttu-id="9eefb-112">Gleichheit</span><span class="sxs-lookup"><span data-stu-id="9eefb-112">Equality</span></span>    | <span data-ttu-id="9eefb-113">-eq</span><span class="sxs-lookup"><span data-stu-id="9eefb-113">-eq</span></span>          | <span data-ttu-id="9eefb-114">equals</span><span class="sxs-lookup"><span data-stu-id="9eefb-114">equals</span></span>                                    |
|             | <span data-ttu-id="9eefb-115">-ne</span><span class="sxs-lookup"><span data-stu-id="9eefb-115">-ne</span></span>          | <span data-ttu-id="9eefb-116">ungleich</span><span class="sxs-lookup"><span data-stu-id="9eefb-116">not equals</span></span>                                |
|             | <span data-ttu-id="9eefb-117">-gt</span><span class="sxs-lookup"><span data-stu-id="9eefb-117">-gt</span></span>          | <span data-ttu-id="9eefb-118">Größer als</span><span class="sxs-lookup"><span data-stu-id="9eefb-118">greater than</span></span>                              |
|             | <span data-ttu-id="9eefb-119">-ge</span><span class="sxs-lookup"><span data-stu-id="9eefb-119">-ge</span></span>          | <span data-ttu-id="9eefb-120">Größer als oder gleich</span><span class="sxs-lookup"><span data-stu-id="9eefb-120">greater than or equal</span></span>                     |
|             | <span data-ttu-id="9eefb-121">-lt</span><span class="sxs-lookup"><span data-stu-id="9eefb-121">-lt</span></span>          | <span data-ttu-id="9eefb-122">Kleiner als</span><span class="sxs-lookup"><span data-stu-id="9eefb-122">less than</span></span>                                 |
|             | <span data-ttu-id="9eefb-123">-le</span><span class="sxs-lookup"><span data-stu-id="9eefb-123">-le</span></span>          | <span data-ttu-id="9eefb-124">Kleiner als oder gleich</span><span class="sxs-lookup"><span data-stu-id="9eefb-124">less than or equal</span></span>                        |
| <span data-ttu-id="9eefb-125">Matching</span><span class="sxs-lookup"><span data-stu-id="9eefb-125">Matching</span></span>    | <span data-ttu-id="9eefb-126">-like</span><span class="sxs-lookup"><span data-stu-id="9eefb-126">-like</span></span>        | <span data-ttu-id="9eefb-127">Zeichenfolge entspricht Platzhalter Muster</span><span class="sxs-lookup"><span data-stu-id="9eefb-127">string matches wildcard pattern</span></span>           |
|             | <span data-ttu-id="9eefb-128">-notlike</span><span class="sxs-lookup"><span data-stu-id="9eefb-128">-notlike</span></span>     | <span data-ttu-id="9eefb-129">Zeichenfolge entspricht nicht dem Platzhalter Muster</span><span class="sxs-lookup"><span data-stu-id="9eefb-129">string does not match wildcard pattern</span></span>    |
|             | <span data-ttu-id="9eefb-130">-match</span><span class="sxs-lookup"><span data-stu-id="9eefb-130">-match</span></span>       | <span data-ttu-id="9eefb-131">Zeichenfolge entspricht dem Regex-Muster</span><span class="sxs-lookup"><span data-stu-id="9eefb-131">string matches regex pattern</span></span>              |
|             | <span data-ttu-id="9eefb-132">-notmatch</span><span class="sxs-lookup"><span data-stu-id="9eefb-132">-notmatch</span></span>    | <span data-ttu-id="9eefb-133">die Zeichenfolge entspricht nicht dem Regex-Muster.</span><span class="sxs-lookup"><span data-stu-id="9eefb-133">string does not match regex pattern</span></span>       |
| <span data-ttu-id="9eefb-134">Ersatz</span><span class="sxs-lookup"><span data-stu-id="9eefb-134">Replacement</span></span> | <span data-ttu-id="9eefb-135">-Replace</span><span class="sxs-lookup"><span data-stu-id="9eefb-135">-replace</span></span>     | <span data-ttu-id="9eefb-136">ersetzt Zeichen folgen, die einem Regex-Muster entsprechen</span><span class="sxs-lookup"><span data-stu-id="9eefb-136">replaces strings matching a regex pattern</span></span> |
| <span data-ttu-id="9eefb-137">Containment</span><span class="sxs-lookup"><span data-stu-id="9eefb-137">Containment</span></span> | <span data-ttu-id="9eefb-138">-contains</span><span class="sxs-lookup"><span data-stu-id="9eefb-138">-contains</span></span>    | <span data-ttu-id="9eefb-139">die Sammlung enthält einen Wert.</span><span class="sxs-lookup"><span data-stu-id="9eefb-139">collection contains a value</span></span>               |
|             | <span data-ttu-id="9eefb-140">-notcontains</span><span class="sxs-lookup"><span data-stu-id="9eefb-140">-notcontains</span></span> | <span data-ttu-id="9eefb-141">die Sammlung enthält keinen Wert.</span><span class="sxs-lookup"><span data-stu-id="9eefb-141">collection does not contain a value</span></span>       |
|             | <span data-ttu-id="9eefb-142">-in</span><span class="sxs-lookup"><span data-stu-id="9eefb-142">-in</span></span>          | <span data-ttu-id="9eefb-143">Wert ist in einer Sammlung</span><span class="sxs-lookup"><span data-stu-id="9eefb-143">value is in a collection</span></span>                  |
|             | <span data-ttu-id="9eefb-144">-NOTIN</span><span class="sxs-lookup"><span data-stu-id="9eefb-144">-notin</span></span>       | <span data-ttu-id="9eefb-145">der Wert ist nicht in einer Sammlung.</span><span class="sxs-lookup"><span data-stu-id="9eefb-145">value is not in a collection</span></span>              |
| <span data-ttu-id="9eefb-146">type</span><span class="sxs-lookup"><span data-stu-id="9eefb-146">Type</span></span>        | <span data-ttu-id="9eefb-147">-ist</span><span class="sxs-lookup"><span data-stu-id="9eefb-147">-is</span></span>          | <span data-ttu-id="9eefb-148">beide Objekte weisen denselben Typ auf.</span><span class="sxs-lookup"><span data-stu-id="9eefb-148">both objects are the same type</span></span>            |
|             | <span data-ttu-id="9eefb-149">-IsNot</span><span class="sxs-lookup"><span data-stu-id="9eefb-149">-isnot</span></span>       | <span data-ttu-id="9eefb-150">die Objekte weisen nicht denselben Typ auf.</span><span class="sxs-lookup"><span data-stu-id="9eefb-150">the objects are not the same type</span></span>         |

## <a name="common-features"></a><span data-ttu-id="9eefb-151">Allgemeine Funktionen</span><span class="sxs-lookup"><span data-stu-id="9eefb-151">Common features</span></span>

<span data-ttu-id="9eefb-152">Standardmäßig wird bei allen Vergleichs Operatoren die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="9eefb-152">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="9eefb-153">Um die Groß-/Kleinschreibung für Vergleichs Operatoren zu erstellen, fügen Sie `c` nach dem ein `-` .</span><span class="sxs-lookup"><span data-stu-id="9eefb-153">To make a comparison operator case-sensitive, add a `c` after the `-`.</span></span> <span data-ttu-id="9eefb-154">Beispielsweise `-ceq` ist die Version von mit Beachtung der Groß-/Kleinschreibung `-eq` .</span><span class="sxs-lookup"><span data-stu-id="9eefb-154">For example, `-ceq` is the case-sensitive version of `-eq`.</span></span> <span data-ttu-id="9eefb-155">Um die Groß-/Kleinschreibung nicht explizit explizit zu gestalten, fügen Sie eine `i` vor hinzu `-` .</span><span class="sxs-lookup"><span data-stu-id="9eefb-155">To make the case-insensitivity explicit, add an `i` before `-`.</span></span> <span data-ttu-id="9eefb-156">Beispielsweise `-ieq` ist die explizite Version von ohne Beachtung der Groß-/Kleinschreibung `-eq` .</span><span class="sxs-lookup"><span data-stu-id="9eefb-156">For example, `-ieq` is the explicitly case-insensitive version of `-eq`.</span></span>

<span data-ttu-id="9eefb-157">Wenn die Eingabe eines Operators ein skalarer Wert ist, gibt der Operator einen **booleschen** Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="9eefb-157">When the input of an operator is a scalar value, the operator returns a **Boolean** value.</span></span> <span data-ttu-id="9eefb-158">Wenn die Eingabe eine Auflistung ist, gibt der Operator die Elemente der Auflistung zurück, die dem rechten Wert des Ausdrucks entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9eefb-158">When the input is a collection, the operator returns the elements of the collection that match the right-hand value of the expression.</span></span>
<span data-ttu-id="9eefb-159">Wenn in der Auflistung keine Übereinstimmungen vorhanden sind, geben Vergleichs Operatoren ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="9eefb-159">If there are no matches in the collection, comparison operators return an empty array.</span></span> <span data-ttu-id="9eefb-160">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9eefb-160">For example:</span></span>

```powershell
$a = (1, 2 -eq 3)
$a.GetType().Name
$a.Count
```

```output
Object[]
0
```

<span data-ttu-id="9eefb-161">Es gibt ein paar Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="9eefb-161">There are a few exceptions:</span></span>

- <span data-ttu-id="9eefb-162">Der Containment-und der Type-Operator geben immer einen **booleschen** Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="9eefb-162">The containment and type operators always return a **Boolean** value</span></span>
- <span data-ttu-id="9eefb-163">Der `-replace` Operator gibt das Ersetzungs Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="9eefb-163">The `-replace` operator returns the replacement result</span></span>
- <span data-ttu-id="9eefb-164">Die `-match` `-notmatch` Operatoren und füllen auch die `$Matches` Automatische Variable auf.</span><span class="sxs-lookup"><span data-stu-id="9eefb-164">The `-match` and `-notmatch` operators also populate the `$Matches` automatic variable</span></span>

## <a name="equality-operators"></a><span data-ttu-id="9eefb-165">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="9eefb-165">Equality operators</span></span>

### <a name="-eq-and--ne"></a><span data-ttu-id="9eefb-166">-eq und -ne</span><span class="sxs-lookup"><span data-stu-id="9eefb-166">-eq and -ne</span></span>

<span data-ttu-id="9eefb-167">Wenn die linke Seite Skalar ist, wird `-eq` **true** zurückgegeben, wenn die Rechte Seite eine genaue Entsprechung ist; andernfalls wird `-eq` **false** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9eefb-167">When the left-hand side is scalar, `-eq` returns **True** if the right-hand side is an exact match, otherwise, `-eq` returns **False**.</span></span> <span data-ttu-id="9eefb-168">`-ne` hat das Gegenteil. gibt **false** zurück, wenn beide Seiten einander entsprechen. Andernfalls wird `-ne` true zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9eefb-168">`-ne` does the opposite; it returns **False** when both sides match; otherwise, `-ne` returns True.</span></span>

<span data-ttu-id="9eefb-169">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9eefb-169">Example:</span></span>

```powershell
2 -eq 2                 # Output: True
2 -eq 3                 # Output: False
"abc" -eq "abc"         # Output: True
"abc" -eq "abc", "def"  # Output: False
"abc" -ne "def"         # Output: True
"abc" -ne "abc"         # Output: False
"abc" -ne "abc", "def"  # Output: True
```

<span data-ttu-id="9eefb-170">Wenn die linke Seite eine Auflistung ist, gibt die Elemente zurück, die `-eq` der rechten Seite entsprechen, während `-ne` Sie von herausgefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="9eefb-170">When the left-hand side is a collection, `-eq` returns those members that match the right-hand side, while `-ne` filters them out.</span></span>

<span data-ttu-id="9eefb-171">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9eefb-171">Example:</span></span>

```powershell
1,2,3 -eq 2             # Output: 2
"abc", "def" -eq "abc"  # Output: abc
"abc", "def" -ne "abc"  # Output: def
```

<span data-ttu-id="9eefb-172">Diese Operatoren verarbeiten alle Elemente der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="9eefb-172">These operators process all elements of the collection.</span></span> <span data-ttu-id="9eefb-173">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9eefb-173">Example:</span></span>

```powershell
"zzz", "def", "zzz" -eq "zzz"
```

```output
zzz
zzz
```

<span data-ttu-id="9eefb-174">Die Gleichheits Operatoren akzeptieren zwei Objekte, nicht nur einen skalaren oder eine Auflistung.</span><span class="sxs-lookup"><span data-stu-id="9eefb-174">The equality operators accept any two objects, not just a scalar or collection.</span></span>
<span data-ttu-id="9eefb-175">Das Vergleichs Ergebnis ist jedoch für den Endbenutzer nicht unbedingt sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="9eefb-175">But the comparison result is not guaranteed to be meaningful for the end-user.</span></span>
<span data-ttu-id="9eefb-176">Im folgenden Beispiel wird das Problem veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9eefb-176">The following example demonstrates the issue.</span></span>

```powershell
class MyFileInfoSet {
    [String]$File
    [Int64]$Size
}
$a = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$b = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$a -eq $b
```

```Output
False
```

<span data-ttu-id="9eefb-177">In diesem Beispiel haben wir zwei Objekte mit identischen Eigenschaften erstellt.</span><span class="sxs-lookup"><span data-stu-id="9eefb-177">In this example, we created two objects with identical properties.</span></span> <span data-ttu-id="9eefb-178">Das Ergebnis der Gleichheits Überprüfung ist jedoch **falsch** , da es sich um unterschiedliche Objekte handelt.</span><span class="sxs-lookup"><span data-stu-id="9eefb-178">Yet, the equality test result is **False** because they are different objects.</span></span> <span data-ttu-id="9eefb-179">Um vergleichbare Klassen zu erstellen, müssen Sie [System. IEquatable \<T> ][2] in ihrer Klasse implementieren.</span><span class="sxs-lookup"><span data-stu-id="9eefb-179">To create comparable classes, you need to implement [System.IEquatable\<T>][2] in your class.</span></span> <span data-ttu-id="9eefb-180">Im folgenden Beispiel wird die partielle Implementierung einer **myfileinfoset** -Klasse veranschaulicht, die " [System. \<T> IEquatable][2] " implementiert und zwei Eigenschaften hat: " **File** " und " **size**".</span><span class="sxs-lookup"><span data-stu-id="9eefb-180">The following example demonstrates the partial implementation of a **MyFileInfoSet** class that implements [System.IEquatable\<T>][2] and has two properties, **File** and **Size**.</span></span> <span data-ttu-id="9eefb-181">Die `Equals()` -Methode gibt true zurück, wenn die Datei-und Größen Eigenschaften von zwei **myfileinfoset** -Objekten identisch sind.</span><span class="sxs-lookup"><span data-stu-id="9eefb-181">The `Equals()` method returns True if the File and Size properties of two **MyFileInfoSet** objects are the same.</span></span>

```powershell
class MyFileInfoSet : System.IEquatable[Object] {
    [String]$File
    [Int64]$Size

    [bool] Equals([Object] $obj) {
        return ($this.File -eq $obj.File) -and ($this.Size -eq $obj.Size)
    }
}
$a = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$b = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$a -eq $b
```

```Output
True
```

<span data-ttu-id="9eefb-182">Ein hervorragendes Beispiel für den Vergleich beliebiger Objekte besteht darin, herauszufinden, ob Sie NULL sind.</span><span class="sxs-lookup"><span data-stu-id="9eefb-182">A prominent example of comparing arbitrary objects is to find out if they are null.</span></span> <span data-ttu-id="9eefb-183">Wenn Sie jedoch bestimmen müssen, ob eine Variable ist `$null` , müssen Sie `$null` auf der linken Seite des Gleichheits Operators ablegen.</span><span class="sxs-lookup"><span data-stu-id="9eefb-183">But if you need to determine whether a variable is `$null`, you must put `$null` on the left-hand side of the equality operator.</span></span> <span data-ttu-id="9eefb-184">Wenn Sie es auf der rechten Seite platzieren, ist das nicht das, was Sie erwarten.</span><span class="sxs-lookup"><span data-stu-id="9eefb-184">Putting it on the right-hand side does not do what you expect.</span></span>

<span data-ttu-id="9eefb-185">Beispielsweise `$a` ein Array, das NULL-Elemente enthält:</span><span class="sxs-lookup"><span data-stu-id="9eefb-185">For example, let `$a` be an array containing null elements:</span></span>

```powershell
$a = 1, 2, $null, 4, $null, 6
```

<span data-ttu-id="9eefb-186">Die folgenden Tests, die `$a` nicht NULL sind.</span><span class="sxs-lookup"><span data-stu-id="9eefb-186">The following tests that `$a` is not null.</span></span>

```powershell
$null -ne $a
```

```output
False
```

<span data-ttu-id="9eefb-187">Der folgende Filter filtert jedoch alle NULL-Elemente aus `$a` :</span><span class="sxs-lookup"><span data-stu-id="9eefb-187">The following, however, filers out all null elements from `$a`:</span></span>

```powershell
$a -ne $null # Output: 1, 2, 4, 6
```

```output
1
2
4
6
```

### <a name="-gt--ge--lt-and--le"></a><span data-ttu-id="9eefb-188">-gt,-ge,-lt und-Le</span><span class="sxs-lookup"><span data-stu-id="9eefb-188">-gt, -ge, -lt, and -le</span></span>

<span data-ttu-id="9eefb-189">`-gt`, `-ge` , `-lt` und `-le` Verhalten sich ähnlich.</span><span class="sxs-lookup"><span data-stu-id="9eefb-189">`-gt`, `-ge`, `-lt`, and `-le` behave very similarly.</span></span> <span data-ttu-id="9eefb-190">Wenn beide Seiten Skalar sind, geben Sie " **true** " oder " **false** " zurück, je nachdem, wie die beiden Seiten verglichen werden</span><span class="sxs-lookup"><span data-stu-id="9eefb-190">When both sides are scalar they return **True** or **False** depending on how the two sides compare:</span></span>

| <span data-ttu-id="9eefb-191">Betreiber</span><span class="sxs-lookup"><span data-stu-id="9eefb-191">Operator</span></span> | <span data-ttu-id="9eefb-192">Gibt "true" zurück, wenn...</span><span class="sxs-lookup"><span data-stu-id="9eefb-192">Returns True when...</span></span>                   |
| -------- | -------------------------------------- |
| <span data-ttu-id="9eefb-193">-gt</span><span class="sxs-lookup"><span data-stu-id="9eefb-193">-gt</span></span>      | <span data-ttu-id="9eefb-194">Die linke Seite ist größer.</span><span class="sxs-lookup"><span data-stu-id="9eefb-194">The left-hand side is greater</span></span>          |
| <span data-ttu-id="9eefb-195">-ge</span><span class="sxs-lookup"><span data-stu-id="9eefb-195">-ge</span></span>      | <span data-ttu-id="9eefb-196">Die linke Seite ist größer als oder gleich.</span><span class="sxs-lookup"><span data-stu-id="9eefb-196">The left-hand side is greater or equal</span></span> |
| <span data-ttu-id="9eefb-197">-lt</span><span class="sxs-lookup"><span data-stu-id="9eefb-197">-lt</span></span>      | <span data-ttu-id="9eefb-198">Die linke Seite ist kleiner.</span><span class="sxs-lookup"><span data-stu-id="9eefb-198">The left-hand side is smaller</span></span>          |
| <span data-ttu-id="9eefb-199">-le</span><span class="sxs-lookup"><span data-stu-id="9eefb-199">-le</span></span>      | <span data-ttu-id="9eefb-200">Die linke Seite ist kleiner oder gleich.</span><span class="sxs-lookup"><span data-stu-id="9eefb-200">The left-hand side is smaller or equal</span></span> |

<span data-ttu-id="9eefb-201">In den folgenden Beispielen geben alle-Anweisungen true zurück.</span><span class="sxs-lookup"><span data-stu-id="9eefb-201">In the following examples, all statements return True.</span></span>

```powershell
8 -gt 6  # Output: True
8 -ge 8  # Output: True
6 -lt 8  # Output: True
8 -le 8  # Output: True
```

> [!NOTE]
> <span data-ttu-id="9eefb-202">In den meisten Programmiersprachen ist der größer-als-Operator `>` .</span><span class="sxs-lookup"><span data-stu-id="9eefb-202">In most programming languages the greater-than operator is `>`.</span></span> <span data-ttu-id="9eefb-203">In PowerShell wird dieses Zeichen für die Umleitung verwendet.</span><span class="sxs-lookup"><span data-stu-id="9eefb-203">In PowerShell, this character is used for redirection.</span></span> <span data-ttu-id="9eefb-204">Weitere Informationen finden Sie unter [about_Redirection][3].</span><span class="sxs-lookup"><span data-stu-id="9eefb-204">For details, see [about_Redirection][3].</span></span>

<span data-ttu-id="9eefb-205">Wenn die linke Seite eine Auflistung ist, vergleichen diese Operatoren jeden Member der Auflistung mit der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="9eefb-205">When the left-hand side is a collection, these operators compare each member of the collection with the right-hand side.</span></span> <span data-ttu-id="9eefb-206">Abhängig von ihrer Logik behalten Sie den Member bei oder verwerfen ihn.</span><span class="sxs-lookup"><span data-stu-id="9eefb-206">Depending on their logic, they either keep or discard the member.</span></span>

<span data-ttu-id="9eefb-207">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9eefb-207">Example:</span></span>

```powershell
$a=5, 6, 7, 8, 9

Write-Output "Test collection:"
$a

Write-Output "`nMembers greater than 7"
$a -gt 7

Write-Output "`nMembers greater than or equal to 7"
$a -ge 7

Write-Output "`nMembers smaller than 7"
$a -lt 7

Write-Output "`nMembers smaller than or equal to 7"
$a -le 7
```

```output
Test collection:
5
6
7
8
9

Members greater than 7
8
9

Members greater than or equal to 7
7
8
9

Members smaller than 7
5
6

Members smaller than or equal to 7
5
6
7
```

<span data-ttu-id="9eefb-208">Diese Operatoren arbeiten mit jeder Klasse, die [System. ivergleichbare][1]implementiert.</span><span class="sxs-lookup"><span data-stu-id="9eefb-208">These operators work with any class that implements [System.IComparable][1].</span></span>

<span data-ttu-id="9eefb-209">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="9eefb-209">Examples:</span></span>

```powershell
# Date comparison
[DateTime]'2001-11-12' -lt [DateTime]'2020-08-01' # True

# Sorting order comparison
'a' -lt 'z'           # True; 'a' comes before 'z'
'macOS' -ilt 'MacOS'  # False
'MacOS' -ilt 'macOS'  # False
'macOS' -clt 'MacOS'  # True; 'm' comes before 'M'
```

<span data-ttu-id="9eefb-210">Im folgenden Beispiel wird veranschaulicht, dass kein Symbol auf einer American QWERTY-Tastatur vorhanden ist, die nach "a" sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="9eefb-210">The following example demonstrates that there is no symbol on an American QWERTY keyboard that gets sorted after 'a'.</span></span> <span data-ttu-id="9eefb-211">Er fügt eine Menge, die alle Symbole enthält, an den `-gt` Operator an, um Sie mit "a" zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="9eefb-211">It feeds a set containing all such symbols to the `-gt` operator to compare them against 'a'.</span></span> <span data-ttu-id="9eefb-212">Die Ausgabe ist ein leeres Array.</span><span class="sxs-lookup"><span data-stu-id="9eefb-212">The output is an empty array.</span></span>

```powershell
$a=' ','`','~','!','@','#','$','%','^','&','*','(',')','_','+','-','=',
   '{','}','[',']',':',';','"','''','\','|','/','?','.','>',',','<'
$a -gt 'a'
# Output: Nothing
```

<span data-ttu-id="9eefb-213">Wenn die beiden Seiten der Operatoren nicht angemessen vergleichbar sind, wird ein Fehler ohne Abbruch ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="9eefb-213">If the two sides of the operators are not reasonably comparable, these operators raise a non-terminating error.</span></span>

## <a name="matching-operators"></a><span data-ttu-id="9eefb-214">Vergleichs Operatoren</span><span class="sxs-lookup"><span data-stu-id="9eefb-214">Matching operators</span></span>

<span data-ttu-id="9eefb-215">Die übereinstimmenden Operatoren ( `-like` , `-notlike` , `-match` und `-notmatch` ) suchen Elemente, die mit einem angegebenen Muster übereinstimmen oder nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="9eefb-215">The matching operators (`-like`, `-notlike`, `-match`, and `-notmatch`) find elements that match or do not match a specified pattern.</span></span> <span data-ttu-id="9eefb-216">Das Muster für `-like` und `-notlike` ist ein Platzhalter Ausdruck (mit `*` , `?` und `[ ]` ), während `-match` und `-notmatch` einen regulären Ausdruck (Regex) akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="9eefb-216">The pattern for `-like` and `-notlike` is a wildcard expression (containing `*`, `?`, and `[ ]`), while `-match` and `-notmatch` accept a regular expression (Regex).</span></span>

<span data-ttu-id="9eefb-217">Die Syntax ist:</span><span class="sxs-lookup"><span data-stu-id="9eefb-217">The syntax is:</span></span>

```
<string[]> -like    <wildcard-expression>
<string[]> -notlike <wildcard-expression>
<string[]> -match    <regular-expression>
<string[]> -notmatch <regular-expression>
```

<span data-ttu-id="9eefb-218">Wenn die Eingabe dieser Operatoren ein skalarer Wert ist, wird ein **boolescher** Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9eefb-218">When the input of these operators is a scalar value, they return a **Boolean** value.</span></span> <span data-ttu-id="9eefb-219">Wenn die Eingabe eine Auflistung von Werten ist, geben die Operatoren alle übereinstimmenden Member zurück.</span><span class="sxs-lookup"><span data-stu-id="9eefb-219">When the input is a collection of values, the operators return any matching members.</span></span> <span data-ttu-id="9eefb-220">Wenn keine Übereinstimmungen in einer Auflistung vorhanden sind, geben die Operatoren ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="9eefb-220">If there are no matches in a collection, the operators return an empty array.</span></span>

### <a name="-like-and--notlike"></a><span data-ttu-id="9eefb-221">-like und-notlike</span><span class="sxs-lookup"><span data-stu-id="9eefb-221">-like and -notlike</span></span>

<span data-ttu-id="9eefb-222">`-like`und `-notlike` Verhalten sich ähnlich wie `-eq` und `-ne` , aber die Rechte Seite könnte eine Zeichenfolge sein, [](about_Wildcards.md)die Platzhalter enthält.</span><span class="sxs-lookup"><span data-stu-id="9eefb-222">`-like` and `-notlike` behave similarly to `-eq` and `-ne`, but the right-hand side could be a string containing [wildcards](about_Wildcards.md).</span></span>

<span data-ttu-id="9eefb-223">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9eefb-223">Example:</span></span>

```powershell
"PowerShell" -like    "*shell"           # Output: True
"PowerShell" -notlike "*shell"           # Output: False
"PowerShell" -like    "Power?hell"       # Output: True
"PowerShell" -notlike "Power?hell"       # Output: False
"PowerShell" -like    "Power[p-w]hell"   # Output: True
"PowerShell" -notlike "Power[p-w]hell"   # Output: False

"PowerShell", "Server" -like "*shell"    # Output: PowerShell
"PowerShell", "Server" -notlike "*shell" # Output: Server
```

### <a name="-match-and--notmatch"></a><span data-ttu-id="9eefb-224">-Match und-notmatch</span><span class="sxs-lookup"><span data-stu-id="9eefb-224">-match and -notmatch</span></span>

<span data-ttu-id="9eefb-225">`-match` und `-notmatch` verwenden reguläre Ausdrücke, um in den linksseitigen Werten nach Mustern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="9eefb-225">`-match` and `-notmatch` use regular expressions to search for pattern in the left-hand side values.</span></span> <span data-ttu-id="9eefb-226">Reguläre Ausdrücke können komplexe Muster wie e-Mail-Adressen, UNC-Pfade oder formatierte Telefonnummern erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9eefb-226">Regular expressions can match complex patterns like email addresses, UNC paths, or formatted phone numbers.</span></span> <span data-ttu-id="9eefb-227">Die Zeichenfolge auf der rechten Seite muss den Regeln für [reguläre Ausdrücke](about_Regular_Expressions.md) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9eefb-227">The right-hand side string must adhere to the [regular expressions](about_Regular_Expressions.md) rules.</span></span>

<span data-ttu-id="9eefb-228">Skalare Beispiele:</span><span class="sxs-lookup"><span data-stu-id="9eefb-228">Scalar examples:</span></span>

```powershell
# Partial match test, showing how differently -match and -like behave
"PowerShell" -match 'shell'        # Output: True
"PowerShell" -like  'shell'        # Output: False

# Regex syntax test
"PowerShell" -match    '^Power\w+' # Output: True
'bag'        -notmatch 'b[iou]g'   # Output: True
```

<span data-ttu-id="9eefb-229">Wenn es sich bei der Eingabe um eine Auflistung handelt, geben die Operatoren die übereinstimmenden Member der Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="9eefb-229">If the input is a collection, the operators return the matching members of that collection.</span></span>

<span data-ttu-id="9eefb-230">Beispiele für Sammlungen:</span><span class="sxs-lookup"><span data-stu-id="9eefb-230">Collection examples:</span></span>

```powershell
"PowerShell", "Super PowerShell", "Power's hell" -match '^Power\w+'
# Output: PowerShell

"Rhell", "Chell", "Mel", "Smell", "Shell" -match "hell"
# Output: Rhell, Chell, Shell

"Bag", "Beg", "Big", "Bog", "Bug"  -match 'b[iou]g'
#Output: Big, Bog, Bug

"Bag", "Beg", "Big", "Bog", "Bug"  -notmatch 'b[iou]g'
#Output: Bag, Beg
```

<span data-ttu-id="9eefb-231">`-match` und `-notmatch` unterstützen Regex-Erfassungs Gruppen.</span><span class="sxs-lookup"><span data-stu-id="9eefb-231">`-match` and `-notmatch` support regex capture groups.</span></span> <span data-ttu-id="9eefb-232">Jedes Mal, wenn Sie ausgeführt werden, überschreiben Sie die `$Matches` Automatische Variable.</span><span class="sxs-lookup"><span data-stu-id="9eefb-232">Each time they run, they overwrite the `$Matches` automatic variable.</span></span> <span data-ttu-id="9eefb-233">Wenn `<input>` eine Auflistung ist, `$Matches` ist die Variable `$null` .</span><span class="sxs-lookup"><span data-stu-id="9eefb-233">When `<input>` is a collection the `$Matches` variable is `$null`.</span></span> <span data-ttu-id="9eefb-234">`$Matches` ist eine **Hash Tabelle** , die immer über einen Schlüssel mit dem Namen ' 0 ' verfügt, der die gesamte Entsprechung speichert.</span><span class="sxs-lookup"><span data-stu-id="9eefb-234">`$Matches` is a **Hashtable** that always has a key named '0', which stores the entire match.</span></span> <span data-ttu-id="9eefb-235">Wenn der reguläre Ausdruck Erfassungs Gruppen enthält, `$Matches` enthält die zusätzliche Schlüssel für jede Gruppe.</span><span class="sxs-lookup"><span data-stu-id="9eefb-235">If the regular expression contains capture groups, the `$Matches` contains additional keys for each group.</span></span>

<span data-ttu-id="9eefb-236">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9eefb-236">Example:</span></span>

```powershell
$string = 'The last logged on user was CONTOSO\jsmith'
$string -match 'was (?<domain>.+)\\(?<user>.+)'

$Matches

Write-Output "`nDomain name:"
$Matches.domain

Write-Output "`nUser name:"
$Matches.user
```

```output
True

Name                           Value
----                           -----
domain                         CONTOSO
user                           jsmith
0                              was CONTOSO\jsmith

Domain name:
CONTOSO

User name:
jsmith
```

<span data-ttu-id="9eefb-237">Weitere Informationen finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="9eefb-237">For details, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

## <a name="replacement-operator"></a><span data-ttu-id="9eefb-238">Ersatz Operator</span><span class="sxs-lookup"><span data-stu-id="9eefb-238">Replacement operator</span></span>

### <a name="replacement-with-regular-expressions"></a><span data-ttu-id="9eefb-239">Ersetzung durch reguläre Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="9eefb-239">Replacement with regular expressions</span></span>

<span data-ttu-id="9eefb-240">Ebenso `-match` verwendet der- `-replace` Operator reguläre Ausdrücke, um nach dem angegebenen Muster zu suchen.</span><span class="sxs-lookup"><span data-stu-id="9eefb-240">Like `-match`, the `-replace` operator uses regular expressions to find the specified pattern.</span></span> <span data-ttu-id="9eefb-241">Im Gegensatz `-match` dazu werden die Übereinstimmungen durch einen anderen angegebenen Wert ersetzt.</span><span class="sxs-lookup"><span data-stu-id="9eefb-241">But unlike `-match`, it replaces the matches with another specified value.</span></span>

<span data-ttu-id="9eefb-242">Syntax:</span><span class="sxs-lookup"><span data-stu-id="9eefb-242">Syntax:</span></span>

```
<input> -replace <regular-expression>, <substitute>
```

<span data-ttu-id="9eefb-243">Der-Operator ersetzt den gesamten oder einen Teil eines Werts durch den angegebenen Wert mithilfe regulärer Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="9eefb-243">The operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="9eefb-244">Sie können den-Operator für viele Verwaltungsaufgaben verwenden, z. b. das Umbenennen von Dateien.</span><span class="sxs-lookup"><span data-stu-id="9eefb-244">You can use the operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="9eefb-245">Der folgende Befehl ändert z. b. die Dateinamen Erweiterungen aller `.txt` Dateien in `.log` :</span><span class="sxs-lookup"><span data-stu-id="9eefb-245">For example, the following command changes the file name extensions of all `.txt` files to `.log`:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

<span data-ttu-id="9eefb-246">Standardmäßig `-replace` wird bei dem Operator die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="9eefb-246">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="9eefb-247">Verwenden Sie, um die Groß-/Kleinschreibung zu beachten `-creplace`</span><span class="sxs-lookup"><span data-stu-id="9eefb-247">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="9eefb-248">Verwenden Sie, um die Groß-/Kleinschreibung explizit zu Unternehmen `-ireplace` .</span><span class="sxs-lookup"><span data-stu-id="9eefb-248">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="9eefb-249">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="9eefb-249">Examples:</span></span>

```powershell
"book" -ireplace "B", "C" # Case insensitive
"book" -creplace "B", "C" # Case-sensitive; hence, nothing to replace
```

```Output
Cook
book
```

### <a name="regular-expressions-substitutions"></a><span data-ttu-id="9eefb-250">Reguläre Ausdrucks Ersetzungen</span><span class="sxs-lookup"><span data-stu-id="9eefb-250">Regular expressions substitutions</span></span>

<span data-ttu-id="9eefb-251">Es ist auch möglich, reguläre Ausdrücke zum dynamischen Ersetzen von Text mithilfe von Erfassungs Gruppen und Ersetzungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9eefb-251">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="9eefb-252">Auf Erfassungs Gruppen kann in der `<substitute>` Zeichenfolge mit dem Dollarzeichen ( `$` ) vor der Gruppen Kennung verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="9eefb-252">Capture groups can be referenced in the `<substitute>` string using the dollar sign (`$`) character before the group identifier.</span></span>

<span data-ttu-id="9eefb-253">Im folgenden Beispiel `-replace` akzeptiert der-Operator einen Benutzernamen in der Form `DomainName\Username` und konvertiert in das- `Username@DomainName` Format:</span><span class="sxs-lookup"><span data-stu-id="9eefb-253">In the following example, the `-replace` operator accepts a username in the form of `DomainName\Username` and converts to the `Username@DomainName` format:</span></span>

```powershell
$SearchExp = '^(?<DomainName>[\w-.]+)\\(?<Username>[\w-.]+)$'
$ReplaceExp = '${Username}@${DomainName}'

'Contoso.local\John.Doe' -replace $SearchExp,$ReplaceExp
```

```output
John.Doe@Contoso.local
```

> [!WARNING]
> <span data-ttu-id="9eefb-254">Das `$` Zeichen verfügt über syntatic-Rollen in PowerShell und regulären Ausdrücken:</span><span class="sxs-lookup"><span data-stu-id="9eefb-254">The `$` character has syntatic roles in both PowerShell and regular expressions:</span></span>
>
> - <span data-ttu-id="9eefb-255">In PowerShell werden zwischen doppelten Anführungszeichen Variablen festgelegt und als Teil Ausdruck bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9eefb-255">In PowerShell, between double quotation marks, it designates variables and acts as a subexpression operator.</span></span>
> - <span data-ttu-id="9eefb-256">In Regex-Such Zeichenfolgen gibt es das Ende der Zeile an.</span><span class="sxs-lookup"><span data-stu-id="9eefb-256">In Regex search strings, it denotes end of the line</span></span>
> - <span data-ttu-id="9eefb-257">In Regex-Ersetzungs Zeichenfolgen bezeichnet sie erfasste Gruppen. Stellen Sie sicher, dass Sie die regulären Ausdrücke zwischen einfachen Anführungszeichen platzieren, oder fügen Sie vor Ihnen ein Graviszeichen- `` ` `` Zeichen () ein.</span><span class="sxs-lookup"><span data-stu-id="9eefb-257">In Regex substitution strings, it denotes captured groups.Be sure to either put your regular expressions between single quotation marks or insert a backtick (`` ` ``) character before them.</span></span>

<span data-ttu-id="9eefb-258">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9eefb-258">For example:</span></span>

```powershell
$1 = 'Goodbye'

'Hello World' -replace '(\w+) \w+', "$1 Universe"
# Output: Goodbye Universe

'Hello World' -replace '(\w+) \w+', '$1 Universe'
# Output: Hello Universe
```

<span data-ttu-id="9eefb-259">`$$` in Regex steht für einen Literalwert `$` .</span><span class="sxs-lookup"><span data-stu-id="9eefb-259">`$$` in Regex denotes a literal `$`.</span></span> <span data-ttu-id="9eefb-260">Dies `$$` in der Ersetzungs Zeichenfolge zum Einschließen eines Literals `$` in den resultierenden Austausch.</span><span class="sxs-lookup"><span data-stu-id="9eefb-260">This `$$` in the substitution string to include a literal `$` in the resulting replacement.</span></span> <span data-ttu-id="9eefb-261">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9eefb-261">For example:</span></span>

```powershell
'5.72' -replace '(.+)', '$ $1' # Output: $ 5.72
'5.72' -replace '(.+)', '$$$1' # Output: $5.72
'5.72' -replace '(.+)', '$$1'  # Output: $1
```

<span data-ttu-id="9eefb-262">Weitere Informationen finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md) und Ersetzungen [in regulären Ausdrücken][4].</span><span class="sxs-lookup"><span data-stu-id="9eefb-262">To learn more, see [about_Regular_Expressions](about_Regular_Expressions.md) and [Substitutions in Regular Expressions][4].</span></span>

### <a name="substituting-in-a-collection"></a><span data-ttu-id="9eefb-263">Ersetzen in einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="9eefb-263">Substituting in a collection</span></span>

<span data-ttu-id="9eefb-264">Wenn der `<input>` für den `-replace` Operator eine Auflistung ist, wendet PowerShell die Ersetzung auf jeden Wert in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="9eefb-264">When the `<input>` to the `-replace` operator is a collection, PowerShell applies the replacement to every value in the collection.</span></span> <span data-ttu-id="9eefb-265">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9eefb-265">For example:</span></span>

```powershell
"B1","B2","B3","B4","B5" -replace "B", 'a'
a1
a2
a3
a4
a5
```

### <a name="replacement-with-a-script-block"></a><span data-ttu-id="9eefb-266">Ersetzung durch einen Skriptblock</span><span class="sxs-lookup"><span data-stu-id="9eefb-266">Replacement with a script block</span></span>

<span data-ttu-id="9eefb-267">In PowerShell 6 und höher akzeptiert der `-replace` Operator auch einen Skriptblock, der die Ersetzung durchführt.</span><span class="sxs-lookup"><span data-stu-id="9eefb-267">In PowerShell 6 and later, the `-replace` operator also accepts a script block that performs the replacement.</span></span> <span data-ttu-id="9eefb-268">Der Skriptblock wird bei jeder Übereinstimmung einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9eefb-268">The script block runs once for every match.</span></span>

<span data-ttu-id="9eefb-269">Syntax:</span><span class="sxs-lookup"><span data-stu-id="9eefb-269">Syntax:</span></span>

```powershell
<String> -replace <regular-expression>, {<Script-block>}
```

<span data-ttu-id="9eefb-270">Verwenden Sie im Skriptblock die `$_` Automatische Variable, um auf den zu ersetzenden Eingabetext und andere nützliche Informationen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9eefb-270">Within the script block, use the `$_` automatic variable to access the input text being replaced and other useful information.</span></span> <span data-ttu-id="9eefb-271">Der Klassentyp dieser Variablen ist [System. Text. RegularExpressions. Match][2].</span><span class="sxs-lookup"><span data-stu-id="9eefb-271">This variable's class type is [System.Text.RegularExpressions.Match][2].</span></span>

<span data-ttu-id="9eefb-272">Im folgenden Beispiel wird jede Sequenz von drei Ziffern durch die Zeichen Entsprechungen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="9eefb-272">The following example replaces each sequence of three digits with the character equivalents.</span></span> <span data-ttu-id="9eefb-273">Der Skriptblock wird für jeden Satz von drei Ziffern ausgeführt, die ersetzt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="9eefb-273">The script block runs for each set of three digits that needs to be replaced.</span></span>

```powershell
"072101108108111" -replace "\d{3}", {return [char][int]$_.Value}
```

```output
Hello
```

## <a name="containment-operators"></a><span data-ttu-id="9eefb-274">Containment-Operatoren</span><span class="sxs-lookup"><span data-stu-id="9eefb-274">Containment operators</span></span>

<span data-ttu-id="9eefb-275">Die Containment-Operatoren ( `-contains` , `-notcontains` , `-in` und `-notin` ) ähneln den Gleichheits Operatoren, mit dem Unterschied, dass Sie immer einen **booleschen** Wert zurückgeben, auch wenn die Eingabe eine Auflistung ist.</span><span class="sxs-lookup"><span data-stu-id="9eefb-275">The containment operators (`-contains`, `-notcontains`, `-in`, and `-notin`) are similar to the equality operators, except that they always return a **Boolean** value, even when the input is a collection.</span></span> <span data-ttu-id="9eefb-276">Diese Operatoren enden den Vergleich ab, sobald die erste Übereinstimmung erkannt wird, während die Gleichheits Operatoren alle Eingabeelemente auswerten.</span><span class="sxs-lookup"><span data-stu-id="9eefb-276">These operators stop comparing as soon as they detect the first match, whereas the equality operators evaluate all input members.</span></span> <span data-ttu-id="9eefb-277">In einer sehr großen Auflistung geben diese Operatoren schneller zurück als die Gleichheits Operatoren.</span><span class="sxs-lookup"><span data-stu-id="9eefb-277">In a very large collection, these operators return quicker than the equality operators.</span></span>

<span data-ttu-id="9eefb-278">Syntax:</span><span class="sxs-lookup"><span data-stu-id="9eefb-278">Syntax:</span></span>

```
<Collection> -contains <Test-object>
<Collection> -notcontains <Test-object>
<Test-object> -in <Collection>
<Test-object> -notin <Collection>
```

### <a name="-contains-and--notcontains"></a><span data-ttu-id="9eefb-279">-enthält und-notenthält</span><span class="sxs-lookup"><span data-stu-id="9eefb-279">-contains and -notcontains</span></span>

<span data-ttu-id="9eefb-280">Diese Operatoren erkennen, ob ein Satz ein bestimmtes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="9eefb-280">These operators tell whether a set includes a certain element.</span></span> <span data-ttu-id="9eefb-281">`-contains` gibt true zurück, wenn die Rechte Seite (Testobjekt) mit einem der Elemente in der Menge übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="9eefb-281">`-contains` returns True when the right-hand side (test object) matches one of the elements in the set.</span></span> <span data-ttu-id="9eefb-282">`-notcontains` gibt stattdessen false zurück.</span><span class="sxs-lookup"><span data-stu-id="9eefb-282">`-notcontains` returns False instead.</span></span> <span data-ttu-id="9eefb-283">Wenn das Testobjekt eine Auflistung ist, verwenden diese Operatoren Verweis Gleichheit, d. h. Sie überprüfen, ob eines der Elemente des Satzes dieselbe Instanz des Testobjekts ist.</span><span class="sxs-lookup"><span data-stu-id="9eefb-283">When the test object is a collection, these operators use reference equality, i.e. they check whether one of the set's elements is the same instance of the test object.</span></span>

<span data-ttu-id="9eefb-284">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="9eefb-284">Examples:</span></span>

```powershell
"abc", "def" -contains "def"                  # Output: True
"abc", "def" -notcontains "def"               # Output: False
"Windows", "PowerShell" -contains "Shell"     # Output: False
"Windows", "PowerShell" -notcontains "Shell"  # Output: True
"abc", "def", "ghi" -contains "abc", "def"    # Output: False
"abc", "def", "ghi" -notcontains "abc", "def" # Output: True
```

<span data-ttu-id="9eefb-285">Komplexere Beispiele:</span><span class="sxs-lookup"><span data-stu-id="9eefb-285">More complex examples:</span></span>

```powershell
$DomainServers = "ContosoDC1","ContosoDC2","ContosoFileServer","ContosoDNS",
                 "ContosoDHCP","ContosoWSUS"
$thisComputer  = "ContosoDC2"

$DomainServers -contains $thisComputer
# Output: True

$a = "abc", "def"
"abc", "def", "ghi" -contains $a # Output: False
$a, "ghi" -contains $a           # Output: True
```

### <a name="-in-and--notin"></a><span data-ttu-id="9eefb-286">-in und-NOTIN</span><span class="sxs-lookup"><span data-stu-id="9eefb-286">-in and -notin</span></span>

<span data-ttu-id="9eefb-287">Die `-in` `notin` Operatoren und wurden in PowerShell 3 als syntaktische Umkehrung der der `contains` Operatoren und eingeführt `-notcontain` .</span><span class="sxs-lookup"><span data-stu-id="9eefb-287">The `-in` and -`notin` operators were introduced in PowerShell 3 as the syntactic reverse of the of `contains` and `-notcontain` operators.</span></span> <span data-ttu-id="9eefb-288">`-in` gibt **true** zurück, wenn die linke Seite `<test-object>` mit einem der Elemente in der Menge übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="9eefb-288">`-in` returns **True** when the left-hand side `<test-object>` matches one of the elements in the set.</span></span> <span data-ttu-id="9eefb-289">`-notin` gibt stattdessen **false** zurück.</span><span class="sxs-lookup"><span data-stu-id="9eefb-289">`-notin` returns **False** instead.</span></span> <span data-ttu-id="9eefb-290">Wenn das Testobjekt eine Menge ist, verwenden diese Operatoren Verweis Gleichheit, um zu überprüfen, ob eines der Elemente der Gruppe dieselbe Instanz des Testobjekts ist.</span><span class="sxs-lookup"><span data-stu-id="9eefb-290">When the test object is a set, these operators use reference equality to check whether one of the set's elements is the same instance of the test object.</span></span>

<span data-ttu-id="9eefb-291">In den folgenden Beispielen werden dieselben Schritte wie in den Beispielen für `-contain` und `-notcontain` durchzuführen, aber Sie werden `-in` stattdessen mit und geschrieben `-notin` .</span><span class="sxs-lookup"><span data-stu-id="9eefb-291">The following examples do the same thing that the examples for `-contain` and `-notcontain` do, but they are written with `-in` and `-notin` instead.</span></span>

```powershell
"def" -in "abc", "def"                  # Output: True
"def" -notin "abc", "def"               # Output: False
"Shell" -in "Windows", "PowerShell"     # Output: False
"Shell" -notin "Windows", "PowerShell"  # Output: True
"abc", "def" -in "abc", "def", "ghi"    # Output: False
"abc", "def" -notin "abc", "def", "ghi" # Output: True
```

<span data-ttu-id="9eefb-292">Komplexere Beispiele:</span><span class="sxs-lookup"><span data-stu-id="9eefb-292">More complex examples:</span></span>

```powershell
$DomainServers = "ContosoDC1","ContosoDC2","ContosoFileServer","ContosoDNS",
                 "ContosoDHCP","ContosoWSUS"
$thisComputer  = "ContosoDC2"

$thisComputer -in $DomainServers
# Output: True

$a = "abc", "def"
$a -in "abc", "def", "ghi" # Output: False
$a -in $a, "ghi"           # Output: True
```

## <a name="type-comparison"></a><span data-ttu-id="9eefb-293">Typvergleich</span><span class="sxs-lookup"><span data-stu-id="9eefb-293">Type comparison</span></span>

<span data-ttu-id="9eefb-294">Die typvergleichs Operatoren ( `-is` und `-isnot` ) werden verwendet, um zu bestimmen, ob es sich bei einem Objekt um einen bestimmten Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="9eefb-294">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

<span data-ttu-id="9eefb-295">Syntax:</span><span class="sxs-lookup"><span data-stu-id="9eefb-295">Syntax:</span></span>

```powershell
<object> -is <type-reference>
<object> -isnot <type-reference>
```

<span data-ttu-id="9eefb-296">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9eefb-296">Example:</span></span>

```powershell
$a = 1
$b = "1"
$a -is [int]           # Output: True
$a -is $b.GetType()    # Output: False
$b -isnot [int]        # Output: True
$a -isnot $b.GetType() # Output: True
```

## <a name="see-also"></a><span data-ttu-id="9eefb-297">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="9eefb-297">SEE ALSO</span></span>

- [<span data-ttu-id="9eefb-298">about_Operators</span><span class="sxs-lookup"><span data-stu-id="9eefb-298">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="9eefb-299">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="9eefb-299">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="9eefb-300">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="9eefb-300">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="9eefb-301">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="9eefb-301">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="9eefb-302">ForEach-Objekt</span><span class="sxs-lookup"><span data-stu-id="9eefb-302">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="9eefb-303">Where-Object</span><span class="sxs-lookup"><span data-stu-id="9eefb-303">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)

[1]: /dotnet/api/system.icomparable
[2]: /dotnet/api/system.iequatable-1
[3]: /dotnet/api/system.text.regularexpressions.match
[4]: about_Redirection.md#potential-confusion-with-comparison-operators
[5]: /dotnet/standard/base-types/substitutions-in-regular-expressions
