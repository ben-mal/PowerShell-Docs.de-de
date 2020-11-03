---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Runspace
ms.openlocfilehash: fb1076e7bb0843fe7208d00e51e19063c27dfa68
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213940"
---
# <span data-ttu-id="4b2ff-103">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="4b2ff-103">Get-Runspace</span></span>

## <span data-ttu-id="4b2ff-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4b2ff-104">SYNOPSIS</span></span>
<span data-ttu-id="4b2ff-105">Ruft aktive Runspaces in einem PowerShell-Host Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="4b2ff-105">Gets active runspaces within a PowerShell host process.</span></span>

## <span data-ttu-id="4b2ff-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4b2ff-106">SYNTAX</span></span>

### <span data-ttu-id="4b2ff-107">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="4b2ff-107">NameParameterSet (Default)</span></span>

```
Get-Runspace [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="4b2ff-108">Idparameterset</span><span class="sxs-lookup"><span data-stu-id="4b2ff-108">IdParameterSet</span></span>

```
Get-Runspace [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="4b2ff-109">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="4b2ff-109">InstanceIdParameterSet</span></span>

```
Get-Runspace [-InstanceId] <Guid[]> [<CommonParameters>]
```

## <span data-ttu-id="4b2ff-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4b2ff-110">DESCRIPTION</span></span>

<span data-ttu-id="4b2ff-111">Das- `Get-Runspace` Cmdlet ruft aktive Runspaces in einem PowerShell-Host Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="4b2ff-111">The `Get-Runspace` cmdlet gets active runspaces in a PowerShell host process.</span></span>

## <span data-ttu-id="4b2ff-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4b2ff-112">EXAMPLES</span></span>

### <span data-ttu-id="4b2ff-113">Beispiel 1: erhalten von Runspaces</span><span class="sxs-lookup"><span data-stu-id="4b2ff-113">Example 1: Get runspaces</span></span>

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

### <span data-ttu-id="4b2ff-114">Beispiel 2: Get-Runspace nach ID</span><span class="sxs-lookup"><span data-stu-id="4b2ff-114">Example 2: Get runspace by Id</span></span>

```powershell
Get-Runspace -Id 2
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  2 Runspace2       localhost       Local         Opened        Available
```

### <span data-ttu-id="4b2ff-115">Beispiel 3: Ausführen von Runspace nach Name</span><span class="sxs-lookup"><span data-stu-id="4b2ff-115">Example 3: Get runspace by Name</span></span>

```powershell
Get-Runspace -Name Runspace1
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

### <span data-ttu-id="4b2ff-116">Beispiel 4: erhalten von Runspace nach InstanceId</span><span class="sxs-lookup"><span data-stu-id="4b2ff-116">Example 4: Get runspace by InstanceId</span></span>

<span data-ttu-id="4b2ff-117">In diesem Beispiel identifizieren wir mithilfe des Parameters einen verfügbaren Runspace `Name` und speichern das Rückgabe Objekt in der Variablen `$activeRunspace` .</span><span class="sxs-lookup"><span data-stu-id="4b2ff-117">In this example, we identify an available runspace using the `Name` parameter and store the return object to the variable `$activeRunspace`.</span></span> <span data-ttu-id="4b2ff-118">Dies ermöglicht es Ihnen, die Eigenschaften des **Runspace** in nachfolgenden Ausführungen von zu verwenden `Get-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="4b2ff-118">This allows you to use the properties of the **Runspace** in subsequent runs of `Get-Runspace`.</span></span>

```powershell
$activeRunspace = Get-Runspace -Name Runspace1
Get-Runspace -InstanceId $activeRunspace.InstanceId
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

## <span data-ttu-id="4b2ff-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4b2ff-119">PARAMETERS</span></span>

### <span data-ttu-id="4b2ff-120">-Id</span><span class="sxs-lookup"><span data-stu-id="4b2ff-120">-Id</span></span>

<span data-ttu-id="4b2ff-121">Gibt die ID eines Runspace an.</span><span class="sxs-lookup"><span data-stu-id="4b2ff-121">Specifies the Id of a runspace</span></span>

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

### <span data-ttu-id="4b2ff-122">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="4b2ff-122">-InstanceId</span></span>

<span data-ttu-id="4b2ff-123">Gibt die Instanz-ID-GUID eines laufenden Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="4b2ff-123">Specifies the instance ID GUID of a running job.</span></span>

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

### <span data-ttu-id="4b2ff-124">-Name</span><span class="sxs-lookup"><span data-stu-id="4b2ff-124">-Name</span></span>

<span data-ttu-id="4b2ff-125">Gibt den Namen eines Runspace an.</span><span class="sxs-lookup"><span data-stu-id="4b2ff-125">Specifies the Name of a runspace</span></span>

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

### <span data-ttu-id="4b2ff-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4b2ff-126">CommonParameters</span></span>

<span data-ttu-id="4b2ff-127">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4b2ff-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4b2ff-128">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4b2ff-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4b2ff-129">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4b2ff-129">INPUTS</span></span>

## <span data-ttu-id="4b2ff-130">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4b2ff-130">OUTPUTS</span></span>

### <span data-ttu-id="4b2ff-131">System. Management. Automation. Runspaces. Runspace</span><span class="sxs-lookup"><span data-stu-id="4b2ff-131">System.Management.Automation.Runspaces.Runspace</span></span>

<span data-ttu-id="4b2ff-132">Sie können die Ergebnisse eines `Get-Runspace` Befehls an die Pipeline übergeben `Debug-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="4b2ff-132">You can pipe the results of a `Get-Runspace` command to `Debug-Runspace`.</span></span>

## <span data-ttu-id="4b2ff-133">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4b2ff-133">NOTES</span></span>

## <span data-ttu-id="4b2ff-134">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4b2ff-134">RELATED LINKS</span></span>

[<span data-ttu-id="4b2ff-135">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="4b2ff-135">Debug-Runspace</span></span>](Debug-Runspace.md)
