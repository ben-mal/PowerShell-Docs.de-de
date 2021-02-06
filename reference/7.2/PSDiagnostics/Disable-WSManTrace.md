---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 647a7676eddf2175bf29e02b3482cc9c7c4d8ebe
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602302"
---
# <span data-ttu-id="ff615-102">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="ff615-102">Disable-WSManTrace</span></span>

## <span data-ttu-id="ff615-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ff615-103">SYNOPSIS</span></span>
<span data-ttu-id="ff615-104">Stoppt die von enable-wsmantrace gestartete WSMAN-Protokollierungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ff615-104">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="ff615-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ff615-105">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="ff615-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ff615-106">DESCRIPTION</span></span>
<span data-ttu-id="ff615-107">Mit diesem Cmdlet wird die WSMAN-Protokollierungs Sitzung beendet, die von enable-wsmantrace gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="ff615-107">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="ff615-108">Dieses Cmdlet verwendet das- `Stop-Trace` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ff615-108">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="ff615-109">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="ff615-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="ff615-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ff615-110">EXAMPLES</span></span>

### <span data-ttu-id="ff615-111">Beispiel 1: Abbrechen einer WSMAN-Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="ff615-111">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="ff615-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ff615-112">PARAMETERS</span></span>

### <span data-ttu-id="ff615-113">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ff615-113">CommonParameters</span></span>

<span data-ttu-id="ff615-114">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ff615-114">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ff615-115">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ff615-115">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ff615-116">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ff615-116">INPUTS</span></span>

### <span data-ttu-id="ff615-117">Keine</span><span class="sxs-lookup"><span data-stu-id="ff615-117">None</span></span>

## <span data-ttu-id="ff615-118">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ff615-118">OUTPUTS</span></span>

### <span data-ttu-id="ff615-119">Keine</span><span class="sxs-lookup"><span data-stu-id="ff615-119">None</span></span>

## <span data-ttu-id="ff615-120">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ff615-120">NOTES</span></span>

## <span data-ttu-id="ff615-121">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ff615-121">RELATED LINKS</span></span>

[<span data-ttu-id="ff615-122">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="ff615-122">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="ff615-123">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="ff615-123">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="ff615-124">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="ff615-124">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

