---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 0b9c76ca1e26adaa244473366c2eabdaaa28452c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212031"
---
# Get-Job

## ZUSAMMENFASSUNG
Ruft PowerShell-Hintergrund Aufträge ab, die in der aktuellen Sitzung ausgeführt werden.

## SYNTAX

### Sessionidparameterset (Standard)

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### Commandparameterset

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### Instanceidparameterset

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### Nameparameterset

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### Stateparameterset

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### Filterparameterset

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION

Das **Get-Job** -Cmdlet ruft Objekte ab, die die in der aktuellen Sitzung gestarteten Hintergrundaufträge darstellen.
Sie können **Get-Job** verwenden, um Aufträge zu erhalten, die mit dem Cmdlet "Start-Job" oder mit dem *AsJob* -Parameter eines beliebigen Cmdlets gestartet wurden.

Ohne Parameter ruft ein **Get-Job-** Befehl alle Aufträge in der aktuellen Sitzung ab.
Mithilfe der Parameter von **Get-Job** können Sie bestimmte Aufträge abrufen.

Das von **Get-Job** zurückgegebene Auftragsobjekt enthält nützliche Informationen zum Auftrag, aber keine Auftragsergebnisse.
Verwenden Sie das Cmdlet "Receive-Job", um die Ergebnisse zu erhalten.

Ein Windows PowerShell-Hintergrund Auftrag ist ein Befehl, der im Hintergrund ausgeführt wird, ohne mit der aktuellen Sitzung zu interagieren.
In der Regel verwenden Sie einen Hintergrund Auftrag, um einen komplexen Befehl auszuführen, der lange Zeit in Anspruch nimmt.
Weitere Informationen zu Hintergrundaufträgen in Windows PowerShell finden Sie unter about_Jobs.

Ab Windows PowerShell 3.0 ruft das **Get-Job** -Cmdlet auch benutzerdefinierte Auftragstypen ab, wie z. B. Workflowaufträge und Instanzen von geplanten Aufträgen.
Zum Ermitteln des Auftragstyps eines Auftrags verwenden Sie die **PSJobTypeName** -Eigenschaft des Auftrags.

Zum Aktivieren von **Get-Job** zum erhalten eines benutzerdefinierten Auftrags Typs importieren Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, in die Sitzung, bevor Sie einen **Get-Job-** Befehl ausführen. verwenden Sie hierzu entweder das Cmdlet "Import-Module", oder verwenden Sie ein Cmdlet im Modul.
Informationen zu einem bestimmten benutzerdefinierten Auftragstyp finden Sie in der Dokumentation der Funktion „Benutzerdefinierte Auftragstypen“.

## BEISPIELE

### Beispiel 1: alle Hintergrund Aufträge, die in der aktuellen Sitzung gestartet wurden

```
PS C:\> Get-Job
```

Dieser Befehl ruft alle Hintergrundaufträge ab, die in der aktuellen Sitzung gestartet wurden.
In anderen Sitzungen erstellte Aufträge sind nicht enthalten, auch wenn die Aufträge auf dem lokalen Computer ausgeführt werden.

### Beispiel 2: Beenden eines Auftrags mit einer Instanz-ID

```
The first command uses the **Get-Job** cmdlet to get a job. It uses the *Name* parameter to identify the job. The command stores the job object that **Get-Job** returns in the $j variable. In this example, there is only one job with the specified name.
PS C:\> $j = Get-Job -Name Job1

The second command gets the **InstanceId** property of the object in the $j variable and stores it in the $ID variable.
PS C:\> $ID = $j.InstanceID

The third command displays the value of the $ID variable.
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

The fourth command uses Stop-Job cmdlet to stop the job. It uses the *InstanceId* parameter to identify the job and $ID variable to represent the instance ID of the job.
PS C:\> Stop-Job -InstanceId $ID
```

Diese Befehle zeigen, wie die Instanz-ID eines Auftrags abgerufen und dann zum Beenden eines Auftrags verwendet wird.
Im Gegensatz zum Namen eines Auftrags, der nicht eindeutig ist, ist die Instanz-ID eindeutig.

### Beispiel 3: Get-Aufträge, die einen bestimmten Befehl enthalten

```
PS C:\> Get-Job -Command "*get-process*"
```

Dieser Befehl ruft die Aufträge im System ab, die einen Get-Process Befehl enthalten.
Der Befehl verwendet den *Command* -Parameter von **Get-Job** , um die abgerufenen Aufträge einzuschränken.
Der Befehl verwendet Platzhalter Zeichen (*), um Aufträge zu erhalten, die in der Befehls Zeichenfolge einen **Get-Process-** Befehl enthalten.

### Beispiel 4: Get-Aufträge, die einen bestimmten Befehl enthalten, mithilfe der Pipeline

