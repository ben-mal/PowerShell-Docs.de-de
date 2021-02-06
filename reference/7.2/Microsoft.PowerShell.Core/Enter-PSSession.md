---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSSession
ms.openlocfilehash: 9c08e78d840815a396b55eb26bf8e21d73cb81aa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603708"
---
# <span data-ttu-id="f13a1-102">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="f13a1-102">Enter-PSSession</span></span>

## <span data-ttu-id="f13a1-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f13a1-103">SYNOPSIS</span></span>
<span data-ttu-id="f13a1-104">Startet eine interaktive Sitzung mit einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="f13a1-104">Starts an interactive session with a remote computer.</span></span>

## <span data-ttu-id="f13a1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f13a1-105">SYNTAX</span></span>

### <span data-ttu-id="f13a1-106">Computername (Standard)</span><span class="sxs-lookup"><span data-stu-id="f13a1-106">ComputerName (Default)</span></span>

```
Enter-PSSession [-ComputerName] <String> [-EnableNetworkAccess] [[-Credential] <PSCredential>]
 [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL] [-ApplicationName <String>]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="f13a1-107">Sshhost</span><span class="sxs-lookup"><span data-stu-id="f13a1-107">SSHHost</span></span>

```
Enter-PSSession [-HostName] <String> [-Port <Int32>] [-UserName <String>] [-KeyFilePath <String>]
 [-SSHTransport] [<CommonParameters>]
