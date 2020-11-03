---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: b51d5c2d21734a8db31a6e257579cca68809ebc5
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210996"
---
# <span data-ttu-id="4cb85-103">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="4cb85-103">Disable-PSRemoting</span></span>

## <span data-ttu-id="4cb85-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4cb85-104">SYNOPSIS</span></span>
<span data-ttu-id="4cb85-105">Verhindert, dass PowerShell-Endpunkte Remote Verbindungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-105">Prevents PowerShell endpoints from receiving remote connections.</span></span>

## <span data-ttu-id="4cb85-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4cb85-106">SYNTAX</span></span>

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4cb85-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4cb85-107">DESCRIPTION</span></span>

<span data-ttu-id="4cb85-108">`Disable-PSRemoting`Mit dem-Cmdlet wird der Remote Zugriff auf alle PowerShell-Konfigurationen, Version 6, und eine größere Sitzungs Endpunkt Konfiguration auf dem lokalen Computer blockiert.</span><span class="sxs-lookup"><span data-stu-id="4cb85-108">The `Disable-PSRemoting` cmdlet blocks remote access to all PowerShell version 6 and greater session endpoint configurations on the local computer.</span></span> <span data-ttu-id="4cb85-109">Es wirkt sich nicht auf Windows PowerShell-Endpunkt Konfigurationen aus.</span><span class="sxs-lookup"><span data-stu-id="4cb85-109">It does not affect Windows PowerShell endpoint configurations.</span></span> <span data-ttu-id="4cb85-110">Zum Deaktivieren der Konfigurationen von Windows PowerShell-Sitzungs Endpunkten führen Sie den `Disable-PSRemoting` Befehl in einer Windows PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="4cb85-110">To disable Windows PowerShell session endpoint configurations, run `Disable-PSRemoting` command from within a Windows PowerShell session.</span></span>

<span data-ttu-id="4cb85-111">Verwenden Sie das-Cmdlet, um den Remote Zugriff auf alle PowerShell-Konfigurationen der Version 6 und einer größeren Sitzungs Endpunkt-Konfiguration wieder zu aktivieren `Enable-PSRemoting` .</span><span class="sxs-lookup"><span data-stu-id="4cb85-111">To re-enable remote access to all PowerShell version 6 and greater session endpoint configurations, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="4cb85-112">Um den Remote Zugriff auf alle Konfigurationen von Windows PowerShell-Sitzungs Endpunkten wieder zu aktivieren, führen Sie `Enable-PSRemoting` in einer Windows PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="4cb85-112">To re-enable remote access to all Windows PowerShell session endpoint configurations, run `Enable-PSRemoting` from within a Windows PowerShell session.</span></span>

> [!NOTE]
> <span data-ttu-id="4cb85-113">Wenn Sie den gesamten PowerShell-Remote Zugriff auf einen lokalen Windows-Computer deaktivieren möchten, müssen Sie diesen Befehl sowohl innerhalb von PowerShell, Version 6 oder höher, als auch innerhalb einer Windows PowerShell-Sitzung ausführen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-113">If you want to disable all PowerShell remote access to a local Windows machine, you must run this command both from a within PowerShell version 6 or greater session and from within a Windows PowerShell session.</span></span> <span data-ttu-id="4cb85-114">Windows PowerShell ist standardmäßig auf allen Windows-Computern installiert.</span><span class="sxs-lookup"><span data-stu-id="4cb85-114">Windows PowerShell is installed on all Windows machines by default.</span></span>

