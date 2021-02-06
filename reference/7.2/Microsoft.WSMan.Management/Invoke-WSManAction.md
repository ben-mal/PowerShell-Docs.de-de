---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/invoke-wsmanaction?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WSManAction
ms.openlocfilehash: e2456e1da866929d60c36cc0e09990399b41614b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596755"
---
# <span data-ttu-id="7400b-102">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="7400b-102">Invoke-WSManAction</span></span>

## <span data-ttu-id="7400b-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7400b-103">SYNOPSIS</span></span>
<span data-ttu-id="7400b-104">Ruft eine Aktion für das Objekt auf, das durch den Ressourcen-URI und die Selektoren angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="7400b-104">Invokes an action on the object that is specified by the Resource URI and by the selectors.</span></span>

## <span data-ttu-id="7400b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7400b-105">SYNTAX</span></span>

### <span data-ttu-id="7400b-106">URI (Standard)</span><span class="sxs-lookup"><span data-stu-id="7400b-106">URI (Default)</span></span>

```
Invoke-WSManAction [-Action] <String> [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>]
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-ValueSet <Hashtable>] [-ResourceURI] <Uri>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="7400b-107">Computername</span><span class="sxs-lookup"><span data-stu-id="7400b-107">ComputerName</span></span>

```
Invoke-WSManAction [-Action] <String> [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-UseSSL] [-ValueSet <Hashtable>] [-ResourceURI] <Uri> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="7400b-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7400b-108">DESCRIPTION</span></span>
<span data-ttu-id="7400b-109">Die **Aufruf-wsmanaction** führt eine Aktion für das Objekt aus, das durch RESOURCE_URI angegeben wird, wobei Parameter durch Schlüssel-Wert-Paare angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7400b-109">The **Invoke-WSManAction** runs an action on the object that is specified by RESOURCE_URI, where parameters are specified by key value pairs.</span></span>

<span data-ttu-id="7400b-110">Das Cmdlet verwendet die Verbindungs-/Transportschicht von WSMan zum Ausführen der Aktion.</span><span class="sxs-lookup"><span data-stu-id="7400b-110">This cmdlet uses the WSMan connection/transport layer to run the action.</span></span>

## <span data-ttu-id="7400b-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7400b-111">EXAMPLES</span></span>

### <span data-ttu-id="7400b-112">Beispiel 1: Aufrufen einer Methode</span><span class="sxs-lookup"><span data-stu-id="7400b-112">Example 1: Invoke a method</span></span>

```powershell
Invoke-WSManAction -Action startservice -ResourceURI wmicimv2/win32_service  -SelectorSet @{name="spooler"} -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="7400b-113">Dieser Befehl ruft die **Start Service** -Methode der Win32_Service WMI-Klasseninstanz auf, die dem Spoolerdienst entspricht.</span><span class="sxs-lookup"><span data-stu-id="7400b-113">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>

<span data-ttu-id="7400b-114">Der Rückgabewert gibt an, ob die Aktion erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="7400b-114">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="7400b-115">In diesem Fall deutet der Rückgabewert 0 auf eine erfolgreiche Aktion hin.</span><span class="sxs-lookup"><span data-stu-id="7400b-115">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="7400b-116">Der Rückgabewert 5 gibt an, dass der Dienst bereits gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="7400b-116">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="7400b-117">Beispiel 2: Aufrufen einer Methode</span><span class="sxs-lookup"><span data-stu-id="7400b-117">Example 2: Invoke a method</span></span>

```powershell
Invoke-WSManAction -Action stopservice -ResourceURI wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:input.xml -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="7400b-118">Mit diesem Befehl wird die **Stop Service** -Methode für den Spoolerdienst aufgerufen, indem Eingaben aus einer Datei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7400b-118">This command calls the **StopService** method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="7400b-119">Die Datei „Input.xml“ weist folgenden Inhalt auf:</span><span class="sxs-lookup"><span data-stu-id="7400b-119">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

