---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: 3a281786f99b2a46d0aeb9785480f02b35b2b433
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212103"
---
# <span data-ttu-id="9f6f9-103">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="9f6f9-103">Disable-PSRemoting</span></span>

## <span data-ttu-id="9f6f9-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9f6f9-104">SYNOPSIS</span></span>
<span data-ttu-id="9f6f9-105">Verhindert, dass PowerShell-Endpunkte Remote Verbindungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-105">Prevents PowerShell endpoints from receiving remote connections.</span></span>

## <span data-ttu-id="9f6f9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9f6f9-106">SYNTAX</span></span>

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9f6f9-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9f6f9-107">DESCRIPTION</span></span>

<span data-ttu-id="9f6f9-108">Mit dem- `Disable-PSRemoting` Cmdlet wird der Remote Zugriff auf alle Konfigurationen von Windows PowerShell-Sitzungs Endpunkten auf dem lokalen Computer blockiert.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-108">The `Disable-PSRemoting` cmdlet blocks remote access to all Windows PowerShell session endpoint configurations on the local computer.</span></span> <span data-ttu-id="9f6f9-109">Dies schließt alle Endpunkte ein, die von PowerShell 6 oder höher erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-109">This includes any endpoints created by PowerShell 6 or higher.</span></span>

<span data-ttu-id="9f6f9-110">Verwenden Sie das-Cmdlet, um den Remote Zugriff auf alle Sitzungs Konfigurationen wieder zu aktivieren `Enable-PSRemoting` .</span><span class="sxs-lookup"><span data-stu-id="9f6f9-110">To re-enable remote access to all session configurations, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="9f6f9-111">Dies schließt alle Endpunkte ein, die von PowerShell 6 oder höher erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-111">This includes any endpoints created by PowerShell 6 or higher.</span></span> <span data-ttu-id="9f6f9-112">Um den Remote Zugriff auf ausgewählte Sitzungs Konfigurationen zu aktivieren, verwenden Sie den **AccessMode** -Parameter des `Set-PSSessionConfiguration` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-112">To enable remote access to selected session configurations, use the **AccessMode** parameter of the `Set-PSSessionConfiguration` cmdlet.</span></span>
<span data-ttu-id="9f6f9-113">Sie können auch die `Enable-PSSessionConfiguration` `Disable-PSSessionConfiguration` Cmdlets und verwenden, um Sitzungs Konfigurationen für alle Benutzer zu aktivieren und zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-113">You can also use the `Enable-PSSessionConfiguration` and `Disable-PSSessionConfiguration` cmdlets to enable and disable session configurations for all users.</span></span> <span data-ttu-id="9f6f9-114">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="9f6f9-114">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9f6f9-115">Auch nach `Disable-PSRemoting` der Ausführung können Sie Loopback Verbindungen auf dem lokalen Computer durchführen.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-115">Even after running `Disable-PSRemoting` you can still make loopback connections on the local machine.</span></span> <span data-ttu-id="9f6f9-116">Eine Loopback Verbindung ist eine PowerShell-Remote Sitzung, die aus stammt und eine Verbindung mit dem gleichen lokalen Computer herstellt.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-116">A loopback connection is a PowerShell remote session that originates from and connects to the same local machine.</span></span> <span data-ttu-id="9f6f9-117">Remote Sitzungen aus externen Quellen bleiben blockiert.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-117">Remote sessions from external sources remain blocked.</span></span> <span data-ttu-id="9f6f9-118">Für Loopback Verbindungen müssen Sie die impliziten Anmelde Informationen für den **enablenetworkaccess** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-118">For loopback connections you must use implicit credentials along the **EnableNetworkAccess** parameter.</span></span> <span data-ttu-id="9f6f9-119">Weitere Informationen zu Loopback Verbindungen finden Sie unter [New-PSSession](New-PSSession.md).</span><span class="sxs-lookup"><span data-stu-id="9f6f9-119">For more information about loopback connections, see [New-PSSession](New-PSSession.md).</span></span>

<span data-ttu-id="9f6f9-120">Um dieses Cmdlet auszuführen, starten Sie Windows PowerShell mit der Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="9f6f9-120">To run this cmdlet, start Windows PowerShell with the **Run as administrator** option.</span></span>

## <span data-ttu-id="9f6f9-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9f6f9-121">EXAMPLES</span></span>

