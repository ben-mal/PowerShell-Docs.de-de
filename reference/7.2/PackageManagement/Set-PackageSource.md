---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/set-packagesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PackageSource
ms.openlocfilehash: 9f258c3b02064aafdaf272141f2613ff5cbaf5b5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99595540"
---
# <span data-ttu-id="fe672-102">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="fe672-102">Set-PackageSource</span></span>

## <span data-ttu-id="fe672-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="fe672-103">SYNOPSIS</span></span>
<span data-ttu-id="fe672-104">Ersetzt eine Paketquelle für einen angegebenen Paketanbieter.</span><span class="sxs-lookup"><span data-stu-id="fe672-104">Replaces a package source for a specified package provider.</span></span>

## <span data-ttu-id="fe672-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fe672-105">SYNTAX</span></span>

### <span data-ttu-id="fe672-106">Sourcebysearch (Standard)</span><span class="sxs-lookup"><span data-stu-id="fe672-106">SourceBySearch (Default)</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [[-Name] <String>] [-Location <String>] [-NewLocation <String>] [-NewName <String>] [-Trusted]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="fe672-107">Sourcebyinputobject</span><span class="sxs-lookup"><span data-stu-id="fe672-107">SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] -InputObject <PackageSource> [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fe672-108">Nuget: sourcebyinputobject</span><span class="sxs-lookup"><span data-stu-id="fe672-108">NuGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="fe672-109">Nuget: sourcebysearch</span><span class="sxs-lookup"><span data-stu-id="fe672-109">NuGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="fe672-110">PowerShellGet: sourcebyinputobject</span><span class="sxs-lookup"><span data-stu-id="fe672-110">PowerShellGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="fe672-111">PowerShellGet: sourcebysearch</span><span class="sxs-lookup"><span data-stu-id="fe672-111">PowerShellGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="fe672-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fe672-112">DESCRIPTION</span></span>

<span data-ttu-id="fe672-113">`Set-PackageSource`Ersetzt eine Paketquelle für einen angegebenen Paketanbieter.</span><span class="sxs-lookup"><span data-stu-id="fe672-113">The `Set-PackageSource` replaces a package source for a specified package provider.</span></span> <span data-ttu-id="fe672-114">Paketquellen werden immer von einem Paketanbieter verwaltet.</span><span class="sxs-lookup"><span data-stu-id="fe672-114">Package sources are always managed by a package provider.</span></span>

## <span data-ttu-id="fe672-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="fe672-115">EXAMPLES</span></span>

### <span data-ttu-id="fe672-116">Beispiel 1: Ändern einer Paketquelle</span><span class="sxs-lookup"><span data-stu-id="fe672-116">Example 1: Change a package source</span></span>

<span data-ttu-id="fe672-117">Mit diesem Befehl wird der vorhandene Name einer Paketquelle geändert.</span><span class="sxs-lookup"><span data-stu-id="fe672-117">This command changes the existing name of a package source.</span></span> <span data-ttu-id="fe672-118">Die Quelle ist auf " **vertrauenswürdig**" festgelegt. Dadurch werden Aufforderungen zum Überprüfen der Quelle beim Installieren von Paketen beseitigt.</span><span class="sxs-lookup"><span data-stu-id="fe672-118">The source is set to **Trusted**, which eliminates prompts to verify the source when packages are installed.</span></span>

```
PS C:\> Set-PackageSource -Name MyNuget -NewName NewNuGet -Trusted -ProviderName NuGet
```

## <span data-ttu-id="fe672-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fe672-119">PARAMETERS</span></span>

### <span data-ttu-id="fe672-120">-Configfile</span><span class="sxs-lookup"><span data-stu-id="fe672-120">-ConfigFile</span></span>

<span data-ttu-id="fe672-121">Gibt eine Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="fe672-121">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="fe672-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="fe672-122">-Credential</span></span>

<span data-ttu-id="fe672-123">Gibt ein Benutzerkonto an, das über die Berechtigung zum Installieren von Paket Anbietern verfügt.</span><span class="sxs-lookup"><span data-stu-id="fe672-123">Specifies a user account that has permission to install package providers.</span></span>

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

### <span data-ttu-id="fe672-124">-Force</span><span class="sxs-lookup"><span data-stu-id="fe672-124">-Force</span></span>

<span data-ttu-id="fe672-125">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="fe672-125">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="fe672-126">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="fe672-126">-ForceBootstrap</span></span>

<span data-ttu-id="fe672-127">Gibt an, dass `Set-PackageSource` **packagemanagement** zwingt, den Paketanbieter automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="fe672-127">Indicates that `Set-PackageSource` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="fe672-128">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fe672-128">-InputObject</span></span>

<span data-ttu-id="fe672-129">Gibt ein Paketquellen-ID-Objekt an, das das zu ändernde Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="fe672-129">Specifies a package source ID object that represents the package that you want to change.</span></span> <span data-ttu-id="fe672-130">Paket Quell-IDs sind Teil der Ergebnisse des `Get-PackageSource` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fe672-130">Package source IDs are part of the results of the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="fe672-131">-Location</span><span class="sxs-lookup"><span data-stu-id="fe672-131">-Location</span></span>

