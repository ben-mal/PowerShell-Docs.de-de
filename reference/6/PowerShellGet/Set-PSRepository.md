---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/set-psrepository?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSRepository
ms.openlocfilehash: 4dcd3d1824612de5dd5195491c5034a74c02cdea
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215919"
---
# <span data-ttu-id="5451f-103">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="5451f-103">Set-PSRepository</span></span>

## <span data-ttu-id="5451f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5451f-104">SYNOPSIS</span></span>
<span data-ttu-id="5451f-105">Legt Werte für ein registriertes Repository fest.</span><span class="sxs-lookup"><span data-stu-id="5451f-105">Sets values for a registered repository.</span></span>

## <span data-ttu-id="5451f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5451f-106">SYNTAX</span></span>

```
Set-PSRepository [-Name] <String> [[-SourceLocation] <Uri>] [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

## <span data-ttu-id="5451f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5451f-107">DESCRIPTION</span></span>

<span data-ttu-id="5451f-108">Mit dem- `Set-PSRepository` Cmdlet werden Werte für ein registriertes modulrepository festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5451f-108">The `Set-PSRepository` cmdlet sets values for a registered module repository.</span></span> <span data-ttu-id="5451f-109">Die Einstellungen sind für den aktuellen Benutzer persistent und gelten für alle Versionen von PowerShell, die für diesen Benutzer installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5451f-109">The settings are persistent for the current user and apply to all versions of PowerShell installed for that user.</span></span>

## <span data-ttu-id="5451f-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5451f-110">EXAMPLES</span></span>

### <span data-ttu-id="5451f-111">Beispiel 1: Festlegen der Installations Richtlinie für ein Repository</span><span class="sxs-lookup"><span data-stu-id="5451f-111">Example 1: Set the installation policy for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -InstallationPolicy Trusted
```

<span data-ttu-id="5451f-112">Mit diesem Befehl wird die Installations Richtlinie für das **myinternalsource** -Repository auf " **vertrauenswürdig** " festgelegt, sodass Sie vor der Installation von Modulen aus dieser Quelle nicht aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="5451f-112">This command sets the installation policy for the **myInternalSource** repository to **Trusted** , so that you are not prompted before installing modules from that source.</span></span>

### <span data-ttu-id="5451f-113">Beispiel 2: Festlegen der Quell-und Veröffentlichungs Speicherorte für ein Repository</span><span class="sxs-lookup"><span data-stu-id="5451f-113">Example 2: Set the source and publish locations for a repository</span></span>

```powershell
Set-PSRepository -Name "myInternalSource" -SourceLocation 'https://someNuGetUrl.com/api/v2' -PublishLocation 'https://someNuGetUrl.com/api/v2/packages'
```

<span data-ttu-id="5451f-114">Mit diesem Befehl werden der Quell Speicherort und der Veröffentlichungsort für **myinternalsource** auf die angegebenen URIs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5451f-114">This command sets the source location and publish location for **myInternalSource** to the specified URIs.</span></span>

## <span data-ttu-id="5451f-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5451f-115">PARAMETERS</span></span>

### <span data-ttu-id="5451f-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="5451f-116">-Credential</span></span>

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

### <span data-ttu-id="5451f-117">-Installationpolicy</span><span class="sxs-lookup"><span data-stu-id="5451f-117">-InstallationPolicy</span></span>

<span data-ttu-id="5451f-118">Gibt die Installations Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="5451f-118">Specifies the installation policy.</span></span> <span data-ttu-id="5451f-119">Gültige Werte sind: **vertrauenswürdig** , **nicht vertrauenswürdig** .</span><span class="sxs-lookup"><span data-stu-id="5451f-119">Valid values are: **Trusted** , **Untrusted** .</span></span>

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

### <span data-ttu-id="5451f-120">-Name</span><span class="sxs-lookup"><span data-stu-id="5451f-120">-Name</span></span>

<span data-ttu-id="5451f-121">Gibt den Namen des Repository an.</span><span class="sxs-lookup"><span data-stu-id="5451f-121">Specifies the name of the repository.</span></span>

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

### <span data-ttu-id="5451f-122">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="5451f-122">-PackageManagementProvider</span></span>

<span data-ttu-id="5451f-123">Gibt den Paket Verwaltungs Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="5451f-123">Specifies the package management provider.</span></span>

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

### <span data-ttu-id="5451f-124">-Proxy</span><span class="sxs-lookup"><span data-stu-id="5451f-124">-Proxy</span></span>

<span data-ttu-id="5451f-125">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="5451f-125">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="5451f-126">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="5451f-126">-ProxyCredential</span></span>

<span data-ttu-id="5451f-127">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5451f-127">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="5451f-128">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="5451f-128">-PublishLocation</span></span>

<span data-ttu-id="5451f-129">Gibt den URI des Veröffentlichungs Speicher Orts an.</span><span class="sxs-lookup"><span data-stu-id="5451f-129">Specifies the URI of the publish location.</span></span> <span data-ttu-id="5451f-130">Beispielsweise ist für nuget-basierte Depots der Veröffentlichungs Speicherort vergleichbar mit `https://someNuGetUrl.com/api/v2/Packages` .</span><span class="sxs-lookup"><span data-stu-id="5451f-130">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

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

### <span data-ttu-id="5451f-131">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="5451f-131">-ScriptPublishLocation</span></span>

<span data-ttu-id="5451f-132">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="5451f-132">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="5451f-133">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="5451f-133">-ScriptSourceLocation</span></span>

<span data-ttu-id="5451f-134">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="5451f-134">Specifies the script source location.</span></span>

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

### <span data-ttu-id="5451f-135">-Sourcelokation</span><span class="sxs-lookup"><span data-stu-id="5451f-135">-SourceLocation</span></span>

<span data-ttu-id="5451f-136">Gibt den URI zum Ermitteln und Installieren von Modulen aus diesem Repository an.</span><span class="sxs-lookup"><span data-stu-id="5451f-136">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="5451f-137">Beispielsweise ist der Quell Speicherort für nuget-basierte Depots vergleichbar mit `https://someNuGetUrl.com/api/v2` .</span><span class="sxs-lookup"><span data-stu-id="5451f-137">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

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

### <span data-ttu-id="5451f-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5451f-138">CommonParameters</span></span>

<span data-ttu-id="5451f-139">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5451f-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5451f-140">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5451f-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5451f-141">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5451f-141">INPUTS</span></span>

### <span data-ttu-id="5451f-142">System.String</span><span class="sxs-lookup"><span data-stu-id="5451f-142">System.String</span></span>

### <span data-ttu-id="5451f-143">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="5451f-143">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="5451f-144">System.Uri</span><span class="sxs-lookup"><span data-stu-id="5451f-144">System.Uri</span></span>

## <span data-ttu-id="5451f-145">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5451f-145">OUTPUTS</span></span>

### <span data-ttu-id="5451f-146">System.Object</span><span class="sxs-lookup"><span data-stu-id="5451f-146">System.Object</span></span>

## <span data-ttu-id="5451f-147">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5451f-147">NOTES</span></span>

## <span data-ttu-id="5451f-148">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5451f-148">RELATED LINKS</span></span>

[<span data-ttu-id="5451f-149">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="5451f-149">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="5451f-150">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="5451f-150">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="5451f-151">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="5451f-151">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
