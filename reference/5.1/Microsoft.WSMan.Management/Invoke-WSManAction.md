---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/invoke-wsmanaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WSManAction
ms.openlocfilehash: 1eeeb912ab32ec5334959daba1e352f20fec15b1
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224799"
---
# <span data-ttu-id="39c03-103">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="39c03-103">Invoke-WSManAction</span></span>

## <span data-ttu-id="39c03-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="39c03-104">SYNOPSIS</span></span>
<span data-ttu-id="39c03-105">Ruft eine Aktion für das Objekt auf, das durch den Ressourcen-URI und die Selektoren angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="39c03-105">Invokes an action on the object that is specified by the Resource URI and by the selectors.</span></span>

## <span data-ttu-id="39c03-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="39c03-106">SYNTAX</span></span>

### <span data-ttu-id="39c03-107">URI (Standard)</span><span class="sxs-lookup"><span data-stu-id="39c03-107">URI (Default)</span></span>

```
Invoke-WSManAction [-Action] <String> [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>]
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-ValueSet <Hashtable>] [-ResourceURI] <Uri>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="39c03-108">Computername</span><span class="sxs-lookup"><span data-stu-id="39c03-108">ComputerName</span></span>

```
Invoke-WSManAction [-Action] <String> [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-UseSSL] [-ValueSet <Hashtable>] [-ResourceURI] <Uri> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="39c03-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="39c03-109">DESCRIPTION</span></span>

<span data-ttu-id="39c03-110">Invoke-WSManAction führt eine Aktion für das Objekt aus, das durch RESOURCE_URI angegeben wird. Parameter werden dabei durch Schlüssel-Wert-Paare angegeben.</span><span class="sxs-lookup"><span data-stu-id="39c03-110">The Invoke-WSManAction runs an action on the object that is specified by RESOURCE_URI, where parameters are specified by key value pairs.</span></span>

<span data-ttu-id="39c03-111">Das Cmdlet verwendet die Verbindungs-/Transportschicht von WSMan zum Ausführen der Aktion.</span><span class="sxs-lookup"><span data-stu-id="39c03-111">This cmdlet uses the WSMan connection/transport layer to run the action.</span></span>

## <span data-ttu-id="39c03-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="39c03-112">EXAMPLES</span></span>

### <span data-ttu-id="39c03-113">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="39c03-113">Example 1</span></span>

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

<span data-ttu-id="39c03-114">Dieser Befehl ruft die StartService-Methode der WMI-Klasseninstanz Win32_Service auf, die dem Spoolerdienst entspricht.</span><span class="sxs-lookup"><span data-stu-id="39c03-114">This command calls the StartService method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>

<span data-ttu-id="39c03-115">Der Rückgabewert gibt an, ob die Aktion erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="39c03-115">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="39c03-116">In diesem Fall deutet der Rückgabewert 0 auf eine erfolgreiche Aktion hin.</span><span class="sxs-lookup"><span data-stu-id="39c03-116">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="39c03-117">Der Rückgabewert 5 gibt an, dass der Dienst bereits gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="39c03-117">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="39c03-118">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="39c03-118">Example 2</span></span>

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

<span data-ttu-id="39c03-119">Dieser Befehl ruft die StopService-Methode für den Spoolerdienst auf und verwendet für die Eingabe eine Datei.</span><span class="sxs-lookup"><span data-stu-id="39c03-119">This command calls the StopService method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="39c03-120">Die Datei „Input.xml“ weist folgenden Inhalt auf:</span><span class="sxs-lookup"><span data-stu-id="39c03-120">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

<span data-ttu-id="39c03-121">Der Rückgabewert gibt an, ob die Aktion erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="39c03-121">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="39c03-122">In diesem Fall deutet der Rückgabewert 0 auf eine erfolgreiche Aktion hin.</span><span class="sxs-lookup"><span data-stu-id="39c03-122">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="39c03-123">Der Rückgabewert 5 gibt an, dass der Dienst bereits gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="39c03-123">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="39c03-124">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="39c03-124">Example 3</span></span>

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

