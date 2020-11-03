---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-runspacedebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-RunspaceDebug
ms.openlocfilehash: 79fe5c58f26f9146adfca18827f65cff53bde23f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214076"
---
# <span data-ttu-id="3fb2a-103">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="3fb2a-103">Disable-RunspaceDebug</span></span>

## <span data-ttu-id="3fb2a-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3fb2a-104">SYNOPSIS</span></span>
<span data-ttu-id="3fb2a-105">Deaktiviert das Debuggen in einem oder mehreren Runspaces und gibt alle ausstehenden Debugger-Stopps frei.</span><span class="sxs-lookup"><span data-stu-id="3fb2a-105">Disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="3fb2a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3fb2a-106">SYNTAX</span></span>

### <span data-ttu-id="3fb2a-107">Runspacenameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="3fb2a-107">RunspaceNameParameterSet (Default)</span></span>

```
Disable-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="3fb2a-108">Runspaceparameterset</span><span class="sxs-lookup"><span data-stu-id="3fb2a-108">RunspaceParameterSet</span></span>

```
Disable-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="3fb2a-109">Runspaceidparameterset</span><span class="sxs-lookup"><span data-stu-id="3fb2a-109">RunspaceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="3fb2a-110">Runspaceinstanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="3fb2a-110">RunspaceInstanceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="3fb2a-111">Processnameparameterset</span><span class="sxs-lookup"><span data-stu-id="3fb2a-111">ProcessNameParameterSet</span></span>

```
Disable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="3fb2a-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3fb2a-112">DESCRIPTION</span></span>

<span data-ttu-id="3fb2a-113">Das `Disable-RunspaceDebug` -Cmdlet deaktiviert das Debuggen in einem oder mehreren Runspaces und gibt alle ausstehenden Debugger-Stopps frei.</span><span class="sxs-lookup"><span data-stu-id="3fb2a-113">The `Disable-RunspaceDebug` cmdlet disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="3fb2a-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3fb2a-114">EXAMPLES</span></span>

### <span data-ttu-id="3fb2a-115">1: Deaktivieren des standardrunspace-Debuggers</span><span class="sxs-lookup"><span data-stu-id="3fb2a-115">1: Disable the default runspace debugger</span></span>

```powershell
Disable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="3fb2a-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3fb2a-116">PARAMETERS</span></span>

### <span data-ttu-id="3fb2a-117">-Appdomainname</span><span class="sxs-lookup"><span data-stu-id="3fb2a-117">-AppDomainName</span></span>

<span data-ttu-id="3fb2a-118">Der Name der Anwendungsdomäne, die den PowerShell-Runspace hostet.</span><span class="sxs-lookup"><span data-stu-id="3fb2a-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3fb2a-119">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="3fb2a-119">-ProcessName</span></span>

<span data-ttu-id="3fb2a-120">Der Name des Prozesses, der den PowerShell-Runspace hostet.</span><span class="sxs-lookup"><span data-stu-id="3fb2a-120">The name of the process that hosts the PowerShell runspace.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3fb2a-121">-Runspace</span><span class="sxs-lookup"><span data-stu-id="3fb2a-121">-Runspace</span></span>

<span data-ttu-id="3fb2a-122">Mindestens ein **Runspace** -Objekt, das deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3fb2a-122">One or more **Runspace** objects to be disabled.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.Runspace[]
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3fb2a-123">-Runspaceid</span><span class="sxs-lookup"><span data-stu-id="3fb2a-123">-RunspaceId</span></span>

<span data-ttu-id="3fb2a-124">Mindestens eine zu deaktivier Ende **Runspace** -ID-Nummer.</span><span class="sxs-lookup"><span data-stu-id="3fb2a-124">One or more **Runspace** Id numbers to be disabled.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: RunspaceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3fb2a-125">-Runspaceinstanceid</span><span class="sxs-lookup"><span data-stu-id="3fb2a-125">-RunspaceInstanceId</span></span>

<span data-ttu-id="3fb2a-126">Mindestens eine **Runspace** -GUIDs, die deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3fb2a-126">One or more **Runspace** GUIDs to be disabled.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: RunspaceInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3fb2a-127">-Runspacename</span><span class="sxs-lookup"><span data-stu-id="3fb2a-127">-RunspaceName</span></span>

<span data-ttu-id="3fb2a-128">Mindestens ein **Runspace** -Name, der deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3fb2a-128">One or more **Runspace** names to be disabled.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RunspaceNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3fb2a-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3fb2a-129">CommonParameters</span></span>

<span data-ttu-id="3fb2a-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3fb2a-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3fb2a-131">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3fb2a-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3fb2a-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3fb2a-132">INPUTS</span></span>

## <span data-ttu-id="3fb2a-133">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3fb2a-133">OUTPUTS</span></span>

## <span data-ttu-id="3fb2a-134">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3fb2a-134">NOTES</span></span>

## <span data-ttu-id="3fb2a-135">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3fb2a-135">RELATED LINKS</span></span>

[<span data-ttu-id="3fb2a-136">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="3fb2a-136">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)

[<span data-ttu-id="3fb2a-137">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="3fb2a-137">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)
