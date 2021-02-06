---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-tracesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TraceSource
ms.openlocfilehash: c196d00359c9b20b5dc1fefc0ab2b94655703f6f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602321"
---
# <span data-ttu-id="244a5-102">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="244a5-102">Get-TraceSource</span></span>

## <span data-ttu-id="244a5-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="244a5-103">SYNOPSIS</span></span>
<span data-ttu-id="244a5-104">Ruft PowerShell-Komponenten ab, die für die Ablauf Verfolgung instrumentiert werden.</span><span class="sxs-lookup"><span data-stu-id="244a5-104">Gets PowerShell components that are instrumented for tracing.</span></span>

## <span data-ttu-id="244a5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="244a5-105">SYNTAX</span></span>

```
Get-TraceSource [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="244a5-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="244a5-106">DESCRIPTION</span></span>

<span data-ttu-id="244a5-107">Das Cmdlet " **Get-TraceSource** " Ruft die Ablauf Verfolgungs Quellen für PowerShell-Komponenten ab, die derzeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="244a5-107">The **Get-TraceSource** cmdlet gets the trace sources for PowerShell components that are currently in use.</span></span>
<span data-ttu-id="244a5-108">Sie können die Daten verwenden, um zu bestimmen, welche PowerShell-Komponenten Sie verfolgen können.</span><span class="sxs-lookup"><span data-stu-id="244a5-108">You can use the data to determine which PowerShell components you can trace.</span></span>
<span data-ttu-id="244a5-109">Bei der Ablaufverfolgung generiert die Komponente detaillierte Meldungen zu den einzelnen Schritten der internen Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="244a5-109">When tracing, the component generates detailed messages about each step in its internal processing.</span></span>
<span data-ttu-id="244a5-110">Entwickler verwenden die Ablaufverfolgungsdaten zur Überwachung des Datenflusses, der Programmausführung und von Fehlern.</span><span class="sxs-lookup"><span data-stu-id="244a5-110">Developers use the trace data to monitor data flow, program execution, and errors.</span></span>

<span data-ttu-id="244a5-111">Die Cmdlets für die Ablauf Verfolgung wurden für PowerShell-Entwickler entwickelt, sind aber für alle Benutzer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="244a5-111">The tracing cmdlets were designed for PowerShell developers, but they are available to all users.</span></span>

## <span data-ttu-id="244a5-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="244a5-112">EXAMPLES</span></span>

### <span data-ttu-id="244a5-113">Beispiel 1: erhalten von Ablauf Verfolgungs Quellen nach Namen</span><span class="sxs-lookup"><span data-stu-id="244a5-113">Example 1: Get trace sources by name</span></span>

```
PS C:\> Get-TraceSource -Name "*provider*"
```

<span data-ttu-id="244a5-114">Mit diesem Befehl werden alle Ablauf Verfolgungs Quellen abgerufen, deren Namen den Anbieter enthalten.</span><span class="sxs-lookup"><span data-stu-id="244a5-114">This command gets all of the trace sources that have names that include provider.</span></span>

### <span data-ttu-id="244a5-115">Beispiel 2: alle Ablauf Verfolgungs Quellen</span><span class="sxs-lookup"><span data-stu-id="244a5-115">Example 2: Get all trace sources</span></span>

```
PS C:\> Get-TraceSource
```

<span data-ttu-id="244a5-116">Dieser Befehl ruft alle PowerShell-Komponenten ab, die verfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="244a5-116">This command gets all of the PowerShell components that can be traced.</span></span>

## <span data-ttu-id="244a5-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="244a5-117">PARAMETERS</span></span>

### <span data-ttu-id="244a5-118">-Name</span><span class="sxs-lookup"><span data-stu-id="244a5-118">-Name</span></span>

<span data-ttu-id="244a5-119">Gibt die abzurufverfolgungs Quellen an.</span><span class="sxs-lookup"><span data-stu-id="244a5-119">Specifies the trace sources to get.</span></span>
<span data-ttu-id="244a5-120">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="244a5-120">Wildcards are permitted.</span></span>
<span data-ttu-id="244a5-121">Der Parameter Name *Name* ist optional.</span><span class="sxs-lookup"><span data-stu-id="244a5-121">The parameter name *Name* is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="244a5-122">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="244a5-122">CommonParameters</span></span>

<span data-ttu-id="244a5-123">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="244a5-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="244a5-124">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="244a5-124">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="244a5-125">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="244a5-125">INPUTS</span></span>

### <span data-ttu-id="244a5-126">System.String</span><span class="sxs-lookup"><span data-stu-id="244a5-126">System.String</span></span>

<span data-ttu-id="244a5-127">Sie können eine Zeichenfolge, die den Namen einer Ablauf Verfolgungs Quelle enthält, über die Pipeline an **Get-TraceSource** übergeben.</span><span class="sxs-lookup"><span data-stu-id="244a5-127">You can pipe a string that contains the name of a trace source to **Get-TraceSource**.</span></span>

## <span data-ttu-id="244a5-128">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="244a5-128">OUTPUTS</span></span>

### <span data-ttu-id="244a5-129">System. Management. Automation. pstracesource</span><span class="sxs-lookup"><span data-stu-id="244a5-129">System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="244a5-130">**Get-TraceSource** gibt Objekte zurück, die die Ablauf Verfolgungs Quellen darstellen.</span><span class="sxs-lookup"><span data-stu-id="244a5-130">**Get-TraceSource** returns objects that represent the trace sources.</span></span>

## <span data-ttu-id="244a5-131">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="244a5-131">NOTES</span></span>

## <span data-ttu-id="244a5-132">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="244a5-132">RELATED LINKS</span></span>

[<span data-ttu-id="244a5-133">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="244a5-133">Set-TraceSource</span></span>](Set-TraceSource.md)

[<span data-ttu-id="244a5-134">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="244a5-134">Trace-Command</span></span>](Trace-Command.md)

