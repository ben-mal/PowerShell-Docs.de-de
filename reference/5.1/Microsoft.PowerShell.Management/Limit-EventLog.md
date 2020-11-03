---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/limit-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Limit-EventLog
ms.openlocfilehash: 3ec3214103dc6151e148f7482b0be8b821871e3c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214663"
---
# <span data-ttu-id="c866d-103">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="c866d-103">Limit-EventLog</span></span>

## <span data-ttu-id="c866d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c866d-104">SYNOPSIS</span></span>
<span data-ttu-id="c866d-105">Legt die Ereignisprotokolleigenschaften fest, die die Größe des Ereignisprotokolls und das Alter seiner Einträge einschränken.</span><span class="sxs-lookup"><span data-stu-id="c866d-105">Sets the event log properties that limit the size of the event log and the age of its entries.</span></span>

## <span data-ttu-id="c866d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c866d-106">SYNTAX</span></span>

```
Limit-EventLog [-LogName] <String[]> [-ComputerName <String[]>] [-RetentionDays <Int32>]
 [-OverflowAction <OverflowAction>] [-MaximumSize <Int64>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c866d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c866d-107">DESCRIPTION</span></span>
<span data-ttu-id="c866d-108">Das **Limit-EventLog** -Cmdlet legt die maximale Größe eines klassischen Ereignis Protokolls fest, wie lange jedes Ereignis beibehalten werden muss und was geschieht, wenn das Protokoll seine maximale Größe erreicht.</span><span class="sxs-lookup"><span data-stu-id="c866d-108">The **Limit-EventLog** cmdlet sets the maximum size of a classic event log, how long each event must be retained, and what happens when the log reaches its maximum size.</span></span>
<span data-ttu-id="c866d-109">Sie können hiermit die Ereignisprotokolle auf lokalen Computern oder Remotecomputern einschränken.</span><span class="sxs-lookup"><span data-stu-id="c866d-109">You can use it to limit the event logs on local or remote computers.</span></span>

<span data-ttu-id="c866d-110">Die Cmdlets, die das Substantiv %%amp;quot;EventLog%%amp;quot; enthalten (die EventLog-Cmdlets), können nur für klassische Ereignisprotokolle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c866d-110">The cmdlets that contain the EventLog noun (the EventLog cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="c866d-111">Verwenden Sie %%amp;quot;Get-WinEvent%%amp;quot;, um Ereignisse aus Protokollen abzurufen, die die Windows-Ereignisprotokolltechnologie in Windows Vista und höheren Versionen von Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="c866d-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of Windows, use Get-WinEvent.</span></span>

## <span data-ttu-id="c866d-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c866d-112">EXAMPLES</span></span>

### <span data-ttu-id="c866d-113">Beispiel 1: Vergrößern der Größe eines Ereignis Protokolls</span><span class="sxs-lookup"><span data-stu-id="c866d-113">Example 1: Increase the size of an event log</span></span>

```
PS C:\> Limit-EventLog -LogName "Windows PowerShell" -MaximumSize 20KB
```

<span data-ttu-id="c866d-114">Dieser Befehl erhöht die maximale Größe des Windows PowerShell-Ereignisprotokolls auf dem lokalen Computer auf 20480 Byte (20 KB).</span><span class="sxs-lookup"><span data-stu-id="c866d-114">This command increases the maximum size of the Windows PowerShell event log on the local computer to 20480 bytes (20 KB).</span></span>

### <span data-ttu-id="c866d-115">Beispiel 2: beibehalten eines Ereignis Protokolls für eine angegebene Dauer</span><span class="sxs-lookup"><span data-stu-id="c866d-115">Example 2: Retain an event log for a specified duration</span></span>

```
PS C:\> Limit-EventLog -LogName Security -ComputerName "Server01", "Server02" -RetentionDays 7
```

<span data-ttu-id="c866d-116">Dieser Befehl stellt sicher, dass Ereignisse im Sicherheitsprotokoll auf den Computern %%amp;quot;Server01%%amp;quot; und %%amp;quot;Server02%%amp;quot; mindestens 7 Tage lang beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="c866d-116">This command ensures that events in the Security log on the Server01 and Server02 computers are retained for at least 7 days.</span></span>

### <span data-ttu-id="c866d-117">Beispiel 3: Ändern der Überlauf Aktion aller Ereignisprotokolle</span><span class="sxs-lookup"><span data-stu-id="c866d-117">Example 3: Change the overflow action of all event logs</span></span>

```
PS C:\> $Logs = Get-EventLog -List | ForEach {$_.log}
PS C:\> Limit-EventLog -OverflowAction OverwriteOlder -LogName $Logs
PS C:\> Get-EventLog -List

