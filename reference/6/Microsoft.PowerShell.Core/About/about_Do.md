---
description: Führt eine Anweisungs Liste einmal oder mehrmals aus, je nach while-oder until-Bedingung.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_do?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Do
ms.openlocfilehash: ac8ddca01611f4477d424426ccedf9a39af85a82
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221695"
---
# <a name="about-do"></a>Informationen zu do

## <a name="short-description"></a>KURZE BESCHREIBUNG
Führt eine Anweisungs Liste einmal oder mehrmals aus, je nach while-oder until-Bedingung.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Das do-Schlüsselwort funktioniert mit dem while-Schlüsselwort oder dem until-Schlüsselwort, um die Anweisungen in einem Skriptblock auszuführen, je nach Bedingung. Anders als bei der zugehörigen while-Schleife wird der Skriptblock in einer Do-Schleife immer mindestens einmal ausgeführt.

Eine **do-while-** Schleife ist eine Vielzahl der while-Schleife. In einer **do-while-** Schleife wird die Bedingung ausgewertet, nachdem der Skriptblock ausgeführt wurde. Wie in einer while-Schleife wird der Skriptblock wiederholt, solange die Bedingung als true ausgewertet wird.

Wie eine **do-while-** Schleife wird eine **Do-Until-** Schleife immer mindestens einmal ausgeführt, bevor die Bedingung ausgewertet wird. Der Skriptblock wird jedoch nur ausgeführt, während die Bedingung false ist.

Die Schlüsselwörter für die Fluss Steuerung " *Continue* " und " *break* " können in einer **do-while-** Schleife oder in einer **Do-Until-** Schleife verwendet werden.

### <a name="syntax"></a>Syntax

Das folgende Beispiel zeigt die Syntax der **do-while-** Anweisung:

```powershell
do {<statement list>} while (<condition>)
```

Das folgende Beispiel zeigt die Syntax der **Do-Until-** Anweisung:

```powershell
do {<statement list>} until (<condition>)
```

Die Anweisungs Liste enthält eine oder mehrere-Anweisungen, die jedes Mal ausgeführt werden, wenn die Schleife eingegeben oder wiederholt wird.

Der Bedingungs Teil der-Anweisung wird in true oder false aufgelöst.

### <a name="example"></a>Beispiel

Das folgende Beispiel einer Do-Anweisung zählt die Elemente in einem Array, bis Sie ein Element mit dem Wert 0 erreicht.

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } while ($x[$a] -ne 0)
C:\PS> $count
3
```

Im folgenden Beispiel wird das until-Schlüsselwort verwendet. Beachten Sie, dass der ungleich-Operator ( `-ne` ) durch den Gleichheits Operator () ersetzt wird `-eq` .

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } until ($x[$a] -eq 0)
C:\PS> $count
3
```

Im folgenden Beispiel werden alle Werte eines Arrays geschrieben, wobei jeder Wert übersprungen wird, der kleiner als 0 (null) ist.

```powershell
do {
  if ($x[$a] -lt 0) { continue }
  Write-Host $x[$a]
}
while (++$a -lt 10)
```

## <a name="see-also"></a>SIEHE AUCH

[about_While](about_While.md)

[about_Operators](about_Operators.md)

[about_Assignment_Operators](about_Assignment_Operators.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Break](about_Break.md)

[about_Continue](about_Continue.md)
