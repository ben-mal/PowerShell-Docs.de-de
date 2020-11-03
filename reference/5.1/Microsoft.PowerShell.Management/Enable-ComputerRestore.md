---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/enable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ComputerRestore
ms.openlocfilehash: f9616a7f9af4dd2fa45e150bb64eef65427b4947
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215492"
---
# Enable-ComputerRestore

## ZUSAMMENFASSUNG
Aktiviert das Systemwiederherstellungsfeature auf dem angegebenen Dateisystemlaufwerk.

## SYNTAX

```
Enable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das **enable-computerrestore-** Cmdlet aktiviert das System Wiederherstellungs Feature auf einem oder mehreren Datei System Laufwerken.
Sie können daher mit Tools wie dem Cmdlet %%amp;quot;Restore-Computer%%amp;quot; den Computer in einem vorherigen Status wiederherstellen.

Standardmäßig ist die Systemwiederherstellung auf allen freigegebenen Laufwerken aktiviert, Sie können sie jedoch deaktivieren, z. B. mit dem Cmdlet %%amp;quot;Disable-ComputerRestore%%amp;quot;.
Zum Aktivieren (oder erneuten Aktivieren) der Systemwiederherstellung auf einem Laufwerk muss sie auf dem Systemlaufwerk aktiviert werden, entweder zuerst oder gleichzeitig.
Mit %%amp;quot;Rstrui.exe%%amp;quot; können Sie den Status der Systemwiederherstellung für jedes Laufwerk ermitteln.

Systemwiederherstellungspunkte und die ComputerRestore-Cmdlets werden nur unter Clientbetriebssystemen wie Windows 7, Windows Vista und Windows XP unterstützt.

## BEISPIELE

### Beispiel 1: Aktivieren der System Wiederherstellung auf dem angegebenen Laufwerk

```
PS C:\> Enable-ComputerRestore -Drive "C:\"
```

Dieser Befehl aktiviert die Systemwiederherstellung auf Laufwerk %%amp;quot;C:%%amp;quot; des lokalen Computers.

### Beispiel 2: Aktivieren der System Wiederherstellung auf mehreren Laufwerken

```
PS C:\> Enable-ComputerRestore -Drive "C:\", "D:\"
```

Dieser Befehl aktiviert die Systemwiederherstellung auf den Laufwerken %%amp;quot;C:%%amp;quot; und %%amp;quot;D:%%amp;quot; des lokalen Computers.

## PARAMETERS

### -Laufwerk
Gibt die Dateisystemlaufwerke an.
Geben Sie einen oder mehrere Dateisystem Laufwerk Buchstaben ein, gefolgt von einem Doppelpunkt und einem umgekehrten Schrägstrich und in Anführungszeichen (z. b. C:\). oder d:\.
Dieser Parameter ist erforderlich.

Mit diesem Cmdlet können Sie die Systemwiederherstellung auf einem Remotenetzlaufwerk nicht aktivieren, auch wenn das Laufwerk dem lokalen Computer zugeordnet ist, und Sie können die Systemwiederherstellung nicht auf Laufwerken aktivieren, die für die Systemwiederherstellung nicht geeignet sind, z. B. externe Laufwerke.

Zum Aktivieren der Systemwiederherstellung auf einem Laufwerk muss sie auf dem Systemlaufwerk aktiviert werden, entweder zuerst oder gleichzeitig.

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
Objekte können nicht an dieses Cmdlet weitergereicht werden.

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

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)
