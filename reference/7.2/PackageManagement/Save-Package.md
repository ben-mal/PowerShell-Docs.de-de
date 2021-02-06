---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/save-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Package
ms.openlocfilehash: 93ec8264bad588e38554daddcdf5dc9befce053e
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99600899"
---
# <span data-ttu-id="5eee9-102">Save-Package</span><span class="sxs-lookup"><span data-stu-id="5eee9-102">Save-Package</span></span>

## <span data-ttu-id="5eee9-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5eee9-103">SYNOPSIS</span></span>
<span data-ttu-id="5eee9-104">Speichert Pakete auf dem lokalen Computer, ohne Sie zu installieren.</span><span class="sxs-lookup"><span data-stu-id="5eee9-104">Saves packages to the local computer without installing them.</span></span>

## <span data-ttu-id="5eee9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5eee9-105">SYNTAX</span></span>

### <span data-ttu-id="5eee9-106">Packagebysearch</span><span class="sxs-lookup"><span data-stu-id="5eee9-106">PackageBySearch</span></span>

```
Save-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Path <String>] [-LiteralPath <String>]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllVersions]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="5eee9-107">Packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="5eee9-107">PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] -InputObject <SoftwareIdentity>
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllVersions]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5eee9-108">Nuget: packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="5eee9-108">NuGet:PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>]
 [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="5eee9-109">NuGet</span><span class="sxs-lookup"><span data-stu-id="5eee9-109">NuGet</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>]
 [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="5eee9-110">PowerShellGet: packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="5eee9-110">PowerShellGet:PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AllowPrereleaseVersions] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [<CommonParameters>]
```

### <span data-ttu-id="5eee9-111">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="5eee9-111">PowerShellGet</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AllowPrereleaseVersions] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [<CommonParameters>]
```

## <span data-ttu-id="5eee9-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5eee9-112">DESCRIPTION</span></span>

<span data-ttu-id="5eee9-113">Mit dem- `Save-Package` Cmdlet werden Pakete auf dem lokalen Computer gespeichert, die Pakete werden jedoch nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="5eee9-113">The `Save-Package` cmdlet saves packages to the local computer but doesn't install the packages.</span></span>
<span data-ttu-id="5eee9-114">Dieses Cmdlet speichert die neueste Version eines Pakets, es sei denn, Sie geben eine "Requirements **dverion" an**.</span><span class="sxs-lookup"><span data-stu-id="5eee9-114">This cmdlet saves the newest version of a package unless you specify a **RequiredVerion**.</span></span> <span data-ttu-id="5eee9-115">Die **path** -und **literalpath** -Parameter schließen sich gegenseitig aus und können dem gleichen Befehl nicht hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5eee9-115">The **Path** and **LiteralPath** parameters are mutually exclusive, and cannot be added to the same command.</span></span>

## <span data-ttu-id="5eee9-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5eee9-116">EXAMPLES</span></span>

### <span data-ttu-id="5eee9-117">Beispiel 1: Speichern eines Pakets auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="5eee9-117">Example 1: Save a package to the local computer</span></span>

<span data-ttu-id="5eee9-118">In diesem Beispiel wird die neueste Version des Pakets in einem Verzeichnis auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5eee9-118">This example saves the newest version of the package to a directory on the local computer.</span></span> <span data-ttu-id="5eee9-119">Die Paketabhängigkeiten werden mit dem Paket heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="5eee9-119">The package's dependencies are download with the package.</span></span>

```
PS> Save-Package -Name NuGet.Core -ProviderName NuGet -Path C:\LocalPkg
```

```Output
Name                    Version    Source    Summary
----                    -------    ------    -------
Microsoft.Web.Xdt       3.0.0      Nuget     Microsoft Xml Document Transformation (XDT) enables...
NuGet.Core              2.14.0     Nuget     NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="5eee9-120">`Save-Package` verwendet den **Name** -Parameter, um das Paket anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5eee9-120">`Save-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="5eee9-121">Das Paket wird aus dem durch den **providerName** -Parameter angegebenen Repository heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="5eee9-121">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="5eee9-122">Der **path** -Parameter bestimmt, wo das Paket gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="5eee9-122">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="5eee9-123">Beispiel 2: Speichern einer bestimmten Paketversion</span><span class="sxs-lookup"><span data-stu-id="5eee9-123">Example 2: Save a specific package version</span></span>

