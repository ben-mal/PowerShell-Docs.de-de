---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: 748ef22203f59090be6f5491ea76b50d54930a95
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217564"
---
# <span data-ttu-id="53c30-103">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="53c30-103">Unregister-Event</span></span>

## <span data-ttu-id="53c30-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="53c30-104">SYNOPSIS</span></span>
<span data-ttu-id="53c30-105">Storniert ein Ereignisabonnement.</span><span class="sxs-lookup"><span data-stu-id="53c30-105">Cancels an event subscription.</span></span>

## <span data-ttu-id="53c30-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="53c30-106">SYNTAX</span></span>

### <span data-ttu-id="53c30-107">Bysource (Standard)</span><span class="sxs-lookup"><span data-stu-id="53c30-107">BySource (Default)</span></span>

```
Unregister-Event [-SourceIdentifier] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="53c30-108">ById</span><span class="sxs-lookup"><span data-stu-id="53c30-108">ById</span></span>

```
Unregister-Event [-SubscriptionId] <Int32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="53c30-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="53c30-109">DESCRIPTION</span></span>
<span data-ttu-id="53c30-110">Das **Unregister-Event-** Cmdlet bricht ein Ereignis Abonnement ab, das mit dem Cmdlet Register-engineevent, Register-ObjectEvent oder Register-WmiEvent erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="53c30-110">The **Unregister-Event** cmdlet cancels an event subscription that was created by using the Register-EngineEvent, Register-ObjectEvent, or Register-WmiEvent cmdlet.</span></span>

<span data-ttu-id="53c30-111">Wenn ein Ereignisabonnement gekündigt wird, wird der Ereignisabonnent aus der Sitzung gelöscht und die abonnierten Ereignisse werden nicht mehr der Ereigniswarteschlange hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="53c30-111">When an event subscription is canceled, the event subscriber is deleted from the session and the subscribed events are no longer added to the event queue.</span></span>
<span data-ttu-id="53c30-112">Wenn Sie ein Abonnement für ein Ereignis kündigen, das mithilfe des New-Event-Cmdlets erstellt wurde, wird das neue Ereignis auch aus der Sitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="53c30-112">When you cancel a subscription to an event created by using the New-Event cmdlet, the new event is also deleted from the session.</span></span>

<span data-ttu-id="53c30-113">**Unregister-Event** löscht keine Ereignisse aus der Ereignis Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="53c30-113">**Unregister-Event** does not delete events from the event queue.</span></span>
<span data-ttu-id="53c30-114">Um Ereignisse zu löschen, verwenden Sie das Remove-Event-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="53c30-114">To delete events, use the Remove-Event cmdlet.</span></span>

## <span data-ttu-id="53c30-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="53c30-115">EXAMPLES</span></span>

### <span data-ttu-id="53c30-116">Beispiel 1: Abbrechen eines Ereignis Abonnements nach Quell Bezeichner</span><span class="sxs-lookup"><span data-stu-id="53c30-116">Example 1: Cancel an event subscription by source identifier</span></span>

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="53c30-117">Mit diesem Befehl wird das Ereignis Abonnement abgebrochen, das den Quell Bezeichner "processstarted" aufweist.</span><span class="sxs-lookup"><span data-stu-id="53c30-117">This command cancels the event subscription that has a source identifier of ProcessStarted.</span></span>

<span data-ttu-id="53c30-118">Um den Quellenbezeichner eines Ereignisses zu finden, verwenden Sie das Get-Event-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="53c30-118">To find the source identifier of an event, use the Get-Event cmdlet.</span></span>
<span data-ttu-id="53c30-119">Verwenden Sie das **Get-eventsubscriber** -Cmdlet, um den Quell Bezeichner eines Ereignis Abonnements zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="53c30-119">To find the source identifier of an event subscription, use the **Get-EventSubscriber** cmdlet.</span></span>

