---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/unprotect-cmsmessage?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unprotect-CmsMessage
ms.openlocfilehash: 5897c792b16ce0b3a98e9e3cd0f1dea52cac2afd
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346376"
---
# <span data-ttu-id="ce8c1-103">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="ce8c1-103">Unprotect-CmsMessage</span></span>

## <span data-ttu-id="ce8c1-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ce8c1-104">SYNOPSIS</span></span>
<span data-ttu-id="ce8c1-105">Entschlüsselt Inhalt, der mithilfe des kryptografischen Nachrichten Syntax Formats verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-105">Decrypts content that has been encrypted by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="ce8c1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ce8c1-106">SYNTAX</span></span>

### <span data-ttu-id="ce8c1-107">Bywinevent (Standard)</span><span class="sxs-lookup"><span data-stu-id="ce8c1-107">ByWinEvent (Default)</span></span>

```
Unprotect-CmsMessage [-EventLogRecord] <PSObject> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="ce8c1-108">Bycontent</span><span class="sxs-lookup"><span data-stu-id="ce8c1-108">ByContent</span></span>

```
Unprotect-CmsMessage [-Content] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### <span data-ttu-id="ce8c1-109">Bypath</span><span class="sxs-lookup"><span data-stu-id="ce8c1-109">ByPath</span></span>

```
Unprotect-CmsMessage [-Path] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### <span data-ttu-id="ce8c1-110">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="ce8c1-110">ByLiteralPath</span></span>

```
Unprotect-CmsMessage [-LiteralPath] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="ce8c1-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ce8c1-111">DESCRIPTION</span></span>

