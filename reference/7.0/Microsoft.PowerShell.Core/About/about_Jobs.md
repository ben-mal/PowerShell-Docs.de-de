---
description: Enthält Informationen dazu, wie PowerShell-Hintergrund Aufträge einen Befehl oder Ausdruck im Hintergrund ausführen, ohne mit der aktuellen Sitzung zu interagieren.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: 838e142fe39260b759e9a44c6d69b80d3c5b293e
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "93224631"
---
# <a name="about-jobs"></a><span data-ttu-id="5edcc-104">Informationen zu Aufträgen</span><span class="sxs-lookup"><span data-stu-id="5edcc-104">About Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="5edcc-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5edcc-105">Short description</span></span>
<span data-ttu-id="5edcc-106">Enthält Informationen dazu, wie PowerShell-Hintergrund Aufträge einen Befehl oder Ausdruck im Hintergrund ausführen, ohne mit der aktuellen Sitzung zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="5edcc-106">Provides information about how PowerShell background jobs run a command or expression in the background without interacting with the current session.</span></span>

## <a name="long-description"></a><span data-ttu-id="5edcc-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5edcc-107">Long description</span></span>

<span data-ttu-id="5edcc-108">PowerShell führt gleichzeitig Befehle und Skripts durch Aufträge aus.</span><span class="sxs-lookup"><span data-stu-id="5edcc-108">PowerShell concurrently runs commands and script through jobs.</span></span> <span data-ttu-id="5edcc-109">Es gibt drei auf Aufträgen basierende Lösungen, die von PowerShell zur Unterstützung von Parallelität bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5edcc-109">There are three jobs-based solutions provided by PowerShell to support concurrency.</span></span>

|<span data-ttu-id="5edcc-110">Auftrag</span><span class="sxs-lookup"><span data-stu-id="5edcc-110">Job</span></span>            |<span data-ttu-id="5edcc-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5edcc-111">Description</span></span>                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |<span data-ttu-id="5edcc-112">Befehl und Skript werden auf einem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5edcc-112">Command and script run on a remote computer.</span></span>                 |
|`BackgroundJob`|<span data-ttu-id="5edcc-113">Befehl und Skript werden in einem separaten Prozess auf dem lokalen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5edcc-113">Command and script run in a separate process on the local</span></span>    |
|               |<span data-ttu-id="5edcc-114">2 virtuelle CPUs zu.</span><span class="sxs-lookup"><span data-stu-id="5edcc-114">machine.</span></span>                                                     |
|`ThreadJob`    |<span data-ttu-id="5edcc-115">Befehl und Skript werden in einem separaten Thread innerhalb desselben</span><span class="sxs-lookup"><span data-stu-id="5edcc-115">Command and script run in a separate thread within the same</span></span>  |
|               |<span data-ttu-id="5edcc-116">Prozess auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="5edcc-116">process on the local machine.</span></span>                                |

<span data-ttu-id="5edcc-117">Jeder Auftragstyp hat Vorteile und Nachteile.</span><span class="sxs-lookup"><span data-stu-id="5edcc-117">Each type of job has benefits and drawbacks.</span></span> <span data-ttu-id="5edcc-118">Die Remote Ausführung von Skripts auf einem separaten Computer oder in einem separaten Prozess hat eine große Isolation.</span><span class="sxs-lookup"><span data-stu-id="5edcc-118">Running script remotely on a separate machine or in a separate process has great isolation.</span></span> <span data-ttu-id="5edcc-119">Alle Fehler wirken sich nicht auf andere laufende Aufträge oder den Client aus, von dem der Auftrag gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="5edcc-119">Any errors won't affect other running jobs or the client that started the job.</span></span> <span data-ttu-id="5edcc-120">Die Remoting-Schicht erhöht jedoch den mehr Aufwand, einschließlich Objektserialisierung.</span><span class="sxs-lookup"><span data-stu-id="5edcc-120">But the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="5edcc-121">Alle Objekte, die an und von der Remote Sitzung weitergeleitet werden, müssen serialisiert und dann deserialisiert werden, wenn Sie zwischen dem Client und der Ziel Sitzung übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="5edcc-121">All objects passed to and from the remote session must be serialized and then deserialized as it passes between the client and the target session.</span></span> <span data-ttu-id="5edcc-122">Der Serialisierungsvorgang kann viele COMPUTE-und Speicherressourcen für große komplexe Datenobjekte verwenden.</span><span class="sxs-lookup"><span data-stu-id="5edcc-122">The serialization operation can use many compute and memory resources for large complex data objects.</span></span>

