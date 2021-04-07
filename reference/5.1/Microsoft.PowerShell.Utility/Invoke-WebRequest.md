---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/05/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: 4aa3b889ed00c6b0442a1191f055e1228f252631
ms.sourcegitcommit: d95a7255f6775b2973aa9473611185a5583881ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "106555524"
---
# <span data-ttu-id="690ba-102">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="690ba-102">Invoke-WebRequest</span></span>

## <span data-ttu-id="690ba-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="690ba-103">Synopsis</span></span>
<span data-ttu-id="690ba-104">Ruft Inhalte von einer Webseite im Internet ab.</span><span class="sxs-lookup"><span data-stu-id="690ba-104">Gets content from a web page on the Internet.</span></span>

## <span data-ttu-id="690ba-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="690ba-105">Syntax</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>] [-SessionVariable <String>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-CertificateThumbprint <String>]
 [-Certificate <X509Certificate>] [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>]
 [-Headers <IDictionary>] [-MaximumRedirection <Int32>] [-Method <WebRequestMethod>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>] [-ContentType <String>]
 [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="690ba-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="690ba-106">Description</span></span>

<span data-ttu-id="690ba-107">Das- `Invoke-WebRequest` Cmdlet sendet http-, HTTPS-, FTP-und File-Anforderungen an eine Webseite oder einen Webdienst.</span><span class="sxs-lookup"><span data-stu-id="690ba-107">The `Invoke-WebRequest` cmdlet sends HTTP, HTTPS, FTP, and FILE requests to a web page or web service.</span></span>
<span data-ttu-id="690ba-108">Das Cmdlet analysiert die Antwort und gibt Auflistungen von Formularen, Links, Bildern und anderen wichtigen HTML-Elementen zurück.</span><span class="sxs-lookup"><span data-stu-id="690ba-108">It parses the response and returns collections of forms, links, images, and other significant HTML elements.</span></span>

<span data-ttu-id="690ba-109">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="690ba-109">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="690ba-110">Standardmäßig kann der Skriptcode auf der Webseite ausgeführt werden, wenn die Seite analysiert wird, um die Eigenschaft aufzufüllen `ParsedHtml` .</span><span class="sxs-lookup"><span data-stu-id="690ba-110">By default, script code in the web page may be run when the page is being parsed to populate the `ParsedHtml` property.</span></span> <span data-ttu-id="690ba-111">Verwenden Sie den- `-UseBasicParsing` Schalter, um dies zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="690ba-111">Use the `-UseBasicParsing` switch to suppress this.</span></span>

## <span data-ttu-id="690ba-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="690ba-112">Examples</span></span>

### <span data-ttu-id="690ba-113">Beispiel 1: Senden einer Webanforderung</span><span class="sxs-lookup"><span data-stu-id="690ba-113">Example 1: Send a web request</span></span>

<span data-ttu-id="690ba-114">Dieser Befehl verwendet das `Invoke-WebRequest` Cmdlet, um eine Webanforderung an die Bing.com-Website zu senden.</span><span class="sxs-lookup"><span data-stu-id="690ba-114">This command uses the `Invoke-WebRequest` cmdlet to send a web request to the Bing.com site.</span></span>

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

<span data-ttu-id="690ba-115">Der erste Befehl gibt die Anforderung aus und speichert die Antwort in der `$R` Variablen.</span><span class="sxs-lookup"><span data-stu-id="690ba-115">The first command issues the request and saves the response in the `$R` variable.</span></span>

<span data-ttu-id="690ba-116">Mit dem zweiten Befehl werden die Objekte in der **AllElements** -Eigenschaft gefiltert, wobei die **Name** -Eigenschaft wie "\* Value" und der **Tagname** "Input" lautet.</span><span class="sxs-lookup"><span data-stu-id="690ba-116">The second command filters the objects in the **AllElements** property where the **name** property is like "\* Value" and the **tagName** is "INPUT".</span></span> <span data-ttu-id="690ba-117">Die gefilterten Ergebnisse werden an weitergeleitet `Select-Object` , um die Eigenschaften **Name** und **Wert** auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="690ba-117">The filtered results are piped to `Select-Object` to select the **name** and **value** properties.</span></span>

### <span data-ttu-id="690ba-118">Beispiel 2: Verwenden eines Zustands behafteten Webdiensts</span><span class="sxs-lookup"><span data-stu-id="690ba-118">Example 2: Use a stateful web service</span></span>

<span data-ttu-id="690ba-119">In diesem Beispiel wird gezeigt, wie das `Invoke-WebRequest` Cmdlet mit einem Zustands behafteten Webdienst (z. b. Facebook) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="690ba-119">This example shows how to use the `Invoke-WebRequest` cmdlet with a stateful web service, such as Facebook.</span></span>

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

<span data-ttu-id="690ba-120">Der erste Befehl verwendet das `Invoke-WebRequest` Cmdlet, um eine Anmelde Anforderung zu senden.</span><span class="sxs-lookup"><span data-stu-id="690ba-120">The first command uses the `Invoke-WebRequest` cmdlet to send a sign-in request.</span></span> <span data-ttu-id="690ba-121">Der Befehl gibt den Wert "FB" für den Wert des **sessionvariable** -Parameters an und speichert das Ergebnis in der `$R` Variablen.</span><span class="sxs-lookup"><span data-stu-id="690ba-121">The command specifies a value of "FB" for the value of the **SessionVariable** parameter, and saves the result in the `$R` variable.</span></span> <span data-ttu-id="690ba-122">Wenn der Befehl abgeschlossen ist, `$R` enthält die Variable ein **htmlwebresponseobject** , und die `$FB` Variable enthält ein **webrequestsession** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="690ba-122">When the command completes, the `$R` variable contains an **HtmlWebResponseObject** and the `$FB` variable contains a **WebRequestSession** object.</span></span>

<span data-ttu-id="690ba-123">Nachdem sich das `Invoke-WebRequest` Cmdlet bei Facebook angemeldet hat, gibt die **Status Description** -Eigenschaft des WebResponse-Objekts in der `$R` Variablen an, dass der Benutzer erfolgreich angemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="690ba-123">After the `Invoke-WebRequest` cmdlet signs in to facebook, the **StatusDescription** property of the web response object in the `$R` variable indicates that the user is signed in successfully.</span></span>

### <span data-ttu-id="690ba-124">Beispiel 3: erhalten von Links von einer Webseite</span><span class="sxs-lookup"><span data-stu-id="690ba-124">Example 3: Get links from a web page</span></span>

<span data-ttu-id="690ba-125">Dieser Befehl ruft die Links auf einer Webseite ab.</span><span class="sxs-lookup"><span data-stu-id="690ba-125">This command gets the links in a web page.</span></span>

```powershell
(Invoke-WebRequest -Uri "https://devblogs.microsoft.com/powershell/").Links.Href
```

<span data-ttu-id="690ba-126">Mit dem- `Invoke-WebRequest` Cmdlet wird der Webseiteninhalt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="690ba-126">The `Invoke-WebRequest` cmdlet gets the web page content.</span></span> <span data-ttu-id="690ba-127">Anschließend wird die Eigenschaft " **Links** " des zurückgegebenen **htmlwebresponseobject** verwendet, um die **href** -Eigenschaft der einzelnen Links anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="690ba-127">Then the **Links** property of the returned **HtmlWebResponseObject** is used to display the **Href** property of each link.</span></span>

### <span data-ttu-id="690ba-128">Beispiel 4: Erfassen von nicht erfolgreichen Nachrichten aus Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="690ba-128">Example 4: Catch non success messages from Invoke-WebRequest</span></span>

<span data-ttu-id="690ba-129">Wenn `Invoke-WebRequest` eine nicht Erfolgs-HTTP-Nachricht (404, 500 usw.) findet, wird keine Ausgabe zurückgegeben, und es wird ein Abbruch Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="690ba-129">When `Invoke-WebRequest` encounters a non-success HTTP message (404, 500, etc.), it returns no output and throws a terminating error.</span></span> <span data-ttu-id="690ba-130">Um den Fehler zu erfassen und den **Statuscode** anzuzeigen, können Sie die Ausführung in einen- `try/catch` Block einschließen.</span><span class="sxs-lookup"><span data-stu-id="690ba-130">To catch the error and view the **StatusCode** you can enclose execution in a `try/catch` block.</span></span> <span data-ttu-id="690ba-131">Im folgenden Beispiel wird gezeigt, wie dies erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="690ba-131">The following example shows how to accomplish this.</span></span>

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

<span data-ttu-id="690ba-132">Der abschließende Fehler wird durch den- `catch` Block abgefangen, der den **Statuscode** aus dem **Ausnahme** Objekt abruft.</span><span class="sxs-lookup"><span data-stu-id="690ba-132">The terminating error is caught by the `catch` block, which retrieves the **StatusCode** from the **Exception** object.</span></span>

## <span data-ttu-id="690ba-133">Parameter</span><span class="sxs-lookup"><span data-stu-id="690ba-133">Parameters</span></span>

### <span data-ttu-id="690ba-134">-Text</span><span class="sxs-lookup"><span data-stu-id="690ba-134">-Body</span></span>

<span data-ttu-id="690ba-135">Gibt den Anforderungstext an.</span><span class="sxs-lookup"><span data-stu-id="690ba-135">Specifies the body of the request.</span></span>
<span data-ttu-id="690ba-136">Der Text entspricht dem Inhalt der Anforderung, der auf die Header folgt.</span><span class="sxs-lookup"><span data-stu-id="690ba-136">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="690ba-137">Sie können einen Textwert auch über die Pipeline an senden `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="690ba-137">You can also pipe a body value to `Invoke-WebRequest`.</span></span>

<span data-ttu-id="690ba-138">Der **Body**-Parameter kann verwendet werden, um eine Liste von Abfrageparametern oder den Inhalt der Antwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="690ba-138">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="690ba-139">Wenn die Eingabe eine GET-Anforderung und der Text ein **IDictionary** (in der Regel eine Hash Tabelle) ist, wird der Text dem URI als Abfrage Parameter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="690ba-139">When the input is a GET request and the body is an **IDictionary** (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="690ba-140">Bei anderen Get-Anforderungen wird der Text als Wert des Anforderungs Texts im Standardformat festgelegt `name=value` .</span><span class="sxs-lookup"><span data-stu-id="690ba-140">For other GET requests, the body is set as the value of the request body in the standard `name=value` format.</span></span>

<span data-ttu-id="690ba-141">Wenn der Text ein Formular oder die Ausgabe eines- `Invoke-WebRequest` Aufrufes ist, legt PowerShell den Anforderungs Inhalt auf die Formularfelder fest.</span><span class="sxs-lookup"><span data-stu-id="690ba-141">When the body is a form, or it is the output of an `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>
<span data-ttu-id="690ba-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="690ba-142">For example:</span></span>

`$r = Invoke-WebRequest https://website.com/login.aspx`
`$r.Forms\[0\].Name = "MyName"`
`$r.Forms\[0\].Password = "MyPassword"`
`Invoke-RestMethod https://website.com/service.aspx -Body $r`

- <span data-ttu-id="690ba-143">ODER</span><span class="sxs-lookup"><span data-stu-id="690ba-143">or -</span></span>

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

### <span data-ttu-id="690ba-144">-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="690ba-144">-Certificate</span></span>

<span data-ttu-id="690ba-145">Gibt das Clientzertifikat an, das für eine sichere Webanforderung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="690ba-145">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="690ba-146">Geben Sie eine Variable ein, die ein Zertifikat, einen Befehl oder einen Ausdruck enthält, durch die das Zertifikat abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="690ba-146">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="690ba-147">Um ein Zertifikat zu suchen, verwenden Sie `Get-PfxCertificate` oder das- `Get-ChildItem` Cmdlet  im Zertifikat `Cert:` Laufwerk ().</span><span class="sxs-lookup"><span data-stu-id="690ba-147">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the **Certificate** (`Cert:`) drive.</span></span> <span data-ttu-id="690ba-148">Wenn das Zertifikat ungültig ist oder keine qualifizierte Zertifizierungsstelle aufweist, verursacht der Befehl einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="690ba-148">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="690ba-149">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="690ba-149">-CertificateThumbprint</span></span>

<span data-ttu-id="690ba-150">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Senden der Anforderung verfügt.</span><span class="sxs-lookup"><span data-stu-id="690ba-150">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="690ba-151">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="690ba-151">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="690ba-152">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="690ba-152">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="690ba-153">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="690ba-153">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="690ba-154">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den- `Get-Item` Befehl oder den- `Get-ChildItem` Befehl im PowerShell- `Cert:` Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="690ba-154">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

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

### <span data-ttu-id="690ba-155">-ContentType</span><span class="sxs-lookup"><span data-stu-id="690ba-155">-ContentType</span></span>

<span data-ttu-id="690ba-156">Gibt den Inhaltstyp der Webanforderung an.</span><span class="sxs-lookup"><span data-stu-id="690ba-156">Specifies the content type of the web request.</span></span>

<span data-ttu-id="690ba-157">Wenn dieser Parameter ausgelassen wird und die Anforderungs Methode Post ist, `Invoke-WebRequest` legt den Inhaltstyp auf application/x-www-form-urlencoded fest.</span><span class="sxs-lookup"><span data-stu-id="690ba-157">If this parameter is omitted and the request method is POST, `Invoke-WebRequest` sets the content type to application/x-www-form-urlencoded.</span></span> <span data-ttu-id="690ba-158">Andernfalls wird der Inhaltstyp nicht im Aufruf angegeben.</span><span class="sxs-lookup"><span data-stu-id="690ba-158">Otherwise, the content type is not specified in the call.</span></span>

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

### <span data-ttu-id="690ba-159">-Credential</span><span class="sxs-lookup"><span data-stu-id="690ba-159">-Credential</span></span>

<span data-ttu-id="690ba-160">Gibt ein Benutzerkonto an, das über die Berechtigung zum Senden der Anforderung verfügt.</span><span class="sxs-lookup"><span data-stu-id="690ba-160">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="690ba-161">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="690ba-161">The default is the current user.</span></span>

<span data-ttu-id="690ba-162">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="690ba-162">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="690ba-163">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="690ba-163">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="690ba-164">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="690ba-164">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="690ba-165">-Disablekeepalive</span><span class="sxs-lookup"><span data-stu-id="690ba-165">-DisableKeepAlive</span></span>

<span data-ttu-id="690ba-166">Gibt an, dass mit dem Cmdlet der **KeepAlive** -Wert im HTTP-Header auf **false** festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="690ba-166">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to **False**.</span></span> <span data-ttu-id="690ba-167">Standardmäßig ist **KeepAlive** auf **true**.</span><span class="sxs-lookup"><span data-stu-id="690ba-167">By default, **KeepAlive** is **True**.</span></span> <span data-ttu-id="690ba-168">**KeepAlive** richtet eine persistente Verbindung mit dem Server ein, um nachfolgende Anforderungen zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="690ba-168">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="690ba-169">-Header</span><span class="sxs-lookup"><span data-stu-id="690ba-169">-Headers</span></span>

<span data-ttu-id="690ba-170">Gibt die Header der Webanforderung an.</span><span class="sxs-lookup"><span data-stu-id="690ba-170">Specifies the headers of the web request.</span></span> <span data-ttu-id="690ba-171">Geben Sie eine Hashtabelle oder ein Wörterbuch ein.</span><span class="sxs-lookup"><span data-stu-id="690ba-171">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="690ba-172">Verwenden Sie den **userAgent** -Parameter, um **userAgent** -Header festzulegen.</span><span class="sxs-lookup"><span data-stu-id="690ba-172">To set **UserAgent** headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="690ba-173">Sie können diesen Parameter nicht verwenden, um **userAgent** -oder Cookie-Header anzugeben.</span><span class="sxs-lookup"><span data-stu-id="690ba-173">You cannot use this parameter to specify **UserAgent** or cookie headers.</span></span>

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

### <span data-ttu-id="690ba-174">-Eingabedatei</span><span class="sxs-lookup"><span data-stu-id="690ba-174">-InFile</span></span>

<span data-ttu-id="690ba-175">Ruft den Inhalt der Webanforderung aus einer Datei ab.</span><span class="sxs-lookup"><span data-stu-id="690ba-175">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="690ba-176">Geben Sie einen Pfad- und Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="690ba-176">Enter a path and file name.</span></span> <span data-ttu-id="690ba-177">Wenn Sie den Pfad weglassen, wird der aktuelle Speicherort als Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="690ba-177">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="690ba-178">-Maximumredirect</span><span class="sxs-lookup"><span data-stu-id="690ba-178">-MaximumRedirection</span></span>

<span data-ttu-id="690ba-179">Gibt an, wie oft PowerShell eine Verbindung an eine Alternative Uniform Resource Identifier (URI) umleitet, bevor die Verbindung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="690ba-179">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="690ba-180">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="690ba-180">The default value is 5.</span></span> <span data-ttu-id="690ba-181">Der Wert 0 (null) unterbindet sämtliche Umleitungen.</span><span class="sxs-lookup"><span data-stu-id="690ba-181">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="690ba-182">-Methode</span><span class="sxs-lookup"><span data-stu-id="690ba-182">-Method</span></span>

<span data-ttu-id="690ba-183">Gibt die für die Webanforderung verwendete Methode an.</span><span class="sxs-lookup"><span data-stu-id="690ba-183">Specifies the method used for the web request.</span></span> <span data-ttu-id="690ba-184">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="690ba-184">The acceptable values for this parameter are:</span></span>

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

### <span data-ttu-id="690ba-185">-Outfile</span><span class="sxs-lookup"><span data-stu-id="690ba-185">-OutFile</span></span>

<span data-ttu-id="690ba-186">Gibt die Ausgabedatei an, für die dieses Cmdlet den Antworttext speichert.</span><span class="sxs-lookup"><span data-stu-id="690ba-186">Specifies the output file for which this cmdlet saves the response body.</span></span> <span data-ttu-id="690ba-187">Geben Sie einen Pfad- und Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="690ba-187">Enter a path and file name.</span></span>
<span data-ttu-id="690ba-188">Wenn Sie den Pfad weglassen, wird der aktuelle Speicherort als Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="690ba-188">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="690ba-189">Standardmäßig `Invoke-WebRequest` gibt die Ergebnisse an die Pipeline zurück.</span><span class="sxs-lookup"><span data-stu-id="690ba-189">By default, `Invoke-WebRequest` returns the results to the pipeline.</span></span> <span data-ttu-id="690ba-190">Verwenden Sie den **Passthru**-Parameter, um Ergebnisse an eine Datei und an die Pipeline zu senden.</span><span class="sxs-lookup"><span data-stu-id="690ba-190">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="690ba-191">-PassThru</span><span class="sxs-lookup"><span data-stu-id="690ba-191">-PassThru</span></span>

<span data-ttu-id="690ba-192">Gibt an, dass das Cmdlet zusätzlich zum Schreiben in eine Datei die Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="690ba-192">Indicates that the cmdlet returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="690ba-193">Dieser Parameter ist nur gültig, wenn der **OutFile**-Parameter ebenfalls im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="690ba-193">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="690ba-194">-Proxy</span><span class="sxs-lookup"><span data-stu-id="690ba-194">-Proxy</span></span>

<span data-ttu-id="690ba-195">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="690ba-195">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>
<span data-ttu-id="690ba-196">Geben Sie den URI des Netzwerk-Proxyservers ein.</span><span class="sxs-lookup"><span data-stu-id="690ba-196">Enter the URI of a network proxy server.</span></span>

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

### <span data-ttu-id="690ba-197">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="690ba-197">-ProxyCredential</span></span>

<span data-ttu-id="690ba-198">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="690ba-198">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="690ba-199">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="690ba-199">The default is the current user.</span></span>

<span data-ttu-id="690ba-200">Geben Sie einen Benutzernamen ein, z. b. `User01` oder `Domain01\User01` , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="690ba-200">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="690ba-201">Dieser Parameter ist nur gültig, wenn der **Proxy** Parameter auch im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="690ba-201">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="690ba-202">Der **ProxyCredential**-Parameter und der **ProxyUseDefaultCredentials**-Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="690ba-202">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="690ba-203">-Proxyusedefault-Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="690ba-203">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="690ba-204">Gibt an, dass das Cmdlet die Anmelde Informationen des aktuellen Benutzers verwendet, um auf den Proxy Server zuzugreifen, der durch den **Proxy** Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="690ba-204">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="690ba-205">Dieser Parameter ist nur gültig, wenn der **Proxy** Parameter auch im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="690ba-205">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="690ba-206">Der **ProxyCredential**-Parameter und der **ProxyUseDefaultCredentials**-Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="690ba-206">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="690ba-207">-Sessionvariable</span><span class="sxs-lookup"><span data-stu-id="690ba-207">-SessionVariable</span></span>

<span data-ttu-id="690ba-208">Gibt eine Variable an, für die dieses Cmdlet eine Webanforderungs Sitzung erstellt und im Wert speichert.</span><span class="sxs-lookup"><span data-stu-id="690ba-208">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="690ba-209">Geben Sie einen Variablennamen ohne das Dollarzeichen `$` Symbol () ein.</span><span class="sxs-lookup"><span data-stu-id="690ba-209">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="690ba-210">Wenn Sie eine Sitzungs Variable angeben, `Invoke-WebRequest` erstellt ein Webanforderungs-Sitzungs Objekt und weist es einer Variablen mit dem angegebenen Namen in der PowerShell-Sitzung zu.</span><span class="sxs-lookup"><span data-stu-id="690ba-210">When you specify a session variable, `Invoke-WebRequest` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="690ba-211">Sie können die Variable in der Sitzung verwenden, sobald der Befehl abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="690ba-211">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="690ba-212">Im Gegensatz zu einer Remotesitzung besteht bei der Webanforderungssitzung keine persistente Verbindung.</span><span class="sxs-lookup"><span data-stu-id="690ba-212">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="690ba-213">Es handelt sich um ein Objekt, das Informationen über die Verbindung und die Anforderung enthält, einschließlich Cookies, Anmeldeinformationen, dem Maximalwert für Umleitungen und der Zeichenfolge des Benutzer-Agents.</span><span class="sxs-lookup"><span data-stu-id="690ba-213">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="690ba-214">Sie können das Objekt verwenden, um den Zustand und die Daten übergreifend für Webanforderungen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="690ba-214">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="690ba-215">Um die Webanforderungssitzung in nachfolgenden Webanforderungen zu verwenden, geben Sie die Sitzungsvariable im Wert des **WebSession**-Parameters an.</span><span class="sxs-lookup"><span data-stu-id="690ba-215">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="690ba-216">PowerShell verwendet die Daten im Sitzungs Objekt der Webanforderung, wenn die neue Verbindung hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="690ba-216">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="690ba-217">Um einen Wert in der Webanforderungssitzung zu überschreiben, verwenden Sie einen Cmdletparameter wie **UserAgent** oder **Credential**.</span><span class="sxs-lookup"><span data-stu-id="690ba-217">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="690ba-218">Parameterwerte haben Vorrang vor Werten in der Webanforderungssitzung.</span><span class="sxs-lookup"><span data-stu-id="690ba-218">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="690ba-219">Der **sessionvariable** -Parameter und der **websession** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="690ba-219">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="690ba-220">-Timeoutsec</span><span class="sxs-lookup"><span data-stu-id="690ba-220">-TimeoutSec</span></span>

<span data-ttu-id="690ba-221">Gibt an, wie lange die Anforderung ausstehend sein kann, bevor eine Zeitüberschreitung auftritt. Geben Sie einen Wert in Sekunden ein.</span><span class="sxs-lookup"><span data-stu-id="690ba-221">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="690ba-222">Der Standardwert 0 (null) steht für einen unbegrenzten Zeitüberschreitungswert.</span><span class="sxs-lookup"><span data-stu-id="690ba-222">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="690ba-223">Eine Domain Name System (DNS)-Abfrage kann bis zu 15 Sekunden dauern, bis eine Rückgabe oder ein Timeout auftritt. Wenn Ihre Anforderung einen Hostnamen enthält, der aufgelöst werden muss, und Sie **timeoutsec** auf einen Wert größer als 0 (null), aber weniger als 15 Sekunden festlegen, kann es 15 Sekunden oder länger dauern, bis eine **WebException** ausgelöst wird und für Ihre Anforderung ein Timeout eintritt.</span><span class="sxs-lookup"><span data-stu-id="690ba-223">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a **WebException** is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="690ba-224">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="690ba-224">-TransferEncoding</span></span>

<span data-ttu-id="690ba-225">Gibt einen Wert für den HTTP-Antwortheader transfer-encoding an.</span><span class="sxs-lookup"><span data-stu-id="690ba-225">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="690ba-226">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="690ba-226">The acceptable values for this parameter are:</span></span>

- `Chunked`
- `Compress`
- `Deflate`
- `GZip`
- `Identity`

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

### <span data-ttu-id="690ba-227">-URI</span><span class="sxs-lookup"><span data-stu-id="690ba-227">-Uri</span></span>

<span data-ttu-id="690ba-228">Gibt den URI (Uniform Resource Identifier) der Internetressource an, an die die Webanforderung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="690ba-228">Specifies the Uniform Resource Identifier (URI) of the Internet resource to which the web request is sent.</span></span> <span data-ttu-id="690ba-229">Geben Sie einen URI ein.</span><span class="sxs-lookup"><span data-stu-id="690ba-229">Enter a URI.</span></span> <span data-ttu-id="690ba-230">Dieser Parameter unterstützt HTTP-, HTTPS-, FTP- und FILE-Werte.</span><span class="sxs-lookup"><span data-stu-id="690ba-230">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="690ba-231">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="690ba-231">This parameter is required.</span></span>

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

### <span data-ttu-id="690ba-232">-Usebasicparamesing</span><span class="sxs-lookup"><span data-stu-id="690ba-232">-UseBasicParsing</span></span>

<span data-ttu-id="690ba-233">Gibt an, dass das Cmdlet das Antwortobjekt für HTML-Inhalt ohne Dokumentobjektmodell (DOM)-Verarbeitung verwendet.</span><span class="sxs-lookup"><span data-stu-id="690ba-233">Indicates that the cmdlet uses the response object for HTML content without Document Object Model (DOM) parsing.</span></span> <span data-ttu-id="690ba-234">Dieser Parameter ist erforderlich, wenn Internet Explorer nicht auf den Computern installiert ist, wie z. B. im Falle einer Server Core-Installation eines Windows Server-Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="690ba-234">This parameter is required when Internet Explorer is not installed on the computers, such as on a Server Core installation of a Windows Server operating system.</span></span>

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

### <span data-ttu-id="690ba-235">-Usedefault-Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="690ba-235">-UseDefaultCredentials</span></span>

<span data-ttu-id="690ba-236">Gibt an, dass das Cmdlet die Anmelde Informationen des aktuellen Benutzers verwendet, um die Webanforderung zu senden.</span><span class="sxs-lookup"><span data-stu-id="690ba-236">Indicates that the cmdlet uses the credentials of the current user to send the web request.</span></span>

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

### <span data-ttu-id="690ba-237">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="690ba-237">-UserAgent</span></span>

<span data-ttu-id="690ba-238">Gibt eine Benutzer-Agent-Zeichenfolge für die Webanforderung an.</span><span class="sxs-lookup"><span data-stu-id="690ba-238">Specifies a user agent string for the web request.</span></span> <span data-ttu-id="690ba-239">Der Standard-Benutzer-Agent ähnelt `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` mit geringfügigen Abweichungen für die einzelnen Betriebssysteme und Plattformen.</span><span class="sxs-lookup"><span data-stu-id="690ba-239">The default user agent is similar to `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="690ba-240">Um eine Website mit der standardmäßigen Benutzer-Agent-Zeichenfolge zu testen, die von den meisten Internet Browsern verwendet wird, verwenden Sie die Eigenschaften der Klasse [psuseragent](/dotnet/api/microsoft.powershell.commands.psuseragent) , z. b. Chrome, Firefox, Internet Explorer, Opera und Safari.</span><span class="sxs-lookup"><span data-stu-id="690ba-240">To test a website with the standard user agent string that is used by most Internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span> <span data-ttu-id="690ba-241">Der folgende Befehl verwendet z. b. die Benutzer-Agent-Zeichenfolge für Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="690ba-241">For example, the following command uses the user agent string for Internet Explorer</span></span>

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

### <span data-ttu-id="690ba-242">-Websession</span><span class="sxs-lookup"><span data-stu-id="690ba-242">-WebSession</span></span>

<span data-ttu-id="690ba-243">Gibt eine Webanforderungssitzung an.</span><span class="sxs-lookup"><span data-stu-id="690ba-243">Specifies a web request session.</span></span> <span data-ttu-id="690ba-244">Geben Sie den Variablennamen einschließlich des Dollar Zeichens ( `$` ) ein.</span><span class="sxs-lookup"><span data-stu-id="690ba-244">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="690ba-245">Um einen Wert in der Webanforderungssitzung zu überschreiben, verwenden Sie einen Cmdletparameter wie **UserAgent** oder **Credential**.</span><span class="sxs-lookup"><span data-stu-id="690ba-245">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="690ba-246">Parameterwerte haben Vorrang vor Werten in der Webanforderungssitzung.</span><span class="sxs-lookup"><span data-stu-id="690ba-246">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="690ba-247">Im Gegensatz zu einer Remotesitzung besteht bei der Webanforderungssitzung keine persistente Verbindung.</span><span class="sxs-lookup"><span data-stu-id="690ba-247">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="690ba-248">Es handelt sich um ein Objekt, das Informationen über die Verbindung und die Anforderung enthält, einschließlich Cookies, Anmeldeinformationen, dem Maximalwert für Umleitungen und der Zeichenfolge des Benutzer-Agents.</span><span class="sxs-lookup"><span data-stu-id="690ba-248">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="690ba-249">Sie können das Objekt verwenden, um den Zustand und die Daten übergreifend für Webanforderungen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="690ba-249">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="690ba-250">Um eine Webanforderungs Sitzung zu erstellen, geben Sie einen Variablennamen (ohne Dollarzeichen) in den Wert des **sessionvariable** -Parameters eines `Invoke-WebRequest` Befehls ein.</span><span class="sxs-lookup"><span data-stu-id="690ba-250">To create a web request session, enter a variable name (without a dollar sign) in the value of the **SessionVariable** parameter of an `Invoke-WebRequest` command.</span></span> <span data-ttu-id="690ba-251">`Invoke-WebRequest` erstellt die Sitzung und speichert Sie in der Variablen.</span><span class="sxs-lookup"><span data-stu-id="690ba-251">`Invoke-WebRequest` creates the session and saves it in the variable.</span></span> <span data-ttu-id="690ba-252">In allen nachfolgenden Befehlen verwenden Sie die Variable als Wert für den **WebSession**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="690ba-252">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="690ba-253">Der **sessionvariable** -Parameter und der **websession** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="690ba-253">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="690ba-254">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="690ba-254">CommonParameters</span></span>

<span data-ttu-id="690ba-255">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="690ba-255">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="690ba-256">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="690ba-256">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="690ba-257">Eingaben</span><span class="sxs-lookup"><span data-stu-id="690ba-257">Inputs</span></span>

### <span data-ttu-id="690ba-258">System.Object</span><span class="sxs-lookup"><span data-stu-id="690ba-258">System.Object</span></span>

<span data-ttu-id="690ba-259">Sie können den Text einer Webanforderung an übergeben `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="690ba-259">You can pipe the body of a web request to `Invoke-WebRequest`.</span></span>

## <span data-ttu-id="690ba-260">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="690ba-260">Outputs</span></span>

### <span data-ttu-id="690ba-261">Microsoft.PowerShell.Commands.Htmlwebresponseobject</span><span class="sxs-lookup"><span data-stu-id="690ba-261">Microsoft.PowerShell.Commands.HtmlWebResponseObject</span></span>

## <span data-ttu-id="690ba-262">Hinweise</span><span class="sxs-lookup"><span data-stu-id="690ba-262">Notes</span></span>

## <span data-ttu-id="690ba-263">Ähnliche Themen</span><span class="sxs-lookup"><span data-stu-id="690ba-263">Related Links</span></span>

[<span data-ttu-id="690ba-264">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="690ba-264">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="690ba-265">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="690ba-265">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="690ba-266">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="690ba-266">ConvertTo-Json</span></span>](ConvertTo-Json.md)
