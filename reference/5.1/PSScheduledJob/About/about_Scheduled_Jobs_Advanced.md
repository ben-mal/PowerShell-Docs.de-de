---
description: Erläutert erweiterte geplante Auftragsthemen, einschließlich der Dateistruktur, die geplanten Aufträgen zugrunde liegt.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_advanced?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Advanced
ms.openlocfilehash: 7b09a72e8ad7e68641c73d2f7e59065dbf8f889b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221935"
---
# <a name="about-scheduled-jobs-advanced"></a>Informationen zu geplanten Aufträgen erweitert

## <a name="short-description"></a>Kurze Beschreibung

Erläutert erweiterte geplante Auftragsthemen, einschließlich der Dateistruktur, die geplanten Aufträgen zugrunde liegt.

## <a name="long-description"></a>Lange Beschreibung

Weitere Informationen zu den im **psscheduledjob** -Modul enthaltenen Cmdlets finden Sie unter [psscheduledjob](xref:PSScheduledJob).

## <a name="scheduled-job-directories-and-files"></a>Geplante Auftrags Verzeichnisse und-Dateien

Geplante PowerShell-Aufträge sind PowerShell-Aufträge und Taskplaner Tasks.
Jeder geplante Auftrag wird in Taskplaner registriert und im XML-Format Microsoft .NET Framework-Serialisierung auf dem Datenträger gespeichert.

Wenn Sie einen geplanten Auftrag erstellen, erstellt PowerShell ein Verzeichnis für den geplanten Auftrag im `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` Verzeichnis auf dem lokalen Computer. Der Verzeichnisname ist identisch mit dem Auftrags Namen.

Im folgenden finden Sie ein Beispiel für ein **scheduledjobs** -Verzeichnis.

```powershell
Get-ChildItem $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs
```

```Output
Directory: C:\Users\User01\AppData\Local
               \Microsoft\Windows\PowerShell\ScheduledJobs

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         9/29/2011  10:03 AM            ArchiveProjects
d----         9/30/2011   1:18 PM            Inventory
d----        10/20/2011   9:15 AM            Backup-Scripts
d----         11/7/2011  10:40 AM            ProcessJob
d----         11/2/2011  10:25 AM            SecureJob
d----         9/27/2011   1:29 PM            Test-HelpFiles
d----         9/26/2011   4:22 PM            DeployPackage
```

Jeder geplante Auftrag verfügt über ein eigenes Verzeichnis. Das Verzeichnis enthält die XML-Datei für den geplanten Auftrag und ein **Ausgabe** Unterverzeichnis.

```powershell
$Path = "$home\AppData\Local\Microsoft\Windows\PowerShell"
$Path += "\ScheduledJobs\ProcessJob"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         11/1/2011   3:00 PM            Output
-a---         11/1/2011   3:43 PM       7281 ScheduledJobDefinition.xml
```

Das **Ausgabe** Verzeichnis für einen geplanten Auftrag enthält seinen Ausführungs Verlauf.
Jedes Mal, wenn ein Auftrags auslöst einen geplanten Auftrag startet, erstellt PowerShell im Ausgabeverzeichnis ein Verzeichnis mit dem Namen Timestamp. Das Zeitstempel-Verzeichnis enthält die Ergebnisse des Auftrags in einer **Results.xml** Datei und den Auftragsstatus in einer **Status.xml** Datei.

Der folgende Befehl zeigt die Ausführungs Verlaufs Verzeichnisse für den geplanten Auftrag **processjob** .

