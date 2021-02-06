---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 05/22/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Package
ms.openlocfilehash: c26365eb5b4833c4982fa54e742521cf72307e99
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99603930"
---
# <span data-ttu-id="d6321-102">Get-Package</span><span class="sxs-lookup"><span data-stu-id="d6321-102">Get-Package</span></span>

## <span data-ttu-id="d6321-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d6321-103">SYNOPSIS</span></span>
<span data-ttu-id="d6321-104">Gibt eine Liste aller Softwarepakete zurück, die mit **packagemanagement** installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d6321-104">Returns a list of all software packages that were installed with **PackageManagement**.</span></span>

## <span data-ttu-id="d6321-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d6321-105">SYNTAX</span></span>

### <span data-ttu-id="d6321-106">NuGet</span><span class="sxs-lookup"><span data-stu-id="d6321-106">NuGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="d6321-107">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="d6321-107">PowerShellGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Scope <String>] [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions]
 [<CommonParameters>]
```

## <span data-ttu-id="d6321-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d6321-108">DESCRIPTION</span></span>

<span data-ttu-id="d6321-109">Mit dem- `Get-Package` Cmdlet wird eine Liste aller Softwarepakete auf dem lokalen Computer zurückgegeben, die mit **packagemanagement** installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d6321-109">The `Get-Package` cmdlet returns a list of all software packages on the local computer that were installed with **PackageManagement**.</span></span> <span data-ttu-id="d6321-110">Sie können `Get-Package` auf Remote Computern ausführen, indem Sie Sie als Teil eines- `Invoke-Command` oder- `Enter-PSSession` Befehls oder-Skripts ausführen.</span><span class="sxs-lookup"><span data-stu-id="d6321-110">You can run `Get-Package` on remote computers by running it as part of an `Invoke-Command` or `Enter-PSSession` command or script.</span></span>

## <span data-ttu-id="d6321-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d6321-111">EXAMPLES</span></span>

### <span data-ttu-id="d6321-112">Beispiel 1: alle installierten Pakete erhalten</span><span class="sxs-lookup"><span data-stu-id="d6321-112">Example 1: Get all installed packages</span></span>

<span data-ttu-id="d6321-113">Mit dem- `Get-Package` Cmdlet werden alle Pakete abgerufen, die auf dem lokalen Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="d6321-113">The `Get-Package` cmdlet gets all packages that are installed on the local computer.</span></span>

```powershell
Get-Package
```

```Output
Name           Version      Source                                     ProviderName
----           -------      ------                                     ------------
posh-git       0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
```

### <span data-ttu-id="d6321-114">Beispiel 2: Get-Pakete, die auf einem Remote Computer installiert sind</span><span class="sxs-lookup"><span data-stu-id="d6321-114">Example 2: Get packages that are installed on a remote computer</span></span>

<span data-ttu-id="d6321-115">Mit diesem Befehl wird eine Liste der Pakete abgerufen, die von **packagemanagement** auf einem Remote Computer installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d6321-115">This command gets a list of packages that were installed by **PackageManagement** on a remote computer.</span></span> <span data-ttu-id="d6321-116">Mit diesem Befehl werden Sie aufgefordert, das Kennwort des angegebenen Benutzers anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d6321-116">This command prompts you to provide the specified user's password.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -Credential CONTOSO\TestUser -ScriptBlock {Get-Package}
```

<span data-ttu-id="d6321-117">`Invoke-Command` verwendet den **Computername** -Parameter, um einen Remote Computer anzugeben, **Server01**.</span><span class="sxs-lookup"><span data-stu-id="d6321-117">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer, **Server01**.</span></span> <span data-ttu-id="d6321-118">Der **Credential** -Parameter gibt eine Domäne und einen Benutzernamen mit Berechtigungen zum Ausführen von Befehlen auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="d6321-118">The **Credential** parameter specifies a domain and user name with permissions to run commands on the computer.</span></span> <span data-ttu-id="d6321-119">Der **ScriptBlock** -Parameter führt das `Get-Package` Cmdlet auf dem Remote Computer aus.</span><span class="sxs-lookup"><span data-stu-id="d6321-119">The **ScriptBlock** parameter runs the `Get-Package` cmdlet on the remote computer.</span></span>

### <span data-ttu-id="d6321-120">Beispiel 3: Paket für einen angegebenen Anbieter erhalten</span><span class="sxs-lookup"><span data-stu-id="d6321-120">Example 3: Get packages for a specified provider</span></span>

