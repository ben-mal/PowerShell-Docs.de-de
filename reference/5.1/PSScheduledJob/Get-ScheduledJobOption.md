---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJobOption
ms.openlocfilehash: 5c317be9add0898137aceed6c39032f3e271bac1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213428"
---
# Get-ScheduledJobOption

## ZUSAMMENFASSUNG
Ruft die Auftragsoptionen geplanter Aufträge ab.

## SYNTAX

### Jobdefinition (Standard)

```
Get-ScheduledJobOption [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### JobDefinitionId

```
Get-ScheduledJobOption [-Id] <Int32> [<CommonParameters>]
```

### JobDefinitionName

```
Get-ScheduledJobOption [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
Mit dem **Get-scheduledjoboption-** Cmdlet werden die Auftrags Optionen geplanter Aufträge abgerufen.
Sie können den Befehl verwenden, um die Auftragsoptionen zu untersuchen bzw. an andere Cmdlets weiterzureichen.

Auftragsoptionen werden nicht unabhängig voneinander auf dem Datenträger gespeichert, da sie Teil eines geplanten Auftrags sind.
Um die Auftragsoptionen eines geplanten Auftrags abzurufen, geben Sie den geplanten Auftrag an.

Verwenden Sie die Parameter des **Get-ScheduledJobOption** -Cmdlets, um den geplanten Auftrag zu identifizieren.
Sie können geplante Aufträge anhand ihrer Namen oder Identifikationsnummern identifizieren oder indem Sie **ScheduledJob** -Objekte (z. b. die vom Get-ScheduledJob-Cmdlet zurückgegebenen) an **Get-scheduledjoboption** eingeben oder weiterleiten.

**Get-scheduledjoboption** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Get Job Options

```
PS C:\> Get-ScheduledJobOption -Name "*Backup*"
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : False

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

Dieser Befehl ruft die Auftrags Optionen geplanter Aufträge ab, deren Namen eine Sicherung aufweisen.
Die Ergebnisse zeigen das Objekt mit Auftragsoptionen, das von **Get-ScheduledJobOption** zurückgegeben wurde.

### Beispiel 2: alle Auftrags Optionen

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption
```

Dieser Befehl ruft die Auftragsoptionen aller geplanten Aufträge vom lokalen Computer ab.

Er verwendet das Cmdlet "Get-ScheduledJob", um die geplanten Aufträge auf dem lokalen Computer zu erhalten.
Ein Pipeline Operator (|) sendet die geplanten Aufträge an das **Get-scheduledjoboption-** Cmdlet, das die Auftrags Optionen jedes geplanten Auftrags abruft.

### Beispiel 3: Get Selected Job Options

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun}
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : True

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The second command shows how to find to which scheduled job the job options belong. This command uses a pipeline operator (|) to send the selected job options to the ForEach-Object cmdlet, which gets the JobDefinition property of each options object. The JobDefinition property contains the originating job object. The results show that the selected options came from the DeployPkg scheduled job.
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun} | ForEach-Object {$_.JobDefinition}
Id         Name            Triggers        Command                                  Enabled

--         ----            --------        -------                                  -------

2          DeployPkg         {1, 2}        DeployPackage.ps1                        True
```

In diesem Beispiel wird veranschaulicht, wie ein Objekt mit Auftragsoptionen, das bestimmte Werte enthält, ermittelt wird.

Der erste Befehl ruft die Auftrags Optionen ab, in denen die Eigenschaft runerhöhten den Wert $true hat und die runwithoutnetwork-Eigenschaft den Wert $false hat.
Die Ausgabe zeigt das **joboptions** -Objekt, das ausgewählt wurde.

### Beispiel 4: Verwenden von Auftrags Optionen zum Erstellen eines neuen Auftrags

```
PS C:\> $Opts = Get-ScheduledJobOption -Name "BackupTestLogs"
PS C:\> Register-ScheduledJob -Name "Archive-Scripts" -FilePath "\\Srv01\Scripts\ArchiveScripts.ps1" -ScheduledJobOption $Opts
```

Dieses Beispiel zeigt, wie die Auftrags Optionen verwendet werden, die Get-ScheduledJobOption in einem neuen geplanten Auftrag erhält.

Der erste Befehl verwendet **Get-scheduledjoboption** , um die Auftrags Optionen des geplanten Auftrags backuptestlogs zu erhalten.
Der Befehl speichert die Optionen in der $Opts-Variablen.

Der zweite Befehl verwendet Register-ScheduledJob Cmdlet, um einen neuen geplanten Auftrag zu erstellen.
Der Wert des *ScheduledJobOption* -Parameters entspricht dem Options-Objekt in der $Opts-Variablen.

### Beispiel 5: erhalten von Auftrags Optionen von einem Remote Computer

```
PS C:\> $O = Invoke-Command -ComputerName "Srv01" -ScriptBlock {Get-ScheduledJob -Name "DataDemon" }
```

Dieser Befehl verwendet das Cmdlet "Invoke-Command", um die Optionen für den geplanten Auftrag des datademon-Auftrags auf dem SRV01-Computer zu erhalten.
Der Befehl speichert die Optionen in der $O Variable.

## PARAMETERS

### -Id
Gibt die ID eines geplanten Auftrags an.
**Get-ScheduledJobOption** ruft die Auftragsoptionen des angegebenen geplanten Auftrags ab.

Verwenden Sie das Cmdlet "Get-ScheduledJob", um die Identifikationsnummern geplanter Aufträge auf dem lokalen Computer oder einem Remote Computer zu erhalten.

```yaml
Type: System.Int32
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Gibt einen geplanten Auftrag an.
Geben Sie eine Variable ein, die ein **ScheduledJob** -Objekt enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der ein **ScheduledJob** -Objekt abruft, z.b. einen Get-ScheduledJob Befehl.
Sie können auch ein **ScheduledJob** -Objekt an **Get-ScheduledJobOption** weiterreichen.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Gibt die Namen geplanter Aufträge an.
**Get-ScheduledJobOption** ruft die Auftragsoptionen des angegebenen geplanten Auftrags ab.
Platzhalter werden unterstützt.

Verwenden Sie das Cmdlet "Get-ScheduledJob", um die Namen geplanter Aufträge auf dem lokalen Computer oder einem Remote Computer zu erhalten.

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition
Sie können einen geplanten Auftrag von Get-ScheduledJob an **Get-scheduledjoboption** weiterreichen.

## AUSGABEN

### Microsoft. PowerShell. ScheduledJob. scheduledjoboptions

## HINWEISE

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
