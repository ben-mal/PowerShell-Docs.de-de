---
ms.date: 08/03/2020
keywords: powershell,cmdlet
title: Anhang 1 – Kompatibilitätsaliase
description: PowerShell verfügt über mehrere Aliase, die UNIX- und cmd.exe-Benutzern ermöglichen, vertraute Befehle zu verwenden.
ms.openlocfilehash: 8cbbd5a358de9018fcb5c840e711cd76f7a9a353
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500741"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="4b4b1-104">Anhang 1: Kompatibilitätsaliase</span><span class="sxs-lookup"><span data-stu-id="4b4b1-104">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="4b4b1-105">PowerShell verfügt über mehrere Aliase, die **UNIX** - und **cmd.exe** -Benutzern ermöglichen, vertraute Befehle zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b4b1-105">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="4b4b1-106">Die Befehle, das zugehörige PowerShell-Cmdlet und der PowerShell-Alias sind in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="4b4b1-106">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|            <span data-ttu-id="4b4b1-107">Befehl „cmd. exe“</span><span class="sxs-lookup"><span data-stu-id="4b4b1-107">cmd.exe command</span></span>            | <span data-ttu-id="4b4b1-108">UNIX-Befehl</span><span class="sxs-lookup"><span data-stu-id="4b4b1-108">UNIX command</span></span> | <span data-ttu-id="4b4b1-109">PowerShell-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4b4b1-109">PowerShell cmdlet</span></span> | <span data-ttu-id="4b4b1-110">PowerShell-Alias</span><span class="sxs-lookup"><span data-stu-id="4b4b1-110">PowerShell alias</span></span> |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| <span data-ttu-id="4b4b1-111">**cd** , **chdir**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-111">**cd** , **chdir**</span></span>                     | <span data-ttu-id="4b4b1-112">**cd**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-112">**cd**</span></span>       | `Set-Location`    | `sl`             |
| <span data-ttu-id="4b4b1-113">**cls**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-113">**cls**</span></span>                               | <span data-ttu-id="4b4b1-114">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-114">**clear**</span></span>    | `Clear-Host`      | `cls`            |
| <span data-ttu-id="4b4b1-115">**copy**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-115">**copy**</span></span>                              | <span data-ttu-id="4b4b1-116">**cp**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-116">**cp**</span></span>       | `Copy-Item`       | `cpi`            |
| <span data-ttu-id="4b4b1-117">**del** , **erase** , **rd** , **rmdir**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-117">**del** , **erase** , **rd** , **rmdir**</span></span> | <span data-ttu-id="4b4b1-118">**rm**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-118">**rm**</span></span>       | `Remove-Item`     | `ri`             |
| <span data-ttu-id="4b4b1-119">**dir**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-119">**dir**</span></span>                               | <span data-ttu-id="4b4b1-120">**ls**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-120">**ls**</span></span>       | `Get-ChildItem`   | `gci`            |
| <span data-ttu-id="4b4b1-121">**echo**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-121">**echo**</span></span>                              | <span data-ttu-id="4b4b1-122">**echo**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-122">**echo**</span></span>     | `Write-Output`    | `write`          |
| <span data-ttu-id="4b4b1-123">**md**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-123">**md**</span></span>                                | <span data-ttu-id="4b4b1-124">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-124">**mkdir**</span></span>    | `New-Item`        | `ni`             |
| <span data-ttu-id="4b4b1-125">**move**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-125">**move**</span></span>                              | <span data-ttu-id="4b4b1-126">**mv**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-126">**mv**</span></span>       | `Move-Item`       | `mi`             |
| <span data-ttu-id="4b4b1-127">**popd**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-127">**popd**</span></span>                              | <span data-ttu-id="4b4b1-128">**popd**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-128">**popd**</span></span>     | `Pop-Location`    | `popd`           |
| <span data-ttu-id="4b4b1-129">**pushd**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-129">**pushd**</span></span>                             | <span data-ttu-id="4b4b1-130">**pushd**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-130">**pushd**</span></span>    | `Push-Location`   | `pushd`          |
| <span data-ttu-id="4b4b1-131">**ren**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-131">**ren**</span></span>                               | <span data-ttu-id="4b4b1-132">**mv**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-132">**mv**</span></span>       | `Rename-Item`     | `rni`            |
| <span data-ttu-id="4b4b1-133">**type**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-133">**type**</span></span>                              | <span data-ttu-id="4b4b1-134">**cat**</span><span class="sxs-lookup"><span data-stu-id="4b4b1-134">**cat**</span></span>      | `Get-Content`     | `gc`             |

<span data-ttu-id="4b4b1-135">Verwenden Sie das [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias)-Cmdlet, um die PowerShell-Aliase zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="4b4b1-135">To find the PowerShell aliases, use the [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) cmdlet.</span></span> <span data-ttu-id="4b4b1-136">Um die Aliase eines Cmdlets anzuzeigen, verwenden Sie den **Definition** -Parameter, und geben Sie den Namen des Cmdlets an.</span><span class="sxs-lookup"><span data-stu-id="4b4b1-136">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="4b4b1-137">Verwenden Sie alternativ den **Name** -Parameter, um den Cmdlet-Namen eines Alias zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4b4b1-137">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

```Output
CommandType     Name
-----------     ----
Alias           dir -> Get-ChildItem
Alias           gci -> Get-ChildItem
Alias           ls -> Get-ChildItem
```

```powershell
Get-Alias -Name gci
```

```Output
CommandType     Name
-----------     ----
Alias           gci -> Get-ChildItem
```
