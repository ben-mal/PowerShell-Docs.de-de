---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-JobTrigger
ms.openlocfilehash: 7a75a5a7e6875ed88fd31ea0f385c19f1991f8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213439"
---
# Get-JobTrigger

## ZUSAMMENFASSUNG
Ruft die Auftragstrigger geplanter Aufträge ab.

## SYNTAX

### Jobdefinition (Standard)

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### JobDefinitionId

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Id] <Int32> [<CommonParameters>]
```

### JobDefinitionName

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
Mit dem **Get-JobTrigger** -Cmdlet werden die Auftragstrigger geplanter Aufträge abgerufen.
Sie können den Befehl verwenden, um die Auftragstrigger zu untersuchen bzw. um sie an andere Cmdlets weiterzureichen.

Ein Auftrags-Trigger definiert einen wiederkehrenden Zeitplan oder Bedingungen für das Starten eines geplanten Auftrags.
Auftragstrigger werden nicht unabhängig voneinander auf dem Datenträger gespeichert, da sie Teil eines geplanten Auftrags sind.
Um einen Auftragstrigger abzurufen, geben Sie den geplanten Auftrag an, den der Trigger startet.

Verwenden Sie die Parameter des **Get-JobTrigger** -Cmdlets, um die geplanten Aufträge zu identifizieren.
Sie können die geplanten Aufträge anhand ihrer Namen oder Identifikationsnummern identifizieren, oder indem Sie **ScheduledJob** -Objekte (z. b. die vom Get-ScheduledJob-Cmdlet zurückgegebenen) an **Get-Job-** Token eingeben oder weiterleiten.

**Get-jobausgelöst** ist eine Auflistung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: erhalten eines Auftrags Auslösers nach dem Namen des geplanten Auftrags

```
PS C:\> Get-JobTrigger -Name "BackupJob"
```

Der Befehl verwendet den *Name* -Parameter von **Get-jobtrigger** , um die Auftrags Trigger des geplanten Auftrags backupjob zu erhalten.

### Beispiel 2: erhalten eines Auftrags Auslösers nach ID

```
The first command uses the Get-ScheduledJob cmdlet to display the scheduled jobs on the local computer. The display includes the IDs of the scheduled jobs.
PS C:\> Get-ScheduledJob
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProjects {1}             \\Server\Share\Archive-Projects.ps1      True
2          Backup          {1,2}           \\Server\Share\Run-Backup.ps1            True
3          Test-HelpFiles  {1}             \\Server\Share\Test-HelpFiles.ps1        True
4          TestJob         {}              \\Server\Share\Run-AllTests.ps1          True

The second command uses the **Get-JobTrigger** cmdlet to get the job trigger for the Test-HelpFiles job (ID = 3)
PS C:\> Get-JobTrigger -ID 3
```

Im Beispiel wird der *ID* -Parameter von **Get-jobtrigger** verwendet, um die Auftrags Trigger eines geplanten Auftrags zu erhalten.

### Beispiel 3: erhalten von Auftrags Triggern durch Weiterleiten eines Auftrags

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive* | Get-JobTrigger
```

Dieser Befehl ruft die Auftrags Trigger aller Aufträge ab, deren Namen eine Sicherung oder ein Archiv aufweisen.

### Beispiel 4: Starten des Auftrags Auslösers eines Auftrags auf einem Remote Computer

```
PS C:\> Invoke-Command -ComputerName Server01 { Get-ScheduledJob Backup | Get-JobTrigger -TriggerID 2 }
```

Dieser Befehl ruft einen der beiden Auftragstrigger eines geplanten Auftrags auf einem Remotecomputer ab.

Der Befehl verwendet das Cmdlet "Invoke-Command", um einen Befehl auf dem Server01-Computer auszuführen.
Er verwendet das Cmdlet "Get-ScheduledJob", um den geplanten Auftrag für die Sicherung zu erhalten, der an das **Get-Job-** Cmdlet weitergeleitet wird.
Er verwendet den *triggerid* -Parameter, um nur den zweiten Trigger zu erhalten.

