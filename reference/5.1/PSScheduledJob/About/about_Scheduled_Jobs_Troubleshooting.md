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
# <a name="about-scheduled-jobs-troubleshooting"></a><span data-ttu-id="96358-104">Informationen zur Problembehandlung bei geplanten Aufträgen</span><span class="sxs-lookup"><span data-stu-id="96358-104">About Scheduled Jobs Troubleshooting</span></span>

## <a name="short-description"></a><span data-ttu-id="96358-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96358-105">Short description</span></span>

<span data-ttu-id="96358-106">Erläutert, wie Probleme mit geplanten Aufträgen gelöst werden.</span><span class="sxs-lookup"><span data-stu-id="96358-106">Explains how to resolve problems with scheduled jobs</span></span>

## <a name="long-description"></a><span data-ttu-id="96358-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96358-107">Long description</span></span>

<span data-ttu-id="96358-108">In diesem Dokument werden einige der Probleme beschrieben, die bei der Verwendung der Features für geplante Aufträge von PowerShell auftreten können. es werden Lösungen für diese Probleme vorgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="96358-108">This document describes some of the problems that you might experience when using the scheduled job features of PowerShell and it suggests solutions to these problems.</span></span>

<span data-ttu-id="96358-109">Vor der Verwendung geplanter PowerShell-Aufträge finden Sie weitere Informationen unter [about_Scheduled_Jobs](about_Scheduled_Jobs.md) und den zugehörigen geplanten Aufträgen zu Themen.</span><span class="sxs-lookup"><span data-stu-id="96358-109">Before using PowerShell scheduled jobs, see [about_Scheduled_Jobs](about_Scheduled_Jobs.md) and the related scheduled jobs about topics.</span></span>

<span data-ttu-id="96358-110">Weitere Informationen zu den im **psscheduledjob** -Modul enthaltenen Cmdlets finden Sie unter [psscheduledjob](xref:PSScheduledJob).</span><span class="sxs-lookup"><span data-stu-id="96358-110">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

## <a name="cant-find-job-results"></a><span data-ttu-id="96358-111">Auftrags Ergebnisse können nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="96358-111">Can't find job results</span></span>

### <a name="basic-method-for-getting-job-results-in-powershell"></a><span data-ttu-id="96358-112">Grundlegende Methode zum erhalten von Auftrags Ergebnissen in PowerShell</span><span class="sxs-lookup"><span data-stu-id="96358-112">Basic method for getting job results in PowerShell</span></span>

<span data-ttu-id="96358-113">Wenn ein geplanter Auftrag ausgeführt wird, erstellt er eine Instanz des geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="96358-113">When a scheduled job runs, it creates an instance of the scheduled job.</span></span> <span data-ttu-id="96358-114">Verwenden Sie die Job-Cmdlets, um die Ergebnisse geplanter Auftrags Instanzen anzuzeigen, zu verwalten und zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="96358-114">To view, manage, and get the results of scheduled job instances, use the Job cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="96358-115">Damit die Job-Cmdlets für Instanzen geplanter Aufträge verwendet werden können, muss das **psscheduledjob** -Modul in die Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="96358-115">To use the Job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="96358-116">Um das **psscheduledjob** -Modul zu importieren, geben Sie `Import-Module PSScheduledJob` ein beliebiges geplanter Job-Cmdlet ein, z `Get-ScheduledJob` . b..</span><span class="sxs-lookup"><span data-stu-id="96358-116">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

<span data-ttu-id="96358-117">Verwenden Sie das-Cmdlet, um eine Liste aller Instanzen eines geplanten Auftrags zu erhalten `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="96358-117">To get a list of all instances of a scheduled job, use the `Get-Job` cmdlet.</span></span>

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

<span data-ttu-id="96358-118">Das- `Get-Job` Cmdlet sendet **processjob** -Objekte über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="96358-118">The `Get-Job` cmdlet sends **ProcessJob** objects down the pipeline.</span></span> <span data-ttu-id="96358-119">Mit dem- `Format-Table` Cmdlet werden die Eigenschaften " **Name**", " **ID**" und " **psbegintime** " einer geplanten Auftrags Instanz in einer Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="96358-119">The `Format-Table` cmdlet displays the **Name**, **ID**, and **PSBeginTime** properties of a scheduled job instance in a table.</span></span>

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

<span data-ttu-id="96358-120">Verwenden Sie das-Cmdlet, um die Ergebnisse einer Instanz eines geplanten Auftrags zu erhalten `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="96358-120">To get the results of an instance of a scheduled job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="96358-121">Der folgende Befehl ruft die Ergebnisse der neuesten Instanz von processjob (ID = 50) ab.</span><span class="sxs-lookup"><span data-stu-id="96358-121">The following command gets the results of the newest instance of the ProcessJob (ID = 50).</span></span>

