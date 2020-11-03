---
description: Beschreibt geplante Aufträge und erläutert, wie geplante Aufträge in PowerShell und in Taskplaner verwendet und verwaltet werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs
ms.openlocfilehash: 4d4e86957a584bb4deb47cadcd8588c1236455ac
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221940"
---
# <a name="about-scheduled-jobs"></a><span data-ttu-id="59b72-104">Informationen zu geplanten Aufträgen</span><span class="sxs-lookup"><span data-stu-id="59b72-104">About Scheduled Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="59b72-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59b72-105">Short description</span></span>

<span data-ttu-id="59b72-106">Beschreibt geplante Aufträge und erläutert, wie geplante Aufträge in PowerShell und in Taskplaner verwendet und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="59b72-106">Describes scheduled jobs and explains how to use and manage scheduled jobs in PowerShell and in Task Scheduler.</span></span>

## <a name="long-description"></a><span data-ttu-id="59b72-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59b72-107">Long description</span></span>

<span data-ttu-id="59b72-108">Geplante PowerShell-Aufträge sind eine nützliche Hybridlösung von PowerShell-Hintergrund Aufträgen und Taskplaner Tasks.</span><span class="sxs-lookup"><span data-stu-id="59b72-108">PowerShell scheduled jobs are a useful hybrid of PowerShell background jobs and Task Scheduler tasks.</span></span>

<span data-ttu-id="59b72-109">Wie PowerShell-Hintergrund Aufträge werden geplante Aufträge asynchron im Hintergrund ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="59b72-109">Like PowerShell background jobs, scheduled jobs run asynchronously in the background.</span></span> <span data-ttu-id="59b72-110">Instanzen geplanter Aufträge, die ausgeführt wurden, können mit den Job-Cmdlets verwaltet werden, z `Start-Job` `Get-Job` . b.,, `Stop-Job` und `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="59b72-110">Instances of scheduled jobs that have run can be managed by using the job cmdlets, such as `Start-Job`, `Get-Job`, `Stop-Job`, and `Receive-Job`.</span></span>

<span data-ttu-id="59b72-111">Wie Taskplaner Tasks werden geplante Aufträge auf dem Datenträger gespeichert.</span><span class="sxs-lookup"><span data-stu-id="59b72-111">Like Task Scheduler tasks, scheduled jobs are saved to disk.</span></span> <span data-ttu-id="59b72-112">Sie können die Aufträge in Taskplaner anzeigen und verwalten, Sie bei Bedarf aktivieren und deaktivieren, Sie ausführen oder als Vorlagen verwenden, einen einmaligen oder wiederkehrenden Zeitplan zum Starten der Aufträge einrichten oder Bedingungen festlegen, unter denen die Aufträge gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="59b72-112">You can view and manage the jobs in Task Scheduler, enable and disable them as needed, run them or use them as templates, establish a one-time or recurring schedules for starting the jobs, or set conditions under which the jobs start.</span></span>

<span data-ttu-id="59b72-113">Außerdem werden die Ergebnisse geplanter Auftrags Instanzen in einem leicht zugänglichen Format auf dem Datenträger gespeichert, und es wird ein ausgelaufendes Protokoll der Auftrags Ausgabe bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="59b72-113">In addition, the results of scheduled job instances are saved to disk in an easily accessible format, providing a running log of job output.</span></span> <span data-ttu-id="59b72-114">Geplante Aufträge verfügen über einen angepassten Satz von Cmdlets für deren Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="59b72-114">Scheduled jobs come with a customized set of cmdlets for managing them.</span></span> <span data-ttu-id="59b72-115">Mit den-Cmdlets können Sie geplante Aufträge, Auftrags Trigger und Auftrags Optionen erstellen, bearbeiten, verwalten, deaktivieren und erneut aktivieren.</span><span class="sxs-lookup"><span data-stu-id="59b72-115">The cmdlets let you create, edit, manage, disable, and re-enable scheduled jobs, job triggers and job options.</span></span>

<span data-ttu-id="59b72-116">Diese umfassende und flexible Reihe von Tools machen geplante Aufträge zu einer wesentlichen Komponente vieler professioneller PowerShell-IT-Lösungen.</span><span class="sxs-lookup"><span data-stu-id="59b72-116">This comprehensive and flexible set of tools make scheduled jobs an essential component of many professional PowerShell IT solutions.</span></span>

<span data-ttu-id="59b72-117">Die Cmdlets für geplante Aufträge sind im **psscheduledjob** -Modul enthalten, das mit PowerShell installiert wird.</span><span class="sxs-lookup"><span data-stu-id="59b72-117">The scheduled job cmdlets are included in the **PSScheduledJob** module that is installed with PowerShell.</span></span> <span data-ttu-id="59b72-118">Dieses Modul wurde in PowerShell 3,0 eingeführt und funktioniert in PowerShell 3,0 und höheren Versionen von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59b72-118">This module was introduced in PowerShell 3.0 and works in PowerShell 3.0 and later versions of PowerShell.</span></span> <span data-ttu-id="59b72-119">Weitere Informationen zu den im **psscheduledjob** -Modul enthaltenen Cmdlets finden Sie unter [psscheduledjob](xref:PSScheduledJob).</span><span class="sxs-lookup"><span data-stu-id="59b72-119">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

<span data-ttu-id="59b72-120">Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="59b72-120">For more information about PowerShell background jobs, see [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

<span data-ttu-id="59b72-121">Weitere Informationen zu Taskplaner finden Sie unter [Taskplaner](/windows/desktop/TaskSchd/task-scheduler-reference).</span><span class="sxs-lookup"><span data-stu-id="59b72-121">For more information about Task Scheduler, see [Task Scheduler](/windows/desktop/TaskSchd/task-scheduler-reference).</span></span>

> [!NOTE]
> <span data-ttu-id="59b72-122">Sie können geplante PowerShell-Aufträge in Taskplaner anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="59b72-122">You can view and manage PowerShell scheduled jobs in Task Scheduler.</span></span> <span data-ttu-id="59b72-123">Die PowerShell-Aufträge und-Cmdlets für geplante Aufträge funktionieren nur für geplante Aufträge, die in PowerShell erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="59b72-123">The PowerShell jobs and scheduled job cmdlets work only on scheduled jobs that are created in PowerShell.</span></span>

## <a name="quick-start"></a><span data-ttu-id="59b72-124">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="59b72-124">Quick start</span></span>

<span data-ttu-id="59b72-125">In diesem Beispiel wird ein geplanter Auftrag erstellt, der jeden Tag um 3:00 Uhr beginnt und das `Get-Process` Cmdlet ausführt.</span><span class="sxs-lookup"><span data-stu-id="59b72-125">This example creates a scheduled job that starts every day at 3:00 AM and runs the `Get-Process` cmdlet.</span></span> <span data-ttu-id="59b72-126">Der Auftrag wird auch dann gestartet, wenn der Computer unter Batterien ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="59b72-126">The job starts even if the computer is running on batteries.</span></span>

```powershell
$trigger = New-JobTrigger -Daily -At 3AM
$options = New-ScheduledJobOption -StartIfOnBattery
Register-ScheduledJob -Name ProcessJob -ScriptBlock {Get-Process} `
-Trigger $trigger -ScheduledJobOption $options
```

