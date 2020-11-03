---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: c872b57186a854a67908bb07daac7f1a31bbb995
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209278"
---
# <span data-ttu-id="064b9-103">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="064b9-103">Enable-WSManTrace</span></span>

## <span data-ttu-id="064b9-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="064b9-104">SYNOPSIS</span></span>
<span data-ttu-id="064b9-105">Starten Sie eine Protokollierungs Sitzung mit aktivierten WSMAN-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="064b9-105">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="064b9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="064b9-106">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="064b9-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="064b9-107">DESCRIPTION</span></span>
<span data-ttu-id="064b9-108">Mit diesem Cmdlet wird eine Protokollierungs Sitzung mit aktivierten WSMAN-Anbietern gestartet.</span><span class="sxs-lookup"><span data-stu-id="064b9-108">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="064b9-109">Die folgenden Ereignis Anbieter sind aktiviert:</span><span class="sxs-lookup"><span data-stu-id="064b9-109">The following event providers are enabled:</span></span>

- <span data-ttu-id="064b9-110">Ereignis Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="064b9-110">Event Forwarding</span></span>
- <span data-ttu-id="064b9-111">IPMIdrv</span><span class="sxs-lookup"><span data-stu-id="064b9-111">IpmiDrv</span></span>
- <span data-ttu-id="064b9-112">Ipmiprv</span><span class="sxs-lookup"><span data-stu-id="064b9-112">IPMIPrv</span></span>
- <span data-ttu-id="064b9-113">WinRM</span><span class="sxs-lookup"><span data-stu-id="064b9-113">WinRM</span></span>
- <span data-ttu-id="064b9-114">Winrscmd</span><span class="sxs-lookup"><span data-stu-id="064b9-114">WinrsCmd</span></span>
- <span data-ttu-id="064b9-115">Winrsexe</span><span class="sxs-lookup"><span data-stu-id="064b9-115">WinrsExe</span></span>
- <span data-ttu-id="064b9-116">Winrsmgr</span><span class="sxs-lookup"><span data-stu-id="064b9-116">WinrsMgr</span></span>
- <span data-ttu-id="064b9-117">Wsmanprovhost</span><span class="sxs-lookup"><span data-stu-id="064b9-117">WSManProvHost</span></span>

<span data-ttu-id="064b9-118">Die Sitzung hat den Namen "wsmlog".</span><span class="sxs-lookup"><span data-stu-id="064b9-118">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="064b9-119">Dieses Cmdlet verwendet das- `Start-Trace` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="064b9-119">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="064b9-120">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="064b9-120">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="064b9-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="064b9-121">EXAMPLES</span></span>

### <span data-ttu-id="064b9-122">Beispiel 1: Starten einer WSMAN-Protokollierungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="064b9-122">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="064b9-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="064b9-123">PARAMETERS</span></span>

### <span data-ttu-id="064b9-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="064b9-124">CommonParameters</span></span>

<span data-ttu-id="064b9-125">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="064b9-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="064b9-126">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="064b9-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="064b9-127">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="064b9-127">INPUTS</span></span>

### <span data-ttu-id="064b9-128">Keine</span><span class="sxs-lookup"><span data-stu-id="064b9-128">None</span></span>

## <span data-ttu-id="064b9-129">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="064b9-129">OUTPUTS</span></span>

### <span data-ttu-id="064b9-130">Keine</span><span class="sxs-lookup"><span data-stu-id="064b9-130">None</span></span>

## <span data-ttu-id="064b9-131">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="064b9-131">NOTES</span></span>

## <span data-ttu-id="064b9-132">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="064b9-132">RELATED LINKS</span></span>

[<span data-ttu-id="064b9-133">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="064b9-133">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="064b9-134">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="064b9-134">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="064b9-135">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="064b9-135">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)