```powershell
Receive-Job -ID 50
```

### <a name="basic-method-for-finding-job-results-on-disk"></a><span data-ttu-id="96358-122">Grundlegende Methode zum Ermitteln von Auftrags Ergebnissen auf einem Datenträger</span><span class="sxs-lookup"><span data-stu-id="96358-122">Basic method for finding job results on disk</span></span>

<span data-ttu-id="96358-123">Verwenden Sie zum Verwalten geplanter Aufträge die Job-Cmdlets, z `Get-Job` `Receive-Job` . b. und.</span><span class="sxs-lookup"><span data-stu-id="96358-123">To manage scheduled jobs, use the job cmdlets, such as `Get-Job` and `Receive-Job`.</span></span>

<span data-ttu-id="96358-124">Wenn `Get-Job` die Auftrags Instanz nicht abruft oder `Receive-Job` die Auftrags Ergebnisse nicht erhalten, können Sie die Ausführungs Verlaufs Dateien für den Auftrag auf dem Datenträger durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="96358-124">If `Get-Job` does not get the job instance or `Receive-Job` does not get the job results, you can search the execution history files for the job on disk.</span></span>
<span data-ttu-id="96358-125">Der Ausführungs Verlauf enthält einen Datensatz aller ausgelösten Auftrags Instanzen.</span><span class="sxs-lookup"><span data-stu-id="96358-125">The execution history contains a record of all triggered job instances.</span></span>

<span data-ttu-id="96358-126">Vergewissern Sie sich, dass im Verzeichnis für einen geplanten Auftrag ein Verzeichnis mit dem Namen Timestamp im folgenden Pfad vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="96358-126">Verify that there is a timestamp-named directory in the directory for a scheduled job in the following path:</span></span>

`$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJob\<ScheduledJobName>\Output`

<span data-ttu-id="96358-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="96358-127">For example:</span></span>

`C:\Users<UserName>\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJob\<ScheduledJobName>\Output`

<span data-ttu-id="96358-128">Beispielsweise ruft das `Get-ChildItem` Cmdlet den Ausführungs Verlauf auf dem Datenträger des geplanten Auftrags **processjob** ab.</span><span class="sxs-lookup"><span data-stu-id="96358-128">For example, the `Get-ChildItem` cmdlet gets the on-disk execution history of the **ProcessJob** scheduled job.</span></span>

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

<span data-ttu-id="96358-129">Jedes Zeitstempel benannte Verzeichnis stellt eine Auftrags Instanz dar.</span><span class="sxs-lookup"><span data-stu-id="96358-129">Each timestamp-named directory represents a job instance.</span></span> <span data-ttu-id="96358-130">Die Ergebnisse der einzelnen Auftrags Instanzen werden in einer **Results.xml** -Datei im Verzeichnis mit dem Namen Timestamp gespeichert.</span><span class="sxs-lookup"><span data-stu-id="96358-130">The results of each job instance are saved in a **Results.xml** file in the timestamp-named directory.</span></span>

<span data-ttu-id="96358-131">Beispielsweise ruft der folgende Befehl die **Results.xml** Dateien für jede gespeicherte Instanz des geplanten Auftrags **processjob** ab.</span><span class="sxs-lookup"><span data-stu-id="96358-131">For example, the following command gets the **Results.xml** files for every saved instance of the **ProcessJob** scheduled job.</span></span> <span data-ttu-id="96358-132">Wenn die **Results.xml** Datei fehlt, kann PowerShell die Auftrags Ergebnisse nicht zurückgeben oder anzeigen.</span><span class="sxs-lookup"><span data-stu-id="96358-132">If the **Results.xml** file is missing, PowerShell cannot return or display the job results.</span></span>

```powershell
$Path = '$home\AppData\Local\Microsoft\Windows\PowerShell'
$Path += '\ScheduledJobs\ProcessJob\Output\*\Results.xml'
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\Appdata\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output
```

<span data-ttu-id="96358-133">Das Auftrags-Cmdlet ist möglicherweise nicht in der Lage, geplante Auftrags Instanzen oder Ihre Ergebnisse abzurufen, da das **psscheduledjob** -Modul nicht in die Sitzung importiert wird.</span><span class="sxs-lookup"><span data-stu-id="96358-133">The job cmdlet might not be able to get scheduled job instances or their results because the **PSScheduledJob** module is not imported into the session.</span></span>