### <span data-ttu-id="7400b-120">Beispiel 3: Aufrufen einer Methode mit angegebenen Parameterwerten</span><span class="sxs-lookup"><span data-stu-id="7400b-120">Example 3: Invoke a method with specified parameter values</span></span>

```powershell
Invoke-WSManAction -Action create -ResourceURI wmicimv2/win32_process -ValueSet @{commandline="notepad.exe";currentdirectory="C:\"}
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Process
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ProcessId   : 6356
ReturnValue : 0
```

<span data-ttu-id="7400b-121">Dieser Befehl ruft die **Create** -Methode der Win32_Process-Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="7400b-121">This command calls the **Create** method of the Win32_Process class.</span></span>
<span data-ttu-id="7400b-122">Die Methode übergibt die beiden Parameterwerte Notepad.exe und c:\.</span><span class="sxs-lookup"><span data-stu-id="7400b-122">It passes the method two parameter values, Notepad.exe and C:\.</span></span>
<span data-ttu-id="7400b-123">Folglich wird ein neuer Prozess erstellt, um Notepad auszuführen, und das aktuelle Verzeichnis des neuen Prozesses wird auf c:\fest gelegt.</span><span class="sxs-lookup"><span data-stu-id="7400b-123">As a result, a new process is created to run Notepad, and the current directory of the new process is set to C:\.</span></span>

### <span data-ttu-id="7400b-124">Beispiel 4: Aufrufen einer Methode auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="7400b-124">Example 4: Invoke a method on a remote computer</span></span>

