---
description: Enthält Informationen dazu, wie PowerShell-Hintergrund Aufträge einen Befehl oder Ausdruck im Hintergrund ausführen, ohne mit der aktuellen Sitzung zu interagieren.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: 6ddb54bac62e7bc11a045874700acb3982a0093b
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524455"
---
# <a name="about-jobs"></a><span data-ttu-id="59195-104">Informationen zu Aufträgen</span><span class="sxs-lookup"><span data-stu-id="59195-104">About Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="59195-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59195-105">Short description</span></span>
<span data-ttu-id="59195-106">Enthält Informationen dazu, wie PowerShell-Hintergrund Aufträge einen Befehl oder Ausdruck im Hintergrund ausführen, ohne mit der aktuellen Sitzung zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="59195-106">Provides information about how PowerShell background jobs run a command or expression in the background without interacting with the current session.</span></span>

## <a name="long-description"></a><span data-ttu-id="59195-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59195-107">Long description</span></span>

<span data-ttu-id="59195-108">PowerShell führt Befehle und Skripts gleichzeitig durch Aufträge aus.</span><span class="sxs-lookup"><span data-stu-id="59195-108">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="59195-109">Es gibt drei Auftrags Typen, die von PowerShell zur Unterstützung von Parallelität bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="59195-109">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="59195-110">`RemoteJob` -Befehle und Skripts werden in einer Remote Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="59195-110">`RemoteJob` - Commands and scripts run on a remote session.</span></span> <span data-ttu-id="59195-111">Weitere Informationen finden Sie unter [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="59195-111">For information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
- <span data-ttu-id="59195-112">`BackgroundJob` -Befehle und Skripts werden in einem separaten Prozess auf dem lokalen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="59195-112">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span>
- <span data-ttu-id="59195-113">`PSTaskJob``ThreadJob`-Befehle und-Skripts werden in einem separaten Thread innerhalb desselben Prozesses auf dem lokalen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="59195-113">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span> <span data-ttu-id="59195-114">Weitere Informationen finden Sie unter [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span><span class="sxs-lookup"><span data-stu-id="59195-114">For more information, see [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span></span>

<span data-ttu-id="59195-115">Das Remote Ausführen von Skripts auf einem separaten Computer oder in einem separaten Prozess bietet eine hohe Isolation.</span><span class="sxs-lookup"><span data-stu-id="59195-115">Running scripts remotely, on a separate machine or in a separate process, provides great isolation.</span></span> <span data-ttu-id="59195-116">Fehler, die im Remote Auftrag auftreten, wirken sich nicht auf andere laufende Aufträge oder die übergeordnete Sitzung aus, die den Auftrag gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="59195-116">Any errors that occur in the remote job do not affect other running jobs or the parent session that started the job.</span></span> <span data-ttu-id="59195-117">Allerdings erhöht die Remoting-Ebene mehr Aufwand, einschließlich Objektserialisierung.</span><span class="sxs-lookup"><span data-stu-id="59195-117">However, the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="59195-118">Alle Objekte werden serialisiert und deserialisiert, wenn Sie zwischen der übergeordneten Sitzung und der Remote Sitzung (Auftrags Sitzung) weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="59195-118">All objects are serialized and deserialized as they are passed between the parent session and the remote (job) session.</span></span> <span data-ttu-id="59195-119">Die Serialisierung von großen komplexen Datenobjekten kann große Mengen an COMPUTE-und Speicherressourcen beanspruchen und große Datenmengen über das Netzwerk übertragen.</span><span class="sxs-lookup"><span data-stu-id="59195-119">Serialization of large complex data objects can consume large amounts of compute and memory resources and transfer large amounts of data across the network.</span></span>

<span data-ttu-id="59195-120">Thread basierte Aufträge sind nicht so robust wie Remote-und Hintergrund Aufträge, da Sie in demselben Prozess in verschiedenen Threads ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="59195-120">Thread-based jobs are not as robust as remote and background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="59195-121">Wenn bei einem Auftrag ein schwerwiegender Fehler auftritt, der den Prozess abstürzt, werden alle anderen Aufträge im Prozess beendet.</span><span class="sxs-lookup"><span data-stu-id="59195-121">If one job has a critical error that crashes the process, then all other jobs in the process are terminated.</span></span>

<span data-ttu-id="59195-122">Thread basierte Aufträge erfordern jedoch weniger Aufwand.</span><span class="sxs-lookup"><span data-stu-id="59195-122">However, thread-based jobs require less overhead.</span></span> <span data-ttu-id="59195-123">Sie verwenden nicht die Remoting-Schicht oder die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="59195-123">They don't use the remoting layer or serialization.</span></span> <span data-ttu-id="59195-124">Die Ergebnis Objekte werden als Verweise auf Live-Objekte in der aktuellen Sitzung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="59195-124">The result objects are returned as references to live objects in the current session.</span></span> <span data-ttu-id="59195-125">Ohne diesen Aufwand werden Thread basierte Aufträge schneller ausgeführt und verbrauchen weniger Ressourcen als die anderen Auftrags Typen.</span><span class="sxs-lookup"><span data-stu-id="59195-125">Without this overhead, thread-based jobs run faster and use fewer resources than the other job types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59195-126">In der übergeordneten Sitzung, mit der der Auftrag erstellt wurde, wird auch der Auftragsstatus überwacht und Pipeline Daten gesammelt.</span><span class="sxs-lookup"><span data-stu-id="59195-126">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="59195-127">Der untergeordnete Prozess des Auftrags wird vom übergeordneten Prozess beendet, sobald der Auftrag den Status "abgeschlossen" erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="59195-127">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="59195-128">Wenn die übergeordnete Sitzung beendet wird, werden alle untergeordneten Aufträge zusammen mit ihren untergeordneten Prozessen beendet.</span><span class="sxs-lookup"><span data-stu-id="59195-128">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="59195-129">Es gibt zwei Möglichkeiten, diese Einschränkung zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="59195-129">There are two ways work around this limitation:</span></span>

1. <span data-ttu-id="59195-130">Verwenden `Invoke-Command` Sie, um Aufträge zu erstellen, die in getrennten Sitzungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="59195-130">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="59195-131">Weitere Informationen finden Sie unter [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="59195-131">For more information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
1. <span data-ttu-id="59195-132">Verwenden `Start-Process` Sie, um anstelle eines Auftrags einen neuen Prozess zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="59195-132">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="59195-133">Weitere Informationen finden Sie unter [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span><span class="sxs-lookup"><span data-stu-id="59195-133">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="59195-134">Die Job-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="59195-134">The job cmdlets</span></span>

|<span data-ttu-id="59195-135">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="59195-135">Cmdlet</span></span>          |<span data-ttu-id="59195-136">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="59195-136">Description</span></span>                                            |
|----------------|-------------------------------------------------------|
|`Start-Job`     |<span data-ttu-id="59195-137">Startet einen Hintergrundauftrag auf einem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="59195-137">Starts a background job on a local computer.</span></span>           |
|`Get-Job`       |<span data-ttu-id="59195-138">Ruft die Hintergrund Aufträge ab, die im</span><span class="sxs-lookup"><span data-stu-id="59195-138">Gets the background jobs that were started in the</span></span>      |
|                |<span data-ttu-id="59195-139">aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="59195-139">current session.</span></span>                                       |
|`Receive-Job`   |<span data-ttu-id="59195-140">Ruft die Ergebnisse der Hintergrund Aufträge ab.</span><span class="sxs-lookup"><span data-stu-id="59195-140">Gets the results of background jobs.</span></span>                   |
|`Stop-Job`      |<span data-ttu-id="59195-141">Beendet einen Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="59195-141">Stops a background job.</span></span>                                |
|`Wait-Job`      |<span data-ttu-id="59195-142">Unterdrückt die Eingabeaufforderung, bis ein oder alle Aufträge</span><span class="sxs-lookup"><span data-stu-id="59195-142">Suppresses the command prompt until one or all jobs are</span></span>|
|                |<span data-ttu-id="59195-143">ganz.</span><span class="sxs-lookup"><span data-stu-id="59195-143">complete.</span></span>                                              |
|`Remove-Job`    |<span data-ttu-id="59195-144">Löscht einen Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="59195-144">Deletes a background job.</span></span>                              |
|`Invoke-Command`|<span data-ttu-id="59195-145">Der **AsJob** -Parameter erstellt einen Hintergrund Auftrag auf einem</span><span class="sxs-lookup"><span data-stu-id="59195-145">The **AsJob** parameter creates a background job on a</span></span>  |
|                |<span data-ttu-id="59195-146">Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="59195-146">remote computer.</span></span> <span data-ttu-id="59195-147">Sie können `Invoke-Command` zum Ausführen von verwenden.</span><span class="sxs-lookup"><span data-stu-id="59195-147">You can use `Invoke-Command` to run</span></span>   |
|                |<span data-ttu-id="59195-148">Alle Auftrags Befehle Remote, einschließlich `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="59195-148">any job command remotely, including `Start-Job`.</span></span>       |

## <a name="how-to-start-a-job-on-the-local-computer"></a><span data-ttu-id="59195-149">Starten eines Auftrags auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="59195-149">How to start a job on the local computer</span></span>

<span data-ttu-id="59195-150">Verwenden Sie das-Cmdlet, um einen Hintergrund Auftrag auf dem lokalen Computer zu starten `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="59195-150">To start a background job on the local computer, use the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="59195-151">Um einen Befehl zu schreiben `Start-Job` , schließen Sie den Befehl ein, dass der Auftrag in geschweiften Klammern () ausgeführt wird `{}` .</span><span class="sxs-lookup"><span data-stu-id="59195-151">To write a `Start-Job` command, enclose the command that the job runs in curly braces (`{}`).</span></span> <span data-ttu-id="59195-152">Verwenden Sie den **ScriptBlock** -Parameter, um den Befehl anzugeben.</span><span class="sxs-lookup"><span data-stu-id="59195-152">Use the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="59195-153">Der folgende Befehl startet einen Hintergrund Auftrag, der einen `Get-Process` Befehl auf dem lokalen Computer ausführt.</span><span class="sxs-lookup"><span data-stu-id="59195-153">The following command starts a background job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="59195-154">Wenn Sie einen Hintergrund Auftrag starten, wird die Eingabeaufforderung sofort zurückgegeben, auch wenn die Ausführung des Auftrags längere Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="59195-154">When you start a background job, the command prompt returns immediately, even if the job takes an extended time to complete.</span></span> <span data-ttu-id="59195-155">Sie können ohne Unterbrechung in der Sitzung weiterarbeiten, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="59195-155">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="59195-156">Der `Start-Job` Befehl gibt ein Objekt zurück, das den Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="59195-156">The `Start-Job` command returns an object that represents the job.</span></span> <span data-ttu-id="59195-157">Das Auftragsobjekt enthält nützliche Informationen zum Auftrag, aber keine Auftragsergebnisse.</span><span class="sxs-lookup"><span data-stu-id="59195-157">The job object contains useful information about the job, but it does not contain the job results.</span></span>

<span data-ttu-id="59195-158">Sie können das Auftrags Objekt in einer Variablen speichern und dann mit den anderen **Auftrags** -Cmdlets verwenden, um den Hintergrund Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="59195-158">You can save the job object in a variable and then use it with the other **Job** cmdlets to manage the background job.</span></span> <span data-ttu-id="59195-159">Der folgende Befehl startet ein Auftrags Objekt und speichert das resultierende Auftrags Objekt in der `$job` Variablen.</span><span class="sxs-lookup"><span data-stu-id="59195-159">The following command starts a job object and saves the resulting job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="59195-160">Ab PowerShell 6,0 können Sie den Hintergrund Operator ( `&` ) am Ende einer Pipeline verwenden, um einen Hintergrund Auftrag zu starten.</span><span class="sxs-lookup"><span data-stu-id="59195-160">Beginning in PowerShell 6.0, you can use the background operator (`&`) at the end of a pipeline to start a background job.</span></span> <span data-ttu-id="59195-161">Weitere Informationen finden Sie unter [Background-Operator](about_Operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="59195-161">For more information, see [background operator](about_Operators.md#background-operator-).</span></span>

<span data-ttu-id="59195-162">Die Verwendung des Background-Operators ist funktional äquivalent zur Verwendung des- `Start-Job` Cmdlets im vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="59195-162">Using the background operator is functionally equivalent to using the `Start-Job` cmdlet in the previous example.</span></span>

```powershell
$job = Get-Process &
```

## <a name="getting-job-objects"></a><span data-ttu-id="59195-163">Auftrags Objekte werden erhalten.</span><span class="sxs-lookup"><span data-stu-id="59195-163">Getting job objects</span></span>

<span data-ttu-id="59195-164">Das- `Get-Job` Cmdlet gibt Objekte zurück, die die Hintergrund Aufträge darstellen, die in der aktuellen Sitzung gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="59195-164">The `Get-Job` cmdlet returns objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="59195-165">Ohne Parameter `Get-Job` gibt alle Aufträge zurück, die in der aktuellen Sitzung gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="59195-165">Without parameters, `Get-Job` returns all of the jobs that were started in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="59195-166">Das Auftrags Objekt enthält den Status des Auftrags, der angibt, ob der Auftrag abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="59195-166">The job object contains the state of the job, which indicates whether the job has finished.</span></span> <span data-ttu-id="59195-167">Ein fertiggestelltes Auftrag hat den Status " **abgeschlossen** " oder " **failed** ".</span><span class="sxs-lookup"><span data-stu-id="59195-167">A finished job has a state of **Complete** or **Failed**.</span></span> <span data-ttu-id="59195-168">Ein Auftrag kann auch **blockiert** werden oder **ausgeführt** werden.</span><span class="sxs-lookup"><span data-stu-id="59195-168">A job might also be **Blocked** or **Running**.</span></span>

```Output
Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

<span data-ttu-id="59195-169">Sie können das Auftrags Objekt in einer Variablen speichern und es verwenden, um den Auftrag in einem späteren Befehl darzustellen.</span><span class="sxs-lookup"><span data-stu-id="59195-169">You can save the job object in a variable and use it to represent the job in a later command.</span></span> <span data-ttu-id="59195-170">Mit dem folgenden Befehl wird der Auftrag mit der ID 1 abgerufen und in der `$job` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="59195-170">The following command gets the job with ID 1 and saves it in the `$job` variable.</span></span>

```powershell
$job = Get-Job -Id 1
```

## <a name="getting-the-results-of-a-job"></a><span data-ttu-id="59195-171">Erhalten der Ergebnisse eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="59195-171">Getting the results of a job</span></span>

<span data-ttu-id="59195-172">Wenn Sie einen Hintergrund Auftrag ausführen, werden die Ergebnisse nicht sofort angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59195-172">When you run a background job, the results do not appear immediately.</span></span> <span data-ttu-id="59195-173">Verwenden Sie das-Cmdlet, um die Ergebnisse eines Hintergrund Auftrags zu erhalten `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="59195-173">To get the results of a background job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="59195-174">Im folgenden Beispiel ruft das `Receive-Job` Cmdlet die Ergebnisse des Auftrags mithilfe des Auftrags Objekts in der `$job` Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="59195-174">The following example, the `Receive-Job` cmdlet gets the results of the job using job object in the `$job` variable.</span></span>

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

<span data-ttu-id="59195-175">Sie können die Ergebnisse eines Auftrags in einer Variablen speichern.</span><span class="sxs-lookup"><span data-stu-id="59195-175">You can save the results of a job in a variable.</span></span> <span data-ttu-id="59195-176">Der folgende Befehl speichert die Ergebnisse des Auftrags in der `$job` Variablen in der `$results` Variablen.</span><span class="sxs-lookup"><span data-stu-id="59195-176">The following command saves the results of the job in the `$job` variable to the `$results` variable.</span></span>

```powershell
$results = Receive-Job -Job $job
```

### <a name="getting-and-keeping-partial-job-results"></a><span data-ttu-id="59195-177">Erhalten und Aufbewahren von partiellen Auftrags Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="59195-177">Getting and keeping partial job results</span></span>

<span data-ttu-id="59195-178">Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse eines Hintergrund Auftrags abgerufen.</span><span class="sxs-lookup"><span data-stu-id="59195-178">The `Receive-Job` cmdlet gets the results of a background job.</span></span> <span data-ttu-id="59195-179">Wenn der Auftrag vollständig ist, werden `Receive-Job` alle Auftrags Ergebnisse abgerufen.</span><span class="sxs-lookup"><span data-stu-id="59195-179">If the job is complete, `Receive-Job` gets all job results.</span></span> <span data-ttu-id="59195-180">Wenn der Auftrag noch ausgeführt wird, ruft `Receive-Job` die bisher generierten Ergebnisse ab.</span><span class="sxs-lookup"><span data-stu-id="59195-180">If the job is still running, `Receive-Job` gets the results that have been generated thus far.</span></span> <span data-ttu-id="59195-181">Sie können `Receive-Job` Befehle erneut ausführen, um die verbleibenden Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="59195-181">You can run `Receive-Job` commands again to get the remaining results.</span></span>

<span data-ttu-id="59195-182">Standardmäßig `Receive-Job` werden die Ergebnisse aus dem Cache gelöscht, in denen Auftrags Ergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="59195-182">By default, `Receive-Job` deletes the results from the cache where job results are stored.</span></span> <span data-ttu-id="59195-183">Wenn Sie `Receive-Job` erneut ausführen, erhalten Sie nur die neuen Ergebnisse, die nach der ersten Ausführung eingetroffen sind.</span><span class="sxs-lookup"><span data-stu-id="59195-183">When you run `Receive-Job` again, you get only the new results that arrived after the first run.</span></span>

<span data-ttu-id="59195-184">Die folgenden Befehle zeigen die Ergebnisse von `Receive-Job` Befehlen, die vor Abschluss des Auftrags ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="59195-184">The following commands show the results of `Receive-Job` commands run before the job is complete.</span></span>

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

<span data-ttu-id="59195-185">Verwenden Sie den **Keep** -Parameter, um zu verhindern, `Receive-Job` dass die zurückgegebenen Auftrags Ergebnisse gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="59195-185">Use the **Keep** parameter to prevent `Receive-Job` from deleting the job results that are returned.</span></span> <span data-ttu-id="59195-186">Die folgenden Befehle zeigen die Auswirkung der Verwendung des **Keep** -Parameters auf einen Auftrag, der noch nicht beendet ist.</span><span class="sxs-lookup"><span data-stu-id="59195-186">The following commands show the effect of using the **Keep** parameter on a job that is not yet complete.</span></span>

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

### <a name="waiting-for-the-results"></a><span data-ttu-id="59195-187">Warten auf die Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="59195-187">Waiting for the results</span></span>

<span data-ttu-id="59195-188">Wenn Sie einen Befehl ausführen, der eine lange Zeit in Anspruch nimmt, können Sie die Eigenschaften des Auftrags Objekts verwenden, um zu bestimmen, wann der Auftrag beendet ist.</span><span class="sxs-lookup"><span data-stu-id="59195-188">If you run a command that takes a long time to complete, you can use the properties of the job object to determine when the job is complete.</span></span> <span data-ttu-id="59195-189">Der folgende Befehl verwendet das- `Get-Job` Objekt, um alle Hintergrund Aufträge in der aktuellen Sitzung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="59195-189">The following command uses the `Get-Job` object to get all of the background jobs in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="59195-190">Die Ergebnisse werden in einer Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59195-190">The results appear in a table.</span></span> <span data-ttu-id="59195-191">Der Status des Auftrags wird in der Spalte **Bundesstaat** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59195-191">The status of the job appears in the **State** column.</span></span>

```Output
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

<span data-ttu-id="59195-192">In diesem Fall zeigt die **State** -Eigenschaft an, dass Auftrag 2 noch ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="59195-192">In this case, the **State** property reveals that Job 2 is still running.</span></span> <span data-ttu-id="59195-193">Wenn Sie das `Receive-Job` Cmdlet verwenden, um die Auftrags Ergebnisse jetzt zu erhalten, sind die Ergebnisse unvollständig.</span><span class="sxs-lookup"><span data-stu-id="59195-193">If you were to use the `Receive-Job` cmdlet to get the job results now, the results would be incomplete.</span></span> <span data-ttu-id="59195-194">Sie können das `Receive-Job` Cmdlet wiederholt verwenden, um alle Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="59195-194">You can use the `Receive-Job` cmdlet repeatedly to get all of the results.</span></span> <span data-ttu-id="59195-195">Verwenden Sie die **State** -Eigenschaft, um zu bestimmen, wann der Auftrag beendet ist.</span><span class="sxs-lookup"><span data-stu-id="59195-195">Use the **State** property to determine when the job is complete.</span></span>

<span data-ttu-id="59195-196">Sie können auch den **Wait** -Parameter des `Receive-Job` Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="59195-196">You can also use the **Wait** parameter of the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="59195-197">Wenn Sie diesen Parameter verwenden, gibt das Cmdlet erst dann die Eingabeaufforderung zurück, wenn der Auftrag abgeschlossen ist und alle Ergebnisse verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="59195-197">When use use this parameter, the cmdlet does not return the command prompt until the job is completed and all results are available.</span></span>

<span data-ttu-id="59195-198">Sie können auch das- `Wait-Job` Cmdlet verwenden, um auf ein oder alle Ergebnisse des Auftrags zu warten.</span><span class="sxs-lookup"><span data-stu-id="59195-198">You can also use the `Wait-Job` cmdlet to wait for any or all of the results of the job.</span></span> <span data-ttu-id="59195-199">`Wait-Job` ermöglicht das warten auf einen oder mehrere bestimmte Aufträge oder auf alle Aufträge.</span><span class="sxs-lookup"><span data-stu-id="59195-199">`Wait-Job` lets you wait for one or more specific job or for all jobs.</span></span>
<span data-ttu-id="59195-200">Der folgende Befehl verwendet das `Wait-Job` Cmdlet, um auf einen Auftrag mit der **ID** zu warten.</span><span class="sxs-lookup"><span data-stu-id="59195-200">The following command uses the `Wait-Job` cmdlet to wait for a job with **ID**</span></span>
10.

```powershell
Wait-Job -ID 10
```

<span data-ttu-id="59195-201">Folglich wird die PowerShell-Eingabeaufforderung unterdrückt, bis der Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="59195-201">As a result, the PowerShell prompt is suppressed until the job is completed.</span></span>

<span data-ttu-id="59195-202">Sie können auch einen vordefinierten Zeitraum warten.</span><span class="sxs-lookup"><span data-stu-id="59195-202">You can also wait for a predetermined period of time.</span></span> <span data-ttu-id="59195-203">Dieser Befehl verwendet den **Timeout** -Parameter, um die Wartezeit auf 120 Sekunden einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="59195-203">This command uses the **Timeout** parameter to limit the wait to 120 seconds.</span></span> <span data-ttu-id="59195-204">Wenn die Zeit abläuft, wird die Eingabeaufforderung zurückgegeben, aber der Auftrag wird weiterhin im Hintergrund ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="59195-204">When the time expires, the command prompt returns, but the job continues to run in the background.</span></span>

```powershell
Wait-Job -ID 10 -Timeout 120
```

## <a name="stopping-a-job"></a><span data-ttu-id="59195-205">Beenden eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="59195-205">Stopping a job</span></span>

<span data-ttu-id="59195-206">Verwenden Sie das-Cmdlet, um einen Hintergrund Auftrag zu unterbinden `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="59195-206">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="59195-207">Der folgende Befehl startet einen Auftrag, um jeden Eintrag im System Ereignisprotokoll zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="59195-207">The following command starts a job to get every entry in the System event log.</span></span> <span data-ttu-id="59195-208">Das Auftrags Objekt wird in der `$job` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="59195-208">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-EventLog -Log System}
```

<span data-ttu-id="59195-209">Mit dem folgenden Befehl wird der Auftrag beendet.</span><span class="sxs-lookup"><span data-stu-id="59195-209">The following command stops the job.</span></span> <span data-ttu-id="59195-210">Er verwendet einen Pipeline Operator ( `|` ), um den Auftrag in der `$job` Variablen an zu senden `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="59195-210">It uses a pipeline operator (`|`) to send the job in the `$job` variable to `Stop-Job`.</span></span>

```powershell
$job | Stop-Job
```

## <a name="deleting-a-job"></a><span data-ttu-id="59195-211">Löschen eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="59195-211">Deleting a job</span></span>

<span data-ttu-id="59195-212">Verwenden Sie das-Cmdlet, um einen Hintergrund Auftrag zu löschen `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="59195-212">To delete a background job, use the `Remove-Job` cmdlet.</span></span> <span data-ttu-id="59195-213">Der folgende Befehl löscht den Auftrag in der `$job` Variablen.</span><span class="sxs-lookup"><span data-stu-id="59195-213">The following command deletes the job in the `$job` variable.</span></span>

```powershell
Remove-Job -Job $job
```

## <a name="investigating-a-failed-job"></a><span data-ttu-id="59195-214">Untersuchen eines fehlgeschlagenen Auftrags</span><span class="sxs-lookup"><span data-stu-id="59195-214">Investigating a failed job</span></span>

<span data-ttu-id="59195-215">Aufträge können aus vielen Gründen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="59195-215">Jobs can fail for many reasons.</span></span> <span data-ttu-id="59195-216">das Auftrags Objekt enthält eine **reason** -Eigenschaft, die Informationen über die Ursache des Fehlers enthält.</span><span class="sxs-lookup"><span data-stu-id="59195-216">the job object contains a **Reason** property that contains information about the cause of the failure.</span></span>

<span data-ttu-id="59195-217">Im folgenden Beispiel wird ein Auftrag ohne die erforderlichen Anmelde Informationen gestartet.</span><span class="sxs-lookup"><span data-stu-id="59195-217">The following example starts a job without the required credentials.</span></span>

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}
Get-Job $job

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

<span data-ttu-id="59195-218">Überprüfen Sie die Eigenschaft **Grund** , um den Fehler zu finden, durch den der Auftrag fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="59195-218">Inspect the **Reason** property to find the error that caused the job to fail.</span></span>

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

<span data-ttu-id="59195-219">In diesem Fall ist der Auftrag nicht erfolgreich, weil der Remote Computer explizite Anmelde Informationen zum Ausführen des Befehls benötigt hat.</span><span class="sxs-lookup"><span data-stu-id="59195-219">In this case, the job failed because the remote computer required explicit credentials to run the command.</span></span> <span data-ttu-id="59195-220">Die **reason** -Eigenschaft enthält die folgende Meldung:</span><span class="sxs-lookup"><span data-stu-id="59195-220">The **Reason** property contains the following message:</span></span>

> <span data-ttu-id="59195-221">Fehler beim Herstellen einer Verbindung mit dem Remote Server mit der folgenden Fehlermeldung: "der Zugriff wurde verweigert."</span><span class="sxs-lookup"><span data-stu-id="59195-221">Connecting to remote server failed with the following error message: "Access is denied".</span></span>

## <a name="see-also"></a><span data-ttu-id="59195-222">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59195-222">See also</span></span>

- [<span data-ttu-id="59195-223">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="59195-223">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="59195-224">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="59195-224">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="59195-225">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="59195-225">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="59195-226">about_Remote</span><span class="sxs-lookup"><span data-stu-id="59195-226">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="59195-227">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="59195-227">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="59195-228">Start-Job</span><span class="sxs-lookup"><span data-stu-id="59195-228">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="59195-229">Get-Job</span><span class="sxs-lookup"><span data-stu-id="59195-229">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="59195-230">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="59195-230">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="59195-231">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="59195-231">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="59195-232">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="59195-232">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="59195-233">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="59195-233">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="59195-234">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="59195-234">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
