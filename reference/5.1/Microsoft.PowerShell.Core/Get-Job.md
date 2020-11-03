---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 0b9c76ca1e26adaa244473366c2eabdaaa28452c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212031"
---
# <span data-ttu-id="9e645-103">Get-Job</span><span class="sxs-lookup"><span data-stu-id="9e645-103">Get-Job</span></span>

## <span data-ttu-id="9e645-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9e645-104">SYNOPSIS</span></span>
<span data-ttu-id="9e645-105">Ruft PowerShell-Hintergrund Aufträge ab, die in der aktuellen Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9e645-105">Gets PowerShell background jobs that are running in the current session.</span></span>

## <span data-ttu-id="9e645-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9e645-106">SYNTAX</span></span>

### <span data-ttu-id="9e645-107">Sessionidparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="9e645-107">SessionIdParameterSet (Default)</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="9e645-108">Commandparameterset</span><span class="sxs-lookup"><span data-stu-id="9e645-108">CommandParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="9e645-109">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="9e645-109">InstanceIdParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="9e645-110">Nameparameterset</span><span class="sxs-lookup"><span data-stu-id="9e645-110">NameParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="9e645-111">Stateparameterset</span><span class="sxs-lookup"><span data-stu-id="9e645-111">StateParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="9e645-112">Filterparameterset</span><span class="sxs-lookup"><span data-stu-id="9e645-112">FilterParameterSet</span></span>

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="9e645-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9e645-113">DESCRIPTION</span></span>

<span data-ttu-id="9e645-114">Das **Get-Job** -Cmdlet ruft Objekte ab, die die in der aktuellen Sitzung gestarteten Hintergrundaufträge darstellen.</span><span class="sxs-lookup"><span data-stu-id="9e645-114">The **Get-Job** cmdlet gets objects that represent the background jobs that were started in the current session.</span></span>
<span data-ttu-id="9e645-115">Sie können **Get-Job** verwenden, um Aufträge zu erhalten, die mit dem Cmdlet "Start-Job" oder mit dem *AsJob* -Parameter eines beliebigen Cmdlets gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="9e645-115">You can use **Get-Job** to get jobs that were started by using the Start-Job cmdlet, or by using the *AsJob* parameter of any cmdlet.</span></span>

<span data-ttu-id="9e645-116">Ohne Parameter ruft ein **Get-Job-** Befehl alle Aufträge in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="9e645-116">Without parameters, a **Get-Job** command gets all jobs in the current session.</span></span>
<span data-ttu-id="9e645-117">Mithilfe der Parameter von **Get-Job** können Sie bestimmte Aufträge abrufen.</span><span class="sxs-lookup"><span data-stu-id="9e645-117">You can use the parameters of **Get-Job** to get particular jobs.</span></span>

<span data-ttu-id="9e645-118">Das von **Get-Job** zurückgegebene Auftragsobjekt enthält nützliche Informationen zum Auftrag, aber keine Auftragsergebnisse.</span><span class="sxs-lookup"><span data-stu-id="9e645-118">The job object that **Get-Job** returns contains useful information about the job, but it does not contain the job results.</span></span>
<span data-ttu-id="9e645-119">Verwenden Sie das Cmdlet "Receive-Job", um die Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9e645-119">To get the results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="9e645-120">Ein Windows PowerShell-Hintergrund Auftrag ist ein Befehl, der im Hintergrund ausgeführt wird, ohne mit der aktuellen Sitzung zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="9e645-120">A Windows PowerShell background job is a command that runs in the background without interacting with the current session.</span></span>
<span data-ttu-id="9e645-121">In der Regel verwenden Sie einen Hintergrund Auftrag, um einen komplexen Befehl auszuführen, der lange Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="9e645-121">Typically, you use a background job to run a complex command that takes a long time to finish.</span></span>
<span data-ttu-id="9e645-122">Weitere Informationen zu Hintergrundaufträgen in Windows PowerShell finden Sie unter about_Jobs.</span><span class="sxs-lookup"><span data-stu-id="9e645-122">For more information about background jobs in Windows PowerShell, see about_Jobs.</span></span>

<span data-ttu-id="9e645-123">Ab Windows PowerShell 3.0 ruft das **Get-Job** -Cmdlet auch benutzerdefinierte Auftragstypen ab, wie z. B. Workflowaufträge und Instanzen von geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="9e645-123">Beginning in Windows PowerShell 3.0, the **Get-Job** cmdlet also gets custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="9e645-124">Zum Ermitteln des Auftragstyps eines Auftrags verwenden Sie die **PSJobTypeName** -Eigenschaft des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="9e645-124">To find the job type of a job, use the **PSJobTypeName** property of the job.</span></span>

