---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: f67b5d9fe8da48cca5fd4ec7d2056a4702d3ff16
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213540"
---
# <span data-ttu-id="7da80-103">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="7da80-103">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="7da80-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7da80-104">SYNOPSIS</span></span>
<span data-ttu-id="7da80-105">Starten Sie eine Protokollierungs Sitzung mit aktiviertem WSMAN und PowerShell-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="7da80-105">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="7da80-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7da80-106">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="7da80-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7da80-107">DESCRIPTION</span></span>

<span data-ttu-id="7da80-108">Dieses Cmdlet startet eine Protokollierungs Sitzung mit den folgenden aktivierten PowerShell-Anbietern:</span><span class="sxs-lookup"><span data-stu-id="7da80-108">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="7da80-109">Microsoft-Windows-PowerShell</span><span class="sxs-lookup"><span data-stu-id="7da80-109">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="7da80-110">Microsoft-Windows-WinRM</span><span class="sxs-lookup"><span data-stu-id="7da80-110">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="7da80-111">Die Sitzung hat den Namen "pstrace".</span><span class="sxs-lookup"><span data-stu-id="7da80-111">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="7da80-112">Dieses Cmdlet verwendet das- `Start-Trace` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7da80-112">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="7da80-113">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="7da80-113">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="7da80-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7da80-114">EXAMPLES</span></span>

### <span data-ttu-id="7da80-115">Beispiel 1: Starten einer kombinierten Protokollierungs Sitzung</span><span class="sxs-lookup"><span data-stu-id="7da80-115">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="7da80-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7da80-116">PARAMETERS</span></span>

### <span data-ttu-id="7da80-117">-Donoteverschreiteexistingtrace</span><span class="sxs-lookup"><span data-stu-id="7da80-117">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="7da80-118">Standardmäßig werden die Ereignisse in "$PSHome \traces\pstrace.ETL" geschrieben.</span><span class="sxs-lookup"><span data-stu-id="7da80-118">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="7da80-119">Wenn dieser Parameter verwendet wird, erstellt das Cmdlet einen eindeutigen Dateinamen: "$PSHome \traces\ PSTrace_ {GUID}. ETL"</span><span class="sxs-lookup"><span data-stu-id="7da80-119">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7da80-120">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7da80-120">CommonParameters</span></span>

<span data-ttu-id="7da80-121">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7da80-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7da80-122">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7da80-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7da80-123">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7da80-123">INPUTS</span></span>

### <span data-ttu-id="7da80-124">Keine</span><span class="sxs-lookup"><span data-stu-id="7da80-124">None</span></span>

## <span data-ttu-id="7da80-125">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7da80-125">OUTPUTS</span></span>

### <span data-ttu-id="7da80-126">System.Object</span><span class="sxs-lookup"><span data-stu-id="7da80-126">System.Object</span></span>

## <span data-ttu-id="7da80-127">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7da80-127">NOTES</span></span>

## <span data-ttu-id="7da80-128">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7da80-128">RELATED LINKS</span></span>

[<span data-ttu-id="7da80-129">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="7da80-129">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="7da80-130">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="7da80-130">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="7da80-131">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="7da80-131">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)
