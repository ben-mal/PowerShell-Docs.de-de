---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/connect-wsman?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-WSMan
ms.openlocfilehash: d06ede0e27713b1a309aa2ed265f02881d34124e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217087"
---
# <span data-ttu-id="d21bd-103">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="d21bd-103">Connect-WSMan</span></span>

## <span data-ttu-id="d21bd-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d21bd-104">SYNOPSIS</span></span>
<span data-ttu-id="d21bd-105">Stellt eine Verbindung mit dem WinRM-Dienst auf einem Remotecomputer her.</span><span class="sxs-lookup"><span data-stu-id="d21bd-105">Connects to the WinRM service on a remote computer.</span></span>

## <span data-ttu-id="d21bd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d21bd-106">SYNTAX</span></span>

### <span data-ttu-id="d21bd-107">Computername (Standard)</span><span class="sxs-lookup"><span data-stu-id="d21bd-107">ComputerName (Default)</span></span>

```
Connect-WSMan [-ApplicationName <String>] [[-ComputerName] <String>] [-OptionSet <Hashtable>] [-Port <Int32>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="d21bd-108">URI</span><span class="sxs-lookup"><span data-stu-id="d21bd-108">URI</span></span>

```
Connect-WSMan [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-Port <Int32>] [-SessionOption <SessionOption>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="d21bd-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d21bd-109">DESCRIPTION</span></span>
<span data-ttu-id="d21bd-110">Das **Connect-WSMAN-** Cmdlet stellt eine Verbindung mit dem WinRM-Dienst auf einem Remote Computer her und stellt eine permanente Verbindung mit dem Remote Computer her.</span><span class="sxs-lookup"><span data-stu-id="d21bd-110">The **Connect-WSMan** cmdlet connects to the WinRM service on a remote computer, and it establishes a persistent connection to the remote computer.</span></span>
<span data-ttu-id="d21bd-111">Sie können dieses Cmdlet im Kontext des WSMAN-Anbieters verwenden, um eine Verbindung mit dem WinRM-Dienst auf einem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d21bd-111">You can use this cmdlet in the context of the WSMan provider to connect to the WinRM service on a remote computer.</span></span>
<span data-ttu-id="d21bd-112">Sie können dieses Cmdlet jedoch auch verwenden, um eine Verbindung mit dem WinRM-Dienst auf einem Remotecomputer herzustellen, bevor Sie zum WSMan-Anbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="d21bd-112">However, you can also use this cmdlet to connect to the WinRM service on a remote computer before you change to the WSMan provider.</span></span>
<span data-ttu-id="d21bd-113">Der Remote Computer wird im Stammverzeichnis des WSMAN-Anbieters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d21bd-113">The remote computer appears in the root directory of the WSMan provider.</span></span>

<span data-ttu-id="d21bd-114">Wenn die Client- und Servercomputer in verschiedenen Domänen oder Arbeitsgruppen enthalten sind, sind explizite Anmeldeinformationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d21bd-114">Explicit credentials are required when the client and server computers are in different domains or workgroups.</span></span>

<span data-ttu-id="d21bd-115">Informationen zum Trennen der Verbindung mit dem WinRM-Dienst auf einem Remote Computer finden Sie im Disconnect-WSMan Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d21bd-115">For information about how to disconnect from the WinRM service on a remote computer, see the Disconnect-WSMan cmdlet.</span></span>

## <span data-ttu-id="d21bd-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d21bd-116">EXAMPLES</span></span>

### <span data-ttu-id="d21bd-117">Beispiel 1: Herstellen einer Verbindung mit einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="d21bd-117">Example 1: Connect to a remote computer</span></span>

```
PS C:\> Connect-WSMan -ComputerName "server01"
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="d21bd-118">Dieser Befehl erstellt eine Verbindung mit dem Remotecomputer server01.</span><span class="sxs-lookup"><span data-stu-id="d21bd-118">This command creates a connection to the remote server01 computer.</span></span>

<span data-ttu-id="d21bd-119">Das **Connect-WSMAN-** Cmdlet wird in der Regel im Kontext des WSMAN-Anbieters verwendet, um eine Verbindung mit einem Remote Computer herzustellen, in diesem Fall dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="d21bd-119">The **Connect-WSMan** cmdlet is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="d21bd-120">Sie können das Cmdlet jedoch verwenden, um Verbindungen mit Remotecomputern herzustellen, bevor Sie zum WSMan-Anbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="d21bd-120">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="d21bd-121">Diese Verbindungen werden in der **Computername** -Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d21bd-121">Those connections appear in the **ComputerName** list.</span></span>

### <span data-ttu-id="d21bd-122">Beispiel 2: Herstellen einer Verbindung mit einem Remote Computer mithilfe von Administrator Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="d21bd-122">Example 2: Connect to a remote computer by using Administrator credentials</span></span>

```
PS C:\> $cred = Get-Credential Administrator
PS C:\> Connect-WSMan -ComputerName "server01" -Credential $cred
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="d21bd-123">Dieser Befehl erstellt eine Verbindung mit dem Remotesystem server01 unter Verwendung der Anmeldeinformationen für das Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="d21bd-123">This command creates a connection to the remote system server01 using the Administrator account credentials.</span></span>

<span data-ttu-id="d21bd-124">Der erste Befehl verwendet das Get-Credential-Cmdlet zum Abrufen der Administratoranmeldeinformationen und speichert sie dann in der $cred-Variablen.</span><span class="sxs-lookup"><span data-stu-id="d21bd-124">The first command uses the Get-Credential cmdlet to get the Administrator credentials and then stores them in the $cred variable.</span></span>
<span data-ttu-id="d21bd-125">Mit " **Get-Credential** " werden Sie abhängig von den Einstellungen der Systemregistrierung aufgefordert, ein Kennwort für Benutzername und Kennwort über ein Dialogfeld oder in der Befehlszeile anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d21bd-125">**Get-Credential** prompts you for a password of username and password through a dialog box or at the command line, depending on system registry settings.</span></span>

<span data-ttu-id="d21bd-126">Der zweite Befehl verwendet den *Credential* -Parameter, um die in $cred gespeicherten Anmelde Informationen an **Connect-WSMAN** zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="d21bd-126">The second command uses the *Credential* parameter to pass the credentials stored in $cred to **Connect-WSMan**.</span></span>
<span data-ttu-id="d21bd-127">**Connect-WSMAN** stellt dann unter Verwendung der Administrator Anmelde Informationen eine Verbindung mit dem Remote System Server01 her.</span><span class="sxs-lookup"><span data-stu-id="d21bd-127">**Connect-WSMan** then connects to the remote system server01 by using the Administrator credentials.</span></span>

### <span data-ttu-id="d21bd-128">Beispiel 3: Herstellen einer Verbindung mit einem Remote Computer über einen angegebenen Port</span><span class="sxs-lookup"><span data-stu-id="d21bd-128">Example 3: Connect to a remote computer over a specified port</span></span>

```
PS C:\> Connect-WSMan -ComputerName "server01" -Port 80
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="d21bd-129">Dieser Befehl stellt über Port 80 eine Verbindung mit dem Remotecomputer server01 her.</span><span class="sxs-lookup"><span data-stu-id="d21bd-129">This command creates a connection to the remote server01 computer over port 80.</span></span>

### <span data-ttu-id="d21bd-130">Beispiel 4: Herstellen einer Verbindung mit einem Remote Computer mithilfe von Verbindungsoptionen</span><span class="sxs-lookup"><span data-stu-id="d21bd-130">Example 4: Connect to a remote computer by using connection options</span></span>

```
PS C:\> $a = New-WSManSessionOption -OperationTimeout 30000
PS C:\> Connect-WSMan -ComputerName "server01" -SessionOption $a
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="d21bd-131">In diesem Beispiel wird eine Verbindung mit dem Remote Computer Server01 erstellt, indem die Verbindungsoptionen verwendet werden, die im Befehl **New-wsmansessionoption** definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d21bd-131">This example creates a connection to the remote server01 computer by using the connection options that are defined in the **New-WSManSessionOption** command.</span></span>

<span data-ttu-id="d21bd-132">Der erste Befehl verwendet " **New-wsmansessionoption** ", um einen Satz von Optionen für Verbindungseinstellungen in der $a Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d21bd-132">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="d21bd-133">In diesem Fall wird durch die Sitzungsoptionen ein Verbindungstimeout von 30 Sekunden (30.000 Millisekunden) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d21bd-133">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="d21bd-134">Der zweite Befehl verwendet den *sessionoption* -Parameter, um die Anmelde Informationen, die in der $a Variablen gespeichert sind, an **Connect-WSMAN** zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="d21bd-134">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan**.</span></span>
<span data-ttu-id="d21bd-135">Anschließend stellt **Connect-WSMAN** mithilfe der angegebenen Sitzungs Optionen eine Verbindung mit dem Remote Computer Server01 her.</span><span class="sxs-lookup"><span data-stu-id="d21bd-135">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

## <span data-ttu-id="d21bd-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d21bd-136">PARAMETERS</span></span>

### <span data-ttu-id="d21bd-137">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="d21bd-137">-ApplicationName</span></span>
<span data-ttu-id="d21bd-138">Gibt den Anwendungsnamen in der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="d21bd-138">Specifies the application name in the connection.</span></span>
<span data-ttu-id="d21bd-139">Der Standardwert des *ApplicationName* -Parameters lautet "wsman".</span><span class="sxs-lookup"><span data-stu-id="d21bd-139">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="d21bd-140">Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="d21bd-140">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="d21bd-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="d21bd-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="d21bd-142">Beispiel: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="d21bd-142">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="d21bd-143">Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="d21bd-143">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="d21bd-144">Diese Standardeinstellung von WSMAN eignet sich für die meisten Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="d21bd-144">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="d21bd-145">Dieser Parameter ist für die Verwendung bestimmt, wenn viele Computer Remote Verbindungen mit einem Computer herstellen, auf dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d21bd-145">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="d21bd-146">In diesem Fall wird Web Services for Management (WS-Management) aus Gründen der Effizienz von IIS gehostet.</span><span class="sxs-lookup"><span data-stu-id="d21bd-146">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d21bd-147">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d21bd-147">-Authentication</span></span>
<span data-ttu-id="d21bd-148">Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d21bd-148">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="d21bd-149">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="d21bd-149">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d21bd-150">Standard.</span><span class="sxs-lookup"><span data-stu-id="d21bd-150">Basic.</span></span>
<span data-ttu-id="d21bd-151">„Basic“ ist ein Schema, bei dem der Benutzername und das Kennwort im Klartext an den Server oder Proxy gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d21bd-151">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="d21bd-152">Standard.</span><span class="sxs-lookup"><span data-stu-id="d21bd-152">Default.</span></span>
<span data-ttu-id="d21bd-153">Verwendet die vom WS-Verwaltungsprotokoll implementierte Authentifizierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="d21bd-153">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="d21bd-154">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="d21bd-154">This is the default.</span></span>
- <span data-ttu-id="d21bd-155">Digest.</span><span class="sxs-lookup"><span data-stu-id="d21bd-155">Digest.</span></span>
<span data-ttu-id="d21bd-156">„Digest“ ist ein Abfrage/Rückmeldung-Schema, bei dem eine vom Server angegebene Datenzeichenfolge für die Abfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d21bd-156">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="d21bd-157">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="d21bd-157">Kerberos.</span></span>
<span data-ttu-id="d21bd-158">Der Clientcomputer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="d21bd-158">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="d21bd-159">Negotiate</span><span class="sxs-lookup"><span data-stu-id="d21bd-159">Negotiate.</span></span>
<span data-ttu-id="d21bd-160">„Negotiate“ ist ein Abfrage/Rückmeldung-Schema, bei dem das für die Authentifizierung zu verwendende Schema mit dem Server oder Proxy ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="d21bd-160">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="d21bd-161">Dieser Parameterwert ermöglicht beispielsweise die Aushandlung, um zu bestimmen, ob das Kerberos-Protokoll oder NTLM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d21bd-161">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="d21bd-162">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="d21bd-162">CredSSP.</span></span>
<span data-ttu-id="d21bd-163">Verwenden Sie die Authentifizierung der Credential Security Support Provider (kredssp), mit der der Benutzer Anmelde Informationen delegieren kann.</span><span class="sxs-lookup"><span data-stu-id="d21bd-163">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="d21bd-164">Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.</span><span class="sxs-lookup"><span data-stu-id="d21bd-164">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="d21bd-165">Vorsicht: die Anmelde Informationen des Benutzers werden vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="d21bd-165">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="d21bd-166">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="d21bd-166">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="d21bd-167">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d21bd-167">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am
Accepted values: None, Default, Digest, Negotiate, Basic, Kerberos, ClientCertificate, Credssp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d21bd-168">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="d21bd-168">-CertificateThumbprint</span></span>
<span data-ttu-id="d21bd-169">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="d21bd-169">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="d21bd-170">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="d21bd-170">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="d21bd-171">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d21bd-171">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="d21bd-172">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="d21bd-172">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="d21bd-173">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den Befehl Get-Item oder Get-ChildItem im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="d21bd-173">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d21bd-174">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d21bd-174">-ComputerName</span></span>
<span data-ttu-id="d21bd-175">Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d21bd-175">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="d21bd-176">Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="d21bd-176">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="d21bd-177">Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d21bd-177">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="d21bd-178">Der lokale Computer ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="d21bd-178">The local computer is the default.</span></span>
<span data-ttu-id="d21bd-179">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d21bd-179">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="d21bd-180">Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="d21bd-180">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d21bd-181">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="d21bd-181">-ConnectionURI</span></span>
<span data-ttu-id="d21bd-182">Gibt den Verbindungsendpunkt an.</span><span class="sxs-lookup"><span data-stu-id="d21bd-182">Specifies the connection endpoint.</span></span>
<span data-ttu-id="d21bd-183">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d21bd-183">The format of this string is as follows:</span></span>

<span data-ttu-id="d21bd-184">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="d21bd-184">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="d21bd-185">Die folgende Zeichenfolge ist ein ordnungsgemäß formatierter Wert für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="d21bd-185">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="d21bd-186">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="d21bd-186">The URI must be fully qualified.</span></span>

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d21bd-187">-Credential</span><span class="sxs-lookup"><span data-stu-id="d21bd-187">-Credential</span></span>
<span data-ttu-id="d21bd-188">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="d21bd-188">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="d21bd-189">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d21bd-189">The default is the current user.</span></span>
<span data-ttu-id="d21bd-190">Geben Sie einen Benutzernamen ein, z. b. USER01, Domain01\User01 oder User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="d21bd-190">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="d21bd-191">Oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom Get-Credential-Cmdlet zurück gegebenes Objekt.</span><span class="sxs-lookup"><span data-stu-id="d21bd-191">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="d21bd-192">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d21bd-192">When you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: cred, c

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d21bd-193">-OptionSET</span><span class="sxs-lookup"><span data-stu-id="d21bd-193">-OptionSet</span></span>
<span data-ttu-id="d21bd-194">Gibt eine Reihe von Schaltern für einen Dienst an, um die Art der Anforderung zu ändern oder zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="d21bd-194">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="d21bd-195">Diese ähneln Switches, die in Befehlszeilenshells verwendet werden, da Sie Dienst spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="d21bd-195">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="d21bd-196">Es können beliebig viele Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d21bd-196">Any number of options can be specified.</span></span>

<span data-ttu-id="d21bd-197">Das folgende Beispiel veranschaulicht die Syntax, durch die die Werte 1, 2 und 3 für die Parameter „a“, „b“ und „c“ übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="d21bd-197">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d21bd-198">-Port</span><span class="sxs-lookup"><span data-stu-id="d21bd-198">-Port</span></span>
<span data-ttu-id="d21bd-199">Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="d21bd-199">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="d21bd-200">Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80.</span><span class="sxs-lookup"><span data-stu-id="d21bd-200">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="d21bd-201">Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.</span><span class="sxs-lookup"><span data-stu-id="d21bd-201">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="d21bd-202">Wenn Sie HTTPS als Transport verwenden, muss der Wert des *Computername* -Parameters mit dem allgemeinen Namen des Serverzertifikats (CN) identisch sein.</span><span class="sxs-lookup"><span data-stu-id="d21bd-202">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="d21bd-203">Wenn der *skipcncheck* -Parameter jedoch als Teil des *sessionoption* -Parameters angegeben wird, muss der allgemeine Name des Zertifikats für den Server nicht mit dem Hostnamen des Servers identisch sein.</span><span class="sxs-lookup"><span data-stu-id="d21bd-203">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="d21bd-204">Der *skipcncheck* -Parameter sollte nur für vertrauenswürdige Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d21bd-204">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d21bd-205">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="d21bd-205">-SessionOption</span></span>
<span data-ttu-id="d21bd-206">Gibt erweiterte Optionen für die WS-Management Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="d21bd-206">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="d21bd-207">Geben Sie ein **sessionoption** -Objekt ein, das Sie mit dem New-WSManSessionOption-Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="d21bd-207">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="d21bd-208">Geben Sie ein, um weitere Informationen zu den verfügbaren Optionen zu erhalten `Get-Help New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="d21bd-208">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

```yaml
Type: Microsoft.WSMan.Management.SessionOption
Parameter Sets: (All)
Aliases: so

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d21bd-209">-US-</span><span class="sxs-lookup"><span data-stu-id="d21bd-209">-UseSSL</span></span>
<span data-ttu-id="d21bd-210">Gibt an, dass das Secure Sockets Layer (SSL)-Protokoll verwendet wird, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d21bd-210">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="d21bd-211">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d21bd-211">By default, SSL is not used.</span></span>

<span data-ttu-id="d21bd-212">WS-Management verschlüsselt alle PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="d21bd-212">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="d21bd-213">Mit *dem Parameter "* Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.</span><span class="sxs-lookup"><span data-stu-id="d21bd-213">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="d21bd-214">Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="d21bd-214">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="d21bd-215">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d21bd-215">CommonParameters</span></span>
<span data-ttu-id="d21bd-216">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d21bd-216">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d21bd-217">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d21bd-217">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d21bd-218">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d21bd-218">INPUTS</span></span>

### <span data-ttu-id="d21bd-219">Keine</span><span class="sxs-lookup"><span data-stu-id="d21bd-219">None</span></span>
<span data-ttu-id="d21bd-220">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="d21bd-220">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="d21bd-221">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d21bd-221">OUTPUTS</span></span>

### <span data-ttu-id="d21bd-222">Keine</span><span class="sxs-lookup"><span data-stu-id="d21bd-222">None</span></span>
<span data-ttu-id="d21bd-223">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d21bd-223">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d21bd-224">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d21bd-224">NOTES</span></span>

* <span data-ttu-id="d21bd-225">Sie können auf einem Remotecomputer Verwaltungsbefehle ausführen oder Verwaltungsdaten abfragen, ohne eine WS-Management-Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d21bd-225">You can run management commands or query management data on a remote computer without creating a WS-Management session.</span></span> <span data-ttu-id="d21bd-226">Verwenden Sie hierzu die *Computername* -Parameter von Invoke-WSManAction und Get-wsmaninstance.</span><span class="sxs-lookup"><span data-stu-id="d21bd-226">You can do this by using the *ComputerName* parameters of Invoke-WSManAction and Get-WSManInstance.</span></span> <span data-ttu-id="d21bd-227">Wenn Sie den *Computername* -Parameter verwenden, erstellt PowerShell eine temporäre Verbindung, die für den einzelnen Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d21bd-227">When you use the *ComputerName* parameter, PowerShell creates a temporary connection that is used for the single command.</span></span> <span data-ttu-id="d21bd-228">Nachdem der Befehl ausgeführt wurde, wird die Verbindung geschlossen.</span><span class="sxs-lookup"><span data-stu-id="d21bd-228">After the command runs, the connection is closed.</span></span>

*

## <span data-ttu-id="d21bd-229">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d21bd-229">RELATED LINKS</span></span>

[<span data-ttu-id="d21bd-230">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="d21bd-230">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="d21bd-231">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="d21bd-231">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="d21bd-232">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="d21bd-232">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="d21bd-233">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="d21bd-233">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="d21bd-234">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d21bd-234">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="d21bd-235">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="d21bd-235">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="d21bd-236">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d21bd-236">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="d21bd-237">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="d21bd-237">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="d21bd-238">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d21bd-238">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="d21bd-239">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d21bd-239">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="d21bd-240">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="d21bd-240">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="d21bd-241">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="d21bd-241">Test-WSMan</span></span>](Test-WSMan.md)
