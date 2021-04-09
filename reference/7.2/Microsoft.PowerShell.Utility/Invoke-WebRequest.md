---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/05/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: 49fa39807a522c86b94f950ba63c8ff54a112953
ms.sourcegitcommit: 241071803915ab7d544576b5652ac23349a86369
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "107027225"
---
# Invoke-WebRequest

## Übersicht
Ruft Inhalte von einer Webseite im Internet ab.

## Syntax

### Standardmethod (Standard)

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Method <WebRequestMethod>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### Standardmethodnoproxy

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Method <WebRequestMethod>] -NoProxy
 [-Body <Object>] [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>]
 [-InFile <String>] [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck]
 [-PreserveAuthorizationOnRedirect] [-SkipHeaderValidation] [<CommonParameters>]
```

### Custommethod

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -CustomMethod <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### Custommethodnoproxy

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -CustomMethod <String> -NoProxy
 [-Body <Object>] [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>]
 [-InFile <String>] [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck]
 [-PreserveAuthorizationOnRedirect] [-SkipHeaderValidation] [<CommonParameters>]
```

## Beschreibung

Das `Invoke-WebRequest` -Cmdlet sendet HTTP-und HTTPS-Anforderungen an eine Webseite oder einen Webdienst. Er analysiert die Antwort und gibt Auflistungen von Links, Bildern und anderen wichtigen HTML-Elementen zurück.

Dieses Cmdlet wurde in PowerShell 3,0 eingeführt.

