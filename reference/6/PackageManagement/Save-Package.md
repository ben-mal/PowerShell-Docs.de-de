---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/save-package?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Package
ms.openlocfilehash: f94f1e3feba96aa49d44c25f2775ac9cffd0c459
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214815"
---
# <span data-ttu-id="b7b11-103">Save-Package</span><span class="sxs-lookup"><span data-stu-id="b7b11-103">Save-Package</span></span>

## <span data-ttu-id="b7b11-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b7b11-104">SYNOPSIS</span></span>
<span data-ttu-id="b7b11-105">Speichert Pakete auf dem lokalen Computer, ohne Sie zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b7b11-105">Saves packages to the local computer without installing them.</span></span>

## <span data-ttu-id="b7b11-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b7b11-106">SYNTAX</span></span>

### <span data-ttu-id="b7b11-107">Packagebysearch</span><span class="sxs-lookup"><span data-stu-id="b7b11-107">PackageBySearch</span></span>

```
Save-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Path <String>] [-LiteralPath <String>]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllVersions]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="b7b11-108">Packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="b7b11-108">PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] -InputObject <SoftwareIdentity>
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllVersions]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b7b11-109">Nuget: packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="b7b11-109">NuGet:PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>]
 [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="b7b11-110">NuGet</span><span class="sxs-lookup"><span data-stu-id="b7b11-110">NuGet</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>]
 [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="b7b11-111">PowerShellGet: packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="b7b11-111">PowerShellGet:PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AllowPrereleaseVersions] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [<CommonParameters>]
```

### <span data-ttu-id="b7b11-112">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="b7b11-112">PowerShellGet</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AllowPrereleaseVersions] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [<CommonParameters>]
```

## <span data-ttu-id="b7b11-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b7b11-113">DESCRIPTION</span></span>

<span data-ttu-id="b7b11-114">Mit dem- `Save-Package` Cmdlet werden Pakete auf dem lokalen Computer gespeichert, die Pakete werden jedoch nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="b7b11-114">The `Save-Package` cmdlet saves packages to the local computer but doesn't install the packages.</span></span>
<span data-ttu-id="b7b11-115">Dieses Cmdlet speichert die neueste Version eines Pakets, es sei denn, Sie geben eine "Requirements **dverion" an** .</span><span class="sxs-lookup"><span data-stu-id="b7b11-115">This cmdlet saves the newest version of a package unless you specify a **RequiredVerion** .</span></span> <span data-ttu-id="b7b11-116">Die **path** -und **literalpath** -Parameter schließen sich gegenseitig aus und können dem gleichen Befehl nicht hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b7b11-116">The **Path** and **LiteralPath** parameters are mutually exclusive, and cannot be added to the same command.</span></span>

## <span data-ttu-id="b7b11-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b7b11-117">EXAMPLES</span></span>

### <span data-ttu-id="b7b11-118">Beispiel 1: Speichern eines Pakets auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="b7b11-118">Example 1: Save a package to the local computer</span></span>

<span data-ttu-id="b7b11-119">In diesem Beispiel wird die neueste Version des Pakets in einem Verzeichnis auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b7b11-119">This example saves the newest version of the package to a directory on the local computer.</span></span> <span data-ttu-id="b7b11-120">Die Paketabhängigkeiten werden mit dem Paket heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="b7b11-120">The package's dependencies are download with the package.</span></span>

```
PS> Save-Package -Name NuGet.Core -ProviderName NuGet -Path C:\LocalPkg
```

```Output
Name                    Version    Source    Summary
----                    -------    ------    -------
Microsoft.Web.Xdt       3.0.0      Nuget     Microsoft Xml Document Transformation (XDT) enables...
NuGet.Core              2.14.0     Nuget     NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="b7b11-121">`Save-Package` verwendet den **Name** -Parameter, um das Paket anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b7b11-121">`Save-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="b7b11-122">Das Paket wird aus dem durch den **providerName** -Parameter angegebenen Repository heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="b7b11-122">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="b7b11-123">Der **path** -Parameter bestimmt, wo das Paket gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="b7b11-123">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="b7b11-124">Beispiel 2: Speichern einer bestimmten Paketversion</span><span class="sxs-lookup"><span data-stu-id="b7b11-124">Example 2: Save a specific package version</span></span>

