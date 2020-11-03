---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 3/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventLog
ms.openlocfilehash: ab1a97dc3c78bbfdcc239fd573ef3b1f839e2b21
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215468"
---
# <span data-ttu-id="ed9d6-103">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="ed9d6-103">Get-EventLog</span></span>

## <span data-ttu-id="ed9d6-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ed9d6-104">SYNOPSIS</span></span>
<span data-ttu-id="ed9d6-105">Ruft die Ereignisse in einem Ereignisprotokoll oder eine Liste der Ereignisprotokolle auf dem lokalen Computer oder auf Remote Computern ab.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-105">Gets the events in an event log, or a list of the event logs, on the local computer or remote computers.</span></span>

## <span data-ttu-id="ed9d6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ed9d6-106">SYNTAX</span></span>

### <span data-ttu-id="ed9d6-107">Logname (Standard)</span><span class="sxs-lookup"><span data-stu-id="ed9d6-107">LogName (Default)</span></span>

```
Get-EventLog [-LogName] <String> [-ComputerName <String[]>] [-Newest <Int32>] [-After <DateTime>]
 [-Before <DateTime>] [-UserName <String[]>] [[-InstanceId] <Int64[]>] [-Index <Int32[]>]
 [-EntryType <String[]>] [-Source <String[]>] [-Message <String>] [-AsBaseObject]
 [<CommonParameters>]
```

### <span data-ttu-id="ed9d6-108">List</span><span class="sxs-lookup"><span data-stu-id="ed9d6-108">List</span></span>

```
Get-EventLog [-ComputerName <String[]>] [-List] [-AsString] [<CommonParameters>]
```

## <span data-ttu-id="ed9d6-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ed9d6-109">DESCRIPTION</span></span>

<span data-ttu-id="ed9d6-110">Mit dem- `Get-EventLog` Cmdlet werden Ereignisse und Ereignisprotokolle von lokalen Computern und Remote Computern abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-110">The `Get-EventLog` cmdlet gets events and event logs from local and remote computers.</span></span> <span data-ttu-id="ed9d6-111">Standardmäßig ruft `Get-EventLog` Protokolle vom lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-111">By default, `Get-EventLog` gets logs from the local computer.</span></span> <span data-ttu-id="ed9d6-112">Um Protokolle von Remote Computern zu erhalten, verwenden Sie den **Computername** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-112">To get logs from remote computers, use the **ComputerName** parameter.</span></span>

<span data-ttu-id="ed9d6-113">Sie können die `Get-EventLog` Parameter und Eigenschaftswerte verwenden, um nach Ereignissen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-113">You can use the `Get-EventLog` parameters and property values to search for events.</span></span> <span data-ttu-id="ed9d6-114">Mit dem-Cmdlet werden Ereignisse abgerufen, die den angegebenen Eigenschafts Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-114">The cmdlet gets events that match the specified property values.</span></span>

<span data-ttu-id="ed9d6-115">PowerShell-Cmdlets, die das `EventLog` Substantiv enthalten, funktionieren nur für klassische Windows-Ereignisprotokolle wie z. b. Anwendung, System oder Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-115">PowerShell cmdlets that contain the `EventLog` noun work only on Windows classic event logs such as Application, System, or Security.</span></span> <span data-ttu-id="ed9d6-116">Verwenden Sie, um Protokolle zu erhalten, in denen die Windows-Ereignisprotokoll Technologie in Windows Vista und neueren Windows-Versionen verwendet wird `Get-WinEvent` .</span><span class="sxs-lookup"><span data-stu-id="ed9d6-116">To get logs that use the Windows Event Log technology in Windows Vista and later Windows versions, use `Get-WinEvent`.</span></span>

> [!NOTE]
> <span data-ttu-id="ed9d6-117">`Get-EventLog` verwendet eine als veraltet markierte Win32-API.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-117">`Get-EventLog` uses a Win32 API that is deprecated.</span></span> <span data-ttu-id="ed9d6-118">Die Ergebnisse sind möglicherweise nicht korrekt.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-118">The results may not be accurate.</span></span> <span data-ttu-id="ed9d6-119">Verwenden Sie `Get-WinEvent` stattdessen das-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-119">Use the `Get-WinEvent` cmdlet instead.</span></span>

## <span data-ttu-id="ed9d6-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ed9d6-120">EXAMPLES</span></span>

### <span data-ttu-id="ed9d6-121">Beispiel 1: erhalten von Ereignisprotokollen auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="ed9d6-121">Example 1: Get event logs on the local computer</span></span>