### <span data-ttu-id="9f6f9-122">Beispiel 1: verhindern des Remote Zugriffs auf alle Sitzungs Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9f6f9-122">Example 1: Prevent remote access to all session configurations</span></span>

<span data-ttu-id="9f6f9-123">In diesem Beispiel wird der Remote Zugriff auf alle PowerShell-Sitzungs Endpunkt Konfigurationen auf dem Computer verhindert.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-123">This example prevents remote access to all PowerShell session endpoint configurations on the computer.</span></span>

```powershell
Disable-PSRemoting
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="9f6f9-124">Beispiel 2: verhindern des Remote Zugriffs auf alle Sitzungs Konfigurationen ohne Bestätigungsaufforderung</span><span class="sxs-lookup"><span data-stu-id="9f6f9-124">Example 2: Prevent remote access to all session configurations without confirmation prompt</span></span>

<span data-ttu-id="9f6f9-125">In diesem Beispiel wird der Remote Zugriff auf alle PowerShell-Sitzungs Endpunkt Konfigurationen auf dem Computer ohne Eingabeaufforderung verhindert.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-125">This example prevents remote access all PowerShell session endpoint configurations on the computer without prompting.</span></span>

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="9f6f9-126">Beispiel 3: Auswirkungen der Ausführung dieses Cmdlets</span><span class="sxs-lookup"><span data-stu-id="9f6f9-126">Example 3: Effects of running this cmdlet</span></span>

<span data-ttu-id="9f6f9-127">In diesem Beispiel werden die Auswirkungen der Verwendung des- `Disable-PSRemoting` Cmdlets veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-127">This example shows the effect of using the `Disable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="9f6f9-128">Starten Sie PowerShell mit der Option **als Administrator ausführen** , um diese Befehlssequenz auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-128">To run this command sequence, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="9f6f9-129">Nachdem Sie die Sitzungs Konfigurationen deaktiviert haben, `New-PSSession` versucht das Cmdlet, eine Remote Sitzung mit dem lokalen Computer (auch als "Loopback" bezeichnet) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-129">After disabling the sessions configurations, the `New-PSSession` cmdlet attempts to create a remote session to the local computer (also known as a "loopback").</span></span> <span data-ttu-id="9f6f9-130">Da der Remote Zugriff auf dem lokalen Computer deaktiviert ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-130">Because remote access is disabled on the local machine, the command fails.</span></span>

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
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

### <span data-ttu-id="9f6f9-131">Beispiel 4: Auswirkungen der Ausführung dieses Cmdlets und Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="9f6f9-131">Example 4: Effects of running this cmdlet and Enable-PSRemoting</span></span>

<span data-ttu-id="9f6f9-132">Dieses Beispiel zeigt die Auswirkung auf die Sitzungs Konfigurationen von mithilfe der `Disable-PSRemoting` `Enable-PSRemoting` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-132">This example shows the effect on the session configurations of using the `Disable-PSRemoting` and `Enable-PSRemoting` cmdlets.</span></span>

<span data-ttu-id="9f6f9-133">`Disable-PSRemoting` wird verwendet, um den Remote Zugriff auf alle Konfigurationen von PowerShell-Sitzungs Endpunkten zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-133">`Disable-PSRemoting` is used to disable remote access to all PowerShell session endpoint configurations.</span></span> <span data-ttu-id="9f6f9-134">Mit dem **Force** -Parameter werden alle Eingabeaufforderungen unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-134">The **Force** parameter suppresses all user prompts.</span></span> <span data-ttu-id="9f6f9-135">`Get-PSSessionConfiguration`Mit den-und- `Format-Table` Cmdlets werden die Sitzungs Konfigurationen auf dem Computer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-135">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations on the computer.</span></span>

<span data-ttu-id="9f6f9-136">Die Ausgabe zeigt, dass allen Remote Benutzern mit einem Netzwerk Token der Zugriff auf die Endpunkt Konfigurationen verweigert wird.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-136">The output shows that all remote users with a network token are denied access to the endpoint configurations.</span></span> <span data-ttu-id="9f6f9-137">Die Gruppe "Administratoren" auf dem lokalen Computer verfügt über Zugriff auf die Endpunkt Konfigurationen, solange Sie lokal (auch als Loopback bezeichnet) eine Verbindung herstellen und implizite Anmelde Informationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-137">Administrators group on the local computer are allowed access to the endpoint configurations as long as they are connecting locally (also known as loopback) and using implicit credentials.</span></span>

