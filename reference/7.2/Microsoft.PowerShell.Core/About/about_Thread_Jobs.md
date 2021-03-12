---
description: Enthält Informationen zu PowerShell-Thread basierten Aufträgen. Ein Thread Auftrag ist eine Art von Hintergrund Auftrag, der einen Befehl oder einen Ausdruck in einem separaten Thread innerhalb des aktuellen Sitzungs Prozesses ausführt.
Locale: en-US
ms.date: 11/11/2020
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: 67f3fc585a8c2d1c3ca98c7336a7e367ed6c66c7
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195874"
---
# <a name="about-thread-jobs"></a><span data-ttu-id="bf82a-104">Informationen über Thread Aufträge</span><span class="sxs-lookup"><span data-stu-id="bf82a-104">About Thread Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="bf82a-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf82a-105">Short description</span></span>

<span data-ttu-id="bf82a-106">Enthält Informationen zu PowerShell-Thread basierten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="bf82a-106">Provides information about PowerShell thread-based jobs.</span></span> <span data-ttu-id="bf82a-107">Ein Thread Auftrag ist eine Art von Hintergrund Auftrag, der einen Befehl oder einen Ausdruck in einem separaten Thread innerhalb des aktuellen Sitzungs Prozesses ausführt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-107">A thread job is a type of background job that runs a command or expression in a separate thread within the current session process.</span></span>

## <a name="long-description"></a><span data-ttu-id="bf82a-108">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf82a-108">Long description</span></span>

<span data-ttu-id="bf82a-109">PowerShell führt Befehle und Skripts gleichzeitig durch Aufträge aus.</span><span class="sxs-lookup"><span data-stu-id="bf82a-109">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="bf82a-110">Es gibt drei Auftrags Typen, die von PowerShell zur Unterstützung von Parallelität bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="bf82a-110">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="bf82a-111">`RemoteJob` -Befehle und Skripts werden in einer Remote Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-111">`RemoteJob` - Commands and scripts run in a remote session.</span></span> <span data-ttu-id="bf82a-112">Weitere Informationen finden Sie unter [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="bf82a-112">For information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
- <span data-ttu-id="bf82a-113">`BackgroundJob` -Befehle und Skripts werden in einem separaten Prozess auf dem lokalen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-113">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span> <span data-ttu-id="bf82a-114">Weitere Informationen finden Sie unter [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="bf82a-114">For more information, see [about_Jobs](about_Jobs.md).</span></span>
- <span data-ttu-id="bf82a-115">`PSTaskJob``ThreadJob`-Befehle und-Skripts werden in einem separaten Thread innerhalb desselben Prozesses auf dem lokalen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-115">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span>

<span data-ttu-id="bf82a-116">Thread basierte Aufträge sind nicht so robust wie Remote-und Hintergrund Aufträge, da Sie in demselben Prozess in verschiedenen Threads ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bf82a-116">Thread-based jobs are not as robust as remote and background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="bf82a-117">Wenn bei einem Auftrag ein schwerwiegender Fehler auftritt, der den Prozess abstürzt, werden alle anderen Aufträge im Prozess beendet.</span><span class="sxs-lookup"><span data-stu-id="bf82a-117">If one job has a critical error that crashes the process, then all other jobs in the process are terminated.</span></span>

