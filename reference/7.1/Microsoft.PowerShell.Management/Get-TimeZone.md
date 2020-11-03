---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TimeZone
ms.openlocfilehash: 6e0ed432713cabc4db23f3b070a3e925639a60fb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211639"
---
# <span data-ttu-id="f34b5-103">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="f34b5-103">Get-TimeZone</span></span>

## <span data-ttu-id="f34b5-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f34b5-104">SYNOPSIS</span></span>
<span data-ttu-id="f34b5-105">Ruft die aktuelle Zeitzone oder eine Liste verfügbarer Zeitzonen ab.</span><span class="sxs-lookup"><span data-stu-id="f34b5-105">Gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="f34b5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f34b5-106">SYNTAX</span></span>

### <span data-ttu-id="f34b5-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="f34b5-107">Name (Default)</span></span>

```
Get-TimeZone [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="f34b5-108">Id</span><span class="sxs-lookup"><span data-stu-id="f34b5-108">Id</span></span>

```
Get-TimeZone -Id <String[]> [<CommonParameters>]
```

### <span data-ttu-id="f34b5-109">ListAvailable</span><span class="sxs-lookup"><span data-stu-id="f34b5-109">ListAvailable</span></span>

```
Get-TimeZone [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="f34b5-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f34b5-110">DESCRIPTION</span></span>

<span data-ttu-id="f34b5-111">Mit dem " **Get-timezone"-** Cmdlet wird die aktuelle Zeitzone oder eine Liste verfügbarer Zeitzonen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f34b5-111">The **Get-TimeZone** cmdlet gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="f34b5-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f34b5-112">EXAMPLES</span></span>

### <span data-ttu-id="f34b5-113">Beispiel 1: erhalten der aktuellen Zeitzone</span><span class="sxs-lookup"><span data-stu-id="f34b5-113">Example 1: Get the current time zone</span></span>

```
PS C:\> Get-TimeZone
Pacific Standard Time
```

<span data-ttu-id="f34b5-114">Mit diesem Befehl wird die aktuelle Zeitzone abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f34b5-114">This command gets the current time zone.</span></span>

### <span data-ttu-id="f34b5-115">Beispiel 2: erhalten von Zeitzonen, die einer angegebenen Zeichenfolge entsprechen</span><span class="sxs-lookup"><span data-stu-id="f34b5-115">Example 2: Get time zones that match a specified string</span></span>

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

<span data-ttu-id="f34b5-116">Mit diesem Befehl werden alle Zeitzonen abgerufen, die mit dem angegebenen Platzhalter Zeichen identisch sind.</span><span class="sxs-lookup"><span data-stu-id="f34b5-116">This command gets all time zones that match the specified wildcard.</span></span>

### <span data-ttu-id="f34b5-117">Beispiel 3: alle verfügbaren Zeitzonen erhalten</span><span class="sxs-lookup"><span data-stu-id="f34b5-117">Example 3: Get all available time zones</span></span>

```
PS C:\> Get-TimeZone -ListAvailable
```

<span data-ttu-id="f34b5-118">Mit diesem Befehl werden alle verfügbaren Zeitzonen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f34b5-118">This command gets all available time zones.</span></span>

## <span data-ttu-id="f34b5-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f34b5-119">PARAMETERS</span></span>

### <span data-ttu-id="f34b5-120">-Id</span><span class="sxs-lookup"><span data-stu-id="f34b5-120">-Id</span></span>

<span data-ttu-id="f34b5-121">Gibt die ID oder IDs der von diesem Cmdlet abgelegten Zeitzonen als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="f34b5-121">Specifies, as a string array, the ID or IDs of the time zones that this cmdlet gets.</span></span>

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

### <span data-ttu-id="f34b5-122">-Listavailable</span><span class="sxs-lookup"><span data-stu-id="f34b5-122">-ListAvailable</span></span>

<span data-ttu-id="f34b5-123">Gibt an, dass dieses Cmdlet alle verfügbaren Zeitzonen abruft.</span><span class="sxs-lookup"><span data-stu-id="f34b5-123">Indicates that this cmdlet gets all available time zones.</span></span>

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

### <span data-ttu-id="f34b5-124">-Name</span><span class="sxs-lookup"><span data-stu-id="f34b5-124">-Name</span></span>

<span data-ttu-id="f34b5-125">Gibt den Namen oder die Namen der von diesem Cmdlet abgelegten Zeitzonen als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="f34b5-125">Specifies, as a string array, the name or names of the time zones that this cmdlet gets.</span></span>

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

### <span data-ttu-id="f34b5-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f34b5-126">CommonParameters</span></span>

<span data-ttu-id="f34b5-127">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f34b5-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f34b5-128">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f34b5-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f34b5-129">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f34b5-129">INPUTS</span></span>

### <span data-ttu-id="f34b5-130">System.String[]</span><span class="sxs-lookup"><span data-stu-id="f34b5-130">System.String[]</span></span>

## <span data-ttu-id="f34b5-131">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f34b5-131">OUTPUTS</span></span>

### <span data-ttu-id="f34b5-132">System. timezoneingefo []</span><span class="sxs-lookup"><span data-stu-id="f34b5-132">System.TimeZoneInfo[]</span></span>

## <span data-ttu-id="f34b5-133">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f34b5-133">NOTES</span></span>

## <span data-ttu-id="f34b5-134">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f34b5-134">RELATED LINKS</span></span>

[<span data-ttu-id="f34b5-135">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="f34b5-135">Set-TimeZone</span></span>](Set-TimeZone.md)