```powershell
Invoke-WSManAction -Action startservice -ResourceURI wmicimv2/win32_service  -SelectorSet @{name="spooler"} -ComputerName server01 -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="7400b-125">Dieser Befehl ruft die **Start Service** -Methode der Win32_Service WMI-Klasseninstanz auf, die dem Spoolerdienst entspricht.</span><span class="sxs-lookup"><span data-stu-id="7400b-125">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>
<span data-ttu-id="7400b-126">Da der *Computername* -Parameter angegeben wird, wird der Befehl auf dem Remote Computer Server01 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7400b-126">Because the *ComputerName* parameter is specified, the command runs against the remote server01 computer.</span></span>

## <span data-ttu-id="7400b-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7400b-127">PARAMETERS</span></span>

### <span data-ttu-id="7400b-128">-Action</span><span class="sxs-lookup"><span data-stu-id="7400b-128">-Action</span></span>
<span data-ttu-id="7400b-129">Gibt die Methode an, die für das von resourceUri und Selektoren angegebene Verwaltungs Objekt ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7400b-129">Specifies the method to run on the management object specified by the ResourceURI and selectors.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7400b-130">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="7400b-130">-ApplicationName</span></span>
<span data-ttu-id="7400b-131">Gibt den Anwendungsnamen in der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="7400b-131">Specifies the application name in the connection.</span></span>
<span data-ttu-id="7400b-132">Der Standardwert des *ApplicationName* -Parameters lautet "wsman".</span><span class="sxs-lookup"><span data-stu-id="7400b-132">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="7400b-133">Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="7400b-133">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="7400b-134">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="7400b-134">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="7400b-135">Beispiel: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="7400b-135">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="7400b-136">Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="7400b-136">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="7400b-137">Diese Standardeinstellung von WSMAN eignet sich für die meisten Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="7400b-137">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="7400b-138">Dieser Parameter ist für die Verwendung bestimmt, wenn viele Computer Remote Verbindungen mit einem Computer herstellen, auf dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7400b-138">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="7400b-139">In diesem Fall wird Web Services for Management (WS-Management) aus Gründen der Effizienz von IIS gehostet.</span><span class="sxs-lookup"><span data-stu-id="7400b-139">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="7400b-140">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7400b-140">-Authentication</span></span>
<span data-ttu-id="7400b-141">Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7400b-141">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="7400b-142">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="7400b-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7400b-143">Standard.</span><span class="sxs-lookup"><span data-stu-id="7400b-143">Basic.</span></span>
<span data-ttu-id="7400b-144">„Basic“ ist ein Schema, bei dem der Benutzername und das Kennwort im Klartext an den Server oder Proxy gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="7400b-144">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="7400b-145">Standard.</span><span class="sxs-lookup"><span data-stu-id="7400b-145">Default.</span></span>
<span data-ttu-id="7400b-146">Verwendet die vom WS-Verwaltungsprotokoll implementierte Authentifizierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="7400b-146">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="7400b-147">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="7400b-147">This is the default.</span></span>
- <span data-ttu-id="7400b-148">Digest.</span><span class="sxs-lookup"><span data-stu-id="7400b-148">Digest.</span></span>
<span data-ttu-id="7400b-149">„Digest“ ist ein Abfrage/Rückmeldung-Schema, bei dem eine vom Server angegebene Datenzeichenfolge für die Abfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7400b-149">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="7400b-150">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7400b-150">Kerberos.</span></span>
<span data-ttu-id="7400b-151">Der Clientcomputer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="7400b-151">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="7400b-152">Negotiate</span><span class="sxs-lookup"><span data-stu-id="7400b-152">Negotiate.</span></span>
<span data-ttu-id="7400b-153">„Negotiate“ ist ein Abfrage/Rückmeldung-Schema, bei dem das für die Authentifizierung zu verwendende Schema mit dem Server oder Proxy ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="7400b-153">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="7400b-154">Dieser Parameterwert ermöglicht beispielsweise die Aushandlung, um zu bestimmen, ob das Kerberos-Protokoll oder NTLM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7400b-154">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="7400b-155">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="7400b-155">CredSSP.</span></span>
<span data-ttu-id="7400b-156">Verwenden Sie die Authentifizierung der Credential Security Support Provider (kredssp), mit der der Benutzer Anmelde Informationen delegieren kann.</span><span class="sxs-lookup"><span data-stu-id="7400b-156">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="7400b-157">Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.</span><span class="sxs-lookup"><span data-stu-id="7400b-157">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="7400b-158">Vorsicht: die Anmelde Informationen des Benutzers werden vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="7400b-158">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="7400b-159">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="7400b-159">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="7400b-160">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7400b-160">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="7400b-161">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="7400b-161">-CertificateThumbprint</span></span>
<span data-ttu-id="7400b-162">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="7400b-162">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="7400b-163">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="7400b-163">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="7400b-164">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7400b-164">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="7400b-165">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="7400b-165">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="7400b-166">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den Befehl Get-Item oder Get-ChildItem im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="7400b-166">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="7400b-167">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="7400b-167">-ComputerName</span></span>
<span data-ttu-id="7400b-168">Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7400b-168">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="7400b-169">Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="7400b-169">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="7400b-170">Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7400b-170">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="7400b-171">Der lokale Computer ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="7400b-171">The local computer is the default.</span></span>
<span data-ttu-id="7400b-172">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7400b-172">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="7400b-173">Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="7400b-173">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="7400b-174">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="7400b-174">-ConnectionURI</span></span>
<span data-ttu-id="7400b-175">Gibt den Verbindungsendpunkt an.</span><span class="sxs-lookup"><span data-stu-id="7400b-175">Specifies the connection endpoint.</span></span>
<span data-ttu-id="7400b-176">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7400b-176">The format of this string is as follows:</span></span>

<span data-ttu-id="7400b-177">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="7400b-177">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="7400b-178">Die folgende Zeichenfolge ist ein ordnungsgemäß formatierter Wert für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="7400b-178">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="7400b-179">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="7400b-179">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="7400b-180">-Credential</span><span class="sxs-lookup"><span data-stu-id="7400b-180">-Credential</span></span>
<span data-ttu-id="7400b-181">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="7400b-181">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="7400b-182">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7400b-182">The default is the current user.</span></span>
<span data-ttu-id="7400b-183">Geben Sie einen Benutzernamen ein, z. b. USER01, Domain01\User01 oder User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="7400b-183">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="7400b-184">Oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom Get-Credential-Cmdlet zurück gegebenes Objekt.</span><span class="sxs-lookup"><span data-stu-id="7400b-184">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="7400b-185">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7400b-185">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="7400b-186">-FilePath</span><span class="sxs-lookup"><span data-stu-id="7400b-186">-FilePath</span></span>
<span data-ttu-id="7400b-187">Gibt den Pfad einer Datei an, die zum Aktualisieren einer Verwaltungsressource verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7400b-187">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="7400b-188">Sie geben die Verwaltungs Ressource mit dem *resourceUri* -Parameter und dem *selectorset* -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="7400b-188">You specify the management resource by using the *ResourceURI* parameter and the *SelectorSet* parameter.</span></span>
<span data-ttu-id="7400b-189">Der folgende Befehl verwendet z. b. den *FilePath* -Parameter:</span><span class="sxs-lookup"><span data-stu-id="7400b-189">For example, the following command uses the *FilePath* parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath c:\input.xml -Authentication default`