```powershell
Disable-PSRemoting -force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Enable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow BUILTIN\Administrators AccessAllowed
microsoft.powershell32        BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   BUILTIN\Administrators AccessAllowed
```

<span data-ttu-id="9f6f9-138">Mit dem `Enable-PSRemoting` -Cmdlet wird der Remote Zugriff auf alle PowerShell-Sitzungs Endpunkt Konfigurationen auf dem Computer erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-138">The `Enable-PSRemoting` cmdlet re-enables remote access to all PowerShell session endpoint configurations on the computer.</span></span> <span data-ttu-id="9f6f9-139">Der **Force** -Parameter unterdrückt alle Benutzer Aufforderungen und startet den WinRM-Dienst ohne Aufforderung neu.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-139">The **Force** parameter suppresses all user prompts and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="9f6f9-140">Die neue Ausgabe zeigt, dass die **AccessDenied** -Sicherheits Beschreibungen aus allen Sitzungs Konfigurationen entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-140">The new output shows that the **AccessDenied** security descriptors have been removed from all session configurations.</span></span>

### <span data-ttu-id="9f6f9-141">Beispiel 5: Loopback Verbindungen mit deaktivierten Sitzungs Endpunkt Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9f6f9-141">Example 5: Loopback connections with disabled session endpoint configurations</span></span>

<span data-ttu-id="9f6f9-142">In diesem Beispiel wird veranschaulicht, wie Endpunkt Konfigurationen deaktiviert werden, und es wird gezeigt, wie Sie eine erfolgreiche Loopback Verbindung mit einem deaktivierten Endpunkt herstellen.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-142">This example demonstrates how endpoint configurations are disabled, and shows how to make a successful loopback connection to a disabled endpoint.</span></span> <span data-ttu-id="9f6f9-143">`Disable-PSRemoting` deaktiviert alle PowerShell-Sitzungs Endpunkt Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-143">`Disable-PSRemoting` disables all PowerShell session endpoint configurations.</span></span>

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message : Access is
denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [New-PSSession], PSRemotin
   gTransportException
    + FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed

```

```powershell
New-PSSession -ComputerName localhost -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

<span data-ttu-id="9f6f9-144">Bei der ersten Verwendung von wird `New-PSSession` versucht, eine Remote Sitzung mit dem lokalen Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-144">The first use of `New-PSSession` attempts to create a remote session to the local machine.</span></span> <span data-ttu-id="9f6f9-145">Dieser Verbindungstyp wird durch den Netzwerk Stapel geleitet und ist kein Loopback.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-145">This type of connection goes through the network stack and is not a loopback.</span></span> <span data-ttu-id="9f6f9-146">Folglich schlägt der Verbindungsversuch mit dem deaktivierten Endpunkt mit dem Fehler " **Zugriff verweigert** " fehl.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-146">Consequently, the connection attempt to the disabled endpoint fails with an **Access is denied** error.</span></span>

<span data-ttu-id="9f6f9-147">Bei der zweiten Verwendung von wird `New-PSSession` auch versucht, eine Remote Sitzung mit dem lokalen Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-147">The second use of `New-PSSession` also attempts to create a remote session to the local machine.</span></span>
<span data-ttu-id="9f6f9-148">In diesem Fall ist dies erfolgreich, weil es sich um eine Loopback Verbindung handelt, die den Netzwerk Stapel umgeht.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-148">In this case, it succeeds because it is a loopback connection that bypasses the network stack.</span></span>

<span data-ttu-id="9f6f9-149">Eine Loopback Verbindung wird erstellt, wenn die folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="9f6f9-149">A loopback connection is created when the following conditions are met:</span></span>

- <span data-ttu-id="9f6f9-150">Der Computername, mit dem eine Verbindung hergestellt werden soll, ist "localhost".</span><span class="sxs-lookup"><span data-stu-id="9f6f9-150">The computer name to connect to is 'localhost'.</span></span>
- <span data-ttu-id="9f6f9-151">Es werden keine Anmelde Informationen übermittelt.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-151">No credentials are passed in.</span></span> <span data-ttu-id="9f6f9-152">Der aktuell angemeldete Benutzer (implizite Anmelde Informationen) wird für die Verbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-152">Current logged in user (implicit credentials) is used for the connection.</span></span>
- <span data-ttu-id="9f6f9-153">Der **enablenetworkaccess** -Schalter Parameter wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-153">The **EnableNetworkAccess** switch parameter is used.</span></span>

