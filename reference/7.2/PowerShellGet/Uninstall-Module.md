---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Module
ms.openlocfilehash: 0df911ad8b1f7b4516eef4a1c2b0180893013e3e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600721"
---
# <span data-ttu-id="3ff8c-102">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="3ff8c-102">Uninstall-Module</span></span>

## <span data-ttu-id="3ff8c-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3ff8c-103">SYNOPSIS</span></span>
<span data-ttu-id="3ff8c-104">Deinstalliert ein Modul.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-104">Uninstalls a module.</span></span>

## <span data-ttu-id="3ff8c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3ff8c-105">SYNTAX</span></span>

### <span data-ttu-id="3ff8c-106">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="3ff8c-106">NameParameterSet (Default)</span></span>

```
Uninstall-Module [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="3ff8c-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="3ff8c-107">InputObject</span></span>

```
Uninstall-Module [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3ff8c-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3ff8c-108">DESCRIPTION</span></span>

<span data-ttu-id="3ff8c-109">Mit dem- `Uninstall-Module` Cmdlet wird ein angegebenes Modul vom lokalen Computer deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-109">The `Uninstall-Module` cmdlet uninstalls a specified module from the local computer.</span></span> <span data-ttu-id="3ff8c-110">Sie können ein Modul nicht deinstallieren, wenn es über andere Module als Abhängigkeiten verfügt.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-110">You can't uninstall a module if it has other modules as dependencies.</span></span>

## <span data-ttu-id="3ff8c-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3ff8c-111">EXAMPLES</span></span>

### <span data-ttu-id="3ff8c-112">Beispiel 1: Deinstallieren eines Moduls</span><span class="sxs-lookup"><span data-stu-id="3ff8c-112">Example 1: Uninstall a module</span></span>

<span data-ttu-id="3ff8c-113">In diesem Beispiel wird ein Modul deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-113">This example uninstalls a module.</span></span>

```powershell
Uninstall-Module -Name SpeculationControl
```

<span data-ttu-id="3ff8c-114">`Uninstall-Module` verwendet den **Name** -Parameter, um das Modul anzugeben, das vom lokalen Computer deinstalliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-114">`Uninstall-Module` uses the **Name** parameter to specify the module to uninstall from the local computer.</span></span>

### <span data-ttu-id="3ff8c-115">Beispiel 2: Verwenden der Pipeline zum Deinstallieren eines Moduls</span><span class="sxs-lookup"><span data-stu-id="3ff8c-115">Example 2: Use the pipeline to uninstall a module</span></span>

<span data-ttu-id="3ff8c-116">In diesem Beispiel wird die Pipeline zum Deinstallieren eines Moduls verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-116">In this example, the pipeline is used to uninstall a module.</span></span>

```powershell
Get-InstalledModule -Name SpeculationControl | Uninstall-Module
```

<span data-ttu-id="3ff8c-117">`Get-InstalledModule` verwendet den **Name** -Parameter, um das Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-117">`Get-InstalledModule` uses the **Name** parameter to specify the module.</span></span> <span data-ttu-id="3ff8c-118">Das Objekt wird über die Pipeline an gesendet `Uninstall-Module` und deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-118">The object is sent down the pipeline to `Uninstall-Module` and is uninstalled.</span></span>

## <span data-ttu-id="3ff8c-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3ff8c-119">PARAMETERS</span></span>

### <span data-ttu-id="3ff8c-120">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="3ff8c-120">-AllowPrerelease</span></span>

<span data-ttu-id="3ff8c-121">Ermöglicht das Deinstallieren eines als Vorabversion markierten Moduls.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-121">Allows you to uninstall a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="3ff8c-122">-Allversions</span><span class="sxs-lookup"><span data-stu-id="3ff8c-122">-AllVersions</span></span>

<span data-ttu-id="3ff8c-123">Gibt an, dass Sie alle verfügbaren Versionen eines Moduls einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-123">Specifies that you want to include all available versions of a module.</span></span> <span data-ttu-id="3ff8c-124">Der **allversions** -Parameter kann nicht mit den Parametern **MinimumVersion**, **MaximumVersion** oder Requirements **dversion** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-124">You can't use the **AllVersions** parameter with the **MinimumVersion**, **MaximumVersion**, or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="3ff8c-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3ff8c-125">-Confirm</span></span>

<span data-ttu-id="3ff8c-126">Fordert Sie zur Bestätigung auf, bevor Sie den ausführen `Uninstall-Module` .</span><span class="sxs-lookup"><span data-stu-id="3ff8c-126">Prompts you for confirmation before running the `Uninstall-Module`.</span></span>

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

### <span data-ttu-id="3ff8c-127">-Force</span><span class="sxs-lookup"><span data-stu-id="3ff8c-127">-Force</span></span>

<span data-ttu-id="3ff8c-128">Erzwingt das `Uninstall-Module` Ausführen von, ohne dass eine Benutzer Bestätigung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-128">Forces `Uninstall-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="3ff8c-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3ff8c-129">-InputObject</span></span>

<span data-ttu-id="3ff8c-130">Akzeptiert ein **PSRepositoryItemInfo** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-130">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="3ff8c-131">Geben `Get-InstalledModule` Sie z. b. eine Ausgabe an eine Variable ein, und verwenden Sie diese Variable als **Inputobject** -Argument.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-131">For example, output `Get-InstalledModule` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="3ff8c-132">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="3ff8c-132">-MaximumVersion</span></span>

<span data-ttu-id="3ff8c-133">Gibt die maximale oder neueste Version des zu deinstallierenden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-133">Specifies the maximum, or newest, version of the module to uninstall.</span></span> <span data-ttu-id="3ff8c-134">Die Parameter **MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-134">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="3ff8c-135">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="3ff8c-135">-MinimumVersion</span></span>

<span data-ttu-id="3ff8c-136">Gibt die Mindestversion des zu deinstallierenden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-136">Specifies the minimum version of the module to uninstall.</span></span> <span data-ttu-id="3ff8c-137">Die Parameter **MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-137">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="3ff8c-138">-Name</span><span class="sxs-lookup"><span data-stu-id="3ff8c-138">-Name</span></span>

<span data-ttu-id="3ff8c-139">Gibt ein Array von Modulnamen an, die deinstalliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-139">Specifies an array of module names to uninstall.</span></span>

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

### <span data-ttu-id="3ff8c-140">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="3ff8c-140">-RequiredVersion</span></span>

<span data-ttu-id="3ff8c-141">Gibt die genaue Versionsnummer des zu deinstallierenden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-141">Specifies the exact version number of the module to uninstall.</span></span>

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

### <span data-ttu-id="3ff8c-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3ff8c-142">-WhatIf</span></span>

<span data-ttu-id="3ff8c-143">Zeigt, was geschieht, wenn ausgeführt wird `Uninstall-Module` .</span><span class="sxs-lookup"><span data-stu-id="3ff8c-143">Shows what would happen if `Uninstall-Module` runs.</span></span> <span data-ttu-id="3ff8c-144">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-144">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="3ff8c-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3ff8c-145">CommonParameters</span></span>

<span data-ttu-id="3ff8c-146">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3ff8c-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3ff8c-147">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3ff8c-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3ff8c-148">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3ff8c-148">INPUTS</span></span>

### <span data-ttu-id="3ff8c-149">System.String[]</span><span class="sxs-lookup"><span data-stu-id="3ff8c-149">System.String[]</span></span>

### <span data-ttu-id="3ff8c-150">System. Management. Automation. psobject []</span><span class="sxs-lookup"><span data-stu-id="3ff8c-150">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="3ff8c-151">System.String</span><span class="sxs-lookup"><span data-stu-id="3ff8c-151">System.String</span></span>

## <span data-ttu-id="3ff8c-152">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3ff8c-152">OUTPUTS</span></span>

### <span data-ttu-id="3ff8c-153">System.Object</span><span class="sxs-lookup"><span data-stu-id="3ff8c-153">System.Object</span></span>

## <span data-ttu-id="3ff8c-154">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3ff8c-154">NOTES</span></span>

## <span data-ttu-id="3ff8c-155">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3ff8c-155">RELATED LINKS</span></span>

[<span data-ttu-id="3ff8c-156">Find-Module</span><span class="sxs-lookup"><span data-stu-id="3ff8c-156">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="3ff8c-157">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="3ff8c-157">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="3ff8c-158">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="3ff8c-158">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="3ff8c-159">Save-Module</span><span class="sxs-lookup"><span data-stu-id="3ff8c-159">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="3ff8c-160">Update-Module</span><span class="sxs-lookup"><span data-stu-id="3ff8c-160">Update-Module</span></span>](Update-Module.md)