<span data-ttu-id="4cb85-115">Verwenden Sie die `Enable-PSSessionConfiguration` Cmdlets und, um den Remote Zugriff auf bestimmte Sitzungs Endpunkt Konfigurationen zu deaktivieren und erneut zu aktivieren `Disable-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="4cb85-115">To disable and re-enable remote access to specific session endpoint configurations, use the `Enable-PSSessionConfiguration` and `Disable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="4cb85-116">Um spezifische Zugriffs Konfigurationen einzelner Endpunkte festzulegen, verwenden Sie das `Set-PSSessionConfiguration` Cmdlet zusammen mit dem **AccessMode** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="4cb85-116">To set specific access configurations of individual endpoints, use the `Set-PSSessionConfiguration` cmdlet along with the **AccessMode** parameter.</span></span> <span data-ttu-id="4cb85-117">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="4cb85-117">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4cb85-118">Auch nach `Disable-PSRemoting` der Ausführung können Sie Loopback Verbindungen auf dem lokalen Computer durchführen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-118">Even after running `Disable-PSRemoting` you can still make loopback connections on the local machine.</span></span> <span data-ttu-id="4cb85-119">Eine Loopback Verbindung ist eine PowerShell-Remote Sitzung, die aus stammt und eine Verbindung mit dem gleichen lokalen Computer herstellt.</span><span class="sxs-lookup"><span data-stu-id="4cb85-119">A loopback connection is a PowerShell remote session that originates from and connects to the same local machine.</span></span> <span data-ttu-id="4cb85-120">Remote Sitzungen aus externen Quellen bleiben blockiert.</span><span class="sxs-lookup"><span data-stu-id="4cb85-120">Remote sessions from external sources remain blocked.</span></span> <span data-ttu-id="4cb85-121">Für Loopback Verbindungen müssen Sie die impliziten Anmelde Informationen für den **enablenetworkaccess** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cb85-121">For loopback connections you must use implicit credentials along the **EnableNetworkAccess** parameter.</span></span> <span data-ttu-id="4cb85-122">Weitere Informationen zu Loopback Verbindungen finden Sie unter [New-PSSession](New-PSSession.md).</span><span class="sxs-lookup"><span data-stu-id="4cb85-122">For more information about loopback connections, see [New-PSSession](New-PSSession.md).</span></span>

<span data-ttu-id="4cb85-123">Dieses Cmdlet ist nur auf der Windows-Plattform verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4cb85-123">This cmdlet is only available on the Windows platform.</span></span> <span data-ttu-id="4cb85-124">Sie ist unter Linux-oder macOS-Versionen von PowerShell nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4cb85-124">It is not available on Linux or macOS versions of PowerShell.</span></span> <span data-ttu-id="4cb85-125">Starten Sie PowerShell mit der Option **als Administrator ausführen** , um dieses Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-125">To run this cmdlet, start PowerShell with the **Run as administrator** option.</span></span>

## <span data-ttu-id="4cb85-126">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4cb85-126">EXAMPLES</span></span>

### <span data-ttu-id="4cb85-127">Beispiel 1: verhindern des Remote Zugriffs auf alle PowerShell-Sitzungs Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="4cb85-127">Example 1: Prevent remote access to all PowerShell session configurations</span></span>

<span data-ttu-id="4cb85-128">In diesem Beispiel wird der Remote Zugriff auf alle PowerShell-Sitzungs Endpunkt Konfigurationen auf dem Computer verhindert.</span><span class="sxs-lookup"><span data-stu-id="4cb85-128">This example prevents remote access to all PowerShell session endpoint configurations on the computer.</span></span>

```powershell
Disable-PSRemoting
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="4cb85-129">Beispiel 2: verhindern des Remote Zugriffs auf alle PowerShell-Sitzungs Konfigurationen ohne Bestätigungsaufforderung</span><span class="sxs-lookup"><span data-stu-id="4cb85-129">Example 2: Prevent remote access to all PowerShell session configurations without confirmation prompt</span></span>

<span data-ttu-id="4cb85-130">In diesem Beispiel wird der Remote Zugriff auf alle PowerShell-Sitzungs Endpunkt Konfigurationen auf dem Computer ohne Eingabeaufforderung verhindert.</span><span class="sxs-lookup"><span data-stu-id="4cb85-130">This example prevents remote access all PowerShell session endpoint configurations on the computer without prompting.</span></span>

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="4cb85-131">Beispiel 3: Auswirkungen der Ausführung dieses Cmdlets</span><span class="sxs-lookup"><span data-stu-id="4cb85-131">Example 3: Effects of running this cmdlet</span></span>

<span data-ttu-id="4cb85-132">In diesem Beispiel werden die Auswirkungen der Verwendung des- `Disable-PSRemoting` Cmdlets veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4cb85-132">This example shows the effect of using the `Disable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="4cb85-133">Starten Sie PowerShell mit der Option **als Administrator ausführen** , um diese Befehlssequenz auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-133">To run this command sequence, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="4cb85-134">Nachdem Sie die Sitzungs Konfigurationen deaktiviert haben, `New-PSSession` versucht das Cmdlet, eine Remote Sitzung mit dem lokalen Computer (auch als "Loopback" bezeichnet) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-134">After disabling the sessions configurations, the `New-PSSession` cmdlet attempts to create a remote session to the local computer (also known as a "loopback").</span></span> <span data-ttu-id="4cb85-135">Da der Remote Zugriff auf dem lokalen Computer deaktiviert ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="4cb85-135">Because remote access is disabled on the local machine, the command fails.</span></span>

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error
 message : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