<span data-ttu-id="b7b11-125">In diesem Beispiel wird die Paketversion angegeben und in einem Verzeichnis auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b7b11-125">This example specifies the package version and saves it to a directory on the local computer.</span></span>

```
PS> Save-Package -Name NuGet.Core -RequiredVersion 2.9.0 -ProviderName NuGet -Path C:\LocalPkg
```

```Output
Name                    Version    Source    Summary
----                    -------    ------    -------
Microsoft.Web.Xdt       3.0.0      Nuget     Microsoft Xml Document Transformation (XDT) enables...
NuGet.Core              2.9.0      Nuget     NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="b7b11-126">`Save-Package` verwendet den **Name** -Parameter, um das Paket anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b7b11-126">`Save-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="b7b11-127">Requirements **dversion** gibt eine bestimmte Paketversion an.</span><span class="sxs-lookup"><span data-stu-id="b7b11-127">**RequiredVersion** indicates a specific package version.</span></span> <span data-ttu-id="b7b11-128">Das Paket wird aus dem durch den **providerName** -Parameter angegebenen Repository heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="b7b11-128">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="b7b11-129">Der **path** -Parameter bestimmt, wo das Paket gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="b7b11-129">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="b7b11-130">Beispiel 3: Verwenden von Find-Package zum Speichern eines Pakets</span><span class="sxs-lookup"><span data-stu-id="b7b11-130">Example 3: Use Find-Package to save a package</span></span>

<span data-ttu-id="b7b11-131">Dieser Befehl verwendet `Find-Package` , um die neueste Version des Pakets zu suchen, und sendet das Objekt an `Save-Package` .</span><span class="sxs-lookup"><span data-stu-id="b7b11-131">This command uses `Find-Package` to locate the newest version of the package and sends the object to `Save-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -ProviderName NuGet | Save-Package -Path C:\LocalPkg
```

<span data-ttu-id="b7b11-132">`Find-Package` verwendet den **Name** -Parameter, um das Paket anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b7b11-132">`Find-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="b7b11-133">Das Paket wird aus dem durch den **providerName** -Parameter angegebenen Repository heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="b7b11-133">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="b7b11-134">Das Objekt wird über die Pipeline an gesendet `Save-Package` .</span><span class="sxs-lookup"><span data-stu-id="b7b11-134">The object is sent down the pipeline to `Save-Package`.</span></span> <span data-ttu-id="b7b11-135">Der **path** -Parameter bestimmt, wo das Paket gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="b7b11-135">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="b7b11-136">Beispiel 4: Speichern und Installieren des Pakets</span><span class="sxs-lookup"><span data-stu-id="b7b11-136">Example 4: Save and install the package</span></span>

<span data-ttu-id="b7b11-137">Die neueste Version des Pakets und seine Abhängigkeiten werden heruntergeladen und auf dem lokalen Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="b7b11-137">The newest version of the package and its dependencies are downloaded and installed on the local computer.</span></span>

```
PS> Save-Package -Name NuGet.Core -ProviderName NuGet -Path C:\LocalPkg
PS> Install-Package C:\LocalPkg\NuGet.Core.2.14.0.nupkg
```

<span data-ttu-id="b7b11-138">`Save-Package` Herunterladen der Paketdatei und ihrer Abhängigkeiten auf den lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="b7b11-138">`Save-Package` downloads the package file and its dependencies to the local computer.</span></span>
<span data-ttu-id="b7b11-139">`Install-Package` installiert das Paket und die Abhängigkeiten aus dem angegebenen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b7b11-139">`Install-Package` installs the package and dependencies from the specified directory.</span></span>

## <span data-ttu-id="b7b11-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b7b11-140">PARAMETERS</span></span>

### <span data-ttu-id="b7b11-141">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="b7b11-141">-AcceptLicense</span></span>

