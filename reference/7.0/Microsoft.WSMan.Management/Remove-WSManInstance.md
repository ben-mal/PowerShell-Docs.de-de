---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/remove-wsmaninstance?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WSManInstance
ms.openlocfilehash: 0e605d35b485740a7fbe7408427aa191983cc436
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218348"
---
# <span data-ttu-id="7ec8f-103">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="7ec8f-103">Remove-WSManInstance</span></span>

## <span data-ttu-id="7ec8f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7ec8f-104">SYNOPSIS</span></span>
<span data-ttu-id="7ec8f-105">Löscht eine Instanz einer Verwaltungsressource.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-105">Deletes a management resource instance.</span></span>

## <span data-ttu-id="7ec8f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7ec8f-106">SYNTAX</span></span>

### <span data-ttu-id="7ec8f-107">Computername (Standard)</span><span class="sxs-lookup"><span data-stu-id="7ec8f-107">ComputerName (Default)</span></span>

```
Remove-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-OptionSet <Hashtable>]
 [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-UseSSL]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="7ec8f-108">URI</span><span class="sxs-lookup"><span data-stu-id="7ec8f-108">URI</span></span>

```
Remove-WSManInstance [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="7ec8f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7ec8f-109">DESCRIPTION</span></span>

<span data-ttu-id="7ec8f-110">Das **Remove-wsmaninstance** -Cmdlet löscht eine Instanz einer Verwaltungs Ressource, die in den Parametern " *resourceUri* " und " *selectorset* " angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-110">The **Remove-WSManInstance** cmdlet deletes an instance of a management resource that is specified in the *ResourceURI* and *SelectorSet* parameters.</span></span>

<span data-ttu-id="7ec8f-111">Das Cmdlet verwendet die Verbindungs-/Transportschicht von WinRM, um die Instanz der Verwaltungsressource zu löschen.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-111">This cmdlet uses the WinRM connection/transport layer to delete the management resource instance.</span></span>

## <span data-ttu-id="7ec8f-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7ec8f-112">EXAMPLES</span></span>

### <span data-ttu-id="7ec8f-113">Beispiel 1: Löschen eines Listener</span><span class="sxs-lookup"><span data-stu-id="7ec8f-113">Example 1: Delete a listener</span></span>

```
PS C:\> Remove-WSManInstance -ResourceUri winrm/config/Listener -SelectorSet Address=test.fabrikam.com;Transport=http
```

<span data-ttu-id="7ec8f-114">Mit diesem Befehl wird der WS-Management HTTP-Listener auf einem Computer gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-114">This command deletes the WS-Management HTTP listener on a computer.</span></span>

## <span data-ttu-id="7ec8f-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7ec8f-115">PARAMETERS</span></span>

### <span data-ttu-id="7ec8f-116">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="7ec8f-116">-ApplicationName</span></span>

<span data-ttu-id="7ec8f-117">Gibt den Anwendungsnamen in der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-117">Specifies the application name in the connection.</span></span>
<span data-ttu-id="7ec8f-118">Der Standardwert des *ApplicationName* -Parameters lautet "wsman".</span><span class="sxs-lookup"><span data-stu-id="7ec8f-118">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="7ec8f-119">Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="7ec8f-119">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="7ec8f-120">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="7ec8f-120">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="7ec8f-121">Beispiel: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="7ec8f-121">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="7ec8f-122">Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-122">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="7ec8f-123">Diese Standardeinstellung von WSMAN eignet sich für die meisten Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-123">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="7ec8f-124">Dieser Parameter ist für die Verwendung bestimmt, wenn viele Computer Remote Verbindungen mit einem Computer herstellen, auf dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-124">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="7ec8f-125">In diesem Fall wird Web Services for Management (WS-Management) aus Gründen der Effizienz von IIS gehostet.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-125">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="7ec8f-126">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7ec8f-126">-Authentication</span></span>

<span data-ttu-id="7ec8f-127">Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-127">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="7ec8f-128">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="7ec8f-128">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7ec8f-129">Standard.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-129">Basic.</span></span>
<span data-ttu-id="7ec8f-130">„Basic“ ist ein Schema, bei dem der Benutzername und das Kennwort im Klartext an den Server oder Proxy gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-130">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="7ec8f-131">Standard.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-131">Default.</span></span>
<span data-ttu-id="7ec8f-132">Verwendet die vom WS-Verwaltungsprotokoll implementierte Authentifizierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-132">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="7ec8f-133">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-133">This is the default.</span></span>
- <span data-ttu-id="7ec8f-134">Digest.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-134">Digest.</span></span>
<span data-ttu-id="7ec8f-135">„Digest“ ist ein Abfrage/Rückmeldung-Schema, bei dem eine vom Server angegebene Datenzeichenfolge für die Abfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-135">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="7ec8f-136">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-136">Kerberos.</span></span>
<span data-ttu-id="7ec8f-137">Der Clientcomputer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-137">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="7ec8f-138">Negotiate</span><span class="sxs-lookup"><span data-stu-id="7ec8f-138">Negotiate.</span></span>
<span data-ttu-id="7ec8f-139">„Negotiate“ ist ein Abfrage/Rückmeldung-Schema, bei dem das für die Authentifizierung zu verwendende Schema mit dem Server oder Proxy ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-139">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="7ec8f-140">Dieser Parameterwert ermöglicht beispielsweise die Aushandlung, um zu bestimmen, ob das Kerberos-Protokoll oder NTLM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-140">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="7ec8f-141">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-141">CredSSP.</span></span>
<span data-ttu-id="7ec8f-142">Verwenden Sie die Authentifizierung der Credential Security Support Provider (kredssp), mit der der Benutzer Anmelde Informationen delegieren kann.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-142">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="7ec8f-143">Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-143">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="7ec8f-144">Vorsicht: die Anmelde Informationen des Benutzers werden vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-144">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="7ec8f-145">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-145">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="7ec8f-146">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-146">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="7ec8f-147">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="7ec8f-147">-CertificateThumbprint</span></span>

<span data-ttu-id="7ec8f-148">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-148">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="7ec8f-149">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-149">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="7ec8f-150">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-150">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="7ec8f-151">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-151">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="7ec8f-152">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den Befehl Get-Item oder Get-ChildItem im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="7ec8f-152">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="7ec8f-153">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="7ec8f-153">-ComputerName</span></span>

<span data-ttu-id="7ec8f-154">Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-154">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="7ec8f-155">Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-155">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="7ec8f-156">Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-156">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="7ec8f-157">Der lokale Computer ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-157">The local computer is the default.</span></span>
<span data-ttu-id="7ec8f-158">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-158">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="7ec8f-159">Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-159">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7ec8f-160">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="7ec8f-160">-ConnectionURI</span></span>

<span data-ttu-id="7ec8f-161">Gibt den Verbindungsendpunkt an.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-161">Specifies the connection endpoint.</span></span>
<span data-ttu-id="7ec8f-162">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7ec8f-162">The format of this string is as follows:</span></span>

<span data-ttu-id="7ec8f-163">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="7ec8f-163">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="7ec8f-164">Die folgende Zeichenfolge ist ein ordnungsgemäß formatierter Wert für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="7ec8f-164">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="7ec8f-165">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-165">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="7ec8f-166">-Credential</span><span class="sxs-lookup"><span data-stu-id="7ec8f-166">-Credential</span></span>

<span data-ttu-id="7ec8f-167">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-167">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="7ec8f-168">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-168">The default is the current user.</span></span>
<span data-ttu-id="7ec8f-169">Geben Sie einen Benutzernamen ein, z. b. USER01, Domain01\User01 oder User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="7ec8f-169">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="7ec8f-170">Oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom Get-Credential-Cmdlet zurück gegebenes Objekt.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-170">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="7ec8f-171">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-171">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="7ec8f-172">-OptionSET</span><span class="sxs-lookup"><span data-stu-id="7ec8f-172">-OptionSet</span></span>

<span data-ttu-id="7ec8f-173">Gibt eine Reihe von Schaltern für einen Dienst an, um die Art der Anforderung zu ändern oder zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-173">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="7ec8f-174">Diese ähneln Switches, die in Befehlszeilenshells verwendet werden, da Sie Dienst spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-174">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="7ec8f-175">Es können beliebig viele Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-175">Any number of options can be specified.</span></span>

<span data-ttu-id="7ec8f-176">Das folgende Beispiel veranschaulicht die Syntax, durch die die Werte 1, 2 und 3 für die Parameter „a“, „b“ und „c“ übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="7ec8f-176">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="7ec8f-177">-Port</span><span class="sxs-lookup"><span data-stu-id="7ec8f-177">-Port</span></span>

<span data-ttu-id="7ec8f-178">Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-178">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="7ec8f-179">Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-179">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="7ec8f-180">Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-180">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="7ec8f-181">Wenn Sie HTTPS als Transport verwenden, muss der Wert des *Computername* -Parameters mit dem allgemeinen Namen des Serverzertifikats (CN) identisch sein.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-181">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="7ec8f-182">Wenn der *skipcncheck* -Parameter jedoch als Teil des *sessionoption* -Parameters angegeben wird, muss der allgemeine Name des Zertifikats für den Server nicht mit dem Hostnamen des Servers identisch sein.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-182">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="7ec8f-183">Der *skipcncheck* -Parameter sollte nur für vertrauenswürdige Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-183">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="7ec8f-184">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="7ec8f-184">-ResourceURI</span></span>

<span data-ttu-id="7ec8f-185">Gibt den URI der Ressourcen Klasse oder-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-185">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="7ec8f-186">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-186">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="7ec8f-187">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-187">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="7ec8f-188">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7ec8f-188">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ruri

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7ec8f-189">-Selector Set</span><span class="sxs-lookup"><span data-stu-id="7ec8f-189">-SelectorSet</span></span>

<span data-ttu-id="7ec8f-190">Gibt eine Reihe von Wertpaaren an, mit denen bestimmte Instanzen von Verwaltungsressourcen ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-190">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="7ec8f-191">Der *selectorset* -Parameter wird verwendet, wenn mehr als eine Instanz der Ressource vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-191">The *SelectorSet* parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="7ec8f-192">Der Wert von *Selector Set* muss eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-192">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="7ec8f-193">Das folgende Beispiel zeigt, wie Sie einen Wert für diesen Parameter eingeben:</span><span class="sxs-lookup"><span data-stu-id="7ec8f-193">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7ec8f-194">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="7ec8f-194">-SessionOption</span></span>

<span data-ttu-id="7ec8f-195">Gibt erweiterte Optionen für die WS-Management Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-195">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="7ec8f-196">Geben Sie ein **sessionoption** -Objekt ein, das Sie mit dem New-WSManSessionOption-Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-196">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="7ec8f-197">Geben Sie ein, um weitere Informationen zu den verfügbaren Optionen zu erhalten `Get-Help New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="7ec8f-197">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="7ec8f-198">-US-</span><span class="sxs-lookup"><span data-stu-id="7ec8f-198">-UseSSL</span></span>

<span data-ttu-id="7ec8f-199">Gibt an, dass das Secure Sockets Layer (SSL)-Protokoll verwendet wird, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-199">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="7ec8f-200">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-200">By default, SSL is not used.</span></span>

<span data-ttu-id="7ec8f-201">WS-Management verschlüsselt alle PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-201">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="7ec8f-202">Mit *dem Parameter "* Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-202">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="7ec8f-203">Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-203">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases: ssl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7ec8f-204">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7ec8f-204">CommonParameters</span></span>

<span data-ttu-id="7ec8f-205">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-205">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7ec8f-206">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7ec8f-206">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7ec8f-207">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7ec8f-207">INPUTS</span></span>

### <span data-ttu-id="7ec8f-208">Keine</span><span class="sxs-lookup"><span data-stu-id="7ec8f-208">None</span></span>

<span data-ttu-id="7ec8f-209">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-209">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="7ec8f-210">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7ec8f-210">OUTPUTS</span></span>

### <span data-ttu-id="7ec8f-211">Keine</span><span class="sxs-lookup"><span data-stu-id="7ec8f-211">None</span></span>

<span data-ttu-id="7ec8f-212">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-212">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7ec8f-213">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7ec8f-213">NOTES</span></span>

* <span data-ttu-id="7ec8f-214">Das Remove-WmiObject-Cmdlet ist ein vergleichbares Cmdlet der Windows-Verwaltungsinstrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="7ec8f-214">The Remove-WmiObject cmdlet, a Windows Management Instrumentation (WMI) cmdlet, is similar.</span></span> <span data-ttu-id="7ec8f-215">**Remove-WMIObject** verwendet die Verbindungs-/Transportschicht von DCOM zum Erstellen oder Aktualisieren von WMI-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="7ec8f-215">**Remove-WmiObject** uses the DCOM connection/transport layer to create or update WMI instances.</span></span>

*

## <span data-ttu-id="7ec8f-216">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7ec8f-216">RELATED LINKS</span></span>

[<span data-ttu-id="7ec8f-217">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="7ec8f-217">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="7ec8f-218">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="7ec8f-218">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="7ec8f-219">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="7ec8f-219">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="7ec8f-220">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="7ec8f-220">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="7ec8f-221">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="7ec8f-221">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="7ec8f-222">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="7ec8f-222">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="7ec8f-223">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="7ec8f-223">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="7ec8f-224">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="7ec8f-224">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="7ec8f-225">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="7ec8f-225">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="7ec8f-226">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="7ec8f-226">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="7ec8f-227">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="7ec8f-227">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="7ec8f-228">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="7ec8f-228">Test-WSMan</span></span>](Test-WSMan.md)
