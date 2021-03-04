---
description: Erläutert, wie Probleme mit geplanten Aufträgen gelöst werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_troubleshooting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Troubleshooting
ms.openlocfilehash: aac2133cee4abdd7e50e7b433104b9578d74b0a8
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685863"
---
# <a name="about-scheduled-jobs-troubleshooting"></a>Informationen zur Problembehandlung bei geplanten Aufträgen

## <a name="short-description"></a>Kurze Beschreibung

Erläutert, wie Probleme mit geplanten Aufträgen gelöst werden.

## <a name="long-description"></a>Lange Beschreibung

In diesem Dokument werden einige der Probleme beschrieben, die bei der Verwendung der Features für geplante Aufträge von PowerShell auftreten können. es werden Lösungen für diese Probleme vorgeschlagen.

Vor der Verwendung geplanter PowerShell-Aufträge finden Sie weitere Informationen unter [about_Scheduled_Jobs](about_Scheduled_Jobs.md) und den zugehörigen geplanten Aufträgen zu Themen.

Weitere Informationen zu den im **psscheduledjob** -Modul enthaltenen Cmdlets finden Sie unter [psscheduledjob](xref:PSScheduledJob).

## <a name="cant-find-job-results"></a>Auftrags Ergebnisse können nicht gefunden werden.

### <a name="basic-method-for-getting-job-results-in-powershell"></a>Grundlegende Methode zum erhalten von Auftrags Ergebnissen in PowerShell

Wenn ein geplanter Auftrag ausgeführt wird, erstellt er eine Instanz des geplanten Auftrags. Verwenden Sie die Job-Cmdlets, um die Ergebnisse geplanter Auftrags Instanzen anzuzeigen, zu verwalten und zu erhalten.

> [!NOTE]
> Damit die Job-Cmdlets für Instanzen geplanter Aufträge verwendet werden können, muss das **psscheduledjob** -Modul in die Sitzung importiert werden. Um das **psscheduledjob** -Modul zu importieren, geben Sie `Import-Module PSScheduledJob` ein beliebiges geplanter Job-Cmdlet ein, z `Get-ScheduledJob` . b..

Verwenden Sie das-Cmdlet, um eine Liste aller Instanzen eines geplanten Auftrags zu erhalten `Get-Job` .

```powershell
Import-Module PSScheduledJob
Get-Job ProcessJob
```

```Output
Id     Name         PSJobTypeName   State         HasMoreData     Location
--     ----         -------------   -----         -----------     --------
43     ProcessJob   PSScheduledJob  Completed     False           localhost
44     ProcessJob   PSScheduledJob  Completed     False           localhost
45     ProcessJob   PSScheduledJob  Completed     False           localhost
46     ProcessJob   PSScheduledJob  Completed     False           localhost
47     ProcessJob   PSScheduledJob  Completed     False           localhost
48     ProcessJob   PSScheduledJob  Completed     False           localhost
49     ProcessJob   PSScheduledJob  Completed     False           localhost
50     ProcessJob   PSScheduledJob  Completed     False           localhost
```

Das- `Get-Job` Cmdlet sendet **processjob** -Objekte über die Pipeline. Mit dem- `Format-Table` Cmdlet werden die Eigenschaften " **Name**", " **ID**" und " **psbegintime** " einer geplanten Auftrags Instanz in einer Tabelle angezeigt.

```powershell
Get-Job ProcessJob | Format-Table -Property Name, ID, PSBeginTime -Auto
```

```Output
Name       Id PSBeginTime
----       -- ---------
ProcessJob 43 11/2/2011 3:00:02 AM
ProcessJob 44 11/3/2011 3:00:02 AM
ProcessJob 45 11/4/2011 3:00:02 AM
ProcessJob 46 11/5/2011 3:00:02 AM
ProcessJob 47 11/6/2011 3:00:02 AM
ProcessJob 48 11/7/2011 12:00:01 AM
ProcessJob 49 11/7/2011 3:00:02 AM
ProcessJob 50 11/8/2011 3:00:02 AM
```