<span data-ttu-id="b7b11-142">Akzeptieren Sie den Lizenzvertrag während der Installation automatisch, wenn dies für das Paket erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b7b11-142">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="b7b11-143">-Allowprereleaseversions</span><span class="sxs-lookup"><span data-stu-id="b7b11-143">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="b7b11-144">Ermöglicht das Speichern von Paketen, die als Vorabversion markiert sind.</span><span class="sxs-lookup"><span data-stu-id="b7b11-144">Allows packages marked as Prerelease to be saved.</span></span>

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

### <span data-ttu-id="b7b11-145">-Allversions</span><span class="sxs-lookup"><span data-stu-id="b7b11-145">-AllVersions</span></span>

<span data-ttu-id="b7b11-146">Gibt an, dass dieses Cmdlet alle verfügbaren Versionen des Pakets speichert.</span><span class="sxs-lookup"><span data-stu-id="b7b11-146">Indicates that this cmdlet saves all available versions of the package.</span></span>

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

### <span data-ttu-id="b7b11-147">-Command</span><span class="sxs-lookup"><span data-stu-id="b7b11-147">-Command</span></span>

<span data-ttu-id="b7b11-148">Gibt einen oder mehrere Befehle an, die im Paket enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b7b11-148">Specifies one or more commands included in the package.</span></span>

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

### <span data-ttu-id="b7b11-149">-Configfile</span><span class="sxs-lookup"><span data-stu-id="b7b11-149">-ConfigFile</span></span>

<span data-ttu-id="b7b11-150">Gibt eine Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="b7b11-150">Specifies a configuration File.</span></span>

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

### <span data-ttu-id="b7b11-151">-Enthält</span><span class="sxs-lookup"><span data-stu-id="b7b11-151">-Contains</span></span>

