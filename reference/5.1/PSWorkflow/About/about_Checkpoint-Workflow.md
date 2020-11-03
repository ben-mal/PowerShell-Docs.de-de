---
description: Beschreibt die Checkpoint-Workflow-Aktivität, die einen Prüfpunkt in einem Workflow annimmt.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_checkpoint-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Workflow about_Checkpoint
ms.openlocfilehash: 223deb07ff6ed387cf04736116ea0ce3f998bb59
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221911"
---
# <a name="about-checkpoint-workflow"></a><span data-ttu-id="6d68c-104">Informationen zu Checkpoint-Workflow</span><span class="sxs-lookup"><span data-stu-id="6d68c-104">About Checkpoint-Workflow</span></span>

## <a name="short-description"></a><span data-ttu-id="6d68c-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6d68c-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="6d68c-106">Beschreibt die Checkpoint-Workflow-Aktivität, die einen Prüfpunkt in einem Workflow annimmt.</span><span class="sxs-lookup"><span data-stu-id="6d68c-106">Describes the Checkpoint-Workflow activity, which takes a checkpoint in a workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="6d68c-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6d68c-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="6d68c-108">Die Checkpoint-Workflow-Aktivität nimmt einen Prüfpunkt an, der den Zustand und die Daten im Workflow speichert.</span><span class="sxs-lookup"><span data-stu-id="6d68c-108">The Checkpoint-Workflow activity takes a checkpoint, which saves state and data in the workflow.</span></span> <span data-ttu-id="6d68c-109">Wenn der Workflow angehalten oder unterbrochen wird, kann er vom letzten Prüfpunkt aus fortgesetzt werden, anstatt neu gestartet werden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="6d68c-109">If the workflow is suspended or interrupted, it can be resumed from the most recent checkpoint, rather than having to be restarted.</span></span>

<span data-ttu-id="6d68c-110">Die Checkpoint-Workflow Aktivität ist nur in einem Workflow gültig.</span><span class="sxs-lookup"><span data-stu-id="6d68c-110">The Checkpoint-Workflow activity is valid only in a workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="6d68c-111">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6d68c-111">SYNTAX</span></span>

```
Workflow <Verb-Noun>
{
    Checkpoint-Workflow
}
```

<span data-ttu-id="6d68c-112">Die Checkpoint-Workflow-Aktivität akzeptiert keine Parameter, einschließlich der allgemeinen Parameter und allgemeinen Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="6d68c-112">The Checkpoint-Workflow activity does not accept any parameters, including common parameters and workflow common parameters.</span></span>

<span data-ttu-id="6d68c-113">Sie können den Checkpoint-Activity Prüfpunkt an einer beliebigen Stelle in einem Workflow nach der cmdletbinding-oder Param-Anweisung platzieren.</span><span class="sxs-lookup"><span data-stu-id="6d68c-113">You can place the Checkpoint-Activity checkpoint anywhere in a workflow after the CmdletBinding or Param statement.</span></span> <span data-ttu-id="6d68c-114">Beim Platzieren von Prüfpunkten sollten Sie jedoch die Leistungseinbußen beim Sammeln der Daten und beim Schreiben der Daten auf den Datenträger auf dem Computer, auf dem der Workflow ausgeführt wird, überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6d68c-114">However, when placing checkpoints, consider the performance cost of collecting the data and writing it to disk on the computer that is running the workflow.</span></span>

<span data-ttu-id="6d68c-115">Sie können davon ausgehen, dass der Zeitaufwand für die erneute Ausführung eines unterbrochenen Workflowabschnitts höher ist als der Zeitaufwand für das Schreiben von Prüfpunktstatus und -daten auf den Datenträger.</span><span class="sxs-lookup"><span data-stu-id="6d68c-115">Be sure that the time it takes to rerun a section of the workflow if it is interrupted is greater than the time it takes to write the checkpoint state and data to disk.</span></span>

<span data-ttu-id="6d68c-116">Sie sollten Prüfpunkte nach kritischen Schritten übernehmen, damit der Workflow fortgesetzt werden kann, anstatt neu gestartet zu werden.</span><span class="sxs-lookup"><span data-stu-id="6d68c-116">Consider taking checkpoints after critical steps so the workflow can be resumed rather than restarted.</span></span> <span data-ttu-id="6d68c-117">Nehmen Sie z. b. einen Prüfpunkt auf, der nicht idempotent ist.</span><span class="sxs-lookup"><span data-stu-id="6d68c-117">For example, take a checkpoint after commands that are not idempotent.</span></span>

