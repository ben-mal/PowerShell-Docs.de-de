---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSSession
ms.openlocfilehash: 40d9da7d2e7e3233608b893b026c2b89c7155ab1
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "93218935"
---
# <span data-ttu-id="0507c-103">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="0507c-103">Enter-PSSession</span></span>

## <span data-ttu-id="0507c-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0507c-104">SYNOPSIS</span></span>
<span data-ttu-id="0507c-105">Startet eine interaktive Sitzung mit einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="0507c-105">Starts an interactive session with a remote computer.</span></span>

## <span data-ttu-id="0507c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0507c-106">SYNTAX</span></span>

### <span data-ttu-id="0507c-107">Computername (Standard)</span><span class="sxs-lookup"><span data-stu-id="0507c-107">ComputerName (Default)</span></span>

```
Enter-PSSession [-ComputerName] <String> [-EnableNetworkAccess] [-Credential <PSCredential>]
 [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL] [-ApplicationName <String>]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="0507c-108">Sitzung</span><span class="sxs-lookup"><span data-stu-id="0507c-108">Session</span></span>

```
Enter-PSSession [[-Session] <PSSession>] [<CommonParameters>]
```

### <span data-ttu-id="0507c-109">Uri</span><span class="sxs-lookup"><span data-stu-id="0507c-109">Uri</span></span>

```
Enter-PSSession [[-ConnectionUri] <Uri>] [-EnableNetworkAccess] [-Credential <PSCredential>]
 [-ConfigurationName <String>] [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="0507c-110">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0507c-110">InstanceId</span></span>

```
Enter-PSSession [-InstanceId <Guid>] [<CommonParameters>]
```

### <span data-ttu-id="0507c-111">Id</span><span class="sxs-lookup"><span data-stu-id="0507c-111">Id</span></span>

```
Enter-PSSession [[-Id] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="0507c-112">Name</span><span class="sxs-lookup"><span data-stu-id="0507c-112">Name</span></span>

```
Enter-PSSession [-Name <String>] [<CommonParameters>]
```

### <span data-ttu-id="0507c-113">VMId</span><span class="sxs-lookup"><span data-stu-id="0507c-113">VMId</span></span>

```
Enter-PSSession [-VMId] <Guid> -Credential <PSCredential> [-ConfigurationName <String>] [<CommonParameters>]
```

### <span data-ttu-id="0507c-114">VMName</span><span class="sxs-lookup"><span data-stu-id="0507c-114">VMName</span></span>

```
Enter-PSSession [-VMName] <String> -Credential <PSCredential> [-ConfigurationName <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="0507c-115">ContainerId</span><span class="sxs-lookup"><span data-stu-id="0507c-115">ContainerId</span></span>

```
Enter-PSSession [-ContainerId] <String> [-ConfigurationName <String>] [-RunAsAdministrator]
 [<CommonParameters>]
```

## <span data-ttu-id="0507c-116">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0507c-116">DESCRIPTION</span></span>

<span data-ttu-id="0507c-117">Mit dem- `Enter-PSSession` Cmdlet wird eine interaktive Sitzung mit einem einzelnen Remote Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="0507c-117">The `Enter-PSSession` cmdlet starts an interactive session with a single remote computer.</span></span> <span data-ttu-id="0507c-118">Während der Sitzung werden die Befehle, die Sie eingeben, auf dem Remote Computer ausgeführt, so als würden Sie direkt auf dem Remote Computer eingeben.</span><span class="sxs-lookup"><span data-stu-id="0507c-118">During the session, the commands that you type run on the remote computer, just as if you were typing directly on the remote computer.</span></span> <span data-ttu-id="0507c-119">Sie können sich zu einem Zeitpunkt jeweils nur in einer interaktiven Sitzung befinden.</span><span class="sxs-lookup"><span data-stu-id="0507c-119">You can have only one interactive session at a time.</span></span>

<span data-ttu-id="0507c-120">Normalerweise verwenden Sie den **ComputerName** -Parameter, um den Namen des Remotecomputers anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0507c-120">Typically, you use the **ComputerName** parameter to specify the name of the remote computer.</span></span>
<span data-ttu-id="0507c-121">Sie können jedoch auch eine Sitzung verwenden, die Sie mit dem `New-PSSession` Cmdlet für die interaktive Sitzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="0507c-121">However, you can also use a session that you create by using the `New-PSSession` cmdlet for the interactive session.</span></span> <span data-ttu-id="0507c-122">Allerdings können Sie die `Disconnect-PSSession` `Connect-PSSession` Cmdlets, oder nicht verwenden, um die Verbindung mit `Receive-PSSession` einer interaktiven Sitzung zu trennen oder erneut eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0507c-122">However, you cannot use the `Disconnect-PSSession`, `Connect-PSSession`, or `Receive-PSSession` cmdlets to disconnect from or re-connect to an interactive session.</span></span>

<span data-ttu-id="0507c-123">Um die interaktive Sitzung zu beenden und die Verbindung mit dem Remote Computer zu trennen, verwenden Sie das- `Exit-PSSession` Cmdlet oder den-Typ `exit` .</span><span class="sxs-lookup"><span data-stu-id="0507c-123">To end the interactive session and disconnect from the remote computer, use the `Exit-PSSession` cmdlet, or type `exit`.</span></span>

## <span data-ttu-id="0507c-124">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0507c-124">EXAMPLES</span></span>

### <span data-ttu-id="0507c-125">Beispiel 1: Starten einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="0507c-125">Example 1: Start an interactive session</span></span>

```
PS C:\> Enter-PSSession
[localhost]: PS C:\>
```

<span data-ttu-id="0507c-126">Dieser Befehl startet eine interaktive Sitzung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="0507c-126">This command starts an interactive session on the local computer.</span></span> <span data-ttu-id="0507c-127">Die Eingabeaufforderung ändert sich, um anzugeben, dass die Befehle nun in einer anderen Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0507c-127">The command prompt changes to indicate that you are now running commands in a different session.</span></span>

<span data-ttu-id="0507c-128">Die eingegebenen Befehle werden in der neuen Sitzung ausgeführt, und die Ergebnisse werden als Text an die Standardsitzung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0507c-128">The commands that you enter run in the new session, and the results are returned to the default session as text.</span></span>

### <span data-ttu-id="0507c-129">Beispiel 2: Arbeiten mit einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="0507c-129">Example 2: Work with an interactive session</span></span>

<span data-ttu-id="0507c-130">Der erste Befehl verwendet das `Enter-PSSession` Cmdlet, um eine interaktive Sitzung mit Server01, einem Remote Computer, zu starten.</span><span class="sxs-lookup"><span data-stu-id="0507c-130">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with Server01, a remote computer.</span></span> <span data-ttu-id="0507c-131">Wenn die Sitzung startet, ändert sich die Eingabeaufforderung und enthält den Computernamen.</span><span class="sxs-lookup"><span data-stu-id="0507c-131">When the session starts, the command prompt changes to include the computer name.</span></span>
<span data-ttu-id="0507c-132">Mit dem zweiten Befehl wird der Windows PowerShell-Prozess abgerufen und die Ausgabe an die Process.txt Datei umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="0507c-132">The second command gets the Windows PowerShell process and redirects the output to the Process.txt file.</span></span> <span data-ttu-id="0507c-133">Der Befehl wird an den Remotecomputer gesendet, und die Datei wird auf dem Remotecomputer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0507c-133">The command is submitted to the remote computer, and the file is saved on the remote computer.</span></span>
<span data-ttu-id="0507c-134">Der dritte Befehl verwendet das **Exit** -Schlüsselwort, um die interaktive Sitzung zu beenden und die Verbindung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0507c-134">The third command uses the **Exit** keyword to end the interactive session and close the connection.</span></span>
<span data-ttu-id="0507c-135">Der vierte Befehl bestätigt, dass sich die Datei „Process.txt“ auf dem Remotecomputer befindet.</span><span class="sxs-lookup"><span data-stu-id="0507c-135">The fourth command confirms that the Process.txt file is on the remote computer.</span></span> <span data-ttu-id="0507c-136">`Get-ChildItem`Der Befehl ("dir") auf dem lokalen Computer kann die Datei nicht finden.</span><span class="sxs-lookup"><span data-stu-id="0507c-136">A `Get-ChildItem` ("dir") command on the local computer cannot find the file.</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS C:\>
[Server01]: PS C:\> Get-Process PowerShell > C:\ps-test\Process.txt
[Server01]: PS C:\> exit
PS C:\>
PS C:\> dir C:\ps-test\process.txt
Get-ChildItem : Cannot find path 'C:\ps-test\process.txt' because it does not exist.
At line:1 char:4
+ dir <<<<  c:\ps-test\process.txt
```

<span data-ttu-id="0507c-137">Dieser Befehl zeigt die Arbeitsweise in einer interaktiven Sitzung mit einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="0507c-137">This command shows how to work in an interactive session with a remote computer.</span></span>

### <span data-ttu-id="0507c-138">Beispiel 3: Verwenden des Session-Parameters</span><span class="sxs-lookup"><span data-stu-id="0507c-138">Example 3: Use the Session parameter</span></span>

```powershell
PS C:\> $s = New-PSSession -ComputerName Server01
PS C:\> Enter-PSSession -Session $s
[Server01]: PS C:\>
```

<span data-ttu-id="0507c-139">Diese Befehle verwenden den **Session** -Parameter von `Enter-PSSession` , um die interaktive Sitzung in einer vorhandenen Windows PowerShell-Sitzung ( **PSSession** ) auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0507c-139">These commands use the **Session** parameter of `Enter-PSSession` to run the interactive session in an existing Windows PowerShell session ( **PSSession** ).</span></span>

### <span data-ttu-id="0507c-140">Beispiel 4: Starten einer interaktiven Sitzung und angeben der Parameter für Port und Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="0507c-140">Example 4: Start an interactive session and specify the Port and Credential parameters</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01 -Port 90 -Credential Domain01\User01
[Server01]: PS C:\>
```

<span data-ttu-id="0507c-141">Dieser Befehl startet eine interaktive Sitzung mit dem Computer „Server01“.</span><span class="sxs-lookup"><span data-stu-id="0507c-141">This command starts an interactive session with the Server01 computer.</span></span> <span data-ttu-id="0507c-142">Er verwendet den **Port** -Parameter, um den Port anzugeben, und den **Credential** -Parameter, um das Konto eines Benutzers anzugeben, der über die Berechtigung zum Herstellen einer Verbindung mit dem Remote Computer verfügt.</span><span class="sxs-lookup"><span data-stu-id="0507c-142">It uses the **Port** parameter to specify the port and the **Credential** parameter to specify the account of a user who has permission to connect to the remote computer.</span></span>

### <span data-ttu-id="0507c-143">Beispiel 5: Beenden einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="0507c-143">Example 5: Stop an interactive session</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS C:\> Exit-PSSession
PS C:\>
```

<span data-ttu-id="0507c-144">In diesem Beispiel wird veranschaulicht, wie eine interaktive Sitzung gestartet und beendet wird.</span><span class="sxs-lookup"><span data-stu-id="0507c-144">This example shows how to start and stop an interactive session.</span></span> <span data-ttu-id="0507c-145">Der erste Befehl verwendet das `Enter-PSSession` Cmdlet, um eine interaktive Sitzung mit dem Server01-Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="0507c-145">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with the Server01 computer.</span></span>

<span data-ttu-id="0507c-146">Der zweite Befehl verwendet das `Exit-PSSession` Cmdlet, um die Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="0507c-146">The second command uses the `Exit-PSSession` cmdlet to end the session.</span></span> <span data-ttu-id="0507c-147">Sie können auch das **Exit** -Schlüsselwort verwenden, um die interaktive Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="0507c-147">You can also use the **Exit** keyword to end the interactive session.</span></span> <span data-ttu-id="0507c-148">`Exit-PSSession` und **Exit** haben dieselbe Wirkung.</span><span class="sxs-lookup"><span data-stu-id="0507c-148">`Exit-PSSession` and **Exit** have the same effect.</span></span>

## <span data-ttu-id="0507c-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0507c-149">PARAMETERS</span></span>

### <span data-ttu-id="0507c-150">-Zuweisung Richtung</span><span class="sxs-lookup"><span data-stu-id="0507c-150">-AllowRedirection</span></span>

<span data-ttu-id="0507c-151">Ermöglicht die Umleitung dieser Verbindung an einen alternativen URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="0507c-151">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="0507c-152">Standardmäßig ist die Umleitung nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="0507c-152">By default, redirection is not allowed.</span></span>

<span data-ttu-id="0507c-153">Bei Verwendung des **ConnectionURI** -Parameters kann das Remoteziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0507c-153">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="0507c-154">Standardmäßig erfolgt mit Windows PowerShell keine Umleitung von Verbindungen, Sie können jedoch mit diesem Parameter die Umleitung von Verbindungen zulassen.</span><span class="sxs-lookup"><span data-stu-id="0507c-154">By default, Windows PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="0507c-155">Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie den **MaximumConnectionRedirectionCount** -Optionswert der Sitzung ändern.</span><span class="sxs-lookup"><span data-stu-id="0507c-155">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="0507c-156">Verwenden Sie den **maximumredirect** -Parameter des `New-PSSessionOption` Cmdlets, oder legen Sie die **maximumconnectionredirectioncount** -Eigenschaft der `$PSSessionOption` Preference-Variablen fest.</span><span class="sxs-lookup"><span data-stu-id="0507c-156">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="0507c-157">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="0507c-157">The default value is 5.</span></span>

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

### <span data-ttu-id="0507c-158">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="0507c-158">-ApplicationName</span></span>

<span data-ttu-id="0507c-159">Gibt das Anwendungsnamenssegment des Verbindungs-URI an.</span><span class="sxs-lookup"><span data-stu-id="0507c-159">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="0507c-160">Mit diesem Parameter können Sie den Anwendungsnamen angeben, wenn Sie den **ConnectionURI** -Parameter im Befehl nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="0507c-160">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="0507c-161">Der Standardwert ist der Wert der Einstellungs `$PSSessionApplicationName` Variablen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="0507c-161">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="0507c-162">Wenn diese Einstellungsvariable nicht definiert ist, ist der Standardwert „WSMan“.</span><span class="sxs-lookup"><span data-stu-id="0507c-162">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="0507c-163">Dieser Wert ist für die meisten Verwendungsarten geeignet.</span><span class="sxs-lookup"><span data-stu-id="0507c-163">This value is appropriate for most uses.</span></span> <span data-ttu-id="0507c-164">Weitere Informationen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="0507c-164">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="0507c-165">Der **WinRM** -Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus.</span><span class="sxs-lookup"><span data-stu-id="0507c-165">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="0507c-166">Der Wert dieses Parameters sollte mit dem Wert der **URLPrefix** -Eigenschaft eines Listeners auf dem Remotecomputer übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="0507c-166">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

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

### <span data-ttu-id="0507c-167">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0507c-167">-Authentication</span></span>

<span data-ttu-id="0507c-168">Gibt den Mechanismus an, der zum Authentifizieren der Anmeldeinformationen des Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0507c-168">Specifies the mechanism that is used to authenticate the user's credentials.</span></span> <span data-ttu-id="0507c-169">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="0507c-169">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0507c-170">Standard</span><span class="sxs-lookup"><span data-stu-id="0507c-170">Default</span></span>
- <span data-ttu-id="0507c-171">Basic</span><span class="sxs-lookup"><span data-stu-id="0507c-171">Basic</span></span>
- <span data-ttu-id="0507c-172">CredSSP</span><span class="sxs-lookup"><span data-stu-id="0507c-172">Credssp</span></span>
- <span data-ttu-id="0507c-173">Digest</span><span class="sxs-lookup"><span data-stu-id="0507c-173">Digest</span></span>
- <span data-ttu-id="0507c-174">Kerberos</span><span class="sxs-lookup"><span data-stu-id="0507c-174">Kerberos</span></span>
- <span data-ttu-id="0507c-175">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="0507c-175">Negotiate</span></span>
- <span data-ttu-id="0507c-176">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="0507c-176">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="0507c-177">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="0507c-177">The default value is Default.</span></span>

<span data-ttu-id="0507c-178">Die kredssp-Authentifizierung ist nur in Windows Vista, Windows Server 2008 und höheren Versionen des Windows-Betriebssystems verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0507c-178">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="0507c-179">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0507c-179">For more information about the values of this parameter, see [AuthenticationMechanism Enum](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

<span data-ttu-id="0507c-180">Vorsicht: die Authentifizierung der Credential Security Support Provider (kredssp), bei der die Anmelde Informationen des Benutzers an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. den Zugriff auf eine Remote Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="0507c-180">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="0507c-181">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="0507c-181">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="0507c-182">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0507c-182">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="0507c-183">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="0507c-183">-CertificateThumbprint</span></span>

<span data-ttu-id="0507c-184">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="0507c-184">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="0507c-185">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="0507c-185">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="0507c-186">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0507c-186">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="0507c-187">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="0507c-187">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="0507c-188">Um ein Zertifikat zu erhalten, verwenden Sie den- `Get-Item` Befehl oder den- `Get-ChildItem` Befehl im Windows PowerShell-CERT:-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="0507c-188">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="0507c-189">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0507c-189">-ComputerName</span></span>

<span data-ttu-id="0507c-190">Gibt einen Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="0507c-190">Specifies a computer name.</span></span> <span data-ttu-id="0507c-191">Dieses Cmdlet startet eine interaktive Sitzung mit dem angegebenen Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="0507c-191">This cmdlet starts an interactive session with the specified remote computer.</span></span> <span data-ttu-id="0507c-192">Geben Sie nur einen Computernamen ein.</span><span class="sxs-lookup"><span data-stu-id="0507c-192">Enter only one computer name.</span></span> <span data-ttu-id="0507c-193">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="0507c-193">The default is the local computer.</span></span>

<span data-ttu-id="0507c-194">Geben Sie den NetBIOS-Namen, die IP-Adresse oder den vollqualifizierten Domänennamen des Computers ein.</span><span class="sxs-lookup"><span data-stu-id="0507c-194">Type the NetBIOS name, the IP address, or the fully qualified domain name of the computer.</span></span> <span data-ttu-id="0507c-195">Sie können einen Computernamen auch über die Pipeline an senden `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="0507c-195">You can also pipe a computer name to `Enter-PSSession`.</span></span>

<span data-ttu-id="0507c-196">Um eine IP-Adresse im Wert des **Computername** -Parameters zu verwenden, muss der Befehl den **Credential** -Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="0507c-196">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="0507c-197">Außerdem muss der Computer für den HTTPS-Transport konfiguriert sein, oder die IP-Adresse des Remotecomputers muss in der WinRM TrustedHosts-Liste auf dem lokalen Computer enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="0507c-197">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="0507c-198">Anweisungen zum Hinzufügen eines Computer namens zur Liste "Treuhänder Hosts" finden Sie unter "Vorgehensweise beim Hinzufügen eines Computers zur Liste vertrauenswürdiger Hosts" in [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="0507c-198">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="0507c-199">Hinweis: in Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie Windows PowerShell mit der Option als Administrator ausführen starten, um den lokalen Computer in den Wert des **Computername** -Parameters einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0507c-199">Note: In Windows Vista and later versions of the Windows operating system, to include the local computer in the value of the **ComputerName** parameter, you must start Windows PowerShell with the Run as administrator option.</span></span>

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

### <span data-ttu-id="0507c-200">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="0507c-200">-ConfigurationName</span></span>

<span data-ttu-id="0507c-201">Gibt die Sitzungskonfiguration an, die für die interaktive Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0507c-201">Specifies the session configuration that is used for the interactive session.</span></span>

<span data-ttu-id="0507c-202">Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="0507c-202">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="0507c-203">Wenn Sie nur den Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="0507c-203">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span>

<span data-ttu-id="0507c-204">Die Sitzungskonfiguration für eine Sitzung befindet sich auf dem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="0507c-204">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="0507c-205">Wenn die angegebene Sitzungskonfiguration auf dem Remotecomputer nicht vorhanden ist, führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="0507c-205">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="0507c-206">Der Standardwert ist der Wert der Einstellungs `$PSSessionConfigurationName` Variablen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="0507c-206">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="0507c-207">Wenn diese Einstellungsvariable nicht festgelegt ist, ist die Standardeinstellung „Microsoft.PowerShell“.</span><span class="sxs-lookup"><span data-stu-id="0507c-207">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="0507c-208">Weitere Informationen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="0507c-208">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

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

### <span data-ttu-id="0507c-209">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="0507c-209">-ConnectionUri</span></span>

<span data-ttu-id="0507c-210">Gibt einen URI an, der den Verbindungs Endpunkt für die Sitzung definiert.</span><span class="sxs-lookup"><span data-stu-id="0507c-210">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="0507c-211">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="0507c-211">The URI must be fully qualified.</span></span> <span data-ttu-id="0507c-212">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0507c-212">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="0507c-213">Der Standardwert lautet:</span><span class="sxs-lookup"><span data-stu-id="0507c-213">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="0507c-214">Wenn Sie keinen **ConnectionURI** angeben, können Sie die Parameter **UseSSL** , **ComputerName** , **Port** und **ApplicationName** zur Angabe der **ConnectionURI** -Werte verwenden.</span><span class="sxs-lookup"><span data-stu-id="0507c-214">If you do not specify a **ConnectionURI** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="0507c-215">Gültige Werte für das Transport-Segment des URI sind „HTTP“ und „HTTPS“.</span><span class="sxs-lookup"><span data-stu-id="0507c-215">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="0507c-216">Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mithilfe von Standardports erstellt: 80 für http und 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0507c-216">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created by using standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="0507c-217">Um die Standardports für Windows PowerShell-Remoting zu verwenden, geben Sie Port 5985 für HTTP bzw. 5986 für HTTPS an.</span><span class="sxs-lookup"><span data-stu-id="0507c-217">To use the default ports for Windows PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="0507c-218">Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert Windows PowerShell die Umleitung, sofern Sie nicht den **AllowRedirection** -Parameter im Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="0507c-218">If the destination computer redirects the connection to a different URI, Windows PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

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

### <span data-ttu-id="0507c-219">-Containerid</span><span class="sxs-lookup"><span data-stu-id="0507c-219">-ContainerId</span></span>

<span data-ttu-id="0507c-220">Gibt die ID eines Containers an.</span><span class="sxs-lookup"><span data-stu-id="0507c-220">Specifies the ID of a container.</span></span>

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

### <span data-ttu-id="0507c-221">-Credential</span><span class="sxs-lookup"><span data-stu-id="0507c-221">-Credential</span></span>

<span data-ttu-id="0507c-222">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="0507c-222">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="0507c-223">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0507c-223">The default is the current user.</span></span>

<span data-ttu-id="0507c-224">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0507c-224">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="0507c-225">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="0507c-225">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="0507c-226">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0507c-226">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="0507c-227">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="0507c-227">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="0507c-228">-Enablenetworkaccess</span><span class="sxs-lookup"><span data-stu-id="0507c-228">-EnableNetworkAccess</span></span>

<span data-ttu-id="0507c-229">Gibt an, dass mit diesem Cmdlet Loopback Sitzungen ein interaktives Sicherheits Token hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0507c-229">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="0507c-230">Mit dem interaktiven Token können Sie die Befehle in der Loopbacksitzung ausführen, um Daten von anderen Computern abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0507c-230">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="0507c-231">Beispielsweise können Sie einen Befehl in der Sitzung ausführen, mit dem XML-Dateien von einem Remotecomputer auf den lokalen Computer kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="0507c-231">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="0507c-232">Eine Loopback Sitzung ist eine **PSSession** , die auf demselben computerbasiert und endet.</span><span class="sxs-lookup"><span data-stu-id="0507c-232">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="0507c-233">Um eine Loopback Sitzung zu erstellen, lassen Sie den **Computername** -Parameter aus, oder legen Sie seinen Wert auf fest.</span><span class="sxs-lookup"><span data-stu-id="0507c-233">To create a loopback session, omit the **ComputerName** parameter or set its value to .</span></span> <span data-ttu-id="0507c-234">(Punkt), localhost oder der Name des lokalen Computers.</span><span class="sxs-lookup"><span data-stu-id="0507c-234">(dot), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="0507c-235">Standardmäßig werden Loopback Sitzungen mit einem Netzwerk Token erstellt, das möglicherweise nicht über ausreichende Berechtigungen zum Authentifizieren bei Remote Computern verfügt.</span><span class="sxs-lookup"><span data-stu-id="0507c-235">By default, loopback sessions are created by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="0507c-236">Der **EnableNetworkAccess** -Parameter ist nur bei Loopbacksitzungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="0507c-236">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="0507c-237">Wenn Sie **enablenetworkaccess** verwenden, wenn Sie eine Sitzung auf einem Remote Computer erstellen, ist der Befehl erfolgreich, aber der-Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0507c-237">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="0507c-238">Sie können auch Remotezugriff in einer Loopbacksitzung erlauben, indem Sie den **CredSSP** -Wert des **Authentication** -Parameters verwenden, der die Anmeldeinformationen für die Sitzung an andere Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="0507c-238">You can also allow remote access in a loopback session by using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="0507c-239">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="0507c-239">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0507c-240">-Id</span><span class="sxs-lookup"><span data-stu-id="0507c-240">-Id</span></span>

<span data-ttu-id="0507c-241">Gibt die ID einer vorhandenen Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="0507c-241">Specifies the ID of an existing session.</span></span> <span data-ttu-id="0507c-242">`Enter-PSSession` verwendet die angegebene Sitzung für die interaktive Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0507c-242">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="0507c-243">Verwenden Sie das-Cmdlet, um die ID einer Sitzung zu ermitteln `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="0507c-243">To find the ID of a session, use the `Get-PSSession` cmdlet.</span></span>

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

### <span data-ttu-id="0507c-244">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="0507c-244">-InstanceId</span></span>

<span data-ttu-id="0507c-245">Gibt die Instanz-ID einer vorhandenen Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="0507c-245">Specifies the instance ID of an existing session.</span></span> <span data-ttu-id="0507c-246">`Enter-PSSession` verwendet die angegebene Sitzung für die interaktive Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0507c-246">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="0507c-247">Die Instanz-ID ist eine GUID.</span><span class="sxs-lookup"><span data-stu-id="0507c-247">The instance ID is a GUID.</span></span> <span data-ttu-id="0507c-248">Verwenden Sie das-Cmdlet, um die Instanz-ID einer Sitzung zu ermitteln `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="0507c-248">To find the instance ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="0507c-249">Sie können auch die Parameter " **Session** ", " **Name** " oder " **ID** " verwenden, um eine vorhandene Sitzung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0507c-249">You can also use the **Session** , **Name** , or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="0507c-250">Oder Sie können den **Computername** -Parameter verwenden, um eine temporäre Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="0507c-250">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

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

### <span data-ttu-id="0507c-251">-Name</span><span class="sxs-lookup"><span data-stu-id="0507c-251">-Name</span></span>

<span data-ttu-id="0507c-252">Gibt den Anzeigenamen einer vorhandenen Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="0507c-252">Specifies the friendly name of an existing session.</span></span> <span data-ttu-id="0507c-253">`Enter-PSSession` verwendet die angegebene Sitzung für die interaktive Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0507c-253">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="0507c-254">Wenn der angegebene Name mit mehr als einer Sitzung übereinstimmt, führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="0507c-254">If the name that you specify matches more than one session, the command fails.</span></span> <span data-ttu-id="0507c-255">Sie können auch die Parameter " **Session** ", " **InstanceId** " oder " **ID** " verwenden, um eine vorhandene Sitzung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0507c-255">You can also use the **Session** , **InstanceID** , or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="0507c-256">Oder Sie können den **Computername** -Parameter verwenden, um eine temporäre Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="0507c-256">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

<span data-ttu-id="0507c-257">Um einen anzeigen Amen für eine Sitzung zu erstellen, verwenden Sie den **Name** -Parameter des `New-PSSession` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0507c-257">To establish a friendly name for a session, use the **Name** parameter of the `New-PSSession` cmdlet.</span></span>

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

### <span data-ttu-id="0507c-258">-Port</span><span class="sxs-lookup"><span data-stu-id="0507c-258">-Port</span></span>

<span data-ttu-id="0507c-259">Gibt den Netzwerkport auf dem Remote Computer an, der für diesen Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0507c-259">Specifies the network port on the remote computer that is used for this command.</span></span> <span data-ttu-id="0507c-260">Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören.</span><span class="sxs-lookup"><span data-stu-id="0507c-260">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="0507c-261">Die Standardports sind 5985. Dies ist der WinRM-Port für http und 5986 (der WinRM-Port für HTTPS).</span><span class="sxs-lookup"><span data-stu-id="0507c-261">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="0507c-262">Bevor ein alternativer Port verwendet werden kann, müssen Sie den WinRM-Listener auf dem Remotecomputer für das Abhören an diesen Port konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0507c-262">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="0507c-263">Verwenden Sie die folgenden Befehle, um den Listener zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="0507c-263">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="0507c-264">Verwenden Sie den **Port** -Parameter nur, wenn es unbedingt notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="0507c-264">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="0507c-265">Die Porteinstellung im Befehl gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0507c-265">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="0507c-266">Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0507c-266">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0507c-267">-Runasadministrator</span><span class="sxs-lookup"><span data-stu-id="0507c-267">-RunAsAdministrator</span></span>

<span data-ttu-id="0507c-268">Gibt an, dass die **PSSession** als Administrator ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0507c-268">Indicates that the **PSSession** runs as administrator.</span></span>

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

### <span data-ttu-id="0507c-269">-Sitzung</span><span class="sxs-lookup"><span data-stu-id="0507c-269">-Session</span></span>

<span data-ttu-id="0507c-270">Gibt eine Windows PowerShell-Sitzung ( **PSSession** ) an, die für die interaktive Sitzung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0507c-270">Specifies a Windows PowerShell session ( **PSSession** ) to use for the interactive session.</span></span> <span data-ttu-id="0507c-271">Dieser Parameter akzeptiert ein Sitzungsobjekt.</span><span class="sxs-lookup"><span data-stu-id="0507c-271">This parameter takes a session object.</span></span> <span data-ttu-id="0507c-272">Sie können auch den **Namen** , die **InstanceId** oder die **ID** -Parameter verwenden, um eine **PSSession** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0507c-272">You can also use the **Name** , **InstanceID** , or **ID** parameters to specify a **PSSession**.</span></span>

<span data-ttu-id="0507c-273">Geben Sie eine Variable ein, die ein Sitzungs Objekt oder einen Befehl enthält, mit dem ein Sitzungs Objekt erstellt oder abgerufen wird, z. b. ein- `New-PSSession` oder- `Get-PSSession` Befehl</span><span class="sxs-lookup"><span data-stu-id="0507c-273">Enter a variable that contains a session object or a command that creates or gets a session object, such as a `New-PSSession` or `Get-PSSession` command.</span></span> <span data-ttu-id="0507c-274">Sie können ein Sitzungs Objekt auch über die Pipeline an senden `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="0507c-274">You can also pipe a session object to `Enter-PSSession`.</span></span> <span data-ttu-id="0507c-275">Mithilfe dieses Parameters können Sie nur eine **PSSession** senden.</span><span class="sxs-lookup"><span data-stu-id="0507c-275">You can submit only one **PSSession** by using this parameter.</span></span> <span data-ttu-id="0507c-276">Wenn Sie eine Variable eingeben, die mehr als eine **PSSession** enthält, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="0507c-276">If you enter a variable that contains more than one **PSSession** , the command fails.</span></span>

<span data-ttu-id="0507c-277">Wenn Sie `Exit-PSSession` oder das **Exit** -Schlüsselwort verwenden, wird die interaktive Sitzung beendet, die erstellte **PSSession** bleibt jedoch geöffnet und kann verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0507c-277">When you use `Exit-PSSession` or the **EXIT** keyword, the interactive session ends, but the **PSSession** that you created remains open and available for use.</span></span>

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

### <span data-ttu-id="0507c-278">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="0507c-278">-SessionOption</span></span>

<span data-ttu-id="0507c-279">Legt erweiterte Optionen für die Sitzung fest.</span><span class="sxs-lookup"><span data-stu-id="0507c-279">Sets advanced options for the session.</span></span> <span data-ttu-id="0507c-280">Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem `New-PSSessionOption` Cmdlet erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.</span><span class="sxs-lookup"><span data-stu-id="0507c-280">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="0507c-281">Die Standardwerte für die Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0507c-281">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="0507c-282">Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="0507c-282">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="0507c-283">Die Sitzungs Optionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der `$PSSessionOption` Preference-Variablen und in der Sitzungs Konfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="0507c-283">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="0507c-284">Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="0507c-284">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="0507c-285">Eine Beschreibung der Sitzungs Optionen, einschließlich der Standardwerte, finden Sie unter `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="0507c-285">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="0507c-286">Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="0507c-286">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="0507c-287">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="0507c-287">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

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

### <span data-ttu-id="0507c-288">-US-</span><span class="sxs-lookup"><span data-stu-id="0507c-288">-UseSSL</span></span>

<span data-ttu-id="0507c-289">Gibt an, dass dieses Cmdlet das Secure Sockets Layer (SSL)-Protokoll verwendet, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0507c-289">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="0507c-290">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="0507c-290">By default, SSL is not used.</span></span>

<span data-ttu-id="0507c-291">WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="0507c-291">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="0507c-292">Der Parameter " **eessl** " ist ein zusätzlicher Schutz, der die Daten über eine HTTPS-Verbindung anstelle einer HTTP-Verbindung sendet.</span><span class="sxs-lookup"><span data-stu-id="0507c-292">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="0507c-293">Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port, der für den Befehl verwendet wird, nicht verfügbar ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="0507c-293">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

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

### <span data-ttu-id="0507c-294">-VMID</span><span class="sxs-lookup"><span data-stu-id="0507c-294">-VMId</span></span>

<span data-ttu-id="0507c-295">Gibt die ID einer virtuellen Maschine an.</span><span class="sxs-lookup"><span data-stu-id="0507c-295">Specifies the ID of a virtual machine.</span></span>

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

### <span data-ttu-id="0507c-296">-VMName</span><span class="sxs-lookup"><span data-stu-id="0507c-296">-VMName</span></span>

<span data-ttu-id="0507c-297">Gibt den Namen eines virtuellen Computers an.</span><span class="sxs-lookup"><span data-stu-id="0507c-297">Specifies the name of a virtual machine.</span></span>

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

### <span data-ttu-id="0507c-298">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0507c-298">CommonParameters</span></span>

<span data-ttu-id="0507c-299">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0507c-299">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0507c-300">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0507c-300">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0507c-301">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0507c-301">INPUTS</span></span>

### <span data-ttu-id="0507c-302">System. String, System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="0507c-302">System.String, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="0507c-303">Sie können einen Computernamen, eine Zeichenfolge oder ein Sitzungs Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="0507c-303">You can pipe a computer name, as a string, or a session object to this cmdlet.</span></span>

## <span data-ttu-id="0507c-304">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0507c-304">OUTPUTS</span></span>

### <span data-ttu-id="0507c-305">Keine</span><span class="sxs-lookup"><span data-stu-id="0507c-305">None</span></span>

<span data-ttu-id="0507c-306">Das Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="0507c-306">The cmdlet does not return any output.</span></span>

## <span data-ttu-id="0507c-307">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0507c-307">NOTES</span></span>

<span data-ttu-id="0507c-308">Um eine Verbindung zu einem Remotecomputer herzustellen, müssen Sie Mitglied der Gruppe „Administratoren“ auf dem Remotecomputer sein.</span><span class="sxs-lookup"><span data-stu-id="0507c-308">To connect to a remote computer, you must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="0507c-309">Um eine interaktive Sitzung auf dem lokalen Computer zu starten, müssen Sie PowerShell mit der Option **als Administrator ausführen** starten.</span><span class="sxs-lookup"><span data-stu-id="0507c-309">To start an interactive session on the local computer, you must start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="0507c-310">Wenn Sie verwenden `Enter-PSSession` , wird Ihr Benutzerprofil auf dem Remote Computer für die interaktive Sitzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0507c-310">When you use `Enter-PSSession`, your user profile on the remote computer is used for the interactive session.</span></span> <span data-ttu-id="0507c-311">Die Befehle im Remote Benutzerprofil, einschließlich der Befehle zum Hinzufügen von PowerShell-Modulen und zum Ändern der Eingabeaufforderung, werden ausgeführt, bevor die Remote Eingabeaufforderung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0507c-311">The commands in the remote user profile, including commands to add PowerShell modules and to change the command prompt, run before the remote prompt is displayed.</span></span>

<span data-ttu-id="0507c-312">`Enter-PSSession` verwendet die Benutzeroberflächen Kultur-Einstellung auf dem lokalen Computer für die interaktive Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0507c-312">`Enter-PSSession` uses the UI culture setting on the local computer for the interactive session.</span></span> <span data-ttu-id="0507c-313">Um die lokale Benutzeroberflächen Kultur zu ermitteln, verwenden Sie die `$UICulture` Automatische Variable.</span><span class="sxs-lookup"><span data-stu-id="0507c-313">To find the local UI culture, use the `$UICulture` automatic variable.</span></span>

<span data-ttu-id="0507c-314">`Enter-PSSession` erfordert die `Get-Command` `Out-Default` `Exit-PSSession` Cmdlets, und.</span><span class="sxs-lookup"><span data-stu-id="0507c-314">`Enter-PSSession` requires the `Get-Command`, `Out-Default`, and `Exit-PSSession` cmdlets.</span></span> <span data-ttu-id="0507c-315">Wenn diese Cmdlets in der Sitzungs Konfiguration auf dem Remote Computer nicht enthalten sind, können die Befehle nicht ausgeführt werden `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="0507c-315">If these cmdlets are not included in the session configuration on the remote computer, the `Enter-PSSession` commands fails.</span></span>

<span data-ttu-id="0507c-316">Im Gegensatz zu `Invoke-Command` , das die Befehle vor dem Senden an den Remote Computer analysiert und interpretiert, `Enter-PSSession` sendet die Befehle ohne Interpretation direkt an den Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="0507c-316">Unlike `Invoke-Command`, which parses and interprets the commands before it sends them to the remote computer, `Enter-PSSession` sends the commands directly to the remote computer without interpretation.</span></span>

<span data-ttu-id="0507c-317">Wenn die Sitzung, die Sie eingeben möchten, mit der Verarbeitung eines Befehls ausgelastet ist, kann es zu einer Verzögerung kommen, bevor PowerShell auf den `Enter-PSSession` Befehl antwortet.</span><span class="sxs-lookup"><span data-stu-id="0507c-317">If the session you want to enter is busy processing a command, there might be a delay before PowerShell responds to the `Enter-PSSession` command.</span></span> <span data-ttu-id="0507c-318">Sie sind verbunden, sobald die Sitzung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0507c-318">You are connected as soon as the session is available.</span></span> <span data-ttu-id="0507c-319">Um den Befehl abzubrechen `Enter-PSSession` , drücken Sie <kbd>STRG</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="0507c-319">To cancel the `Enter-PSSession` command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

## <span data-ttu-id="0507c-320">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0507c-320">RELATED LINKS</span></span>

[<span data-ttu-id="0507c-321">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="0507c-321">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="0507c-322">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="0507c-322">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="0507c-323">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="0507c-323">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="0507c-324">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="0507c-324">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="0507c-325">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="0507c-325">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="0507c-326">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="0507c-326">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="0507c-327">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="0507c-327">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="0507c-328">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="0507c-328">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="0507c-329">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="0507c-329">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="0507c-330">about_Remote</span><span class="sxs-lookup"><span data-stu-id="0507c-330">about_Remote</span></span>](About/about_Remote.md)
