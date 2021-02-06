---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-authenticodesignature?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AuthenticodeSignature
ms.openlocfilehash: 831f40e9bd24cee20eeae54a41e0b022dc6300da
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603714"
---
# <span data-ttu-id="ed449-102">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="ed449-102">Set-AuthenticodeSignature</span></span>

## <span data-ttu-id="ed449-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ed449-103">SYNOPSIS</span></span>
<span data-ttu-id="ed449-104">Fügt einem PowerShell-Skript oder einer anderen Datei eine [Authenticode](/windows-hardware/drivers/install/authenticode) -Signatur hinzu.</span><span class="sxs-lookup"><span data-stu-id="ed449-104">Adds an [Authenticode](/windows-hardware/drivers/install/authenticode) signature to a PowerShell script or other file.</span></span>

## <span data-ttu-id="ed449-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ed449-105">SYNTAX</span></span>

### <span data-ttu-id="ed449-106">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="ed449-106">ByPath (Default)</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] [-FilePath] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ed449-107">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="ed449-107">ByLiteralPath</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -LiteralPath <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ed449-108">Bycontent</span><span class="sxs-lookup"><span data-stu-id="ed449-108">ByContent</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -SourcePathOrExtension <String[]>
 -Content <Byte[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ed449-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ed449-109">DESCRIPTION</span></span>

<span data-ttu-id="ed449-110">Mit dem- `Set-AuthenticodeSignature` Cmdlet wird einer beliebigen Datei eine Authenticode-Signatur hinzugefügt, die das Subject Interface Package (SIP) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ed449-110">The `Set-AuthenticodeSignature` cmdlet adds an Authenticode signature to any file that supports Subject Interface Package (SIP).</span></span>

<span data-ttu-id="ed449-111">In einer PowerShell-Skriptdatei hat die Signatur die Form eines Textblocks, der das Ende der Anweisungen angibt, die im Skript ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ed449-111">In a PowerShell script file, the signature takes the form of a block of text that indicates the end of the instructions that are executed in the script.</span></span> <span data-ttu-id="ed449-112">Wenn beim Ausführen dieses Cmdlets eine Signatur in der Datei vorhanden ist, wird die Signatur entfernt.</span><span class="sxs-lookup"><span data-stu-id="ed449-112">If there is a signature in the file when this cmdlet runs, that signature is removed.</span></span>

## <span data-ttu-id="ed449-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ed449-113">EXAMPLES</span></span>

### <span data-ttu-id="ed449-114">Beispiel 1: Signieren eines Skripts mit einem Zertifikat aus dem lokalen Zertifikat Speicher</span><span class="sxs-lookup"><span data-stu-id="ed449-114">Example 1 - Sign a script using a certificate from the local certificate store</span></span>

<span data-ttu-id="ed449-115">Diese Befehle rufen ein Code Signaturzertifikat vom PowerShell-Zertifikat Anbieter ab und verwenden es zum Signieren eines PowerShell-Skripts.</span><span class="sxs-lookup"><span data-stu-id="ed449-115">These commands retrieve a code-signing certificate from the PowerShell certificate provider and use it to sign a PowerShell script.</span></span>

```powershell
$cert=Get-ChildItem -Path Cert:\CurrentUser\My -CodeSigningCert
Set-AuthenticodeSignature -FilePath PsTestInternet2.ps1 -Certificate $cert
```

<span data-ttu-id="ed449-116">Der erste Befehl verwendet das `Get-ChildItem` Cmdlet und den PowerShell-Zertifikat Anbieter, um die Zertifikate im `Cert:\CurrentUser\My` Unterverzeichnis des Zertifikat Speicher zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ed449-116">The first command uses the `Get-ChildItem` cmdlet and the PowerShell certificate provider to get the certificates in the `Cert:\CurrentUser\My` subdirectory of the certificate store.</span></span> <span data-ttu-id="ed449-117">Das `Cert:` Laufwerk ist das Laufwerk, das vom Zertifikat Anbieter verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="ed449-117">The `Cert:` drive is the drive exposed by the certificate provider.</span></span> <span data-ttu-id="ed449-118">Der **codeSigningCert** -Parameter, der nur vom Zertifikat Anbieter unterstützt wird, schränkt die Zertifikate ein, die für diese Zertifikate mit Code Signatur Autorität abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ed449-118">The **CodeSigningCert** parameter, which is supported only by the certificate provider, limits the certificates retrieved to those with code-signing authority.</span></span> <span data-ttu-id="ed449-119">Der Befehl speichert das Ergebnis in der `$cert` Variablen.</span><span class="sxs-lookup"><span data-stu-id="ed449-119">The command stores the result in the `$cert` variable.</span></span>

<span data-ttu-id="ed449-120">Der zweite Befehl verwendet das `Set-AuthenticodeSignature` Cmdlet, um das Skript zu signieren `PSTestInternet2.ps1` .</span><span class="sxs-lookup"><span data-stu-id="ed449-120">The second command uses the `Set-AuthenticodeSignature` cmdlet to sign the `PSTestInternet2.ps1` script.</span></span> <span data-ttu-id="ed449-121">Er verwendet den **FilePath** -Parameter, um den Namen des Skripts anzugeben, und den **Certificate** -Parameter, um anzugeben, dass das Zertifikat in der Variablen gespeichert wird `$cert` .</span><span class="sxs-lookup"><span data-stu-id="ed449-121">It uses the **FilePath** parameter to specify the name of the script and the **Certificate** parameter to specify that the certificate is stored in the `$cert` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="ed449-122">Wenn Sie den **codeSigningCert** -Parameter mit verwenden `Get-ChildItem` , werden nur Zertifikate zurückgegeben, die über eine Code Signatur Autorität verfügen und einen privaten Schlüssel enthalten.</span><span class="sxs-lookup"><span data-stu-id="ed449-122">Using the **CodeSigningCert** parameter with `Get-ChildItem` only returns certificates that have code-signing authority and contain a private key.</span></span> <span data-ttu-id="ed449-123">Wenn kein privater Schlüssel vorhanden ist, können die Zertifikate nicht zum Signieren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ed449-123">If there is no private key, the certificates cannot be used for signing.</span></span>

### <span data-ttu-id="ed449-124">Beispiel 2: Signieren eines Skripts mit einem Zertifikat aus einer PFX-Datei</span><span class="sxs-lookup"><span data-stu-id="ed449-124">Example 2 - Sign a script using a certificate from a PFX file</span></span>

<span data-ttu-id="ed449-125">Diese Befehle verwenden das `Get-PfxCertificate` Cmdlet, um ein Code Signaturzertifikat zu laden.</span><span class="sxs-lookup"><span data-stu-id="ed449-125">These commands use the `Get-PfxCertificate` cmdlet to load a code signing certificate.</span></span> <span data-ttu-id="ed449-126">Verwenden Sie ihn anschließend zum Signieren eines PowerShell-Skripts.</span><span class="sxs-lookup"><span data-stu-id="ed449-126">Then, use it to sign a PowerShell script.</span></span>

```powershell
$cert = Get-PfxCertificate -FilePath C:\Test\Mysign.pfx
Set-AuthenticodeSignature -FilePath ServerProps.ps1 -Certificate $cert
```

<span data-ttu-id="ed449-127">Der erste Befehl verwendet das `Get-PfxCertificate` Cmdlet, um das c:\test\mysign.pfx-Zertifikat in die-Variable zu laden `$cert` .</span><span class="sxs-lookup"><span data-stu-id="ed449-127">The first command uses the `Get-PfxCertificate` cmdlet to load the C:\Test\MySign.pfx certificate into the `$cert` variable.</span></span>

<span data-ttu-id="ed449-128">Der zweite Befehl verwendet `Set-AuthenticodeSignature` , um das Skript zu signieren.</span><span class="sxs-lookup"><span data-stu-id="ed449-128">The second command uses `Set-AuthenticodeSignature` to sign the script.</span></span> <span data-ttu-id="ed449-129">Der **FilePath** -Parameter von `Set-AuthenticodeSignature` gibt den Pfad der Skriptdatei an, die signiert wird, und der **CERT** -Parameter übergibt die `$cert` Variable, die das Zertifikat enthält, an `Set-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="ed449-129">The **FilePath** parameter of `Set-AuthenticodeSignature` specifies the path to the script file being signed and the **Cert** parameter passes the `$cert` variable containing the certificate to `Set-AuthenticodeSignature`.</span></span>

<span data-ttu-id="ed449-130">Wenn die Zertifikat Datei Kenn Wort geschützt ist, werden Sie von PowerShell zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ed449-130">If the certificate file is password protected, PowerShell prompts you for the password.</span></span>

### <span data-ttu-id="ed449-131">Beispiel 3: Hinzufügen einer Signatur, die die Stamm Zertifizierungsstelle enthält</span><span class="sxs-lookup"><span data-stu-id="ed449-131">Example 3 - Add a signature that includes the root authority</span></span>

<span data-ttu-id="ed449-132">Dieser Befehl fügt eine digitale Signatur hinzu, die die Stammzertifizierungsstelle in der Vertrauenskette enthält, und wird von einem Zeitstempelserver eines Drittanbieters signiert.</span><span class="sxs-lookup"><span data-stu-id="ed449-132">This command adds a digital signature that includes the root authority in the trust chain, and it is signed by a third-party timestamp server.</span></span>

```powershell
Set-AuthenticodeSignature -FilePath c:\scripts\Remodel.ps1 -Certificate $cert -IncludeChain All -TimestampServer "http://timestamp.fabrikam.com/scripts/timstamper.dll"
```

<span data-ttu-id="ed449-133">Der Befehl verwendet den **FilePath** -Parameter, um das signierte Skript anzugeben, und den **Certificate** -Parameter, um das Zertifikat anzugeben, das in der Variablen gespeichert wird `$cert` .</span><span class="sxs-lookup"><span data-stu-id="ed449-133">The command uses the **FilePath** parameter to specify the script being signed and the **Certificate** parameter to specify the certificate that is saved in the `$cert` variable.</span></span> <span data-ttu-id="ed449-134">Er verwendet den **incluentchain** -Parameter, um alle Signaturen in der Vertrauenskette einzuschließen, einschließlich der Stamm Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="ed449-134">It uses the **IncludeChain** parameter to include all of the signatures in the trust chain, including the root authority.</span></span> <span data-ttu-id="ed449-135">Außerdem verwendet er den **Timestampserver** -Parameter, um der Signatur einen Zeitstempel hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ed449-135">It also uses the **TimeStampServer** parameter to add a timestamp to the signature.</span></span>
<span data-ttu-id="ed449-136">Dadurch wird verhindert, dass das Skript bei Ablauf des Zertifikats einen Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="ed449-136">This prevents the script from failing when the certificate expires.</span></span>

## <span data-ttu-id="ed449-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ed449-137">PARAMETERS</span></span>

### <span data-ttu-id="ed449-138">-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="ed449-138">-Certificate</span></span>

<span data-ttu-id="ed449-139">Gibt das Zertifikat an, das verwendet wird, um das Skript oder die Datei zu signieren.</span><span class="sxs-lookup"><span data-stu-id="ed449-139">Specifies the certificate that will be used to sign the script or file.</span></span> <span data-ttu-id="ed449-140">Geben Sie eine Variable ein, die ein Objekt speichert, das das Zertifikat oder einen Ausdruck darstellt, der das Zertifikat abruft.</span><span class="sxs-lookup"><span data-stu-id="ed449-140">Enter a variable that stores an object representing the certificate or an expression that gets the certificate.</span></span>

<span data-ttu-id="ed449-141">Verwenden Sie `Get-PfxCertificate` das `Get-ChildItem` Cmdlet im Zertifikat Laufwerk, oder verwenden Sie es, um ein Zertifikat zu suchen `Cert:` .</span><span class="sxs-lookup"><span data-stu-id="ed449-141">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate `Cert:` drive.</span></span> <span data-ttu-id="ed449-142">Wenn das Zertifikat ungültig ist oder keine `code-signing` Autorität hat, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="ed449-142">If the certificate is not valid or does not have `code-signing` authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed449-143">-FilePath</span><span class="sxs-lookup"><span data-stu-id="ed449-143">-FilePath</span></span>

<span data-ttu-id="ed449-144">Gibt den Pfad zu einer Datei an, die signiert wird.</span><span class="sxs-lookup"><span data-stu-id="ed449-144">Specifies the path to a file that is being signed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ed449-145">-Force</span><span class="sxs-lookup"><span data-stu-id="ed449-145">-Force</span></span>

<span data-ttu-id="ed449-146">Ermöglicht es dem Cmdlet, eine Signatur an eine schreibgeschützte Datei anzufügen.</span><span class="sxs-lookup"><span data-stu-id="ed449-146">Allows the cmdlet to append a signature to a read-only file.</span></span> <span data-ttu-id="ed449-147">Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="ed449-147">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="ed449-148">-HashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="ed449-148">-HashAlgorithm</span></span>

<span data-ttu-id="ed449-149">Gibt den Hashalgorithmus an, den Windows verwendet, um die digitale Signatur für die Datei zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="ed449-149">Specifies the hashing algorithm that Windows uses to compute the digital signature for the file.</span></span>

<span data-ttu-id="ed449-150">Für PowerShell 3,0 ist der Standardwert SHA256. Dies ist der Windows-Standard Hash Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="ed449-150">For PowerShell 3.0, the default is SHA256, which is the Windows default hashing algorithm.</span></span> <span data-ttu-id="ed449-151">Für PowerShell 2,0 lautet der Standardwert SHA1.</span><span class="sxs-lookup"><span data-stu-id="ed449-151">For PowerShell 2.0, the default is SHA1.</span></span> <span data-ttu-id="ed449-152">Dateien, die mit einem anderen Hashalgorithmus signiert sind, werden auf anderen Systemen möglicherweise nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="ed449-152">Files that are signed with a different hashing algorithm might not be recognized on other systems.</span></span> <span data-ttu-id="ed449-153">Welche Algorithmen unterstützt werden, hängt von der Version des Betriebssystems ab.</span><span class="sxs-lookup"><span data-stu-id="ed449-153">Which algorithms are supported depends on the version of the operating system.</span></span>

<span data-ttu-id="ed449-154">Eine Liste möglicher Werte finden Sie unter [hashalgorithmname-Struktur](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties).</span><span class="sxs-lookup"><span data-stu-id="ed449-154">For a list of possible values, see [HashAlgorithmName Struct](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: SHA256
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed449-155">-Incluentchain</span><span class="sxs-lookup"><span data-stu-id="ed449-155">-IncludeChain</span></span>

<span data-ttu-id="ed449-156">Bestimmt, welche Zertifikate in der Zertifikatvertrauenskette in der digitalen Signatur enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ed449-156">Determines which certificates in the certificate trust chain are included in the digital signature.</span></span>
<span data-ttu-id="ed449-157">**Notroot** ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="ed449-157">**NotRoot** is the default.</span></span>

<span data-ttu-id="ed449-158">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ed449-158">Valid values are:</span></span>

- <span data-ttu-id="ed449-159">Signatur Geber: schließt nur das Zertifikat des Signatur Gebers ein.</span><span class="sxs-lookup"><span data-stu-id="ed449-159">Signer: Includes only the signer's certificate.</span></span>
- <span data-ttu-id="ed449-160">Notroot: schließt alle Zertifikate in der Zertifikatskette mit Ausnahme der Stamm Zertifizierungsstelle ein.</span><span class="sxs-lookup"><span data-stu-id="ed449-160">NotRoot: Includes all of the certificates in the certificate chain, except for the root authority.</span></span>
- <span data-ttu-id="ed449-161">All: schließt alle Zertifikate in der Zertifikat Kette ein.</span><span class="sxs-lookup"><span data-stu-id="ed449-161">All: Includes all the certificates in the certificate chain.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: NotRoot
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed449-162">-Timestampserver</span><span class="sxs-lookup"><span data-stu-id="ed449-162">-TimestampServer</span></span>

<span data-ttu-id="ed449-163">Verwendet den angegebenen Zeitstempelserver, um der Signatur einen Zeitstempel hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ed449-163">Uses the specified time stamp server to add a time stamp to the signature.</span></span> <span data-ttu-id="ed449-164">Geben Sie die URL des Zeitstempelservers als Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="ed449-164">Type the URL of the time stamp server as a string.</span></span>

<span data-ttu-id="ed449-165">Der Zeitstempel gibt die genaue Zeit an, zu der das Zertifikat der Datei hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="ed449-165">The time stamp represents the exact time that the certificate was added to the file.</span></span> <span data-ttu-id="ed449-166">Ein Zeitstempel verhindert, dass das Skript fehlschlägt, wenn das Zertifikat abläuft, da Benutzer und Programme sicherstellen können, dass das Zertifikat beim Signieren gültig war.</span><span class="sxs-lookup"><span data-stu-id="ed449-166">A time stamp prevents the script from failing if the certificate expires because users and programs can verify that the certificate was valid at the time of signing.</span></span>

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

### <span data-ttu-id="ed449-167">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="ed449-167">-LiteralPath</span></span>

<span data-ttu-id="ed449-168">Gibt den Pfad zu einer Datei an, die signiert wird.</span><span class="sxs-lookup"><span data-stu-id="ed449-168">Specifies the path to a file that is being signed.</span></span> <span data-ttu-id="ed449-169">Im Gegensatz zu **FilePath** wird der Wert des **LiteralPath**-Parameters genau wie eingegeben verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed449-169">Unlike **FilePath**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="ed449-170">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="ed449-170">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="ed449-171">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="ed449-171">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ed449-172">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="ed449-172">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ed449-173">-Sourceplthorextension</span><span class="sxs-lookup"><span data-stu-id="ed449-173">-SourcePathOrExtension</span></span>

<span data-ttu-id="ed449-174">Der Pfad zur Datei oder zum Dateityp des Inhalts, dem die digitale Signatur hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ed449-174">Path to the file or file type of the content for which the digital signature is added.</span></span> <span data-ttu-id="ed449-175">Dieser Parameter wird mit **Inhalten** verwendet, bei denen der Dateiinhalt als Bytearray übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ed449-175">This parameter is used with **Content** where file content is passed as a byte array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ed449-176">-Inhalt</span><span class="sxs-lookup"><span data-stu-id="ed449-176">-Content</span></span>

<span data-ttu-id="ed449-177">Der Inhalt einer Datei als Bytearray, für das die digitale Signatur hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ed449-177">Contents of a file as a byte array for which the digital signature is added.</span></span> <span data-ttu-id="ed449-178">Dieser Parameter muss mit dem **sourcepthorextension** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ed449-178">This parameter must be used with **SourcePathOrExtension** parameter.</span></span> <span data-ttu-id="ed449-179">Der Inhalt der Datei muss im Unicode-Format (UTF-16LE) vorliegen.</span><span class="sxs-lookup"><span data-stu-id="ed449-179">The contents of the file must be in Unicode (UTF-16LE) format.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ed449-180">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ed449-180">-Confirm</span></span>

<span data-ttu-id="ed449-181">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ed449-181">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed449-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ed449-182">-WhatIf</span></span>

<span data-ttu-id="ed449-183">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ed449-183">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="ed449-184">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed449-184">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed449-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ed449-185">CommonParameters</span></span>

<span data-ttu-id="ed449-186">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ed449-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ed449-187">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ed449-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ed449-188">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ed449-188">INPUTS</span></span>

### <span data-ttu-id="ed449-189">System.String</span><span class="sxs-lookup"><span data-stu-id="ed449-189">System.String</span></span>

<span data-ttu-id="ed449-190">Sie können eine Zeichenfolge, die den Dateipfad enthält, an die Pipeline übergeben `Set-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="ed449-190">You can pipe a string that contains the file path to `Set-AuthenticodeSignature`.</span></span>

## <span data-ttu-id="ed449-191">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ed449-191">OUTPUTS</span></span>

### <span data-ttu-id="ed449-192">System. Management. Automation. Signature</span><span class="sxs-lookup"><span data-stu-id="ed449-192">System.Management.Automation.Signature</span></span>

## <span data-ttu-id="ed449-193">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ed449-193">NOTES</span></span>

<span data-ttu-id="ed449-194">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ed449-194">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="ed449-195">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ed449-195">RELATED LINKS</span></span>

[<span data-ttu-id="ed449-196">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="ed449-196">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="ed449-197">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="ed449-197">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="ed449-198">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="ed449-198">Get-PfxCertificate</span></span>](Get-PfxCertificate.md)

[<span data-ttu-id="ed449-199">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="ed449-199">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)

[<span data-ttu-id="ed449-200">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="ed449-200">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="ed449-201">about_Signing</span><span class="sxs-lookup"><span data-stu-id="ed449-201">about_Signing</span></span>](../Microsoft.PowerShell.Core/About/about_Signing.md)
