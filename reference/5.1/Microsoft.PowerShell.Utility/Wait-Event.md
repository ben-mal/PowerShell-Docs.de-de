---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-event?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Event
ms.openlocfilehash: 55fa54521a6c2e9d37b333a27af4572c6a34913a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213615"
---
# <span data-ttu-id="0f1f2-103">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="0f1f2-103">Wait-Event</span></span>

## <span data-ttu-id="0f1f2-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0f1f2-104">SYNOPSIS</span></span>
<span data-ttu-id="0f1f2-105">Wartet, bis ein bestimmtes Ereignis ausgelöst wird, bevor die Ausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-105">Waits until a particular event is raised before continuing to run.</span></span>

## <span data-ttu-id="0f1f2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0f1f2-106">SYNTAX</span></span>

```
Wait-Event [[-SourceIdentifier] <String>] [-Timeout <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="0f1f2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0f1f2-107">DESCRIPTION</span></span>

<span data-ttu-id="0f1f2-108">Das `Wait-Event` Cmdlet hält die Ausführung eines Skripts oder einer Funktion an, bis ein bestimmtes Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-108">The `Wait-Event` cmdlet suspends execution of a script or function until a particular event is raised.</span></span> <span data-ttu-id="0f1f2-109">Die Ausführung wird fortgesetzt, wenn das Ereignis erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-109">Execution resumes when the event is detected.</span></span> <span data-ttu-id="0f1f2-110">Drücken Sie <kbd>STRG</kbd>C, um den warte Vorgang abzubrechen + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-110">To cancel the wait, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

<span data-ttu-id="0f1f2-111">Diese Funktion bietet eine Alternative zum Abruf für ein Ereignis.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-111">This feature provides an alternative to polling for an event.</span></span> <span data-ttu-id="0f1f2-112">Außerdem können Sie die Reaktion auf ein Ereignis auf zwei verschiedene Arten bestimmen:</span><span class="sxs-lookup"><span data-stu-id="0f1f2-112">It also allows you to determine the response to an event in two different ways:</span></span>

- <span data-ttu-id="0f1f2-113">Verwenden des **Action** -Parameters des Ereignis Abonnements</span><span class="sxs-lookup"><span data-stu-id="0f1f2-113">using the **Action** parameter of the event subscription</span></span>
- <span data-ttu-id="0f1f2-114">warten auf Rückgabe eines Ereignisses und anschließendes reagieren mit einer Aktion</span><span class="sxs-lookup"><span data-stu-id="0f1f2-114">waiting for an event to return and then respond with an action</span></span>

## <span data-ttu-id="0f1f2-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0f1f2-115">EXAMPLES</span></span>

### <span data-ttu-id="0f1f2-116">Beispiel 1: warten auf das nächste Ereignis</span><span class="sxs-lookup"><span data-stu-id="0f1f2-116">Example 1: Wait for the next event</span></span>

<span data-ttu-id="0f1f2-117">In diesem Beispiel wird auf das nächste Ereignis gewartet, das ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-117">This example waits for the next event that is raised.</span></span>

```powershell
Wait-Event
```

### <span data-ttu-id="0f1f2-118">Beispiel 2: warten auf ein Ereignis mit einem angegebenen Quell Bezeichner</span><span class="sxs-lookup"><span data-stu-id="0f1f2-118">Example 2: Wait for an event with a specified source identifier</span></span>

<span data-ttu-id="0f1f2-119">In diesem Beispiel wird auf das nächste Ereignis gewartet, das ausgelöst wird und das den Quell Bezeichner "processstarted" aufweist.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-119">This example waits for the next event that is raised and that has a source identifier of ProcessStarted.</span></span>

```powershell
Wait-Event -SourceIdentifier "ProcessStarted"
```

### <span data-ttu-id="0f1f2-120">Beispiel 3: warten auf ein abgelaufener Timer-Ereignis</span><span class="sxs-lookup"><span data-stu-id="0f1f2-120">Example 3: Wait for a timer elapsed event</span></span>

<span data-ttu-id="0f1f2-121">In diesem Beispiel wird das- `Wait-Event` Cmdlet verwendet, um auf ein Zeit Geber Ereignis auf einem Timer zu warten, der für 2000 Millisekunden festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-121">This example uses the `Wait-Event` cmdlet to wait for a timer event on a timer that is set for 2000 milliseconds.</span></span>

```powershell
$Timer = New-Object Timers.Timer
$objectEventArgs = @{
    InputObject = $Timer
    EventName = 'Elapsed'
    SourceIdentifier = 'Timer.Elapsed'
}
Register-ObjectEvent @objectEventArgs
$Timer.Interval = 2000
$Timer.Autoreset = $False
$Timer.Enabled = $True
Wait-Event Timer.Elapsed
```

```Output
ComputerName     :
RunspaceId       : bb560b14-ff43-48d4-b801-5adc31bbc6fb
EventIdentifier  : 1
Sender           : System.Timers.Timer
SourceEventArgs  : System.Timers.ElapsedEventArgs
SourceArgs       : {System.Timers.Timer, System.Timers.ElapsedEventArgs}
SourceIdentifier : Timer.Elapsed
TimeGenerated    : 4/23/2020 2:30:37 PM
MessageData      :
```

### <span data-ttu-id="0f1f2-122">Beispiel 4: warten auf ein Ereignis nach einem angegebenen Timeout</span><span class="sxs-lookup"><span data-stu-id="0f1f2-122">Example 4: Wait for an event after a specified timeout</span></span>

<span data-ttu-id="0f1f2-123">In diesem Beispiel werden bis zu 90 Sekunden auf das nächste Ereignis gewartet, das ausgelöst wird und das den Quell Bezeichner " **processstarted** " aufweist.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-123">This example waits up to 90 seconds for the next event that is raised and that has a source identifier of **ProcessStarted** .</span></span> <span data-ttu-id="0f1f2-124">Wenn die angegebene Zeit abgelaufen ist, wird der Wartevorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-124">If the specified time expires, the wait ends.</span></span>

```powershell
Wait-Event -SourceIdentifier "ProcessStarted" -Timeout 90
```

## <span data-ttu-id="0f1f2-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0f1f2-125">PARAMETERS</span></span>

### <span data-ttu-id="0f1f2-126">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="0f1f2-126">-SourceIdentifier</span></span>

<span data-ttu-id="0f1f2-127">Gibt den Quell Bezeichner an, den dieses Cmdlet auf Ereignisse wartet.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-127">Specifies the source identifier that this cmdlet waits for events.</span></span>
<span data-ttu-id="0f1f2-128">Standardmäßig `Wait-Event` wartet auf ein beliebiges Ereignis.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-128">By default, `Wait-Event` waits for any event.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0f1f2-129">-Timeout</span><span class="sxs-lookup"><span data-stu-id="0f1f2-129">-Timeout</span></span>

<span data-ttu-id="0f1f2-130">Gibt die maximale Zeit in Sekunden an, die `Wait-Event` auf das Eintreten des Ereignisses wartet.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-130">Specifies the maximum time, in seconds, that `Wait-Event` waits for the event to occur.</span></span> <span data-ttu-id="0f1f2-131">Der Standardwert -1 wartet unbegrenzt.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-131">The default, -1, waits indefinitely.</span></span> <span data-ttu-id="0f1f2-132">Die zeitliche Steuerung beginnt, wenn Sie den Befehl übermitteln `Wait-Event` .</span><span class="sxs-lookup"><span data-stu-id="0f1f2-132">The timing starts when you submit the `Wait-Event` command.</span></span>

<span data-ttu-id="0f1f2-133">Wenn die angegebene Zeit überschritten ist, wird der Wartevorgang beendet und die Befehlseingabeaufforderung wieder angezeigt, auch wenn das Ereignis nicht ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-133">If the specified time is exceeded, the wait ends and the command prompt returns, even if the event has not been raised.</span></span> <span data-ttu-id="0f1f2-134">Es wird keine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-134">No error message is displayed.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f1f2-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0f1f2-135">CommonParameters</span></span>

<span data-ttu-id="0f1f2-136">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0f1f2-137">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0f1f2-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0f1f2-138">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0f1f2-138">INPUTS</span></span>

### <span data-ttu-id="0f1f2-139">System.String</span><span class="sxs-lookup"><span data-stu-id="0f1f2-139">System.String</span></span>

## <span data-ttu-id="0f1f2-140">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0f1f2-140">OUTPUTS</span></span>

### <span data-ttu-id="0f1f2-141">System. Management. Automation. psiebziger args</span><span class="sxs-lookup"><span data-stu-id="0f1f2-141">System.Management.Automation.PSEventArgs</span></span>

## <span data-ttu-id="0f1f2-142">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0f1f2-142">NOTES</span></span>

<span data-ttu-id="0f1f2-143">Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-143">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="0f1f2-144">Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="0f1f2-144">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="0f1f2-145">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0f1f2-145">RELATED LINKS</span></span>

[<span data-ttu-id="0f1f2-146">Get-Event</span><span class="sxs-lookup"><span data-stu-id="0f1f2-146">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="0f1f2-147">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="0f1f2-147">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="0f1f2-148">New-Event</span><span class="sxs-lookup"><span data-stu-id="0f1f2-148">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="0f1f2-149">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="0f1f2-149">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="0f1f2-150">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="0f1f2-150">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="0f1f2-151">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="0f1f2-151">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="0f1f2-152">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="0f1f2-152">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="0f1f2-153">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="0f1f2-153">Wait-Event</span></span>](Wait-Event.md)
