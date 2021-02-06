---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 4ae9fd46-338a-459c-8186-07f910774cb8
Module Name: PackageManagement
ms.date: 06/09/2017
schema: 2.0.0
title: PackageManagement
ms.openlocfilehash: 86e6f37f6f7f0527c5dcca309cf581cb6f1b4de5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99596969"
---
# <span data-ttu-id="8054c-102">PackageManagement-Modul</span><span class="sxs-lookup"><span data-stu-id="8054c-102">PackageManagement Module</span></span>

## <span data-ttu-id="8054c-103">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8054c-103">Description</span></span>

<span data-ttu-id="8054c-104">In diesem Thema werden die Hilfe Themen für die Paketverwaltung-Cmdlets angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8054c-104">This topic displays help topics for the Package Management Cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8054c-105">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="8054c-105">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="8054c-106">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="8054c-106">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="8054c-107">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="8054c-107">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="8054c-108">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="8054c-108">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="8054c-109">PackageManagement-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="8054c-109">PackageManagement Cmdlets</span></span>

### [<span data-ttu-id="8054c-110">Find-Package</span><span class="sxs-lookup"><span data-stu-id="8054c-110">Find-Package</span></span>](Find-Package.md)
<span data-ttu-id="8054c-111">Findet Softwarepakete in verfügbaren Paketquellen.</span><span class="sxs-lookup"><span data-stu-id="8054c-111">Finds software packages in available package sources.</span></span>

### [<span data-ttu-id="8054c-112">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="8054c-112">Find-PackageProvider</span></span>](Find-PackageProvider.md)
<span data-ttu-id="8054c-113">Gibt eine Liste von Paketverwaltung Paket Anbietern zurück, die für die Installation verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8054c-113">Returns a list of Package Management package providers available for installation.</span></span>

### [<span data-ttu-id="8054c-114">Get-Package</span><span class="sxs-lookup"><span data-stu-id="8054c-114">Get-Package</span></span>](Get-Package.md)
<span data-ttu-id="8054c-115">Gibt eine Liste aller Softwarepakete zurück, die mit **packagemanagement** installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="8054c-115">Returns a list of all software packages that were installed with **PackageManagement**.</span></span>

### [<span data-ttu-id="8054c-116">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="8054c-116">Get-PackageProvider</span></span>](Get-PackageProvider.md)
<span data-ttu-id="8054c-117">Gibt eine Liste von Paket Anbietern zurück, die mit Paketverwaltung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="8054c-117">Returns a list of package providers that are connected to Package Management.</span></span>

### [<span data-ttu-id="8054c-118">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8054c-118">Get-PackageSource</span></span>](Get-PackageSource.md)
<span data-ttu-id="8054c-119">Ruft eine Liste der Paketquellen ab, die für einen Paketanbieter registriert sind.</span><span class="sxs-lookup"><span data-stu-id="8054c-119">Gets a list of package sources that are registered for a package provider.</span></span>

### [<span data-ttu-id="8054c-120">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="8054c-120">Import-PackageProvider</span></span>](Import-PackageProvider.md)
<span data-ttu-id="8054c-121">Fügt der aktuellen Sitzung Paketverwaltung Paketanbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="8054c-121">Adds Package Management package providers to the current session.</span></span>

### [<span data-ttu-id="8054c-122">Install-Package</span><span class="sxs-lookup"><span data-stu-id="8054c-122">Install-Package</span></span>](Install-Package.md)
<span data-ttu-id="8054c-123">Installiert mindestens ein Softwarepaket.</span><span class="sxs-lookup"><span data-stu-id="8054c-123">Installs one or more software packages.</span></span>

### [<span data-ttu-id="8054c-124">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="8054c-124">Install-PackageProvider</span></span>](Install-PackageProvider.md)
<span data-ttu-id="8054c-125">Installiert einen oder mehrere Paketverwaltung Paketanbieter.</span><span class="sxs-lookup"><span data-stu-id="8054c-125">Installs one or more Package Management package providers.</span></span>

### [<span data-ttu-id="8054c-126">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8054c-126">Register-PackageSource</span></span>](Register-PackageSource.md)
<span data-ttu-id="8054c-127">Fügt eine Paketquelle für einen angegebenen Paketanbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="8054c-127">Adds a package source for a specified package provider.</span></span>

### [<span data-ttu-id="8054c-128">Save-Package</span><span class="sxs-lookup"><span data-stu-id="8054c-128">Save-Package</span></span>](Save-Package.md)
<span data-ttu-id="8054c-129">Speichert Pakete auf dem lokalen Computer, ohne Sie zu installieren.</span><span class="sxs-lookup"><span data-stu-id="8054c-129">Saves packages to the local computer without installing them.</span></span>

### [<span data-ttu-id="8054c-130">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8054c-130">Set-PackageSource</span></span>](Set-PackageSource.md)
<span data-ttu-id="8054c-131">Ersetzt eine Paketquelle für einen angegebenen Paketanbieter.</span><span class="sxs-lookup"><span data-stu-id="8054c-131">Replaces a package source for a specified package provider.</span></span>

### [<span data-ttu-id="8054c-132">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="8054c-132">Uninstall-Package</span></span>](Uninstall-Package.md)
<span data-ttu-id="8054c-133">Deinstalliert mindestens ein Softwarepaket.</span><span class="sxs-lookup"><span data-stu-id="8054c-133">Uninstalls one or more software packages.</span></span>

### [<span data-ttu-id="8054c-134">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8054c-134">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
<span data-ttu-id="8054c-135">Entfernt eine registrierte Paketquelle.</span><span class="sxs-lookup"><span data-stu-id="8054c-135">Removes a registered package source.</span></span>
