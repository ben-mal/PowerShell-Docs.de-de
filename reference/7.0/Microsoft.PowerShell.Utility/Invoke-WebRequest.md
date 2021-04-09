---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/05/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: 7baa84d062e9a25d59d0353f175e108dd0bd769e
ms.sourcegitcommit: 241071803915ab7d544576b5652ac23349a86369
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "107027242"
---
# <span data-ttu-id="be89b-102">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="be89b-102">Invoke-WebRequest</span></span>

## <span data-ttu-id="be89b-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="be89b-103">Synopsis</span></span>
<span data-ttu-id="be89b-104">Ruft Inhalte von einer Webseite im Internet ab.</span><span class="sxs-lookup"><span data-stu-id="be89b-104">Gets content from a web page on the internet.</span></span>

## <span data-ttu-id="be89b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="be89b-105">Syntax</span></span>

### <span data-ttu-id="be89b-106">Standardmethod (Standard)</span><span class="sxs-lookup"><span data-stu-id="be89b-106">StandardMethod (Default)</span></span>

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

### <span data-ttu-id="be89b-107">Standardmethodnoproxy</span><span class="sxs-lookup"><span data-stu-id="be89b-107">StandardMethodNoProxy</span></span>

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

### <span data-ttu-id="be89b-108">Custommethod</span><span class="sxs-lookup"><span data-stu-id="be89b-108">CustomMethod</span></span>

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

### <span data-ttu-id="be89b-109">Custommethodnoproxy</span><span class="sxs-lookup"><span data-stu-id="be89b-109">CustomMethodNoProxy</span></span>

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

## <span data-ttu-id="be89b-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be89b-110">Description</span></span>

<span data-ttu-id="be89b-111">Das `Invoke-WebRequest` -Cmdlet sendet HTTP-und HTTPS-Anforderungen an eine Webseite oder einen Webdienst.</span><span class="sxs-lookup"><span data-stu-id="be89b-111">The `Invoke-WebRequest` cmdlet sends HTTP and HTTPS requests to a web page or web service.</span></span> <span data-ttu-id="be89b-112">Er analysiert die Antwort und gibt Auflistungen von Links, Bildern und anderen wichtigen HTML-Elementen zurück.</span><span class="sxs-lookup"><span data-stu-id="be89b-112">It parses the response and returns collections of links, images, and other significant HTML elements.</span></span>

