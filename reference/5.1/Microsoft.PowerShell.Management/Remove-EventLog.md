---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-EventLog
ms.openlocfilehash: 4cf29146727c9a54715459a2d56e47a27c5bacc0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214556"
---
# <span data-ttu-id="71136-103">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="71136-103">Remove-EventLog</span></span>

## <span data-ttu-id="71136-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="71136-104">SYNOPSIS</span></span>
<span data-ttu-id="71136-105">Löscht ein Ereignisprotokoll oder hebt die Registrierung einer Ereignisquelle auf.</span><span class="sxs-lookup"><span data-stu-id="71136-105">Deletes an event log or unregisters an event source.</span></span>

## <span data-ttu-id="71136-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="71136-106">SYNTAX</span></span>

### <span data-ttu-id="71136-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="71136-107">Default (Default)</span></span>

```
Remove-EventLog [[-ComputerName] <String[]>] [-LogName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="71136-108">`Source`</span><span class="sxs-lookup"><span data-stu-id="71136-108">Source</span></span>

```
Remove-EventLog [[-ComputerName] <String[]>] [-Source <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="71136-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="71136-109">DESCRIPTION</span></span>
<span data-ttu-id="71136-110">Das **Remove-EventLog** -Cmdlet löscht eine Ereignisprotokoll Datei von einem lokalen Computer oder einem Remote Computer und hebt die Registrierung aller Ereignis Quellen für das Protokoll auf.</span><span class="sxs-lookup"><span data-stu-id="71136-110">The **Remove-EventLog** cmdlet deletes an event log file from a local or remote computer and unregisters all its event sources for the log.</span></span>
<span data-ttu-id="71136-111">Sie können mit diesem Cmdlet auch die Registrierung der Ereignisquellen aufheben, ohne Ereignisprotokolle zu löschen.</span><span class="sxs-lookup"><span data-stu-id="71136-111">You can also use this cmdlet to unregister event sources without deleting any event logs.</span></span>

<span data-ttu-id="71136-112">Die Cmdlets, die das **EventLog** -Substantiv ( **EventLog** -Cmdlets) enthalten, funktionieren nur in klassischen Ereignisprotokollen.</span><span class="sxs-lookup"><span data-stu-id="71136-112">The cmdlets that contain the **EventLog** noun, the **EventLog** cmdlets, work only on classic event logs.</span></span>
<span data-ttu-id="71136-113">Verwenden Sie Get-WinEvent, um Ereignisse aus Protokollen zu erhalten, in denen die Windows-Ereignisprotokoll Technologie in Windows Vista und höheren Versionen des Windows-Betriebssystems verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="71136-113">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use Get-WinEvent.</span></span>

<span data-ttu-id="71136-114">Vorsicht: mit diesem Cmdlet können Ereignisprotokolle des Betriebssystems gelöscht werden. Dies kann zu Anwendungsfehlern und unerwartetem Systemverhalten führen.</span><span class="sxs-lookup"><span data-stu-id="71136-114">CAUTION: This cmdlet can delete operating system event logs, which might cause application failures and unexpected system behavior.</span></span>

## <span data-ttu-id="71136-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="71136-115">EXAMPLES</span></span>

### <span data-ttu-id="71136-116">Beispiel 1: Entfernen eines Ereignis Protokolls vom lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="71136-116">Example 1: Remove an event log from the local computer</span></span>

```
PS C:\> Remove-EventLog -LogName "MyLog"
```

<span data-ttu-id="71136-117">Dieser Befehl löscht das Ereignisprotokoll %%amp;quot;MyLog%%amp;quot; vom lokalen Computer und hebt die Registrierung seiner Ereignisquellen auf.</span><span class="sxs-lookup"><span data-stu-id="71136-117">This command deletes the MyLog event log from the local computer and unregisters its event sources.</span></span>

### <span data-ttu-id="71136-118">Beispiel 2: Entfernen eines Ereignis Protokolls von mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="71136-118">Example 2: Remove an event log from several computers</span></span>

```
PS C:\> Remove-EventLog -LogName "MyLog", "TestLog" -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="71136-119">Mit diesem Befehl werden die Ereignisprotokolle MyLog und testlog vom lokalen Computer und den Remote Computern Server01 und Server02 gelöscht.</span><span class="sxs-lookup"><span data-stu-id="71136-119">This command deletes the MyLog and TestLog event logs from the local computer and the Server01 and Server02 remote computers.</span></span>
<span data-ttu-id="71136-120">Der Befehl hebt auch die Registrierung der Ereignisquellen für diese Protokolle auf.</span><span class="sxs-lookup"><span data-stu-id="71136-120">The command also unregisters the event sources for these logs.</span></span>

### <span data-ttu-id="71136-121">Beispiel 3: Löschen einer Ereignis Quelle</span><span class="sxs-lookup"><span data-stu-id="71136-121">Example 3: Delete an event source</span></span>

```
PS C:\> Remove-EventLog -Source "MyApp"
```

<span data-ttu-id="71136-122">Dieser Befehl löscht die Ereignisquelle %%amp;quot;MyApp%%amp;quot; aus den Protokollen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="71136-122">This command deletes the MyApp event source from the logs on the local computer.</span></span>
<span data-ttu-id="71136-123">Wenn der Befehl abgeschlossen ist, kann das Programm MyApp nicht in Ereignisprotokolle schreiben.</span><span class="sxs-lookup"><span data-stu-id="71136-123">When the command finishes, the MyApp program cannot write to any event logs.</span></span>

### <span data-ttu-id="71136-124">Beispiel 4: Entfernen eines Ereignis Protokolls und bestätigen der Aktion</span><span class="sxs-lookup"><span data-stu-id="71136-124">Example 4: Remove an event log and confirm the action</span></span>

```
The first command lists the event logs on the local computer.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
15,168      7 OverwriteAsNeeded          12 ZapLog

The second command deletes the ZapLog event log.
PS C:\> Remove-EventLog -LogName "ZapLog"

The third command lists the event logs again. The ZapLog event log no longer appears in the list.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
```

<span data-ttu-id="71136-125">Diese Befehle zeigen, wie Sie die Ereignisprotokolle auf einem Computer auflisten und überprüfen, ob der Befehl **Remove-EventLog** erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="71136-125">These commands show how to list the event logs on a computer and verify that a **Remove-EventLog** command was successful.</span></span>

### <span data-ttu-id="71136-126">Beispiel 5: Entfernen einer Ereignis Quelle und bestätigen der Aktion</span><span class="sxs-lookup"><span data-stu-id="71136-126">Example 5: Remove an event source and confirm the action</span></span>

```
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'" | foreach {$_.sources}
MyApp
TestApp
PS C:\> Remove-Eventlog -Source "MyApp"
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'"} | foreach {$_.sources}
TestApp
```

<span data-ttu-id="71136-127">In diesen Befehlen werden mit dem Cmdlet %%amp;quot;Get-WmiObject%%amp;quot; die Ereignisquellen auf dem lokalen Computer aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="71136-127">These commands use the Get-WmiObject cmdlet to list the event sources on the local computer.</span></span>
<span data-ttu-id="71136-128">Sie können mit diesen Befehlen die erfolgreiche Ausführung eines Befehls überprüfen oder eine Ereignisquelle löschen.</span><span class="sxs-lookup"><span data-stu-id="71136-128">You can these commands to verify the success of a command or to delete an event source.</span></span>

<span data-ttu-id="71136-129">Der erste Befehl ruft die Ereignisquellen des Ereignisprotokolls %%amp;quot;TestLog%%amp;quot; auf dem lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="71136-129">The first command gets the event sources of the TestLog event log on the local computer.</span></span>
<span data-ttu-id="71136-130">Eine der Quellen ist %%amp;quot;MyApp%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="71136-130">MyApp is one of the sources.</span></span>

<span data-ttu-id="71136-131">Der zweite Befehl verwendet den *Source* -Parameter von " **Remove-EventLog** ", um die Ereignis Quelle "MyApp" zu löschen.</span><span class="sxs-lookup"><span data-stu-id="71136-131">The second command uses the *Source* parameter of **Remove-EventLog** to delete the MyApp event source.</span></span>

<span data-ttu-id="71136-132">Der dritte Befehl ist mit dem ersten Befehl identisch.</span><span class="sxs-lookup"><span data-stu-id="71136-132">The third command is identical to the first.</span></span>
<span data-ttu-id="71136-133">Er zeigt, dass die Ereignisquelle %%amp;quot;MyApp%%amp;quot; gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="71136-133">It shows that the MyApp event source was deleted.</span></span>

## <span data-ttu-id="71136-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="71136-134">PARAMETERS</span></span>

### <span data-ttu-id="71136-135">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="71136-135">-ComputerName</span></span>
<span data-ttu-id="71136-136">Gibt einen Remotecomputer an.</span><span class="sxs-lookup"><span data-stu-id="71136-136">Specifies a remote computer.</span></span>
<span data-ttu-id="71136-137">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="71136-137">The default is the local computer.</span></span>

<span data-ttu-id="71136-138">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein.</span><span class="sxs-lookup"><span data-stu-id="71136-138">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="71136-139">Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="71136-139">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="71136-140">Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="71136-140">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="71136-141">Sie können den *Computername* -Parameter von **Remove-EventLog** auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="71136-141">You can use the *ComputerName* parameter of **Remove-EventLog** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71136-142">-LogName</span><span class="sxs-lookup"><span data-stu-id="71136-142">-LogName</span></span>
<span data-ttu-id="71136-143">Gibt die Ereignisprotokolle an.</span><span class="sxs-lookup"><span data-stu-id="71136-143">Specifies the event logs.</span></span>
<span data-ttu-id="71136-144">Geben Sie den Protokollnamen eines oder mehrerer Ereignisprotokolle ein, die durch Kommas getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="71136-144">Enter the log name of one or more event logs, separated by commas.</span></span>
<span data-ttu-id="71136-145">Der Protokoll Name ist der Wert der **Log** -Eigenschaft, nicht der *LogDisplayName* . Platzhalter Zeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="71136-145">The log name is the value of the **Log** property, not the *LogDisplayName* , Wildcard characters are not permitted.</span></span>
<span data-ttu-id="71136-146">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="71136-146">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71136-147">-Source</span><span class="sxs-lookup"><span data-stu-id="71136-147">-Source</span></span>
<span data-ttu-id="71136-148">Gibt die Ereignis Quellen an, deren Registrierung dieses Cmdlet aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="71136-148">Specifies the event sources that this cmdlet unregisters.</span></span>
<span data-ttu-id="71136-149">Geben Sie die Quellnamen, nicht den Namen der ausführbaren Datei, durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="71136-149">Enter the source names, not the executable name, separated by commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: SRC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71136-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="71136-150">-Confirm</span></span>
<span data-ttu-id="71136-151">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="71136-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="71136-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="71136-152">-WhatIf</span></span>
<span data-ttu-id="71136-153">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="71136-153">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="71136-154">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="71136-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="71136-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="71136-155">CommonParameters</span></span>
<span data-ttu-id="71136-156">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="71136-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="71136-157">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="71136-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="71136-158">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="71136-158">INPUTS</span></span>

### <span data-ttu-id="71136-159">Keine</span><span class="sxs-lookup"><span data-stu-id="71136-159">None</span></span>
<span data-ttu-id="71136-160">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="71136-160">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="71136-161">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="71136-161">OUTPUTS</span></span>

### <span data-ttu-id="71136-162">Keine</span><span class="sxs-lookup"><span data-stu-id="71136-162">None</span></span>
<span data-ttu-id="71136-163">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="71136-163">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="71136-164">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="71136-164">NOTES</span></span>

* <span data-ttu-id="71136-165">Wenn Sie " **Remove-EventLog** " unter Windows Vista und höheren Versionen des Windows-Betriebssystems verwenden möchten, starten Sie Windows PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="71136-165">To use **Remove-EventLog** on Windows Vista and later versions of the Windows operating system, start Windows PowerShell by using the Run as administrator option.</span></span>

  <span data-ttu-id="71136-166">Wenn Sie ein Ereignisprotokoll entfernen und das Protokoll dann neu erstellen, können Sie nicht die gleichen Ereignisquellen registrieren.</span><span class="sxs-lookup"><span data-stu-id="71136-166">If you remove an event log and then re-create the log, you will not be able to register the same event sources.</span></span>
<span data-ttu-id="71136-167">Anwendungen, die die Ereignisquellen zum Schreiben von Einträgen im ursprünglichen Protokoll verwendet haben, können nicht in das neue Protokoll schreiben.</span><span class="sxs-lookup"><span data-stu-id="71136-167">Applications that used the events sources to write entries to the original log will not be able to write to the new log.</span></span>

* <span data-ttu-id="71136-168">Wenn Sie die Registrierung einer Ereignisquelle für ein bestimmtes Protokoll aufheben, kann die Ereignisquelle möglicherweise keine Einträge mehr in andere Ereignisprotokolle schreiben.</span><span class="sxs-lookup"><span data-stu-id="71136-168">When you unregister an event source for a particular log, the event source might be prevented from writing entries in other event logs.</span></span>

## <span data-ttu-id="71136-169">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="71136-169">RELATED LINKS</span></span>

[<span data-ttu-id="71136-170">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="71136-170">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="71136-171">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="71136-171">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="71136-172">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="71136-172">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="71136-173">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="71136-173">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="71136-174">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="71136-174">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="71136-175">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="71136-175">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="71136-176">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="71136-176">Write-EventLog</span></span>](Write-EventLog.md)