```powershell
$Path = "$home\AppData\Local\Microsoft"
$Path += "\Windows\PowerShell\ScheduledJobs\ProcessJob\Output"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft
               \Windows\PowerShell\ScheduledJobs\ProcessJob\Output

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

```powershell
$Path = "$home\AppData\Local\Microsoft\Windows\PowerShell\"
$Path += "ScheduledJobs\ProcessJob\Output\20111102-030002-260"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output\20111102-030002-260

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         11/2/2011   3:00 AM     581106 Results.xml
-a---         11/2/2011   3:00 AM       9451 Status.xml
```

Sie können die Dateien **ScheduledJobDefinition.xml** , **Results.xml** und **Status.xml** öffnen und überprüfen, oder Sie können das `Select-XML` Cmdlet verwenden, um die Dateien zu analysieren.

> [!WARNING]
> Bearbeiten Sie die XML-Dateien nicht. Wenn eine XML-Datei ungültigen XML-Code enthält, löscht PowerShell den geplanten Auftrag und den zugehörigen Ausführungs Verlauf, einschließlich der Auftrags Ergebnisse.

## <a name="start-a-scheduled-job-immediately"></a>Einen geplanten Auftrag sofort starten

Es gibt zwei Möglichkeiten, einen geplanten Auftrag zu starten:

- Führen Sie das- `Start-Job` Cmdlet aus, um einen geplanten Auftrag zu starten.
- Fügen Sie dem Befehl den **runnow** -Parameter hinzu `Register-ScheduledJob` , um den Auftrag zu starten, sobald der Befehl ausgeführt wird.

Aufträge, die mithilfe des `Start-Job` Cmdlets gestartet werden, sind Standard-PowerShell-Hintergrund Aufträge, keine Instanzen des geplanten Auftrags. Diese Aufträge werden wie alle Hintergrund Aufträge sofort gestartet, unterliegen nicht den Auftrags Optionen oder werden von Auftrags Triggern nicht beeinträchtigt. Die Auftrags Ausgabe wird nicht im **Ausgabe** Verzeichnis des Verzeichnisses für den geplanten Auftrag gespeichert.

Der folgende Befehl verwendet den **DefinitionName** -Parameter des `Start-Job` Cmdlets, um den geplanten Auftrag "processjob" zu starten.

```powershell
Start-Job -DefinitionName ProcessJob
```

Verwenden Sie die Job-Cmdlets, um den Auftrag zu verwalten und die Auftrags Ergebnisse zu erhalten. Weitere Informationen zu den Auftrags-Cmdlets finden Sie unter [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).

> [!NOTE]
> Damit die Job-Cmdlets für Instanzen geplanter Aufträge verwendet werden können, muss das **psscheduledjob** -Modul in die Sitzung importiert werden. Um das **psscheduledjob** -Modul zu importieren, geben Sie `Import-Module PSScheduledJob` ein beliebiges geplanter Job-Cmdlet ein, z `Get-ScheduledJob` . b..

## <a name="rename-a-scheduled-job"></a>Umbenennen eines geplanten Auftrags

Um einen geplanten Auftrag umzubenennen, verwenden Sie den Name-Parameter des `Set-ScheduledJob` Cmdlets. Wenn Sie einen geplanten Auftrag umbenennen, ändert PowerShell den Namen des geplanten Auftrags und des geplanten Auftrags Verzeichnisses. Allerdings werden die Namen von Instanzen des geplanten Auftrags, die bereits ausgeführt wurden, nicht geändert.

## <a name="get-start-and-end-times"></a>Start-und Endzeit

Um die Datums-und Uhrzeitangaben der Auftrags Instanzen abzurufen, verwenden Sie die Eigenschaften **psbegintime** und **psendtime** des ScheduledJob-Objekts, das `Get-Job` für geplante Aufträge zurückgibt.

Im folgenden Beispiel wird der **Property** -Parameter des `Format-Table` Cmdlets verwendet, um die Eigenschaften **psbegintime** und **psendtime** der einzelnen Auftrags Instanzen in einer Tabelle anzuzeigen. Eine berechnete Eigenschaft namens **Bezeichnung** zeigt die verstrichene Zeit der einzelnen Auftrags Instanzen an.

```powershell
Get-job -Name UpdateHelpJob | 
  Format-Table -Property ID, PSBeginTime, PSEndTime,