> [!NOTE]
> <span data-ttu-id="96358-134">Vergewissern Sie sich vor der Verwendung eines Auftrags-Cmdlets für geplante Auftrags Instanzen, dass das **psscheduledjob** -Modul in der Sitzung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="96358-134">Before using a job cmdlet on scheduled job instances, verify that the **PSScheduledJob** module is included in the session.</span></span> <span data-ttu-id="96358-135">Ohne das **psscheduledjob** -Modul können die Auftrags-Cmdlets keine geplanten Auftrags Instanzen oder Ihre Ergebnisse erhalten.</span><span class="sxs-lookup"><span data-stu-id="96358-135">Without the **PSScheduledJob** module, the job cmdlets cannot get scheduled job instances or their results.</span></span>

<span data-ttu-id="96358-136">So importieren Sie das **psscheduledjob** -Modul:</span><span class="sxs-lookup"><span data-stu-id="96358-136">To import the **PSScheduledJob** module:</span></span>

```powershell
Import-Module PSScheduledJob
```

### <a name="receive-job-cmdlet-might-already-have-returned-the-results"></a><span data-ttu-id="96358-137">Receive-Job Cmdlet hat möglicherweise bereits die Ergebnisse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="96358-137">Receive-Job cmdlet might already have returned the results</span></span>

<span data-ttu-id="96358-138">Wenn `Receive-Job` keine Ergebnisse der Auftrags Instanz zurückgibt, kann dies daran liegen, `Receive-Job` dass ein Befehl für diese Auftrags Instanz in der aktuellen Sitzung ohne den **Keep** -Parameter ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="96358-138">If `Receive-Job` does not return job instance results, it might be because a `Receive-Job` command has been run for that job instance in the current session without the **Keep** parameter.</span></span>

<span data-ttu-id="96358-139">Wenn Sie `Receive-Job` ohne den **Keep** -Parameter verwenden, `Receive-Job` gibt die Auftrags Ergebnisse zurück und legt die **hasmoredata** -Eigenschaft der Auftrags Instanz auf **false** fest.</span><span class="sxs-lookup"><span data-stu-id="96358-139">When you use `Receive-Job` without the **Keep** parameter, `Receive-Job` returns the job results and sets the job instance's **HasMoreData** property to **False**.</span></span> <span data-ttu-id="96358-140">Der Wert **false** bedeutet, dass `Receive-Job` die Ergebnisse des Auftrags zurückgegeben hat und die Instanz keine weiteren Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="96358-140">The **False** value means that `Receive-Job` returned the job's results and the instance has no more results to return.</span></span> <span data-ttu-id="96358-141">Diese Einstellung ist für Standard-Hintergrund Aufträge geeignet, jedoch nicht für Instanzen geplanter Aufträge, die auf dem Datenträger gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="96358-141">This setting is appropriate for standard background jobs, but not for instances of scheduled jobs, which are saved to disk.</span></span>

<span data-ttu-id="96358-142">Um die Ergebnisse der Auftrags Instanz erneut zu erhalten, starten Sie eine neue PowerShell-Sitzung, indem Sie eingeben `PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="96358-142">To get the job instance results again, start a new PowerShell session by typing `PowerShell`.</span></span> <span data-ttu-id="96358-143">Importieren Sie das **psscheduledjob** -Modul, und `Receive-Job` Wiederholen Sie den Befehl.</span><span class="sxs-lookup"><span data-stu-id="96358-143">Import the **PSScheduledJob** module, and try the `Receive-Job` command again.</span></span>

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

### <a name="using-keep-parameter-to-get-results-more-than-one-time-in-a-session"></a><span data-ttu-id="96358-144">Verwenden von Keep-Parametern, um Ergebnisse mehr als einmal in einer Sitzung zu erhalten</span><span class="sxs-lookup"><span data-stu-id="96358-144">Using Keep parameter to get results more than one time in a session</span></span>

<span data-ttu-id="96358-145">Um das Ergebnis einer Auftrags Instanz mehr als einmal in einer Sitzung zu erhalten, verwenden Sie den **Keep** -Parameter des `Receive-Job` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="96358-145">To get the result of a job instance more than one time in a session, use the **Keep** parameter of the `Receive-Job` cmdlet.</span></span>

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

### <a name="the-scheduled-job-might-be-corrupted"></a><span data-ttu-id="96358-146">Der geplante Auftrag ist möglicherweise beschädigt.</span><span class="sxs-lookup"><span data-stu-id="96358-146">The scheduled job might be corrupted</span></span>

<span data-ttu-id="96358-147">Wenn ein geplanter Auftrag beschädigt wird, löscht PowerShell den beschädigten geplanten Auftrag und seine Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="96358-147">If a scheduled job becomes corrupted, PowerShell deletes the corrupted scheduled job and its results.</span></span> <span data-ttu-id="96358-148">Die Ergebnisse eines beschädigten geplanten Auftrags können nicht wieder hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="96358-148">You cannot recover the results of a corrupted scheduled job.</span></span>

<span data-ttu-id="96358-149">Verwenden Sie das-Cmdlet, um zu bestimmen, ob ein geplanter Auftrag noch vorhanden ist `Get-ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="96358-149">To determine if a scheduled job still exists, use the `Get-ScheduledJob` cmdlet.</span></span>

