---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedscript?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledScript
ms.openlocfilehash: 6a69108694d5ba614bb7f195004d2d37ac6de092
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215991"
---
# <span data-ttu-id="726da-103">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="726da-103">Get-InstalledScript</span></span>

## <span data-ttu-id="726da-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="726da-104">SYNOPSIS</span></span>
<span data-ttu-id="726da-105">Ruft ein installiertes Skript ab.</span><span class="sxs-lookup"><span data-stu-id="726da-105">Gets an installed script.</span></span>

## <span data-ttu-id="726da-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="726da-106">SYNTAX</span></span>

```
Get-InstalledScript [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="726da-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="726da-107">DESCRIPTION</span></span>

<span data-ttu-id="726da-108">Mit dem " **Get-installedscript"-** Cmdlet werden installierte Skripts für die Bereiche CurrentUser und ALLUSERS abgerufen.</span><span class="sxs-lookup"><span data-stu-id="726da-108">The **Get-InstalledScript** cmdlet gets installed scripts for CurrentUser and AllUsers scopes.</span></span>

## <span data-ttu-id="726da-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="726da-109">EXAMPLES</span></span>

### <span data-ttu-id="726da-110">Beispiel 1: alle installierten Skripts</span><span class="sxs-lookup"><span data-stu-id="726da-110">Example 1: Get all installed scripts</span></span>

```
PS C:\> Get-InstalledScript
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     local1               Description for the Script-WithDependencies1 script
```

<span data-ttu-id="726da-111">Dieser Befehl ruft alle installierten Skripts ab.</span><span class="sxs-lookup"><span data-stu-id="726da-111">This command gets all installed scripts.</span></span>

### <span data-ttu-id="726da-112">Beispiel 2: Installieren von installierten Skripts nach Namen</span><span class="sxs-lookup"><span data-stu-id="726da-112">Example 2: Get installed scripts by name</span></span>

```
PS C:\> Get-InstalledScript -Name "Required-Scri*"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="726da-113">Dieser Befehl ruft Skripts ab, deren Name mit "required-SKR" beginnt.</span><span class="sxs-lookup"><span data-stu-id="726da-113">This command gets scripts where the name begins with Required-Scri.</span></span>

## <span data-ttu-id="726da-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="726da-114">PARAMETERS</span></span>

### <span data-ttu-id="726da-115">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="726da-115">-AllowPrerelease</span></span>

<span data-ttu-id="726da-116">Schließt in die als Vorabversion markierten Ergebnisskripts ein.</span><span class="sxs-lookup"><span data-stu-id="726da-116">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="726da-117">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="726da-117">-MaximumVersion</span></span>

<span data-ttu-id="726da-118">Gibt die maximale oder neueste Version eines Skripts an, das Sie erhalten.</span><span class="sxs-lookup"><span data-stu-id="726da-118">Specifies the maximum, or latest, version of a script to get.</span></span>
<span data-ttu-id="726da-119">Die Parameter " *MaximumVersion* " und "Requirements *dversion* " schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="726da-119">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="726da-120">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="726da-120">-MinimumVersion</span></span>

<span data-ttu-id="726da-121">Gibt die Mindestversion eines zu entzurufenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="726da-121">Specifies the minimum version of a script to get.</span></span>
<span data-ttu-id="726da-122">Die Parameter *MinimumVersion* und Requirements *dversion* schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="726da-122">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="726da-123">-Name</span><span class="sxs-lookup"><span data-stu-id="726da-123">-Name</span></span>

<span data-ttu-id="726da-124">Gibt ein Array von Namen von Skripts an, die erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="726da-124">Specifies an array of names of scripts to get.</span></span>
<span data-ttu-id="726da-125">Platzhalter werden akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="726da-125">Wildcards are accepted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="726da-126">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="726da-126">-RequiredVersion</span></span>

<span data-ttu-id="726da-127">Gibt die exakte Version eines Skripts an, das Sie erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="726da-127">Specifies the exact version of a script to get.</span></span>

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

### <span data-ttu-id="726da-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="726da-128">CommonParameters</span></span>

<span data-ttu-id="726da-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="726da-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="726da-130">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="726da-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="726da-131">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="726da-131">INPUTS</span></span>

### <span data-ttu-id="726da-132">System.String[]</span><span class="sxs-lookup"><span data-stu-id="726da-132">System.String[]</span></span>

### <span data-ttu-id="726da-133">System.String</span><span class="sxs-lookup"><span data-stu-id="726da-133">System.String</span></span>

## <span data-ttu-id="726da-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="726da-134">OUTPUTS</span></span>

### <span data-ttu-id="726da-135">System.Object</span><span class="sxs-lookup"><span data-stu-id="726da-135">System.Object</span></span>

## <span data-ttu-id="726da-136">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="726da-136">NOTES</span></span>

## <span data-ttu-id="726da-137">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="726da-137">RELATED LINKS</span></span>

[<span data-ttu-id="726da-138">Install-Script</span><span class="sxs-lookup"><span data-stu-id="726da-138">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="726da-139">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="726da-139">Uninstall-Script</span></span>](Uninstall-Script.md)
