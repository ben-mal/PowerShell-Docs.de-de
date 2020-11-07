---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 6/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: 623b7bb0084c7fe7822509081d141ddcccf0057a
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347328"
---
# <span data-ttu-id="1b954-103">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="1b954-103">Restart-Computer</span></span>

## <span data-ttu-id="1b954-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1b954-104">SYNOPSIS</span></span>
<span data-ttu-id="1b954-105">Startet das Betriebssystem auf lokalen Computern und Remote Computern neu.</span><span class="sxs-lookup"><span data-stu-id="1b954-105">Restarts the operating system on local and remote computers.</span></span>

## <span data-ttu-id="1b954-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1b954-106">SYNTAX</span></span>

### <span data-ttu-id="1b954-107">Defaultset (Standard)</span><span class="sxs-lookup"><span data-stu-id="1b954-107">DefaultSet (Default)</span></span>

```
Restart-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential]<PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1b954-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1b954-108">DESCRIPTION</span></span>

<span data-ttu-id="1b954-109">`Restart-Computer`Mit dem-Cmdlet wird das Betriebssystem auf dem lokalen Computer und auf dem Remote Computer neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="1b954-109">The `Restart-Computer` cmdlet restarts the operating system on the local and remote computers.</span></span>

<span data-ttu-id="1b954-110">Sie können die Parameter von verwenden `Restart-Computer` , um die Neustart Vorgänge auszuführen, um die Authentifizierungs Ebenen und Alternative Anmelde Informationen anzugeben, um die Vorgänge einzuschränken, die gleichzeitig ausgeführt werden, und um einen sofortigen Neustart zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="1b954-110">You can use the parameters of `Restart-Computer` to run the restart operations, to specify the authentication levels and alternate credentials, to limit the operations that run at the same time, and to force an immediate restart.</span></span>

<span data-ttu-id="1b954-111">Ab Windows PowerShell 3,0 können Sie warten, bis der Neustart beendet ist, bevor Sie den nächsten Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="1b954-111">Starting in Windows PowerShell 3.0, you can wait for the restart to complete before you run the next command.</span></span> <span data-ttu-id="1b954-112">Geben Sie ein Wartezeit-und Abfrageintervall an, und warten Sie, bis bestimmte Dienste auf dem neu gestarteten Computer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1b954-112">Specify a waiting time-out and query interval, and wait for particular services to be available on the restarted computer.</span></span> <span data-ttu-id="1b954-113">Diese Funktion erleichtert die Verwendung von `Restart-Computer` in Skripts und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="1b954-113">This feature makes it practical to use `Restart-Computer` in scripts and functions.</span></span>

## <span data-ttu-id="1b954-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1b954-114">EXAMPLES</span></span>

### <span data-ttu-id="1b954-115">Beispiel 1: Neustarten des lokalen Computers</span><span class="sxs-lookup"><span data-stu-id="1b954-115">Example 1: Restart the local computer</span></span>

<span data-ttu-id="1b954-116">`Restart-Computer` startet den lokalen Computer neu.</span><span class="sxs-lookup"><span data-stu-id="1b954-116">`Restart-Computer` restarts the local computer.</span></span>

```powershell
Restart-Computer
```

### <span data-ttu-id="1b954-117">Beispiel 2: Neustarten mehrerer Computer</span><span class="sxs-lookup"><span data-stu-id="1b954-117">Example 2: Restart multiple computers</span></span>

<span data-ttu-id="1b954-118">`Restart-Computer` Remote Computer und lokale Computer können neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="1b954-118">`Restart-Computer` can restart remote and local computers.</span></span> <span data-ttu-id="1b954-119">Der Computer **Name** -Parameter akzeptiert ein Array von Computernamen.</span><span class="sxs-lookup"><span data-stu-id="1b954-119">The **ComputerName** parameter accepts an array of computer names.</span></span>

```powershell
Restart-Computer -ComputerName Server01, Server02, localhost
```

### <span data-ttu-id="1b954-120">Beispiel 3: erhalten von Computernamen aus einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="1b954-120">Example 3: Get computer names from a text file</span></span>

<span data-ttu-id="1b954-121">`Restart-Computer` Ruft eine Liste von Computernamen aus einer Textdatei ab und startet die Computer neu.</span><span class="sxs-lookup"><span data-stu-id="1b954-121">`Restart-Computer` gets a list of computer names from a text file and restarts the computers.</span></span> <span data-ttu-id="1b954-122">Der **Computername** -Parameter ist nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="1b954-122">The **ComputerName** parameter isn't specified.</span></span> <span data-ttu-id="1b954-123">Da es sich jedoch um den ersten Positions Parameter handelt, akzeptiert er die Computernamen aus der Textdatei, die über die Pipeline gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b954-123">But because it's the first position parameter, it accepts the computer names from the text file that are sent down the pipeline.</span></span>

```powershell
Get-Content -Path C:\Domain01.txt | Restart-Computer
```

<span data-ttu-id="1b954-124">`Get-Content` verwendet den **path** -Parameter, um eine Liste der Computernamen aus einer Textdatei, **Domain01.txt** , zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1b954-124">`Get-Content` uses the **Path** parameter to get a list of computer names from a text file, **Domain01.txt**.</span></span> <span data-ttu-id="1b954-125">Die Computernamen werden über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="1b954-125">The computer names are sent down the pipeline.</span></span> <span data-ttu-id="1b954-126">`Restart-Computer` startet jeden Computer neu.</span><span class="sxs-lookup"><span data-stu-id="1b954-126">`Restart-Computer` restarts each computer.</span></span>

### <span data-ttu-id="1b954-127">Beispiel 4: Erzwingen des Neustarts von Computern, die in einer Textdatei aufgeführt sind</span><span class="sxs-lookup"><span data-stu-id="1b954-127">Example 4: Force restart of computers listed in a text file</span></span>

<span data-ttu-id="1b954-128">Dieses Beispiel erzwingt einen sofortigen Neustart der Computer, die in der-Datei aufgeführt sind `Domain01.txt` .</span><span class="sxs-lookup"><span data-stu-id="1b954-128">This example forces an immediate restart of the computers listed in the `Domain01.txt` file.</span></span> <span data-ttu-id="1b954-129">Die Computernamen aus der Textdatei werden in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1b954-129">The computer names from the text file are stored in a variable.</span></span> <span data-ttu-id="1b954-130">Der **Force** -Parameter erzwingt einen sofortigen Neustart.</span><span class="sxs-lookup"><span data-stu-id="1b954-130">The **Force** parameter forces an immediate restart.</span></span>

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force
```

