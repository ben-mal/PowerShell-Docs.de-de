---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: 54ba1d7db60db7b4bb64f3161bba9c1fba124219
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212196"
---
# <span data-ttu-id="03f93-103">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="03f93-103">Test-Connection</span></span>

## <span data-ttu-id="03f93-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="03f93-104">SYNOPSIS</span></span>
<span data-ttu-id="03f93-105">Sendet ICMP-Echo Anforderungs Pakete (Pings) an einen oder mehrere Computer.</span><span class="sxs-lookup"><span data-stu-id="03f93-105">Sends ICMP echo request packets, or pings, to one or more computers.</span></span>

## <span data-ttu-id="03f93-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="03f93-106">SYNTAX</span></span>

### <span data-ttu-id="03f93-107">Pingcount (Standard)</span><span class="sxs-lookup"><span data-stu-id="03f93-107">PingCount (Default)</span></span>

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Count <Int32>] [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="03f93-108">Pingfort setzt</span><span class="sxs-lookup"><span data-stu-id="03f93-108">PingContinues</span></span>

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-Continues] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="03f93-109">Detectionofmtusize</span><span class="sxs-lookup"><span data-stu-id="03f93-109">DetectionOfMTUSize</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -MTUSizeDetect [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="03f93-110">TraceRoute</span><span class="sxs-lookup"><span data-stu-id="03f93-110">TraceRoute</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-TimeoutSeconds <Int32>] [-TargetName] <String[]> -Traceroute [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="03f93-111">Connectionbytcpport</span><span class="sxs-lookup"><span data-stu-id="03f93-111">ConnectionByTCPPort</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -TCPPort <Int32> [-Quiet] [<CommonParameters>]
```

## <span data-ttu-id="03f93-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="03f93-112">DESCRIPTION</span></span>

<span data-ttu-id="03f93-113">Das `Test-Connection` -Cmdlet sendet ICMP (Internet Control Message Protocol)-Echo Anforderungs Pakete (Pings) an einen oder mehrere Remote Computer und gibt die Echo Antwort Antworten zurück.</span><span class="sxs-lookup"><span data-stu-id="03f93-113">The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies.</span></span> <span data-ttu-id="03f93-114">Mit diesem Cmdlet können Sie ermitteln, ob ein bestimmter Computer über ein IP-Netzwerk kontaktiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="03f93-114">You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.</span></span>

<span data-ttu-id="03f93-115">Sie können mit den Parametern von `Test-Connection` sowohl den sendenden als auch den empfangenden Computer angeben, den Befehl als Hintergrund Auftrag ausführen, ein Timeout und eine Anzahl von Pings festlegen und die Verbindung und die Authentifizierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="03f93-115">You can use the parameters of `Test-Connection` to specify both the sending and receiving computers, to run the command as a background job, to set a time-out and number of pings, and to configure the connection and authentication.</span></span>

<span data-ttu-id="03f93-116">Im Gegensatz zum vertrauten **Ping** -Befehl `Test-Connection` gibt ein **testconnectioncommand + pingreport** -Objekt zurück, das Sie in PowerShell untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="03f93-116">Unlike the familiar **ping** command, `Test-Connection` returns a **TestConnectionCommand+PingReport** object that you can investigate in PowerShell.</span></span> <span data-ttu-id="03f93-117">Der **quiet** -Parameter gibt für jede getestete Verbindung einen **booleschen** Wert in einem **System. Boolean** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="03f93-117">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object for each tested connection.</span></span> <span data-ttu-id="03f93-118">Wenn mehrere Verbindungen getestet werden, wird ein Array von **booleschen** Werten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="03f93-118">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="03f93-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="03f93-119">EXAMPLES</span></span>

### <span data-ttu-id="03f93-120">Beispiel 1: Senden von ECHO Anforderungen an einen Remote Computer</span><span class="sxs-lookup"><span data-stu-id="03f93-120">Example 1: Send echo requests to a remote computer</span></span>

<span data-ttu-id="03f93-121">In diesem Beispiel werden Echo Request-Pakete vom lokalen Computer an den Server01-Computer gesendet.</span><span class="sxs-lookup"><span data-stu-id="03f93-121">This example sends echo request packets from the local computer to the Server01 computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -IPv4
```

```Output
Pinging Server01 [10.59.137.44] with 32 bytes of data:
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Ping complete.

Source     Destination Replies
------     ----------- -------
Server01   Server01    {System.Net.NetworkInformation.PingReply, System.Net.NetworkInformation ...
```

<span data-ttu-id="03f93-122">`Test-Connection` verwendet den **TargetName** -Parameter, um den Server01-Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="03f93-122">`Test-Connection` uses the **TargetName** parameter to specify the Server01 computer.</span></span> <span data-ttu-id="03f93-123">Der **IPv4** -Parameter gibt das Protokoll für den Test an.</span><span class="sxs-lookup"><span data-stu-id="03f93-123">The **IPv4** parameter specifies the protocol for the test.</span></span>

<span data-ttu-id="03f93-124">Die Ping-Ausgabe wird an den **Informationsdaten** Strom gesendet, während das **testconnectioncommand + pingreport** -Objekt an den **Success** -Stream gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="03f93-124">The ping output is sent to the **Information** stream while the **TestConnectionCommand+PingReport** object sent to the **Success** stream.</span></span> <span data-ttu-id="03f93-125">Weitere Informationen zu den Ausgabestreams finden Sie unter [about_Redirection](../microsoft.powershell.core/about/about_redirection.md).</span><span class="sxs-lookup"><span data-stu-id="03f93-125">For more information about the output streams, see [about_Redirection](../microsoft.powershell.core/about/about_redirection.md).</span></span>

### <span data-ttu-id="03f93-126">Beispiel 2: Senden von ECHO Anforderungen an mehrere Computer</span><span class="sxs-lookup"><span data-stu-id="03f93-126">Example 2: Send echo requests to several computers</span></span>

<span data-ttu-id="03f93-127">In diesem Beispiel werden Pings vom lokalen Computer an mehrere Remote Computer gesendet.</span><span class="sxs-lookup"><span data-stu-id="03f93-127">This example sends pings from the local computer to several remote computers.</span></span>

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### <span data-ttu-id="03f93-128">Beispiel 3: Senden von ECHO Anforderungen von mehreren Computern an einen Computer</span><span class="sxs-lookup"><span data-stu-id="03f93-128">Example 3: Send echo requests from several computers to a computer</span></span>

<span data-ttu-id="03f93-129">In diesem Beispiel werden Pings von unterschiedlichen Quell Computern an einen einzelnen Remote Computer, SERVER01, gesendet.</span><span class="sxs-lookup"><span data-stu-id="03f93-129">This example sends pings from different source computers to a single remote computer, Server01.</span></span>

```powershell
Test-Connection -Source Server02, Server12, localhost -TargetName Server01
```

<span data-ttu-id="03f93-130">Verwenden Sie diesen Befehl, um die Wartezeit von Verbindungen von mehreren Punkten aus zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="03f93-130">Use this command format to test the latency of connections from multiple points.</span></span>

### <span data-ttu-id="03f93-131">Beispiel 4: Verwenden von Parametern zum Anpassen des Test Befehls</span><span class="sxs-lookup"><span data-stu-id="03f93-131">Example 4: Use parameters to customize the test command</span></span>

<span data-ttu-id="03f93-132">In diesem Beispiel werden die Parameter von verwendet `Test-Connection` , um den Befehl anzupassen.</span><span class="sxs-lookup"><span data-stu-id="03f93-132">This example uses the parameters of `Test-Connection` to customize the command.</span></span> <span data-ttu-id="03f93-133">Der lokale Computer sendet einen Pingtest an einen Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="03f93-133">The local computer sends a ping test to a remote computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

<span data-ttu-id="03f93-134">`Test-Connection` verwendet den **TargetName** -Parameter, um Server01 anzugeben.</span><span class="sxs-lookup"><span data-stu-id="03f93-134">`Test-Connection` uses the **TargetName** parameter to specify Server01.</span></span> <span data-ttu-id="03f93-135">Der **count** -Parameter gibt an, dass drei Pings mit einer **Verzögerung** von 2-Sekunden-Intervallen an den Server01-Computer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="03f93-135">The **Count** parameter specifies three pings are sent to the Server01 computer with a **Delay** of 2-second intervals.</span></span>

<span data-ttu-id="03f93-136">Sie können diese Optionen verwenden, wenn die Ping-Antwort erwartungsgemäß länger als üblich dauert, entweder aufgrund einer erweiterten Hopanzahl oder einer Netzwerk Bedingung mit hohem Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="03f93-136">You might use these options when the ping response is expected to take longer than usual, either because of an extended number of hops or a high-traffic network condition.</span></span>

### <span data-ttu-id="03f93-137">Beispiel 5: Ausführen eines Tests als Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="03f93-137">Example 5: Run a test as a background job</span></span>

<span data-ttu-id="03f93-138">Dieses Beispiel zeigt, wie Sie einen `Test-Connection` Befehl als PowerShell-Hintergrund Auftrag ausführen.</span><span class="sxs-lookup"><span data-stu-id="03f93-138">This example shows how to run a `Test-Connection` command as a PowerShell background job.</span></span>

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content "Servers.txt") }
if ($job.JobStateInfo.State -ne "Running") { $Results = Receive-Job $job }
```

<span data-ttu-id="03f93-139">Der `Start-Job` Befehl verwendet das `Test-Connection` Cmdlet, um viele Computer in einem Unternehmen zu pingen.</span><span class="sxs-lookup"><span data-stu-id="03f93-139">The `Start-Job` command uses the `Test-Connection` cmdlet to ping many computers in an enterprise.</span></span>
<span data-ttu-id="03f93-140">Der Wert des **TargetName** -Parameters ist ein `Get-Content` Befehl, der eine Liste mit Computernamen aus der `Servers.txt` Datei liest.</span><span class="sxs-lookup"><span data-stu-id="03f93-140">The value of the **TargetName** parameter is a `Get-Content` command that reads a list of computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="03f93-141">Der Befehl verwendet das `Start-Job` Cmdlet, um den Befehl als Hintergrund Auftrag auszuführen, und speichert den Auftrag in der `$job` Variablen.</span><span class="sxs-lookup"><span data-stu-id="03f93-141">The command uses the `Start-Job` cmdlet to run the command as a background job and it saves the job in the `$job` variable.</span></span>

<span data-ttu-id="03f93-142">`if`Mit dem Befehl wird überprüft, ob der Auftrag noch nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="03f93-142">The `if` command checks to see that the job isn't still running.</span></span> <span data-ttu-id="03f93-143">Wenn der Auftrag nicht ausgeführt wird, werden `Receive-Job` die Ergebnisse abgerufen und in der `$Results` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="03f93-143">If the job isn't running, `Receive-Job` gets the results and stores them in the `$Results` variable.</span></span>

### <span data-ttu-id="03f93-144">Beispiel 6: Erstellen einer Sitzung nur, wenn ein Verbindungstest erfolgreich ist</span><span class="sxs-lookup"><span data-stu-id="03f93-144">Example 6: Create a session only if a connection test succeeds</span></span>

<span data-ttu-id="03f93-145">In diesem Beispiel wird nur dann eine Sitzung auf dem Computer Server01 erstellt, wenn mindestens eines der an den Computer gesendeten Pings erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="03f93-145">This example creates a session on the Server01 computer only if at least one of the pings sent to the computer succeeds.</span></span>

```powershell
if (Test-Connection -TargetName Server01 -Quiet) {New-PSSession Server01}
```

<span data-ttu-id="03f93-146">Der `if` Befehl verwendet das `Test-Connection` Cmdlet, um den Server01-Computer zu pingen.</span><span class="sxs-lookup"><span data-stu-id="03f93-146">The `if` command uses the `Test-Connection` cmdlet to ping the Server01 computer.</span></span> <span data-ttu-id="03f93-147">Der Befehl verwendet den **quiet** -Parameter, der einen **booleschen** Wert anstelle eines **testconnectioncommand + pingreport** -Objekts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="03f93-147">The command uses the **Quiet** parameter, which returns a **Boolean** value, instead of a **TestConnectionCommand+PingReport** object.</span></span>

<span data-ttu-id="03f93-148">Der Wert ist, `$True` Wenn eine der vier Pings erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="03f93-148">The value is `$True` if any of the four pings succeed.</span></span> <span data-ttu-id="03f93-149">Wenn keines der Pings erfolgreich ist, ist der Wert `$False` .</span><span class="sxs-lookup"><span data-stu-id="03f93-149">If none of the pings succeed, the value is `$False`.</span></span>

<span data-ttu-id="03f93-150">Wenn der `Test-Connection` Befehl den Wert zurückgibt `$True` , verwendet der Befehl das `New-PSSession` Cmdlet, um die **PSSession** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="03f93-150">If the `Test-Connection` command returns a value of `$True`, the command uses the `New-PSSession` cmdlet to create the **PSSession** .</span></span>

### <span data-ttu-id="03f93-151">Beispiel 7: Verwenden des traceroute-Parameters</span><span class="sxs-lookup"><span data-stu-id="03f93-151">Example 7: Use the Traceroute parameter</span></span>

<span data-ttu-id="03f93-152">Ab PowerShell 6,0 ordnet der **traceroute** -Parameter eine Route zwischen dem lokalen Computer und dem Remote Ziel zu, das Sie mit dem **TargetName** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="03f93-152">Beginning in PowerShell 6.0, the **Traceroute** parameter maps a route between the local computer and the remote destination you specify with the **TargetName** parameter.</span></span>

```powershell
Test-Connection -TargetName www.microsoft.com -Traceroute | ForEach-Object {
  $_ | Format-Table Source, DestinationAddress, DestinationHost
  $_.Replies | ForEach-Object {
      $_ | Format-Table Hop, ReplyRouterAddress
      $_.PingReplies | Format-Table
  }
}
```

```Output
Tracing route to www.microsoft.com [96.6.27.90] over a maximum of 128 hops:
  1   0 ms   0 ms   0 ms   192.168.0.3 [192.168.0.3]
  2   0 ms   0 ms   0 ms   192.168.1.1 [192.168.1.1]
  3   3 ms   29 ms   4 ms   96.6.27.90 [96.6.27.90]
