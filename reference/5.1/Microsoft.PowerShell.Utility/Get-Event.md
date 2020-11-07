---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-event?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Event
ms.openlocfilehash: e8f61d0c897c5ece7071ff982eb141079c8c88b9
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344693"
---
# <span data-ttu-id="f1a74-103">Get-Event</span><span class="sxs-lookup"><span data-stu-id="f1a74-103">Get-Event</span></span>

## <span data-ttu-id="f1a74-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f1a74-104">SYNOPSIS</span></span>
<span data-ttu-id="f1a74-105">Ruft die Ereignisse in der Ereigniswarteschlange ab.</span><span class="sxs-lookup"><span data-stu-id="f1a74-105">Gets the events in the event queue.</span></span>

## <span data-ttu-id="f1a74-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f1a74-106">SYNTAX</span></span>

### <span data-ttu-id="f1a74-107">Bysource (Standard)</span><span class="sxs-lookup"><span data-stu-id="f1a74-107">BySource (Default)</span></span>

```
Get-Event [[-SourceIdentifier] <String>] [<CommonParameters>]
```

### <span data-ttu-id="f1a74-108">ById</span><span class="sxs-lookup"><span data-stu-id="f1a74-108">ById</span></span>

```
Get-Event [-EventIdentifier] <Int32> [<CommonParameters>]
```

## <span data-ttu-id="f1a74-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f1a74-109">DESCRIPTION</span></span>

<span data-ttu-id="f1a74-110">Das- `Get-Event` Cmdlet ruft Ereignisse in der PowerShell-Ereignis Warteschlange für die aktuelle Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="f1a74-110">The `Get-Event` cmdlet gets events in the PowerShell event queue for the current session.</span></span> <span data-ttu-id="f1a74-111">Sie können alle Ereignisse oder den **eventidentifier** -oder **SourceIdentifier** -Parameter verwenden, um die Ereignisse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f1a74-111">You can get all events or use the **EventIdentifier** or **SourceIdentifier** parameter to specify the events.</span></span>

<span data-ttu-id="f1a74-112">Wenn ein Ereignis auftritt, wird es zur Ereigniswarteschlange hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f1a74-112">When an event occurs, it is added to the event queue.</span></span> <span data-ttu-id="f1a74-113">Die Ereignis Warteschlange enthält Ereignisse, für die Sie sich registriert haben, Ereignisse, die mithilfe des `New-Event` Cmdlets erstellt wurden, und das Ereignis, das ausgelöst wird, wenn PowerShell beendet wird.</span><span class="sxs-lookup"><span data-stu-id="f1a74-113">The event queue includes events for which you have registered, events created by using the `New-Event` cmdlet, and the event that is raised when PowerShell exits.</span></span> <span data-ttu-id="f1a74-114">Sie können `Get-Event` oder verwenden `Wait-Event` , um die Ereignisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f1a74-114">You can use `Get-Event` or `Wait-Event` to get the events.</span></span>

<span data-ttu-id="f1a74-115">Dieses Cmdlet ruft keine Ereignisse aus den Protokollen der Ereignisanzeige ab.</span><span class="sxs-lookup"><span data-stu-id="f1a74-115">This cmdlet does not get events from the Event Viewer logs.</span></span> <span data-ttu-id="f1a74-116">Um diese Ereignisse zu erhalten, verwenden Sie `Get-WinEvent` oder `Get-EventLog` .</span><span class="sxs-lookup"><span data-stu-id="f1a74-116">To get those events, use `Get-WinEvent` or `Get-EventLog`.</span></span>

## <span data-ttu-id="f1a74-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f1a74-117">EXAMPLES</span></span>

### <span data-ttu-id="f1a74-118">Beispiel 1: alle Ereignisse erhalten</span><span class="sxs-lookup"><span data-stu-id="f1a74-118">Example 1: Get all events</span></span>

```
PS C:\> Get-Event
```

<span data-ttu-id="f1a74-119">Mit diesem Befehl werden alle Ereignisse in der Ereigniswarteschlange abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f1a74-119">This command gets all events in the event queue.</span></span>

### <span data-ttu-id="f1a74-120">Beispiel 2: Ereignisse nach Quell Bezeichner</span><span class="sxs-lookup"><span data-stu-id="f1a74-120">Example 2: Get events by source identifier</span></span>

```
PS C:\> Get-Event -SourceIdentifier "PowerShell.ProcessCreated"
```

<span data-ttu-id="f1a74-121">Dieser Befehl ruft Ereignisse ab, in denen der Wert der SourceIdentifier-Eigenschaft "PowerShell. processcreated" ist.</span><span class="sxs-lookup"><span data-stu-id="f1a74-121">This command gets events in which the value of the SourceIdentifier property is PowerShell.ProcessCreated.</span></span>

