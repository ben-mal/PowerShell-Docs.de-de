---
description: Listet die PowerShell-Operatoren in der Rangfolge auf.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operator_precedence?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operator_Precedence
ms.openlocfilehash: 602a99d6acee63177d45425d90f8fcd47766fb93
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223407"
---
# <a name="about-operator-precedence"></a><span data-ttu-id="2ce05-104">Informationen zur Operator Rangfolge</span><span class="sxs-lookup"><span data-stu-id="2ce05-104">About Operator Precedence</span></span>

## <a name="short-description"></a><span data-ttu-id="2ce05-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2ce05-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="2ce05-106">Listet die PowerShell-Operatoren in der Rangfolge auf.</span><span class="sxs-lookup"><span data-stu-id="2ce05-106">Lists the PowerShell operators in precedence order.</span></span>

## <a name="long-description"></a><span data-ttu-id="2ce05-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2ce05-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="2ce05-108">Mit PowerShell-Operatoren können Sie einfache, aber leistungsstarke Ausdrücke erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ce05-108">PowerShell operators let you construct simple, but powerful expressions.</span></span> <span data-ttu-id="2ce05-109">In diesem Thema werden die Operatoren in der Rangfolge aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2ce05-109">This topic lists the operators in precedence order.</span></span> <span data-ttu-id="2ce05-110">Die Rangfolge ist die Reihenfolge, in der PowerShell die Operatoren auswertet, wenn mehrere Operatoren im gleichen Ausdruck vorkommen.</span><span class="sxs-lookup"><span data-stu-id="2ce05-110">Precedence order is the order in which PowerShell evaluates the operators when multiple operators appear in the same expression.</span></span>

<span data-ttu-id="2ce05-111">Wenn Operatoren die gleiche Rangfolge aufweisen, wertet PowerShell Sie von links nach rechts aus, so wie Sie im Ausdruck angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2ce05-111">When operators have equal precedence, PowerShell evaluates them from left to right as they appear within the expression.</span></span> <span data-ttu-id="2ce05-112">Ausnahmen sind Zuweisungs Operatoren, Umwandlungs Operatoren und Negations Operatoren ( `!` , `-not` , `-bnot` ), die von rechts nach links ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="2ce05-112">The exceptions are the assignment operators, the cast operators, and the negation operators (`!`, `-not`, `-bnot`), which are evaluated from right to left.</span></span>

<span data-ttu-id="2ce05-113">Sie können Gehäuse wie Klammern verwenden, um die standardmäßige Rangfolge zu überschreiben und PowerShell zu zwingen, den eingeschlossenen Teil eines Ausdrucks vor einem nicht eingeschlossenen Teil auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="2ce05-113">You can use enclosures, such as parentheses, to override the standard precedence order and force PowerShell to evaluate the enclosed part of an expression before an unenclosed part.</span></span>

<span data-ttu-id="2ce05-114">In der folgenden Liste werden Operatoren in der Reihenfolge aufgelistet, in der Sie ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="2ce05-114">In the following list, operators are listed in the order that they are evaluated.</span></span> <span data-ttu-id="2ce05-115">Operatoren in derselben Zeile oder in derselben Gruppe haben die gleiche Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="2ce05-115">Operators on the same line, or in the same group, have equal precedence.</span></span>

<span data-ttu-id="2ce05-116">In der Spalte Operator sind die Operatoren aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2ce05-116">The Operator column lists the operators.</span></span> <span data-ttu-id="2ce05-117">In der Spalte Verweis ist das PowerShell-Hilfethema aufgeführt, in dem der-Operator beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="2ce05-117">The Reference column lists the PowerShell Help topic in which the operator is described.</span></span> <span data-ttu-id="2ce05-118">Um das Thema anzuzeigen, geben Sie ein `get-help <topic-name>` .</span><span class="sxs-lookup"><span data-stu-id="2ce05-118">To display the topic, type `get-help <topic-name>`.</span></span>

