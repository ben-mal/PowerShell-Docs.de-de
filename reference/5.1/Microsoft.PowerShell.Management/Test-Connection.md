---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: a8d3923db69a20cfada58391944b592cf999e6ef
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214335"
---
# <span data-ttu-id="06cc5-103">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="06cc5-103">Test-Connection</span></span>

## <span data-ttu-id="06cc5-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="06cc5-104">SYNOPSIS</span></span>
<span data-ttu-id="06cc5-105">Sendet ICMP-Echo Anforderungs Pakete (Pings) an einen oder mehrere Computer.</span><span class="sxs-lookup"><span data-stu-id="06cc5-105">Sends ICMP echo request packets, or pings, to one or more computers.</span></span>

## <span data-ttu-id="06cc5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="06cc5-106">SYNTAX</span></span>

### <span data-ttu-id="06cc5-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="06cc5-107">Default (Default)</span></span>

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-TimeToLive <Int32>]
 [-Delay <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="06cc5-108">`Source`</span><span class="sxs-lookup"><span data-stu-id="06cc5-108">Source</span></span>

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Credential <PSCredential>] [-Source] <String[]> [-Impersonation <ImpersonationLevel>]
 [-ThrottleLimit <Int32>] [-TimeToLive <Int32>] [-Delay <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="06cc5-109">Quiet</span><span class="sxs-lookup"><span data-stu-id="06cc5-109">Quiet</span></span>

```
Test-Connection [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-TimeToLive <Int32>] [-Delay <Int32>] [-Quiet]
 [<CommonParameters>]
```

## <span data-ttu-id="06cc5-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06cc5-110">DESCRIPTION</span></span>

<span data-ttu-id="06cc5-111">Das `Test-Connection` -Cmdlet sendet ICMP (Internet Control Message Protocol)-Echo Anforderungs Pakete (Pings) an einen oder mehrere Remote Computer und gibt die Echo Antwort Antworten zurück.</span><span class="sxs-lookup"><span data-stu-id="06cc5-111">The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies.</span></span> <span data-ttu-id="06cc5-112">Mit diesem Cmdlet können Sie ermitteln, ob ein bestimmter Computer über ein IP-Netzwerk kontaktiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="06cc5-112">You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.</span></span>

<span data-ttu-id="06cc5-113">Sie können mit den Parametern von `Test-Connection` sowohl den sendenden als auch den empfangenden Computer angeben, den Befehl als Hintergrund Auftrag ausführen, ein Timeout und eine Anzahl von Pings festlegen und die Verbindung und die Authentifizierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="06cc5-113">You can use the parameters of `Test-Connection` to specify both the sending and receiving computers, to run the command as a background job, to set a time-out and number of pings, and to configure the connection and authentication.</span></span>

<span data-ttu-id="06cc5-114">Im Gegensatz zum vertrauten **Ping** -Befehl `Test-Connection` gibt ein **Win32_PingStatus** Objekt zurück, das Sie in PowerShell untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="06cc5-114">Unlike the familiar **ping** command, `Test-Connection` returns a **Win32_PingStatus** object that you can investigate in PowerShell.</span></span> <span data-ttu-id="06cc5-115">Der **quiet** -Parameter gibt für jede getestete Verbindung einen **booleschen** Wert in einem **System. Boolean** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="06cc5-115">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object for each tested connection.</span></span> <span data-ttu-id="06cc5-116">Wenn mehrere Verbindungen getestet werden, wird ein Array von **booleschen** Werten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06cc5-116">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="06cc5-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="06cc5-117">EXAMPLES</span></span>

### <span data-ttu-id="06cc5-118">Beispiel 1: Senden von ECHO Anforderungen an einen Remote Computer</span><span class="sxs-lookup"><span data-stu-id="06cc5-118">Example 1: Send echo requests to a remote computer</span></span>

<span data-ttu-id="06cc5-119">In diesem Beispiel werden Echo Request-Pakete vom lokalen Computer an den Server01-Computer gesendet.</span><span class="sxs-lookup"><span data-stu-id="06cc5-119">This example sends echo request packets from the local computer to the Server01 computer.</span></span>

```powershell
Test-Connection -ComputerName Server01
```

```Output
Source        Destination     IPV4Address     IPV6Address  Bytes    Time(ms)
------        -----------     -----------     -----------  -----    --------
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       1
```

<span data-ttu-id="06cc5-120">`Test-Connection` verwendet den Computer **Name** -Parameter, um den Server01-Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="06cc5-120">`Test-Connection` uses the **ComputerName** parameter to specify the Server01 computer.</span></span>

### <span data-ttu-id="06cc5-121">Beispiel 2: Senden von ECHO Anforderungen an mehrere Computer</span><span class="sxs-lookup"><span data-stu-id="06cc5-121">Example 2: Send echo requests to several computers</span></span>

<span data-ttu-id="06cc5-122">In diesem Beispiel werden Pings vom lokalen Computer an mehrere Remote Computer gesendet.</span><span class="sxs-lookup"><span data-stu-id="06cc5-122">This example sends pings from the local computer to several remote computers.</span></span>

```powershell
Test-Connection -ComputerName Server01, Server02, Server12
```

### <span data-ttu-id="06cc5-123">Beispiel 3: Senden von ECHO Anforderungen von mehreren Computern an einen Computer</span><span class="sxs-lookup"><span data-stu-id="06cc5-123">Example 3: Send echo requests from several computers to a computer</span></span>

<span data-ttu-id="06cc5-124">In diesem Beispiel werden Pings von unterschiedlichen Quell Computern an einen einzelnen Remote Computer, SERVER01, gesendet.</span><span class="sxs-lookup"><span data-stu-id="06cc5-124">This example sends pings from different source computers to a single remote computer, Server01.</span></span>

```powershell
Test-Connection -Source Server02, Server12, localhost -ComputerName Server01 -Credential Domain01\Admin01
```

<span data-ttu-id="06cc5-125">`Test-Connection` verwendet den **Credential** -Parameter, um die Anmelde Informationen eines Benutzers anzugeben, der über die Berechtigung zum Senden einer Ping-Anforderung von den Quell Computern verfügt.</span><span class="sxs-lookup"><span data-stu-id="06cc5-125">`Test-Connection` uses the **Credential** parameter to specify the credentials of a user who has permission to send a ping request from the source computers.</span></span> <span data-ttu-id="06cc5-126">Verwenden Sie diesen Befehl, um die Wartezeit von Verbindungen von mehreren Punkten aus zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="06cc5-126">Use this command format to test the latency of connections from multiple points.</span></span>

### <span data-ttu-id="06cc5-127">Beispiel 4: Verwenden von Parametern zum Anpassen des Test Befehls</span><span class="sxs-lookup"><span data-stu-id="06cc5-127">Example 4: Use parameters to customize the test command</span></span>

<span data-ttu-id="06cc5-128">In diesem Beispiel werden die Parameter von verwendet `Test-Connection` , um den Befehl anzupassen.</span><span class="sxs-lookup"><span data-stu-id="06cc5-128">This example uses the parameters of `Test-Connection` to customize the command.</span></span> <span data-ttu-id="06cc5-129">Der lokale Computer sendet einen Pingtest an einen Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="06cc5-129">The local computer sends a ping test to a remote computer.</span></span>

```powershell
Test-Connection -ComputerName Server01 -Count 3 -Delay 2 -TTL 255 -BufferSize 256 -ThrottleLimit 32
```

<span data-ttu-id="06cc5-130">`Test-Connection` verwendet den **Computername** -Parameter, um Server01 anzugeben.</span><span class="sxs-lookup"><span data-stu-id="06cc5-130">`Test-Connection` uses the **ComputerName** parameter to specify Server01.</span></span> <span data-ttu-id="06cc5-131">Der **count** -Parameter gibt an, dass drei Pings mit einer **Verzögerung** von 2-Sekunden-Intervallen an den Server01-Computer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="06cc5-131">The **Count** parameter specifies three pings are sent to the Server01 computer with a **Delay** of 2-second intervals.</span></span>

<span data-ttu-id="06cc5-132">Sie können diese Optionen verwenden, wenn die Ping-Antwort erwartungsgemäß länger als üblich dauert, entweder aufgrund einer erweiterten Hopanzahl oder einer Netzwerk Bedingung mit hohem Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="06cc5-132">You might use these options when the ping response is expected to take longer than usual, either because of an extended number of hops or a high-traffic network condition.</span></span>

### <span data-ttu-id="06cc5-133">Beispiel 5: Ausführen eines Tests als Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="06cc5-133">Example 5: Run a test as a background job</span></span>

<span data-ttu-id="06cc5-134">Dieses Beispiel zeigt, wie Sie einen `Test-Connection` Befehl als PowerShell-Hintergrund Auftrag ausführen.</span><span class="sxs-lookup"><span data-stu-id="06cc5-134">This example shows how to run a `Test-Connection` command as a PowerShell background job.</span></span>

```powershell
$job = Test-Connection -ComputerName (Get-Content Servers.txt) -AsJob
if ($job.JobStateInfo.State -ne "Running") {$Results = Receive-Job $job}
```

<span data-ttu-id="06cc5-135">Der `Test-Connection` Befehl pingt viele Computer in einem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="06cc5-135">The `Test-Connection` command pings many computers in an enterprise.</span></span> <span data-ttu-id="06cc5-136">Der Wert des **Computername** -Parameters ist ein `Get-Content` Befehl, der eine Liste mit Computernamen aus der liest `Servers.txt file` .</span><span class="sxs-lookup"><span data-stu-id="06cc5-136">The value of the **ComputerName** parameter is a `Get-Content` command that reads a list of computer names from the `Servers.txt file`.</span></span> <span data-ttu-id="06cc5-137">Der Befehl verwendet den **AsJob** -Parameter, um den Befehl als Hintergrund Auftrag auszuführen, und speichert den Auftrag in der `$job` Variablen.</span><span class="sxs-lookup"><span data-stu-id="06cc5-137">The command uses the **AsJob** parameter to run the command as a background job and it saves the job in the `$job` variable.</span></span>

<span data-ttu-id="06cc5-138">`if`Mit dem Befehl wird überprüft, ob der Auftrag noch nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="06cc5-138">The `if` command checks to see that the job isn't still running.</span></span> <span data-ttu-id="06cc5-139">Wenn der Auftrag nicht ausgeführt wird, werden `Receive-Job` die Ergebnisse abgerufen und in der `$Results` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="06cc5-139">If the job isn't running, `Receive-Job` gets the results and stores them in the `$Results` variable.</span></span>

### <span data-ttu-id="06cc5-140">Beispiel 6: Pingen eines Remote Computers mit Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="06cc5-140">Example 6: Ping a remote computer with credentials</span></span>

<span data-ttu-id="06cc5-141">Dieser Befehl verwendet das `Test-Connection` Cmdlet, um einen Remote Computer zu pingen.</span><span class="sxs-lookup"><span data-stu-id="06cc5-141">This command uses the `Test-Connection` cmdlet to ping a remote computer.</span></span>

```powershell
Test-Connection Server55 -Credential Domain55\User01 -Impersonation Identify
```

<span data-ttu-id="06cc5-142">Der Befehl verwendet den **Credential** -Parameter, um ein Benutzerkonto anzugeben, das über die Berechtigung zum Pingen des Remote Computers und den Identitäts **Wechsel Parameter zum** Ändern der Identitätswechsel Ebene zur **Identifizierung** verfügt.</span><span class="sxs-lookup"><span data-stu-id="06cc5-142">The command uses the **Credential** parameter to specify a user account that has permission to ping the remote computer and the **Impersonation** parameter to change the impersonation level to **Identify** .</span></span>

### <span data-ttu-id="06cc5-143">Beispiel 7: Erstellen einer Sitzung nur dann, wenn ein Verbindungstest erfolgreich ist</span><span class="sxs-lookup"><span data-stu-id="06cc5-143">Example 7: Create a session only if a connection test succeeds</span></span>

<span data-ttu-id="06cc5-144">In diesem Beispiel wird nur dann eine Sitzung auf dem Computer Server01 erstellt, wenn mindestens eines der an den Computer gesendeten Pings erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="06cc5-144">This example creates a session on the Server01 computer only if at least one of the pings sent to the computer succeeds.</span></span>

```powershell
if (Test-Connection -ComputerName Server01 -Quiet) {New-PSSession Server01}
```

<span data-ttu-id="06cc5-145">Der `if` Befehl verwendet das `Test-Connection` Cmdlet, um den Server01-Computer zu pingen.</span><span class="sxs-lookup"><span data-stu-id="06cc5-145">The `if` command uses the `Test-Connection` cmdlet to ping the Server01 computer.</span></span> <span data-ttu-id="06cc5-146">Der Befehl verwendet den **quiet** -Parameter, der anstelle eines **Win32_PingStatus** Objekts einen **booleschen** Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="06cc5-146">The command uses the **Quiet** parameter, which returns a **Boolean** value, instead of a **Win32_PingStatus** object.</span></span> <span data-ttu-id="06cc5-147">Der Wert ist `$True` , wenn eine der vier Pings erfolgreich ist und ist, andernfalls `$False` .</span><span class="sxs-lookup"><span data-stu-id="06cc5-147">The value is `$True` if any of the four pings succeed and is, otherwise, `$False`.</span></span>

<span data-ttu-id="06cc5-148">Wenn der `Test-Connection` Befehl den Wert zurückgibt `$True` , verwendet der Befehl das `New-PSSession` Cmdlet, um die **PSSession** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="06cc5-148">If the `Test-Connection` command returns a value of `$True`, the command uses the `New-PSSession` cmdlet to create the **PSSession** .</span></span>

## <span data-ttu-id="06cc5-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="06cc5-149">PARAMETERS</span></span>

### <span data-ttu-id="06cc5-150">-AsJob</span><span class="sxs-lookup"><span data-stu-id="06cc5-150">-AsJob</span></span>

<span data-ttu-id="06cc5-151">Gibt an, dass dieses Cmdlet als Hintergrund Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="06cc5-151">Indicates that this cmdlet runs as a background job.</span></span>

<span data-ttu-id="06cc5-152">Um diesen Parameter verwenden zu können, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein. unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell mit der Option **als Administrator ausführen** öffnen.</span><span class="sxs-lookup"><span data-stu-id="06cc5-152">To use this parameter, the local and remote computers must be configured for remoting and, on Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as administrator** option.</span></span> <span data-ttu-id="06cc5-153">Weitere Informationen finden Sie unter [about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06cc5-153">For more information, see [about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md).</span></span>

<span data-ttu-id="06cc5-154">Wenn Sie den **AsJob** -Parameter angeben, gibt der Befehl sofort ein Objekt zurück, das den Hintergrund Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="06cc5-154">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="06cc5-155">Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="06cc5-155">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="06cc5-156">Der Auftrag wird auf dem lokalen Computer erstellt, und die Ergebnisse von Remotecomputern werden automatisch an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06cc5-156">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="06cc5-157">Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet `Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="06cc5-157">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="06cc5-158">Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) und [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md).</span><span class="sxs-lookup"><span data-stu-id="06cc5-158">For more information about PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06cc5-159">-BufferSize</span><span class="sxs-lookup"><span data-stu-id="06cc5-159">-BufferSize</span></span>

<span data-ttu-id="06cc5-160">Gibt die Größe des mit diesem Befehl gesendeten Puffers in Bytes an.</span><span class="sxs-lookup"><span data-stu-id="06cc5-160">Specifies the size, in bytes, of the buffer sent with this command.</span></span> <span data-ttu-id="06cc5-161">Der Standardwert ist 32.</span><span class="sxs-lookup"><span data-stu-id="06cc5-161">The default value is 32.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06cc5-162">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="06cc5-162">-ComputerName</span></span>

<span data-ttu-id="06cc5-163">Gibt die zu pingenden Computer an.</span><span class="sxs-lookup"><span data-stu-id="06cc5-163">Specifies the computers to ping.</span></span> <span data-ttu-id="06cc5-164">Geben Sie die Computernamen oder IP-Adressen im IPv4- oder IPv6-Format ein.</span><span class="sxs-lookup"><span data-stu-id="06cc5-164">Type the computer names or type IP addresses in IPv4 or IPv6 format.</span></span> <span data-ttu-id="06cc5-165">Platzhalterzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="06cc5-165">Wildcard characters are not permitted.</span></span> <span data-ttu-id="06cc5-166">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="06cc5-166">This parameter is required.</span></span>

<span data-ttu-id="06cc5-167">Dieser Parameter beruht nicht auf PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="06cc5-167">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="06cc5-168">Sie können den **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="06cc5-168">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

> [!NOTE]
> <span data-ttu-id="06cc5-169">Der **Computername** -Parameter wird in PowerShell 6,0 und höher in " **TargetName** " umbenannt.</span><span class="sxs-lookup"><span data-stu-id="06cc5-169">The **ComputerName** parameter is renamed to **TargetName** in PowerShell 6.0 and above.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, IPAddress, __SERVER, Server, Destination

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="06cc5-170">-Anzahl</span><span class="sxs-lookup"><span data-stu-id="06cc5-170">-Count</span></span>

<span data-ttu-id="06cc5-171">Gibt die Anzahl der zu sendenden Echoanforderungen an.</span><span class="sxs-lookup"><span data-stu-id="06cc5-171">Specifies the number of echo requests to send.</span></span> <span data-ttu-id="06cc5-172">Der Standardwert ist 4.</span><span class="sxs-lookup"><span data-stu-id="06cc5-172">The default value is 4.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06cc5-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="06cc5-173">-Credential</span></span>

<span data-ttu-id="06cc5-174">Gibt ein Benutzerkonto an, das über die Berechtigung zum Senden einer Ping-Anforderung vom Quellcomputer verfügt.</span><span class="sxs-lookup"><span data-stu-id="06cc5-174">Specifies a user account that has permission to send a ping request from the source computer.</span></span> <span data-ttu-id="06cc5-175">Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. einen aus dem `Get-Credential` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="06cc5-175">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="06cc5-176">Der **Credential** -Parameter ist nur gültig, wenn der **Source** -Parameter im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="06cc5-176">The **Credential** parameter is valid only when the **Source** parameter is used in the command.</span></span> <span data-ttu-id="06cc5-177">Die Anmelde Informationen wirken sich nicht auf den Zielcomputer aus.</span><span class="sxs-lookup"><span data-stu-id="06cc5-177">The credentials don't affect the destination computer.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Source
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06cc5-178">-Dcomauthentication</span><span class="sxs-lookup"><span data-stu-id="06cc5-178">-DcomAuthentication</span></span>

<span data-ttu-id="06cc5-179">Gibt die Authentifizierungs Ebene an, die dieses Cmdlet mit WMI verwendet.</span><span class="sxs-lookup"><span data-stu-id="06cc5-179">Specifies the authentication level that this cmdlet uses with WMI.</span></span>
<span data-ttu-id="06cc5-180">`Test-Connection` verwendet WMI.</span><span class="sxs-lookup"><span data-stu-id="06cc5-180">`Test-Connection` uses WMI.</span></span>
<span data-ttu-id="06cc5-181">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="06cc5-181">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="06cc5-182">**Default** .</span><span class="sxs-lookup"><span data-stu-id="06cc5-182">**Default** .</span></span> <span data-ttu-id="06cc5-183">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="06cc5-183">Windows Authentication</span></span>
- <span data-ttu-id="06cc5-184">**Keine** .</span><span class="sxs-lookup"><span data-stu-id="06cc5-184">**None** .</span></span> <span data-ttu-id="06cc5-185">Keine COM-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="06cc5-185">No COM authentication</span></span>
- <span data-ttu-id="06cc5-186">**Verbinden** Sie sich.</span><span class="sxs-lookup"><span data-stu-id="06cc5-186">**Connect** .</span></span> <span data-ttu-id="06cc5-187">COM-Authentifizierung auf Verbindungsebene</span><span class="sxs-lookup"><span data-stu-id="06cc5-187">Connect-level COM authentication</span></span>
- <span data-ttu-id="06cc5-188">**Aufgerufen** wird.</span><span class="sxs-lookup"><span data-stu-id="06cc5-188">**Call** .</span></span> <span data-ttu-id="06cc5-189">COM-Authentifizierung auf Aufrufebene</span><span class="sxs-lookup"><span data-stu-id="06cc5-189">Call-level COM authentication</span></span>
- <span data-ttu-id="06cc5-190">**Paket** .</span><span class="sxs-lookup"><span data-stu-id="06cc5-190">**Packet** .</span></span> <span data-ttu-id="06cc5-191">COM-Authentifizierung auf Paketebene</span><span class="sxs-lookup"><span data-stu-id="06cc5-191">Packet-level COM authentication</span></span>
- <span data-ttu-id="06cc5-192">**Packetintegrity** .</span><span class="sxs-lookup"><span data-stu-id="06cc5-192">**PacketIntegrity** .</span></span> <span data-ttu-id="06cc5-193">COM-Authentifizierung auf Paketintegritätsebene.</span><span class="sxs-lookup"><span data-stu-id="06cc5-193">Packet Integrity-level COM authentication</span></span>
- <span data-ttu-id="06cc5-194">**PacketPrivacy** .</span><span class="sxs-lookup"><span data-stu-id="06cc5-194">**PacketPrivacy** .</span></span> <span data-ttu-id="06cc5-195">COM-Authentifizierung auf Paketdaten Schutz Ebene</span><span class="sxs-lookup"><span data-stu-id="06cc5-195">Packet Privacy-level COM authentication</span></span>
- <span data-ttu-id="06cc5-196">**Unverändert** .</span><span class="sxs-lookup"><span data-stu-id="06cc5-196">**Unchanged** .</span></span> <span data-ttu-id="06cc5-197">Identisch mit dem vorherigen Befehl</span><span class="sxs-lookup"><span data-stu-id="06cc5-197">Same as the previous command</span></span>

<span data-ttu-id="06cc5-198">Der Standardwert ist **Packet** , das den Enumerationswert **4** aufweist.</span><span class="sxs-lookup"><span data-stu-id="06cc5-198">The default value is **Packet** that has an enumerated value of **4** .</span></span> <span data-ttu-id="06cc5-199">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="06cc5-199">For more information about the values of this parameter, see [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel) enumeration.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet (enumerated value of 4)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06cc5-200">-Verzögerung</span><span class="sxs-lookup"><span data-stu-id="06cc5-200">-Delay</span></span>

<span data-ttu-id="06cc5-201">Gibt das Intervall zwischen Pings in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="06cc5-201">Specifies the interval between pings, in seconds.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1 (second)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06cc5-202">-Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="06cc5-202">-Impersonation</span></span>

<span data-ttu-id="06cc5-203">Gibt die Identitätswechsel Ebene an, die verwendet werden soll, wenn dieses Cmdlet WMI aufruft.</span><span class="sxs-lookup"><span data-stu-id="06cc5-203">Specifies the impersonation level to use when this cmdlet calls WMI.</span></span> <span data-ttu-id="06cc5-204">`Test-Connection` verwendet WMI.</span><span class="sxs-lookup"><span data-stu-id="06cc5-204">`Test-Connection` uses WMI.</span></span>

<span data-ttu-id="06cc5-205">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="06cc5-205">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="06cc5-206">**Default** .</span><span class="sxs-lookup"><span data-stu-id="06cc5-206">**Default** .</span></span> <span data-ttu-id="06cc5-207">Standardidentitätswechsel.</span><span class="sxs-lookup"><span data-stu-id="06cc5-207">Default impersonation.</span></span>
- <span data-ttu-id="06cc5-208">**Anonym** .</span><span class="sxs-lookup"><span data-stu-id="06cc5-208">**Anonymous** .</span></span> <span data-ttu-id="06cc5-209">Blendet die Identität des Aufrufers aus</span><span class="sxs-lookup"><span data-stu-id="06cc5-209">Hides the identity of the caller.</span></span>
- <span data-ttu-id="06cc5-210">**Identifizieren** Sie.</span><span class="sxs-lookup"><span data-stu-id="06cc5-210">**Identify** .</span></span> <span data-ttu-id="06cc5-211">Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers abzufragen.</span><span class="sxs-lookup"><span data-stu-id="06cc5-211">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="06cc5-212">Identität **annehmen.**</span><span class="sxs-lookup"><span data-stu-id="06cc5-212">**Impersonate** .</span></span> <span data-ttu-id="06cc5-213">Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="06cc5-213">Allows objects to use the credentials of the caller.</span></span>

<span data-ttu-id="06cc5-214">Der Standard **Wert ist "** Identitätswechsel".</span><span class="sxs-lookup"><span data-stu-id="06cc5-214">The default value is **Impersonate** .</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06cc5-215">-Protocol</span><span class="sxs-lookup"><span data-stu-id="06cc5-215">-Protocol</span></span>

<span data-ttu-id="06cc5-216">Gibt ein Protokoll an.</span><span class="sxs-lookup"><span data-stu-id="06cc5-216">Specifies a protocol.</span></span> <span data-ttu-id="06cc5-217">Die zulässigen Werte für diesen Parameter sind "DCOM" und "wsman".</span><span class="sxs-lookup"><span data-stu-id="06cc5-217">The acceptable values for this parameter are DCOM and WSMan.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06cc5-218">-Quiet</span><span class="sxs-lookup"><span data-stu-id="06cc5-218">-Quiet</span></span>

<span data-ttu-id="06cc5-219">Der **quiet** -Parameter gibt einen **booleschen** Wert in einem **System. Boolean** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="06cc5-219">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object.</span></span> <span data-ttu-id="06cc5-220">Durch die Verwendung dieses Parameters werden alle Fehler unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="06cc5-220">Using this parameter suppresses all errors.</span></span>

<span data-ttu-id="06cc5-221">Jede getestete Verbindung gibt einen **booleschen** Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="06cc5-221">Each connection that's tested returns a **Boolean** value.</span></span> <span data-ttu-id="06cc5-222">Wenn der **Computername** -Parameter mehrere Computer angibt, wird ein Array von **booleschen** Werten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06cc5-222">If the **ComputerName** parameter specifies multiple computers, an array of **Boolean** values is returned.</span></span>

<span data-ttu-id="06cc5-223">Wenn **ein** Ping erfolgreich ist, `$True` wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06cc5-223">If **any** ping succeeds, `$True` is returned.</span></span>

<span data-ttu-id="06cc5-224">Wenn **alle** Pings fehlschlagen, `$False` wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06cc5-224">If **all** pings fail, `$False` is returned.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Quiet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06cc5-225">-Source</span><span class="sxs-lookup"><span data-stu-id="06cc5-225">-Source</span></span>

<span data-ttu-id="06cc5-226">Gibt die Namen der Computer an, von denen der Ping stammt.</span><span class="sxs-lookup"><span data-stu-id="06cc5-226">Specifies the names of the computers where the ping originates.</span></span> <span data-ttu-id="06cc5-227">Geben Sie eine durch Trennzeichen getrennte Liste von Computernamen ein.</span><span class="sxs-lookup"><span data-stu-id="06cc5-227">Enter a comma-separated list of computer names.</span></span> <span data-ttu-id="06cc5-228">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="06cc5-228">The default is the local computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: FCN, SRC

Required: True
Position: 1
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06cc5-229">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="06cc5-229">-ThrottleLimit</span></span>

<span data-ttu-id="06cc5-230">Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="06cc5-230">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="06cc5-231">Wenn Sie diesen Parameter weglassen oder den Wert %%amp;quot;0%%amp;quot; eingeben, wird der Standardwert %%amp;quot;32%%amp;quot; verwendet.</span><span class="sxs-lookup"><span data-stu-id="06cc5-231">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="06cc5-232">Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.</span><span class="sxs-lookup"><span data-stu-id="06cc5-232">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06cc5-233">-Timeto Live</span><span class="sxs-lookup"><span data-stu-id="06cc5-233">-TimeToLive</span></span>

<span data-ttu-id="06cc5-234">Gibt an, wie oft ein Paket maximal weitergeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="06cc5-234">Specifies the maximum times a packet can be forwarded.</span></span> <span data-ttu-id="06cc5-235">Bei jedem Hop in Gateways, Routern usw. wird der Wert von " **Timeto Live** " um 1 reduziert.</span><span class="sxs-lookup"><span data-stu-id="06cc5-235">For every hop in gateways, routers etc. the **TimeToLive** value is decreased by one.</span></span> <span data-ttu-id="06cc5-236">Bei Null wird das Paket verworfen, und es wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06cc5-236">At zero the packet is discarded and an error is returned.</span></span>
<span data-ttu-id="06cc5-237">In **Windows** ist der Standardwert **128** .</span><span class="sxs-lookup"><span data-stu-id="06cc5-237">In **Windows** , The default value is **128** .</span></span> <span data-ttu-id="06cc5-238">Der Alias des **timetelive** -Parameters ist **TTL** .</span><span class="sxs-lookup"><span data-stu-id="06cc5-238">The alias of the **TimeToLive** parameter is **TTL** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TTL

Required: False
Position: Named
Default value: 128 in Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06cc5-239">-Wsmanauthentication</span><span class="sxs-lookup"><span data-stu-id="06cc5-239">-WsmanAuthentication</span></span>

<span data-ttu-id="06cc5-240">Gibt den Mechanismus an, der verwendet wird, um die Benutzer Anmelde Informationen zu authentifizieren, wenn dieses Cmdlet das WSMAN-Protokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="06cc5-240">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span>
<span data-ttu-id="06cc5-241">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="06cc5-241">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="06cc5-242">Basic</span><span class="sxs-lookup"><span data-stu-id="06cc5-242">Basic</span></span>
- <span data-ttu-id="06cc5-243">CredSSP</span><span class="sxs-lookup"><span data-stu-id="06cc5-243">CredSSP</span></span>
- <span data-ttu-id="06cc5-244">Standard</span><span class="sxs-lookup"><span data-stu-id="06cc5-244">Default</span></span>
- <span data-ttu-id="06cc5-245">Digest</span><span class="sxs-lookup"><span data-stu-id="06cc5-245">Digest</span></span>
- <span data-ttu-id="06cc5-246">Kerberos</span><span class="sxs-lookup"><span data-stu-id="06cc5-246">Kerberos</span></span>
- <span data-ttu-id="06cc5-247">Negotiate</span><span class="sxs-lookup"><span data-stu-id="06cc5-247">Negotiate.</span></span>

<span data-ttu-id="06cc5-248">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="06cc5-248">The default value is Default.</span></span>

<span data-ttu-id="06cc5-249">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0).</span><span class="sxs-lookup"><span data-stu-id="06cc5-249">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0).</span></span>