<span data-ttu-id="1b954-131">`Get-Content` verwendet den **path** -Parameter, um eine Liste der Computernamen aus einer Textdatei, **Domain01.txt** , zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1b954-131">`Get-Content` uses the **Path** parameter to get a list of computer names from a text file, **Domain01.txt**.</span></span> <span data-ttu-id="1b954-132">Die Computernamen werden in der Variablen gespeichert `$Names` .</span><span class="sxs-lookup"><span data-stu-id="1b954-132">The computer names are stored in the variable `$Names`.</span></span> <span data-ttu-id="1b954-133">`Get-Credential` fordert Sie zur Eingabe eines Benutzernamens und Kennworts auf und speichert die Werte in der Variablen `$Creds` .</span><span class="sxs-lookup"><span data-stu-id="1b954-133">`Get-Credential` prompts you for a username and password and stores the values in the variable `$Creds`.</span></span> <span data-ttu-id="1b954-134">`Restart-Computer` verwendet die Parameter " **Computername** " und " **Credential** " mit ihren Variablen.</span><span class="sxs-lookup"><span data-stu-id="1b954-134">`Restart-Computer` uses the **ComputerName** and **Credential** parameters with their variables.</span></span> <span data-ttu-id="1b954-135">Der **Force** -Parameter bewirkt einen sofortigen Neustart der einzelnen Computer.</span><span class="sxs-lookup"><span data-stu-id="1b954-135">The **Force** parameter causes an immediate restart of each computer.</span></span>

### <span data-ttu-id="1b954-136">Beispiel 6: Neustarten eines Remote Computers und warten auf PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b954-136">Example 6: Restart a remote computer and wait for PowerShell</span></span>