```powershell
Get-ScheduledJob
```

### <a name="the-number-of-results-might-have-exceeded-the-executionhistorylength"></a><span data-ttu-id="96358-150">Die Anzahl der Ergebnisse hat möglicherweise die executionhistorylength überschritten.</span><span class="sxs-lookup"><span data-stu-id="96358-150">The number of results might have exceeded the ExecutionHistoryLength</span></span>

<span data-ttu-id="96358-151">Die **executionhistorylength** -Eigenschaft eines geplanten Auftrags legt fest, wie viele Auftrags Instanzen und ihre Ergebnisse auf dem Datenträger gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="96358-151">The **ExecutionHistoryLength** property of a scheduled job determines how many job instances, and their results, are saved to disk.</span></span> <span data-ttu-id="96358-152">Der Standardwert ist 32.</span><span class="sxs-lookup"><span data-stu-id="96358-152">The default value is 32.</span></span>
<span data-ttu-id="96358-153">Wenn die Anzahl der Instanzen eines geplanten Auftrags diesen Wert überschreitet, löscht PowerShell die älteste Auftrags Instanz, um Platz für jede neue Auftrags Instanz zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="96358-153">When the number of instances of a scheduled job exceeds this value, PowerShell deletes the oldest job instance to make room for each new job instance.</span></span>

<span data-ttu-id="96358-154">Um den Wert der **executionhistorylength** -Eigenschaft eines geplanten Auftrags zu erhalten, verwenden Sie das folgende Befehls Format:</span><span class="sxs-lookup"><span data-stu-id="96358-154">To get the value of the **ExecutionHistoryLength** property of a scheduled job, use the following command format:</span></span>

```powershell
(Get-ScheduledJob <JobName>).ExecutionHistoryLength
```

<span data-ttu-id="96358-155">Mit dem folgenden Befehl wird z. b. der Wert der **executionhistorylength** -Eigenschaft des geplanten Auftrags **processjob** abgerufen.</span><span class="sxs-lookup"><span data-stu-id="96358-155">For example, the following command gets the value of the **ExecutionHistoryLength** property of the **ProcessJob** scheduled job.</span></span>

```powershell
(Get-ScheduledJob ProcessJob).ExecutionHistoryLength
```

<span data-ttu-id="96358-156">Um den Wert der **executionhistorylength** -Eigenschaft festzulegen oder zu ändern, verwenden Sie den **maxresultcount** -Parameter der `Register-ScheduledJob` `Set-ScheduledJob` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="96358-156">To set or change the value of the **ExecutionHistoryLength** property, use the **MaxResultCount** parameter of the `Register-ScheduledJob` and `Set-ScheduledJob` cmdlets.</span></span>

