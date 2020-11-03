---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-eventsubscriber?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventSubscriber
ms.openlocfilehash: e1ac039ce49141197c2e14b060118dd4c87f7003
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213092"
---
# <span data-ttu-id="5dca7-103">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="5dca7-103">Get-EventSubscriber</span></span>

## <span data-ttu-id="5dca7-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5dca7-104">SYNOPSIS</span></span>
<span data-ttu-id="5dca7-105">Ruft die Ereignisabonnenten in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="5dca7-105">Gets the event subscribers in the current session.</span></span>

## <span data-ttu-id="5dca7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5dca7-106">SYNTAX</span></span>

### <span data-ttu-id="5dca7-107">Bysource (Standard)</span><span class="sxs-lookup"><span data-stu-id="5dca7-107">BySource (Default)</span></span>

```
Get-EventSubscriber [[-SourceIdentifier] <String>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="5dca7-108">ById</span><span class="sxs-lookup"><span data-stu-id="5dca7-108">ById</span></span>

```
Get-EventSubscriber [-SubscriptionId] <Int32> [-Force] [<CommonParameters>]
```

## <span data-ttu-id="5dca7-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5dca7-109">DESCRIPTION</span></span>

<span data-ttu-id="5dca7-110">Das **Get-eventsubscriber** -Cmdlet ruft die Ereignis Abonnenten in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="5dca7-110">The **Get-EventSubscriber** cmdlet gets the event subscribers in the current session.</span></span>

<span data-ttu-id="5dca7-111">Wenn Sie ein Ereignis mithilfe eines Register Event-Cmdlets abonnieren, wird der PowerShell-Sitzung ein Ereignis Abonnent hinzugefügt, und die von Ihnen abonnierten Ereignisse werden ihrer Ereignis Warteschlange hinzugefügt, sobald sie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="5dca7-111">When you subscribe to an event by using a Register event cmdlet, an event subscriber is added to your PowerShell session, and the events to which you subscribed are added to your event queue whenever they are raised.</span></span>
<span data-ttu-id="5dca7-112">Um ein Ereignisabonnement zu stornieren, löschen Sie den Ereignisabonnenten mithilfe des Unregister-Event-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="5dca7-112">To cancel an event subscription, delete the event subscriber by using the Unregister-Event cmdlet.</span></span>

## <span data-ttu-id="5dca7-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5dca7-113">EXAMPLES</span></span>

### <span data-ttu-id="5dca7-114">Beispiel 1: erhalten des Ereignis Abonnenten für ein Zeit Geber Ereignis</span><span class="sxs-lookup"><span data-stu-id="5dca7-114">Example 1: Get the event subscriber for a timer event</span></span>

```
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer | Get-Member -Type Event
PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Elapsed
PS C:\> Get-EventSubscriber
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer | Get-Member -Type Event
TypeName: System.Timers.Timer
Name     MemberType Definition
----     ---------- ----------
Disposed Event      System.EventHandler Disposed(System.Object, System.EventArgs)
Elapsed  Event      System.Timers.ElapsedEventHandler Elapsed(System.Object, System.Timers.ElapsedEventArgs) PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Elapsed
PS C:\> Get-EventSubscriber
SubscriptionId   : 4
SourceObject     : System.Timers.Timer
EventName        : Elapsed
SourceIdentifier : Timer.Elapsed
Action           :
HandlerDelegate  :
SupportEvent     : False
ForwardEvent     : False
```

<span data-ttu-id="5dca7-115">In diesem Beispiel wird ein **Get-eventsubscriber** -Befehl verwendet, um den Ereignis Abonnenten für ein Zeit Geber Ereignis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5dca7-115">This example uses a **Get-EventSubscriber** command to get the event subscriber for a timer event.</span></span>

<span data-ttu-id="5dca7-116">Der erste Befehl verwendet das New-Object-Cmdlet, um eine Instanz eines Zeitgeberobjekts zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5dca7-116">The first command uses the New-Object cmdlet to create an instance of a timer object.</span></span>
<span data-ttu-id="5dca7-117">Das neue Timer-Objekt wird in der $Timer-Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5dca7-117">It saves the new timer object in the $Timer variable.</span></span>

<span data-ttu-id="5dca7-118">Der zweite Befehl verwendet das Get-Member-Cmdlet, um die für Zeitgeberobjekte verfügbaren Ereignisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5dca7-118">The second command uses the Get-Member cmdlet to display the events that are available for timer objects.</span></span>
<span data-ttu-id="5dca7-119">Der Befehl verwendet den Type-Parameter des Cmdlets " **Get-Member** " mit dem Wert "Event".</span><span class="sxs-lookup"><span data-stu-id="5dca7-119">The command uses the Type parameter of the **Get-Member** cmdlet with a value of Event.</span></span>

<span data-ttu-id="5dca7-120">Der dritte Befehl verwendet das Register-ObjectEvent-Cmdlet, um sich für das Elapsed-Ereignis des Zeitgeberobjekts zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="5dca7-120">The third command uses the Register-ObjectEvent cmdlet to register for the Elapsed event on the timer object.</span></span>

<span data-ttu-id="5dca7-121">Der vierte Befehl verwendet das **Get-eventsubscriber** -Cmdlet, um den Ereignis Abonnenten für das verstrichene Ereignis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5dca7-121">The fourth command uses the **Get-EventSubscriber** cmdlet to get the event subscriber for the Elapsed event.</span></span>

### <span data-ttu-id="5dca7-122">Beispiel 2: Verwenden des dynamischen Moduls in psiebziger Job in der Action-Eigenschaft des Ereignis Abonnenten</span><span class="sxs-lookup"><span data-stu-id="5dca7-122">Example 2: Use the dynamic module in PSEventJob in the Action property of the event subscriber</span></span>

```
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer.Interval = 500
PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Random -Action { $Random = Get-Random -Min 0 -Max 100 }

