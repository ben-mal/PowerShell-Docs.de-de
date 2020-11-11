---
description: Listet die PowerShell-Operatoren in der Rangfolge auf.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operator_precedence?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operator_Precedence
ms.openlocfilehash: 8f0f69f2328343b9655ebd0d7515a469565ff5f5
ms.sourcegitcommit: 768816a5c05cc2d07ffd84bed95b0499f4b49f2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94483099"
---
# <a name="about-operator-precedence"></a>Informationen zur Operator Rangfolge

## <a name="short-description"></a>KURZE BESCHREIBUNG
Listet die PowerShell-Operatoren in der Rangfolge auf.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Mit PowerShell-Operatoren können Sie einfache, aber leistungsstarke Ausdrücke erstellen. In diesem Thema werden die Operatoren in der Rangfolge aufgelistet. Die Rangfolge ist die Reihenfolge, in der PowerShell die Operatoren auswertet, wenn mehrere Operatoren im gleichen Ausdruck vorkommen.

Wenn Operatoren die gleiche Rangfolge aufweisen, wertet PowerShell Sie von links nach rechts aus, so wie Sie im Ausdruck angezeigt werden. Ausnahmen sind Zuweisungs Operatoren, Umwandlungs Operatoren und Negations Operatoren ( `!` , `-not` , `-bnot` ), die von rechts nach links ausgewertet werden.

Sie können Gehäuse wie Klammern verwenden, um die standardmäßige Rangfolge zu überschreiben und PowerShell zu zwingen, den eingeschlossenen Teil eines Ausdrucks vor einem nicht eingeschlossenen Teil auszuwerten.

In der folgenden Liste werden Operatoren in der Reihenfolge aufgelistet, in der Sie ausgewertet werden. Operatoren in derselben Zeile oder in derselben Gruppe haben die gleiche Rangfolge.

In der Spalte Operator sind die Operatoren aufgelistet. In der Spalte Verweis ist das PowerShell-Hilfethema aufgeführt, in dem der-Operator beschrieben wird. Um das Thema anzuzeigen, geben Sie ein `get-help <topic-name>` .

|         OPERATOR         |           Angabe            |
| ------------------------ | ------------------------------ |
| `$() @() () @{}`         | [about_Operators][]            |
| `. ?.` (Member Access)   | [about_Operators][]            |
| `::` Kum            | [about_Operators][]            |
| `[0] ?[0]` (Index-Operator) | [about_Operators][]         |
| `[int]` (Umwandlungs Operatoren) | [about_Operators][]            |
| `-split` unären         | [about_Split][]                |
| `-join` unären          | [about_Join][]                 |
| `,` (Komma-Operator)     | [about_Operators][]            |
| `++ --`                  | [about_Assignment_Operators][] |
| `! -not`                 | [about_Logical_Operators][]    |
| `..` (Bereichs Operator)    | [about_Operators][]            |
| `-f` (Format Operator)   | [about_Operators][]            |
| `-` (Unär/negativ)     | [about_Arithmetic_Operators][] |
| `* / %`                  | [about_Arithmetic_Operators][] |
| `+ -`                    | [about_Arithmetic_Operators][] |

Die folgende Gruppe von Operatoren hat die gleiche Rangfolge. Die Unterscheidung nach Groß-/Kleinschreibung und explizite Unterscheidung nach Groß-/Kleinschreibung haben dieselbe Priorität

|         OPERATOR          |           Angabe            |
| ------------------------- | ------------------------------ |
| `-split` ärer         | [about_Split][]                |
| `-join` ärer          | [about_Join][]                 |
| `-is -isnot -as`          | [about_Type_Operators][]       |
| `-eq -ne -gt -gt -lt -le` | [about_Comparison_Operators][] |
| `-like -notlike`          | [about_Comparison_Operators][] |
| `-match -notmatch`        | [about_Comparison_Operators][] |
| `-in -notIn`              | [about_Comparison_Operators][] |
| `-contains -notContains`  | [about_Comparison_Operators][] |
| `-replace`                | [about_Comparison_Operators][] |

Die Liste wird hier mit den folgenden Operatoren in der Rangfolge fortgesetzt:

|                OPERATOR                 |           Angabe            |
| --------------------------------------- | ------------------------------ |
| `-band -bnot -bor -bxor -shr -shl`      | [about_Arithmetic_Operators][] |
| `-and -or -xor`                         | [about_Logical_Operators][]    |

