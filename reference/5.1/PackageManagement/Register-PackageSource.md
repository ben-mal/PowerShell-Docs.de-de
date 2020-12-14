---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/register-packagesource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PackageSource
ms.openlocfilehash: 323d59724507cfec5cde086e3b8e2a2c2f34b96e
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891311"
---
# <span data-ttu-id="4c34c-103">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="4c34c-103">Register-PackageSource</span></span>

## <span data-ttu-id="4c34c-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4c34c-104">SYNOPSIS</span></span>
<span data-ttu-id="4c34c-105">Fügt eine Paketquelle für einen angegebenen Paketanbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="4c34c-105">Adds a package source for a specified package provider.</span></span>

## <span data-ttu-id="4c34c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4c34c-106">SYNTAX</span></span>

### <span data-ttu-id="4c34c-107">Sourcebysearch</span><span class="sxs-lookup"><span data-stu-id="4c34c-107">SourceBySearch</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="4c34c-108">NuGet</span><span class="sxs-lookup"><span data-stu-id="4c34c-108">NuGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="4c34c-109">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="4c34c-109">PowerShellGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="4c34c-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4c34c-110">DESCRIPTION</span></span>

<span data-ttu-id="4c34c-111">Mit dem- `Register-PackageSource` Cmdlet wird eine Paketquelle für einen angegebenen Paketanbieter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4c34c-111">The `Register-PackageSource` cmdlet adds a package source for a specified package provider.</span></span> <span data-ttu-id="4c34c-112">Paketquellen werden immer von einem Paketanbieter verwaltet.</span><span class="sxs-lookup"><span data-stu-id="4c34c-112">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="4c34c-113">Wenn der Paketanbieter keine Paketquelle hinzufügen oder ersetzen kann, generiert der Anbieter eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="4c34c-113">If the package provider cannot add or replace a package source, the provider generates an error message.</span></span>

## <span data-ttu-id="4c34c-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4c34c-114">EXAMPLES</span></span>

### <span data-ttu-id="4c34c-115">Beispiel 1: Registrieren einer Paketquelle für den nuget-Anbieter</span><span class="sxs-lookup"><span data-stu-id="4c34c-115">Example 1: Register a package source for the NuGet provider</span></span>

<span data-ttu-id="4c34c-116">Mit diesem Befehl wird eine Paketquelle, ein webbasierter Speicherort für den **nuget** -Anbieter, registriert.</span><span class="sxs-lookup"><span data-stu-id="4c34c-116">This command registers a package source, a web-based location for the **NuGet** provider.</span></span> <span data-ttu-id="4c34c-117">Standardmäßig sind Quellen nicht vertrauenswürdig.</span><span class="sxs-lookup"><span data-stu-id="4c34c-117">By default, sources aren't trusted.</span></span> <span data-ttu-id="4c34c-118">Sie werden aufgefordert, zu bestätigen, dass die Quelle vertrauenswürdig ist, bevor Pakete installiert werden.</span><span class="sxs-lookup"><span data-stu-id="4c34c-118">You are prompted to confirm the source is trusted before packages are installed.</span></span> <span data-ttu-id="4c34c-119">Um die Standardeinstellung zu überschreiben, verwenden Sie den- `-Trusted` Parameter.</span><span class="sxs-lookup"><span data-stu-id="4c34c-119">To override the default, use the `-Trusted` parameter.</span></span>

```powershell
Register-PackageSource -Name MyNuGet -Location https://www.nuget.org/api/v2 -ProviderName NuGet
```

```Output
Name          ProviderName     IsTrusted  Location
----          ------------     ---------  --------
MyNuGet       NuGet            False      https://www.nuget.org/api/v2
```

## <span data-ttu-id="4c34c-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4c34c-120">PARAMETERS</span></span>

### <span data-ttu-id="4c34c-121">-Configfile</span><span class="sxs-lookup"><span data-stu-id="4c34c-121">-ConfigFile</span></span>

<span data-ttu-id="4c34c-122">Gibt eine Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="4c34c-122">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="4c34c-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="4c34c-123">-Credential</span></span>

<span data-ttu-id="4c34c-124">Gibt ein Benutzerkonto an, das über die Berechtigung zum Zugriff auf den authentifizierten Speicherort verfügt.</span><span class="sxs-lookup"><span data-stu-id="4c34c-124">Specifies a user account that has permission to access the authenticated location.</span></span>

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

