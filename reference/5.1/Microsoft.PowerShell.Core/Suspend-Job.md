---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/suspend-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Job
ms.openlocfilehash: 6ab50342e963832d89b3dfc4128a22fc16405926
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212724"
---
# Suspend-Job

## ZUSAMMENFASSUNG
Beendet Workflowaufträge temporär.

## SYNTAX

### Sessionidparameterset (Standard)

```
Suspend-Job [-Force] [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Jobparameterset

```
Suspend-Job [-Job] <Job[]> [-Force] [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Nameparameterset

```
Suspend-Job [-Force] [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Instanceidparameterset

```
Suspend-Job [-Force] [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Filterparameterset

```
Suspend-Job [-Force] [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Stateparameterset

```
Suspend-Job [-Force] [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das **Suspend-Job-** Cmdlet hält Workflow Aufträge an.
Suspend bedeutet, dass ein Workflow Auftrag vorübergehend unterbrochen oder angehalten werden soll.
Mit diesem Cmdlet können Benutzer, die Workflows ausführen, den Workflow anhalten.
Es ergänzt die Suspend-Workflow- https://go.microsoft.com/fwlink/?LinkId=267141 Aktivität, bei der es sich um einen Befehl im Workflow handelt, der den Workflow anhält.

Das **Suspend-Job** -Cmdlet funktioniert nur für Workflowaufträge.
Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets "Start-Job".

Um einen Workflowauftrag zu identifizieren, suchen Sie nach dem Wert PSWorkflowJob in der **PSJobTypeName** -Eigenschaft des Auftrags.
Um zu bestimmen, ob ein bestimmter benutzerdefinierter Auftragstyp das **Suspend-Job** -Cmdlet unterstützt, informieren Sie sich in den Hilfethemen für den benutzerdefinierten Auftragstyp.

Wenn Sie einen Workflowauftrag anhalten, wird er bis zum nächsten Prüfpunkt ausgeführt, angehalten und gibt sofort ein Workflowauftragsobjekt zurück.
Um auf den Abschluss der Unterbrechung zu warten, bevor der Auftrag ausgeführt wird, verwenden Sie den *Wait* -Parameter von **Suspend-Job** oder das Wait-Job-Cmdlet.
Wenn der Workflow Auftrag angehalten wird, wird der Wert der **State** -Eigenschaft des Auftrags angehalten.

Das korrekte Anhalten ist von Prüfpunkten abhängig.
Der aktuelle Auftragsstatus, Metadaten und die Ausgabe werden im Prüfpunkt gespeichert, sodass der Workflow Auftrag ohne Verlust von Status oder Daten fortgesetzt werden kann.
Wenn der Workflow Auftrag keine Prüfpunkte aufweist, kann er nicht ordnungsgemäß angehalten werden.
Um Prüfpunkte zu einem Workflow hinzuzufügen, den Sie ausführen, verwenden Sie den allgemeinen *PSPersist* -Workflowparameter.
Sie können den *Force* -Parameter verwenden, um einen Workflow Auftrag sofort anzuhalten und einen Workflow Auftrag anzuhalten, der keine Prüfpunkte aufweist, aber die Aktion kann zu Zustands-und Datenverlust führen.

Bevor Sie ein Auftrags-Cmdlet für einen benutzerdefinierten Auftragstyp verwenden, z. b. einen Workflow Auftrag ( **psworkflowjob** ), importieren Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, entweder mithilfe des-Cmdlets Import-Module oder mithilfe von oder mithilfe eines Cmdlets im-Modul.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: aussetzen eines Workflow Auftrags nach Name

```
The first command creates the Get-SystemLog workflow. The workflow uses the CheckPoint-Workflow activity to define a checkpoint in the workflow.
#Sample WorkflowWorkflow Get-SystemLog
{
    $Events = Get-WinEvent -LogName System
    CheckPoint-Workflow
    InlineScript {\\Server01\Scripts\Analyze-SystemEvents.ps1 -Events $Events}
}

The second command uses the *AsJob* parameter that is common to all workflows to run the Get-SystemLog workflow as a background job. The command uses the *JobName* workflow common parameter to specify a friendly name for the workflow job.
PS C:\> Get-SystemLog -AsJob -JobName "Get-SystemLogJob"

The third command uses the **Get-Job** cmdlet to get the Get-SystemLogJob workflow job. The output shows that the value of the **PSJobTypeName** property is PSWorkflowJob.
PS C:\> Get-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Running     True            localhost   Get-SystemLog

The fourth command uses the **Suspend-Job** cmdlet to suspend the Get-SystemLogJob job. The job runs to the checkpoint and then suspends.
PS C:\> Suspend-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Suspended   True            localhost   Get-SystemLog
```

In diesem Beispiel wird veranschaulicht, wie ein Workflowauftrag angehalten wird.

### Beispiel 2: aussetzen und Fortsetzen eines Workflow Auftrags

```
The first command suspends the LogWorkflowJob job.The command returns immediately. The output shows that the workflow job is still running, even though it is being suspended.
PS C:\> Suspend-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow

The second command uses the **Get-Job** cmdlet to get the LogWorkflowJob job. The output shows that the workflow job suspended successfully.
PS C:\> Get-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Suspended     True            localhost            LogWorkflow

The third command uses the **Get-Job** cmdlet to get the LogWorkflowJob job and the Resume-Job cmdlet to resume it. The output shows that the workflow job resumed successfully and is now running.
PS C:\> Get-Job -Name LogWorkflowJob | Resume-Job
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow
```

In diesem Beispiel wird veranschaulicht, wie ein Workflowauftrag angehalten und fortgesetzt wird.

### Beispiel 3: aussetzen eines Workflow Auftrags auf einem Remote Computer

```
PS C:\> Invoke-Command -ComputerName Srv01 -Scriptblock {Suspend-Job -Filter @{CustomID="031589"}
```

Dieser Befehl verwendet das Cmdlet "Invoke-Command" zum Aussetzen eines Workflow Auftrags auf dem Remote Computer SRV01.
Der Wert des *Filter* -Parameters ist eine Hash Tabelle, die einen "CustomId"-Wert angibt.
Diese **CustomID** umfasst Auftragsmetadaten ( **PSPrivateMetadata** ).

### Beispiel 4: warten auf das Aussetzen des Workflow Auftrags

```
PS C:\> Suspend-Job VersionCheck -Wait
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
 5     VersionCheck  PSWorkflowJob      Suspended     True            localhost            LogWorkflow
```

Dieser Befehl hält den VersionCheck-Workflowauftrag an.
Der Befehl verwendet den *Wait* -Parameter, um zu warten, bis der Workflowauftrag angehalten wurde.
Wenn der Workflow Auftrag bis zum nächsten Prüfpunkt ausgeführt und angehalten wurde, wird der Befehl abgeschlossen und gibt das Auftrags Objekt zurück.

### Beispiel 5: erzwingen, dass ein Workflow Auftrag angehalten wird

```
PS C:\> Suspend-Job Maintenance -Force
```

Dieser Befehl erzwingt das Anhalten des Maintenance-Workflowauftrags
Der Wartungsauftrag weist keine Prüfpunkte auf.
Sie kann nicht ordnungsgemäß angehalten und nicht ordnungsgemäß fortgesetzt werden.

## PARAMETERS

### -Filter
Gibt eine Hash Tabelle mit Bedingungen an.
Dieses Cmdlet hält Aufträge an, die alle Bedingungen erfüllen.
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

### -Force
Hält den Workflowauftrag sofort an.
Diese Aktion kann zu einem Verlust des Zustands und der Daten führen.

Standardmäßig wird der Workflowauftrag mit **Suspend-Job** bis zum nächsten Prüfpunkt ausgeführt und dann angehalten.
Mit diesem Parameter können Sie auch Workflowaufträge ohne Prüfpunkte anhalten.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: F

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Gibt die IDs von Aufträgen an, die von diesem Cmdlet angehalten werden.

Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.
Es ist einfacher, sich zu merken und als die Instanz-ID einzugeben, aber es ist nur in der aktuellen Sitzung eindeutig.
Sie können eine oder mehrere IDs (durch Kommas getrennt) eingeben.
Um die ID eines Auftrags zu ermitteln, verwenden Sie das Cmdlet "Get-Job".

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
Gibt die Instanz-IDs von Aufträgen an, die von diesem Cmdlet angehalten werden.
Standardmäßig werden alle Aufträge fortgesetzt.

Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.
Zum Ermitteln der Instanz-ID eines Auftrags verwenden Sie **Get-Job** .

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
Gibt die Workflow Aufträge an, die von diesem Cmdlet beendet werden.
Geben Sie eine Variable ein, die die Workflowaufträge enthält, oder einen Befehl, der die Workflowaufträge abruft.
Sie können Workflowaufträge auch an das **Suspend-Job** -Cmdlet weiterreichen.

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
Gibt die anzeigen Amen von Aufträgen an, die von diesem Cmdlet angehalten werden.
Geben Sie einen oder mehrere Workflowauftragsnamen ein.
Platzhalterzeichen werden unterstützt.

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
Gibt einen Auftragsstatus an.
Dieses Cmdlet beendet nur Aufträge im angegebenen Zustand.
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

**Suspend-Job** hält nur Workflow Aufträge im Status wird **ausgeführt** an.

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
Gibt an, dass dieses Cmdlet die Eingabeaufforderung unterdrückt, bis sich der Workflow Auftrag im angehaltenen Zustand befindet.
Standardmäßig wird **Suspend-Job** sofort zurückgegeben, auch wenn sich der Workflow Auftrag noch nicht im angehaltenen Zustand befindet.

Der *Wait* -Parameter entspricht der Weiterleitung eines **Suspend-Job-** Befehls an das **Wait-Job-** Cmdlet.

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
Wenn **Suspend-Job** jedoch einen Auftrag eines nicht unterstützten Typs erhält, wird ein Abbruch Fehler zurückgegeben.

## AUSGABEN

### System. Management. Automation. Job
Mit diesem Cmdlet werden die Aufträge zurückgegeben, die angehalten wurden.

## HINWEISE

* Der Mechanismus und der Speicherort für einen angehaltenen Auftrag können je nach Auftragstyp unterschiedlich sein. Beispielsweise werden angehaltene Workflowaufträge standardmäßig in einem Flatfilespeicher gespeichert, sie können jedoch auch in einer Datenbank gespeichert werden.
* Wenn Sie einen Workflowauftrag weiterleiten, der nicht den Status Running aufweist, zeigt **Suspend-Job** eine Warnmeldung an. Um die Warnung zu unterdrücken, verwenden Sie den allgemeinen *WarningAction* -Parameter mit dem Wert SilentlyContinue.

  Wenn es sich bei einem Auftrag nicht um einen Typ handelt, der das Anhalten unterstützt, gibt **Suspend-Job** einen abschließenden Fehler zurück.

* Verwenden Sie den *State* -Parameter des **Get-Job-** Cmdlets, um Workflow Aufträge mit dem Status "angehalten" zu ermitteln, die angehalten wurden, einschließlich der von diesem Cmdlet angehaltenen Workflow Aufträge.
* Einige Auftragstypen verfügen über Optionen oder Eigenschaften, die das Anhalten des Auftrags durch Windows PowerShell verhindern. Wenn der Versuch, den Auftrag anzuhalten, fehlschlägt, überprüfen Sie, ob die Auftrags Optionen und-Eigenschaften das Anhalten zulassen.

## VERWANDTE LINKS

[Get-Job](Get-Job.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
