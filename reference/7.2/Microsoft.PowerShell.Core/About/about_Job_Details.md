---
description: Enthält Details zu Hintergrund Aufträgen auf lokalen Computern und Remote Computern.
Locale: en-US
ms.date: 10/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_job_details?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Job_Details
ms.openlocfilehash: 1ceb0be9cc140b69afdebaaf336dad75e482aa22
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599646"
---
# <a name="about-job-details"></a>Informationen zu Auftrags Details

## <a name="short-description"></a>Kurze Beschreibung
Enthält Details zu Hintergrund Aufträgen auf lokalen Computern und Remote Computern.

## <a name="detailed-description"></a>Detaillierte Beschreibung

In diesem Thema wird das Konzept eines Hintergrund Auftrags erläutert, und es werden technische Informationen zur Funktionsweise von Hintergrund Aufträgen in PowerShell bereitstellt.

Dieses Thema ist eine Ergänzung zu den Themen [about_Jobs](about_Jobs.md), [about_Thread_Jobs](about_Thread_Jobs.md)und [about_Remote_Jobs](about_Remote_Jobs.md) .

### <a name="about-background-jobs"></a>Informationen zu Hintergrund Aufträgen

Ein Hintergrund Auftrag führt einen Befehl oder einen Ausdruck asynchron aus. Sie kann ein Cmdlet, eine Funktion, ein Skript oder eine beliebige andere Befehls basierte Aufgabe ausführen. Es ist für die Ausführung von Befehlen konzipiert, die einen längeren Zeitraum in Anspruch nehmen, aber Sie können ihn zum Ausführen beliebiger Befehle im Hintergrund verwenden.

Wenn ein synchroner Befehl ausgeführt wird, wird die PowerShell-Eingabeaufforderung unterdrückt, bis der Befehl beendet ist. Ein Hintergrund Auftrag unterdrückt die PowerShell-Eingabeaufforderung jedoch nicht. Ein Befehl zum Starten eines Hintergrund Auftrags gibt ein Auftrags Objekt zurück.
Die Eingabeaufforderung wird sofort zurückgegeben, sodass Sie an anderen Aufgaben arbeiten können, während der Hintergrund Auftrag ausgeführt wird.

Wenn Sie jedoch einen Hintergrund Auftrag starten, werden die Ergebnisse nicht sofort angezeigt, auch wenn der Auftrag sehr schnell ausgeführt wird. Das zurückgegebene Auftrags Objekt enthält nützliche Informationen zum Auftrag, enthält jedoch keine Auftrags Ergebnisse. Sie müssen einen separaten Befehl ausführen, um die Auftrags Ergebnisse zu erhalten. Sie können auch Befehle ausführen, um den Auftrag anzuhalten, auf den Abschluss des Auftrags zu warten und den Auftrag zu löschen.

Um die zeitliche Steuerung eines Hintergrund Auftrags unabhängig von anderen Befehlen vorzunehmen, wird jeder Hintergrund Auftrag in einer eigenen PowerShell-Sitzung ausgeführt. Dabei kann es sich jedoch um eine temporäre Verbindung handeln, die nur zum Ausführen des Auftrags erstellt und dann zerstört wird, oder es kann sich um eine persistente **PSSession** handeln, die Sie verwenden können, um mehrere zugehörige Aufträge oder Befehle auszuführen.

### <a name="using-the-job-cmdlets"></a>Verwenden der Auftrags-Cmdlets

Verwenden `Start-Job` Sie einen Befehl, um einen Hintergrund Auftrag auf einem lokalen Computer zu starten.
`Start-Job` Gibt ein Auftrags Objekt zurück. Sie können auch Objekte, die die Aufträge darstellen, die auf dem lokalen Computer gestartet wurden, mithilfe des- `Get-Job` Cmdlets erhalten.

