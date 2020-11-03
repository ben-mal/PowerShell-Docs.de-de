---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: 04e9e47055610ef8120b44f2418a0843e5901062
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210588"
---
# <span data-ttu-id="d023a-103">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="d023a-103">Test-Connection</span></span>

## <span data-ttu-id="d023a-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d023a-104">SYNOPSIS</span></span>
<span data-ttu-id="d023a-105">Sendet ICMP-Echo Anforderungs Pakete (Pings) an einen oder mehrere Computer.</span><span class="sxs-lookup"><span data-stu-id="d023a-105">Sends ICMP echo request packets, or pings, to one or more computers.</span></span>

## <span data-ttu-id="d023a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d023a-106">SYNTAX</span></span>

### <span data-ttu-id="d023a-107">Defaultping (Standard)</span><span class="sxs-lookup"><span data-stu-id="d023a-107">DefaultPing (Default)</span></span>

```
Test-Connection [-TargetName] <string[]> [-Ping] [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-Count <int>] [-Delay <int>] [-BufferSize <int>]
 [-DontFragment] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="d023a-108">Repeatping</span><span class="sxs-lookup"><span data-stu-id="d023a-108">RepeatPing</span></span>

```
Test-Connection [-TargetName] <string[]> -Repeat [-Ping] [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-Delay <int>] [-BufferSize <int>] [-DontFragment]
 [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="d023a-109">Mtusizedetect</span><span class="sxs-lookup"><span data-stu-id="d023a-109">MtuSizeDetect</span></span>

```
Test-Connection [-TargetName] <string[]> -MtuSize [-IPv4] [-IPv6] [-ResolveDestination]
 [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="d023a-110">TraceRoute</span><span class="sxs-lookup"><span data-stu-id="d023a-110">TraceRoute</span></span>

```
Test-Connection [-TargetName] <string[]> -Traceroute [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="d023a-111">TcpPort</span><span class="sxs-lookup"><span data-stu-id="d023a-111">TcpPort</span></span>

```
Test-Connection [-TargetName] <string[]> -TcpPort <int> [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

## <span data-ttu-id="d023a-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d023a-112">DESCRIPTION</span></span>

<span data-ttu-id="d023a-113">Das `Test-Connection` -Cmdlet sendet ICMP (Internet Control Message Protocol)-Echo Anforderungs Pakete (Pings) an einen oder mehrere Remote Computer und gibt die Echo Antwort Antworten zurück.</span><span class="sxs-lookup"><span data-stu-id="d023a-113">The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies.</span></span> <span data-ttu-id="d023a-114">Mit diesem Cmdlet können Sie ermitteln, ob ein bestimmter Computer über ein IP-Netzwerk kontaktiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d023a-114">You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.</span></span>

<span data-ttu-id="d023a-115">Sie können mit den Parametern von `Test-Connection` sowohl den sendenden als auch den empfangenden Computer angeben, den Befehl als Hintergrund Auftrag ausführen, ein Timeout und eine Anzahl von Pings festlegen und die Verbindung und die Authentifizierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d023a-115">You can use the parameters of `Test-Connection` to specify both the sending and receiving computers, to run the command as a background job, to set a time-out and number of pings, and to configure the connection and authentication.</span></span>

<span data-ttu-id="d023a-116">Im Gegensatz zum vertrauten **Ping** -Befehl `Test-Connection` gibt ein **testconnectioncommand + Pingstatus** -Objekt zurück, das Sie in PowerShell untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="d023a-116">Unlike the familiar **ping** command, `Test-Connection` returns a **TestConnectionCommand+PingStatus** object that you can investigate in PowerShell.</span></span> <span data-ttu-id="d023a-117">Der **quiet** -Parameter gibt für jede getestete Verbindung einen **booleschen** Wert in einem **System. Boolean** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="d023a-117">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object for each tested connection.</span></span> <span data-ttu-id="d023a-118">Wenn mehrere Verbindungen getestet werden, wird ein Array von **booleschen** Werten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d023a-118">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="d023a-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d023a-119">EXAMPLES</span></span>

### <span data-ttu-id="d023a-120">Beispiel 1: Senden von ECHO Anforderungen an einen Remote Computer</span><span class="sxs-lookup"><span data-stu-id="d023a-120">Example 1: Send echo requests to a remote computer</span></span>

<span data-ttu-id="d023a-121">In diesem Beispiel werden Echo Request-Pakete vom lokalen Computer an den Server01-Computer gesendet.</span><span class="sxs-lookup"><span data-stu-id="d023a-121">This example sends echo request packets from the local computer to the Server01 computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -IPv4
```

```Output
   Destination: Server01

Ping Source           Address                   Latency BufferSize Status
                                                   (ms)        (B)
---- ------           -------                   ------- ---------- ------
   1 ADMIN1           10.59.137.44                   24         32 Success
   2 ADMIN1           10.59.137.44                   39         32 Success
   3 ADMIN1           *                               *          * TimedOut
   4 ADMIN1           10.59.137.44                   28         32 Success
```

<span data-ttu-id="d023a-122">`Test-Connection` verwendet den **TargetName** -Parameter, um den Server01-Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d023a-122">`Test-Connection` uses the **TargetName** parameter to specify the Server01 computer.</span></span> <span data-ttu-id="d023a-123">Der **IPv4** -Parameter gibt das Protokoll für den Test an.</span><span class="sxs-lookup"><span data-stu-id="d023a-123">The **IPv4** parameter specifies the protocol for the test.</span></span>

<span data-ttu-id="d023a-124">Eine Reihe von **Test ConnectionCommand + Pingstatus** -Objekten wird an den Ausgabestream gesendet, ein Objekt pro Ping-Antwort vom Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="d023a-124">A series of **TestConnectionCommand+PingStatus** objects are sent to the output stream, one object per ping reply from the target machine.</span></span>

### <span data-ttu-id="d023a-125">Beispiel 2: Senden von ECHO Anforderungen an mehrere Computer</span><span class="sxs-lookup"><span data-stu-id="d023a-125">Example 2: Send echo requests to several computers</span></span>

<span data-ttu-id="d023a-126">In diesem Beispiel werden Pings vom lokalen Computer an mehrere Remote Computer gesendet.</span><span class="sxs-lookup"><span data-stu-id="d023a-126">This example sends pings from the local computer to several remote computers.</span></span>

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### <span data-ttu-id="d023a-127">Beispiel 3: Verwenden von Parametern zum Anpassen des Test Befehls</span><span class="sxs-lookup"><span data-stu-id="d023a-127">Example 3: Use parameters to customize the test command</span></span>

<span data-ttu-id="d023a-128">In diesem Beispiel werden die Parameter von verwendet `Test-Connection` , um den Befehl anzupassen.</span><span class="sxs-lookup"><span data-stu-id="d023a-128">This example uses the parameters of `Test-Connection` to customize the command.</span></span> <span data-ttu-id="d023a-129">Der lokale Computer sendet einen Pingtest an einen Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="d023a-129">The local computer sends a ping test to a remote computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

<span data-ttu-id="d023a-130">`Test-Connection` verwendet den **TargetName** -Parameter, um Server01 anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d023a-130">`Test-Connection` uses the **TargetName** parameter to specify Server01.</span></span> <span data-ttu-id="d023a-131">Der **count** -Parameter gibt an, dass drei Pings mit einer **Verzögerung** von 2-Sekunden-Intervallen an den Server01-Computer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d023a-131">The **Count** parameter specifies three pings are sent to the Server01 computer with a **Delay** of 2-second intervals.</span></span>

<span data-ttu-id="d023a-132">Sie können diese Optionen verwenden, wenn die Ping-Antwort erwartungsgemäß länger als üblich dauert, entweder aufgrund einer erweiterten Hopanzahl oder einer Netzwerk Bedingung mit hohem Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="d023a-132">You might use these options when the ping response is expected to take longer than usual, either because of an extended number of hops or a high-traffic network condition.</span></span>

### <span data-ttu-id="d023a-133">Beispiel 4: Ausführen eines Tests als Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="d023a-133">Example 4: Run a test as a background job</span></span>

<span data-ttu-id="d023a-134">Dieses Beispiel zeigt, wie Sie einen `Test-Connection` Befehl als PowerShell-Hintergrund Auftrag ausführen.</span><span class="sxs-lookup"><span data-stu-id="d023a-134">This example shows how to run a `Test-Connection` command as a PowerShell background job.</span></span>

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content -Path "Servers.txt") }
$Results = Receive-Job $job -Wait
```

<span data-ttu-id="d023a-135">Der `Start-Job` Befehl verwendet das `Test-Connection` Cmdlet, um viele Computer in einem Unternehmen zu pingen.</span><span class="sxs-lookup"><span data-stu-id="d023a-135">The `Start-Job` command uses the `Test-Connection` cmdlet to ping many computers in an enterprise.</span></span>
<span data-ttu-id="d023a-136">Der Wert des **TargetName** -Parameters ist ein `Get-Content` Befehl, der eine Liste mit Computernamen aus der `Servers.txt` Datei liest.</span><span class="sxs-lookup"><span data-stu-id="d023a-136">The value of the **TargetName** parameter is a `Get-Content` command that reads a list of computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="d023a-137">Der Befehl verwendet das `Start-Job` Cmdlet, um den Befehl als Hintergrund Auftrag auszuführen, und speichert den Auftrag in der `$job` Variablen.</span><span class="sxs-lookup"><span data-stu-id="d023a-137">The command uses the `Start-Job` cmdlet to run the command as a background job and it saves the job in the `$job` variable.</span></span>

<span data-ttu-id="d023a-138">Der `Receive-Job` -Befehl wird an den, `-Wait` bis der Auftrag abgeschlossen ist, und ruft dann die Ergebnisse ab und speichert Sie in der `$Results` Variablen.</span><span class="sxs-lookup"><span data-stu-id="d023a-138">The `Receive-Job` command is instructed to `-Wait` until the job is completed, and then gets the results and stores them in the `$Results` variable.</span></span>

### <span data-ttu-id="d023a-139">Beispiel 5: Erstellen einer Sitzung nur, wenn ein Verbindungstest erfolgreich ist</span><span class="sxs-lookup"><span data-stu-id="d023a-139">Example 5: Create a session only if a connection test succeeds</span></span>

<span data-ttu-id="d023a-140">In diesem Beispiel wird nur dann eine Sitzung auf dem Computer Server01 erstellt, wenn mindestens eines der an den Computer gesendeten Pings erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="d023a-140">This example creates a session on the Server01 computer only if at least one of the pings sent to the computer succeeds.</span></span>

```powershell
if (Test-Connection -TargetName Server01 -Quiet) { New-PSSession -ComputerName Server01 }
```

<span data-ttu-id="d023a-141">Das `Test-Connection` Cmdlet Pingt den `Server01` Computer mit dem angegebenen **quiet** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d023a-141">The `Test-Connection` cmdlet pings the `Server01` computer, with the **Quiet** parameter provided.</span></span>
<span data-ttu-id="d023a-142">Der resultierende Wert ist, `$True` Wenn eine der vier Pings erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="d023a-142">The resulting value is `$True` if any of the four pings succeed.</span></span> <span data-ttu-id="d023a-143">Wenn keines der Pings erfolgreich ist, ist der Wert `$False` .</span><span class="sxs-lookup"><span data-stu-id="d023a-143">If none of the pings succeed, the value is `$False`.</span></span>

<span data-ttu-id="d023a-144">Wenn der `Test-Connection` Befehl den Wert zurückgibt `$True` , verwendet der Befehl das `New-PSSession` Cmdlet, um die **PSSession** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d023a-144">If the `Test-Connection` command returns a value of `$True`, the command uses the `New-PSSession` cmdlet to create the **PSSession** .</span></span>

### <span data-ttu-id="d023a-145">Beispiel 6: Verwenden des traceroute-Parameters</span><span class="sxs-lookup"><span data-stu-id="d023a-145">Example 6: Use the Traceroute parameter</span></span>

<span data-ttu-id="d023a-146">Mit dem Parameter **traceroute** , der in PowerShell 6,0 eingeführt wurde, wird eine Route zwischen dem lokalen Computer und dem Remote Ziel, das Sie angeben, mit dem **TargetName** -Parameter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d023a-146">Introduced in PowerShell 6.0, the **Traceroute** parameter maps a route between the local computer and the remote destination you specify with the **TargetName** parameter.</span></span>

```powershell
Test-Connection -TargetName www.google.com -Traceroute
```

```Output
   Target: google.com