<span data-ttu-id="06cc5-250">Vorsicht: die Authentifizierung des Anmelde Informations Diensts (Credential Security Service Provider, kredssp), in der die Benutzer Anmelde Informationen an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. auf eine Remote Netzwerkfreigabe</span><span class="sxs-lookup"><span data-stu-id="06cc5-250">Caution: Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
<span data-ttu-id="06cc5-251">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="06cc5-251">This mechanism increases the security risk of the remote operation.</span></span>
<span data-ttu-id="06cc5-252">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="06cc5-252">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="06cc5-253">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="06cc5-253">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06cc5-254">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="06cc5-254">CommonParameters</span></span>

<span data-ttu-id="06cc5-255">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="06cc5-255">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="06cc5-256">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="06cc5-256">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="06cc5-257">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="06cc5-257">INPUTS</span></span>

### <span data-ttu-id="06cc5-258">Keine</span><span class="sxs-lookup"><span data-stu-id="06cc5-258">None</span></span>

<span data-ttu-id="06cc5-259">Eingaben können nicht an dieses Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="06cc5-259">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="06cc5-260">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="06cc5-260">OUTPUTS</span></span>

### <span data-ttu-id="06cc5-261">System. Management. ManagementObject # root\cimv2\ Win32_PingStatus, System. Management. Automation. remotingjob, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="06cc5-261">System.Management.ManagementObject#root\cimv2\Win32_PingStatus, System.Management.Automation.RemotingJob, System.Boolean</span></span>