Um die Auftrags Ergebnisse zu erhalten, verwenden Sie einen- `Receive-Job` Befehl. Wenn der Auftrag nicht vollständig ist, `Receive-Job` gibt partielle Ergebnisse zurück. Sie können auch das `Wait-Job` Cmdlet verwenden, um die Eingabeaufforderung zu unterdrücken, bis ein oder alle Aufträge, die in der Sitzung gestartet wurden, vollständig sind.

Verwenden Sie das-Cmdlet, um einen Hintergrund Auftrag zu unterbinden `Stop-Job` . Verwenden Sie das Cmdlet, um einen Auftrag zu löschen `Remove-Job` .

Weitere Informationen zur Funktionsweise der Cmdlets finden Sie im Hilfethema für jedes Cmdlet und unter [about_Jobs](about_Jobs.md).

### <a name="starting-background-jobs-on-remote-computers"></a>Starten von Hintergrund Aufträgen auf Remote Computern

Hintergrund Aufträge können auf einem lokalen Computer oder einem Remote Computer erstellt und verwaltet werden. Wenn Sie einen Hintergrund Auftrag Remote ausführen möchten, verwenden Sie den **AsJob** -Parameter eines Cmdlets `Invoke-Command` , z. b., oder verwenden `Invoke-Command` Sie das Cmdlet, um einen `Start-Job` Befehl Remote auszuführen. Sie können auch einen Hintergrund Auftrag in einer interaktiven Sitzung starten.

Weitere Informationen zu Remote Hintergrund Aufträgen finden Sie unter [about_Remote_Jobs](about_Remote_Jobs.md).

### <a name="child-jobs"></a>Untergeordnete Aufträge

Jeder Hintergrund Auftrag besteht aus einem übergeordneten Auftrag und einem oder mehreren untergeordneten Aufträgen. Bei Aufträgen `Start-Job` , die mit oder dem **AsJob** -Parameter von gestartet `Invoke-Command` wurden, ist der übergeordnete Auftrag eine Führungskraft. Es werden keine Befehle ausgeführt, oder es werden keine Ergebnisse zurückgegeben. Die Befehle werden tatsächlich von den untergeordneten Aufträgen ausgeführt. Aufträge, die mit anderen Cmdlets gestartet wurden, funktionieren möglicherweise anders.

Die untergeordneten Aufträge werden in der **childjobs** -Eigenschaft des übergeordneten Auftrags Objekts gespeichert. Die **childjobs** -Eigenschaft kann ein oder mehrere untergeordnete Auftrags Objekte enthalten.
Die untergeordneten Auftrags Objekte haben einen **Namen**, eine **ID** und eine **InstanceId** , die sich von dem übergeordneten Auftrag unterscheiden, sodass Sie die übergeordneten und untergeordneten Aufträge einzeln oder als Einheit verwalten können.

Um die übergeordneten und untergeordneten Aufträge eines Auftrags zu erhalten, verwenden Sie den **includechildjobs** -Parameter des `Get-Job` Cmdlets. Der **includechildjob** -Parameter wurde in Windows PowerShell 3,0 eingeführt.

```powershell
PS> Get-Job -IncludeChildJob

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
1  Job1   RemoteJob     Failed     True          localhost   Get-Process
2  Job2                 Completed  True          Server01    Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

Um den übergeordneten Auftrag und nur die untergeordneten Aufträge mit einem bestimmten **Zustands** Wert zu erhalten, verwenden Sie den **childjobstate** -Parameter des `Get-Job` Cmdlets. Der **childjobstate** -Parameter wurde in Windows PowerShell 3,0 eingeführt.

```powershell
PS> Get-Job -ChildJobState Failed

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
1  Job1   RemoteJob     Failed     True          localhost   Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

Um die untergeordneten Aufträge eines Auftrags in allen Versionen von PowerShell zu erhalten, verwenden Sie die **childjob** -Eigenschaft des übergeordneten Auftrags.