```
PS C:\> "*get-process*" | Get-Job
```

Wie der Befehl im vorherigen Beispiel ruft dieser Befehl die Aufträge im System ab, die einen **Get-Process-** Befehl enthalten.
Der Befehl verwendet einen Pipeline Operator (|), um eine Zeichenfolge in Anführungszeichen an das **Get-Job-** Cmdlet zu senden.
Dies entspricht dem vorherigen Befehl.

### Beispiel 5: Aufträge, die noch nicht gestartet wurden

```
PS C:\> Get-Job -State NotStarted
```

Mit diesem Befehl werden nur die Aufträge abgerufen, die erstellt, aber noch nicht gestartet wurden.
Dazu gehören Aufträge, deren Ausführung für einen Zeitpunkt in der Zukunft geplant ist, und solche, die noch nicht geplant wurden.

### Beispiel 6: Aufträge erhalten, denen kein Name zugewiesen wurde

```
PS C:\> Get-Job -Name Job*
```

Dieser Befehl ruft alle Aufträge ab, deren Auftrags Name mit "Job" beginnt.
Da Job \<number\> der Standardname für einen Auftrag ist, ruft dieser Befehl alle Aufträge ab, denen kein explizit zugewiesener Name zugewiesen ist.

### Beispiel 7: Verwenden eines Auftrags Objekts zur Darstellung des Auftrags in einem Befehl

```
The first command uses the **Start-Job** cmdlet to start a background job that runs a **Get-Process** command on the local computer. The command uses the *Name* parameter of **Start-Job** to assign a friendly name to the job.
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob

The second command uses Get-Job to get the job. It uses the *Name* parameter of **Get-Job** to identify the job. The command saves the resulting job object in the $j variable.
PS C:\> $j = Get-Job -Name MyJob

The third command displays the value of the job object in the $j variable. The value of the **State** property shows that the job is completed. The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

The fourth command uses the **Receive-Job** cmdlet to get the results of the job. It uses the job object in the $j variable to represent the job. You can also use a pipeline operator to send a job object to **Receive-Job**.
PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

Dieses Beispiel veranschaulicht, wie Sie mit **Get-Job** ein Auftragsobjekt abrufen. Anschließend wird gezeigt, wie Sie mit dem Auftragsobjekt den Auftrag in einem Befehl darstellen.

### Beispiel 8: alle Aufträge einschließlich der von einer anderen Methode gestarteten Aufträge

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer.
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}

The second command uses the *AsJob* parameter of the **Invoke-Command** cmdlet to start a job on the S1 computer. Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob

The third command uses the **Invoke-Command** cmdlet to run a **Start-Job** command on the S2 computer. By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}

The fourth command uses **Get-Job** to get the jobs stored on the local computer. The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the **Start-Job** cmdlet is a background job and the job started in a remote session by using the **Invoke-Command** cmdlet is a remote job.
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

The fifth command uses **Invoke-Command** to run a **Get-Job** command on the S2 computer.The sample output shows the results of the Get-Job command. On the S2 computer, the job appears to be a local job. The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see about_Remote_Jobs.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

In diesem Beispiel wird veranschaulicht, dass das **Get-Job-** Cmdlet alle Aufträge, die in der aktuellen Sitzung gestartet wurden, auch dann erhalten kann, wenn Sie mit verschiedenen Methoden gestartet wurden.

### Beispiel 9: Untersuchen eines fehlgeschlagenen Auftrags

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer. The job object that **Start-Job** returns shows that the job failed. The value of the **State** property is Failed.
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

The second command uses the **Get-Job** cmdlet to get the job. The command uses the dot method to get the value of the **JobStateInfo** property of the object. It uses a pipeline operator to send the object in the **JobStateInfo** property to the Format-List cmdlet, which formats all of the properties of the object (*) in a list.The result of the **Format-List** command shows that the value of the **Reason** property of the job is blank.
PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

The third command investigates more. It uses a **Get-Job** command to get the job and then uses a pipeline operator to send the whole job object to the **Format-List** cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.
PS C:\> Get-Job | Format-List -Property *
HasMoreData   : False
StatusMessage :
Location      : localhost
Command       : get-process
JobStateInfo  : Failed
Finished      : System.Threading.ManualReset
EventInstanceId    : fb792295-1318-4f5d-8ac8-8a89c5261507
Id            : 1
Name          : Job1
ChildJobs     : {Job2}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :

The fourth command uses **Get-Job** to get the job object that represents the Job2 child job. This is the job in which the command actually ran. It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error. In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see about_Remote_Requirements. For troubleshooting tips, see about_Remote_Troubleshooting.
PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.
```

