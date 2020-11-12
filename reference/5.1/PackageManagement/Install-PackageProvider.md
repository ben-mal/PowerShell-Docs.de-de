---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-packageprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-PackageProvider
ms.openlocfilehash: eb8cedd8275e9d8ea092a508c542464b8021878e
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524424"
---
# <span data-ttu-id="58112-103">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="58112-103">Install-PackageProvider</span></span>

## <span data-ttu-id="58112-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="58112-104">SYNOPSIS</span></span>
<span data-ttu-id="58112-105">Installiert einen oder mehrere Paketverwaltung Paketanbieter.</span><span class="sxs-lookup"><span data-stu-id="58112-105">Installs one or more Package Management package providers.</span></span>

## <span data-ttu-id="58112-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="58112-106">SYNTAX</span></span>

### <span data-ttu-id="58112-107">Packagebysearch (Standard)</span><span class="sxs-lookup"><span data-stu-id="58112-107">PackageBySearch (Default)</span></span>

```
Install-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Credential <PSCredential>] [-Scope <String>] [-Source <String[]>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="58112-108">Packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="58112-108">PackageByInputObject</span></span>

```
Install-PackageProvider [-Scope <String>] [-InputObject] <SoftwareIdentity[]> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="58112-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="58112-109">DESCRIPTION</span></span>

<span data-ttu-id="58112-110">Mit dem- `Install-PackageProvider` Cmdlet werden übereinstimmende Paketverwaltung Anbieter installiert, die in mit **PowerShellGet** registrierten Paketquellen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="58112-110">The `Install-PackageProvider` cmdlet installs matching Package Management providers that are available in package sources registered with **PowerShellGet**.</span></span> <span data-ttu-id="58112-111">Standardmäßig schließt dies Module ein, die im Windows-PowerShell-Katalog mit dem Tag **packagemanagement** verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="58112-111">By default, this includes modules available in the Windows PowerShell Gallery with the **PackageManagement** tag.</span></span> <span data-ttu-id="58112-112">Der **PowerShellGet** -Paketverwaltung-Anbieter wird für die Suche nach Anbietern in diesen Depots verwendet.</span><span class="sxs-lookup"><span data-stu-id="58112-112">The **PowerShellGet** Package Management provider is used for finding providers in these repositories.</span></span>

<span data-ttu-id="58112-113">Mit diesem Cmdlet werden auch übereinstimmende Paketverwaltung Anbieter installiert, die mit der Paketverwaltung Bootstrapping-Anwendung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="58112-113">This cmdlet also installs matching Package Management providers that are available using the Package Management bootstrapping application.</span></span>

<span data-ttu-id="58112-114">Dieses Cmdlet installiert auch entsprechende Paketverwaltung Anbieter, die im Paketverwaltung Azure-BLOB-Speicher verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="58112-114">This cmdlet also installs matching Package Management providers that are available in the Package Management Azure Blob store.</span></span> <span data-ttu-id="58112-115">Verwenden Sie den Boots Trapper-Anbieter, um diese zu suchen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="58112-115">Use the bootstrapper provider to find and install them.</span></span>

<span data-ttu-id="58112-116">Um das erste Mal auszuführen, erfordert packagemanagement eine Internetverbindung zum Herunterladen des nuget-Paket Anbieters.</span><span class="sxs-lookup"><span data-stu-id="58112-116">In order to execute the first time, PackageManagement requires an internet connection to download the NuGet package provider.</span></span> <span data-ttu-id="58112-117">Wenn der Computer jedoch nicht über eine Internetverbindung verfügt und Sie den nuget-oder PowerShellGet-Anbieter verwenden müssen, können Sie ihn auf einem anderen Computer herunterladen und auf den Zielcomputer kopieren.</span><span class="sxs-lookup"><span data-stu-id="58112-117">However, if your computer does not have an internet connection and you need to use the NuGet or PowerShellGet provider, you can download them on another computer and copy them to your target computer.</span></span> <span data-ttu-id="58112-118">Führen Sie hierzu die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="58112-118">Use the following steps to do this:</span></span>

