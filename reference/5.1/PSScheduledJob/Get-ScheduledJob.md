---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJob
ms.openlocfilehash: 40224432c208ee45efc20f556312fa250e9bb7a6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213436"
---
# Get-ScheduledJob

## ZUSAMMENFASSUNG
Ruft geplante Aufträge auf dem lokalen Computer ab.

## SYNTAX

### Definitions (Standard)

```
Get-ScheduledJob [[-Id] <Int32[]>] [<CommonParameters>]
```

### DefinitionName

```
Get-ScheduledJob [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION
Das **Get-ScheduledJob** -Cmdlet ruft geplante Aufträge auf dem lokalen Computer ab.
**Get-ScheduledJob** ruft nur geplante Aufträge ab, die vom aktuellen Benutzer mit dem-Cmdlet "Register-ScheduledJob" erstellt werden.

Obwohl Aufträge, die mit dem **Register-ScheduledJob** -Cmdlet erstellt wurden, im Taskplaner angezeigt werden, ruft **Get-ScheduledJob** nur geplante Aufträge ab.
Geplante Tasks, die im Taskplaner erstellt wurden, werden nicht abgerufen.

Ohne Parameter ruft **Get-ScheduledJob** alle geplanten Aufträge auf dem Computer ab.
Sie können die Parameter von **Get-ScheduledJob** verwenden, um geplante Aufträge nach der ID oder dem Namen abzurufen und zu untersuchen oder an andere Cmdlets weiterzureichen.

" **Get-ScheduledJob** " ist eine Sammlung von Auftrags Planungs-Cmdlets im **psscheduledjob** -Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: alle geplanten Aufträge erhalten

```
PS C:\> Get-ScheduledJob
```

Dieser Befehl ruft alle geplanten Aufträge auf dem lokalen Computer ab.

### Beispiel 2: geplante Aufträge nach Namen

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive*
```

Dieser Befehl ruft alle geplanten Aufträge auf dem Computer ab, deren Name "Backup" oder "Archive" umfasst.
Mit diesem Befehlsformat können Sie bestimmte Aufträge suchen.

### Beispiel 3: geplante Aufträge auf Remote Computern

```
PS C:\> Invoke-Command -ComputerName (Get-Content Servers.txt) {Get-ScheduledJob}
```

Dieser Befehl ruft alle geplanten Aufträge auf den Computern ab, die in der Datei „Servers.txt“ aufgelistet sind.
Der Befehl verwendet das Cmdlet "Invoke-Command", um einen **Get-schedulejob-** Befehl auf jedem Computer auszuführen.

### Beispiel 4: übermitteln geplanter Aufträge an andere Cmdlets

```
PS C:\> Get-ScheduledJob DailyBackup, WeeklyBackup | Get-JobTrigger
```

Dieser Befehl ruft die Auftragstrigger der geplanten Aufträge DailyBackup und WeeklyBackup ab.
Er verwendet das **Get-ScheduledJob** -Cmdlet, um die geplanten Aufträge zu erhalten, und das Cmdlet "Get-JobTrigger", um die Auftrags Trigger der geplanten Aufträge zu erhalten.

## PARAMETERS

### -Id
Ruft nur die geplanten Aufträge mit der angegebenen ID ab.
Geben Sie mindestens eine ID eines geplanten Auftrags auf dem Computer ein.
**Get-ScheduledJob** ruft standardmäßig alle geplanten Aufträge auf dem Computer ab.

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Ruft nur die geplanten Aufträge mit den angegebenen Namen ab.
Geben Sie mindestens einen Namen eines geplanten Auftrags auf dem Computer ein.
Platzhalter werden unterstützt.
**Get-ScheduledJob** ruft standardmäßig alle geplanten Aufträge auf dem Computer ab.

```yaml
Type: System.String[]
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine
Eingaben können nicht an **Get-ScheduledJob übergeben werden** .

## AUSGABEN

### Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition

## HINWEISE

* Jeder geplante Auftrag wird in einem Unterverzeichnis des Verzeichnisses „$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs“ auf dem lokalen Computer gespeichert. Das Unterverzeichnis wird für den geplanten Auftrag benannt und enthält die XML-Datei für den geplanten Auftrag sowie Einträge zu dessen Ausführungsverlauf. Weitere Informationen zu geplanten Aufträgen auf dem Datenträger finden Sie unter About_Scheduled_Jobs_Advanced.
* Geplante Aufträge, die Sie in Windows PowerShell erstellen, werden im Taskplaner im Ordner „Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs“ angezeigt. Sie können den Taskplaner zum Anzeigen und Bearbeiten des geplanten Auftrags verwenden.
* Sie können den Taskplaner, das Befehlszeilentool „SchTasks.exe“ und die Taskplaner-Cmdlets zum Verwalten geplanter Aufträge verwenden, die Sie mit den Cmdlets für geplante Aufträge erstellen. Sie können die Cmdlets für geplante Aufträge jedoch nicht zum Verwalten von Tasks verwenden, die Sie im Taskplaner erstellen.

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
