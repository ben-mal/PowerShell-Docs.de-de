---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/unregister-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-ScheduledJob
ms.openlocfilehash: 0c0b55513bcfdcebdcd5d8a6f17968a4a45e2839
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213372"
---
# Unregister-ScheduledJob

## ZUSAMMENFASSUNG
Löscht geplante Aufträge auf dem lokalen Computer.

## SYNTAX

### Definition (Standard)

```
Unregister-ScheduledJob [-InputObject] <ScheduledJobDefinition[]> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Definitions

```
Unregister-ScheduledJob [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefinitionName

```
Unregister-ScheduledJob [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das **Unregister-ScheduledJob** -Cmdlet löscht geplante Aufträge vom lokalen Computer.

Beim Löschen oder Aufheben der Registrierung eines geplanten Auftrags löscht **Unregister-ScheduledJob** das Verzeichnis für den geplanten Auftrag (im Verzeichnis $Home \appdata\local\microsoft\windows\powershell\scheduledjobs), das die XML-Datei enthält, in der der geplante Auftrag, der Auftrags Ausführungs Verlauf und alle Auftrags Ergebnisse definiert sind.
Diese Aktion löscht auch den Auftrag aus dem Taskplaner.

**Unregister-ScheduledJob** löscht nur die geplanten Aufträge, die mit dem Cmdlet "Register-ScheduledJob" erstellt wurden.
Geplante Aufträge, die im Taskplaner erstellt werden, werden nicht gelöscht.

Sie können die Parameter von **Unregister-ScheduledJob** verwenden, um geplante Aufträge nach ID oder Name zu löschen, oder geplante Aufträge von Get-ScheduledJob an **Unregister-ScheduledJob** weiterreichen.

**Unregister-ScheduledJob** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Löschen eines geplanten Auftrags

```
PS C:\> Unregister-ScheduledJob TestJob
```

Dieser Befehl löscht den geplanten Auftrag TestJob vom lokalen Computer.

### Beispiel 2: Löschen aller geplanten Aufträge

```
PS C:\> Get-ScheduledJob | Unregister-ScheduledJob -Force
PS C:\> Unregister-ScheduledJob -Name "*" -Force
```

In diesem Beispiel werden zwei verschiedene Befehle veranschaulicht, die alle geplanten Aufträge auf dem lokalen Computer löschen.

Der erste Befehl verwendet das Cmdlet "Get-ScheduledJob", um alle geplanten Aufträge auf dem lokalen Computer zu erhalten.
Ein Pipelineoperator (|) sendet die geplanten Aufträge an **Unregister-ScheduleJob** , durch das sie gelöscht werden.

Der zweite Befehl verwendet den *Name* -Parameter von **Unregister-ScheduledJob** mit einem Platzhalter für alle Aufträge (*), um alle geplanten Aufträge zu löschen.

Beide Befehle verwenden den *Force* -Parameter, der einen geplanten Auftrag selbst dann löscht, wenn eine Instanz des Auftrags ausgeführt wird.

### Beispiel 3: Löschen eines geplanten Auftrags auf einem Remote Computer

```
PS C:\> Invoke-Command -ComputerName "Server01" { Unregister-ScheduledJob -Name "Test*"}
```

Mit diesem Befehl werden geplante Aufträge mit Namen gelöscht, die mit "Test" auf dem Remote Computer "Server01" beginnen.
Der Befehl verwendet das Cmdlet "Invoke-Command", um den **Unregister-ScheduledJob-** Befehl auf dem Server02-Computer auszuführen.

## PARAMETERS

### -Force
Löscht den geplanten Auftrag selbst dann, wenn eine Instanz des Auftrags ausgeführt wird.
Ausgeführte Aufträge werden von **Unregister-ScheduledJob** standardmäßig nicht unterbrochen.

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

### -Id
Löscht die geplanten Aufträge mit den angegebenen IDs.
Geben Sie die IDs der geplanten Aufträge auf dem Computer ein.

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Gibt einen geplanten Auftrag an.
Geben Sie eine Variable ein, die **ScheduledJob** -Objekte enthält, oder geben Sie einen Befehl oder Ausdruck ein, der **ScheduledJob** -Objekte abruft, z. b. einen Get-ScheduledJob
Sie können **ScheduledJob** -Objekte auch über die Pipeline an **Unregister-Job-** Token übergeben.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Löscht die geplanten Aufträge mit den angegebenen Namen.
Geben Sie den Namen mindestens eines geplanten Auftrags auf dem Computer ein.
Platzhalter werden unterstützt.

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

### Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition
Sie können geplante Aufträge an Unregister-ScheduledJob weiterreichen.

## AUSGABEN

### Keine
Dieses Cmdlet generiert keine Ausgabe.

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