<span data-ttu-id="d6321-121">Mit diesem Befehl werden die auf dem lokalen Computer installierten Softwarepakete von einem bestimmten Anbieter abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d6321-121">This command gets software packages installed on the local computer from a specific provider.</span></span>

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

<span data-ttu-id="d6321-122">`Get-Package` verwendet den **providerName** -Parameter, um einen bestimmten Anbieter, **PowerShellGet**, anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d6321-122">`Get-Package` uses the **ProviderName** parameter to specify a specific provider, **PowerShellGet**.</span></span>
<span data-ttu-id="d6321-123">Mit dem Parameter **alle Versionen** wird jede installierte Version angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6321-123">The **All-Versions** parameter displays each version that is installed.</span></span>

### <span data-ttu-id="d6321-124">Beispiel 4: beziehen einer exakten Version eines bestimmten Pakets</span><span class="sxs-lookup"><span data-stu-id="d6321-124">Example 4: Get an exact version of a specific package</span></span>

<span data-ttu-id="d6321-125">Mit diesem Befehl wird eine bestimmte Version eines installierten Pakets abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d6321-125">This command gets a specific version of an installed package.</span></span> <span data-ttu-id="d6321-126">Es können mehr als eine Version eines Pakets installiert werden.</span><span class="sxs-lookup"><span data-stu-id="d6321-126">More than one version of a package can be installed.</span></span>

```powershell
Get-Package -Name PackageManagement -ProviderName PowerShellGet -RequiredVersion 1.3.1
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

<span data-ttu-id="d6321-127">`Get-Package` verwendet den **Name** -Parameter, um den Paketnamen, **packagemanagement**, anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d6321-127">`Get-Package` uses **Name** parameter to specify the package name, **PackageManagement**.</span></span> <span data-ttu-id="d6321-128">Der **providerName** -Parameter gibt den Anbieter **PowerShellGet** an.</span><span class="sxs-lookup"><span data-stu-id="d6321-128">The **ProviderName** parameter specifies the provider, **PowerShellGet**.</span></span> <span data-ttu-id="d6321-129">Der **erforderliche-Version-** Parameter gibt eine installierte Version an.</span><span class="sxs-lookup"><span data-stu-id="d6321-129">The **Required-Version** parameter specifies an installed version.</span></span>

### <span data-ttu-id="d6321-130">Beispiel 5: Deinstallieren eines Pakets</span><span class="sxs-lookup"><span data-stu-id="d6321-130">Example 5: Uninstall a package</span></span>

<span data-ttu-id="d6321-131">In diesem Beispiel werden Paketinformationen abgerufen und dann das Paket deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="d6321-131">This example gets package information and then uninstalls the package.</span></span>

```powershell
Get-Package -Name posh-git -RequiredVersion 0.7.3 | Uninstall-Package
```

<span data-ttu-id="d6321-132">`Get-Package` verwendet den **Name** -Parameter zum Angeben des Paket namens **Posh-git**.</span><span class="sxs-lookup"><span data-stu-id="d6321-132">`Get-Package` uses the **Name** parameter to specify the package name, **posh-git**.</span></span> <span data-ttu-id="d6321-133">Der Parameter "Requirements **dversion** " ist eine bestimmte Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="d6321-133">The **RequiredVersion** parameter is a specific version of the package.</span></span> <span data-ttu-id="d6321-134">Das Objekt wird über die Pipeline an das `Uninstall-Package` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="d6321-134">The object is sent down the pipeline to the `Uninstall-Package` cmdlet.</span></span> <span data-ttu-id="d6321-135">`Uninstall-Package` entfernt das Paket.</span><span class="sxs-lookup"><span data-stu-id="d6321-135">`Uninstall-Package` removes the package.</span></span>

## <span data-ttu-id="d6321-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d6321-136">PARAMETERS</span></span>

### <span data-ttu-id="d6321-137">-Allowclobber</span><span class="sxs-lookup"><span data-stu-id="d6321-137">-AllowClobber</span></span>

<span data-ttu-id="d6321-138">Überschreibt Warnmeldungen zu Konflikten mit vorhandenen Befehlen.</span><span class="sxs-lookup"><span data-stu-id="d6321-138">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="d6321-139">Überschreibt vorhandene Befehle mit demselben Namen wie Befehle, die von einem Modul installiert werden.</span><span class="sxs-lookup"><span data-stu-id="d6321-139">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>

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

### <span data-ttu-id="d6321-140">-Allowprereleaseversions</span><span class="sxs-lookup"><span data-stu-id="d6321-140">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="d6321-141">Schließt Pakete ein, die in den Ergebnissen als Vorabversion gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="d6321-141">Includes packages marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="d6321-142">-Allversions</span><span class="sxs-lookup"><span data-stu-id="d6321-142">-AllVersions</span></span>

<span data-ttu-id="d6321-143">Gibt an, dass `Get-Package` alle verfügbaren Versionen des Pakets zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d6321-143">Indicates that `Get-Package` returns all available versions of the package.</span></span> <span data-ttu-id="d6321-144">Standardmäßig wird `Get-Package` nur die neueste verfügbare Version zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d6321-144">By default, `Get-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="d6321-145">-Destination</span><span class="sxs-lookup"><span data-stu-id="d6321-145">-Destination</span></span>