<span data-ttu-id="96358-157">Der folgende Befehl erhöht den Wert der **executionhistorylength** -Eigenschaft auf 50.</span><span class="sxs-lookup"><span data-stu-id="96358-157">The following command increases the value of the **ExecutionHistoryLength** property to 50.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 50
```

### <a name="the-job-instance-results-might-have-been-deleted"></a><span data-ttu-id="96358-158">Die Ergebnisse der Auftrags Instanz wurden möglicherweise gelöscht.</span><span class="sxs-lookup"><span data-stu-id="96358-158">The job instance results might have been deleted</span></span>

<span data-ttu-id="96358-159">Der **clearexecutionhistory** -Parameter des `Set-ScheduledJob` Cmdlets löscht den Ausführungs Verlauf eines Auftrags.</span><span class="sxs-lookup"><span data-stu-id="96358-159">The **ClearExecutionHistory** parameter of the `Set-ScheduledJob` cmdlet deletes the execution history of a job.</span></span> <span data-ttu-id="96358-160">Sie können diese Funktion verwenden, um Speicherplatz freizugeben oder Ergebnisse zu löschen, die nicht benötigt oder bereits verwendet, analysiert oder an einem anderen Speicherort gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="96358-160">You can use this feature to free up disk space or delete results that are not needed, or already used, analyzed or saved in a different location.</span></span>

<span data-ttu-id="96358-161">Um den Ausführungs Verlauf eines geplanten Auftrags zu löschen, verwenden Sie den **clearexecutionhistory** -Parameter des geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="96358-161">To delete the execution history of a scheduled job, use the **ClearExecutionHistory** parameter of the scheduled job.</span></span>

<span data-ttu-id="96358-162">Der folgende Befehl löscht den Ausführungs Verlauf des geplanten Auftrags **processjob** .</span><span class="sxs-lookup"><span data-stu-id="96358-162">The following command deletes the execution history of the **ProcessJob** scheduled job.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

<span data-ttu-id="96358-163">Außerdem löscht das `Remove-Job` Cmdlet Auftrags Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="96358-163">Also, the `Remove-Job` cmdlet deletes job results.</span></span> <span data-ttu-id="96358-164">Wenn Sie verwenden, `Remove-Job` um einen geplanten Auftrag zu löschen, werden alle Instanzen des Auftrags auf dem Datenträger gelöscht, einschließlich des Ausführungs Verlaufs und aller Auftrags Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="96358-164">When you use `Remove-Job` to delete a scheduled job, it deletes all instances of the job on disk, including the execution history and all job results.</span></span>

### <a name="jobs-started-by-using-the-start-job-cmdlet-are-not-saved-to-disk"></a><span data-ttu-id="96358-165">Mit dem Cmdlet "Start-Job" gestartete Aufträge werden nicht auf dem Datenträger gespeichert.</span><span class="sxs-lookup"><span data-stu-id="96358-165">Jobs started by using the Start-Job cmdlet are not saved to disk</span></span>

<span data-ttu-id="96358-166">Wenn Sie verwenden, `Start-Job` um einen geplanten Auftrag zu starten, startet anstelle eines Auftrags Auslösers `Start-Job` einen Standard Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="96358-166">When you use `Start-Job` to start a scheduled job, instead of using a job trigger, `Start-Job` starts a standard background job.</span></span> <span data-ttu-id="96358-167">Der Hintergrund Auftrag und seine Ergebnisse werden nicht im Ausführungs Verlauf des Auftrags auf dem Datenträger gespeichert.</span><span class="sxs-lookup"><span data-stu-id="96358-167">The background job and its results are not stored in the execution history of the job on disk.</span></span>

<span data-ttu-id="96358-168">Sie können das `Get-Job` Cmdlet zum Abrufen des Auftrags und des `Receive-Job` Cmdlets verwenden, um die Auftrags Ergebnisse zu erhalten. die Ergebnisse sind jedoch nur verfügbar, bis Sie Sie erhalten, es sei denn, Sie verwenden den Keep-Parameter des `Receive-Job` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="96358-168">You can use the `Get-Job` cmdlet to get the job and the `Receive-Job` cmdlet to get the job results, but the results are available only until you receive them, unless you use the Keep parameter of the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="96358-169">Außerdem sind Hintergrund Aufträge und ihre Ergebnisse Sitzungs spezifisch. Sie sind nur in der Sitzung vorhanden, in der Sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="96358-169">Also, background jobs and their results are session-specific; they exist only in the session in which they are created.</span></span> <span data-ttu-id="96358-170">Wenn Sie den Auftrag mit löschen `Remove-Job` , schließen Sie die Sitzung, oder schließen Sie PowerShell, sodass die Auftrags Instanz und ihre Ergebnisse gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="96358-170">If you delete the job with `Remove-Job`, close the session or close PowerShell, the job instance and its results are deleted.</span></span>

## <a name="scheduled-job-doesnt-run"></a><span data-ttu-id="96358-171">Der geplante Auftrag wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="96358-171">Scheduled job doesn't run</span></span>

<span data-ttu-id="96358-172">Geplante Aufträge werden nicht automatisch ausgeführt, wenn der Auftrag ausgelöst oder der geplante Auftrag deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="96358-172">Scheduled jobs don't run automatically if the job triggers or the scheduled job are disabled.</span></span>

<span data-ttu-id="96358-173">Verwenden Sie das `Get-ScheduledJob` Cmdlet, um den geplanten Auftrag zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="96358-173">Use the `Get-ScheduledJob` cmdlet to get the scheduled job.</span></span> <span data-ttu-id="96358-174">Vergewissern Sie sich, dass der Wert der **aktivierten** Eigenschaft des geplanten Auftrags " **true**" lautet.</span><span class="sxs-lookup"><span data-stu-id="96358-174">Verify that the value of the **Enabled** property of the scheduled job is **True**.</span></span>

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

<span data-ttu-id="96358-175">Verwenden Sie das `Get-JobTrigger` Cmdlet, um die Auftrags Trigger des geplanten Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="96358-175">Use the `Get-JobTrigger` cmdlet to get the job triggers of the scheduled job.</span></span>
<span data-ttu-id="96358-176">Vergewissern Sie sich, dass der Wert der **aktivierten** Eigenschaft des Auftrags Auslösers " **true**" ist.</span><span class="sxs-lookup"><span data-stu-id="96358-176">Verify that the value of the **Enabled** property of the job trigger is **True**.</span></span>

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

### <a name="scheduled-jobs-dont-run-automatically-if-job-triggers-are-invalid"></a><span data-ttu-id="96358-177">Geplante Aufträge werden nicht automatisch ausgeführt, wenn Auftrags Trigger ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="96358-177">Scheduled jobs don't run automatically if job triggers are invalid</span></span>

<span data-ttu-id="96358-178">Beispielsweise kann ein Auftrags Fehler ein Datum in der Vergangenheit oder ein Datum angeben, das nicht eintritt, z. b. den 5. Montag des Monats.</span><span class="sxs-lookup"><span data-stu-id="96358-178">For example, a job trigger might specify a date in the past or a date that does not occur, such as the 5th Monday of the month.</span></span>

<span data-ttu-id="96358-179">Geplante Aufträge werden nicht automatisch ausgeführt, wenn die Bedingungen des Auftrags Auslösers oder der Auftrags Optionen nicht erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="96358-179">Scheduled jobs do not run automatically if the conditions of the job trigger or the job options are not satisfied.</span></span>

<span data-ttu-id="96358-180">Beispielsweise wird ein geplanter Auftrag, der nur ausgeführt wird, wenn sich ein bestimmter Benutzer am Computer anmeldet, nicht ausgeführt, wenn sich der Benutzer nicht anmeldet oder nur eine Remote Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="96358-180">For example, a scheduled job that runs only when a particular user logs on to the computer will not run if that user does not log on or only connects remotely.</span></span>

<span data-ttu-id="96358-181">Überprüfen Sie die Optionen des geplanten Auftrags, und stellen Sie sicher, dass Sie erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="96358-181">Examine the options of the scheduled job and make sure that they are satisfied.</span></span>
<span data-ttu-id="96358-182">Beispielsweise wird ein geplanter Auftrag, der erfordert, dass sich der Computer im Leerlauf befindet oder eine Netzwerkverbindung erfordert oder eine lange **idleduration** -oder eine kurze **IdleTimeout** -Eigenschaft aufweist, nie ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="96358-182">For example, a scheduled job that requires that the computer be idle or requires a network connection, or has a long **IdleDuration** or a brief **IdleTimeout** might never run.</span></span>

<span data-ttu-id="96358-183">Verwenden `Get-ScheduledJobOption` Sie das Cmdlet, um die Auftrags Optionen und deren Werte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="96358-183">Use the `Get-ScheduledJobOption` cmdlet to examine the job options and their values.</span></span>

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

<span data-ttu-id="96358-184">Beschreibungen der Optionen für geplante Aufträge finden Sie unter [New-scheduledjoboption](xref:PSScheduledJob.New-ScheduledJobOption).</span><span class="sxs-lookup"><span data-stu-id="96358-184">For descriptions of the scheduled job options, see [New-ScheduledJobOption](xref:PSScheduledJob.New-ScheduledJobOption).</span></span>

### <a name="the-scheduled-job-instance-might-have-failed"></a><span data-ttu-id="96358-185">Bei der geplanten Auftrags Instanz ist möglicherweise ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="96358-185">The scheduled job instance might have failed</span></span>

<span data-ttu-id="96358-186">Wenn ein Befehl für einen geplanten Auftrag fehlschlägt, meldet PowerShell ihn sofort, indem er eine Fehlermeldung erzeugt.</span><span class="sxs-lookup"><span data-stu-id="96358-186">If a scheduled job command fails, PowerShell reports it immediately by generating an error message.</span></span> <span data-ttu-id="96358-187">Wenn der Auftrag jedoch fehlschlägt, wenn Taskplaner versucht, ihn auszuführen, ist der Fehler für PowerShell nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="96358-187">However, if the job fails when Task Scheduler tries to run it, the error is not available to PowerShell.</span></span>

<span data-ttu-id="96358-188">Verwenden Sie die folgenden Methoden, um Auftrags Fehler zu erkennen und zu beheben:</span><span class="sxs-lookup"><span data-stu-id="96358-188">Use the following methods to detect and correct job failures:</span></span>

<span data-ttu-id="96358-189">Überprüfen Sie das Ereignisprotokoll Taskplaner auf Fehler.</span><span class="sxs-lookup"><span data-stu-id="96358-189">Check the Task Scheduler event log for errors.</span></span> <span data-ttu-id="96358-190">Um das Protokoll zu überprüfen, verwenden Sie Ereignisanzeige oder einen PowerShell-Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="96358-190">To check the log, use Event Viewer or a PowerShell command such as the following:</span></span>

```powershell
Get-WinEvent -LogName Microsoft-Windows-TaskScheduler/Operational |
 Where {$_.Message -like "fail"}
