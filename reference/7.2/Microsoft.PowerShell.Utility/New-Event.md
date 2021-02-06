---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Event
ms.openlocfilehash: 86a4370caccb43edf62af75337afb15f3fb63d7c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602320"
---
# <span data-ttu-id="5b05c-102">New-Event</span><span class="sxs-lookup"><span data-stu-id="5b05c-102">New-Event</span></span>

## <span data-ttu-id="5b05c-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5b05c-103">SYNOPSIS</span></span>
<span data-ttu-id="5b05c-104">Erstellt ein neues Ereignis.</span><span class="sxs-lookup"><span data-stu-id="5b05c-104">Creates a new event.</span></span>

## <span data-ttu-id="5b05c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5b05c-105">SYNTAX</span></span>

```
New-Event [-SourceIdentifier] <String> [[-Sender] <PSObject>] [[-EventArguments] <PSObject[]>]
 [[-MessageData] <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="5b05c-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5b05c-106">DESCRIPTION</span></span>

<span data-ttu-id="5b05c-107">Das- `New-Event` Cmdlet erstellt ein neues benutzerdefiniertes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="5b05c-107">The `New-Event` cmdlet creates a new custom event.</span></span>

<span data-ttu-id="5b05c-108">Mit benutzerdefinierten Ereignissen können Sie die Benutzer über Statusänderungen in Ihrem Programm und jede Änderung benachrichtigen, die das Programm erkennen kann, einschließlich Hardware- oder Systembedingungen, Anwendungsstatus, Datenträgerstatus, Netzwerkstatus oder den Abschluss eines Auftrags im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="5b05c-108">You can use custom events to notify users about state changes in your program and any change that your program can detect, including hardware or system conditions, application status, disk status, network status, or the completion of a background job.</span></span>

<span data-ttu-id="5b05c-109">Benutzerdefinierte Ereignisse werden bei ihrer Auslösung automatisch der Warteschlange in der Sitzung hinzugefügt. Es ist kein Abonnement erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5b05c-109">Custom events are automatically added to the event queue in your session whenever they are raised; you do not need to subscribe to them.</span></span> <span data-ttu-id="5b05c-110">Wenn Sie ein Ereignis jedoch an die lokale Sitzung weiterleiten oder eine Aktion zur Reaktion auf das Ereignis angeben möchten, verwenden Sie das `Register-EngineEvent` Cmdlet, um das benutzerdefinierte Ereignis zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="5b05c-110">However, if you want to forward an event to the local session or specify an action to respond to the event, use the `Register-EngineEvent` cmdlet to subscribe to the custom event.</span></span>

<span data-ttu-id="5b05c-111">Wenn Sie ein benutzerdefiniertes Ereignis abonnieren, wird der Ereignisabonnent Ihrer Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5b05c-111">When you subscribe to a custom event, the event subscriber is added to your session.</span></span> <span data-ttu-id="5b05c-112">Wenn Sie das Ereignis Abonnement mithilfe des `Unregister-Event` Cmdlets abbrechen, werden der Ereignis Abonnent und das benutzerdefinierte Ereignis aus der Sitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="5b05c-112">If you cancel the event subscription by using the `Unregister-Event` cmdlet, the event subscriber and custom event are deleted from the session.</span></span> <span data-ttu-id="5b05c-113">Wenn Sie das benutzerdefinierte Ereignis nicht abonnieren, müssen Sie zum Löschen des Ereignisses die Programmbedingungen ändern oder die PowerShell-Sitzung schließen.</span><span class="sxs-lookup"><span data-stu-id="5b05c-113">If you do not subscribe to the custom event, to delete the event, you must change the program conditions or close the PowerShell session.</span></span>

## <span data-ttu-id="5b05c-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5b05c-114">EXAMPLES</span></span>

### <span data-ttu-id="5b05c-115">Beispiel 1: Erstellen eines neuen Ereignisses in der Ereignis Warteschlange</span><span class="sxs-lookup"><span data-stu-id="5b05c-115">Example 1: Create a new event in the event queue</span></span>

```
PS C:\> New-Event -SourceIdentifier Timer -Sender windows.timer -MessageData "Test"
```

<span data-ttu-id="5b05c-116">Dieser Befehl erstellt ein neues Ereignis in der PowerShell-Ereignis Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="5b05c-116">This command creates a new event in the PowerShell event queue.</span></span> <span data-ttu-id="5b05c-117">Er verwendet ein **Windows. Timer** -Objekt, um das Ereignis zu senden.</span><span class="sxs-lookup"><span data-stu-id="5b05c-117">It uses a **Windows.Timer** object to send the event.</span></span>

### <span data-ttu-id="5b05c-118">Beispiel 2: Ausführen eines Ereignisses als Reaktion auf ein anderes Ereignis</span><span class="sxs-lookup"><span data-stu-id="5b05c-118">Example 2: Raise an event in response to another event</span></span>

```
PS C:\> function Enable-ProcessCreationEvent
{
   $Query = New-Object System.Management.WqlEventQuery "__InstanceCreationEvent", (New-Object TimeSpan 0,0,1), "TargetInstance isa 'Win32_Process'"
   $ProcessWatcher = New-Object System.Management.ManagementEventWatcher $Query
   $Identifier = "WMI.ProcessCreated"
   Register-ObjectEvent $ProcessWatcher "EventArrived" -SupportEvent $Identifier -Action
   {
      [void] (New-Event -SourceID "PowerShell.ProcessCreated" -Sender $Args[0] -EventArguments $Args[1].SourceEventArgs.NewEvent.TargetInstance)
   }
}
```

<span data-ttu-id="5b05c-119">Diese Beispiel Funktion verwendet das- `New-Event` Cmdlet, um ein Ereignis als Reaktion auf ein anderes Ereignis aufzurichten.</span><span class="sxs-lookup"><span data-stu-id="5b05c-119">This sample function uses the `New-Event` cmdlet to raise an event in response to another event.</span></span> <span data-ttu-id="5b05c-120">Der Befehl verwendet das `Register-ObjectEvent` Cmdlet, um das Ereignis Windows-Verwaltungsinstrumentation (WMI) zu abonnieren, das beim Erstellen eines neuen Prozesses ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="5b05c-120">The command uses the `Register-ObjectEvent` cmdlet to subscribe to the Windows Management Instrumentation (WMI) event that is raised when a new process is created.</span></span> <span data-ttu-id="5b05c-121">Der Befehl verwendet den **Action** -Parameter des Cmdlets, um das `New-Event` Cmdlet aufzurufen, das das neue Ereignis erstellt.</span><span class="sxs-lookup"><span data-stu-id="5b05c-121">The command uses the **Action** parameter of the cmdlet to call the `New-Event` cmdlet, which creates the new event.</span></span>

<span data-ttu-id="5b05c-122">Da die `New-Event` ausgelösten Ereignisse automatisch zur PowerShell-Ereignis Warteschlange hinzugefügt werden, müssen Sie sich für dieses Ereignis nicht registrieren.</span><span class="sxs-lookup"><span data-stu-id="5b05c-122">Because the events that `New-Event` raises are automatically added to the PowerShell event queue, you do not need to register for that event.</span></span>

## <span data-ttu-id="5b05c-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5b05c-123">PARAMETERS</span></span>

### <span data-ttu-id="5b05c-124">-Eventarguments</span><span class="sxs-lookup"><span data-stu-id="5b05c-124">-EventArguments</span></span>

<span data-ttu-id="5b05c-125">Gibt ein Objekt an, das Optionen für das Ereignis enthält.</span><span class="sxs-lookup"><span data-stu-id="5b05c-125">Specifies an object that contains options for the event.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5b05c-126">-MessageData</span><span class="sxs-lookup"><span data-stu-id="5b05c-126">-MessageData</span></span>

<span data-ttu-id="5b05c-127">Gibt zusätzliche Daten an, die dem Ereignis zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5b05c-127">Specifies additional data associated with the event.</span></span> <span data-ttu-id="5b05c-128">Der Wert dieses Parameters wird in der **MessageData**-Eigenschaft des Ereignisobjekts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b05c-128">The value of this parameter appears in the **MessageData** property of the event object.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5b05c-129">-Absender</span><span class="sxs-lookup"><span data-stu-id="5b05c-129">-Sender</span></span>

<span data-ttu-id="5b05c-130">Gibt das Objekt an, das das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="5b05c-130">Specifies the object that raises the event.</span></span> <span data-ttu-id="5b05c-131">Der Standardwert ist das PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="5b05c-131">The default is the PowerShell engine.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5b05c-132">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="5b05c-132">-SourceIdentifier</span></span>

<span data-ttu-id="5b05c-133">Gibt einen Namen für das neue Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="5b05c-133">Specifies a name for the new event.</span></span> <span data-ttu-id="5b05c-134">Dieser Parameter ist erforderlich und muss in der Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="5b05c-134">This parameter is required, and it must be unique in the session.</span></span>

<span data-ttu-id="5b05c-135">Der Wert dieses Parameters wird in der **SourceIdentifier** -Eigenschaft der Ereignisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b05c-135">The value of this parameter appears in the **SourceIdentifier** property of the events.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5b05c-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5b05c-136">CommonParameters</span></span>

<span data-ttu-id="5b05c-137">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5b05c-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5b05c-138">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5b05c-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5b05c-139">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5b05c-139">INPUTS</span></span>

### <span data-ttu-id="5b05c-140">Keine</span><span class="sxs-lookup"><span data-stu-id="5b05c-140">None</span></span>

<span data-ttu-id="5b05c-141">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="5b05c-141">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="5b05c-142">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5b05c-142">OUTPUTS</span></span>

### <span data-ttu-id="5b05c-143">System. Management. Automation. psiebziger args</span><span class="sxs-lookup"><span data-stu-id="5b05c-143">System.Management.Automation.PSEventArgs</span></span>

## <span data-ttu-id="5b05c-144">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5b05c-144">NOTES</span></span>

<span data-ttu-id="5b05c-145">Auf den Linux-oder macOS-Plattformen sind keine Ereignis Quellen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5b05c-145">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="5b05c-146">Das neue benutzerdefinierte Ereignis, das Ereignisabonnement und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5b05c-146">The new custom event, the event subscription, and the event queue exist only in the current session.</span></span>
<span data-ttu-id="5b05c-147">Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="5b05c-147">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="5b05c-148">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5b05c-148">RELATED LINKS</span></span>

[<span data-ttu-id="5b05c-149">Get-Event</span><span class="sxs-lookup"><span data-stu-id="5b05c-149">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="5b05c-150">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="5b05c-150">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="5b05c-151">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="5b05c-151">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="5b05c-152">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="5b05c-152">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="5b05c-153">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="5b05c-153">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="5b05c-154">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="5b05c-154">Wait-Event</span></span>](Wait-Event.md)