<span data-ttu-id="5edcc-123">In diesem Thema wird erläutert, wie Hintergrund Aufträge in PowerShell auf einem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5edcc-123">This topic explains how to run background jobs in PowerShell on a local computer.</span></span> <span data-ttu-id="5edcc-124">Informationen zum Ausführen von Hintergrund Aufträgen auf Remote Computern finden Sie unter [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="5edcc-124">For information about running background jobs on remote computers, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span> <span data-ttu-id="5edcc-125">Weitere Informationen zu Thread Aufträgen finden Sie unter [about_Thread_Jobs](about_Thread_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="5edcc-125">For more information about thread jobs, see [about_Thread_Jobs](about_Thread_Jobs.md).</span></span>

<span data-ttu-id="5edcc-126">Wenn Sie einen Hintergrund Auftrag starten, wird die Eingabeaufforderung sofort zurückgegeben, auch wenn die Ausführung des Auftrags längere Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="5edcc-126">When you start a background job, the command prompt returns immediately, even if the job takes an extended time to complete.</span></span> <span data-ttu-id="5edcc-127">Sie können ohne Unterbrechung in der Sitzung weiterarbeiten, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="5edcc-127">You can continue to work in the session without interruption while the job runs.</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="5edcc-128">Die Job-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5edcc-128">The job cmdlets</span></span>

