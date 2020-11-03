---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-psbreakpoint?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSBreakpoint
ms.openlocfilehash: c130feac876ff812a854d52961ba3141ba341af0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216652"
---
# Get-PSBreakpoint

## ZUSAMMENFASSUNG
Ruft die Haltepunkte ab, die in der aktuellen Sitzung festgelegt sind.

## SYNTAX

### Skript (Standard)

```
Get-PSBreakpoint [-Script <String[]>] [<CommonParameters>]
```

### Variable

```
Get-PSBreakpoint [-Script <String[]>] -Variable <String[]> [<CommonParameters>]
```

### Get-Help

```
Get-PSBreakpoint [-Script <String[]>] -Command <String[]> [<CommonParameters>]
```

### type

```
Get-PSBreakpoint [-Script <String[]>] [-Type] <BreakpointType[]> [<CommonParameters>]
```

### Id

```
Get-PSBreakpoint [-Id] <Int32[]> [<CommonParameters>]
```

## DESCRIPTION

Das **Get-psbreakpoint** -Cmdlet ruft die Breakpoints ab, die in der aktuellen Sitzung festgelegt sind.
Mithilfe der Cmdlet-Parameter können Sie bestimmte Haltepunkte abrufen.

Ein Haltepunkt ist ein Punkt in einem Befehl oder Skript, an dem die Ausführung vorübergehend beendet wird, damit Sie die Anweisungen lesen können.
**Get-psbreakpoint** ist eines von mehreren Cmdlets für das Debuggen von PowerShell-Skripts und-Befehlen. Weitere Informationen zum PowerShell-Debugger finden Sie unter about_Debuggers.

## BEISPIELE

### Beispiel 1: alle Haltepunkte für alle Skripts und Funktionen

```
PS C:\> Get-PSBreakpoint
```

Dieser Befehl ruft alle Haltepunkte ab, die für alle Skripts und Funktionen in der aktuellen Sitzung festgelegt sind.

### Beispiel 2: Get Breakpoints by ID

```
PS C:\> Get-PSBreakpoint -Id 2
Function   :
IncrementAction     :
Enabled    :
TrueHitCount   : 0
Id         : 2
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

Dieser Befehl ruft den Haltepunkt mit Haltepunkt-ID 2 ab.

### Beispiel 3: übergeben einer ID an Get-PSBreakpoint

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Command "Increment"
PS C:\> $B.Id | Get-PSBreakpoint
```

Diese Befehle zeigen, wie Sie einen Haltepunkt durch Weiterleiten einer Haltepunkt-ID an **Get-psbreakpoint** erhalten.

Der erste Befehl verwendet das Set-PSBreakpoint-Cmdlet, um einen Haltepunkt für die Increment-Funktion im Skript „Sample.ps1“ zu erstellen. Das Haltepunkt Objekt wird in der $B Variablen gespeichert.

Der zweite Befehl verwendet den Punkt Operator (.), um die ID-Eigenschaft des Haltepunkt Objekts in der $B Variablen zu erhalten. Er verwendet einen Pipeline Operator (|), um die ID an das **Get-psbreakpoint** -Cmdlet zu senden.

Daher ruft **Get-psbreakpoint** den Haltepunkt mit der angegebenen ID ab.

### Beispiel 4: Get Breakpoints in angegebenen Skriptdateien

```
PS C:\> Get-PSBreakpoint -Script "Sample.ps1, SupportScript.ps1"
```

Dieser Befehl ruft alle Haltepunkte in den Dateien „Sample.ps1“ und „SupportScript.ps1“ ab.

Dieser Befehl ruft keine anderen Breakpoints ab, die möglicherweise in anderen Skripts oder in Funktionen in der Sitzung festgelegt werden.

### Beispiel 5: Get Breakpoints in angegebenen Cmdlets

```
PS C:\> Get-PSBreakpoint -Command "Read-Host, Write-Host" -Script "Sample.ps1"
```

Dieser Befehl ruft alle Command-Haltepunkte ab, die für den Read-Host- oder den Write-Host-Befehl in der Datei „Sample.ps1“ festgelegt sind.

### Beispiel 6: Get Command Breakpoints in a angegebene file

```
PS C:\> Get-PSBreakpoint -Type Command -Script "Sample.ps1"
```

Dieser Befehl ruft alle Command-Haltepunkte in der Datei „Sample.ps1“ ab.

### Beispiel 7: Get Breakpoints by Variable

```
PS C:\> Get-PSBreakpoint -Variable "Index, Swap"
```

Dieser Befehl ruft Breakpoints ab, die für die $Index-und $Swap Variablen in der aktuellen Sitzung festgelegt sind.

### Beispiel 8: alle Zeilen-und Variablen Breakpoints in einer Datei

```
PS C:\> Get-PSBreakpoint -Type Line, Variable -Script "Sample.ps1"
```

Dieser Befehl ruft alle Line- und Variable-Haltepunkte im Skript „Sample.ps1“ ab.

## PARAMETERS

### -Command

Gibt ein Array von Befehls Breakpoints an, die für die angegebenen Befehlsnamen festgelegt werden.
Geben Sie die Befehlsnamen ein, z. B. den Namen eines Cmdlets oder einer Funktion.

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Gibt die Haltepunkt-IDs an, die dieses Cmdlet abruft.
Geben Sie die IDs in einer durch Trennzeichen getrennten Liste ein.
Sie können Haltepunkt-IDs auch an **Get-psbreakpoint** übergeben.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Skript

Gibt ein Array von Skripts an, die die Breakpoints enthalten.
Geben Sie den Pfad (optional) und die Namen von mindestens einer Skriptdatei ein.
Wenn Sie den Pfad weglassen, wird als Standardspeicherort das aktuelle Verzeichnis verwendet.

```yaml
Type: System.String[]
Parameter Sets: Script, Variable, Command, Type
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Type

Gibt ein Array von breakpointtypen an, die von diesem Cmdlet abgerufen werden.
Geben Sie einen oder mehrere Typen ein.
Zulässige Werte für diesen Parameter:

- Zeile
- Get-Help
- Variable

Sie können Haltepunkt Typen auch an **Get-psbreakpoint** übergeben.

```yaml
Type: Microsoft.PowerShell.Commands.BreakpointType[]
Parameter Sets: Type
Aliases:
Accepted values: Line, Variable, Command

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Variable

Gibt ein Array von Variablen Breakpoints an, die für die angegebenen Variablennamen festgelegt werden.
Geben Sie die Variablennamen ohne Dollarzeichen ein.

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen finden Sie unter "about_CommonParameters" (https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Int32, Microsoft. PowerShell. Commands. breakpointtype

Sie können Haltepunkt-IDs und Haltepunkt Typen an **Get-psbreakpoint** übergeben.

## AUSGABEN

### System. Management. Automation. Breakpoint

**Get-psbreakpoint** gibt Objekte zurück, die die Haltepunkte in der Sitzung darstellen.

## HINWEISE

* Sie können **Get-psbreakpoint** oder seinen Alias, "GBP", verwenden.

## VERWANDTE LINKS

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)
