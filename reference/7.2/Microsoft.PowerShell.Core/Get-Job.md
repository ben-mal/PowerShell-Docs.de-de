---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 7df3375d547b696d67c44462142d592e6047ac63
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597581"
---
# <span data-ttu-id="23e21-102">Get-Job</span><span class="sxs-lookup"><span data-stu-id="23e21-102">Get-Job</span></span>

## <span data-ttu-id="23e21-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="23e21-103">SYNOPSIS</span></span>
<span data-ttu-id="23e21-104">Ruft PowerShell-Hintergrund Aufträge ab, die in der aktuellen Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="23e21-104">Gets PowerShell background jobs that are running in the current session.</span></span>

## <span data-ttu-id="23e21-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="23e21-105">SYNTAX</span></span>

### <span data-ttu-id="23e21-106">Sessionidparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="23e21-106">SessionIdParameterSet (Default)</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="23e21-107">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="23e21-107">InstanceIdParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="23e21-108">Nameparameterset</span><span class="sxs-lookup"><span data-stu-id="23e21-108">NameParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="23e21-109">Stateparameterset</span><span class="sxs-lookup"><span data-stu-id="23e21-109">StateParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="23e21-110">Commandparameterset</span><span class="sxs-lookup"><span data-stu-id="23e21-110">CommandParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="23e21-111">Filterparameterset</span><span class="sxs-lookup"><span data-stu-id="23e21-111">FilterParameterSet</span></span>

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="23e21-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="23e21-112">DESCRIPTION</span></span>

<span data-ttu-id="23e21-113">Das- `Get-Job` Cmdlet ruft Objekte ab, die die Hintergrund Aufträge darstellen, die in der aktuellen Sitzung gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="23e21-113">The `Get-Job` cmdlet gets objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="23e21-114">Sie können verwenden, `Get-Job` um Aufträge zu erhalten, die mithilfe des `Start-Job` Cmdlets gestartet wurden, oder indem Sie den **AsJob** -Parameter eines beliebigen Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="23e21-114">You can use `Get-Job` to get jobs that were started by using the `Start-Job` cmdlet, or by using the **AsJob** parameter of any cmdlet.</span></span>

<span data-ttu-id="23e21-115">Ohne Parameter ruft ein `Get-Job` Befehl alle Aufträge in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="23e21-115">Without parameters, a `Get-Job` command gets all jobs in the current session.</span></span> <span data-ttu-id="23e21-116">Sie können die Parameter von verwenden `Get-Job` , um bestimmte Aufträge zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="23e21-116">You can use the parameters of `Get-Job` to get particular jobs.</span></span>

<span data-ttu-id="23e21-117">Das zurückgegebene Auftrags Objekt `Get-Job` enthält nützliche Informationen zum Auftrag, aber keine Auftrags Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="23e21-117">The job object that `Get-Job` returns contains useful information about the job, but it does not contain the job results.</span></span> <span data-ttu-id="23e21-118">Verwenden Sie das-Cmdlet, um die Ergebnisse zu erhalten `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="23e21-118">To get the results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="23e21-119">Ein Windows PowerShell-Hintergrund Auftrag ist ein Befehl, der im Hintergrund ausgeführt wird, ohne mit der aktuellen Sitzung zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="23e21-119">A Windows PowerShell background job is a command that runs in the background without interacting with the current session.</span></span> <span data-ttu-id="23e21-120">In der Regel verwenden Sie einen Hintergrund Auftrag, um einen komplexen Befehl auszuführen, der lange Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="23e21-120">Typically, you use a background job to run a complex command that takes a long time to finish.</span></span> <span data-ttu-id="23e21-121">Weitere Informationen zu Hintergrundaufträgen in Windows PowerShell finden Sie unter [about_Jobs](./about/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="23e21-121">For more information about background jobs in Windows PowerShell, see [about_Jobs](./about/about_Jobs.md).</span></span>

<span data-ttu-id="23e21-122">Ab Windows PowerShell 3,0 `Get-Job` Ruft das Cmdlet auch benutzerdefinierte Auftrags Typen ab, wie z. b. Workflow Aufträge und Instanzen von geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="23e21-122">Beginning in Windows PowerShell 3.0, the `Get-Job` cmdlet also gets custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="23e21-123">Zum Ermitteln des Auftragstyps eines Auftrags verwenden Sie die **PSJobTypeName**-Eigenschaft des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="23e21-123">To find the job type of a job, use the **PSJobTypeName** property of the job.</span></span>

<span data-ttu-id="23e21-124">`Get-Job`Wenn Sie aktivieren möchten, um einen benutzerdefinierten Auftragstyp zu erhalten, importieren Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, in die Sitzung, bevor Sie einen `Get-Job` Befehl ausführen, entweder mithilfe des- `Import-Module` Cmdlets oder mithilfe des-Cmdlets oder mithilfe des-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="23e21-124">To enable `Get-Job` to get a custom job type, import the module that supports the custom job type into the session before you run a `Get-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="23e21-125">Informationen zu einem bestimmten benutzerdefinierten Auftragstyp finden Sie in der Dokumentation der Funktion „Benutzerdefinierte Auftragstypen“.</span><span class="sxs-lookup"><span data-stu-id="23e21-125">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="23e21-126">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="23e21-126">EXAMPLES</span></span>

### <span data-ttu-id="23e21-127">Beispiel 1: alle Hintergrund Aufträge, die in der aktuellen Sitzung gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="23e21-127">Example 1: Get all background jobs started in the current session</span></span>

<span data-ttu-id="23e21-128">Dieser Befehl ruft alle Hintergrundaufträge ab, die in der aktuellen Sitzung gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="23e21-128">This command gets all background jobs started in the current session.</span></span> <span data-ttu-id="23e21-129">In anderen Sitzungen erstellte Aufträge sind nicht enthalten, auch wenn die Aufträge auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="23e21-129">It does not include jobs created in other sessions, even if the jobs run on the local computer.</span></span>

```
PS C:\> Get-Job
```

### <span data-ttu-id="23e21-130">Beispiel 2: Beenden eines Auftrags mit einer Instanz-ID</span><span class="sxs-lookup"><span data-stu-id="23e21-130">Example 2: Stop a job by using an instance ID</span></span>

<span data-ttu-id="23e21-131">Diese Befehle zeigen, wie die Instanz-ID eines Auftrags abgerufen und dann zum Beenden eines Auftrags verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="23e21-131">These commands show how to get the instance ID of a job and then use it to stop a job.</span></span> <span data-ttu-id="23e21-132">Im Gegensatz zum Namen eines Auftrags, der nicht eindeutig ist, ist die Instanz-ID eindeutig.</span><span class="sxs-lookup"><span data-stu-id="23e21-132">Unlike the name of a job, which is not unique, the instance ID is unique.</span></span>

