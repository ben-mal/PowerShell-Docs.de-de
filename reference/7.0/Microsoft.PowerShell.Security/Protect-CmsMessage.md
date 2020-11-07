---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/protect-cmsmessage?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Protect-CmsMessage
ms.openlocfilehash: de72454f4c50746ca22853dd51e2ec0447bed101
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347634"
---
# <span data-ttu-id="23dca-103">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="23dca-103">Protect-CmsMessage</span></span>

## <span data-ttu-id="23dca-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="23dca-104">SYNOPSIS</span></span>
<span data-ttu-id="23dca-105">Verschlüsselt Inhalt mithilfe des kryptografischen Nachrichten Syntax Formats.</span><span class="sxs-lookup"><span data-stu-id="23dca-105">Encrypts content by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="23dca-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="23dca-106">SYNTAX</span></span>

### <span data-ttu-id="23dca-107">Bycontent (Standard)</span><span class="sxs-lookup"><span data-stu-id="23dca-107">ByContent (Default)</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Content] <PSObject> [[-OutFile] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="23dca-108">Bypath</span><span class="sxs-lookup"><span data-stu-id="23dca-108">ByPath</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Path] <String> [[-OutFile] <String>] [<CommonParameters>]
```

### <span data-ttu-id="23dca-109">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="23dca-109">ByLiteralPath</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-LiteralPath] <String> [[-OutFile] <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="23dca-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="23dca-110">DESCRIPTION</span></span>

<span data-ttu-id="23dca-111">Das `Protect-CmsMessage` Cmdlet verschlüsselt Inhalte mithilfe des CMS-Formats (Cryptographic Message Syntax).</span><span class="sxs-lookup"><span data-stu-id="23dca-111">The `Protect-CmsMessage` cmdlet encrypts content by using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="23dca-112">Die CMS-Cmdlets unterstützen die Verschlüsselung und Entschlüsselung von Inhalten mithilfe des IETF-Formats, wie von [RFC5652](https://tools.ietf.org/html/rfc5652.html)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="23dca-112">The CMS cmdlets support encryption and decryption of content using the IETF format as documented by [RFC5652](https://tools.ietf.org/html/rfc5652.html).</span></span>

<span data-ttu-id="23dca-113">Der CMS-Verschlüsselungsstandard verwendet die Kryptografie mit öffentlichem Schlüssel, bei der die Schlüssel zum Verschlüsseln von Inhalten (der öffentliche Schlüssel) und die Schlüssel, die zum Entschlüsseln von Inhalten (der private Schlüssel) verwendet werden, separat sind.</span><span class="sxs-lookup"><span data-stu-id="23dca-113">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="23dca-114">Ihr öffentlicher Schlüssel kann umfassend freigegeben werden, da seine Daten nicht vertraulich sind.</span><span class="sxs-lookup"><span data-stu-id="23dca-114">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="23dca-115">Wenn Inhalte mit diesem öffentlichen Schlüssel verschlüsselt sind, können sie nur mit Ihrem privaten Schlüssel entschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="23dca-115">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="23dca-116">Weitere Informationen finden Sie unter [Public-Key-Verschlüsselungsverfahren](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="23dca-116">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="23dca-117">Bevor Sie das `Protect-CmsMessage` Cmdlet ausführen können, müssen Sie ein Verschlüsselungs Zertifikat eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="23dca-117">Before you can run the `Protect-CmsMessage` cmdlet, you must have an encryption certificate set up.</span></span>
<span data-ttu-id="23dca-118">Um in PowerShell erkannt zu werden, benötigen Verschlüsselungs Zertifikate eine eindeutige[EKU](/windows/desktop/SecCrypto/eku)-ID (Extended Key Usage), um Sie als Daten Verschlüsselungs Zertifikate zu identifizieren (z. b. die IDs für Code Signierung und verschlüsselte e-Mail).</span><span class="sxs-lookup"><span data-stu-id="23dca-118">To be recognized in PowerShell, encryption certificates require a unique extended key usage ([EKU](/windows/desktop/SecCrypto/eku)) ID to identify them as data encryption certificates (such as the IDs for Code Signing and Encrypted Mail).</span></span> <span data-ttu-id="23dca-119">Ein Beispiel für ein Zertifikat, das für die Dokument Verschlüsselung funktioniert, finden Sie in Beispiel 1 in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="23dca-119">For an example of a certificate that would work for document encryption, see Example 1 in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="23dca-120">Dieses Cmdlet ist nur unter Windows verfügbar.</span><span class="sxs-lookup"><span data-stu-id="23dca-120">This cmdlet is only available on Windows.</span></span>

## <span data-ttu-id="23dca-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="23dca-121">EXAMPLES</span></span>

### <span data-ttu-id="23dca-122">Beispiel 1: Erstellen eines Zertifikats zum Verschlüsseln von Inhalten</span><span class="sxs-lookup"><span data-stu-id="23dca-122">Example 1: Create a certificate for encrypting content</span></span>

<span data-ttu-id="23dca-123">Bevor Sie das `Protect-CmsMessage` Cmdlet ausführen können, müssen Sie ein Verschlüsselungs Zertifikat erstellen.</span><span class="sxs-lookup"><span data-stu-id="23dca-123">Before you can run the `Protect-CmsMessage` cmdlet, you must create an encryption certificate.</span></span> <span data-ttu-id="23dca-124">Ändern Sie den Namen in der Betreffzeile unter Verwendung des folgenden Texts in ihren Namen, Ihre e-Mail-Adresse oder einen anderen Bezeichner, und speichern Sie das Zertifikat in einer Datei (z `DocumentEncryption.inf` . b., wie in diesem Beispiel gezeigt).</span><span class="sxs-lookup"><span data-stu-id="23dca-124">Using the following text, change the name in the Subject line to your name, email, or other identifier, and save the certificate in a file (such as `DocumentEncryption.inf`, as shown in this example).</span></span>

```powershell
# Create .INF file for certreq
{[Version]
Signature = "$Windows NT$"

[Strings]
szOID_ENHANCED_KEY_USAGE = "2.5.29.37"
szOID_DOCUMENT_ENCRYPTION = "1.3.6.1.4.1.311.80.1"

[NewRequest]
Subject = "cn=youralias@emailaddress.com"
MachineKeySet = false
KeyLength = 2048
KeySpec = AT_KEYEXCHANGE
HashAlgorithm = Sha1
Exportable = true
RequestType = Cert
KeyUsage = "CERT_KEY_ENCIPHERMENT_KEY_USAGE | CERT_DATA_ENCIPHERMENT_KEY_USAGE"
ValidityPeriod = "Years"
ValidityPeriodUnits = "1000"

[Extensions]
%szOID_ENHANCED_KEY_USAGE% = "{text}%szOID_DOCUMENT_ENCRYPTION%"
} | Out-File -FilePath DocumentEncryption.inf

