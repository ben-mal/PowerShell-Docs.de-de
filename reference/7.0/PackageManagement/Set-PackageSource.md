---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/set-packagesource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PackageSource
ms.openlocfilehash: 67a5a97c4e29556c9b93a17d25576d4bd6eaea0c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892704"
---
# <span data-ttu-id="08fa9-103">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="08fa9-103">Set-PackageSource</span></span>

## <span data-ttu-id="08fa9-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="08fa9-104">SYNOPSIS</span></span>
<span data-ttu-id="08fa9-105">Ersetzt eine Paketquelle für einen angegebenen Paketanbieter.</span><span class="sxs-lookup"><span data-stu-id="08fa9-105">Replaces a package source for a specified package provider.</span></span>

## <span data-ttu-id="08fa9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="08fa9-106">SYNTAX</span></span>

### <span data-ttu-id="08fa9-107">Sourcebysearch (Standard)</span><span class="sxs-lookup"><span data-stu-id="08fa9-107">SourceBySearch (Default)</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [[-Name] <String>] [-Location <String>] [-NewLocation <String>] [-NewName <String>] [-Trusted]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="08fa9-108">Sourcebyinputobject</span><span class="sxs-lookup"><span data-stu-id="08fa9-108">SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] -InputObject <PackageSource> [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="08fa9-109">Nuget: sourcebyinputobject</span><span class="sxs-lookup"><span data-stu-id="08fa9-109">NuGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="08fa9-110">Nuget: sourcebysearch</span><span class="sxs-lookup"><span data-stu-id="08fa9-110">NuGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="08fa9-111">PowerShellGet: sourcebyinputobject</span><span class="sxs-lookup"><span data-stu-id="08fa9-111">PowerShellGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="08fa9-112">PowerShellGet: sourcebysearch</span><span class="sxs-lookup"><span data-stu-id="08fa9-112">PowerShellGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="08fa9-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08fa9-113">DESCRIPTION</span></span>

<span data-ttu-id="08fa9-114">`Set-PackageSource`Ersetzt eine Paketquelle für einen angegebenen Paketanbieter.</span><span class="sxs-lookup"><span data-stu-id="08fa9-114">The `Set-PackageSource` replaces a package source for a specified package provider.</span></span> <span data-ttu-id="08fa9-115">Paketquellen werden immer von einem Paketanbieter verwaltet.</span><span class="sxs-lookup"><span data-stu-id="08fa9-115">Package sources are always managed by a package provider.</span></span>

## <span data-ttu-id="08fa9-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="08fa9-116">EXAMPLES</span></span>

### <span data-ttu-id="08fa9-117">Beispiel 1: Ändern einer Paketquelle</span><span class="sxs-lookup"><span data-stu-id="08fa9-117">Example 1: Change a package source</span></span>

<span data-ttu-id="08fa9-118">Mit diesem Befehl wird der vorhandene Name einer Paketquelle geändert.</span><span class="sxs-lookup"><span data-stu-id="08fa9-118">This command changes the existing name of a package source.</span></span> <span data-ttu-id="08fa9-119">Die Quelle ist auf " **vertrauenswürdig**" festgelegt. Dadurch werden Aufforderungen zum Überprüfen der Quelle beim Installieren von Paketen beseitigt.</span><span class="sxs-lookup"><span data-stu-id="08fa9-119">The source is set to **Trusted**, which eliminates prompts to verify the source when packages are installed.</span></span>

```
PS C:\> Set-PackageSource -Name MyNuget -NewName NewNuGet -Trusted -ProviderName NuGet
```

## <span data-ttu-id="08fa9-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="08fa9-120">PARAMETERS</span></span>

### <span data-ttu-id="08fa9-121">-Configfile</span><span class="sxs-lookup"><span data-stu-id="08fa9-121">-ConfigFile</span></span>

<span data-ttu-id="08fa9-122">Gibt eine Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="08fa9-122">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08fa9-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="08fa9-123">-Credential</span></span>

<span data-ttu-id="08fa9-124">Gibt ein Benutzerkonto an, das über die Berechtigung zum Installieren von Paket Anbietern verfügt.</span><span class="sxs-lookup"><span data-stu-id="08fa9-124">Specifies a user account that has permission to install package providers.</span></span>

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

### <span data-ttu-id="08fa9-125">-Force</span><span class="sxs-lookup"><span data-stu-id="08fa9-125">-Force</span></span>

<span data-ttu-id="08fa9-126">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="08fa9-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="08fa9-127">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="08fa9-127">-ForceBootstrap</span></span>

<span data-ttu-id="08fa9-128">Gibt an, dass `Set-PackageSource` **packagemanagement** zwingt, den Paketanbieter automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="08fa9-128">Indicates that `Set-PackageSource` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="08fa9-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="08fa9-129">-InputObject</span></span>

<span data-ttu-id="08fa9-130">Gibt ein Paketquellen-ID-Objekt an, das das zu ändernde Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="08fa9-130">Specifies a package source ID object that represents the package that you want to change.</span></span> <span data-ttu-id="08fa9-131">Paket Quell-IDs sind Teil der Ergebnisse des `Get-PackageSource` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="08fa9-131">Package source IDs are part of the results of the `Get-PackageSource` cmdlet.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.PackageSource
Parameter Sets: SourceByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="08fa9-132">-Location</span><span class="sxs-lookup"><span data-stu-id="08fa9-132">-Location</span></span>