```

<span data-ttu-id="96358-191">Überprüfen Sie den Auftragsdaten Satz in Taskplaner.</span><span class="sxs-lookup"><span data-stu-id="96358-191">Check the job record in Task Scheduler.</span></span> <span data-ttu-id="96358-192">Geplante PowerShell-Aufträge werden im folgenden geplanten Aufgaben Ordner gespeichert:</span><span class="sxs-lookup"><span data-stu-id="96358-192">PowerShell scheduled jobs are stored in the following Task Scheduled folder:</span></span>

`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`

### <a name="the-scheduled-job-might-not-run-because-of-insufficient-permission"></a><span data-ttu-id="96358-193">Der geplante Auftrag kann aufgrund unzureichender Berechtigungen nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="96358-193">The scheduled job might not run because of insufficient permission</span></span>

<span data-ttu-id="96358-194">Geplante Aufträge werden mit den Berechtigungen des Benutzers ausgeführt, der den Auftrag erstellt hat, oder mit den Berechtigungen des Benutzers, der durch den **Credential** -Parameter im `Register-ScheduledJob` Befehl oder angegeben wird `Set-ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="96358-194">Scheduled jobs run with the permissions of the user who created the job or the permissions of the user who is specified by the **Credential** parameter in the `Register-ScheduledJob` or `Set-ScheduledJob` command.</span></span>