<span data-ttu-id="ce8c1-112">Mit dem- `Unprotect-CmsMessage` Cmdlet werden Inhalte entschlüsselt, die mit dem CMS-Format (Cryptographic Message Syntax) verschlüsselt wurden.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-112">The `Unprotect-CmsMessage` cmdlet decrypts content that has been encrypted by using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="ce8c1-113">Die CMS-Cmdlets unterstützen die Verschlüsselung und Entschlüsselung von Inhalten mithilfe des IETF-Standard Formats für kryptografisch geschützte Nachrichten, wie von [RFC5652](https://tools.ietf.org/html/rfc5652)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-113">The CMS cmdlets support encryption and decryption of content using the IETF standard format for cryptographically protecting messages, as documented by [RFC5652](https://tools.ietf.org/html/rfc5652).</span></span>

<span data-ttu-id="ce8c1-114">Der CMS-Verschlüsselungsstandard verwendet die Kryptografie mit öffentlichem Schlüssel, bei der die Schlüssel zum Verschlüsseln von Inhalten (der öffentliche Schlüssel) und die Schlüssel, die zum Entschlüsseln von Inhalten (der private Schlüssel) verwendet werden, separat sind.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-114">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="ce8c1-115">Ihr öffentlicher Schlüssel kann umfassend freigegeben werden, da seine Daten nicht vertraulich sind.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-115">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="ce8c1-116">Wenn Inhalte mit diesem öffentlichen Schlüssel verschlüsselt sind, können sie nur mit Ihrem privaten Schlüssel entschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-116">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="ce8c1-117">Weitere Informationen finden Sie unter [Public-Key-Verschlüsselungsverfahren](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="ce8c1-117">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="ce8c1-118">`Unprotect-CmsMessage` entschlüsselt Inhalte, die im CMS-Format verschlüsselt wurden.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-118">`Unprotect-CmsMessage` decrypts content that has been encrypted in CMS format.</span></span> <span data-ttu-id="ce8c1-119">Sie können dieses Cmdlet ausführen, um Inhalte zu entschlüsseln, die Sie durch Ausführen des `Protect-CmsMessage` Cmdlets verschlüsselt haben.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-119">You can run this cmdlet to decrypt content that you have encrypted by running the `Protect-CmsMessage` cmdlet.</span></span> <span data-ttu-id="ce8c1-120">Sie können den Inhalt, der als Zeichenfolge entschlüsselt werden soll, durch die ID-Nummer des Verschlüsselungs Ereignisprotokoll-Datensatzes oder durch den Pfad zum verschlüsselten Inhalt angeben.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-120">You can specify content that you want to decrypt as a string, by the encryption event log record ID number, or by path to the encrypted content.</span></span> <span data-ttu-id="ce8c1-121">Mit dem- `Unprotect-CmsMessage` Cmdlet wird der entschlüsselte Inhalt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-121">The `Unprotect-CmsMessage` cmdlet returns the decrypted content.</span></span>

<span data-ttu-id="ce8c1-122">Unterstützung für Linux und macOS wurde in PowerShell 7,1 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-122">Support for Linux and macOS was added in PowerShell 7.1.</span></span>

## <span data-ttu-id="ce8c1-123">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ce8c1-123">EXAMPLES</span></span>

### <span data-ttu-id="ce8c1-124">Beispiel 1: Entschlüsseln einer Nachricht</span><span class="sxs-lookup"><span data-stu-id="ce8c1-124">Example 1: Decrypt a message</span></span>

<span data-ttu-id="ce8c1-125">Im folgenden Beispiel entschlüsseln Sie die Inhalte, die sich im literalpfad befinden `C:\Users\Test\Documents\PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="ce8c1-125">In the following example, you decrypt content that is located at the literal path `C:\Users\Test\Documents\PowerShell`.</span></span> <span data-ttu-id="ce8c1-126">Für den Wert **des Parameters erforderlich für wird** in diesem Beispiel der Fingerabdruck des Zertifikats verwendet, das zum Durchführen der Verschlüsselung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-126">For the value of the required **To** parameter, this example uses the thumbprint of the certificate that was used to perform the encryption.</span></span> <span data-ttu-id="ce8c1-127">Die entschlüsselte Meldung "try the New Break all Command" ist das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-127">The decrypted message, "Try the new Break All command," is the result.</span></span>

```powershell
$parameters = @{
  LiteralPath = "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
  To = '0f 8j b1 ab e0 ce 35 1d 67 d2 f2 6f a2 d2 00 cl 22 z9 m9 85'
}
Unprotect-CmsMessage -LiteralPath @parameters
```

```Output
Try the new Break All command
```

## <span data-ttu-id="ce8c1-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ce8c1-128">PARAMETERS</span></span>

### <span data-ttu-id="ce8c1-129">-Inhalt</span><span class="sxs-lookup"><span data-stu-id="ce8c1-129">-Content</span></span>

<span data-ttu-id="ce8c1-130">Gibt eine verschlüsselte Zeichenfolge oder eine Variable an, die eine verschlüsselte Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-130">Specifies an encrypted string, or a variable containing an encrypted string.</span></span>

```yaml
Type: System.String
Parameter Sets: ByContent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ce8c1-131">-EventLogRecord</span><span class="sxs-lookup"><span data-stu-id="ce8c1-131">-EventLogRecord</span></span>

<span data-ttu-id="ce8c1-132">Gibt eine Ereignisprotokoll-Daten Satz-ID an, die einen CMS-Verschlüsselungs Vorgang darstellt.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-132">Specifies an event log record ID that represents a CMS encryption operation.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByWinEvent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ce8c1-133">-Includecontext</span><span class="sxs-lookup"><span data-stu-id="ce8c1-133">-IncludeContext</span></span>

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

### <span data-ttu-id="ce8c1-134">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="ce8c1-134">-LiteralPath</span></span>

<span data-ttu-id="ce8c1-135">Gibt den Pfad zu verschlüsseltem Inhalt an, der entschlüsselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-135">Specifies the path to encrypted content that you want to decrypt.</span></span> <span data-ttu-id="ce8c1-136">Im Gegensatz zu **Path** wird der Wert von **LiteralPath** genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-136">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="ce8c1-137">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-137">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="ce8c1-138">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-138">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ce8c1-139">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-139">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce8c1-140">-Path</span><span class="sxs-lookup"><span data-stu-id="ce8c1-140">-Path</span></span>

<span data-ttu-id="ce8c1-141">Gibt den Pfad zu verschlüsseltem Inhalt an, der entschlüsselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-141">Specifies the path to encrypted content that you want to decrypt.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce8c1-142">Bis</span><span class="sxs-lookup"><span data-stu-id="ce8c1-142">-To</span></span>

<span data-ttu-id="ce8c1-143">Gibt einen oder mehrere CMS-Nachrichtenempfänger an, die in einem der folgenden Formate identifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="ce8c1-143">Specifies one or more CMS message recipients, identified in any of the following formats:</span></span>

- <span data-ttu-id="ce8c1-144">Ein tatsächliches Zertifikat (wie vom Zertifikat Anbieter abgerufen).</span><span class="sxs-lookup"><span data-stu-id="ce8c1-144">An actual certificate (as retrieved from the certificate provider).</span></span>
- <span data-ttu-id="ce8c1-145">Pfad zu einer Datei, die das Zertifikat enthält.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-145">Path to the a file containing the certificate.</span></span>
- <span data-ttu-id="ce8c1-146">Pfad zu einem Verzeichnis, das das Zertifikat enthält.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-146">Path to a directory containing the certificate.</span></span>
- <span data-ttu-id="ce8c1-147">Der Fingerabdruck des Zertifikats (dient zum Suchen im Zertifikat Speicher).</span><span class="sxs-lookup"><span data-stu-id="ce8c1-147">Thumbprint of the certificate (used to look in the certificate store).</span></span>
- <span data-ttu-id="ce8c1-148">Der Antragsteller Name des Zertifikats (das zum Suchen im Zertifikat Speicher verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="ce8c1-148">Subject name of the certificate (used to look in the certificate store).</span></span>

```yaml
Type: System.Management.Automation.CmsMessageRecipient[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce8c1-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ce8c1-149">CommonParameters</span></span>

<span data-ttu-id="ce8c1-150">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ce8c1-151">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ce8c1-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ce8c1-152">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ce8c1-152">INPUTS</span></span>

### <span data-ttu-id="ce8c1-153">System. Diagnostics. Eventing. Reader. EventLogRecord oder System. String</span><span class="sxs-lookup"><span data-stu-id="ce8c1-153">System.Diagnostics.Eventing.Reader.EventLogRecord or System.String</span></span>

<span data-ttu-id="ce8c1-154">Sie können ein Objekt, das verschlüsselten Inhalt enthält, an die Pipeline übergeben `Unprotect-CmsMessage` .</span><span class="sxs-lookup"><span data-stu-id="ce8c1-154">You can pipe an object containing encrypted content to `Unprotect-CmsMessage`.</span></span>

## <span data-ttu-id="ce8c1-155">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ce8c1-155">OUTPUTS</span></span>

### <span data-ttu-id="ce8c1-156">System.String</span><span class="sxs-lookup"><span data-stu-id="ce8c1-156">System.String</span></span>

<span data-ttu-id="ce8c1-157">Die unverschlüsselte Nachricht.</span><span class="sxs-lookup"><span data-stu-id="ce8c1-157">The unencrypted message.</span></span>

## <span data-ttu-id="ce8c1-158">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ce8c1-158">NOTES</span></span>

## <span data-ttu-id="ce8c1-159">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ce8c1-159">RELATED LINKS</span></span>

[<span data-ttu-id="ce8c1-160">about_Providers</span><span class="sxs-lookup"><span data-stu-id="ce8c1-160">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="ce8c1-161">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="ce8c1-161">Get-CmsMessage</span></span>](Get-CmsMessage.md)

[<span data-ttu-id="ce8c1-162">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="ce8c1-162">Protect-CmsMessage</span></span>](Protect-CmsMessage.md)
