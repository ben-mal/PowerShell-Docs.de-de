---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmaninstance?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManInstance
ms.openlocfilehash: 9060f683372617b3a01365ceb81668c75986f46d
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218708"
---
# <span data-ttu-id="3f589-103">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3f589-103">Set-WSManInstance</span></span>

## <span data-ttu-id="3f589-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3f589-104">SYNOPSIS</span></span>
<span data-ttu-id="3f589-105">Ändert die mit einer Ressource verknüpften Verwaltungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="3f589-105">Modifies the management information that is related to a resource.</span></span>

## <span data-ttu-id="3f589-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3f589-106">SYNTAX</span></span>

### <span data-ttu-id="3f589-107">Computername (Standard)</span><span class="sxs-lookup"><span data-stu-id="3f589-107">ComputerName (Default)</span></span>

```
Set-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-Dialect <Uri>] [-FilePath <String>]
 [-Fragment <String>] [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri>
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="3f589-108">URI</span><span class="sxs-lookup"><span data-stu-id="3f589-108">URI</span></span>

```
Set-WSManInstance [-ConnectionURI <Uri>] [-Dialect <Uri>] [-FilePath <String>] [-Fragment <String>]
 [-OptionSet <Hashtable>] [-ResourceURI] <Uri> [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-ValueSet <Hashtable>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="3f589-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3f589-109">DESCRIPTION</span></span>

<span data-ttu-id="3f589-110">Das Set-WSManInstance-Cmdlet ändert die mit einer Ressource verknüpften Verwaltungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="3f589-110">The Set-WSManInstance cmdlet modifies the management information that is related to a resource.</span></span>

<span data-ttu-id="3f589-111">Das Cmdlet verwendet die Verbindungs-/Transportschicht von WinRM zum Ändern der Informationen.</span><span class="sxs-lookup"><span data-stu-id="3f589-111">This cmdlet uses the WinRM connection/transport layer to modify the information.</span></span>

## <span data-ttu-id="3f589-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3f589-112">EXAMPLES</span></span>

### <span data-ttu-id="3f589-113">Beispiel 1: Deaktivieren eines Listener auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="3f589-113">Example 1: Disable a listener on the local computer</span></span>

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

<span data-ttu-id="3f589-114">Dieser Befehl deaktiviert den HTTPS-Listener auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="3f589-114">This command disables the https listener on the local computer.</span></span>

<span data-ttu-id="3f589-115">Wichtig: beim Zuordnen der angegebenen Eigenschaften *wird die Groß* -/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="3f589-115">Important: The *ValueSet* parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="3f589-116">Beispielsweise wird in diesem Befehl</span><span class="sxs-lookup"><span data-stu-id="3f589-116">For example, in this command,</span></span>

<span data-ttu-id="3f589-117">Dies schlägt fehl: `-ValueSet @{enabled="False"}`</span><span class="sxs-lookup"><span data-stu-id="3f589-117">This fails: `-ValueSet @{enabled="False"}`</span></span>

<span data-ttu-id="3f589-118">Dies ist erfolgreich: `-ValueSet @{Enabled="False"}`</span><span class="sxs-lookup"><span data-stu-id="3f589-118">This succeeds: `-ValueSet @{Enabled="False"}`</span></span>

### <span data-ttu-id="3f589-119">Beispiel 2: Festlegen der maximalen Umschlag Größe auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="3f589-119">Example 2: Set the maximum envelope size on the local computer</span></span>

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

<span data-ttu-id="3f589-120">Dieser Befehl legt den MaxEnvelopeSizekb-Wert auf dem lokalen Computer auf 200 fest.</span><span class="sxs-lookup"><span data-stu-id="3f589-120">This command sets the MaxEnvelopeSizekb value to 200 on the local computer.</span></span>

<span data-ttu-id="3f589-121">Wichtig: beim Zuordnen der angegebenen Eigenschaften wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="3f589-121">Important: The ValueSet parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="3f589-122">Siehe folgendes Beispiel zum vorherigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="3f589-122">For example, using the above command.</span></span>

<span data-ttu-id="3f589-123">Dies schlägt fehl:-valueset @ {maxenvelopesizekb = "200"}</span><span class="sxs-lookup"><span data-stu-id="3f589-123">This fails:     -ValueSet @{MaxEnvelopeSizeKB ="200"}</span></span>

<span data-ttu-id="3f589-124">Dies ist erfolgreich:-valueset @ {maxenvelopesizekb = "200"}</span><span class="sxs-lookup"><span data-stu-id="3f589-124">This succeeds:  -ValueSet @{MaxEnvelopeSizekb ="200"}</span></span>

### <span data-ttu-id="3f589-125">Beispiel 3: Deaktivieren eines Listener auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="3f589-125">Example 3: Disable a listener on a remote computer</span></span>

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

<span data-ttu-id="3f589-126">Dieser Befehl deaktiviert den HTTPS-Listener auf dem Remotecomputer SERVER02.</span><span class="sxs-lookup"><span data-stu-id="3f589-126">This command disables the https listener on the remote computer SERVER02.</span></span>

<span data-ttu-id="3f589-127">Wichtig: beim Zuordnen der angegebenen Eigenschaften wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="3f589-127">Important: The ValueSet parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="3f589-128">Siehe folgendes Beispiel zum vorherigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="3f589-128">For example, using the above command.</span></span>

<span data-ttu-id="3f589-129">Dies schlägt fehl:-valueset @ {aktiviert = "false"}</span><span class="sxs-lookup"><span data-stu-id="3f589-129">This fails:     -ValueSet @{enabled="False"}</span></span>

<span data-ttu-id="3f589-130">Dies ist erfolgreich:-valueset @ {aktiviert = "false"}</span><span class="sxs-lookup"><span data-stu-id="3f589-130">This succeeds:  -ValueSet @{Enabled="False"}</span></span>

## <span data-ttu-id="3f589-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3f589-131">PARAMETERS</span></span>

### <span data-ttu-id="3f589-132">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="3f589-132">-ApplicationName</span></span>

<span data-ttu-id="3f589-133">Gibt den Anwendungsnamen in der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="3f589-133">Specifies the application name in the connection.</span></span>
<span data-ttu-id="3f589-134">Der Standardwert des ApplicationName-Parameters lautet „WSMAN“.</span><span class="sxs-lookup"><span data-stu-id="3f589-134">The default value of the ApplicationName parameter is "WSMAN".</span></span>
<span data-ttu-id="3f589-135">Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="3f589-135">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="3f589-136">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="3f589-136">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="3f589-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f589-137">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="3f589-138">Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="3f589-138">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="3f589-139">Die Standardeinstellung „WSMAN“ eignet sich für die meisten Verwendungszwecke.</span><span class="sxs-lookup"><span data-stu-id="3f589-139">This default setting of "WSMAN" is appropriate for most uses.</span></span>
<span data-ttu-id="3f589-140">Dieser Parameter soll verwendet werden, wenn mehrere Computer Remoteverbindungen mit einem Computer herstellen, auf dem Windows PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3f589-140">This parameter is designed to be used when numerous computers establish remote connections to one computer that is running Windows PowerShell.</span></span>
<span data-ttu-id="3f589-141">In diesem Fall wird Web Services for Management (WS-Management) aus Gründen der Effizienz von IIS gehostet.</span><span class="sxs-lookup"><span data-stu-id="3f589-141">In this case, IIS hosts Web Services for Management (WS-Management ) for efficiency.</span></span>

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

### <span data-ttu-id="3f589-142">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="3f589-142">-Authentication</span></span>

<span data-ttu-id="3f589-143">Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3f589-143">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="3f589-144">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="3f589-144">Possible values are:</span></span>

- <span data-ttu-id="3f589-145">Basic: Standard ist ein Schema, in dem der Benutzername und das Kennwort als Klartext an den Server oder Proxy gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f589-145">Basic: Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="3f589-146">Standardwert: Verwenden Sie die vom WS-Management Protokoll implementierte Authentifizierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="3f589-146">Default : Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="3f589-147">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="3f589-147">This is the default.</span></span>
- <span data-ttu-id="3f589-148">Digest: Digest ist ein Challenge-Response-Schema, das eine vom Server angegebene Daten Zeichenfolge für die Abfrage verwendet.</span><span class="sxs-lookup"><span data-stu-id="3f589-148">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="3f589-149">Kerberos: der Client Computer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="3f589-149">Kerberos: The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="3f589-150">Aushandeln: aushandeln ist ein Challenge-Response-Schema, das mit dem Server oder Proxy aushandelt, um das für die Authentifizierung zu verwendende Schema zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="3f589-150">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="3f589-151">Dieser Parameterwert ermöglicht es z. B., die Verwendung des Kerberos-Protokolls oder von NTLM auszuhandeln.</span><span class="sxs-lookup"><span data-stu-id="3f589-151">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="3f589-152">Kredssp: verwendet die Authentifizierung des Credential Security Support Provider (aufwärtssp), die dem Benutzer das Delegieren von Anmelde Informationen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="3f589-152">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="3f589-153">Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.</span><span class="sxs-lookup"><span data-stu-id="3f589-153">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="3f589-154">Vorsicht: die Anmelde Informationen des Benutzers werden vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="3f589-154">Caution: CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="3f589-155">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="3f589-155">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="3f589-156">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f589-156">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="3f589-157">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="3f589-157">-CertificateThumbprint</span></span>

<span data-ttu-id="3f589-158">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="3f589-158">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="3f589-159">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="3f589-159">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="3f589-160">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="3f589-160">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="3f589-161">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="3f589-161">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="3f589-162">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den Befehl Get-Item oder Get-ChildItem im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="3f589-162">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="3f589-163">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="3f589-163">-ComputerName</span></span>

<span data-ttu-id="3f589-164">Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3f589-164">Specifies the computer against which you want to run the management operation.</span></span>
<span data-ttu-id="3f589-165">Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="3f589-165">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="3f589-166">Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3f589-166">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="3f589-167">Der lokale Computer ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="3f589-167">The local computer is the default.</span></span>
<span data-ttu-id="3f589-168">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f589-168">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="3f589-169">Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="3f589-169">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="3f589-170">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="3f589-170">-ConnectionURI</span></span>

<span data-ttu-id="3f589-171">Gibt den Verbindungsendpunkt an.</span><span class="sxs-lookup"><span data-stu-id="3f589-171">Specifies the connection endpoint.</span></span>
<span data-ttu-id="3f589-172">Das Format dieser Zeichenfolge lautet:</span><span class="sxs-lookup"><span data-stu-id="3f589-172">The format of this string is:</span></span>

<span data-ttu-id="3f589-173">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="3f589-173">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="3f589-174">Die folgende Zeichenfolge ist ein ordnungsgemäß formatierter Wert für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="3f589-174">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="3f589-175">Der URI muss voll qualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="3f589-175">The URI must be fully qualified .</span></span>

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

### <span data-ttu-id="3f589-176">-Credential</span><span class="sxs-lookup"><span data-stu-id="3f589-176">-Credential</span></span>

<span data-ttu-id="3f589-177">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="3f589-177">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="3f589-178">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3f589-178">The default is the current user.</span></span>
<span data-ttu-id="3f589-179">Geben Sie einen Benutzernamen ein, z. b. "USER01", "Domain01\User01" oder " User@Domain.com ".</span><span class="sxs-lookup"><span data-stu-id="3f589-179">Type a user name, such as "User01", "Domain01\User01", or "User@Domain.com".</span></span>
<span data-ttu-id="3f589-180">Oder geben Sie ein PSCredential-Objekt ein, z. B. ein vom Get-Credential-Cmdlet zurückgegebenes Objekt.</span><span class="sxs-lookup"><span data-stu-id="3f589-180">Or, enter a PSCredential object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="3f589-181">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="3f589-181">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="3f589-182">-Dialekt</span><span class="sxs-lookup"><span data-stu-id="3f589-182">-Dialect</span></span>

<span data-ttu-id="3f589-183">Gibt den im Filterprädikat zu verwendenden Dialekt an.</span><span class="sxs-lookup"><span data-stu-id="3f589-183">Specifies the dialect to use in the filter predicate.</span></span>
<span data-ttu-id="3f589-184">Dies kann ein beliebiger vom Remotedienst unterstützter Dialekt sein.</span><span class="sxs-lookup"><span data-stu-id="3f589-184">This can be any dialect that is supported by the remote service.</span></span>
<span data-ttu-id="3f589-185">Die folgenden Aliase können für den Dialekt-URI verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="3f589-185">The following aliases can be used for the dialect URI:</span></span>

- <span data-ttu-id="3f589-186">WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span><span class="sxs-lookup"><span data-stu-id="3f589-186">WQL: `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span></span>
- <span data-ttu-id="3f589-187">Ktor `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span><span class="sxs-lookup"><span data-stu-id="3f589-187">Selector: `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span></span>
- <span data-ttu-id="3f589-188">Anwalt `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span><span class="sxs-lookup"><span data-stu-id="3f589-188">Association: `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span></span>

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

### <span data-ttu-id="3f589-189">-FilePath</span><span class="sxs-lookup"><span data-stu-id="3f589-189">-FilePath</span></span>

<span data-ttu-id="3f589-190">Gibt den Pfad einer Datei an, die zum Aktualisieren einer Verwaltungsressource verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f589-190">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="3f589-191">Sie geben die Verwaltungsressource mit dem ResourceURI-Parameter und SelectorSet-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="3f589-191">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter .</span></span>
<span data-ttu-id="3f589-192">Der folgende Befehl verwendet z. B. den FilePath-Parameter:</span><span class="sxs-lookup"><span data-stu-id="3f589-192">For example, the following command uses the FilePath parameter:</span></span>

`Invoke-WSManAction -action StopService -resourceuri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:c:\input.xml -authentication default`

<span data-ttu-id="3f589-193">Dieser Befehl ruft die StopService-Methode für den Spoolerdienst auf und verwendet für die Eingabe eine Datei.</span><span class="sxs-lookup"><span data-stu-id="3f589-193">This command calls the StopService method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="3f589-194">Die Datei „Input.xml“ weist folgenden Inhalt auf:</span><span class="sxs-lookup"><span data-stu-id="3f589-194">The file, Input.xml, contains the following content:</span></span>

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

### <span data-ttu-id="3f589-195">-Fragment</span><span class="sxs-lookup"><span data-stu-id="3f589-195">-Fragment</span></span>

<span data-ttu-id="3f589-196">Gibt einen Abschnitt innerhalb der Instanz an, die aktualisiert oder für den angegebenen Vorgang abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="3f589-196">Specifies a section inside the instance that is to be updated or retrieved for the specified operation.</span></span>
<span data-ttu-id="3f589-197">Um beispielsweise den Status eines Spoolerdiensts abzurufen, geben Sie „-Fragment-Status“ ein.</span><span class="sxs-lookup"><span data-stu-id="3f589-197">For example, to get the status of a spooler service, specify "-Fragment Status".</span></span>

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

### <span data-ttu-id="3f589-198">-OptionSET</span><span class="sxs-lookup"><span data-stu-id="3f589-198">-OptionSet</span></span>

<span data-ttu-id="3f589-199">Übergibt eine Reihe von Schaltern an einen Dienst, um die Art der Anforderung zu ändern oder zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="3f589-199">Passes a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="3f589-200">Diese sind mit Schaltern in Befehlszeilenshells vergleichbar, da sie dienstspezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="3f589-200">These are similar to switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="3f589-201">Es können beliebig viele Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3f589-201">Any number of options can be specified.</span></span>

<span data-ttu-id="3f589-202">Das folgende Beispiel veranschaulicht die Syntax, durch die die Werte 1, 2 und 3 für die Parameter „a“, „b“ und „c“ übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="3f589-202">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

<span data-ttu-id="3f589-203">-OptionSet @{a=1;b=2;c=3}</span><span class="sxs-lookup"><span data-stu-id="3f589-203">-OptionSet @{a=1;b=2;c=3}</span></span>

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

### <span data-ttu-id="3f589-204">-Port</span><span class="sxs-lookup"><span data-stu-id="3f589-204">-Port</span></span>

<span data-ttu-id="3f589-205">Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="3f589-205">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="3f589-206">Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80.</span><span class="sxs-lookup"><span data-stu-id="3f589-206">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="3f589-207">Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.</span><span class="sxs-lookup"><span data-stu-id="3f589-207">When the transport is HTTPS, the default port is 443.</span></span>
<span data-ttu-id="3f589-208">Wenn Sie HTTPS als Transport verwenden, muss der Wert des ComputerName-Parameters mit dem allgemeinen Namen des Serverzertifikats übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="3f589-208">When you use HTTPS as the transport, the value of the ComputerName parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="3f589-209">Wenn der SkipCNCheck-Parameter jedoch als Teil des SessionOption-Parameters angegeben wird, muss der allgemeine Servername im Zertifikat nicht mit dem Hostnamen des Servers übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="3f589-209">However, if the SkipCNCheck parameter is specified as part of the SessionOption parameter, then the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="3f589-210">Der SkipCNCheck-Parameter darf nur für vertrauenswürdige Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f589-210">The SkipCNCheck parameter should be used only for trusted machines.</span></span>

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

### <span data-ttu-id="3f589-211">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="3f589-211">-ResourceURI</span></span>

<span data-ttu-id="3f589-212">Enthält den URI (Uniform Resource Identifier) der Ressourcenklasse oder -instanz.</span><span class="sxs-lookup"><span data-stu-id="3f589-212">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="3f589-213">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="3f589-213">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="3f589-214">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="3f589-214">A URI consists of a prefix and a path to a resource.</span></span>
<span data-ttu-id="3f589-215">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f589-215">For example:</span></span>

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

### <span data-ttu-id="3f589-216">-Selector Set</span><span class="sxs-lookup"><span data-stu-id="3f589-216">-SelectorSet</span></span>

<span data-ttu-id="3f589-217">Gibt eine Reihe von Wertpaaren an, mit denen bestimmte Instanzen von Verwaltungsressourcen ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="3f589-217">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="3f589-218">Der SelectorSet-Parameter wird verwendet, wenn mehr als eine Instanz der Ressource vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3f589-218">The SelectorSet parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="3f589-219">Der Wert des SelectorSet-Parameters muss eine Hashtabelle sein.</span><span class="sxs-lookup"><span data-stu-id="3f589-219">The value of the SelectorSet parameter must be a hash table.</span></span>
<span data-ttu-id="3f589-220">Das folgende Beispiel zeigt, wie Sie einen Wert für diesen Parameter eingeben:</span><span class="sxs-lookup"><span data-stu-id="3f589-220">The following example shows how to enter a value for this parameter:</span></span>

<span data-ttu-id="3f589-221">-SelectorSet @{Name="WinRM";ID="yyy"}</span><span class="sxs-lookup"><span data-stu-id="3f589-221">-SelectorSet @{Name="WinRM";ID="yyy"}</span></span>

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

### <span data-ttu-id="3f589-222">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="3f589-222">-SessionOption</span></span>

<span data-ttu-id="3f589-223">Definiert eine Reihe von erweiterten Optionen für die WS-Management-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="3f589-223">Defines a set of extended options for the WS-Management session.</span></span>
<span data-ttu-id="3f589-224">Geben Sie ein SessionOption-Objekt ein, das Sie mit dem New-WSManSessionOption-Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="3f589-224">Enter a SessionOption object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="3f589-225">Weitere Informationen zu den verfügbaren Optionen finden Sie unter „New-WSManSessionOption“.</span><span class="sxs-lookup"><span data-stu-id="3f589-225">For more information about the options that are available, see New-WSManSessionOption.</span></span>

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

### <span data-ttu-id="3f589-226">-US-</span><span class="sxs-lookup"><span data-stu-id="3f589-226">-UseSSL</span></span>

<span data-ttu-id="3f589-227">Gibt an, dass das SSL (Secure Sockets Layer)-Protokoll verwendet werden soll, um eine Verbindung mit dem Remotecomputer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="3f589-227">Specifies that the Secure Sockets Layer (SSL) protocol should be used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="3f589-228">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="3f589-228">By default, SSL is not used.</span></span>

<span data-ttu-id="3f589-229">WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="3f589-229">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="3f589-230">Mit dem UseSSL-Parameter können Sie anstelle von HTTP das sicherere HTTPS angeben.</span><span class="sxs-lookup"><span data-stu-id="3f589-230">The UseSSL parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="3f589-231">Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, verursacht der Befehl einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="3f589-231">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="3f589-232">-Valueset</span><span class="sxs-lookup"><span data-stu-id="3f589-232">-ValueSet</span></span>

<span data-ttu-id="3f589-233">Gibt eine Hashtabelle an, mit deren Hilfe eine Verwaltungsressource geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3f589-233">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="3f589-234">Sie geben die Verwaltungs Ressource mit dem resourceUri-Parameter und dem selectorset-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="3f589-234">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter.</span></span>
<span data-ttu-id="3f589-235">Der Wert des ValueSet-Parameters muss eine Hashtabelle sein.</span><span class="sxs-lookup"><span data-stu-id="3f589-235">The value of the ValueSet parameter must be a hash table.</span></span>

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

### <span data-ttu-id="3f589-236">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3f589-236">CommonParameters</span></span>

<span data-ttu-id="3f589-237">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3f589-237">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3f589-238">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="3f589-238">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="3f589-239">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3f589-239">INPUTS</span></span>

### <span data-ttu-id="3f589-240">Keine</span><span class="sxs-lookup"><span data-stu-id="3f589-240">None</span></span>

<span data-ttu-id="3f589-241">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="3f589-241">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="3f589-242">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3f589-242">OUTPUTS</span></span>

### <span data-ttu-id="3f589-243">Keine</span><span class="sxs-lookup"><span data-stu-id="3f589-243">None</span></span>

<span data-ttu-id="3f589-244">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="3f589-244">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3f589-245">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3f589-245">NOTES</span></span>

## <span data-ttu-id="3f589-246">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3f589-246">RELATED LINKS</span></span>

[<span data-ttu-id="3f589-247">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="3f589-247">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="3f589-248">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="3f589-248">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="3f589-249">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="3f589-249">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="3f589-250">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="3f589-250">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="3f589-251">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="3f589-251">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="3f589-252">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3f589-252">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="3f589-253">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="3f589-253">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="3f589-254">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3f589-254">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="3f589-255">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="3f589-255">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="3f589-256">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3f589-256">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="3f589-257">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="3f589-257">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="3f589-258">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="3f589-258">Test-WSMan</span></span>](Test-WSMan.md)

