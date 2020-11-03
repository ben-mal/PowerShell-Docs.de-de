---
description: Beschreibt eine sprach Anweisung, mit der Sie einen Befehls Block auf der Grundlage der Ergebnisse eines bedingten Tests ausführen können.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_while?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_While
ms.openlocfilehash: 60b944d3f09db786b54a1c7afb685543de808a92
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223711"
---
# <a name="about-while"></a>Ungefähr while

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt eine sprach Anweisung, mit der Sie einen Befehls Block auf der Grundlage der Ergebnisse eines bedingten Tests ausführen können.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Bei der while-Anweisung (auch als while-Schleife bezeichnet) handelt es sich um ein Sprachkonstrukt zum Erstellen einer Schleife, die Befehle in einem Befehls Block ausführt, solange ein bedingter Test als true ausgewertet wird. Die while-Anweisung ist einfacher zu konstruieren als eine for-Anweisung, da die Syntax weniger kompliziert ist. Außerdem ist er flexibler als die foreach-Anweisung, da Sie einen bedingten Test in der while-Anweisung angeben, um zu steuern, wie oft die Schleife ausgeführt wird.

Das folgende Beispiel zeigt die Syntax der while-Anweisung:

```powershell
while (<condition>){<statement list>}
```

Wenn Sie eine while-Anweisung ausführen, wertet PowerShell den `<condition>` Abschnitt der Anweisung aus, bevor Sie in den `<statement list>` Abschnitt wechseln. Der Bedingungs Teil der-Anweisung wird entweder in true oder false aufgelöst. Solange die Bedingung weiterhin zutrifft, führt PowerShell den Abschnitt erneut aus `<statement list>` .

Der- `<statement list>` Abschnitt der-Anweisung enthält mindestens einen Befehl, der jedes Mal ausgeführt wird, wenn die Schleife eingegeben oder wiederholt wird.

In der folgenden while-Anweisung werden z. b. die Zahlen 1 bis 3 angezeigt, wenn die $Val Variable nicht erstellt wurde oder wenn die $Val Variable erstellt und mit 0 initialisiert wurde.

```powershell
while($val -ne 3)
{
    $val++
    Write-Host $val
}
```

In diesem Beispiel ist die Bedingung ($Val nicht gleich 3), die $Val \= 0, 1, 2. Jedes Mal, wenn die Schleife durchlaufen wird, wird $Val mit dem \+ \+ unären Inkrementoperator ($Val) um 1 erhöht \+ \+ . Das letzte Mal durch die Schleife, $Val \= 3. Wenn $Val 3 entspricht, wird die Bedingungs Anweisung als false ausgewertet, und die Schleife wird beendet.

Wenn Sie diesen Befehl an der PowerShell-Eingabeaufforderung bequem schreiben möchten, können Sie ihn wie folgt eingeben:

```powershell
while($val -ne 3){$val++; Write-Host $val}
```

Beachten Sie, dass das Semikolon den ersten Befehl, der 1 hinzufügt, $Val aus dem zweiten Befehl trennt, der den Wert $Val in die Konsole schreibt.

## <a name="see-also"></a>SIEHE AUCH

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Do](about_Do.md)

[about_Foreach](about_Foreach.md)

[about_For](about_For.md)

[about_Language_Keywords](about_Language_Keywords.md)

