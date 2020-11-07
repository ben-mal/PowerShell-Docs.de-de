---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: bb3f2b78fecd33288a0febd2882277721d9cf289
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342687"
---
# <span data-ttu-id="deb61-103">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="deb61-103">Get-ComputerInfo</span></span>

## <span data-ttu-id="deb61-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="deb61-104">SYNOPSIS</span></span>
<span data-ttu-id="deb61-105">Ruft ein konsolidiertes Objekt der System-und Betriebssystem Eigenschaften ab.</span><span class="sxs-lookup"><span data-stu-id="deb61-105">Gets a consolidated object of system and operating system properties.</span></span>

## <span data-ttu-id="deb61-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="deb61-106">SYNTAX</span></span>

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="deb61-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="deb61-107">DESCRIPTION</span></span>

<span data-ttu-id="deb61-108">`Get-ComputerInfo`Mit dem-Cmdlet wird ein konsolidiertes Objekt der System-und Betriebssystem Eigenschaften abgerufen.</span><span class="sxs-lookup"><span data-stu-id="deb61-108">The `Get-ComputerInfo` cmdlet gets a consolidated object of system and operating system properties.</span></span>
<span data-ttu-id="deb61-109">Dieses Cmdlet wurde in Windows PowerShell 5,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deb61-109">This cmdlet was introduced in Windows PowerShell 5.1.</span></span>

## <span data-ttu-id="deb61-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="deb61-110">EXAMPLES</span></span>

### <span data-ttu-id="deb61-111">Beispiel 1: alle Computer Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="deb61-111">Example 1: Get all computer properties</span></span>

```powershell
Get-ComputerInfo
```

<span data-ttu-id="deb61-112">Mit diesem Befehl werden alle System-und Betriebssystem Eigenschaften vom Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="deb61-112">This command gets all system and operating system properties from the computer.</span></span>

### <span data-ttu-id="deb61-113">Beispiel 2: alle Computerbetriebssystem-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="deb61-113">Example 2: Get all computer operating system properties</span></span>

```powershell
Get-ComputerInfo -Property "os*"
```

<span data-ttu-id="deb61-114">Mit diesem Befehl werden alle Betriebssystem Eigenschaften vom Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="deb61-114">This command gets all operating system properties from the computer.</span></span>

## <span data-ttu-id="deb61-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="deb61-115">PARAMETERS</span></span>

### <span data-ttu-id="deb61-116">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="deb61-116">-Property</span></span>

<span data-ttu-id="deb61-117">Gibt die Computer Eigenschaften, die dieses Cmdlet anzeigt, als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="deb61-117">Specifies, as a string array, the computer properties in which this cmdlet displays.</span></span>

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

### <span data-ttu-id="deb61-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="deb61-118">CommonParameters</span></span>

<span data-ttu-id="deb61-119">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="deb61-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="deb61-120">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="deb61-120">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="deb61-121">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="deb61-121">INPUTS</span></span>

### <span data-ttu-id="deb61-122">System.String[]</span><span class="sxs-lookup"><span data-stu-id="deb61-122">System.String[]</span></span>

## <span data-ttu-id="deb61-123">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="deb61-123">OUTPUTS</span></span>

### <span data-ttu-id="deb61-124">Microsoft. PowerShell. Management. ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="deb61-124">Microsoft.PowerShell.Management.ComputerInfo</span></span>

## <span data-ttu-id="deb61-125">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="deb61-125">NOTES</span></span>

## <span data-ttu-id="deb61-126">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="deb61-126">RELATED LINKS</span></span>
