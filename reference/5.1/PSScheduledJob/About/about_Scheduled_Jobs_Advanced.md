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
# <a name="about-scheduled-jobs-advanced"></a><span data-ttu-id="eb77c-104">Informationen zu geplanten Aufträgen erweitert</span><span class="sxs-lookup"><span data-stu-id="eb77c-104">About Scheduled Jobs Advanced</span></span>

## <a name="short-description"></a><span data-ttu-id="eb77c-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb77c-105">Short description</span></span>

<span data-ttu-id="eb77c-106">Erläutert erweiterte geplante Auftragsthemen, einschließlich der Dateistruktur, die geplanten Aufträgen zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="eb77c-106">Explains advanced scheduled job topics, including the file structure that underlies scheduled jobs.</span></span>

## <a name="long-description"></a><span data-ttu-id="eb77c-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb77c-107">Long description</span></span>

<span data-ttu-id="eb77c-108">Weitere Informationen zu den im **psscheduledjob** -Modul enthaltenen Cmdlets finden Sie unter [psscheduledjob](xref:PSScheduledJob).</span><span class="sxs-lookup"><span data-stu-id="eb77c-108">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

## <a name="scheduled-job-directories-and-files"></a><span data-ttu-id="eb77c-109">Geplante Auftrags Verzeichnisse und-Dateien</span><span class="sxs-lookup"><span data-stu-id="eb77c-109">Scheduled job directories and files</span></span>

<span data-ttu-id="eb77c-110">Geplante PowerShell-Aufträge sind PowerShell-Aufträge und Taskplaner Tasks.</span><span class="sxs-lookup"><span data-stu-id="eb77c-110">PowerShell scheduled jobs are both PowerShell jobs and Task Scheduler tasks.</span></span>
<span data-ttu-id="eb77c-111">Jeder geplante Auftrag wird in Taskplaner registriert und im XML-Format Microsoft .NET Framework-Serialisierung auf dem Datenträger gespeichert.</span><span class="sxs-lookup"><span data-stu-id="eb77c-111">Each scheduled job is registered in Task Scheduler and saved on disk in Microsoft .NET Framework Serialization XML format.</span></span>