|<span data-ttu-id="5edcc-129">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="5edcc-129">Cmdlet</span></span>          |<span data-ttu-id="5edcc-130">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5edcc-130">Description</span></span>                                            |
|----------------|-------------------------------------------------------|
|`Start-Job`     |<span data-ttu-id="5edcc-131">Startet einen Hintergrundauftrag auf einem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="5edcc-131">Starts a background job on a local computer.</span></span>           |
|`Get-Job`       |<span data-ttu-id="5edcc-132">Ruft die Hintergrund Aufträge ab, die im</span><span class="sxs-lookup"><span data-stu-id="5edcc-132">Gets the background jobs that were started in the</span></span>      |
|                |<span data-ttu-id="5edcc-133">aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="5edcc-133">current session.</span></span>                                       |
|`Receive-Job`   |<span data-ttu-id="5edcc-134">Ruft die Ergebnisse der Hintergrund Aufträge ab.</span><span class="sxs-lookup"><span data-stu-id="5edcc-134">Gets the results of background jobs.</span></span>                   |
|`Stop-Job`      |<span data-ttu-id="5edcc-135">Beendet einen Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="5edcc-135">Stops a background job.</span></span>                                |
|`Wait-Job`      |<span data-ttu-id="5edcc-136">Unterdrückt die Eingabeaufforderung, bis ein oder alle Aufträge</span><span class="sxs-lookup"><span data-stu-id="5edcc-136">Suppresses the command prompt until one or all jobs are</span></span>|
|                |<span data-ttu-id="5edcc-137">ganz.</span><span class="sxs-lookup"><span data-stu-id="5edcc-137">complete.</span></span>                                              |
|`Remove-Job`    |<span data-ttu-id="5edcc-138">Löscht einen Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="5edcc-138">Deletes a background job.</span></span>                              |
|`Invoke-Command`|<span data-ttu-id="5edcc-139">Der **AsJob** -Parameter erstellt einen Hintergrund Auftrag auf einem</span><span class="sxs-lookup"><span data-stu-id="5edcc-139">The **AsJob** parameter creates a background job on a</span></span>  |
|                |<span data-ttu-id="5edcc-140">Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="5edcc-140">remote computer.</span></span> <span data-ttu-id="5edcc-141">Sie können `Invoke-Command` zum Ausführen von verwenden.</span><span class="sxs-lookup"><span data-stu-id="5edcc-141">You can use `Invoke-Command` to run</span></span>   |
|                |<span data-ttu-id="5edcc-142">Alle Auftrags Befehle Remote, einschließlich `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="5edcc-142">any job command remotely, including `Start-Job`.</span></span>       |

## <a name="how-to-start-a-job-on-the-local-computer"></a><span data-ttu-id="5edcc-143">Starten eines Auftrags auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="5edcc-143">How to start a job on the local computer</span></span>

<span data-ttu-id="5edcc-144">Verwenden Sie das-Cmdlet, um einen Hintergrund Auftrag auf dem lokalen Computer zu starten `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="5edcc-144">To start a background job on the local computer, use the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="5edcc-145">Um einen Befehl zu schreiben `Start-Job` , schließen Sie den Befehl ein, dass der Auftrag in geschweiften Klammern () ausgeführt wird `{}` .</span><span class="sxs-lookup"><span data-stu-id="5edcc-145">To write a `Start-Job` command, enclose the command that the job runs in curly braces (`{}`).</span></span> <span data-ttu-id="5edcc-146">Verwenden Sie den **ScriptBlock** -Parameter, um den Befehl anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5edcc-146">Use the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="5edcc-147">Der folgende Befehl startet einen Hintergrund Auftrag, der einen `Get-Process` Befehl auf dem lokalen Computer ausführt.</span><span class="sxs-lookup"><span data-stu-id="5edcc-147">The following command starts a background job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="5edcc-148">Der `Start-Job` Befehl gibt ein Objekt zurück, das den Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="5edcc-148">The `Start-Job` command returns an object that represents the job.</span></span> <span data-ttu-id="5edcc-149">Das Auftragsobjekt enthält nützliche Informationen zum Auftrag, aber keine Auftragsergebnisse.</span><span class="sxs-lookup"><span data-stu-id="5edcc-149">The job object contains useful information about the job, but it does not contain the job results.</span></span>

<span data-ttu-id="5edcc-150">Speichern Sie das Auftrags Objekt in einer Variablen, und verwenden Sie es dann mit den anderen Auftrags-Cmdlets, um den Hintergrund Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="5edcc-150">Save the job object in a variable, and then use it with the other Job cmdlets to manage the background job.</span></span> <span data-ttu-id="5edcc-151">Der folgende Befehl startet ein Auftrags Objekt und speichert das resultierende Auftrags Objekt in der `$job` Variablen.</span><span class="sxs-lookup"><span data-stu-id="5edcc-151">The following command starts a job object and saves the resulting job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="5edcc-152">Ab PowerShell 6,0 können Sie einen "amersand ()" `&` am Ende einer Pipeline verwenden, um einen Hintergrund Auftrag zu starten.</span><span class="sxs-lookup"><span data-stu-id="5edcc-152">Beginning in PowerShell 6.0, you can use an amersand (`&`) at the end of a pipeline to start a background job.</span></span> <span data-ttu-id="5edcc-153">Der folgende Befehl ist funktional äquivalent zum obigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="5edcc-153">The following command is functionally equivalent to the command above.</span></span>

```powershell
$job = Get-Process &
```

<span data-ttu-id="5edcc-154">Das kaufmännische und-( `&` ) wird als Background-Operator bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5edcc-154">The ampersand (`&`) is called the background operator.</span></span> <span data-ttu-id="5edcc-155">Weitere Informationen finden Sie unter [Background-Operator](about_Operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="5edcc-155">For more information, see [background operator](about_Operators.md#background-operator-).</span></span>

