---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 05/22/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-package?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Package
ms.openlocfilehash: bc6ba83a6f0d585e166b1bdc419c8b9c7148e47c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892881"
---
# <span data-ttu-id="341b1-103">Get-Package</span><span class="sxs-lookup"><span data-stu-id="341b1-103">Get-Package</span></span>

## <span data-ttu-id="341b1-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="341b1-104">SYNOPSIS</span></span>
<span data-ttu-id="341b1-105">Gibt eine Liste aller Softwarepakete zurück, die mit **packagemanagement** installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="341b1-105">Returns a list of all software packages that were installed with **PackageManagement**.</span></span>

## <span data-ttu-id="341b1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="341b1-106">SYNTAX</span></span>

### <span data-ttu-id="341b1-107">MSI-Datei</span><span class="sxs-lookup"><span data-stu-id="341b1-107">msi</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-AdditionalArguments <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="341b1-108">Programs</span><span class="sxs-lookup"><span data-stu-id="341b1-108">Programs</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-IncludeWindowsInstaller] [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="341b1-109">NuGet</span><span class="sxs-lookup"><span data-stu-id="341b1-109">NuGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="341b1-110">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="341b1-110">PowerShellGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Scope <String>] [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions]
 [<CommonParameters>]
```

## <span data-ttu-id="341b1-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="341b1-111">DESCRIPTION</span></span>

<span data-ttu-id="341b1-112">Mit dem- `Get-Package` Cmdlet wird eine Liste aller Softwarepakete auf dem lokalen Computer zurückgegeben, die mit **packagemanagement** installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="341b1-112">The `Get-Package` cmdlet returns a list of all software packages on the local computer that were installed with **PackageManagement**.</span></span> <span data-ttu-id="341b1-113">Sie können `Get-Package` auf Remote Computern ausführen, indem Sie Sie als Teil eines- `Invoke-Command` oder- `Enter-PSSession` Befehls oder-Skripts ausführen.</span><span class="sxs-lookup"><span data-stu-id="341b1-113">You can run `Get-Package` on remote computers by running it as part of an `Invoke-Command` or `Enter-PSSession` command or script.</span></span>

## <span data-ttu-id="341b1-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="341b1-114">EXAMPLES</span></span>

### <span data-ttu-id="341b1-115">Beispiel 1: alle installierten Pakete erhalten</span><span class="sxs-lookup"><span data-stu-id="341b1-115">Example 1: Get all installed packages</span></span>

<span data-ttu-id="341b1-116">Mit dem- `Get-Package` Cmdlet werden alle Pakete abgerufen, die auf dem lokalen Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="341b1-116">The `Get-Package` cmdlet gets all packages that are installed on the local computer.</span></span>

```powershell
Get-Package
```

```Output
Name           Version      Source                                     ProviderName
----           -------      ------                                     ------------
posh-git       0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
```

### <span data-ttu-id="341b1-117">Beispiel 2: Get-Pakete, die auf einem Remote Computer installiert sind</span><span class="sxs-lookup"><span data-stu-id="341b1-117">Example 2: Get packages that are installed on a remote computer</span></span>

<span data-ttu-id="341b1-118">Mit diesem Befehl wird eine Liste der Pakete abgerufen, die von **packagemanagement** auf einem Remote Computer installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="341b1-118">This command gets a list of packages that were installed by **PackageManagement** on a remote computer.</span></span> <span data-ttu-id="341b1-119">Mit diesem Befehl werden Sie aufgefordert, das Kennwort des angegebenen Benutzers anzugeben.</span><span class="sxs-lookup"><span data-stu-id="341b1-119">This command prompts you to provide the specified user's password.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -Credential CONTOSO\TestUser -ScriptBlock {Get-Package}
```

