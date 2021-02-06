---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/register-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSRepository
ms.openlocfilehash: 179e672a099cfb92275795a0dc6129581a0e0299
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99599434"
---
# <span data-ttu-id="98378-102">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="98378-102">Register-PSRepository</span></span>

## <span data-ttu-id="98378-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="98378-103">SYNOPSIS</span></span>
<span data-ttu-id="98378-104">Registriert ein PowerShell-Repository.</span><span class="sxs-lookup"><span data-stu-id="98378-104">Registers a PowerShell repository.</span></span>

## <span data-ttu-id="98378-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="98378-105">SYNTAX</span></span>

### <span data-ttu-id="98378-106">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="98378-106">NameParameterSet (Default)</span></span>

```
Register-PSRepository [-Name] <String> [-SourceLocation] <Uri> [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

### <span data-ttu-id="98378-107">Psgalleryparameterset</span><span class="sxs-lookup"><span data-stu-id="98378-107">PSGalleryParameterSet</span></span>

```
Register-PSRepository [-Default] [-InstallationPolicy <String>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="98378-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="98378-108">DESCRIPTION</span></span>

<span data-ttu-id="98378-109">Mit dem- `Register-PSRepository` Cmdlet wird das standardrepository für PowerShell-Module registriert.</span><span class="sxs-lookup"><span data-stu-id="98378-109">The `Register-PSRepository` cmdlet registers the default repository for PowerShell modules.</span></span> <span data-ttu-id="98378-110">Nachdem ein Repository registriert wurde, können Sie aus den `Find-Module` `Install-Module` Cmdlets, und darauf verweisen `Publish-Module` .</span><span class="sxs-lookup"><span data-stu-id="98378-110">After a repository is registered, you can reference it from the `Find-Module`, `Install-Module`, and `Publish-Module` cmdlets.</span></span> <span data-ttu-id="98378-111">Das registrierte Repository wird das standardrepository in `Find-Module` und `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="98378-111">The registered repository becomes the default repository in `Find-Module` and `Install-Module`.</span></span>

<span data-ttu-id="98378-112">Registrierte Repositorys sind benutzerspezifisch.</span><span class="sxs-lookup"><span data-stu-id="98378-112">Registered repositories are user-specific.</span></span> <span data-ttu-id="98378-113">Sie sind nicht in einem systemweiten Kontext registriert.</span><span class="sxs-lookup"><span data-stu-id="98378-113">They are not registered in a system-wide context.</span></span>

<span data-ttu-id="98378-114">Jedes registrierte Repository ist einem oneget-Paketanbieter zugeordnet, der mit dem **packagemanagementprovider** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="98378-114">Each registered repository is associated with a OneGet package provider, which is specified with the **PackageManagementProvider** parameter.</span></span> <span data-ttu-id="98378-115">Jeder oneget-Anbieter ist für die Interaktion mit einem bestimmten Repository konzipiert.</span><span class="sxs-lookup"><span data-stu-id="98378-115">Each OneGet provider is designed to interact with a specific type of repository.</span></span> <span data-ttu-id="98378-116">Der nuget-Anbieter ist beispielsweise für die Interaktion mit nuget-basierten Depots konzipiert.</span><span class="sxs-lookup"><span data-stu-id="98378-116">For example, the NuGet provider is designed to interact with NuGet-based repositories.</span></span> <span data-ttu-id="98378-117">Wenn ein oneget-Anbieter während der Registrierung nicht angegeben wird, versucht PowerShellGet, einen oneget-Anbieter zu finden, der den angegebenen Quell Speicherort verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="98378-117">If a OneGet provider is not specified during registration, PowerShellGet attempts to find a OneGet provider that can handle the specified source location.</span></span>

## <span data-ttu-id="98378-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="98378-118">EXAMPLES</span></span>

### <span data-ttu-id="98378-119">Beispiel 1: Registrieren eines Repository</span><span class="sxs-lookup"><span data-stu-id="98378-119">Example 1: Register a repository</span></span>

```powershell
$parameters = @{
  Name = "myNuGetSource"
  SourceLocation = "https://www.myget.org/F/powershellgetdemo/api/v2"
  PublishLocation = "https://www.myget.org/F/powershellgetdemo/api/v2/Packages"
  InstallationPolicy = 'Trusted'
}
Register-PSRepository @parameters
Get-PSRepository
```

```Output
Name                SourceLocation          OneGetProvider       InstallationPolicy
----                --------------          --------------       ------------------
PSGallery           http://go.micro...      NuGet                Untrusted
myNuGetSource       https://myget.c...      NuGet                Trusted
```

<span data-ttu-id="98378-120">Der erste Befehl wird `https://www.myget.org/F/powershellgetdemo/` als Repository für den aktuellen Benutzer registriert.</span><span class="sxs-lookup"><span data-stu-id="98378-120">The first command registers `https://www.myget.org/F/powershellgetdemo/` as a repository for the current user.</span></span> <span data-ttu-id="98378-121">Nachdem Sie mynugetsource registriert haben, können Sie beim Suchen, installieren und Veröffentlichen von Modulen explizit darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="98378-121">After myNuGetSource is registered, you can explicitly reference it when searching for, installing, and publishing modules.</span></span> <span data-ttu-id="98378-122">Da der **packagemanagementprovider** -Parameter nicht angegeben wird, ist das Repository nicht explizit einem oneget-Paketanbieter zugeordnet, sodass PowerShellGet verfügbare Paketanbieter abruft und dem nuget-Anbieter zuordnet.</span><span class="sxs-lookup"><span data-stu-id="98378-122">Because the **PackageManagementProvider** parameter isn't specified, the repository is not explicitly associated with a OneGet package provider, so PowerShellGet polls available package providers and associates it with the NuGet provider.</span></span>

<span data-ttu-id="98378-123">Mit dem zweiten Befehl werden registrierte Depots abgerufen und die Ergebnisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98378-123">The second command gets registered repositories and displays the results.</span></span>

## <span data-ttu-id="98378-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="98378-124">PARAMETERS</span></span>

### <span data-ttu-id="98378-125">-Credential</span><span class="sxs-lookup"><span data-stu-id="98378-125">-Credential</span></span>

<span data-ttu-id="98378-126">Gibt die Anmelde Informationen eines Kontos an, das über Rechte zum Registrieren eines Repository verfügt.</span><span class="sxs-lookup"><span data-stu-id="98378-126">Specifies credentials of an account that has rights to register a repository.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="98378-127">-Default</span><span class="sxs-lookup"><span data-stu-id="98378-127">-Default</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PSGalleryParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98378-128">-Installationpolicy</span><span class="sxs-lookup"><span data-stu-id="98378-128">-InstallationPolicy</span></span>

<span data-ttu-id="98378-129">Gibt die Installations Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="98378-129">Specifies the installation policy.</span></span> <span data-ttu-id="98378-130">Gültige Werte sind: vertrauenswürdig, nicht vertrauenswürdig.</span><span class="sxs-lookup"><span data-stu-id="98378-130">Valid values are: Trusted, UnTrusted.</span></span> <span data-ttu-id="98378-131">Der Standardwert ist nicht vertrauenswürdig.</span><span class="sxs-lookup"><span data-stu-id="98378-131">The default value is UnTrusted.</span></span>

<span data-ttu-id="98378-132">Die Installations Richtlinie eines Repository gibt das PowerShell-Verhalten bei der Installation aus diesem Repository an.</span><span class="sxs-lookup"><span data-stu-id="98378-132">A repository's installation policy specifies PowerShell behavior when installing from that repository.</span></span> <span data-ttu-id="98378-133">Wenn Sie Module aus einem nicht vertrauenswürdigen Repository installieren, wird der Benutzer zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="98378-133">When installing modules from an UnTrusted repository, the user is prompted for confirmation.</span></span>

<span data-ttu-id="98378-134">Sie können die **installationpolicy** mit dem- `Set-PSRepository` Cmdlet festlegen.</span><span class="sxs-lookup"><span data-stu-id="98378-134">You can set the **InstallationPolicy** with the `Set-PSRepository` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Trusted, Untrusted

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98378-135">-Name</span><span class="sxs-lookup"><span data-stu-id="98378-135">-Name</span></span>

<span data-ttu-id="98378-136">Gibt den Namen des zu registrierenden Repository an.</span><span class="sxs-lookup"><span data-stu-id="98378-136">Specifies the name of the repository to register.</span></span> <span data-ttu-id="98378-137">Sie können diesen Namen verwenden, um das Repository in Cmdlets anzugeben, `Find-Module` z `Install-Module` . b. und.</span><span class="sxs-lookup"><span data-stu-id="98378-137">You can use this name to specify the repository in cmdlets such as `Find-Module` and `Install-Module`.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98378-138">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="98378-138">-PackageManagementProvider</span></span>

<span data-ttu-id="98378-139">Gibt einen oneget-Paketanbieter an.</span><span class="sxs-lookup"><span data-stu-id="98378-139">Specifies a OneGet package provider.</span></span> <span data-ttu-id="98378-140">Wenn Sie keinen Wert für diesen Parameter angeben, fragt PowerShellGet verfügbare Paketanbieter ab und ordnet dieses Repository dem ersten Paketanbieter zu, der angibt, dass das Repository behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="98378-140">If you don't specify a value for this parameter, PowerShellGet polls available package providers and associates this repository with the first package provider that indicates it can handle the repository.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98378-141">-Proxy</span><span class="sxs-lookup"><span data-stu-id="98378-141">-Proxy</span></span>

<span data-ttu-id="98378-142">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="98378-142">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="98378-143">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="98378-143">-ProxyCredential</span></span>

<span data-ttu-id="98378-144">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="98378-144">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="98378-145">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="98378-145">-PublishLocation</span></span>

<span data-ttu-id="98378-146">Gibt den URI des Veröffentlichungs Speicher Orts an.</span><span class="sxs-lookup"><span data-stu-id="98378-146">Specifies the URI of the publish location.</span></span> <span data-ttu-id="98378-147">Beispielsweise ist für nuget-basierte Depots der Veröffentlichungs Speicherort vergleichbar mit `https://someNuGetUrl.com/api/v2/Packages` .</span><span class="sxs-lookup"><span data-stu-id="98378-147">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98378-148">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="98378-148">-ScriptPublishLocation</span></span>

<span data-ttu-id="98378-149">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="98378-149">Specifies the script publish location.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98378-150">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="98378-150">-ScriptSourceLocation</span></span>

<span data-ttu-id="98378-151">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="98378-151">Specifies the script source location.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98378-152">-Sourcelokation</span><span class="sxs-lookup"><span data-stu-id="98378-152">-SourceLocation</span></span>

<span data-ttu-id="98378-153">Gibt den URI zum Ermitteln und Installieren von Modulen aus diesem Repository an.</span><span class="sxs-lookup"><span data-stu-id="98378-153">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="98378-154">Ein URI kann ein nuget-Server Feed (häufigste Situation), ein HTTP-, HTTPS-, FTP-oder Datei Speicherort sein.</span><span class="sxs-lookup"><span data-stu-id="98378-154">A URI can be a NuGet server feed (most common situation), HTTP, HTTPS, FTP or file location.</span></span>

<span data-ttu-id="98378-155">Beispielsweise ist der Quell Speicherort für nuget-basierte Depots vergleichbar mit `https://someNuGetUrl.com/api/v2` .</span><span class="sxs-lookup"><span data-stu-id="98378-155">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98378-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="98378-156">CommonParameters</span></span>

<span data-ttu-id="98378-157">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="98378-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="98378-158">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="98378-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="98378-159">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="98378-159">INPUTS</span></span>

### <span data-ttu-id="98378-160">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="98378-160">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="98378-161">System.Uri</span><span class="sxs-lookup"><span data-stu-id="98378-161">System.Uri</span></span>

## <span data-ttu-id="98378-162">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="98378-162">OUTPUTS</span></span>

### <span data-ttu-id="98378-163">System.Object</span><span class="sxs-lookup"><span data-stu-id="98378-163">System.Object</span></span>

## <span data-ttu-id="98378-164">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="98378-164">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98378-165">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="98378-165">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="98378-166">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="98378-166">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="98378-167">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="98378-167">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="98378-168">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="98378-168">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="98378-169">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="98378-169">RELATED LINKS</span></span>

[<span data-ttu-id="98378-170">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="98378-170">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="98378-171">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="98378-171">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="98378-172">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="98378-172">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
