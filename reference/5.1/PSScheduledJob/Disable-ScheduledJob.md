---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ScheduledJob
ms.openlocfilehash: a7ea520d7d0365fd0de8c9d0bb767981b68467c6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213476"
---
# Disable-ScheduledJob

## ZUSAMMENFASSUNG
Deaktiviert einen geplanten Auftrag.

## SYNTAX

### Definition (Standard)

```
Disable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Definitions

```
Disable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefinitionName

```
Disable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Geplante Aufträge werden vom **Disable-ScheduledJob** -Cmdlet vorübergehend deaktiviert.
Beim Deaktivieren werden alle Auftragseigenschaften beibehalten und keine Auftragstrigger deaktiviert. Gleichzeitig verhindert das Cmdlet, dass geplante Aufträge bei einem Trigger automatisch gestartet werden.
Sie können einen deaktivierten geplanten Auftrag starten, indem Sie das Cmdlet "Start-Job" verwenden oder einen deaktivierten geplanten Auftrag als Vorlage verwenden.

Zum Deaktivieren eines geplanten Auftrags legt das **Disable-ScheduledJob** -Cmdlet die **Enabled** -Eigenschaft des geplanten Auftrags auf „False“ ($false) fest.
Verwenden Sie das Cmdlet "Enable-ScheduledJob", um den geplanten Auftrag erneut zu aktivieren.

" **Deaktivieren-ScheduledJob** " ist eine Sammlung von Auftrags Planungs-Cmdlets im **psscheduledjob** -Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Deaktivieren eines geplanten Auftrags

```
PS C:\> Disable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
```

Dieser Befehl deaktiviert den geplanten Auftrag mit der ID 2 auf dem lokalen Computer.
Die Ausgabe veranschaulicht die Auswirkungen des Befehls.

### Beispiel 2: Deaktivieren aller geplanten Aufträge

```
PS C:\> Get-ScheduledJob | Disable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        False
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     False
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       False
```

Dieser Befehl deaktiviert alle geplanten Aufträge auf dem lokalen Computer.
Er verwendet das Cmdlet "Get-ScheduledJob", um alle geplanten Aufträge zu erhalten, und das Cmdlet " **Deaktivieren-ScheduledJob** ", um Sie zu deaktivieren.

Sie können den geplanten Auftrag erneut aktivieren, indem Sie das Cmdlet "Enable-ScheduledJob" verwenden und einen deaktivierten geplanten Auftrag ausführen, indem Sie das Start-Job-Cmdlet verwenden.

" **Deaktivieren-ScheduledJob** " generiert keine Warnungen oder Fehler, wenn Sie einen geplanten Auftrag, der bereits deaktiviert ist, deaktivieren, sodass Sie alle geplanten Aufträge ohne Bedingungen deaktivieren können.

### Beispiel 3: deaktivieren ausgewählter geplanter Aufträge

```
PS C:\> Get-ScheduledJob | Where-Object {!$_.Credential} | Disable-ScheduledJob
```

Dieser Befehl deaktiviert geplante Aufträge, die keine Anmeldeinformationen enthalten.
Aufträge ohne Anmeldeinformationen werden mit der Berechtigung des Benutzers ausgeführt, der sie erstellt hat.

Der Befehl verwendet das Cmdlet "Get-ScheduledJob", um alle geplanten Aufträge auf dem Computer zu erhalten.
Ein Pipeline Operator sendet die geplanten Aufträge an das Where-Object-Cmdlet, das geplante Aufträge ohne Anmelde Informationen auswählt.
Der Befehl verwendet den NOT-Operator (!) und verweist auf die Credential-Eigenschaft des geplanten Auftrags.
Ein weiterer Pipelineoperator sendet die ausgewählten geplanten Aufträge an das **Disable-ScheduledJob** -Cmdlet, von dem sie deaktiviert werden.

### Beispiel 4: deaktivieren geplanter Aufträge auf einem Remote Computer

```
PS C:\> Invoke-Command -ComputerName Srv01, Srv10 -ScriptBlock {Disable-ScheduledJob -Name TestJob}
```

Dieser Befehl deaktiviert den geplanten Auftrag TestJob auf den beiden Remotecomputern Srv01 und Srv10.

Der Befehl verwendet das Cmdlet "Invoke-Command", um den Befehl " **Deaktivierte ScheduledJob** " auf den Computern SRV01 und Srv10 auszuführen.
Der Befehl verwendet den *Name* -Parameter von **Disable-ScheduledJob** , um den geplanten Auftrag TestJob auf jedem Computer auszuwählen.

### Beispiel 5: Deaktivieren eines geplanten Auftrags anhand seiner globalen ID

```
The first command demonstrates one way of finding the GlobalID of a scheduled job. The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Format-Table cmdlet, which displays the Name, GlobalID, and Command properties of each job in a table.
PS C:\> Get-ScheduledJob | Format-Table -Property Name, GlobalID, Command -Autosize
Name             GlobalId                             Command
----             --------                             -------
ArchiveProjects1 a26a0b3d-b4e6-44d3-8b95-8706ef621f7c C:\Scripts\Archive-DxProjects.ps1
Inventory        3ac37e5d-84c0-4a8f-9661-7e88ebb8f914 \\Srv01\Scripts\Get-FullInventory.ps1
Backup-Scripts   4d0cc6be-c082-48d1-baec-1bd8278f3c81  Copy-Item C:\CurrentScripts\*.ps1 -Destination C:\BackupScripts
Test-HelpFiles   d77020ca-f20d-42be-86c8-fc64df97db90 .\Test-HelpFiles.ps1
Test-HelpFiles   2f1606d2-c6cf-4bef-8b1c-ae36a9cc9934 .\Test-DomainHelpFiles.ps1

