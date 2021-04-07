---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/05/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RestMethod
ms.openlocfilehash: 916c221a4fb0886494a4632e38f25a639d5d414e
ms.sourcegitcommit: d95a7255f6775b2973aa9473611185a5583881ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "106555506"
---
# <span data-ttu-id="a615b-103">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="a615b-103">Invoke-RestMethod</span></span>

## <span data-ttu-id="a615b-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a615b-104">Synopsis</span></span>
<span data-ttu-id="a615b-105">Sendet eine HTTP- oder HTTPS-Anforderung an einen RESTful-Webdienst.</span><span class="sxs-lookup"><span data-stu-id="a615b-105">Sends an HTTP or HTTPS request to a RESTful web service.</span></span>

## <span data-ttu-id="a615b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a615b-106">Syntax</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-CertificateThumbprint <String>] [-Certificate <X509Certificate>]
 [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>] [-Headers <IDictionary>]
 [-MaximumRedirection <Int32>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials]
 [-Body <Object>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>]
 [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="a615b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a615b-107">Description</span></span>

<span data-ttu-id="a615b-108">Das `Invoke-RestMethod` -Cmdlet sendet HTTP-und HTTPS-Anforderungen an Rest (Representational State Transfer)-Webdienste, die Umfang strukturierte Daten zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a615b-108">The `Invoke-RestMethod` cmdlet sends HTTP and HTTPS requests to Representational State Transfer (REST) web services that returns richly structured data.</span></span>

<span data-ttu-id="a615b-109">Windows PowerShell formatiert die Antwort auf der Grundlage des Datentyps.</span><span class="sxs-lookup"><span data-stu-id="a615b-109">Windows PowerShell formats the response based to the data type.</span></span> <span data-ttu-id="a615b-110">Bei einem RSS- oder ATOM-Feed gibt Windows PowerShell den Item- oder Entry XML-Knoten zurück.</span><span class="sxs-lookup"><span data-stu-id="a615b-110">For an RSS or ATOM feed, Windows PowerShell returns the Item or Entry XML nodes.</span></span> <span data-ttu-id="a615b-111">Bei JavaScript Object Notation (JSON) oder XML konvertiert (oder deserialisiert) Windows PowerShell den Inhalt in Objekte.</span><span class="sxs-lookup"><span data-stu-id="a615b-111">For JavaScript Object Notation (JSON) or XML, Windows PowerShell converts (or deserializes) the content into objects.</span></span>

<span data-ttu-id="a615b-112">Dieses Cmdlet wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a615b-112">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="a615b-113">Standardmäßig kann der Skriptcode auf der Webseite ausgeführt werden, wenn die Seite analysiert wird, um die Eigenschaft aufzufüllen `ParsedHtml` .</span><span class="sxs-lookup"><span data-stu-id="a615b-113">By default, script code in the web page may be run when the page is being parsed to populate the `ParsedHtml` property.</span></span> <span data-ttu-id="a615b-114">Verwenden Sie den Schalter **usebasicparamesing** , um dies zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="a615b-114">Use the **UseBasicParsing** switch to suppress this.</span></span>

## <span data-ttu-id="a615b-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a615b-115">Examples</span></span>

### <span data-ttu-id="a615b-116">Beispiel 1: Holen Sie sich den PowerShell-RSS-Feed</span><span class="sxs-lookup"><span data-stu-id="a615b-116">Example 1: Get the PowerShell RSS feed</span></span>

```powershell
Invoke-RestMethod -Uri https://devblogs.microsoft.com/powershell/feed/ |
  Format-Table -Property Title, pubDate
```

```Output
Title                                                                pubDate
-----                                                                -------
Join the PowerShell 10th Anniversary Celebration!                    Tue, 08 Nov 2016 23:00:04 +0000
DSC Resource Kit November 2016 Release                               Thu, 03 Nov 2016 00:19:07 +0000
PSScriptAnalyzer Community Call - Oct 18, 2016                       Thu, 13 Oct 2016 17:52:35 +0000
New Home for In-Box DSC Resources                                    Sat, 08 Oct 2016 07:13:10 +0000
New Social Features on Gallery                                       Fri, 30 Sep 2016 23:04:34 +0000
PowerShellGet and PackageManagement in PowerShell Gallery and GitHub Thu, 29 Sep 2016 22:21:42 +0000
PowerShell Security at DerbyCon                                      Wed, 28 Sep 2016 01:13:19 +0000
DSC Resource Kit September Release                                   Thu, 22 Sep 2016 00:25:37 +0000
PowerShell DSC and implicit remoting broken in KB3176934             Tue, 23 Aug 2016 15:07:50 +0000
PowerShell on Linux and Open Source!                                 Thu, 18 Aug 2016 15:32:02 +0000
```

<span data-ttu-id="a615b-117">Dieser Befehl verwendet das `Invoke-RestMethod` Cmdlet, um Informationen aus dem PowerShell-Blog-RSS-Feed zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a615b-117">This command uses the `Invoke-RestMethod` cmdlet to get information from the PowerShell Blog RSS feed.</span></span> <span data-ttu-id="a615b-118">Der Befehl verwendet das `Format-Table` Cmdlet, um die Werte der **Titel** -und **pubDate** -Eigenschaften jedes Blogs in einer Tabelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a615b-118">The command uses the `Format-Table` cmdlet to display the values of the **Title** and **pubDate** properties of each blog in a table.</span></span>

### <span data-ttu-id="a615b-119">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="a615b-119">Example 2</span></span>

<span data-ttu-id="a615b-120">Im folgenden Beispiel führt ein Benutzer aus, `Invoke-RestMethod` um eine Post-Anforderung auf einer Intranetwebsite in der Organisation des Benutzers auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a615b-120">In the following example, a user runs `Invoke-RestMethod` to perform a POST request on an intranet website in the user's organization.</span></span>

```powershell
$Cred = Get-Credential

# Next, allow the use of self-signed SSL certificates.

[System.Net.ServicePointManager]::ServerCertificateValidationCallback = { $True }

# Create variables to store the values consumed by the Invoke-RestMethod command.
# The search variable contents are later embedded in the body variable.

$Server = 'server.contoso.com'
$Url = "https://${server}:8089/services/search/jobs/export"
$Search = "search index=_internal | reverse | table index,host,source,sourcetype,_raw"

# The cmdlet handles URL encoding. The body variable describes the search criteria, specifies CSV as
# the output mode, and specifies a time period for returned data that starts two days ago and ends
# one day ago. The body variable specifies values for parameters that apply to the particular REST
# API with which Invoke-RestMethod is communicating.

$Body = @{
    search = $Search
    output_mode = "csv"
    earliest_time = "-2d@d"
    latest_time = "-1d@d"
}

# Now, run the Invoke-RestMethod command with all variables in place, specifying a path and file
# name for the resulting CSV output file.

Invoke-RestMethod -Method Post -Uri $url -Credential $Cred -Body $body -OutFile output.csv

{"preview":true,"offset":0,"result":{"sourcetype":"contoso1","count":"9624"}}

{"preview":true,"offset":1,"result":{"sourcetype":"contoso2","count":"152"}}

{"preview":true,"offset":2,"result":{"sourcetype":"contoso3","count":"88494"}}

{"preview":true,"offset":3,"result":{"sourcetype":"contoso4","count":"15277"}}
```

### <span data-ttu-id="a615b-121">Beispiel 3: übergeben mehrerer Header</span><span class="sxs-lookup"><span data-stu-id="a615b-121">Example 3: Pass multiple headers</span></span>

<span data-ttu-id="a615b-122">In diesem Beispiel wird veranschaulicht, wie mehrere Header von einem `hash-table` an eine Rest-API übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a615b-122">This example demonstrates, how to pass multiple headers in from a `hash-table` to a REST API.</span></span>

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

<span data-ttu-id="a615b-123">APIs erfordern häufig übergebenen Header für Authentifizierung, Validierung usw.</span><span class="sxs-lookup"><span data-stu-id="a615b-123">APIs often require passed headers for authentication, validation etc.</span></span>

### <span data-ttu-id="a615b-124">Beispiel 3: Senden von Formulardaten</span><span class="sxs-lookup"><span data-stu-id="a615b-124">Example 3: Submitting form data</span></span>

<span data-ttu-id="a615b-125">Wenn der Text ein Formular oder die Ausgabe eines anderen `Invoke-WebRequest` Aufrufes ist, legt PowerShell den Anforderungs Inhalt auf die Formularfelder fest.</span><span class="sxs-lookup"><span data-stu-id="a615b-125">When the body is a form, or it is the output of another `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>

<span data-ttu-id="a615b-126">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a615b-126">For example:</span></span>

```powershell
$R = Invoke-WebRequest https://website.com/login.aspx
$R.Forms[0].Name = "MyName"
$R.Forms[0].Password = "MyPassword"
Invoke-RestMethod https://website.com/service.aspx -Body $R.Forms[0]
```

## <span data-ttu-id="a615b-127">Parameter</span><span class="sxs-lookup"><span data-stu-id="a615b-127">Parameters</span></span>

### <span data-ttu-id="a615b-128">-Text</span><span class="sxs-lookup"><span data-stu-id="a615b-128">-Body</span></span>

<span data-ttu-id="a615b-129">Gibt den Anforderungstext an.</span><span class="sxs-lookup"><span data-stu-id="a615b-129">Specifies the body of the request.</span></span> <span data-ttu-id="a615b-130">Der Text entspricht dem Inhalt der Anforderung, der auf die Header folgt.</span><span class="sxs-lookup"><span data-stu-id="a615b-130">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="a615b-131">Sie können einen Textwert auch über die Pipeline an senden `Invoke-RestMethod` .</span><span class="sxs-lookup"><span data-stu-id="a615b-131">You can also pipe a body value to `Invoke-RestMethod`.</span></span>

<span data-ttu-id="a615b-132">Der **Body**-Parameter kann verwendet werden, um eine Liste von Abfrageparametern oder den Inhalt der Antwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a615b-132">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="a615b-133">Wenn die Eingabe eine GET-Anforderung und der Text ein IDictionary-Objekt (i. d. r. eine Hashtabelle) ist, wird der Text dem URI als Abfrageparameter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a615b-133">When the input is a GET request, and the body is an IDictionary (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="a615b-134">Für andere Anforderungstypen (z. B. POST) wird der Text als Wert des Anforderungstexts im Format „Standardname=Wertformat“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a615b-134">For other request types (such as POST), the body is set as the value of the request body in the standard name=value format.</span></span>

> [!WARNING]
> <span data-ttu-id="a615b-135">Die ausführliche Ausgabe eines Post-Texts endet mit `with -1-byte payload` , auch wenn die Größe des Texts im HTTP-Header bekannt ist und gesendet wird `Content-Length` .</span><span class="sxs-lookup"><span data-stu-id="a615b-135">The verbose output of a POST body will end with `with -1-byte payload`, even though the size of the body is both known and sent in the `Content-Length` HTTP header.</span></span>

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

### <span data-ttu-id="a615b-136">-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="a615b-136">-Certificate</span></span>

<span data-ttu-id="a615b-137">Gibt das Clientzertifikat an, das für eine sichere Webanforderung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a615b-137">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="a615b-138">Geben Sie eine Variable ein, die ein Zertifikat, einen Befehl oder einen Ausdruck enthält, durch die das Zertifikat abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a615b-138">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="a615b-139">Um ein Zertifikat zu suchen, verwenden Sie `Get-PfxCertificate` oder das- `Get-ChildItem` Cmdlet im Zertifikat `Cert:` Laufwerk ().</span><span class="sxs-lookup"><span data-stu-id="a615b-139">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="a615b-140">Wenn das Zertifikat ungültig ist oder keine qualifizierte Zertifizierungsstelle aufweist, verursacht der Befehl einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="a615b-140">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="a615b-141">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="a615b-141">-CertificateThumbprint</span></span>

<span data-ttu-id="a615b-142">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Senden der Anforderung verfügt.</span><span class="sxs-lookup"><span data-stu-id="a615b-142">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="a615b-143">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="a615b-143">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="a615b-144">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a615b-144">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="a615b-145">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="a615b-145">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="a615b-146">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den- `Get-Item` Befehl oder den- `Get-ChildItem` Befehl im Windows PowerShell- `Cert:` Laufwerk ().</span><span class="sxs-lookup"><span data-stu-id="a615b-146">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the Windows PowerShell (`Cert:`) drive.</span></span>

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

### <span data-ttu-id="a615b-147">-ContentType</span><span class="sxs-lookup"><span data-stu-id="a615b-147">-ContentType</span></span>

<span data-ttu-id="a615b-148">Gibt den Inhaltstyp der Webanforderung an.</span><span class="sxs-lookup"><span data-stu-id="a615b-148">Specifies the content type of the web request.</span></span>

<span data-ttu-id="a615b-149">Wenn dieser Parameter ausgelassen wird und die Anforderungs Methode Post ist, `Invoke-RestMethod` legt den Inhaltstyp auf application/x-www-form-urlencoded fest.</span><span class="sxs-lookup"><span data-stu-id="a615b-149">If this parameter is omitted and the request method is POST, `Invoke-RestMethod` sets the content type to "application/x-www-form-urlencoded".</span></span> <span data-ttu-id="a615b-150">Andernfalls wird der Inhaltstyp nicht im Aufruf angegeben.</span><span class="sxs-lookup"><span data-stu-id="a615b-150">Otherwise, the content type is not specified in the call.</span></span>

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

### <span data-ttu-id="a615b-151">-Credential</span><span class="sxs-lookup"><span data-stu-id="a615b-151">-Credential</span></span>

<span data-ttu-id="a615b-152">Gibt ein Benutzerkonto an, das über die Berechtigung zum Senden der Anforderung verfügt.</span><span class="sxs-lookup"><span data-stu-id="a615b-152">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="a615b-153">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a615b-153">The default is the current user.</span></span>

<span data-ttu-id="a615b-154">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a615b-154">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="a615b-155">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a615b-155">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="a615b-156">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="a615b-156">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="a615b-157">-Disablekeepalive</span><span class="sxs-lookup"><span data-stu-id="a615b-157">-DisableKeepAlive</span></span>

<span data-ttu-id="a615b-158">Legt den **KeepAlive**-Wert im HTTP-Header auf „False“ fest.</span><span class="sxs-lookup"><span data-stu-id="a615b-158">Sets the **KeepAlive** value in the HTTP header to False.</span></span> <span data-ttu-id="a615b-159">Der Standardwert von **KeepAlive** ist „True“.</span><span class="sxs-lookup"><span data-stu-id="a615b-159">By default, **KeepAlive** is True.</span></span>
<span data-ttu-id="a615b-160">**KeepAlive** richtet eine persistente Verbindung mit dem Server ein, um nachfolgende Anforderungen zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="a615b-160">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: KeepAlive
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a615b-161">-Header</span><span class="sxs-lookup"><span data-stu-id="a615b-161">-Headers</span></span>

<span data-ttu-id="a615b-162">Gibt die Header der Webanforderung an.</span><span class="sxs-lookup"><span data-stu-id="a615b-162">Specifies the headers of the web request.</span></span> <span data-ttu-id="a615b-163">Geben Sie eine Hashtabelle oder ein Wörterbuch ein.</span><span class="sxs-lookup"><span data-stu-id="a615b-163">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="a615b-164">Verwenden Sie zum Festlegen der UserAgent-Header den **UserAgent**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="a615b-164">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="a615b-165">Sie können diesen Parameter nicht verwenden, um UserAgent- oder Cookieheader anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a615b-165">You cannot use this parameter to specify UserAgent or cookie headers.</span></span>

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

### <span data-ttu-id="a615b-166">-Eingabedatei</span><span class="sxs-lookup"><span data-stu-id="a615b-166">-InFile</span></span>

<span data-ttu-id="a615b-167">Ruft den Inhalt der Webanforderung aus einer Datei ab.</span><span class="sxs-lookup"><span data-stu-id="a615b-167">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="a615b-168">Geben Sie einen Pfad- und Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="a615b-168">Enter a path and file name.</span></span> <span data-ttu-id="a615b-169">Wenn Sie den Pfad weglassen, wird der aktuelle Speicherort als Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="a615b-169">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="a615b-170">-Maximumredirect</span><span class="sxs-lookup"><span data-stu-id="a615b-170">-MaximumRedirection</span></span>

<span data-ttu-id="a615b-171">Bestimmt, wie oft Windows PowerShell eine Verbindung an einen alternativen URI (Uniform Resource Identifier) umleitet, bevor die Verbindung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="a615b-171">Determines how many times Windows PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="a615b-172">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="a615b-172">The default value is 5.</span></span> <span data-ttu-id="a615b-173">Der Wert 0 (null) unterbindet sämtliche Umleitungen.</span><span class="sxs-lookup"><span data-stu-id="a615b-173">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="a615b-174">-Methode</span><span class="sxs-lookup"><span data-stu-id="a615b-174">-Method</span></span>

<span data-ttu-id="a615b-175">Gibt die für die Webanforderung verwendete Methode an.</span><span class="sxs-lookup"><span data-stu-id="a615b-175">Specifies the method used for the web request.</span></span> <span data-ttu-id="a615b-176">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="a615b-176">The acceptable values for this parameter are:</span></span>

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
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a615b-177">-Outfile</span><span class="sxs-lookup"><span data-stu-id="a615b-177">-OutFile</span></span>

<span data-ttu-id="a615b-178">Speichert den Antworttext in der angegebenen Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="a615b-178">Saves the response body in the specified output file.</span></span> <span data-ttu-id="a615b-179">Geben Sie einen Pfad- und Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="a615b-179">Enter a path and file name.</span></span> <span data-ttu-id="a615b-180">Wenn Sie den Pfad weglassen, wird der aktuelle Speicherort als Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="a615b-180">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="a615b-181">Standardmäßig `Invoke-RestMethod` gibt die Ergebnisse an die Pipeline zurück.</span><span class="sxs-lookup"><span data-stu-id="a615b-181">By default, `Invoke-RestMethod` returns the results to the pipeline.</span></span> <span data-ttu-id="a615b-182">Verwenden Sie den **Passthru**-Parameter, um Ergebnisse an eine Datei und an die Pipeline zu senden.</span><span class="sxs-lookup"><span data-stu-id="a615b-182">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="a615b-183">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a615b-183">-PassThru</span></span>

<span data-ttu-id="a615b-184">Gibt die Ergebnisse zurück und schreibt sie in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="a615b-184">Returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="a615b-185">Dieser Parameter ist nur gültig, wenn der **OutFile**-Parameter ebenfalls im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a615b-185">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: No output
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a615b-186">-Proxy</span><span class="sxs-lookup"><span data-stu-id="a615b-186">-Proxy</span></span>

<span data-ttu-id="a615b-187">Verwendet einen Proxyserver für die Anforderung, anstatt eine direkte Verbindung mit der Internetressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="a615b-187">Uses a proxy server for the request, rather than connecting directly to the Internet resource.</span></span> <span data-ttu-id="a615b-188">Geben Sie den URI des Netzwerk-Proxyservers ein.</span><span class="sxs-lookup"><span data-stu-id="a615b-188">Enter the URI of a network proxy server.</span></span>

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

### <span data-ttu-id="a615b-189">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="a615b-189">-ProxyCredential</span></span>

<span data-ttu-id="a615b-190">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a615b-190">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="a615b-191">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a615b-191">The default is the current user.</span></span>

<span data-ttu-id="a615b-192">Geben Sie einen Benutzernamen ein, z. B. %%amp;quot;User01%%amp;quot; oder %%amp;quot;Domain01\User01%%amp;quot;, oder geben Sie ein **PSCredential**-Objekt ein, z. B. ein vom `Get-Credential`-Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="a615b-192">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="a615b-193">Dieser Parameter ist nur gültig, wenn der **Proxy** Parameter auch im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a615b-193">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="a615b-194">Der **ProxyCredential**-Parameter und der **ProxyUseDefaultCredentials**-Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a615b-194">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="a615b-195">-Proxyusedefault-Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="a615b-195">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="a615b-196">Verwendet die Anmeldeinformationen des aktuellen Benutzers, um auf den Proxyserver zuzugreifen, der vom **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a615b-196">Uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="a615b-197">Dieser Parameter ist nur gültig, wenn der **Proxy** Parameter auch im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a615b-197">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="a615b-198">Der **ProxyCredential**-Parameter und der **ProxyUseDefaultCredentials**-Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a615b-198">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="a615b-199">-Sessionvariable</span><span class="sxs-lookup"><span data-stu-id="a615b-199">-SessionVariable</span></span>

<span data-ttu-id="a615b-200">Erstellt eine Webanforderungssitzung und speichert sie in dem Wert der angegebenen Variablen.</span><span class="sxs-lookup"><span data-stu-id="a615b-200">Creates a web request session and saves it in the value of the specified variable.</span></span> <span data-ttu-id="a615b-201">Geben Sie einen Variablennamen ohne das Dollarzeichen `$` Symbol () ein.</span><span class="sxs-lookup"><span data-stu-id="a615b-201">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="a615b-202">Wenn Sie eine Sitzungs Variable angeben, `Invoke-RestMethod` erstellt ein Webanforderungs-Sitzungs Objekt und weist es einer Variablen mit dem angegebenen Namen in der PowerShell-Sitzung zu.</span><span class="sxs-lookup"><span data-stu-id="a615b-202">When you specify a session variable, `Invoke-RestMethod` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="a615b-203">Sie können die Variable in der Sitzung verwenden, sobald der Befehl abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="a615b-203">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="a615b-204">Im Gegensatz zu einer Remotesitzung besteht bei der Webanforderungssitzung keine persistente Verbindung.</span><span class="sxs-lookup"><span data-stu-id="a615b-204">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="a615b-205">Es handelt sich um ein Objekt, das Informationen über die Verbindung und die Anforderung enthält, einschließlich Cookies, Anmeldeinformationen, dem Maximalwert für Umleitungen und der Zeichenfolge des Benutzer-Agents.</span><span class="sxs-lookup"><span data-stu-id="a615b-205">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="a615b-206">Sie können das Objekt verwenden, um den Zustand und die Daten übergreifend für Webanforderungen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="a615b-206">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="a615b-207">Um die Webanforderungssitzung in nachfolgenden Webanforderungen zu verwenden, geben Sie die Sitzungsvariable im Wert des **WebSession**-Parameters an.</span><span class="sxs-lookup"><span data-stu-id="a615b-207">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="a615b-208">Windows PowerShell verwendet die Daten im Objekt der Webanforderungssitzung beim Herstellen der neuen Verbindung.</span><span class="sxs-lookup"><span data-stu-id="a615b-208">Windows PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="a615b-209">Um einen Wert in der Webanforderungssitzung zu überschreiben, verwenden Sie einen Cmdletparameter wie **UserAgent** oder **Credential**.</span><span class="sxs-lookup"><span data-stu-id="a615b-209">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="a615b-210">Parameterwerte haben Vorrang vor Werten in der Webanforderungssitzung.</span><span class="sxs-lookup"><span data-stu-id="a615b-210">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="a615b-211">Der **sessionvariable** -Parameter und der **websession** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a615b-211">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="a615b-212">-Timeoutsec</span><span class="sxs-lookup"><span data-stu-id="a615b-212">-TimeoutSec</span></span>

<span data-ttu-id="a615b-213">Gibt an, wie lange die Anforderung ausstehend sein kann, bevor eine Zeitüberschreitung auftritt. Geben Sie einen Wert in Sekunden ein.</span><span class="sxs-lookup"><span data-stu-id="a615b-213">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="a615b-214">Der Standardwert 0 (null) steht für einen unbegrenzten Zeitüberschreitungswert.</span><span class="sxs-lookup"><span data-stu-id="a615b-214">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="a615b-215">Eine Domain Name System (DNS)-Abfrage kann bis zu 15 Sekunden dauern, bis eine Rückgabe oder ein Timeout auftritt. Wenn Ihre Anforderung einen Hostnamen enthält, der aufgelöst werden muss, und Sie timeoutsec auf einen Wert größer als 0 (null), aber weniger als 15 Sekunden festlegen, kann es 15 Sekunden oder länger dauern, bis eine WebException ausgelöst wird und für Ihre Anforderung ein Timeout eintritt.</span><span class="sxs-lookup"><span data-stu-id="a615b-215">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set TimeoutSec to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="a615b-216">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="a615b-216">-TransferEncoding</span></span>

<span data-ttu-id="a615b-217">Gibt einen Wert für den HTTP-Antwortheader transfer-encoding an.</span><span class="sxs-lookup"><span data-stu-id="a615b-217">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="a615b-218">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="a615b-218">The acceptable values for this parameter are:</span></span>

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

### <span data-ttu-id="a615b-219">-URI</span><span class="sxs-lookup"><span data-stu-id="a615b-219">-Uri</span></span>

<span data-ttu-id="a615b-220">Gibt den URI (Uniform Resource Identifier) der Internetressource an, an die die Webanforderung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="a615b-220">Specifies the Uniform Resource Identifier (URI) of the Internet resource to which the web request is sent.</span></span> <span data-ttu-id="a615b-221">Dieser Parameter unterstützt HTTP-, HTTPS-, FTP- und FILE-Werte.</span><span class="sxs-lookup"><span data-stu-id="a615b-221">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="a615b-222">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a615b-222">This parameter is required.</span></span> <span data-ttu-id="a615b-223">Der Parameter Name (**URI**) ist optional.</span><span class="sxs-lookup"><span data-stu-id="a615b-223">The parameter name (**Uri**) is optional.</span></span>

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

### <span data-ttu-id="a615b-224">-Usebasicparamesing</span><span class="sxs-lookup"><span data-stu-id="a615b-224">-UseBasicParsing</span></span>

<span data-ttu-id="a615b-225">Gibt an, dass das Cmdlet eine grundlegende-Verarbeitung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a615b-225">Indicates that the cmdlet uses basic parsing.</span></span> <span data-ttu-id="a615b-226">Das Cmdlet gibt den unformatierten HTML-Code in einem **String** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="a615b-226">The cmdlet returns the raw HTML in a **String** object.</span></span>

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

### <span data-ttu-id="a615b-227">-Usedefault-Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="a615b-227">-UseDefaultCredentials</span></span>

<span data-ttu-id="a615b-228">Er verwendet die Anmeldeinformationen des aktuellen Benutzers, um die Webanforderung zu senden.</span><span class="sxs-lookup"><span data-stu-id="a615b-228">Uses the credentials of the current user to send the web request.</span></span>

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

### <span data-ttu-id="a615b-229">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="a615b-229">-UserAgent</span></span>

<span data-ttu-id="a615b-230">Gibt eine Benutzer-Agent-Zeichenfolge für die Webanforderung an.</span><span class="sxs-lookup"><span data-stu-id="a615b-230">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="a615b-231">Der Standard-Benutzer-Agent ähnelt „Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0“ mit geringfügigen Abweichungen für die einzelnen Betriebssysteme und Plattformen.</span><span class="sxs-lookup"><span data-stu-id="a615b-231">The default user agent is similar to "Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0" with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="a615b-232">Um eine Website mit der standardmäßigen Benutzer-Agent-Zeichenfolge zu testen, die von den meisten Internet Browsern verwendet wird, verwenden Sie die Eigenschaften der Klasse [psuseragent](/dotnet/api/microsoft.powershell.commands) , z. b. Chrome, Firefox, Internet Explorer, Opera und Safari.</span><span class="sxs-lookup"><span data-stu-id="a615b-232">To test a website with the standard user agent string that is used by most Internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands) class, such as Chrome, FireFox, Internet Explorer, Opera, and Safari.</span></span>

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

### <span data-ttu-id="a615b-233">-Websession</span><span class="sxs-lookup"><span data-stu-id="a615b-233">-WebSession</span></span>

<span data-ttu-id="a615b-234">Gibt eine Webanforderungssitzung an.</span><span class="sxs-lookup"><span data-stu-id="a615b-234">Specifies a web request session.</span></span> <span data-ttu-id="a615b-235">Geben Sie den Variablennamen einschließlich des Dollar Zeichens ( `$` ) ein.</span><span class="sxs-lookup"><span data-stu-id="a615b-235">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="a615b-236">Um einen Wert in der Webanforderungssitzung zu überschreiben, verwenden Sie einen Cmdletparameter wie **UserAgent** oder **Credential**.</span><span class="sxs-lookup"><span data-stu-id="a615b-236">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="a615b-237">Parameterwerte haben Vorrang vor Werten in der Webanforderungssitzung.</span><span class="sxs-lookup"><span data-stu-id="a615b-237">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="a615b-238">Im Gegensatz zu einer Remotesitzung besteht bei der Webanforderungssitzung keine persistente Verbindung.</span><span class="sxs-lookup"><span data-stu-id="a615b-238">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="a615b-239">Es handelt sich um ein Objekt, das Informationen über die Verbindung und die Anforderung enthält, einschließlich Cookies, Anmeldeinformationen, dem Maximalwert für Umleitungen und der Zeichenfolge des Benutzer-Agents.</span><span class="sxs-lookup"><span data-stu-id="a615b-239">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="a615b-240">Sie können das Objekt verwenden, um den Zustand und die Daten übergreifend für Webanforderungen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="a615b-240">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="a615b-241">Um eine Webanforderungs Sitzung zu erstellen, geben Sie einen Variablennamen (ohne Dollarzeichen) in den Wert des **sessionvariable** -Parameters eines `Invoke-RestMethod` Befehls ein.</span><span class="sxs-lookup"><span data-stu-id="a615b-241">To create a web request session, enter a variable name (without a dollar sign) in the value of the **SessionVariable** parameter of an `Invoke-RestMethod` command.</span></span> <span data-ttu-id="a615b-242">`Invoke-RestMethod` erstellt die Sitzung und speichert Sie in der Variablen.</span><span class="sxs-lookup"><span data-stu-id="a615b-242">`Invoke-RestMethod` creates the session and saves it in the variable.</span></span> <span data-ttu-id="a615b-243">In allen nachfolgenden Befehlen verwenden Sie die Variable als Wert für den **WebSession**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="a615b-243">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="a615b-244">Der **sessionvariable** -Parameter und der **websession** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a615b-244">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="a615b-245">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a615b-245">CommonParameters</span></span>

<span data-ttu-id="a615b-246">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a615b-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a615b-247">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a615b-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a615b-248">Eingaben</span><span class="sxs-lookup"><span data-stu-id="a615b-248">Inputs</span></span>

### <span data-ttu-id="a615b-249">System.Object</span><span class="sxs-lookup"><span data-stu-id="a615b-249">System.Object</span></span>

<span data-ttu-id="a615b-250">Sie können den Text einer Webanforderung an übergeben `Invoke-RestMethod` .</span><span class="sxs-lookup"><span data-stu-id="a615b-250">You can pipe the body of a web request to `Invoke-RestMethod`.</span></span>

## <span data-ttu-id="a615b-251">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="a615b-251">Outputs</span></span>

### <span data-ttu-id="a615b-252">System.Xml.Xml-Dokument, Microsoft.PowerShell.Commands.Htmlwebresponseobject, System. String</span><span class="sxs-lookup"><span data-stu-id="a615b-252">System.Xml.XmlDocument, Microsoft.PowerShell.Commands.HtmlWebResponseObject, System.String</span></span>

<span data-ttu-id="a615b-253">Die Ausgabe des Cmdlets hängt vom Format des abgerufenen Inhalts ab.</span><span class="sxs-lookup"><span data-stu-id="a615b-253">The output of the cmdlet depends upon the format of the content that is retrieved.</span></span>

### <span data-ttu-id="a615b-254">PSObject</span><span class="sxs-lookup"><span data-stu-id="a615b-254">PSObject</span></span>

<span data-ttu-id="a615b-255">Wenn die Anforderung JSON-Zeichen folgen zurückgibt, `Invoke-RestMethod` gibt ein psobject zurück, das die Zeichen folgen darstellt.</span><span class="sxs-lookup"><span data-stu-id="a615b-255">If the request returns JSON strings, `Invoke-RestMethod` returns a PSObject that represents the strings.</span></span>

## <span data-ttu-id="a615b-256">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a615b-256">Notes</span></span>

## <span data-ttu-id="a615b-257">Ähnliche Themen</span><span class="sxs-lookup"><span data-stu-id="a615b-257">Related Links</span></span>

[<span data-ttu-id="a615b-258">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="a615b-258">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="a615b-259">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="a615b-259">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="a615b-260">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="a615b-260">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)