<span data-ttu-id="7400b-190">Mit diesem Befehl wird die **Stop Service** -Methode für den **Spoolerdienst** aufgerufen, indem Eingaben aus einer Datei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7400b-190">This command calls the **StopService** method on the **Spooler** service by using input from a file.</span></span>
<span data-ttu-id="7400b-191">Die Datei „Input.xml“ weist folgenden Inhalt auf:</span><span class="sxs-lookup"><span data-stu-id="7400b-191">The file, Input.xml, contains the following content:</span></span>

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

### <span data-ttu-id="7400b-192">-OptionSET</span><span class="sxs-lookup"><span data-stu-id="7400b-192">-OptionSet</span></span>
<span data-ttu-id="7400b-193">Gibt eine Reihe von Schaltern für einen Dienst an, um die Art der Anforderung zu ändern oder zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="7400b-193">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="7400b-194">Diese ähneln Switches, die in Befehlszeilenshells verwendet werden, da Sie Dienst spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="7400b-194">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="7400b-195">Es können beliebig viele Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7400b-195">Any number of options can be specified.</span></span>

<span data-ttu-id="7400b-196">Das folgende Beispiel veranschaulicht die Syntax, durch die die Werte 1, 2 und 3 für die Parameter „a“, „b“ und „c“ übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="7400b-196">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7400b-197">-Port</span><span class="sxs-lookup"><span data-stu-id="7400b-197">-Port</span></span>
<span data-ttu-id="7400b-198">Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="7400b-198">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="7400b-199">Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80.</span><span class="sxs-lookup"><span data-stu-id="7400b-199">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="7400b-200">Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.</span><span class="sxs-lookup"><span data-stu-id="7400b-200">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="7400b-201">Wenn Sie HTTPS als Transport verwenden, muss der Wert des *Computername* -Parameters mit dem allgemeinen Namen des Serverzertifikats (CN) identisch sein.</span><span class="sxs-lookup"><span data-stu-id="7400b-201">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="7400b-202">Wenn der *skipcncheck* -Parameter jedoch als Teil des *sessionoption* -Parameters angegeben wird, muss der allgemeine Name des Zertifikats für den Server nicht mit dem Hostnamen des Servers identisch sein.</span><span class="sxs-lookup"><span data-stu-id="7400b-202">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="7400b-203">Der *skipcncheck* -Parameter sollte nur für vertrauenswürdige Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7400b-203">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="7400b-204">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="7400b-204">-ResourceURI</span></span>
<span data-ttu-id="7400b-205">Gibt den URI der Ressourcen Klasse oder-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="7400b-205">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="7400b-206">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="7400b-206">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="7400b-207">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="7400b-207">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="7400b-208">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7400b-208">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ruri

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7400b-209">-Selector Set</span><span class="sxs-lookup"><span data-stu-id="7400b-209">-SelectorSet</span></span>
<span data-ttu-id="7400b-210">Gibt eine Reihe von Wertpaaren an, mit denen bestimmte Instanzen von Verwaltungsressourcen ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="7400b-210">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="7400b-211">*Selector Set* wird verwendet, wenn mehr als eine Instanz der Ressource vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7400b-211">*SelectorSet* is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="7400b-212">Der Wert von *Selector Set* muss eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="7400b-212">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="7400b-213">Das folgende Beispiel zeigt, wie Sie einen Wert für diesen Parameter eingeben:</span><span class="sxs-lookup"><span data-stu-id="7400b-213">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7400b-214">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="7400b-214">-SessionOption</span></span>
<span data-ttu-id="7400b-215">Gibt erweiterte Optionen für die WS-Management Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="7400b-215">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="7400b-216">Geben Sie ein **sessionoption** -Objekt ein, das Sie mit dem New-WSManSessionOption-Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="7400b-216">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="7400b-217">Geben Sie ein, um weitere Informationen zu den verfügbaren Optionen zu erhalten `Get-Help New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="7400b-217">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="7400b-218">-US-</span><span class="sxs-lookup"><span data-stu-id="7400b-218">-UseSSL</span></span>
<span data-ttu-id="7400b-219">Gibt an, dass das Secure Sockets Layer (SSL)-Protokoll verwendet wird, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="7400b-219">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="7400b-220">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7400b-220">By default, SSL is not used.</span></span>

<span data-ttu-id="7400b-221">WS-Management verschlüsselt alle PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="7400b-221">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="7400b-222">Mit *dem Parameter "* Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.</span><span class="sxs-lookup"><span data-stu-id="7400b-222">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="7400b-223">Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="7400b-223">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="7400b-224">-Valueset</span><span class="sxs-lookup"><span data-stu-id="7400b-224">-ValueSet</span></span>
<span data-ttu-id="7400b-225">Gibt eine Hashtabelle an, mit deren Hilfe eine Verwaltungsressource geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="7400b-225">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="7400b-226">Sie geben die Verwaltungs Ressource mithilfe von *resourceUri* und *Selector set* an.</span><span class="sxs-lookup"><span data-stu-id="7400b-226">You specify the management resource by using *ResourceURI* and *SelectorSet*.</span></span>
<span data-ttu-id="7400b-227">Der Wert des *valueset* -Parameters muss eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="7400b-227">The value of the *ValueSet* parameter must be a hash table.</span></span>

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

### <span data-ttu-id="7400b-228">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7400b-228">CommonParameters</span></span>
<span data-ttu-id="7400b-229">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7400b-229">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7400b-230">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7400b-230">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7400b-231">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7400b-231">INPUTS</span></span>

### <span data-ttu-id="7400b-232">Keine</span><span class="sxs-lookup"><span data-stu-id="7400b-232">None</span></span>
<span data-ttu-id="7400b-233">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="7400b-233">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="7400b-234">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7400b-234">OUTPUTS</span></span>

### <span data-ttu-id="7400b-235">Keine</span><span class="sxs-lookup"><span data-stu-id="7400b-235">None</span></span>
<span data-ttu-id="7400b-236">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7400b-236">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7400b-237">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7400b-237">NOTES</span></span>

## <span data-ttu-id="7400b-238">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7400b-238">RELATED LINKS</span></span>

[<span data-ttu-id="7400b-239">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="7400b-239">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="7400b-240">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="7400b-240">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="7400b-241">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="7400b-241">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="7400b-242">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="7400b-242">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="7400b-243">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="7400b-243">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="7400b-244">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="7400b-244">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="7400b-245">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="7400b-245">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="7400b-246">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="7400b-246">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="7400b-247">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="7400b-247">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="7400b-248">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="7400b-248">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="7400b-249">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="7400b-249">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="7400b-250">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="7400b-250">Test-WSMan</span></span>](Test-WSMan.md)

