---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-authenticodesignature?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AuthenticodeSignature
ms.openlocfilehash: d4d0b6cf71ac1f856d66639bccd1fce8ab91ccc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216884"
---
# <span data-ttu-id="ff9c6-103">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="ff9c6-103">Set-AuthenticodeSignature</span></span>

## <span data-ttu-id="ff9c6-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ff9c6-104">SYNOPSIS</span></span>
<span data-ttu-id="ff9c6-105">Fügt einem PowerShell-Skript oder einer anderen Datei eine [Authenticode](/windows-hardware/drivers/install/authenticode) -Signatur hinzu.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-105">Adds an [Authenticode](/windows-hardware/drivers/install/authenticode) signature to a PowerShell script or other file.</span></span>

## <span data-ttu-id="ff9c6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ff9c6-106">SYNTAX</span></span>

### <span data-ttu-id="ff9c6-107">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="ff9c6-107">ByPath (Default)</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] [-FilePath] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ff9c6-108">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="ff9c6-108">ByLiteralPath</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -LiteralPath <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ff9c6-109">Bycontent</span><span class="sxs-lookup"><span data-stu-id="ff9c6-109">ByContent</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -SourcePathOrExtension <String[]>
 -Content <Byte[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ff9c6-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ff9c6-110">DESCRIPTION</span></span>

<span data-ttu-id="ff9c6-111">Mit dem- `Set-AuthenticodeSignature` Cmdlet wird einer beliebigen Datei eine Authenticode-Signatur hinzugefügt, die das Subject Interface Package (SIP) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-111">The `Set-AuthenticodeSignature` cmdlet adds an Authenticode signature to any file that supports Subject Interface Package (SIP).</span></span>

<span data-ttu-id="ff9c6-112">In einer PowerShell-Skriptdatei hat die Signatur die Form eines Textblocks, der das Ende der Anweisungen angibt, die im Skript ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-112">In a PowerShell script file, the signature takes the form of a block of text that indicates the end of the instructions that are executed in the script.</span></span> <span data-ttu-id="ff9c6-113">Wenn beim Ausführen dieses Cmdlets eine Signatur in der Datei vorhanden ist, wird die Signatur entfernt.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-113">If there is a signature in the file when this cmdlet runs, that signature is removed.</span></span>

## <span data-ttu-id="ff9c6-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ff9c6-114">EXAMPLES</span></span>

### <span data-ttu-id="ff9c6-115">Beispiel 1: Signieren eines Skripts mit einem Zertifikat aus dem lokalen Zertifikat Speicher</span><span class="sxs-lookup"><span data-stu-id="ff9c6-115">Example 1 - Sign a script using a certificate from the local certificate store</span></span>

<span data-ttu-id="ff9c6-116">Diese Befehle rufen ein Code Signaturzertifikat vom PowerShell-Zertifikat Anbieter ab und verwenden es zum Signieren eines PowerShell-Skripts.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-116">These commands retrieve a code-signing certificate from the PowerShell certificate provider and use it to sign a PowerShell script.</span></span>

```powershell
$cert=Get-ChildItem -Path Cert:\CurrentUser\My -CodeSigningCert
Set-AuthenticodeSignature -FilePath PsTestInternet2.ps1 -Certificate $cert
```

<span data-ttu-id="ff9c6-117">Der erste Befehl verwendet das `Get-ChildItem` Cmdlet und den PowerShell-Zertifikat Anbieter, um die Zertifikate im `Cert:\CurrentUser\My` Unterverzeichnis des Zertifikat Speicher zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-117">The first command uses the `Get-ChildItem` cmdlet and the PowerShell certificate provider to get the certificates in the `Cert:\CurrentUser\My` subdirectory of the certificate store.</span></span> <span data-ttu-id="ff9c6-118">Das `Cert:` Laufwerk ist das Laufwerk, das vom Zertifikat Anbieter verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-118">The `Cert:` drive is the drive exposed by the certificate provider.</span></span> <span data-ttu-id="ff9c6-119">Der **codeSigningCert** -Parameter, der nur vom Zertifikat Anbieter unterstützt wird, schränkt die Zertifikate ein, die für diese Zertifikate mit Code Signatur Autorität abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-119">The **CodeSigningCert** parameter, which is supported only by the certificate provider, limits the certificates retrieved to those with code-signing authority.</span></span> <span data-ttu-id="ff9c6-120">Der Befehl speichert das Ergebnis in der `$cert` Variablen.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-120">The command stores the result in the `$cert` variable.</span></span>

<span data-ttu-id="ff9c6-121">Der zweite Befehl verwendet das `Set-AuthenticodeSignature` Cmdlet, um das Skript zu signieren `PSTestInternet2.ps1` .</span><span class="sxs-lookup"><span data-stu-id="ff9c6-121">The second command uses the `Set-AuthenticodeSignature` cmdlet to sign the `PSTestInternet2.ps1` script.</span></span> <span data-ttu-id="ff9c6-122">Er verwendet den **FilePath** -Parameter, um den Namen des Skripts anzugeben, und den **Certificate** -Parameter, um anzugeben, dass das Zertifikat in der Variablen gespeichert wird `$cert` .</span><span class="sxs-lookup"><span data-stu-id="ff9c6-122">It uses the **FilePath** parameter to specify the name of the script and the **Certificate** parameter to specify that the certificate is stored in the `$cert` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="ff9c6-123">Wenn Sie den **codeSigningCert** -Parameter mit verwenden `Get-ChildItem` , werden nur Zertifikate zurückgegeben, die über eine Code Signatur Autorität verfügen und einen privaten Schlüssel enthalten.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-123">Using the **CodeSigningCert** parameter with `Get-ChildItem` only returns certificates that have code-signing authority and contain a private key.</span></span> <span data-ttu-id="ff9c6-124">Wenn kein privater Schlüssel vorhanden ist, können die Zertifikate nicht zum Signieren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-124">If there is no private key, the certificates cannot be used for signing.</span></span>

### <span data-ttu-id="ff9c6-125">Beispiel 2: Signieren eines Skripts mit einem Zertifikat aus einer PFX-Datei</span><span class="sxs-lookup"><span data-stu-id="ff9c6-125">Example 2 - Sign a script using a certificate from a PFX file</span></span>

<span data-ttu-id="ff9c6-126">Diese Befehle verwenden das `Get-PfxCertificate` Cmdlet, um ein Code Signaturzertifikat zu laden.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-126">These commands use the `Get-PfxCertificate` cmdlet to load a code signing certificate.</span></span> <span data-ttu-id="ff9c6-127">Verwenden Sie ihn anschließend zum Signieren eines PowerShell-Skripts.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-127">Then, use it to sign a PowerShell script.</span></span>

```powershell
$cert = Get-PfxCertificate -FilePath C:\Test\Mysign.pfx
Set-AuthenticodeSignature -FilePath ServerProps.ps1 -Certificate $cert
```

<span data-ttu-id="ff9c6-128">Der erste Befehl verwendet das `Get-PfxCertificate` Cmdlet, um das c:\test\mysign.pfx-Zertifikat in die-Variable zu laden `$cert` .</span><span class="sxs-lookup"><span data-stu-id="ff9c6-128">The first command uses the `Get-PfxCertificate` cmdlet to load the C:\Test\MySign.pfx certificate into the `$cert` variable.</span></span>

<span data-ttu-id="ff9c6-129">Der zweite Befehl verwendet `Set-AuthenticodeSignature` , um das Skript zu signieren.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-129">The second command uses `Set-AuthenticodeSignature` to sign the script.</span></span> <span data-ttu-id="ff9c6-130">Der **FilePath** -Parameter von `Set-AuthenticodeSignature` gibt den Pfad der Skriptdatei an, die signiert wird, und der **CERT** -Parameter übergibt die `$cert` Variable, die das Zertifikat enthält, an `Set-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="ff9c6-130">The **FilePath** parameter of `Set-AuthenticodeSignature` specifies the path to the script file being signed and the **Cert** parameter passes the `$cert` variable containing the certificate to `Set-AuthenticodeSignature`.</span></span>

<span data-ttu-id="ff9c6-131">Wenn die Zertifikat Datei Kenn Wort geschützt ist, werden Sie von PowerShell zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-131">If the certificate file is password protected, PowerShell prompts you for the password.</span></span>

### <span data-ttu-id="ff9c6-132">Beispiel 3: Hinzufügen einer Signatur, die die Stamm Zertifizierungsstelle enthält</span><span class="sxs-lookup"><span data-stu-id="ff9c6-132">Example 3 - Add a signature that includes the root authority</span></span>

<span data-ttu-id="ff9c6-133">Dieser Befehl fügt eine digitale Signatur hinzu, die die Stammzertifizierungsstelle in der Vertrauenskette enthält, und wird von einem Zeitstempelserver eines Drittanbieters signiert.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-133">This command adds a digital signature that includes the root authority in the trust chain, and it is signed by a third-party timestamp server.</span></span>

```powershell
Set-AuthenticodeSignature -FilePath c:\scripts\Remodel.ps1 -Certificate $cert -IncludeChain All -TimestampServer "http://timestamp.fabrikam.com/scripts/timstamper.dll"
```

<span data-ttu-id="ff9c6-134">Der Befehl verwendet den **FilePath** -Parameter, um das signierte Skript anzugeben, und den **Certificate** -Parameter, um das Zertifikat anzugeben, das in der Variablen gespeichert wird `$cert` .</span><span class="sxs-lookup"><span data-stu-id="ff9c6-134">The command uses the **FilePath** parameter to specify the script being signed and the **Certificate** parameter to specify the certificate that is saved in the `$cert` variable.</span></span> <span data-ttu-id="ff9c6-135">Er verwendet den **incluentchain** -Parameter, um alle Signaturen in der Vertrauenskette einzuschließen, einschließlich der Stamm Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-135">It uses the **IncludeChain** parameter to include all of the signatures in the trust chain, including the root authority.</span></span> <span data-ttu-id="ff9c6-136">Außerdem verwendet er den **Timestampserver** -Parameter, um der Signatur einen Zeitstempel hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-136">It also uses the **TimeStampServer** parameter to add a timestamp to the signature.</span></span>
<span data-ttu-id="ff9c6-137">Dadurch wird verhindert, dass das Skript bei Ablauf des Zertifikats einen Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-137">This prevents the script from failing when the certificate expires.</span></span>

## <span data-ttu-id="ff9c6-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ff9c6-138">PARAMETERS</span></span>

### <span data-ttu-id="ff9c6-139">-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="ff9c6-139">-Certificate</span></span>

<span data-ttu-id="ff9c6-140">Gibt das Zertifikat an, das verwendet wird, um das Skript oder die Datei zu signieren.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-140">Specifies the certificate that will be used to sign the script or file.</span></span> <span data-ttu-id="ff9c6-141">Geben Sie eine Variable ein, die ein Objekt speichert, das das Zertifikat oder einen Ausdruck darstellt, der das Zertifikat abruft.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-141">Enter a variable that stores an object representing the certificate or an expression that gets the certificate.</span></span>

<span data-ttu-id="ff9c6-142">Verwenden Sie `Get-PfxCertificate` das `Get-ChildItem` Cmdlet im Zertifikat Laufwerk, oder verwenden Sie es, um ein Zertifikat zu suchen `Cert:` .</span><span class="sxs-lookup"><span data-stu-id="ff9c6-142">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate `Cert:` drive.</span></span> <span data-ttu-id="ff9c6-143">Wenn das Zertifikat ungültig ist oder keine `code-signing` Autorität hat, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-143">If the certificate is not valid or does not have `code-signing` authority, the command fails.</span></span>

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

### <span data-ttu-id="ff9c6-144">-FilePath</span><span class="sxs-lookup"><span data-stu-id="ff9c6-144">-FilePath</span></span>

<span data-ttu-id="ff9c6-145">Gibt den Pfad zu einer Datei an, die signiert wird.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-145">Specifies the path to a file that is being signed.</span></span>

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

### <span data-ttu-id="ff9c6-146">-Force</span><span class="sxs-lookup"><span data-stu-id="ff9c6-146">-Force</span></span>

<span data-ttu-id="ff9c6-147">Ermöglicht es dem Cmdlet, eine Signatur an eine schreibgeschützte Datei anzufügen.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-147">Allows the cmdlet to append a signature to a read-only file.</span></span> <span data-ttu-id="ff9c6-148">Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-148">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="ff9c6-149">-HashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="ff9c6-149">-HashAlgorithm</span></span>

<span data-ttu-id="ff9c6-150">Gibt den Hashalgorithmus an, den Windows verwendet, um die digitale Signatur für die Datei zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-150">Specifies the hashing algorithm that Windows uses to compute the digital signature for the file.</span></span>

<span data-ttu-id="ff9c6-151">Für PowerShell 3,0 ist der Standardwert SHA256. Dies ist der Windows-Standard Hash Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-151">For PowerShell 3.0, the default is SHA256, which is the Windows default hashing algorithm.</span></span> <span data-ttu-id="ff9c6-152">Für PowerShell 2,0 lautet der Standardwert SHA1.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-152">For PowerShell 2.0, the default is SHA1.</span></span> <span data-ttu-id="ff9c6-153">Dateien, die mit einem anderen Hashalgorithmus signiert sind, werden auf anderen Systemen möglicherweise nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-153">Files that are signed with a different hashing algorithm might not be recognized on other systems.</span></span> <span data-ttu-id="ff9c6-154">Welche Algorithmen unterstützt werden, hängt von der Version des Betriebssystems ab.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-154">Which algorithms are supported depends on the version of the operating system.</span></span>

<span data-ttu-id="ff9c6-155">Eine Liste möglicher Werte finden Sie unter [hashalgorithmname-Struktur](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties).</span><span class="sxs-lookup"><span data-stu-id="ff9c6-155">For a list of possible values, see [HashAlgorithmName Struct](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties).</span></span>

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

### <span data-ttu-id="ff9c6-156">-Incluentchain</span><span class="sxs-lookup"><span data-stu-id="ff9c6-156">-IncludeChain</span></span>

<span data-ttu-id="ff9c6-157">Bestimmt, welche Zertifikate in der Zertifikatvertrauenskette in der digitalen Signatur enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-157">Determines which certificates in the certificate trust chain are included in the digital signature.</span></span>
<span data-ttu-id="ff9c6-158">**Notroot** ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-158">**NotRoot** is the default.</span></span>

<span data-ttu-id="ff9c6-159">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ff9c6-159">Valid values are:</span></span>

- <span data-ttu-id="ff9c6-160">Signatur Geber: schließt nur das Zertifikat des Signatur Gebers ein.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-160">Signer: Includes only the signer's certificate.</span></span>
- <span data-ttu-id="ff9c6-161">Notroot: schließt alle Zertifikate in der Zertifikatskette mit Ausnahme der Stamm Zertifizierungsstelle ein.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-161">NotRoot: Includes all of the certificates in the certificate chain, except for the root authority.</span></span>
- <span data-ttu-id="ff9c6-162">All: schließt alle Zertifikate in der Zertifikat Kette ein.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-162">All: Includes all the certificates in the certificate chain.</span></span>

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

### <span data-ttu-id="ff9c6-163">-Timestampserver</span><span class="sxs-lookup"><span data-stu-id="ff9c6-163">-TimestampServer</span></span>

<span data-ttu-id="ff9c6-164">Verwendet den angegebenen Zeitstempelserver, um der Signatur einen Zeitstempel hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-164">Uses the specified time stamp server to add a time stamp to the signature.</span></span> <span data-ttu-id="ff9c6-165">Geben Sie die URL des Zeitstempelservers als Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-165">Type the URL of the time stamp server as a string.</span></span>

<span data-ttu-id="ff9c6-166">Der Zeitstempel gibt die genaue Zeit an, zu der das Zertifikat der Datei hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-166">The time stamp represents the exact time that the certificate was added to the file.</span></span> <span data-ttu-id="ff9c6-167">Ein Zeitstempel verhindert, dass das Skript fehlschlägt, wenn das Zertifikat abläuft, da Benutzer und Programme sicherstellen können, dass das Zertifikat beim Signieren gültig war.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-167">A time stamp prevents the script from failing if the certificate expires because users and programs can verify that the certificate was valid at the time of signing.</span></span>

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

### <span data-ttu-id="ff9c6-168">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="ff9c6-168">-LiteralPath</span></span>

<span data-ttu-id="ff9c6-169">Gibt den Pfad zu einer Datei an, die signiert wird.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-169">Specifies the path to a file that is being signed.</span></span> <span data-ttu-id="ff9c6-170">Im Gegensatz zu **FilePath** wird der Wert des **LiteralPath** -Parameters genau wie eingegeben verwendet.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-170">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="ff9c6-171">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-171">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="ff9c6-172">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-172">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ff9c6-173">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-173">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="ff9c6-174">-Sourceplthorextension</span><span class="sxs-lookup"><span data-stu-id="ff9c6-174">-SourcePathOrExtension</span></span>

<span data-ttu-id="ff9c6-175">Der Pfad zur Datei oder zum Dateityp des Inhalts, dem die digitale Signatur hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-175">Path to the file or file type of the content for which the digital signature is added.</span></span> <span data-ttu-id="ff9c6-176">Dieser Parameter wird mit **Inhalten** verwendet, bei denen der Dateiinhalt als Bytearray übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-176">This parameter is used with **Content** where file content is passed as a byte array.</span></span>

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

### <span data-ttu-id="ff9c6-177">-Inhalt</span><span class="sxs-lookup"><span data-stu-id="ff9c6-177">-Content</span></span>

<span data-ttu-id="ff9c6-178">Der Inhalt einer Datei als Bytearray, für das die digitale Signatur hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-178">Contents of a file as a byte array for which the digital signature is added.</span></span> <span data-ttu-id="ff9c6-179">Dieser Parameter muss mit dem **sourcepthorextension** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-179">This parameter must be used with **SourcePathOrExtension** parameter.</span></span> <span data-ttu-id="ff9c6-180">Der Inhalt der Datei muss im Unicode-Format (UTF-16LE) vorliegen.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-180">The contents of the file must be in Unicode (UTF-16LE) format.</span></span>

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

### <span data-ttu-id="ff9c6-181">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ff9c6-181">-Confirm</span></span>

<span data-ttu-id="ff9c6-182">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-182">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ff9c6-183">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ff9c6-183">-WhatIf</span></span>

<span data-ttu-id="ff9c6-184">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-184">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="ff9c6-185">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-185">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ff9c6-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ff9c6-186">CommonParameters</span></span>

<span data-ttu-id="ff9c6-187">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ff9c6-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ff9c6-188">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ff9c6-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ff9c6-189">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ff9c6-189">INPUTS</span></span>

### <span data-ttu-id="ff9c6-190">System.String</span><span class="sxs-lookup"><span data-stu-id="ff9c6-190">System.String</span></span>

<span data-ttu-id="ff9c6-191">Sie können eine Zeichenfolge, die den Dateipfad enthält, an die Pipeline übergeben `Set-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="ff9c6-191">You can pipe a string that contains the file path to `Set-AuthenticodeSignature`.</span></span>

## <span data-ttu-id="ff9c6-192">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ff9c6-192">OUTPUTS</span></span>

### <span data-ttu-id="ff9c6-193">System. Management. Automation. Signature</span><span class="sxs-lookup"><span data-stu-id="ff9c6-193">System.Management.Automation.Signature</span></span>

## <span data-ttu-id="ff9c6-194">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ff9c6-194">NOTES</span></span>

## <span data-ttu-id="ff9c6-195">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ff9c6-195">RELATED LINKS</span></span>

[<span data-ttu-id="ff9c6-196">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="ff9c6-196">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="ff9c6-197">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="ff9c6-197">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="ff9c6-198">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="ff9c6-198">Get-PfxCertificate</span></span>](Get-PfxCertificate.md)

[<span data-ttu-id="ff9c6-199">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="ff9c6-199">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)

[<span data-ttu-id="ff9c6-200">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="ff9c6-200">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="ff9c6-201">about_Signing</span><span class="sxs-lookup"><span data-stu-id="ff9c6-201">about_Signing</span></span>](../Microsoft.PowerShell.Core/About/about_Signing.md)
