---
description: Hier wird beschrieben, wie Hintergrund Aufträge auf Remote Computern ausgeführt werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: fb2270ea5c0acdcf2c506e687787d22c73e2cb2c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222887"
---
# <a name="about-remote-jobs"></a><span data-ttu-id="67bdc-104">Informationen zu Remote Aufträgen</span><span class="sxs-lookup"><span data-stu-id="67bdc-104">About Remote Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="67bdc-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="67bdc-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="67bdc-106">Hier wird beschrieben, wie Hintergrund Aufträge auf Remote Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="67bdc-106">Describes how to run background jobs on remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="67bdc-107">DETAILLIERTE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="67bdc-107">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="67bdc-108">Ein Hintergrund Auftrag ist ein Befehl, der asynchron ausgeführt wird, ohne mit der aktuellen Sitzung zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="67bdc-108">A background job is a command that runs asynchronously without interacting with the current session.</span></span> <span data-ttu-id="67bdc-109">Die Eingabeaufforderung wird sofort zurückgegeben, und Sie können die Sitzung weiterhin verwenden, während der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="67bdc-109">The command prompt returns immediately, and you can continue to use the session while the job runs.</span></span>

<span data-ttu-id="67bdc-110">Standardmäßig werden Hintergrund Aufträge auf dem lokalen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="67bdc-110">By default, background jobs run on the local computer.</span></span> <span data-ttu-id="67bdc-111">Sie können jedoch mehrere verschiedene Prozeduren verwenden, um Hintergrund Aufträge auf Remote Computern auszuführen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-111">However, you can use several different procedures to run background jobs on remote computers.</span></span>

