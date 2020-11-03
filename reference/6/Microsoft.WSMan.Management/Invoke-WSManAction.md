---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/invoke-wsmanaction?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WSManAction
ms.openlocfilehash: b969449d3e2e888138f783c17e16fa696fe40efe
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218599"
---
# <span data-ttu-id="5aa86-103">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="5aa86-103">Invoke-WSManAction</span></span>

## <span data-ttu-id="5aa86-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5aa86-104">SYNOPSIS</span></span>
<span data-ttu-id="5aa86-105">Ruft eine Aktion für das Objekt auf, das durch den Ressourcen-URI und die Selektoren angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="5aa86-105">Invokes an action on the object that is specified by the Resource URI and by the selectors.</span></span>

## <span data-ttu-id="5aa86-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5aa86-106">SYNTAX</span></span>

### <span data-ttu-id="5aa86-107">URI (Standard)</span><span class="sxs-lookup"><span data-stu-id="5aa86-107">URI (Default)</span></span>

```
Invoke-WSManAction [-Action] <String> [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>]
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-ValueSet <Hashtable>] [-ResourceURI] <Uri>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="5aa86-108">Computername</span><span class="sxs-lookup"><span data-stu-id="5aa86-108">ComputerName</span></span>

```
Invoke-WSManAction [-Action] <String> [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-UseSSL] [-ValueSet <Hashtable>] [-ResourceURI] <Uri> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="5aa86-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5aa86-109">DESCRIPTION</span></span>
<span data-ttu-id="5aa86-110">Die **Aufruf-wsmanaction** führt eine Aktion für das Objekt aus, das durch RESOURCE_URI angegeben wird, wobei Parameter durch Schlüssel-Wert-Paare angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5aa86-110">The **Invoke-WSManAction** runs an action on the object that is specified by RESOURCE_URI, where parameters are specified by key value pairs.</span></span>

<span data-ttu-id="5aa86-111">Das Cmdlet verwendet die Verbindungs-/Transportschicht von WSMan zum Ausführen der Aktion.</span><span class="sxs-lookup"><span data-stu-id="5aa86-111">This cmdlet uses the WSMan connection/transport layer to run the action.</span></span>

## <span data-ttu-id="5aa86-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5aa86-112">EXAMPLES</span></span>

### <span data-ttu-id="5aa86-113">Beispiel 1: Aufrufen einer Methode</span><span class="sxs-lookup"><span data-stu-id="5aa86-113">Example 1: Invoke a method</span></span>

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

<span data-ttu-id="5aa86-114">Dieser Befehl ruft die **Start Service** -Methode der Win32_Service WMI-Klasseninstanz auf, die dem Spoolerdienst entspricht.</span><span class="sxs-lookup"><span data-stu-id="5aa86-114">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>

<span data-ttu-id="5aa86-115">Der Rückgabewert gibt an, ob die Aktion erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="5aa86-115">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="5aa86-116">In diesem Fall deutet der Rückgabewert 0 auf eine erfolgreiche Aktion hin.</span><span class="sxs-lookup"><span data-stu-id="5aa86-116">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="5aa86-117">Der Rückgabewert 5 gibt an, dass der Dienst bereits gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="5aa86-117">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="5aa86-118">Beispiel 2: Aufrufen einer Methode</span><span class="sxs-lookup"><span data-stu-id="5aa86-118">Example 2: Invoke a method</span></span>

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

<span data-ttu-id="5aa86-119">Mit diesem Befehl wird die **Stop Service** -Methode für den Spoolerdienst aufgerufen, indem Eingaben aus einer Datei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5aa86-119">This command calls the **StopService** method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="5aa86-120">Die Datei „Input.xml“ weist folgenden Inhalt auf:</span><span class="sxs-lookup"><span data-stu-id="5aa86-120">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

### <span data-ttu-id="5aa86-121">Beispiel 3: Aufrufen einer Methode mit angegebenen Parameterwerten</span><span class="sxs-lookup"><span data-stu-id="5aa86-121">Example 3: Invoke a method with specified parameter values</span></span>

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