### <span data-ttu-id="f1a74-122">Beispiel 3: erhalten eines Ereignisses basierend auf dem Zeitpunkt, an dem es generiert wurde</span><span class="sxs-lookup"><span data-stu-id="f1a74-122">Example 3: Get an event based on the time it was generated</span></span>

```
PS C:\> $Events = Get-Event
PS C:\> $Events[0] | Format-List -Property *
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b805917d1b7b
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:09:32 PM
MessageData      : PS C:\> Get-Event | Where {$_.TimeGenerated -ge "11/13/2008 12:15:00 PM"}
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b8059325d1a0
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:15:00 PM
MessageData      :
```

<span data-ttu-id="f1a74-123">Dieses Beispiel zeigt, wie Ereignisse mithilfe anderer Eigenschaften als „SourceIdentifier“ abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f1a74-123">This example shows how to get events by using properties other than SourceIdentifier.</span></span>

<span data-ttu-id="f1a74-124">Der erste Befehl ruft alle Ereignisse in der Ereignis Warteschlange ab und speichert Sie in der `$Events` Variablen.</span><span class="sxs-lookup"><span data-stu-id="f1a74-124">The first command gets all events in the event queue and saves them in the `$Events` variable.</span></span>

<span data-ttu-id="f1a74-125">Der zweite Befehl verwendet die Array Notation, um das erste Ereignis (0-Index) im Array in der `$Events` Variablen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f1a74-125">The second command uses array notation to get the first (0-index) event in the array in the `$Events` variable.</span></span> <span data-ttu-id="f1a74-126">Der Befehl verwendet einen Pipeline Operator ( `|` ), um das Ereignis an den `Format-List` Befehl zu senden, der alle Eigenschaften des Ereignisses in einer Liste anzeigt.</span><span class="sxs-lookup"><span data-stu-id="f1a74-126">The command uses a pipeline operator (`|`) to send the event to the `Format-List` command, which displays all properties of the event in a list.</span></span> <span data-ttu-id="f1a74-127">Dadurch können Sie die Eigenschaften des Ereignisobjekts überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f1a74-127">This allows you to examine the properties of the event object.</span></span>

<span data-ttu-id="f1a74-128">Der dritte Befehl zeigt, wie das `Where-Object` Cmdlet verwendet wird, um ein Ereignis basierend auf dem Zeitpunkt, an dem es generiert wurde, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f1a74-128">The third command shows how to use the `Where-Object` cmdlet to get an event based on the time that it was generated.</span></span>

### <span data-ttu-id="f1a74-129">Beispiel 4: erhalten eines Ereignisses anhand seines Bezeichners</span><span class="sxs-lookup"><span data-stu-id="f1a74-129">Example 4: Get an event by its identifier</span></span>

```
PS C:\> Get-Event -EventIdentifier 2
```

<span data-ttu-id="f1a74-130">Dieser Befehl ruft das Ereignis mit der Ereignis-ID 2 ab.</span><span class="sxs-lookup"><span data-stu-id="f1a74-130">This command gets the event with an event identifier of 2.</span></span>

## <span data-ttu-id="f1a74-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f1a74-131">PARAMETERS</span></span>

### <span data-ttu-id="f1a74-132">-Eventidentifier</span><span class="sxs-lookup"><span data-stu-id="f1a74-132">-EventIdentifier</span></span>

<span data-ttu-id="f1a74-133">Gibt die Ereignis Bezeichner an, für die dieses Cmdlet Ereignisse abruft.</span><span class="sxs-lookup"><span data-stu-id="f1a74-133">Specifies the event identifiers for which this cmdlet gets events.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f1a74-134">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="f1a74-134">-SourceIdentifier</span></span>

<span data-ttu-id="f1a74-135">Gibt Quell Bezeichner an, für die dieses Cmdlet Ereignisse abruft.</span><span class="sxs-lookup"><span data-stu-id="f1a74-135">Specifies source identifiers for which this cmdlet gets events.</span></span> <span data-ttu-id="f1a74-136">Standardmäßig werden alle Ereignisse in der Ereigniswarteschlange abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f1a74-136">The default is all events in the event queue.</span></span> <span data-ttu-id="f1a74-137">Platzhalter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="f1a74-137">Wildcards are not permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f1a74-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f1a74-138">CommonParameters</span></span>

<span data-ttu-id="f1a74-139">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f1a74-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f1a74-140">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f1a74-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f1a74-141">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f1a74-141">INPUTS</span></span>

### <span data-ttu-id="f1a74-142">Keine</span><span class="sxs-lookup"><span data-stu-id="f1a74-142">None</span></span>

