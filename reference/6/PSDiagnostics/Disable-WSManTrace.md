---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: f7ec371e0d9826dc095fbf71c4785cae2856875b
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200823"
---
# <span data-ttu-id="e6628-103">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="e6628-103">Disable-WSManTrace</span></span>

## <span data-ttu-id="e6628-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e6628-104">SYNOPSIS</span></span>
<span data-ttu-id="e6628-105">Stoppt die von enable-wsmantrace gestartete WSMAN-Protokollierungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e6628-105">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="e6628-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e6628-106">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="e6628-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6628-107">DESCRIPTION</span></span>
<span data-ttu-id="e6628-108">Mit diesem Cmdlet wird die WSMAN-Protokollierungs Sitzung beendet, die von enable-wsmantrace gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="e6628-108">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="e6628-109">Dieses Cmdlet verwendet das- `Stop-Trace` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e6628-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="e6628-110">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="e6628-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="e6628-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e6628-111">EXAMPLES</span></span>

### <span data-ttu-id="e6628-112">Beispiel 1: Abbrechen einer WSMAN-Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="e6628-112">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="e6628-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e6628-113">PARAMETERS</span></span>

### <span data-ttu-id="e6628-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e6628-114">CommonParameters</span></span>

<span data-ttu-id="e6628-115">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e6628-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e6628-116">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e6628-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e6628-117">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e6628-117">INPUTS</span></span>

### <span data-ttu-id="e6628-118">Keine</span><span class="sxs-lookup"><span data-stu-id="e6628-118">None</span></span>

## <span data-ttu-id="e6628-119">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e6628-119">OUTPUTS</span></span>

### <span data-ttu-id="e6628-120">Keine</span><span class="sxs-lookup"><span data-stu-id="e6628-120">None</span></span>

## <span data-ttu-id="e6628-121">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e6628-121">NOTES</span></span>

## <span data-ttu-id="e6628-122">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e6628-122">RELATED LINKS</span></span>

[<span data-ttu-id="e6628-123">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="e6628-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="e6628-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="e6628-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="e6628-125">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="e6628-125">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
