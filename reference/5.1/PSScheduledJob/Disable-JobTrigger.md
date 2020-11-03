---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-JobTrigger
ms.openlocfilehash: 236e6b7e6e450bd1f3f868f889a19cf796890127
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213492"
---
# Disable-JobTrigger

## ZUSAMMENFASSUNG
Deaktiviert die Auftragstrigger geplanter Aufträge.

## SYNTAX

```
Disable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mit dem **Disable-JobTrigger** -Cmdlet werden die Auftragstrigger geplanter Aufträge vorübergehend deaktiviert.
Beim Deaktivieren bleiben alle Auftragstriggereigenschaften erhalten, allerdings wird verhindert, dass der geplante Auftrag durch den Auftragstrigger gestartet wird.

Um dieses Cmdlet zu verwenden, verwenden Sie das Cmdlet "Get-JobTrigger", um die Auftrags Trigger zu erhalten.
Reichen Sie die Auftragstrigger dann an **Disable-JobTrigger** weiter, oder verwenden Sie den zugehörigen *InputObject* -Parameter.

Zum Deaktivieren eines Auftrags Auslösers wird die aktivierte Eigenschaft des $false Auftrags Auslösers mit dem Cmdlet "" vom Typ "" **deaktiviert** .
Zum erneuten Aktivieren des Auftrags Auslösers verwenden Sie das Cmdlet "Enable-JobTrigger", mit dem die **aktivierte** Eigenschaft des Auftrags Auslösers auf $true festgelegt wird.
Durch das Deaktivieren eines Auftrags Triggers wird der geplante Auftrag nicht deaktiviert, wie z. b. durch das Cmdlet "Disable-ScheduledJob", aber wenn Sie alle Auftrags Trigger deaktivieren, ist der Effekt identisch mit der Deaktivierung des geplanten Auftrags.

Wenn Sie einen geplanten Auftrag deaktivieren oder alle Auftrags Trigger eines geplanten Auftrags deaktivieren, können Sie den Auftrag dennoch mit dem Cmdlet "Start-Job" starten oder den deaktivierten geplanten Auftrag als Vorlage verwenden.

" **Deaktivieren-ScheduledJob** " ist eine Sammlung von Auftrags Planungs-Cmdlets im **psscheduledjob** -Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Deaktivieren eines Auftrags Auslösers

```
PS C:\> Get-JobTrigger -Name "Backup-Archives" -TriggerID 1 | Disable-JobTrigger
```

Dieser Befehl deaktiviert den ersten Trigger (ID=1) des geplanten Auftrags Backup-Archives auf dem lokalen Computer.

Der Befehl verwendet das Cmdlet "Get-JobTrigger", um den Auftrags--Befehl zu erhalten.
Ein Pipelineoperator sendet den Auftragstrigger an das **Disable-JobTrigger** -Cmdlet, durch das er deaktiviert wird.

### Beispiel 2: Deaktivieren aller Auftrags Trigger

```
The first command uses the Get-ScheduledJob cmdlet to get the Backup-Archives and Inventory scheduled jobs. A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs. Another pipeline operator sends the job triggers to the **Disable-JobTrigger** cmdlet, which disables them.The first command uses the **Get-ScheduledJob** cmdlet to get the jobs, because its *Name* parameter takes multiple names.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Disable-JobTrigger

The second command displays the results. The command repeats the **Get-ScheduledJob** and **Get-JobTrigger** command. A pipeline operator sends the job triggers to the Format-Table cmdlet, which displays the job triggers in a table. The **Format-Table** command adds a JobName property that displays the value of the Name property of the scheduled job in the JobDefinition property of the job trigger object.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
1  Weekly    9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
2  Daily     9/29/2011 1:00:00 AM              False   Backup-Archive
1  Weekly    10/20/2011 11:00:00 PM {Friday}   False   Inventory
1  Weekly    11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

Diese Befehle deaktivieren alle Auftragstrigger zwei geplanter Aufträge und zeigen die Ergebnisse an.

### Beispiel 3: Deaktivieren des Auftrags Auslösers eines geplanten Auftrags auf einem Remote Computer

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "Daily"} | Disable-JobTrigger}
```

Dieser Befehl deaktiviert die täglichen Auftragstrigger für den geplanten Auftrag DeployPackage auf dem Remotecomputer Server01.

Der Befehl verwendet das Cmdlet "Invoke-Command", um die Befehle auf dem Server01-Computer auszuführen.
Der Remote Befehl verwendet das Cmdlet "Get-JobTrigger", um die Auftrags Trigger des geplanten Auftrags DeployPackage zu erhalten.
Ein Pipeline Operator sendet die Auftrags Trigger an das Where-Object-Cmdlet, das nur tägliche Auftrags Trigger zurückgibt.
Ein Pipeline Operator sendet die täglichen Auftrags Trigger an das **Deaktivierte** Cmdlet "Disab-jobtrigger".

## PARAMETERS

### -InputObject
Gibt den zu deaktivierenden Auftragstrigger an.
Geben Sie eine Variable ein, die  **ScheduledJob-** Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **ScheduledJob-** Objekte abruft, z. b. einen Get-JobTrigger Befehl
Sie können ein **ScheduledJob-** Objekt auch über die Pipeline an " **Deaktivierte jobauslöst** " übergeben.

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
Sie können Auftragstrigger an **Disable-JobTrigger** weiterreichen.

## AUSGABEN

### Keine
Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* " **Deaktivieren-jobtriggern** " generiert keine Fehler oder Warnungen, wenn Sie einen bereits deaktivierten Auftrags Triggern deaktivieren.

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