<span data-ttu-id="5edcc-156">Sie können auch das- `Get-Job` Cmdlet verwenden, um Objekte zu erhalten, die die in der aktuellen Sitzung gestarteten Aufträge darstellen.</span><span class="sxs-lookup"><span data-stu-id="5edcc-156">You can also use the `Get-Job` cmdlet to get objects that represent the jobs started in the current session.</span></span> <span data-ttu-id="5edcc-157">`Get-Job` Gibt das gleiche Auftrags Objekt zurück, das `Start-Job` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5edcc-157">`Get-Job` returns the same job object that `Start-Job` returns.</span></span>

## <a name="getting-job-objects"></a><span data-ttu-id="5edcc-158">Auftrags Objekte werden erhalten.</span><span class="sxs-lookup"><span data-stu-id="5edcc-158">Getting job objects</span></span>

<span data-ttu-id="5edcc-159">Verwenden Sie das-Cmdlet, um ein Objekt zu erhalten, das die Hintergrund Aufträge darstellt, die in der aktuellen Sitzung gestartet wurden `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="5edcc-159">To get object that represent the background jobs that were started in the current session, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="5edcc-160">Ohne Parameter `Get-Job` gibt alle Aufträge zurück, die in der aktuellen Sitzung gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="5edcc-160">Without parameters, `Get-Job` returns all of the jobs that were started in the current session.</span></span>

<span data-ttu-id="5edcc-161">Beispielsweise ruft der folgende Befehl die Aufträge in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="5edcc-161">For example, the following command gets the jobs in the current session.</span></span>

```powershell
PS C:> Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Running    True         localhost  Get-Process
```

<span data-ttu-id="5edcc-162">Sie können auch das Auftrags Objekt in einer Variablen speichern und es verwenden, um den Auftrag in einem späteren Befehl darzustellen.</span><span class="sxs-lookup"><span data-stu-id="5edcc-162">You can also save the job object in a variable and use it to represent the job in a later command.</span></span> <span data-ttu-id="5edcc-163">Mit dem folgenden Befehl wird der Auftrag mit der ID 1 abgerufen und in der `$job` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5edcc-163">The following command gets the job with ID 1 and saves it in the `$job` variable.</span></span>

```powershell
$job = Get-Job -Id 1
```

<span data-ttu-id="5edcc-164">Das Auftrags Objekt enthält den Status des Auftrags, der angibt, ob der Auftrag abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="5edcc-164">The job object contains the state of the job, which indicates whether the job has finished.</span></span> <span data-ttu-id="5edcc-165">Ein fertiggestelltes Auftrag hat den Status " **abgeschlossen** " oder " **failed** ".</span><span class="sxs-lookup"><span data-stu-id="5edcc-165">A finished job has a state of **Complete** or **Failed**.</span></span> <span data-ttu-id="5edcc-166">Ein Auftrag kann auch **blockiert** werden oder **ausgeführt** werden.</span><span class="sxs-lookup"><span data-stu-id="5edcc-166">A job might also be **blocked** or **running**.</span></span>

```powershell
Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

## <a name="getting-the-results-of-a-job"></a><span data-ttu-id="5edcc-167">Erhalten der Ergebnisse eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="5edcc-167">Getting the results of a job</span></span>

<span data-ttu-id="5edcc-168">Wenn Sie einen Hintergrund Auftrag ausführen, werden die Ergebnisse nicht sofort angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5edcc-168">When you run a background job, the results do not appear immediately.</span></span> <span data-ttu-id="5edcc-169">Stattdessen gibt das `Start-Job` Cmdlet ein Auftrags Objekt zurück, das den Auftrag darstellt, aber die Ergebnisse nicht enthält.</span><span class="sxs-lookup"><span data-stu-id="5edcc-169">Instead, the `Start-Job` cmdlet returns a job object that represents the job, but it does not contain the results.</span></span> <span data-ttu-id="5edcc-170">Verwenden Sie das-Cmdlet, um die Ergebnisse eines Hintergrund Auftrags zu erhalten `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="5edcc-170">To get the results of a background job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="5edcc-171">Der folgende Befehl verwendet das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5edcc-171">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="5edcc-172">Es verwendet ein in der Variablen gespeichertes Auftrags Objekt `$job` , um den Auftrag zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5edcc-172">It uses a job object saved in the `$job` variable to identify the job.</span></span>