<span data-ttu-id="08fa9-133">Gibt den Quell Speicherort des aktuellen Pakets an.</span><span class="sxs-lookup"><span data-stu-id="08fa9-133">Specifies the current package source location.</span></span> <span data-ttu-id="08fa9-134">Der Wert kann ein URI, ein Dateipfad oder ein beliebiges anderes Zielformat sein, das vom Paketanbieter unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="08fa9-134">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08fa9-135">-Name</span><span class="sxs-lookup"><span data-stu-id="08fa9-135">-Name</span></span>

<span data-ttu-id="08fa9-136">Gibt den Namen einer Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="08fa9-136">Specifies a package source's name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: SourceName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08fa9-137">-NewLocation</span><span class="sxs-lookup"><span data-stu-id="08fa9-137">-NewLocation</span></span>

<span data-ttu-id="08fa9-138">Gibt den neuen Speicherort für eine Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="08fa9-138">Specifies the new location for a package source.</span></span> <span data-ttu-id="08fa9-139">Der Wert kann ein URI, ein Dateipfad oder ein beliebiges anderes Zielformat sein, das vom Paketanbieter unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="08fa9-139">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

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

### <span data-ttu-id="08fa9-140">-Newname</span><span class="sxs-lookup"><span data-stu-id="08fa9-140">-NewName</span></span>

<span data-ttu-id="08fa9-141">Gibt den neuen Namen an, den Sie einer Paketquelle zuweisen.</span><span class="sxs-lookup"><span data-stu-id="08fa9-141">Specifies the new name you assign to a package source.</span></span>

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

### <span data-ttu-id="08fa9-142">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="08fa9-142">-PackageManagementProvider</span></span>

<span data-ttu-id="08fa9-143">Gibt einen Paket Verwaltungs Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="08fa9-143">Specifies a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08fa9-144">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="08fa9-144">-ProviderName</span></span>

<span data-ttu-id="08fa9-145">Gibt einen Anbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="08fa9-145">Specifies a provider name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="08fa9-146">-Proxy</span><span class="sxs-lookup"><span data-stu-id="08fa9-146">-Proxy</span></span>

<span data-ttu-id="08fa9-147">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="08fa9-147">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="08fa9-148">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="08fa9-148">-ProxyCredential</span></span>

<span data-ttu-id="08fa9-149">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="08fa9-149">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="08fa9-150">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="08fa9-150">-PublishLocation</span></span>

<span data-ttu-id="08fa9-151">Gibt den Veröffentlichungs Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="08fa9-151">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08fa9-152">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="08fa9-152">-ScriptPublishLocation</span></span>

<span data-ttu-id="08fa9-153">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="08fa9-153">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08fa9-154">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="08fa9-154">-ScriptSourceLocation</span></span>

<span data-ttu-id="08fa9-155">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="08fa9-155">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08fa9-156">-Skipvalidate</span><span class="sxs-lookup"><span data-stu-id="08fa9-156">-SkipValidate</span></span>

<span data-ttu-id="08fa9-157">Ein Schalter, der die Validierung der Anmelde Informationen einer Paketquelle überspringt.</span><span class="sxs-lookup"><span data-stu-id="08fa9-157">Switch that skips validating the credentials of a package source.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08fa9-158">-Vertrauenswürdig</span><span class="sxs-lookup"><span data-stu-id="08fa9-158">-Trusted</span></span>

<span data-ttu-id="08fa9-159">Gibt an, dass die Quelle ein vertrauenswürdiger Paketanbieter ist.</span><span class="sxs-lookup"><span data-stu-id="08fa9-159">Indicates that the source is a trusted package provider.</span></span> <span data-ttu-id="08fa9-160">Vertrauenswürdige Quellen werden nicht zur Überprüfung aufgefordert, um Pakete zu installieren.</span><span class="sxs-lookup"><span data-stu-id="08fa9-160">Trusted sources don't prompt for verification to install packages.</span></span>

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

### <span data-ttu-id="08fa9-161">-Confirm</span><span class="sxs-lookup"><span data-stu-id="08fa9-161">-Confirm</span></span>

<span data-ttu-id="08fa9-162">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="08fa9-162">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="08fa9-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="08fa9-163">-WhatIf</span></span>

<span data-ttu-id="08fa9-164">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="08fa9-164">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="08fa9-165">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="08fa9-165">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="08fa9-166">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="08fa9-166">CommonParameters</span></span>

<span data-ttu-id="08fa9-167">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="08fa9-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="08fa9-168">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="08fa9-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="08fa9-169">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="08fa9-169">INPUTS</span></span>

### <span data-ttu-id="08fa9-170">`Set-PackageSource` akzeptiert keine Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="08fa9-170">`Set-PackageSource` doesn't accept pipeline input.</span></span>

## <span data-ttu-id="08fa9-171">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="08fa9-171">OUTPUTS</span></span>

### <span data-ttu-id="08fa9-172">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="08fa9-172">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="08fa9-173">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="08fa9-173">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08fa9-174">Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="08fa9-174">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="08fa9-175">Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="08fa9-175">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="08fa9-176">Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="08fa9-176">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="08fa9-177">Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.</span><span class="sxs-lookup"><span data-stu-id="08fa9-177">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="08fa9-178">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="08fa9-178">RELATED LINKS</span></span>

[<span data-ttu-id="08fa9-179">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="08fa9-179">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="08fa9-180">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="08fa9-180">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="08fa9-181">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="08fa9-181">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="08fa9-182">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="08fa9-182">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
