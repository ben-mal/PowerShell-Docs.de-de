---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 1d73a601-4a6c-43c5-ba3f-619b18bbb404
Module Name: PowerShellGet
ms.date: 06/09/2017
schema: 2.0.0
title: PowerShellGet
ms.openlocfilehash: 0d4e5e26184558055a17f99bd5321aaf3f3789f7
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99602118"
---
# <span data-ttu-id="2d49a-102">PowerShellGet-Modul</span><span class="sxs-lookup"><span data-stu-id="2d49a-102">PowerShellGet Module</span></span>

## <span data-ttu-id="2d49a-103">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2d49a-103">Description</span></span>

<span data-ttu-id="2d49a-104">PowerShellGet ist ein Modul mit Befehlen zum ermitteln, installieren, aktualisieren und Veröffentlichen von PowerShell-Artefakten wie Modulen, DSC-Ressourcen, Rollen Funktionen und Skripts.</span><span class="sxs-lookup"><span data-stu-id="2d49a-104">PowerShellGet is a module with commands for discovering, installing, updating and publishing PowerShell artifacts like Modules, DSC Resources, Role Capabilities, and Scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d49a-105">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="2d49a-105">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="2d49a-106">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="2d49a-106">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="2d49a-107">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="2d49a-107">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="2d49a-108">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="2d49a-108">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="2d49a-109">PowerShellGet-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2d49a-109">PowerShellGet Cmdlets</span></span>

### [<span data-ttu-id="2d49a-110">Find-Command</span><span class="sxs-lookup"><span data-stu-id="2d49a-110">Find-Command</span></span>](Find-Command.md)
<span data-ttu-id="2d49a-111">Sucht PowerShell-Befehle in Modulen.</span><span class="sxs-lookup"><span data-stu-id="2d49a-111">Finds PowerShell commands in modules.</span></span>

### [<span data-ttu-id="2d49a-112">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="2d49a-112">Find-DscResource</span></span>](Find-DscResource.md)
<span data-ttu-id="2d49a-113">Sucht DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="2d49a-113">Finds Desired State Configuration (DSC) resources.</span></span>

### [<span data-ttu-id="2d49a-114">Find-Module</span><span class="sxs-lookup"><span data-stu-id="2d49a-114">Find-Module</span></span>](Find-Module.md)
<span data-ttu-id="2d49a-115">Sucht Module in einem Repository, die den angegebenen Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2d49a-115">Finds modules in a repository that match specified criteria.</span></span>

### [<span data-ttu-id="2d49a-116">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="2d49a-116">Find-RoleCapability</span></span>](Find-RoleCapability.md)
<span data-ttu-id="2d49a-117">Sucht nach Rollenfunktionen in Modulen.</span><span class="sxs-lookup"><span data-stu-id="2d49a-117">Finds role capabilities in modules.</span></span>

### [<span data-ttu-id="2d49a-118">Find-Script</span><span class="sxs-lookup"><span data-stu-id="2d49a-118">Find-Script</span></span>](Find-Script.md)
<span data-ttu-id="2d49a-119">Sucht nach einem Skript.</span><span class="sxs-lookup"><span data-stu-id="2d49a-119">Finds a script.</span></span>

### [<span data-ttu-id="2d49a-120">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="2d49a-120">Get-InstalledModule</span></span>](Get-InstalledModule.md)
<span data-ttu-id="2d49a-121">Ruft eine Liste von Modulen auf dem Computer ab, die von PowerShellGet installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="2d49a-121">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

### [<span data-ttu-id="2d49a-122">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="2d49a-122">Get-InstalledScript</span></span>](Get-InstalledScript.md)
<span data-ttu-id="2d49a-123">Ruft ein installiertes Skript ab.</span><span class="sxs-lookup"><span data-stu-id="2d49a-123">Gets an installed script.</span></span>

### [<span data-ttu-id="2d49a-124">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="2d49a-124">Get-PSRepository</span></span>](Get-PSRepository.md)
<span data-ttu-id="2d49a-125">Ruft PowerShell-Repository ab.</span><span class="sxs-lookup"><span data-stu-id="2d49a-125">Gets PowerShell repositories.</span></span>

### [<span data-ttu-id="2d49a-126">Install-Module</span><span class="sxs-lookup"><span data-stu-id="2d49a-126">Install-Module</span></span>](Install-Module.md)
<span data-ttu-id="2d49a-127">Lädt ein oder mehrere Module aus einem Repository herunter und installiert Sie auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="2d49a-127">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

### [<span data-ttu-id="2d49a-128">Install-Script</span><span class="sxs-lookup"><span data-stu-id="2d49a-128">Install-Script</span></span>](Install-Script.md)
<span data-ttu-id="2d49a-129">Installiert ein Skript.</span><span class="sxs-lookup"><span data-stu-id="2d49a-129">Installs a script.</span></span>

