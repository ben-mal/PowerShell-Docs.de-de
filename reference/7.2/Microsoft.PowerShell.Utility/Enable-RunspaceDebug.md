---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-runspacedebug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-RunspaceDebug
ms.openlocfilehash: 26ab9b9135eedafa0238eab5c07aa7abb7880ed4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602315"
---
# <span data-ttu-id="d8969-102">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="d8969-102">Enable-RunspaceDebug</span></span>

## <span data-ttu-id="d8969-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d8969-103">SYNOPSIS</span></span>
<span data-ttu-id="d8969-104">Aktiviert das Debuggen in Runspaces, wo ein Haltepunkt beibehalten wird, bis ein Debugger angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d8969-104">Enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="d8969-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d8969-105">SYNTAX</span></span>

### <span data-ttu-id="d8969-106">Runspacenameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="d8969-106">RunspaceNameParameterSet (Default)</span></span>

```
Enable-RunspaceDebug [-BreakAll] [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="d8969-107">Runspaceparameterset</span><span class="sxs-lookup"><span data-stu-id="d8969-107">RunspaceParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="d8969-108">Runspaceidparameterset</span><span class="sxs-lookup"><span data-stu-id="d8969-108">RunspaceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="d8969-109">Runspaceinstanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="d8969-109">RunspaceInstanceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="d8969-110">Processnameparameterset</span><span class="sxs-lookup"><span data-stu-id="d8969-110">ProcessNameParameterSet</span></span>

```
Enable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="d8969-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8969-111">DESCRIPTION</span></span>

<span data-ttu-id="d8969-112">Das- `Enable-RunspaceDebug` Cmdlet aktiviert das Debuggen in Runspaces, wo ein Haltepunkt beibehalten wird, bis ein Debugger angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d8969-112">The `Enable-RunspaceDebug` cmdlet enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="d8969-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d8969-113">EXAMPLES</span></span>

### <span data-ttu-id="d8969-114">1: Aktivieren Sie den Standard-Runspace-Debugger.</span><span class="sxs-lookup"><span data-stu-id="d8969-114">1: Enable the default runspace debugger</span></span>

```powershell
Enable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            True       False
```

## <span data-ttu-id="d8969-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d8969-115">PARAMETERS</span></span>

### <span data-ttu-id="d8969-116">-Appdomainname</span><span class="sxs-lookup"><span data-stu-id="d8969-116">-AppDomainName</span></span>

<span data-ttu-id="d8969-117">Der Name der Anwendungsdomäne, die den PowerShell-Runspace hostet.</span><span class="sxs-lookup"><span data-stu-id="d8969-117">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="d8969-118">-Breakall</span><span class="sxs-lookup"><span data-stu-id="d8969-118">-BreakAll</span></span>

<span data-ttu-id="d8969-119">Bewirkt, dass alle laufenden Befehle oder Skripts im Runspace im Schritt Modus beendet werden, unabhängig davon, ob ein Debugger zurzeit angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="d8969-119">Causes any running command or script in the Runspace to stop in step mode, regardless of whether a debugger is currently attached.</span></span> <span data-ttu-id="d8969-120">Das Skript oder der Befehl bleibt angehalten, bis ein Debugger zum Debuggen des aktuellen Stopp Punkts angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d8969-120">The script or command will remain stopped until a debugger is attached to debug the current stop point.</span></span>

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

### <span data-ttu-id="d8969-121">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="d8969-121">-ProcessName</span></span>

<span data-ttu-id="d8969-122">Der Name des Prozesses, der den PowerShell-Runspace hostet.</span><span class="sxs-lookup"><span data-stu-id="d8969-122">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="d8969-123">-Runspace</span><span class="sxs-lookup"><span data-stu-id="d8969-123">-Runspace</span></span>

<span data-ttu-id="d8969-124">Mindestens ein **Runspace** -Objekt, das deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8969-124">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="d8969-125">-Runspaceid</span><span class="sxs-lookup"><span data-stu-id="d8969-125">-RunspaceId</span></span>

<span data-ttu-id="d8969-126">Mindestens eine zu deaktivier Ende **Runspace** -ID-Nummer.</span><span class="sxs-lookup"><span data-stu-id="d8969-126">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="d8969-127">-Runspaceinstanceid</span><span class="sxs-lookup"><span data-stu-id="d8969-127">-RunspaceInstanceId</span></span>

<span data-ttu-id="d8969-128">Mindestens eine **Runspace** -GUIDs, die deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8969-128">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="d8969-129">-Runspacename</span><span class="sxs-lookup"><span data-stu-id="d8969-129">-RunspaceName</span></span>

<span data-ttu-id="d8969-130">Mindestens ein **Runspace** -Name, der deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8969-130">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="d8969-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d8969-131">CommonParameters</span></span>

<span data-ttu-id="d8969-132">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d8969-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d8969-133">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d8969-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d8969-134">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d8969-134">INPUTS</span></span>

## <span data-ttu-id="d8969-135">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d8969-135">OUTPUTS</span></span>

## <span data-ttu-id="d8969-136">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d8969-136">NOTES</span></span>

## <span data-ttu-id="d8969-137">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d8969-137">RELATED LINKS</span></span>

[<span data-ttu-id="d8969-138">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="d8969-138">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="d8969-139">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="d8969-139">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)

