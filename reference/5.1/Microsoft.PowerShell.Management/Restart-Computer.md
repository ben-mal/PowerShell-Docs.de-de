---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 6/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: 553b61c9669afab325e9feec101d701c2b9a7c83
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218263"
---
# <span data-ttu-id="724cb-103">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="724cb-103">Restart-Computer</span></span>

## <span data-ttu-id="724cb-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="724cb-104">SYNOPSIS</span></span>
<span data-ttu-id="724cb-105">Startet das Betriebssystem auf lokalen Computern und Remote Computern neu.</span><span class="sxs-lookup"><span data-stu-id="724cb-105">Restarts the operating system on local and remote computers.</span></span>

## <span data-ttu-id="724cb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="724cb-106">SYNTAX</span></span>

### <span data-ttu-id="724cb-107">Defaultset (Standard)</span><span class="sxs-lookup"><span data-stu-id="724cb-107">DefaultSet (Default)</span></span>

```
Restart-Computer [-DcomAuthentication <AuthenticationLevel>] [-Impersonation <ImpersonationLevel>]
 [-WsmanAuthentication <String>] [-Protocol <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="724cb-108">Asjobset</span><span class="sxs-lookup"><span data-stu-id="724cb-108">AsJobSet</span></span>

```
Restart-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>]
 [-Impersonation <ImpersonationLevel>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Force] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="724cb-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="724cb-109">DESCRIPTION</span></span>

<span data-ttu-id="724cb-110">`Restart-Computer`Mit dem-Cmdlet wird das Betriebssystem auf dem lokalen Computer und auf dem Remote Computer neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="724cb-110">The `Restart-Computer` cmdlet restarts the operating system on the local and remote computers.</span></span>

<span data-ttu-id="724cb-111">Mit den Parametern von können Sie `Restart-Computer` die Neustart Vorgänge als Hintergrund Auftrag ausführen, die Authentifizierungs Ebenen und Alternative Anmelde Informationen angeben, die Vorgänge, die gleichzeitig ausgeführt werden, einschränken und einen sofortigen Neustart erzwingen.</span><span class="sxs-lookup"><span data-stu-id="724cb-111">You can use the parameters of `Restart-Computer` to run the restart operations as a background job, to specify the authentication levels and alternate credentials, to limit the operations that run at the same time, and to force an immediate restart.</span></span>

<span data-ttu-id="724cb-112">Ab Windows PowerShell 3,0 können Sie warten, bis der Neustart beendet ist, bevor Sie den nächsten Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="724cb-112">Starting in Windows PowerShell 3.0, you can wait for the restart to complete before you run the next command.</span></span> <span data-ttu-id="724cb-113">Geben Sie ein Wartezeit-und Abfrageintervall an, und warten Sie, bis bestimmte Dienste auf dem neu gestarteten Computer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="724cb-113">Specify a waiting time-out and query interval, and wait for particular services to be available on the restarted computer.</span></span> <span data-ttu-id="724cb-114">Diese Funktion erleichtert die Verwendung von `Restart-Computer` in Skripts und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="724cb-114">This feature makes it practical to use `Restart-Computer` in scripts and functions.</span></span>

<span data-ttu-id="724cb-115">Sie können das WSMAN-Protokoll (WS-Management) verwenden, um den Computer neu zu starten, falls DCOM-Aufrufe (verteiltes Component Object Model) blockiert werden (z. b. durch eine Unternehmens Firewall).</span><span class="sxs-lookup"><span data-stu-id="724cb-115">You can use the WS-Management (WSMan) protocol to restart the computer, in case Distributed Component Object Model (DCOM) calls are blocked, such as by an enterprise firewall.</span></span> <span data-ttu-id="724cb-116">Weitere Informationen finden Sie unter [WS-Management-Protokoll](/windows/desktop/WinRM/ws-management-protocol).</span><span class="sxs-lookup"><span data-stu-id="724cb-116">For more information, see [WS-Management Protocol](/windows/desktop/WinRM/ws-management-protocol).</span></span>

<span data-ttu-id="724cb-117">Bei diesem Cmdlet ist Windows PowerShell-Remoting nur erforderlich, wenn Sie den **AsJob** -Parameter in einem Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="724cb-117">This cmdlet requires Windows PowerShell remoting only when you use the **AsJob** parameter in a command.</span></span>

## <span data-ttu-id="724cb-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="724cb-118">EXAMPLES</span></span>

### <span data-ttu-id="724cb-119">Beispiel 1: Neustarten des lokalen Computers</span><span class="sxs-lookup"><span data-stu-id="724cb-119">Example 1: Restart the local computer</span></span>

<span data-ttu-id="724cb-120">`Restart-Computer` startet den lokalen Computer neu.</span><span class="sxs-lookup"><span data-stu-id="724cb-120">`Restart-Computer` restarts the local computer.</span></span>

