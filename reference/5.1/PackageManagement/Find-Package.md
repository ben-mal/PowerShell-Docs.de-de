---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-package?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Package
ms.openlocfilehash: 71266e097524847502e9ce2e4e59c4908352c859
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213351"
---
# <span data-ttu-id="8de3c-103">Find-Package</span><span class="sxs-lookup"><span data-stu-id="8de3c-103">Find-Package</span></span>

## <span data-ttu-id="8de3c-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="8de3c-104">SYNOPSIS</span></span>
<span data-ttu-id="8de3c-105">Findet Softwarepakete in verfügbaren Paketquellen.</span><span class="sxs-lookup"><span data-stu-id="8de3c-105">Finds software packages in available package sources.</span></span>

## <span data-ttu-id="8de3c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8de3c-106">SYNTAX</span></span>

### <span data-ttu-id="8de3c-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="8de3c-107">NuGet</span></span>

```
Find-Package [-IncludeDependencies] [-AllVersions] [-Source <String[]>] [-Credential <PSCredential>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String[]>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>]
 [-FilterOnTag <String[]>] [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="8de3c-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="8de3c-108">PowerShellGet</span></span>

```
Find-Package [-IncludeDependencies] [-AllVersions] [-Source <String[]>] [-Credential <PSCredential>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String[]>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-AllowPrereleaseVersions] [-PackageManagementProvider <String>]
 [-PublishLocation <String>] [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>]
 [-Type <String>] [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>]
 [-DscResource <String[]>] [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense]
 [<CommonParameters>]
```

## <span data-ttu-id="8de3c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8de3c-109">DESCRIPTION</span></span>

<span data-ttu-id="8de3c-110">`Find-Package` findet Softwarepakete, die in Paketquellen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8de3c-110">`Find-Package` finds software packages that are available in package sources.</span></span> <span data-ttu-id="8de3c-111">`Get-PackageProvider` und `Get-PackageSource` zeigen Sie Details zu ihren Anbietern an.</span><span class="sxs-lookup"><span data-stu-id="8de3c-111">`Get-PackageProvider` and `Get-PackageSource` display details about your providers.</span></span>

## <span data-ttu-id="8de3c-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8de3c-112">EXAMPLES</span></span>

### <span data-ttu-id="8de3c-113">Beispiel 1: Suchen aller verfügbaren Pakete von einem Paketanbieter</span><span class="sxs-lookup"><span data-stu-id="8de3c-113">Example 1: Find all available packages from a package provider</span></span>

<span data-ttu-id="8de3c-114">Mit diesem Befehl werden alle verfügbaren PowerShell-Modul Pakete in einem registrierten Katalog gefunden.</span><span class="sxs-lookup"><span data-stu-id="8de3c-114">This command finds all available PowerShell module packages in a registered gallery.</span></span> <span data-ttu-id="8de3c-115">Verwenden `Get-PackageProvider` Sie, um den Anbieter Namen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8de3c-115">Use `Get-PackageProvider` to get the provider name.</span></span>

```
Find-Package -ProviderName NuGet
```

```Output
Name               Version   Source     Summary
----               -------   ------     -------
NUnit              3.11.0    MyNuGet    NUnit is a unit-testing framework for all .NET langua...
Newtonsoft.Json    12.0.1    MyNuGet    Json.NET is a popular high-performance JSON framework...
EntityFramework    6.2.0     MyNuGet    Entity Framework is Microsoft's recommended data acce...
MySql.Data         8.0.15    MyNuGet    MySql.Data.MySqlClient .Net Core Class Library
bootstrap          4.3.1     MyNuGet    Bootstrap framework in CSS. Includes fonts and JavaSc...
NuGet.Core         2.14.0    MyNuGet    NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="8de3c-116">`Find-Package` verwendet den **Provider** -Parameter, um den **nuget** -Anbieter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8de3c-116">`Find-Package` uses the **Provider** parameter to specify the provider **NuGet** .</span></span>

### <span data-ttu-id="8de3c-117">Beispiel 2: Suchen eines Pakets aus einer Paketquelle</span><span class="sxs-lookup"><span data-stu-id="8de3c-117">Example 2: Find a package from a package source</span></span>