<span data-ttu-id="eb77c-112">Wenn Sie einen geplanten Auftrag erstellen, erstellt PowerShell ein Verzeichnis für den geplanten Auftrag im `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` Verzeichnis auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="eb77c-112">When you create a scheduled job, PowerShell creates a directory for the scheduled job in the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` directory on the local computer.</span></span> <span data-ttu-id="eb77c-113">Der Verzeichnisname ist identisch mit dem Auftrags Namen.</span><span class="sxs-lookup"><span data-stu-id="eb77c-113">The directory name is the same as the job name.</span></span>

<span data-ttu-id="eb77c-114">Im folgenden finden Sie ein Beispiel für ein **scheduledjobs** -Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="eb77c-114">The following is a sample **ScheduledJobs** directory.</span></span>

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

<span data-ttu-id="eb77c-115">Jeder geplante Auftrag verfügt über ein eigenes Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="eb77c-115">Each scheduled job has its own directory.</span></span> <span data-ttu-id="eb77c-116">Das Verzeichnis enthält die XML-Datei für den geplanten Auftrag und ein **Ausgabe** Unterverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="eb77c-116">The directory contains the scheduled job XML file and an **Output** subdirectory.</span></span>

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

<span data-ttu-id="eb77c-117">Das **Ausgabe** Verzeichnis für einen geplanten Auftrag enthält seinen Ausführungs Verlauf.</span><span class="sxs-lookup"><span data-stu-id="eb77c-117">The **Output** directory for a scheduled job contains its execution history.</span></span>
<span data-ttu-id="eb77c-118">Jedes Mal, wenn ein Auftrags auslöst einen geplanten Auftrag startet, erstellt PowerShell im Ausgabeverzeichnis ein Verzeichnis mit dem Namen Timestamp.</span><span class="sxs-lookup"><span data-stu-id="eb77c-118">Each time a job trigger starts a scheduled job, PowerShell creates a timestamp-named directory in the output directory.</span></span> <span data-ttu-id="eb77c-119">Das Zeitstempel-Verzeichnis enthält die Ergebnisse des Auftrags in einer **Results.xml** Datei und den Auftragsstatus in einer **Status.xml** Datei.</span><span class="sxs-lookup"><span data-stu-id="eb77c-119">The timestamp directory contains the results of the job in a **Results.xml** file and the job status in a **Status.xml** file.</span></span>

<span data-ttu-id="eb77c-120">Der folgende Befehl zeigt die Ausführungs Verlaufs Verzeichnisse für den geplanten Auftrag **processjob** .</span><span class="sxs-lookup"><span data-stu-id="eb77c-120">The following command shows the execution history directories for the **ProcessJob** scheduled job.</span></span>

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

<span data-ttu-id="eb77c-121">Sie können die Dateien **ScheduledJobDefinition.xml** , **Results.xml** und **Status.xml** öffnen und überprüfen, oder Sie können das `Select-XML` Cmdlet verwenden, um die Dateien zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="eb77c-121">You can open and examine the **ScheduledJobDefinition.xml** , **Results.xml** and **Status.xml** files or use the `Select-XML` cmdlet to parse the files.</span></span>

> [!WARNING]
> <span data-ttu-id="eb77c-122">Bearbeiten Sie die XML-Dateien nicht.</span><span class="sxs-lookup"><span data-stu-id="eb77c-122">Do not edit the XML files.</span></span> <span data-ttu-id="eb77c-123">Wenn eine XML-Datei ungültigen XML-Code enthält, löscht PowerShell den geplanten Auftrag und den zugehörigen Ausführungs Verlauf, einschließlich der Auftrags Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="eb77c-123">If any XML file contains invalid XML, PowerShell deletes the scheduled job and its execution history, including job results.</span></span>

## <a name="start-a-scheduled-job-immediately"></a><span data-ttu-id="eb77c-124">Einen geplanten Auftrag sofort starten</span><span class="sxs-lookup"><span data-stu-id="eb77c-124">Start a scheduled job immediately</span></span>

<span data-ttu-id="eb77c-125">Es gibt zwei Möglichkeiten, einen geplanten Auftrag zu starten:</span><span class="sxs-lookup"><span data-stu-id="eb77c-125">You can start a scheduled job immediately in one of two ways:</span></span>

- <span data-ttu-id="eb77c-126">Führen Sie das- `Start-Job` Cmdlet aus, um einen geplanten Auftrag zu starten.</span><span class="sxs-lookup"><span data-stu-id="eb77c-126">Run the `Start-Job` cmdlet to start any scheduled job.</span></span>
- <span data-ttu-id="eb77c-127">Fügen Sie dem Befehl den **runnow** -Parameter hinzu `Register-ScheduledJob` , um den Auftrag zu starten, sobald der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eb77c-127">Add the **RunNow** parameter to your `Register-ScheduledJob` command to start the job as soon as the command is run.</span></span>

<span data-ttu-id="eb77c-128">Aufträge, die mithilfe des `Start-Job` Cmdlets gestartet werden, sind Standard-PowerShell-Hintergrund Aufträge, keine Instanzen des geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="eb77c-128">Jobs that are started by using the `Start-Job` cmdlet are standard PowerShell background jobs, not instances of the scheduled job.</span></span> <span data-ttu-id="eb77c-129">Diese Aufträge werden wie alle Hintergrund Aufträge sofort gestartet, unterliegen nicht den Auftrags Optionen oder werden von Auftrags Triggern nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="eb77c-129">Like all background jobs, these jobs start immediately, they aren't subject to job options or affected by job triggers.</span></span> <span data-ttu-id="eb77c-130">Die Auftrags Ausgabe wird nicht im **Ausgabe** Verzeichnis des Verzeichnisses für den geplanten Auftrag gespeichert.</span><span class="sxs-lookup"><span data-stu-id="eb77c-130">The job output isn't saved in the **Output** directory of the scheduled job directory.</span></span>

<span data-ttu-id="eb77c-131">Der folgende Befehl verwendet den **DefinitionName** -Parameter des `Start-Job` Cmdlets, um den geplanten Auftrag "processjob" zu starten.</span><span class="sxs-lookup"><span data-stu-id="eb77c-131">The following command uses the **DefinitionName** parameter of the `Start-Job` cmdlet to start the ProcessJob scheduled job.</span></span>

```powershell
Start-Job -DefinitionName ProcessJob
```

<span data-ttu-id="eb77c-132">Verwenden Sie die Job-Cmdlets, um den Auftrag zu verwalten und die Auftrags Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="eb77c-132">To manage the job and get the job results, use the job cmdlets.</span></span> <span data-ttu-id="eb77c-133">Weitere Informationen zu den Auftrags-Cmdlets finden Sie unter [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="eb77c-133">For more information about the job cmdlets, see [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

> [!NOTE]
> <span data-ttu-id="eb77c-134">Damit die Job-Cmdlets für Instanzen geplanter Aufträge verwendet werden können, muss das **psscheduledjob** -Modul in die Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="eb77c-134">To use the Job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="eb77c-135">Um das **psscheduledjob** -Modul zu importieren, geben Sie `Import-Module PSScheduledJob` ein beliebiges geplanter Job-Cmdlet ein, z `Get-ScheduledJob` . b..</span><span class="sxs-lookup"><span data-stu-id="eb77c-135">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

## <a name="rename-a-scheduled-job"></a><span data-ttu-id="eb77c-136">Umbenennen eines geplanten Auftrags</span><span class="sxs-lookup"><span data-stu-id="eb77c-136">Rename a scheduled job</span></span>

<span data-ttu-id="eb77c-137">Um einen geplanten Auftrag umzubenennen, verwenden Sie den Name-Parameter des `Set-ScheduledJob` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="eb77c-137">To rename a scheduled job, use the Name parameter of the `Set-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="eb77c-138">Wenn Sie einen geplanten Auftrag umbenennen, ändert PowerShell den Namen des geplanten Auftrags und des geplanten Auftrags Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="eb77c-138">When you rename a scheduled job, PowerShell changes the name of the scheduled job and the scheduled job directory.</span></span> <span data-ttu-id="eb77c-139">Allerdings werden die Namen von Instanzen des geplanten Auftrags, die bereits ausgeführt wurden, nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="eb77c-139">However, it doesn't change the names of instances of the scheduled job that have already run.</span></span>

