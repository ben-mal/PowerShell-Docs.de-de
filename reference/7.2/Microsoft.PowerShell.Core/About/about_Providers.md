---
description: Hier wird beschrieben, wie PowerShell-Anbieter den Zugriff auf Daten und Komponenten ermöglichen, auf die in der Befehlszeile sonst nicht einfach zugegriffen werden kann. Die Daten werden in einem konsistenten Format dargestellt, das einem Dateisystem Laufwerk ähnelt.
Locale: en-US
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_providers?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Providers
ms.openlocfilehash: 6073ef13a6d0a02cded69073d7ffaef903a807ea
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598396"
---
# <a name="about-providers"></a><span data-ttu-id="04a70-104">Informationen zu Anbietern</span><span class="sxs-lookup"><span data-stu-id="04a70-104">About Providers</span></span>

## <a name="short-description"></a><span data-ttu-id="04a70-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04a70-105">Short description</span></span>
<span data-ttu-id="04a70-106">Hier wird beschrieben, wie PowerShell-Anbieter den Zugriff auf Daten und Komponenten ermöglichen, auf die in der Befehlszeile sonst nicht einfach zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="04a70-106">Describes how PowerShell providers provide access to data and components that wouldn't otherwise be easily accessible at the command line.</span></span>
<span data-ttu-id="04a70-107">Die Daten werden in einem konsistenten Format dargestellt, das einem Dateisystem Laufwerk ähnelt.</span><span class="sxs-lookup"><span data-stu-id="04a70-107">The data is presented in a consistent format that resembles a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="04a70-108">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04a70-108">Long description</span></span>

<span data-ttu-id="04a70-109">PowerShell-Anbieter sind .net-Programme, die den Zugriff auf spezialisierte Datenspeicher bereitstellen, um die Anzeige und Verwaltung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="04a70-109">PowerShell providers are .NET programs that provide access to specialized data stores for easier viewing and management.</span></span> <span data-ttu-id="04a70-110">Die Daten werden in einem Laufwerk angezeigt, und Sie greifen auf die Daten in einem Pfad wie auf einem Festplattenlaufwerk zu.</span><span class="sxs-lookup"><span data-stu-id="04a70-110">The data appears in a drive, and you access the data in a path like you would on a hard disk drive.</span></span> <span data-ttu-id="04a70-111">Sie können alle integrierten Cmdlets verwenden, die der Anbieter unterstützt, um die Daten im Anbieter Laufwerk zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="04a70-111">You can use any of the built-in cmdlets that the provider supports to manage the data in the provider drive.</span></span> <span data-ttu-id="04a70-112">Und Sie können benutzerdefinierte Cmdlets verwenden, die speziell für die Daten entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="04a70-112">And, you can use custom cmdlets that are designed especially for the data.</span></span>

<span data-ttu-id="04a70-113">Die Anbieter können den integrierten Cmdlets auch dynamische Parameter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="04a70-113">The providers can also add dynamic parameters to the built-in cmdlets.</span></span> <span data-ttu-id="04a70-114">Diese Parameter sind nur verfügbar, wenn Sie das-Cmdlet mit den Anbieter Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="04a70-114">These parameters are only available when you use the cmdlet with the provider data.</span></span>

## <a name="built-in-providers"></a><span data-ttu-id="04a70-115">Integrierte Anbieter</span><span class="sxs-lookup"><span data-stu-id="04a70-115">Built-in providers</span></span>

<span data-ttu-id="04a70-116">PowerShell umfasst eine Reihe integrierter Anbieter, mit denen Sie auf die verschiedenen Typen von Daten speichern zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="04a70-116">PowerShell includes a set of built-in providers that you can use to access the different types of data stores.</span></span>

