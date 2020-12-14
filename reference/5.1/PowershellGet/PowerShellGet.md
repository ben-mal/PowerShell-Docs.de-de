---
Download Help Link: https://go.microsoft.com/fwlink/?LinkId=393271
Help Version: 5.2.0.0
keywords: powershell,cmdlet
Locale: en-US
Module Guid: 1d73a601-4a6c-43c5-ba3f-619b18bbb404
Module Name: PowerShellGet
ms.date: 06/09/2017
schema: 2.0.0
title: PowerShellGet
ms.openlocfilehash: 130582b1b9f18a8f6ada7c009c6d25a7dab75e46
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890711"
---
# <span data-ttu-id="4371b-103">PowerShellGet-Modul</span><span class="sxs-lookup"><span data-stu-id="4371b-103">PowerShellGet Module</span></span>

## <span data-ttu-id="4371b-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4371b-104">Description</span></span>

<span data-ttu-id="4371b-105">PowerShellGet ist ein Modul mit Befehlen zum ermitteln, installieren, aktualisieren und Veröffentlichen von PowerShell-Artefakten wie Modulen, DSC-Ressourcen, Rollen Funktionen und Skripts.</span><span class="sxs-lookup"><span data-stu-id="4371b-105">PowerShellGet is a module with commands for discovering, installing, updating and publishing PowerShell artifacts like Modules, DSC Resources, Role Capabilities, and Scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4371b-106">Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="4371b-106">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="4371b-107">Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4371b-107">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="4371b-108">Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="4371b-108">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="4371b-109">Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.</span><span class="sxs-lookup"><span data-stu-id="4371b-109">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="4371b-110">PowerShellGet-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="4371b-110">PowerShellGet Cmdlets</span></span>

### [<span data-ttu-id="4371b-111">Find-Command</span><span class="sxs-lookup"><span data-stu-id="4371b-111">Find-Command</span></span>](Find-Command.md)
<span data-ttu-id="4371b-112">Sucht PowerShell-Befehle in Modulen.</span><span class="sxs-lookup"><span data-stu-id="4371b-112">Finds PowerShell commands in modules.</span></span>

### [<span data-ttu-id="4371b-113">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="4371b-113">Find-DscResource</span></span>](Find-DscResource.md)
<span data-ttu-id="4371b-114">Sucht eine DSC-Ressource.</span><span class="sxs-lookup"><span data-stu-id="4371b-114">Finds a DSC resource.</span></span>

### [<span data-ttu-id="4371b-115">Find-Module</span><span class="sxs-lookup"><span data-stu-id="4371b-115">Find-Module</span></span>](Find-Module.md)
<span data-ttu-id="4371b-116">Sucht Module in einem Repository, die den angegebenen Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4371b-116">Finds modules in a repository that match specified criteria.</span></span>

### [<span data-ttu-id="4371b-117">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="4371b-117">Find-RoleCapability</span></span>](Find-RoleCapability.md)
<span data-ttu-id="4371b-118">Sucht nach Rollenfunktionen in Modulen.</span><span class="sxs-lookup"><span data-stu-id="4371b-118">Finds role capabilities in modules.</span></span>

### [<span data-ttu-id="4371b-119">Find-Script</span><span class="sxs-lookup"><span data-stu-id="4371b-119">Find-Script</span></span>](Find-Script.md)
<span data-ttu-id="4371b-120">Sucht nach einem Skript.</span><span class="sxs-lookup"><span data-stu-id="4371b-120">Finds a script.</span></span>

### [<span data-ttu-id="4371b-121">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="4371b-121">Get-InstalledModule</span></span>](Get-InstalledModule.md)
<span data-ttu-id="4371b-122">Ruft eine Liste von Modulen auf dem Computer ab, die von PowerShellGet installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="4371b-122">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

### [<span data-ttu-id="4371b-123">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="4371b-123">Get-InstalledScript</span></span>](Get-InstalledScript.md)
<span data-ttu-id="4371b-124">Ruft ein installiertes Skript ab.</span><span class="sxs-lookup"><span data-stu-id="4371b-124">Gets an installed script.</span></span>

### [<span data-ttu-id="4371b-125">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="4371b-125">Get-PSRepository</span></span>](Get-PSRepository.md)
<span data-ttu-id="4371b-126">Ruft PowerShell-Repository ab.</span><span class="sxs-lookup"><span data-stu-id="4371b-126">Gets PowerShell repositories.</span></span>

### [<span data-ttu-id="4371b-127">Install-Module</span><span class="sxs-lookup"><span data-stu-id="4371b-127">Install-Module</span></span>](Install-Module.md)
<span data-ttu-id="4371b-128">Lädt ein oder mehrere Module aus einem Repository herunter und installiert Sie auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="4371b-128">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

### [<span data-ttu-id="4371b-129">Install-Script</span><span class="sxs-lookup"><span data-stu-id="4371b-129">Install-Script</span></span>](Install-Script.md)
<span data-ttu-id="4371b-130">Installiert ein Skript.</span><span class="sxs-lookup"><span data-stu-id="4371b-130">Installs a script.</span></span>

