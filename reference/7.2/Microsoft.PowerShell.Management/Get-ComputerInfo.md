---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: abc820bd6f8f5c8cd8c6301aacee268c82161d7e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601128"
---
# <span data-ttu-id="04f28-102">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="04f28-102">Get-ComputerInfo</span></span>

## <span data-ttu-id="04f28-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="04f28-103">SYNOPSIS</span></span>
<span data-ttu-id="04f28-104">Ruft ein konsolidiertes Objekt der System-und Betriebssystem Eigenschaften ab.</span><span class="sxs-lookup"><span data-stu-id="04f28-104">Gets a consolidated object of system and operating system properties.</span></span>

## <span data-ttu-id="04f28-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="04f28-105">SYNTAX</span></span>

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="04f28-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="04f28-106">DESCRIPTION</span></span>

<span data-ttu-id="04f28-107">`Get-ComputerInfo`Mit dem-Cmdlet wird ein konsolidiertes Objekt der System-und Betriebssystem Eigenschaften abgerufen.</span><span class="sxs-lookup"><span data-stu-id="04f28-107">The `Get-ComputerInfo` cmdlet gets a consolidated object of system and operating system properties.</span></span>
<span data-ttu-id="04f28-108">Dieses Cmdlet wurde in Windows PowerShell 5,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="04f28-108">This cmdlet was introduced in Windows PowerShell 5.1.</span></span>

## <span data-ttu-id="04f28-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="04f28-109">EXAMPLES</span></span>

### <span data-ttu-id="04f28-110">Beispiel 1: alle Computer Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="04f28-110">Example 1: Get all computer properties</span></span>

```powershell
Get-ComputerInfo
```

<span data-ttu-id="04f28-111">Mit diesem Befehl werden alle System-und Betriebssystem Eigenschaften vom Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="04f28-111">This command gets all system and operating system properties from the computer.</span></span>

### <span data-ttu-id="04f28-112">Beispiel 2: alle Computerbetriebssystem-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="04f28-112">Example 2: Get all computer operating system properties</span></span>

```powershell
Get-ComputerInfo -Property "os*"
```

<span data-ttu-id="04f28-113">Mit diesem Befehl werden alle Betriebssystem Eigenschaften vom Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="04f28-113">This command gets all operating system properties from the computer.</span></span>

## <span data-ttu-id="04f28-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="04f28-114">PARAMETERS</span></span>

### <span data-ttu-id="04f28-115">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="04f28-115">-Property</span></span>

<span data-ttu-id="04f28-116">Gibt die Computer Eigenschaften, die dieses Cmdlet anzeigt, als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="04f28-116">Specifies, as a string array, the computer properties in which this cmdlet displays.</span></span>

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

### <span data-ttu-id="04f28-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="04f28-117">CommonParameters</span></span>

<span data-ttu-id="04f28-118">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="04f28-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="04f28-119">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="04f28-119">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="04f28-120">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="04f28-120">INPUTS</span></span>

### <span data-ttu-id="04f28-121">System.String[]</span><span class="sxs-lookup"><span data-stu-id="04f28-121">System.String[]</span></span>

## <span data-ttu-id="04f28-122">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="04f28-122">OUTPUTS</span></span>

### <span data-ttu-id="04f28-123">Microsoft. PowerShell. Management. ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="04f28-123">Microsoft.PowerShell.Management.ComputerInfo</span></span>

## <span data-ttu-id="04f28-124">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="04f28-124">NOTES</span></span>

<span data-ttu-id="04f28-125">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="04f28-125">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="04f28-126">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="04f28-126">RELATED LINKS</span></span>