<span data-ttu-id="ed9d6-122">In diesem Beispiel wird die Liste der Ereignisprotokolle angezeigt, die auf dem lokalen Computer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-122">This example displays the list of event logs that are available on the local computer.</span></span> <span data-ttu-id="ed9d6-123">Die Namen in der Spalte Log werden mit dem Parameter **logName** verwendet, um anzugeben, welches Protokoll nach Ereignissen durchsucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-123">The names in the Log column are used with the **LogName** parameter to specify which log is searched for events.</span></span>

```powershell
Get-EventLog -List
```

```Output
Max(K)   Retain   OverflowAction      Entries  Log
------   ------   --------------      -------  ---
15,168        0   OverwriteAsNeeded   20,792   Application
15,168        0   OverwriteAsNeeded   12,559   System
15,360        0   OverwriteAsNeeded   11,173   Windows PowerShell
```

<span data-ttu-id="ed9d6-124">Das `Get-EventLog` Cmdlet verwendet den **List** -Parameter, um die verfügbaren Protokolle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-124">The `Get-EventLog` cmdlet uses the **List** parameter to display the available logs.</span></span>

### <span data-ttu-id="ed9d6-125">Beispiel 2: erhalten aktueller Einträge aus einem Ereignisprotokoll auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="ed9d6-125">Example 2: Get recent entries from an event log on the local computer</span></span>

<span data-ttu-id="ed9d6-126">In diesem Beispiel werden aktuelle Einträge aus dem System Ereignisprotokoll abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-126">This example gets recent entries from the System event log.</span></span>

```powershell
Get-EventLog -LogName System -Newest 5
```

```Output
Index   Time          EntryType    Source              InstanceID   Message
-----   ----          ---------    ------              ----------   -------
13820   Jan 17 19:16  Error        DCOM                     10016   The description for Event...
13819   Jan 17 19:08  Error        DCOM                     10016   The description for Event...
13818   Jan 17 19:06  Information  Service Control...  1073748864   The start type of the Back...
13817   Jan 17 19:05  Error        DCOM                     10016   The description for Event...
13815   Jan 17 19:03  Information  Microsoft-Windows...        35   The time service is now sync...
```

<span data-ttu-id="ed9d6-127">Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Ereignisprotokoll anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-127">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="ed9d6-128">Mit dem **neuesten** Parameter werden die fünf letzten Ereignisse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-128">The **Newest** parameter returns the five most recent events.</span></span>

### <span data-ttu-id="ed9d6-129">Beispiel 3: Suchen aller Quellen für eine bestimmte Anzahl von Einträgen in einem Ereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="ed9d6-129">Example 3: Find all sources for a specific number of entries in an event log</span></span>

<span data-ttu-id="ed9d6-130">Dieses Beispiel zeigt, wie Sie alle Quellen suchen können, die in den 1000 letzten Einträgen im System Ereignisprotokoll enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-130">This example shows how to find all of the sources that are included in the 1000 most recent entries in the System event log.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$Events | Group-Object -Property Source -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count   Name
-----   ----
  110   DCOM
   65   Service Control Manager
   51   Microsoft-Windows-Kern...
   14   EventLog
   14   BTHUSB
   13   Win32k
```

<span data-ttu-id="ed9d6-131">Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Protokoll anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-131">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="ed9d6-132">Der **neueste** Parameter wählt die 1000 aktuellsten Ereignisse aus.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-132">The **Newest** parameter selects the 1000 most recent events.</span></span> <span data-ttu-id="ed9d6-133">Die Ereignis Objekte werden in der `$Events` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-133">The event objects are stored in the `$Events` variable.</span></span> <span data-ttu-id="ed9d6-134">Die `$Events` Objekte werden über die Pipeline an das `Group-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-134">The `$Events` objects are sent down the pipeline to the `Group-Object` cmdlet.</span></span>
<span data-ttu-id="ed9d6-135">`Group-Object` verwendet den **Property** -Parameter, um die Objekte nach Quelle zu gruppieren, und zählt die Anzahl der-Objekte für jede Quelle.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-135">`Group-Object` uses the **Property** parameter to group the objects by source and counts the number of objects for each source.</span></span> <span data-ttu-id="ed9d6-136">Der **noelement** -Parameter entfernt die Gruppenmitglieder aus der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-136">The **NoElement** parameter removes the group members from the output.</span></span>
<span data-ttu-id="ed9d6-137">Das `Sort-Object` Cmdlet verwendet den **Property** -Parameter, um nach der Anzahl der einzelnen Quellen Namen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-137">The `Sort-Object` cmdlet uses the **Property** parameter to sort by the count of each source name.</span></span>
<span data-ttu-id="ed9d6-138">Der **Absteig** Ende Parameter sortiert die Liste nach Anzahl von der höchsten zum niedrigsten.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-138">The **Descending** parameter sorts the list in order by count from highest to lowest.</span></span>

