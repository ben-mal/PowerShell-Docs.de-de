---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: 9a0a7f9fa81242fae10325e0c69ffc627088ae71
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200886"
---
# <span data-ttu-id="08d11-103">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="08d11-103">Enable-WSManTrace</span></span>

## <span data-ttu-id="08d11-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="08d11-104">SYNOPSIS</span></span>
<span data-ttu-id="08d11-105">Starten Sie eine Protokollierungs Sitzung mit aktivierten WSMAN-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="08d11-105">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="08d11-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="08d11-106">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="08d11-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08d11-107">DESCRIPTION</span></span>
<span data-ttu-id="08d11-108">Mit diesem Cmdlet wird eine Protokollierungs Sitzung mit aktivierten WSMAN-Anbietern gestartet.</span><span class="sxs-lookup"><span data-stu-id="08d11-108">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="08d11-109">Die folgenden Ereignis Anbieter sind aktiviert:</span><span class="sxs-lookup"><span data-stu-id="08d11-109">The following event providers are enabled:</span></span>

- <span data-ttu-id="08d11-110">Ereignis Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="08d11-110">Event Forwarding</span></span>
- <span data-ttu-id="08d11-111">IPMIdrv</span><span class="sxs-lookup"><span data-stu-id="08d11-111">IpmiDrv</span></span>
- <span data-ttu-id="08d11-112">Ipmiprv</span><span class="sxs-lookup"><span data-stu-id="08d11-112">IPMIPrv</span></span>
- <span data-ttu-id="08d11-113">WinRM</span><span class="sxs-lookup"><span data-stu-id="08d11-113">WinRM</span></span>
- <span data-ttu-id="08d11-114">Winrscmd</span><span class="sxs-lookup"><span data-stu-id="08d11-114">WinrsCmd</span></span>
- <span data-ttu-id="08d11-115">Winrsexe</span><span class="sxs-lookup"><span data-stu-id="08d11-115">WinrsExe</span></span>
- <span data-ttu-id="08d11-116">Winrsmgr</span><span class="sxs-lookup"><span data-stu-id="08d11-116">WinrsMgr</span></span>
- <span data-ttu-id="08d11-117">Wsmanprovhost</span><span class="sxs-lookup"><span data-stu-id="08d11-117">WSManProvHost</span></span>

<span data-ttu-id="08d11-118">Die Sitzung hat den Namen "wsmlog".</span><span class="sxs-lookup"><span data-stu-id="08d11-118">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="08d11-119">Dieses Cmdlet verwendet das- `Start-Trace` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="08d11-119">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="08d11-120">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="08d11-120">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="08d11-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="08d11-121">EXAMPLES</span></span>

### <span data-ttu-id="08d11-122">Beispiel 1: Starten einer WSMAN-Protokollierungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="08d11-122">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="08d11-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="08d11-123">PARAMETERS</span></span>

### <span data-ttu-id="08d11-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="08d11-124">CommonParameters</span></span>

<span data-ttu-id="08d11-125">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="08d11-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="08d11-126">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="08d11-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="08d11-127">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="08d11-127">INPUTS</span></span>

### <span data-ttu-id="08d11-128">Keine</span><span class="sxs-lookup"><span data-stu-id="08d11-128">None</span></span>

## <span data-ttu-id="08d11-129">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="08d11-129">OUTPUTS</span></span>

### <span data-ttu-id="08d11-130">Keine</span><span class="sxs-lookup"><span data-stu-id="08d11-130">None</span></span>

## <span data-ttu-id="08d11-131">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="08d11-131">NOTES</span></span>

## <span data-ttu-id="08d11-132">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="08d11-132">RELATED LINKS</span></span>

[<span data-ttu-id="08d11-133">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="08d11-133">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="08d11-134">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="08d11-134">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="08d11-135">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="08d11-135">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

