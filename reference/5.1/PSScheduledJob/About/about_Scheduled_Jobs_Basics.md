---
description: Erläutert das Erstellen und Verwalten geplanter Aufträge.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_basics?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Basics
ms.openlocfilehash: d957c3267959c13b705e79fb220da4048e27a435
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221927"
---
# <a name="about-scheduled-jobs-basics"></a><span data-ttu-id="29b45-104">Grundlagen zu geplanten Aufträgen</span><span class="sxs-lookup"><span data-stu-id="29b45-104">About Scheduled Jobs Basics</span></span>

## <a name="short-description"></a><span data-ttu-id="29b45-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29b45-105">Short description</span></span>

<span data-ttu-id="29b45-106">Erläutert das Erstellen und Verwalten geplanter Aufträge.</span><span class="sxs-lookup"><span data-stu-id="29b45-106">Explains how to create and manage scheduled jobs.</span></span>

## <a name="long-description"></a><span data-ttu-id="29b45-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29b45-107">Long description</span></span>

<span data-ttu-id="29b45-108">In diesem Dokument wird gezeigt, wie Sie grundlegende Aufgaben zum Erstellen und Verwalten geplanter Aufträge ausführen.</span><span class="sxs-lookup"><span data-stu-id="29b45-108">This document shows how to perform basic tasks of creating and managing scheduled jobs.</span></span> <span data-ttu-id="29b45-109">Weitere Informationen zu erweiterten Aufgaben finden Sie unter [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="29b45-109">For information about more advanced tasks, see [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md).</span></span>

<span data-ttu-id="29b45-110">Weitere Informationen zu den im **psscheduledjob** -Modul enthaltenen Cmdlets finden Sie unter [psscheduledjob](xref:PSScheduledJob).</span><span class="sxs-lookup"><span data-stu-id="29b45-110">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

## <a name="how-to-create-a-scheduled-job"></a><span data-ttu-id="29b45-111">Erstellen eines geplanten Auftrags</span><span class="sxs-lookup"><span data-stu-id="29b45-111">How to create a scheduled job</span></span>

<span data-ttu-id="29b45-112">Um einen geplanten Auftrag zu erstellen, verwenden Sie das- `Register-ScheduledJob` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="29b45-112">To create a scheduled job, use the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="29b45-113">Das-Cmdlet erfordert einen Namen und die Befehle oder Skripts, die der Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="29b45-113">The cmdlet requires a name and the commands or script that the job runs.</span></span> <span data-ttu-id="29b45-114">Sie können den Auftrag entweder sofort ausführen, indem Sie den **runnow** -Parameter hinzufügen, einen Auftrags-und einen Auftrags Erstellungs Vorgang erstellen und Auftrags Optionen festlegen, wenn Sie den Auftrag erstellen, oder einen vorhandenen Auftrag bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="29b45-114">You can either run the job immediately by adding the **RunNow** parameter, or create a job trigger and set job options when you create the job, or edit an existing job.</span></span>

<span data-ttu-id="29b45-115">Um einen Auftrag zu erstellen, der ein Skript ausführt, verwenden Sie den **FilePath** -Parameter, um den Pfad zur Skriptdatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="29b45-115">To create a job that runs a script, use the **FilePath** parameter to specify the path to the script file.</span></span> <span data-ttu-id="29b45-116">Verwenden Sie den **ScriptBlock** -Parameter, um einen Auftrag zu erstellen, der Befehle ausführt.</span><span class="sxs-lookup"><span data-stu-id="29b45-116">To create a job that runs commands, use the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="29b45-117">Das- `Register-ScheduledJob` Cmdlet erstellt den **processjob** , der einen- `Get-Process` Befehl ausführt.</span><span class="sxs-lookup"><span data-stu-id="29b45-117">The `Register-ScheduledJob` cmdlet creates the **ProcessJob** , which runs a `Get-Process` command.</span></span> <span data-ttu-id="29b45-118">Dieser geplante Auftrag verfügt über die Standard Auftrags Optionen und keinen Auftrags Auslösers.</span><span class="sxs-lookup"><span data-stu-id="29b45-118">This scheduled job has the default job options and no job trigger.</span></span>

```powershell
Register-ScheduledJob -Name ProcessJob -ScriptBlock { Get-Process }
```

```Output
Id         Name            Triggers        Command       Enabled
--         ----            --------        -------       -------
8          ProcessJob      {}              Get-Process   True
```

## <a name="how-to-create-a-job-trigger"></a><span data-ttu-id="29b45-119">Erstellen eines Auftrags Auslösers</span><span class="sxs-lookup"><span data-stu-id="29b45-119">How to create a job trigger</span></span>

<span data-ttu-id="29b45-120">Auftrags Trigger starten einen geplanten Auftrag automatisch.</span><span class="sxs-lookup"><span data-stu-id="29b45-120">Job triggers start a scheduled job automatically.</span></span> <span data-ttu-id="29b45-121">Ein Auftrags Auslösung kann ein einmaliger oder sich Wiederhol ender Zeitplan oder ein Ereignis sein, z. b. wenn sich ein Benutzer anmeldet oder Windows gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="29b45-121">A job trigger can be one-time or recurring schedule or an event, such as when a user logs on or Windows starts.</span></span> <span data-ttu-id="29b45-122">Jeder Auftrag kann über NULL, einen oder mehrere Auftrags Trigger verfügen.</span><span class="sxs-lookup"><span data-stu-id="29b45-122">Each job can have zero, one, or multiple job triggers.</span></span>

<span data-ttu-id="29b45-123">Verwenden Sie zum Erstellen eines Auftrags Auslösers das- `New-JobTrigger` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="29b45-123">To create a job trigger, use the `New-JobTrigger` cmdlet.</span></span> <span data-ttu-id="29b45-124">Der folgende Befehl erstellt einen Auftrags--Befehl, der einen Auftrag jeden Montag und Donnerstag um 5:00 Uhr startet.</span><span class="sxs-lookup"><span data-stu-id="29b45-124">The following command creates a job trigger that starts a job every Monday and Thursday at 5:00 AM.</span></span>
<span data-ttu-id="29b45-125">Der Befehl speichert den Auftrags--Befehl in der `$T` Variablen.</span><span class="sxs-lookup"><span data-stu-id="29b45-125">The command saves the job trigger in the `$T` variable.</span></span>

```powershell
$T = New-JobTrigger -Weekly -DaysOfWeek "Monday", "Thursday" -At "5:00 AM"
```

<span data-ttu-id="29b45-126">Auftragstrigger sind optional.</span><span class="sxs-lookup"><span data-stu-id="29b45-126">Job triggers are optional.</span></span> <span data-ttu-id="29b45-127">Sie können einen geplanten Auftrag jederzeit starten, indem Sie dem Befehl den **runnow** -Parameter hinzufügen `Register-ScheduledJob` oder indem Sie die- `Start-Job` Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="29b45-127">You can start a scheduled job at any time by adding the **RunNow** parameter to your `Register-ScheduledJob` command, or by using the `Start-Job` cmdlets.</span></span>

## <a name="how-to-add-a-job-trigger"></a><span data-ttu-id="29b45-128">Vorgehensweise beim Hinzufügen eines Auftrags Auslösers</span><span class="sxs-lookup"><span data-stu-id="29b45-128">How to add a job trigger</span></span>

<span data-ttu-id="29b45-129">Wenn Sie einem geplanten Auftrag einen Auftrags-Triggervorgang hinzufügen, wird der Auftrags-und der geplante Auftrags-XML-Datei für den geplanten Auftrag hinzugefügt und wird Teil des geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="29b45-129">When you add a job trigger to a scheduled job, the job trigger is added to the scheduled job XML file for the scheduled job and becomes part of the scheduled job.</span></span>

<span data-ttu-id="29b45-130">Sie können einem geplanten Auftrag einen Auftrags-und einen Auftrags--Auslösers hinzufügen, wenn Sie den geplanten Auftrag erstellen oder einen vorhandenen Auftrag bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="29b45-130">You can add a job trigger to a scheduled job when you create the scheduled job, or edit an existing job.</span></span> <span data-ttu-id="29b45-131">Sie können den Auftrags-und einen geplanten Auftrag jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="29b45-131">You can change the job trigger of a scheduled job at any time.</span></span>

<span data-ttu-id="29b45-132">PowerShell verwendet einige der gleichen Auftrags Trigger, die von Taskplaner verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="29b45-132">PowerShell uses some of the same job triggers that Task Scheduler uses.</span></span> <span data-ttu-id="29b45-133">Ausführliche Informationen zu Auftrags Triggern finden Sie im Hilfethema für das [New-jobtrigger](xref:PSScheduledJob.New-JobTrigger) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="29b45-133">For detailed information about job triggers, see the help topic for the [New-JobTrigger](xref:PSScheduledJob.New-JobTrigger) cmdlet.</span></span>

<span data-ttu-id="29b45-134">Im folgenden Beispiel wird Verteilung verwendet, um `$JobParms` Parameterwerte zu erstellen, die an das `Register-ScheduledJob` Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="29b45-134">The following example uses splatting to create `$JobParms` which are parameter values that are passed to the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="29b45-135">Weitere Informationen finden Sie unter [about_Splatting. MD](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="29b45-135">For more information, see [about_Splatting.md](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>
<span data-ttu-id="29b45-136">Der `Register-ScheduledJob` verwendet `@JobParms` , um einen geplanten Auftrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="29b45-136">The `Register-ScheduledJob` uses `@JobParms` to create a scheduled job.</span></span> <span data-ttu-id="29b45-137">Er verwendet den **-Parameter für den-** Parameter, um den Auftrags-und in der `$T` Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="29b45-137">It uses the **Trigger** parameter to specify the job trigger in the `$T` variable.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Command}
  Trigger = $T
}

Register-ScheduledJob @JobParms
```

<span data-ttu-id="29b45-138">Sie können einem vorhandenen geplanten Auftrag auch jederzeit einen Auftrags-Auslösers hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="29b45-138">You can also add a job trigger to an existing scheduled job at any time.</span></span> <span data-ttu-id="29b45-139">Mit dem- `Add-JobTrigger` Cmdlet wird der Auftrags-/Auftragsaus der `$T` Variablen dem geplanten Auftrag **processjob** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="29b45-139">The `Add-JobTrigger` cmdlet adds the job trigger in the `$T` variable to the **ProcessJob** scheduled job.</span></span>

```powershell
Add-JobTrigger -Name ProcessJob -Trigger $T
```

<span data-ttu-id="29b45-140">Demzufolge startet der Auftrags--auslöst den **processjob** automatisch jeden Montag und Donnerstag um 5:00 Uhr.</span><span class="sxs-lookup"><span data-stu-id="29b45-140">As a result, the job trigger starts the **ProcessJob** automatically every Monday and Thursday at 5:00 AM.</span></span>

## <a name="how-to-get-a-job-trigger"></a><span data-ttu-id="29b45-141">Vorgehensweise beim erhalten eines Auftrags Auslösers</span><span class="sxs-lookup"><span data-stu-id="29b45-141">How to get a job trigger</span></span>

<span data-ttu-id="29b45-142">Verwenden Sie zum Ausführen des Auftrags Auslösers eines geplanten Auftrags das `Get-JobTrigger` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="29b45-142">To get the job trigger of a scheduled job, use the `Get-JobTrigger` cmdlet.</span></span> <span data-ttu-id="29b45-143">Verwenden Sie die Parameter " **Name** ", " **ID** " und " **Inputobject** ", um den geplanten Auftrag anzugeben, nicht den Auftrags-.</span><span class="sxs-lookup"><span data-stu-id="29b45-143">Use the **Name** , **ID** , and **InputObject** parameters to specify the scheduled job, not the job trigger.</span></span>

<span data-ttu-id="29b45-144">`Get-JobTrigger` Ruft den Auftrags--auslöst von **processjob** ab.</span><span class="sxs-lookup"><span data-stu-id="29b45-144">`Get-JobTrigger` gets the job trigger of the **ProcessJob**.</span></span>

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id   Frequency       Time                   DaysOfWeek              Enabled
--   ---------       ----                   ----------              -------
1    Weekly          11/7/2011 5:00:00 AM   {Monday, Thursday}      True
```

## <a name="how-to-create-job-options"></a><span data-ttu-id="29b45-145">Erstellen von Auftrags Optionen</span><span class="sxs-lookup"><span data-stu-id="29b45-145">How to create job options</span></span>

<span data-ttu-id="29b45-146">Mit Auftrags Optionen werden Bedingungen zum Starten und Ausführen des Auftrags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="29b45-146">Job options establish conditions for starting and running the job.</span></span> <span data-ttu-id="29b45-147">Jeder Auftrag verfügt über die Standard Auftrags Optionen, es sei denn, Sie ändern diese.</span><span class="sxs-lookup"><span data-stu-id="29b45-147">Every job has the default job options unless you change them.</span></span> <span data-ttu-id="29b45-148">Da Auftrags Optionen verhindern können, dass ein Auftrag zum geplanten Zeitpunkt ausgeführt wird, ist es wichtig, die Auftrags Optionen zu verstehen und Sie sorgfältig zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="29b45-148">Because job options can prevent a job from running at the scheduled time, it is important to understand the job options and use them carefully.</span></span>

<span data-ttu-id="29b45-149">PowerShell verwendet die gleichen Auftrags Optionen, die von Taskplaner verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="29b45-149">PowerShell uses the same job options that Task Scheduler uses.</span></span> <span data-ttu-id="29b45-150">Ausführliche Informationen zu den Auftrags Optionen finden Sie im Hilfethema zu [New-scheduledjoboption](xref:PSScheduledJob.New-ScheduledJobOption).</span><span class="sxs-lookup"><span data-stu-id="29b45-150">For detailed information about the job options, see the help topic for [New-ScheduledJobOption](xref:PSScheduledJob.New-ScheduledJobOption).</span></span>

<span data-ttu-id="29b45-151">Auftrags Optionen werden in der XML-Datei des geplanten Auftrags gespeichert.</span><span class="sxs-lookup"><span data-stu-id="29b45-151">Job options are stored in the scheduled job XML file.</span></span> <span data-ttu-id="29b45-152">Sie können Auftrags Optionen festlegen, wenn Sie einen geplanten Auftrag erstellen oder jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="29b45-152">You can set job options when you create a scheduled job or change them at any time.</span></span>

<span data-ttu-id="29b45-153">Mit dem- `New-ScheduledJobOption` Cmdlet wird eine Option für geplante Aufträge erstellt, bei der die Option für den geplanten Auftrag " **waketor** " auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="29b45-153">The `New-ScheduledJobOption` cmdlet creates a scheduled job option in which the **WakeToRun** scheduled job option is set to True.</span></span> <span data-ttu-id="29b45-154">Die Option " **waketor UN** " führt den geplanten Auftrag selbst dann aus, wenn sich der Computer zur geplanten Startzeit im Standbymodus oder Ruhezustand befindet.</span><span class="sxs-lookup"><span data-stu-id="29b45-154">The **WakeToRun** option runs the scheduled job even if the computer is in the Sleep or Hibernate state at the scheduled start time.</span></span> <span data-ttu-id="29b45-155">Der Befehl speichert die Auftrags Optionen in der `$O` Variablen.</span><span class="sxs-lookup"><span data-stu-id="29b45-155">The command saves the job options in the `$O` variable.</span></span>

```powershell
$O = New-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-job-options"></a><span data-ttu-id="29b45-156">Vorgehensweise beim erhalten von Auftrags Optionen</span><span class="sxs-lookup"><span data-stu-id="29b45-156">How to get job options</span></span>

<span data-ttu-id="29b45-157">Verwenden Sie das-Cmdlet, um die Auftrags Optionen eines geplanten Auftrags zu erhalten `Get-ScheduledJobOption` .</span><span class="sxs-lookup"><span data-stu-id="29b45-157">To get the job options of a scheduled job, use the `Get-ScheduledJobOption` cmdlet.</span></span> <span data-ttu-id="29b45-158">Verwenden Sie die Parameter **Name** , **ID** und **Inputobject** , um den geplanten Auftrag und nicht die Auftrags Optionen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="29b45-158">Use the **Name** , **ID** , and **InputObject** parameters to specify the scheduled job, not the job options.</span></span>

<span data-ttu-id="29b45-159">`Get-ScheduledJobOption` Ruft die Auftrags Optionen von **processjob** ab.</span><span class="sxs-lookup"><span data-stu-id="29b45-159">`Get-ScheduledJobOption` gets the job options of the **ProcessJob**.</span></span>

```powershell
Get-ScheduledJobOption -Name ProcessJob
```

```Output
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
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

## <a name="how-to-change-job-options"></a><span data-ttu-id="29b45-160">Vorgehensweise beim Ändern von Auftrags Optionen</span><span class="sxs-lookup"><span data-stu-id="29b45-160">How to change job options</span></span>

<span data-ttu-id="29b45-161">Sie können die Auftrags Optionen eines geplanten Auftrags ändern, wenn Sie einen geplanten Auftrag erstellen oder einen vorhandenen Auftrag bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="29b45-161">You can change the job options of a scheduled job when you create a scheduled job or edit an existing job.</span></span>

<span data-ttu-id="29b45-162">Der splatted `$JobParms` wird an das `Add-JobTrigger` Cmdlet übergeben, um den Prozess Auftrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="29b45-162">The splatted `$JobParms` are passed to the `Add-JobTrigger` cmdlet to create the process job.</span></span> <span data-ttu-id="29b45-163">Er verwendet den **scheduledjoboption** -Parameter, um die Auftrags Optionen in der `$O` Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="29b45-163">It uses the **ScheduledJobOption** parameter to specify the job options in the `$O` variable.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  ScheduledJobOption = $O
}

