---
description: Beschreibt das `Sequence` Schlüsselwort, das ausgewählte Aktivitäten sequenziell ausführt.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_sequence?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über_Sequence
ms.openlocfilehash: a9dd4fb24274fe4e1478ca69c734b43a2f196792
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221884"
---
# <a name="about-sequence"></a><span data-ttu-id="f089f-104">Informationen zur Sequenz</span><span class="sxs-lookup"><span data-stu-id="f089f-104">About Sequence</span></span>

## <a name="short-description"></a><span data-ttu-id="f089f-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f089f-105">Short description</span></span>

<span data-ttu-id="f089f-106">Beschreibt das `Sequence` Schlüsselwort, das ausgewählte Aktivitäten sequenziell ausführt.</span><span class="sxs-lookup"><span data-stu-id="f089f-106">Describes the `Sequence` keyword that runs selected activities sequentially.</span></span>

## <a name="long-description"></a><span data-ttu-id="f089f-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f089f-107">Long description</span></span>

<span data-ttu-id="f089f-108">Das `Sequence` Schlüsselwort führt ausgewählte Workflow Aktivitäten sequenziell aus.</span><span class="sxs-lookup"><span data-stu-id="f089f-108">The `Sequence` keyword runs selected workflow activities sequentially.</span></span> <span data-ttu-id="f089f-109">Workflow Aktivitäten werden in der Reihenfolge ausgeführt, in der Sie angezeigt werden und nicht gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f089f-109">Workflow activities run in the order that they appear and do not run concurrently.</span></span> <span data-ttu-id="f089f-110">Das `Sequence` Schlüsselwort ist nur in einem PowerShell-Workflow gültig.</span><span class="sxs-lookup"><span data-stu-id="f089f-110">The `Sequence` keyword is only valid in a PowerShell Workflow.</span></span>

<span data-ttu-id="f089f-111">Das `Sequence` Schlüsselwort wird in einem `Parallel` Skriptblock verwendet, um ausgewählte Befehle sequenziell auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f089f-111">The `Sequence` keyword is used in a `Parallel` script block to run selected commands sequentially.</span></span>

<span data-ttu-id="f089f-112">Da Workflow Aktivitäten standardmäßig sequenziell ausgeführt werden, `Sequence` ist das Schlüsselwort nur in einem `Parallel` Skriptblock wirksam.</span><span class="sxs-lookup"><span data-stu-id="f089f-112">Because workflow activities run sequentially by default, the `Sequence` keyword is only effective in a `Parallel` script block.</span></span> <span data-ttu-id="f089f-113">Wenn das `Sequence` Schlüsselwort nicht in einem `Parallel` Skriptblock enthalten ist, ist es gültig, aber nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="f089f-113">If the `Sequence` keyword isn't included in a `Parallel` script block, it's valid but ineffective.</span></span>

<span data-ttu-id="f089f-114">`Sequence`Mit dem Script-Block können Sie weitere Befehle parallel ausführen, indem Sie abhängige Befehle sequenziell ausführen können.</span><span class="sxs-lookup"><span data-stu-id="f089f-114">The `Sequence` script block lets you run more commands in parallel by allowing you to run dependent commands sequentially.</span></span>

## <a name="syntax"></a><span data-ttu-id="f089f-115">Syntax</span><span class="sxs-lookup"><span data-stu-id="f089f-115">Syntax</span></span>

### <a name="workflow-using-sequence"></a><span data-ttu-id="f089f-116">Workflow mit Sequenz</span><span class="sxs-lookup"><span data-stu-id="f089f-116">Workflow using Sequence</span></span>

```
workflow <Verb-Noun>
{
    Sequence
    {
        [<Activity>]
        [<Activity>]
        # ...
    }
}
```

### <a name="workflow-using-parallel-and-sequence"></a><span data-ttu-id="f089f-117">Workflow mit parallel und Sequence</span><span class="sxs-lookup"><span data-stu-id="f089f-117">Workflow using Parallel and Sequence</span></span>

```
workflow <Verb-Noun>
{
    Parallel
    {
        [<Activity>]
        Sequence
        {
            [<Activity>]
            [<Activity>]
            # ...
        }
    }
}
```

## <a name="detailed-description"></a><span data-ttu-id="f089f-118">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f089f-118">Detailed description</span></span>

<span data-ttu-id="f089f-119">Die Befehle in einem `Parallel`-Skriptblock können gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f089f-119">The commands in a `Parallel` script block can run concurrently.</span></span> <span data-ttu-id="f089f-120">Die Reihenfolge, in der sie ausgeführt werden, ist nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f089f-120">The order in which they run is not determined.</span></span> <span data-ttu-id="f089f-121">Diese Funktion verbessert die Leistung eines Skript Workflows.</span><span class="sxs-lookup"><span data-stu-id="f089f-121">This feature improves the performance of a script workflow.</span></span>