Dieser Befehl zeigt, wie das von **Get-Job** zurückgegebene Auftrags Objekt verwendet wird, um zu untersuchen, warum ein Auftrag fehlgeschlagen ist.
Weiterhin wird gezeigt, wie die untergeordneten Aufträge der einzelnen Aufträge abgerufen werden.

### Beispiel 10: Filtern von gefilterten Ergebnissen

```
The first command uses the **Workflow** keyword to create the WFProcess workflow.
PS C:\> Workflow WFProcess {Get-Process}

The second command uses the *AsJob* parameter of the WFProcess workflow to run the workflow as a background job. It uses the *JobName* parameter of the workflow to specify a name for the job, and the *PSPrivateMetadata* parameter of the workflow to specify a custom ID.
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}

The third command uses the *Filter* parameter of **Get-Job** to get the job by custom ID that was specified in the *PSPrivateMetadata* parameter.
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

Dieses Beispiel zeigt, wie Sie den *Filter* -Parameter zum Abrufen eines Workflowauftrags verwenden.
Der in Windows PowerShell 3.0 eingeführte *Filter* -Parameter ist nur für benutzerdefinierte Auftragstypen gültig, wie z. B. Workflowaufträge und geplante Aufträge.

### Beispiel 11: erhalten von Informationen zu untergeordneten Aufträgen

```
The first command gets the jobs in the current session. The output includes a background job, a remote job and several instances of a scheduled job. The remote job, Job4, appears to have failed.
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The second command uses the *IncludeChildJob* parameter of **Get-Job**. The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.
PS C:\> Get-Job -IncludeChildJob
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
3      Job3                            Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
6      Job6                            Completed     True            Server02            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The third command uses the *ChildJobState* parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.
PS C:\> Get-Job -Name Job4 -ChildJobState Failed
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.
PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

Dieses Beispiel zeigt die Auswirkungen der Verwendung der Parameter *IncludeChildJob* und *ChildJobState* des **Get-Job** -Cmdlets.

## PARAMETERS

### Nach

Ruft abgeschlossene Aufträge ab, die nach dem angegebenen Datum und der angegebenen Uhrzeit beendet wurden.
Geben Sie ein **DateTime** -Objekt ein, z. b. ein vom Get-Date Cmdlet zurück gegebenes oder eine Zeichenfolge, die in ein **DateTime** -Objekt konvertiert werden kann, z `Dec 1, 2012 2:00 AM` . b `11/06` . oder.

Dieser Parameter kann nur für benutzerdefinierte Auftragstypen wie z. B. Workflowaufträge und geplante Aufträge verwendet werden, die über eine **EndTime** -Eigenschaft verfügen.
Es funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets **Start-Job** .
Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vor

Ruft abgeschlossene Aufträge ab, die vor dem angegebenen Datum und der angegebenen Uhrzeit beendet wurden.
Geben Sie ein **DateTime** -Objekt ein.

Dieser Parameter kann nur für benutzerdefinierte Auftragstypen wie z. B. Workflowaufträge und geplante Aufträge verwendet werden, die über eine **EndTime** -Eigenschaft verfügen.
Es funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets **Start-Job** .
Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Childjobstate

Ruft nur die untergeordneten Aufträge ab, die den angegebenen Status aufweisen.
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

Standardmäßig ruft **Get-Job** keine untergeordneten Aufträge ab.
Wenn Sie den *incluentchildjob* -Parameter verwenden, ruft **Get-Job** alle untergeordneten Aufträge ab.
Bei Verwendung des *ChildJobState* -Parameters hat der *IncludeChildJob* -Parameter keine Auswirkungen.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Command

Gibt ein Array von Befehlen als Zeichen folgen an.
Mit diesem Cmdlet werden die Aufträge abgerufen, die die angegebenen Befehle enthalten.
Standardmäßig werden alle Aufträge fortgesetzt.
Sie können Platzhalter Zeichen verwenden, um ein Befehls Muster anzugeben.

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Filter

Gibt eine Hash Tabelle mit Bedingungen an.
Dieses Cmdlet ruft Aufträge ab, die alle Bedingungen erfüllen.
Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.

Dieser Parameter funktioniert nur mit benutzerdefinierten Auftragstypen, z. B. Workflowaufträgen und geplanten Aufträgen.
Es funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets **Start-Job** .
Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

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

### -Hasmoredata

Gibt an, ob dieses Cmdlet nur Aufträge mit dem angegebenen **hasmoredata** -Eigenschafts Wert abruft.
Die **HasMoreData** -Eigenschaft gibt an, ob alle Auftragsergebnisse in der aktuellen Sitzung empfangen wurden.
Um Aufträge mit weiteren Ergebnissen zu erhalten, geben Sie den Wert $true an.
Um Aufträge zu erhalten, die keine weiteren Ergebnisse aufweisen, geben Sie den Wert $false an.

