---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 03/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmaninstance?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManInstance
ms.openlocfilehash: f072bf946bc3114db0b6503157880cbe0fb6d6c3
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218359"
---
# <span data-ttu-id="d88b8-103">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d88b8-103">New-WSManInstance</span></span>

## <span data-ttu-id="d88b8-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d88b8-104">SYNOPSIS</span></span>
<span data-ttu-id="d88b8-105">Erstellt eine neue Instanz einer Verwaltungsressource.</span><span class="sxs-lookup"><span data-stu-id="d88b8-105">Creates a new instance of a management resource.</span></span>

## <span data-ttu-id="d88b8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d88b8-106">SYNTAX</span></span>

### <span data-ttu-id="d88b8-107">Computername (Standard)</span><span class="sxs-lookup"><span data-stu-id="d88b8-107">ComputerName (Default)</span></span>

```
New-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable>
 [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="d88b8-108">URI</span><span class="sxs-lookup"><span data-stu-id="d88b8-108">URI</span></span>

```
New-WSManInstance [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="d88b8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d88b8-109">DESCRIPTION</span></span>

<span data-ttu-id="d88b8-110">Das- `New-WSManInstance` Cmdlet erstellt eine neue Instanz einer Verwaltungs Ressource.</span><span class="sxs-lookup"><span data-stu-id="d88b8-110">The `New-WSManInstance` cmdlet creates a new instance of a management resource.</span></span> <span data-ttu-id="d88b8-111">Es verwendet einen Ressourcen-URI und einen Wertsatz oder eine Eingabedatei zum Erstellen der neuen Instanz der Verwaltungsressource.</span><span class="sxs-lookup"><span data-stu-id="d88b8-111">It uses a resource URI and a value set or input file to create the new instance of the management resource.</span></span>

<span data-ttu-id="d88b8-112">Das Cmdlet verwendet die Verbindungs-/Transportschicht von WinRM, um die Instanz der Verwaltungsressource zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d88b8-112">This cmdlet uses the WinRM connection/transport layer to create the management resource instance.</span></span>

## <span data-ttu-id="d88b8-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d88b8-113">EXAMPLES</span></span>

### <span data-ttu-id="d88b8-114">Beispiel 1: Erstellen eines HTTPS-Listener</span><span class="sxs-lookup"><span data-stu-id="d88b8-114">Example 1: Create a HTTPS listener</span></span>

<span data-ttu-id="d88b8-115">Dieser Befehl erstellt eine Instanz eines WS-Management-HTTPS-Listeners für alle IP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="d88b8-115">This command creates an instance of a WS-Management HTTPS listener on all IP addresses.</span></span>

```powershell
New-WSManInstance winrm/config/Listener -SelectorSet @{Transport='HTTPS'; Address='*'} -ValueSet @{Hostname="HOST";CertificateThumbprint="XXXXXXXXXX"}
```

## <span data-ttu-id="d88b8-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d88b8-116">PARAMETERS</span></span>

### <span data-ttu-id="d88b8-117">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="d88b8-117">-ApplicationName</span></span>

<span data-ttu-id="d88b8-118">Gibt den Anwendungsnamen in der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="d88b8-118">Specifies the application name in the connection.</span></span> <span data-ttu-id="d88b8-119">Der Standardwert des **ApplicationName** -Parameters lautet " **WSMAN** ".</span><span class="sxs-lookup"><span data-stu-id="d88b8-119">The default value of the **ApplicationName** parameter is **WSMAN**.</span></span> <span data-ttu-id="d88b8-120">Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="d88b8-120">The complete identifier for the remote endpoint is in the following format:</span></span>

`<transport>://<server>:<port>/<ApplicationName>`

<span data-ttu-id="d88b8-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d88b8-121">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="d88b8-122">Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="d88b8-122">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span> <span data-ttu-id="d88b8-123">Diese Standardeinstellung von **WSMAN** eignet sich für die meisten Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="d88b8-123">This default setting of **WSMAN** is appropriate for most uses.</span></span> <span data-ttu-id="d88b8-124">Dieser Parameter soll verwendet werden, wenn mehrere Computer Remoteverbindungen mit einem Computer herstellen, auf dem Windows PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d88b8-124">This parameter is designed to be used when numerous computers establish remote connections to one computer that is running Windows PowerShell.</span></span> <span data-ttu-id="d88b8-125">In diesem Fall wird Web Services for Management (WS-Management) aus Gründen der Effizienz von IIS gehostet.</span><span class="sxs-lookup"><span data-stu-id="d88b8-125">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="d88b8-126">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d88b8-126">-Authentication</span></span>

<span data-ttu-id="d88b8-127">Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d88b8-127">Specifies the authentication mechanism to be used at the server.</span></span> <span data-ttu-id="d88b8-128">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="d88b8-128">Possible values are:</span></span>

- <span data-ttu-id="d88b8-129">Basic: Standard ist ein Schema, in dem der Benutzername und das Kennwort als Klartext an den Server oder Proxy gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d88b8-129">Basic: Basic is a scheme in which the username and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="d88b8-130">Standardwert: Verwenden Sie die vom WS-Management Protokoll implementierte Authentifizierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="d88b8-130">Default: Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="d88b8-131">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="d88b8-131">This is the default.</span></span>
- <span data-ttu-id="d88b8-132">Digest: Digest ist ein Challenge-Response-Schema, das eine vom Server angegebene Daten Zeichenfolge für die Abfrage verwendet.</span><span class="sxs-lookup"><span data-stu-id="d88b8-132">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="d88b8-133">Kerberos: der Client Computer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="d88b8-133">Kerberos: The client computer and the server mutually authenticate using Kerberos certificates.</span></span>
- <span data-ttu-id="d88b8-134">Aushandeln: aushandeln ist ein Challenge-Response-Schema, das mit dem Server oder Proxy aushandelt, um das für die Authentifizierung zu verwendende Schema zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="d88b8-134">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="d88b8-135">Dieser Parameterwert ermöglicht es z. B., die Verwendung des Kerberos-Protokolls oder von NTLM auszuhandeln.</span><span class="sxs-lookup"><span data-stu-id="d88b8-135">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="d88b8-136">Kredssp: verwendet die Authentifizierung des Credential Security Support Provider (aufwärtssp), die dem Benutzer das Delegieren von Anmelde Informationen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="d88b8-136">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="d88b8-137">Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.</span><span class="sxs-lookup"><span data-stu-id="d88b8-137">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

> [!CAUTION]
> <span data-ttu-id="d88b8-138">Bei „CredSSP“ werden die Anmeldeinformationen des Benutzers vom lokalen Computer an einen Remotecomputer delegiert.</span><span class="sxs-lookup"><span data-stu-id="d88b8-138">CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span> <span data-ttu-id="d88b8-139">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="d88b8-139">This practice increases the security risk of the remote operation.</span></span> <span data-ttu-id="d88b8-140">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d88b8-140">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="d88b8-141">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="d88b8-141">-CertificateThumbprint</span></span>

<span data-ttu-id="d88b8-142">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="d88b8-142">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="d88b8-143">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="d88b8-143">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="d88b8-144">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d88b8-144">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="d88b8-145">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="d88b8-145">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="d88b8-146">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den- `Get-Item` Befehl oder den- `Get-ChildItem` Befehl im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="d88b8-146">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="d88b8-147">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d88b8-147">-ComputerName</span></span>

<span data-ttu-id="d88b8-148">Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d88b8-148">Specifies the computer against which you want to run the management operation.</span></span> <span data-ttu-id="d88b8-149">Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="d88b8-149">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="d88b8-150">Verwenden Sie den lokalen Computernamen, verwenden Sie localhost, oder verwenden Sie einen Punkt ( `.` ), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d88b8-150">Use the local computer name, use localhost, or use a dot (`.`) to specify the local computer.</span></span> <span data-ttu-id="d88b8-151">Der lokale Computer ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="d88b8-151">The local computer is the default.</span></span> <span data-ttu-id="d88b8-152">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d88b8-152">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span> <span data-ttu-id="d88b8-153">Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="d88b8-153">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="d88b8-154">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="d88b8-154">-ConnectionURI</span></span>

<span data-ttu-id="d88b8-155">Gibt den Verbindungsendpunkt an.</span><span class="sxs-lookup"><span data-stu-id="d88b8-155">Specifies the connection endpoint.</span></span>
<span data-ttu-id="d88b8-156">Das Format dieser Zeichenfolge lautet:</span><span class="sxs-lookup"><span data-stu-id="d88b8-156">The format of this string is:</span></span>

`<Transport>://<Server>:<Port>/<ApplicationName>`

<span data-ttu-id="d88b8-157">Die folgende Zeichenfolge ist ein ordnungsgemäß formatierter Wert für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="d88b8-157">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="d88b8-158">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="d88b8-158">The URI must be fully qualified.</span></span>

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases: CURI, CU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d88b8-159">-Credential</span><span class="sxs-lookup"><span data-stu-id="d88b8-159">-Credential</span></span>

<span data-ttu-id="d88b8-160">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="d88b8-160">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="d88b8-161">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d88b8-161">The default is the current user.</span></span> <span data-ttu-id="d88b8-162">Geben Sie einen Benutzernamen ein, z. b. "USER01", "Domain01\User01" oder " User@Domain.com ".</span><span class="sxs-lookup"><span data-stu-id="d88b8-162">Type a user name, such as "User01", "Domain01\User01", or "User@Domain.com".</span></span> <span data-ttu-id="d88b8-163">Oder geben Sie ein PSCredential-Objekt ein, z. b. ein vom Cmdlet zurück gegebenes Objekt `Get-Credential` .</span><span class="sxs-lookup"><span data-stu-id="d88b8-163">Or, enter a PSCredential object, such as one returned by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="d88b8-164">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d88b8-164">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="d88b8-165">-FilePath</span><span class="sxs-lookup"><span data-stu-id="d88b8-165">-FilePath</span></span>

<span data-ttu-id="d88b8-166">Gibt den Pfad einer Datei an, die zum Erstellen einer Verwaltungsressource verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d88b8-166">Specifies the path of a file that is used to create a management resource.</span></span> <span data-ttu-id="d88b8-167">Sie geben die Verwaltungs Ressource mit dem **resourceUri** -Parameter und dem **selectorset** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="d88b8-167">You specify the management resource using the **ResourceURI** parameter and the **SelectorSet** parameter .</span></span> <span data-ttu-id="d88b8-168">Der folgende Befehl verwendet z. b. den **File** -Parameter:</span><span class="sxs-lookup"><span data-stu-id="d88b8-168">For example, the following command uses the **File** parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmi/cimv2/Win32_Service -SelectorSet @{Name="spooler"} -File c:\input.xml -Authentication Default`

<span data-ttu-id="d88b8-169">Dieser Befehl ruft die **Stop Service** -Methode für den Spoolerdienst mithilfe von Eingaben aus einer Datei auf.</span><span class="sxs-lookup"><span data-stu-id="d88b8-169">This command calls the **StopService** method on the Spooler service using input from a file.</span></span> <span data-ttu-id="d88b8-170">Die Datei `Input.xml` enthält den folgenden Inhalt:</span><span class="sxs-lookup"><span data-stu-id="d88b8-170">The file, `Input.xml`, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d88b8-171">-OptionSET</span><span class="sxs-lookup"><span data-stu-id="d88b8-171">-OptionSet</span></span>

<span data-ttu-id="d88b8-172">Übergibt eine Reihe von Schaltern an einen Dienst, um die Art der Anforderung zu ändern oder zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="d88b8-172">Passes a set of switches to a service to modify or refine the nature of the request.</span></span> <span data-ttu-id="d88b8-173">Diese sind mit Schaltern in Befehlszeilenshells vergleichbar, da sie dienstspezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="d88b8-173">These are similar to switches used in command-line shells because they are service specific.</span></span> <span data-ttu-id="d88b8-174">Es können beliebig viele Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d88b8-174">Any number of options can be specified.</span></span>

<span data-ttu-id="d88b8-175">Das folgende Beispiel veranschaulicht die Syntax, durch die die Werte 1, 2 und 3 für die Parameter „a“, „b“ und „c“ übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="d88b8-175">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="d88b8-176">-Port</span><span class="sxs-lookup"><span data-stu-id="d88b8-176">-Port</span></span>

<span data-ttu-id="d88b8-177">Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="d88b8-177">Specifies the port to use when the client connects to the WinRM service.</span></span> <span data-ttu-id="d88b8-178">Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80.</span><span class="sxs-lookup"><span data-stu-id="d88b8-178">When the transport is HTTP, the default port is 80.</span></span> <span data-ttu-id="d88b8-179">Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.</span><span class="sxs-lookup"><span data-stu-id="d88b8-179">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="d88b8-180">Wenn Sie HTTPS als Transport verwenden, muss der Wert des **Computername** -Parameters mit dem allgemeinen Namen des Serverzertifikats (CN) identisch sein.</span><span class="sxs-lookup"><span data-stu-id="d88b8-180">When you use HTTPS as the transport, the value of the **ComputerName** parameter must match the server's certificate common name (CN).</span></span> <span data-ttu-id="d88b8-181">Wenn der **skipcncheck** -Parameter jedoch als Teil des **sessionoption** -Parameters angegeben wird, muss der allgemeine Name des Zertifikats für den Server nicht mit dem Hostnamen des Servers identisch sein.</span><span class="sxs-lookup"><span data-stu-id="d88b8-181">However, if the **SkipCNCheck** parameter is specified as part of the **SessionOption** parameter, the certificate common name of the server does not have to match the host name of the server.</span></span> <span data-ttu-id="d88b8-182">Der **skipcncheck** -Parameter sollte nur für vertrauenswürdige Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d88b8-182">The **SkipCNCheck** parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="d88b8-183">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="d88b8-183">-ResourceURI</span></span>

<span data-ttu-id="d88b8-184">Enthält den URI (Uniform Resource Identifier) der Ressourcenklasse oder -instanz.</span><span class="sxs-lookup"><span data-stu-id="d88b8-184">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="d88b8-185">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="d88b8-185">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="d88b8-186">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="d88b8-186">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="d88b8-187">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d88b8-187">For example:</span></span>

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

### <span data-ttu-id="d88b8-188">-Selector Set</span><span class="sxs-lookup"><span data-stu-id="d88b8-188">-SelectorSet</span></span>

<span data-ttu-id="d88b8-189">Gibt eine Reihe von Wertpaaren an, mit denen bestimmte Instanzen von Verwaltungsressourcen ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="d88b8-189">Specifies a set of value pairs that are used to select particular management resource instances.</span></span> <span data-ttu-id="d88b8-190">Der **selectorset** -Parameter wird verwendet, wenn mehr als eine Instanz der Ressource vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d88b8-190">The **SelectorSet** parameter is used when more than one instance of the resource exists.</span></span> <span data-ttu-id="d88b8-191">Der Wert des **selectorset** -Parameters muss eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="d88b8-191">The value of the **SelectorSet** parameter must be a hash table.</span></span>

<span data-ttu-id="d88b8-192">Das folgende Beispiel zeigt, wie Sie einen Wert für diesen Parameter eingeben:</span><span class="sxs-lookup"><span data-stu-id="d88b8-192">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d88b8-193">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="d88b8-193">-SessionOption</span></span>

<span data-ttu-id="d88b8-194">Definiert eine Reihe von erweiterten Optionen für die WS-Management-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d88b8-194">Defines a set of extended options for the WS-Management session.</span></span> <span data-ttu-id="d88b8-195">Geben Sie ein **sessionoption** -Objekt ein, das Sie mit dem `New-WSManSessionOption` Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="d88b8-195">Enter a **SessionOption** object that you create using the `New-WSManSessionOption` cmdlet.</span></span> <span data-ttu-id="d88b8-196">Weitere Informationen zu den verfügbaren Optionen finden Sie unter `New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="d88b8-196">For more information about the options that are available, see `New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="d88b8-197">-US-</span><span class="sxs-lookup"><span data-stu-id="d88b8-197">-UseSSL</span></span>

<span data-ttu-id="d88b8-198">Gibt an, dass das SSL (Secure Sockets Layer)-Protokoll verwendet werden soll, um eine Verbindung mit dem Remotecomputer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d88b8-198">Specifies that the Secure Sockets Layer (SSL) protocol should be used to establish a connection to the remote computer.</span></span> <span data-ttu-id="d88b8-199">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d88b8-199">By default, SSL is not used.</span></span>

<span data-ttu-id="d88b8-200">WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="d88b8-200">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span> <span data-ttu-id="d88b8-201">Mit **dem Parameter "** Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.</span><span class="sxs-lookup"><span data-stu-id="d88b8-201">The **UseSSL** parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="d88b8-202">Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, verursacht der Befehl einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="d88b8-202">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="d88b8-203">-Valueset</span><span class="sxs-lookup"><span data-stu-id="d88b8-203">-ValueSet</span></span>

<span data-ttu-id="d88b8-204">Gibt eine Hashtabelle an, mit deren Hilfe eine Verwaltungsressource geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d88b8-204">Specifies a hash table that helps modify a management resource.</span></span> <span data-ttu-id="d88b8-205">Sie geben die Verwaltungs Ressource mit dem **resourceUri** -Parameter und dem **selectorset** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="d88b8-205">You specify the management resource using the **ResourceURI** parameter and the **SelectorSet** parameter.</span></span> <span data-ttu-id="d88b8-206">Der Wert des **valueset** -Parameters muss eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="d88b8-206">The value of the **ValueSet** parameter must be a hash table.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d88b8-207">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d88b8-207">CommonParameters</span></span>

<span data-ttu-id="d88b8-208">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d88b8-208">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d88b8-209">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d88b8-209">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d88b8-210">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d88b8-210">INPUTS</span></span>

### <span data-ttu-id="d88b8-211">Keine</span><span class="sxs-lookup"><span data-stu-id="d88b8-211">None</span></span>

<span data-ttu-id="d88b8-212">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="d88b8-212">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="d88b8-213">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d88b8-213">OUTPUTS</span></span>

### <span data-ttu-id="d88b8-214">Keine</span><span class="sxs-lookup"><span data-stu-id="d88b8-214">None</span></span>

<span data-ttu-id="d88b8-215">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d88b8-215">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d88b8-216">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d88b8-216">NOTES</span></span>

<span data-ttu-id="d88b8-217">Das `Set-WmiInstance` Cmdlet, ein Windows-Verwaltungsinstrumentation (WMI)-Cmdlet, ist ähnlich.</span><span class="sxs-lookup"><span data-stu-id="d88b8-217">The `Set-WmiInstance` cmdlet, a Windows Management Instrumentation (WMI) cmdlet, is similar.</span></span>
<span data-ttu-id="d88b8-218">`Set-WmiInstance` verwendet die Verbindungs-/Transportschicht von DCOM zum Erstellen oder Aktualisieren von WMI-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="d88b8-218">`Set-WmiInstance` uses the DCOM connection/transport layer to create or update WMI instances.</span></span>

## <span data-ttu-id="d88b8-219">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d88b8-219">RELATED LINKS</span></span>

[<span data-ttu-id="d88b8-220">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="d88b8-220">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="d88b8-221">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="d88b8-221">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="d88b8-222">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="d88b8-222">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="d88b8-223">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="d88b8-223">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="d88b8-224">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="d88b8-224">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="d88b8-225">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d88b8-225">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="d88b8-226">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="d88b8-226">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="d88b8-227">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="d88b8-227">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="d88b8-228">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d88b8-228">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="d88b8-229">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d88b8-229">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="d88b8-230">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="d88b8-230">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="d88b8-231">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="d88b8-231">Test-WSMan</span></span>](Test-WSMan.md)
