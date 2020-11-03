---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: 854769bea9c1b3c104f87d99909f6201a39cac42
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200892"
---
# <span data-ttu-id="b3852-103">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="b3852-103">Disable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="b3852-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b3852-104">SYNOPSIS</span></span>
<span data-ttu-id="b3852-105">Hält die Protokollierungs Sitzung an, die von enable-pslismancombinedtrace gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="b3852-105">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

## <span data-ttu-id="b3852-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b3852-106">SYNTAX</span></span>

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## <span data-ttu-id="b3852-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b3852-107">DESCRIPTION</span></span>

<span data-ttu-id="b3852-108">Dieses Cmdlet hält die Protokollierungs Sitzung an, die von gestartet wurde `Enable-PSWSManCombinedTrace` .</span><span class="sxs-lookup"><span data-stu-id="b3852-108">This cmdlet stops the logging session started by `Enable-PSWSManCombinedTrace`.</span></span>

<span data-ttu-id="b3852-109">Dieses Cmdlet verwendet das- `Stop-Trace` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b3852-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="b3852-110">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="b3852-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="b3852-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b3852-111">EXAMPLES</span></span>

### <span data-ttu-id="b3852-112">Beispiel 1: Deaktivieren der kombinierten Protokollierungs Sitzung</span><span class="sxs-lookup"><span data-stu-id="b3852-112">Example 1: Disable the combined logging session</span></span>

```powershell
Disable-PSWSManCombinedTrace
```

## <span data-ttu-id="b3852-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b3852-113">PARAMETERS</span></span>

### <span data-ttu-id="b3852-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b3852-114">CommonParameters</span></span>

<span data-ttu-id="b3852-115">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b3852-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b3852-116">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b3852-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b3852-117">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b3852-117">INPUTS</span></span>

### <span data-ttu-id="b3852-118">Keine</span><span class="sxs-lookup"><span data-stu-id="b3852-118">None</span></span>

## <span data-ttu-id="b3852-119">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b3852-119">OUTPUTS</span></span>

### <span data-ttu-id="b3852-120">Keine</span><span class="sxs-lookup"><span data-stu-id="b3852-120">None</span></span>

## <span data-ttu-id="b3852-121">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b3852-121">NOTES</span></span>

## <span data-ttu-id="b3852-122">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b3852-122">RELATED LINKS</span></span>

[<span data-ttu-id="b3852-123">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="b3852-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="b3852-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="b3852-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="b3852-125">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="b3852-125">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

