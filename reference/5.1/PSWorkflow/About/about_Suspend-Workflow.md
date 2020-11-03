---
description: Beschreibt die- `Suspend-Workflow` Aktivität, die den Workflow anhält, in dem die-Aktivität angezeigt wird.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_suspend-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Workflow about_Suspend
ms.openlocfilehash: cbe5386ae5aa4bd863079fde240ddf2ce5384727
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221863"
---
# <a name="about-suspend-workflow"></a><span data-ttu-id="938ad-104">Informationen zu Suspend-Workflow</span><span class="sxs-lookup"><span data-stu-id="938ad-104">About Suspend-Workflow</span></span>

## <a name="short-description"></a><span data-ttu-id="938ad-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="938ad-105">Short description</span></span>

<span data-ttu-id="938ad-106">Beschreibt die- `Suspend-Workflow` Aktivität, die den Workflow anhält, in dem die-Aktivität angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="938ad-106">Describes the `Suspend-Workflow` activity, which suspends the workflow in which the activity appears.</span></span>

## <a name="long-description"></a><span data-ttu-id="938ad-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="938ad-107">Long description</span></span>

<span data-ttu-id="938ad-108">Die- `Suspend-Workflow` Aktivität beendet die Workflow Verarbeitung vorübergehend innerhalb des Workflows.</span><span class="sxs-lookup"><span data-stu-id="938ad-108">The `Suspend-Workflow` activity temporarily stops workflow processing from within the workflow.</span></span> <span data-ttu-id="938ad-109">Vor dem Anhalten nimmt der Windows PowerShell-Workflow einen Prüfpunkt an, sodass der Zustand und die Daten des Workflows beibehalten werden und der Workflow vom Unterbrechungs Punkt fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="938ad-109">Before suspending, Windows PowerShell Workflow takes a checkpoint so the workflow's state and data are preserved and the workflow can resume from the suspension point.</span></span>

<span data-ttu-id="938ad-110">Zum Fortsetzen des Workflows verwendet der Benutzer, der den Workflow durchführt, das- `Resume-Job` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="938ad-110">To resume the workflow, the user running the workflow uses the `Resume-Job` cmdlet.</span></span> <span data-ttu-id="938ad-111">Ein Workflow kann nicht innerhalb des Workflows fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="938ad-111">You can't resume a workflow from within the workflow.</span></span>

## <a name="syntax"></a><span data-ttu-id="938ad-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="938ad-112">Syntax</span></span>

```
workflow <Verb-Noun>
{
    Suspend-Workflow
}
```

## <a name="detailed-description"></a><span data-ttu-id="938ad-113">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="938ad-113">Detailed description</span></span>

<span data-ttu-id="938ad-114">`Suspend-Workflow`Beendet den Workflow vorübergehend und gibt ein Auftrags Objekt zurück, das den Workflow Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="938ad-114">The `Suspend-Workflow` temporarily stops the workflow and returns a job object that represents the workflow job.</span></span> <span data-ttu-id="938ad-115">Ein Auftrags Objekt wird auch dann zurückgegeben, wenn Sie den Workflow nicht als Auftrag ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="938ad-115">A job object is returned even if you didn't run the workflow as a job.</span></span> <span data-ttu-id="938ad-116">Beispielsweise mit dem allgemeinen Workflow Parameter **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="938ad-116">For example, such as by using the **AsJob** workflow common parameter.</span></span> <span data-ttu-id="938ad-117">Der Auftrags **Status ist "** angehalten".</span><span class="sxs-lookup"><span data-stu-id="938ad-117">The job state is **Suspended**.</span></span>

<span data-ttu-id="938ad-118">Sie können die Job-Cmdlets verwenden, um den angehaltenen Workflow Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="938ad-118">You can use the job cmdlets to manage the suspended workflow job.</span></span> <span data-ttu-id="938ad-119">Verwenden Sie das-Cmdlet, um den Workflow Auftrag fortzusetzen `Resume-Job` .</span><span class="sxs-lookup"><span data-stu-id="938ad-119">To resume the workflow job, use the `Resume-Job` cmdlet.</span></span>

<span data-ttu-id="938ad-120">Wenn Sie den Workflow Auftrag fortsetzen, wird der Workflow mit dem Befehl fortgesetzt, der der `Suspend-Workflow` Aktivität folgt.</span><span class="sxs-lookup"><span data-stu-id="938ad-120">When you resume the workflow job, the workflow resumes at the command that follows the `Suspend-Workflow` activity.</span></span>