<span data-ttu-id="1b954-137">`Restart-Computer` startet den Remote Computer neu und wartet dann bis zu 5 Minuten (300 Sekunden) darauf, dass PowerShell auf dem neu gestarteten Computer verfügbar wird, bevor es fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="1b954-137">`Restart-Computer` restarts the remote computer and then waits up to 5 minutes (300 seconds) for PowerShell to become available on the restarted computer before it continues.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

<span data-ttu-id="1b954-138">`Restart-Computer` verwendet den **Computername** -Parameter, um **Server01** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1b954-138">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01**.</span></span> <span data-ttu-id="1b954-139">Der **Wait** -Parameter wartet, bis der Neustart abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1b954-139">The **Wait** parameter waits for the restart to finish.</span></span> <span data-ttu-id="1b954-140">Der **für** gibt an, dass PowerShell Befehle auf dem Remote Computer ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="1b954-140">The **For** specifies that PowerShell can run commands on the remote computer.</span></span> <span data-ttu-id="1b954-141">Der **Timeout** -Parameter gibt eine Wartezeit von fünf Minuten an.</span><span class="sxs-lookup"><span data-stu-id="1b954-141">The **Timeout** parameter specifies a five-minute wait.</span></span> <span data-ttu-id="1b954-142">Der **Verzögerungs** Parameter fragt den Remote Computer alle zwei Sekunden ab, um zu bestimmen, ob er neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1b954-142">The **Delay** parameter queries the remote computer every two seconds to determine whether it's restarted.</span></span>

### <span data-ttu-id="1b954-143">Beispiel 7: Neustarten eines Computers mithilfe von wsmanauthentication</span><span class="sxs-lookup"><span data-stu-id="1b954-143">Example 7: Restart a computer by using WsmanAuthentication</span></span>

<span data-ttu-id="1b954-144">`Restart-Computer` der Remote Computer wird mit dem **wsmanauthentication** -Mechanismus neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="1b954-144">`Restart-Computer` restarts the remote computer using the **WsmanAuthentication** mechanism.</span></span>
<span data-ttu-id="1b954-145">Die Kerberos-Authentifizierung bestimmt, ob der aktuelle Benutzer über die Berechtigung zum Neustarten des Remote Computers verfügt.</span><span class="sxs-lookup"><span data-stu-id="1b954-145">Kerberos authentication determines whether the current user has permission to restart the remote computer.</span></span> <span data-ttu-id="1b954-146">Weitere Informationen finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="1b954-146">For more information, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

```powershell
Restart-Computer -ComputerName Server01 -WsmanAuthentication Kerberos
```

<span data-ttu-id="1b954-147">`Restart-Computer` verwendet den **Computername** -Parameter, um den Remote Computer anzugeben, **Server01**.</span><span class="sxs-lookup"><span data-stu-id="1b954-147">`Restart-Computer` uses the **ComputerName** parameter to specify the remote computer, **Server01**.</span></span>
<span data-ttu-id="1b954-148">Der **wsmanauthentication** -Parameter gibt die Authentifizierungsmethode als **Kerberos** an.</span><span class="sxs-lookup"><span data-stu-id="1b954-148">The **WsmanAuthentication** parameter specifies the authentication method as **Kerberos**.</span></span>

## <span data-ttu-id="1b954-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1b954-149">PARAMETERS</span></span>

### <span data-ttu-id="1b954-150">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="1b954-150">-ComputerName</span></span>

<span data-ttu-id="1b954-151">Gibt einen Computernamen oder ein durch Trennzeichen getrenntes Array von Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="1b954-151">Specifies one computer name or a comma-separated array of computer names.</span></span> <span data-ttu-id="1b954-152">`Restart-Computer` nimmt **Computername** -Objekte aus der Pipeline oder den Variablen an.</span><span class="sxs-lookup"><span data-stu-id="1b954-152">`Restart-Computer` accepts **ComputerName** objects from the pipeline or variables.</span></span>

<span data-ttu-id="1b954-153">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein.</span><span class="sxs-lookup"><span data-stu-id="1b954-153">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span> <span data-ttu-id="1b954-154">Geben Sie den Computernamen, einen Punkt oder einen localhost ein, um den lokalen Computer anzugeben `.` .</span><span class="sxs-lookup"><span data-stu-id="1b954-154">To specify the local computer, type the computer name, a dot `.`, or localhost.</span></span>

