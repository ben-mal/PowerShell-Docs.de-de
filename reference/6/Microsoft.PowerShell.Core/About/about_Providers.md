---
description: Hier wird beschrieben, wie PowerShell-Anbieter den Zugriff auf Daten und Komponenten ermöglichen, auf die in der Befehlszeile sonst nicht einfach zugegriffen werden kann. Die Daten werden in einem konsistenten Format dargestellt, das einem Dateisystem Laufwerk ähnelt.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_providers?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Providers
ms.openlocfilehash: cbafcab2b24e77a43d7b628ce9500f480ed9b5b8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221335"
---
# <a name="about-providers"></a><span data-ttu-id="ca934-105">Informationen zu Anbietern</span><span class="sxs-lookup"><span data-stu-id="ca934-105">About Providers</span></span>

## <a name="short-description"></a><span data-ttu-id="ca934-106">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca934-106">Short description</span></span>
<span data-ttu-id="ca934-107">Hier wird beschrieben, wie PowerShell-Anbieter den Zugriff auf Daten und Komponenten ermöglichen, auf die in der Befehlszeile sonst nicht einfach zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ca934-107">Describes how PowerShell providers provide access to data and components that wouldn't otherwise be easily accessible at the command line.</span></span>
<span data-ttu-id="ca934-108">Die Daten werden in einem konsistenten Format dargestellt, das einem Dateisystem Laufwerk ähnelt.</span><span class="sxs-lookup"><span data-stu-id="ca934-108">The data is presented in a consistent format that resembles a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="ca934-109">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca934-109">Long description</span></span>

<span data-ttu-id="ca934-110">PowerShell-Anbieter sind .net-Programme, die den Zugriff auf spezialisierte Datenspeicher bereitstellen, um die Anzeige und Verwaltung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="ca934-110">PowerShell providers are .NET programs that provide access to specialized data stores for easier viewing and management.</span></span> <span data-ttu-id="ca934-111">Die Daten werden in einem Laufwerk angezeigt, und Sie greifen auf die Daten in einem Pfad wie auf einem Festplattenlaufwerk zu.</span><span class="sxs-lookup"><span data-stu-id="ca934-111">The data appears in a drive, and you access the data in a path like you would on a hard disk drive.</span></span> <span data-ttu-id="ca934-112">Sie können alle integrierten Cmdlets verwenden, die der Anbieter unterstützt, um die Daten im Anbieter Laufwerk zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="ca934-112">You can use any of the built-in cmdlets that the provider supports to manage the data in the provider drive.</span></span> <span data-ttu-id="ca934-113">Und Sie können benutzerdefinierte Cmdlets verwenden, die speziell für die Daten entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="ca934-113">And, you can use custom cmdlets that are designed especially for the data.</span></span>

<span data-ttu-id="ca934-114">Die Anbieter können den integrierten Cmdlets auch dynamische Parameter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ca934-114">The providers can also add dynamic parameters to the built-in cmdlets.</span></span> <span data-ttu-id="ca934-115">Diese Parameter sind nur verfügbar, wenn Sie das-Cmdlet mit den Anbieter Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca934-115">These parameters are only available when you use the cmdlet with the provider data.</span></span>

## <a name="built-in-providers"></a><span data-ttu-id="ca934-116">Integrierte Anbieter</span><span class="sxs-lookup"><span data-stu-id="ca934-116">Built-in providers</span></span>

<span data-ttu-id="ca934-117">PowerShell umfasst eine Reihe integrierter Anbieter, mit denen Sie auf die verschiedenen Typen von Daten speichern zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="ca934-117">PowerShell includes a set of built-in providers that you can use to access the different types of data stores.</span></span>