```

### <span data-ttu-id="f13a1-108">Sitzung</span><span class="sxs-lookup"><span data-stu-id="f13a1-108">Session</span></span>

```
Enter-PSSession [[-Session] <PSSession>] [<CommonParameters>]
```

### <span data-ttu-id="f13a1-109">Uri</span><span class="sxs-lookup"><span data-stu-id="f13a1-109">Uri</span></span>

```
Enter-PSSession [[-ConnectionUri] <Uri>] [-EnableNetworkAccess] [[-Credential] <PSCredential>]
 [-ConfigurationName <String>] [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="f13a1-110">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f13a1-110">InstanceId</span></span>

```
Enter-PSSession [-InstanceId <Guid>] [<CommonParameters>]
```

### <span data-ttu-id="f13a1-111">Id</span><span class="sxs-lookup"><span data-stu-id="f13a1-111">Id</span></span>

```
Enter-PSSession [[-Id] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="f13a1-112">Name</span><span class="sxs-lookup"><span data-stu-id="f13a1-112">Name</span></span>

```
Enter-PSSession [-Name <String>] [<CommonParameters>]
```

### <span data-ttu-id="f13a1-113">VMId</span><span class="sxs-lookup"><span data-stu-id="f13a1-113">VMId</span></span>

```
Enter-PSSession [-VMId] <Guid> [-Credential] <PSCredential> [-ConfigurationName <String>] [<CommonParameters>]
```

### <span data-ttu-id="f13a1-114">VMName</span><span class="sxs-lookup"><span data-stu-id="f13a1-114">VMName</span></span>

```
Enter-PSSession [-VMName] <String> [-Credential] <PSCredential> [-ConfigurationName <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="f13a1-115">ContainerId</span><span class="sxs-lookup"><span data-stu-id="f13a1-115">ContainerId</span></span>

```
Enter-PSSession [-ContainerId] <String> [-ConfigurationName <String>] [-RunAsAdministrator]
 [<CommonParameters>]
```

## <span data-ttu-id="f13a1-116">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f13a1-116">DESCRIPTION</span></span>

<span data-ttu-id="f13a1-117">Mit dem- `Enter-PSSession` Cmdlet wird eine interaktive Sitzung mit einem einzelnen Remote Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="f13a1-117">The `Enter-PSSession` cmdlet starts an interactive session with a single remote computer.</span></span>
<span data-ttu-id="f13a1-118">Während der Sitzung werden die Befehle, die Sie eingeben, auf dem Remote Computer ausgeführt, so als würden Sie direkt auf dem Remote Computer eingeben.</span><span class="sxs-lookup"><span data-stu-id="f13a1-118">During the session, the commands that you type run on the remote computer, just as if you were typing directly on the remote computer.</span></span> <span data-ttu-id="f13a1-119">Sie können sich zu einem Zeitpunkt jeweils nur in einer interaktiven Sitzung befinden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-119">You can have only one interactive session at a time.</span></span>

<span data-ttu-id="f13a1-120">Normalerweise verwenden Sie den **ComputerName**-Parameter, um den Namen des Remotecomputers anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f13a1-120">Typically, you use the **ComputerName** parameter to specify the name of the remote computer.</span></span>
<span data-ttu-id="f13a1-121">Sie können jedoch auch eine Sitzung verwenden, die Sie mit dem `New-PSSession` Cmdlet für die interaktive Sitzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-121">However, you can also use a session that you create by using the `New-PSSession` cmdlet for the interactive session.</span></span> <span data-ttu-id="f13a1-122">Allerdings können Sie die `Disconnect-PSSession` `Connect-PSSession` Cmdlets, oder nicht verwenden, um die Verbindung mit `Receive-PSSession` einer interaktiven Sitzung zu trennen oder erneut eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-122">However, you cannot use the `Disconnect-PSSession`, `Connect-PSSession`, or `Receive-PSSession` cmdlets to disconnect from or re-connect to an interactive session.</span></span>

<span data-ttu-id="f13a1-123">Ab PowerShell 6,0 können Sie Secure Shell (SSH) verwenden, um eine Verbindung mit einem Remote Computer herzustellen, wenn ssh auf dem lokalen Computer verfügbar ist und der Remote Computer mit einem PowerShell-SSH-Endpunkt konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="f13a1-123">Starting with PowerShell 6.0 you can use Secure Shell (SSH) to establish a connection to a remote computer, if SSH is available on the local computer and the remote computer is configured with a PowerShell SSH endpoint.</span></span> <span data-ttu-id="f13a1-124">Eine auf ssh basierende PowerShell-Remote Sitzung hat den Vorteil, dass Sie auf mehreren Plattformen (Windows, Linux, macOS) funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f13a1-124">The benefit an SSH based PowerShell remote session is that it works across multiple platforms (Windows, Linux, macOS).</span></span> <span data-ttu-id="f13a1-125">Für SSH-basiertes Remoting verwenden Sie den **Hostname** -Parametersatz, um den Remote Computer und relevante Verbindungsinformationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f13a1-125">For SSH based remoting you use the **HostName** parameter set to specify the remote computer and relevant connection information.</span></span> <span data-ttu-id="f13a1-126">Weitere Informationen zum Einrichten von PowerShell-SSH-Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="f13a1-126">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

<span data-ttu-id="f13a1-127">Um die interaktive Sitzung zu beenden und die Verbindung mit dem Remote Computer zu trennen, verwenden Sie das- `Exit-PSSession` Cmdlet oder den-Typ `exit` .</span><span class="sxs-lookup"><span data-stu-id="f13a1-127">To end the interactive session and disconnect from the remote computer, use the `Exit-PSSession` cmdlet, or type `exit`.</span></span>

## <span data-ttu-id="f13a1-128">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f13a1-128">EXAMPLES</span></span>

### <span data-ttu-id="f13a1-129">Beispiel 1: Starten einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="f13a1-129">Example 1: Start an interactive session</span></span>

```
PS> Enter-PSSession
[localhost]: PS>
```

<span data-ttu-id="f13a1-130">Dieser Befehl startet eine interaktive Sitzung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="f13a1-130">This command starts an interactive session on the local computer.</span></span> <span data-ttu-id="f13a1-131">Die Eingabeaufforderung ändert sich, um anzugeben, dass die Befehle nun in einer anderen Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-131">The command prompt changes to indicate that you are now running commands in a different session.</span></span>

<span data-ttu-id="f13a1-132">Die eingegebenen Befehle werden in der neuen Sitzung ausgeführt, und die Ergebnisse werden als Text an die Standardsitzung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f13a1-132">The commands that you enter run in the new session, and the results are returned to the default session as text.</span></span>

### <span data-ttu-id="f13a1-133">Beispiel 2: Arbeiten mit einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="f13a1-133">Example 2: Work with an interactive session</span></span>

<span data-ttu-id="f13a1-134">Der erste Befehl verwendet das `Enter-PSSession` Cmdlet, um eine interaktive Sitzung mit Server01, einem Remote Computer, zu starten.</span><span class="sxs-lookup"><span data-stu-id="f13a1-134">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with Server01, a remote computer.</span></span> <span data-ttu-id="f13a1-135">Wenn die Sitzung startet, ändert sich die Eingabeaufforderung und enthält den Computernamen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-135">When the session starts, the command prompt changes to include the computer name.</span></span>

<span data-ttu-id="f13a1-136">Der zweite Befehl ruft den PowerShell-Prozess ab und leitet die Ausgabe in die Datei „Process.txt“ um.</span><span class="sxs-lookup"><span data-stu-id="f13a1-136">The second command gets the PowerShell process and redirects the output to the Process.txt file.</span></span> <span data-ttu-id="f13a1-137">Der Befehl wird an den Remotecomputer gesendet, und die Datei wird auf dem Remotecomputer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f13a1-137">The command is submitted to the remote computer, and the file is saved on the remote computer.</span></span>

<span data-ttu-id="f13a1-138">Der dritte Befehl verwendet das **Exit** -Schlüsselwort, um die interaktive Sitzung zu beenden und die Verbindung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-138">The third command uses the **Exit** keyword to end the interactive session and close the connection.</span></span>
<span data-ttu-id="f13a1-139">Der vierte Befehl bestätigt, dass sich die Datei „Process.txt“ auf dem Remotecomputer befindet.</span><span class="sxs-lookup"><span data-stu-id="f13a1-139">The fourth command confirms that the Process.txt file is on the remote computer.</span></span> <span data-ttu-id="f13a1-140">`Get-ChildItem`Der Befehl ("dir") auf dem lokalen Computer kann die Datei nicht finden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-140">A `Get-ChildItem` ("dir") command on the local computer cannot find the file.</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS>
[Server01]: PS C:\> Get-Process PowerShell > C:\ps-test\Process.txt
[Server01]: PS C:\> exit
PS C:\>
PS C:\> dir C:\ps-test\process.txt
Get-ChildItem : Cannot find path 'C:\ps-test\process.txt' because it does not exist.
At line:1 char:4
+ dir <<<<  c:\ps-test\process.txt
```

<span data-ttu-id="f13a1-141">Dieser Befehl zeigt die Arbeitsweise in einer interaktiven Sitzung mit einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="f13a1-141">This command shows how to work in an interactive session with a remote computer.</span></span>

### <span data-ttu-id="f13a1-142">Beispiel 3: Verwenden des Session-Parameters</span><span class="sxs-lookup"><span data-stu-id="f13a1-142">Example 3: Use the Session parameter</span></span>

```powershell
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
[Server01]: PS>
```

<span data-ttu-id="f13a1-143">Diese Befehle verwenden den **Session** -Parameter von `Enter-PSSession` , um die interaktive Sitzung in einer vorhandenen PowerShell-Sitzung (**PSSession**) auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-143">These commands use the **Session** parameter of `Enter-PSSession` to run the interactive session in an existing PowerShell session (**PSSession**).</span></span>

### <span data-ttu-id="f13a1-144">Beispiel 4: Starten einer interaktiven Sitzung und angeben der Parameter für Port und Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="f13a1-144">Example 4: Start an interactive session and specify the Port and Credential parameters</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01 -Port 90 -Credential Domain01\User01
[Server01]: PS>
```

<span data-ttu-id="f13a1-145">Dieser Befehl startet eine interaktive Sitzung mit dem Computer „Server01“.</span><span class="sxs-lookup"><span data-stu-id="f13a1-145">This command starts an interactive session with the Server01 computer.</span></span> <span data-ttu-id="f13a1-146">Er verwendet den **Port** -Parameter, um den Port anzugeben, und den **Credential** -Parameter, um das Konto eines Benutzers anzugeben, der über die Berechtigung zum Herstellen einer Verbindung mit dem Remote Computer verfügt.</span><span class="sxs-lookup"><span data-stu-id="f13a1-146">It uses the **Port** parameter to specify the port and the **Credential** parameter to specify the account of a user who has permission to connect to the remote computer.</span></span>

### <span data-ttu-id="f13a1-147">Beispiel 5: Beenden einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="f13a1-147">Example 5: Stop an interactive session</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01
[Server01]: PS> Exit-PSSession
PS>
```

<span data-ttu-id="f13a1-148">In diesem Beispiel wird veranschaulicht, wie eine interaktive Sitzung gestartet und beendet wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-148">This example shows how to start and stop an interactive session.</span></span> <span data-ttu-id="f13a1-149">Der erste Befehl verwendet das `Enter-PSSession` Cmdlet, um eine interaktive Sitzung mit dem Server01-Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="f13a1-149">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with the Server01 computer.</span></span>

<span data-ttu-id="f13a1-150">Der zweite Befehl verwendet das `Exit-PSSession` Cmdlet, um die Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-150">The second command uses the `Exit-PSSession` cmdlet to end the session.</span></span> <span data-ttu-id="f13a1-151">Sie können auch das **Exit** -Schlüsselwort verwenden, um die interaktive Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-151">You can also use the **Exit** keyword to end the interactive session.</span></span> <span data-ttu-id="f13a1-152">`Exit-PSSession` und **Exit** haben dieselbe Wirkung.</span><span class="sxs-lookup"><span data-stu-id="f13a1-152">`Exit-PSSession` and **Exit** have the same effect.</span></span>

### <span data-ttu-id="f13a1-153">Beispiel 6: Starten einer interaktiven Sitzung mithilfe von SSH</span><span class="sxs-lookup"><span data-stu-id="f13a1-153">Example 6: Start an interactive session using SSH</span></span>

```powershell
PS> Enter-PSSession -HostName UserA@LinuxServer01
```

<span data-ttu-id="f13a1-154">Dieses Beispiel zeigt, wie eine interaktive Sitzung mithilfe von Secure Shell (SSH) gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-154">This example shows how to start an interactive session using Secure Shell (SSH).</span></span> <span data-ttu-id="f13a1-155">Wenn SSH auf dem Remote Computer für die Eingabe von Kenn Wörtern konfiguriert ist, erhalten Sie eine Kenn Wort Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="f13a1-155">If SSH is configured on the remote computer to prompt for passwords then you will get a password prompt.</span></span>
<span data-ttu-id="f13a1-156">Andernfalls müssen Sie die SSH-Schlüssel basierte Benutzerauthentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-156">Otherwise you will have to use SSH key based user authentication.</span></span>

### <span data-ttu-id="f13a1-157">Beispiel 7: Starten einer interaktiven Sitzung mithilfe von SSH und angeben des Ports und des Benutzer Authentifizierungs Schlüssels</span><span class="sxs-lookup"><span data-stu-id="f13a1-157">Example 7: Start an interactive session using SSH and specify the Port and user authentication key</span></span>

```powershell
PS> Enter-PSSession -HostName UserA@LinuxServer02:22 -KeyFilePath c:\<path>\userAKey_rsa
```

<span data-ttu-id="f13a1-158">Dieses Beispiel zeigt, wie eine interaktive Sitzung mithilfe von SSH gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-158">This example shows how to start an interactive session using SSH.</span></span> <span data-ttu-id="f13a1-159">Er verwendet den **Port** -Parameter, um den zu verwendenden Port anzugeben, und den **keyFilePath** -Parameter, um einen RSA-Schlüssel anzugeben, der zum Authentifizieren des Benutzers auf dem Remote Computer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-159">It uses the **Port** parameter to specify the port to use and the **KeyFilePath** parameter to specify an RSA key used to authenticate the user on the remote computer.</span></span>

## <span data-ttu-id="f13a1-160">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f13a1-160">PARAMETERS</span></span>

### <span data-ttu-id="f13a1-161">-Zuweisung Richtung</span><span class="sxs-lookup"><span data-stu-id="f13a1-161">-AllowRedirection</span></span>

<span data-ttu-id="f13a1-162">Ermöglicht die Umleitung dieser Verbindung an einen alternativen URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="f13a1-162">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="f13a1-163">Standardmäßig ist die Umleitung nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="f13a1-163">By default, redirection is not allowed.</span></span>

<span data-ttu-id="f13a1-164">Bei Verwendung des **ConnectionURI**-Parameters kann das Remoteziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f13a1-164">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="f13a1-165">Standardmäßig werden Verbindungen von PowerShell nicht umgeleitet, aber Sie können diesen Parameter verwenden, um die Umleitung der Verbindung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-165">By default, PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="f13a1-166">Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie den **MaximumConnectionRedirectionCount**-Optionswert der Sitzung ändern.</span><span class="sxs-lookup"><span data-stu-id="f13a1-166">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="f13a1-167">Verwenden Sie den **maximumredirect** -Parameter des `New-PSSessionOption` Cmdlets, oder legen Sie die **maximumconnectionredirectioncount** -Eigenschaft der `$PSSessionOption` Preference-Variablen fest.</span><span class="sxs-lookup"><span data-stu-id="f13a1-167">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="f13a1-168">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="f13a1-168">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-169">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="f13a1-169">-ApplicationName</span></span>

<span data-ttu-id="f13a1-170">Gibt das Anwendungsnamenssegment des Verbindungs-URI an.</span><span class="sxs-lookup"><span data-stu-id="f13a1-170">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="f13a1-171">Mit diesem Parameter können Sie den Anwendungsnamen angeben, wenn Sie den **ConnectionURI**-Parameter im Befehl nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-171">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="f13a1-172">Der Standardwert ist der Wert der Einstellungs `$PSSessionApplicationName` Variablen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="f13a1-172">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="f13a1-173">Wenn diese Einstellungsvariable nicht definiert ist, ist der Standardwert „WSMan“.</span><span class="sxs-lookup"><span data-stu-id="f13a1-173">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="f13a1-174">Dieser Wert ist für die meisten Verwendungsarten geeignet.</span><span class="sxs-lookup"><span data-stu-id="f13a1-174">This value is appropriate for most uses.</span></span> <span data-ttu-id="f13a1-175">Weitere Informationen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="f13a1-175">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="f13a1-176">Der **WinRM** -Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus.</span><span class="sxs-lookup"><span data-stu-id="f13a1-176">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="f13a1-177">Der Wert dieses Parameters sollte mit dem Wert der **URLPrefix**-Eigenschaft eines Listeners auf dem Remotecomputer übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-177">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-178">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="f13a1-178">-Authentication</span></span>

<span data-ttu-id="f13a1-179">Gibt den Mechanismus an, der zum Authentifizieren der Anmeldeinformationen des Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-179">Specifies the mechanism that is used to authenticate the user's credentials.</span></span> <span data-ttu-id="f13a1-180">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="f13a1-180">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f13a1-181">Standard</span><span class="sxs-lookup"><span data-stu-id="f13a1-181">Default</span></span>
- <span data-ttu-id="f13a1-182">Basic</span><span class="sxs-lookup"><span data-stu-id="f13a1-182">Basic</span></span>
- <span data-ttu-id="f13a1-183">CredSSP</span><span class="sxs-lookup"><span data-stu-id="f13a1-183">Credssp</span></span>
- <span data-ttu-id="f13a1-184">Digest</span><span class="sxs-lookup"><span data-stu-id="f13a1-184">Digest</span></span>
- <span data-ttu-id="f13a1-185">Kerberos</span><span class="sxs-lookup"><span data-stu-id="f13a1-185">Kerberos</span></span>
- <span data-ttu-id="f13a1-186">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="f13a1-186">Negotiate</span></span>
- <span data-ttu-id="f13a1-187">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="f13a1-187">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="f13a1-188">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="f13a1-188">The default value is Default.</span></span>

<span data-ttu-id="f13a1-189">Die kredssp-Authentifizierung ist nur in Windows Vista, Windows Server 2008 und höheren Versionen des Windows-Betriebssystems verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f13a1-189">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="f13a1-190">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="f13a1-190">For more information about the values of this parameter, see [AuthenticationMechanism Enum](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

<span data-ttu-id="f13a1-191">Vorsicht: die Authentifizierung der Credential Security Support Provider (kredssp), bei der die Anmelde Informationen des Benutzers an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. den Zugriff auf eine Remote Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="f13a1-191">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="f13a1-192">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="f13a1-192">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="f13a1-193">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-193">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, Uri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-194">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="f13a1-194">-CertificateThumbprint</span></span>

<span data-ttu-id="f13a1-195">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="f13a1-195">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="f13a1-196">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="f13a1-196">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="f13a1-197">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f13a1-197">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="f13a1-198">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="f13a1-198">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="f13a1-199">Um ein Zertifikat zu erhalten, verwenden Sie den `Get-Item` `Get-ChildItem` Befehl oder im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="f13a1-199">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-200">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="f13a1-200">-ComputerName</span></span>

<span data-ttu-id="f13a1-201">Gibt einen Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="f13a1-201">Specifies a computer name.</span></span> <span data-ttu-id="f13a1-202">Dieses Cmdlet startet eine interaktive Sitzung mit dem angegebenen Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="f13a1-202">This cmdlet starts an interactive session with the specified remote computer.</span></span> <span data-ttu-id="f13a1-203">Geben Sie nur einen Computernamen ein.</span><span class="sxs-lookup"><span data-stu-id="f13a1-203">Enter only one computer name.</span></span> <span data-ttu-id="f13a1-204">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="f13a1-204">The default is the local computer.</span></span>

<span data-ttu-id="f13a1-205">Geben Sie den NetBIOS-Namen, die IP-Adresse oder den vollqualifizierten Domänennamen des Computers ein.</span><span class="sxs-lookup"><span data-stu-id="f13a1-205">Type the NetBIOS name, the IP address, or the fully qualified domain name of the computer.</span></span> <span data-ttu-id="f13a1-206">Sie können einen Computernamen auch über die Pipeline an senden `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f13a1-206">You can also pipe a computer name to `Enter-PSSession`.</span></span>

<span data-ttu-id="f13a1-207">Um eine IP-Adresse im Wert des **Computername** -Parameters zu verwenden, muss der Befehl den **Credential** -Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="f13a1-207">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="f13a1-208">Außerdem muss der Computer für den HTTPS-Transport konfiguriert sein, oder die IP-Adresse des Remotecomputers muss in der WinRM TrustedHosts-Liste auf dem lokalen Computer enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="f13a1-208">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="f13a1-209">Anweisungen zum Hinzufügen eines Computer namens zur Liste "Treuhänder Hosts" finden Sie unter "Vorgehensweise beim Hinzufügen eines Computers zur Liste vertrauenswürdiger Hosts" in [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="f13a1-209">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="f13a1-210">Hinweis: in Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell mit der Option als Administrator ausführen starten, um den lokalen Computer in den Wert des **Computername** -Parameters einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-210">Note: In Windows Vista and later versions of the Windows operating system, to include the local computer in the value of the **ComputerName** parameter, you must start PowerShell with the Run as administrator option.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-211">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="f13a1-211">-ConfigurationName</span></span>

<span data-ttu-id="f13a1-212">Gibt die Sitzungskonfiguration an, die für die interaktive Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-212">Specifies the session configuration that is used for the interactive session.</span></span>

<span data-ttu-id="f13a1-213">Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="f13a1-213">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="f13a1-214">Wenn Sie nur den Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="f13a1-214">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span>

<span data-ttu-id="f13a1-215">Bei Verwendung mit SSH gibt dies das Subsystem an, das auf dem Ziel verwendet werden soll, wie in sshd_config definiert.</span><span class="sxs-lookup"><span data-stu-id="f13a1-215">When used with SSH, this specifies the subsystem to use on the target as defined in sshd_config.</span></span> <span data-ttu-id="f13a1-216">Der Standardwert für SSH ist das `powershell` Subsystem.</span><span class="sxs-lookup"><span data-stu-id="f13a1-216">The default value for SSH is the `powershell` subsystem.</span></span>

<span data-ttu-id="f13a1-217">Die Sitzungskonfiguration für eine Sitzung befindet sich auf dem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="f13a1-217">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="f13a1-218">Wenn die angegebene Sitzungskonfiguration auf dem Remotecomputer nicht vorhanden ist, führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="f13a1-218">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="f13a1-219">Der Standardwert ist der Wert der Einstellungs `$PSSessionConfigurationName` Variablen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="f13a1-219">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="f13a1-220">Wenn diese Einstellungsvariable nicht festgelegt ist, ist die Standardeinstellung „Microsoft.PowerShell“.</span><span class="sxs-lookup"><span data-stu-id="f13a1-220">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="f13a1-221">Weitere Informationen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="f13a1-221">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri, VMId, VMName, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-222">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="f13a1-222">-ConnectionUri</span></span>

<span data-ttu-id="f13a1-223">Gibt einen URI an, der den Verbindungs Endpunkt für die Sitzung definiert.</span><span class="sxs-lookup"><span data-stu-id="f13a1-223">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="f13a1-224">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="f13a1-224">The URI must be fully qualified.</span></span> <span data-ttu-id="f13a1-225">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f13a1-225">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="f13a1-226">Der Standardwert lautet:</span><span class="sxs-lookup"><span data-stu-id="f13a1-226">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="f13a1-227">Wenn Sie keinen **ConnectionURI** angeben, können Sie die Parameter **UseSSL**, **ComputerName**, **Port** und **ApplicationName** zur Angabe der **ConnectionURI**-Werte verwenden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-227">If you do not specify a **ConnectionURI**, you can use the **UseSSL**, **ComputerName**, **Port**, and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="f13a1-228">Gültige Werte für das Transport-Segment des URI sind „HTTP“ und „HTTPS“.</span><span class="sxs-lookup"><span data-stu-id="f13a1-228">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="f13a1-229">Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mithilfe von Standardports erstellt: 80 für http und 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f13a1-229">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created by using standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="f13a1-230">Wenn Sie die Standardports für PowerShell-Remoting verwenden möchten, geben Sie Port 5985 für http oder 5986 für HTTPS an.</span><span class="sxs-lookup"><span data-stu-id="f13a1-230">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="f13a1-231">Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert PowerShell die Umleitung, es sei denn, Sie verwenden den Parameter " **Zuweisung** " im Befehl.</span><span class="sxs-lookup"><span data-stu-id="f13a1-231">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri
Parameter Sets: Uri
Aliases: URI, CU

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-232">-Containerid</span><span class="sxs-lookup"><span data-stu-id="f13a1-232">-ContainerId</span></span>

<span data-ttu-id="f13a1-233">Gibt die ID eines Containers an.</span><span class="sxs-lookup"><span data-stu-id="f13a1-233">Specifies the ID of a container.</span></span>

```yaml
Type: System.String
Parameter Sets: ContainerId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-234">-Credential</span><span class="sxs-lookup"><span data-stu-id="f13a1-234">-Credential</span></span>

<span data-ttu-id="f13a1-235">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="f13a1-235">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="f13a1-236">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f13a1-236">The default is the current user.</span></span>

<span data-ttu-id="f13a1-237">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f13a1-237">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="f13a1-238">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f13a1-238">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="f13a1-239">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f13a1-239">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="f13a1-240">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="f13a1-240">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, Uri, VMId, VMName
Aliases:

Required: True (VMId, VMName), False (ComputerName, Uri)
Position: 1
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-241">-Enablenetworkaccess</span><span class="sxs-lookup"><span data-stu-id="f13a1-241">-EnableNetworkAccess</span></span>

<span data-ttu-id="f13a1-242">Gibt an, dass mit diesem Cmdlet Loopback Sitzungen ein interaktives Sicherheits Token hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-242">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="f13a1-243">Mit dem interaktiven Token können Sie die Befehle in der Loopbacksitzung ausführen, um Daten von anderen Computern abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-243">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="f13a1-244">Beispielsweise können Sie einen Befehl in der Sitzung ausführen, mit dem XML-Dateien von einem Remotecomputer auf den lokalen Computer kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-244">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="f13a1-245">Eine Loopback Sitzung ist eine **PSSession** , die auf demselben computerbasiert und endet.</span><span class="sxs-lookup"><span data-stu-id="f13a1-245">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="f13a1-246">Um eine Loopback Sitzung zu erstellen, lassen Sie den **Computername** -Parameter aus, oder legen Sie seinen Wert auf fest.</span><span class="sxs-lookup"><span data-stu-id="f13a1-246">To create a loopback session, omit the **ComputerName** parameter or set its value to .</span></span> <span data-ttu-id="f13a1-247">(Punkt), localhost oder der Name des lokalen Computers.</span><span class="sxs-lookup"><span data-stu-id="f13a1-247">(dot), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="f13a1-248">Standardmäßig werden Loopback Sitzungen mit einem Netzwerk Token erstellt, das möglicherweise nicht über ausreichende Berechtigungen zum Authentifizieren bei Remote Computern verfügt.</span><span class="sxs-lookup"><span data-stu-id="f13a1-248">By default, loopback sessions are created by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="f13a1-249">Der **EnableNetworkAccess**-Parameter ist nur bei Loopbacksitzungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="f13a1-249">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="f13a1-250">Wenn Sie **enablenetworkaccess** verwenden, wenn Sie eine Sitzung auf einem Remote Computer erstellen, ist der Befehl erfolgreich, aber der-Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f13a1-250">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="f13a1-251">Sie können auch Remotezugriff in einer Loopbacksitzung erlauben, indem Sie den **CredSSP**-Wert des **Authentication**-Parameters verwenden, der die Anmeldeinformationen für die Sitzung an andere Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="f13a1-251">You can also allow remote access in a loopback session by using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="f13a1-252">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f13a1-252">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-253">-HostName</span><span class="sxs-lookup"><span data-stu-id="f13a1-253">-HostName</span></span>

<span data-ttu-id="f13a1-254">Gibt einen Computernamen für eine Secure Shell (SSH)-basierte Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="f13a1-254">Specifies a computer name for a Secure Shell (SSH) based connection.</span></span> <span data-ttu-id="f13a1-255">Dies ähnelt dem **Computername** -Parameter, mit dem Unterschied, dass die Verbindung mit dem Remote Computer anstelle von Windows WinRM über SSH hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-255">This is similar to the **ComputerName** parameter except that the connection to the remote computer is made using SSH rather than Windows WinRM.</span></span> <span data-ttu-id="f13a1-256">Dieser Parameter unterstützt die Angabe des Benutzernamens und/oder Ports als Teil des Hostname-Parameter Werts unter Verwendung des Formulars `user@hostname:port` .</span><span class="sxs-lookup"><span data-stu-id="f13a1-256">This parameter supports specifying the user name and/or port as part of the host name parameter value using the form `user@hostname:port`.</span></span> <span data-ttu-id="f13a1-257">Der als Teil des Host namens angegebene Benutzername und/oder Port `-UserName` `-Port` hat Vorrang vor den Parametern und.</span><span class="sxs-lookup"><span data-stu-id="f13a1-257">The user name and/or port specified as part of the host name takes precedence over the `-UserName` and `-Port` parameters, if specified.</span></span> <span data-ttu-id="f13a1-258">Dadurch können mehrere Computernamen an diesen Parameter übergeben werden, bei denen einige bestimmte Benutzernamen und/oder Ports aufweisen, während andere Benutzer den Benutzernamen und/oder den Port aus den `-UserName` `-Port` Parametern und verwenden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-258">This allows passing multiple computer names to this parameter where some have specific user names and/or ports, while others use the user name and/or port from the `-UserName` and `-Port` parameters.</span></span>

<span data-ttu-id="f13a1-259">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f13a1-259">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-260">-Id</span><span class="sxs-lookup"><span data-stu-id="f13a1-260">-Id</span></span>

<span data-ttu-id="f13a1-261">Gibt die ID einer vorhandenen Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="f13a1-261">Specifies the ID of an existing session.</span></span> <span data-ttu-id="f13a1-262">`Enter-PSSession` verwendet die angegebene Sitzung für die interaktive Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f13a1-262">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="f13a1-263">Verwenden Sie das-Cmdlet, um die ID einer Sitzung zu ermitteln `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f13a1-263">To find the ID of a session, use the `Get-PSSession` cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Id
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-264">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="f13a1-264">-InstanceId</span></span>

<span data-ttu-id="f13a1-265">Gibt die Instanz-ID einer vorhandenen Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="f13a1-265">Specifies the instance ID of an existing session.</span></span> <span data-ttu-id="f13a1-266">`Enter-PSSession` verwendet die angegebene Sitzung für die interaktive Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f13a1-266">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="f13a1-267">Die Instanz-ID ist eine GUID.</span><span class="sxs-lookup"><span data-stu-id="f13a1-267">The instance ID is a GUID.</span></span> <span data-ttu-id="f13a1-268">Verwenden Sie das-Cmdlet, um die Instanz-ID einer Sitzung zu ermitteln `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f13a1-268">To find the instance ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="f13a1-269">Sie können auch die Parameter " **Session**", " **Name**" oder " **ID** " verwenden, um eine vorhandene Sitzung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f13a1-269">You can also use the **Session**, **Name**, or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="f13a1-270">Oder Sie können den **Computername** -Parameter verwenden, um eine temporäre Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="f13a1-270">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

```yaml
Type: System.Guid
Parameter Sets: InstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-271">-KeyFilePath</span><span class="sxs-lookup"><span data-stu-id="f13a1-271">-KeyFilePath</span></span>

<span data-ttu-id="f13a1-272">Gibt einen Schlüssel Dateipfad an, der von Secure Shell (SSH) zum Authentifizieren eines Benutzers auf einem Remote Computer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-272">Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.</span></span>

<span data-ttu-id="f13a1-273">SSH ermöglicht die Durchführung der Benutzerauthentifizierung über private/öffentliche Schlüssel als Alternative zur grundlegenden Kenn Wort Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f13a1-273">SSH allows user authentication to be performed via private/public keys as an alternative to basic password authentication.</span></span> <span data-ttu-id="f13a1-274">Wenn der Remote Computer für die Schlüssel Authentifizierung konfiguriert ist, kann dieser Parameter verwendet werden, um den Schlüssel zur Identifizierung des Benutzers bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-274">If the remote computer is configured for key authentication then this parameter can be used to provide the key that identifies the user.</span></span>

<span data-ttu-id="f13a1-275">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f13a1-275">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-276">-Name</span><span class="sxs-lookup"><span data-stu-id="f13a1-276">-Name</span></span>

<span data-ttu-id="f13a1-277">Gibt den Anzeigenamen einer vorhandenen Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="f13a1-277">Specifies the friendly name of an existing session.</span></span> <span data-ttu-id="f13a1-278">`Enter-PSSession` verwendet die angegebene Sitzung für die interaktive Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f13a1-278">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="f13a1-279">Wenn der angegebene Name mit mehr als einer Sitzung übereinstimmt, führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="f13a1-279">If the name that you specify matches more than one session, the command fails.</span></span> <span data-ttu-id="f13a1-280">Sie können auch die Parameter " **Session**", " **InstanceId**" oder " **ID** " verwenden, um eine vorhandene Sitzung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f13a1-280">You can also use the **Session**, **InstanceID**, or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="f13a1-281">Oder Sie können den **Computername** -Parameter verwenden, um eine temporäre Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="f13a1-281">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

<span data-ttu-id="f13a1-282">Um einen anzeigen Amen für eine Sitzung zu erstellen, verwenden Sie den **Name** -Parameter des `New-PSSession` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f13a1-282">To establish a friendly name for a session, use the **Name** parameter of the `New-PSSession` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-283">-Port</span><span class="sxs-lookup"><span data-stu-id="f13a1-283">-Port</span></span>

<span data-ttu-id="f13a1-284">Gibt den Netzwerkport auf dem Remote Computer an, der für diesen Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-284">Specifies the network port on the remote computer that is used for this command.</span></span>

<span data-ttu-id="f13a1-285">In PowerShell 6,0 wurde dieser Parameter im **Hostname** -Parametersatz angegeben, der Secure Shell (SSH)-Verbindungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f13a1-285">In PowerShell 6.0 this parameter was inlcuded in the **HostName** parameter set which supports Secure Shell (SSH) connections.</span></span>

<span data-ttu-id="f13a1-286">**WinRM (Computername-Parametersatz)**</span><span class="sxs-lookup"><span data-stu-id="f13a1-286">**WinRM (ComputerName parameter set)**</span></span>

<span data-ttu-id="f13a1-287">Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören.</span><span class="sxs-lookup"><span data-stu-id="f13a1-287">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="f13a1-288">Die Standardports sind 5985. Dies ist der WinRM-Port für http und 5986 (der WinRM-Port für HTTPS).</span><span class="sxs-lookup"><span data-stu-id="f13a1-288">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="f13a1-289">Bevor ein alternativer Port verwendet werden kann, müssen Sie den WinRM-Listener auf dem Remotecomputer für das Abhören an diesen Port konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f13a1-289">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="f13a1-290">Verwenden Sie die folgenden Befehle, um den Listener zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f13a1-290">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="f13a1-291">Verwenden Sie den **Port**-Parameter nur, wenn es unbedingt notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="f13a1-291">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="f13a1-292">Die Porteinstellung im Befehl gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-292">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="f13a1-293">Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-293">An alternate port setting might prevent the command from running on all computers.</span></span>

<span data-ttu-id="f13a1-294">**SSH (Hostname-Parametersatz)**</span><span class="sxs-lookup"><span data-stu-id="f13a1-294">**SSH (HostName parameter set)**</span></span>

<span data-ttu-id="f13a1-295">Zum Herstellen einer Verbindung mit einem Remote Computer muss der Remote Computer mit dem SSH-Dienst (sshd) konfiguriert sein, und der Port, der von der Verbindung verwendet wird, muss überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-295">To connect to a remote computer, the remote computer must be configured with the SSH service (SSHD) and must be listening on the port that the connection uses.</span></span> <span data-ttu-id="f13a1-296">Der Standardport für SSH ist 22.</span><span class="sxs-lookup"><span data-stu-id="f13a1-296">The default port for SSH is 22.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-297">-Runasadministrator</span><span class="sxs-lookup"><span data-stu-id="f13a1-297">-RunAsAdministrator</span></span>

<span data-ttu-id="f13a1-298">Gibt an, dass die **PSSession** als Administrator ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-298">Indicates that the **PSSession** runs as administrator.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-299">-Sitzung</span><span class="sxs-lookup"><span data-stu-id="f13a1-299">-Session</span></span>

<span data-ttu-id="f13a1-300">Gibt eine PowerShell-Sitzung (**PSSession**) an, die für die interaktive Sitzung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f13a1-300">Specifies a PowerShell session (**PSSession**) to use for the interactive session.</span></span> <span data-ttu-id="f13a1-301">Dieser Parameter akzeptiert ein Sitzungsobjekt.</span><span class="sxs-lookup"><span data-stu-id="f13a1-301">This parameter takes a session object.</span></span> <span data-ttu-id="f13a1-302">Sie können auch den **Namen**, die **InstanceId** oder die **ID** -Parameter verwenden, um eine **PSSession** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f13a1-302">You can also use the **Name**, **InstanceID**, or **ID** parameters to specify a **PSSession**.</span></span>

<span data-ttu-id="f13a1-303">Geben Sie eine Variable ein, die ein Sitzungs Objekt oder einen Befehl enthält, mit dem ein Sitzungs Objekt erstellt oder abgerufen wird, z. b. ein- `New-PSSession` oder- `Get-PSSession` Befehl</span><span class="sxs-lookup"><span data-stu-id="f13a1-303">Enter a variable that contains a session object or a command that creates or gets a session object, such as a `New-PSSession` or `Get-PSSession` command.</span></span> <span data-ttu-id="f13a1-304">Sie können ein Sitzungs Objekt auch über die Pipeline an senden `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f13a1-304">You can also pipe a session object to `Enter-PSSession`.</span></span> <span data-ttu-id="f13a1-305">Mithilfe dieses Parameters können Sie nur eine **PSSession** senden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-305">You can submit only one **PSSession** by using this parameter.</span></span> <span data-ttu-id="f13a1-306">Wenn Sie eine Variable eingeben, die mehr als eine **PSSession** enthält, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="f13a1-306">If you enter a variable that contains more than one **PSSession**, the command fails.</span></span>

<span data-ttu-id="f13a1-307">Wenn Sie `Exit-PSSession` oder das **Exit** -Schlüsselwort verwenden, wird die interaktive Sitzung beendet, die erstellte **PSSession** bleibt jedoch geöffnet und kann verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-307">When you use `Exit-PSSession` or the **EXIT** keyword, the interactive session ends, but the **PSSession** that you created remains open and available for use.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-308">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="f13a1-308">-SessionOption</span></span>

<span data-ttu-id="f13a1-309">Legt erweiterte Optionen für die Sitzung fest.</span><span class="sxs-lookup"><span data-stu-id="f13a1-309">Sets advanced options for the session.</span></span> <span data-ttu-id="f13a1-310">Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem `New-PSSessionOption` Cmdlet erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.</span><span class="sxs-lookup"><span data-stu-id="f13a1-310">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="f13a1-311">Die Standardwerte für die Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f13a1-311">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="f13a1-312">Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f13a1-312">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="f13a1-313">Die Sitzungs Optionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der `$PSSessionOption` Preference-Variablen und in der Sitzungs Konfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f13a1-313">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="f13a1-314">Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f13a1-314">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="f13a1-315">Eine Beschreibung der Sitzungs Optionen, einschließlich der Standardwerte, finden Sie unter `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="f13a1-315">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="f13a1-316">Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="f13a1-316">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="f13a1-317">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="f13a1-317">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-318">-Sshtransport</span><span class="sxs-lookup"><span data-stu-id="f13a1-318">-SSHTransport</span></span>

<span data-ttu-id="f13a1-319">Gibt an, dass die Remote Verbindung mithilfe von Secure Shell (SSH) hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-319">Indicates that the remote connection is established using Secure Shell (SSH).</span></span>

<span data-ttu-id="f13a1-320">Standardmäßig verwendet PowerShell Windows WinRM, um eine Verbindung mit einem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-320">By default PowerShell uses Windows WinRM to connect to a remote computer.</span></span> <span data-ttu-id="f13a1-321">Dieser Schalter zwingt PowerShell, den Hostname-Parametersatz zum Einrichten einer SSH-basierten Remote Verbindung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f13a1-321">This switch forces PowerShell to use the HostName parameter set for establishing an SSH based remote connection.</span></span>

<span data-ttu-id="f13a1-322">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f13a1-322">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-323">-Subsystem</span><span class="sxs-lookup"><span data-stu-id="f13a1-323">-Subsystem</span></span>

<span data-ttu-id="f13a1-324">Gibt das SSH-Subsystem an, das für die neue **PSSession** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-324">Specifies the SSH subsystem used for the new **PSSession**.</span></span>

<span data-ttu-id="f13a1-325">Gibt das Subsystem an, das auf dem Ziel verwendet werden soll, wie in sshd_config definiert.</span><span class="sxs-lookup"><span data-stu-id="f13a1-325">This specifies the subsystem to use on the target as defined in sshd_config.</span></span> <span data-ttu-id="f13a1-326">Das Subsystem startet eine bestimmte Version von PowerShell mit vordefinierten Parametern.</span><span class="sxs-lookup"><span data-stu-id="f13a1-326">The subsystem starts a specific version of PowerShell with predefined parameters.</span></span> <span data-ttu-id="f13a1-327">Wenn das angegebene Subsystem auf dem Remote Computer nicht vorhanden ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="f13a1-327">If the specified subsystem does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="f13a1-328">Wenn dieser Parameter nicht verwendet wird, ist der Standardwert das "PowerShell"-Subsystem.</span><span class="sxs-lookup"><span data-stu-id="f13a1-328">If this parameter is not used, the default is the 'powershell' subsystem.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-329">-UserName</span><span class="sxs-lookup"><span data-stu-id="f13a1-329">-UserName</span></span>

<span data-ttu-id="f13a1-330">Gibt den Benutzernamen für das Konto an, das verwendet wird, um eine Sitzung auf dem Remote Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-330">Specifies the user name for the account used to create a session on the remote computer.</span></span> <span data-ttu-id="f13a1-331">Die Benutzer Authentifizierungsmethode hängt davon ab, wie Secure Shell (SSH) auf dem Remote Computer konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-331">User authentication method will depend on how Secure Shell (SSH) is configured on the remote computer.</span></span>

<span data-ttu-id="f13a1-332">Wenn SSH für die einfache Kenn Wort Authentifizierung konfiguriert ist, werden Sie zur Eingabe des Benutzer Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f13a1-332">If SSH is configured for basic password authentication then you will be prompted for the user password.</span></span>

<span data-ttu-id="f13a1-333">Wenn SSH für die Schlüssel basierte Benutzerauthentifizierung konfiguriert ist, kann ein Schlüssel Dateipfad über den **keyFilePath** -Parameter bereitgestellt werden, und es wird keine Kenn Wort Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f13a1-333">If SSH is configured for key based user authentication then a key file path can be provided via the **KeyFilePath** parameter and no password prompt will occur.</span></span> <span data-ttu-id="f13a1-334">Beachten Sie, dass der Schlüssel **FilePath** -Parameter für die Schlüssel basierte Authentifizierung nicht benötigt wird, wenn sich die Client Benutzer Schlüsseldatei an einem bekannten SSH-Speicherort befindet. die Benutzerauthentifizierung erfolgt automatisch basierend auf dem Benutzernamen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-334">Note that if the client user key file is located in an SSH known location then the **KeyFilePath** parameter is not needed for key based authentication, and user authentication will occur automatically based on the user name.</span></span> <span data-ttu-id="f13a1-335">Weitere Informationen finden Sie in der SSH-Dokumentation zur Schlüssel basierten Benutzerauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f13a1-335">See SSH documentation about key based user authentication for more information.</span></span>

<span data-ttu-id="f13a1-336">Dies ist kein erforderlicher Parameter.</span><span class="sxs-lookup"><span data-stu-id="f13a1-336">This is not a required parameter.</span></span> <span data-ttu-id="f13a1-337">Wenn kein **username** -Parameter angegeben wird, wird der aktuelle Anmelde Name des Benutzers für die Verbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f13a1-337">If no **UserName** parameter is specified then the current log on user name is used for the connection.</span></span>

<span data-ttu-id="f13a1-338">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f13a1-338">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-339">-US-</span><span class="sxs-lookup"><span data-stu-id="f13a1-339">-UseSSL</span></span>

<span data-ttu-id="f13a1-340">Gibt an, dass dieses Cmdlet das Secure Sockets Layer (SSL)-Protokoll verwendet, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-340">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="f13a1-341">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f13a1-341">By default, SSL is not used.</span></span>

<span data-ttu-id="f13a1-342">WS-Management verschlüsselt alle über das Netzwerk übertragenen PowerShell-Inhalte.</span><span class="sxs-lookup"><span data-stu-id="f13a1-342">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="f13a1-343">Der Parameter " **eessl** " ist ein zusätzlicher Schutz, der die Daten über eine HTTPS-Verbindung anstelle einer HTTP-Verbindung sendet.</span><span class="sxs-lookup"><span data-stu-id="f13a1-343">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="f13a1-344">Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port, der für den Befehl verwendet wird, nicht verfügbar ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="f13a1-344">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-345">-VMID</span><span class="sxs-lookup"><span data-stu-id="f13a1-345">-VMId</span></span>

<span data-ttu-id="f13a1-346">Gibt die ID einer virtuellen Maschine an.</span><span class="sxs-lookup"><span data-stu-id="f13a1-346">Specifies the ID of a virtual machine.</span></span>

```yaml
Type: System.Guid
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-347">-VMName</span><span class="sxs-lookup"><span data-stu-id="f13a1-347">-VMName</span></span>

<span data-ttu-id="f13a1-348">Gibt den Namen eines virtuellen Computers an.</span><span class="sxs-lookup"><span data-stu-id="f13a1-348">Specifies the name of a virtual machine.</span></span>

```yaml
Type: System.String
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f13a1-349">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f13a1-349">CommonParameters</span></span>

<span data-ttu-id="f13a1-350">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f13a1-350">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f13a1-351">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f13a1-351">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f13a1-352">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f13a1-352">INPUTS</span></span>

### <span data-ttu-id="f13a1-353">System. String, System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="f13a1-353">System.String, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="f13a1-354">Sie können einen Computernamen, eine Zeichenfolge oder ein Sitzungs Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="f13a1-354">You can pipe a computer name, as a string, or a session object to this cmdlet.</span></span>

## <span data-ttu-id="f13a1-355">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f13a1-355">OUTPUTS</span></span>

### <span data-ttu-id="f13a1-356">Keine</span><span class="sxs-lookup"><span data-stu-id="f13a1-356">None</span></span>

<span data-ttu-id="f13a1-357">Das Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="f13a1-357">The cmdlet does not return any output.</span></span>

## <span data-ttu-id="f13a1-358">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f13a1-358">NOTES</span></span>

<span data-ttu-id="f13a1-359">Um eine Verbindung zu einem Remotecomputer herzustellen, müssen Sie Mitglied der Gruppe „Administratoren“ auf dem Remotecomputer sein.</span><span class="sxs-lookup"><span data-stu-id="f13a1-359">To connect to a remote computer, you must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="f13a1-360">Um eine interaktive Sitzung auf dem lokalen Computer zu starten, müssen Sie PowerShell mit der Option **als Administrator ausführen** starten.</span><span class="sxs-lookup"><span data-stu-id="f13a1-360">To start an interactive session on the local computer, you must start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="f13a1-361">Wenn Sie verwenden `Enter-PSSession` , wird Ihr Benutzerprofil auf dem Remote Computer für die interaktive Sitzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f13a1-361">When you use `Enter-PSSession`, your user profile on the remote computer is used for the interactive session.</span></span> <span data-ttu-id="f13a1-362">Die Befehle im Remote Benutzerprofil, einschließlich der Befehle zum Hinzufügen von PowerShell-Modulen und zum Ändern der Eingabeaufforderung, werden ausgeführt, bevor die Remote Eingabeaufforderung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f13a1-362">The commands in the remote user profile, including commands to add PowerShell modules and to change the command prompt, run before the remote prompt is displayed.</span></span>

<span data-ttu-id="f13a1-363">`Enter-PSSession` verwendet die Benutzeroberflächen Kultur-Einstellung auf dem lokalen Computer für die interaktive Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f13a1-363">`Enter-PSSession` uses the UI culture setting on the local computer for the interactive session.</span></span> <span data-ttu-id="f13a1-364">Um die lokale Benutzeroberflächen Kultur zu ermitteln, verwenden Sie die `$UICulture` Automatische Variable.</span><span class="sxs-lookup"><span data-stu-id="f13a1-364">To find the local UI culture, use the `$UICulture` automatic variable.</span></span>

<span data-ttu-id="f13a1-365">`Enter-PSSession` erfordert die `Get-Command` `Out-Default` `Exit-PSSession` Cmdlets, und.</span><span class="sxs-lookup"><span data-stu-id="f13a1-365">`Enter-PSSession` requires the `Get-Command`, `Out-Default`, and `Exit-PSSession` cmdlets.</span></span> <span data-ttu-id="f13a1-366">Wenn diese Cmdlets in der Sitzungs Konfiguration auf dem Remote Computer nicht enthalten sind, können die Befehle nicht ausgeführt werden `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f13a1-366">If these cmdlets are not included in the session configuration on the remote computer, the `Enter-PSSession` commands fails.</span></span>

<span data-ttu-id="f13a1-367">Im Gegensatz zu `Invoke-Command` , das die Befehle vor dem Senden an den Remote Computer analysiert und interpretiert, `Enter-PSSession` sendet die Befehle ohne Interpretation direkt an den Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="f13a1-367">Unlike `Invoke-Command`, which parses and interprets the commands before it sends them to the remote computer, `Enter-PSSession` sends the commands directly to the remote computer without interpretation.</span></span>

<span data-ttu-id="f13a1-368">Wenn die Sitzung, die Sie eingeben möchten, mit der Verarbeitung eines Befehls ausgelastet ist, kann es zu einer Verzögerung kommen, bevor PowerShell auf den `Enter-PSSession` Befehl antwortet.</span><span class="sxs-lookup"><span data-stu-id="f13a1-368">If the session you want to enter is busy processing a command, there might be a delay before PowerShell responds to the `Enter-PSSession` command.</span></span> <span data-ttu-id="f13a1-369">Sie sind verbunden, sobald die Sitzung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f13a1-369">You are connected as soon as the session is available.</span></span> <span data-ttu-id="f13a1-370">Um den Befehl abzubrechen `Enter-PSSession` , drücken Sie <kbd>STRG</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="f13a1-370">To cancel the `Enter-PSSession` command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

<span data-ttu-id="f13a1-371">Der **Hostname** -Parametersatz wurde ab PowerShell 6,0 eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-371">The **HostName** parameter set was included starting with PowerShell 6.0.</span></span> <span data-ttu-id="f13a1-372">Es wurde hinzugefügt, um PowerShell-Remoting basierend auf Secure Shell (SSH) bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f13a1-372">It was added to provide PowerShell remoting based on Secure Shell (SSH).</span></span> <span data-ttu-id="f13a1-373">Sowohl SSH als auch PowerShell werden auf mehreren Plattformen (Windows, Linux, macOS) unterstützt, und PowerShell-Remoting funktioniert auf diesen Plattformen, auf denen PowerShell und SSH installiert und konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="f13a1-373">Both SSH and PowerShell are supported on multiple platforms (Windows, Linux, macOS) and PowerShell remoting will work over these platforms where PowerShell and SSH are installed and configured.</span></span> <span data-ttu-id="f13a1-374">Dies ist vom vorherigen Windows-Remoting getrennt, das auf WinRM basiert, und ein Großteil der speziellen Features und Einschränkungen von WinRM ist nicht anwendbar.</span><span class="sxs-lookup"><span data-stu-id="f13a1-374">This is separate from the previous Windows only remoting that is based on WinRM and much of the WinRM specific features and limitations do not apply.</span></span> <span data-ttu-id="f13a1-375">Beispielsweise werden WinRM-basierte Kontingente, Sitzungs Optionen, benutzerdefinierte Endpunkt Konfiguration und Features zum Trennen und Wiederherstellen von Verbindungen derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f13a1-375">For example, WinRM based quotas, session options, custom endpoint configuration, and disconnect/reconnect features are currently not supported.</span></span> <span data-ttu-id="f13a1-376">Weitere Informationen zum Einrichten von PowerShell-SSH-Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="f13a1-376">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

<span data-ttu-id="f13a1-377">Vor PowerShell 7.1 unterstützte das Remoting über SSH keine Remotesitzungen über einen zweiten Hop.</span><span class="sxs-lookup"><span data-stu-id="f13a1-377">Prior to PowerShell 7.1, remoting over SSH did not support second-hop remote sessions.</span></span> <span data-ttu-id="f13a1-378">Diese Funktion war auf Sitzungen beschränkt, die WinRM verwendeten.</span><span class="sxs-lookup"><span data-stu-id="f13a1-378">This capability was limited to sessions using WinRM.</span></span> <span data-ttu-id="f13a1-379">PowerShell 7.1 ermöglicht, dass `Enter-PSSession` und `Enter-PSHostProcess` in jeder interaktiven Remotesitzung funktionieren.</span><span class="sxs-lookup"><span data-stu-id="f13a1-379">PowerShell 7.1 allows `Enter-PSSession` and `Enter-PSHostProcess` to work from within any interactive remote session.</span></span>

## <span data-ttu-id="f13a1-380">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f13a1-380">RELATED LINKS</span></span>

[<span data-ttu-id="f13a1-381">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="f13a1-381">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="f13a1-382">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="f13a1-382">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="f13a1-383">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="f13a1-383">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="f13a1-384">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="f13a1-384">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="f13a1-385">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="f13a1-385">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="f13a1-386">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="f13a1-386">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="f13a1-387">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="f13a1-387">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="f13a1-388">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="f13a1-388">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="f13a1-389">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="f13a1-389">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="f13a1-390">about_Remote</span><span class="sxs-lookup"><span data-stu-id="f13a1-390">about_Remote</span></span>](About/about_Remote.md)