<span data-ttu-id="1b954-155">Dieser Parameter beruht nicht auf PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="1b954-155">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="1b954-156">Sie können den **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1b954-156">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

<span data-ttu-id="1b954-157">Wenn der **Computername** -Parameter nicht angegeben ist, wird `Restart-Computer` der lokale Computer neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="1b954-157">If the **ComputerName** parameter isn't specified, `Restart-Computer` restarts the local computer.</span></span>

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

### <span data-ttu-id="1b954-158">-Credential</span><span class="sxs-lookup"><span data-stu-id="1b954-158">-Credential</span></span>

<span data-ttu-id="1b954-159">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="1b954-159">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="1b954-160">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1b954-160">The default is the current user.</span></span>

<span data-ttu-id="1b954-161">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1b954-161">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="1b954-162">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="1b954-162">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="1b954-163">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1b954-163">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="1b954-164">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="1b954-164">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="1b954-165">-Verzögerung</span><span class="sxs-lookup"><span data-stu-id="1b954-165">-Delay</span></span>

<span data-ttu-id="1b954-166">Gibt die Häufigkeit von Abfragen in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="1b954-166">Specifies the frequency of queries, in seconds.</span></span> <span data-ttu-id="1b954-167">PowerShell fragt den durch den **for** -Parameter angegebenen Dienst ab, um zu bestimmen, ob der Dienst nach dem Neustart des Computers verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1b954-167">PowerShell queries the service specified by the **For** parameter to determine whether the service is available after the computer is restarted.</span></span>

<span data-ttu-id="1b954-168">Dieser Parameter ist nur in Verbindung mit den **Wait** -und **for** -Parametern gültig.</span><span class="sxs-lookup"><span data-stu-id="1b954-168">This parameter is valid only together with the **Wait** and **For** parameters.</span></span>

<span data-ttu-id="1b954-169">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1b954-169">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="1b954-170">Wenn der **Delay** -Parameter nicht angegeben wird, `Restart-Computer` verwendet eine Verzögerung von fünf Sekunden.</span><span class="sxs-lookup"><span data-stu-id="1b954-170">If the **Delay** parameter isn't specified, `Restart-Computer` uses a five second delay.</span></span>

