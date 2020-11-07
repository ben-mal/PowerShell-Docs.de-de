---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-event?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Event
ms.openlocfilehash: fb5c6761427ea3c79075a18e551bfa7b39f72dc3
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343418"
---
# <span data-ttu-id="4c3a6-103">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="4c3a6-103">Remove-Event</span></span>

## <span data-ttu-id="4c3a6-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4c3a6-104">SYNOPSIS</span></span>
<span data-ttu-id="4c3a6-105">Löscht Ereignisse aus der Ereigniswarteschlange.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-105">Deletes events from the event queue.</span></span>

## <span data-ttu-id="4c3a6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4c3a6-106">SYNTAX</span></span>

### <span data-ttu-id="4c3a6-107">Bysource (Standard)</span><span class="sxs-lookup"><span data-stu-id="4c3a6-107">BySource (Default)</span></span>

```
Remove-Event [-SourceIdentifier] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4c3a6-108">Byidentifier</span><span class="sxs-lookup"><span data-stu-id="4c3a6-108">ByIdentifier</span></span>

```
Remove-Event [-EventIdentifier] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4c3a6-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4c3a6-109">DESCRIPTION</span></span>

<span data-ttu-id="4c3a6-110">Das- `Remove-Event` Cmdlet löscht Ereignisse aus der Ereignis Warteschlange in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-110">The `Remove-Event` cmdlet deletes events from the event queue in the current session.</span></span>

<span data-ttu-id="4c3a6-111">Mit diesem Cmdlet werden nur Ereignisse gelöscht, die sich aktuell in der Warteschlange befinden.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-111">This cmdlet deletes only the events currently in the queue.</span></span> <span data-ttu-id="4c3a6-112">Verwenden Sie das Cmdlet, um Ereignis Registrierungen abzubrechen oder das Abonnement abzubestellen `Unregister-Event` .</span><span class="sxs-lookup"><span data-stu-id="4c3a6-112">To cancel event registrations or unsubscribe, use the `Unregister-Event` cmdlet.</span></span>

## <span data-ttu-id="4c3a6-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4c3a6-113">EXAMPLES</span></span>

### <span data-ttu-id="4c3a6-114">Beispiel 1: Entfernen eines Ereignisses nach dem Quell Bezeichner</span><span class="sxs-lookup"><span data-stu-id="4c3a6-114">Example 1: Remove an event by source identifier</span></span>

```
PS C:\> Remove-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="4c3a6-115">Dieser Befehl löscht Ereignisse mit einem Quell Bezeichner des Prozesses, der aus der Ereignis Warteschlange gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-115">This command deletes events with a source identifier of Process Started from the event queue.</span></span>

### <span data-ttu-id="4c3a6-116">Beispiel 2: Entfernen eines Ereignisses nach Ereignis Bezeichner</span><span class="sxs-lookup"><span data-stu-id="4c3a6-116">Example 2: Remove an event by event identifier</span></span>

```
PS C:\> Remove-Event -EventIdentifier 30
```

<span data-ttu-id="4c3a6-117">Dieser Befehl löscht das Ereignis mit der Ereignis-ID 30 aus der Ereigniswarteschlange.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-117">This command deletes the event with an event ID of 30 from the event queue.</span></span>

### <span data-ttu-id="4c3a6-118">Beispiel 3: Entfernen aller Ereignisse</span><span class="sxs-lookup"><span data-stu-id="4c3a6-118">Example 3: Remove all events</span></span>

```
PS C:\> Get-Event | Remove-Event
```

<span data-ttu-id="4c3a6-119">Dieser Befehl löscht alle Ereignisse aus der Ereigniswarteschlange.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-119">This command deletes all events from the event queue.</span></span>

## <span data-ttu-id="4c3a6-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4c3a6-120">PARAMETERS</span></span>

### <span data-ttu-id="4c3a6-121">-Eventidentifier</span><span class="sxs-lookup"><span data-stu-id="4c3a6-121">-EventIdentifier</span></span>

<span data-ttu-id="4c3a6-122">Gibt den Ereignis Bezeichner an, den das Cmdlet löscht.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-122">Specifies the event identifier for which the cmdlet deletes.</span></span> <span data-ttu-id="4c3a6-123">Ein **eventidentifier** -oder **SourceIdentifier** -Parameter ist in jedem Befehl erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-123">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ByIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4c3a6-124">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="4c3a6-124">-SourceIdentifier</span></span>

<span data-ttu-id="4c3a6-125">Gibt den Quell Bezeichner an, aus dem dieses Cmdlet Ereignisse löscht.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-125">Specifies the source identifier for which this cmdlet deletes events from.</span></span> <span data-ttu-id="4c3a6-126">Platzhalter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-126">Wildcards are not permitted.</span></span> <span data-ttu-id="4c3a6-127">Ein **eventidentifier** -oder **SourceIdentifier** -Parameter ist in jedem Befehl erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-127">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4c3a6-128">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4c3a6-128">-Confirm</span></span>

<span data-ttu-id="4c3a6-129">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-129">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4c3a6-130">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4c3a6-130">-WhatIf</span></span>

<span data-ttu-id="4c3a6-131">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-131">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="4c3a6-132">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-132">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4c3a6-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4c3a6-133">CommonParameters</span></span>

<span data-ttu-id="4c3a6-134">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4c3a6-135">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4c3a6-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4c3a6-136">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4c3a6-136">INPUTS</span></span>

### <span data-ttu-id="4c3a6-137">System. Management. Automation. psiebziger args</span><span class="sxs-lookup"><span data-stu-id="4c3a6-137">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="4c3a6-138">Ereignisse können von `Get-Event` an übergeben werden `Remove-Event` .</span><span class="sxs-lookup"><span data-stu-id="4c3a6-138">You can pipe events from `Get-Event` to `Remove-Event`.</span></span>

## <span data-ttu-id="4c3a6-139">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4c3a6-139">OUTPUTS</span></span>

### <span data-ttu-id="4c3a6-140">Keine</span><span class="sxs-lookup"><span data-stu-id="4c3a6-140">None</span></span>

<span data-ttu-id="4c3a6-141">Das Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-141">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="4c3a6-142">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4c3a6-142">NOTES</span></span>

<span data-ttu-id="4c3a6-143">Auf den Linux-oder macOS-Plattformen sind keine Ereignis Quellen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-143">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="4c3a6-144">Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-144">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="4c3a6-145">Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="4c3a6-145">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="4c3a6-146">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4c3a6-146">RELATED LINKS</span></span>

[<span data-ttu-id="4c3a6-147">Get-Event</span><span class="sxs-lookup"><span data-stu-id="4c3a6-147">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="4c3a6-148">New-Event</span><span class="sxs-lookup"><span data-stu-id="4c3a6-148">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="4c3a6-149">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="4c3a6-149">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="4c3a6-150">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="4c3a6-150">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="4c3a6-151">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="4c3a6-151">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="4c3a6-152">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="4c3a6-152">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="4c3a6-153">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="4c3a6-153">Wait-Event</span></span>](Wait-Event.md)