### <a name="about-checkpoints"></a><span data-ttu-id="6d68c-118">Informationen zu Prüfpunkten</span><span class="sxs-lookup"><span data-stu-id="6d68c-118">ABOUT CHECKPOINTS</span></span>

<span data-ttu-id="6d68c-119">Ein Prüfpunkt ist eine Momentaufnahme des aktuellen Zustands des Workflows, einschließlich der aktuellen Werte von Variablen, und beliebiger, bis zu diesem Punkt generierter Ausgaben, die auf dem Datenträger gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="6d68c-119">A checkpoint is a snapshot of the current state of the workflow, including the current values of variables, and any output generated up to that point, and it saves it to disk.</span></span>

<span data-ttu-id="6d68c-120">Wenn ein Workflow absichtlich oder versehentlich unterbrochen wird, verwendet der Windows PowerShell-Workflow automatisch die Daten im neuesten Prüfpunkt, um den Workflow wiederherzustellen und fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="6d68c-120">If a workflow is interrupted, intentionally or unintentionally, Windows PowerShell Workflow automatically uses the data in newest checkpoint to recover and resume the workflow.</span></span>

<span data-ttu-id="6d68c-121">Wenn Sie den Workflow als Auftrag ausführen, z. b. mit dem allgemeinen Workflow Parameter AsJob, werden die Workflow Prüfpunkte so lange beibehalten, bis Sie den Auftrag löschen, z. b. mithilfe des Remove-Job-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6d68c-121">When you run the workflow as a job, such as by using the AsJob workflow common parameter, the workflow checkpoints are retained until you delete the job, such as by using the Remove-Job cmdlet.</span></span>
<span data-ttu-id="6d68c-122">Andernfalls werden Workflow Prüfpunkte gelöscht, wenn der Workflow abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="6d68c-122">Otherwise, workflow checkpoints are deleted when the workflow completes.</span></span>

### <a name="other-checkpointing-techniques"></a><span data-ttu-id="6d68c-123">andere Prüf Punkt Techniken</span><span class="sxs-lookup"><span data-stu-id="6d68c-123">OTHER CHECKPOINTING TECHNIQUES</span></span>

<span data-ttu-id="6d68c-124">Zusätzlich zur Checkpoint-Workflow Aktivität unterstützt der Windows PowerShell-Workflow auch andere Prüf Punkt Techniken, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="6d68c-124">In addition to the Checkpoint-Workflow activity, Windows PowerShell Workflow supports other checkpointing techniques, including the following:</span></span>

- <span data-ttu-id="6d68c-125">Allgemeiner Workflowparameter "PSPersist"</span><span class="sxs-lookup"><span data-stu-id="6d68c-125">PSPersist workflow common parameter</span></span>
- <span data-ttu-id="6d68c-126">Allgemeiner Aktivitätsparameter "PSPersist"</span><span class="sxs-lookup"><span data-stu-id="6d68c-126">PSPersist activity common parameter</span></span>
- <span data-ttu-id="6d68c-127">Pspersistpreference-Variable (in einem Workflow)</span><span class="sxs-lookup"><span data-stu-id="6d68c-127">PSPersistPreference variable (in a workflow)</span></span>

<span data-ttu-id="6d68c-128">Weitere Informationen zum Hinzufügen eines Prüf Punkts zu einem Workflow finden Sie unter "Vorgehensweise beim Hinzufügen von Prüfpunkten zu einem Workflow".</span><span class="sxs-lookup"><span data-stu-id="6d68c-128">For more information about adding a checkpoint to a workflow, see "How to Add Checkpoints to a Workflow."</span></span>

## <a name="examples"></a><span data-ttu-id="6d68c-129">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6d68c-129">EXAMPLES</span></span>

<span data-ttu-id="6d68c-130">Der folgende Workflow schließt einen aufzurufenden Checkpoint-Workflow Aktivität ein, nachdem eine Funktion mit langer Laufzeit und ein Skript, das Daten gemeinsam nutzen, fertiggestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="6d68c-130">The following workflow includes a call to the Checkpoint-Workflow activity after completing a long-running function and a script that share data.</span></span>

```powershell
Workflow Test-Workflow
{
    $a = Invoke-LongRunningFunction
    InlineScript { \\Server\Share\Get-DataPacks.ps1 $Using:a}
    Checkpoint-Workflow

    Invoke-LongRunningFunction
    {
        ...
    }
}
```

## <a name="see-also"></a><span data-ttu-id="6d68c-131">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="6d68c-131">SEE ALSO</span></span>

[<span data-ttu-id="6d68c-132">Schreiben Sie einen Windows PowerShell-Workflow</span><span class="sxs-lookup"><span data-stu-id="6d68c-132">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
