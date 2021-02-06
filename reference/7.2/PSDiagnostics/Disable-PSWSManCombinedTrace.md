---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: 690a8b050fd0e16033a585df210db340f41a83a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596133"
---
# <span data-ttu-id="4844b-102">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="4844b-102">Disable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="4844b-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4844b-103">SYNOPSIS</span></span>
<span data-ttu-id="4844b-104">Hält die Protokollierungs Sitzung an, die von enable-pslismancombinedtrace gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="4844b-104">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

## <span data-ttu-id="4844b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4844b-105">SYNTAX</span></span>

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## <span data-ttu-id="4844b-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4844b-106">DESCRIPTION</span></span>

<span data-ttu-id="4844b-107">Dieses Cmdlet hält die Protokollierungs Sitzung an, die von gestartet wurde `Enable-PSWSManCombinedTrace` .</span><span class="sxs-lookup"><span data-stu-id="4844b-107">This cmdlet stops the logging session started by `Enable-PSWSManCombinedTrace`.</span></span>

<span data-ttu-id="4844b-108">Dieses Cmdlet verwendet das- `Stop-Trace` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4844b-108">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="4844b-109">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="4844b-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="4844b-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4844b-110">EXAMPLES</span></span>

### <span data-ttu-id="4844b-111">Beispiel 1: Deaktivieren der kombinierten Protokollierungs Sitzung</span><span class="sxs-lookup"><span data-stu-id="4844b-111">Example 1: Disable the combined logging session</span></span>

```powershell
Disable-PSWSManCombinedTrace
```

## <span data-ttu-id="4844b-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4844b-112">PARAMETERS</span></span>

### <span data-ttu-id="4844b-113">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4844b-113">CommonParameters</span></span>

<span data-ttu-id="4844b-114">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4844b-114">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4844b-115">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4844b-115">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4844b-116">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4844b-116">INPUTS</span></span>

### <span data-ttu-id="4844b-117">Keine</span><span class="sxs-lookup"><span data-stu-id="4844b-117">None</span></span>

## <span data-ttu-id="4844b-118">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4844b-118">OUTPUTS</span></span>

### <span data-ttu-id="4844b-119">Keine</span><span class="sxs-lookup"><span data-stu-id="4844b-119">None</span></span>

## <span data-ttu-id="4844b-120">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4844b-120">NOTES</span></span>

## <span data-ttu-id="4844b-121">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4844b-121">RELATED LINKS</span></span>

[<span data-ttu-id="4844b-122">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="4844b-122">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="4844b-123">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="4844b-123">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="4844b-124">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="4844b-124">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