Add-JobTrigger @JobParms
```

<span data-ttu-id="29b45-164">Sie können die Auftrags Optionen auch jederzeit in einen vorhandenen geplanten Auftrag ändern.</span><span class="sxs-lookup"><span data-stu-id="29b45-164">You can also change the job options to an existing scheduled job at any time.</span></span>
<span data-ttu-id="29b45-165">Der folgende Befehl verwendet das `Set-ScheduledJobOption` Cmdlet, um den Wert der **Wake-on-** Option von **processjob** ScheduledJob in **true** zu ändern.</span><span class="sxs-lookup"><span data-stu-id="29b45-165">The following command uses the `Set-ScheduledJobOption` cmdlet to change the value of the **WakeToRun** option of the **ProcessJob** scheduledJob to **True**.</span></span>

<span data-ttu-id="29b45-166">Die `Set` Cmdlets im **psscheduledjob** -Modul, wie z `Set-ScheduledJobOption` . b. das Cmdlet, haben keine **namens** -oder **ID** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="29b45-166">The `Set` cmdlets in the **PSScheduledJob** module, such as the `Set-ScheduledJobOption` cmdlet, don't have **Name** or **ID** parameters.</span></span> <span data-ttu-id="29b45-167">Sie können den **Inputobject** -Parameter verwenden, um die Optionen für geplante Aufträge anzugeben oder einen geplanten Auftrag vom `Get-ScheduledJobOption` Cmdlet an weiterzuleiten `Set-ScheduledJobOption` .</span><span class="sxs-lookup"><span data-stu-id="29b45-167">You can use the **InputObject** parameter to specify the scheduled job options or pipe a scheduled job from `Get-ScheduledJobOption` cmdlet to `Set-ScheduledJobOption`.</span></span>

<span data-ttu-id="29b45-168">In diesem Beispiel wird das- `Get-ScheduledJob` Cmdlet zum erhalten von processjob verwendet.</span><span class="sxs-lookup"><span data-stu-id="29b45-168">This example uses the `Get-ScheduledJob` cmdlet to get the ProcessJob.</span></span> <span data-ttu-id="29b45-169">Er verwendet das `Get-ScheduledJobOption` Cmdlet, um die Auftrags Optionen in **processjob** und das `Set-ScheduledJobOption` Cmdlet zu erhalten, um die Option " **waketor UN** Job" in "processjob" in "true" zu ändern.</span><span class="sxs-lookup"><span data-stu-id="29b45-169">It uses the `Get-ScheduledJobOption` cmdlet to get the job options in the **ProcessJob** and the `Set-ScheduledJobOption` cmdlet to change the **WakeToRun** job option in the ProcessJob to True.</span></span>

```powershell
Get-ScheduledJob -Name ProcessJob | Get-ScheduledJobOption |
 Set-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-scheduled-job-instances"></a><span data-ttu-id="29b45-170">So erhalten Sie geplante Auftrags Instanzen</span><span class="sxs-lookup"><span data-stu-id="29b45-170">How to get scheduled job instances</span></span>