<span data-ttu-id="5eee9-124">In diesem Beispiel wird die Paketversion angegeben und in einem Verzeichnis auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5eee9-124">This example specifies the package version and saves it to a directory on the local computer.</span></span>

```
PS> Save-Package -Name NuGet.Core -RequiredVersion 2.9.0 -ProviderName NuGet -Path C:\LocalPkg
```

```Output
Name                    Version    Source    Summary
----                    -------    ------    -------
Microsoft.Web.Xdt       3.0.0      Nuget     Microsoft Xml Document Transformation (XDT) enables...
NuGet.Core              2.9.0      Nuget     NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="5eee9-125">`Save-Package` verwendet den **Name** -Parameter, um das Paket anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5eee9-125">`Save-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="5eee9-126">Requirements **dversion** gibt eine bestimmte Paketversion an.</span><span class="sxs-lookup"><span data-stu-id="5eee9-126">**RequiredVersion** indicates a specific package version.</span></span> <span data-ttu-id="5eee9-127">Das Paket wird aus dem durch den **providerName** -Parameter angegebenen Repository heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="5eee9-127">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="5eee9-128">Der **path** -Parameter bestimmt, wo das Paket gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="5eee9-128">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="5eee9-129">Beispiel 3: Verwenden von Find-Package zum Speichern eines Pakets</span><span class="sxs-lookup"><span data-stu-id="5eee9-129">Example 3: Use Find-Package to save a package</span></span>

<span data-ttu-id="5eee9-130">Dieser Befehl verwendet `Find-Package` , um die neueste Version des Pakets zu suchen, und sendet das Objekt an `Save-Package` .</span><span class="sxs-lookup"><span data-stu-id="5eee9-130">This command uses `Find-Package` to locate the newest version of the package and sends the object to `Save-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -ProviderName NuGet | Save-Package -Path C:\LocalPkg
```

<span data-ttu-id="5eee9-131">`Find-Package` verwendet den **Name** -Parameter, um das Paket anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5eee9-131">`Find-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="5eee9-132">Das Paket wird aus dem durch den **providerName** -Parameter angegebenen Repository heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="5eee9-132">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="5eee9-133">Das Objekt wird über die Pipeline an gesendet `Save-Package` .</span><span class="sxs-lookup"><span data-stu-id="5eee9-133">The object is sent down the pipeline to `Save-Package`.</span></span> <span data-ttu-id="5eee9-134">Der **path** -Parameter bestimmt, wo das Paket gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="5eee9-134">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="5eee9-135">Beispiel 4: Speichern und Installieren des Pakets</span><span class="sxs-lookup"><span data-stu-id="5eee9-135">Example 4: Save and install the package</span></span>

<span data-ttu-id="5eee9-136">Die neueste Version des Pakets und seine Abhängigkeiten werden heruntergeladen und auf dem lokalen Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="5eee9-136">The newest version of the package and its dependencies are downloaded and installed on the local computer.</span></span>

```
PS> Save-Package -Name NuGet.Core -ProviderName NuGet -Path C:\LocalPkg
PS> Install-Package C:\LocalPkg\NuGet.Core.2.14.0.nupkg
```

<span data-ttu-id="5eee9-137">`Save-Package` Herunterladen der Paketdatei und ihrer Abhängigkeiten auf den lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="5eee9-137">`Save-Package` downloads the package file and its dependencies to the local computer.</span></span>
<span data-ttu-id="5eee9-138">`Install-Package` installiert das Paket und die Abhängigkeiten aus dem angegebenen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5eee9-138">`Install-Package` installs the package and dependencies from the specified directory.</span></span>

