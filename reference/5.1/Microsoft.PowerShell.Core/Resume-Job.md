---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 85cbfad2a4866bf18e69fb99afb8698e233c4c80
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212775"
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
Das **Resume-Job-** Cmdlet setzt einen Workflow Auftrag fort, der angehalten wurde, z. b. mit dem Suspend-Job-Cmdlet oder der about_Suspend-Workflow-Aktivität.
Wenn ein Workflow Auftrag fortgesetzt wird, rekonstruiert die Auftrags-Engine den Zustand, die Metadaten und die Ausgabe aus gespeicherten Ressourcen, wie z. b. Prüfpunkten.
Der Auftrag wird ohne Verlust von Status oder Daten neu gestartet.
Der Status des Auftrags wird von **Suspended** in **Running** geändert.

Verwenden Sie die Parameter von **Resume-Job** , um Aufträge anhand des Namens, der ID, der Instanz-ID oder der Pipe eines Auftrags Objekts (z. b. eines vom Get-Job-Cmdlet zurückgegebenen Auftrags) an **Resume-Job** auszuwählen.
Um einen fortzusetzenden Auftrag auszuwählen, können Sie auch einen Eigenschaftenfilter verwenden.

Standardmäßig wird **Resume-Job** sofort zurückgegeben, selbst wenn noch nicht alle Aufträge wieder aufgenommen wurden.
Um die Eingabeaufforderung zu unterdrücken, bis alle angegebenen Aufträge wieder aufgenommen wurden, verwenden Sie den *Wait* -Parameter.

Das **Resume-Job** -Cmdlet funktioniert nur mit benutzerdefinierten Auftragstypen, wie z. B. Workflowaufträgen.
Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets "Start-Job".
Wenn Sie einen Auftrag eines nicht unterstützten Typs übermitteln, generiert **Resume-Job** einen Fehler mit Abbruch und die Ausführung wird beendet.

Um einen Workflowauftrag zu identifizieren, suchen Sie nach dem Wert **PSWorkflowJob** in der **PSJobTypeName** -Eigenschaft des Auftrags.
Um zu bestimmen, ob ein benutzerdefinierter Auftragstyp das **Resume-Job** -Cmdlet unterstützt, nutzen Sie die Hilfethemen für den benutzerdefinierten Auftragstyp.

Bevor Sie ein Job-Cmdlet für einen benutzerdefinierten Auftragstyp verwenden, importieren Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, entweder mithilfe des Cmdlets "Import-Module" oder mithilfe eines Cmdlets im Modul.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Fortsetzen eines Auftrags nach ID

```
The first command uses the **Get-Job** cmdlet to get the job. The output shows that the job is a suspended workflow job.
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

The second command uses the *Id* parameter of the **Resume-Job** cmdlet to resume the job with an *Id* value of 4.
PS C:\> Resume-Job -Id 4
```

Die Befehle in diesem Beispiel prüfen, ob es sich bei dem Auftrag um einen angehaltenen Workflowauftrag handelt, und setzen den Auftrag anschließend fort.

### Beispiel 2: Fortsetzen eines Auftrags nach Name

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

Dieser Befehl verwendet den *Name* -Parameter, um mehrere Workflowaufträge auf dem lokalen Computer fortzusetzen.

### Beispiel 3: Verwenden von benutzerdefinierten Eigenschafts Werten

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

Dieser Befehl verwendet den Wert einer benutzerdefinierten Eigenschaft, um den fortzusetzenden Workflowauftrag zu identifizieren.
Der Befehl verwendet den *Filter* -Parameter zum Identifizieren des Workflowauftrags nach seiner **CustomID** -Eigenschaft.
Darüber hinaus überprüft er mithilfe des *State* -Parameters, ob der Workflowauftrag angehalten wurde, bevor er versucht, ihn fortzusetzen.

### Beispiel 4: Fortsetzen aller angehaltenen Aufträge auf einem Remote Computer

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

Mit diesem Befehl werden alle angehaltenen Aufträge auf dem Remotecomputer „Srv01“ fortgesetzt.

Der Befehl verwendet das Cmdlet "Invoke-Command", um einen Befehl auf dem SRV01-Computer auszuführen.
Der Remote Befehl verwendet den *State* -Parameter des **Get-Job-** Cmdlets, um alle angehaltenen Aufträge auf dem Computer zu erhalten.
Ein Pipelineoperator (|) sendet die angehaltenen Aufträge an das **Resume-Job** -Cmdlet, welches sie fortsetzt.

### Beispiel 5: warten auf Fortsetzen von Aufträgen

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

Dieser Befehl verwendet den *Wait* -Parameter, um **Resume-Job** nur dann zurückzugeben, wenn alle angegebenen Aufträge fortgesetzt werden.
Der *Wait* -Parameter ist besonders in Skripts nützlich, die davon ausgehen, dass Aufträge fortgesetzt werden, bevor das Skript fortfährt.

### Beispiel 6: Fortsetzen eines Workflows, der sich selbst anhält

