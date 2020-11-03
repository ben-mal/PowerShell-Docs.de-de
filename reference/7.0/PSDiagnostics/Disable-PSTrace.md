---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: 50ad2d48faee88c196942b13141d3ad57c51fdeb
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210071"
---
# <span data-ttu-id="a2765-102">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="a2765-102">Disable-PSTrace</span></span>

## <span data-ttu-id="a2765-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a2765-103">SYNOPSIS</span></span>
<span data-ttu-id="a2765-104">Deaktiviert die Protokolle von Microsoft-Windows-PowerShell-Ereignis Anbietern.</span><span class="sxs-lookup"><span data-stu-id="a2765-104">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="a2765-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a2765-105">SYNTAX</span></span>

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="a2765-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a2765-106">DESCRIPTION</span></span>

<span data-ttu-id="a2765-107">Dieses Cmdlet deaktiviert die Betriebs-und Analyse Ereignisprotokolle des Microsoft-Windows-PowerShell-Ereignis Anbieters.</span><span class="sxs-lookup"><span data-stu-id="a2765-107">This cmdlet disables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="a2765-108">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="a2765-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="a2765-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a2765-109">EXAMPLES</span></span>

### <span data-ttu-id="a2765-110">Beispiel 1: Deaktivieren des analytischen Ereignis Protokolls für PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2765-110">Example 1: Disable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="a2765-111">Im folgenden Beispiel wird nur das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a2765-111">The following example disables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Disable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="a2765-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a2765-112">PARAMETERS</span></span>

### <span data-ttu-id="a2765-113">-Analytily</span><span class="sxs-lookup"><span data-stu-id="a2765-113">-AnalyticOnly</span></span>

<span data-ttu-id="a2765-114">Wenn dieser Parameter verwendet wird, wird das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters vom Cmdlet deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a2765-114">When this parameter is used, the cmdlet disables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="a2765-115">Das Betriebs Ereignisprotokoll wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="a2765-115">The Operational event log is not changed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2765-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a2765-116">CommonParameters</span></span>
<span data-ttu-id="a2765-117">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a2765-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a2765-118">Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a2765-118">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a2765-119">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a2765-119">INPUTS</span></span>

### <span data-ttu-id="a2765-120">Keine</span><span class="sxs-lookup"><span data-stu-id="a2765-120">None</span></span>

## <span data-ttu-id="a2765-121">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a2765-121">OUTPUTS</span></span>

### <span data-ttu-id="a2765-122">Keine</span><span class="sxs-lookup"><span data-stu-id="a2765-122">None</span></span>

## <span data-ttu-id="a2765-123">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a2765-123">NOTES</span></span>

<span data-ttu-id="a2765-124">Dieses Cmdlet verwendet die `Get-LogProperties` `Set-LogProperties` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="a2765-124">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="a2765-125">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="a2765-125">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="a2765-126">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a2765-126">RELATED LINKS</span></span>

[<span data-ttu-id="a2765-127">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="a2765-127">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="a2765-128">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="a2765-128">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="a2765-129">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="a2765-129">Enable-PSTrace</span></span>](Enable-PSTrace.md)
