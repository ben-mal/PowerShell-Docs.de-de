---
description: Enthält Details zu Hintergrund Aufträgen auf lokalen Computern und Remote Computern.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_job_details?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Job_Details
ms.openlocfilehash: 0d85cd242c8e79281fa8be153b0e140660f16c1a
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "93224636"
---
# <a name="about-job-details"></a><span data-ttu-id="a678c-104">Informationen zu Auftrags Details</span><span class="sxs-lookup"><span data-stu-id="a678c-104">About Job Details</span></span>

## <a name="short-description"></a><span data-ttu-id="a678c-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a678c-105">Short description</span></span>
<span data-ttu-id="a678c-106">Enthält Details zu Hintergrund Aufträgen auf lokalen Computern und Remote Computern.</span><span class="sxs-lookup"><span data-stu-id="a678c-106">Provides details about background jobs on local and remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="a678c-107">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a678c-107">Detailed description</span></span>

<span data-ttu-id="a678c-108">In diesem Thema wird das Konzept eines Hintergrund Auftrags erläutert, und es werden technische Informationen zur Funktionsweise von Hintergrund Aufträgen in PowerShell bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a678c-108">This topic explains the concept of a background job and provides technical information about how background jobs work in PowerShell.</span></span>

<span data-ttu-id="a678c-109">Dieses Thema ist eine Ergänzung zu den Themen [about_Jobs](about_Jobs.md), [about_Thread_Jobs](about_Thread_Jobs.md)und [about_Remote_Jobs](about_Remote_Jobs.md) .</span><span class="sxs-lookup"><span data-stu-id="a678c-109">This topic is a supplement to the [about_Jobs](about_Jobs.md), [about_Thread_Jobs](about_Thread_Jobs.md), and [about_Remote_Jobs](about_Remote_Jobs.md) topics.</span></span>

### <a name="about-background-jobs"></a><span data-ttu-id="a678c-110">Informationen zu Hintergrund Aufträgen</span><span class="sxs-lookup"><span data-stu-id="a678c-110">About background jobs</span></span>

<span data-ttu-id="a678c-111">Ein Hintergrund Auftrag führt einen Befehl oder einen Ausdruck asynchron aus.</span><span class="sxs-lookup"><span data-stu-id="a678c-111">A background job runs a command or expression asynchronously.</span></span> <span data-ttu-id="a678c-112">Sie kann ein Cmdlet, eine Funktion, ein Skript oder eine beliebige andere Befehls basierte Aufgabe ausführen.</span><span class="sxs-lookup"><span data-stu-id="a678c-112">It might run a cmdlet, a function, a script, or any other command-based task.</span></span> <span data-ttu-id="a678c-113">Es ist für die Ausführung von Befehlen konzipiert, die einen längeren Zeitraum in Anspruch nehmen, aber Sie können ihn zum Ausführen beliebiger Befehle im Hintergrund verwenden.</span><span class="sxs-lookup"><span data-stu-id="a678c-113">It is designed to run commands that take an extended period of time, but you can use it to run any command in the background.</span></span>

<span data-ttu-id="a678c-114">Wenn ein synchroner Befehl ausgeführt wird, wird die PowerShell-Eingabeaufforderung unterdrückt, bis der Befehl beendet ist.</span><span class="sxs-lookup"><span data-stu-id="a678c-114">When a synchronous command runs, the PowerShell command prompt is suppressed until the command is complete.</span></span> <span data-ttu-id="a678c-115">Ein Hintergrund Auftrag unterdrückt die PowerShell-Eingabeaufforderung jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="a678c-115">But a background job does not suppress the PowerShell prompt.</span></span> <span data-ttu-id="a678c-116">Ein Befehl zum Starten eines Hintergrund Auftrags gibt ein Auftrags Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="a678c-116">A command to start a background job returns a job object.</span></span>
<span data-ttu-id="a678c-117">Die Eingabeaufforderung wird sofort zurückgegeben, sodass Sie an anderen Aufgaben arbeiten können, während der Hintergrund Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a678c-117">The prompt returns immediately so you can work on other tasks while the background job runs.</span></span>