Max(K) Retain OverflowAction     Entries  Log
------ ------ --------------     -------  ---
15,168      0 OverwriteOlder       3,412  Application
512         0 OverwriteOlder           0  DFS Replication
512         0 OverwriteOlder          17  DxStudio
10,240      7 OverwriteOlder           0  HardwareEvents
512         0 OverwriteOlder           0  Internet Explorer
512         0 OverwriteOlder           0  Key Management Service
16,384      0 OverwriteOlder           4  ODiag
16,384      0 OverwriteOlder         389  OSession Security
15,168      0 OverwriteOlder      19,360  System
15,360      0 OverwriteOlder      15,828  Windows PowerShell
```

<span data-ttu-id="c866d-118">In diesem Beispiel wird die Überlauf Aktion aller Ereignisprotokolle auf dem lokalen Computer in über Schreibweise geändert.</span><span class="sxs-lookup"><span data-stu-id="c866d-118">This example changes the overflow action of all event logs on the local computer to OverwriteOlder.</span></span>

<span data-ttu-id="c866d-119">Der erste Befehl ruft die Protokollnamen aller Protokolle auf dem lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="c866d-119">The first command gets the log names of all of the logs on the local computer.</span></span>
<span data-ttu-id="c866d-120">Der zweite Befehl legt die Überlaufaktion fest.</span><span class="sxs-lookup"><span data-stu-id="c866d-120">The second command sets the overflow action.</span></span>
<span data-ttu-id="c866d-121">Der dritte Befehl zeigt die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="c866d-121">The third command displays the results.</span></span>

## <span data-ttu-id="c866d-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c866d-122">PARAMETERS</span></span>

### <span data-ttu-id="c866d-123">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="c866d-123">-ComputerName</span></span>
<span data-ttu-id="c866d-124">Gibt Remote Computer an.</span><span class="sxs-lookup"><span data-stu-id="c866d-124">Specifies remote computers.</span></span>
<span data-ttu-id="c866d-125">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="c866d-125">The default is the local computer.</span></span>

<span data-ttu-id="c866d-126">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) eines Remote Computers ein.</span><span class="sxs-lookup"><span data-stu-id="c866d-126">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>
<span data-ttu-id="c866d-127">Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c866d-127">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="c866d-128">Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="c866d-128">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="c866d-129">Sie können den *Computername* -Parameter von **Limit-EventLog** auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c866d-129">You can use the *ComputerName* parameter of **Limit-EventLog** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c866d-130">-LogName</span><span class="sxs-lookup"><span data-stu-id="c866d-130">-LogName</span></span>
<span data-ttu-id="c866d-131">Gibt die Ereignisprotokolle an.</span><span class="sxs-lookup"><span data-stu-id="c866d-131">Specifies the event logs.</span></span>
<span data-ttu-id="c866d-132">Geben Sie den Protokollnamen (den Wert der Log-Eigenschaft, nicht %%amp;quot;LogDisplayName%%amp;quot;) von Ereignisprotokollen durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="c866d-132">Enter the log name (the value of the Log property; not the LogDisplayName) of one or more event logs, separated by commas.</span></span>
<span data-ttu-id="c866d-133">Platzhalterzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="c866d-133">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="c866d-134">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c866d-134">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c866d-135">-MaximumSize</span><span class="sxs-lookup"><span data-stu-id="c866d-135">-MaximumSize</span></span>
<span data-ttu-id="c866d-136">Gibt die maximale Größe der Ereignisprotokolle in Bytes an.</span><span class="sxs-lookup"><span data-stu-id="c866d-136">Specifies the maximum size of the event logs in bytes.</span></span>
<span data-ttu-id="c866d-137">Geben Sie einen Wert zwischen 64 KB (Kilobytes) und 4 GB (Gigabytes) ein.</span><span class="sxs-lookup"><span data-stu-id="c866d-137">Enter a value between 64 kilobytes (KB) and 4 gigabytes (GB).</span></span>
<span data-ttu-id="c866d-138">Der Wert muss durch 64 KB (65536) teilbar sein.</span><span class="sxs-lookup"><span data-stu-id="c866d-138">The value must be divisible by 64 KB (65536).</span></span>

<span data-ttu-id="c866d-139">Dieser Parameter gibt den Wert der **MaximumKilobytes** -Eigenschaft des **System. Diagnostics. EventLog** -Objekts an, das ein klassisches Ereignisprotokoll darstellt.</span><span class="sxs-lookup"><span data-stu-id="c866d-139">This parameter specifies the value of the **MaximumKilobytes** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c866d-140">-OverflowAction</span><span class="sxs-lookup"><span data-stu-id="c866d-140">-OverflowAction</span></span>
<span data-ttu-id="c866d-141">Gibt an, was geschieht, wenn das Ereignisprotokoll die maximale Größe erreicht.</span><span class="sxs-lookup"><span data-stu-id="c866d-141">Specifies what happens when the event log reaches its maximum size.</span></span>

<span data-ttu-id="c866d-142">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="c866d-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c866d-143">Donoyverwrite: vorhandene Einträge werden beibehalten, und neue Einträge werden verworfen.</span><span class="sxs-lookup"><span data-stu-id="c866d-143">DoNotOverwrite:  Existing entries are retained and new entries are discarded.</span></span>
- <span data-ttu-id="c866d-144">Overschreiteasbenötigter: jeder neue Eintrag überschreibt den ältesten Eintrag.</span><span class="sxs-lookup"><span data-stu-id="c866d-144">OverwriteAsNeeded:  Each new entry overwrites the oldest entry.</span></span>
- <span data-ttu-id="c866d-145">Overschreiteälter: neue Ereignisse überschreiben Ereignisse, die älter als der von der **MinimumRetentionDays** -Eigenschaft angegebene Wert sind.</span><span class="sxs-lookup"><span data-stu-id="c866d-145">OverwriteOlder:  New events overwrite events older than the value specified by the **MinimumRetentionDays** property.</span></span> <span data-ttu-id="c866d-146">Wenn keine Ereignisse vorhanden sind, die älter sind als durch den **MinimumRetentionDays** -Eigenschafts Wert angegeben, werden neue Ereignisse verworfen.</span><span class="sxs-lookup"><span data-stu-id="c866d-146">If there are no events older than specified by the **MinimumRetentionDays** property value, new events are discarded.</span></span>

<span data-ttu-id="c866d-147">Dieser Parameter gibt den Wert der **OverflowAction** -Eigenschaft des **System. Diagnostics. EventLog** -Objekts an, das ein klassisches Ereignisprotokoll darstellt.</span><span class="sxs-lookup"><span data-stu-id="c866d-147">This parameter specifies the value of the **OverflowAction** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Diagnostics.OverflowAction
Parameter Sets: (All)
Aliases: OFA
Accepted values: OverwriteOlder, OverwriteAsNeeded, DoNotOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c866d-148">-RetentionDays</span><span class="sxs-lookup"><span data-stu-id="c866d-148">-RetentionDays</span></span>
<span data-ttu-id="c866d-149">Gibt die Mindestanzahl von Tagen an, die ein Ereignis im Ereignisprotokoll bleiben muss.</span><span class="sxs-lookup"><span data-stu-id="c866d-149">Specifies the minimum number of days that an event must remain in the event log.</span></span>

<span data-ttu-id="c866d-150">Dieser Parameter gibt den Wert der **MinimumRetentionDays** -Eigenschaft des **System. Diagnostics. EventLog** -Objekts an, das ein klassisches Ereignisprotokoll darstellt.</span><span class="sxs-lookup"><span data-stu-id="c866d-150">This parameter specifies the value of the **MinimumRetentionDays** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: MRD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c866d-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c866d-151">-Confirm</span></span>
<span data-ttu-id="c866d-152">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="c866d-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c866d-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c866d-153">-WhatIf</span></span>
<span data-ttu-id="c866d-154">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c866d-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c866d-155">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c866d-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c866d-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c866d-156">CommonParameters</span></span>
<span data-ttu-id="c866d-157">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c866d-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c866d-158">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c866d-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c866d-159">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c866d-159">INPUTS</span></span>

### <span data-ttu-id="c866d-160">Keine</span><span class="sxs-lookup"><span data-stu-id="c866d-160">None</span></span>
<span data-ttu-id="c866d-161">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="c866d-161">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c866d-162">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c866d-162">OUTPUTS</span></span>

### <span data-ttu-id="c866d-163">Keine</span><span class="sxs-lookup"><span data-stu-id="c866d-163">None</span></span>
<span data-ttu-id="c866d-164">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c866d-164">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c866d-165">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c866d-165">NOTES</span></span>

* <span data-ttu-id="c866d-166">Wenn Sie dieses Cmdlet unter Windows Vista und höheren Versionen von Windows verwenden möchten, öffnen Sie Windows PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="c866d-166">To use this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="c866d-167">Dieses Cmdlet ändert die Eigenschaften des **System. Diagnostics. EventLog** -Objekts, das ein klassisches Ereignisprotokoll darstellt.</span><span class="sxs-lookup"><span data-stu-id="c866d-167">This cmdlet changes the properties of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>
<span data-ttu-id="c866d-168">Um die aktuellen Einstellungen der Ereignisprotokoll Eigenschaften anzuzeigen, geben Sie ein `Get-EventLog -List` .</span><span class="sxs-lookup"><span data-stu-id="c866d-168">To see the current settings of the event log properties, type `Get-EventLog -List`.</span></span>

*

## <span data-ttu-id="c866d-169">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c866d-169">RELATED LINKS</span></span>

[<span data-ttu-id="c866d-170">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="c866d-170">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="c866d-171">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="c866d-171">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="c866d-172">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="c866d-172">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="c866d-173">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="c866d-173">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="c866d-174">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="c866d-174">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="c866d-175">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="c866d-175">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="c866d-176">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="c866d-176">Write-EventLog</span></span>](Write-EventLog.md)
