---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmaninstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManInstance
ms.openlocfilehash: 2e5d68c2a75ea3040fd3998d2dc469200c054e58
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601321"
---
# <span data-ttu-id="31736-102">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="31736-102">Set-WSManInstance</span></span>

## <span data-ttu-id="31736-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="31736-103">SYNOPSIS</span></span>
<span data-ttu-id="31736-104">Ändert die mit einer Ressource verknüpften Verwaltungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="31736-104">Modifies the management information that is related to a resource.</span></span>

## <span data-ttu-id="31736-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="31736-105">SYNTAX</span></span>

### <span data-ttu-id="31736-106">Computername (Standard)</span><span class="sxs-lookup"><span data-stu-id="31736-106">ComputerName (Default)</span></span>

```
Set-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-Dialect <Uri>] [-FilePath <String>]
 [-Fragment <String>] [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri>
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="31736-107">URI</span><span class="sxs-lookup"><span data-stu-id="31736-107">URI</span></span>

```
Set-WSManInstance [-ConnectionURI <Uri>] [-Dialect <Uri>] [-FilePath <String>] [-Fragment <String>]
 [-OptionSet <Hashtable>] [-ResourceURI] <Uri> [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-ValueSet <Hashtable>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="31736-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="31736-108">DESCRIPTION</span></span>

<span data-ttu-id="31736-109">Das Set-WSManInstance-Cmdlet ändert die mit einer Ressource verknüpften Verwaltungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="31736-109">The Set-WSManInstance cmdlet modifies the management information that is related to a resource.</span></span>

<span data-ttu-id="31736-110">Das Cmdlet verwendet die Verbindungs-/Transportschicht von WinRM zum Ändern der Informationen.</span><span class="sxs-lookup"><span data-stu-id="31736-110">This cmdlet uses the WinRM connection/transport layer to modify the information.</span></span>

## <span data-ttu-id="31736-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="31736-111">EXAMPLES</span></span>

### <span data-ttu-id="31736-112">Beispiel 1: Deaktivieren eines Listener auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="31736-112">Example 1: Disable a listener on the local computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{address="*";transport="https"} -ValueSet @{Enabled="false"}
```

```Output
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTPS
Port                  : 443
Hostname              :
Enabled               : false
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {127.0.0.1, 172.30.168.171, ::1, 2001:4898:0:fff:0:5efe:172.30.168.171...}
```

<span data-ttu-id="31736-113">Dieser Befehl deaktiviert den HTTPS-Listener auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="31736-113">This command disables the https listener on the local computer.</span></span>

<span data-ttu-id="31736-114">Wichtig: beim Zuordnen der angegebenen Eigenschaften *wird die Groß* -/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="31736-114">Important: The *ValueSet* parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="31736-115">Beispielsweise wird in diesem Befehl</span><span class="sxs-lookup"><span data-stu-id="31736-115">For example, in this command,</span></span>

<span data-ttu-id="31736-116">Dies schlägt fehl: `-ValueSet @{enabled="False"}`</span><span class="sxs-lookup"><span data-stu-id="31736-116">This fails: `-ValueSet @{enabled="False"}`</span></span>

<span data-ttu-id="31736-117">Dies ist erfolgreich: `-ValueSet @{Enabled="False"}`</span><span class="sxs-lookup"><span data-stu-id="31736-117">This succeeds: `-ValueSet @{Enabled="False"}`</span></span>

### <span data-ttu-id="31736-118">Beispiel 2: Festlegen der maximalen Umschlag Größe auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="31736-118">Example 2: Set the maximum envelope size on the local computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config -ValueSet @{MaxEnvelopeSizekb = "200"}
```

```Output
cfg                 : http://schemas.microsoft.com/wbem/wsman/1/config
lang                : en-US
MaxEnvelopeSizekb   : 200
MaxTimeoutms        : 60000
MaxBatchItems       : 32000
MaxProviderRequests : 4294967295
Client              : Client
Service             : Service
Winrs               : Winrs
```

<span data-ttu-id="31736-119">Dieser Befehl legt den MaxEnvelopeSizekb-Wert auf dem lokalen Computer auf 200 fest.</span><span class="sxs-lookup"><span data-stu-id="31736-119">This command sets the MaxEnvelopeSizekb value to 200 on the local computer.</span></span>

<span data-ttu-id="31736-120">Wichtig: beim Zuordnen der angegebenen Eigenschaften wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="31736-120">Important: The ValueSet parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="31736-121">Siehe folgendes Beispiel zum vorherigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="31736-121">For example, using the above command.</span></span>

<span data-ttu-id="31736-122">Dies schlägt fehl:-valueset @ {maxenvelopesizekb = "200"}</span><span class="sxs-lookup"><span data-stu-id="31736-122">This fails:     -ValueSet @{MaxEnvelopeSizeKB ="200"}</span></span>

<span data-ttu-id="31736-123">Dies ist erfolgreich:-valueset @ {maxenvelopesizekb = "200"}</span><span class="sxs-lookup"><span data-stu-id="31736-123">This succeeds:  -ValueSet @{MaxEnvelopeSizekb ="200"}</span></span>

### <span data-ttu-id="31736-124">Beispiel 3: Deaktivieren eines Listener auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="31736-124">Example 3: Disable a listener on a remote computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config/listener -ComputerName SERVER02 -SelectorSet @{address="*";transport="https"} -ValueSet @{Enabled="false"}
```

```Output
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTPS
Port                  : 443
Hostname              :
Enabled               : false
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {127.0.0.1, 172.30.168.172, ::1, 2001:4898:0:fff:0:5efe:172.30.168.172...}
```

<span data-ttu-id="31736-125">Dieser Befehl deaktiviert den HTTPS-Listener auf dem Remotecomputer SERVER02.</span><span class="sxs-lookup"><span data-stu-id="31736-125">This command disables the https listener on the remote computer SERVER02.</span></span>

<span data-ttu-id="31736-126">Wichtig: beim Zuordnen der angegebenen Eigenschaften wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="31736-126">Important: The ValueSet parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="31736-127">Siehe folgendes Beispiel zum vorherigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="31736-127">For example, using the above command.</span></span>

<span data-ttu-id="31736-128">Dies schlägt fehl:-valueset @ {aktiviert = "false"}</span><span class="sxs-lookup"><span data-stu-id="31736-128">This fails:     -ValueSet @{enabled="False"}</span></span>

<span data-ttu-id="31736-129">Dies ist erfolgreich:-valueset @ {aktiviert = "false"}</span><span class="sxs-lookup"><span data-stu-id="31736-129">This succeeds:  -ValueSet @{Enabled="False"}</span></span>

## <span data-ttu-id="31736-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="31736-130">PARAMETERS</span></span>

### <span data-ttu-id="31736-131">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="31736-131">-ApplicationName</span></span>

<span data-ttu-id="31736-132">Gibt den Anwendungsnamen in der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="31736-132">Specifies the application name in the connection.</span></span>
<span data-ttu-id="31736-133">Der Standardwert des ApplicationName-Parameters lautet „WSMAN“.</span><span class="sxs-lookup"><span data-stu-id="31736-133">The default value of the ApplicationName parameter is "WSMAN".</span></span>
<span data-ttu-id="31736-134">Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="31736-134">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="31736-135">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="31736-135">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="31736-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="31736-136">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="31736-137">Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="31736-137">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="31736-138">Die Standardeinstellung „WSMAN“ eignet sich für die meisten Verwendungszwecke.</span><span class="sxs-lookup"><span data-stu-id="31736-138">This default setting of "WSMAN" is appropriate for most uses.</span></span>
<span data-ttu-id="31736-139">Dieser Parameter soll verwendet werden, wenn mehrere Computer Remoteverbindungen mit einem Computer herstellen, auf dem Windows PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="31736-139">This parameter is designed to be used when numerous computers establish remote connections to one computer that is running Windows PowerShell.</span></span>
<span data-ttu-id="31736-140">In diesem Fall wird Web Services for Management (WS-Management) aus Gründen der Effizienz von IIS gehostet.</span><span class="sxs-lookup"><span data-stu-id="31736-140">In this case, IIS hosts Web Services for Management (WS-Management ) for efficiency.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: Wsman
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31736-141">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="31736-141">-Authentication</span></span>

<span data-ttu-id="31736-142">Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="31736-142">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="31736-143">Dabei sind folgende Werte möglich:</span><span class="sxs-lookup"><span data-stu-id="31736-143">Possible values are:</span></span>

- <span data-ttu-id="31736-144">Basic: Standard ist ein Schema, in dem der Benutzername und das Kennwort als Klartext an den Server oder Proxy gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="31736-144">Basic: Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="31736-145">Standardwert: Verwenden Sie die vom WS-Management Protokoll implementierte Authentifizierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="31736-145">Default : Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="31736-146">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="31736-146">This is the default.</span></span>
- <span data-ttu-id="31736-147">Digest: Digest ist ein Challenge-Response-Schema, das eine vom Server angegebene Daten Zeichenfolge für die Abfrage verwendet.</span><span class="sxs-lookup"><span data-stu-id="31736-147">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="31736-148">Kerberos: der Client Computer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="31736-148">Kerberos: The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="31736-149">Aushandeln: aushandeln ist ein Challenge-Response-Schema, das mit dem Server oder Proxy aushandelt, um das für die Authentifizierung zu verwendende Schema zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="31736-149">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="31736-150">Dieser Parameterwert ermöglicht es z. B., die Verwendung des Kerberos-Protokolls oder von NTLM auszuhandeln.</span><span class="sxs-lookup"><span data-stu-id="31736-150">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="31736-151">Kredssp: verwendet die Authentifizierung des Credential Security Support Provider (aufwärtssp), die dem Benutzer das Delegieren von Anmelde Informationen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="31736-151">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="31736-152">Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.</span><span class="sxs-lookup"><span data-stu-id="31736-152">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="31736-153">Vorsicht: die Anmelde Informationen des Benutzers werden vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="31736-153">Caution: CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="31736-154">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="31736-154">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="31736-155">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31736-155">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31736-156">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="31736-156">-CertificateThumbprint</span></span>

<span data-ttu-id="31736-157">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="31736-157">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="31736-158">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="31736-158">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="31736-159">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="31736-159">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="31736-160">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="31736-160">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="31736-161">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den Befehl Get-Item oder Get-ChildItem im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="31736-161">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="31736-162">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="31736-162">-ComputerName</span></span>

<span data-ttu-id="31736-163">Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="31736-163">Specifies the computer against which you want to run the management operation.</span></span>
<span data-ttu-id="31736-164">Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="31736-164">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="31736-165">Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="31736-165">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="31736-166">Der lokale Computer ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="31736-166">The local computer is the default.</span></span>
<span data-ttu-id="31736-167">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="31736-167">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="31736-168">Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="31736-168">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31736-169">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="31736-169">-ConnectionURI</span></span>

<span data-ttu-id="31736-170">Gibt den Verbindungsendpunkt an.</span><span class="sxs-lookup"><span data-stu-id="31736-170">Specifies the connection endpoint.</span></span>
<span data-ttu-id="31736-171">Das Format dieser Zeichenfolge lautet:</span><span class="sxs-lookup"><span data-stu-id="31736-171">The format of this string is:</span></span>

<span data-ttu-id="31736-172">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="31736-172">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="31736-173">Die folgende Zeichenfolge ist ein ordnungsgemäß formatierter Wert für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="31736-173">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="31736-174">Der URI muss voll qualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="31736-174">The URI must be fully qualified .</span></span>

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

### <span data-ttu-id="31736-175">-Credential</span><span class="sxs-lookup"><span data-stu-id="31736-175">-Credential</span></span>

<span data-ttu-id="31736-176">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="31736-176">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="31736-177">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="31736-177">The default is the current user.</span></span>
<span data-ttu-id="31736-178">Geben Sie einen Benutzernamen ein, z. b. "USER01", "Domain01\User01" oder " User@Domain.com ".</span><span class="sxs-lookup"><span data-stu-id="31736-178">Type a user name, such as "User01", "Domain01\User01", or "User@Domain.com".</span></span>
<span data-ttu-id="31736-179">Oder geben Sie ein PSCredential-Objekt ein, z. B. ein vom Get-Credential-Cmdlet zurückgegebenes Objekt.</span><span class="sxs-lookup"><span data-stu-id="31736-179">Or, enter a PSCredential object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="31736-180">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="31736-180">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="31736-181">-Dialekt</span><span class="sxs-lookup"><span data-stu-id="31736-181">-Dialect</span></span>

<span data-ttu-id="31736-182">Gibt den im Filterprädikat zu verwendenden Dialekt an.</span><span class="sxs-lookup"><span data-stu-id="31736-182">Specifies the dialect to use in the filter predicate.</span></span>
<span data-ttu-id="31736-183">Dies kann ein beliebiger vom Remotedienst unterstützter Dialekt sein.</span><span class="sxs-lookup"><span data-stu-id="31736-183">This can be any dialect that is supported by the remote service.</span></span>
<span data-ttu-id="31736-184">Die folgenden Aliase können für den Dialekt-URI verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="31736-184">The following aliases can be used for the dialect URI:</span></span>

- <span data-ttu-id="31736-185">WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span><span class="sxs-lookup"><span data-stu-id="31736-185">WQL: `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span></span>
- <span data-ttu-id="31736-186">Ktor `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span><span class="sxs-lookup"><span data-stu-id="31736-186">Selector: `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span></span>
- <span data-ttu-id="31736-187">Anwalt `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span><span class="sxs-lookup"><span data-stu-id="31736-187">Association: `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: http://schemas.microsoft.com/wbem/wsman/1/WQL
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31736-188">-FilePath</span><span class="sxs-lookup"><span data-stu-id="31736-188">-FilePath</span></span>

<span data-ttu-id="31736-189">Gibt den Pfad einer Datei an, die zum Aktualisieren einer Verwaltungsressource verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31736-189">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="31736-190">Sie geben die Verwaltungsressource mit dem ResourceURI-Parameter und SelectorSet-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="31736-190">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter .</span></span>
<span data-ttu-id="31736-191">Der folgende Befehl verwendet z. B. den FilePath-Parameter:</span><span class="sxs-lookup"><span data-stu-id="31736-191">For example, the following command uses the FilePath parameter:</span></span>

`Invoke-WSManAction -action StopService -resourceuri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:c:\input.xml -authentication default`

<span data-ttu-id="31736-192">Dieser Befehl ruft die StopService-Methode für den Spoolerdienst auf und verwendet für die Eingabe eine Datei.</span><span class="sxs-lookup"><span data-stu-id="31736-192">This command calls the StopService method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="31736-193">Die Datei „Input.xml“ weist folgenden Inhalt auf:</span><span class="sxs-lookup"><span data-stu-id="31736-193">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="31736-194">-Fragment</span><span class="sxs-lookup"><span data-stu-id="31736-194">-Fragment</span></span>

<span data-ttu-id="31736-195">Gibt einen Abschnitt innerhalb der Instanz an, die aktualisiert oder für den angegebenen Vorgang abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="31736-195">Specifies a section inside the instance that is to be updated or retrieved for the specified operation.</span></span>
<span data-ttu-id="31736-196">Um beispielsweise den Status eines Spoolerdiensts abzurufen, geben Sie „-Fragment-Status“ ein.</span><span class="sxs-lookup"><span data-stu-id="31736-196">For example, to get the status of a spooler service, specify "-Fragment Status".</span></span>

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

### <span data-ttu-id="31736-197">-OptionSET</span><span class="sxs-lookup"><span data-stu-id="31736-197">-OptionSet</span></span>

<span data-ttu-id="31736-198">Übergibt eine Reihe von Schaltern an einen Dienst, um die Art der Anforderung zu ändern oder zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="31736-198">Passes a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="31736-199">Diese sind mit Schaltern in Befehlszeilenshells vergleichbar, da sie dienstspezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="31736-199">These are similar to switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="31736-200">Es können beliebig viele Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="31736-200">Any number of options can be specified.</span></span>

<span data-ttu-id="31736-201">Das folgende Beispiel veranschaulicht die Syntax, durch die die Werte 1, 2 und 3 für die Parameter „a“, „b“ und „c“ übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="31736-201">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

<span data-ttu-id="31736-202">-OptionSet @{a=1;b=2;c=3}</span><span class="sxs-lookup"><span data-stu-id="31736-202">-OptionSet @{a=1;b=2;c=3}</span></span>

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

### <span data-ttu-id="31736-203">-Port</span><span class="sxs-lookup"><span data-stu-id="31736-203">-Port</span></span>

<span data-ttu-id="31736-204">Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="31736-204">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="31736-205">Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80.</span><span class="sxs-lookup"><span data-stu-id="31736-205">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="31736-206">Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.</span><span class="sxs-lookup"><span data-stu-id="31736-206">When the transport is HTTPS, the default port is 443.</span></span>
<span data-ttu-id="31736-207">Wenn Sie HTTPS als Transport verwenden, muss der Wert des ComputerName-Parameters mit dem allgemeinen Namen des Serverzertifikats übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="31736-207">When you use HTTPS as the transport, the value of the ComputerName parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="31736-208">Wenn der SkipCNCheck-Parameter jedoch als Teil des SessionOption-Parameters angegeben wird, muss der allgemeine Servername im Zertifikat nicht mit dem Hostnamen des Servers übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="31736-208">However, if the SkipCNCheck parameter is specified as part of the SessionOption parameter, then the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="31736-209">Der SkipCNCheck-Parameter darf nur für vertrauenswürdige Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31736-209">The SkipCNCheck parameter should be used only for trusted machines.</span></span>

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

### <span data-ttu-id="31736-210">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="31736-210">-ResourceURI</span></span>

<span data-ttu-id="31736-211">Enthält den URI (Uniform Resource Identifier) der Ressourcenklasse oder -instanz.</span><span class="sxs-lookup"><span data-stu-id="31736-211">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="31736-212">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="31736-212">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="31736-213">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="31736-213">A URI consists of a prefix and a path to a resource.</span></span>
<span data-ttu-id="31736-214">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="31736-214">For example:</span></span>

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

### <span data-ttu-id="31736-215">-Selector Set</span><span class="sxs-lookup"><span data-stu-id="31736-215">-SelectorSet</span></span>

<span data-ttu-id="31736-216">Gibt eine Reihe von Wertpaaren an, mit denen bestimmte Instanzen von Verwaltungsressourcen ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="31736-216">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="31736-217">Der SelectorSet-Parameter wird verwendet, wenn mehr als eine Instanz der Ressource vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="31736-217">The SelectorSet parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="31736-218">Der Wert des SelectorSet-Parameters muss eine Hashtabelle sein.</span><span class="sxs-lookup"><span data-stu-id="31736-218">The value of the SelectorSet parameter must be a hash table.</span></span>
<span data-ttu-id="31736-219">Das folgende Beispiel zeigt, wie Sie einen Wert für diesen Parameter eingeben:</span><span class="sxs-lookup"><span data-stu-id="31736-219">The following example shows how to enter a value for this parameter:</span></span>

<span data-ttu-id="31736-220">-SelectorSet @{Name="WinRM";ID="yyy"}</span><span class="sxs-lookup"><span data-stu-id="31736-220">-SelectorSet @{Name="WinRM";ID="yyy"}</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="31736-221">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="31736-221">-SessionOption</span></span>

<span data-ttu-id="31736-222">Definiert eine Reihe von erweiterten Optionen für die WS-Management-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="31736-222">Defines a set of extended options for the WS-Management session.</span></span>
<span data-ttu-id="31736-223">Geben Sie ein SessionOption-Objekt ein, das Sie mit dem New-WSManSessionOption-Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="31736-223">Enter a SessionOption object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="31736-224">Weitere Informationen zu den verfügbaren Optionen finden Sie unter „New-WSManSessionOption“.</span><span class="sxs-lookup"><span data-stu-id="31736-224">For more information about the options that are available, see New-WSManSessionOption.</span></span>

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

### <span data-ttu-id="31736-225">-US-</span><span class="sxs-lookup"><span data-stu-id="31736-225">-UseSSL</span></span>

<span data-ttu-id="31736-226">Gibt an, dass das SSL (Secure Sockets Layer)-Protokoll verwendet werden soll, um eine Verbindung mit dem Remotecomputer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="31736-226">Specifies that the Secure Sockets Layer (SSL) protocol should be used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="31736-227">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="31736-227">By default, SSL is not used.</span></span>

<span data-ttu-id="31736-228">WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="31736-228">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="31736-229">Mit dem UseSSL-Parameter können Sie anstelle von HTTP das sicherere HTTPS angeben.</span><span class="sxs-lookup"><span data-stu-id="31736-229">The UseSSL parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="31736-230">Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, verursacht der Befehl einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="31736-230">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="31736-231">-Valueset</span><span class="sxs-lookup"><span data-stu-id="31736-231">-ValueSet</span></span>

<span data-ttu-id="31736-232">Gibt eine Hashtabelle an, mit deren Hilfe eine Verwaltungsressource geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="31736-232">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="31736-233">Sie geben die Verwaltungs Ressource mit dem resourceUri-Parameter und dem selectorset-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="31736-233">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter.</span></span>
<span data-ttu-id="31736-234">Der Wert des ValueSet-Parameters muss eine Hashtabelle sein.</span><span class="sxs-lookup"><span data-stu-id="31736-234">The value of the ValueSet parameter must be a hash table.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="31736-235">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="31736-235">CommonParameters</span></span>

<span data-ttu-id="31736-236">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="31736-236">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="31736-237">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="31736-237">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="31736-238">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="31736-238">INPUTS</span></span>

### <span data-ttu-id="31736-239">Keine</span><span class="sxs-lookup"><span data-stu-id="31736-239">None</span></span>

<span data-ttu-id="31736-240">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="31736-240">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="31736-241">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="31736-241">OUTPUTS</span></span>

### <span data-ttu-id="31736-242">Keine</span><span class="sxs-lookup"><span data-stu-id="31736-242">None</span></span>

<span data-ttu-id="31736-243">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="31736-243">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="31736-244">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="31736-244">NOTES</span></span>

## <span data-ttu-id="31736-245">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="31736-245">RELATED LINKS</span></span>

[<span data-ttu-id="31736-246">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="31736-246">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="31736-247">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="31736-247">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="31736-248">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="31736-248">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="31736-249">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="31736-249">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="31736-250">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="31736-250">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="31736-251">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="31736-251">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="31736-252">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="31736-252">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="31736-253">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="31736-253">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="31736-254">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="31736-254">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="31736-255">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="31736-255">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="31736-256">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="31736-256">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="31736-257">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="31736-257">Test-WSMan</span></span>](Test-WSMan.md)

