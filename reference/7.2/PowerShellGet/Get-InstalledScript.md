---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedscript?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledScript
ms.openlocfilehash: fe5fc0feb34fda87dab987f33140992a346017a1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601927"
---
# <span data-ttu-id="1d332-102">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="1d332-102">Get-InstalledScript</span></span>

## <span data-ttu-id="1d332-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1d332-103">SYNOPSIS</span></span>
<span data-ttu-id="1d332-104">Ruft ein installiertes Skript ab.</span><span class="sxs-lookup"><span data-stu-id="1d332-104">Gets an installed script.</span></span>

## <span data-ttu-id="1d332-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1d332-105">SYNTAX</span></span>

```
Get-InstalledScript [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="1d332-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1d332-106">DESCRIPTION</span></span>

<span data-ttu-id="1d332-107">Mit dem " **Get-installedscript"-** Cmdlet werden installierte Skripts für die Bereiche CurrentUser und ALLUSERS abgerufen.</span><span class="sxs-lookup"><span data-stu-id="1d332-107">The **Get-InstalledScript** cmdlet gets installed scripts for CurrentUser and AllUsers scopes.</span></span>

## <span data-ttu-id="1d332-108">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1d332-108">EXAMPLES</span></span>

### <span data-ttu-id="1d332-109">Beispiel 1: alle installierten Skripts</span><span class="sxs-lookup"><span data-stu-id="1d332-109">Example 1: Get all installed scripts</span></span>

```
PS C:\> Get-InstalledScript
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     local1               Description for the Script-WithDependencies1 script
```

<span data-ttu-id="1d332-110">Dieser Befehl ruft alle installierten Skripts ab.</span><span class="sxs-lookup"><span data-stu-id="1d332-110">This command gets all installed scripts.</span></span>

### <span data-ttu-id="1d332-111">Beispiel 2: Installieren von installierten Skripts nach Namen</span><span class="sxs-lookup"><span data-stu-id="1d332-111">Example 2: Get installed scripts by name</span></span>

```
PS C:\> Get-InstalledScript -Name "Required-Scri*"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="1d332-112">Dieser Befehl ruft Skripts ab, deren Name mit "required-SKR" beginnt.</span><span class="sxs-lookup"><span data-stu-id="1d332-112">This command gets scripts where the name begins with Required-Scri.</span></span>

## <span data-ttu-id="1d332-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1d332-113">PARAMETERS</span></span>

### <span data-ttu-id="1d332-114">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="1d332-114">-AllowPrerelease</span></span>

<span data-ttu-id="1d332-115">Schließt in die als Vorabversion markierten Ergebnisskripts ein.</span><span class="sxs-lookup"><span data-stu-id="1d332-115">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="1d332-116">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="1d332-116">-MaximumVersion</span></span>

<span data-ttu-id="1d332-117">Gibt die maximale oder neueste Version eines Skripts an, das Sie erhalten.</span><span class="sxs-lookup"><span data-stu-id="1d332-117">Specifies the maximum, or latest, version of a script to get.</span></span>
<span data-ttu-id="1d332-118">Die Parameter " *MaximumVersion* " und "Requirements *dversion* " schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d332-118">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="1d332-119">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="1d332-119">-MinimumVersion</span></span>

<span data-ttu-id="1d332-120">Gibt die Mindestversion eines zu entzurufenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="1d332-120">Specifies the minimum version of a script to get.</span></span>
<span data-ttu-id="1d332-121">Die Parameter *MinimumVersion* und Requirements *dversion* schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d332-121">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="1d332-122">-Name</span><span class="sxs-lookup"><span data-stu-id="1d332-122">-Name</span></span>

<span data-ttu-id="1d332-123">Gibt ein Array von Namen von Skripts an, die erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="1d332-123">Specifies an array of names of scripts to get.</span></span>
<span data-ttu-id="1d332-124">Platzhalter werden akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="1d332-124">Wildcards are accepted.</span></span>

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

### <span data-ttu-id="1d332-125">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="1d332-125">-RequiredVersion</span></span>

<span data-ttu-id="1d332-126">Gibt die exakte Version eines Skripts an, das Sie erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="1d332-126">Specifies the exact version of a script to get.</span></span>

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

### <span data-ttu-id="1d332-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1d332-127">CommonParameters</span></span>

<span data-ttu-id="1d332-128">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1d332-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1d332-129">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1d332-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1d332-130">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1d332-130">INPUTS</span></span>

### <span data-ttu-id="1d332-131">System.String[]</span><span class="sxs-lookup"><span data-stu-id="1d332-131">System.String[]</span></span>

### <span data-ttu-id="1d332-132">System.String</span><span class="sxs-lookup"><span data-stu-id="1d332-132">System.String</span></span>

## <span data-ttu-id="1d332-133">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1d332-133">OUTPUTS</span></span>

### <span data-ttu-id="1d332-134">System.Object</span><span class="sxs-lookup"><span data-stu-id="1d332-134">System.Object</span></span>

## <span data-ttu-id="1d332-135">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1d332-135">NOTES</span></span>

## <span data-ttu-id="1d332-136">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1d332-136">RELATED LINKS</span></span>

[<span data-ttu-id="1d332-137">Install-Script</span><span class="sxs-lookup"><span data-stu-id="1d332-137">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="1d332-138">Deinstallieren: Skript</span><span class="sxs-lookup"><span data-stu-id="1d332-138">Uninstall-Script</span></span>](Uninstall-Script.md)