<span data-ttu-id="96358-195">Wenn dieser Benutzer nicht über die Berechtigung zum Ausführen der Befehle oder Skripts verfügt, schlägt der Auftrag fehl.</span><span class="sxs-lookup"><span data-stu-id="96358-195">If that user does not have permission to run the commands or scripts, the job fails.</span></span>

## <a name="cant-get-scheduled-job-or-scheduled-job-is-corrupted"></a><span data-ttu-id="96358-196">Der geplante Auftrag konnte nicht oder der geplante Auftrag beschädigt werden.</span><span class="sxs-lookup"><span data-stu-id="96358-196">Can't get scheduled job or scheduled job is corrupted</span></span>

<span data-ttu-id="96358-197">In seltenen Fällen können geplante Aufträge beschädigt werden oder interne Widersprüche enthalten, die nicht aufgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="96358-197">On rare occasions, scheduled jobs can become corrupted or contain internal contradictions that cannot be resolved.</span></span> <span data-ttu-id="96358-198">Dies geschieht in der Regel, wenn die XML-Dateien für den geplanten Auftrag manuell bearbeitet werden, was zu einem ungültigen XML-Code führt.</span><span class="sxs-lookup"><span data-stu-id="96358-198">Typically, this happens when the XML files for the scheduled job are manually edited, resulting in invalid XML.</span></span>

<span data-ttu-id="96358-199">Wenn ein geplanter Auftrag beschädigt ist, versucht PowerShell, den geplanten Auftrag, seinen Ausführungs Verlauf und seine Ergebnisse von der Festplatte zu löschen.</span><span class="sxs-lookup"><span data-stu-id="96358-199">When a scheduled job is corrupted, PowerShell attempts to delete the scheduled job, its execution history, and its results from disk.</span></span>

