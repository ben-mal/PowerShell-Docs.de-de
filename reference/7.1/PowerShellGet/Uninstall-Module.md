---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Module
ms.openlocfilehash: 77a89a9189d3ae8f7c3450bdddbe9456b4e941c7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212620"
---
# <span data-ttu-id="68916-103">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="68916-103">Uninstall-Module</span></span>

## <span data-ttu-id="68916-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="68916-104">SYNOPSIS</span></span>
<span data-ttu-id="68916-105">Deinstalliert ein Modul.</span><span class="sxs-lookup"><span data-stu-id="68916-105">Uninstalls a module.</span></span>

## <span data-ttu-id="68916-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="68916-106">SYNTAX</span></span>

### <span data-ttu-id="68916-107">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="68916-107">NameParameterSet (Default)</span></span>

```
Uninstall-Module [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="68916-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="68916-108">InputObject</span></span>

```
Uninstall-Module [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="68916-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="68916-109">DESCRIPTION</span></span>

<span data-ttu-id="68916-110">Mit dem- `Uninstall-Module` Cmdlet wird ein angegebenes Modul vom lokalen Computer deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="68916-110">The `Uninstall-Module` cmdlet uninstalls a specified module from the local computer.</span></span> <span data-ttu-id="68916-111">Sie können ein Modul nicht deinstallieren, wenn es über andere Module als Abhängigkeiten verfügt.</span><span class="sxs-lookup"><span data-stu-id="68916-111">You can't uninstall a module if it has other modules as dependencies.</span></span>

## <span data-ttu-id="68916-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="68916-112">EXAMPLES</span></span>

### <span data-ttu-id="68916-113">Beispiel 1: Deinstallieren eines Moduls</span><span class="sxs-lookup"><span data-stu-id="68916-113">Example 1: Uninstall a module</span></span>

<span data-ttu-id="68916-114">In diesem Beispiel wird ein Modul deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="68916-114">This example uninstalls a module.</span></span>

```powershell
Uninstall-Module -Name SpeculationControl
```

<span data-ttu-id="68916-115">`Uninstall-Module` verwendet den **Name** -Parameter, um das Modul anzugeben, das vom lokalen Computer deinstalliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="68916-115">`Uninstall-Module` uses the **Name** parameter to specify the module to uninstall from the local computer.</span></span>

### <span data-ttu-id="68916-116">Beispiel 2: Verwenden der Pipeline zum Deinstallieren eines Moduls</span><span class="sxs-lookup"><span data-stu-id="68916-116">Example 2: Use the pipeline to uninstall a module</span></span>

<span data-ttu-id="68916-117">In diesem Beispiel wird die Pipeline zum Deinstallieren eines Moduls verwendet.</span><span class="sxs-lookup"><span data-stu-id="68916-117">In this example, the pipeline is used to uninstall a module.</span></span>

```powershell
Get-InstalledModule -Name SpeculationControl | Uninstall-Module
```

<span data-ttu-id="68916-118">`Get-InstalledModule` verwendet den **Name** -Parameter, um das Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="68916-118">`Get-InstalledModule` uses the **Name** parameter to specify the module.</span></span> <span data-ttu-id="68916-119">Das Objekt wird über die Pipeline an gesendet `Uninstall-Module` und deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="68916-119">The object is sent down the pipeline to `Uninstall-Module` and is uninstalled.</span></span>

## <span data-ttu-id="68916-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="68916-120">PARAMETERS</span></span>

### <span data-ttu-id="68916-121">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="68916-121">-AllowPrerelease</span></span>

<span data-ttu-id="68916-122">Ermöglicht das Deinstallieren eines als Vorabversion markierten Moduls.</span><span class="sxs-lookup"><span data-stu-id="68916-122">Allows you to uninstall a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="68916-123">-Allversions</span><span class="sxs-lookup"><span data-stu-id="68916-123">-AllVersions</span></span>

<span data-ttu-id="68916-124">Gibt an, dass Sie alle verfügbaren Versionen eines Moduls einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="68916-124">Specifies that you want to include all available versions of a module.</span></span> <span data-ttu-id="68916-125">Der **allversions** -Parameter kann nicht mit den Parametern **MinimumVersion** , **MaximumVersion** oder Requirements **dversion** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68916-125">You can't use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="68916-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="68916-126">-Confirm</span></span>

<span data-ttu-id="68916-127">Fordert Sie zur Bestätigung auf, bevor Sie den ausführen `Uninstall-Module` .</span><span class="sxs-lookup"><span data-stu-id="68916-127">Prompts you for confirmation before running the `Uninstall-Module`.</span></span>

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

### <span data-ttu-id="68916-128">-Force</span><span class="sxs-lookup"><span data-stu-id="68916-128">-Force</span></span>

<span data-ttu-id="68916-129">Erzwingt das `Uninstall-Module` Ausführen von, ohne dass eine Benutzer Bestätigung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="68916-129">Forces `Uninstall-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="68916-130">-InputObject</span><span class="sxs-lookup"><span data-stu-id="68916-130">-InputObject</span></span>

<span data-ttu-id="68916-131">Akzeptiert ein **PSRepositoryItemInfo** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="68916-131">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="68916-132">Geben `Get-InstalledModule` Sie z. b. eine Ausgabe an eine Variable ein, und verwenden Sie diese Variable als **Inputobject** -Argument.</span><span class="sxs-lookup"><span data-stu-id="68916-132">For example, output `Get-InstalledModule` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="68916-133">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="68916-133">-MaximumVersion</span></span>

<span data-ttu-id="68916-134">Gibt die maximale oder neueste Version des zu deinstallierenden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="68916-134">Specifies the maximum, or newest, version of the module to uninstall.</span></span> <span data-ttu-id="68916-135">Die Parameter **MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68916-135">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="68916-136">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="68916-136">-MinimumVersion</span></span>

<span data-ttu-id="68916-137">Gibt die Mindestversion des zu deinstallierenden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="68916-137">Specifies the minimum version of the module to uninstall.</span></span> <span data-ttu-id="68916-138">Die Parameter **MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68916-138">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="68916-139">-Name</span><span class="sxs-lookup"><span data-stu-id="68916-139">-Name</span></span>

<span data-ttu-id="68916-140">Gibt ein Array von Modulnamen an, die deinstalliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="68916-140">Specifies an array of module names to uninstall.</span></span>

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

### <span data-ttu-id="68916-141">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="68916-141">-RequiredVersion</span></span>

<span data-ttu-id="68916-142">Gibt die genaue Versionsnummer des zu deinstallierenden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="68916-142">Specifies the exact version number of the module to uninstall.</span></span>

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

### <span data-ttu-id="68916-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="68916-143">-WhatIf</span></span>

<span data-ttu-id="68916-144">Zeigt, was geschieht, wenn ausgeführt wird `Uninstall-Module` .</span><span class="sxs-lookup"><span data-stu-id="68916-144">Shows what would happen if `Uninstall-Module` runs.</span></span> <span data-ttu-id="68916-145">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="68916-145">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="68916-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="68916-146">CommonParameters</span></span>

<span data-ttu-id="68916-147">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="68916-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="68916-148">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="68916-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="68916-149">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="68916-149">INPUTS</span></span>

### <span data-ttu-id="68916-150">System.String[]</span><span class="sxs-lookup"><span data-stu-id="68916-150">System.String[]</span></span>

### <span data-ttu-id="68916-151">System. Management. Automation. psobject []</span><span class="sxs-lookup"><span data-stu-id="68916-151">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="68916-152">System.String</span><span class="sxs-lookup"><span data-stu-id="68916-152">System.String</span></span>

## <span data-ttu-id="68916-153">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="68916-153">OUTPUTS</span></span>

### <span data-ttu-id="68916-154">System.Object</span><span class="sxs-lookup"><span data-stu-id="68916-154">System.Object</span></span>

## <span data-ttu-id="68916-155">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="68916-155">NOTES</span></span>

## <span data-ttu-id="68916-156">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="68916-156">RELATED LINKS</span></span>

[<span data-ttu-id="68916-157">Find-Module</span><span class="sxs-lookup"><span data-stu-id="68916-157">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="68916-158">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="68916-158">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="68916-159">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="68916-159">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="68916-160">Save-Module</span><span class="sxs-lookup"><span data-stu-id="68916-160">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="68916-161">Update-Module</span><span class="sxs-lookup"><span data-stu-id="68916-161">Update-Module</span></span>](Update-Module.md)