<span data-ttu-id="9e645-125">Zum Aktivieren von **Get-Job** zum erhalten eines benutzerdefinierten Auftrags Typs importieren Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, in die Sitzung, bevor Sie einen **Get-Job-** Befehl ausführen. verwenden Sie hierzu entweder das Cmdlet "Import-Module", oder verwenden Sie ein Cmdlet im Modul.</span><span class="sxs-lookup"><span data-stu-id="9e645-125">To enable **Get-Job** to get a custom job type, import the module that supports the custom job type into the session before you run a **Get-Job** command, either by using the Import-Module cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="9e645-126">Informationen zu einem bestimmten benutzerdefinierten Auftragstyp finden Sie in der Dokumentation der Funktion „Benutzerdefinierte Auftragstypen“.</span><span class="sxs-lookup"><span data-stu-id="9e645-126">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="9e645-127">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9e645-127">EXAMPLES</span></span>

### <span data-ttu-id="9e645-128">Beispiel 1: alle Hintergrund Aufträge, die in der aktuellen Sitzung gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="9e645-128">Example 1: Get all background jobs started in the current session</span></span>

```
PS C:\> Get-Job
```

<span data-ttu-id="9e645-129">Dieser Befehl ruft alle Hintergrundaufträge ab, die in der aktuellen Sitzung gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="9e645-129">This command gets all background jobs started in the current session.</span></span>
<span data-ttu-id="9e645-130">In anderen Sitzungen erstellte Aufträge sind nicht enthalten, auch wenn die Aufträge auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9e645-130">It does not include jobs created in other sessions, even if the jobs run on the local computer.</span></span>

### <span data-ttu-id="9e645-131">Beispiel 2: Beenden eines Auftrags mit einer Instanz-ID</span><span class="sxs-lookup"><span data-stu-id="9e645-131">Example 2: Stop a job by using an instance ID</span></span>

```
The first command uses the **Get-Job** cmdlet to get a job. It uses the *Name* parameter to identify the job. The command stores the job object that **Get-Job** returns in the $j variable. In this example, there is only one job with the specified name.
PS C:\> $j = Get-Job -Name Job1

The second command gets the **InstanceId** property of the object in the $j variable and stores it in the $ID variable.
PS C:\> $ID = $j.InstanceID

The third command displays the value of the $ID variable.
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

The fourth command uses Stop-Job cmdlet to stop the job. It uses the *InstanceId* parameter to identify the job and $ID variable to represent the instance ID of the job.
PS C:\> Stop-Job -InstanceId $ID
```

<span data-ttu-id="9e645-132">Diese Befehle zeigen, wie die Instanz-ID eines Auftrags abgerufen und dann zum Beenden eines Auftrags verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e645-132">These commands show how to get the instance ID of a job and then use it to stop a job.</span></span>
<span data-ttu-id="9e645-133">Im Gegensatz zum Namen eines Auftrags, der nicht eindeutig ist, ist die Instanz-ID eindeutig.</span><span class="sxs-lookup"><span data-stu-id="9e645-133">Unlike the name of a job, which is not unique, the instance ID is unique.</span></span>

### <span data-ttu-id="9e645-134">Beispiel 3: Get-Aufträge, die einen bestimmten Befehl enthalten</span><span class="sxs-lookup"><span data-stu-id="9e645-134">Example 3: Get jobs that include a specific command</span></span>

```
PS C:\> Get-Job -Command "*get-process*"
```

<span data-ttu-id="9e645-135">Dieser Befehl ruft die Aufträge im System ab, die einen Get-Process Befehl enthalten.</span><span class="sxs-lookup"><span data-stu-id="9e645-135">This command gets the jobs on the system that include a Get-Process command.</span></span>
<span data-ttu-id="9e645-136">Der Befehl verwendet den *Command* -Parameter von **Get-Job** , um die abgerufenen Aufträge einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="9e645-136">The command uses the *Command* parameter of **Get-Job** to limit the jobs retrieved.</span></span>
<span data-ttu-id="9e645-137">Der Befehl verwendet Platzhalter Zeichen (\*), um Aufträge zu erhalten, die in der Befehls Zeichenfolge einen **Get-Process-** Befehl enthalten.</span><span class="sxs-lookup"><span data-stu-id="9e645-137">The command uses wildcard characters (\*) to get jobs that include a **Get-Process** command anywhere in the command string.</span></span>

### <span data-ttu-id="9e645-138">Beispiel 4: Get-Aufträge, die einen bestimmten Befehl enthalten, mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="9e645-138">Example 4: Get jobs that include a specific command by using the pipeline</span></span>

```
PS C:\> "*get-process*" | Get-Job
```

<span data-ttu-id="9e645-139">Wie der Befehl im vorherigen Beispiel ruft dieser Befehl die Aufträge im System ab, die einen **Get-Process-** Befehl enthalten.</span><span class="sxs-lookup"><span data-stu-id="9e645-139">Like the command in the previous example, this command gets the jobs on the system that include a **Get-Process** command.</span></span>
<span data-ttu-id="9e645-140">Der Befehl verwendet einen Pipeline Operator (|), um eine Zeichenfolge in Anführungszeichen an das **Get-Job-** Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="9e645-140">The command uses a pipeline operator (|) to send a string, in quotation marks, to the **Get-Job** cmdlet.</span></span>
<span data-ttu-id="9e645-141">Dies entspricht dem vorherigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="9e645-141">It is the equivalent of the previous command.</span></span>