<span data-ttu-id="29b45-171">Wenn ein geplanter Auftrag gestartet wird, erstellt PowerShell eine Auftrags Instanz, die einem standardmäßigen PowerShell-Hintergrund Auftrag ähnelt.</span><span class="sxs-lookup"><span data-stu-id="29b45-171">When a scheduled job is started, PowerShell creates a job instance that is similar to a standard PowerShell background job.</span></span> <span data-ttu-id="29b45-172">Sie können die Auftrags-Cmdlets, z `Get-Job` . b `Stop-Job` ., und verwenden, `Receive-Job` um die Auftrags Instanzen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="29b45-172">You can use the job cmdlets, such as `Get-Job`, `Stop-Job` and `Receive-Job` to manage the job instances.</span></span>

> [!NOTE]
> <span data-ttu-id="29b45-173">Damit die Job-Cmdlets für Instanzen geplanter Aufträge verwendet werden können, muss das **psscheduledjob** -Modul in die Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="29b45-173">To use the job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="29b45-174">Um das **psscheduledjob** -Modul zu importieren, geben Sie `Import-Module PSScheduledJob` ein beliebiges geplanter Job-Cmdlet ein, z `Get-ScheduledJob` . b..</span><span class="sxs-lookup"><span data-stu-id="29b45-174">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

