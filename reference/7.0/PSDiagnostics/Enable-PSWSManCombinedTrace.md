---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: f6b14ea6cda7d83792f7b51b854471a2cb62bfb5
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209676"
---
# <span data-ttu-id="dbdcb-103">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="dbdcb-103">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="dbdcb-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="dbdcb-104">SYNOPSIS</span></span>
<span data-ttu-id="dbdcb-105">Starten Sie eine Protokollierungs Sitzung mit aktiviertem WSMAN und PowerShell-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="dbdcb-105">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="dbdcb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dbdcb-106">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="dbdcb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dbdcb-107">DESCRIPTION</span></span>

<span data-ttu-id="dbdcb-108">Dieses Cmdlet startet eine Protokollierungs Sitzung mit den folgenden aktivierten PowerShell-Anbietern:</span><span class="sxs-lookup"><span data-stu-id="dbdcb-108">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="dbdcb-109">Microsoft-Windows-PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbdcb-109">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="dbdcb-110">Microsoft-Windows-WinRM</span><span class="sxs-lookup"><span data-stu-id="dbdcb-110">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="dbdcb-111">Die Sitzung hat den Namen "pstrace".</span><span class="sxs-lookup"><span data-stu-id="dbdcb-111">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="dbdcb-112">Dieses Cmdlet verwendet das- `Start-Trace` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dbdcb-112">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="dbdcb-113">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="dbdcb-113">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="dbdcb-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="dbdcb-114">EXAMPLES</span></span>

### <span data-ttu-id="dbdcb-115">Beispiel 1: Starten einer kombinierten Protokollierungs Sitzung</span><span class="sxs-lookup"><span data-stu-id="dbdcb-115">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="dbdcb-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dbdcb-116">PARAMETERS</span></span>

### <span data-ttu-id="dbdcb-117">-Donoteverschreiteexistingtrace</span><span class="sxs-lookup"><span data-stu-id="dbdcb-117">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="dbdcb-118">Standardmäßig werden die Ereignisse in "$PSHome \traces\pstrace.ETL" geschrieben.</span><span class="sxs-lookup"><span data-stu-id="dbdcb-118">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="dbdcb-119">Wenn dieser Parameter verwendet wird, erstellt das Cmdlet einen eindeutigen Dateinamen: "$PSHome \traces\ PSTrace_ {GUID}. ETL"</span><span class="sxs-lookup"><span data-stu-id="dbdcb-119">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

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

### <span data-ttu-id="dbdcb-120">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dbdcb-120">CommonParameters</span></span>

<span data-ttu-id="dbdcb-121">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dbdcb-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dbdcb-122">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dbdcb-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dbdcb-123">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="dbdcb-123">INPUTS</span></span>

### <span data-ttu-id="dbdcb-124">Keine</span><span class="sxs-lookup"><span data-stu-id="dbdcb-124">None</span></span>

## <span data-ttu-id="dbdcb-125">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="dbdcb-125">OUTPUTS</span></span>

### <span data-ttu-id="dbdcb-126">Keine</span><span class="sxs-lookup"><span data-stu-id="dbdcb-126">None</span></span>

## <span data-ttu-id="dbdcb-127">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="dbdcb-127">NOTES</span></span>

## <span data-ttu-id="dbdcb-128">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="dbdcb-128">RELATED LINKS</span></span>

[<span data-ttu-id="dbdcb-129">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="dbdcb-129">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="dbdcb-130">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="dbdcb-130">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="dbdcb-131">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="dbdcb-131">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)