<span data-ttu-id="f1a74-143">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="f1a74-143">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="f1a74-144">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f1a74-144">OUTPUTS</span></span>

### <span data-ttu-id="f1a74-145">System. Management. Automation. psiebziger args</span><span class="sxs-lookup"><span data-stu-id="f1a74-145">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="f1a74-146">`Get-Event` Gibt ein **peventargs** -Objekt für jedes Ereignis zurück.</span><span class="sxs-lookup"><span data-stu-id="f1a74-146">`Get-Event` returns a **PSEventArgs** object for each event.</span></span> <span data-ttu-id="f1a74-147">Um eine Beschreibung dieses Objekts anzuzeigen, geben Sie ein, `Get-Help Get-Event -Full` und lesen Sie den Abschnitt "Hinweise" des Hilfe Themas.</span><span class="sxs-lookup"><span data-stu-id="f1a74-147">To see a description of this object, type `Get-Help Get-Event -Full` and see the Notes section of the help topic.</span></span>

## <span data-ttu-id="f1a74-148">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f1a74-148">NOTES</span></span>

<span data-ttu-id="f1a74-149">Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f1a74-149">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="f1a74-150">Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="f1a74-150">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

<span data-ttu-id="f1a74-151">Das- `Get-Event` Cmdlet gibt ein **psiebziger args** -Objekt ( **System. Management. Automation. psiebargs** ) mit den folgenden Eigenschaften zurück:</span><span class="sxs-lookup"><span data-stu-id="f1a74-151">The `Get-Event` cmdlet returns a **PSEventArgs** object ( **System.Management.Automation.PSEventArgs** ) with the following properties:</span></span>

- <span data-ttu-id="f1a74-152">Computername.</span><span class="sxs-lookup"><span data-stu-id="f1a74-152">ComputerName.</span></span> <span data-ttu-id="f1a74-153">Der Name des Computers, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f1a74-153">The name of the computer on which the event occurred.</span></span> <span data-ttu-id="f1a74-154">Dieser Eigenschaftswert wird nur aufgefüllt, wenn das Ereignis von einem Remotecomputer weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="f1a74-154">This property value is populated only when the event is forwarded from a remote computer.</span></span>

- <span data-ttu-id="f1a74-155">Runspaceid.</span><span class="sxs-lookup"><span data-stu-id="f1a74-155">RunspaceId.</span></span> <span data-ttu-id="f1a74-156">Eine GUID, die die Sitzung, in der das Ereignis aufgetreten ist, eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f1a74-156">A GUID that uniquely identifies the session in which the event occurred.</span></span> <span data-ttu-id="f1a74-157">Dieser Eigenschaftswert wird nur aufgefüllt, wenn das Ereignis von einem Remotecomputer weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="f1a74-157">This property value is populated only when the event is forwarded from a remote computer.</span></span>

- <span data-ttu-id="f1a74-158">EventIdentifier.</span><span class="sxs-lookup"><span data-stu-id="f1a74-158">EventIdentifier.</span></span> <span data-ttu-id="f1a74-159">Eine ganze Zahl (Int32), die die Ereignisbenachrichtigung in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f1a74-159">An integer (Int32) that uniquely identifies the event notification in the current session.</span></span>

- <span data-ttu-id="f1a74-160">Sen.</span><span class="sxs-lookup"><span data-stu-id="f1a74-160">Sender.</span></span> <span data-ttu-id="f1a74-161">Das Objekt, das das Ereignis generiert hat.</span><span class="sxs-lookup"><span data-stu-id="f1a74-161">The object that generated the event.</span></span> <span data-ttu-id="f1a74-162">Im Wert des **Action** -Parameters enthält die `$Sender` Automatische Variable das Sender-Objekt.</span><span class="sxs-lookup"><span data-stu-id="f1a74-162">In the value of the **Action** parameter, the `$Sender` automatic variable contains the sender object.</span></span>

- <span data-ttu-id="f1a74-163">SourceEventArgs.</span><span class="sxs-lookup"><span data-stu-id="f1a74-163">SourceEventArgs.</span></span> <span data-ttu-id="f1a74-164">Der erste Parameter, der von EventArgs abgeleitet wird, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f1a74-164">The first parameter that derives from EventArgs, if it exists.</span></span> <span data-ttu-id="f1a74-165">Beispielsweise enthält die **sourceeventargs** -Eigenschaft in einem Ereignis mit Timer-verstrichenen Ereignissen, bei dem die Signatur das Formular Objekt Absender, **Timer. ElapsedEventArgs** e, die Eigenschaft " **Timers. ElapsedEventArgs** ".</span><span class="sxs-lookup"><span data-stu-id="f1a74-165">For example, in a timer elapsed event in which the signature has the form Object sender, **Timers.ElapsedEventArgs** e, the **SourceEventArgs** property would contain the **Timers.ElapsedEventArgs**.</span></span> <span data-ttu-id="f1a74-166">Im Wert des **Action** -Parameters enthält die `$EventArgs` Automatische Variable diesen Wert.</span><span class="sxs-lookup"><span data-stu-id="f1a74-166">In the value of the **Action** parameter, the `$EventArgs` automatic variable contains this value.</span></span>