<span data-ttu-id="d6321-146">Gibt den Pfad zu einem Verzeichnis an, das extrahierte Paketdateien enthält.</span><span class="sxs-lookup"><span data-stu-id="d6321-146">Specifies the path to a directory that contains extracted package files.</span></span>

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

### <span data-ttu-id="d6321-147">-Excludeversion</span><span class="sxs-lookup"><span data-stu-id="d6321-147">-ExcludeVersion</span></span>

<span data-ttu-id="d6321-148">Wechseln Sie zum Ausschließen der Versionsnummer im Ordner Pfad.</span><span class="sxs-lookup"><span data-stu-id="d6321-148">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="d6321-149">-Force</span><span class="sxs-lookup"><span data-stu-id="d6321-149">-Force</span></span>

<span data-ttu-id="d6321-150">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d6321-150">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="d6321-151">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="d6321-151">-ForceBootstrap</span></span>

<span data-ttu-id="d6321-152">Gibt an, dass `Get-Package` **packagemanagement** zwingt, den Paketanbieter automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="d6321-152">Indicates that `Get-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="d6321-153">-Installupdate</span><span class="sxs-lookup"><span data-stu-id="d6321-153">-InstallUpdate</span></span>

<span data-ttu-id="d6321-154">Gibt an, dass dieses Cmdlet Updates installiert.</span><span class="sxs-lookup"><span data-stu-id="d6321-154">Indicates that this cmdlet installs updates.</span></span>

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

### <span data-ttu-id="d6321-155">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="d6321-155">-MaximumVersion</span></span>

<span data-ttu-id="d6321-156">Gibt die maximale Paketversion an, die Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="d6321-156">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="d6321-157">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="d6321-157">-MinimumVersion</span></span>

<span data-ttu-id="d6321-158">Gibt die minimale Paketversion an, die Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="d6321-158">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="d6321-159">Wenn eine höhere Version verfügbar ist, wird diese Version zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d6321-159">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="d6321-160">-Name</span><span class="sxs-lookup"><span data-stu-id="d6321-160">-Name</span></span>

<span data-ttu-id="d6321-161">Gibt einen oder mehrere Paketnamen oder Paketnamen mit Platzhalter Zeichen an.</span><span class="sxs-lookup"><span data-stu-id="d6321-161">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="d6321-162">Trennen Sie mehrere Paketnamen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="d6321-162">Separate multiple package names with commas.</span></span>

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

### <span data-ttu-id="d6321-163">-Nopathupdate</span><span class="sxs-lookup"><span data-stu-id="d6321-163">-NoPathUpdate</span></span>

<span data-ttu-id="d6321-164">**Nopathupdate** gilt nur für das `Install-Script` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d6321-164">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="d6321-165">**Nopathupdate** ist ein vom Anbieter hinzugefügter dynamischer Parameter, der von nicht unterstützt wird `Get-Package` .</span><span class="sxs-lookup"><span data-stu-id="d6321-165">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Get-Package`.</span></span>

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

### <span data-ttu-id="d6321-166">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="d6321-166">-PackageManagementProvider</span></span>

<span data-ttu-id="d6321-167">Gibt den Namen eines Paket Verwaltungs Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="d6321-167">Specifies the name of a package management provider.</span></span>

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

### <span data-ttu-id="d6321-168">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="d6321-168">-ProviderName</span></span>

<span data-ttu-id="d6321-169">Gibt einen oder mehrere Paketanbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="d6321-169">Specifies one or more package provider names.</span></span> <span data-ttu-id="d6321-170">Trennen Sie mehrere Paketanbieter Namen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="d6321-170">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="d6321-171">Verwenden `Get-PackageProvider` Sie, um eine Liste der verfügbaren Paketanbieter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d6321-171">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="d6321-172">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="d6321-172">-RequiredVersion</span></span>

