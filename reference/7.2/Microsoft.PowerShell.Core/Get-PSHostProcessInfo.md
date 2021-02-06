---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pshostprocessinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSHostProcessInfo
ms.openlocfilehash: 6528d25ea706ac63927ef3d23cf661489caae8aa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599836"
---
# <span data-ttu-id="e7b9f-102">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="e7b9f-102">Get-PSHostProcessInfo</span></span>

## <span data-ttu-id="e7b9f-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e7b9f-103">SYNOPSIS</span></span>
<span data-ttu-id="e7b9f-104">Ruft Prozessinformationen zum PowerShell-Host ab.</span><span class="sxs-lookup"><span data-stu-id="e7b9f-104">Gets process information about the PowerShell host.</span></span>

## <span data-ttu-id="e7b9f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e7b9f-105">SYNTAX</span></span>

### <span data-ttu-id="e7b9f-106">Processnameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="e7b9f-106">ProcessNameParameterSet (Default)</span></span>

```
Get-PSHostProcessInfo [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="e7b9f-107">Processparameterset</span><span class="sxs-lookup"><span data-stu-id="e7b9f-107">ProcessParameterSet</span></span>

```
Get-PSHostProcessInfo [-Process] <Process[]> [<CommonParameters>]
```

### <span data-ttu-id="e7b9f-108">Processidparameterset</span><span class="sxs-lookup"><span data-stu-id="e7b9f-108">ProcessIdParameterSet</span></span>

```
Get-PSHostProcessInfo [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="e7b9f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e7b9f-109">DESCRIPTION</span></span>

<span data-ttu-id="e7b9f-110">Mit dem- `Get-PSHostProcessInfo` Cmdlet werden Informationen zu PowerShell-Host Prozessen abgerufen, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e7b9f-110">The `Get-PSHostProcessInfo` cmdlet gets information about PowerShell host processes running on the local computer.</span></span>

<span data-ttu-id="e7b9f-111">Ab PowerShell 6,2 wird dieses Cmdlet auf nicht-Windows-Plattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e7b9f-111">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="e7b9f-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e7b9f-112">EXAMPLES</span></span>

### <span data-ttu-id="e7b9f-113">1: eine Liste der PowerShell-Hosts, die auf dem System ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="e7b9f-113">1: Get a list of PowerShell hosts running on the system</span></span>

```powershell
Get-PSHostProcessInfo
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
powershell      11204 DefaultAppDomain
pwsh            13912 DefaultAppDomain
```

### <span data-ttu-id="e7b9f-114">2: PowerShell-Hostinformationen für einen bestimmten Prozessnamen erhalten</span><span class="sxs-lookup"><span data-stu-id="e7b9f-114">2: Get PowerShell host information for a specific process name</span></span>

```powershell
Get-PSHostProcessInfo -Name pwsh
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
pwsh            13912 DefaultAppDomain
```

## <span data-ttu-id="e7b9f-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e7b9f-115">PARAMETERS</span></span>

### <span data-ttu-id="e7b9f-116">-Id</span><span class="sxs-lookup"><span data-stu-id="e7b9f-116">-Id</span></span>

<span data-ttu-id="e7b9f-117">Gibt einen Prozess mit der Prozess-ID an.</span><span class="sxs-lookup"><span data-stu-id="e7b9f-117">Specifies a process by the process ID.</span></span> <span data-ttu-id="e7b9f-118">Führen Sie das-Cmdlet aus, um eine Prozess-ID zu erhalten `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="e7b9f-118">To get a process ID, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="e7b9f-119">-Name</span><span class="sxs-lookup"><span data-stu-id="e7b9f-119">-Name</span></span>

<span data-ttu-id="e7b9f-120">Gibt einen Prozess anhand des Prozess namens an.</span><span class="sxs-lookup"><span data-stu-id="e7b9f-120">Specifies a process by the process name.</span></span> <span data-ttu-id="e7b9f-121">Um einen Prozessnamen zu erhalten, führen Sie das- `Get-Process` Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="e7b9f-121">To get a process name, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="e7b9f-122">-Prozess</span><span class="sxs-lookup"><span data-stu-id="e7b9f-122">-Process</span></span>

<span data-ttu-id="e7b9f-123">Gibt einen Prozess vom Prozess Objekt an.</span><span class="sxs-lookup"><span data-stu-id="e7b9f-123">Specifies a process by the process object.</span></span> <span data-ttu-id="e7b9f-124">Die einfachste Möglichkeit, diesen Parameter zu verwenden, besteht darin, die Ergebnisse eines Befehls zu speichern, der den `Get-Process` Prozess zurückgibt, den Sie in eine Variable eingeben möchten, und dann die Variable als Wert dieses Parameters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e7b9f-124">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="e7b9f-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e7b9f-125">CommonParameters</span></span>

<span data-ttu-id="e7b9f-126">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e7b9f-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e7b9f-127">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e7b9f-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e7b9f-128">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e7b9f-128">INPUTS</span></span>

### <span data-ttu-id="e7b9f-129">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="e7b9f-129">System.Diagnostics.Process</span></span>

<span data-ttu-id="e7b9f-130">Sie können ein **Prozess** Objekt `Get-Process` über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="e7b9f-130">You can pipe a **Process** object from `Get-Process` to this cmdlet.</span></span>

## <span data-ttu-id="e7b9f-131">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e7b9f-131">OUTPUTS</span></span>

### <span data-ttu-id="e7b9f-132">Microsoft. PowerShell. Commands. pshostprocessinfo</span><span class="sxs-lookup"><span data-stu-id="e7b9f-132">Microsoft.PowerShell.Commands.PSHostProcessInfo</span></span>

## <span data-ttu-id="e7b9f-133">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e7b9f-133">NOTES</span></span>

## <span data-ttu-id="e7b9f-134">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e7b9f-134">RELATED LINKS</span></span>

[<span data-ttu-id="e7b9f-135">Get-Process</span><span class="sxs-lookup"><span data-stu-id="e7b9f-135">Get-Process</span></span>](../Microsoft.PowerShell.Management/get-process.md)

