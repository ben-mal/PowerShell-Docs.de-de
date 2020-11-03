---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/uninstall-package?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Package
ms.openlocfilehash: 4da97d9643483db0eae4fc7d34e0e6997d16bd04
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215767"
---
# <span data-ttu-id="cfbf9-103">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="cfbf9-103">Uninstall-Package</span></span>

## <span data-ttu-id="cfbf9-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="cfbf9-104">SYNOPSIS</span></span>
<span data-ttu-id="cfbf9-105">Deinstalliert mindestens ein Softwarepaket.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-105">Uninstalls one or more software packages.</span></span>

## <span data-ttu-id="cfbf9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cfbf9-106">SYNTAX</span></span>

### <span data-ttu-id="cfbf9-107">Packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="cfbf9-107">PackageByInputObject</span></span>

```
Uninstall-Package [-InputObject] <SoftwareIdentity[]> [-AllVersions] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cfbf9-108">Packagebysearch</span><span class="sxs-lookup"><span data-stu-id="cfbf9-108">PackageBySearch</span></span>

```
Uninstall-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="cfbf9-109">Nuget: packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="cfbf9-109">NuGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="cfbf9-110">Nuget: packagebysearch</span><span class="sxs-lookup"><span data-stu-id="cfbf9-110">NuGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="cfbf9-111">PowerShellGet: packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="cfbf9-111">PowerShellGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="cfbf9-112">PowerShellGet: packagebysearch</span><span class="sxs-lookup"><span data-stu-id="cfbf9-112">PowerShellGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

## <span data-ttu-id="cfbf9-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cfbf9-113">DESCRIPTION</span></span>

<span data-ttu-id="cfbf9-114">Mit dem- `Uninstall-Package` Cmdlet werden ein oder mehrere Softwarepakete auf dem lokalen Computer deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-114">The `Uninstall-Package` cmdlet uninstalls one or more software packages from the local computer.</span></span> <span data-ttu-id="cfbf9-115">Verwenden Sie das-Cmdlet, um installierte Pakete zu suchen `Get-Package` .</span><span class="sxs-lookup"><span data-stu-id="cfbf9-115">To find installed packages, use the `Get-Package` cmdlet.</span></span>

## <span data-ttu-id="cfbf9-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="cfbf9-116">EXAMPLES</span></span>

### <span data-ttu-id="cfbf9-117">Beispiel 1: Deinstallieren eines Pakets</span><span class="sxs-lookup"><span data-stu-id="cfbf9-117">Example 1: Uninstall a package</span></span>

<span data-ttu-id="cfbf9-118">Mit dem- `Uninstall-Package` Cmdlet werden Pakete deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-118">The `Uninstall-Package` cmdlet uninstalls packages.</span></span> <span data-ttu-id="cfbf9-119">Der **Name** -Parameter gibt das zu deinstallierende Paket an.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-119">The **Name** parameter specifies the package to uninstall.</span></span> <span data-ttu-id="cfbf9-120">Wenn mehrere Versionen eines Pakets installiert sind, wird die neueste Version deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-120">If multiple versions of a package are installed, the newest version is uninstalled.</span></span>

```
PS> Uninstall-Package -Name NuGet.Core
```

### <span data-ttu-id="cfbf9-121">Beispiel 2: Verwenden der Pipeline zum Deinstallieren eines Pakets</span><span class="sxs-lookup"><span data-stu-id="cfbf9-121">Example 2: Use the pipeline to uninstall a package</span></span>

<span data-ttu-id="cfbf9-122">`Get-Package` Gibt ein bestimmtes Paket an und sendet das **softwareidentity** -Objekt über die Pipeline an das `Uninsall-Package` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-122">`Get-Package` locates a specific package and sends the **SoftwareIdentity** object down the pipeline to the `Uninsall-Package` cmdlet.</span></span>

```
PS> Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 | Uninstall-Package
```

