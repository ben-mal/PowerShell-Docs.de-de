---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Script
ms.openlocfilehash: 2cd8b51e1d4ef11a0a5f9e3542ff89e094854d8c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599221"
---
# <span data-ttu-id="46ece-102">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="46ece-102">Uninstall-Script</span></span>

## <span data-ttu-id="46ece-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="46ece-103">SYNOPSIS</span></span>
<span data-ttu-id="46ece-104">Deinstalliert ein Skript.</span><span class="sxs-lookup"><span data-stu-id="46ece-104">Uninstalls a script.</span></span>

## <span data-ttu-id="46ece-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="46ece-105">SYNTAX</span></span>

### <span data-ttu-id="46ece-106">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="46ece-106">NameParameterSet (Default)</span></span>

```
Uninstall-Script [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="46ece-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="46ece-107">InputObject</span></span>

```
Uninstall-Script [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="46ece-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="46ece-108">DESCRIPTION</span></span>

<span data-ttu-id="46ece-109">Mit dem- `Uninstall-Script` Cmdlet wird ein angegebenes Skript auf dem lokalen Computer deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="46ece-109">The `Uninstall-Script` cmdlet uninstalls a specified script from the local computer.</span></span>

## <span data-ttu-id="46ece-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="46ece-110">EXAMPLES</span></span>

### <span data-ttu-id="46ece-111">Beispiel 1: Deinstallieren eines Skripts</span><span class="sxs-lookup"><span data-stu-id="46ece-111">Example 1: Uninstall a script</span></span>

<span data-ttu-id="46ece-112">In diesem Beispiel wird ein Skript deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="46ece-112">This example uninstalls a script.</span></span>

```powershell
Uninstall-Script -Name UpdateManagement-Template
```

<span data-ttu-id="46ece-113">`Uninstall-Script` verwendet den **Name** -Parameter zum Angeben des Skripts, das vom lokalen Computer deinstalliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="46ece-113">`Uninstall-Script` uses the **Name** parameter to specify the script to uninstall from the local computer.</span></span>

### <span data-ttu-id="46ece-114">Beispiel 2: Verwenden der Pipeline zum Deinstallieren eines Skripts</span><span class="sxs-lookup"><span data-stu-id="46ece-114">Example 2: Use the pipeline to uninstall a script</span></span>

<span data-ttu-id="46ece-115">In diesem Beispiel wird die Pipeline zum Deinstallieren eines Skripts verwendet.</span><span class="sxs-lookup"><span data-stu-id="46ece-115">In this example, the pipeline is used to uninstall a script.</span></span>

```powershell
Get-InstalledScript -Name UpdateManagement-Template | Uninstall-Script
```

<span data-ttu-id="46ece-116">`Get-InstalledScript` verwendet den **Name** -Parameter, um das Skript anzugeben.</span><span class="sxs-lookup"><span data-stu-id="46ece-116">`Get-InstalledScript` uses the **Name** parameter to specify the script.</span></span> <span data-ttu-id="46ece-117">Das Objekt wird an die Pipeline gesendet, `Uninstall-Script` und das Skript wird deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="46ece-117">The object is sent down the pipeline to `Uninstall-Script` and the script is uninstalled.</span></span>

## <span data-ttu-id="46ece-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="46ece-118">PARAMETERS</span></span>

### <span data-ttu-id="46ece-119">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="46ece-119">-AllowPrerelease</span></span>

<span data-ttu-id="46ece-120">Ermöglicht das Deinstallieren eines als Vorabversion markierten Skripts.</span><span class="sxs-lookup"><span data-stu-id="46ece-120">Allows you to uninstall a script marked as a prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="46ece-121">-Confirm</span><span class="sxs-lookup"><span data-stu-id="46ece-121">-Confirm</span></span>

<span data-ttu-id="46ece-122">Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Uninstall-Script` .</span><span class="sxs-lookup"><span data-stu-id="46ece-122">Prompts you for confirmation before running `Uninstall-Script`.</span></span>

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

### <span data-ttu-id="46ece-123">-Force</span><span class="sxs-lookup"><span data-stu-id="46ece-123">-Force</span></span>

<span data-ttu-id="46ece-124">Erzwingt das `Uninstall-Script` Ausführen von, ohne dass eine Benutzer Bestätigung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="46ece-124">Forces `Uninstall-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="46ece-125">-InputObject</span><span class="sxs-lookup"><span data-stu-id="46ece-125">-InputObject</span></span>

<span data-ttu-id="46ece-126">Akzeptiert ein **PSRepositoryItemInfo** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="46ece-126">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="46ece-127">Geben `Get-InstalledScript` Sie z. b. eine Ausgabe an eine Variable ein, und verwenden Sie diese Variable als **Inputobject** -Argument.</span><span class="sxs-lookup"><span data-stu-id="46ece-127">For example, output `Get-InstalledScript` to a variable and use that variable as the **InputObject** argument.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="46ece-128">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="46ece-128">-MaximumVersion</span></span>

<span data-ttu-id="46ece-129">Gibt die maximale oder neueste Version des zu deinstallierenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="46ece-129">Specifies the maximum, or newest, version of the script to uninstall.</span></span> <span data-ttu-id="46ece-130">Die Parameter **MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="46ece-130">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="46ece-131">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="46ece-131">-MinimumVersion</span></span>

<span data-ttu-id="46ece-132">Gibt die Mindestversion des zu deinstallierenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="46ece-132">Specifies the minimum version of the script to uninstall.</span></span> <span data-ttu-id="46ece-133">Die Parameter **MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="46ece-133">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="46ece-134">-Name</span><span class="sxs-lookup"><span data-stu-id="46ece-134">-Name</span></span>

<span data-ttu-id="46ece-135">Gibt ein Array von Skriptnamen an, die deinstalliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="46ece-135">Specifies an array of script names to uninstall.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="46ece-136">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="46ece-136">-RequiredVersion</span></span>

<span data-ttu-id="46ece-137">Gibt die genaue Versionsnummer des zu deinstallierenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="46ece-137">Specifies the exact version number of the script to uninstall.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="46ece-138">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="46ece-138">-WhatIf</span></span>

<span data-ttu-id="46ece-139">Zeigt, was geschieht, wenn ausgeführt wird `Uninstall-Script` .</span><span class="sxs-lookup"><span data-stu-id="46ece-139">Shows what would happen if `Uninstall-Script` runs.</span></span> <span data-ttu-id="46ece-140">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="46ece-140">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="46ece-141">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="46ece-141">CommonParameters</span></span>

<span data-ttu-id="46ece-142">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="46ece-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="46ece-143">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="46ece-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="46ece-144">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="46ece-144">INPUTS</span></span>

### <span data-ttu-id="46ece-145">System.String[]</span><span class="sxs-lookup"><span data-stu-id="46ece-145">System.String[]</span></span>

### <span data-ttu-id="46ece-146">System. Management. Automation. psobject []</span><span class="sxs-lookup"><span data-stu-id="46ece-146">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="46ece-147">System.String</span><span class="sxs-lookup"><span data-stu-id="46ece-147">System.String</span></span>

## <span data-ttu-id="46ece-148">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="46ece-148">OUTPUTS</span></span>

### <span data-ttu-id="46ece-149">System.Object</span><span class="sxs-lookup"><span data-stu-id="46ece-149">System.Object</span></span>

## <span data-ttu-id="46ece-150">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="46ece-150">NOTES</span></span>

## <span data-ttu-id="46ece-151">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="46ece-151">RELATED LINKS</span></span>

[<span data-ttu-id="46ece-152">Find-Script</span><span class="sxs-lookup"><span data-stu-id="46ece-152">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="46ece-153">Install-Script</span><span class="sxs-lookup"><span data-stu-id="46ece-153">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="46ece-154">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="46ece-154">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="46ece-155">Save-Script</span><span class="sxs-lookup"><span data-stu-id="46ece-155">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="46ece-156">Update-Script</span><span class="sxs-lookup"><span data-stu-id="46ece-156">Update-Script</span></span>](Update-Script.md)