```powershell
PS> (Get-Job Job1).ChildJobs

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
2  Job2                 Completed  True          Server01    Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

Sie können auch einen `Get-Job` Befehl für den untergeordneten Auftrag verwenden, wie im folgenden Befehl gezeigt:

```powershell
PS> Get-Job Job3

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
3  Job3                 Failed     False         localhost   Get-Process
```

Die Konfiguration des untergeordneten Auftrags hängt von dem Befehl ab, mit dem der Auftrag gestartet wird.

- Wenn Sie verwenden, `Start-Job` um einen Auftrag auf einem lokalen Computer zu starten, besteht der Auftrag aus einem übergeordneten auftragsauftrag und einem untergeordneten Auftrag, der den Befehl ausführt.

- Wenn Sie den **AsJob** -Parameter von verwenden, `Invoke-Command` um einen Auftrag auf einem oder mehreren Computern zu starten, besteht der Auftrag aus einem übergeordneten auftragsauftrag und einem untergeordneten Auftrag für jeden Auftrag, der auf jedem Computer ausgeführt wird.

- Wenn Sie `Invoke-Command` zum Ausführen eines `Start-Job` Befehls auf einem oder mehreren Remote Computern verwenden, ist das Ergebnis das gleiche wie ein lokaler Befehl, der auf jedem Remote Computer ausgeführt wird. Der Befehl gibt für jeden Computer ein Auftrags Objekt zurück. Das Auftrags Objekt besteht aus einem übergeordneten auftragsauftrag und einem untergeordneten Auftrag, der den Befehl ausführt.

Der übergeordnete Auftrag stellt alle untergeordneten Aufträge dar. Wenn Sie einen übergeordneten Auftrag verwalten, verwalten Sie auch die zugehörigen untergeordneten Aufträge. Wenn Sie z. b. einen übergeordneten Auftrag beenden, werden alle untergeordneten Aufträge angehalten. Wenn Sie die Ergebnisse eines übergeordneten Auftrags erhalten, erhalten Sie die Ergebnisse aller untergeordneten Aufträge.

Sie können jedoch auch untergeordnete Aufträge einzeln verwalten. Dies ist besonders hilfreich, wenn Sie ein Problem mit einem Auftrag untersuchen oder nur die Ergebnisse einer Reihe von untergeordneten Aufträgen erhalten möchten, die mit dem **AsJob** -Parameter von gestartet wurden `Invoke-Command` .

Der folgende Befehl verwendet den **AsJob** -Parameter von `Invoke-Command` , um Hintergrund Aufträge auf dem lokalen Computer und auf zwei Remote Computern zu starten. Der Befehl speichert den Auftrag in der `$j` Variablen.

```powershell
PS> $j = Invoke-Command -ComputerName localhost, Server01, Server02 `
-Command {Get-Date} -AsJob
```

Wenn Sie die Eigenschaften "Name" und " **childjob** " des Auftrags in anzeigen `$j` , wird angezeigt, dass der Befehl ein Auftrags Objekt mit drei untergeordneten Aufträgen zurückgegeben hat, eines für jeden Computer.

```powershell
PS> $j | Format-List Name, ChildJobs

Name      : Job3
ChildJobs : {Job4, Job5, Job6}
```

Wenn Sie den übergeordneten Auftrag anzeigen, wird angezeigt, dass der Auftrag fehlgeschlagen ist.

```powershell
PS> $j

Id Name   PSJobTypeName State      HasMoreData   Location
-- ----   ------------- -----      -----------   --------
3  Job3   RemotingJob   Failed     False         localhost,Server...
```

Wenn Sie jedoch einen Befehl ausführen, `Get-Job` der die untergeordneten Aufträge abruft, zeigt die Ausgabe an, dass nur ein untergeordneter Auftrag fehlgeschlagen ist.

```powershell
PS> Get-Job -IncludeChildJobs

Id  Name   PSJobTypeName State      HasMoreData   Location    Command
--  ----   ------------- -----      -----------   --------    -------
3   Job3   RemotingJob   Failed     False         localhost,Server...
4   Job4                 Completed  True          localhost   Get-Date
5   Job5                 Failed     False         Server01    Get-Date
6   Job6                 Completed  True          Server02    Get-Date
```

