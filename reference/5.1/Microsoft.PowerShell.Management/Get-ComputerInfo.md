---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: e9b9e63815e1eb312a30eca11c691107ea3d070f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215484"
---
# <span data-ttu-id="037a6-103">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="037a6-103">Get-ComputerInfo</span></span>

## <span data-ttu-id="037a6-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="037a6-104">SYNOPSIS</span></span>
<span data-ttu-id="037a6-105">Ruft ein konsolidiertes Objekt der System-und Betriebssystem Eigenschaften ab.</span><span class="sxs-lookup"><span data-stu-id="037a6-105">Gets a consolidated object of system and operating system properties.</span></span>

## <span data-ttu-id="037a6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="037a6-106">SYNTAX</span></span>

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="037a6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="037a6-107">DESCRIPTION</span></span>

<span data-ttu-id="037a6-108">`Get-ComputerInfo`Mit dem-Cmdlet wird ein konsolidiertes Objekt der System-und Betriebssystem Eigenschaften abgerufen.</span><span class="sxs-lookup"><span data-stu-id="037a6-108">The `Get-ComputerInfo` cmdlet gets a consolidated object of system and operating system properties.</span></span>
<span data-ttu-id="037a6-109">Dieses Cmdlet wurde in Windows PowerShell 5,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="037a6-109">This cmdlet was introduced in Windows PowerShell 5.1.</span></span>

## <span data-ttu-id="037a6-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="037a6-110">EXAMPLES</span></span>

### <span data-ttu-id="037a6-111">Beispiel 1: alle Computer Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="037a6-111">Example 1: Get all computer properties</span></span>

```powershell
Get-ComputerInfo
```

<span data-ttu-id="037a6-112">Mit diesem Befehl werden alle System-und Betriebssystem Eigenschaften vom Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="037a6-112">This command gets all system and operating system properties from the computer.</span></span>

### <span data-ttu-id="037a6-113">Beispiel 2: alle Computerbetriebssystem-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="037a6-113">Example 2: Get all computer operating system properties</span></span>

```powershell
Get-ComputerInfo -Property "os*"
```

<span data-ttu-id="037a6-114">Mit diesem Befehl werden alle Betriebssystem Eigenschaften vom Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="037a6-114">This command gets all operating system properties from the computer.</span></span>

## <span data-ttu-id="037a6-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="037a6-115">PARAMETERS</span></span>

### <span data-ttu-id="037a6-116">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="037a6-116">-Property</span></span>

<span data-ttu-id="037a6-117">Gibt die Computer Eigenschaften, die dieses Cmdlet anzeigt, als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="037a6-117">Specifies, as a string array, the computer properties in which this cmdlet displays.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="037a6-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="037a6-118">CommonParameters</span></span>

<span data-ttu-id="037a6-119">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="037a6-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="037a6-120">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="037a6-120">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="037a6-121">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="037a6-121">INPUTS</span></span>

### <span data-ttu-id="037a6-122">System.String[]</span><span class="sxs-lookup"><span data-stu-id="037a6-122">System.String[]</span></span>

## <span data-ttu-id="037a6-123">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="037a6-123">OUTPUTS</span></span>

### <span data-ttu-id="037a6-124">Microsoft. PowerShell. Management. ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="037a6-124">Microsoft.PowerShell.Management.ComputerInfo</span></span>

## <span data-ttu-id="037a6-125">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="037a6-125">NOTES</span></span>

## <span data-ttu-id="037a6-126">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="037a6-126">RELATED LINKS</span></span>