The second command uses the  Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Where-Object cmdlet, which selects the scheduled job with the specified global ID. Another pipeline operator sends the job to the **Disable-ScheduledJob** cmdlet, which disables it.
PS C:\> Get-ScheduledJob | Where-Object {$_.GlobalID = d77020ca-f20d-42be-86c8-fc64df97db90} | Disable-ScheduledJob
```

In diesem Beispiel wird gezeigt, wie ein geplanter Auftrag nach seinem globalen Bezeichner deaktiviert wird.
Der Wert der GlobalID-Eigenschaft eines geplanten Auftrags ist eine GUID (Globally Unique Identifier).
Verwenden Sie den GlobalID-Wert, wenn es auf Genauigkeit ankommt, z. B. beim Deaktivieren von geplanten Aufträgen auf mehreren Computern.

## PARAMETERS

### -Id
Deaktiviert den geplanten Auftrag mit der angegebenen ID.
Geben Sie die ID eines geplanten Auftrags ein.

```yaml
Type: System.Int32
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Gibt den zu deaktivierenden geplanten Auftrag an.
Geben Sie eine Variable ein, die  **scheduledjobdefinition** -Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **scheduledjobdefinition** -Objekte, z. b. einen Get-ScheduledJob Befehl
Sie können ein **scheduledjobdefinition** -Objekt auch über die Pipeline an " **Deaktivierte ScheduledJob** " übergeben.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Deaktiviert die geplanten Aufträge mit den angegebenen Namen.
Geben Sie den Namen eines geplanten Auftrags ein.
Platzhalter werden unterstützt.

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

### Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition
Sie können einen geplanten Auftrag an **Disable-ScheduledJob** weiterreichen.

## AUSGABEN

### None oder Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition
Bei Verwendung des **Passthru** -Parameters gibt **Disable-ScheduledJob** den geplanten Auftrag zurück, der deaktiviert wurde.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

* " **Deaktivieren-ScheduledJob** " generiert keine Warnungen oder Fehler, wenn Sie einen geplanten Auftrag, der bereits deaktiviert ist, deaktivieren.

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
