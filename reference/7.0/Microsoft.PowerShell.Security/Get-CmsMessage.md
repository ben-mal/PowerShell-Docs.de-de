---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-cmsmessage?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CmsMessage
ms.openlocfilehash: b90059cd735e26eceb66d211533abbe25894d0ec
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209807"
---
# <span data-ttu-id="4cff1-103">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="4cff1-103">Get-CmsMessage</span></span>

## <span data-ttu-id="4cff1-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4cff1-104">SYNOPSIS</span></span>
<span data-ttu-id="4cff1-105">Ruft Inhalt ab, der mit dem Format der kryptografischen Nachrichten Syntax verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="4cff1-105">Gets content that has been encrypted by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="4cff1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4cff1-106">SYNTAX</span></span>

### <span data-ttu-id="4cff1-107">Bycontent</span><span class="sxs-lookup"><span data-stu-id="4cff1-107">ByContent</span></span>

```
Get-CmsMessage [-Content] <String> [<CommonParameters>]
```

### <span data-ttu-id="4cff1-108">Bypath</span><span class="sxs-lookup"><span data-stu-id="4cff1-108">ByPath</span></span>

```
Get-CmsMessage [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="4cff1-109">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="4cff1-109">ByLiteralPath</span></span>

```
Get-CmsMessage [-LiteralPath] <String> [<CommonParameters>]
```

## <span data-ttu-id="4cff1-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4cff1-110">DESCRIPTION</span></span>

<span data-ttu-id="4cff1-111">Mit dem- `Get-CmsMessage` Cmdlet werden Inhalte abgerufen, die mit dem CMS-Format (Cryptographic Message Syntax) verschlüsselt wurden.</span><span class="sxs-lookup"><span data-stu-id="4cff1-111">The `Get-CmsMessage` cmdlet gets content that has been encrypted using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="4cff1-112">Die CMS-Cmdlets unterstützen die Verschlüsselung und Entschlüsselung von Inhalten mithilfe des IETF-Formats für kryptografisch geschützte Nachrichten, wie von [RFC5652](https://tools.ietf.org/html/rfc5652)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="4cff1-112">The CMS cmdlets support encryption and decryption of content using the IETF format for cryptographically protecting messages, as documented by [RFC5652](https://tools.ietf.org/html/rfc5652).</span></span>

<span data-ttu-id="4cff1-113">Der CMS-Verschlüsselungsstandard verwendet die Kryptografie mit öffentlichem Schlüssel, bei der die Schlüssel zum Verschlüsseln von Inhalten (der öffentliche Schlüssel) und die Schlüssel, die zum Entschlüsseln von Inhalten (der private Schlüssel) verwendet werden, separat sind.</span><span class="sxs-lookup"><span data-stu-id="4cff1-113">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="4cff1-114">Ihr öffentlicher Schlüssel kann umfassend freigegeben werden, da seine Daten nicht vertraulich sind.</span><span class="sxs-lookup"><span data-stu-id="4cff1-114">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="4cff1-115">Wenn Inhalte mit diesem öffentlichen Schlüssel verschlüsselt sind, können sie nur mit Ihrem privaten Schlüssel entschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="4cff1-115">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="4cff1-116">Weitere Informationen finden Sie unter [Public-Key-Verschlüsselungsverfahren](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="4cff1-116">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="4cff1-117">`Get-CmsMessage` Ruft Inhalt ab, der im CMS-Format verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="4cff1-117">`Get-CmsMessage` gets content that has been encrypted in CMS format.</span></span> <span data-ttu-id="4cff1-118">Der Inhalt wird nicht entschlüsselt oder nicht geschützt.</span><span class="sxs-lookup"><span data-stu-id="4cff1-118">It does not decrypt or unprotect content.</span></span> <span data-ttu-id="4cff1-119">Sie können dieses Cmdlet ausführen, um Inhalte zu erhalten, die Sie durch Ausführen des `Protect-CmsMessage` Cmdlets verschlüsselt haben.</span><span class="sxs-lookup"><span data-stu-id="4cff1-119">You can run this cmdlet to get content that you have encrypted by running the `Protect-CmsMessage` cmdlet.</span></span> <span data-ttu-id="4cff1-120">Sie können den Inhalt angeben, der als Zeichenfolge oder als Pfad zum verschlüsselten Inhalt entschlüsselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4cff1-120">You can specify content that you want to decrypt as a string, or by path to the encrypted content.</span></span> <span data-ttu-id="4cff1-121">Sie können die Ergebnisse von an übergeben, `Get-CmsMessage` `Unprotect-CmsMessage` um den Inhalt zu entschlüsseln, vorausgesetzt, Sie verfügen über Informationen über das Dokument Verschlüsselungs Zertifikat, das zum Verschlüsseln des Inhalts verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4cff1-121">You can pipe the results of `Get-CmsMessage` to `Unprotect-CmsMessage` to decrypt the content, provided that you have information about the document encryption certificate that was used to encrypt the content.</span></span>

> [!NOTE]
> <span data-ttu-id="4cff1-122">Dieses Cmdlet ist nur unter Windows verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4cff1-122">This cmdlet is only available on Windows.</span></span>

## <span data-ttu-id="4cff1-123">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4cff1-123">EXAMPLES</span></span>

### <span data-ttu-id="4cff1-124">Beispiel 1: erhalten von verschlüsseltem Inhalt</span><span class="sxs-lookup"><span data-stu-id="4cff1-124">Example 1: Get encrypted content</span></span>

```powershell
$Msg = Get-CmsMessage -Path "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
$Msg.Content
```

```Output
-----BEGIN CMS-----
MIIBqAYJKoZIhvcNAQcDoIIBmTCCAZUCAQAxggFQMIIBTAIBADA0MCAxHjAcBgNVBAMBFWxlZWhv
bG1AbGljcm9zb2Z0LmNvbQIQQYHsbcXnjIJCtH+OhGmc1DANBgkqhkiG9w0BAQcwAASCAQAnkFHM
proJnFy4geFGfyNmxH3yeoPvwEYzdnsoVqqDPAd8D3wao77z7OhJEXwz9GeFLnxD6djKV/tF4PxR
E27aduKSLbnxfpf/sepZ4fUkuGibnwWFrxGE3B1G26MCenHWjYQiqv+Nq32Gc97qEAERrhLv6S4R
G+2dJEnesW8A+z9QPo+DwYP5FzD0Td0ExrkswVckpLNR6j17Yaags3ltNXmbdEXekhi6Psf2MLMP
TSO79lv2L0KeXFGuPOrdzPRwCkV0vNEqTEBeDnZGrjv/5766bM3GW34FXApod9u+VSFpBnqVOCBA
DVDraA6k+xwBt66cV84AHLkh0kT02SIHMDwGCSqGSIb3DQEHATAdBglghkgBZQMEASoEEJbJaiRl
KMnBoD1dkb/FzSWAEBaL8xkFwCu0e1AtDj7nSJc=
-----END CMS-----
```

<span data-ttu-id="4cff1-125">Mit diesem Befehl werden verschlüsselte Inhalte abgerufen, die sich unter C:\Users\Test\Documents\PowerShell\Future_Plans.txt befinden.</span><span class="sxs-lookup"><span data-stu-id="4cff1-125">This command gets encrypted content located at C:\Users\Test\Documents\PowerShell\Future_Plans.txt.</span></span>

### <span data-ttu-id="4cff1-126">Beispiel 2: übergeben von verschlüsselten Inhalten an Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="4cff1-126">Example 2: Pipe encrypted content to Unprotect-CmsMessage</span></span>

```powershell
$Msg = Get-CmsMessage -Path "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
$Msg | Unprotect-CmsMessage -To "cn=youralias@emailaddress.com"
```

```Output
Try the new Break All command
```

<span data-ttu-id="4cff1-127">Mit diesem Befehl werden die Ergebnisse des `Get-CmsMessage` Cmdlets aus Beispiel 1 an weitergeleitet `Unprotect-CmsMessage` , um die Nachricht zu entschlüsseln und in nur-Text-Text zu lesen.</span><span class="sxs-lookup"><span data-stu-id="4cff1-127">This command pipes the results of the `Get-CmsMessage` cmdlet from Example 1 to `Unprotect-CmsMessage`, to decrypt the message and read it in plain text.</span></span> <span data-ttu-id="4cff1-128">In diesem Fall ist der Wert des **to** -Parameters der Wert der Betreffzeile des verschlüsselnden Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="4cff1-128">In this case, the value of the **To** parameter is the value of the encrypting certificate's Subject line.</span></span> <span data-ttu-id="4cff1-129">Die entschlüsselte Meldung "try the New Break all Command" ist das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="4cff1-129">The decrypted message, "Try the new Break All command," is the result.</span></span>

## <span data-ttu-id="4cff1-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4cff1-130">PARAMETERS</span></span>

### <span data-ttu-id="4cff1-131">-Inhalt</span><span class="sxs-lookup"><span data-stu-id="4cff1-131">-Content</span></span>

<span data-ttu-id="4cff1-132">Gibt eine verschlüsselte Zeichenfolge oder eine Variable an, die eine verschlüsselte Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="4cff1-132">Specifies an encrypted string, or a variable containing an encrypted string.</span></span>

```yaml
Type: System.String
Parameter Sets: ByContent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4cff1-133">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="4cff1-133">-LiteralPath</span></span>

