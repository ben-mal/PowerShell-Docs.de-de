---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: 9373cb1c5080b95317925937ccf04baa3d335bea
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344149"
---
# <span data-ttu-id="5be62-103">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="5be62-103">Unregister-Event</span></span>

## <span data-ttu-id="5be62-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5be62-104">SYNOPSIS</span></span>
<span data-ttu-id="5be62-105">Storniert ein Ereignisabonnement.</span><span class="sxs-lookup"><span data-stu-id="5be62-105">Cancels an event subscription.</span></span>

## <span data-ttu-id="5be62-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5be62-106">SYNTAX</span></span>

### <span data-ttu-id="5be62-107">Bysource (Standard)</span><span class="sxs-lookup"><span data-stu-id="5be62-107">BySource (Default)</span></span>

```
Unregister-Event [-SourceIdentifier] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5be62-108">ById</span><span class="sxs-lookup"><span data-stu-id="5be62-108">ById</span></span>

```
Unregister-Event [-SubscriptionId] <Int32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5be62-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5be62-109">DESCRIPTION</span></span>

<span data-ttu-id="5be62-110">Mit dem- `Unregister-Event` Cmdlet wird ein Ereignis Abonnement abgebrochen, das mit `Register-EngineEvent` dem `Register-ObjectEvent` Cmdlet, oder erstellt wurde `Register-WmiEvent` .</span><span class="sxs-lookup"><span data-stu-id="5be62-110">The `Unregister-Event` cmdlet cancels an event subscription that was created by using the `Register-EngineEvent`, `Register-ObjectEvent`, or `Register-WmiEvent` cmdlet.</span></span>

<span data-ttu-id="5be62-111">Wenn ein Ereignisabonnement gekündigt wird, wird der Ereignisabonnent aus der Sitzung gelöscht und die abonnierten Ereignisse werden nicht mehr der Ereigniswarteschlange hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5be62-111">When an event subscription is canceled, the event subscriber is deleted from the session and the subscribed events are no longer added to the event queue.</span></span> <span data-ttu-id="5be62-112">Wenn Sie ein Abonnement für ein Ereignis abbrechen, das mit dem `New-Event` Cmdlet erstellt wurde, wird das neue Ereignis auch aus der Sitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="5be62-112">When you cancel a subscription to an event created by using the `New-Event` cmdlet, the new event is also deleted from the session.</span></span>

<span data-ttu-id="5be62-113">`Unregister-Event` löscht keine Ereignisse aus der Ereignis Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="5be62-113">`Unregister-Event` does not delete events from the event queue.</span></span> <span data-ttu-id="5be62-114">Verwenden Sie das-Cmdlet, um Ereignisse zu löschen `Remove-Event` .</span><span class="sxs-lookup"><span data-stu-id="5be62-114">To delete events, use the `Remove-Event` cmdlet.</span></span>

## <span data-ttu-id="5be62-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5be62-115">EXAMPLES</span></span>

### <span data-ttu-id="5be62-116">Beispiel 1: Abbrechen eines Ereignis Abonnements nach Quell Bezeichner</span><span class="sxs-lookup"><span data-stu-id="5be62-116">Example 1: Cancel an event subscription by source identifier</span></span>

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="5be62-117">Mit diesem Befehl wird das Ereignis Abonnement abgebrochen, das den Quell Bezeichner "processstarted" aufweist.</span><span class="sxs-lookup"><span data-stu-id="5be62-117">This command cancels the event subscription that has a source identifier of ProcessStarted.</span></span>

<span data-ttu-id="5be62-118">Verwenden Sie das-Cmdlet, um den Quell Bezeichner eines Ereignisses zu finden `Get-Event` .</span><span class="sxs-lookup"><span data-stu-id="5be62-118">To find the source identifier of an event, use the `Get-Event` cmdlet.</span></span> <span data-ttu-id="5be62-119">Verwenden Sie das-Cmdlet, um den Quell Bezeichner eines Ereignis Abonnements zu ermitteln `Get-EventSubscriber` .</span><span class="sxs-lookup"><span data-stu-id="5be62-119">To find the source identifier of an event subscription, use the `Get-EventSubscriber` cmdlet.</span></span>

