---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/set-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSRepository
ms.openlocfilehash: d6f3901ba389ff910dcc808d2e4296032617052c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99602098"
---
# <span data-ttu-id="d9902-102">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="d9902-102">Set-PSRepository</span></span>

## <span data-ttu-id="d9902-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d9902-103">SYNOPSIS</span></span>
<span data-ttu-id="d9902-104">Legt Werte für ein registriertes Repository fest.</span><span class="sxs-lookup"><span data-stu-id="d9902-104">Sets values for a registered repository.</span></span>

## <span data-ttu-id="d9902-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d9902-105">SYNTAX</span></span>

```
Set-PSRepository [-Name] <String> [[-SourceLocation] <Uri>] [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

## <span data-ttu-id="d9902-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d9902-106">DESCRIPTION</span></span>

<span data-ttu-id="d9902-107">Mit dem- `Set-PSRepository` Cmdlet werden Werte für ein registriertes modulrepository festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d9902-107">The `Set-PSRepository` cmdlet sets values for a registered module repository.</span></span> <span data-ttu-id="d9902-108">Die Einstellungen sind für den aktuellen Benutzer persistent und gelten für alle Versionen von PowerShell, die für diesen Benutzer installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d9902-108">The settings are persistent for the current user and apply to all versions of PowerShell installed for that user.</span></span>

## <span data-ttu-id="d9902-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d9902-109">EXAMPLES</span></span>

### <span data-ttu-id="d9902-110">Beispiel 1: Festlegen der Installations Richtlinie für ein Repository</span><span class="sxs-lookup"><span data-stu-id="d9902-110">Example 1: Set the installation policy for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -InstallationPolicy Trusted
```

<span data-ttu-id="d9902-111">Mit diesem Befehl wird die Installations Richtlinie für das **myinternalsource** -Repository auf " **vertrauenswürdig**" festgelegt, sodass Sie vor der Installation von Modulen aus dieser Quelle nicht aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="d9902-111">This command sets the installation policy for the **myInternalSource** repository to **Trusted**, so that you are not prompted before installing modules from that source.</span></span>

### <span data-ttu-id="d9902-112">Beispiel 2: Festlegen der Quell-und Veröffentlichungs Speicherorte für ein Repository</span><span class="sxs-lookup"><span data-stu-id="d9902-112">Example 2: Set the source and publish locations for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -SourceLocation 'https://someNuGetUrl.com/api/v2' -PublishLocation 'https://someNuGetUrl.com/api/v2/packages'
```

<span data-ttu-id="d9902-113">Mit diesem Befehl werden der Quell Speicherort und der Veröffentlichungsort für **myinternalsource** auf die angegebenen URIs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d9902-113">This command sets the source location and publish location for **myInternalSource** to the specified URIs.</span></span>

## <span data-ttu-id="d9902-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d9902-114">PARAMETERS</span></span>

### <span data-ttu-id="d9902-115">-Credential</span><span class="sxs-lookup"><span data-stu-id="d9902-115">-Credential</span></span>

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

### <span data-ttu-id="d9902-116">-Installationpolicy</span><span class="sxs-lookup"><span data-stu-id="d9902-116">-InstallationPolicy</span></span>

<span data-ttu-id="d9902-117">Gibt die Installations Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="d9902-117">Specifies the installation policy.</span></span> <span data-ttu-id="d9902-118">Gültige Werte sind: **vertrauenswürdig**, **nicht vertrauenswürdig**.</span><span class="sxs-lookup"><span data-stu-id="d9902-118">Valid values are: **Trusted**, **Untrusted**.</span></span>

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

### <span data-ttu-id="d9902-119">-Name</span><span class="sxs-lookup"><span data-stu-id="d9902-119">-Name</span></span>

<span data-ttu-id="d9902-120">Gibt den Namen des Repository an.</span><span class="sxs-lookup"><span data-stu-id="d9902-120">Specifies the name of the repository.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d9902-121">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="d9902-121">-PackageManagementProvider</span></span>

<span data-ttu-id="d9902-122">Gibt den Paket Verwaltungs Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="d9902-122">Specifies the package management provider.</span></span>

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

### <span data-ttu-id="d9902-123">-Proxy</span><span class="sxs-lookup"><span data-stu-id="d9902-123">-Proxy</span></span>

<span data-ttu-id="d9902-124">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d9902-124">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="d9902-125">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="d9902-125">-ProxyCredential</span></span>

<span data-ttu-id="d9902-126">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d9902-126">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="d9902-127">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="d9902-127">-PublishLocation</span></span>

<span data-ttu-id="d9902-128">Gibt den URI des Veröffentlichungs Speicher Orts an.</span><span class="sxs-lookup"><span data-stu-id="d9902-128">Specifies the URI of the publish location.</span></span> <span data-ttu-id="d9902-129">Beispielsweise ist für nuget-basierte Depots der Veröffentlichungs Speicherort vergleichbar mit `https://someNuGetUrl.com/api/v2/Packages` .</span><span class="sxs-lookup"><span data-stu-id="d9902-129">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

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

### <span data-ttu-id="d9902-130">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="d9902-130">-ScriptPublishLocation</span></span>

<span data-ttu-id="d9902-131">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="d9902-131">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="d9902-132">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="d9902-132">-ScriptSourceLocation</span></span>

<span data-ttu-id="d9902-133">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="d9902-133">Specifies the script source location.</span></span>

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

### <span data-ttu-id="d9902-134">-Sourcelokation</span><span class="sxs-lookup"><span data-stu-id="d9902-134">-SourceLocation</span></span>

<span data-ttu-id="d9902-135">Gibt den URI zum Ermitteln und Installieren von Modulen aus diesem Repository an.</span><span class="sxs-lookup"><span data-stu-id="d9902-135">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="d9902-136">Beispielsweise ist der Quell Speicherort für nuget-basierte Depots vergleichbar mit `https://someNuGetUrl.com/api/v2` .</span><span class="sxs-lookup"><span data-stu-id="d9902-136">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9902-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d9902-137">CommonParameters</span></span>

<span data-ttu-id="d9902-138">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d9902-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d9902-139">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d9902-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d9902-140">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d9902-140">INPUTS</span></span>

### <span data-ttu-id="d9902-141">System.String</span><span class="sxs-lookup"><span data-stu-id="d9902-141">System.String</span></span>

### <span data-ttu-id="d9902-142">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="d9902-142">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="d9902-143">System.Uri</span><span class="sxs-lookup"><span data-stu-id="d9902-143">System.Uri</span></span>

## <span data-ttu-id="d9902-144">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d9902-144">OUTPUTS</span></span>

### <span data-ttu-id="d9902-145">System.Object</span><span class="sxs-lookup"><span data-stu-id="d9902-145">System.Object</span></span>

## <span data-ttu-id="d9902-146">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d9902-146">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9902-147">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="d9902-147">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="d9902-148">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="d9902-148">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="d9902-149">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="d9902-149">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="d9902-150">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="d9902-150">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="d9902-151">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d9902-151">RELATED LINKS</span></span>

[<span data-ttu-id="d9902-152">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="d9902-152">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="d9902-153">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="d9902-153">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="d9902-154">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="d9902-154">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