<span data-ttu-id="f089f-122">Sie können einen `Sequence` Skriptblock verwenden, um ausgewählte Aktivitäten sequenziell auszuführen, auch wenn die Aktivitäten in einem `Parallel` Skriptblock angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f089f-122">You can use a `Sequence` script block to run selected activities sequentially, even though the activities appear in a `Parallel` script block.</span></span>

<span data-ttu-id="f089f-123">Die Aktivitäten in einem `Sequence` Skriptblock werden nacheinander in der Reihenfolge ausgeführt, in der Sie aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="f089f-123">The activities in a `Sequence` script block run consecutively in the order that they are listed.</span></span> <span data-ttu-id="f089f-124">Eine Aktivität in einem `Sequence` Skriptblock wird erst gestartet, nachdem die vorherige Aktivität abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="f089f-124">An activity in a `Sequence` script block starts only after the previous activity completes.</span></span>

<span data-ttu-id="f089f-125">Wenn der Skriptblock jedoch `Sequence` in einem `Parallel` Skriptblock angezeigt wird, wird die Reihenfolge, in der der `Sequence` Skriptblock ausgeführt wird, nicht ermittelt.</span><span class="sxs-lookup"><span data-stu-id="f089f-125">However, when the `Sequence` script block appears in a `Parallel` script block, the order in which the `Sequence` script block runs isn't determined.</span></span> <span data-ttu-id="f089f-126">Sie kann vor, nach oder gleichzeitig mit anderen Aktivitäten im `Parallel` Skriptblock ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f089f-126">It might run before, after, or concurrent with other activities in the `Parallel` script block.</span></span>

<span data-ttu-id="f089f-127">Der folgende Workflow enthält z. b `Parallel` . einen Skriptblock, der Aktivitäten ausführt, die Prozesse und Dienste auf dem Computer erhalten.</span><span class="sxs-lookup"><span data-stu-id="f089f-127">For example, the following workflow includes a `Parallel` script block that runs activities that get processes and services on the computer.</span></span> <span data-ttu-id="f089f-128">Der `Parallel` Skriptblock enthält einen `Sequence` Skriptblock, der Informationen aus einer Datei abruft und die Informationen als Eingabe für ein Skript verwendet.</span><span class="sxs-lookup"><span data-stu-id="f089f-128">The `Parallel` script block contains a `Sequence` script block that gets information from a file and uses the information as input to a script.</span></span>

<span data-ttu-id="f089f-129">Die `Get-Process` `Get-Service` -,-und-hotfixbezogenen Befehle sind voneinander unabhängig.</span><span class="sxs-lookup"><span data-stu-id="f089f-129">The `Get-Process`, `Get-Service`, and hotfix-related commands are independent of each other.</span></span> <span data-ttu-id="f089f-130">Die Befehle können gleichzeitig oder in beliebiger Reihenfolge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f089f-130">The commands can run concurrently or in any order.</span></span> <span data-ttu-id="f089f-131">Der Befehl, mit dem die Hotfixinformationen abgerufen werden, muss jedoch vor dem Befehl ausgeführt werden, der ihn verwendet.</span><span class="sxs-lookup"><span data-stu-id="f089f-131">But, the command that gets the hotfix information must run before the command that uses it.</span></span>

```powershell
workflow Test-Workflow
{
    Parallel
    {
    Get-Process
    Get-Service

    Sequence
    {
        $Hotfix = Get-Content 'D:\HotFixes\Required.txt'
        Foreach ($h in $Hotfix) {'D:\Scripts\Verify-Hotfix' -Hotfix $h}
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="f089f-132">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="f089f-132">See also</span></span>

[<span data-ttu-id="f089f-133">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="f089f-133">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[<span data-ttu-id="f089f-134">about_ForEach parallel</span><span class="sxs-lookup"><span data-stu-id="f089f-134">about_ForEach-Parallel</span></span>](about_ForEach-Parallel.md)

[<span data-ttu-id="f089f-135">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="f089f-135">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="f089f-136">about_Parallel</span><span class="sxs-lookup"><span data-stu-id="f089f-136">about_Parallel</span></span>](about_Parallel.md)

[<span data-ttu-id="f089f-137">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="f089f-137">about_Workflows</span></span>](about_Workflows.md)

[<span data-ttu-id="f089f-138">Erstellen eines Workflows mit einem Windows PowerShell-Skript</span><span class="sxs-lookup"><span data-stu-id="f089f-138">Creating a Workflow by Using a Windows PowerShell Script</span></span>](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)
