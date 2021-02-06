---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TimeZone
ms.openlocfilehash: 22034eeac6988478a5f2ff87b2582cc5e1acc1c0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602519"
---
# <span data-ttu-id="4c0f5-102">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="4c0f5-102">Get-TimeZone</span></span>

## <span data-ttu-id="4c0f5-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4c0f5-103">SYNOPSIS</span></span>
<span data-ttu-id="4c0f5-104">Ruft die aktuelle Zeitzone oder eine Liste verfügbarer Zeitzonen ab.</span><span class="sxs-lookup"><span data-stu-id="4c0f5-104">Gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="4c0f5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4c0f5-105">SYNTAX</span></span>

### <span data-ttu-id="4c0f5-106">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="4c0f5-106">Name (Default)</span></span>

```
Get-TimeZone [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="4c0f5-107">Id</span><span class="sxs-lookup"><span data-stu-id="4c0f5-107">Id</span></span>

```
Get-TimeZone -Id <String[]> [<CommonParameters>]
```

### <span data-ttu-id="4c0f5-108">ListAvailable</span><span class="sxs-lookup"><span data-stu-id="4c0f5-108">ListAvailable</span></span>

```
Get-TimeZone [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="4c0f5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4c0f5-109">DESCRIPTION</span></span>

<span data-ttu-id="4c0f5-110">Mit dem " **Get-timezone"-** Cmdlet wird die aktuelle Zeitzone oder eine Liste verfügbarer Zeitzonen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4c0f5-110">The **Get-TimeZone** cmdlet gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="4c0f5-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4c0f5-111">EXAMPLES</span></span>

### <span data-ttu-id="4c0f5-112">Beispiel 1: erhalten der aktuellen Zeitzone</span><span class="sxs-lookup"><span data-stu-id="4c0f5-112">Example 1: Get the current time zone</span></span>

```
PS C:\> Get-TimeZone
Pacific Standard Time
```

<span data-ttu-id="4c0f5-113">Mit diesem Befehl wird die aktuelle Zeitzone abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4c0f5-113">This command gets the current time zone.</span></span>

### <span data-ttu-id="4c0f5-114">Beispiel 2: erhalten von Zeitzonen, die einer angegebenen Zeichenfolge entsprechen</span><span class="sxs-lookup"><span data-stu-id="4c0f5-114">Example 2: Get time zones that match a specified string</span></span>

```
PS C:\> Get-TimeZone -Name "*pac*"
Pacific Standard Time (Mexico)

(UTC-08:00) Pacific Time (US &amp; Canada)

Pacific Standard Time

SA Pacific Standard Time

Pacific SA Standard Time

West Pacific Standard Time

Central Pacific Standard Time
```

<span data-ttu-id="4c0f5-115">Mit diesem Befehl werden alle Zeitzonen abgerufen, die mit dem angegebenen Platzhalter Zeichen identisch sind.</span><span class="sxs-lookup"><span data-stu-id="4c0f5-115">This command gets all time zones that match the specified wildcard.</span></span>

### <span data-ttu-id="4c0f5-116">Beispiel 3: alle verfügbaren Zeitzonen erhalten</span><span class="sxs-lookup"><span data-stu-id="4c0f5-116">Example 3: Get all available time zones</span></span>

```
PS C:\> Get-TimeZone -ListAvailable
```

<span data-ttu-id="4c0f5-117">Mit diesem Befehl werden alle verfügbaren Zeitzonen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4c0f5-117">This command gets all available time zones.</span></span>

## <span data-ttu-id="4c0f5-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4c0f5-118">PARAMETERS</span></span>

### <span data-ttu-id="4c0f5-119">-Id</span><span class="sxs-lookup"><span data-stu-id="4c0f5-119">-Id</span></span>

<span data-ttu-id="4c0f5-120">Gibt die ID oder IDs der von diesem Cmdlet abgelegten Zeitzonen als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="4c0f5-120">Specifies, as a string array, the ID or IDs of the time zones that this cmdlet gets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4c0f5-121">-Listavailable</span><span class="sxs-lookup"><span data-stu-id="4c0f5-121">-ListAvailable</span></span>

<span data-ttu-id="4c0f5-122">Gibt an, dass dieses Cmdlet alle verfügbaren Zeitzonen abruft.</span><span class="sxs-lookup"><span data-stu-id="4c0f5-122">Indicates that this cmdlet gets all available time zones.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAvailable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4c0f5-123">-Name</span><span class="sxs-lookup"><span data-stu-id="4c0f5-123">-Name</span></span>

<span data-ttu-id="4c0f5-124">Gibt den Namen oder die Namen der von diesem Cmdlet abgelegten Zeitzonen als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="4c0f5-124">Specifies, as a string array, the name or names of the time zones that this cmdlet gets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="4c0f5-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4c0f5-125">CommonParameters</span></span>

<span data-ttu-id="4c0f5-126">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4c0f5-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4c0f5-127">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4c0f5-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4c0f5-128">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4c0f5-128">INPUTS</span></span>

### <span data-ttu-id="4c0f5-129">System.String[]</span><span class="sxs-lookup"><span data-stu-id="4c0f5-129">System.String[]</span></span>

## <span data-ttu-id="4c0f5-130">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4c0f5-130">OUTPUTS</span></span>

### <span data-ttu-id="4c0f5-131">System. timezoneingefo []</span><span class="sxs-lookup"><span data-stu-id="4c0f5-131">System.TimeZoneInfo[]</span></span>

## <span data-ttu-id="4c0f5-132">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4c0f5-132">NOTES</span></span>

<span data-ttu-id="4c0f5-133">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4c0f5-133">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="4c0f5-134">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4c0f5-134">RELATED LINKS</span></span>

[<span data-ttu-id="4c0f5-135">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="4c0f5-135">Set-TimeZone</span></span>](Set-TimeZone.md)
