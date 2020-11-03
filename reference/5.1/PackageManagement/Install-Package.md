---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 05/23/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-package?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Package
ms.openlocfilehash: 058ed7f90e63bd7ca7a29cf6c89864a30255662a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213292"
---
# <span data-ttu-id="03d3e-103">Install-Package</span><span class="sxs-lookup"><span data-stu-id="03d3e-103">Install-Package</span></span>

## <span data-ttu-id="03d3e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="03d3e-104">SYNOPSIS</span></span>
<span data-ttu-id="03d3e-105">Installiert mindestens ein Softwarepaket.</span><span class="sxs-lookup"><span data-stu-id="03d3e-105">Installs one or more software packages.</span></span>

## <span data-ttu-id="03d3e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="03d3e-106">SYNTAX</span></span>

### <span data-ttu-id="03d3e-107">Packagebysearch (Standard)</span><span class="sxs-lookup"><span data-stu-id="03d3e-107">PackageBySearch (Default)</span></span>

```
Install-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="03d3e-108">Packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="03d3e-108">PackageByInputObject</span></span>

```
Install-Package [-InputObject] <SoftwareIdentity[]> [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="03d3e-109">Programme: packagebysearch</span><span class="sxs-lookup"><span data-stu-id="03d3e-109">Programs:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-IncludeWindowsInstaller]
 [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="03d3e-110">Programme: packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="03d3e-110">Programs:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-IncludeWindowsInstaller]
 [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="03d3e-111">MSI: packagebysearch</span><span class="sxs-lookup"><span data-stu-id="03d3e-111">msi:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AdditionalArguments <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="03d3e-112">MSI: packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="03d3e-112">msi:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AdditionalArguments <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="03d3e-113">Nuget: packagebysearch</span><span class="sxs-lookup"><span data-stu-id="03d3e-113">NuGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="03d3e-114">Nuget: packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="03d3e-114">NuGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="03d3e-115">PowerShellGet: packagebysearch</span><span class="sxs-lookup"><span data-stu-id="03d3e-115">PowerShellGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

### <span data-ttu-id="03d3e-116">PowerShellGet: packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="03d3e-116">PowerShellGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

## <span data-ttu-id="03d3e-117">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="03d3e-117">DESCRIPTION</span></span>

<span data-ttu-id="03d3e-118">Mit dem- `Install-Package` Cmdlet wird mindestens ein Softwarepaket auf dem lokalen Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="03d3e-118">The `Install-Package` cmdlet installs one or more software packages on the local computer.</span></span> <span data-ttu-id="03d3e-119">Wenn Sie über mehrere Software Quellen verfügen, verwenden Sie `Get-PackageProvider` und, `Get-PackageSource` um Details zu ihren Anbietern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="03d3e-119">If you have multiple software sources, use `Get-PackageProvider` and `Get-PackageSource` to display details about your providers.</span></span>

## <span data-ttu-id="03d3e-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="03d3e-120">EXAMPLES</span></span>

### <span data-ttu-id="03d3e-121">Beispiel 1: Installieren eines Pakets nach Paketname</span><span class="sxs-lookup"><span data-stu-id="03d3e-121">Example 1: Install a package by package name</span></span>

<span data-ttu-id="03d3e-122">Mit dem `Install-Package` -Cmdlet werden ein Softwarepaket und seine Abhängigkeiten installiert.</span><span class="sxs-lookup"><span data-stu-id="03d3e-122">The `Install-Package` cmdlet installs a software package and its dependencies.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -Credential Contoso\TestUser
```

<span data-ttu-id="03d3e-123">`Install-Package` verwendet Parameter, um den **Namen** und die **Quelle** des Pakets anzugeben.</span><span class="sxs-lookup"><span data-stu-id="03d3e-123">`Install-Package` uses parameters to specify the packages **Name** and **Source** .</span></span> <span data-ttu-id="03d3e-124">Der **Credential** -Parameter verwendet ein Domänen Benutzerkonto mit Berechtigungen zum Installieren von Paketen.</span><span class="sxs-lookup"><span data-stu-id="03d3e-124">The **Credential** parameter uses a domain user account with permissions to install packages.</span></span> <span data-ttu-id="03d3e-125">Der Befehl fordert Sie zur Eingabe des Kennworts für das Benutzerkonto auf.</span><span class="sxs-lookup"><span data-stu-id="03d3e-125">The command prompts you for the user account password.</span></span>

### <span data-ttu-id="03d3e-126">Beispiel 2: Verwenden von Find-Package zum Installieren eines Pakets</span><span class="sxs-lookup"><span data-stu-id="03d3e-126">Example 2: Use Find-Package to install a package</span></span>

<span data-ttu-id="03d3e-127">In diesem Beispiel wird das von zurückgegebene `Find-Package` -Objekt über die Pipeline gesendet und von installiert `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="03d3e-127">In this example, the object returned by `Find-Package` is sent down the pipeline and installed by `Install-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -Source MyNuGet | Install-Package
```

<span data-ttu-id="03d3e-128">`Find-Package` verwendet den **Name** -Parameter und den **Quell** Parameter, um ein Paket zu suchen.</span><span class="sxs-lookup"><span data-stu-id="03d3e-128">`Find-Package` uses the **Name** and **Source** parameters to locate a package.</span></span> <span data-ttu-id="03d3e-129">Das Objekt wird über die Pipeline gesendet und `Install-Package` installiert das Paket auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="03d3e-129">The object is sent down the pipeline and `Install-Package` installs the package on the local computer.</span></span>

### <span data-ttu-id="03d3e-130">Beispiel 3: Installieren von Paketen durch Angeben eines Bereichs von Versionen</span><span class="sxs-lookup"><span data-stu-id="03d3e-130">Example 3: Install packages by specifying a range of versions</span></span>

<span data-ttu-id="03d3e-131">`Install-Package` verwendet die Parameter **MinimumVersion** und **MaximumVersion** , um einen Bereich von Softwareversionen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="03d3e-131">`Install-Package` uses the **MinimumVersion** and **MaximumVersion** parameters to specify a range of software versions.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -MinimumVersion 2.8.0 -MaximumVersion 2.9.0
```

<span data-ttu-id="03d3e-132">`Install-Package` verwendet den **Name** -Parameter und den **Quell** Parameter, um ein Paket zu suchen.</span><span class="sxs-lookup"><span data-stu-id="03d3e-132">`Install-Package` uses the **Name** and **Source** parameters to find a package.</span></span> <span data-ttu-id="03d3e-133">Mit den Parametern **MinimumVersion** und **MaximumVersion** wird ein Bereich von Softwareversionen angegeben.</span><span class="sxs-lookup"><span data-stu-id="03d3e-133">The **MinimumVersion** and **MaximumVersion** parameters specify a range of software versions.</span></span> <span data-ttu-id="03d3e-134">Die höchste Version im Bereich ist installiert.</span><span class="sxs-lookup"><span data-stu-id="03d3e-134">The highest version in the range is installed.</span></span>

## <span data-ttu-id="03d3e-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="03d3e-135">PARAMETERS</span></span>

### <span data-ttu-id="03d3e-136">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="03d3e-136">-AcceptLicense</span></span>

 <span data-ttu-id="03d3e-137">" **Accept License** " akzeptiert den Lizenzvertrag während der Installation automatisch.</span><span class="sxs-lookup"><span data-stu-id="03d3e-137">**AcceptLicense** automatically accepts the license agreement during installation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-138">-Allowclobber</span><span class="sxs-lookup"><span data-stu-id="03d3e-138">-AllowClobber</span></span>

<span data-ttu-id="03d3e-139">Überschreibt Warnmeldungen zu Konflikten mit vorhandenen Befehlen.</span><span class="sxs-lookup"><span data-stu-id="03d3e-139">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="03d3e-140">Überschreibt vorhandene Befehle, die denselben Namen wie die Befehle aufweisen, die installiert werden.</span><span class="sxs-lookup"><span data-stu-id="03d3e-140">Overwrites existing commands that have the same name as commands being installed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-141">-Allowprereleaseversions</span><span class="sxs-lookup"><span data-stu-id="03d3e-141">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="03d3e-142">Ermöglicht die Installation von Paketen, die als Vorabversion markiert sind.</span><span class="sxs-lookup"><span data-stu-id="03d3e-142">Allows the installation of packages marked as prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject, PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-143">-Allversions</span><span class="sxs-lookup"><span data-stu-id="03d3e-143">-AllVersions</span></span>

<span data-ttu-id="03d3e-144">`Install-Package` installiert alle verfügbaren Versionen des Pakets.</span><span class="sxs-lookup"><span data-stu-id="03d3e-144">`Install-Package` installs all available versions of the package.</span></span> <span data-ttu-id="03d3e-145">Standardmäßig wird nur die neueste Version installiert.</span><span class="sxs-lookup"><span data-stu-id="03d3e-145">By default, only the newest version is installed.</span></span>

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

### <span data-ttu-id="03d3e-146">-Command</span><span class="sxs-lookup"><span data-stu-id="03d3e-146">-Command</span></span>

<span data-ttu-id="03d3e-147">Gibt einen oder mehrere Befehle an, die `Install-Package` durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="03d3e-147">Specifies one or more commands that `Install-Package` searches.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-148">-Configfile</span><span class="sxs-lookup"><span data-stu-id="03d3e-148">-ConfigFile</span></span>

<span data-ttu-id="03d3e-149">Gibt einen Pfad an, der eine Konfigurationsdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="03d3e-149">Specifies a path that contains a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-150">-Enthält</span><span class="sxs-lookup"><span data-stu-id="03d3e-150">-Contains</span></span>

<span data-ttu-id="03d3e-151">`Install-Package` Ruft Objekte ab, wenn der **enthält** -Parameter einen Wert angibt, der mit den Eigenschafts Werten des-Objekts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="03d3e-151">`Install-Package` gets objects if the **Contains** parameter specifies a value that matches any of the object's property values.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-152">-Credential</span><span class="sxs-lookup"><span data-stu-id="03d3e-152">-Credential</span></span>

<span data-ttu-id="03d3e-153">Gibt ein Benutzerkonto an, das über die Berechtigung zum Zugreifen auf den Computer und zum Ausführen von Befehlen verfügt.</span><span class="sxs-lookup"><span data-stu-id="03d3e-153">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="03d3e-154">Geben Sie einen Benutzernamen ein, z. b. **USER01** , **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="03d3e-154">Type a user name, such as **User01** , **Domain01\User01** , or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="03d3e-155">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="03d3e-155">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="03d3e-156">Wenn der **Credential** -Parameter nicht angegeben ist, `Install-Package` verwendet den aktuellen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="03d3e-156">When the **Credential** parameter isn't specified, `Install-Package` uses the current user.</span></span>

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

### <span data-ttu-id="03d3e-157">-Destination</span><span class="sxs-lookup"><span data-stu-id="03d3e-157">-Destination</span></span>

<span data-ttu-id="03d3e-158">Gibt einen Pfad zu einem Eingabe Objekt an.</span><span class="sxs-lookup"><span data-stu-id="03d3e-158">Specifies a path to an input object.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-159">-Dscresource</span><span class="sxs-lookup"><span data-stu-id="03d3e-159">-DscResource</span></span>

<span data-ttu-id="03d3e-160">Gibt eine oder mehrere DSC-Ressourcen (DSC) an, die von durchsucht werden `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="03d3e-160">Specifies one or more Desired State Configuration (DSC) resources that are searched by `Install-Package`.</span></span> <span data-ttu-id="03d3e-161">Verwenden `Find-DscResource` Sie das Cmdlet, um DSC-Ressourcen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="03d3e-161">Use the `Find-DscResource` cmdlet to find DSC resources.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-162">-Excludeversion</span><span class="sxs-lookup"><span data-stu-id="03d3e-162">-ExcludeVersion</span></span>

<span data-ttu-id="03d3e-163">Wechseln Sie zum Ausschließen der Versionsnummer im Ordner Pfad.</span><span class="sxs-lookup"><span data-stu-id="03d3e-163">Switch to exclude the version number in the folder path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-164">-Filter</span><span class="sxs-lookup"><span data-stu-id="03d3e-164">-Filter</span></span>

<span data-ttu-id="03d3e-165">Gibt die Begriffe an, nach denen in den Eigenschaften **Name** und **Description** gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="03d3e-165">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-166">-Filterontag</span><span class="sxs-lookup"><span data-stu-id="03d3e-166">-FilterOnTag</span></span>

<span data-ttu-id="03d3e-167">Gibt ein Tag an, das Ergebnisse filtert und Ergebnisse ausschließt, die das angegebene Tag nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="03d3e-167">Specifies a tag that filters results and excludes results that don't contain the specified tag.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-168">-Force</span><span class="sxs-lookup"><span data-stu-id="03d3e-168">-Force</span></span>

<span data-ttu-id="03d3e-169">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="03d3e-169">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="03d3e-170">Überschreibt Einschränkungen, die eine erfolgreiche Ausführung verhindern `Install-Package` , mit Ausnahme der Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="03d3e-170">Overrides restrictions that prevent `Install-Package` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="03d3e-171">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="03d3e-171">-ForceBootstrap</span></span>

<span data-ttu-id="03d3e-172">Erzwingt **packagemanagement** , den Paketanbieter für das angegebene Paket automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="03d3e-172">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="03d3e-173">-Header</span><span class="sxs-lookup"><span data-stu-id="03d3e-173">-Headers</span></span>

<span data-ttu-id="03d3e-174">Gibt die Paket Header an.</span><span class="sxs-lookup"><span data-stu-id="03d3e-174">Specifies the package headers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-175">-Includes</span><span class="sxs-lookup"><span data-stu-id="03d3e-175">-Includes</span></span>

<span data-ttu-id="03d3e-176">Gibt an, ob `Install-Package` alle Pakettypen finden soll.</span><span class="sxs-lookup"><span data-stu-id="03d3e-176">Specifies whether `Install-Package` should find all package types.</span></span> <span data-ttu-id="03d3e-177">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="03d3e-177">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="03d3e-178">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="03d3e-178">Cmdlet</span></span>
- <span data-ttu-id="03d3e-179">DscResource</span><span class="sxs-lookup"><span data-stu-id="03d3e-179">DscResource</span></span>
- <span data-ttu-id="03d3e-180">Funktion</span><span class="sxs-lookup"><span data-stu-id="03d3e-180">Function</span></span>
- <span data-ttu-id="03d3e-181">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="03d3e-181">RoleCapability</span></span>
- <span data-ttu-id="03d3e-182">Workflow</span><span class="sxs-lookup"><span data-stu-id="03d3e-182">Workflow</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: Cmdlet, DscResource, Function, RoleCapability, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-183">-InputObject</span><span class="sxs-lookup"><span data-stu-id="03d3e-183">-InputObject</span></span>

<span data-ttu-id="03d3e-184">Akzeptiert Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="03d3e-184">Accepts pipeline input.</span></span> <span data-ttu-id="03d3e-185">Gibt ein Paket mit dem **softwareidentity** -Typ des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="03d3e-185">Specifies a package by using the package's **SoftwareIdentity** type.</span></span>
<span data-ttu-id="03d3e-186">`Find-Package` Gibt ein **softwareidentity** -Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="03d3e-186">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

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

### <span data-ttu-id="03d3e-187">-Installupdate</span><span class="sxs-lookup"><span data-stu-id="03d3e-187">-InstallUpdate</span></span>

<span data-ttu-id="03d3e-188">Gibt an, dass `Install-Package` Updates installiert.</span><span class="sxs-lookup"><span data-stu-id="03d3e-188">Indicates that `Install-Package` installs updates.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-189">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="03d3e-189">-MaximumVersion</span></span>

<span data-ttu-id="03d3e-190">Gibt die maximal zulässige Paketversion an, die Sie installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="03d3e-190">Specifies the maximum allowed package version that you want to install.</span></span> <span data-ttu-id="03d3e-191">Wenn Sie diesen Parameter nicht angeben, `Install-Package` installiert die neueste Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="03d3e-191">If you don't specify this parameter, `Install-Package` installs the package's newest version.</span></span>

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

### <span data-ttu-id="03d3e-192">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="03d3e-192">-MinimumVersion</span></span>

<span data-ttu-id="03d3e-193">Gibt die minimal zulässige Paketversion an, die Sie installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="03d3e-193">Specifies the minimum allowed package version that you want to install.</span></span> <span data-ttu-id="03d3e-194">Wenn Sie diesen Parameter nicht hinzufügen, `Install-Package` installiert die neueste Version des Pakets, die jeder Version entspricht, die durch den **MaximumVersion** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="03d3e-194">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="03d3e-195">-Name</span><span class="sxs-lookup"><span data-stu-id="03d3e-195">-Name</span></span>

<span data-ttu-id="03d3e-196">Gibt mindestens einen Paketnamen an.</span><span class="sxs-lookup"><span data-stu-id="03d3e-196">Specifies one or more package names.</span></span> <span data-ttu-id="03d3e-197">Mehrere Paketnamen müssen durch Kommas getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="03d3e-197">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="03d3e-198">-Nopathupdate</span><span class="sxs-lookup"><span data-stu-id="03d3e-198">-NoPathUpdate</span></span>

<span data-ttu-id="03d3e-199">**Nopathupdate** gilt nur für das `Install-Script` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="03d3e-199">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="03d3e-200">**Nopathupdate** ist ein vom Anbieter hinzugefügter dynamischer Parameter, der von nicht unterstützt wird `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="03d3e-200">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Install-Package`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-201">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="03d3e-201">-PackageManagementProvider</span></span>

<span data-ttu-id="03d3e-202">Gibt den Namen des **packagemanagement** -Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="03d3e-202">Specifies the name of the **PackageManagement** provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-203">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="03d3e-203">-ProviderName</span></span>

<span data-ttu-id="03d3e-204">Gibt einen oder mehrere Paketanbieter Namen an, denen der Bereich der Paket Suche entspricht.</span><span class="sxs-lookup"><span data-stu-id="03d3e-204">Specifies one or more package provider names to which to scope your package search.</span></span> <span data-ttu-id="03d3e-205">Paketanbieternamen können Sie durch Ausführen des Cmdlets `Get-PackageProvider` abrufen.</span><span class="sxs-lookup"><span data-stu-id="03d3e-205">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="03d3e-206">-Proxy</span><span class="sxs-lookup"><span data-stu-id="03d3e-206">-Proxy</span></span>

<span data-ttu-id="03d3e-207">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit einer Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="03d3e-207">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="03d3e-208">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="03d3e-208">-ProxyCredential</span></span>

<span data-ttu-id="03d3e-209">Gibt ein Benutzerkonto an, das über die Berechtigung zum Verwenden des Proxy Servers verfügt, der durch den **Proxy** Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="03d3e-209">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="03d3e-210">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="03d3e-210">-PublishLocation</span></span>

<span data-ttu-id="03d3e-211">Gibt den Pfad zum veröffentlichten Speicherort eines Pakets an.</span><span class="sxs-lookup"><span data-stu-id="03d3e-211">Specifies the path to a package's published location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-212">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="03d3e-212">-RequiredVersion</span></span>

<span data-ttu-id="03d3e-213">Gibt die exakt zulässige Version des Pakets an, das Sie installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="03d3e-213">Specifies the exact allowed version of the package that you want to install.</span></span> <span data-ttu-id="03d3e-214">Wenn Sie diesen Parameter nicht hinzufügen, `Install-Package` installiert die neueste Version des Pakets, die jeder Version entspricht, die durch den **MaximumVersion** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="03d3e-214">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="03d3e-215">-Rolecapability</span><span class="sxs-lookup"><span data-stu-id="03d3e-215">-RoleCapability</span></span>

<span data-ttu-id="03d3e-216">Gibt ein Array von Rollen Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="03d3e-216">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-217">-Bereich</span><span class="sxs-lookup"><span data-stu-id="03d3e-217">-Scope</span></span>

<span data-ttu-id="03d3e-218">Gibt den Bereich an, für den das Paket installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="03d3e-218">Specifies the scope for which to install the package.</span></span> <span data-ttu-id="03d3e-219">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="03d3e-219">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="03d3e-220">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="03d3e-220">CurrentUser</span></span>
- <span data-ttu-id="03d3e-221">ALLUSERS</span><span class="sxs-lookup"><span data-stu-id="03d3e-221">AllUsers</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject, PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-222">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="03d3e-222">-ScriptPublishLocation</span></span>

<span data-ttu-id="03d3e-223">Gibt den Pfad zum veröffentlichten Speicherort eines Skripts an.</span><span class="sxs-lookup"><span data-stu-id="03d3e-223">Specifies the path to a script's published location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-224">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="03d3e-224">-ScriptSourceLocation</span></span>

<span data-ttu-id="03d3e-225">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="03d3e-225">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-226">-Skipabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="03d3e-226">-SkipDependencies</span></span>

<span data-ttu-id="03d3e-227">Überspringt die Installation von Software Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="03d3e-227">Skips the installation of software dependencies.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-228">-Skippublishercheck</span><span class="sxs-lookup"><span data-stu-id="03d3e-228">-SkipPublisherCheck</span></span>

<span data-ttu-id="03d3e-229">Ermöglicht es Ihnen, eine Paketversion zu erhalten, die neuer als die installierte Version ist.</span><span class="sxs-lookup"><span data-stu-id="03d3e-229">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="03d3e-230">Beispielsweise wird ein installiertes Paket, das von einem vertrauenswürdigen Verleger digital signiert ist, aber eine neue Version ist nicht digital signiert.</span><span class="sxs-lookup"><span data-stu-id="03d3e-230">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-231">-Skipvalidate</span><span class="sxs-lookup"><span data-stu-id="03d3e-231">-SkipValidate</span></span>

<span data-ttu-id="03d3e-232">Ein Schalter, der die Validierung der Anmelde Informationen eines Pakets überspringt.</span><span class="sxs-lookup"><span data-stu-id="03d3e-232">Switch that skips validating the credentials of a package.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-233">-Source</span><span class="sxs-lookup"><span data-stu-id="03d3e-233">-Source</span></span>

<span data-ttu-id="03d3e-234">Gibt mindestens eine Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="03d3e-234">Specifies one or more package sources.</span></span> <span data-ttu-id="03d3e-235">Mehrere Paketquellen Namen müssen durch Kommas getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="03d3e-235">Multiple package source names must be separated by commas.</span></span>
<span data-ttu-id="03d3e-236">Sie können die Paket Quellnamen durch Ausführen des `Get-PackageSource` Cmdlets erhalten.</span><span class="sxs-lookup"><span data-stu-id="03d3e-236">You can get package source names by running the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="03d3e-237">-Tag</span><span class="sxs-lookup"><span data-stu-id="03d3e-237">-Tag</span></span>

<span data-ttu-id="03d3e-238">Gibt eine oder mehrere Zeichen folgen an, die in den Paket Metadaten gesucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="03d3e-238">Specifies one or more strings to search for in the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-239">-Type</span><span class="sxs-lookup"><span data-stu-id="03d3e-239">-Type</span></span>

<span data-ttu-id="03d3e-240">Gibt an, ob Pakete mit einem Modul, einem Skript oder beidem gesucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="03d3e-240">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="03d3e-241">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="03d3e-241">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="03d3e-242">Modul</span><span class="sxs-lookup"><span data-stu-id="03d3e-242">Module</span></span>
- <span data-ttu-id="03d3e-243">Skript</span><span class="sxs-lookup"><span data-stu-id="03d3e-243">Script</span></span>
- <span data-ttu-id="03d3e-244">Alle</span><span class="sxs-lookup"><span data-stu-id="03d3e-244">All</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-245">-Confirm</span><span class="sxs-lookup"><span data-stu-id="03d3e-245">-Confirm</span></span>

<span data-ttu-id="03d3e-246">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="03d3e-246">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="03d3e-247">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="03d3e-247">-WhatIf</span></span>

<span data-ttu-id="03d3e-248">Zeigt, was geschieht, wenn das `Install-Package` Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="03d3e-248">Shows what would happen if `Install-Package` cmdlet is run.</span></span> <span data-ttu-id="03d3e-249">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="03d3e-249">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="03d3e-250">-Additionalarguments</span><span class="sxs-lookup"><span data-stu-id="03d3e-250">-AdditionalArguments</span></span>

<span data-ttu-id="03d3e-251">Gibt mindestens ein zusätzliches Argument für die Installation an.</span><span class="sxs-lookup"><span data-stu-id="03d3e-251">Specifies one or more additional arguments for installation.</span></span>

```yaml
Type: System.String[]
Parameter Sets: msi:PackageBySearch, msi:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-252">-Includesystemcomponent</span><span class="sxs-lookup"><span data-stu-id="03d3e-252">-IncludeSystemComponent</span></span>

<span data-ttu-id="03d3e-253">Gibt an, dass dieses Cmdlet Systemkomponenten in die Ergebnisse einschließt.</span><span class="sxs-lookup"><span data-stu-id="03d3e-253">Indicates that this cmdlet includes system components in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs:PackageBySearch, Programs:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-254">-Include WindowsInstaller</span><span class="sxs-lookup"><span data-stu-id="03d3e-254">-IncludeWindowsInstaller</span></span>

<span data-ttu-id="03d3e-255">Gibt an, dass dieses Cmdlet den Windows Installer in die Ergebnisse einschließt.</span><span class="sxs-lookup"><span data-stu-id="03d3e-255">Indicates that this cmdlet includes the Windows installer in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs:PackageBySearch, Programs:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d3e-256">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="03d3e-256">CommonParameters</span></span>

<span data-ttu-id="03d3e-257">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="03d3e-257">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="03d3e-258">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="03d3e-258">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="03d3e-259">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="03d3e-259">INPUTS</span></span>

### <span data-ttu-id="03d3e-260">`Install-Package` akzeptiert Eingaben aus der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="03d3e-260">`Install-Package` accepts input from the pipeline.</span></span>

## <span data-ttu-id="03d3e-261">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="03d3e-261">OUTPUTS</span></span>

### <span data-ttu-id="03d3e-262">Software Identity []</span><span class="sxs-lookup"><span data-stu-id="03d3e-262">SoftwareIdentity[]</span></span>

## <span data-ttu-id="03d3e-263">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="03d3e-263">NOTES</span></span>

<span data-ttu-id="03d3e-264">Durch das Einschließen eines Paket Anbieters in einen Befehl können dynamische Parameter für ein Cmdlet verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="03d3e-264">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="03d3e-265">Dynamische Parameter sind für einen Paketanbieter spezifisch.</span><span class="sxs-lookup"><span data-stu-id="03d3e-265">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="03d3e-266">Das `Get-Help` -Cmdlet listet die Parametersätze eines Cmdlets auf und schließt den Parametersatz des Anbieters ein.</span><span class="sxs-lookup"><span data-stu-id="03d3e-266">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="03d3e-267">Beispielsweise `Install-Package` ist für den **PowerShellGet** -Parameter festgelegt, der `-NoPathUpdate` , und enthält `AllowClobber` `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="03d3e-267">For example, `Install-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="03d3e-268">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="03d3e-268">RELATED LINKS</span></span>

[<span data-ttu-id="03d3e-269">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="03d3e-269">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="03d3e-270">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="03d3e-270">Find-DscResource</span></span>](../PowershellGet/Find-DscResource.md)

[<span data-ttu-id="03d3e-271">Get-Help</span><span class="sxs-lookup"><span data-stu-id="03d3e-271">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="03d3e-272">Get-Package</span><span class="sxs-lookup"><span data-stu-id="03d3e-272">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="03d3e-273">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="03d3e-273">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="03d3e-274">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="03d3e-274">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="03d3e-275">Find-Package</span><span class="sxs-lookup"><span data-stu-id="03d3e-275">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="03d3e-276">Save-Package</span><span class="sxs-lookup"><span data-stu-id="03d3e-276">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="03d3e-277">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="03d3e-277">Uninstall-Package</span></span>](Uninstall-Package.md)
