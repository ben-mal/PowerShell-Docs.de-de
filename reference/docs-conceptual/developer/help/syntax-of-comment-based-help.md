---
ms.date: 09/12/2016
ms.topic: reference
title: Syntax der kommentarbasierten Hilfe
description: Syntax der kommentarbasierten Hilfe
ms.openlocfilehash: 3866f25b40fc970e8d219af6f423b7a25f5b875c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659521"
---
# <a name="syntax-of-comment-based-help"></a>Syntax der kommentarbasierten Hilfe

In diesem Abschnitt wird die Syntax der Kommentar basierten Hilfe beschrieben.

## <a name="syntax-diagram"></a>Syntax Diagramm

 Die Syntax für die Kommentar basierte Hilfe lautet wie folgt:

```
# .< help keyword>
# <help content>

-or -

<#
.< help keyword>
< help content>
#>
```

## <a name="syntax-description"></a>Syntaxbeschreibung

 Die Kommentar basierte Hilfe wird als eine Reihe von Kommentaren geschrieben. Sie können `#` vor jeder Zeile von Kommentaren ein Kommentar Symbol () eingeben, oder Sie können das-Symbol und das-Symbol verwenden, `<#` `#>` um einen Kommentar Block zu erstellen. Alle Zeilen innerhalb des Kommentar Blocks werden als Kommentare interpretiert.

 Jeder Abschnitt der Kommentar basierten Hilfe wird durch ein Schlüsselwort definiert, und jedem Schlüsselwort wird ein Punkt ( `.` ) vorangestellt. Die Schlüsselwörter können in beliebiger Reihenfolge angezeigt werden. Beim Schlüsselwort Namen wird die Groß-/Kleinschreibung nicht beachtet.

 Ein Kommentar Block muss mindestens ein Hilfe Schlüsselwort enthalten. Einige der Schlüsselwörter (z. b. **beispielsweise**) können mehrmals im gleichen Kommentar Block vorkommen. Der Hilfe Inhalt für jedes Schlüsselwort beginnt in der Zeile nach dem-Schlüsselwort und kann sich über mehrere Zeilen erstrecken.

 Alle Zeilen in einem Kommentar basierten Hilfethema müssen zusammenhängend sein. Wenn ein Kommentar basiertes Hilfethema einem Kommentar folgt, der nicht Teil des Hilfe Themas ist, muss mindestens eine Leerzeile zwischen der letzten nicht-Hilfe Kommentarzeile und dem Anfang der Kommentar basierten Hilfe vorhanden sein.

 Beispielsweise enthält das folgende Kommentar basierte Hilfethema die. Description-Schlüsselwort und sein Wert, eine Beschreibung einer Funktion oder eines Skripts.

```powershell
<#
    .Description
    The Get-Function function displays the name and syntax of all functions in the session.
#>
```
