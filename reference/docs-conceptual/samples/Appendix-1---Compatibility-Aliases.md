---
ms.date: 08/03/2020
keywords: powershell,cmdlet
title: Anhang 1 – Kompatibilitätsaliase
ms.openlocfilehash: e5bd170fea6b6109d2ef4fd58863d6cc8a0e3ae1
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87758498"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="2e427-103">Anhang 1: Kompatibilitätsaliase</span><span class="sxs-lookup"><span data-stu-id="2e427-103">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="2e427-104">PowerShell verfügt über mehrere Aliase, die **UNIX**- und **cmd.exe**-Benutzern ermöglichen, vertraute Befehle zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e427-104">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="2e427-105">Die Befehle, das zugehörige PowerShell-Cmdlet und der PowerShell-Alias sind in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="2e427-105">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|            <span data-ttu-id="2e427-106">Befehl „cmd. exe“</span><span class="sxs-lookup"><span data-stu-id="2e427-106">cmd.exe command</span></span>            | <span data-ttu-id="2e427-107">UNIX-Befehl</span><span class="sxs-lookup"><span data-stu-id="2e427-107">UNIX command</span></span> | <span data-ttu-id="2e427-108">PowerShell-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2e427-108">PowerShell cmdlet</span></span> | <span data-ttu-id="2e427-109">PowerShell-Alias</span><span class="sxs-lookup"><span data-stu-id="2e427-109">PowerShell alias</span></span> |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| <span data-ttu-id="2e427-110">**cd**, **chdir**</span><span class="sxs-lookup"><span data-stu-id="2e427-110">**cd**, **chdir**</span></span>                     | <span data-ttu-id="2e427-111">**cd**</span><span class="sxs-lookup"><span data-stu-id="2e427-111">**cd**</span></span>       | `Set-Location`    | `sl`             |
| <span data-ttu-id="2e427-112">**cls**</span><span class="sxs-lookup"><span data-stu-id="2e427-112">**cls**</span></span>                               | <span data-ttu-id="2e427-113">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="2e427-113">**clear**</span></span>    | `Clear-Host`      | `cls`            |
| <span data-ttu-id="2e427-114">**copy**</span><span class="sxs-lookup"><span data-stu-id="2e427-114">**copy**</span></span>                              | <span data-ttu-id="2e427-115">**cp**</span><span class="sxs-lookup"><span data-stu-id="2e427-115">**cp**</span></span>       | `Copy-Item`       | `cpi`            |
| <span data-ttu-id="2e427-116">**del**, **erase**, **rd**, **rmdir**</span><span class="sxs-lookup"><span data-stu-id="2e427-116">**del**, **erase**, **rd**, **rmdir**</span></span> | <span data-ttu-id="2e427-117">**rm**</span><span class="sxs-lookup"><span data-stu-id="2e427-117">**rm**</span></span>       | `Remove-Item`     | `ri`             |
| <span data-ttu-id="2e427-118">**dir**</span><span class="sxs-lookup"><span data-stu-id="2e427-118">**dir**</span></span>                               | <span data-ttu-id="2e427-119">**ls**</span><span class="sxs-lookup"><span data-stu-id="2e427-119">**ls**</span></span>       | `Get-ChildItem`   | `gci`            |
| <span data-ttu-id="2e427-120">**echo**</span><span class="sxs-lookup"><span data-stu-id="2e427-120">**echo**</span></span>                              | <span data-ttu-id="2e427-121">**echo**</span><span class="sxs-lookup"><span data-stu-id="2e427-121">**echo**</span></span>     | `Write-Output`    | `write`          |
| <span data-ttu-id="2e427-122">**md**</span><span class="sxs-lookup"><span data-stu-id="2e427-122">**md**</span></span>                                | <span data-ttu-id="2e427-123">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="2e427-123">**mkdir**</span></span>    | `New-Item`        | `ni`             |
| <span data-ttu-id="2e427-124">**move**</span><span class="sxs-lookup"><span data-stu-id="2e427-124">**move**</span></span>                              | <span data-ttu-id="2e427-125">**mv**</span><span class="sxs-lookup"><span data-stu-id="2e427-125">**mv**</span></span>       | `Move-Item`       | `mi`             |
| <span data-ttu-id="2e427-126">**popd**</span><span class="sxs-lookup"><span data-stu-id="2e427-126">**popd**</span></span>                              | <span data-ttu-id="2e427-127">**popd**</span><span class="sxs-lookup"><span data-stu-id="2e427-127">**popd**</span></span>     | `Pop-Location`    | `popd`           |
| <span data-ttu-id="2e427-128">**pushd**</span><span class="sxs-lookup"><span data-stu-id="2e427-128">**pushd**</span></span>                             | <span data-ttu-id="2e427-129">**pushd**</span><span class="sxs-lookup"><span data-stu-id="2e427-129">**pushd**</span></span>    | `Push-Location`   | `pushd`          |
| <span data-ttu-id="2e427-130">**ren**</span><span class="sxs-lookup"><span data-stu-id="2e427-130">**ren**</span></span>                               | <span data-ttu-id="2e427-131">**mv**</span><span class="sxs-lookup"><span data-stu-id="2e427-131">**mv**</span></span>       | `Rename-Item`     | `rni`            |
| <span data-ttu-id="2e427-132">**type**</span><span class="sxs-lookup"><span data-stu-id="2e427-132">**type**</span></span>                              | <span data-ttu-id="2e427-133">**cat**</span><span class="sxs-lookup"><span data-stu-id="2e427-133">**cat**</span></span>      | `Get-Content`     | `gc`             |

<span data-ttu-id="2e427-134">Verwenden Sie das [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias)-Cmdlet, um die PowerShell-Aliase zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="2e427-134">To find the PowerShell aliases, use the [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) cmdlet.</span></span> <span data-ttu-id="2e427-135">Um die Aliase eines Cmdlets anzuzeigen, verwenden Sie den **Definition**-Parameter, und geben Sie den Namen des Cmdlets an.</span><span class="sxs-lookup"><span data-stu-id="2e427-135">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="2e427-136">Verwenden Sie alternativ den **Name**-Parameter, um den Cmdlet-Namen eines Alias zu suchen.</span><span class="sxs-lookup"><span data-stu-id="2e427-136">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

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
