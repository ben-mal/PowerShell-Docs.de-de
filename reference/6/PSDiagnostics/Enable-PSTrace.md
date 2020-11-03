---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: d5008d5105b18b5a3d0423cab4282735e3d382d8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212484"
---
# <span data-ttu-id="5828d-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="5828d-102">Enable-PSTrace</span></span>

## <span data-ttu-id="5828d-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5828d-103">SYNOPSIS</span></span>
<span data-ttu-id="5828d-104">Aktiviert die Protokolle von Microsoft-Windows-PowerShell-Ereignis Anbietern.</span><span class="sxs-lookup"><span data-stu-id="5828d-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="5828d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5828d-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="5828d-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5828d-106">DESCRIPTION</span></span>

<span data-ttu-id="5828d-107">Dieses Cmdlet aktiviert die Betriebs-und Analyse Ereignisprotokolle des Microsoft-Windows-PowerShell-Ereignis Anbieters.</span><span class="sxs-lookup"><span data-stu-id="5828d-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="5828d-108">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="5828d-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="5828d-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5828d-109">EXAMPLES</span></span>

### <span data-ttu-id="5828d-110">Beispiel 1: Aktivieren des analytischen Ereignis Protokolls für PowerShell</span><span class="sxs-lookup"><span data-stu-id="5828d-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="5828d-111">Im folgenden Beispiel wird nur das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5828d-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="5828d-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5828d-112">PARAMETERS</span></span>

### <span data-ttu-id="5828d-113">-Analytily</span><span class="sxs-lookup"><span data-stu-id="5828d-113">-AnalyticOnly</span></span>

<span data-ttu-id="5828d-114">Wenn dieser Parameter verwendet wird, aktiviert das Cmdlet das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="5828d-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="5828d-115">Das Betriebs Ereignisprotokoll wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="5828d-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="5828d-116">-Force</span><span class="sxs-lookup"><span data-stu-id="5828d-116">-Force</span></span>

<span data-ttu-id="5828d-117">Wird verwendet, um die Änderung ohne Eingabeaufforderung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="5828d-117">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="5828d-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5828d-118">CommonParameters</span></span>
<span data-ttu-id="5828d-119">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5828d-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5828d-120">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5828d-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5828d-121">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5828d-121">INPUTS</span></span>

### <span data-ttu-id="5828d-122">Keine</span><span class="sxs-lookup"><span data-stu-id="5828d-122">None</span></span>

## <span data-ttu-id="5828d-123">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5828d-123">OUTPUTS</span></span>

### <span data-ttu-id="5828d-124">Keine</span><span class="sxs-lookup"><span data-stu-id="5828d-124">None</span></span>

## <span data-ttu-id="5828d-125">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5828d-125">NOTES</span></span>

<span data-ttu-id="5828d-126">Dieses Cmdlet verwendet die `Get-LogProperties` `Set-LogProperties` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="5828d-126">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="5828d-127">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="5828d-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="5828d-128">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5828d-128">RELATED LINKS</span></span>

[<span data-ttu-id="5828d-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="5828d-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="5828d-130">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="5828d-130">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="5828d-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="5828d-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)