### <span data-ttu-id="5be62-120">Beispiel 2: Abbrechen eines Ereignis Abonnements nach Abonnement Bezeichner</span><span class="sxs-lookup"><span data-stu-id="5be62-120">Example 2: Cancel an event subscription by subscription identifier</span></span>

```
PS C:\> Unregister-Event -SubscriptionId 2
```

<span data-ttu-id="5be62-121">Mit diesem Befehl wird das Ereignisabonnement gekündigt, das den Abonnementbezeichner „2“ aufweist.</span><span class="sxs-lookup"><span data-stu-id="5be62-121">This command cancels the event subscription that has a subscription identifier of 2.</span></span>

<span data-ttu-id="5be62-122">Verwenden Sie das-Cmdlet, um den Abonnement Bezeichner eines Ereignis Abonnements zu ermitteln `Get-EventSubscriber` .</span><span class="sxs-lookup"><span data-stu-id="5be62-122">To find the subscription identifier of an event subscription, use the `Get-EventSubscriber` cmdlet.</span></span>

### <span data-ttu-id="5be62-123">Beispiel 3: Abbrechen aller Ereignis Abonnements</span><span class="sxs-lookup"><span data-stu-id="5be62-123">Example 3: Cancel all event subscriptions</span></span>

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

<span data-ttu-id="5be62-124">Mit diesem Befehl werden alle Ereignisabonnements in der Sitzung gekündigt.</span><span class="sxs-lookup"><span data-stu-id="5be62-124">This command cancels all event subscriptions in the session.</span></span>

<span data-ttu-id="5be62-125">Der Befehl verwendet das `Get-EventSubscriber` Cmdlet, um alle Ereignis Abonnenten Objekte in der Sitzung zu erhalten, einschließlich der Abonnenten, die mit dem **supportevent** -Parameter der Cmdlets für die Ereignis Registrierung ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="5be62-125">The command uses the `Get-EventSubscriber` cmdlet to get all event subscriber objects in the session, including the subscribers that are hidden by using the **SupportEvent** parameter of the event registration cmdlets.</span></span>

<span data-ttu-id="5be62-126">Er verwendet einen Pipeline Operator ( `|` ), um die Abonnenten Objekte an zu senden `Unregister-Event` , wodurch Sie aus der Sitzung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="5be62-126">It uses a pipeline operator (`|`) to send the subscriber objects to `Unregister-Event`, which deletes them from the session.</span></span> <span data-ttu-id="5be62-127">Um die Aufgabe abzuschließen, ist der **Force** -Parameter auch für erforderlich `Unregister-Event` .</span><span class="sxs-lookup"><span data-stu-id="5be62-127">To complete the task, the **Force** parameter is also required on `Unregister-Event`.</span></span>

## <span data-ttu-id="5be62-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5be62-128">PARAMETERS</span></span>

### <span data-ttu-id="5be62-129">-Force</span><span class="sxs-lookup"><span data-stu-id="5be62-129">-Force</span></span>

<span data-ttu-id="5be62-130">Bricht alle Ereignis Abonnements ab, einschließlich Abonnements, die mit dem **supportevent** -Parameter von `Register-ObjectEvent` , `Register-WmiEvent` und ausgeblendet wurden `Register-EngineEvent` .</span><span class="sxs-lookup"><span data-stu-id="5be62-130">Cancels all event subscriptions, including subscriptions that were hidden by using the **SupportEvent** parameter of `Register-ObjectEvent`, `Register-WmiEvent`, and `Register-EngineEvent`.</span></span>

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

### <span data-ttu-id="5be62-131">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="5be62-131">-SourceIdentifier</span></span>

