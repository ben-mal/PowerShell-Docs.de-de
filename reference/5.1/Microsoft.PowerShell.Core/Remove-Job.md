---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Job
ms.openlocfilehash: 589c43c814d5d68e57fd20226c675bf0f9587b69
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212791"
---
# <span data-ttu-id="c6245-103">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="c6245-103">Remove-Job</span></span>

## <span data-ttu-id="c6245-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c6245-104">SYNOPSIS</span></span>
<span data-ttu-id="c6245-105">Löscht einen PowerShell-Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="c6245-105">Deletes a PowerShell background job.</span></span>

## <span data-ttu-id="c6245-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c6245-106">SYNTAX</span></span>

### <span data-ttu-id="c6245-107">Sessionidparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="c6245-107">SessionIdParameterSet (Default)</span></span>

```
Remove-Job [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c6245-108">Jobparameterset</span><span class="sxs-lookup"><span data-stu-id="c6245-108">JobParameterSet</span></span>

```
Remove-Job [-Job] <Job[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c6245-109">Nameparameterset</span><span class="sxs-lookup"><span data-stu-id="c6245-109">NameParameterSet</span></span>

```
Remove-Job [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c6245-110">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="c6245-110">InstanceIdParameterSet</span></span>

```
Remove-Job [-InstanceId] <Guid[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c6245-111">Filterparameterset</span><span class="sxs-lookup"><span data-stu-id="c6245-111">FilterParameterSet</span></span>

```
Remove-Job [-Filter] <Hashtable> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c6245-112">Stateparameterset</span><span class="sxs-lookup"><span data-stu-id="c6245-112">StateParameterSet</span></span>

```
Remove-Job [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c6245-113">Commandparameterset</span><span class="sxs-lookup"><span data-stu-id="c6245-113">CommandParameterSet</span></span>

```
Remove-Job [-Command <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c6245-114">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c6245-114">DESCRIPTION</span></span>

<span data-ttu-id="c6245-115">Das- `Remove-Job` Cmdlet löscht PowerShell-Hintergrund Aufträge, die durch das- `Start-Job` Cmdlet oder durch Cmdlets gestartet wurden `Invoke-Command` , z. b., die den **AsJob** -Parameter unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c6245-115">The `Remove-Job` cmdlet deletes PowerShell background jobs that were started by the `Start-Job` cmdlet or by cmdlets such as `Invoke-Command` that support the **AsJob** parameter.</span></span>

<span data-ttu-id="c6245-116">Sie können verwenden `Remove-Job` , um alle Aufträge zu löschen oder ausgewählte Aufträge zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c6245-116">You can use `Remove-Job` to delete all jobs or delete selected jobs.</span></span> <span data-ttu-id="c6245-117">Die Aufträge werden anhand Ihres **namens** , der **ID** , der **Instanz-ID** , des **Befehls** oder des **Zustands** identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c6245-117">The jobs are identified by their **Name** , **ID** , **Instance ID** , **Command** , or **State** .</span></span> <span data-ttu-id="c6245-118">Oder ein Job-Objekt kann über die Pipeline an gesendet werden `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="c6245-118">Or, a job object can be sent down the pipeline to `Remove-Job`.</span></span> <span data-ttu-id="c6245-119">Ohne Parameter oder Parameterwerte `Remove-Job` hat keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="c6245-119">Without parameters or parameter values, `Remove-Job` has no effect.</span></span>

<span data-ttu-id="c6245-120">Seit PowerShell 3,0 `Remove-Job` können benutzerdefinierte Auftrags Typen, z. b. geplante Aufträge und Workflow Aufträge, löschen.</span><span class="sxs-lookup"><span data-stu-id="c6245-120">Since PowerShell 3.0, `Remove-Job` can delete custom job types, such as scheduled jobs and workflow jobs.</span></span> <span data-ttu-id="c6245-121">`Remove-Job`Löscht z. b. den geplanten Auftrag, alle Instanzen des geplanten Auftrags auf dem Datenträger und die Ergebnisse aller ausgelösten Auftrags Instanzen.</span><span class="sxs-lookup"><span data-stu-id="c6245-121">For example, `Remove-Job` deletes the scheduled job, all instances of the scheduled job on disk, and the results of all triggered job instances.</span></span>

<span data-ttu-id="c6245-122">Wenn Sie versuchen, einen laufenden Auftrag zu löschen, `Remove-Job` schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="c6245-122">If you try to delete a running job, `Remove-Job` fails.</span></span> <span data-ttu-id="c6245-123">Verwenden `Stop-Job` Sie das Cmdlet, um einen laufenden Auftrag zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="c6245-123">Use the `Stop-Job` cmdlet to stop a running job.</span></span> <span data-ttu-id="c6245-124">Sie können auch `Remove-Job` mit dem **Force** -Parameter verwenden, um einen laufenden Auftrag zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c6245-124">Or, use `Remove-Job` with the **Force** parameter to delete a running job.</span></span>

<span data-ttu-id="c6245-125">Aufträge verbleiben im globalen Auftrags Cache, bis Sie den Hintergrund Auftrag löschen oder die PowerShell-Sitzung schließen.</span><span class="sxs-lookup"><span data-stu-id="c6245-125">Jobs remain in the global job cache until you delete the background job or close the PowerShell session.</span></span>

## <span data-ttu-id="c6245-126">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c6245-126">EXAMPLES</span></span>

### <span data-ttu-id="c6245-127">Beispiel 1: Löschen eines Auftrags mithilfe des Namens</span><span class="sxs-lookup"><span data-stu-id="c6245-127">Example 1: Delete a job by using its name</span></span>

<span data-ttu-id="c6245-128">In diesem Beispiel wird eine-Variable und die-Pipeline verwendet, um einen Auftrag anhand des Namens zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c6245-128">This example uses a variable and the pipeline to delete a job by name.</span></span>

```powershell
$batch = Get-Job -Name BatchJob
$batch | Remove-Job
```

<span data-ttu-id="c6245-129">`Get-Job` verwendet den **Name** -Parameter, um den Auftrag, **Batchjob** , anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c6245-129">`Get-Job` uses the **Name** parameter to specify the job, **BatchJob** .</span></span> <span data-ttu-id="c6245-130">Das Auftrags Objekt wird in der `$batch` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c6245-130">The job object is stored in the `$batch` variable.</span></span> <span data-ttu-id="c6245-131">Das-Objekt in `$batch` wird über die Pipeline an gesendet `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="c6245-131">The object in `$batch` is sent down the pipeline to `Remove-Job`.</span></span>

<span data-ttu-id="c6245-132">Eine Alternative besteht darin, den **Job** -Parameter zu verwenden, z `Remove-Job -Job $batch` . b..</span><span class="sxs-lookup"><span data-stu-id="c6245-132">An alternative is to use the **Job** parameter, such as `Remove-Job -Job $batch`.</span></span>

### <span data-ttu-id="c6245-133">Beispiel 2: Löschen aller Aufträge in einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="c6245-133">Example 2: Delete all jobs in a session</span></span>

<span data-ttu-id="c6245-134">In diesem Beispiel werden alle Aufträge in der aktuellen PowerShell-Sitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c6245-134">In this example, all the jobs in the current PowerShell session are deleted.</span></span>

```powershell
Get-job | Remove-Job
```

<span data-ttu-id="c6245-135">`Get-Job` Ruft alle Aufträge in der aktuellen PowerShell-Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="c6245-135">`Get-Job` gets all the jobs in the current PowerShell session.</span></span> <span data-ttu-id="c6245-136">Die Auftrags Objekte werden über die Pipeline an gesendet `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="c6245-136">The job objects are sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="c6245-137">Beispiel 3: Löschen von notstarted-Aufträgen</span><span class="sxs-lookup"><span data-stu-id="c6245-137">Example 3: Delete NotStarted jobs</span></span>

<span data-ttu-id="c6245-138">In diesem Beispiel werden alle Aufträge aus der aktuellen PowerShell-Sitzung gelöscht, die noch nicht gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="c6245-138">This example deletes all jobs from the current PowerShell session that haven't started.</span></span>

```powershell
Remove-Job -State NotStarted
```

<span data-ttu-id="c6245-139">`Remove-Job` verwendet den **State** -Parameter, um den Auftragsstatus anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c6245-139">`Remove-Job` uses the **State** parameter to specify the job status.</span></span>

### <span data-ttu-id="c6245-140">Beispiel 4: Löschen von Aufträgen mit einem anzeigen Amen</span><span class="sxs-lookup"><span data-stu-id="c6245-140">Example 4: Delete jobs by using a friendly name</span></span>

<span data-ttu-id="c6245-141">In diesem Beispiel werden alle Aufträge aus der aktuellen Sitzung mit anzeigen Amen gelöscht, die auf \* Batch \* \* enden, einschließlich der Aufträge, die ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c6245-141">This example deletes all jobs from the current session with friendly names that end with \*batch\*\*, including jobs that are running.</span></span>

```powershell
Remove-Job -Name *batch -Force
```

<span data-ttu-id="c6245-142">`Remove-Job` verwendet den **Name** -Parameter, um ein Auftrags Namensmuster anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c6245-142">`Remove-Job` uses the **Name** parameter to specify a job name pattern.</span></span> <span data-ttu-id="c6245-143">Das Muster enthält das Platzhalter Zeichen ( `*` ), um alle Auftrags Namen zu suchen, die mit **Batch** enden.</span><span class="sxs-lookup"><span data-stu-id="c6245-143">The pattern includes the asterisk (`*`) wildcard to find all job names that end with **batch** .</span></span> <span data-ttu-id="c6245-144">Der **Force** -Parameter löscht Aufträge, die ausführen.</span><span class="sxs-lookup"><span data-stu-id="c6245-144">The **Force** parameter deletes jobs that running.</span></span>

### <span data-ttu-id="c6245-145">Beispiel 5: Löschen eines Auftrags, der von Invoke-Command erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="c6245-145">Example 5: Delete a job that was created by Invoke-Command</span></span>

<span data-ttu-id="c6245-146">In diesem Beispiel wird ein Auftrag, der auf einem Remote Computer mithilfe von `Invoke-Command` mit dem **AsJob** -Parameter gestartet wurde, entfernt.</span><span class="sxs-lookup"><span data-stu-id="c6245-146">This example removes a job that was started on a remote computer using `Invoke-Command` with the **AsJob** parameter.</span></span>

<span data-ttu-id="c6245-147">Da im Beispiel der **AsJob** -Parameter verwendet wird, wird das Auftrags Objekt auf dem lokalen Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="c6245-147">Because the example uses the **AsJob** parameter, the job object is created on the local computer.</span></span>
<span data-ttu-id="c6245-148">Der Auftrag wird jedoch auf einem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c6245-148">But, the job runs on a remote computer.</span></span> <span data-ttu-id="c6245-149">Folglich verwenden Sie lokale Befehle, um den Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c6245-149">As a result, you use local commands to manage the job.</span></span>

```powershell
$job = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Process} -AsJob
$job | Remove-Job
```

<span data-ttu-id="c6245-150">`Invoke-Command` führt einen Auftrag auf dem **Server01** -Computer aus.</span><span class="sxs-lookup"><span data-stu-id="c6245-150">`Invoke-Command` runs a job on the **Server01** computer.</span></span> <span data-ttu-id="c6245-151">Der **AsJob** -Parameter führt den **ScriptBlock** als Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="c6245-151">The **AsJob** parameter runs the **ScriptBlock** as a background job.</span></span> <span data-ttu-id="c6245-152">Das Auftrags Objekt wird in der `$job` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c6245-152">The job object is stored in the `$job` variable.</span></span> <span data-ttu-id="c6245-153">Das `$job` Variablen Objekt wird über die Pipeline an gesendet `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="c6245-153">The `$job` variable object is sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="c6245-154">Beispiel 6: Löschen eines Auftrags, der von Invoke-Command erstellt wurde, und Start-Job</span><span class="sxs-lookup"><span data-stu-id="c6245-154">Example 6: Delete a job that was created by Invoke-Command and Start-Job</span></span>

<span data-ttu-id="c6245-155">In diesem Beispiel wird gezeigt, wie ein Auftrag auf einem Remote Computer entfernt wird, der mithilfe von zum Ausführen von gestartet wurde `Invoke-Command` `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="c6245-155">This example shows how to remove a job on a remote computer that was started by using `Invoke-Command` to run `Start-Job`.</span></span> <span data-ttu-id="c6245-156">Das Auftrags Objekt wird auf dem Remote Computer erstellt, und Remote Befehle werden zum Verwalten des Auftrags verwendet.</span><span class="sxs-lookup"><span data-stu-id="c6245-156">The job object is created on the remote computer and remote commands are used to manage the job.</span></span> <span data-ttu-id="c6245-157">Eine permanente Verbindung ist erforderlich, wenn ein Remote `Start-Job` Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c6245-157">A persistent connection is required when running a remote `Start-Job` command.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -ScriptBlock {Start-Job -ScriptBlock {Get-Process} -Name MyJob}
Invoke-Command -Session $S -ScriptBlock {Remove-Job -Name MyJob}
```

<span data-ttu-id="c6245-158">`New-PSSession` erstellt eine **PSSession** , eine permanente Verbindung, mit dem **Server01** -Computer.</span><span class="sxs-lookup"><span data-stu-id="c6245-158">`New-PSSession` creates a **PSSession** , a persistent connection, to the **Server01** computer.</span></span> <span data-ttu-id="c6245-159">Die Verbindung wird in der `$S` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c6245-159">The connection is saved in the `$S` variable.</span></span>

<span data-ttu-id="c6245-160">`Invoke-Command` stellt eine Verbindung mit der in gespeicherten Sitzung her `$S` .</span><span class="sxs-lookup"><span data-stu-id="c6245-160">`Invoke-Command` connects to the session saved in `$S`.</span></span> <span data-ttu-id="c6245-161">Der **ScriptBlock** verwendet `Start-Job` , um einen Remote Auftrag zu starten.</span><span class="sxs-lookup"><span data-stu-id="c6245-161">The **ScriptBlock** uses `Start-Job` to start a remote job.</span></span> <span data-ttu-id="c6245-162">Der Auftrag führt einen `Get-Process` Befehl aus und verwendet den **Name** -Parameter, um den anzeigen Amen **MyJob** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c6245-162">The job runs a `Get-Process` command and uses the **Name** parameter to specify a friendly job name, **MyJob** .</span></span>

<span data-ttu-id="c6245-163">`Invoke-Command` verwendet die `$S` Sitzung und führt Sie aus `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="c6245-163">`Invoke-Command` uses the `$S` session and runs `Remove-Job`.</span></span> <span data-ttu-id="c6245-164">Der **Name** -Parameter gibt an, dass der Auftrag mit dem Namen **MyJob** gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="c6245-164">The **Name** parameter specifies that the job named **MyJob** is deleted.</span></span>

### <span data-ttu-id="c6245-165">Beispiel 7: Löschen eines Auftrags mithilfe der InstanceId</span><span class="sxs-lookup"><span data-stu-id="c6245-165">Example 7: Delete a job by using its InstanceId</span></span>

<span data-ttu-id="c6245-166">In diesem Beispiel wird ein Auftrag basierend auf seiner **InstanceId** entfernt.</span><span class="sxs-lookup"><span data-stu-id="c6245-166">This example removes a job based on its **InstanceId** .</span></span>

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

<span data-ttu-id="c6245-167">`Start-Job` startet einen Hintergrund Auftrag, und das Auftrags Objekt wird in der `$job` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c6245-167">`Start-Job` starts a background job and the job object is saved in the `$job` variable.</span></span>

<span data-ttu-id="c6245-168">Das-Objekt in `$job` wird über die Pipeline an gesendet `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="c6245-168">The object in `$job` is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="c6245-169">Der **Property** -Parameter verwendet ein Sternchen ( `*` ), um anzugeben, dass alle Eigenschaften des Objekts in einer Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c6245-169">The **Property** parameter uses an asterisk (`*`) to specify that all the object's properties are displayed in a list.</span></span>

<span data-ttu-id="c6245-170">`Remove-Job` verwendet den **InstanceId-** Parameter, um den Auftrag anzugeben, der gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="c6245-170">`Remove-Job` uses the **InstanceId** parameter to specify the job to delete.</span></span>

## <span data-ttu-id="c6245-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c6245-171">PARAMETERS</span></span>

### <span data-ttu-id="c6245-172">-Command</span><span class="sxs-lookup"><span data-stu-id="c6245-172">-Command</span></span>

<span data-ttu-id="c6245-173">Löscht Aufträge, die die im Befehl angegebenen Wörter enthalten.</span><span class="sxs-lookup"><span data-stu-id="c6245-173">Deletes jobs that include the specified words in the command.</span></span> <span data-ttu-id="c6245-174">Sie können ein Komma getrenntes Array eingeben.</span><span class="sxs-lookup"><span data-stu-id="c6245-174">You can enter a comma-separated array.</span></span>

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

### <span data-ttu-id="c6245-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c6245-175">-Confirm</span></span>

<span data-ttu-id="c6245-176">Fordert Sie zur Bestätigung auf, bevor `Remove-Job` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c6245-176">Prompts you for confirmation before `Remove-Job` is run.</span></span>

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

### <span data-ttu-id="c6245-177">-Filter</span><span class="sxs-lookup"><span data-stu-id="c6245-177">-Filter</span></span>

<span data-ttu-id="c6245-178">Löscht Aufträge, die alle in der zugeordneten Hash Tabelle festgelegten Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c6245-178">Deletes jobs that satisfy all the conditions established in the associated hash table.</span></span> <span data-ttu-id="c6245-179">Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="c6245-179">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="c6245-180">Dieser Parameter funktioniert nur mit benutzerdefinierten Auftragstypen, z. B. Workflowaufträgen und geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="c6245-180">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="c6245-181">Es funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, z. b. bei den mit erstellten `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="c6245-181">It doesn't work on standard background jobs, such as those created by using the `Start-Job`.</span></span>

<span data-ttu-id="c6245-182">Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c6245-182">This parameter is introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c6245-183">-Force</span><span class="sxs-lookup"><span data-stu-id="c6245-183">-Force</span></span>

<span data-ttu-id="c6245-184">Löscht einen Auftrag, auch wenn der Status des Auftrags "wird **ausgeführt** " lautet.</span><span class="sxs-lookup"><span data-stu-id="c6245-184">Deletes a job even if the job's state is **Running** .</span></span> <span data-ttu-id="c6245-185">Wenn der **Force** -Parameter nicht angegeben wird, werden `Remove-Job` keine laufenden Aufträge gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c6245-185">If the **Force** parameter isn't specified, `Remove-Job` doesn't delete running jobs.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, JobParameterSet, NameParameterSet, InstanceIdParameterSet, FilterParameterSet
Aliases: F

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c6245-186">-Id</span><span class="sxs-lookup"><span data-stu-id="c6245-186">-Id</span></span>

<span data-ttu-id="c6245-187">Löscht Hintergrund Aufträge mit der angegebenen **ID** . Sie können ein Komma getrenntes Array eingeben.</span><span class="sxs-lookup"><span data-stu-id="c6245-187">Deletes background jobs with the specified **Id** . You can enter a comma-separated array.</span></span> <span data-ttu-id="c6245-188">Die Auftrags- **ID** ist eine eindeutige ganze Zahl, die einen Auftrag innerhalb der aktuellen Sitzung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c6245-188">The job's **Id** is a unique integer that identifies a job within the current session.</span></span>

<span data-ttu-id="c6245-189">Um die **ID** eines Auftrags zu ermitteln, verwenden Sie `Get-Job` ohne Parameter.</span><span class="sxs-lookup"><span data-stu-id="c6245-189">To find a job's **Id** , use `Get-Job` without parameters.</span></span>

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

### <span data-ttu-id="c6245-190">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="c6245-190">-InstanceId</span></span>

<span data-ttu-id="c6245-191">Löscht Aufträge mit der angegebenen **InstanceId** .</span><span class="sxs-lookup"><span data-stu-id="c6245-191">Deletes jobs with the specified **InstanceId** .</span></span> <span data-ttu-id="c6245-192">Sie können ein Komma getrenntes Array eingeben.</span><span class="sxs-lookup"><span data-stu-id="c6245-192">You can enter a comma-separated array.</span></span> <span data-ttu-id="c6245-193">Eine **InstanceId** ist eine eindeutige GUID, die einen Auftrag identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c6245-193">An **InstanceId** is a unique GUID that identifies a job.</span></span>

<span data-ttu-id="c6245-194">Um die **InstanceId** eines Auftrags zu ermitteln, verwenden Sie `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="c6245-194">To find a job's **InstanceId** , use `Get-Job`.</span></span>

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

### <span data-ttu-id="c6245-195">-Auftrag</span><span class="sxs-lookup"><span data-stu-id="c6245-195">-Job</span></span>

<span data-ttu-id="c6245-196">Gibt die zu löschenden Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="c6245-196">Specifies the jobs to be deleted.</span></span> <span data-ttu-id="c6245-197">Geben Sie eine Variable ein, die entweder die Aufträge oder einen Befehl enthält, durch den die Aufträge abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c6245-197">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="c6245-198">Sie können ein Komma getrenntes Array eingeben.</span><span class="sxs-lookup"><span data-stu-id="c6245-198">You can enter a comma-separated array.</span></span>

<span data-ttu-id="c6245-199">Sie können Auftrags Objekte über die Pipeline an senden `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="c6245-199">You can send job objects down the pipeline to `Remove-Job`.</span></span>

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

### <span data-ttu-id="c6245-200">-Name</span><span class="sxs-lookup"><span data-stu-id="c6245-200">-Name</span></span>

<span data-ttu-id="c6245-201">Löscht nur Aufträge mit dem angegebenen anzeigen Amen.</span><span class="sxs-lookup"><span data-stu-id="c6245-201">Only deletes jobs with the specified friendly name.</span></span> <span data-ttu-id="c6245-202">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="c6245-202">Wildcards are permitted.</span></span> <span data-ttu-id="c6245-203">Sie können ein Komma getrenntes Array eingeben.</span><span class="sxs-lookup"><span data-stu-id="c6245-203">You can enter a comma-separated array.</span></span>

<span data-ttu-id="c6245-204">Anzeigen Amen für Aufträge sind nicht garantiert eindeutig, auch innerhalb einer PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c6245-204">Friendly names for jobs aren't guaranteed to be unique, even within a PowerShell session.</span></span> <span data-ttu-id="c6245-205">Verwenden Sie die Parameter " **WhatIf** " und " **Confirm** ", wenn Sie Dateien nach Namen löschen.</span><span class="sxs-lookup"><span data-stu-id="c6245-205">Use the **WhatIf** and **Confirm** parameters when you delete files by name.</span></span>

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

### <span data-ttu-id="c6245-206">-State</span><span class="sxs-lookup"><span data-stu-id="c6245-206">-State</span></span>

<span data-ttu-id="c6245-207">Löscht nur Aufträge mit dem angegebenen Zustand.</span><span class="sxs-lookup"><span data-stu-id="c6245-207">Only deletes jobs with the specified state.</span></span> <span data-ttu-id="c6245-208">Verwenden Sie den **Force** -Parameter, um Aufträge mit dem Status "wird **ausgeführt** " zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c6245-208">To delete jobs with a state of **Running** , use the **Force** parameter.</span></span>

<span data-ttu-id="c6245-209">Akzeptierte Werte:</span><span class="sxs-lookup"><span data-stu-id="c6245-209">Accepted values:</span></span>

- <span data-ttu-id="c6245-210">"Atbreakpoint"</span><span class="sxs-lookup"><span data-stu-id="c6245-210">AtBreakpoint</span></span>
- <span data-ttu-id="c6245-211">Blockiert</span><span class="sxs-lookup"><span data-stu-id="c6245-211">Blocked</span></span>
- <span data-ttu-id="c6245-212">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="c6245-212">Completed</span></span>
- <span data-ttu-id="c6245-213">Getrennt</span><span class="sxs-lookup"><span data-stu-id="c6245-213">Disconnected</span></span>
- <span data-ttu-id="c6245-214">Fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="c6245-214">Failed</span></span>
- <span data-ttu-id="c6245-215">NotStarted</span><span class="sxs-lookup"><span data-stu-id="c6245-215">NotStarted</span></span>
- <span data-ttu-id="c6245-216">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="c6245-216">Running</span></span>
- <span data-ttu-id="c6245-217">Beendet</span><span class="sxs-lookup"><span data-stu-id="c6245-217">Stopped</span></span>
- <span data-ttu-id="c6245-218">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="c6245-218">Stopping</span></span>
- <span data-ttu-id="c6245-219">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="c6245-219">Suspended</span></span>
- <span data-ttu-id="c6245-220">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="c6245-220">Suspending</span></span>

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

### <span data-ttu-id="c6245-221">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c6245-221">-WhatIf</span></span>

<span data-ttu-id="c6245-222">Zeigt, was geschieht, wenn ausgeführt wird `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="c6245-222">Shows what would happen if `Remove-Job` runs.</span></span> <span data-ttu-id="c6245-223">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c6245-223">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="c6245-224">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c6245-224">CommonParameters</span></span>

<span data-ttu-id="c6245-225">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c6245-225">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c6245-226">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c6245-226">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c6245-227">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c6245-227">INPUTS</span></span>

### <span data-ttu-id="c6245-228">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="c6245-228">System.Management.Automation.Job</span></span>

<span data-ttu-id="c6245-229">Sie können ein Auftrags Objekt über die Pipeline an senden `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="c6245-229">You can send a job object down the pipeline to `Remove-Job`.</span></span>

## <span data-ttu-id="c6245-230">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c6245-230">OUTPUTS</span></span>

### <span data-ttu-id="c6245-231">Keine</span><span class="sxs-lookup"><span data-stu-id="c6245-231">None</span></span>

<span data-ttu-id="c6245-232">`Remove-Job` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c6245-232">`Remove-Job` doesn't generate any output.</span></span>

## <span data-ttu-id="c6245-233">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c6245-233">NOTES</span></span>

<span data-ttu-id="c6245-234">Ein PowerShell-Auftrag erstellt einen neuen Prozess.</span><span class="sxs-lookup"><span data-stu-id="c6245-234">A PowerShell job creates a new process.</span></span> <span data-ttu-id="c6245-235">Wenn der Auftrag abgeschlossen ist, wird der Prozess beendet.</span><span class="sxs-lookup"><span data-stu-id="c6245-235">When the job completes, the process exits.</span></span> <span data-ttu-id="c6245-236">Wenn `Remove-Job` ausgeführt wird, wird der Status des Auftrags entfernt.</span><span class="sxs-lookup"><span data-stu-id="c6245-236">When `Remove-Job` is run, the job's state is removed.</span></span>

<span data-ttu-id="c6245-237">Wenn ein Auftrag vor dem Abschluss beendet wird und der Prozess nicht beendet wurde, wird der Prozess erzwungen.</span><span class="sxs-lookup"><span data-stu-id="c6245-237">If a job stops before completion and its process hasn't exited, the process is forcibly terminated.</span></span>

## <span data-ttu-id="c6245-238">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c6245-238">RELATED LINKS</span></span>

[<span data-ttu-id="c6245-239">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="c6245-239">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="c6245-240">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="c6245-240">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="c6245-241">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="c6245-241">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="c6245-242">Get-Job</span><span class="sxs-lookup"><span data-stu-id="c6245-242">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="c6245-243">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="c6245-243">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="c6245-244">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="c6245-244">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="c6245-245">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="c6245-245">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="c6245-246">Start-Job</span><span class="sxs-lookup"><span data-stu-id="c6245-246">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="c6245-247">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="c6245-247">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="c6245-248">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="c6245-248">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="c6245-249">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="c6245-249">Wait-Job</span></span>](Wait-Job.md)