```powershell
Receive-Job -Job $job
```

<span data-ttu-id="5edcc-173">Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse des Auftrags zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5edcc-173">The `Receive-Job` cmdlet returns the results of the job.</span></span>

```
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
    103       4    11328       9692    56           1176 audiodg
    804      14    12228      14108   100   101.74  1740 CcmExec
    668       7     2672       6168   104    32.26   488 csrss
# ...
```

<span data-ttu-id="5edcc-174">Sie können auch die Ergebnisse eines Auftrags in einer Variablen speichern.</span><span class="sxs-lookup"><span data-stu-id="5edcc-174">You can also save the results of a job in a variable.</span></span> <span data-ttu-id="5edcc-175">Der folgende Befehl speichert die Ergebnisse des Auftrags in der `$job` Variablen in der `$results` Variablen.</span><span class="sxs-lookup"><span data-stu-id="5edcc-175">The following command saves the results of the job in the `$job` variable to the `$results` variable.</span></span>

```powershell
$results = Receive-Job -Job $job
```

<span data-ttu-id="5edcc-176">Außerdem können Sie die Ergebnisse des Auftrags in einer Datei speichern, indem Sie den Umleitungs Operator ( `>` ) oder das `Out-File` Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="5edcc-176">And, you can save the results of the job in a file by using the redirection operator (`>`) or the `Out-File` cmdlet.</span></span> <span data-ttu-id="5edcc-177">Der folgende Befehl verwendet den Redirect-Operator, um die Ergebnisse des Auftrags in der- `$job` Variable in der-Datei zu speichern `Results.txt` .</span><span class="sxs-lookup"><span data-stu-id="5edcc-177">The following command uses the redirection operator to save the results of the job in the `$job` variable in the `Results.txt` file.</span></span>

```powershell
Receive-Job -Job $job > results.txt
```

## <a name="getting-and-keeping-partial-job-results"></a><span data-ttu-id="5edcc-178">Erhalten und Aufbewahren von partiellen Auftrags Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="5edcc-178">Getting and keeping partial job results</span></span>

<span data-ttu-id="5edcc-179">Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse eines Hintergrund Auftrags abgerufen.</span><span class="sxs-lookup"><span data-stu-id="5edcc-179">The `Receive-Job` cmdlet gets the results of a background job.</span></span> <span data-ttu-id="5edcc-180">Wenn der Auftrag vollständig ist, werden `Receive-Job` alle Auftrags Ergebnisse abgerufen.</span><span class="sxs-lookup"><span data-stu-id="5edcc-180">If the job is complete, `Receive-Job` gets all job results.</span></span> <span data-ttu-id="5edcc-181">Wenn der Auftrag noch ausgeführt wird, ruft `Receive-Job` die bisher generierten Ergebnisse ab.</span><span class="sxs-lookup"><span data-stu-id="5edcc-181">If the job is still running, `Receive-Job` gets the results that have been generated thus far.</span></span> <span data-ttu-id="5edcc-182">Sie können `Receive-Job` Befehle erneut ausführen, um die verbleibenden Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5edcc-182">You can run `Receive-Job` commands again to get the remaining results.</span></span>

<span data-ttu-id="5edcc-183">Wenn `Receive-Job` Ergebnisse zurückgibt, werden diese Ergebnisse standardmäßig aus dem Cache gelöscht, in dem Auftrags Ergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="5edcc-183">When `Receive-Job` returns results, by default, it deletes those results from the cache where job results are stored.</span></span> <span data-ttu-id="5edcc-184">Wenn Sie einen anderen `Receive-Job` Befehl ausführen, werden nur die Ergebnisse angezeigt, die noch nicht empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="5edcc-184">If you run another `Receive-Job` command, you get only the results that are not yet received.</span></span>