<span data-ttu-id="59b72-127">Mit dem- `Get-ScheduledJob` Cmdlet werden die geplanten Aufträge auf dem lokalen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="59b72-127">The `Get-ScheduledJob` cmdlet gets the scheduled jobs on the local computer.</span></span>

```powershell
Get-ScheduledJob
```

```Output
Id         Name            Triggers        Command            Enabled
--         ----            --------        -------            -------
7          ProcessJob      {1}             Get-Process        True
```

<span data-ttu-id="59b72-128">`Get-JobTrigger` Ruft die Auftrags Trigger von **processjob** ab.</span><span class="sxs-lookup"><span data-stu-id="59b72-128">`Get-JobTrigger` gets the job triggers of **ProcessJob**.</span></span> <span data-ttu-id="59b72-129">Mit den Eingabe Parametern wird der geplante Auftrag und nicht der Trigger angegeben, da Trigger in einem geplanten Auftrag gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="59b72-129">The input parameters specify the scheduled job, not the trigger, because triggers are saved in a scheduled job.</span></span>

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id         Frequency       Time                   DaysOfWeek        Enabled
--         ---------       ----                   ----------        -------
1          Daily           11/5/2011 3:00:00 AM                     True
```

<span data-ttu-id="59b72-130">In diesem Beispiel wird der **continueifgoingonbattery** -Parameter des `Set-ScheduledJob` Cmdlets verwendet, um die **stopifgoingonakkus** -Eigenschaft von **processjob** in **false** zu ändern.</span><span class="sxs-lookup"><span data-stu-id="59b72-130">This example uses the **ContinueIfGoingOnBattery** parameter of the `Set-ScheduledJob` cmdlet to change the **StopIfGoingOnBatteries** property of **ProcessJob** to **False**.</span></span>

```powershell
Get-ScheduledJob -Name ProcessJob | Set-ScheduledJobOption `
-ContinueIfGoingOnBattery -Passthru
```

