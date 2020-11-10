---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 6d08d9053e100cb53d37a6e4931d118f90c35a6a
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388534"
---
# Resume-Job

## ZUSAMMENFASSUNG
Startet einen angehaltenen Auftrag neu.

## SYNTAX

### Sessionidparameterset (Standard)

```
Resume-Job [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Jobparameterset

```
Resume-Job [-Job] <Job[]> [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Nameparameterset

```
Resume-Job [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Instanceidparameterset

```
Resume-Job [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Stateparameterset

```
Resume-Job [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Filterparameterset

```
Resume-Job [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Resume-Job` Cmdlet wird ein Workflow Auftrag, der angehalten wurde, wie z `Suspend-Job` . b. mithilfe des-Cmdlets oder der [about_Suspend-Workflow-](../PSWorkflow/about/about_Suspend-Workflow.md) Aktivität fortgesetzt. Wenn ein Workflow Auftrag fortgesetzt wird, rekonstruiert die Auftrags-Engine den Zustand, die Metadaten und die Ausgabe aus gespeicherten Ressourcen, wie z. b. Prüfpunkten. Der Auftrag wird ohne Verlust von Status oder Daten neu gestartet.
Der Status des Auftrags wird von **Suspended** in **Running** geändert.

Wählen Sie mithilfe der Parameter von `Resume-Job` Aufträge nach Name, ID, Instanz-ID aus, oder übergeben Sie ein Auftrags Objekt, z. b. ein vom Cmdlet zurück gegebenes-Objekt `Get-Job` an `Resume-Job` . Um einen fortzusetzenden Auftrag auszuwählen, können Sie auch einen Eigenschaftenfilter verwenden.

Standardmäßig wird `Resume-Job` sofort zurückgegeben, obwohl möglicherweise noch nicht alle Aufträge fortgesetzt werden. Um die Eingabeaufforderung zu unterdrücken, bis alle angegebenen Aufträge wieder aufgenommen wurden, verwenden Sie den **Wait** -Parameter.

Das- `Resume-Job` Cmdlet funktioniert nur mit benutzerdefinierten Auftrags Typen, z. b. Workflow Aufträgen. Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des `Start-Job` Cmdlets. Wenn Sie einen Auftrag mit einem nicht unterstützten Typ übermitteln, wird von `Resume-Job` ein Abbruch Fehler generiert, und die Ausführung wird beendet.

Um einen Workflowauftrag zu identifizieren, suchen Sie nach dem Wert **PSWorkflowJob** in der **PSJobTypeName** -Eigenschaft des Auftrags. Informationen zum bestimmen, ob ein bestimmter benutzerdefinierter Auftragstyp das- `Resume-Job` Cmdlet unterstützt, finden Sie in den Hilfe Themen für den benutzerdefinierten Auftragstyp.

Bevor Sie ein Job-Cmdlet für einen benutzerdefinierten Auftragstyp verwenden, importieren Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, entweder mithilfe des `Import-Module` Cmdlets oder mithilfe eines Cmdlets im Modul.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Fortsetzen eines Auftrags nach ID

Die Befehle in diesem Beispiel prüfen, ob es sich bei dem Auftrag um einen angehaltenen Workflowauftrag handelt, und setzen den Auftrag anschließend fort. Der erste Befehl verwendet das `Get-Job` Cmdlet, um den Auftrag zu erhalten. Die Ausgabe zeigt, dass es sich bei dem Auftrag um einen angehaltenen Workflowauftrag handelt. Der zweite Befehl verwendet den **ID** -Parameter des `Resume-Job` Cmdlets, um den Auftrag mit dem **ID** -Wert 4 fortzusetzen.

```
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

PS C:\> Resume-Job -Id 4
```

### Beispiel 2: Fortsetzen eines Auftrags nach Name

Dieser Befehl verwendet den **Name** -Parameter, um mehrere Workflowaufträge auf dem lokalen Computer fortzusetzen.

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

### Beispiel 3: Verwenden von benutzerdefinierten Eigenschafts Werten

Dieser Befehl verwendet den Wert einer benutzerdefinierten Eigenschaft, um den fortzusetzenden Workflowauftrag zu identifizieren. Der Befehl verwendet den **Filter** -Parameter zum Identifizieren des Workflowauftrags nach seiner **CustomID** -Eigenschaft. Darüber hinaus überprüft er mithilfe des **State** -Parameters, ob der Workflowauftrag angehalten wurde, bevor er versucht, ihn fortzusetzen.

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

### Beispiel 4: Fortsetzen aller angehaltenen Aufträge auf einem Remote Computer

Mit diesem Befehl werden alle angehaltenen Aufträge auf dem Remotecomputer „Srv01“ fortgesetzt.

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

Der Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines Befehls auf dem SRV01-Computer. Der Remote Befehl verwendet den **State** -Parameter des `Get-Job` Cmdlets, um alle angehaltenen Aufträge auf dem Computer zu erhalten. Ein Pipeline Operator ( `|` ) sendet die angehaltenen Aufträge an das `Resume-Job` Cmdlet, das Sie wieder aufnimmt.

### Beispiel 5: warten auf Fortsetzen von Aufträgen

Dieser Befehl verwendet den **Wait** -Parameter, um `Resume-Job` nur zurückzugeben, nachdem alle angegebenen Aufträge wieder aufgenommen wurden. Der **Wait** -Parameter ist besonders in Skripts nützlich, die davon ausgehen, dass Aufträge fortgesetzt werden, bevor das Skript fortfährt.

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

### Beispiel 6: Fortsetzen eines Workflows, der sich selbst anhält

Dieses Codebeispiel zeigt die- `Suspend-Workflow` Aktivität in einem Workflow.

Der `Test-Suspend` Workflow auf dem Server01-Computer. Wenn Sie den Workflow ausführen, führt der Workflow die `Get-Date` -Aktivität aus und speichert das Ergebnis in der `$a` Variablen. Anschließend wird die- `Suspend-Workflow` Aktivität ausgeführt. Als Reaktion darauf erstellt er einen Prüfpunkt, hält den Workflow an und gibt ein Workflowauftragsobjekt zurück. `Suspend-Workflow` Gibt ein Workflow Auftrags Objekt zurück, auch wenn der Workflow nicht explizit als Auftrag ausgeführt wird.

`Resume-Job` nimmt den `Test-Suspend` Workflow in Job8 wieder auf. Der Befehl verwendet den **Wait** -Parameter, um die Eingabeaufforderung anzuhalten, bis der Auftrag fortgesetzt wird.

Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse des `Test-Suspend` Workflows abgerufen. Der letzte Befehl im Workflow gibt ein **TimeSpan** -Objekt zurück, das die verstrichene Zeit zwischen dem aktuellen Datum und der aktuellen Uhrzeit und dem Datum und der Uhrzeit darstellt, die in der Variablen gespeichert wurden, `$a` bevor der Workflow angehalten wurde.

```
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

PS C:\> Receive-Job -Name Job8
        Days              : 0
        Hours             : 0
        Minutes           : 0
        Seconds           : 19
        Milliseconds      : 823
        Ticks             : 198230041
        TotalDays         : 0.000229432917824074
        TotalHours        : 0.00550639002777778
        TotalMinutes      : 0.330383401666667
        TotalSeconds      : 19.8230041
        TotalMilliseconds : 19823.0041
        PSComputerName    : Server01
```

Mit dem- `Resume-Job` Cmdlet können Sie einen Workflow Auftrag, der angehalten wurde, mithilfe der-Aktivität fortsetzen `Suspend-Workflow` . Diese Aktivität hält einen Workflow innerhalb eines Workflows an. Die Aktivität ist nur in Workflows gültig.

Weitere Informationen zum finden Sie unter `Suspend-Workflow` about_Suspend-Workflow] (.. /Psworkflow/about/about_Suspend-Workflow. MD).

## PARAMETERS

### -Filter

Gibt eine Hash Tabelle mit Bedingungen an. Mit diesem Cmdlet werden Aufträge, die alle Bedingungen in der Hash Tabelle erfüllen, fortgesetzt. Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id

Gibt ein Array von IDs für Aufträge an, die von diesem Cmdlet fortgesetzt werden.

Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert. Es ist einfacher, sich zu merken und als die Instanz-ID einzugeben, aber es ist nur in der aktuellen Sitzung eindeutig. Sie können eine oder mehrere IDs (durch Kommas getrennt) eingeben. Um die ID eines Auftrags zu ermitteln, führen Sie aus `Get-Job` .

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Gibt ein Array von Instanz-IDs von Aufträgen an, die von diesem Cmdlet fortgesetzt werden. Standardmäßig werden alle Aufträge fortgesetzt.

Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert. Führen Sie aus, um die Instanz-ID eines Auftrags zu ermitteln `Get-Job` .

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Auftrag

Gibt die fortzusetzenden Aufträge an. Geben Sie eine Variable ein, die entweder die Aufträge oder einen Befehl enthält, durch den die Aufträge abgerufen werden. Sie können Aufträge auch über die Pipeline an das `Resume-Job` Cmdlet übergeben.

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Gibt ein Array von anzeigen Amen von Aufträgen an, die von diesem Cmdlet fortgesetzt werden. Geben Sie mindestens einen Auftragsnamen ein.
Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State

Gibt den Status der fort zusetzenden Aufträge an. Zulässige Werte für diesen Parameter:

- NotStarted
- Wird ausgeführt
- Abgeschlossen
- Fehler
- Beendet
- Blockiert
- Ausgesetzt
- Getrennt
- Wird angehalten
- Wird beendet

Mit diesem Cmdlet werden nur Aufträge im angehaltenen **Zustand fort** gesetzt.

Weitere Informationen zu Auftrags Zuständen finden Sie unter [jobstate-Enumeration](/dotnet/api/system.management.automation.jobstate).

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Wait

Gibt an, dass dieses Cmdlet die Eingabeaufforderung unterdrückt, bis alle Auftrags Ergebnisse neu gestartet werden. Standardmäßig gibt dieses Cmdlet sofort die verfügbaren Ergebnisse zurück.

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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

### System. Management. Automation. Job

Sie können alle Arten von Aufträgen an dieses Cmdlet weiterreichen. Wenn `Resume-Job` einen Auftrag eines nicht unterstützten Typs abruft, wird ein Abbruch Fehler zurückgegeben.

## AUSGABEN

### Keine, System. Management. Automation. Job

Dieses Cmdlet gibt die Aufträge zurück, die wieder aufgenommen werden sollen, wenn Sie den **passthru** -Parameter verwenden.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

- `Resume-Job` kann nur Aufträge fortsetzen, die angehalten wurden. Wenn Sie einen Auftrag in einem anderen Zustand übermitteln, `Resume-Job` führt den Wiederaufnahme Vorgang für den Auftrag aus, generiert jedoch eine Warnung, um Sie darüber zu benachrichtigen, dass der Auftrag nicht fortgesetzt werden konnte. Um die Warnung zu unterdrücken, verwenden Sie den allgemeinen **WarningAction** -Parameter mit dem Wert SilentlyContinue.
- Wenn ein Auftrag nicht von einem Typ ist, der das fortsetzen unterstützt, wie z. b. ein Workflow Auftrag ( **psworkflowjob** ), wird `Resume-Job` ein Abbruch Fehler zurückgegeben.
- Der Mechanismus und der Speicherort für einen angehaltenen Auftrag können je nach Auftragstyp unterschiedlich sein. Beispielsweise werden angehaltene Workflowaufträge standardmäßig in einem Flatfile-Speicher gespeichert, können aber auch in einer SQL-Datenbank gespeichert werden.
- Wenn Sie einen Auftrag fortsetzen, ändert sich der Status des Auftrags von **Suspended** in **Running**. Zum Ermitteln der Aufträge, die ausgeführt werden, einschließlich derjenigen, die mit diesem Cmdlet fortgesetzt wurden, verwenden Sie den **State** -Parameter des `Get-Job` Cmdlets, um Aufträge mit dem Status "wird **ausgeführt** " zu ermitteln.
- Einige Auftragstypen verfügen über Optionen oder Eigenschaften, die das Anhalten des Auftrags durch Windows PowerShell verhindern.
  Wenn der Versuch, den Auftrag anzuhalten, fehlschlägt, überprüfen Sie, ob die Auftrags Optionen und-Eigenschaften das Anhalten zulassen.

## VERWANDTE LINKS

[Get-Job](Get-Job.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