|         <span data-ttu-id="2ce05-119">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="2ce05-119">OPERATOR</span></span>         |           <span data-ttu-id="2ce05-120">Angabe</span><span class="sxs-lookup"><span data-stu-id="2ce05-120">REFERENCE</span></span>            |
| ------------------------ | ------------------------------ |
| `$() @() ()`             | <span data-ttu-id="2ce05-121">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-121">[about_Operators][]</span></span>            |
| <span data-ttu-id="2ce05-122">`.` (Member Access)</span><span class="sxs-lookup"><span data-stu-id="2ce05-122">`.` (member access)</span></span>      | <span data-ttu-id="2ce05-123">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-123">[about_Operators][]</span></span>            |
| <span data-ttu-id="2ce05-124">`::` Kum</span><span class="sxs-lookup"><span data-stu-id="2ce05-124">`::` (static)</span></span>            | <span data-ttu-id="2ce05-125">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-125">[about_Operators][]</span></span>            |
| <span data-ttu-id="2ce05-126">`[0]` (Index-Operator)</span><span class="sxs-lookup"><span data-stu-id="2ce05-126">`[0]` (index operator)</span></span>   | <span data-ttu-id="2ce05-127">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-127">[about_Operators][]</span></span>            |
| <span data-ttu-id="2ce05-128">`[int]` (Umwandlungs Operatoren)</span><span class="sxs-lookup"><span data-stu-id="2ce05-128">`[int]` (cast operators)</span></span> | <span data-ttu-id="2ce05-129">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-129">[about_Operators][]</span></span>            |
| <span data-ttu-id="2ce05-130">`-split` unären</span><span class="sxs-lookup"><span data-stu-id="2ce05-130">`-split` (unary)</span></span>         | <span data-ttu-id="2ce05-131">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-131">[about_Split][]</span></span>                |
| <span data-ttu-id="2ce05-132">`-join` unären</span><span class="sxs-lookup"><span data-stu-id="2ce05-132">`-join` (unary)</span></span>          | <span data-ttu-id="2ce05-133">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-133">[about_Join][]</span></span>                 |
| <span data-ttu-id="2ce05-134">`,` (Komma-Operator)</span><span class="sxs-lookup"><span data-stu-id="2ce05-134">`,` (comma operator)</span></span>     | <span data-ttu-id="2ce05-135">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-135">[about_Operators][]</span></span>            |
| `++ --`                  | <span data-ttu-id="2ce05-136">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-136">[about_Assignment_Operators][]</span></span> |
| `! -not`                 | <span data-ttu-id="2ce05-137">[about_Logical_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-137">[about_Logical_Operators][]</span></span>    |
| <span data-ttu-id="2ce05-138">`..` (Bereichs Operator)</span><span class="sxs-lookup"><span data-stu-id="2ce05-138">`..` (range operator)</span></span>    | <span data-ttu-id="2ce05-139">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-139">[about_Operators][]</span></span>            |
| <span data-ttu-id="2ce05-140">`-f` (Format Operator)</span><span class="sxs-lookup"><span data-stu-id="2ce05-140">`-f` (format operator)</span></span>   | <span data-ttu-id="2ce05-141">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-141">[about_Operators][]</span></span>            |
| <span data-ttu-id="2ce05-142">`-` (Unär/negativ)</span><span class="sxs-lookup"><span data-stu-id="2ce05-142">`-` (unary/negative)</span></span>     | <span data-ttu-id="2ce05-143">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-143">[about_Arithmetic_Operators][]</span></span> |
| `* / %`                  | <span data-ttu-id="2ce05-144">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-144">[about_Arithmetic_Operators][]</span></span> |
| `+ -`                    | <span data-ttu-id="2ce05-145">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-145">[about_Arithmetic_Operators][]</span></span> |

<span data-ttu-id="2ce05-146">Die folgende Gruppe von Operatoren hat die gleiche Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="2ce05-146">The following group of operators have equal precedence.</span></span> <span data-ttu-id="2ce05-147">Die Unterscheidung nach Groß-/Kleinschreibung und explizite Unterscheidung nach Groß-/Kleinschreibung haben dieselbe Priorität</span><span class="sxs-lookup"><span data-stu-id="2ce05-147">Their case-sensitive and explicitly case-insensitive variants have the same precedence.</span></span>

|         <span data-ttu-id="2ce05-148">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="2ce05-148">OPERATOR</span></span>          |           <span data-ttu-id="2ce05-149">Angabe</span><span class="sxs-lookup"><span data-stu-id="2ce05-149">REFERENCE</span></span>            |
| ------------------------- | ------------------------------ |
| <span data-ttu-id="2ce05-150">`-split` ärer</span><span class="sxs-lookup"><span data-stu-id="2ce05-150">`-split` (binary)</span></span>         | <span data-ttu-id="2ce05-151">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-151">[about_Split][]</span></span>                |
| <span data-ttu-id="2ce05-152">`-join` ärer</span><span class="sxs-lookup"><span data-stu-id="2ce05-152">`-join` (binary)</span></span>          | <span data-ttu-id="2ce05-153">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-153">[about_Join][]</span></span>                 |
| `-is -isnot -as`          | <span data-ttu-id="2ce05-154">[about_Type_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-154">[about_Type_Operators][]</span></span>       |
| `-eq -ne -gt -gt -lt -le` | <span data-ttu-id="2ce05-155">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-155">[about_Comparison_Operators][]</span></span> |
| `-like -notlike`          | <span data-ttu-id="2ce05-156">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-156">[about_Comparison_Operators][]</span></span> |
| `-match -notmatch`        | <span data-ttu-id="2ce05-157">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-157">[about_Comparison_Operators][]</span></span> |
| `-in -notIn`              | <span data-ttu-id="2ce05-158">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-158">[about_Comparison_Operators][]</span></span> |
| `-contains -notContains`  | <span data-ttu-id="2ce05-159">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-159">[about_Comparison_Operators][]</span></span> |
| `-replace`                | <span data-ttu-id="2ce05-160">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-160">[about_Comparison_Operators][]</span></span> |

<span data-ttu-id="2ce05-161">Die Liste wird hier mit den folgenden Operatoren in der Rangfolge fortgesetzt:</span><span class="sxs-lookup"><span data-stu-id="2ce05-161">The list resumes here with the following operators in precedence order:</span></span>

|                <span data-ttu-id="2ce05-162">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="2ce05-162">OPERATOR</span></span>                 |           <span data-ttu-id="2ce05-163">Angabe</span><span class="sxs-lookup"><span data-stu-id="2ce05-163">REFERENCE</span></span>            |
| --------------------------------------- | ------------------------------ |
| `-band -bnot -bor -bxor -shr -shl`      | <span data-ttu-id="2ce05-164">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-164">[about_Arithmetic_Operators][]</span></span> |
| `-and -or -xor`                         | <span data-ttu-id="2ce05-165">[about_Logical_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-165">[about_Logical_Operators][]</span></span>    |

<span data-ttu-id="2ce05-166">Die folgenden Elemente sind keine true-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="2ce05-166">The following items are not true operators.</span></span> <span data-ttu-id="2ce05-167">Sie sind Teil der Befehlssyntax von PowerShell, nicht der Ausdruckssyntax.</span><span class="sxs-lookup"><span data-stu-id="2ce05-167">They are part of PowerShell's command syntax, not expression syntax.</span></span> <span data-ttu-id="2ce05-168">Die Zuweisung ist immer die letzte Aktion, die ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2ce05-168">Assignment is always the last action that happens.</span></span>

|                <span data-ttu-id="2ce05-169">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2ce05-169">SYNTAX</span></span>                   |           <span data-ttu-id="2ce05-170">Angabe</span><span class="sxs-lookup"><span data-stu-id="2ce05-170">REFERENCE</span></span>            |
| --------------------------------------- | ------------------------------ |
| <span data-ttu-id="2ce05-171">`.` (Punkt-Quelle)</span><span class="sxs-lookup"><span data-stu-id="2ce05-171">`.` (dot-source)</span></span>                        | <span data-ttu-id="2ce05-172">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-172">[about_Operators][]</span></span>            |
| <span data-ttu-id="2ce05-173">`&` erfordern</span><span class="sxs-lookup"><span data-stu-id="2ce05-173">`&` (call)</span></span>                              | <span data-ttu-id="2ce05-174">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-174">[about_Operators][]</span></span>            |
| <span data-ttu-id="2ce05-175"><code>&#124;</code> (Pipeline Operator)</span><span class="sxs-lookup"><span data-stu-id="2ce05-175"><code>&#124;</code> (pipeline operator)</span></span> | <span data-ttu-id="2ce05-176">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-176">[about_Operators][]</span></span>            |
| `> >> 2> 2>> 2>&1`                      | <span data-ttu-id="2ce05-177">[about_Redirection][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-177">[about_Redirection][]</span></span>          |
| `= += -= *= /= %=`                      | <span data-ttu-id="2ce05-178">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-178">[about_Assignment_Operators][]</span></span> |

## <a name="examples"></a><span data-ttu-id="2ce05-179">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2ce05-179">EXAMPLES</span></span>

<span data-ttu-id="2ce05-180">Die folgenden beiden Befehle zeigen die arithmetischen Operatoren und die Auswirkung der Verwendung von Klammern, um PowerShell zu erzwingen, den eingeschlossenen Teil des Ausdrucks zuerst auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="2ce05-180">The following two commands show the arithmetic operators and the effect of using parentheses to force PowerShell to evaluate the enclosed part of the expression first.</span></span>

```powershell
PS> 2 + 3 * 4
14

PS> (2 + 3) * 4
20
```

<span data-ttu-id="2ce05-181">Im folgenden Beispiel werden die schreibgeschützten Textdateien aus dem lokalen Verzeichnis abgerufen und in der Variablen gespeichert `$read_only` .</span><span class="sxs-lookup"><span data-stu-id="2ce05-181">The following example gets the read-only text files from the local directory and saves them in the `$read_only` variable.</span></span>

```powershell
$read_only = Get-ChildItem *.txt | Where-Object {$_.isReadOnly}
```

<span data-ttu-id="2ce05-182">Dies entspricht dem folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2ce05-182">It is equivalent to the following example.</span></span>

```powershell
$read_only = ( Get-ChildItem *.txt | Where-Object {$_.isReadOnly} )
```

<span data-ttu-id="2ce05-183">Da der Pipeline Operator ( `|` ) eine höhere Rangfolge aufweist als der Zuweisungs Operator ( `=` ), werden die Dateien, die das `Get-ChildItem` Cmdlet abruft, zum Filtern an das `Where-Object` Cmdlet gesendet, bevor Sie der Variablen zugewiesen werden `$read_only` .</span><span class="sxs-lookup"><span data-stu-id="2ce05-183">Because the pipeline operator (`|`) has a higher precedence than the assignment operator (`=`), the files that the `Get-ChildItem` cmdlet gets are sent to the `Where-Object` cmdlet for filtering before they are assigned to the `$read_only` variable.</span></span>

<span data-ttu-id="2ce05-184">Im folgenden Beispiel wird veranschaulicht, dass der Index Operator Vorrang vor dem Cast-Operator hat.</span><span class="sxs-lookup"><span data-stu-id="2ce05-184">The following example demonstrates that the index operator takes precedence over the cast operator.</span></span>

<span data-ttu-id="2ce05-185">Dieser Ausdruck erstellt ein Array aus drei Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="2ce05-185">This expression creates an array of three strings.</span></span> <span data-ttu-id="2ce05-186">Anschließend wird der Index Operator mit dem Wert 0 verwendet, um das erste Objekt im Array auszuwählen, das die erste Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="2ce05-186">Then, it uses the index operator with a value of 0 to select the first object in the array, which is the first string.</span></span> <span data-ttu-id="2ce05-187">Schließlich wird das ausgewählte Objekt in eine Zeichenfolge umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="2ce05-187">Finally, it casts the selected object as a string.</span></span> <span data-ttu-id="2ce05-188">In diesem Fall hat die Umwandlung keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="2ce05-188">In this case, the cast has no effect.</span></span>

```powershell
PS> [string]@('Windows','PowerShell','2.0')[0]
Windows
```

<span data-ttu-id="2ce05-189">Dieser Ausdruck verwendet Klammern, um zu erzwingen, dass der Umwandlungs Vorgang vor der Index Auswahl erfolgt.</span><span class="sxs-lookup"><span data-stu-id="2ce05-189">This expression uses parentheses to force the cast operation to occur before the index selection.</span></span> <span data-ttu-id="2ce05-190">Folglich wird das gesamte Array in eine (einzelne) Zeichenfolge umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="2ce05-190">As a result, the entire array is cast as a (single) string.</span></span> <span data-ttu-id="2ce05-191">Anschließend wählt der Index Operator das erste Element im Zeichen folgen Array aus, das das erste Zeichen ist.</span><span class="sxs-lookup"><span data-stu-id="2ce05-191">Then, the index operator selects the first item in the string array, which is the first character.</span></span>

```powershell
PS> ([string]@('Windows','PowerShell','2.0'))[0]
W
```

<span data-ttu-id="2ce05-192">Im folgenden Beispiel `-gt` ist das Ergebnis des Ausdrucks false, da der-Operator (größer als) Vorrang vor dem `-and` -Operator (logischer and) hat.</span><span class="sxs-lookup"><span data-stu-id="2ce05-192">In the following example, because the `-gt` (greater-than) operator has a higher precedence than the `-and` (logical AND) operator, the result of the expression is FALSE.</span></span>

```powershell
PS> 2 -gt 4 -and 1
False
```

<span data-ttu-id="2ce05-193">Dies entspricht dem folgenden Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="2ce05-193">It is equivalent to the following expression.</span></span>

```powershell
PS> (2 -gt 4) -and 1
False
```

<span data-ttu-id="2ce05-194">Wenn der-and-Operator eine höhere Rangfolge hat, wäre die Antwort true.</span><span class="sxs-lookup"><span data-stu-id="2ce05-194">If the -and operator had higher precedence, the answer would be TRUE.</span></span>

```powershell
PS> 2 -gt (4 -and 1)
True
```

<span data-ttu-id="2ce05-195">Dieses Beispiel veranschaulicht jedoch ein wichtiges Prinzip der Verwaltung der Operator Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="2ce05-195">However, this example demonstrates an important principle of managing operator precedence.</span></span> <span data-ttu-id="2ce05-196">Wenn die Interpretation eines Ausdrucks schwierig ist, verwenden Sie Klammern, um die Auswertungs Reihenfolge zu erzwingen, auch wenn Sie die Standard Operator Rangfolge erzwingt.</span><span class="sxs-lookup"><span data-stu-id="2ce05-196">When an expression is difficult for people to interpret, use parentheses to force the evaluation order, even when it forces the default operator precedence.</span></span> <span data-ttu-id="2ce05-197">Die Klammern machen Ihre Absichten für Personen klar, die Ihre Skripts lesen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="2ce05-197">The parentheses make your intentions clear to people who are reading and maintaining your scripts.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ce05-198">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="2ce05-198">SEE ALSO</span></span>

<span data-ttu-id="2ce05-199">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-199">[about_Operators][]</span></span>

<span data-ttu-id="2ce05-200">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-200">[about_Assignment_Operators][]</span></span>

<span data-ttu-id="2ce05-201">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-201">[about_Comparison_Operators][]</span></span>

<span data-ttu-id="2ce05-202">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-202">[about_Arithmetic_Operators][]</span></span>

<span data-ttu-id="2ce05-203">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-203">[about_Join][]</span></span>

<span data-ttu-id="2ce05-204">[about_Redirection][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-204">[about_Redirection][]</span></span>

<span data-ttu-id="2ce05-205">[about_Scopes][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-205">[about_Scopes][]</span></span>

<span data-ttu-id="2ce05-206">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-206">[about_Split][]</span></span>

<span data-ttu-id="2ce05-207">[about_Type_Operators][]</span><span class="sxs-lookup"><span data-stu-id="2ce05-207">[about_Type_Operators][]</span></span>

<!-- reference links -->
[about_Arithmetic_Operators]: about_Arithmetic_Operators.md
[about_Assignment_Operators]: about_Assignment_Operators.md
[about_Comparison_Operators]: about_Comparison_Operators.md
[about_Join]: about_Join.md
[about_Logical_Operators]: about_logical_operators.md
[about_Operators]: about_Operators.md
[about_Redirection]: about_Redirection.md
[about_Scopes]: about_Scopes.md
[about_Split]: about_Split.md
[about_Type_Operators]: about_Type_Operators.md
