---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restore-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-Computer
ms.openlocfilehash: 824e9a24693c7a7de01358a048a0df55be333263
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214476"
---
# Restore-Computer

## ZUSAMMENFASSUNG
Startet eine Systemwiederherstellung auf dem lokalen Computer.

## SYNTAX

```
Restore-Computer [-RestorePoint] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mit dem Cmdlet " **Restore-Computer** " wird der lokale Computer am angegebenen Systemwiederherstellungspunkt wieder hergestellt.

**Restore-Computer** startet den Computer neu.
Die Wiederherstellung wird während des Neustartvorgangs abgeschlossen.

System Wiederherstellungspunkte und **Restore-Computer** werden nur unter Client Betriebssystemen wie Windows 7, Windows Vista und Windows XP unterstützt.

## BEISPIELE

### Beispiel 1: Wiederherstellen des lokalen Computers

```
PS C:\> Restore-Computer -RestorePoint 253
```

Mit diesem Befehl wird der lokale Computer am Wiederherstellungspunkt mit der Sequenznummer 253 wieder hergestellt.

### Beispiel 2: Wiederherstellen des lokalen Computers mit Bestätigung

```
PS C:\> Restore-Computer -RestorePoint 255 -Confirm
Confirm
Are you sure you want to perform this action?
Performing operation "Restore-Computer" .
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Mit diesem Befehl wird der lokale Computer am Wiederherstellungspunkt mit der Sequenznummer 255 wieder hergestellt.
Er verwendet den *Confirm* -Parameter, um den Benutzer aufzufordern, bevor der Vorgang tatsächlich durchgeführt wird.

### Beispiel 3: Wiederherstellen eines Computers und Überprüfen des Status

```
PS C:\> Get-ComputerRestorePoint
PS C:\> Restore-Computer -RestorePoint 255
PS C:\> Get-ComputerRestorePoint -LastStatus
```

Mit diesen Befehlen wird eine Systemwiederherstellung ausgeführt und ihr Status überprüft.

Der erste Befehl verwendet **Get-ComputerRestorePoint** , um die Wiederherstellungspunkte auf dem lokalen Computer abzurufen.

Mit dem zweiten Befehl wird der Computer am Wiederherstellungspunkt mit der Sequenznummer 255 wieder hergestellt.

Der dritte Befehl verwendet den *laststatus* -Parameter des *Get-ComputerRestorePoint-* Cmdlets, um den Status des Wiederherstellungs Vorgangs zu überprüfen.
Da **Restore-Computer** einen Neustart erzwingt, wird dieser Befehl nach dem Neustart des Computers eingegeben.

## PARAMETERS

### -RestorePoint
Gibt die Sequenznummer des Wiederherstellungspunkts an.
Verwenden Sie das Cmdlet "Get-ComputerRestorePoint", um die Sequenznummer zu ermitteln.
Dieser Parameter ist erforderlich.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: SequenceNumber, SN, RP

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

### Keine
Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Keine
Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* Wenn Sie einen Restore-Computer Befehl unter Windows Vista und höheren Versionen des Windows-Betriebssystems ausführen möchten, öffnen Sie Windows PowerShell mit der Option als Administrator ausführen.
* Dieses Cmdlet verwendet die Windows-Verwaltungsinstrumentation (WMI) **SystemRestore** -Klasse.

## VERWANDTE LINKS

[Checkpoint-Computer](Checkpoint-Computer.md)

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restart-Computer](Restart-Computer.md)
