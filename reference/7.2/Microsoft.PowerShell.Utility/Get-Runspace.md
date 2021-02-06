---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Runspace
ms.openlocfilehash: 34843894cb6253e3d8e89072cf79cb9237d4fc19
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602322"
---
# <span data-ttu-id="5c030-102">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="5c030-102">Get-Runspace</span></span>

## <span data-ttu-id="5c030-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5c030-103">SYNOPSIS</span></span>
<span data-ttu-id="5c030-104">Ruft aktive Runspaces in einem PowerShell-Host Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="5c030-104">Gets active runspaces within a PowerShell host process.</span></span>

## <span data-ttu-id="5c030-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5c030-105">SYNTAX</span></span>

### <span data-ttu-id="5c030-106">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="5c030-106">NameParameterSet (Default)</span></span>

```
Get-Runspace [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="5c030-107">Idparameterset</span><span class="sxs-lookup"><span data-stu-id="5c030-107">IdParameterSet</span></span>

```
Get-Runspace [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="5c030-108">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="5c030-108">InstanceIdParameterSet</span></span>

```
Get-Runspace [-InstanceId] <Guid[]> [<CommonParameters>]
```

## <span data-ttu-id="5c030-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c030-109">DESCRIPTION</span></span>

<span data-ttu-id="5c030-110">Das- `Get-Runspace` Cmdlet ruft aktive Runspaces in einem PowerShell-Host Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="5c030-110">The `Get-Runspace` cmdlet gets active runspaces in a PowerShell host process.</span></span>

## <span data-ttu-id="5c030-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5c030-111">EXAMPLES</span></span>

### <span data-ttu-id="5c030-112">Beispiel 1: erhalten von Runspaces</span><span class="sxs-lookup"><span data-stu-id="5c030-112">Example 1: Get runspaces</span></span>

```powershell
Get-Runspace
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
  2 Runspace2       localhost       Local         Opened        Available
  3 Runspace3       localhost       Local         Opened        Available
```

### <span data-ttu-id="5c030-113">Beispiel 2: Get-Runspace nach ID</span><span class="sxs-lookup"><span data-stu-id="5c030-113">Example 2: Get runspace by Id</span></span>

```powershell
Get-Runspace -Id 2
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  2 Runspace2       localhost       Local         Opened        Available
```

### <span data-ttu-id="5c030-114">Beispiel 3: Ausführen von Runspace nach Name</span><span class="sxs-lookup"><span data-stu-id="5c030-114">Example 3: Get runspace by Name</span></span>

```powershell
Get-Runspace -Name Runspace1
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

### <span data-ttu-id="5c030-115">Beispiel 4: erhalten von Runspace nach InstanceId</span><span class="sxs-lookup"><span data-stu-id="5c030-115">Example 4: Get runspace by InstanceId</span></span>

<span data-ttu-id="5c030-116">In diesem Beispiel identifizieren wir mithilfe des Parameters einen verfügbaren Runspace `Name` und speichern das Rückgabe Objekt in der Variablen `$activeRunspace` .</span><span class="sxs-lookup"><span data-stu-id="5c030-116">In this example, we identify an available runspace using the `Name` parameter and store the return object to the variable `$activeRunspace`.</span></span> <span data-ttu-id="5c030-117">Dies ermöglicht es Ihnen, die Eigenschaften des **Runspace** in nachfolgenden Ausführungen von zu verwenden `Get-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="5c030-117">This allows you to use the properties of the **Runspace** in subsequent runs of `Get-Runspace`.</span></span>

```powershell
$activeRunspace = Get-Runspace -Name Runspace1
Get-Runspace -InstanceId $activeRunspace.InstanceId
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

## <span data-ttu-id="5c030-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5c030-118">PARAMETERS</span></span>

### <span data-ttu-id="5c030-119">-Id</span><span class="sxs-lookup"><span data-stu-id="5c030-119">-Id</span></span>

<span data-ttu-id="5c030-120">Gibt die ID eines Runspace an.</span><span class="sxs-lookup"><span data-stu-id="5c030-120">Specifies the Id of a runspace</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5c030-121">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="5c030-121">-InstanceId</span></span>

<span data-ttu-id="5c030-122">Gibt die Instanz-ID-GUID eines laufenden Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="5c030-122">Specifies the instance ID GUID of a running job.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5c030-123">-Name</span><span class="sxs-lookup"><span data-stu-id="5c030-123">-Name</span></span>

<span data-ttu-id="5c030-124">Gibt den Namen eines Runspace an.</span><span class="sxs-lookup"><span data-stu-id="5c030-124">Specifies the Name of a runspace</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5c030-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5c030-125">CommonParameters</span></span>

<span data-ttu-id="5c030-126">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5c030-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5c030-127">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5c030-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5c030-128">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5c030-128">INPUTS</span></span>

## <span data-ttu-id="5c030-129">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5c030-129">OUTPUTS</span></span>

### <span data-ttu-id="5c030-130">System. Management. Automation. Runspaces. Runspace</span><span class="sxs-lookup"><span data-stu-id="5c030-130">System.Management.Automation.Runspaces.Runspace</span></span>

<span data-ttu-id="5c030-131">Sie können die Ergebnisse eines `Get-Runspace` Befehls an die Pipeline übergeben `Debug-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="5c030-131">You can pipe the results of a `Get-Runspace` command to `Debug-Runspace`.</span></span>

## <span data-ttu-id="5c030-132">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5c030-132">NOTES</span></span>

## <span data-ttu-id="5c030-133">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5c030-133">RELATED LINKS</span></span>

[<span data-ttu-id="5c030-134">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="5c030-134">Debug-Runspace</span></span>](Debug-Runspace.md)

