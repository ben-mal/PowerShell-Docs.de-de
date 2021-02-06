---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/remove-wsmaninstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WSManInstance
ms.openlocfilehash: 4d1273fe1ed643f8d45b627db9863b75212b6b24
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602105"
---
# <span data-ttu-id="84340-102">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="84340-102">Remove-WSManInstance</span></span>

## <span data-ttu-id="84340-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="84340-103">SYNOPSIS</span></span>
<span data-ttu-id="84340-104">Löscht eine Instanz einer Verwaltungsressource.</span><span class="sxs-lookup"><span data-stu-id="84340-104">Deletes a management resource instance.</span></span>

## <span data-ttu-id="84340-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="84340-105">SYNTAX</span></span>

### <span data-ttu-id="84340-106">Computername (Standard)</span><span class="sxs-lookup"><span data-stu-id="84340-106">ComputerName (Default)</span></span>

```
Remove-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-OptionSet <Hashtable>]
 [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-UseSSL]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="84340-107">URI</span><span class="sxs-lookup"><span data-stu-id="84340-107">URI</span></span>

```
Remove-WSManInstance [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="84340-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="84340-108">DESCRIPTION</span></span>

<span data-ttu-id="84340-109">Das **Remove-wsmaninstance** -Cmdlet löscht eine Instanz einer Verwaltungs Ressource, die in den Parametern " *resourceUri* " und " *selectorset* " angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="84340-109">The **Remove-WSManInstance** cmdlet deletes an instance of a management resource that is specified in the *ResourceURI* and *SelectorSet* parameters.</span></span>

<span data-ttu-id="84340-110">Das Cmdlet verwendet die Verbindungs-/Transportschicht von WinRM, um die Instanz der Verwaltungsressource zu löschen.</span><span class="sxs-lookup"><span data-stu-id="84340-110">This cmdlet uses the WinRM connection/transport layer to delete the management resource instance.</span></span>

## <span data-ttu-id="84340-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="84340-111">EXAMPLES</span></span>

### <span data-ttu-id="84340-112">Beispiel 1: Löschen eines Listener</span><span class="sxs-lookup"><span data-stu-id="84340-112">Example 1: Delete a listener</span></span>

```
PS C:\> Remove-WSManInstance -ResourceUri winrm/config/Listener -SelectorSet Address=test.fabrikam.com;Transport=http
```

<span data-ttu-id="84340-113">Mit diesem Befehl wird der WS-Management HTTP-Listener auf einem Computer gelöscht.</span><span class="sxs-lookup"><span data-stu-id="84340-113">This command deletes the WS-Management HTTP listener on a computer.</span></span>

## <span data-ttu-id="84340-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="84340-114">PARAMETERS</span></span>

### <span data-ttu-id="84340-115">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="84340-115">-ApplicationName</span></span>

<span data-ttu-id="84340-116">Gibt den Anwendungsnamen in der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="84340-116">Specifies the application name in the connection.</span></span>
<span data-ttu-id="84340-117">Der Standardwert des *ApplicationName* -Parameters lautet "wsman".</span><span class="sxs-lookup"><span data-stu-id="84340-117">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="84340-118">Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="84340-118">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="84340-119">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="84340-119">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="84340-120">Beispiel: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="84340-120">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="84340-121">Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="84340-121">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="84340-122">Diese Standardeinstellung von WSMAN eignet sich für die meisten Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="84340-122">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="84340-123">Dieser Parameter ist für die Verwendung bestimmt, wenn viele Computer Remote Verbindungen mit einem Computer herstellen, auf dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="84340-123">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="84340-124">In diesem Fall wird Web Services for Management (WS-Management) aus Gründen der Effizienz von IIS gehostet.</span><span class="sxs-lookup"><span data-stu-id="84340-124">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="84340-125">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="84340-125">-Authentication</span></span>

<span data-ttu-id="84340-126">Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="84340-126">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="84340-127">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="84340-127">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="84340-128">Standard.</span><span class="sxs-lookup"><span data-stu-id="84340-128">Basic.</span></span>
<span data-ttu-id="84340-129">„Basic“ ist ein Schema, bei dem der Benutzername und das Kennwort im Klartext an den Server oder Proxy gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="84340-129">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="84340-130">Standard.</span><span class="sxs-lookup"><span data-stu-id="84340-130">Default.</span></span>
<span data-ttu-id="84340-131">Verwendet die vom WS-Verwaltungsprotokoll implementierte Authentifizierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="84340-131">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="84340-132">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="84340-132">This is the default.</span></span>
- <span data-ttu-id="84340-133">Digest.</span><span class="sxs-lookup"><span data-stu-id="84340-133">Digest.</span></span>
<span data-ttu-id="84340-134">„Digest“ ist ein Abfrage/Rückmeldung-Schema, bei dem eine vom Server angegebene Datenzeichenfolge für die Abfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84340-134">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="84340-135">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="84340-135">Kerberos.</span></span>
<span data-ttu-id="84340-136">Der Clientcomputer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="84340-136">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="84340-137">Negotiate</span><span class="sxs-lookup"><span data-stu-id="84340-137">Negotiate.</span></span>
<span data-ttu-id="84340-138">„Negotiate“ ist ein Abfrage/Rückmeldung-Schema, bei dem das für die Authentifizierung zu verwendende Schema mit dem Server oder Proxy ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="84340-138">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="84340-139">Dieser Parameterwert ermöglicht beispielsweise die Aushandlung, um zu bestimmen, ob das Kerberos-Protokoll oder NTLM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84340-139">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="84340-140">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="84340-140">CredSSP.</span></span>
<span data-ttu-id="84340-141">Verwenden Sie die Authentifizierung der Credential Security Support Provider (kredssp), mit der der Benutzer Anmelde Informationen delegieren kann.</span><span class="sxs-lookup"><span data-stu-id="84340-141">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="84340-142">Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.</span><span class="sxs-lookup"><span data-stu-id="84340-142">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="84340-143">Vorsicht: die Anmelde Informationen des Benutzers werden vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="84340-143">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="84340-144">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="84340-144">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="84340-145">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="84340-145">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="84340-146">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="84340-146">-CertificateThumbprint</span></span>

<span data-ttu-id="84340-147">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="84340-147">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="84340-148">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="84340-148">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="84340-149">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="84340-149">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="84340-150">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="84340-150">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="84340-151">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den Befehl Get-Item oder Get-ChildItem im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="84340-151">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="84340-152">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="84340-152">-ComputerName</span></span>

<span data-ttu-id="84340-153">Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="84340-153">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="84340-154">Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="84340-154">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="84340-155">Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="84340-155">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="84340-156">Der lokale Computer ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="84340-156">The local computer is the default.</span></span>
<span data-ttu-id="84340-157">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="84340-157">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="84340-158">Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="84340-158">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="84340-159">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="84340-159">-ConnectionURI</span></span>

<span data-ttu-id="84340-160">Gibt den Verbindungsendpunkt an.</span><span class="sxs-lookup"><span data-stu-id="84340-160">Specifies the connection endpoint.</span></span>
<span data-ttu-id="84340-161">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="84340-161">The format of this string is as follows:</span></span>

<span data-ttu-id="84340-162">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="84340-162">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="84340-163">Die folgende Zeichenfolge ist ein ordnungsgemäß formatierter Wert für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="84340-163">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="84340-164">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="84340-164">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="84340-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="84340-165">-Credential</span></span>

<span data-ttu-id="84340-166">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="84340-166">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="84340-167">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="84340-167">The default is the current user.</span></span>
<span data-ttu-id="84340-168">Geben Sie einen Benutzernamen ein, z. b. USER01, Domain01\User01 oder User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="84340-168">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="84340-169">Oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom Get-Credential-Cmdlet zurück gegebenes Objekt.</span><span class="sxs-lookup"><span data-stu-id="84340-169">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="84340-170">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="84340-170">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="84340-171">-OptionSET</span><span class="sxs-lookup"><span data-stu-id="84340-171">-OptionSet</span></span>

<span data-ttu-id="84340-172">Gibt eine Reihe von Schaltern für einen Dienst an, um die Art der Anforderung zu ändern oder zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="84340-172">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="84340-173">Diese ähneln Switches, die in Befehlszeilenshells verwendet werden, da Sie Dienst spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="84340-173">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="84340-174">Es können beliebig viele Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="84340-174">Any number of options can be specified.</span></span>

<span data-ttu-id="84340-175">Das folgende Beispiel veranschaulicht die Syntax, durch die die Werte 1, 2 und 3 für die Parameter „a“, „b“ und „c“ übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="84340-175">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="84340-176">-Port</span><span class="sxs-lookup"><span data-stu-id="84340-176">-Port</span></span>

<span data-ttu-id="84340-177">Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="84340-177">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="84340-178">Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80.</span><span class="sxs-lookup"><span data-stu-id="84340-178">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="84340-179">Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.</span><span class="sxs-lookup"><span data-stu-id="84340-179">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="84340-180">Wenn Sie HTTPS als Transport verwenden, muss der Wert des *Computername* -Parameters mit dem allgemeinen Namen des Serverzertifikats (CN) identisch sein.</span><span class="sxs-lookup"><span data-stu-id="84340-180">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="84340-181">Wenn der *skipcncheck* -Parameter jedoch als Teil des *sessionoption* -Parameters angegeben wird, muss der allgemeine Name des Zertifikats für den Server nicht mit dem Hostnamen des Servers identisch sein.</span><span class="sxs-lookup"><span data-stu-id="84340-181">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="84340-182">Der *skipcncheck* -Parameter sollte nur für vertrauenswürdige Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="84340-182">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="84340-183">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="84340-183">-ResourceURI</span></span>

<span data-ttu-id="84340-184">Gibt den URI der Ressourcen Klasse oder-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="84340-184">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="84340-185">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="84340-185">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="84340-186">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="84340-186">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="84340-187">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="84340-187">For example:</span></span>

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

### <span data-ttu-id="84340-188">-Selector Set</span><span class="sxs-lookup"><span data-stu-id="84340-188">-SelectorSet</span></span>

<span data-ttu-id="84340-189">Gibt eine Reihe von Wertpaaren an, mit denen bestimmte Instanzen von Verwaltungsressourcen ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="84340-189">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="84340-190">Der *selectorset* -Parameter wird verwendet, wenn mehr als eine Instanz der Ressource vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="84340-190">The *SelectorSet* parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="84340-191">Der Wert von *Selector Set* muss eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="84340-191">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="84340-192">Das folgende Beispiel zeigt, wie Sie einen Wert für diesen Parameter eingeben:</span><span class="sxs-lookup"><span data-stu-id="84340-192">The following example shows how to enter a value for this parameter:</span></span>

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

### <span data-ttu-id="84340-193">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="84340-193">-SessionOption</span></span>

<span data-ttu-id="84340-194">Gibt erweiterte Optionen für die WS-Management Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="84340-194">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="84340-195">Geben Sie ein **sessionoption** -Objekt ein, das Sie mit dem New-WSManSessionOption-Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="84340-195">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="84340-196">Geben Sie ein, um weitere Informationen zu den verfügbaren Optionen zu erhalten `Get-Help New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="84340-196">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="84340-197">-US-</span><span class="sxs-lookup"><span data-stu-id="84340-197">-UseSSL</span></span>

<span data-ttu-id="84340-198">Gibt an, dass das Secure Sockets Layer (SSL)-Protokoll verwendet wird, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="84340-198">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="84340-199">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="84340-199">By default, SSL is not used.</span></span>

<span data-ttu-id="84340-200">WS-Management verschlüsselt alle PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="84340-200">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="84340-201">Mit *dem Parameter "* Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.</span><span class="sxs-lookup"><span data-stu-id="84340-201">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="84340-202">Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="84340-202">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="84340-203">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="84340-203">CommonParameters</span></span>

<span data-ttu-id="84340-204">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="84340-204">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="84340-205">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="84340-205">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="84340-206">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="84340-206">INPUTS</span></span>

### <span data-ttu-id="84340-207">Keine</span><span class="sxs-lookup"><span data-stu-id="84340-207">None</span></span>

<span data-ttu-id="84340-208">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="84340-208">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="84340-209">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="84340-209">OUTPUTS</span></span>

### <span data-ttu-id="84340-210">Keine</span><span class="sxs-lookup"><span data-stu-id="84340-210">None</span></span>

<span data-ttu-id="84340-211">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="84340-211">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="84340-212">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="84340-212">NOTES</span></span>

* <span data-ttu-id="84340-213">Das Remove-WmiObject-Cmdlet ist ein vergleichbares Cmdlet der Windows-Verwaltungsinstrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="84340-213">The Remove-WmiObject cmdlet, a Windows Management Instrumentation (WMI) cmdlet, is similar.</span></span> <span data-ttu-id="84340-214">**Remove-WMIObject** verwendet die Verbindungs-/Transportschicht von DCOM zum Erstellen oder Aktualisieren von WMI-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="84340-214">**Remove-WmiObject** uses the DCOM connection/transport layer to create or update WMI instances.</span></span>

*

## <span data-ttu-id="84340-215">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="84340-215">RELATED LINKS</span></span>

[<span data-ttu-id="84340-216">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="84340-216">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="84340-217">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="84340-217">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="84340-218">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="84340-218">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="84340-219">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="84340-219">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="84340-220">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="84340-220">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="84340-221">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="84340-221">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="84340-222">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="84340-222">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="84340-223">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="84340-223">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="84340-224">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="84340-224">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="84340-225">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="84340-225">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="84340-226">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="84340-226">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="84340-227">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="84340-227">Test-WSMan</span></span>](Test-WSMan.md)