### Beispiel 5: Get all Job Triggers (alle Auftrags Trigger)

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="ScheduledJob";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                    DaysOfWeek Enabled ScheduledJob
-- --------- --                    ---------- ------- ------------
1    Weekly  9/28/2011 3:00:00 AM  {Monday}   True    Backup
1    Daily   9/27/2011 11:00:00 PM            True    Test-HelpFiles
```

Dieser Befehl ruft alle Auftragstrigger aller geplanten Aufträge vom lokalen Computer ab.

Der Befehl verwendet die Get-ScheduledJob, um die geplanten Aufträge auf dem lokalen Computer zu erhalten, und leitet Sie an **Get-jobauslöst** weiter, wodurch der Auftrags-Auslösung jedes geplanten Auftrags (sofern vorhanden) abgerufen wird.

Um den Namen des geplanten Auftrags der Anzeige des Auftrags Auslösers hinzuzufügen, verwendet der Befehl die Funktion für berechnete Eigenschaften des Format-Table-Cmdlets.
Zusätzlich zu den Eigenschaften des Auftrags Auslösers, die standardmäßig angezeigt werden, erstellt der Befehl eine neue ScheduledJob-Eigenschaft, die den Namen des geplanten Auftrags anzeigt.

### Beispiel 6: Get the Job-auslösereigenschaft eines geplanten Auftrags

```
The command uses the Get-ScheduledJob cmdlet to get the Test-HelpFiles scheduled job. Then it uses the dot method (.) to get the JobTriggers property of the Test-HelpFiles scheduled job.
PS C:\> (Get-ScheduledJob Test-HelpFiles).JobTriggers

The second command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer. It uses the ForEach-Object cmdlet to get the value of the JobTrigger property of each scheduled job.
PS C:\> Get-ScheduledJob | foreach {$_.JobTriggers}
```

Die Auftragstrigger eines geplanten Auftrags werden in der JobTriggers-Eigenschaft des Auftrags gespeichert.
Dieses Beispiel zeigt Alternativen zur Verwendung des **Get-jobtrigger** -Cmdlets zum erhalten von Auftrags Triggern.
Die Ergebnisse sind identisch mit der Verwendung des **Get-JobTrigger** -Cmdlets, und die Techniken sind austauschbar.

### Beispiel 7: Vergleichen von Auftrags Triggern

```
The first command gets the job trigger of the ArchiveProjects scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T1 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name ArchiveProjects | Get-JobTrigger | Tee-Object -Variable T1
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The second command gets the job trigger of the Test-HelpFiles scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T2 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name "Test-HelpFiles" | Get-JobTrigger | Tee-Object -Variable T2
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The third command compares the job triggers in the $t1 and $t2 variables. It uses the Get-Member cmdlet to get the properties of the job trigger in the $t1 variable. It pipes the properties to the ForEach-Object cmdlet, which compares each property to the properties of the job trigger in the $t2 variable by name. The command then pipes the differing properties to the Format-List cmdlet, which displays them in a list.The output indicates that, although the job triggers appear to be the same, the HelpFiles job trigger includes a random delay of three (3) minutes.
PS C:\> $T1 | Get-Member -Type Property | ForEach-Object { Compare-Object $T1 $T2 -Property $_.Name}
RandomDelay                                                 SideIndicator
-----------                                                 -------------
00:00:00                                                    =>
00:03:00                                                    <=
```

Dieses Beispiel zeigt, wie die Auftragstrigger von zwei geplanten Aufträgen verglichen werden.

## PARAMETERS

### -Id
Gibt die ID eines geplanten Auftrags an.
**Get-JobTrigger** ruft den Auftragstrigger des angegebenen geplanten Auftrags ab.

Verwenden Sie das Cmdlet "Get-ScheduledJob", um die ID der geplanten Aufträge auf dem lokalen Computer oder einem Remote Computer zu ermitteln.

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
Geben Sie eine Variable ein, die  **ScheduledJob** -Objekte enthält, oder geben Sie einen Befehl oder Ausdruck ein, der **ScheduledJob** -Objekte abruft, z. b. einen Get-ScheduledJob
Sie können **ScheduledJob** -Objekte auch über die Pipeline an **Get-Job-** Token übergeben.

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
Gibt den Namen eines geplanten Auftrags an.
**Get-JobTrigger** ruft den Auftragstrigger des angegebenen geplanten Auftrags ab.
Platzhalter werden unterstützt.

Verwenden Sie das Cmdlet "Get-ScheduledJob", um die Namen geplanter Aufträge auf dem lokalen Computer oder einem Remote Computer zu erhalten.

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Triggerid
Ruft die angegebenen Auftragstrigger ab.
Geben Sie die Trigger-ID mindestens eines Auftragstriggers eines geplanten Auftrags ein.
Verwenden Sie diesen Parameter, wenn der durch den Parameter *Name* , *ID* oder *InputObject* angegebene geplante Auftrag über mehrere Auftragstrigger verfügt.

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition
Sie können einen geplanten Auftrag von Get-ScheduledJob an **Get-joblöst** weiterreichen.

## AUSGABEN

### Microsoft. PowerShell. ScheduledJob. ScheduledJob-Auslösers

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
