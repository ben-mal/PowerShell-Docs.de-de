---
description: Hier finden Sie Fragen und Antworten zum Ausführen von Remote Befehlen in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_faq?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_FAQ
ms.openlocfilehash: db3b7b554096c0cee6f13365dd8b2fbacb498282
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222895"
---
# <a name="about-remote-faq"></a><span data-ttu-id="25a92-104">About Remote FAQ</span><span class="sxs-lookup"><span data-stu-id="25a92-104">About Remote FAQ</span></span>

## <a name="short-description"></a><span data-ttu-id="25a92-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25a92-105">Short description</span></span>
<span data-ttu-id="25a92-106">Hier finden Sie Fragen und Antworten zum Ausführen von Remote Befehlen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25a92-106">Contains questions and answers about running remote commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="25a92-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25a92-107">Long description</span></span>

<span data-ttu-id="25a92-108">Wenn Sie Remote arbeiten, geben Sie Befehle in PowerShell auf einem Computer (als "lokaler Computer" bezeichnet) ein, die Befehle werden jedoch auf einem anderen Computer ausgeführt (der als "Remote Computer" bezeichnet wird).</span><span class="sxs-lookup"><span data-stu-id="25a92-108">When you work remotely, you type commands in PowerShell on one computer (known as the "local computer"), but the commands run on another computer (known as the "remote computer").</span></span> <span data-ttu-id="25a92-109">Die Remote Arbeit sollte so ähnlich wie möglich auf dem Remote Computer funktionieren.</span><span class="sxs-lookup"><span data-stu-id="25a92-109">The experience of working remotely should be as much like working directly at the remote computer as possible.</span></span>