<span data-ttu-id="8de3c-118">Dieser Befehl sucht die neueste Version eines Pakets aus einer angegebenen Paketquelle.</span><span class="sxs-lookup"><span data-stu-id="8de3c-118">This command finds the newest version of a package from a specified package source.</span></span> <span data-ttu-id="8de3c-119">Wenn keine Paketquelle bereitgestellt wird, `Find-Package` durchsucht die einzelnen installierten Paketanbieter und die zugehörigen Paketquellen.</span><span class="sxs-lookup"><span data-stu-id="8de3c-119">If a package source isn't provided, `Find-Package` searches each installed package provider and its package sources.</span></span> <span data-ttu-id="8de3c-120">Verwenden `Get-PackageSource` Sie, um den Quellnamen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8de3c-120">Use `Get-PackageSource` to get the source name.</span></span>

```
Find-Package -Name NuGet.Core -Source MyNuGet
```

```Output
Name         Version   Source    Summary
----         -------   ------    -------
NuGet.Core   2.14.0    MyNuGet   NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="8de3c-121">`Find-Package` verwendet den **Name** -Parameter, um den Paketnamen " **nuget. Core** " anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8de3c-121">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core** .</span></span> <span data-ttu-id="8de3c-122">Der **Source** -Parameter gibt an, dass in **mynuget** nach dem Paket gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="8de3c-122">The **Source** parameter specifies to search for the package in **MyNuGet** .</span></span>

### <span data-ttu-id="8de3c-123">Beispiel 3: Suchen aller Versionen eines Pakets</span><span class="sxs-lookup"><span data-stu-id="8de3c-123">Example 3: Find all versions of a package</span></span>

<span data-ttu-id="8de3c-124">Mit diesem Befehl werden alle verfügbaren Paketversionen von einem angegebenen Anbieter ermittelt.</span><span class="sxs-lookup"><span data-stu-id="8de3c-124">This command finds all available package versions from a specified provider.</span></span>

```
Find-Package -Name NuGet.Core -Source MyNuGet -AllVersions
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.14.0           MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.14.0-rtm-832   MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.13.0           MyNuGet      NuGet.Core is the core framework assembly for NuGet...
...
NuGet.Core    1.1.229.159      MyNuGet      NuGet.Core is the core framework assembly for NuGet...
Nuget.Core    1.0.1120.104     MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="8de3c-125">`Find-Package` verwendet den **Name** -Parameter, um das **nuget. Core** -Paket anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8de3c-125">`Find-Package` uses the **Name** parameter to specify the package **NuGet.Core** .</span></span> <span data-ttu-id="8de3c-126">Der **providerName** -Parameter gibt an, dass in **mynuget** nach dem Paket gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="8de3c-126">The **ProviderName** parameter specifies to search for the package in **MyNuGet** .</span></span> <span data-ttu-id="8de3c-127">**Allversions** gibt an, dass alle verfügbaren Versionen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8de3c-127">**AllVersions** specifies that all available versions are returned.</span></span>

### <span data-ttu-id="8de3c-128">Beispiel 4: Suchen eines Pakets mit einem bestimmten Namen und einer bestimmten Version</span><span class="sxs-lookup"><span data-stu-id="8de3c-128">Example 4: Find a package with a specific name and version</span></span>

<span data-ttu-id="8de3c-129">Dieser Befehl sucht eine bestimmte Paketversion von einem angegebenen Anbieter.</span><span class="sxs-lookup"><span data-stu-id="8de3c-129">This command finds a specific package version from a specified provider.</span></span>