Verwenden Sie das-Cmdlet, um die Ergebnisse einer Instanz eines geplanten Auftrags zu erhalten `Receive-Job` . Der folgende Befehl ruft die Ergebnisse der neuesten Instanz von processjob (ID = 50) ab.

```powershell
Receive-Job -ID 50
```

### <a name="basic-method-for-finding-job-results-on-disk"></a>Grundlegende Methode zum Ermitteln von Auftrags Ergebnissen auf einem Datenträger

Verwenden Sie zum Verwalten geplanter Aufträge die Job-Cmdlets, z `Get-Job` `Receive-Job` . b. und.

Wenn `Get-Job` die Auftrags Instanz nicht abruft oder `Receive-Job` die Auftrags Ergebnisse nicht erhalten, können Sie die Ausführungs Verlaufs Dateien für den Auftrag auf dem Datenträger durchsuchen.
Der Ausführungs Verlauf enthält einen Datensatz aller ausgelösten Auftrags Instanzen.

Vergewissern Sie sich, dass im Verzeichnis für einen geplanten Auftrag ein Verzeichnis mit dem Namen Timestamp im folgenden Pfad vorhanden ist:

`$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJob\<ScheduledJobName>\Output`

Beispiel:

`C:\Users<UserName>\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJob\<ScheduledJobName>\Output`

Beispielsweise ruft das `Get-ChildItem` Cmdlet den Ausführungs Verlauf auf dem Datenträger des geplanten Auftrags **processjob** ab.

```powershell
$Path = '$home\AppData\Local\Microsoft\Windows\PowerShell'
$Path += '\ScheduledJobs\ProcessJob\Output'
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         11/2/2011   3:00 AM            20111102-030002-260
d----         11/3/2011   3:00 AM            20111103-030002-277
d----         11/4/2011   3:00 AM            20111104-030002-209
d----         11/5/2011   3:00 AM            20111105-030002-251
d----         11/6/2011   3:00 AM            20111106-030002-174
d----         11/7/2011  12:00 AM            20111107-000001-914
d----         11/7/2011   3:00 AM            20111107-030002-376
```

Jedes Zeitstempel benannte Verzeichnis stellt eine Auftrags Instanz dar. Die Ergebnisse der einzelnen Auftrags Instanzen werden in einer **Results.xml** -Datei im Verzeichnis mit dem Namen Timestamp gespeichert.

Beispielsweise ruft der folgende Befehl die **Results.xml** Dateien für jede gespeicherte Instanz des geplanten Auftrags **processjob** ab. Wenn die **Results.xml** Datei fehlt, kann PowerShell die Auftrags Ergebnisse nicht zurückgeben oder anzeigen.

```powershell
$Path = '$home\AppData\Local\Microsoft\Windows\PowerShell'
$Path += '\ScheduledJobs\ProcessJob\Output\*\Results.xml'
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\Appdata\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output
```

Das Auftrags-Cmdlet ist möglicherweise nicht in der Lage, geplante Auftrags Instanzen oder Ihre Ergebnisse abzurufen, da das **psscheduledjob** -Modul nicht in die Sitzung importiert wird.

> [!NOTE]
> Vergewissern Sie sich vor der Verwendung eines Auftrags-Cmdlets für geplante Auftrags Instanzen, dass das **psscheduledjob** -Modul in der Sitzung enthalten ist. Ohne das **psscheduledjob** -Modul können die Auftrags-Cmdlets keine geplanten Auftrags Instanzen oder Ihre Ergebnisse erhalten.

So importieren Sie das **psscheduledjob** -Modul:

```powershell
Import-Module PSScheduledJob
```

### <a name="receive-job-cmdlet-might-already-have-returned-the-results"></a>Receive-Job Cmdlet hat möglicherweise bereits die Ergebnisse zurückgegeben.