- <span data-ttu-id="f1a74-167">Sourceargs.</span><span class="sxs-lookup"><span data-stu-id="f1a74-167">SourceArgs.</span></span> <span data-ttu-id="f1a74-168">Alle Parameter der ursprünglichen Ereignissignatur.</span><span class="sxs-lookup"><span data-stu-id="f1a74-168">All parameters of the original event signature.</span></span> <span data-ttu-id="f1a74-169">Für eine Standard Ereignis Signatur `$Args[0]` stellt den Absender dar und `$Args[1]` stellt die **sourceeventargs** dar.</span><span class="sxs-lookup"><span data-stu-id="f1a74-169">For a standard event signature, `$Args[0]` represents the sender, and `$Args[1]` represents the **SourceEventArgs**.</span></span> <span data-ttu-id="f1a74-170">Im Wert des **Action** -Parameters enthält die `$Args` Automatische Variable diesen Wert.</span><span class="sxs-lookup"><span data-stu-id="f1a74-170">In the value of the **Action** parameter, the `$Args` automatic variable contains this value.</span></span>

- <span data-ttu-id="f1a74-171">SourceIdentifier.</span><span class="sxs-lookup"><span data-stu-id="f1a74-171">SourceIdentifier.</span></span> <span data-ttu-id="f1a74-172">Eine Zeichenfolge, die das Ereignisabonnement bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f1a74-172">A string that identifies the event subscription.</span></span> <span data-ttu-id="f1a74-173">Im Wert des **Action** -Parameters enthält die **SourceIdentifier** -Eigenschaft der `$Event` automatischen Variablen diesen Wert.</span><span class="sxs-lookup"><span data-stu-id="f1a74-173">In the value of the **Action** parameter, the **SourceIdentifier** property of the `$Event` automatic variable contains this value.</span></span>

- <span data-ttu-id="f1a74-174">TimeGenerated.</span><span class="sxs-lookup"><span data-stu-id="f1a74-174">TimeGenerated.</span></span> <span data-ttu-id="f1a74-175">Ein **DateTime** -Objekt, das die Uhrzeit darstellt, zu der das Ereignis generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f1a74-175">A **DateTime** object that represents the time at which the event was generated.</span></span>
  <span data-ttu-id="f1a74-176">Im Wert des **Action** -Parameters enthält die **TimeGenerated** -Eigenschaft der `$Event` automatischen Variablen diesen Wert.</span><span class="sxs-lookup"><span data-stu-id="f1a74-176">In the value of the **Action** parameter, the **TimeGenerated** property of the `$Event` automatic variable contains this value.</span></span>

- <span data-ttu-id="f1a74-177">MessageData.</span><span class="sxs-lookup"><span data-stu-id="f1a74-177">MessageData.</span></span> <span data-ttu-id="f1a74-178">Die dem Ereignisabonnement zugeordneten Daten.</span><span class="sxs-lookup"><span data-stu-id="f1a74-178">Data associated with the event subscription.</span></span> <span data-ttu-id="f1a74-179">Benutzer geben diese Daten an, wenn sie ein Ereignis registrieren.</span><span class="sxs-lookup"><span data-stu-id="f1a74-179">Users specify this data when they register an event.</span></span> <span data-ttu-id="f1a74-180">Im Wert des **Action** -Parameters enthält die **messageData** -Eigenschaft der `$Event` automatischen Variablen diesen Wert.</span><span class="sxs-lookup"><span data-stu-id="f1a74-180">In the value of the **Action** parameter, the **MessageData** property of the `$Event` automatic variable contains this value.</span></span>

## <span data-ttu-id="f1a74-181">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f1a74-181">RELATED LINKS</span></span>

[<span data-ttu-id="f1a74-182">New-Event</span><span class="sxs-lookup"><span data-stu-id="f1a74-182">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="f1a74-183">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="f1a74-183">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="f1a74-184">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="f1a74-184">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="f1a74-185">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="f1a74-185">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="f1a74-186">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="f1a74-186">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="f1a74-187">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="f1a74-187">Wait-Event</span></span>](Wait-Event.md)
