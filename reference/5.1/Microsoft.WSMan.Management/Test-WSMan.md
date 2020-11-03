---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/test-wsman?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-WSMan
ms.openlocfilehash: 3178c12dbc14b9d0841f1d924a695ae2f761f579
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224740"
---
# <span data-ttu-id="0b4b5-103">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="0b4b5-103">Test-WSMan</span></span>

## <span data-ttu-id="0b4b5-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0b4b5-104">SYNOPSIS</span></span>
<span data-ttu-id="0b4b5-105">Überprüft, ob der WinRM-Dienst auf einem lokalen oder Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-105">Tests whether the WinRM service is running on a local or remote computer.</span></span>

## <span data-ttu-id="0b4b5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0b4b5-106">SYNTAX</span></span>

```
Test-WSMan [[-ComputerName] <String>] [-Authentication <AuthenticationMechanism>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-Credential <PSCredential>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="0b4b5-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b4b5-107">DESCRIPTION</span></span>
<span data-ttu-id="0b4b5-108">Das **Test-WSMAN-** Cmdlet sendet eine Identifikations Anforderung, mit der bestimmt wird, ob der WinRM-Dienst auf einem lokalen Computer oder einem Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-108">The **Test-WSMan** cmdlet submits an identification request that determines whether the WinRM service is running on a local or remote computer.</span></span>
<span data-ttu-id="0b4b5-109">Wenn der Dienst auf dem überprüften Computer ausgeführt wird, zeigt das Cmdlet das WS-Management-Identitätsschema, die Protokollversion, den Produkthersteller und die Produktversion des überprüften Diensts an.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-109">If the tested computer is running the service, the cmdlet displays the WS-Management identity schema, the protocol version, the product vendor, and the product version of the tested service.</span></span>

## <span data-ttu-id="0b4b5-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0b4b5-110">EXAMPLES</span></span>

### <span data-ttu-id="0b4b5-111">Beispiel 1: Bestimmen des Status des WinRM-Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="0b4b5-111">Example 1: Determine the status of the WinRM service</span></span>

```
PS C:\> Test-WSMan
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 0.0.0 SP: 0.0 Stack: 2.0
```

<span data-ttu-id="0b4b5-112">Dieser Befehl ermittelt, ob der WinRM-Dienst auf einem lokalen oder Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-112">This command determines whether the WinRM service is running on the local computer or on a remote computer.</span></span>

### <span data-ttu-id="0b4b5-113">Beispiel 2: Bestimmen des Status des WinRM-Dienstanbieter auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="0b4b5-113">Example 2: Determine the status of the WinRM service on a remote computer</span></span>

```
PS C:\> Test-WSMan -ComputerName "server01"
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 0.0.0 SP: 0.0 Stack: 2.0
```

<span data-ttu-id="0b4b5-114">Mit diesem Befehl wird ermittelt, ob der WinRM-Dienst auf dem Server01-Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-114">This command determines whether the WinRM service is running on the server01 computer.</span></span>

### <span data-ttu-id="0b4b5-115">Beispiel 3: Bestimmen des Status des WinRM-Dienstanbieter und der Betriebssystemversion</span><span class="sxs-lookup"><span data-stu-id="0b4b5-115">Example 3: Determine the status of the WinRM service and the operating system version</span></span>

```
PS C:\> Test-WSMan -Authentication default
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 6.0.6001 SP: 1.0 Stack: 2.0
```

<span data-ttu-id="0b4b5-116">Mit diesem Befehl wird überprüft, ob der WS-Management (WinRM)-Dienst auf dem lokalen Computer ausgeführt wird, indem der Authentifizierungs Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-116">This command tests to see whether the WS-Management (WinRM) service is running on the local computer by using the authentication parameter.</span></span>

<span data-ttu-id="0b4b5-117">Mithilfe des Authentifizierungs Parameters kann **Test-WSMAN** die Betriebssystemversion zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-117">Using the authentication parameter enables **Test-WSMan** to return the operating system version.</span></span>

### <span data-ttu-id="0b4b5-118">Beispiel 4: Bestimmen des Status des WinRM-diensdienstanbieter und der Betriebssystemversion auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="0b4b5-118">Example 4: Determine the status of the WinRM service and the operating system version on a remote computer</span></span>

```
PS C:\> Test-WSMan -ComputerName "server01" -Authentication default
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 6.1.7021 SP: 0.0 Stack: 2.0
```

<span data-ttu-id="0b4b5-119">Mit diesem Befehl wird getestet, ob der WS-Management (WinRM)-Dienst auf dem Computer mit dem Namen Server01 unter Verwendung des Authentifizierungs Parameters ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-119">This command tests to see whether the WS-Management (WinRM) service is running on the computer named server01 using the authentication parameter.</span></span>

<span data-ttu-id="0b4b5-120">Mithilfe des Authentifizierungs Parameters kann **Test-WSMAN** die Betriebssystemversion zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-120">Using the authentication parameter enables **Test-WSMan** to return the operating system version.</span></span>

## <span data-ttu-id="0b4b5-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0b4b5-121">PARAMETERS</span></span>

### <span data-ttu-id="0b4b5-122">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="0b4b5-122">-ApplicationName</span></span>
<span data-ttu-id="0b4b5-123">Gibt den Anwendungsnamen in der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-123">Specifies the application name in the connection.</span></span>
<span data-ttu-id="0b4b5-124">Der Standardwert des *ApplicationName* -Parameters lautet "wsman".</span><span class="sxs-lookup"><span data-stu-id="0b4b5-124">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="0b4b5-125">Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="0b4b5-125">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="0b4b5-126">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="0b4b5-126">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="0b4b5-127">Beispiel: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="0b4b5-127">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="0b4b5-128">Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-128">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="0b4b5-129">Diese Standardeinstellung von WSMAN eignet sich für die meisten Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-129">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="0b4b5-130">Dieser Parameter ist für die Verwendung bestimmt, wenn viele Computer Remote Verbindungen mit einem Computer herstellen, auf dem Windows PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-130">This parameter is designed to be used if many computers establish remote connections to one computer that is running Windows PowerShell.</span></span>
<span data-ttu-id="0b4b5-131">In diesem Fall wird Web Services for Management (WS-Management) aus Gründen der Effizienz von IIS gehostet.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-131">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="0b4b5-132">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0b4b5-132">-Authentication</span></span>
<span data-ttu-id="0b4b5-133">Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-133">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="0b4b5-134">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="0b4b5-134">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0b4b5-135">Standard.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-135">Basic.</span></span>
<span data-ttu-id="0b4b5-136">„Basic“ ist ein Schema, bei dem der Benutzername und das Kennwort im Klartext an den Server oder Proxy gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-136">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="0b4b5-137">Standard.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-137">Default.</span></span>
<span data-ttu-id="0b4b5-138">Verwendet die vom WS-Verwaltungsprotokoll implementierte Authentifizierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-138">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="0b4b5-139">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-139">This is the default.</span></span>
- <span data-ttu-id="0b4b5-140">Digest.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-140">Digest.</span></span>
<span data-ttu-id="0b4b5-141">„Digest“ ist ein Abfrage/Rückmeldung-Schema, bei dem eine vom Server angegebene Datenzeichenfolge für die Abfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-141">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="0b4b5-142">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-142">Kerberos.</span></span>
<span data-ttu-id="0b4b5-143">Der Clientcomputer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-143">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="0b4b5-144">Negotiate</span><span class="sxs-lookup"><span data-stu-id="0b4b5-144">Negotiate.</span></span>
<span data-ttu-id="0b4b5-145">„Negotiate“ ist ein Abfrage/Rückmeldung-Schema, bei dem das für die Authentifizierung zu verwendende Schema mit dem Server oder Proxy ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-145">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="0b4b5-146">Dieser Parameterwert ermöglicht beispielsweise die Aushandlung, um zu bestimmen, ob das Kerberos-Protokoll oder NTLM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-146">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="0b4b5-147">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-147">CredSSP.</span></span>
<span data-ttu-id="0b4b5-148">Verwenden Sie die Authentifizierung der Credential Security Support Provider (kredssp), mit der der Benutzer Anmelde Informationen delegieren kann.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-148">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="0b4b5-149">Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-149">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="0b4b5-150">Vorsicht: die Anmelde Informationen des Benutzers werden vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-150">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="0b4b5-151">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-151">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="0b4b5-152">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-152">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

<span data-ttu-id="0b4b5-153">Wichtig: Wenn Sie den *Authentifizierungs* Parameter nicht angeben, wird die **Test-WSMAN-** Anforderung anonym an den Remote Computer gesendet, ohne die-Authentifizierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-153">Important: If you do not specify the *Authentication* parameter,, the **Test-WSMan** request is sent to the remote computer anonymously, without using authentication.</span></span>
<span data-ttu-id="0b4b5-154">Wenn die Anforderung anonym erfolgt, werden keine Informationen zurückgegeben, die spezifisch für die Betriebssystemversion sind.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-154">If the request is made anonymously, it returns no information that is specific to the operating-system version.</span></span>
<span data-ttu-id="0b4b5-155">Stattdessen zeigt dieses Cmdlet NULL-Werte für die Betriebssystemversion und Service Pack Ebene an (OS: 0.0.0 SP: 0,0).</span><span class="sxs-lookup"><span data-stu-id="0b4b5-155">Instead, this cmdlet displays null values for the operating system version and service pack level (OS: 0.0.0 SP: 0.0).</span></span>

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

### <span data-ttu-id="0b4b5-156">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="0b4b5-156">-CertificateThumbprint</span></span>
<span data-ttu-id="0b4b5-157">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-157">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="0b4b5-158">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-158">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="0b4b5-159">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-159">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="0b4b5-160">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-160">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="0b4b5-161">Um einen Zertifikatfingerabdruck abzurufen, verwenden Sie den Get-Item-Befehl oder Get-ChildItem-Befehl auf dem Windows PowerShell-Laufwerk „Cert:“.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-161">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="0b4b5-162">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0b4b5-162">-ComputerName</span></span>
<span data-ttu-id="0b4b5-163">Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-163">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="0b4b5-164">Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-164">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="0b4b5-165">Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-165">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="0b4b5-166">Der lokale Computer ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-166">The local computer is the default.</span></span>
<span data-ttu-id="0b4b5-167">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-167">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="0b4b5-168">Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-168">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: cn

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0b4b5-169">-Credential</span><span class="sxs-lookup"><span data-stu-id="0b4b5-169">-Credential</span></span>
<span data-ttu-id="0b4b5-170">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-170">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="0b4b5-171">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-171">The default is the current user.</span></span>
<span data-ttu-id="0b4b5-172">Geben Sie einen Benutzernamen ein, z. b. USER01, Domain01\User01 oder User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="0b4b5-172">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="0b4b5-173">Oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom Get-Credential-Cmdlet zurück gegebenes Objekt.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-173">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="0b4b5-174">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-174">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="0b4b5-175">-Port</span><span class="sxs-lookup"><span data-stu-id="0b4b5-175">-Port</span></span>
<span data-ttu-id="0b4b5-176">Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-176">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="0b4b5-177">Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-177">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="0b4b5-178">Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-178">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="0b4b5-179">Wenn Sie HTTPS als Transport verwenden, muss der Wert des *Computername* -Parameters mit dem allgemeinen Namen des Serverzertifikats (CN) identisch sein.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-179">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>

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

### <span data-ttu-id="0b4b5-180">-US-</span><span class="sxs-lookup"><span data-stu-id="0b4b5-180">-UseSSL</span></span>
<span data-ttu-id="0b4b5-181">Gibt an, dass das Secure Sockets Layer (SSL)-Protokoll verwendet wird, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-181">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="0b4b5-182">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-182">By default, SSL is not used.</span></span>

<span data-ttu-id="0b4b5-183">WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-183">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="0b4b5-184">Mit *dem Parameter "* Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-184">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="0b4b5-185">Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-185">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="0b4b5-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0b4b5-186">CommonParameters</span></span>
<span data-ttu-id="0b4b5-187">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0b4b5-188">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0b4b5-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0b4b5-189">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0b4b5-189">INPUTS</span></span>

### <span data-ttu-id="0b4b5-190">Keine</span><span class="sxs-lookup"><span data-stu-id="0b4b5-190">None</span></span>
<span data-ttu-id="0b4b5-191">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-191">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="0b4b5-192">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0b4b5-192">OUTPUTS</span></span>

### <span data-ttu-id="0b4b5-193">Keine</span><span class="sxs-lookup"><span data-stu-id="0b4b5-193">None</span></span>
<span data-ttu-id="0b4b5-194">Dieses Cmdlet generiert kein Ausgabeobjekt.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-194">This cmdlet does not generate any output object.</span></span>

## <span data-ttu-id="0b4b5-195">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0b4b5-195">NOTES</span></span>

* <span data-ttu-id="0b4b5-196">Standardmäßig fragt das **Test-WSMAN-** Cmdlet den WinRM-Dienst ohne Authentifizierung ab und gibt keine für die Betriebssystemversion spezifischen Informationen zurück.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-196">By default, the **Test-WSMan** cmdlet queries the WinRM service without using authentication, and it returns no information that is specific to the operating-system version.</span></span> <span data-ttu-id="0b4b5-197">Stattdessen werden NULL-Werte für die Betriebssystemversion und die Service Pack Ebene (OS: 0.0.0 SP: 0,0) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b4b5-197">Instead, it displays null values for the operating system version and service pack level (OS: 0.0.0 SP: 0.0).</span></span>

*

## <span data-ttu-id="0b4b5-198">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0b4b5-198">RELATED LINKS</span></span>

[<span data-ttu-id="0b4b5-199">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="0b4b5-199">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="0b4b5-200">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0b4b5-200">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="0b4b5-201">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="0b4b5-201">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="0b4b5-202">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0b4b5-202">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="0b4b5-203">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0b4b5-203">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="0b4b5-204">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0b4b5-204">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="0b4b5-205">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="0b4b5-205">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="0b4b5-206">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0b4b5-206">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="0b4b5-207">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="0b4b5-207">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="0b4b5-208">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0b4b5-208">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="0b4b5-209">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0b4b5-209">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="0b4b5-210">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="0b4b5-210">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)