### <span data-ttu-id="4c34c-125">-Force</span><span class="sxs-lookup"><span data-stu-id="4c34c-125">-Force</span></span>

<span data-ttu-id="4c34c-126">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4c34c-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="4c34c-127">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="4c34c-127">-ForceBootstrap</span></span>

<span data-ttu-id="4c34c-128">Gibt an, dass dieses Cmdlet den Paketanbieter automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="4c34c-128">Indicates that this cmdlet automatically installs the package provider.</span></span>

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

### <span data-ttu-id="4c34c-129">-Location</span><span class="sxs-lookup"><span data-stu-id="4c34c-129">-Location</span></span>

<span data-ttu-id="4c34c-130">Gibt den Quell Speicherort des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="4c34c-130">Specifies the package source location.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4c34c-131">-Name</span><span class="sxs-lookup"><span data-stu-id="4c34c-131">-Name</span></span>

<span data-ttu-id="4c34c-132">Gibt den Namen der Paketquelle an, die registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c34c-132">Specifies the name of the package source to register.</span></span>

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

### <span data-ttu-id="4c34c-133">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="4c34c-133">-PackageManagementProvider</span></span>

<span data-ttu-id="4c34c-134">Gibt den Paketverwaltung Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="4c34c-134">Specifies the Package Management provider.</span></span>

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

### <span data-ttu-id="4c34c-135">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="4c34c-135">-ProviderName</span></span>

<span data-ttu-id="4c34c-136">Gibt den Namen des Paket Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="4c34c-136">Specifies the package provider's name.</span></span>

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

### <span data-ttu-id="4c34c-137">-Proxy</span><span class="sxs-lookup"><span data-stu-id="4c34c-137">-Proxy</span></span>

<span data-ttu-id="4c34c-138">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4c34c-138">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="4c34c-139">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="4c34c-139">-ProxyCredential</span></span>

<span data-ttu-id="4c34c-140">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4c34c-140">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="4c34c-141">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="4c34c-141">-PublishLocation</span></span>

<span data-ttu-id="4c34c-142">Gibt den Veröffentlichungs Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="4c34c-142">Specifies the publish location.</span></span>

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

### <span data-ttu-id="4c34c-143">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="4c34c-143">-ScriptPublishLocation</span></span>

<span data-ttu-id="4c34c-144">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="4c34c-144">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="4c34c-145">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="4c34c-145">-ScriptSourceLocation</span></span>

<span data-ttu-id="4c34c-146">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="4c34c-146">Specifies the script source location.</span></span>

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

### <span data-ttu-id="4c34c-147">-Skipvalidate</span><span class="sxs-lookup"><span data-stu-id="4c34c-147">-SkipValidate</span></span>

<span data-ttu-id="4c34c-148">Ein Schalter, der die Validierung der Anmelde Informationen einer Paketquelle überspringt.</span><span class="sxs-lookup"><span data-stu-id="4c34c-148">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="4c34c-149">-Vertrauenswürdig</span><span class="sxs-lookup"><span data-stu-id="4c34c-149">-Trusted</span></span>

<span data-ttu-id="4c34c-150">Gibt an, dass die Paketquelle vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="4c34c-150">Indicates that the package source is trusted.</span></span>

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

### <span data-ttu-id="4c34c-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4c34c-151">-Confirm</span></span>

<span data-ttu-id="4c34c-152">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="4c34c-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4c34c-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4c34c-153">-WhatIf</span></span>

<span data-ttu-id="4c34c-154">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4c34c-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="4c34c-155">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4c34c-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4c34c-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4c34c-156">CommonParameters</span></span>

<span data-ttu-id="4c34c-157">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4c34c-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4c34c-158">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4c34c-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4c34c-159">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4c34c-159">INPUTS</span></span>

## <span data-ttu-id="4c34c-160">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4c34c-160">OUTPUTS</span></span>

## <span data-ttu-id="4c34c-161">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4c34c-161">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c34c-162">Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="4c34c-162">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="4c34c-163">Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4c34c-163">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="4c34c-164">Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="4c34c-164">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="4c34c-165">Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.</span><span class="sxs-lookup"><span data-stu-id="4c34c-165">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="4c34c-166">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4c34c-166">RELATED LINKS</span></span>

[<span data-ttu-id="4c34c-167">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="4c34c-167">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="4c34c-168">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="4c34c-168">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="4c34c-169">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="4c34c-169">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="4c34c-170">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="4c34c-170">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
