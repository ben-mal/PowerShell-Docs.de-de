---
description: Beschreibt einen Sprachbefehl, den Sie verwenden können, um-Anweisungen auf der Grundlage eines bedingten Tests auszuführen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 3/4/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_for?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_For
ms.openlocfilehash: 07037b73a5507bb0ef420ad39271be8832f7500b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220919"
---
# <a name="about-for"></a>Info zu

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt einen Sprachbefehl, den Sie verwenden können, um-Anweisungen auf der Grundlage eines bedingten Tests auszuführen.

## <a name="long-description"></a>Lange Beschreibung

Die- `For` Anweisung (auch als- `For` Schleife bezeichnet) ist ein Sprachkonstrukt, mit dem Sie eine-Schleife erstellen können, die Befehle in einem Befehls Block ausführt, während eine angegebene Bedingung als ausgewertet wird `$true` .

Eine typische Verwendung der `For` -Schleife besteht darin, ein Array von-Werten zu durchlaufen und eine Teilmenge dieser Werte zu verarbeiten. Wenn Sie alle Werte in einem Array durchlaufen möchten, sollten Sie in den meisten Fällen eine- `Foreach` Anweisung verwenden.

### <a name="syntax"></a>Syntax

Das folgende Beispiel zeigt die- `For` Anweisungs Syntax.

```
for (<Init>; <Condition>; <Repeat>)
{
    <Statement list>
}
```

Der **Init** -Platzhalter stellt einen oder mehrere Befehle dar, die vor Beginn der Schleife ausgeführt werden. In der Regel verwenden Sie den **Init** -Teil der-Anweisung, um eine Variable mit einem Startwert zu erstellen und zu initialisieren.

Diese Variable ist die Grundlage für die Bedingung, die im nächsten Teil der Anweisung getestet werden soll `For` .

Der **Bedingungs Platzhalter stellt den Teil** der- `For` Anweisung dar, der zu `$true` einem `$false` **booleschen Wert oder einem booleschen** Wert aufgelöst wird. PowerShell wertet die Bedingung bei jeder Ausführung der `For` Schleife aus. Wenn die-Anweisung ist `$true` , werden die Befehle im Befehls Block ausgeführt, und die-Anweisung wird erneut ausgewertet. Wenn die Bedingung weiterhin besteht `$true` , werden die Befehle in der **Anweisungs Liste** erneut ausgeführt. Die Schleife wird wiederholt, bis die Bedingung wird `$false` .

Der **Wiederholungs** Platzhalter stellt einen oder mehrere durch Kommas getrennte Befehle dar, die jedes Mal ausgeführt werden, wenn die Schleife wiederholt wird. In der Regel wird dies verwendet, um eine Variable zu ändern, die innerhalb des **Bedingungs Teils der** Anweisung getestet wird.

Der Platzhalter der **Anweisungs Liste** stellt einen Satz von mindestens einem Befehl dar, der jedes Mal ausgeführt wird, wenn die Schleife eingegeben oder wiederholt wird. Der Inhalt der **Anweisungs Liste** wird durch geschweifte Klammern eingeschlossen.

### <a name="support-for-multiple-operations"></a>Unterstützung für mehrere Vorgänge

Die folgenden Syntaxen werden für mehrere Zuweisungs Vorgänge in der **Init** -Anweisung unterstützt:

```powershell
# Comma separated assignment expressions enclosed in parenthesis.
for (($i = 0), ($j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}

# Sub-expression using the semicolon to separate statements.
for ($($i = 0;$j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}
```

Die folgenden Syntaxen werden bei mehreren Zuweisungs Vorgängen in der **Repeat** -Anweisung unterstützt:

```powershell
# Comma separated assignment expressions.
for (($i = 0), ($j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}

# Comma separated assignment expressions enclosed in parenthesis.
for (($i = 0), ($j = 0); $i -lt 10; ($i++), ($j++))
{
    "`$i:$i"
    "`$j:$j"
}

