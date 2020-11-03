---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: 08c9d61f210761e2ed7a3a5014812b2bd362201b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213535"
---
# <span data-ttu-id="4a8fa-103">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="4a8fa-103">Enable-WSManTrace</span></span>

## <span data-ttu-id="4a8fa-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4a8fa-104">SYNOPSIS</span></span>
<span data-ttu-id="4a8fa-105">Starten Sie eine Protokollierungs Sitzung mit aktivierten WSMAN-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="4a8fa-105">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="4a8fa-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4a8fa-106">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="4a8fa-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4a8fa-107">DESCRIPTION</span></span>
<span data-ttu-id="4a8fa-108">Mit diesem Cmdlet wird eine Protokollierungs Sitzung mit aktivierten WSMAN-Anbietern gestartet.</span><span class="sxs-lookup"><span data-stu-id="4a8fa-108">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="4a8fa-109">Die folgenden Ereignis Anbieter sind aktiviert:</span><span class="sxs-lookup"><span data-stu-id="4a8fa-109">The following event providers are enabled:</span></span>

- <span data-ttu-id="4a8fa-110">Ereignis Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="4a8fa-110">Event Forwarding</span></span>
- <span data-ttu-id="4a8fa-111">IPMIdrv</span><span class="sxs-lookup"><span data-stu-id="4a8fa-111">IpmiDrv</span></span>
- <span data-ttu-id="4a8fa-112">Ipmiprv</span><span class="sxs-lookup"><span data-stu-id="4a8fa-112">IPMIPrv</span></span>
- <span data-ttu-id="4a8fa-113">WinRM</span><span class="sxs-lookup"><span data-stu-id="4a8fa-113">WinRM</span></span>
- <span data-ttu-id="4a8fa-114">Winrscmd</span><span class="sxs-lookup"><span data-stu-id="4a8fa-114">WinrsCmd</span></span>
- <span data-ttu-id="4a8fa-115">Winrsexe</span><span class="sxs-lookup"><span data-stu-id="4a8fa-115">WinrsExe</span></span>
- <span data-ttu-id="4a8fa-116">Winrsmgr</span><span class="sxs-lookup"><span data-stu-id="4a8fa-116">WinrsMgr</span></span>
- <span data-ttu-id="4a8fa-117">Wsmanprovhost</span><span class="sxs-lookup"><span data-stu-id="4a8fa-117">WSManProvHost</span></span>

<span data-ttu-id="4a8fa-118">Die Sitzung hat den Namen "wsmlog".</span><span class="sxs-lookup"><span data-stu-id="4a8fa-118">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="4a8fa-119">Dieses Cmdlet verwendet das- `Start-Trace` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4a8fa-119">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="4a8fa-120">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="4a8fa-120">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="4a8fa-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4a8fa-121">EXAMPLES</span></span>

### <span data-ttu-id="4a8fa-122">Beispiel 1: Starten einer WSMAN-Protokollierungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4a8fa-122">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="4a8fa-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4a8fa-123">PARAMETERS</span></span>

### <span data-ttu-id="4a8fa-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4a8fa-124">CommonParameters</span></span>

<span data-ttu-id="4a8fa-125">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4a8fa-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4a8fa-126">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4a8fa-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4a8fa-127">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4a8fa-127">INPUTS</span></span>

### <span data-ttu-id="4a8fa-128">Keine</span><span class="sxs-lookup"><span data-stu-id="4a8fa-128">None</span></span>

## <span data-ttu-id="4a8fa-129">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4a8fa-129">OUTPUTS</span></span>

### <span data-ttu-id="4a8fa-130">System.Object</span><span class="sxs-lookup"><span data-stu-id="4a8fa-130">System.Object</span></span>

## <span data-ttu-id="4a8fa-131">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4a8fa-131">NOTES</span></span>

## <span data-ttu-id="4a8fa-132">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4a8fa-132">RELATED LINKS</span></span>

[<span data-ttu-id="4a8fa-133">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="4a8fa-133">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="4a8fa-134">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="4a8fa-134">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="4a8fa-135">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="4a8fa-135">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)
