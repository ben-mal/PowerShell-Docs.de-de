---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 5566fb2e11311990cea76e6802c84985795c3553
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200887"
---
# <span data-ttu-id="6b1bd-103">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="6b1bd-103">Disable-WSManTrace</span></span>

## <span data-ttu-id="6b1bd-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6b1bd-104">SYNOPSIS</span></span>
<span data-ttu-id="6b1bd-105">Stoppt die von enable-wsmantrace gestartete WSMAN-Protokollierungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-105">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="6b1bd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6b1bd-106">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="6b1bd-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6b1bd-107">DESCRIPTION</span></span>
<span data-ttu-id="6b1bd-108">Mit diesem Cmdlet wird die WSMAN-Protokollierungs Sitzung beendet, die von enable-wsmantrace gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-108">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="6b1bd-109">Dieses Cmdlet verwendet das- `Stop-Trace` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="6b1bd-110">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="6b1bd-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6b1bd-111">EXAMPLES</span></span>

### <span data-ttu-id="6b1bd-112">Beispiel 1: Abbrechen einer WSMAN-Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="6b1bd-112">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="6b1bd-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6b1bd-113">PARAMETERS</span></span>

### <span data-ttu-id="6b1bd-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6b1bd-114">CommonParameters</span></span>

<span data-ttu-id="6b1bd-115">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6b1bd-116">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6b1bd-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6b1bd-117">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6b1bd-117">INPUTS</span></span>

### <span data-ttu-id="6b1bd-118">Keine</span><span class="sxs-lookup"><span data-stu-id="6b1bd-118">None</span></span>

## <span data-ttu-id="6b1bd-119">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6b1bd-119">OUTPUTS</span></span>

### <span data-ttu-id="6b1bd-120">Keine</span><span class="sxs-lookup"><span data-stu-id="6b1bd-120">None</span></span>

## <span data-ttu-id="6b1bd-121">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6b1bd-121">NOTES</span></span>

## <span data-ttu-id="6b1bd-122">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6b1bd-122">RELATED LINKS</span></span>

[<span data-ttu-id="6b1bd-123">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="6b1bd-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="6b1bd-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="6b1bd-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="6b1bd-125">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="6b1bd-125">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

