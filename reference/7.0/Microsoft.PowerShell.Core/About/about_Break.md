---
description: Beschreibt eine-Anweisung, die Sie zum sofortigen Beenden von-,-,-,-oder-Anweisungen verwenden können `foreach` `for` `while` `do` `switch` `trap` .
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_break?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Break
ms.openlocfilehash: 4dbc1a09ca4ec317c4756c65058f661ec41a513a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220759"
---
# <a name="about-break"></a>Info zur Pause

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt eine-Anweisung, die Sie zum sofortigen Beenden von-,-,-,-oder-Anweisungen verwenden können `foreach` `for` `while` `do` `switch` `trap` .

## <a name="long-description"></a>Lange Beschreibung

Die- `break` Anweisung bietet eine Möglichkeit, den aktuellen Kontroll Block zu beenden.
Die Ausführung wird bei der nächsten Anweisung nach dem Kontroll Block fortgesetzt. Die-Anweisung unterstützt Bezeichnungen. Eine Bezeichnung ist ein Name, den Sie einer Anweisung in einem Skript zuweisen.

## <a name="using-break-in-loops"></a>Verwenden von Break in-Schleifen

Wenn eine- `break` Anweisung in einer-Schleife, z. b. einer-,-,-oder-Schleife, angezeigt `foreach` `for` `do` `while` wird, beendet PowerShell sofort die Schleife.

Eine- `break` Anweisung kann eine Bezeichnung enthalten, mit der Sie eingebettete Schleifen beenden können. Eine Bezeichnung kann ein beliebiges Schleifen Schlüsselwort (z `foreach` `for` . b., oder) `while` in einem Skript angeben.

Im folgenden Beispiel wird gezeigt, wie eine-Anweisung verwendet wird `break` , um eine-Anweisung zu beenden `for` :

```powershell
for($i=1; $i -le 10; $i++) {
   Write-Host $i
   break
}
```

In diesem Beispiel wird die-Schleife durch die- `break` Anweisung beendet, `for` Wenn die- `$i` Variable 1 ist. Obwohl die- `for` Anweisung zu **true** ausgewertet `$i` wird, bis größer als 10 ist, erreicht PowerShell die Break-Anweisung, wenn die Schleife zum ersten Mal `for` ausgeführt wird.

Häufig wird die-Anweisung in einer-Schleife verwendet, in der `break` eine innere Bedingung erfüllt werden muss. Beachten Sie das folgende Beispiel für eine `foreach` Anweisung:

```powershell
$i=0
$varB = 10,20,30,40
foreach ($val in $varB) {
  if ($val -eq 30) {
    break
  }
  $i++
}
Write-Host "30 was found in array index $i"
```

In diesem Beispiel `foreach` iteriert die-Anweisung das `$varB` Array. Die `if` -Anweisung wird zum ersten Mal als false ausgewertet, und die Variable `$i` wird um 1 erhöht. Der dritte Zeitpunkt, an dem die Schleife ausgeführt wird, `$i` gleich 2 und die `$val` Variable gleich 30. An diesem Punkt wird die `break` -Anweisung ausgeführt, und die- `foreach` Schleife wird beendet.

### <a name="using-a-labeled-break-in-a-loop"></a>Verwenden einer beschrifteten Unterbrechung in einer Schleife

Eine- `break` Anweisung kann eine Bezeichnung enthalten. Wenn Sie das- `break` Schlüsselwort mit einer Bezeichnung verwenden, beendet PowerShell die bezeichnete Schleife, anstatt die aktuelle Schleife zu beenden.
Die Bezeichnung ist ein Doppelpunkt, gefolgt von dem Namen, den Sie zuweisen. Die Bezeichnung muss das erste Token in einer-Anweisung sein, und es muss das Schleifen Schlüsselwort folgen, z `while` . b..

`break` Verschiebt die Ausführung aus der gekennzeichneten Schleife. In eingebetteten Schleifen hat dies ein anderes Ergebnis als das- `break` Schlüsselwort, wenn es von sich selbst verwendet wird. Dieses Beispiel enthält eine- `while` Anweisung mit einer- `for` Anweisung:

```powershell
:myLabel while (<condition 1>) {
  for ($item in $items) {
    if (<condition 2>) {
      break myLabel
    }
    $item = $x   # A statement inside the For-loop
  }
}
$a = $c  # A statement after the labeled While-loop
```

Wenn Bedingung 2 als **true** ausgewertet wird, wird die Ausführung des Skripts nach der gekennzeichneten Schleife auf die Anweisung überspringt. Im Beispiel beginnt die Ausführung erneut mit der-Anweisung `$a = $c` .

Sie können viele bezeichnete Schleifen schachteln, wie im folgenden Beispiel gezeigt.

```powershell
:red while (<condition1>) {
  :yellow while (<condition2>) {
    while (<condition3>) {
      if ($a) {break}
      if ($b) {break red}
      if ($c) {break yellow}
    }
    Write-Host "After innermost loop"
  }
  Write-Host "After yellow loop"
}
Write-Host "After red loop"
```

