---
description: Packagemanagement ist ein Aggregator für Softwarepaket-Manager.
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_packagemanagement?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PackageManagement
ms.openlocfilehash: 22f47d01063778fca4f51a534b15d485b3beee28
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596961"
---
# <a name="about-packagemanagement"></a><span data-ttu-id="390c5-103">Informationen zu packagemanagement</span><span class="sxs-lookup"><span data-stu-id="390c5-103">About PackageManagement</span></span>

## <a name="short-description"></a><span data-ttu-id="390c5-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="390c5-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="390c5-105">Packagemanagement ist ein Aggregator für Softwarepaket-Manager.</span><span class="sxs-lookup"><span data-stu-id="390c5-105">PackageManagement is an aggregator for software package managers.</span></span>

## <a name="long-description"></a><span data-ttu-id="390c5-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="390c5-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="390c5-107">Die packagemanagement-Funktionalität wurde in Windows PowerShell 5,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="390c5-107">PackageManagement functionality was introduced in Windows PowerShell 5.0.</span></span>

<span data-ttu-id="390c5-108">Packagemanagement ist eine einheitliche Schnittstelle für Softwarepaket Verwaltungssysteme. Sie können die packagemanagement-Cmdlets ausführen, um Aufgaben für die Software Ermittlung, Installation und Inventur (SDII) auszuführen.</span><span class="sxs-lookup"><span data-stu-id="390c5-108">PackageManagement is a unified interface for software package management systems; you can run PackageManagement cmdlets to perform software discovery, installation, and inventory (SDII) tasks.</span></span> <span data-ttu-id="390c5-109">Unabhängig von der zugrunde liegenden Installations Technologie können Sie die allgemeinen Cmdlets im packagemanagement-Modul ausführen, um Pakete zu suchen, zu installieren oder zu deinstallieren. Hinzufügen, entfernen und Abfragen von paketrepositorys und Ausführen von Abfragen auf einem Computer, um zu bestimmen, welche Softwarepakete installiert sind.</span><span class="sxs-lookup"><span data-stu-id="390c5-109">Regardless of the underlying installation technology, you can run the common cmdlets in the PackageManagement module to search for, install, or uninstall packages; add, remove, and query package repositories; and run queries on a computer to determine which software packages are installed.</span></span>

<span data-ttu-id="390c5-110">Packagemanagement unterstützt ein flexibles Plug-in-Modell, das die Unterstützung anderer Softwarepaket-Verwaltungssysteme ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="390c5-110">PackageManagement supports a flexible plug-in model that enables support for other software package management systems.</span></span>

<span data-ttu-id="390c5-111">Das packagemanagement-Modul ist in Windows PowerShell 5,0 und neueren Versionen von PowerShell enthalten und funktioniert auf drei Ebenen der Paket Verwaltungsstruktur: Paketanbieter, Paketquellen und Pakete selbst.</span><span class="sxs-lookup"><span data-stu-id="390c5-111">The PackageManagement module is included with Windows PowerShell 5.0 and later releases of PowerShell, and works on three levels of package management structure: package providers, package sources, and the packages themselves.</span></span> <span data-ttu-id="390c5-112">Wir definieren einige Begriffe:</span><span class="sxs-lookup"><span data-stu-id="390c5-112">Let us define some terms:</span></span>

- <span data-ttu-id="390c5-113">Paket-Manager: Software Paketverwaltungssystem.</span><span class="sxs-lookup"><span data-stu-id="390c5-113">Package manager: Software package management system.</span></span> <span data-ttu-id="390c5-114">In den packagemanagement-Begriffen handelt es sich hierbei um einen Paketanbieter.</span><span class="sxs-lookup"><span data-stu-id="390c5-114">In PackageManagement terms, this is a package provider.</span></span>
- <span data-ttu-id="390c5-115">Paketanbieter: packagemanagement-Begriff für einen Paket-Manager.</span><span class="sxs-lookup"><span data-stu-id="390c5-115">Package provider: PackageManagement term for a package manager.</span></span> <span data-ttu-id="390c5-116">Beispiele hierfür sind Windows Installer, Chocolatey und andere.</span><span class="sxs-lookup"><span data-stu-id="390c5-116">Examples can include Windows Installer, Chocolatey, and others.</span></span>
- <span data-ttu-id="390c5-117">Paketquelle: eine URL, ein lokaler Ordner oder ein frei gegebener Netzwerkordner, den Sie als Repository für die Verwendung von Paket Anbietern konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="390c5-117">Package source: A URL, local folder, or network shared folder that you configure package providers to use as a repository.</span></span>
- <span data-ttu-id="390c5-118">Package: eine Softwarekomponente, die von einem Paketanbieter verwaltet wird und die in einer bestimmten Paketquelle gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="390c5-118">Package: A piece of software that a package provider manages, and that is stored in a specific package source.</span></span>