# After you have created your certificate file, run the following command to add
# the certificate file to the certificate store. Now you are ready to encrypt and
# decrypt content with the next two examples.
certreq.exe -new DocumentEncryption.inf DocumentEncryption.cer
```

### <span data-ttu-id="23dca-125">Beispiel 2: Verschlüsseln einer per e-Mail gesendeten Nachricht</span><span class="sxs-lookup"><span data-stu-id="23dca-125">Example 2: Encrypt a message sent by email</span></span>

```powershell
$Protected = "Hello World" | Protect-CmsMessage -To "*youralias@emailaddress.com*"
```

<span data-ttu-id="23dca-126">Im folgenden Beispiel verschlüsseln Sie die Meldung "Hallo Welt", indem Sie Sie an das `Protect-CmsMessage` Cmdlet weiterleiten, und speichern dann die verschlüsselte Nachricht in einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="23dca-126">In the following example, you encrypt a message, "Hello World", by piping it to the `Protect-CmsMessage` cmdlet, and then save the encrypted message in a variable.</span></span> <span data-ttu-id="23dca-127">Der **to** -Parameter verwendet den Wert der Betreffzeile im Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="23dca-127">The **To** parameter uses the value of the Subject line in the certificate.</span></span>

### <span data-ttu-id="23dca-128">Beispiel 3: Anzeigen von Dokumenten Verschlüsselungs Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="23dca-128">Example 3: View document encryption certificates</span></span>

```
PS C:\> cd Cert:\CurrentUser\My
PS Cert:\CurrentUser\My> Get-ChildItem -DocumentEncryptionCert
```

<span data-ttu-id="23dca-129">Um Dokument Verschlüsselungs Zertifikate im Zertifikat Anbieter anzuzeigen, können Sie den dynamischen **documentverschlüsseltioncert** -Parameter von [Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md)hinzufügen, der nur verfügbar ist, wenn der Zertifikat Anbieter geladen wird.</span><span class="sxs-lookup"><span data-stu-id="23dca-129">To view document encryption certificates in the certificate provider, you can add the **DocumentEncryptionCert** dynamic parameter of [Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md), available only when the certificate provider is loaded.</span></span>

## <span data-ttu-id="23dca-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="23dca-130">PARAMETERS</span></span>

### <span data-ttu-id="23dca-131">-Inhalt</span><span class="sxs-lookup"><span data-stu-id="23dca-131">-Content</span></span>

<span data-ttu-id="23dca-132">Gibt ein **psobject** an, das Inhalte enthält, die Sie verschlüsseln möchten.</span><span class="sxs-lookup"><span data-stu-id="23dca-132">Specifies a **PSObject** that contains content that you want to encrypt.</span></span> <span data-ttu-id="23dca-133">Beispielsweise können Sie den Inhalt einer Ereignis Nachricht verschlüsseln und dann die Variable mit der Meldung ( `$Event` in diesem Beispiel) als Wert für den **Content** -Parameter verwenden: `$event = Get-WinEvent -ProviderName "PowerShell" -MaxEvents 1` .</span><span class="sxs-lookup"><span data-stu-id="23dca-133">For example, you can encrypt the content of an event message, and then use the variable containing the message (`$Event`, in this example) as the value of the **Content** parameter: `$event = Get-WinEvent -ProviderName "PowerShell" -MaxEvents 1`.</span></span> <span data-ttu-id="23dca-134">Sie können auch das- `Get-Content` Cmdlet verwenden, um den Inhalt einer Datei, z. b. ein Microsoft Word-Dokument, zu erhalten und den Inhalt in einer Variablen zu speichern, die Sie als Wert des **Content** -Parameters verwenden.</span><span class="sxs-lookup"><span data-stu-id="23dca-134">You can also use the `Get-Content` cmdlet to get the contents of a file, such as a Microsoft Word document, and save the content in a variable that you use as the value of the **Content** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByContent
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="23dca-135">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="23dca-135">-LiteralPath</span></span>

<span data-ttu-id="23dca-136">Gibt den Pfad zu den zu verschlüsselnden Inhalten an.</span><span class="sxs-lookup"><span data-stu-id="23dca-136">Specifies the path to content that you want to encrypt.</span></span> <span data-ttu-id="23dca-137">Im Gegensatz zu **Path** wird der Wert von **LiteralPath** genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="23dca-137">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="23dca-138">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="23dca-138">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="23dca-139">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="23dca-139">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="23dca-140">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="23dca-140">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23dca-141">-Outfile</span><span class="sxs-lookup"><span data-stu-id="23dca-141">-OutFile</span></span>

<span data-ttu-id="23dca-142">Gibt den Pfad und den Dateinamen einer Datei an, an die der verschlüsselte Inhalt gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="23dca-142">Specifies the path and file name of a file to which you want to send the encrypted content.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23dca-143">-Path</span><span class="sxs-lookup"><span data-stu-id="23dca-143">-Path</span></span>

<span data-ttu-id="23dca-144">Gibt den Pfad zu den zu verschlüsselnden Inhalten an.</span><span class="sxs-lookup"><span data-stu-id="23dca-144">Specifies the path to content that you want to encrypt.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23dca-145">Bis</span><span class="sxs-lookup"><span data-stu-id="23dca-145">-To</span></span>

<span data-ttu-id="23dca-146">Gibt einen oder mehrere CMS-Nachrichtenempfänger an, die in einem der folgenden Formate identifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="23dca-146">Specifies one or more CMS message recipients, identified in any of the following formats:</span></span>

- <span data-ttu-id="23dca-147">Ein tatsächliches Zertifikat (wie vom Zertifikat Anbieter abgerufen).</span><span class="sxs-lookup"><span data-stu-id="23dca-147">An actual certificate (as retrieved from the certificate provider).</span></span>
- <span data-ttu-id="23dca-148">Der Pfad zu der Datei, die das Zertifikat enthält.</span><span class="sxs-lookup"><span data-stu-id="23dca-148">Path to the file containing the certificate.</span></span>
- <span data-ttu-id="23dca-149">Pfad zu einem Verzeichnis, das das Zertifikat enthält.</span><span class="sxs-lookup"><span data-stu-id="23dca-149">Path to a directory containing the certificate.</span></span>
- <span data-ttu-id="23dca-150">Der Fingerabdruck des Zertifikats (dient zum Suchen im Zertifikat Speicher).</span><span class="sxs-lookup"><span data-stu-id="23dca-150">Thumbprint of the certificate (used to look in the certificate store).</span></span>
- <span data-ttu-id="23dca-151">Der Antragsteller Name des Zertifikats (das zum Suchen im Zertifikat Speicher verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="23dca-151">Subject name of the certificate (used to look in the certificate store).</span></span>

```yaml
Type: System.Management.Automation.CmsMessageRecipient[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23dca-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="23dca-152">CommonParameters</span></span>

<span data-ttu-id="23dca-153">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="23dca-153">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="23dca-154">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="23dca-154">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="23dca-155">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="23dca-155">INPUTS</span></span>

## <span data-ttu-id="23dca-156">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="23dca-156">OUTPUTS</span></span>

## <span data-ttu-id="23dca-157">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="23dca-157">NOTES</span></span>

<span data-ttu-id="23dca-158">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="23dca-158">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="23dca-159">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="23dca-159">RELATED LINKS</span></span>

[<span data-ttu-id="23dca-160">about_Providers</span><span class="sxs-lookup"><span data-stu-id="23dca-160">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="23dca-161">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="23dca-161">Get-CmsMessage</span></span>](Get-CmsMessage.md)

[<span data-ttu-id="23dca-162">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="23dca-162">Unprotect-CmsMessage</span></span>](Unprotect-CmsMessage.md)