### <span data-ttu-id="4cb85-136">Beispiel 4: Auswirkungen der Ausführung dieses Cmdlets und Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="4cb85-136">Example 4: Effects of running this cmdlet and Enable-PSRemoting</span></span>

<span data-ttu-id="4cb85-137">Dieses Beispiel zeigt die Auswirkung auf die Sitzungs Konfigurationen von mithilfe der `Disable-PSRemoting` `Enable-PSRemoting` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="4cb85-137">This example shows the effect on the session configurations of using the `Disable-PSRemoting` and `Enable-PSRemoting` cmdlets.</span></span>

<span data-ttu-id="4cb85-138">`Disable-PSRemoting` wird verwendet, um den Remote Zugriff auf alle Konfigurationen von PowerShell-Sitzungs Endpunkten zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4cb85-138">`Disable-PSRemoting` is used to disable remote access to all PowerShell session endpoint configurations.</span></span> <span data-ttu-id="4cb85-139">Mit dem **Force** -Parameter werden alle Eingabeaufforderungen unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="4cb85-139">The **Force** parameter suppresses all user prompts.</span></span> <span data-ttu-id="4cb85-140">`Get-PSSessionConfiguration`Mit den-und- `Format-Table` Cmdlets werden die Sitzungs Konfigurationen auf dem Computer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4cb85-140">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations on the computer.</span></span>

<span data-ttu-id="4cb85-141">Die Ausgabe zeigt, dass allen Remote Benutzern mit einem Netzwerk Token der Zugriff auf die Endpunkt Konfigurationen verweigert wird.</span><span class="sxs-lookup"><span data-stu-id="4cb85-141">The output shows that all remote users with a network token are denied access to the endpoint configurations.</span></span> <span data-ttu-id="4cb85-142">Die Gruppe "Administratoren" auf dem lokalen Computer verfügt über Zugriff auf die Endpunkt Konfigurationen, solange Sie lokal (auch als Loopback bezeichnet) eine Verbindung herstellen und implizite Anmelde Informationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cb85-142">Administrators group on the local computer are allowed access to the endpoint configurations as long as they are connecting locally (also known as loopback) and using implicit credentials.</span></span>

```powershell
Disable-PSRemoting -force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Enable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
PowerShell.6.2.0   NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...

Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
PowerShell.6.2.0   NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
```

<span data-ttu-id="4cb85-143">Mit dem `Enable-PSRemoting` -Cmdlet wird der Remote Zugriff auf alle PowerShell-Sitzungs Endpunkt Konfigurationen auf dem Computer erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4cb85-143">The `Enable-PSRemoting` cmdlet re-enables remote access to all PowerShell session endpoint configurations on the computer.</span></span> <span data-ttu-id="4cb85-144">Der **Force** -Parameter unterdrückt alle Benutzer Aufforderungen und startet den WinRM-Dienst ohne Aufforderung neu.</span><span class="sxs-lookup"><span data-stu-id="4cb85-144">The **Force** parameter suppresses all user prompts and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="4cb85-145">Die neue Ausgabe zeigt, dass die **AccessDenied** -Sicherheits Beschreibungen aus allen Sitzungs Konfigurationen entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="4cb85-145">The new output shows that the **AccessDenied** security descriptors have been removed from all session configurations.</span></span>

### <span data-ttu-id="4cb85-146">Beispiel 5: Loopback Verbindungen mit deaktivierten Sitzungs Endpunkt Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="4cb85-146">Example 5: Loopback connections with disabled session endpoint configurations</span></span>

<span data-ttu-id="4cb85-147">In diesem Beispiel wird veranschaulicht, wie Endpunkt Konfigurationen deaktiviert werden, und es wird gezeigt, wie Sie eine erfolgreiche Loopback Verbindung mit einem deaktivierten Endpunkt herstellen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-147">This example demonstrates how endpoint configurations are disabled, and shows how to make a successful loopback connection to a disabled endpoint.</span></span> <span data-ttu-id="4cb85-148">`Disable-PSRemoting` deaktiviert alle PowerShell-Sitzungs Endpunkt Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-148">`Disable-PSRemoting` disables all PowerShell session endpoint configurations.</span></span>

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

