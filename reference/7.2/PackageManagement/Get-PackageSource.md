---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 03/29/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packagesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageSource
ms.openlocfilehash: 8b91c5b950e0e16c4ce0821ee2f96b830dab1fc2
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99601105"
---
# <span data-ttu-id="f1e1b-102">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="f1e1b-102">Get-PackageSource</span></span>

## <span data-ttu-id="f1e1b-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f1e1b-103">SYNOPSIS</span></span>
<span data-ttu-id="f1e1b-104">Ruft eine Liste der Paketquellen ab, die für einen Paketanbieter registriert sind.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-104">Gets a list of package sources that are registered for a package provider.</span></span>

## <span data-ttu-id="f1e1b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f1e1b-105">SYNTAX</span></span>

### <span data-ttu-id="f1e1b-106">NuGet</span><span class="sxs-lookup"><span data-stu-id="f1e1b-106">NuGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="f1e1b-107">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="f1e1b-107">PowerShellGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="f1e1b-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f1e1b-108">DESCRIPTION</span></span>

<span data-ttu-id="f1e1b-109">Mit dem- `Get-PackageSource` Cmdlet wird eine Liste der Paketquellen abgerufen, die bei **packagemanagement** auf dem lokalen Computer registriert sind.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-109">The `Get-PackageSource` cmdlet gets a list of package sources that are registered with **PackageManagement** on the local computer.</span></span> <span data-ttu-id="f1e1b-110">Wenn Sie einen Paketanbieter angeben, werden `Get-PackageSource` von nur die Quellen abgerufen, die dem angegebenen Anbieter zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-110">If you specify a package provider, `Get-PackageSource` gets only those sources that are associated with the specified provider.</span></span> <span data-ttu-id="f1e1b-111">Andernfalls gibt der Befehl alle Paketquellen zurück, die bei **packagemanagement** registriert sind.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-111">Otherwise, the command returns all package sources that are registered with **PackageManagement**.</span></span>

## <span data-ttu-id="f1e1b-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f1e1b-112">EXAMPLES</span></span>

### <span data-ttu-id="f1e1b-113">Beispiel 1: alle Paketquellen erhalten</span><span class="sxs-lookup"><span data-stu-id="f1e1b-113">Example 1: Get all package sources</span></span>

<span data-ttu-id="f1e1b-114">Mit dem- `Get-PackageSource` Cmdlet werden alle Paketquellen abgerufen, die bei **packagemanagement** auf dem lokalen Computer registriert sind.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-114">The `Get-PackageSource` cmdlet gets all package sources that are registered with **PackageManagement** on the local computer.</span></span>

```powershell
Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
PSGallery            PowerShellGet    False      https://www.powershellgallery.com/api/v2
```

### <span data-ttu-id="f1e1b-115">Beispiel 2: alle Paketquellen für einen bestimmten Anbieter</span><span class="sxs-lookup"><span data-stu-id="f1e1b-115">Example 2: Get all package sources for a specific provider</span></span>

<span data-ttu-id="f1e1b-116">Mit diesem Befehl werden Paketquellen abgerufen, die für einen bestimmten Anbieter registriert sind.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-116">This command gets package sources that are registered for a specific provider.</span></span>

```powershell
Get-PackageSource -ProviderName NuGet
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="f1e1b-117">`Get-PackageSource` verwendet den **providerName** -Parameter, um Paketquellen zu erhalten, die für den **nuget** -Anbieter registriert sind.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-117">`Get-PackageSource` uses the **ProviderName** parameter to get package sources that are registered for the **NuGet** provider.</span></span>

### <span data-ttu-id="f1e1b-118">Beispiel 3: Quellen von einem Paketanbieter beziehen</span><span class="sxs-lookup"><span data-stu-id="f1e1b-118">Example 3: Get sources from a package provider</span></span>

<span data-ttu-id="f1e1b-119">Dieser Befehl verwendet einen Paketanbieter, um Paketquellen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-119">This command uses a package provider to get package sources.</span></span>

```powershell
Get-PackageProvider -Name NuGet | Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="f1e1b-120">`Get-PackageProvider` verwendet den **Name** -Parameter, um den Anbieter Namen ( **nuget**) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-120">`Get-PackageProvider` uses the **Name** parameter specify the provider name, **NuGet**.</span></span> <span data-ttu-id="f1e1b-121">Das Objekt wird über die Pipeline an gesendet `Get-PackageSource` .</span><span class="sxs-lookup"><span data-stu-id="f1e1b-121">The object is sent down the pipeline to `Get-PackageSource`.</span></span>

