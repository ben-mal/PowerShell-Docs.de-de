---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-eventsubscriber?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventSubscriber
ms.openlocfilehash: b8f55770770fa9077f654d382818386cc480c638
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600703"
---
# <span data-ttu-id="7c4d3-102">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="7c4d3-102">Get-EventSubscriber</span></span>

## <span data-ttu-id="7c4d3-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7c4d3-103">SYNOPSIS</span></span>
<span data-ttu-id="7c4d3-104">Ruft die Ereignisabonnenten in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-104">Gets the event subscribers in the current session.</span></span>

## <span data-ttu-id="7c4d3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7c4d3-105">SYNTAX</span></span>

### <span data-ttu-id="7c4d3-106">Bysource (Standard)</span><span class="sxs-lookup"><span data-stu-id="7c4d3-106">BySource (Default)</span></span>

```
Get-EventSubscriber [[-SourceIdentifier] <String>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="7c4d3-107">ById</span><span class="sxs-lookup"><span data-stu-id="7c4d3-107">ById</span></span>

```
Get-EventSubscriber [-SubscriptionId] <Int32> [-Force] [<CommonParameters>]
```

## <span data-ttu-id="7c4d3-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c4d3-108">DESCRIPTION</span></span>

<span data-ttu-id="7c4d3-109">Das **Get-eventsubscriber** -Cmdlet ruft die Ereignis Abonnenten in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-109">The **Get-EventSubscriber** cmdlet gets the event subscribers in the current session.</span></span>

<span data-ttu-id="7c4d3-110">Wenn Sie ein Ereignis mithilfe eines Register Event-Cmdlets abonnieren, wird der PowerShell-Sitzung ein Ereignis Abonnent hinzugefügt, und die von Ihnen abonnierten Ereignisse werden ihrer Ereignis Warteschlange hinzugefügt, sobald sie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-110">When you subscribe to an event by using a Register event cmdlet, an event subscriber is added to your PowerShell session, and the events to which you subscribed are added to your event queue whenever they are raised.</span></span>
<span data-ttu-id="7c4d3-111">Um ein Ereignisabonnement zu stornieren, löschen Sie den Ereignisabonnenten mithilfe des Unregister-Event-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-111">To cancel an event subscription, delete the event subscriber by using the Unregister-Event cmdlet.</span></span>

## <span data-ttu-id="7c4d3-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7c4d3-112">EXAMPLES</span></span>

### <span data-ttu-id="7c4d3-113">Beispiel 1: erhalten des Ereignis Abonnenten für ein Zeit Geber Ereignis</span><span class="sxs-lookup"><span data-stu-id="7c4d3-113">Example 1: Get the event subscriber for a timer event</span></span>

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

<span data-ttu-id="7c4d3-114">In diesem Beispiel wird ein **Get-eventsubscriber** -Befehl verwendet, um den Ereignis Abonnenten für ein Zeit Geber Ereignis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-114">This example uses a **Get-EventSubscriber** command to get the event subscriber for a timer event.</span></span>

<span data-ttu-id="7c4d3-115">Der erste Befehl verwendet das New-Object-Cmdlet, um eine Instanz eines Zeitgeberobjekts zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-115">The first command uses the New-Object cmdlet to create an instance of a timer object.</span></span>
<span data-ttu-id="7c4d3-116">Das neue Timer-Objekt wird in der $Timer-Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-116">It saves the new timer object in the $Timer variable.</span></span>

<span data-ttu-id="7c4d3-117">Der zweite Befehl verwendet das Get-Member-Cmdlet, um die für Zeitgeberobjekte verfügbaren Ereignisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-117">The second command uses the Get-Member cmdlet to display the events that are available for timer objects.</span></span>
<span data-ttu-id="7c4d3-118">Der Befehl verwendet den Type-Parameter des Cmdlets " **Get-Member** " mit dem Wert "Event".</span><span class="sxs-lookup"><span data-stu-id="7c4d3-118">The command uses the Type parameter of the **Get-Member** cmdlet with a value of Event.</span></span>

<span data-ttu-id="7c4d3-119">Der dritte Befehl verwendet das Register-ObjectEvent-Cmdlet, um sich für das Elapsed-Ereignis des Zeitgeberobjekts zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-119">The third command uses the Register-ObjectEvent cmdlet to register for the Elapsed event on the timer object.</span></span>

<span data-ttu-id="7c4d3-120">Der vierte Befehl verwendet das **Get-eventsubscriber** -Cmdlet, um den Ereignis Abonnenten für das verstrichene Ereignis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-120">The fourth command uses the **Get-EventSubscriber** cmdlet to get the event subscriber for the Elapsed event.</span></span>

### <span data-ttu-id="7c4d3-121">Beispiel 2: Verwenden des dynamischen Moduls in psiebziger Job in der Action-Eigenschaft des Ereignis Abonnenten</span><span class="sxs-lookup"><span data-stu-id="7c4d3-121">Example 2: Use the dynamic module in PSEventJob in the Action property of the event subscriber</span></span>

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

<span data-ttu-id="7c4d3-122">Dieses Beispiel zeigt, wie Sie das dynamische Modul im **psiebziger Job** -Objekt in der Action-Eigenschaft des Ereignis Abonnenten verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-122">This example shows how to use the dynamic module in the **PSEventJob** object in the Action property of the event subscriber.</span></span>

<span data-ttu-id="7c4d3-123">Der erste Befehl verwendet das New-Object-Cmdlet, um ein Zeitgeberobjekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-123">The first command uses the New-Object cmdlet to create a timer object.</span></span>
<span data-ttu-id="7c4d3-124">Der zweite Befehl legt das Intervall des Zeitgebers auf 500 (Millisekunden) fest.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-124">The second command sets the interval of the timer to 500 (milliseconds).</span></span>

<span data-ttu-id="7c4d3-125">Der dritte Befehl verwendet das Register-ObjectEvent-Cmdlet, um sich für das Elapsed-Ereignis des Zeitgeberobjekts zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-125">The third command uses the Register-ObjectEvent cmdlet to register the Elapsed event of the timer object.</span></span>
<span data-ttu-id="7c4d3-126">Der Befehl enthält eine Aktion zur Behandlung des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-126">The command includes an action that handles the event.</span></span>
<span data-ttu-id="7c4d3-127">Wenn das Zeitgeberintervall abläuft, wird ein Ereignis ausgelöst, und die Befehle in der Aktion werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-127">Whenever the timer interval elapses, an event is raised and the commands in the action run.</span></span>
<span data-ttu-id="7c4d3-128">In diesem Fall generiert das Cmdlet "Get-Random" eine Zufallszahl zwischen 0 und 100 und speichert Sie in der $Random-Variablen.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-128">In this case, the Get-Random cmdlet generates a random number between 0 and 100 and saves it in the $Random variable.</span></span>
<span data-ttu-id="7c4d3-129">Der Quellbezeichner des Ereignisses ist Timer.Random.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-129">The source identifier of the event is Timer.Random.</span></span>

<span data-ttu-id="7c4d3-130">Wenn Sie einen *Action* -Parameter in einem **Register-ObjectEvent-** Befehl verwenden, gibt der Befehl ein **psiebziger Job** -Objekt zurück, das die Aktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-130">When you use an *Action* parameter in a **Register-ObjectEvent** command, the command returns a **PSEventJob** object that represents the action.</span></span>

<span data-ttu-id="7c4d3-131">Der vierte Befehl aktiviert den Zeitgeber.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-131">The fourth command enables the timer.</span></span>

<span data-ttu-id="7c4d3-132">Der fünfte Befehl verwendet das **Get-eventsubscriber** -Cmdlet, um den Ereignis Abonnenten des Timer. Random-Ereignisses zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-132">The fifth command uses the **Get-EventSubscriber** cmdlet to get the event subscriber of the Timer.Random event.</span></span>
<span data-ttu-id="7c4d3-133">Das Ereignis Abonnenten Objekt wird in der $Subscriber Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-133">It saves the event subscriber object in the $Subscriber variable.</span></span>

<span data-ttu-id="7c4d3-134">Der sechste Befehl zeigt, dass die Action-Eigenschaft des Ereignis Abonnenten Objekts ein **peventjob** -Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-134">The sixth command shows that the Action property of the event subscriber object contains a **PSEventJob** object.</span></span>
<span data-ttu-id="7c4d3-135">Tatsächlich enthält Sie das gleiche **psiebziger Job** -Objekt, das vom **Register-ObjectEvent** -Befehl zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-135">In fact, it contains the same **PSEventJob** object that the **Register-ObjectEvent** command returned.</span></span>

<span data-ttu-id="7c4d3-136">Der siebte Befehl verwendet das Cmdlet "Format-List", um alle Eigenschaften des **psiebziger Job** -Objekts in der Action-Eigenschaft in einer Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-136">The seventh command uses the Format-List cmdlet to display all of the properties of the **PSEventJob** object in the Action property in a list.</span></span>
<span data-ttu-id="7c4d3-137">Das Ergebnis zeigt, dass das **psiebziger Job** -Objekt über eine Module-Eigenschaft verfügt, die ein dynamisches Skript Modul enthält, das die Aktion implementiert.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-137">The result reveals that the **PSEventJob** object has a Module property that contains a dynamic script module that implements the action.</span></span>

<span data-ttu-id="7c4d3-138">Die übrigen Befehle verwenden den Aufruf Operator (&), um den Befehl im Modul aufzurufen und den Wert der $Random Variablen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-138">The remaining commands use the call operator (&) to invoke the command in the module and display the value of the $Random variable.</span></span>
<span data-ttu-id="7c4d3-139">Mit dem Aufrufoperator können Sie einen beliebigen Befehl in einem Modul aufrufen, einschließlich nicht exportierter Befehle.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-139">You can use the call operator to invoke any command in a module, including commands that are not exported.</span></span>
<span data-ttu-id="7c4d3-140">In diesem Fall zeigen die Befehle die Zufallszahl an, die bei Eintritt des Elapsed-Ereignisses generiert wird.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-140">In this case, the commands show the random number that is being generated when the Elapsed event occurs.</span></span>

<span data-ttu-id="7c4d3-141">Weitere Informationen zu Modulen finden Sie unter [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="7c4d3-141">For more information about modules, see [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

## <span data-ttu-id="7c4d3-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7c4d3-142">PARAMETERS</span></span>

### <span data-ttu-id="7c4d3-143">-Force</span><span class="sxs-lookup"><span data-stu-id="7c4d3-143">-Force</span></span>

<span data-ttu-id="7c4d3-144">Gibt an, dass dieses Cmdlet alle Ereignis Abonnenten abruft, einschließlich Abonnenten für Ereignisse, die mit dem *supportevent* -Parameter von Register-ObjectEvent, Register-wmievent und Register-engineevent ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-144">Indicates that this cmdlet gets all event subscribers, including subscribers for events that are hidden by using the *SupportEvent* parameter of Register-ObjectEvent, Register-WmiEvent, and Register-EngineEvent.</span></span>

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

### <span data-ttu-id="7c4d3-145">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="7c4d3-145">-SourceIdentifier</span></span>

<span data-ttu-id="7c4d3-146">Gibt den **SourceIdentifier** -Eigenschafts Wert an, der nur die Ereignis Abonnenten abruft.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-146">Specifies the **SourceIdentifier** property value that gets only the event subscribers.</span></span>
<span data-ttu-id="7c4d3-147">Standardmäßig ruft **Get-eventsubscriber** alle Ereignis Abonnenten in der Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-147">By default, **Get-EventSubscriber** gets all event subscribers in the session.</span></span>
<span data-ttu-id="7c4d3-148">Platzhalter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-148">Wildcards are not permitted.</span></span>
<span data-ttu-id="7c4d3-149">Bei diesem Parameter wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-149">This parameter is case-sensitive.</span></span>

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

### <span data-ttu-id="7c4d3-150">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="7c4d3-150">-SubscriptionId</span></span>

<span data-ttu-id="7c4d3-151">Gibt den Abonnement Bezeichner an, der von diesem Cmdlet abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-151">Specifies the subscription identifier that this cmdlet gets.</span></span>
<span data-ttu-id="7c4d3-152">Standardmäßig ruft **Get-eventsubscriber** alle Ereignis Abonnenten in der Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-152">By default, **Get-EventSubscriber** gets all event subscribers in the session.</span></span>

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

### <span data-ttu-id="7c4d3-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7c4d3-153">CommonParameters</span></span>

<span data-ttu-id="7c4d3-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7c4d3-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7c4d3-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7c4d3-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7c4d3-156">INPUTS</span></span>

### <span data-ttu-id="7c4d3-157">Keine</span><span class="sxs-lookup"><span data-stu-id="7c4d3-157">None</span></span>

<span data-ttu-id="7c4d3-158">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-158">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="7c4d3-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7c4d3-159">OUTPUTS</span></span>

### <span data-ttu-id="7c4d3-160">System. Management. Automation. psiebziger Subscriber</span><span class="sxs-lookup"><span data-stu-id="7c4d3-160">System.Management.Automation.PSEventSubscriber</span></span>

<span data-ttu-id="7c4d3-161">**Get-eventsubscriber** gibt ein Objekt zurück, das die einzelnen Ereignis Abonnenten darstellt.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-161">**Get-EventSubscriber** returns an object that represents each event subscriber.</span></span>

## <span data-ttu-id="7c4d3-162">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7c4d3-162">NOTES</span></span>

* <span data-ttu-id="7c4d3-163">Das New-Event-Cmdlet, durch das ein benutzerdefiniertes Ereignis erstellt wird, generiert keinen Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-163">The New-Event cmdlet, which creates a custom event, does not generate a subscriber.</span></span> <span data-ttu-id="7c4d3-164">Das **Get-eventsubscriber** -Cmdlet findet daher kein Abonnenten Objekt für diese Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-164">Therefore, the **Get-EventSubscriber** cmdlet will not find a subscriber object for these events.</span></span> <span data-ttu-id="7c4d3-165">Wenn Sie jedoch das Cmdlet "Register-EngineEvent" verwenden, um ein benutzerdefiniertes Ereignis zu abonnieren (um das Ereignis weiterzuleiten oder um eine Aktion anzugeben), findet **Get-eventsubscriber** den von **Register-engineevent** generierten Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-165">However, if you use the Register-EngineEvent cmdlet to subscribe to a custom event (in order to forward the event or to specify an action), **Get-EventSubscriber** will find the subscriber that **Register-EngineEvent** generates.</span></span>

  <span data-ttu-id="7c4d3-166">Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-166">Events, event subscriptions, and the event queue exist only in the current session.</span></span>
<span data-ttu-id="7c4d3-167">Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="7c4d3-167">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

*

## <span data-ttu-id="7c4d3-168">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7c4d3-168">RELATED LINKS</span></span>

[<span data-ttu-id="7c4d3-169">Get-Event</span><span class="sxs-lookup"><span data-stu-id="7c4d3-169">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="7c4d3-170">New-Event</span><span class="sxs-lookup"><span data-stu-id="7c4d3-170">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="7c4d3-171">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="7c4d3-171">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="7c4d3-172">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="7c4d3-172">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="7c4d3-173">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="7c4d3-173">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="7c4d3-174">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="7c4d3-174">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="7c4d3-175">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="7c4d3-175">Wait-Event</span></span>](Wait-Event.md)