```Output
StartIfOnBatteries     : True
StopIfGoingOnBatteries : False
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

<span data-ttu-id="59b72-131">Mit dem- `Get-ScheduledJob` Cmdlet wird der geplante Auftrag " **processjob** " abgerufen.</span><span class="sxs-lookup"><span data-stu-id="59b72-131">The `Get-ScheduledJob` cmdlet gets the **ProcessJob** scheduled job.</span></span>

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command        Enabled
--         ----            --------        -------        -------
7          ProcessJob      {1}             Get-Process    True
```

<span data-ttu-id="59b72-132">Mit dem- `Get-Job` Cmdlet werden alle Instanzen des geplanten Auftrags " **processjob** " abgerufen, die bisher ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="59b72-132">The `Get-Job` cmdlet gets all instances of the **ProcessJob** scheduled job that have run thus far.</span></span> <span data-ttu-id="59b72-133">Mit dem- `Get-Job` Cmdlet werden geplante Aufträge nur abgerufen, wenn das **psscheduledjob** -Modul in die aktuelle Sitzung importiert wird.</span><span class="sxs-lookup"><span data-stu-id="59b72-133">The `Get-Job` cmdlet gets scheduled jobs only when the **PSScheduledJob** module is imported into the current session.</span></span>

> [!TIP]
> <span data-ttu-id="59b72-134">Beachten Sie, dass Sie die Cmdlets für geplante Aufträge verwenden, um geplante Aufträge zu verwalten, aber Sie verwenden die Job-Cmdlets zum Verwalten von Instanzen geplanter Aufträge.</span><span class="sxs-lookup"><span data-stu-id="59b72-134">Notice that you use the scheduled job cmdlets to manage scheduled jobs, but you use the job cmdlets to manage instances of scheduled jobs.</span></span>

```powershell
Get-Job -Name ProcessJob
```

```Output
Id     Name        PSJobTypeName  State    HasMoreData   Location   Command
--     ----        ------------   -----    -----------   --------   -------
45     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
46     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
47     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
48     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
49     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
50     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
51     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
```

<span data-ttu-id="59b72-135">Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse der aktuellen Instanz des geplanten Auftrags " **processjob** " abgerufen (ID = 51).</span><span class="sxs-lookup"><span data-stu-id="59b72-135">The `Receive-Job` cmdlet gets the results of the most recent instance of the **ProcessJob** scheduled job (ID = 51).</span></span>

```powershell
Receive-Job -ID 51
```

<span data-ttu-id="59b72-136">Obwohl der `Receive-Job` Befehl nicht den **Keep** -Parameter enthielt, werden die Ergebnisse des Auftrags auf dem Datenträger gespeichert, bis Sie ihn löschen oder die maximale Anzahl von Ergebnissen überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="59b72-136">Even though the `Receive-Job` command did not include the **Keep** parameter, the results of the job are saved on disk until you delete them or the maximum number of results are exceeded.</span></span>

<span data-ttu-id="59b72-137">Die Auftrags Ergebnisse sind in dieser Sitzung nicht mehr verfügbar. Wenn Sie jedoch eine neue Sitzung starten oder ein neues PowerShell-Fenster öffnen, sind die Ergebnisse des Auftrags erneut verfügbar.</span><span class="sxs-lookup"><span data-stu-id="59b72-137">The job results are no longer available in this session, but if you start a new session or open a new PowerShell window, the results of the job are available again.</span></span>

<span data-ttu-id="59b72-138">Der folgende Befehl verwendet den **DefinitionName** -Parameter des `Start-Job` Cmdlets, um den geplanten Auftrag " **processjob** " zu starten.</span><span class="sxs-lookup"><span data-stu-id="59b72-138">The following command uses the **DefinitionName** parameter of the `Start-Job` cmdlet to start the **ProcessJob** scheduled job.</span></span>

<span data-ttu-id="59b72-139">Aufträge, die mithilfe des `Start-Job` Cmdlets gestartet werden, sind Standard-PowerShell-Hintergrund Aufträge, keine Instanzen des geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="59b72-139">Jobs that are started by using the `Start-Job` cmdlet are standard PowerShell background jobs, not instances of the scheduled job.</span></span> <span data-ttu-id="59b72-140">Diese Aufträge werden wie alle Hintergrund Aufträge sofort gestartet, unterliegen nicht den Auftrags Optionen oder werden von Auftrags Triggern nicht betroffen, und ihre Ausgabe wird nicht im Ausgabeverzeichnis des Zeitplans für das geplante Verzeichnis gespeichert.</span><span class="sxs-lookup"><span data-stu-id="59b72-140">Like all background jobs, these jobs start immediately, they aren't subject to job options or affected by job triggers, and their output is not saved in the output directory of the scheduled job directory.</span></span>

