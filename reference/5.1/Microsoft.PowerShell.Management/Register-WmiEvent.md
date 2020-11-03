---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 07/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/register-wmievent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-WmiEvent
ms.openlocfilehash: be29ce6376dea7686c0c063cc5528fbc7d840a9d
ms.sourcegitcommit: 41b072f0b6046d619b0e7f758982783fb648a3d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2020
ms.locfileid: "93219047"
---
# <span data-ttu-id="ef6fc-103">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="ef6fc-103">Register-WmiEvent</span></span>

## <span data-ttu-id="ef6fc-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ef6fc-104">SYNOPSIS</span></span>
<span data-ttu-id="ef6fc-105">Abonniert ein Ereignis der Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-105">Subscribes to a Windows Management Instrumentation (WMI) event.</span></span>

## <span data-ttu-id="ef6fc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ef6fc-106">SYNTAX</span></span>

### <span data-ttu-id="ef6fc-107">Class (Standard)</span><span class="sxs-lookup"><span data-stu-id="ef6fc-107">class (Default)</span></span>

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Class] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="ef6fc-108">Abfrage</span><span class="sxs-lookup"><span data-stu-id="ef6fc-108">query</span></span>

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Query] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="ef6fc-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ef6fc-109">DESCRIPTION</span></span>

<span data-ttu-id="ef6fc-110">Das- `Register-WmiEvent` Cmdlet abonniert Windows-Verwaltungsinstrumentation (WMI)-Ereignisse auf dem lokalen Computer oder auf einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-110">The `Register-WmiEvent` cmdlet subscribes to Windows Management Instrumentation (WMI) events on the local computer or on a remote computer.</span></span>

<span data-ttu-id="ef6fc-111">Wenn das abonnierte WMI-Ereignis ausgelöst wird, wird es der Ereigniswarteschlange in der lokalen Sitzung hinzugefügt, auch wenn das Ereignis auf einem Remotecomputer eintritt.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-111">When the subscribed WMI event is raised, it is added to the event queue in your local session even if the event occurs on a remote computer.</span></span> <span data-ttu-id="ef6fc-112">Verwenden Sie das-Cmdlet, um Ereignisse in der Ereignis Warteschlange zu erhalten `Get-Event` .</span><span class="sxs-lookup"><span data-stu-id="ef6fc-112">To get events in the event queue, use the `Get-Event` cmdlet.</span></span>

<span data-ttu-id="ef6fc-113">Sie können die Parameter von verwenden `Register-WmiEvent` , um Ereignisse auf Remote Computern zu abonnieren und die Eigenschaftswerte der Ereignisse anzugeben, mit deren Hilfe Sie das Ereignis in der Warteschlange identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-113">You can use the parameters of `Register-WmiEvent` to subscribe to events on remote computers and to specify the property values of the events that can help you identify the event in the queue.</span></span> <span data-ttu-id="ef6fc-114">Sie können auch den **Action** -Parameter verwenden, um Aktionen anzugeben, die ausgeführt werden, wenn ein abonnierte Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-114">You can also use the **Action** parameter to specify actions to take when a subscribed event is raised.</span></span>

<span data-ttu-id="ef6fc-115">Wenn Sie ein Ereignis abonnieren, wird der Sitzung ein Ereignisabonnent hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-115">When you subscribe to an event, an event subscriber is added to your session.</span></span> <span data-ttu-id="ef6fc-116">Rufen Sie die Ereignisabonnenten in der Sitzung mithilfe des Cmdlets `Get-EventSubscriber` ab.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-116">To get the event subscribers in the session, use the `Get-EventSubscriber` cmdlet.</span></span> <span data-ttu-id="ef6fc-117">Brechen Sie das Abonnement mit dem Cmdlet `Unregister-Event` ab, wodurch die Ereignisabonnenten aus der Sitzung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-117">To cancel the subscription, use the `Unregister-Event` cmdlet, which deletes the event subscriber from the session.</span></span>

