---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 167f56964bbdb675c2dd85e2803fdee2d308ee4f
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389571"
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

### Commandparameterset

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### Filterparameterset

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-Job` Cmdlet ruft Objekte ab, die die Hintergrund Aufträge darstellen, die in der aktuellen Sitzung gestartet wurden. Sie können verwenden, `Get-Job` um Aufträge zu erhalten, die mithilfe des `Start-Job` Cmdlets gestartet wurden, oder indem Sie den **AsJob** -Parameter eines beliebigen Cmdlets verwenden.

Ohne Parameter ruft ein `Get-Job` Befehl alle Aufträge in der aktuellen Sitzung ab. Sie können die Parameter von verwenden `Get-Job` , um bestimmte Aufträge zu erhalten.

Das zurückgegebene Auftrags Objekt `Get-Job` enthält nützliche Informationen zum Auftrag, aber keine Auftrags Ergebnisse. Verwenden Sie das-Cmdlet, um die Ergebnisse zu erhalten `Receive-Job` .

Ein Windows PowerShell-Hintergrund Auftrag ist ein Befehl, der im Hintergrund ausgeführt wird, ohne mit der aktuellen Sitzung zu interagieren. In der Regel verwenden Sie einen Hintergrund Auftrag, um einen komplexen Befehl auszuführen, der lange Zeit in Anspruch nimmt. Weitere Informationen zu Hintergrundaufträgen in Windows PowerShell finden Sie unter [about_Jobs](./about/about_Jobs.md).

Ab Windows PowerShell 3,0 `Get-Job` Ruft das Cmdlet auch benutzerdefinierte Auftrags Typen ab, wie z. b. Workflow Aufträge und Instanzen von geplanten Aufträgen. Zum Ermitteln des Auftragstyps eines Auftrags verwenden Sie die **PSJobTypeName** -Eigenschaft des Auftrags.

`Get-Job`Wenn Sie aktivieren möchten, um einen benutzerdefinierten Auftragstyp zu erhalten, importieren Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, in die Sitzung, bevor Sie einen `Get-Job` Befehl ausführen, entweder mithilfe des- `Import-Module` Cmdlets oder mithilfe des-Cmdlets oder mithilfe des-Cmdlets. Informationen zu einem bestimmten benutzerdefinierten Auftragstyp finden Sie in der Dokumentation der Funktion „Benutzerdefinierte Auftragstypen“.

## BEISPIELE

### Beispiel 1: alle Hintergrund Aufträge, die in der aktuellen Sitzung gestartet wurden

Dieser Befehl ruft alle Hintergrundaufträge ab, die in der aktuellen Sitzung gestartet wurden. In anderen Sitzungen erstellte Aufträge sind nicht enthalten, auch wenn die Aufträge auf dem lokalen Computer ausgeführt werden.

```
PS C:\> Get-Job
```

### Beispiel 2: Beenden eines Auftrags mit einer Instanz-ID

Diese Befehle zeigen, wie die Instanz-ID eines Auftrags abgerufen und dann zum Beenden eines Auftrags verwendet wird. Im Gegensatz zum Namen eines Auftrags, der nicht eindeutig ist, ist die Instanz-ID eindeutig.

Der erste Befehl verwendet das `Get-Job` Cmdlet, um einen Auftrag zu erhalten. Er verwendet den **Name** -Parameter, um den Auftrag zu identifizieren. Der Befehl speichert das Auftrags Objekt, das `Get-Job` in der `$j` Variablen zurückgibt. In diesem Beispiel ist nur ein Auftrag mit dem angegebenen Namen vorhanden. Mit dem zweiten Befehl wird die **InstanceId-** Eigenschaft des Objekts in der `$j` Variablen abgerufen und in der `$ID` Variablen gespeichert. Der dritte Befehl zeigt den Wert der `$ID` Variablen an. Der vierte Befehl verwendet das `Stop-Job` Cmdlet, um den Auftrag zu unterbinden.
Er verwendet den **InstanceId-** Parameter, um den Auftrag und die `$ID` Variable zu identifizieren, um die Instanz-ID des Auftrags darzustellen.

```
PS C:\> $j = Get-Job -Name Job1
PS C:\> $ID = $j.InstanceID
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