### [<span data-ttu-id="2d49a-130">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="2d49a-130">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)
<span data-ttu-id="2d49a-131">Erstellt eine Skriptdatei mit Metadaten</span><span class="sxs-lookup"><span data-stu-id="2d49a-131">Creates a script file with metadata.</span></span>

### [<span data-ttu-id="2d49a-132">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="2d49a-132">Publish-Module</span></span>](Publish-Module.md)
<span data-ttu-id="2d49a-133">Veröffentlicht ein angegebenes Modul aus dem lokalen Computer in einem Onlinekatalog</span><span class="sxs-lookup"><span data-stu-id="2d49a-133">Publishes a specified module from the local computer to an online gallery.</span></span>

### [<span data-ttu-id="2d49a-134">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="2d49a-134">Publish-Script</span></span>](Publish-Script.md)
<span data-ttu-id="2d49a-135">Veröffentlicht ein Skript.</span><span class="sxs-lookup"><span data-stu-id="2d49a-135">Publishes a script.</span></span>

### [<span data-ttu-id="2d49a-136">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="2d49a-136">Register-PSRepository</span></span>](Register-PSRepository.md)
<span data-ttu-id="2d49a-137">Registriert ein PowerShell-Repository.</span><span class="sxs-lookup"><span data-stu-id="2d49a-137">Registers a PowerShell repository.</span></span>

### [<span data-ttu-id="2d49a-138">Save-Module</span><span class="sxs-lookup"><span data-stu-id="2d49a-138">Save-Module</span></span>](Save-Module.md)
<span data-ttu-id="2d49a-139">Speichert ein Modul und seine Abhängigkeiten auf dem lokalen Computer, installiert das Modul jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="2d49a-139">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

### [<span data-ttu-id="2d49a-140">Save-Script</span><span class="sxs-lookup"><span data-stu-id="2d49a-140">Save-Script</span></span>](Save-Script.md)
<span data-ttu-id="2d49a-141">Speichert ein Skript.</span><span class="sxs-lookup"><span data-stu-id="2d49a-141">Saves a script.</span></span>

### [<span data-ttu-id="2d49a-142">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="2d49a-142">Set-PSRepository</span></span>](Set-PSRepository.md)
<span data-ttu-id="2d49a-143">Legt Werte für ein registriertes Repository fest.</span><span class="sxs-lookup"><span data-stu-id="2d49a-143">Sets values for a registered repository.</span></span>

### [<span data-ttu-id="2d49a-144">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="2d49a-144">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)
<span data-ttu-id="2d49a-145">Überprüft einen Kommentar Block für ein Skript.</span><span class="sxs-lookup"><span data-stu-id="2d49a-145">Validates a comment block for a script.</span></span>

### [<span data-ttu-id="2d49a-146">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="2d49a-146">Uninstall-Module</span></span>](Uninstall-Module.md)
<span data-ttu-id="2d49a-147">Deinstalliert ein Modul.</span><span class="sxs-lookup"><span data-stu-id="2d49a-147">Uninstalls a module.</span></span>

### [<span data-ttu-id="2d49a-148">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="2d49a-148">Uninstall-Script</span></span>](Uninstall-Script.md)
<span data-ttu-id="2d49a-149">Deinstalliert ein Skript.</span><span class="sxs-lookup"><span data-stu-id="2d49a-149">Uninstalls a script.</span></span>

### [<span data-ttu-id="2d49a-150">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="2d49a-150">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
<span data-ttu-id="2d49a-151">Hebt die Registrierung eines Repositorys auf</span><span class="sxs-lookup"><span data-stu-id="2d49a-151">Unregisters a repository.</span></span>

### [<span data-ttu-id="2d49a-152">Update-Module</span><span class="sxs-lookup"><span data-stu-id="2d49a-152">Update-Module</span></span>](Update-Module.md)
<span data-ttu-id="2d49a-153">Lädt die neueste Version der angegebenen Module aus einem Onlinekatalog auf den lokalen Computer herunter und installiert diese</span><span class="sxs-lookup"><span data-stu-id="2d49a-153">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

### [<span data-ttu-id="2d49a-154">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="2d49a-154">Update-ModuleManifest</span></span>](Update-ModuleManifest.md)
<span data-ttu-id="2d49a-155">Aktualisiert eine Modulmanifestdatei</span><span class="sxs-lookup"><span data-stu-id="2d49a-155">Updates a module manifest file.</span></span>

### [<span data-ttu-id="2d49a-156">Update-Script</span><span class="sxs-lookup"><span data-stu-id="2d49a-156">Update-Script</span></span>](Update-Script.md)
<span data-ttu-id="2d49a-157">Aktualisiert ein Skript.</span><span class="sxs-lookup"><span data-stu-id="2d49a-157">Updates a script.</span></span>

### [<span data-ttu-id="2d49a-158">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="2d49a-158">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
<span data-ttu-id="2d49a-159">Aktualisiert Informationen für ein Skript.</span><span class="sxs-lookup"><span data-stu-id="2d49a-159">Updates information for a script.</span></span>