| <span data-ttu-id="ca934-118">Anbieter</span><span class="sxs-lookup"><span data-stu-id="ca934-118">Provider</span></span>   |   <span data-ttu-id="ca934-119">Laufwerk (e)</span><span class="sxs-lookup"><span data-stu-id="ca934-119">Drive(s)</span></span>  |<span data-ttu-id="ca934-120">OutputType</span><span class="sxs-lookup"><span data-stu-id="ca934-120">OutputType</span></span>                                                    |
|----------- |------------ |--------------------------------------------------------------|
|<span data-ttu-id="ca934-121">Alias</span><span class="sxs-lookup"><span data-stu-id="ca934-121">Alias</span></span>       |<span data-ttu-id="ca934-122">Alias:</span><span class="sxs-lookup"><span data-stu-id="ca934-122">Alias:</span></span>       |<span data-ttu-id="ca934-123">System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="ca934-123">System.Management.Automation.AliasInfo</span></span>                        |
|<span data-ttu-id="ca934-124">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="ca934-124">Certificate</span></span> |<span data-ttu-id="ca934-125">Cert:</span><span class="sxs-lookup"><span data-stu-id="ca934-125">Cert:</span></span>        |<span data-ttu-id="ca934-126">Microsoft. PowerShell. Commands. X509StoreLocation</span><span class="sxs-lookup"><span data-stu-id="ca934-126">Microsoft.PowerShell.Commands.X509StoreLocation</span></span>               |
|            |             |<span data-ttu-id="ca934-127">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="ca934-127">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>|
|<span data-ttu-id="ca934-128">Environment</span><span class="sxs-lookup"><span data-stu-id="ca934-128">Environment</span></span> |<span data-ttu-id="ca934-129">Env:</span><span class="sxs-lookup"><span data-stu-id="ca934-129">Env:</span></span>         |<span data-ttu-id="ca934-130">System. Collections. ditionaryentry</span><span class="sxs-lookup"><span data-stu-id="ca934-130">System.Collections.DictionaryEntry</span></span>                            |
|<span data-ttu-id="ca934-131">FileSystem</span><span class="sxs-lookup"><span data-stu-id="ca934-131">FileSystem</span></span>  |<span data-ttu-id="ca934-132">C: (\*)</span><span class="sxs-lookup"><span data-stu-id="ca934-132">C: (\*)</span></span>       |<span data-ttu-id="ca934-133">System. IO. fileingefo</span><span class="sxs-lookup"><span data-stu-id="ca934-133">System.IO.FileInfo</span></span>                                            |
|            |             |<span data-ttu-id="ca934-134">System. IO. directoriyinfo</span><span class="sxs-lookup"><span data-stu-id="ca934-134">System.IO.DirectoryInfo</span></span>                                       |
|<span data-ttu-id="ca934-135">Funktion</span><span class="sxs-lookup"><span data-stu-id="ca934-135">Function</span></span>    |<span data-ttu-id="ca934-136">Funktion:</span><span class="sxs-lookup"><span data-stu-id="ca934-136">Function:</span></span>    |<span data-ttu-id="ca934-137">System. Management. Automation. functioninfo</span><span class="sxs-lookup"><span data-stu-id="ca934-137">System.Management.Automation.FunctionInfo</span></span>                     |
|<span data-ttu-id="ca934-138">Registrierung</span><span class="sxs-lookup"><span data-stu-id="ca934-138">Registry</span></span>    |<span data-ttu-id="ca934-139">HKLM: HKCU:</span><span class="sxs-lookup"><span data-stu-id="ca934-139">HKLM: HKCU:</span></span>  |<span data-ttu-id="ca934-140">Microsoft. Win32. RegistryKey</span><span class="sxs-lookup"><span data-stu-id="ca934-140">Microsoft.Win32.RegistryKey</span></span>                                   |
|<span data-ttu-id="ca934-141">Variable</span><span class="sxs-lookup"><span data-stu-id="ca934-141">Variable</span></span>    |<span data-ttu-id="ca934-142">Variable:</span><span class="sxs-lookup"><span data-stu-id="ca934-142">Variable:</span></span>    |<span data-ttu-id="ca934-143">System. Management. Automation. psvariable</span><span class="sxs-lookup"><span data-stu-id="ca934-143">System.Management.Automation.PSVariable</span></span>                       |
|<span data-ttu-id="ca934-144">WSMan</span><span class="sxs-lookup"><span data-stu-id="ca934-144">WSMan</span></span>       |<span data-ttu-id="ca934-145">WS-Management:</span><span class="sxs-lookup"><span data-stu-id="ca934-145">WSMan:</span></span>       |<span data-ttu-id="ca934-146">Microsoft. WSMAN. Management. wsmanconfigcontainerelement</span><span class="sxs-lookup"><span data-stu-id="ca934-146">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>        |