PS C:\> Stop-Job -InstanceId $ID
```

### Beispiel 3: Get-Aufträge, die einen bestimmten Befehl enthalten

Dieser Befehl ruft die Aufträge im System ab, die einen `Get-Process` Befehl enthalten. Der Befehl verwendet den **Command** -Parameter von `Get-Job` , um die abgerufenen Aufträge einzuschränken. Der Befehl verwendet Platzhalter Zeichen ( `*` ) zum Aufrufen von Aufträgen, die einen `Get-Process` Befehl an beliebiger Stelle in der Befehls Zeichenfolge enthalten.

```
PS C:\> Get-Job -Command "*get-process*"
```

### Beispiel 4: Get-Aufträge, die einen bestimmten Befehl enthalten, mithilfe der Pipeline

Wie der Befehl im vorherigen Beispiel ruft dieser Befehl die Aufträge im System ab, die einen Befehl enthalten `Get-Process` . Der Befehl verwendet einen Pipeline Operator ( `|` ), um eine Zeichenfolge in Anführungszeichen an das `Get-Job` Cmdlet zu senden. Dies entspricht dem vorherigen Befehl.

```
PS C:\> "*get-process*" | Get-Job
```

### Beispiel 5: Aufträge, die noch nicht gestartet wurden

Mit diesem Befehl werden nur die Aufträge abgerufen, die erstellt, aber noch nicht gestartet wurden. Dazu gehören Aufträge, deren Ausführung für einen Zeitpunkt in der Zukunft geplant ist, und solche, die noch nicht geplant wurden.

```
PS C:\> Get-Job -State NotStarted
```

### Beispiel 6: Aufträge erhalten, denen kein Name zugewiesen wurde

Dieser Befehl ruft alle Aufträge ab, deren Auftrags Name mit "Job" beginnt. Da `job<number>` der Standardname für einen Auftrag ist, ruft dieser Befehl alle Aufträge ab, denen kein explizit zugewiesener Name zugewiesen ist.

```
PS C:\> Get-Job -Name Job*
```

### Beispiel 7: Verwenden eines Auftrags Objekts zur Darstellung des Auftrags in einem Befehl

In diesem Beispiel wird gezeigt, wie verwendet `Get-Job` wird, um ein Auftrags Objekt zu erhalten, und anschließend wird gezeigt, wie das Auftrags Objekt verwendet wird, um den Auftrag in einem Befehl darzustellen.

Der erste Befehl verwendet das `Start-Job` Cmdlet, um einen Hintergrund Auftrag zu starten, der einen `Get-Process` Befehl auf dem lokalen Computer ausführt. Der Befehl verwendet den **Name** -Parameter von `Start-Job` , um dem Auftrag einen anzeigen Amen zuzuweisen. Der zweite Befehl verwendet `Get-Job` , um den Auftrag zu erhalten. Er verwendet den **Name** -Parameter von `Get-Job` , um den Auftrag zu identifizieren. Der Befehl speichert das resultierende Auftrags Objekt in der `$j` Variablen. Der dritte Befehl zeigt den Wert des Auftrags Objekts in der `$j` Variablen an. Der Wert der **State** -Eigenschaft zeigt an, dass der Auftrag abgeschlossen ist. Der Wert der **HasMoreData** -Eigenschaft zeigt, dass Ergebnisse des Auftrags verfügbar sind, die noch nicht abgerufen wurden. Der vierte Befehl verwendet das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags zu erhalten. Er verwendet das Auftrags Objekt in der `$j` Variablen, um den Auftrag darzustellen. Sie können auch einen Pipeline Operator verwenden, um ein Auftrags Objekt an zu senden `Receive-Job` .

```
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob
PS C:\> $j = Get-Job -Name MyJob
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```


### Beispiel 8: alle Aufträge einschließlich der von einer anderen Methode gestarteten Aufträge

In diesem Beispiel wird veranschaulicht, dass mit dem `Get-Job` Cmdlet alle Aufträge, die in der aktuellen Sitzung gestartet wurden, angezeigt werden können. Dies ist auch dann der Fall, wenn Sie mithilfe verschiedener Methoden gestartet wurden.

Der erste Befehl verwendet das `Start-Job` Cmdlet, um einen Auftrag auf dem lokalen Computer zu starten. Der zweite Befehl verwendet den **AsJob** -Parameter des `Invoke-Command` Cmdlets, um einen Auftrag auf dem S1-Computer zu starten. Obwohl die Befehle im Auftrag auf dem Remotecomputer ausgeführt werden, wird das Auftragsobjekt auf dem lokalen Computer erstellt; daher verwenden Sie lokale Befehle zum Verwalten des Auftrags. Der dritte Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines `Start-Job` Befehls auf dem Computer S2. Wenn diese Methode verwendet wird, wird das Auftrags Objekt auf dem Remote Computer erstellt, sodass Sie Remote Befehle verwenden, um den Auftrag zu verwalten. Der vierte Befehl verwendet `Get-Job` , um die auf dem lokalen Computer gespeicherten Aufträge zu erhalten. Die **psjobtypame** -Eigenschaft von Aufträgen, die in Windows PowerShell 3,0 eingeführt wurde, zeigt, dass der lokale Auftrag, der mithilfe des `Start-Job` Cmdlets gestartet wurde, ein Hintergrund Auftrag ist und der Auftrag, der in einer Remote Sitzung mithilfe des `Invoke-Command` Cmdlets gestartet wurde, ein Remote Auftrag ist. Der fünfte Befehl verwendet `Invoke-Command` , um `Get-Job` auf dem Computer S2 einen Befehl auszuführen. Die Beispielausgabe zeigt die Ergebnisse des `Get-Job` Befehls an. Auf dem Computer S2 scheint der Auftrag ein lokaler Auftrag zu sein. Der Computername ist "localhost", und der Auftragstyp ist ein Hintergrund Auftrag. Weitere Informationen zum Ausführen von Hintergrund Aufträgen auf Remote Computern finden Sie unter [about_Remote_Jobs](./about/about_Remote_Jobs.md).

```
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