Wenn `Receive-Job` keine Ergebnisse der Auftrags Instanz zurückgibt, kann dies daran liegen, `Receive-Job` dass ein Befehl für diese Auftrags Instanz in der aktuellen Sitzung ohne den **Keep** -Parameter ausgeführt wurde.

Wenn Sie `Receive-Job` ohne den **Keep** -Parameter verwenden, `Receive-Job` gibt die Auftrags Ergebnisse zurück und legt die **hasmoredata** -Eigenschaft der Auftrags Instanz auf **false** fest. Der Wert **false** bedeutet, dass `Receive-Job` die Ergebnisse des Auftrags zurückgegeben hat und die Instanz keine weiteren Ergebnisse zurückgibt. Diese Einstellung ist für Standard-Hintergrund Aufträge geeignet, jedoch nicht für Instanzen geplanter Aufträge, die auf dem Datenträger gespeichert werden.

Um die Ergebnisse der Auftrags Instanz erneut zu erhalten, starten Sie eine neue PowerShell-Sitzung, indem Sie eingeben `PowerShell` . Importieren Sie das **psscheduledjob** -Modul, und `Receive-Job` Wiederholen Sie den Befehl.

```powershell
Receive-Job -ID 50
```

```Output
#No results
```

```powershell
PowerShell.exe
```

```Output
Windows PowerShell
Copyright (C) 2012 Microsoft Corporation. All rights reserved.
```

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 50
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

### <a name="using-keep-parameter-to-get-results-more-than-one-time-in-a-session"></a>Verwenden von Keep-Parametern, um Ergebnisse mehr als einmal in einer Sitzung zu erhalten

Um das Ergebnis einer Auftrags Instanz mehr als einmal in einer Sitzung zu erhalten, verwenden Sie den **Keep** -Parameter des `Receive-Job` Cmdlets.

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 50 -Keep
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

```powershell
Receive-Job -ID 50 -Keep
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

### <a name="the-scheduled-job-might-be-corrupted"></a>Der geplante Auftrag ist möglicherweise beschädigt.

Wenn ein geplanter Auftrag beschädigt wird, löscht PowerShell den beschädigten geplanten Auftrag und seine Ergebnisse. Die Ergebnisse eines beschädigten geplanten Auftrags können nicht wieder hergestellt werden.

Verwenden Sie das-Cmdlet, um zu bestimmen, ob ein geplanter Auftrag noch vorhanden ist `Get-ScheduledJob` .

```powershell
Get-ScheduledJob
```

### <a name="the-number-of-results-might-have-exceeded-the-executionhistorylength"></a>Die Anzahl der Ergebnisse hat möglicherweise die executionhistorylength überschritten.

Die **executionhistorylength** -Eigenschaft eines geplanten Auftrags legt fest, wie viele Auftrags Instanzen und ihre Ergebnisse auf dem Datenträger gespeichert werden. Der Standardwert ist 32.
Wenn die Anzahl der Instanzen eines geplanten Auftrags diesen Wert überschreitet, löscht PowerShell die älteste Auftrags Instanz, um Platz für jede neue Auftrags Instanz zu schaffen.

Um den Wert der **executionhistorylength** -Eigenschaft eines geplanten Auftrags zu erhalten, verwenden Sie das folgende Befehls Format:

```powershell
(Get-ScheduledJob <JobName>).ExecutionHistoryLength
```

Mit dem folgenden Befehl wird z. b. der Wert der **executionhistorylength** -Eigenschaft des geplanten Auftrags **processjob** abgerufen.

```powershell
(Get-ScheduledJob ProcessJob).ExecutionHistoryLength
```

Um den Wert der **executionhistorylength** -Eigenschaft festzulegen oder zu ändern, verwenden Sie den **maxresultcount** -Parameter der `Register-ScheduledJob` `Set-ScheduledJob` Cmdlets und.

Der folgende Befehl erhöht den Wert der **executionhistorylength** -Eigenschaft auf 50.

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 50
```