<span data-ttu-id="cfbf9-123">Das `Get-Package` -Cmdlet verwendet die Parameter " **Name** " und "Requirements **dversion** ", um ein Paket anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-123">The `Get-Package` cmdlet uses the **Name** and **RequiredVersion** parameters to specify a package.</span></span>
<span data-ttu-id="cfbf9-124">Ein **softwareidentity** -Objekt wird über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-124">A **SoftwareIdentity** object is sent down the pipeline.</span></span> <span data-ttu-id="cfbf9-125">Das `Uninstall-Package` Cmdlet empfängt das Objekt als **Inputobject** und entfernt das Paket.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-125">The `Uninstall-Package` cmdlet receives the object as an **InputObject** and removes the package.</span></span>

<span data-ttu-id="cfbf9-126">Als Alternative `Uninstall-Package` kann das Cmdlet einen Wert für den **Inputobject** -Parameter angeben:</span><span class="sxs-lookup"><span data-stu-id="cfbf9-126">As an alternative, the `Uninstall-Package` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Uninstall-Package -InputObject ( Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 )`

## <span data-ttu-id="cfbf9-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cfbf9-127">PARAMETERS</span></span>

### <span data-ttu-id="cfbf9-128">-Allowclobber</span><span class="sxs-lookup"><span data-stu-id="cfbf9-128">-AllowClobber</span></span>

<span data-ttu-id="cfbf9-129">Überschreibt Warnmeldungen zu Konflikten mit vorhandenen Befehlen.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-129">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="cfbf9-130">Überschreibt vorhandene Befehle, die denselben Namen wie die Befehle aufweisen, die installiert werden.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-130">Overwrites existing commands that have the same name as commands being installed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfbf9-131">-Allowprereleaseversions</span><span class="sxs-lookup"><span data-stu-id="cfbf9-131">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="cfbf9-132">Ermöglicht das Deinstallieren von als Vorabversion markierten Paketen.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-132">Allows packages marked as prerelease to be uninstalled.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfbf9-133">-Allversions</span><span class="sxs-lookup"><span data-stu-id="cfbf9-133">-AllVersions</span></span>

<span data-ttu-id="cfbf9-134">Gibt an, dass mit diesem Cmdlet alle Versionen des Pakets deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-134">Indicates that this cmdlet uninstalls all versions of the package.</span></span>

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

### <span data-ttu-id="cfbf9-135">-Destination</span><span class="sxs-lookup"><span data-stu-id="cfbf9-135">-Destination</span></span>

<span data-ttu-id="cfbf9-136">Gibt eine Zeichenfolge des Pfads zum Eingabe Objekt an.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-136">Specifies a string of the path to the input object.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfbf9-137">-Excludeversion</span><span class="sxs-lookup"><span data-stu-id="cfbf9-137">-ExcludeVersion</span></span>

<span data-ttu-id="cfbf9-138">Wechseln Sie zum Ausschließen der Versionsnummer im Ordner Pfad.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-138">Switch to exclude the version number in the folder path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfbf9-139">-Force</span><span class="sxs-lookup"><span data-stu-id="cfbf9-139">-Force</span></span>

<span data-ttu-id="cfbf9-140">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-140">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="cfbf9-141">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="cfbf9-141">-ForceBootstrap</span></span>

<span data-ttu-id="cfbf9-142">Erzwingt **packagemanagement** , den Paketanbieter für das angegebene Paket automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-142">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="cfbf9-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cfbf9-143">-InputObject</span></span>

<span data-ttu-id="cfbf9-144">Akzeptiert Pipeline Eingaben, die das **softwareidentity** -Objekt des Pakets aus dem `Get-Package` Cmdlet angeben.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-144">Accepts pipeline input that specifies the package's **SoftwareIdentity** object from the `Get-Package` cmdlet.</span></span> <span data-ttu-id="cfbf9-145">**Inputobject** akzeptiert das **softwareidentity** -Objekt als `Get-Package` Wert oder eine Variable, die das Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-145">**InputObject** accepts the **SoftwareIdentity** object as a `Get-Package` value or a variable that contains the object.</span></span>

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

### <span data-ttu-id="cfbf9-146">-Installupdate</span><span class="sxs-lookup"><span data-stu-id="cfbf9-146">-InstallUpdate</span></span>

<span data-ttu-id="cfbf9-147">Gibt an, dass `Uninstall-Package` Updates von deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-147">Indicates that `Uninstall-Package` uninstalls updates.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfbf9-148">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="cfbf9-148">-MaximumVersion</span></span>

<span data-ttu-id="cfbf9-149">Gibt die maximal zulässige Paketversion an, die Sie deinstallieren möchten.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-149">Specifies the maximum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="cfbf9-150">Wenn Sie diesen Parameter nicht angeben, wird `Uninstall-Package` die neueste Version des Pakets von deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-150">If you don't specify this parameter, `Uninstall-Package` uninstalls the package's newest version.</span></span>

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

### <span data-ttu-id="cfbf9-151">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="cfbf9-151">-MinimumVersion</span></span>

<span data-ttu-id="cfbf9-152">Gibt die minimal zulässige Paketversion an, die Sie deinstallieren möchten.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-152">Specifies the minimum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="cfbf9-153">Wenn Sie diesen Parameter nicht hinzufügen, `Uninstall-Package` deinstalliert die neueste Version des Pakets, die jeder Version entspricht, die durch den **MaximumVersion** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-153">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="cfbf9-154">-Name</span><span class="sxs-lookup"><span data-stu-id="cfbf9-154">-Name</span></span>

<span data-ttu-id="cfbf9-155">Gibt mindestens einen Paketnamen an.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-155">Specifies one or more package names.</span></span> <span data-ttu-id="cfbf9-156">Mehrere Paketnamen müssen durch Kommas getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-156">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="cfbf9-157">-Nopathupdate</span><span class="sxs-lookup"><span data-stu-id="cfbf9-157">-NoPathUpdate</span></span>

<span data-ttu-id="cfbf9-158">**Nopathupdate** gilt nur für das `Install-Script` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-158">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="cfbf9-159">**Nopathupdate** ist ein vom Anbieter hinzugefügter dynamischer Parameter, der von nicht unterstützt wird `Uninstall-Package` .</span><span class="sxs-lookup"><span data-stu-id="cfbf9-159">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Uninstall-Package`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfbf9-160">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="cfbf9-160">-PackageManagementProvider</span></span>

