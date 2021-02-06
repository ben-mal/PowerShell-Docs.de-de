---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Event
ms.openlocfilehash: 3193de9020f2f54795bde9d5cce1bb86c4431ef9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595521"
---
# <span data-ttu-id="05960-102">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="05960-102">Remove-Event</span></span>

## <span data-ttu-id="05960-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="05960-103">SYNOPSIS</span></span>
<span data-ttu-id="05960-104">Löscht Ereignisse aus der Ereigniswarteschlange.</span><span class="sxs-lookup"><span data-stu-id="05960-104">Deletes events from the event queue.</span></span>

## <span data-ttu-id="05960-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="05960-105">SYNTAX</span></span>

### <span data-ttu-id="05960-106">Bysource (Standard)</span><span class="sxs-lookup"><span data-stu-id="05960-106">BySource (Default)</span></span>

```
Remove-Event [-SourceIdentifier] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="05960-107">Byidentifier</span><span class="sxs-lookup"><span data-stu-id="05960-107">ByIdentifier</span></span>

```
Remove-Event [-EventIdentifier] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="05960-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="05960-108">DESCRIPTION</span></span>

<span data-ttu-id="05960-109">Das- `Remove-Event` Cmdlet löscht Ereignisse aus der Ereignis Warteschlange in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="05960-109">The `Remove-Event` cmdlet deletes events from the event queue in the current session.</span></span>

<span data-ttu-id="05960-110">Mit diesem Cmdlet werden nur Ereignisse gelöscht, die sich aktuell in der Warteschlange befinden.</span><span class="sxs-lookup"><span data-stu-id="05960-110">This cmdlet deletes only the events currently in the queue.</span></span> <span data-ttu-id="05960-111">Verwenden Sie das Cmdlet, um Ereignis Registrierungen abzubrechen oder das Abonnement abzubestellen `Unregister-Event` .</span><span class="sxs-lookup"><span data-stu-id="05960-111">To cancel event registrations or unsubscribe, use the `Unregister-Event` cmdlet.</span></span>

## <span data-ttu-id="05960-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="05960-112">EXAMPLES</span></span>

### <span data-ttu-id="05960-113">Beispiel 1: Entfernen eines Ereignisses nach dem Quell Bezeichner</span><span class="sxs-lookup"><span data-stu-id="05960-113">Example 1: Remove an event by source identifier</span></span>

```
PS C:\> Remove-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="05960-114">Dieser Befehl löscht Ereignisse mit einem Quell Bezeichner des Prozesses, der aus der Ereignis Warteschlange gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="05960-114">This command deletes events with a source identifier of Process Started from the event queue.</span></span>

### <span data-ttu-id="05960-115">Beispiel 2: Entfernen eines Ereignisses nach Ereignis Bezeichner</span><span class="sxs-lookup"><span data-stu-id="05960-115">Example 2: Remove an event by event identifier</span></span>

```
PS C:\> Remove-Event -EventIdentifier 30
```

<span data-ttu-id="05960-116">Dieser Befehl löscht das Ereignis mit der Ereignis-ID 30 aus der Ereigniswarteschlange.</span><span class="sxs-lookup"><span data-stu-id="05960-116">This command deletes the event with an event ID of 30 from the event queue.</span></span>

### <span data-ttu-id="05960-117">Beispiel 3: Entfernen aller Ereignisse</span><span class="sxs-lookup"><span data-stu-id="05960-117">Example 3: Remove all events</span></span>

```
PS C:\> Get-Event | Remove-Event
```

<span data-ttu-id="05960-118">Dieser Befehl löscht alle Ereignisse aus der Ereigniswarteschlange.</span><span class="sxs-lookup"><span data-stu-id="05960-118">This command deletes all events from the event queue.</span></span>

## <span data-ttu-id="05960-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="05960-119">PARAMETERS</span></span>

### <span data-ttu-id="05960-120">-Eventidentifier</span><span class="sxs-lookup"><span data-stu-id="05960-120">-EventIdentifier</span></span>

<span data-ttu-id="05960-121">Gibt den Ereignis Bezeichner an, den das Cmdlet löscht.</span><span class="sxs-lookup"><span data-stu-id="05960-121">Specifies the event identifier for which the cmdlet deletes.</span></span> <span data-ttu-id="05960-122">Ein **eventidentifier** -oder **SourceIdentifier** -Parameter ist in jedem Befehl erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05960-122">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

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

### <span data-ttu-id="05960-123">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="05960-123">-SourceIdentifier</span></span>

<span data-ttu-id="05960-124">Gibt den Quell Bezeichner an, aus dem dieses Cmdlet Ereignisse löscht.</span><span class="sxs-lookup"><span data-stu-id="05960-124">Specifies the source identifier for which this cmdlet deletes events from.</span></span> <span data-ttu-id="05960-125">Platzhalter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="05960-125">Wildcards are not permitted.</span></span> <span data-ttu-id="05960-126">Ein **eventidentifier** -oder **SourceIdentifier** -Parameter ist in jedem Befehl erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05960-126">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

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

### <span data-ttu-id="05960-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="05960-127">-Confirm</span></span>

<span data-ttu-id="05960-128">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="05960-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="05960-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="05960-129">-WhatIf</span></span>

<span data-ttu-id="05960-130">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="05960-130">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="05960-131">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="05960-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="05960-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="05960-132">CommonParameters</span></span>

<span data-ttu-id="05960-133">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="05960-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="05960-134">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="05960-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="05960-135">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="05960-135">INPUTS</span></span>

### <span data-ttu-id="05960-136">System. Management. Automation. psiebziger args</span><span class="sxs-lookup"><span data-stu-id="05960-136">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="05960-137">Ereignisse können von `Get-Event` an übergeben werden `Remove-Event` .</span><span class="sxs-lookup"><span data-stu-id="05960-137">You can pipe events from `Get-Event` to `Remove-Event`.</span></span>

## <span data-ttu-id="05960-138">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="05960-138">OUTPUTS</span></span>

### <span data-ttu-id="05960-139">Keine</span><span class="sxs-lookup"><span data-stu-id="05960-139">None</span></span>

<span data-ttu-id="05960-140">Das Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="05960-140">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="05960-141">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="05960-141">NOTES</span></span>

<span data-ttu-id="05960-142">Auf den Linux-oder macOS-Plattformen sind keine Ereignis Quellen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="05960-142">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="05960-143">Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="05960-143">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="05960-144">Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="05960-144">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="05960-145">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="05960-145">RELATED LINKS</span></span>

[<span data-ttu-id="05960-146">Get-Event</span><span class="sxs-lookup"><span data-stu-id="05960-146">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="05960-147">New-Event</span><span class="sxs-lookup"><span data-stu-id="05960-147">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="05960-148">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="05960-148">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="05960-149">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="05960-149">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="05960-150">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="05960-150">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="05960-151">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="05960-151">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="05960-152">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="05960-152">Wait-Event</span></span>](Wait-Event.md)
