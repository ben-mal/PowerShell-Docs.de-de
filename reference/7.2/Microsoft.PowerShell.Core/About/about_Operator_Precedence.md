---
description: Listet die PowerShell-Operatoren in der Rangfolge auf.
Locale: en-US
ms.date: 11/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operator_precedence?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operator_Precedence
ms.openlocfilehash: d4031a9d9a67340470d5418a9c2d3e33c5caed13
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603515"
---
# <a name="about-operator-precedence"></a><span data-ttu-id="0b0e9-103">Informationen zur Operator Rangfolge</span><span class="sxs-lookup"><span data-stu-id="0b0e9-103">About Operator Precedence</span></span>

## <a name="short-description"></a><span data-ttu-id="0b0e9-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0b0e9-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="0b0e9-105">Listet die PowerShell-Operatoren in der Rangfolge auf.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-105">Lists the PowerShell operators in precedence order.</span></span>

## <a name="long-description"></a><span data-ttu-id="0b0e9-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0b0e9-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="0b0e9-107">Mit PowerShell-Operatoren können Sie einfache, aber leistungsstarke Ausdrücke erstellen.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-107">PowerShell operators let you construct simple, but powerful expressions.</span></span> <span data-ttu-id="0b0e9-108">In diesem Thema werden die Operatoren in der Rangfolge aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-108">This topic lists the operators in precedence order.</span></span> <span data-ttu-id="0b0e9-109">Die Rangfolge ist die Reihenfolge, in der PowerShell die Operatoren auswertet, wenn mehrere Operatoren im gleichen Ausdruck vorkommen.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-109">Precedence order is the order in which PowerShell evaluates the operators when multiple operators appear in the same expression.</span></span>

<span data-ttu-id="0b0e9-110">Wenn Operatoren die gleiche Rangfolge aufweisen, wertet PowerShell Sie von links nach rechts aus, so wie Sie im Ausdruck angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-110">When operators have equal precedence, PowerShell evaluates them from left to right as they appear within the expression.</span></span> <span data-ttu-id="0b0e9-111">Ausnahmen sind Zuweisungs Operatoren, Umwandlungs Operatoren und Negations Operatoren ( `!` , `-not` , `-bnot` ), die von rechts nach links ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-111">The exceptions are the assignment operators, the cast operators, and the negation operators (`!`, `-not`, `-bnot`), which are evaluated from right to left.</span></span>

<span data-ttu-id="0b0e9-112">Sie können Gehäuse wie Klammern verwenden, um die standardmäßige Rangfolge zu überschreiben und PowerShell zu zwingen, den eingeschlossenen Teil eines Ausdrucks vor einem nicht eingeschlossenen Teil auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-112">You can use enclosures, such as parentheses, to override the standard precedence order and force PowerShell to evaluate the enclosed part of an expression before an unenclosed part.</span></span>

<span data-ttu-id="0b0e9-113">In der folgenden Liste werden Operatoren in der Reihenfolge aufgelistet, in der Sie ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-113">In the following list, operators are listed in the order that they are evaluated.</span></span> <span data-ttu-id="0b0e9-114">Operatoren in derselben Zeile oder in derselben Gruppe haben die gleiche Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-114">Operators on the same line, or in the same group, have equal precedence.</span></span>

<span data-ttu-id="0b0e9-115">In der Spalte Operator sind die Operatoren aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-115">The Operator column lists the operators.</span></span> <span data-ttu-id="0b0e9-116">In der Spalte Verweis ist das PowerShell-Hilfethema aufgeführt, in dem der-Operator beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-116">The Reference column lists the PowerShell Help topic in which the operator is described.</span></span> <span data-ttu-id="0b0e9-117">Um das Thema anzuzeigen, geben Sie ein `get-help <topic-name>` .</span><span class="sxs-lookup"><span data-stu-id="0b0e9-117">To display the topic, type `get-help <topic-name>`.</span></span>