Die folgenden Elemente sind keine true-Operatoren. Sie sind Teil der Befehlssyntax von PowerShell, nicht der Ausdruckssyntax. Die Zuweisung ist immer die letzte Aktion, die ausgeführt wird.

|                SYNTAX                   |           Angabe            |
| --------------------------------------- | ------------------------------ |
| `.` (Punkt-Quelle)                        | [about_Operators][]            |
| `&` erfordern                              | [about_Operators][]            |
| `? <if-true> : <if-false>` (Ternärer Operator) | [about_Operators][]      |
| `??` (null-coalese-Operator)            | [about_Operators][]            |
| <code>&#124;</code> (Pipeline Operator) | [about_Operators][]            |
| `> >> 2> 2>> 2>&1`                      | [about_Redirection][]          |
| <code>&& &#124;&#124;</code> (Pipeline Ketten Operatoren) | [about_Operators][] |
| `= += -= *= /= %= ??=`                  | [about_Assignment_Operators][] |

## <a name="examples"></a>BEISPIELE

Die folgenden beiden Befehle zeigen die arithmetischen Operatoren und die Auswirkung der Verwendung von Klammern, um PowerShell zu erzwingen, den eingeschlossenen Teil des Ausdrucks zuerst auszuwerten.

```powershell
PS> 2 + 3 * 4
14

PS> (2 + 3) * 4
20
```

Im folgenden Beispiel werden die schreibgeschützten Textdateien aus dem lokalen Verzeichnis abgerufen und in der Variablen gespeichert `$read_only` .

```powershell
$read_only = Get-ChildItem *.txt | Where-Object {$_.isReadOnly}
```

Dies entspricht dem folgenden Beispiel.

```powershell
$read_only = ( Get-ChildItem *.txt | Where-Object {$_.isReadOnly} )
```

Da der Pipeline Operator ( `|` ) eine höhere Rangfolge aufweist als der Zuweisungs Operator ( `=` ), werden die Dateien, die das `Get-ChildItem` Cmdlet abruft, zum Filtern an das `Where-Object` Cmdlet gesendet, bevor Sie der Variablen zugewiesen werden `$read_only` .

Im folgenden Beispiel wird veranschaulicht, dass der Index Operator Vorrang vor dem Cast-Operator hat.

Dieser Ausdruck erstellt ein Array aus drei Zeichen folgen. Anschließend wird der Index Operator mit dem Wert 0 verwendet, um das erste Objekt im Array auszuwählen, das die erste Zeichenfolge ist. Schließlich wird das ausgewählte Objekt in eine Zeichenfolge umgewandelt. In diesem Fall hat die Umwandlung keine Auswirkung.

```powershell
PS> [string]@('Windows','PowerShell','2.0')[0]
Windows
```

Dieser Ausdruck verwendet Klammern, um zu erzwingen, dass der Umwandlungs Vorgang vor der Index Auswahl erfolgt. Folglich wird das gesamte Array in eine (einzelne) Zeichenfolge umgewandelt. Anschließend wählt der Index Operator das erste Element im Zeichen folgen Array aus, das das erste Zeichen ist.

```powershell
PS> ([string]@('Windows','PowerShell','2.0'))[0]
W
```

Im folgenden Beispiel `-gt` ist das Ergebnis des Ausdrucks false, da der-Operator (größer als) Vorrang vor dem `-and` -Operator (logischer and) hat.

```powershell
PS> 2 -gt 4 -and 1
False
```

Dies entspricht dem folgenden Ausdruck.

```powershell
PS> (2 -gt 4) -and 1
False
```

Wenn der-and-Operator eine höhere Rangfolge hat, wäre die Antwort true.

```powershell
PS> 2 -gt (4 -and 1)
True
```

Dieses Beispiel veranschaulicht jedoch ein wichtiges Prinzip der Verwaltung der Operator Rangfolge. Wenn die Interpretation eines Ausdrucks schwierig ist, verwenden Sie Klammern, um die Auswertungs Reihenfolge zu erzwingen, auch wenn Sie die Standard Operator Rangfolge erzwingt. Die Klammern machen Ihre Absichten für Personen klar, die Ihre Skripts lesen und verwalten.

## <a name="see-also"></a>SIEHE AUCH

[about_Operators][]

[about_Assignment_Operators][]

[about_Comparison_Operators][]

[about_Arithmetic_Operators][]

[about_Join][]

[about_Redirection][]

[about_Scopes][]

[about_Split][]

[about_Type_Operators][]

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