### Beispiel 9: Untersuchen eines fehlgeschlagenen Auftrags

Dieser Befehl zeigt, wie das zurückgegebene Auftrags Objekt verwendet wird `Get-Job` , um zu untersuchen, warum ein Auftrag fehlgeschlagen ist.
Weiterhin wird gezeigt, wie die untergeordneten Aufträge der einzelnen Aufträge abgerufen werden.

Der erste Befehl verwendet das `Start-Job` Cmdlet, um einen Auftrag auf dem lokalen Computer zu starten. Das zurückgegebene Auftrags Objekt `Start-Job` zeigt, dass der Auftrag fehlgeschlagen ist. Der Wert der **State** -Eigenschaft ist fehlerhaft.

Der zweite Befehl verwendet das `Get-Job` Cmdlet, um den Auftrag zu erhalten. Der Befehl verwendet die Punktmethode, um den Wert der **JobStateInfo** -Eigenschaft des Objekts abzurufen. Er verwendet einen Pipeline-Operator, um das Objekt in der **jobstatueinfo** -Eigenschaft an das `Format-List` Cmdlet zu senden, das alle Eigenschaften des Objekts ( `*` ) in einer Liste formatiert. Das Ergebnis des- `Format-List` Befehls zeigt, dass der Wert der **reason** -Eigenschaft des Auftrags leer ist.

