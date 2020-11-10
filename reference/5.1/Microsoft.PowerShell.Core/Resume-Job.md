---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 6d08d9053e100cb53d37a6e4931d118f90c35a6a
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388534"
---
# <span data-ttu-id="85f51-103">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="85f51-103">Resume-Job</span></span>

## <span data-ttu-id="85f51-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="85f51-104">SYNOPSIS</span></span>
<span data-ttu-id="85f51-105">Startet einen angehaltenen Auftrag neu.</span><span class="sxs-lookup"><span data-stu-id="85f51-105">Restarts a suspended job.</span></span>

## <span data-ttu-id="85f51-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="85f51-106">SYNTAX</span></span>

### <span data-ttu-id="85f51-107">Sessionidparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="85f51-107">SessionIdParameterSet (Default)</span></span>

```
Resume-Job [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="85f51-108">Jobparameterset</span><span class="sxs-lookup"><span data-stu-id="85f51-108">JobParameterSet</span></span>

```
Resume-Job [-Job] <Job[]> [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="85f51-109">Nameparameterset</span><span class="sxs-lookup"><span data-stu-id="85f51-109">NameParameterSet</span></span>

```
Resume-Job [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="85f51-110">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="85f51-110">InstanceIdParameterSet</span></span>

```
Resume-Job [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="85f51-111">Stateparameterset</span><span class="sxs-lookup"><span data-stu-id="85f51-111">StateParameterSet</span></span>

```
Resume-Job [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="85f51-112">Filterparameterset</span><span class="sxs-lookup"><span data-stu-id="85f51-112">FilterParameterSet</span></span>

```
Resume-Job [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="85f51-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="85f51-113">DESCRIPTION</span></span>

<span data-ttu-id="85f51-114">Mit dem- `Resume-Job` Cmdlet wird ein Workflow Auftrag, der angehalten wurde, wie z `Suspend-Job` . b. mithilfe des-Cmdlets oder der [about_Suspend-Workflow-](../PSWorkflow/about/about_Suspend-Workflow.md) Aktivität fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="85f51-114">The `Resume-Job` cmdlet resumes a workflow job that was suspended, such as by using the `Suspend-Job` cmdlet or the [about_Suspend-Workflow](../PSWorkflow/about/about_Suspend-Workflow.md) activity.</span></span> <span data-ttu-id="85f51-115">Wenn ein Workflow Auftrag fortgesetzt wird, rekonstruiert die Auftrags-Engine den Zustand, die Metadaten und die Ausgabe aus gespeicherten Ressourcen, wie z. b. Prüfpunkten.</span><span class="sxs-lookup"><span data-stu-id="85f51-115">When a workflow job resumes, the job engine reconstructs the state, metadata, and output from saved resources, such as checkpoints.</span></span> <span data-ttu-id="85f51-116">Der Auftrag wird ohne Verlust von Status oder Daten neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="85f51-116">The job is restarted without any loss of state or data.</span></span>
<span data-ttu-id="85f51-117">Der Status des Auftrags wird von **Suspended** in **Running** geändert.</span><span class="sxs-lookup"><span data-stu-id="85f51-117">The job state is changed from **Suspended** to **Running**.</span></span>

<span data-ttu-id="85f51-118">Wählen Sie mithilfe der Parameter von `Resume-Job` Aufträge nach Name, ID, Instanz-ID aus, oder übergeben Sie ein Auftrags Objekt, z. b. ein vom Cmdlet zurück gegebenes-Objekt `Get-Job` an `Resume-Job` .</span><span class="sxs-lookup"><span data-stu-id="85f51-118">Use the parameters of `Resume-Job` to select jobs by name, ID, instance ID or pipe a job object, such as one returned by the `Get-Job` cmdlet, to `Resume-Job`.</span></span> <span data-ttu-id="85f51-119">Um einen fortzusetzenden Auftrag auszuwählen, können Sie auch einen Eigenschaftenfilter verwenden.</span><span class="sxs-lookup"><span data-stu-id="85f51-119">You can also use a property filter to select a job to be resumed.</span></span>

<span data-ttu-id="85f51-120">Standardmäßig wird `Resume-Job` sofort zurückgegeben, obwohl möglicherweise noch nicht alle Aufträge fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="85f51-120">By default, `Resume-Job` returns immediately, even though all jobs might not yet be resumed.</span></span> <span data-ttu-id="85f51-121">Um die Eingabeaufforderung zu unterdrücken, bis alle angegebenen Aufträge wieder aufgenommen wurden, verwenden Sie den **Wait** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="85f51-121">To suppress the command prompt until all specified jobs are resumed, use the **Wait** parameter.</span></span>

<span data-ttu-id="85f51-122">Das- `Resume-Job` Cmdlet funktioniert nur mit benutzerdefinierten Auftrags Typen, z. b. Workflow Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="85f51-122">The `Resume-Job` cmdlet works only on custom job types, such as workflow jobs.</span></span> <span data-ttu-id="85f51-123">Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des `Start-Job` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="85f51-123">It does not work on standard background jobs, such as those that are started by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="85f51-124">Wenn Sie einen Auftrag mit einem nicht unterstützten Typ übermitteln, wird von `Resume-Job` ein Abbruch Fehler generiert, und die Ausführung wird beendet.</span><span class="sxs-lookup"><span data-stu-id="85f51-124">If you submit a job of an unsupported type, `Resume-Job` generates a terminating error and stops running.</span></span>

<span data-ttu-id="85f51-125">Um einen Workflowauftrag zu identifizieren, suchen Sie nach dem Wert **PSWorkflowJob** in der **PSJobTypeName** -Eigenschaft des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="85f51-125">To identify a workflow job, look for a value of **PSWorkflowJob** in the **PSJobTypeName** property of the job.</span></span> <span data-ttu-id="85f51-126">Informationen zum bestimmen, ob ein bestimmter benutzerdefinierter Auftragstyp das- `Resume-Job` Cmdlet unterstützt, finden Sie in den Hilfe Themen für den benutzerdefinierten Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="85f51-126">To determine whether a particular custom job type supports the `Resume-Job` cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="85f51-127">Bevor Sie ein Job-Cmdlet für einen benutzerdefinierten Auftragstyp verwenden, importieren Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, entweder mithilfe des `Import-Module` Cmdlets oder mithilfe eines Cmdlets im Modul.</span><span class="sxs-lookup"><span data-stu-id="85f51-127">Before using a Job cmdlet on a custom job type, import the module that supports the custom job type, either by using the `Import-Module` cmdlet or getting or using a cmdlet in the module.</span></span>

<span data-ttu-id="85f51-128">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="85f51-128">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="85f51-129">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="85f51-129">EXAMPLES</span></span>

### <span data-ttu-id="85f51-130">Beispiel 1: Fortsetzen eines Auftrags nach ID</span><span class="sxs-lookup"><span data-stu-id="85f51-130">Example 1: Resume a job by ID</span></span>

<span data-ttu-id="85f51-131">Die Befehle in diesem Beispiel prüfen, ob es sich bei dem Auftrag um einen angehaltenen Workflowauftrag handelt, und setzen den Auftrag anschließend fort.</span><span class="sxs-lookup"><span data-stu-id="85f51-131">The commands in this example verify that the job is a suspended workflow job and then resume the job.</span></span> <span data-ttu-id="85f51-132">Der erste Befehl verwendet das `Get-Job` Cmdlet, um den Auftrag zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="85f51-132">The first command uses the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="85f51-133">Die Ausgabe zeigt, dass es sich bei dem Auftrag um einen angehaltenen Workflowauftrag handelt.</span><span class="sxs-lookup"><span data-stu-id="85f51-133">The output shows that the job is a suspended workflow job.</span></span> <span data-ttu-id="85f51-134">Der zweite Befehl verwendet den **ID** -Parameter des `Resume-Job` Cmdlets, um den Auftrag mit dem **ID** -Wert 4 fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="85f51-134">The second command uses the **Id** parameter of the `Resume-Job` cmdlet to resume the job with an **Id** value of 4.</span></span>

```
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

PS C:\> Resume-Job -Id 4
```

### <span data-ttu-id="85f51-135">Beispiel 2: Fortsetzen eines Auftrags nach Name</span><span class="sxs-lookup"><span data-stu-id="85f51-135">Example 2: Resume a job by name</span></span>

<span data-ttu-id="85f51-136">Dieser Befehl verwendet den **Name** -Parameter, um mehrere Workflowaufträge auf dem lokalen Computer fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="85f51-136">This command uses the **Name** parameter to resume several workflow jobs on the local computer.</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

### <span data-ttu-id="85f51-137">Beispiel 3: Verwenden von benutzerdefinierten Eigenschafts Werten</span><span class="sxs-lookup"><span data-stu-id="85f51-137">Example 3: Use custom property values</span></span>

<span data-ttu-id="85f51-138">Dieser Befehl verwendet den Wert einer benutzerdefinierten Eigenschaft, um den fortzusetzenden Workflowauftrag zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="85f51-138">This command uses the value of a custom property to identify the workflow job to resume.</span></span> <span data-ttu-id="85f51-139">Der Befehl verwendet den **Filter** -Parameter zum Identifizieren des Workflowauftrags nach seiner **CustomID** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="85f51-139">It uses the **Filter** parameter to identify the workflow job by its **CustomID** property.</span></span> <span data-ttu-id="85f51-140">Darüber hinaus überprüft er mithilfe des **State** -Parameters, ob der Workflowauftrag angehalten wurde, bevor er versucht, ihn fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="85f51-140">It also uses the **State** parameter to verify that the workflow job is suspended, before it tries to resume it.</span></span>

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

### <span data-ttu-id="85f51-141">Beispiel 4: Fortsetzen aller angehaltenen Aufträge auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="85f51-141">Example 4: Resume all suspended jobs on a remote computer</span></span>

<span data-ttu-id="85f51-142">Mit diesem Befehl werden alle angehaltenen Aufträge auf dem Remotecomputer „Srv01“ fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="85f51-142">This command resumes all suspended jobs on the Srv01 remote computer.</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

<span data-ttu-id="85f51-143">Der Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines Befehls auf dem SRV01-Computer.</span><span class="sxs-lookup"><span data-stu-id="85f51-143">The command uses the `Invoke-Command` cmdlet to run a command on the Srv01 computer.</span></span> <span data-ttu-id="85f51-144">Der Remote Befehl verwendet den **State** -Parameter des `Get-Job` Cmdlets, um alle angehaltenen Aufträge auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="85f51-144">The remote command uses the **State** parameter of the `Get-Job` cmdlet to get all suspended jobs on the computer.</span></span> <span data-ttu-id="85f51-145">Ein Pipeline Operator ( `|` ) sendet die angehaltenen Aufträge an das `Resume-Job` Cmdlet, das Sie wieder aufnimmt.</span><span class="sxs-lookup"><span data-stu-id="85f51-145">A pipeline operator (`|`) sends the suspended jobs to the `Resume-Job` cmdlet, which resumes them.</span></span>

### <span data-ttu-id="85f51-146">Beispiel 5: warten auf Fortsetzen von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="85f51-146">Example 5: Wait for jobs to resume</span></span>

<span data-ttu-id="85f51-147">Dieser Befehl verwendet den **Wait** -Parameter, um `Resume-Job` nur zurückzugeben, nachdem alle angegebenen Aufträge wieder aufgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="85f51-147">This command uses the **Wait** parameter to direct `Resume-Job` to return only after all specified jobs are resumed.</span></span> <span data-ttu-id="85f51-148">Der **Wait** -Parameter ist besonders in Skripts nützlich, die davon ausgehen, dass Aufträge fortgesetzt werden, bevor das Skript fortfährt.</span><span class="sxs-lookup"><span data-stu-id="85f51-148">The **Wait** parameter is especially useful in scripts that assume that jobs are resumed before the script continues.</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

### <span data-ttu-id="85f51-149">Beispiel 6: Fortsetzen eines Workflows, der sich selbst anhält</span><span class="sxs-lookup"><span data-stu-id="85f51-149">Example 6: Resume a workflow that suspends itself</span></span>

<span data-ttu-id="85f51-150">Dieses Codebeispiel zeigt die- `Suspend-Workflow` Aktivität in einem Workflow.</span><span class="sxs-lookup"><span data-stu-id="85f51-150">This code sample shows the `Suspend-Workflow` activity in a workflow.</span></span>

<span data-ttu-id="85f51-151">Der `Test-Suspend` Workflow auf dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="85f51-151">The `Test-Suspend` workflow on the Server01 computer.</span></span> <span data-ttu-id="85f51-152">Wenn Sie den Workflow ausführen, führt der Workflow die `Get-Date` -Aktivität aus und speichert das Ergebnis in der `$a` Variablen.</span><span class="sxs-lookup"><span data-stu-id="85f51-152">When you run the workflow, the workflow runs the `Get-Date` activity and stores the result in the `$a` variable.</span></span> <span data-ttu-id="85f51-153">Anschließend wird die- `Suspend-Workflow` Aktivität ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="85f51-153">Then it runs the `Suspend-Workflow` activity.</span></span> <span data-ttu-id="85f51-154">Als Reaktion darauf erstellt er einen Prüfpunkt, hält den Workflow an und gibt ein Workflowauftragsobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="85f51-154">In response, it takes a checkpoint, suspends the workflow, and returns a workflow job object.</span></span> <span data-ttu-id="85f51-155">`Suspend-Workflow` Gibt ein Workflow Auftrags Objekt zurück, auch wenn der Workflow nicht explizit als Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="85f51-155">`Suspend-Workflow` returns a workflow job object even if the workflow is not explicitly run as a job.</span></span>

<span data-ttu-id="85f51-156">`Resume-Job` nimmt den `Test-Suspend` Workflow in Job8 wieder auf.</span><span class="sxs-lookup"><span data-stu-id="85f51-156">`Resume-Job` resumes the `Test-Suspend` workflow in Job8.</span></span> <span data-ttu-id="85f51-157">Der Befehl verwendet den **Wait** -Parameter, um die Eingabeaufforderung anzuhalten, bis der Auftrag fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="85f51-157">It uses the **Wait** parameter to hold the command prompt until the job is resumed.</span></span>

<span data-ttu-id="85f51-158">Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse des `Test-Suspend` Workflows abgerufen.</span><span class="sxs-lookup"><span data-stu-id="85f51-158">The `Receive-Job` cmdlet gets the results of the `Test-Suspend` workflow.</span></span> <span data-ttu-id="85f51-159">Der letzte Befehl im Workflow gibt ein **TimeSpan** -Objekt zurück, das die verstrichene Zeit zwischen dem aktuellen Datum und der aktuellen Uhrzeit und dem Datum und der Uhrzeit darstellt, die in der Variablen gespeichert wurden, `$a` bevor der Workflow angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="85f51-159">The final command in the workflow returns a **TimeSpan** object that represents the elapsed time between the current date and time and the date and time that was saved in the `$a` variable before the workflow was suspended.</span></span>

```
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

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

<span data-ttu-id="85f51-160">Mit dem- `Resume-Job` Cmdlet können Sie einen Workflow Auftrag, der angehalten wurde, mithilfe der-Aktivität fortsetzen `Suspend-Workflow` .</span><span class="sxs-lookup"><span data-stu-id="85f51-160">The `Resume-Job` cmdlet lets you resume a workflow job that was suspend by using the `Suspend-Workflow` activity.</span></span> <span data-ttu-id="85f51-161">Diese Aktivität hält einen Workflow innerhalb eines Workflows an.</span><span class="sxs-lookup"><span data-stu-id="85f51-161">This activity suspends a workflow from within a workflow.</span></span> <span data-ttu-id="85f51-162">Die Aktivität ist nur in Workflows gültig.</span><span class="sxs-lookup"><span data-stu-id="85f51-162">It is valid only in workflows.</span></span>

<span data-ttu-id="85f51-163">Weitere Informationen zum finden Sie unter `Suspend-Workflow` about_Suspend-Workflow] (.. /Psworkflow/about/about_Suspend-Workflow. MD).</span><span class="sxs-lookup"><span data-stu-id="85f51-163">For information about the `Suspend-Workflow`, see about_Suspend-Workflow](../PSWorkflow/about/about_Suspend-Workflow.md).</span></span>

## <span data-ttu-id="85f51-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="85f51-164">PARAMETERS</span></span>

### <span data-ttu-id="85f51-165">-Filter</span><span class="sxs-lookup"><span data-stu-id="85f51-165">-Filter</span></span>

<span data-ttu-id="85f51-166">Gibt eine Hash Tabelle mit Bedingungen an.</span><span class="sxs-lookup"><span data-stu-id="85f51-166">Specifies a hash table of conditions.</span></span> <span data-ttu-id="85f51-167">Mit diesem Cmdlet werden Aufträge, die alle Bedingungen in der Hash Tabelle erfüllen, fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="85f51-167">This cmdlet resumes jobs that satisfy all of the conditions in the hash table.</span></span> <span data-ttu-id="85f51-168">Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="85f51-168">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

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

### <span data-ttu-id="85f51-169">-Id</span><span class="sxs-lookup"><span data-stu-id="85f51-169">-Id</span></span>

<span data-ttu-id="85f51-170">Gibt ein Array von IDs für Aufträge an, die von diesem Cmdlet fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="85f51-170">Specifies an array of IDs for jobs that this cmdlet resumes.</span></span>

<span data-ttu-id="85f51-171">Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="85f51-171">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="85f51-172">Es ist einfacher, sich zu merken und als die Instanz-ID einzugeben, aber es ist nur in der aktuellen Sitzung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="85f51-172">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="85f51-173">Sie können eine oder mehrere IDs (durch Kommas getrennt) eingeben.</span><span class="sxs-lookup"><span data-stu-id="85f51-173">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="85f51-174">Um die ID eines Auftrags zu ermitteln, führen Sie aus `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="85f51-174">To find the ID of a job, run `Get-Job`.</span></span>

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

### <span data-ttu-id="85f51-175">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="85f51-175">-InstanceId</span></span>

<span data-ttu-id="85f51-176">Gibt ein Array von Instanz-IDs von Aufträgen an, die von diesem Cmdlet fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="85f51-176">Specifies an array of instance IDs of jobs that this cmdlet resumes.</span></span> <span data-ttu-id="85f51-177">Standardmäßig werden alle Aufträge fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="85f51-177">The default is all jobs.</span></span>

<span data-ttu-id="85f51-178">Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="85f51-178">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="85f51-179">Führen Sie aus, um die Instanz-ID eines Auftrags zu ermitteln `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="85f51-179">To find the instance ID of a job, run `Get-Job`.</span></span>

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

### <span data-ttu-id="85f51-180">-Auftrag</span><span class="sxs-lookup"><span data-stu-id="85f51-180">-Job</span></span>

<span data-ttu-id="85f51-181">Gibt die fortzusetzenden Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="85f51-181">Specifies the jobs to be resumed.</span></span> <span data-ttu-id="85f51-182">Geben Sie eine Variable ein, die entweder die Aufträge oder einen Befehl enthält, durch den die Aufträge abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="85f51-182">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="85f51-183">Sie können Aufträge auch über die Pipeline an das `Resume-Job` Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="85f51-183">You can also pipe jobs to the `Resume-Job` cmdlet.</span></span>

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

### <span data-ttu-id="85f51-184">-Name</span><span class="sxs-lookup"><span data-stu-id="85f51-184">-Name</span></span>

<span data-ttu-id="85f51-185">Gibt ein Array von anzeigen Amen von Aufträgen an, die von diesem Cmdlet fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="85f51-185">Specifies an array of friendly names of jobs that this cmdlet resumes.</span></span> <span data-ttu-id="85f51-186">Geben Sie mindestens einen Auftragsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="85f51-186">Enter one or more job names.</span></span>
<span data-ttu-id="85f51-187">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="85f51-187">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="85f51-188">-State</span><span class="sxs-lookup"><span data-stu-id="85f51-188">-State</span></span>

<span data-ttu-id="85f51-189">Gibt den Status der fort zusetzenden Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="85f51-189">Specifies the state of jobs to resume.</span></span> <span data-ttu-id="85f51-190">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="85f51-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="85f51-191">NotStarted</span><span class="sxs-lookup"><span data-stu-id="85f51-191">NotStarted</span></span>
- <span data-ttu-id="85f51-192">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="85f51-192">Running</span></span>
- <span data-ttu-id="85f51-193">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="85f51-193">Completed</span></span>
- <span data-ttu-id="85f51-194">Fehler</span><span class="sxs-lookup"><span data-stu-id="85f51-194">Failed</span></span>
- <span data-ttu-id="85f51-195">Beendet</span><span class="sxs-lookup"><span data-stu-id="85f51-195">Stopped</span></span>
- <span data-ttu-id="85f51-196">Blockiert</span><span class="sxs-lookup"><span data-stu-id="85f51-196">Blocked</span></span>
- <span data-ttu-id="85f51-197">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="85f51-197">Suspended</span></span>
- <span data-ttu-id="85f51-198">Getrennt</span><span class="sxs-lookup"><span data-stu-id="85f51-198">Disconnected</span></span>
- <span data-ttu-id="85f51-199">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="85f51-199">Suspending</span></span>
- <span data-ttu-id="85f51-200">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="85f51-200">Stopping</span></span>

<span data-ttu-id="85f51-201">Mit diesem Cmdlet werden nur Aufträge im angehaltenen **Zustand fort** gesetzt.</span><span class="sxs-lookup"><span data-stu-id="85f51-201">This cmdlet resumes only jobs in the **Suspended** state.</span></span>

<span data-ttu-id="85f51-202">Weitere Informationen zu Auftrags Zuständen finden Sie unter [jobstate-Enumeration](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="85f51-202">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="85f51-203">-Wait</span><span class="sxs-lookup"><span data-stu-id="85f51-203">-Wait</span></span>

<span data-ttu-id="85f51-204">Gibt an, dass dieses Cmdlet die Eingabeaufforderung unterdrückt, bis alle Auftrags Ergebnisse neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="85f51-204">Indicates that this cmdlet suppresses the command prompt until all job results are restarted.</span></span> <span data-ttu-id="85f51-205">Standardmäßig gibt dieses Cmdlet sofort die verfügbaren Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="85f51-205">By default, this cmdlet immediately returns the available results.</span></span>

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

### <span data-ttu-id="85f51-206">-Confirm</span><span class="sxs-lookup"><span data-stu-id="85f51-206">-Confirm</span></span>

<span data-ttu-id="85f51-207">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="85f51-207">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="85f51-208">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="85f51-208">-WhatIf</span></span>

<span data-ttu-id="85f51-209">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="85f51-209">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="85f51-210">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="85f51-210">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="85f51-211">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="85f51-211">CommonParameters</span></span>

<span data-ttu-id="85f51-212">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="85f51-212">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="85f51-213">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="85f51-213">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="85f51-214">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="85f51-214">INPUTS</span></span>

### <span data-ttu-id="85f51-215">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="85f51-215">System.Management.Automation.Job</span></span>

<span data-ttu-id="85f51-216">Sie können alle Arten von Aufträgen an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="85f51-216">You can pipe all types of jobs to this cmdlet.</span></span> <span data-ttu-id="85f51-217">Wenn `Resume-Job` einen Auftrag eines nicht unterstützten Typs abruft, wird ein Abbruch Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="85f51-217">If `Resume-Job` gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="85f51-218">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="85f51-218">OUTPUTS</span></span>

### <span data-ttu-id="85f51-219">Keine, System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="85f51-219">None, System.Management.Automation.Job</span></span>

<span data-ttu-id="85f51-220">Dieses Cmdlet gibt die Aufträge zurück, die wieder aufgenommen werden sollen, wenn Sie den **passthru** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="85f51-220">This cmdlet returns the jobs that it tries to resume, if you use the **PassThru** parameter.</span></span>
<span data-ttu-id="85f51-221">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="85f51-221">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="85f51-222">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="85f51-222">NOTES</span></span>

- <span data-ttu-id="85f51-223">`Resume-Job` kann nur Aufträge fortsetzen, die angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="85f51-223">`Resume-Job` can only resume jobs that are suspended.</span></span> <span data-ttu-id="85f51-224">Wenn Sie einen Auftrag in einem anderen Zustand übermitteln, `Resume-Job` führt den Wiederaufnahme Vorgang für den Auftrag aus, generiert jedoch eine Warnung, um Sie darüber zu benachrichtigen, dass der Auftrag nicht fortgesetzt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="85f51-224">If you submit a job in a different state, `Resume-Job` runs the resume operation on the job, but generates a warning to notify you that the job could not be resumed.</span></span> <span data-ttu-id="85f51-225">Um die Warnung zu unterdrücken, verwenden Sie den allgemeinen **WarningAction** -Parameter mit dem Wert SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="85f51-225">To suppress the warning, use the **WarningAction** common parameter with a value of SilentlyContinue.</span></span>
- <span data-ttu-id="85f51-226">Wenn ein Auftrag nicht von einem Typ ist, der das fortsetzen unterstützt, wie z. b. ein Workflow Auftrag ( **psworkflowjob** ), wird `Resume-Job` ein Abbruch Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="85f51-226">If a job is not of a type that supports resuming, such as a workflow job ( **PSWorkflowJob** ), `Resume-Job` returns a terminating error.</span></span>
- <span data-ttu-id="85f51-227">Der Mechanismus und der Speicherort für einen angehaltenen Auftrag können je nach Auftragstyp unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="85f51-227">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="85f51-228">Beispielsweise werden angehaltene Workflowaufträge standardmäßig in einem Flatfile-Speicher gespeichert, können aber auch in einer SQL-Datenbank gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="85f51-228">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a SQL database.</span></span>
- <span data-ttu-id="85f51-229">Wenn Sie einen Auftrag fortsetzen, ändert sich der Status des Auftrags von **Suspended** in **Running**.</span><span class="sxs-lookup"><span data-stu-id="85f51-229">When you resume a job, the job state changes from **Suspended** to **Running**.</span></span> <span data-ttu-id="85f51-230">Zum Ermitteln der Aufträge, die ausgeführt werden, einschließlich derjenigen, die mit diesem Cmdlet fortgesetzt wurden, verwenden Sie den **State** -Parameter des `Get-Job` Cmdlets, um Aufträge mit dem Status "wird **ausgeführt** " zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="85f51-230">To find the jobs that are running, including those that were resumed by this cmdlet, use the **State** parameter of the `Get-Job` cmdlet to get jobs in the **Running** state.</span></span>
- <span data-ttu-id="85f51-231">Einige Auftragstypen verfügen über Optionen oder Eigenschaften, die das Anhalten des Auftrags durch Windows PowerShell verhindern.</span><span class="sxs-lookup"><span data-stu-id="85f51-231">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span>
  <span data-ttu-id="85f51-232">Wenn der Versuch, den Auftrag anzuhalten, fehlschlägt, überprüfen Sie, ob die Auftrags Optionen und-Eigenschaften das Anhalten zulassen.</span><span class="sxs-lookup"><span data-stu-id="85f51-232">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="85f51-233">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="85f51-233">RELATED LINKS</span></span>

[<span data-ttu-id="85f51-234">Get-Job</span><span class="sxs-lookup"><span data-stu-id="85f51-234">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="85f51-235">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="85f51-235">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="85f51-236">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="85f51-236">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="85f51-237">Start-Job</span><span class="sxs-lookup"><span data-stu-id="85f51-237">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="85f51-238">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="85f51-238">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="85f51-239">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="85f51-239">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="85f51-240">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="85f51-240">Wait-Job</span></span>](Wait-Job.md)
