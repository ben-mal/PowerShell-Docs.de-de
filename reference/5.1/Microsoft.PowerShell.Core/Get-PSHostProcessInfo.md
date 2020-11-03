---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pshostprocessinfo?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSHostProcessInfo
ms.openlocfilehash: 5f3579e002030715d7e5926de5f6209cd61b0367
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212023"
---
# <span data-ttu-id="7dfd7-103">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="7dfd7-103">Get-PSHostProcessInfo</span></span>

## <span data-ttu-id="7dfd7-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7dfd7-104">SYNOPSIS</span></span>
<span data-ttu-id="7dfd7-105">Ruft Prozessinformationen zum PowerShell-Host ab.</span><span class="sxs-lookup"><span data-stu-id="7dfd7-105">Gets process information about the PowerShell host.</span></span>

## <span data-ttu-id="7dfd7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7dfd7-106">SYNTAX</span></span>

### <span data-ttu-id="7dfd7-107">Processnameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="7dfd7-107">ProcessNameParameterSet (Default)</span></span>

```
Get-PSHostProcessInfo [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="7dfd7-108">Processparameterset</span><span class="sxs-lookup"><span data-stu-id="7dfd7-108">ProcessParameterSet</span></span>

```
Get-PSHostProcessInfo [-Process] <Process[]> [<CommonParameters>]
```

### <span data-ttu-id="7dfd7-109">Processidparameterset</span><span class="sxs-lookup"><span data-stu-id="7dfd7-109">ProcessIdParameterSet</span></span>

```
Get-PSHostProcessInfo [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="7dfd7-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7dfd7-110">DESCRIPTION</span></span>

<span data-ttu-id="7dfd7-111">Mit dem- `Get-PSHostProcessInfo` Cmdlet werden Informationen zu PowerShell-Host Prozessen abgerufen, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7dfd7-111">The `Get-PSHostProcessInfo` cmdlet gets information about PowerShell host processes running on the local computer.</span></span>

<span data-ttu-id="7dfd7-112">Ab PowerShell 6,2 wird dieses Cmdlet auf nicht-Windows-Plattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7dfd7-112">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="7dfd7-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7dfd7-113">EXAMPLES</span></span>

### <span data-ttu-id="7dfd7-114">1: eine Liste der PowerShell-Hosts, die auf dem System ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="7dfd7-114">1: Get a list of PowerShell hosts running on the system</span></span>

```powershell
Get-PSHostProcessInfo
```

```Output
ProcessName ProcessId AppDomainName    MainWindowTitle
----------- --------- -------------    ---------------
powershell      14676 DefaultAppDomain Windows PowerShell
powershell       5184 DefaultAppDomain Windows PowerShell
```

### <span data-ttu-id="7dfd7-115">2: PowerShell-Hostinformationen für einen bestimmten Prozess</span><span class="sxs-lookup"><span data-stu-id="7dfd7-115">2: Get PowerShell host information for a specific process</span></span>

```powershell
Get-PSHostProcessInfo -Id 14676
```

```Output
ProcessName ProcessId AppDomainName    MainWindowTitle
----------- --------- -------------    ---------------
powershell      14676 DefaultAppDomain Windows PowerShell
```

## <span data-ttu-id="7dfd7-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7dfd7-116">PARAMETERS</span></span>

### <span data-ttu-id="7dfd7-117">-Id</span><span class="sxs-lookup"><span data-stu-id="7dfd7-117">-Id</span></span>

<span data-ttu-id="7dfd7-118">Gibt einen Prozess mit der Prozess-ID an.</span><span class="sxs-lookup"><span data-stu-id="7dfd7-118">Specifies a process by the process ID.</span></span> <span data-ttu-id="7dfd7-119">Führen Sie das-Cmdlet aus, um eine Prozess-ID zu erhalten `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="7dfd7-119">To get a process ID, run the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: ProcessIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7dfd7-120">-Name</span><span class="sxs-lookup"><span data-stu-id="7dfd7-120">-Name</span></span>

<span data-ttu-id="7dfd7-121">Gibt einen Prozess anhand des Prozess namens an.</span><span class="sxs-lookup"><span data-stu-id="7dfd7-121">Specifies a process by the process name.</span></span> <span data-ttu-id="7dfd7-122">Um einen Prozessnamen zu erhalten, führen Sie das- `Get-Process` Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="7dfd7-122">To get a process name, run the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7dfd7-123">-Prozess</span><span class="sxs-lookup"><span data-stu-id="7dfd7-123">-Process</span></span>

<span data-ttu-id="7dfd7-124">Gibt einen Prozess vom Prozess Objekt an.</span><span class="sxs-lookup"><span data-stu-id="7dfd7-124">Specifies a process by the process object.</span></span> <span data-ttu-id="7dfd7-125">Die einfachste Möglichkeit, diesen Parameter zu verwenden, besteht darin, die Ergebnisse eines Befehls zu speichern, der den `Get-Process` Prozess zurückgibt, den Sie in eine Variable eingeben möchten, und dann die Variable als Wert dieses Parameters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7dfd7-125">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: ProcessParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7dfd7-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7dfd7-126">CommonParameters</span></span>

<span data-ttu-id="7dfd7-127">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7dfd7-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7dfd7-128">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7dfd7-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7dfd7-129">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7dfd7-129">INPUTS</span></span>

### <span data-ttu-id="7dfd7-130">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="7dfd7-130">System.Diagnostics.Process</span></span>

<span data-ttu-id="7dfd7-131">Sie können ein **Prozess** Objekt `Get-Process` über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="7dfd7-131">You can pipe a **Process** object from `Get-Process` to this cmdlet.</span></span>

## <span data-ttu-id="7dfd7-132">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7dfd7-132">OUTPUTS</span></span>

### <span data-ttu-id="7dfd7-133">Microsoft. PowerShell. Commands. pshostprocessinfo</span><span class="sxs-lookup"><span data-stu-id="7dfd7-133">Microsoft.PowerShell.Commands.PSHostProcessInfo</span></span>

## <span data-ttu-id="7dfd7-134">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7dfd7-134">NOTES</span></span>

## <span data-ttu-id="7dfd7-135">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7dfd7-135">RELATED LINKS</span></span>

[<span data-ttu-id="7dfd7-136">Get-Process</span><span class="sxs-lookup"><span data-stu-id="7dfd7-136">Get-Process</span></span>](../Microsoft.PowerShell.Management/get-process.md)
