---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-tracesource?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TraceSource
ms.openlocfilehash: d136dd46eaceb65b5c512e3ff5c98e13d685d45e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216636"
---
# <span data-ttu-id="e5383-103">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="e5383-103">Get-TraceSource</span></span>

## <span data-ttu-id="e5383-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e5383-104">SYNOPSIS</span></span>
<span data-ttu-id="e5383-105">Ruft PowerShell-Komponenten ab, die für die Ablauf Verfolgung instrumentiert werden.</span><span class="sxs-lookup"><span data-stu-id="e5383-105">Gets PowerShell components that are instrumented for tracing.</span></span>

## <span data-ttu-id="e5383-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e5383-106">SYNTAX</span></span>

```
Get-TraceSource [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="e5383-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e5383-107">DESCRIPTION</span></span>

<span data-ttu-id="e5383-108">Das Cmdlet " **Get-TraceSource** " Ruft die Ablauf Verfolgungs Quellen für PowerShell-Komponenten ab, die derzeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e5383-108">The **Get-TraceSource** cmdlet gets the trace sources for PowerShell components that are currently in use.</span></span>
<span data-ttu-id="e5383-109">Sie können die Daten verwenden, um zu bestimmen, welche PowerShell-Komponenten Sie verfolgen können.</span><span class="sxs-lookup"><span data-stu-id="e5383-109">You can use the data to determine which PowerShell components you can trace.</span></span>
<span data-ttu-id="e5383-110">Bei der Ablaufverfolgung generiert die Komponente detaillierte Meldungen zu den einzelnen Schritten der internen Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="e5383-110">When tracing, the component generates detailed messages about each step in its internal processing.</span></span>
<span data-ttu-id="e5383-111">Entwickler verwenden die Ablaufverfolgungsdaten zur Überwachung des Datenflusses, der Programmausführung und von Fehlern.</span><span class="sxs-lookup"><span data-stu-id="e5383-111">Developers use the trace data to monitor data flow, program execution, and errors.</span></span>

<span data-ttu-id="e5383-112">Die Cmdlets für die Ablauf Verfolgung wurden für PowerShell-Entwickler entwickelt, sind aber für alle Benutzer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e5383-112">The tracing cmdlets were designed for PowerShell developers, but they are available to all users.</span></span>

## <span data-ttu-id="e5383-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e5383-113">EXAMPLES</span></span>

### <span data-ttu-id="e5383-114">Beispiel 1: erhalten von Ablauf Verfolgungs Quellen nach Namen</span><span class="sxs-lookup"><span data-stu-id="e5383-114">Example 1: Get trace sources by name</span></span>

```
PS C:\> Get-TraceSource -Name "*provider*"
```

<span data-ttu-id="e5383-115">Mit diesem Befehl werden alle Ablauf Verfolgungs Quellen abgerufen, deren Namen den Anbieter enthalten.</span><span class="sxs-lookup"><span data-stu-id="e5383-115">This command gets all of the trace sources that have names that include provider.</span></span>

### <span data-ttu-id="e5383-116">Beispiel 2: alle Ablauf Verfolgungs Quellen</span><span class="sxs-lookup"><span data-stu-id="e5383-116">Example 2: Get all trace sources</span></span>

```
PS C:\> Get-TraceSource
```

<span data-ttu-id="e5383-117">Dieser Befehl ruft alle PowerShell-Komponenten ab, die verfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="e5383-117">This command gets all of the PowerShell components that can be traced.</span></span>

## <span data-ttu-id="e5383-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e5383-118">PARAMETERS</span></span>

### <span data-ttu-id="e5383-119">-Name</span><span class="sxs-lookup"><span data-stu-id="e5383-119">-Name</span></span>

<span data-ttu-id="e5383-120">Gibt die abzurufverfolgungs Quellen an.</span><span class="sxs-lookup"><span data-stu-id="e5383-120">Specifies the trace sources to get.</span></span>
<span data-ttu-id="e5383-121">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="e5383-121">Wildcards are permitted.</span></span>
<span data-ttu-id="e5383-122">Der Parameter Name *Name* ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5383-122">The parameter name *Name* is optional.</span></span>

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

### <span data-ttu-id="e5383-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e5383-123">CommonParameters</span></span>

<span data-ttu-id="e5383-124">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e5383-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e5383-125">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e5383-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e5383-126">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e5383-126">INPUTS</span></span>

### <span data-ttu-id="e5383-127">System.String</span><span class="sxs-lookup"><span data-stu-id="e5383-127">System.String</span></span>

<span data-ttu-id="e5383-128">Sie können eine Zeichenfolge, die den Namen einer Ablauf Verfolgungs Quelle enthält, über die Pipeline an **Get-TraceSource** übergeben.</span><span class="sxs-lookup"><span data-stu-id="e5383-128">You can pipe a string that contains the name of a trace source to **Get-TraceSource** .</span></span>

## <span data-ttu-id="e5383-129">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e5383-129">OUTPUTS</span></span>

### <span data-ttu-id="e5383-130">System. Management. Automation. pstracesource</span><span class="sxs-lookup"><span data-stu-id="e5383-130">System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="e5383-131">**Get-TraceSource** gibt Objekte zurück, die die Ablauf Verfolgungs Quellen darstellen.</span><span class="sxs-lookup"><span data-stu-id="e5383-131">**Get-TraceSource** returns objects that represent the trace sources.</span></span>

## <span data-ttu-id="e5383-132">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e5383-132">NOTES</span></span>

## <span data-ttu-id="e5383-133">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e5383-133">RELATED LINKS</span></span>

[<span data-ttu-id="e5383-134">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="e5383-134">Set-TraceSource</span></span>](Set-TraceSource.md)

[<span data-ttu-id="e5383-135">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="e5383-135">Trace-Command</span></span>](Trace-Command.md)
