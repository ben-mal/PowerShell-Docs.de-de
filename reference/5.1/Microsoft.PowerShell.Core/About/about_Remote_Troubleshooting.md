---
description: Beschreibt die Problembehandlung bei Remote Vorgängen in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Troubleshooting
ms.openlocfilehash: 33661392583393b69723449a914ace84f394fc94
ms.sourcegitcommit: c1e4739f5d52282fb05a8cff92b0f5d10e2edac1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2020
ms.locfileid: "93225284"
---
# <a name="about-remote-troubleshooting"></a><span data-ttu-id="96532-104">Informationen zur Remote Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="96532-104">About Remote Troubleshooting</span></span>

## <a name="short-description"></a><span data-ttu-id="96532-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96532-105">Short description</span></span>
<span data-ttu-id="96532-106">Beschreibt die Problembehandlung bei Remote Vorgängen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96532-106">Describes how to troubleshoot remote operations in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="96532-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96532-107">Long description</span></span>

<span data-ttu-id="96532-108">In diesem Abschnitt werden einige der Probleme beschrieben, die auftreten können, wenn Sie die Remoting-Features von PowerShell verwenden, die auf WS-Management Technologie basieren, und Lösungen für diese Probleme vorschlägt.</span><span class="sxs-lookup"><span data-stu-id="96532-108">This section describes some of the problems that you might encounter when using the remoting features of PowerShell that are based on WS-Management technology and it suggests solutions to these problems.</span></span>

<span data-ttu-id="96532-109">Vor der Verwendung von PowerShell-Remoting finden Sie unter [about_Remote](about_remote.md) und [about_Remote_Requirements](about_Remote_Requirements.md) Anleitungen zur Konfiguration und grundlegenden Verwendung.</span><span class="sxs-lookup"><span data-stu-id="96532-109">Before using PowerShell remoting, see [about_Remote](about_remote.md) and [about_Remote_Requirements](about_Remote_Requirements.md) for guidance on configuration and basic use.</span></span> <span data-ttu-id="96532-110">Außerdem verfügen die Hilfe Themen für die einzelnen Remoting-Cmdlets, insbesondere die Parameter Beschreibungen, über nützliche Informationen, die Ihnen helfen sollen, Probleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="96532-110">Also, the Help topics for each of the remoting cmdlets, particularly the parameter descriptions, have useful information that is designed to help you avoid problems.</span></span>

> [!NOTE]
> <span data-ttu-id="96532-111">Starten Sie PowerShell mit der Option **als Administrator ausführen** , um Einstellungen für den lokalen Computer im WSMAN:-Laufwerk anzuzeigen oder zu ändern, einschließlich Änderungen an den Sitzungs Konfigurationen, vertrauenswürdigen Hosts, Ports oder Listenern.</span><span class="sxs-lookup"><span data-stu-id="96532-111">To view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start PowerShell with the **Run as administrator** option.</span></span>

## <a name="troubleshooting-permission-and-authentication-issues"></a><span data-ttu-id="96532-112">Problembehandlung bei Berechtigungen und Authentifizierungs Problemen</span><span class="sxs-lookup"><span data-stu-id="96532-112">Troubleshooting permission and authentication issues</span></span>

<span data-ttu-id="96532-113">In diesem Abschnitt werden remotingprobleme im Zusammenhang mit Benutzer-und Computer Berechtigungen und Remote Anforderungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="96532-113">This section discusses remoting problems that are related to user and computer permissions and remoting requirements.</span></span>

### <a name="how-to-run-as-administrator"></a><span data-ttu-id="96532-114">Vorgehensweise beim Ausführen als Administrator</span><span class="sxs-lookup"><span data-stu-id="96532-114">How to run as administrator</span></span>

```
ERROR: Access is denied. You need to run this cmdlet from an elevated
process.
```

<span data-ttu-id="96532-115">Starten Sie Windows PowerShell mit der Option **als Administrator ausführen** , um eine Remote Sitzung auf dem lokalen Computer zu starten oder Einstellungen für den lokalen Computer im WSMAN:-Laufwerk anzuzeigen oder zu ändern, einschließlich Änderungen an den Sitzungs Konfigurationen, vertrauenswürdigen Hosts, Ports oder Listenern.</span><span class="sxs-lookup"><span data-stu-id="96532-115">To start a remote session on the local computer, or to view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start Windows PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="96532-116">So starten Sie Windows PowerShell mit der Option **als Administrator ausführen** :</span><span class="sxs-lookup"><span data-stu-id="96532-116">To start Windows PowerShell with the **Run as administrator** option:</span></span>

- <span data-ttu-id="96532-117">Klicken Sie mit der rechten Maustaste auf ein Windows PowerShell-Symbol (oder Windows PowerShell ISE), und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="96532-117">Right-click a Windows PowerShell (or Windows PowerShell ISE) icon and then click **Run as administrator**.</span></span>

  <span data-ttu-id="96532-118">Zum Starten von Windows PowerShell mit der Option **als Administrator ausführen** in Windows 7 und Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="96532-118">To start Windows PowerShell with the **Run as administrator** option in Windows 7 and Windows Server 2008 R2.</span></span>

- <span data-ttu-id="96532-119">Klicken Sie in der Windows-Taskleiste mit der rechten Maustaste auf das Windows PowerShell-Symbol, und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="96532-119">In the Windows taskbar, right-click the Windows PowerShell icon, and then click **Run as administrator**.</span></span>

  <span data-ttu-id="96532-120">In Windows Server 2008 R2 wird das Windows PowerShell-Symbol standardmäßig an die Taskleiste angeheftet.</span><span class="sxs-lookup"><span data-stu-id="96532-120">In Windows Server 2008 R2, the Windows PowerShell icon is pinned to the taskbar by default.</span></span>

### <a name="how-to-enable-remoting"></a><span data-ttu-id="96532-121">Aktivieren von Remoting</span><span class="sxs-lookup"><span data-stu-id="96532-121">How to enable remoting</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to
listen for requests on the correct port and HTTP URL.
```

<span data-ttu-id="96532-122">Es ist keine Konfiguration erforderlich, um es einem Computer zu ermöglichen, Remote Befehle zu senden.</span><span class="sxs-lookup"><span data-stu-id="96532-122">No configuration is required to enable a computer to send remote commands.</span></span>
<span data-ttu-id="96532-123">Zum Empfangen von Remote Befehlen muss jedoch PowerShell-Remoting auf dem Computer aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="96532-123">However, to receive remote commands, PowerShell remoting must be enabled on the computer.</span></span> <span data-ttu-id="96532-124">Aktivieren von umfasst das Starten des WinRM-Dienst, das Festlegen des Starttyps für den WinRM-Dienst auf automatisch, das Erstellen von Listenern für http-und HTTPS-Verbindungen und das Erstellen von</span><span class="sxs-lookup"><span data-stu-id="96532-124">Enabling includes starting the WinRM service, setting the startup type for the WinRM service to Automatic, creating listeners for HTTP and HTTPS connections, and creating default session configurations.</span></span>

<span data-ttu-id="96532-125">Windows PowerShell-Remoting ist unter Windows Server 2012 und neueren Versionen von Windows Server standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="96532-125">Windows PowerShell remoting is enabled on Windows Server 2012 and newer releases of Windows Server by default.</span></span> <span data-ttu-id="96532-126">Führen Sie auf allen anderen Systemen das- `Enable-PSRemoting` Cmdlet aus, um Remoting zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="96532-126">On all other systems, run the `Enable-PSRemoting` cmdlet to enable remoting.</span></span> <span data-ttu-id="96532-127">Sie können das `Enable-PSRemoting` Cmdlet auch zum erneuten Aktivieren von Remoting unter Windows Server 2012 und neueren Versionen von Windows Server ausführen, wenn Remoting deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="96532-127">You can also run the `Enable-PSRemoting` cmdlet to re-enable remoting on Windows Server 2012 and newer releases of Windows Server if remoting is disabled.</span></span>

<span data-ttu-id="96532-128">Verwenden Sie das-Cmdlet, um einen Computer für den Empfang von Remote Befehlen zu konfigurieren `Enable-PSRemoting` .</span><span class="sxs-lookup"><span data-stu-id="96532-128">To configure a computer to receive remote commands, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="96532-129">Der folgende Befehl aktiviert alle erforderlichen Remote Einstellungen, aktiviert die Sitzungs Konfigurationen und startet den WinRM-Dienst neu, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="96532-129">The following command enables all required remote settings, enables the session configurations, and restarts the WinRM service to make the changes effective.</span></span>

`Enable-PSRemoting`

<span data-ttu-id="96532-130">Um alle Eingabe Aufforderungen zu unterdrücken, geben Sie ein</span><span class="sxs-lookup"><span data-stu-id="96532-130">To suppress all user prompts, type:</span></span>

`Enable-PSRemoting -Force`

<span data-ttu-id="96532-131">Weitere Informationen finden Sie unter [enable-psremoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).</span><span class="sxs-lookup"><span data-stu-id="96532-131">For more information, see [Enable-PSRemoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).</span></span>

### <a name="how-to-enable-remoting-in-an-enterprise"></a><span data-ttu-id="96532-132">Aktivieren von Remoting in einem Unternehmen</span><span class="sxs-lookup"><span data-stu-id="96532-132">How to enable remoting in an enterprise</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="96532-133">Verwenden Sie das-Cmdlet, um einen einzelnen Computer zum Empfangen von PowerShell-Remote Befehlen und zum Akzeptieren von Verbindungen zu aktivieren `Enable-PSRemoting` .</span><span class="sxs-lookup"><span data-stu-id="96532-133">To enable a single computer to receive remote PowerShell commands and accept connections, use the `Enable-PSRemoting` cmdlet.</span></span>

<span data-ttu-id="96532-134">Zum Aktivieren von Remoting für mehrere Computer in einem Unternehmen können Sie die folgenden skalierten Optionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="96532-134">To enable remoting for multiple computers in an enterprise, you can use the following scaled options.</span></span>

- <span data-ttu-id="96532-135">Aktivieren Sie die Gruppenrichtlinie **Automatische Konfiguration von** Listenern zulassen, um Listener für Remoting zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="96532-135">To configure listeners for remoting, enable the **Allow automatic configuration of listeners** group policy.</span></span>

- <span data-ttu-id="96532-136">Verwenden Sie das-Cmdlet, um den Starttyp der Windows-Remoteverwaltung (WinRM) auf mehreren Computern auf "automatisch" festzulegen `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="96532-136">To set the startup type of the Windows Remote Management (WinRM) to Automatic on multiple computers, use the `Set-Service` cmdlet.</span></span>