<span data-ttu-id="cfbf9-161">Gibt den **packagemanagement** -Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-161">Specifies the **PackageManagement** provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfbf9-162">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="cfbf9-162">-ProviderName</span></span>

<span data-ttu-id="cfbf9-163">Gibt einen oder mehrere Paketanbieter Namen für die Suche nach Paketen an.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-163">Specifies one or more package provider names to search for packages.</span></span> <span data-ttu-id="cfbf9-164">Paketanbieternamen können Sie durch Ausführen des Cmdlets `Get-PackageProvider` abrufen.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-164">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cfbf9-165">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="cfbf9-165">-RequiredVersion</span></span>

<span data-ttu-id="cfbf9-166">Gibt die exakt zulässige Version des Pakets an, das Sie deinstallieren möchten.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-166">Specifies the exact allowed version of the package that you want to uninstall.</span></span> <span data-ttu-id="cfbf9-167">Wenn Sie diesen Parameter nicht hinzufügen, `Uninstall-Package` deinstalliert die neueste Version des Pakets, die jeder Version entspricht, die durch den **MaximumVersion** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-167">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="cfbf9-168">-Bereich</span><span class="sxs-lookup"><span data-stu-id="cfbf9-168">-Scope</span></span>

<span data-ttu-id="cfbf9-169">Gibt den Bereich an, für den das Paket deinstalliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-169">Specifies the scope for which to uninstall the package.</span></span> <span data-ttu-id="cfbf9-170">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cfbf9-170">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="cfbf9-171">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="cfbf9-171">CurrentUser</span></span>
- <span data-ttu-id="cfbf9-172">ALLUSERS</span><span class="sxs-lookup"><span data-stu-id="cfbf9-172">AllUsers</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch, PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfbf9-173">-Skipabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="cfbf9-173">-SkipDependencies</span></span>