<span data-ttu-id="ca934-147">(\*) Die Dateisystem Laufwerke variieren je nach System.</span><span class="sxs-lookup"><span data-stu-id="ca934-147">(\*) The FileSystem drives vary on each system.</span></span>

<span data-ttu-id="ca934-148">Sie können auch Ihre eigenen PowerShell-Anbieter erstellen, und Sie können Anbieter installieren, die andere entwickeln.</span><span class="sxs-lookup"><span data-stu-id="ca934-148">You can also create your own PowerShell providers, and you can install providers that others develop.</span></span> <span data-ttu-id="ca934-149">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ca934-149">To list the providers that are available in your session, type:</span></span>

```powershell
Get-PSProvider
```

## <a name="installing-and-removing-providers"></a><span data-ttu-id="ca934-150">Installieren und Entfernen von Anbietern</span><span class="sxs-lookup"><span data-stu-id="ca934-150">Installing and removing providers</span></span>

<span data-ttu-id="ca934-151">Anbieter werden in der Regel über PowerShell-Module installiert.</span><span class="sxs-lookup"><span data-stu-id="ca934-151">Providers are typically installed via PowerShell modules.</span></span> <span data-ttu-id="ca934-152">Beim Importieren des Moduls wird der Anbieter in Ihre Sitzung geladen.</span><span class="sxs-lookup"><span data-stu-id="ca934-152">Importing the module loads the provider into your session.</span></span> <span data-ttu-id="ca934-153">Sie können die integrierten Anbieter nicht deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="ca934-153">You can't uninstall the built-in providers.</span></span> <span data-ttu-id="ca934-154">Sie können von anderen Modulen geladene Anbieter deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="ca934-154">You can uninstall providers loaded by other modules.</span></span>

<span data-ttu-id="ca934-155">Sie können einen Anbieter aus der aktuellen Sitzung mithilfe des `Remove-Module` Cmdlets entladen.</span><span class="sxs-lookup"><span data-stu-id="ca934-155">You can unload a provider from the current session using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="ca934-156">Mit diesem Cmdlet wird der Anbieter nicht deinstalliert, aber der Anbieter ist in der Sitzung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ca934-156">This cmdlet doesn't uninstall the provider, but it makes the provider unavailable in the session.</span></span>

<span data-ttu-id="ca934-157">Sie können auch das- `Remove-PSDrive` Cmdlet verwenden, um ein beliebiges Laufwerk aus der aktuellen Sitzung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="ca934-157">You can also use the `Remove-PSDrive` cmdlet to remove any drive from the current session.</span></span> <span data-ttu-id="ca934-158">Diese Daten auf dem Laufwerk sind nicht betroffen, aber das Laufwerk ist in dieser Sitzung nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ca934-158">This data on the drive isn't affected, but the drive is no longer available in that session.</span></span>

## <a name="viewing-providers"></a><span data-ttu-id="ca934-159">Anzeigen von Anbietern</span><span class="sxs-lookup"><span data-stu-id="ca934-159">Viewing providers</span></span>

<span data-ttu-id="ca934-160">Geben Sie Folgendes ein, um die PowerShell-Anbieter auf Ihrem Computer anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="ca934-160">To view the PowerShell providers on your computer, type:</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="ca934-161">Die Ausgabe listet die integrierten Anbieter und die Anbieter auf, die Sie der Sitzung hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="ca934-161">The output lists the built-in providers and the providers that you added to the session.</span></span>

## <a name="the-provider-cmdlets"></a><span data-ttu-id="ca934-162">Die Anbieter-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ca934-162">The provider cmdlets</span></span>

<span data-ttu-id="ca934-163">Die folgenden Cmdlets sind für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="ca934-163">The following cmdlets are designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="ca934-164">Sie können dieselben Cmdlets auf dieselbe Weise verwenden, um die verschiedenen Typen von Daten zu verwalten, die von Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="ca934-164">You can use the same cmdlets in the same way to manage the different types of data that providers expose.</span></span> <span data-ttu-id="ca934-165">Nachdem Sie erfahren haben, wie Sie die Daten eines Anbieters verwalten, können Sie die gleichen Prozeduren mit den Daten von beliebigen Anbietern verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca934-165">After you learn to manage the data of one provider, you can use the same procedures with the data from any provider.</span></span>