## <a name="get-start-and-end-times"></a><span data-ttu-id="eb77c-140">Start-und Endzeit</span><span class="sxs-lookup"><span data-stu-id="eb77c-140">Get start and end times</span></span>

<span data-ttu-id="eb77c-141">Um die Datums-und Uhrzeitangaben der Auftrags Instanzen abzurufen, verwenden Sie die Eigenschaften **psbegintime** und **psendtime** des ScheduledJob-Objekts, das `Get-Job` für geplante Aufträge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="eb77c-141">To get the dates and times that job instances started and ended, use the **PSBeginTime** and **PSEndTime** properties of the ScheduledJob object that `Get-Job` returns for scheduled jobs.</span></span>

<span data-ttu-id="eb77c-142">Im folgenden Beispiel wird der **Property** -Parameter des `Format-Table` Cmdlets verwendet, um die Eigenschaften **psbegintime** und **psendtime** der einzelnen Auftrags Instanzen in einer Tabelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="eb77c-142">The following example uses the **Property** parameter of the `Format-Table` cmdlet to display the **PSBeginTime** and **PSEndTime** properties of each job instance in a table.</span></span> <span data-ttu-id="eb77c-143">Eine berechnete Eigenschaft namens **Bezeichnung** zeigt die verstrichene Zeit der einzelnen Auftrags Instanzen an.</span><span class="sxs-lookup"><span data-stu-id="eb77c-143">A calculated property named **Label** displays the elapsed time of each job instance.</span></span>

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

## <a name="manage-execution-history"></a><span data-ttu-id="eb77c-144">Verwalten des Ausführungs Verlaufs</span><span class="sxs-lookup"><span data-stu-id="eb77c-144">Manage execution history</span></span>

<span data-ttu-id="eb77c-145">Sie können die Anzahl der Ergebnisse der Auftrags Instanz ermitteln, die für jeden geplanten Auftrag gespeichert werden, und den Ausführungs Verlauf und die gespeicherten Auftrags Ergebnisse eines beliebigen geplanten Auftrags löschen.</span><span class="sxs-lookup"><span data-stu-id="eb77c-145">You can determine the number of job instance results that are saved for each scheduled job and delete the execution history and saved job results of any scheduled job.</span></span>

<span data-ttu-id="eb77c-146">Die **executionhistorylength** -Eigenschaft eines geplanten Auftrags bestimmt, wie viele auftragsinstanzergebnisse für den geplanten Auftrag gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="eb77c-146">The **ExecutionHistoryLength** property of a scheduled job determines how many job instance results are saved for the scheduled job.</span></span> <span data-ttu-id="eb77c-147">Wenn die Anzahl gespeicherter Ergebnisse den Wert der **executionhistorylength** -Eigenschaft überschreitet, löscht PowerShell die Ergebnisse der ältesten Instanz, um Platz für die Ergebnisse der neuesten Instanz zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="eb77c-147">When the number of saved results exceeds the value of the **ExecutionHistoryLength** property, PowerShell deletes the results of the oldest instance to make room for the results of the newest instance.</span></span>

<span data-ttu-id="eb77c-148">Standardmäßig speichert PowerShell den Ausführungs Verlauf und die Ergebnisse von 32 Instanzen jedes geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="eb77c-148">By default, PowerShell saves the execution history and results of 32 instances of each scheduled job.</span></span> <span data-ttu-id="eb77c-149">Um diesen Wert zu ändern, verwenden Sie die **maxresultcount** -Parameter der `Register-ScheduledJob` `Set-ScheduledJob` Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="eb77c-149">To change that value, use the **MaxResultCount** parameters of the `Register-ScheduledJob` or `Set-ScheduledJob` cmdlets.</span></span>

