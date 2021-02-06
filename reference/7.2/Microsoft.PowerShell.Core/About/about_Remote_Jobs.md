---
description: Hier wird beschrieben, wie Aufträge auf Remote Computern ausgeführt werden.
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: 93e1d3aba1f4037cc3c5c18386488bf321fc2a64
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603692"
---
# <a name="about-remote-jobs"></a><span data-ttu-id="2d503-103">Informationen zu Remote Aufträgen</span><span class="sxs-lookup"><span data-stu-id="2d503-103">About Remote Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="2d503-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d503-104">Short Description</span></span>
<span data-ttu-id="2d503-105">Hier wird beschrieben, wie Hintergrund Aufträge auf Remote Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2d503-105">Describes how to run background jobs on remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="2d503-106">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d503-106">Detailed Description</span></span>

<span data-ttu-id="2d503-107">PowerShell führt Befehle und Skripts gleichzeitig durch Aufträge aus.</span><span class="sxs-lookup"><span data-stu-id="2d503-107">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="2d503-108">Es gibt drei Auftrags Typen, die von PowerShell zur Unterstützung von Parallelität bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2d503-108">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="2d503-109">`RemoteJob` -Befehle und Skripts werden in einer Remote Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d503-109">`RemoteJob` - Commands and scripts run in a remote session.</span></span>
- <span data-ttu-id="2d503-110">`BackgroundJob` -Befehle und Skripts werden in einem separaten Prozess auf dem lokalen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d503-110">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span> <span data-ttu-id="2d503-111">Weitere Informationen finden Sie unter [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="2d503-111">For more information, see [about_Jobs](about_Jobs.md).</span></span>
- <span data-ttu-id="2d503-112">`PSTaskJob``ThreadJob`-Befehle und-Skripts werden in einem separaten Thread innerhalb desselben Prozesses auf dem lokalen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d503-112">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span> <span data-ttu-id="2d503-113">Weitere Informationen finden Sie unter [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span><span class="sxs-lookup"><span data-stu-id="2d503-113">For more information, see [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span></span>

<span data-ttu-id="2d503-114">Das Remote Ausführen von Skripts auf einem separaten Computer oder in einem separaten Prozess bietet eine hohe Isolation.</span><span class="sxs-lookup"><span data-stu-id="2d503-114">Running scripts remotely, on a separate machine or in a separate process, provide great isolation.</span></span> <span data-ttu-id="2d503-115">Fehler, die im Remote Auftrag auftreten, wirken sich nicht auf andere laufende Aufträge oder die übergeordnete Sitzung aus, die den Auftrag gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="2d503-115">Any errors that occur in the remote job do not affect other running jobs or the parent session that started the job.</span></span> <span data-ttu-id="2d503-116">Allerdings erhöht die Remoting-Ebene mehr Aufwand, einschließlich Objektserialisierung.</span><span class="sxs-lookup"><span data-stu-id="2d503-116">However, the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="2d503-117">Alle Objekte werden serialisiert und deserialisiert, wenn Sie zwischen der übergeordneten Sitzung und der Remote Sitzung (Auftrags Sitzung) weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2d503-117">All objects are serialized and deserialized as they are passed between the parent session and the remote (job) session.</span></span> <span data-ttu-id="2d503-118">Die Serialisierung von großen komplexen Datenobjekten kann große Mengen an COMPUTE-und Speicherressourcen beanspruchen und große Datenmengen über das Netzwerk übertragen.</span><span class="sxs-lookup"><span data-stu-id="2d503-118">Serialization of large complex data objects can consume large amounts of compute and memory resources and transfer large amounts of data across the network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d503-119">In der übergeordneten Sitzung, mit der der Auftrag erstellt wurde, wird auch der Auftragsstatus überwacht und Pipeline Daten gesammelt.</span><span class="sxs-lookup"><span data-stu-id="2d503-119">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="2d503-120">Der untergeordnete Prozess des Auftrags wird vom übergeordneten Prozess beendet, sobald der Auftrag den Status "abgeschlossen" erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="2d503-120">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="2d503-121">Wenn die übergeordnete Sitzung beendet wird, werden alle untergeordneten Aufträge zusammen mit ihren untergeordneten Prozessen beendet.</span><span class="sxs-lookup"><span data-stu-id="2d503-121">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="2d503-122">Es gibt zwei Möglichkeiten, diese Situation zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="2d503-122">There are two ways work around this situation:</span></span>