<span data-ttu-id="5aa86-122">Dieser Befehl ruft die **Create** -Methode der Win32_Process-Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="5aa86-122">This command calls the **Create** method of the Win32_Process class.</span></span>
<span data-ttu-id="5aa86-123">Die Methode übergibt die beiden Parameterwerte Notepad.exe und c:\.</span><span class="sxs-lookup"><span data-stu-id="5aa86-123">It passes the method two parameter values, Notepad.exe and C:\.</span></span>
<span data-ttu-id="5aa86-124">Folglich wird ein neuer Prozess erstellt, um Notepad auszuführen, und das aktuelle Verzeichnis des neuen Prozesses wird auf c:\fest gelegt.</span><span class="sxs-lookup"><span data-stu-id="5aa86-124">As a result, a new process is created to run Notepad, and the current directory of the new process is set to C:\.</span></span>

### <span data-ttu-id="5aa86-125">Beispiel 4: Aufrufen einer Methode auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="5aa86-125">Example 4: Invoke a method on a remote computer</span></span>

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

<span data-ttu-id="5aa86-126">Dieser Befehl ruft die **Start Service** -Methode der Win32_Service WMI-Klasseninstanz auf, die dem Spoolerdienst entspricht.</span><span class="sxs-lookup"><span data-stu-id="5aa86-126">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>
<span data-ttu-id="5aa86-127">Da der *Computername* -Parameter angegeben wird, wird der Befehl auf dem Remote Computer Server01 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5aa86-127">Because the *ComputerName* parameter is specified, the command runs against the remote server01 computer.</span></span>

## <span data-ttu-id="5aa86-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5aa86-128">PARAMETERS</span></span>

### <span data-ttu-id="5aa86-129">-Action</span><span class="sxs-lookup"><span data-stu-id="5aa86-129">-Action</span></span>
<span data-ttu-id="5aa86-130">Gibt die Methode an, die für das von resourceUri und Selektoren angegebene Verwaltungs Objekt ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5aa86-130">Specifies the method to run on the management object specified by the ResourceURI and selectors.</span></span>

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

