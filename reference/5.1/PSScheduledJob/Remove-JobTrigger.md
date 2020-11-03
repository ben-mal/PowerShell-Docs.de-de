---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/remove-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-JobTrigger
ms.openlocfilehash: adcd74361b1a045a57c7db2f15996f4ea53d6d5b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213412"
---
# Remove-JobTrigger

## ZUSAMMENFASSUNG
Löschen von Auftrags Triggern aus geplanten Aufträgen.

## SYNTAX

### Jobdefinition (Standard)

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-InputObject] <ScheduledJobDefinition[]> [<CommonParameters>]
```

### JobDefinitionId

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Id] <Int32[]> [<CommonParameters>]
```

### JobDefinitionName

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION
Das **Remove-jobtrigger-** Cmdlet löscht Auftrags Trigger aus geplanten Aufträgen.

Ein Auftrags-Trigger definiert einen wiederkehrenden Zeitplan oder Bedingungen für das Starten eines geplanten Auftrags.
Verwenden Sie zum Verwalten von Auftrags Triggern die Cmdlets New-jobtrigger, Add-jobtrigger, Set-jobtrigger und Set-ScheduledJob.

Verwenden Sie die Parameter *Name* , *ID* oder *InputObject* von **Remove-JobTrigger** , um die geplanten Aufträge zu identifizieren, aus denen die Trigger entfernt werden.
Verwenden Sie den *triggerid* -Parameter, um die zu löschenden Auftrags Trigger zu identifizieren.
Durch **Remove-JobTrigger** werden standardmäßig alle Auftragstrigger eines geplanten Auftrags gelöscht.

**Remove-jobauslöst** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Löschen aller Auftrags Trigger

```
PS C:\> Remove-JobTrigger -Name "Test*"
```

Mit diesem Befehl werden alle Auftrags Trigger aus dem geplanten Auftrag gelöscht, deren Namen mit "Test" beginnen.

### Beispiel 2: Löschen ausgewählter Auftrags Trigger

```
PS C:\> Remove-JobTrigger -Name "BackupArchive" -TriggerID 3
```

Dieser Befehl löscht nur den dritten Trigger (ID = 3) aus dem geplanten Auftrag BackupArchive.

### Beispiel 3: Löschen der atstartup-Auftrags Trigger aus allen geplanten Aufträgen

```
PS C:\> function Delete-AtStartup
{
    Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.Frequency -eq "AtStartup"} | ForEach-Object { Remove-JobTrigger -InputObject $_.JobDefinition -TriggerID $_.ID}
}
```

Diese Funktion löscht alle AtStartup-Auftragstrigger aus allen Aufträgen auf dem lokalen Computer.
Um die Funktion zu verwenden, führen Sie die Funktion in der Sitzung aus, und geben Sie dann ein `Delete-AtStartup` .

Die Delete-AtStartup-Funktion enthält einen einzelnen Befehl.
Der Befehl verwendet das Cmdlet "Get-ScheduledJob", um die geplanten Aufträge auf dem lokalen Computer zu erhalten.
Ein Pipeline Operator (|) sendet die geplanten Aufträge an das Get-JobTrigger-Cmdlet, das alle Auftrags Trigger aus jedem der geplanten Aufträge abruft.
Ein Pipeline Operator sendet die Auftrags Trigger an das Where-Object-Cmdlet, das Auftrags Trigger auswählt, bei denen der Wert der Frequency-Eigenschaft des Auftrags Triggers atstartup entspricht.

**Jobtriggerobjekte** verfügen über eine **Jobdefinition** -Eigenschaft, die den geplanten Auftrag enthält, den Sie auslöst.
Im übrigen Teil des Befehls wird dieses hilfreiche Feature verwendet.

Ein Pipeline Operator sendet die atstartup-Auftrags Trigger an das ForEach-Object-Cmdlet, das für jeden atstartup-Trigger einen **Remove-jobtrigger** -Befehl ausführt.
Der Wert der *InputObject* -Parameter von **Remove-JobTrigger** entspricht dem geplanten Auftrag in der JobDefinition-Eigenschaft des Auftragstriggers.
Der Wert des *TriggerID* -Parameters ist der Bezeichner in der ID-Eigenschaft des Auftragstriggers.

### Beispiel 4: Löschen eines Auftrags Auslösers aus einem geplanten Remote Auftrag

```
PS C:\> Invoke-Command -ComputerName "Server01" { Remove-JobTrigger -ID 38 -TriggerID 1 }
```

Dieser Befehl löscht den ersten Auftragstrigger aus dem Inventurauftrag auf dem Computer Server01.

Der Befehl verwendet das Cmdlet "Start **-Command** ", um das Cmdlet " **Remove-jobject** " auf dem Server01-Computer auszuführen.
Das **Remove-jobtrigger-** Cmdlet verwendet den *ID* -Parameter, um den geplanten Inventur Auftrag zu identifizieren, und den *triggerid* -Parameter, um den ersten Trigger anzugeben.
Der *ID* -Parameter ist besonders nützlich, wenn mehrere geplante Aufträge denselben oder ähnliche Namen aufweisen.

## PARAMETERS

### -Id
Gibt die IDs der geplanten Aufträge an.
**Remove-JobTrigger** löscht Auftragstrigger aus den angegebenen geplanten Aufträgen.

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
Sie können **ScheduledJob** -Objekte auch über die Pipeline an **Remove-Job-** Token übergeben.

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
**Remove-JobTrigger** löscht die Auftragstrigger aus den angegebenen geplanten Aufträgen.
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

### -Triggerid
Löscht nur die angegebenen Auftragstrigger.
Durch **Remove-JobTrigger** werden standardmäßig alle Trigger aus den geplanten Aufträgen gelöscht.
Verwenden Sie diesen Parameter, wenn die geplanten Aufträge mehrere Auftragstrigger aufweisen.

Geben Sie die Trigger-ID mindestens eines Auftragstriggers eines geplanten Auftrags ein.
Wenn Sie mehrere geplante Aufträge angeben, löscht **Remove-jobdelete** den Auftrags--Auslösers mit der angegebenen ID aus allen geplanten Aufträgen.

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition
Sie können geplante Aufträge an das **Remove-JobTrigger** -Cmdlet weiterreichen.

## AUSGABEN

### Keine
Das Cmdlet generiert keine Ausgabe.

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
