---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 85cbfad2a4866bf18e69fb99afb8698e233c4c80
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212775"
---
# <span data-ttu-id="aa24d-103">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="aa24d-103">Resume-Job</span></span>

## <span data-ttu-id="aa24d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="aa24d-104">SYNOPSIS</span></span>
<span data-ttu-id="aa24d-105">Startet einen angehaltenen Auftrag neu.</span><span class="sxs-lookup"><span data-stu-id="aa24d-105">Restarts a suspended job.</span></span>

## <span data-ttu-id="aa24d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aa24d-106">SYNTAX</span></span>

### <span data-ttu-id="aa24d-107">Sessionidparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="aa24d-107">SessionIdParameterSet (Default)</span></span>

```
Resume-Job [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="aa24d-108">Jobparameterset</span><span class="sxs-lookup"><span data-stu-id="aa24d-108">JobParameterSet</span></span>

```
Resume-Job [-Job] <Job[]> [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="aa24d-109">Nameparameterset</span><span class="sxs-lookup"><span data-stu-id="aa24d-109">NameParameterSet</span></span>

```
Resume-Job [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="aa24d-110">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="aa24d-110">InstanceIdParameterSet</span></span>

```
Resume-Job [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="aa24d-111">Stateparameterset</span><span class="sxs-lookup"><span data-stu-id="aa24d-111">StateParameterSet</span></span>

```
Resume-Job [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="aa24d-112">Filterparameterset</span><span class="sxs-lookup"><span data-stu-id="aa24d-112">FilterParameterSet</span></span>

```
Resume-Job [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="aa24d-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aa24d-113">DESCRIPTION</span></span>
<span data-ttu-id="aa24d-114">Das **Resume-Job-** Cmdlet setzt einen Workflow Auftrag fort, der angehalten wurde, z. b. mit dem Suspend-Job-Cmdlet oder der about_Suspend-Workflow-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="aa24d-114">The **Resume-Job** cmdlet resumes a workflow job that was suspended, such as by using the Suspend-Job cmdlet or the about_Suspend-Workflow activity.</span></span>
<span data-ttu-id="aa24d-115">Wenn ein Workflow Auftrag fortgesetzt wird, rekonstruiert die Auftrags-Engine den Zustand, die Metadaten und die Ausgabe aus gespeicherten Ressourcen, wie z. b. Prüfpunkten.</span><span class="sxs-lookup"><span data-stu-id="aa24d-115">When a workflow job resumes, the job engine reconstructs the state, metadata, and output from saved resources, such as checkpoints.</span></span>
<span data-ttu-id="aa24d-116">Der Auftrag wird ohne Verlust von Status oder Daten neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="aa24d-116">The job is restarted without any loss of state or data.</span></span>
<span data-ttu-id="aa24d-117">Der Status des Auftrags wird von **Suspended** in **Running** geändert.</span><span class="sxs-lookup"><span data-stu-id="aa24d-117">The job state is changed from **Suspended** to **Running** .</span></span>

<span data-ttu-id="aa24d-118">Verwenden Sie die Parameter von **Resume-Job** , um Aufträge anhand des Namens, der ID, der Instanz-ID oder der Pipe eines Auftrags Objekts (z. b. eines vom Get-Job-Cmdlet zurückgegebenen Auftrags) an **Resume-Job** auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="aa24d-118">Use the parameters of **Resume-Job** to select jobs by name, ID, instance ID or pipe a job object, such as one returned by the Get-Job cmdlet, to **Resume-Job** .</span></span>
<span data-ttu-id="aa24d-119">Um einen fortzusetzenden Auftrag auszuwählen, können Sie auch einen Eigenschaftenfilter verwenden.</span><span class="sxs-lookup"><span data-stu-id="aa24d-119">You can also use a property filter to select a job to be resumed.</span></span>

<span data-ttu-id="aa24d-120">Standardmäßig wird **Resume-Job** sofort zurückgegeben, selbst wenn noch nicht alle Aufträge wieder aufgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="aa24d-120">By default, **Resume-Job** returns immediately, even though all jobs might not yet be resumed.</span></span>
<span data-ttu-id="aa24d-121">Um die Eingabeaufforderung zu unterdrücken, bis alle angegebenen Aufträge wieder aufgenommen wurden, verwenden Sie den *Wait* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="aa24d-121">To suppress the command prompt until all specified jobs are resumed, use the *Wait* parameter.</span></span>

<span data-ttu-id="aa24d-122">Das **Resume-Job** -Cmdlet funktioniert nur mit benutzerdefinierten Auftragstypen, wie z. B. Workflowaufträgen.</span><span class="sxs-lookup"><span data-stu-id="aa24d-122">The **Resume-Job** cmdlet works only on custom job types, such as workflow jobs.</span></span>
<span data-ttu-id="aa24d-123">Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets "Start-Job".</span><span class="sxs-lookup"><span data-stu-id="aa24d-123">It does not work on standard background jobs, such as those that are started by using the Start-Job cmdlet.</span></span>
<span data-ttu-id="aa24d-124">Wenn Sie einen Auftrag eines nicht unterstützten Typs übermitteln, generiert **Resume-Job** einen Fehler mit Abbruch und die Ausführung wird beendet.</span><span class="sxs-lookup"><span data-stu-id="aa24d-124">If you submit a job of an unsupported type, **Resume-Job** generates a terminating error and stops running.</span></span>

<span data-ttu-id="aa24d-125">Um einen Workflowauftrag zu identifizieren, suchen Sie nach dem Wert **PSWorkflowJob** in der **PSJobTypeName** -Eigenschaft des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="aa24d-125">To identify a workflow job, look for a value of **PSWorkflowJob** in the **PSJobTypeName** property of the job.</span></span>
<span data-ttu-id="aa24d-126">Um zu bestimmen, ob ein benutzerdefinierter Auftragstyp das **Resume-Job** -Cmdlet unterstützt, nutzen Sie die Hilfethemen für den benutzerdefinierten Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="aa24d-126">To determine whether a particular custom job type supports the **Resume-Job** cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="aa24d-127">Bevor Sie ein Job-Cmdlet für einen benutzerdefinierten Auftragstyp verwenden, importieren Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, entweder mithilfe des Cmdlets "Import-Module" oder mithilfe eines Cmdlets im Modul.</span><span class="sxs-lookup"><span data-stu-id="aa24d-127">Before using a Job cmdlet on a custom job type, import the module that supports the custom job type, either by using the Import-Module cmdlet or getting or using a cmdlet in the module.</span></span>

<span data-ttu-id="aa24d-128">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="aa24d-128">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="aa24d-129">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="aa24d-129">EXAMPLES</span></span>

### <span data-ttu-id="aa24d-130">Beispiel 1: Fortsetzen eines Auftrags nach ID</span><span class="sxs-lookup"><span data-stu-id="aa24d-130">Example 1: Resume a job by ID</span></span>

```
The first command uses the **Get-Job** cmdlet to get the job. The output shows that the job is a suspended workflow job.
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

The second command uses the *Id* parameter of the **Resume-Job** cmdlet to resume the job with an *Id* value of 4.
PS C:\> Resume-Job -Id 4
```

<span data-ttu-id="aa24d-131">Die Befehle in diesem Beispiel prüfen, ob es sich bei dem Auftrag um einen angehaltenen Workflowauftrag handelt, und setzen den Auftrag anschließend fort.</span><span class="sxs-lookup"><span data-stu-id="aa24d-131">The commands in this example verify that the job is a suspended workflow job and then resume the job.</span></span>

### <span data-ttu-id="aa24d-132">Beispiel 2: Fortsetzen eines Auftrags nach Name</span><span class="sxs-lookup"><span data-stu-id="aa24d-132">Example 2: Resume a job by name</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

<span data-ttu-id="aa24d-133">Dieser Befehl verwendet den *Name* -Parameter, um mehrere Workflowaufträge auf dem lokalen Computer fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="aa24d-133">This command uses the *Name* parameter to resume several workflow jobs on the local computer.</span></span>

### <span data-ttu-id="aa24d-134">Beispiel 3: Verwenden von benutzerdefinierten Eigenschafts Werten</span><span class="sxs-lookup"><span data-stu-id="aa24d-134">Example 3: Use custom property values</span></span>

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

<span data-ttu-id="aa24d-135">Dieser Befehl verwendet den Wert einer benutzerdefinierten Eigenschaft, um den fortzusetzenden Workflowauftrag zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="aa24d-135">This command uses the value of a custom property to identify the workflow job to resume.</span></span>
<span data-ttu-id="aa24d-136">Der Befehl verwendet den *Filter* -Parameter zum Identifizieren des Workflowauftrags nach seiner **CustomID** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="aa24d-136">It uses the *Filter* parameter to identify the workflow job by its **CustomID** property.</span></span>
<span data-ttu-id="aa24d-137">Darüber hinaus überprüft er mithilfe des *State* -Parameters, ob der Workflowauftrag angehalten wurde, bevor er versucht, ihn fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="aa24d-137">It also uses the *State* parameter to verify that the workflow job is suspended, before it tries to resume it.</span></span>

### <span data-ttu-id="aa24d-138">Beispiel 4: Fortsetzen aller angehaltenen Aufträge auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="aa24d-138">Example 4: Resume all suspended jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

<span data-ttu-id="aa24d-139">Mit diesem Befehl werden alle angehaltenen Aufträge auf dem Remotecomputer „Srv01“ fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="aa24d-139">This command resumes all suspended jobs on the Srv01 remote computer.</span></span>

<span data-ttu-id="aa24d-140">Der Befehl verwendet das Cmdlet "Invoke-Command", um einen Befehl auf dem SRV01-Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="aa24d-140">The command uses the Invoke-Command cmdlet to run a command on the Srv01 computer.</span></span>
<span data-ttu-id="aa24d-141">Der Remote Befehl verwendet den *State* -Parameter des **Get-Job-** Cmdlets, um alle angehaltenen Aufträge auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="aa24d-141">The remote command uses the *State* parameter of the **Get-Job** cmdlet to get all suspended jobs on the computer.</span></span>
<span data-ttu-id="aa24d-142">Ein Pipelineoperator (|) sendet die angehaltenen Aufträge an das **Resume-Job** -Cmdlet, welches sie fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="aa24d-142">A pipeline operator (|) sends the suspended jobs to the **Resume-Job** cmdlet, which resumes them.</span></span>

### <span data-ttu-id="aa24d-143">Beispiel 5: warten auf Fortsetzen von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="aa24d-143">Example 5: Wait for jobs to resume</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

<span data-ttu-id="aa24d-144">Dieser Befehl verwendet den *Wait* -Parameter, um **Resume-Job** nur dann zurückzugeben, wenn alle angegebenen Aufträge fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="aa24d-144">This command uses the *Wait* parameter to direct **Resume-Job** to return only after all specified jobs are resumed.</span></span>
<span data-ttu-id="aa24d-145">Der *Wait* -Parameter ist besonders in Skripts nützlich, die davon ausgehen, dass Aufträge fortgesetzt werden, bevor das Skript fortfährt.</span><span class="sxs-lookup"><span data-stu-id="aa24d-145">The *Wait* parameter is especially useful in scripts that assume that jobs are resumed before the script continues.</span></span>

### <span data-ttu-id="aa24d-146">Beispiel 6: Fortsetzen eines Workflows, der sich selbst anhält</span><span class="sxs-lookup"><span data-stu-id="aa24d-146">Example 6: Resume a workflow that suspends itself</span></span>

```
This code sample shows the **Suspend-Workflow** activity in a workflow.
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

The following command runs the Test-Suspend workflow on the Server01 computer.When you run the workflow, the workflow runs the Get-Date activity and stores the result in the $a variable. Then it runs the Suspend-Workflow activity. In response, it takes a checkpoint, suspends the workflow, and returns a workflow job object.  Suspend-Workflow returns a workflow job object even if the workflow is not explicitly run as a job.
PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

The following command resumes the Test-Suspend workflow in Job8. It uses the *Wait* parameter to hold the command prompt until the job is resumed.
PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command

--     ----            -------------   -----         -----------     --------             -------

8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

This command uses the **Receive-Job** cmdlet to get the results of the Test-Suspend workflow. The final command in the workflow returns a **TimeSpan** object that represents the elapsed time between the current date and time and the date and time that was saved in the $a variable before the workflow was suspended.
PS C:\> Receive-Job -Name Job8
        Days              : 0
        Hours             : 0
        Minutes           : 0
        Seconds           : 19
        Milliseconds      : 823
        Ticks             : 198230041
        TotalDays         : 0.000229432917824074
        TotalHours        : 0.00550639002777778
        TotalMinutes      : 0.330383401666667
        TotalSeconds      : 19.8230041
        TotalMilliseconds : 19823.0041
        PSComputerName    : Server01
```

<span data-ttu-id="aa24d-147">Mit dem **Resume-Job-** Cmdlet können Sie einen Workflow Auftrag fortsetzen, der mithilfe der **Suspend-Workflow-** Aktivität angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="aa24d-147">The **Resume-Job** cmdlet lets you resume a workflow job that was suspend by using the **Suspend-Workflow** activity.</span></span>
<span data-ttu-id="aa24d-148">Diese Aktivität hält einen Workflow innerhalb eines Workflows an.</span><span class="sxs-lookup"><span data-stu-id="aa24d-148">This activity suspends a workflow from within a workflow.</span></span>
<span data-ttu-id="aa24d-149">Die Aktivität ist nur in Workflows gültig.</span><span class="sxs-lookup"><span data-stu-id="aa24d-149">It is valid only in workflows.</span></span>

<span data-ttu-id="aa24d-150">Informationen über Suspend-Workflow finden Sie unter about_Suspend-Workflow.</span><span class="sxs-lookup"><span data-stu-id="aa24d-150">For information about the Suspend-Workflow, see about_Suspend-Workflow.</span></span>

## <span data-ttu-id="aa24d-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aa24d-151">PARAMETERS</span></span>

### <span data-ttu-id="aa24d-152">-Filter</span><span class="sxs-lookup"><span data-stu-id="aa24d-152">-Filter</span></span>
<span data-ttu-id="aa24d-153">Gibt eine Hash Tabelle mit Bedingungen an.</span><span class="sxs-lookup"><span data-stu-id="aa24d-153">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="aa24d-154">Mit diesem Cmdlet werden Aufträge, die alle Bedingungen in der Hash Tabelle erfüllen, fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="aa24d-154">This cmdlet resumes jobs that satisfy all of the conditions in the hash table.</span></span>
<span data-ttu-id="aa24d-155">Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="aa24d-155">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

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

### <span data-ttu-id="aa24d-156">-Id</span><span class="sxs-lookup"><span data-stu-id="aa24d-156">-Id</span></span>
<span data-ttu-id="aa24d-157">Gibt ein Array von IDs für Aufträge an, die von diesem Cmdlet fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="aa24d-157">Specifies an array of IDs for jobs that this cmdlet resumes.</span></span>

<span data-ttu-id="aa24d-158">Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="aa24d-158">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="aa24d-159">Es ist einfacher, sich zu merken und als die Instanz-ID einzugeben, aber es ist nur in der aktuellen Sitzung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="aa24d-159">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="aa24d-160">Sie können eine oder mehrere IDs (durch Kommas getrennt) eingeben.</span><span class="sxs-lookup"><span data-stu-id="aa24d-160">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="aa24d-161">Um die ID eines Auftrags zu ermitteln, führen **Sie Get-Job** aus.</span><span class="sxs-lookup"><span data-stu-id="aa24d-161">To find the ID of a job, run **Get-Job** .</span></span>

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

### <span data-ttu-id="aa24d-162">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="aa24d-162">-InstanceId</span></span>
<span data-ttu-id="aa24d-163">Gibt ein Array von Instanz-IDs von Aufträgen an, die von diesem Cmdlet fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="aa24d-163">Specifies an array of instance IDs of jobs that this cmdlet resumes.</span></span>
<span data-ttu-id="aa24d-164">Standardmäßig werden alle Aufträge fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="aa24d-164">The default is all jobs.</span></span>

<span data-ttu-id="aa24d-165">Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="aa24d-165">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="aa24d-166">Um die Instanz-ID eines Auftrags zu ermitteln, führen **Sie Get-Job** aus.</span><span class="sxs-lookup"><span data-stu-id="aa24d-166">To find the instance ID of a job, run **Get-Job** .</span></span>

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

### <span data-ttu-id="aa24d-167">-Auftrag</span><span class="sxs-lookup"><span data-stu-id="aa24d-167">-Job</span></span>
<span data-ttu-id="aa24d-168">Gibt die fortzusetzenden Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="aa24d-168">Specifies the jobs to be resumed.</span></span>
<span data-ttu-id="aa24d-169">Geben Sie eine Variable ein, die entweder die Aufträge oder einen Befehl enthält, durch den die Aufträge abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="aa24d-169">Enter a variable that contains the jobs or a command that gets the jobs.</span></span>
<span data-ttu-id="aa24d-170">Sie können Aufträge auch über die Pipeline an das **Resume-Job** -Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="aa24d-170">You can also pipe jobs to the **Resume-Job** cmdlet.</span></span>

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

### <span data-ttu-id="aa24d-171">-Name</span><span class="sxs-lookup"><span data-stu-id="aa24d-171">-Name</span></span>
<span data-ttu-id="aa24d-172">Gibt ein Array von anzeigen Amen von Aufträgen an, die von diesem Cmdlet fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="aa24d-172">Specifies an array of friendly names of jobs that this cmdlet resumes.</span></span>
<span data-ttu-id="aa24d-173">Geben Sie mindestens einen Auftragsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="aa24d-173">Enter one or more job names.</span></span>
<span data-ttu-id="aa24d-174">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="aa24d-174">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="aa24d-175">-State</span><span class="sxs-lookup"><span data-stu-id="aa24d-175">-State</span></span>
<span data-ttu-id="aa24d-176">Gibt den Status der fort zusetzenden Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="aa24d-176">Specifies the state of jobs to resume.</span></span>
<span data-ttu-id="aa24d-177">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="aa24d-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="aa24d-178">NotStarted</span><span class="sxs-lookup"><span data-stu-id="aa24d-178">NotStarted</span></span>
- <span data-ttu-id="aa24d-179">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="aa24d-179">Running</span></span>
- <span data-ttu-id="aa24d-180">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="aa24d-180">Completed</span></span>
- <span data-ttu-id="aa24d-181">Fehler</span><span class="sxs-lookup"><span data-stu-id="aa24d-181">Failed</span></span>
- <span data-ttu-id="aa24d-182">Beendet</span><span class="sxs-lookup"><span data-stu-id="aa24d-182">Stopped</span></span>
- <span data-ttu-id="aa24d-183">Blockiert</span><span class="sxs-lookup"><span data-stu-id="aa24d-183">Blocked</span></span>
- <span data-ttu-id="aa24d-184">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="aa24d-184">Suspended</span></span>
- <span data-ttu-id="aa24d-185">Getrennt</span><span class="sxs-lookup"><span data-stu-id="aa24d-185">Disconnected</span></span>
- <span data-ttu-id="aa24d-186">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="aa24d-186">Suspending</span></span>
- <span data-ttu-id="aa24d-187">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="aa24d-187">Stopping</span></span>

<span data-ttu-id="aa24d-188">Mit diesem Cmdlet werden nur Aufträge im angehaltenen **Zustand fort** gesetzt.</span><span class="sxs-lookup"><span data-stu-id="aa24d-188">This cmdlet resumes only jobs in the **Suspended** state.</span></span>

<span data-ttu-id="aa24d-189">Weitere Informationen zu Auftrags Zuständen finden Sie unter [jobstate-Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="aa24d-189">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="aa24d-190">-Wait</span><span class="sxs-lookup"><span data-stu-id="aa24d-190">-Wait</span></span>
<span data-ttu-id="aa24d-191">Gibt an, dass dieses Cmdlet die Eingabeaufforderung unterdrückt, bis alle Auftrags Ergebnisse neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="aa24d-191">Indicates that this cmdlet suppresses the command prompt until all job results are restarted.</span></span>
<span data-ttu-id="aa24d-192">Standardmäßig gibt dieses Cmdlet sofort die verfügbaren Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="aa24d-192">By default, this cmdlet immediately returns the available results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa24d-193">-Confirm</span><span class="sxs-lookup"><span data-stu-id="aa24d-193">-Confirm</span></span>
<span data-ttu-id="aa24d-194">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="aa24d-194">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="aa24d-195">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="aa24d-195">-WhatIf</span></span>
<span data-ttu-id="aa24d-196">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="aa24d-196">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="aa24d-197">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="aa24d-197">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="aa24d-198">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aa24d-198">CommonParameters</span></span>
<span data-ttu-id="aa24d-199">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aa24d-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aa24d-200">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aa24d-200">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aa24d-201">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="aa24d-201">INPUTS</span></span>

### <span data-ttu-id="aa24d-202">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="aa24d-202">System.Management.Automation.Job</span></span>
<span data-ttu-id="aa24d-203">Sie können alle Arten von Aufträgen an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="aa24d-203">You can pipe all types of jobs to this cmdlet.</span></span>
<span data-ttu-id="aa24d-204">Wenn **Resume-Job** einen Auftrag eines nicht unterstützten Typs erhält, wird ein Abbruch Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aa24d-204">If **Resume-Job** gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="aa24d-205">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="aa24d-205">OUTPUTS</span></span>

### <span data-ttu-id="aa24d-206">Keine, System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="aa24d-206">None, System.Management.Automation.Job</span></span>
<span data-ttu-id="aa24d-207">Dieses Cmdlet gibt die Aufträge zurück, die wieder aufgenommen werden sollen, wenn Sie den *passthru* -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="aa24d-207">This cmdlet returns the jobs that it tries to resume, if you use the *PassThru* parameter.</span></span>
<span data-ttu-id="aa24d-208">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="aa24d-208">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="aa24d-209">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="aa24d-209">NOTES</span></span>

* <span data-ttu-id="aa24d-210">**Resume-Job** kann nur Aufträge fortsetzen, die angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="aa24d-210">**Resume-Job** can only resume jobs that are suspended.</span></span> <span data-ttu-id="aa24d-211">Wenn Sie einen Auftrag in einem anderen Zustand übermitteln, führt **Resume-Job** den Wiederaufnahmevorgang zwar aus, generiert jedoch eine Warnmeldung, dass der Auftrag nicht fortgesetzt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="aa24d-211">If you submit a job in a different state, **Resume-Job** runs the resume operation on the job, but generates a warning to notify you that the job could not be resumed.</span></span> <span data-ttu-id="aa24d-212">Um die Warnung zu unterdrücken, verwenden Sie den allgemeinen *WarningAction* -Parameter mit dem Wert SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="aa24d-212">To suppress the warning, use the *WarningAction* common parameter with a value of SilentlyContinue.</span></span>
* <span data-ttu-id="aa24d-213">Wenn es sich bei einem Auftrag nicht um einen Typ handelt, der das fortsetzen unterstützt, z. b. einen Workflow Auftrag ( **psworkflowjob** ), gibt **Resume-Job** einen abschließenden Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="aa24d-213">If a job is not of a type that supports resuming, such as a workflow job ( **PSWorkflowJob** ), **Resume-Job** returns a terminating error.</span></span>
* <span data-ttu-id="aa24d-214">Der Mechanismus und der Speicherort für einen angehaltenen Auftrag können je nach Auftragstyp unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="aa24d-214">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="aa24d-215">Beispielsweise werden angehaltene Workflowaufträge standardmäßig in einem Flatfile-Speicher gespeichert, können aber auch in einer SQL-Datenbank gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="aa24d-215">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a SQL database.</span></span>
* <span data-ttu-id="aa24d-216">Wenn Sie einen Auftrag fortsetzen, ändert sich der Status des Auftrags von **Suspended** in **Running** .</span><span class="sxs-lookup"><span data-stu-id="aa24d-216">When you resume a job, the job state changes from **Suspended** to **Running** .</span></span> <span data-ttu-id="aa24d-217">Verwenden Sie den *State* -Parameter des **Get-Job-** Cmdlets, um Aufträge mit dem Status "wird **ausgeführt** " zu ermitteln, die ausgeführt werden, einschließlich der mit diesem Cmdlet fortgesetzten Aufträge.</span><span class="sxs-lookup"><span data-stu-id="aa24d-217">To find the jobs that are running, including those that were resumed by this cmdlet, use the *State* parameter of the **Get-Job** cmdlet to get jobs in the **Running** state.</span></span>
* <span data-ttu-id="aa24d-218">Einige Auftragstypen verfügen über Optionen oder Eigenschaften, die das Anhalten des Auftrags durch Windows PowerShell verhindern.</span><span class="sxs-lookup"><span data-stu-id="aa24d-218">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span> <span data-ttu-id="aa24d-219">Wenn der Versuch, den Auftrag anzuhalten, fehlschlägt, überprüfen Sie, ob die Auftrags Optionen und-Eigenschaften das Anhalten zulassen.</span><span class="sxs-lookup"><span data-stu-id="aa24d-219">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="aa24d-220">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="aa24d-220">RELATED LINKS</span></span>

[<span data-ttu-id="aa24d-221">Get-Job</span><span class="sxs-lookup"><span data-stu-id="aa24d-221">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="aa24d-222">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="aa24d-222">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="aa24d-223">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="aa24d-223">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="aa24d-224">Start-Job</span><span class="sxs-lookup"><span data-stu-id="aa24d-224">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="aa24d-225">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="aa24d-225">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="aa24d-226">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="aa24d-226">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="aa24d-227">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="aa24d-227">Wait-Job</span></span>](Wait-Job.md)