<span data-ttu-id="390c5-119">Das packagemanagement-Modul umfasst die folgenden Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="390c5-119">The PackageManagement module includes the following cmdlets.</span></span> <span data-ttu-id="390c5-120">Weitere Informationen finden Sie in der [packagemanagement](/powershell/module/packagemanagement) -Hilfe.</span><span class="sxs-lookup"><span data-stu-id="390c5-120">For more information, see the [PackageManagement](/powershell/module/packagemanagement) help.</span></span>

- <span data-ttu-id="390c5-121">`Get-PackageProvider`: Gibt eine Liste von Paket Anbietern zurück, die mit packagemanagement verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="390c5-121">`Get-PackageProvider`: Returns a list of package providers that are  connected to PackageManagement.</span></span>
- <span data-ttu-id="390c5-122">`Get-PackageSource`: Ruft eine Liste der Paketquellen ab, die für einen Paketanbieter registriert sind.</span><span class="sxs-lookup"><span data-stu-id="390c5-122">`Get-PackageSource`: Gets a list of package sources that are registered for a package provider.</span></span>
- <span data-ttu-id="390c5-123">`Register-PackageSource`: Fügt eine Paketquelle für einen angegebenen Paketanbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="390c5-123">`Register-PackageSource`: Adds a package source for a specified package provider.</span></span>
- <span data-ttu-id="390c5-124">`Set-PackageSource`: Legt Eigenschaften für eine vorhandene Paketquelle fest.</span><span class="sxs-lookup"><span data-stu-id="390c5-124">`Set-PackageSource`: Sets properties on an existing package source.</span></span>
- <span data-ttu-id="390c5-125">`Unregister-PackageSource`: Entfernt eine registrierte Paketquelle.</span><span class="sxs-lookup"><span data-stu-id="390c5-125">`Unregister-PackageSource`: Removes a registered package source.</span></span>
- <span data-ttu-id="390c5-126">`Get-Package`: Gibt eine Liste der installierten Softwarepakete zurück.</span><span class="sxs-lookup"><span data-stu-id="390c5-126">`Get-Package`: Returns a list of installed software packages.</span></span>
- <span data-ttu-id="390c5-127">`Find-Package`: Findet Softwarepakete in verfügbaren Paketquellen.</span><span class="sxs-lookup"><span data-stu-id="390c5-127">`Find-Package`: Finds software packages in available package sources.</span></span>
- <span data-ttu-id="390c5-128">`Install-Package`: Installiert mindestens ein Softwarepaket.</span><span class="sxs-lookup"><span data-stu-id="390c5-128">`Install-Package`: Installs one or more software packages.</span></span>
- <span data-ttu-id="390c5-129">`Save-Package`: Speichert Pakete auf dem lokalen Computer, ohne Sie zu installieren.</span><span class="sxs-lookup"><span data-stu-id="390c5-129">`Save-Package`: Saves packages to the local computer without installing them.</span></span>
- <span data-ttu-id="390c5-130">`Uninstall-Package`: Deinstalliert mindestens ein Softwarepaket.</span><span class="sxs-lookup"><span data-stu-id="390c5-130">`Uninstall-Package`: Uninstalls one or more software packages.</span></span>

### <a name="package-provider-bootstrapping-and-dynamic-cmdlet-parameters"></a><span data-ttu-id="390c5-131">Paketanbieter-Bootstrapping und dynamische Cmdlet-Parameter</span><span class="sxs-lookup"><span data-stu-id="390c5-131">Package Provider Bootstrapping and Dynamic Cmdlet Parameters</span></span>

<span data-ttu-id="390c5-132">Standardmäßig wird packagemanagement mit einem kernbootstrap-Anbieter ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="390c5-132">By default, PackageManagement ships with a core bootstrap provider.</span></span> <span data-ttu-id="390c5-133">Sie können weitere Paketanbieter installieren, wenn Sie Sie benötigen, indem Sie Bootstrapping für die Anbieter durchstarten. Das heißt, dass auf eine Aufforderung zum automatischen Installieren des Anbieters von einem Webdienst aus reagiert wird.</span><span class="sxs-lookup"><span data-stu-id="390c5-133">You can install additional package providers as you need them by bootstrapping the providers; that is, responding to a prompt to install the provider automatically, from a web service.</span></span> <span data-ttu-id="390c5-134">Sie können einen Paketanbieter mit einem beliebigen packagemanagement-Cmdlet angeben. Wenn der angegebene Anbieter nicht verfügbar ist, werden Sie von packagemanagement aufgefordert, den Anbieter zu Bootstrap (oder automatisch zu installieren).</span><span class="sxs-lookup"><span data-stu-id="390c5-134">You can specify a package provider with any PackageManagement cmdlet; if the specified provider is not available, PackageManagement prompts you to bootstrap (or automatically install) the provider.</span></span> <span data-ttu-id="390c5-135">Wenn der Chocolatey-Anbieter nicht bereits installiert ist, wird in den folgenden Beispielen der Anbieter von packagemanagement installiert.</span><span class="sxs-lookup"><span data-stu-id="390c5-135">In the following examples, if the Chocolatey provider is not already installed, PackageManagement bootstrapping installs the provider.</span></span>