Trace complete.

Source      DestinationAddress DestinationHost   Replies
------      ------------------ ---------------   -------
SERVER01    96.6.27.90         www.microsoft.com {, , }

Hop ReplyRouterAddress
--- ------------------
  1 192.168.0.3

    Status Address      RoundtripTime Options Buffer
    ------ -------      ------------- ------- ------
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  2 192.168.1.1

    Status Address     RoundtripTime Options Buffer
    ------ -------     ------------- ------- ------
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  3 96.6.27.90

 Status Address    RoundtripTime Options                                   Buffer
 ------ -------    ------------- -------                                   ------
Success 96.6.27.90             3 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             2 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             4 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
```

<span data-ttu-id="03f93-153">Der `Test-Connection` Befehl verwendet den **traceroute** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="03f93-153">The `Test-Connection` command uses the **Traceroute** parameter.</span></span> <span data-ttu-id="03f93-154">Die Ergebnisse, bei denen es sich `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` um-Objekte handelt, werden an das `ForEach-Object` Cmdlet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="03f93-154">The results, which are `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` objects, are piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="03f93-155">`ForEach-Object` erstellt eine strukturierte Ausgabe der enthaltenen `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` Objekte und nachfolgenden `[System.Net.NetworkInformation.PingReply]` Objekte.</span><span class="sxs-lookup"><span data-stu-id="03f93-155">`ForEach-Object` creates a structured output of the contained `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` objects and subsequent `[System.Net.NetworkInformation.PingReply]` objects.</span></span>

## <span data-ttu-id="03f93-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="03f93-156">PARAMETERS</span></span>

### <span data-ttu-id="03f93-157">-BufferSize</span><span class="sxs-lookup"><span data-stu-id="03f93-157">-BufferSize</span></span>

<span data-ttu-id="03f93-158">Gibt die Größe des mit diesem Befehl gesendeten Puffers in Bytes an.</span><span class="sxs-lookup"><span data-stu-id="03f93-158">Specifies the size, in bytes, of the buffer sent with this command.</span></span> <span data-ttu-id="03f93-159">Der Standardwert ist 32.</span><span class="sxs-lookup"><span data-stu-id="03f93-159">The default value is 32.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-160">-Anzahl</span><span class="sxs-lookup"><span data-stu-id="03f93-160">-Count</span></span>

<span data-ttu-id="03f93-161">Gibt die Anzahl der zu sendenden Echoanforderungen an.</span><span class="sxs-lookup"><span data-stu-id="03f93-161">Specifies the number of echo requests to send.</span></span> <span data-ttu-id="03f93-162">Der Standardwert ist 4.</span><span class="sxs-lookup"><span data-stu-id="03f93-162">The default value is 4.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-163">-Verzögerung</span><span class="sxs-lookup"><span data-stu-id="03f93-163">-Delay</span></span>

<span data-ttu-id="03f93-164">Gibt das Intervall zwischen Pings in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="03f93-164">Specifies the interval between pings, in seconds.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-165">-DontFragment</span><span class="sxs-lookup"><span data-stu-id="03f93-165">-DontFragment</span></span>

<span data-ttu-id="03f93-166">Dieser Parameter legt das Flag " **nicht Fragment** " im IP-Header fest.</span><span class="sxs-lookup"><span data-stu-id="03f93-166">This parameter sets the **Don't Fragment** flag in the IP header.</span></span> <span data-ttu-id="03f93-167">Sie können diesen Parameter mit dem **bufferSize** -Parameter verwenden, um den Pfad der MTU-Größe zu testen.</span><span class="sxs-lookup"><span data-stu-id="03f93-167">You can use this parameter with the **BufferSize** parameter to test the Path MTU size.</span></span> <span data-ttu-id="03f93-168">Weitere Informationen zu Path MTU finden Sie im Artikel zur Ermittlung der [MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) in Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="03f93-168">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-169">-IPv4</span><span class="sxs-lookup"><span data-stu-id="03f93-169">-IPv4</span></span>

<span data-ttu-id="03f93-170">Erzwingt, dass das Cmdlet das IPv4-Protokoll für den Test verwendet.</span><span class="sxs-lookup"><span data-stu-id="03f93-170">Forces the cmdlet to use the IPv4 protocol for the test.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-171">-IPv6</span><span class="sxs-lookup"><span data-stu-id="03f93-171">-IPv6</span></span>

<span data-ttu-id="03f93-172">Erzwingt, dass das Cmdlet das IPv6-Protokoll für den Test verwendet.</span><span class="sxs-lookup"><span data-stu-id="03f93-172">Forces the cmdlet to use the IPv6 protocol for the test.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-173">-MaxHops</span><span class="sxs-lookup"><span data-stu-id="03f93-173">-MaxHops</span></span>

<span data-ttu-id="03f93-174">Legt die maximale Anzahl von Hops fest, die eine ICMP-Anforderungs Nachricht senden kann.</span><span class="sxs-lookup"><span data-stu-id="03f93-174">Sets the maximum number of hops that an ICMP request message can be sent.</span></span> <span data-ttu-id="03f93-175">Der Standardwert wird vom Betriebssystem gesteuert.</span><span class="sxs-lookup"><span data-stu-id="03f93-175">The default value is controlled by the operating system.</span></span> <span data-ttu-id="03f93-176">Der Standardwert für Windows 10 ist 128 Hops.</span><span class="sxs-lookup"><span data-stu-id="03f93-176">The default value for Windows 10 is 128 hops.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-177">-Ping</span><span class="sxs-lookup"><span data-stu-id="03f93-177">-Ping</span></span>

<span data-ttu-id="03f93-178">Bewirkt, dass das Cmdlet einen Pingtest durchführen kann. Dies ist die Standardaktion.</span><span class="sxs-lookup"><span data-stu-id="03f93-178">Causes the cmdlet to do a ping test, which is the default action.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: Ping test
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-179">-Quiet</span><span class="sxs-lookup"><span data-stu-id="03f93-179">-Quiet</span></span>

<span data-ttu-id="03f93-180">Der **quiet** -Parameter gibt einen **booleschen** Wert in einem **System. Boolean** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="03f93-180">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object.</span></span> <span data-ttu-id="03f93-181">Durch die Verwendung dieses Parameters werden alle Fehler unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="03f93-181">Using this parameter suppresses all errors.</span></span>

<span data-ttu-id="03f93-182">Jede getestete Verbindung gibt einen **booleschen** Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="03f93-182">Each connection that's tested returns a **Boolean** value.</span></span> <span data-ttu-id="03f93-183">Wenn der **TargetName** -Parameter mehrere Computer angibt, wird ein Array von **booleschen** Werten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="03f93-183">If the **TargetName** parameter specifies multiple computers, an array of **Boolean** values is returned.</span></span>

<span data-ttu-id="03f93-184">Wenn **ein** Ping erfolgreich ist, `$True` wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="03f93-184">If **any** ping succeeds, `$True` is returned.</span></span>

<span data-ttu-id="03f93-185">Wenn **alle** Pings fehlschlagen, `$False` wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="03f93-185">If **all** pings fail, `$False` is returned.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-186">-Resolvedestination</span><span class="sxs-lookup"><span data-stu-id="03f93-186">-ResolveDestination</span></span>

<span data-ttu-id="03f93-187">Bewirkt, dass das Cmdlet versucht, den DNS-Namen des Ziels aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="03f93-187">Causes the cmdlet to attempt to resolve the DNS name of the target.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-188">-Source</span><span class="sxs-lookup"><span data-stu-id="03f93-188">-Source</span></span>

<span data-ttu-id="03f93-189">Gibt die Namen der Computer an, von denen der Ping stammt.</span><span class="sxs-lookup"><span data-stu-id="03f93-189">Specifies the names of the computers where the ping originates.</span></span> <span data-ttu-id="03f93-190">Geben Sie eine durch Trennzeichen getrennte Liste von Computernamen ein.</span><span class="sxs-lookup"><span data-stu-id="03f93-190">Enter a comma-separated list of computer names.</span></span> <span data-ttu-id="03f93-191">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="03f93-191">The default is the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: PingCount, PingContinues, TraceRoute, ConnectionByTCPPort
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-192">-TargetName</span><span class="sxs-lookup"><span data-stu-id="03f93-192">-TargetName</span></span>

<span data-ttu-id="03f93-193">Gibt die zu testenden Computer an.</span><span class="sxs-lookup"><span data-stu-id="03f93-193">Specifies the computers to test.</span></span> <span data-ttu-id="03f93-194">Geben Sie die Computernamen oder IP-Adressen im IPv4- oder IPv6-Format ein.</span><span class="sxs-lookup"><span data-stu-id="03f93-194">Type the computer names or type IP addresses in IPv4 or IPv6 format.</span></span> <span data-ttu-id="03f93-195">Platzhalter Zeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="03f93-195">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="03f93-196">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03f93-196">This parameter is required.</span></span> <span data-ttu-id="03f93-197">**Computername** ist ein Alias für diesen Parameter.</span><span class="sxs-lookup"><span data-stu-id="03f93-197">**ComputerName** is an alias for this parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ComputerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-198">-TcpPort</span><span class="sxs-lookup"><span data-stu-id="03f93-198">-TCPPort</span></span>

<span data-ttu-id="03f93-199">Gibt die TCP-Portnummer an, die im TCP-Verbindungstest verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="03f93-199">Specifies the TCP port number on the target to be used in the TCP connection test.</span></span> <span data-ttu-id="03f93-200">Mit dem-Cmdlet wird versucht, eine TCP-Verbindung mit dem angegebenen Port auf dem Ziel herzustellen.</span><span class="sxs-lookup"><span data-stu-id="03f93-200">The cmdlet will attempt to make a TCP connection to the specified port on the target.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ConnectionByTCPPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-201">-TimeoutSeconds</span><span class="sxs-lookup"><span data-stu-id="03f93-201">-TimeoutSeconds</span></span>

<span data-ttu-id="03f93-202">Legt den Timeout Wert für den Test fest.</span><span class="sxs-lookup"><span data-stu-id="03f93-202">Sets the timeout value for the test.</span></span> <span data-ttu-id="03f93-203">Der Test schlägt fehl, wenn eine Antwort nicht empfangen wird, bevor das Timeout abläuft.</span><span class="sxs-lookup"><span data-stu-id="03f93-203">The test fails if a response isn't received before the timeout expires.</span></span> <span data-ttu-id="03f93-204">Der Standardwert beträgt fünf Sekunden.</span><span class="sxs-lookup"><span data-stu-id="03f93-204">The default is five seconds.</span></span>

<span data-ttu-id="03f93-205">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="03f93-205">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5 seconds
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-206">-Traceroute</span><span class="sxs-lookup"><span data-stu-id="03f93-206">-Traceroute</span></span>

<span data-ttu-id="03f93-207">Bewirkt, dass das Cmdlet einen traceroute-Test durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="03f93-207">Causes the cmdlet to do a traceroute test.</span></span> <span data-ttu-id="03f93-208">Wenn dieser Parameter verwendet wird, gibt das Cmdlet ein- `TestConnectionCommand+TraceRouteResult` Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="03f93-208">When this parameter is used, the cmdlet returns a `TestConnectionCommand+TraceRouteResult` object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TraceRoute
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-209">-Wird fortgesetzt</span><span class="sxs-lookup"><span data-stu-id="03f93-209">-Continues</span></span>

<span data-ttu-id="03f93-210">Bewirkt, dass das Cmdlet immer dann Ping-Anforderungen sendet.</span><span class="sxs-lookup"><span data-stu-id="03f93-210">Causes the cmdlet to send ping requests continuously.</span></span> <span data-ttu-id="03f93-211">Dieser Parameter kann nicht mit dem **count** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="03f93-211">This parameter can't be used with the **Count** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-212">-Mtusizedetect</span><span class="sxs-lookup"><span data-stu-id="03f93-212">-MTUSizeDetect</span></span>

<span data-ttu-id="03f93-213">Dieser Parameter wird verwendet, um den Pfad der MTU-Größe zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="03f93-213">This parameter is used to discover the Path MTU size.</span></span> <span data-ttu-id="03f93-214">Das-Cmdlet gibt ein **PingReply # mtusize** -Objekt zurück, das den Pfad der MTU-Größe zum Ziel enthält.</span><span class="sxs-lookup"><span data-stu-id="03f93-214">The cmdlet returns a **PingReply#MTUSize** object that contains the Path MTU size to the target.</span></span> <span data-ttu-id="03f93-215">Weitere Informationen zu Path MTU finden Sie im Artikel zur Ermittlung der [MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) in Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="03f93-215">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetectionOfMTUSize
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03f93-216">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="03f93-216">CommonParameters</span></span>

<span data-ttu-id="03f93-217">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="03f93-217">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="03f93-218">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="03f93-218">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="03f93-219">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="03f93-219">INPUTS</span></span>

### <span data-ttu-id="03f93-220">Keine</span><span class="sxs-lookup"><span data-stu-id="03f93-220">None</span></span>

<span data-ttu-id="03f93-221">Eingaben können nicht an dieses Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="03f93-221">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="03f93-222">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="03f93-222">OUTPUTS</span></span>

### <span data-ttu-id="03f93-223">Testconnectioncommand + pingreport, testconnectioncommand + tracerouteresult, Boolean, PingReply # mtusize</span><span class="sxs-lookup"><span data-stu-id="03f93-223">TestConnectionCommand+PingReport, TestConnectionCommand+TraceRouteResult, Boolean, PingReply#MTUSize</span></span>

<span data-ttu-id="03f93-224">Wenn Sie den **quiet** -Parameter angeben, wird ein **boolescher** Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="03f93-224">If you specify the **Quiet** parameter, it returns a **Boolean** value.</span></span> <span data-ttu-id="03f93-225">Wenn mehrere Verbindungen getestet werden, wird ein Array von **booleschen** Werten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="03f93-225">If multiple connections are tested, an array of **Boolean** values is returned.</span></span> <span data-ttu-id="03f93-226">Andernfalls wird `Test-Connection` für jeden Ping ein **testconnectioncommand + pingreport** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="03f93-226">Otherwise, `Test-Connection` returns a **TestConnectionCommand+PingReport** object for each ping.</span></span>

## <span data-ttu-id="03f93-227">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="03f93-227">NOTES</span></span>

## <span data-ttu-id="03f93-228">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="03f93-228">RELATED LINKS</span></span>

[<span data-ttu-id="03f93-229">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="03f93-229">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="03f93-230">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="03f93-230">Stop-Computer</span></span>](Stop-Computer.md)