<span data-ttu-id="29b45-175">Verwenden Sie das-Cmdlet, um alle Instanzen von geplanten PowerShell-Aufträgen und alle aktiven Standardaufträge zu erhalten `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="29b45-175">To get all instances of PowerShell scheduled jobs, and all active standard jobs, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="29b45-176">`Import-Module`Mit dem-Cmdlet wird das **psscheduledjob** -Modul importiert, und `Get-Job` die Aufträge werden auf dem lokalen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="29b45-176">The `Import-Module` cmdlet imports the **PSScheduledJob** module and `Get-Job` gets the jobs on the local computer.</span></span>

```powershell
Import-Module PSScheduledJob
Get-Job
```

<span data-ttu-id="29b45-177">`Get-Job` Ruft die Instanzen von **processjob** auf dem lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="29b45-177">`Get-Job` gets instances of **ProcessJob** on the local computer.</span></span>

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

<span data-ttu-id="29b45-178">Die Standard Anzeige zeigt nicht die Startzeit an, in der normalerweise Instanzen desselben geplanten Auftrags unterschieden werden.</span><span class="sxs-lookup"><span data-stu-id="29b45-178">The default display does not show the start time, which typically distinguishes instances of the same scheduled job.</span></span>

<span data-ttu-id="29b45-179">Das- `Get-Job` Cmdlet sendet Objekte über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="29b45-179">The `Get-Job` cmdlet sends objects down the pipeline.</span></span> <span data-ttu-id="29b45-180">Das- `Format-Table` Cmdlet zeigt die Eigenschaften " **Name** ", " **ID** " und " **BeginTime** " des geplanten Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="29b45-180">The `Format-Table` cmdlet displays the **Name** , **ID** , and **BeginTime** properties of the scheduled job.</span></span>

```powershell
Get-Job ProcessJob | Format-Table -Property Name, ID, BeginTime
```

```Output
Name       Id BeginTime
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