Hop Hostname                  Ping Latency Status           Source       TargetAddress
                                      (ms)
--- --------                  ---- ------- ------           ------       -------------
  1 172.20.0.1                   1       4 Success          Lira         172.217.9.174
  1 172.20.0.1                   2       3 Success          Lira         172.217.9.174
  1 172.20.0.1                   3       2 Success          Lira         172.217.9.174
  2 12.108.153.193               1       3 Success          Lira         172.217.9.174
  2 12.108.153.193               2       3 Success          Lira         172.217.9.174
  2 12.108.153.193               3       2 Success          Lira         172.217.9.174
  3 12.244.85.177                1      11 Success          Lira         172.217.9.174
  3 12.244.85.177                2      12 Success          Lira         172.217.9.174
  3 12.244.85.177                3      12 Success          Lira         172.217.9.174
  4 *                            1      14 DestinationNetw… Lira         172.217.9.174
  4 *                            2       * TimedOut         Lira         172.217.9.174
  4 *                            3      20 DestinationNetw… Lira         172.217.9.174
  5 *                            1       * TimedOut         Lira         172.217.9.174
  5 *                            2      15 DestinationNetw… Lira         172.217.9.174
  5 *                            3       * TimedOut         Lira         172.217.9.174
  6 *                            1      18 DestinationNetw… Lira         172.217.9.174
  6 *                            2       * TimedOut         Lira         172.217.9.174
  6 *                            3      16 DestinationNetw… Lira         172.217.9.174
  7 *                            1       * TimedOut         Lira         172.217.9.174
  7 *                            2       * TimedOut         Lira         172.217.9.174
  7 *                            3       * TimedOut         Lira         172.217.9.174
  8 *                            1       * TimedOut         Lira         172.217.9.174
  8 *                            2       * TimedOut         Lira         172.217.9.174
  8 *                            3       * TimedOut         Lira         172.217.9.174
  9 *                            1       * TimedOut         Lira         172.217.9.174
  9 *                            2       * TimedOut         Lira         172.217.9.174
  9 *                            3       * TimedOut         Lira         172.217.9.174
 10 *                            1       * TimedOut         Lira         172.217.9.174
 10 *                            2       * TimedOut         Lira         172.217.9.174
 10 *                            3       * TimedOut         Lira         172.217.9.174
 11 172.217.9.174                1      23 Success          Lira         172.217.9.174
 11 172.217.9.174                2      21 Success          Lira         172.217.9.174
 11 172.217.9.174                3      22 Success          Lira         172.217.9.174
