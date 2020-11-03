---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: 9abc91086d42ec7b813695e241820947f7fb0acc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213543"
---
# <span data-ttu-id="7934a-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="7934a-102">Enable-PSTrace</span></span>

## <span data-ttu-id="7934a-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7934a-103">SYNOPSIS</span></span>
<span data-ttu-id="7934a-104">Aktiviert die Protokolle von Microsoft-Windows-PowerShell-Ereignis Anbietern.</span><span class="sxs-lookup"><span data-stu-id="7934a-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="7934a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7934a-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly]
```

## <span data-ttu-id="7934a-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7934a-106">DESCRIPTION</span></span>

<span data-ttu-id="7934a-107">Dieses Cmdlet aktiviert die Betriebs-und Analyse Ereignisprotokolle des Microsoft-Windows-PowerShell-Ereignis Anbieters.</span><span class="sxs-lookup"><span data-stu-id="7934a-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="7934a-108">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="7934a-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="7934a-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7934a-109">EXAMPLES</span></span>

### <span data-ttu-id="7934a-110">Beispiel 1: Aktivieren des analytischen Ereignis Protokolls für PowerShell</span><span class="sxs-lookup"><span data-stu-id="7934a-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="7934a-111">Im folgenden Beispiel wird nur das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7934a-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="7934a-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7934a-112">PARAMETERS</span></span>

### <span data-ttu-id="7934a-113">-Analytily</span><span class="sxs-lookup"><span data-stu-id="7934a-113">-AnalyticOnly</span></span>

<span data-ttu-id="7934a-114">Wenn dieser Parameter verwendet wird, aktiviert das Cmdlet das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="7934a-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="7934a-115">Das Betriebs Ereignisprotokoll wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="7934a-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="7934a-116">-Force</span><span class="sxs-lookup"><span data-stu-id="7934a-116">-Force</span></span>

<span data-ttu-id="7934a-117">Wird verwendet, um die Änderung ohne Eingabeaufforderung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="7934a-117">Used to force the change without prompting.</span></span>

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

## <span data-ttu-id="7934a-118">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7934a-118">INPUTS</span></span>

### <span data-ttu-id="7934a-119">Keine</span><span class="sxs-lookup"><span data-stu-id="7934a-119">None</span></span>

## <span data-ttu-id="7934a-120">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7934a-120">OUTPUTS</span></span>

### <span data-ttu-id="7934a-121">System.Object</span><span class="sxs-lookup"><span data-stu-id="7934a-121">System.Object</span></span>

## <span data-ttu-id="7934a-122">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7934a-122">NOTES</span></span>

<span data-ttu-id="7934a-123">Dieses Cmdlet verwendet die `Get-LogProperties` `Set-LogProperties` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="7934a-123">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="7934a-124">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="7934a-124">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="7934a-125">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7934a-125">RELATED LINKS</span></span>

[<span data-ttu-id="7934a-126">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="7934a-126">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="7934a-127">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="7934a-127">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="7934a-128">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="7934a-128">Disable-PSTrace</span></span>](Disable-PSTrace.md)
