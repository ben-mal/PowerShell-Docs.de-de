---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedscript?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledScript
ms.openlocfilehash: a90ece844d5a271402537f17c601bf2e36b5ed8c
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210236"
---
# <span data-ttu-id="effdc-103">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="effdc-103">Get-InstalledScript</span></span>

## <span data-ttu-id="effdc-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="effdc-104">SYNOPSIS</span></span>
<span data-ttu-id="effdc-105">Ruft ein installiertes Skript ab.</span><span class="sxs-lookup"><span data-stu-id="effdc-105">Gets an installed script.</span></span>

## <span data-ttu-id="effdc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="effdc-106">SYNTAX</span></span>

```
Get-InstalledScript [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="effdc-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="effdc-107">DESCRIPTION</span></span>

<span data-ttu-id="effdc-108">Mit dem " **Get-installedscript"-** Cmdlet werden installierte Skripts für die Bereiche CurrentUser und ALLUSERS abgerufen.</span><span class="sxs-lookup"><span data-stu-id="effdc-108">The **Get-InstalledScript** cmdlet gets installed scripts for CurrentUser and AllUsers scopes.</span></span>

## <span data-ttu-id="effdc-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="effdc-109">EXAMPLES</span></span>

### <span data-ttu-id="effdc-110">Beispiel 1: alle installierten Skripts</span><span class="sxs-lookup"><span data-stu-id="effdc-110">Example 1: Get all installed scripts</span></span>

```
PS C:\> Get-InstalledScript
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     local1               Description for the Script-WithDependencies1 script
```

<span data-ttu-id="effdc-111">Dieser Befehl ruft alle installierten Skripts ab.</span><span class="sxs-lookup"><span data-stu-id="effdc-111">This command gets all installed scripts.</span></span>

### <span data-ttu-id="effdc-112">Beispiel 2: Installieren von installierten Skripts nach Namen</span><span class="sxs-lookup"><span data-stu-id="effdc-112">Example 2: Get installed scripts by name</span></span>

```
PS C:\> Get-InstalledScript -Name "Required-Scri*"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="effdc-113">Dieser Befehl ruft Skripts ab, deren Name mit "required-SKR" beginnt.</span><span class="sxs-lookup"><span data-stu-id="effdc-113">This command gets scripts where the name begins with Required-Scri.</span></span>

## <span data-ttu-id="effdc-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="effdc-114">PARAMETERS</span></span>

### <span data-ttu-id="effdc-115">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="effdc-115">-AllowPrerelease</span></span>

<span data-ttu-id="effdc-116">Schließt in die als Vorabversion markierten Ergebnisskripts ein.</span><span class="sxs-lookup"><span data-stu-id="effdc-116">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="effdc-117">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="effdc-117">-MaximumVersion</span></span>

<span data-ttu-id="effdc-118">Gibt die maximale oder neueste Version eines Skripts an, das Sie erhalten.</span><span class="sxs-lookup"><span data-stu-id="effdc-118">Specifies the maximum, or latest, version of a script to get.</span></span>
<span data-ttu-id="effdc-119">Die Parameter " *MaximumVersion* " und "Requirements *dversion* " schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="effdc-119">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="effdc-120">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="effdc-120">-MinimumVersion</span></span>

<span data-ttu-id="effdc-121">Gibt die Mindestversion eines zu entzurufenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="effdc-121">Specifies the minimum version of a script to get.</span></span>
<span data-ttu-id="effdc-122">Die Parameter *MinimumVersion* und Requirements *dversion* schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="effdc-122">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="effdc-123">-Name</span><span class="sxs-lookup"><span data-stu-id="effdc-123">-Name</span></span>

<span data-ttu-id="effdc-124">Gibt ein Array von Namen von Skripts an, die erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="effdc-124">Specifies an array of names of scripts to get.</span></span>
<span data-ttu-id="effdc-125">Platzhalter werden akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="effdc-125">Wildcards are accepted.</span></span>

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

### <span data-ttu-id="effdc-126">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="effdc-126">-RequiredVersion</span></span>

<span data-ttu-id="effdc-127">Gibt die exakte Version eines Skripts an, das Sie erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="effdc-127">Specifies the exact version of a script to get.</span></span>

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

### <span data-ttu-id="effdc-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="effdc-128">CommonParameters</span></span>

<span data-ttu-id="effdc-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="effdc-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="effdc-130">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="effdc-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="effdc-131">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="effdc-131">INPUTS</span></span>

### <span data-ttu-id="effdc-132">System.String[]</span><span class="sxs-lookup"><span data-stu-id="effdc-132">System.String[]</span></span>

### <span data-ttu-id="effdc-133">System.String</span><span class="sxs-lookup"><span data-stu-id="effdc-133">System.String</span></span>

## <span data-ttu-id="effdc-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="effdc-134">OUTPUTS</span></span>

### <span data-ttu-id="effdc-135">System.Object</span><span class="sxs-lookup"><span data-stu-id="effdc-135">System.Object</span></span>

## <span data-ttu-id="effdc-136">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="effdc-136">NOTES</span></span>

## <span data-ttu-id="effdc-137">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="effdc-137">RELATED LINKS</span></span>

[<span data-ttu-id="effdc-138">Install-Script</span><span class="sxs-lookup"><span data-stu-id="effdc-138">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="effdc-139">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="effdc-139">Uninstall-Script</span></span>](Uninstall-Script.md)