| <span data-ttu-id="04a70-117">Anbieter</span><span class="sxs-lookup"><span data-stu-id="04a70-117">Provider</span></span>   |   <span data-ttu-id="04a70-118">Laufwerk (e)</span><span class="sxs-lookup"><span data-stu-id="04a70-118">Drive(s)</span></span>  |<span data-ttu-id="04a70-119">OutputType</span><span class="sxs-lookup"><span data-stu-id="04a70-119">OutputType</span></span>                                                    |
|----------- |------------ |--------------------------------------------------------------|
|<span data-ttu-id="04a70-120">Alias</span><span class="sxs-lookup"><span data-stu-id="04a70-120">Alias</span></span>       |<span data-ttu-id="04a70-121">Alias:</span><span class="sxs-lookup"><span data-stu-id="04a70-121">Alias:</span></span>       |<span data-ttu-id="04a70-122">System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="04a70-122">System.Management.Automation.AliasInfo</span></span>                        |
|<span data-ttu-id="04a70-123">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="04a70-123">Certificate</span></span> |<span data-ttu-id="04a70-124">Cert:</span><span class="sxs-lookup"><span data-stu-id="04a70-124">Cert:</span></span>        |<span data-ttu-id="04a70-125">Microsoft. PowerShell. Commands. X509StoreLocation</span><span class="sxs-lookup"><span data-stu-id="04a70-125">Microsoft.PowerShell.Commands.X509StoreLocation</span></span>               |
|            |             |<span data-ttu-id="04a70-126">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="04a70-126">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>|
|<span data-ttu-id="04a70-127">Umgebung</span><span class="sxs-lookup"><span data-stu-id="04a70-127">Environment</span></span> |<span data-ttu-id="04a70-128">Env:</span><span class="sxs-lookup"><span data-stu-id="04a70-128">Env:</span></span>         |<span data-ttu-id="04a70-129">System. Collections. ditionaryentry</span><span class="sxs-lookup"><span data-stu-id="04a70-129">System.Collections.DictionaryEntry</span></span>                            |
|<span data-ttu-id="04a70-130">FileSystem</span><span class="sxs-lookup"><span data-stu-id="04a70-130">FileSystem</span></span>  |<span data-ttu-id="04a70-131">C: (\*)</span><span class="sxs-lookup"><span data-stu-id="04a70-131">C: (\*)</span></span>       |<span data-ttu-id="04a70-132">System. IO. fileingefo</span><span class="sxs-lookup"><span data-stu-id="04a70-132">System.IO.FileInfo</span></span>                                            |
|            |             |<span data-ttu-id="04a70-133">System. IO. directoriyinfo</span><span class="sxs-lookup"><span data-stu-id="04a70-133">System.IO.DirectoryInfo</span></span>                                       |
|<span data-ttu-id="04a70-134">Funktion</span><span class="sxs-lookup"><span data-stu-id="04a70-134">Function</span></span>    |<span data-ttu-id="04a70-135">Funktion:</span><span class="sxs-lookup"><span data-stu-id="04a70-135">Function:</span></span>    |<span data-ttu-id="04a70-136">System. Management. Automation. functioninfo</span><span class="sxs-lookup"><span data-stu-id="04a70-136">System.Management.Automation.FunctionInfo</span></span>                     |
|<span data-ttu-id="04a70-137">Registrierung</span><span class="sxs-lookup"><span data-stu-id="04a70-137">Registry</span></span>    |<span data-ttu-id="04a70-138">HKLM: HKCU:</span><span class="sxs-lookup"><span data-stu-id="04a70-138">HKLM: HKCU:</span></span>  |<span data-ttu-id="04a70-139">Microsoft. Win32. RegistryKey</span><span class="sxs-lookup"><span data-stu-id="04a70-139">Microsoft.Win32.RegistryKey</span></span>                                   |
|<span data-ttu-id="04a70-140">Variable</span><span class="sxs-lookup"><span data-stu-id="04a70-140">Variable</span></span>    |<span data-ttu-id="04a70-141">Variable:</span><span class="sxs-lookup"><span data-stu-id="04a70-141">Variable:</span></span>    |<span data-ttu-id="04a70-142">System. Management. Automation. psvariable</span><span class="sxs-lookup"><span data-stu-id="04a70-142">System.Management.Automation.PSVariable</span></span>                       |
|<span data-ttu-id="04a70-143">WSMan</span><span class="sxs-lookup"><span data-stu-id="04a70-143">WSMan</span></span>       |<span data-ttu-id="04a70-144">WS-Management:</span><span class="sxs-lookup"><span data-stu-id="04a70-144">WSMan:</span></span>       |<span data-ttu-id="04a70-145">Microsoft. WSMAN. Management. wsmanconfigcontainerelement</span><span class="sxs-lookup"><span data-stu-id="04a70-145">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>        |