## <a name="get-scheduled-job-results"></a><span data-ttu-id="29b45-181">Geplante Auftrags Ergebnisse erhalten</span><span class="sxs-lookup"><span data-stu-id="29b45-181">Get scheduled job results</span></span>

<span data-ttu-id="29b45-182">Verwenden Sie das-Cmdlet, um die Ergebnisse einer Instanz eines geplanten Auftrags zu erhalten `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="29b45-182">To get the results of an instance of a scheduled job, use the `Receive-Job` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="29b45-183">Damit die Job-Cmdlets für Instanzen geplanter Aufträge verwendet werden können, muss das **psscheduledjob** -Modul in die Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="29b45-183">To use the Job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="29b45-184">Um das **psscheduledjob** -Modul zu importieren, geben Sie `Import-Module PSScheduledJob` ein beliebiges geplanter Job-Cmdlet ein, z `Get-ScheduledJob` . b..</span><span class="sxs-lookup"><span data-stu-id="29b45-184">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

<span data-ttu-id="29b45-185">In diesem Beispiel werden die Ergebnisse der aktuellen Instanz des geplanten Auftrags **processjob** (ID = 51) abgerufen.</span><span class="sxs-lookup"><span data-stu-id="29b45-185">This examples gets the results of the newest instance of the **ProcessJob** scheduled job (ID = 51).</span></span>

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 51 -Keep
```

