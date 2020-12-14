---
Download Help Link: https://aka.ms/powershell71-help
Help Version: 7.1.0.0
keywords: powershell,cmdlet
Locale: en-US
Module Guid: 4ae9fd46-338a-459c-8186-07f910774cb8
Module Name: PackageManagement
ms.date: 06/09/2017
schema: 2.0.0
title: PackageManagement
ms.openlocfilehash: 88dcb47bee268af3553bb797aaa264e27ed8c51c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94889639"
---
# <span data-ttu-id="a45ea-103">PackageManagement-Modul</span><span class="sxs-lookup"><span data-stu-id="a45ea-103">PackageManagement Module</span></span>

## <span data-ttu-id="a45ea-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a45ea-104">Description</span></span>

<span data-ttu-id="a45ea-105">In diesem Thema werden die Hilfe Themen für die Paketverwaltung-Cmdlets angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a45ea-105">This topic displays help topics for the Package Management Cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a45ea-106">Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="a45ea-106">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="a45ea-107">Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a45ea-107">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="a45ea-108">Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="a45ea-108">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="a45ea-109">Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.</span><span class="sxs-lookup"><span data-stu-id="a45ea-109">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="a45ea-110">PackageManagement-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a45ea-110">PackageManagement Cmdlets</span></span>

### [<span data-ttu-id="a45ea-111">Find-Package</span><span class="sxs-lookup"><span data-stu-id="a45ea-111">Find-Package</span></span>](Find-Package.md)
<span data-ttu-id="a45ea-112">Findet Softwarepakete in verfügbaren Paketquellen.</span><span class="sxs-lookup"><span data-stu-id="a45ea-112">Finds software packages in available package sources.</span></span>

### [<span data-ttu-id="a45ea-113">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="a45ea-113">Find-PackageProvider</span></span>](Find-PackageProvider.md)
<span data-ttu-id="a45ea-114">Gibt eine Liste von Paketverwaltung Paket Anbietern zurück, die für die Installation verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a45ea-114">Returns a list of Package Management package providers available for installation.</span></span>

### [<span data-ttu-id="a45ea-115">Get-Package</span><span class="sxs-lookup"><span data-stu-id="a45ea-115">Get-Package</span></span>](Get-Package.md)
<span data-ttu-id="a45ea-116">Gibt eine Liste aller Softwarepakete zurück, die mit **packagemanagement** installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a45ea-116">Returns a list of all software packages that were installed with **PackageManagement**.</span></span>

### [<span data-ttu-id="a45ea-117">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="a45ea-117">Get-PackageProvider</span></span>](Get-PackageProvider.md)
<span data-ttu-id="a45ea-118">Gibt eine Liste von Paket Anbietern zurück, die mit Paketverwaltung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="a45ea-118">Returns a list of package providers that are connected to Package Management.</span></span>

### [<span data-ttu-id="a45ea-119">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="a45ea-119">Get-PackageSource</span></span>](Get-PackageSource.md)
<span data-ttu-id="a45ea-120">Ruft eine Liste der Paketquellen ab, die für einen Paketanbieter registriert sind.</span><span class="sxs-lookup"><span data-stu-id="a45ea-120">Gets a list of package sources that are registered for a package provider.</span></span>

### [<span data-ttu-id="a45ea-121">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="a45ea-121">Import-PackageProvider</span></span>](Import-PackageProvider.md)
<span data-ttu-id="a45ea-122">Fügt der aktuellen Sitzung Paketverwaltung Paketanbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="a45ea-122">Adds Package Management package providers to the current session.</span></span>

### [<span data-ttu-id="a45ea-123">Install-Package</span><span class="sxs-lookup"><span data-stu-id="a45ea-123">Install-Package</span></span>](Install-Package.md)
<span data-ttu-id="a45ea-124">Installiert mindestens ein Softwarepaket.</span><span class="sxs-lookup"><span data-stu-id="a45ea-124">Installs one or more software packages.</span></span>

### [<span data-ttu-id="a45ea-125">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="a45ea-125">Install-PackageProvider</span></span>](Install-PackageProvider.md)
<span data-ttu-id="a45ea-126">Installiert einen oder mehrere Paketverwaltung Paketanbieter.</span><span class="sxs-lookup"><span data-stu-id="a45ea-126">Installs one or more Package Management package providers.</span></span>

### [<span data-ttu-id="a45ea-127">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="a45ea-127">Register-PackageSource</span></span>](Register-PackageSource.md)
<span data-ttu-id="a45ea-128">Fügt eine Paketquelle für einen angegebenen Paketanbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="a45ea-128">Adds a package source for a specified package provider.</span></span>

### [<span data-ttu-id="a45ea-129">Save-Package</span><span class="sxs-lookup"><span data-stu-id="a45ea-129">Save-Package</span></span>](Save-Package.md)
<span data-ttu-id="a45ea-130">Speichert Pakete auf dem lokalen Computer, ohne Sie zu installieren.</span><span class="sxs-lookup"><span data-stu-id="a45ea-130">Saves packages to the local computer without installing them.</span></span>

### [<span data-ttu-id="a45ea-131">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="a45ea-131">Set-PackageSource</span></span>](Set-PackageSource.md)
<span data-ttu-id="a45ea-132">Ersetzt eine Paketquelle für einen angegebenen Paketanbieter.</span><span class="sxs-lookup"><span data-stu-id="a45ea-132">Replaces a package source for a specified package provider.</span></span>

### [<span data-ttu-id="a45ea-133">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="a45ea-133">Uninstall-Package</span></span>](Uninstall-Package.md)
<span data-ttu-id="a45ea-134">Deinstalliert mindestens ein Softwarepaket.</span><span class="sxs-lookup"><span data-stu-id="a45ea-134">Uninstalls one or more software packages.</span></span>

### [<span data-ttu-id="a45ea-135">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="a45ea-135">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
<span data-ttu-id="a45ea-136">Entfernt eine registrierte Paketquelle.</span><span class="sxs-lookup"><span data-stu-id="a45ea-136">Removes a registered package source.</span></span>

