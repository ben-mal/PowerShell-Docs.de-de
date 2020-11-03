---
description: Enthält Informationen zu PowerShell-Thread basierten Aufträgen. Ein Thread Auftrag ist eine Art von Hintergrund Auftrag, der einen Befehl oder einen Ausdruck in einem separaten Thread innerhalb des aktuellen Sitzungs Prozesses ausführt.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/16/2020
online version: 1.0.0
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: d3f7c2754a2e54bc1b6f9fb95d1cf6ce2fed5b9b
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "93224591"
---
# <a name="about-thread-jobs"></a><span data-ttu-id="a87f2-105">Informationen über Thread Aufträge</span><span class="sxs-lookup"><span data-stu-id="a87f2-105">About Thread Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="a87f2-106">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a87f2-106">Short description</span></span>

<span data-ttu-id="a87f2-107">Enthält Informationen zu PowerShell-Thread basierten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="a87f2-107">Provides information about PowerShell thread-based jobs.</span></span> <span data-ttu-id="a87f2-108">Ein Thread Auftrag ist eine Art von Hintergrund Auftrag, der einen Befehl oder einen Ausdruck in einem separaten Thread innerhalb des aktuellen Sitzungs Prozesses ausführt.</span><span class="sxs-lookup"><span data-stu-id="a87f2-108">A thread job is a type of background job that runs a command or expression in a separate thread within the current session process.</span></span>

## <a name="long-description"></a><span data-ttu-id="a87f2-109">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a87f2-109">Long description</span></span>

