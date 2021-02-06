---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsessionoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSessionOption
ms.openlocfilehash: 54a2ca8a28d54bfe1d9676acdaace4592f62620f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598190"
---
# <span data-ttu-id="4126a-102">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="4126a-102">New-CimSessionOption</span></span>

## <span data-ttu-id="4126a-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4126a-103">SYNOPSIS</span></span>
<span data-ttu-id="4126a-104">Gibt erweiterte Optionen für das New-CimSession-Cmdlet an.</span><span class="sxs-lookup"><span data-stu-id="4126a-104">Specifies advanced options for the New-CimSession cmdlet.</span></span>

## <span data-ttu-id="4126a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4126a-105">SYNTAX</span></span>

### <span data-ttu-id="4126a-106">Protocoltypeset (Standard)</span><span class="sxs-lookup"><span data-stu-id="4126a-106">ProtocolTypeSet (Default)</span></span>

```
New-CimSessionOption [-Protocol] <ProtocolType> [-UICulture <CultureInfo>] [-Culture <CultureInfo>]
 [<CommonParameters>]
```

### <span data-ttu-id="4126a-107">Wsmanparameterset</span><span class="sxs-lookup"><span data-stu-id="4126a-107">WSManParameterSet</span></span>

```
New-CimSessionOption [-NoEncryption] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-EncodePortInServicePrincipalName] [-Encoding <PacketEncoding>] [-HttpPrefix <Uri>]
 [-MaxEnvelopeSizeKB <UInt32>] [-ProxyAuthentication <PasswordAuthenticationMechanism>]
 [-ProxyCertificateThumbprint <String>] [-ProxyCredential <PSCredential>] [-ProxyType <ProxyType>]
 [-UseSsl] [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

### <span data-ttu-id="4126a-108">Dcomparameterset</span><span class="sxs-lookup"><span data-stu-id="4126a-108">DcomParameterSet</span></span>

```
New-CimSessionOption [-Impersonation <ImpersonationType>] [-PacketIntegrity] [-PacketPrivacy]
 [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

## <span data-ttu-id="4126a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4126a-109">DESCRIPTION</span></span>

<span data-ttu-id="4126a-110">Das- `New-CimSessionOption` Cmdlet erstellt eine Instanz eines CIM-Sitzungs Options-Objekts.</span><span class="sxs-lookup"><span data-stu-id="4126a-110">The `New-CimSessionOption` cmdlet creates an instance of a CIM session options object.</span></span> <span data-ttu-id="4126a-111">Sie verwenden ein CIM-Sitzungs Options Objekt als Eingabe für das `New-CimSession` Cmdlet, um die Optionen für eine CIM-Sitzung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4126a-111">You use a CIM session options object as input to the `New-CimSession` cmdlet to specify the options for a CIM session.</span></span>

<span data-ttu-id="4126a-112">Dieses Cmdlet verfügt über zwei Parametersätze: einen für WSMAN-Optionen und einen für DCOM-Optionen (verteiltes Component Object Model).</span><span class="sxs-lookup"><span data-stu-id="4126a-112">This cmdlet has two parameter sets, one for WsMan options and one for Distributed Component Object Model (DCOM) options.</span></span> <span data-ttu-id="4126a-113">Abhängig von den Parametern, die Sie verwenden, gibt das Cmdlet entweder eine Instanz der DCOM-Sitzungs Optionen zurück oder gibt WSMAN-Sitzungs Optionen zurück.</span><span class="sxs-lookup"><span data-stu-id="4126a-113">Depending on which parameters you use, the cmdlet returns either an instance of DCOM session options or returns WsMan session options.</span></span>

## <span data-ttu-id="4126a-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4126a-114">EXAMPLES</span></span>

### <span data-ttu-id="4126a-115">Beispiel 1: Erstellen eines CIM-Sitzungs Options Objekts für DCOM</span><span class="sxs-lookup"><span data-stu-id="4126a-115">Example 1: Create a CIM session options object for DCOM</span></span>

<span data-ttu-id="4126a-116">In diesem Beispiel wird ein CIM-Sitzungs Options-Objekt für das DCOM-Protokoll erstellt und in einer Variablen mit dem Namen gespeichert `$so` .</span><span class="sxs-lookup"><span data-stu-id="4126a-116">This example creates a CIM session options object for the DCOM protocol and stores it in a variable named `$so`.</span></span> <span data-ttu-id="4126a-117">Der Inhalt der Variablen wird dann an das `New-CimSession` Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="4126a-117">The contents of the variable are then passed to the `New-CimSession` cmdlet.</span></span>
<span data-ttu-id="4126a-118">`New-CimSession` Anschließend wird eine neue CIM-Sitzung mit dem Remote Server mit dem Namen Server01 erstellt, wobei die in der Variablen definierten Optionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4126a-118">`New-CimSession` then creates a new CIM session with the remote server named Server01, using the options defined in the variable.</span></span>

```powershell
$so = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server01 -SessionOption $so
```

### <span data-ttu-id="4126a-119">Beispiel 2: Erstellen eines CIM-Sitzungs Options-Objekts für WSMAN</span><span class="sxs-lookup"><span data-stu-id="4126a-119">Example 2: Create a CIM session options object for WsMan</span></span>

<span data-ttu-id="4126a-120">In diesem Beispiel wird ein CIM-Sitzungs Options-Objekt für das WSMAN-Protokoll erstellt.</span><span class="sxs-lookup"><span data-stu-id="4126a-120">This example creates a CIM session options object for the WsMan protocol.</span></span> <span data-ttu-id="4126a-121">Das-Objekt enthält die Konfiguration für den Authentifizierungsmodus von **Kerberos** , der durch den **Proxyauthentication** -Parameter angegeben wird, die vom **proxycredential** -Parameter angegebenen Anmelde Informationen und gibt an, dass der Befehl die Überprüfung der Zertifizierungsstelle überspringt, die CN-Überprüfung überspringt und SSL verwendet.</span><span class="sxs-lookup"><span data-stu-id="4126a-121">The object contains configuration for the authentication mode of **Kerberos** specified by the **ProxyAuthentication** parameter, the credentials specified by the **ProxyCredential** parameter, and specifies that the command is to skip the CA check, skip the CN check, and use SSL.</span></span>

```powershell
New-CimSessionOption -ProxyAuthentication Kerberos -ProxyCredential $cred -SkipCACheck -SkipCNCheck -UseSsl
```

### <span data-ttu-id="4126a-122">Beispiel 3: Erstellen eines CIM-Sitzungs Options Objekts mit der angegebenen Kultur</span><span class="sxs-lookup"><span data-stu-id="4126a-122">Example 3: Create a CIM session options object with the culture specified</span></span>

```powershell
New-CimSessionOption -Culture Fr-Fr -Protocol Wsman
```

<span data-ttu-id="4126a-123">In diesem Beispiel wird die Kultur angegeben, die für die CIM-Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4126a-123">This example specifies the culture that is used for the CIM session.</span></span> <span data-ttu-id="4126a-124">Standardmäßig wird die Kultur des Clients beim Ausführen von Vorgängen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4126a-124">By default, the culture of the client is used when performing operations.</span></span> <span data-ttu-id="4126a-125">Die Standard Kultur kann jedoch mit dem **Culture** -Parameter überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="4126a-125">However, the default culture can be overridden using the **Culture** parameter.</span></span>

## <span data-ttu-id="4126a-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4126a-126">PARAMETERS</span></span>

### <span data-ttu-id="4126a-127">-Kultur</span><span class="sxs-lookup"><span data-stu-id="4126a-127">-Culture</span></span>

<span data-ttu-id="4126a-128">Gibt die Kultur der Benutzeroberfläche an, die für die CIM-Sitzung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4126a-128">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="4126a-129">Geben Sie den Wert für diesen Parameter in einem der folgenden Formate an:</span><span class="sxs-lookup"><span data-stu-id="4126a-129">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="4126a-130">Ein Kultur Name im `<languagecode2>-<country/regioncode2>` Format, z. b. "en-US".</span><span class="sxs-lookup"><span data-stu-id="4126a-130">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="4126a-131">Eine Variable, die ein **CultureInfo** -Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="4126a-131">A variable that contains a **CultureInfo** object.</span></span>
- <span data-ttu-id="4126a-132">Ein Befehl, der ein **CultureInfo** -Objekt abruft, z. b. " [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md) "</span><span class="sxs-lookup"><span data-stu-id="4126a-132">A command that gets a **CultureInfo** object, such as [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)</span></span>

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

### <span data-ttu-id="4126a-133">-Encodeportinserviceprincipalname</span><span class="sxs-lookup"><span data-stu-id="4126a-133">-EncodePortInServicePrincipalName</span></span>

<span data-ttu-id="4126a-134">Gibt an, dass die Kerberos-Verbindung eine Verbindung mit einem Dienst herstellt, dessen Dienst Prinzipal Name (SPN) die Dienst Portnummer enthält.</span><span class="sxs-lookup"><span data-stu-id="4126a-134">Indicates that the Kerberos connection is connecting to a service whose service principal name (SPN) includes the service port number.</span></span> <span data-ttu-id="4126a-135">Dieser Verbindungstyp ist nicht üblich.</span><span class="sxs-lookup"><span data-stu-id="4126a-135">This type of connection is not common.</span></span>

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

### <span data-ttu-id="4126a-136">-Codierung</span><span class="sxs-lookup"><span data-stu-id="4126a-136">-Encoding</span></span>

<span data-ttu-id="4126a-137">Gibt die für das WSMAN-Protokoll verwendete Codierung an.</span><span class="sxs-lookup"><span data-stu-id="4126a-137">Specifies the encoding used for the WsMan protocol.</span></span> <span data-ttu-id="4126a-138">Die zulässigen Werte für diesen Parameter sind: **default**, **UTF8** oder **Utf16**.</span><span class="sxs-lookup"><span data-stu-id="4126a-138">The acceptable values for this parameter are: **Default**, **Utf8**, or **Utf16**.</span></span>

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

### <span data-ttu-id="4126a-139">-Httpprefix</span><span class="sxs-lookup"><span data-stu-id="4126a-139">-HttpPrefix</span></span>

<span data-ttu-id="4126a-140">Gibt den Teil der http-URL nach dem Computernamen und der Portnummer an.</span><span class="sxs-lookup"><span data-stu-id="4126a-140">Specifies the part of the HTTP URL after the computer name and port number.</span></span> <span data-ttu-id="4126a-141">Das Ändern dieser Änderung ist nicht üblich.</span><span class="sxs-lookup"><span data-stu-id="4126a-141">Changing this is not common.</span></span> <span data-ttu-id="4126a-142">Standardmäßig ist der Wert dieses Parameters **/WSMAN**.</span><span class="sxs-lookup"><span data-stu-id="4126a-142">By default, the value of this parameter is **/wsman**.</span></span>

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

### <span data-ttu-id="4126a-143">-Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="4126a-143">-Impersonation</span></span>

<span data-ttu-id="4126a-144">Erstellt eine DCOM-Sitzung zum Windows-Verwaltungsinstrumentation (WMI) mithilfe des Identitäts Wechsels.</span><span class="sxs-lookup"><span data-stu-id="4126a-144">Creates a DCOM session to Windows Management Instrumentation (WMI) using impersonation.</span></span>

<span data-ttu-id="4126a-145">Gültige Parameterwerte:</span><span class="sxs-lookup"><span data-stu-id="4126a-145">Valid values for this parameter are:</span></span>

- <span data-ttu-id="4126a-146">Standard: DCOM kann die Identitätswechsel Ebene mithilfe des normalen sicherheitsaushandlungs Algorithmus auswählen.</span><span class="sxs-lookup"><span data-stu-id="4126a-146">Default: DCOM can choose the impersonation level using its normal security negotiation algorithm.</span></span>
- <span data-ttu-id="4126a-147">None: der Client ist für den Server anonym.</span><span class="sxs-lookup"><span data-stu-id="4126a-147">None: The client is anonymous to the server.</span></span> <span data-ttu-id="4126a-148">Der Server Prozess kann die Identität des Clients annehmen, das Identitätswechsel Token enthält jedoch keine Informationen und kann nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4126a-148">The server process can impersonate the client, but the impersonation token does not contain any information and cannot be used.</span></span>
- <span data-ttu-id="4126a-149">Identifizieren: ermöglicht es Objekten, die Anmelde Informationen des Aufrufers abzufragen.</span><span class="sxs-lookup"><span data-stu-id="4126a-149">Identify: Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="4126a-150">Identität annehmen: ermöglicht es Objekten, die Anmelde Informationen des Aufrufers zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4126a-150">Impersonate: Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="4126a-151">Delegat: ermöglicht es Objekten, anderen Objekten die Verwendung der Anmelde Informationen des Aufrufers zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="4126a-151">Delegate: Allows objects to permit other objects to use the credentials of the caller.</span></span>

<span data-ttu-id="4126a-152">Wenn **der** Identitätswechsel nicht angegeben wird, `New-CimSession` verwendet das Cmdlet den Wert von Identitätswechsel.</span><span class="sxs-lookup"><span data-stu-id="4126a-152">If **Impersonation** is not specified, the `New-CimSession` cmdlet uses the value of **Impersonate**.</span></span>

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

### <span data-ttu-id="4126a-153">-Maxenvelopesizekb</span><span class="sxs-lookup"><span data-stu-id="4126a-153">-MaxEnvelopeSizeKB</span></span>

<span data-ttu-id="4126a-154">Gibt die Größenbeschränkung von WSMAN-XML-Nachrichten für beide Richtungen an.</span><span class="sxs-lookup"><span data-stu-id="4126a-154">Specifies the size limit of WsMan XML messages for either direction.</span></span>

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

### <span data-ttu-id="4126a-155">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="4126a-155">-NoEncryption</span></span>

<span data-ttu-id="4126a-156">Gibt an, dass die Datenverschlüsselung deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4126a-156">Specifies that data encryption is turned off.</span></span>

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

### <span data-ttu-id="4126a-157">-Packetintegrity</span><span class="sxs-lookup"><span data-stu-id="4126a-157">-PacketIntegrity</span></span>

<span data-ttu-id="4126a-158">Gibt an, dass die für WMI erstellte DCOM-Sitzung die Component Object Model (com) _packetintegrity_ -Funktionalität verwendet.</span><span class="sxs-lookup"><span data-stu-id="4126a-158">Specifies that the DCOM session created to WMI uses the Component Object Model (COM) _PacketIntegrity_ functionality.</span></span> <span data-ttu-id="4126a-159">Standardmäßig wird für alle mit DCOM erstellten CIM-Sitzungen der **packetintegrity** -Parameter auf **true** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4126a-159">By default, all CIM sessions created using DCOM have the **PacketIntegrity** parameter set to **True**.</span></span>

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

### <span data-ttu-id="4126a-160">-PacketPrivacy</span><span class="sxs-lookup"><span data-stu-id="4126a-160">-PacketPrivacy</span></span>

<span data-ttu-id="4126a-161">Erstellt eine DCOM-Sitzung mit WMI mithilfe von com _PacketPrivacy_.</span><span class="sxs-lookup"><span data-stu-id="4126a-161">Creates a DCOM session to WMI using the COM _PacketPrivacy_.</span></span> <span data-ttu-id="4126a-162">Standardmäßig wird für alle mit DCOM erstellten CIM-Sitzungen der **PacketPrivacy** -Parameter auf **true** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4126a-162">By default, all CIM sessions created using DCOM have the **PacketPrivacy** parameter set to **true**.</span></span>

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

### <span data-ttu-id="4126a-163">-Protocol</span><span class="sxs-lookup"><span data-stu-id="4126a-163">-Protocol</span></span>

<span data-ttu-id="4126a-164">Gibt das zu verwendende Protokoll an.</span><span class="sxs-lookup"><span data-stu-id="4126a-164">Specifies the protocol to use.</span></span> <span data-ttu-id="4126a-165">Die zulässigen Werte für diesen Parameter sind: **DCOM**, **default** oder **WSMAN**.</span><span class="sxs-lookup"><span data-stu-id="4126a-165">The acceptable values for this parameter are: **DCOM**, **Default**, or **Wsman**.</span></span>

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

### <span data-ttu-id="4126a-166">-Proxy Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4126a-166">-ProxyAuthentication</span></span>

<span data-ttu-id="4126a-167">Gibt die Authentifizierungsmethode an, die für die Proxy Auflösung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4126a-167">Specifies the authentication method to use for proxy resolution.</span></span> <span data-ttu-id="4126a-168">Die zulässigen Werte für diesen Parameter sind: **default**, **Digest**, **Aushandlungs**, **Basic**, **Kerberos**, **ntlmdomain** oder **kredssp**.</span><span class="sxs-lookup"><span data-stu-id="4126a-168">The acceptable values for this parameter are: **Default**, **Digest**, **Negotiate**, **Basic**, **Kerberos**, **NtlmDomain**, or **CredSsp**.</span></span>

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

### <span data-ttu-id="4126a-169">-Proxycertifipaethumschlag Print</span><span class="sxs-lookup"><span data-stu-id="4126a-169">-ProxyCertificateThumbprint</span></span>

<span data-ttu-id="4126a-170">Gibt das digitale Zertifikat für öffentliche Schlüssel (x. 509) eines Benutzerkontos für die Proxy Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="4126a-170">Specifies the (x.509) digital public key certificate of a user account for proxy authentication.</span></span>
<span data-ttu-id="4126a-171">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="4126a-171">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="4126a-172">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="4126a-172">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="4126a-173">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänen Konten.</span><span class="sxs-lookup"><span data-stu-id="4126a-173">They can only be mapped to local user accounts and they do not work with domain accounts.</span></span>

<span data-ttu-id="4126a-174">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie `Get-Item` die `Get-ChildItem` Cmdlets oder im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="4126a-174">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="4126a-175">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="4126a-175">-ProxyCredential</span></span>

<span data-ttu-id="4126a-176">Gibt die Anmeldeinformationen an, die für die Proxyauthentifizierung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4126a-176">Specifies the credentials to use for proxy authentication.</span></span> <span data-ttu-id="4126a-177">Geben Sie eine der folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="4126a-177">Enter one of the following:</span></span>

- <span data-ttu-id="4126a-178">Eine Variable, die ein PSCredential-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="4126a-178">A variable that contains a PSCredential object.</span></span>
- <span data-ttu-id="4126a-179">Ein Befehl, der ein PSCredential-Objekt abruft, z. b. `Get-Credential`</span><span class="sxs-lookup"><span data-stu-id="4126a-179">A command that gets a PSCredential object, such as `Get-Credential`</span></span>

<span data-ttu-id="4126a-180">Wenn diese Option nicht festgelegt ist, können Sie keine Anmelde Informationen angeben.</span><span class="sxs-lookup"><span data-stu-id="4126a-180">If this option is not set, then you cannot specify any credentials.</span></span>

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

### <span data-ttu-id="4126a-181">-ProxyType</span><span class="sxs-lookup"><span data-stu-id="4126a-181">-ProxyType</span></span>

<span data-ttu-id="4126a-182">Gibt den zu verwendenden Mechanismus zur Auflösung des Host namens an.</span><span class="sxs-lookup"><span data-stu-id="4126a-182">Specifies the host name resolution mechanism to use.</span></span> <span data-ttu-id="4126a-183">Die zulässigen Werte für diesen Parameter lauten: **None**, **WinHTTP**, **Auto** oder **InternetExplorer**.</span><span class="sxs-lookup"><span data-stu-id="4126a-183">The acceptable values for this parameter are: **None**, **WinHttp**, **Auto**, or **InternetExplorer**.</span></span>

<span data-ttu-id="4126a-184">Der Standardwert dieses Parameters ist " **InternetExplorer**".</span><span class="sxs-lookup"><span data-stu-id="4126a-184">The default value of this parameter is **InternetExplorer**.</span></span>

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

### <span data-ttu-id="4126a-185">-Skipcacheck</span><span class="sxs-lookup"><span data-stu-id="4126a-185">-SkipCACheck</span></span>

<span data-ttu-id="4126a-186">Gibt an, dass der Client beim Herstellen einer Verbindung über HTTPS nicht überprüft, ob das Serverzertifikat von einer vertrauenswürdigen Zertifizierungsstelle (Certification Authority, ca) signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4126a-186">Indicates that when connecting over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>

<span data-ttu-id="4126a-187">Verwenden Sie diesen Parameter nur, wenn der Remote Computer mit einem anderen Mechanismus vertraut ist, z. b. wenn der Remote Computer Teil eines physisch sicheren und isolierten Netzwerks ist oder wenn der Remote Computer in einer WinRM-Konfiguration als vertrauenswürdiger Host aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="4126a-187">Use this parameter only when the remote computer is trusted using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated, or when the remote computer is listed as a trusted host in a WinRM configuration.</span></span>

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

### <span data-ttu-id="4126a-188">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="4126a-188">-SkipCNCheck</span></span>

<span data-ttu-id="4126a-189">Gibt an, dass der allgemeine Name des Zertifikats (Common Name, CN) des Servers nicht mit dem Hostnamen des Servers identisch sein muss.</span><span class="sxs-lookup"><span data-stu-id="4126a-189">Indicates that the certificate common name (CN) of the server does not need to match the hostname of the server.</span></span> <span data-ttu-id="4126a-190">Verwenden Sie diesen Parameter nur für Remote Vorgänge mit vertrauenswürdigen Computern, die das HTTPS-Protokoll verwenden.</span><span class="sxs-lookup"><span data-stu-id="4126a-190">Use this parameter for remote operations only with trusted computers that use the HTTPS protocol.</span></span>

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

### <span data-ttu-id="4126a-191">-Skiprevocationcheck</span><span class="sxs-lookup"><span data-stu-id="4126a-191">-SkipRevocationCheck</span></span>

<span data-ttu-id="4126a-192">Gibt an, dass die Sperr Überprüfung für Server Zertifikate übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="4126a-192">Indicates that the revocation check for server certificates is skipped.</span></span> <span data-ttu-id="4126a-193">Verwenden Sie diesen Parameter nur für vertrauenswürdige Computer.</span><span class="sxs-lookup"><span data-stu-id="4126a-193">Use this parameter only for trusted computers.</span></span>

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

### <span data-ttu-id="4126a-194">-UICulture</span><span class="sxs-lookup"><span data-stu-id="4126a-194">-UICulture</span></span>

<span data-ttu-id="4126a-195">Gibt die Kultur der Benutzeroberfläche an, die für die CIM-Sitzung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4126a-195">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="4126a-196">Geben Sie den Wert für diesen Parameter in einem der folgenden Formate an:</span><span class="sxs-lookup"><span data-stu-id="4126a-196">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="4126a-197">Ein Kultur Name im `<languagecode2>-<country/regioncode2>` Format, z. b. "en-US".</span><span class="sxs-lookup"><span data-stu-id="4126a-197">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="4126a-198">Eine Variable, die ein CultureInfo-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="4126a-198">A variable that contains a CultureInfo object.</span></span>
- <span data-ttu-id="4126a-199">Ein Befehl, der ein CultureInfo-Objekt abruft, z `Get-Culture` . b..</span><span class="sxs-lookup"><span data-stu-id="4126a-199">A command that gets a CultureInfo object, such as `Get-Culture`.</span></span>

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

### <span data-ttu-id="4126a-200">-US-</span><span class="sxs-lookup"><span data-stu-id="4126a-200">-UseSsl</span></span>

<span data-ttu-id="4126a-201">Gibt an, dass SSL verwendet werden soll, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4126a-201">Indicates that SSL should be used to establish a connection to the remote computer.</span></span> <span data-ttu-id="4126a-202">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="4126a-202">By default, SSL is not used.</span></span> <span data-ttu-id="4126a-203">WSMAN verschlüsselt alle Inhalte, die über das Netzwerk übertragen werden, selbst dann, wenn http verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4126a-203">WsMan encrypts all content that is transmitted over the network, even when using HTTP.</span></span>

<span data-ttu-id="4126a-204">Mit diesem Parameter können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.</span><span class="sxs-lookup"><span data-stu-id="4126a-204">This parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="4126a-205">Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="4126a-205">If SSL is not available on the port used for the connection and you specify this parameter, then the command fails.</span></span>

<span data-ttu-id="4126a-206">Es wird empfohlen, diesen Parameter nur dann zu verwenden, wenn der **PacketPrivacy** -Parameter nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="4126a-206">It is recommended that you use this parameter only when the **PacketPrivacy** parameter is not specified.</span></span>

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

### <span data-ttu-id="4126a-207">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4126a-207">CommonParameters</span></span>

<span data-ttu-id="4126a-208">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4126a-208">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4126a-209">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4126a-209">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4126a-210">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4126a-210">INPUTS</span></span>

### <span data-ttu-id="4126a-211">Keine</span><span class="sxs-lookup"><span data-stu-id="4126a-211">None</span></span>

<span data-ttu-id="4126a-212">Dieses Cmdlet akzeptiert keine Eingabe Objekte.</span><span class="sxs-lookup"><span data-stu-id="4126a-212">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="4126a-213">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4126a-213">OUTPUTS</span></span>

### <span data-ttu-id="4126a-214">Cimsessionoption</span><span class="sxs-lookup"><span data-stu-id="4126a-214">CIMSessionOption</span></span>

<span data-ttu-id="4126a-215">Dieses Cmdlet gibt ein Objekt zurück, das CIM-Sitzungs Options Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="4126a-215">This cmdlet returns an object that contains CIM session options information.</span></span>

## <span data-ttu-id="4126a-216">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4126a-216">NOTES</span></span>

## <span data-ttu-id="4126a-217">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4126a-217">RELATED LINKS</span></span>

[<span data-ttu-id="4126a-218">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="4126a-218">Get-ChildItem</span></span>](../microsoft.powershell.management/get-childitem.md)

[<span data-ttu-id="4126a-219">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="4126a-219">Get-Credential</span></span>](../microsoft.powershell.security/get-credential.md)

[<span data-ttu-id="4126a-220">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="4126a-220">Get-Culture</span></span>](../microsoft.powershell.utility/get-culture.md)

[<span data-ttu-id="4126a-221">Get-Item</span><span class="sxs-lookup"><span data-stu-id="4126a-221">Get-Item</span></span>](../microsoft.powershell.management/get-item.md)

[<span data-ttu-id="4126a-222">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="4126a-222">New-CimSession</span></span>](New-CimSession.md)