### <span data-ttu-id="9e645-142">Beispiel 5: Aufträge, die noch nicht gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="9e645-142">Example 5: Get jobs that have not been started</span></span>

```
PS C:\> Get-Job -State NotStarted
```

<span data-ttu-id="9e645-143">Mit diesem Befehl werden nur die Aufträge abgerufen, die erstellt, aber noch nicht gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="9e645-143">This command gets only those jobs that have been created but have not yet been started.</span></span>
<span data-ttu-id="9e645-144">Dazu gehören Aufträge, deren Ausführung für einen Zeitpunkt in der Zukunft geplant ist, und solche, die noch nicht geplant wurden.</span><span class="sxs-lookup"><span data-stu-id="9e645-144">This includes jobs that are scheduled to run in the future and those not yet scheduled.</span></span>

### <span data-ttu-id="9e645-145">Beispiel 6: Aufträge erhalten, denen kein Name zugewiesen wurde</span><span class="sxs-lookup"><span data-stu-id="9e645-145">Example 6: Get jobs that have not been assigned a name</span></span>

```
PS C:\> Get-Job -Name Job*
```

<span data-ttu-id="9e645-146">Dieser Befehl ruft alle Aufträge ab, deren Auftrags Name mit "Job" beginnt.</span><span class="sxs-lookup"><span data-stu-id="9e645-146">This command gets all jobs that have job names that begin with job.</span></span>
<span data-ttu-id="9e645-147">Da Job \<number\> der Standardname für einen Auftrag ist, ruft dieser Befehl alle Aufträge ab, denen kein explizit zugewiesener Name zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="9e645-147">Because job\<number\> is the default name for a job, this command gets all jobs that do not have an explicitly assigned name.</span></span>

### <span data-ttu-id="9e645-148">Beispiel 7: Verwenden eines Auftrags Objekts zur Darstellung des Auftrags in einem Befehl</span><span class="sxs-lookup"><span data-stu-id="9e645-148">Example 7: Use a job object to represent the job in a command</span></span>

```
The first command uses the **Start-Job** cmdlet to start a background job that runs a **Get-Process** command on the local computer. The command uses the *Name* parameter of **Start-Job** to assign a friendly name to the job.
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob

The second command uses Get-Job to get the job. It uses the *Name* parameter of **Get-Job** to identify the job. The command saves the resulting job object in the $j variable.
PS C:\> $j = Get-Job -Name MyJob

The third command displays the value of the job object in the $j variable. The value of the **State** property shows that the job is completed. The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

The fourth command uses the **Receive-Job** cmdlet to get the results of the job. It uses the job object in the $j variable to represent the job. You can also use a pipeline operator to send a job object to **Receive-Job**.
PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

<span data-ttu-id="9e645-149">Dieses Beispiel veranschaulicht, wie Sie mit **Get-Job** ein Auftragsobjekt abrufen. Anschließend wird gezeigt, wie Sie mit dem Auftragsobjekt den Auftrag in einem Befehl darstellen.</span><span class="sxs-lookup"><span data-stu-id="9e645-149">This example shows how to use **Get-Job** to get a job object, and then it shows how to use the job object to represent the job in a command.</span></span>

### <span data-ttu-id="9e645-150">Beispiel 8: alle Aufträge einschließlich der von einer anderen Methode gestarteten Aufträge</span><span class="sxs-lookup"><span data-stu-id="9e645-150">Example 8: Get all jobs including jobs started by a different method</span></span>

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer.
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}

The second command uses the *AsJob* parameter of the **Invoke-Command** cmdlet to start a job on the S1 computer. Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob

The third command uses the **Invoke-Command** cmdlet to run a **Start-Job** command on the S2 computer. By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}

The fourth command uses **Get-Job** to get the jobs stored on the local computer. The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the **Start-Job** cmdlet is a background job and the job started in a remote session by using the **Invoke-Command** cmdlet is a remote job.
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

The fifth command uses **Invoke-Command** to run a **Get-Job** command on the S2 computer.The sample output shows the results of the Get-Job command. On the S2 computer, the job appears to be a local job. The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see about_Remote_Jobs.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

<span data-ttu-id="9e645-151">In diesem Beispiel wird veranschaulicht, dass das **Get-Job-** Cmdlet alle Aufträge, die in der aktuellen Sitzung gestartet wurden, auch dann erhalten kann, wenn Sie mit verschiedenen Methoden gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="9e645-151">This example demonstrates that the **Get-Job** cmdlet can get all of the jobs that were started in the current session, even if they were started by using different methods.</span></span>

### <span data-ttu-id="9e645-152">Beispiel 9: Untersuchen eines fehlgeschlagenen Auftrags</span><span class="sxs-lookup"><span data-stu-id="9e645-152">Example 9: Investigate a failed job</span></span>

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer. The job object that **Start-Job** returns shows that the job failed. The value of the **State** property is Failed.
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

The second command uses the **Get-Job** cmdlet to get the job. The command uses the dot method to get the value of the **JobStateInfo** property of the object. It uses a pipeline operator to send the object in the **JobStateInfo** property to the Format-List cmdlet, which formats all of the properties of the object (*) in a list.The result of the **Format-List** command shows that the value of the **Reason** property of the job is blank.
PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

The third command investigates more. It uses a **Get-Job** command to get the job and then uses a pipeline operator to send the whole job object to the **Format-List** cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.
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

The fourth command uses **Get-Job** to get the job object that represents the Job2 child job. This is the job in which the command actually ran. It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error. In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see about_Remote_Requirements. For troubleshooting tips, see about_Remote_Troubleshooting.
PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.
```