## <span data-ttu-id="f1e1b-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f1e1b-122">PARAMETERS</span></span>

### <span data-ttu-id="f1e1b-123">-Configfile</span><span class="sxs-lookup"><span data-stu-id="f1e1b-123">-ConfigFile</span></span>

<span data-ttu-id="f1e1b-124">Gibt eine Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-124">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="f1e1b-125">-Force</span><span class="sxs-lookup"><span data-stu-id="f1e1b-125">-Force</span></span>

<span data-ttu-id="f1e1b-126">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="f1e1b-127">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="f1e1b-127">-ForceBootstrap</span></span>

<span data-ttu-id="f1e1b-128">Gibt an, dass mit diesem Cmdlet **packagemanagement** gezwungen wird, einen Paketanbieter automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-128">Indicates that this cmdlet forces **PackageManagement** to automatically install a package provider.</span></span>

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

### <span data-ttu-id="f1e1b-129">-Location</span><span class="sxs-lookup"><span data-stu-id="f1e1b-129">-Location</span></span>

<span data-ttu-id="f1e1b-130">Gibt den Speicherort einer Paket Verwaltungs Quelle oder eines Repository an.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-130">Specifies the location of a package management source or repository.</span></span>

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

### <span data-ttu-id="f1e1b-131">-Name</span><span class="sxs-lookup"><span data-stu-id="f1e1b-131">-Name</span></span>

<span data-ttu-id="f1e1b-132">Gibt den Namen einer Paket Verwaltungs Quelle an.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-132">Specifies the name of a package management source.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f1e1b-133">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="f1e1b-133">-PackageManagementProvider</span></span>

<span data-ttu-id="f1e1b-134">Gibt einen Paket Verwaltungs Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-134">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="f1e1b-135">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="f1e1b-135">-ProviderName</span></span>

<span data-ttu-id="f1e1b-136">Gibt einen oder mehrere Paketanbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-136">Specifies one or more package provider names.</span></span> <span data-ttu-id="f1e1b-137">Trennen Sie mehrere Paketanbieter Namen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-137">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="f1e1b-138">Verwenden `Get-PackageProvider` Sie, um eine Liste der verfügbaren Paketanbieter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-138">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="f1e1b-139">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="f1e1b-139">-PublishLocation</span></span>

<span data-ttu-id="f1e1b-140">Gibt den Veröffentlichungs Speicherort für die Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-140">Specifies the publish location for the package source.</span></span>

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

### <span data-ttu-id="f1e1b-141">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="f1e1b-141">-ScriptPublishLocation</span></span>

<span data-ttu-id="f1e1b-142">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-142">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="f1e1b-143">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="f1e1b-143">-ScriptSourceLocation</span></span>

<span data-ttu-id="f1e1b-144">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-144">Specifies the script source location.</span></span>

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

### <span data-ttu-id="f1e1b-145">-Skipvalidate</span><span class="sxs-lookup"><span data-stu-id="f1e1b-145">-SkipValidate</span></span>

<span data-ttu-id="f1e1b-146">Ein Schalter, der die Validierung der Anmelde Informationen einer Paketquelle überspringt.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-146">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="f1e1b-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f1e1b-147">CommonParameters</span></span>

<span data-ttu-id="f1e1b-148">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f1e1b-149">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f1e1b-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f1e1b-150">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f1e1b-150">INPUTS</span></span>

## <span data-ttu-id="f1e1b-151">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f1e1b-151">OUTPUTS</span></span>

### <span data-ttu-id="f1e1b-152">Packagesource []</span><span class="sxs-lookup"><span data-stu-id="f1e1b-152">PackageSource[]</span></span>

<span data-ttu-id="f1e1b-153">Gibt mindestens eine Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-153">Specifies one or more package sources.</span></span>

## <span data-ttu-id="f1e1b-154">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f1e1b-154">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1e1b-155">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-155">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="f1e1b-156">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="f1e1b-156">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="f1e1b-157">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="f1e1b-157">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="f1e1b-158">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="f1e1b-158">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="f1e1b-159">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f1e1b-159">RELATED LINKS</span></span>

[<span data-ttu-id="f1e1b-160">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="f1e1b-160">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="f1e1b-161">Find-Package</span><span class="sxs-lookup"><span data-stu-id="f1e1b-161">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="f1e1b-162">Get-Package</span><span class="sxs-lookup"><span data-stu-id="f1e1b-162">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="f1e1b-163">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="f1e1b-163">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="f1e1b-164">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="f1e1b-164">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="f1e1b-165">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="f1e1b-165">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="f1e1b-166">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="f1e1b-166">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
