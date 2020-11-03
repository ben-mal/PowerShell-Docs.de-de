---
description: Listet die Cmdlets auf, die für die Verwendung mit PowerShell-Anbietern konzipiert sind.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: 5c784518ae30108813d32497f654198e7d10b379
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220732"
---
# <a name="about-core-commands"></a><span data-ttu-id="2463a-104">Informationen zu Kern Befehlen</span><span class="sxs-lookup"><span data-stu-id="2463a-104">About Core Commands</span></span>

## <a name="short-description"></a><span data-ttu-id="2463a-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2463a-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="2463a-106">Listet die Cmdlets auf, die für die Verwendung mit PowerShell-Anbietern konzipiert sind.</span><span class="sxs-lookup"><span data-stu-id="2463a-106">Lists the cmdlets that are designed for use with PowerShell providers.</span></span>

## <a name="long-description"></a><span data-ttu-id="2463a-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2463a-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="2463a-108">PowerShell umfasst einen Satz von Cmdlets, die speziell für die Verwaltung der Elemente in den Daten speichern entwickelt wurden, die von PowerShell-Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="2463a-108">PowerShell includes a set of cmdlets that are specifically designed to manage the items in the data stores that are exposed by PowerShell providers.</span></span>
<span data-ttu-id="2463a-109">Sie können diese Cmdlets auf die gleiche Weise verwenden, um alle unterschiedlichen Datentypen zu verwalten, die die Anbieter für Sie verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="2463a-109">You can use these cmdlets in the same ways to manage all the different types of data that the providers make available to you.</span></span> <span data-ttu-id="2463a-110">Wenn Sie weitere Informationen zu Anbietern benötigen, geben Sie "Get-Help about_Providers" ein.</span><span class="sxs-lookup"><span data-stu-id="2463a-110">For more information about providers, type "get-help about_providers".</span></span>

<span data-ttu-id="2463a-111">Beispielsweise können Sie mit dem Cmdlet "Get-ChildItem" die Dateien in einem Dateisystem Verzeichnis, die Schlüssel unter einem Registrierungsschlüssel oder die Elemente auflisten, die von einem Anbieter verfügbar gemacht werden, den Sie schreiben oder herunterladen.</span><span class="sxs-lookup"><span data-stu-id="2463a-111">For example, you can use the Get-ChildItem cmdlet to list the files in a file system directory, the keys under a registry key, or the items that are exposed by a provider that you write or download.</span></span>

<span data-ttu-id="2463a-112">Im folgenden finden Sie eine Liste der PowerShell-Cmdlets, die für die Verwendung mit Anbietern entwickelt wurden:</span><span class="sxs-lookup"><span data-stu-id="2463a-112">The following is a list of the PowerShell cmdlets that are designed for use with providers:</span></span>

<span data-ttu-id="2463a-113">ChildItem-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2463a-113">ChildItem cmdlets</span></span>

- <span data-ttu-id="2463a-114">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="2463a-114">Get-ChildItem</span></span>

<span data-ttu-id="2463a-115">Content-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2463a-115">Content cmdlets</span></span>

- <span data-ttu-id="2463a-116">Add-Content</span><span class="sxs-lookup"><span data-stu-id="2463a-116">Add-Content</span></span>
- <span data-ttu-id="2463a-117">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="2463a-117">Clear-Content</span></span>
- <span data-ttu-id="2463a-118">Get-Content</span><span class="sxs-lookup"><span data-stu-id="2463a-118">Get-Content</span></span>
- <span data-ttu-id="2463a-119">Set-Content</span><span class="sxs-lookup"><span data-stu-id="2463a-119">Set-Content</span></span>

<span data-ttu-id="2463a-120">Item-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2463a-120">Item cmdlets</span></span>

