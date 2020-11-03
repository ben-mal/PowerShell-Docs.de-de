---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-runspacedebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-RunspaceDebug
ms.openlocfilehash: 54fb9500a924d2e5de98489fa4fb391accb23d0c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214071"
---
# <span data-ttu-id="5a4e3-103">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="5a4e3-103">Enable-RunspaceDebug</span></span>

## <span data-ttu-id="5a4e3-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5a4e3-104">SYNOPSIS</span></span>
<span data-ttu-id="5a4e3-105">Aktiviert das Debuggen in Runspaces, wo ein Haltepunkt beibehalten wird, bis ein Debugger angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5a4e3-105">Enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="5a4e3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5a4e3-106">SYNTAX</span></span>

### <span data-ttu-id="5a4e3-107">Runspacenameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="5a4e3-107">RunspaceNameParameterSet (Default)</span></span>

```
Enable-RunspaceDebug [-BreakAll] [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="5a4e3-108">Runspaceparameterset</span><span class="sxs-lookup"><span data-stu-id="5a4e3-108">RunspaceParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="5a4e3-109">Runspaceidparameterset</span><span class="sxs-lookup"><span data-stu-id="5a4e3-109">RunspaceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="5a4e3-110">Runspaceinstanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="5a4e3-110">RunspaceInstanceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="5a4e3-111">Processnameparameterset</span><span class="sxs-lookup"><span data-stu-id="5a4e3-111">ProcessNameParameterSet</span></span>

```
Enable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="5a4e3-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5a4e3-112">DESCRIPTION</span></span>

<span data-ttu-id="5a4e3-113">Das- `Enable-RunspaceDebug` Cmdlet aktiviert das Debuggen in Runspaces, wo ein Haltepunkt beibehalten wird, bis ein Debugger angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5a4e3-113">The `Enable-RunspaceDebug` cmdlet enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="5a4e3-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5a4e3-114">EXAMPLES</span></span>

### <span data-ttu-id="5a4e3-115">1: Aktivieren Sie den Standard-Runspace-Debugger.</span><span class="sxs-lookup"><span data-stu-id="5a4e3-115">1: Enable the default runspace debugger</span></span>

```powershell
Enable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            True       False
```

## <span data-ttu-id="5a4e3-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5a4e3-116">PARAMETERS</span></span>

### <span data-ttu-id="5a4e3-117">-Appdomainname</span><span class="sxs-lookup"><span data-stu-id="5a4e3-117">-AppDomainName</span></span>

<span data-ttu-id="5a4e3-118">Der Name der Anwendungsdomäne, die den PowerShell-Runspace hostet.</span><span class="sxs-lookup"><span data-stu-id="5a4e3-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="5a4e3-119">-Breakall</span><span class="sxs-lookup"><span data-stu-id="5a4e3-119">-BreakAll</span></span>

<span data-ttu-id="5a4e3-120">Bewirkt, dass alle laufenden Befehle oder Skripts im Runspace im Schritt Modus beendet werden, unabhängig davon, ob ein Debugger zurzeit angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="5a4e3-120">Causes any running command or script in the Runspace to stop in step mode, regardless of whether a debugger is currently attached.</span></span> <span data-ttu-id="5a4e3-121">Das Skript oder der Befehl bleibt angehalten, bis ein Debugger zum Debuggen des aktuellen Stopp Punkts angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5a4e3-121">The script or command will remain stopped until a debugger is attached to debug the current stop point.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RunspaceNameParameterSet, RunspaceParameterSet, RunspaceIdParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a4e3-122">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="5a4e3-122">-ProcessName</span></span>

<span data-ttu-id="5a4e3-123">Der Name des Prozesses, der den PowerShell-Runspace hostet.</span><span class="sxs-lookup"><span data-stu-id="5a4e3-123">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="5a4e3-124">-Runspace</span><span class="sxs-lookup"><span data-stu-id="5a4e3-124">-Runspace</span></span>

<span data-ttu-id="5a4e3-125">Mindestens ein **Runspace** -Objekt, das deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5a4e3-125">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="5a4e3-126">-Runspaceid</span><span class="sxs-lookup"><span data-stu-id="5a4e3-126">-RunspaceId</span></span>

<span data-ttu-id="5a4e3-127">Mindestens eine zu deaktivier Ende **Runspace** -ID-Nummer.</span><span class="sxs-lookup"><span data-stu-id="5a4e3-127">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="5a4e3-128">-Runspaceinstanceid</span><span class="sxs-lookup"><span data-stu-id="5a4e3-128">-RunspaceInstanceId</span></span>

<span data-ttu-id="5a4e3-129">Mindestens eine **Runspace** -GUIDs, die deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5a4e3-129">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="5a4e3-130">-Runspacename</span><span class="sxs-lookup"><span data-stu-id="5a4e3-130">-RunspaceName</span></span>

<span data-ttu-id="5a4e3-131">Mindestens ein **Runspace** -Name, der deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5a4e3-131">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="5a4e3-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5a4e3-132">CommonParameters</span></span>

<span data-ttu-id="5a4e3-133">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5a4e3-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5a4e3-134">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5a4e3-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5a4e3-135">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5a4e3-135">INPUTS</span></span>

## <span data-ttu-id="5a4e3-136">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5a4e3-136">OUTPUTS</span></span>

## <span data-ttu-id="5a4e3-137">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5a4e3-137">NOTES</span></span>

## <span data-ttu-id="5a4e3-138">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5a4e3-138">RELATED LINKS</span></span>

[<span data-ttu-id="5a4e3-139">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="5a4e3-139">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="5a4e3-140">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="5a4e3-140">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)