### <span data-ttu-id="ed9d6-139">Beispiel 4: erhalten von Fehlerereignissen aus einem bestimmten Ereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="ed9d6-139">Example 4: Get error events from a specific event log</span></span>

<span data-ttu-id="ed9d6-140">In diesem Beispiel werden Fehlerereignisse aus dem System Ereignisprotokoll abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-140">This example gets error events from the System event log.</span></span>

```powershell
Get-EventLog -LogName System -EntryType Error
```

```Output
Index Time          EntryType   Source  InstanceID Message
----- ----          ---------   ------  ---------- -------
13296 Jan 16 13:53  Error       DCOM    10016 The description for Event ID '10016' in Source...
13291 Jan 16 13:51  Error       DCOM    10016 The description for Event ID '10016' in Source...
13245 Jan 16 11:45  Error       DCOM    10016 The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error       DCOM    10016 The description for Event ID '10016' in Source...
```

<span data-ttu-id="ed9d6-141">Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Protokoll anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-141">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="ed9d6-142">Der **entryType** -Parameter filtert die Ereignisse so, dass nur Fehlerereignisse angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-142">The **EntryType** parameter filters the events to show only Error events.</span></span>

### <span data-ttu-id="ed9d6-143">Beispiel 5: Ereignisse aus einem Ereignisprotokoll mit InstanceId und Quellwert erhalten</span><span class="sxs-lookup"><span data-stu-id="ed9d6-143">Example 5: Get events from an event log with an InstanceId and Source value</span></span>

<span data-ttu-id="ed9d6-144">In diesem Beispiel werden Ereignisse aus dem System Protokoll für eine bestimmte InstanceId und eine bestimmte Quelle abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-144">This example gets events from the System log for a specific InstanceId and Source.</span></span>

```powershell
Get-EventLog -LogName System -InstanceId 10016 -Source DCOM
```

```Output
Index Time          EntryType  Source  InstanceID  Message
----- ----          ---------  ------  ----------  -------
13245 Jan 16 11:45  Error      DCOM         10016  The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error      DCOM         10016  The description for Event ID '10016' in Source...
13219 Jan 16 10:00  Error      DCOM         10016  The description for Event ID '10016' in Source...
```

<span data-ttu-id="ed9d6-145">Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Protokoll anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-145">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="ed9d6-146">Der **InstanceId-** Parameter wählt die Ereignisse mit der angegebenen Instanz-ID aus.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-146">The **InstanceID** parameter selects the events with the specified Instance ID.</span></span> <span data-ttu-id="ed9d6-147">Der **Source** -Parameter gibt die Ereignis Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-147">The **Source** parameter specifies the event property.</span></span>

### <span data-ttu-id="ed9d6-148">Beispiel 6: Ereignisse von mehreren Computern erhalten</span><span class="sxs-lookup"><span data-stu-id="ed9d6-148">Example 6: Get events from multiple computers</span></span>

<span data-ttu-id="ed9d6-149">Mit diesem Befehl werden die Ereignisse aus dem System Ereignisprotokoll auf drei Computern abgerufen: Server01, Server02 und Server03.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-149">This command gets the events from the System event log on three computers: Server01, Server02, and Server03.</span></span>

```powershell
Get-EventLog -LogName System -ComputerName Server01, Server02, Server03
```

<span data-ttu-id="ed9d6-150">Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Protokoll anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-150">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="ed9d6-151">Der **Computername** -Parameter verwendet eine durch Trennzeichen getrennte Zeichenfolge, um die Computer aufzulisten, von denen Sie die Ereignisprotokolle erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-151">The **ComputerName** parameter uses a comma-separated string to list the computers from which you want to get the event logs.</span></span>

### <span data-ttu-id="ed9d6-152">Beispiel 7: alle Ereignisse, die ein bestimmtes Wort enthalten, werden in der Nachricht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-152">Example 7: Get all events that include a specific word in the message</span></span>

<span data-ttu-id="ed9d6-153">Dieser Befehl ruft alle Ereignisse im System Ereignisprotokoll ab, die ein bestimmtes Wort in der Meldung des Ereignisses enthalten.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-153">This command gets all the events in the System event log that contain a specific word in the event's message.</span></span> <span data-ttu-id="ed9d6-154">Es ist möglich, dass der Wert Ihres angegebenen **Nachrichten** Parameters im Inhalt der Nachricht enthalten ist, aber nicht in der PowerShell-Konsole angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-154">It's possible that your specified **Message** parameter's value is included in the message's content but isn't displayed on the PowerShell console.</span></span>