<span data-ttu-id="ef6fc-118">Die neuen Common Information Model (CIM)-Cmdlets, die Windows PowerShell 3,0 eingeführt haben, führen dieselben Aufgaben wie die WMI-Cmdlets aus.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-118">New Common Information Model (CIM) cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="ef6fc-119">Die CIM-Cmdlets entsprechen den WS-Management (WSMAN)-Standards und dem CIM-Standard. Dadurch können die Cmdlets dieselben Verfahren zum Verwalten von Computern verwenden, auf denen das Windows-Betriebssystem ausgeführt wird, und auf denen andere Betriebssysteme ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-119">The CIM cmdlets comply with WS-Management (WSMan) standards and with the CIM standard, which enables the cmdlets to use the same techniques to manage computers that run the Windows operating system and those that run other operating systems.</span></span> <span data-ttu-id="ef6fc-120">Anstatt zu verwenden `Register-WmiEvent` , sollten Sie das Cmdlet [Register-cimindikticmdlet](../cimcmdlets/register-cimindicationevent.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-120">Instead of using `Register-WmiEvent`, consider using the [Register-CimIndicationEvent](../cimcmdlets/register-cimindicationevent.md) cmdlet.</span></span>

## <span data-ttu-id="ef6fc-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ef6fc-121">EXAMPLES</span></span>

### <span data-ttu-id="ef6fc-122">Beispiel 1: Abonnieren von Ereignissen, die von einer Klasse generiert wurden</span><span class="sxs-lookup"><span data-stu-id="ef6fc-122">Example 1: Subscribe to events generated by a class</span></span>

<span data-ttu-id="ef6fc-123">Dieser Befehl abonniert die Ereignisse, die von der **Win32_ProcessStartTrace** -Klasse generiert werden.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-123">This command subscribes to the events generated by the **Win32_ProcessStartTrace** class.</span></span> <span data-ttu-id="ef6fc-124">Diese Klasse löst immer dann ein Ereignis aus, wenn ein Prozess gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-124">This class raises an event whenever a process starts.</span></span>

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted"
```

### <span data-ttu-id="ef6fc-125">Beispiel 2: Abonnieren von Erstellungs Ereignissen für einen Prozess</span><span class="sxs-lookup"><span data-stu-id="ef6fc-125">Example 2: Subscribe to creation events for a process</span></span>

<span data-ttu-id="ef6fc-126">In diesem Befehl werden Win32_process-Instanzerstellungsereignisse mithilfe einer Abfrage abonniert.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-126">This command uses a query to subscribe to Win32_process instance creation events.</span></span>

```powershell
$wmiParameters = @{
  Query = "select * from __instancecreationevent within 5 where targetinstance isa 'win32_process'"
  SourceIdentifier = "WMIProcess"
  MessageData = "Test 01"
  TimeOut = 500
}
Register-WmiEvent @wmiParameters
```

### <span data-ttu-id="ef6fc-127">Beispiel 3: Verwenden Sie eine Aktion, um auf ein Ereignis zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-127">Example 3: Use an action to respond to an event</span></span>

<span data-ttu-id="ef6fc-128">In diesem Beispiel wird die Verwendung einer Aktion als Antwort auf ein Ereignis veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-128">This example shows how to use an action to respond to an event.</span></span> <span data-ttu-id="ef6fc-129">In diesem Fall `Start-Process` werden alle Befehle in der aktuellen Sitzung in eine XML-Datei geschrieben, wenn ein Prozess gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-129">In this case, when a process starts, any `Start-Process` commands in the current session are written to an XML file.</span></span>

```powershell
$action = { Get-History | where { $_.commandline -like "*start-process*" } | export-cliXml "commandHistory.clixml" }
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -Action $action
```

```Output
Id    Name            State      HasMoreData   Location  Command
--    ----            -----      -----------   --------  -------
1     ProcessStarted  NotStarted False                   get-history | where {...
```

<span data-ttu-id="ef6fc-130">Wenn Sie den **Action** -Parameter verwenden, `Register-WmiEvent` gibt einen Hintergrund Auftrag zurück, der die Ereignis Aktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-130">When you use the **Action** parameter, `Register-WmiEvent` returns a background job that represents the event action.</span></span> <span data-ttu-id="ef6fc-131">Sie können die **Job** -Cmdlets wie und verwenden `Get-Job` `Receive-Job` , um den Ereignis Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-131">You can use the **Job** cmdlets, such as `Get-Job` and `Receive-Job`, to manage the event job.</span></span>

<span data-ttu-id="ef6fc-132">Weitere Informationen finden Sie unter %%amp;quot;about_Jobs%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-132">For more information, see about_Jobs.</span></span>

### <span data-ttu-id="ef6fc-133">Beispiel 4: Registrieren für Ereignisse auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="ef6fc-133">Example 4: Register for events on a remote computer</span></span>

<span data-ttu-id="ef6fc-134">In diesem Beispiel werden Ereignisse auf dem Remotecomputer %%amp;quot;Server01%%amp;quot; registriert.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-134">This example registers for events on the Server01 remote computer.</span></span>

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "Start" -Computername Server01
Get-Event -SourceIdentifier "Start"
```

<span data-ttu-id="ef6fc-135">WMI gibt die Ereignisse an den lokalen Computer zurück und speichert sie in der Ereigniswarteschlange in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-135">WMI returns the events to the local computer and stores them in the event queue in the current session.</span></span> <span data-ttu-id="ef6fc-136">Um die Ereignisse abzurufen, führen Sie einen lokalen `Get-Event` Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-136">To retrieve the events, run a local `Get-Event` command.</span></span>

## <span data-ttu-id="ef6fc-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ef6fc-137">PARAMETERS</span></span>

### <span data-ttu-id="ef6fc-138">-Action</span><span class="sxs-lookup"><span data-stu-id="ef6fc-138">-Action</span></span>

<span data-ttu-id="ef6fc-139">Gibt Befehle an, die die Ereignisse behandeln.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-139">Specifies commands that handle the events.</span></span> <span data-ttu-id="ef6fc-140">Die Befehle im **Action** -Parameter werden ausgeführt, wenn ein Ereignis ausgelöst wird, anstatt das Ereignis an die Ereignis Warteschlange zu senden.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-140">The commands in the **Action** parameter run when an event is raised instead of sending the event to the event queue.</span></span> <span data-ttu-id="ef6fc-141">Schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein, um einen Skriptblock zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-141">Enclose the commands in braces (`{}`) to create a script block.</span></span>

<span data-ttu-id="ef6fc-142">Der Wert der **Aktion** kann die `$Event` `$EventSubscriber` automatischen Variablen,,, `$Sender` und enthalten `$EventArgs` `$Args` , die dem **Aktions** Skriptblock Informationen zum Ereignis bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-142">The value of **Action** can include the `$Event`, `$EventSubscriber`, `$Sender`, `$EventArgs`, and `$Args` automatic variables, which provide information about the event to the **Action** script block.</span></span> <span data-ttu-id="ef6fc-143">Weitere Informationen finden Sie unter %%amp;quot;about_Automatic_Variables%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-143">For more information, see about_Automatic_Variables.</span></span>

<span data-ttu-id="ef6fc-144">Wenn Sie eine Aktion angeben, `Register-WmiEvent` gibt ein Ereignis Auftrags Objekt zurück, das diese Aktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-144">When you specify an action, `Register-WmiEvent` returns an event job object that represents that action.</span></span> <span data-ttu-id="ef6fc-145">Sie können die-Cmdlets verwenden, die das **Auftrags** Substantiv (die **Job** -Cmdlets) enthalten, um den Ereignis Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-145">You can use the cmdlets that contain the **Job** noun (the **Job** cmdlets) to manage the event job.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: 101
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef6fc-146">-Klasse</span><span class="sxs-lookup"><span data-stu-id="ef6fc-146">-Class</span></span>

<span data-ttu-id="ef6fc-147">Gibt das Ereignis an, das Sie abonnieren.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-147">Specifies the event to which you are subscribing.</span></span> <span data-ttu-id="ef6fc-148">Geben Sie die WMI-Klasse ein, die die Ereignisse generiert.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-148">Enter the WMI class that generates the events.</span></span> <span data-ttu-id="ef6fc-149">Ein **Class** -oder **Query** -Parameter ist in jedem Befehl erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-149">A **Class** or **Query** parameter is required in every command.</span></span>

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef6fc-150">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="ef6fc-150">-ComputerName</span></span>

<span data-ttu-id="ef6fc-151">Gibt den Namen des Computers an, auf dem der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-151">Specifies the name of the computer on which the command runs.</span></span> <span data-ttu-id="ef6fc-152">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-152">The default is the local computer.</span></span>

<span data-ttu-id="ef6fc-153">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen des Computers ein.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-153">Type the NetBIOS name, an IP address, or a fully qualified domain name of the computer.</span></span> <span data-ttu-id="ef6fc-154">Geben Sie den Computernamen, einen Punkt () oder einen localhost ein, um den lokalen Computer anzugeben `.` .</span><span class="sxs-lookup"><span data-stu-id="ef6fc-154">To specify the local computer, type the computer name, a dot (`.`), or localhost.</span></span>

<span data-ttu-id="ef6fc-155">Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-155">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="ef6fc-156">Sie können den **ComputerName** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remotebefehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-156">You can use the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef6fc-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="ef6fc-157">-Credential</span></span>

<span data-ttu-id="ef6fc-158">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-158">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="ef6fc-159">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-159">The default is the current user.</span></span>

<span data-ttu-id="ef6fc-160">Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-160">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="ef6fc-161">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-161">If you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef6fc-162">-Vorwärts</span><span class="sxs-lookup"><span data-stu-id="ef6fc-162">-Forward</span></span>

<span data-ttu-id="ef6fc-163">Gibt an, dass dieses Cmdlet Ereignisse für dieses Abonnement an die Sitzung auf dem lokalen Computer sendet.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-163">Indicates that this cmdlet sends events for this subscription to the session on the local computer.</span></span>
<span data-ttu-id="ef6fc-164">Verwenden Sie diesen Parameter, wenn Sie sich auf einem Remotecomputer oder in einer Remotesitzung für Ereignisse registrieren.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-164">Use this parameter when you are registering for events on a remote computer or in a remote session.</span></span>

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

### <span data-ttu-id="ef6fc-165">-Maxtriggercount</span><span class="sxs-lookup"><span data-stu-id="ef6fc-165">-MaxTriggerCount</span></span>

<span data-ttu-id="ef6fc-166">Gibt die maximale Anzahl von Auslösers an.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-166">Specifies the maximum trigger count.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef6fc-167">-MessageData</span><span class="sxs-lookup"><span data-stu-id="ef6fc-167">-MessageData</span></span>

<span data-ttu-id="ef6fc-168">Gibt alle weiteren Daten an, die diesem Ereignisabonnement zugeordnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-168">Specifies any additional data to be associated with this event subscription.</span></span> <span data-ttu-id="ef6fc-169">Der Wert dieses Parameters wird in der **messageData** -Eigenschaft aller diesem Abonnement zugeordneten Ereignisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-169">The value of this parameter appears in the **MessageData** property of all events associated with this subscription.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef6fc-170">-Namespace</span><span class="sxs-lookup"><span data-stu-id="ef6fc-170">-Namespace</span></span>

<span data-ttu-id="ef6fc-171">Gibt den Namespace der WMI-Klasse an.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-171">Specifies the namespace of the WMI class.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef6fc-172">-Query</span><span class="sxs-lookup"><span data-stu-id="ef6fc-172">-Query</span></span>

<span data-ttu-id="ef6fc-173">Gibt eine Abfrage in WMI-Abfragesprache (WQL) an, die die WMI-Ereignisklasse identifiziert, z `select * from __InstanceDeletionEvent` . b.:.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-173">Specifies a query in WMI Query Language (WQL) that identifies the WMI event class, such as: `select * from __InstanceDeletionEvent`.</span></span>

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef6fc-174">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="ef6fc-174">-SourceIdentifier</span></span>

<span data-ttu-id="ef6fc-175">Gibt einen Namen an, den Sie für das Abonnement auswählen.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-175">Specifies a name that you select for the subscription.</span></span> <span data-ttu-id="ef6fc-176">Der von Ihnen ausgewählte Name muss in der aktuellen Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-176">The name that you select must be unique in the current session.</span></span> <span data-ttu-id="ef6fc-177">Der Standardwert ist die von Windows PowerShell zugewiesene GUID.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-177">The default value is the GUID that Windows PowerShell assigns.</span></span>

<span data-ttu-id="ef6fc-178">Der Wert dieses Parameters wird im Wert der **SourceIdentifier** -Eigenschaft des Abonnentenobjekts und aller diesem Abonnement zugeordneten Ereignisobjekte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-178">The value of this parameter appears in the value of the **SourceIdentifier** property of the subscriber object and of all event objects associated with this subscription.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef6fc-179">-Supportevent</span><span class="sxs-lookup"><span data-stu-id="ef6fc-179">-SupportEvent</span></span>

<span data-ttu-id="ef6fc-180">Gibt an, dass dieses Cmdlet das Ereignis Abonnement verbirgt.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-180">Indicates that this cmdlet hides the event subscription.</span></span> <span data-ttu-id="ef6fc-181">Verwenden Sie diesen Parameter, wenn das aktuelle Abonnement Teil eines komplexeren Ereignisregistrierungsmechanismus ist und nicht unabhängig erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-181">Use this parameter when the current subscription is part of a more complex event registration mechanism and it should not be discovered independently.</span></span>

<span data-ttu-id="ef6fc-182">Um ein Abonnement anzuzeigen oder abzubrechen, das mit dem **supportevent** -Parameter erstellt wurde, geben Sie den **Force** -Parameter der `Get-EventSubscriber` -und- `Unregister-Event` Cmdlets an.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-182">To view or cancel a subscription that was created by using the **SupportEvent** parameter, specify the **Force** parameter of the `Get-EventSubscriber` and `Unregister-Event` cmdlets.</span></span>

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

### <span data-ttu-id="ef6fc-183">-Timeout</span><span class="sxs-lookup"><span data-stu-id="ef6fc-183">-Timeout</span></span>

<span data-ttu-id="ef6fc-184">Gibt an, wie lange Windows PowerShell auf den Abschluss dieses Befehls wartet.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-184">Specifies how long Windows PowerShell waits for this command to finish.</span></span>

<span data-ttu-id="ef6fc-185">Der Standardwert %%amp;quot;0%%amp;quot; (null) bedeutet, dass kein Timeout vorliegt und Windows PowerShell unbegrenzt wartet.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-185">The default value, 0 (zero), means that there is no time-out, and it causes Windows PowerShell to wait indefinitely.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: TimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef6fc-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ef6fc-186">CommonParameters</span></span>

<span data-ttu-id="ef6fc-187">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ef6fc-188">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ef6fc-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ef6fc-189">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ef6fc-189">INPUTS</span></span>

### <span data-ttu-id="ef6fc-190">Keine</span><span class="sxs-lookup"><span data-stu-id="ef6fc-190">None</span></span>

<span data-ttu-id="ef6fc-191">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-191">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="ef6fc-192">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ef6fc-192">OUTPUTS</span></span>

### <span data-ttu-id="ef6fc-193">Keine</span><span class="sxs-lookup"><span data-stu-id="ef6fc-193">None</span></span>

<span data-ttu-id="ef6fc-194">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-194">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ef6fc-195">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ef6fc-195">NOTES</span></span>

<span data-ttu-id="ef6fc-196">Wenn Sie dieses Cmdlet in Windows Vista oder einer neueren Version des Windows-Betriebssystems verwenden möchten, starten Sie Windows PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-196">To use this cmdlet in Windows Vista or a later version of the Windows operating system, start Windows PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="ef6fc-197">Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-197">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="ef6fc-198">Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="ef6fc-198">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="ef6fc-199">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ef6fc-199">RELATED LINKS</span></span>