```yaml
Type: System.Int16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b954-171">-Für</span><span class="sxs-lookup"><span data-stu-id="1b954-171">-For</span></span>

<span data-ttu-id="1b954-172">Gibt das Verhalten von PowerShell an, da es darauf wartet, dass der angegebene Dienst oder das Feature nach dem Neustart des Computers verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="1b954-172">Specifies the behavior of PowerShell as it waits for the specified service or feature to become available after the computer restarts.</span></span> <span data-ttu-id="1b954-173">Dieser Parameter ist nur mit dem **Wait** -Parameter gültig.</span><span class="sxs-lookup"><span data-stu-id="1b954-173">This parameter is only valid with the **Wait** parameter.</span></span>

<span data-ttu-id="1b954-174">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="1b954-174">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1b954-175">**Standard** : wartet darauf, dass PowerShell neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1b954-175">**Default** : Waits for PowerShell to restart.</span></span>
- <span data-ttu-id="1b954-176">**PowerShell** : kann Befehle in einer PowerShell-Remote Sitzung auf dem Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="1b954-176">**PowerShell** : Can run commands in a PowerShell remote session on the computer.</span></span>
- <span data-ttu-id="1b954-177">**WMI** : empfängt eine Antwort auf eine Win32_ComputerSystem Abfrage für den Computer.</span><span class="sxs-lookup"><span data-stu-id="1b954-177">**WMI** : Receives a reply to a Win32_ComputerSystem query for the computer.</span></span>
- <span data-ttu-id="1b954-178">**WinRM** : kann mithilfe von WS-Management eine Remote Sitzung mit dem Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="1b954-178">**WinRM** : Can establish a remote session to the computer by using WS-Management.</span></span>

<span data-ttu-id="1b954-179">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1b954-179">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: (All)
Aliases:
Accepted values: Wmi, WinRM, PowerShell

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b954-180">-Force</span><span class="sxs-lookup"><span data-stu-id="1b954-180">-Force</span></span>

<span data-ttu-id="1b954-181">Erzwingt einen sofortigen Neustart des Computers.</span><span class="sxs-lookup"><span data-stu-id="1b954-181">Forces an immediate restart of the computer.</span></span>

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

### <span data-ttu-id="1b954-182">-Timeout</span><span class="sxs-lookup"><span data-stu-id="1b954-182">-Timeout</span></span>

<span data-ttu-id="1b954-183">Gibt die Dauer des Wartevorgangs in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="1b954-183">Specifies the duration of the wait, in seconds.</span></span> <span data-ttu-id="1b954-184">Wenn das Timeout abläuft, `Restart-Computer` kehrt zur Eingabeaufforderung zurück, auch wenn die Computer nicht neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="1b954-184">When the timeout elapses, `Restart-Computer` returns to the command prompt, even if the computers aren't restarted.</span></span>

<span data-ttu-id="1b954-185">Der **Timeout** -Parameter ist nur mit dem **Wait** -Parameter gültig.</span><span class="sxs-lookup"><span data-stu-id="1b954-185">The **Timeout** parameter is only valid with the **Wait** parameter.</span></span> <span data-ttu-id="1b954-186">**Timeout** überschreibt den unbegrenzten warte Zeitraum des **Wait** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="1b954-186">**Timeout** overrides the **Wait** parameter's indefinite waiting period.</span></span>

<span data-ttu-id="1b954-187">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1b954-187">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b954-188">-Wait</span><span class="sxs-lookup"><span data-stu-id="1b954-188">-Wait</span></span>

<span data-ttu-id="1b954-189">`Restart-Computer` unterdrückt die PowerShell-Eingabeaufforderung und blockiert die Pipeline, bis die Computer neu gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="1b954-189">`Restart-Computer` suppresses the PowerShell prompt and blocks the pipeline until the computers have restarted.</span></span> <span data-ttu-id="1b954-190">Sie können diesen Parameter in einem Skript verwenden, um Computer neu zu starten und die Verarbeitung anschließend fortzusetzen, wenn der Neustart abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1b954-190">You can use this parameter in a script to restart computers and then continue to process when the restart is finished.</span></span>

<span data-ttu-id="1b954-191">Der **Wait** -Parameter wartet unbegrenzt, bis der Computer neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1b954-191">The **Wait** parameter waits indefinitely for the computers to restart.</span></span> <span data-ttu-id="1b954-192">Mit **Timeout** können Sie die zeitliche Steuerung und die Parameter **für** und **Verzögerung** anpassen, um zu warten, bis bestimmte Dienste auf den neu gestarteten Computern verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1b954-192">You can use **Timeout** to adjust the timing and the **For** and **Delay** parameters to wait for particular services to become available on the restarted computers.</span></span>

<span data-ttu-id="1b954-193">Der **Wait** -Parameter ist nicht gültig, wenn Sie den lokalen Computer neu starten.</span><span class="sxs-lookup"><span data-stu-id="1b954-193">The **Wait** parameter isn't valid when you're restarting the local computer.</span></span> <span data-ttu-id="1b954-194">Wenn der Wert des **Computername** -Parameters die Namen der Remote Computer und des lokalen Computers enthält, `Restart-Computer` generiert einen Fehler ohne Abbruch auf dem lokalen Computer, wartet **jedoch auf** den Neustart der Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="1b954-194">If the value of the **ComputerName** parameter contains the names of remote computers and the local computer, `Restart-Computer` generates a non-terminating error for **Wait** on the local computer, but waits for the remote computers to restart.</span></span>

<span data-ttu-id="1b954-195">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1b954-195">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="1b954-196">-Wsmanauthentication</span><span class="sxs-lookup"><span data-stu-id="1b954-196">-WsmanAuthentication</span></span>

<span data-ttu-id="1b954-197">Gibt den Mechanismus an, der verwendet wird, um die Benutzer Anmelde Informationen zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="1b954-197">Specifies the mechanism that is used to authenticate the user credentials.</span></span> <span data-ttu-id="1b954-198">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1b954-198">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="1b954-199">Die zulässigen Werte für diesen Parameter sind: **Basic** , **kredssp** , **default** , **Digest** , **Kerberos** und **Aushandlungs**.</span><span class="sxs-lookup"><span data-stu-id="1b954-199">The acceptable values for this parameter are: **Basic** , **CredSSP** , **Default** , **Digest** , **Kerberos** , and **Negotiate**.</span></span>

<span data-ttu-id="1b954-200">Weitere Informationen finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="1b954-200">For more information, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="1b954-201">Die Authentifizierung des Anmelde Informations Diensts (Credential Security Service Provider, kredssp), in der die Benutzer Anmelde Informationen an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehreren Ressourcen erfordern</span><span class="sxs-lookup"><span data-stu-id="1b954-201">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="1b954-202">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="1b954-202">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="1b954-203">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b954-203">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Basic, CredSSP, Default, Digest, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b954-204">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1b954-204">-Confirm</span></span>

<span data-ttu-id="1b954-205">Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Restart-Computer` .</span><span class="sxs-lookup"><span data-stu-id="1b954-205">Prompts you for confirmation before running `Restart-Computer`.</span></span>

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

