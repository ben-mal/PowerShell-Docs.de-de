---
description: Beschreibt das `ForEach -Parallel` Sprachkonstrukt in Windows PowerShell Workflow.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_foreach-parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Parallel about_Foreach
ms.openlocfilehash: 1012b45396b65d424dacac067c2af8d3b6823f92
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221908"
---
# <a name="about-foreach-parallel"></a><span data-ttu-id="881c7-104">Informationen zu Foreach-Parallel</span><span class="sxs-lookup"><span data-stu-id="881c7-104">About Foreach-Parallel</span></span>

## <a name="short-description"></a><span data-ttu-id="881c7-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="881c7-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="881c7-106">Beschreibt das `ForEach -Parallel` Sprachkonstrukt in Windows PowerShell Workflow.</span><span class="sxs-lookup"><span data-stu-id="881c7-106">Describes the `ForEach -Parallel` language construct in Windows PowerShell Workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="881c7-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="881c7-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="881c7-108">Der **parallele** Parameter des `ForEach` Schlüssel Worts führt die Befehle in einem `ForEach` Skriptblock einmal für jedes Element in einer bestimmten Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="881c7-108">The **Parallel** parameter of the `ForEach` keyword runs the commands in a `ForEach` script block once for each item in a specified collection.</span></span>

<span data-ttu-id="881c7-109">Die Elemente in der Auflistung, z. b. ein Datenträger in einer Sammlung von Datenträgern, werden parallel verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="881c7-109">The items in the collection, such as a disk in a collection of disks, are processed in parallel.</span></span> <span data-ttu-id="881c7-110">Die Befehle im Skriptblock werden sequenziell für jedes Element in der Sammlung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="881c7-110">The commands in the script block run sequentially on each item in the collection.</span></span>

<span data-ttu-id="881c7-111">`ForEach -Parallel` ist nur in einem Windows PowerShell-Workflow gültig.</span><span class="sxs-lookup"><span data-stu-id="881c7-111">`ForEach -Parallel` is valid only in a Windows PowerShell Workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="881c7-112">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="881c7-112">SYNTAX</span></span>

```
ForEach -Parallel ($<item> in $<collection>)
{
    [<Activity1>]
    [<Activity2>]
    ...
}
```

### <a name="detailed-description"></a><span data-ttu-id="881c7-113">DETAILLIERTE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="881c7-113">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="881c7-114">Wie die foreach-Anweisung in Windows PowerShell muss die Variable, die die Auflistung enthält, `$<collection>` vor der-Anweisung definiert werden `ForEach -Parallel` , aber die Variable, die das aktuelle Element darstellt, `$<item>` wird in der- `ForEach -Parallel` Anweisung definiert.</span><span class="sxs-lookup"><span data-stu-id="881c7-114">Like the ForEach statement in Windows PowerShell, the variable that contains collection `$<collection>` must be defined before the `ForEach -Parallel` statement, but the variable that represents the current item `$<item>` is defined in the `ForEach -Parallel` statement.</span></span>

<span data-ttu-id="881c7-115">Das `ForEach -Parallel` -Konstrukt unterscheidet sich vom `ForEach` -Schlüsselwort und dem **parallel** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="881c7-115">The `ForEach -Parallel` construct is different from the `ForEach` keyword and the **Parallel** parameter.</span></span> <span data-ttu-id="881c7-116">Mit dem- `ForEach` Schlüsselwort werden die Elemente in der-Auflistung nacheinander verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="881c7-116">The `ForEach` keyword processes the items in the collection in sequence.</span></span> <span data-ttu-id="881c7-117">Der **parallele** Parameter führt Befehle parallel in einem Skriptblock aus.</span><span class="sxs-lookup"><span data-stu-id="881c7-117">The **Parallel** parameter runs commands in a script block in parallel.</span></span> <span data-ttu-id="881c7-118">Sie können einen parallelen Skriptblock in einen `ForEach -Parallel` Skriptblock einschließen.</span><span class="sxs-lookup"><span data-stu-id="881c7-118">You can enclose a Parallel script block in a `ForEach -Parallel` script block.</span></span>

<span data-ttu-id="881c7-119">Die Zielcomputer in einem Workflow, z. b. die durch den allgemeinen Workflow Parameter **pscomputername** angegebenen, werden immer parallel verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="881c7-119">The target computers in a workflow, such as those specified by the **PSComputerName** workflow common parameter, are always processed in parallel.</span></span>
<span data-ttu-id="881c7-120">Sie müssen `ForEach -Parallel` für diesen Zweck nicht das Schlüsselwort angeben.</span><span class="sxs-lookup"><span data-stu-id="881c7-120">You do not need to specify the `ForEach -Parallel` keyword for this purpose.</span></span>

### <a name="examples"></a><span data-ttu-id="881c7-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="881c7-121">EXAMPLES</span></span>

<span data-ttu-id="881c7-122">Der folgende Workflow enthält eine-Anweisung, die die Datenträger verarbeitet, die von der-Aktivität abgerufen werden `ForEach -Parallel` `Get-Disk` .</span><span class="sxs-lookup"><span data-stu-id="881c7-122">The following workflow contains a `ForEach -Parallel` statement that processes the disks that the `Get-Disk` activity gets.</span></span> <span data-ttu-id="881c7-123">Die Befehle im `ForEach -Parallel` Skriptblock werden nacheinander ausgeführt, auf den Datenträgern werden Sie jedoch parallel ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="881c7-123">The commands in the `ForEach -Parallel` script block run sequentially, but they run on the disks in parallel.</span></span> <span data-ttu-id="881c7-124">Die Datenträger werden möglicherweise gleichzeitig und in beliebiger Reihenfolge verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="881c7-124">The disks might be processed concurrently and in any order.</span></span>

```powershell
workflow Test-Workflow
{
    $Disks = Get-Disk

    # The disks are processed in parallel.
    ForEach -Parallel ($Disk in $Disks)
    {
        # The commands run sequentially on each disk.
        $DiskPath = $Disk.Path
        $Disk | Initialize-Disk
        Set-Disk -Path $DiskPath
    }
}

workflow Test-Workflow
{
    #Run commands in parallel.
    Parallel
    {
        Get-Process
        Get-Service
    }

   $Disks = Get-Disk

   # The disks are processed in parallel.
   ForEach -Parallel ($Disk in $Disks)
   {
       # The commands run in parallel on each disk.
       Parallel
       {
           Initialize-Disk
           InlineScript {.\Get-DiskInventory}
       }
   }
}
```

## <a name="see-also"></a><span data-ttu-id="881c7-125">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="881c7-125">SEE ALSO</span></span>

[<span data-ttu-id="881c7-126">Writing a Script Workflow</span><span class="sxs-lookup"><span data-stu-id="881c7-126">Writing a Script Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)

[<span data-ttu-id="881c7-127">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="881c7-127">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_ForEach.md)

[<span data-ttu-id="881c7-128">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="881c7-128">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="881c7-129">about_Parallel</span><span class="sxs-lookup"><span data-stu-id="881c7-129">about_Parallel</span></span>](about_Parallel.md)

[<span data-ttu-id="881c7-130">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="881c7-130">about_Workflows</span></span>](about_Workflows.md)