## <span data-ttu-id="5eee9-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5eee9-139">PARAMETERS</span></span>

### <span data-ttu-id="5eee9-140">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="5eee9-140">-AcceptLicense</span></span>

<span data-ttu-id="5eee9-141">Akzeptieren Sie den Lizenzvertrag während der Installation automatisch, wenn dies für das Paket erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5eee9-141">Automatically accept the license agreement during installation if the package requires it.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-142">-Allowprereleaseversions</span><span class="sxs-lookup"><span data-stu-id="5eee9-142">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="5eee9-143">Ermöglicht das Speichern von Paketen, die als Vorabversion markiert sind.</span><span class="sxs-lookup"><span data-stu-id="5eee9-143">Allows packages marked as Prerelease to be saved.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet, PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-144">-Allversions</span><span class="sxs-lookup"><span data-stu-id="5eee9-144">-AllVersions</span></span>

<span data-ttu-id="5eee9-145">Gibt an, dass dieses Cmdlet alle verfügbaren Versionen des Pakets speichert.</span><span class="sxs-lookup"><span data-stu-id="5eee9-145">Indicates that this cmdlet saves all available versions of the package.</span></span>

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

### <span data-ttu-id="5eee9-146">-Command</span><span class="sxs-lookup"><span data-stu-id="5eee9-146">-Command</span></span>

<span data-ttu-id="5eee9-147">Gibt einen oder mehrere Befehle an, die im Paket enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5eee9-147">Specifies one or more commands included in the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-148">-Configfile</span><span class="sxs-lookup"><span data-stu-id="5eee9-148">-ConfigFile</span></span>

<span data-ttu-id="5eee9-149">Gibt eine Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="5eee9-149">Specifies a configuration File.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-150">-Enthält</span><span class="sxs-lookup"><span data-stu-id="5eee9-150">-Contains</span></span>

