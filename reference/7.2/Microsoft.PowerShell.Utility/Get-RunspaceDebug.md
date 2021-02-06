---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspacedebug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RunspaceDebug
ms.openlocfilehash: a77695fe32345fda8e6a0284cd29becb432a4273
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599847"
---
# <span data-ttu-id="50889-102">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="50889-102">Get-RunspaceDebug</span></span>

## <span data-ttu-id="50889-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="50889-103">SYNOPSIS</span></span>
<span data-ttu-id="50889-104">Zeigt die Runspace-Debugoptionen an.</span><span class="sxs-lookup"><span data-stu-id="50889-104">Shows runspace debugging options.</span></span>

## <span data-ttu-id="50889-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="50889-105">SYNTAX</span></span>

### <span data-ttu-id="50889-106">Runspacenameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="50889-106">RunspaceNameParameterSet (Default)</span></span>

```
Get-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="50889-107">Runspaceparameterset</span><span class="sxs-lookup"><span data-stu-id="50889-107">RunspaceParameterSet</span></span>

```
Get-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="50889-108">Runspaceidparameterset</span><span class="sxs-lookup"><span data-stu-id="50889-108">RunspaceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="50889-109">Runspaceinstanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="50889-109">RunspaceInstanceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="50889-110">Processnameparameterset</span><span class="sxs-lookup"><span data-stu-id="50889-110">ProcessNameParameterSet</span></span>

```
Get-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="50889-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="50889-111">DESCRIPTION</span></span>

<span data-ttu-id="50889-112">Das- `Get-RunspaceDebug` Cmdlet zeigt Runspace-Debugoptionen.</span><span class="sxs-lookup"><span data-stu-id="50889-112">The `Get-RunspaceDebug` cmdlet shows runspace debugging options.</span></span>

## <span data-ttu-id="50889-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="50889-113">EXAMPLES</span></span>

### <span data-ttu-id="50889-114">1: zeigt den Status des standardrunspace-Debuggers an.</span><span class="sxs-lookup"><span data-stu-id="50889-114">1: Show the state of the default runspace debugger</span></span>

```powershell
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="50889-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="50889-115">PARAMETERS</span></span>

### <span data-ttu-id="50889-116">-Appdomainname</span><span class="sxs-lookup"><span data-stu-id="50889-116">-AppDomainName</span></span>

<span data-ttu-id="50889-117">Der Name der Anwendungsdomäne, die den PowerShell-Runspace hostet.</span><span class="sxs-lookup"><span data-stu-id="50889-117">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="50889-118">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="50889-118">-ProcessName</span></span>

<span data-ttu-id="50889-119">Der Name des Prozesses, der den PowerShell-Runspace hostet.</span><span class="sxs-lookup"><span data-stu-id="50889-119">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="50889-120">-Runspace</span><span class="sxs-lookup"><span data-stu-id="50889-120">-Runspace</span></span>

<span data-ttu-id="50889-121">Mindestens ein **Runspace** -Objekt, das deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="50889-121">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="50889-122">-Runspaceid</span><span class="sxs-lookup"><span data-stu-id="50889-122">-RunspaceId</span></span>

<span data-ttu-id="50889-123">Mindestens eine zu deaktivier Ende **Runspace** -ID-Nummer.</span><span class="sxs-lookup"><span data-stu-id="50889-123">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="50889-124">-Runspaceinstanceid</span><span class="sxs-lookup"><span data-stu-id="50889-124">-RunspaceInstanceId</span></span>

<span data-ttu-id="50889-125">Mindestens eine **Runspace** -GUIDs, die deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="50889-125">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="50889-126">-Runspacename</span><span class="sxs-lookup"><span data-stu-id="50889-126">-RunspaceName</span></span>

<span data-ttu-id="50889-127">Mindestens ein **Runspace** -Name, der deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="50889-127">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="50889-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="50889-128">CommonParameters</span></span>

<span data-ttu-id="50889-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="50889-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="50889-130">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="50889-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="50889-131">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="50889-131">INPUTS</span></span>

## <span data-ttu-id="50889-132">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="50889-132">OUTPUTS</span></span>

## <span data-ttu-id="50889-133">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="50889-133">NOTES</span></span>

## <span data-ttu-id="50889-134">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="50889-134">RELATED LINKS</span></span>

[<span data-ttu-id="50889-135">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="50889-135">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="50889-136">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="50889-136">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)

