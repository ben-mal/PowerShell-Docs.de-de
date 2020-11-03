---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-command?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Command
ms.openlocfilehash: 970c72d5661796c25d6beb30eb08b6cd7032ceb1
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211183"
---
# Measure-Command

## ZUSAMMENFASSUNG
Misst die Ausführungszeit von Skriptblöcken und Cmdlets.

## SYNTAX

```
Measure-Command [-InputObject <PSObject>] [-Expression] <ScriptBlock> [<CommonParameters>]
```

## DESCRIPTION

Das `Measure-Command` Cmdlet führt einen Skriptblock oder ein Cmdlet intern aus, bei der Ausführung des Vorgangs und beim Zurückgeben der Ausführungszeit.

> [!NOTE]
> Skriptblöcke `Measure-Command` , die ausgeführt werden, werden im aktuellen Bereich ausgeführt, nicht unter einem untergeordneten Bereich.

## BEISPIELE

### Beispiel 1: Messen eines Befehls

In diesem Beispiel wird die Zeit gemessen, die benötigt wird, um einen `Get-EventLog` Befehl auszuführen, mit dem die Ereignisse im Windows PowerShell-Ereignisprotokoll abgerufen werden.

```powershell
Measure-Command { Get-EventLog "windows powershell" }
```

### Beispiel 2: Vergleichen von zwei Ausgaben aus Measure-Command

Der erste Befehl misst die Zeit, die zum Verarbeiten eines rekursiven Befehls benötigt wird `Get-ChildItem` , der den **path** -Parameter verwendet, um nur `.txt` Dateien im `C:\Windows` Verzeichnis und seinen Unterverzeichnissen abzurufen.

Der zweite Befehl misst die Zeit, die zum Verarbeiten eines rekursiven Befehls benötigt wird `Get-ChildItem` , der den anbieterspezifischen Parameter verwendet.

Diese Befehle zeigen den Wert der Verwendung eines anbieterspezifischen Filters in PowerShell-Befehlen.

```powershell
Measure-Command { Get-ChildItem -Path C:\Windows\*.txt -Recurse }
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 8
Milliseconds      : 618
Ticks             : 86182763
TotalDays         : 9.9748568287037E-05
TotalHours        : 0.00239396563888889
TotalMinutes      : 0.143637938333333
TotalSeconds      : 8.6182763
TotalMilliseconds : 8618.2763
```

```powershell
Measure-Command {Get-ChildItem C:\Windows -Filter "*.txt" -Recurse}
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 1
Milliseconds      : 140
Ticks             : 11409189
TotalDays         : 1.32050798611111E-05
TotalHours        : 0.000316921916666667
TotalMinutes      : 0.019015315
TotalSeconds      : 1.1409189
TotalMilliseconds : 1140.9189
```

### Beispiel 3: übertragen von Eingaben an Measure-Command

Objekte, die an weitergeleitet werden, `Measure-Command` sind für den Skriptblock verfügbar, der an den **Expression** -Parameter übergeben wird. Der Skriptblock wird einmal für jedes Objekt in der Pipeline ausgeführt.

```powershell
# Perform a simple operation to demonstrate the InputObject parameter
# Note that no output is displayed.
10, 20, 50 | Measure-Command -Expression { for ($i=0; $i -lt $_; $i++) {$i} }
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 12
Ticks             : 122672
TotalDays         : 1.41981481481481E-07
TotalHours        : 3.40755555555556E-06
TotalMinutes      : 0.000204453333333333
TotalSeconds      : 0.0122672
TotalMilliseconds : 12.2672
```

### Beispiel 4: Anzeigen der Ausgabe des gemessenen Befehls

Um die Ausgabe des Ausdrucks in anzuzeigen, `Measure-Command` können Sie eine Pipe zu verwenden `Out-Default` .

```powershell
# Perform the same operation as above adding Out-Default to every execution.
# This will show that the ScriptBlock is in fact executing for every item.
10, 20, 50 | Measure-Command -Expression {for ($i=0; $i -lt $_; $i++) {$i}; "$($_)" | Out-Default }
```

```Output
10
20
50


Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 11
Ticks             : 113745
TotalDays         : 1.31649305555556E-07
TotalHours        : 3.15958333333333E-06
TotalMinutes      : 0.000189575
TotalSeconds      : 0.0113745
TotalMilliseconds : 11.3745
```

### Beispiel 5: Messen der Ausführung in einem untergeordneten Bereich

`Measure-Command` führt den Skriptblock im aktuellen Bereich aus, sodass der Skriptblock Werte im aktuellen Bereich ändern kann. Um Änderungen am aktuellen Gültigkeitsbereich zu vermeiden, müssen Sie den Skriptblock in geschweiften Klammern () umschließen `{}` und den Aufruf Operator ( `&` ) verwenden, um den Block in einem untergeordneten Bereich auszuführen.

```powershell
$foo = 'Value 1'
$null = Measure-Command { $foo = 'Value 2' }
$foo
$null = Measure-Command { & { $foo = 'Value 3' } }
$foo
```

```Output
Value 2
Value 2
```

Weitere Informationen zum Aufruf Operator finden Sie unter [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md#call-operator-).

## PARAMETERS

### -Ausdruck

Gibt den Ausdruck an, dessen Ausführungsdauer gemessen wird. Schließen Sie den Ausdruck in geschweifte Klammern ( `{}` ) ein.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

An den **Inputobject** -Parameter gebundene Objekte sind optionale Eingaben für den Skriptblock, der an den **Expression** -Parameter übergeben wird. Innerhalb des Skript Blocks `$_` kann verwendet werden, um auf das aktuelle Objekt in der Pipeline zu verweisen.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können ein Objekt über die Pipeline an übergeben `Measure-Command` .

## AUSGABEN

### System.TimeSpan

`Measure-Command` Gibt ein Zeitspannen Objekt zurück, das das Ergebnis darstellt.

## HINWEISE

## VERWANDTE LINKS

[Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)

[Trace-Command](Trace-Command.md)