<span data-ttu-id="4cff1-134">Gibt den Pfad zu dem verschlüsselten Inhalt an, den Sie erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="4cff1-134">Specifies the path to encrypted content that you want to get.</span></span> <span data-ttu-id="4cff1-135">Im Gegensatz zu **Path** wird der Wert von **LiteralPath** genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="4cff1-135">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="4cff1-136">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="4cff1-136">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="4cff1-137">Wenn der Pfad Escapezeichen enthält, schließen Sie jeden in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="4cff1-137">If the path includes escape characters, enclose each one in single quotation marks.</span></span>
<span data-ttu-id="4cff1-138">Einfache Anführungszeichen weisen PowerShell an, eingeschlossene Zeichen nicht als Escapezeichen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="4cff1-138">Single quotation marks tell PowerShell not to interpret enclosed characters as escape characters.</span></span>

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

### <span data-ttu-id="4cff1-139">-Path</span><span class="sxs-lookup"><span data-stu-id="4cff1-139">-Path</span></span>

<span data-ttu-id="4cff1-140">Gibt den Pfad zu verschlüsseltem Inhalt an, der entschlüsselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4cff1-140">Specifies the path to encrypted content that you want to decrypt.</span></span>

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

### <span data-ttu-id="4cff1-141">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4cff1-141">CommonParameters</span></span>

<span data-ttu-id="4cff1-142">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4cff1-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4cff1-143">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4cff1-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4cff1-144">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4cff1-144">INPUTS</span></span>

## <span data-ttu-id="4cff1-145">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4cff1-145">OUTPUTS</span></span>

## <span data-ttu-id="4cff1-146">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4cff1-146">NOTES</span></span>

## <span data-ttu-id="4cff1-147">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4cff1-147">RELATED LINKS</span></span>

[<span data-ttu-id="4cff1-148">about_Providers</span><span class="sxs-lookup"><span data-stu-id="4cff1-148">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="4cff1-149">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="4cff1-149">Protect-CmsMessage</span></span>](Protect-CmsMessage.md)

[<span data-ttu-id="4cff1-150">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="4cff1-150">Unprotect-CmsMessage</span></span>](Unprotect-CmsMessage.md)
