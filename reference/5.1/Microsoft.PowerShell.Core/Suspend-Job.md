---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/suspend-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Job
ms.openlocfilehash: 6ab50342e963832d89b3dfc4128a22fc16405926
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212724"
---
# <span data-ttu-id="108d7-103">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="108d7-103">Suspend-Job</span></span>

## <span data-ttu-id="108d7-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="108d7-104">SYNOPSIS</span></span>
<span data-ttu-id="108d7-105">Beendet Workflowaufträge temporär.</span><span class="sxs-lookup"><span data-stu-id="108d7-105">Temporarily stops workflow jobs.</span></span>

## <span data-ttu-id="108d7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="108d7-106">SYNTAX</span></span>

### <span data-ttu-id="108d7-107">Sessionidparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="108d7-107">SessionIdParameterSet (Default)</span></span>

```
Suspend-Job [-Force] [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="108d7-108">Jobparameterset</span><span class="sxs-lookup"><span data-stu-id="108d7-108">JobParameterSet</span></span>

```
Suspend-Job [-Job] <Job[]> [-Force] [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="108d7-109">Nameparameterset</span><span class="sxs-lookup"><span data-stu-id="108d7-109">NameParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="108d7-110">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="108d7-110">InstanceIdParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="108d7-111">Filterparameterset</span><span class="sxs-lookup"><span data-stu-id="108d7-111">FilterParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="108d7-112">Stateparameterset</span><span class="sxs-lookup"><span data-stu-id="108d7-112">StateParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="108d7-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="108d7-113">DESCRIPTION</span></span>
<span data-ttu-id="108d7-114">Das **Suspend-Job-** Cmdlet hält Workflow Aufträge an.</span><span class="sxs-lookup"><span data-stu-id="108d7-114">The **Suspend-Job** cmdlet suspends workflow jobs.</span></span>
<span data-ttu-id="108d7-115">Suspend bedeutet, dass ein Workflow Auftrag vorübergehend unterbrochen oder angehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="108d7-115">Suspend means to temporarily interrupt or pause a workflow job.</span></span>
<span data-ttu-id="108d7-116">Mit diesem Cmdlet können Benutzer, die Workflows ausführen, den Workflow anhalten.</span><span class="sxs-lookup"><span data-stu-id="108d7-116">This cmdlet allows users who are running workflows to suspend the workflow.</span></span>
<span data-ttu-id="108d7-117">Es ergänzt die Suspend-Workflow- https://go.microsoft.com/fwlink/?LinkId=267141 Aktivität, bei der es sich um einen Befehl im Workflow handelt, der den Workflow anhält.</span><span class="sxs-lookup"><span data-stu-id="108d7-117">It complements the Suspend-Workflowhttps://go.microsoft.com/fwlink/?LinkId=267141 activity, which is a command in the workflow that suspends the workflow.</span></span>

<span data-ttu-id="108d7-118">Das **Suspend-Job** -Cmdlet funktioniert nur für Workflowaufträge.</span><span class="sxs-lookup"><span data-stu-id="108d7-118">The **Suspend-Job** cmdlet works only on workflow jobs.</span></span>
<span data-ttu-id="108d7-119">Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets "Start-Job".</span><span class="sxs-lookup"><span data-stu-id="108d7-119">It does not work on standard background jobs, such as those that are started by using the Start-Job cmdlet.</span></span>

<span data-ttu-id="108d7-120">Um einen Workflowauftrag zu identifizieren, suchen Sie nach dem Wert PSWorkflowJob in der **PSJobTypeName** -Eigenschaft des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="108d7-120">To identify a workflow job, look for a value of PSWorkflowJob in the **PSJobTypeName** property of the job.</span></span>
<span data-ttu-id="108d7-121">Um zu bestimmen, ob ein bestimmter benutzerdefinierter Auftragstyp das **Suspend-Job** -Cmdlet unterstützt, informieren Sie sich in den Hilfethemen für den benutzerdefinierten Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="108d7-121">To determine whether a particular custom job type supports the **Suspend-Job** cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="108d7-122">Wenn Sie einen Workflowauftrag anhalten, wird er bis zum nächsten Prüfpunkt ausgeführt, angehalten und gibt sofort ein Workflowauftragsobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="108d7-122">When you suspend a workflow job, the workflow job runs to the next checkpoint, suspends, and immediately returns a workflow job object.</span></span>
<span data-ttu-id="108d7-123">Um auf den Abschluss der Unterbrechung zu warten, bevor der Auftrag ausgeführt wird, verwenden Sie den *Wait* -Parameter von **Suspend-Job** oder das Wait-Job-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="108d7-123">To wait for the suspension to complete before getting the job, use the *Wait* parameter of **Suspend-Job** or the Wait-Job cmdlet.</span></span>
<span data-ttu-id="108d7-124">Wenn der Workflow Auftrag angehalten wird, wird der Wert der **State** -Eigenschaft des Auftrags angehalten.</span><span class="sxs-lookup"><span data-stu-id="108d7-124">When the workflow job is suspended, the value of the **State** property of the job is Suspended.</span></span>

<span data-ttu-id="108d7-125">Das korrekte Anhalten ist von Prüfpunkten abhängig.</span><span class="sxs-lookup"><span data-stu-id="108d7-125">Suspending correctly relies on checkpoints.</span></span>
<span data-ttu-id="108d7-126">Der aktuelle Auftragsstatus, Metadaten und die Ausgabe werden im Prüfpunkt gespeichert, sodass der Workflow Auftrag ohne Verlust von Status oder Daten fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="108d7-126">The current job state, metadata, and output are saved in the checkpoint so the workflow job can be resumed without loss of state or data.</span></span>
<span data-ttu-id="108d7-127">Wenn der Workflow Auftrag keine Prüfpunkte aufweist, kann er nicht ordnungsgemäß angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="108d7-127">If the workflow job does not have checkpoints, it cannot be suspended correctly.</span></span>
<span data-ttu-id="108d7-128">Um Prüfpunkte zu einem Workflow hinzuzufügen, den Sie ausführen, verwenden Sie den allgemeinen *PSPersist* -Workflowparameter.</span><span class="sxs-lookup"><span data-stu-id="108d7-128">To add checkpoints to a workflow that you are running, use the *PSPersist* workflow common parameter.</span></span>
<span data-ttu-id="108d7-129">Sie können den *Force* -Parameter verwenden, um einen Workflow Auftrag sofort anzuhalten und einen Workflow Auftrag anzuhalten, der keine Prüfpunkte aufweist, aber die Aktion kann zu Zustands-und Datenverlust führen.</span><span class="sxs-lookup"><span data-stu-id="108d7-129">You can use the *Force* parameter to suspend any workflow job immediately and to suspend a workflow job that does not have checkpoints, but the action could cause loss of state and data.</span></span>

<span data-ttu-id="108d7-130">Bevor Sie ein Auftrags-Cmdlet für einen benutzerdefinierten Auftragstyp verwenden, z. b. einen Workflow Auftrag ( **psworkflowjob** ), importieren Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, entweder mithilfe des-Cmdlets Import-Module oder mithilfe von oder mithilfe eines Cmdlets im-Modul.</span><span class="sxs-lookup"><span data-stu-id="108d7-130">Before you use a Job cmdlet on a custom job type, such as a workflow job ( **PSWorkflowJob** ) import the module that supports the custom job type, either by using the Import-Module cmdlet or using or using a cmdlet in the module.</span></span>

<span data-ttu-id="108d7-131">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="108d7-131">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="108d7-132">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="108d7-132">EXAMPLES</span></span>

### <span data-ttu-id="108d7-133">Beispiel 1: aussetzen eines Workflow Auftrags nach Name</span><span class="sxs-lookup"><span data-stu-id="108d7-133">Example 1: Suspend a workflow job by name</span></span>

```
The first command creates the Get-SystemLog workflow. The workflow uses the CheckPoint-Workflow activity to define a checkpoint in the workflow.
#Sample WorkflowWorkflow Get-SystemLog
{
    $Events = Get-WinEvent -LogName System
    CheckPoint-Workflow
    InlineScript {\\Server01\Scripts\Analyze-SystemEvents.ps1 -Events $Events}
}

The second command uses the *AsJob* parameter that is common to all workflows to run the Get-SystemLog workflow as a background job. The command uses the *JobName* workflow common parameter to specify a friendly name for the workflow job.
PS C:\> Get-SystemLog -AsJob -JobName "Get-SystemLogJob"

The third command uses the **Get-Job** cmdlet to get the Get-SystemLogJob workflow job. The output shows that the value of the **PSJobTypeName** property is PSWorkflowJob.
PS C:\> Get-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Running     True            localhost   Get-SystemLog

The fourth command uses the **Suspend-Job** cmdlet to suspend the Get-SystemLogJob job. The job runs to the checkpoint and then suspends.
PS C:\> Suspend-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Suspended   True            localhost   Get-SystemLog
```

<span data-ttu-id="108d7-134">In diesem Beispiel wird veranschaulicht, wie ein Workflowauftrag angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="108d7-134">This example shows how to suspend a workflow job.</span></span>

### <span data-ttu-id="108d7-135">Beispiel 2: aussetzen und Fortsetzen eines Workflow Auftrags</span><span class="sxs-lookup"><span data-stu-id="108d7-135">Example 2: Suspend and resume a workflow job</span></span>

```
The first command suspends the LogWorkflowJob job.The command returns immediately. The output shows that the workflow job is still running, even though it is being suspended.
PS C:\> Suspend-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow

The second command uses the **Get-Job** cmdlet to get the LogWorkflowJob job. The output shows that the workflow job suspended successfully.
PS C:\> Get-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Suspended     True            localhost            LogWorkflow

The third command uses the **Get-Job** cmdlet to get the LogWorkflowJob job and the Resume-Job cmdlet to resume it. The output shows that the workflow job resumed successfully and is now running.
PS C:\> Get-Job -Name LogWorkflowJob | Resume-Job
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow
```

<span data-ttu-id="108d7-136">In diesem Beispiel wird veranschaulicht, wie ein Workflowauftrag angehalten und fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="108d7-136">This example shows how to suspend and resume a workflow job.</span></span>

### <span data-ttu-id="108d7-137">Beispiel 3: aussetzen eines Workflow Auftrags auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="108d7-137">Example 3: Suspend a workflow job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -Scriptblock {Suspend-Job -Filter @{CustomID="031589"}
```

<span data-ttu-id="108d7-138">Dieser Befehl verwendet das Cmdlet "Invoke-Command" zum Aussetzen eines Workflow Auftrags auf dem Remote Computer SRV01.</span><span class="sxs-lookup"><span data-stu-id="108d7-138">This command uses the Invoke-Command cmdlet to suspend a workflow job on the Srv01 remote computer.</span></span>
<span data-ttu-id="108d7-139">Der Wert des *Filter* -Parameters ist eine Hash Tabelle, die einen "CustomId"-Wert angibt.</span><span class="sxs-lookup"><span data-stu-id="108d7-139">The value of the *Filter* parameter is a hash table that specifies a CustomID value.</span></span>
<span data-ttu-id="108d7-140">Diese **CustomID** umfasst Auftragsmetadaten ( **PSPrivateMetadata** ).</span><span class="sxs-lookup"><span data-stu-id="108d7-140">This **CustomID** is job metadata ( **PSPrivateMetadata** ).</span></span>

### <span data-ttu-id="108d7-141">Beispiel 4: warten auf das Aussetzen des Workflow Auftrags</span><span class="sxs-lookup"><span data-stu-id="108d7-141">Example 4: Wait for the workflow job to suspend</span></span>

```
PS C:\> Suspend-Job VersionCheck -Wait
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
 5     VersionCheck  PSWorkflowJob      Suspended     True            localhost            LogWorkflow
```

<span data-ttu-id="108d7-142">Dieser Befehl hält den VersionCheck-Workflowauftrag an.</span><span class="sxs-lookup"><span data-stu-id="108d7-142">This command suspends the VersionCheck workflow job.</span></span>
<span data-ttu-id="108d7-143">Der Befehl verwendet den *Wait* -Parameter, um zu warten, bis der Workflowauftrag angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="108d7-143">The command uses the *Wait* parameter to wait until the workflow job is suspended.</span></span>
<span data-ttu-id="108d7-144">Wenn der Workflow Auftrag bis zum nächsten Prüfpunkt ausgeführt und angehalten wurde, wird der Befehl abgeschlossen und gibt das Auftrags Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="108d7-144">When the workflow job runs to the next checkpoint and is suspended, the command finishes and returns the job object.</span></span>

### <span data-ttu-id="108d7-145">Beispiel 5: erzwingen, dass ein Workflow Auftrag angehalten wird</span><span class="sxs-lookup"><span data-stu-id="108d7-145">Example 5: Force a workflow job to suspend</span></span>

```
PS C:\> Suspend-Job Maintenance -Force
```

<span data-ttu-id="108d7-146">Dieser Befehl erzwingt das Anhalten des Maintenance-Workflowauftrags</span><span class="sxs-lookup"><span data-stu-id="108d7-146">This command suspends the Maintenance workflow job forcibly.</span></span>
<span data-ttu-id="108d7-147">Der Wartungsauftrag weist keine Prüfpunkte auf.</span><span class="sxs-lookup"><span data-stu-id="108d7-147">The Maintenance job does not have checkpoints.</span></span>
<span data-ttu-id="108d7-148">Sie kann nicht ordnungsgemäß angehalten und nicht ordnungsgemäß fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="108d7-148">It cannot be suspended correctly and might not resume correctly.</span></span>

## <span data-ttu-id="108d7-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="108d7-149">PARAMETERS</span></span>

### <span data-ttu-id="108d7-150">-Filter</span><span class="sxs-lookup"><span data-stu-id="108d7-150">-Filter</span></span>
<span data-ttu-id="108d7-151">Gibt eine Hash Tabelle mit Bedingungen an.</span><span class="sxs-lookup"><span data-stu-id="108d7-151">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="108d7-152">Dieses Cmdlet hält Aufträge an, die alle Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="108d7-152">This cmdlet suspends jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="108d7-153">Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="108d7-153">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

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

### <span data-ttu-id="108d7-154">-Force</span><span class="sxs-lookup"><span data-stu-id="108d7-154">-Force</span></span>
<span data-ttu-id="108d7-155">Hält den Workflowauftrag sofort an.</span><span class="sxs-lookup"><span data-stu-id="108d7-155">Suspends the workflow job immediately.</span></span>
<span data-ttu-id="108d7-156">Diese Aktion kann zu einem Verlust des Zustands und der Daten führen.</span><span class="sxs-lookup"><span data-stu-id="108d7-156">This action could cause a loss of state and data.</span></span>

<span data-ttu-id="108d7-157">Standardmäßig wird der Workflowauftrag mit **Suspend-Job** bis zum nächsten Prüfpunkt ausgeführt und dann angehalten.</span><span class="sxs-lookup"><span data-stu-id="108d7-157">By default, **Suspend-Job** lets the workflow job run until the next checkpoint and then suspends it.</span></span>
<span data-ttu-id="108d7-158">Mit diesem Parameter können Sie auch Workflowaufträge ohne Prüfpunkte anhalten.</span><span class="sxs-lookup"><span data-stu-id="108d7-158">You can also use this parameter to suspend workflow jobs that do not have checkpoints.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: F

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="108d7-159">-Id</span><span class="sxs-lookup"><span data-stu-id="108d7-159">-Id</span></span>
<span data-ttu-id="108d7-160">Gibt die IDs von Aufträgen an, die von diesem Cmdlet angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="108d7-160">Specifies the IDs of jobs that this cmdlet suspends.</span></span>

<span data-ttu-id="108d7-161">Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="108d7-161">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="108d7-162">Es ist einfacher, sich zu merken und als die Instanz-ID einzugeben, aber es ist nur in der aktuellen Sitzung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="108d7-162">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="108d7-163">Sie können eine oder mehrere IDs (durch Kommas getrennt) eingeben.</span><span class="sxs-lookup"><span data-stu-id="108d7-163">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="108d7-164">Um die ID eines Auftrags zu ermitteln, verwenden Sie das Cmdlet "Get-Job".</span><span class="sxs-lookup"><span data-stu-id="108d7-164">To find the ID of a job, use the Get-Job cmdlet.</span></span>

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

### <span data-ttu-id="108d7-165">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="108d7-165">-InstanceId</span></span>
<span data-ttu-id="108d7-166">Gibt die Instanz-IDs von Aufträgen an, die von diesem Cmdlet angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="108d7-166">Specifies the instance IDs of jobs that this cmdlet suspends.</span></span>
<span data-ttu-id="108d7-167">Standardmäßig werden alle Aufträge fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="108d7-167">The default is all jobs.</span></span>

<span data-ttu-id="108d7-168">Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="108d7-168">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="108d7-169">Zum Ermitteln der Instanz-ID eines Auftrags verwenden Sie **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="108d7-169">To find the instance ID of a job, use **Get-Job** .</span></span>

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

### <span data-ttu-id="108d7-170">-Auftrag</span><span class="sxs-lookup"><span data-stu-id="108d7-170">-Job</span></span>
<span data-ttu-id="108d7-171">Gibt die Workflow Aufträge an, die von diesem Cmdlet beendet werden.</span><span class="sxs-lookup"><span data-stu-id="108d7-171">Specifies the workflow jobs that this cmdlet stops.</span></span>
<span data-ttu-id="108d7-172">Geben Sie eine Variable ein, die die Workflowaufträge enthält, oder einen Befehl, der die Workflowaufträge abruft.</span><span class="sxs-lookup"><span data-stu-id="108d7-172">Enter a variable that contains the workflow jobs or a command that gets the workflow jobs.</span></span>
<span data-ttu-id="108d7-173">Sie können Workflowaufträge auch an das **Suspend-Job** -Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="108d7-173">You can also pipe workflow jobs to the **Suspend-Job** cmdlet.</span></span>

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

### <span data-ttu-id="108d7-174">-Name</span><span class="sxs-lookup"><span data-stu-id="108d7-174">-Name</span></span>
<span data-ttu-id="108d7-175">Gibt die anzeigen Amen von Aufträgen an, die von diesem Cmdlet angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="108d7-175">Specifies friendly names of jobs that this cmdlet suspends.</span></span>
<span data-ttu-id="108d7-176">Geben Sie einen oder mehrere Workflowauftragsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="108d7-176">Enter one or more workflow job names.</span></span>
<span data-ttu-id="108d7-177">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="108d7-177">Wildcard characters are supported.</span></span>

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

### <span data-ttu-id="108d7-178">-State</span><span class="sxs-lookup"><span data-stu-id="108d7-178">-State</span></span>
<span data-ttu-id="108d7-179">Gibt einen Auftragsstatus an.</span><span class="sxs-lookup"><span data-stu-id="108d7-179">Specifies a job state.</span></span>
<span data-ttu-id="108d7-180">Dieses Cmdlet beendet nur Aufträge im angegebenen Zustand.</span><span class="sxs-lookup"><span data-stu-id="108d7-180">This cmdlet stops only jobs in the specified state.</span></span>
<span data-ttu-id="108d7-181">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="108d7-181">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="108d7-182">NotStarted</span><span class="sxs-lookup"><span data-stu-id="108d7-182">NotStarted</span></span>
- <span data-ttu-id="108d7-183">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="108d7-183">Running</span></span>
- <span data-ttu-id="108d7-184">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="108d7-184">Completed</span></span>
- <span data-ttu-id="108d7-185">Fehler</span><span class="sxs-lookup"><span data-stu-id="108d7-185">Failed</span></span>
- <span data-ttu-id="108d7-186">Beendet</span><span class="sxs-lookup"><span data-stu-id="108d7-186">Stopped</span></span>
- <span data-ttu-id="108d7-187">Blockiert</span><span class="sxs-lookup"><span data-stu-id="108d7-187">Blocked</span></span>
- <span data-ttu-id="108d7-188">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="108d7-188">Suspended</span></span>
- <span data-ttu-id="108d7-189">Getrennt</span><span class="sxs-lookup"><span data-stu-id="108d7-189">Disconnected</span></span>
- <span data-ttu-id="108d7-190">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="108d7-190">Suspending</span></span>
- <span data-ttu-id="108d7-191">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="108d7-191">Stopping</span></span>

<span data-ttu-id="108d7-192">**Suspend-Job** hält nur Workflow Aufträge im Status wird **ausgeführt** an.</span><span class="sxs-lookup"><span data-stu-id="108d7-192">**Suspend-Job** suspends only workflow jobs in the **Running** state.</span></span>

<span data-ttu-id="108d7-193">Weitere Informationen zu Auftrags Zuständen finden Sie unter [jobstate-Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="108d7-193">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="108d7-194">-Wait</span><span class="sxs-lookup"><span data-stu-id="108d7-194">-Wait</span></span>
<span data-ttu-id="108d7-195">Gibt an, dass dieses Cmdlet die Eingabeaufforderung unterdrückt, bis sich der Workflow Auftrag im angehaltenen Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="108d7-195">Indicates that this cmdlet suppresses the command prompt until the workflow job is in the suspended state.</span></span>
<span data-ttu-id="108d7-196">Standardmäßig wird **Suspend-Job** sofort zurückgegeben, auch wenn sich der Workflow Auftrag noch nicht im angehaltenen Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="108d7-196">By default, **Suspend-Job** returns immediately, even if the workflow job is not yet in the suspended state.</span></span>

<span data-ttu-id="108d7-197">Der *Wait* -Parameter entspricht der Weiterleitung eines **Suspend-Job-** Befehls an das **Wait-Job-** Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="108d7-197">The *Wait* parameter is equivalent to piping a **Suspend-Job** command to the **Wait-Job** cmdlet.</span></span>

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

### <span data-ttu-id="108d7-198">-Confirm</span><span class="sxs-lookup"><span data-stu-id="108d7-198">-Confirm</span></span>
<span data-ttu-id="108d7-199">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="108d7-199">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="108d7-200">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="108d7-200">-WhatIf</span></span>
<span data-ttu-id="108d7-201">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="108d7-201">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="108d7-202">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="108d7-202">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="108d7-203">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="108d7-203">CommonParameters</span></span>
<span data-ttu-id="108d7-204">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="108d7-204">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="108d7-205">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="108d7-205">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="108d7-206">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="108d7-206">INPUTS</span></span>

### <span data-ttu-id="108d7-207">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="108d7-207">System.Management.Automation.Job</span></span>
<span data-ttu-id="108d7-208">Sie können alle Arten von Aufträgen an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="108d7-208">You can pipe all types of jobs to this cmdlet.</span></span>
<span data-ttu-id="108d7-209">Wenn **Suspend-Job** jedoch einen Auftrag eines nicht unterstützten Typs erhält, wird ein Abbruch Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="108d7-209">However, if **Suspend-Job** gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="108d7-210">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="108d7-210">OUTPUTS</span></span>

### <span data-ttu-id="108d7-211">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="108d7-211">System.Management.Automation.Job</span></span>
<span data-ttu-id="108d7-212">Mit diesem Cmdlet werden die Aufträge zurückgegeben, die angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="108d7-212">This cmdlet returns the jobs that it suspended.</span></span>

## <span data-ttu-id="108d7-213">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="108d7-213">NOTES</span></span>

* <span data-ttu-id="108d7-214">Der Mechanismus und der Speicherort für einen angehaltenen Auftrag können je nach Auftragstyp unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="108d7-214">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="108d7-215">Beispielsweise werden angehaltene Workflowaufträge standardmäßig in einem Flatfilespeicher gespeichert, sie können jedoch auch in einer Datenbank gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="108d7-215">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a database.</span></span>
* <span data-ttu-id="108d7-216">Wenn Sie einen Workflowauftrag weiterleiten, der nicht den Status Running aufweist, zeigt **Suspend-Job** eine Warnmeldung an.</span><span class="sxs-lookup"><span data-stu-id="108d7-216">If you submit a workflow job that is not in the Running state, **Suspend-Job** displays a warning message.</span></span> <span data-ttu-id="108d7-217">Um die Warnung zu unterdrücken, verwenden Sie den allgemeinen *WarningAction* -Parameter mit dem Wert SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="108d7-217">To suppress the warning, use the *WarningAction* common parameter with a value of SilentlyContinue.</span></span>

  <span data-ttu-id="108d7-218">Wenn es sich bei einem Auftrag nicht um einen Typ handelt, der das Anhalten unterstützt, gibt **Suspend-Job** einen abschließenden Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="108d7-218">If a job is not of a type that supports suspending, **Suspend-Job** returns a terminating error.</span></span>

* <span data-ttu-id="108d7-219">Verwenden Sie den *State* -Parameter des **Get-Job-** Cmdlets, um Workflow Aufträge mit dem Status "angehalten" zu ermitteln, die angehalten wurden, einschließlich der von diesem Cmdlet angehaltenen Workflow Aufträge.</span><span class="sxs-lookup"><span data-stu-id="108d7-219">To find the workflow jobs that are suspended, including those that were suspended by this cmdlet, use the *State* parameter of the **Get-Job** cmdlet to get workflow jobs in the Suspended state.</span></span>
* <span data-ttu-id="108d7-220">Einige Auftragstypen verfügen über Optionen oder Eigenschaften, die das Anhalten des Auftrags durch Windows PowerShell verhindern.</span><span class="sxs-lookup"><span data-stu-id="108d7-220">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span> <span data-ttu-id="108d7-221">Wenn der Versuch, den Auftrag anzuhalten, fehlschlägt, überprüfen Sie, ob die Auftrags Optionen und-Eigenschaften das Anhalten zulassen.</span><span class="sxs-lookup"><span data-stu-id="108d7-221">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="108d7-222">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="108d7-222">RELATED LINKS</span></span>

[<span data-ttu-id="108d7-223">Get-Job</span><span class="sxs-lookup"><span data-stu-id="108d7-223">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="108d7-224">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="108d7-224">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="108d7-225">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="108d7-225">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="108d7-226">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="108d7-226">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="108d7-227">Start-Job</span><span class="sxs-lookup"><span data-stu-id="108d7-227">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="108d7-228">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="108d7-228">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="108d7-229">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="108d7-229">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="108d7-230">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="108d7-230">Wait-Job</span></span>](Wait-Job.md)