```powershell
Get-EventLog -LogName System -Message *description*
```

```Output
Index Time          EntryType   Source       InstanceID   Message
----- ----          ---------   ------       ----------   -------
13821 Jan 17 19:17  Error       DCOM              10016   The description for Event ID '10016'...
13820 Jan 17 19:16  Error       DCOM              10016   The description for Event ID '10016'...
13819 Jan 17 19:08  Error       DCOM              10016   The description for Event ID '10016'...
```

<span data-ttu-id="ed9d6-155">Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Ereignisprotokoll anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-155">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="ed9d6-156">Der **Message** -Parameter gibt ein Wort an, nach dem im Meldungs Feld jedes Ereignisses gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-156">The **Message** parameter specifies a word to search for in the message field of each event.</span></span>

### <span data-ttu-id="ed9d6-157">Beispiel 8: Anzeigen der Eigenschaftswerte eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="ed9d6-157">Example 8: Display the property values of an event</span></span>

<span data-ttu-id="ed9d6-158">Dieses Beispiel zeigt, wie alle Eigenschaften und Werte eines Ereignisses angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-158">This example shows how to display all of an event's properties and values.</span></span>

```powershell
$A = Get-EventLog -LogName System -Newest 1
$A | Select-Object -Property *
```

```Output
EventID            : 10016
MachineName        : localhost
Data               : {}
Index              : 13821
Category           : (0)
CategoryNumber     : 0
EntryType          : Error
Message            : The description for Event ID '10016' in Source 'DCOM'...
Source             : DCOM
ReplacementStrings : {Local,...}
InstanceId         : 10016
TimeGenerated      : 1/17/2019 19:17:23
TimeWritten        : 1/17/2019 19:17:23
UserName           : username
Site               :
Container          :
```

<span data-ttu-id="ed9d6-159">Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Ereignisprotokoll anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-159">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="ed9d6-160">Der **neueste** Parameter wählt das aktuellste Ereignis Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-160">The **Newest** parameter selects the most recent event object.</span></span> <span data-ttu-id="ed9d6-161">Das-Objekt wird in der- `$A` Variable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-161">The object is stored in the `$A` variable.</span></span> <span data-ttu-id="ed9d6-162">Das Objekt in der `$A` Variablen wird in der Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-162">The object in the `$A` variable is sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="ed9d6-163">`Select-Object` verwendet den **Property** -Parameter mit einem Sternchen ( `*` ), um alle Eigenschaften des Objekts auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-163">`Select-Object` uses the **Property** parameter with an asterisk (`*`) to select all of the object's properties.</span></span>

### <span data-ttu-id="ed9d6-164">Beispiel 9: Ereignisse aus einem Ereignisprotokoll mithilfe einer Quell-und Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="ed9d6-164">Example 9: Get events from an event log using a source and event ID</span></span>

<span data-ttu-id="ed9d6-165">In diesem Beispiel werden Ereignisse für eine angegebene Quelle und Ereignis-ID abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-165">This example gets events for a specified Source and Event ID.</span></span>

```powershell
Get-EventLog -LogName Application -Source Outlook | Where-Object {$_.EventID -eq 63} |
              Select-Object -Property Source, EventID, InstanceId, Message
```

```Output
Source   EventID   InstanceId   Message
------   -------   ----------   -------
Outlook       63   1073741887   The Exchange web service request succeeded.
Outlook       63   1073741887   Outlook detected a change notification.
Outlook       63   1073741887   The Exchange web service request succeeded.
```

<span data-ttu-id="ed9d6-166">Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das Anwendungs Ereignisprotokoll anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-166">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the Application event log.</span></span> <span data-ttu-id="ed9d6-167">Der **Quell** Parameter gibt den Anwendungsnamen an, Outlook.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-167">The **Source** parameter specifies the application name, Outlook.</span></span> <span data-ttu-id="ed9d6-168">Die Objekte werden über die Pipeline an das `Where-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-168">The objects are sent down the pipeline to the `Where-Object` cmdlet.</span></span> <span data-ttu-id="ed9d6-169">Für jedes Objekt in der Pipeline verwendet das `Where-Object` Cmdlet die Variable, `$_.EventID` um die Ereignis-ID-Eigenschaft mit dem angegebenen Wert zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-169">For each object in the pipeline, the `Where-Object` cmdlet uses the variable `$_.EventID` to compare the Event ID property to the specified value.</span></span> <span data-ttu-id="ed9d6-170">Die Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-170">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="ed9d6-171">`Select-Object` verwendet den **Property** -Parameter, um die Eigenschaften auszuwählen, die in der PowerShell-Konsole angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-171">`Select-Object` uses the **Property** parameter to select the properties to display in the PowerShell console.</span></span>

### <span data-ttu-id="ed9d6-172">Beispiel 10: Ereignisse erhalten und nach einer Eigenschaft gruppieren</span><span class="sxs-lookup"><span data-stu-id="ed9d6-172">Example 10: Get events and group by a property</span></span>

```powershell
Get-EventLog -LogName System -UserName NT* | Group-Object -Property UserName -NoElement |
              Select-Object -Property Count, Name