<span data-ttu-id="9e645-153">Dieser Befehl zeigt, wie das von **Get-Job** zurückgegebene Auftrags Objekt verwendet wird, um zu untersuchen, warum ein Auftrag fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="9e645-153">This command shows how to use the job object that **Get-Job** returns to investigate why a job failed.</span></span>
<span data-ttu-id="9e645-154">Weiterhin wird gezeigt, wie die untergeordneten Aufträge der einzelnen Aufträge abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9e645-154">It also shows how to get the child jobs of each job.</span></span>

### <span data-ttu-id="9e645-155">Beispiel 10: Filtern von gefilterten Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="9e645-155">Example 10: Get filtered results</span></span>

```
The first command uses the **Workflow** keyword to create the WFProcess workflow.
PS C:\> Workflow WFProcess {Get-Process}

The second command uses the *AsJob* parameter of the WFProcess workflow to run the workflow as a background job. It uses the *JobName* parameter of the workflow to specify a name for the job, and the *PSPrivateMetadata* parameter of the workflow to specify a custom ID.
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}

The third command uses the *Filter* parameter of **Get-Job** to get the job by custom ID that was specified in the *PSPrivateMetadata* parameter.
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

<span data-ttu-id="9e645-156">Dieses Beispiel zeigt, wie Sie den *Filter* -Parameter zum Abrufen eines Workflowauftrags verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e645-156">This example shows how to use the *Filter* parameter to get a workflow job.</span></span>
<span data-ttu-id="9e645-157">Der in Windows PowerShell 3.0 eingeführte *Filter* -Parameter ist nur für benutzerdefinierte Auftragstypen gültig, wie z. B. Workflowaufträge und geplante Aufträge.</span><span class="sxs-lookup"><span data-stu-id="9e645-157">The *Filter* parameter, introduced in Windows PowerShell 3.0 is valid only on custom job types, such as workflow jobs and scheduled jobs.</span></span>

### <span data-ttu-id="9e645-158">Beispiel 11: erhalten von Informationen zu untergeordneten Aufträgen</span><span class="sxs-lookup"><span data-stu-id="9e645-158">Example 11: Get information about child jobs</span></span>

```
The first command gets the jobs in the current session. The output includes a background job, a remote job and several instances of a scheduled job. The remote job, Job4, appears to have failed.
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The second command uses the *IncludeChildJob* parameter of **Get-Job**. The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.
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

The third command uses the *ChildJobState* parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.
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

The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.
PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

<span data-ttu-id="9e645-159">Dieses Beispiel zeigt die Auswirkungen der Verwendung der Parameter *IncludeChildJob* und *ChildJobState* des **Get-Job** -Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9e645-159">This example shows the effect of using the *IncludeChildJob* and *ChildJobState* parameters of the **Get-Job** cmdlet.</span></span>

## <span data-ttu-id="9e645-160">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9e645-160">PARAMETERS</span></span>

### <span data-ttu-id="9e645-161">Nach</span><span class="sxs-lookup"><span data-stu-id="9e645-161">-After</span></span>

<span data-ttu-id="9e645-162">Ruft abgeschlossene Aufträge ab, die nach dem angegebenen Datum und der angegebenen Uhrzeit beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="9e645-162">Gets completed jobs that ended after the specified date and time.</span></span>
<span data-ttu-id="9e645-163">Geben Sie ein **DateTime** -Objekt ein, z. b. ein vom Get-Date Cmdlet zurück gegebenes oder eine Zeichenfolge, die in ein **DateTime** -Objekt konvertiert werden kann, z `Dec 1, 2012 2:00 AM` . b `11/06` . oder.</span><span class="sxs-lookup"><span data-stu-id="9e645-163">Enter a **DateTime** object, such as one returned by the Get-Date cmdlet or a string that can be converted to a **DateTime** object, such as `Dec 1, 2012 2:00 AM` or `11/06`.</span></span>

<span data-ttu-id="9e645-164">Dieser Parameter kann nur für benutzerdefinierte Auftragstypen wie z. B. Workflowaufträge und geplante Aufträge verwendet werden, die über eine **EndTime** -Eigenschaft verfügen.</span><span class="sxs-lookup"><span data-stu-id="9e645-164">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span>
<span data-ttu-id="9e645-165">Es funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="9e645-165">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="9e645-166">Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="9e645-166">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="9e645-167">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9e645-167">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e645-168">-Vor</span><span class="sxs-lookup"><span data-stu-id="9e645-168">-Before</span></span>