### <span data-ttu-id="1b954-206">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1b954-206">-WhatIf</span></span>

<span data-ttu-id="1b954-207">Zeigt, was geschieht, wenn die ausgeführt wird `Restart-Computer` .</span><span class="sxs-lookup"><span data-stu-id="1b954-207">Shows what would happen if the `Restart-Computer` runs.</span></span> <span data-ttu-id="1b954-208">Das- `Restart-Computer` Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1b954-208">The `Restart-Computer` cmdlet isn't run.</span></span>

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

### <span data-ttu-id="1b954-209">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1b954-209">CommonParameters</span></span>

<span data-ttu-id="1b954-210">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1b954-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1b954-211">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1b954-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1b954-212">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1b954-212">INPUTS</span></span>

### <span data-ttu-id="1b954-213">System.String</span><span class="sxs-lookup"><span data-stu-id="1b954-213">System.String</span></span>

<span data-ttu-id="1b954-214">`Restart-Computer` nimmt Computernamen aus der Pipeline oder den Variablen an.</span><span class="sxs-lookup"><span data-stu-id="1b954-214">`Restart-Computer` accepts computer names from the pipeline or variables.</span></span>

## <span data-ttu-id="1b954-215">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1b954-215">OUTPUTS</span></span>

### <span data-ttu-id="1b954-216">Keine</span><span class="sxs-lookup"><span data-stu-id="1b954-216">None</span></span>

<span data-ttu-id="1b954-217">`Restart-Computer` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="1b954-217">`Restart-Computer` doesn't generate any output.</span></span>

## <span data-ttu-id="1b954-218">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1b954-218">NOTES</span></span>

<span data-ttu-id="1b954-219">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1b954-219">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="1b954-220">`Restart-Computer` funktioniert nur auf Computern unter Windows und erfordert, dass WinRM und WMI ein System Herunterfahren, einschließlich des lokalen Systems.</span><span class="sxs-lookup"><span data-stu-id="1b954-220">`Restart-Computer` only works on computers running Windows and requires WinRM and WMI to shutdown a system, including the local system.</span></span>
- <span data-ttu-id="1b954-221">`Restart-Computer` verwendet die [Win32Shutdown-Methode](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) der WMI- [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) Klasse (Windows-Verwaltungsinstrumentation).</span><span class="sxs-lookup"><span data-stu-id="1b954-221">`Restart-Computer` uses the [Win32Shutdown method](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) of the Windows Management Instrumentation (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) class.</span></span> <span data-ttu-id="1b954-222">Diese Methode erfordert, dass die **SeShutdownPrivilege** -Berechtigung für das Benutzerkonto aktiviert ist, mit dem der Computer neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1b954-222">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

## <span data-ttu-id="1b954-223">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1b954-223">RELATED LINKS</span></span>

[<span data-ttu-id="1b954-224">Informationen zu Windows-Remoteverwaltung</span><span class="sxs-lookup"><span data-stu-id="1b954-224">About Windows Remote Management</span></span>](/windows/desktop/WinRM/about-windows-remote-management)

[<span data-ttu-id="1b954-225">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="1b954-225">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="1b954-226">WS-Verwaltungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="1b954-226">WS-Management Protocol</span></span>](/windows/desktop/WinRM/ws-management-protocol)