Verwenden Sie das Cmdlet "Receive-Job", um die Ergebnisse eines Auftrags zu erhalten.

Wenn Sie das **Receive-Job-** Cmdlet verwenden, löscht es die zurückgegebenen Ergebnisse aus dem in-Memory-Sitzungs spezifischen Speicher.
Wenn alle Ergebnisse des Auftrags in der aktuellen Sitzung zurückgegeben wurden, wird der Wert der **hasmoredata** -Eigenschaft des Auftrags auf $false) festgelegt, um anzugeben, dass keine weiteren Ergebnisse für den Auftrag in der aktuellen Sitzung angezeigt werden.
Verwenden Sie den *Keep* -Parameter von **Receive-Job** , um zu verhindern, dass **Receive-Job** Ergebnisse löscht und den Wert der **HasMoreData** -Eigenschaft ändert.
Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help Receive-Job`.

Die **HasMoreData** -Eigenschaft ist für die aktuelle Sitzung spezifisch.
Wenn die Ergebnisse für einen benutzerdefinierten Auftragstyp außerhalb der Sitzung gespeichert werden, wie z. b. der geplante Auftragstyp, der Auftrags Ergebnisse auf dem Datenträger speichert, können Sie das **Receive-Job-** Cmdlet in einer anderen Sitzung verwenden, um die Auftrags Ergebnisse zu erhalten, auch wenn der Wert von **hasmoredata** $false ist.
Weitere Informationen finden Sie in den Hilfethemen für den benutzerdefinierten Auftragstyp.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Gibt ein Array von IDs von Aufträgen an, die von diesem Cmdlet abgerufen werden.

Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.
Es ist einfacher, sich zu merken und als die Instanz-ID einzugeben, aber es ist nur in der aktuellen Sitzung eindeutig.
Sie können eine oder mehrere durch Kommas getrennte IDs eingeben.
Um die ID eines Auftrags zu ermitteln, geben Sie `Get-Job` ohne Parameter ein.

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Incluentchildjob

Gibt an, dass dieses Cmdlet neben den übergeordneten Aufträgen auch untergeordnete Aufträge zurückgibt.

Dieser Parameter ist besonders nützlich für die Untersuchung von Workflow Aufträgen, für die **Get-Job** einen übergeordneten Container Auftrag zurückgibt, sowie für Auftrags Fehler, da der Grund für den Fehler in einer Eigenschaft des untergeordneten Auftrags gespeichert wird.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Gibt ein Array von Instanz-IDs von Aufträgen an, die von diesem Cmdlet abgerufen werden.
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

### -Name

Gibt ein Array von instanzfreundlichen Namen von Aufträgen an, die von diesem Cmdlet abgerufen werden.
Geben Sie einen Auftragsnamen ein, oder verwenden Sie Platzhalterzeichen, um ein Auftragsnamensmuster einzugeben.
Standardmäßig ruft **Get-Job** alle Aufträge in der aktuellen Sitzung ab.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Latest

Gibt eine Anzahl von Aufträgen an, die erhalten werden.
Dieses Cmdlet ruft die Aufträge ab, die zuletzt beendet wurden.

Die letzten Aufträge werden vom *Newest* -Parameter nicht in der Reihenfolge ihrer Endezeit sortiert oder zurückgegeben.
Um die Ausgabe zu sortieren, verwenden Sie das Cmdlet "Sort-Object".

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State

Gibt einen Auftragsstatus an.
Dieses Cmdlet ruft nur Aufträge im angegebenen Zustand ab.
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

Standardmäßig ruft **Get-Job** alle Aufträge in der aktuellen Sitzung ab.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Management. Automation. remotingjob

Dieses Cmdlet gibt Objekte zurück, die die Aufträge in der Sitzung darstellen.

## HINWEISE

* Die **PSJobTypeName** -Eigenschaft von Aufträgen gibt den Auftragstyp des Auftrags an. Der Eigenschaftswert wird vom Autor des Auftragstyps bestimmt. Die folgende Liste enthält allgemeine Auftragstypen.

  - **Backgroundjob** .
Lokaler Auftrag wurde mithilfe von **Start-Job** gestartet.

  - **Remotejob** .
Der Auftrag wurde in einer **PSSession** mithilfe des *AsJob* -Parameters des Invoke-Command-Cmdlets gestartet.

  - **Psworkflowjob** .
Auftrag, der mit dem allgemeinen *AsJob* -Parameter von Workflows gestartet wurde.

## VERWANDTE LINKS

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)

[about_Jobs](About/about_Jobs.md)

[about_Job_Details](About/about_Job_Details.md)

[about_Remote_Jobs](About/about_Remote_Jobs.md)

[about_Scheduled_Jobs](../PSScheduledJob/About/about_Scheduled_Jobs.md)