### <a name="the-job-instance-results-might-have-been-deleted"></a>Die Ergebnisse der Auftrags Instanz wurden möglicherweise gelöscht.

Der **clearexecutionhistory** -Parameter des `Set-ScheduledJob` Cmdlets löscht den Ausführungs Verlauf eines Auftrags. Sie können diese Funktion verwenden, um Speicherplatz freizugeben oder Ergebnisse zu löschen, die nicht benötigt oder bereits verwendet, analysiert oder an einem anderen Speicherort gespeichert wurden.

Um den Ausführungs Verlauf eines geplanten Auftrags zu löschen, verwenden Sie den **clearexecutionhistory** -Parameter des geplanten Auftrags.

Der folgende Befehl löscht den Ausführungs Verlauf des geplanten Auftrags **processjob** .

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

Außerdem löscht das `Remove-Job` Cmdlet Auftrags Ergebnisse. Wenn Sie verwenden, `Remove-Job` um einen geplanten Auftrag zu löschen, werden alle Instanzen des Auftrags auf dem Datenträger gelöscht, einschließlich des Ausführungs Verlaufs und aller Auftrags Ergebnisse.

### <a name="jobs-started-by-using-the-start-job-cmdlet-are-not-saved-to-disk"></a>Mit dem Cmdlet "Start-Job" gestartete Aufträge werden nicht auf dem Datenträger gespeichert.

Wenn Sie verwenden, `Start-Job` um einen geplanten Auftrag zu starten, startet anstelle eines Auftrags Auslösers `Start-Job` einen Standard Hintergrund Auftrag. Der Hintergrund Auftrag und seine Ergebnisse werden nicht im Ausführungs Verlauf des Auftrags auf dem Datenträger gespeichert.

Sie können das `Get-Job` Cmdlet zum Abrufen des Auftrags und des `Receive-Job` Cmdlets verwenden, um die Auftrags Ergebnisse zu erhalten. die Ergebnisse sind jedoch nur verfügbar, bis Sie Sie erhalten, es sei denn, Sie verwenden den Keep-Parameter des `Receive-Job` Cmdlets.

Außerdem sind Hintergrund Aufträge und ihre Ergebnisse Sitzungs spezifisch. Sie sind nur in der Sitzung vorhanden, in der Sie erstellt wurden. Wenn Sie den Auftrag mit löschen `Remove-Job` , schließen Sie die Sitzung, oder schließen Sie PowerShell, sodass die Auftrags Instanz und ihre Ergebnisse gelöscht werden.

## <a name="scheduled-job-doesnt-run"></a>Der geplante Auftrag wird nicht ausgeführt.

Geplante Aufträge werden nicht automatisch ausgeführt, wenn der Auftrag ausgelöst oder der geplante Auftrag deaktiviert wird.

