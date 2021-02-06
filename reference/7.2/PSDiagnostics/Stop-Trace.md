---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/stop-trace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Trace
ms.openlocfilehash: 5727ae52326830fa16012722d0b801b7d43e50dd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598391"
---
# <span data-ttu-id="a5fee-102">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="a5fee-102">Stop-Trace</span></span>

## <span data-ttu-id="a5fee-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a5fee-103">SYNOPSIS</span></span>
<span data-ttu-id="a5fee-104">Beenden Sie eine Sitzung zur Protokollierung der Ereignis Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="a5fee-104">Stop an Event Trace logging session.</span></span>

## <span data-ttu-id="a5fee-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a5fee-105">SYNTAX</span></span>

```
Stop-Trace [-SessionName] <Object> [-ETS] [<CommonParameters>]
```

## <span data-ttu-id="a5fee-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a5fee-106">DESCRIPTION</span></span>

<span data-ttu-id="a5fee-107">Dieses Cmdlet beendet eine Windows-Ereignis Ablauf Verfolgungs Protokollierungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a5fee-107">This cmdlet stops a Windows Event Trace logging session.</span></span>

<span data-ttu-id="a5fee-108">Dieses Cmdlet wird von den folgenden Cmdlets verwendet:</span><span class="sxs-lookup"><span data-stu-id="a5fee-108">This cmdlet is used by the following cmdlets:</span></span>

- `Disable-PSWSManCombinedTrace`
- `Disable-WSManTrace`

<span data-ttu-id="a5fee-109">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="a5fee-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="a5fee-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a5fee-110">EXAMPLES</span></span>

### <span data-ttu-id="a5fee-111">Beispiel 1: Abbrechen einer WSMAN-Ablauf Verfolgungs Protokollierungs Sitzung</span><span class="sxs-lookup"><span data-stu-id="a5fee-111">Example 1: Stop a WSMan Trace logging session</span></span>

```powershell
Stop-Trace -SessionName 'wsmlog'
```

## <span data-ttu-id="a5fee-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a5fee-112">PARAMETERS</span></span>

### <span data-ttu-id="a5fee-113">-ETS</span><span class="sxs-lookup"><span data-stu-id="a5fee-113">-ETS</span></span>
<span data-ttu-id="a5fee-114">Direktes Senden von Befehlen an Ereignis Ablauf Verfolgungs Sitzungen, ohne zu speichern oder zu planen.</span><span class="sxs-lookup"><span data-stu-id="a5fee-114">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a5fee-115">-Sessionname</span><span class="sxs-lookup"><span data-stu-id="a5fee-115">-SessionName</span></span>
<span data-ttu-id="a5fee-116">Der Name der Ereignis Ablauf Verfolgungs Sitzung, die beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a5fee-116">The name of the Event Trace session to be stopped.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a5fee-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a5fee-117">CommonParameters</span></span>
<span data-ttu-id="a5fee-118">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a5fee-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a5fee-119">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a5fee-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a5fee-120">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a5fee-120">INPUTS</span></span>

### <span data-ttu-id="a5fee-121">Keine</span><span class="sxs-lookup"><span data-stu-id="a5fee-121">None</span></span>

## <span data-ttu-id="a5fee-122">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a5fee-122">OUTPUTS</span></span>

### <span data-ttu-id="a5fee-123">Keine</span><span class="sxs-lookup"><span data-stu-id="a5fee-123">None</span></span>

## <span data-ttu-id="a5fee-124">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a5fee-124">NOTES</span></span>

## <span data-ttu-id="a5fee-125">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a5fee-125">RELATED LINKS</span></span>

[<span data-ttu-id="a5fee-126">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="a5fee-126">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="a5fee-127">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="a5fee-127">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="a5fee-128">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="a5fee-128">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="a5fee-129">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="a5fee-129">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="a5fee-130">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="a5fee-130">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="a5fee-131">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="a5fee-131">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