```powershell
Start-Job -DefinitionName ProcessJob
```

<span data-ttu-id="59b72-141">`Unregister-ScheduledJob`Mit dem-Cmdlet werden der geplante Auftrag **processjob** und alle gespeicherten Ergebnisse der Auftrags Instanzen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="59b72-141">The `Unregister-ScheduledJob` cmdlet deletes the **ProcessJob** scheduled job and all saved results of its job instances.</span></span>

```powershell
Unregister-ScheduledJob ProcessJob
```

## <a name="scheduled-jobs-concepts"></a><span data-ttu-id="59b72-142">Konzepte geplanter Aufträge</span><span class="sxs-lookup"><span data-stu-id="59b72-142">Scheduled jobs concepts</span></span>

<span data-ttu-id="59b72-143">Ein geplanter Auftrag führt Befehle oder ein Skript aus.</span><span class="sxs-lookup"><span data-stu-id="59b72-143">A scheduled job runs commands or a script.</span></span> <span data-ttu-id="59b72-144">Ein geplanter Auftrag kann Auftrags Trigger enthalten, mit denen der Auftrag und Auftrags Optionen gestartet werden, mit denen Bedingungen zum Ausführen des Auftrags festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="59b72-144">A scheduled job can include job triggers that start the job and job options that set conditions for running the job.</span></span>

<span data-ttu-id="59b72-145">Ein Auftrags--Auslösung startet einen geplanten Auftrag automatisch.</span><span class="sxs-lookup"><span data-stu-id="59b72-145">A job trigger starts a scheduled job automatically.</span></span> <span data-ttu-id="59b72-146">Ein Auftrags Auslösung kann einen einmaligen oder wiederkehrenden Zeitplan einschließen oder ein Ereignis angeben, z. b. wenn sich ein Benutzer anmeldet oder Windows gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="59b72-146">A job trigger can include a one-time or recurring schedule or specify an event, such as when a user logs on or Windows starts.</span></span> <span data-ttu-id="59b72-147">Ein geplanter Auftrag kann über einen oder mehrere Auftrags Trigger verfügen, und Sie können Auftrags Trigger erstellen, hinzufügen, aktivieren, deaktivieren und erhalten.</span><span class="sxs-lookup"><span data-stu-id="59b72-147">A scheduled job can have one or more job triggers, and you can create, add, enable, disable, and get job triggers.</span></span>