<span data-ttu-id="29b45-186">Die Ergebnisse geplanter Aufträge werden auf dem Datenträger gespeichert, sodass der **Keep** -Parameter von `Receive-Job` nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="29b45-186">The results of scheduled jobs are saved on disk, so the **Keep** parameter of `Receive-Job` is not required.</span></span> <span data-ttu-id="29b45-187">Ohne den **Keep** -Parameter können Sie die Ergebnisse eines geplanten Auftrags jedoch nur einmal in jeder PowerShell-Sitzung erhalten.</span><span class="sxs-lookup"><span data-stu-id="29b45-187">However, without the **Keep** parameter, you can get the results of a scheduled job only once in each PowerShell session.</span></span> <span data-ttu-id="29b45-188">Zum Starten einer neuen PowerShell-Sitzung geben `PowerShell` oder öffnen Sie ein neues PowerShell-Fenster.</span><span class="sxs-lookup"><span data-stu-id="29b45-188">To start a new PowerShell session, type `PowerShell` or open a new PowerShell window.</span></span>

## <a name="see-also"></a><span data-ttu-id="29b45-189">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="29b45-189">See also</span></span>

[<span data-ttu-id="29b45-190">about_Scheduled_Jobs_Advanced</span><span class="sxs-lookup"><span data-stu-id="29b45-190">about_Scheduled_Jobs_Advanced</span></span>](about_Scheduled_Jobs_Advanced.md)

[<span data-ttu-id="29b45-191">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="29b45-191">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

[<span data-ttu-id="29b45-192">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="29b45-192">about_Scheduled_Jobs</span></span>](about_Scheduled_Jobs.md)

[<span data-ttu-id="29b45-193">about_Splatting. MD</span><span class="sxs-lookup"><span data-stu-id="29b45-193">about_Splatting.md</span></span>](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

<span data-ttu-id="29b45-194">Cmdlets für das [psscheduledjob](xref:PSScheduledJob) -Modul</span><span class="sxs-lookup"><span data-stu-id="29b45-194">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="29b45-195">Aufgabenplanung</span><span class="sxs-lookup"><span data-stu-id="29b45-195">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
