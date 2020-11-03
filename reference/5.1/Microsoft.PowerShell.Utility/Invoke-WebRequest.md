---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: 25da6262e93be3e3749aabaf4950e2fbcd91ff5c
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219228"
---
# Invoke-WebRequest

## ZUSAMMENFASSUNG
Ruft Inhalte von einer Webseite im Internet ab.

## SYNTAX

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>] [-SessionVariable <String>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-CertificateThumbprint <String>]
 [-Certificate <X509Certificate>] [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>]
 [-Headers <IDictionary>] [-MaximumRedirection <Int32>] [-Method <WebRequestMethod>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>] [-ContentType <String>]
 [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

Das- `Invoke-WebRequest` Cmdlet sendet http-, HTTPS-, FTP-und File-Anforderungen an eine Webseite oder einen Webdienst.
Das Cmdlet analysiert die Antwort und gibt Auflistungen von Formularen, Links, Bildern und anderen wichtigen HTML-Elementen zurück.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

> [!NOTE]
> Standardmäßig kann der Skriptcode auf der Webseite ausgeführt werden, wenn die Seite analysiert wird, um die Eigenschaft aufzufüllen `ParsedHtml` .
> Verwenden Sie den- `-UseBasicParsing` Schalter, um dies zu unterdrücken.

## BEISPIELE

### Beispiel 1: Senden einer Webanforderung

Dieser Befehl verwendet das `Invoke-WebRequest` Cmdlet, um eine Webanforderung an die Bing.com-Website zu senden.

```powershell
$R = Invoke-WebRequest -URI https://www.bing.com?q=how+many+feet+in+a+mile
$R.AllElements | Where-Object {
    $_.name -like "* Value" -and $_.tagName -eq "INPUT"
} | Select-Object Name, Value
```

```Output
name       value
----       -----
From Value 1
To Value   5280
```

Der erste Befehl gibt die Anforderung aus und speichert die Antwort in der `$R` Variablen.

Mit dem zweiten Befehl werden die Objekte in der **AllElements** -Eigenschaft gefiltert, wobei die **Name** -Eigenschaft wie "* Value" und der **Tagname** "Input" lautet. Die gefilterten Ergebnisse werden an weitergeleitet `Select-Object` , um die Eigenschaften **Name** und **Wert** auszuwählen.

### Beispiel 2: Verwenden eines Zustands behafteten Webdiensts

In diesem Beispiel wird gezeigt, wie das `Invoke-WebRequest` Cmdlet mit einem Zustands behafteten Webdienst (z. b. Facebook) verwendet wird.

```powershell
$R = Invoke-WebRequest https://www.facebook.com/login.php -SessionVariable fb
# This command stores the first form in the Forms property of the $R variable in the $Form variable.
$Form = $R.Forms[0]
# This command shows the fields available in the Form.
$Form.fields
```

```Output
Key                     Value
---                     -----
...
email
pass
...
```

```powershell
# These commands populate the username and password of the respective Form fields.
$Form.Fields["email"]="User01@Fabrikam.com"
$Form.Fields["pass"]="P@ssw0rd"
# This command creates the Uri that will be used to log in to facebook.
# The value of the Uri parameter is the value of the Action property of the form.
$Uri = "https://www.facebook.com" + $Form.Action
# Now the Invoke-WebRequest cmdlet is used to sign into the Facebook web service.
# The WebRequestSession object in the $FB variable is passed as the value of the WebSession parameter.
# The value of the Body parameter is the hash table in the Fields property of the form.
# The value of the *Method* parameter is POST. The command saves the output in the $R variable.
$R = Invoke-WebRequest -Uri $Uri -WebSession $FB -Method POST -Body $Form.Fields
$R.StatusDescription
```

Der erste Befehl verwendet das `Invoke-WebRequest` Cmdlet, um eine Anmelde Anforderung zu senden. Der Befehl gibt den Wert "FB" für den Wert des **sessionvariable** -Parameters an und speichert das Ergebnis in der `$R` Variablen. Wenn der Befehl abgeschlossen ist, `$R` enthält die Variable ein **htmlwebresponseobject** , und die `$FB` Variable enthält ein **webrequestsession** -Objekt.

Nachdem sich das `Invoke-WebRequest` Cmdlet bei Facebook angemeldet hat, gibt die **Status Description** -Eigenschaft des WebResponse-Objekts in der `$R` Variablen an, dass der Benutzer erfolgreich angemeldet wurde.

### Beispiel 3: erhalten von Links von einer Webseite

Dieser Befehl ruft die Links auf einer Webseite ab.

```powershell
(Invoke-WebRequest -Uri "https://devblogs.microsoft.com/powershell/").Links.Href
```

Mit dem- `Invoke-WebRequest` Cmdlet wird der Webseiteninhalt abgerufen. Anschließend wird die Eigenschaft " **Links** " des zurückgegebenen **htmlwebresponseobject** verwendet, um die **href** -Eigenschaft der einzelnen Links anzuzeigen.

### Beispiel 4: Erfassen von nicht erfolgreichen Nachrichten aus Invoke-WebRequest

Wenn `Invoke-WebRequest` eine nicht Erfolgs-HTTP-Nachricht (404, 500 usw.) findet, wird keine Ausgabe zurückgegeben, und es wird ein Abbruch Fehler ausgelöst. Um den Fehler zu erfassen und den **Statuscode** anzuzeigen, können Sie die Ausführung in einen- `try/catch` Block einschließen. Im folgenden Beispiel wird gezeigt, wie dies erreicht wird.

```powershell
try
{
    $response = Invoke-WebRequest -Uri "www.microsoft.com/unkownhost" -ErrorAction Stop
    # This will only execute if the Invoke-WebRequest is successful.
    $StatusCode = $Response.StatusCode
}
catch
{
    $StatusCode = $_.Exception.Response.StatusCode.value__
}
$StatusCode
```

```Output
404
```

Der erste Befehl ruft `Invoke-WebRequest` mit der **ErrorAction-Aktion** " **Beenden** " auf, die erzwingt, `Invoke-WebRequest` bei allen fehlgeschlagenen Anforderungen einen Beendigungs Fehler auszulösen. Der abschließende Fehler wird durch den- `catch` Block abgefangen, der den **Statuscode** aus dem **Ausnahme** Objekt abruft.

## PARAMETERS

### -Text

Gibt den Anforderungstext an.
Der Text entspricht dem Inhalt der Anforderung, der auf die Header folgt.
Sie können einen Textwert auch über die Pipeline an senden `Invoke-WebRequest` .

Der **Body** -Parameter kann verwendet werden, um eine Liste von Abfrageparametern oder den Inhalt der Antwort anzugeben.

Wenn die Eingabe eine GET-Anforderung und der Text ein **IDictionary** (in der Regel eine Hash Tabelle) ist, wird der Text dem URI als Abfrage Parameter hinzugefügt. Bei anderen Get-Anforderungen wird der Text als Wert des Anforderungs Texts im Standardformat festgelegt `name=value` .

Wenn der Text ein Formular oder die Ausgabe eines- `Invoke-WebRequest` Aufrufes ist, legt PowerShell den Anforderungs Inhalt auf die Formularfelder fest.
Beispiel:

`$r = Invoke-WebRequest https://website.com/login.aspx`
`$r.Forms\[0\].Name = "MyName"`
`$r.Forms\[0\].Password = "MyPassword"`
`Invoke-RestMethod https://website.com/service.aspx -Body $r`

- ODER

`Invoke-RestMethod https://website.com/service.aspx -Body $r.Forms\[0\]`

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Zertifikat

Gibt das Clientzertifikat an, das für eine sichere Webanforderung verwendet wird. Geben Sie eine Variable ein, die ein Zertifikat, einen Befehl oder einen Ausdruck enthält, durch die das Zertifikat abgerufen wird.

Um ein Zertifikat zu suchen, verwenden Sie `Get-PfxCertificate` oder das- `Get-ChildItem` Cmdlet **Certificate** im Zertifikat `Cert:` Laufwerk (). Wenn das Zertifikat ungültig ist oder keine qualifizierte Zertifizierungsstelle aufweist, verursacht der Befehl einen Fehler.

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certifiupethumschlag-Print

Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Senden der Anforderung verfügt. Geben Sie den Zertifikatfingerabdruck des Zertifikats ein. Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet. Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.

Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den- `Get-Item` Befehl oder den- `Get-ChildItem` Befehl im PowerShell- `Cert:` Laufwerk.

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

### -ContentType

Gibt den Inhaltstyp der Webanforderung an.

Wenn dieser Parameter ausgelassen wird und die Anforderungs Methode Post ist, `Invoke-WebRequest` legt den Inhaltstyp auf application/x-www-form-urlencoded fest. Andernfalls wird der Inhaltstyp nicht im Aufruf angegeben.

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

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Senden der Anforderung verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disablekeepalive

Gibt an, dass mit dem Cmdlet der **KeepAlive** -Wert im HTTP-Header auf **false** festgelegt wird. Standardmäßig ist **KeepAlive** auf **true**. **KeepAlive** richtet eine persistente Verbindung mit dem Server ein, um nachfolgende Anforderungen zu erleichtern.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header

Gibt die Header der Webanforderung an. Geben Sie eine Hashtabelle oder ein Wörterbuch ein.

Verwenden Sie den **userAgent** -Parameter, um **userAgent** -Header festzulegen. Sie können diesen Parameter nicht verwenden, um **userAgent** -oder Cookie-Header anzugeben.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Eingabedatei

Ruft den Inhalt der Webanforderung aus einer Datei ab.

Geben Sie einen Pfad- und Dateinamen ein. Wenn Sie den Pfad weglassen, wird der aktuelle Speicherort als Standard verwendet.

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

### -Maximumredirect

Gibt an, wie oft PowerShell eine Verbindung an eine Alternative Uniform Resource Identifier (URI) umleitet, bevor die Verbindung fehlschlägt. Der Standardwert ist 5. Der Wert 0 (null) unterbindet sämtliche Umleitungen.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Methode

Gibt die für die Webanforderung verwendete Methode an. Zulässige Werte für diesen Parameter:

- Standard
- Löschen
- Herunterladen
- Head
- Merge
- Optionen
- Patch
- Posten
- Put
- Trace

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestMethod
Parameter Sets: (All)
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Outfile

Gibt die Ausgabedatei an, für die dieses Cmdlet den Antworttext speichert. Geben Sie einen Pfad- und Dateinamen ein.
Wenn Sie den Pfad weglassen, wird der aktuelle Speicherort als Standard verwendet.

Standardmäßig `Invoke-WebRequest` gibt die Ergebnisse an die Pipeline zurück. Verwenden Sie den **Passthru** -Parameter, um Ergebnisse an eine Datei und an die Pipeline zu senden.

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

### -PassThru

Gibt an, dass das Cmdlet zusätzlich zum Schreiben in eine Datei die Ergebnisse zurückgibt. Dieser Parameter ist nur gültig, wenn der **OutFile** -Parameter ebenfalls im Befehl verwendet wird.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxy

Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.
Geben Sie den URI des Netzwerk-Proxyservers ein.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxy Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy** -Parameter angegeben wird. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. `User01` oder `Domain01\User01` , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.

Dieser Parameter ist nur gültig, wenn der **Proxy** Parameter auch im Befehl verwendet wird. Der **ProxyCredential** -Parameter und der **ProxyUseDefaultCredentials** -Parameter können nicht im selben Befehl verwendet werden.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxyusedefault-Anmelde Informationen

Gibt an, dass das Cmdlet die Anmelde Informationen des aktuellen Benutzers verwendet, um auf den Proxy Server zuzugreifen, der durch den **Proxy** Parameter angegeben wird.

Dieser Parameter ist nur gültig, wenn der **Proxy** Parameter auch im Befehl verwendet wird. Der **ProxyCredential** -Parameter und der **ProxyUseDefaultCredentials** -Parameter können nicht im selben Befehl verwendet werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sessionvariable

Gibt eine Variable an, für die dieses Cmdlet eine Webanforderungs Sitzung erstellt und im Wert speichert.
Geben Sie einen Variablennamen ohne das Dollarzeichen `$` Symbol () ein.

Wenn Sie eine Sitzungs Variable angeben, `Invoke-WebRequest` erstellt ein Webanforderungs-Sitzungs Objekt und weist es einer Variablen mit dem angegebenen Namen in der PowerShell-Sitzung zu. Sie können die Variable in der Sitzung verwenden, sobald der Befehl abgeschlossen wurde.

Im Gegensatz zu einer Remotesitzung besteht bei der Webanforderungssitzung keine persistente Verbindung. Es handelt sich um ein Objekt, das Informationen über die Verbindung und die Anforderung enthält, einschließlich Cookies, Anmeldeinformationen, dem Maximalwert für Umleitungen und der Zeichenfolge des Benutzer-Agents. Sie können das Objekt verwenden, um den Zustand und die Daten übergreifend für Webanforderungen zu nutzen.

Um die Webanforderungssitzung in nachfolgenden Webanforderungen zu verwenden, geben Sie die Sitzungsvariable im Wert des **WebSession** -Parameters an. PowerShell verwendet die Daten im Sitzungs Objekt der Webanforderung, wenn die neue Verbindung hergestellt wird. Um einen Wert in der Webanforderungssitzung zu überschreiben, verwenden Sie einen Cmdletparameter wie **UserAgent** oder **Credential**. Parameterwerte haben Vorrang vor Werten in der Webanforderungssitzung.

Der **sessionvariable** -Parameter und der **websession** -Parameter können nicht im selben Befehl verwendet werden.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SV

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timeoutsec

Gibt an, wie lange die Anforderung ausstehend sein kann, bevor eine Zeitüberschreitung auftritt. Geben Sie einen Wert in Sekunden ein. Der Standardwert 0 (null) steht für einen unbegrenzten Zeitüberschreitungswert.

Eine Domain Name System (DNS)-Abfrage kann bis zu 15 Sekunden dauern, bis eine Rückgabe oder ein Timeout auftritt. Wenn Ihre Anforderung einen Hostnamen enthält, der aufgelöst werden muss, und Sie **timeoutsec** auf einen Wert größer als 0 (null), aber weniger als 15 Sekunden festlegen, kann es 15 Sekunden oder länger dauern, bis eine **WebException** ausgelöst wird und für Ihre Anforderung ein Timeout eintritt.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransferEncoding

Gibt einen Wert für den HTTP-Antwortheader transfer-encoding an. Zulässige Werte für diesen Parameter:

- Aufgeteilte
- Komprimieren
- Deflate
- GZip
- Identität

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: chunked, compress, deflate, gzip, identity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -URI

Gibt den URI (Uniform Resource Identifier) der Internetressource an, an die die Webanforderung gesendet wird. Geben Sie einen URI ein. Dieser Parameter unterstützt HTTP-, HTTPS-, FTP- und FILE-Werte.

Dieser Parameter ist erforderlich.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Usebasicparamesing

Gibt an, dass das Cmdlet das Antwortobjekt für HTML-Inhalt ohne Dokumentobjektmodell (DOM)-Verarbeitung verwendet. Dieser Parameter ist erforderlich, wenn Internet Explorer nicht auf den Computern installiert ist, wie z. B. im Falle einer Server Core-Installation eines Windows Server-Betriebssystems.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Usedefault-Anmelde Informationen

Gibt an, dass das cmdet die Anmelde Informationen des aktuellen Benutzers verwendet, um die Webanforderung zu senden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserAgent

Gibt eine Benutzer-Agent-Zeichenfolge für die Webanforderung an. Der Standard-Benutzer-Agent ähnelt `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` mit geringfügigen Abweichungen für die einzelnen Betriebssysteme und Plattformen.

Um eine Website mit der standardmäßigen Benutzer-Agent-Zeichenfolge zu testen, die von den meisten Internet Browsern verwendet wird, verwenden Sie die Eigenschaften der Klasse [psuseragent](/dotnet/api/microsoft.powershell.commands.psuseragent) , z. b. Chrome, Firefox, Internet Explorer, Opera und Safari. Der folgende Befehl verwendet z. b. die Benutzer-Agent-Zeichenfolge für Internet Explorer.

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

### -Websession

Gibt eine Webanforderungssitzung an. Geben Sie den Variablennamen einschließlich des Dollar Zeichens ( `$` ) ein.

Um einen Wert in der Webanforderungssitzung zu überschreiben, verwenden Sie einen Cmdletparameter wie **UserAgent** oder **Credential**. Parameterwerte haben Vorrang vor Werten in der Webanforderungssitzung.

Im Gegensatz zu einer Remotesitzung besteht bei der Webanforderungssitzung keine persistente Verbindung. Es handelt sich um ein Objekt, das Informationen über die Verbindung und die Anforderung enthält, einschließlich Cookies, Anmeldeinformationen, dem Maximalwert für Umleitungen und der Zeichenfolge des Benutzer-Agents. Sie können das Objekt verwenden, um den Zustand und die Daten übergreifend für Webanforderungen zu nutzen.

Um eine Webanforderungs Sitzung zu erstellen, geben Sie einen Variablennamen (ohne Dollarzeichen) in den Wert des **sessionvariable** -Parameters eines `Invoke-WebRequest` Befehls ein. `Invoke-WebRequest` erstellt die Sitzung und speichert Sie in der Variablen. In allen nachfolgenden Befehlen verwenden Sie die Variable als Wert für den **WebSession** -Parameter.

Der **sessionvariable** -Parameter und der **websession** -Parameter können nicht im selben Befehl verwendet werden.

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` . Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.Object

Sie können den Text einer Webanforderung an übergeben `Invoke-WebRequest` .

## AUSGABEN

### Microsoft.PowerShell.Commands.Htmlwebresponseobject

## HINWEISE

## VERWANDTE LINKS

[Invoke-RestMethod](Invoke-RestMethod.md)

[ConvertFrom-Json](ConvertFrom-Json.md)

[ConvertTo-Json](ConvertTo-Json.md)
