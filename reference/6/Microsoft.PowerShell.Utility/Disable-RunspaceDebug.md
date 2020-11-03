---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-runspacedebug?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-RunspaceDebug
ms.openlocfilehash: ad9a08b3936044ef74c83b5e0d0cff146bf43e3f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216767"
---
# <span data-ttu-id="082b8-103">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="082b8-103">Disable-RunspaceDebug</span></span>

## <span data-ttu-id="082b8-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="082b8-104">SYNOPSIS</span></span>
<span data-ttu-id="082b8-105">Deaktiviert das Debuggen in einem oder mehreren Runspaces und gibt alle ausstehenden Debugger-Stopps frei.</span><span class="sxs-lookup"><span data-stu-id="082b8-105">Disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="082b8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="082b8-106">SYNTAX</span></span>

### <span data-ttu-id="082b8-107">Runspacenameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="082b8-107">RunspaceNameParameterSet (Default)</span></span>

```
Disable-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="082b8-108">Runspaceparameterset</span><span class="sxs-lookup"><span data-stu-id="082b8-108">RunspaceParameterSet</span></span>

```
Disable-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="082b8-109">Runspaceidparameterset</span><span class="sxs-lookup"><span data-stu-id="082b8-109">RunspaceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="082b8-110">Runspaceinstanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="082b8-110">RunspaceInstanceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="082b8-111">Processnameparameterset</span><span class="sxs-lookup"><span data-stu-id="082b8-111">ProcessNameParameterSet</span></span>

```
Disable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="082b8-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="082b8-112">DESCRIPTION</span></span>

<span data-ttu-id="082b8-113">Das `Disable-RunspaceDebug` -Cmdlet deaktiviert das Debuggen in einem oder mehreren Runspaces und gibt alle ausstehenden Debugger-Stopps frei.</span><span class="sxs-lookup"><span data-stu-id="082b8-113">The `Disable-RunspaceDebug` cmdlet disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="082b8-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="082b8-114">EXAMPLES</span></span>

### <span data-ttu-id="082b8-115">1: Deaktivieren des standardrunspace-Debuggers</span><span class="sxs-lookup"><span data-stu-id="082b8-115">1: Disable the default runspace debugger</span></span>

```powershell
Disable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="082b8-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="082b8-116">PARAMETERS</span></span>

### <span data-ttu-id="082b8-117">-Appdomainname</span><span class="sxs-lookup"><span data-stu-id="082b8-117">-AppDomainName</span></span>

<span data-ttu-id="082b8-118">Der Name der Anwendungsdomäne, die den PowerShell-Runspace hostet.</span><span class="sxs-lookup"><span data-stu-id="082b8-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="082b8-119">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="082b8-119">-ProcessName</span></span>

<span data-ttu-id="082b8-120">Der Name des Prozesses, der den PowerShell-Runspace hostet.</span><span class="sxs-lookup"><span data-stu-id="082b8-120">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="082b8-121">-Runspace</span><span class="sxs-lookup"><span data-stu-id="082b8-121">-Runspace</span></span>

<span data-ttu-id="082b8-122">Mindestens ein **Runspace** -Objekt, das deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="082b8-122">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="082b8-123">-Runspaceid</span><span class="sxs-lookup"><span data-stu-id="082b8-123">-RunspaceId</span></span>

<span data-ttu-id="082b8-124">Mindestens eine zu deaktivier Ende **Runspace** -ID-Nummer.</span><span class="sxs-lookup"><span data-stu-id="082b8-124">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="082b8-125">-Runspaceinstanceid</span><span class="sxs-lookup"><span data-stu-id="082b8-125">-RunspaceInstanceId</span></span>

<span data-ttu-id="082b8-126">Mindestens eine **Runspace** -GUIDs, die deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="082b8-126">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="082b8-127">-Runspacename</span><span class="sxs-lookup"><span data-stu-id="082b8-127">-RunspaceName</span></span>

<span data-ttu-id="082b8-128">Mindestens ein **Runspace** -Name, der deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="082b8-128">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="082b8-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="082b8-129">CommonParameters</span></span>

<span data-ttu-id="082b8-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="082b8-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="082b8-131">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="082b8-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="082b8-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="082b8-132">INPUTS</span></span>

## <span data-ttu-id="082b8-133">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="082b8-133">OUTPUTS</span></span>

## <span data-ttu-id="082b8-134">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="082b8-134">NOTES</span></span>

## <span data-ttu-id="082b8-135">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="082b8-135">RELATED LINKS</span></span>

[<span data-ttu-id="082b8-136">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="082b8-136">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)

[<span data-ttu-id="082b8-137">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="082b8-137">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)