<span data-ttu-id="eb77c-150">Um den Ausführungs Verlauf und alle Ergebnisse für einen geplanten Auftrag zu löschen, verwenden Sie den **clearexecutionhistory** -Parameter des `Set-ScheduledJob` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="eb77c-150">To delete the execution history and all results for a scheduled job, use the **ClearExecutionHistory** parameter of the `Set-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="eb77c-151">Wenn Sie diesen Ausführungs Verlauf löschen, wird nicht verhindert, dass PowerShell die Ergebnisse der neuen Instanzen des geplanten Auftrags speichert.</span><span class="sxs-lookup"><span data-stu-id="eb77c-151">Deleting this execution history does not prevent PowerShell from saving the results of new instances of the scheduled job.</span></span>

<span data-ttu-id="eb77c-152">Im folgenden Beispiel wird Verteilung verwendet, um `$JobParms` Parameterwerte zu erstellen, die an das `Register-ScheduledJob` Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="eb77c-152">The following example uses splatting to create `$JobParms` which are parameter values that are passed to the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="eb77c-153">Weitere Informationen finden Sie unter [about_Splatting. MD](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="eb77c-153">For more information, see [about_Splatting.md](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>
<span data-ttu-id="eb77c-154">Der `Register-ScheduledJob` verwendet `@JobParms` , um einen geplanten Auftrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb77c-154">The `Register-ScheduledJob` uses `@JobParms` to create a scheduled job.</span></span> <span data-ttu-id="eb77c-155">Der Befehl verwendet den **maxresultcount** -Parameter mit dem Wert 12, um nur die Ergebnisse der 12 neuesten Auftrags Instanz des geplanten Auftrags zu speichern.</span><span class="sxs-lookup"><span data-stu-id="eb77c-155">The command uses the **MaxResultCount** parameter with a value of 12 to save only the 12 newest job instance results of the scheduled job.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  MaxResultCount = "12"
}

Register-ScheduledJob @JobParms
```

<span data-ttu-id="eb77c-156">Der folgende Befehl verwendet den **maxresultcount** -Parameter des `Set-ScheduledJob` Cmdlets, um die Anzahl der gespeicherten instanzergebnisse auf zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="eb77c-156">The following command uses the **MaxResultCount** parameter of the `Set-ScheduledJob` cmdlet to increase the number of saved instance results to</span></span>
15.

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 15
```

<span data-ttu-id="eb77c-157">Der folgende Befehl löscht den Ausführungs Verlauf und die aktuell gespeicherten Ergebnisse des geplanten Auftrags **processjob** .</span><span class="sxs-lookup"><span data-stu-id="eb77c-157">The following command deletes the execution history and the current saved results of the **ProcessJob** scheduled job.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

<span data-ttu-id="eb77c-158">Der folgende Befehl ruft die Werte der Eigenschaften "Name" und " **executionhistorylength** " aller geplanten Aufträge auf dem Computer ab und zeigt Sie in einer Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="eb77c-158">The following command gets the values of the name and **ExecutionHistoryLength** properties of all scheduled jobs on the computer and displays them in a table.</span></span>

```powershell
Get-ScheduledJob | 
  Format-Table -Property Name, ExecutionHistoryLength -AutoSize
```

## <a name="see-also"></a><span data-ttu-id="eb77c-159">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="eb77c-159">See also</span></span>

[<span data-ttu-id="eb77c-160">about_Scheduled_Jobs_Basics</span><span class="sxs-lookup"><span data-stu-id="eb77c-160">about_Scheduled_Jobs_Basics</span></span>](about_Scheduled_Jobs_Basics.md)

[<span data-ttu-id="eb77c-161">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="eb77c-161">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

[<span data-ttu-id="eb77c-162">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="eb77c-162">about_Scheduled_Jobs</span></span>](about_Scheduled_Jobs.md)

[<span data-ttu-id="eb77c-163">about_Splatting. MD</span><span class="sxs-lookup"><span data-stu-id="eb77c-163">about_Splatting.md</span></span>](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

<span data-ttu-id="eb77c-164">Cmdlets für das [psscheduledjob](xref:PSScheduledJob) -Modul</span><span class="sxs-lookup"><span data-stu-id="eb77c-164">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="eb77c-165">Aufgabenplanung</span><span class="sxs-lookup"><span data-stu-id="eb77c-165">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