<span data-ttu-id="cfbf9-174">Überspringt die deinstalstallation von Software Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-174">Skips the uninstallation of software dependencies.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfbf9-175">-Skippublishercheck</span><span class="sxs-lookup"><span data-stu-id="cfbf9-175">-SkipPublisherCheck</span></span>

<span data-ttu-id="cfbf9-176">Ermöglicht es Ihnen, eine Paketversion zu erhalten, die neuer als die installierte Version ist.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-176">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="cfbf9-177">Beispielsweise wird ein installiertes Paket, das von einem vertrauenswürdigen Verleger digital signiert ist, aber eine neue Version ist nicht digital signiert.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-177">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfbf9-178">-Type</span><span class="sxs-lookup"><span data-stu-id="cfbf9-178">-Type</span></span>

<span data-ttu-id="cfbf9-179">Gibt an, ob Pakete mit einem Modul, einem Skript oder beidem gesucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-179">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="cfbf9-180">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cfbf9-180">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="cfbf9-181">Modul</span><span class="sxs-lookup"><span data-stu-id="cfbf9-181">Module</span></span>
- <span data-ttu-id="cfbf9-182">Skript</span><span class="sxs-lookup"><span data-stu-id="cfbf9-182">Script</span></span>
- <span data-ttu-id="cfbf9-183">Alle</span><span class="sxs-lookup"><span data-stu-id="cfbf9-183">All</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfbf9-184">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cfbf9-184">-Confirm</span></span>

<span data-ttu-id="cfbf9-185">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-185">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="cfbf9-186">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cfbf9-186">-WhatIf</span></span>

<span data-ttu-id="cfbf9-187">Zeigt, was geschieht, wenn das `Uninstall-Package` Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-187">Shows what would happen if `Uninstall-Package` cmdlet is run.</span></span> <span data-ttu-id="cfbf9-188">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-188">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="cfbf9-189">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cfbf9-189">CommonParameters</span></span>

<span data-ttu-id="cfbf9-190">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-190">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cfbf9-191">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cfbf9-191">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cfbf9-192">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="cfbf9-192">INPUTS</span></span>

### <span data-ttu-id="cfbf9-193">`Uninstall-Package` akzeptiert **softwareidentity** -Objekte aus der Pipeline als Eingabe.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-193">`Uninstall-Package` accepts **SoftwareIdentity** objects from the pipeline as input.</span></span>

## <span data-ttu-id="cfbf9-194">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="cfbf9-194">OUTPUTS</span></span>

### <span data-ttu-id="cfbf9-195">`Uninstall-Package` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-195">`Uninstall-Package` doesn't generate any output.</span></span>

## <span data-ttu-id="cfbf9-196">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="cfbf9-196">NOTES</span></span>

<span data-ttu-id="cfbf9-197">Durch das Einschließen eines Paket Anbieters in einen Befehl können dynamische Parameter für ein Cmdlet verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-197">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="cfbf9-198">Dynamische Parameter sind für einen Paketanbieter spezifisch.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-198">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="cfbf9-199">Das `Get-Help` -Cmdlet listet die Parametersätze eines Cmdlets auf und schließt den Parametersatz des Anbieters ein.</span><span class="sxs-lookup"><span data-stu-id="cfbf9-199">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="cfbf9-200">Beispielsweise `Uninstall-Package` ist für den **PowerShellGet** -Parameter festgelegt, der `-NoPathUpdate` , und enthält `AllowClobber` `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="cfbf9-200">For example, `Uninstall-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="cfbf9-201">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="cfbf9-201">RELATED LINKS</span></span>

[<span data-ttu-id="cfbf9-202">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="cfbf9-202">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="cfbf9-203">Find-Package</span><span class="sxs-lookup"><span data-stu-id="cfbf9-203">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="cfbf9-204">Get-Package</span><span class="sxs-lookup"><span data-stu-id="cfbf9-204">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="cfbf9-205">Install-Package</span><span class="sxs-lookup"><span data-stu-id="cfbf9-205">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="cfbf9-206">Save-Package</span><span class="sxs-lookup"><span data-stu-id="cfbf9-206">Save-Package</span></span>](Save-Package.md)