1. <span data-ttu-id="58112-119">Führen `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` Sie aus, um den Anbieter von einem Computer mit Internetverbindung zu installieren.</span><span class="sxs-lookup"><span data-stu-id="58112-119">Run `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` to install the provider from a computer with an internet connection.</span></span>
1. <span data-ttu-id="58112-120">Nach der Installation können Sie den Anbieter finden, der in `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\<ProviderName>\<ProviderVersion>` oder installiert ist `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\<ProviderName>\<ProviderVersion>` .</span><span class="sxs-lookup"><span data-stu-id="58112-120">After the install, you can find the provider installed in `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\<ProviderName>\<ProviderVersion>` or `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\<ProviderName>\<ProviderVersion>`.</span></span>
1. <span data-ttu-id="58112-121">Platzieren `<ProviderName>` Sie den Ordner (in diesem Fall den nuget-Ordner) am entsprechenden Speicherort auf dem Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="58112-121">Place the `<ProviderName>` folder, which in this case is the NuGet folder, in the corresponding location on your target computer.</span></span> <span data-ttu-id="58112-122">Wenn es sich bei dem Zielcomputer um einen Nano-Server handelt, müssen Sie `Install-PackageProvider` von Nano Server ausführen, um die richtigen nuget-Binärdateien herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="58112-122">If your target computer is a Nano server, you need to run `Install-PackageProvider` from Nano Server to download the correct NuGet binaries.</span></span>
1. <span data-ttu-id="58112-123">Starten Sie PowerShell neu, um den Paketanbieter automatisch zu laden.</span><span class="sxs-lookup"><span data-stu-id="58112-123">Restart PowerShell to auto-load the package provider.</span></span> <span data-ttu-id="58112-124">Alternativ können Sie ausführen, `Get-PackageProvider -ListAvailable` um alle Paketanbieter aufzulisten, die auf dem Computer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="58112-124">Alternatively, run `Get-PackageProvider -ListAvailable` to list all the package providers available on the computer.</span></span>
   <span data-ttu-id="58112-125">Verwenden `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` Sie dann, um den Anbieter in die aktuelle Windows PowerShell-Sitzung zu importieren.</span><span class="sxs-lookup"><span data-stu-id="58112-125">Then use `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` to import the provider to the current Windows PowerShell session.</span></span>

## <span data-ttu-id="58112-126">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="58112-126">EXAMPLES</span></span>

### <span data-ttu-id="58112-127">Beispiel 1: Installieren eines Paket Anbieters aus dem PowerShell-Katalog</span><span class="sxs-lookup"><span data-stu-id="58112-127">Example 1: Install a package provider from the PowerShell Gallery</span></span>

<span data-ttu-id="58112-128">Mit diesem Befehl wird der Anbieter des gistprovider-Pakets aus dem PowerShell-Katalog installiert.</span><span class="sxs-lookup"><span data-stu-id="58112-128">This command installs the GistProvider package provider from the PowerShell Gallery.</span></span>

```powershell
Install-PackageProvider -Name "GistProvider" -Verbose
```

### <span data-ttu-id="58112-129">Beispiel 2: Installieren einer bestimmten Version eines Paket Anbieters</span><span class="sxs-lookup"><span data-stu-id="58112-129">Example 2: Install a specified version of a package provider</span></span>

<span data-ttu-id="58112-130">In diesem Beispiel wird eine angegebene Version des nuget-Paket Anbieters installiert.</span><span class="sxs-lookup"><span data-stu-id="58112-130">This example installs a specified version of the NuGet package provider.</span></span>

<span data-ttu-id="58112-131">Der erste Befehl sucht alle Versionen des Paket Anbieters namens nuget.</span><span class="sxs-lookup"><span data-stu-id="58112-131">The first command finds all versions of the package provider named NuGet.</span></span>
<span data-ttu-id="58112-132">Mit dem zweiten Befehl wird eine angegebene Version des nuget-Paket Anbieters installiert.</span><span class="sxs-lookup"><span data-stu-id="58112-132">The second command installs a specified version of the NuGet package provider.</span></span>

```powershell
Find-PackageProvider -Name "NuGet" -AllVersions
Install-PackageProvider -Name "NuGet" -RequiredVersion "2.8.5.216" -Force
```

### <span data-ttu-id="58112-133">Beispiel 3: Suchen eines Anbieters und Installieren des Anbieters</span><span class="sxs-lookup"><span data-stu-id="58112-133">Example 3: Find a provider and install it</span></span>

<span data-ttu-id="58112-134">In diesem Beispiel werden `Find-PackageProvider` und die Pipeline verwendet, um nach dem GIST-Anbieter zu suchen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="58112-134">This example uses `Find-PackageProvider` and the pipeline to search for the Gist provider and install it.</span></span>

```powershell
Find-PackageProvider -Name "GistProvider" | Install-PackageProvider -Verbose
```

### <span data-ttu-id="58112-135">Beispiel 4: Installieren eines Anbieters im Modul Ordner des aktuellen Benutzers</span><span class="sxs-lookup"><span data-stu-id="58112-135">Example 4: Install a provider to the current user's module folder</span></span>

<span data-ttu-id="58112-136">Mit diesem Befehl wird ein Paketanbieter auf installiert, `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies` sodass er nur vom aktuellen Benutzer verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="58112-136">This command installs a package provider to `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies` so that only the current user can use it.</span></span>

```powershell
Install-PackageProvider -Name GistProvider -Verbose -Scope CurrentUser
```