<span data-ttu-id="d6321-173">Gibt die genaue Version des zu suchenden Pakets an.</span><span class="sxs-lookup"><span data-stu-id="d6321-173">Specifies the exact version of the package to find.</span></span>

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

### <span data-ttu-id="d6321-174">-Bereich</span><span class="sxs-lookup"><span data-stu-id="d6321-174">-Scope</span></span>

<span data-ttu-id="d6321-175">Gibt den Suchbereich für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="d6321-175">Specifies the search scope for the package.</span></span>

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

### <span data-ttu-id="d6321-176">-Skipabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="d6321-176">-SkipDependencies</span></span>

<span data-ttu-id="d6321-177">Switch, der angibt, dass das Suchen nach Paketabhängigkeiten übersprungen werden soll</span><span class="sxs-lookup"><span data-stu-id="d6321-177">Switch that specifies to skip finding any package dependencies.</span></span>

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

### <span data-ttu-id="d6321-178">-Skippublishercheck</span><span class="sxs-lookup"><span data-stu-id="d6321-178">-SkipPublisherCheck</span></span>

<span data-ttu-id="d6321-179">Ermöglicht es Ihnen, eine Paketversion zu erhalten, die neuer als die installierte Version ist.</span><span class="sxs-lookup"><span data-stu-id="d6321-179">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="d6321-180">Beispielsweise wird ein installiertes Paket, das von einem vertrauenswürdigen Verleger digital signiert ist, aber eine neue Version ist nicht digital signiert.</span><span class="sxs-lookup"><span data-stu-id="d6321-180">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="d6321-181">-Type</span><span class="sxs-lookup"><span data-stu-id="d6321-181">-Type</span></span>

<span data-ttu-id="d6321-182">Gibt an, ob nach Paketen mit einem Modul, einem Skript oder einer der beiden Optionen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6321-182">Specifies whether to search for packages with a module, a script, or either.</span></span>

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

### <span data-ttu-id="d6321-183">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d6321-183">CommonParameters</span></span>

<span data-ttu-id="d6321-184">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d6321-184">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d6321-185">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d6321-185">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d6321-186">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d6321-186">INPUTS</span></span>

## <span data-ttu-id="d6321-187">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d6321-187">OUTPUTS</span></span>

### <span data-ttu-id="d6321-188">Software Identity []</span><span class="sxs-lookup"><span data-stu-id="d6321-188">SoftwareIdentity[]</span></span>

## <span data-ttu-id="d6321-189">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d6321-189">NOTES</span></span>

<span data-ttu-id="d6321-190">Durch das Einschließen eines Paket Anbieters in einen Befehl können dynamische Parameter für ein Cmdlet verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d6321-190">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="d6321-191">Dynamische Parameter sind für einen Paketanbieter spezifisch.</span><span class="sxs-lookup"><span data-stu-id="d6321-191">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="d6321-192">Das `Get-Help` -Cmdlet listet die Parametersätze eines Cmdlets auf und schließt den Parametersatz des Anbieters ein.</span><span class="sxs-lookup"><span data-stu-id="d6321-192">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="d6321-193">Beispielsweise `Get-Package` ist für den **PowerShellGet** -Parameter festgelegt, der `-NoPathUpdate` , und enthält `AllowClobber` `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="d6321-193">For example, `Get-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6321-194">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="d6321-194">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="d6321-195">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="d6321-195">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="d6321-196">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="d6321-196">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="d6321-197">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="d6321-197">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="d6321-198">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d6321-198">RELATED LINKS</span></span>

[<span data-ttu-id="d6321-199">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="d6321-199">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="d6321-200">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="d6321-200">Enter-PSSession</span></span>](../Microsoft.PowerShell.Core/Enter-PSSession.md)

[<span data-ttu-id="d6321-201">Find-Package</span><span class="sxs-lookup"><span data-stu-id="d6321-201">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="d6321-202">Get-Help</span><span class="sxs-lookup"><span data-stu-id="d6321-202">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="d6321-203">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="d6321-203">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="d6321-204">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d6321-204">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="d6321-205">Install-Package</span><span class="sxs-lookup"><span data-stu-id="d6321-205">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="d6321-206">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="d6321-206">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="d6321-207">Save-Package</span><span class="sxs-lookup"><span data-stu-id="d6321-207">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="d6321-208">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="d6321-208">Uninstall-Package</span></span>](Uninstall-Package.md)