```
Find-Package -Name NuGet.Core -ProviderName NuGet -RequiredVersion 2.9.0
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.9.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="8de3c-130">`Find-Package` verwendet den **Name** -Parameter, um den Paketnamen " **nuget. Core** " anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8de3c-130">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core** .</span></span> <span data-ttu-id="8de3c-131">Der **providerName** -Parameter gibt an, dass in **nuget** nach dem Paket gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="8de3c-131">The **ProviderName** parameter specifies to search for the package in **NuGet** .</span></span> <span data-ttu-id="8de3c-132">Requirements **dversion** gibt an, dass nur Version **2.9.0** zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8de3c-132">**RequiredVersion** specifies that only version **2.9.0** is returned.</span></span>

### <span data-ttu-id="8de3c-133">Beispiel 5: Suchen nach Paketen innerhalb eines Bereichs von Versionen</span><span class="sxs-lookup"><span data-stu-id="8de3c-133">Example 5: Find packages within a range of versions</span></span>

<span data-ttu-id="8de3c-134">Dieser Befehl sucht einen Bereich von Versionen für ein angegebenes Paket.</span><span class="sxs-lookup"><span data-stu-id="8de3c-134">This command finds a range of versions for a specified package.</span></span>

```
Find-Package -Name NuGet.Core -ProviderName NuGet -MinimumVersion 2.7.0 -MaximumVersion 2.9.0 -AllVersions
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.9.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.8.6            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.8.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.7.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="8de3c-135">`Find-Package` verwendet den **Name** -Parameter, um den Paketnamen " **nuget. Core** " anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8de3c-135">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core** .</span></span> <span data-ttu-id="8de3c-136">Der **providerName** -Parameter gibt an, dass in **nuget** nach dem Paket gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="8de3c-136">The **ProviderName** parameter specifies to search for the package in **NuGet** .</span></span> <span data-ttu-id="8de3c-137">**MinimumVersion** gibt die niedrigste Version an **2.7.0** an.</span><span class="sxs-lookup"><span data-stu-id="8de3c-137">**MinimumVersion** specifies the lowest version **2.7.0** .</span></span> <span data-ttu-id="8de3c-138">**MaximumVersion** gibt die höchste Version an **2.9.0** an.</span><span class="sxs-lookup"><span data-stu-id="8de3c-138">**MaximumVersion** specifies the highest version **2.9.0** .</span></span>
<span data-ttu-id="8de3c-139">**Allversions** gibt an, dass der Bereich gemäß dem minimal-und Maximalwert zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8de3c-139">**AllVersions** determines the range is returned as specified by the minimum and maximum.</span></span>

### <span data-ttu-id="8de3c-140">Beispiel 6: Suchen eines Pakets aus einem Dateisystem</span><span class="sxs-lookup"><span data-stu-id="8de3c-140">Example 6: Find a package from a file system</span></span>

<span data-ttu-id="8de3c-141">Dieser Befehl sucht Pakete mit der Dateierweiterung `.nupkg` , die auf dem lokalen Computer gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="8de3c-141">This command finds packages with the file extension `.nupkg` that are stored on the local computer.</span></span>
<span data-ttu-id="8de3c-142">Bei den Dateien handelt es sich um Pakete, die aus einem Katalog wie **nuget** heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="8de3c-142">The files are packages downloaded from a gallery such as the **NuGet** .</span></span>

```
PS> Find-Package -Source C:\LocalPkg
```

```Output
Name                 Version    Source           Summary
----                 -------    ------           -------
Microsoft.Web.Xdt    3.0.0      C:\LocalPkg\     Microsoft Xml Document Transformation (XDT)...
NuGet.Core           2.14.0     C:\LocalPkg\     NuGet.Core is the core framework assembly...
```

## <span data-ttu-id="8de3c-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8de3c-143">PARAMETERS</span></span>

### <span data-ttu-id="8de3c-144">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="8de3c-144">-AcceptLicense</span></span>

<span data-ttu-id="8de3c-145">Akzeptiert automatisch einen Lizenzvertrag, wenn dies für das Paket erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8de3c-145">Automatically accepts a license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="8de3c-146">-Allowprereleaseversions</span><span class="sxs-lookup"><span data-stu-id="8de3c-146">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="8de3c-147">Schließt Pakete ein, die in den Ergebnissen als Vorabversion gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="8de3c-147">Includes packages marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="8de3c-148">-Allversions</span><span class="sxs-lookup"><span data-stu-id="8de3c-148">-AllVersions</span></span>

