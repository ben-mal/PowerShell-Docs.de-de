---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: 70ce4849e78262fc3553502d307e1df4e9ecfcf3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200824"
---
# <span data-ttu-id="d1ec3-103">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="d1ec3-103">Enable-WSManTrace</span></span>

## <span data-ttu-id="d1ec3-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d1ec3-104">SYNOPSIS</span></span>
<span data-ttu-id="d1ec3-105">Starten Sie eine Protokollierungs Sitzung mit aktivierten WSMAN-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="d1ec3-105">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="d1ec3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d1ec3-106">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="d1ec3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d1ec3-107">DESCRIPTION</span></span>
<span data-ttu-id="d1ec3-108">Mit diesem Cmdlet wird eine Protokollierungs Sitzung mit aktivierten WSMAN-Anbietern gestartet.</span><span class="sxs-lookup"><span data-stu-id="d1ec3-108">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="d1ec3-109">Die folgenden Ereignis Anbieter sind aktiviert:</span><span class="sxs-lookup"><span data-stu-id="d1ec3-109">The following event providers are enabled:</span></span>

- <span data-ttu-id="d1ec3-110">Ereignis Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="d1ec3-110">Event Forwarding</span></span>
- <span data-ttu-id="d1ec3-111">IPMIdrv</span><span class="sxs-lookup"><span data-stu-id="d1ec3-111">IpmiDrv</span></span>
- <span data-ttu-id="d1ec3-112">Ipmiprv</span><span class="sxs-lookup"><span data-stu-id="d1ec3-112">IPMIPrv</span></span>
- <span data-ttu-id="d1ec3-113">WinRM</span><span class="sxs-lookup"><span data-stu-id="d1ec3-113">WinRM</span></span>
- <span data-ttu-id="d1ec3-114">Winrscmd</span><span class="sxs-lookup"><span data-stu-id="d1ec3-114">WinrsCmd</span></span>
- <span data-ttu-id="d1ec3-115">Winrsexe</span><span class="sxs-lookup"><span data-stu-id="d1ec3-115">WinrsExe</span></span>
- <span data-ttu-id="d1ec3-116">Winrsmgr</span><span class="sxs-lookup"><span data-stu-id="d1ec3-116">WinrsMgr</span></span>
- <span data-ttu-id="d1ec3-117">Wsmanprovhost</span><span class="sxs-lookup"><span data-stu-id="d1ec3-117">WSManProvHost</span></span>

<span data-ttu-id="d1ec3-118">Die Sitzung hat den Namen "wsmlog".</span><span class="sxs-lookup"><span data-stu-id="d1ec3-118">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="d1ec3-119">Dieses Cmdlet verwendet das- `Start-Trace` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d1ec3-119">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="d1ec3-120">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="d1ec3-120">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="d1ec3-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d1ec3-121">EXAMPLES</span></span>

### <span data-ttu-id="d1ec3-122">Beispiel 1: Starten einer WSMAN-Protokollierungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d1ec3-122">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="d1ec3-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d1ec3-123">PARAMETERS</span></span>

### <span data-ttu-id="d1ec3-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d1ec3-124">CommonParameters</span></span>

<span data-ttu-id="d1ec3-125">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d1ec3-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d1ec3-126">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d1ec3-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d1ec3-127">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d1ec3-127">INPUTS</span></span>

### <span data-ttu-id="d1ec3-128">Keine</span><span class="sxs-lookup"><span data-stu-id="d1ec3-128">None</span></span>

## <span data-ttu-id="d1ec3-129">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d1ec3-129">OUTPUTS</span></span>

### <span data-ttu-id="d1ec3-130">Keine</span><span class="sxs-lookup"><span data-stu-id="d1ec3-130">None</span></span>

## <span data-ttu-id="d1ec3-131">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d1ec3-131">NOTES</span></span>

## <span data-ttu-id="d1ec3-132">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d1ec3-132">RELATED LINKS</span></span>

[<span data-ttu-id="d1ec3-133">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="d1ec3-133">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="d1ec3-134">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="d1ec3-134">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="d1ec3-135">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="d1ec3-135">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)