<span data-ttu-id="9e645-169">Ruft abgeschlossene Aufträge ab, die vor dem angegebenen Datum und der angegebenen Uhrzeit beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="9e645-169">Gets completed jobs that ended before the specified date and time.</span></span>
<span data-ttu-id="9e645-170">Geben Sie ein **DateTime** -Objekt ein.</span><span class="sxs-lookup"><span data-stu-id="9e645-170">Enter a **DateTime** object.</span></span>

<span data-ttu-id="9e645-171">Dieser Parameter kann nur für benutzerdefinierte Auftragstypen wie z. B. Workflowaufträge und geplante Aufträge verwendet werden, die über eine **EndTime** -Eigenschaft verfügen.</span><span class="sxs-lookup"><span data-stu-id="9e645-171">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span>
<span data-ttu-id="9e645-172">Es funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="9e645-172">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="9e645-173">Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="9e645-173">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="9e645-174">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9e645-174">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e645-175">-Childjobstate</span><span class="sxs-lookup"><span data-stu-id="9e645-175">-ChildJobState</span></span>

<span data-ttu-id="9e645-176">Ruft nur die untergeordneten Aufträge ab, die den angegebenen Status aufweisen.</span><span class="sxs-lookup"><span data-stu-id="9e645-176">Gets only the child jobs that have the specified state.</span></span>
<span data-ttu-id="9e645-177">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="9e645-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9e645-178">NotStarted</span><span class="sxs-lookup"><span data-stu-id="9e645-178">NotStarted</span></span>
- <span data-ttu-id="9e645-179">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="9e645-179">Running</span></span>
- <span data-ttu-id="9e645-180">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="9e645-180">Completed</span></span>
- <span data-ttu-id="9e645-181">Fehler</span><span class="sxs-lookup"><span data-stu-id="9e645-181">Failed</span></span>
- <span data-ttu-id="9e645-182">Beendet</span><span class="sxs-lookup"><span data-stu-id="9e645-182">Stopped</span></span>
- <span data-ttu-id="9e645-183">Blockiert</span><span class="sxs-lookup"><span data-stu-id="9e645-183">Blocked</span></span>
- <span data-ttu-id="9e645-184">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="9e645-184">Suspended</span></span>
- <span data-ttu-id="9e645-185">Getrennt</span><span class="sxs-lookup"><span data-stu-id="9e645-185">Disconnected</span></span>
- <span data-ttu-id="9e645-186">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="9e645-186">Suspending</span></span>
- <span data-ttu-id="9e645-187">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="9e645-187">Stopping</span></span>

<span data-ttu-id="9e645-188">Standardmäßig ruft **Get-Job** keine untergeordneten Aufträge ab.</span><span class="sxs-lookup"><span data-stu-id="9e645-188">By default, **Get-Job** does not get child jobs.</span></span>
<span data-ttu-id="9e645-189">Wenn Sie den *incluentchildjob* -Parameter verwenden, ruft **Get-Job** alle untergeordneten Aufträge ab.</span><span class="sxs-lookup"><span data-stu-id="9e645-189">By using the *IncludeChildJob* parameter, **Get-Job** gets all child jobs.</span></span>
<span data-ttu-id="9e645-190">Bei Verwendung des *ChildJobState* -Parameters hat der *IncludeChildJob* -Parameter keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="9e645-190">If you use the *ChildJobState* parameter, the *IncludeChildJob* parameter has no effect.</span></span>

<span data-ttu-id="9e645-191">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9e645-191">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e645-192">-Command</span><span class="sxs-lookup"><span data-stu-id="9e645-192">-Command</span></span>

<span data-ttu-id="9e645-193">Gibt ein Array von Befehlen als Zeichen folgen an.</span><span class="sxs-lookup"><span data-stu-id="9e645-193">Specifies an array of commands as strings.</span></span>
<span data-ttu-id="9e645-194">Mit diesem Cmdlet werden die Aufträge abgerufen, die die angegebenen Befehle enthalten.</span><span class="sxs-lookup"><span data-stu-id="9e645-194">This cmdlet gets the jobs that include the specified commands.</span></span>
<span data-ttu-id="9e645-195">Standardmäßig werden alle Aufträge fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9e645-195">The default is all jobs.</span></span>
<span data-ttu-id="9e645-196">Sie können Platzhalter Zeichen verwenden, um ein Befehls Muster anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9e645-196">You can use wildcard characters to specify a command pattern.</span></span>

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

### <span data-ttu-id="9e645-197">-Filter</span><span class="sxs-lookup"><span data-stu-id="9e645-197">-Filter</span></span>

<span data-ttu-id="9e645-198">Gibt eine Hash Tabelle mit Bedingungen an.</span><span class="sxs-lookup"><span data-stu-id="9e645-198">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="9e645-199">Dieses Cmdlet ruft Aufträge ab, die alle Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9e645-199">This cmdlet gets jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="9e645-200">Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="9e645-200">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="9e645-201">Dieser Parameter funktioniert nur mit benutzerdefinierten Auftragstypen, z. B. Workflowaufträgen und geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="9e645-201">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span>
<span data-ttu-id="9e645-202">Es funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="9e645-202">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="9e645-203">Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="9e645-203">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="9e645-204">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9e645-204">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="9e645-205">-Hasmoredata</span><span class="sxs-lookup"><span data-stu-id="9e645-205">-HasMoreData</span></span>