<span data-ttu-id="8de3c-149">Gibt an, dass `Find-Package` alle verfügbaren Versionen des Pakets zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8de3c-149">Indicates that `Find-Package` returns all available versions of the package.</span></span> <span data-ttu-id="8de3c-150">Standardmäßig wird `Find-Package` nur die neueste verfügbare Version zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8de3c-150">By default, `Find-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="8de3c-151">-Command</span><span class="sxs-lookup"><span data-stu-id="8de3c-151">-Command</span></span>

<span data-ttu-id="8de3c-152">Gibt ein Array von Befehlen an, die von gesucht werden `Find-Package` .</span><span class="sxs-lookup"><span data-stu-id="8de3c-152">Specifies an array of commands searched by `Find-Package`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8de3c-153">-Configfile</span><span class="sxs-lookup"><span data-stu-id="8de3c-153">-ConfigFile</span></span>

<span data-ttu-id="8de3c-154">Gibt eine Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="8de3c-154">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="8de3c-155">-Enthält</span><span class="sxs-lookup"><span data-stu-id="8de3c-155">-Contains</span></span>

<span data-ttu-id="8de3c-156">`Find-Package` Ruft Objekte ab, wenn ein beliebiges Element in den Eigenschafts Werten des Objekts eine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="8de3c-156">`Find-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

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

### <span data-ttu-id="8de3c-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="8de3c-157">-Credential</span></span>

<span data-ttu-id="8de3c-158">Gibt ein Benutzerkonto an, das über die Berechtigung zum Suchen nach Paketen verfügt.</span><span class="sxs-lookup"><span data-stu-id="8de3c-158">Specifies a user account that has permission to search for packages.</span></span>

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

### <span data-ttu-id="8de3c-159">-Dscresource</span><span class="sxs-lookup"><span data-stu-id="8de3c-159">-DscResource</span></span>

<span data-ttu-id="8de3c-160">Gibt ein Array von DSC-Ressourcen (DSC) an, die von diesem Cmdlet durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="8de3c-160">Specifies an array of Desired State Configuration (DSC) resources that this cmdlet searches.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8de3c-161">-Filter</span><span class="sxs-lookup"><span data-stu-id="8de3c-161">-Filter</span></span>

<span data-ttu-id="8de3c-162">Gibt die Begriffe an, nach denen in den Eigenschaften **Name** und **Description** gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="8de3c-162">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

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

### <span data-ttu-id="8de3c-163">-Filterontag</span><span class="sxs-lookup"><span data-stu-id="8de3c-163">-FilterOnTag</span></span>

<span data-ttu-id="8de3c-164">Gibt das Tag an, das die Ergebnisse filtert.</span><span class="sxs-lookup"><span data-stu-id="8de3c-164">Specifies the tag that filters the results.</span></span> <span data-ttu-id="8de3c-165">Ergebnisse, die das angegebene Tag nicht enthalten, werden ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8de3c-165">Results that don't contain the specified tag are excluded.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8de3c-166">-Force</span><span class="sxs-lookup"><span data-stu-id="8de3c-166">-Force</span></span>

<span data-ttu-id="8de3c-167">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8de3c-167">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="8de3c-168">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="8de3c-168">-ForceBootstrap</span></span>