## <span data-ttu-id="58112-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="58112-137">PARAMETERS</span></span>

### <span data-ttu-id="58112-138">-Allversions</span><span class="sxs-lookup"><span data-stu-id="58112-138">-AllVersions</span></span>

<span data-ttu-id="58112-139">Gibt an, dass dieses Cmdlet alle verfügbaren Versionen des Paket Anbieters installiert.</span><span class="sxs-lookup"><span data-stu-id="58112-139">Indicates that this cmdlet installs all available versions of the package provider.</span></span> <span data-ttu-id="58112-140">Standardmäßig wird `Install-PackageProvider` nur die höchste verfügbare Version zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="58112-140">By default, `Install-PackageProvider` only returns the highest available version.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58112-141">-Credential</span><span class="sxs-lookup"><span data-stu-id="58112-141">-Credential</span></span>

<span data-ttu-id="58112-142">Gibt ein Benutzerkonto an, das über die Berechtigung zum Installieren von Paket Anbietern verfügt.</span><span class="sxs-lookup"><span data-stu-id="58112-142">Specifies a user account that has permission to install package providers.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58112-143">-Force</span><span class="sxs-lookup"><span data-stu-id="58112-143">-Force</span></span>

<span data-ttu-id="58112-144">Gibt an, dass dieses Cmdlet alle Aktionen mit diesem Cmdlet erzwingt, die erzwungen werden können.</span><span class="sxs-lookup"><span data-stu-id="58112-144">Indicates that this cmdlet forces all actions with this cmdlet that can be forced.</span></span> <span data-ttu-id="58112-145">Dies bedeutet derzeit, dass der **Force** -Parameter mit dem Parameter " **forcebootstrap** " identisch ist.</span><span class="sxs-lookup"><span data-stu-id="58112-145">Currently, this means the **Force** parameter acts the same as the **ForceBootstrap** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58112-146">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="58112-146">-ForceBootstrap</span></span>

<span data-ttu-id="58112-147">Gibt an, dass dieses Cmdlet den Paketanbieter automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="58112-147">Indicates that this cmdlet automatically installs the package provider.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58112-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="58112-148">-InputObject</span></span>

<span data-ttu-id="58112-149">Gibt ein **softwareidentity** -Objekt an.</span><span class="sxs-lookup"><span data-stu-id="58112-149">Specifies a **SoftwareIdentity** object.</span></span> <span data-ttu-id="58112-150">Verwenden Sie das- `Find-PackageProvider` Cmdlet, um ein **softwareidentity** -Objekt zu erhalten, das über die Pipeline an `Install-PackageProvider`</span><span class="sxs-lookup"><span data-stu-id="58112-150">Use the `Find-PackageProvider` cmdlet to obtain a **SoftwareIdentity** object to pipe into `Install-PackageProvider`.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.SoftwareIdentity[]
Parameter Sets: PackageByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="58112-151">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="58112-151">-MaximumVersion</span></span>

<span data-ttu-id="58112-152">Gibt die maximal zulässige Version des Paket Anbieters an, den Sie installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="58112-152">Specifies the maximum allowed version of the package provider that you want to install.</span></span> <span data-ttu-id="58112-153">Wenn Sie diesen Parameter nicht hinzufügen, wird `Install-PackageProvider` von die höchste verfügbare Version des Anbieters installiert.</span><span class="sxs-lookup"><span data-stu-id="58112-153">If you do not add this parameter, `Install-PackageProvider` installs the highest available version of the provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58112-154">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="58112-154">-MinimumVersion</span></span>

<span data-ttu-id="58112-155">Gibt die mindestens zulässige Version des Paket Anbieters an, den Sie installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="58112-155">Specifies the minimum allowed version of the package provider that you want to install.</span></span> <span data-ttu-id="58112-156">Wenn Sie diesen Parameter nicht hinzufügen, `Install-PackageProvider` installiert die höchste verfügbare Version des Pakets, das auch alle Anforderungen erfüllt, die durch den *MaximumVersion* -Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="58112-156">If you do not add this parameter, `Install-PackageProvider` installs the highest available version of the package that also satisfies any requirement specified by the *MaximumVersion* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58112-157">-Name</span><span class="sxs-lookup"><span data-stu-id="58112-157">-Name</span></span>

<span data-ttu-id="58112-158">Gibt einen oder mehrere Paketanbieter-Modulnamen an.</span><span class="sxs-lookup"><span data-stu-id="58112-158">Specifies one or more package provider module names.</span></span> <span data-ttu-id="58112-159">Trennen Sie mehrere Paketnamen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="58112-159">Separate multiple package names with commas.</span></span>
<span data-ttu-id="58112-160">Platzhalterzeichen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="58112-160">Wildcard characters are not supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58112-161">-Proxy</span><span class="sxs-lookup"><span data-stu-id="58112-161">-Proxy</span></span>

