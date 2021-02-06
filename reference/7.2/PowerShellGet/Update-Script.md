---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Script
ms.openlocfilehash: 0fa537e463464fe055ea14aeab05cbb3ac5d1012
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99595532"
---
# <span data-ttu-id="a3372-102">Update-Script</span><span class="sxs-lookup"><span data-stu-id="a3372-102">Update-Script</span></span>

## <span data-ttu-id="a3372-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a3372-103">SYNOPSIS</span></span>
<span data-ttu-id="a3372-104">Aktualisiert ein Skript.</span><span class="sxs-lookup"><span data-stu-id="a3372-104">Updates a script.</span></span>

## <span data-ttu-id="a3372-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a3372-105">SYNTAX</span></span>

### <span data-ttu-id="a3372-106">Alle</span><span class="sxs-lookup"><span data-stu-id="a3372-106">All</span></span>

```
Update-Script [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a3372-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a3372-107">DESCRIPTION</span></span>

<span data-ttu-id="a3372-108">Mit dem- `Update-Script` Cmdlet wird ein Skript aktualisiert, das auf dem lokalen Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a3372-108">The `Update-Script` cmdlet updates a script that is installed on the local computer.</span></span> <span data-ttu-id="a3372-109">Das aktualisierte Skript wird aus demselben Repository wie die installierte Version heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="a3372-109">The updated script is downloaded from the same repository as the installed version.</span></span>

## <span data-ttu-id="a3372-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a3372-110">EXAMPLES</span></span>

### <span data-ttu-id="a3372-111">Beispiel 1: Aktualisieren des angegebenen Skripts</span><span class="sxs-lookup"><span data-stu-id="a3372-111">Example 1: Update the specified script</span></span>

<span data-ttu-id="a3372-112">In diesem Beispiel wird ein installiertes Skript aktualisiert und die aktualisierte Version angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3372-112">This example updates an installed script and displays the updated version.</span></span>

```powershell
Update-Script -Name UpdateManagement-Template -RequiredVersion 1.1
Get-InstalledScript -Name UpdateManagement-Template
```

```Output
Version   Name                       Repository   Description
-------   ----                       ----------   -----------
1.1       UpdateManagement-Template  PSGallery    This is a template script for Update Management...
```

<span data-ttu-id="a3372-113">`Update-Script` verwendet den **Name** -Parameter, um das zu Aktualisier gende Skript anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a3372-113">`Update-Script` uses the **Name** parameter to specify the script to update.</span></span> <span data-ttu-id="a3372-114">Der Requirements **dversion** -Parameter gibt die Skript Version an.</span><span class="sxs-lookup"><span data-stu-id="a3372-114">The **RequiredVersion** parameter specifies the script version.</span></span> <span data-ttu-id="a3372-115">`Get-InstalledScript` zeigt die aktualisierte Version des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="a3372-115">`Get-InstalledScript` displays the updated version of the script.</span></span>

## <span data-ttu-id="a3372-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a3372-116">PARAMETERS</span></span>

### <span data-ttu-id="a3372-117">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="a3372-117">-AcceptLicense</span></span>

<span data-ttu-id="a3372-118">Akzeptieren Sie den Lizenzvertrag während der Installation automatisch, wenn dies für das Paket erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a3372-118">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="a3372-119">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="a3372-119">-AllowPrerelease</span></span>

<span data-ttu-id="a3372-120">Ermöglicht das Aktualisieren eines Skripts mit dem neueren Skript, das als Vorabversion markiert ist.</span><span class="sxs-lookup"><span data-stu-id="a3372-120">Allows you to update a script with the newer script marked as a prerelease.</span></span>

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

### <span data-ttu-id="a3372-121">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a3372-121">-Confirm</span></span>

<span data-ttu-id="a3372-122">Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Update-Script` .</span><span class="sxs-lookup"><span data-stu-id="a3372-122">Prompts you for confirmation before running `Update-Script`.</span></span>

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

### <span data-ttu-id="a3372-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="a3372-123">-Credential</span></span>

<span data-ttu-id="a3372-124">Gibt ein Benutzerkonto an, das über die Berechtigung zum Aktualisieren eines Skripts verfügt.</span><span class="sxs-lookup"><span data-stu-id="a3372-124">Specifies a user account that has permission to update a script.</span></span>

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