```

```Output
Count  Name
-----  ----
6031   NT AUTHORITY\SYSTEM
  42   NT AUTHORITY\LOCAL SERVICE
   4   NT AUTHORITY\NETWORK SERVICE
```

<span data-ttu-id="ed9d6-173">Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Protokoll anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-173">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="ed9d6-174">Der **username** -Parameter enthält den Platzhalter ( `*` ), um einen Teil des Benutzernamens anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-174">The **UserName** parameter includes the asterisk (`*`) wildcard to specify a portion of the user name.</span></span> <span data-ttu-id="ed9d6-175">Die Ereignis Objekte werden über die Pipeline an das `Group-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-175">The event objects are sent down the pipeline to the `Group-Object` cmdlet.</span></span> <span data-ttu-id="ed9d6-176">`Group-Object` verwendet den **Property** -Parameter, um anzugeben, dass die **username** -Eigenschaft zum Gruppieren der Objekte und zum zählen der Anzahl von Objekten für jeden Benutzernamen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-176">`Group-Object` uses the **Property** parameter to specify that the **UserName** property is used to group the objects and count the number of objects for each user name.</span></span> <span data-ttu-id="ed9d6-177">Der **noelement** -Parameter entfernt die Gruppenmitglieder aus der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-177">The **NoElement** parameter removes the group members from the output.</span></span> <span data-ttu-id="ed9d6-178">Die Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-178">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="ed9d6-179">`Select-Object` verwendet den **Property** -Parameter, um die Eigenschaften auszuwählen, die in der PowerShell-Konsole angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-179">`Select-Object` uses the **Property** parameter to select the properties to display in the PowerShell console.</span></span>

### <span data-ttu-id="ed9d6-180">Beispiel 11: Ereignisse, die während eines bestimmten Datums-und Zeit Bereichs aufgetreten sind</span><span class="sxs-lookup"><span data-stu-id="ed9d6-180">Example 11: Get events that occurred during a specific date and time range</span></span>

<span data-ttu-id="ed9d6-181">In diesem Beispiel werden Fehlerereignisse aus dem System Ereignisprotokoll für einen bestimmten Datums-und Uhrzeit Bereich abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-181">This example gets Error events from the System event log for a specified date and time range.</span></span> <span data-ttu-id="ed9d6-182">Die Parameter " **before** " und " **after** " legen den Datums-und Uhrzeit Bereich fest, werden jedoch aus der Ausgabe ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-182">The **Before** and **After** parameters set the date and time range but are excluded from the output.</span></span>

```powershell
$Begin = Get-Date -Date '1/17/2019 08:00:00'
$End = Get-Date -Date '1/17/2019 17:00:00'
Get-EventLog -LogName System -EntryType Error -After $Begin -Before $End
```

```Output
Index Time          EntryType   Source   InstanceID  Message
----- ----          ---------   ------   ----------  -------
13821 Jan 17 13:40  Error       DCOM          10016  The description for Event ID...
13820 Jan 17 13:11  Error       DCOM          10016  The description for Event ID...
...
12372 Jan 17 10:08  Error       DCOM          10016  The description for Event ID...
12371 Jan 17 09:04  Error       DCOM          10016  The description for Event ID...
```

<span data-ttu-id="ed9d6-183">Das `Get-Date` Cmdlet verwendet den **Date** -Parameter, um ein Datum und eine Uhrzeit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-183">The `Get-Date` cmdlet uses the **Date** parameter to specify a date and time.</span></span> <span data-ttu-id="ed9d6-184">Die **DateTime** -Objekte werden in der `$Begin` -Variable und der- `$End` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-184">The **DateTime** objects are stored in the `$Begin` and `$End` variables.</span></span> <span data-ttu-id="ed9d6-185">Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Protokoll anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-185">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="ed9d6-186">Der **entryType** -Parameter gibt den Fehler Ereignistyp an.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-186">The **EntryType** parameter specifies the Error event type.</span></span> <span data-ttu-id="ed9d6-187">Der Datums-und Uhrzeit Bereich wird durch den **after** -Parameter und `$Begin` die-Variable sowie den **before** -Parameter und die-Variable festgelegt `$End` .</span><span class="sxs-lookup"><span data-stu-id="ed9d6-187">The date and time range is set by the **After** parameter and `$Begin` variable and the **Before** parameter and `$End` variable.</span></span>