<span data-ttu-id="9f6f9-154">Weitere Informationen zu Loopback Verbindungen finden Sie im Dokument [New-PSSession](New-PSSession.md) .</span><span class="sxs-lookup"><span data-stu-id="9f6f9-154">For more information on loopback connections, see [New-PSSession](New-PSSession.md) document.</span></span>

### <span data-ttu-id="9f6f9-155">Beispiel 6: verhindern des Remote Zugriffs auf Sitzungs Konfigurationen mit benutzerdefinierten Sicherheits Deskriptoren</span><span class="sxs-lookup"><span data-stu-id="9f6f9-155">Example 6: Prevent remote access to session configurations that have custom security descriptors</span></span>

<span data-ttu-id="9f6f9-156">Dieses Beispiel zeigt, dass das `Disable-PSRemoting` Cmdlet den Remote Zugriff auf alle Sitzungs Konfigurationen deaktiviert, die Sitzungs Konfigurationen mit benutzerdefinierten Sicherheits Beschreibungen einschließen.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-156">This example demonstrates that the `Disable-PSRemoting` cmdlet disables remote access to all session configurations that include session configurations with custom security descriptors.</span></span>

<span data-ttu-id="9f6f9-157">`Register-PSSessionConfiguration` erstellt die **Test** Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-157">`Register-PSSessionConfiguration` creates the **Test** session configuration.</span></span> <span data-ttu-id="9f6f9-158">Der **FilePath** -Parameter gibt eine Sitzungs Konfigurationsdatei an, die die Sitzung anpasst.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-158">The **FilePath** parameter specifies a session configuration file that customizes the session.</span></span> <span data-ttu-id="9f6f9-159">Der **showsecuritydescriptorui** -Parameter zeigt ein Dialogfeld an, in dem Berechtigungen für die Sitzungs Konfiguration festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-159">The **ShowSecurityDescriptorUI** parameter displays a dialog box that sets permissions for the session configuration.</span></span> <span data-ttu-id="9f6f9-160">Im Dialogfeld "Berechtigungen" erstellen wir benutzerdefinierte voll Zugriffsberechtigungen für den angezeigten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-160">In the Permissions dialog box, we create custom full-access permissions for the indicated user.</span></span>

<span data-ttu-id="9f6f9-161">Die `Get-PSSessionConfiguration` -und- `Format-Table` Cmdlets zeigen die Sitzungs Konfigurationen und deren Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-161">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations and their properties.</span></span> <span data-ttu-id="9f6f9-162">Die Ausgabe zeigt, dass die **Test** Sitzungs Konfiguration interaktiven Zugriff und spezielle Berechtigungen für den Benutzer ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-162">The output shows that the **Test** session configuration allows interactive access and special permissions for the indicated user.</span></span>

<span data-ttu-id="9f6f9-163">`Disable-PSRemoting` deaktiviert den Remote Zugriff auf alle Sitzungs Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-163">`Disable-PSRemoting` disables remote access to all session configurations.</span></span>