<span data-ttu-id="bf82a-118">Thread basierte Aufträge erfordern jedoch weniger Aufwand.</span><span class="sxs-lookup"><span data-stu-id="bf82a-118">However, thread-based jobs require less overhead.</span></span> <span data-ttu-id="bf82a-119">Sie verwenden nicht die Remoting-Schicht oder die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="bf82a-119">They don't use the remoting layer or serialization.</span></span> <span data-ttu-id="bf82a-120">Die Ergebnis Objekte werden als Verweise auf Live-Objekte in der aktuellen Sitzung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bf82a-120">The result objects are returned as references to live objects in the current session.</span></span> <span data-ttu-id="bf82a-121">Ohne diesen Aufwand werden Thread basierte Aufträge schneller ausgeführt und verbrauchen weniger Ressourcen als die anderen Auftrags Typen.</span><span class="sxs-lookup"><span data-stu-id="bf82a-121">Without this overhead, thread-based jobs run faster and use fewer resources than the other job types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf82a-122">In der übergeordneten Sitzung, mit der der Auftrag erstellt wurde, wird auch der Auftragsstatus überwacht und Pipeline Daten gesammelt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-122">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="bf82a-123">Der untergeordnete Prozess des Auftrags wird vom übergeordneten Prozess beendet, sobald der Auftrag den Status "abgeschlossen" erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="bf82a-123">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="bf82a-124">Wenn die übergeordnete Sitzung beendet wird, werden alle untergeordneten Aufträge zusammen mit ihren untergeordneten Prozessen beendet.</span><span class="sxs-lookup"><span data-stu-id="bf82a-124">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="bf82a-125">Es gibt zwei Möglichkeiten, diese Situation zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="bf82a-125">There are two ways work around this situation:</span></span>

1. <span data-ttu-id="bf82a-126">Verwenden `Invoke-Command` Sie, um Aufträge zu erstellen, die in getrennten Sitzungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bf82a-126">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="bf82a-127">Weitere Informationen finden Sie unter [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="bf82a-127">For more information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
1. <span data-ttu-id="bf82a-128">Verwenden `Start-Process` Sie, um anstelle eines Auftrags einen neuen Prozess zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf82a-128">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="bf82a-129">Weitere Informationen finden Sie unter [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span><span class="sxs-lookup"><span data-stu-id="bf82a-129">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="how-to-start-and-manage-thread-based-jobs"></a><span data-ttu-id="bf82a-130">Starten und Verwalten von Thread basierten Aufträgen</span><span class="sxs-lookup"><span data-stu-id="bf82a-130">How to start and manage thread-based jobs</span></span>

<span data-ttu-id="bf82a-131">Es gibt zwei Möglichkeiten, Thread basierte Aufträge zu starten:</span><span class="sxs-lookup"><span data-stu-id="bf82a-131">There are two ways to start thread-based jobs:</span></span>

- <span data-ttu-id="bf82a-132">`Start-ThreadJob` -aus dem **threadjob** -Modul</span><span class="sxs-lookup"><span data-stu-id="bf82a-132">`Start-ThreadJob` - from the **ThreadJob** module</span></span>
- <span data-ttu-id="bf82a-133">`ForEach-Object -Parallel -AsJob` -das parallele Feature wurde in PowerShell 7,0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-133">`ForEach-Object -Parallel -AsJob` - the parallel feature was added in PowerShell 7.0</span></span>

<span data-ttu-id="bf82a-134">Verwenden Sie die gleichen **Auftrags** -Cmdlets, die in [about_Jobs](about_Jobs.md) beschrieben werden, um Thread basierte Aufträge zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="bf82a-134">Use the same **Job** cmdlets described in [about_Jobs](about_Jobs.md) to manage thread-based jobs.</span></span>

### <a name="using-start-threadjob"></a><span data-ttu-id="bf82a-135">Verwenden von `Start-ThreadJob`</span><span class="sxs-lookup"><span data-stu-id="bf82a-135">Using `Start-ThreadJob`</span></span>

<span data-ttu-id="bf82a-136">Das **Thread Job** -Modul wurde zunächst mit PowerShell 6 ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="bf82a-136">The **ThreadJob** module first shipped with PowerShell 6.</span></span> <span data-ttu-id="bf82a-137">Sie kann auch über die PowerShell-Katalog für Windows PowerShell 5,1 installiert werden.</span><span class="sxs-lookup"><span data-stu-id="bf82a-137">It can also be installed from the PowerShell Gallery for Windows PowerShell 5.1.</span></span>

<span data-ttu-id="bf82a-138">Um einen Thread Auftrag auf dem lokalen Computer zu starten, verwenden Sie das `Start-ThreadJob` Cmdlet mit einem Befehl oder Skript, der in geschweiften Klammern () eingeschlossen ist `{ }` .</span><span class="sxs-lookup"><span data-stu-id="bf82a-138">To start a thread job on the local computer, use the `Start-ThreadJob` cmdlet with a command or script enclosed in curly braces (`{ }`).</span></span>