<span data-ttu-id="9e645-206">Gibt an, ob dieses Cmdlet nur Aufträge mit dem angegebenen **hasmoredata** -Eigenschafts Wert abruft.</span><span class="sxs-lookup"><span data-stu-id="9e645-206">Indicates whether this cmdlet gets only jobs that have the specified **HasMoreData** property value.</span></span>
<span data-ttu-id="9e645-207">Die **HasMoreData** -Eigenschaft gibt an, ob alle Auftragsergebnisse in der aktuellen Sitzung empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="9e645-207">The **HasMoreData** property indicates whether all job results have been received in the current session.</span></span>
<span data-ttu-id="9e645-208">Um Aufträge mit weiteren Ergebnissen zu erhalten, geben Sie den Wert $true an.</span><span class="sxs-lookup"><span data-stu-id="9e645-208">To get jobs that have more results, specify a value of $True.</span></span>
<span data-ttu-id="9e645-209">Um Aufträge zu erhalten, die keine weiteren Ergebnisse aufweisen, geben Sie den Wert $false an.</span><span class="sxs-lookup"><span data-stu-id="9e645-209">To get jobs that do not have more results, specify a value of $False.</span></span>

<span data-ttu-id="9e645-210">Verwenden Sie das Cmdlet "Receive-Job", um die Ergebnisse eines Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9e645-210">To get the results of a job, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="9e645-211">Wenn Sie das **Receive-Job-** Cmdlet verwenden, löscht es die zurückgegebenen Ergebnisse aus dem in-Memory-Sitzungs spezifischen Speicher.</span><span class="sxs-lookup"><span data-stu-id="9e645-211">When you use the **Receive-Job** cmdlet, it deletes from its in-memory, session-specific storage the results that it returned.</span></span>
<span data-ttu-id="9e645-212">Wenn alle Ergebnisse des Auftrags in der aktuellen Sitzung zurückgegeben wurden, wird der Wert der **hasmoredata** -Eigenschaft des Auftrags auf $false) festgelegt, um anzugeben, dass keine weiteren Ergebnisse für den Auftrag in der aktuellen Sitzung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9e645-212">When it has returned all results of the job in the current session, it sets the value of the **HasMoreData** property of the job to $False) to indicate that it has no more results for the job in the current session.</span></span>
<span data-ttu-id="9e645-213">Verwenden Sie den *Keep* -Parameter von **Receive-Job** , um zu verhindern, dass **Receive-Job** Ergebnisse löscht und den Wert der **HasMoreData** -Eigenschaft ändert.</span><span class="sxs-lookup"><span data-stu-id="9e645-213">Use the *Keep* parameter of **Receive-Job** to prevent **Receive-Job** from deleting results and changing the value of the **HasMoreData** property.</span></span>
<span data-ttu-id="9e645-214">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="9e645-214">For more information, type `Get-Help Receive-Job`.</span></span>

<span data-ttu-id="9e645-215">Die **HasMoreData** -Eigenschaft ist für die aktuelle Sitzung spezifisch.</span><span class="sxs-lookup"><span data-stu-id="9e645-215">The **HasMoreData** property is specific to the current session.</span></span>
<span data-ttu-id="9e645-216">Wenn die Ergebnisse für einen benutzerdefinierten Auftragstyp außerhalb der Sitzung gespeichert werden, wie z. b. der geplante Auftragstyp, der Auftrags Ergebnisse auf dem Datenträger speichert, können Sie das **Receive-Job-** Cmdlet in einer anderen Sitzung verwenden, um die Auftrags Ergebnisse zu erhalten, auch wenn der Wert von **hasmoredata** $false ist.</span><span class="sxs-lookup"><span data-stu-id="9e645-216">If results for a custom job type are saved outside of the session, such as the scheduled job type, which saves job results on disk, you can use the **Receive-Job** cmdlet in a different session to get the job results again, even if the value of **HasMoreData** is $False.</span></span>
<span data-ttu-id="9e645-217">Weitere Informationen finden Sie in den Hilfethemen für den benutzerdefinierten Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="9e645-217">For more information, see the help topics for the custom job type.</span></span>

<span data-ttu-id="9e645-218">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9e645-218">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e645-219">-Id</span><span class="sxs-lookup"><span data-stu-id="9e645-219">-Id</span></span>

<span data-ttu-id="9e645-220">Gibt ein Array von IDs von Aufträgen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9e645-220">Specifies an array of IDs of jobs that this cmdlet gets.</span></span>