## <span data-ttu-id="ed9d6-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ed9d6-188">PARAMETERS</span></span>

### <span data-ttu-id="ed9d6-189">Nach</span><span class="sxs-lookup"><span data-stu-id="ed9d6-189">-After</span></span>

<span data-ttu-id="ed9d6-190">Ruft Ereignisse ab, die nach einem angegebenen Datum und einer angegebenen Uhrzeit aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-190">Gets events that occurred after a specified date and time.</span></span> <span data-ttu-id="ed9d6-191">Das Datum und die Uhrzeit des **after** -Parameters werden aus der Ausgabe ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-191">The **After** parameter date and time are excluded from the output.</span></span> <span data-ttu-id="ed9d6-192">Geben Sie ein **DateTime** -Objekt ein, z. b. den vom `Get-Date` Cmdlet zurückgegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-192">Enter a **DateTime** object, such as the value returned by the `Get-Date` cmdlet.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed9d6-193">-Asbaseobject</span><span class="sxs-lookup"><span data-stu-id="ed9d6-193">-AsBaseObject</span></span>

<span data-ttu-id="ed9d6-194">Gibt an, dass dieses Cmdlet ein **System. Diagnostics. EventLogEntry** -Standard Objekt für jedes Ereignis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-194">Indicates that this cmdlet returns a standard **System.Diagnostics.EventLogEntry** object for each event.</span></span> <span data-ttu-id="ed9d6-195">Ohne diesen Parameter `Get-EventLog` gibt ein erweitertes **psobject** -Objekt mit zusätzlichen Eigenschaften " **Eventlogname** ", " **Source** " und " **InstanceId** " zurück.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-195">Without this parameter, `Get-EventLog` returns an extended **PSObject** object with additional **EventLogName** , **Source** , and **InstanceId** properties.</span></span>

<span data-ttu-id="ed9d6-196">Um die Auswirkung dieses Parameters anzuzeigen, übergeben Sie die Ereignisse an das `Get-Member` Cmdlet, und untersuchen Sie den **TypeName** -Wert im Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-196">To see the effect of this parameter, pipe the events to the `Get-Member` cmdlet and examine the **TypeName** value in the result.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed9d6-197">-AsString</span><span class="sxs-lookup"><span data-stu-id="ed9d6-197">-AsString</span></span>

<span data-ttu-id="ed9d6-198">Gibt an, dass dieses Cmdlet die Ausgabe als Zeichen folgen anstelle von-Objekten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-198">Indicates that this cmdlet returns the output as strings, instead of objects.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed9d6-199">-Vor</span><span class="sxs-lookup"><span data-stu-id="ed9d6-199">-Before</span></span>

<span data-ttu-id="ed9d6-200">Ruft Ereignisse ab, die vor dem angegebenen Datum und der angegebenen Uhrzeit aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-200">Gets events that occurred before a specified date and time.</span></span> <span data-ttu-id="ed9d6-201">Der **before** -Parameter "Date" und "Time" werden aus der Ausgabe ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-201">The **Before** parameter date and time are excluded from the output.</span></span> <span data-ttu-id="ed9d6-202">Geben Sie ein **DateTime** -Objekt ein, z. b. den vom `Get-Date` Cmdlet zurückgegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-202">Enter a **DateTime** object, such as the value returned by the `Get-Date` cmdlet.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed9d6-203">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="ed9d6-203">-ComputerName</span></span>

<span data-ttu-id="ed9d6-204">Dieser Parameter gibt den NetBIOS-Namen, die IP-Adresse oder einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) eines Remote Computers an.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-204">This parameter specifies a remote computer's NetBIOS name, Internet Protocol (IP) address, or a fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="ed9d6-205">Wenn der **Computername** -Parameter nicht angegeben ist, wird `Get-EventLog` standardmäßig der lokale Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-205">If the **ComputerName** parameter isn't specified, `Get-EventLog` defaults to the local computer.</span></span> <span data-ttu-id="ed9d6-206">Der-Parameter akzeptiert auch einen Punkt ( `.` ), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-206">The parameter also accepts a dot (`.`) to specify the local computer.</span></span>