- <span data-ttu-id="96532-137">Um eine Firewallausnahme zu aktivieren, verwenden Sie die Gruppenrichtlinie **Windows-Firewall: lokale Port Ausnahmen zulassen** .</span><span class="sxs-lookup"><span data-stu-id="96532-137">To enable a firewall exception, use the **Windows Firewall: Allow Local Port Exceptions** group policy.</span></span>

### <a name="how-to-enable-listeners-by-using-a-group-policy"></a><span data-ttu-id="96532-138">Aktivieren von Listenern mithilfe einer Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="96532-138">How to enable listeners by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="96532-139">Um die Listener für alle Computer in einer Domäne zu konfigurieren, aktivieren Sie die Richtlinie **Automatische Konfiguration von** Listenern zulassen im folgenden Gruppenrichtlinie Pfad:</span><span class="sxs-lookup"><span data-stu-id="96532-139">To configure the listeners for all computers in a domain, enable the **Allow automatic configuration of listeners** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Windows Components
    \Windows Remote Management (WinRM)\WinRM service
```

<span data-ttu-id="96532-140">Aktivieren Sie die Richtlinie, und geben Sie die IPv4-und IPv6-Filter</span><span class="sxs-lookup"><span data-stu-id="96532-140">Enable the policy and specify the IPv4 and IPv6 filters.</span></span> <span data-ttu-id="96532-141">Platzhalter ( `*` ) sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="96532-141">Wildcards (`*`) are permitted.</span></span>

### <a name="how-to-enable-remoting-on-public-networks"></a><span data-ttu-id="96532-142">Aktivieren von Remoting in öffentlichen Netzwerken</span><span class="sxs-lookup"><span data-stu-id="96532-142">How to enable remoting on public networks</span></span>

```
ERROR:  Unable to check the status of the firewall
```

<span data-ttu-id="96532-143">`Enable-PSRemoting`Mit dem-Cmdlet wird dieser Fehler zurückgegeben, wenn das lokale Netzwerk öffentlich ist und der **skipnetworkprofilecheck** -Parameter nicht im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96532-143">The `Enable-PSRemoting` cmdlet returns this error when the local network is public and the **SkipNetworkProfileCheck** parameter is not used in the command.</span></span>

<span data-ttu-id="96532-144">Unter Serverversionen von Windows ist `Enable-PSRemoting` bei allen Netzwerkadressen Typen erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="96532-144">On server versions of Windows, `Enable-PSRemoting` succeeds on all network location types.</span></span> <span data-ttu-id="96532-145">Es werden Firewallregeln erstellt, die den Remote Zugriff auf private und Domänen Netzwerke ("Home" und "Work") ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="96532-145">It creates firewall rules that allow remote access to private and domain ("Home" and "Work") networks.</span></span> <span data-ttu-id="96532-146">Für öffentliche Netzwerke werden Firewallregeln erstellt, die den Remote Zugriff über das gleiche lokale Subnetz ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="96532-146">For public networks, it creates firewall rules that allows remote access from the same local subnet.</span></span>

<span data-ttu-id="96532-147">Unter Client Versionen von Windows ist `Enable-PSRemoting` für private Netzwerke und Domänen Netzwerke erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="96532-147">On client versions of Windows, `Enable-PSRemoting` succeeds on private and domain networks.</span></span> <span data-ttu-id="96532-148">Standardmäßig schlägt Sie in öffentlichen Netzwerken fehl, aber wenn Sie den **skipnetworkprofilecheck** -Parameter verwenden, ist erfolgreich, und es wird `Enable-PSRemoting` eine Firewallregel erstellt, die Datenverkehr aus dem gleichen lokalen Subnetz zulässt.</span><span class="sxs-lookup"><span data-stu-id="96532-148">By default, it fails on public networks, but if you use the **SkipNetworkProfileCheck** parameter, `Enable-PSRemoting` succeeds and creates a firewall rule that allows traffic from the same local subnet.</span></span>

<span data-ttu-id="96532-149">Führen Sie den folgenden Befehl aus, um die Einschränkung des lokalen Subnetzes in öffentlichen Netzwerken zu entfernen und den Remote Zugriff von einem beliebigen Speicherort zuzulassen:</span><span class="sxs-lookup"><span data-stu-id="96532-149">To remove the local subnet restriction on public networks and allow remote access from any location, run the following command:</span></span>

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

<span data-ttu-id="96532-150">Das- `Set-NetFirewallRule` Cmdlet wird vom Netsecurity-Modul exportiert.</span><span class="sxs-lookup"><span data-stu-id="96532-150">The `Set-NetFirewallRule` cmdlet is exported by the NetSecurity module.</span></span>

> [!NOTE]
> <span data-ttu-id="96532-151">In Windows PowerShell 2,0 erstellt auf Computern, auf denen Serverversionen von Windows ausgeführt werden, `Enable-PSRemoting` Firewallregeln, die den Remote Zugriff auf private, Domänen-und öffentliche Netzwerke ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="96532-151">In Windows PowerShell 2.0, on computers running server versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access on private, domain and public networks.</span></span> <span data-ttu-id="96532-152">Auf Computern, auf denen Client Versionen von Windows ausgeführt werden, `Enable-PSRemoting` erstellt Firewallregeln, die den Remote Zugriff nur in privaten und Domänen Netzwerken zulassen.</span><span class="sxs-lookup"><span data-stu-id="96532-152">On computers running client versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access only on private and domain networks.</span></span>

### <a name="how-to-enable-a-firewall-exception-by-using-a-group-policy"></a><span data-ttu-id="96532-153">Aktivieren einer Firewallausnahme mithilfe einer Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="96532-153">How to enable a firewall exception by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="96532-154">Aktivieren Sie zum Aktivieren einer Firewallausnahme für auf allen Computern in einer Domäne die Richtlinie " **Windows-Firewall: Ausnahmen für lokale Ports zulassen** " im folgenden Gruppenrichtlinie Pfad:</span><span class="sxs-lookup"><span data-stu-id="96532-154">To enable a firewall exception for in all computers in a domain, enable the **Windows Firewall: Allow local port exceptions** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Network
    \Network Connections\Windows Firewall\Domain Profile
```

<span data-ttu-id="96532-155">Diese Richtlinie ermöglicht Mitgliedern der Gruppe "Administratoren" auf dem Computer die Verwendung der **Windows-Firewall** in der **Systemsteuerung** , um eine Firewallausnahme für den Windows-Remoteverwaltung-Dienst zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="96532-155">This policy allows members of the Administrators group on the computer to use **Windows Firewall** in **Control Panel** to create a firewall exception for the Windows Remote Management service.</span></span>

<span data-ttu-id="96532-156">Wenn die Richtlinien Konfiguration falsch ist, erhalten Sie möglicherweise die folgende Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="96532-156">If the policy configuration is incorrect you may receive the following error:</span></span>

```
The client cannot connect to the destination specified in the request. Verify
that the service on the destination is running and is accepting requests.
```

<span data-ttu-id="96532-157">Ein Konfigurationsfehler in der Richtlinie führt zu einem leeren Wert für die **listeningon** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="96532-157">A configuration error in the policy results in an empty value for the **ListeningOn** property.</span></span> <span data-ttu-id="96532-158">Verwenden Sie den folgenden Befehl, um den Wert zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="96532-158">Use the following command to check the value.</span></span>

```powershell
PS> Get-WSManInstance winrm/config/listener -Enumerate

cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
Source                : GPO
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 5985
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {}
```