<span data-ttu-id="9e645-221">Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9e645-221">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="9e645-222">Es ist einfacher, sich zu merken und als die Instanz-ID einzugeben, aber es ist nur in der aktuellen Sitzung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="9e645-222">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="9e645-223">Sie können eine oder mehrere durch Kommas getrennte IDs eingeben.</span><span class="sxs-lookup"><span data-stu-id="9e645-223">You can type one or more IDs separated by commas.</span></span>
<span data-ttu-id="9e645-224">Um die ID eines Auftrags zu ermitteln, geben Sie `Get-Job` ohne Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="9e645-224">To find the ID of a job, type `Get-Job` without parameters.</span></span>

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

### <span data-ttu-id="9e645-225">-Incluentchildjob</span><span class="sxs-lookup"><span data-stu-id="9e645-225">-IncludeChildJob</span></span>

<span data-ttu-id="9e645-226">Gibt an, dass dieses Cmdlet neben den übergeordneten Aufträgen auch untergeordnete Aufträge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9e645-226">Indicates that this cmdlet returns child jobs, in addition to parent jobs.</span></span>

<span data-ttu-id="9e645-227">Dieser Parameter ist besonders nützlich für die Untersuchung von Workflow Aufträgen, für die **Get-Job** einen übergeordneten Container Auftrag zurückgibt, sowie für Auftrags Fehler, da der Grund für den Fehler in einer Eigenschaft des untergeordneten Auftrags gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="9e645-227">This parameter is especially useful for investigating workflow jobs, for which **Get-Job** returns a container parent job, and job failures, because the reason for the failure is saved in a property of the child job.</span></span>

<span data-ttu-id="9e645-228">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9e645-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e645-229">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="9e645-229">-InstanceId</span></span>

<span data-ttu-id="9e645-230">Gibt ein Array von Instanz-IDs von Aufträgen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9e645-230">Specifies an array of instance IDs of jobs that this cmdlet gets.</span></span>
<span data-ttu-id="9e645-231">Standardmäßig werden alle Aufträge fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9e645-231">The default is all jobs.</span></span>

<span data-ttu-id="9e645-232">Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9e645-232">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="9e645-233">Zum Ermitteln der Instanz-ID eines Auftrags verwenden Sie **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="9e645-233">To find the instance ID of a job, use **Get-Job** .</span></span>

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

### <span data-ttu-id="9e645-234">-Name</span><span class="sxs-lookup"><span data-stu-id="9e645-234">-Name</span></span>

<span data-ttu-id="9e645-235">Gibt ein Array von instanzfreundlichen Namen von Aufträgen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9e645-235">Specifies an array of instance friendly names of jobs that this cmdlet gets.</span></span>
<span data-ttu-id="9e645-236">Geben Sie einen Auftragsnamen ein, oder verwenden Sie Platzhalterzeichen, um ein Auftragsnamensmuster einzugeben.</span><span class="sxs-lookup"><span data-stu-id="9e645-236">Enter a job name, or use wildcard characters to enter a job name pattern.</span></span>
<span data-ttu-id="9e645-237">Standardmäßig ruft **Get-Job** alle Aufträge in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="9e645-237">By default, **Get-Job** gets all jobs in the current session.</span></span>

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

### <span data-ttu-id="9e645-238">-Latest</span><span class="sxs-lookup"><span data-stu-id="9e645-238">-Newest</span></span>

<span data-ttu-id="9e645-239">Gibt eine Anzahl von Aufträgen an, die erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="9e645-239">Specifies a number of jobs to get.</span></span>
<span data-ttu-id="9e645-240">Dieses Cmdlet ruft die Aufträge ab, die zuletzt beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="9e645-240">This cmdlet gets the jobs that ended most recently.</span></span>

<span data-ttu-id="9e645-241">Die letzten Aufträge werden vom *Newest* -Parameter nicht in der Reihenfolge ihrer Endezeit sortiert oder zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9e645-241">The *Newest* parameter does not sort or return the newest jobs in end-time order.</span></span>
<span data-ttu-id="9e645-242">Um die Ausgabe zu sortieren, verwenden Sie das Cmdlet "Sort-Object".</span><span class="sxs-lookup"><span data-stu-id="9e645-242">To sort the output, use the Sort-Object cmdlet.</span></span>

<span data-ttu-id="9e645-243">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9e645-243">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e645-244">-State</span><span class="sxs-lookup"><span data-stu-id="9e645-244">-State</span></span>