```powershell
Register-PSSessionConfiguration -Name Test -FilePath .\TestEndpoint.pssc -ShowSecurityDescriptorUI -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap

Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap
New-PSSession -ComputerName localhost -ConfigurationName Test
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
DOMAIN01\User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\NETWORK AccessDenied, NTAUTHORITY\INTERACTIVE AccessAllowed,
BUILTIN\Administrators AccessAllowed, DOMAIN01\User01 AccessAllowed


[Server01] Connecting to remote server failed with the following error message : Access is denied. For more information, see the about_Rem
ote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

<span data-ttu-id="9f6f9-164">Die `Get-PSSessionConfiguration` `Format-Table` Cmdlets und zeigen nun, dass allen Sitzungs Konfigurationen, einschließlich der **Test** Sitzungs Konfiguration, eine **AccessDenied** -Sicherheits Beschreibung für alle Netzwerk Benutzer hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-164">Now the `Get-PSSessionConfiguration` and `Format-Table` cmdlets shows that an **AccessDenied** security descriptor for all network users is added to all session configurations, including the **Test** session configuration.</span></span> <span data-ttu-id="9f6f9-165">Obwohl die anderen Sicherheits Deskriptoren nicht geändert werden, hat der Sicherheits Deskriptor "network_deny_all" Vorrang.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-165">Although the other security descriptors are not changed, the "network_deny_all" security descriptor takes precedence.</span></span> <span data-ttu-id="9f6f9-166">Dies wird durch den Versuch veranschaulicht, zu verwenden, `New-PSSession` um eine Verbindung mit der **Test** Sitzungs Konfiguration herzustellen.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-166">This is illustrated by the attempt to use `New-PSSession` to connect to the **Test** session configuration.</span></span>

### <span data-ttu-id="9f6f9-167">Beispiel 7: Erneutes Aktivieren des Remote Zugriffs auf ausgewählte Sitzungs Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9f6f9-167">Example 7: Re-enable remote access to selected session configurations</span></span>

<span data-ttu-id="9f6f9-168">In diesem Beispiel wird veranschaulicht, wie der Remotezugriff nur auf ausgewählte Sitzungskonfigurationen erneut aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-168">This example shows how to re-enable remote access only to selected session configurations.</span></span> <span data-ttu-id="9f6f9-169">Nachdem Sie alle Sitzungs Konfigurationen deaktiviert haben, aktivieren wir eine bestimmte Sitzung erneut.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-169">After disabling all session configurations, we re-enable a specific session.</span></span>

<span data-ttu-id="9f6f9-170">Das- `Set-PSSessionConfiguration` Cmdlet wird verwendet, um **Microsoft zu ändern. Server Manager** -Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-170">The `Set-PSSessionConfiguration` cmdlet is used to change the **microsoft.ServerManager** session configuration.</span></span> <span data-ttu-id="9f6f9-171">Der **AccessMode** -Parameter mit dem Wert **Remote** aktiviert den Remote Zugriff auf die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-171">The **AccessMode** parameter with a value of **Remote** re-enables remote access to the configuration.</span></span>

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name Microsoft.ServerManager -AccessMode Remote -Force
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

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
```

## <span data-ttu-id="9f6f9-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9f6f9-172">PARAMETERS</span></span>

### <span data-ttu-id="9f6f9-173">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9f6f9-173">-Confirm</span></span>

<span data-ttu-id="9f6f9-174">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-174">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9f6f9-175">-Force</span><span class="sxs-lookup"><span data-stu-id="9f6f9-175">-Force</span></span>
<span data-ttu-id="9f6f9-176">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-176">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="9f6f9-177">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9f6f9-177">-WhatIf</span></span>

<span data-ttu-id="9f6f9-178">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-178">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9f6f9-179">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-179">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9f6f9-180">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9f6f9-180">CommonParameters</span></span>

<span data-ttu-id="9f6f9-181">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-181">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9f6f9-182">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9f6f9-182">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9f6f9-183">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9f6f9-183">INPUTS</span></span>

### <span data-ttu-id="9f6f9-184">Keine</span><span class="sxs-lookup"><span data-stu-id="9f6f9-184">None</span></span>

<span data-ttu-id="9f6f9-185">Sie können keine Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-185">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="9f6f9-186">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9f6f9-186">OUTPUTS</span></span>

### <span data-ttu-id="9f6f9-187">Keine</span><span class="sxs-lookup"><span data-stu-id="9f6f9-187">None</span></span>

<span data-ttu-id="9f6f9-188">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-188">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9f6f9-189">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9f6f9-189">NOTES</span></span>