```powershell
Restart-Computer
```

### <span data-ttu-id="724cb-121">Beispiel 2: Neustarten mehrerer Computer</span><span class="sxs-lookup"><span data-stu-id="724cb-121">Example 2: Restart multiple computers</span></span>

<span data-ttu-id="724cb-122">`Restart-Computer` Remote Computer und lokale Computer können neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="724cb-122">`Restart-Computer` can restart remote and local computers.</span></span> <span data-ttu-id="724cb-123">Der Computer **Name** -Parameter akzeptiert ein Array von Computernamen.</span><span class="sxs-lookup"><span data-stu-id="724cb-123">The **ComputerName** parameter accepts an array of computer names.</span></span>

```powershell
Restart-Computer -ComputerName Server01, Server02, localhost
```

### <span data-ttu-id="724cb-124">Beispiel 3: Neustarten von Computern als Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="724cb-124">Example 3: Restart computers as a background job</span></span>

<span data-ttu-id="724cb-125">Diese Befehle führen einen `Restart-Computer` Befehl als Hintergrund Auftrag auf zwei Remote Computern aus und erhalten dann die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="724cb-125">These commands run a `Restart-Computer` command as a background job on two remote computers, and then get the results.</span></span>

<span data-ttu-id="724cb-126">Da **AsJob** den Auftrag auf dem lokalen Computer erstellt und die Ergebnisse automatisch an den lokalen Computer zurückgibt, können Sie ihn `Receive-Job` als lokalen Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="724cb-126">Because **AsJob** creates the job on the local computer and automatically returns the results to the local computer, you can run `Receive-Job` as a local command.</span></span>

```powershell
$Job = Restart-Computer -ComputerName "Server01", "Server02" -AsJob
$Job | Receive-Job
```

<span data-ttu-id="724cb-127">`Restart-Computer` verwendet den **Computername** -Parameter zum Angeben von **Server01** und **Server02**.</span><span class="sxs-lookup"><span data-stu-id="724cb-127">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01** and **Server02**.</span></span> <span data-ttu-id="724cb-128">Der **AsJob** -Parameter führt den Befehl als Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="724cb-128">The **AsJob** parameter runs the command as a background job.</span></span> <span data-ttu-id="724cb-129">Das Auftrags Objekt wird in der `$Job` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="724cb-129">The job object is stored in the `$Job` variable.</span></span> <span data-ttu-id="724cb-130">`$Job` wird über die Pipeline an das `Receive-Job` Cmdlet gesendet, das die Ergebnisse abruft.</span><span class="sxs-lookup"><span data-stu-id="724cb-130">`$Job` is sent down the pipeline to the `Receive-Job` cmdlet that gets the results.</span></span>

### <span data-ttu-id="724cb-131">Beispiel 4: Neustart eines Remote Computers</span><span class="sxs-lookup"><span data-stu-id="724cb-131">Example 4: Restart a remote computer</span></span>

<span data-ttu-id="724cb-132">`Restart-Computer` startet einen Remote Computer mit angepassten Identitätswechsel-und Authentifizierungs Einstellungen neu.</span><span class="sxs-lookup"><span data-stu-id="724cb-132">`Restart-Computer` restarts a remote computer with customized impersonation and authentication settings.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

<span data-ttu-id="724cb-133">`Restart-Computer` verwendet den **Computername** -Parameter, um **Server01** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="724cb-133">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01**.</span></span> <span data-ttu-id="724cb-134">Der Identitäts **Wechsel Parameter gibt** anonym an, um die Identität des Anforderers auszublenden.</span><span class="sxs-lookup"><span data-stu-id="724cb-134">The **Impersonation** parameter specifies Anonymous to hide the requester's identity.</span></span> <span data-ttu-id="724cb-135">Der **dcomauthentication** -Parameter gibt packetintegrity als Authentifizierungs Ebene der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="724cb-135">The **DcomAuthentication** parameter specifies PacketIntegrity as the connection's authentication level.</span></span>

### <span data-ttu-id="724cb-136">Beispiel 5: Erzwingen des Neustarts von Computern, die in einer Textdatei aufgeführt sind</span><span class="sxs-lookup"><span data-stu-id="724cb-136">Example 5: Force restart of computers listed in a text file</span></span>