Id  Name           State      HasMoreData  Location  Command
--  ----           -----      -----------  --------  -------
3   Timer.Random   NotStarted False                  $Random = Get-Random ...

PS C:\> $Timer.Enabled = $True
PS C:\> $Subscriber = Get-EventSubscriber -SourceIdentifier Timer.Random
PS C:\> ($Subscriber.action).gettype().fullname
System.Management.Automation.PSEventJob
PS C:\> $Subscriber.action | Format-List -Property *

State         : Running
Module        : __DynamicModule_6b5cbe82-d634-41d1-ae5e-ad7fe8d57fe0
StatusMessage :
HasMoreData   : True
Location      :
Command       : $random = Get-Random -Min 0 -Max 100
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : 88944290-133d-4b44-8752-f901bd8012e2
Id            : 1
Name          : Timer.Random
ChildJobs     : {}
...

PS C:\> & $Subscriber.action.module {$Random}
96
PS C:\> & $Subscriber.action.module {$Random}
23
```

<span data-ttu-id="5dca7-123">Dieses Beispiel zeigt, wie Sie das dynamische Modul im **psiebziger Job** -Objekt in der Action-Eigenschaft des Ereignis Abonnenten verwenden.</span><span class="sxs-lookup"><span data-stu-id="5dca7-123">This example shows how to use the dynamic module in the **PSEventJob** object in the Action property of the event subscriber.</span></span>

<span data-ttu-id="5dca7-124">Der erste Befehl verwendet das New-Object-Cmdlet, um ein Zeitgeberobjekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5dca7-124">The first command uses the New-Object cmdlet to create a timer object.</span></span>
<span data-ttu-id="5dca7-125">Der zweite Befehl legt das Intervall des Zeitgebers auf 500 (Millisekunden) fest.</span><span class="sxs-lookup"><span data-stu-id="5dca7-125">The second command sets the interval of the timer to 500 (milliseconds).</span></span>

<span data-ttu-id="5dca7-126">Der dritte Befehl verwendet das Register-ObjectEvent-Cmdlet, um sich für das Elapsed-Ereignis des Zeitgeberobjekts zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="5dca7-126">The third command uses the Register-ObjectEvent cmdlet to register the Elapsed event of the timer object.</span></span>
<span data-ttu-id="5dca7-127">Der Befehl enthält eine Aktion zur Behandlung des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="5dca7-127">The command includes an action that handles the event.</span></span>
<span data-ttu-id="5dca7-128">Wenn das Zeitgeberintervall abläuft, wird ein Ereignis ausgelöst, und die Befehle in der Aktion werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5dca7-128">Whenever the timer interval elapses, an event is raised and the commands in the action run.</span></span>
<span data-ttu-id="5dca7-129">In diesem Fall generiert das Cmdlet "Get-Random" eine Zufallszahl zwischen 0 und 100 und speichert Sie in der $Random-Variablen.</span><span class="sxs-lookup"><span data-stu-id="5dca7-129">In this case, the Get-Random cmdlet generates a random number between 0 and 100 and saves it in the $Random variable.</span></span>
<span data-ttu-id="5dca7-130">Der Quellbezeichner des Ereignisses ist Timer.Random.</span><span class="sxs-lookup"><span data-stu-id="5dca7-130">The source identifier of the event is Timer.Random.</span></span>

<span data-ttu-id="5dca7-131">Wenn Sie einen *Action* -Parameter in einem **Register-ObjectEvent-** Befehl verwenden, gibt der Befehl ein **psiebziger Job** -Objekt zurück, das die Aktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="5dca7-131">When you use an *Action* parameter in a **Register-ObjectEvent** command, the command returns a **PSEventJob** object that represents the action.</span></span>

<span data-ttu-id="5dca7-132">Der vierte Befehl aktiviert den Zeitgeber.</span><span class="sxs-lookup"><span data-stu-id="5dca7-132">The fourth command enables the timer.</span></span>

<span data-ttu-id="5dca7-133">Der fünfte Befehl verwendet das **Get-eventsubscriber** -Cmdlet, um den Ereignis Abonnenten des Timer. Random-Ereignisses zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5dca7-133">The fifth command uses the **Get-EventSubscriber** cmdlet to get the event subscriber of the Timer.Random event.</span></span>
<span data-ttu-id="5dca7-134">Das Ereignis Abonnenten Objekt wird in der $Subscriber Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5dca7-134">It saves the event subscriber object in the $Subscriber variable.</span></span>

<span data-ttu-id="5dca7-135">Der sechste Befehl zeigt, dass die Action-Eigenschaft des Ereignis Abonnenten Objekts ein **peventjob** -Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="5dca7-135">The sixth command shows that the Action property of the event subscriber object contains a **PSEventJob** object.</span></span>
<span data-ttu-id="5dca7-136">Tatsächlich enthält Sie das gleiche **psiebziger Job** -Objekt, das vom **Register-ObjectEvent** -Befehl zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="5dca7-136">In fact, it contains the same **PSEventJob** object that the **Register-ObjectEvent** command returned.</span></span>

<span data-ttu-id="5dca7-137">Der siebte Befehl verwendet das Cmdlet "Format-List", um alle Eigenschaften des **psiebziger Job** -Objekts in der Action-Eigenschaft in einer Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5dca7-137">The seventh command uses the Format-List cmdlet to display all of the properties of the **PSEventJob** object in the Action property in a list.</span></span>
<span data-ttu-id="5dca7-138">Das Ergebnis zeigt, dass das **psiebziger Job** -Objekt über eine Module-Eigenschaft verfügt, die ein dynamisches Skript Modul enthält, das die Aktion implementiert.</span><span class="sxs-lookup"><span data-stu-id="5dca7-138">The result reveals that the **PSEventJob** object has a Module property that contains a dynamic script module that implements the action.</span></span>

<span data-ttu-id="5dca7-139">Die übrigen Befehle verwenden den Aufruf Operator (&), um den Befehl im Modul aufzurufen und den Wert der $Random Variablen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5dca7-139">The remaining commands use the call operator (&) to invoke the command in the module and display the value of the $Random variable.</span></span>
<span data-ttu-id="5dca7-140">Mit dem Aufrufoperator können Sie einen beliebigen Befehl in einem Modul aufrufen, einschließlich nicht exportierter Befehle.</span><span class="sxs-lookup"><span data-stu-id="5dca7-140">You can use the call operator to invoke any command in a module, including commands that are not exported.</span></span>
<span data-ttu-id="5dca7-141">In diesem Fall zeigen die Befehle die Zufallszahl an, die bei Eintritt des Elapsed-Ereignisses generiert wird.</span><span class="sxs-lookup"><span data-stu-id="5dca7-141">In this case, the commands show the random number that is being generated when the Elapsed event occurs.</span></span>

<span data-ttu-id="5dca7-142">Weitere Informationen zu Modulen finden Sie unter [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="5dca7-142">For more information about modules, see [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

## <span data-ttu-id="5dca7-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5dca7-143">PARAMETERS</span></span>

### <span data-ttu-id="5dca7-144">-Force</span><span class="sxs-lookup"><span data-stu-id="5dca7-144">-Force</span></span>

<span data-ttu-id="5dca7-145">Gibt an, dass dieses Cmdlet alle Ereignis Abonnenten abruft, einschließlich Abonnenten für Ereignisse, die mit dem *supportevent* -Parameter von Register-ObjectEvent, Register-wmievent und Register-engineevent ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="5dca7-145">Indicates that this cmdlet gets all event subscribers, including subscribers for events that are hidden by using the *SupportEvent* parameter of Register-ObjectEvent, Register-WmiEvent, and Register-EngineEvent.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5dca7-146">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="5dca7-146">-SourceIdentifier</span></span>

<span data-ttu-id="5dca7-147">Gibt den **SourceIdentifier** -Eigenschafts Wert an, der nur die Ereignis Abonnenten abruft.</span><span class="sxs-lookup"><span data-stu-id="5dca7-147">Specifies the **SourceIdentifier** property value that gets only the event subscribers.</span></span>
<span data-ttu-id="5dca7-148">Standardmäßig ruft **Get-eventsubscriber** alle Ereignis Abonnenten in der Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="5dca7-148">By default, **Get-EventSubscriber** gets all event subscribers in the session.</span></span>
<span data-ttu-id="5dca7-149">Platzhalter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="5dca7-149">Wildcards are not permitted.</span></span>
<span data-ttu-id="5dca7-150">Bei diesem Parameter wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5dca7-150">This parameter is case-sensitive.</span></span>

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

### <span data-ttu-id="5dca7-151">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="5dca7-151">-SubscriptionId</span></span>

<span data-ttu-id="5dca7-152">Gibt den Abonnement Bezeichner an, der von diesem Cmdlet abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5dca7-152">Specifies the subscription identifier that this cmdlet gets.</span></span>
<span data-ttu-id="5dca7-153">Standardmäßig ruft **Get-eventsubscriber** alle Ereignis Abonnenten in der Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="5dca7-153">By default, **Get-EventSubscriber** gets all event subscribers in the session.</span></span>

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

### <span data-ttu-id="5dca7-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5dca7-154">CommonParameters</span></span>

<span data-ttu-id="5dca7-155">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5dca7-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5dca7-156">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5dca7-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5dca7-157">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5dca7-157">INPUTS</span></span>

### <span data-ttu-id="5dca7-158">Keine</span><span class="sxs-lookup"><span data-stu-id="5dca7-158">None</span></span>

<span data-ttu-id="5dca7-159">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="5dca7-159">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="5dca7-160">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5dca7-160">OUTPUTS</span></span>

### <span data-ttu-id="5dca7-161">System. Management. Automation. psiebziger Subscriber</span><span class="sxs-lookup"><span data-stu-id="5dca7-161">System.Management.Automation.PSEventSubscriber</span></span>

<span data-ttu-id="5dca7-162">**Get-eventsubscriber** gibt ein Objekt zurück, das die einzelnen Ereignis Abonnenten darstellt.</span><span class="sxs-lookup"><span data-stu-id="5dca7-162">**Get-EventSubscriber** returns an object that represents each event subscriber.</span></span>

## <span data-ttu-id="5dca7-163">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5dca7-163">NOTES</span></span>

* <span data-ttu-id="5dca7-164">Das New-Event-Cmdlet, durch das ein benutzerdefiniertes Ereignis erstellt wird, generiert keinen Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="5dca7-164">The New-Event cmdlet, which creates a custom event, does not generate a subscriber.</span></span> <span data-ttu-id="5dca7-165">Das **Get-eventsubscriber** -Cmdlet findet daher kein Abonnenten Objekt für diese Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="5dca7-165">Therefore, the **Get-EventSubscriber** cmdlet will not find a subscriber object for these events.</span></span> <span data-ttu-id="5dca7-166">Wenn Sie jedoch das Cmdlet "Register-EngineEvent" verwenden, um ein benutzerdefiniertes Ereignis zu abonnieren (um das Ereignis weiterzuleiten oder um eine Aktion anzugeben), findet **Get-eventsubscriber** den von **Register-engineevent** generierten Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="5dca7-166">However, if you use the Register-EngineEvent cmdlet to subscribe to a custom event (in order to forward the event or to specify an action), **Get-EventSubscriber** will find the subscriber that **Register-EngineEvent** generates.</span></span>

  <span data-ttu-id="5dca7-167">Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5dca7-167">Events, event subscriptions, and the event queue exist only in the current session.</span></span>
<span data-ttu-id="5dca7-168">Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="5dca7-168">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

*

## <span data-ttu-id="5dca7-169">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5dca7-169">RELATED LINKS</span></span>

[<span data-ttu-id="5dca7-170">Get-Event</span><span class="sxs-lookup"><span data-stu-id="5dca7-170">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="5dca7-171">New-Event</span><span class="sxs-lookup"><span data-stu-id="5dca7-171">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="5dca7-172">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="5dca7-172">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="5dca7-173">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="5dca7-173">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="5dca7-174">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="5dca7-174">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="5dca7-175">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="5dca7-175">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="5dca7-176">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="5dca7-176">Wait-Event</span></span>](Wait-Event.md)

