---
description: Beschreibt, wie die- `continue` Anweisung den Programmablauf sofort an den Anfang einer Programm Schleife, einer- `switch` Anweisung oder einer-Anweisung zurückgibt `trap` .
keywords: powershell,cmdlet
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_continue?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Continue
ms.openlocfilehash: 5a33451da91fa0d837b51ded6bae51ce66eb07e4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222127"
---
# <a name="about-continue"></a>Informationen zum Fortfahren

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt, wie die- `continue` Anweisung den Programmablauf sofort an den Anfang einer Programm Schleife, einer- `switch` Anweisung oder einer-Anweisung zurückgibt `trap` .

## <a name="long-description"></a>Lange Beschreibung

Die- `continue` Anweisung bietet eine Möglichkeit, den aktuellen Kontroll Block zu beenden und die Ausführung fortzusetzen, anstatt vollständig zu beenden. Die-Anweisung unterstützt Bezeichnungen.
Eine Bezeichnung ist ein Name, den Sie einer Anweisung in einem Skript zuweisen.

## <a name="using-continue-in-loops"></a>Verwenden von Continue in Schleifen

Eine unbezeichnete `continue` Anweisung gibt den Programmfluss sofort an den Anfang der innersten Schleife zurück, der von einer-,-,-oder-Anweisung gesteuert wird `for` `foreach` `do` `while` . Die aktuelle Iterations Schleife wird beendet, und die Schleife wird mit der nächsten Iterations Phase fortgesetzt.

Im folgenden Beispiel kehrt der Programmfluss an den Anfang der Schleife zurück, `while` Wenn die `$ctr` Variable gleich 5 ist. Folglich werden alle Zahlen zwischen 1 und 10 mit Ausnahme von 5 angezeigt:

```powershell
while ($ctr -lt 10)
{
    $ctr += 1
    if ($ctr -eq 5)
    {
        continue
    }

    Write-Host -Object $ctr
}
```

Bei Verwendung einer- `for` Schleife wird die Ausführung bei der Anweisung fortgesetzt `<Repeat>` , gefolgt vom `<Condition>` Test. Im folgenden Beispiel kommt es nicht zu einer Endlosschleife, da der Dekrement von `$i` nach dem- `continue` Schlüsselwort auftritt.

```powershell
#   <Init>  <Condition> <Repeat>
for ($i = 0; $i -lt 10; $i++)
{
    Write-Host -Object $i
    if ($i -eq 5)
    {
        continue
        # Will not result in an infinite loop.
        $i--
    }
}
```

### <a name="using-a-labeled-continue-in-a-loop"></a>Verwenden eines gekennzeichneten Continue in einer Schleife

Eine bezeichnete `continue` Anweisung beendet die Ausführung der Iterationen und überträgt die Steuerung an die zielschließende einschließende Iterations-oder `switch` Anweisungsbezeichnung.

Im folgenden Beispiel wird die innerste beendet, wenn den Wert `for` `$condition` **true** hat und die Iterationen mit der zweiten Schleife bei fortgesetzt werden `for` `labelB` .

```powershell
:labelA for ($i = 1; $i -le 10; $i++) {
    :labelB for ($j = 1; $j -le 10; $j++) {
        :labelC for ($k = 1; $k -le 10; $k++) {
            if ($condition) {
                continue labelB
            } else {
                $condition = Update-Condition
            }
        }
    }
}
```

## <a name="using-continue-in-a-switch-statement"></a>Verwenden von Continue in einer Switch-Anweisung

Eine unbezeichnete `continue` Anweisung in der `switch` beendet die Ausführung der aktuellen `switch` Iterationen und überträgt die Steuerung an den Anfang des `switch` , um das nächste Eingabe Element zu erhalten.

Wenn ein einzelnes Eingabe Element vorhanden ist, wird `continue` die gesamte- `switch` Anweisung beendet.
Wenn `switch` es sich bei der Eingabe um eine Auflistung handelt, `switch` testet jedes Element der Auflistung. Der `continue` beendet die aktuelle Iterations-und `switch` setzt mit dem nächsten Element fort.

```powershell
switch (1,2,3) {
  2 { continue }  # moves on to the next element, 3
  default { $_ }
}
```

```Output
1
3
```

## <a name="using-continue-in-a-trap-statement"></a>Verwenden von Continue in einer Trap-Anweisung

Wenn die letzte im Text einer-Anweisung ausgeführte Anweisung `trap` ist `continue` , wird der aufgefangenen Fehler automatisch ignoriert, und die Ausführung wird mit der-Anweisung fortgesetzt, die den Fehler verursacht hat `trap` .

## <a name="do-not-use-continue-outside-of-a-loop-switch-or-trap"></a>Nicht weiter außerhalb einer Schleife, eines Schalters oder eines Trap verwenden

Wenn `continue` außerhalb eines Konstrukts verwendet wird, das es direkt unterstützt (Schleifen, `switch` , `trap` ), sucht PowerShell _die-aufrufsstapel_ nach einem einschließenden Konstrukt. Wenn kein einschließendes Konstrukt gefunden werden kann, wird der aktuelle Runspace ruhig beendet.

Dies bedeutet, dass Funktionen und Skripts, die versehentlich einen `continue` außerhalb eines einschließenden Konstrukts verwenden, das es unter _callers_ stützt, ihre Aufrufer versehentlich beenden können.

Durch `continue` die Verwendung von in einer Pipeline, wie z. b. einem `ForEach-Object` Skriptblock, wird die Pipeline nicht nur beendet, sondern der gesamte Runspace wird möglicherweise beendet.

## <a name="see-also"></a>Weitere Informationen:

[about_Break](about_Break.md)

[about_For](about_For.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Throw](about_Throw.md)

[about_Trap](about_Trap.md)

[about_Try_Catch_Finally](about_Try_Catch_Finally.md)