<span data-ttu-id="341b1-120">`Invoke-Command` verwendet den **Computername** -Parameter, um einen Remote Computer anzugeben, **Server01**.</span><span class="sxs-lookup"><span data-stu-id="341b1-120">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer, **Server01**.</span></span> <span data-ttu-id="341b1-121">Der **Credential** -Parameter gibt eine Domäne und einen Benutzernamen mit Berechtigungen zum Ausführen von Befehlen auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="341b1-121">The **Credential** parameter specifies a domain and user name with permissions to run commands on the computer.</span></span> <span data-ttu-id="341b1-122">Der **ScriptBlock** -Parameter führt das `Get-Package` Cmdlet auf dem Remote Computer aus.</span><span class="sxs-lookup"><span data-stu-id="341b1-122">The **ScriptBlock** parameter runs the `Get-Package` cmdlet on the remote computer.</span></span>

### <span data-ttu-id="341b1-123">Beispiel 3: Paket für einen angegebenen Anbieter erhalten</span><span class="sxs-lookup"><span data-stu-id="341b1-123">Example 3: Get packages for a specified provider</span></span>

<span data-ttu-id="341b1-124">Mit diesem Befehl werden die auf dem lokalen Computer installierten Softwarepakete von einem bestimmten Anbieter abgerufen.</span><span class="sxs-lookup"><span data-stu-id="341b1-124">This command gets software packages installed on the local computer from a specific provider.</span></span>

```powershell
Get-Package -ProviderName PowerShellGet -AllVersions
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.2.2        https://www.powershellgallery.com/api/v2   PowerShellGet
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
posh-git              0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
PowerShellGet         2.0.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

<span data-ttu-id="341b1-125">`Get-Package` verwendet den **providerName** -Parameter, um einen bestimmten Anbieter, **PowerShellGet**, anzugeben.</span><span class="sxs-lookup"><span data-stu-id="341b1-125">`Get-Package` uses the **ProviderName** parameter to specify a specific provider, **PowerShellGet**.</span></span>
<span data-ttu-id="341b1-126">Mit dem Parameter **alle Versionen** wird jede installierte Version angezeigt.</span><span class="sxs-lookup"><span data-stu-id="341b1-126">The **All-Versions** parameter displays each version that is installed.</span></span>

### <span data-ttu-id="341b1-127">Beispiel 4: beziehen einer exakten Version eines bestimmten Pakets</span><span class="sxs-lookup"><span data-stu-id="341b1-127">Example 4: Get an exact version of a specific package</span></span>

<span data-ttu-id="341b1-128">Mit diesem Befehl wird eine bestimmte Version eines installierten Pakets abgerufen.</span><span class="sxs-lookup"><span data-stu-id="341b1-128">This command gets a specific version of an installed package.</span></span> <span data-ttu-id="341b1-129">Es können mehr als eine Version eines Pakets installiert werden.</span><span class="sxs-lookup"><span data-stu-id="341b1-129">More than one version of a package can be installed.</span></span>

```powershell
Get-Package -Name PackageManagement -ProviderName PowerShellGet -RequiredVersion 1.3.1
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

<span data-ttu-id="341b1-130">`Get-Package` verwendet den **Name** -Parameter, um den Paketnamen, **packagemanagement**, anzugeben.</span><span class="sxs-lookup"><span data-stu-id="341b1-130">`Get-Package` uses **Name** parameter to specify the package name, **PackageManagement**.</span></span> <span data-ttu-id="341b1-131">Der **providerName** -Parameter gibt den Anbieter **PowerShellGet** an.</span><span class="sxs-lookup"><span data-stu-id="341b1-131">The **ProviderName** parameter specifies the provider, **PowerShellGet**.</span></span> <span data-ttu-id="341b1-132">Der **erforderliche-Version-** Parameter gibt eine installierte Version an.</span><span class="sxs-lookup"><span data-stu-id="341b1-132">The **Required-Version** parameter specifies an installed version.</span></span>

### <span data-ttu-id="341b1-133">Beispiel 5: Deinstallieren eines Pakets</span><span class="sxs-lookup"><span data-stu-id="341b1-133">Example 5: Uninstall a package</span></span>