<span data-ttu-id="04a70-146">(\*) Die Dateisystem Laufwerke variieren je nach System.</span><span class="sxs-lookup"><span data-stu-id="04a70-146">(\*) The FileSystem drives vary on each system.</span></span>

<span data-ttu-id="04a70-147">Sie können auch Ihre eigenen PowerShell-Anbieter erstellen, und Sie können Anbieter installieren, die andere entwickeln.</span><span class="sxs-lookup"><span data-stu-id="04a70-147">You can also create your own PowerShell providers, and you can install providers that others develop.</span></span> <span data-ttu-id="04a70-148">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="04a70-148">To list the providers that are available in your session, type:</span></span>

```powershell
Get-PSProvider
```

## <a name="installing-and-removing-providers"></a><span data-ttu-id="04a70-149">Installieren und Entfernen von Anbietern</span><span class="sxs-lookup"><span data-stu-id="04a70-149">Installing and removing providers</span></span>

<span data-ttu-id="04a70-150">Anbieter werden in der Regel über PowerShell-Module installiert.</span><span class="sxs-lookup"><span data-stu-id="04a70-150">Providers are typically installed via PowerShell modules.</span></span> <span data-ttu-id="04a70-151">Beim Importieren des Moduls wird der Anbieter in Ihre Sitzung geladen.</span><span class="sxs-lookup"><span data-stu-id="04a70-151">Importing the module loads the provider into your session.</span></span> <span data-ttu-id="04a70-152">Sie können die integrierten Anbieter nicht deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="04a70-152">You can't uninstall the built-in providers.</span></span> <span data-ttu-id="04a70-153">Sie können von anderen Modulen geladene Anbieter deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="04a70-153">You can uninstall providers loaded by other modules.</span></span>

<span data-ttu-id="04a70-154">Sie können einen Anbieter aus der aktuellen Sitzung mithilfe des `Remove-Module` Cmdlets entladen.</span><span class="sxs-lookup"><span data-stu-id="04a70-154">You can unload a provider from the current session using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="04a70-155">Mit diesem Cmdlet wird der Anbieter nicht deinstalliert, aber der Anbieter ist in der Sitzung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="04a70-155">This cmdlet doesn't uninstall the provider, but it makes the provider unavailable in the session.</span></span>

<span data-ttu-id="04a70-156">Sie können auch das- `Remove-PSDrive` Cmdlet verwenden, um ein beliebiges Laufwerk aus der aktuellen Sitzung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="04a70-156">You can also use the `Remove-PSDrive` cmdlet to remove any drive from the current session.</span></span> <span data-ttu-id="04a70-157">Diese Daten auf dem Laufwerk sind nicht betroffen, aber das Laufwerk ist in dieser Sitzung nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="04a70-157">This data on the drive isn't affected, but the drive is no longer available in that session.</span></span>

## <a name="viewing-providers"></a><span data-ttu-id="04a70-158">Anzeigen von Anbietern</span><span class="sxs-lookup"><span data-stu-id="04a70-158">Viewing providers</span></span>

<span data-ttu-id="04a70-159">Geben Sie Folgendes ein, um die PowerShell-Anbieter auf Ihrem Computer anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="04a70-159">To view the PowerShell providers on your computer, type:</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="04a70-160">Die Ausgabe listet die integrierten Anbieter und die Anbieter auf, die Sie der Sitzung hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="04a70-160">The output lists the built-in providers and the providers that you added to the session.</span></span>

## <a name="the-provider-cmdlets"></a><span data-ttu-id="04a70-161">Die Anbieter-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="04a70-161">The provider cmdlets</span></span>

<span data-ttu-id="04a70-162">Die folgenden Cmdlets sind für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="04a70-162">The following cmdlets are designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="04a70-163">Sie können dieselben Cmdlets auf dieselbe Weise verwenden, um die verschiedenen Typen von Daten zu verwalten, die von Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="04a70-163">You can use the same cmdlets in the same way to manage the different types of data that providers expose.</span></span> <span data-ttu-id="04a70-164">Nachdem Sie erfahren haben, wie Sie die Daten eines Anbieters verwalten, können Sie die gleichen Prozeduren mit den Daten von beliebigen Anbietern verwenden.</span><span class="sxs-lookup"><span data-stu-id="04a70-164">After you learn to manage the data of one provider, you can use the same procedures with the data from any provider.</span></span>