<span data-ttu-id="b7b11-152">`Save-Package` Ruft Objekte ab, wenn ein beliebiges Element in den Eigenschafts Werten des Objekts eine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="b7b11-152">`Save-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

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

### <span data-ttu-id="b7b11-153">-Credential</span><span class="sxs-lookup"><span data-stu-id="b7b11-153">-Credential</span></span>

<span data-ttu-id="b7b11-154">Gibt ein Benutzerkonto an, das über die Berechtigung zum Speichern eines Pakets aus einem angegebenen Paketanbieter oder einer angegebenen Quelle verfügt.</span><span class="sxs-lookup"><span data-stu-id="b7b11-154">Specifies a user account that has permission to save a package from a specified package provider or source.</span></span>

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

### <span data-ttu-id="b7b11-155">-Dscresource</span><span class="sxs-lookup"><span data-stu-id="b7b11-155">-DscResource</span></span>

<span data-ttu-id="b7b11-156">Gibt mindestens eine DSC-Ressource (DSC) für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="b7b11-156">Specifies one or more Desired State Configuration (DSC) resources for the package.</span></span>

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

### <span data-ttu-id="b7b11-157">-Filter</span><span class="sxs-lookup"><span data-stu-id="b7b11-157">-Filter</span></span>

<span data-ttu-id="b7b11-158">Gibt einen Filter für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="b7b11-158">Specifies a filter for the package.</span></span>

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

### <span data-ttu-id="b7b11-159">-Filterontag</span><span class="sxs-lookup"><span data-stu-id="b7b11-159">-FilterOnTag</span></span>

<span data-ttu-id="b7b11-160">Gibt das Tag an, das die Ergebnisse filtert.</span><span class="sxs-lookup"><span data-stu-id="b7b11-160">Specifies the tag that filters the results.</span></span> <span data-ttu-id="b7b11-161">Ergebnisse, die das angegebene Tag nicht enthalten, werden ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b7b11-161">Results that don't contain the specified tag are excluded.</span></span>

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

### <span data-ttu-id="b7b11-162">-Force</span><span class="sxs-lookup"><span data-stu-id="b7b11-162">-Force</span></span>

<span data-ttu-id="b7b11-163">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b7b11-163">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="b7b11-164">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="b7b11-164">-ForceBootstrap</span></span>

<span data-ttu-id="b7b11-165">Gibt an, dass `Save-Package` **packagemanagement** zwingt, den Paketanbieter automatisch für das angegebene Paket zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b7b11-165">Indicates that `Save-Package` forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="b7b11-166">-Header</span><span class="sxs-lookup"><span data-stu-id="b7b11-166">-Headers</span></span>

<span data-ttu-id="b7b11-167">Gibt die Header für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="b7b11-167">Specifies the headers for the package.</span></span>

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

### <span data-ttu-id="b7b11-168">-Includes</span><span class="sxs-lookup"><span data-stu-id="b7b11-168">-Includes</span></span>

<span data-ttu-id="b7b11-169">Gibt die Ressourcen an, die das Paket enthält.</span><span class="sxs-lookup"><span data-stu-id="b7b11-169">Indicates the resources that the package includes.</span></span>

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

### <span data-ttu-id="b7b11-170">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b7b11-170">-InputObject</span></span>

<span data-ttu-id="b7b11-171">Ein Software-ID-Objekt, das das zu speichernde Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="b7b11-171">A software ID object that represents the package that you want to save.</span></span> <span data-ttu-id="b7b11-172">Software-IDs sind Teil der Ergebnisse des `Find-Package` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b7b11-172">Software IDs are part of the results of the `Find-Package` cmdlet.</span></span>

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

### <span data-ttu-id="b7b11-173">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="b7b11-173">-LiteralPath</span></span>

<span data-ttu-id="b7b11-174">Gibt den literalpfad an, in dem Sie das Paket speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="b7b11-174">Specifies the literal path to which you want to save the package.</span></span> <span data-ttu-id="b7b11-175">Sie können diesen Parameter und den **path** -Parameter nicht demselben Befehl hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b7b11-175">You cannot add both this parameter and the **Path** parameter to the same command.</span></span>

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

### <span data-ttu-id="b7b11-176">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="b7b11-176">-MaximumVersion</span></span>

<span data-ttu-id="b7b11-177">Gibt die maximale Version des Pakets an, das Sie speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="b7b11-177">Specifies the maximum version of the package that you want to save.</span></span>

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

### <span data-ttu-id="b7b11-178">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="b7b11-178">-MinimumVersion</span></span>

<span data-ttu-id="b7b11-179">Gibt die Mindestversion des Pakets an, das Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="b7b11-179">Specifies the minimum version of the package that you want to find.</span></span>

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

### <span data-ttu-id="b7b11-180">-Name</span><span class="sxs-lookup"><span data-stu-id="b7b11-180">-Name</span></span>

<span data-ttu-id="b7b11-181">Gibt mindestens einen Paketnamen an.</span><span class="sxs-lookup"><span data-stu-id="b7b11-181">Specifies one or more package names.</span></span>

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

### <span data-ttu-id="b7b11-182">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="b7b11-182">-PackageManagementProvider</span></span>

<span data-ttu-id="b7b11-183">Gibt einen Paket Verwaltungs Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="b7b11-183">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="b7b11-184">-Path</span><span class="sxs-lookup"><span data-stu-id="b7b11-184">-Path</span></span>

<span data-ttu-id="b7b11-185">Gibt den Speicherort auf dem lokalen Computer an, an dem das Paket gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b7b11-185">Specifies the location on the local computer to store the package.</span></span>

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

### <span data-ttu-id="b7b11-186">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="b7b11-186">-ProviderName</span></span>

<span data-ttu-id="b7b11-187">Gibt einen oder mehrere Anbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="b7b11-187">Specifies one or more provider names.</span></span>

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

### <span data-ttu-id="b7b11-188">-Proxy</span><span class="sxs-lookup"><span data-stu-id="b7b11-188">-Proxy</span></span>

<span data-ttu-id="b7b11-189">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="b7b11-189">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="b7b11-190">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="b7b11-190">-ProxyCredential</span></span>

<span data-ttu-id="b7b11-191">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b7b11-191">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="b7b11-192">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="b7b11-192">-PublishLocation</span></span>

<span data-ttu-id="b7b11-193">Gibt den Veröffentlichungs Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="b7b11-193">Specifies the publish location.</span></span>

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

### <span data-ttu-id="b7b11-194">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="b7b11-194">-RequiredVersion</span></span>

<span data-ttu-id="b7b11-195">Gibt die genaue Version des Pakets an, das gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b7b11-195">Specifies the exact version of the package to save.</span></span>

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

### <span data-ttu-id="b7b11-196">-Rolecapability</span><span class="sxs-lookup"><span data-stu-id="b7b11-196">-RoleCapability</span></span>

<span data-ttu-id="b7b11-197">Gibt ein Array von Rollen Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="b7b11-197">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="b7b11-198">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="b7b11-198">-ScriptPublishLocation</span></span>

<span data-ttu-id="b7b11-199">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="b7b11-199">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="b7b11-200">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="b7b11-200">-ScriptSourceLocation</span></span>

<span data-ttu-id="b7b11-201">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="b7b11-201">Specifies the script source location.</span></span>

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

### <span data-ttu-id="b7b11-202">-Skipvalidate</span><span class="sxs-lookup"><span data-stu-id="b7b11-202">-SkipValidate</span></span>

<span data-ttu-id="b7b11-203">Ein Schalter, der die Validierung der Anmelde Informationen eines Pakets überspringt.</span><span class="sxs-lookup"><span data-stu-id="b7b11-203">Switch that skips validating the credentials of a package.</span></span>

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

### <span data-ttu-id="b7b11-204">-Source</span><span class="sxs-lookup"><span data-stu-id="b7b11-204">-Source</span></span>

<span data-ttu-id="b7b11-205">Gibt mindestens eine Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="b7b11-205">Specifies one or more package sources.</span></span>

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

### <span data-ttu-id="b7b11-206">-Tag</span><span class="sxs-lookup"><span data-stu-id="b7b11-206">-Tag</span></span>

<span data-ttu-id="b7b11-207">Gibt ein Tag an, nach dem innerhalb der Paket Metadaten gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="b7b11-207">Specifies a tag to search for within the package metadata.</span></span>

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

### <span data-ttu-id="b7b11-208">-Type</span><span class="sxs-lookup"><span data-stu-id="b7b11-208">-Type</span></span>

<span data-ttu-id="b7b11-209">Gibt an, ob nach Paketen mit einem Modul, einem Skript oder einer der beiden Optionen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="b7b11-209">Specifies whether to search for packages with a module, a script, or either.</span></span>

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

### <span data-ttu-id="b7b11-210">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b7b11-210">-Confirm</span></span>

<span data-ttu-id="b7b11-211">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b7b11-211">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b7b11-212">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b7b11-212">-WhatIf</span></span>

<span data-ttu-id="b7b11-213">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b7b11-213">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b7b11-214">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7b11-214">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b7b11-215">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b7b11-215">CommonParameters</span></span>

<span data-ttu-id="b7b11-216">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b7b11-216">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b7b11-217">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b7b11-217">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b7b11-218">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b7b11-218">INPUTS</span></span>

### <span data-ttu-id="b7b11-219">`Save-Package` akzeptiert Objekte aus der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="b7b11-219">`Save-Package` accepts objects from the pipeline.</span></span>

## <span data-ttu-id="b7b11-220">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b7b11-220">OUTPUTS</span></span>

### <span data-ttu-id="b7b11-221">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="b7b11-221">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b7b11-222">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b7b11-222">NOTES</span></span>

## <span data-ttu-id="b7b11-223">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b7b11-223">RELATED LINKS</span></span>

[<span data-ttu-id="b7b11-224">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="b7b11-224">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="b7b11-225">Get-Package</span><span class="sxs-lookup"><span data-stu-id="b7b11-225">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="b7b11-226">Install-Package</span><span class="sxs-lookup"><span data-stu-id="b7b11-226">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="b7b11-227">Save-Package</span><span class="sxs-lookup"><span data-stu-id="b7b11-227">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="b7b11-228">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="b7b11-228">Uninstall-Package</span></span>](Uninstall-Package.md)