### <span data-ttu-id="5aa86-131">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="5aa86-131">-ApplicationName</span></span>
<span data-ttu-id="5aa86-132">Gibt den Anwendungsnamen in der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="5aa86-132">Specifies the application name in the connection.</span></span>
<span data-ttu-id="5aa86-133">Der Standardwert des *ApplicationName* -Parameters lautet "wsman".</span><span class="sxs-lookup"><span data-stu-id="5aa86-133">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="5aa86-134">Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="5aa86-134">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="5aa86-135">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="5aa86-135">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="5aa86-136">Beispiel: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="5aa86-136">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="5aa86-137">Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="5aa86-137">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="5aa86-138">Diese Standardeinstellung von WSMAN eignet sich für die meisten Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="5aa86-138">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="5aa86-139">Dieser Parameter ist für die Verwendung bestimmt, wenn viele Computer Remote Verbindungen mit einem Computer herstellen, auf dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5aa86-139">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="5aa86-140">In diesem Fall wird Web Services for Management (WS-Management) aus Gründen der Effizienz von IIS gehostet.</span><span class="sxs-lookup"><span data-stu-id="5aa86-140">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="5aa86-141">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5aa86-141">-Authentication</span></span>
<span data-ttu-id="5aa86-142">Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5aa86-142">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="5aa86-143">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="5aa86-143">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5aa86-144">Standard.</span><span class="sxs-lookup"><span data-stu-id="5aa86-144">Basic.</span></span>
<span data-ttu-id="5aa86-145">„Basic“ ist ein Schema, bei dem der Benutzername und das Kennwort im Klartext an den Server oder Proxy gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="5aa86-145">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="5aa86-146">Standard.</span><span class="sxs-lookup"><span data-stu-id="5aa86-146">Default.</span></span>
<span data-ttu-id="5aa86-147">Verwendet die vom WS-Verwaltungsprotokoll implementierte Authentifizierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="5aa86-147">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="5aa86-148">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="5aa86-148">This is the default.</span></span>
- <span data-ttu-id="5aa86-149">Digest.</span><span class="sxs-lookup"><span data-stu-id="5aa86-149">Digest.</span></span>
<span data-ttu-id="5aa86-150">„Digest“ ist ein Abfrage/Rückmeldung-Schema, bei dem eine vom Server angegebene Datenzeichenfolge für die Abfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5aa86-150">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="5aa86-151">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="5aa86-151">Kerberos.</span></span>
<span data-ttu-id="5aa86-152">Der Clientcomputer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="5aa86-152">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="5aa86-153">Negotiate</span><span class="sxs-lookup"><span data-stu-id="5aa86-153">Negotiate.</span></span>
<span data-ttu-id="5aa86-154">„Negotiate“ ist ein Abfrage/Rückmeldung-Schema, bei dem das für die Authentifizierung zu verwendende Schema mit dem Server oder Proxy ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="5aa86-154">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="5aa86-155">Dieser Parameterwert ermöglicht beispielsweise die Aushandlung, um zu bestimmen, ob das Kerberos-Protokoll oder NTLM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5aa86-155">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="5aa86-156">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="5aa86-156">CredSSP.</span></span>
<span data-ttu-id="5aa86-157">Verwenden Sie die Authentifizierung der Credential Security Support Provider (kredssp), mit der der Benutzer Anmelde Informationen delegieren kann.</span><span class="sxs-lookup"><span data-stu-id="5aa86-157">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="5aa86-158">Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.</span><span class="sxs-lookup"><span data-stu-id="5aa86-158">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="5aa86-159">Vorsicht: die Anmelde Informationen des Benutzers werden vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="5aa86-159">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="5aa86-160">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="5aa86-160">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="5aa86-161">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5aa86-161">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="5aa86-162">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="5aa86-162">-CertificateThumbprint</span></span>
<span data-ttu-id="5aa86-163">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="5aa86-163">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="5aa86-164">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="5aa86-164">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="5aa86-165">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5aa86-165">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="5aa86-166">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="5aa86-166">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="5aa86-167">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den Befehl Get-Item oder Get-ChildItem im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="5aa86-167">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="5aa86-168">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="5aa86-168">-ComputerName</span></span>
<span data-ttu-id="5aa86-169">Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5aa86-169">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="5aa86-170">Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="5aa86-170">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="5aa86-171">Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5aa86-171">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="5aa86-172">Der lokale Computer ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="5aa86-172">The local computer is the default.</span></span>
<span data-ttu-id="5aa86-173">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="5aa86-173">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="5aa86-174">Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="5aa86-174">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="5aa86-175">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="5aa86-175">-ConnectionURI</span></span>
<span data-ttu-id="5aa86-176">Gibt den Verbindungsendpunkt an.</span><span class="sxs-lookup"><span data-stu-id="5aa86-176">Specifies the connection endpoint.</span></span>
<span data-ttu-id="5aa86-177">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5aa86-177">The format of this string is as follows:</span></span>

