---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: 2ec01393a46de84b59f06995473bdff6bd5b2b4f
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195025"
---
# <span data-ttu-id="a5177-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="a5177-102">Enable-PSTrace</span></span>

## <span data-ttu-id="a5177-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a5177-103">SYNOPSIS</span></span>
<span data-ttu-id="a5177-104">Aktiviert die Protokolle von Microsoft-Windows-PowerShell-Ereignis Anbietern.</span><span class="sxs-lookup"><span data-stu-id="a5177-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="a5177-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a5177-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly]
```

## <span data-ttu-id="a5177-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a5177-106">DESCRIPTION</span></span>

<span data-ttu-id="a5177-107">Dieses Cmdlet aktiviert die Betriebs-und Analyse Ereignisprotokolle des Microsoft-Windows-PowerShell-Ereignis Anbieters.</span><span class="sxs-lookup"><span data-stu-id="a5177-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="a5177-108">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="a5177-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="a5177-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a5177-109">EXAMPLES</span></span>

### <span data-ttu-id="a5177-110">Beispiel 1: Aktivieren des analytischen Ereignis Protokolls für PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5177-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="a5177-111">Im folgenden Beispiel wird nur das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a5177-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="a5177-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a5177-112">PARAMETERS</span></span>

### <span data-ttu-id="a5177-113">-Analytily</span><span class="sxs-lookup"><span data-stu-id="a5177-113">-AnalyticOnly</span></span>

<span data-ttu-id="a5177-114">Wenn dieser Parameter verwendet wird, aktiviert das Cmdlet das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="a5177-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="a5177-115">Das Betriebs Ereignisprotokoll wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="a5177-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="a5177-116">-Force</span><span class="sxs-lookup"><span data-stu-id="a5177-116">-Force</span></span>

<span data-ttu-id="a5177-117">Wird verwendet, um die Änderung ohne Eingabeaufforderung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="a5177-117">Used to force the change without prompting.</span></span>

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

## <span data-ttu-id="a5177-118">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a5177-118">INPUTS</span></span>

### <span data-ttu-id="a5177-119">Keine</span><span class="sxs-lookup"><span data-stu-id="a5177-119">None</span></span>

## <span data-ttu-id="a5177-120">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a5177-120">OUTPUTS</span></span>

### <span data-ttu-id="a5177-121">System.Object</span><span class="sxs-lookup"><span data-stu-id="a5177-121">System.Object</span></span>

## <span data-ttu-id="a5177-122">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a5177-122">NOTES</span></span>

<span data-ttu-id="a5177-123">Dieses Cmdlet verwendet die `Get-LogProperties` `Set-LogProperties` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="a5177-123">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="a5177-124">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="a5177-124">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="a5177-125">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a5177-125">RELATED LINKS</span></span>

[<span data-ttu-id="a5177-126">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="a5177-126">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="a5177-127">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="a5177-127">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="a5177-128">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="a5177-128">Disable-PSTrace</span></span>](Disable-PSTrace.md)