```powershell
New-PSSession -ComputerName localhost -ConfigurationName powershell.6 -Credential (Get-Credential)
```

```Output
PowerShell credential request
Enter your credentials.
User: UserName
Password for user UserName: ************

New-PSSession: [localhost] Connecting to remote server localhost failed with the following error message
 : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
```

```powershell
New-PSSession -ComputerName localhost -ConfigurationName powershell.6 -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

<span data-ttu-id="4cb85-149">Bei der ersten Verwendung von wird `New-PSSession` versucht, eine Remote Sitzung mit dem lokalen Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-149">The first use of `New-PSSession` attempts to create a remote session to the local machine.</span></span> <span data-ttu-id="4cb85-150">Der **ConfigurationName** -Parameter wird verwendet, um einen deaktivierten PowerShell-Endpunkt anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4cb85-150">The **ConfigurationName** parameter is used to specify a disabled PowerShell endpoint.</span></span> <span data-ttu-id="4cb85-151">Anmelde Informationen werden explizit über den **Credential** -Parameter an den Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="4cb85-151">Credentials are explicitly passed to the command through the **Credential** parameter.</span></span> <span data-ttu-id="4cb85-152">Dieser Verbindungstyp wird durch den Netzwerk Stapel geleitet und ist kein Loopback.</span><span class="sxs-lookup"><span data-stu-id="4cb85-152">This type of connection goes through the network stack and is not a loopback.</span></span> <span data-ttu-id="4cb85-153">Folglich schlägt der Verbindungsversuch mit dem deaktivierten Endpunkt mit dem Fehler " **Zugriff verweigert** " fehl.</span><span class="sxs-lookup"><span data-stu-id="4cb85-153">Consequently, the connection attempt to the disabled endpoint fails with an **Access is denied** error.</span></span>

<span data-ttu-id="4cb85-154">Bei der zweiten Verwendung von wird `New-PSSession` auch versucht, eine Remote Sitzung mit dem lokalen Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-154">The second use of `New-PSSession` also attempts to create a remote session to the local machine.</span></span>
<span data-ttu-id="4cb85-155">In diesem Fall ist dies erfolgreich, weil es sich um eine Loopback Verbindung handelt, die den Netzwerk Stapel umgeht.</span><span class="sxs-lookup"><span data-stu-id="4cb85-155">In this case, it succeeds because it is a loopback connection that bypasses the network stack.</span></span>

<span data-ttu-id="4cb85-156">Eine Loopback Verbindung wird erstellt, wenn die folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="4cb85-156">A loopback connection is created when the following conditions are met:</span></span>

- <span data-ttu-id="4cb85-157">Der Computername, mit dem eine Verbindung hergestellt werden soll, ist "localhost".</span><span class="sxs-lookup"><span data-stu-id="4cb85-157">The computer name to connect to is 'localhost'.</span></span>
- <span data-ttu-id="4cb85-158">Es werden keine Anmelde Informationen übermittelt.</span><span class="sxs-lookup"><span data-stu-id="4cb85-158">No credentials are passed in.</span></span> <span data-ttu-id="4cb85-159">Der aktuell angemeldete Benutzer (implizite Anmelde Informationen) wird für die Verbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cb85-159">Current logged in user (implicit credentials) is used for the connection.</span></span>
- <span data-ttu-id="4cb85-160">Der **enablenetworkaccess** -Schalter Parameter wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cb85-160">The **EnableNetworkAccess** switch parameter is used.</span></span>

<span data-ttu-id="4cb85-161">Weitere Informationen zu Loopback Verbindungen finden Sie im Dokument [New-PSSession](New-PSSession.md) .</span><span class="sxs-lookup"><span data-stu-id="4cb85-161">For more information on loopback connections, see [New-PSSession](New-PSSession.md) document.</span></span>

### <span data-ttu-id="4cb85-162">Beispiel 6: Deaktivieren aller PowerShell-Remoting-Endpunkt Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="4cb85-162">Example 6: Disabling all PowerShell remoting endpoint configurations</span></span>

<span data-ttu-id="4cb85-163">In diesem Beispiel wird veranschaulicht, wie die Ausführung des `Disable-PSRemoting` Befehls keine Auswirkungen auf Windows PowerShell-Endpunkt Konfigurationen hat.</span><span class="sxs-lookup"><span data-stu-id="4cb85-163">This example demonstrates how running the `Disable-PSRemoting` command does not affect Windows PowerShell endpoint configurations.</span></span> <span data-ttu-id="4cb85-164">`Get-PSSessionConfiguration` in Windows PowerShell ausführen werden alle Endpunkt Konfigurationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4cb85-164">`Get-PSSessionConfiguration` run within Windows PowerShell shows all endpoint configurations.</span></span> <span data-ttu-id="4cb85-165">Wir sehen, dass die Windows PowerShell-Endpunkt Konfigurationen nicht deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="4cb85-165">We see that the Windows PowerShell endpoint configurations are not disabled.</span></span>

```powershell
Disable-PSRemoting -Force
powershell.exe -command 'Get-PSSessionConfiguration'
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name          : microsoft.powershell
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote
                Management Users AccessAllowed