<span data-ttu-id="fe672-132">Gibt den Quell Speicherort des aktuellen Pakets an.</span><span class="sxs-lookup"><span data-stu-id="fe672-132">Specifies the current package source location.</span></span> <span data-ttu-id="fe672-133">Der Wert kann ein URI, ein Dateipfad oder ein beliebiges anderes Zielformat sein, das vom Paketanbieter unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="fe672-133">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

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

### <span data-ttu-id="fe672-134">-Name</span><span class="sxs-lookup"><span data-stu-id="fe672-134">-Name</span></span>

<span data-ttu-id="fe672-135">Gibt den Namen einer Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="fe672-135">Specifies a package source's name.</span></span>

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

### <span data-ttu-id="fe672-136">-NewLocation</span><span class="sxs-lookup"><span data-stu-id="fe672-136">-NewLocation</span></span>

<span data-ttu-id="fe672-137">Gibt den neuen Speicherort für eine Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="fe672-137">Specifies the new location for a package source.</span></span> <span data-ttu-id="fe672-138">Der Wert kann ein URI, ein Dateipfad oder ein beliebiges anderes Zielformat sein, das vom Paketanbieter unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="fe672-138">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

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

### <span data-ttu-id="fe672-139">-Newname</span><span class="sxs-lookup"><span data-stu-id="fe672-139">-NewName</span></span>

<span data-ttu-id="fe672-140">Gibt den neuen Namen an, den Sie einer Paketquelle zuweisen.</span><span class="sxs-lookup"><span data-stu-id="fe672-140">Specifies the new name you assign to a package source.</span></span>

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

### <span data-ttu-id="fe672-141">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="fe672-141">-PackageManagementProvider</span></span>

<span data-ttu-id="fe672-142">Gibt einen Paket Verwaltungs Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="fe672-142">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="fe672-143">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="fe672-143">-ProviderName</span></span>

<span data-ttu-id="fe672-144">Gibt einen Anbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="fe672-144">Specifies a provider name.</span></span>

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

### <span data-ttu-id="fe672-145">-Proxy</span><span class="sxs-lookup"><span data-stu-id="fe672-145">-Proxy</span></span>

<span data-ttu-id="fe672-146">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="fe672-146">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="fe672-147">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="fe672-147">-ProxyCredential</span></span>

<span data-ttu-id="fe672-148">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fe672-148">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="fe672-149">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="fe672-149">-PublishLocation</span></span>

<span data-ttu-id="fe672-150">Gibt den Veröffentlichungs Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="fe672-150">Specifies the publish location.</span></span>

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

### <span data-ttu-id="fe672-151">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="fe672-151">-ScriptPublishLocation</span></span>

<span data-ttu-id="fe672-152">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="fe672-152">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="fe672-153">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="fe672-153">-ScriptSourceLocation</span></span>

<span data-ttu-id="fe672-154">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="fe672-154">Specifies the script source location.</span></span>

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

### <span data-ttu-id="fe672-155">-Skipvalidate</span><span class="sxs-lookup"><span data-stu-id="fe672-155">-SkipValidate</span></span>

<span data-ttu-id="fe672-156">Ein Schalter, der die Validierung der Anmelde Informationen einer Paketquelle überspringt.</span><span class="sxs-lookup"><span data-stu-id="fe672-156">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="fe672-157">-Vertrauenswürdig</span><span class="sxs-lookup"><span data-stu-id="fe672-157">-Trusted</span></span>

<span data-ttu-id="fe672-158">Gibt an, dass die Quelle ein vertrauenswürdiger Paketanbieter ist.</span><span class="sxs-lookup"><span data-stu-id="fe672-158">Indicates that the source is a trusted package provider.</span></span> <span data-ttu-id="fe672-159">Vertrauenswürdige Quellen werden nicht zur Überprüfung aufgefordert, um Pakete zu installieren.</span><span class="sxs-lookup"><span data-stu-id="fe672-159">Trusted sources don't prompt for verification to install packages.</span></span>

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

### <span data-ttu-id="fe672-160">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fe672-160">-Confirm</span></span>

<span data-ttu-id="fe672-161">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="fe672-161">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fe672-162">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fe672-162">-WhatIf</span></span>

<span data-ttu-id="fe672-163">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fe672-163">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fe672-164">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fe672-164">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fe672-165">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fe672-165">CommonParameters</span></span>

<span data-ttu-id="fe672-166">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fe672-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fe672-167">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fe672-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fe672-168">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="fe672-168">INPUTS</span></span>

### <span data-ttu-id="fe672-169">`Set-PackageSource` akzeptiert keine Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="fe672-169">`Set-PackageSource` doesn't accept pipeline input.</span></span>

## <span data-ttu-id="fe672-170">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="fe672-170">OUTPUTS</span></span>

### <span data-ttu-id="fe672-171">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="fe672-171">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fe672-172">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="fe672-172">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe672-173">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="fe672-173">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="fe672-174">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="fe672-174">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="fe672-175">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="fe672-175">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="fe672-176">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="fe672-176">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="fe672-177">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="fe672-177">RELATED LINKS</span></span>

[<span data-ttu-id="fe672-178">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="fe672-178">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="fe672-179">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="fe672-179">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="fe672-180">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="fe672-180">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="fe672-181">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="fe672-181">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