<span data-ttu-id="23e21-133">Der erste Befehl verwendet das `Get-Job` Cmdlet, um einen Auftrag zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="23e21-133">The first command uses the `Get-Job` cmdlet to get a job.</span></span> <span data-ttu-id="23e21-134">Er verwendet den **Name** -Parameter, um den Auftrag zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="23e21-134">It uses the **Name** parameter to identify the job.</span></span> <span data-ttu-id="23e21-135">Der Befehl speichert das Auftrags Objekt, das `Get-Job` in der `$j` Variablen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="23e21-135">The command stores the job object that `Get-Job` returns in the `$j` variable.</span></span> <span data-ttu-id="23e21-136">In diesem Beispiel ist nur ein Auftrag mit dem angegebenen Namen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="23e21-136">In this example, there is only one job with the specified name.</span></span> <span data-ttu-id="23e21-137">Mit dem zweiten Befehl wird die **InstanceId-** Eigenschaft des Objekts in der `$j` Variablen abgerufen und in der `$ID` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="23e21-137">The second command gets the **InstanceId** property of the object in the `$j` variable and stores it in the `$ID` variable.</span></span> <span data-ttu-id="23e21-138">Der dritte Befehl zeigt den Wert der `$ID` Variablen an.</span><span class="sxs-lookup"><span data-stu-id="23e21-138">The third command displays the value of the `$ID` variable.</span></span> <span data-ttu-id="23e21-139">Der vierte Befehl verwendet das `Stop-Job` Cmdlet, um den Auftrag zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="23e21-139">The fourth command uses `Stop-Job` cmdlet to stop the job.</span></span>
<span data-ttu-id="23e21-140">Er verwendet den **InstanceId-** Parameter, um den Auftrag und die `$ID` Variable zu identifizieren, um die Instanz-ID des Auftrags darzustellen.</span><span class="sxs-lookup"><span data-stu-id="23e21-140">It uses the **InstanceId** parameter to identify the job and `$ID` variable to represent the instance ID of the job.</span></span>

```
PS C:\> $j = Get-Job -Name Job1
PS C:\> $ID = $j.InstanceID
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

PS C:\> Stop-Job -InstanceId $ID
```

### <span data-ttu-id="23e21-141">Beispiel 3: Get-Aufträge, die einen bestimmten Befehl enthalten</span><span class="sxs-lookup"><span data-stu-id="23e21-141">Example 3: Get jobs that include a specific command</span></span>

<span data-ttu-id="23e21-142">Dieser Befehl ruft die Aufträge im System ab, die einen `Get-Process` Befehl enthalten.</span><span class="sxs-lookup"><span data-stu-id="23e21-142">This command gets the jobs on the system that include a `Get-Process` command.</span></span> <span data-ttu-id="23e21-143">Der Befehl verwendet den **Command** -Parameter von `Get-Job` , um die abgerufenen Aufträge einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="23e21-143">The command uses the **Command** parameter of `Get-Job` to limit the jobs retrieved.</span></span> <span data-ttu-id="23e21-144">Der Befehl verwendet Platzhalter Zeichen ( `*` ) zum Aufrufen von Aufträgen, die einen `Get-Process` Befehl an beliebiger Stelle in der Befehls Zeichenfolge enthalten.</span><span class="sxs-lookup"><span data-stu-id="23e21-144">The command uses wildcard characters (`*`) to get jobs that include a `Get-Process` command anywhere in the command string.</span></span>

```
PS C:\> Get-Job -Command "*get-process*"
```

### <span data-ttu-id="23e21-145">Beispiel 4: Get-Aufträge, die einen bestimmten Befehl enthalten, mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="23e21-145">Example 4: Get jobs that include a specific command by using the pipeline</span></span>