### <span data-ttu-id="a3372-125">-Force</span><span class="sxs-lookup"><span data-stu-id="a3372-125">-Force</span></span>

<span data-ttu-id="a3372-126">Erzwingt das `Update-Script` Ausführen von, ohne dass eine Benutzer Bestätigung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="a3372-126">Forces `Update-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="a3372-127">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="a3372-127">-MaximumVersion</span></span>

<span data-ttu-id="a3372-128">Gibt die maximale oder neueste Version des zu aktualisierenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="a3372-128">Specifies the maximum, or newest, version of the script to update.</span></span> <span data-ttu-id="a3372-129">Die Parameter **MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3372-129">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a3372-130">-Name</span><span class="sxs-lookup"><span data-stu-id="a3372-130">-Name</span></span>

<span data-ttu-id="a3372-131">Gibt einen Skriptnamen oder ein Array von zu aktualisierenden Skriptnamen an.</span><span class="sxs-lookup"><span data-stu-id="a3372-131">Specifies one script name or an array of script names to update.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a3372-132">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a3372-132">-PassThru</span></span>

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

### <span data-ttu-id="a3372-133">-Proxy</span><span class="sxs-lookup"><span data-stu-id="a3372-133">-Proxy</span></span>

<span data-ttu-id="a3372-134">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit einer Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="a3372-134">Specifies a proxy server for the request rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="a3372-135">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="a3372-135">-ProxyCredential</span></span>

<span data-ttu-id="a3372-136">Gibt ein Benutzerkonto an, das über die Berechtigung zum Verwenden des Proxy Servers verfügt, der durch den **Proxy** Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a3372-136">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="a3372-137">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="a3372-137">-RequiredVersion</span></span>

<span data-ttu-id="a3372-138">Gibt die genaue Versionsnummer des zu aktualisierenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="a3372-138">Specifies the exact version number of the script to update.</span></span> <span data-ttu-id="a3372-139">Die Parameter **MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3372-139">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a3372-140">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a3372-140">-WhatIf</span></span>

<span data-ttu-id="a3372-141">Zeigt, was geschieht, wenn ausgeführt wird `Update-Script` .</span><span class="sxs-lookup"><span data-stu-id="a3372-141">Shows what would happen if `Update-Script` runs.</span></span> <span data-ttu-id="a3372-142">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a3372-142">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="a3372-143">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a3372-143">CommonParameters</span></span>

<span data-ttu-id="a3372-144">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a3372-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a3372-145">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a3372-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a3372-146">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a3372-146">INPUTS</span></span>

### <span data-ttu-id="a3372-147">System.String[]</span><span class="sxs-lookup"><span data-stu-id="a3372-147">System.String[]</span></span>

### <span data-ttu-id="a3372-148">System.String</span><span class="sxs-lookup"><span data-stu-id="a3372-148">System.String</span></span>

### <span data-ttu-id="a3372-149">System.Uri</span><span class="sxs-lookup"><span data-stu-id="a3372-149">System.Uri</span></span>

### <span data-ttu-id="a3372-150">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="a3372-150">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="a3372-151">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a3372-151">OUTPUTS</span></span>

### <span data-ttu-id="a3372-152">System.Object</span><span class="sxs-lookup"><span data-stu-id="a3372-152">System.Object</span></span>

## <span data-ttu-id="a3372-153">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a3372-153">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3372-154">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="a3372-154">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="a3372-155">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="a3372-155">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="a3372-156">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="a3372-156">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="a3372-157">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="a3372-157">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="a3372-158">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a3372-158">RELATED LINKS</span></span>

[<span data-ttu-id="a3372-159">Find-Script</span><span class="sxs-lookup"><span data-stu-id="a3372-159">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="a3372-160">Install-Script</span><span class="sxs-lookup"><span data-stu-id="a3372-160">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="a3372-161">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="a3372-161">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="a3372-162">Save-Script</span><span class="sxs-lookup"><span data-stu-id="a3372-162">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="a3372-163">Deinstallieren: Skript</span><span class="sxs-lookup"><span data-stu-id="a3372-163">Uninstall-Script</span></span>](Uninstall-Script.md)