# Sub-expression using the semicolon to separate statements.
for ($($i = 0;$j = 0); $i -lt 10; $($i++;$j++))
{
    "`$i:$i"
    "`$j:$j"
}
```

> [!NOTE]
> Andere Vorgänge als Pre-oder Post-Inkrement funktionieren möglicherweise nicht für alle Syntaxen.

Verwenden Sie für mehrere **Bedingungen** logische Operatoren, wie im folgenden Beispiel gezeigt.

```powershell
for (($i = 0), ($j = 0); $i -lt 10 -and $j -lt 10; $i++,$j++)
{
    "`$i:$i"
    "`$j:$j"
}
```

Weitere Informationen finden Sie unter [about_Logical_Operators](about_Logical_Operators.md).

### <a name="examples"></a>Beispiele

Eine- `For` Anweisung erfordert mindestens die Klammer, die die Initialisierungs **Init** -, Bedingungs-und **Wiederholungs** Teile der Anweisung umgibt, sowie einen Befehl, der von geschweiften Klammern im **Anweisungs Listen** Teil der Anweisung umgeben **ist**.

Beachten Sie, dass in den bevorstehenden Beispielen absichtlich Code außerhalb der-Anweisung angezeigt wird `For` . In späteren Beispielen ist Code in die- `For` Anweisung integriert.

Beispielsweise zeigt die folgende `For` Anweisung den Wert der Variablen kontinuierlich an, `$i` bis Sie den Befehl manuell verlassen, indem Sie STRG + C drücken.

```powershell
$i = 1
for (;;)
{
    Write-Host $i
}
```

Sie können der Anweisungs Liste zusätzliche Befehle hinzufügen, sodass der Wert von `$i` bei jedem Ausführen der Schleife um 1 erhöht wird, wie im folgenden Beispiel gezeigt.

```powershell
for (;;)
{
    $i++; Write-Host $i
}
```

Bis Sie den Befehl durch Drücken von STRG + C verlassen, zeigt diese Anweisung fortlaufend den Wert der Variablen an, `$i` da Sie bei jedem Ausführen der Schleife um 1 erhöht wird.

Anstatt den Wert der Variablen im Anweisungs Listen Teil der Anweisung zu ändern `For` , können Sie stattdessen den **Wiederholungs** Teil der `For` Anweisung wie folgt verwenden.

```powershell
$i=1
for (;;$i++)
{
    Write-Host $i
}
```

Diese Anweisung wird nach wie vor unbegrenzt wiederholt, bis Sie den Befehl durch Drücken von STRG + C aufbrechen.

Sie können die `For` Schleife mit einer *Bedingung* beenden. Sie können **eine Bedingung mithilfe des Bedingungs Teils der** Anweisung platzieren `For` . Die- `For` Schleife wird beendet, wenn die Bedingung als ausgewertet wird `$false` .

Im folgenden Beispiel wird die- `For` Schleife ausgeführt, während der Wert von `$i` kleiner oder gleich 10 ist.

```powershell
$i=1
for(;$i -le 10;$i++)
{
    Write-Host $i
}
```

Anstatt die Variable außerhalb der-Anweisung zu erstellen und `For` zu initialisieren, können Sie diese Aufgabe innerhalb der-Schleife ausführen, `For` indem Sie den **Init** -Teil der- `For` Anweisung verwenden.

```powershell
for($i=1; $i -le 10; $i++){Write-Host $i}
```

Sie können Wagen Rückläufe anstelle von Semikolons verwenden, um die **Init** -, **Condition** -und **Repeat** -Teile der Anweisung zu begrenzen `For` . Das folgende Beispiel zeigt einen `For` , der diese alternative Syntax verwendet.

```powershell
for ($i = 0
  $i -lt 10
  $i++){
  $i
}
```

Diese alternative Form der `For` -Anweisung funktioniert in PowerShell-Skriptdateien und an der PowerShell-Eingabeaufforderung. Es ist jedoch einfacher, die `For` Anweisungs Syntax mit Semikolons zu verwenden, wenn Sie interaktive Befehle an der Eingabeaufforderung eingeben.

Die- `For` Schleife ist flexibler als die- `Foreach` Schleife, da Sie das Inkrement von Werten in einem Array oder einer Auflistung mithilfe von Mustern ermöglicht. Im folgenden Beispiel wird die- `$i` Variable im **Wiederholungs** Abschnitt der-Anweisung um 2 erhöht `For` .

```powershell
for ($i = 0; $i -le 20; $i += 2)
{
    Write-Host $i
}
```

Die- `For` Schleife kann auch in einer Zeile geschrieben werden, wie im folgenden Beispiel gezeigt.

```powershell
for ($i = 0; $i -lt 10; $i++) { Write-Host $i }
```

## <a name="see-also"></a>SIEHE AUCH

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Foreach](about_Foreach.md)