```

<span data-ttu-id="d023a-147">Der `Test-Connection` Befehl wird mit dem **traceroute** -Parameter aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d023a-147">The `Test-Connection` command is called with the **Traceroute** parameter.</span></span> <span data-ttu-id="d023a-148">Die Ergebnisse, bei denen es sich `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceStatus]` um-Objekte handelt, werden an den **Erfolgs** Datenstrom ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="d023a-148">The results, which are `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceStatus]` objects, are output to the **Success** output stream.</span></span>

## <span data-ttu-id="d023a-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d023a-149">PARAMETERS</span></span>

### <span data-ttu-id="d023a-150">-BufferSize</span><span class="sxs-lookup"><span data-stu-id="d023a-150">-BufferSize</span></span>

<span data-ttu-id="d023a-151">Gibt die Größe des mit diesem Befehl gesendeten Puffers in Bytes an.</span><span class="sxs-lookup"><span data-stu-id="d023a-151">Specifies the size, in bytes, of the buffer sent with this command.</span></span> <span data-ttu-id="d023a-152">Der Standardwert ist 32.</span><span class="sxs-lookup"><span data-stu-id="d023a-152">The default value is 32.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing, RepeatPing
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d023a-153">-Wiederholen</span><span class="sxs-lookup"><span data-stu-id="d023a-153">-Repeat</span></span>

<span data-ttu-id="d023a-154">Bewirkt, dass das Cmdlet immer dann Ping-Anforderungen sendet.</span><span class="sxs-lookup"><span data-stu-id="d023a-154">Causes the cmdlet to send ping requests continuously.</span></span> <span data-ttu-id="d023a-155">Dieser Parameter kann nicht mit dem **count** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d023a-155">This parameter can't be used with the **Count** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RepeatPing
Aliases: Continuous

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d023a-156">-Anzahl</span><span class="sxs-lookup"><span data-stu-id="d023a-156">-Count</span></span>

<span data-ttu-id="d023a-157">Gibt die Anzahl der zu sendenden Echoanforderungen an.</span><span class="sxs-lookup"><span data-stu-id="d023a-157">Specifies the number of echo requests to send.</span></span> <span data-ttu-id="d023a-158">Der Standardwert ist 4.</span><span class="sxs-lookup"><span data-stu-id="d023a-158">The default value is 4.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d023a-159">-Verzögerung</span><span class="sxs-lookup"><span data-stu-id="d023a-159">-Delay</span></span>

<span data-ttu-id="d023a-160">Gibt das Intervall zwischen Pings in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="d023a-160">Specifies the interval between pings, in seconds.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing, RepeatPing
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d023a-161">-DontFragment</span><span class="sxs-lookup"><span data-stu-id="d023a-161">-DontFragment</span></span>

<span data-ttu-id="d023a-162">Dieser Parameter legt das Flag " **nicht Fragment** " im IP-Header fest.</span><span class="sxs-lookup"><span data-stu-id="d023a-162">This parameter sets the **Don't Fragment** flag in the IP header.</span></span> <span data-ttu-id="d023a-163">Sie können diesen Parameter mit dem **bufferSize** -Parameter verwenden, um den Pfad der MTU-Größe zu testen.</span><span class="sxs-lookup"><span data-stu-id="d023a-163">You can use this parameter with the **BufferSize** parameter to test the Path MTU size.</span></span> <span data-ttu-id="d023a-164">Weitere Informationen zu Path MTU finden Sie im Artikel zur Ermittlung der [MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) in Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="d023a-164">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultPing, RepeatPing
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d023a-165">-IPv4</span><span class="sxs-lookup"><span data-stu-id="d023a-165">-IPv4</span></span>

<span data-ttu-id="d023a-166">Erzwingt, dass das Cmdlet das IPv4-Protokoll für den Test verwendet.</span><span class="sxs-lookup"><span data-stu-id="d023a-166">Forces the cmdlet to use the IPv4 protocol for the test.</span></span>

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

### <span data-ttu-id="d023a-167">-IPv6</span><span class="sxs-lookup"><span data-stu-id="d023a-167">-IPv6</span></span>

<span data-ttu-id="d023a-168">Erzwingt, dass das Cmdlet das IPv6-Protokoll für den Test verwendet.</span><span class="sxs-lookup"><span data-stu-id="d023a-168">Forces the cmdlet to use the IPv6 protocol for the test.</span></span>

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

### <span data-ttu-id="d023a-169">-MaxHops</span><span class="sxs-lookup"><span data-stu-id="d023a-169">-MaxHops</span></span>

<span data-ttu-id="d023a-170">Legt die maximale Anzahl von Hops fest, die eine ICMP-Anforderungs Nachricht senden kann.</span><span class="sxs-lookup"><span data-stu-id="d023a-170">Sets the maximum number of hops that an ICMP request message can be sent.</span></span> <span data-ttu-id="d023a-171">Der Standardwert wird vom Betriebssystem gesteuert.</span><span class="sxs-lookup"><span data-stu-id="d023a-171">The default value is controlled by the operating system.</span></span> <span data-ttu-id="d023a-172">Der Standardwert für Windows 10 ist 128 Hops.</span><span class="sxs-lookup"><span data-stu-id="d023a-172">The default value for Windows 10 is 128 hops.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing, RepeatPing, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d023a-173">-Ping</span><span class="sxs-lookup"><span data-stu-id="d023a-173">-Ping</span></span>

<span data-ttu-id="d023a-174">Bewirkt, dass das Cmdlet einen Ping-Test durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="d023a-174">Causes the cmdlet to do a ping test.</span></span> <span data-ttu-id="d023a-175">Dies ist der Standardmodus für das- `Test-Connection` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d023a-175">This is the default mode for the `Test-Connection` cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultPing, RepeatPing
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d023a-176">-Quiet</span><span class="sxs-lookup"><span data-stu-id="d023a-176">-Quiet</span></span>

<span data-ttu-id="d023a-177">Der **quiet** -Parameter gibt einen **booleschen** Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="d023a-177">The **Quiet** parameter returns a **Boolean** value.</span></span> <span data-ttu-id="d023a-178">Durch die Verwendung dieses Parameters werden alle Fehler unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="d023a-178">Using this parameter suppresses all errors.</span></span>

<span data-ttu-id="d023a-179">Jede getestete Verbindung gibt einen **booleschen** Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="d023a-179">Each connection that's tested returns a **Boolean** value.</span></span> <span data-ttu-id="d023a-180">Wenn der **TargetName** -Parameter mehrere Computer angibt, wird ein Array von **booleschen** Werten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d023a-180">If the **TargetName** parameter specifies multiple computers, an array of **Boolean** values is returned.</span></span>

<span data-ttu-id="d023a-181">Wenn **ein** Ping an ein bestimmtes Ziel erfolgreich `$True` ist, wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d023a-181">If **any** ping to a given target succeeds, `$True` is returned.</span></span>

<span data-ttu-id="d023a-182">Wenn **alle** Pings an ein bestimmtes Ziel fehlschlagen, `$False` wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d023a-182">If **all** pings to a given target fail, `$False` is returned.</span></span>

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

### <span data-ttu-id="d023a-183">-Resolvedestination</span><span class="sxs-lookup"><span data-stu-id="d023a-183">-ResolveDestination</span></span>

<span data-ttu-id="d023a-184">Bewirkt, dass das Cmdlet versucht, den DNS-Namen des Ziels aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="d023a-184">Causes the cmdlet to attempt to resolve the DNS name of the target.</span></span> <span data-ttu-id="d023a-185">Wenn es in Verbindung mit dem **traceroute** -Parameter verwendet wird, werden die DNS-Namen aller zwischen Hosts nach Möglichkeit auch abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d023a-185">When used in conjunction with the **Traceroute** parameter, the DNS names of all intermediate hosts will also be retrieved, if possible.</span></span>

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

### <span data-ttu-id="d023a-186">-Source</span><span class="sxs-lookup"><span data-stu-id="d023a-186">-Source</span></span>

<span data-ttu-id="d023a-187">Gibt die Namen der Computer an, von denen der Ping stammt.</span><span class="sxs-lookup"><span data-stu-id="d023a-187">Specifies the names of the computers where the ping originates.</span></span> <span data-ttu-id="d023a-188">Geben Sie eine durch Trennzeichen getrennte Liste von Computernamen ein.</span><span class="sxs-lookup"><span data-stu-id="d023a-188">Enter a comma-separated list of computer names.</span></span> <span data-ttu-id="d023a-189">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="d023a-189">The default is the local computer.</span></span>

<span data-ttu-id="d023a-190">**Hinweis:** Dieser Parameter ist in PowerShell, Version 6 und höher, nicht funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="d023a-190">**NOTE:** This parameter is not functional in PowerShell versions 6 and up.</span></span>
<span data-ttu-id="d023a-191">Das Bereitstellen dieses Parameters hat keine Auswirkung auf den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d023a-191">Supplying this parameter will have no effect on the command.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultPing, RepeatPing, TraceRoute, TcpPort
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d023a-192">-TargetName</span><span class="sxs-lookup"><span data-stu-id="d023a-192">-TargetName</span></span>

<span data-ttu-id="d023a-193">Gibt die zu testenden Computer an.</span><span class="sxs-lookup"><span data-stu-id="d023a-193">Specifies the computer(s) to test.</span></span> <span data-ttu-id="d023a-194">Geben Sie die Computernamen oder IP-Adressen im IPv4- oder IPv6-Format ein.</span><span class="sxs-lookup"><span data-stu-id="d023a-194">Type the computer names or type IP addresses in IPv4 or IPv6 format.</span></span>

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

### <span data-ttu-id="d023a-195">-TimeoutSeconds</span><span class="sxs-lookup"><span data-stu-id="d023a-195">-TimeoutSeconds</span></span>

<span data-ttu-id="d023a-196">Legt den Timeout Wert für den Test fest.</span><span class="sxs-lookup"><span data-stu-id="d023a-196">Sets the timeout value for the test.</span></span> <span data-ttu-id="d023a-197">Der Test schlägt fehl, wenn eine Antwort nicht empfangen wird, bevor das Timeout abläuft.</span><span class="sxs-lookup"><span data-stu-id="d023a-197">The test fails if a response isn't received before the timeout expires.</span></span> <span data-ttu-id="d023a-198">Der Standardwert beträgt fünf Sekunden.</span><span class="sxs-lookup"><span data-stu-id="d023a-198">The default is five seconds.</span></span>

<span data-ttu-id="d023a-199">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d023a-199">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="d023a-200">-Traceroute</span><span class="sxs-lookup"><span data-stu-id="d023a-200">-Traceroute</span></span>

<span data-ttu-id="d023a-201">Bewirkt, dass das Cmdlet einen traceroute-Test durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="d023a-201">Causes the cmdlet to do a traceroute test.</span></span> <span data-ttu-id="d023a-202">Wenn dieser Parameter verwendet wird, gibt das Cmdlet ein- `TestConnectionCommand+TraceStatus` Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="d023a-202">When this parameter is used, the cmdlet returns a `TestConnectionCommand+TraceStatus` object.</span></span>

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

### <span data-ttu-id="d023a-203">-Mtusize</span><span class="sxs-lookup"><span data-stu-id="d023a-203">-MtuSize</span></span>

<span data-ttu-id="d023a-204">Dieser Parameter wird verwendet, um den Pfad der MTU-Größe zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="d023a-204">This parameter is used to discover the Path MTU size.</span></span> <span data-ttu-id="d023a-205">Das-Cmdlet gibt ein **PingReply # mtusize** -Objekt zurück, das den Pfad der MTU-Größe zum Ziel enthält.</span><span class="sxs-lookup"><span data-stu-id="d023a-205">The cmdlet returns a **PingReply#MTUSize** object that contains the Path MTU size to the target.</span></span> <span data-ttu-id="d023a-206">Weitere Informationen zu Path MTU finden Sie im Artikel zur Ermittlung der [MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) in Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="d023a-206">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MtuSizeDetect
Aliases: MtuSizeDetect

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d023a-207">-TcpPort</span><span class="sxs-lookup"><span data-stu-id="d023a-207">-TcpPort</span></span>

<span data-ttu-id="d023a-208">Gibt die TCP-Portnummer an, die im TCP-Verbindungstest verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d023a-208">Specifies the TCP port number on the target to be used in the TCP connection test.</span></span> <span data-ttu-id="d023a-209">Mit dem-Cmdlet wird versucht, eine TCP-Verbindung mit dem angegebenen Port auf dem Ziel herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d023a-209">The cmdlet will attempt to make a TCP connection to the specified port on the target.</span></span>

<span data-ttu-id="d023a-210">Wenn eine Verbindung hergestellt werden kann, `$True` wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d023a-210">If a connection can be made, `$True` will be returned.</span></span>

<span data-ttu-id="d023a-211">Wenn eine Verbindung nicht hergestellt werden kann, `$False` wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d023a-211">If a connection cannot be made, `$False` will be returned.</span></span>

```yaml
Type: System.Int32
Parameter Sets: TcpPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d023a-212">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d023a-212">CommonParameters</span></span>