<span data-ttu-id="39c03-125">Dieser Befehl ruft die Create-Methode der Win32_Process-Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="39c03-125">This command calls the Create method of the Win32_Process class.</span></span>
<span data-ttu-id="39c03-126">Die Methode übergibt zwei Parameterwerte, Notepad.exe und "C:" \" .</span><span class="sxs-lookup"><span data-stu-id="39c03-126">It passes the method two parameter values, Notepad.exe and "C:\".</span></span>
<span data-ttu-id="39c03-127">Daher wird ein neuer Prozess erstellt, um Notepad auszuführen, und das aktuelle Verzeichnis des neuen Prozesses wird auf "C:" festgelegt \" .</span><span class="sxs-lookup"><span data-stu-id="39c03-127">As a result, a new process is created to run Notepad, and the current directory of the new process is set to "C:\".</span></span>

### <span data-ttu-id="39c03-128">Beispiel 4</span><span class="sxs-lookup"><span data-stu-id="39c03-128">Example 4</span></span>

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

<span data-ttu-id="39c03-129">Dieser Befehl ruft die StartService-Methode der WMI-Klasseninstanz Win32_Service auf, die dem Spoolerdienst entspricht.</span><span class="sxs-lookup"><span data-stu-id="39c03-129">This command calls the StartService method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>
<span data-ttu-id="39c03-130">Da der ComputerName-Parameter angegeben ist, wird der Befehl für den Remotecomputer server01 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="39c03-130">Because the ComputerName parameter is specified, the command runs against the remote server01 computer.</span></span>

<span data-ttu-id="39c03-131">Der Rückgabewert gibt an, ob die Aktion erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="39c03-131">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="39c03-132">In diesem Fall deutet der Rückgabewert 0 auf eine erfolgreiche Aktion hin.</span><span class="sxs-lookup"><span data-stu-id="39c03-132">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="39c03-133">Der Rückgabewert 5 gibt an, dass der Dienst bereits gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="39c03-133">A return value of 5 indicates that the service is already started.</span></span>

## <span data-ttu-id="39c03-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="39c03-134">PARAMETERS</span></span>

### <span data-ttu-id="39c03-135">-Action</span><span class="sxs-lookup"><span data-stu-id="39c03-135">-Action</span></span>

<span data-ttu-id="39c03-136">Gibt die Methode an, die für das von resourceUri und Selektoren angegebene Verwaltungs Objekt ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="39c03-136">Specifies the method to run on the management object specified by the ResourceURI and selectors.</span></span>

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

### <span data-ttu-id="39c03-137">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="39c03-137">-ApplicationName</span></span>

<span data-ttu-id="39c03-138">Gibt den Anwendungsnamen in der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="39c03-138">Specifies the application name in the connection.</span></span>
<span data-ttu-id="39c03-139">Der Standardwert des ApplicationName-Parameters lautet WSMAN.</span><span class="sxs-lookup"><span data-stu-id="39c03-139">The default value of the ApplicationName parameter is WSMAN.</span></span>
<span data-ttu-id="39c03-140">Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="39c03-140">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="39c03-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="39c03-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="39c03-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="39c03-142">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="39c03-143">Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="39c03-143">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="39c03-144">Die Standardeinstellung „WSMAN“ eignet sich für die meisten Verwendungszwecke.</span><span class="sxs-lookup"><span data-stu-id="39c03-144">This default setting of "WSMAN" is appropriate for most uses.</span></span>
<span data-ttu-id="39c03-145">Dieser Parameter soll verwendet werden, wenn mehrere Computer Remoteverbindungen mit einem Computer herstellen, auf dem Windows PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="39c03-145">This parameter is designed to be used when numerous computers establish remote connections to one computer running Windows PowerShell.</span></span>
<span data-ttu-id="39c03-146">In diesem Fall wird Web Services for Management (WS-Management) aus Gründen der Effizienz von IIS gehostet.</span><span class="sxs-lookup"><span data-stu-id="39c03-146">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="39c03-147">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="39c03-147">-Authentication</span></span>

<span data-ttu-id="39c03-148">Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="39c03-148">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="39c03-149">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="39c03-149">Possible values are:</span></span>