<span data-ttu-id="5eee9-151">`Save-Package` Ruft Objekte ab, wenn ein beliebiges Element in den Eigenschafts Werten des Objekts eine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="5eee9-151">`Save-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-152">-Credential</span><span class="sxs-lookup"><span data-stu-id="5eee9-152">-Credential</span></span>

<span data-ttu-id="5eee9-153">Gibt ein Benutzerkonto an, das über die Berechtigung zum Speichern eines Pakets aus einem angegebenen Paketanbieter oder einer angegebenen Quelle verfügt.</span><span class="sxs-lookup"><span data-stu-id="5eee9-153">Specifies a user account that has permission to save a package from a specified package provider or source.</span></span>

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

### <span data-ttu-id="5eee9-154">-Dscresource</span><span class="sxs-lookup"><span data-stu-id="5eee9-154">-DscResource</span></span>

<span data-ttu-id="5eee9-155">Gibt mindestens eine DSC-Ressource (DSC) für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="5eee9-155">Specifies one or more Desired State Configuration (DSC) resources for the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-156">-Filter</span><span class="sxs-lookup"><span data-stu-id="5eee9-156">-Filter</span></span>

<span data-ttu-id="5eee9-157">Gibt einen Filter für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="5eee9-157">Specifies a filter for the package.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-158">-Filterontag</span><span class="sxs-lookup"><span data-stu-id="5eee9-158">-FilterOnTag</span></span>

<span data-ttu-id="5eee9-159">Gibt das Tag an, das die Ergebnisse filtert.</span><span class="sxs-lookup"><span data-stu-id="5eee9-159">Specifies the tag that filters the results.</span></span> <span data-ttu-id="5eee9-160">Ergebnisse, die das angegebene Tag nicht enthalten, werden ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5eee9-160">Results that don't contain the specified tag are excluded.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-161">-Force</span><span class="sxs-lookup"><span data-stu-id="5eee9-161">-Force</span></span>

<span data-ttu-id="5eee9-162">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="5eee9-162">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="5eee9-163">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="5eee9-163">-ForceBootstrap</span></span>

<span data-ttu-id="5eee9-164">Gibt an, dass `Save-Package` **packagemanagement** zwingt, den Paketanbieter automatisch für das angegebene Paket zu installieren.</span><span class="sxs-lookup"><span data-stu-id="5eee9-164">Indicates that `Save-Package` forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="5eee9-165">-Header</span><span class="sxs-lookup"><span data-stu-id="5eee9-165">-Headers</span></span>

<span data-ttu-id="5eee9-166">Gibt die Header für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="5eee9-166">Specifies the headers for the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-167">-Includes</span><span class="sxs-lookup"><span data-stu-id="5eee9-167">-Includes</span></span>

<span data-ttu-id="5eee9-168">Gibt die Ressourcen an, die das Paket enthält.</span><span class="sxs-lookup"><span data-stu-id="5eee9-168">Indicates the resources that the package includes.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:
Accepted values: DscResource, Cmdlet, Function, Workflow, RoleCapability

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-169">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5eee9-169">-InputObject</span></span>

<span data-ttu-id="5eee9-170">Ein Software-ID-Objekt, das das zu speichernde Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="5eee9-170">A software ID object that represents the package that you want to save.</span></span> <span data-ttu-id="5eee9-171">Software-IDs sind Teil der Ergebnisse des `Find-Package` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="5eee9-171">Software IDs are part of the results of the `Find-Package` cmdlet.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.SoftwareIdentity
Parameter Sets: PackageByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-172">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="5eee9-172">-LiteralPath</span></span>

<span data-ttu-id="5eee9-173">Gibt den literalpfad an, in dem Sie das Paket speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="5eee9-173">Specifies the literal path to which you want to save the package.</span></span> <span data-ttu-id="5eee9-174">Sie können diesen Parameter und den **path** -Parameter nicht demselben Befehl hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5eee9-174">You cannot add both this parameter and the **Path** parameter to the same command.</span></span>

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

### <span data-ttu-id="5eee9-175">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="5eee9-175">-MaximumVersion</span></span>

<span data-ttu-id="5eee9-176">Gibt die maximale Version des Pakets an, das Sie speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="5eee9-176">Specifies the maximum version of the package that you want to save.</span></span>

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

### <span data-ttu-id="5eee9-177">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="5eee9-177">-MinimumVersion</span></span>

<span data-ttu-id="5eee9-178">Gibt die Mindestversion des Pakets an, das Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="5eee9-178">Specifies the minimum version of the package that you want to find.</span></span>

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

### <span data-ttu-id="5eee9-179">-Name</span><span class="sxs-lookup"><span data-stu-id="5eee9-179">-Name</span></span>

<span data-ttu-id="5eee9-180">Gibt mindestens einen Paketnamen an.</span><span class="sxs-lookup"><span data-stu-id="5eee9-180">Specifies one or more package names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-181">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="5eee9-181">-PackageManagementProvider</span></span>

<span data-ttu-id="5eee9-182">Gibt einen Paket Verwaltungs Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="5eee9-182">Specifies a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-183">-Path</span><span class="sxs-lookup"><span data-stu-id="5eee9-183">-Path</span></span>

<span data-ttu-id="5eee9-184">Gibt den Speicherort auf dem lokalen Computer an, an dem das Paket gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5eee9-184">Specifies the location on the local computer to store the package.</span></span>

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

### <span data-ttu-id="5eee9-185">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="5eee9-185">-ProviderName</span></span>

<span data-ttu-id="5eee9-186">Gibt einen oder mehrere Anbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="5eee9-186">Specifies one or more provider names.</span></span>

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

### <span data-ttu-id="5eee9-187">-Proxy</span><span class="sxs-lookup"><span data-stu-id="5eee9-187">-Proxy</span></span>

<span data-ttu-id="5eee9-188">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="5eee9-188">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="5eee9-189">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="5eee9-189">-ProxyCredential</span></span>

<span data-ttu-id="5eee9-190">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5eee9-190">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="5eee9-191">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="5eee9-191">-PublishLocation</span></span>

<span data-ttu-id="5eee9-192">Gibt den Veröffentlichungs Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="5eee9-192">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-193">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="5eee9-193">-RequiredVersion</span></span>

<span data-ttu-id="5eee9-194">Gibt die genaue Version des Pakets an, das gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5eee9-194">Specifies the exact version of the package to save.</span></span>

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

### <span data-ttu-id="5eee9-195">-Rolecapability</span><span class="sxs-lookup"><span data-stu-id="5eee9-195">-RoleCapability</span></span>

<span data-ttu-id="5eee9-196">Gibt ein Array von Rollen Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="5eee9-196">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-197">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="5eee9-197">-ScriptPublishLocation</span></span>

<span data-ttu-id="5eee9-198">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="5eee9-198">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-199">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="5eee9-199">-ScriptSourceLocation</span></span>

<span data-ttu-id="5eee9-200">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="5eee9-200">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-201">-Skipvalidate</span><span class="sxs-lookup"><span data-stu-id="5eee9-201">-SkipValidate</span></span>

<span data-ttu-id="5eee9-202">Ein Schalter, der die Validierung der Anmelde Informationen eines Pakets überspringt.</span><span class="sxs-lookup"><span data-stu-id="5eee9-202">Switch that skips validating the credentials of a package.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-203">-Source</span><span class="sxs-lookup"><span data-stu-id="5eee9-203">-Source</span></span>

<span data-ttu-id="5eee9-204">Gibt mindestens eine Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="5eee9-204">Specifies one or more package sources.</span></span>

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

### <span data-ttu-id="5eee9-205">-Tag</span><span class="sxs-lookup"><span data-stu-id="5eee9-205">-Tag</span></span>

<span data-ttu-id="5eee9-206">Gibt ein Tag an, nach dem innerhalb der Paket Metadaten gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="5eee9-206">Specifies a tag to search for within the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-207">-Type</span><span class="sxs-lookup"><span data-stu-id="5eee9-207">-Type</span></span>

<span data-ttu-id="5eee9-208">Gibt an, ob nach Paketen mit einem Modul, einem Skript oder einer der beiden Optionen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="5eee9-208">Specifies whether to search for packages with a module, a script, or either.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eee9-209">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5eee9-209">-Confirm</span></span>

<span data-ttu-id="5eee9-210">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="5eee9-210">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5eee9-211">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5eee9-211">-WhatIf</span></span>

<span data-ttu-id="5eee9-212">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5eee9-212">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="5eee9-213">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5eee9-213">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5eee9-214">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5eee9-214">CommonParameters</span></span>

<span data-ttu-id="5eee9-215">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5eee9-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5eee9-216">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5eee9-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5eee9-217">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5eee9-217">INPUTS</span></span>

### <span data-ttu-id="5eee9-218">`Save-Package` akzeptiert Objekte aus der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="5eee9-218">`Save-Package` accepts objects from the pipeline.</span></span>

## <span data-ttu-id="5eee9-219">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5eee9-219">OUTPUTS</span></span>

### <span data-ttu-id="5eee9-220">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5eee9-220">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5eee9-221">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5eee9-221">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5eee9-222">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="5eee9-222">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="5eee9-223">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="5eee9-223">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="5eee9-224">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="5eee9-224">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="5eee9-225">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="5eee9-225">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="5eee9-226">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5eee9-226">RELATED LINKS</span></span>

[<span data-ttu-id="5eee9-227">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="5eee9-227">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="5eee9-228">Get-Package</span><span class="sxs-lookup"><span data-stu-id="5eee9-228">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="5eee9-229">Install-Package</span><span class="sxs-lookup"><span data-stu-id="5eee9-229">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="5eee9-230">Save-Package</span><span class="sxs-lookup"><span data-stu-id="5eee9-230">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="5eee9-231">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="5eee9-231">Uninstall-Package</span></span>](Uninstall-Package.md)