<span data-ttu-id="be89b-113">Dieses Cmdlet wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="be89b-113">This cmdlet was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="be89b-114">Ab PowerShell 7,0 `Invoke-WebRequest` unterstützt die durch Umgebungsvariablen definierte Proxykonfiguration.</span><span class="sxs-lookup"><span data-stu-id="be89b-114">Beginning in PowerShell 7.0, `Invoke-WebRequest` supports proxy configuration defined by environment variables.</span></span> <span data-ttu-id="be89b-115">Weitere Informationen finden Sie in diesem Artikel im Abschnitt mit [hinweisen](#notes) .</span><span class="sxs-lookup"><span data-stu-id="be89b-115">See the [Notes](#notes) section of this article.</span></span>

## <span data-ttu-id="be89b-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="be89b-116">Examples</span></span>

### <span data-ttu-id="be89b-117">Beispiel 1: Senden einer Webanforderung</span><span class="sxs-lookup"><span data-stu-id="be89b-117">Example 1: Send a web request</span></span>

<span data-ttu-id="be89b-118">In diesem Beispiel wird das- `Invoke-WebRequest` Cmdlet verwendet, um eine Webanforderung an die Bing.com-Website zu senden.</span><span class="sxs-lookup"><span data-stu-id="be89b-118">This example uses the `Invoke-WebRequest` cmdlet to send a web request to the Bing.com site.</span></span>

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

<span data-ttu-id="be89b-119">Der erste Befehl gibt die Anforderung aus und speichert die Antwort in der `$Response` Variablen.</span><span class="sxs-lookup"><span data-stu-id="be89b-119">The first command issues the request and saves the response in the `$Response` variable.</span></span>

<span data-ttu-id="be89b-120">Mit dem zweiten Befehl wird ein beliebiges **Input Field abgerufen** , in dem die **Name** -Eigenschaft aussieht `"* Value"` .</span><span class="sxs-lookup"><span data-stu-id="be89b-120">The second command gets any **InputField** where the **Name** property is like `"* Value"`.</span></span> <span data-ttu-id="be89b-121">Die gefilterten Ergebnisse werden an weitergeleitet `Select-Object` , um die Eigenschaften **Name** und **Wert** auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="be89b-121">The filtered results are piped to `Select-Object` to select the **Name** and **Value** properties.</span></span>

### <span data-ttu-id="be89b-122">Beispiel 2: Verwenden eines Zustands behafteten Webdiensts</span><span class="sxs-lookup"><span data-stu-id="be89b-122">Example 2: Use a stateful web service</span></span>

<span data-ttu-id="be89b-123">In diesem Beispiel wird gezeigt, wie das `Invoke-WebRequest` Cmdlet mit einem Zustands behafteten Webdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-123">This example shows how to use the `Invoke-WebRequest` cmdlet with a stateful web service.</span></span>

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

<span data-ttu-id="be89b-124">Der erste-Befehl `Invoke-WebRequest` sendet eine Anmelde Anforderung.</span><span class="sxs-lookup"><span data-stu-id="be89b-124">The first call to `Invoke-WebRequest` sends a sign-in request.</span></span> <span data-ttu-id="be89b-125">Der Befehl gibt den Wert "Session" für den Wert des **-sessionvariable-** Parameters an und speichert das Ergebnis in der `$LoginResponse` Variablen.</span><span class="sxs-lookup"><span data-stu-id="be89b-125">The command specifies a value of "Session" for the value of the **-SessionVariable** parameter, and saves the result in the `$LoginResponse` variable.</span></span> <span data-ttu-id="be89b-126">Wenn der Befehl abgeschlossen ist, `$LoginResponse` enthält die-Variable ein `BasicHtmlWebResponseObject` -Objekt, und die- `$Session` Variable enthält ein- `WebRequestSession` Objekt.</span><span class="sxs-lookup"><span data-stu-id="be89b-126">When the command completes, the `$LoginResponse` variable contains an `BasicHtmlWebResponseObject` and the `$Session` variable contains a `WebRequestSession` object.</span></span> <span data-ttu-id="be89b-127">Dadurch wird der Benutzer an der Website protokolliert.</span><span class="sxs-lookup"><span data-stu-id="be89b-127">This logs the user into the site.</span></span>

<span data-ttu-id="be89b-128">Der-Befehl `$Session` von selbst zeigt das- `WebRequestSession` Objekt in der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="be89b-128">The call to `$Session` by itself shows the `WebRequestSession` object in the variable.</span></span>

<span data-ttu-id="be89b-129">Der zweite Rückruf ruft `Invoke-WebRequest` das Profil des Benutzers ab, das erfordert, dass der Benutzer bei der Website angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="be89b-129">The second call to `Invoke-WebRequest` fetches the user's profile which requires that the user be logged into the site.</span></span> <span data-ttu-id="be89b-130">Die in der-Variablen gespeicherten Sitzungsdaten `$Session` werden verwendet, um Sitzungs Cookies für die Website bereitzustellen, die während des Anmelde namens erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="be89b-130">The session data stored in the `$Session` variable is used to provide session cookies to the site created during the login.</span></span> <span data-ttu-id="be89b-131">Das Ergebnis wird in der `$ProfileResponse` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="be89b-131">The result is saved in the `$ProfileResponse` variable.</span></span>

<span data-ttu-id="be89b-132">Der-Befehl `$ProfileResponse` von selbst zeigt den `BasicHtmlWebResponseObject` in der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="be89b-132">The call to `$ProfileResponse` by itself shows the `BasicHtmlWebResponseObject` in the variable.</span></span>

### <span data-ttu-id="be89b-133">Beispiel 3: erhalten von Links von einer Webseite</span><span class="sxs-lookup"><span data-stu-id="be89b-133">Example 3: Get links from a web page</span></span>

<span data-ttu-id="be89b-134">Dieses Beispiel ruft die Links auf einer Webseite ab.</span><span class="sxs-lookup"><span data-stu-id="be89b-134">This example gets the links in a web page.</span></span> <span data-ttu-id="be89b-135">Er verwendet das `Invoke-WebRequest` Cmdlet, um den Webseiteninhalt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="be89b-135">It uses the `Invoke-WebRequest` cmdlet to get the web page content.</span></span> <span data-ttu-id="be89b-136">Anschließend wird die **Verknüpfungs** Eigenschaft des-Objekts verwendet `BasicHtmlWebResponseObject` `Invoke-WebRequest` , das zurückgibt, und die **href** -Eigenschaft der einzelnen Links.</span><span class="sxs-lookup"><span data-stu-id="be89b-136">Then it uses the **Links** property of the `BasicHtmlWebResponseObject` that `Invoke-WebRequest` returns, and the **Href** property of each link.</span></span>

```powershell
(Invoke-WebRequest -Uri "https://aka.ms/pscore6-docs").Links.Href
```

### <span data-ttu-id="be89b-137">Beispiel 4: schreibt den Antwort Inhalt mithilfe der in der angeforderten Seite definierten Codierung in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="be89b-137">Example 4: Writes the response content to a file using the encoding defined in the requested page.</span></span>

<span data-ttu-id="be89b-138">In diesem Beispiel wird das- `Invoke-WebRequest` Cmdlet verwendet, um den Webseiteninhalt einer PowerShell-Dokumentationsseite abzurufen.</span><span class="sxs-lookup"><span data-stu-id="be89b-138">This example uses the `Invoke-WebRequest` cmdlet to retrieve the web page content of a PowerShell documentation page.</span></span>

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

<span data-ttu-id="be89b-139">Der erste Befehl ruft die Seite ab und speichert das Response-Objekt in der `$Response` Variablen.</span><span class="sxs-lookup"><span data-stu-id="be89b-139">The first command retrieves the page and saves the response object in the `$Response` variable.</span></span>

<span data-ttu-id="be89b-140">Mit dem zweiten Befehl wird ein erstellt, mit dem `StreamWriter` der Antwort Inhalt in eine Datei geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-140">The second command creates a `StreamWriter` to use to write the response content to a file.</span></span> <span data-ttu-id="be89b-141">Die **Encoding** -Eigenschaft des Response-Objekts wird verwendet, um die Codierung für die Datei festzulegen.</span><span class="sxs-lookup"><span data-stu-id="be89b-141">The **Encoding** property of the response object is used to set the encoding for the file.</span></span>

<span data-ttu-id="be89b-142">Die letzten Befehle schreiben die **Content** -Eigenschaft in die Datei und verwirft dann das `StreamWriter` .</span><span class="sxs-lookup"><span data-stu-id="be89b-142">The final few commands write the **Content** property to the file then disposes the `StreamWriter`.</span></span>

<span data-ttu-id="be89b-143">Beachten Sie, dass die **Encoding** -Eigenschaft NULL ist, wenn die Webanforderung keinen Text Inhalt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="be89b-143">Note that the **Encoding** property is null if the web request doesn't return text content.</span></span>

### <span data-ttu-id="be89b-144">Beispiel 5: Übermitteln einer Multipart/Form-Datendatei</span><span class="sxs-lookup"><span data-stu-id="be89b-144">Example 5: Submit a multipart/form-data file</span></span>

<span data-ttu-id="be89b-145">In diesem Beispiel wird das- `Invoke-WebRequest` Cmdlet zum Hochladen einer Datei als `multipart/form-data` Übermittlung verwendet.</span><span class="sxs-lookup"><span data-stu-id="be89b-145">This example uses the `Invoke-WebRequest` cmdlet upload a file as a `multipart/form-data` submission.</span></span> <span data-ttu-id="be89b-146">Die Datei `c:\document.txt` wird als Formularfeld `document` mit dem `Content-Type` von übermittelt `text/plain` .</span><span class="sxs-lookup"><span data-stu-id="be89b-146">The file `c:\document.txt` is submitted as the form field `document` with the `Content-Type` of `text/plain`.</span></span>

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

### <span data-ttu-id="be89b-147">Beispiel 6: vereinfachte Multipart/Form-Übermittlung von Daten</span><span class="sxs-lookup"><span data-stu-id="be89b-147">Example 6: Simplified Multipart/Form-Data Submission</span></span>

<span data-ttu-id="be89b-148">Einige APIs erfordern `multipart/form-data` Übermittlungen zum Hochladen von Dateien und gemischtem Inhalt.</span><span class="sxs-lookup"><span data-stu-id="be89b-148">Some APIs require `multipart/form-data` submissions to upload files and mixed content.</span></span> <span data-ttu-id="be89b-149">In diesem Beispiel wird das Aktualisieren eines Benutzerprofils veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="be89b-149">This example demonstrates updating a user profile.</span></span>

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

<span data-ttu-id="be89b-150">Das Profil Formular erfordert die folgenden Felder: `firstName` , `lastName` , `email` , `avatar` , `birthday` und `hobbies` .</span><span class="sxs-lookup"><span data-stu-id="be89b-150">The profile form requires these fields: `firstName`, `lastName`, `email`, `avatar`, `birthday`, and `hobbies`.</span></span> <span data-ttu-id="be89b-151">Die API erwartet ein Bild, damit das Benutzerprofil im Feld bereitgestellt wird `avatar` .</span><span class="sxs-lookup"><span data-stu-id="be89b-151">The API is expecting an image for the user profile pic to be supplied in the `avatar` field.</span></span> <span data-ttu-id="be89b-152">Die API akzeptiert auch mehrere `hobbies` Einträge, die im gleichen Formular übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="be89b-152">The API also accepts multiple `hobbies` entries to be submitted in the same form.</span></span>

<span data-ttu-id="be89b-153">Beim Erstellen der `$Form` Hash Tabelle werden die Schlüsselnamen als Formular Feldnamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="be89b-153">When creating the `$Form` HashTable, the key names are used as form field names.</span></span> <span data-ttu-id="be89b-154">Standardmäßig werden die Werte der Hash Tabelle in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="be89b-154">By default, the values of the HashTable are converted to strings.</span></span> <span data-ttu-id="be89b-155">Wenn ein **System. IO. FileInfo** -Wert vorhanden ist, wird der Inhalt der Datei übermittelt.</span><span class="sxs-lookup"><span data-stu-id="be89b-155">If a **System.IO.FileInfo** value is present, the file contents are submitted.</span></span> <span data-ttu-id="be89b-156">Wenn eine Auflistung, z. b. Arrays oder Listen, vorhanden ist, wird das Formularfeld mehrmals übermittelt.</span><span class="sxs-lookup"><span data-stu-id="be89b-156">If a collection such as arrays or lists are present, the form field is submitted multiple times.</span></span>

<span data-ttu-id="be89b-157">Wenn Sie `Get-Item` für den `avatar` Schlüssel verwenden, `FileInfo` wird das-Objekt als-Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="be89b-157">By using `Get-Item` on the `avatar` key, the `FileInfo` object is set as the value.</span></span> <span data-ttu-id="be89b-158">Das Ergebnis ist, dass die Bilddaten für über `jdoe.png` mittelt werden.</span><span class="sxs-lookup"><span data-stu-id="be89b-158">The result is that the image data for `jdoe.png` is submitted.</span></span>

<span data-ttu-id="be89b-159">Wenn eine Liste für den Schlüssel bereitgestellt wird `hobbies` , `hobbies` ist das Feld in den Einsendungen einmal für jedes Listenelement enthalten.</span><span class="sxs-lookup"><span data-stu-id="be89b-159">By supplying a list to the `hobbies` key, the `hobbies` field is present in the submissions once for each list item.</span></span>

### <span data-ttu-id="be89b-160">Beispiel 7: Erfassen von nicht erfolgreichen Nachrichten von Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="be89b-160">Example 7: Catch non success messages from Invoke-WebRequest</span></span>

<span data-ttu-id="be89b-161">Wenn `Invoke-WebRequest` eine nicht Erfolgs-HTTP-Nachricht (404, 500 usw.) findet, wird keine Ausgabe zurückgegeben, und es wird ein Abbruch Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="be89b-161">When `Invoke-WebRequest` encounters a non-success HTTP message (404, 500, etc.), it returns no output and throws a terminating error.</span></span> <span data-ttu-id="be89b-162">Um den Fehler zu erfassen und den **Statuscode** anzuzeigen, können Sie die Ausführung in einen- `try/catch` Block einschließen.</span><span class="sxs-lookup"><span data-stu-id="be89b-162">To catch the error and view the **StatusCode** you can enclose execution in a `try/catch` block.</span></span>

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

<span data-ttu-id="be89b-163">Der abschließende Fehler wird durch den- `catch` Block abgefangen, der den **Statuscode** aus dem **Ausnahme** Objekt abruft.</span><span class="sxs-lookup"><span data-stu-id="be89b-163">The terminating error is caught by the `catch` block, which retrieves the **StatusCode** from the **Exception** object.</span></span>

## <span data-ttu-id="be89b-164">Parameter</span><span class="sxs-lookup"><span data-stu-id="be89b-164">Parameters</span></span>

### <span data-ttu-id="be89b-165">-"-Zugewunverschlüsseltedauthentication"</span><span class="sxs-lookup"><span data-stu-id="be89b-165">-AllowUnencryptedAuthentication</span></span>

<span data-ttu-id="be89b-166">Ermöglicht das Senden von Anmelde Informationen und Geheimnissen über unverschlüsselte Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="be89b-166">Allows sending of credentials and secrets over unencrypted connections.</span></span> <span data-ttu-id="be89b-167">Standardmäßig führt die Angabe von Anmelde **Informationen oder einer** beliebigen **Authentifizierungs** Option mit einem **URI** , der nicht mit beginnt, `https://` zu einem Fehler, und die Anforderung wird abgebrochen, um zu verhindern, dass Geheimnisse versehentlich im Klartext über unverschlüsselte Verbindungen kommuniziert werden.</span><span class="sxs-lookup"><span data-stu-id="be89b-167">By default, supplying **Credential** or any **Authentication** option with a **Uri** that does not begin with `https://` results in an error and the request is aborted to prevent unintentionally communicating secrets in plain text over unencrypted connections.</span></span> <span data-ttu-id="be89b-168">Um dieses Verhalten auf eigene Gefahr zu überschreiben, geben Sie den Parameter " **zugswunverschlüsseltedauthentication** " an.</span><span class="sxs-lookup"><span data-stu-id="be89b-168">To override this behavior at your own risk, supply the **AllowUnencryptedAuthentication** parameter.</span></span>

> [!WARNING]
> <span data-ttu-id="be89b-169">Die Verwendung dieses Parameters ist nicht sicher und wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="be89b-169">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="be89b-170">Sie wird nur aus Gründen der Kompatibilität mit Legacy Systemen bereitgestellt, die keine verschlüsselten Verbindungen bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="be89b-170">It is provided only for compatibility with legacy systems that cannot provide encrypted connections.</span></span> <span data-ttu-id="be89b-171">Verwenden Sie auf eigene Gefahr.</span><span class="sxs-lookup"><span data-stu-id="be89b-171">Use at your own risk.</span></span>

<span data-ttu-id="be89b-172">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-172">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="be89b-173">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="be89b-173">-Authentication</span></span>

<span data-ttu-id="be89b-174">Gibt den für die Anforderung zu verwendenden expliziten Authentifizierungstyp an.</span><span class="sxs-lookup"><span data-stu-id="be89b-174">Specifies the explicit authentication type to use for the request.</span></span> <span data-ttu-id="be89b-175">Der Standardwert ist **None** (Kein).</span><span class="sxs-lookup"><span data-stu-id="be89b-175">The default is **None**.</span></span>
<span data-ttu-id="be89b-176">Die **Authentifizierung** kann nicht mit **usedefault-Anmelde** Informationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be89b-176">**Authentication** cannot be used with **UseDefaultCredentials**.</span></span>

<span data-ttu-id="be89b-177">Verfügbare Authentifizierungs Optionen:</span><span class="sxs-lookup"><span data-stu-id="be89b-177">Available Authentication Options:</span></span>

- <span data-ttu-id="be89b-178">`None`: Dies ist die Standardoption, wenn keine **Authentifizierung** bereitgestellt wird. Es wird keine explizite Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="be89b-178">`None`: This is the default option when **Authentication** isn't supplied; no explicit authentication is used.</span></span>
- <span data-ttu-id="be89b-179">`Basic`: Erfordert **Credential**.</span><span class="sxs-lookup"><span data-stu-id="be89b-179">`Basic`: Requires **Credential**.</span></span> <span data-ttu-id="be89b-180">Die Anmelde Informationen werden in einem RFC 7617-Standard Authentifizierungs Header im Format von gesendet `base64(user:password)` .</span><span class="sxs-lookup"><span data-stu-id="be89b-180">The credentials are sent in an RFC 7617 Basic Authentication header in the format of `base64(user:password)`.</span></span>
- <span data-ttu-id="be89b-181">`Bearer`: Erfordert **Token**.</span><span class="sxs-lookup"><span data-stu-id="be89b-181">`Bearer`: Requires **Token**.</span></span> <span data-ttu-id="be89b-182">Sendet einen RFC 6750- `Authorization: Bearer` Header mit dem angegebenen Token.</span><span class="sxs-lookup"><span data-stu-id="be89b-182">Sends an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="be89b-183">Dies ist ein Alias für **OAuth.**</span><span class="sxs-lookup"><span data-stu-id="be89b-183">This is an alias for **OAuth**</span></span>
- <span data-ttu-id="be89b-184">`OAuth`: Erfordert **Token**.</span><span class="sxs-lookup"><span data-stu-id="be89b-184">`OAuth`: Requires **Token**.</span></span> <span data-ttu-id="be89b-185">Sendet einen RFC 6750- `Authorization: Bearer` Header mit dem angegebenen Token.</span><span class="sxs-lookup"><span data-stu-id="be89b-185">Sends an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="be89b-186">Dies ist ein **Alias für** Bearer.</span><span class="sxs-lookup"><span data-stu-id="be89b-186">This is an alias for **Bearer**</span></span>

<span data-ttu-id="be89b-187">Durch die Bereitstellung der **Authentifizierung** werden alle Header überschrieben `Authorization` , die für **Header** bereitgestellt oder in **websession** eingeschlossen</span><span class="sxs-lookup"><span data-stu-id="be89b-187">Supplying **Authentication** overrides any `Authorization` headers supplied to **Headers** or included in **WebSession**.</span></span>

<span data-ttu-id="be89b-188">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-188">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="be89b-189">-Text</span><span class="sxs-lookup"><span data-stu-id="be89b-189">-Body</span></span>

<span data-ttu-id="be89b-190">Gibt den Anforderungstext an.</span><span class="sxs-lookup"><span data-stu-id="be89b-190">Specifies the body of the request.</span></span> <span data-ttu-id="be89b-191">Der Text entspricht dem Inhalt der Anforderung, der auf die Header folgt.</span><span class="sxs-lookup"><span data-stu-id="be89b-191">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="be89b-192">Sie können einen Textwert auch über die Pipeline an senden `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="be89b-192">You can also pipe a body value to `Invoke-WebRequest`.</span></span>

<span data-ttu-id="be89b-193">Der **Body**-Parameter kann verwendet werden, um eine Liste von Abfrageparametern oder den Inhalt der Antwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="be89b-193">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="be89b-194">Wenn die Eingabe eine GET-Anforderung und der Text `IDictionary` (in der Regel eine Hash Tabelle) ist, wird der Text dem URI als Abfrage Parameter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-194">When the input is a GET request and the body is an `IDictionary` (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="be89b-195">Für andere Anforderungs Typen (z. b. Post) wird der Text als Wert des Anforderungs Texts im Standardformat festgelegt `name=value` .</span><span class="sxs-lookup"><span data-stu-id="be89b-195">For other request types (such as POST), the body is set as the value of the request body in the standard `name=value` format.</span></span>

<span data-ttu-id="be89b-196">Der **Body** -Parameter kann auch ein- `System.Net.Http.MultipartFormDataContent` Objekt akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="be89b-196">The **Body** parameter may also accept a `System.Net.Http.MultipartFormDataContent` object.</span></span> <span data-ttu-id="be89b-197">Dies erleichtert `multipart/form-data` Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="be89b-197">This facilitates `multipart/form-data` requests.</span></span> <span data-ttu-id="be89b-198">Wenn für **Body** ein **multipartformdatacontent** -Objekt bereitgestellt wird, werden alle Inhalts bezogenen Header, die für den **ContentType**-, **Header**-oder **websession** -Parameter bereitgestellt werden, von den Inhalts Headern des **multipartformdatacontent** -Objekts überschrieben.</span><span class="sxs-lookup"><span data-stu-id="be89b-198">When a **MultipartFormDataContent** object is supplied for **Body**, any Content related headers supplied to the **ContentType**, **Headers**, or **WebSession** parameters is overridden by the Content headers of the **MultipartFormDataContent** object.</span></span> <span data-ttu-id="be89b-199">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-199">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="be89b-200">-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="be89b-200">-Certificate</span></span>

<span data-ttu-id="be89b-201">Gibt das Client Zertifikat an, das für eine sichere Webanforderung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-201">Specifies the client certificate that's used for a secure web request.</span></span> <span data-ttu-id="be89b-202">Geben Sie eine Variable ein, die ein Zertifikat, einen Befehl oder einen Ausdruck enthält, durch die das Zertifikat abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-202">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="be89b-203">Um ein Zertifikat zu suchen, verwenden Sie `Get-PfxCertificate` oder das- `Get-ChildItem` Cmdlet im Zertifikat `Cert:` Laufwerk ().</span><span class="sxs-lookup"><span data-stu-id="be89b-203">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="be89b-204">Wenn das Zertifikat ungültig ist oder nicht über ausreichende Berechtigungen verfügt, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="be89b-204">If the certificate isn't valid or doesn't have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="be89b-205">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="be89b-205">-CertificateThumbprint</span></span>

<span data-ttu-id="be89b-206">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Senden der Anforderung verfügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-206">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="be89b-207">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="be89b-207">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="be89b-208">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="be89b-208">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="be89b-209">Sie können nur lokalen Benutzerkonten zugeordnet werden. Sie funktionieren nicht mit Domänen Konten.</span><span class="sxs-lookup"><span data-stu-id="be89b-209">They can be mapped only to local user accounts; they don't work with domain accounts.</span></span>

<span data-ttu-id="be89b-210">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den- `Get-Item` Befehl oder den- `Get-ChildItem` Befehl im PowerShell- `Cert:` Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="be89b-210">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

> [!NOTE]
> <span data-ttu-id="be89b-211">Diese Funktion wird zurzeit nur auf Windows-Betriebssystemplattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be89b-211">This feature is currently only supported on Windows OS platforms.</span></span>

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

### <span data-ttu-id="be89b-212">-ContentType</span><span class="sxs-lookup"><span data-stu-id="be89b-212">-ContentType</span></span>

<span data-ttu-id="be89b-213">Gibt den Inhaltstyp der Webanforderung an.</span><span class="sxs-lookup"><span data-stu-id="be89b-213">Specifies the content type of the web request.</span></span>

<span data-ttu-id="be89b-214">Wenn dieser Parameter ausgelassen wird und die Anforderungs Methode Post ist, `Invoke-WebRequest` legt den Inhaltstyp auf fest `application/x-www-form-urlencoded` .</span><span class="sxs-lookup"><span data-stu-id="be89b-214">If this parameter is omitted and the request method is POST, `Invoke-WebRequest` sets the content type to `application/x-www-form-urlencoded`.</span></span> <span data-ttu-id="be89b-215">Andernfalls wird der Inhaltstyp nicht im-Befehl angegeben.</span><span class="sxs-lookup"><span data-stu-id="be89b-215">Otherwise, the content type isn't specified in the call.</span></span>

<span data-ttu-id="be89b-216">" **ContentType** " wird überschrieben, wenn ein **multipartformdatacontent** -Objekt für den **Text** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-216">**ContentType** is overridden when a **MultipartFormDataContent** object is supplied for **Body**.</span></span>

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

### <span data-ttu-id="be89b-217">-Credential</span><span class="sxs-lookup"><span data-stu-id="be89b-217">-Credential</span></span>

<span data-ttu-id="be89b-218">Gibt ein Benutzerkonto an, das über die Berechtigung zum Senden der Anforderung verfügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-218">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="be89b-219">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="be89b-219">The default is the current user.</span></span>

<span data-ttu-id="be89b-220">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="be89b-220">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="be89b-221">Anmelde **Informationen können allein** oder in Verbindung mit bestimmten **Authentifizierungs** Parameter Optionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be89b-221">**Credential** can be used alone or in conjunction with certain **Authentication** parameter options.</span></span> <span data-ttu-id="be89b-222">Bei Verwendung allein werden Anmelde Informationen nur für den Remote Server bereitgestellt, wenn vom Remote Server eine Anforderung zur Authentifizierungs Aufforderung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-222">When used alone, it only supplies credentials to the remote server if the remote server sends an authentication challenge request.</span></span> <span data-ttu-id="be89b-223">Bei Verwendung mit **Authentifizierungs** Optionen werden die Anmelde Informationen explizit gesendet.</span><span class="sxs-lookup"><span data-stu-id="be89b-223">When used with **Authentication** options, the credentials are explicitly sent.</span></span>

<span data-ttu-id="be89b-224">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="be89b-224">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="be89b-225">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="be89b-225">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="be89b-226">-Custommethod</span><span class="sxs-lookup"><span data-stu-id="be89b-226">-CustomMethod</span></span>

<span data-ttu-id="be89b-227">Gibt eine für die Webanforderung verwendete benutzerdefinierte Methode an.</span><span class="sxs-lookup"><span data-stu-id="be89b-227">Specifies a custom method used for the web request.</span></span> <span data-ttu-id="be89b-228">Diese Option kann verwendet werden, wenn die für den Endpunkt erforderliche Anforderungs Methode nicht für die **Methode** verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="be89b-228">This can be used if the Request Method required by the endpoint isn't an available option on the **Method**.</span></span> <span data-ttu-id="be89b-229">Die **Methode** und die **custommethod** können nicht gleichzeitig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be89b-229">**Method** and **CustomMethod** can't be used together.</span></span>

<span data-ttu-id="be89b-230">In diesem Beispiel wird eine `TEST` http-Anforderung an die API:</span><span class="sxs-lookup"><span data-stu-id="be89b-230">This example makes a `TEST` HTTP request to the API:</span></span>

`Invoke-WebRequest -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

<span data-ttu-id="be89b-231">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-231">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.String
Parameter Sets: CustomMethodNoProxy, CustomMethod
Aliases: CM

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be89b-232">-Disablekeepalive</span><span class="sxs-lookup"><span data-stu-id="be89b-232">-DisableKeepAlive</span></span>

<span data-ttu-id="be89b-233">Gibt an, dass mit dem Cmdlet der **KeepAlive** -Wert im HTTP-Header auf **false** festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-233">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to **False**.</span></span> <span data-ttu-id="be89b-234">Standardmäßig ist **KeepAlive** auf **true**.</span><span class="sxs-lookup"><span data-stu-id="be89b-234">By default, **KeepAlive** is **True**.</span></span> <span data-ttu-id="be89b-235">**KeepAlive** richtet eine persistente Verbindung mit dem Server ein, um nachfolgende Anforderungen zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="be89b-235">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="be89b-236">-Formular</span><span class="sxs-lookup"><span data-stu-id="be89b-236">-Form</span></span>

<span data-ttu-id="be89b-237">Konvertiert ein Wörterbuch in eine `multipart/form-data` Übermittlung.</span><span class="sxs-lookup"><span data-stu-id="be89b-237">Converts a dictionary to a `multipart/form-data` submission.</span></span> <span data-ttu-id="be89b-238">Das **Formular** darf nicht mit dem **Textkörper** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be89b-238">**Form** may not be used with **Body**.</span></span>
<span data-ttu-id="be89b-239">Wenn **ContentType** verwendet wird, wird es ignoriert.</span><span class="sxs-lookup"><span data-stu-id="be89b-239">If **ContentType** is used, it's ignored.</span></span>

<span data-ttu-id="be89b-240">Die Schlüssel des Wörterbuchs werden als Formular Feldnamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="be89b-240">The keys of the dictionary are used as the form field names.</span></span> <span data-ttu-id="be89b-241">Standardmäßig werden Formular Werte in Zeichen folgen Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="be89b-241">By default, form values are converted to string values.</span></span>

<span data-ttu-id="be89b-242">Wenn der Wert ein **System. IO. FileInfo** -Objekt ist, wird der Inhalt der Binärdatei übermittelt.</span><span class="sxs-lookup"><span data-stu-id="be89b-242">If the value is a **System.IO.FileInfo** object, then the binary file contents are submitted.</span></span> <span data-ttu-id="be89b-243">Der Name der Datei wird als **Dateiname** -Eigenschaft übermittelt.</span><span class="sxs-lookup"><span data-stu-id="be89b-243">The name of the file is submitted as the **filename** property.</span></span> <span data-ttu-id="be89b-244">Der MIME-Typ wird als festgelegt `application/octet-stream` .</span><span class="sxs-lookup"><span data-stu-id="be89b-244">The MIME type is set as `application/octet-stream`.</span></span> <span data-ttu-id="be89b-245">`Get-Item` kann verwendet werden, um die Bereitstellung des **System. IO. FileInfo** -Objekts zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="be89b-245">`Get-Item` can be used to simplify supplying the **System.IO.FileInfo** object.</span></span>

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

<span data-ttu-id="be89b-246">Wenn der Wert ein Auflistungstyp ist (z. b. Arrays oder Listen), werden die Felder for mehrmals übermittelt.</span><span class="sxs-lookup"><span data-stu-id="be89b-246">If the value is a collection type, such Arrays or Lists, the for field are submitted multiple times.</span></span>
<span data-ttu-id="be89b-247">Die Werte der Liste werden standardmäßig als Zeichen folgen behandelt.</span><span class="sxs-lookup"><span data-stu-id="be89b-247">The values of the list are treated as strings by default.</span></span> <span data-ttu-id="be89b-248">Wenn der Wert ein **System. IO. FileInfo** -Objekt ist, wird der Inhalt der Binärdatei übermittelt.</span><span class="sxs-lookup"><span data-stu-id="be89b-248">If the value is a **System.IO.FileInfo** object, then the binary file contents are submitted.</span></span> <span data-ttu-id="be89b-249">Unterstützte Auflistungen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be89b-249">Nested collections aren't supported.</span></span>

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

<span data-ttu-id="be89b-250">Im obigen Beispiel wird das `tags` Feld dreimal in der Form bereitgestellt, einmal für jede von `Vacation` , `Italy` und `2017` .</span><span class="sxs-lookup"><span data-stu-id="be89b-250">In the above example the `tags` field are supplied three times in the form, once for each of `Vacation`, `Italy`, and `2017`.</span></span> <span data-ttu-id="be89b-251">Das `pictures` Feld wird auch einmal für jede Datei im Ordner übermittelt `2017-Italy` .</span><span class="sxs-lookup"><span data-stu-id="be89b-251">The `pictures` field is also submitted once for each file in the `2017-Italy` folder.</span></span> <span data-ttu-id="be89b-252">Der binäre Inhalt der Dateien in diesem Ordner wird als-Werte übermittelt.</span><span class="sxs-lookup"><span data-stu-id="be89b-252">The binary contents of the files in that folder are submitted as the values.</span></span>

<span data-ttu-id="be89b-253">Diese Funktion wurde in PowerShell 6.1.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-253">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="be89b-254">-Header</span><span class="sxs-lookup"><span data-stu-id="be89b-254">-Headers</span></span>

<span data-ttu-id="be89b-255">Gibt die Header der Webanforderung an.</span><span class="sxs-lookup"><span data-stu-id="be89b-255">Specifies the headers of the web request.</span></span> <span data-ttu-id="be89b-256">Geben Sie eine Hashtabelle oder ein Wörterbuch ein.</span><span class="sxs-lookup"><span data-stu-id="be89b-256">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="be89b-257">Verwenden Sie zum Festlegen der UserAgent-Header den **UserAgent**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="be89b-257">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="be89b-258">Sie können diesen Parameter nicht verwenden, um **Benutzer-Agent-** oder Cookie-Header anzugeben.</span><span class="sxs-lookup"><span data-stu-id="be89b-258">You can't use this parameter to specify **User-Agent** or cookie headers.</span></span>

<span data-ttu-id="be89b-259">Inhalts bezogene Header, z. b., werden `Content-Type` überschrieben, wenn ein **multipartformdatacontent** -Objekt für den **Text** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-259">Content related headers, such as `Content-Type` is overridden when a **MultipartFormDataContent** object is supplied for **Body**.</span></span>

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

### <span data-ttu-id="be89b-260">-Eingabedatei</span><span class="sxs-lookup"><span data-stu-id="be89b-260">-InFile</span></span>

<span data-ttu-id="be89b-261">Ruft den Inhalt der Webanforderung aus einer Datei ab.</span><span class="sxs-lookup"><span data-stu-id="be89b-261">Gets the content of the web request from a file.</span></span> <span data-ttu-id="be89b-262">Geben Sie einen Pfad- und Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="be89b-262">Enter a path and file name.</span></span> <span data-ttu-id="be89b-263">Wenn Sie den Pfad weglassen, wird der aktuelle Speicherort als Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="be89b-263">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="be89b-264">-Maximumredirect</span><span class="sxs-lookup"><span data-stu-id="be89b-264">-MaximumRedirection</span></span>

<span data-ttu-id="be89b-265">Gibt an, wie oft PowerShell eine Verbindung an eine Alternative Uniform Resource Identifier (URI) umleitet, bevor die Verbindung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="be89b-265">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="be89b-266">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="be89b-266">The default value is 5.</span></span> <span data-ttu-id="be89b-267">Der Wert 0 (null) unterbindet sämtliche Umleitungen.</span><span class="sxs-lookup"><span data-stu-id="be89b-267">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="be89b-268">-Maximumretrycount</span><span class="sxs-lookup"><span data-stu-id="be89b-268">-MaximumRetryCount</span></span>

<span data-ttu-id="be89b-269">Gibt an, wie oft PowerShell versucht, eine Verbindung wiederherzustellen, wenn ein Fehlercode zwischen 400 und 599, inklusiv oder 304 empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-269">Specifies how many times PowerShell retries a connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="be89b-270">Siehe auch den Parameter **retryintervalsec** zum Angeben der Anzahl von Wiederholungen.</span><span class="sxs-lookup"><span data-stu-id="be89b-270">Also see **RetryIntervalSec** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="be89b-271">-Methode</span><span class="sxs-lookup"><span data-stu-id="be89b-271">-Method</span></span>

<span data-ttu-id="be89b-272">Gibt die für die Webanforderung verwendete Methode an.</span><span class="sxs-lookup"><span data-stu-id="be89b-272">Specifies the method used for the web request.</span></span> <span data-ttu-id="be89b-273">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="be89b-273">The acceptable values for this parameter are:</span></span>

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

<span data-ttu-id="be89b-274">Der **custommethod** -Parameter kann für Anforderungs Methoden verwendet werden, die oben nicht aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="be89b-274">The **CustomMethod** parameter can be used for Request Methods not listed above.</span></span>

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

### <span data-ttu-id="be89b-275">-NoProxy</span><span class="sxs-lookup"><span data-stu-id="be89b-275">-NoProxy</span></span>

<span data-ttu-id="be89b-276">Gibt an, dass das Cmdlet keinen Proxy verwenden soll, um das Ziel zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="be89b-276">Indicates that the cmdlet shouldn't use a proxy to reach the destination.</span></span> <span data-ttu-id="be89b-277">Wenn Sie den in der Umgebung konfigurierten Proxy umgehen müssen, verwenden Sie diesen Switch.</span><span class="sxs-lookup"><span data-stu-id="be89b-277">When you need to bypass the proxy configured in the environment, use this switch.</span></span> <span data-ttu-id="be89b-278">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-278">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="be89b-279">-Outfile</span><span class="sxs-lookup"><span data-stu-id="be89b-279">-OutFile</span></span>

<span data-ttu-id="be89b-280">Gibt die Ausgabedatei an, für die dieses Cmdlet den Antworttext speichert.</span><span class="sxs-lookup"><span data-stu-id="be89b-280">Specifies the output file for which this cmdlet saves the response body.</span></span> <span data-ttu-id="be89b-281">Geben Sie einen Pfad- und Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="be89b-281">Enter a path and file name.</span></span>
<span data-ttu-id="be89b-282">Wenn Sie den Pfad weglassen, wird der aktuelle Speicherort als Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="be89b-282">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="be89b-283">Standardmäßig `Invoke-WebRequest` gibt die Ergebnisse an die Pipeline zurück.</span><span class="sxs-lookup"><span data-stu-id="be89b-283">By default, `Invoke-WebRequest` returns the results to the pipeline.</span></span> <span data-ttu-id="be89b-284">Verwenden Sie den **Passthru**-Parameter, um Ergebnisse an eine Datei und an die Pipeline zu senden.</span><span class="sxs-lookup"><span data-stu-id="be89b-284">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="be89b-285">-PassThru</span><span class="sxs-lookup"><span data-stu-id="be89b-285">-PassThru</span></span>

<span data-ttu-id="be89b-286">Gibt an, dass das Cmdlet zusätzlich zum Schreiben in eine Datei die Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="be89b-286">Indicates that the cmdlet returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="be89b-287">Dieser Parameter ist nur gültig, wenn der **OutFile**-Parameter ebenfalls im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-287">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="be89b-288">-Preserveauthorizationonredirect</span><span class="sxs-lookup"><span data-stu-id="be89b-288">-PreserveAuthorizationOnRedirect</span></span>

<span data-ttu-id="be89b-289">Gibt an, dass das Cmdlet den `Authorization` Header, falls vorhanden, über Umleitungen beibehalten soll.</span><span class="sxs-lookup"><span data-stu-id="be89b-289">Indicates the cmdlet should preserve the `Authorization` header, when present, across redirections.</span></span>

<span data-ttu-id="be89b-290">Standardmäßig entfernt das Cmdlet den `Authorization` Header vor der Umleitung.</span><span class="sxs-lookup"><span data-stu-id="be89b-290">By default, the cmdlet strips the `Authorization` header before redirecting.</span></span> <span data-ttu-id="be89b-291">Durch die Angabe dieses Parameters wird diese Logik in Fällen deaktiviert, in denen der Header an den Umleitungs Speicherort gesendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="be89b-291">Specifying this parameter disables this logic for cases where the header needs to be sent to the redirection location.</span></span>

<span data-ttu-id="be89b-292">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-292">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="be89b-293">-Proxy</span><span class="sxs-lookup"><span data-stu-id="be89b-293">-Proxy</span></span>

<span data-ttu-id="be89b-294">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="be89b-294">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>
<span data-ttu-id="be89b-295">Geben Sie den URI des Netzwerk-Proxyservers ein.</span><span class="sxs-lookup"><span data-stu-id="be89b-295">Enter the URI of a network proxy server.</span></span>

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

### <span data-ttu-id="be89b-296">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="be89b-296">-ProxyCredential</span></span>

<span data-ttu-id="be89b-297">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-297">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="be89b-298">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="be89b-298">The default is the current user.</span></span>

<span data-ttu-id="be89b-299">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, **User@Domain.Com** , oder geben Sie ein- `PSCredential` Objekt ein, z. b. das vom `Get-Credential` Cmdlet generierte.</span><span class="sxs-lookup"><span data-stu-id="be89b-299">Type a user name, such as **User01** or **Domain01\User01**, **User@Domain.Com**, or enter a `PSCredential` object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="be89b-300">Dieser Parameter ist nur gültig, wenn der **Proxy** Parameter auch im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-300">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="be89b-301">Die Parameter " **proxycredential** " und " **proxyusedefaultcredential** " können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be89b-301">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="be89b-302">-Proxyusedefault-Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="be89b-302">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="be89b-303">Gibt an, dass das Cmdlet die Anmelde Informationen des aktuellen Benutzers verwendet, um auf den Proxy Server zuzugreifen, der durch den **Proxy** Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-303">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="be89b-304">Dieser Parameter ist nur gültig, wenn der **Proxy** Parameter auch im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-304">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="be89b-305">Die Parameter " **proxycredential** " und " **proxyusedefaultcredential** " können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be89b-305">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="be89b-306">-Fortsetzen</span><span class="sxs-lookup"><span data-stu-id="be89b-306">-Resume</span></span>

<span data-ttu-id="be89b-307">Führt einen bewährten Versuch aus, den Download einer partiellen Datei fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="be89b-307">Performs a best effort attempt to resume downloading a partial file.</span></span> <span data-ttu-id="be89b-308">**Resume** erfordert **outfile**.</span><span class="sxs-lookup"><span data-stu-id="be89b-308">**Resume** requires **OutFile**.</span></span>

<span data-ttu-id="be89b-309">**Resume** funktioniert nur mit der Größe der lokalen Datei und der Remote Datei und führt keine andere Überprüfung durch, dass die lokale Datei und die Remote Datei identisch sind.</span><span class="sxs-lookup"><span data-stu-id="be89b-309">**Resume** only operates on the size of the local file and remote file and performs no other validation that the local file and the remote file are the same.</span></span>

<span data-ttu-id="be89b-310">Wenn die lokale Dateigröße kleiner ist als die Remote Dateigröße, versucht das Cmdlet, das Herunterladen der Datei fortzusetzen und die verbleibenden Bytes an das Ende der Datei anzuhängen.</span><span class="sxs-lookup"><span data-stu-id="be89b-310">If the local file size is smaller than the remote file size, then the cmdlet attempts to resume downloading the file and append the remaining bytes to the end of the file.</span></span>

<span data-ttu-id="be89b-311">Wenn die lokale Dateigröße mit der Remote Dateigröße identisch ist, wird keine Aktion ausgeführt, und das Cmdlet geht davon aus, dass der Download bereits beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="be89b-311">If the local file size is the same as the remote file size, then no action is taken and the cmdlet assumes the download already complete.</span></span>

<span data-ttu-id="be89b-312">Wenn die Größe der lokalen Datei größer ist als die Remote Dateigröße, wird die lokale Datei überschrieben, und die gesamte Remote Datei wird erneut heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="be89b-312">If the local file size is larger than the remote file size, then the local file is overwritten and the entire remote file is re-downloaded.</span></span> <span data-ttu-id="be89b-313">Dieses Verhalten ist mit der Verwendung von **outfile** ohne **fort** Setzung identisch.</span><span class="sxs-lookup"><span data-stu-id="be89b-313">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="be89b-314">Wenn der Remote Server das Herunterladen von Downloads nicht unterstützt, wird die lokale Datei überschrieben, und die gesamte Remote Datei wird erneut heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="be89b-314">If the remote server does not support download resuming, then the local file is overwritten and the entire remote file is re-downloaded.</span></span> <span data-ttu-id="be89b-315">Dieses Verhalten ist mit der Verwendung von **outfile** ohne **fort** Setzung identisch.</span><span class="sxs-lookup"><span data-stu-id="be89b-315">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="be89b-316">Wenn die lokale Datei nicht vorhanden ist, wird die lokale Datei erstellt und die gesamte Remote Datei heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="be89b-316">If the local file does not exist, then the local file is created and the entire remote file is downloaded.</span></span> <span data-ttu-id="be89b-317">Dieses Verhalten ist mit der Verwendung von **outfile** ohne **fort** Setzung identisch.</span><span class="sxs-lookup"><span data-stu-id="be89b-317">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="be89b-318">Diese Funktion wurde in PowerShell 6.1.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-318">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="be89b-319">-Retryintervalsec</span><span class="sxs-lookup"><span data-stu-id="be89b-319">-RetryIntervalSec</span></span>

<span data-ttu-id="be89b-320">Gibt das Intervall zwischen den Wiederholungs versuchen für die Verbindung an, wenn ein Fehlercode zwischen 400 und 599, inklusiv oder 304 empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-320">Specifies the interval between retries for the connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="be89b-321">Siehe auch " **maximumretrycount** "-Parameter zum Angeben der Anzahl von Wiederholungs versuchen.</span><span class="sxs-lookup"><span data-stu-id="be89b-321">Also see **MaximumRetryCount** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="be89b-322">-Sessionvariable</span><span class="sxs-lookup"><span data-stu-id="be89b-322">-SessionVariable</span></span>

<span data-ttu-id="be89b-323">Gibt eine Variable an, für die dieses Cmdlet eine Webanforderungs Sitzung erstellt und im Wert speichert.</span><span class="sxs-lookup"><span data-stu-id="be89b-323">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="be89b-324">Geben Sie einen Variablennamen ohne das Dollarzeichen `$` Symbol () ein.</span><span class="sxs-lookup"><span data-stu-id="be89b-324">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="be89b-325">Wenn Sie eine Sitzungs Variable angeben, `Invoke-WebRequest` erstellt ein Webanforderungs-Sitzungs Objekt und weist es einer Variablen mit dem angegebenen Namen in der PowerShell-Sitzung zu.</span><span class="sxs-lookup"><span data-stu-id="be89b-325">When you specify a session variable, `Invoke-WebRequest` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="be89b-326">Sie können die Variable in der Sitzung verwenden, sobald der Befehl abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="be89b-326">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="be89b-327">Im Gegensatz zu einer Remotesitzung besteht bei der Webanforderungssitzung keine persistente Verbindung.</span><span class="sxs-lookup"><span data-stu-id="be89b-327">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="be89b-328">Dabei handelt es sich um ein Objekt, das Informationen über die Verbindung und die Anforderung enthält, einschließlich Cookies, Anmelde Informationen, des maximalen Umleitungs Werts und der Zeichenfolge des Benutzer-Agents.</span><span class="sxs-lookup"><span data-stu-id="be89b-328">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="be89b-329">Sie können das Objekt verwenden, um den Zustand und die Daten übergreifend für Webanforderungen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="be89b-329">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="be89b-330">Um die Webanforderungssitzung in nachfolgenden Webanforderungen zu verwenden, geben Sie die Sitzungsvariable im Wert des **WebSession**-Parameters an.</span><span class="sxs-lookup"><span data-stu-id="be89b-330">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="be89b-331">PowerShell verwendet die Daten im Sitzungs Objekt der Webanforderung, wenn die neue Verbindung hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-331">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="be89b-332">Um einen Wert in der Webanforderungssitzung zu überschreiben, verwenden Sie einen Cmdletparameter wie **UserAgent** oder **Credential**.</span><span class="sxs-lookup"><span data-stu-id="be89b-332">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="be89b-333">Parameterwerte haben Vorrang vor Werten in der Webanforderungssitzung.</span><span class="sxs-lookup"><span data-stu-id="be89b-333">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="be89b-334">Der **sessionvariable** -Parameter und der **websession** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be89b-334">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="be89b-335">-SkipCertificateCheck</span><span class="sxs-lookup"><span data-stu-id="be89b-335">-SkipCertificateCheck</span></span>

<span data-ttu-id="be89b-336">Überspringt die Überprüfung der Zertifikat Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="be89b-336">Skips certificate validation checks.</span></span> <span data-ttu-id="be89b-337">Dies schließt alle Überprüfungen ein, z. b. Ablauf, Widerruf, vertrauenswürdige Stamm Zertifizierungsstelle usw.</span><span class="sxs-lookup"><span data-stu-id="be89b-337">This includes all validations such as expiration, revocation, trusted root authority, etc.</span></span>

> [!WARNING]
> <span data-ttu-id="be89b-338">Die Verwendung dieses Parameters ist nicht sicher und wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="be89b-338">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="be89b-339">Dieser Switch sollte nur für bekannte Hosts verwendet werden, die ein selbst signiertes Zertifikat zu Testzwecken verwenden.</span><span class="sxs-lookup"><span data-stu-id="be89b-339">This switch is only intended to be used against known hosts using a self-signed certificate for testing purposes.</span></span> <span data-ttu-id="be89b-340">Verwenden Sie auf eigene Gefahr.</span><span class="sxs-lookup"><span data-stu-id="be89b-340">Use at your own risk.</span></span>

<span data-ttu-id="be89b-341">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-341">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="be89b-342">-Skipheadervalidation</span><span class="sxs-lookup"><span data-stu-id="be89b-342">-SkipHeaderValidation</span></span>

<span data-ttu-id="be89b-343">Gibt an, dass das Cmdlet der Anforderung Header ohne Validierung hinzufügen soll.</span><span class="sxs-lookup"><span data-stu-id="be89b-343">Indicates the cmdlet should add headers to the request without validation.</span></span>

<span data-ttu-id="be89b-344">Dieser Switch sollte für Standorte verwendet werden, für die Header Werte erforderlich sind, die nicht den Standards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="be89b-344">This switch should be used for sites that require header values that do not conform to standards.</span></span>
<span data-ttu-id="be89b-345">Wenn Sie diesen Schalter angeben, wird die Validierung deaktiviert, damit der Wert nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="be89b-345">Specifying this switch disables validation to allow the value to be passed unchecked.</span></span> <span data-ttu-id="be89b-346">Wenn angegeben, werden alle Header ohne Validierung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-346">When specified, all headers are added without validation.</span></span>

<span data-ttu-id="be89b-347">Dieser Schalter deaktiviert die Überprüfung von Werten, die an die Parameter **ContentType**, **Headers** und **userAgent** übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="be89b-347">This switch disables validation for values passed to the **ContentType**, **Headers** and **UserAgent** parameters.</span></span>

<span data-ttu-id="be89b-348">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-348">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="be89b-349">-Skiphttperrorcheck</span><span class="sxs-lookup"><span data-stu-id="be89b-349">-SkipHttpErrorCheck</span></span>

<span data-ttu-id="be89b-350">Dieser Parameter bewirkt, dass das Cmdlet http-Fehlerstatus ignoriert und die Verarbeitung von Antworten fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="be89b-350">This parameter causes the cmdlet to ignore HTTP error statuses and continue to process responses.</span></span>
<span data-ttu-id="be89b-351">Die Fehler Antworten werden genau so in die Pipeline geschrieben, als ob Sie erfolgreich waren.</span><span class="sxs-lookup"><span data-stu-id="be89b-351">The error responses are written to the pipeline just as if they were successful.</span></span>

<span data-ttu-id="be89b-352">Dieser Parameter wurde in PowerShell 7 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="be89b-352">This parameter was introduced in PowerShell 7.</span></span>

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

### <span data-ttu-id="be89b-353">-SslProtocol</span><span class="sxs-lookup"><span data-stu-id="be89b-353">-SslProtocol</span></span>

<span data-ttu-id="be89b-354">Legt die SSL/TLS-Protokolle fest, die für die Webanforderung zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="be89b-354">Sets the SSL/TLS protocols that are permissible for the web request.</span></span> <span data-ttu-id="be89b-355">Standardmäßig sind alle vom System unterstützten SSL/TLS-Protokolle zulässig.</span><span class="sxs-lookup"><span data-stu-id="be89b-355">By default all, SSL/TLS protocols supported by the system are allowed.</span></span> <span data-ttu-id="be89b-356">**SslProtocol** ermöglicht die Beschränkung auf bestimmte Protokolle zu Konformitäts Zwecken.</span><span class="sxs-lookup"><span data-stu-id="be89b-356">**SslProtocol** allows for limiting to specific protocols for compliance purposes.</span></span>

<span data-ttu-id="be89b-357">Diese Werte werden als Flag-basierte Enumeration definiert.</span><span class="sxs-lookup"><span data-stu-id="be89b-357">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="be89b-358">Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen.</span><span class="sxs-lookup"><span data-stu-id="be89b-358">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="be89b-359">Die Werte können als Array von Werten an den **SslProtocol** -Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="be89b-359">The values can be passed to the **SslProtocol** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="be89b-360">Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert.</span><span class="sxs-lookup"><span data-stu-id="be89b-360">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="be89b-361">Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="be89b-361">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span> <span data-ttu-id="be89b-362">Möglicherweise sind Sie nicht in der Lage, mehrere Optionen auf allen Plattformen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="be89b-362">You may not be able to define multiple options on all platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="be89b-363">Auf nicht-Windows-Plattformen ist es möglicherweise nicht möglich, `Tls` oder `Tls12` als Option anzugeben.</span><span class="sxs-lookup"><span data-stu-id="be89b-363">On non-Windows platforms it may not be possible to supply `Tls` or `Tls12` as an option.</span></span>

<span data-ttu-id="be89b-364">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="be89b-364">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="be89b-365">-Timeoutsec</span><span class="sxs-lookup"><span data-stu-id="be89b-365">-TimeoutSec</span></span>

<span data-ttu-id="be89b-366">Gibt an, wie lange die Anforderung ausstehend sein kann, bevor eine Zeitüberschreitung auftritt. Geben Sie einen Wert in Sekunden ein.</span><span class="sxs-lookup"><span data-stu-id="be89b-366">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="be89b-367">Der Standardwert 0 (null) steht für einen unbegrenzten Zeitüberschreitungswert.</span><span class="sxs-lookup"><span data-stu-id="be89b-367">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="be89b-368">Eine Domain Name System (DNS)-Abfrage kann bis zu 15 Sekunden dauern, bis eine Rückgabe oder ein Timeout auftritt. Wenn Ihre Anforderung einen Hostnamen enthält, der aufgelöst werden muss, und Sie **timeoutsec** auf einen Wert größer als 0 (null), aber weniger als 15 Sekunden festlegen, kann es 15 Sekunden oder länger dauern, bis eine WebException ausgelöst wird und für Ihre Anforderung ein Timeout eintritt.</span><span class="sxs-lookup"><span data-stu-id="be89b-368">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="be89b-369">-Token</span><span class="sxs-lookup"><span data-stu-id="be89b-369">-Token</span></span>

<span data-ttu-id="be89b-370">Das OAuth-oder bearertoken, das in die Anforderung aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="be89b-370">The OAuth or Bearer token to include in the request.</span></span> <span data-ttu-id="be89b-371">**Token** ist für bestimmte **Authentifizierungs** Optionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="be89b-371">**Token** is required by certain **Authentication** options.</span></span> <span data-ttu-id="be89b-372">Sie kann nicht unabhängig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be89b-372">It cannot be used independently.</span></span>

<span data-ttu-id="be89b-373">**Token** nimmt eine, `SecureString` die das Token enthält.</span><span class="sxs-lookup"><span data-stu-id="be89b-373">**Token** takes a `SecureString` containing the token.</span></span> <span data-ttu-id="be89b-374">Um das Token manuell bereitzustellen, verwenden Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="be89b-374">To supply the token manually use the following:</span></span>

`Invoke-WebRequest -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

<span data-ttu-id="be89b-375">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="be89b-375">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="be89b-376">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="be89b-376">-TransferEncoding</span></span>

<span data-ttu-id="be89b-377">Gibt einen Wert für den HTTP-Antwortheader transfer-encoding an.</span><span class="sxs-lookup"><span data-stu-id="be89b-377">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="be89b-378">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="be89b-378">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="be89b-379">Aufgeteilte</span><span class="sxs-lookup"><span data-stu-id="be89b-379">Chunked</span></span>
- <span data-ttu-id="be89b-380">Komprimieren</span><span class="sxs-lookup"><span data-stu-id="be89b-380">Compress</span></span>
- <span data-ttu-id="be89b-381">Deflate</span><span class="sxs-lookup"><span data-stu-id="be89b-381">Deflate</span></span>
- <span data-ttu-id="be89b-382">GZip</span><span class="sxs-lookup"><span data-stu-id="be89b-382">GZip</span></span>
- <span data-ttu-id="be89b-383">Identity</span><span class="sxs-lookup"><span data-stu-id="be89b-383">Identity</span></span>

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

### <span data-ttu-id="be89b-384">-URI</span><span class="sxs-lookup"><span data-stu-id="be89b-384">-Uri</span></span>

<span data-ttu-id="be89b-385">Gibt den Uniform Resource Identifier (URI) der Internet Ressource an, an die die Webanforderung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-385">Specifies the Uniform Resource Identifier (URI) of the internet resource to which the web request is sent.</span></span> <span data-ttu-id="be89b-386">Geben Sie einen URI ein.</span><span class="sxs-lookup"><span data-stu-id="be89b-386">Enter a URI.</span></span> <span data-ttu-id="be89b-387">Dieser Parameter unterstützt nur http oder HTTPS.</span><span class="sxs-lookup"><span data-stu-id="be89b-387">This parameter supports HTTP or HTTPS only.</span></span>

<span data-ttu-id="be89b-388">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="be89b-388">This parameter is required.</span></span> <span data-ttu-id="be89b-389">Der Parameter Name- **URI** ist optional.</span><span class="sxs-lookup"><span data-stu-id="be89b-389">The parameter name **Uri** is optional.</span></span>

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

### <span data-ttu-id="be89b-390">-Usebasicparamesing</span><span class="sxs-lookup"><span data-stu-id="be89b-390">-UseBasicParsing</span></span>

<span data-ttu-id="be89b-391">Dieser Parameter ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="be89b-391">This parameter has been deprecated.</span></span> <span data-ttu-id="be89b-392">Ab PowerShell 6.0.0 verwenden alle Webanforderungen nur die grundlegende-Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="be89b-392">Beginning with PowerShell 6.0.0, all Web requests use basic parsing only.</span></span> <span data-ttu-id="be89b-393">Dieser Parameter ist nur aus Gründen der Abwärtskompatibilität enthalten, und jede Verwendung dieser Parameter hat keine Auswirkung auf den Vorgang des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="be89b-393">This parameter is included for backwards compatibility only and any use of it has no effect on the operation of the cmdlet.</span></span>

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

### <span data-ttu-id="be89b-394">-Usedefault-Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="be89b-394">-UseDefaultCredentials</span></span>

<span data-ttu-id="be89b-395">Gibt an, dass das Cmdlet die Anmelde Informationen des aktuellen Benutzers verwendet, um die Webanforderung zu senden.</span><span class="sxs-lookup"><span data-stu-id="be89b-395">Indicates that the cmdlet uses the credentials of the current user to send the web request.</span></span> <span data-ttu-id="be89b-396">Dies kann nicht mit **Authentifizierung** **oder Anmelde** Informationen verwendet werden und wird möglicherweise nicht auf allen Plattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be89b-396">This can't be used with **Authentication** or **Credential** and may not be supported on all platforms.</span></span>

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

### <span data-ttu-id="be89b-397">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="be89b-397">-UserAgent</span></span>

<span data-ttu-id="be89b-398">Gibt eine Benutzer-Agent-Zeichenfolge für die Webanforderung an.</span><span class="sxs-lookup"><span data-stu-id="be89b-398">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="be89b-399">Der Standard-Benutzer-Agent ähnelt `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` mit geringfügigen Abweichungen für die einzelnen Betriebssysteme und Plattformen.</span><span class="sxs-lookup"><span data-stu-id="be89b-399">The default user agent is similar to `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="be89b-400">Um eine Website mit der standardmäßigen Benutzer-Agent-Zeichenfolge zu testen, die von den meisten Internetbrowsern verwendet wird, verwenden Sie die Eigenschaften der Klasse [psuseragent](/dotnet/api/microsoft.powershell.commands.psuseragent) , z. b. Chrome, Firefox, Internet Explorer, Opera und Safari.</span><span class="sxs-lookup"><span data-stu-id="be89b-400">To test a website with the standard user agent string that is used by most internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span>

<span data-ttu-id="be89b-401">Der folgende Befehl verwendet z. b. die Benutzer-Agent-Zeichenfolge für Internet Explorer: `Invoke-WebRequest -Uri https://website.com/ -UserAgent ([Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer)`</span><span class="sxs-lookup"><span data-stu-id="be89b-401">For example, the following command uses the user agent string for Internet Explorer: `Invoke-WebRequest -Uri https://website.com/ -UserAgent ([Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer)`</span></span>

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

### <span data-ttu-id="be89b-402">-Websession</span><span class="sxs-lookup"><span data-stu-id="be89b-402">-WebSession</span></span>

<span data-ttu-id="be89b-403">Gibt eine Webanforderungssitzung an.</span><span class="sxs-lookup"><span data-stu-id="be89b-403">Specifies a web request session.</span></span> <span data-ttu-id="be89b-404">Geben Sie den Variablennamen einschließlich des Dollar Zeichens ( `$` ) ein.</span><span class="sxs-lookup"><span data-stu-id="be89b-404">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="be89b-405">Um einen Wert in der Webanforderungssitzung zu überschreiben, verwenden Sie einen Cmdletparameter wie **UserAgent** oder **Credential**.</span><span class="sxs-lookup"><span data-stu-id="be89b-405">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="be89b-406">Parameterwerte haben Vorrang vor Werten in der Webanforderungssitzung.</span><span class="sxs-lookup"><span data-stu-id="be89b-406">Parameter values take precedence over values in the web request session.</span></span> <span data-ttu-id="be89b-407">Inhalts bezogene Header, wie z `Content-Type` . b., werden auch überschrieben, wenn ein **multipartformdatacontent** -Objekt für den **Text** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-407">Content related headers, such as `Content-Type`, are also be overridden when a **MultipartFormDataContent** object is supplied for **Body**.</span></span>

<span data-ttu-id="be89b-408">Im Gegensatz zu einer Remote Sitzung ist die Webanforderungs Sitzung keine persistente Verbindung.</span><span class="sxs-lookup"><span data-stu-id="be89b-408">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="be89b-409">Dabei handelt es sich um ein Objekt, das Informationen über die Verbindung und die Anforderung enthält, einschließlich Cookies, Anmelde Informationen, des maximalen Umleitungs Werts und der Zeichenfolge des Benutzer-Agents.</span><span class="sxs-lookup"><span data-stu-id="be89b-409">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="be89b-410">Sie können das Objekt verwenden, um den Zustand und die Daten übergreifend für Webanforderungen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="be89b-410">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="be89b-411">Um eine Webanforderungs Sitzung zu erstellen, geben Sie einen Variablennamen ohne Dollarzeichen in den Wert des **sessionvariable** -Parameters eines `Invoke-WebRequest` Befehls ein.</span><span class="sxs-lookup"><span data-stu-id="be89b-411">To create a web request session, enter a variable name, without a dollar sign, in the value of the **SessionVariable** parameter of an `Invoke-WebRequest` command.</span></span> <span data-ttu-id="be89b-412">`Invoke-WebRequest` erstellt die Sitzung und speichert Sie in der Variablen.</span><span class="sxs-lookup"><span data-stu-id="be89b-412">`Invoke-WebRequest` creates the session and saves it in the variable.</span></span> <span data-ttu-id="be89b-413">In allen nachfolgenden Befehlen verwenden Sie die Variable als Wert für den **WebSession**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="be89b-413">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="be89b-414">Der **sessionvariable** -Parameter und der **websession** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be89b-414">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="be89b-415">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="be89b-415">CommonParameters</span></span>

<span data-ttu-id="be89b-416">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="be89b-416">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="be89b-417">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="be89b-417">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="be89b-418">Eingaben</span><span class="sxs-lookup"><span data-stu-id="be89b-418">Inputs</span></span>

### <span data-ttu-id="be89b-419">System.Object</span><span class="sxs-lookup"><span data-stu-id="be89b-419">System.Object</span></span>

<span data-ttu-id="be89b-420">Sie können den Text einer Webanforderung an übergeben `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="be89b-420">You can pipe the body of a web request to `Invoke-WebRequest`.</span></span>

## <span data-ttu-id="be89b-421">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="be89b-421">Outputs</span></span>

### <span data-ttu-id="be89b-422">Microsoft. PowerShell. Commands. basichtmlwebresponseobject</span><span class="sxs-lookup"><span data-stu-id="be89b-422">Microsoft.PowerShell.Commands.BasicHtmlWebResponseObject</span></span>

## <span data-ttu-id="be89b-423">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be89b-423">Notes</span></span>

<span data-ttu-id="be89b-424">Ab PowerShell 6.0.0 `Invoke-WebRequest` unterstützt nur die grundlegende-Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="be89b-424">Beginning with PowerShell 6.0.0 `Invoke-WebRequest` supports basic parsing only.</span></span>

<span data-ttu-id="be89b-425">Weitere Informationen finden Sie unter [basichtmlwebresponseobject](/dotnet/api/microsoft.powershell.commands.basichtmlwebresponseobject).</span><span class="sxs-lookup"><span data-stu-id="be89b-425">For more information, see [BasicHtmlWebResponseObject](/dotnet/api/microsoft.powershell.commands.basichtmlwebresponseobject).</span></span>

<span data-ttu-id="be89b-426">Aufgrund von Änderungen in .net Core 3,1 verwenden PowerShell 7,0 und höher die [HttpClient. defaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) -Eigenschaft, um die Proxykonfiguration zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="be89b-426">Because of changes in .NET Core 3.1, PowerShell 7.0 and higher use the [HttpClient.DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) Property to determine the proxy configuration.</span></span>

<span data-ttu-id="be89b-427">Der Wert dieser Eigenschaft wird von Ihrer Plattform bestimmt:</span><span class="sxs-lookup"><span data-stu-id="be89b-427">The value of this property is determined by your platform:</span></span>

- <span data-ttu-id="be89b-428">**Für Windows**: liest die Proxykonfiguration aus Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="be89b-428">**For Windows**: Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="be89b-429">Wenn diese Variablen nicht definiert sind, wird die Eigenschaft von den Proxy Einstellungen des Benutzers abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="be89b-429">If those variables are not defined the property is derived from the user's proxy settings.</span></span>
- <span data-ttu-id="be89b-430">**Für macOS**: liest die Proxykonfiguration aus Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="be89b-430">**For macOS**: Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="be89b-431">Wenn diese Variablen nicht definiert sind, wird die Eigenschaft von den Proxy Einstellungen des Systems abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="be89b-431">If those variables are not defined the property is derived from the system's proxy settings.</span></span>
- <span data-ttu-id="be89b-432">**Für Linux**: liest die Proxykonfiguration aus Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="be89b-432">**For Linux**: Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="be89b-433">Wenn diese Variablen nicht definiert sind, initialisiert die-Eigenschaft eine nicht konfigurierte-Instanz, die alle Adressen umgeht.</span><span class="sxs-lookup"><span data-stu-id="be89b-433">If those variables are not defined the property initializes a non-configured instance that bypasses all addresses.</span></span>

<span data-ttu-id="be89b-434">Die Umgebungsvariablen, die für die `DefaultProxy` Initialisierung auf Windows-und UNIX-basierten Plattformen verwendet werden, sind:</span><span class="sxs-lookup"><span data-stu-id="be89b-434">The environment variables used for `DefaultProxy` initialization on Windows and Unix-based platforms are:</span></span>

- <span data-ttu-id="be89b-435">`HTTP_PROXY`: der Hostname oder die IP-Adresse des Proxy Servers, der für HTTP-Anforderungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-435">`HTTP_PROXY`: the hostname or IP address of the proxy server used on HTTP requests.</span></span>
- <span data-ttu-id="be89b-436">`HTTPS_PROXY`: der Hostname oder die IP-Adresse des Proxy Servers, der für HTTPS-Anforderungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="be89b-436">`HTTPS_PROXY`: the hostname or IP address of the proxy server used on HTTPS requests.</span></span>
- <span data-ttu-id="be89b-437">`ALL_PROXY`: der Hostname oder die IP-Adresse des Proxy Servers, der für http-und HTTPS-Anforderungen verwendet wird, falls `HTTP_PROXY` oder `HTTPS_PROXY` nicht definiert sind.</span><span class="sxs-lookup"><span data-stu-id="be89b-437">`ALL_PROXY`: the hostname or IP address of the proxy server used on HTTP and HTTPS requests in case `HTTP_PROXY` or `HTTPS_PROXY` are not defined.</span></span>
- <span data-ttu-id="be89b-438">`NO_PROXY`: eine durch Trennzeichen getrennte Liste von Hostnamen, die von der Proxy Datei ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="be89b-438">`NO_PROXY`: a comma-separated list of hostnames that should be excluded from proxying.</span></span>

## <span data-ttu-id="be89b-439">Ähnliche Themen</span><span class="sxs-lookup"><span data-stu-id="be89b-439">Related Links</span></span>

[<span data-ttu-id="be89b-440">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="be89b-440">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="be89b-441">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="be89b-441">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="be89b-442">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="be89b-442">ConvertTo-Json</span></span>](ConvertTo-Json.md)
