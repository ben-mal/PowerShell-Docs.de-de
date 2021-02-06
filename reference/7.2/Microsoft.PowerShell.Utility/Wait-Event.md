---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Event
ms.openlocfilehash: caf2a1c80848d3140e7ad46fdf54dbe71886c633
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595948"
---
# <span data-ttu-id="f4f8f-102">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="f4f8f-102">Wait-Event</span></span>

## <span data-ttu-id="f4f8f-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f4f8f-103">SYNOPSIS</span></span>
<span data-ttu-id="f4f8f-104">Wartet, bis ein bestimmtes Ereignis ausgelöst wird, bevor die Ausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-104">Waits until a particular event is raised before continuing to run.</span></span>

## <span data-ttu-id="f4f8f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f4f8f-105">SYNTAX</span></span>

```
Wait-Event [[-SourceIdentifier] <String>] [-Timeout <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="f4f8f-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f4f8f-106">DESCRIPTION</span></span>

<span data-ttu-id="f4f8f-107">Das `Wait-Event` Cmdlet hält die Ausführung eines Skripts oder einer Funktion an, bis ein bestimmtes Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-107">The `Wait-Event` cmdlet suspends execution of a script or function until a particular event is raised.</span></span> <span data-ttu-id="f4f8f-108">Die Ausführung wird fortgesetzt, wenn das Ereignis erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-108">Execution resumes when the event is detected.</span></span> <span data-ttu-id="f4f8f-109">Drücken Sie <kbd>STRG</kbd>C, um den warte Vorgang abzubrechen + <kbd></kbd>.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-109">To cancel the wait, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

<span data-ttu-id="f4f8f-110">Diese Funktion bietet eine Alternative zum Abruf für ein Ereignis.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-110">This feature provides an alternative to polling for an event.</span></span> <span data-ttu-id="f4f8f-111">Außerdem können Sie die Reaktion auf ein Ereignis auf zwei verschiedene Arten bestimmen:</span><span class="sxs-lookup"><span data-stu-id="f4f8f-111">It also allows you to determine the response to an event in two different ways:</span></span>

- <span data-ttu-id="f4f8f-112">Verwenden des **Action** -Parameters des Ereignis Abonnements</span><span class="sxs-lookup"><span data-stu-id="f4f8f-112">using the **Action** parameter of the event subscription</span></span>
- <span data-ttu-id="f4f8f-113">warten auf Rückgabe eines Ereignisses und anschließendes reagieren mit einer Aktion</span><span class="sxs-lookup"><span data-stu-id="f4f8f-113">waiting for an event to return and then respond with an action</span></span>

## <span data-ttu-id="f4f8f-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f4f8f-114">EXAMPLES</span></span>

### <span data-ttu-id="f4f8f-115">Beispiel 1: warten auf das nächste Ereignis</span><span class="sxs-lookup"><span data-stu-id="f4f8f-115">Example 1: Wait for the next event</span></span>

<span data-ttu-id="f4f8f-116">In diesem Beispiel wird auf das nächste Ereignis gewartet, das ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-116">This example waits for the next event that is raised.</span></span>

```powershell
Wait-Event
```

### <span data-ttu-id="f4f8f-117">Beispiel 2: warten auf ein Ereignis mit einem angegebenen Quell Bezeichner</span><span class="sxs-lookup"><span data-stu-id="f4f8f-117">Example 2: Wait for an event with a specified source identifier</span></span>

<span data-ttu-id="f4f8f-118">In diesem Beispiel wird auf das nächste Ereignis gewartet, das ausgelöst wird und das den Quell Bezeichner "processstarted" aufweist.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-118">This example waits for the next event that is raised and that has a source identifier of ProcessStarted.</span></span>

```powershell
Wait-Event -SourceIdentifier "ProcessStarted"
```

### <span data-ttu-id="f4f8f-119">Beispiel 3: warten auf ein abgelaufener Timer-Ereignis</span><span class="sxs-lookup"><span data-stu-id="f4f8f-119">Example 3: Wait for a timer elapsed event</span></span>

<span data-ttu-id="f4f8f-120">In diesem Beispiel wird das- `Wait-Event` Cmdlet verwendet, um auf ein Zeit Geber Ereignis auf einem Timer zu warten, der für 2000 Millisekunden festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-120">This example uses the `Wait-Event` cmdlet to wait for a timer event on a timer that is set for 2000 milliseconds.</span></span>

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

### <span data-ttu-id="f4f8f-121">Beispiel 4: warten auf ein Ereignis nach einem angegebenen Timeout</span><span class="sxs-lookup"><span data-stu-id="f4f8f-121">Example 4: Wait for an event after a specified timeout</span></span>

<span data-ttu-id="f4f8f-122">In diesem Beispiel werden bis zu 90 Sekunden auf das nächste Ereignis gewartet, das ausgelöst wird und das den Quell Bezeichner " **processstarted**" aufweist.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-122">This example waits up to 90 seconds for the next event that is raised and that has a source identifier of **ProcessStarted**.</span></span> <span data-ttu-id="f4f8f-123">Wenn die angegebene Zeit abgelaufen ist, wird der Wartevorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-123">If the specified time expires, the wait ends.</span></span>

```powershell
Wait-Event -SourceIdentifier "ProcessStarted" -Timeout 90
```

## <span data-ttu-id="f4f8f-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f4f8f-124">PARAMETERS</span></span>

### <span data-ttu-id="f4f8f-125">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="f4f8f-125">-SourceIdentifier</span></span>

<span data-ttu-id="f4f8f-126">Gibt den Quell Bezeichner an, den dieses Cmdlet auf Ereignisse wartet.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-126">Specifies the source identifier that this cmdlet waits for events.</span></span>
<span data-ttu-id="f4f8f-127">Standardmäßig `Wait-Event` wartet auf ein beliebiges Ereignis.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-127">By default, `Wait-Event` waits for any event.</span></span>

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

### <span data-ttu-id="f4f8f-128">-Timeout</span><span class="sxs-lookup"><span data-stu-id="f4f8f-128">-Timeout</span></span>

<span data-ttu-id="f4f8f-129">Gibt die maximale Zeit in Sekunden an, die `Wait-Event` auf das Eintreten des Ereignisses wartet.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-129">Specifies the maximum time, in seconds, that `Wait-Event` waits for the event to occur.</span></span> <span data-ttu-id="f4f8f-130">Der Standardwert -1 wartet unbegrenzt.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-130">The default, -1, waits indefinitely.</span></span> <span data-ttu-id="f4f8f-131">Die zeitliche Steuerung beginnt, wenn Sie den Befehl übermitteln `Wait-Event` .</span><span class="sxs-lookup"><span data-stu-id="f4f8f-131">The timing starts when you submit the `Wait-Event` command.</span></span>

<span data-ttu-id="f4f8f-132">Wenn die angegebene Zeit überschritten ist, wird der Wartevorgang beendet und die Befehlseingabeaufforderung wieder angezeigt, auch wenn das Ereignis nicht ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-132">If the specified time is exceeded, the wait ends and the command prompt returns, even if the event has not been raised.</span></span> <span data-ttu-id="f4f8f-133">Es wird keine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-133">No error message is displayed.</span></span>

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

### <span data-ttu-id="f4f8f-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f4f8f-134">CommonParameters</span></span>

<span data-ttu-id="f4f8f-135">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f4f8f-136">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f4f8f-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f4f8f-137">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f4f8f-137">INPUTS</span></span>

### <span data-ttu-id="f4f8f-138">System.String</span><span class="sxs-lookup"><span data-stu-id="f4f8f-138">System.String</span></span>

## <span data-ttu-id="f4f8f-139">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f4f8f-139">OUTPUTS</span></span>

### <span data-ttu-id="f4f8f-140">System. Management. Automation. psiebziger args</span><span class="sxs-lookup"><span data-stu-id="f4f8f-140">System.Management.Automation.PSEventArgs</span></span>

## <span data-ttu-id="f4f8f-141">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f4f8f-141">NOTES</span></span>

<span data-ttu-id="f4f8f-142">Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-142">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="f4f8f-143">Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="f4f8f-143">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="f4f8f-144">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f4f8f-144">RELATED LINKS</span></span>

[<span data-ttu-id="f4f8f-145">Get-Event</span><span class="sxs-lookup"><span data-stu-id="f4f8f-145">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="f4f8f-146">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="f4f8f-146">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="f4f8f-147">New-Event</span><span class="sxs-lookup"><span data-stu-id="f4f8f-147">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="f4f8f-148">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="f4f8f-148">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="f4f8f-149">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="f4f8f-149">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="f4f8f-150">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="f4f8f-150">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="f4f8f-151">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="f4f8f-151">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="f4f8f-152">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="f4f8f-152">Wait-Event</span></span>](Wait-Event.md)

