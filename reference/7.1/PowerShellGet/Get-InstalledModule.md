---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 02/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedmodule?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledModule
ms.openlocfilehash: 9d4ec71a5f754b1fba090129d026d38bd32a8bc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215703"
---
# <span data-ttu-id="27a21-103">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="27a21-103">Get-InstalledModule</span></span>

## <span data-ttu-id="27a21-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="27a21-104">SYNOPSIS</span></span>
<span data-ttu-id="27a21-105">Ruft eine Liste von Modulen auf dem Computer ab, die von PowerShellGet installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="27a21-105">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

## <span data-ttu-id="27a21-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="27a21-106">SYNTAX</span></span>

```
Get-InstalledModule [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="27a21-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="27a21-107">DESCRIPTION</span></span>

<span data-ttu-id="27a21-108">Mit dem- `Get-InstalledModule` Cmdlet werden mithilfe von PowerShellGet PowerShell-Module abgerufen, die auf einem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="27a21-108">The `Get-InstalledModule` cmdlet gets PowerShell modules that are installed on a computer using PowerShellGet.</span></span> <span data-ttu-id="27a21-109">Wenn Sie alle auf dem System installierten Module anzeigen möchten, verwenden Sie den `Get-Module -ListAvailable` Befehl.</span><span class="sxs-lookup"><span data-stu-id="27a21-109">To see all modules installed on the system, use the `Get-Module -ListAvailable` command.</span></span>

## <span data-ttu-id="27a21-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="27a21-110">EXAMPLES</span></span>

### <span data-ttu-id="27a21-111">Beispiel 1: alle installierten Module</span><span class="sxs-lookup"><span data-stu-id="27a21-111">Example 1: Get all installed modules</span></span>

```powershell
Get-InstalledModule
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
2.0.0      PSGTEST-UploadMultipleVersionOfP... Module     GalleryINT     Module for DAC functionality
1.3.5      AzureAutomationDebug                Module     PSGallery      Module for debugging Azure Automation runbooks, emulating AA native cmdlets
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="27a21-112">Dieser Befehl ruft alle installierten Module ab.</span><span class="sxs-lookup"><span data-stu-id="27a21-112">This command gets all installed modules.</span></span>

### <span data-ttu-id="27a21-113">Beispiel 2: beziehen bestimmter Versionen eines Moduls</span><span class="sxs-lookup"><span data-stu-id="27a21-113">Example 2: Get specific versions of a module</span></span>

```powershell
Get-InstalledModule -Name "AzureRM.Automation" -MinimumVersion 1.0 -MaximumVersion 2.0
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="27a21-114">Mit diesem Befehl werden Versionen des azurerm. Automation-Moduls von Version 1,0 bis Version 2,0 abgerufen.</span><span class="sxs-lookup"><span data-stu-id="27a21-114">This command gets versions of the AzureRM.Automation module from version 1.0 through version 2.0.</span></span>

## <span data-ttu-id="27a21-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="27a21-115">PARAMETERS</span></span>

### <span data-ttu-id="27a21-116">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="27a21-116">-AllowPrerelease</span></span>

<span data-ttu-id="27a21-117">Schließt in die als Vorabversion markierten Ergebnis Module ein.</span><span class="sxs-lookup"><span data-stu-id="27a21-117">Includes in the results modules marked as a prerelease.</span></span>

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

### <span data-ttu-id="27a21-118">-Allversions</span><span class="sxs-lookup"><span data-stu-id="27a21-118">-AllVersions</span></span>

<span data-ttu-id="27a21-119">Gibt an, dass Sie alle verfügbaren Versionen eines Moduls erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="27a21-119">Indicates that you want to get all available versions of a module.</span></span>
<span data-ttu-id="27a21-120">Der **allversions** -Parameter kann nicht mit den Parametern **MinimumVersion** , **MaximumVersion** oder Requirements **dversion** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27a21-120">You cannot use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="27a21-121">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="27a21-121">-MaximumVersion</span></span>

<span data-ttu-id="27a21-122">Gibt die maximale oder neueste Version eines zu erzurufenden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="27a21-122">Specifies the maximum, or newest, version of a module to get.</span></span> <span data-ttu-id="27a21-123">Die Parameter " **MaximumVersion** " und "Requirements **dversion** " schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27a21-123">The **MaximumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="27a21-124">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="27a21-124">-MinimumVersion</span></span>

<span data-ttu-id="27a21-125">Gibt die Mindestversion eines einzelnen Moduls an, das Sie erhalten.</span><span class="sxs-lookup"><span data-stu-id="27a21-125">Specifies the minimum version of a single module to get.</span></span> <span data-ttu-id="27a21-126">Die Parameter **MinimumVersion** und Requirements **dversion** schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27a21-126">The **MinimumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="27a21-127">-Name</span><span class="sxs-lookup"><span data-stu-id="27a21-127">-Name</span></span>

<span data-ttu-id="27a21-128">Gibt ein Array von Namen von Modulen an, die erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="27a21-128">Specifies an array of names of modules to get.</span></span>

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

### <span data-ttu-id="27a21-129">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="27a21-129">-RequiredVersion</span></span>

<span data-ttu-id="27a21-130">Gibt die exakte Version eines zu erzurufenden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="27a21-130">Specifies the exact version of a module to get.</span></span>

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

### <span data-ttu-id="27a21-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="27a21-131">CommonParameters</span></span>

<span data-ttu-id="27a21-132">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="27a21-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="27a21-133">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="27a21-133">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="27a21-134">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="27a21-134">INPUTS</span></span>

### <span data-ttu-id="27a21-135">System.String[]</span><span class="sxs-lookup"><span data-stu-id="27a21-135">System.String[]</span></span>

### <span data-ttu-id="27a21-136">System.String</span><span class="sxs-lookup"><span data-stu-id="27a21-136">System.String</span></span>

## <span data-ttu-id="27a21-137">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="27a21-137">OUTPUTS</span></span>

### <span data-ttu-id="27a21-138">System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="27a21-138">System.Management.Automation.PSCustomObject</span></span>

## <span data-ttu-id="27a21-139">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="27a21-139">NOTES</span></span>

## <span data-ttu-id="27a21-140">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="27a21-140">RELATED LINKS</span></span>