<span data-ttu-id="938ad-121">Der folgende Workflow schließt z. b. die- `Suspend-Workflow` Aktivität ein.</span><span class="sxs-lookup"><span data-stu-id="938ad-121">For example, the following workflow includes the `Suspend-Workflow` activity.</span></span>
<span data-ttu-id="938ad-122">Wenn Sie den Workflow ausführen, führt er die- `Get-Date` Aktivität aus, speichert die Ausgabe in der `$a` Variablen, hält den Workflow an und gibt ein Auftrags Objekt zurück, das den angehaltenen Workflow darstellt.</span><span class="sxs-lookup"><span data-stu-id="938ad-122">When you run the workflow, it runs the `Get-Date` activity, saves its output in the `$a` variable, and then suspends the workflow, and returns a job object that represents the suspended workflow.</span></span> <span data-ttu-id="938ad-123">Der Auftragstyp ist " **psworkflowjob** ".</span><span class="sxs-lookup"><span data-stu-id="938ad-123">The job type is **PSWorkflowJob**.</span></span>

<span data-ttu-id="938ad-124">Sie können die Job-Cmdlets, z `Get-Job` . b., verwenden, um den Workflow Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="938ad-124">You can use the job cmdlets, such as `Get-Job`, to manage the workflow job.</span></span>

```powershell
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

Test-Suspend
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Suspended  True         localhost Test-Suspend
```

## <a name="resuming-a-workflow-job"></a><span data-ttu-id="938ad-125">Fortsetzen eines Workflow Auftrags</span><span class="sxs-lookup"><span data-stu-id="938ad-125">Resuming a workflow job</span></span>

<span data-ttu-id="938ad-126">Verwenden Sie das-Cmdlet, um den Workflow Auftrag fortzusetzen `Resume-Job` .</span><span class="sxs-lookup"><span data-stu-id="938ad-126">To resume the workflow job, use the `Resume-Job` cmdlet.</span></span> <span data-ttu-id="938ad-127">Das Cmdlet `Resume-Job` gibt das Workflowauftragsobjekt sofort zurück, obgleich es möglicherweise noch nicht fortgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="938ad-127">The `Resume-Job` cmdlet returns the workflow job object immediately, even though it might not yet be resumed.</span></span> <span data-ttu-id="938ad-128">Um zu warten, bis der Auftrag fortgesetzt wird, verwenden Sie den **Wait** -Parameter, oder verwenden Sie das `Get-Job` Cmdlet, um das aktuelle Auftrags Objekt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="938ad-128">To wait for the job to be resumed, use the **Wait** parameter, or use the `Get-Job` cmdlet to get the current job object.</span></span>

```powershell
Resume-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State    HasMoreData  Location  Command
--  ----  -------------  -----    -----------  --------  -------
8   Job8  PSWorkflowJob  Running  True         localhost Test-Suspend
```

```powershell
Get-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Completed  True         localhost Test-Suspend
```

## <a name="getting-the-output-of-a-workflow-job"></a><span data-ttu-id="938ad-129">Erhalten der Ausgabe eines Workflow Auftrags</span><span class="sxs-lookup"><span data-stu-id="938ad-129">Getting the output of a workflow job</span></span>

<span data-ttu-id="938ad-130">Verwenden Sie das-Cmdlet, um die Ausgabe eines Workflow Auftrags zu erhalten `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="938ad-130">To get the output of a workflow job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="938ad-131">Die Ausgabe zeigt, dass der Workflow mit dem Befehl fortgesetzt wird, der mit dem `Suspend-Workflow` Cmdlet gefolgt ist.</span><span class="sxs-lookup"><span data-stu-id="938ad-131">The output shows that the workflow resumed at the command that followed the `Suspend-Workflow` cmdlet.</span></span> <span data-ttu-id="938ad-132">Der Wert der `$a` Variablen, die vor der Unterbrechung aufgefüllt wurde, ist für den Workflow verfügbar, wenn er fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="938ad-132">The value of the `$a` variable, which was populated before the suspension, is available to the workflow when it resumes.</span></span>

```powershell
Get-Job -Name Job8 | Receive-Job
```

```Output
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
PSComputerName    : localhost
```

## <a name="see-also"></a><span data-ttu-id="938ad-133">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="938ad-133">See also</span></span>

[<span data-ttu-id="938ad-134">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="938ad-134">about_Workflows</span></span>](about_Workflows.md)

[<span data-ttu-id="938ad-135">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="938ad-135">about_WorkflowCommonParameters</span></span>](about_WorkflowCommonParameters.md)

<span data-ttu-id="938ad-136">[Psworkflow](xref:PSWorkflow) -Cmdlets</span><span class="sxs-lookup"><span data-stu-id="938ad-136">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="938ad-137">Handbuch zu Workflows</span><span class="sxs-lookup"><span data-stu-id="938ad-137">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="938ad-138">Schreiben Sie einen Windows PowerShell-Workflow</span><span class="sxs-lookup"><span data-stu-id="938ad-138">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
