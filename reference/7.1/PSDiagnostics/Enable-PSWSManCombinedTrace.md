---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: 0999c59ab2e27b066dc6afa0b21cce029a9419e1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211700"
---
# <span data-ttu-id="6bacb-103">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="6bacb-103">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="6bacb-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6bacb-104">SYNOPSIS</span></span>
<span data-ttu-id="6bacb-105">Starten Sie eine Protokollierungs Sitzung mit aktiviertem WSMAN und PowerShell-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="6bacb-105">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="6bacb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6bacb-106">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="6bacb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6bacb-107">DESCRIPTION</span></span>

<span data-ttu-id="6bacb-108">Dieses Cmdlet startet eine Protokollierungs Sitzung mit den folgenden aktivierten PowerShell-Anbietern:</span><span class="sxs-lookup"><span data-stu-id="6bacb-108">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="6bacb-109">Microsoft-Windows-PowerShell</span><span class="sxs-lookup"><span data-stu-id="6bacb-109">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="6bacb-110">Microsoft-Windows-WinRM</span><span class="sxs-lookup"><span data-stu-id="6bacb-110">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="6bacb-111">Die Sitzung hat den Namen "pstrace".</span><span class="sxs-lookup"><span data-stu-id="6bacb-111">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="6bacb-112">Dieses Cmdlet verwendet das- `Start-Trace` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6bacb-112">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="6bacb-113">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="6bacb-113">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="6bacb-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6bacb-114">EXAMPLES</span></span>

### <span data-ttu-id="6bacb-115">Beispiel 1: Starten einer kombinierten Protokollierungs Sitzung</span><span class="sxs-lookup"><span data-stu-id="6bacb-115">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="6bacb-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6bacb-116">PARAMETERS</span></span>

### <span data-ttu-id="6bacb-117">-Donoteverschreiteexistingtrace</span><span class="sxs-lookup"><span data-stu-id="6bacb-117">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="6bacb-118">Standardmäßig werden die Ereignisse in "$PSHome \traces\pstrace.ETL" geschrieben.</span><span class="sxs-lookup"><span data-stu-id="6bacb-118">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="6bacb-119">Wenn dieser Parameter verwendet wird, erstellt das Cmdlet einen eindeutigen Dateinamen: "$PSHome \traces\ PSTrace_ {GUID}. ETL"</span><span class="sxs-lookup"><span data-stu-id="6bacb-119">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

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

### <span data-ttu-id="6bacb-120">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6bacb-120">CommonParameters</span></span>

<span data-ttu-id="6bacb-121">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6bacb-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6bacb-122">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6bacb-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6bacb-123">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6bacb-123">INPUTS</span></span>

### <span data-ttu-id="6bacb-124">Keine</span><span class="sxs-lookup"><span data-stu-id="6bacb-124">None</span></span>

## <span data-ttu-id="6bacb-125">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6bacb-125">OUTPUTS</span></span>

### <span data-ttu-id="6bacb-126">Keine</span><span class="sxs-lookup"><span data-stu-id="6bacb-126">None</span></span>

## <span data-ttu-id="6bacb-127">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6bacb-127">NOTES</span></span>

## <span data-ttu-id="6bacb-128">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6bacb-128">RELATED LINKS</span></span>

[<span data-ttu-id="6bacb-129">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="6bacb-129">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="6bacb-130">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="6bacb-130">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="6bacb-131">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="6bacb-131">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