- <span data-ttu-id="2463a-121">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="2463a-121">Clear-Item</span></span>
- <span data-ttu-id="2463a-122">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="2463a-122">Copy-Item</span></span>
- <span data-ttu-id="2463a-123">Get-Item</span><span class="sxs-lookup"><span data-stu-id="2463a-123">Get-Item</span></span>
- <span data-ttu-id="2463a-124">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="2463a-124">Invoke-Item</span></span>
- <span data-ttu-id="2463a-125">Move-Item</span><span class="sxs-lookup"><span data-stu-id="2463a-125">Move-Item</span></span>
- <span data-ttu-id="2463a-126">New-Item</span><span class="sxs-lookup"><span data-stu-id="2463a-126">New-Item</span></span>
- <span data-ttu-id="2463a-127">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="2463a-127">Remove-Item</span></span>
- <span data-ttu-id="2463a-128">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="2463a-128">Rename-Item</span></span>
- <span data-ttu-id="2463a-129">Set-Item</span><span class="sxs-lookup"><span data-stu-id="2463a-129">Set-Item</span></span>

<span data-ttu-id="2463a-130">ItemProperty-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2463a-130">ItemProperty cmdlets</span></span>

- <span data-ttu-id="2463a-131">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2463a-131">Clear-ItemProperty</span></span>
- <span data-ttu-id="2463a-132">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2463a-132">Copy-ItemProperty</span></span>
- <span data-ttu-id="2463a-133">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2463a-133">Get-ItemProperty</span></span>
- <span data-ttu-id="2463a-134">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2463a-134">Move-ItemProperty</span></span>
- <span data-ttu-id="2463a-135">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2463a-135">New-ItemProperty</span></span>
- <span data-ttu-id="2463a-136">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2463a-136">Remove-ItemProperty</span></span>
- <span data-ttu-id="2463a-137">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2463a-137">Rename-ItemProperty</span></span>
- <span data-ttu-id="2463a-138">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2463a-138">Set-ItemProperty</span></span>

<span data-ttu-id="2463a-139">Location-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2463a-139">Location cmdlets</span></span>

- <span data-ttu-id="2463a-140">Get-Location</span><span class="sxs-lookup"><span data-stu-id="2463a-140">Get-Location</span></span>
- <span data-ttu-id="2463a-141">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="2463a-141">Pop-Location</span></span>
- <span data-ttu-id="2463a-142">Push-Location</span><span class="sxs-lookup"><span data-stu-id="2463a-142">Push-Location</span></span>
- <span data-ttu-id="2463a-143">Set-Location</span><span class="sxs-lookup"><span data-stu-id="2463a-143">Set-Location</span></span>

<span data-ttu-id="2463a-144">Pfad-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2463a-144">Path cmdlets</span></span>

- <span data-ttu-id="2463a-145">Join-Path</span><span class="sxs-lookup"><span data-stu-id="2463a-145">Join-Path</span></span>
- <span data-ttu-id="2463a-146">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="2463a-146">Convert-Path</span></span>
- <span data-ttu-id="2463a-147">Split-Path</span><span class="sxs-lookup"><span data-stu-id="2463a-147">Split-Path</span></span>
- <span data-ttu-id="2463a-148">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="2463a-148">Resolve-Path</span></span>
- <span data-ttu-id="2463a-149">Test-Path</span><span class="sxs-lookup"><span data-stu-id="2463a-149">Test-Path</span></span>

<span data-ttu-id="2463a-150">PSDrive-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2463a-150">PSDrive cmdlets</span></span>

- <span data-ttu-id="2463a-151">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="2463a-151">Get-PSDrive</span></span>
- <span data-ttu-id="2463a-152">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="2463a-152">New-PSDrive</span></span>
- <span data-ttu-id="2463a-153">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="2463a-153">Remove-PSDrive</span></span>

<span data-ttu-id="2463a-154">Psprovider-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2463a-154">PSProvider cmdlets</span></span>

- <span data-ttu-id="2463a-155">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="2463a-155">Get-PSProvider</span></span>

<span data-ttu-id="2463a-156">Weitere Informationen zu einem Cmdlet erhalten Sie, indem Sie eingeben `get-help <cmdlet-name>` .</span><span class="sxs-lookup"><span data-stu-id="2463a-156">For more information about a cmdlet, type `get-help <cmdlet-name>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2463a-157">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="2463a-157">SEE ALSO</span></span>

[<span data-ttu-id="2463a-158">about_Providers</span><span class="sxs-lookup"><span data-stu-id="2463a-158">about_Providers</span></span>](about_Providers.md)