<span data-ttu-id="58112-162">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="58112-162">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58112-163">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="58112-163">-ProxyCredential</span></span>

<span data-ttu-id="58112-164">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="58112-164">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58112-165">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="58112-165">-RequiredVersion</span></span>

<span data-ttu-id="58112-166">Gibt die exakt zulässige Version des Paket Anbieters an, den Sie installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="58112-166">Specifies the exact allowed version of the package provider that you want to install.</span></span> <span data-ttu-id="58112-167">Wenn Sie diesen Parameter nicht hinzufügen, wird `Install-PackageProvider` von die höchste verfügbare Version des Anbieters installiert, die auch eine beliebige maximale Version erfüllt, die durch den **MaximumVersion** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="58112-167">If you do not add this parameter, `Install-PackageProvider` installs the highest available version of the provider that also satisfies any maximum version specified by the **MaximumVersion** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58112-168">-Bereich</span><span class="sxs-lookup"><span data-stu-id="58112-168">-Scope</span></span>

<span data-ttu-id="58112-169">Gibt den Installationsbereich des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="58112-169">Specifies the installation scope of the provider.</span></span> <span data-ttu-id="58112-170">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="58112-170">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="58112-171">**ALLUSERS** : installiert Anbieter an einem Speicherort, auf den alle Benutzer des Computers zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="58112-171">**AllUsers** - installs providers in a location that is accessible to all users of the computer.</span></span>
  <span data-ttu-id="58112-172">Standardmäßig ist dies **$ENV:P rogramfiles\packagemanagement\providerassemblies.**</span><span class="sxs-lookup"><span data-stu-id="58112-172">By default, this is **$env:ProgramFiles\PackageManagement\ProviderAssemblies.**</span></span>

- <span data-ttu-id="58112-173">**CurrentUser** : installiert Anbieter an einem Speicherort, an den Sie nur für den aktuellen Benutzer zugänglich sind.</span><span class="sxs-lookup"><span data-stu-id="58112-173">**CurrentUser** - installs providers in a location where they are only accessible to the current user.</span></span> <span data-ttu-id="58112-174">Standardmäßig ist dies **$ENV: localappdata\packagemanagement\providerassemblies.**</span><span class="sxs-lookup"><span data-stu-id="58112-174">By default, this is **$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies.**</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58112-175">-Source</span><span class="sxs-lookup"><span data-stu-id="58112-175">-Source</span></span>

<span data-ttu-id="58112-176">Gibt mindestens eine Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="58112-176">Specifies one or more package sources.</span></span> <span data-ttu-id="58112-177">Verwenden Sie das `Get-PackageSource` Cmdlet, um eine Liste der verfügbaren Paketquellen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="58112-177">Use the `Get-PackageSource` cmdlet to get a list of available package sources.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="58112-178">-Confirm</span><span class="sxs-lookup"><span data-stu-id="58112-178">-Confirm</span></span>

<span data-ttu-id="58112-179">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="58112-179">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58112-180">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="58112-180">-WhatIf</span></span>

<span data-ttu-id="58112-181">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="58112-181">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="58112-182">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="58112-182">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="58112-183">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="58112-183">CommonParameters</span></span>

<span data-ttu-id="58112-184">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="58112-184">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="58112-185">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="58112-185">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="58112-186">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="58112-186">INPUTS</span></span>

### <span data-ttu-id="58112-187">Microsoft. packagemanagement. Packaging. softwareidentity</span><span class="sxs-lookup"><span data-stu-id="58112-187">Microsoft.PackageManagement.Packaging.SoftwareIdentity</span></span>

<span data-ttu-id="58112-188">Sie können ein **softwareidentity** -Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="58112-188">You can pipe a **SoftwareIdentity** object to this cmdlet.</span></span> <span data-ttu-id="58112-189">Verwenden `Find-PackageProvider` Sie, um ein **softwareidentity** -Objekt zu erhalten, das an weitergeleitet werden kann `Install-PackageProvider` .</span><span class="sxs-lookup"><span data-stu-id="58112-189">Use `Find-PackageProvider` to get a **SoftwareIdentity** object that can be piped into `Install-PackageProvider`.</span></span>

## <span data-ttu-id="58112-190">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="58112-190">OUTPUTS</span></span>

## <span data-ttu-id="58112-191">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="58112-191">NOTES</span></span>

## <span data-ttu-id="58112-192">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="58112-192">RELATED LINKS</span></span>

[<span data-ttu-id="58112-193">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="58112-193">Find-PackageProvider</span></span>](Find-PackageProvider.md)

[<span data-ttu-id="58112-194">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="58112-194">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="58112-195">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="58112-195">Import-PackageProvider</span></span>](Import-PackageProvider.md)