<span data-ttu-id="5edcc-185">Die folgenden Befehle zeigen die Ergebnisse von `Receive-Job` Befehlen, die vor Abschluss des Auftrags ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5edcc-185">The following commands show the results of `Receive-Job` commands run before the job is complete.</span></span>

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

<span data-ttu-id="5edcc-186">`Receive-Job`Verwenden Sie den **Keep** -Parameter, um zu verhindern, dass die zurückgegebenen Auftrags Ergebnisse gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="5edcc-186">To prevent `Receive-Job` from deleting the job results that it has returned, use the **Keep** parameter.</span></span> <span data-ttu-id="5edcc-187">Folglich `Receive-Job` gibt alle Ergebnisse zurück, die bis zu diesem Zeitpunkt generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5edcc-187">As a result, `Receive-Job` returns all of the results that have been generated until that time.</span></span>

<span data-ttu-id="5edcc-188">Die folgenden Befehle zeigen die Auswirkung der Verwendung des **Keep** -Parameters auf einen Auftrag, der noch nicht beendet ist.</span><span class="sxs-lookup"><span data-stu-id="5edcc-188">The following commands show the effect of using the **Keep** parameter on a job that is not yet complete.</span></span>

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

## <a name="waiting-for-the-results"></a><span data-ttu-id="5edcc-189">Warten auf die Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="5edcc-189">Waiting for the results</span></span>

<span data-ttu-id="5edcc-190">Wenn Sie einen Befehl ausführen, der eine lange Zeit in Anspruch nimmt, können Sie die Eigenschaften des Auftrags Objekts verwenden, um zu bestimmen, wann der Auftrag beendet ist.</span><span class="sxs-lookup"><span data-stu-id="5edcc-190">If you run a command that takes a long time to complete, you can use the properties of the job object to determine when the job is complete.</span></span> <span data-ttu-id="5edcc-191">Der folgende Befehl verwendet das- `Get-Job` Objekt, um alle Hintergrund Aufträge in der aktuellen Sitzung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5edcc-191">The following command uses the `Get-Job` object to get all of the background jobs in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="5edcc-192">Die Ergebnisse werden in einer Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5edcc-192">The results appear in a table.</span></span> <span data-ttu-id="5edcc-193">Der Status des Auftrags wird in der Spalte **Bundesstaat** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5edcc-193">The status of the job appears in the **State** column.</span></span>