<span data-ttu-id="23e21-146">Wie der Befehl im vorherigen Beispiel ruft dieser Befehl die Aufträge im System ab, die einen Befehl enthalten `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="23e21-146">Like the command in the previous example, this command gets the jobs on the system that include a `Get-Process` command.</span></span> <span data-ttu-id="23e21-147">Der Befehl verwendet einen Pipeline Operator ( `|` ), um eine Zeichenfolge in Anführungszeichen an das `Get-Job` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="23e21-147">The command uses a pipeline operator (`|`) to send a string, in quotation marks, to the `Get-Job` cmdlet.</span></span> <span data-ttu-id="23e21-148">Dies entspricht dem vorherigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="23e21-148">It is the equivalent of the previous command.</span></span>

```
PS C:\> "*get-process*" | Get-Job
```

### <span data-ttu-id="23e21-149">Beispiel 5: Aufträge, die noch nicht gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="23e21-149">Example 5: Get jobs that have not been started</span></span>

<span data-ttu-id="23e21-150">Mit diesem Befehl werden nur die Aufträge abgerufen, die erstellt, aber noch nicht gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="23e21-150">This command gets only those jobs that have been created but have not yet been started.</span></span> <span data-ttu-id="23e21-151">Dazu gehören Aufträge, deren Ausführung für einen Zeitpunkt in der Zukunft geplant ist, und solche, die noch nicht geplant wurden.</span><span class="sxs-lookup"><span data-stu-id="23e21-151">This includes jobs that are scheduled to run in the future and those not yet scheduled.</span></span>

```
PS C:\> Get-Job -State NotStarted
```

### <span data-ttu-id="23e21-152">Beispiel 6: Aufträge erhalten, denen kein Name zugewiesen wurde</span><span class="sxs-lookup"><span data-stu-id="23e21-152">Example 6: Get jobs that have not been assigned a name</span></span>

<span data-ttu-id="23e21-153">Dieser Befehl ruft alle Aufträge ab, deren Auftrags Name mit "Job" beginnt.</span><span class="sxs-lookup"><span data-stu-id="23e21-153">This command gets all jobs that have job names that begin with job.</span></span> <span data-ttu-id="23e21-154">Da `job<number>` der Standardname für einen Auftrag ist, ruft dieser Befehl alle Aufträge ab, denen kein explizit zugewiesener Name zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="23e21-154">Because `job<number>` is the default name for a job, this command gets all jobs that do not have an explicitly assigned name.</span></span>

```
PS C:\> Get-Job -Name Job*
```

### <span data-ttu-id="23e21-155">Beispiel 7: Verwenden eines Auftrags Objekts zur Darstellung des Auftrags in einem Befehl</span><span class="sxs-lookup"><span data-stu-id="23e21-155">Example 7: Use a job object to represent the job in a command</span></span>

<span data-ttu-id="23e21-156">In diesem Beispiel wird gezeigt, wie verwendet `Get-Job` wird, um ein Auftrags Objekt zu erhalten, und anschließend wird gezeigt, wie das Auftrags Objekt verwendet wird, um den Auftrag in einem Befehl darzustellen.</span><span class="sxs-lookup"><span data-stu-id="23e21-156">This example shows how to use `Get-Job` to get a job object, and then it shows how to use the job object to represent the job in a command.</span></span>

<span data-ttu-id="23e21-157">Der erste Befehl verwendet das `Start-Job` Cmdlet, um einen Hintergrund Auftrag zu starten, der einen `Get-Process` Befehl auf dem lokalen Computer ausführt.</span><span class="sxs-lookup"><span data-stu-id="23e21-157">The first command uses the `Start-Job` cmdlet to start a background job that runs a `Get-Process` command on the local computer.</span></span> <span data-ttu-id="23e21-158">Der Befehl verwendet den **Name** -Parameter von `Start-Job` , um dem Auftrag einen anzeigen Amen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="23e21-158">The command uses the **Name** parameter of `Start-Job` to assign a friendly name to the job.</span></span> <span data-ttu-id="23e21-159">Der zweite Befehl verwendet `Get-Job` , um den Auftrag zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="23e21-159">The second command uses `Get-Job` to get the job.</span></span> <span data-ttu-id="23e21-160">Er verwendet den **Name** -Parameter von `Get-Job` , um den Auftrag zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="23e21-160">It uses the **Name** parameter of `Get-Job` to identify the job.</span></span> <span data-ttu-id="23e21-161">Der Befehl speichert das resultierende Auftrags Objekt in der `$j` Variablen.</span><span class="sxs-lookup"><span data-stu-id="23e21-161">The command saves the resulting job object in the `$j` variable.</span></span> <span data-ttu-id="23e21-162">Der dritte Befehl zeigt den Wert des Auftrags Objekts in der `$j` Variablen an.</span><span class="sxs-lookup"><span data-stu-id="23e21-162">The third command displays the value of the job object in the `$j` variable.</span></span> <span data-ttu-id="23e21-163">Der Wert der **State** -Eigenschaft zeigt an, dass der Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="23e21-163">The value of the **State** property shows that the job is completed.</span></span> <span data-ttu-id="23e21-164">Der Wert der **HasMoreData**-Eigenschaft zeigt, dass Ergebnisse des Auftrags verfügbar sind, die noch nicht abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="23e21-164">The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.</span></span> <span data-ttu-id="23e21-165">Der vierte Befehl verwendet das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="23e21-165">The fourth command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="23e21-166">Er verwendet das Auftrags Objekt in der `$j` Variablen, um den Auftrag darzustellen.</span><span class="sxs-lookup"><span data-stu-id="23e21-166">It uses the job object in the `$j` variable to represent the job.</span></span> <span data-ttu-id="23e21-167">Sie können auch einen Pipeline Operator verwenden, um ein Auftrags Objekt an zu senden `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="23e21-167">You can also use a pipeline operator to send a job object to `Receive-Job`.</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob
PS C:\> $j = Get-Job -Name MyJob
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```


### <span data-ttu-id="23e21-168">Beispiel 8: alle Aufträge einschließlich der von einer anderen Methode gestarteten Aufträge</span><span class="sxs-lookup"><span data-stu-id="23e21-168">Example 8: Get all jobs including jobs started by a different method</span></span>

<span data-ttu-id="23e21-169">In diesem Beispiel wird veranschaulicht, dass mit dem `Get-Job` Cmdlet alle Aufträge, die in der aktuellen Sitzung gestartet wurden, angezeigt werden können. Dies ist auch dann der Fall, wenn Sie mithilfe verschiedener Methoden gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="23e21-169">This example demonstrates that the `Get-Job` cmdlet can get all of the jobs that were started in the current session, even if they were started by using different methods.</span></span>

<span data-ttu-id="23e21-170">Der erste Befehl verwendet das `Start-Job` Cmdlet, um einen Auftrag auf dem lokalen Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="23e21-170">The first command uses the `Start-Job` cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="23e21-171">Der zweite Befehl verwendet den **AsJob** -Parameter des `Invoke-Command` Cmdlets, um einen Auftrag auf dem S1-Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="23e21-171">The second command uses the **AsJob** parameter of the `Invoke-Command` cmdlet to start a job on the S1 computer.</span></span> <span data-ttu-id="23e21-172">Obwohl die Befehle im Auftrag auf dem Remotecomputer ausgeführt werden, wird das Auftragsobjekt auf dem lokalen Computer erstellt; daher verwenden Sie lokale Befehle zum Verwalten des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="23e21-172">Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.</span></span> <span data-ttu-id="23e21-173">Der dritte Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines `Start-Job` Befehls auf dem Computer S2.</span><span class="sxs-lookup"><span data-stu-id="23e21-173">The third command uses the `Invoke-Command` cmdlet to run a `Start-Job` command on the S2 computer.</span></span> <span data-ttu-id="23e21-174">Wenn diese Methode verwendet wird, wird das Auftrags Objekt auf dem Remote Computer erstellt, sodass Sie Remote Befehle verwenden, um den Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="23e21-174">By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.</span></span> <span data-ttu-id="23e21-175">Der vierte Befehl verwendet `Get-Job` , um die auf dem lokalen Computer gespeicherten Aufträge zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="23e21-175">The fourth command uses `Get-Job` to get the jobs stored on the local computer.</span></span> <span data-ttu-id="23e21-176">Die **psjobtypame** -Eigenschaft von Aufträgen, die in Windows PowerShell 3,0 eingeführt wurde, zeigt, dass der lokale Auftrag, der mithilfe des `Start-Job` Cmdlets gestartet wurde, ein Hintergrund Auftrag ist und der Auftrag, der in einer Remote Sitzung mithilfe des `Invoke-Command` Cmdlets gestartet wurde, ein Remote Auftrag ist.</span><span class="sxs-lookup"><span data-stu-id="23e21-176">The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the `Start-Job` cmdlet is a background job and the job started in a remote session by using the `Invoke-Command` cmdlet is a remote job.</span></span> <span data-ttu-id="23e21-177">Der fünfte Befehl verwendet `Invoke-Command` , um `Get-Job` auf dem Computer S2 einen Befehl auszuführen. Die Beispielausgabe zeigt die Ergebnisse des `Get-Job` Befehls an.</span><span class="sxs-lookup"><span data-stu-id="23e21-177">The fifth command uses `Invoke-Command` to run a `Get-Job` command on the S2 computer.The sample output shows the results of the `Get-Job` command.</span></span> <span data-ttu-id="23e21-178">Auf dem Computer S2 scheint der Auftrag ein lokaler Auftrag zu sein.</span><span class="sxs-lookup"><span data-stu-id="23e21-178">On the S2 computer, the job appears to be a local job.</span></span> <span data-ttu-id="23e21-179">Der Computername ist "localhost", und der Auftragstyp ist ein Hintergrund Auftrag. Weitere Informationen zum Ausführen von Hintergrund Aufträgen auf Remote Computern finden Sie unter [about_Remote_Jobs](./about/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="23e21-179">The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see [about_Remote_Jobs](./about/about_Remote_Jobs.md).</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

### <span data-ttu-id="23e21-180">Beispiel 9: Untersuchen eines fehlgeschlagenen Auftrags</span><span class="sxs-lookup"><span data-stu-id="23e21-180">Example 9: Investigate a failed job</span></span>

<span data-ttu-id="23e21-181">Dieser Befehl zeigt, wie das zurückgegebene Auftrags Objekt verwendet wird `Get-Job` , um zu untersuchen, warum ein Auftrag fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="23e21-181">This command shows how to use the job object that `Get-Job` returns to investigate why a job failed.</span></span>
<span data-ttu-id="23e21-182">Weiterhin wird gezeigt, wie die untergeordneten Aufträge der einzelnen Aufträge abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="23e21-182">It also shows how to get the child jobs of each job.</span></span>

<span data-ttu-id="23e21-183">Der erste Befehl verwendet das `Start-Job` Cmdlet, um einen Auftrag auf dem lokalen Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="23e21-183">The first command uses the `Start-Job` cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="23e21-184">Das zurückgegebene Auftrags Objekt `Start-Job` zeigt, dass der Auftrag fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="23e21-184">The job object that `Start-Job` returns shows that the job failed.</span></span> <span data-ttu-id="23e21-185">Der Wert der **State** -Eigenschaft ist fehlerhaft.</span><span class="sxs-lookup"><span data-stu-id="23e21-185">The value of the **State** property is Failed.</span></span>

<span data-ttu-id="23e21-186">Der zweite Befehl verwendet das `Get-Job` Cmdlet, um den Auftrag zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="23e21-186">The second command uses the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="23e21-187">Der Befehl verwendet die Punktmethode, um den Wert der **JobStateInfo**-Eigenschaft des Objekts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="23e21-187">The command uses the dot method to get the value of the **JobStateInfo** property of the object.</span></span> <span data-ttu-id="23e21-188">Er verwendet einen Pipeline-Operator, um das Objekt in der **jobstatueinfo** -Eigenschaft an das `Format-List` Cmdlet zu senden, das alle Eigenschaften des Objekts ( `*` ) in einer Liste formatiert. Das Ergebnis des- `Format-List` Befehls zeigt, dass der Wert der **reason** -Eigenschaft des Auftrags leer ist.</span><span class="sxs-lookup"><span data-stu-id="23e21-188">It uses a pipeline operator to send the object in the **JobStateInfo** property to the `Format-List` cmdlet, which formats all of the properties of the object (`*`) in a list.The result of the `Format-List` command shows that the value of the **Reason** property of the job is blank.</span></span>

<span data-ttu-id="23e21-189">Mit dem dritten Befehl werden weitere Informationen untersucht.</span><span class="sxs-lookup"><span data-stu-id="23e21-189">The third command investigates more.</span></span> <span data-ttu-id="23e21-190">Er verwendet einen `Get-Job` Befehl, um den Auftrag zu erhalten, und verwendet dann einen Pipeline Operator, um das gesamte Auftrags Objekt an das `Format-List` Cmdlet zu senden, das alle Eigenschaften des Auftrags in einer Liste anzeigt. Die Anzeige aller Eigenschaften im Auftrags Objekt zeigt, dass der Auftrag einen untergeordneten Auftrag mit dem Namen Job2 enthält.</span><span class="sxs-lookup"><span data-stu-id="23e21-190">It uses a `Get-Job` command to get the job and then uses a pipeline operator to send the whole job object to the `Format-List` cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.</span></span>

<span data-ttu-id="23e21-191">Der vierte Befehl verwendet `Get-Job` , um das Auftrags Objekt, das den untergeordneten Job2-Auftrag darstellt, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="23e21-191">The fourth command uses `Get-Job` to get the job object that represents the Job2 child job.</span></span> <span data-ttu-id="23e21-192">Dies ist der Auftrag, in dem der Befehl tatsächlich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="23e21-192">This is the job in which the command actually ran.</span></span> <span data-ttu-id="23e21-193">Er verwendet die Punkt-Methode, um die **reason** -Eigenschaft der **Jobstatus Info** -Eigenschaft zu erhalten. Das Ergebnis zeigt, dass der Auftrag aufgrund eines Zugriffs Verweigerungs Fehlers fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="23e21-193">It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error.</span></span> <span data-ttu-id="23e21-194">In diesem Fall hat der Benutzer vergessen, beim Starten von Windows PowerShell die Option als Administrator ausführen zu verwenden. da Hintergrund Aufträge die Remotingfeatures von Windows PowerShell verwenden, muss der Computer für Remoting konfiguriert werden, um einen Auftrag auszuführen, auch wenn der Auftrag auf dem lokalen Computer ausgeführt wird. Informationen zu den Anforderungen für Remoting in Windows PowerShell finden Sie unter [about_Remote_Requirements](./about/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23e21-194">In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see [about_Remote_Requirements](./about/about_Remote_Requirements.md).</span></span> <span data-ttu-id="23e21-195">Tipps zur Problembehandlung finden Sie unter [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="23e21-195">For troubleshooting tips, see [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md).</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

PS C:\> Get-Job | Format-List -Property *
HasMoreData   : False
StatusMessage :
Location      : localhost
Command       : get-process
JobStateInfo  : Failed
Finished      : System.Threading.ManualReset
EventInstanceId    : fb792295-1318-4f5d-8ac8-8a89c5261507
Id            : 1
Name          : Job1
ChildJobs     : {Job2}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :

PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the
following error message: Access is denied.
```

