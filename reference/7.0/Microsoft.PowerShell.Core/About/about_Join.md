---
description: Beschreibt, wie der Joinoperator (-Join) mehrere Zeichen folgen zu einer einzelnen Zeichenfolge kombiniert.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_join?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Join
ms.openlocfilehash: d89b9066ef34e814c0e546246c7b50cfc73bcb38
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222252"
---
# <a name="about-join"></a>Informationen zum Join

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt, wie der Joinoperator (-Join) mehrere Zeichen folgen zu einer einzelnen Zeichenfolge kombiniert.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Der Join-Operator verkettet eine Reihe von Zeichen folgen zu einer einzelnen Zeichenfolge. Die Zeichen folgen werden in der Reihenfolge, in der Sie im Befehl angezeigt werden, an die resultierende Zeichenfolge angehängt.

### <a name="syntax"></a>Syntax

Das folgende Diagramm zeigt die Syntax für den Join-Operator.

```powershell
-Join <String[]>
<String[]> -Join <Delimiter>
```

#### <a name="parameters"></a>Parameter

String []: gibt eine oder mehrere Zeichen folgen an, die verknüpft werden sollen.

Delimiter: gibt ein oder mehrere Zeichen an, die zwischen den verketteten Zeichen folgen platziert werden. Der Standardwert ist kein Trennzeichen ("").

Hinweise

Der unäre Joinoperator (-Join <String [] >) hat Vorrang vor einem Komma. Wenn Sie daher eine durch Trennzeichen getrennte Liste von Zeichen folgen an den unären Joinoperator übermitteln, wird nur die erste Zeichenfolge (vor dem ersten Komma) an den Join-Operator übermittelt.

Um den unären Join-Operator zu verwenden, schließen Sie die Zeichen folgen in Klammern ein, oder speichern Sie die Zeichen folgen in einer Variablen, und senden Sie dann die Variable an Join.

Beispiel:

```powershell
-join "a", "b", "c"
a
b
c

-join ("a", "b", "c")
abc

$z = "a", "b", "c"
-join $z
abc
```

### <a name="examples"></a>Beispiele

Die folgende Anweisung verbindet drei Zeichen folgen:

```powershell
-join ("Windows", "PowerShell", "2.0")
WindowsPowerShell2.0
```

Die folgende Anweisung verbindet drei Zeichen folgen, die durch ein Leerzeichen voneinander getrennt sind:

```powershell
"Windows", "PowerShell", "2.0" -join " "
Windows PowerShell 2.0
```

In den folgenden Anweisungen wird ein Trennzeichen für mehrere Zeichen verwendet, um drei Zeichen folgen zu verknüpfen:

```powershell
$a = "WIND", "S P", "ERSHELL"
$a -join "OW"
WINDOWS POWERSHELL
```

Die folgende Anweisung verbindet die Zeilen in einer here-Zeichenfolge mit einer einzelnen Zeichenfolge. Da eine here-Zeichenfolge eine Zeichenfolge ist, müssen die Zeilen in der here-Zeichenfolge aufgeteilt werden, bevor Sie verknüpft werden können. Sie können diese Methode verwenden, um die Zeichen folgen in einer XML-Datei, die in einer here-Zeichenfolge gespeichert wurde, erneut hinzuzufügen:

```powershell
$a = @'
a
b
c
'@

(-split $a) -join " "
a b c
```

## <a name="see-also"></a>SIEHE AUCH

[about_Operators](about_Operators.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Split](about_Split.md)