<span data-ttu-id="bf82a-139">Im folgenden Beispiel wird ein Thread Auftrag gestartet, der einen `Get-Process` Befehl auf dem lokalen Computer ausführt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-139">The following example starts a thread job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

<span data-ttu-id="bf82a-140">Der `Start-ThreadJob` Befehl gibt ein- `ThreadJob` Objekt zurück, das den laufenden Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-140">The `Start-ThreadJob` command returns a `ThreadJob` object that represents the running job.</span></span> <span data-ttu-id="bf82a-141">Das Auftrags Objekt enthält nützliche Informationen zum Auftrag, einschließlich des aktuellen Status.</span><span class="sxs-lookup"><span data-stu-id="bf82a-141">The job object contains useful information about the job including its current running status.</span></span> <span data-ttu-id="bf82a-142">Die Ergebnisse des Auftrags werden erfasst, wenn die Ergebnisse generiert werden.</span><span class="sxs-lookup"><span data-stu-id="bf82a-142">It collects the results of the job as the results are being generated.</span></span>

### <a name="using-foreach-object--parallel--asjob"></a><span data-ttu-id="bf82a-143">Verwenden von `ForEach-Object -Parallel -AsJob`</span><span class="sxs-lookup"><span data-stu-id="bf82a-143">Using `ForEach-Object -Parallel -AsJob`</span></span>

<span data-ttu-id="bf82a-144">PowerShell 7,0 hat dem Cmdlet einen neuen Parameter hinzugefügt `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="bf82a-144">PowerShell 7.0 added a new parameter set to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="bf82a-145">Die neuen Parameter ermöglichen es Ihnen, Skriptblöcke in parallelen Threads als PowerShell-Aufträge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bf82a-145">The new parameters allow you to run script blocks in parallel threads as PowerShell jobs.</span></span>

<span data-ttu-id="bf82a-146">Sie können Daten über die Pipeline an senden `ForEach-Object -Parallel` .</span><span class="sxs-lookup"><span data-stu-id="bf82a-146">You can pipe data to `ForEach-Object -Parallel`.</span></span> <span data-ttu-id="bf82a-147">Die Daten werden an den Skriptblock, der parallel ausgeführt wird, übermittelt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-147">The data is passed to the script block that is run in parallel.</span></span> <span data-ttu-id="bf82a-148">Der- `-AsJob` Parameter erstellt Auftrags Objekte für jeden paralleler Thread.</span><span class="sxs-lookup"><span data-stu-id="bf82a-148">The `-AsJob` parameter creates jobs objects for each of the parallel threads.</span></span>

<span data-ttu-id="bf82a-149">Der folgende Befehl startet einen Auftrag, der untergeordnete Aufträge für jeden Eingabe Wert enthält, der an den Befehl weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="bf82a-149">The following command starts a job that contains child jobs for each input value piped to the command.</span></span> <span data-ttu-id="bf82a-150">Jeder untergeordnete Auftrag führt den `Write-Output` Befehl mit einem weitergeleiteten Eingabe Wert als Argument aus.</span><span class="sxs-lookup"><span data-stu-id="bf82a-150">Each child job runs the `Write-Output` command with a piped input value as the argument.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob
```

<span data-ttu-id="bf82a-151">Der `ForEach-Object -Parallel` Befehl gibt ein- `PSTaskJob` Objekt zurück, das untergeordnete Aufträge für jeden weitergeleiteten Eingabe Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="bf82a-151">The `ForEach-Object -Parallel` command returns a `PSTaskJob` object that contains child jobs for each piped input value.</span></span> <span data-ttu-id="bf82a-152">Das Auftrags Objekt enthält nützliche Informationen über die untergeordneten Aufträge, in denen der Status ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bf82a-152">The job object contains useful information about the child jobs running status.</span></span> <span data-ttu-id="bf82a-153">Die Ergebnisse der untergeordneten Aufträge werden erfasst, wenn die Ergebnisse generiert werden.</span><span class="sxs-lookup"><span data-stu-id="bf82a-153">It collects the results of the child jobs as the results are being generated.</span></span>

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a><span data-ttu-id="bf82a-154">Warten auf den Abschluss eines Auftrags und Abrufen von Auftrags Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="bf82a-154">How to wait for a job to complete and retrieve job results</span></span>