### <span data-ttu-id="23e21-196">Beispiel 10: Filtern von gefilterten Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="23e21-196">Example 10: Get filtered results</span></span>

<span data-ttu-id="23e21-197">Dieses Beispiel zeigt, wie Sie den **Filter**-Parameter zum Abrufen eines Workflowauftrags verwenden.</span><span class="sxs-lookup"><span data-stu-id="23e21-197">This example shows how to use the **Filter** parameter to get a workflow job.</span></span> <span data-ttu-id="23e21-198">Der in Windows PowerShell 3.0 eingeführte **Filter**-Parameter ist nur für benutzerdefinierte Auftragstypen gültig, wie z. B. Workflowaufträge und geplante Aufträge.</span><span class="sxs-lookup"><span data-stu-id="23e21-198">The **Filter** parameter, introduced in Windows PowerShell 3.0 is valid only on custom job types, such as workflow jobs and scheduled jobs.</span></span>

<span data-ttu-id="23e21-199">Der erste Befehl verwendet das **Workflow** Schlüsselwort, um den WfProcess-Workflow zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23e21-199">The first command uses the **Workflow** keyword to create the WFProcess workflow.</span></span> <span data-ttu-id="23e21-200">Der zweite Befehl verwendet den **AsJob** -Parameter des WfProcess-Workflows, um den Workflow als Hintergrund Auftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="23e21-200">The second command uses the **AsJob** parameter of the WFProcess workflow to run the workflow as a background job.</span></span> <span data-ttu-id="23e21-201">Mithilfe des **JobName**-Parameters des Workflows wird ein Name für den Auftrag angegeben und mithilfe des **PSPrivateMetadata**-Parameters des Workflows eine benutzerdefinierte ID.</span><span class="sxs-lookup"><span data-stu-id="23e21-201">It uses the **JobName** parameter of the workflow to specify a name for the job, and the **PSPrivateMetadata** parameter of the workflow to specify a custom ID.</span></span> <span data-ttu-id="23e21-202">Der dritte Befehl verwendet den **Filter** -Parameter von `Get-Job` , um den Auftrag anhand der benutzerdefinierten ID zu erhalten, die im **psprivatemetadata** -Parameter angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="23e21-202">The third command uses the **Filter** parameter of `Get-Job` to get the job by custom ID that was specified in the **PSPrivateMetadata** parameter.</span></span>