|         <span data-ttu-id="0b0e9-118">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="0b0e9-118">OPERATOR</span></span>         |           <span data-ttu-id="0b0e9-119">Angabe</span><span class="sxs-lookup"><span data-stu-id="0b0e9-119">REFERENCE</span></span>            |
| ------------------------ | ------------------------------ |
| `$() @() () @{}`         | <span data-ttu-id="0b0e9-120">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-120">[about_Operators][]</span></span>            |
| <span data-ttu-id="0b0e9-121">`. ?.` (Member Access)</span><span class="sxs-lookup"><span data-stu-id="0b0e9-121">`. ?.` (member access)</span></span>   | <span data-ttu-id="0b0e9-122">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-122">[about_Operators][]</span></span>            |
| <span data-ttu-id="0b0e9-123">`::` Kum</span><span class="sxs-lookup"><span data-stu-id="0b0e9-123">`::` (static)</span></span>            | <span data-ttu-id="0b0e9-124">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-124">[about_Operators][]</span></span>            |
| <span data-ttu-id="0b0e9-125">`[0] ?[0]` (Index-Operator)</span><span class="sxs-lookup"><span data-stu-id="0b0e9-125">`[0] ?[0]` (index operator)</span></span> | <span data-ttu-id="0b0e9-126">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-126">[about_Operators][]</span></span>         |
| <span data-ttu-id="0b0e9-127">`[int]` (Umwandlungs Operatoren)</span><span class="sxs-lookup"><span data-stu-id="0b0e9-127">`[int]` (cast operators)</span></span> | <span data-ttu-id="0b0e9-128">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-128">[about_Operators][]</span></span>            |
| <span data-ttu-id="0b0e9-129">`-split` unären</span><span class="sxs-lookup"><span data-stu-id="0b0e9-129">`-split` (unary)</span></span>         | <span data-ttu-id="0b0e9-130">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-130">[about_Split][]</span></span>                |
| <span data-ttu-id="0b0e9-131">`-join` unären</span><span class="sxs-lookup"><span data-stu-id="0b0e9-131">`-join` (unary)</span></span>          | <span data-ttu-id="0b0e9-132">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-132">[about_Join][]</span></span>                 |
| <span data-ttu-id="0b0e9-133">`,` (Komma-Operator)</span><span class="sxs-lookup"><span data-stu-id="0b0e9-133">`,` (comma operator)</span></span>     | <span data-ttu-id="0b0e9-134">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-134">[about_Operators][]</span></span>            |
| `++ --`                  | <span data-ttu-id="0b0e9-135">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-135">[about_Assignment_Operators][]</span></span> |
| `! -not`                 | <span data-ttu-id="0b0e9-136">[about_Logical_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-136">[about_Logical_Operators][]</span></span>    |
| <span data-ttu-id="0b0e9-137">`..` (Bereichs Operator)</span><span class="sxs-lookup"><span data-stu-id="0b0e9-137">`..` (range operator)</span></span>    | <span data-ttu-id="0b0e9-138">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-138">[about_Operators][]</span></span>            |
| <span data-ttu-id="0b0e9-139">`-f` (Format Operator)</span><span class="sxs-lookup"><span data-stu-id="0b0e9-139">`-f` (format operator)</span></span>   | <span data-ttu-id="0b0e9-140">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-140">[about_Operators][]</span></span>            |
| <span data-ttu-id="0b0e9-141">`-` (Unär/negativ)</span><span class="sxs-lookup"><span data-stu-id="0b0e9-141">`-` (unary/negative)</span></span>     | <span data-ttu-id="0b0e9-142">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-142">[about_Arithmetic_Operators][]</span></span> |
| `* / %`                  | <span data-ttu-id="0b0e9-143">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-143">[about_Arithmetic_Operators][]</span></span> |
| `+ -`                    | <span data-ttu-id="0b0e9-144">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-144">[about_Arithmetic_Operators][]</span></span> |

<span data-ttu-id="0b0e9-145">Die folgende Gruppe von Operatoren hat die gleiche Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-145">The following group of operators have equal precedence.</span></span> <span data-ttu-id="0b0e9-146">Die Unterscheidung nach Groß-/Kleinschreibung und explizite Unterscheidung nach Groß-/Kleinschreibung haben dieselbe Priorität</span><span class="sxs-lookup"><span data-stu-id="0b0e9-146">Their case-sensitive and explicitly case-insensitive variants have the same precedence.</span></span>

|         <span data-ttu-id="0b0e9-147">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="0b0e9-147">OPERATOR</span></span>          |           <span data-ttu-id="0b0e9-148">Angabe</span><span class="sxs-lookup"><span data-stu-id="0b0e9-148">REFERENCE</span></span>            |
| ------------------------- | ------------------------------ |
| <span data-ttu-id="0b0e9-149">`-split` ärer</span><span class="sxs-lookup"><span data-stu-id="0b0e9-149">`-split` (binary)</span></span>         | <span data-ttu-id="0b0e9-150">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-150">[about_Split][]</span></span>                |
| <span data-ttu-id="0b0e9-151">`-join` ärer</span><span class="sxs-lookup"><span data-stu-id="0b0e9-151">`-join` (binary)</span></span>          | <span data-ttu-id="0b0e9-152">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-152">[about_Join][]</span></span>                 |
| `-is -isnot -as`          | <span data-ttu-id="0b0e9-153">[about_Type_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-153">[about_Type_Operators][]</span></span>       |
| `-eq -ne -gt -gt -lt -le` | <span data-ttu-id="0b0e9-154">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-154">[about_Comparison_Operators][]</span></span> |
| `-like -notlike`          | <span data-ttu-id="0b0e9-155">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-155">[about_Comparison_Operators][]</span></span> |
| `-match -notmatch`        | <span data-ttu-id="0b0e9-156">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-156">[about_Comparison_Operators][]</span></span> |
| `-in -notIn`              | <span data-ttu-id="0b0e9-157">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-157">[about_Comparison_Operators][]</span></span> |
| `-contains -notContains`  | <span data-ttu-id="0b0e9-158">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-158">[about_Comparison_Operators][]</span></span> |
| `-replace`                | <span data-ttu-id="0b0e9-159">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-159">[about_Comparison_Operators][]</span></span> |

<span data-ttu-id="0b0e9-160">Die Liste wird hier mit den folgenden Operatoren in der Rangfolge fortgesetzt:</span><span class="sxs-lookup"><span data-stu-id="0b0e9-160">The list resumes here with the following operators in precedence order:</span></span>

|                <span data-ttu-id="0b0e9-161">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="0b0e9-161">OPERATOR</span></span>                 |           <span data-ttu-id="0b0e9-162">Angabe</span><span class="sxs-lookup"><span data-stu-id="0b0e9-162">REFERENCE</span></span>            |
| --------------------------------------- | ------------------------------ |
| `-band -bnot -bor -bxor -shr -shl`      | <span data-ttu-id="0b0e9-163">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-163">[about_Arithmetic_Operators][]</span></span> |
| `-and -or -xor`                         | <span data-ttu-id="0b0e9-164">[about_Logical_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-164">[about_Logical_Operators][]</span></span>    |

<span data-ttu-id="0b0e9-165">Die folgenden Elemente sind keine true-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-165">The following items are not true operators.</span></span> <span data-ttu-id="0b0e9-166">Sie sind Teil der Befehlssyntax von PowerShell, nicht der Ausdruckssyntax.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-166">They are part of PowerShell's command syntax, not expression syntax.</span></span> <span data-ttu-id="0b0e9-167">Die Zuweisung ist immer die letzte Aktion, die ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-167">Assignment is always the last action that happens.</span></span>

|                <span data-ttu-id="0b0e9-168">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0b0e9-168">SYNTAX</span></span>                   |           <span data-ttu-id="0b0e9-169">Angabe</span><span class="sxs-lookup"><span data-stu-id="0b0e9-169">REFERENCE</span></span>            |
| --------------------------------------- | ------------------------------ |
| <span data-ttu-id="0b0e9-170">`.` (Punkt-Quelle)</span><span class="sxs-lookup"><span data-stu-id="0b0e9-170">`.` (dot-source)</span></span>                        | <span data-ttu-id="0b0e9-171">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-171">[about_Operators][]</span></span>            |
| <span data-ttu-id="0b0e9-172">`&` erfordern</span><span class="sxs-lookup"><span data-stu-id="0b0e9-172">`&` (call)</span></span>                              | <span data-ttu-id="0b0e9-173">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-173">[about_Operators][]</span></span>            |
| <span data-ttu-id="0b0e9-174">`? <if-true> : <if-false>` (Ternärer Operator)</span><span class="sxs-lookup"><span data-stu-id="0b0e9-174">`? <if-true> : <if-false>` (Ternary operator)</span></span> | <span data-ttu-id="0b0e9-175">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-175">[about_Operators][]</span></span>      |
| <span data-ttu-id="0b0e9-176">`??` (null-coalese-Operator)</span><span class="sxs-lookup"><span data-stu-id="0b0e9-176">`??` (null-coalese operator)</span></span>            | <span data-ttu-id="0b0e9-177">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-177">[about_Operators][]</span></span>            |
| <span data-ttu-id="0b0e9-178"><code>&#124;</code> (Pipeline Operator)</span><span class="sxs-lookup"><span data-stu-id="0b0e9-178"><code>&#124;</code> (pipeline operator)</span></span> | <span data-ttu-id="0b0e9-179">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-179">[about_Operators][]</span></span>            |
| `> >> 2> 2>> 2>&1`                      | <span data-ttu-id="0b0e9-180">[about_Redirection][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-180">[about_Redirection][]</span></span>          |
| <span data-ttu-id="0b0e9-181"><code>&& &#124;&#124;</code> (Pipeline Ketten Operatoren)</span><span class="sxs-lookup"><span data-stu-id="0b0e9-181"><code>&& &#124;&#124;</code> (pipeline chain operators)</span></span> | <span data-ttu-id="0b0e9-182">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-182">[about_Operators][]</span></span> |
| `= += -= *= /= %= ??=`                  | <span data-ttu-id="0b0e9-183">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-183">[about_Assignment_Operators][]</span></span> |

## <a name="examples"></a><span data-ttu-id="0b0e9-184">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0b0e9-184">EXAMPLES</span></span>

<span data-ttu-id="0b0e9-185">Die folgenden beiden Befehle zeigen die arithmetischen Operatoren und die Auswirkung der Verwendung von Klammern, um PowerShell zu erzwingen, den eingeschlossenen Teil des Ausdrucks zuerst auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-185">The following two commands show the arithmetic operators and the effect of using parentheses to force PowerShell to evaluate the enclosed part of the expression first.</span></span>

```powershell
PS> 2 + 3 * 4
14

PS> (2 + 3) * 4
20
```

<span data-ttu-id="0b0e9-186">Im folgenden Beispiel werden die schreibgeschützten Textdateien aus dem lokalen Verzeichnis abgerufen und in der Variablen gespeichert `$read_only` .</span><span class="sxs-lookup"><span data-stu-id="0b0e9-186">The following example gets the read-only text files from the local directory and saves them in the `$read_only` variable.</span></span>

```powershell
$read_only = Get-ChildItem *.txt | Where-Object {$_.isReadOnly}
```

<span data-ttu-id="0b0e9-187">Dies entspricht dem folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-187">It is equivalent to the following example.</span></span>

```powershell
$read_only = ( Get-ChildItem *.txt | Where-Object {$_.isReadOnly} )
```

<span data-ttu-id="0b0e9-188">Da der Pipeline Operator ( `|` ) eine höhere Rangfolge aufweist als der Zuweisungs Operator ( `=` ), werden die Dateien, die das `Get-ChildItem` Cmdlet abruft, zum Filtern an das `Where-Object` Cmdlet gesendet, bevor Sie der Variablen zugewiesen werden `$read_only` .</span><span class="sxs-lookup"><span data-stu-id="0b0e9-188">Because the pipeline operator (`|`) has a higher precedence than the assignment operator (`=`), the files that the `Get-ChildItem` cmdlet gets are sent to the `Where-Object` cmdlet for filtering before they are assigned to the `$read_only` variable.</span></span>

<span data-ttu-id="0b0e9-189">Im folgenden Beispiel wird veranschaulicht, dass der Index Operator Vorrang vor dem Cast-Operator hat.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-189">The following example demonstrates that the index operator takes precedence over the cast operator.</span></span>

<span data-ttu-id="0b0e9-190">Dieser Ausdruck erstellt ein Array aus drei Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-190">This expression creates an array of three strings.</span></span> <span data-ttu-id="0b0e9-191">Anschließend wird der Index Operator mit dem Wert 0 verwendet, um das erste Objekt im Array auszuwählen, das die erste Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-191">Then, it uses the index operator with a value of 0 to select the first object in the array, which is the first string.</span></span> <span data-ttu-id="0b0e9-192">Schließlich wird das ausgewählte Objekt in eine Zeichenfolge umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-192">Finally, it casts the selected object as a string.</span></span> <span data-ttu-id="0b0e9-193">In diesem Fall hat die Umwandlung keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-193">In this case, the cast has no effect.</span></span>

```powershell
PS> [string]@('Windows','PowerShell','2.0')[0]
Windows
```

<span data-ttu-id="0b0e9-194">Dieser Ausdruck verwendet Klammern, um zu erzwingen, dass der Umwandlungs Vorgang vor der Index Auswahl erfolgt.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-194">This expression uses parentheses to force the cast operation to occur before the index selection.</span></span> <span data-ttu-id="0b0e9-195">Folglich wird das gesamte Array in eine (einzelne) Zeichenfolge umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-195">As a result, the entire array is cast as a (single) string.</span></span> <span data-ttu-id="0b0e9-196">Anschließend wählt der Index Operator das erste Element im Zeichen folgen Array aus, das das erste Zeichen ist.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-196">Then, the index operator selects the first item in the string array, which is the first character.</span></span>

```powershell
PS> ([string]@('Windows','PowerShell','2.0'))[0]
W
```

<span data-ttu-id="0b0e9-197">Im folgenden Beispiel `-gt` ist das Ergebnis des Ausdrucks false, da der-Operator (größer als) Vorrang vor dem `-and` -Operator (logischer and) hat.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-197">In the following example, because the `-gt` (greater-than) operator has a higher precedence than the `-and` (logical AND) operator, the result of the expression is FALSE.</span></span>

```powershell
PS> 2 -gt 4 -and 1
False
```

<span data-ttu-id="0b0e9-198">Dies entspricht dem folgenden Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-198">It is equivalent to the following expression.</span></span>

```powershell
PS> (2 -gt 4) -and 1
False
```

<span data-ttu-id="0b0e9-199">Wenn der-and-Operator eine höhere Rangfolge hat, wäre die Antwort true.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-199">If the -and operator had higher precedence, the answer would be TRUE.</span></span>

```powershell
PS> 2 -gt (4 -and 1)
True
```

<span data-ttu-id="0b0e9-200">Dieses Beispiel veranschaulicht jedoch ein wichtiges Prinzip der Verwaltung der Operator Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-200">However, this example demonstrates an important principle of managing operator precedence.</span></span> <span data-ttu-id="0b0e9-201">Wenn die Interpretation eines Ausdrucks schwierig ist, verwenden Sie Klammern, um die Auswertungs Reihenfolge zu erzwingen, auch wenn Sie die Standard Operator Rangfolge erzwingt.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-201">When an expression is difficult for people to interpret, use parentheses to force the evaluation order, even when it forces the default operator precedence.</span></span> <span data-ttu-id="0b0e9-202">Die Klammern machen Ihre Absichten für Personen klar, die Ihre Skripts lesen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="0b0e9-202">The parentheses make your intentions clear to people who are reading and maintaining your scripts.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b0e9-203">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="0b0e9-203">SEE ALSO</span></span>

<span data-ttu-id="0b0e9-204">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-204">[about_Operators][]</span></span>

<span data-ttu-id="0b0e9-205">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-205">[about_Assignment_Operators][]</span></span>

<span data-ttu-id="0b0e9-206">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-206">[about_Comparison_Operators][]</span></span>

<span data-ttu-id="0b0e9-207">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-207">[about_Arithmetic_Operators][]</span></span>

<span data-ttu-id="0b0e9-208">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-208">[about_Join][]</span></span>

<span data-ttu-id="0b0e9-209">[about_Redirection][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-209">[about_Redirection][]</span></span>

<span data-ttu-id="0b0e9-210">[about_Scopes][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-210">[about_Scopes][]</span></span>

<span data-ttu-id="0b0e9-211">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-211">[about_Split][]</span></span>

<span data-ttu-id="0b0e9-212">[about_Type_Operators][]</span><span class="sxs-lookup"><span data-stu-id="0b0e9-212">[about_Type_Operators][]</span></span>

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