<span data-ttu-id="9e645-245">Gibt einen Auftragsstatus an.</span><span class="sxs-lookup"><span data-stu-id="9e645-245">Specifies a job state.</span></span>
<span data-ttu-id="9e645-246">Dieses Cmdlet ruft nur Aufträge im angegebenen Zustand ab.</span><span class="sxs-lookup"><span data-stu-id="9e645-246">This cmdlet gets only jobs in the specified state.</span></span>
<span data-ttu-id="9e645-247">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="9e645-247">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9e645-248">NotStarted</span><span class="sxs-lookup"><span data-stu-id="9e645-248">NotStarted</span></span>
- <span data-ttu-id="9e645-249">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="9e645-249">Running</span></span>
- <span data-ttu-id="9e645-250">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="9e645-250">Completed</span></span>
- <span data-ttu-id="9e645-251">Fehler</span><span class="sxs-lookup"><span data-stu-id="9e645-251">Failed</span></span>
- <span data-ttu-id="9e645-252">Beendet</span><span class="sxs-lookup"><span data-stu-id="9e645-252">Stopped</span></span>
- <span data-ttu-id="9e645-253">Blockiert</span><span class="sxs-lookup"><span data-stu-id="9e645-253">Blocked</span></span>
- <span data-ttu-id="9e645-254">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="9e645-254">Suspended</span></span>
- <span data-ttu-id="9e645-255">Getrennt</span><span class="sxs-lookup"><span data-stu-id="9e645-255">Disconnected</span></span>
- <span data-ttu-id="9e645-256">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="9e645-256">Suspending</span></span>
- <span data-ttu-id="9e645-257">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="9e645-257">Stopping</span></span>

<span data-ttu-id="9e645-258">Standardmäßig ruft **Get-Job** alle Aufträge in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="9e645-258">By default, **Get-Job** gets all the jobs in the current session.</span></span>

<span data-ttu-id="9e645-259">Weitere Informationen zu Auftrags Zuständen finden Sie unter [jobstate-Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="9e645-259">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="9e645-260">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9e645-260">CommonParameters</span></span>

<span data-ttu-id="9e645-261">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9e645-261">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9e645-262">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9e645-262">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9e645-263">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9e645-263">INPUTS</span></span>

### <span data-ttu-id="9e645-264">Keine</span><span class="sxs-lookup"><span data-stu-id="9e645-264">None</span></span>

<span data-ttu-id="9e645-265">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="9e645-265">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="9e645-266">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9e645-266">OUTPUTS</span></span>

### <span data-ttu-id="9e645-267">System. Management. Automation. remotingjob</span><span class="sxs-lookup"><span data-stu-id="9e645-267">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="9e645-268">Dieses Cmdlet gibt Objekte zurück, die die Aufträge in der Sitzung darstellen.</span><span class="sxs-lookup"><span data-stu-id="9e645-268">This cmdlet returns objects that represent the jobs in the session.</span></span>

## <span data-ttu-id="9e645-269">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9e645-269">NOTES</span></span>

* <span data-ttu-id="9e645-270">Die **PSJobTypeName** -Eigenschaft von Aufträgen gibt den Auftragstyp des Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="9e645-270">The **PSJobTypeName** property of jobs indicates the job type of the job.</span></span> <span data-ttu-id="9e645-271">Der Eigenschaftswert wird vom Autor des Auftragstyps bestimmt.</span><span class="sxs-lookup"><span data-stu-id="9e645-271">The property value is determined by the job type author.</span></span> <span data-ttu-id="9e645-272">Die folgende Liste enthält allgemeine Auftragstypen.</span><span class="sxs-lookup"><span data-stu-id="9e645-272">The following list shows common job types.</span></span>

  - <span data-ttu-id="9e645-273">**Backgroundjob** .</span><span class="sxs-lookup"><span data-stu-id="9e645-273">**BackgroundJob** .</span></span>
<span data-ttu-id="9e645-274">Lokaler Auftrag wurde mithilfe von **Start-Job** gestartet.</span><span class="sxs-lookup"><span data-stu-id="9e645-274">Local job started by using **Start-Job** .</span></span>

  - <span data-ttu-id="9e645-275">**Remotejob** .</span><span class="sxs-lookup"><span data-stu-id="9e645-275">**RemoteJob** .</span></span>
<span data-ttu-id="9e645-276">Der Auftrag wurde in einer **PSSession** mithilfe des *AsJob* -Parameters des Invoke-Command-Cmdlets gestartet.</span><span class="sxs-lookup"><span data-stu-id="9e645-276">Job started in a **PSSession** by using the *AsJob* parameter of the Invoke-Command cmdlet.</span></span>

  - <span data-ttu-id="9e645-277">**Psworkflowjob** .</span><span class="sxs-lookup"><span data-stu-id="9e645-277">**PSWorkflowJob** .</span></span>
<span data-ttu-id="9e645-278">Auftrag, der mit dem allgemeinen *AsJob* -Parameter von Workflows gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="9e645-278">Job started by using the *AsJob* common parameter of workflows.</span></span>

## <span data-ttu-id="9e645-279">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9e645-279">RELATED LINKS</span></span>

[<span data-ttu-id="9e645-280">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="9e645-280">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="9e645-281">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="9e645-281">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="9e645-282">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="9e645-282">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="9e645-283">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="9e645-283">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="9e645-284">Start-Job</span><span class="sxs-lookup"><span data-stu-id="9e645-284">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="9e645-285">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="9e645-285">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="9e645-286">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="9e645-286">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="9e645-287">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="9e645-287">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="9e645-288">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="9e645-288">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="9e645-289">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="9e645-289">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="9e645-290">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="9e645-290">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)

[<span data-ttu-id="9e645-291">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="9e645-291">about_Scheduled_Jobs</span></span>](../PSScheduledJob/About/about_Scheduled_Jobs.md)