<span data-ttu-id="25a92-110">Hinweis: um PowerShell-Remoting zu verwenden, muss der Remote Computer für Remoting konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="25a92-110">Note: To use PowerShell remoting, the remote computer must be configured for remoting.</span></span> <span data-ttu-id="25a92-111">Weitere Informationen finden Sie unter [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25a92-111">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

### <a name="must-both-computers-have-powershell-installed"></a><span data-ttu-id="25a92-112">Muss PowerShell auf beiden Computern installiert sein?</span><span class="sxs-lookup"><span data-stu-id="25a92-112">Must both computers have PowerShell installed?</span></span>

<span data-ttu-id="25a92-113">Ja.</span><span class="sxs-lookup"><span data-stu-id="25a92-113">Yes.</span></span> <span data-ttu-id="25a92-114">Für die Remote Ausführung müssen auf dem lokalen Computer und auf dem Remote Computer PowerShell, das Microsoft .NET-Framework und das WS-Management-Protokoll (Web Services for Management) vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="25a92-114">To work remotely, the local and remote computers must have PowerShell, the Microsoft .NET Framework, and the Web Services for Management (WS-Management) protocol.</span></span> <span data-ttu-id="25a92-115">Alle Dateien und anderen Ressourcen, die zum Ausführen eines bestimmten Befehls benötigt werden, müssen sich auf dem Remote Computer befinden.</span><span class="sxs-lookup"><span data-stu-id="25a92-115">Any files and other resources that are needed to execute a particular command must be on the remote computer.</span></span>

<span data-ttu-id="25a92-116">Computer mit Windows PowerShell 3,0 und Computern, auf denen Windows PowerShell 2,0 ausgeführt wird, können eine Remote Verbindung herstellen und Remote Befehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="25a92-116">Computers running Windows PowerShell 3.0 and computers running Windows PowerShell 2.0 can connect to each other remotely and run remote commands.</span></span>
<span data-ttu-id="25a92-117">Einige Features, z. b. die Möglichkeit, eine Verbindung mit einer Sitzung herzustellen und erneut eine Verbindung herzustellen, funktionieren jedoch nur, wenn auf beiden Computern Windows PowerShell 3,0 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="25a92-117">However, some features, such as the ability to disconnect from a session and reconnect to it, work only when both computers are running Windows PowerShell 3.0.</span></span>

<span data-ttu-id="25a92-118">Sie müssen über die Berechtigung zum Herstellen einer Verbindung mit dem Remote Computer, die Berechtigung zum Ausführen von PowerShell und die Berechtigung zum Zugreifen auf Datenspeicher (z. b. Dateien und Ordner) und die Registrierung auf dem Remote Computer verfügen.</span><span class="sxs-lookup"><span data-stu-id="25a92-118">You must have permission to connect to the remote computer, permission to run PowerShell, and permission to access data stores (such as files and folders), and the registry on the remote computer.</span></span>

<span data-ttu-id="25a92-119">Weitere Informationen finden Sie unter [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25a92-119">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

### <a name="how-does-remoting-work"></a><span data-ttu-id="25a92-120">Funktionsweise von Remoting</span><span class="sxs-lookup"><span data-stu-id="25a92-120">How does remoting work?</span></span>

<span data-ttu-id="25a92-121">Wenn Sie einen Remote Befehl übermitteln, wird der Befehl über das Netzwerk an das PowerShell-Modul auf dem Remote Computer übertragen und im PowerShell-Client auf dem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="25a92-121">When you submit a remote command, the command is transmitted across the network to the PowerShell engine on the remote computer, and it runs in the PowerShell client on the remote computer.</span></span> <span data-ttu-id="25a92-122">Die Befehls Ergebnisse werden zurück an den lokalen Computer gesendet und in der PowerShell-Sitzung auf dem lokalen Computer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25a92-122">The command results are sent back to the local computer and appear in the PowerShell session on the local computer.</span></span>

<span data-ttu-id="25a92-123">Zum Übertragen der Befehle und empfangen der Ausgabe verwendet PowerShell das WS-Management Protokoll.</span><span class="sxs-lookup"><span data-stu-id="25a92-123">To transmit the commands and receive the output, PowerShell uses the WS-Management protocol.</span></span> <span data-ttu-id="25a92-124">Weitere Informationen zum WS-Management-Protokoll finden Sie unter [WS-Management-Protokoll](/windows/win32/winrm/ws-management-protocol) in der Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="25a92-124">For information about the WS-Management protocol, see [WS-Management Protocol](/windows/win32/winrm/ws-management-protocol) in the Windows documentation.</span></span>

<span data-ttu-id="25a92-125">Ab Windows PowerShell 3,0 werden Remote Sitzungen auf dem Remote Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="25a92-125">Beginning in Windows PowerShell 3.0, remote sessions are stored on the remote computer.</span></span> <span data-ttu-id="25a92-126">Auf diese Weise können Sie die Verbindung mit der Sitzung trennen und die Verbindung von einer anderen Sitzung oder einem anderen Computer wiederherstellen, ohne die Befehle zu unterbrechen oder den Zustand zu verlieren.</span><span class="sxs-lookup"><span data-stu-id="25a92-126">This enables you to disconnect from the session and reconnect from a different session or a different computer without interrupting the commands or losing state.</span></span>

### <a name="is-powershell-remoting-secure"></a><span data-ttu-id="25a92-127">Ist PowerShell-Remoting sicher?</span><span class="sxs-lookup"><span data-stu-id="25a92-127">Is PowerShell remoting secure?</span></span>

<span data-ttu-id="25a92-128">Wenn Sie eine Verbindung mit einem Remote Computer herstellen, verwendet das System die Anmelde Informationen für Benutzername und Kennwort auf dem lokalen Computer oder die Anmelde Informationen, die Sie im Befehl angeben, um Sie beim Remote Computer anzumelden.</span><span class="sxs-lookup"><span data-stu-id="25a92-128">When you connect to a remote computer, the system uses the username and password credentials on the local computer or the credentials that you supply in the command to log you in to the remote computer.</span></span> <span data-ttu-id="25a92-129">Die Anmelde Informationen und die restliche Übertragung werden verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="25a92-129">The credentials and the rest of the transmission are encrypted.</span></span>

<span data-ttu-id="25a92-130">Um zusätzlichen Schutz hinzuzufügen, können Sie den Remote Computer so konfigurieren, dass er Secure Sockets Layer (SSL) anstelle von HTTP verwendet, um auf Windows-Remoteverwaltung (WinRM)-Anforderungen zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="25a92-130">To add additional protection, you can configure the remote computer to use Secure Sockets Layer (SSL) instead of HTTP to listen for Windows Remote Management (WinRM) requests.</span></span> <span data-ttu-id="25a92-131">Anschließend können Benutzer beim Herstellen einer Verbindung **den Parameter "** -Parameter" der `Invoke-Command` `New-PSSession` `Enter-PSSession` Cmdlets, und verwenden.</span><span class="sxs-lookup"><span data-stu-id="25a92-131">Then, users can use the **UseSSL** parameter of the `Invoke-Command`, `New-PSSession`, and `Enter-PSSession` cmdlets when establishing a connection.</span></span> <span data-ttu-id="25a92-132">Diese Option verwendet den sichereren HTTPS-Kanal anstelle von http.</span><span class="sxs-lookup"><span data-stu-id="25a92-132">This option uses the more secure HTTPS channel instead of HTTP.</span></span>

### <a name="do-all-remote-commands-require-powershell-remoting"></a><span data-ttu-id="25a92-133">Benötigen alle Remote Befehle PowerShell-Remoting?</span><span class="sxs-lookup"><span data-stu-id="25a92-133">Do all remote commands require PowerShell remoting?</span></span>

<span data-ttu-id="25a92-134">Nein.</span><span class="sxs-lookup"><span data-stu-id="25a92-134">No.</span></span> <span data-ttu-id="25a92-135">Mehrere Cmdlets verfügen über einen **Computername** -Parameter, mit dem Sie Objekte vom Remote Computer erhalten.</span><span class="sxs-lookup"><span data-stu-id="25a92-135">Several cmdlets have a **ComputerName** parameter that lets you get objects from the remote computer.</span></span>

<span data-ttu-id="25a92-136">Diese Cmdlets verwenden nicht PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="25a92-136">These cmdlets do not use PowerShell remoting.</span></span> <span data-ttu-id="25a92-137">Sie können Sie also auf allen Computern verwenden, auf denen PowerShell ausgeführt wird, auch wenn der Computer nicht für PowerShell-Remoting konfiguriert ist oder der Computer die Anforderungen für PowerShell-Remoting nicht erfüllt.</span><span class="sxs-lookup"><span data-stu-id="25a92-137">So, you can use them on any computer that is running PowerShell, even if the computer is not configured for PowerShell remoting or if the computer does not meet the requirements for PowerShell remoting.</span></span>

<span data-ttu-id="25a92-138">Diese Cmdlets umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="25a92-138">These cmdlets include the following:</span></span>

- `Get-Process`
- `Get-Service`
- `Get-WinEvent`
- `Get-EventLog`
- `Test-Connection`

<span data-ttu-id="25a92-139">Um alle Cmdlets mit dem **Computername** -Parameter zu suchen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="25a92-139">To find all the cmdlets with a **ComputerName** parameter, type:</span></span>

```powershell
Get-Help * -Parameter ComputerName
# or
Get-Command -ParameterName ComputerName
```

<span data-ttu-id="25a92-140">Informationen zum bestimmen, ob der **Computername** -Parameter eines bestimmten Cmdlets PowerShell-Remoting erfordert, finden Sie in der Beschreibung des Parameters.</span><span class="sxs-lookup"><span data-stu-id="25a92-140">To determine whether the **ComputerName** parameter of a particular cmdlet requires PowerShell remoting, see the parameter description.</span></span> <span data-ttu-id="25a92-141">Geben Sie Folgendes ein, um die Parameter Beschreibung anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="25a92-141">To display the parameter description, type:</span></span>

```powershell
Get-Help <cmdlet-name> -Parameter ComputerName
```

<span data-ttu-id="25a92-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="25a92-142">For example:</span></span>

```powershell
Get-Help Get-Process -Parameter ComputerName
```

<span data-ttu-id="25a92-143">Verwenden Sie für alle anderen Befehle das- `Invoke-Command` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="25a92-143">For all other commands, use the `Invoke-Command` cmdlet.</span></span>

### <a name="how-do-i-run-a-command-on-a-remote-computer"></a><span data-ttu-id="25a92-144">Gewusst wie führen Sie einen Befehl auf einem Remote Computer aus?</span><span class="sxs-lookup"><span data-stu-id="25a92-144">How do I run a command on a remote computer?</span></span>

<span data-ttu-id="25a92-145">Verwenden Sie das-Cmdlet, um einen Befehl auf einem Remote Computer auszuführen `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="25a92-145">To run a command on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="25a92-146">Schließen Sie den Befehl in geschweifte Klammern ( `{}` ) ein, um ihn als Skriptblock zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="25a92-146">Enclose your command in braces (`{}`) to make it a script block.</span></span> <span data-ttu-id="25a92-147">Verwenden Sie den **ScriptBlock** -Parameter von `Invoke-Command` , um den Befehl anzugeben.</span><span class="sxs-lookup"><span data-stu-id="25a92-147">Use the **ScriptBlock** parameter of `Invoke-Command` to specify the command.</span></span>

<span data-ttu-id="25a92-148">Sie können den **Computername** -Parameter von verwenden `Invoke-Command` , um einen Remote Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="25a92-148">You can use the **ComputerName** parameter of `Invoke-Command` to specify a remote computer.</span></span> <span data-ttu-id="25a92-149">Oder Sie können eine permanente Verbindung mit einem Remote Computer (eine-Sitzung) erstellen und dann den **Session** -Parameter von verwenden `Invoke-Command` , um den Befehl in der Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="25a92-149">Or, you can create a persistent connection to a remote computer (a session) and then use the **Session** parameter of `Invoke-Command` to run the command in the session.</span></span>

<span data-ttu-id="25a92-150">Beispielsweise führen die folgenden Befehle einen `Get-Process` Befehl Remote aus.</span><span class="sxs-lookup"><span data-stu-id="25a92-150">For example, the following commands run a `Get-Process` command remotely.</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-Process}

#  - OR -

Invoke-Command -Session $s -ScriptBlock {Get-Process}
```

<span data-ttu-id="25a92-151">Um einen Remote Befehl zu unterbrechen, geben Sie <kbd>STRG</kbd> + <kbd>C</kbd>ein.</span><span class="sxs-lookup"><span data-stu-id="25a92-151">To interrupt a remote command, type <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="25a92-152">Die Unterbrechungs Anforderung wird an den Remote Computer weitergeleitet, wo der Remote Befehl beendet wird.</span><span class="sxs-lookup"><span data-stu-id="25a92-152">The interruption request is passed to the remote computer, where it terminates the remote command.</span></span>

<span data-ttu-id="25a92-153">Weitere Informationen zu Remote Befehlen finden Sie unter about_Remote und in den Hilfe Themen für die Cmdlets, die Remoting unterstützen.</span><span class="sxs-lookup"><span data-stu-id="25a92-153">For more information about remote commands, see about_Remote and the Help topics for the cmdlets that support remoting.</span></span>

### <a name="can-i-just-telnet-into-a-remote-computer"></a><span data-ttu-id="25a92-154">Kann ich nur Telnet auf einem Remote Computer ausführen?</span><span class="sxs-lookup"><span data-stu-id="25a92-154">Can I just telnet into a remote computer?</span></span>

<span data-ttu-id="25a92-155">Mit dem- `Enter-PSSession` Cmdlet können Sie eine interaktive Sitzung mit einem Remote Computer starten.</span><span class="sxs-lookup"><span data-stu-id="25a92-155">You can use the `Enter-PSSession` cmdlet to start an interactive session with a remote computer.</span></span>

<span data-ttu-id="25a92-156">Geben Sie an der PowerShell-Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="25a92-156">At the PowerShell prompt, type:</span></span>

```powershell
Enter-PSSession <ComputerName>
```

<span data-ttu-id="25a92-157">Die Eingabeaufforderung ändert sich, um anzuzeigen, dass Sie mit dem Remote Computer verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="25a92-157">The command prompt changes to show that you are connected to the remote computer.</span></span>

```
<ComputerName>\C:>
```

<span data-ttu-id="25a92-158">Nun werden die Befehle, die Sie eingeben, auf dem Remote Computer ausgeführt, so als würden Sie Sie direkt auf dem Remote Computer eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="25a92-158">Now, the commands that you type run on the remote computer just as though you typed them directly on the remote computer.</span></span>

<span data-ttu-id="25a92-159">Um die interaktive Sitzung zu beenden, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="25a92-159">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="25a92-160">Eine interaktive Sitzung ist eine persistente Sitzung, die das WS-Management-Protokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="25a92-160">An interactive session is a persistent session that uses the WS-Management protocol.</span></span> <span data-ttu-id="25a92-161">Sie ist nicht mit der Verwendung von Telnet identisch, bietet aber eine ähnliche Darstellung.</span><span class="sxs-lookup"><span data-stu-id="25a92-161">It is not the same as using Telnet, but it provides a similar experience.</span></span>

<span data-ttu-id="25a92-162">Weitere Informationen finden Sie unter `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="25a92-162">For more information, see `Enter-PSSession`.</span></span>

### <a name="can-i-create-a-persistent-connection"></a><span data-ttu-id="25a92-163">Kann ich eine permanente Verbindung erstellen?</span><span class="sxs-lookup"><span data-stu-id="25a92-163">Can I create a persistent connection?</span></span>

<span data-ttu-id="25a92-164">Ja.</span><span class="sxs-lookup"><span data-stu-id="25a92-164">Yes.</span></span> <span data-ttu-id="25a92-165">Sie können Remote Befehle ausführen, indem Sie den Namen des Remote Computers, den NetBIOS-Namen oder die zugehörige IP-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="25a92-165">You can run remote commands by specifying the name of the remote computer, its NetBIOS name, or its IP address.</span></span> <span data-ttu-id="25a92-166">Oder Sie können Remote Befehle ausführen, indem Sie eine PowerShell-Sitzung (PSSession) angeben, die mit dem Remote Computer verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="25a92-166">Or, you can run remote commands by specifying a PowerShell session (PSSession) that is connected to the remote computer.</span></span>

<span data-ttu-id="25a92-167">Wenn Sie den **Computername** -Parameter von `Invoke-Command` oder verwenden `Enter-PSSession` , stellt PowerShell eine temporäre Verbindung her.</span><span class="sxs-lookup"><span data-stu-id="25a92-167">When you use the **ComputerName** parameter of `Invoke-Command` or `Enter-PSSession`, PowerShell establishes a temporary connection.</span></span> <span data-ttu-id="25a92-168">PowerShell verwendet die Verbindung, um nur den aktuellen Befehl auszuführen, und schließt dann die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="25a92-168">PowerShell uses the connection to run only the current command, and then it closes the connection.</span></span> <span data-ttu-id="25a92-169">Dies ist eine sehr effiziente Methode zum Ausführen eines einzelnen Befehls oder mehrerer nicht zusammenhängender Befehle, auch auf vielen Remote Computern.</span><span class="sxs-lookup"><span data-stu-id="25a92-169">This is a very efficient method for running a single command or several unrelated commands, even on many remote computers.</span></span>

<span data-ttu-id="25a92-170">Wenn Sie mit dem `New-PSSession` Cmdlet eine PSSession erstellen, stellt PowerShell eine permanente Verbindung für die PSSession her.</span><span class="sxs-lookup"><span data-stu-id="25a92-170">When you use the `New-PSSession` cmdlet to create a PSSession, PowerShell establishes a persistent connection for the PSSession.</span></span> <span data-ttu-id="25a92-171">Anschließend können Sie mehrere Befehle in der PSSession ausführen, einschließlich der Befehle, die Daten gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="25a92-171">Then, you can run multiple commands in the PSSession, including commands that share data.</span></span>

<span data-ttu-id="25a92-172">In der Regel erstellen Sie eine PSSession, um eine Reihe verwandter Befehle auszuführen, die Daten gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="25a92-172">Typically, you create a PSSession to run a series of related commands that share data.</span></span> <span data-ttu-id="25a92-173">Andernfalls ist die temporäre Verbindung, die vom **Computername** -Parameter erstellt wurde, für die meisten Befehle ausreichend.</span><span class="sxs-lookup"><span data-stu-id="25a92-173">Otherwise, the temporary connection created by the **ComputerName** parameter is sufficient for most commands.</span></span>

<span data-ttu-id="25a92-174">Weitere Informationen zu Sitzungen finden Sie unter about_PSSessions.</span><span class="sxs-lookup"><span data-stu-id="25a92-174">For more information about sessions, see about_PSSessions.</span></span>

### <a name="can-i-run-commands-on-more-than-one-computer-at-a-time"></a><span data-ttu-id="25a92-175">Kann ich Befehle gleichzeitig auf mehreren Computern ausführen?</span><span class="sxs-lookup"><span data-stu-id="25a92-175">Can I run commands on more than one computer at a time?</span></span>

<span data-ttu-id="25a92-176">Ja.</span><span class="sxs-lookup"><span data-stu-id="25a92-176">Yes.</span></span> <span data-ttu-id="25a92-177">Der Computer **Name** -Parameter des `Invoke-Command` Cmdlets akzeptiert mehrere Computernamen, und der **Session** -Parameter akzeptiert mehrere pssessions.</span><span class="sxs-lookup"><span data-stu-id="25a92-177">The **ComputerName** parameter of the `Invoke-Command` cmdlet accepts multiple computer names, and the **Session** parameter accepts multiple PSSessions.</span></span>

<span data-ttu-id="25a92-178">Wenn Sie einen `Invoke-Command` Befehl ausführen, führt PowerShell die Befehle auf allen angegebenen Computern oder in allen angegebenen pssessions aus.</span><span class="sxs-lookup"><span data-stu-id="25a92-178">When you run an `Invoke-Command` command, PowerShell runs the commands on all of the specified computers or in all of the specified PSSessions.</span></span>

<span data-ttu-id="25a92-179">PowerShell kann Hunderte gleichzeitiger Remote Verbindungen verwalten.</span><span class="sxs-lookup"><span data-stu-id="25a92-179">PowerShell can manage hundreds of concurrent remote connections.</span></span> <span data-ttu-id="25a92-180">Die Anzahl der Remote Befehle, die Sie senden können, kann jedoch durch die Ressourcen Ihres Computers und seine Kapazität zum Einrichten und Verwalten mehrerer Netzwerkverbindungen eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="25a92-180">However, the number of remote commands that you can send might be limited by the resources of your computer and its capacity to establish and maintain multiple network connections.</span></span>

<span data-ttu-id="25a92-181">Weitere Informationen finden Sie im Beispiel des `Invoke-Command` Hilfe Themas.</span><span class="sxs-lookup"><span data-stu-id="25a92-181">For more information, see the example in the `Invoke-Command` Help topic.</span></span>

### <a name="where-are-my-profiles"></a><span data-ttu-id="25a92-182">Wo sind meine profile?</span><span class="sxs-lookup"><span data-stu-id="25a92-182">Where are my profiles?</span></span>

<span data-ttu-id="25a92-183">PowerShell-Profile werden nicht automatisch in Remote Sitzungen ausgeführt, sodass die Befehle, die das Profil hinzufügt, nicht in der Sitzung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="25a92-183">PowerShell profiles are not run automatically in remote sessions, so the commands that the profile adds are not present in the session.</span></span> <span data-ttu-id="25a92-184">Außerdem `$profile` wird die automatische Variable nicht in Remote Sitzungen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="25a92-184">In addition, the `$profile` automatic variable is not populated in remote sessions.</span></span>

<span data-ttu-id="25a92-185">Verwenden Sie das-Cmdlet, um ein Profil in einer Sitzung auszuführen `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="25a92-185">To run a profile in a session, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="25a92-186">Der folgende Befehl führt z. b. das Profil "currentuserhappthost" vom lokalen Computer in der Sitzung in aus `$s` .</span><span class="sxs-lookup"><span data-stu-id="25a92-186">For example, the following command runs the CurrentUserCurrentHost profile from the local computer in the session in `$s`.</span></span>

```
Invoke-Command -Session $s -FilePath $profile
```

<span data-ttu-id="25a92-187">Mit dem folgenden Befehl wird das Profil "currentusercomputhost" vom Remote Computer in der Sitzung in ausgeführt `$s` .</span><span class="sxs-lookup"><span data-stu-id="25a92-187">The following command runs the CurrentUserCurrentHost profile from the remote computer in the session in `$s`.</span></span> <span data-ttu-id="25a92-188">Da die `$profile` Variable nicht aufgefüllt wird, verwendet der Befehl den expliziten Pfad zum Profil.</span><span class="sxs-lookup"><span data-stu-id="25a92-188">Because the `$profile` variable is not populated, the command uses the explicit path to the profile.</span></span>

```powershell
Invoke-Command -Session $s {
  . "$home\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

<span data-ttu-id="25a92-189">Nachdem Sie diesen Befehl ausgeführt haben, sind die Befehle, die das Profil der Sitzung hinzufügt, in verfügbar `$s` .</span><span class="sxs-lookup"><span data-stu-id="25a92-189">After running this command, the commands that the profile adds to the session are available in `$s`.</span></span>

<span data-ttu-id="25a92-190">Sie können auch ein Startskript in einer Sitzungs Konfiguration verwenden, um ein Profil in jeder Remote Sitzung auszuführen, die die Sitzungs Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="25a92-190">You can also use a startup script in a session configuration to run a profile in every remote session that uses the session configuration.</span></span>

<span data-ttu-id="25a92-191">Weitere Informationen zu PowerShell-Profilen finden Sie unter about_Profiles.</span><span class="sxs-lookup"><span data-stu-id="25a92-191">For more information about PowerShell profiles, see about_Profiles.</span></span>
<span data-ttu-id="25a92-192">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="25a92-192">For more information about session configurations, see `Register-PSSessionConfiguration`.</span></span>

### <a name="how-does-throttling-work-on-remote-commands"></a><span data-ttu-id="25a92-193">Wie funktioniert die Drosselung bei Remote Befehlen?</span><span class="sxs-lookup"><span data-stu-id="25a92-193">How does throttling work on remote commands?</span></span>

<span data-ttu-id="25a92-194">Damit Sie die Ressourcen auf dem lokalen Computer verwalten können, umfasst PowerShell eine Einschränkung pro Befehl, mit der Sie die Anzahl der gleichzeitigen Remote Verbindungen begrenzen können, die für jeden Befehl eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="25a92-194">To help you manage the resources on your local computer, PowerShell includes a per-command throttling feature that lets you limit the number of concurrent remote connections that are established for each command.</span></span>

<span data-ttu-id="25a92-195">Der Standardwert ist 32 gleichzeitige Verbindungen, Sie können jedoch den **throttlelimit** -Parameter der Cmdlets verwenden, um eine benutzerdefinierte Drosselungs Grenze für bestimmte Befehle festzulegen.</span><span class="sxs-lookup"><span data-stu-id="25a92-195">The default is 32 concurrent connections, but you can use the **ThrottleLimit** parameter of the cmdlets to set a custom throttle limit for particular commands.</span></span>

<span data-ttu-id="25a92-196">Beachten Sie bei Verwendung der Drosselungs Funktion, dass Sie für jeden Befehl, nicht für die gesamte Sitzung oder den Computer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="25a92-196">When you use the throttling feature, remember that it is applied to each command, not to the entire session or to the computer.</span></span> <span data-ttu-id="25a92-197">Wenn Sie Befehle gleichzeitig in mehreren Sitzungen oder pssessions ausführen, entspricht die Anzahl gleichzeitiger Verbindungen der Summe der gleichzeitigen Verbindungen in allen Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="25a92-197">If you are running commands concurrently in several sessions or PSSessions, the number of concurrent connections is the sum of the concurrent connections in all the sessions.</span></span>

<span data-ttu-id="25a92-198">Um Cmdlets mit einem **throttlelimit** -Parameter zu suchen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="25a92-198">To find cmdlets with a **ThrottleLimit** parameter, type:</span></span>

```
Get-Help * -Parameter ThrottleLimit
-or-
Get-Command -ParameterName ThrottleLimit
```

### <a name="is-the-output-of-remote-commands-different-from-local-output"></a><span data-ttu-id="25a92-199">Unterscheiden sich die Ausgabe von Remote Befehlen von der lokalen Ausgabe?</span><span class="sxs-lookup"><span data-stu-id="25a92-199">Is the output of remote commands different from local output?</span></span>

<span data-ttu-id="25a92-200">Wenn Sie PowerShell lokal verwenden, senden und empfangen Sie "Live"-.NET Framework Objekte. "Live"-Objekte sind Objekte, die mit den eigentlichen Programmen oder Systemkomponenten verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="25a92-200">When you use PowerShell locally, you send and receive "live" .NET Framework objects; "live" objects are objects that are associated with actual programs or system components.</span></span> <span data-ttu-id="25a92-201">Wenn Sie die-Methoden aufrufen oder die Eigenschaften von Live-Objekten ändern, wirken sich die Änderungen auf das tatsächliche Programm oder die tatsächliche Komponente aus.</span><span class="sxs-lookup"><span data-stu-id="25a92-201">When you invoke the methods or change the properties of live objects, the changes affect the actual program or component.</span></span> <span data-ttu-id="25a92-202">Wenn sich die Eigenschaften eines Programms oder einer Komponente ändern, ändern sich auch die Eigenschaften des Objekts, die diese darstellen.</span><span class="sxs-lookup"><span data-stu-id="25a92-202">And, when the properties of a program or component change, the properties of the object that represent them also change.</span></span>

<span data-ttu-id="25a92-203">Da die meisten Live Objekte jedoch nicht über das Netzwerk übertragen werden können, serialisiert PowerShell die meisten Objekte, die in Remote Befehlen gesendet werden, d. h., Sie konvertiert jedes Objekt in eine Reihe von XML-Datenelementen (Einschränkungs Sprache in XML [CliXML]) für die Übertragung.</span><span class="sxs-lookup"><span data-stu-id="25a92-203">However, because most live objects cannot be transmitted over the network, PowerShell "serializes" most of the objects sent in remote commands, that is, it converts each object into a series of XML (Constraint Language in XML [CLiXML]) data elements for transmission.</span></span>

<span data-ttu-id="25a92-204">Wenn PowerShell ein serialisiertes Objekt empfängt, wird der XML-Code in einen deserialisierten Objekttyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="25a92-204">When PowerShell receives a serialized object, it converts the XML into a deserialized object type.</span></span> <span data-ttu-id="25a92-205">Das deserialisierte Objekt ist ein genauer Datensatz der Eigenschaften des Programms oder der Komponente zu einem früheren Zeitpunkt, aber es ist nicht mehr "Live", d. h., es ist nicht mehr direkt der Komponente zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="25a92-205">The deserialized object is an accurate record of the properties of the program or component at a previous time, but it is no longer "live", that is, it is no longer directly associated with the component.</span></span> <span data-ttu-id="25a92-206">Und die Methoden werden entfernt, da Sie nicht mehr gültig sind.</span><span class="sxs-lookup"><span data-stu-id="25a92-206">And, the methods are removed because they are no longer effective.</span></span>

<span data-ttu-id="25a92-207">In der Regel können Sie deserialisierte Objekte genauso wie Live-Objekte verwenden, aber Sie müssen sich mit ihren Einschränkungen vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="25a92-207">Typically, you can use deserialized objects just as you would use live objects, but you must be aware of their limitations.</span></span> <span data-ttu-id="25a92-208">Außerdem verfügen die Objekte, die vom Cmdlet zurückgegeben werden, `Invoke-Command` über zusätzliche Eigenschaften, die Ihnen helfen, den Ursprung des Befehls zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="25a92-208">Also, the objects that are returned by the `Invoke-Command` cmdlet have additional properties that help you to determine the origin of the command.</span></span>

<span data-ttu-id="25a92-209">Einige Objekttypen, z. b. DirectoryInfo-Objekte und GUIDs, werden wieder in Live Objekte konvertiert, wenn Sie empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="25a92-209">Some object types, such as DirectoryInfo objects and GUIDs, are converted back into live objects when they are received.</span></span> <span data-ttu-id="25a92-210">Diese Objekte benötigen keine besondere Behandlung oder Formatierung.</span><span class="sxs-lookup"><span data-stu-id="25a92-210">These objects do not need any special handling or formatting.</span></span>

<span data-ttu-id="25a92-211">Weitere Informationen zum Interpretieren und Formatieren der Remote Ausgabe finden Sie unter [about_Remote_Output](about_Remote_Output.md).</span><span class="sxs-lookup"><span data-stu-id="25a92-211">For information about interpreting and formatting remote output, see [about_Remote_Output](about_Remote_Output.md).</span></span>

### <a name="can-i-run-background-jobs-remotely"></a><span data-ttu-id="25a92-212">Kann ich Hintergrund Aufträge Remote ausführen?</span><span class="sxs-lookup"><span data-stu-id="25a92-212">Can I run background jobs remotely?</span></span>

<span data-ttu-id="25a92-213">Ja.</span><span class="sxs-lookup"><span data-stu-id="25a92-213">Yes.</span></span> <span data-ttu-id="25a92-214">Ein PowerShell-Hintergrund Auftrag ist ein PowerShell-Befehl, der asynchron ausgeführt wird, ohne mit der Sitzung zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="25a92-214">A PowerShell background job is a PowerShell command that runs asynchronously without interacting with the session.</span></span> <span data-ttu-id="25a92-215">Wenn Sie einen Hintergrund Auftrag starten, wird die Eingabeaufforderung sofort zurückgegeben, und Sie können die Arbeit in der Sitzung fortsetzen, während der Auftrag ausgeführt wird, auch wenn er über einen längeren Zeitraum ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="25a92-215">When you start a background job, the command prompt returns immediately, and you can continue to work in the session while the job runs even if it runs for an extended period of time.</span></span>

<span data-ttu-id="25a92-216">Sie können einen Hintergrund Auftrag auch dann starten, wenn andere Befehle ausgeführt werden, da Hintergrund Aufträge in einer temporären Sitzung immer asynchron ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="25a92-216">You can start a background job even while other commands are running because background jobs always run asynchronously in a temporary session.</span></span>

<span data-ttu-id="25a92-217">Hintergrund Aufträge können auf einem lokalen Computer oder einem Remote Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="25a92-217">You can run background jobs on a local or remote computer.</span></span> <span data-ttu-id="25a92-218">Standardmäßig wird ein Hintergrund Auftrag auf dem lokalen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="25a92-218">By default, a background job runs on the local computer.</span></span> <span data-ttu-id="25a92-219">Sie können jedoch den **AsJob** -Parameter des `Invoke-Command` Cmdlets verwenden, um einen beliebigen Remote Befehl als Hintergrund Auftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="25a92-219">However, you can use the **AsJob** parameter of the `Invoke-Command` cmdlet to run any remote command as a background job.</span></span> <span data-ttu-id="25a92-220">Und Sie können verwenden, `Invoke-Command` um einen `Start-Job` Befehl Remote auszuführen.</span><span class="sxs-lookup"><span data-stu-id="25a92-220">And, you can use `Invoke-Command` to run a `Start-Job` command remotely.</span></span>

<span data-ttu-id="25a92-221">Weitere Informationen zu Hintergrund Aufträgen in PowerShell finden Sie unter [about_Jobs (about_Jobs. MD)] und [about_Remote_Jobs (about_Remote_Jobs. MD)].</span><span class="sxs-lookup"><span data-stu-id="25a92-221">For more information about background jobs in PowerShell , see [about_Jobs(about_Jobs.md)] and [about_Remote_Jobs(about_Remote_Jobs.md)].</span></span>

### <a name="can-i-run-windows-programs-on-a-remote-computer"></a><span data-ttu-id="25a92-222">Kann ich Windows-Programme auf einem Remote Computer ausführen?</span><span class="sxs-lookup"><span data-stu-id="25a92-222">Can I run windows programs on a remote computer?</span></span>

<span data-ttu-id="25a92-223">Mit PowerShell-Remote Befehlen können Sie Windows-basierte Programme auf Remote Computern ausführen.</span><span class="sxs-lookup"><span data-stu-id="25a92-223">You can use PowerShell remote commands to run Windows-based programs on remote computers.</span></span> <span data-ttu-id="25a92-224">Beispielsweise können Sie `Shutdown.exe` oder `Ipconfig.exe` auf einem Remote Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="25a92-224">For example, you can run `Shutdown.exe` or `Ipconfig.exe` on a remote computer.</span></span>

<span data-ttu-id="25a92-225">Sie können jedoch keine PowerShell-Befehle verwenden, um die Benutzeroberfläche für ein beliebiges Programm auf einem Remote Computer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="25a92-225">However, you cannot use PowerShell commands to open the user interface for any program on a remote computer.</span></span>

<span data-ttu-id="25a92-226">Wenn Sie ein Windows-Programm auf einem Remote Computer starten, wird der Befehl nicht abgeschlossen, und die PowerShell-Eingabeaufforderung wird erst zurückgegeben, wenn das Programm abgeschlossen ist oder Sie <kbd>STRG</kbd> + <kbd>C</kbd> drücken, um den Befehl zu unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="25a92-226">When you start a Windows program on a remote computer, the command is not completed, and the PowerShell command prompt does not return, until the program is finished or until you press <kbd>CTRL</kbd>+<kbd>C</kbd> to interrupt the command.</span></span> <span data-ttu-id="25a92-227">Wenn Sie das Programm z. b `Ipconfig.exe` . auf einem Remote Computer ausführen, wird die Eingabeaufforderung nicht zurückgegeben, bis `Ipconfig.exe` abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="25a92-227">For example, if you run the `Ipconfig.exe` program on a remote computer, the command prompt does not return until `Ipconfig.exe` is completed.</span></span>

<span data-ttu-id="25a92-228">Wenn Sie Remote Befehle verwenden, um ein Programm zu starten, das über eine Benutzeroberfläche verfügt, wird der Programmprozess gestartet, aber die Benutzeroberfläche wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25a92-228">If you use remote commands to start a program that has a user interface, the program process starts, but the user interface does not appear.</span></span> <span data-ttu-id="25a92-229">Der PowerShell-Befehl wird nicht abgeschlossen, und die Eingabeaufforderung wird erst zurückgegeben, wenn Sie den Programmprozess beenden oder <kbd>STRG</kbd> + <kbd>C</kbd>drücken, wodurch der Befehl unterbrochen und der Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="25a92-229">The PowerShell command is not completed, and the command prompt does not return until you stop the program process or until you press <kbd>CTRL</kbd>+<kbd>C</kbd>, which interrupts the command and stops the process.</span></span>

<span data-ttu-id="25a92-230">Wenn Sie z. b. einen PowerShell-Befehl verwenden, um `Notepad` auf einem Remote Computer auszuführen, wird der Notepad-Prozess auf dem Remote Computer gestartet, aber die Benutzeroberfläche des Notepad wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25a92-230">For example, if you use a PowerShell command to run `Notepad` on a remote computer, the Notepad process starts on the remote computer, but the Notepad user interface does not appear.</span></span> <span data-ttu-id="25a92-231">Drücken Sie <kbd>STRG</kbd>C, um den Befehl zu unterbrechen und die Eingabeaufforderung wiederherzustellen + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="25a92-231">To interrupt the command and restore the command prompt, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

### <a name="can-i-limit-the-commands-that-users-can-run-remotely-on-my-computer"></a><span data-ttu-id="25a92-232">Kann ich die Befehle einschränken, die Benutzer Remote auf dem Computer ausführen können?</span><span class="sxs-lookup"><span data-stu-id="25a92-232">Can I limit the commands that users can run remotely on my computer?</span></span>

<span data-ttu-id="25a92-233">Ja.</span><span class="sxs-lookup"><span data-stu-id="25a92-233">Yes.</span></span> <span data-ttu-id="25a92-234">Jede Remote Sitzung muss eine der Sitzungs Konfigurationen auf dem Remote Computer verwenden.</span><span class="sxs-lookup"><span data-stu-id="25a92-234">Every remote session must use one of the session configurations on the remote computer.</span></span> <span data-ttu-id="25a92-235">Sie können die Sitzungs Konfigurationen auf dem Computer (und die Berechtigungen für diese Sitzungs Konfigurationen) verwalten, um zu bestimmen, wer Befehle Remote auf dem Computer ausführen und welche Befehle ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="25a92-235">You can manage the session configurations on your computer (and the permissions to those session configurations) to determine who can run commands remotely on your computer and which commands they can run.</span></span>

<span data-ttu-id="25a92-236">Eine Sitzungs Konfiguration konfiguriert die Umgebung für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="25a92-236">A session configuration configures the environment for the session.</span></span> <span data-ttu-id="25a92-237">Sie können die Konfiguration mithilfe einer Assembly definieren, die eine neue Konfigurations Klasse implementiert, oder mithilfe eines Skripts, das in der Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="25a92-237">You can define the configuration by using an assembly that implements a new configuration class or by using a script that runs in the session.</span></span> <span data-ttu-id="25a92-238">Die Konfiguration kann die Befehle ermitteln, die in der Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="25a92-238">The configuration can determine the commands that are available in the session.</span></span>
<span data-ttu-id="25a92-239">Und die Konfiguration kann Einstellungen enthalten, die den Computer schützen, z. b. Einstellungen, die die Datenmenge beschränken, die von der Sitzung Remote in einem einzigen Objekt oder Befehl empfangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="25a92-239">And, the configuration can include settings that protect the computer, such as settings that limit the amount of data that the session can receive remotely in a single object or command.</span></span> <span data-ttu-id="25a92-240">Sie können auch eine Sicherheits Beschreibung angeben, die die Berechtigungen bestimmt, die für die Verwendung der Konfiguration erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="25a92-240">You can also specify a security descriptor that determines the permissions that are required to use the configuration.</span></span>

<span data-ttu-id="25a92-241">`Enable-PSRemoting`Mit dem-Cmdlet werden die Standard Sitzungs Konfigurationen auf dem Computer erstellt: Microsoft. PowerShell, Microsoft. PowerShell. Workflow und Microsoft. PowerShell32 (nur 64-Bit-Betriebssysteme).</span><span class="sxs-lookup"><span data-stu-id="25a92-241">The `Enable-PSRemoting` cmdlet creates the default session configurations on your computer: Microsoft.PowerShell, Microsoft.PowerShell.Workflow, and Microsoft.PowerShell32 (64-bit operating systems only).</span></span> <span data-ttu-id="25a92-242">`Enable-PSRemoting` legt die Sicherheits Beschreibung für die Konfiguration fest, damit nur Mitglieder der Gruppe "Administratoren" auf dem Computer diese verwenden können.</span><span class="sxs-lookup"><span data-stu-id="25a92-242">`Enable-PSRemoting` sets the security descriptor for the configuration to allow only members of the Administrators group on your computer to use them.</span></span>

<span data-ttu-id="25a92-243">Sie können die Sitzungs konfigurationscmdlets verwenden, um die Standard Sitzungs Konfigurationen zu bearbeiten, neue Sitzungs Konfigurationen zu erstellen und die Sicherheits Beschreibungen aller Sitzungs Konfigurationen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="25a92-243">You can use the session configuration cmdlets to edit the default session configurations, to create new session configurations, and to change the security descriptors of all the session configurations.</span></span>

<span data-ttu-id="25a92-244">Ab Windows PowerShell 3,0 `New-PSSessionConfigurationFile` können Sie mit dem Cmdlet benutzerdefinierte Sitzungs Konfigurationen erstellen, indem Sie eine Textdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="25a92-244">Beginning in Windows PowerShell 3.0, the `New-PSSessionConfigurationFile` cmdlet lets you create custom session configurations by using a text file.</span></span> <span data-ttu-id="25a92-245">Die Datei enthält Optionen zum Festlegen des Sprachmodus und zum Angeben der Cmdlets und Module, die in Sitzungen verfügbar sind, die die Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="25a92-245">The file includes options for setting the language mode and for specifying the cmdlets and modules that are available in sessions that use the session configuration.</span></span>

<span data-ttu-id="25a92-246">Wenn Benutzer die `Invoke-Command` `New-PSSession` `Enter-PSSession` Cmdlets, oder verwenden, können Sie den **ConfigurationName** -Parameter verwenden, um die Sitzungs Konfiguration anzugeben, die für die Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25a92-246">When users use the `Invoke-Command`, `New-PSSession`, or `Enter-PSSession` cmdlets, they can use the **ConfigurationName** parameter to indicate the session configuration that is used for the session.</span></span> <span data-ttu-id="25a92-247">Außerdem können Sie die Standardkonfiguration ändern, die von ihren Sitzungen verwendet wird, indem Sie den Wert der `$PSSessionConfigurationName` Preference-Variablen in der Sitzung ändern.</span><span class="sxs-lookup"><span data-stu-id="25a92-247">And, they can change the default configuration that their sessions use by changing the value of the `$PSSessionConfigurationName` preference variable in the session.</span></span>

<span data-ttu-id="25a92-248">Weitere Informationen zu Sitzungs Konfigurationen finden Sie in der Hilfe zu den Cmdlets für die Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="25a92-248">For more information about session configurations, see the Help for the session configuration cmdlets.</span></span> <span data-ttu-id="25a92-249">Um die Sitzungs Konfigurations-Cmdlets zu finden, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="25a92-249">To find the session configuration cmdlets, type:</span></span>

```powershell
Get-Command *PSSessionConfiguration
```

### <a name="what-are-fan-in-and-fan-out-configurations"></a><span data-ttu-id="25a92-250">Was sind Lüfter-in-und Lüfter-Konfigurationen?</span><span class="sxs-lookup"><span data-stu-id="25a92-250">What are fan in and fan out configurations?</span></span>

<span data-ttu-id="25a92-251">Das häufigste PowerShell-Remotingszenario mit mehreren Computern ist die 1: n-Konfiguration, bei der auf einem lokalen Computer (dem Computer des Administrators) PowerShell-Befehle auf zahlreichen Remote Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="25a92-251">The most common PowerShell remoting scenario involving multiple computers is the one-to-many configuration, in which one local computer (the administrator's computer) runs PowerShell commands on numerous remote computers.</span></span> <span data-ttu-id="25a92-252">Dies wird als "Fan-Out"-Szenario bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="25a92-252">This is known as the "fan-out" scenario.</span></span>

<span data-ttu-id="25a92-253">In einigen Unternehmen ist die Konfiguration jedoch eine n:1-Konfiguration, bei der viele Client Computer eine Verbindung mit einem einzelnen Remote Computer herstellen, auf dem PowerShell ausgeführt wird (z. b. ein Dateiserver oder ein Kiosk).</span><span class="sxs-lookup"><span data-stu-id="25a92-253">However, in some enterprises, the configuration is many-to-one, where many client computers connect to a single remote computer that is running PowerShell, such as a file server or a kiosk.</span></span> <span data-ttu-id="25a92-254">Dies wird als "Lüfter"-Konfiguration bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="25a92-254">This is known as the "fan-in" configuration.</span></span>

<span data-ttu-id="25a92-255">PowerShell-Remoting unterstützt sowohl lüfterout-als auch Lüfter-Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="25a92-255">PowerShell remoting supports both fan-out and fan-in configurations.</span></span>

<span data-ttu-id="25a92-256">Für die lüfterout-Konfiguration verwendet PowerShell das Web Services for Management (WS-Management)-Protokoll und den WinRM-Dienst, der die Microsoft-Implementierung von WS-Management unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25a92-256">For the fan-out configuration, PowerShell uses the Web Services for Management (WS-Management) protocol and the WinRM service that supports the Microsoft implementation of WS-Management.</span></span> <span data-ttu-id="25a92-257">Wenn ein lokaler Computer eine Verbindung mit einem Remote Computer herstellt, stellt WS-Management eine Verbindung her und verwendet ein Plug-in für PowerShell, um den PowerShell-Host Prozess (Wsmprovhost.exe) auf dem Remote Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="25a92-257">When a local computer connects to a remote computer, WS-Management establishes a connection and uses a plug-in for PowerShell to start the PowerShell host process (Wsmprovhost.exe) on the remote computer.</span></span> <span data-ttu-id="25a92-258">Der Benutzer kann einen alternativen Port, eine Alternative Sitzungs Konfiguration und andere Features angeben, um die Remote Verbindung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="25a92-258">The user can specify an alternate port, an alternate session configuration, and other features to customize the remote connection.</span></span>

<span data-ttu-id="25a92-259">Zur Unterstützung der "Lüfter"-Konfiguration verwendet PowerShell Internetinformationsdienste (IIS), um die WS-Verwaltung zu hosten, das PowerShell-Plug-in zu laden und PowerShell zu starten.</span><span class="sxs-lookup"><span data-stu-id="25a92-259">To support the "fan-in" configuration, PowerShell uses internet Information Services (IIS) to host WS-Management, to load the PowerShell plug-in, and to start PowerShell.</span></span> <span data-ttu-id="25a92-260">In diesem Szenario werden alle PowerShell-Sitzungen in demselben Host Prozess ausgeführt, anstatt jede PowerShell-Sitzung in einem separaten Prozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="25a92-260">In this scenario, instead of starting each PowerShell session in a separate process, all PowerShell sessions run in the same host process.</span></span>

<span data-ttu-id="25a92-261">Das IIS-Hosting und die Lüfter-in-Remote Verwaltung werden in Windows XP oder Windows Server 2003 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25a92-261">IIS hosting and fan-in remote management is not supported in Windows XP or in Windows Server 2003.</span></span>

<span data-ttu-id="25a92-262">In einer Fan-in-Konfiguration kann der Benutzer einen Verbindungs-URI und einen HTTP-Endpunkt angeben, einschließlich Transport, Computername, Port und Anwendungsname.</span><span class="sxs-lookup"><span data-stu-id="25a92-262">In a fan-in configuration, the user can specify a connection URI and an HTTP endpoint, including the transport, computer name, port, and application name.</span></span>
<span data-ttu-id="25a92-263">IIS leitet alle Anforderungen mit einem angegebenen Anwendungsnamen an die Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="25a92-263">IIS forwards all the requests with a specified application name to the application.</span></span> <span data-ttu-id="25a92-264">Der Standardwert ist WS-Management, der PowerShell hosten kann.</span><span class="sxs-lookup"><span data-stu-id="25a92-264">The default is WS-Management, which can host PowerShell.</span></span>

<span data-ttu-id="25a92-265">Sie können auch einen Authentifizierungsmechanismus angeben und die Umleitung von http-und HTTPS-Endpunkten zulassen oder zulassen.</span><span class="sxs-lookup"><span data-stu-id="25a92-265">You can also specify an authentication mechanism and prohibit or allow redirection from HTTP and HTTPS endpoints.</span></span>

### <a name="can-i-test-remoting-on-a-single-computer-not-in-a-domain"></a><span data-ttu-id="25a92-266">Kann ich das Remoting auf einem einzelnen Computer testen, der sich nicht in einer Domäne befindet?</span><span class="sxs-lookup"><span data-stu-id="25a92-266">Can I test remoting on a single computer not in a domain?</span></span>

<span data-ttu-id="25a92-267">Ja.</span><span class="sxs-lookup"><span data-stu-id="25a92-267">Yes.</span></span> <span data-ttu-id="25a92-268">PowerShell-Remoting ist auch dann verfügbar, wenn sich der lokale Computer nicht in einer Domäne befindet.</span><span class="sxs-lookup"><span data-stu-id="25a92-268">PowerShell remoting is available even when the local computer is not in a domain.</span></span> <span data-ttu-id="25a92-269">Sie können die Remoting-Features verwenden, um eine Verbindung mit Sitzungen herzustellen und Sitzungen auf demselben Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="25a92-269">You can use the remoting features to connect to sessions and to create sessions on the same computer.</span></span> <span data-ttu-id="25a92-270">Die Funktionen funktionieren genauso wie beim Herstellen einer Verbindung mit einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="25a92-270">The features work the same as they do when you connect to a remote computer.</span></span>

<span data-ttu-id="25a92-271">Um Remote Befehle auf einem Computer in einer Arbeitsgruppe auszuführen, ändern Sie die folgenden Windows-Einstellungen auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="25a92-271">To run remote commands on a computer in a workgroup, change the following Windows settings on the computer.</span></span>

<span data-ttu-id="25a92-272">Vorsicht: Diese Einstellungen wirken sich auf alle Benutzer im System aus, und Sie können das System anfällig für böswillige Angriffe machen.</span><span class="sxs-lookup"><span data-stu-id="25a92-272">Caution: These settings affect all users on the system and they can make the system more vulnerable to a malicious attack.</span></span> <span data-ttu-id="25a92-273">Gehen Sie vorsichtig vor, wenn Sie diese Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="25a92-273">Use caution when making these changes.</span></span>

- <span data-ttu-id="25a92-274">Windows Vista, Windows 7, Windows 8:</span><span class="sxs-lookup"><span data-stu-id="25a92-274">Windows Vista, Windows 7, Windows 8:</span></span>

  <span data-ttu-id="25a92-275">Erstellen Sie den folgenden Registrierungs Eintrag, und legen Sie seinen Wert auf 1 fest: localaccountbukenfilterpolicy in ` HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`</span><span class="sxs-lookup"><span data-stu-id="25a92-275">Create the following registry entry, and then set its value to 1: LocalAccountTokenFilterPolicy in ` HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`</span></span>

  <span data-ttu-id="25a92-276">Zum Hinzufügen dieses Eintrags können Sie den folgenden PowerShell-Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="25a92-276">You can use the following PowerShell command to add this entry:</span></span>

    ```powershell
    $parameters = @{
      Path='HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System'
      Name='LocalAccountTokenFilterPolicy'
      propertyType='DWord'
      Value=1
    }
    New-ItemProperty @parameters
    ```

- <span data-ttu-id="25a92-277">Windows Server 2003, Windows Server 2008, Windows Server 2012, Windows Server 2012 R2:</span><span class="sxs-lookup"><span data-stu-id="25a92-277">Windows Server 2003, Windows Server 2008, Windows Server 2012, Windows Server 2012 R2:</span></span>

  <span data-ttu-id="25a92-278">Es sind keine Änderungen erforderlich, da die Standardeinstellung für die Richtlinie "Netzwerk Zugriff: Modell für gemeinsame Nutzung und Sicherheitsmodell für lokale Konten" "klassisch" lautet.</span><span class="sxs-lookup"><span data-stu-id="25a92-278">No changes are needed because the default setting of the "Network Access: Sharing and security model for local accounts" policy is "Classic".</span></span> <span data-ttu-id="25a92-279">Überprüfen Sie die Einstellung für den Fall, dass Sie geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="25a92-279">Verify the setting in case it has changed.</span></span>

### <a name="can-i-run-remote-commands-on-a-computer-in-another-domain"></a><span data-ttu-id="25a92-280">Kann ich Remote Befehle auf einem Computer in einer anderen Domäne ausführen?</span><span class="sxs-lookup"><span data-stu-id="25a92-280">Can I run remote commands on a computer in another domain?</span></span>

<span data-ttu-id="25a92-281">Ja.</span><span class="sxs-lookup"><span data-stu-id="25a92-281">Yes.</span></span> <span data-ttu-id="25a92-282">In der Regel werden die Befehle ohne Fehler ausgeführt, aber Sie müssen möglicherweise den **Credential** -Parameter der- `Invoke-Command` ,-oder- `New-PSSession` `Enter-PSSession` Cmdlets verwenden, um die Anmelde Informationen eines Mitglieds der Gruppe "Administratoren" auf dem Remote Computer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="25a92-282">Typically, the commands run without error, although you might need to use the **Credential** parameter of the `Invoke-Command`, `New-PSSession`, or `Enter-PSSession` cmdlets to provide the credentials of a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="25a92-283">Dies ist auch dann erforderlich, wenn der aktuelle Benutzer ein Mitglied der Gruppe "Administratoren" auf dem lokalen Computer und dem Remote Computer ist.</span><span class="sxs-lookup"><span data-stu-id="25a92-283">This is sometimes required even when the current user is a member of the Administrators group on the local and remote computers.</span></span>

<span data-ttu-id="25a92-284">Wenn sich der Remote Computer jedoch nicht in einer Domäne befindet, der der lokale Computer vertraut, ist der Remote Computer möglicherweise nicht in der Lage, die Anmelde Informationen des Benutzers zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="25a92-284">However, if the remote computer is not in a domain that the local computer trusts, the remote computer might not be able to authenticate the user's credentials.</span></span>

<span data-ttu-id="25a92-285">Verwenden Sie zum Aktivieren der Authentifizierung den folgenden Befehl, um den Remote Computer der Liste der vertrauenswürdigen Hosts für den lokalen Computer in WinRM hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="25a92-285">To enable authentication, use the following command to add the remote computer to the list of trusted hosts for the local computer in WinRM.</span></span> <span data-ttu-id="25a92-286">Geben Sie den Befehl an der PowerShell-Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="25a92-286">Type the command at the PowerShell prompt.</span></span>

```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value <Remote-computer-name>
```

<span data-ttu-id="25a92-287">Um z. b. den Server01-Computer der Liste der vertrauenswürdigen Hosts auf dem lokalen Computer hinzuzufügen, geben Sie an der PowerShell-Eingabeaufforderung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="25a92-287">For example, to add the Server01 computer to the list of trusted hosts on the local computer, type the following command at the PowerShell prompt:</span></span>

```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value Server01
```

### <a name="does-powershell-support-remoting-over-ssh"></a><span data-ttu-id="25a92-288">Unterstützt PowerShell Remoting über SSH?</span><span class="sxs-lookup"><span data-stu-id="25a92-288">Does PowerShell support remoting over SSH?</span></span>

<span data-ttu-id="25a92-289">Ja.</span><span class="sxs-lookup"><span data-stu-id="25a92-289">Yes.</span></span> <span data-ttu-id="25a92-290">Weitere Informationen finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="25a92-290">For more information, see [PowerShell remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <a name="see-also"></a><span data-ttu-id="25a92-291">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="25a92-291">See also</span></span>

[<span data-ttu-id="25a92-292">about_Remote</span><span class="sxs-lookup"><span data-stu-id="25a92-292">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="25a92-293">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="25a92-293">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="25a92-294">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="25a92-294">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="25a92-295">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="25a92-295">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)

[<span data-ttu-id="25a92-296">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="25a92-296">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="25a92-297">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="25a92-297">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="25a92-298">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="25a92-298">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