<span data-ttu-id="724cb-137">Dieses Beispiel erzwingt einen sofortigen Neustart der Computer, die in der-Datei aufgeführt sind `Domain01.txt` .</span><span class="sxs-lookup"><span data-stu-id="724cb-137">This example forces an immediate restart of the computers listed in the `Domain01.txt` file.</span></span> <span data-ttu-id="724cb-138">Die Computernamen aus der Textdatei werden in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="724cb-138">The computer names from the text file are stored in a variable.</span></span> <span data-ttu-id="724cb-139">Der **Force** -Parameter erzwingt einen sofortigen Neustart, und der **throttlelimit** -Parameter schränkt die Anzahl gleichzeitiger Verbindungen ein.</span><span class="sxs-lookup"><span data-stu-id="724cb-139">The **Force** parameter forces an immediate restart and the **ThrottleLimit** parameter limits the number of concurrent connections.</span></span>

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force -ThrottleLimit 10
```

<span data-ttu-id="724cb-140">`Get-Content` verwendet den **path** -Parameter, um eine Liste der Computernamen aus einer Textdatei, **Domain01.txt** , zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="724cb-140">`Get-Content` uses the **Path** parameter to get a list of computer names from a text file, **Domain01.txt**.</span></span> <span data-ttu-id="724cb-141">Die Computernamen werden in der Variablen gespeichert `$Names` .</span><span class="sxs-lookup"><span data-stu-id="724cb-141">The computer names are stored in the variable `$Names`.</span></span> <span data-ttu-id="724cb-142">`Get-Credential` fordert Sie zur Eingabe eines Benutzernamens und Kennworts auf und speichert die Werte in der Variablen `$Creds` .</span><span class="sxs-lookup"><span data-stu-id="724cb-142">`Get-Credential` prompts you for a username and password and stores the values in the variable `$Creds`.</span></span> <span data-ttu-id="724cb-143">`Restart-Computer` verwendet die Parameter " **Computername** " und " **Credential** " mit ihren Variablen.</span><span class="sxs-lookup"><span data-stu-id="724cb-143">`Restart-Computer` uses the **ComputerName** and **Credential** parameters with their variables.</span></span> <span data-ttu-id="724cb-144">Der **Force** -Parameter bewirkt einen sofortigen Neustart der einzelnen Computer.</span><span class="sxs-lookup"><span data-stu-id="724cb-144">The **Force** parameter causes an immediate restart of each computer.</span></span> <span data-ttu-id="724cb-145">Der **throttlelimit** -Parameter schränkt den Befehl auf 10 gleichzeitige Verbindungen ein.</span><span class="sxs-lookup"><span data-stu-id="724cb-145">The **ThrottleLimit** parameter limits the command to 10 concurrent connections.</span></span>

### <span data-ttu-id="724cb-146">Beispiel 6: Neustarten eines Remote Computers und warten auf PowerShell</span><span class="sxs-lookup"><span data-stu-id="724cb-146">Example 6: Restart a remote computer and wait for PowerShell</span></span>

<span data-ttu-id="724cb-147">`Restart-Computer` startet den Remote Computer neu und wartet dann bis zu 5 Minuten (300 Sekunden) darauf, dass PowerShell auf dem neu gestarteten Computer verfügbar wird, bevor es fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="724cb-147">`Restart-Computer` restarts the remote computer and then waits up to 5 minutes (300 seconds) for PowerShell to become available on the restarted computer before it continues.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

<span data-ttu-id="724cb-148">`Restart-Computer` verwendet den **Computername** -Parameter, um **Server01** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="724cb-148">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01**.</span></span> <span data-ttu-id="724cb-149">Der **Wait** -Parameter wartet, bis der Neustart abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="724cb-149">The **Wait** parameter waits for the restart to finish.</span></span> <span data-ttu-id="724cb-150">Der **für** gibt an, dass PowerShell Befehle auf dem Remote Computer ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="724cb-150">The **For** specifies that PowerShell can run commands on the remote computer.</span></span> <span data-ttu-id="724cb-151">Der **Timeout** -Parameter gibt eine Wartezeit von fünf Minuten an.</span><span class="sxs-lookup"><span data-stu-id="724cb-151">The **Timeout** parameter specifies a five-minute wait.</span></span> <span data-ttu-id="724cb-152">Der **Verzögerungs** Parameter fragt den Remote Computer alle zwei Sekunden ab, um zu bestimmen, ob er neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="724cb-152">The **Delay** parameter queries the remote computer every two seconds to determine whether it's restarted.</span></span>

### <span data-ttu-id="724cb-153">Beispiel 7: Neustarten eines Computers mithilfe des WSMAN-Protokolls</span><span class="sxs-lookup"><span data-stu-id="724cb-153">Example 7: Restart a computer by using the WSMan Protocol</span></span>

<span data-ttu-id="724cb-154">`Restart-Computer` der Remote Computer wird mit dem WSMAN-Protokoll anstelle der standardmäßigen DCOM neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="724cb-154">`Restart-Computer` restarts the remote computer by using the WSMan protocol instead of the default, DCOM.</span></span> <span data-ttu-id="724cb-155">Die Kerberos-Authentifizierung bestimmt, ob der aktuelle Benutzer über die Berechtigung zum Neustarten des Remote Computers verfügt.</span><span class="sxs-lookup"><span data-stu-id="724cb-155">Kerberos authentication determines whether the current user has permission to restart the remote computer.</span></span>

<span data-ttu-id="724cb-156">Diese Einstellungen sind für Unternehmen konzipiert, in denen DCOM-basierte Neustarts fehlschlagen, da DCOM blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="724cb-156">These settings are designed for enterprises in which DCOM-based restarts fail because DCOM is blocked.</span></span> <span data-ttu-id="724cb-157">Beispielsweise durch eine Firewall.</span><span class="sxs-lookup"><span data-stu-id="724cb-157">For example, by a firewall.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Protocol WSMan -WsmanAuthentication Kerberos
```