<span data-ttu-id="ed9d6-207">Der **Computername** -Parameter beruht nicht auf Windows PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-207">The **ComputerName** parameter doesn't rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="ed9d6-208">Sie können `Get-EventLog` mit dem **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-208">You can use `Get-EventLog` with the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed9d6-209">-EntryType</span><span class="sxs-lookup"><span data-stu-id="ed9d6-209">-EntryType</span></span>

<span data-ttu-id="ed9d6-210">Gibt den Eintragstyp der Ereignisse, die von diesem Cmdlet abgerufen werden, als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-210">Specifies, as a string array, the entry type of the events that this cmdlet gets.</span></span>

<span data-ttu-id="ed9d6-211">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="ed9d6-211">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ed9d6-212">Fehler</span><span class="sxs-lookup"><span data-stu-id="ed9d6-212">Error</span></span>
- <span data-ttu-id="ed9d6-213">Information</span><span class="sxs-lookup"><span data-stu-id="ed9d6-213">Information</span></span>
- <span data-ttu-id="ed9d6-214">FAILUREAUDIT</span><span class="sxs-lookup"><span data-stu-id="ed9d6-214">FailureAudit</span></span>
- <span data-ttu-id="ed9d6-215">;</span><span class="sxs-lookup"><span data-stu-id="ed9d6-215">SuccessAudit</span></span>
- <span data-ttu-id="ed9d6-216">Warnung</span><span class="sxs-lookup"><span data-stu-id="ed9d6-216">Warning</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed9d6-217">-Index</span><span class="sxs-lookup"><span data-stu-id="ed9d6-217">-Index</span></span>

<span data-ttu-id="ed9d6-218">Gibt die Indexwerte an, die aus dem Ereignisprotokoll abgeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-218">Specifies the index values to get from the event log.</span></span> <span data-ttu-id="ed9d6-219">Der-Parameter akzeptiert eine durch Kommas getrennte Zeichenfolge von Werten.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-219">The parameter accepts a comma-separated string of values.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed9d6-220">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="ed9d6-220">-InstanceId</span></span>

<span data-ttu-id="ed9d6-221">Gibt die Instanz-IDs an, die aus dem Ereignisprotokoll abgeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-221">Specifies the Instance IDs to get from the event log.</span></span> <span data-ttu-id="ed9d6-222">Der-Parameter akzeptiert eine durch Kommas getrennte Zeichenfolge von Werten.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-222">The parameter accepts a comma-separated string of values.</span></span>

```yaml
Type: System.Int64[]
Parameter Sets: LogName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed9d6-223">-List</span><span class="sxs-lookup"><span data-stu-id="ed9d6-223">-List</span></span>

<span data-ttu-id="ed9d6-224">Zeigt die Liste der Ereignisprotokolle auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-224">Displays the list of event logs on the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed9d6-225">-LogName</span><span class="sxs-lookup"><span data-stu-id="ed9d6-225">-LogName</span></span>

<span data-ttu-id="ed9d6-226">Gibt den Namen eines Ereignis Protokolls an.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-226">Specifies the name of one event log.</span></span> <span data-ttu-id="ed9d6-227">Zum Ermitteln der Protokollnamen verwenden Sie `Get-EventLog -List` .</span><span class="sxs-lookup"><span data-stu-id="ed9d6-227">To find the log names use `Get-EventLog -List`.</span></span> <span data-ttu-id="ed9d6-228">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-228">Wildcard characters are permitted.</span></span> <span data-ttu-id="ed9d6-229">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-229">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ed9d6-230">-Meldung</span><span class="sxs-lookup"><span data-stu-id="ed9d6-230">-Message</span></span>

<span data-ttu-id="ed9d6-231">Gibt eine Zeichenfolge in der Ereignismeldung an.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-231">Specifies a string in the event message.</span></span> <span data-ttu-id="ed9d6-232">Sie können diesen Parameter verwenden, um nach Nachrichten zu suchen, die bestimmte Wörter oder Ausdrücke enthalten.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-232">You can use this parameter to search for messages that contain certain words or phrases.</span></span> <span data-ttu-id="ed9d6-233">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-233">Wildcards are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: MSG

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ed9d6-234">-Latest</span><span class="sxs-lookup"><span data-stu-id="ed9d6-234">-Newest</span></span>

<span data-ttu-id="ed9d6-235">Beginnt mit den neuesten Ereignissen und ruft die angegebene Anzahl von Ereignissen ab.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-235">Begins with the newest events and gets the specified number of events.</span></span> <span data-ttu-id="ed9d6-236">Die Anzahl der Ereignisse ist beispielsweise erforderlich `-Newest 100` .</span><span class="sxs-lookup"><span data-stu-id="ed9d6-236">The number of events is required, for example `-Newest 100`.</span></span> <span data-ttu-id="ed9d6-237">Gibt die maximale Anzahl von Ereignissen an, die zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-237">Specifies the maximum number of events that are returned.</span></span>

```yaml
Type: System.Int32
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed9d6-238">-Source</span><span class="sxs-lookup"><span data-stu-id="ed9d6-238">-Source</span></span>

