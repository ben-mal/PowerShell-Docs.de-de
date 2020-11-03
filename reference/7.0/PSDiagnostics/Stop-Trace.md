---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/stop-trace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Trace
ms.openlocfilehash: 2629ae1beb722282065e76600174b511bfe5fbc9
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211116"
---
# <span data-ttu-id="2b1fe-103">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="2b1fe-103">Stop-Trace</span></span>

## <span data-ttu-id="2b1fe-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2b1fe-104">SYNOPSIS</span></span>
<span data-ttu-id="2b1fe-105">Beenden Sie eine Sitzung zur Protokollierung der Ereignis Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="2b1fe-105">Stop an Event Trace logging session.</span></span>

## <span data-ttu-id="2b1fe-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2b1fe-106">SYNTAX</span></span>

```
Stop-Trace [-SessionName] <Object> [-ETS] [<CommonParameters>]
```

## <span data-ttu-id="2b1fe-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2b1fe-107">DESCRIPTION</span></span>

<span data-ttu-id="2b1fe-108">Dieses Cmdlet beendet eine Windows-Ereignis Ablauf Verfolgungs Protokollierungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2b1fe-108">This cmdlet stops a Windows Event Trace logging session.</span></span>

<span data-ttu-id="2b1fe-109">Dieses Cmdlet wird von den folgenden Cmdlets verwendet:</span><span class="sxs-lookup"><span data-stu-id="2b1fe-109">This cmdlet is used by the following cmdlets:</span></span>

- `Disable-PSWSManCombinedTrace`
- `Disable-WSManTrace`

<span data-ttu-id="2b1fe-110">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="2b1fe-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="2b1fe-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2b1fe-111">EXAMPLES</span></span>

### <span data-ttu-id="2b1fe-112">Beispiel 1: Abbrechen einer WSMAN-Ablauf Verfolgungs Protokollierungs Sitzung</span><span class="sxs-lookup"><span data-stu-id="2b1fe-112">Example 1: Stop a WSMan Trace logging session</span></span>

```powershell
Stop-Trace -SessionName 'wsmlog'
```

## <span data-ttu-id="2b1fe-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2b1fe-113">PARAMETERS</span></span>

### <span data-ttu-id="2b1fe-114">-ETS</span><span class="sxs-lookup"><span data-stu-id="2b1fe-114">-ETS</span></span>
<span data-ttu-id="2b1fe-115">Direktes Senden von Befehlen an Ereignis Ablauf Verfolgungs Sitzungen, ohne zu speichern oder zu planen.</span><span class="sxs-lookup"><span data-stu-id="2b1fe-115">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="2b1fe-116">-Sessionname</span><span class="sxs-lookup"><span data-stu-id="2b1fe-116">-SessionName</span></span>
<span data-ttu-id="2b1fe-117">Der Name der Ereignis Ablauf Verfolgungs Sitzung, die beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2b1fe-117">The name of the Event Trace session to be stopped.</span></span>

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

### <span data-ttu-id="2b1fe-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2b1fe-118">CommonParameters</span></span>
<span data-ttu-id="2b1fe-119">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2b1fe-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2b1fe-120">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2b1fe-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2b1fe-121">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2b1fe-121">INPUTS</span></span>

### <span data-ttu-id="2b1fe-122">Keine</span><span class="sxs-lookup"><span data-stu-id="2b1fe-122">None</span></span>

## <span data-ttu-id="2b1fe-123">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2b1fe-123">OUTPUTS</span></span>

### <span data-ttu-id="2b1fe-124">Keine</span><span class="sxs-lookup"><span data-stu-id="2b1fe-124">None</span></span>

## <span data-ttu-id="2b1fe-125">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2b1fe-125">NOTES</span></span>

## <span data-ttu-id="2b1fe-126">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2b1fe-126">RELATED LINKS</span></span>

[<span data-ttu-id="2b1fe-127">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="2b1fe-127">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="2b1fe-128">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="2b1fe-128">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="2b1fe-129">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="2b1fe-129">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="2b1fe-130">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="2b1fe-130">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="2b1fe-131">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="2b1fe-131">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="2b1fe-132">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="2b1fe-132">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
