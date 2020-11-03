---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ScheduledJob
ms.openlocfilehash: 757402a348a6b694d2f2aee53053a1b7615dbb53
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213447"
---
# Enable-ScheduledJob

## ZUSAMMENFASSUNG
Aktiviert einen geplanten Auftrag.

## SYNTAX

### Definition (Standard)

```
Enable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Definitions

```
Enable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefinitionName

```
Enable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das **enable-ScheduledJob** -Cmdlet aktiviert geplante Aufträge, die deaktiviert sind, wie z. b. solche, die mit dem Disable-ScheduledJob-Cmdlet deaktiviert werden.
Aktivierte Aufträge werden automatisch ausgeführt, wenn sie ausgelöst werden.

Um einen geplanten Auftrag zu aktivieren, legt das **enable-ScheduledJob** -Cmdlet die aktivierte Eigenschaft des geplanten Auftrags auf $true fest.

**Aktiviert-ScheduledJob** ist eine Sammlung von Auftrags Planungs-Cmdlets im **psscheduledjob** -Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Aktivieren eines geplanten Auftrags

```
PS C:\> Enable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
```

Dieser Befehl aktiviert den geplanten Auftrag mit der ID 2 auf dem lokalen Computer.
Die Ausgabe veranschaulicht die Auswirkungen des Befehls.

### Beispiel 2: Aktivieren aller geplanten Aufträge

```
PS C:\> Get-ScheduledJob | Enable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        True
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     True
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       True
```

Dieser Befehl aktiviert alle geplanten Aufträge auf dem lokalen Computer.
Er verwendet das Cmdlet "Get-ScheduledJob", um alle geplanten Aufträge zu erhalten, und das **enable-ScheduledJob-** Cmdlet, um Sie zu aktivieren.

**Enable-ScheduledJob** generiert keine Warnungen oder Fehler, wenn Sie einen geplanten Auftrag aktivieren, der bereits aktiviert ist, sodass Sie alle geplanten Aufträge ohne Bedingungen aktivieren können.

### Beispiel 3: Aktivieren ausgewählter geplanter Aufträge

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where-Object {$_.RunWithoutNetwork} | ForEach-Object {Enable-ScheduledJob -InputObject $_.JobDefinition}
```

Dieser Befehl aktiviert geplante Aufträge, die keine Netzwerkverbindung benötigen.

Der Befehl verwendet das Cmdlet "Get-ScheduledJob", um alle geplanten Aufträge auf dem Computer zu erhalten.
Ein Pipeline Operator sendet die geplanten Aufträge an das Get-ScheduledJobOption-Cmdlet, das die Auftrags Optionen jedes geplanten Auftrags abruft.
Jedes Objekt für Auftragsoptionen verfügt über eine JobDefinition-Eigenschaft, die den zugeordneten geplanten Auftrag enthält.
Die JobDefinition-Eigenschaft wird verwendet, um den Befehl abzuschließen.

Der Befehl verwendet einen Pipeline Operator (|), um die Auftrags Optionen an das Where-Object-Cmdlet zu senden, das Optionen für geplante Auftrags Optionen auswählt, bei denen die **runwithoutnetwork** -Eigenschaft den Wert true ($true) aufweist.
Ein anderer Pipeline Operator sendet die ausgewählten Optionen für geplante Auftrags Optionen an das ForEach-Object-Cmdlet, das einen **enable-ScheduledJob** -Befehl für den geplanten Auftrag im Wert der Jobdefinition-Eigenschaft jedes Auftrags Options Objekts ausführt.

### Beispiel 4: Aktivieren geplanter Aufträge auf einem Remote Computer

```
PS C:\> Invoke-Command -ComputerName "Srv01,Srv10" -ScriptBlock {Enable-ScheduledJob -Name "Inventory"}
```

Dieser Befehl aktiviert geplante Aufträge mit der Zeichenfolge „test“ im Namen auf den beiden Remotecomputern Srv01 und Srv10.

Der Befehl verwendet das Cmdlet "Invoke-Command" zum Ausführen eines **enable-ScheduledJob** -Befehls auf den Computern SRV01 und Srv10.
Der Befehl verwendet den *Name* -Parameter von **Enable-ScheduledJob** , um den geplanten Auftrag Inventory auf jedem Computer zu aktivieren.

## PARAMETERS

### -Id
Aktiviert den geplanten Auftrag mit der angegebenen ID.
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
Gibt den zu aktivierende geplanten Auftrag an.
Geben Sie eine Variable ein, die **scheduledjobdefinition** -Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **scheduledjobdefinition** -Objekte, z. b. einen Get-ScheduledJob Befehl
Sie können ein **scheduledjobdefinition** -Objekt auch über die Pipeline an **enable-ScheduledJob** übergeben.

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
Aktiviert die geplanten Aufträge mit den angegebenen Namen.
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
Sie können einen geplanten Auftrag an **enable-ScheduledJob** weiterreichen.

## AUSGABEN

### None oder Microsoft. PowerShell. ScheduledJob. scheduledjobdefinition
Bei Verwendung des **Passthru** -Parameters gibt **Enable-ScheduledJob** den geplanten Auftrag zurück, der aktiviert wurde.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

* **Enable-ScheduledJob** generiert keine Warnungen oder Fehler, wenn Sie diesen verwenden, um einen geplanten Auftrag zu aktivieren, der bereits aktiviert ist.

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