<span data-ttu-id="a678c-118">Wenn Sie jedoch einen Hintergrund Auftrag starten, werden die Ergebnisse nicht sofort angezeigt, auch wenn der Auftrag sehr schnell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a678c-118">However, when you start a background job, you do not get the results immediately even if the job runs very quickly.</span></span> <span data-ttu-id="a678c-119">Das zurückgegebene Auftrags Objekt enthält nützliche Informationen zum Auftrag, enthält jedoch keine Auftrags Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="a678c-119">The job object that is returned contains useful information about the job, but it does not contain the job results.</span></span> <span data-ttu-id="a678c-120">Sie müssen einen separaten Befehl ausführen, um die Auftrags Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a678c-120">You must run a separate command to get the job results.</span></span> <span data-ttu-id="a678c-121">Sie können auch Befehle ausführen, um den Auftrag anzuhalten, auf den Abschluss des Auftrags zu warten und den Auftrag zu löschen.</span><span class="sxs-lookup"><span data-stu-id="a678c-121">You can also run commands to stop the job, to wait for the job to be completed, and to delete the job.</span></span>

<span data-ttu-id="a678c-122">Um die zeitliche Steuerung eines Hintergrund Auftrags unabhängig von anderen Befehlen vorzunehmen, wird jeder Hintergrund Auftrag in einer eigenen PowerShell-Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a678c-122">To make the timing of a background job independent of other commands, each background job runs in its own PowerShell session.</span></span> <span data-ttu-id="a678c-123">Dabei kann es sich jedoch um eine temporäre Verbindung handeln, die nur zum Ausführen des Auftrags erstellt und dann zerstört wird, oder es kann sich um eine persistente **PSSession** handeln, die Sie verwenden können, um mehrere zugehörige Aufträge oder Befehle auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a678c-123">However, this can be a temporary connection that is created only to run the job and is then destroyed, or it can be a persistent **PSSession** that you can use to run several related jobs or commands.</span></span>

### <a name="using-the-job-cmdlets"></a><span data-ttu-id="a678c-124">Verwenden der Auftrags-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a678c-124">Using the job cmdlets</span></span>

<span data-ttu-id="a678c-125">Verwenden `Start-Job` Sie einen Befehl, um einen Hintergrund Auftrag auf einem lokalen Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="a678c-125">Use a `Start-Job` command to start a background job on a local computer.</span></span>
<span data-ttu-id="a678c-126">`Start-Job` Gibt ein Auftrags Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="a678c-126">`Start-Job` returns a job object.</span></span> <span data-ttu-id="a678c-127">Sie können auch Objekte, die die Aufträge darstellen, die auf dem lokalen Computer gestartet wurden, mithilfe des- `Get-Job` Cmdlets erhalten.</span><span class="sxs-lookup"><span data-stu-id="a678c-127">You can also get objects representing the jobs that were started on the local computer using the `Get-Job` cmdlet.</span></span>

<span data-ttu-id="a678c-128">Um die Auftrags Ergebnisse zu erhalten, verwenden Sie einen- `Receive-Job` Befehl.</span><span class="sxs-lookup"><span data-stu-id="a678c-128">To get the job results, use a `Receive-Job` command.</span></span> <span data-ttu-id="a678c-129">Wenn der Auftrag nicht vollständig ist, `Receive-Job` gibt partielle Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="a678c-129">If the job is not complete, `Receive-Job` returns partial results.</span></span> <span data-ttu-id="a678c-130">Sie können auch das `Wait-Job` Cmdlet verwenden, um die Eingabeaufforderung zu unterdrücken, bis ein oder alle Aufträge, die in der Sitzung gestartet wurden, vollständig sind.</span><span class="sxs-lookup"><span data-stu-id="a678c-130">You can also use the `Wait-Job` cmdlet to suppress the command prompt until one or all of the jobs that were started in the session are complete.</span></span>

<span data-ttu-id="a678c-131">Verwenden Sie das-Cmdlet, um einen Hintergrund Auftrag zu unterbinden `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="a678c-131">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="a678c-132">Verwenden Sie das Cmdlet, um einen Auftrag zu löschen `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="a678c-132">To delete a job, use the `Remove-Job` cmdlet.</span></span>

