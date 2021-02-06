---
description: Beschreibt die Operatoren, die-Anweisungen in PowerShell verbinden.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logical_operators?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logical_Operators
ms.openlocfilehash: 8602551f3ecf74027b59715e1f47aab1b10bea92
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596139"
---
# <a name="about_logical_operators"></a>about_Logical_Operators

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt die Operatoren, die-Anweisungen in PowerShell verbinden.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Die logischen PowerShell-Operatoren verbinden Ausdrücke und Anweisungen, sodass Sie einen einzelnen Ausdruck verwenden können, um mehrere Bedingungen zu testen.

Beispielsweise verwendet die folgende Anweisung den and-Operator und den or-Operator, um drei bedingte Anweisungen zu verbinden. Die-Anweisung ist nur dann true, wenn der Wert von $a größer als der Wert $b ist und entweder $a oder $b kleiner als ist.
20.

```powershell
($a -gt $b) -and (($a -lt 20) -or ($b -lt 20))
```

PowerShell unterstützt die folgenden logischen Operatoren.

|Operator|BESCHREIBUNG                        |Beispiel                   |
|--------|-----------------------------------|--------------------------|
|`-and`  |Logisches AND. TRUE, wenn beide        |`(1 -eq 1) -and (1 -eq 2)`|
|        |-Anweisungen sind "true".               |`False`                   |
|`-or`   |Logisches OR. TRUE, wenn beide       |`(1 -eq 1) -or (1 -eq 2)` |
|        |die Anweisung ist "true".                 |`True`                    |
|`-xor`  |Logisches exklusives OR. TRUE, wenn    |`(1 -eq 1) -xor (2 -eq 2)`|
|        |nur eine Anweisung ist "true".         |`False`                   |
|`-not`  |Logisches Not. Negiert die Anweisung. |`-not (1 -eq 1)`          |
|        |Das folgt.                      |`False`                   |
|`!`     |Identisch mit `-not`                     |`!(1 -eq 1)`              |
|        |                                   |`False`                   |

 Anmerkung:

In den vorherigen Beispielen wird auch der Gleichheits Operator verwendet `-eq` . Weitere Informationen finden Sie unter [about_Comparison_Operators](about_Comparison_Operators.md). In den Beispielen werden auch die booleschen Werte von Ganzzahlen verwendet. Die Ganzzahl 0 hat den Wert false. Alle anderen Ganzzahlen haben den Wert "true".

Die Syntax der logischen Operatoren lautet wie folgt:

```
<statement> {-AND | -OR | -XOR} <statement>
{! | -NOT} <statement>
```

Anweisungen, die die logischen Operatoren verwenden, geben boolesche Werte (true oder false) zurück.

Die logischen Operatoren von PowerShell Werten nur die Anweisungen aus, die erforderlich sind, um den Wahrheitswert der Anweisung zu bestimmen. Wenn der linke Operand in einer-Anweisung, die den and-Operator enthält, false ist, wird der rechte Operand nicht ausgewertet.
Wenn der linke Operand in einer-Anweisung, die die-oder-Anweisung enthält, true ist, wird der rechte Operand nicht ausgewertet. Daher können Sie diese Anweisungen auf die gleiche Weise wie die- `If` Anweisung verwenden.

## <a name="see-also"></a>SIEHE AUCH

[about_Operators](about_Operators.md)

[Compare-Object](xref:Microsoft.PowerShell.Utility.Compare-Object)

[about_Comparison_operators](about_Comparison_Operators.md)

[about_If](about_If.md)