### <a name="how-to-set-the-startup-type-of-the-winrm-service"></a><span data-ttu-id="96532-159">Festlegen des Starttyps für den WinRM-Dienst</span><span class="sxs-lookup"><span data-stu-id="96532-159">How to set the startup type of the WinRM service</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="96532-160">PowerShell-Remoting ist abhängig vom Windows-Remoteverwaltung (WinRM)-Dienst.</span><span class="sxs-lookup"><span data-stu-id="96532-160">PowerShell remoting depends upon the Windows Remote Management (WinRM) service.</span></span>
<span data-ttu-id="96532-161">Der Dienst muss ausgeführt werden, um Remote Befehle zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="96532-161">The service must be running to support remote commands.</span></span>

<span data-ttu-id="96532-162">Unter Serverversionen von Windows ist der Starttyp des Windows-Remoteverwaltung (WinRM)-Dienstanbieter automatisch.</span><span class="sxs-lookup"><span data-stu-id="96532-162">On server versions of Windows, the startup type of the Windows Remote Management (WinRM) service is Automatic.</span></span>

<span data-ttu-id="96532-163">Unter Client Versionen von Windows ist der WinRM-Dienst jedoch standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="96532-163">However, on client versions of Windows, the WinRM service is disabled by default.</span></span>

<span data-ttu-id="96532-164">Verwenden Sie das-Cmdlet, um den Starttyp eines Dienstanbieter auf einem Remote Computer festzulegen `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="96532-164">To set the startup type of a service on a remote computer, use the `Set-Service` cmdlet.</span></span>

<span data-ttu-id="96532-165">Wenn Sie den Befehl auf mehreren Computern ausführen möchten, können Sie eine Textdatei oder eine CSV-Datei mit den Computernamen erstellen.</span><span class="sxs-lookup"><span data-stu-id="96532-165">To run the command on multiple computers, you can create a text file or CSV file of the computer names.</span></span>

<span data-ttu-id="96532-166">Mit den folgenden Befehlen wird z. b. eine Liste mit Computernamen aus der `Servers.txt` Datei und dann der Starttyp des WinRM-Dienstanbieter auf allen Computern auf **automatisch** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="96532-166">For example, the following commands get a list of computer names from the `Servers.txt` file and then sets the startup type of the WinRM service on all of the computers to **Automatic**.</span></span>

```powershell
$servers = Get-Content servers.txt
Set-Service WinRM -ComputerName $servers -startuptype Automatic
```

<span data-ttu-id="96532-167">Verwenden Sie das `Get-WMIObject` Cmdlet mit dem **Win32_Service** Objekt, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="96532-167">To see the results use the `Get-WMIObject` cmdlet with the **Win32_Service** object.</span></span> <span data-ttu-id="96532-168">Weitere Informationen finden Sie unter [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).</span><span class="sxs-lookup"><span data-stu-id="96532-168">For more information, see [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).</span></span>

### <a name="how-to-recreate-the-default-session-configurations"></a><span data-ttu-id="96532-169">So erstellen Sie die Standard Sitzungs Konfigurationen neu</span><span class="sxs-lookup"><span data-stu-id="96532-169">How to recreate the default session configurations</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="96532-170">Um eine Verbindung mit dem lokalen Computer herzustellen und Befehle Remote auszuführen, muss der lokale Computer Sitzungs Konfigurationen für Remote Befehle enthalten.</span><span class="sxs-lookup"><span data-stu-id="96532-170">To connect to the local computer and run commands remotely, the local computer must include session configurations for remote commands.</span></span>

<span data-ttu-id="96532-171">Wenn Sie verwenden `Enable-PSRemoting` , werden Standard Sitzungs Konfigurationen auf dem lokalen Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="96532-171">When you use `Enable-PSRemoting`, it creates default session configurations on the local computer.</span></span> <span data-ttu-id="96532-172">Remote Benutzer verwenden diese Sitzungs Konfigurationen, wenn ein Remote Befehl nicht den **ConfigurationName** -Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="96532-172">Remote users use these session configurations whenever a remote command does not include the **ConfigurationName** parameter.</span></span>

<span data-ttu-id="96532-173">Wenn die Registrierung der Standardkonfigurationen auf einem Computer aufgehoben oder gelöscht wird, verwenden `Enable-PSRemoting` Sie das Cmdlet, um Sie neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="96532-173">If the default configurations on a computer are unregistered or deleted, use the `Enable-PSRemoting` cmdlet to recreate them.</span></span> <span data-ttu-id="96532-174">Dieses Cmdlet kann wiederholt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="96532-174">You can use this cmdlet repeatedly.</span></span> <span data-ttu-id="96532-175">Wenn bereits eine Funktion konfiguriert ist, werden keine Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="96532-175">It does not generate errors if a feature is already configured.</span></span>

<span data-ttu-id="96532-176">Wenn Sie die Standard Sitzungs Konfigurationen ändern und die ursprünglichen Standard Sitzungs Konfigurationen wiederherstellen möchten, verwenden Sie das `Unregister-PSSessionConfiguration` Cmdlet, um die geänderten Sitzungs Konfigurationen zu löschen, und verwenden Sie dann das `Enable-PSRemoting` Cmdlet, um Sie wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="96532-176">If you change the default session configurations and want to restore the original default session configurations, use the `Unregister-PSSessionConfiguration` cmdlet to delete the changed session configurations and then use the `Enable-PSRemoting` cmdlet to restore them.</span></span>
<span data-ttu-id="96532-177">`Enable-PSRemoting` vorhandene Sitzungs Konfigurationen werden von nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="96532-177">`Enable-PSRemoting` does not change existing session configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="96532-178">Wenn `Enable-PSRemoting` die Standard Sitzungs Konfiguration von wieder hergestellt wird, werden keine expliziten Sicherheits Deskriptoren für die Konfigurationen erstellt.</span><span class="sxs-lookup"><span data-stu-id="96532-178">When `Enable-PSRemoting` restores the default session configuration, it does not create explicit security descriptors for the configurations.</span></span> <span data-ttu-id="96532-179">Stattdessen erben die Konfigurationen die Sicherheits Beschreibung von rootddl, die standardmäßig sicher ist.</span><span class="sxs-lookup"><span data-stu-id="96532-179">Instead, the configurations inherit the security descriptor of the RootSDDL, which is secure by default.</span></span>

<span data-ttu-id="96532-180">Geben Sie Folgendes ein, um die Sicherheits Beschreibung für roozddl anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="96532-180">To see the RootSDDL security descriptor, type:</span></span>

```powershell
Get-Item wsman:\localhost\Service\RootSDDL
```

<span data-ttu-id="96532-181">Verwenden Sie das `Set-Item` Cmdlet im WSMAN:-Laufwerk, um die rootsddl zu ändern.</span><span class="sxs-lookup"><span data-stu-id="96532-181">To change the RootSDDL, use the `Set-Item` cmdlet in the WSMan: drive.</span></span> <span data-ttu-id="96532-182">Verwenden Sie das `Set-PSSessionConfiguration` Cmdlet mit den Parametern **securitydescriptorsddl** oder **showsecuritydescriptorui** , um die Sicherheits Beschreibung einer Sitzungs Konfiguration zu ändern.</span><span class="sxs-lookup"><span data-stu-id="96532-182">To change the security descriptor of a session configuration, use the `Set-PSSessionConfiguration` cmdlet with the **SecurityDescriptorSDDL** or **ShowSecurityDescriptorUI** parameters.</span></span>

<span data-ttu-id="96532-183">Weitere Informationen zum WSMAN:-Laufwerk finden Sie im Hilfethema für den WSMAN-Anbieter ("Get-Help WSMAN").</span><span class="sxs-lookup"><span data-stu-id="96532-183">For more information about the WSMan: drive, see the Help topic for the WSMan provider ("Get-Help wsman").</span></span>

### <a name="how-to-provide-administrator-credentials"></a><span data-ttu-id="96532-184">Angeben von Administrator Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="96532-184">How to provide administrator credentials</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="96532-185">Zum Erstellen einer PSSession oder zum Ausführen von Befehlen auf einem Remote Computer muss der aktuelle Benutzer standardmäßig Mitglied der Gruppe "Administratoren" auf dem Remote Computer sein.</span><span class="sxs-lookup"><span data-stu-id="96532-185">To create a PSSession or run commands on a remote computer, by default, the current user must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="96532-186">Anmelde Informationen werden manchmal auch dann benötigt, wenn der aktuelle Benutzer an einem Konto angemeldet ist, das Mitglied der Gruppe "Administratoren" ist.</span><span class="sxs-lookup"><span data-stu-id="96532-186">Credentials are sometimes required even when the current user is logged on to an account that is a member of the Administrators group.</span></span>

<span data-ttu-id="96532-187">Wenn der aktuelle Benutzer ein Mitglied der Gruppe "Administratoren" auf dem Remote Computer ist oder die Anmelde Informationen eines Mitglieds der Gruppe "Administratoren" angeben kann, verwenden Sie den **Credential** -Parameter der `New-PSSession` `Enter-PSSession` `Invoke-Command` Cmdlets, oder, um eine Remote Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="96532-187">If the current user is a member of the Administrators group on the remote computer, or can provide the credentials of a member of the Administrators group, use the **Credential** parameter of the `New-PSSession`, `Enter-PSSession` or `Invoke-Command` cmdlets to connect remotely.</span></span>

<span data-ttu-id="96532-188">Der folgende Befehl stellt z. b. die Anmelde Informationen eines Administrators bereit.</span><span class="sxs-lookup"><span data-stu-id="96532-188">For example, the following command provides the credentials of an Administrator.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\Admin01
```