<span data-ttu-id="a678c-133">Weitere Informationen zur Funktionsweise der Cmdlets finden Sie im Hilfethema für jedes Cmdlet und unter [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="a678c-133">For more information about how the cmdlets work, see the Help topic for each cmdlet, and see [about_Jobs](about_Jobs.md).</span></span>

### <a name="starting-background-jobs-on-remote-computers"></a><span data-ttu-id="a678c-134">Starten von Hintergrund Aufträgen auf Remote Computern</span><span class="sxs-lookup"><span data-stu-id="a678c-134">Starting background jobs on remote computers</span></span>

<span data-ttu-id="a678c-135">Hintergrund Aufträge können auf einem lokalen Computer oder einem Remote Computer erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="a678c-135">You can create and manage background jobs on a local or remote computer.</span></span> <span data-ttu-id="a678c-136">Wenn Sie einen Hintergrund Auftrag Remote ausführen möchten, verwenden Sie den **AsJob** -Parameter eines Cmdlets `Invoke-Command` , z. b., oder verwenden `Invoke-Command` Sie das Cmdlet, um einen `Start-Job` Befehl Remote auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a678c-136">To run a background job remotely, use the **AsJob** parameter of a cmdlet such as `Invoke-Command`, or use the `Invoke-Command` cmdlet to run a `Start-Job` command remotely.</span></span> <span data-ttu-id="a678c-137">Sie können auch einen Hintergrund Auftrag in einer interaktiven Sitzung starten.</span><span class="sxs-lookup"><span data-stu-id="a678c-137">You can also start a background job in an interactive session.</span></span>

<span data-ttu-id="a678c-138">Weitere Informationen zu Remote Hintergrund Aufträgen finden Sie unter [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="a678c-138">For more information about remote background jobs, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>

### <a name="child-jobs"></a><span data-ttu-id="a678c-139">Untergeordnete Aufträge</span><span class="sxs-lookup"><span data-stu-id="a678c-139">Child jobs</span></span>

<span data-ttu-id="a678c-140">Jeder Hintergrund Auftrag besteht aus einem übergeordneten Auftrag und einem oder mehreren untergeordneten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="a678c-140">Each background job consists of a parent job and one or more child jobs.</span></span> <span data-ttu-id="a678c-141">Bei Aufträgen `Start-Job` , die mit oder dem **AsJob** -Parameter von gestartet `Invoke-Command` wurden, ist der übergeordnete Auftrag eine Führungskraft.</span><span class="sxs-lookup"><span data-stu-id="a678c-141">In jobs started using `Start-Job` or the **AsJob** parameter of `Invoke-Command`, the parent job is an executive.</span></span> <span data-ttu-id="a678c-142">Es werden keine Befehle ausgeführt, oder es werden keine Ergebnisse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a678c-142">It does not run any commands or return any results.</span></span> <span data-ttu-id="a678c-143">Die Befehle werden tatsächlich von den untergeordneten Aufträgen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a678c-143">The commands are actually run by the child jobs.</span></span> <span data-ttu-id="a678c-144">Aufträge, die mit anderen Cmdlets gestartet wurden, funktionieren möglicherweise anders.</span><span class="sxs-lookup"><span data-stu-id="a678c-144">Jobs started using other cmdlets might work differently.</span></span>

<span data-ttu-id="a678c-145">Die untergeordneten Aufträge werden in der **childjobs** -Eigenschaft des übergeordneten Auftrags Objekts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a678c-145">The child jobs are stored in the **ChildJobs** property of the parent job object.</span></span> <span data-ttu-id="a678c-146">Die **childjobs** -Eigenschaft kann ein oder mehrere untergeordnete Auftrags Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="a678c-146">The **ChildJobs** property can contain one or many child job objects.</span></span>
<span data-ttu-id="a678c-147">Die untergeordneten Auftrags Objekte haben einen **Namen** , eine **ID** und eine **InstanceId** , die sich von dem übergeordneten Auftrag unterscheiden, sodass Sie die übergeordneten und untergeordneten Aufträge einzeln oder als Einheit verwalten können.</span><span class="sxs-lookup"><span data-stu-id="a678c-147">The child job objects have a **Name** , **ID** , and **InstanceId** that differ from the parent job so that you can manage the parent and child jobs individually or as a unit.</span></span>

<span data-ttu-id="a678c-148">Um die übergeordneten und untergeordneten Aufträge eines Auftrags zu erhalten, verwenden Sie den **includechildjobs** -Parameter des `Get-Job` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a678c-148">To get the parent and child jobs of a job, use the **IncludeChildJobs** parameter of the `Get-Job` cmdlet.</span></span> <span data-ttu-id="a678c-149">Der **includechildjob** -Parameter wurde in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a678c-149">The **IncludeChildJob** parameter was introduced in Windows PowerShell 3.0.</span></span>

```powershell
PS> Get-Job -IncludeChildJob

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
1  Job1   RemoteJob     Failed     True          localhost   Get-Process
2  Job2                 Completed  True          Server01    Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="a678c-150">Um den übergeordneten Auftrag und nur die untergeordneten Aufträge mit einem bestimmten **Zustands** Wert zu erhalten, verwenden Sie den **childjobstate** -Parameter des `Get-Job` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a678c-150">To get the parent job and only the child jobs with a particular **State** value, use the **ChildJobState** parameter of the `Get-Job` cmdlet.</span></span> <span data-ttu-id="a678c-151">Der **childjobstate** -Parameter wurde in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a678c-151">The **ChildJobState** parameter was introduced in Windows PowerShell 3.0.</span></span>

```powershell
PS> Get-Job -ChildJobState Failed

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
1  Job1   RemoteJob     Failed     True          localhost   Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="a678c-152">Um die untergeordneten Aufträge eines Auftrags in allen Versionen von PowerShell zu erhalten, verwenden Sie die **childjob** -Eigenschaft des übergeordneten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="a678c-152">To get the child jobs of a job on all versions of PowerShell, use the **ChildJob** property of the parent job.</span></span>

```powershell
PS> (Get-Job Job1).ChildJobs

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
2  Job2                 Completed  True          Server01    Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="a678c-153">Sie können auch einen `Get-Job` Befehl für den untergeordneten Auftrag verwenden, wie im folgenden Befehl gezeigt:</span><span class="sxs-lookup"><span data-stu-id="a678c-153">You can also use a `Get-Job` command on the child job, as shown in the following command:</span></span>

```powershell
PS> Get-Job Job3

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="a678c-154">Die Konfiguration des untergeordneten Auftrags hängt von dem Befehl ab, mit dem der Auftrag gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="a678c-154">The configuration of the child job depends on the command that you use to start the job.</span></span>

- <span data-ttu-id="a678c-155">Wenn Sie verwenden, `Start-Job` um einen Auftrag auf einem lokalen Computer zu starten, besteht der Auftrag aus einem übergeordneten auftragsauftrag und einem untergeordneten Auftrag, der den Befehl ausführt.</span><span class="sxs-lookup"><span data-stu-id="a678c-155">When you use `Start-Job` to start a job on a local computer, the job consists of an executive parent job and a child job that runs the command.</span></span>

- <span data-ttu-id="a678c-156">Wenn Sie den **AsJob** -Parameter von verwenden, `Invoke-Command` um einen Auftrag auf einem oder mehreren Computern zu starten, besteht der Auftrag aus einem übergeordneten auftragsauftrag und einem untergeordneten Auftrag für jeden Auftrag, der auf jedem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a678c-156">When you use the **AsJob** parameter of `Invoke-Command` to start a job on one or more computers, the job consists of an executive parent job and a child job for each job run on each computer.</span></span>

- <span data-ttu-id="a678c-157">Wenn Sie `Invoke-Command` zum Ausführen eines `Start-Job` Befehls auf einem oder mehreren Remote Computern verwenden, ist das Ergebnis das gleiche wie ein lokaler Befehl, der auf jedem Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a678c-157">When you use `Invoke-Command` to run a `Start-Job` command on one or more remote computers, the result is the same as a local command run on each remote computer.</span></span> <span data-ttu-id="a678c-158">Der Befehl gibt für jeden Computer ein Auftrags Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="a678c-158">The command returns a job object for each computer.</span></span> <span data-ttu-id="a678c-159">Das Auftrags Objekt besteht aus einem übergeordneten auftragsauftrag und einem untergeordneten Auftrag, der den Befehl ausführt.</span><span class="sxs-lookup"><span data-stu-id="a678c-159">The job object consists of an executive parent job and one child job that runs the command.</span></span>

<span data-ttu-id="a678c-160">Der übergeordnete Auftrag stellt alle untergeordneten Aufträge dar.</span><span class="sxs-lookup"><span data-stu-id="a678c-160">The parent job represents all of the child jobs.</span></span> <span data-ttu-id="a678c-161">Wenn Sie einen übergeordneten Auftrag verwalten, verwalten Sie auch die zugehörigen untergeordneten Aufträge.</span><span class="sxs-lookup"><span data-stu-id="a678c-161">When you manage a parent job, you also manage the associated child jobs.</span></span> <span data-ttu-id="a678c-162">Wenn Sie z. b. einen übergeordneten Auftrag beenden, werden alle untergeordneten Aufträge angehalten.</span><span class="sxs-lookup"><span data-stu-id="a678c-162">For example, if you stop a parent job, all child jobs are stopped.</span></span> <span data-ttu-id="a678c-163">Wenn Sie die Ergebnisse eines übergeordneten Auftrags erhalten, erhalten Sie die Ergebnisse aller untergeordneten Aufträge.</span><span class="sxs-lookup"><span data-stu-id="a678c-163">If you get the results of a parent job, you get the results of all child jobs.</span></span>

<span data-ttu-id="a678c-164">Sie können jedoch auch untergeordnete Aufträge einzeln verwalten.</span><span class="sxs-lookup"><span data-stu-id="a678c-164">However, you can also manage child jobs individually.</span></span> <span data-ttu-id="a678c-165">Dies ist besonders hilfreich, wenn Sie ein Problem mit einem Auftrag untersuchen oder nur die Ergebnisse einer Reihe von untergeordneten Aufträgen erhalten möchten, die mit dem **AsJob** -Parameter von gestartet wurden `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="a678c-165">This is most useful when you want to investigate a problem with a job or get the results of only one of a number of child jobs started using the **AsJob** parameter of `Invoke-Command`.</span></span>

<span data-ttu-id="a678c-166">Der folgende Befehl verwendet den **AsJob** -Parameter von `Invoke-Command` , um Hintergrund Aufträge auf dem lokalen Computer und auf zwei Remote Computern zu starten.</span><span class="sxs-lookup"><span data-stu-id="a678c-166">The following command uses the **AsJob** parameter of `Invoke-Command` to start background jobs on the local computer and two remote computers.</span></span> <span data-ttu-id="a678c-167">Der Befehl speichert den Auftrag in der `$j` Variablen.</span><span class="sxs-lookup"><span data-stu-id="a678c-167">The command saves the job in the `$j` variable.</span></span>

```powershell
PS> $j = Invoke-Command -ComputerName localhost, Server01, Server02 `
-Command {Get-Date} -AsJob
```

<span data-ttu-id="a678c-168">Wenn Sie die Eigenschaften "Name" und " **childjob** " des Auftrags in anzeigen `$j` , wird angezeigt, dass der Befehl ein Auftrags Objekt mit drei untergeordneten Aufträgen zurückgegeben hat, eines für jeden Computer.</span><span class="sxs-lookup"><span data-stu-id="a678c-168">When you display the Name and **ChildJob** properties of the job in `$j`, it shows that the command returned a job object with three child jobs, one for each computer.</span></span>

```powershell
PS> $j | Format-List Name, ChildJobs

Name      : Job3
ChildJobs : {Job4, Job5, Job6}
```

<span data-ttu-id="a678c-169">Wenn Sie den übergeordneten Auftrag anzeigen, wird angezeigt, dass der Auftrag fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="a678c-169">When you display the parent job, it shows that the job failed.</span></span>

```powershell
PS> $j

Id Name   PSJobTypeName State      HasMoreData   Location
-- ----   ------------- -----      -----------   --------
3  Job3   RemotingJob   Failed     False         localhost,Server...
```

<span data-ttu-id="a678c-170">Wenn Sie jedoch einen Befehl ausführen, `Get-Job` der die untergeordneten Aufträge abruft, zeigt die Ausgabe an, dass nur ein untergeordneter Auftrag fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="a678c-170">But when you run a `Get-Job` command that gets the child jobs, the output shows that only one child job failed.</span></span>

```powershell
PS> Get-Job -IncludeChildJobs

Id  Name   PSJobTypeName State      HasMoreData   Location    Command
--  ----   ------------- -----      -----------   --------    -------
3   Job3   RemotingJob   Failed     False         localhost,Server...
4   Job4                 Completed  True          localhost   Get-Date
5   Job5                 Failed     False         Server01    Get-Date
6   Job6                 Completed  True          Server02    Get-Date
```

<span data-ttu-id="a678c-171">Um die Ergebnisse aller untergeordneten Aufträge zu erhalten, verwenden Sie das `Receive-Job` Cmdlet, um die Ergebnisse des übergeordneten Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a678c-171">To get the results of all child jobs, use the `Receive-Job` cmdlet to get the results of the parent job.</span></span> <span data-ttu-id="a678c-172">Sie können jedoch auch die Ergebnisse eines bestimmten untergeordneten Auftrags erhalten, wie im folgenden Befehl gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a678c-172">But you can also get the results of a particular child job, as shown in the following command.</span></span>

```powershell
PS> Receive-Job -Name Job6 -Keep | Format-Table ComputerName,
>> DateTime -AutoSize
ComputerName DateTime
------------ --------
Server02     Thursday, March 13, 2008 4:16:03 PM
```

<span data-ttu-id="a678c-173">Mit dem Feature für untergeordnete Aufträge von PowerShell-Hintergrund Aufträgen können Sie besser steuern, welche Aufträge Sie ausführen.</span><span class="sxs-lookup"><span data-stu-id="a678c-173">The child jobs feature of PowerShell background jobs gives you more control over the jobs that you run.</span></span>

### <a name="job-types"></a><span data-ttu-id="a678c-174">Auftragstypen</span><span class="sxs-lookup"><span data-stu-id="a678c-174">Job types</span></span>

<span data-ttu-id="a678c-175">PowerShell unterstützt verschiedene Arten von Aufträgen für verschiedene Tasks.</span><span class="sxs-lookup"><span data-stu-id="a678c-175">PowerShell supports different types of jobs for different tasks.</span></span> <span data-ttu-id="a678c-176">Ab Windows PowerShell 3,0 können Entwickler "Auftrags Quell Adapter" schreiben, mit denen PowerShell neue Auftrags Typen hinzugefügt und die Auftrags Quell Adapter in Module eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="a678c-176">Beginning in Windows PowerShell 3.0, developers can write "job source adapters" that add new job types to PowerShell and include the job source adapters in modules.</span></span>
<span data-ttu-id="a678c-177">Wenn Sie das Modul importieren, können Sie den neuen Auftragstyp in Ihrer Sitzung verwenden.</span><span class="sxs-lookup"><span data-stu-id="a678c-177">When you import the module, you can use the new job type in your session.</span></span>

<span data-ttu-id="a678c-178">Das psscheduledjob-Modul fügt z. b. geplante Aufträge hinzu, und das psworkflow-Modul fügt Workflow Aufträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="a678c-178">For example, the PSScheduledJob module adds scheduled jobs and the PSWorkflow module adds workflow jobs.</span></span>

<span data-ttu-id="a678c-179">Benutzerdefinierte Auftrags Typen können sich stark von PowerShell-Standard Hintergrund Aufträgen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="a678c-179">Custom jobs types might differ significantly from standard PowerShell background jobs.</span></span> <span data-ttu-id="a678c-180">Beispielsweise werden geplante Aufträge auf dem Datenträger gespeichert. Sie sind nicht nur in einer bestimmten Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a678c-180">For example, scheduled jobs are saved on disk; they do not exist only in a particular session.</span></span> <span data-ttu-id="a678c-181">Workflow Aufträge können angehalten und fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a678c-181">Workflow jobs can be suspended and resumed.</span></span>

<span data-ttu-id="a678c-182">Die Cmdlets, mit denen Sie benutzerdefinierte Aufträge verwalten, hängen vom Auftragstyp ab.</span><span class="sxs-lookup"><span data-stu-id="a678c-182">The cmdlets that you use to manage custom jobs depend on the job type.</span></span> <span data-ttu-id="a678c-183">Bei manchen verwenden Sie die standardmäßigen Job-Cmdlets, z `Get-Job` `Start-Job` . b. und.</span><span class="sxs-lookup"><span data-stu-id="a678c-183">For some, you use the standard job cmdlets, such as `Get-Job` and `Start-Job`.</span></span> <span data-ttu-id="a678c-184">Andere verfügen über spezialisierte Cmdlets, die nur eine bestimmte Art von Auftrag verwalten.</span><span class="sxs-lookup"><span data-stu-id="a678c-184">Others come with specialized cmdlets that manage only a particular type of job.</span></span> <span data-ttu-id="a678c-185">Ausführliche Informationen zu benutzerdefinierten Auftrags Typen finden Sie in den Hilfe Themen zum Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="a678c-185">For detailed information about custom job types, see the help topics about the job type.</span></span>

<span data-ttu-id="a678c-186">Verwenden Sie das-Cmdlet, um den Auftragstyp eines Auftrags zu ermitteln `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="a678c-186">To find the job type of a job, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="a678c-187">`Get-Job` gibt für verschiedene Auftrags Typen unterschiedliche Auftrags Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="a678c-187">`Get-Job` returns different job objects for different types of jobs.</span></span> <span data-ttu-id="a678c-188">Der Wert der **psjobtypame** -Eigenschaft der Auftrags Objekte, die `Get-Job` zurückgibt, gibt den Auftragstyp an.</span><span class="sxs-lookup"><span data-stu-id="a678c-188">The value of the **PSJobTypeName** property of the job objects that `Get-Job` returns indicates the job type.</span></span>

<span data-ttu-id="a678c-189">In der folgenden Tabelle sind die Auftrags Typen aufgeführt, die in PowerShell enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a678c-189">The following table lists the job types that come with PowerShell.</span></span>

|    <span data-ttu-id="a678c-190">Auftragstyp</span><span class="sxs-lookup"><span data-stu-id="a678c-190">Job Type</span></span>    |                       <span data-ttu-id="a678c-191">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a678c-191">Description</span></span>                        |
| -------------- | -------------------------------------------------------- |
| <span data-ttu-id="a678c-192">Backgroundjob</span><span class="sxs-lookup"><span data-stu-id="a678c-192">BackgroundJob</span></span>  | <span data-ttu-id="a678c-193">Die Verwendung des `Start-Job` Cmdlets wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="a678c-193">Started using the `Start-Job` cmdlet.</span></span>                    |
| <span data-ttu-id="a678c-194">Remotejob</span><span class="sxs-lookup"><span data-stu-id="a678c-194">RemoteJob</span></span>      | <span data-ttu-id="a678c-195">Gestartet mit dem **AsJob** -Parameter des</span><span class="sxs-lookup"><span data-stu-id="a678c-195">Started using the **AsJob** parameter of the</span></span>             |
|                | <span data-ttu-id="a678c-196">`Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a678c-196">`Invoke-Command` cmdlet.</span></span>                                 |
| <span data-ttu-id="a678c-197">PSWorkflowJob</span><span class="sxs-lookup"><span data-stu-id="a678c-197">PSWorkflowJob</span></span>  | <span data-ttu-id="a678c-198">Gestartet mit dem **AsJob** -Parameter eines Workflows.</span><span class="sxs-lookup"><span data-stu-id="a678c-198">Started using the **AsJob** parameter of a workflow.</span></span>     |
| <span data-ttu-id="a678c-199">PSScheduledJob</span><span class="sxs-lookup"><span data-stu-id="a678c-199">PSScheduledJob</span></span> | <span data-ttu-id="a678c-200">Eine Instanz eines geplanten Auftrags, der von einem Auftrags--Vorgang gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="a678c-200">An instance of a scheduled job started by a job trigger.</span></span> |
| <span data-ttu-id="a678c-201">Cimjob</span><span class="sxs-lookup"><span data-stu-id="a678c-201">CIMJob</span></span>         | <span data-ttu-id="a678c-202">Gestartet mit dem **AsJob** -Parameter eines Cmdlets aus einem</span><span class="sxs-lookup"><span data-stu-id="a678c-202">Started using the **AsJob** parameter of a cmdlet from a</span></span> |
|                | <span data-ttu-id="a678c-203">Cdxml-Modul.</span><span class="sxs-lookup"><span data-stu-id="a678c-203">CDXML module.</span></span>                                            |
| <span data-ttu-id="a678c-204">Wmijob</span><span class="sxs-lookup"><span data-stu-id="a678c-204">WMIJob</span></span>         | <span data-ttu-id="a678c-205">Gestartet mit dem **AsJob** -Parameter eines Cmdlets aus einem</span><span class="sxs-lookup"><span data-stu-id="a678c-205">Started using the **AsJob** parameter of a cmdlet from a</span></span> |
|                | <span data-ttu-id="a678c-206">WMI-Modul.</span><span class="sxs-lookup"><span data-stu-id="a678c-206">WMI module.</span></span>                                              |
| <span data-ttu-id="a678c-207">PSEventJob</span><span class="sxs-lookup"><span data-stu-id="a678c-207">PSEventJob</span></span>     | <span data-ttu-id="a678c-208">Erstellt mit `Register-ObjectEvent` und Angeben eines</span><span class="sxs-lookup"><span data-stu-id="a678c-208">Created using`Register-ObjectEvent` and specifying an</span></span>    |
|                | <span data-ttu-id="a678c-209">Aktion mit dem **Action** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="a678c-209">action with the **Action** parameter.</span></span>                    |

<span data-ttu-id="a678c-210">Hinweis: bevor Sie mit dem `Get-Job` Cmdlet Aufträge eines bestimmten Typs erhalten, überprüfen Sie, ob das Modul, das den Auftragstyp hinzufügt, in die aktuelle Sitzung importiert wird.</span><span class="sxs-lookup"><span data-stu-id="a678c-210">NOTE: Before using the `Get-Job` cmdlet to get jobs of a particular type, verify that the module that adds the job type is imported into the current session.</span></span>
<span data-ttu-id="a678c-211">Andernfalls `Get-Job` werden von keine Aufträge dieses Typs erhalten.</span><span class="sxs-lookup"><span data-stu-id="a678c-211">Otherwise, `Get-Job` does not get jobs of that type.</span></span>

## <a name="examples"></a><span data-ttu-id="a678c-212">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a678c-212">Examples</span></span>

<span data-ttu-id="a678c-213">Die folgenden Befehle erstellen einen lokalen Hintergrund Auftrag, einen Remote Hintergrund Auftrag, einen Workflow Auftrag und einen geplanten Auftrag.</span><span class="sxs-lookup"><span data-stu-id="a678c-213">The following commands create a local background job, a remote background job, a workflow job, and a scheduled job.</span></span> <span data-ttu-id="a678c-214">Dann wird das `Get-Job` Cmdlet verwendet, um die Aufträge zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a678c-214">Then, it uses the `Get-Job` cmdlet to get the jobs.</span></span> <span data-ttu-id="a678c-215">`Get-Job` der geplante Auftrag wird nicht abgerufen, aber es werden alle gestarteten Instanzen des geplanten Auftrags abgerufen.</span><span class="sxs-lookup"><span data-stu-id="a678c-215">`Get-Job` does not get the scheduled job, but it gets any started instances of the scheduled job.</span></span>

<span data-ttu-id="a678c-216">Startet einen Hintergrund Auftrag auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="a678c-216">Start a background job on the local computer.</span></span>

```powershell
PS> Start-Job -Name LocalData {Get-Process}

Id Name        PSJobTypeName   State   HasMoreData   Location   Command
-- ----        -------------   -----   -----------   --------   -------
2  LocalData   BackgroundJob   Running        True   localhost  Get-Process
```

<span data-ttu-id="a678c-217">Startet einen Hintergrund Auftrag, der auf einem Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a678c-217">Start a background job that runs on a remote computer.</span></span>

```powershell
PS> Invoke-Command -ComputerName Server01 {Get-Process} `
-AsJob -JobName RemoteData

Id  Name        PSJobTypeName  State   HasMoreData   Location   Command
--  ----        -------------  -----   -----------   --------   -------
2   RemoteData  RemoteJob      Running        True   Server01   Get-Process
```

<span data-ttu-id="a678c-218">Geplanten Auftrag erstellen</span><span class="sxs-lookup"><span data-stu-id="a678c-218">Create a scheduled job</span></span>

```powershell
PS>  Register-ScheduledJob -Name ScheduledJob -ScriptBlock `
 {Get-Process} -Trigger (New-JobTrigger -Once -At "3 PM")

Id         Name            JobTriggers     Command       Enabled
--         ----            -----------     -------       -------
1          ScheduledJob    1               Get-Process   True
```

<span data-ttu-id="a678c-219">Erstellen Sie einen Workflow.</span><span class="sxs-lookup"><span data-stu-id="a678c-219">Create a workflow.</span></span>

```powershell
PS> workflow Test-Workflow {Get-Process}
```

<span data-ttu-id="a678c-220">Führen Sie den Workflow als Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="a678c-220">Run the workflow as a job.</span></span>

```powershell

PS> Test-Workflow -AsJob -JobName TestWFJob

Id  Name       PSJobTypeName   State   HasMoreData   Location   Command
--  ----       -------------   -----   -----------   --------   -------
2   TestWFJob  PSWorkflowJob   NotStarted     True   localhost  Get-Process
```

<span data-ttu-id="a678c-221">Sie erhalten die Aufträge.</span><span class="sxs-lookup"><span data-stu-id="a678c-221">Get the jobs.</span></span> <span data-ttu-id="a678c-222">`Get-Job`Mit dem Befehl werden keine geplanten Aufträge abgerufen, sondern es werden Instanzen des geplanten Auftrags abgerufen, die gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="a678c-222">The `Get-Job` command does not get scheduled jobs, but it gets instances of the scheduled job that are started.</span></span>

```powershell
PS> Get-Job

Id  Name         PSJobTypeName  State     HasMoreData  Location  Command
--  ----         -------------  -----     -----------  --------  -------
2   LocalData    BackgroundJob  Completed True         localhost Get-Process
4   RemoteData   RemoteJob      Completed True         Server01  Get-Process
6   TestWFJob    PSWorkflowJob  Completed True         localhost WorkflowJob
8   ScheduledJob PSScheduledJob Completed True         localhost Get-Process
```

<span data-ttu-id="a678c-223">Verwenden Sie das-Cmdlet, um geplante Aufträge zu erhalten `Get-ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="a678c-223">To get scheduled jobs, use the `Get-ScheduledJob` cmdlet.</span></span>

```powershell
PS> Get-ScheduledJob

Id         Name            JobTriggers     Command       Enabled
--         ----            -----------     -------       -------
1          ScheduledJob    1               Get-Process   True
```

## <a name="see-also"></a><span data-ttu-id="a678c-224">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a678c-224">See also</span></span>

- [<span data-ttu-id="a678c-225">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="a678c-225">about_Jobs</span></span>](about_Jobs.md)
- [<span data-ttu-id="a678c-226">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="a678c-226">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="a678c-227">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="a678c-227">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="a678c-228">about_Remote</span><span class="sxs-lookup"><span data-stu-id="a678c-228">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="a678c-229">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="a678c-229">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [<span data-ttu-id="a678c-230">Start-Job</span><span class="sxs-lookup"><span data-stu-id="a678c-230">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="a678c-231">Get-Job</span><span class="sxs-lookup"><span data-stu-id="a678c-231">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="a678c-232">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="a678c-232">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="a678c-233">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="a678c-233">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="a678c-234">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="a678c-234">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="a678c-235">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="a678c-235">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
- [<span data-ttu-id="a678c-236">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="a678c-236">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)
- [<span data-ttu-id="a678c-237">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="a678c-237">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)