Um die Ergebnisse aller untergeordneten Aufträge zu erhalten, verwenden Sie das `Receive-Job` Cmdlet, um die Ergebnisse des übergeordneten Auftrags zu erhalten. Sie können jedoch auch die Ergebnisse eines bestimmten untergeordneten Auftrags erhalten, wie im folgenden Befehl gezeigt.

```powershell
PS> Receive-Job -Name Job6 -Keep | Format-Table ComputerName,
>> DateTime -AutoSize
ComputerName DateTime
------------ --------
Server02     Thursday, March 13, 2008 4:16:03 PM
```

Mit dem Feature für untergeordnete Aufträge von PowerShell-Hintergrund Aufträgen können Sie besser steuern, welche Aufträge Sie ausführen.

### <a name="job-types"></a>Auftragstypen

PowerShell unterstützt verschiedene Arten von Aufträgen für verschiedene Tasks. Ab Windows PowerShell 3,0 können Entwickler "Auftrags Quell Adapter" schreiben, mit denen PowerShell neue Auftrags Typen hinzugefügt und die Auftrags Quell Adapter in Module eingeschlossen werden.
Wenn Sie das Modul importieren, können Sie den neuen Auftragstyp in Ihrer Sitzung verwenden.

Das psscheduledjob-Modul fügt z. b. geplante Aufträge hinzu, und das psworkflow-Modul fügt Workflow Aufträge hinzu.

Benutzerdefinierte Auftrags Typen können sich stark von PowerShell-Standard Hintergrund Aufträgen unterscheiden. Beispielsweise werden geplante Aufträge auf dem Datenträger gespeichert. Sie sind nicht nur in einer bestimmten Sitzung vorhanden. Workflow Aufträge können angehalten und fortgesetzt werden.

Die Cmdlets, mit denen Sie benutzerdefinierte Aufträge verwalten, hängen vom Auftragstyp ab. Bei manchen verwenden Sie die standardmäßigen Job-Cmdlets, z `Get-Job` `Start-Job` . b. und. Andere verfügen über spezialisierte Cmdlets, die nur eine bestimmte Art von Auftrag verwalten. Ausführliche Informationen zu benutzerdefinierten Auftrags Typen finden Sie in den Hilfe Themen zum Auftragstyp.

Verwenden Sie das-Cmdlet, um den Auftragstyp eines Auftrags zu ermitteln `Get-Job` . `Get-Job` gibt für verschiedene Auftrags Typen unterschiedliche Auftrags Objekte zurück. Der Wert der **psjobtypame** -Eigenschaft der Auftrags Objekte, die `Get-Job` zurückgibt, gibt den Auftragstyp an.

In der folgenden Tabelle sind die Auftrags Typen aufgeführt, die in PowerShell enthalten sind.

|    Auftragstyp    |                       BESCHREIBUNG                        |
| -------------- | -------------------------------------------------------- |
| Backgroundjob  | Die Verwendung des `Start-Job` Cmdlets wurde gestartet.                    |
| Remotejob      | Gestartet mit dem **AsJob** -Parameter des             |
|                | `Invoke-Command` cmdlet.                                 |
| PSWorkflowJob  | Gestartet mit dem **AsJob** -Parameter eines Workflows.     |
| PSScheduledJob | Eine Instanz eines geplanten Auftrags, der von einem Auftrags--Vorgang gestartet wurde. |
| Cimjob         | Gestartet mit dem **AsJob** -Parameter eines Cmdlets aus einem |
|                | Cdxml-Modul.                                            |
| Wmijob         | Gestartet mit dem **AsJob** -Parameter eines Cmdlets aus einem |
|                | WMI-Modul.                                              |
| PSEventJob     | Erstellt mit `Register-ObjectEvent` und Angeben eines    |
|                | Aktion mit dem **Action** -Parameter.                    |