<span data-ttu-id="341b1-134">In diesem Beispiel werden Paketinformationen abgerufen und dann das Paket deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="341b1-134">This example gets package information and then uninstalls the package.</span></span>

```powershell
Get-Package -Name posh-git -RequiredVersion 0.7.3 | Uninstall-Package
```

<span data-ttu-id="341b1-135">`Get-Package` verwendet den **Name** -Parameter zum Angeben des Paket namens **Posh-git**.</span><span class="sxs-lookup"><span data-stu-id="341b1-135">`Get-Package` uses the **Name** parameter to specify the package name, **posh-git**.</span></span> <span data-ttu-id="341b1-136">Der Parameter "Requirements **dversion** " ist eine bestimmte Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="341b1-136">The **RequiredVersion** parameter is a specific version of the package.</span></span> <span data-ttu-id="341b1-137">Das Objekt wird über die Pipeline an das `Uninstall-Package` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="341b1-137">The object is sent down the pipeline to the `Uninstall-Package` cmdlet.</span></span> <span data-ttu-id="341b1-138">`Uninstall-Package` entfernt das Paket.</span><span class="sxs-lookup"><span data-stu-id="341b1-138">`Uninstall-Package` removes the package.</span></span>

## <span data-ttu-id="341b1-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="341b1-139">PARAMETERS</span></span>

### <span data-ttu-id="341b1-140">-Allowclobber</span><span class="sxs-lookup"><span data-stu-id="341b1-140">-AllowClobber</span></span>

<span data-ttu-id="341b1-141">Überschreibt Warnmeldungen zu Konflikten mit vorhandenen Befehlen.</span><span class="sxs-lookup"><span data-stu-id="341b1-141">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="341b1-142">Überschreibt vorhandene Befehle mit demselben Namen wie Befehle, die von einem Modul installiert werden.</span><span class="sxs-lookup"><span data-stu-id="341b1-142">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-143">-Allowprereleaseversions</span><span class="sxs-lookup"><span data-stu-id="341b1-143">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="341b1-144">Schließt Pakete ein, die in den Ergebnissen als Vorabversion gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="341b1-144">Includes packages marked as a prerelease in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-145">-Allversions</span><span class="sxs-lookup"><span data-stu-id="341b1-145">-AllVersions</span></span>

<span data-ttu-id="341b1-146">Gibt an, dass `Get-Package` alle verfügbaren Versionen des Pakets zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="341b1-146">Indicates that `Get-Package` returns all available versions of the package.</span></span> <span data-ttu-id="341b1-147">Standardmäßig wird `Get-Package` nur die neueste verfügbare Version zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="341b1-147">By default, `Get-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="341b1-148">-Destination</span><span class="sxs-lookup"><span data-stu-id="341b1-148">-Destination</span></span>

<span data-ttu-id="341b1-149">Gibt den Pfad zu einem Verzeichnis an, das extrahierte Paketdateien enthält.</span><span class="sxs-lookup"><span data-stu-id="341b1-149">Specifies the path to a directory that contains extracted package files.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-150">-Excludeversion</span><span class="sxs-lookup"><span data-stu-id="341b1-150">-ExcludeVersion</span></span>

<span data-ttu-id="341b1-151">Wechseln Sie zum Ausschließen der Versionsnummer im Ordner Pfad.</span><span class="sxs-lookup"><span data-stu-id="341b1-151">Switch to exclude the version number in the folder path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-152">-Force</span><span class="sxs-lookup"><span data-stu-id="341b1-152">-Force</span></span>

<span data-ttu-id="341b1-153">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="341b1-153">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="341b1-154">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="341b1-154">-ForceBootstrap</span></span>

<span data-ttu-id="341b1-155">Gibt an, dass `Get-Package` **packagemanagement** zwingt, den Paketanbieter automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="341b1-155">Indicates that `Get-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="341b1-156">-Installupdate</span><span class="sxs-lookup"><span data-stu-id="341b1-156">-InstallUpdate</span></span>

