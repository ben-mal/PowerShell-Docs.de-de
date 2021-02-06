---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: ef333edaa091e96df11a8288e9b16f133614c1e0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596549"
---
# <span data-ttu-id="c7b1f-102">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="c7b1f-102">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="c7b1f-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c7b1f-103">SYNOPSIS</span></span>
<span data-ttu-id="c7b1f-104">Starten Sie eine Protokollierungs Sitzung mit aktiviertem WSMAN und PowerShell-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="c7b1f-104">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="c7b1f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c7b1f-105">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="c7b1f-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c7b1f-106">DESCRIPTION</span></span>

<span data-ttu-id="c7b1f-107">Dieses Cmdlet startet eine Protokollierungs Sitzung mit den folgenden aktivierten PowerShell-Anbietern:</span><span class="sxs-lookup"><span data-stu-id="c7b1f-107">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="c7b1f-108">Microsoft-Windows-PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7b1f-108">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="c7b1f-109">Microsoft-Windows-WinRM</span><span class="sxs-lookup"><span data-stu-id="c7b1f-109">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="c7b1f-110">Die Sitzung hat den Namen "pstrace".</span><span class="sxs-lookup"><span data-stu-id="c7b1f-110">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="c7b1f-111">Dieses Cmdlet verwendet das- `Start-Trace` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c7b1f-111">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="c7b1f-112">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="c7b1f-112">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="c7b1f-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c7b1f-113">EXAMPLES</span></span>

### <span data-ttu-id="c7b1f-114">Beispiel 1: Starten einer kombinierten Protokollierungs Sitzung</span><span class="sxs-lookup"><span data-stu-id="c7b1f-114">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="c7b1f-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c7b1f-115">PARAMETERS</span></span>

### <span data-ttu-id="c7b1f-116">-Donoteverschreiteexistingtrace</span><span class="sxs-lookup"><span data-stu-id="c7b1f-116">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="c7b1f-117">Standardmäßig werden die Ereignisse in "$PSHome \traces\pstrace.ETL" geschrieben.</span><span class="sxs-lookup"><span data-stu-id="c7b1f-117">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="c7b1f-118">Wenn dieser Parameter verwendet wird, erstellt das Cmdlet einen eindeutigen Dateinamen: "$PSHome \traces\ PSTrace_ {GUID}. ETL"</span><span class="sxs-lookup"><span data-stu-id="c7b1f-118">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

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

### <span data-ttu-id="c7b1f-119">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c7b1f-119">CommonParameters</span></span>

<span data-ttu-id="c7b1f-120">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c7b1f-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c7b1f-121">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c7b1f-121">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c7b1f-122">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c7b1f-122">INPUTS</span></span>

### <span data-ttu-id="c7b1f-123">Keine</span><span class="sxs-lookup"><span data-stu-id="c7b1f-123">None</span></span>

## <span data-ttu-id="c7b1f-124">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c7b1f-124">OUTPUTS</span></span>

### <span data-ttu-id="c7b1f-125">Keine</span><span class="sxs-lookup"><span data-stu-id="c7b1f-125">None</span></span>

## <span data-ttu-id="c7b1f-126">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c7b1f-126">NOTES</span></span>

## <span data-ttu-id="c7b1f-127">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c7b1f-127">RELATED LINKS</span></span>

[<span data-ttu-id="c7b1f-128">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="c7b1f-128">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="c7b1f-129">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="c7b1f-129">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="c7b1f-130">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="c7b1f-130">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

