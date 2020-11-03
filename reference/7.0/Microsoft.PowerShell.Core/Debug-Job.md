---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/debug-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Job
ms.openlocfilehash: 947fcea58ea32e34bdd0dc0129443ac5bc39c561
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210871"
---
# Debug-Job

## ZUSAMMENFASSUNG
Debuggen eines laufenden Hintergrund-, Remote-oder PowerShell-Workflow Auftrags.

## SYNTAX

### Jobparameterset (Standard)

```
Debug-Job [-Job] <Job> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Jobnameparameterset

```
Debug-Job [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Jobidparameterset

```
Debug-Job [-Id] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Jobinstanceidparameterset

```
Debug-Job [-InstanceId] <Guid> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mit dem Cmdlet " **Debug-Job** " können Sie Skripts debuggen, die in Aufträgen ausgeführt werden.
Mit dem-Cmdlet können Sie PowerShell-Workflow Aufträge, Hintergrund Aufträge und in Remote Sitzungen ausgeführten Aufträgen Debuggen.
**Debug-Job** akzeptiert ein Auftrags Objekt, einen Namen, eine ID oder eine Instanz-ID als Eingabe und startet eine Debugsitzung für das Skript, das ausgeführt wird.
Der Debugger-Befehl **Beenden** beendet den Auftrag und führt das Skript aus.
Ab Windows PowerShell 5,0 trennt der Befehl **Exit** den Debugger und ermöglicht die Fortsetzung des Auftrags.

## BEISPIELE

### Beispiel 1: Debuggen eines Auftrags nach Auftrags-ID

```
PS C:\> Debug-Job -ID 3
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
3      Job3            RemoteJob       Running       True            PowerShellIx         TestWFDemo1.ps1
          Entering debug mode. Use h or ? for help.

          Hit Line breakpoint on 'C:\TestWFDemo1.ps1:8'

          At C:\TestWFDemo1.ps1:8 char:5
          +     Write-Output -InputObject "Now writing output:"
          +     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
          [DBG:PowerShellIx]: PS C:\> > list

              3:
              4:  workflow SampleWorkflowTest
              5:  {
              6:      param ($MyOutput)
              7:
              8:*     Write-Output -InputObject "Now writing output:"
              9:      Write-Output -Input $MyOutput
             10:
             11:      Write-Output -InputObject "Get PowerShell process:"
             12:      Get-Process -Name powershell
             13:
             14:      Write-Output -InputObject "Workflow function complete."
             15:  }
             16:
             17:  # Call workflow function
             18:  SampleWorkflowTest -MyOutput "Hello"
```

Dieser Befehl unterbricht einen laufenden Auftrag mit der ID 3.

## PARAMETERS

### -Id
Gibt die ID-Nummer eines laufenden Auftrags an.
Um die ID-Nummer eines Auftrags zu erhalten, führen Sie das Get-Job-Cmdlet aus.

```yaml
Type: System.Int32
Parameter Sets: JobIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId
Gibt die Instanz-ID-GUID eines laufenden Auftrags an.
Um die *InstanceId* eines Auftrags zu erhalten, führen Sie das **Get-Job-** Cmdlet aus, und übergeben Sie die Ergebnisse in ein **Format-*-** Cmdlet, wie im folgenden Beispiel gezeigt:

`Get-Job | Format-List -Property Id,Name,InstanceId,State`

```yaml
Type: System.Guid
Parameter Sets: JobInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Auftrag
Gibt ein Auftrags Objekt an, das ausgeführt wird.
Die einfachste Möglichkeit, diesen Parameter zu verwenden, ist das Speichern der Ergebnisse eines **Get-Job-** Befehls, der den laufenden Auftrag zurückgibt, den Sie in einer Variablen debuggen möchten, und dann die Variable als Wert dieses Parameters angeben.

```yaml
Type: System.Management.Automation.Job
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Gibt einen Auftrag mit dem anzeigen amen des Auftrags an.
Wenn Sie einen Auftrag starten, können Sie einen Auftrags Namen angeben, indem Sie den *Jobname* -Parameter in Cmdlets wie Invoke-Command und Start-Job hinzufügen.

```yaml
Type: System.String
Parameter Sets: JobNameParameterSet
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

### System. Management. Automation. remotingjob

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[Get-Job](Get-Job.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Wait-Job](Wait-Job.md)
