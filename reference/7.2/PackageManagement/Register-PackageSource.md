---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/register-packagesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PackageSource
ms.openlocfilehash: 76b3bd49f81f42cc80f4127f4b549acddcd1d906
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99596555"
---
# <span data-ttu-id="6a2ec-102">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="6a2ec-102">Register-PackageSource</span></span>

## <span data-ttu-id="6a2ec-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6a2ec-103">SYNOPSIS</span></span>
<span data-ttu-id="6a2ec-104">Fügt eine Paketquelle für einen angegebenen Paketanbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-104">Adds a package source for a specified package provider.</span></span>

## <span data-ttu-id="6a2ec-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6a2ec-105">SYNTAX</span></span>

### <span data-ttu-id="6a2ec-106">Sourcebysearch</span><span class="sxs-lookup"><span data-stu-id="6a2ec-106">SourceBySearch</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="6a2ec-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="6a2ec-107">NuGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="6a2ec-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="6a2ec-108">PowerShellGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="6a2ec-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6a2ec-109">DESCRIPTION</span></span>

<span data-ttu-id="6a2ec-110">Mit dem- `Register-PackageSource` Cmdlet wird eine Paketquelle für einen angegebenen Paketanbieter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-110">The `Register-PackageSource` cmdlet adds a package source for a specified package provider.</span></span> <span data-ttu-id="6a2ec-111">Paketquellen werden immer von einem Paketanbieter verwaltet.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-111">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="6a2ec-112">Wenn der Paketanbieter keine Paketquelle hinzufügen oder ersetzen kann, generiert der Anbieter eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-112">If the package provider cannot add or replace a package source, the provider generates an error message.</span></span>

## <span data-ttu-id="6a2ec-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6a2ec-113">EXAMPLES</span></span>

### <span data-ttu-id="6a2ec-114">Beispiel 1: Registrieren einer Paketquelle für den nuget-Anbieter</span><span class="sxs-lookup"><span data-stu-id="6a2ec-114">Example 1: Register a package source for the NuGet provider</span></span>

<span data-ttu-id="6a2ec-115">Mit diesem Befehl wird eine Paketquelle, ein webbasierter Speicherort für den **nuget** -Anbieter, registriert.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-115">This command registers a package source, a web-based location for the **NuGet** provider.</span></span> <span data-ttu-id="6a2ec-116">Standardmäßig sind Quellen nicht vertrauenswürdig.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-116">By default, sources aren't trusted.</span></span> <span data-ttu-id="6a2ec-117">Sie werden aufgefordert, zu bestätigen, dass die Quelle vertrauenswürdig ist, bevor Pakete installiert werden.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-117">You are prompted to confirm the source is trusted before packages are installed.</span></span> <span data-ttu-id="6a2ec-118">Um die Standardeinstellung zu überschreiben, verwenden Sie den- `-Trusted` Parameter.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-118">To override the default, use the `-Trusted` parameter.</span></span>

```powershell
Register-PackageSource -Name MyNuGet -Location https://www.nuget.org/api/v2 -ProviderName NuGet
```

```Output
Name          ProviderName     IsTrusted  Location
----          ------------     ---------  --------
MyNuGet       NuGet            False      https://www.nuget.org/api/v2
```

## <span data-ttu-id="6a2ec-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6a2ec-119">PARAMETERS</span></span>

### <span data-ttu-id="6a2ec-120">-Configfile</span><span class="sxs-lookup"><span data-stu-id="6a2ec-120">-ConfigFile</span></span>

<span data-ttu-id="6a2ec-121">Gibt eine Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-121">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="6a2ec-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="6a2ec-122">-Credential</span></span>

<span data-ttu-id="6a2ec-123">Gibt ein Benutzerkonto an, das über die Berechtigung zum Zugriff auf den authentifizierten Speicherort verfügt.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-123">Specifies a user account that has permission to access the authenticated location.</span></span>

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

### <span data-ttu-id="6a2ec-124">-Force</span><span class="sxs-lookup"><span data-stu-id="6a2ec-124">-Force</span></span>

