---
description: Beschreibt das parallele Schlüsselwort, mit dem die Aktivitäten in einem Workflow parallel ausgeführt werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parallel
ms.openlocfilehash: 402e93672bbea4ec9b6bfda8d608f266f6c40a21
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221892"
---
# <a name="about-parallel"></a><span data-ttu-id="9a001-104">Informationen zu parallel</span><span class="sxs-lookup"><span data-stu-id="9a001-104">About Parallel</span></span>

## <a name="short-description"></a><span data-ttu-id="9a001-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9a001-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="9a001-106">Beschreibt das parallele Schlüsselwort, mit dem die Aktivitäten in einem Workflow parallel ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9a001-106">Describes the Parallel keyword, which runs the activities in a workflow in parallel.</span></span>

## <a name="long-description"></a><span data-ttu-id="9a001-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9a001-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="9a001-108">Das Schlüsselwort "parallel" führt Workflow Aktivitäten parallel aus.</span><span class="sxs-lookup"><span data-stu-id="9a001-108">The Parallel keyword runs workflow activities in parallel.</span></span> <span data-ttu-id="9a001-109">Dieses Schlüsselwort ist nur in Windows PowerShell-Workflows gültig.</span><span class="sxs-lookup"><span data-stu-id="9a001-109">This keyword is valid only in  Windows PowerShell  Workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="9a001-110">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9a001-110">SYNTAX</span></span>

```
workflow <Verb-Noun>
{
     Parallel
     {
          [<Activity>]
          [<Activity>]
        ...
     }
 }
```

## <a name="detailed-description"></a><span data-ttu-id="9a001-111">DETAILLIERTE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9a001-111">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="9a001-112">Die Befehle in einem Parallel-Skriptblock können gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9a001-112">The commands in a Parallel script block can run concurrently.</span></span> <span data-ttu-id="9a001-113">Die Reihenfolge, in der sie ausgeführt werden, ist nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9a001-113">The order in which they run is not determined.</span></span>

<span data-ttu-id="9a001-114">Der folgende Workflow enthält beispielsweise einen Parallel-Skriptblock, der Aktivitäten ausführt, die Prozesse und Dienste auf dem Computer abrufen.</span><span class="sxs-lookup"><span data-stu-id="9a001-114">For example, the following workflow includes a Parallel script block that runs activities that get processes and services on the computer.</span></span> <span data-ttu-id="9a001-115">Da die Befehle Get-Process und Get-Service unabhängig voneinander sind, können Sie gleichzeitig und in beliebiger Reihenfolge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9a001-115">Because the Get-Process and Get-Service commands are independent of each other, they can run concurrently and in any order.</span></span>

```powershell
workflow Test-Workflow
{
    Parallel
    {
         Get-Process
         Get-Service
    }
}
```

<span data-ttu-id="9a001-116">Das parallele Ausführen von Befehlen ist sehr effizient und verkürzt die Zeit, die zum Ausführen eines Workflows benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="9a001-116">Running commands in parallel is very efficient and reduces the time it takes to complete a workflow significantly.</span></span>

<span data-ttu-id="9a001-117">Verwenden Sie das Sequence-Schlüsselwort, um ausgewählte Befehle in einem parallelen Skriptblock in sequenzieller Reihenfolge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9a001-117">To run selected commands in a Parallel script block in sequential order, use the Sequence keyword.</span></span> <span data-ttu-id="9a001-118">Weitere Informationen finden Sie unter about_Sequence.</span><span class="sxs-lookup"><span data-stu-id="9a001-118">For more information, see about_Sequence.</span></span>

<span data-ttu-id="9a001-119">Um einen parallelen Skriptblock für Elemente in einer Auflistung auszuführen, verwenden Sie die Schlüsselwörter foreach oder foreach-parallel.</span><span class="sxs-lookup"><span data-stu-id="9a001-119">To run a Parallel script block on items in a collection, use the ForEach or ForEach -Parallel keywords.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a001-120">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="9a001-120">SEE ALSO</span></span>

<span data-ttu-id="9a001-121">["Schreiben eines Skript Workflows"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="9a001-121">["Writing a Script Workflow"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))</span></span>

[<span data-ttu-id="9a001-122">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="9a001-122">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[<span data-ttu-id="9a001-123">about_ForEach parallel</span><span class="sxs-lookup"><span data-stu-id="9a001-123">about_ForEach-Parallel</span></span>](about_ForEach-Parallel.md)

[<span data-ttu-id="9a001-124">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="9a001-124">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="9a001-125">Informationen über_Sequence</span><span class="sxs-lookup"><span data-stu-id="9a001-125">about_Sequence</span></span>](about_Sequence.md)

[<span data-ttu-id="9a001-126">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="9a001-126">about_Workflows</span></span>](about_workflows.md)
