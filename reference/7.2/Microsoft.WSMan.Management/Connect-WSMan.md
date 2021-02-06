---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/connect-wsman?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-WSMan
ms.openlocfilehash: 5dfd0b355a3589bf45ea92b92ae8778023132bcd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596560"
---
# <span data-ttu-id="7ce25-102">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="7ce25-102">Connect-WSMan</span></span>

## <span data-ttu-id="7ce25-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7ce25-103">SYNOPSIS</span></span>
<span data-ttu-id="7ce25-104">Stellt eine Verbindung mit dem WinRM-Dienst auf einem Remotecomputer her.</span><span class="sxs-lookup"><span data-stu-id="7ce25-104">Connects to the WinRM service on a remote computer.</span></span>

## <span data-ttu-id="7ce25-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7ce25-105">SYNTAX</span></span>

### <span data-ttu-id="7ce25-106">Computername (Standard)</span><span class="sxs-lookup"><span data-stu-id="7ce25-106">ComputerName (Default)</span></span>

```
Connect-WSMan [-ApplicationName <String>] [[-ComputerName] <String>] [-OptionSet <Hashtable>] [-Port <Int32>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="7ce25-107">URI</span><span class="sxs-lookup"><span data-stu-id="7ce25-107">URI</span></span>

```
Connect-WSMan [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-Port <Int32>] [-SessionOption <SessionOption>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="7ce25-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7ce25-108">DESCRIPTION</span></span>
<span data-ttu-id="7ce25-109">Das **Connect-WSMAN-** Cmdlet stellt eine Verbindung mit dem WinRM-Dienst auf einem Remote Computer her und stellt eine permanente Verbindung mit dem Remote Computer her.</span><span class="sxs-lookup"><span data-stu-id="7ce25-109">The **Connect-WSMan** cmdlet connects to the WinRM service on a remote computer, and it establishes a persistent connection to the remote computer.</span></span>
<span data-ttu-id="7ce25-110">Sie können dieses Cmdlet im Kontext des WSMAN-Anbieters verwenden, um eine Verbindung mit dem WinRM-Dienst auf einem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="7ce25-110">You can use this cmdlet in the context of the WSMan provider to connect to the WinRM service on a remote computer.</span></span>
<span data-ttu-id="7ce25-111">Sie können dieses Cmdlet jedoch auch verwenden, um eine Verbindung mit dem WinRM-Dienst auf einem Remotecomputer herzustellen, bevor Sie zum WSMan-Anbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="7ce25-111">However, you can also use this cmdlet to connect to the WinRM service on a remote computer before you change to the WSMan provider.</span></span>
<span data-ttu-id="7ce25-112">Der Remote Computer wird im Stammverzeichnis des WSMAN-Anbieters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ce25-112">The remote computer appears in the root directory of the WSMan provider.</span></span>

<span data-ttu-id="7ce25-113">Wenn die Client- und Servercomputer in verschiedenen Domänen oder Arbeitsgruppen enthalten sind, sind explizite Anmeldeinformationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7ce25-113">Explicit credentials are required when the client and server computers are in different domains or workgroups.</span></span>

<span data-ttu-id="7ce25-114">Informationen zum Trennen der Verbindung mit dem WinRM-Dienst auf einem Remote Computer finden Sie im Disconnect-WSMan Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7ce25-114">For information about how to disconnect from the WinRM service on a remote computer, see the Disconnect-WSMan cmdlet.</span></span>

## <span data-ttu-id="7ce25-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7ce25-115">EXAMPLES</span></span>

### <span data-ttu-id="7ce25-116">Beispiel 1: Herstellen einer Verbindung mit einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="7ce25-116">Example 1: Connect to a remote computer</span></span>

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

<span data-ttu-id="7ce25-117">Dieser Befehl erstellt eine Verbindung mit dem Remotecomputer server01.</span><span class="sxs-lookup"><span data-stu-id="7ce25-117">This command creates a connection to the remote server01 computer.</span></span>

<span data-ttu-id="7ce25-118">Das **Connect-WSMAN-** Cmdlet wird in der Regel im Kontext des WSMAN-Anbieters verwendet, um eine Verbindung mit einem Remote Computer herzustellen, in diesem Fall dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="7ce25-118">The **Connect-WSMan** cmdlet is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="7ce25-119">Sie können das Cmdlet jedoch verwenden, um Verbindungen mit Remotecomputern herzustellen, bevor Sie zum WSMan-Anbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="7ce25-119">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="7ce25-120">Diese Verbindungen werden in der **Computername** -Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ce25-120">Those connections appear in the **ComputerName** list.</span></span>

### <span data-ttu-id="7ce25-121">Beispiel 2: Herstellen einer Verbindung mit einem Remote Computer mithilfe von Administrator Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="7ce25-121">Example 2: Connect to a remote computer by using Administrator credentials</span></span>

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

<span data-ttu-id="7ce25-122">Dieser Befehl erstellt eine Verbindung mit dem Remotesystem server01 unter Verwendung der Anmeldeinformationen für das Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="7ce25-122">This command creates a connection to the remote system server01 using the Administrator account credentials.</span></span>

<span data-ttu-id="7ce25-123">Der erste Befehl verwendet das Get-Credential-Cmdlet zum Abrufen der Administratoranmeldeinformationen und speichert sie dann in der $cred-Variablen.</span><span class="sxs-lookup"><span data-stu-id="7ce25-123">The first command uses the Get-Credential cmdlet to get the Administrator credentials and then stores them in the $cred variable.</span></span>
<span data-ttu-id="7ce25-124">Mit " **Get-Credential** " werden Sie abhängig von den Einstellungen der Systemregistrierung aufgefordert, ein Kennwort für Benutzername und Kennwort über ein Dialogfeld oder in der Befehlszeile anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7ce25-124">**Get-Credential** prompts you for a password of username and password through a dialog box or at the command line, depending on system registry settings.</span></span>

<span data-ttu-id="7ce25-125">Der zweite Befehl verwendet den *Credential* -Parameter, um die in $cred gespeicherten Anmelde Informationen an **Connect-WSMAN** zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="7ce25-125">The second command uses the *Credential* parameter to pass the credentials stored in $cred to **Connect-WSMan**.</span></span>
<span data-ttu-id="7ce25-126">**Connect-WSMAN** stellt dann unter Verwendung der Administrator Anmelde Informationen eine Verbindung mit dem Remote System Server01 her.</span><span class="sxs-lookup"><span data-stu-id="7ce25-126">**Connect-WSMan** then connects to the remote system server01 by using the Administrator credentials.</span></span>

### <span data-ttu-id="7ce25-127">Beispiel 3: Herstellen einer Verbindung mit einem Remote Computer über einen angegebenen Port</span><span class="sxs-lookup"><span data-stu-id="7ce25-127">Example 3: Connect to a remote computer over a specified port</span></span>

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

<span data-ttu-id="7ce25-128">Dieser Befehl stellt über Port 80 eine Verbindung mit dem Remotecomputer server01 her.</span><span class="sxs-lookup"><span data-stu-id="7ce25-128">This command creates a connection to the remote server01 computer over port 80.</span></span>

### <span data-ttu-id="7ce25-129">Beispiel 4: Herstellen einer Verbindung mit einem Remote Computer mithilfe von Verbindungsoptionen</span><span class="sxs-lookup"><span data-stu-id="7ce25-129">Example 4: Connect to a remote computer by using connection options</span></span>

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

<span data-ttu-id="7ce25-130">In diesem Beispiel wird eine Verbindung mit dem Remote Computer Server01 erstellt, indem die Verbindungsoptionen verwendet werden, die im Befehl **New-wsmansessionoption** definiert sind.</span><span class="sxs-lookup"><span data-stu-id="7ce25-130">This example creates a connection to the remote server01 computer by using the connection options that are defined in the **New-WSManSessionOption** command.</span></span>

<span data-ttu-id="7ce25-131">Der erste Befehl verwendet " **New-wsmansessionoption** ", um einen Satz von Optionen für Verbindungseinstellungen in der $a Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7ce25-131">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="7ce25-132">In diesem Fall wird durch die Sitzungsoptionen ein Verbindungstimeout von 30 Sekunden (30.000 Millisekunden) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7ce25-132">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="7ce25-133">Der zweite Befehl verwendet den *sessionoption* -Parameter, um die Anmelde Informationen, die in der $a Variablen gespeichert sind, an **Connect-WSMAN** zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="7ce25-133">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan**.</span></span>
<span data-ttu-id="7ce25-134">Anschließend stellt **Connect-WSMAN** mithilfe der angegebenen Sitzungs Optionen eine Verbindung mit dem Remote Computer Server01 her.</span><span class="sxs-lookup"><span data-stu-id="7ce25-134">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

## <span data-ttu-id="7ce25-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7ce25-135">PARAMETERS</span></span>

### <span data-ttu-id="7ce25-136">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="7ce25-136">-ApplicationName</span></span>
<span data-ttu-id="7ce25-137">Gibt den Anwendungsnamen in der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="7ce25-137">Specifies the application name in the connection.</span></span>
<span data-ttu-id="7ce25-138">Der Standardwert des *ApplicationName* -Parameters lautet "wsman".</span><span class="sxs-lookup"><span data-stu-id="7ce25-138">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="7ce25-139">Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="7ce25-139">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="7ce25-140">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="7ce25-140">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="7ce25-141">Beispiel: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="7ce25-141">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="7ce25-142">Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="7ce25-142">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="7ce25-143">Diese Standardeinstellung von WSMAN eignet sich für die meisten Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="7ce25-143">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="7ce25-144">Dieser Parameter ist für die Verwendung bestimmt, wenn viele Computer Remote Verbindungen mit einem Computer herstellen, auf dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7ce25-144">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="7ce25-145">In diesem Fall wird Web Services for Management (WS-Management) aus Gründen der Effizienz von IIS gehostet.</span><span class="sxs-lookup"><span data-stu-id="7ce25-145">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="7ce25-146">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7ce25-146">-Authentication</span></span>
<span data-ttu-id="7ce25-147">Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ce25-147">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="7ce25-148">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="7ce25-148">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7ce25-149">Standard.</span><span class="sxs-lookup"><span data-stu-id="7ce25-149">Basic.</span></span>
<span data-ttu-id="7ce25-150">„Basic“ ist ein Schema, bei dem der Benutzername und das Kennwort im Klartext an den Server oder Proxy gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ce25-150">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="7ce25-151">Standard.</span><span class="sxs-lookup"><span data-stu-id="7ce25-151">Default.</span></span>
<span data-ttu-id="7ce25-152">Verwendet die vom WS-Verwaltungsprotokoll implementierte Authentifizierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="7ce25-152">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="7ce25-153">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="7ce25-153">This is the default.</span></span>
- <span data-ttu-id="7ce25-154">Digest.</span><span class="sxs-lookup"><span data-stu-id="7ce25-154">Digest.</span></span>
<span data-ttu-id="7ce25-155">„Digest“ ist ein Abfrage/Rückmeldung-Schema, bei dem eine vom Server angegebene Datenzeichenfolge für die Abfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ce25-155">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="7ce25-156">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7ce25-156">Kerberos.</span></span>
<span data-ttu-id="7ce25-157">Der Clientcomputer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="7ce25-157">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="7ce25-158">Negotiate</span><span class="sxs-lookup"><span data-stu-id="7ce25-158">Negotiate.</span></span>
<span data-ttu-id="7ce25-159">„Negotiate“ ist ein Abfrage/Rückmeldung-Schema, bei dem das für die Authentifizierung zu verwendende Schema mit dem Server oder Proxy ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="7ce25-159">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="7ce25-160">Dieser Parameterwert ermöglicht beispielsweise die Aushandlung, um zu bestimmen, ob das Kerberos-Protokoll oder NTLM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ce25-160">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="7ce25-161">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="7ce25-161">CredSSP.</span></span>
<span data-ttu-id="7ce25-162">Verwenden Sie die Authentifizierung der Credential Security Support Provider (kredssp), mit der der Benutzer Anmelde Informationen delegieren kann.</span><span class="sxs-lookup"><span data-stu-id="7ce25-162">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="7ce25-163">Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.</span><span class="sxs-lookup"><span data-stu-id="7ce25-163">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="7ce25-164">Vorsicht: die Anmelde Informationen des Benutzers werden vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="7ce25-164">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="7ce25-165">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="7ce25-165">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="7ce25-166">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ce25-166">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="7ce25-167">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="7ce25-167">-CertificateThumbprint</span></span>
<span data-ttu-id="7ce25-168">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="7ce25-168">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="7ce25-169">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="7ce25-169">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="7ce25-170">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ce25-170">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="7ce25-171">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="7ce25-171">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="7ce25-172">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den Befehl Get-Item oder Get-ChildItem im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="7ce25-172">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="7ce25-173">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="7ce25-173">-ComputerName</span></span>
<span data-ttu-id="7ce25-174">Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ce25-174">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="7ce25-175">Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="7ce25-175">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="7ce25-176">Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7ce25-176">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="7ce25-177">Der lokale Computer ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="7ce25-177">The local computer is the default.</span></span>
<span data-ttu-id="7ce25-178">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7ce25-178">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="7ce25-179">Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="7ce25-179">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="7ce25-180">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="7ce25-180">-ConnectionURI</span></span>
<span data-ttu-id="7ce25-181">Gibt den Verbindungsendpunkt an.</span><span class="sxs-lookup"><span data-stu-id="7ce25-181">Specifies the connection endpoint.</span></span>
<span data-ttu-id="7ce25-182">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7ce25-182">The format of this string is as follows:</span></span>

<span data-ttu-id="7ce25-183">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="7ce25-183">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="7ce25-184">Die folgende Zeichenfolge ist ein ordnungsgemäß formatierter Wert für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="7ce25-184">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="7ce25-185">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="7ce25-185">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="7ce25-186">-Credential</span><span class="sxs-lookup"><span data-stu-id="7ce25-186">-Credential</span></span>
<span data-ttu-id="7ce25-187">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="7ce25-187">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="7ce25-188">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7ce25-188">The default is the current user.</span></span>
<span data-ttu-id="7ce25-189">Geben Sie einen Benutzernamen ein, z. b. USER01, Domain01\User01 oder User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="7ce25-189">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="7ce25-190">Oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom Get-Credential-Cmdlet zurück gegebenes Objekt.</span><span class="sxs-lookup"><span data-stu-id="7ce25-190">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="7ce25-191">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7ce25-191">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="7ce25-192">-OptionSET</span><span class="sxs-lookup"><span data-stu-id="7ce25-192">-OptionSet</span></span>
<span data-ttu-id="7ce25-193">Gibt eine Reihe von Schaltern für einen Dienst an, um die Art der Anforderung zu ändern oder zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="7ce25-193">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="7ce25-194">Diese ähneln Switches, die in Befehlszeilenshells verwendet werden, da Sie Dienst spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="7ce25-194">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="7ce25-195">Es können beliebig viele Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7ce25-195">Any number of options can be specified.</span></span>

<span data-ttu-id="7ce25-196">Das folgende Beispiel veranschaulicht die Syntax, durch die die Werte 1, 2 und 3 für die Parameter „a“, „b“ und „c“ übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="7ce25-196">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="7ce25-197">-Port</span><span class="sxs-lookup"><span data-stu-id="7ce25-197">-Port</span></span>
<span data-ttu-id="7ce25-198">Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="7ce25-198">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="7ce25-199">Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80.</span><span class="sxs-lookup"><span data-stu-id="7ce25-199">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="7ce25-200">Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.</span><span class="sxs-lookup"><span data-stu-id="7ce25-200">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="7ce25-201">Wenn Sie HTTPS als Transport verwenden, muss der Wert des *Computername* -Parameters mit dem allgemeinen Namen des Serverzertifikats (CN) identisch sein.</span><span class="sxs-lookup"><span data-stu-id="7ce25-201">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="7ce25-202">Wenn der *skipcncheck* -Parameter jedoch als Teil des *sessionoption* -Parameters angegeben wird, muss der allgemeine Name des Zertifikats für den Server nicht mit dem Hostnamen des Servers identisch sein.</span><span class="sxs-lookup"><span data-stu-id="7ce25-202">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="7ce25-203">Der *skipcncheck* -Parameter sollte nur für vertrauenswürdige Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ce25-203">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="7ce25-204">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="7ce25-204">-SessionOption</span></span>
<span data-ttu-id="7ce25-205">Gibt erweiterte Optionen für die WS-Management Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="7ce25-205">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="7ce25-206">Geben Sie ein **sessionoption** -Objekt ein, das Sie mit dem New-WSManSessionOption-Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="7ce25-206">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="7ce25-207">Geben Sie ein, um weitere Informationen zu den verfügbaren Optionen zu erhalten `Get-Help New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="7ce25-207">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="7ce25-208">-US-</span><span class="sxs-lookup"><span data-stu-id="7ce25-208">-UseSSL</span></span>
<span data-ttu-id="7ce25-209">Gibt an, dass das Secure Sockets Layer (SSL)-Protokoll verwendet wird, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="7ce25-209">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="7ce25-210">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ce25-210">By default, SSL is not used.</span></span>

<span data-ttu-id="7ce25-211">WS-Management verschlüsselt alle PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="7ce25-211">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="7ce25-212">Mit *dem Parameter "* Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.</span><span class="sxs-lookup"><span data-stu-id="7ce25-212">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="7ce25-213">Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="7ce25-213">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="7ce25-214">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7ce25-214">CommonParameters</span></span>
<span data-ttu-id="7ce25-215">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7ce25-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7ce25-216">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7ce25-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7ce25-217">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7ce25-217">INPUTS</span></span>

### <span data-ttu-id="7ce25-218">Keine</span><span class="sxs-lookup"><span data-stu-id="7ce25-218">None</span></span>
<span data-ttu-id="7ce25-219">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="7ce25-219">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="7ce25-220">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7ce25-220">OUTPUTS</span></span>

### <span data-ttu-id="7ce25-221">Keine</span><span class="sxs-lookup"><span data-stu-id="7ce25-221">None</span></span>
<span data-ttu-id="7ce25-222">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7ce25-222">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7ce25-223">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7ce25-223">NOTES</span></span>

* <span data-ttu-id="7ce25-224">Sie können auf einem Remotecomputer Verwaltungsbefehle ausführen oder Verwaltungsdaten abfragen, ohne eine WS-Management-Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7ce25-224">You can run management commands or query management data on a remote computer without creating a WS-Management session.</span></span> <span data-ttu-id="7ce25-225">Verwenden Sie hierzu die *Computername* -Parameter von Invoke-WSManAction und Get-wsmaninstance.</span><span class="sxs-lookup"><span data-stu-id="7ce25-225">You can do this by using the *ComputerName* parameters of Invoke-WSManAction and Get-WSManInstance.</span></span> <span data-ttu-id="7ce25-226">Wenn Sie den *Computername* -Parameter verwenden, erstellt PowerShell eine temporäre Verbindung, die für den einzelnen Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ce25-226">When you use the *ComputerName* parameter, PowerShell creates a temporary connection that is used for the single command.</span></span> <span data-ttu-id="7ce25-227">Nachdem der Befehl ausgeführt wurde, wird die Verbindung geschlossen.</span><span class="sxs-lookup"><span data-stu-id="7ce25-227">After the command runs, the connection is closed.</span></span>

*

## <span data-ttu-id="7ce25-228">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7ce25-228">RELATED LINKS</span></span>

[<span data-ttu-id="7ce25-229">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="7ce25-229">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="7ce25-230">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="7ce25-230">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="7ce25-231">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="7ce25-231">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="7ce25-232">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="7ce25-232">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="7ce25-233">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="7ce25-233">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="7ce25-234">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="7ce25-234">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="7ce25-235">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="7ce25-235">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="7ce25-236">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="7ce25-236">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="7ce25-237">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="7ce25-237">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="7ce25-238">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="7ce25-238">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="7ce25-239">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="7ce25-239">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="7ce25-240">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="7ce25-240">Test-WSMan</span></span>](Test-WSMan.md)