<span data-ttu-id="724cb-158">`Restart-Computer` verwendet den **Computername** -Parameter, um den Remote Computer anzugeben, **Server01**.</span><span class="sxs-lookup"><span data-stu-id="724cb-158">`Restart-Computer` uses the **ComputerName** parameter to specify the remote computer, **Server01**.</span></span>
<span data-ttu-id="724cb-159">Der **Protokoll** Parameter gibt an, dass das WSMAN-Protokoll verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="724cb-159">The **Protocol** parameter specifies to use the WSMan protocol.</span></span> <span data-ttu-id="724cb-160">Der **wsmanauthentication** -Parameter gibt die Authentifizierungsmethode als **Kerberos** an.</span><span class="sxs-lookup"><span data-stu-id="724cb-160">The **WsmanAuthentication** parameter specifies the authentication method as **Kerberos**.</span></span>

## <span data-ttu-id="724cb-161">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="724cb-161">PARAMETERS</span></span>

### <span data-ttu-id="724cb-162">-AsJob</span><span class="sxs-lookup"><span data-stu-id="724cb-162">-AsJob</span></span>

<span data-ttu-id="724cb-163">Gibt an, dass `Restart-Computer` als Hintergrund Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="724cb-163">Indicates that `Restart-Computer` runs as a background job.</span></span>

