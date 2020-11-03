---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/set-psrepository?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSRepository
ms.openlocfilehash: 277bfc0ae4662e0c822ae7c227490eaf887c8ecb
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209948"
---
# <span data-ttu-id="90c40-103">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="90c40-103">Set-PSRepository</span></span>

## <span data-ttu-id="90c40-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="90c40-104">SYNOPSIS</span></span>
<span data-ttu-id="90c40-105">Legt Werte für ein registriertes Repository fest.</span><span class="sxs-lookup"><span data-stu-id="90c40-105">Sets values for a registered repository.</span></span>

## <span data-ttu-id="90c40-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="90c40-106">SYNTAX</span></span>

```
Set-PSRepository [-Name] <String> [[-SourceLocation] <Uri>] [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

## <span data-ttu-id="90c40-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="90c40-107">DESCRIPTION</span></span>

<span data-ttu-id="90c40-108">Mit dem- `Set-PSRepository` Cmdlet werden Werte für ein registriertes modulrepository festgelegt.</span><span class="sxs-lookup"><span data-stu-id="90c40-108">The `Set-PSRepository` cmdlet sets values for a registered module repository.</span></span> <span data-ttu-id="90c40-109">Die Einstellungen sind für den aktuellen Benutzer persistent und gelten für alle Versionen von PowerShell, die für diesen Benutzer installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="90c40-109">The settings are persistent for the current user and apply to all versions of PowerShell installed for that user.</span></span>

## <span data-ttu-id="90c40-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="90c40-110">EXAMPLES</span></span>

### <span data-ttu-id="90c40-111">Beispiel 1: Festlegen der Installations Richtlinie für ein Repository</span><span class="sxs-lookup"><span data-stu-id="90c40-111">Example 1: Set the installation policy for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -InstallationPolicy Trusted
```

<span data-ttu-id="90c40-112">Mit diesem Befehl wird die Installations Richtlinie für das **myinternalsource** -Repository auf " **vertrauenswürdig** " festgelegt, sodass Sie vor der Installation von Modulen aus dieser Quelle nicht aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="90c40-112">This command sets the installation policy for the **myInternalSource** repository to **Trusted** , so that you are not prompted before installing modules from that source.</span></span>

### <span data-ttu-id="90c40-113">Beispiel 2: Festlegen der Quell-und Veröffentlichungs Speicherorte für ein Repository</span><span class="sxs-lookup"><span data-stu-id="90c40-113">Example 2: Set the source and publish locations for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -SourceLocation 'https://someNuGetUrl.com/api/v2' -PublishLocation 'https://someNuGetUrl.com/api/v2/packages'
```

<span data-ttu-id="90c40-114">Mit diesem Befehl werden der Quell Speicherort und der Veröffentlichungsort für **myinternalsource** auf die angegebenen URIs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="90c40-114">This command sets the source location and publish location for **myInternalSource** to the specified URIs.</span></span>

## <span data-ttu-id="90c40-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="90c40-115">PARAMETERS</span></span>

### <span data-ttu-id="90c40-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="90c40-116">-Credential</span></span>

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

### <span data-ttu-id="90c40-117">-Installationpolicy</span><span class="sxs-lookup"><span data-stu-id="90c40-117">-InstallationPolicy</span></span>

<span data-ttu-id="90c40-118">Gibt die Installations Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="90c40-118">Specifies the installation policy.</span></span> <span data-ttu-id="90c40-119">Gültige Werte sind: **vertrauenswürdig** , **nicht vertrauenswürdig** .</span><span class="sxs-lookup"><span data-stu-id="90c40-119">Valid values are: **Trusted** , **Untrusted** .</span></span>

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

### <span data-ttu-id="90c40-120">-Name</span><span class="sxs-lookup"><span data-stu-id="90c40-120">-Name</span></span>

<span data-ttu-id="90c40-121">Gibt den Namen des Repository an.</span><span class="sxs-lookup"><span data-stu-id="90c40-121">Specifies the name of the repository.</span></span>

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

### <span data-ttu-id="90c40-122">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="90c40-122">-PackageManagementProvider</span></span>

<span data-ttu-id="90c40-123">Gibt den Paket Verwaltungs Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="90c40-123">Specifies the package management provider.</span></span>

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

### <span data-ttu-id="90c40-124">-Proxy</span><span class="sxs-lookup"><span data-stu-id="90c40-124">-Proxy</span></span>

<span data-ttu-id="90c40-125">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="90c40-125">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="90c40-126">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="90c40-126">-ProxyCredential</span></span>

<span data-ttu-id="90c40-127">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="90c40-127">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="90c40-128">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="90c40-128">-PublishLocation</span></span>

<span data-ttu-id="90c40-129">Gibt den URI des Veröffentlichungs Speicher Orts an.</span><span class="sxs-lookup"><span data-stu-id="90c40-129">Specifies the URI of the publish location.</span></span> <span data-ttu-id="90c40-130">Beispielsweise ist für nuget-basierte Depots der Veröffentlichungs Speicherort vergleichbar mit `https://someNuGetUrl.com/api/v2/Packages` .</span><span class="sxs-lookup"><span data-stu-id="90c40-130">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

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

### <span data-ttu-id="90c40-131">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="90c40-131">-ScriptPublishLocation</span></span>

<span data-ttu-id="90c40-132">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="90c40-132">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="90c40-133">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="90c40-133">-ScriptSourceLocation</span></span>

<span data-ttu-id="90c40-134">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="90c40-134">Specifies the script source location.</span></span>

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

### <span data-ttu-id="90c40-135">-Sourcelokation</span><span class="sxs-lookup"><span data-stu-id="90c40-135">-SourceLocation</span></span>

<span data-ttu-id="90c40-136">Gibt den URI zum Ermitteln und Installieren von Modulen aus diesem Repository an.</span><span class="sxs-lookup"><span data-stu-id="90c40-136">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="90c40-137">Beispielsweise ist der Quell Speicherort für nuget-basierte Depots vergleichbar mit `https://someNuGetUrl.com/api/v2` .</span><span class="sxs-lookup"><span data-stu-id="90c40-137">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

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

### <span data-ttu-id="90c40-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="90c40-138">CommonParameters</span></span>

<span data-ttu-id="90c40-139">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="90c40-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="90c40-140">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="90c40-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="90c40-141">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="90c40-141">INPUTS</span></span>

### <span data-ttu-id="90c40-142">System.String</span><span class="sxs-lookup"><span data-stu-id="90c40-142">System.String</span></span>

### <span data-ttu-id="90c40-143">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="90c40-143">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="90c40-144">System.Uri</span><span class="sxs-lookup"><span data-stu-id="90c40-144">System.Uri</span></span>

## <span data-ttu-id="90c40-145">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="90c40-145">OUTPUTS</span></span>

### <span data-ttu-id="90c40-146">System.Object</span><span class="sxs-lookup"><span data-stu-id="90c40-146">System.Object</span></span>

## <span data-ttu-id="90c40-147">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="90c40-147">NOTES</span></span>

## <span data-ttu-id="90c40-148">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="90c40-148">RELATED LINKS</span></span>

[<span data-ttu-id="90c40-149">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="90c40-149">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="90c40-150">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="90c40-150">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="90c40-151">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="90c40-151">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
