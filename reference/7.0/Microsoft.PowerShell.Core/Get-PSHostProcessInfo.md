---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pshostprocessinfo?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSHostProcessInfo
ms.openlocfilehash: 196b9bc1cb1e318e334e4002e83d73a466b6578d
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211295"
---
# <span data-ttu-id="a73af-103">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="a73af-103">Get-PSHostProcessInfo</span></span>

## <span data-ttu-id="a73af-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a73af-104">SYNOPSIS</span></span>
<span data-ttu-id="a73af-105">Ruft Prozessinformationen zum PowerShell-Host ab.</span><span class="sxs-lookup"><span data-stu-id="a73af-105">Gets process information about the PowerShell host.</span></span>

## <span data-ttu-id="a73af-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a73af-106">SYNTAX</span></span>

### <span data-ttu-id="a73af-107">Processnameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="a73af-107">ProcessNameParameterSet (Default)</span></span>

```
Get-PSHostProcessInfo [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="a73af-108">Processparameterset</span><span class="sxs-lookup"><span data-stu-id="a73af-108">ProcessParameterSet</span></span>

```
Get-PSHostProcessInfo [-Process] <Process[]> [<CommonParameters>]
```

### <span data-ttu-id="a73af-109">Processidparameterset</span><span class="sxs-lookup"><span data-stu-id="a73af-109">ProcessIdParameterSet</span></span>

```
Get-PSHostProcessInfo [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="a73af-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a73af-110">DESCRIPTION</span></span>

<span data-ttu-id="a73af-111">Mit dem- `Get-PSHostProcessInfo` Cmdlet werden Informationen zu PowerShell-Host Prozessen abgerufen, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a73af-111">The `Get-PSHostProcessInfo` cmdlet gets information about PowerShell host processes running on the local computer.</span></span>

<span data-ttu-id="a73af-112">Ab PowerShell 6,2 wird dieses Cmdlet auf nicht-Windows-Plattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a73af-112">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="a73af-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a73af-113">EXAMPLES</span></span>

### <span data-ttu-id="a73af-114">1: eine Liste der PowerShell-Hosts, die auf dem System ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="a73af-114">1: Get a list of PowerShell hosts running on the system</span></span>

```powershell
Get-PSHostProcessInfo
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
powershell      11204 DefaultAppDomain
pwsh            13912 DefaultAppDomain
```

### <span data-ttu-id="a73af-115">2: PowerShell-Hostinformationen für einen bestimmten Prozessnamen erhalten</span><span class="sxs-lookup"><span data-stu-id="a73af-115">2: Get PowerShell host information for a specific process name</span></span>

```powershell
Get-PSHostProcessInfo -Name pwsh
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
pwsh            13912 DefaultAppDomain
```

## <span data-ttu-id="a73af-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a73af-116">PARAMETERS</span></span>

### <span data-ttu-id="a73af-117">-Id</span><span class="sxs-lookup"><span data-stu-id="a73af-117">-Id</span></span>

<span data-ttu-id="a73af-118">Gibt einen Prozess mit der Prozess-ID an.</span><span class="sxs-lookup"><span data-stu-id="a73af-118">Specifies a process by the process ID.</span></span> <span data-ttu-id="a73af-119">Führen Sie das-Cmdlet aus, um eine Prozess-ID zu erhalten `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="a73af-119">To get a process ID, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="a73af-120">-Name</span><span class="sxs-lookup"><span data-stu-id="a73af-120">-Name</span></span>

<span data-ttu-id="a73af-121">Gibt einen Prozess anhand des Prozess namens an.</span><span class="sxs-lookup"><span data-stu-id="a73af-121">Specifies a process by the process name.</span></span> <span data-ttu-id="a73af-122">Um einen Prozessnamen zu erhalten, führen Sie das- `Get-Process` Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="a73af-122">To get a process name, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="a73af-123">-Prozess</span><span class="sxs-lookup"><span data-stu-id="a73af-123">-Process</span></span>

<span data-ttu-id="a73af-124">Gibt einen Prozess vom Prozess Objekt an.</span><span class="sxs-lookup"><span data-stu-id="a73af-124">Specifies a process by the process object.</span></span> <span data-ttu-id="a73af-125">Die einfachste Möglichkeit, diesen Parameter zu verwenden, besteht darin, die Ergebnisse eines Befehls zu speichern, der den `Get-Process` Prozess zurückgibt, den Sie in eine Variable eingeben möchten, und dann die Variable als Wert dieses Parameters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a73af-125">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="a73af-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a73af-126">CommonParameters</span></span>

<span data-ttu-id="a73af-127">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a73af-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a73af-128">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a73af-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a73af-129">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a73af-129">INPUTS</span></span>

### <span data-ttu-id="a73af-130">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="a73af-130">System.Diagnostics.Process</span></span>

<span data-ttu-id="a73af-131">Sie können ein **Prozess** Objekt `Get-Process` über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="a73af-131">You can pipe a **Process** object from `Get-Process` to this cmdlet.</span></span>

## <span data-ttu-id="a73af-132">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a73af-132">OUTPUTS</span></span>

### <span data-ttu-id="a73af-133">Microsoft. PowerShell. Commands. pshostprocessinfo</span><span class="sxs-lookup"><span data-stu-id="a73af-133">Microsoft.PowerShell.Commands.PSHostProcessInfo</span></span>

## <span data-ttu-id="a73af-134">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a73af-134">NOTES</span></span>

## <span data-ttu-id="a73af-135">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a73af-135">RELATED LINKS</span></span>

[<span data-ttu-id="a73af-136">Get-Process</span><span class="sxs-lookup"><span data-stu-id="a73af-136">Get-Process</span></span>](../Microsoft.PowerShell.Management/get-process.md)