<span data-ttu-id="06cc5-262">Dieses Cmdlet gibt ein Auftrags Objekt zurück, wenn Sie den **AsJob** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="06cc5-262">This cmdlet returns a job object, if you specify the **AsJob** parameter.</span></span>

<span data-ttu-id="06cc5-263">Wenn Sie den **quiet** -Parameter angeben, wird ein **boolescher** Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06cc5-263">If you specify the **Quiet** parameter, it returns a **Boolean** value.</span></span> <span data-ttu-id="06cc5-264">Wenn mehrere Verbindungen getestet werden, wird ein Array von **booleschen** Werten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06cc5-264">If multiple connections are tested, an array of **Boolean** values is returned.</span></span> <span data-ttu-id="06cc5-265">Andernfalls wird `Test-Connection` für jeden Ping ein **Win32_PingStatus** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06cc5-265">Otherwise, `Test-Connection` returns a **Win32_PingStatus** object for each ping.</span></span>

## <span data-ttu-id="06cc5-266">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="06cc5-266">NOTES</span></span>

<span data-ttu-id="06cc5-267">Dieses Cmdlet verwendet die **Win32_PingStatus** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="06cc5-267">This cmdlet uses the **Win32_PingStatus** class.</span></span> <span data-ttu-id="06cc5-268">Ein `Get-WMIObject Win32_PingStatus` Befehl entspricht einem `Test-Connection` Befehl.</span><span class="sxs-lookup"><span data-stu-id="06cc5-268">A `Get-WMIObject Win32_PingStatus` command is equivalent to a `Test-Connection` command.</span></span>

<span data-ttu-id="06cc5-269">Der **Quell** Parametersatz wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="06cc5-269">The **Source** parameter set was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="06cc5-270">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="06cc5-270">RELATED LINKS</span></span>

[<span data-ttu-id="06cc5-271">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="06cc5-271">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="06cc5-272">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="06cc5-272">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="06cc5-273">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="06cc5-273">Stop-Computer</span></span>](Stop-Computer.md)