<span data-ttu-id="ca934-166">Beispielsweise wird mit dem- `New-Item` Cmdlet ein neues Element erstellt.</span><span class="sxs-lookup"><span data-stu-id="ca934-166">For example, the `New-Item` cmdlet creates a new item.</span></span> <span data-ttu-id="ca934-167">Auf dem `C:` Laufwerk, das vom **File System** -Anbieter unterstützt wird, können Sie verwenden, `New-Item` um eine neue Datei oder einen neuen Ordner zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ca934-167">In the `C:` drive that is supported by the **FileSystem** provider, you can use `New-Item` to create a new file or folder.</span></span> <span data-ttu-id="ca934-168">Auf den Laufwerken, die vom **Registrierungs** Anbieter unterstützt werden, können Sie verwenden, `New-Item` um einen neuen Registrierungsschlüssel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ca934-168">In the drives that are supported by the **Registry** provider, you can use `New-Item` to create a new registry key.</span></span> <span data-ttu-id="ca934-169">Im- `Alias:` Laufwerk können Sie verwenden, `New-Item` um einen neuen Alias zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ca934-169">In the `Alias:` drive, you can use `New-Item` to create a new alias.</span></span>

<span data-ttu-id="ca934-170">Ausführliche Informationen zu den folgenden Cmdlets erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="ca934-170">For detailed information about any of the following cmdlets, type:</span></span>

```
Get-Help <cmdlet-name> -Detailed
```

### <a name="childitem-cmdlets"></a><span data-ttu-id="ca934-171">ChildItem-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ca934-171">ChildItem cmdlets</span></span>