```
PS C:\> Workflow WFProcess {Get-Process}
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

### <span data-ttu-id="23e21-203">Beispiel 11: erhalten von Informationen zu untergeordneten Aufträgen</span><span class="sxs-lookup"><span data-stu-id="23e21-203">Example 11: Get information about child jobs</span></span>

<span data-ttu-id="23e21-204">Dieses Beispiel zeigt die Auswirkung der Verwendung der Parameter **includechildjob** und **childjobstate** des `Get-Job` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="23e21-204">This example shows the effect of using the **IncludeChildJob** and **ChildJobState** parameters of the `Get-Job` cmdlet.</span></span>

<span data-ttu-id="23e21-205">Der erste Befehl ruft die Aufträge in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="23e21-205">The first command gets the jobs in the current session.</span></span> <span data-ttu-id="23e21-206">Die Ausgabe umfasst einen Hintergrundauftrag, einen Remoteauftrag und mehrere Instanzen eines geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="23e21-206">The output includes a background job, a remote job and several instances of a scheduled job.</span></span> <span data-ttu-id="23e21-207">Bei der Ausführung des Remoteauftrags (Job4) scheint ein Fehler aufgetreten zu sein.</span><span class="sxs-lookup"><span data-stu-id="23e21-207">The remote job, Job4, appears to have failed.</span></span>
<span data-ttu-id="23e21-208">Der zweite Befehl verwendet den **incluentchildjob** -Parameter von `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="23e21-208">The second command uses the **IncludeChildJob** parameter of `Get-Job`.</span></span> <span data-ttu-id="23e21-209">In der Ausgabe werden die untergeordneten Aufträge aller Aufträge hinzugefügt, die über untergeordnete Aufträge verfügen. In diesem Fall zeigt die überarbeitete Ausgabe an, dass nur der untergeordnete Job5-Auftrag von Job4 fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="23e21-209">The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.</span></span> <span data-ttu-id="23e21-210">Der dritte Befehl verwendet den **childjobstate** -Parameter mit dem Wert failed. die Ausgabe enthält alle übergeordneten Aufträge und nur die untergeordneten Aufträge, die fehlgeschlagen sind.</span><span class="sxs-lookup"><span data-stu-id="23e21-210">The third command uses the **ChildJobState** parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.</span></span> <span data-ttu-id="23e21-211">Der fünfte Befehl verwendet die **jobstateinfo** -Eigenschaft von Aufträgen und seine **reason** -Eigenschaft, um zu ermitteln, warum Job5 fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="23e21-211">The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.</span></span>

```
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

PS C:\> Get-Job -IncludeChildJob
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
3      Job3                            Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
6      Job6                            Completed     True            Server02            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

PS C:\> Get-Job -Name Job4 -ChildJobState Failed
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
```

<span data-ttu-id="23e21-212">Weitere Informationen finden Sie im [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) Hilfethema.</span><span class="sxs-lookup"><span data-stu-id="23e21-212">For more information, see the [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) Help topic.</span></span>

## <span data-ttu-id="23e21-213">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="23e21-213">PARAMETERS</span></span>

### <span data-ttu-id="23e21-214">Nach</span><span class="sxs-lookup"><span data-stu-id="23e21-214">-After</span></span>

<span data-ttu-id="23e21-215">Ruft abgeschlossene Aufträge ab, die nach dem angegebenen Datum und der angegebenen Uhrzeit beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="23e21-215">Gets completed jobs that ended after the specified date and time.</span></span> <span data-ttu-id="23e21-216">Geben Sie ein **DateTime** -Objekt ein, z. b. ein vom `Get-Date` Cmdlet zurück gegebenes oder eine Zeichenfolge, die in ein **DateTime** -Objekt konvertiert werden kann, z `Dec 1, 2012 2:00 AM` . b `11/06` . oder.</span><span class="sxs-lookup"><span data-stu-id="23e21-216">Enter a **DateTime** object, such as one returned by the `Get-Date` cmdlet or a string that can be converted to a **DateTime** object, such as `Dec 1, 2012 2:00 AM` or `11/06`.</span></span>

<span data-ttu-id="23e21-217">Dieser Parameter kann nur für benutzerdefinierte Auftragstypen wie z. B. Workflowaufträge und geplante Aufträge verwendet werden, die über eine **EndTime**-Eigenschaft verfügen.</span><span class="sxs-lookup"><span data-stu-id="23e21-217">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="23e21-218">Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des `Start-Job` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="23e21-218">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="23e21-219">Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="23e21-219">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="23e21-220">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="23e21-220">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23e21-221">-Vor</span><span class="sxs-lookup"><span data-stu-id="23e21-221">-Before</span></span>

