---
external help file: Microsoft.PowerShell.ScheduledJob.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/add-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-JobTrigger
ms.openlocfilehash: 6066b8f91c99830fefb09a8bea13fac6ddf958e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213495"
---
# Add-JobTrigger

## ZUSAMMENFASSUNG
Fügt geplanten Aufträgen Auftragstrigger hinzu.

## SYNTAX

### Jobdefinition (Standard)

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-InputObject] <ScheduledJobDefinition[]>
 [<CommonParameters>]
```

### JobDefinitionId

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Id] <Int32[]> [<CommonParameters>]
```

### JobDefinitionName

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION
Das **Add-JobTrigger** -Cmdlet fügt geplanten Aufträgen Auftragstrigger hinzu.
Sie können es verwenden, um mehreren geplanten Aufträgen mehrere Trigger hinzuzufügen.

Ein Auftrags Fehler startet einen geplanten Auftrag nach einem einmaligen oder wiederkehrenden Zeitplan oder bei Auftreten eines Ereignisses.

Verwenden Sie den *Trigger* -Parameter von **Add-jobtrigger** , um die hinzu zufügenden Auftrags Trigger zu identifizieren.
Verwenden Sie die Parameter *Name* , *ID* oder *Inputobject* von **Add-jobtrigger** , um den geplanten Auftrag zu identifizieren, dem die Trigger hinzugefügt werden.

Zum Erstellen von Auftrags Triggern für den Wert des *Trigger* -Parameters verwenden Sie das Cmdlet "New-JobTrigger", oder verwenden Sie eine Hash Tabelle, um den Auftrags Trigger anzugeben.

**Add-jobauslöst** ist eine Sammlung von Auftrags Planungs-Cmdlets im **psscheduledjob** -Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Hinzufügen eines Auftrags Auslösers zu einem geplanten Auftrag

```
PS C:\> $Daily = New-JobTrigger -Daily -At 3AMPS
PS C:\> Add-JobTrigger -Trigger $Daily -Name "TestJob"
```

Diese Befehle fügen dem geplanten Auftrag TestJob den Daily-Auftragstrigger hinzu.

Der erste Befehl verwendet das Cmdlet "New-JobTrigger" zum Erstellen eines Auftrags Auslösers, der jeden Tag um 3:00 Uhr einen geplanten Auftrag startet.
Der Befehl speichert den Auftrags--Befehl in der $Daily-Variablen.

Der zweite Befehl verwendet das **Add-JobTrigger** -Cmdlet, um den Auftragstrigger in der $Startup-Variablen dem geplanten Auftrag TestJob hinzuzufügen.

### Beispiel 2: Hinzufügen eines Auftrags Auslösers zu mehreren geplanten Aufträgen

```
PS C:\> Get-ScheduledJob | Add-JobTrigger -Trigger (New-JobTrigger -AtStartup)
```

Dieser Befehl fügt allen geplanten Aufträgen auf dem lokalen Computer einen AtStartup-Auftragstrigger hinzu.
Er verwendet die Get-ScheduledJob, um alle geplanten Aufträge auf dem Computer zu erhalten.
Er verwendet einen Pipelineoperator (|), um die Aufträge an das **Add-JobTrigger** -Cmdlet zu senden, das jedem geplanten Auftrag den Auftragstrigger hinzufügt.
Der Wert des-Parameter *Auslösers* ist ein New-JobTrigger Befehl, der den atstartup-Auftrags-Auslösers erstellt.

### Beispiel 3: Kopieren eines Auftrags Auslösers

```
PS C:\> $T = Get-JobTrigger -Name "BackupArchives"
PS C:\> Add-JobTrigger -Name "TestBackup,BackupLogs" -Trigger $T
```

Diese Befehle kopieren den Auftragstrigger aus dem geplanten Auftrag BackupArchives und fügen ihn den geplanten Aufträgen TestBackup und BackupLogs hinzu.

Der erste Befehl verwendet das Cmdlet "Get-JobTrigger", um den Auftrags-und den geplanten Auftrag "backuparamechives" zu erhalten.
Der Befehl speichert den Trigger in der $t-Variablen.

Der zweite Befehl verwendet das **Add-JobTrigger** -Cmdlet, um den Auftragstrigger in $t den geplanten Aufträgen TestBackup und BackupLogs hinzuzufügen.

## PARAMETERS

### -Id
Gibt die IDs der geplanten Aufträge an.
**Add-JobTrigger** fügt den angegebenen geplanten Aufträgen den Auftragstrigger hinzu.

Verwenden Sie das Cmdlet "Get-ScheduledJob", um die ID der geplanten Aufträge auf dem lokalen Computer oder einem Remote Computer zu ermitteln.

```yaml
Type: System.Int32[]
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Gibt die geplanten Aufträge an.
Geben Sie eine Variable ein, die **ScheduledJob** -Objekte enthält, oder geben Sie einen Befehl oder Ausdruck ein, der **ScheduledJob** -Objekte abruft, z. b. einen Get-ScheduledJob
Sie können **ScheduledJob** -Objekte auch über die Pipeline an **Add-Job-** Token übergeben.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
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
**Add-JobTrigger** fügt den angegebenen geplanten Aufträgen die Auftragstrigger hinzu.
Platzhalter werden unterstützt.

Verwenden Sie das Cmdlet "Get-ScheduledJob", um die Namen geplanter Aufträge auf dem lokalen Computer oder einem Remote Computer zu erhalten.

```yaml
Type: System.String[]
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### --Auslösung
Gibt die hinzu zufügenden Auftrags Trigger an.
Geben Sie eine Hash Tabelle ein, die Auftrags Trigger oder eine Variable angibt, die **scheduledjobtrigger** -Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **scheduledjobtrigger** -Objekte abruft, z. b. einen Get-JobTrigger Befehl
Sie können **scheduledjobauslöserobjekte** auch über die Pipeline an **Add-Job-** Token übergeben.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Microsoft. PowerShell. ScheduledJob. scheduledjobtriggern, Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition
Sie können Auftragstrigger oder geplante Aufträge an **Add-JobTrigger** weiterreichen.

## AUSGABEN

### Keine
Dieses Cmdlet gibt keine Ausgabe zurück.

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
