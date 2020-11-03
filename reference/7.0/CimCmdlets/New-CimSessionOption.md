---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsessionoption?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSessionOption
ms.openlocfilehash: 113652e3166f36e20106d3d60578069a32e2ab66
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209780"
---
# New-CimSessionOption

## ZUSAMMENFASSUNG
Gibt erweiterte Optionen für das New-CimSession-Cmdlet an.

## SYNTAX

### Protocoltypeset (Standard)

```
New-CimSessionOption [-Protocol] <ProtocolType> [-UICulture <CultureInfo>] [-Culture <CultureInfo>]
 [<CommonParameters>]
```

### Wsmanparameterset

```
New-CimSessionOption [-NoEncryption] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-EncodePortInServicePrincipalName] [-Encoding <PacketEncoding>] [-HttpPrefix <Uri>]
 [-MaxEnvelopeSizeKB <UInt32>] [-ProxyAuthentication <PasswordAuthenticationMechanism>]
 [-ProxyCertificateThumbprint <String>] [-ProxyCredential <PSCredential>] [-ProxyType <ProxyType>]
 [-UseSsl] [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

### Dcomparameterset

```
New-CimSessionOption [-Impersonation <ImpersonationType>] [-PacketIntegrity] [-PacketPrivacy]
 [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

## DESCRIPTION

Das- `New-CimSessionOption` Cmdlet erstellt eine Instanz eines CIM-Sitzungs Options-Objekts. Sie verwenden ein CIM-Sitzungs Options Objekt als Eingabe für das `New-CimSession` Cmdlet, um die Optionen für eine CIM-Sitzung anzugeben.

Dieses Cmdlet verfügt über zwei Parametersätze: einen für WSMAN-Optionen und einen für DCOM-Optionen (verteiltes Component Object Model). Abhängig von den Parametern, die Sie verwenden, gibt das Cmdlet entweder eine Instanz der DCOM-Sitzungs Optionen zurück oder gibt WSMAN-Sitzungs Optionen zurück.

## BEISPIELE

### Beispiel 1: Erstellen eines CIM-Sitzungs Options Objekts für DCOM

In diesem Beispiel wird ein CIM-Sitzungs Options-Objekt für das DCOM-Protokoll erstellt und in einer Variablen mit dem Namen gespeichert `$so` . Der Inhalt der Variablen wird dann an das `New-CimSession` Cmdlet übergeben.
`New-CimSession` Anschließend wird eine neue CIM-Sitzung mit dem Remote Server mit dem Namen Server01 erstellt, wobei die in der Variablen definierten Optionen verwendet werden.

```powershell
$so = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server01 -SessionOption $so
```

### Beispiel 2: Erstellen eines CIM-Sitzungs Options-Objekts für WSMAN

In diesem Beispiel wird ein CIM-Sitzungs Options-Objekt für das WSMAN-Protokoll erstellt. Das-Objekt enthält die Konfiguration für den Authentifizierungsmodus von **Kerberos** , der durch den **Proxyauthentication** -Parameter angegeben wird, die vom **proxycredential** -Parameter angegebenen Anmelde Informationen und gibt an, dass der Befehl die Überprüfung der Zertifizierungsstelle überspringt, die CN-Überprüfung überspringt und SSL verwendet.

```powershell
New-CimSessionOption -ProxyAuthentication Kerberos -ProxyCredential $cred -SkipCACheck -SkipCNCheck -UseSsl
```

### Beispiel 3: Erstellen eines CIM-Sitzungs Options Objekts mit der angegebenen Kultur

```powershell
New-CimSessionOption -Culture Fr-Fr -Protocol Wsman
```

In diesem Beispiel wird die Kultur angegeben, die für die CIM-Sitzung verwendet wird. Standardmäßig wird die Kultur des Clients beim Ausführen von Vorgängen verwendet. Die Standard Kultur kann jedoch mit dem **Culture** -Parameter überschrieben werden.

## PARAMETERS

### -Kultur

Gibt die Kultur der Benutzeroberfläche an, die für die CIM-Sitzung verwendet werden soll. Geben Sie den Wert für diesen Parameter in einem der folgenden Formate an:

- Ein Kultur Name im `<languagecode2>-<country/regioncode2>` Format, z. b. "en-US".
- Eine Variable, die ein **CultureInfo** -Objekt enthält.
- Ein Befehl, der ein **CultureInfo** -Objekt abruft, z. b. " [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md) "

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

### -Encodeportinserviceprincipalname

Gibt an, dass die Kerberos-Verbindung eine Verbindung mit einem Dienst herstellt, dessen Dienst Prinzipal Name (SPN) die Dienst Portnummer enthält. Dieser Verbindungstyp ist nicht üblich.

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

### -Codierung

Gibt die für das WSMAN-Protokoll verwendete Codierung an. Die zulässigen Werte für diesen Parameter sind: **default** , **UTF8** oder **Utf16** .

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

### -Httpprefix

Gibt den Teil der http-URL nach dem Computernamen und der Portnummer an. Das Ändern dieser Änderung ist nicht üblich. Standardmäßig ist der Wert dieses Parameters **/WSMAN** .

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

### -Identitätswechsel

Erstellt eine DCOM-Sitzung zum Windows-Verwaltungsinstrumentation (WMI) mithilfe des Identitäts Wechsels.

Gültige Parameterwerte:

- Standard: DCOM kann die Identitätswechsel Ebene mithilfe des normalen sicherheitsaushandlungs Algorithmus auswählen.
- None: der Client ist für den Server anonym. Der Server Prozess kann die Identität des Clients annehmen, das Identitätswechsel Token enthält jedoch keine Informationen und kann nicht verwendet werden.
- Identifizieren: ermöglicht es Objekten, die Anmelde Informationen des Aufrufers abzufragen.
- Identität annehmen: ermöglicht es Objekten, die Anmelde Informationen des Aufrufers zu verwenden.
- Delegat: ermöglicht es Objekten, anderen Objekten die Verwendung der Anmelde Informationen des Aufrufers zu gestatten.

Wenn **der** Identitätswechsel nicht angegeben wird, `New-CimSession` verwendet das Cmdlet den Wert **Impersonate** von Identitätswechsel.

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

### -Maxenvelopesizekb

Gibt die Größenbeschränkung von WSMAN-XML-Nachrichten für beide Richtungen an.

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

### -NoEncryption

Gibt an, dass die Datenverschlüsselung deaktiviert ist.

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

### -Packetintegrity

Gibt an, dass die für WMI erstellte DCOM-Sitzung die Component Object Model (com) _packetintegrity_ -Funktionalität verwendet. Standardmäßig wird für alle mit DCOM erstellten CIM-Sitzungen der **packetintegrity** -Parameter auf **true** festgelegt.

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

### -PacketPrivacy

Erstellt eine DCOM-Sitzung mit WMI mithilfe von com _PacketPrivacy_ . Standardmäßig wird für alle mit DCOM erstellten CIM-Sitzungen der **PacketPrivacy** -Parameter auf **true** festgelegt.

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

### -Protocol

Gibt das zu verwendende Protokoll an. Die zulässigen Werte für diesen Parameter sind: **DCOM** , **default** oder **WSMAN** .

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

### -Proxy Authentifizierung

Gibt die Authentifizierungsmethode an, die für die Proxy Auflösung verwendet werden soll. Die zulässigen Werte für diesen Parameter sind: **default** , **Digest** , **Aushandlungs** , **Basic** , **Kerberos** , **ntlmdomain** oder **kredssp** .

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

### -Proxycertifipaethumschlag Print

Gibt das digitale Zertifikat für öffentliche Schlüssel (x. 509) eines Benutzerkontos für die Proxy Authentifizierung an.
Geben Sie den Zertifikatfingerabdruck des Zertifikats ein. Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet. Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänen Konten.

Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie `Get-Item` die `Get-ChildItem` Cmdlets oder im PowerShell-Laufwerk "CERT:".

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

### -Proxy Credential

Gibt die Anmeldeinformationen an, die für die Proxyauthentifizierung verwendet werden sollen. Geben Sie eine der folgenden Informationen an:

- Eine Variable, die ein PSCredential-Objekt enthält.
- Ein Befehl, der ein PSCredential-Objekt abruft, z. b. `Get-Credential`

Wenn diese Option nicht festgelegt ist, können Sie keine Anmelde Informationen angeben.

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

### -ProxyType

Gibt den zu verwendenden Mechanismus zur Auflösung des Host namens an. Die zulässigen Werte für diesen Parameter lauten: **None** , **WinHTTP** , **Auto** oder **InternetExplorer** .

Der Standardwert dieses Parameters ist " **InternetExplorer** ".

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

### -Skipcacheck

Gibt an, dass der Client beim Herstellen einer Verbindung über HTTPS nicht überprüft, ob das Serverzertifikat von einer vertrauenswürdigen Zertifizierungsstelle (Certification Authority, ca) signiert wurde.

Verwenden Sie diesen Parameter nur, wenn der Remote Computer mit einem anderen Mechanismus vertraut ist, z. b. wenn der Remote Computer Teil eines physisch sicheren und isolierten Netzwerks ist oder wenn der Remote Computer in einer WinRM-Konfiguration als vertrauenswürdiger Host aufgeführt ist.

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

### -SkipCNCheck

Gibt an, dass der allgemeine Name des Zertifikats (Common Name, CN) des Servers nicht mit dem Hostnamen des Servers identisch sein muss. Verwenden Sie diesen Parameter nur für Remote Vorgänge mit vertrauenswürdigen Computern, die das HTTPS-Protokoll verwenden.

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

### -Skiprevocationcheck

Gibt an, dass die Sperr Überprüfung für Server Zertifikate übersprungen wird. Verwenden Sie diesen Parameter nur für vertrauenswürdige Computer.

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

### -UICulture

Gibt die Kultur der Benutzeroberfläche an, die für die CIM-Sitzung verwendet werden soll. Geben Sie den Wert für diesen Parameter in einem der folgenden Formate an:

- Ein Kultur Name im `<languagecode2>-<country/regioncode2>` Format, z. b. "en-US".
- Eine Variable, die ein CultureInfo-Objekt enthält.
- Ein Befehl, der ein CultureInfo-Objekt abruft, z `Get-Culture` . b..

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

### -US-

Gibt an, dass SSL verwendet werden soll, um eine Verbindung mit dem Remote Computer herzustellen. Standardmäßig wird SSL nicht verwendet. WSMAN verschlüsselt alle Inhalte, die über das Netzwerk übertragen werden, selbst dann, wenn http verwendet wird.

Mit diesem Parameter können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben. Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, schlägt der Befehl fehl.

Es wird empfohlen, diesen Parameter nur dann zu verwenden, wenn der **PacketPrivacy** -Parameter nicht angegeben ist.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Dieses Cmdlet akzeptiert keine Eingabe Objekte.

## AUSGABEN

### Cimsessionoption

Dieses Cmdlet gibt ein Objekt zurück, das CIM-Sitzungs Options Informationen enthält.

## HINWEISE

## VERWANDTE LINKS

[Get-ChildItem](../microsoft.powershell.management/get-childitem.md)

[Get-Credential](../microsoft.powershell.security/get-credential.md)

[Get-Culture](../microsoft.powershell.utility/get-culture.md)

[Get-Item](../microsoft.powershell.management/get-item.md)

[New-CimSession](New-CimSession.md)