```powershell
Find-Package -Provider Chocolatey <PackageName>
```

<span data-ttu-id="390c5-136">Wenn der Chocolatey-Anbieter nicht bereits installiert ist, werden Sie beim Ausführen des vorherigen Befehls aufgefordert, ihn zu installieren.</span><span class="sxs-lookup"><span data-stu-id="390c5-136">If the Chocolatey provider is not already installed, when you run the preceding command, you are prompted to install it.</span></span>

```powershell
Install-Package <Chocolatey package Name> -ForceBootstrap
```

<span data-ttu-id="390c5-137">Wenn der Chocolatey-Anbieter nicht bereits installiert ist, wird der Anbieter installiert, wenn Sie den vorherigen Befehl ausführen. aber da der forcebootstrap-Parameter dem Befehl hinzugefügt wurde, werden Sie nicht aufgefordert, ihn zu installieren. sowohl der Anbieter als auch das Paket werden automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="390c5-137">If the Chocolatey provider is not already installed, when you run the preceding command, the provider is installed; but because the ForceBootstrap parameter has been added to the command, you are not prompted to install it; both the provider and the package are installed automatically.</span></span>

<span data-ttu-id="390c5-138">Wenn Sie versuchen, ein Paket zu installieren, wenn der unterstützende Anbieter nicht bereits installiert ist und Sie dem Befehl den forcebootstrap-Parameter nicht hinzufügen, werden Sie von packagemanagement aufgefordert, den Anbieter zu installieren.</span><span class="sxs-lookup"><span data-stu-id="390c5-138">When you try to install a package, if you do not already have the supporting provider installed, and you do not add the ForceBootstrap parameter to your command, PackageManagement prompts you to install the provider.</span></span>

<span data-ttu-id="390c5-139">Durch die Angabe eines Paket Anbieters in Ihrem packagemanagement-Befehl können dynamische Parameter verfügbar gemacht werden, die für diesen Paketanbieter spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="390c5-139">Specifying a package provider in your PackageManagement command can make dynamic parameters available that are specific to that package provider.</span></span> <span data-ttu-id="390c5-140">Wenn Sie Get-Help für ein bestimmtes packagemanagement-Cmdlet ausführen, wird eine Liste von Parametersätzen zurückgegeben, wobei dynamische Parameter für verfügbare Paketanbieter in separaten Parametersätzen gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="390c5-140">When you run Get-Help for a specific PackageManagement cmdlet, a list of parameter sets are returned, grouping dynamic parameters for available package providers in separate parameter sets.</span></span>

<span data-ttu-id="390c5-141">Weitere Informationen zum Projekt "packagemanagement"</span><span class="sxs-lookup"><span data-stu-id="390c5-141">More Information About the PackageManagement Project</span></span>

<span data-ttu-id="390c5-142">Weitere Informationen zum geöffneten Entwicklungsprojekt packagemanagement, einschließlich der Erstellung eines packagemanagement-Paket Anbieters, finden Sie im Projekt packagemanagement auf GitHub unter https://oneget.org .</span><span class="sxs-lookup"><span data-stu-id="390c5-142">For more information about the PackageManagement open development project, including how to create a PackageManagement package provider, see the PackageManagement project on GitHub at https://oneget.org.</span></span>

## <a name="see-also"></a><span data-ttu-id="390c5-143">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="390c5-143">SEE ALSO</span></span>

[<span data-ttu-id="390c5-144">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="390c5-144">Get-PackageProvider</span></span>](xref:PackageManagement.Get-PackageProvider)

[<span data-ttu-id="390c5-145">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="390c5-145">Get-PackageSource</span></span>](xref:PackageManagement.Get-PackageSource)

[<span data-ttu-id="390c5-146">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="390c5-146">Register-PackageSource</span></span>](xref:PackageManagement.Register-PackageSource)

[<span data-ttu-id="390c5-147">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="390c5-147">Set-PackageSource</span></span>](xref:PackageManagement.Set-PackageSource)

[<span data-ttu-id="390c5-148">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="390c5-148">Unregister-PackageSource</span></span>](xref:PackageManagement.Unregister-PackageSource)

[<span data-ttu-id="390c5-149">Get-Package</span><span class="sxs-lookup"><span data-stu-id="390c5-149">Get-Package</span></span>](xref:PackageManagement.Get-Package)

[<span data-ttu-id="390c5-150">Find-Package</span><span class="sxs-lookup"><span data-stu-id="390c5-150">Find-Package</span></span>](xref:PackageManagement.Find-Package)

[<span data-ttu-id="390c5-151">Install-Package</span><span class="sxs-lookup"><span data-stu-id="390c5-151">Install-Package</span></span>](xref:PackageManagement.Install-Package)

[<span data-ttu-id="390c5-152">Save-Package</span><span class="sxs-lookup"><span data-stu-id="390c5-152">Save-Package</span></span>](xref:PackageManagement.Save-Package)

[<span data-ttu-id="390c5-153">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="390c5-153">Uninstall-Package</span></span>](xref:PackageManagement.Uninstall-Package)