```
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

<span data-ttu-id="5edcc-194">In diesem Fall zeigt die State-Eigenschaft an, dass Auftrag 2 noch ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5edcc-194">In this case, the State property reveals that Job 2 is still running.</span></span> <span data-ttu-id="5edcc-195">Wenn Sie das `Receive-Job` Cmdlet verwenden, um die Auftrags Ergebnisse jetzt zu erhalten, sind die Ergebnisse unvollständig.</span><span class="sxs-lookup"><span data-stu-id="5edcc-195">If you were to use the `Receive-Job` cmdlet to get the job results now, the results would be incomplete.</span></span> <span data-ttu-id="5edcc-196">Sie können das `Receive-Job` Cmdlet wiederholt verwenden, um alle Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5edcc-196">You can use the `Receive-Job` cmdlet repeatedly to get all of the results.</span></span> <span data-ttu-id="5edcc-197">Standardmäßig erhalten Sie jedes Mal, wenn Sie Sie verwenden, nur die Ergebnisse, die nicht bereits empfangen wurden, aber Sie können den **Keep** -Parameter des `Receive-Job` Cmdlets verwenden, um die Ergebnisse beizubehalten, auch wenn Sie bereits empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="5edcc-197">By default, each time you use it, you get only the results that were not already received, but you can use the **Keep** parameter of the `Receive-Job` cmdlet to retain the results, even though they were already received.</span></span>

<span data-ttu-id="5edcc-198">Sie können die partiellen Ergebnisse in eine Datei schreiben und dann neue Ergebnisse beim Eintreffen anfügen, oder Sie können warten und den Status des Auftrags später überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5edcc-198">You can write the partial results to a file and then append newer results as they arrive or you can wait and check the state of the job later.</span></span>

<span data-ttu-id="5edcc-199">Sie können den **Wait** -Parameter des `Receive-Job` Cmdlets verwenden, das die Eingabeaufforderung nicht zurückgibt, bis der Auftrag vollständig ist und alle Ergebnisse verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5edcc-199">You can use the **Wait** parameter of the `Receive-Job` cmdlet, which does not return the command prompt until the job is complete and all results are available.</span></span>

<span data-ttu-id="5edcc-200">Sie können auch das- `Wait-Job` Cmdlet verwenden, um auf ein oder alle Ergebnisse des Auftrags zu warten.</span><span class="sxs-lookup"><span data-stu-id="5edcc-200">You can also use the `Wait-Job` cmdlet to wait for any or all of the results of the job.</span></span> <span data-ttu-id="5edcc-201">`Wait-Job` Hiermit können Sie auf einen bestimmten Auftrag, auf alle Aufträge oder auf den Abschluss eines der Aufträge warten.</span><span class="sxs-lookup"><span data-stu-id="5edcc-201">`Wait-Job` lets you wait for a particular job, for all jobs, or for any of the jobs to be completed.</span></span>

<span data-ttu-id="5edcc-202">Der folgende Befehl verwendet das `Wait-Job` Cmdlet, um auf einen Auftrag mit der **ID** zu warten.</span><span class="sxs-lookup"><span data-stu-id="5edcc-202">The following command uses the `Wait-Job` cmdlet to wait for a job with **ID**</span></span>
10.

```powershell
Wait-Job -ID 10
```

<span data-ttu-id="5edcc-203">Folglich wird die PowerShell-Eingabeaufforderung unterdrückt, bis der Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5edcc-203">As a result, the PowerShell prompt is suppressed until the job is completed.</span></span>

<span data-ttu-id="5edcc-204">Sie können auch einen vordefinierten Zeitraum warten.</span><span class="sxs-lookup"><span data-stu-id="5edcc-204">You can also wait for a predetermined period of time.</span></span> <span data-ttu-id="5edcc-205">Dieser Befehl verwendet den **Timeout** -Parameter, um die Wartezeit auf 120 Sekunden einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="5edcc-205">This command uses the **Timeout** parameter to limit the wait to 120 seconds.</span></span> <span data-ttu-id="5edcc-206">Wenn die Zeit abläuft, wird die Eingabeaufforderung zurückgegeben, aber der Auftrag wird weiterhin im Hintergrund ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5edcc-206">When the time expires, the command prompt returns, but the job continues to run in the background.</span></span>

```powershell
Wait-Job -ID 10 -Timeout 120
```

## <a name="stopping-a-job"></a><span data-ttu-id="5edcc-207">Beenden eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="5edcc-207">Stopping a job</span></span>

<span data-ttu-id="5edcc-208">Verwenden Sie das-Cmdlet, um einen Hintergrund Auftrag zu unterbinden `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="5edcc-208">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="5edcc-209">Der folgende Befehl startet einen Auftrag, um jeden Eintrag im System Ereignisprotokoll zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5edcc-209">The following command starts a job to get every entry in the System event log.</span></span> <span data-ttu-id="5edcc-210">Das Auftrags Objekt wird in der `$job` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5edcc-210">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-EventLog -Log System}
```

<span data-ttu-id="5edcc-211">Mit dem folgenden Befehl wird der Auftrag beendet.</span><span class="sxs-lookup"><span data-stu-id="5edcc-211">The following command stops the job.</span></span> <span data-ttu-id="5edcc-212">Er verwendet einen Pipeline Operator ( `|` ), um den Auftrag in der `$job` Variablen an zu senden `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="5edcc-212">It uses a pipeline operator (`|`) to send the job in the `$job` variable to `Stop-Job`.</span></span>