### <span data-ttu-id="53c30-120">Beispiel 2: Abbrechen eines Ereignis Abonnements nach Abonnement Bezeichner</span><span class="sxs-lookup"><span data-stu-id="53c30-120">Example 2: Cancel an event subscription by subscription identifier</span></span>

```
PS C:\> Unregister-Event -SubscriptionId 2
```

<span data-ttu-id="53c30-121">Mit diesem Befehl wird das Ereignisabonnement gekündigt, das den Abonnementbezeichner „2“ aufweist.</span><span class="sxs-lookup"><span data-stu-id="53c30-121">This command cancels the event subscription that has a subscription identifier of 2.</span></span>

<span data-ttu-id="53c30-122">Verwenden Sie das **Get-eventsubscriber** -Cmdlet, um den Abonnement Bezeichner eines Ereignis Abonnements zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="53c30-122">To find the subscription identifier of an event subscription, use the **Get-EventSubscriber** cmdlet.</span></span>

### <span data-ttu-id="53c30-123">Beispiel 3: Abbrechen aller Ereignis Abonnements</span><span class="sxs-lookup"><span data-stu-id="53c30-123">Example 3: Cancel all event subscriptions</span></span>

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

<span data-ttu-id="53c30-124">Mit diesem Befehl werden alle Ereignisabonnements in der Sitzung gekündigt.</span><span class="sxs-lookup"><span data-stu-id="53c30-124">This command cancels all event subscriptions in the session.</span></span>

<span data-ttu-id="53c30-125">Der Befehl verwendet das **Get-eventsubscriber** -Cmdlet, um alle Ereignis Abonnenten Objekte in der Sitzung zu erhalten, einschließlich der Abonnenten, die mit dem *supportevent* -Parameter der Cmdlets für die Ereignis Registrierung ausgeblendet sind.</span><span class="sxs-lookup"><span data-stu-id="53c30-125">The command uses the **Get-EventSubscriber** cmdlet to get all event subscriber objects in the session, including the subscribers that are hidden by using the *SupportEvent* parameter of the event registration cmdlets.</span></span>

<span data-ttu-id="53c30-126">Er verwendet einen Pipeline Operator (|), um die Abonnenten Objekte an **Unregister-Event** zu senden, das Sie aus der Sitzung löscht.</span><span class="sxs-lookup"><span data-stu-id="53c30-126">It uses a pipeline operator (|) to send the subscriber objects to **Unregister-Event** , which deletes them from the session.</span></span>
<span data-ttu-id="53c30-127">Um die Aufgabe abzuschließen, ist der *Force* -Parameter auch für **Unregister-Event** erforderlich.</span><span class="sxs-lookup"><span data-stu-id="53c30-127">To complete the task, the *Force* parameter is also required on **Unregister-Event**.</span></span>

## <span data-ttu-id="53c30-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="53c30-128">PARAMETERS</span></span>

### <span data-ttu-id="53c30-129">-Force</span><span class="sxs-lookup"><span data-stu-id="53c30-129">-Force</span></span>
<span data-ttu-id="53c30-130">Bricht alle Ereignis Abonnements ab, einschließlich Abonnements, die mit dem *supportevent* -Parameter von **Register-ObjectEvent** , **Register-wmievent** und **Register-engineevent** ausgeblendet wurden.</span><span class="sxs-lookup"><span data-stu-id="53c30-130">Cancels all event subscriptions, including subscriptions that were hidden by using the *SupportEvent* parameter of **Register-ObjectEvent** , **Register-WmiEvent** , and **Register-EngineEvent**.</span></span>

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

### <span data-ttu-id="53c30-131">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="53c30-131">-SourceIdentifier</span></span>
<span data-ttu-id="53c30-132">Gibt einen Quell Bezeichner an, mit dem dieses Cmdlet Ereignis Abonnements abbricht.</span><span class="sxs-lookup"><span data-stu-id="53c30-132">Specifies a source identifier that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="53c30-133">Ein *SourceIdentifier* -oder *Abonnement-ID* -Parameter muss in jedem Befehl enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="53c30-133">A *SourceIdentifier* or *SubscriptionId* parameter must be included in every command.</span></span>

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

