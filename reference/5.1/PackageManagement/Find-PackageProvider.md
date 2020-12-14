---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-packageprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-PackageProvider
ms.openlocfilehash: f8ef02a4afb9491375e3a1c37a9b5846eef7e057
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892898"
---
# <span data-ttu-id="c77ba-103">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="c77ba-103">Find-PackageProvider</span></span>

## <span data-ttu-id="c77ba-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c77ba-104">SYNOPSIS</span></span>
<span data-ttu-id="c77ba-105">Gibt eine Liste von Paketverwaltung Paket Anbietern zurück, die für die Installation verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c77ba-105">Returns a list of Package Management package providers available for installation.</span></span>

## <span data-ttu-id="c77ba-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c77ba-106">SYNTAX</span></span>

```
Find-PackageProvider [[-Name] <String[]>] [-AllVersions] [-Source <String[]>] [-IncludeDependencies]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="c77ba-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c77ba-107">DESCRIPTION</span></span>

<span data-ttu-id="c77ba-108">Das Cmdlet " **Find-packageprovider** " findet übereinstimmende packagemanagement-Anbieter, die in mit PowerShellGet registrierten Paketquellen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c77ba-108">The **Find-PackageProvider** cmdlet finds matching PackageManagement providers that are available in package sources registered with PowerShellGet.</span></span>
<span data-ttu-id="c77ba-109">Dies sind Paketanbieter, die für die Installation mit dem Cmdlet „Install-PackageProvider“ verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c77ba-109">These are package providers available for installation with the Install-PackageProvider cmdlet.</span></span>
<span data-ttu-id="c77ba-110">Standardmäßig schließt dies Module ein, die im PowerShell-Katalog mit den Tags " **packagemanagement** " und " **Provider** " verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c77ba-110">By default, this includes modules available in the PowerShell Gallery with the **PackageManagement** and **Provider** tags.</span></span>

<span data-ttu-id="c77ba-111">" **Find-packageprovider** " findet auch übereinstimmende Paketverwaltung Anbieter, die im Paketverwaltung Azure-BLOB-Speicher verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c77ba-111">**Find-PackageProvider** also finds matching Package Management providers that are available in the Package Management Azure Blob store.</span></span>
<span data-ttu-id="c77ba-112">Verwenden Sie den Boots Trapper-Anbieter, um diese zu suchen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c77ba-112">Use the bootstrapper provider to find and install them.</span></span>

## <span data-ttu-id="c77ba-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c77ba-113">EXAMPLES</span></span>

### <span data-ttu-id="c77ba-114">Beispiel 1: Suchen aller verfügbaren Paketanbieter</span><span class="sxs-lookup"><span data-stu-id="c77ba-114">Example 1: Find all available package providers</span></span>

```
PS C:\> Find-PackageProvider
```

<span data-ttu-id="c77ba-115">Dieser Befehl ruft eine Liste aller Paketanbieter ab, die in den von Paketverwaltung unterstützten Depots verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c77ba-115">This command gets a list of all package providers that are available on the repositories supported by Package Management.</span></span>
<span data-ttu-id="c77ba-116">Standardmäßig sind diese Paketanbieter auf dem PowerShell-Katalog und mithilfe der Paketverwaltung Bootstrapping-Anwendung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c77ba-116">By default, those package providers are available on the PowerShell Gallery and by using the Package Management bootstrapping application.</span></span>

### <span data-ttu-id="c77ba-117">Beispiel 2: Suchen aller Versionen eines Anbieters</span><span class="sxs-lookup"><span data-stu-id="c77ba-117">Example 2: Find all versions of a provider</span></span>

```
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
```

<span data-ttu-id="c77ba-118">Dieser Befehl sucht alle Versionen des Paket Anbieters namens nuget.</span><span class="sxs-lookup"><span data-stu-id="c77ba-118">This command finds all versions of the package provider named Nuget.</span></span>

### <span data-ttu-id="c77ba-119">Beispiel 3: Suchen eines Anbieters aus einer angegebenen Quelle</span><span class="sxs-lookup"><span data-stu-id="c77ba-119">Example 3: Find a provider from a specified source</span></span>

```
PS C:\> Find-PackageProvider -Name "Gistprovider" -Source "PSGallery"
```

<span data-ttu-id="c77ba-120">Dieser Befehl sucht einen Paketanbieter, der mit einer angegebenen Paketquelle verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c77ba-120">This command finds a package provider available by using a specified package source.</span></span>

## <span data-ttu-id="c77ba-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c77ba-121">PARAMETERS</span></span>

### <span data-ttu-id="c77ba-122">-Allversions</span><span class="sxs-lookup"><span data-stu-id="c77ba-122">-AllVersions</span></span>

<span data-ttu-id="c77ba-123">Gibt an, dass dieses Cmdlet alle verfügbaren Versionen des Paket Anbieters zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c77ba-123">Indicates that this cmdlet returns all available versions of the package provider.</span></span>
<span data-ttu-id="c77ba-124">Standardmäßig gibt " **Find-packageprovider** " nur die neueste verfügbare Version zurück.</span><span class="sxs-lookup"><span data-stu-id="c77ba-124">By default, **Find-PackageProvider** only returns the newest available version.</span></span>

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

### <span data-ttu-id="c77ba-125">-Credential</span><span class="sxs-lookup"><span data-stu-id="c77ba-125">-Credential</span></span>

<span data-ttu-id="c77ba-126">Gibt ein Benutzerkonto an, das über die Berechtigung zum Suchen nach Paket Anbietern verfügt.</span><span class="sxs-lookup"><span data-stu-id="c77ba-126">Specifies a user account that has permission to search for package providers.</span></span>

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

### <span data-ttu-id="c77ba-127">-Force</span><span class="sxs-lookup"><span data-stu-id="c77ba-127">-Force</span></span>

<span data-ttu-id="c77ba-128">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c77ba-128">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="c77ba-129">Dies entspricht derzeit dem *forcebootstrap* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="c77ba-129">Currently, this is equivalent to the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="c77ba-130">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="c77ba-130">-ForceBootstrap</span></span>

<span data-ttu-id="c77ba-131">Gibt an, dass dieses Cmdlet Paketverwaltung zum automatischen Installieren des Paket Anbieters erzwingt.</span><span class="sxs-lookup"><span data-stu-id="c77ba-131">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="c77ba-132">-Includababhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="c77ba-132">-IncludeDependencies</span></span>

<span data-ttu-id="c77ba-133">Gibt an, dass dieses Cmdlet Abhängigkeiten enthält.</span><span class="sxs-lookup"><span data-stu-id="c77ba-133">Indicates that this cmdlet includes dependencies.</span></span>

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

### <span data-ttu-id="c77ba-134">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="c77ba-134">-MaximumVersion</span></span>

<span data-ttu-id="c77ba-135">Gibt die maximal zulässige Version des Paket Anbieters an, den Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="c77ba-135">Specifies the maximum allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="c77ba-136">Wenn Sie diesen Parameter nicht hinzufügen, findet " **Find-packageprovider** " die höchste verfügbare Version des Anbieters.</span><span class="sxs-lookup"><span data-stu-id="c77ba-136">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the provider.</span></span>

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

### <span data-ttu-id="c77ba-137">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="c77ba-137">-MinimumVersion</span></span>

<span data-ttu-id="c77ba-138">Gibt die mindestens zulässige Version des Paket Anbieters an, den Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="c77ba-138">Specifies the minimum allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="c77ba-139">Wenn Sie diesen Parameter nicht hinzufügen, findet " **Find-packageprovider** " die höchste verfügbare Version des Pakets, das auch eine beliebige maximale, vom *MaximumVersion* -Parameter angegebene Version erfüllt.</span><span class="sxs-lookup"><span data-stu-id="c77ba-139">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the package that also satisfies any maximum specified version specified by the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="c77ba-140">-Name</span><span class="sxs-lookup"><span data-stu-id="c77ba-140">-Name</span></span>

<span data-ttu-id="c77ba-141">Gibt einen oder mehrere Paketanbieter-Modulnamen oder Anbieter Namen mit Platzhalter Zeichen an.</span><span class="sxs-lookup"><span data-stu-id="c77ba-141">Specifies one or more package provider module names, or provider names with wildcard characters.</span></span>
<span data-ttu-id="c77ba-142">Trennen Sie mehrere Paketnamen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="c77ba-142">Separate multiple package names with commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="c77ba-143">-Proxy</span><span class="sxs-lookup"><span data-stu-id="c77ba-143">-Proxy</span></span>

<span data-ttu-id="c77ba-144">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="c77ba-144">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="c77ba-145">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="c77ba-145">-ProxyCredential</span></span>

<span data-ttu-id="c77ba-146">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c77ba-146">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="c77ba-147">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="c77ba-147">-RequiredVersion</span></span>

<span data-ttu-id="c77ba-148">Gibt die genau zulässige Version des Paket Anbieters an, den Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="c77ba-148">Specifies the exact allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="c77ba-149">Wenn Sie diesen Parameter nicht hinzufügen, findet " **Find-packageprovider** " die höchste verfügbare Version des Anbieters, die auch eine beliebige maximale Version erfüllt, die durch den *MaximumVersion* -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c77ba-149">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the provider that also satisfies any maximum version specified by the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="c77ba-150">-Source</span><span class="sxs-lookup"><span data-stu-id="c77ba-150">-Source</span></span>

<span data-ttu-id="c77ba-151">Gibt mindestens eine Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="c77ba-151">Specifies one or more package sources.</span></span>
<span data-ttu-id="c77ba-152">Mit dem Cmdlet "Get-PackageSource" können Sie eine Liste der verfügbaren Paketquellen erhalten.</span><span class="sxs-lookup"><span data-stu-id="c77ba-152">You can get a list of available package sources by using the Get-PackageSource cmdlet.</span></span>

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

### <span data-ttu-id="c77ba-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c77ba-153">CommonParameters</span></span>

<span data-ttu-id="c77ba-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c77ba-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c77ba-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c77ba-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c77ba-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c77ba-156">INPUTS</span></span>

## <span data-ttu-id="c77ba-157">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c77ba-157">OUTPUTS</span></span>

### <span data-ttu-id="c77ba-158">Microsoft. packagemanagement. Packaging. softwareidentity</span><span class="sxs-lookup"><span data-stu-id="c77ba-158">Microsoft.PackageManagement.Packaging.SoftwareIdentity</span></span>

<span data-ttu-id="c77ba-159">Dieses Cmdlet gibt ein **softwareidentity** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="c77ba-159">This cmdlet returns a **SoftwareIdentity** object.</span></span>
<span data-ttu-id="c77ba-160">Ein **softwareidentity** -Objekt kann an " **install-packageprovider** " weitergeleitet werden, um die Ergebnisse von " **Find-packageprovider**" zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c77ba-160">A **SoftwareIdentity** object can be piped into **Install-PackageProvider** to install the results of **Find-PackageProvider**.</span></span>

## <span data-ttu-id="c77ba-161">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c77ba-161">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c77ba-162">Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="c77ba-162">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="c77ba-163">Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c77ba-163">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="c77ba-164">Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="c77ba-164">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="c77ba-165">Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.</span><span class="sxs-lookup"><span data-stu-id="c77ba-165">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="c77ba-166">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c77ba-166">RELATED LINKS</span></span>

[<span data-ttu-id="c77ba-167">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="c77ba-167">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="c77ba-168">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="c77ba-168">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="c77ba-169">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="c77ba-169">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="c77ba-170">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="c77ba-170">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="c77ba-171">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="c77ba-171">Install-PackageProvider</span></span>](Install-PackageProvider.md)