### [<span data-ttu-id="4371b-131">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="4371b-131">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)
<span data-ttu-id="4371b-132">Erstellt eine Skriptdatei mit Metadaten</span><span class="sxs-lookup"><span data-stu-id="4371b-132">Creates a script file with metadata.</span></span>

### [<span data-ttu-id="4371b-133">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="4371b-133">Publish-Module</span></span>](Publish-Module.md)
<span data-ttu-id="4371b-134">Veröffentlicht ein angegebenes Modul aus dem lokalen Computer in einem Onlinekatalog</span><span class="sxs-lookup"><span data-stu-id="4371b-134">Publishes a specified module from the local computer to an online gallery.</span></span>

### [<span data-ttu-id="4371b-135">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="4371b-135">Publish-Script</span></span>](Publish-Script.md)
<span data-ttu-id="4371b-136">Veröffentlicht ein Skript.</span><span class="sxs-lookup"><span data-stu-id="4371b-136">Publishes a script.</span></span>

### [<span data-ttu-id="4371b-137">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="4371b-137">Register-PSRepository</span></span>](Register-PSRepository.md)
<span data-ttu-id="4371b-138">Registriert ein PowerShell-Repository.</span><span class="sxs-lookup"><span data-stu-id="4371b-138">Registers a PowerShell repository.</span></span>

### [<span data-ttu-id="4371b-139">Save-Module</span><span class="sxs-lookup"><span data-stu-id="4371b-139">Save-Module</span></span>](Save-Module.md)
<span data-ttu-id="4371b-140">Speichert ein Modul und seine Abhängigkeiten auf dem lokalen Computer, installiert das Modul jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="4371b-140">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

### [<span data-ttu-id="4371b-141">Save-Script</span><span class="sxs-lookup"><span data-stu-id="4371b-141">Save-Script</span></span>](Save-Script.md)
<span data-ttu-id="4371b-142">Speichert ein Skript.</span><span class="sxs-lookup"><span data-stu-id="4371b-142">Saves a script.</span></span>

### [<span data-ttu-id="4371b-143">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="4371b-143">Set-PSRepository</span></span>](Set-PSRepository.md)
<span data-ttu-id="4371b-144">Legt Werte für ein registriertes Repository fest.</span><span class="sxs-lookup"><span data-stu-id="4371b-144">Sets values for a registered repository.</span></span>

### [<span data-ttu-id="4371b-145">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="4371b-145">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)
<span data-ttu-id="4371b-146">Überprüft einen Kommentar Block für ein Skript.</span><span class="sxs-lookup"><span data-stu-id="4371b-146">Validates a comment block for a script.</span></span>

### [<span data-ttu-id="4371b-147">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="4371b-147">Uninstall-Module</span></span>](Uninstall-Module.md)
<span data-ttu-id="4371b-148">Deinstalliert ein Modul.</span><span class="sxs-lookup"><span data-stu-id="4371b-148">Uninstalls a module.</span></span>

### [<span data-ttu-id="4371b-149">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="4371b-149">Uninstall-Script</span></span>](Uninstall-Script.md)
<span data-ttu-id="4371b-150">Deinstalliert ein Skript.</span><span class="sxs-lookup"><span data-stu-id="4371b-150">Uninstalls a script.</span></span>

### [<span data-ttu-id="4371b-151">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="4371b-151">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
<span data-ttu-id="4371b-152">Hebt die Registrierung eines Repositorys auf</span><span class="sxs-lookup"><span data-stu-id="4371b-152">Unregisters a repository.</span></span>

### [<span data-ttu-id="4371b-153">Update-Module</span><span class="sxs-lookup"><span data-stu-id="4371b-153">Update-Module</span></span>](Update-Module.md)
<span data-ttu-id="4371b-154">Lädt die neueste Version der angegebenen Module aus einem Onlinekatalog auf den lokalen Computer herunter und installiert diese</span><span class="sxs-lookup"><span data-stu-id="4371b-154">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

### [<span data-ttu-id="4371b-155">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="4371b-155">Update-ModuleManifest</span></span>](Update-ModuleManifest.md)
<span data-ttu-id="4371b-156">Aktualisiert eine Modulmanifestdatei</span><span class="sxs-lookup"><span data-stu-id="4371b-156">Updates a module manifest file.</span></span>

### [<span data-ttu-id="4371b-157">Update-Script</span><span class="sxs-lookup"><span data-stu-id="4371b-157">Update-Script</span></span>](Update-Script.md)
<span data-ttu-id="4371b-158">Aktualisiert ein Skript.</span><span class="sxs-lookup"><span data-stu-id="4371b-158">Updates a script.</span></span>

### [<span data-ttu-id="4371b-159">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="4371b-159">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
<span data-ttu-id="4371b-160">Aktualisiert Informationen für ein Skript.</span><span class="sxs-lookup"><span data-stu-id="4371b-160">Updates information for a script.</span></span>