Verwenden Sie das `Get-ScheduledJob` Cmdlet, um den geplanten Auftrag zu erhalten. Vergewissern Sie sich, dass der Wert der **aktivierten** Eigenschaft des geplanten Auftrags " **true**" lautet.

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command         Enabled
--         ----            --------        -------         -------
4          ProcessJob      {1, 2}          Get-Process     True
```

```powershell
(Get-ScheduledJob ProcessJob).Enabled
```

```Output
True
```

Verwenden Sie das `Get-JobTrigger` Cmdlet, um die Auftrags Trigger des geplanten Auftrags zu erhalten.
Vergewissern Sie sich, dass der Wert der **aktivierten** Eigenschaft des Auftrags Auslösers " **true**" ist.

```powershell
Get-ScheduledJob ProcessJob | Get-JobTrigger
```

```Output
Id      Frequency    Time                   DaysOfWeek            Enabled
--      ---------    ----                   ----------            -------
1       Weekly       11/7/2011 5:00:00 AM   {Monday, Thursday}    True
2       Daily        11/7/2011 3:00:00 PM                         True
```

```powershell
Get-ScheduledJob ProcessJob|Get-JobTrigger|Format-Table ID, Enabled -Auto
```

```Output
Id Enabled
-- -------
1    True
2    True
```

### <a name="scheduled-jobs-dont-run-automatically-if-job-triggers-are-invalid"></a>Geplante Aufträge werden nicht automatisch ausgeführt, wenn Auftrags Trigger ungültig sind.

Beispielsweise kann ein Auftrags Fehler ein Datum in der Vergangenheit oder ein Datum angeben, das nicht eintritt, z. b. den 5. Montag des Monats.

Geplante Aufträge werden nicht automatisch ausgeführt, wenn die Bedingungen des Auftrags Auslösers oder der Auftrags Optionen nicht erfüllt werden.

Beispielsweise wird ein geplanter Auftrag, der nur ausgeführt wird, wenn sich ein bestimmter Benutzer am Computer anmeldet, nicht ausgeführt, wenn sich der Benutzer nicht anmeldet oder nur eine Remote Verbindung herstellt.

Überprüfen Sie die Optionen des geplanten Auftrags, und stellen Sie sicher, dass Sie erfüllt sind.
Beispielsweise wird ein geplanter Auftrag, der erfordert, dass sich der Computer im Leerlauf befindet oder eine Netzwerkverbindung erfordert oder eine lange **idleduration** -oder eine kurze **IdleTimeout** -Eigenschaft aufweist, nie ausgeführt.

Verwenden `Get-ScheduledJobOption` Sie das Cmdlet, um die Auftrags Optionen und deren Werte zu überprüfen.

```powershell
Get-ScheduledJobOption -Name ProcessJob
```

```Output
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : True
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

Beschreibungen der Optionen für geplante Aufträge finden Sie unter [New-scheduledjoboption](xref:PSScheduledJob.New-ScheduledJobOption).

### <a name="the-scheduled-job-instance-might-have-failed"></a>Bei der geplanten Auftrags Instanz ist möglicherweise ein Fehler aufgetreten.

Wenn ein Befehl für einen geplanten Auftrag fehlschlägt, meldet PowerShell ihn sofort, indem er eine Fehlermeldung erzeugt. Wenn der Auftrag jedoch fehlschlägt, wenn Taskplaner versucht, ihn auszuführen, ist der Fehler für PowerShell nicht verfügbar.

Verwenden Sie die folgenden Methoden, um Auftrags Fehler zu erkennen und zu beheben:

Überprüfen Sie das Ereignisprotokoll Taskplaner auf Fehler. Um das Protokoll zu überprüfen, verwenden Sie Ereignisanzeige oder einen PowerShell-Befehl wie den folgenden:

```powershell
Get-WinEvent -LogName Microsoft-Windows-TaskScheduler/Operational |
 Where {$_.Message -like "fail"}
```

Überprüfen Sie den Auftragsdaten Satz in Taskplaner. Geplante PowerShell-Aufträge werden im folgenden geplanten Aufgaben Ordner gespeichert:

`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`

### <a name="the-scheduled-job-might-not-run-because-of-insufficient-permission"></a>Der geplante Auftrag kann aufgrund unzureichender Berechtigungen nicht ausgeführt werden.

Geplante Aufträge werden mit den Berechtigungen des Benutzers ausgeführt, der den Auftrag erstellt hat, oder mit den Berechtigungen des Benutzers, der durch den **Credential** -Parameter im `Register-ScheduledJob` Befehl oder angegeben wird `Set-ScheduledJob` .

Wenn dieser Benutzer nicht über die Berechtigung zum Ausführen der Befehle oder Skripts verfügt, schlägt der Auftrag fehl.

## <a name="cant-get-scheduled-job-or-scheduled-job-is-corrupted"></a>Der geplante Auftrag konnte nicht oder der geplante Auftrag beschädigt werden.

In seltenen Fällen können geplante Aufträge beschädigt werden oder interne Widersprüche enthalten, die nicht aufgelöst werden können. Dies geschieht in der Regel, wenn die XML-Dateien für den geplanten Auftrag manuell bearbeitet werden, was zu einem ungültigen XML-Code führt.