Mit dem dritten Befehl werden weitere Informationen untersucht. Er verwendet einen `Get-Job` Befehl, um den Auftrag zu erhalten, und verwendet dann einen Pipeline Operator, um das gesamte Auftrags Objekt an das `Format-List` Cmdlet zu senden, das alle Eigenschaften des Auftrags in einer Liste anzeigt. Die Anzeige aller Eigenschaften im Auftrags Objekt zeigt, dass der Auftrag einen untergeordneten Auftrag mit dem Namen Job2 enthält.

Der vierte Befehl verwendet `Get-Job` , um das Auftrags Objekt, das den untergeordneten Job2-Auftrag darstellt, zu erhalten. Dies ist der Auftrag, in dem der Befehl tatsächlich ausgeführt wurde. Er verwendet die Punkt-Methode, um die **reason** -Eigenschaft der **Jobstatus Info** -Eigenschaft zu erhalten. Das Ergebnis zeigt, dass der Auftrag aufgrund eines Zugriffs Verweigerungs Fehlers fehlgeschlagen ist. In diesem Fall hat der Benutzer vergessen, beim Starten von Windows PowerShell die Option als Administrator ausführen zu verwenden. da Hintergrund Aufträge die Remotingfeatures von Windows PowerShell verwenden, muss der Computer für Remoting konfiguriert werden, um einen Auftrag auszuführen, auch wenn der Auftrag auf dem lokalen Computer ausgeführt wird. Informationen zu den Anforderungen für Remoting in Windows PowerShell finden Sie unter [about_Remote_Requirements](./about/about_Remote_Requirements.md). Tipps zur Problembehandlung finden Sie unter [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md).

```
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

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

PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the
following error message: Access is denied.
```

### Beispiel 10: Filtern von gefilterten Ergebnissen

Dieses Beispiel zeigt, wie Sie den **Filter** -Parameter zum Abrufen eines Workflowauftrags verwenden. Der in Windows PowerShell 3.0 eingeführte **Filter** -Parameter ist nur für benutzerdefinierte Auftragstypen gültig, wie z. B. Workflowaufträge und geplante Aufträge.

Der erste Befehl verwendet das **Workflow** Schlüsselwort, um den WfProcess-Workflow zu erstellen. Der zweite Befehl verwendet den **AsJob** -Parameter des WfProcess-Workflows, um den Workflow als Hintergrund Auftrag auszuführen. Mithilfe des **JobName** -Parameters des Workflows wird ein Name für den Auftrag angegeben und mithilfe des **PSPrivateMetadata** -Parameters des Workflows eine benutzerdefinierte ID. Der dritte Befehl verwendet den **Filter** -Parameter von `Get-Job` , um den Auftrag anhand der benutzerdefinierten ID zu erhalten, die im **psprivatemetadata** -Parameter angegeben wurde.

```
PS C:\> Workflow WFProcess {Get-Process}
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

### Beispiel 11: erhalten von Informationen zu untergeordneten Aufträgen

Dieses Beispiel zeigt die Auswirkung der Verwendung der Parameter **includechildjob** und **childjobstate** des `Get-Job` Cmdlets.

Der erste Befehl ruft die Aufträge in der aktuellen Sitzung ab. Die Ausgabe umfasst einen Hintergrundauftrag, einen Remoteauftrag und mehrere Instanzen eines geplanten Auftrags. Bei der Ausführung des Remoteauftrags (Job4) scheint ein Fehler aufgetreten zu sein.
Der zweite Befehl verwendet den **incluentchildjob** -Parameter von `Get-Job` . In der Ausgabe werden die untergeordneten Aufträge aller Aufträge hinzugefügt, die über untergeordnete Aufträge verfügen. In diesem Fall zeigt die überarbeitete Ausgabe an, dass nur der untergeordnete Job5-Auftrag von Job4 fehlgeschlagen ist. Der dritte Befehl verwendet den **childjobstate** -Parameter mit dem Wert failed. die Ausgabe enthält alle übergeordneten Aufträge und nur die untergeordneten Aufträge, die fehlgeschlagen sind. Der fünfte Befehl verwendet die **jobstateinfo** -Eigenschaft von Aufträgen und seine **reason** -Eigenschaft, um zu ermitteln, warum Job5 fehlgeschlagen ist.

```
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

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

PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
```

Weitere Informationen finden Sie im [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) Hilfethema.

## PARAMETERS

### Nach

Ruft abgeschlossene Aufträge ab, die nach dem angegebenen Datum und der angegebenen Uhrzeit beendet wurden. Geben Sie ein **DateTime** -Objekt ein, z. b. ein vom `Get-Date` Cmdlet zurück gegebenes oder eine Zeichenfolge, die in ein **DateTime** -Objekt konvertiert werden kann, z `Dec 1, 2012 2:00 AM` . b `11/06` . oder.

Dieser Parameter kann nur für benutzerdefinierte Auftragstypen wie z. B. Workflowaufträge und geplante Aufträge verwendet werden, die über eine **EndTime** -Eigenschaft verfügen. Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des `Start-Job` Cmdlets. Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vor

Ruft abgeschlossene Aufträge ab, die vor dem angegebenen Datum und der angegebenen Uhrzeit beendet wurden. Geben Sie ein **DateTime** -Objekt ein.

Dieser Parameter kann nur für benutzerdefinierte Auftragstypen wie z. B. Workflowaufträge und geplante Aufträge verwendet werden, die über eine **EndTime** -Eigenschaft verfügen. Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des `Start-Job` Cmdlets. Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Childjobstate

Ruft nur die untergeordneten Aufträge ab, die den angegebenen Status aufweisen. Zulässige Werte für diesen Parameter:

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

Standardmäßig werden von keine untergeordneten `Get-Job` Aufträge erhalten. Wenn Sie den **incluentchildjob** -Parameter verwenden, werden alle untergeordneten `Get-Job` Aufträge abgerufen. Bei Verwendung des **ChildJobState** -Parameters hat der **IncludeChildJob** -Parameter keine Auswirkungen.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Command

Gibt ein Array von Befehlen als Zeichen folgen an. Mit diesem Cmdlet werden die Aufträge abgerufen, die die angegebenen Befehle enthalten. Standardmäßig werden alle Aufträge fortgesetzt. Sie können Platzhalter Zeichen verwenden, um ein Befehls Muster anzugeben.

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

Gibt eine Hash Tabelle mit Bedingungen an. Dieses Cmdlet ruft Aufträge ab, die alle Bedingungen erfüllen.
Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.

Dieser Parameter funktioniert nur mit benutzerdefinierten Auftragstypen, z. B. Workflowaufträgen und geplanten Aufträgen. Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des `Start-Job` Cmdlets. Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.

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
Die **HasMoreData** -Eigenschaft gibt an, ob alle Auftragsergebnisse in der aktuellen Sitzung empfangen wurden. Um Aufträge mit weiteren Ergebnissen zu erhalten, geben Sie den Wert an `$True` . Um Aufträge zu erhalten, die keine weiteren Ergebnisse aufweisen, geben Sie den Wert an `$False` .

Verwenden Sie das-Cmdlet, um die Ergebnisse eines Auftrags zu erhalten `Receive-Job` .

Wenn Sie das `Receive-Job` Cmdlet verwenden, wird es aus dem in-Memory-Sitzungs spezifischen Speicher für die zurückgegebenen Ergebnisse gelöscht. Wenn alle Ergebnisse des Auftrags in der aktuellen Sitzung zurückgegeben wurden, wird der Wert der **hasmoredata** -Eigenschaft des Auftrags auf festgelegt, `$False` um anzugeben, dass keine weiteren Ergebnisse für den Auftrag in der aktuellen Sitzung angezeigt werden. Verwenden Sie den **Keep** -Parameter von `Receive-Job` , um zu verhindern, dass `Receive-Job` Ergebnisse gelöscht und der Wert der **hasmoredata** -Eigenschaft geändert werden.
Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help Receive-Job`.