<span data-ttu-id="04a70-165">Beispielsweise wird mit dem- `New-Item` Cmdlet ein neues Element erstellt.</span><span class="sxs-lookup"><span data-stu-id="04a70-165">For example, the `New-Item` cmdlet creates a new item.</span></span> <span data-ttu-id="04a70-166">Auf dem `C:` Laufwerk, das vom **File System** -Anbieter unterstützt wird, können Sie verwenden, `New-Item` um eine neue Datei oder einen neuen Ordner zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="04a70-166">In the `C:` drive that is supported by the **FileSystem** provider, you can use `New-Item` to create a new file or folder.</span></span> <span data-ttu-id="04a70-167">Auf den Laufwerken, die vom **Registrierungs** Anbieter unterstützt werden, können Sie verwenden, `New-Item` um einen neuen Registrierungsschlüssel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="04a70-167">In the drives that are supported by the **Registry** provider, you can use `New-Item` to create a new registry key.</span></span> <span data-ttu-id="04a70-168">Im- `Alias:` Laufwerk können Sie verwenden, `New-Item` um einen neuen Alias zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="04a70-168">In the `Alias:` drive, you can use `New-Item` to create a new alias.</span></span>

<span data-ttu-id="04a70-169">Ausführliche Informationen zu den folgenden Cmdlets erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="04a70-169">For detailed information about any of the following cmdlets, type:</span></span>

```
Get-Help <cmdlet-name> -Detailed
```

### <a name="childitem-cmdlets"></a><span data-ttu-id="04a70-170">ChildItem-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="04a70-170">ChildItem cmdlets</span></span>