<span data-ttu-id="8de3c-169">Gibt an, dass `Find-Package` **packagemanagement** zwingt, den Paketanbieter automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="8de3c-169">Indicates that `Find-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="8de3c-170">-Header</span><span class="sxs-lookup"><span data-stu-id="8de3c-170">-Headers</span></span>

<span data-ttu-id="8de3c-171">Gibt die Header für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="8de3c-171">Specifies the headers for the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8de3c-172">-Includababhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="8de3c-172">-IncludeDependencies</span></span>

<span data-ttu-id="8de3c-173">Gibt an, dass dieses Cmdlet Paketabhängigkeiten in den Ergebnissen enthält.</span><span class="sxs-lookup"><span data-stu-id="8de3c-173">Indicates that this cmdlet includes package dependencies in the results.</span></span>

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

### <span data-ttu-id="8de3c-174">-Includes</span><span class="sxs-lookup"><span data-stu-id="8de3c-174">-Includes</span></span>

<span data-ttu-id="8de3c-175">Gibt an, ob `Find-Package` alle Pakete innerhalb einer Kategorie finden soll.</span><span class="sxs-lookup"><span data-stu-id="8de3c-175">Specifies whether `Find-Package` should find all packages within a category.</span></span>

<span data-ttu-id="8de3c-176">Die zulässigen Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8de3c-176">The accepted values are as follows:</span></span>

- <span data-ttu-id="8de3c-177">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8de3c-177">Cmdlet</span></span>
- <span data-ttu-id="8de3c-178">DscResource</span><span class="sxs-lookup"><span data-stu-id="8de3c-178">DscResource</span></span>
- <span data-ttu-id="8de3c-179">Funktion</span><span class="sxs-lookup"><span data-stu-id="8de3c-179">Function</span></span>
- <span data-ttu-id="8de3c-180">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="8de3c-180">RoleCapability</span></span>
- <span data-ttu-id="8de3c-181">Workflow</span><span class="sxs-lookup"><span data-stu-id="8de3c-181">Workflow</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:
Accepted values: Cmdlet, DscResource, Function, RoleCapability, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8de3c-182">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="8de3c-182">-MaximumVersion</span></span>

<span data-ttu-id="8de3c-183">Gibt die maximale Paketversion an, die Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="8de3c-183">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="8de3c-184">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="8de3c-184">-MinimumVersion</span></span>

<span data-ttu-id="8de3c-185">Gibt die minimale Paketversion an, die Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="8de3c-185">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="8de3c-186">Wenn eine höhere Version verfügbar ist, wird diese Version zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8de3c-186">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="8de3c-187">-Name</span><span class="sxs-lookup"><span data-stu-id="8de3c-187">-Name</span></span>

<span data-ttu-id="8de3c-188">Gibt einen oder mehrere Paketnamen oder Paketnamen mit Platzhalter Zeichen an.</span><span class="sxs-lookup"><span data-stu-id="8de3c-188">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="8de3c-189">Trennen Sie mehrere Paketnamen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="8de3c-189">Separate multiple package names with commas.</span></span>

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

### <span data-ttu-id="8de3c-190">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="8de3c-190">-PackageManagementProvider</span></span>

<span data-ttu-id="8de3c-191">Gibt den Namen eines Paket Verwaltungs Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="8de3c-191">Specifies the name of a package management provider.</span></span>

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

### <span data-ttu-id="8de3c-192">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="8de3c-192">-ProviderName</span></span>

<span data-ttu-id="8de3c-193">Gibt einen oder mehrere Paketanbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="8de3c-193">Specifies one or more package provider names.</span></span> <span data-ttu-id="8de3c-194">Trennen Sie mehrere Paketanbieter Namen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="8de3c-194">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="8de3c-195">Verwenden `Get-PackageProvider` Sie, um eine Liste der verfügbaren Paketanbieter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8de3c-195">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="8de3c-196">-Proxy</span><span class="sxs-lookup"><span data-stu-id="8de3c-196">-Proxy</span></span>

<span data-ttu-id="8de3c-197">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="8de3c-197">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="8de3c-198">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="8de3c-198">-ProxyCredential</span></span>

<span data-ttu-id="8de3c-199">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8de3c-199">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="8de3c-200">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="8de3c-200">-PublishLocation</span></span>

<span data-ttu-id="8de3c-201">Gibt einen Speicherort für die Veröffentlichung des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="8de3c-201">Specifies a location for publishing the package.</span></span>

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

### <span data-ttu-id="8de3c-202">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="8de3c-202">-RequiredVersion</span></span>

<span data-ttu-id="8de3c-203">Gibt eine genaue Paketversion an, die Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="8de3c-203">Specifies an exact package version that you want to find.</span></span>

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

### <span data-ttu-id="8de3c-204">-Rolecapability</span><span class="sxs-lookup"><span data-stu-id="8de3c-204">-RoleCapability</span></span>

<span data-ttu-id="8de3c-205">Gibt ein Array von Rollen Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="8de3c-205">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8de3c-206">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="8de3c-206">-ScriptPublishLocation</span></span>

<span data-ttu-id="8de3c-207">Gibt einen Speicherort für die Skript Veröffentlichung für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="8de3c-207">Specifies a script publishing location for the package.</span></span>

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

### <span data-ttu-id="8de3c-208">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="8de3c-208">-ScriptSourceLocation</span></span>

<span data-ttu-id="8de3c-209">Gibt einen Skript Quell Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="8de3c-209">Specifies a script source location.</span></span>

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

### <span data-ttu-id="8de3c-210">-Skipvalidate</span><span class="sxs-lookup"><span data-stu-id="8de3c-210">-SkipValidate</span></span>

<span data-ttu-id="8de3c-211">Der Schalter, der die Überprüfung der Paket Anmelde Informationen überspringt.</span><span class="sxs-lookup"><span data-stu-id="8de3c-211">Switch that skips package credential validation.</span></span>

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

### <span data-ttu-id="8de3c-212">-Source</span><span class="sxs-lookup"><span data-stu-id="8de3c-212">-Source</span></span>

<span data-ttu-id="8de3c-213">Gibt mindestens eine Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="8de3c-213">Specifies one or more package sources.</span></span> <span data-ttu-id="8de3c-214">Verwenden `Get-PackageSource` Sie, um eine Liste der verfügbaren Paketquellen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8de3c-214">Use `Get-PackageSource` to get a list of available package sources.</span></span> <span data-ttu-id="8de3c-215">Ein Dateisystem Verzeichnis kann als Quelle für Download Pakete verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8de3c-215">A file system directory can be used as a source for download packages.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8de3c-216">-Tag</span><span class="sxs-lookup"><span data-stu-id="8de3c-216">-Tag</span></span>

<span data-ttu-id="8de3c-217">Gibt eine oder mehrere Zeichen folgen an, die in den Paket Metadaten gesucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8de3c-217">Specifies one or more strings to search for in the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8de3c-218">-Type</span><span class="sxs-lookup"><span data-stu-id="8de3c-218">-Type</span></span>

<span data-ttu-id="8de3c-219">Gibt an, ob nach Paketen mit einem Modul, einem Skript oder einer der beiden Optionen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="8de3c-219">Specifies whether to search for packages with a module, a script, or either.</span></span>

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

### <span data-ttu-id="8de3c-220">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8de3c-220">CommonParameters</span></span>

<span data-ttu-id="8de3c-221">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8de3c-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8de3c-222">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8de3c-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8de3c-223">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="8de3c-223">INPUTS</span></span>

### <span data-ttu-id="8de3c-224">Keine</span><span class="sxs-lookup"><span data-stu-id="8de3c-224">None</span></span>

<span data-ttu-id="8de3c-225">`Find-Package` akzeptiert keine Eingaben aus der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="8de3c-225">`Find-Package` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="8de3c-226">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="8de3c-226">OUTPUTS</span></span>

### <span data-ttu-id="8de3c-227">Softwareidentify []</span><span class="sxs-lookup"><span data-stu-id="8de3c-227">SoftwareIdentify[]</span></span>

<span data-ttu-id="8de3c-228">`Find-Package` Gibt ein **softwareidentity** -Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="8de3c-228">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

## <span data-ttu-id="8de3c-229">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="8de3c-229">NOTES</span></span>

## <span data-ttu-id="8de3c-230">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="8de3c-230">RELATED LINKS</span></span>

[<span data-ttu-id="8de3c-231">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="8de3c-231">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="8de3c-232">Get-Package</span><span class="sxs-lookup"><span data-stu-id="8de3c-232">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="8de3c-233">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="8de3c-233">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="8de3c-234">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8de3c-234">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="8de3c-235">Install-Package</span><span class="sxs-lookup"><span data-stu-id="8de3c-235">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="8de3c-236">Save-Package</span><span class="sxs-lookup"><span data-stu-id="8de3c-236">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="8de3c-237">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="8de3c-237">Uninstall-Package</span></span>](Uninstall-Package.md)