Die **HasMoreData** -Eigenschaft ist für die aktuelle Sitzung spezifisch. Wenn die Ergebnisse für einen benutzerdefinierten Auftragstyp außerhalb der Sitzung gespeichert werden, wie z. b. der geplante Auftragstyp, der Auftrags Ergebnisse auf dem Datenträger speichert, können Sie das `Receive-Job` Cmdlet in einer anderen Sitzung verwenden, um die Auftrags Ergebnisse erneut zu erhalten, auch wenn der Wert von **hasmoredata** ist `$False` . Weitere Informationen finden Sie in den Hilfethemen für den benutzerdefinierten Auftragstyp.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Gibt ein Array von IDs von Aufträgen an, die von diesem Cmdlet abgerufen werden.

Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert. Es ist einfacher, sich zu merken und als die Instanz-ID einzugeben, aber es ist nur in der aktuellen Sitzung eindeutig. Sie können eine oder mehrere durch Kommas getrennte IDs eingeben. Um die ID eines Auftrags zu ermitteln, geben Sie `Get-Job` ohne Parameter ein.

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

Dieser Parameter ist besonders nützlich für die Untersuchung von Workflow Aufträgen, für die `Get-Job` einen übergeordneten Container Auftrag und Auftrags Fehler zurückgibt, da die Ursache für den Fehler in einer Eigenschaft des untergeordneten Auftrags gespeichert wird.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Gibt ein Array von Instanz-IDs von Aufträgen an, die von diesem Cmdlet abgerufen werden. Standardmäßig werden alle Aufträge fortgesetzt.

Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert. Um die Instanz-ID eines Auftrags zu ermitteln, verwenden Sie `Get-Job` .

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

Gibt ein Array von instanzfreundlichen Namen von Aufträgen an, die von diesem Cmdlet abgerufen werden. Geben Sie einen Auftragsnamen ein, oder verwenden Sie Platzhalterzeichen, um ein Auftragsnamensmuster einzugeben. Standardmäßig ruft `Get-Job` alle Aufträge in der aktuellen Sitzung ab.

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

Gibt eine Anzahl von Aufträgen an, die erhalten werden. Dieses Cmdlet ruft die Aufträge ab, die zuletzt beendet wurden.

Die letzten Aufträge werden vom **Newest** -Parameter nicht in der Reihenfolge ihrer Endezeit sortiert oder zurückgegeben. Verwenden Sie das-Cmdlet, um die Ausgabe zu sortieren `Sort-Object` .

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State

Gibt einen Auftragsstatus an. Dieses Cmdlet ruft nur Aufträge im angegebenen Zustand ab. Zulässige Werte für diesen Parameter:

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

Standardmäßig ruft `Get-Job` alle Aufträge in der aktuellen Sitzung ab.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Management. Automation. remotingjob

Dieses Cmdlet gibt Objekte zurück, die die Aufträge in der Sitzung darstellen.

## HINWEISE

Die **PSJobTypeName** -Eigenschaft von Aufträgen gibt den Auftragstyp des Auftrags an. Der Eigenschaftswert wird vom Autor des Auftragstyps bestimmt. Die folgende Liste enthält allgemeine Auftragstypen.

- **Backgroundjob**. Lokaler Auftrag, der mit gestartet wurde `Start-Job` .
- **Remotejob**. Der Auftrag wurde in einer **PSSession** mithilfe des **AsJob** -Parameters des `Invoke-Command` Cmdlets gestartet.
- **Psworkflowjob**. Auftrag, der mit dem allgemeinen **AsJob** -Parameter von Workflows gestartet wurde.

## VERWANDTE LINKS

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Wait-Job](Wait-Job.md)

[about_Jobs](About/about_Jobs.md)

[about_Job_Details](About/about_Job_Details.md)

[about_Remote_Jobs](About/about_Remote_Jobs.md)