<span data-ttu-id="96532-189">Weitere Informationen zum **Credential** -Parameter finden Sie unter [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) oder [aufrufen-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).</span><span class="sxs-lookup"><span data-stu-id="96532-189">For more information about the **Credential** parameter, see [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).</span></span>

### <a name="how-to-enable-remoting-for-non-administrative-users"></a><span data-ttu-id="96532-190">Aktivieren von Remoting für Benutzer, die keine Administratoren sind</span><span class="sxs-lookup"><span data-stu-id="96532-190">How to enable remoting for non-administrative users</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="96532-191">Um eine PSSession einzurichten oder einen Befehl auf einem Remote Computer auszuführen, muss der Benutzer über die Berechtigung zum Verwenden der Sitzungs Konfigurationen auf dem Remote Computer verfügen.</span><span class="sxs-lookup"><span data-stu-id="96532-191">To establish a PSSession or run a command on a remote computer, the user must have permission to use the session configurations on the remote computer.</span></span>

<span data-ttu-id="96532-192">Standardmäßig haben nur Mitglieder der Gruppe "Administratoren" auf einem Computer die Berechtigung, die Standard Sitzungs Konfigurationen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="96532-192">By default, only members of the Administrators group on a computer have permission to use the default session configurations.</span></span> <span data-ttu-id="96532-193">Daher können nur Mitglieder der Gruppe "Administratoren" eine Remote Verbindung mit dem Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="96532-193">Therefore, only members of the Administrators group can connect to the computer remotely.</span></span>

<span data-ttu-id="96532-194">Um anderen Benutzern das Herstellen einer Verbindung mit dem lokalen Computer zu gestatten, erteilen Sie dem Benutzerberechtigungen zum Ausführen der Standard Sitzungs Konfigurationen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="96532-194">To allow other users to connect to the local computer, give the user Execute permissions to the default session configurations on the local computer.</span></span>

<span data-ttu-id="96532-195">Mit dem folgenden Befehl wird ein Eigenschaften Blatt geöffnet, mit dem Sie die Sicherheits Beschreibung der standardmäßigen Microsoft. PowerShell-Sitzungs Konfiguration auf dem lokalen Computer ändern können.</span><span class="sxs-lookup"><span data-stu-id="96532-195">The following command opens a property sheet that lets you change the security descriptor of the default Microsoft.PowerShell session configuration on the local computer.</span></span>

```powershell
Set-PSSessionConfiguration Microsoft.PowerShell -ShowSecurityDescriptorUI
```