@{Label="Elapsed Time";Expression={$.PsEndTime - $.PSBeginTime}}
```

```Output
Id   PSBeginTime             PSEndTime                Elapsed Time
--   -----------             ---------                ------------
 2   11/3/2011 3:00:01 AM    11/3/2011 3:00:39 AM     00:00:38.0053854
 3   11/4/2011 3:00:02 AM    11/4/2011 3:01:01 AM     00:00:59.1188475
 4   11/5/2011 3:00:02 AM    11/5/2011 3:00:50 AM     00:00:48.3692034
 5   11/6/2011 3:00:01 AM    11/6/2011 3:00:54 AM     00:00:52.8013036
 6   11/7/2011 3:00:01 AM    11/7/2011 3:00:38 AM     00:00:37.1930350
 7   11/8/2011 3:00:01 AM    11/8/2011 3:00:57 AM     00:00:56.2570556
 8   11/9/2011 3:00:03 AM    11/9/2011 3:00:55 AM     00:00:51.8142222
 9   11/10/2011 3:00:02 AM   11/10/2011 3:00:42 AM    00:00:40.7195954
```

## <a name="manage-execution-history"></a>Verwalten des Ausführungs Verlaufs

Sie können die Anzahl der Ergebnisse der Auftrags Instanz ermitteln, die für jeden geplanten Auftrag gespeichert werden, und den Ausführungs Verlauf und die gespeicherten Auftrags Ergebnisse eines beliebigen geplanten Auftrags löschen.

Die **executionhistorylength** -Eigenschaft eines geplanten Auftrags bestimmt, wie viele auftragsinstanzergebnisse für den geplanten Auftrag gespeichert werden. Wenn die Anzahl gespeicherter Ergebnisse den Wert der **executionhistorylength** -Eigenschaft überschreitet, löscht PowerShell die Ergebnisse der ältesten Instanz, um Platz für die Ergebnisse der neuesten Instanz zu schaffen.

Standardmäßig speichert PowerShell den Ausführungs Verlauf und die Ergebnisse von 32 Instanzen jedes geplanten Auftrags. Um diesen Wert zu ändern, verwenden Sie die **maxresultcount** -Parameter der `Register-ScheduledJob` `Set-ScheduledJob` Cmdlets oder.

Um den Ausführungs Verlauf und alle Ergebnisse für einen geplanten Auftrag zu löschen, verwenden Sie den **clearexecutionhistory** -Parameter des `Set-ScheduledJob` Cmdlets. Wenn Sie diesen Ausführungs Verlauf löschen, wird nicht verhindert, dass PowerShell die Ergebnisse der neuen Instanzen des geplanten Auftrags speichert.

Im folgenden Beispiel wird Verteilung verwendet, um `$JobParms` Parameterwerte zu erstellen, die an das `Register-ScheduledJob` Cmdlet übergeben werden. Weitere Informationen finden Sie unter [about_Splatting. MD](../../Microsoft.PowerShell.Core/About/about_Splatting.md).
Der `Register-ScheduledJob` verwendet `@JobParms` , um einen geplanten Auftrag zu erstellen. Der Befehl verwendet den **maxresultcount** -Parameter mit dem Wert 12, um nur die Ergebnisse der 12 neuesten Auftrags Instanz des geplanten Auftrags zu speichern.

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  MaxResultCount = "12"
}

Register-ScheduledJob @JobParms
```

Der folgende Befehl verwendet den **maxresultcount** -Parameter des `Set-ScheduledJob` Cmdlets, um die Anzahl der gespeicherten instanzergebnisse auf zu erhöhen.
15.

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 15
```

Der folgende Befehl löscht den Ausführungs Verlauf und die aktuell gespeicherten Ergebnisse des geplanten Auftrags **processjob** .

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

Der folgende Befehl ruft die Werte der Eigenschaften "Name" und " **executionhistorylength** " aller geplanten Aufträge auf dem Computer ab und zeigt Sie in einer Tabelle an.

```powershell
Get-ScheduledJob | 
  Format-Table -Property Name, ExecutionHistoryLength -AutoSize
```

## <a name="see-also"></a>Weitere Informationen:

[about_Scheduled_Jobs_Basics](about_Scheduled_Jobs_Basics.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

[about_Scheduled_Jobs](about_Scheduled_Jobs.md)

[about_Splatting. MD](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

Cmdlets für das [psscheduledjob](xref:PSScheduledJob) -Modul

[Aufgabenplanung](/windows/desktop/TaskSchd/task-scheduler-reference)