<span data-ttu-id="d023a-213">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d023a-213">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d023a-214">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d023a-214">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d023a-215">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d023a-215">INPUTS</span></span>

### <span data-ttu-id="d023a-216">Keine</span><span class="sxs-lookup"><span data-stu-id="d023a-216">None</span></span>

<span data-ttu-id="d023a-217">Eingaben können nicht an dieses Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="d023a-217">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="d023a-218">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d023a-218">OUTPUTS</span></span>

### <span data-ttu-id="d023a-219">Testconnectioncommand + Pingstatus, testconnectioncommand + TRACESTATUS, Boolean, testconnectioncommand und pingmtustatus</span><span class="sxs-lookup"><span data-stu-id="d023a-219">TestConnectionCommand+PingStatus, TestConnectionCommand+TraceStatus, Boolean, TestConnectionCommand+PingMtuStatus</span></span>

<span data-ttu-id="d023a-220">Standardmäßig wird `Test-Connection` für jede Ping-Antwort ein **testconnectioncommand + Pingstatus** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d023a-220">By default, `Test-Connection` returns a **TestConnectionCommand+PingStatus** object for each ping reply.</span></span>

<span data-ttu-id="d023a-221">Wenn Sie den **traceroute** -Parameter angeben, gibt das Cmdlet ein **testconnectioncommand + TRACESTATUS** -Objekt für jede Ping-Antwort entlang der Route zurück.</span><span class="sxs-lookup"><span data-stu-id="d023a-221">If you specify the **Traceroute** parameter, the cmdlet will return a **TestConnectionCommand+TraceStatus** object for each ping reply along the route.</span></span>

<span data-ttu-id="d023a-222">Wenn Sie die Parameter " **quiet** " oder " **TcpPort** " angeben, wird ein **boolescher** Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d023a-222">If you specify the **Quiet** or **TcpPort** parameters, it returns a **Boolean** value.</span></span> <span data-ttu-id="d023a-223">Wenn mehrere Verbindungen getestet werden, wird ein Array von **booleschen** Werten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d023a-223">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="d023a-224">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d023a-224">NOTES</span></span>

## <span data-ttu-id="d023a-225">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d023a-225">RELATED LINKS</span></span>

[<span data-ttu-id="d023a-226">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="d023a-226">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="d023a-227">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="d023a-227">Stop-Computer</span></span>](Stop-Computer.md)