<span data-ttu-id="96532-196">Weitere Informationen finden Sie unter [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="96532-196">For more information, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

### <a name="how-to-enable-remoting-for-administrators-in-other-domains"></a><span data-ttu-id="96532-197">Aktivieren von Remoting für Administratoren in anderen Domänen</span><span class="sxs-lookup"><span data-stu-id="96532-197">How to enable remoting for administrators in other domains</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="96532-198">Wenn ein Benutzer in einer anderen Domäne Mitglied der Gruppe "Administratoren" auf dem lokalen Computer ist, kann der Benutzer nicht Remote mit Administrator Rechten eine Verbindung mit dem lokalen Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="96532-198">When a user in another domain is a member of the Administrators group on the local computer, the user cannot connect to the local computer remotely with Administrator privileges.</span></span> <span data-ttu-id="96532-199">Standardmäßig werden Remote Verbindungen aus anderen Domänen nur mit Standard Token für Benutzerberechtigungen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="96532-199">By default, remote connections from other domains run with only standard user privilege tokens.</span></span>

<span data-ttu-id="96532-200">Sie können jedoch den Registrierungs Eintrag **LocalAccountTokenFilterPolicy** verwenden, um das Standardverhalten zu ändern und Remote Benutzern, die Mitglieder der Gruppe "Administratoren" sind, das Ausführen von Administrator Rechten zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="96532-200">However, you can use the **LocalAccountTokenFilterPolicy** registry entry to change the default behavior and allow remote users who are members of the Administrators group to run with Administrator privileges.</span></span>

> [!CAUTION]
> <span data-ttu-id="96532-201">Mit dem Eintrag **LocalAccountTokenFilterPolicy** werden die Remote Einschränkungen der Benutzerkontensteuerung (User Account Control, UAC) für alle Benutzer aller betroffenen Computer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="96532-201">The **LocalAccountTokenFilterPolicy** entry disables user account control (UAC) remote restrictions for all users of all affected computers.</span></span> <span data-ttu-id="96532-202">Berücksichtigen Sie die Auswirkungen dieser Einstellung sorgfältig, bevor Sie die Richtlinie ändern.</span><span class="sxs-lookup"><span data-stu-id="96532-202">Consider the implications of this setting carefully before changing the policy.</span></span>

<span data-ttu-id="96532-203">Verwenden Sie den folgenden Befehl, um die Richtlinie zu ändern: Legen Sie den Wert des Registrierungs Eintrags **localaccountbukenfilterpolicy** auf 1 fest.</span><span class="sxs-lookup"><span data-stu-id="96532-203">To change the policy, use the following command to set the value of the **LocalAccountTokenFilterPolicy** registry entry to 1.</span></span>

```powershell
New-ItemProperty -Name LocalAccountTokenFilterPolicy `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System `
  -PropertyType DWord -Value 1
```

### <a name="how-to-use-an-ip-address-in-a-remote-command"></a><span data-ttu-id="96532-204">Verwenden einer IP-Adresse in einem Remote Befehl</span><span class="sxs-lookup"><span data-stu-id="96532-204">How to use an ip address in a remote command</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="96532-205">Der **Computername** -Parameter der `New-PSSession` `Enter-PSSession` `Invoke-Command` Cmdlets, und akzeptiert eine IP-Adresse als gültigen Wert.</span><span class="sxs-lookup"><span data-stu-id="96532-205">The **ComputerName** parameter of the `New-PSSession`, `Enter-PSSession` and `Invoke-Command` cmdlets accepts an IP address as a valid value.</span></span> <span data-ttu-id="96532-206">Da die Kerberos-Authentifizierung IP-Adressen jedoch nicht unterstützt, wird standardmäßig die NTLM-Authentifizierung verwendet, wenn Sie eine IP-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="96532-206">However, because Kerberos authentication does not support IP addresses, NTLM authentication is used by default whenever you specify an IP address.</span></span>

<span data-ttu-id="96532-207">Wenn Sie die NTLM-Authentifizierung verwenden, ist das folgende Verfahren für Remoting erforderlich.</span><span class="sxs-lookup"><span data-stu-id="96532-207">When using NTLM authentication, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="96532-208">Konfigurieren Sie den Computer für den HTTPS-Transport, oder fügen Sie die IP-Adressen der Remote Computer der Liste "Treuhänder Hosts" auf dem lokalen Computer hinzu.</span><span class="sxs-lookup"><span data-stu-id="96532-208">Configure the computer for HTTPS transport or add the IP addresses of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="96532-209">Verwenden Sie den **Credential** -Parameter in allen Remote Befehlen.</span><span class="sxs-lookup"><span data-stu-id="96532-209">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="96532-210">Dies ist auch dann erforderlich, wenn Sie die Anmelde Informationen des aktuellen Benutzers übermitteln.</span><span class="sxs-lookup"><span data-stu-id="96532-210">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-connect-remotely-from-a-workgroup-based-computer"></a><span data-ttu-id="96532-211">Herstellen einer Remote Verbindung von einem Arbeitsgruppen basierten Computer aus</span><span class="sxs-lookup"><span data-stu-id="96532-211">How to connect remotely from a workgroup-based computer</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="96532-212">Wenn sich der lokale Computer nicht in einer Domäne befindet, ist das folgende Verfahren für Remoting erforderlich.</span><span class="sxs-lookup"><span data-stu-id="96532-212">When the local computer is not in a domain, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="96532-213">Konfigurieren Sie den Computer für den HTTPS-Transport, oder fügen Sie die Namen der Remote Computer der Liste "Treuhänder Hosts" auf dem lokalen Computer hinzu.</span><span class="sxs-lookup"><span data-stu-id="96532-213">Configure the computer for HTTPS transport or add the names of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="96532-214">Vergewissern Sie sich, dass auf dem Arbeitsgruppen basierten Computer ein Kennwort festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="96532-214">Verify that a password is set on the workgroup-based computer.</span></span> <span data-ttu-id="96532-215">Wenn kein Kennwort festgelegt ist oder der Kenn Wort Wert leer ist, können Sie keine Remote Befehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="96532-215">If a password is not set or the password value is empty, you cannot run remote commands.</span></span>

   <span data-ttu-id="96532-216">Verwenden Sie die Benutzerkonten in der Systemsteuerung, um das Kennwort für Ihr Benutzerkonto festzulegen.</span><span class="sxs-lookup"><span data-stu-id="96532-216">To set password for your user account, use User Accounts in Control Panel.</span></span>

1. <span data-ttu-id="96532-217">Verwenden Sie den **Credential** -Parameter in allen Remote Befehlen.</span><span class="sxs-lookup"><span data-stu-id="96532-217">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="96532-218">Dies ist auch dann erforderlich, wenn Sie die Anmelde Informationen des aktuellen Benutzers übermitteln.</span><span class="sxs-lookup"><span data-stu-id="96532-218">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-add-a-computer-to-the-trusted-hosts-list"></a><span data-ttu-id="96532-219">Hinzufügen eines Computers zur Liste der vertrauenswürdigen Hosts</span><span class="sxs-lookup"><span data-stu-id="96532-219">How to add a computer to the trusted hosts list</span></span>

<span data-ttu-id="96532-220">Das Element "Treuhänder Hosts" kann eine durch Trennzeichen getrennte Liste von Computernamen, IP-Adressen und voll qualifizierten Domänen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="96532-220">The TrustedHosts item can contain a comma-separated list of computer names, IP addresses, and fully-qualified domain names.</span></span> <span data-ttu-id="96532-221">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="96532-221">Wildcards are permitted.</span></span>

<span data-ttu-id="96532-222">Verwenden Sie das WSMAN:-Laufwerk, um die Liste der vertrauenswürdigen Hosts anzuzeigen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="96532-222">To view or change the trusted host list, use the WSMan: drive.</span></span> <span data-ttu-id="96532-223">Das Element "Treuhänder Host" befindet sich im- `WSMan:\localhost\Client` Knoten.</span><span class="sxs-lookup"><span data-stu-id="96532-223">The TrustedHost item is in the `WSMan:\localhost\Client` node.</span></span>

<span data-ttu-id="96532-224">Nur Mitglieder der Gruppe "Administratoren" auf dem Computer verfügen über die Berechtigung, die Liste der vertrauenswürdigen Hosts auf dem Computer zu ändern.</span><span class="sxs-lookup"><span data-stu-id="96532-224">Only members of the Administrators group on the computer have permission to change the list of trusted hosts on the computer.</span></span>

<span data-ttu-id="96532-225">Vorsicht: der Wert, den Sie für das Element "Treuhänder Hosts" festlegen, wirkt sich auf alle Benutzer des Computers aus.</span><span class="sxs-lookup"><span data-stu-id="96532-225">Caution: The value that you set for the TrustedHosts item affects all users of the computer.</span></span>

<span data-ttu-id="96532-226">Verwenden Sie den folgenden Befehl, um die Liste der vertrauenswürdigen Hosts anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="96532-226">To view the list of trusted hosts, use the following command:</span></span>

```powershell
Get-Item wsman:\localhost\Client\TrustedHosts
```

<span data-ttu-id="96532-227">Sie können auch das `Set-Location` Cmdlet (Alias = CD) verwenden, um durch das WSMAN:-Laufwerk an den Speicherort zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="96532-227">You can also use the `Set-Location` cmdlet (alias = cd) to navigate though the WSMan: drive to the location.</span></span> <span data-ttu-id="96532-228">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="96532-228">For example:</span></span>

```powershell
cd WSMan:\localhost\Client; dir
```

<span data-ttu-id="96532-229">Wenn Sie alle Computer der Liste vertrauenswürdiger Hosts hinzufügen möchten, verwenden Sie den folgenden Befehl, der den Wert \* (alle) in Computername platziert.</span><span class="sxs-lookup"><span data-stu-id="96532-229">To add all computers to the list of trusted hosts, use the following command, which places a value of \* (all) in the ComputerName</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts -Value *
```

<span data-ttu-id="96532-230">Sie können auch ein Platzhalter Zeichen ( `*` ) verwenden, um alle Computer in einer bestimmten Domäne der Liste der vertrauenswürdigen Hosts hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="96532-230">You can also use a wildcard character (`*`) to add all computers in a particular domain to the list of trusted hosts.</span></span> <span data-ttu-id="96532-231">Mit dem folgenden Befehl werden beispielsweise alle Computer in der Domäne "Fabrikam" der Liste der vertrauenswürdigen Hosts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="96532-231">For example, the following command adds all of the computers in the Fabrikam domain to the list of trusted hosts.</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts *.fabrikam.com
```

<span data-ttu-id="96532-232">Um die Namen bestimmter Computer der Liste vertrauenswürdiger Hosts hinzuzufügen, verwenden Sie das folgende Befehls Format:</span><span class="sxs-lookup"><span data-stu-id="96532-232">To add the names of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <ComputerName>
```

<span data-ttu-id="96532-233">Jeder Wert `<ComputerName>` muss das folgende Format aufweisen:</span><span class="sxs-lookup"><span data-stu-id="96532-233">where each value `<ComputerName>` must have the following format:</span></span>

```
<Computer>.<Domain>.<Company>.<top-level-domain>
```

<span data-ttu-id="96532-234">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="96532-234">For example:</span></span>

```powershell
$server = 'Server01.Domain01.Fabrikam.com'
Set-Item wsman:\localhost\Client\TrustedHosts -Value $server
```

<span data-ttu-id="96532-235">Wenn Sie einen Computernamen zu einer vorhandenen Liste vertrauenswürdiger Hosts hinzufügen möchten, speichern Sie zuerst den aktuellen Wert in einer Variablen, und legen Sie dann den Wert auf eine durch Trennzeichen getrennte Liste fest, die die aktuellen und die neuen Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="96532-235">To add a computer name to an existing list of trusted hosts, first save the current value in a variable, and then set the value to a comma-separated list that includes the current and new values.</span></span>

<span data-ttu-id="96532-236">Verwenden Sie z. b. den folgenden Befehl, um den Computer "Server01" einer vorhandenen Liste vertrauenswürdiger Hosts hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="96532-236">For example, to add the Server01 computer to an existing list of trusted hosts, use the following command</span></span>

```powershell
$curValue = (Get-Item wsman:\localhost\Client\TrustedHosts).value

Set-Item wsman:\localhost\Client\TrustedHosts -Value `
  "$curValue, Server01.Domain01.Fabrikam.com"
```

<span data-ttu-id="96532-237">Verwenden Sie das folgende Befehls Format, um die IP-Adressen bestimmter Computer der Liste der vertrauenswürdigen Hosts hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="96532-237">To add the IP addresses of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <IP Address>
```

<span data-ttu-id="96532-238">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="96532-238">For example:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value 172.16.0.0
```

<span data-ttu-id="96532-239">Zum Hinzufügen eines Computers zur Liste "Treuhänder Hosts" eines Remote Computers verwenden Sie das `Connect-WSMan` Cmdlet zum Hinzufügen eines Knotens für den Remote Computer zum WSMAN:-Laufwerk auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="96532-239">To add a computer to the TrustedHosts list of a remote computer, use the `Connect-WSMan` cmdlet to add a node for the remote computer to the WSMan: drive on the local computer.</span></span> <span data-ttu-id="96532-240">Verwenden Sie dann einen `Set-Item` Befehl, um den Computer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="96532-240">Then use a `Set-Item` command to add the computer.</span></span>

<span data-ttu-id="96532-241">Weitere Informationen zum `Connect-WSMan` Cmdlet finden Sie unter [Connect-WSMAN](xref:Microsoft.WSMan.Management.Connect-WSMan).</span><span class="sxs-lookup"><span data-stu-id="96532-241">For more information about the `Connect-WSMan` cmdlet, see [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span>

## <a name="troubleshooting-computer-configuration-issues"></a><span data-ttu-id="96532-242">Problembehandlung bei Computer Konfigurationsproblemen</span><span class="sxs-lookup"><span data-stu-id="96532-242">Troubleshooting computer configuration issues</span></span>

<span data-ttu-id="96532-243">In diesem Abschnitt werden remotingprobleme erläutert, die sich auf bestimmte Konfigurationen eines Computers, einer Domäne oder eines Unternehmens beziehen.</span><span class="sxs-lookup"><span data-stu-id="96532-243">This section discusses remoting problems that are related to particular configurations of a computer, domain, or enterprise.</span></span>

### <a name="how-to-configure-remoting-on-alternate-ports"></a><span data-ttu-id="96532-244">Konfigurieren von Remoting für alternative Ports</span><span class="sxs-lookup"><span data-stu-id="96532-244">How to configure remoting on alternate ports</span></span>

```
ERROR: The connection to the specified remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="96532-245">PowerShell-Remoting verwendet standardmäßig Port 80 für den HTTP-Transport.</span><span class="sxs-lookup"><span data-stu-id="96532-245">PowerShell remoting uses port 80 for HTTP transport by default.</span></span> <span data-ttu-id="96532-246">Der Standardport wird verwendet, wenn der Benutzer die **ConnectionUri** -oder **Port** -Parameter nicht in einem Remote Befehl angibt.</span><span class="sxs-lookup"><span data-stu-id="96532-246">The default port is used whenever the user does not specify the **ConnectionURI** or **Port** parameters in a remote command.</span></span>

<span data-ttu-id="96532-247">Um den Standardport zu ändern, der von PowerShell verwendet wird, verwenden Sie das- `Set-Item` Cmdlet im WSMAN:-Laufwerk, um den Portwert im Listener-Blattknoten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="96532-247">To change the default port that PowerShell uses, use `Set-Item` cmdlet in the WSMan: drive to change the Port value in the listener leaf node.</span></span>

<span data-ttu-id="96532-248">Der folgende Befehl ändert z. b. den Standardport in 8080.</span><span class="sxs-lookup"><span data-stu-id="96532-248">For example, the following command changes the default port to 8080.</span></span>

```powershell
Set-Item wsman:\localhost\listener\listener*\port -Value 8080
```

### <a name="how-to-configure-remoting-with-a-proxy-server"></a><span data-ttu-id="96532-249">Konfigurieren von Remoting mit einem Proxy Server</span><span class="sxs-lookup"><span data-stu-id="96532-249">How to configure remoting with a proxy server</span></span>

```
ERROR: The client cannot connect to the destination specified in the request.
Verify that the service on the destination is running and is accepting
requests.
```

<span data-ttu-id="96532-250">Da PowerShell-Remoting das HTTP-Protokoll verwendet, wird es von http-Proxy Einstellungen beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="96532-250">Because PowerShell remoting uses the HTTP protocol, it is affected by HTTP proxy settings.</span></span> <span data-ttu-id="96532-251">In Unternehmen, die über Proxy Server verfügen, können Benutzer nicht direkt auf einen PowerShell-Remote Computer zugreifen.</span><span class="sxs-lookup"><span data-stu-id="96532-251">In enterprises that have proxy servers, users cannot access a PowerShell remote computer directly.</span></span>

<span data-ttu-id="96532-252">Um dieses Problem zu beheben, verwenden Sie die Optionen für die Proxy Einstellung in Ihrem Remote Befehl.</span><span class="sxs-lookup"><span data-stu-id="96532-252">To resolve this problem, use proxy setting options in your remote command.</span></span> <span data-ttu-id="96532-253">Die folgenden Einstellungen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="96532-253">The following settings are available:</span></span>

- <span data-ttu-id="96532-254">Proxy Access Type</span><span class="sxs-lookup"><span data-stu-id="96532-254">ProxyAccessType</span></span>
- <span data-ttu-id="96532-255">Proxy Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="96532-255">ProxyAuthentication</span></span>
- <span data-ttu-id="96532-256">ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="96532-256">ProxyCredential</span></span>

<span data-ttu-id="96532-257">Um diese Optionen für einen bestimmten Befehl festzulegen, verwenden Sie das folgende Verfahren:</span><span class="sxs-lookup"><span data-stu-id="96532-257">To set these options for a particular command, use the following procedure:</span></span>

1. <span data-ttu-id="96532-258">Verwenden Sie die Parameter **proxyaccesstype** , **Proxyauthentication** und **proxycredential** des `New-PSSessionOption` Cmdlets, um ein Sitzungs Options Objekt mit den Proxy Einstellungen für Ihr Unternehmen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="96532-258">Use the **ProxyAccessType** , **ProxyAuthentication** , and **ProxyCredential** parameters of the `New-PSSessionOption` cmdlet to create a session option object with the proxy settings for your enterprise.</span></span> <span data-ttu-id="96532-259">Speichern Sie das Options Objekt ist eine Variable.</span><span class="sxs-lookup"><span data-stu-id="96532-259">Save the option object is a variable.</span></span>

1. <span data-ttu-id="96532-260">Verwenden Sie die Variable, die das Options Objekt enthält, als Wert des **sessionoption** -Parameters eines- `New-PSSession` ,-oder- `Enter-PSSession` `Invoke-Command` Befehls.</span><span class="sxs-lookup"><span data-stu-id="96532-260">Use the variable that contains the option object as the value of the **SessionOption** parameter of a `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` command.</span></span>

<span data-ttu-id="96532-261">Der folgende Befehl erstellt z. b. ein Sitzungs Options Objekt mit Proxy Sitzungs Optionen und verwendet dann das-Objekt, um eine Remote Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="96532-261">For example, the following command creates a session option object with proxy session options and then uses the object to create a remote session.</span></span>

```powershell
$SessionOption = New-PSSessionOption -ProxyAccessType IEConfig `
-ProxyAuthentication Negotiate -ProxyCredential Domain01\User01

New-PSSession -ConnectionURI https://www.fabrikam.com
```

<span data-ttu-id="96532-262">Weitere Informationen zum `New-PSSessionOption` Cmdlet finden Sie unter [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="96532-262">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

<span data-ttu-id="96532-263">Um diese Optionen für alle Remote Befehle in der aktuellen Sitzung festzulegen, verwenden Sie das Options Objekt, das `New-PSSessionOption` im Wert der `$PSSessionOption` Preference-Variablen erstellt.</span><span class="sxs-lookup"><span data-stu-id="96532-263">To set these options for all remote commands in the current session, use the option object that `New-PSSessionOption` creates in the value of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="96532-264">Weitere Informationen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="96532-264">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="96532-265">Um diese Optionen für alle Remote Befehle für alle PowerShell-Sitzungen auf dem lokalen Computer festzulegen, fügen Sie `$PSSessionOption` Ihrem PowerShell-Profil die Preference-Variable hinzu.</span><span class="sxs-lookup"><span data-stu-id="96532-265">To set these options for all remote commands all PowerShell sessions on the local computer, add the `$PSSessionOption` preference variable to your PowerShell profile.</span></span> <span data-ttu-id="96532-266">Weitere Informationen zu PowerShell-Profilen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="96532-266">For more information about PowerShell profiles, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="how-to-detect-a-32-bit-session-on-a-64-bit-computer"></a><span data-ttu-id="96532-267">Erkennen einer 32-Bit-Sitzung auf einem 64-Bit-Computer</span><span class="sxs-lookup"><span data-stu-id="96532-267">How to detect a 32-bit session on a 64-bit computer</span></span>

```
ERROR: The term "<tool-Name>" is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="96532-268">Wenn auf dem Remote Computer eine 64-Bit-Version von Windows ausgeführt wird und der Remote Befehl eine 32-Bit-Sitzungs Konfiguration verwendet, wie z. b. Microsoft. PowerShell32, wird von Windows-Remoteverwaltung (WinRM) ein WOW64-Prozess geladen, und Windows leitet automatisch alle Verweise auf das `$env:Windir\System32` Verzeichnis in das `$env:Windir\SysWOW64` Verzeichnis um.</span><span class="sxs-lookup"><span data-stu-id="96532-268">If the remote computer is running a 64-bit version of Windows, and the remote command is using a 32-bit session configuration, such as Microsoft.PowerShell32, Windows Remote Management (WinRM) loads a WOW64 process and Windows automatically redirects all references to the `$env:Windir\System32` directory to the `$env:Windir\SysWOW64` directory.</span></span>

<span data-ttu-id="96532-269">Wenn Sie versuchen, Tools im Verzeichnis "System32" zu verwenden, die keine Entsprechungen im Verzeichnis "syswow64" aufweisen, z `Defrag.exe` . b., können die Tools nicht im Verzeichnis gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="96532-269">As a result, if you try to use tools in the System32 directory that do not have counterparts in the SysWow64 directory, such as `Defrag.exe`, the tools cannot be found in the directory.</span></span>

<span data-ttu-id="96532-270">Um die Prozessorarchitektur zu ermitteln, die in der Sitzung verwendet wird, verwenden Sie den Wert der **PROCESSOR_ARCHITECTURE** -Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="96532-270">To find the processor architecture that is being used in the session, use the value of the **PROCESSOR_ARCHITECTURE** environment variable.</span></span> <span data-ttu-id="96532-271">Der folgende Befehl sucht die Prozessorarchitektur der Sitzung in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="96532-271">The following command finds the processor architecture of the session in the `$s` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -ConfigurationName CustomShell
Invoke-Command -Session $s {$env:PROCESSOR_ARCHITECTURE}
```

```Output
x86
```

<span data-ttu-id="96532-272">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="96532-272">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

## <a name="troubleshooting-policy-and-preference-issues"></a><span data-ttu-id="96532-273">Problembehandlung und bevorzugte Probleme</span><span class="sxs-lookup"><span data-stu-id="96532-273">Troubleshooting policy and preference issues</span></span>

<span data-ttu-id="96532-274">In diesem Abschnitt werden remotingprobleme im Zusammenhang mit Richtlinien und Einstellungen erläutert, die auf den lokalen Computern und Remote Computern festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="96532-274">This section discusses remoting problems that are related to policies and preferences set on the local and remote computers.</span></span>

### <a name="how-to-change-the-execution-policy-for-import-pssession-and-import-module"></a><span data-ttu-id="96532-275">Vorgehensweise beim Ändern der Ausführungs Richtlinie für Import-PSSession und Import-Module</span><span class="sxs-lookup"><span data-stu-id="96532-275">How to change the execution policy for Import-PSSession and Import-Module</span></span>

```
ERROR: Import-Module: File <filename> cannot be loaded because the
execution of scripts is disabled on this system.
```

<span data-ttu-id="96532-276">`Import-PSSession`Mit den `Export-PSSession` Cmdlets und werden Module erstellt, die nicht signierte Skriptdateien und Formatierungs Dateien enthalten.</span><span class="sxs-lookup"><span data-stu-id="96532-276">The `Import-PSSession` and `Export-PSSession` cmdlets create modules that contains unsigned script files and formatting files.</span></span>

<span data-ttu-id="96532-277">Zum Importieren der Module, die von diesen Cmdlets erstellt werden, entweder mithilfe von `Import-PSSession` oder `Import-Module` , kann die Ausführungs Richtlinie in der aktuellen Sitzung nicht eingeschränkt oder AllSigned werden.</span><span class="sxs-lookup"><span data-stu-id="96532-277">To import the modules that are created by these cmdlets, either by using `Import-PSSession` or `Import-Module`, the execution policy in the current session cannot be Restricted or AllSigned.</span></span> <span data-ttu-id="96532-278">Weitere Informationen zu PowerShell-Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="96532-278">For information about PowerShell execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="96532-279">Um die Module zu importieren, ohne die Ausführungs Richtlinie für den lokalen Computer zu ändern, der in der Registrierung festgelegt ist, verwenden Sie den **Scope** -Parameter von, `Set-ExecutionPolicy` um eine weniger restriktive Ausführungs Richtlinie für einen einzelnen Prozess festzulegen.</span><span class="sxs-lookup"><span data-stu-id="96532-279">To import the modules without changing the execution policy for the local computer that is set in the registry, use the **Scope** parameter of `Set-ExecutionPolicy` to set a less restrictive execution policy for a single process.</span></span>

<span data-ttu-id="96532-280">Mit dem folgenden Befehl wird z. b. ein Prozess mit der `RemoteSigned` Ausführungs Richtlinie gestartet.</span><span class="sxs-lookup"><span data-stu-id="96532-280">For example, the following command starts a process with the `RemoteSigned` execution policy.</span></span> <span data-ttu-id="96532-281">Die Änderung der Ausführungs Richtlinie wirkt sich nur auf den aktuellen Prozess aus und ändert nicht die Registrierungs Einstellung für die PowerShell- **ExecutionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="96532-281">The execution policy change affects only the current process and does not change the PowerShell **ExecutionPolicy** registry setting.</span></span>

```powershell
Set-ExecutionPolicy -Scope process -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="96532-282">Sie können auch den **ExecutionPolicy** -Parameter von verwenden `PowerShell.exe` , um eine einzelne Sitzung mit einer weniger restriktiven Ausführungs Richtlinie zu starten.</span><span class="sxs-lookup"><span data-stu-id="96532-282">You can also use the **ExecutionPolicy** parameter of `PowerShell.exe` to start a single session with a less restrictive execution policy.</span></span>

```powershell
PowerShell.exe -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="96532-283">Weitere Informationen zu Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="96532-283">For more information about execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span> <span data-ttu-id="96532-284">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `PowerShell.exe -?`.</span><span class="sxs-lookup"><span data-stu-id="96532-284">For more information, type `PowerShell.exe -?`.</span></span>

### <a name="how-to-set-and-change-quotas"></a><span data-ttu-id="96532-285">Festlegen und Ändern von Kontingenten</span><span class="sxs-lookup"><span data-stu-id="96532-285">How to set and change quotas</span></span>

```
ERROR: The total data received from the remote client exceeded allowed
maximum.
```

<span data-ttu-id="96532-286">Mithilfe von Kontingenten können Sie den lokalen Computer und den Remote Computer vor übermäßig hoher Ressourcenverwendung (versehentlich und bösartig) schützen.</span><span class="sxs-lookup"><span data-stu-id="96532-286">You can use quotas to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span>

<span data-ttu-id="96532-287">Die folgenden Kontingente sind in der grundlegenden Konfiguration verfügbar.</span><span class="sxs-lookup"><span data-stu-id="96532-287">The following quotas are available in the basic configuration.</span></span>

- <span data-ttu-id="96532-288">Der WSMAN-Anbieter (WSMAN:) bietet mehrere Kontingent Einstellungen, wie z. b. die Einstellungen **maxenvelopesizekb** und **maxproviderrequests** im `WSMan:<ComputerName>` Knoten und die Einstellungen **maxconcurrentoperations** , **maxconcurrentoperationsperuser** und **MaxConnections** im `WSMan:<ComputerName>\Service` Knoten.</span><span class="sxs-lookup"><span data-stu-id="96532-288">The WSMan provider (WSMan:) provides several quota settings, such as the **MaxEnvelopeSizeKB** and **MaxProviderRequests** settings in the `WSMan:<ComputerName>` node and the **MaxConcurrentOperations** , **MaxConcurrentOperationsPerUser** , and **MaxConnections** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="96532-289">Sie können den lokalen Computer mit den Parametern **maximumreceiveddatasizepercommand** und **maximumreceivedobjectsize** des `New-PSSessionOption` Cmdlets und der Preference- `$PSSessionOption` Variablen schützen.</span><span class="sxs-lookup"><span data-stu-id="96532-289">You can protect the local computer by using the **MaximumReceivedDataSizePerCommand** and **MaximumReceivedObjectSize** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="96532-290">Sie können den Remote Computer schützen, indem Sie den Sitzungs Konfigurationen Einschränkungen hinzufügen, z. b. mit den Parametern **maximumreceiveddatasizepercommandmb** und **maximumreceivedobjectsizemb** des `Register-PSSessionConfiguration` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="96532-290">You can protect the remote computer by adding restrictions to the session configurations, such as by using the **MaximumReceivedDataSizePerCommandMB** and **MaximumReceivedObjectSizeMB** parameters of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="96532-291">Wenn Kontingente mit einem Befehl in Konflikt stehen, generiert PowerShell einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="96532-291">When quotas conflict with a command, PowerShell generates an error.</span></span>

<span data-ttu-id="96532-292">Um den Fehler zu beheben, ändern Sie den Remote Befehl so, dass er dem Kontingent entspricht.</span><span class="sxs-lookup"><span data-stu-id="96532-292">To resolve the error, change the remote command to comply with the quota.</span></span> <span data-ttu-id="96532-293">Sie können auch die Quelle des Kontingents ermitteln und dann das Kontingent erhöhen, um den Abschluss des Befehls zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="96532-293">Or, determine the source of the quota, and then increase the quota to allow the command to complete.</span></span>

<span data-ttu-id="96532-294">Der folgende Befehl erhöht z. b. das Objektgrößen Kontingent in der Microsoft. PowerShell-Sitzungs Konfiguration auf dem Remote Computer von 10 MB (Standardwert) auf 11 MB.</span><span class="sxs-lookup"><span data-stu-id="96532-294">For example, the following command increases the object size quota in the Microsoft.PowerShell session configuration on the remote computer from 10 MB (the default value) to 11 MB.</span></span>

```powershell
Set-PSSessionConfiguration -Name microsoft.PowerShell `
  -MaximumReceivedObjectSizeMB 11 -Force
```

<span data-ttu-id="96532-295">Weitere Informationen zum- `New-PSSessionOption` Cmdlet finden Sie unter `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="96532-295">For more information about the `New-PSSessionOption` cmdlet, see `New-PSSessionOption`.</span></span>

<span data-ttu-id="96532-296">Weitere Informationen zu den WS-Management Kontingenten finden Sie unter [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="96532-296">For more information about the WS-Management quotas, see [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).</span></span>

### <a name="how-to-resolve-timeout-errors"></a><span data-ttu-id="96532-297">Auflösen von Timeout Fehlern</span><span class="sxs-lookup"><span data-stu-id="96532-297">How to resolve timeout errors</span></span>

```
ERROR: The WS-Management service cannot complete the operation within
the time specified in OperationTimeout.
```

<span data-ttu-id="96532-298">Sie können Timeouts verwenden, um den lokalen Computer und den Remote Computer vor übermäßig hoher Ressourcenverwendung zu schützen, sowohl versehentlich als auch bösartig.</span><span class="sxs-lookup"><span data-stu-id="96532-298">You can use timeouts to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span> <span data-ttu-id="96532-299">Wenn Timeouts auf dem lokalen Computer und auf dem Remote Computer festgelegt sind, verwendet PowerShell die kürzesten Timeout Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="96532-299">When timeouts are set on both the local and remote computer, PowerShell uses the shortest timeout settings.</span></span>

<span data-ttu-id="96532-300">Die folgenden Timeouts sind in der grundlegenden Konfiguration verfügbar.</span><span class="sxs-lookup"><span data-stu-id="96532-300">The following timeouts are available in the basic configuration.</span></span>

- <span data-ttu-id="96532-301">Der WSMAN-Anbieter (WSMAN:) bietet mehrere Client seitige und Dienst seitige Timeout Einstellungen, wie z. b. die Einstellung **maxtimeoutms** im `WSMan:<ComputerName>` Knoten und die Einstellungen **enumerationtimeoutms** und **maxpacketretrievaltimeseconds** im `WSMan:<ComputerName>\Service` Knoten.</span><span class="sxs-lookup"><span data-stu-id="96532-301">The WSMan provider (WSMan:) provides several client-side and service-side timeout settings, such as the **MaxTimeoutms** setting in the `WSMan:<ComputerName>` node and the **EnumerationTimeoutms** and **MaxPacketRetrievalTimeSeconds** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="96532-302">Sie können den lokalen Computer mit den Parametern **canceltimeout** , **IdleTimeout** , **OpenTimeout** und **OperationTimeout** des `New-PSSessionOption` Cmdlets und der `$PSSessionOption` Preference-Variablen schützen.</span><span class="sxs-lookup"><span data-stu-id="96532-302">You can protect the local computer by using the **CancelTimeout** , **IdleTimeout** , **OpenTimeout** , and **OperationTimeout** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="96532-303">Sie können den Remote Computer auch schützen, indem Sie Timeout Werte Programm gesteuert in der Sitzungs Konfiguration für die Sitzung festlegen.</span><span class="sxs-lookup"><span data-stu-id="96532-303">You can also protect the remote computer by setting timeout values programmatically in the session configuration for the session.</span></span>

<span data-ttu-id="96532-304">Wenn ein Timeout Wert keinen Vorgang zulässt, beendet PowerShell den Vorgang und generiert einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="96532-304">When a timeout value does not permit a operation to complete, PowerShell terminates the operation and generates an error.</span></span>

<span data-ttu-id="96532-305">Um den Fehler zu beheben, ändern Sie den Befehl innerhalb des Timeout Intervalls in "Fertigstellen", oder ermitteln Sie die Quelle des Timeout Limits, und erhöhen Sie das Timeout Intervall, um den Abschluss des Befehls zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="96532-305">To resolve the error, change the command to complete within the timeout interval or determine the source of the timeout limit and increase the timeout interval to allow the command to complete.</span></span>

<span data-ttu-id="96532-306">Beispielsweise verwenden die folgenden Befehle das- `New-PSSessionOption` Cmdlet, um ein Sitzungs Options Objekt mit einem **OperationTimeout** -Wert von 4 Minuten (in MS) zu erstellen, und verwenden dann das Sitzungs Options Objekt, um eine Remote Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="96532-306">For example, the following commands use the `New-PSSessionOption` cmdlet to create a session option object with an **OperationTimeout** value of 4 minutes (in MS) and then use the session option object to create a remote session.</span></span>

```powershell
$pso = New-PSSessionoption -OperationTimeout 240000

New-PSSession -ComputerName Server01 -sessionOption $pso
```

<span data-ttu-id="96532-307">Weitere Informationen zu den WS-Management Timeouts finden Sie im Hilfethema für den WSMAN-Anbieter (Type `Get-Help WSMan` ).</span><span class="sxs-lookup"><span data-stu-id="96532-307">For more information about the WS-Management timeouts, see the Help topic for the WSMan provider (type `Get-Help WSMan`).</span></span>

<span data-ttu-id="96532-308">Weitere Informationen zum `New-PSSessionOption` Cmdlet finden Sie unter [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="96532-308">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

## <a name="troubleshooting-unresponsive-behavior"></a><span data-ttu-id="96532-309">Behandeln von nicht reagierenden Verhalten</span><span class="sxs-lookup"><span data-stu-id="96532-309">Troubleshooting unresponsive behavior</span></span>

<span data-ttu-id="96532-310">In diesem Abschnitt werden Remoting-Probleme erläutert, die verhindern, dass ein Befehl abgeschlossen wird, und die Rückgabe der PowerShell-Eingabeaufforderung verhindern oder verzögern.</span><span class="sxs-lookup"><span data-stu-id="96532-310">This section discusses remoting problems that prevent a command from completing and prevent or delay the return of the PowerShell prompt.</span></span>

### <a name="how-to-interrupt-a-command"></a><span data-ttu-id="96532-311">Vorgehensweise beim Unterbrechen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="96532-311">How to interrupt a command</span></span>

<span data-ttu-id="96532-312">Einige systemeigene Windows-Programme, z. b. Programme mit einer Benutzeroberfläche, Konsolen Anwendungen, die Eingabeaufforderung anfordern, und Konsolen Anwendungen, die die Win32-Konsolen-API verwenden, funktionieren im PowerShell-Remote Host nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="96532-312">Some native Windows programs, such as programs with a user interface, console applications that prompt for input, and console applications that use the Win32 console API, do not work correctly in the PowerShell remote host.</span></span>

<span data-ttu-id="96532-313">Wenn Sie diese Programme verwenden, wird möglicherweise ein unerwartetes Verhalten angezeigt, wie z. b. keine Ausgabe, partielle Ausgabe oder Remote Befehl, der nicht vollständig ist.</span><span class="sxs-lookup"><span data-stu-id="96532-313">When you use these programs, you might see unexpected behavior, such as no output, partial output, or a remote command that does not complete.</span></span>

<span data-ttu-id="96532-314">Um ein nicht reagierendes Programm zu beenden, geben Sie <kbd>STRG</kbd> + <kbd>C</kbd>ein.</span><span class="sxs-lookup"><span data-stu-id="96532-314">To end an unresponsive program, type <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="96532-315">Wenn Sie eventuell gemeldete Fehler anzeigen möchten, geben Sie `$error` den lokalen Host und die Remote Sitzung ein.</span><span class="sxs-lookup"><span data-stu-id="96532-315">To view any errors that might have been reported, type `$error` in the local host and the remote session.</span></span>

## <a name="how-to-recover-from-an-operation-failure"></a><span data-ttu-id="96532-316">Vorgehensweise beim Wiederherstellen nach einem Vorgangs Fehler</span><span class="sxs-lookup"><span data-stu-id="96532-316">How to recover from an operation failure</span></span>

```
ERROR: The I/O operation has been aborted because of either a thread exit
or an  application request.
```

<span data-ttu-id="96532-317">Dieser Fehler wird zurückgegeben, wenn ein Vorgang beendet wird, bevor er abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="96532-317">This error is returned when an operation is terminated before it completes.</span></span>
<span data-ttu-id="96532-318">Dies tritt normalerweise auf, wenn der WinRM-Dienst beendet oder neu gestartet wird, während andere WinRM-Vorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="96532-318">Typically, it occurs when the WinRM service stops or restarts while other WinRM operations are in progress.</span></span>

<span data-ttu-id="96532-319">Um dieses Problem zu beheben, überprüfen Sie, ob der WinRM-Dienst ausgeführt wird, und wiederholen Sie den Befehl.</span><span class="sxs-lookup"><span data-stu-id="96532-319">To resolve this issue, verify that the WinRM service is running and try the command again.</span></span>

1. <span data-ttu-id="96532-320">Starten Sie PowerShell mit der Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="96532-320">Start PowerShell with the **Run as administrator** option.</span></span>
1. <span data-ttu-id="96532-321">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="96532-321">Run the following command:</span></span>

   `Start-Service WinRM`

1. <span data-ttu-id="96532-322">Führen Sie den Befehl erneut aus, der den Fehler generiert hat.</span><span class="sxs-lookup"><span data-stu-id="96532-322">Re-run the command that generated the error.</span></span>

## <a name="linux-and-macos-limitations"></a><span data-ttu-id="96532-323">Einschränkungen für Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="96532-323">Linux and macOS limitations</span></span>

### <a name="authentication"></a><span data-ttu-id="96532-324">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="96532-324">Authentication</span></span>

<span data-ttu-id="96532-325">Nur die Standard Authentifizierung funktioniert unter macOS und der Versuch, andere Authentifizierungs Schemas zu verwenden, kann dazu führen, dass der Prozess abstürzt.</span><span class="sxs-lookup"><span data-stu-id="96532-325">Only basic authentication works on macOS and attempting to use other authentication schemes may result in the process crashing.</span></span>

<span data-ttu-id="96532-326">Weitere Informationen finden Sie in den Anweisungen zur [Omi-Authentifizierung](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) .</span><span class="sxs-lookup"><span data-stu-id="96532-326">Please see the [OMI authentication](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="96532-327">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="96532-327">SEE ALSO</span></span>

[<span data-ttu-id="96532-328">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="96532-328">Import-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Import-PSSession)

[<span data-ttu-id="96532-329">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="96532-329">Export-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Export-PSSession)

[<span data-ttu-id="96532-330">Import-Module</span><span class="sxs-lookup"><span data-stu-id="96532-330">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="96532-331">about_Remote</span><span class="sxs-lookup"><span data-stu-id="96532-331">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="96532-332">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="96532-332">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="96532-333">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="96532-333">about_Remote_Variables</span></span>](about_Remote_Variables.md)