<span data-ttu-id="724cb-164">Um diesen Parameter verwenden zu können, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="724cb-164">To use this parameter, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="724cb-165">Unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell öffnen, indem Sie die Option **als Administrator ausführen** verwenden.</span><span class="sxs-lookup"><span data-stu-id="724cb-165">On Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as Administrator** option.</span></span> <span data-ttu-id="724cb-166">Weitere Informationen finden Sie unter [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="724cb-166">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="724cb-167">Wenn Sie den **AsJob** -Parameter angeben, gibt der Befehl sofort ein Objekt zurück, das den Hintergrund Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="724cb-167">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="724cb-168">Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="724cb-168">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="724cb-169">Der Auftrag wird auf dem lokalen Computer erstellt, und die Ergebnisse von Remotecomputern werden automatisch an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="724cb-169">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="724cb-170">Verwenden Sie die **Job** -Cmdlets, um den Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="724cb-170">To manage the job, use the **Job** cmdlets.</span></span> <span data-ttu-id="724cb-171">Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet `Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="724cb-171">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="724cb-172">Weitere Informationen zu Windows PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) und [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="724cb-172">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="724cb-173">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="724cb-173">-ComputerName</span></span>

<span data-ttu-id="724cb-174">Gibt einen Computernamen oder ein durch Trennzeichen getrenntes Array von Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="724cb-174">Specifies one computer name or a comma-separated array of computer names.</span></span> <span data-ttu-id="724cb-175">`Restart-Computer` nimmt **Computername** -Objekte aus der Pipeline oder den Variablen an.</span><span class="sxs-lookup"><span data-stu-id="724cb-175">`Restart-Computer` accepts **ComputerName** objects from the pipeline or variables.</span></span>

<span data-ttu-id="724cb-176">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein.</span><span class="sxs-lookup"><span data-stu-id="724cb-176">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span> <span data-ttu-id="724cb-177">Geben Sie den Computernamen, einen Punkt oder einen localhost ein, um den lokalen Computer anzugeben `.` .</span><span class="sxs-lookup"><span data-stu-id="724cb-177">To specify the local computer, type the computer name, a dot `.`, or localhost.</span></span>

<span data-ttu-id="724cb-178">Dieser Parameter beruht nicht auf PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="724cb-178">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="724cb-179">Sie können den **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="724cb-179">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

<span data-ttu-id="724cb-180">Wenn der **Computername** -Parameter nicht angegeben ist, wird `Restart-Computer` der lokale Computer neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="724cb-180">If the **ComputerName** parameter isn't specified, `Restart-Computer` restarts the local computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="724cb-181">-Credential</span><span class="sxs-lookup"><span data-stu-id="724cb-181">-Credential</span></span>

<span data-ttu-id="724cb-182">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="724cb-182">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="724cb-183">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="724cb-183">The default is the current user.</span></span>

<span data-ttu-id="724cb-184">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="724cb-184">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="724cb-185">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="724cb-185">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="724cb-186">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="724cb-186">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="724cb-187">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="724cb-187">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="724cb-188">-Dcomauthentication</span><span class="sxs-lookup"><span data-stu-id="724cb-188">-DcomAuthentication</span></span>

<span data-ttu-id="724cb-189">Gibt die Authentifizierungs Ebene an, die für die WMI-Verbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="724cb-189">Specifies the authentication level that is used for the WMI connection.</span></span> <span data-ttu-id="724cb-190">`Restart-Computer` verwendet WMI.</span><span class="sxs-lookup"><span data-stu-id="724cb-190">`Restart-Computer` uses WMI.</span></span>

<span data-ttu-id="724cb-191">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="724cb-191">Valid values are:</span></span>

- <span data-ttu-id="724cb-192">**Rückruf** : com-Authentifizierung auf aufrufsebene</span><span class="sxs-lookup"><span data-stu-id="724cb-192">**Call** :            Call-level COM authentication</span></span>
- <span data-ttu-id="724cb-193">**Connect** : com-Authentifizierung auf Verbindungs Ebene</span><span class="sxs-lookup"><span data-stu-id="724cb-193">**Connect** :         Connect-level COM authentication</span></span>
- <span data-ttu-id="724cb-194">**Standard** : Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="724cb-194">**Default** :         Windows Authentication</span></span>
- <span data-ttu-id="724cb-195">**None** : keine com-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="724cb-195">**None** :            No COM authentication</span></span>
- <span data-ttu-id="724cb-196">**Paket** : com-Authentifizierung auf Paketebene.</span><span class="sxs-lookup"><span data-stu-id="724cb-196">**Packet** :          Packet-level COM authentication.</span></span>
- <span data-ttu-id="724cb-197">**Packetintegrity** : com-Authentifizierung auf Paket Integritäts Ebene</span><span class="sxs-lookup"><span data-stu-id="724cb-197">**PacketIntegrity** : Packet Integrity-level COM authentication</span></span>
- <span data-ttu-id="724cb-198">**PacketPrivacy** : com-Authentifizierung auf Paketdaten Schutz Ebene.</span><span class="sxs-lookup"><span data-stu-id="724cb-198">**PacketPrivacy** :   Packet Privacy-level COM authentication.</span></span>
- <span data-ttu-id="724cb-199">**Unverändert** : die Authentifizierungs Ebene entspricht dem vorherigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="724cb-199">**Unchanged** :       The authentication level is the same as the previous command.</span></span>

<span data-ttu-id="724cb-200">Weitere Informationen finden Sie unter [AuthenticationLevel-Enumeration](/dotnet/api/system.management.authenticationlevel).</span><span class="sxs-lookup"><span data-stu-id="724cb-200">For more information, see [AuthenticationLevel Enumeration](/dotnet/api/system.management.authenticationlevel).</span></span>

<span data-ttu-id="724cb-201">Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="724cb-201">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="724cb-202">-Verzögerung</span><span class="sxs-lookup"><span data-stu-id="724cb-202">-Delay</span></span>

<span data-ttu-id="724cb-203">Gibt die Häufigkeit von Abfragen in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="724cb-203">Specifies the frequency of queries, in seconds.</span></span> <span data-ttu-id="724cb-204">PowerShell fragt den durch den **for** -Parameter angegebenen Dienst ab, um zu bestimmen, ob der Dienst nach dem Neustart des Computers verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="724cb-204">PowerShell queries the service specified by the **For** parameter to determine whether the service is available after the computer is restarted.</span></span>

<span data-ttu-id="724cb-205">Dieser Parameter ist nur in Verbindung mit den **Wait** -und **for** -Parametern gültig.</span><span class="sxs-lookup"><span data-stu-id="724cb-205">This parameter is valid only together with the **Wait** and **For** parameters.</span></span>

<span data-ttu-id="724cb-206">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="724cb-206">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="724cb-207">Wenn der **Delay** -Parameter nicht angegeben wird, `Restart-Computer` verwendet eine Verzögerung von fünf Sekunden.</span><span class="sxs-lookup"><span data-stu-id="724cb-207">If the **Delay** parameter isn't specified, `Restart-Computer` uses a five second delay.</span></span>

```yaml
Type: System.Int16
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="724cb-208">-Für</span><span class="sxs-lookup"><span data-stu-id="724cb-208">-For</span></span>

<span data-ttu-id="724cb-209">Gibt das Verhalten von PowerShell an, da es darauf wartet, dass der angegebene Dienst oder das Feature nach dem Neustart des Computers verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="724cb-209">Specifies the behavior of PowerShell as it waits for the specified service or feature to become available after the computer restarts.</span></span> <span data-ttu-id="724cb-210">Dieser Parameter ist nur mit dem **Wait** -Parameter gültig.</span><span class="sxs-lookup"><span data-stu-id="724cb-210">This parameter is only valid with the **Wait** parameter.</span></span>

<span data-ttu-id="724cb-211">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="724cb-211">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="724cb-212">**Standard** : wartet darauf, dass PowerShell neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="724cb-212">**Default** : Waits for PowerShell to restart.</span></span>
- <span data-ttu-id="724cb-213">**PowerShell** : kann Befehle in einer PowerShell-Remote Sitzung auf dem Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="724cb-213">**PowerShell** : Can run commands in a PowerShell remote session on the computer.</span></span>
- <span data-ttu-id="724cb-214">**WMI** : empfängt eine Antwort auf eine Win32_ComputerSystem Abfrage für den Computer.</span><span class="sxs-lookup"><span data-stu-id="724cb-214">**WMI** : Receives a reply to a Win32_ComputerSystem query for the computer.</span></span>
- <span data-ttu-id="724cb-215">**WinRM** : kann mithilfe von WS-Management eine Remote Sitzung mit dem Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="724cb-215">**WinRM** : Can establish a remote session to the computer by using WS-Management.</span></span>

<span data-ttu-id="724cb-216">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="724cb-216">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: DefaultSet
Aliases:
Accepted values: Wmi, WinRM, PowerShell

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="724cb-217">-Force</span><span class="sxs-lookup"><span data-stu-id="724cb-217">-Force</span></span>

<span data-ttu-id="724cb-218">Erzwingt einen sofortigen Neustart des Computers.</span><span class="sxs-lookup"><span data-stu-id="724cb-218">Forces an immediate restart of the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="724cb-219">-Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="724cb-219">-Impersonation</span></span>

<span data-ttu-id="724cb-220">Gibt die Identitätswechsel Ebene an, die dieses Cmdlet zum Abrufen von WMI verwendet.</span><span class="sxs-lookup"><span data-stu-id="724cb-220">Specifies the impersonation level that this cmdlet uses to call WMI.</span></span> <span data-ttu-id="724cb-221">`Restart-Computer` verwendet WMI.</span><span class="sxs-lookup"><span data-stu-id="724cb-221">`Restart-Computer` uses WMI.</span></span>
<span data-ttu-id="724cb-222">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="724cb-222">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="724cb-223">**Standard** : Standard Identitätswechsel.</span><span class="sxs-lookup"><span data-stu-id="724cb-223">**Default** : Default impersonation.</span></span> <span data-ttu-id="724cb-224">Trotz des Namens ist dies nicht der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="724cb-224">Despite the name, this isn't the default value.</span></span>
- <span data-ttu-id="724cb-225">**Anonymous** : Blendet die Identität des Aufrufers aus.</span><span class="sxs-lookup"><span data-stu-id="724cb-225">**Anonymous** : Hides the identity of the caller.</span></span>
- <span data-ttu-id="724cb-226">**Identifizieren** : ermöglicht es Objekten, die Anmelde Informationen des Aufrufers abzufragen.</span><span class="sxs-lookup"><span data-stu-id="724cb-226">**Identify** : Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="724cb-227">Identität **annehmen: ermöglicht** es Objekten, die Anmelde Informationen des Aufrufers zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="724cb-227">**Impersonate** : Allows objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="724cb-228">-Protocol</span><span class="sxs-lookup"><span data-stu-id="724cb-228">-Protocol</span></span>

<span data-ttu-id="724cb-229">Gibt an, welches Protokoll zum Neustarten der Computer verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="724cb-229">Specifies which protocol to use to restart the computers.</span></span> <span data-ttu-id="724cb-230">Gültige Werte sind **WSMAN** und **DCOM**.</span><span class="sxs-lookup"><span data-stu-id="724cb-230">The valid values are **WSMan** and **DCOM**.</span></span>

<span data-ttu-id="724cb-231">Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="724cb-231">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="724cb-232">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="724cb-232">-ThrottleLimit</span></span>

<span data-ttu-id="724cb-233">Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="724cb-233">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="724cb-234">Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.</span><span class="sxs-lookup"><span data-stu-id="724cb-234">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

<span data-ttu-id="724cb-235">Wenn der **throttlelimit** -Parameter nicht angegeben oder der Wert 0 verwendet wird, `Restart-Computer` verwendet maximal 32 gleichzeitige Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="724cb-235">If the **ThrottleLimit** parameter isn't specified or a value of 0 is used, `Restart-Computer` uses a maximum of 32 concurrent connections.</span></span>

```yaml
Type: System.Int32
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="724cb-236">-Timeout</span><span class="sxs-lookup"><span data-stu-id="724cb-236">-Timeout</span></span>

<span data-ttu-id="724cb-237">Gibt die Dauer des Wartevorgangs in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="724cb-237">Specifies the duration of the wait, in seconds.</span></span> <span data-ttu-id="724cb-238">Wenn das Timeout abläuft, `Restart-Computer` kehrt zur Eingabeaufforderung zurück, auch wenn die Computer nicht neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="724cb-238">When the timeout elapses, `Restart-Computer` returns to the command prompt, even if the computers aren't restarted.</span></span>

<span data-ttu-id="724cb-239">Der **Timeout** -Parameter ist nur mit dem **Wait** -Parameter gültig.</span><span class="sxs-lookup"><span data-stu-id="724cb-239">The **Timeout** parameter is only valid with the **Wait** parameter.</span></span> <span data-ttu-id="724cb-240">**Timeout** überschreibt den unbegrenzten warte Zeitraum des **Wait** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="724cb-240">**Timeout** overrides the **Wait** parameter's indefinite waiting period.</span></span>

<span data-ttu-id="724cb-241">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="724cb-241">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultSet
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="724cb-242">-Wait</span><span class="sxs-lookup"><span data-stu-id="724cb-242">-Wait</span></span>

<span data-ttu-id="724cb-243">`Restart-Computer` unterdrückt die PowerShell-Eingabeaufforderung und blockiert die Pipeline, bis die Computer neu gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="724cb-243">`Restart-Computer` suppresses the PowerShell prompt and blocks the pipeline until the computers have restarted.</span></span> <span data-ttu-id="724cb-244">Sie können diesen Parameter in einem Skript verwenden, um Computer neu zu starten und die Verarbeitung anschließend fortzusetzen, wenn der Neustart abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="724cb-244">You can use this parameter in a script to restart computers and then continue to process when the restart is finished.</span></span>

<span data-ttu-id="724cb-245">Der **Wait** -Parameter wartet unbegrenzt, bis der Computer neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="724cb-245">The **Wait** parameter waits indefinitely for the computers to restart.</span></span> <span data-ttu-id="724cb-246">Mit **Timeout** können Sie die zeitliche Steuerung und die Parameter **für** und **Verzögerung** anpassen, um zu warten, bis bestimmte Dienste auf den neu gestarteten Computern verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="724cb-246">You can use **Timeout** to adjust the timing and the **For** and **Delay** parameters to wait for particular services to become available on the restarted computers.</span></span>

<span data-ttu-id="724cb-247">Der **Wait** -Parameter ist nicht gültig, wenn Sie den lokalen Computer neu starten.</span><span class="sxs-lookup"><span data-stu-id="724cb-247">The **Wait** parameter isn't valid when you're restarting the local computer.</span></span> <span data-ttu-id="724cb-248">Wenn der Wert des **Computername** -Parameters die Namen der Remote Computer und des lokalen Computers enthält, `Restart-Computer` generiert einen Fehler ohne Abbruch auf dem lokalen Computer, wartet **jedoch auf** den Neustart der Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="724cb-248">If the value of the **ComputerName** parameter contains the names of remote computers and the local computer, `Restart-Computer` generates a non-terminating error for **Wait** on the local computer, but waits for the remote computers to restart.</span></span>

<span data-ttu-id="724cb-249">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="724cb-249">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="724cb-250">-Wsmanauthentication</span><span class="sxs-lookup"><span data-stu-id="724cb-250">-WsmanAuthentication</span></span>

<span data-ttu-id="724cb-251">Gibt den Mechanismus an, der verwendet wird, um die Benutzer Anmelde Informationen zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="724cb-251">Specifies the mechanism that is used to authenticate the user credentials.</span></span> <span data-ttu-id="724cb-252">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="724cb-252">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="724cb-253">Die zulässigen Werte für diesen Parameter sind: **Basic** , **kredssp** , **default** , **Digest** , **Kerberos** und **Aushandlungs**.</span><span class="sxs-lookup"><span data-stu-id="724cb-253">The acceptable values for this parameter are: **Basic** , **CredSSP** , **Default** , **Digest** , **Kerberos** , and **Negotiate**.</span></span>

<span data-ttu-id="724cb-254">Weitere Informationen finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="724cb-254">For more information, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="724cb-255">Die Authentifizierung des Anmelde Informations Diensts (Credential Security Service Provider, kredssp), in der die Benutzer Anmelde Informationen an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehreren Ressourcen erfordern</span><span class="sxs-lookup"><span data-stu-id="724cb-255">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="724cb-256">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="724cb-256">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="724cb-257">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="724cb-257">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: Basic, CredSSP, Default, Digest, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="724cb-258">-Confirm</span><span class="sxs-lookup"><span data-stu-id="724cb-258">-Confirm</span></span>

<span data-ttu-id="724cb-259">Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Restart-Computer` .</span><span class="sxs-lookup"><span data-stu-id="724cb-259">Prompts you for confirmation before running `Restart-Computer`.</span></span>

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

### <span data-ttu-id="724cb-260">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="724cb-260">-WhatIf</span></span>

<span data-ttu-id="724cb-261">Zeigt, was geschieht, wenn die ausgeführt wird `Restart-Computer` .</span><span class="sxs-lookup"><span data-stu-id="724cb-261">Shows what would happen if the `Restart-Computer` runs.</span></span> <span data-ttu-id="724cb-262">Das- `Restart-Computer` Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="724cb-262">The `Restart-Computer` cmdlet isn't run.</span></span>

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

### <span data-ttu-id="724cb-263">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="724cb-263">CommonParameters</span></span>

<span data-ttu-id="724cb-264">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="724cb-264">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="724cb-265">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="724cb-265">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="724cb-266">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="724cb-266">INPUTS</span></span>

### <span data-ttu-id="724cb-267">System.String</span><span class="sxs-lookup"><span data-stu-id="724cb-267">System.String</span></span>

<span data-ttu-id="724cb-268">`Restart-Computer` nimmt Computernamen aus der Pipeline oder den Variablen an.</span><span class="sxs-lookup"><span data-stu-id="724cb-268">`Restart-Computer` accepts computer names from the pipeline or variables.</span></span>

<span data-ttu-id="724cb-269">In Windows PowerShell 2.0 nimmt der **ComputerName** -Parameter Eingaben über die Pipeline nur nach Eigenschaftenname an.</span><span class="sxs-lookup"><span data-stu-id="724cb-269">In Windows PowerShell 2.0, the **ComputerName** parameter takes input from the pipeline only by property name.</span></span> <span data-ttu-id="724cb-270">In Windows PowerShell 3,0 und höher nimmt der **Computername** -Parameter Eingaben aus der Pipeline nach Wert.</span><span class="sxs-lookup"><span data-stu-id="724cb-270">In Windows PowerShell 3.0, and later, the **ComputerName** parameter takes input from the pipeline by value.</span></span>

## <span data-ttu-id="724cb-271">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="724cb-271">OUTPUTS</span></span>

### <span data-ttu-id="724cb-272">Keine, System. Management. Automation. remotingjob</span><span class="sxs-lookup"><span data-stu-id="724cb-272">None, System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="724cb-273">Wenn Sie den **AsJob** -Parameter angeben, wird `Restart-Computer` ein Auftrags Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="724cb-273">If you specify the **AsJob** parameter, `Restart-Computer` returns a job object.</span></span> <span data-ttu-id="724cb-274">Andernfalls wird keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="724cb-274">Otherwise, no output is generated.</span></span>

## <span data-ttu-id="724cb-275">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="724cb-275">NOTES</span></span>

- <span data-ttu-id="724cb-276">`Restart-Computer` nur auf Computern, auf denen Windows ausgeführt wird, ist es erforderlich, dass WinRM und WMI ein System Herunterfahren, einschließlich des lokalen Systems.</span><span class="sxs-lookup"><span data-stu-id="724cb-276">`Restart-Computer` only work on computers running Windows and requires WinRM and WMI to shutdown a system, including the local system.</span></span>
- <span data-ttu-id="724cb-277">`Restart-Computer` verwendet die [Win32Shutdown-Methode](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) der WMI- [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) Klasse (Windows-Verwaltungsinstrumentation).</span><span class="sxs-lookup"><span data-stu-id="724cb-277">`Restart-Computer` uses the [Win32Shutdown method](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) of the Windows Management Instrumentation (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) class.</span></span>  <span data-ttu-id="724cb-278">Diese Methode erfordert, dass die **SeShutdownPrivilege** -Berechtigung für das Benutzerkonto aktiviert ist, mit dem der Computer neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="724cb-278">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

<span data-ttu-id="724cb-279">In Windows PowerShell 2,0 funktioniert der **AsJob** -Parameter nicht zuverlässig, wenn Sie Remote Computer neu starten oder beenden.</span><span class="sxs-lookup"><span data-stu-id="724cb-279">In Windows PowerShell 2.0, the **AsJob** parameter doesn't work reliably when you are restarting or stopping remote computers.</span></span> <span data-ttu-id="724cb-280">In Windows PowerShell 3.0 wurde die Implementierung geändert, um dieses Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="724cb-280">In Windows PowerShell 3.0, the implementation is changed to resolve this problem.</span></span>

## <span data-ttu-id="724cb-281">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="724cb-281">RELATED LINKS</span></span>

[<span data-ttu-id="724cb-282">Informationen zu Windows-Remoteverwaltung</span><span class="sxs-lookup"><span data-stu-id="724cb-282">About Windows Remote Management</span></span>](/windows/desktop/WinRM/about-windows-remote-management)

[<span data-ttu-id="724cb-283">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="724cb-283">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="724cb-284">WS-Verwaltungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="724cb-284">WS-Management Protocol</span></span>](/windows/desktop/WinRM/ws-management-protocol)
