---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/disable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ComputerRestore
ms.openlocfilehash: 941829c3caa0f6bb2f5712dda9eb7d8c36908062
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215495"
---
# Disable-ComputerRestore

## ZUSAMMENFASSUNG
Deaktiviert das Systemwiederherstellungsfeature auf dem angegebenen Dateisystemlaufwerk.

## SYNTAX

```
Disable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das Cmdlet " **Debuggen-computerrestore" deaktiviert** das System Wiederherstellungs Feature auf einem oder mehreren Datei System Laufwerken.
Versuche, den Computer wiederherzustellen, haben deshalb keine Auswirkungen auf das angegebene Laufwerk.

Zum Deaktivieren der Systemwiederherstellung auf einem Laufwerk muss sie auf dem Systemlaufwerk deaktiviert werden, entweder zuerst oder gleichzeitig.

Verwenden Sie das Cmdlet %%amp;quot;Enable-ComputerRestore%%amp;quot;, um die Systemwiederherstellung erneut zu aktivieren.
Mit %%amp;quot;Rstrui.exe%%amp;quot; können Sie den Status der Systemwiederherstellung für jedes Laufwerk ermitteln.

Systemwiederherstellungspunkte und die ComputerRestore-Cmdlets werden nur unter Clientbetriebssystemen wie Windows 7, Windows Vista und Windows XP unterstützt.

## BEISPIELE

### Beispiel 1: Deaktivieren der System Wiederherstellung auf dem angegebenen Laufwerk

```
PS C:\> Disable-ComputerRestore -Drive "C:\"
```

Dieser Befehl deaktiviert die Systemwiederherstellung auf Laufwerk %%amp;quot;C:%%amp;quot;.

### Beispiel 2: Deaktivieren der System Wiederherstellung auf mehreren Laufwerken

```
PS C:\> Disable-ComputerRestore "C:\", "D:\"
```

Dieser Befehl deaktiviert die Systemwiederherstellung auf den Laufwerken %%amp;quot;C:%%amp;quot; und %%amp;quot;D:%%amp;quot;.
Der Befehl verwendet den *Drive* -Parameter, aber der Name des Laufwerks Parameters wird ausgelassen.

## PARAMETERS

### -Laufwerk
Gibt die Dateisystemlaufwerke an.
Geben Sie einen oder mehrere Dateisystem Laufwerk Buchstaben ein, gefolgt von einem Doppelpunkt und einem umgekehrten Schrägstrich und in Anführungszeichen (z. b. C:\). oder d:\.
Dieser Parameter ist erforderlich.

Mit diesem Cmdlet können Sie die Systemwiederherstellung auf einem Remotenetzlaufwerk nicht deaktivieren, auch wenn das Laufwerk dem lokalen Computer zugeordnet ist, und Sie können die Systemwiederherstellung nicht auf Laufwerken deaktivieren, die für die Systemwiederherstellung nicht geeignet sind, z. B. externe Laufwerke.

Zum Deaktivieren der Systemwiederherstellung auf einem Laufwerk muss sie auf dem Systemlaufwerk deaktiviert werden, entweder zuerst oder gleichzeitig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

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

* Wenn Sie dieses Cmdlet unter Windows Vista und höheren Versionen von Windows ausführen möchten, öffnen Sie Windows PowerShell mit der Option als Administrator ausführen.

  Informationen zu den Dateisystem Laufwerken, die für die Systemwiederherstellung geeignet sind, finden Sie unter System in der Systemsteuerung auf der Registerkarte Systemschutz. Um diese Registerkarte in Windows PowerShell zu öffnen, geben Sie ein `SystemPropertiesProtection` .

  Dieses Cmdlet verwendet die Windows-Verwaltungsinstrumentation (WMI) **SystemRestore** -Klasse.

*

## VERWANDTE LINKS

[Checkpoint-Computer](Checkpoint-Computer.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)