<span data-ttu-id="341b1-157">Gibt an, dass dieses Cmdlet Updates installiert.</span><span class="sxs-lookup"><span data-stu-id="341b1-157">Indicates that this cmdlet installs updates.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-158">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="341b1-158">-MaximumVersion</span></span>

<span data-ttu-id="341b1-159">Gibt die maximale Paketversion an, die Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="341b1-159">Specifies the maximum package version that you want to find.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-160">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="341b1-160">-MinimumVersion</span></span>

<span data-ttu-id="341b1-161">Gibt die minimale Paketversion an, die Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="341b1-161">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="341b1-162">Wenn eine höhere Version verfügbar ist, wird diese Version zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="341b1-162">If a higher version is available, that version is returned.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-163">-Name</span><span class="sxs-lookup"><span data-stu-id="341b1-163">-Name</span></span>

<span data-ttu-id="341b1-164">Gibt einen oder mehrere Paketnamen oder Paketnamen mit Platzhalter Zeichen an.</span><span class="sxs-lookup"><span data-stu-id="341b1-164">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="341b1-165">Trennen Sie mehrere Paketnamen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="341b1-165">Separate multiple package names with commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="341b1-166">-Nopathupdate</span><span class="sxs-lookup"><span data-stu-id="341b1-166">-NoPathUpdate</span></span>

<span data-ttu-id="341b1-167">**Nopathupdate** gilt nur für das `Install-Script` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="341b1-167">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="341b1-168">**Nopathupdate** ist ein vom Anbieter hinzugefügter dynamischer Parameter, der von nicht unterstützt wird `Get-Package` .</span><span class="sxs-lookup"><span data-stu-id="341b1-168">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Get-Package`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-169">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="341b1-169">-PackageManagementProvider</span></span>

<span data-ttu-id="341b1-170">Gibt den Namen eines Paket Verwaltungs Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="341b1-170">Specifies the name of a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-171">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="341b1-171">-ProviderName</span></span>

<span data-ttu-id="341b1-172">Gibt einen oder mehrere Paketanbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="341b1-172">Specifies one or more package provider names.</span></span> <span data-ttu-id="341b1-173">Trennen Sie mehrere Paketanbieter Namen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="341b1-173">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="341b1-174">Verwenden `Get-PackageProvider` Sie, um eine Liste der verfügbaren Paketanbieter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="341b1-174">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-175">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="341b1-175">-RequiredVersion</span></span>

<span data-ttu-id="341b1-176">Gibt die genaue Version des zu suchenden Pakets an.</span><span class="sxs-lookup"><span data-stu-id="341b1-176">Specifies the exact version of the package to find.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-177">-Bereich</span><span class="sxs-lookup"><span data-stu-id="341b1-177">-Scope</span></span>

<span data-ttu-id="341b1-178">Gibt den Suchbereich für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="341b1-178">Specifies the search scope for the package.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet, PowerShellGet
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-179">-Skipabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="341b1-179">-SkipDependencies</span></span>

<span data-ttu-id="341b1-180">Switch, der angibt, dass das Suchen nach Paketabhängigkeiten übersprungen werden soll</span><span class="sxs-lookup"><span data-stu-id="341b1-180">Switch that specifies to skip finding any package dependencies.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-181">-Skippublishercheck</span><span class="sxs-lookup"><span data-stu-id="341b1-181">-SkipPublisherCheck</span></span>

<span data-ttu-id="341b1-182">Ermöglicht es Ihnen, eine Paketversion zu erhalten, die neuer als die installierte Version ist.</span><span class="sxs-lookup"><span data-stu-id="341b1-182">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="341b1-183">Beispielsweise wird ein installiertes Paket, das von einem vertrauenswürdigen Verleger digital signiert ist, aber eine neue Version ist nicht digital signiert.</span><span class="sxs-lookup"><span data-stu-id="341b1-183">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-184">-Type</span><span class="sxs-lookup"><span data-stu-id="341b1-184">-Type</span></span>

<span data-ttu-id="341b1-185">Gibt an, ob nach Paketen mit einem Modul, einem Skript oder einer der beiden Optionen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="341b1-185">Specifies whether to search for packages with a module, a script, or either.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-186">-Additionalarguments</span><span class="sxs-lookup"><span data-stu-id="341b1-186">-AdditionalArguments</span></span>

<span data-ttu-id="341b1-187">Gibt zusätzliche Argumente an.</span><span class="sxs-lookup"><span data-stu-id="341b1-187">Specifies additional arguments.</span></span>

```yaml
Type: System.String[]
Parameter Sets: msi
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-188">-Includesystemcomponent</span><span class="sxs-lookup"><span data-stu-id="341b1-188">-IncludeSystemComponent</span></span>

