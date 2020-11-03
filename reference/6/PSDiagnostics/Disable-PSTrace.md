---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: 3f99869825b2255d3f5487c48b6eaa90a4ae901f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212463"
---
# <span data-ttu-id="4fa8a-102">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="4fa8a-102">Disable-PSTrace</span></span>

## <span data-ttu-id="4fa8a-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4fa8a-103">SYNOPSIS</span></span>
<span data-ttu-id="4fa8a-104">Deaktiviert die Protokolle von Microsoft-Windows-PowerShell-Ereignis Anbietern.</span><span class="sxs-lookup"><span data-stu-id="4fa8a-104">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="4fa8a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4fa8a-105">SYNTAX</span></span>

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="4fa8a-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4fa8a-106">DESCRIPTION</span></span>

<span data-ttu-id="4fa8a-107">Dieses Cmdlet deaktiviert die Betriebs-und Analyse Ereignisprotokolle des Microsoft-Windows-PowerShell-Ereignis Anbieters.</span><span class="sxs-lookup"><span data-stu-id="4fa8a-107">This cmdlet disables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="4fa8a-108">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="4fa8a-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="4fa8a-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4fa8a-109">EXAMPLES</span></span>

### <span data-ttu-id="4fa8a-110">Beispiel 1: Deaktivieren des analytischen Ereignis Protokolls für PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fa8a-110">Example 1: Disable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="4fa8a-111">Im folgenden Beispiel wird nur das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4fa8a-111">The following example disables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Disable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="4fa8a-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4fa8a-112">PARAMETERS</span></span>

### <span data-ttu-id="4fa8a-113">-Analytily</span><span class="sxs-lookup"><span data-stu-id="4fa8a-113">-AnalyticOnly</span></span>

<span data-ttu-id="4fa8a-114">Wenn dieser Parameter verwendet wird, wird das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters vom Cmdlet deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4fa8a-114">When this parameter is used, the cmdlet disables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="4fa8a-115">Das Betriebs Ereignisprotokoll wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="4fa8a-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="4fa8a-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4fa8a-116">CommonParameters</span></span>
<span data-ttu-id="4fa8a-117">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4fa8a-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4fa8a-118">Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4fa8a-118">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4fa8a-119">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4fa8a-119">INPUTS</span></span>

### <span data-ttu-id="4fa8a-120">Keine</span><span class="sxs-lookup"><span data-stu-id="4fa8a-120">None</span></span>

## <span data-ttu-id="4fa8a-121">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4fa8a-121">OUTPUTS</span></span>

### <span data-ttu-id="4fa8a-122">Keine</span><span class="sxs-lookup"><span data-stu-id="4fa8a-122">None</span></span>

## <span data-ttu-id="4fa8a-123">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4fa8a-123">NOTES</span></span>

<span data-ttu-id="4fa8a-124">Dieses Cmdlet verwendet die `Get-LogProperties` `Set-LogProperties` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="4fa8a-124">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="4fa8a-125">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="4fa8a-125">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="4fa8a-126">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4fa8a-126">RELATED LINKS</span></span>

[<span data-ttu-id="4fa8a-127">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="4fa8a-127">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="4fa8a-128">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="4fa8a-128">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="4fa8a-129">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="4fa8a-129">Enable-PSTrace</span></span>](Enable-PSTrace.md)