- <span data-ttu-id="39c03-150">Basic: Standard ist ein Schema, in dem der Benutzername und das Kennwort als Klartext an den Server oder Proxy gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="39c03-150">Basic: Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="39c03-151">Standardwert: Verwenden Sie die vom WS-Management Protokoll implementierte Authentifizierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="39c03-151">Default : Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="39c03-152">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="39c03-152">This is the default.</span></span>
- <span data-ttu-id="39c03-153">Digest: Digest ist ein Challenge-Response-Schema, das eine vom Server angegebene Daten Zeichenfolge für die Abfrage verwendet.</span><span class="sxs-lookup"><span data-stu-id="39c03-153">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="39c03-154">Kerberos: der Client Computer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="39c03-154">Kerberos: The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="39c03-155">Aushandeln: aushandeln ist ein Challenge-Response-Schema, das mit dem Server oder Proxy aushandelt, um das für die Authentifizierung zu verwendende Schema zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="39c03-155">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="39c03-156">Dieser Parameterwert ermöglicht es z. B., die Verwendung des Kerberos-Protokolls oder von NTLM auszuhandeln.</span><span class="sxs-lookup"><span data-stu-id="39c03-156">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="39c03-157">Kredssp: verwendet die Authentifizierung des Credential Security Support Provider (aufwärtssp), die dem Benutzer das Delegieren von Anmelde Informationen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="39c03-157">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="39c03-158">Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.</span><span class="sxs-lookup"><span data-stu-id="39c03-158">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="39c03-159">Vorsicht: die Anmelde Informationen des Benutzers werden vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="39c03-159">Caution: CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="39c03-160">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="39c03-160">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="39c03-161">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39c03-161">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="39c03-162">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="39c03-162">-CertificateThumbprint</span></span>

<span data-ttu-id="39c03-163">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="39c03-163">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="39c03-164">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="39c03-164">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="39c03-165">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="39c03-165">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="39c03-166">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="39c03-166">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="39c03-167">Um einen Zertifikatfingerabdruck abzurufen, verwenden Sie den Get-Item-Befehl oder Get-ChildItem-Befehl auf dem Windows PowerShell-Laufwerk „Cert:“.</span><span class="sxs-lookup"><span data-stu-id="39c03-167">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="39c03-168">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="39c03-168">-ComputerName</span></span>

<span data-ttu-id="39c03-169">Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="39c03-169">Specifies the computer against which you want to run the management operation.</span></span>
<span data-ttu-id="39c03-170">Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="39c03-170">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="39c03-171">Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="39c03-171">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="39c03-172">Der lokale Computer ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="39c03-172">The local computer is the default.</span></span>
<span data-ttu-id="39c03-173">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="39c03-173">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="39c03-174">Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="39c03-174">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="39c03-175">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="39c03-175">-ConnectionURI</span></span>

<span data-ttu-id="39c03-176">Gibt den Verbindungsendpunkt an.</span><span class="sxs-lookup"><span data-stu-id="39c03-176">Specifies the connection endpoint.</span></span>
<span data-ttu-id="39c03-177">Das Format dieser Zeichenfolge lautet:</span><span class="sxs-lookup"><span data-stu-id="39c03-177">The format of this string is:</span></span>

<span data-ttu-id="39c03-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="39c03-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="39c03-179">Die folgende Zeichenfolge ist ein ordnungsgemäß formatierter Wert für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="39c03-179">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="39c03-180">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="39c03-180">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="39c03-181">-Credential</span><span class="sxs-lookup"><span data-stu-id="39c03-181">-Credential</span></span>

<span data-ttu-id="39c03-182">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="39c03-182">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="39c03-183">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="39c03-183">The default is the current user.</span></span>
<span data-ttu-id="39c03-184">Geben Sie einen Benutzernamen ein, z. b. "USER01", "Domain01\User01" oder User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="39c03-184">Type a user name, such as "User01", "Domain01\User01", or User@Domain.com.</span></span>
<span data-ttu-id="39c03-185">Oder geben Sie ein PSCredential-Objekt ein, z. B. ein vom Get-Credential-Cmdlet zurückgegebenes Objekt.</span><span class="sxs-lookup"><span data-stu-id="39c03-185">Or, enter a PSCredential object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="39c03-186">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="39c03-186">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="39c03-187">-FilePath</span><span class="sxs-lookup"><span data-stu-id="39c03-187">-FilePath</span></span>