Hinweis: bevor Sie mit dem `Get-Job` Cmdlet Aufträge eines bestimmten Typs erhalten, überprüfen Sie, ob das Modul, das den Auftragstyp hinzufügt, in die aktuelle Sitzung importiert wird.
Andernfalls `Get-Job` werden von keine Aufträge dieses Typs erhalten.

## <a name="examples"></a>Beispiele

Die folgenden Befehle erstellen einen lokalen Hintergrund Auftrag, einen Remote Hintergrund Auftrag, einen Workflow Auftrag und einen geplanten Auftrag. Dann wird das `Get-Job` Cmdlet verwendet, um die Aufträge zu erhalten. `Get-Job` der geplante Auftrag wird nicht abgerufen, aber es werden alle gestarteten Instanzen des geplanten Auftrags abgerufen.

Startet einen Hintergrund Auftrag auf dem lokalen Computer.

```powershell
PS> Start-Job -Name LocalData {Get-Process}

Id Name        PSJobTypeName   State   HasMoreData   Location   Command
-- ----        -------------   -----   -----------   --------   -------
2  LocalData   BackgroundJob   Running        True   localhost  Get-Process
```

Startet einen Hintergrund Auftrag, der auf einem Remote Computer ausgeführt wird.

```powershell
PS> Invoke-Command -ComputerName Server01 {Get-Process} `
-AsJob -JobName RemoteData

Id  Name        PSJobTypeName  State   HasMoreData   Location   Command
--  ----        -------------  -----   -----------   --------   -------
2   RemoteData  RemoteJob      Running        True   Server01   Get-Process
```

Geplanten Auftrag erstellen

```powershell
PS>  Register-ScheduledJob -Name ScheduledJob -ScriptBlock `
 {Get-Process} -Trigger (New-JobTrigger -Once -At "3 PM")

Id         Name            JobTriggers     Command       Enabled
--         ----            -----------     -------       -------
1          ScheduledJob    1               Get-Process   True
```

Erstellen Sie einen Workflow.

```powershell
PS> workflow Test-Workflow {Get-Process}
```

Führen Sie den Workflow als Auftrag aus.

```powershell

PS> Test-Workflow -AsJob -JobName TestWFJob

Id  Name       PSJobTypeName   State   HasMoreData   Location   Command
--  ----       -------------   -----   -----------   --------   -------
2   TestWFJob  PSWorkflowJob   NotStarted     True   localhost  Get-Process
```

Sie erhalten die Aufträge. `Get-Job`Mit dem Befehl werden keine geplanten Aufträge abgerufen, sondern es werden Instanzen des geplanten Auftrags abgerufen, die gestartet werden.

```powershell
PS> Get-Job

Id  Name         PSJobTypeName  State     HasMoreData  Location  Command
--  ----         -------------  -----     -----------  --------  -------
2   LocalData    BackgroundJob  Completed True         localhost Get-Process
4   RemoteData   RemoteJob      Completed True         Server01  Get-Process
6   TestWFJob    PSWorkflowJob  Completed True         localhost WorkflowJob
8   ScheduledJob PSScheduledJob Completed True         localhost Get-Process
```

Verwenden Sie das-Cmdlet, um geplante Aufträge zu erhalten `Get-ScheduledJob` .

```powershell
PS> Get-ScheduledJob

Id         Name            JobTriggers     Command       Enabled
--         ----            -----------     -------       -------
1          ScheduledJob    1               Get-Process   True
```

## <a name="see-also"></a>Weitere Informationen

- [about_Jobs](about_Jobs.md)
- [about_Remote_Jobs](about_Remote_Jobs.md)
- [about_Thread_Jobs](about_Thread_Jobs.md)
- [about_Remote](about_Remote.md)
- [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [Start-Job](xref:Microsoft.PowerShell.Core.Start-Job)
- [Get-Job](xref:Microsoft.PowerShell.Core.Get-Job)
- [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job)
- [Stop-Job](xref:Microsoft.PowerShell.Core.Stop-Job)
- [Remove-Job](xref:Microsoft.PowerShell.Core.Remove-Job)
- [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)
- [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)
- [Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession)