1. <span data-ttu-id="2d503-123">Verwenden `Invoke-Command` Sie, um Aufträge zu erstellen, die in getrennten Sitzungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2d503-123">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="2d503-124">Weitere Informationen finden Sie im Abschnitt " [getrennte Prozesse](#how-to-run-as-a-detached-process) " in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="2d503-124">See the [detached processes](#how-to-run-as-a-detached-process) section of this article.</span></span>
1. <span data-ttu-id="2d503-125">Verwenden `Start-Process` Sie, um anstelle eines Auftrags einen neuen Prozess zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d503-125">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="2d503-126">Weitere Informationen finden Sie unter [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span><span class="sxs-lookup"><span data-stu-id="2d503-126">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="remote-jobs"></a><span data-ttu-id="2d503-127">Remote Aufträge</span><span class="sxs-lookup"><span data-stu-id="2d503-127">Remote Jobs</span></span>

<span data-ttu-id="2d503-128">Sie können Aufträge auf Remote Computern ausführen, indem Sie drei verschiedene Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d503-128">You can run jobs on remote computers by using three different methods.</span></span>

- <span data-ttu-id="2d503-129">Starten Sie eine interaktive Sitzung auf einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="2d503-129">Start an interactive session on a remote computer.</span></span> <span data-ttu-id="2d503-130">Starten Sie dann einen Auftrag in der interaktiven Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2d503-130">Then start a job in the interactive session.</span></span> <span data-ttu-id="2d503-131">Die Prozeduren sind mit dem Ausführen eines lokalen Auftrags identisch, obwohl alle Aktionen auf dem Remote Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2d503-131">The procedures are the same as running a local job, although all actions are performed on the remote computer.</span></span>

- <span data-ttu-id="2d503-132">Führen Sie einen Auftrag auf einem Remote Computer aus, von dem die Ergebnisse an den lokalen Computer zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2d503-132">Run a job on a remote computer that returns its results to the local computer.</span></span> <span data-ttu-id="2d503-133">Verwenden Sie diese Methode, wenn Sie die Ergebnisse von Aufträgen erfassen und an einem zentralen Speicherort auf dem lokalen Computer aufbewahren möchten.</span><span class="sxs-lookup"><span data-stu-id="2d503-133">Use this method when you want to collect the results of jobs and maintain them in a central location on the local computer.</span></span>

- <span data-ttu-id="2d503-134">Führen Sie einen Auftrag auf einem Remote Computer aus, der seine Ergebnisse auf dem Remote Computer beibehält.</span><span class="sxs-lookup"><span data-stu-id="2d503-134">Run a job on a remote computer that maintains its results on the remote computer.</span></span> <span data-ttu-id="2d503-135">Verwenden Sie diese Methode, wenn die Auftragsdaten auf dem Ursprungs Computer sicherer verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="2d503-135">Use this method when the job data is more securely maintained on the originating computer.</span></span>

### <a name="start-a-job-in-an-interactive-session"></a><span data-ttu-id="2d503-136">Starten eines Auftrags in einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="2d503-136">Start a job in an interactive session</span></span>

<span data-ttu-id="2d503-137">Sie können eine interaktive Sitzung mit einem Remote Computer starten und dann während der interaktiven Sitzung einen Auftrag starten.</span><span class="sxs-lookup"><span data-stu-id="2d503-137">You can start an interactive session with a remote computer and then start a job during the interactive session.</span></span> <span data-ttu-id="2d503-138">Weitere Informationen zu interaktiven Sitzungen finden Sie unter about_Remote und unter `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="2d503-138">For more information about interactive sessions, see about_Remote, and see `Enter-PSSession`.</span></span>

<span data-ttu-id="2d503-139">Das Verfahren zum Starten eines Auftrags in einer interaktiven Sitzung ist fast identisch mit dem Verfahren zum Starten eines Hintergrund Auftrags auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="2d503-139">The procedure for starting a job in an interactive session is almost identical to the procedure for starting a background job on the local computer.</span></span> <span data-ttu-id="2d503-140">Allerdings erfolgen alle Vorgänge auf dem Remote Computer, nicht auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="2d503-140">However, all of the operations occur on the remote computer, not the local computer.</span></span>

1. <span data-ttu-id="2d503-141">Verwenden `Enter-PSSession` Sie das Cmdlet, um eine interaktive Sitzung mit einem Remote Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="2d503-141">Use the `Enter-PSSession` cmdlet to start an interactive session with a remote computer.</span></span> <span data-ttu-id="2d503-142">Sie können den Computername-Parameter von verwenden `Enter-PSSession` , um eine temporäre Verbindung für die interaktive Sitzung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2d503-142">You can use the ComputerName parameter of `Enter-PSSession` to establish a temporary connection for the interactive session.</span></span> <span data-ttu-id="2d503-143">Oder Sie können den Session-Parameter verwenden, um die interaktive Sitzung in einer PowerShell-Sitzung (PSSession) auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d503-143">Or, you can use the Session parameter to run the interactive session in a PowerShell session (PSSession).</span></span>

   <span data-ttu-id="2d503-144">Der folgende Befehl startet eine interaktive Sitzung auf dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="2d503-144">The following command starts an interactive session on the Server01 computer.</span></span>

   ```powershell
   C:\PS> Enter-PSSession -computername Server01
   ```

   <span data-ttu-id="2d503-145">Die Eingabeaufforderung ändert sich, um anzuzeigen, dass Sie jetzt mit dem Computer Server01 verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="2d503-145">The command prompt changes to show that you are now connected to the Server01 computer.</span></span>

   ```
   Server01\C:>
   ```

1. <span data-ttu-id="2d503-146">Verwenden Sie das-Cmdlet, um einen Remote Auftrag in der Sitzung zu starten `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="2d503-146">To start a remote job in the session, use the `Start-Job` cmdlet.</span></span> <span data-ttu-id="2d503-147">Der folgende Befehl führt einen Remote Auftrag aus, der die Ereignisse im Windows PowerShell-Ereignisprotokoll auf dem Server01-Computer abruft.</span><span class="sxs-lookup"><span data-stu-id="2d503-147">The following command runs a remote job that gets the events in the Windows PowerShell event log on the Server01 computer.</span></span> <span data-ttu-id="2d503-148">Das- `Start-Job` Cmdlet gibt ein Objekt zurück, das den Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="2d503-148">The `Start-Job` cmdlet returns an object that represents the job.</span></span>

   <span data-ttu-id="2d503-149">Mit diesem Befehl wird das Auftrags Objekt in der `$job` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d503-149">This command saves the job object in the `$job` variable.</span></span>

   ```powershell
   Server01\C:> $job = Start-Job -scriptblock {
     Get-Eventlog "Windows PowerShell"
   }
   ```

   <span data-ttu-id="2d503-150">Während der Ausführung des Auftrags können Sie die interaktive Sitzung verwenden, um andere Befehle auszuführen, einschließlich anderer Aufträge.</span><span class="sxs-lookup"><span data-stu-id="2d503-150">While the job runs, you can use the interactive session to run other commands, including other jobs.</span></span> <span data-ttu-id="2d503-151">Sie müssen jedoch die interaktive Sitzung geöffnet lassen, bis der Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2d503-151">However, you must keep the interactive session open until the job is completed.</span></span> <span data-ttu-id="2d503-152">Wenn Sie die Sitzung beenden, wird der Auftrag unterbrochen, und die Ergebnisse gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="2d503-152">If you end the session, the job is interrupted, and the results are lost.</span></span>

1. <span data-ttu-id="2d503-153">Wenn Sie herausfinden möchten, ob der Auftrag beendet ist, zeigen Sie den Wert der `$job` Variablen an, oder verwenden Sie das `Get-Job` Cmdlet, um den Auftrag zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d503-153">To find out if the job is complete, display the value of the `$job` variable, or use the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="2d503-154">Der folgende Befehl verwendet das `Get-Job` Cmdlet, um den Auftrag anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d503-154">The following command uses the `Get-Job` cmdlet to display the job.</span></span>

   ```powershell
   Server01\C:> Get-Job $job

   SessionId  Name  State      HasMoreData  Location   Command
   ---------  ----  -----      -----------  --------   -------
   1          Job1  Complete   True         localhost  Get-Eventlog "Windows...
   ```

   <span data-ttu-id="2d503-155">Die `Get-Job` Ausgabe zeigt, dass der Auftrag auf dem Computer "localhost" ausgeführt wird, weil der Auftrag auf dem gleichen Computer gestartet wurde (in diesem Fall Server01).</span><span class="sxs-lookup"><span data-stu-id="2d503-155">The `Get-Job` output shows that job is running on the "localhost" computer because the job was started on and is running on the same computer (in this case, Server01).</span></span>

1. <span data-ttu-id="2d503-156">Verwenden Sie das-Cmdlet, um die Ergebnisse des Auftrags zu erhalten `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="2d503-156">To get the results of the job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="2d503-157">Sie können die Ergebnisse in der interaktiven Sitzung anzeigen oder Sie in einer Datei auf dem Remote Computer speichern.</span><span class="sxs-lookup"><span data-stu-id="2d503-157">You can display the results in the interactive session or save them to a file on the remote computer.</span></span> <span data-ttu-id="2d503-158">Der folgende Befehl ruft die Ergebnisse des Auftrags in der $Job-Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="2d503-158">The following command gets the results of the job in the $job variable.</span></span> <span data-ttu-id="2d503-159">Der Befehl verwendet den Umleitungs Operator ( `>` ), um die Ergebnisse des Auftrags in der PsLog.txt-Datei auf dem Server01-Computer zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2d503-159">The command uses the redirection operator (`>`) to save the results of the job in the PsLog.txt file on the Server01 computer.</span></span>

   ```powershell
   Server01\C:> Receive-Job $job > c:\logs\PsLog.txt
   ```

1. <span data-ttu-id="2d503-160">Verwenden Sie das-Cmdlet, um die interaktive Sitzung zu beenden `Exit-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="2d503-160">To end the interactive session, use the `Exit-PSSession` cmdlet.</span></span> <span data-ttu-id="2d503-161">Die Eingabeaufforderung ändert sich, um anzuzeigen, dass Sie sich wieder in der ursprünglichen Sitzung auf dem lokalen Computer befinden.</span><span class="sxs-lookup"><span data-stu-id="2d503-161">The command prompt changes to show that you are back in the original session on the local computer.</span></span>

   ```powershell
   Server01\C:> Exit-PSSession
   C:\PS>
   ```

1. <span data-ttu-id="2d503-162">Um den Inhalt der `PsLog.txt` Datei auf dem Server01-Computer zu einem beliebigen Zeitpunkt anzuzeigen, starten Sie eine andere interaktive Sitzung, oder führen Sie einen Remote Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="2d503-162">To view the contents of the `PsLog.txt` file on the Server01 computer at any time, start another interactive session, or run a remote command.</span></span> <span data-ttu-id="2d503-163">Diese Art von Befehl wird am besten in einer PSSession (eine permanente Verbindung) ausgeführt, wenn Sie mehrere Befehle verwenden möchten, um die Daten in der Datei zu untersuchen und zu verwalten `PsLog.txt` .</span><span class="sxs-lookup"><span data-stu-id="2d503-163">This type of command is best run in a PSSession (a persistent connection) in case you want to use several commands to investigate and manage the data in the `PsLog.txt` file.</span></span> <span data-ttu-id="2d503-164">Weitere Informationen zu pssessions finden Sie unter [about_PSSessions](about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="2d503-164">For more information about PSSessions, see [about_PSSessions](about_PSSessions.md).</span></span>

   <span data-ttu-id="2d503-165">Die folgenden Befehle verwenden das `New-PSSession` Cmdlet, um eine **PSSession** zu erstellen, die mit dem Server01-Computer verbunden ist, und Sie verwenden das `Invoke-Command` Cmdlet, um einen `Get-Content` Befehl in der PSSession auszuführen und den Inhalt der Datei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d503-165">The following commands use the `New-PSSession` cmdlet to create a **PSSession** that is connected to the Server01 computer, and they use the `Invoke-Command` cmdlet to run a `Get-Content` command in the PSSession to view the contents of the file.</span></span>

   ```powershell
   $s = New-PSSession -computername Server01
   Invoke-Command -session $s -scriptblock {
     Get-Content c:\logs\pslog.txt}
   ```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a><span data-ttu-id="2d503-166">Starten eines Remote Auftrags, der die Ergebnisse an den lokalen Computer zurückgibt (AsJob)</span><span class="sxs-lookup"><span data-stu-id="2d503-166">Start a remote job that returns the results to the local computer (AsJob)</span></span>

<span data-ttu-id="2d503-167">Um einen Auftrag auf einem Remote Computer zu starten, der die Ergebnisse des Befehls an den lokalen Computer zurückgibt, verwenden Sie den **AsJob** -Parameter eines Cmdlets, z `Invoke-Command` . b. das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d503-167">To start a job on a remote computer that returns the command results to the local computer, use the **AsJob** parameter of a cmdlet such as the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="2d503-168">Wenn Sie den **AsJob** -Parameter verwenden, wird das Auftrags Objekt tatsächlich auf dem lokalen Computer erstellt, obwohl der Auftrag auf dem Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d503-168">When you use the **AsJob** parameter, the job object is actually created on the local computer even though the job runs on the remote computer.</span></span> <span data-ttu-id="2d503-169">Wenn der Auftrag abgeschlossen ist, werden die Ergebnisse an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2d503-169">When the job is completed, the results are returned to the local computer.</span></span>

<span data-ttu-id="2d503-170">Sie können die-Cmdlets verwenden, die das Auftrags Substantiv (die Job-Cmdlets) enthalten, um alle Aufträge zu verwalten, die von einem Cmdlet erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2d503-170">You can use the cmdlets that contain the Job noun (the Job cmdlets) to manage any job created by any cmdlet.</span></span> <span data-ttu-id="2d503-171">Viele Cmdlets, die über **AsJob** -Parameter verfügen, verwenden keine PowerShell-Remoting, Sie können Sie auch auf Computern verwenden, die nicht für Remoting konfiguriert sind und die Anforderungen für Remoting nicht erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2d503-171">Many of the cmdlets that have **AsJob** parameters do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting and that do not meet the requirements for remoting.</span></span>

1. <span data-ttu-id="2d503-172">Der folgende Befehl verwendet den **AsJob** -Parameter von `Invoke-Command` , um einen Auftrag auf dem Server01-Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="2d503-172">The following command uses the **AsJob** parameter of `Invoke-Command` to start a job on the Server01 computer.</span></span> <span data-ttu-id="2d503-173">Der Auftrag führt einen `Get-Eventlog` Befehl aus, der die Ereignisse im System Protokoll abruft.</span><span class="sxs-lookup"><span data-stu-id="2d503-173">The job runs a `Get-Eventlog` command that gets the events in the System log.</span></span> <span data-ttu-id="2d503-174">Sie können den Jobname-Parameter verwenden, um dem Auftrag einen anzeigen Amen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="2d503-174">You can use the JobName parameter to assign a display name to the job.</span></span>

   ```powershell
   Invoke-Command -computername Server01 -scriptblock {
     Get-Eventlog system} -AsJob
   ```

   <span data-ttu-id="2d503-175">Die Ergebnisse des Befehls ähneln der folgenden Beispielausgabe.</span><span class="sxs-lookup"><span data-stu-id="2d503-175">The results of the command resemble the following sample output.</span></span>

   ```Output
   SessionId   Name   State    HasMoreData   Location   Command
   ---------   ----   -----    -----------   --------   -------
   1           Job1   Running  True          Server01   Get-Eventlog system
   ```

   <span data-ttu-id="2d503-176">Wenn der **AsJob** -Parameter verwendet wird, `Invoke-Command` gibt den gleichen Typ von Auftrags Objekten zurück, der `Start-Job` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2d503-176">When the **AsJob** parameter is used, `Invoke-Command` returns the same type of job object that `Start-Job` returns.</span></span> <span data-ttu-id="2d503-177">Sie können das Auftrags Objekt in einer Variablen speichern, oder Sie können einen Befehl verwenden, `Get-Job` um den Auftrag zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d503-177">You can save the job object in a variable, or you can use a `Get-Job` command to get the job.</span></span>

   <span data-ttu-id="2d503-178">Beachten Sie, dass der Wert der Location-Eigenschaft anzeigt, dass der Auftrag auf dem Server01-Computer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="2d503-178">Note that the value of the Location property shows that the job ran on the Server01 computer.</span></span>

1. <span data-ttu-id="2d503-179">Verwenden Sie die Job-Cmdlets, um einen Auftrag zu verwalten, der mit dem **AsJob** -Parameter des `Invoke-Command` Cmdlets gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="2d503-179">To manage a job started by using the **AsJob** parameter of the `Invoke-Command` cmdlet, use the Job cmdlets.</span></span> <span data-ttu-id="2d503-180">Da sich das Auftrags Objekt, das den Remote Auftrag darstellt, auf dem lokalen Computer befindet, müssen Sie keine Remote Befehle ausführen, um den Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2d503-180">Because the job object that represents the remote job is on the local computer, you do not need to run remote commands to manage the job.</span></span>

   <span data-ttu-id="2d503-181">Um zu ermitteln, ob der Auftrag fertiggestellt ist, verwenden Sie einen- `Get-Job` Befehl.</span><span class="sxs-lookup"><span data-stu-id="2d503-181">To determine whether the job is complete, use a `Get-Job` command.</span></span> <span data-ttu-id="2d503-182">Der folgende Befehl ruft alle Aufträge ab, die in der aktuellen Sitzung gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="2d503-182">The following command gets all of the jobs that were started in the current session.</span></span>

   ```powershell
   Get-Job
   ```

   <span data-ttu-id="2d503-183">Da der Remote Auftrag in der aktuellen Sitzung gestartet wurde, `Get-Job` wird der Auftrag mit einem lokalen Befehl abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2d503-183">Because the remote job was started in the current session, a local `Get-Job` command gets the job.</span></span> <span data-ttu-id="2d503-184">Die State-Eigenschaft des Auftrags Objekts zeigt, dass der Befehl erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="2d503-184">The State property of the job object shows that the command was completed successfully.</span></span>

   ```Output
   SessionId   Name   State      HasMoreData   Location   Command
   ---------   ----   -----      -----------   --------   -------
   1           Job1   Completed  True          Server01   Get-Eventlog system
   ```

1. <span data-ttu-id="2d503-185">Verwenden Sie das-Cmdlet, um die Ergebnisse des Auftrags zu erhalten `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="2d503-185">To get the results of the job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="2d503-186">Da die Auftrags Ergebnisse automatisch an den Computer zurückgegeben werden, auf dem sich das Auftrags Objekt befindet, können Sie die Ergebnisse mit einem lokalen `Receive-Job` Befehl erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d503-186">Because the job results are automatically returned to the computer where the job object resides, you can get the results with a local `Receive-Job` command.</span></span>

   <span data-ttu-id="2d503-187">Der folgende Befehl verwendet das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d503-187">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="2d503-188">Die Sitzungs-ID wird verwendet, um den Auftrag zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2d503-188">It uses the session ID to identify the job.</span></span> <span data-ttu-id="2d503-189">Mit diesem Befehl werden die Auftrags Ergebnisse in der $results Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d503-189">This command saves the job results in the $results variable.</span></span> <span data-ttu-id="2d503-190">Sie können die Ergebnisse auch in eine Datei umleiten.</span><span class="sxs-lookup"><span data-stu-id="2d503-190">You can also redirect the results to a file.</span></span>

   ```powershell
   $results = Receive-Job -id 1
   ```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a><span data-ttu-id="2d503-191">Starten eines Remote Auftrags, der die Ergebnisse auf dem Remote Computer beibehält</span><span class="sxs-lookup"><span data-stu-id="2d503-191">Start a remote job that keeps the results on the remote computer</span></span>

<span data-ttu-id="2d503-192">Verwenden Sie zum Starten eines Auftrags auf einem Remote Computer, der die Befehls Ergebnisse auf dem Remote Computer beibehält, das- `Invoke-Command` Cmdlet, um einen `Start-Job` Befehl auf einem Remote Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d503-192">To start a job on a remote computer that keeps the command results on the remote computer, use the `Invoke-Command` cmdlet to run a `Start-Job` command on a remote computer.</span></span> <span data-ttu-id="2d503-193">Mit dieser Methode können Sie Aufträge auf mehreren Computern ausführen.</span><span class="sxs-lookup"><span data-stu-id="2d503-193">You can use this method to run jobs on multiple computers.</span></span>

<span data-ttu-id="2d503-194">Wenn Sie einen `Start-Job` Befehl Remote ausführen, wird das Auftrags Objekt auf dem Remote Computer erstellt, und die Auftrags Ergebnisse werden auf dem Remote Computer beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2d503-194">When you run a `Start-Job` command remotely, the job object is created on the remote computer, and the job results are maintained on the remote computer.</span></span>
<span data-ttu-id="2d503-195">Aus der Perspektive des Auftrags sind alle Vorgänge lokal.</span><span class="sxs-lookup"><span data-stu-id="2d503-195">From the perspective of the job, all operations are local.</span></span> <span data-ttu-id="2d503-196">Sie führen Befehle nur Remote aus, um einen lokalen Auftrag auf dem Remote Computer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2d503-196">You are just running commands remotely to manage a local job on the remote computer.</span></span>

1. <span data-ttu-id="2d503-197">Verwenden Sie das- `Invoke-Command` Cmdlet, um einen `Start-Job` Befehl auf einem Remote Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d503-197">Use the `Invoke-Command` cmdlet to run a `Start-Job` command on a remote computer.</span></span>

   <span data-ttu-id="2d503-198">Dieser Befehl erfordert eine PSSession (eine permanente Verbindung).</span><span class="sxs-lookup"><span data-stu-id="2d503-198">This command requires a PSSession (a persistent connection).</span></span> <span data-ttu-id="2d503-199">Wenn Sie den Computername-Parameter von verwenden, `Invoke-Command` um eine temporäre Verbindung herzustellen, `Invoke-Command` wird der Befehl als Complete betrachtet, wenn das Auftrags Objekt zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2d503-199">If you use the ComputerName parameter of `Invoke-Command` to establish a temporary connection, the `Invoke-Command` command is considered to be complete when the job object is returned.</span></span> <span data-ttu-id="2d503-200">Folglich wird die temporäre Verbindung geschlossen, und der Auftrag wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2d503-200">As a result, the temporary connection is closed, and the job is canceled.</span></span>

   <span data-ttu-id="2d503-201">Der folgende Befehl verwendet das `New-PSSession` Cmdlet, um eine PSSession zu erstellen, die mit dem Server01-Computer verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="2d503-201">The following command uses the `New-PSSession` cmdlet to create a PSSession that is connected to the Server01 computer.</span></span> <span data-ttu-id="2d503-202">Der Befehl speichert die PSSession in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="2d503-202">The command saves the PSSession in the `$s` variable.</span></span>

   ```powershell
   $s = New-PSSession -computername Server01
   ```

   <span data-ttu-id="2d503-203">Der nächste Befehl verwendet das `Invoke-Command` Cmdlet, um einen `Start-Job` Befehl in der PSSession auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d503-203">The next command uses the `Invoke-Command` cmdlet to run a `Start-Job` command in the PSSession.</span></span> <span data-ttu-id="2d503-204">Der `Start-Job` Befehl und der `Get-Eventlog` Befehl werden in geschweifte Klammern eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2d503-204">The `Start-Job` command and the `Get-Eventlog` command are enclosed in braces.</span></span>

   ```powershell
   Invoke-Command -session $s -scriptblock {
     Start-Job -scriptblock {Get-Eventlog system}}
   ```

   <span data-ttu-id="2d503-205">Die Ergebnisse ähneln der folgenden Beispielausgabe.</span><span class="sxs-lookup"><span data-stu-id="2d503-205">The results resemble the following sample output.</span></span>

   ```Output
   Id       Name    State      HasMoreData     Location   Command
   --       ----    -----      -----------     --------   -------
   2        Job2    Running    True            Localhost  Get-Eventlog system
   ```

   <span data-ttu-id="2d503-206">Wenn Sie einen `Start-Job` Befehl Remote ausführen, wird `Invoke-Command` der gleiche Typ von Auftrags Objekten zurückgegeben, der von zurückgegeben wird `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="2d503-206">When you run a `Start-Job` command remotely, `Invoke-Command` returns the same type of job object that `Start-Job` returns.</span></span> <span data-ttu-id="2d503-207">Sie können das Auftrags Objekt in einer Variablen speichern, oder Sie können einen Befehl verwenden, `Get-Job` um den Auftrag zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d503-207">You can save the job object in a variable, or you can use a `Get-Job` command to get the job.</span></span>

   <span data-ttu-id="2d503-208">Beachten Sie, dass der Wert der **Location** -Eigenschaft anzeigt, dass der Auftrag auf dem lokalen Computer ausgeführt wurde, der als "localhost" bezeichnet wird, obwohl der Auftrag auf dem Server01-Computer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="2d503-208">Note that the value of the **Location** property shows that the job ran on the local computer, known as "LocalHost", even though the job ran on the Server01 computer.</span></span> <span data-ttu-id="2d503-209">Da das Auftrags Objekt auf dem Computer Server01 erstellt wird und der Auftrag auf dem gleichen Computer ausgeführt wird, wird er als lokaler Hintergrund Auftrag betrachtet.</span><span class="sxs-lookup"><span data-stu-id="2d503-209">Because the job object is created on the Server01 computer and the job runs on the same computer, it is considered to be a local background job.</span></span>

1. <span data-ttu-id="2d503-210">Verwenden Sie zum Verwalten eines Remote Auftrags die **Job** -Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="2d503-210">To manage a remote job, use the **Job** cmdlets.</span></span> <span data-ttu-id="2d503-211">Da sich das Auftrags Objekt auf dem Remote Computer befindet, müssen Sie Remote Befehle ausführen, um die Auftrags Ergebnisse abzurufen, zu warten, abzufragen oder abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2d503-211">Because the job object is on the remote computer, you need to run remote commands to get, stop, wait for, or retrieve the job results.</span></span>

   <span data-ttu-id="2d503-212">Um festzustellen, ob der Auftrag beendet ist, verwenden `Invoke-Command` Sie einen Befehl, um einen `Get-Job` Befehl in der PSSession auszuführen, der mit dem Server01-Computer verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="2d503-212">To see if the job is complete, use an `Invoke-Command` command to run a `Get-Job` command in the PSSession that is connected to the Server01 computer.</span></span>

   ```powershell
   Invoke-Command -session $s -scriptblock {Get-Job}
   ```

   <span data-ttu-id="2d503-213">Der Befehl gibt ein Auftragsobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="2d503-213">The command returns a job object.</span></span> <span data-ttu-id="2d503-214">Die **State** -Eigenschaft des Auftrags Objekts zeigt, dass der Befehl erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="2d503-214">The **State** property of the job object shows that the command was completed successfully.</span></span>

   ```Output
   SessionId   Name  State      HasMoreData   Location   Command
   ---------   ----  -----      -----------   --------   -------
   2           Job2  Completed  True          LocalHost   Get-Eventlog system
   ```

1. <span data-ttu-id="2d503-215">Um die Ergebnisse des Auftrags abzurufen, verwenden Sie das `Invoke-Command` Cmdlet, um einen `Receive-Job` Befehl in der PSSession auszuführen, die mit dem Server01-Computer verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="2d503-215">To get the results of the job, use the `Invoke-Command` cmdlet to run a `Receive-Job` command in the PSSession that is connected to the Server01 computer.</span></span>

   <span data-ttu-id="2d503-216">Der folgende Befehl verwendet das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d503-216">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="2d503-217">Die Sitzungs-ID wird verwendet, um den Auftrag zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2d503-217">It uses the session ID to identify the job.</span></span> <span data-ttu-id="2d503-218">Mit diesem Befehl werden die Auftrags Ergebnisse in der `$results` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d503-218">This command saves the job results in the `$results` variable.</span></span> <span data-ttu-id="2d503-219">Er verwendet den Keep-Parameter von `Receive-Job` , um das Ergebnis im Auftrags Cache auf dem Remote Computer beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="2d503-219">It uses the Keep parameter of `Receive-Job` to keep the result in the job cache on the remote computer.</span></span>

   ```powershell
   $results = Invoke-Command -session $s -scriptblock {
     Receive-Job -SessionId 2 -Keep
   }
   ```

   <span data-ttu-id="2d503-220">Sie können die Ergebnisse auch in eine Datei auf dem lokalen Computer oder auf einem Remote Computer umleiten.</span><span class="sxs-lookup"><span data-stu-id="2d503-220">You can also redirect the results to a file on the local or remote computer.</span></span>
   <span data-ttu-id="2d503-221">Der folgende Befehl verwendet einen Umleitungs Operator, um die Ergebnisse in einer Datei auf dem Server01-Computer zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2d503-221">The following command uses a redirection operator to save the results in a file on the Server01 computer.</span></span>

   ```powershell
   Invoke-Command -session $s -command {
     Receive-Job -SessionId 2 > c:\logs\pslog.txt
   }
   ```

## <a name="how-to-run-as-a-detached-process"></a><span data-ttu-id="2d503-222">Ausführen als getrennter Prozess</span><span class="sxs-lookup"><span data-stu-id="2d503-222">How to run as a detached process</span></span>

<span data-ttu-id="2d503-223">Wie bereits erwähnt, werden alle untergeordneten Aufträge, die ausgeführt werden, zusammen mit ihren untergeordneten Prozessen beendet, wenn die übergeordnete Sitzung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d503-223">As previously mentioned, when the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span> <span data-ttu-id="2d503-224">Sie können Remoting auf dem lokalen Computer verwenden, um Aufträge auszuführen, die nicht an die aktuelle PowerShell-Sitzung angefügt sind.</span><span class="sxs-lookup"><span data-stu-id="2d503-224">You can use remoting on the local machine to run jobs that are not attached to the current PowerShell session.</span></span>

<span data-ttu-id="2d503-225">Erstellen Sie eine neue PowerShell-Sitzung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="2d503-225">Create a new PowerShell session on the local machine.</span></span> <span data-ttu-id="2d503-226">Der `Invoke-Command` zum Starten eines Auftrags in dieser Sitzung verwendete.</span><span class="sxs-lookup"><span data-stu-id="2d503-226">The use `Invoke-Command` to start a job in this session.</span></span> <span data-ttu-id="2d503-227">`Invoke-Command` ermöglicht das Trennen einer Remote Sitzung und das Beenden der übergeordneten Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2d503-227">`Invoke-Command` allows you to disconnect a remote session and terminate the parent session.</span></span> <span data-ttu-id="2d503-228">Später können Sie eine neue PowerShell-Sitzung starten und eine Verbindung mit der zuvor getrennten Sitzung herstellen, um die Überwachung des Auftrags fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="2d503-228">Later, you can start a new PowerShell session and connect to the previously disconnected session to resume monitoring the job.</span></span> <span data-ttu-id="2d503-229">Alle Daten, die an die ursprüngliche PowerShell-Sitzung zurückgegeben wurden, gehen jedoch verloren, wenn diese Sitzung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d503-229">However, any data that was returned to the original PowerShell session is lost when that session is terminated.</span></span> <span data-ttu-id="2d503-230">Wenn die Verbindung erneut hergestellt wird, werden nur neue Datenobjekte zurückgegeben, die nach der Trennung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="2d503-230">Only new data objects generated after the disconnect are returned when re-connected.</span></span>

```powershell
# Create remote session on local machine
PS> $session = New-PSSession -cn localhost

# Start remote job
PS> $job = Invoke-Command -Session $session -ScriptBlock { 1..60 | % { sleep 1; "Output $_" } } -AsJob
PS> $job

Id     Name     PSJobTypeName   State         HasMoreData     Location      Command
--     ----     -------------   -----         -----------     --------      -------
1      Job1     RemoteJob       Running       True            localhost     1..60 | % { sleep 1; ...

# Disconnect the job session
PS> Disconnect-PSSession $session

Id Name         Transport ComputerName    ComputerType    State         ConfigurationName     Availability
-- ----         --------- ------------    ------------    -----         -----------------     ------------
1 Runspace1     WSMan     localhost       RemoteMachine   Disconnected  Microsoft.PowerShell          None

PS> $job

Id     Name     PSJobTypeName   State         HasMoreData     Location      Command
--     ----     -------------   -----         -----------     --------      -------
1      Job1     RemoteJob       Disconnected  True            localhost     1..60 | % { sleep 1;

# Reconnect the session to a new job object
PS> $jobNew = Receive-PSSession -Session $session -OutTarget Job
PS> $job | Wait-Job | Receive-Job
Output 9
Output 10
Output 11
...
```

<span data-ttu-id="2d503-231">In diesem Beispiel werden die Aufträge immer noch an eine übergeordnete PowerShell-Sitzung angefügt.</span><span class="sxs-lookup"><span data-stu-id="2d503-231">For this example, the jobs are still attached to a parent PowerShell session.</span></span>
<span data-ttu-id="2d503-232">Allerdings ist die übergeordnete Sitzung nicht die ursprüngliche PowerShell-Sitzung, in der `Invoke-Command` ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="2d503-232">However, the parent session is not the original PowerShell session where `Invoke-Command` was run.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d503-233">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d503-233">See also</span></span>

- [<span data-ttu-id="2d503-234">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="2d503-234">about_Jobs</span></span>](about_Jobs.md)
- [<span data-ttu-id="2d503-235">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="2d503-235">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="2d503-236">about_Remote</span><span class="sxs-lookup"><span data-stu-id="2d503-236">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="2d503-237">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="2d503-237">about_Remote_Variables</span></span>](about_Remote_Variables.md)
- [<span data-ttu-id="2d503-238">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="2d503-238">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [<span data-ttu-id="2d503-239">Start-Job</span><span class="sxs-lookup"><span data-stu-id="2d503-239">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="2d503-240">Get-Job</span><span class="sxs-lookup"><span data-stu-id="2d503-240">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="2d503-241">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="2d503-241">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="2d503-242">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="2d503-242">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="2d503-243">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="2d503-243">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="2d503-244">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="2d503-244">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
- [<span data-ttu-id="2d503-245">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="2d503-245">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)
- [<span data-ttu-id="2d503-246">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="2d503-246">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)