Wenn ein geplanter Auftrag beschädigt ist, versucht PowerShell, den geplanten Auftrag, seinen Ausführungs Verlauf und seine Ergebnisse von der Festplatte zu löschen.

Wenn der geplante Auftrag nicht entfernt werden kann, erhalten Sie jedes Mal, wenn Sie das Cmdlet ausführen, eine Fehlermeldung zu einem fehlerhaften Auftrag `Get-ScheduledJob` .

Verwenden Sie zum Entfernen eines beschädigten geplanten Auftrags eine der folgenden Methoden:

Löschen Sie das `<ScheduledJobName>` Verzeichnis für den geplanten Auftrag. Löschen Sie das **ScheduledJob** -Verzeichnis nicht.

Der Speicherort des Verzeichnisses:

`$env:UserProfile\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>`

Beispiel:

`C:\Users<UserName>\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>.`

Verwenden Sie Taskplaner, um den geplanten Auftrag zu löschen. Geplante PowerShell-Tasks werden im folgenden Taskplaner Pfad angezeigt:

`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>`

## <a name="job-cmdlets-cant-consistently-find-scheduled-jobs"></a>Auftrags-Cmdlets können geplante Aufträge nicht konsistent finden.

Wenn das **psscheduledjob** -Modul nicht in der aktuellen Sitzung enthalten ist, können die Auftrags-Cmdlets keine geplanten Aufträge erhalten, Sie starten oder Ergebnisse erhalten.

Um das **psscheduledjob** -Modul zu importieren, geben `Import-Module PSScheduledJob` Sie ein Cmdlet im Modul ein, oder führen Sie es aus, z `Get-ScheduledJob` . b. das Cmdlet.
Ab PowerShell 3,0 werden Module automatisch importiert, wenn Sie ein beliebiges Cmdlet im Modul erhalten oder verwenden.

Wenn das **psscheduledjob** -Modul nicht in der aktuellen Sitzung enthalten ist, ist die folgende Befehlssequenz möglich.

```powershell
Get-Job ProcessJob
```

```Output
Get-Job : The command cannot find the job because the job name
ProcessJob was not found.
Verify the value of the Name parameter, and then try the command again.
+ CategoryInfo          : ObjectNotFound: (ProcessJob:String) [Get-Job],
PSArgumentException
+ FullyQualifiedErrorId : JobWithSpecifiedNameNotFound,Microsoft.PowerShell.
Commands.GetJobCommand
```

```powershell
Get-Job
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command      Enabled
--         ----            --------        -------      -------
4          ProcessJob      {1}             Get-Process  True
```

```powershell
Get-Job ProcessJob
```

```Output
Id     Name         PSJobTypeName   State       HasMoreData     Location
--     ----         -------------   -----       -----------     --------
43     ProcessJob   PSScheduledJob  Completed   True            localhost
44     ProcessJob   PSScheduledJob  Completed   True            localhost
45     ProcessJob   PSScheduledJob  Completed   True            localhost
46     ProcessJob   PSScheduledJob  Completed   True            localhost
47     ProcessJob   PSScheduledJob  Completed   True            localhost
48     ProcessJob   PSScheduledJob  Completed   True            localhost
49     ProcessJob   PSScheduledJob  Completed   True            localhost
50     ProcessJob   PSScheduledJob  Completed   True            localhost
```

Dieses Verhalten tritt auf, da der `Get-ScheduledJob` Befehl automatisch das **psscheduledjob** -Modul importiert und dann den Befehl ausführt.

## <a name="see-also"></a>Weitere Informationen

[about_Scheduled_Jobs_Basics](about_Scheduled_Jobs_Basics.md)

[about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)

[about_Scheduled_Jobs](about_Scheduled_Jobs.md)

Cmdlets für das [psscheduledjob](xref:PSScheduledJob) -Modul

[Aufgabenplanung](/windows/desktop/TaskSchd/task-scheduler-reference)
