---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 905f3522a071fdd3f59d020b734c689a59e68a63
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217679"
---
# Debug-Process

## ZUSAMMENFASSUNG
Debuggt Prozesse, die auf dem lokalen Computer ausgeführt werden.

## SYNTAX

### Name (Standard)

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Id

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das **Debug-Process-** Cmdlet fügt einen Debugger an einen oder mehrere laufende Prozesse auf einem lokalen Computer an.
Sie können die Prozesse durch ihren Prozessnamen oder Ihre Prozess-ID (PID) angeben, oder Sie können Prozess Objekte über die Pipeline an dieses Cmdlet übergeben.

Dieses Cmdlet fügt den Debugger an, der derzeit für den Prozess registriert ist.
Überprüfen Sie vor dem Verwenden dieses Cmdlets, dass ein Debugger heruntergeladen und ordnungsgemäß konfiguriert wurde.

## BEISPIELE

### Beispiel 1: Anfügen eines Debuggers an einen Prozess auf dem Computer

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

Dieser Befehl fügt einen Debugger an den PowerShell-Prozess auf dem Computer an.

### Beispiel 2: Anfügen eines Debuggers an alle Prozesse, die mit der angegebenen Zeichenfolge beginnen

```
PS C:\> Debug-Process -Name "SQL*"
```

Dieser Befehl fügt einen Debugger an alle Prozesse an, deren Namen mit SQL beginnen.

### Beispiel 3: Anfügen eines Debuggers an mehrere Prozesse

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

Dieser Befehl fügt einen Debugger an die Winlogon-, Explorer- und Outlook-Prozesse an.

### Beispiel 4: Anfügen eines Debuggers an mehrere Prozess-IDs

```
PS C:\> Debug-Process -Id 1132, 2028
```

Dieser Befehl fügt einen Debugger an die Prozesse mit den Prozess-IDs 1132 und 2028 an.

### Beispiel 5: Verwenden Sie Get-Process, um einen Prozess zu erhalten, und fügen Sie dann einen Debugger an.

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

Dieser Befehl fügt einen Debugger an die PowerShell-Prozesse auf dem Computer an.
Er verwendet das **Get-Process-** Cmdlet, um die PowerShell-Prozesse auf dem Computer zu erhalten, und verwendet einen Pipeline Operator (|), um die Prozesse an das **Debug-Process-** Cmdlet zu senden.

Verwenden Sie zum Angeben eines bestimmten PowerShell-Prozesses den ID-Parameter von **Get-Process**.

### Beispiel 6: Anfügen eines Debuggers an einen aktuellen Prozess auf dem lokalen Computer

```
PS C:\> $PID | Debug-Process
```

Dieser Befehl fügt einen Debugger an die aktuellen PowerShell-Prozesse auf dem Computer an.

Der Befehl verwendet die $PID automatische Variable, die die Prozess-ID des aktuellen PowerShell-Prozesses enthält.
Anschließend wird ein Pipeline Operator (|) verwendet, um die Prozess-ID an das **Debug-Process-** Cmdlet zu senden.

Weitere Informationen über die $PID automatische Variable finden Sie unter about_Automatic_Variables.

### Beispiel 7: Anfügen eines Debuggers an einen Prozess, der den Inputobject-Parameter verwendet

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

Dieser Befehl fügt einen Debugger an die PowerShell-Prozesse auf dem lokalen Computer an.

Der erste Befehl verwendet das **Get-Process-** Cmdlet, um die PowerShell-Prozesse auf dem Computer zu erhalten.
Das resultierende Prozess Objekt wird in der Variablen mit dem Namen $P gespeichert.

Der zweite Befehl verwendet den *Inputobject* -Parameter des **Debug-Process-** Cmdlets, um das Process-Objekt in der $P-Variablen zu übermitteln.

## PARAMETERS

### -Id

Gibt die Prozess-IDs der zu debuggenden Prozesse an.
Der *ID* -Parameter Name ist optional.

Um die Prozess-ID eines Prozesses zu ermitteln, geben Sie ein `Get-Process` .

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases: PID, ProcessId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Gibt die Prozessobjekte an, die zu debuggende Prozesse darstellen.
Geben Sie eine Variable ein, die die Prozess Objekte enthält, oder einen Befehl, mit dem die Prozess Objekte abgerufen werden, z. b. das Get-Process Cmdlet.
Sie können Prozess Objekte auch über die Pipeline an dieses Cmdlet übergeben.

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Gibt die Namen der zu debuggenden Prozesse an.
Wenn mehr als ein Prozess mit demselben Namen vorhanden ist, fügt dieses Cmdlet einen Debugger an alle Prozesse mit diesem Namen an.
Der *Name* -Parameter ist optional.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Int32, System. Diagnostics. Process, System. String

Sie können eine Prozess-ID (Int32), ein Prozess Objekt (System. Diagnostics. Process) oder einen Prozessnamen (String) über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* Dieses Cmdlet verwendet die AttachDebugger-Methode der Win32_Process-Klasse der Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI). Weitere Informationen zu dieser Methode finden Sie unter [AttachDebugger-Methode](https://go.microsoft.com/fwlink/?LinkId=143640) in der MSDN Library.

## VERWANDTE LINKS

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Process](Start-Process.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)