Name          : microsoft.powershell.workflow
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : microsoft.powershell32
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote
                Management Users AccessAllowed

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

```powershell
powershell.exe -command 'Disable-PSRemoting -Force'
powershell.exe -command 'Get-PSSessionConfiguration'
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting or
Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the
Administrators group on the computer.

Name          : microsoft.powershell
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : microsoft.powershell.workflow
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management
                Users AccessAllowed

Name          : microsoft.powershell32
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

<span data-ttu-id="4cb85-166">Um diese Endpunkt Konfigurationen zu deaktivieren, `Disable-PSRemoting` muss der Befehl innerhalb einer Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4cb85-166">To disable these endpoint configurations, the `Disable-PSRemoting` command must be run from within a Windows PowerShell session.</span></span> <span data-ttu-id="4cb85-167">Jetzt können Sie `Get-PSSessionConfiguration` in Windows PowerShell ausführen, um zu sehen, dass alle Endpunkt Konfigurationen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="4cb85-167">Now, `Get-PSSessionConfiguration` run from within Windows PowerShell shows that all endpoint configurations are disabled.</span></span>

### <span data-ttu-id="4cb85-168">Beispiel 7: verhindern des Remote Zugriffs auf Sitzungs Konfigurationen mit benutzerdefinierten Sicherheits Deskriptoren</span><span class="sxs-lookup"><span data-stu-id="4cb85-168">Example 7: Prevent remote access to session configurations that have custom security descriptors</span></span>

<span data-ttu-id="4cb85-169">Dieses Beispiel zeigt, dass das `Disable-PSRemoting` Cmdlet den Remote Zugriff auf alle Sitzungs Konfigurationen deaktiviert, die Sitzungs Konfigurationen mit benutzerdefinierten Sicherheits Beschreibungen einschließen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-169">This example demonstrates that the `Disable-PSRemoting` cmdlet disables remote access to all session configurations that include session configurations with custom security descriptors.</span></span>

<span data-ttu-id="4cb85-170">`Register-PSSessionConfiguration` erstellt die **Test** Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="4cb85-170">`Register-PSSessionConfiguration` creates the **Test** session configuration.</span></span> <span data-ttu-id="4cb85-171">Der **FilePath** -Parameter gibt eine Sitzungs Konfigurationsdatei an, die die Sitzung anpasst.</span><span class="sxs-lookup"><span data-stu-id="4cb85-171">The **FilePath** parameter specifies a session configuration file that customizes the session.</span></span> <span data-ttu-id="4cb85-172">Der **showsecuritydescriptorui** -Parameter zeigt ein Dialogfeld an, in dem Berechtigungen für die Sitzungs Konfiguration festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4cb85-172">The **ShowSecurityDescriptorUI** parameter displays a dialog box that sets permissions for the session configuration.</span></span> <span data-ttu-id="4cb85-173">Im Dialogfeld "Berechtigungen" erstellen wir benutzerdefinierte voll Zugriffsberechtigungen für den angezeigten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4cb85-173">In the Permissions dialog box, we create custom full-access permissions for the indicated user.</span></span>

<span data-ttu-id="4cb85-174">Die `Get-PSSessionConfiguration` -und- `Format-Table` Cmdlets zeigen die Sitzungs Konfigurationen und deren Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="4cb85-174">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations and their properties.</span></span> <span data-ttu-id="4cb85-175">Die Ausgabe zeigt, dass die **Test** Sitzungs Konfiguration interaktiven Zugriff und spezielle Berechtigungen für den Benutzer ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="4cb85-175">The output shows that the **Test** session configuration allows interactive access and special permissions for the indicated user.</span></span>

<span data-ttu-id="4cb85-176">`Disable-PSRemoting` deaktiviert den Remote Zugriff auf alle Sitzungs Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-176">`Disable-PSRemoting` disables remote access to all session configurations.</span></span>

```powershell
Register-PSSessionConfiguration -Name Test -FilePath .\TestEndpoint.pssc -ShowSecurityDescriptorUI -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap

Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap
New-PSSession -ComputerName localhost -ConfigurationName Test
```

```Output
Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   BUILTIN\Remote Management Users AccessAllowed
PowerShell.6.2.0   NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   BUILTIN\Remote Management Users AccessAllowed
Test               NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
PowerShell.6.2.0   NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
Test               NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, User01 AccessAllowed

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message
 : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName Test
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