<span data-ttu-id="5aa86-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="5aa86-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="5aa86-179">Die folgende Zeichenfolge ist ein ordnungsgemäß formatierter Wert für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="5aa86-179">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="5aa86-180">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="5aa86-180">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="5aa86-181">-Credential</span><span class="sxs-lookup"><span data-stu-id="5aa86-181">-Credential</span></span>
<span data-ttu-id="5aa86-182">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="5aa86-182">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="5aa86-183">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="5aa86-183">The default is the current user.</span></span>
<span data-ttu-id="5aa86-184">Geben Sie einen Benutzernamen ein, z. b. USER01, Domain01\User01 oder User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="5aa86-184">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="5aa86-185">Oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom Get-Credential-Cmdlet zurück gegebenes Objekt.</span><span class="sxs-lookup"><span data-stu-id="5aa86-185">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="5aa86-186">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="5aa86-186">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="5aa86-187">-FilePath</span><span class="sxs-lookup"><span data-stu-id="5aa86-187">-FilePath</span></span>
<span data-ttu-id="5aa86-188">Gibt den Pfad einer Datei an, die zum Aktualisieren einer Verwaltungsressource verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5aa86-188">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="5aa86-189">Sie geben die Verwaltungs Ressource mit dem *resourceUri* -Parameter und dem *selectorset* -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="5aa86-189">You specify the management resource by using the *ResourceURI* parameter and the *SelectorSet* parameter.</span></span>
<span data-ttu-id="5aa86-190">Der folgende Befehl verwendet z. b. den *FilePath* -Parameter:</span><span class="sxs-lookup"><span data-stu-id="5aa86-190">For example, the following command uses the *FilePath* parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath c:\input.xml -Authentication default`

<span data-ttu-id="5aa86-191">Mit diesem Befehl wird die **Stop Service** -Methode für den **Spoolerdienst** aufgerufen, indem Eingaben aus einer Datei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5aa86-191">This command calls the **StopService** method on the **Spooler** service by using input from a file.</span></span>
<span data-ttu-id="5aa86-192">Die Datei „Input.xml“ weist folgenden Inhalt auf:</span><span class="sxs-lookup"><span data-stu-id="5aa86-192">The file, Input.xml, contains the following content:</span></span>

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

### <span data-ttu-id="5aa86-193">-OptionSET</span><span class="sxs-lookup"><span data-stu-id="5aa86-193">-OptionSet</span></span>
<span data-ttu-id="5aa86-194">Gibt eine Reihe von Schaltern für einen Dienst an, um die Art der Anforderung zu ändern oder zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="5aa86-194">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="5aa86-195">Diese ähneln Switches, die in Befehlszeilenshells verwendet werden, da Sie Dienst spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="5aa86-195">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="5aa86-196">Es können beliebig viele Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5aa86-196">Any number of options can be specified.</span></span>

<span data-ttu-id="5aa86-197">Das folgende Beispiel veranschaulicht die Syntax, durch die die Werte 1, 2 und 3 für die Parameter „a“, „b“ und „c“ übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="5aa86-197">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="5aa86-198">-Port</span><span class="sxs-lookup"><span data-stu-id="5aa86-198">-Port</span></span>
<span data-ttu-id="5aa86-199">Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="5aa86-199">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="5aa86-200">Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80.</span><span class="sxs-lookup"><span data-stu-id="5aa86-200">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="5aa86-201">Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.</span><span class="sxs-lookup"><span data-stu-id="5aa86-201">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="5aa86-202">Wenn Sie HTTPS als Transport verwenden, muss der Wert des *Computername* -Parameters mit dem allgemeinen Namen des Serverzertifikats (CN) identisch sein.</span><span class="sxs-lookup"><span data-stu-id="5aa86-202">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="5aa86-203">Wenn der *skipcncheck* -Parameter jedoch als Teil des *sessionoption* -Parameters angegeben wird, muss der allgemeine Name des Zertifikats für den Server nicht mit dem Hostnamen des Servers identisch sein.</span><span class="sxs-lookup"><span data-stu-id="5aa86-203">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="5aa86-204">Der *skipcncheck* -Parameter sollte nur für vertrauenswürdige Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5aa86-204">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="5aa86-205">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="5aa86-205">-ResourceURI</span></span>
<span data-ttu-id="5aa86-206">Gibt den URI der Ressourcen Klasse oder-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="5aa86-206">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="5aa86-207">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="5aa86-207">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="5aa86-208">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="5aa86-208">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="5aa86-209">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5aa86-209">For example:</span></span>

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

### <span data-ttu-id="5aa86-210">-Selector Set</span><span class="sxs-lookup"><span data-stu-id="5aa86-210">-SelectorSet</span></span>
<span data-ttu-id="5aa86-211">Gibt eine Reihe von Wertpaaren an, mit denen bestimmte Instanzen von Verwaltungsressourcen ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="5aa86-211">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="5aa86-212">*Selector Set* wird verwendet, wenn mehr als eine Instanz der Ressource vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5aa86-212">*SelectorSet* is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="5aa86-213">Der Wert von *Selector Set* muss eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="5aa86-213">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="5aa86-214">Das folgende Beispiel zeigt, wie Sie einen Wert für diesen Parameter eingeben:</span><span class="sxs-lookup"><span data-stu-id="5aa86-214">The following example shows how to enter a value for this parameter:</span></span>

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

### <span data-ttu-id="5aa86-215">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="5aa86-215">-SessionOption</span></span>
<span data-ttu-id="5aa86-216">Gibt erweiterte Optionen für die WS-Management Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="5aa86-216">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="5aa86-217">Geben Sie ein **sessionoption** -Objekt ein, das Sie mit dem New-WSManSessionOption-Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="5aa86-217">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="5aa86-218">Geben Sie ein, um weitere Informationen zu den verfügbaren Optionen zu erhalten `Get-Help New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="5aa86-218">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="5aa86-219">-US-</span><span class="sxs-lookup"><span data-stu-id="5aa86-219">-UseSSL</span></span>
<span data-ttu-id="5aa86-220">Gibt an, dass das Secure Sockets Layer (SSL)-Protokoll verwendet wird, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="5aa86-220">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="5aa86-221">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5aa86-221">By default, SSL is not used.</span></span>

