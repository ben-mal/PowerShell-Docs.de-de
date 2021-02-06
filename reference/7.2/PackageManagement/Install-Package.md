---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 05/23/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Package
ms.openlocfilehash: 1518be0d34733e36217b46cbbf496e580ec7b649
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99602528"
---
# <span data-ttu-id="7146e-102">Install-Package</span><span class="sxs-lookup"><span data-stu-id="7146e-102">Install-Package</span></span>

## <span data-ttu-id="7146e-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7146e-103">SYNOPSIS</span></span>
<span data-ttu-id="7146e-104">Installiert mindestens ein Softwarepaket.</span><span class="sxs-lookup"><span data-stu-id="7146e-104">Installs one or more software packages.</span></span>

## <span data-ttu-id="7146e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7146e-105">SYNTAX</span></span>

### <span data-ttu-id="7146e-106">Packagebysearch (Standard)</span><span class="sxs-lookup"><span data-stu-id="7146e-106">PackageBySearch (Default)</span></span>

```
Install-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="7146e-107">Packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="7146e-107">PackageByInputObject</span></span>

```
Install-Package [-InputObject] <SoftwareIdentity[]> [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="7146e-108">Nuget: packagebysearch</span><span class="sxs-lookup"><span data-stu-id="7146e-108">NuGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="7146e-109">Nuget: packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="7146e-109">NuGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="7146e-110">PowerShellGet: packagebysearch</span><span class="sxs-lookup"><span data-stu-id="7146e-110">PowerShellGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

### <span data-ttu-id="7146e-111">PowerShellGet: packagebyinputobject</span><span class="sxs-lookup"><span data-stu-id="7146e-111">PowerShellGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

## <span data-ttu-id="7146e-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7146e-112">DESCRIPTION</span></span>

<span data-ttu-id="7146e-113">Mit dem- `Install-Package` Cmdlet wird mindestens ein Softwarepaket auf dem lokalen Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="7146e-113">The `Install-Package` cmdlet installs one or more software packages on the local computer.</span></span> <span data-ttu-id="7146e-114">Wenn Sie über mehrere Software Quellen verfügen, verwenden Sie `Get-PackageProvider` und, `Get-PackageSource` um Details zu ihren Anbietern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7146e-114">If you have multiple software sources, use `Get-PackageProvider` and `Get-PackageSource` to display details about your providers.</span></span>

## <span data-ttu-id="7146e-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7146e-115">EXAMPLES</span></span>

### <span data-ttu-id="7146e-116">Beispiel 1: Installieren eines Pakets nach Paketname</span><span class="sxs-lookup"><span data-stu-id="7146e-116">Example 1: Install a package by package name</span></span>

<span data-ttu-id="7146e-117">Mit dem `Install-Package` -Cmdlet werden ein Softwarepaket und seine Abhängigkeiten installiert.</span><span class="sxs-lookup"><span data-stu-id="7146e-117">The `Install-Package` cmdlet installs a software package and its dependencies.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -Credential Contoso\TestUser
```

<span data-ttu-id="7146e-118">`Install-Package` verwendet Parameter, um den **Namen** und die **Quelle** des Pakets anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7146e-118">`Install-Package` uses parameters to specify the packages **Name** and **Source**.</span></span> <span data-ttu-id="7146e-119">Der **Credential** -Parameter verwendet ein Domänen Benutzerkonto mit Berechtigungen zum Installieren von Paketen.</span><span class="sxs-lookup"><span data-stu-id="7146e-119">The **Credential** parameter uses a domain user account with permissions to install packages.</span></span> <span data-ttu-id="7146e-120">Der Befehl fordert Sie zur Eingabe des Kennworts für das Benutzerkonto auf.</span><span class="sxs-lookup"><span data-stu-id="7146e-120">The command prompts you for the user account password.</span></span>

### <span data-ttu-id="7146e-121">Beispiel 2: Verwenden von Find-Package zum Installieren eines Pakets</span><span class="sxs-lookup"><span data-stu-id="7146e-121">Example 2: Use Find-Package to install a package</span></span>

<span data-ttu-id="7146e-122">In diesem Beispiel wird das von zurückgegebene `Find-Package` -Objekt über die Pipeline gesendet und von installiert `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="7146e-122">In this example, the object returned by `Find-Package` is sent down the pipeline and installed by `Install-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -Source MyNuGet | Install-Package
```

<span data-ttu-id="7146e-123">`Find-Package` verwendet den **Name** -Parameter und den **Quell** Parameter, um ein Paket zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7146e-123">`Find-Package` uses the **Name** and **Source** parameters to locate a package.</span></span> <span data-ttu-id="7146e-124">Das Objekt wird über die Pipeline gesendet und `Install-Package` installiert das Paket auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="7146e-124">The object is sent down the pipeline and `Install-Package` installs the package on the local computer.</span></span>

### <span data-ttu-id="7146e-125">Beispiel 3: Installieren von Paketen durch Angeben eines Bereichs von Versionen</span><span class="sxs-lookup"><span data-stu-id="7146e-125">Example 3: Install packages by specifying a range of versions</span></span>

<span data-ttu-id="7146e-126">`Install-Package` verwendet die Parameter **MinimumVersion** und **MaximumVersion** , um einen Bereich von Softwareversionen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7146e-126">`Install-Package` uses the **MinimumVersion** and **MaximumVersion** parameters to specify a range of software versions.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -MinimumVersion 2.8.0 -MaximumVersion 2.9.0
```

<span data-ttu-id="7146e-127">`Install-Package` verwendet den **Name** -Parameter und den **Quell** Parameter, um ein Paket zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7146e-127">`Install-Package` uses the **Name** and **Source** parameters to find a package.</span></span> <span data-ttu-id="7146e-128">Mit den Parametern **MinimumVersion** und **MaximumVersion** wird ein Bereich von Softwareversionen angegeben.</span><span class="sxs-lookup"><span data-stu-id="7146e-128">The **MinimumVersion** and **MaximumVersion** parameters specify a range of software versions.</span></span> <span data-ttu-id="7146e-129">Die höchste Version im Bereich ist installiert.</span><span class="sxs-lookup"><span data-stu-id="7146e-129">The highest version in the range is installed.</span></span>

## <span data-ttu-id="7146e-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7146e-130">PARAMETERS</span></span>

### <span data-ttu-id="7146e-131">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="7146e-131">-AcceptLicense</span></span>

 <span data-ttu-id="7146e-132">" **Accept License** " akzeptiert den Lizenzvertrag während der Installation automatisch.</span><span class="sxs-lookup"><span data-stu-id="7146e-132">**AcceptLicense** automatically accepts the license agreement during installation.</span></span>

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

### <span data-ttu-id="7146e-133">-Allowclobber</span><span class="sxs-lookup"><span data-stu-id="7146e-133">-AllowClobber</span></span>

<span data-ttu-id="7146e-134">Überschreibt Warnmeldungen zu Konflikten mit vorhandenen Befehlen.</span><span class="sxs-lookup"><span data-stu-id="7146e-134">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="7146e-135">Überschreibt vorhandene Befehle, die denselben Namen wie die Befehle aufweisen, die installiert werden.</span><span class="sxs-lookup"><span data-stu-id="7146e-135">Overwrites existing commands that have the same name as commands being installed.</span></span>

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

### <span data-ttu-id="7146e-136">-Allowprereleaseversions</span><span class="sxs-lookup"><span data-stu-id="7146e-136">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="7146e-137">Ermöglicht die Installation von Paketen, die als Vorabversion markiert sind.</span><span class="sxs-lookup"><span data-stu-id="7146e-137">Allows the installation of packages marked as prerelease.</span></span>

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

### <span data-ttu-id="7146e-138">-Allversions</span><span class="sxs-lookup"><span data-stu-id="7146e-138">-AllVersions</span></span>

<span data-ttu-id="7146e-139">`Install-Package` installiert alle verfügbaren Versionen des Pakets.</span><span class="sxs-lookup"><span data-stu-id="7146e-139">`Install-Package` installs all available versions of the package.</span></span> <span data-ttu-id="7146e-140">Standardmäßig wird nur die neueste Version installiert.</span><span class="sxs-lookup"><span data-stu-id="7146e-140">By default, only the newest version is installed.</span></span>

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

### <span data-ttu-id="7146e-141">-Command</span><span class="sxs-lookup"><span data-stu-id="7146e-141">-Command</span></span>

<span data-ttu-id="7146e-142">Gibt einen oder mehrere Befehle an, die `Install-Package` durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="7146e-142">Specifies one or more commands that `Install-Package` searches.</span></span>

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

### <span data-ttu-id="7146e-143">-Configfile</span><span class="sxs-lookup"><span data-stu-id="7146e-143">-ConfigFile</span></span>

<span data-ttu-id="7146e-144">Gibt einen Pfad an, der eine Konfigurationsdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="7146e-144">Specifies a path that contains a configuration file.</span></span>

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

### <span data-ttu-id="7146e-145">-Enthält</span><span class="sxs-lookup"><span data-stu-id="7146e-145">-Contains</span></span>

<span data-ttu-id="7146e-146">`Install-Package` Ruft Objekte ab, wenn der **enthält** -Parameter einen Wert angibt, der mit den Eigenschafts Werten des-Objekts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="7146e-146">`Install-Package` gets objects if the **Contains** parameter specifies a value that matches any of the object's property values.</span></span>

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

### <span data-ttu-id="7146e-147">-Credential</span><span class="sxs-lookup"><span data-stu-id="7146e-147">-Credential</span></span>

<span data-ttu-id="7146e-148">Gibt ein Benutzerkonto an, das über die Berechtigung zum Zugreifen auf den Computer und zum Ausführen von Befehlen verfügt.</span><span class="sxs-lookup"><span data-stu-id="7146e-148">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="7146e-149">Geben Sie einen Benutzernamen ein, z. b. **USER01**, **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7146e-149">Type a user name, such as **User01**, **Domain01\User01**, or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="7146e-150">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7146e-150">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="7146e-151">Wenn der **Credential** -Parameter nicht angegeben ist, `Install-Package` verwendet den aktuellen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7146e-151">When the **Credential** parameter isn't specified, `Install-Package` uses the current user.</span></span>

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

### <span data-ttu-id="7146e-152">-Destination</span><span class="sxs-lookup"><span data-stu-id="7146e-152">-Destination</span></span>

<span data-ttu-id="7146e-153">Gibt einen Pfad zu einem Eingabe Objekt an.</span><span class="sxs-lookup"><span data-stu-id="7146e-153">Specifies a path to an input object.</span></span>

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

### <span data-ttu-id="7146e-154">-Dscresource</span><span class="sxs-lookup"><span data-stu-id="7146e-154">-DscResource</span></span>

<span data-ttu-id="7146e-155">Gibt eine oder mehrere DSC-Ressourcen (DSC) an, die von durchsucht werden `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="7146e-155">Specifies one or more Desired State Configuration (DSC) resources that are searched by `Install-Package`.</span></span> <span data-ttu-id="7146e-156">Verwenden `Find-DscResource` Sie das Cmdlet, um DSC-Ressourcen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7146e-156">Use the `Find-DscResource` cmdlet to find DSC resources.</span></span>

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

### <span data-ttu-id="7146e-157">-Excludeversion</span><span class="sxs-lookup"><span data-stu-id="7146e-157">-ExcludeVersion</span></span>

<span data-ttu-id="7146e-158">Wechseln Sie zum Ausschließen der Versionsnummer im Ordner Pfad.</span><span class="sxs-lookup"><span data-stu-id="7146e-158">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="7146e-159">-Filter</span><span class="sxs-lookup"><span data-stu-id="7146e-159">-Filter</span></span>

<span data-ttu-id="7146e-160">Gibt die Begriffe an, nach denen in den Eigenschaften **Name** und **Description** gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="7146e-160">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

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

### <span data-ttu-id="7146e-161">-Filterontag</span><span class="sxs-lookup"><span data-stu-id="7146e-161">-FilterOnTag</span></span>

<span data-ttu-id="7146e-162">Gibt ein Tag an, das Ergebnisse filtert und Ergebnisse ausschließt, die das angegebene Tag nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="7146e-162">Specifies a tag that filters results and excludes results that don't contain the specified tag.</span></span>

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

### <span data-ttu-id="7146e-163">-Force</span><span class="sxs-lookup"><span data-stu-id="7146e-163">-Force</span></span>

<span data-ttu-id="7146e-164">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7146e-164">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="7146e-165">Überschreibt Einschränkungen, die eine erfolgreiche Ausführung verhindern `Install-Package` , mit Ausnahme der Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="7146e-165">Overrides restrictions that prevent `Install-Package` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="7146e-166">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="7146e-166">-ForceBootstrap</span></span>

<span data-ttu-id="7146e-167">Erzwingt **packagemanagement** , den Paketanbieter für das angegebene Paket automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="7146e-167">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="7146e-168">-Header</span><span class="sxs-lookup"><span data-stu-id="7146e-168">-Headers</span></span>

<span data-ttu-id="7146e-169">Gibt die Paket Header an.</span><span class="sxs-lookup"><span data-stu-id="7146e-169">Specifies the package headers.</span></span>

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

### <span data-ttu-id="7146e-170">-Includes</span><span class="sxs-lookup"><span data-stu-id="7146e-170">-Includes</span></span>

<span data-ttu-id="7146e-171">Gibt an, ob `Install-Package` alle Pakettypen finden soll.</span><span class="sxs-lookup"><span data-stu-id="7146e-171">Specifies whether `Install-Package` should find all package types.</span></span> <span data-ttu-id="7146e-172">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7146e-172">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="7146e-173">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7146e-173">Cmdlet</span></span>
- <span data-ttu-id="7146e-174">DscResource</span><span class="sxs-lookup"><span data-stu-id="7146e-174">DscResource</span></span>
- <span data-ttu-id="7146e-175">Funktion</span><span class="sxs-lookup"><span data-stu-id="7146e-175">Function</span></span>
- <span data-ttu-id="7146e-176">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="7146e-176">RoleCapability</span></span>
- <span data-ttu-id="7146e-177">Workflow</span><span class="sxs-lookup"><span data-stu-id="7146e-177">Workflow</span></span>

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

### <span data-ttu-id="7146e-178">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7146e-178">-InputObject</span></span>

<span data-ttu-id="7146e-179">Akzeptiert Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="7146e-179">Accepts pipeline input.</span></span> <span data-ttu-id="7146e-180">Gibt ein Paket mit dem **softwareidentity** -Typ des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="7146e-180">Specifies a package by using the package's **SoftwareIdentity** type.</span></span>
<span data-ttu-id="7146e-181">`Find-Package` Gibt ein **softwareidentity** -Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="7146e-181">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

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

### <span data-ttu-id="7146e-182">-Installupdate</span><span class="sxs-lookup"><span data-stu-id="7146e-182">-InstallUpdate</span></span>

<span data-ttu-id="7146e-183">Gibt an, dass `Install-Package` Updates installiert.</span><span class="sxs-lookup"><span data-stu-id="7146e-183">Indicates that `Install-Package` installs updates.</span></span>

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

### <span data-ttu-id="7146e-184">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="7146e-184">-MaximumVersion</span></span>

<span data-ttu-id="7146e-185">Gibt die maximal zulässige Paketversion an, die Sie installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7146e-185">Specifies the maximum allowed package version that you want to install.</span></span> <span data-ttu-id="7146e-186">Wenn Sie diesen Parameter nicht angeben, `Install-Package` installiert die neueste Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="7146e-186">If you don't specify this parameter, `Install-Package` installs the package's newest version.</span></span>

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

### <span data-ttu-id="7146e-187">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="7146e-187">-MinimumVersion</span></span>

<span data-ttu-id="7146e-188">Gibt die minimal zulässige Paketversion an, die Sie installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7146e-188">Specifies the minimum allowed package version that you want to install.</span></span> <span data-ttu-id="7146e-189">Wenn Sie diesen Parameter nicht hinzufügen, `Install-Package` installiert die neueste Version des Pakets, die jeder Version entspricht, die durch den **MaximumVersion** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7146e-189">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="7146e-190">-Name</span><span class="sxs-lookup"><span data-stu-id="7146e-190">-Name</span></span>

<span data-ttu-id="7146e-191">Gibt mindestens einen Paketnamen an.</span><span class="sxs-lookup"><span data-stu-id="7146e-191">Specifies one or more package names.</span></span> <span data-ttu-id="7146e-192">Mehrere Paketnamen müssen durch Kommas getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="7146e-192">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="7146e-193">-Nopathupdate</span><span class="sxs-lookup"><span data-stu-id="7146e-193">-NoPathUpdate</span></span>

<span data-ttu-id="7146e-194">**Nopathupdate** gilt nur für das `Install-Script` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7146e-194">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="7146e-195">**Nopathupdate** ist ein vom Anbieter hinzugefügter dynamischer Parameter, der von nicht unterstützt wird `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="7146e-195">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Install-Package`.</span></span>

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

### <span data-ttu-id="7146e-196">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="7146e-196">-PackageManagementProvider</span></span>

<span data-ttu-id="7146e-197">Gibt den Namen des **packagemanagement** -Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="7146e-197">Specifies the name of the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="7146e-198">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="7146e-198">-ProviderName</span></span>

<span data-ttu-id="7146e-199">Gibt einen oder mehrere Paketanbieter Namen an, denen der Bereich der Paket Suche entspricht.</span><span class="sxs-lookup"><span data-stu-id="7146e-199">Specifies one or more package provider names to which to scope your package search.</span></span> <span data-ttu-id="7146e-200">Paketanbieternamen können Sie durch Ausführen des Cmdlets `Get-PackageProvider` abrufen.</span><span class="sxs-lookup"><span data-stu-id="7146e-200">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="7146e-201">-Proxy</span><span class="sxs-lookup"><span data-stu-id="7146e-201">-Proxy</span></span>

<span data-ttu-id="7146e-202">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit einer Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="7146e-202">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="7146e-203">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="7146e-203">-ProxyCredential</span></span>

<span data-ttu-id="7146e-204">Gibt ein Benutzerkonto an, das über die Berechtigung zum Verwenden des Proxy Servers verfügt, der durch den **Proxy** Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7146e-204">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="7146e-205">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="7146e-205">-PublishLocation</span></span>

<span data-ttu-id="7146e-206">Gibt den Pfad zum veröffentlichten Speicherort eines Pakets an.</span><span class="sxs-lookup"><span data-stu-id="7146e-206">Specifies the path to a package's published location.</span></span>

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

### <span data-ttu-id="7146e-207">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="7146e-207">-RequiredVersion</span></span>

<span data-ttu-id="7146e-208">Gibt die exakt zulässige Version des Pakets an, das Sie installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7146e-208">Specifies the exact allowed version of the package that you want to install.</span></span> <span data-ttu-id="7146e-209">Wenn Sie diesen Parameter nicht hinzufügen, `Install-Package` installiert die neueste Version des Pakets, die jeder Version entspricht, die durch den **MaximumVersion** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7146e-209">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="7146e-210">-Rolecapability</span><span class="sxs-lookup"><span data-stu-id="7146e-210">-RoleCapability</span></span>

<span data-ttu-id="7146e-211">Gibt ein Array von Rollen Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="7146e-211">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="7146e-212">-Bereich</span><span class="sxs-lookup"><span data-stu-id="7146e-212">-Scope</span></span>

<span data-ttu-id="7146e-213">Gibt den Bereich an, für den das Paket installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="7146e-213">Specifies the scope for which to install the package.</span></span> <span data-ttu-id="7146e-214">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7146e-214">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="7146e-215">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="7146e-215">CurrentUser</span></span>
- <span data-ttu-id="7146e-216">ALLUSERS</span><span class="sxs-lookup"><span data-stu-id="7146e-216">AllUsers</span></span>

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

### <span data-ttu-id="7146e-217">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="7146e-217">-ScriptPublishLocation</span></span>

<span data-ttu-id="7146e-218">Gibt den Pfad zum veröffentlichten Speicherort eines Skripts an.</span><span class="sxs-lookup"><span data-stu-id="7146e-218">Specifies the path to a script's published location.</span></span>

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

### <span data-ttu-id="7146e-219">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="7146e-219">-ScriptSourceLocation</span></span>

<span data-ttu-id="7146e-220">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="7146e-220">Specifies the script source location.</span></span>

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

### <span data-ttu-id="7146e-221">-Skipabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="7146e-221">-SkipDependencies</span></span>

<span data-ttu-id="7146e-222">Überspringt die Installation von Software Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="7146e-222">Skips the installation of software dependencies.</span></span>

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

### <span data-ttu-id="7146e-223">-Skippublishercheck</span><span class="sxs-lookup"><span data-stu-id="7146e-223">-SkipPublisherCheck</span></span>

<span data-ttu-id="7146e-224">Ermöglicht es Ihnen, eine Paketversion zu erhalten, die neuer als die installierte Version ist.</span><span class="sxs-lookup"><span data-stu-id="7146e-224">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="7146e-225">Beispielsweise wird ein installiertes Paket, das von einem vertrauenswürdigen Verleger digital signiert ist, aber eine neue Version ist nicht digital signiert.</span><span class="sxs-lookup"><span data-stu-id="7146e-225">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="7146e-226">-Skipvalidate</span><span class="sxs-lookup"><span data-stu-id="7146e-226">-SkipValidate</span></span>

<span data-ttu-id="7146e-227">Ein Schalter, der die Validierung der Anmelde Informationen eines Pakets überspringt.</span><span class="sxs-lookup"><span data-stu-id="7146e-227">Switch that skips validating the credentials of a package.</span></span>

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

### <span data-ttu-id="7146e-228">-Source</span><span class="sxs-lookup"><span data-stu-id="7146e-228">-Source</span></span>

<span data-ttu-id="7146e-229">Gibt mindestens eine Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="7146e-229">Specifies one or more package sources.</span></span> <span data-ttu-id="7146e-230">Mehrere Paketquellen Namen müssen durch Kommas getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="7146e-230">Multiple package source names must be separated by commas.</span></span>
<span data-ttu-id="7146e-231">Sie können die Paket Quellnamen durch Ausführen des `Get-PackageSource` Cmdlets erhalten.</span><span class="sxs-lookup"><span data-stu-id="7146e-231">You can get package source names by running the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="7146e-232">-Tag</span><span class="sxs-lookup"><span data-stu-id="7146e-232">-Tag</span></span>

<span data-ttu-id="7146e-233">Gibt eine oder mehrere Zeichen folgen an, die in den Paket Metadaten gesucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7146e-233">Specifies one or more strings to search for in the package metadata.</span></span>

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

### <span data-ttu-id="7146e-234">-Type</span><span class="sxs-lookup"><span data-stu-id="7146e-234">-Type</span></span>

<span data-ttu-id="7146e-235">Gibt an, ob Pakete mit einem Modul, einem Skript oder beidem gesucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7146e-235">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="7146e-236">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7146e-236">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="7146e-237">Modul</span><span class="sxs-lookup"><span data-stu-id="7146e-237">Module</span></span>
- <span data-ttu-id="7146e-238">Skript</span><span class="sxs-lookup"><span data-stu-id="7146e-238">Script</span></span>
- <span data-ttu-id="7146e-239">Alle</span><span class="sxs-lookup"><span data-stu-id="7146e-239">All</span></span>

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

### <span data-ttu-id="7146e-240">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7146e-240">-Confirm</span></span>

<span data-ttu-id="7146e-241">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7146e-241">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7146e-242">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7146e-242">-WhatIf</span></span>

<span data-ttu-id="7146e-243">Zeigt, was geschieht, wenn das `Install-Package` Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7146e-243">Shows what would happen if `Install-Package` cmdlet is run.</span></span> <span data-ttu-id="7146e-244">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7146e-244">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7146e-245">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7146e-245">CommonParameters</span></span>

<span data-ttu-id="7146e-246">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7146e-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7146e-247">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7146e-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7146e-248">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7146e-248">INPUTS</span></span>

### <span data-ttu-id="7146e-249">`Install-Package` akzeptiert Eingaben aus der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="7146e-249">`Install-Package` accepts input from the pipeline.</span></span>

## <span data-ttu-id="7146e-250">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7146e-250">OUTPUTS</span></span>

### <span data-ttu-id="7146e-251">Software Identity []</span><span class="sxs-lookup"><span data-stu-id="7146e-251">SoftwareIdentity[]</span></span>

## <span data-ttu-id="7146e-252">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7146e-252">NOTES</span></span>

<span data-ttu-id="7146e-253">Durch das Einschließen eines Paket Anbieters in einen Befehl können dynamische Parameter für ein Cmdlet verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="7146e-253">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="7146e-254">Dynamische Parameter sind für einen Paketanbieter spezifisch.</span><span class="sxs-lookup"><span data-stu-id="7146e-254">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="7146e-255">Das `Get-Help` -Cmdlet listet die Parametersätze eines Cmdlets auf und schließt den Parametersatz des Anbieters ein.</span><span class="sxs-lookup"><span data-stu-id="7146e-255">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="7146e-256">Beispielsweise `Install-Package` ist für den **PowerShellGet** -Parameter festgelegt, der `-NoPathUpdate` , und enthält `AllowClobber` `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="7146e-256">For example, `Install-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7146e-257">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="7146e-257">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="7146e-258">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="7146e-258">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="7146e-259">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="7146e-259">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="7146e-260">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="7146e-260">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="7146e-261">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7146e-261">RELATED LINKS</span></span>

[<span data-ttu-id="7146e-262">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="7146e-262">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="7146e-263">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="7146e-263">Find-DscResource</span></span>](../PowershellGet/Find-DscResource.md)

[<span data-ttu-id="7146e-264">Get-Help</span><span class="sxs-lookup"><span data-stu-id="7146e-264">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="7146e-265">Get-Package</span><span class="sxs-lookup"><span data-stu-id="7146e-265">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="7146e-266">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="7146e-266">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="7146e-267">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="7146e-267">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="7146e-268">Find-Package</span><span class="sxs-lookup"><span data-stu-id="7146e-268">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="7146e-269">Save-Package</span><span class="sxs-lookup"><span data-stu-id="7146e-269">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="7146e-270">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="7146e-270">Uninstall-Package</span></span>](Uninstall-Package.md)
