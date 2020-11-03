---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/register-psrepository?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSRepository
ms.openlocfilehash: be7ffa38a0409fa7ef0d01649b863a32732e34de
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211084"
---
# <span data-ttu-id="76f01-103">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="76f01-103">Register-PSRepository</span></span>

## <span data-ttu-id="76f01-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="76f01-104">SYNOPSIS</span></span>
<span data-ttu-id="76f01-105">Registriert ein PowerShell-Repository.</span><span class="sxs-lookup"><span data-stu-id="76f01-105">Registers a PowerShell repository.</span></span>

## <span data-ttu-id="76f01-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="76f01-106">SYNTAX</span></span>

### <span data-ttu-id="76f01-107">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="76f01-107">NameParameterSet (Default)</span></span>

```
Register-PSRepository [-Name] <String> [-SourceLocation] <Uri> [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

### <span data-ttu-id="76f01-108">Psgalleryparameterset</span><span class="sxs-lookup"><span data-stu-id="76f01-108">PSGalleryParameterSet</span></span>

```
Register-PSRepository [-Default] [-InstallationPolicy <String>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="76f01-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="76f01-109">DESCRIPTION</span></span>

<span data-ttu-id="76f01-110">Mit dem- `Register-PSRepository` Cmdlet wird das standardrepository für PowerShell-Module registriert.</span><span class="sxs-lookup"><span data-stu-id="76f01-110">The `Register-PSRepository` cmdlet registers the default repository for PowerShell modules.</span></span> <span data-ttu-id="76f01-111">Nachdem ein Repository registriert wurde, können Sie aus den `Find-Module` `Install-Module` Cmdlets, und darauf verweisen `Publish-Module` .</span><span class="sxs-lookup"><span data-stu-id="76f01-111">After a repository is registered, you can reference it from the `Find-Module`, `Install-Module`, and `Publish-Module` cmdlets.</span></span> <span data-ttu-id="76f01-112">Das registrierte Repository wird das standardrepository in `Find-Module` und `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="76f01-112">The registered repository becomes the default repository in `Find-Module` and `Install-Module`.</span></span>

<span data-ttu-id="76f01-113">Registrierte Repositorys sind benutzerspezifisch.</span><span class="sxs-lookup"><span data-stu-id="76f01-113">Registered repositories are user-specific.</span></span> <span data-ttu-id="76f01-114">Sie sind nicht in einem systemweiten Kontext registriert.</span><span class="sxs-lookup"><span data-stu-id="76f01-114">They are not registered in a system-wide context.</span></span>

<span data-ttu-id="76f01-115">Jedes registrierte Repository ist einem oneget-Paketanbieter zugeordnet, der mit dem **packagemanagementprovider** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="76f01-115">Each registered repository is associated with a OneGet package provider, which is specified with the **PackageManagementProvider** parameter.</span></span> <span data-ttu-id="76f01-116">Jeder oneget-Anbieter ist für die Interaktion mit einem bestimmten Repository konzipiert.</span><span class="sxs-lookup"><span data-stu-id="76f01-116">Each OneGet provider is designed to interact with a specific type of repository.</span></span> <span data-ttu-id="76f01-117">Der nuget-Anbieter ist beispielsweise für die Interaktion mit nuget-basierten Depots konzipiert.</span><span class="sxs-lookup"><span data-stu-id="76f01-117">For example, the NuGet provider is designed to interact with NuGet-based repositories.</span></span> <span data-ttu-id="76f01-118">Wenn ein oneget-Anbieter während der Registrierung nicht angegeben wird, versucht PowerShellGet, einen oneget-Anbieter zu finden, der den angegebenen Quell Speicherort verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="76f01-118">If a OneGet provider is not specified during registration, PowerShellGet attempts to find a OneGet provider that can handle the specified source location.</span></span>

## <span data-ttu-id="76f01-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="76f01-119">EXAMPLES</span></span>

### <span data-ttu-id="76f01-120">Beispiel 1: Registrieren eines Repository</span><span class="sxs-lookup"><span data-stu-id="76f01-120">Example 1: Register a repository</span></span>

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

<span data-ttu-id="76f01-121">Der erste Befehl wird `https://www.myget.org/F/powershellgetdemo/` als Repository für den aktuellen Benutzer registriert.</span><span class="sxs-lookup"><span data-stu-id="76f01-121">The first command registers `https://www.myget.org/F/powershellgetdemo/` as a repository for the current user.</span></span> <span data-ttu-id="76f01-122">Nachdem Sie mynugetsource registriert haben, können Sie beim Suchen, installieren und Veröffentlichen von Modulen explizit darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="76f01-122">After myNuGetSource is registered, you can explicitly reference it when searching for, installing, and publishing modules.</span></span> <span data-ttu-id="76f01-123">Da der **packagemanagementprovider** -Parameter nicht angegeben wird, ist das Repository nicht explizit einem oneget-Paketanbieter zugeordnet, sodass PowerShellGet verfügbare Paketanbieter abruft und dem nuget-Anbieter zuordnet.</span><span class="sxs-lookup"><span data-stu-id="76f01-123">Because the **PackageManagementProvider** parameter isn't specified, the repository is not explicitly associated with a OneGet package provider, so PowerShellGet polls available package providers and associates it with the NuGet provider.</span></span>

<span data-ttu-id="76f01-124">Mit dem zweiten Befehl werden registrierte Depots abgerufen und die Ergebnisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76f01-124">The second command gets registered repositories and displays the results.</span></span>

## <span data-ttu-id="76f01-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="76f01-125">PARAMETERS</span></span>

### <span data-ttu-id="76f01-126">-Credential</span><span class="sxs-lookup"><span data-stu-id="76f01-126">-Credential</span></span>

<span data-ttu-id="76f01-127">Gibt die Anmelde Informationen eines Kontos an, das über Rechte zum Registrieren eines Repository verfügt.</span><span class="sxs-lookup"><span data-stu-id="76f01-127">Specifies credentials of an account that has rights to register a repository.</span></span>

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

### <span data-ttu-id="76f01-128">-Default</span><span class="sxs-lookup"><span data-stu-id="76f01-128">-Default</span></span>

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

### <span data-ttu-id="76f01-129">-Installationpolicy</span><span class="sxs-lookup"><span data-stu-id="76f01-129">-InstallationPolicy</span></span>

<span data-ttu-id="76f01-130">Gibt die Installations Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="76f01-130">Specifies the installation policy.</span></span> <span data-ttu-id="76f01-131">Gültige Werte sind: vertrauenswürdig, nicht vertrauenswürdig.</span><span class="sxs-lookup"><span data-stu-id="76f01-131">Valid values are: Trusted, UnTrusted.</span></span> <span data-ttu-id="76f01-132">Der Standardwert ist nicht vertrauenswürdig.</span><span class="sxs-lookup"><span data-stu-id="76f01-132">The default value is UnTrusted.</span></span>

<span data-ttu-id="76f01-133">Die Installations Richtlinie eines Repository gibt das PowerShell-Verhalten bei der Installation aus diesem Repository an.</span><span class="sxs-lookup"><span data-stu-id="76f01-133">A repository's installation policy specifies PowerShell behavior when installing from that repository.</span></span> <span data-ttu-id="76f01-134">Wenn Sie Module aus einem nicht vertrauenswürdigen Repository installieren, wird der Benutzer zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="76f01-134">When installing modules from an UnTrusted repository, the user is prompted for confirmation.</span></span>

<span data-ttu-id="76f01-135">Sie können die **installationpolicy** mit dem- `Set-PSRepository` Cmdlet festlegen.</span><span class="sxs-lookup"><span data-stu-id="76f01-135">You can set the **InstallationPolicy** with the `Set-PSRepository` cmdlet.</span></span>

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

### <span data-ttu-id="76f01-136">-Name</span><span class="sxs-lookup"><span data-stu-id="76f01-136">-Name</span></span>

<span data-ttu-id="76f01-137">Gibt den Namen des zu registrierenden Repository an.</span><span class="sxs-lookup"><span data-stu-id="76f01-137">Specifies the name of the repository to register.</span></span> <span data-ttu-id="76f01-138">Sie können diesen Namen verwenden, um das Repository in Cmdlets anzugeben, `Find-Module` z `Install-Module` . b. und.</span><span class="sxs-lookup"><span data-stu-id="76f01-138">You can use this name to specify the repository in cmdlets such as `Find-Module` and `Install-Module`.</span></span>

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

### <span data-ttu-id="76f01-139">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="76f01-139">-PackageManagementProvider</span></span>

<span data-ttu-id="76f01-140">Gibt einen oneget-Paketanbieter an.</span><span class="sxs-lookup"><span data-stu-id="76f01-140">Specifies a OneGet package provider.</span></span> <span data-ttu-id="76f01-141">Wenn Sie keinen Wert für diesen Parameter angeben, fragt PowerShellGet verfügbare Paketanbieter ab und ordnet dieses Repository dem ersten Paketanbieter zu, der angibt, dass das Repository behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="76f01-141">If you don't specify a value for this parameter, PowerShellGet polls available package providers and associates this repository with the first package provider that indicates it can handle the repository.</span></span>

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

### <span data-ttu-id="76f01-142">-Proxy</span><span class="sxs-lookup"><span data-stu-id="76f01-142">-Proxy</span></span>

<span data-ttu-id="76f01-143">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="76f01-143">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="76f01-144">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="76f01-144">-ProxyCredential</span></span>

<span data-ttu-id="76f01-145">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="76f01-145">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="76f01-146">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="76f01-146">-PublishLocation</span></span>

<span data-ttu-id="76f01-147">Gibt den URI des Veröffentlichungs Speicher Orts an.</span><span class="sxs-lookup"><span data-stu-id="76f01-147">Specifies the URI of the publish location.</span></span> <span data-ttu-id="76f01-148">Beispielsweise ist für nuget-basierte Depots der Veröffentlichungs Speicherort vergleichbar mit `https://someNuGetUrl.com/api/v2/Packages` .</span><span class="sxs-lookup"><span data-stu-id="76f01-148">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

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

### <span data-ttu-id="76f01-149">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="76f01-149">-ScriptPublishLocation</span></span>

<span data-ttu-id="76f01-150">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="76f01-150">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="76f01-151">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="76f01-151">-ScriptSourceLocation</span></span>

<span data-ttu-id="76f01-152">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="76f01-152">Specifies the script source location.</span></span>

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

### <span data-ttu-id="76f01-153">-Sourcelokation</span><span class="sxs-lookup"><span data-stu-id="76f01-153">-SourceLocation</span></span>

<span data-ttu-id="76f01-154">Gibt den URI zum Ermitteln und Installieren von Modulen aus diesem Repository an.</span><span class="sxs-lookup"><span data-stu-id="76f01-154">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="76f01-155">Ein URI kann ein nuget-Server Feed (häufigste Situation), ein HTTP-, HTTPS-, FTP-oder Datei Speicherort sein.</span><span class="sxs-lookup"><span data-stu-id="76f01-155">A URI can be a NuGet server feed (most common situation), HTTP, HTTPS, FTP or file location.</span></span>

<span data-ttu-id="76f01-156">Beispielsweise ist der Quell Speicherort für nuget-basierte Depots vergleichbar mit `https://someNuGetUrl.com/api/v2` .</span><span class="sxs-lookup"><span data-stu-id="76f01-156">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

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

### <span data-ttu-id="76f01-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="76f01-157">CommonParameters</span></span>

<span data-ttu-id="76f01-158">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="76f01-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="76f01-159">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="76f01-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="76f01-160">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="76f01-160">INPUTS</span></span>

### <span data-ttu-id="76f01-161">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="76f01-161">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="76f01-162">System.Uri</span><span class="sxs-lookup"><span data-stu-id="76f01-162">System.Uri</span></span>

## <span data-ttu-id="76f01-163">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="76f01-163">OUTPUTS</span></span>

### <span data-ttu-id="76f01-164">System.Object</span><span class="sxs-lookup"><span data-stu-id="76f01-164">System.Object</span></span>

## <span data-ttu-id="76f01-165">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="76f01-165">NOTES</span></span>

## <span data-ttu-id="76f01-166">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="76f01-166">RELATED LINKS</span></span>

[<span data-ttu-id="76f01-167">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="76f01-167">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="76f01-168">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="76f01-168">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="76f01-169">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="76f01-169">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