<span data-ttu-id="5aa86-222">WS-Management verschlüsselt alle PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="5aa86-222">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="5aa86-223">Mit *dem Parameter "* Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.</span><span class="sxs-lookup"><span data-stu-id="5aa86-223">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="5aa86-224">Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="5aa86-224">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="5aa86-225">-Valueset</span><span class="sxs-lookup"><span data-stu-id="5aa86-225">-ValueSet</span></span>
<span data-ttu-id="5aa86-226">Gibt eine Hashtabelle an, mit deren Hilfe eine Verwaltungsressource geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5aa86-226">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="5aa86-227">Sie geben die Verwaltungs Ressource mithilfe von *resourceUri* und *Selector set* an.</span><span class="sxs-lookup"><span data-stu-id="5aa86-227">You specify the management resource by using *ResourceURI* and *SelectorSet*.</span></span>
<span data-ttu-id="5aa86-228">Der Wert des *valueset* -Parameters muss eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="5aa86-228">The value of the *ValueSet* parameter must be a hash table.</span></span>

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

### <span data-ttu-id="5aa86-229">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5aa86-229">CommonParameters</span></span>
<span data-ttu-id="5aa86-230">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5aa86-230">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5aa86-231">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5aa86-231">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5aa86-232">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5aa86-232">INPUTS</span></span>

### <span data-ttu-id="5aa86-233">Keine</span><span class="sxs-lookup"><span data-stu-id="5aa86-233">None</span></span>
<span data-ttu-id="5aa86-234">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="5aa86-234">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="5aa86-235">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5aa86-235">OUTPUTS</span></span>

### <span data-ttu-id="5aa86-236">Keine</span><span class="sxs-lookup"><span data-stu-id="5aa86-236">None</span></span>
<span data-ttu-id="5aa86-237">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5aa86-237">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5aa86-238">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5aa86-238">NOTES</span></span>

## <span data-ttu-id="5aa86-239">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5aa86-239">RELATED LINKS</span></span>

[<span data-ttu-id="5aa86-240">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="5aa86-240">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="5aa86-241">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="5aa86-241">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="5aa86-242">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="5aa86-242">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="5aa86-243">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="5aa86-243">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="5aa86-244">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="5aa86-244">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="5aa86-245">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="5aa86-245">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="5aa86-246">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="5aa86-246">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="5aa86-247">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="5aa86-247">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="5aa86-248">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="5aa86-248">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="5aa86-249">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="5aa86-249">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="5aa86-250">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="5aa86-250">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="5aa86-251">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="5aa86-251">Test-WSMan</span></span>](Test-WSMan.md)