Ab PowerShell 7,0 `Invoke-WebRequest` unterstützt die durch Umgebungsvariablen definierte Proxykonfiguration. Weitere Informationen finden Sie in diesem Artikel im Abschnitt mit [hinweisen](#notes) .

## Beispiele

### Beispiel 1: Senden einer Webanforderung

In diesem Beispiel wird das- `Invoke-WebRequest` Cmdlet verwendet, um eine Webanforderung an die Bing.com-Website zu senden.

```powershell
$Response = Invoke-WebRequest -URI https://www.bing.com/search?q=how+many+feet+in+a+mile
$Response.InputFields | Where-Object {
    $_.name -like "* Value*"
} | Select-Object Name, Value
```

```Output
name       value
----       -----
From Value 1
To Value   5280
```

Der erste Befehl gibt die Anforderung aus und speichert die Antwort in der `$Response` Variablen.

Mit dem zweiten Befehl wird ein beliebiges **Input Field abgerufen** , in dem die **Name** -Eigenschaft aussieht `"* Value"` . Die gefilterten Ergebnisse werden an weitergeleitet `Select-Object` , um die Eigenschaften **Name** und **Wert** auszuwählen.

### Beispiel 2: Verwenden eines Zustands behafteten Webdiensts

In diesem Beispiel wird gezeigt, wie das `Invoke-WebRequest` Cmdlet mit einem Zustands behafteten Webdienst verwendet wird.

```powershell
$Body = @{
    User = 'jdoe'
    password = 'P@S$w0rd!'
}
$LoginResponse = Invoke-WebRequest 'https://www.contoso.com/login/' -SessionVariable 'Session' -Body $Body -Method 'POST'

$Session

$ProfileResponse = Invoke-WebRequest 'https://www.contoso.com/profile/' -WebSession $Session

$ProfileResponse
```

Der erste-Befehl `Invoke-WebRequest` sendet eine Anmelde Anforderung. Der Befehl gibt den Wert "Session" für den Wert des **-sessionvariable-** Parameters an und speichert das Ergebnis in der `$LoginResponse` Variablen. Wenn der Befehl abgeschlossen ist, `$LoginResponse` enthält die-Variable ein `BasicHtmlWebResponseObject` -Objekt, und die- `$Session` Variable enthält ein- `WebRequestSession` Objekt. Dadurch wird der Benutzer an der Website protokolliert.

Der-Befehl `$Session` von selbst zeigt das- `WebRequestSession` Objekt in der Variablen an.

Der zweite Rückruf ruft `Invoke-WebRequest` das Profil des Benutzers ab, das erfordert, dass der Benutzer bei der Website angemeldet ist. Die in der-Variablen gespeicherten Sitzungsdaten `$Session` werden verwendet, um Sitzungs Cookies für die Website bereitzustellen, die während des Anmelde namens erstellt wurde. Das Ergebnis wird in der `$ProfileResponse` Variablen gespeichert.

Der-Befehl `$ProfileResponse` von selbst zeigt den `BasicHtmlWebResponseObject` in der Variablen an.

### Beispiel 3: erhalten von Links von einer Webseite

Dieses Beispiel ruft die Links auf einer Webseite ab. Er verwendet das `Invoke-WebRequest` Cmdlet, um den Webseiteninhalt zu erhalten. Anschließend wird die **Verknüpfungs** Eigenschaft des-Objekts verwendet `BasicHtmlWebResponseObject` `Invoke-WebRequest` , das zurückgibt, und die **href** -Eigenschaft der einzelnen Links.

```powershell
(Invoke-WebRequest -Uri "https://aka.ms/pscore6-docs").Links.Href
```

### Beispiel 4: schreibt den Antwort Inhalt mithilfe der in der angeforderten Seite definierten Codierung in eine Datei.

In diesem Beispiel wird das- `Invoke-WebRequest` Cmdlet verwendet, um den Webseiteninhalt einer PowerShell-Dokumentationsseite abzurufen.

```powershell
$Response = Invoke-WebRequest -Uri "https://aka.ms/pscore6-docs"
$Stream = [System.IO.StreamWriter]::new('.\docspage.html', $false, $Response.Encoding)
try {
    $Stream.Write($Response.Content)
}
finally {
    $Stream.Dispose()
}
```

Der erste Befehl ruft die Seite ab und speichert das Response-Objekt in der `$Response` Variablen.

Mit dem zweiten Befehl wird ein erstellt, mit dem `StreamWriter` der Antwort Inhalt in eine Datei geschrieben wird. Die **Encoding** -Eigenschaft des Response-Objekts wird verwendet, um die Codierung für die Datei festzulegen.

Die letzten Befehle schreiben die **Content** -Eigenschaft in die Datei und verwirft dann das `StreamWriter` .

Beachten Sie, dass die **Encoding** -Eigenschaft NULL ist, wenn die Webanforderung keinen Text Inhalt zurückgibt.

### Beispiel 5: Übermitteln einer Multipart/Form-Datendatei

In diesem Beispiel wird das- `Invoke-WebRequest` Cmdlet zum Hochladen einer Datei als `multipart/form-data` Übermittlung verwendet. Die Datei `c:\document.txt` wird als Formularfeld `document` mit dem `Content-Type` von übermittelt `text/plain` .

```powershell
$FilePath = 'c:\document.txt'
$FieldName = 'document'
$ContentType = 'text/plain'

$FileStream = [System.IO.FileStream]::new($filePath, [System.IO.FileMode]::Open)
$FileHeader = [System.Net.Http.Headers.ContentDispositionHeaderValue]::new('form-data')
$FileHeader.Name = $FieldName
$FileHeader.FileName = Split-Path -leaf $FilePath
$FileContent = [System.Net.Http.StreamContent]::new($FileStream)
$FileContent.Headers.ContentDisposition = $FileHeader
$FileContent.Headers.ContentType = [System.Net.Http.Headers.MediaTypeHeaderValue]::Parse($ContentType)

$MultipartContent = [System.Net.Http.MultipartFormDataContent]::new()
$MultipartContent.Add($FileContent)

$Response = Invoke-WebRequest -Body $MultipartContent -Method 'POST' -Uri 'https://api.contoso.com/upload'
```

### Beispiel 6: vereinfachte Multipart/Form-Übermittlung von Daten

Einige APIs erfordern `multipart/form-data` Übermittlungen zum Hochladen von Dateien und gemischtem Inhalt. In diesem Beispiel wird das Aktualisieren eines Benutzerprofils veranschaulicht.

```powershell
$Uri = 'https://api.contoso.com/v2/profile'
$Form = @{
    firstName  = 'John'
    lastName   = 'Doe'
    email      = 'john.doe@contoso.com'
    avatar     = Get-Item -Path 'c:\Pictures\jdoe.png'
    birthday   = '1980-10-15'
    hobbies    = 'Hiking','Fishing','Jogging'
}
$Result = Invoke-WebRequest -Uri $Uri -Method Post -Form $Form
```

Das Profil Formular erfordert die folgenden Felder: `firstName` , `lastName` , `email` , `avatar` , `birthday` und `hobbies` . Die API erwartet ein Bild, damit das Benutzerprofil im Feld bereitgestellt wird `avatar` . Die API akzeptiert auch mehrere `hobbies` Einträge, die im gleichen Formular übermittelt werden.

Beim Erstellen der `$Form` Hash Tabelle werden die Schlüsselnamen als Formular Feldnamen verwendet. Standardmäßig werden die Werte der Hash Tabelle in Zeichen folgen konvertiert. Wenn ein **System. IO. FileInfo** -Wert vorhanden ist, wird der Inhalt der Datei übermittelt. Wenn eine Auflistung, z. b. Arrays oder Listen, vorhanden ist, wird das Formularfeld mehrmals übermittelt.

Wenn Sie `Get-Item` für den `avatar` Schlüssel verwenden, `FileInfo` wird das-Objekt als-Wert festgelegt. Das Ergebnis ist, dass die Bilddaten für über `jdoe.png` mittelt werden.

Wenn eine Liste für den Schlüssel bereitgestellt wird `hobbies` , `hobbies` ist das Feld in den Einsendungen einmal für jedes Listenelement enthalten.

### Beispiel 7: Erfassen von nicht erfolgreichen Nachrichten von Invoke-WebRequest

Wenn `Invoke-WebRequest` eine nicht Erfolgs-HTTP-Nachricht (404, 500 usw.) findet, wird keine Ausgabe zurückgegeben, und es wird ein Abbruch Fehler ausgelöst. Um den Fehler zu erfassen und den **Statuscode** anzuzeigen, können Sie die Ausführung in einen- `try/catch` Block einschließen.

```powershell
try
{
    $Response = Invoke-WebRequest -Uri "www.microsoft.com/unkownhost"
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

Der abschließende Fehler wird durch den- `catch` Block abgefangen, der den **Statuscode** aus dem **Ausnahme** Objekt abruft.

## Parameter

### -"-Zugewunverschlüsseltedauthentication"

Ermöglicht das Senden von Anmelde Informationen und Geheimnissen über unverschlüsselte Verbindungen. Standardmäßig führt die Angabe von Anmelde **Informationen oder einer** beliebigen **Authentifizierungs** Option mit einem **URI** , der nicht mit beginnt, `https://` zu einem Fehler, und die Anforderung wird abgebrochen, um zu verhindern, dass Geheimnisse versehentlich im Klartext über unverschlüsselte Verbindungen kommuniziert werden. Um dieses Verhalten auf eigene Gefahr zu überschreiben, geben Sie den Parameter " **zugswunverschlüsseltedauthentication** " an.

> [!WARNING]
> Die Verwendung dieses Parameters ist nicht sicher und wird nicht empfohlen. Sie wird nur aus Gründen der Kompatibilität mit Legacy Systemen bereitgestellt, die keine verschlüsselten Verbindungen bereitstellen können. Verwenden Sie auf eigene Gefahr.

Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.

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

### -Authentifizierung

Gibt den für die Anforderung zu verwendenden expliziten Authentifizierungstyp an. Der Standardwert ist **None** (Kein).
Die **Authentifizierung** kann nicht mit **usedefault-Anmelde** Informationen verwendet werden.

Verfügbare Authentifizierungs Optionen:

- `None`: Dies ist die Standardoption, wenn keine **Authentifizierung** bereitgestellt wird. Es wird keine explizite Authentifizierung verwendet.
- `Basic`: Erfordert **Credential**. Die Anmelde Informationen werden in einem RFC 7617-Standard Authentifizierungs Header im Format von gesendet `base64(user:password)` .
- `Bearer`: Erfordert **Token**. Sendet einen RFC 6750- `Authorization: Bearer` Header mit dem angegebenen Token. Dies ist ein Alias für **OAuth.**
- `OAuth`: Erfordert **Token**. Sendet einen RFC 6750- `Authorization: Bearer` Header mit dem angegebenen Token. Dies ist ein **Alias für** Bearer.

Durch die Bereitstellung der **Authentifizierung** werden alle Header überschrieben `Authorization` , die für **Header** bereitgestellt oder in **websession** eingeschlossen

Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.

```yaml
Type: Microsoft.PowerShell.Commands.WebAuthenticationType
Parameter Sets: (All)
Aliases:
Accepted values: None, Basic, Bearer, OAuth

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Text

Gibt den Anforderungstext an. Der Text entspricht dem Inhalt der Anforderung, der auf die Header folgt.
Sie können einen Textwert auch über die Pipeline an senden `Invoke-WebRequest` .

Der **Body**-Parameter kann verwendet werden, um eine Liste von Abfrageparametern oder den Inhalt der Antwort anzugeben.

Wenn die Eingabe eine GET-Anforderung und der Text `IDictionary` (in der Regel eine Hash Tabelle) ist, wird der Text dem URI als Abfrage Parameter hinzugefügt. Für andere Anforderungs Typen (z. b. Post) wird der Text als Wert des Anforderungs Texts im Standardformat festgelegt `name=value` .

Der **Body** -Parameter kann auch ein- `System.Net.Http.MultipartFormDataContent` Objekt akzeptieren. Dies erleichtert `multipart/form-data` Anforderungen. Wenn für **Body** ein **multipartformdatacontent** -Objekt bereitgestellt wird, werden alle Inhalts bezogenen Header, die für den **ContentType**-, **Header**-oder **websession** -Parameter bereitgestellt werden, von den Inhalts Headern des **multipartformdatacontent** -Objekts überschrieben. Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.

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

Gibt das Client Zertifikat an, das für eine sichere Webanforderung verwendet wird. Geben Sie eine Variable ein, die ein Zertifikat, einen Befehl oder einen Ausdruck enthält, durch die das Zertifikat abgerufen wird.

Um ein Zertifikat zu suchen, verwenden Sie `Get-PfxCertificate` oder das- `Get-ChildItem` Cmdlet im Zertifikat `Cert:` Laufwerk (). Wenn das Zertifikat ungültig ist oder nicht über ausreichende Berechtigungen verfügt, schlägt der Befehl fehl.

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

Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Senden der Anforderung verfügt. Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.

Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet. Sie können nur lokalen Benutzerkonten zugeordnet werden. Sie funktionieren nicht mit Domänen Konten.

Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den- `Get-Item` Befehl oder den- `Get-ChildItem` Befehl im PowerShell- `Cert:` Laufwerk.

> [!NOTE]
> Diese Funktion wird zurzeit nur auf Windows-Betriebssystemplattformen unterstützt.

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

Wenn dieser Parameter ausgelassen wird und die Anforderungs Methode Post ist, `Invoke-WebRequest` legt den Inhaltstyp auf fest `application/x-www-form-urlencoded` . Andernfalls wird der Inhaltstyp nicht im-Befehl angegeben.

" **ContentType** " wird überschrieben, wenn ein **multipartformdatacontent** -Objekt für den **Text** angegeben wird.

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

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.

Anmelde **Informationen können allein** oder in Verbindung mit bestimmten **Authentifizierungs** Parameter Optionen verwendet werden. Bei Verwendung allein werden Anmelde Informationen nur für den Remote Server bereitgestellt, wenn vom Remote Server eine Anforderung zur Authentifizierungs Aufforderung gesendet wird. Bei Verwendung mit **Authentifizierungs** Optionen werden die Anmelde Informationen explizit gesendet.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Custommethod

Gibt eine für die Webanforderung verwendete benutzerdefinierte Methode an. Diese Option kann verwendet werden, wenn die für den Endpunkt erforderliche Anforderungs Methode nicht für die **Methode** verfügbar ist. Die **Methode** und die **custommethod** können nicht gleichzeitig verwendet werden.

In diesem Beispiel wird eine `TEST` http-Anforderung an die API:

`Invoke-WebRequest -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.

```yaml
Type: System.String
Parameter Sets: CustomMethod, CustomMethodNoProxy
Aliases: CM

Required: True
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

### -Formular

Konvertiert ein Wörterbuch in eine `multipart/form-data` Übermittlung. Das **Formular** darf nicht mit dem **Textkörper** verwendet werden.
Wenn **ContentType** verwendet wird, wird es ignoriert.

Die Schlüssel des Wörterbuchs werden als Formular Feldnamen verwendet. Standardmäßig werden Formular Werte in Zeichen folgen Werte konvertiert.

Wenn der Wert ein **System. IO. FileInfo** -Objekt ist, wird der Inhalt der Binärdatei übermittelt. Der Name der Datei wird als **Dateiname** -Eigenschaft übermittelt. Der MIME-Typ wird als festgelegt `application/octet-stream` . `Get-Item` kann verwendet werden, um die Bereitstellung des **System. IO. FileInfo** -Objekts zu vereinfachen.

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

Wenn der Wert ein Auflistungstyp ist (z. b. Arrays oder Listen), werden die Felder for mehrmals übermittelt.
Die Werte der Liste werden standardmäßig als Zeichen folgen behandelt. Wenn der Wert ein **System. IO. FileInfo** -Objekt ist, wird der Inhalt der Binärdatei übermittelt. Unterstützte Auflistungen werden nicht unterstützt.

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

Im obigen Beispiel wird das `tags` Feld dreimal in der Form bereitgestellt, einmal für jede von `Vacation` , `Italy` und `2017` . Das `pictures` Feld wird auch einmal für jede Datei im Ordner übermittelt `2017-Italy` . Der binäre Inhalt der Dateien in diesem Ordner wird als-Werte übermittelt.

Diese Funktion wurde in PowerShell 6.1.0 hinzugefügt.

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

### -Header

Gibt die Header der Webanforderung an. Geben Sie eine Hashtabelle oder ein Wörterbuch ein.

Verwenden Sie zum Festlegen der UserAgent-Header den **UserAgent**-Parameter. Sie können diesen Parameter nicht verwenden, um **Benutzer-Agent-** oder Cookie-Header anzugeben.

Inhalts bezogene Header, z. b., werden `Content-Type` überschrieben, wenn ein **multipartformdatacontent** -Objekt für den **Text** angegeben wird.

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

Ruft den Inhalt der Webanforderung aus einer Datei ab. Geben Sie einen Pfad- und Dateinamen ein. Wenn Sie den Pfad weglassen, wird der aktuelle Speicherort als Standard verwendet.

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
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maximumretrycount

Gibt an, wie oft PowerShell versucht, eine Verbindung wiederherzustellen, wenn ein Fehlercode zwischen 400 und 599, inklusiv oder 304 empfangen wird. Siehe auch den Parameter **retryintervalsec** zum Angeben der Anzahl von Wiederholungen.

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

- `Default`
- `Delete`
- `Get`
- `Head`
- `Merge`
- `Options`
- `Patch`
- `Post`
- `Put`
- `Trace`

Der **custommethod** -Parameter kann für Anforderungs Methoden verwendet werden, die oben nicht aufgeführt sind.

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestMethod
Parameter Sets: StandardMethod, StandardMethodNoProxy
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoProxy

Gibt an, dass das Cmdlet keinen Proxy verwenden soll, um das Ziel zu erreichen. Wenn Sie den in der Umgebung konfigurierten Proxy umgehen müssen, verwenden Sie diesen Switch. Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StandardMethodNoProxy, CustomMethodNoProxy
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Outfile

Gibt die Ausgabedatei an, für die dieses Cmdlet den Antworttext speichert. Geben Sie einen Pfad- und Dateinamen ein.
Wenn Sie den Pfad weglassen, wird der aktuelle Speicherort als Standard verwendet. Der Name wird als literalpfad behandelt.
Namen, die eckige Klammern () enthalten, `[]` müssen in einfache Anführungszeichen () eingeschlossen werden `'` .

Standardmäßig `Invoke-WebRequest` gibt die Ergebnisse an die Pipeline zurück. Verwenden Sie den **Passthru**-Parameter, um Ergebnisse an eine Datei und an die Pipeline zu senden.

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

Gibt an, dass das Cmdlet zusätzlich zum Schreiben in eine Datei die Ergebnisse zurückgibt. Dieser Parameter ist nur gültig, wenn der **OutFile**-Parameter ebenfalls im Befehl verwendet wird.

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

### -Preserveauthorizationonredirect

Gibt an, dass das Cmdlet den `Authorization` Header, falls vorhanden, über Umleitungen beibehalten soll.

Standardmäßig entfernt das Cmdlet den `Authorization` Header vor der Umleitung. Durch die Angabe dieses Parameters wird diese Logik in Fällen deaktiviert, in denen der Header an den Umleitungs Speicherort gesendet werden muss.

Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.

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
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxy Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, **User@Domain.Com** , oder geben Sie ein- `PSCredential` Objekt ein, z. b. das vom `Get-Credential` Cmdlet generierte.

Dieser Parameter ist nur gültig, wenn der **Proxy** Parameter auch im Befehl verwendet wird. Die Parameter " **proxycredential** " und " **proxyusedefaultcredential** " können nicht im selben Befehl verwendet werden.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxyusedefault-Anmelde Informationen

Gibt an, dass das Cmdlet die Anmelde Informationen des aktuellen Benutzers verwendet, um auf den Proxy Server zuzugreifen, der durch den **Proxy** Parameter angegeben wird.

Dieser Parameter ist nur gültig, wenn der **Proxy** Parameter auch im Befehl verwendet wird. Die Parameter " **proxycredential** " und " **proxyusedefaultcredential** " können nicht im selben Befehl verwendet werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fortsetzen

Führt einen bewährten Versuch aus, den Download einer partiellen Datei fortzusetzen. **Resume** erfordert **outfile**.

**Resume** funktioniert nur mit der Größe der lokalen Datei und der Remote Datei und führt keine andere Überprüfung durch, dass die lokale Datei und die Remote Datei identisch sind.

Wenn die lokale Dateigröße kleiner ist als die Remote Dateigröße, versucht das Cmdlet, das Herunterladen der Datei fortzusetzen und die verbleibenden Bytes an das Ende der Datei anzuhängen.

Wenn die lokale Dateigröße mit der Remote Dateigröße identisch ist, wird keine Aktion ausgeführt, und das Cmdlet geht davon aus, dass der Download bereits beendet wurde.

Wenn die Größe der lokalen Datei größer ist als die Remote Dateigröße, wird die lokale Datei überschrieben, und die gesamte Remote Datei wird erneut heruntergeladen. Dieses Verhalten ist mit der Verwendung von **outfile** ohne **fort** Setzung identisch.

Wenn der Remote Server das Herunterladen von Downloads nicht unterstützt, wird die lokale Datei überschrieben, und die gesamte Remote Datei wird erneut heruntergeladen. Dieses Verhalten ist mit der Verwendung von **outfile** ohne **fort** Setzung identisch.

Wenn die lokale Datei nicht vorhanden ist, wird die lokale Datei erstellt und die gesamte Remote Datei heruntergeladen. Dieses Verhalten ist mit der Verwendung von **outfile** ohne **fort** Setzung identisch.

Diese Funktion wurde in PowerShell 6.1.0 hinzugefügt.

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

### -Retryintervalsec

Gibt das Intervall zwischen den Wiederholungs versuchen für die Verbindung an, wenn ein Fehlercode zwischen 400 und 599, inklusiv oder 304 empfangen wird. Siehe auch " **maximumretrycount** "-Parameter zum Angeben der Anzahl von Wiederholungs versuchen.

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

### -Sessionvariable

Gibt eine Variable an, für die dieses Cmdlet eine Webanforderungs Sitzung erstellt und im Wert speichert.
Geben Sie einen Variablennamen ohne das Dollarzeichen `$` Symbol () ein.

Wenn Sie eine Sitzungs Variable angeben, `Invoke-WebRequest` erstellt ein Webanforderungs-Sitzungs Objekt und weist es einer Variablen mit dem angegebenen Namen in der PowerShell-Sitzung zu. Sie können die Variable in der Sitzung verwenden, sobald der Befehl abgeschlossen wurde.

Im Gegensatz zu einer Remotesitzung besteht bei der Webanforderungssitzung keine persistente Verbindung. Dabei handelt es sich um ein Objekt, das Informationen über die Verbindung und die Anforderung enthält, einschließlich Cookies, Anmelde Informationen, des maximalen Umleitungs Werts und der Zeichenfolge des Benutzer-Agents. Sie können das Objekt verwenden, um den Zustand und die Daten übergreifend für Webanforderungen zu nutzen.

Um die Webanforderungssitzung in nachfolgenden Webanforderungen zu verwenden, geben Sie die Sitzungsvariable im Wert des **WebSession**-Parameters an. PowerShell verwendet die Daten im Sitzungs Objekt der Webanforderung, wenn die neue Verbindung hergestellt wird. Um einen Wert in der Webanforderungssitzung zu überschreiben, verwenden Sie einen Cmdletparameter wie **UserAgent** oder **Credential**. Parameterwerte haben Vorrang vor Werten in der Webanforderungssitzung.

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

### -SkipCertificateCheck

Überspringt die Überprüfung der Zertifikat Überprüfung. Dies schließt alle Überprüfungen ein, z. b. Ablauf, Widerruf, vertrauenswürdige Stamm Zertifizierungsstelle usw.

> [!WARNING]
> Die Verwendung dieses Parameters ist nicht sicher und wird nicht empfohlen. Dieser Switch sollte nur für bekannte Hosts verwendet werden, die ein selbst signiertes Zertifikat zu Testzwecken verwenden. Verwenden Sie auf eigene Gefahr.

Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.

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

### -Skipheadervalidation

Gibt an, dass das Cmdlet der Anforderung Header ohne Validierung hinzufügen soll.

Dieser Switch sollte für Standorte verwendet werden, für die Header Werte erforderlich sind, die nicht den Standards entsprechen.
Wenn Sie diesen Schalter angeben, wird die Validierung deaktiviert, damit der Wert nicht aktiviert werden kann. Wenn angegeben, werden alle Header ohne Validierung hinzugefügt.

Dieser Schalter deaktiviert die Überprüfung von Werten, die an die Parameter **ContentType**, **Headers** und **userAgent** übermittelt werden.

Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.

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

### -Skiphttperrorcheck

Dieser Parameter bewirkt, dass das Cmdlet http-Fehlerstatus ignoriert und die Verarbeitung von Antworten fortsetzt.
Die Fehler Antworten werden genau so in die Pipeline geschrieben, als ob Sie erfolgreich waren.

Dieser Parameter wurde in PowerShell 7 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SslProtocol

Legt die SSL/TLS-Protokolle fest, die für die Webanforderung zulässig sind. Standardmäßig sind alle vom System unterstützten SSL/TLS-Protokolle zulässig. **SslProtocol** ermöglicht die Beschränkung auf bestimmte Protokolle zu Konformitäts Zwecken.

Diese Werte werden als Flag-basierte Enumeration definiert. Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen. Die Werte können als Array von Werten an den **SslProtocol** -Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden. Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert. Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden. Möglicherweise sind Sie nicht in der Lage, mehrere Optionen auf allen Plattformen zu definieren.

> [!NOTE]
> Auf nicht-Windows-Plattformen ist es möglicherweise nicht möglich, `Tls` oder `Tls12` als Option anzugeben. Die Unterstützung für `Tls13` ist nicht auf allen Betriebssystemen verfügbar und muss pro Betriebssystem überprüft werden.

Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt, und die Unterstützung für `Tls13` wurde in PowerShell 7,1 hinzugefügt.

```yaml
Type: Microsoft.PowerShell.Commands.WebSslProtocol
Parameter Sets: (All)
Aliases:
Accepted values: Default, Tls, Tls11, Tls12

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timeoutsec

Gibt an, wie lange die Anforderung ausstehend sein kann, bevor eine Zeitüberschreitung auftritt. Geben Sie einen Wert in Sekunden ein. Der Standardwert 0 (null) steht für einen unbegrenzten Zeitüberschreitungswert.

Eine Domain Name System (DNS)-Abfrage kann bis zu 15 Sekunden dauern, bis eine Rückgabe oder ein Timeout auftritt. Wenn Ihre Anforderung einen Hostnamen enthält, der aufgelöst werden muss, und Sie **timeoutsec** auf einen Wert größer als 0 (null), aber weniger als 15 Sekunden festlegen, kann es 15 Sekunden oder länger dauern, bis eine WebException ausgelöst wird und für Ihre Anforderung ein Timeout eintritt.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Token

Das OAuth-oder bearertoken, das in die Anforderung aufgenommen werden soll. **Token** ist für bestimmte **Authentifizierungs** Optionen erforderlich. Sie kann nicht unabhängig verwendet werden.

**Token** nimmt eine, `SecureString` die das Token enthält. Um das Token manuell bereitzustellen, verwenden Sie Folgendes:

`Invoke-WebRequest -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Security.SecureString
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
- Identity

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

Gibt den Uniform Resource Identifier (URI) der Internet Ressource an, an die die Webanforderung gesendet wird. Geben Sie einen URI ein. Dieser Parameter unterstützt nur http oder HTTPS.

Dieser Parameter ist erforderlich. Der Parameter Name- **URI** ist optional.

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

Dieser Parameter ist veraltet. Ab PowerShell 6.0.0 verwenden alle Webanforderungen nur die grundlegende-Verarbeitung. Dieser Parameter ist nur aus Gründen der Abwärtskompatibilität enthalten, und jede Verwendung dieser Parameter hat keine Auswirkung auf den Vorgang des Cmdlets.

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

Gibt an, dass das Cmdlet die Anmelde Informationen des aktuellen Benutzers verwendet, um die Webanforderung zu senden. Dies kann nicht mit **Authentifizierung** **oder Anmelde** Informationen verwendet werden und wird möglicherweise nicht auf allen Plattformen unterstützt.

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

Gibt eine Benutzer-Agent-Zeichenfolge für die Webanforderung an.

Der Standard-Benutzer-Agent ähnelt `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` mit geringfügigen Abweichungen für die einzelnen Betriebssysteme und Plattformen.

Um eine Website mit der standardmäßigen Benutzer-Agent-Zeichenfolge zu testen, die von den meisten Internetbrowsern verwendet wird, verwenden Sie die Eigenschaften der Klasse [psuseragent](/dotnet/api/microsoft.powershell.commands.psuseragent) , z. b. Chrome, Firefox, Internet Explorer, Opera und Safari.

Der folgende Befehl verwendet z. b. die Benutzer-Agent-Zeichenfolge für Internet Explorer: `Invoke-WebRequest -Uri https://website.com/ -UserAgent ([Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer)`

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

Um einen Wert in der Webanforderungssitzung zu überschreiben, verwenden Sie einen Cmdletparameter wie **UserAgent** oder **Credential**. Parameterwerte haben Vorrang vor Werten in der Webanforderungssitzung. Inhalts bezogene Header, wie z `Content-Type` . b., werden auch überschrieben, wenn ein **multipartformdatacontent** -Objekt für den **Text** angegeben wird.

Im Gegensatz zu einer Remote Sitzung ist die Webanforderungs Sitzung keine persistente Verbindung. Dabei handelt es sich um ein Objekt, das Informationen über die Verbindung und die Anforderung enthält, einschließlich Cookies, Anmelde Informationen, des maximalen Umleitungs Werts und der Zeichenfolge des Benutzer-Agents. Sie können das Objekt verwenden, um den Zustand und die Daten übergreifend für Webanforderungen zu nutzen.

Um eine Webanforderungs Sitzung zu erstellen, geben Sie einen Variablennamen ohne Dollarzeichen in den Wert des **sessionvariable** -Parameters eines `Invoke-WebRequest` Befehls ein. `Invoke-WebRequest` erstellt die Sitzung und speichert Sie in der Variablen. In allen nachfolgenden Befehlen verwenden Sie die Variable als Wert für den **WebSession**-Parameter.

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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Eingaben

### System.Object

Sie können den Text einer Webanforderung an übergeben `Invoke-WebRequest` .

## Ausgaben

### Microsoft. PowerShell. Commands. basichtmlwebresponseobject

## Notizen

Ab PowerShell 6.0.0 `Invoke-WebRequest` unterstützt nur die grundlegende-Verarbeitung.

Weitere Informationen finden Sie unter [basichtmlwebresponseobject](/dotnet/api/microsoft.powershell.commands.basichtmlwebresponseobject).

Aufgrund von Änderungen in .net Core 3,1 verwenden PowerShell 7,0 und höher die [HttpClient. defaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) -Eigenschaft, um die Proxykonfiguration zu ermitteln.

Der Wert dieser Eigenschaft wird von Ihrer Plattform bestimmt:

- **Für Windows**: liest die Proxykonfiguration aus Umgebungsvariablen. Wenn diese Variablen nicht definiert sind, wird die Eigenschaft von den Proxy Einstellungen des Benutzers abgeleitet.
- **Für macOS**: liest die Proxykonfiguration aus Umgebungsvariablen. Wenn diese Variablen nicht definiert sind, wird die Eigenschaft von den Proxy Einstellungen des Systems abgeleitet.
- **Für Linux**: liest die Proxykonfiguration aus Umgebungsvariablen. Wenn diese Variablen nicht definiert sind, initialisiert die-Eigenschaft eine nicht konfigurierte-Instanz, die alle Adressen umgeht.

Die Umgebungsvariablen, die für die `DefaultProxy` Initialisierung auf Windows-und UNIX-basierten Plattformen verwendet werden, sind:

- `HTTP_PROXY`: der Hostname oder die IP-Adresse des Proxy Servers, der für HTTP-Anforderungen verwendet wird.
- `HTTPS_PROXY`: der Hostname oder die IP-Adresse des Proxy Servers, der für HTTPS-Anforderungen verwendet wird.
- `ALL_PROXY`: der Hostname oder die IP-Adresse des Proxy Servers, der für http-und HTTPS-Anforderungen verwendet wird, falls `HTTP_PROXY` oder `HTTPS_PROXY` nicht definiert sind.
- `NO_PROXY`: eine durch Trennzeichen getrennte Liste von Hostnamen, die von der Proxy Datei ausgeschlossen werden sollen.

## Ähnliche Themen

[Invoke-RestMethod](Invoke-RestMethod.md)

[ConvertFrom-Json](ConvertFrom-Json.md)

[ConvertTo-Json](ConvertTo-Json.md)
