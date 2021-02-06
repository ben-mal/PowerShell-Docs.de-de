---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-runspacedebug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-RunspaceDebug
ms.openlocfilehash: 589c8cb36a91de510ffc30973fe70729700ad020
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599628"
---
# <span data-ttu-id="1d56c-102">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="1d56c-102">Disable-RunspaceDebug</span></span>

## <span data-ttu-id="1d56c-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1d56c-103">SYNOPSIS</span></span>
<span data-ttu-id="1d56c-104">Deaktiviert das Debuggen in einem oder mehreren Runspaces und gibt alle ausstehenden Debugger-Stopps frei.</span><span class="sxs-lookup"><span data-stu-id="1d56c-104">Disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="1d56c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1d56c-105">SYNTAX</span></span>

### <span data-ttu-id="1d56c-106">Runspacenameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="1d56c-106">RunspaceNameParameterSet (Default)</span></span>

```
Disable-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="1d56c-107">Runspaceparameterset</span><span class="sxs-lookup"><span data-stu-id="1d56c-107">RunspaceParameterSet</span></span>

```
Disable-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="1d56c-108">Runspaceidparameterset</span><span class="sxs-lookup"><span data-stu-id="1d56c-108">RunspaceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="1d56c-109">Runspaceinstanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="1d56c-109">RunspaceInstanceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="1d56c-110">Processnameparameterset</span><span class="sxs-lookup"><span data-stu-id="1d56c-110">ProcessNameParameterSet</span></span>

```
Disable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="1d56c-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1d56c-111">DESCRIPTION</span></span>

<span data-ttu-id="1d56c-112">Das `Disable-RunspaceDebug` -Cmdlet deaktiviert das Debuggen in einem oder mehreren Runspaces und gibt alle ausstehenden Debugger-Stopps frei.</span><span class="sxs-lookup"><span data-stu-id="1d56c-112">The `Disable-RunspaceDebug` cmdlet disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="1d56c-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1d56c-113">EXAMPLES</span></span>

### <span data-ttu-id="1d56c-114">1: Deaktivieren des standardrunspace-Debuggers</span><span class="sxs-lookup"><span data-stu-id="1d56c-114">1: Disable the default runspace debugger</span></span>

```powershell
Disable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="1d56c-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1d56c-115">PARAMETERS</span></span>

### <span data-ttu-id="1d56c-116">-Appdomainname</span><span class="sxs-lookup"><span data-stu-id="1d56c-116">-AppDomainName</span></span>

<span data-ttu-id="1d56c-117">Der Name der Anwendungsdomäne, die den PowerShell-Runspace hostet.</span><span class="sxs-lookup"><span data-stu-id="1d56c-117">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="1d56c-118">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="1d56c-118">-ProcessName</span></span>

<span data-ttu-id="1d56c-119">Der Name des Prozesses, der den PowerShell-Runspace hostet.</span><span class="sxs-lookup"><span data-stu-id="1d56c-119">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="1d56c-120">-Runspace</span><span class="sxs-lookup"><span data-stu-id="1d56c-120">-Runspace</span></span>

<span data-ttu-id="1d56c-121">Mindestens ein **Runspace** -Objekt, das deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1d56c-121">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="1d56c-122">-Runspaceid</span><span class="sxs-lookup"><span data-stu-id="1d56c-122">-RunspaceId</span></span>

<span data-ttu-id="1d56c-123">Mindestens eine zu deaktivier Ende **Runspace** -ID-Nummer.</span><span class="sxs-lookup"><span data-stu-id="1d56c-123">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="1d56c-124">-Runspaceinstanceid</span><span class="sxs-lookup"><span data-stu-id="1d56c-124">-RunspaceInstanceId</span></span>

<span data-ttu-id="1d56c-125">Mindestens eine **Runspace** -GUIDs, die deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1d56c-125">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="1d56c-126">-Runspacename</span><span class="sxs-lookup"><span data-stu-id="1d56c-126">-RunspaceName</span></span>

<span data-ttu-id="1d56c-127">Mindestens ein **Runspace** -Name, der deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1d56c-127">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="1d56c-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1d56c-128">CommonParameters</span></span>

<span data-ttu-id="1d56c-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1d56c-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1d56c-130">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1d56c-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1d56c-131">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1d56c-131">INPUTS</span></span>

## <span data-ttu-id="1d56c-132">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1d56c-132">OUTPUTS</span></span>

## <span data-ttu-id="1d56c-133">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1d56c-133">NOTES</span></span>

## <span data-ttu-id="1d56c-134">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1d56c-134">RELATED LINKS</span></span>

[<span data-ttu-id="1d56c-135">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="1d56c-135">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)

[<span data-ttu-id="1d56c-136">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="1d56c-136">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)