<span data-ttu-id="ed9d6-239">Gibt als Zeichen folgen Array Quellen an, die in das Protokoll geschrieben wurden, das von diesem Cmdlet abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-239">Specifies, as a string array, sources that were written to the log that this cmdlet gets.</span></span> <span data-ttu-id="ed9d6-240">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-240">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ABO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ed9d6-241">-UserName</span><span class="sxs-lookup"><span data-stu-id="ed9d6-241">-UserName</span></span>

<span data-ttu-id="ed9d6-242">Gibt Benutzernamen, die Ereignissen zugeordnet sind, als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-242">Specifies, as a string array, user names that are associated with events.</span></span> <span data-ttu-id="ed9d6-243">Geben Sie Namen oder Namensmuster ein, `User01` z `User*` . b `Domain01\User*` ., oder.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-243">Enter names or name patterns, such as `User01`, `User*`, or `Domain01\User*`.</span></span> <span data-ttu-id="ed9d6-244">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-244">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ed9d6-245">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ed9d6-245">CommonParameters</span></span>

<span data-ttu-id="ed9d6-246">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ed9d6-247">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ed9d6-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ed9d6-248">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ed9d6-248">INPUTS</span></span>

### <span data-ttu-id="ed9d6-249">Keine</span><span class="sxs-lookup"><span data-stu-id="ed9d6-249">None</span></span>

<span data-ttu-id="ed9d6-250">Eingaben können nicht an übergeben werden `Get-EventLog` .</span><span class="sxs-lookup"><span data-stu-id="ed9d6-250">You cannot pipe input to `Get-EventLog`.</span></span>

## <span data-ttu-id="ed9d6-251">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ed9d6-251">OUTPUTS</span></span>

### <span data-ttu-id="ed9d6-252">System. Diagnostics. EventLogEntry.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-252">System.Diagnostics.EventLogEntry.</span></span> <span data-ttu-id="ed9d6-253">System. Diagnostics. EventLog.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-253">System.Diagnostics.EventLog.</span></span> <span data-ttu-id="ed9d6-254">System.String</span><span class="sxs-lookup"><span data-stu-id="ed9d6-254">System.String</span></span>

<span data-ttu-id="ed9d6-255">Wenn der **logName** -Parameter angegeben wird, handelt es sich bei der Ausgabe um eine Sammlung von **System. Diagnostics. EventLogEntry** -Objekten.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-255">If the **LogName** parameter is specified, the output is a collection of **System.Diagnostics.EventLogEntry** objects.</span></span>

<span data-ttu-id="ed9d6-256">Wenn nur der **List** -Parameter angegeben wird, handelt es sich bei der Ausgabe um eine Sammlung von **System. Diagnostics. EventLog** -Objekten.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-256">If only the **List** parameter is specified, the output is a collection of **System.Diagnostics.EventLog** objects.</span></span>

<span data-ttu-id="ed9d6-257">Wenn sowohl der **List** -Parameter als auch der **AsString** -Parameter angegeben sind, ist die Ausgabe eine Auflistung von **System. String** -Objekten.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-257">If both the **List** and **AsString** parameters are specified, the output is a collection of **System.String** objects.</span></span>

## <span data-ttu-id="ed9d6-258">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ed9d6-258">NOTES</span></span>

<span data-ttu-id="ed9d6-259">Die Cmdlets `Get-EventLog` und `Get-WinEvent` werden im Windows Preinstallation Environment (Windows PE) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ed9d6-259">The cmdlets `Get-EventLog` and `Get-WinEvent` are not supported in the Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="ed9d6-260">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ed9d6-260">RELATED LINKS</span></span>

[<span data-ttu-id="ed9d6-261">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="ed9d6-261">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="ed9d6-262">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="ed9d6-262">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="ed9d6-263">Group-Object</span><span class="sxs-lookup"><span data-stu-id="ed9d6-263">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="ed9d6-264">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="ed9d6-264">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="ed9d6-265">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="ed9d6-265">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="ed9d6-266">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="ed9d6-266">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="ed9d6-267">Select-Object</span><span class="sxs-lookup"><span data-stu-id="ed9d6-267">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="ed9d6-268">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="ed9d6-268">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="ed9d6-269">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="ed9d6-269">Write-EventLog</span></span>](Write-EventLog.md)