- [<span data-ttu-id="04a70-171">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="04a70-171">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="content-cmdlets"></a><span data-ttu-id="04a70-172">Content-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="04a70-172">Content Cmdlets</span></span>

- [<span data-ttu-id="04a70-173">Add-Content</span><span class="sxs-lookup"><span data-stu-id="04a70-173">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="04a70-174">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="04a70-174">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="04a70-175">Get-Content</span><span class="sxs-lookup"><span data-stu-id="04a70-175">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="04a70-176">Set-Content</span><span class="sxs-lookup"><span data-stu-id="04a70-176">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="item-cmdlets"></a><span data-ttu-id="04a70-177">Item-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="04a70-177">Item Cmdlets</span></span>

- [<span data-ttu-id="04a70-178">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="04a70-178">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="04a70-179">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="04a70-179">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="04a70-180">Get-Item</span><span class="sxs-lookup"><span data-stu-id="04a70-180">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="04a70-181">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="04a70-181">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="04a70-182">Move-Item</span><span class="sxs-lookup"><span data-stu-id="04a70-182">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="04a70-183">New-Item</span><span class="sxs-lookup"><span data-stu-id="04a70-183">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="04a70-184">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="04a70-184">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="04a70-185">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="04a70-185">Rename-Item</span></span>](xref:Microsoft.PowerShell.Management.Rename-Item)
- [<span data-ttu-id="04a70-186">Set-Item</span><span class="sxs-lookup"><span data-stu-id="04a70-186">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

### <a name="itemproperty-cmdlets"></a><span data-ttu-id="04a70-187">ItemProperty-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="04a70-187">ItemProperty cmdlets</span></span>

- [<span data-ttu-id="04a70-188">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="04a70-188">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="04a70-189">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="04a70-189">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)
- [<span data-ttu-id="04a70-190">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="04a70-190">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="04a70-191">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="04a70-191">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)
- [<span data-ttu-id="04a70-192">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="04a70-192">New-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.New-ItemProperty)
- [<span data-ttu-id="04a70-193">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="04a70-193">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="04a70-194">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="04a70-194">Rename-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Rename-ItemProperty)
- [<span data-ttu-id="04a70-195">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="04a70-195">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

### <a name="location-cmdlets"></a><span data-ttu-id="04a70-196">Location-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="04a70-196">Location cmdlets</span></span>

- [<span data-ttu-id="04a70-197">Get-Location</span><span class="sxs-lookup"><span data-stu-id="04a70-197">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="04a70-198">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="04a70-198">Pop-Location</span></span>](xref:Microsoft.PowerShell.Management.Pop-Location)
- [<span data-ttu-id="04a70-199">Push-Location</span><span class="sxs-lookup"><span data-stu-id="04a70-199">Push-Location</span></span>](xref:Microsoft.PowerShell.Management.Push-Location)
- [<span data-ttu-id="04a70-200">Set-Location</span><span class="sxs-lookup"><span data-stu-id="04a70-200">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)

### <a name="path-cmdlets"></a><span data-ttu-id="04a70-201">Pfad-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="04a70-201">Path cmdlets</span></span>

- [<span data-ttu-id="04a70-202">Join-Path</span><span class="sxs-lookup"><span data-stu-id="04a70-202">Join-Path</span></span>](xref:Microsoft.PowerShell.Management.Join-Path)
- [<span data-ttu-id="04a70-203">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="04a70-203">Convert-Path</span></span>](xref:Microsoft.PowerShell.Management.Convert-Path)
- [<span data-ttu-id="04a70-204">Split-Path</span><span class="sxs-lookup"><span data-stu-id="04a70-204">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)
- [<span data-ttu-id="04a70-205">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="04a70-205">Resolve-Path</span></span>](xref:Microsoft.PowerShell.Management.Resolve-Path)
- [<span data-ttu-id="04a70-206">Test-Path</span><span class="sxs-lookup"><span data-stu-id="04a70-206">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="psdrive-cmdlets"></a><span data-ttu-id="04a70-207">PSDrive-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="04a70-207">PSDrive cmdlets</span></span>

- [<span data-ttu-id="04a70-208">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="04a70-208">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="04a70-209">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="04a70-209">New-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.New-PSDrive)
- [<span data-ttu-id="04a70-210">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="04a70-210">Remove-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Remove-PSDrive)

### <a name="psprovider-cmdlets"></a><span data-ttu-id="04a70-211">Psprovider-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="04a70-211">PSProvider Cmdlets</span></span>

- [<span data-ttu-id="04a70-212">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="04a70-212">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)

## <a name="viewing-provider-data"></a><span data-ttu-id="04a70-213">Anzeigen von Anbieter Daten</span><span class="sxs-lookup"><span data-stu-id="04a70-213">Viewing provider data</span></span>

<span data-ttu-id="04a70-214">Der Hauptvorteil eines Anbieters besteht darin, dass er seine Daten auf vertraute und konsistente Weise verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="04a70-214">The primary benefit of a provider is that it exposes its data in a familiar and consistent way.</span></span> <span data-ttu-id="04a70-215">Das Modell für die Datenpräsentation ist ein Dateisystem Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="04a70-215">The model for data presentation is a file system drive.</span></span>

<span data-ttu-id="04a70-216">Der Anbieter ermöglicht Ihnen das anzeigen, navigieren und Ändern von Elementen im Datenspeicher, als ob es sich um Daten in einem Dateisystem handelt.</span><span class="sxs-lookup"><span data-stu-id="04a70-216">The provider allows you to view, navigate, and change items in the data store as though they were data in a file system.</span></span> <span data-ttu-id="04a70-217">Der Zugriff auf den Datenspeicher erfolgt über den Namen des Laufwerks, das von ihm unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="04a70-217">The data store is accessed by the name of the drive that it supports.</span></span>

<span data-ttu-id="04a70-218">Das Laufwerk wird in der Standard Anzeige des `Get-PSProvider` Cmdlets aufgelistet, Sie können jedoch mithilfe des Cmdlets Informationen über das Anbieter Laufwerk erhalten `Get-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="04a70-218">The drive is listed in the default display of the `Get-PSProvider` cmdlet, but you can get information about the provider drive using the `Get-PSDrive` cmdlet.</span></span> <span data-ttu-id="04a70-219">Geben Sie z. b. Folgendes ein, um alle Eigenschaften des Laufwerks "function:" zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="04a70-219">For example, to get all the properties of the Function: drive, type:</span></span>

```powershell
Get-PSDrive Function | Format-List *
```

<span data-ttu-id="04a70-220">Sie können die Daten in einem Anbieter Laufwerk genau so wie auf einem Dateisystem Laufwerk anzeigen und durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="04a70-220">You can view and move through the data in a provider drive just as you would on a file system drive.</span></span>

<span data-ttu-id="04a70-221">Zum Anzeigen des Inhalts eines Anbieter Laufwerks verwenden Sie die Cmdlets Get-Item oder Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="04a70-221">To view the contents of a provider drive, use the Get-Item or Get-ChildItem cmdlets.</span></span> <span data-ttu-id="04a70-222">Geben Sie den Namen des Laufwerks gefolgt von einem Doppelpunkt (:) ein.</span><span class="sxs-lookup"><span data-stu-id="04a70-222">Type the drive name followed by a colon (:).</span></span> <span data-ttu-id="04a70-223">Wenn Sie z. b. den Inhalt des Alias:-Laufwerks anzeigen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="04a70-223">For example, to view the contents of the Alias: drive, type:</span></span>

```powershell
Get-Item alias:
```

<span data-ttu-id="04a70-224">Sie können die Daten in einem beliebigen Laufwerk von einem anderen Laufwerk anzeigen und verwalten, indem Sie den Namen des Laufwerks in den Pfad einschließen.</span><span class="sxs-lookup"><span data-stu-id="04a70-224">You can view and manage the data in any drive from another drive by including the drive name in the path.</span></span> <span data-ttu-id="04a70-225">Geben Sie beispielsweise Folgendes ein, um den Registrierungsschlüssel "HKLM\Software" auf dem Laufwerk "HKLM:" auf einem anderen Laufwerk anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="04a70-225">For example, to view the HKLM\Software registry key in the HKLM: drive from another drive, type:</span></span>

```powershell
Get-ChildItem HKLM:\SOFTWARE\
```

<span data-ttu-id="04a70-226">Um das Laufwerk zu öffnen, verwenden Sie das Cmdlet "Set-Location".</span><span class="sxs-lookup"><span data-stu-id="04a70-226">To open the drive, use the Set-Location cmdlet.</span></span> <span data-ttu-id="04a70-227">Merken Sie sich den Doppelpunkt, wenn Sie den Laufwerks Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="04a70-227">Remember the colon when you specify the drive path.</span></span> <span data-ttu-id="04a70-228">Wenn Sie z. b. ihren Speicherort in das Stammverzeichnis des Zertifikats "CERT:" ändern möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="04a70-228">For example, to change your location to the root directory of the Cert: drive, type:</span></span>

```powershell
Set-Location cert:
```

<span data-ttu-id="04a70-229">Wenn Sie den Inhalt des Zertifikats "CERT:" anzeigen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="04a70-229">Then, to view the contents of the Cert: drive, type:</span></span>

```powershell
Get-ChildItem
```

## <a name="moving-through-hierarchical-data"></a><span data-ttu-id="04a70-230">Verschieben von hierarchischen Daten</span><span class="sxs-lookup"><span data-stu-id="04a70-230">Moving through hierarchical data</span></span>

<span data-ttu-id="04a70-231">Sie können ein Anbieter Laufwerk wie ein Festplattenlaufwerk durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="04a70-231">You can move through a provider drive just as you would a hard disk drive.</span></span>
<span data-ttu-id="04a70-232">Wenn die Daten in einer Hierarchie von Elementen innerhalb von Elementen angeordnet sind, verwenden Sie einen umgekehrten Schrägstrich ( `\` ), um ein untergeordnetes Element anzugeben.</span><span class="sxs-lookup"><span data-stu-id="04a70-232">If the data is arranged in a hierarchy of items within items, use a backslash (`\`) to indicate a child item.</span></span> <span data-ttu-id="04a70-233">Verwenden Sie das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="04a70-233">Use the following format:</span></span>

```
drive:\location\child-location\...
```

<span data-ttu-id="04a70-234">Wenn Sie beispielsweise ihren Speicherort in den Registrierungsschlüssel "HKLM\Software" ändern möchten, geben Sie einen Set-Location Befehl ein, z. b.:</span><span class="sxs-lookup"><span data-stu-id="04a70-234">For example, to change your location to the HKLM\Software registry key, type a Set-Location command, such as:</span></span>

```powershell
Set-Location HKLM:\SOFTWARE\
```

<span data-ttu-id="04a70-235">Wenn ein beliebiges Element im voll qualifizierten Namen Leerzeichen enthält, müssen Sie den Namen in doppelte Anführungszeichen ( `"` ) einschließen.</span><span class="sxs-lookup"><span data-stu-id="04a70-235">If any element in the fully qualified name includes spaces, you must enclose the name in double-quotation marks (`"`).</span></span> <span data-ttu-id="04a70-236">Das folgende Beispiel zeigt einen voll qualifizierten Pfad, der Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="04a70-236">The following example shows a fully qualified path that includes spaces.</span></span>

```
"C:\Program Files\Internet Explorer\iexplore.exe"
```

<span data-ttu-id="04a70-237">Sie können auch relative Verweise auf Speicherorte verwenden.</span><span class="sxs-lookup"><span data-stu-id="04a70-237">You can also use relative references to locations.</span></span> <span data-ttu-id="04a70-238">Ein Punkt ( `.` ) stellt den aktuellen Speicherort dar.</span><span class="sxs-lookup"><span data-stu-id="04a70-238">A dot (`.`) represents the current location.</span></span> <span data-ttu-id="04a70-239">Wenn Sie z. b. im `HKLM:\Software\Microsoft` Registrierungsschlüssel sind und die Registrierungs Unterschlüssel im Schlüssel auflisten möchten `HKLM:\Software\Microsoft\PowerShell` , geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="04a70-239">For example, if you are in the `HKLM:\Software\Microsoft` registry key, and you want to list the registry subkeys in the `HKLM:\Software\Microsoft\PowerShell` key, type the following command:</span></span>

```powershell
Get-ChildItem .\PowerShell
```

<span data-ttu-id="04a70-240">Außerdem verweist Double-Dots ( `..` ) direkt oberhalb ihres aktuellen Speicher Orts auf das Verzeichnis oder den Container.</span><span class="sxs-lookup"><span data-stu-id="04a70-240">Also, double-dots (`..`) refers to the directory or container directly above your current location.</span></span> <span data-ttu-id="04a70-241">Sie können doppelte Punkte () verwenden `..` , um durch eine Anbieter Hierarchie zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="04a70-241">You can use double-dots (`..`) to navigate through a provider hierarchy.</span></span>

```
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters\> cd ..\..\LanmanWorkstation\Parameters
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters>
```

## <a name="provider-home"></a><span data-ttu-id="04a70-242">Startseite des Anbieters</span><span class="sxs-lookup"><span data-stu-id="04a70-242">Provider Home</span></span>

<span data-ttu-id="04a70-243">Anbieter verfügen auch über einen **eigenen** Standort.</span><span class="sxs-lookup"><span data-stu-id="04a70-243">Providers also have a **Home** location.</span></span>  <span data-ttu-id="04a70-244">Dieser Speicherort wird von allen unter `PSDrives` stützt, die vom Anbieter unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="04a70-244">This location is shared by all `PSDrives` backed by the provider.</span></span> <span data-ttu-id="04a70-245">Sie kann abgerufen werden, indem Sie die **Home** -Eigenschaft des Anbieters anzeigen.</span><span class="sxs-lookup"><span data-stu-id="04a70-245">It can be retrieved by viewing the **Home** property of the provider.</span></span>

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

<span data-ttu-id="04a70-246">Der **File System** -Anbieter ist der einzige Anbieter, der über einen Standardwert für **Home** verfügt.</span><span class="sxs-lookup"><span data-stu-id="04a70-246">The **FileSystem** provider is the only provider that has a default value for **Home**.</span></span> <span data-ttu-id="04a70-247">Dies ist der gleiche Wert wie `$Home` .</span><span class="sxs-lookup"><span data-stu-id="04a70-247">It's the same value as `$Home`.</span></span> <span data-ttu-id="04a70-248">Weitere Informationen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="04a70-248">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="04a70-249">Mithilfe der-Eigenschaft können Sie das **Basisverzeichnis für** einen Anbieter für die aktuelle Sitzung festlegen.</span><span class="sxs-lookup"><span data-stu-id="04a70-249">You can set the **Home** directory for a provider, for the current session, using its property.</span></span>

```powershell
(Get-PSProvider FileSystem).Home = "C:\"
```

<span data-ttu-id="04a70-250">Das `~` -Zeichen kann verwendet werden, um das Basisverzeichnis des Anbieters darzustellen.</span><span class="sxs-lookup"><span data-stu-id="04a70-250">The `~` character can be used to represent the provider's home directory.</span></span>
<span data-ttu-id="04a70-251">Wenn für den Anbieter kein **Start** Speicherort festgelegt ist, wird ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="04a70-251">If the provider doesn't have a **Home** location set, you see an error.</span></span>

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

## <a name="finding-dynamic-parameters"></a><span data-ttu-id="04a70-252">Suchen von dynamischen Parametern</span><span class="sxs-lookup"><span data-stu-id="04a70-252">Finding dynamic parameters</span></span>

<span data-ttu-id="04a70-253">Dynamische Parameter sind Cmdlet-Parameter, die einem Cmdlet von einem Anbieter hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="04a70-253">Dynamic parameters are cmdlet parameters that are added to a cmdlet by a provider.</span></span> <span data-ttu-id="04a70-254">Diese Parameter sind nur verfügbar, wenn das Cmdlet mit dem Anbieter verwendet wird, der Sie hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="04a70-254">These parameters are available only when the cmdlet is used with the provider that added them.</span></span>

<span data-ttu-id="04a70-255">Beispielsweise fügt das `Cert:` Laufwerk dem-Cmdlet und dem-Cmdlet den **codeSigningCert** -Parameter hinzu `Get-Item` `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="04a70-255">For example, the `Cert:` drive adds the **CodeSigningCert** parameter to the `Get-Item` and `Get-ChildItem` cmdlets.</span></span> <span data-ttu-id="04a70-256">Sie können diesen Parameter nur verwenden, wenn Sie `Get-Item` oder `Get-ChildItem` auf dem `Cert:` Laufwerk verwenden.</span><span class="sxs-lookup"><span data-stu-id="04a70-256">You can use this parameter only when you use `Get-Item` or `Get-ChildItem` in the `Cert:` drive.</span></span>

<span data-ttu-id="04a70-257">Eine Liste der dynamischen Parameter, die von einem Anbieter unterstützt werden, finden Sie in der Hilfedatei für den Anbieter.</span><span class="sxs-lookup"><span data-stu-id="04a70-257">For a list of the dynamic parameters that a provider supports, see the Help file for the provider.</span></span> <span data-ttu-id="04a70-258">Typ:</span><span class="sxs-lookup"><span data-stu-id="04a70-258">Type:</span></span>

```
Get-Help <provider-name>
```

<span data-ttu-id="04a70-259">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="04a70-259">For example:</span></span>

```powershell
Get-Help certificate
```

## <a name="learning-about-providers"></a><span data-ttu-id="04a70-260">Kennenlernen von Anbietern</span><span class="sxs-lookup"><span data-stu-id="04a70-260">Learning about providers</span></span>

<span data-ttu-id="04a70-261">Obwohl alle Anbieter Daten auf den Laufwerken angezeigt werden und Sie die gleichen Methoden verwenden, um Sie zu durchlaufen, wird die Ähnlichkeit dort angehalten.</span><span class="sxs-lookup"><span data-stu-id="04a70-261">Although all provider data appears in drives and you use the same methods to move through them, the similarity stops there.</span></span> <span data-ttu-id="04a70-262">Die Datenspeicher, die der Anbieter verfügbar macht, können so unterschiedlich sein wie Active Directory Standorte und Microsoft Exchange Server-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="04a70-262">The data stores that the provider exposes can be as varied as Active Directory locations and Microsoft Exchange Server mailboxes.</span></span>

<span data-ttu-id="04a70-263">Informationen zu einzelnen PowerShell-Anbietern erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="04a70-263">For information about individual PowerShell providers, type:</span></span>

```
Get-Help <ProviderName>
```

<span data-ttu-id="04a70-264">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="04a70-264">For example:</span></span>

```powershell
Get-Help registry
```

<span data-ttu-id="04a70-265">Eine Liste der Hilfe Themen zu den Anbietern erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="04a70-265">For a list of Help topics about the providers, type:</span></span>

```powershell
Get-Help * -Category Provider
```

## <a name="see-also"></a><span data-ttu-id="04a70-266">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04a70-266">See also</span></span>

[<span data-ttu-id="04a70-267">about_Locations</span><span class="sxs-lookup"><span data-stu-id="04a70-267">about_Locations</span></span>](about_Locations.md)

[<span data-ttu-id="04a70-268">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="04a70-268">about_Path_Syntax</span></span>](about_Path_Syntax.md)