```
This code sample shows the **Suspend-Workflow** activity in a workflow.
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

The following command runs the Test-Suspend workflow on the Server01 computer.When you run the workflow, the workflow runs the Get-Date activity and stores the result in the $a variable. Then it runs the Suspend-Workflow activity. In response, it takes a checkpoint, suspends the workflow, and returns a workflow job object.  Suspend-Workflow returns a workflow job object even if the workflow is not explicitly run as a job.
PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

The following command resumes the Test-Suspend workflow in Job8. It uses the *Wait* parameter to hold the command prompt until the job is resumed.
PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command

--     ----            -------------   -----         -----------     --------             -------

8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

This command uses the **Receive-Job** cmdlet to get the results of the Test-Suspend workflow. The final command in the workflow returns a **TimeSpan** object that represents the elapsed time between the current date and time and the date and time that was saved in the $a variable before the workflow was suspended.
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

Mit dem **Resume-Job-** Cmdlet können Sie einen Workflow Auftrag fortsetzen, der mithilfe der **Suspend-Workflow-** Aktivität angehalten wurde.
Diese Aktivität hält einen Workflow innerhalb eines Workflows an.
Die Aktivität ist nur in Workflows gültig.

Informationen über Suspend-Workflow finden Sie unter about_Suspend-Workflow.

## PARAMETERS

### -Filter
Gibt eine Hash Tabelle mit Bedingungen an.
Mit diesem Cmdlet werden Aufträge, die alle Bedingungen in der Hash Tabelle erfüllen, fortgesetzt.
Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.

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

Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.
Es ist einfacher, sich zu merken und als die Instanz-ID einzugeben, aber es ist nur in der aktuellen Sitzung eindeutig.
Sie können eine oder mehrere IDs (durch Kommas getrennt) eingeben.
Um die ID eines Auftrags zu ermitteln, führen **Sie Get-Job** aus.

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
Gibt ein Array von Instanz-IDs von Aufträgen an, die von diesem Cmdlet fortgesetzt werden.
Standardmäßig werden alle Aufträge fortgesetzt.

Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.
Um die Instanz-ID eines Auftrags zu ermitteln, führen **Sie Get-Job** aus.

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
Gibt die fortzusetzenden Aufträge an.
Geben Sie eine Variable ein, die entweder die Aufträge oder einen Befehl enthält, durch den die Aufträge abgerufen werden.
Sie können Aufträge auch über die Pipeline an das **Resume-Job** -Cmdlet übergeben.

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
Gibt ein Array von anzeigen Amen von Aufträgen an, die von diesem Cmdlet fortgesetzt werden.
Geben Sie mindestens einen Auftragsnamen ein.
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
Gibt den Status der fort zusetzenden Aufträge an.
Zulässige Werte für diesen Parameter:

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

Weitere Informationen zu Auftrags Zuständen finden Sie unter [jobstate-Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in der MSDN Library.

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
Gibt an, dass dieses Cmdlet die Eingabeaufforderung unterdrückt, bis alle Auftrags Ergebnisse neu gestartet werden.
Standardmäßig gibt dieses Cmdlet sofort die verfügbaren Ergebnisse zurück.

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

### System. Management. Automation. Job
Sie können alle Arten von Aufträgen an dieses Cmdlet weiterreichen.
Wenn **Resume-Job** einen Auftrag eines nicht unterstützten Typs erhält, wird ein Abbruch Fehler zurückgegeben.

## AUSGABEN

### Keine, System. Management. Automation. Job
Dieses Cmdlet gibt die Aufträge zurück, die wieder aufgenommen werden sollen, wenn Sie den *passthru* -Parameter verwenden.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

* **Resume-Job** kann nur Aufträge fortsetzen, die angehalten wurden. Wenn Sie einen Auftrag in einem anderen Zustand übermitteln, führt **Resume-Job** den Wiederaufnahmevorgang zwar aus, generiert jedoch eine Warnmeldung, dass der Auftrag nicht fortgesetzt werden konnte. Um die Warnung zu unterdrücken, verwenden Sie den allgemeinen *WarningAction* -Parameter mit dem Wert SilentlyContinue.
* Wenn es sich bei einem Auftrag nicht um einen Typ handelt, der das fortsetzen unterstützt, z. b. einen Workflow Auftrag ( **psworkflowjob** ), gibt **Resume-Job** einen abschließenden Fehler zurück.
* Der Mechanismus und der Speicherort für einen angehaltenen Auftrag können je nach Auftragstyp unterschiedlich sein. Beispielsweise werden angehaltene Workflowaufträge standardmäßig in einem Flatfile-Speicher gespeichert, können aber auch in einer SQL-Datenbank gespeichert werden.
* Wenn Sie einen Auftrag fortsetzen, ändert sich der Status des Auftrags von **Suspended** in **Running** . Verwenden Sie den *State* -Parameter des **Get-Job-** Cmdlets, um Aufträge mit dem Status "wird **ausgeführt** " zu ermitteln, die ausgeführt werden, einschließlich der mit diesem Cmdlet fortgesetzten Aufträge.
* Einige Auftragstypen verfügen über Optionen oder Eigenschaften, die das Anhalten des Auftrags durch Windows PowerShell verhindern. Wenn der Versuch, den Auftrag anzuhalten, fehlschlägt, überprüfen Sie, ob die Auftrags Optionen und-Eigenschaften das Anhalten zulassen.

## VERWANDTE LINKS

[Get-Job](Get-Job.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
