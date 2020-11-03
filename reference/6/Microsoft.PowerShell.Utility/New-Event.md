---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-event?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Event
ms.openlocfilehash: 6056861bc6b472e389939e446d922d2bc4302294
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216572"
---
# <span data-ttu-id="f7845-103">New-Event</span><span class="sxs-lookup"><span data-stu-id="f7845-103">New-Event</span></span>

## <span data-ttu-id="f7845-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f7845-104">SYNOPSIS</span></span>
<span data-ttu-id="f7845-105">Erstellt ein neues Ereignis.</span><span class="sxs-lookup"><span data-stu-id="f7845-105">Creates a new event.</span></span>

## <span data-ttu-id="f7845-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f7845-106">SYNTAX</span></span>

```
New-Event [-SourceIdentifier] <String> [[-Sender] <PSObject>] [[-EventArguments] <PSObject[]>]
 [[-MessageData] <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="f7845-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f7845-107">DESCRIPTION</span></span>

<span data-ttu-id="f7845-108">Das **New-Event-** Cmdlet erstellt ein neues benutzerdefiniertes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="f7845-108">The **New-Event** cmdlet creates a new custom event.</span></span>

<span data-ttu-id="f7845-109">Mit benutzerdefinierten Ereignissen können Sie die Benutzer über Statusänderungen in Ihrem Programm und jede Änderung benachrichtigen, die das Programm erkennen kann, einschließlich Hardware- oder Systembedingungen, Anwendungsstatus, Datenträgerstatus, Netzwerkstatus oder den Abschluss eines Auftrags im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="f7845-109">You can use custom events to notify users about state changes in your program and any change that your program can detect, including hardware or system conditions, application status, disk status, network status, or the completion of a background job.</span></span>

<span data-ttu-id="f7845-110">Benutzerdefinierte Ereignisse werden bei ihrer Auslösung automatisch der Warteschlange in der Sitzung hinzugefügt. Es ist kein Abonnement erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f7845-110">Custom events are automatically added to the event queue in your session whenever they are raised; you do not need to subscribe to them.</span></span>
<span data-ttu-id="f7845-111">Wenn Sie ein Ereignis jedoch an die lokale Sitzung weiterleiten oder eine Aktion zur Reaktion auf das Ereignis angeben möchten, verwenden Sie das Register-EngineEvent-Cmdlet, um das benutzerdefinierte Ereignis zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="f7845-111">However, if you want to forward an event to the local session or specify an action to respond to the event, use the Register-EngineEvent cmdlet to subscribe to the custom event.</span></span>

<span data-ttu-id="f7845-112">Wenn Sie ein benutzerdefiniertes Ereignis abonnieren, wird der Ereignisabonnent Ihrer Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f7845-112">When you subscribe to a custom event, the event subscriber is added to your session.</span></span>
<span data-ttu-id="f7845-113">Wenn Sie das Ereignisabonnement mithilfe des Unregister-Event-Cmdlets stornieren, werden der Ereignisabonnent und das benutzerdefinierte Ereignis aus der Sitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f7845-113">If you cancel the event subscription by using the Unregister-Event cmdlet, the event subscriber and custom event are deleted from the session.</span></span>
<span data-ttu-id="f7845-114">Wenn Sie das benutzerdefinierte Ereignis nicht abonnieren, müssen Sie zum Löschen des Ereignisses die Programmbedingungen ändern oder die PowerShell-Sitzung schließen.</span><span class="sxs-lookup"><span data-stu-id="f7845-114">If you do not subscribe to the custom event, to delete the event, you must change the program conditions or close the PowerShell session.</span></span>

## <span data-ttu-id="f7845-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f7845-115">EXAMPLES</span></span>

### <span data-ttu-id="f7845-116">Beispiel 1: Erstellen eines neuen Ereignisses in der Ereignis Warteschlange</span><span class="sxs-lookup"><span data-stu-id="f7845-116">Example 1: Create a new event in the event queue</span></span>

```
PS C:\> New-Event -SourceIdentifier Timer -Sender windows.timer -MessageData "Test"
```

<span data-ttu-id="f7845-117">Dieser Befehl erstellt ein neues Ereignis in der PowerShell-Ereignis Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="f7845-117">This command creates a new event in the PowerShell event queue.</span></span>
<span data-ttu-id="f7845-118">Er verwendet ein **Windows. Timer** -Objekt, um das Ereignis zu senden.</span><span class="sxs-lookup"><span data-stu-id="f7845-118">It uses a **Windows.Timer** object to send the event.</span></span>

### <span data-ttu-id="f7845-119">Beispiel 2: Ausführen eines Ereignisses als Reaktion auf ein anderes Ereignis</span><span class="sxs-lookup"><span data-stu-id="f7845-119">Example 2: Raise an event in response to another event</span></span>

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

<span data-ttu-id="f7845-120">Diese Beispiel Funktion verwendet das **New-Event-** Cmdlet, um ein Ereignis als Reaktion auf ein anderes Ereignis aufzurichten.</span><span class="sxs-lookup"><span data-stu-id="f7845-120">This sample function uses the **New-Event** cmdlet to raise an event in response to another event.</span></span>
<span data-ttu-id="f7845-121">Der Befehl verwendet das Register-ObjectEvent-Cmdlet zum Abonnieren des Ereignisses der Windows-Verwaltungsinstrumentation (WMI), das beim Erstellen eines neuen Prozesses ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f7845-121">The command uses the Register-ObjectEvent cmdlet to subscribe to the Windows Management Instrumentation (WMI) event that is raised when a new process is created.</span></span>
<span data-ttu-id="f7845-122">Der Befehl verwendet den *Action* -Parameter des Cmdlets, um das **New-Event-** Cmdlet aufzurufen, das das neue Ereignis erstellt.</span><span class="sxs-lookup"><span data-stu-id="f7845-122">The command uses the *Action* parameter of the cmdlet to call the **New-Event** cmdlet, which creates the new event.</span></span>

<span data-ttu-id="f7845-123">Da die von **New-Event ausgelösten** Ereignisse der PowerShell-Ereignis Warteschlange automatisch hinzugefügt werden, müssen Sie sich für dieses Ereignis nicht registrieren.</span><span class="sxs-lookup"><span data-stu-id="f7845-123">Because the events that **New-Event** raises are automatically added to the PowerShell event queue, you do not need to register for that event.</span></span>

## <span data-ttu-id="f7845-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f7845-124">PARAMETERS</span></span>

### <span data-ttu-id="f7845-125">-Eventarguments</span><span class="sxs-lookup"><span data-stu-id="f7845-125">-EventArguments</span></span>

<span data-ttu-id="f7845-126">Gibt ein Objekt an, das Optionen für das Ereignis enthält.</span><span class="sxs-lookup"><span data-stu-id="f7845-126">Specifies an object that contains options for the event.</span></span>

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

### <span data-ttu-id="f7845-127">-MessageData</span><span class="sxs-lookup"><span data-stu-id="f7845-127">-MessageData</span></span>

<span data-ttu-id="f7845-128">Gibt zusätzliche Daten an, die dem Ereignis zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f7845-128">Specifies additional data associated with the event.</span></span>
<span data-ttu-id="f7845-129">Der Wert dieses Parameters wird in der **MessageData** -Eigenschaft des Ereignisobjekts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7845-129">The value of this parameter appears in the **MessageData** property of the event object.</span></span>

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

### <span data-ttu-id="f7845-130">-Absender</span><span class="sxs-lookup"><span data-stu-id="f7845-130">-Sender</span></span>

<span data-ttu-id="f7845-131">Gibt das Objekt an, das das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="f7845-131">Specifies the object that raises the event.</span></span>
<span data-ttu-id="f7845-132">Der Standardwert ist das PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="f7845-132">The default is the PowerShell engine.</span></span>

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

### <span data-ttu-id="f7845-133">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="f7845-133">-SourceIdentifier</span></span>

<span data-ttu-id="f7845-134">Gibt einen Namen für das neue Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="f7845-134">Specifies a name for the new event.</span></span>
<span data-ttu-id="f7845-135">Dieser Parameter ist erforderlich und muss in der Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="f7845-135">This parameter is required, and it must be unique in the session.</span></span>

<span data-ttu-id="f7845-136">Der Wert dieses Parameters wird in der **SourceIdentifier** -Eigenschaft der Ereignisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7845-136">The value of this parameter appears in the **SourceIdentifier** property of the events.</span></span>

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

### <span data-ttu-id="f7845-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f7845-137">CommonParameters</span></span>

<span data-ttu-id="f7845-138">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f7845-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f7845-139">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f7845-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f7845-140">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f7845-140">INPUTS</span></span>

### <span data-ttu-id="f7845-141">Keine</span><span class="sxs-lookup"><span data-stu-id="f7845-141">None</span></span>

<span data-ttu-id="f7845-142">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="f7845-142">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="f7845-143">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f7845-143">OUTPUTS</span></span>

### <span data-ttu-id="f7845-144">System. Management. Automation. psiebziger args</span><span class="sxs-lookup"><span data-stu-id="f7845-144">System.Management.Automation.PSEventArgs</span></span>

## <span data-ttu-id="f7845-145">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f7845-145">NOTES</span></span>

<span data-ttu-id="f7845-146">Das neue benutzerdefinierte Ereignis, das Ereignisabonnement und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f7845-146">The new custom event, the event subscription, and the event queue exist only in the current session.</span></span> <span data-ttu-id="f7845-147">Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="f7845-147">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="f7845-148">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f7845-148">RELATED LINKS</span></span>

[<span data-ttu-id="f7845-149">Get-Event</span><span class="sxs-lookup"><span data-stu-id="f7845-149">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="f7845-150">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="f7845-150">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="f7845-151">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="f7845-151">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="f7845-152">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="f7845-152">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="f7845-153">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="f7845-153">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="f7845-154">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="f7845-154">Wait-Event</span></span>](Wait-Event.md)
