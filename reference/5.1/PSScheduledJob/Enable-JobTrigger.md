---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-JobTrigger
ms.openlocfilehash: d08b55f4ba78af69608ac74c097fc6851164093b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213444"
---
# Enable-JobTrigger

## ZUSAMMENFASSUNG
Aktiviert die Auftragstrigger geplanter Aufträge.

## SYNTAX

```
Enable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das **enable-jobtrigger** -Cmdlet aktiviert Auftrags Trigger geplanter Aufträge erneut, z. b. solche, die mit dem Disable-JobTrigger-Cmdlet deaktiviert wurden.
Aktivierte und erneut aktivierte Auftragstrigger können geplante Aufträge sofort starten. Es besteht keine Notwendigkeit, Windows oder Windows PowerShell neu zu starten.

Um dieses Cmdlet zu verwenden, verwenden Sie das Cmdlet "Get-JobTrigger", um die Auftrags Trigger zu erhalten.
Übergeben Sie dann die Auftrags Trigger an **enable-jobtrigger** , oder verwenden Sie den *Inputobject* -Parameter.

Zum Aktivieren eines Auftrags Auslösers legt das **enable-Job-** Cmdlet die aktivierte Eigenschaft des Auftrags Auslösers auf $true fest.

**Enable-ScheduledJob** ist eine Sammlung von Auftrags Planungs-Cmdlets im **psscheduledjob** -Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Aktivieren eines Auftrags Auslösers

```
PS C:\> Get-JobTrigger -Name Backup-Archives -TriggerID 1 | Enable-JobTrigger
```

Dieser Befehl aktiviert den ersten Trigger (ID=1) des geplanten Auftrags Backup-Archives auf dem lokalen Computer.

Der Befehl verwendet das Cmdlet "Get-JobTrigger", um den Auftrags--Befehl zu erhalten.
Ein Pipelineoperator sendet den Auftragstrigger an das **Enable-JobTrigger** -Cmdlet, durch das er aktiviert wird.

### Beispiel 2: Aktivieren aller Auftrags Trigger

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Enable-JobTrigger
```

Der Befehl verwendet das Cmdlet "Get-ScheduledJob", um die geplanten Aufträge auf dem lokalen Computer zu erhalten.
Ein Pipeline Operator (|) sendet die geplanten Aufträge an das Get-JobTrigger-Cmdlet, das alle Auftrags Trigger der geplanten Aufträge abruft.
Ein weiterer Pipelineoperator sendet die Auftragstrigger an das **Enable-JobTrigger** -Cmdlet, durch das sie aktiviert werden.

### Beispiel 3: Aktivieren des Auftrags Auslösers eines geplanten Auftrags auf einem Remote Computer

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "AtLogon"} | Enable-JobTrigger}
```

Dieser Befehl aktiviert die AtLogon-Auftragstrigger für den geplanten Auftrag DeployPackage auf dem Remotecomputer Server01 erneut.

Der Befehl verwendet das Cmdlet "Invoke-Command", um die Befehle auf dem Server01-Computer auszuführen.
Der Remote Befehl verwendet das Cmdlet "Get-JobTrigger", um die Auftrags Trigger des geplanten Auftrags DeployPackage zu erhalten.
Ein Pipeline Operator sendet die Auftrags Trigger an das Where-Object-Cmdlet, das nur atlogon-Auftrags Trigger zurückgibt.
Ein Pipeline Operator sendet die atlogon-Auftrags Trigger an das **enable-jobtrigger** -Cmdlet, wodurch Sie aktiviert werden.

### Beispiel 4: anzeigen deaktivierter Auftrags Trigger

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | where {!$_.Enabled} | Format-Table Id, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}}
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
 1    Weekly 9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
 2    Daily  9/29/2011 1:00:00 AM              False   Backup-Archive
 1    Weekly 10/20/2011 11:00:00 PM {Friday}   False   Inventory
 1    Weekly 11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

Dieser Befehl zeigt alle deaktivierten Auftragstrigger aller geplanten Aufträge in einer Tabelle an.
Sie können einen Befehl wie diesen verwenden, um Auftragstrigger zu ermitteln, die u. U. aktiviert werden müssen.

Der Befehl verwendet das Cmdlet "Get-ScheduledJob", um die geplanten Aufträge auf dem lokalen Computer zu erhalten.
Ein Pipeline Operator (|) sendet die geplanten Aufträge an das Get-JobTrigger-Cmdlet, das alle Auftrags Trigger der geplanten Aufträge abruft.
Ein anderer Pipeline Operator sendet die Auftrags Trigger an das Where-Object-Cmdlet, das nur die deaktivierten Auftrags Trigger zurückgibt, d. h., wenn der Wert der aktivierten Eigenschaft des Auftrags Triggers nicht (!) true ist.

Ein anderer Pipeline Operator sendet die deaktivierten Auftrags Trigger an das Format-Table-Cmdlet, das die ausgewählten Eigenschaften der Auftrags Trigger in einer Tabelle anzeigt.
Die Eigenschaften umfassen eine neue JobName-Eigenschaft, die den Namen des geplanten Auftrags in der JobDefinition-Eigenschaft des Auftragstriggers anzeigt.

## PARAMETERS

### -InputObject
Gibt den zu Aktivier Vorgang für den Auftrag an.
Geben Sie eine Variable ein, die **ScheduledJob-** Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **ScheduledJob-** Objekte abruft, z. b. einen Get-JobTrigger Befehl
Sie können ein **ScheduledJob-** Objekt auch über die Pipeline an **enable-Job-** Token übergeben.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.
Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### Microsoft. PowerShell. ScheduledJob. ScheduledJob-Auslösers
Sie können Auftrags Trigger an **enable-jobtrigger** weiterreichen.

## AUSGABEN

### Keine
Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* **Enable-jobtriggern** generiert keine Fehler oder Warnungen, wenn Sie einen Auftrags Triggern aktivieren, der bereits aktiviert ist.

## VERWANDTE LINKS

[Add-JobTrigger](Add-JobTrigger.md)

[Disable-JobTrigger](Disable-JobTrigger.md)

[Disable-ScheduledJob](Disable-ScheduledJob.md)

[Enable-JobTrigger](Enable-JobTrigger.md)

[Enable-ScheduledJob](Enable-ScheduledJob.md)

[Get-JobTrigger](Get-JobTrigger.md)

[Get-ScheduledJob](Get-ScheduledJob.md)

[Get-ScheduledJobOption](Get-ScheduledJobOption.md)

[New-JobTrigger](New-JobTrigger.md)

[New-ScheduledJobOption](New-ScheduledJobOption.md)

[Register-ScheduledJob](Register-ScheduledJob.md)

[Remove-JobTrigger](Remove-JobTrigger.md)

[Set-JobTrigger](Set-JobTrigger.md)

[Set-ScheduledJob](Set-ScheduledJob.md)

[Set-ScheduledJobOption](Set-ScheduledJobOption.md)

[Unregister-ScheduledJob](Unregister-ScheduledJob.md)