### <span data-ttu-id="53c30-134">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="53c30-134">-SubscriptionId</span></span>
<span data-ttu-id="53c30-135">Gibt eine quellbezeichnerkennung an, mit der dieses Cmdlet Ereignis Abonnements abbricht.</span><span class="sxs-lookup"><span data-stu-id="53c30-135">Specifies a source identifier ID that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="53c30-136">Ein *SourceIdentifier* -oder *Abonnement-ID* -Parameter muss in jedem Befehl enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="53c30-136">A *SourceIdentifier* or *SubscriptionId* parameter must be included in every command.</span></span>

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

### <span data-ttu-id="53c30-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="53c30-137">-Confirm</span></span>
<span data-ttu-id="53c30-138">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="53c30-138">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="53c30-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="53c30-139">-WhatIf</span></span>
<span data-ttu-id="53c30-140">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="53c30-140">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="53c30-141">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="53c30-141">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="53c30-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="53c30-142">CommonParameters</span></span>
<span data-ttu-id="53c30-143">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="53c30-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="53c30-144">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="53c30-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="53c30-145">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="53c30-145">INPUTS</span></span>

### <span data-ttu-id="53c30-146">System. Management. Automation. psiebziger Subscriber</span><span class="sxs-lookup"><span data-stu-id="53c30-146">System.Management.Automation.PSEventSubscriber</span></span>
<span data-ttu-id="53c30-147">Sie können die Ausgabe von Get-EventSubscriber an **Unregister-Event** übergeben.</span><span class="sxs-lookup"><span data-stu-id="53c30-147">You can pipe the output from Get-EventSubscriber to **Unregister-Event**.</span></span>

## <span data-ttu-id="53c30-148">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="53c30-148">OUTPUTS</span></span>

### <span data-ttu-id="53c30-149">Keine</span><span class="sxs-lookup"><span data-stu-id="53c30-149">None</span></span>
<span data-ttu-id="53c30-150">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="53c30-150">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="53c30-151">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="53c30-151">NOTES</span></span>

* <span data-ttu-id="53c30-152">Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="53c30-152">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="53c30-153">Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="53c30-153">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

  <span data-ttu-id="53c30-154">**Unregister-Event** kann Ereignisse nicht löschen, die mit dem Cmdlet "New-Event" erstellt wurden, es sei denn, Sie haben das Ereignis mithilfe des **Register-engineevent** -Cmdlets abonniert.</span><span class="sxs-lookup"><span data-stu-id="53c30-154">**Unregister-Event** cannot delete events created by using the New-Event cmdlet unless you have subscribed to the event by using the **Register-EngineEvent** cmdlet.</span></span>
<span data-ttu-id="53c30-155">Um ein benutzerdefiniertes Ereignis aus der Sitzung zu löschen, müssen Sie es programmgesteuert entfernen oder die Sitzung schließen.</span><span class="sxs-lookup"><span data-stu-id="53c30-155">To delete a custom event from the session, you must remove it programmatically or close the session.</span></span>

*

## <span data-ttu-id="53c30-156">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="53c30-156">RELATED LINKS</span></span>

[<span data-ttu-id="53c30-157">Get-Event</span><span class="sxs-lookup"><span data-stu-id="53c30-157">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="53c30-158">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="53c30-158">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="53c30-159">New-Event</span><span class="sxs-lookup"><span data-stu-id="53c30-159">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="53c30-160">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="53c30-160">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="53c30-161">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="53c30-161">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="53c30-162">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="53c30-162">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="53c30-163">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="53c30-163">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="53c30-164">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="53c30-164">Wait-Event</span></span>](Wait-Event.md)