<span data-ttu-id="5be62-132">Gibt einen Quell Bezeichner an, mit dem dieses Cmdlet Ereignis Abonnements abbricht.</span><span class="sxs-lookup"><span data-stu-id="5be62-132">Specifies a source identifier that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="5be62-133">Ein **SourceIdentifier** -oder **Abonnement-ID** -Parameter muss in jedem Befehl enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="5be62-133">A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command.</span></span>

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5be62-134">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="5be62-134">-SubscriptionId</span></span>

<span data-ttu-id="5be62-135">Gibt eine quellbezeichnerkennung an, mit der dieses Cmdlet Ereignis Abonnements abbricht.</span><span class="sxs-lookup"><span data-stu-id="5be62-135">Specifies a source identifier ID that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="5be62-136">Ein **SourceIdentifier** -oder **Abonnement-ID** -Parameter muss in jedem Befehl enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="5be62-136">A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5be62-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5be62-137">-Confirm</span></span>

<span data-ttu-id="5be62-138">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="5be62-138">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5be62-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5be62-139">-WhatIf</span></span>

<span data-ttu-id="5be62-140">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5be62-140">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="5be62-141">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5be62-141">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5be62-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5be62-142">CommonParameters</span></span>

<span data-ttu-id="5be62-143">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5be62-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5be62-144">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5be62-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5be62-145">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5be62-145">INPUTS</span></span>

### <span data-ttu-id="5be62-146">System. Management. Automation. psiebziger Subscriber</span><span class="sxs-lookup"><span data-stu-id="5be62-146">System.Management.Automation.PSEventSubscriber</span></span>

<span data-ttu-id="5be62-147">Sie können die Ausgabe von an die Pipeline `Get-EventSubscriber` übergeben `Unregister-Event` .</span><span class="sxs-lookup"><span data-stu-id="5be62-147">You can pipe the output from `Get-EventSubscriber` to `Unregister-Event`.</span></span>

## <span data-ttu-id="5be62-148">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5be62-148">OUTPUTS</span></span>

### <span data-ttu-id="5be62-149">Keine</span><span class="sxs-lookup"><span data-stu-id="5be62-149">None</span></span>

<span data-ttu-id="5be62-150">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="5be62-150">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="5be62-151">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5be62-151">NOTES</span></span>

<span data-ttu-id="5be62-152">Auf den Linux-oder macOS-Plattformen sind keine Ereignis Quellen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5be62-152">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="5be62-153">Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5be62-153">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="5be62-154">Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="5be62-154">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

<span data-ttu-id="5be62-155">`Unregister-Event` Ereignisse, die mit dem Cmdlet erstellt wurden, können nicht gelöscht werden `New-Event` , es sei denn, Sie haben das Ereignis mithilfe des `Register-EngineEvent` Cmdlets abonniert.</span><span class="sxs-lookup"><span data-stu-id="5be62-155">`Unregister-Event` cannot delete events created by using the `New-Event` cmdlet unless you have subscribed to the event by using the `Register-EngineEvent` cmdlet.</span></span> <span data-ttu-id="5be62-156">Um ein benutzerdefiniertes Ereignis aus der Sitzung zu löschen, müssen Sie es programmgesteuert entfernen oder die Sitzung schließen.</span><span class="sxs-lookup"><span data-stu-id="5be62-156">To delete a custom event from the session, you must remove it programmatically or close the session.</span></span>

## <span data-ttu-id="5be62-157">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5be62-157">RELATED LINKS</span></span>

[<span data-ttu-id="5be62-158">Get-Event</span><span class="sxs-lookup"><span data-stu-id="5be62-158">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="5be62-159">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="5be62-159">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="5be62-160">New-Event</span><span class="sxs-lookup"><span data-stu-id="5be62-160">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="5be62-161">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="5be62-161">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="5be62-162">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="5be62-162">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="5be62-163">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="5be62-163">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="5be62-164">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="5be62-164">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="5be62-165">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="5be62-165">Wait-Event</span></span>](Wait-Event.md)
