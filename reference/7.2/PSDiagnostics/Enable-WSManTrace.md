---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: a9d91eab94666186c13f8d5c928d83055f6dbefa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599435"
---
# <span data-ttu-id="74dff-102">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="74dff-102">Enable-WSManTrace</span></span>

## <span data-ttu-id="74dff-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="74dff-103">SYNOPSIS</span></span>
<span data-ttu-id="74dff-104">Starten Sie eine Protokollierungs Sitzung mit aktivierten WSMAN-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="74dff-104">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="74dff-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="74dff-105">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="74dff-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="74dff-106">DESCRIPTION</span></span>
<span data-ttu-id="74dff-107">Mit diesem Cmdlet wird eine Protokollierungs Sitzung mit aktivierten WSMAN-Anbietern gestartet.</span><span class="sxs-lookup"><span data-stu-id="74dff-107">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="74dff-108">Die folgenden Ereignis Anbieter sind aktiviert:</span><span class="sxs-lookup"><span data-stu-id="74dff-108">The following event providers are enabled:</span></span>

- <span data-ttu-id="74dff-109">Ereignis Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="74dff-109">Event Forwarding</span></span>
- <span data-ttu-id="74dff-110">IPMIdrv</span><span class="sxs-lookup"><span data-stu-id="74dff-110">IpmiDrv</span></span>
- <span data-ttu-id="74dff-111">Ipmiprv</span><span class="sxs-lookup"><span data-stu-id="74dff-111">IPMIPrv</span></span>
- <span data-ttu-id="74dff-112">WinRM</span><span class="sxs-lookup"><span data-stu-id="74dff-112">WinRM</span></span>
- <span data-ttu-id="74dff-113">Winrscmd</span><span class="sxs-lookup"><span data-stu-id="74dff-113">WinrsCmd</span></span>
- <span data-ttu-id="74dff-114">Winrsexe</span><span class="sxs-lookup"><span data-stu-id="74dff-114">WinrsExe</span></span>
- <span data-ttu-id="74dff-115">Winrsmgr</span><span class="sxs-lookup"><span data-stu-id="74dff-115">WinrsMgr</span></span>
- <span data-ttu-id="74dff-116">Wsmanprovhost</span><span class="sxs-lookup"><span data-stu-id="74dff-116">WSManProvHost</span></span>

<span data-ttu-id="74dff-117">Die Sitzung hat den Namen "wsmlog".</span><span class="sxs-lookup"><span data-stu-id="74dff-117">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="74dff-118">Dieses Cmdlet verwendet das- `Start-Trace` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="74dff-118">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="74dff-119">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="74dff-119">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="74dff-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="74dff-120">EXAMPLES</span></span>

### <span data-ttu-id="74dff-121">Beispiel 1: Starten einer WSMAN-Protokollierungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="74dff-121">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="74dff-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="74dff-122">PARAMETERS</span></span>

### <span data-ttu-id="74dff-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="74dff-123">CommonParameters</span></span>

<span data-ttu-id="74dff-124">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="74dff-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="74dff-125">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="74dff-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="74dff-126">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="74dff-126">INPUTS</span></span>

### <span data-ttu-id="74dff-127">Keine</span><span class="sxs-lookup"><span data-stu-id="74dff-127">None</span></span>

## <span data-ttu-id="74dff-128">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="74dff-128">OUTPUTS</span></span>

### <span data-ttu-id="74dff-129">Keine</span><span class="sxs-lookup"><span data-stu-id="74dff-129">None</span></span>

## <span data-ttu-id="74dff-130">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="74dff-130">NOTES</span></span>

## <span data-ttu-id="74dff-131">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="74dff-131">RELATED LINKS</span></span>

[<span data-ttu-id="74dff-132">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="74dff-132">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="74dff-133">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="74dff-133">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="74dff-134">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="74dff-134">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