<span data-ttu-id="4cb85-177">Die `Get-PSSessionConfiguration` `Format-Table` Cmdlets und zeigen nun, dass allen Sitzungs Konfigurationen, einschließlich der **Test** Sitzungs Konfiguration, eine **AccessDenied** -Sicherheits Beschreibung für alle Netzwerk Benutzer hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4cb85-177">Now the `Get-PSSessionConfiguration` and `Format-Table` cmdlets shows that an **AccessDenied** security descriptor for all network users is added to all session configurations, including the **Test** session configuration.</span></span> <span data-ttu-id="4cb85-178">Obwohl die anderen Sicherheits Deskriptoren nicht geändert werden, hat der Sicherheits Deskriptor "network_deny_all" Vorrang.</span><span class="sxs-lookup"><span data-stu-id="4cb85-178">Although the other security descriptors are not changed, the "network_deny_all" security descriptor takes precedence.</span></span> <span data-ttu-id="4cb85-179">Dies wird durch den Versuch veranschaulicht, zu verwenden, `New-PSSession` um eine Verbindung mit der **Test** Sitzungs Konfiguration herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-179">This is illustrated by the attempt to use `New-PSSession` to connect to the **Test** session configuration.</span></span>

### <span data-ttu-id="4cb85-180">Beispiel 8: Erneutes Aktivieren des Remote Zugriffs auf ausgewählte Sitzungs Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="4cb85-180">Example 8: Re-enable remote access to selected session configurations</span></span>

<span data-ttu-id="4cb85-181">In diesem Beispiel wird veranschaulicht, wie der Remotezugriff nur auf ausgewählte Sitzungskonfigurationen erneut aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="4cb85-181">This example shows how to re-enable remote access only to selected session configurations.</span></span> <span data-ttu-id="4cb85-182">Nachdem Sie alle Sitzungs Konfigurationen deaktiviert haben, aktivieren wir eine bestimmte Sitzung erneut.</span><span class="sxs-lookup"><span data-stu-id="4cb85-182">After disabling all session configurations, we re-enable a specific session.</span></span>

<span data-ttu-id="4cb85-183">Das- `Set-PSSessionConfiguration` Cmdlet wird verwendet, um die Konfiguration der **PowerShell. 6** -Sitzung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4cb85-183">The `Set-PSSessionConfiguration` cmdlet is used to change the **PowerShell.6** session configuration.</span></span> <span data-ttu-id="4cb85-184">Der **AccessMode** -Parameter mit dem Wert **Remote** aktiviert den Remote Zugriff auf die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="4cb85-184">The **AccessMode** parameter with a value of **Remote** re-enables remote access to the configuration.</span></span>

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name PowerShell.6 -AccessMode Remote -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                 Permission
----                 ----------
PowerShell.6         NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...
PowerShell.6.2.0     NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...