- [<span data-ttu-id="ca934-172">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="ca934-172">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="content-cmdlets"></a><span data-ttu-id="ca934-173">Content-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ca934-173">Content Cmdlets</span></span>

- [<span data-ttu-id="ca934-174">Add-Content</span><span class="sxs-lookup"><span data-stu-id="ca934-174">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="ca934-175">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="ca934-175">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="ca934-176">Get-Content</span><span class="sxs-lookup"><span data-stu-id="ca934-176">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="ca934-177">Set-Content</span><span class="sxs-lookup"><span data-stu-id="ca934-177">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="item-cmdlets"></a><span data-ttu-id="ca934-178">Item-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ca934-178">Item Cmdlets</span></span>

- [<span data-ttu-id="ca934-179">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="ca934-179">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="ca934-180">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="ca934-180">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="ca934-181">Get-Item</span><span class="sxs-lookup"><span data-stu-id="ca934-181">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="ca934-182">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="ca934-182">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="ca934-183">Move-Item</span><span class="sxs-lookup"><span data-stu-id="ca934-183">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="ca934-184">New-Item</span><span class="sxs-lookup"><span data-stu-id="ca934-184">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="ca934-185">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="ca934-185">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="ca934-186">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="ca934-186">Rename-Item</span></span>](xref:Microsoft.PowerShell.Management.Rename-Item)
- [<span data-ttu-id="ca934-187">Set-Item</span><span class="sxs-lookup"><span data-stu-id="ca934-187">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

### <a name="itemproperty-cmdlets"></a><span data-ttu-id="ca934-188">ItemProperty-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ca934-188">ItemProperty cmdlets</span></span>

- [<span data-ttu-id="ca934-189">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ca934-189">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="ca934-190">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ca934-190">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)
- [<span data-ttu-id="ca934-191">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ca934-191">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="ca934-192">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ca934-192">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)
- [<span data-ttu-id="ca934-193">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ca934-193">New-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.New-ItemProperty)
- [<span data-ttu-id="ca934-194">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ca934-194">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="ca934-195">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ca934-195">Rename-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Rename-ItemProperty)
- [<span data-ttu-id="ca934-196">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ca934-196">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

### <a name="location-cmdlets"></a><span data-ttu-id="ca934-197">Location-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ca934-197">Location cmdlets</span></span>

- [<span data-ttu-id="ca934-198">Get-Location</span><span class="sxs-lookup"><span data-stu-id="ca934-198">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="ca934-199">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="ca934-199">Pop-Location</span></span>](xref:Microsoft.PowerShell.Management.Pop-Location)
- [<span data-ttu-id="ca934-200">Push-Location</span><span class="sxs-lookup"><span data-stu-id="ca934-200">Push-Location</span></span>](xref:Microsoft.PowerShell.Management.Push-Location)
- [<span data-ttu-id="ca934-201">Set-Location</span><span class="sxs-lookup"><span data-stu-id="ca934-201">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)

### <a name="path-cmdlets"></a><span data-ttu-id="ca934-202">Pfad-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ca934-202">Path cmdlets</span></span>

- [<span data-ttu-id="ca934-203">Join-Path</span><span class="sxs-lookup"><span data-stu-id="ca934-203">Join-Path</span></span>](xref:Microsoft.PowerShell.Management.Join-Path)
- [<span data-ttu-id="ca934-204">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="ca934-204">Convert-Path</span></span>](xref:Microsoft.PowerShell.Management.Convert-Path)
- [<span data-ttu-id="ca934-205">Split-Path</span><span class="sxs-lookup"><span data-stu-id="ca934-205">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)
- [<span data-ttu-id="ca934-206">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="ca934-206">Resolve-Path</span></span>](xref:Microsoft.PowerShell.Management.Resolve-Path)
- [<span data-ttu-id="ca934-207">Test-Path</span><span class="sxs-lookup"><span data-stu-id="ca934-207">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="psdrive-cmdlets"></a><span data-ttu-id="ca934-208">PSDrive-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ca934-208">PSDrive cmdlets</span></span>

- [<span data-ttu-id="ca934-209">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="ca934-209">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="ca934-210">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="ca934-210">New-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.New-PSDrive)
- [<span data-ttu-id="ca934-211">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="ca934-211">Remove-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Remove-PSDrive)

### <a name="psprovider-cmdlets"></a><span data-ttu-id="ca934-212">Psprovider-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ca934-212">PSProvider Cmdlets</span></span>

- [<span data-ttu-id="ca934-213">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="ca934-213">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)

## <a name="viewing-provider-data"></a><span data-ttu-id="ca934-214">Anzeigen von Anbieter Daten</span><span class="sxs-lookup"><span data-stu-id="ca934-214">Viewing provider data</span></span>

<span data-ttu-id="ca934-215">Der Hauptvorteil eines Anbieters besteht darin, dass er seine Daten auf vertraute und konsistente Weise verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="ca934-215">The primary benefit of a provider is that it exposes its data in a familiar and consistent way.</span></span> <span data-ttu-id="ca934-216">Das Modell für die Datenpräsentation ist ein Dateisystem Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="ca934-216">The model for data presentation is a file system drive.</span></span>

<span data-ttu-id="ca934-217">Der Anbieter ermöglicht Ihnen das anzeigen, navigieren und Ändern von Elementen im Datenspeicher, als ob es sich um Daten in einem Dateisystem handelt.</span><span class="sxs-lookup"><span data-stu-id="ca934-217">The provider allows you to view, navigate, and change items in the data store as though they were data in a file system.</span></span> <span data-ttu-id="ca934-218">Der Zugriff auf den Datenspeicher erfolgt über den Namen des Laufwerks, das von ihm unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="ca934-218">The data store is accessed by the name of the drive that it supports.</span></span>

<span data-ttu-id="ca934-219">Das Laufwerk wird in der Standard Anzeige des `Get-PSProvider` Cmdlets aufgelistet, Sie können jedoch mithilfe des Cmdlets Informationen über das Anbieter Laufwerk erhalten `Get-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="ca934-219">The drive is listed in the default display of the `Get-PSProvider` cmdlet, but you can get information about the provider drive using the `Get-PSDrive` cmdlet.</span></span> <span data-ttu-id="ca934-220">Geben Sie z. b. Folgendes ein, um alle Eigenschaften des Laufwerks "function:" zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="ca934-220">For example, to get all the properties of the Function: drive, type:</span></span>

```powershell
Get-PSDrive Function | Format-List *
```

<span data-ttu-id="ca934-221">Sie können die Daten in einem Anbieter Laufwerk genau so wie auf einem Dateisystem Laufwerk anzeigen und durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="ca934-221">You can view and move through the data in a provider drive just as you would on a file system drive.</span></span>

<span data-ttu-id="ca934-222">Zum Anzeigen des Inhalts eines Anbieter Laufwerks verwenden Sie die Cmdlets Get-Item oder Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="ca934-222">To view the contents of a provider drive, use the Get-Item or Get-ChildItem cmdlets.</span></span> <span data-ttu-id="ca934-223">Geben Sie den Namen des Laufwerks gefolgt von einem Doppelpunkt (:) ein.</span><span class="sxs-lookup"><span data-stu-id="ca934-223">Type the drive name followed by a colon (:).</span></span> <span data-ttu-id="ca934-224">Wenn Sie z. b. den Inhalt des Alias:-Laufwerks anzeigen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ca934-224">For example, to view the contents of the Alias: drive, type:</span></span>

```powershell
Get-Item alias:
```

<span data-ttu-id="ca934-225">Sie können die Daten in einem beliebigen Laufwerk von einem anderen Laufwerk anzeigen und verwalten, indem Sie den Namen des Laufwerks in den Pfad einschließen.</span><span class="sxs-lookup"><span data-stu-id="ca934-225">You can view and manage the data in any drive from another drive by including the drive name in the path.</span></span> <span data-ttu-id="ca934-226">Geben Sie beispielsweise Folgendes ein, um den Registrierungsschlüssel "HKLM\Software" auf dem Laufwerk "HKLM:" auf einem anderen Laufwerk anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="ca934-226">For example, to view the HKLM\Software registry key in the HKLM: drive from another drive, type:</span></span>

```powershell
Get-ChildItem HKLM:\SOFTWARE\
```

<span data-ttu-id="ca934-227">Um das Laufwerk zu öffnen, verwenden Sie das Cmdlet "Set-Location".</span><span class="sxs-lookup"><span data-stu-id="ca934-227">To open the drive, use the Set-Location cmdlet.</span></span> <span data-ttu-id="ca934-228">Merken Sie sich den Doppelpunkt, wenn Sie den Laufwerks Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="ca934-228">Remember the colon when you specify the drive path.</span></span> <span data-ttu-id="ca934-229">Wenn Sie z. b. ihren Speicherort in das Stammverzeichnis des Zertifikats "CERT:" ändern möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ca934-229">For example, to change your location to the root directory of the Cert: drive, type:</span></span>

```powershell
Set-Location cert:
```

<span data-ttu-id="ca934-230">Wenn Sie den Inhalt des Zertifikats "CERT:" anzeigen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ca934-230">Then, to view the contents of the Cert: drive, type:</span></span>

```powershell
Get-ChildItem
```

## <a name="moving-through-hierarchical-data"></a><span data-ttu-id="ca934-231">Verschieben von hierarchischen Daten</span><span class="sxs-lookup"><span data-stu-id="ca934-231">Moving through hierarchical data</span></span>

<span data-ttu-id="ca934-232">Sie können ein Anbieter Laufwerk wie ein Festplattenlaufwerk durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="ca934-232">You can move through a provider drive just as you would a hard disk drive.</span></span>
<span data-ttu-id="ca934-233">Wenn die Daten in einer Hierarchie von Elementen innerhalb von Elementen angeordnet sind, verwenden Sie einen umgekehrten Schrägstrich ( `\` ), um ein untergeordnetes Element anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ca934-233">If the data is arranged in a hierarchy of items within items, use a backslash (`\`) to indicate a child item.</span></span> <span data-ttu-id="ca934-234">Verwenden Sie das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="ca934-234">Use the following format:</span></span>

```
drive:\location\child-location\...
```

<span data-ttu-id="ca934-235">Wenn Sie beispielsweise ihren Speicherort in den Registrierungsschlüssel "HKLM\Software" ändern möchten, geben Sie einen Set-Location Befehl ein, z. b.:</span><span class="sxs-lookup"><span data-stu-id="ca934-235">For example, to change your location to the HKLM\Software registry key, type a Set-Location command, such as:</span></span>

```powershell
Set-Location HKLM:\SOFTWARE\
```

<span data-ttu-id="ca934-236">Wenn ein beliebiges Element im voll qualifizierten Namen Leerzeichen enthält, müssen Sie den Namen in doppelte Anführungszeichen ( `"` ) einschließen.</span><span class="sxs-lookup"><span data-stu-id="ca934-236">If any element in the fully qualified name includes spaces, you must enclose the name in double-quotation marks (`"`).</span></span> <span data-ttu-id="ca934-237">Das folgende Beispiel zeigt einen voll qualifizierten Pfad, der Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="ca934-237">The following example shows a fully qualified path that includes spaces.</span></span>

```
"C:\Program Files\Internet Explorer\iexplore.exe"
```

<span data-ttu-id="ca934-238">Sie können auch relative Verweise auf Speicherorte verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca934-238">You can also use relative references to locations.</span></span> <span data-ttu-id="ca934-239">Ein Punkt ( `.` ) stellt den aktuellen Speicherort dar.</span><span class="sxs-lookup"><span data-stu-id="ca934-239">A dot (`.`) represents the current location.</span></span> <span data-ttu-id="ca934-240">Wenn Sie z. b. im `HKLM:\Software\Microsoft` Registrierungsschlüssel sind und die Registrierungs Unterschlüssel im Schlüssel auflisten möchten `HKLM:\Software\Microsoft\PowerShell` , geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="ca934-240">For example, if you are in the `HKLM:\Software\Microsoft` registry key, and you want to list the registry subkeys in the `HKLM:\Software\Microsoft\PowerShell` key, type the following command:</span></span>

```powershell
Get-ChildItem .\PowerShell
```

<span data-ttu-id="ca934-241">Außerdem verweist Double-Dots ( `..` ) direkt oberhalb ihres aktuellen Speicher Orts auf das Verzeichnis oder den Container.</span><span class="sxs-lookup"><span data-stu-id="ca934-241">Also, double-dots (`..`) refers to the directory or container directly above your current location.</span></span> <span data-ttu-id="ca934-242">Sie können doppelte Punkte () verwenden `..` , um durch eine Anbieter Hierarchie zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="ca934-242">You can use double-dots (`..`) to navigate through a provider hierarchy.</span></span>

```
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters\> cd ..\..\LanmanWorkstation\Parameters
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters>
```

## <a name="provider-home"></a><span data-ttu-id="ca934-243">Startseite des Anbieters</span><span class="sxs-lookup"><span data-stu-id="ca934-243">Provider Home</span></span>

<span data-ttu-id="ca934-244">Anbieter verfügen auch über einen **eigenen** Standort.</span><span class="sxs-lookup"><span data-stu-id="ca934-244">Providers also have a **Home** location.</span></span>  <span data-ttu-id="ca934-245">Dieser Speicherort wird von allen unter `PSDrives` stützt, die vom Anbieter unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="ca934-245">This location is shared by all `PSDrives` backed by the provider.</span></span> <span data-ttu-id="ca934-246">Sie kann abgerufen werden, indem Sie die **Home** -Eigenschaft des Anbieters anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ca934-246">It can be retrieved by viewing the **Home** property of the provider.</span></span>

```powershell
Get-PSProvider | Format-Table Name, Home
```

```Output
Name        Home
----        ----
Registry
Alias
Environment
FileSystem  C:\Users\username
Function
Variable
Certificate
```

<span data-ttu-id="ca934-247">Der **File System** -Anbieter ist der einzige Anbieter, der über einen Standardwert für **Home** verfügt.</span><span class="sxs-lookup"><span data-stu-id="ca934-247">The **FileSystem** provider is the only provider that has a default value for **Home**.</span></span> <span data-ttu-id="ca934-248">Dies ist der gleiche Wert wie `$Home` .</span><span class="sxs-lookup"><span data-stu-id="ca934-248">It's the same value as `$Home`.</span></span> <span data-ttu-id="ca934-249">Weitere Informationen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="ca934-249">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="ca934-250">Mithilfe der-Eigenschaft können Sie das **Basisverzeichnis für** einen Anbieter für die aktuelle Sitzung festlegen.</span><span class="sxs-lookup"><span data-stu-id="ca934-250">You can set the **Home** directory for a provider, for the current session, using its property.</span></span>

```powershell
(Get-PSProvider FileSystem).Home = "C:\"
```

<span data-ttu-id="ca934-251">Das `~` -Zeichen kann verwendet werden, um das Basisverzeichnis des Anbieters darzustellen.</span><span class="sxs-lookup"><span data-stu-id="ca934-251">The `~` character can be used to represent the provider's home directory.</span></span>
<span data-ttu-id="ca934-252">Wenn für den Anbieter kein **Start** Speicherort festgelegt ist, wird ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ca934-252">If the provider doesn't have a **Home** location set, you see an error.</span></span>

```powershell
Cert:\> Set-Location ~
```

```Output
Set-Location : Home location for this provider isn't set. To set the home
location, call "(get-psprovider 'Certificate').Home = 'path'".
At line:1 char:1
+ Set-Location ~
+ ~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Set-Location],
                              PSInvalidOperationException
...
```

## <a name="finding-dynamic-parameters"></a><span data-ttu-id="ca934-253">Suchen von dynamischen Parametern</span><span class="sxs-lookup"><span data-stu-id="ca934-253">Finding dynamic parameters</span></span>

<span data-ttu-id="ca934-254">Dynamische Parameter sind Cmdlet-Parameter, die einem Cmdlet von einem Anbieter hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ca934-254">Dynamic parameters are cmdlet parameters that are added to a cmdlet by a provider.</span></span> <span data-ttu-id="ca934-255">Diese Parameter sind nur verfügbar, wenn das Cmdlet mit dem Anbieter verwendet wird, der Sie hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="ca934-255">These parameters are available only when the cmdlet is used with the provider that added them.</span></span>

<span data-ttu-id="ca934-256">Beispielsweise fügt das `Cert:` Laufwerk dem-Cmdlet und dem-Cmdlet den **codeSigningCert** -Parameter hinzu `Get-Item` `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="ca934-256">For example, the `Cert:` drive adds the **CodeSigningCert** parameter to the `Get-Item` and `Get-ChildItem` cmdlets.</span></span> <span data-ttu-id="ca934-257">Sie können diesen Parameter nur verwenden, wenn Sie `Get-Item` oder `Get-ChildItem` auf dem `Cert:` Laufwerk verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca934-257">You can use this parameter only when you use `Get-Item` or `Get-ChildItem` in the `Cert:` drive.</span></span>

<span data-ttu-id="ca934-258">Eine Liste der dynamischen Parameter, die von einem Anbieter unterstützt werden, finden Sie in der Hilfedatei für den Anbieter.</span><span class="sxs-lookup"><span data-stu-id="ca934-258">For a list of the dynamic parameters that a provider supports, see the Help file for the provider.</span></span> <span data-ttu-id="ca934-259">Typ:</span><span class="sxs-lookup"><span data-stu-id="ca934-259">Type:</span></span>

```
Get-Help <provider-name>
```

<span data-ttu-id="ca934-260">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ca934-260">For example:</span></span>

```powershell
Get-Help certificate
```

## <a name="learning-about-providers"></a><span data-ttu-id="ca934-261">Kennenlernen von Anbietern</span><span class="sxs-lookup"><span data-stu-id="ca934-261">Learning about providers</span></span>

<span data-ttu-id="ca934-262">Obwohl alle Anbieter Daten auf den Laufwerken angezeigt werden und Sie die gleichen Methoden verwenden, um Sie zu durchlaufen, wird die Ähnlichkeit dort angehalten.</span><span class="sxs-lookup"><span data-stu-id="ca934-262">Although all provider data appears in drives and you use the same methods to move through them, the similarity stops there.</span></span> <span data-ttu-id="ca934-263">Die Datenspeicher, die der Anbieter verfügbar macht, können so unterschiedlich sein wie Active Directory Standorte und Microsoft Exchange Server-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="ca934-263">The data stores that the provider exposes can be as varied as Active Directory locations and Microsoft Exchange Server mailboxes.</span></span>

<span data-ttu-id="ca934-264">Informationen zu einzelnen PowerShell-Anbietern erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="ca934-264">For information about individual PowerShell providers, type:</span></span>

```
Get-Help <ProviderName>
```

<span data-ttu-id="ca934-265">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ca934-265">For example:</span></span>

```powershell
Get-Help registry
```

<span data-ttu-id="ca934-266">Eine Liste der Hilfe Themen zu den Anbietern erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="ca934-266">For a list of Help topics about the providers, type:</span></span>

```powershell
Get-Help * -Category Provider
```

## <a name="see-also"></a><span data-ttu-id="ca934-267">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="ca934-267">See also</span></span>

[<span data-ttu-id="ca934-268">about_Locations</span><span class="sxs-lookup"><span data-stu-id="ca934-268">about_Locations</span></span>](about_Locations.md)

[<span data-ttu-id="ca934-269">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="ca934-269">about_Path_Syntax</span></span>](about_Path_Syntax.md)
