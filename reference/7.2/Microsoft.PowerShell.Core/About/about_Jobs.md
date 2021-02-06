---
description: Enthält Informationen dazu, wie PowerShell-Hintergrund Aufträge einen Befehl oder Ausdruck im Hintergrund ausführen, ohne mit der aktuellen Sitzung zu interagieren.
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: 862fbf54b927bb70c68e4b3cc43c564f178f9db5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599424"
---
# <a name="about-jobs"></a><span data-ttu-id="72a70-103">Informationen zu Aufträgen</span><span class="sxs-lookup"><span data-stu-id="72a70-103">About Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="72a70-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72a70-104">Short description</span></span>
<span data-ttu-id="72a70-105">Enthält Informationen dazu, wie PowerShell-Hintergrund Aufträge einen Befehl oder Ausdruck im Hintergrund ausführen, ohne mit der aktuellen Sitzung zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="72a70-105">Provides information about how PowerShell background jobs run a command or expression in the background without interacting with the current session.</span></span>

## <a name="long-description"></a><span data-ttu-id="72a70-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72a70-106">Long description</span></span>

<span data-ttu-id="72a70-107">PowerShell führt Befehle und Skripts gleichzeitig durch Aufträge aus.</span><span class="sxs-lookup"><span data-stu-id="72a70-107">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="72a70-108">Es gibt drei Auftrags Typen, die von PowerShell zur Unterstützung von Parallelität bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="72a70-108">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="72a70-109">`RemoteJob` -Befehle und Skripts werden in einer Remote Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="72a70-109">`RemoteJob` - Commands and scripts run on a remote session.</span></span> <span data-ttu-id="72a70-110">Weitere Informationen finden Sie unter [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="72a70-110">For information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
- <span data-ttu-id="72a70-111">`BackgroundJob` -Befehle und Skripts werden in einem separaten Prozess auf dem lokalen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="72a70-111">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span>
- <span data-ttu-id="72a70-112">`PSTaskJob``ThreadJob`-Befehle und-Skripts werden in einem separaten Thread innerhalb desselben Prozesses auf dem lokalen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="72a70-112">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span> <span data-ttu-id="72a70-113">Weitere Informationen finden Sie unter [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span><span class="sxs-lookup"><span data-stu-id="72a70-113">For more information, see [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span></span>

<span data-ttu-id="72a70-114">Das Remote Ausführen von Skripts auf einem separaten Computer oder in einem separaten Prozess bietet eine hohe Isolation.</span><span class="sxs-lookup"><span data-stu-id="72a70-114">Running scripts remotely, on a separate machine or in a separate process, provides great isolation.</span></span> <span data-ttu-id="72a70-115">Fehler, die im Remote Auftrag auftreten, wirken sich nicht auf andere laufende Aufträge oder die übergeordnete Sitzung aus, die den Auftrag gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="72a70-115">Any errors that occur in the remote job do not affect other running jobs or the parent session that started the job.</span></span> <span data-ttu-id="72a70-116">Allerdings erhöht die Remoting-Ebene mehr Aufwand, einschließlich Objektserialisierung.</span><span class="sxs-lookup"><span data-stu-id="72a70-116">However, the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="72a70-117">Alle Objekte werden serialisiert und deserialisiert, wenn Sie zwischen der übergeordneten Sitzung und der Remote Sitzung (Auftrags Sitzung) weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="72a70-117">All objects are serialized and deserialized as they are passed between the parent session and the remote (job) session.</span></span> <span data-ttu-id="72a70-118">Die Serialisierung von großen komplexen Datenobjekten kann große Mengen an COMPUTE-und Speicherressourcen beanspruchen und große Datenmengen über das Netzwerk übertragen.</span><span class="sxs-lookup"><span data-stu-id="72a70-118">Serialization of large complex data objects can consume large amounts of compute and memory resources and transfer large amounts of data across the network.</span></span>

<span data-ttu-id="72a70-119">Thread basierte Aufträge sind nicht so robust wie Remote-und Hintergrund Aufträge, da Sie in demselben Prozess in verschiedenen Threads ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="72a70-119">Thread-based jobs are not as robust as remote and background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="72a70-120">Wenn bei einem Auftrag ein schwerwiegender Fehler auftritt, der den Prozess abstürzt, werden alle anderen Aufträge im Prozess beendet.</span><span class="sxs-lookup"><span data-stu-id="72a70-120">If one job has a critical error that crashes the process, then all other jobs in the process are terminated.</span></span>

<span data-ttu-id="72a70-121">Thread basierte Aufträge erfordern jedoch weniger Aufwand.</span><span class="sxs-lookup"><span data-stu-id="72a70-121">However, thread-based jobs require less overhead.</span></span> <span data-ttu-id="72a70-122">Sie verwenden nicht die Remoting-Schicht oder die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="72a70-122">They don't use the remoting layer or serialization.</span></span> <span data-ttu-id="72a70-123">Die Ergebnis Objekte werden als Verweise auf Live-Objekte in der aktuellen Sitzung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="72a70-123">The result objects are returned as references to live objects in the current session.</span></span> <span data-ttu-id="72a70-124">Ohne diesen Aufwand werden Thread basierte Aufträge schneller ausgeführt und verbrauchen weniger Ressourcen als die anderen Auftrags Typen.</span><span class="sxs-lookup"><span data-stu-id="72a70-124">Without this overhead, thread-based jobs run faster and use fewer resources than the other job types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72a70-125">In der übergeordneten Sitzung, mit der der Auftrag erstellt wurde, wird auch der Auftragsstatus überwacht und Pipeline Daten gesammelt.</span><span class="sxs-lookup"><span data-stu-id="72a70-125">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="72a70-126">Der untergeordnete Prozess des Auftrags wird vom übergeordneten Prozess beendet, sobald der Auftrag den Status "abgeschlossen" erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="72a70-126">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="72a70-127">Wenn die übergeordnete Sitzung beendet wird, werden alle untergeordneten Aufträge zusammen mit ihren untergeordneten Prozessen beendet.</span><span class="sxs-lookup"><span data-stu-id="72a70-127">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="72a70-128">Es gibt zwei Möglichkeiten, diese Situation zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="72a70-128">There are two ways work around this situation:</span></span>

1. <span data-ttu-id="72a70-129">Verwenden `Invoke-Command` Sie, um Aufträge zu erstellen, die in getrennten Sitzungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="72a70-129">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="72a70-130">Weitere Informationen finden Sie unter [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="72a70-130">For more information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
1. <span data-ttu-id="72a70-131">Verwenden `Start-Process` Sie, um anstelle eines Auftrags einen neuen Prozess zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="72a70-131">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="72a70-132">Weitere Informationen finden Sie unter [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span><span class="sxs-lookup"><span data-stu-id="72a70-132">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="72a70-133">Die Job-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="72a70-133">The job cmdlets</span></span>

|<span data-ttu-id="72a70-134">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="72a70-134">Cmdlet</span></span>          |<span data-ttu-id="72a70-135">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="72a70-135">Description</span></span>                                            |
|----------------|-------------------------------------------------------|
|`Start-Job`     |<span data-ttu-id="72a70-136">Startet einen Hintergrundauftrag auf einem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="72a70-136">Starts a background job on a local computer.</span></span>           |
|`Get-Job`       |<span data-ttu-id="72a70-137">Ruft die Hintergrund Aufträge ab, die im</span><span class="sxs-lookup"><span data-stu-id="72a70-137">Gets the background jobs that were started in the</span></span>      |
|                |<span data-ttu-id="72a70-138">aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="72a70-138">current session.</span></span>                                       |
|`Receive-Job`   |<span data-ttu-id="72a70-139">Ruft die Ergebnisse der Hintergrund Aufträge ab.</span><span class="sxs-lookup"><span data-stu-id="72a70-139">Gets the results of background jobs.</span></span>                   |
|`Stop-Job`      |<span data-ttu-id="72a70-140">Beendet einen Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="72a70-140">Stops a background job.</span></span>                                |
|`Wait-Job`      |<span data-ttu-id="72a70-141">Unterdrückt die Eingabeaufforderung, bis ein oder alle Aufträge</span><span class="sxs-lookup"><span data-stu-id="72a70-141">Suppresses the command prompt until one or all jobs are</span></span>|
|                |<span data-ttu-id="72a70-142">ganz.</span><span class="sxs-lookup"><span data-stu-id="72a70-142">complete.</span></span>                                              |
|`Remove-Job`    |<span data-ttu-id="72a70-143">Löscht einen Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="72a70-143">Deletes a background job.</span></span>                              |
|`Invoke-Command`|<span data-ttu-id="72a70-144">Der **AsJob** -Parameter erstellt einen Hintergrund Auftrag auf einem</span><span class="sxs-lookup"><span data-stu-id="72a70-144">The **AsJob** parameter creates a background job on a</span></span>  |
|                |<span data-ttu-id="72a70-145">Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="72a70-145">remote computer.</span></span> <span data-ttu-id="72a70-146">Sie können `Invoke-Command` zum Ausführen von verwenden.</span><span class="sxs-lookup"><span data-stu-id="72a70-146">You can use `Invoke-Command` to run</span></span>   |
|                |<span data-ttu-id="72a70-147">Alle Auftrags Befehle Remote, einschließlich `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="72a70-147">any job command remotely, including `Start-Job`.</span></span>       |

## <a name="how-to-start-a-job-on-the-local-computer"></a><span data-ttu-id="72a70-148">Starten eines Auftrags auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="72a70-148">How to start a job on the local computer</span></span>

<span data-ttu-id="72a70-149">Verwenden Sie das-Cmdlet, um einen Hintergrund Auftrag auf dem lokalen Computer zu starten `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="72a70-149">To start a background job on the local computer, use the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="72a70-150">Um einen Befehl zu schreiben `Start-Job` , schließen Sie den Befehl ein, dass der Auftrag in geschweiften Klammern () ausgeführt wird `{}` .</span><span class="sxs-lookup"><span data-stu-id="72a70-150">To write a `Start-Job` command, enclose the command that the job runs in curly braces (`{}`).</span></span> <span data-ttu-id="72a70-151">Verwenden Sie den **ScriptBlock** -Parameter, um den Befehl anzugeben.</span><span class="sxs-lookup"><span data-stu-id="72a70-151">Use the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="72a70-152">Der folgende Befehl startet einen Hintergrund Auftrag, der einen `Get-Process` Befehl auf dem lokalen Computer ausführt.</span><span class="sxs-lookup"><span data-stu-id="72a70-152">The following command starts a background job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="72a70-153">Wenn Sie einen Hintergrund Auftrag starten, wird die Eingabeaufforderung sofort zurückgegeben, auch wenn die Ausführung des Auftrags längere Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="72a70-153">When you start a background job, the command prompt returns immediately, even if the job takes an extended time to complete.</span></span> <span data-ttu-id="72a70-154">Sie können ohne Unterbrechung in der Sitzung weiterarbeiten, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="72a70-154">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="72a70-155">Der `Start-Job` Befehl gibt ein Objekt zurück, das den Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="72a70-155">The `Start-Job` command returns an object that represents the job.</span></span> <span data-ttu-id="72a70-156">Das Auftragsobjekt enthält nützliche Informationen zum Auftrag, aber keine Auftragsergebnisse.</span><span class="sxs-lookup"><span data-stu-id="72a70-156">The job object contains useful information about the job, but it does not contain the job results.</span></span>

<span data-ttu-id="72a70-157">Sie können das Auftrags Objekt in einer Variablen speichern und dann mit den anderen **Auftrags** -Cmdlets verwenden, um den Hintergrund Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="72a70-157">You can save the job object in a variable and then use it with the other **Job** cmdlets to manage the background job.</span></span> <span data-ttu-id="72a70-158">Der folgende Befehl startet ein Auftrags Objekt und speichert das resultierende Auftrags Objekt in der `$job` Variablen.</span><span class="sxs-lookup"><span data-stu-id="72a70-158">The following command starts a job object and saves the resulting job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="72a70-159">Ab PowerShell 6,0 können Sie den Hintergrund Operator ( `&` ) am Ende einer Pipeline verwenden, um einen Hintergrund Auftrag zu starten.</span><span class="sxs-lookup"><span data-stu-id="72a70-159">Beginning in PowerShell 6.0, you can use the background operator (`&`) at the end of a pipeline to start a background job.</span></span> <span data-ttu-id="72a70-160">Weitere Informationen finden Sie unter [Background-Operator](about_Operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="72a70-160">For more information, see [background operator](about_Operators.md#background-operator-).</span></span>

<span data-ttu-id="72a70-161">Die Verwendung des Background-Operators ist funktional äquivalent zur Verwendung des- `Start-Job` Cmdlets im vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="72a70-161">Using the background operator is functionally equivalent to using the `Start-Job` cmdlet in the previous example.</span></span>

```powershell
$job = Get-Process &
```

## <a name="getting-job-objects"></a><span data-ttu-id="72a70-162">Auftrags Objekte werden erhalten.</span><span class="sxs-lookup"><span data-stu-id="72a70-162">Getting job objects</span></span>

<span data-ttu-id="72a70-163">Das- `Get-Job` Cmdlet gibt Objekte zurück, die die Hintergrund Aufträge darstellen, die in der aktuellen Sitzung gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="72a70-163">The `Get-Job` cmdlet returns objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="72a70-164">Ohne Parameter `Get-Job` gibt alle Aufträge zurück, die in der aktuellen Sitzung gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="72a70-164">Without parameters, `Get-Job` returns all of the jobs that were started in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="72a70-165">Das Auftrags Objekt enthält den Status des Auftrags, der angibt, ob der Auftrag abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="72a70-165">The job object contains the state of the job, which indicates whether the job has finished.</span></span> <span data-ttu-id="72a70-166">Ein fertiggestelltes Auftrag hat den Status " **abgeschlossen** " oder " **failed**".</span><span class="sxs-lookup"><span data-stu-id="72a70-166">A finished job has a state of **Complete** or **Failed**.</span></span> <span data-ttu-id="72a70-167">Ein Auftrag kann auch **blockiert** werden oder **ausgeführt** werden.</span><span class="sxs-lookup"><span data-stu-id="72a70-167">A job might also be **Blocked** or **Running**.</span></span>

```Output
Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

<span data-ttu-id="72a70-168">Sie können das Auftrags Objekt in einer Variablen speichern und es verwenden, um den Auftrag in einem späteren Befehl darzustellen.</span><span class="sxs-lookup"><span data-stu-id="72a70-168">You can save the job object in a variable and use it to represent the job in a later command.</span></span> <span data-ttu-id="72a70-169">Mit dem folgenden Befehl wird der Auftrag mit der ID 1 abgerufen und in der `$job` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="72a70-169">The following command gets the job with ID 1 and saves it in the `$job` variable.</span></span>

```powershell
$job = Get-Job -Id 1
```

## <a name="getting-the-results-of-a-job"></a><span data-ttu-id="72a70-170">Erhalten der Ergebnisse eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="72a70-170">Getting the results of a job</span></span>

<span data-ttu-id="72a70-171">Wenn Sie einen Hintergrund Auftrag ausführen, werden die Ergebnisse nicht sofort angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72a70-171">When you run a background job, the results do not appear immediately.</span></span> <span data-ttu-id="72a70-172">Verwenden Sie das-Cmdlet, um die Ergebnisse eines Hintergrund Auftrags zu erhalten `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="72a70-172">To get the results of a background job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="72a70-173">Im folgenden Beispiel ruft das `Receive-Job` Cmdlet die Ergebnisse des Auftrags mithilfe des Auftrags Objekts in der `$job` Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="72a70-173">The following example, the `Receive-Job` cmdlet gets the results of the job using job object in the `$job` variable.</span></span>

```powershell
Receive-Job -Job $job
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
    103       4    11328       9692    56           1176 audiodg
    804      14    12228      14108   100   101.74  1740 CcmExec
    668       7     2672       6168   104    32.26   488 csrss
...
```

<span data-ttu-id="72a70-174">Sie können die Ergebnisse eines Auftrags in einer Variablen speichern.</span><span class="sxs-lookup"><span data-stu-id="72a70-174">You can save the results of a job in a variable.</span></span> <span data-ttu-id="72a70-175">Der folgende Befehl speichert die Ergebnisse des Auftrags in der `$job` Variablen in der `$results` Variablen.</span><span class="sxs-lookup"><span data-stu-id="72a70-175">The following command saves the results of the job in the `$job` variable to the `$results` variable.</span></span>

```powershell
$results = Receive-Job -Job $job
```

### <a name="getting-and-keeping-partial-job-results"></a><span data-ttu-id="72a70-176">Erhalten und Aufbewahren von partiellen Auftrags Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="72a70-176">Getting and keeping partial job results</span></span>

<span data-ttu-id="72a70-177">Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse eines Hintergrund Auftrags abgerufen.</span><span class="sxs-lookup"><span data-stu-id="72a70-177">The `Receive-Job` cmdlet gets the results of a background job.</span></span> <span data-ttu-id="72a70-178">Wenn der Auftrag vollständig ist, werden `Receive-Job` alle Auftrags Ergebnisse abgerufen.</span><span class="sxs-lookup"><span data-stu-id="72a70-178">If the job is complete, `Receive-Job` gets all job results.</span></span> <span data-ttu-id="72a70-179">Wenn der Auftrag noch ausgeführt wird, ruft `Receive-Job` die bisher generierten Ergebnisse ab.</span><span class="sxs-lookup"><span data-stu-id="72a70-179">If the job is still running, `Receive-Job` gets the results that have been generated thus far.</span></span> <span data-ttu-id="72a70-180">Sie können `Receive-Job` Befehle erneut ausführen, um die verbleibenden Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="72a70-180">You can run `Receive-Job` commands again to get the remaining results.</span></span>

<span data-ttu-id="72a70-181">Standardmäßig `Receive-Job` werden die Ergebnisse aus dem Cache gelöscht, in denen Auftrags Ergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="72a70-181">By default, `Receive-Job` deletes the results from the cache where job results are stored.</span></span> <span data-ttu-id="72a70-182">Wenn Sie `Receive-Job` erneut ausführen, erhalten Sie nur die neuen Ergebnisse, die nach der ersten Ausführung eingetroffen sind.</span><span class="sxs-lookup"><span data-stu-id="72a70-182">When you run `Receive-Job` again, you get only the new results that arrived after the first run.</span></span>

<span data-ttu-id="72a70-183">Die folgenden Befehle zeigen die Ergebnisse von `Receive-Job` Befehlen, die vor Abschluss des Auftrags ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="72a70-183">The following commands show the results of `Receive-Job` commands run before the job is complete.</span></span>

```powershell
C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    68       3     2632        664    29     0.36   1388 ccmsetup
   749      22    21468      19940   203   122.13   3644 communicator
   905       7     2980       2628    34   197.97    424 csrss
  1121      25    28408      32940   174   430.14   3048 explorer
```

<span data-ttu-id="72a70-184">Verwenden Sie den **Keep** -Parameter, um zu verhindern, `Receive-Job` dass die zurückgegebenen Auftrags Ergebnisse gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="72a70-184">Use the **Keep** parameter to prevent `Receive-Job` from deleting the job results that are returned.</span></span> <span data-ttu-id="72a70-185">Die folgenden Befehle zeigen die Auswirkung der Verwendung des **Keep** -Parameters auf einen Auftrag, der noch nicht beendet ist.</span><span class="sxs-lookup"><span data-stu-id="72a70-185">The following commands show the effect of using the **Keep** parameter on a job that is not yet complete.</span></span>

```powershell
C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec
     68       3     2632        664    29     0.36   1388 ccmsetup
    749      22    21468      19940   203   122.13   3644 communicator
    905       7     2980       2628    34   197.97    424 csrss
   1121      25    28408      32940   174   430.14   3048 explorer
```

### <a name="waiting-for-the-results"></a><span data-ttu-id="72a70-186">Warten auf die Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="72a70-186">Waiting for the results</span></span>

<span data-ttu-id="72a70-187">Wenn Sie einen Befehl ausführen, der eine lange Zeit in Anspruch nimmt, können Sie die Eigenschaften des Auftrags Objekts verwenden, um zu bestimmen, wann der Auftrag beendet ist.</span><span class="sxs-lookup"><span data-stu-id="72a70-187">If you run a command that takes a long time to complete, you can use the properties of the job object to determine when the job is complete.</span></span> <span data-ttu-id="72a70-188">Der folgende Befehl verwendet das- `Get-Job` Objekt, um alle Hintergrund Aufträge in der aktuellen Sitzung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="72a70-188">The following command uses the `Get-Job` object to get all of the background jobs in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="72a70-189">Die Ergebnisse werden in einer Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72a70-189">The results appear in a table.</span></span> <span data-ttu-id="72a70-190">Der Status des Auftrags wird in der Spalte **Bundesstaat** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72a70-190">The status of the job appears in the **State** column.</span></span>

```Output
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

<span data-ttu-id="72a70-191">In diesem Fall zeigt die **State** -Eigenschaft an, dass Auftrag 2 noch ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="72a70-191">In this case, the **State** property reveals that Job 2 is still running.</span></span> <span data-ttu-id="72a70-192">Wenn Sie das `Receive-Job` Cmdlet verwenden, um die Auftrags Ergebnisse jetzt zu erhalten, sind die Ergebnisse unvollständig.</span><span class="sxs-lookup"><span data-stu-id="72a70-192">If you were to use the `Receive-Job` cmdlet to get the job results now, the results would be incomplete.</span></span> <span data-ttu-id="72a70-193">Sie können das `Receive-Job` Cmdlet wiederholt verwenden, um alle Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="72a70-193">You can use the `Receive-Job` cmdlet repeatedly to get all of the results.</span></span> <span data-ttu-id="72a70-194">Verwenden Sie die **State** -Eigenschaft, um zu bestimmen, wann der Auftrag beendet ist.</span><span class="sxs-lookup"><span data-stu-id="72a70-194">Use the **State** property to determine when the job is complete.</span></span>

<span data-ttu-id="72a70-195">Sie können auch den **Wait** -Parameter des `Receive-Job` Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="72a70-195">You can also use the **Wait** parameter of the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="72a70-196">Wenn Sie diesen Parameter verwenden, gibt das Cmdlet erst dann die Eingabeaufforderung zurück, wenn der Auftrag abgeschlossen ist und alle Ergebnisse verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="72a70-196">When use use this parameter, the cmdlet does not return the command prompt until the job is completed and all results are available.</span></span>

<span data-ttu-id="72a70-197">Sie können auch das- `Wait-Job` Cmdlet verwenden, um auf ein oder alle Ergebnisse des Auftrags zu warten.</span><span class="sxs-lookup"><span data-stu-id="72a70-197">You can also use the `Wait-Job` cmdlet to wait for any or all of the results of the job.</span></span> <span data-ttu-id="72a70-198">`Wait-Job` ermöglicht das warten auf einen oder mehrere bestimmte Aufträge oder auf alle Aufträge.</span><span class="sxs-lookup"><span data-stu-id="72a70-198">`Wait-Job` lets you wait for one or more specific job or for all jobs.</span></span>
<span data-ttu-id="72a70-199">Der folgende Befehl verwendet das `Wait-Job` Cmdlet, um auf einen Auftrag mit der **ID** zu warten.</span><span class="sxs-lookup"><span data-stu-id="72a70-199">The following command uses the `Wait-Job` cmdlet to wait for a job with **ID**</span></span>
10.

```powershell
Wait-Job -ID 10
```

<span data-ttu-id="72a70-200">Folglich wird die PowerShell-Eingabeaufforderung unterdrückt, bis der Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="72a70-200">As a result, the PowerShell prompt is suppressed until the job is completed.</span></span>

<span data-ttu-id="72a70-201">Sie können auch einen vordefinierten Zeitraum warten.</span><span class="sxs-lookup"><span data-stu-id="72a70-201">You can also wait for a predetermined period of time.</span></span> <span data-ttu-id="72a70-202">Dieser Befehl verwendet den **Timeout** -Parameter, um die Wartezeit auf 120 Sekunden einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="72a70-202">This command uses the **Timeout** parameter to limit the wait to 120 seconds.</span></span> <span data-ttu-id="72a70-203">Wenn die Zeit abläuft, wird die Eingabeaufforderung zurückgegeben, aber der Auftrag wird weiterhin im Hintergrund ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="72a70-203">When the time expires, the command prompt returns, but the job continues to run in the background.</span></span>

```powershell
Wait-Job -ID 10 -Timeout 120
```

## <a name="stopping-a-job"></a><span data-ttu-id="72a70-204">Beenden eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="72a70-204">Stopping a job</span></span>

<span data-ttu-id="72a70-205">Verwenden Sie das-Cmdlet, um einen Hintergrund Auftrag zu unterbinden `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="72a70-205">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="72a70-206">Der folgende Befehl startet einen Auftrag, um jeden Eintrag im System Ereignisprotokoll zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="72a70-206">The following command starts a job to get every entry in the System event log.</span></span> <span data-ttu-id="72a70-207">Das Auftrags Objekt wird in der `$job` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="72a70-207">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-EventLog -Log System}
```

<span data-ttu-id="72a70-208">Mit dem folgenden Befehl wird der Auftrag beendet.</span><span class="sxs-lookup"><span data-stu-id="72a70-208">The following command stops the job.</span></span> <span data-ttu-id="72a70-209">Er verwendet einen Pipeline Operator ( `|` ), um den Auftrag in der `$job` Variablen an zu senden `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="72a70-209">It uses a pipeline operator (`|`) to send the job in the `$job` variable to `Stop-Job`.</span></span>

```powershell
$job | Stop-Job
```

## <a name="deleting-a-job"></a><span data-ttu-id="72a70-210">Löschen eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="72a70-210">Deleting a job</span></span>

<span data-ttu-id="72a70-211">Verwenden Sie das-Cmdlet, um einen Hintergrund Auftrag zu löschen `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="72a70-211">To delete a background job, use the `Remove-Job` cmdlet.</span></span> <span data-ttu-id="72a70-212">Der folgende Befehl löscht den Auftrag in der `$job` Variablen.</span><span class="sxs-lookup"><span data-stu-id="72a70-212">The following command deletes the job in the `$job` variable.</span></span>

```powershell
Remove-Job -Job $job
```

## <a name="investigating-a-failed-job"></a><span data-ttu-id="72a70-213">Untersuchen eines fehlgeschlagenen Auftrags</span><span class="sxs-lookup"><span data-stu-id="72a70-213">Investigating a failed job</span></span>

<span data-ttu-id="72a70-214">Aufträge können aus vielen Gründen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="72a70-214">Jobs can fail for many reasons.</span></span> <span data-ttu-id="72a70-215">das Auftrags Objekt enthält eine **reason** -Eigenschaft, die Informationen über die Ursache des Fehlers enthält.</span><span class="sxs-lookup"><span data-stu-id="72a70-215">the job object contains a **Reason** property that contains information about the cause of the failure.</span></span>

<span data-ttu-id="72a70-216">Im folgenden Beispiel wird ein Auftrag ohne die erforderlichen Anmelde Informationen gestartet.</span><span class="sxs-lookup"><span data-stu-id="72a70-216">The following example starts a job without the required credentials.</span></span>

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}
Get-Job $job

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

<span data-ttu-id="72a70-217">Überprüfen Sie die Eigenschaft **Grund** , um den Fehler zu finden, durch den der Auftrag fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="72a70-217">Inspect the **Reason** property to find the error that caused the job to fail.</span></span>

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

<span data-ttu-id="72a70-218">In diesem Fall ist der Auftrag nicht erfolgreich, weil der Remote Computer explizite Anmelde Informationen zum Ausführen des Befehls benötigt hat.</span><span class="sxs-lookup"><span data-stu-id="72a70-218">In this case, the job failed because the remote computer required explicit credentials to run the command.</span></span> <span data-ttu-id="72a70-219">Die **reason** -Eigenschaft enthält die folgende Meldung:</span><span class="sxs-lookup"><span data-stu-id="72a70-219">The **Reason** property contains the following message:</span></span>

> <span data-ttu-id="72a70-220">Fehler beim Herstellen einer Verbindung mit dem Remote Server mit der folgenden Fehlermeldung: "der Zugriff wurde verweigert."</span><span class="sxs-lookup"><span data-stu-id="72a70-220">Connecting to remote server failed with the following error message: "Access is denied".</span></span>

## <a name="see-also"></a><span data-ttu-id="72a70-221">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="72a70-221">See also</span></span>

- [<span data-ttu-id="72a70-222">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="72a70-222">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="72a70-223">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="72a70-223">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="72a70-224">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="72a70-224">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="72a70-225">about_Remote</span><span class="sxs-lookup"><span data-stu-id="72a70-225">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="72a70-226">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="72a70-226">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="72a70-227">Start-Job</span><span class="sxs-lookup"><span data-stu-id="72a70-227">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="72a70-228">Get-Job</span><span class="sxs-lookup"><span data-stu-id="72a70-228">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="72a70-229">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="72a70-229">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="72a70-230">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="72a70-230">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="72a70-231">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="72a70-231">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="72a70-232">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="72a70-232">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="72a70-233">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="72a70-233">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