Wenn die `$b` Variable als true ausgewertet wird, wird die Ausführung des Skripts nach der Schleife mit der Bezeichnung "Red" fortgesetzt. Wenn die Auswertung der `$c` Variablen true ergibt, wird die Ausführung des Skript Steuer Elements nach der als "gelb" bezeichneten Schleife fortgesetzt.

Wenn die `$a` Variable als true ausgewertet wird, wird die Ausführung nach der innersten Schleife fortgesetzt. Es ist keine Bezeichnung erforderlich.

PowerShell beschränkt nicht, wie weit Bezeichnungen die Ausführung fortsetzen können. Die Bezeichnung kann sogar die Steuerung über Skript-und Funktionsaufrufe hinweg übergeben.

## <a name="using-break-in-a-switch-statement"></a>Verwenden von Break in einer Switch-Anweisung

In einem `switch` Konstrukt bewirkt, dass `break` PowerShell den `switch` Codeblock verlässt.

Das- `break` Schlüsselwort wird verwendet, um das-Konstrukt zu verlassen `switch` . Beispielsweise verwendet die folgende `switch` Anweisung- `break` Anweisungen, um die spezifischsten Bedingungen zu testen:

```powershell
$var = "word2"
switch -regex ($var) {
    "word2" {
      Write-Host "Exact" $_
      break
    }

    "word.*" {
      Write-Host "Match on the prefix" $_
      break
    }

    "w.*" {
      Write-Host "Match on at least the first letter" $_
      break
    }

    default {
      Write-Host "No match" $_
      break
    }
}
```

In diesem Beispiel wird die `$var` -Variable erstellt und mit einem Zeichen folgen Wert initialisiert `word2` . Die `switch` Anweisung verwendet die **Regex** -Klasse, um den Variablen Wert zuerst mit dem Begriff abzugleichen `word2` . Da der Variablen Wert und der erste Test in der `switch` Anweisung Stimmen, wird der erste Codeblock in der `switch` Anweisung ausgeführt.

Wenn PowerShell die erste `break` Anweisung erreicht, wird die- `switch` Anweisung beendet. Wenn die vier `break` Anweisungen aus dem Beispiel entfernt werden, sind alle vier Bedingungen erfüllt. In diesem Beispiel wird die- `break` Anweisung verwendet, um Ergebnisse anzuzeigen, wenn die spezifischsten Bedingungen erfüllt sind.

## <a name="using-break-in-a-trap-statement"></a>Verwenden von Break in einer Trap-Anweisung

Wenn die letzte im Text einer-Anweisung ausgeführte Anweisung `trap` ist `break` , wird das Fehler Objekt unterdrückt, und die Ausnahme wird erneut ausgelöst.

Im folgenden Beispiel wird eine **DivideByZeroException** -Ausnahme erstellt, die mithilfe der-Anweisung eingefangen wird `trap` .

```powershell
function test {
  trap [DivideByZeroException] {
    Write-Host 'divide by zero trapped'
    break
  }

  $i = 3
  'Before loop'
  while ($true) {
     "1 / $i = " + (1 / $i--)
  }
  'After loop'
}
test
```

Beachten Sie, dass die Ausführung bei der Ausnahme beendet wird. Der `After loop` wird niemals erreicht.
Die Ausnahme wird erneut ausgelöst, nachdem `trap` ausgeführt wurde.

```Output
Before loop
1 / 3 = 0.333333333333333
1 / 2 = 0.5
1 / 1 = 1
divide by zero trapped
ParentContainsErrorRecordException:
Line |
  10 |       "1 / $i = " + (1 / $i--)
     |       ~~~~~~~~~~~~~~~~~~~~~~~~
     | Attempted to divide by zero.
```

## <a name="do-not-use-break-outside-of-a-loop-switch-or-trap"></a>Verwenden Sie keine Unterbrechung außerhalb einer Schleife, eines Schalters oder eines Trap

Wenn `break` außerhalb eines Konstrukts verwendet wird, das es direkt unterstützt (Schleifen, `switch` , `trap` ), sucht PowerShell _die-aufrufsstapel_ nach einem einschließenden Konstrukt. Wenn kein einschließendes Konstrukt gefunden werden kann, wird der aktuelle Runspace ruhig beendet.

Dies bedeutet, dass Funktionen und Skripts, die versehentlich einen `break` außerhalb eines einschließenden Konstrukts verwenden, das es _callers_ unterstützt, ihre Aufrufer versehentlich beenden können.

Durch die Verwendung von `break` in einer Pipeline `break` , wie z. b. einem `ForEach-Object` Skriptblock, wird die Pipeline nicht nur beendet, sondern der gesamte Runspace wird möglicherweise beendet.

## <a name="see-also"></a>Weitere Informationen:

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Continue](about_Continue.md)

[about_For](about_For.md)

[about_Foreach](about_Foreach.md)

[about_Switch](about_Switch.md)

[about_Throw](about_Throw.md)

[about_Trap](about_Trap.md)

[about_Try_Catch_Finally](about_Try_Catch_Finally.md)

[about_While](about_While.md)