<span data-ttu-id="341b1-189">Gibt an, dass dieses Cmdlet Systemkomponenten in die Ergebnisse einschließt.</span><span class="sxs-lookup"><span data-stu-id="341b1-189">Indicates that this cmdlet includes system components in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-190">-Include WindowsInstaller</span><span class="sxs-lookup"><span data-stu-id="341b1-190">-IncludeWindowsInstaller</span></span>

<span data-ttu-id="341b1-191">Gibt an, dass dieses Cmdlet die Windows Installer in die Ergebnisse einschließt.</span><span class="sxs-lookup"><span data-stu-id="341b1-191">Indicates that this cmdlet includes the Windows Installer in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="341b1-192">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="341b1-192">CommonParameters</span></span>

<span data-ttu-id="341b1-193">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="341b1-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="341b1-194">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="341b1-194">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="341b1-195">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="341b1-195">INPUTS</span></span>

## <span data-ttu-id="341b1-196">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="341b1-196">OUTPUTS</span></span>

### <span data-ttu-id="341b1-197">Software Identity []</span><span class="sxs-lookup"><span data-stu-id="341b1-197">SoftwareIdentity[]</span></span>

## <span data-ttu-id="341b1-198">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="341b1-198">NOTES</span></span>

<span data-ttu-id="341b1-199">Durch das Einschließen eines Paket Anbieters in einen Befehl können dynamische Parameter für ein Cmdlet verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="341b1-199">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="341b1-200">Dynamische Parameter sind für einen Paketanbieter spezifisch.</span><span class="sxs-lookup"><span data-stu-id="341b1-200">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="341b1-201">Das `Get-Help` -Cmdlet listet die Parametersätze eines Cmdlets auf und schließt den Parametersatz des Anbieters ein.</span><span class="sxs-lookup"><span data-stu-id="341b1-201">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="341b1-202">Beispielsweise `Get-Package` ist für den **PowerShellGet** -Parameter festgelegt, der `-NoPathUpdate` , und enthält `AllowClobber` `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="341b1-202">For example, `Get-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="341b1-203">Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="341b1-203">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="341b1-204">Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="341b1-204">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="341b1-205">Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="341b1-205">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="341b1-206">Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.</span><span class="sxs-lookup"><span data-stu-id="341b1-206">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="341b1-207">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="341b1-207">RELATED LINKS</span></span>

[<span data-ttu-id="341b1-208">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="341b1-208">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="341b1-209">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="341b1-209">Enter-PSSession</span></span>](../Microsoft.PowerShell.Core/Enter-PSSession.md)

[<span data-ttu-id="341b1-210">Find-Package</span><span class="sxs-lookup"><span data-stu-id="341b1-210">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="341b1-211">Get-Help</span><span class="sxs-lookup"><span data-stu-id="341b1-211">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="341b1-212">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="341b1-212">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="341b1-213">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="341b1-213">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="341b1-214">Install-Package</span><span class="sxs-lookup"><span data-stu-id="341b1-214">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="341b1-215">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="341b1-215">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="341b1-216">Save-Package</span><span class="sxs-lookup"><span data-stu-id="341b1-216">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="341b1-217">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="341b1-217">Uninstall-Package</span></span>](Uninstall-Package.md)