- <span data-ttu-id="9f6f9-190">Durch das Deaktivieren der Sitzungs Konfigurationen werden nicht alle Änderungen rückgängig gemacht, die von den- `Enable-PSRemoting` oder- `Enable-PSSessionConfiguration` Cmdlets vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-190">Disabling the session configurations does not undo all the changes that were made by the `Enable-PSRemoting` or `Enable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="9f6f9-191">Möglicherweise müssen Sie Änderungen wie folgt manuell rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-191">You might have to undo the following changes manually.</span></span>

  1. <span data-ttu-id="9f6f9-192">Beenden und deaktivieren Sie den WinRM-Dienst.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-192">Stop and disable the WinRM service.</span></span>
  2. <span data-ttu-id="9f6f9-193">Löschen Sie den Listener, der Anforderungen auf beliebigen IP-Adressen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-193">Delete the listener that accepts requests on any IP address.</span></span>
  3. <span data-ttu-id="9f6f9-194">Deaktivieren Sie die Firewallausnahmen für die WS-Verwaltungskommunikation.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-194">Disable the firewall exceptions for WS-Management communications.</span></span>
  4. <span data-ttu-id="9f6f9-195">Setzen Sie den Wert von LocalAccountTokenFilterPolicy auf 0 zurück. Dadurch wird der Remotezugriff auf Mitglieder der Gruppe „Administratoren“ auf dem Computer beschränkt.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-195">Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the Administrators group on the computer.</span></span>

  <span data-ttu-id="9f6f9-196">Eine Sitzungskonfiguration ist eine Gruppe von Einstellungen, die die Umgebung für eine Sitzung definieren.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-196">A session configuration is a group of settings that define the environment for a session.</span></span> <span data-ttu-id="9f6f9-197">Jede Sitzung, die mit dem Computer verbunden wird, muss eine der auf dem Computer registrierten Sitzungskonfigurationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-197">Every session that connects to the computer must use one of the session configurations that are registered on the computer.</span></span> <span data-ttu-id="9f6f9-198">Indem Sie den Remotezugriff auf alle Sitzungskonfigurationen verweigern, hindern Sie Remotebenutzer effektiv daran, Sitzungen einzurichten, die eine Verbindung mit dem Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-198">By denying remote access to all session configurations, you effectively prevent remote users from establishing sessions that connect to the computer.</span></span>

  <span data-ttu-id="9f6f9-199">Fügt in Windows PowerShell 2,0 `Disable-PSRemoting` den Sicherheits Beschreibungen aller Sitzungs Konfigurationen einen Deny_All Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-199">In Windows PowerShell 2.0, `Disable-PSRemoting` adds a Deny_All entry to the security descriptors of all session configurations.</span></span> <span data-ttu-id="9f6f9-200">Diese Einstellung verhindert, dass alle Benutzer vom Benutzer verwaltete Sitzungen auf dem lokalen Computer erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-200">This setting prevents all users from creating user-managed sessions to the local computer.</span></span> <span data-ttu-id="9f6f9-201">Fügt in Windows PowerShell 3,0 `Disable-PSRemoting` den Sicherheits Beschreibungen aller Sitzungs Konfigurationen einen Network_Deny_All Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-201">In Windows PowerShell 3.0, `Disable-PSRemoting` adds a Network_Deny_All entry to the security descriptors of all session configurations.</span></span> <span data-ttu-id="9f6f9-202">Mit dieser Einstellung wird verhindert, dass Benutzer auf anderen Computern vom Benutzer verwaltete Sitzungen auf dem lokalen Computer erstellen, aber Benutzern des lokalen Computers das Erstellen von Benutzer verwalteten Loopback Sitzungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="9f6f9-202">This setting prevents users on other computers from creating user-managed sessions on the local computer, but allows users of the local computer to create user-managed loopback sessions.</span></span>

  <span data-ttu-id="9f6f9-203">In Windows PowerShell 2,0 `Disable-PSRemoting` ist die Entsprechung von `Disable-PSSessionConfiguration -Name *` .</span><span class="sxs-lookup"><span data-stu-id="9f6f9-203">In Windows PowerShell 2.0, `Disable-PSRemoting` is the equivalent of `Disable-PSSessionConfiguration -Name *`.</span></span> <span data-ttu-id="9f6f9-204">In Windows PowerShell 3,0 und späteren Versionen `Disable-PSRemoting` ist die Entsprechung von `Set-PSSessionConfiguration -Name \<Configuration name\> -AccessMode Local`</span><span class="sxs-lookup"><span data-stu-id="9f6f9-204">In Windows PowerShell 3.0 and later releases, `Disable-PSRemoting` is the equivalent of `Set-PSSessionConfiguration -Name \<Configuration name\> -AccessMode Local`</span></span>

## <span data-ttu-id="9f6f9-205">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9f6f9-205">RELATED LINKS</span></span>

[<span data-ttu-id="9f6f9-206">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f6f9-206">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="9f6f9-207">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="9f6f9-207">Enable-PSRemoting</span></span>](Enable-PSRemoting.md)

[<span data-ttu-id="9f6f9-208">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f6f9-208">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="9f6f9-209">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="9f6f9-209">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="9f6f9-210">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f6f9-210">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="9f6f9-211">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f6f9-211">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="9f6f9-212">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f6f9-212">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="9f6f9-213">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="9f6f9-213">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