<span data-ttu-id="39c03-188">Gibt den Pfad einer Datei an, die zum Aktualisieren einer Verwaltungsressource verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="39c03-188">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="39c03-189">Sie geben die Verwaltungs Ressource mit dem resourceUri-Parameter und dem selectorset-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="39c03-189">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter.</span></span>
<span data-ttu-id="39c03-190">Der folgende Befehl verwendet z. B. den FilePath-Parameter:</span><span class="sxs-lookup"><span data-stu-id="39c03-190">For example, the following command uses the FilePath parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath c:\input.xml -Authentication default`

<span data-ttu-id="39c03-191">Dieser Befehl ruft die StopService-Methode für den Spoolerdienst auf und verwendet für die Eingabe eine Datei.</span><span class="sxs-lookup"><span data-stu-id="39c03-191">This command calls the StopService method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="39c03-192">Die Datei „Input.xml“ weist folgenden Inhalt auf:</span><span class="sxs-lookup"><span data-stu-id="39c03-192">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

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

### <span data-ttu-id="39c03-193">-OptionSET</span><span class="sxs-lookup"><span data-stu-id="39c03-193">-OptionSet</span></span>

<span data-ttu-id="39c03-194">Übergibt eine Reihe von Schaltern an einen Dienst, um die Art der Anforderung zu ändern oder zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="39c03-194">Passes a set of switches  to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="39c03-195">Diese sind mit Schaltern in Befehlszeilenshells vergleichbar, da sie dienstspezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="39c03-195">These are similar to switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="39c03-196">Es können beliebig viele Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="39c03-196">Any number of options  can be specified.</span></span>

<span data-ttu-id="39c03-197">Das folgende Beispiel veranschaulicht die Syntax, durch die die Werte 1, 2 und 3 für die Parameter „a“, „b“ und „c“ übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="39c03-197">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="39c03-198">-Port</span><span class="sxs-lookup"><span data-stu-id="39c03-198">-Port</span></span>

<span data-ttu-id="39c03-199">Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="39c03-199">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="39c03-200">Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80.</span><span class="sxs-lookup"><span data-stu-id="39c03-200">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="39c03-201">Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.</span><span class="sxs-lookup"><span data-stu-id="39c03-201">When the transport is HTTPS, the default port is 443.</span></span>
<span data-ttu-id="39c03-202">Wenn Sie HTTPS als Transport verwenden, muss der Wert des ComputerName-Parameters mit dem allgemeinen Namen des Serverzertifikats übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="39c03-202">When you use HTTPS as the transport, the value of the ComputerName parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="39c03-203">Wenn der SkipCNCheck-Parameter jedoch als Teil des SessionOption-Parameters angegeben wird, muss der allgemeine Servername im Zertifikat nicht mit dem Hostnamen des Servers übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="39c03-203">However, if the SkipCNCheck parameter is specified as part of the SessionOption parameter, then the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="39c03-204">Der SkipCNCheck-Parameter darf nur für vertrauenswürdige Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39c03-204">The SkipCNCheck parameter should be used only for trusted machines.</span></span>

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

### <span data-ttu-id="39c03-205">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="39c03-205">-ResourceURI</span></span>

<span data-ttu-id="39c03-206">Enthält den URI (Uniform Resource Identifier) der Ressourcenklasse oder -instanz.</span><span class="sxs-lookup"><span data-stu-id="39c03-206">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="39c03-207">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="39c03-207">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="39c03-208">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="39c03-208">A URI consists of a prefix and a path to a resource.</span></span>
<span data-ttu-id="39c03-209">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="39c03-209">For example:</span></span>

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

### <span data-ttu-id="39c03-210">-Selector Set</span><span class="sxs-lookup"><span data-stu-id="39c03-210">-SelectorSet</span></span>

<span data-ttu-id="39c03-211">Gibt eine Reihe von Wertpaaren an, mit denen bestimmte Instanzen von Verwaltungsressourcen ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="39c03-211">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="39c03-212">*Selector Set* wird verwendet, wenn mehr als eine Instanz der Ressource vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="39c03-212">*SelectorSet* is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="39c03-213">Der Wert von *Selector Set* muss eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="39c03-213">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="39c03-214">Das folgende Beispiel zeigt, wie Sie einen Wert für diesen Parameter eingeben:</span><span class="sxs-lookup"><span data-stu-id="39c03-214">The following example shows how to enter a value for this parameter:</span></span>

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

### <span data-ttu-id="39c03-215">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="39c03-215">-SessionOption</span></span>

<span data-ttu-id="39c03-216">Definiert eine Reihe von erweiterten Optionen für die WS-Management-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="39c03-216">Defines a set of extended options for the WS-Management session.</span></span>
<span data-ttu-id="39c03-217">Geben Sie ein SessionOption-Objekt ein, das Sie mit dem New-WSManSessionOption-Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="39c03-217">Enter a SessionOption object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="39c03-218">Weitere Informationen zu den verfügbaren Optionen finden Sie unter „New-WSManSessionOption“.</span><span class="sxs-lookup"><span data-stu-id="39c03-218">For more information about the options that are available, see New-WSManSessionOption.</span></span>

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

### <span data-ttu-id="39c03-219">-US-</span><span class="sxs-lookup"><span data-stu-id="39c03-219">-UseSSL</span></span>

<span data-ttu-id="39c03-220">Gibt an, dass das Secure Sockets Layer (SSL)-Protokoll verwendet wird, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="39c03-220">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="39c03-221">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="39c03-221">By default, SSL is not used.</span></span>

<span data-ttu-id="39c03-222">WS-Management verschlüsselt alle PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="39c03-222">WS-Management encrypts all the PowerShell content  that is transmitted over the network.</span></span>
<span data-ttu-id="39c03-223">Mit dem UseSSL-Parameter können Sie anstelle von HTTP das sicherere HTTPS angeben.</span><span class="sxs-lookup"><span data-stu-id="39c03-223">The UseSSL parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="39c03-224">Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, verursacht der Befehl einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="39c03-224">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="39c03-225">-Valueset</span><span class="sxs-lookup"><span data-stu-id="39c03-225">-ValueSet</span></span>

<span data-ttu-id="39c03-226">Gibt eine Hashtabelle an, mit deren Hilfe eine Verwaltungsressource geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="39c03-226">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="39c03-227">Sie geben die Verwaltungs Ressource mit dem resourceUri-Parameter und dem selectorset-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="39c03-227">You specify the management resource using the ResourceURI and SelectorSet parameters.</span></span>
<span data-ttu-id="39c03-228">Der Wert des ValueSet-Parameters muss eine Hashtabelle sein.</span><span class="sxs-lookup"><span data-stu-id="39c03-228">The value of the ValueSet parameter must be a hash table.</span></span>

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

### <span data-ttu-id="39c03-229">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="39c03-229">CommonParameters</span></span>

<span data-ttu-id="39c03-230">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="39c03-230">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="39c03-231">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="39c03-231">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="39c03-232">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="39c03-232">INPUTS</span></span>

### <span data-ttu-id="39c03-233">Keine</span><span class="sxs-lookup"><span data-stu-id="39c03-233">None</span></span>

<span data-ttu-id="39c03-234">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="39c03-234">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="39c03-235">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="39c03-235">OUTPUTS</span></span>

### <span data-ttu-id="39c03-236">Keine</span><span class="sxs-lookup"><span data-stu-id="39c03-236">None</span></span>

<span data-ttu-id="39c03-237">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="39c03-237">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="39c03-238">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="39c03-238">NOTES</span></span>

## <span data-ttu-id="39c03-239">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="39c03-239">RELATED LINKS</span></span>

[<span data-ttu-id="39c03-240">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="39c03-240">Invoke-WmiMethod</span></span>](../Microsoft.PowerShell.Management/Invoke-WmiMethod.md)

[<span data-ttu-id="39c03-241">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="39c03-241">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="39c03-242">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="39c03-242">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="39c03-243">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="39c03-243">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="39c03-244">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="39c03-244">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="39c03-245">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="39c03-245">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="39c03-246">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="39c03-246">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="39c03-247">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="39c03-247">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="39c03-248">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="39c03-248">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="39c03-249">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="39c03-249">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="39c03-250">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="39c03-250">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="39c03-251">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="39c03-251">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="39c03-252">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="39c03-252">Test-WSMan</span></span>](Test-WSMan.md)
