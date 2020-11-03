---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsessionoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSessionOption
ms.openlocfilehash: 6d926200ae923157c0b7d7556ef13400036b8437
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212420"
---
# <span data-ttu-id="a6bcf-103">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="a6bcf-103">New-CimSessionOption</span></span>

## <span data-ttu-id="a6bcf-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a6bcf-104">SYNOPSIS</span></span>
<span data-ttu-id="a6bcf-105">Gibt erweiterte Optionen für das New-CimSession-Cmdlet an.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-105">Specifies advanced options for the New-CimSession cmdlet.</span></span>

## <span data-ttu-id="a6bcf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a6bcf-106">SYNTAX</span></span>

### <span data-ttu-id="a6bcf-107">Protocoltypeset (Standard)</span><span class="sxs-lookup"><span data-stu-id="a6bcf-107">ProtocolTypeSet (Default)</span></span>

```
New-CimSessionOption [-Protocol] <ProtocolType> [-UICulture <CultureInfo>] [-Culture <CultureInfo>]
 [<CommonParameters>]
```

### <span data-ttu-id="a6bcf-108">Wsmanparameterset</span><span class="sxs-lookup"><span data-stu-id="a6bcf-108">WSManParameterSet</span></span>

```
New-CimSessionOption [-NoEncryption] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-EncodePortInServicePrincipalName] [-Encoding <PacketEncoding>] [-HttpPrefix <Uri>]
 [-MaxEnvelopeSizeKB <UInt32>] [-ProxyAuthentication <PasswordAuthenticationMechanism>]
 [-ProxyCertificateThumbprint <String>] [-ProxyCredential <PSCredential>] [-ProxyType <ProxyType>]
 [-UseSsl] [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

### <span data-ttu-id="a6bcf-109">Dcomparameterset</span><span class="sxs-lookup"><span data-stu-id="a6bcf-109">DcomParameterSet</span></span>

```
New-CimSessionOption [-Impersonation <ImpersonationType>] [-PacketIntegrity] [-PacketPrivacy]
 [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

## <span data-ttu-id="a6bcf-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a6bcf-110">DESCRIPTION</span></span>

<span data-ttu-id="a6bcf-111">Das- `New-CimSessionOption` Cmdlet erstellt eine Instanz eines CIM-Sitzungs Options-Objekts.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-111">The `New-CimSessionOption` cmdlet creates an instance of a CIM session options object.</span></span> <span data-ttu-id="a6bcf-112">Sie verwenden ein CIM-Sitzungs Options Objekt als Eingabe für das `New-CimSession` Cmdlet, um die Optionen für eine CIM-Sitzung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-112">You use a CIM session options object as input to the `New-CimSession` cmdlet to specify the options for a CIM session.</span></span>

<span data-ttu-id="a6bcf-113">Dieses Cmdlet verfügt über zwei Parametersätze: einen für WSMAN-Optionen und einen für DCOM-Optionen (verteiltes Component Object Model).</span><span class="sxs-lookup"><span data-stu-id="a6bcf-113">This cmdlet has two parameter sets, one for WsMan options and one for Distributed Component Object Model (DCOM) options.</span></span> <span data-ttu-id="a6bcf-114">Abhängig von den Parametern, die Sie verwenden, gibt das Cmdlet entweder eine Instanz der DCOM-Sitzungs Optionen zurück oder gibt WSMAN-Sitzungs Optionen zurück.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-114">Depending on which parameters you use, the cmdlet returns either an instance of DCOM session options or returns WsMan session options.</span></span>

## <span data-ttu-id="a6bcf-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a6bcf-115">EXAMPLES</span></span>

### <span data-ttu-id="a6bcf-116">Beispiel 1: Erstellen eines CIM-Sitzungs Options Objekts für DCOM</span><span class="sxs-lookup"><span data-stu-id="a6bcf-116">Example 1: Create a CIM session options object for DCOM</span></span>

<span data-ttu-id="a6bcf-117">In diesem Beispiel wird ein CIM-Sitzungs Options-Objekt für das DCOM-Protokoll erstellt und in einer Variablen mit dem Namen gespeichert `$so` .</span><span class="sxs-lookup"><span data-stu-id="a6bcf-117">This example creates a CIM session options object for the DCOM protocol and stores it in a variable named `$so`.</span></span> <span data-ttu-id="a6bcf-118">Der Inhalt der Variablen wird dann an das `New-CimSession` Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-118">The contents of the variable are then passed to the `New-CimSession` cmdlet.</span></span>
<span data-ttu-id="a6bcf-119">`New-CimSession` Anschließend wird eine neue CIM-Sitzung mit dem Remote Server mit dem Namen Server01 erstellt, wobei die in der Variablen definierten Optionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-119">`New-CimSession` then creates a new CIM session with the remote server named Server01, using the options defined in the variable.</span></span>

```powershell
$so = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server01 -SessionOption $so
```

### <span data-ttu-id="a6bcf-120">Beispiel 2: Erstellen eines CIM-Sitzungs Options-Objekts für WSMAN</span><span class="sxs-lookup"><span data-stu-id="a6bcf-120">Example 2: Create a CIM session options object for WsMan</span></span>

<span data-ttu-id="a6bcf-121">In diesem Beispiel wird ein CIM-Sitzungs Options-Objekt für das WSMAN-Protokoll erstellt.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-121">This example creates a CIM session options object for the WsMan protocol.</span></span> <span data-ttu-id="a6bcf-122">Das-Objekt enthält die Konfiguration für den Authentifizierungsmodus von **Kerberos** , der durch den **Proxyauthentication** -Parameter angegeben wird, die vom **proxycredential** -Parameter angegebenen Anmelde Informationen und gibt an, dass der Befehl die Überprüfung der Zertifizierungsstelle überspringt, die CN-Überprüfung überspringt und SSL verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-122">The object contains configuration for the authentication mode of **Kerberos** specified by the **ProxyAuthentication** parameter, the credentials specified by the **ProxyCredential** parameter, and specifies that the command is to skip the CA check, skip the CN check, and use SSL.</span></span>

```powershell
New-CimSessionOption -ProxyAuthentication Kerberos -ProxyCredential $cred -SkipCACheck -SkipCNCheck -UseSsl
```

### <span data-ttu-id="a6bcf-123">Beispiel 3: Erstellen eines CIM-Sitzungs Options Objekts mit der angegebenen Kultur</span><span class="sxs-lookup"><span data-stu-id="a6bcf-123">Example 3: Create a CIM session options object with the culture specified</span></span>

```powershell
New-CimSessionOption -Culture Fr-Fr -Protocol Wsman
```

<span data-ttu-id="a6bcf-124">In diesem Beispiel wird die Kultur angegeben, die für die CIM-Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-124">This example specifies the culture that is used for the CIM session.</span></span> <span data-ttu-id="a6bcf-125">Standardmäßig wird die Kultur des Clients beim Ausführen von Vorgängen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-125">By default, the culture of the client is used when performing operations.</span></span> <span data-ttu-id="a6bcf-126">Die Standard Kultur kann jedoch mit dem **Culture** -Parameter überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-126">However, the default culture can be overridden using the **Culture** parameter.</span></span>

## <span data-ttu-id="a6bcf-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a6bcf-127">PARAMETERS</span></span>

### <span data-ttu-id="a6bcf-128">-Kultur</span><span class="sxs-lookup"><span data-stu-id="a6bcf-128">-Culture</span></span>

<span data-ttu-id="a6bcf-129">Gibt die Kultur der Benutzeroberfläche an, die für die CIM-Sitzung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-129">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="a6bcf-130">Geben Sie den Wert für diesen Parameter in einem der folgenden Formate an:</span><span class="sxs-lookup"><span data-stu-id="a6bcf-130">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="a6bcf-131">Ein Kultur Name im `<languagecode2>-<country/regioncode2>` Format, z. b. "en-US".</span><span class="sxs-lookup"><span data-stu-id="a6bcf-131">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="a6bcf-132">Eine Variable, die ein **CultureInfo** -Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-132">A variable that contains a **CultureInfo** object.</span></span>
- <span data-ttu-id="a6bcf-133">Ein Befehl, der ein **CultureInfo** -Objekt abruft, z. b. " [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md) "</span><span class="sxs-lookup"><span data-stu-id="a6bcf-133">A command that gets a **CultureInfo** object, such as [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-134">-Encodeportinserviceprincipalname</span><span class="sxs-lookup"><span data-stu-id="a6bcf-134">-EncodePortInServicePrincipalName</span></span>

<span data-ttu-id="a6bcf-135">Gibt an, dass die Kerberos-Verbindung eine Verbindung mit einem Dienst herstellt, dessen Dienst Prinzipal Name (SPN) die Dienst Portnummer enthält.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-135">Indicates that the Kerberos connection is connecting to a service whose service principal name (SPN) includes the service port number.</span></span> <span data-ttu-id="a6bcf-136">Dieser Verbindungstyp ist nicht üblich.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-136">This type of connection is not common.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-137">-Codierung</span><span class="sxs-lookup"><span data-stu-id="a6bcf-137">-Encoding</span></span>

<span data-ttu-id="a6bcf-138">Gibt die für das WSMAN-Protokoll verwendete Codierung an.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-138">Specifies the encoding used for the WsMan protocol.</span></span> <span data-ttu-id="a6bcf-139">Die zulässigen Werte für diesen Parameter sind: **default** , **UTF8** oder **Utf16** .</span><span class="sxs-lookup"><span data-stu-id="a6bcf-139">The acceptable values for this parameter are: **Default** , **Utf8** , or **Utf16** .</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.PacketEncoding
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: Default, Utf8, Utf16

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-140">-Httpprefix</span><span class="sxs-lookup"><span data-stu-id="a6bcf-140">-HttpPrefix</span></span>

<span data-ttu-id="a6bcf-141">Gibt den Teil der http-URL nach dem Computernamen und der Portnummer an.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-141">Specifies the part of the HTTP URL after the computer name and port number.</span></span> <span data-ttu-id="a6bcf-142">Das Ändern dieser Änderung ist nicht üblich.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-142">Changing this is not common.</span></span> <span data-ttu-id="a6bcf-143">Standardmäßig ist der Wert dieses Parameters **/WSMAN** .</span><span class="sxs-lookup"><span data-stu-id="a6bcf-143">By default, the value of this parameter is **/wsman** .</span></span>

```yaml
Type: System.Uri
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-144">-Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="a6bcf-144">-Impersonation</span></span>

<span data-ttu-id="a6bcf-145">Erstellt eine DCOM-Sitzung zum Windows-Verwaltungsinstrumentation (WMI) mithilfe des Identitäts Wechsels.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-145">Creates a DCOM session to Windows Management Instrumentation (WMI) using impersonation.</span></span>

<span data-ttu-id="a6bcf-146">Gültige Parameterwerte:</span><span class="sxs-lookup"><span data-stu-id="a6bcf-146">Valid values for this parameter are:</span></span>

- <span data-ttu-id="a6bcf-147">Standard: DCOM kann die Identitätswechsel Ebene mithilfe des normalen sicherheitsaushandlungs Algorithmus auswählen.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-147">Default: DCOM can choose the impersonation level using its normal security negotiation algorithm.</span></span>
- <span data-ttu-id="a6bcf-148">None: der Client ist für den Server anonym.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-148">None: The client is anonymous to the server.</span></span> <span data-ttu-id="a6bcf-149">Der Server Prozess kann die Identität des Clients annehmen, das Identitätswechsel Token enthält jedoch keine Informationen und kann nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-149">The server process can impersonate the client, but the impersonation token does not contain any information and cannot be used.</span></span>
- <span data-ttu-id="a6bcf-150">Identifizieren: ermöglicht es Objekten, die Anmelde Informationen des Aufrufers abzufragen.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-150">Identify: Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="a6bcf-151">Identität annehmen: ermöglicht es Objekten, die Anmelde Informationen des Aufrufers zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-151">Impersonate: Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="a6bcf-152">Delegat: ermöglicht es Objekten, anderen Objekten die Verwendung der Anmelde Informationen des Aufrufers zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-152">Delegate: Allows objects to permit other objects to use the credentials of the caller.</span></span>

<span data-ttu-id="a6bcf-153">Wenn **der** Identitätswechsel nicht angegeben wird, `New-CimSession` verwendet das Cmdlet den Wert **Impersonate** von Identitätswechsel.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-153">If **Impersonation** is not specified, the `New-CimSession` cmdlet uses the value of **Impersonate** .</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.ImpersonationType
Parameter Sets: DcomParameterSet
Aliases:
Accepted values: Default, None, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-154">-Maxenvelopesizekb</span><span class="sxs-lookup"><span data-stu-id="a6bcf-154">-MaxEnvelopeSizeKB</span></span>

<span data-ttu-id="a6bcf-155">Gibt die Größenbeschränkung von WSMAN-XML-Nachrichten für beide Richtungen an.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-155">Specifies the size limit of WsMan XML messages for either direction.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-156">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="a6bcf-156">-NoEncryption</span></span>

<span data-ttu-id="a6bcf-157">Gibt an, dass die Datenverschlüsselung deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-157">Specifies that data encryption is turned off.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-158">-Packetintegrity</span><span class="sxs-lookup"><span data-stu-id="a6bcf-158">-PacketIntegrity</span></span>

<span data-ttu-id="a6bcf-159">Gibt an, dass die für WMI erstellte DCOM-Sitzung die Component Object Model (com) _packetintegrity_ -Funktionalität verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-159">Specifies that the DCOM session created to WMI uses the Component Object Model (COM) _PacketIntegrity_ functionality.</span></span> <span data-ttu-id="a6bcf-160">Standardmäßig wird für alle mit DCOM erstellten CIM-Sitzungen der **packetintegrity** -Parameter auf **true** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-160">By default, all CIM sessions created using DCOM have the **PacketIntegrity** parameter set to **True** .</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DcomParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-161">-PacketPrivacy</span><span class="sxs-lookup"><span data-stu-id="a6bcf-161">-PacketPrivacy</span></span>

<span data-ttu-id="a6bcf-162">Erstellt eine DCOM-Sitzung mit WMI mithilfe von com _PacketPrivacy_ .</span><span class="sxs-lookup"><span data-stu-id="a6bcf-162">Creates a DCOM session to WMI using the COM _PacketPrivacy_ .</span></span> <span data-ttu-id="a6bcf-163">Standardmäßig wird für alle mit DCOM erstellten CIM-Sitzungen der **PacketPrivacy** -Parameter auf **true** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-163">By default, all CIM sessions created using DCOM have the **PacketPrivacy** parameter set to **true** .</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DcomParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-164">-Protocol</span><span class="sxs-lookup"><span data-stu-id="a6bcf-164">-Protocol</span></span>

<span data-ttu-id="a6bcf-165">Gibt das zu verwendende Protokoll an.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-165">Specifies the protocol to use.</span></span> <span data-ttu-id="a6bcf-166">Die zulässigen Werte für diesen Parameter sind: **DCOM** , **default** oder **WSMAN** .</span><span class="sxs-lookup"><span data-stu-id="a6bcf-166">The acceptable values for this parameter are: **DCOM** , **Default** , or **Wsman** .</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimCmdlets.ProtocolType
Parameter Sets: ProtocolTypeSet
Aliases:
Accepted values: Dcom, Default, Wsman

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-167">-Proxy Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a6bcf-167">-ProxyAuthentication</span></span>

<span data-ttu-id="a6bcf-168">Gibt die Authentifizierungsmethode an, die für die Proxy Auflösung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-168">Specifies the authentication method to use for proxy resolution.</span></span> <span data-ttu-id="a6bcf-169">Die zulässigen Werte für diesen Parameter sind: **default** , **Digest** , **Aushandlungs** , **Basic** , **Kerberos** , **ntlmdomain** oder **kredssp** .</span><span class="sxs-lookup"><span data-stu-id="a6bcf-169">The acceptable values for this parameter are: **Default** , **Digest** , **Negotiate** , **Basic** , **Kerberos** , **NtlmDomain** , or **CredSsp** .</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.PasswordAuthenticationMechanism
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: Default, Digest, Negotiate, Basic, Kerberos, NtlmDomain, CredSsp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-170">-Proxycertifipaethumschlag Print</span><span class="sxs-lookup"><span data-stu-id="a6bcf-170">-ProxyCertificateThumbprint</span></span>

<span data-ttu-id="a6bcf-171">Gibt das digitale Zertifikat für öffentliche Schlüssel (x. 509) eines Benutzerkontos für die Proxy Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-171">Specifies the (x.509) digital public key certificate of a user account for proxy authentication.</span></span>
<span data-ttu-id="a6bcf-172">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-172">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="a6bcf-173">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-173">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="a6bcf-174">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänen Konten.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-174">They can only be mapped to local user accounts and they do not work with domain accounts.</span></span>

<span data-ttu-id="a6bcf-175">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie `Get-Item` die `Get-ChildItem` Cmdlets oder im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="a6bcf-175">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-176">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="a6bcf-176">-ProxyCredential</span></span>

<span data-ttu-id="a6bcf-177">Gibt die Anmeldeinformationen an, die für die Proxyauthentifizierung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-177">Specifies the credentials to use for proxy authentication.</span></span> <span data-ttu-id="a6bcf-178">Geben Sie eine der folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="a6bcf-178">Enter one of the following:</span></span>

- <span data-ttu-id="a6bcf-179">Eine Variable, die ein PSCredential-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-179">A variable that contains a PSCredential object.</span></span>
- <span data-ttu-id="a6bcf-180">Ein Befehl, der ein PSCredential-Objekt abruft, z. b. `Get-Credential`</span><span class="sxs-lookup"><span data-stu-id="a6bcf-180">A command that gets a PSCredential object, such as `Get-Credential`</span></span>

<span data-ttu-id="a6bcf-181">Wenn diese Option nicht festgelegt ist, können Sie keine Anmelde Informationen angeben.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-181">If this option is not set, then you cannot specify any credentials.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-182">-ProxyType</span><span class="sxs-lookup"><span data-stu-id="a6bcf-182">-ProxyType</span></span>

<span data-ttu-id="a6bcf-183">Gibt den zu verwendenden Mechanismus zur Auflösung des Host namens an.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-183">Specifies the host name resolution mechanism to use.</span></span> <span data-ttu-id="a6bcf-184">Die zulässigen Werte für diesen Parameter lauten: **None** , **WinHTTP** , **Auto** oder **InternetExplorer** .</span><span class="sxs-lookup"><span data-stu-id="a6bcf-184">The acceptable values for this parameter are: **None** , **WinHttp** , **Auto** , or **InternetExplorer** .</span></span>

<span data-ttu-id="a6bcf-185">Der Standardwert dieses Parameters ist " **InternetExplorer** ".</span><span class="sxs-lookup"><span data-stu-id="a6bcf-185">The default value of this parameter is **InternetExplorer** .</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.ProxyType
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: None, WinHttp, Auto, InternetExplorer

Required: False
Position: Named
Default value: InternetExplorer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-186">-Skipcacheck</span><span class="sxs-lookup"><span data-stu-id="a6bcf-186">-SkipCACheck</span></span>

<span data-ttu-id="a6bcf-187">Gibt an, dass der Client beim Herstellen einer Verbindung über HTTPS nicht überprüft, ob das Serverzertifikat von einer vertrauenswürdigen Zertifizierungsstelle (Certification Authority, ca) signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-187">Indicates that when connecting over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>

<span data-ttu-id="a6bcf-188">Verwenden Sie diesen Parameter nur, wenn der Remote Computer mit einem anderen Mechanismus vertraut ist, z. b. wenn der Remote Computer Teil eines physisch sicheren und isolierten Netzwerks ist oder wenn der Remote Computer in einer WinRM-Konfiguration als vertrauenswürdiger Host aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-188">Use this parameter only when the remote computer is trusted using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated, or when the remote computer is listed as a trusted host in a WinRM configuration.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-189">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="a6bcf-189">-SkipCNCheck</span></span>

<span data-ttu-id="a6bcf-190">Gibt an, dass der allgemeine Name des Zertifikats (Common Name, CN) des Servers nicht mit dem Hostnamen des Servers identisch sein muss.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-190">Indicates that the certificate common name (CN) of the server does not need to match the hostname of the server.</span></span> <span data-ttu-id="a6bcf-191">Verwenden Sie diesen Parameter nur für Remote Vorgänge mit vertrauenswürdigen Computern, die das HTTPS-Protokoll verwenden.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-191">Use this parameter for remote operations only with trusted computers that use the HTTPS protocol.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-192">-Skiprevocationcheck</span><span class="sxs-lookup"><span data-stu-id="a6bcf-192">-SkipRevocationCheck</span></span>

<span data-ttu-id="a6bcf-193">Gibt an, dass die Sperr Überprüfung für Server Zertifikate übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-193">Indicates that the revocation check for server certificates is skipped.</span></span> <span data-ttu-id="a6bcf-194">Verwenden Sie diesen Parameter nur für vertrauenswürdige Computer.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-194">Use this parameter only for trusted computers.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-195">-UICulture</span><span class="sxs-lookup"><span data-stu-id="a6bcf-195">-UICulture</span></span>

<span data-ttu-id="a6bcf-196">Gibt die Kultur der Benutzeroberfläche an, die für die CIM-Sitzung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-196">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="a6bcf-197">Geben Sie den Wert für diesen Parameter in einem der folgenden Formate an:</span><span class="sxs-lookup"><span data-stu-id="a6bcf-197">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="a6bcf-198">Ein Kultur Name im `<languagecode2>-<country/regioncode2>` Format, z. b. "en-US".</span><span class="sxs-lookup"><span data-stu-id="a6bcf-198">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="a6bcf-199">Eine Variable, die ein CultureInfo-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-199">A variable that contains a CultureInfo object.</span></span>
- <span data-ttu-id="a6bcf-200">Ein Befehl, der ein CultureInfo-Objekt abruft, z `Get-Culture` . b..</span><span class="sxs-lookup"><span data-stu-id="a6bcf-200">A command that gets a CultureInfo object, such as `Get-Culture`.</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-201">-US-</span><span class="sxs-lookup"><span data-stu-id="a6bcf-201">-UseSsl</span></span>

<span data-ttu-id="a6bcf-202">Gibt an, dass SSL verwendet werden soll, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-202">Indicates that SSL should be used to establish a connection to the remote computer.</span></span> <span data-ttu-id="a6bcf-203">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-203">By default, SSL is not used.</span></span> <span data-ttu-id="a6bcf-204">WSMAN verschlüsselt alle Inhalte, die über das Netzwerk übertragen werden, selbst dann, wenn http verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-204">WsMan encrypts all content that is transmitted over the network, even when using HTTP.</span></span>

<span data-ttu-id="a6bcf-205">Mit diesem Parameter können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-205">This parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="a6bcf-206">Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-206">If SSL is not available on the port used for the connection and you specify this parameter, then the command fails.</span></span>

<span data-ttu-id="a6bcf-207">Es wird empfohlen, diesen Parameter nur dann zu verwenden, wenn der **PacketPrivacy** -Parameter nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-207">It is recommended that you use this parameter only when the **PacketPrivacy** parameter is not specified.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6bcf-208">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a6bcf-208">CommonParameters</span></span>

<span data-ttu-id="a6bcf-209">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-209">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a6bcf-210">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a6bcf-210">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a6bcf-211">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a6bcf-211">INPUTS</span></span>

### <span data-ttu-id="a6bcf-212">Keine</span><span class="sxs-lookup"><span data-stu-id="a6bcf-212">None</span></span>

<span data-ttu-id="a6bcf-213">Dieses Cmdlet akzeptiert keine Eingabe Objekte.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-213">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="a6bcf-214">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a6bcf-214">OUTPUTS</span></span>

### <span data-ttu-id="a6bcf-215">Cimsessionoption</span><span class="sxs-lookup"><span data-stu-id="a6bcf-215">CIMSessionOption</span></span>

<span data-ttu-id="a6bcf-216">Dieses Cmdlet gibt ein Objekt zurück, das CIM-Sitzungs Options Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="a6bcf-216">This cmdlet returns an object that contains CIM session options information.</span></span>

## <span data-ttu-id="a6bcf-217">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a6bcf-217">NOTES</span></span>

## <span data-ttu-id="a6bcf-218">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a6bcf-218">RELATED LINKS</span></span>

[<span data-ttu-id="a6bcf-219">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="a6bcf-219">Get-ChildItem</span></span>](../microsoft.powershell.management/get-childitem.md)

[<span data-ttu-id="a6bcf-220">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="a6bcf-220">Get-Credential</span></span>](../microsoft.powershell.security/get-credential.md)

[<span data-ttu-id="a6bcf-221">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="a6bcf-221">Get-Culture</span></span>](../microsoft.powershell.utility/get-culture.md)

[<span data-ttu-id="a6bcf-222">Get-Item</span><span class="sxs-lookup"><span data-stu-id="a6bcf-222">Get-Item</span></span>](../microsoft.powershell.management/get-item.md)

[<span data-ttu-id="a6bcf-223">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="a6bcf-223">New-CimSession</span></span>](New-CimSession.md)