<span data-ttu-id="6a2ec-125">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-125">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="6a2ec-126">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="6a2ec-126">-ForceBootstrap</span></span>

<span data-ttu-id="6a2ec-127">Gibt an, dass dieses Cmdlet den Paketanbieter automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-127">Indicates that this cmdlet automatically installs the package provider.</span></span>

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

### <span data-ttu-id="6a2ec-128">-Location</span><span class="sxs-lookup"><span data-stu-id="6a2ec-128">-Location</span></span>

<span data-ttu-id="6a2ec-129">Gibt den Quell Speicherort des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-129">Specifies the package source location.</span></span>

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

### <span data-ttu-id="6a2ec-130">-Name</span><span class="sxs-lookup"><span data-stu-id="6a2ec-130">-Name</span></span>

<span data-ttu-id="6a2ec-131">Gibt den Namen der Paketquelle an, die registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-131">Specifies the name of the package source to register.</span></span>

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

### <span data-ttu-id="6a2ec-132">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="6a2ec-132">-PackageManagementProvider</span></span>

<span data-ttu-id="6a2ec-133">Gibt den Paketverwaltung Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-133">Specifies the Package Management provider.</span></span>

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

### <span data-ttu-id="6a2ec-134">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="6a2ec-134">-ProviderName</span></span>

<span data-ttu-id="6a2ec-135">Gibt den Namen des Paket Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-135">Specifies the package provider's name.</span></span>

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

### <span data-ttu-id="6a2ec-136">-Proxy</span><span class="sxs-lookup"><span data-stu-id="6a2ec-136">-Proxy</span></span>

<span data-ttu-id="6a2ec-137">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-137">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="6a2ec-138">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="6a2ec-138">-ProxyCredential</span></span>

<span data-ttu-id="6a2ec-139">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-139">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="6a2ec-140">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="6a2ec-140">-PublishLocation</span></span>

<span data-ttu-id="6a2ec-141">Gibt den Veröffentlichungs Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-141">Specifies the publish location.</span></span>

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

### <span data-ttu-id="6a2ec-142">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="6a2ec-142">-ScriptPublishLocation</span></span>

<span data-ttu-id="6a2ec-143">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-143">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="6a2ec-144">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="6a2ec-144">-ScriptSourceLocation</span></span>

<span data-ttu-id="6a2ec-145">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-145">Specifies the script source location.</span></span>

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

### <span data-ttu-id="6a2ec-146">-Skipvalidate</span><span class="sxs-lookup"><span data-stu-id="6a2ec-146">-SkipValidate</span></span>

<span data-ttu-id="6a2ec-147">Ein Schalter, der die Validierung der Anmelde Informationen einer Paketquelle überspringt.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-147">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="6a2ec-148">-Vertrauenswürdig</span><span class="sxs-lookup"><span data-stu-id="6a2ec-148">-Trusted</span></span>

<span data-ttu-id="6a2ec-149">Gibt an, dass die Paketquelle vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-149">Indicates that the package source is trusted.</span></span>

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

### <span data-ttu-id="6a2ec-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6a2ec-150">-Confirm</span></span>

<span data-ttu-id="6a2ec-151">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6a2ec-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6a2ec-152">-WhatIf</span></span>

<span data-ttu-id="6a2ec-153">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-153">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6a2ec-154">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6a2ec-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6a2ec-155">CommonParameters</span></span>

<span data-ttu-id="6a2ec-156">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6a2ec-157">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6a2ec-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6a2ec-158">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6a2ec-158">INPUTS</span></span>

## <span data-ttu-id="6a2ec-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6a2ec-159">OUTPUTS</span></span>

## <span data-ttu-id="6a2ec-160">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6a2ec-160">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a2ec-161">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-161">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="6a2ec-162">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="6a2ec-162">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="6a2ec-163">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="6a2ec-163">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="6a2ec-164">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="6a2ec-164">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="6a2ec-165">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6a2ec-165">RELATED LINKS</span></span>

[<span data-ttu-id="6a2ec-166">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="6a2ec-166">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="6a2ec-167">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="6a2ec-167">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="6a2ec-168">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="6a2ec-168">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="6a2ec-169">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="6a2ec-169">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