<span data-ttu-id="96358-200">Wenn der geplante Auftrag nicht entfernt werden kann, erhalten Sie jedes Mal, wenn Sie das Cmdlet ausführen, eine Fehlermeldung zu einem fehlerhaften Auftrag `Get-ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="96358-200">If it cannot remove the scheduled job, you will get a corrupted job error message each time you run the `Get-ScheduledJob` cmdlet.</span></span>

<span data-ttu-id="96358-201">Verwenden Sie zum Entfernen eines beschädigten geplanten Auftrags eine der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="96358-201">To remove a corrupted scheduled job, use either one of the following methods:</span></span>

<span data-ttu-id="96358-202">Löschen Sie das `<ScheduledJobName>` Verzeichnis für den geplanten Auftrag.</span><span class="sxs-lookup"><span data-stu-id="96358-202">Delete the `<ScheduledJobName>` directory for the scheduled job.</span></span> <span data-ttu-id="96358-203">Löschen Sie das **ScheduledJob** -Verzeichnis nicht.</span><span class="sxs-lookup"><span data-stu-id="96358-203">Don't delete the **ScheduledJob** directory.</span></span>

<span data-ttu-id="96358-204">Der Speicherort des Verzeichnisses:</span><span class="sxs-lookup"><span data-stu-id="96358-204">The directory's location:</span></span>

`$env:UserProfile\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>`

<span data-ttu-id="96358-205">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="96358-205">For example:</span></span>

`C:\Users<UserName>\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>.`

<span data-ttu-id="96358-206">Verwenden Sie Taskplaner, um den geplanten Auftrag zu löschen.</span><span class="sxs-lookup"><span data-stu-id="96358-206">Use Task Scheduler to delete the scheduled job.</span></span> <span data-ttu-id="96358-207">Geplante PowerShell-Tasks werden im folgenden Taskplaner Pfad angezeigt:</span><span class="sxs-lookup"><span data-stu-id="96358-207">PowerShell scheduled tasks appear in the following Task Scheduler path:</span></span>

`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>`

## <a name="job-cmdlets-cant-consistently-find-scheduled-jobs"></a><span data-ttu-id="96358-208">Auftrags-Cmdlets können geplante Aufträge nicht konsistent finden.</span><span class="sxs-lookup"><span data-stu-id="96358-208">Job cmdlets can't consistently find scheduled jobs</span></span>

<span data-ttu-id="96358-209">Wenn das **psscheduledjob** -Modul nicht in der aktuellen Sitzung enthalten ist, können die Auftrags-Cmdlets keine geplanten Aufträge erhalten, Sie starten oder Ergebnisse erhalten.</span><span class="sxs-lookup"><span data-stu-id="96358-209">When the **PSScheduledJob** module isn't in the current session, the job cmdlets cannot get scheduled jobs, start them, or get their results.</span></span>

<span data-ttu-id="96358-210">Um das **psscheduledjob** -Modul zu importieren, geben `Import-Module PSScheduledJob` Sie ein Cmdlet im Modul ein, oder führen Sie es aus, z `Get-ScheduledJob` . b. das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="96358-210">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or run or get any cmdlet in the module, such as the `Get-ScheduledJob` cmdlet.</span></span>
<span data-ttu-id="96358-211">Ab PowerShell 3,0 werden Module automatisch importiert, wenn Sie ein beliebiges Cmdlet im Modul erhalten oder verwenden.</span><span class="sxs-lookup"><span data-stu-id="96358-211">Beginning in PowerShell 3.0, modules are imported automatically when you get or use any cmdlet in the module.</span></span>

<span data-ttu-id="96358-212">Wenn das **psscheduledjob** -Modul nicht in der aktuellen Sitzung enthalten ist, ist die folgende Befehlssequenz möglich.</span><span class="sxs-lookup"><span data-stu-id="96358-212">When the **PSScheduledJob** module isn't in the current session, the following command sequence is possible.</span></span>

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

<span data-ttu-id="96358-213">Dieses Verhalten tritt auf, da der `Get-ScheduledJob` Befehl automatisch das **psscheduledjob** -Modul importiert und dann den Befehl ausführt.</span><span class="sxs-lookup"><span data-stu-id="96358-213">This behavior occurs because the `Get-ScheduledJob` command automatically imports the **PSScheduledJob** module, and then runs the command.</span></span>

## <a name="see-also"></a><span data-ttu-id="96358-214">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96358-214">See also</span></span>

[<span data-ttu-id="96358-215">about_Scheduled_Jobs_Basics</span><span class="sxs-lookup"><span data-stu-id="96358-215">about_Scheduled_Jobs_Basics</span></span>](about_Scheduled_Jobs_Basics.md)

[<span data-ttu-id="96358-216">about_Scheduled_Jobs_Advanced</span><span class="sxs-lookup"><span data-stu-id="96358-216">about_Scheduled_Jobs_Advanced</span></span>](about_Scheduled_Jobs_Advanced.md)

[<span data-ttu-id="96358-217">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="96358-217">about_Scheduled_Jobs</span></span>](about_Scheduled_Jobs.md)

<span data-ttu-id="96358-218">Cmdlets für das [psscheduledjob](xref:PSScheduledJob) -Modul</span><span class="sxs-lookup"><span data-stu-id="96358-218">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="96358-219">Aufgabenplanung</span><span class="sxs-lookup"><span data-stu-id="96358-219">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
