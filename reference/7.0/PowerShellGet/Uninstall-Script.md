---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-script?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Script
ms.openlocfilehash: 640ef2187369599d35eea1bca9ad404f5dde745c
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211476"
---
# <span data-ttu-id="c6027-103">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="c6027-103">Uninstall-Script</span></span>

## <span data-ttu-id="c6027-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c6027-104">SYNOPSIS</span></span>
<span data-ttu-id="c6027-105">Deinstalliert ein Skript.</span><span class="sxs-lookup"><span data-stu-id="c6027-105">Uninstalls a script.</span></span>

## <span data-ttu-id="c6027-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c6027-106">SYNTAX</span></span>

### <span data-ttu-id="c6027-107">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="c6027-107">NameParameterSet (Default)</span></span>

```
Uninstall-Script [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c6027-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="c6027-108">InputObject</span></span>

```
Uninstall-Script [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c6027-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c6027-109">DESCRIPTION</span></span>

<span data-ttu-id="c6027-110">Mit dem- `Uninstall-Script` Cmdlet wird ein angegebenes Skript auf dem lokalen Computer deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="c6027-110">The `Uninstall-Script` cmdlet uninstalls a specified script from the local computer.</span></span>

## <span data-ttu-id="c6027-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c6027-111">EXAMPLES</span></span>

### <span data-ttu-id="c6027-112">Beispiel 1: Deinstallieren eines Skripts</span><span class="sxs-lookup"><span data-stu-id="c6027-112">Example 1: Uninstall a script</span></span>

<span data-ttu-id="c6027-113">In diesem Beispiel wird ein Skript deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="c6027-113">This example uninstalls a script.</span></span>

```powershell
Uninstall-Script -Name UpdateManagement-Template
```

<span data-ttu-id="c6027-114">`Uninstall-Script` verwendet den **Name** -Parameter zum Angeben des Skripts, das vom lokalen Computer deinstalliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c6027-114">`Uninstall-Script` uses the **Name** parameter to specify the script to uninstall from the local computer.</span></span>

### <span data-ttu-id="c6027-115">Beispiel 2: Verwenden der Pipeline zum Deinstallieren eines Skripts</span><span class="sxs-lookup"><span data-stu-id="c6027-115">Example 2: Use the pipeline to uninstall a script</span></span>

<span data-ttu-id="c6027-116">In diesem Beispiel wird die Pipeline zum Deinstallieren eines Skripts verwendet.</span><span class="sxs-lookup"><span data-stu-id="c6027-116">In this example, the pipeline is used to uninstall a script.</span></span>

```powershell
Get-InstalledScript -Name UpdateManagement-Template | Uninstall-Script
```

<span data-ttu-id="c6027-117">`Get-InstalledScript` verwendet den **Name** -Parameter, um das Skript anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c6027-117">`Get-InstalledScript` uses the **Name** parameter to specify the script.</span></span> <span data-ttu-id="c6027-118">Das Objekt wird an die Pipeline gesendet, `Uninstall-Script` und das Skript wird deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="c6027-118">The object is sent down the pipeline to `Uninstall-Script` and the script is uninstalled.</span></span>

## <span data-ttu-id="c6027-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c6027-119">PARAMETERS</span></span>

### <span data-ttu-id="c6027-120">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="c6027-120">-AllowPrerelease</span></span>

<span data-ttu-id="c6027-121">Ermöglicht das Deinstallieren eines als Vorabversion markierten Skripts.</span><span class="sxs-lookup"><span data-stu-id="c6027-121">Allows you to uninstall a script marked as a prerelease.</span></span>

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

### <span data-ttu-id="c6027-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c6027-122">-Confirm</span></span>

<span data-ttu-id="c6027-123">Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Uninstall-Script` .</span><span class="sxs-lookup"><span data-stu-id="c6027-123">Prompts you for confirmation before running `Uninstall-Script`.</span></span>

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

### <span data-ttu-id="c6027-124">-Force</span><span class="sxs-lookup"><span data-stu-id="c6027-124">-Force</span></span>

<span data-ttu-id="c6027-125">Erzwingt das `Uninstall-Script` Ausführen von, ohne dass eine Benutzer Bestätigung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="c6027-125">Forces `Uninstall-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="c6027-126">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c6027-126">-InputObject</span></span>

<span data-ttu-id="c6027-127">Akzeptiert ein **PSRepositoryItemInfo** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="c6027-127">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="c6027-128">Geben `Get-InstalledScript` Sie z. b. eine Ausgabe an eine Variable ein, und verwenden Sie diese Variable als **Inputobject** -Argument.</span><span class="sxs-lookup"><span data-stu-id="c6027-128">For example, output `Get-InstalledScript` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="c6027-129">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="c6027-129">-MaximumVersion</span></span>

<span data-ttu-id="c6027-130">Gibt die maximale oder neueste Version des zu deinstallierenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="c6027-130">Specifies the maximum, or newest, version of the script to uninstall.</span></span> <span data-ttu-id="c6027-131">Die Parameter **MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6027-131">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="c6027-132">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="c6027-132">-MinimumVersion</span></span>

<span data-ttu-id="c6027-133">Gibt die Mindestversion des zu deinstallierenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="c6027-133">Specifies the minimum version of the script to uninstall.</span></span> <span data-ttu-id="c6027-134">Die Parameter **MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6027-134">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="c6027-135">-Name</span><span class="sxs-lookup"><span data-stu-id="c6027-135">-Name</span></span>

<span data-ttu-id="c6027-136">Gibt ein Array von Skriptnamen an, die deinstalliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c6027-136">Specifies an array of script names to uninstall.</span></span>

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

### <span data-ttu-id="c6027-137">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="c6027-137">-RequiredVersion</span></span>

<span data-ttu-id="c6027-138">Gibt die genaue Versionsnummer des zu deinstallierenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="c6027-138">Specifies the exact version number of the script to uninstall.</span></span>

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

### <span data-ttu-id="c6027-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c6027-139">-WhatIf</span></span>

<span data-ttu-id="c6027-140">Zeigt, was geschieht, wenn ausgeführt wird `Uninstall-Script` .</span><span class="sxs-lookup"><span data-stu-id="c6027-140">Shows what would happen if `Uninstall-Script` runs.</span></span> <span data-ttu-id="c6027-141">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c6027-141">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="c6027-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c6027-142">CommonParameters</span></span>

<span data-ttu-id="c6027-143">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c6027-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c6027-144">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c6027-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c6027-145">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c6027-145">INPUTS</span></span>

### <span data-ttu-id="c6027-146">System.String[]</span><span class="sxs-lookup"><span data-stu-id="c6027-146">System.String[]</span></span>

### <span data-ttu-id="c6027-147">System. Management. Automation. psobject []</span><span class="sxs-lookup"><span data-stu-id="c6027-147">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="c6027-148">System.String</span><span class="sxs-lookup"><span data-stu-id="c6027-148">System.String</span></span>

## <span data-ttu-id="c6027-149">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c6027-149">OUTPUTS</span></span>

### <span data-ttu-id="c6027-150">System.Object</span><span class="sxs-lookup"><span data-stu-id="c6027-150">System.Object</span></span>

## <span data-ttu-id="c6027-151">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c6027-151">NOTES</span></span>

## <span data-ttu-id="c6027-152">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c6027-152">RELATED LINKS</span></span>

[<span data-ttu-id="c6027-153">Find-Script</span><span class="sxs-lookup"><span data-stu-id="c6027-153">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="c6027-154">Install-Script</span><span class="sxs-lookup"><span data-stu-id="c6027-154">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="c6027-155">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="c6027-155">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="c6027-156">Save-Script</span><span class="sxs-lookup"><span data-stu-id="c6027-156">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="c6027-157">Update-Script</span><span class="sxs-lookup"><span data-stu-id="c6027-157">Update-Script</span></span>](Update-Script.md)