```powershell
$job | Stop-Job
```

## <a name="deleting-a-job"></a><span data-ttu-id="5edcc-213">Löschen eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="5edcc-213">Deleting a job</span></span>

<span data-ttu-id="5edcc-214">Verwenden Sie das-Cmdlet, um einen Hintergrund Auftrag zu löschen `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="5edcc-214">To delete a background job, use the `Remove-Job` cmdlet.</span></span> <span data-ttu-id="5edcc-215">Der folgende Befehl löscht den Auftrag in der `$job` Variablen.</span><span class="sxs-lookup"><span data-stu-id="5edcc-215">The following command deletes the job in the `$job` variable.</span></span>

```powershell
Remove-Job -Job $job
```

## <a name="investigating-a-failed-job"></a><span data-ttu-id="5edcc-216">Untersuchen eines fehlgeschlagenen Auftrags</span><span class="sxs-lookup"><span data-stu-id="5edcc-216">Investigating a failed job</span></span>

<span data-ttu-id="5edcc-217">Um herauszufinden, warum ein Auftrag fehlgeschlagen ist, verwenden Sie die **reason** -Eigenschaft des Auftrags Objekts.</span><span class="sxs-lookup"><span data-stu-id="5edcc-217">To find out why a job failed, use the **Reason** property of the job object.</span></span>

<span data-ttu-id="5edcc-218">Der folgende Befehl startet einen Auftrag ohne die erforderlichen Anmelde Informationen.</span><span class="sxs-lookup"><span data-stu-id="5edcc-218">The following command starts a job without the required credentials.</span></span> <span data-ttu-id="5edcc-219">Das Auftrags Objekt wird in der `$job` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5edcc-219">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

<span data-ttu-id="5edcc-220">Der folgende Befehl verwendet die Reason-Eigenschaft, um den Fehler zu finden, durch den der Auftrag fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="5edcc-220">The following command uses the Reason property to find the error that caused the job to fail.</span></span>

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

<span data-ttu-id="5edcc-221">In diesem Fall ist der Auftrag nicht erfolgreich, weil der Remote Computer explizite Anmelde Informationen zum Ausführen des Befehls benötigt hat.</span><span class="sxs-lookup"><span data-stu-id="5edcc-221">In this case, the job failed because the remote computer required explicit credentials to run the command.</span></span> <span data-ttu-id="5edcc-222">Der Wert der **reason** -Eigenschaft ist:</span><span class="sxs-lookup"><span data-stu-id="5edcc-222">The value of the **Reason** property is:</span></span>

<span data-ttu-id="5edcc-223">Fehler beim Herstellen einer Verbindung mit dem Remote Server mit der folgenden Fehlermeldung: "der Zugriff wurde verweigert."</span><span class="sxs-lookup"><span data-stu-id="5edcc-223">Connecting to remote server failed with the following error message: "Access is denied".</span></span>

## <a name="see-also"></a><span data-ttu-id="5edcc-224">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="5edcc-224">See also</span></span>

- [<span data-ttu-id="5edcc-225">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="5edcc-225">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="5edcc-226">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="5edcc-226">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="5edcc-227">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="5edcc-227">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="5edcc-228">about_Remote</span><span class="sxs-lookup"><span data-stu-id="5edcc-228">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="5edcc-229">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="5edcc-229">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="5edcc-230">Start-Job</span><span class="sxs-lookup"><span data-stu-id="5edcc-230">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="5edcc-231">Get-Job</span><span class="sxs-lookup"><span data-stu-id="5edcc-231">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="5edcc-232">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="5edcc-232">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="5edcc-233">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="5edcc-233">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="5edcc-234">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="5edcc-234">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="5edcc-235">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="5edcc-235">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="5edcc-236">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="5edcc-236">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