<span data-ttu-id="bf82a-155">Sie können PowerShell-Auftrags-Cmdlets wie und verwenden, `Wait-Job` `Receive-Job` um auf den Abschluss eines Auftrags zu warten und dann alle vom Auftrag generierten Ergebnisse zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="bf82a-155">You can use PowerShell job cmdlets, such as `Wait-Job` and `Receive-Job` to wait for a job to complete and then return all results generated by the job.</span></span>

<span data-ttu-id="bf82a-156">Mit dem folgenden Befehl wird ein Thread Auftrag gestartet, der einen- `Get-Process` Befehl ausführt, auf den Abschluss des Befehls wartet und schließlich alle vom Befehl generierten Daten Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-156">The following command starts a thread job that runs a `Get-Process` command, then waits for the command to complete, and finally returns all data results generated by the command.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

<span data-ttu-id="bf82a-157">Der folgende Befehl startet einen Auftrag, der einen `Write-Output` Befehl für jede weitergeleitete Eingabe ausführt, dann auf den Abschluss aller untergeordneten Aufträge wartet und schließlich alle von den untergeordneten Aufträgen generierten Daten Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-157">The following command starts a job that runs a `Write-Output` command for each piped input, then waits for all child jobs to complete, and finally returns all data results generated by the child jobs.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="bf82a-158">Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse der untergeordneten Aufträge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bf82a-158">The `Receive-Job` cmdlet returns the results of the child jobs.</span></span>

```powershell
1
3
2
4
5
```

<span data-ttu-id="bf82a-159">Da jeder untergeordnete Auftrag parallel ausgeführt wird, ist die Reihenfolge der generierten Ergebnisse nicht sichergestellt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-159">Because each child job runs parallel, the order of the generated results is not guaranteed.</span></span>

## <a name="thread-job-performance"></a><span data-ttu-id="bf82a-160">Thread Auftrags Leistung</span><span class="sxs-lookup"><span data-stu-id="bf82a-160">Thread job performance</span></span>

<span data-ttu-id="bf82a-161">Thread Aufträge sind schneller und leichter gewichtet als andere Arten von Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="bf82a-161">Thread jobs are faster and lighter weight than other types of jobs.</span></span> <span data-ttu-id="bf82a-162">Allerdings haben Sie immer noch mehr Aufwand, die im Vergleich zu den Aufgaben, die der Auftrag leistet, groß sein können.</span><span class="sxs-lookup"><span data-stu-id="bf82a-162">But they still have overhead that can be large when compared to work the job is doing.</span></span>

<span data-ttu-id="bf82a-163">PowerShell führt Befehle und Skripts in einer Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="bf82a-163">PowerShell runs commands and script in a session.</span></span> <span data-ttu-id="bf82a-164">In einer Sitzung kann jeweils nur ein Befehl oder ein Skript ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bf82a-164">Only one command or script can run at a time in a session.</span></span> <span data-ttu-id="bf82a-165">Wenn also mehrere Aufträge ausgeführt werden, wird jeder Auftrag in einer separaten Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-165">So when running multiple jobs, each job runs in a separate session.</span></span> <span data-ttu-id="bf82a-166">Jede Sitzung trägt zum Aufwand bei.</span><span class="sxs-lookup"><span data-stu-id="bf82a-166">Each session contributes to the overhead.</span></span>

<span data-ttu-id="bf82a-167">Thread Aufträge bieten die beste Leistung, wenn die von Ihnen ausgeführten Aufgaben größer sind als der Aufwand der Sitzung, die zum Ausführen des Auftrags verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bf82a-167">Thread jobs provide the best performance when the work they perform is greater than the overhead of the session used to run the job.</span></span> <span data-ttu-id="bf82a-168">Es gibt zwei Fälle für, die diese Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="bf82a-168">There are two cases for that meet this criteria.</span></span>