<span data-ttu-id="a87f2-110">In diesem Artikel wird erläutert, wie Thread Aufträge in PowerShell auf einem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-110">This article explains how to run thread jobs in PowerShell on a local computer.</span></span>
<span data-ttu-id="a87f2-111">Informationen zum Ausführen von Hintergrund Aufträgen auf einem lokalen Computer finden Sie unter [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="a87f2-111">For information about running background jobs on a local computer, see [about_Jobs](about_Jobs.md).</span></span>

<span data-ttu-id="a87f2-112">Es gibt zwei Möglichkeiten, einen Thread Auftrag zu starten.</span><span class="sxs-lookup"><span data-stu-id="a87f2-112">You can start a thread job in one of two ways.</span></span>

<span data-ttu-id="a87f2-113">Die erste Möglichkeit ist die Verwendung des- `Start-ThreadJob` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a87f2-113">The first way is with the `Start-ThreadJob` cmdlet.</span></span> <span data-ttu-id="a87f2-114">Dieses Cmdlet ist im **Thread Job** -Modul verfügbar, das im Lieferumfang von PowerShell enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a87f2-114">This cmdlet is available in the **ThreadJob** module that ships with PowerShell.</span></span> <span data-ttu-id="a87f2-115">`Start-ThreadJob` Gibt ein einzelnes Auftrags Objekt zurück, das den laufenden Befehl oder das Skript kapselt und mit allen PowerShell-Cmdlets für die Auftragsbearbeitung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a87f2-115">`Start-ThreadJob` returns a single job object that encapsulates the running command or script, and can be used with all PowerShell job manipulating cmdlets.</span></span>

<span data-ttu-id="a87f2-116">Die zweite Möglichkeit ist mit dem- `ForEach-Object` Cmdlet, mit dem `-Parallel` Parameter Skriptblock Argument zusammen mit dem `-AsJob` Parameter Switch.</span><span class="sxs-lookup"><span data-stu-id="a87f2-116">The second way is with the `ForEach-Object` cmdlet, with the `-Parallel` parameter script block argument along with the `-AsJob` parameter switch.</span></span> <span data-ttu-id="a87f2-117">Dieses Cmdlet gibt ein einzelnes (übergeordnetes) Auftrags Objekt zurück, das einen untergeordneten Auftrag für jede Eingabe enthält, die an das Cmdlet weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="a87f2-117">This cmdlet returns a single (parent) job object that contains a child job for each input piped to the cmdlet.</span></span> <span data-ttu-id="a87f2-118">Jeder untergeordnete Auftrag führt das Skript in einem separaten Thread mit einem ( `-ThrottleLimit` )-Limit aus, um die Anzahl der untergeordneten Aufträge zu einem bestimmten Zeitpunkt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a87f2-118">Each child job runs script in a separate thread with a (`-ThrottleLimit`) limit to how many child jobs run at a given time.</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="a87f2-119">die Job-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a87f2-119">THE JOB CMDLETS</span></span>

|<span data-ttu-id="a87f2-120">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a87f2-120">Cmdlet</span></span>           |<span data-ttu-id="a87f2-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a87f2-121">Description</span></span>                                            |
|-----------------|-------------------------------------------------------|
|`Start-ThreadJob`|<span data-ttu-id="a87f2-122">Startet einen Thread Auftrag auf einem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="a87f2-122">Starts a thread job on a local computer.</span></span>               |
|`ForEach-Object` |<span data-ttu-id="a87f2-123">Startet Thread Aufträge für jedes weitergeleitete Eingabe Objekt, wenn</span><span class="sxs-lookup"><span data-stu-id="a87f2-123">Starts thread jobs for each piped input object, when</span></span>   |
|                 |<span data-ttu-id="a87f2-124">wird mit-parallel-und-AsJob-Parametern verwendet.</span><span class="sxs-lookup"><span data-stu-id="a87f2-124">used with -Parallel and -AsJob parameters.</span></span>             |
|`Get-Job`        |<span data-ttu-id="a87f2-125">Ruft die Aufträge ab, die in der aktuellen Sitzung gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-125">Gets the jobs that were started in the current session.</span></span>|
|`Receive-Job`    |<span data-ttu-id="a87f2-126">Ruft die Ergebnisse der Aufträge ab.</span><span class="sxs-lookup"><span data-stu-id="a87f2-126">Gets the results of jobs.</span></span>                              |
|`Stop-Job`       |<span data-ttu-id="a87f2-127">Beendet einen laufenden Auftrag.</span><span class="sxs-lookup"><span data-stu-id="a87f2-127">Stops a running job.</span></span>                                   |
|`Wait-Job`       |<span data-ttu-id="a87f2-128">Unterdrückt die Eingabeaufforderung, bis ein oder alle Aufträge</span><span class="sxs-lookup"><span data-stu-id="a87f2-128">Suppresses the command prompt until one or all jobs are</span></span>|
|                 |<span data-ttu-id="a87f2-129">ganz.</span><span class="sxs-lookup"><span data-stu-id="a87f2-129">complete.</span></span>                                              |
|`Remove-Job`     |<span data-ttu-id="a87f2-130">Löscht einen Auftrag.</span><span class="sxs-lookup"><span data-stu-id="a87f2-130">Deletes a job.</span></span>                                         |

## <a name="how-to-start-a-thread-job-on-the-local-computer"></a><span data-ttu-id="a87f2-131">Starten eines Thread Auftrags auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="a87f2-131">How to start a thread job on the local computer</span></span>

<span data-ttu-id="a87f2-132">Verwenden Sie das-Cmdlet, um einen Thread Auftrag auf dem lokalen Computer zu starten `Start-ThreadJob` .</span><span class="sxs-lookup"><span data-stu-id="a87f2-132">To start a thread job on the local computer, use the `Start-ThreadJob` cmdlet.</span></span>

<span data-ttu-id="a87f2-133">Wenn Sie einen `Start-ThreadJob` Befehl schreiben möchten, schließen Sie den Befehl oder das Skript für den Auftrag in geschweiften Klammern ( `{ }` ) ein.</span><span class="sxs-lookup"><span data-stu-id="a87f2-133">To write a `Start-ThreadJob` command, enclose the command or script the job runs in curly braces (`{ }`).</span></span>

<span data-ttu-id="a87f2-134">Mit dem folgenden Befehl wird ein Thread Auftrag gestartet, der einen `Get-Process` Befehl auf dem lokalen Computer ausführt.</span><span class="sxs-lookup"><span data-stu-id="a87f2-134">The following command starts a thread job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

<span data-ttu-id="a87f2-135">Der `Start-ThreadJob` Befehl gibt ein- `ThreadJob` Objekt zurück, das den laufenden Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="a87f2-135">The `Start-ThreadJob` command returns a `ThreadJob` object that represents the running job.</span></span> <span data-ttu-id="a87f2-136">Das Auftrags Objekt enthält nützliche Informationen zum Auftrag, einschließlich des aktuellen Status.</span><span class="sxs-lookup"><span data-stu-id="a87f2-136">The job object contains useful information about the job including its current running status.</span></span> <span data-ttu-id="a87f2-137">Die Ergebnisse des Auftrags werden erfasst, wenn die Ergebnisse generiert werden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-137">It collects the results of the job as the results are being generated.</span></span>

<span data-ttu-id="a87f2-138">Um einen Befehl zu schreiben `ForEach-Object -Parallel` , übergeben Sie Daten an den Befehl, und schließen Sie den Befehl oder das Skript für den Auftrag in geschweiften Klammern ( `{}` ) ein.</span><span class="sxs-lookup"><span data-stu-id="a87f2-138">To write a `ForEach-Object -Parallel` command, pipe data to the command and enclose the command or script the job runs in curly braces(`{}`).</span></span> <span data-ttu-id="a87f2-139">Verwenden Sie den `-AsJob` Parameter Switch, damit ein Job-Objekt zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a87f2-139">Use the `-AsJob` parameter switch so that a job object is returned.</span></span>

<span data-ttu-id="a87f2-140">Der folgende Befehl startet einen Auftrag, der untergeordnete Aufträge für jeden Eingabe Wert enthält, der an den Befehl weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="a87f2-140">The following command starts a job that contains child jobs for each input value piped to the command.</span></span> <span data-ttu-id="a87f2-141">Jeder untergeordnete Auftrag führt den `Write-Output` Befehl mit einem weitergeleiteten Eingabe Wert als Argument aus.</span><span class="sxs-lookup"><span data-stu-id="a87f2-141">Each child job runs the `Write-Output` command with a piped input value as the argument.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob
```

<span data-ttu-id="a87f2-142">Der `ForEach-Object -Parallel` Befehl gibt ein- `PSTaskJob` Objekt zurück, das untergeordnete Aufträge für jeden weitergeleiteten Eingabe Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="a87f2-142">The `ForEach-Object -Parallel` command returns a `PSTaskJob` object that contains child jobs for each piped input value.</span></span> <span data-ttu-id="a87f2-143">Das Auftrags Objekt enthält nützliche Informationen über die untergeordneten Aufträge, in denen der Status ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a87f2-143">The job object contains useful information about the child jobs running status.</span></span> <span data-ttu-id="a87f2-144">Die Ergebnisse der untergeordneten Aufträge werden erfasst, wenn die Ergebnisse generiert werden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-144">It collects the results of the child jobs as the results are being generated.</span></span>

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a><span data-ttu-id="a87f2-145">Warten auf den Abschluss eines Auftrags und Abrufen von Auftrags Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a87f2-145">How to wait for a job to complete and retrieve job results</span></span>

<span data-ttu-id="a87f2-146">Sie können PowerShell-Auftrags-Cmdlets wie und verwenden, `Wait-Job` `Receive-Job` um auf den Abschluss eines Auftrags zu warten und dann alle vom Auftrag generierten Ergebnisse zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="a87f2-146">You can use PowerShell job cmdlets, such as `Wait-Job` and `Receive-Job` to wait for a job to complete and then return all results generated by the job.</span></span>

<span data-ttu-id="a87f2-147">Mit dem folgenden Befehl wird ein Thread Auftrag gestartet, der einen- `Get-Process` Befehl ausführt, auf den Abschluss des Befehls wartet und schließlich alle vom Befehl generierten Daten Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a87f2-147">The following command starts a thread job that runs a `Get-Process` command, then waits for the command to complete, and finally returns all data results generated by the command.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

<span data-ttu-id="a87f2-148">Der folgende Befehl startet einen Auftrag, der einen `Write-Output` Befehl für jede weitergeleitete Eingabe ausführt, dann auf den Abschluss aller untergeordneten Aufträge wartet und schließlich alle von den untergeordneten Aufträgen generierten Daten Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a87f2-148">The following command starts a job that runs a `Write-Output` command for each piped input, then waits for all child jobs to complete, and finally returns all data results generated by the child jobs.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="a87f2-149">Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse der untergeordneten Aufträge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a87f2-149">The `Receive-Job` cmdlet returns the results of the child jobs.</span></span>

```powershell
1
3
2
4
5
```

<span data-ttu-id="a87f2-150">Da jeder untergeordnete Auftrag parallel ausgeführt wird, ist die Reihenfolge der generierten Ergebnisse nicht sichergestellt.</span><span class="sxs-lookup"><span data-stu-id="a87f2-150">Because each child job runs parallel, the order of the generated results is not guaranteed.</span></span>

## <a name="powershell-concurrency-and-jobs"></a><span data-ttu-id="a87f2-151">PowerShell-Parallelität und-Aufträge</span><span class="sxs-lookup"><span data-stu-id="a87f2-151">PowerShell concurrency and jobs</span></span>

<span data-ttu-id="a87f2-152">PowerShell führt gleichzeitig Befehle und Skripts durch Aufträge aus.</span><span class="sxs-lookup"><span data-stu-id="a87f2-152">PowerShell concurrently runs commands and script through jobs.</span></span> <span data-ttu-id="a87f2-153">Es gibt drei auf Aufträgen basierende Lösungen, die von PowerShell zur Unterstützung von Parallelität bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-153">There are three jobs-based solutions provided by PowerShell to support concurrency.</span></span>

|<span data-ttu-id="a87f2-154">Auftrag</span><span class="sxs-lookup"><span data-stu-id="a87f2-154">Job</span></span>            |<span data-ttu-id="a87f2-155">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a87f2-155">Description</span></span>                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |<span data-ttu-id="a87f2-156">Befehl und Skript werden auf einem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a87f2-156">Command and script run on a remote computer.</span></span>                 |
|`BackgroundJob`|<span data-ttu-id="a87f2-157">Befehl und Skript werden in einem separaten Prozess auf dem lokalen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a87f2-157">Command and script run in a separate process on the local</span></span>    |
|               |<span data-ttu-id="a87f2-158">2 virtuelle CPUs zu.</span><span class="sxs-lookup"><span data-stu-id="a87f2-158">machine.</span></span>                                                     |
|`ThreadJob`    |<span data-ttu-id="a87f2-159">Befehl und Skript werden in einem separaten Thread innerhalb desselben</span><span class="sxs-lookup"><span data-stu-id="a87f2-159">Command and script run in a separate thread within the same</span></span>  |
|               |<span data-ttu-id="a87f2-160">Prozess auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="a87f2-160">process on the local machine.</span></span>                                |

<span data-ttu-id="a87f2-161">Jeder Auftragstyp hat Vorteile und Nachteile.</span><span class="sxs-lookup"><span data-stu-id="a87f2-161">Each type of job has benefits and drawbacks.</span></span> <span data-ttu-id="a87f2-162">Die Remote Ausführung von Skripts auf einem separaten Computer oder in einem separaten Prozess hat eine große Isolation.</span><span class="sxs-lookup"><span data-stu-id="a87f2-162">Running script remotely on a separate machine or in a separate process has great isolation.</span></span> <span data-ttu-id="a87f2-163">Alle Fehler wirken sich nicht auf andere laufende Aufträge oder den Client aus, von dem der Auftrag gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="a87f2-163">Any errors won't affect other running jobs or the client that started the job.</span></span> <span data-ttu-id="a87f2-164">Die Remoting-Schicht erhöht jedoch den mehr Aufwand, einschließlich Objektserialisierung.</span><span class="sxs-lookup"><span data-stu-id="a87f2-164">But the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="a87f2-165">Alle Objekte, die an und von der Remote Sitzung weitergeleitet werden, müssen serialisiert und dann deserialisiert werden, wenn Sie zwischen dem Client und der Ziel Sitzung übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-165">All objects passed to and from the remote session must be serialized and then deserialized as it passes between the client and the target session.</span></span> <span data-ttu-id="a87f2-166">Der Serialisierungsvorgang kann viele COMPUTE-und Speicherressourcen für große komplexe Datenobjekte verwenden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-166">The serialization operation can use many compute and memory resources for large complex data objects.</span></span>

## <a name="powershell-thread-based-jobs"></a><span data-ttu-id="a87f2-167">PowerShell-Thread basierte Aufträge</span><span class="sxs-lookup"><span data-stu-id="a87f2-167">PowerShell thread based jobs</span></span>

<span data-ttu-id="a87f2-168">Thread basierte Aufträge sind nicht so robust wie Remote-und Hintergrund Aufträge, da Sie in demselben Prozess in verschiedenen Threads ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-168">Thread based jobs are not as robust as Remote and Background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="a87f2-169">Wenn bei einem Auftrag ein schwerwiegender Fehler auftritt, der den Prozess abstürzt, können auch alle anderen Aufträge im Prozess fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="a87f2-169">If one job has a critical error that crashes the process, then all other jobs in the process will also fail.</span></span>

<span data-ttu-id="a87f2-170">Thread basierte Aufträge haben jedoch viel weniger Aufwand.</span><span class="sxs-lookup"><span data-stu-id="a87f2-170">However, thread-based jobs have much less overhead.</span></span> <span data-ttu-id="a87f2-171">Sie müssen die remotingschicht oder die Serialisierung nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-171">They don't need to use the remoting layer or serialization.</span></span> <span data-ttu-id="a87f2-172">Das Ergebnis ist, dass Thread basierte Aufträge tendenziell viel schneller ausgeführt werden und weit weniger Ressourcen als die anderen Auftrags Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-172">The result is that thread-based jobs tend to run much faster and use far less resources than the other job types.</span></span>

## <a name="thread-job-performance"></a><span data-ttu-id="a87f2-173">Thread Auftrags Leistung</span><span class="sxs-lookup"><span data-stu-id="a87f2-173">Thread job performance</span></span>

<span data-ttu-id="a87f2-174">Thread Aufträge sind schneller und leichter gewichtet als andere Arten von Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="a87f2-174">Thread jobs are faster and lighter weight than other types of jobs.</span></span> <span data-ttu-id="a87f2-175">Allerdings haben Sie immer noch mehr Aufwand, die im Vergleich zu den Aufgaben, die der Auftrag leistet, groß sein können.</span><span class="sxs-lookup"><span data-stu-id="a87f2-175">But they still have overhead that can be large when compared to work the job is doing.</span></span>

<span data-ttu-id="a87f2-176">PowerShell führt Befehle und Skripts in einer Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="a87f2-176">PowerShell runs commands and script in a session.</span></span> <span data-ttu-id="a87f2-177">In einer Sitzung kann jeweils nur ein Befehl oder ein Skript ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-177">Only one command or script can run at a time in a session.</span></span> <span data-ttu-id="a87f2-178">Wenn also mehrere Aufträge ausgeführt werden, wird jeder Auftrag in einer separaten Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a87f2-178">So when running multiple jobs, each job runs in a separate session.</span></span> <span data-ttu-id="a87f2-179">Jede Sitzung trägt zum Aufwand bei.</span><span class="sxs-lookup"><span data-stu-id="a87f2-179">Each session contributes to the overhead.</span></span>

<span data-ttu-id="a87f2-180">Thread Aufträge bieten die beste Leistung, wenn die von Ihnen ausgeführten Aufgaben größer sind als der Aufwand der Sitzung, die zum Ausführen des Auftrags verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a87f2-180">Thread jobs provide the best performance when the work they perform is greater than the overhead of the session used to run the job.</span></span> <span data-ttu-id="a87f2-181">Es gibt zwei Fälle für, die diese Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a87f2-181">There are two cases for that meet this criteria.</span></span>

- <span data-ttu-id="a87f2-182">Arbeit ist Rechen intensiv: das Ausführen eines Skripts für mehrere Thread Aufträge kann mehrere Prozessorkerne nutzen und schneller ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-182">Work is compute intensive - Running a script on multiple thread jobs can take advantage of multiple processor cores and complete faster.</span></span>

- <span data-ttu-id="a87f2-183">Die Arbeit besteht aus einem erheblichen Wartezustand. ein Skript, das Zeit für das warten auf e/a-oder Remote Aufruf Ergebnisse verbringt.</span><span class="sxs-lookup"><span data-stu-id="a87f2-183">Work consists of significant waiting - A script that spends time waiting for I/O or remote call results.</span></span> <span data-ttu-id="a87f2-184">Die parallele Ausführung wird normalerweise schneller abgeschlossen als bei der sequenziellen Ausführung.</span><span class="sxs-lookup"><span data-stu-id="a87f2-184">Running in parallel usually completes quicker than if run sequentially.</span></span>

```powershell
(Measure-Command {
    1..1000 | ForEach { Start-ThreadJob { Write-Output "Hello $using:_" } } | Receive-Job -Wait
}).TotalMilliseconds
10457.962


(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
24.9277
```

<span data-ttu-id="a87f2-185">Das erste Beispiel oben zeigt eine foreach-Schleife, die 1000 Thread Aufträge erstellt, um eine einfache Zeichenfolge zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="a87f2-185">The first example above shows a foreach loop that creates 1000 thread jobs to do a simple string write.</span></span> <span data-ttu-id="a87f2-186">Aufgrund des Auftrags Aufwands dauert der Abschluss von mehr als 33 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-186">Due to job overhead, it takes over 33 seconds to complete.</span></span>

<span data-ttu-id="a87f2-187">Im zweiten Beispiel wird das `ForEach` -Cmdlet ausgeführt, um die gleichen 1000-Vorgänge auszuführen, und jeder Zeichen folgen Schreibvorgang wird ohne jeglichen Auftrags Aufwand sequenziell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a87f2-187">The second example runs the `ForEach` cmdlet to do the same 1000 operations and each string write is executed sequentially without any job overhead.</span></span> <span data-ttu-id="a87f2-188">Sie wird in nur 25 Millisekunden abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a87f2-188">It completes in a mere 25 milliseconds.</span></span>

```powershell
$logNames.count
10

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

<span data-ttu-id="a87f2-189">Im obigen Beispiel werden bis zu 5000 Einträge für 10 separate Systemprotokolle gesammelt.</span><span class="sxs-lookup"><span data-stu-id="a87f2-189">In the above example, up to 5000 entries are collected for 10 separate system logs.</span></span> <span data-ttu-id="a87f2-190">Da das Skript eine Reihe von Protokollen liest, ist es sinnvoll, die Vorgänge parallel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a87f2-190">Since the script involves reading a number of logs, it makes sense to do the operations in parallel.</span></span> <span data-ttu-id="a87f2-191">Und der Auftrag wird über zwei Mal so schnell abgeschlossen, als wenn das Skript sequenziell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a87f2-191">And the job completes over twice as fast as when the script is run sequentially.</span></span>

```powershell
Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

## <a name="thread-jobs-and-variables"></a><span data-ttu-id="a87f2-192">Thread Aufträge und-Variablen</span><span class="sxs-lookup"><span data-stu-id="a87f2-192">Thread jobs and variables</span></span>

<span data-ttu-id="a87f2-193">Variablen werden auf verschiedene Weise an Thread Aufträge übermittelt.</span><span class="sxs-lookup"><span data-stu-id="a87f2-193">Variables are passed into thread jobs in various ways.</span></span>

<span data-ttu-id="a87f2-194">`Start-ThreadJob` kann Variablen akzeptieren, die an das Cmdlet weitergeleitet werden, über das Schlüsselwort an den Skriptblock übergeben `$using` oder über den Argument **List** -Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-194">`Start-ThreadJob` can accept variables that are piped to the cmdlet, passed in to the script block via the `$using` keyword, or passed in via the **ArgumentList** parameter.</span></span>

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job

`ForEach-Object -Parallel` accepts piped in variables, and variables passed
directly to the script block via the `$using` keyword.

```powershell
$msg = "Hello"

$msg | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job

1..1 | ForEach-Object -Parallel { Write-Output $using:msg } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="a87f2-195">Da Thread Aufträge in demselben Prozess ausgeführt werden, müssen alle an den Auftrag über gegebenen Variablen Verweis Typen sorgfältig behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-195">Since thread jobs run in the same process, any variable reference type passed into the job has to be treated carefully.</span></span> <span data-ttu-id="a87f2-196">Wenn es sich nicht um ein Thread sicheres Objekt handelt, sollte es niemals zugewiesen werden, und die-Methode und die-Eigenschaften sollten niemals darauf aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-196">If it is not a thread safe object, then it should never be assigned to, and method and properties should never be invoked on it.</span></span>

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

<span data-ttu-id="a87f2-197">Im obigen Beispiel wird ein Thread sicheres dotnet- `ConcurrentDictionary` Objekt an alle untergeordneten Aufträge weitergeleitet, um eindeutig benannte Prozess Objekte zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="a87f2-197">The above example passes a thread safe dotNet `ConcurrentDictionary` object to all child jobs to collect uniquely named process objects.</span></span> <span data-ttu-id="a87f2-198">Da es sich um ein Thread sicheres Objekt handelt, kann es sicher verwendet werden, während die Aufträge gleichzeitig im Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a87f2-198">Since it is a thread safe object, it can be safely used while the jobs run concurrently in the process.</span></span>

## <a name="see-also"></a><span data-ttu-id="a87f2-199">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a87f2-199">See also</span></span>

- [<span data-ttu-id="a87f2-200">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="a87f2-200">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="a87f2-201">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="a87f2-201">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="a87f2-202">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="a87f2-202">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="a87f2-203">about_Remote</span><span class="sxs-lookup"><span data-stu-id="a87f2-203">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="a87f2-204">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="a87f2-204">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="a87f2-205">Start-Job</span><span class="sxs-lookup"><span data-stu-id="a87f2-205">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="a87f2-206">Get-Job</span><span class="sxs-lookup"><span data-stu-id="a87f2-206">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="a87f2-207">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="a87f2-207">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="a87f2-208">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="a87f2-208">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="a87f2-209">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="a87f2-209">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="a87f2-210">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="a87f2-210">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
