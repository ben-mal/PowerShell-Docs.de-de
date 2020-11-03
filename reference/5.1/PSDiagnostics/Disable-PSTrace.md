---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: fc58e0bcfdd0b4ee7c7ee383b44f7d7f428c34c0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213564"
---
# <span data-ttu-id="aee29-102">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="aee29-102">Disable-PSTrace</span></span>

## <span data-ttu-id="aee29-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="aee29-103">SYNOPSIS</span></span>
<span data-ttu-id="aee29-104">Deaktiviert die Protokolle von Microsoft-Windows-PowerShell-Ereignis Anbietern.</span><span class="sxs-lookup"><span data-stu-id="aee29-104">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="aee29-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aee29-105">SYNTAX</span></span>

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="aee29-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aee29-106">DESCRIPTION</span></span>

<span data-ttu-id="aee29-107">Dieses Cmdlet deaktiviert die Betriebs-und Analyse Ereignisprotokolle des Microsoft-Windows-PowerShell-Ereignis Anbieters.</span><span class="sxs-lookup"><span data-stu-id="aee29-107">This cmdlet disables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="aee29-108">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="aee29-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="aee29-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="aee29-109">EXAMPLES</span></span>

### <span data-ttu-id="aee29-110">Beispiel 1: Deaktivieren des analytischen Ereignis Protokolls für PowerShell</span><span class="sxs-lookup"><span data-stu-id="aee29-110">Example 1: Disable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="aee29-111">Im folgenden Beispiel wird nur das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="aee29-111">The following example disables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Disable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="aee29-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aee29-112">PARAMETERS</span></span>

### <span data-ttu-id="aee29-113">-Analytily</span><span class="sxs-lookup"><span data-stu-id="aee29-113">-AnalyticOnly</span></span>

<span data-ttu-id="aee29-114">Wenn dieser Parameter verwendet wird, wird das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters vom Cmdlet deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="aee29-114">When this parameter is used, the cmdlet disables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="aee29-115">Das Betriebs Ereignisprotokoll wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="aee29-115">The Operational event log is not changed.</span></span>

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

## <span data-ttu-id="aee29-116">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="aee29-116">INPUTS</span></span>

### <span data-ttu-id="aee29-117">Keine</span><span class="sxs-lookup"><span data-stu-id="aee29-117">None</span></span>

## <span data-ttu-id="aee29-118">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="aee29-118">OUTPUTS</span></span>

### <span data-ttu-id="aee29-119">System.Object</span><span class="sxs-lookup"><span data-stu-id="aee29-119">System.Object</span></span>

## <span data-ttu-id="aee29-120">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="aee29-120">NOTES</span></span>

<span data-ttu-id="aee29-121">Dieses Cmdlet verwendet die `Get-LogProperties` `Set-LogProperties` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="aee29-121">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="aee29-122">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="aee29-122">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="aee29-123">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="aee29-123">RELATED LINKS</span></span>

[<span data-ttu-id="aee29-124">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="aee29-124">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="aee29-125">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="aee29-125">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="aee29-126">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="aee29-126">Enable-PSTrace</span></span>](Enable-PSTrace.md)