- <span data-ttu-id="bf82a-169">Arbeit ist Rechen intensiv: das Ausführen eines Skripts für mehrere Thread Aufträge kann mehrere Prozessorkerne nutzen und schneller ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bf82a-169">Work is compute intensive - Running a script on multiple thread jobs can take advantage of multiple processor cores and complete faster.</span></span>

- <span data-ttu-id="bf82a-170">Die Arbeit besteht aus einem erheblichen Wartezustand. ein Skript, das Zeit für das warten auf e/a-oder Remote Aufruf Ergebnisse verbringt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-170">Work consists of significant waiting - A script that spends time waiting for I/O or remote call results.</span></span> <span data-ttu-id="bf82a-171">Die parallele Ausführung wird normalerweise schneller abgeschlossen als bei der sequenziellen Ausführung.</span><span class="sxs-lookup"><span data-stu-id="bf82a-171">Running in parallel usually completes quicker than if run sequentially.</span></span>

```powershell
(Measure-Command {
    1..1000 | ForEach { Start-ThreadJob { Write-Output "Hello $using:_" } } | Receive-Job -Wait
}).TotalMilliseconds
36860.8226

(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
7.1975
```

<span data-ttu-id="bf82a-172">Das erste Beispiel oben zeigt eine foreach-Schleife, die 1000 Thread Aufträge erstellt, um eine einfache Zeichenfolge zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="bf82a-172">The first example above shows a foreach loop that creates 1000 thread jobs to do a simple string write.</span></span> <span data-ttu-id="bf82a-173">Aufgrund des Auftrags Aufwands dauert der Abschluss von mehr als 36 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="bf82a-173">Due to job overhead, it takes over 36 seconds to complete.</span></span>

<span data-ttu-id="bf82a-174">Das zweite Beispiel führt das `ForEach` Cmdlet aus, um die gleichen 1000-Vorgänge durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="bf82a-174">The second example runs the `ForEach` cmdlet to do the same 1000 operations.</span></span>
<span data-ttu-id="bf82a-175">Dieses Mal wird `ForEach-Object` sequenziell in einem einzelnen Thread ausgeführt, ohne dass ein Auftrag mehr Aufwand erfordert.</span><span class="sxs-lookup"><span data-stu-id="bf82a-175">This time, `ForEach-Object` runs sequentially, on a single thread, without any job overhead.</span></span> <span data-ttu-id="bf82a-176">Sie wird in nur 7 Millisekunden abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bf82a-176">It completes in a mere 7 milliseconds.</span></span>

<span data-ttu-id="bf82a-177">Im folgenden Beispiel werden bis zu 5000 Einträge für 10 separate Systemprotokolle gesammelt.</span><span class="sxs-lookup"><span data-stu-id="bf82a-177">In the following example, up to 5000 entries are collected for 10 separate system logs.</span></span> <span data-ttu-id="bf82a-178">Da das Skript eine Reihe von Protokollen liest, ist es sinnvoll, die Vorgänge parallel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bf82a-178">Since the script involves reading a number of logs, it makes sense to do the operations in parallel.</span></span>

```powershell
$logNames.count
10

Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

<span data-ttu-id="bf82a-179">Das Skript wird in der Hälfte der Zeit abgeschlossen, wenn die Aufträge parallel ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bf82a-179">The script completes in half the time when the jobs are run in parallel.</span></span>

```powershell
Measure-Command {
    $logs = $logNames | ForEach {
        Start-ThreadJob {
            Get-WinEvent -LogName $using:_ -MaxEvents 5000 2>$null
        } -ThrottleLimit 10
    } | Wait-Job | Receive-Job
}

