---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Job
ms.openlocfilehash: 52613dae3ba73227818c6c0dec40183ba20ce2a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603721"
---
# <span data-ttu-id="15510-102">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="15510-102">Remove-Job</span></span>

## <span data-ttu-id="15510-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="15510-103">SYNOPSIS</span></span>
<span data-ttu-id="15510-104">Löscht einen PowerShell-Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="15510-104">Deletes a PowerShell background job.</span></span>

## <span data-ttu-id="15510-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="15510-105">SYNTAX</span></span>

### <span data-ttu-id="15510-106">Sessionidparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="15510-106">SessionIdParameterSet (Default)</span></span>

```
Remove-Job [-Force] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="15510-107">Jobparameterset</span><span class="sxs-lookup"><span data-stu-id="15510-107">JobParameterSet</span></span>

```
Remove-Job [-Job] <Job[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="15510-108">Nameparameterset</span><span class="sxs-lookup"><span data-stu-id="15510-108">NameParameterSet</span></span>

```
Remove-Job [-Force] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="15510-109">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="15510-109">InstanceIdParameterSet</span></span>

```
Remove-Job [-Force] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="15510-110">Filterparameterset</span><span class="sxs-lookup"><span data-stu-id="15510-110">FilterParameterSet</span></span>

```
Remove-Job [-Force] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="15510-111">Stateparameterset</span><span class="sxs-lookup"><span data-stu-id="15510-111">StateParameterSet</span></span>

```
Remove-Job [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="15510-112">Commandparameterset</span><span class="sxs-lookup"><span data-stu-id="15510-112">CommandParameterSet</span></span>

```
Remove-Job [-Command <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="15510-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="15510-113">DESCRIPTION</span></span>

<span data-ttu-id="15510-114">Das- `Remove-Job` Cmdlet löscht PowerShell-Hintergrund Aufträge, die durch das- `Start-Job` Cmdlet oder durch Cmdlets gestartet wurden `Invoke-Command` , z. b., die den **AsJob** -Parameter unterstützen.</span><span class="sxs-lookup"><span data-stu-id="15510-114">The `Remove-Job` cmdlet deletes PowerShell background jobs that were started by the `Start-Job` cmdlet or by cmdlets such as `Invoke-Command` that support the **AsJob** parameter.</span></span>

<span data-ttu-id="15510-115">Sie können verwenden `Remove-Job` , um alle Aufträge zu löschen oder ausgewählte Aufträge zu löschen.</span><span class="sxs-lookup"><span data-stu-id="15510-115">You can use `Remove-Job` to delete all jobs or delete selected jobs.</span></span> <span data-ttu-id="15510-116">Die Aufträge werden anhand Ihres **namens**, der **ID**, der **Instanz-ID**, des **Befehls** oder des **Zustands** identifiziert.</span><span class="sxs-lookup"><span data-stu-id="15510-116">The jobs are identified by their **Name**, **ID**, **Instance ID**, **Command**, or **State**.</span></span> <span data-ttu-id="15510-117">Oder ein Job-Objekt kann über die Pipeline an gesendet werden `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="15510-117">Or, a job object can be sent down the pipeline to `Remove-Job`.</span></span> <span data-ttu-id="15510-118">Ohne Parameter oder Parameterwerte `Remove-Job` hat keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="15510-118">Without parameters or parameter values, `Remove-Job` has no effect.</span></span>

<span data-ttu-id="15510-119">Seit PowerShell 3,0 `Remove-Job` können benutzerdefinierte Auftrags Typen, z. b. geplante Aufträge und Workflow Aufträge, löschen.</span><span class="sxs-lookup"><span data-stu-id="15510-119">Since PowerShell 3.0, `Remove-Job` can delete custom job types, such as scheduled jobs and workflow jobs.</span></span> <span data-ttu-id="15510-120">`Remove-Job`Löscht z. b. den geplanten Auftrag, alle Instanzen des geplanten Auftrags auf dem Datenträger und die Ergebnisse aller ausgelösten Auftrags Instanzen.</span><span class="sxs-lookup"><span data-stu-id="15510-120">For example, `Remove-Job` deletes the scheduled job, all instances of the scheduled job on disk, and the results of all triggered job instances.</span></span>

<span data-ttu-id="15510-121">Wenn Sie versuchen, einen laufenden Auftrag zu löschen, `Remove-Job` schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="15510-121">If you try to delete a running job, `Remove-Job` fails.</span></span> <span data-ttu-id="15510-122">Verwenden `Stop-Job` Sie das Cmdlet, um einen laufenden Auftrag zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="15510-122">Use the `Stop-Job` cmdlet to stop a running job.</span></span> <span data-ttu-id="15510-123">Sie können auch `Remove-Job` mit dem **Force** -Parameter verwenden, um einen laufenden Auftrag zu löschen.</span><span class="sxs-lookup"><span data-stu-id="15510-123">Or, use `Remove-Job` with the **Force** parameter to delete a running job.</span></span>

<span data-ttu-id="15510-124">Aufträge verbleiben im globalen Auftrags Cache, bis Sie den Hintergrund Auftrag löschen oder die PowerShell-Sitzung schließen.</span><span class="sxs-lookup"><span data-stu-id="15510-124">Jobs remain in the global job cache until you delete the background job or close the PowerShell session.</span></span>

## <span data-ttu-id="15510-125">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="15510-125">EXAMPLES</span></span>

### <span data-ttu-id="15510-126">Beispiel 1: Löschen eines Auftrags mithilfe des Namens</span><span class="sxs-lookup"><span data-stu-id="15510-126">Example 1: Delete a job by using its name</span></span>

<span data-ttu-id="15510-127">In diesem Beispiel wird eine-Variable und die-Pipeline verwendet, um einen Auftrag anhand des Namens zu löschen.</span><span class="sxs-lookup"><span data-stu-id="15510-127">This example uses a variable and the pipeline to delete a job by name.</span></span>

```powershell
$batch = Get-Job -Name BatchJob
$batch | Remove-Job
```

<span data-ttu-id="15510-128">`Get-Job` verwendet den **Name** -Parameter, um den Auftrag, **Batchjob**, anzugeben.</span><span class="sxs-lookup"><span data-stu-id="15510-128">`Get-Job` uses the **Name** parameter to specify the job, **BatchJob**.</span></span> <span data-ttu-id="15510-129">Das Auftrags Objekt wird in der `$batch` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="15510-129">The job object is stored in the `$batch` variable.</span></span> <span data-ttu-id="15510-130">Das-Objekt in `$batch` wird über die Pipeline an gesendet `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="15510-130">The object in `$batch` is sent down the pipeline to `Remove-Job`.</span></span>

<span data-ttu-id="15510-131">Eine Alternative besteht darin, den **Job** -Parameter zu verwenden, z `Remove-Job -Job $batch` . b..</span><span class="sxs-lookup"><span data-stu-id="15510-131">An alternative is to use the **Job** parameter, such as `Remove-Job -Job $batch`.</span></span>

### <span data-ttu-id="15510-132">Beispiel 2: Löschen aller Aufträge in einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="15510-132">Example 2: Delete all jobs in a session</span></span>

<span data-ttu-id="15510-133">In diesem Beispiel werden alle Aufträge in der aktuellen PowerShell-Sitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="15510-133">In this example, all the jobs in the current PowerShell session are deleted.</span></span>

```powershell
Get-job | Remove-Job
```

<span data-ttu-id="15510-134">`Get-Job` Ruft alle Aufträge in der aktuellen PowerShell-Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="15510-134">`Get-Job` gets all the jobs in the current PowerShell session.</span></span> <span data-ttu-id="15510-135">Die Auftrags Objekte werden über die Pipeline an gesendet `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="15510-135">The job objects are sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="15510-136">Beispiel 3: Löschen von notstarted-Aufträgen</span><span class="sxs-lookup"><span data-stu-id="15510-136">Example 3: Delete NotStarted jobs</span></span>

<span data-ttu-id="15510-137">In diesem Beispiel werden alle Aufträge aus der aktuellen PowerShell-Sitzung gelöscht, die noch nicht gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="15510-137">This example deletes all jobs from the current PowerShell session that haven't started.</span></span>

```powershell
Remove-Job -State NotStarted
```

<span data-ttu-id="15510-138">`Remove-Job` verwendet den **State** -Parameter, um den Auftragsstatus anzugeben.</span><span class="sxs-lookup"><span data-stu-id="15510-138">`Remove-Job` uses the **State** parameter to specify the job status.</span></span>

### <span data-ttu-id="15510-139">Beispiel 4: Löschen von Aufträgen mit einem anzeigen Amen</span><span class="sxs-lookup"><span data-stu-id="15510-139">Example 4: Delete jobs by using a friendly name</span></span>

<span data-ttu-id="15510-140">In diesem Beispiel werden alle Aufträge aus der aktuellen Sitzung mit anzeigen Amen gelöscht, die auf \* Batch \* \* enden, einschließlich der Aufträge, die ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="15510-140">This example deletes all jobs from the current session with friendly names that end with \*batch\*\*, including jobs that are running.</span></span>

```powershell
Remove-Job -Name *batch -Force
```

<span data-ttu-id="15510-141">`Remove-Job` verwendet den **Name** -Parameter, um ein Auftrags Namensmuster anzugeben.</span><span class="sxs-lookup"><span data-stu-id="15510-141">`Remove-Job` uses the **Name** parameter to specify a job name pattern.</span></span> <span data-ttu-id="15510-142">Das Muster enthält das Platzhalter Zeichen ( `*` ), um alle Auftrags Namen zu suchen, die mit **Batch** enden.</span><span class="sxs-lookup"><span data-stu-id="15510-142">The pattern includes the asterisk (`*`) wildcard to find all job names that end with **batch**.</span></span> <span data-ttu-id="15510-143">Der **Force** -Parameter löscht Aufträge, die ausführen.</span><span class="sxs-lookup"><span data-stu-id="15510-143">The **Force** parameter deletes jobs that running.</span></span>

### <span data-ttu-id="15510-144">Beispiel 5: Löschen eines Auftrags, der von Invoke-Command erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="15510-144">Example 5: Delete a job that was created by Invoke-Command</span></span>

<span data-ttu-id="15510-145">In diesem Beispiel wird ein Auftrag, der auf einem Remote Computer mithilfe von `Invoke-Command` mit dem **AsJob** -Parameter gestartet wurde, entfernt.</span><span class="sxs-lookup"><span data-stu-id="15510-145">This example removes a job that was started on a remote computer using `Invoke-Command` with the **AsJob** parameter.</span></span>

<span data-ttu-id="15510-146">Da im Beispiel der **AsJob** -Parameter verwendet wird, wird das Auftrags Objekt auf dem lokalen Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="15510-146">Because the example uses the **AsJob** parameter, the job object is created on the local computer.</span></span>
<span data-ttu-id="15510-147">Der Auftrag wird jedoch auf einem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="15510-147">But, the job runs on a remote computer.</span></span> <span data-ttu-id="15510-148">Folglich verwenden Sie lokale Befehle, um den Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="15510-148">As a result, you use local commands to manage the job.</span></span>

```powershell
$job = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Process} -AsJob
$job | Remove-Job
```

<span data-ttu-id="15510-149">`Invoke-Command` führt einen Auftrag auf dem **Server01** -Computer aus.</span><span class="sxs-lookup"><span data-stu-id="15510-149">`Invoke-Command` runs a job on the **Server01** computer.</span></span> <span data-ttu-id="15510-150">Der **AsJob** -Parameter führt den **ScriptBlock** als Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="15510-150">The **AsJob** parameter runs the **ScriptBlock** as a background job.</span></span> <span data-ttu-id="15510-151">Das Auftrags Objekt wird in der `$job` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="15510-151">The job object is stored in the `$job` variable.</span></span> <span data-ttu-id="15510-152">Das `$job` Variablen Objekt wird über die Pipeline an gesendet `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="15510-152">The `$job` variable object is sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="15510-153">Beispiel 6: Löschen eines Auftrags, der von Invoke-Command erstellt wurde, und Start-Job</span><span class="sxs-lookup"><span data-stu-id="15510-153">Example 6: Delete a job that was created by Invoke-Command and Start-Job</span></span>

<span data-ttu-id="15510-154">In diesem Beispiel wird gezeigt, wie ein Auftrag auf einem Remote Computer entfernt wird, der mithilfe von zum Ausführen von gestartet wurde `Invoke-Command` `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="15510-154">This example shows how to remove a job on a remote computer that was started by using `Invoke-Command` to run `Start-Job`.</span></span> <span data-ttu-id="15510-155">Das Auftrags Objekt wird auf dem Remote Computer erstellt, und Remote Befehle werden zum Verwalten des Auftrags verwendet.</span><span class="sxs-lookup"><span data-stu-id="15510-155">The job object is created on the remote computer and remote commands are used to manage the job.</span></span> <span data-ttu-id="15510-156">Eine permanente Verbindung ist erforderlich, wenn ein Remote `Start-Job` Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="15510-156">A persistent connection is required when running a remote `Start-Job` command.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -ScriptBlock {Start-Job -ScriptBlock {Get-Process} -Name MyJob}
Invoke-Command -Session $S -ScriptBlock {Remove-Job -Name MyJob}
```

<span data-ttu-id="15510-157">`New-PSSession` erstellt eine **PSSession**, eine permanente Verbindung, mit dem **Server01** -Computer.</span><span class="sxs-lookup"><span data-stu-id="15510-157">`New-PSSession` creates a **PSSession**, a persistent connection, to the **Server01** computer.</span></span> <span data-ttu-id="15510-158">Die Verbindung wird in der `$S` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="15510-158">The connection is saved in the `$S` variable.</span></span>

<span data-ttu-id="15510-159">`Invoke-Command` stellt eine Verbindung mit der in gespeicherten Sitzung her `$S` .</span><span class="sxs-lookup"><span data-stu-id="15510-159">`Invoke-Command` connects to the session saved in `$S`.</span></span> <span data-ttu-id="15510-160">Der **ScriptBlock** verwendet `Start-Job` , um einen Remote Auftrag zu starten.</span><span class="sxs-lookup"><span data-stu-id="15510-160">The **ScriptBlock** uses `Start-Job` to start a remote job.</span></span> <span data-ttu-id="15510-161">Der Auftrag führt einen `Get-Process` Befehl aus und verwendet den **Name** -Parameter, um den anzeigen Amen **MyJob** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="15510-161">The job runs a `Get-Process` command and uses the **Name** parameter to specify a friendly job name, **MyJob**.</span></span>

<span data-ttu-id="15510-162">`Invoke-Command` verwendet die `$S` Sitzung und führt Sie aus `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="15510-162">`Invoke-Command` uses the `$S` session and runs `Remove-Job`.</span></span> <span data-ttu-id="15510-163">Der **Name** -Parameter gibt an, dass der Auftrag mit dem Namen **MyJob** gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="15510-163">The **Name** parameter specifies that the job named **MyJob** is deleted.</span></span>

### <span data-ttu-id="15510-164">Beispiel 7: Löschen eines Auftrags mithilfe der InstanceId</span><span class="sxs-lookup"><span data-stu-id="15510-164">Example 7: Delete a job by using its InstanceId</span></span>

<span data-ttu-id="15510-165">In diesem Beispiel wird ein Auftrag basierend auf seiner **InstanceId** entfernt.</span><span class="sxs-lookup"><span data-stu-id="15510-165">This example removes a job based on its **InstanceId**.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process PowerShell}
$job | Format-List -Property *
Remove-Job -InstanceId ad02b942-8007-4407-87f3-d23e71955872
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-Process PowerShell
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : ad02b942-8007-4407-87f3-d23e71955872
Id            : 3
Name          : Job3
ChildJobs     : {Job4}
PSBeginTime   : 7/26/2019 11:36:56
PSEndTime     : 7/26/2019 11:36:57
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

<span data-ttu-id="15510-166">`Start-Job` startet einen Hintergrund Auftrag, und das Auftrags Objekt wird in der `$job` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="15510-166">`Start-Job` starts a background job and the job object is saved in the `$job` variable.</span></span>

<span data-ttu-id="15510-167">Das-Objekt in `$job` wird über die Pipeline an gesendet `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="15510-167">The object in `$job` is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="15510-168">Der **Property** -Parameter verwendet ein Sternchen ( `*` ), um anzugeben, dass alle Eigenschaften des Objekts in einer Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="15510-168">The **Property** parameter uses an asterisk (`*`) to specify that all the object's properties are displayed in a list.</span></span>

<span data-ttu-id="15510-169">`Remove-Job` verwendet den **InstanceId-** Parameter, um den Auftrag anzugeben, der gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="15510-169">`Remove-Job` uses the **InstanceId** parameter to specify the job to delete.</span></span>

## <span data-ttu-id="15510-170">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="15510-170">PARAMETERS</span></span>

### <span data-ttu-id="15510-171">-Command</span><span class="sxs-lookup"><span data-stu-id="15510-171">-Command</span></span>

<span data-ttu-id="15510-172">Löscht Aufträge, die die im Befehl angegebenen Wörter enthalten.</span><span class="sxs-lookup"><span data-stu-id="15510-172">Deletes jobs that include the specified words in the command.</span></span> <span data-ttu-id="15510-173">Sie können ein Komma getrenntes Array eingeben.</span><span class="sxs-lookup"><span data-stu-id="15510-173">You can enter a comma-separated array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="15510-174">-Confirm</span><span class="sxs-lookup"><span data-stu-id="15510-174">-Confirm</span></span>

<span data-ttu-id="15510-175">Fordert Sie zur Bestätigung auf, bevor `Remove-Job` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="15510-175">Prompts you for confirmation before `Remove-Job` is run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15510-176">-Filter</span><span class="sxs-lookup"><span data-stu-id="15510-176">-Filter</span></span>

<span data-ttu-id="15510-177">Löscht Aufträge, die alle in der zugeordneten Hash Tabelle festgelegten Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="15510-177">Deletes jobs that satisfy all the conditions established in the associated hash table.</span></span> <span data-ttu-id="15510-178">Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="15510-178">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="15510-179">Dieser Parameter funktioniert nur mit benutzerdefinierten Auftragstypen, z. B. Workflowaufträgen und geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="15510-179">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="15510-180">Es funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, z. b. bei den mit erstellten `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="15510-180">It doesn't work on standard background jobs, such as those created by using the `Start-Job`.</span></span>

<span data-ttu-id="15510-181">Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="15510-181">This parameter is introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="15510-182">-Force</span><span class="sxs-lookup"><span data-stu-id="15510-182">-Force</span></span>

<span data-ttu-id="15510-183">Löscht einen Auftrag, auch wenn der Status des Auftrags "wird **ausgeführt**" lautet.</span><span class="sxs-lookup"><span data-stu-id="15510-183">Deletes a job even if the job's state is **Running**.</span></span> <span data-ttu-id="15510-184">Wenn der **Force** -Parameter nicht angegeben wird, werden `Remove-Job` keine laufenden Aufträge gelöscht.</span><span class="sxs-lookup"><span data-stu-id="15510-184">If the **Force** parameter isn't specified, `Remove-Job` doesn't delete running jobs.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, JobParameterSet, InstanceIdParameterSet, NameParameterSet, FilterParameterSet
Aliases: F

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15510-185">-Id</span><span class="sxs-lookup"><span data-stu-id="15510-185">-Id</span></span>

<span data-ttu-id="15510-186">Löscht Hintergrund Aufträge mit der angegebenen **ID**. Sie können ein Komma getrenntes Array eingeben.</span><span class="sxs-lookup"><span data-stu-id="15510-186">Deletes background jobs with the specified **Id**. You can enter a comma-separated array.</span></span> <span data-ttu-id="15510-187">Die Auftrags- **ID** ist eine eindeutige ganze Zahl, die einen Auftrag innerhalb der aktuellen Sitzung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="15510-187">The job's **Id** is a unique integer that identifies a job within the current session.</span></span>

<span data-ttu-id="15510-188">Um die **ID** eines Auftrags zu ermitteln, verwenden Sie `Get-Job` ohne Parameter.</span><span class="sxs-lookup"><span data-stu-id="15510-188">To find a job's **Id**, use `Get-Job` without parameters.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="15510-189">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="15510-189">-InstanceId</span></span>

<span data-ttu-id="15510-190">Löscht Aufträge mit der angegebenen **InstanceId**.</span><span class="sxs-lookup"><span data-stu-id="15510-190">Deletes jobs with the specified **InstanceId**.</span></span> <span data-ttu-id="15510-191">Sie können ein Komma getrenntes Array eingeben.</span><span class="sxs-lookup"><span data-stu-id="15510-191">You can enter a comma-separated array.</span></span> <span data-ttu-id="15510-192">Eine **InstanceId** ist eine eindeutige GUID, die einen Auftrag identifiziert.</span><span class="sxs-lookup"><span data-stu-id="15510-192">An **InstanceId** is a unique GUID that identifies a job.</span></span>

<span data-ttu-id="15510-193">Um die **InstanceId** eines Auftrags zu ermitteln, verwenden Sie `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="15510-193">To find a job's **InstanceId**, use `Get-Job`.</span></span>

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

### <span data-ttu-id="15510-194">-Auftrag</span><span class="sxs-lookup"><span data-stu-id="15510-194">-Job</span></span>

<span data-ttu-id="15510-195">Gibt die zu löschenden Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="15510-195">Specifies the jobs to be deleted.</span></span> <span data-ttu-id="15510-196">Geben Sie eine Variable ein, die entweder die Aufträge oder einen Befehl enthält, durch den die Aufträge abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="15510-196">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="15510-197">Sie können ein Komma getrenntes Array eingeben.</span><span class="sxs-lookup"><span data-stu-id="15510-197">You can enter a comma-separated array.</span></span>

<span data-ttu-id="15510-198">Sie können Auftrags Objekte über die Pipeline an senden `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="15510-198">You can send job objects down the pipeline to `Remove-Job`.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="15510-199">-Name</span><span class="sxs-lookup"><span data-stu-id="15510-199">-Name</span></span>

<span data-ttu-id="15510-200">Löscht nur Aufträge mit dem angegebenen anzeigen Amen.</span><span class="sxs-lookup"><span data-stu-id="15510-200">Only deletes jobs with the specified friendly name.</span></span> <span data-ttu-id="15510-201">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="15510-201">Wildcards are permitted.</span></span> <span data-ttu-id="15510-202">Sie können ein Komma getrenntes Array eingeben.</span><span class="sxs-lookup"><span data-stu-id="15510-202">You can enter a comma-separated array.</span></span>

<span data-ttu-id="15510-203">Anzeigen Amen für Aufträge sind nicht garantiert eindeutig, auch innerhalb einer PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="15510-203">Friendly names for jobs aren't guaranteed to be unique, even within a PowerShell session.</span></span> <span data-ttu-id="15510-204">Verwenden Sie die Parameter " **WhatIf** " und " **Confirm** ", wenn Sie Dateien nach Namen löschen.</span><span class="sxs-lookup"><span data-stu-id="15510-204">Use the **WhatIf** and **Confirm** parameters when you delete files by name.</span></span>

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

### <span data-ttu-id="15510-205">-State</span><span class="sxs-lookup"><span data-stu-id="15510-205">-State</span></span>

<span data-ttu-id="15510-206">Löscht nur Aufträge mit dem angegebenen Zustand.</span><span class="sxs-lookup"><span data-stu-id="15510-206">Only deletes jobs with the specified state.</span></span> <span data-ttu-id="15510-207">Verwenden Sie den **Force** -Parameter, um Aufträge mit dem Status "wird **ausgeführt**" zu löschen.</span><span class="sxs-lookup"><span data-stu-id="15510-207">To delete jobs with a state of **Running**, use the **Force** parameter.</span></span>

<span data-ttu-id="15510-208">Akzeptierte Werte:</span><span class="sxs-lookup"><span data-stu-id="15510-208">Accepted values:</span></span>

- <span data-ttu-id="15510-209">"Atbreakpoint"</span><span class="sxs-lookup"><span data-stu-id="15510-209">AtBreakpoint</span></span>
- <span data-ttu-id="15510-210">Gesperrt</span><span class="sxs-lookup"><span data-stu-id="15510-210">Blocked</span></span>
- <span data-ttu-id="15510-211">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="15510-211">Completed</span></span>
- <span data-ttu-id="15510-212">Getrennt</span><span class="sxs-lookup"><span data-stu-id="15510-212">Disconnected</span></span>
- <span data-ttu-id="15510-213">Fehler</span><span class="sxs-lookup"><span data-stu-id="15510-213">Failed</span></span>
- <span data-ttu-id="15510-214">NotStarted</span><span class="sxs-lookup"><span data-stu-id="15510-214">NotStarted</span></span>
- <span data-ttu-id="15510-215">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="15510-215">Running</span></span>
- <span data-ttu-id="15510-216">Beendet</span><span class="sxs-lookup"><span data-stu-id="15510-216">Stopped</span></span>
- <span data-ttu-id="15510-217">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="15510-217">Stopping</span></span>
- <span data-ttu-id="15510-218">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="15510-218">Suspended</span></span>
- <span data-ttu-id="15510-219">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="15510-219">Suspending</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: AtBreakpoint, Blocked, Completed, Disconnected, Failed, NotStarted, Running, Stopped, Stopping, Suspended, Suspending

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="15510-220">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="15510-220">-WhatIf</span></span>

<span data-ttu-id="15510-221">Zeigt, was geschieht, wenn ausgeführt wird `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="15510-221">Shows what would happen if `Remove-Job` runs.</span></span> <span data-ttu-id="15510-222">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="15510-222">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15510-223">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="15510-223">CommonParameters</span></span>

<span data-ttu-id="15510-224">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="15510-224">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="15510-225">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="15510-225">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="15510-226">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="15510-226">INPUTS</span></span>

### <span data-ttu-id="15510-227">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="15510-227">System.Management.Automation.Job</span></span>

<span data-ttu-id="15510-228">Sie können ein Auftrags Objekt über die Pipeline an senden `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="15510-228">You can send a job object down the pipeline to `Remove-Job`.</span></span>

## <span data-ttu-id="15510-229">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="15510-229">OUTPUTS</span></span>

### <span data-ttu-id="15510-230">Keine</span><span class="sxs-lookup"><span data-stu-id="15510-230">None</span></span>

<span data-ttu-id="15510-231">`Remove-Job` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="15510-231">`Remove-Job` doesn't generate any output.</span></span>

## <span data-ttu-id="15510-232">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="15510-232">NOTES</span></span>

<span data-ttu-id="15510-233">Ein PowerShell-Auftrag erstellt einen neuen Prozess.</span><span class="sxs-lookup"><span data-stu-id="15510-233">A PowerShell job creates a new process.</span></span> <span data-ttu-id="15510-234">Wenn der Auftrag abgeschlossen ist, wird der Prozess beendet.</span><span class="sxs-lookup"><span data-stu-id="15510-234">When the job completes, the process exits.</span></span> <span data-ttu-id="15510-235">Wenn `Remove-Job` ausgeführt wird, wird der Status des Auftrags entfernt.</span><span class="sxs-lookup"><span data-stu-id="15510-235">When `Remove-Job` is run, the job's state is removed.</span></span>

<span data-ttu-id="15510-236">Wenn ein Auftrag vor dem Abschluss beendet wird und der Prozess nicht beendet wurde, wird der Prozess erzwungen.</span><span class="sxs-lookup"><span data-stu-id="15510-236">If a job stops before completion and its process hasn't exited, the process is forcibly terminated.</span></span>

## <span data-ttu-id="15510-237">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="15510-237">RELATED LINKS</span></span>

[<span data-ttu-id="15510-238">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="15510-238">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="15510-239">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="15510-239">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="15510-240">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="15510-240">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="15510-241">Get-Job</span><span class="sxs-lookup"><span data-stu-id="15510-241">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="15510-242">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="15510-242">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="15510-243">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="15510-243">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="15510-244">Start-Job</span><span class="sxs-lookup"><span data-stu-id="15510-244">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="15510-245">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="15510-245">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="15510-246">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="15510-246">Wait-Job</span></span>](Wait-Job.md)