<span data-ttu-id="23e21-222">Ruft abgeschlossene Aufträge ab, die vor dem angegebenen Datum und der angegebenen Uhrzeit beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="23e21-222">Gets completed jobs that ended before the specified date and time.</span></span> <span data-ttu-id="23e21-223">Geben Sie ein **DateTime** -Objekt ein.</span><span class="sxs-lookup"><span data-stu-id="23e21-223">Enter a **DateTime** object.</span></span>

<span data-ttu-id="23e21-224">Dieser Parameter kann nur für benutzerdefinierte Auftragstypen wie z. B. Workflowaufträge und geplante Aufträge verwendet werden, die über eine **EndTime**-Eigenschaft verfügen.</span><span class="sxs-lookup"><span data-stu-id="23e21-224">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="23e21-225">Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des `Start-Job` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="23e21-225">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="23e21-226">Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="23e21-226">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="23e21-227">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="23e21-227">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23e21-228">-Childjobstate</span><span class="sxs-lookup"><span data-stu-id="23e21-228">-ChildJobState</span></span>

<span data-ttu-id="23e21-229">Ruft nur die untergeordneten Aufträge ab, die den angegebenen Status aufweisen.</span><span class="sxs-lookup"><span data-stu-id="23e21-229">Gets only the child jobs that have the specified state.</span></span> <span data-ttu-id="23e21-230">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="23e21-230">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="23e21-231">NotStarted</span><span class="sxs-lookup"><span data-stu-id="23e21-231">NotStarted</span></span>
- <span data-ttu-id="23e21-232">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="23e21-232">Running</span></span>
- <span data-ttu-id="23e21-233">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="23e21-233">Completed</span></span>
- <span data-ttu-id="23e21-234">Fehler</span><span class="sxs-lookup"><span data-stu-id="23e21-234">Failed</span></span>
- <span data-ttu-id="23e21-235">Beendet</span><span class="sxs-lookup"><span data-stu-id="23e21-235">Stopped</span></span>
- <span data-ttu-id="23e21-236">Gesperrt</span><span class="sxs-lookup"><span data-stu-id="23e21-236">Blocked</span></span>
- <span data-ttu-id="23e21-237">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="23e21-237">Suspended</span></span>
- <span data-ttu-id="23e21-238">Getrennt</span><span class="sxs-lookup"><span data-stu-id="23e21-238">Disconnected</span></span>
- <span data-ttu-id="23e21-239">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="23e21-239">Suspending</span></span>
- <span data-ttu-id="23e21-240">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="23e21-240">Stopping</span></span>

<span data-ttu-id="23e21-241">Standardmäßig werden von keine untergeordneten `Get-Job` Aufträge erhalten.</span><span class="sxs-lookup"><span data-stu-id="23e21-241">By default, `Get-Job` does not get child jobs.</span></span> <span data-ttu-id="23e21-242">Wenn Sie den **incluentchildjob** -Parameter verwenden, werden alle untergeordneten `Get-Job` Aufträge abgerufen.</span><span class="sxs-lookup"><span data-stu-id="23e21-242">By using the **IncludeChildJob** parameter, `Get-Job` gets all child jobs.</span></span> <span data-ttu-id="23e21-243">Bei Verwendung des **ChildJobState**-Parameters hat der **IncludeChildJob**-Parameter keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="23e21-243">If you use the **ChildJobState** parameter, the **IncludeChildJob** parameter has no effect.</span></span>

<span data-ttu-id="23e21-244">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="23e21-244">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23e21-245">-Command</span><span class="sxs-lookup"><span data-stu-id="23e21-245">-Command</span></span>

<span data-ttu-id="23e21-246">Gibt ein Array von Befehlen als Zeichen folgen an.</span><span class="sxs-lookup"><span data-stu-id="23e21-246">Specifies an array of commands as strings.</span></span> <span data-ttu-id="23e21-247">Mit diesem Cmdlet werden die Aufträge abgerufen, die die angegebenen Befehle enthalten.</span><span class="sxs-lookup"><span data-stu-id="23e21-247">This cmdlet gets the jobs that include the specified commands.</span></span> <span data-ttu-id="23e21-248">Standardmäßig werden alle Aufträge fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="23e21-248">The default is all jobs.</span></span> <span data-ttu-id="23e21-249">Sie können Platzhalter Zeichen verwenden, um ein Befehls Muster anzugeben.</span><span class="sxs-lookup"><span data-stu-id="23e21-249">You can use wildcard characters to specify a command pattern.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="23e21-250">-Filter</span><span class="sxs-lookup"><span data-stu-id="23e21-250">-Filter</span></span>

<span data-ttu-id="23e21-251">Gibt eine Hash Tabelle mit Bedingungen an.</span><span class="sxs-lookup"><span data-stu-id="23e21-251">Specifies a hash table of conditions.</span></span> <span data-ttu-id="23e21-252">Dieses Cmdlet ruft Aufträge ab, die alle Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="23e21-252">This cmdlet gets jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="23e21-253">Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="23e21-253">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="23e21-254">Dieser Parameter funktioniert nur mit benutzerdefinierten Auftragstypen, z. B. Workflowaufträgen und geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="23e21-254">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="23e21-255">Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des `Start-Job` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="23e21-255">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="23e21-256">Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="23e21-256">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="23e21-257">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="23e21-257">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="23e21-258">-Hasmoredata</span><span class="sxs-lookup"><span data-stu-id="23e21-258">-HasMoreData</span></span>

<span data-ttu-id="23e21-259">Gibt an, ob dieses Cmdlet nur Aufträge mit dem angegebenen **hasmoredata** -Eigenschafts Wert abruft.</span><span class="sxs-lookup"><span data-stu-id="23e21-259">Indicates whether this cmdlet gets only jobs that have the specified **HasMoreData** property value.</span></span>
<span data-ttu-id="23e21-260">Die **HasMoreData**-Eigenschaft gibt an, ob alle Auftragsergebnisse in der aktuellen Sitzung empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="23e21-260">The **HasMoreData** property indicates whether all job results have been received in the current session.</span></span> <span data-ttu-id="23e21-261">Um Aufträge mit weiteren Ergebnissen zu erhalten, geben Sie den Wert an `$True` .</span><span class="sxs-lookup"><span data-stu-id="23e21-261">To get jobs that have more results, specify a value of `$True`.</span></span> <span data-ttu-id="23e21-262">Um Aufträge zu erhalten, die keine weiteren Ergebnisse aufweisen, geben Sie den Wert an `$False` .</span><span class="sxs-lookup"><span data-stu-id="23e21-262">To get jobs that do not have more results, specify a value of `$False`.</span></span>