<span data-ttu-id="59b72-148">Auftragstrigger sind optional.</span><span class="sxs-lookup"><span data-stu-id="59b72-148">Job triggers are optional.</span></span> <span data-ttu-id="59b72-149">Sie können geplante Aufträge sofort mit dem Starten `Start-Job cmdlet` , oder indem Sie dem Befehl den **runnow** -Parameter hinzufügen `Register-ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="59b72-149">You can start scheduled jobs immediately by using the `Start-Job cmdlet`, or by adding the **RunNow** parameter to your `Register-ScheduledJob` command.</span></span>

<span data-ttu-id="59b72-150">Mit Auftrags Optionen werden die Bedingungen zum Ausführen eines geplanten Auftrags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="59b72-150">Job options set the conditions for running a scheduled job.</span></span> <span data-ttu-id="59b72-151">Jeder geplante Auftrag verfügt über ein Auftrags Options Objekt.</span><span class="sxs-lookup"><span data-stu-id="59b72-151">Every scheduled job has one job options object.</span></span> <span data-ttu-id="59b72-152">Sie können Auftrags Options Objekte erstellen und bearbeiten und Sie einem oder mehreren geplanten Aufträgen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="59b72-152">You can create and edit job options objects and add them to one or more scheduled jobs.</span></span>

<span data-ttu-id="59b72-153">Jedes Mal, wenn ein geplanter Auftrag gestartet wird, wird eine Auftrags Instanz erstellt.</span><span class="sxs-lookup"><span data-stu-id="59b72-153">Each time a scheduled job starts, a job instance is created.</span></span> <span data-ttu-id="59b72-154">Verwenden Sie die PowerShell-Auftrags-Cmdlets, um die Auftrags Instanz anzuzeigen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="59b72-154">Use the PowerShell job cmdlets to view and manage the job instance.</span></span>

<span data-ttu-id="59b72-155">Geplante Aufträge werden auf dem Datenträger gespeichert und verwenden das-Cmdlet-Verb, `Register` anstelle von `New` .</span><span class="sxs-lookup"><span data-stu-id="59b72-155">Scheduled jobs are saved to disk and use the cmdlet verb, `Register`, instead of `New`.</span></span> <span data-ttu-id="59b72-156">Die XML-Dateien befinden sich auf dem lokalen Computer im Verzeichnis `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` .</span><span class="sxs-lookup"><span data-stu-id="59b72-156">The XML files are located on the local computer in the directory `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs`.</span></span>

<span data-ttu-id="59b72-157">PowerShell erstellt ein Verzeichnis für jeden geplanten Auftrag und speichert die Auftrags Befehle, Auftrags Trigger, Auftrags Optionen und Auftrags Ergebnisse im geplanten Auftrags Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="59b72-157">PowerShell creates a directory for each scheduled job and saves the job commands, job triggers, job options and job results in the scheduled job directory.</span></span> <span data-ttu-id="59b72-158">Auftrags Trigger und Auftrags Optionen werden nicht unabhängig auf der Festplatte gespeichert.</span><span class="sxs-lookup"><span data-stu-id="59b72-158">Job triggers and job options aren't saved to disk independently.</span></span>
<span data-ttu-id="59b72-159">Sie werden in der XML des geplanten Auftrags für jeden geplanten Auftrag gespeichert, dem Sie zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="59b72-159">They are saved in the scheduled job XML of each scheduled job with which they are associated.</span></span>

<span data-ttu-id="59b72-160">Geplante Aufträge, Auftrags Trigger und Auftrags Optionen werden in PowerShell als Objekte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59b72-160">Scheduled jobs, job triggers, and job options appear in PowerShell as objects.</span></span>
<span data-ttu-id="59b72-161">Die Objekte sind miteinander verknüpft, sodass Sie in Befehlen und Skripts leicht zu finden und zu verwenden sind.</span><span class="sxs-lookup"><span data-stu-id="59b72-161">The objects are interlinked, which makes them easy to discover and use in commands and scripts.</span></span>

<span data-ttu-id="59b72-162">Geplante Aufträge werden als **scheduledjobdefinition** -Objekte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59b72-162">Scheduled jobs appear as **ScheduledJobDefinition** objects.</span></span> <span data-ttu-id="59b72-163">Das **scheduledjobdefinition** -Objekt verfügt über eine **jobtriggers** -Eigenschaft, die die Auftrags Trigger des geplanten Auftrags und eine **options** -Eigenschaft enthält, die die Auftrags Optionen enthält.</span><span class="sxs-lookup"><span data-stu-id="59b72-163">The **ScheduledJobDefinition** object has a **JobTriggers** property that contains the job triggers of the scheduled job and an **Options** property that contains the job options.</span></span> <span data-ttu-id="59b72-164">Die **scheduledjobtriggers** -und **scheduledjoboptions** -Objekte, die Auftrags Trigger bzw. Auftrags Optionen darstellen, verfügen jeweils über eine **Jobdefinition** -Eigenschaft, die den geplanten Auftrag enthält, dem Sie zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="59b72-164">The **ScheduledJobTriggers** and **ScheduledJobOptions** objects that represent job triggers and job options, respectively, each have a **JobDefinition** property that contains the scheduled job with which they are associated.</span></span> <span data-ttu-id="59b72-165">Diese rekursive Verbindung vereinfacht das Auffinden der Trigger und Optionen eines geplanten Auftrags und das Auffinden, Skripterstellung und Anzeigen des geplanten Auftrags, dem ein beliebiger Auftrags Trigger oder jede Auftrags Option zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="59b72-165">This recursive interconnection makes it easy to find the triggers and options of a scheduled job and to find, script, and display the scheduled job to which any job trigger or job option is associated.</span></span>

## <a name="see-also"></a><span data-ttu-id="59b72-166">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="59b72-166">See also</span></span>

[<span data-ttu-id="59b72-167">about_Scheduled_Jobs_Basics</span><span class="sxs-lookup"><span data-stu-id="59b72-167">about_Scheduled_Jobs_Basics</span></span>](about_Scheduled_Jobs_Basics.md)

[<span data-ttu-id="59b72-168">about_Scheduled_Jobs_Advanced</span><span class="sxs-lookup"><span data-stu-id="59b72-168">about_Scheduled_Jobs_Advanced</span></span>](about_Scheduled_Jobs_Advanced.md)

[<span data-ttu-id="59b72-169">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="59b72-169">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

<span data-ttu-id="59b72-170">Cmdlets für das [psscheduledjob](xref:PSScheduledJob) -Modul</span><span class="sxs-lookup"><span data-stu-id="59b72-170">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="59b72-171">Aufgabenplanung</span><span class="sxs-lookup"><span data-stu-id="59b72-171">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