TotalMilliseconds : 115994.3 (1 minute 56 seconds)
$logs.Count
50000
```

## <a name="thread-jobs-and-variables"></a><span data-ttu-id="bf82a-180">Thread Aufträge und-Variablen</span><span class="sxs-lookup"><span data-stu-id="bf82a-180">Thread jobs and variables</span></span>

<span data-ttu-id="bf82a-181">Es gibt mehrere Möglichkeiten, Werte in Thread basierte Aufträge zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="bf82a-181">There are multiple ways to pass values into the thread-based jobs.</span></span>

<span data-ttu-id="bf82a-182">`Start-ThreadJob` kann Variablen akzeptieren, die an das Cmdlet weitergeleitet werden, über das Schlüsselwort an den Skriptblock übergeben `$using` oder über den Argument **List** -Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="bf82a-182">`Start-ThreadJob` can accept variables that are piped to the cmdlet, passed in to the script block via the `$using` keyword, or passed in via the **ArgumentList** parameter.</span></span>

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job
```

<span data-ttu-id="bf82a-183">`ForEach-Object -Parallel` akzeptiert weitergeleitete Variablen und Variablen, die über das-Schlüsselwort direkt an den Skriptblock übergeben werden `$using` .</span><span class="sxs-lookup"><span data-stu-id="bf82a-183">`ForEach-Object -Parallel` accepts piped in variables, and variables passed directly to the script block via the `$using` keyword.</span></span>

```powershell
$msg = "Hello"

$msg | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job

1..1 | ForEach-Object -Parallel { Write-Output $using:msg } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="bf82a-184">Da Thread Aufträge in demselben Prozess ausgeführt werden, müssen alle an den Auftrag über gegebenen Variablen Verweis Typen sorgfältig behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="bf82a-184">Since thread jobs run in the same process, any variable reference type passed into the job has to be treated carefully.</span></span> <span data-ttu-id="bf82a-185">Wenn es sich nicht um ein Thread sicheres Objekt handelt, sollte es niemals zugewiesen werden, und die-Methode und die-Eigenschaften sollten niemals darauf aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bf82a-185">If it is not a thread safe object, then it should never be assigned to, and method and properties should never be invoked on it.</span></span>

<span data-ttu-id="bf82a-186">Im folgenden Beispiel wird ein Thread sicheres .net- `ConcurrentDictionary` Objekt an alle untergeordneten Aufträge weitergeleitet, um eindeutig benannte Prozess Objekte zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="bf82a-186">The following example passes a thread-safe .NET `ConcurrentDictionary` object to all child jobs to collect uniquely named process objects.</span></span> <span data-ttu-id="bf82a-187">Da es sich um ein Thread sicheres Objekt handelt, kann es sicher verwendet werden, während die Aufträge gleichzeitig im Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bf82a-187">Since it is a thread safe object, it can be safely used while the jobs run concurrently in the process.</span></span>

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
$jobs = Get-Process | ForEach {
    Start-ThreadJob {
        $proc = $using:_
        $dict = $using:threadSafeDictionary
        $dict.TryAdd($proc.ProcessName, $proc)
    }
}
$jobs | Wait-Job | Receive-Job

$threadSafeDictionary.Count
96

$threadSafeDictionary["pwsh"]

NPM(K)  PM(M)   WS(M) CPU(s)    Id SI ProcessName
------  -----   ----- ------    -- -- -----------
  112  108.25  124.43  69.75 16272  1 pwsh
```

## <a name="see-also"></a><span data-ttu-id="bf82a-188">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="bf82a-188">See also</span></span>

- [<span data-ttu-id="bf82a-189">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="bf82a-189">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="bf82a-190">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="bf82a-190">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="bf82a-191">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="bf82a-191">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="bf82a-192">about_Remote</span><span class="sxs-lookup"><span data-stu-id="bf82a-192">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="bf82a-193">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="bf82a-193">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="bf82a-194">Start-Job</span><span class="sxs-lookup"><span data-stu-id="bf82a-194">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="bf82a-195">Get-Job</span><span class="sxs-lookup"><span data-stu-id="bf82a-195">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="bf82a-196">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="bf82a-196">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="bf82a-197">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="bf82a-197">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="bf82a-198">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="bf82a-198">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="bf82a-199">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="bf82a-199">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