<span data-ttu-id="23e21-263">Verwenden Sie das-Cmdlet, um die Ergebnisse eines Auftrags zu erhalten `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="23e21-263">To get the results of a job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="23e21-264">Wenn Sie das `Receive-Job` Cmdlet verwenden, wird es aus dem in-Memory-Sitzungs spezifischen Speicher für die zurückgegebenen Ergebnisse gelöscht.</span><span class="sxs-lookup"><span data-stu-id="23e21-264">When you use the `Receive-Job` cmdlet, it deletes from its in-memory, session-specific storage the results that it returned.</span></span> <span data-ttu-id="23e21-265">Wenn alle Ergebnisse des Auftrags in der aktuellen Sitzung zurückgegeben wurden, wird der Wert der **hasmoredata** -Eigenschaft des Auftrags auf festgelegt, `$False` um anzugeben, dass keine weiteren Ergebnisse für den Auftrag in der aktuellen Sitzung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="23e21-265">When it has returned all results of the job in the current session, it sets the value of the **HasMoreData** property of the job to `$False`) to indicate that it has no more results for the job in the current session.</span></span> <span data-ttu-id="23e21-266">Verwenden Sie den **Keep** -Parameter von `Receive-Job` , um zu verhindern, dass `Receive-Job` Ergebnisse gelöscht und der Wert der **hasmoredata** -Eigenschaft geändert werden.</span><span class="sxs-lookup"><span data-stu-id="23e21-266">Use the **Keep** parameter of `Receive-Job` to prevent `Receive-Job` from deleting results and changing the value of the **HasMoreData** property.</span></span>
<span data-ttu-id="23e21-267">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="23e21-267">For more information, type `Get-Help Receive-Job`.</span></span>

<span data-ttu-id="23e21-268">Die **HasMoreData**-Eigenschaft ist für die aktuelle Sitzung spezifisch.</span><span class="sxs-lookup"><span data-stu-id="23e21-268">The **HasMoreData** property is specific to the current session.</span></span> <span data-ttu-id="23e21-269">Wenn die Ergebnisse für einen benutzerdefinierten Auftragstyp außerhalb der Sitzung gespeichert werden, wie z. b. der geplante Auftragstyp, der Auftrags Ergebnisse auf dem Datenträger speichert, können Sie das `Receive-Job` Cmdlet in einer anderen Sitzung verwenden, um die Auftrags Ergebnisse erneut zu erhalten, auch wenn der Wert von **hasmoredata** ist `$False` .</span><span class="sxs-lookup"><span data-stu-id="23e21-269">If results for a custom job type are saved outside of the session, such as the scheduled job type, which saves job results on disk, you can use the `Receive-Job` cmdlet in a different session to get the job results again, even if the value of **HasMoreData** is `$False`.</span></span> <span data-ttu-id="23e21-270">Weitere Informationen finden Sie in den Hilfethemen für den benutzerdefinierten Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="23e21-270">For more information, see the help topics for the custom job type.</span></span>

<span data-ttu-id="23e21-271">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="23e21-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23e21-272">-Id</span><span class="sxs-lookup"><span data-stu-id="23e21-272">-Id</span></span>

<span data-ttu-id="23e21-273">Gibt ein Array von IDs von Aufträgen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="23e21-273">Specifies an array of IDs of jobs that this cmdlet gets.</span></span>

<span data-ttu-id="23e21-274">Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="23e21-274">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="23e21-275">Es ist einfacher, sich zu merken und als die Instanz-ID einzugeben, aber es ist nur in der aktuellen Sitzung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="23e21-275">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="23e21-276">Sie können eine oder mehrere durch Kommas getrennte IDs eingeben.</span><span class="sxs-lookup"><span data-stu-id="23e21-276">You can type one or more IDs separated by commas.</span></span> <span data-ttu-id="23e21-277">Um die ID eines Auftrags zu ermitteln, geben Sie `Get-Job` ohne Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="23e21-277">To find the ID of a job, type `Get-Job` without parameters.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="23e21-278">-Incluentchildjob</span><span class="sxs-lookup"><span data-stu-id="23e21-278">-IncludeChildJob</span></span>

<span data-ttu-id="23e21-279">Gibt an, dass dieses Cmdlet neben den übergeordneten Aufträgen auch untergeordnete Aufträge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="23e21-279">Indicates that this cmdlet returns child jobs, in addition to parent jobs.</span></span>

<span data-ttu-id="23e21-280">Dieser Parameter ist besonders nützlich für die Untersuchung von Workflow Aufträgen, für die `Get-Job` einen übergeordneten Container Auftrag und Auftrags Fehler zurückgibt, da die Ursache für den Fehler in einer Eigenschaft des untergeordneten Auftrags gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="23e21-280">This parameter is especially useful for investigating workflow jobs, for which `Get-Job` returns a container parent job, and job failures, because the reason for the failure is saved in a property of the child job.</span></span>

<span data-ttu-id="23e21-281">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="23e21-281">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23e21-282">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="23e21-282">-InstanceId</span></span>

<span data-ttu-id="23e21-283">Gibt ein Array von Instanz-IDs von Aufträgen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="23e21-283">Specifies an array of instance IDs of jobs that this cmdlet gets.</span></span> <span data-ttu-id="23e21-284">Standardmäßig werden alle Aufträge fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="23e21-284">The default is all jobs.</span></span>

<span data-ttu-id="23e21-285">Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="23e21-285">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="23e21-286">Um die Instanz-ID eines Auftrags zu ermitteln, verwenden Sie `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="23e21-286">To find the instance ID of a job, use `Get-Job`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="23e21-287">-Name</span><span class="sxs-lookup"><span data-stu-id="23e21-287">-Name</span></span>

<span data-ttu-id="23e21-288">Gibt ein Array von instanzfreundlichen Namen von Aufträgen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="23e21-288">Specifies an array of instance friendly names of jobs that this cmdlet gets.</span></span> <span data-ttu-id="23e21-289">Geben Sie einen Auftragsnamen ein, oder verwenden Sie Platzhalterzeichen, um ein Auftragsnamensmuster einzugeben.</span><span class="sxs-lookup"><span data-stu-id="23e21-289">Enter a job name, or use wildcard characters to enter a job name pattern.</span></span> <span data-ttu-id="23e21-290">Standardmäßig ruft `Get-Job` alle Aufträge in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="23e21-290">By default, `Get-Job` gets all jobs in the current session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="23e21-291">-Latest</span><span class="sxs-lookup"><span data-stu-id="23e21-291">-Newest</span></span>