<span data-ttu-id="67bdc-112">In diesem Thema wird erläutert, wie ein Hintergrund Auftrag auf einem Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="67bdc-112">This topic explains how to run a background job on a remote computer.</span></span> <span data-ttu-id="67bdc-113">Informationen zum Ausführen von Hintergrund Aufträgen auf einem lokalen Computer finden Sie unter [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="67bdc-113">For information about how to run background jobs on a local computer, see [about_Jobs](about_Jobs.md).</span></span> <span data-ttu-id="67bdc-114">Weitere Informationen zu Hintergrund Aufträgen finden Sie unter [about_Job_Details](about_Job_Details.md).</span><span class="sxs-lookup"><span data-stu-id="67bdc-114">For more information about background jobs, see [about_Job_Details](about_Job_Details.md).</span></span>

## <a name="remote-background-jobs"></a><span data-ttu-id="67bdc-115">Remote Hintergrund Aufträge</span><span class="sxs-lookup"><span data-stu-id="67bdc-115">REMOTE BACKGROUND JOBS</span></span>

<span data-ttu-id="67bdc-116">Sie können Hintergrund Aufträge auf Remote Computern ausführen, indem Sie drei verschiedene Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="67bdc-116">You can run background jobs on remote computers by using three different methods.</span></span>

- <span data-ttu-id="67bdc-117">Starten Sie eine interaktive Sitzung mit einem Remote Computer, und starten Sie einen Auftrag in der interaktiven Sitzung.</span><span class="sxs-lookup"><span data-stu-id="67bdc-117">Start an interactive session with a remote computer, and start a job in the interactive session.</span></span> <span data-ttu-id="67bdc-118">Die Prozeduren sind mit dem Ausführen eines lokalen Auftrags identisch, obwohl alle Aktionen auf dem Remote Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="67bdc-118">The procedures are the same as running a local job, although all actions are performed on the remote computer.</span></span>

- <span data-ttu-id="67bdc-119">Führen Sie einen Hintergrund Auftrag auf einem Remote Computer aus, von dem die Ergebnisse an den lokalen Computer zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="67bdc-119">Run a background job on a remote computer that returns its results to the local computer.</span></span> <span data-ttu-id="67bdc-120">Verwenden Sie diese Methode, wenn Sie die Ergebnisse der Hintergrund Aufträge erfassen und an einem zentralen Speicherort auf dem lokalen Computer aufbewahren möchten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-120">Use this method when you want to collect the results of background jobs and maintain them in a central location on the local computer.</span></span>

- <span data-ttu-id="67bdc-121">Führen Sie einen Hintergrund Auftrag auf einem Remote Computer aus, der seine Ergebnisse auf dem Remote Computer beibehält.</span><span class="sxs-lookup"><span data-stu-id="67bdc-121">Run a background job on a remote computer that maintains its results on the remote computer.</span></span> <span data-ttu-id="67bdc-122">Verwenden Sie diese Methode, wenn die Auftragsdaten auf dem Ursprungs Computer sicherer verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="67bdc-122">Use this method when the job data is more securely maintained on the originating computer.</span></span>

### <a name="start-a-background-job-in-an-interactive-session"></a><span data-ttu-id="67bdc-123">Starten eines Hintergrund Auftrags in einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="67bdc-123">START A BACKGROUND JOB IN AN INTERACTIVE SESSION</span></span>

<span data-ttu-id="67bdc-124">Sie können eine interaktive Sitzung mit einem Remote Computer starten und dann während der interaktiven Sitzung einen Hintergrund Auftrag starten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-124">You can start an interactive session with a remote computer and then start a background job during the interactive session.</span></span> <span data-ttu-id="67bdc-125">Weitere Informationen zu interaktiven Sitzungen finden Sie unter about_Remote und Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="67bdc-125">For more information about interactive sessions, see about_Remote, and see Enter-PSSession.</span></span>

<span data-ttu-id="67bdc-126">Das Verfahren zum Starten eines Hintergrund Auftrags in einer interaktiven Sitzung ist fast identisch mit dem Verfahren zum Starten eines Hintergrund Auftrags auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="67bdc-126">The procedure for starting a background job in an interactive session is almost identical to the procedure for starting a background job on the local computer.</span></span> <span data-ttu-id="67bdc-127">Allerdings erfolgen alle Vorgänge auf dem Remote Computer, nicht auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="67bdc-127">However, all of the operations occur on the remote computer, not the local computer.</span></span>

#### <a name="step-1-enter-pssession"></a><span data-ttu-id="67bdc-128">Schritt 1: Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="67bdc-128">STEP 1: ENTER-PSSESSION</span></span>

<span data-ttu-id="67bdc-129">Verwenden Sie das Cmdlet "Enter-PSSession", um eine interaktive Sitzung mit einem Remote Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-129">Use the Enter-PSSession cmdlet to start an interactive session with a remote computer.</span></span> <span data-ttu-id="67bdc-130">Sie können den Computername-Parameter von Enter-PSSession verwenden, um eine temporäre Verbindung für die interaktive Sitzung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-130">You can use the ComputerName parameter of Enter-PSSession to establish a temporary connection for the interactive session.</span></span> <span data-ttu-id="67bdc-131">Oder Sie können den Session-Parameter verwenden, um die interaktive Sitzung in einer PowerShell-Sitzung (PSSession) auszuführen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-131">Or, you can use the Session parameter to run the interactive session in a PowerShell session (PSSession).</span></span>

<span data-ttu-id="67bdc-132">Der folgende Befehl startet eine interaktive Sitzung auf dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="67bdc-132">The following command starts an interactive session on the Server01 computer.</span></span>

```powershell
C:\PS> Enter-PSSession -computername Server01
```

<span data-ttu-id="67bdc-133">Die Eingabeaufforderung ändert sich, um anzuzeigen, dass Sie jetzt mit dem Computer Server01 verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="67bdc-133">The command prompt changes to show that you are now connected to the Server01 computer.</span></span>

```
Server01\C:>
```

#### <a name="step-2-start-job"></a><span data-ttu-id="67bdc-134">Schritt 2: Starten eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="67bdc-134">STEP 2: START-JOB</span></span>

<span data-ttu-id="67bdc-135">Verwenden Sie das Cmdlet "Start-Job", um einen Hintergrund Auftrag in der Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-135">To start a background job in the session, use the Start-Job cmdlet.</span></span>

<span data-ttu-id="67bdc-136">Der folgende Befehl führt einen Hintergrund Auftrag aus, der die Ereignisse im Windows PowerShell-Ereignisprotokoll auf dem Server01-Computer abruft.</span><span class="sxs-lookup"><span data-stu-id="67bdc-136">The following command runs a background job that gets the events in the Windows PowerShell event log on the Server01 computer.</span></span> <span data-ttu-id="67bdc-137">Das Start-Job-Cmdlet gibt ein Objekt zurück, das den Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="67bdc-137">The Start-Job cmdlet returns an object that represents the job.</span></span>

<span data-ttu-id="67bdc-138">Mit diesem Befehl wird das Auftrags Objekt in der \$ Auftrags Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="67bdc-138">This command saves the job object in the \$job variable.</span></span>

```powershell
Server01\C:> $job = start-job -scriptblock {
  get-eventlog "Windows PowerShell"
}
```

<span data-ttu-id="67bdc-139">Während der Ausführung des Auftrags können Sie die interaktive Sitzung verwenden, um andere Befehle auszuführen, einschließlich anderer Hintergrund Aufträge.</span><span class="sxs-lookup"><span data-stu-id="67bdc-139">While the job runs, you can use the interactive session to run other commands, including other background jobs.</span></span> <span data-ttu-id="67bdc-140">Sie müssen jedoch die interaktive Sitzung geöffnet lassen, bis der Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="67bdc-140">However, you must keep the interactive session open until the job is completed.</span></span> <span data-ttu-id="67bdc-141">Wenn Sie die Sitzung beenden, wird der Auftrag unterbrochen, und die Ergebnisse gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="67bdc-141">If you end the session, the job is interrupted, and the results are lost.</span></span>

#### <a name="step-3-get-job"></a><span data-ttu-id="67bdc-142">Schritt 3: Get-Job</span><span class="sxs-lookup"><span data-stu-id="67bdc-142">STEP 3: GET-JOB</span></span>

<span data-ttu-id="67bdc-143">Wenn Sie herausfinden möchten, ob der Auftrag beendet ist, zeigen Sie den Wert der \$ Auftrags Variablen an, oder verwenden Sie das Cmdlet "Get-Job", um den Auftrag zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-143">To find out if the job is complete, display the value of the \$job variable, or use the Get-Job cmdlet to get the job.</span></span> <span data-ttu-id="67bdc-144">Der folgende Befehl verwendet das Cmdlet "Get-Job", um den Auftrag anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-144">The following command uses the Get-Job cmdlet to display the job.</span></span>

```powershell
Server01\C:> get-job $job

SessionId  Name  State      HasMoreData  Location   Command
---------  ----  -----      -----------  --------   -------
1          Job1  Complete   True         localhost  get-eventlog "Windows...
```

<span data-ttu-id="67bdc-145">Die Get-Job Ausgabe zeigt, dass der Auftrag auf dem Computer "localhost" ausgeführt wird, weil der Auftrag auf dem gleichen Computer gestartet wurde (in diesem Fall Server01).</span><span class="sxs-lookup"><span data-stu-id="67bdc-145">The Get-Job output shows that job is running on the "localhost" computer because the job was started on and is running on the same computer (in this case, Server01).</span></span>

#### <a name="step-4-receive-job"></a><span data-ttu-id="67bdc-146">Schritt 4: Receive-Job</span><span class="sxs-lookup"><span data-stu-id="67bdc-146">STEP 4: RECEIVE-JOB</span></span>

<span data-ttu-id="67bdc-147">Verwenden Sie das Cmdlet "Receive-Job", um die Ergebnisse des Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-147">To get the results of the job, use the Receive-Job cmdlet.</span></span> <span data-ttu-id="67bdc-148">Sie können die Ergebnisse in der interaktiven Sitzung anzeigen oder Sie in einer Datei auf dem Remote Computer speichern.</span><span class="sxs-lookup"><span data-stu-id="67bdc-148">You can display the results in the interactive session or save them to a file on the remote computer.</span></span> <span data-ttu-id="67bdc-149">Der folgende Befehl ruft die Ergebnisse des Auftrags in der $Job-Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="67bdc-149">The following command gets the results of the job in the $job variable.</span></span> <span data-ttu-id="67bdc-150">Der Befehl verwendet den Umleitungs Operator (>), um die Ergebnisse des Auftrags in der PsLog.txt-Datei auf dem Server01-Computer zu speichern.</span><span class="sxs-lookup"><span data-stu-id="67bdc-150">The command uses the redirection operator (>) to save the results of the job in the PsLog.txt file on the Server01 computer.</span></span>

```powershell
Server01\C:> receive-job $job > c:\logs\PsLog.txt
```

#### <a name="step-5-exit-pssession"></a><span data-ttu-id="67bdc-151">Schritt 5: Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="67bdc-151">STEP 5: EXIT-PSSESSION</span></span>

<span data-ttu-id="67bdc-152">Verwenden Sie das Cmdlet "Exit-PSSession", um die interaktive Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="67bdc-152">To end the interactive session, use the Exit-PSSession cmdlet.</span></span> <span data-ttu-id="67bdc-153">Die Eingabeaufforderung ändert sich, um anzuzeigen, dass Sie sich wieder in der ursprünglichen Sitzung auf dem lokalen Computer befinden.</span><span class="sxs-lookup"><span data-stu-id="67bdc-153">The command prompt changes to show that you are back in the original session on the local computer.</span></span>

```powershell
Server01\C:> Exit-PSSession
C:\PS>
```

#### <a name="step-6-invoke-command-get-content"></a><span data-ttu-id="67bdc-154">Schritt 6: Aufrufen-Befehl: Get-Content</span><span class="sxs-lookup"><span data-stu-id="67bdc-154">STEP 6: INVOKE-COMMAND: GET-CONTENT</span></span>

<span data-ttu-id="67bdc-155">Um den Inhalt der PsLog.txt Datei auf dem Server01-Computer zu einem beliebigen Zeitpunkt anzuzeigen, starten Sie eine andere interaktive Sitzung, oder führen Sie einen Remote Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="67bdc-155">To view the contents of the PsLog.txt file on the Server01 computer at any time, start another interactive session, or run a remote command.</span></span> <span data-ttu-id="67bdc-156">Diese Art von Befehl wird am besten in einer PSSession (eine permanente Verbindung) ausgeführt, wenn Sie mehrere Befehle verwenden möchten, um die Daten in der PsLog.txt Datei zu untersuchen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-156">This type of command is best run in a PSSession (a persistent connection) in case you want to use several commands to investigate and manage the data in the PsLog.txt file.</span></span> <span data-ttu-id="67bdc-157">Weitere Informationen zu pssessions finden Sie unter about_PSSessions.</span><span class="sxs-lookup"><span data-stu-id="67bdc-157">For more information about PSSessions, see about_PSSessions.</span></span>

<span data-ttu-id="67bdc-158">Die folgenden Befehle verwenden das New-PSSession-Cmdlet, um eine PSSession zu erstellen, die mit dem Server01-Computer verbunden ist, und Sie verwenden das Invoke-Command-Cmdlet, um einen Get-Content Befehl in der PSSession auszuführen und den Inhalt der Datei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-158">The following commands use the New-PSSession cmdlet to create a PSSession that is connected to the Server01 computer, and they use the Invoke-Command cmdlet to run a Get-Content command in the PSSession to view the contents of the file.</span></span>

```powershell
$s = new-pssession -computername Server01
invoke-command -session $s -scriptblock {
  get-content c:\logs\pslog.txt}
```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a><span data-ttu-id="67bdc-159">Starten eines Remote Auftrags, der die Ergebnisse an den lokalen Computer \( AsJob zurückgibt\)</span><span class="sxs-lookup"><span data-stu-id="67bdc-159">START A REMOTE JOB THAT RETURNS THE RESULTS TO THE LOCAL COMPUTER \(ASJOB\)</span></span>

<span data-ttu-id="67bdc-160">Um einen Hintergrund Auftrag auf einem Remote Computer zu starten, der die Befehls Ergebnisse an den lokalen Computer zurückgibt, verwenden Sie den AsJob-Parameter eines Cmdlets, z. b. das Cmdlet "Invoke-Command".</span><span class="sxs-lookup"><span data-stu-id="67bdc-160">To start a background job on a remote computer that returns the command results to the local computer, use the AsJob parameter of a cmdlet such as the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="67bdc-161">Wenn Sie den AsJob-Parameter verwenden, wird das Auftrags Objekt tatsächlich auf dem lokalen Computer erstellt, obwohl der Auftrag auf dem Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="67bdc-161">When you use the AsJob parameter, the job object is actually created on the local computer even though the job runs on the remote computer.</span></span> <span data-ttu-id="67bdc-162">Wenn der Auftrag abgeschlossen ist, werden die Ergebnisse an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="67bdc-162">When the job is completed, the results are returned to the local computer.</span></span>

<span data-ttu-id="67bdc-163">Sie können die-Cmdlets verwenden, die das Auftrags Substantiv (die Job-Cmdlets) enthalten, um alle Aufträge zu verwalten, die von einem Cmdlet erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="67bdc-163">You can use the cmdlets that contain the Job noun (the Job cmdlets) to manage any job created by any cmdlet.</span></span> <span data-ttu-id="67bdc-164">Viele Cmdlets, die über AsJob-Parameter verfügen, verwenden keine PowerShell-Remoting, Sie können Sie auch auf Computern verwenden, die nicht für Remoting konfiguriert sind und die Anforderungen für Remoting nicht erfüllen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-164">Many of the cmdlets that have AsJob parameters do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting and that do not meet the requirements for remoting.</span></span>

#### <a name="step-1-invoke-command--asjob"></a><span data-ttu-id="67bdc-165">Schritt 1: Aufrufen von "-Command-AsJob"</span><span class="sxs-lookup"><span data-stu-id="67bdc-165">STEP 1: INVOKE-COMMAND -ASJOB</span></span>

<span data-ttu-id="67bdc-166">Der folgende Befehl verwendet den AsJob-Parameter von Invoke-Command, um einen Hintergrund Auftrag auf dem Server01-Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-166">The following command uses the AsJob parameter of Invoke-Command to start a background job on the Server01 computer.</span></span> <span data-ttu-id="67bdc-167">Der Auftrag führt einen Get-Eventlog-Befehl aus, der die Ereignisse im Systemprotokoll abruft.</span><span class="sxs-lookup"><span data-stu-id="67bdc-167">The job runs a Get-Eventlog command that gets the events in the System log.</span></span> <span data-ttu-id="67bdc-168">Sie können den Jobname-Parameter verwenden, um dem Auftrag einen anzeigen Amen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-168">You can use the JobName parameter to assign a display name to the job.</span></span>

```powershell
invoke-command -computername Server01 -scriptblock {
  get-eventlog system} -asjob
```

<span data-ttu-id="67bdc-169">Die Ergebnisse des Befehls ähneln der folgenden Beispielausgabe.</span><span class="sxs-lookup"><span data-stu-id="67bdc-169">The results of the command resemble the following sample output.</span></span>

```Output
SessionId   Name   State    HasMoreData   Location   Command
---------   ----   -----    -----------   --------   -------
1           Job1   Running  True          Server01   get-eventlog system
```

<span data-ttu-id="67bdc-170">Wenn der AsJob-Parameter verwendet wird, gibt Invoke-Command denselben Typ von Auftrags Objekten zurück, den Start-Job zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="67bdc-170">When the AsJob parameter is used, Invoke-Command returns the same type of job object that Start-Job returns.</span></span> <span data-ttu-id="67bdc-171">Sie können das Auftrags Objekt in einer Variablen speichern, oder Sie können einen Get-Job Befehl verwenden, um den Auftrag zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-171">You can save the job object in a variable, or you can use a Get-Job command to get the job.</span></span>

<span data-ttu-id="67bdc-172">Beachten Sie, dass der Wert der Location-Eigenschaft anzeigt, dass der Auftrag auf dem Server01-Computer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="67bdc-172">Note that the value of the Location property shows that the job ran on the Server01 computer.</span></span>

#### <a name="step-2-get-job"></a><span data-ttu-id="67bdc-173">Schritt 2: Get-Job</span><span class="sxs-lookup"><span data-stu-id="67bdc-173">STEP 2: GET-JOB</span></span>

<span data-ttu-id="67bdc-174">Verwenden Sie die Job-Cmdlets, um einen Auftrag zu verwalten, der mit dem AsJob-Parameter des Invoke-Command-Cmdlets gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="67bdc-174">To manage a job started by using the AsJob parameter of the Invoke-Command cmdlet, use the Job cmdlets.</span></span> <span data-ttu-id="67bdc-175">Da sich das Auftrags Objekt, das den Remote Auftrag darstellt, auf dem lokalen Computer befindet, müssen Sie keine Remote Befehle ausführen, um den Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-175">Because the job object that represents the remote job is on the local computer, you do not need to run remote commands to manage the job.</span></span>

<span data-ttu-id="67bdc-176">Um zu ermitteln, ob der Auftrag fertiggestellt ist, verwenden Sie einen Get-Job Befehl.</span><span class="sxs-lookup"><span data-stu-id="67bdc-176">To determine whether the job is complete, use a Get-Job command.</span></span> <span data-ttu-id="67bdc-177">Der folgende Befehl ruft alle Aufträge ab, die in der aktuellen Sitzung gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="67bdc-177">The following command gets all of the jobs that were started in the current session.</span></span>

```powershell
get-job
```

<span data-ttu-id="67bdc-178">Da der Remote Auftrag in der aktuellen Sitzung gestartet wurde, wird der Auftrag mit einem lokalen Get-Job Befehl abgerufen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-178">Because the remote job was started in the current session, a local Get-Job command gets the job.</span></span> <span data-ttu-id="67bdc-179">Die State-Eigenschaft des Auftrags Objekts zeigt, dass der Befehl erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="67bdc-179">The State property of the job object shows that the command was completed successfully.</span></span>

```Output
SessionId   Name   State      HasMoreData   Location   Command
---------   ----   -----      -----------   --------   -------
1           Job1   Completed  True          Server01   get-eventlog system
```

#### <a name="step-3-receive-job"></a><span data-ttu-id="67bdc-180">Schritt 3: Empfangen eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="67bdc-180">STEP 3: RECEIVE-JOB</span></span>

<span data-ttu-id="67bdc-181">Verwenden Sie das Cmdlet "Receive-Job", um die Ergebnisse des Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-181">To get the results of the job, use the Receive-Job cmdlet.</span></span> <span data-ttu-id="67bdc-182">Da die Auftrags Ergebnisse automatisch an den Computer zurückgegeben werden, auf dem sich das Auftrags Objekt befindet, können Sie die Ergebnisse mit einem lokalen Receive-Job Befehl erhalten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-182">Because the job results are automatically returned to the computer where the job object resides, you can get the results with a local Receive-Job command.</span></span>

<span data-ttu-id="67bdc-183">Der folgende Befehl verwendet das Cmdlet "Receive-Job", um die Ergebnisse des Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-183">The following command uses the Receive-Job cmdlet to get the results of the job.</span></span> <span data-ttu-id="67bdc-184">Die Sitzungs-ID wird verwendet, um den Auftrag zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="67bdc-184">It uses the session ID to identify the job.</span></span> <span data-ttu-id="67bdc-185">Mit diesem Befehl werden die Auftrags Ergebnisse in der $results Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="67bdc-185">This command saves the job results in the $results variable.</span></span> <span data-ttu-id="67bdc-186">Sie können die Ergebnisse auch in eine Datei umleiten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-186">You can also redirect the results to a file.</span></span>

```powershell
$results = receive-job -id 1
```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a><span data-ttu-id="67bdc-187">Starten eines Remote Auftrags, der die Ergebnisse auf dem Remote Computer beibehält</span><span class="sxs-lookup"><span data-stu-id="67bdc-187">START A REMOTE JOB THAT KEEPS THE RESULTS ON THE REMOTE COMPUTER</span></span>

<span data-ttu-id="67bdc-188">Um einen Hintergrund Auftrag auf einem Remote Computer zu starten, der die Befehls Ergebnisse auf dem Remote Computer beibehält, verwenden Sie das Cmdlet "Invoke-Command", um einen Start-Job Befehl auf einem Remote Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-188">To start a background job on a remote computer that keeps the command results on the remote computer, use the Invoke-Command cmdlet to run a Start-Job command on a remote computer.</span></span> <span data-ttu-id="67bdc-189">Mit dieser Methode können Sie Hintergrund Aufträge auf mehreren Computern ausführen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-189">You can use this method to run background jobs on multiple computers.</span></span>

<span data-ttu-id="67bdc-190">Wenn Sie einen Start-Job Befehl Remote ausführen, wird das Auftrags Objekt auf dem Remote Computer erstellt, und die Auftrags Ergebnisse werden auf dem Remote Computer beibehalten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-190">When you run a Start-Job command remotely, the job object is created on the remote computer, and the job results are maintained on the remote computer.</span></span>
<span data-ttu-id="67bdc-191">Aus der Perspektive des Auftrags sind alle Vorgänge lokal.</span><span class="sxs-lookup"><span data-stu-id="67bdc-191">From the perspective of the job, all operations are local.</span></span> <span data-ttu-id="67bdc-192">Sie führen Befehle nur Remote aus, um einen lokalen Auftrag auf dem Remote Computer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-192">You are just running commands remotely to manage a local job on the remote computer.</span></span>

#### <a name="step-1-invoke-command-start-job"></a><span data-ttu-id="67bdc-193">Schritt 1: Aufrufen des Befehls Start-Job</span><span class="sxs-lookup"><span data-stu-id="67bdc-193">STEP 1: INVOKE-COMMAND START-JOB</span></span>

<span data-ttu-id="67bdc-194">Verwenden Sie das Cmdlet "Invoke-Command", um einen Start-Job Befehl auf einem Remote Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-194">Use the Invoke-Command cmdlet to run a Start-Job command on a remote computer.</span></span>

<span data-ttu-id="67bdc-195">Dieser Befehl erfordert eine PSSession (eine permanente Verbindung).</span><span class="sxs-lookup"><span data-stu-id="67bdc-195">This command requires a PSSession (a persistent connection).</span></span> <span data-ttu-id="67bdc-196">Wenn Sie den Computername-Parameter von Invoke-Command verwenden, um eine temporäre Verbindung herzustellen, wird der Invoke-Command Befehl als Complete betrachtet, wenn das Auftrags Objekt zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="67bdc-196">If you use the ComputerName parameter of Invoke-Command to establish a temporary connection, the Invoke-Command command is considered to be complete when the job object is returned.</span></span> <span data-ttu-id="67bdc-197">Folglich wird die temporäre Verbindung geschlossen, und der Auftrag wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-197">As a result, the temporary connection is closed, and the job is canceled.</span></span>

<span data-ttu-id="67bdc-198">Der folgende Befehl verwendet das New-PSSession-Cmdlet, um eine PSSession zu erstellen, die mit dem Server01-Computer verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="67bdc-198">The following command uses the New-PSSession cmdlet to create a PSSession that is connected to the Server01 computer.</span></span> <span data-ttu-id="67bdc-199">Der Befehl speichert die PSSession in der \$ s-Variablen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-199">The command saves the PSSession in the \$s variable.</span></span>

```powershell
$s = new-pssession -computername Server01
```

<span data-ttu-id="67bdc-200">Der nächste Befehl verwendet das Cmdlet "Invoke-Command", um einen Start-Job Befehl in der PSSession auszuführen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-200">The next command uses the Invoke-Command cmdlet to run a Start-Job command in the PSSession.</span></span> <span data-ttu-id="67bdc-201">Der Start-Job-Befehl und der Get-Eventlog-Befehl werden in geschweifte Klammern eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-201">The Start-Job command and the Get-Eventlog command are enclosed in braces.</span></span>

```powershell
invoke-command -session $s -scriptblock {
  start-job -scriptblock {get-eventlog system}}
```

<span data-ttu-id="67bdc-202">Die Ergebnisse ähneln der folgenden Beispielausgabe.</span><span class="sxs-lookup"><span data-stu-id="67bdc-202">The results resemble the following sample output.</span></span>

```Output
Id       Name    State      HasMoreData     Location   Command
--       ----    -----      -----------     --------   -------
2        Job2    Running    True            Localhost  get-eventlog system
```

<span data-ttu-id="67bdc-203">Wenn Sie einen Start-Job Befehl Remote ausführen, gibt Invoke-Command denselben Typ von Auftrags Objekten zurück, den Start-Job zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="67bdc-203">When you run a Start-Job command remotely, Invoke-Command returns the same type of job object that Start-Job returns.</span></span> <span data-ttu-id="67bdc-204">Sie können das Auftrags Objekt in einer Variablen speichern, oder Sie können einen Get-Job Befehl verwenden, um den Auftrag zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-204">You can save the job object in a variable, or you can use a Get-Job command to get the job.</span></span>

<span data-ttu-id="67bdc-205">Beachten Sie, dass der Wert der Location-Eigenschaft anzeigt, dass der Auftrag auf dem lokalen Computer ausgeführt wurde, der als "localhost" bezeichnet wird, obwohl der Auftrag auf dem Server01-Computer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="67bdc-205">Note that the value of the Location property shows that the job ran on the local computer, known as "LocalHost", even though the job ran on the Server01 computer.</span></span> <span data-ttu-id="67bdc-206">Da das Auftrags Objekt auf dem Computer Server01 erstellt wird und der Auftrag auf dem gleichen Computer ausgeführt wird, wird er als lokaler Hintergrund Auftrag betrachtet.</span><span class="sxs-lookup"><span data-stu-id="67bdc-206">Because the job object is created on the Server01 computer and the job runs on the same computer, it is considered to be a local background job.</span></span>

#### <a name="step-2-invoke-command-get-job"></a><span data-ttu-id="67bdc-207">Schritt 2: Aufrufen des Befehls Get-Job</span><span class="sxs-lookup"><span data-stu-id="67bdc-207">STEP 2: INVOKE-COMMAND GET-JOB</span></span>

<span data-ttu-id="67bdc-208">Verwenden Sie zum Verwalten eines Remote Hintergrund Auftrags die Job-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="67bdc-208">To manage a remote background job, use the Job cmdlets.</span></span> <span data-ttu-id="67bdc-209">Da sich das Auftrags Objekt auf dem Remote Computer befindet, müssen Sie Remote Befehle ausführen, um die Auftrags Ergebnisse abzurufen, zu warten, abzufragen oder abzurufen.</span><span class="sxs-lookup"><span data-stu-id="67bdc-209">Because the job object is on the remote computer, you need to run remote commands to get, stop, wait for, or retrieve the job results.</span></span>

<span data-ttu-id="67bdc-210">Um festzustellen, ob der Auftrag beendet ist, verwenden Sie einen Invoke-Command Befehl, um einen Get-Job Befehl in der PSSession auszuführen, die mit dem Server01-Computer verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="67bdc-210">To see if the job is complete, use an Invoke-Command command to run a Get-Job command in the PSSession that is connected to the Server01 computer.</span></span>

```powershell
invoke-command -session $s -scriptblock {get-job}
```

<span data-ttu-id="67bdc-211">Der Befehl gibt ein Auftragsobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="67bdc-211">The command returns a job object.</span></span> <span data-ttu-id="67bdc-212">Die State-Eigenschaft des Auftrags Objekts zeigt, dass der Befehl erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="67bdc-212">The State property of the job object shows that the command was completed successfully.</span></span>

```Output
SessionId   Name  State      HasMoreData   Location   Command
---------   ----  -----      -----------   --------   -------
2           Job2  Completed  True          LocalHost   get-eventlog system
```

#### <a name="step-3-invoke-command-receive-job"></a><span data-ttu-id="67bdc-213">Schritt 3: Aufrufen des Befehls Receive-Job</span><span class="sxs-lookup"><span data-stu-id="67bdc-213">STEP 3: INVOKE-COMMAND RECEIVE-JOB</span></span>

<span data-ttu-id="67bdc-214">Um die Ergebnisse des Auftrags abzurufen, verwenden Sie das Cmdlet "Invoke-Command", um einen Receive-Job-Befehl in der PSSession auszuführen, die mit dem Server01-Computer verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="67bdc-214">To get the results of the job, use the Invoke-Command cmdlet to run a Receive-Job command in the PSSession that is connected to the Server01 computer.</span></span>

<span data-ttu-id="67bdc-215">Der folgende Befehl verwendet das Cmdlet "Receive-Job", um die Ergebnisse des Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-215">The following command uses the Receive-Job cmdlet to get the results of the job.</span></span> <span data-ttu-id="67bdc-216">Die Sitzungs-ID wird verwendet, um den Auftrag zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="67bdc-216">It uses the session ID to identify the job.</span></span> <span data-ttu-id="67bdc-217">Mit diesem Befehl werden die Auftrags Ergebnisse in der \$ Ergebnis Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="67bdc-217">This command saves the job results in the \$results variable.</span></span> <span data-ttu-id="67bdc-218">Er verwendet den Keep-Parameter von Receive-Job, um das Ergebnis im Auftrags Cache auf dem Remote Computer beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-218">It uses the Keep parameter of Receive-Job to keep the result in the job cache on the remote computer.</span></span>

```powershell
$results = invoke-command -session $s -scriptblock {
  receive-job -sessionid 2 -keep}
```

<span data-ttu-id="67bdc-219">Sie können die Ergebnisse auch in eine Datei auf dem lokalen Computer oder auf einem Remote Computer umleiten.</span><span class="sxs-lookup"><span data-stu-id="67bdc-219">You can also redirect the results to a file on the local or remote computer.</span></span>
<span data-ttu-id="67bdc-220">Der folgende Befehl verwendet einen Umleitungs Operator, um die Ergebnisse in einer Datei auf dem Server01-Computer zu speichern.</span><span class="sxs-lookup"><span data-stu-id="67bdc-220">The following command uses a redirection operator to save the results in a file on the Server01 computer.</span></span>

```powershell
invoke-command -session $s -command {
  receive-job -sessionid 2 > c:\logs\pslog.txt}
```

## <a name="see-also"></a><span data-ttu-id="67bdc-221">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="67bdc-221">SEE ALSO</span></span>

[<span data-ttu-id="67bdc-222">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="67bdc-222">about_Jobs</span></span>](about_Jobs.md)

[<span data-ttu-id="67bdc-223">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="67bdc-223">about_Job_Details</span></span>](about_Job_Details.md)

[<span data-ttu-id="67bdc-224">about_Remote</span><span class="sxs-lookup"><span data-stu-id="67bdc-224">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="67bdc-225">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="67bdc-225">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="67bdc-226">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="67bdc-226">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="67bdc-227">Start-Job</span><span class="sxs-lookup"><span data-stu-id="67bdc-227">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)

[<span data-ttu-id="67bdc-228">Get-Job</span><span class="sxs-lookup"><span data-stu-id="67bdc-228">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)

[<span data-ttu-id="67bdc-229">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="67bdc-229">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)

[<span data-ttu-id="67bdc-230">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="67bdc-230">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)

[<span data-ttu-id="67bdc-231">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="67bdc-231">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)

[<span data-ttu-id="67bdc-232">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="67bdc-232">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="67bdc-233">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="67bdc-233">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="67bdc-234">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="67bdc-234">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)