Name                 Permission
----                 ----------
PowerShell.6         NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\ ...
PowerShell.6.2.0     NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...
```

## <span data-ttu-id="4cb85-185">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4cb85-185">PARAMETERS</span></span>

### <span data-ttu-id="4cb85-186">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4cb85-186">-Confirm</span></span>

<span data-ttu-id="4cb85-187">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="4cb85-187">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4cb85-188">-Force</span><span class="sxs-lookup"><span data-stu-id="4cb85-188">-Force</span></span>

<span data-ttu-id="4cb85-189">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4cb85-189">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="4cb85-190">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4cb85-190">-WhatIf</span></span>

<span data-ttu-id="4cb85-191">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4cb85-191">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="4cb85-192">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4cb85-192">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4cb85-193">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4cb85-193">CommonParameters</span></span>

<span data-ttu-id="4cb85-194">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4cb85-194">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4cb85-195">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4cb85-195">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4cb85-196">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4cb85-196">INPUTS</span></span>

### <span data-ttu-id="4cb85-197">Keine</span><span class="sxs-lookup"><span data-stu-id="4cb85-197">None</span></span>

<span data-ttu-id="4cb85-198">Sie können keine Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="4cb85-198">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="4cb85-199">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4cb85-199">OUTPUTS</span></span>

### <span data-ttu-id="4cb85-200">Keine</span><span class="sxs-lookup"><span data-stu-id="4cb85-200">None</span></span>

<span data-ttu-id="4cb85-201">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4cb85-201">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="4cb85-202">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4cb85-202">NOTES</span></span>

- <span data-ttu-id="4cb85-203">Durch das Deaktivieren der Sitzungs Konfigurationen werden nicht alle Änderungen rückgängig gemacht, die von den- `Enable-PSRemoting` oder- `Enable-PSSessionConfiguration` Cmdlets vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="4cb85-203">Disabling the session configurations does not undo all the changes that were made by the `Enable-PSRemoting` or `Enable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="4cb85-204">Möglicherweise müssen Sie Änderungen wie folgt manuell rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-204">You might have to undo the following changes manually.</span></span>

  1. <span data-ttu-id="4cb85-205">Beenden und deaktivieren Sie den WinRM-Dienst.</span><span class="sxs-lookup"><span data-stu-id="4cb85-205">Stop and disable the WinRM service.</span></span>
  2. <span data-ttu-id="4cb85-206">Löschen Sie den Listener, der Anforderungen auf beliebigen IP-Adressen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="4cb85-206">Delete the listener that accepts requests on any IP address.</span></span>
  3. <span data-ttu-id="4cb85-207">Deaktivieren Sie die Firewallausnahmen für die WS-Verwaltungskommunikation.</span><span class="sxs-lookup"><span data-stu-id="4cb85-207">Disable the firewall exceptions for WS-Management communications.</span></span>
  4. <span data-ttu-id="4cb85-208">Setzen Sie den Wert von LocalAccountTokenFilterPolicy auf 0 zurück. Dadurch wird der Remotezugriff auf Mitglieder der Gruppe „Administratoren“ auf dem Computer beschränkt.</span><span class="sxs-lookup"><span data-stu-id="4cb85-208">Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the Administrators group on the computer.</span></span>

- <span data-ttu-id="4cb85-209">Eine Sitzungs Endpunkt Konfiguration ist eine Gruppe von Einstellungen, die die Umgebung für eine Sitzung definieren.</span><span class="sxs-lookup"><span data-stu-id="4cb85-209">A session endpoint configuration is a group of settings that define the environment for a session.</span></span>
  <span data-ttu-id="4cb85-210">Jede Sitzung, die eine Verbindung mit dem Computer herstellt, muss eine der auf dem Computer registrierten Sitzungs Endpunkt Konfigurationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cb85-210">Every session that connects to the computer must use one of the session endpoint configurations that are registered on the computer.</span></span> <span data-ttu-id="4cb85-211">Indem Sie den Remote Zugriff auf alle Sitzungs Endpunkt Konfigurationen verweigern, verhindern Sie, dass Remote Benutzersitzungen einrichten, die eine Verbindung mit dem Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="4cb85-211">By denying remote access to all session endpoint configurations, you effectively prevent remote users from establishing sessions that connect to the computer.</span></span>

## <span data-ttu-id="4cb85-212">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4cb85-212">RELATED LINKS</span></span>

[<span data-ttu-id="4cb85-213">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4cb85-213">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="4cb85-214">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="4cb85-214">Enable-PSRemoting</span></span>](Enable-PSRemoting.md)

[<span data-ttu-id="4cb85-215">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4cb85-215">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="4cb85-216">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="4cb85-216">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="4cb85-217">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4cb85-217">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="4cb85-218">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4cb85-218">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="4cb85-219">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4cb85-219">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="4cb85-220">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="4cb85-220">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