<span data-ttu-id="23e21-292">Gibt eine Anzahl von Aufträgen an, die erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="23e21-292">Specifies a number of jobs to get.</span></span> <span data-ttu-id="23e21-293">Dieses Cmdlet ruft die Aufträge ab, die zuletzt beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="23e21-293">This cmdlet gets the jobs that ended most recently.</span></span>

<span data-ttu-id="23e21-294">Die letzten Aufträge werden vom **Newest**-Parameter nicht in der Reihenfolge ihrer Endezeit sortiert oder zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="23e21-294">The **Newest** parameter does not sort or return the newest jobs in end-time order.</span></span> <span data-ttu-id="23e21-295">Verwenden Sie das-Cmdlet, um die Ausgabe zu sortieren `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="23e21-295">To sort the output, use the `Sort-Object` cmdlet.</span></span>

<span data-ttu-id="23e21-296">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="23e21-296">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23e21-297">-State</span><span class="sxs-lookup"><span data-stu-id="23e21-297">-State</span></span>

<span data-ttu-id="23e21-298">Gibt einen Auftragsstatus an.</span><span class="sxs-lookup"><span data-stu-id="23e21-298">Specifies a job state.</span></span> <span data-ttu-id="23e21-299">Dieses Cmdlet ruft nur Aufträge im angegebenen Zustand ab.</span><span class="sxs-lookup"><span data-stu-id="23e21-299">This cmdlet gets only jobs in the specified state.</span></span> <span data-ttu-id="23e21-300">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="23e21-300">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="23e21-301">NotStarted</span><span class="sxs-lookup"><span data-stu-id="23e21-301">NotStarted</span></span>
- <span data-ttu-id="23e21-302">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="23e21-302">Running</span></span>
- <span data-ttu-id="23e21-303">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="23e21-303">Completed</span></span>
- <span data-ttu-id="23e21-304">Fehler</span><span class="sxs-lookup"><span data-stu-id="23e21-304">Failed</span></span>
- <span data-ttu-id="23e21-305">Beendet</span><span class="sxs-lookup"><span data-stu-id="23e21-305">Stopped</span></span>
- <span data-ttu-id="23e21-306">Gesperrt</span><span class="sxs-lookup"><span data-stu-id="23e21-306">Blocked</span></span>
- <span data-ttu-id="23e21-307">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="23e21-307">Suspended</span></span>
- <span data-ttu-id="23e21-308">Getrennt</span><span class="sxs-lookup"><span data-stu-id="23e21-308">Disconnected</span></span>
- <span data-ttu-id="23e21-309">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="23e21-309">Suspending</span></span>
- <span data-ttu-id="23e21-310">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="23e21-310">Stopping</span></span>

<span data-ttu-id="23e21-311">Standardmäßig ruft `Get-Job` alle Aufträge in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="23e21-311">By default, `Get-Job` gets all the jobs in the current session.</span></span>

<span data-ttu-id="23e21-312">Weitere Informationen zu Auftrags Zuständen finden Sie unter [jobstate-Enumeration](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="23e21-312">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="23e21-313">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="23e21-313">CommonParameters</span></span>

<span data-ttu-id="23e21-314">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="23e21-314">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="23e21-315">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="23e21-315">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="23e21-316">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="23e21-316">INPUTS</span></span>

### <span data-ttu-id="23e21-317">Keine</span><span class="sxs-lookup"><span data-stu-id="23e21-317">None</span></span>

<span data-ttu-id="23e21-318">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="23e21-318">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="23e21-319">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="23e21-319">OUTPUTS</span></span>

### <span data-ttu-id="23e21-320">System. Management. Automation. remotingjob</span><span class="sxs-lookup"><span data-stu-id="23e21-320">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="23e21-321">Dieses Cmdlet gibt Objekte zurück, die die Aufträge in der Sitzung darstellen.</span><span class="sxs-lookup"><span data-stu-id="23e21-321">This cmdlet returns objects that represent the jobs in the session.</span></span>

## <span data-ttu-id="23e21-322">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="23e21-322">NOTES</span></span>

<span data-ttu-id="23e21-323">Die **PSJobTypeName**-Eigenschaft von Aufträgen gibt den Auftragstyp des Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="23e21-323">The **PSJobTypeName** property of jobs indicates the job type of the job.</span></span> <span data-ttu-id="23e21-324">Der Eigenschaftswert wird vom Autor des Auftragstyps bestimmt.</span><span class="sxs-lookup"><span data-stu-id="23e21-324">The property value is determined by the job type author.</span></span> <span data-ttu-id="23e21-325">Die folgende Liste enthält allgemeine Auftragstypen.</span><span class="sxs-lookup"><span data-stu-id="23e21-325">The following list shows common job types.</span></span>

- <span data-ttu-id="23e21-326">**Backgroundjob**.</span><span class="sxs-lookup"><span data-stu-id="23e21-326">**BackgroundJob**.</span></span> <span data-ttu-id="23e21-327">Lokaler Auftrag, der mit gestartet wurde `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="23e21-327">Local job started by using `Start-Job`.</span></span>
- <span data-ttu-id="23e21-328">**Remotejob**.</span><span class="sxs-lookup"><span data-stu-id="23e21-328">**RemoteJob**.</span></span> <span data-ttu-id="23e21-329">Der Auftrag wurde in einer **PSSession** mithilfe des **AsJob** -Parameters des `Invoke-Command` Cmdlets gestartet.</span><span class="sxs-lookup"><span data-stu-id="23e21-329">Job started in a **PSSession** by using the **AsJob** parameter of the `Invoke-Command` cmdlet.</span></span>
- <span data-ttu-id="23e21-330">**Psworkflowjob**.</span><span class="sxs-lookup"><span data-stu-id="23e21-330">**PSWorkflowJob**.</span></span> <span data-ttu-id="23e21-331">Auftrag, der mit dem allgemeinen **AsJob**-Parameter von Workflows gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="23e21-331">Job started by using the **AsJob** common parameter of workflows.</span></span>

## <span data-ttu-id="23e21-332">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="23e21-332">RELATED LINKS</span></span>

[<span data-ttu-id="23e21-333">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="23e21-333">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="23e21-334">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="23e21-334">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="23e21-335">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="23e21-335">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="23e21-336">Start-Job</span><span class="sxs-lookup"><span data-stu-id="23e21-336">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="23e21-337">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="23e21-337">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="23e21-338">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="23e21-338">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="23e21-339">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="23e21-339">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="23e21-340">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="23e21-340">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="23e21-341">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="23e21-341">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)
