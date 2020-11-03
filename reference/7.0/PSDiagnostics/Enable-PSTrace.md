---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: fea84d9ae83eae88f9a665e8a49aaf2e6743127d
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211359"
---
# <span data-ttu-id="31d35-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="31d35-102">Enable-PSTrace</span></span>

## <span data-ttu-id="31d35-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="31d35-103">SYNOPSIS</span></span>
<span data-ttu-id="31d35-104">Aktiviert die Protokolle von Microsoft-Windows-PowerShell-Ereignis Anbietern.</span><span class="sxs-lookup"><span data-stu-id="31d35-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="31d35-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="31d35-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="31d35-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="31d35-106">DESCRIPTION</span></span>

<span data-ttu-id="31d35-107">Dieses Cmdlet aktiviert die Betriebs-und Analyse Ereignisprotokolle des Microsoft-Windows-PowerShell-Ereignis Anbieters.</span><span class="sxs-lookup"><span data-stu-id="31d35-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="31d35-108">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="31d35-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="31d35-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="31d35-109">EXAMPLES</span></span>

### <span data-ttu-id="31d35-110">Beispiel 1: Aktivieren des analytischen Ereignis Protokolls für PowerShell</span><span class="sxs-lookup"><span data-stu-id="31d35-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="31d35-111">Im folgenden Beispiel wird nur das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters aktiviert.</span><span class="sxs-lookup"><span data-stu-id="31d35-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="31d35-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="31d35-112">PARAMETERS</span></span>

### <span data-ttu-id="31d35-113">-Analytily</span><span class="sxs-lookup"><span data-stu-id="31d35-113">-AnalyticOnly</span></span>

<span data-ttu-id="31d35-114">Wenn dieser Parameter verwendet wird, aktiviert das Cmdlet das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="31d35-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="31d35-115">Das Betriebs Ereignisprotokoll wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="31d35-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="31d35-116">-Force</span><span class="sxs-lookup"><span data-stu-id="31d35-116">-Force</span></span>

<span data-ttu-id="31d35-117">Wird verwendet, um die Änderung ohne Eingabeaufforderung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="31d35-117">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="31d35-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="31d35-118">CommonParameters</span></span>
<span data-ttu-id="31d35-119">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="31d35-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="31d35-120">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="31d35-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="31d35-121">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="31d35-121">INPUTS</span></span>

### <span data-ttu-id="31d35-122">Keine</span><span class="sxs-lookup"><span data-stu-id="31d35-122">None</span></span>

## <span data-ttu-id="31d35-123">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="31d35-123">OUTPUTS</span></span>

### <span data-ttu-id="31d35-124">Keine</span><span class="sxs-lookup"><span data-stu-id="31d35-124">None</span></span>

## <span data-ttu-id="31d35-125">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="31d35-125">NOTES</span></span>

<span data-ttu-id="31d35-126">Dieses Cmdlet verwendet die `Get-LogProperties` `Set-LogProperties` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="31d35-126">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="31d35-127">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="31d35-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="31d35-128">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="31d35-128">RELATED LINKS</span></span>

[<span data-ttu-id="31d35-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="31d35-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="31d35-130">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="31d35-130">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="31d35-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="31d35-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)
