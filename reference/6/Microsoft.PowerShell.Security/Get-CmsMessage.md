---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-cmsmessage?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CmsMessage
ms.openlocfilehash: 30e70549b648f7fb63bb250744cf52f0979c201f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214988"
---
# Get-CmsMessage

## ZUSAMMENFASSUNG
Ruft Inhalt ab, der mit dem Format der kryptografischen Nachrichten Syntax verschlüsselt wurde.

## SYNTAX

### Bycontent

```
Get-CmsMessage [-Content] <String> [<CommonParameters>]
```

### Bypath

```
Get-CmsMessage [-Path] <String> [<CommonParameters>]
```

### Byliteralpath

```
Get-CmsMessage [-LiteralPath] <String> [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-CmsMessage` Cmdlet werden Inhalte abgerufen, die mit dem CMS-Format (Cryptographic Message Syntax) verschlüsselt wurden.

Die CMS-Cmdlets unterstützen die Verschlüsselung und Entschlüsselung von Inhalten mithilfe des IETF-Formats für kryptografisch geschützte Nachrichten, wie von [RFC5652](https://tools.ietf.org/html/rfc5652)dokumentiert.

Der CMS-Verschlüsselungsstandard verwendet die Kryptografie mit öffentlichem Schlüssel, bei der die Schlüssel zum Verschlüsseln von Inhalten (der öffentliche Schlüssel) und die Schlüssel, die zum Entschlüsseln von Inhalten (der private Schlüssel) verwendet werden, separat sind. Ihr öffentlicher Schlüssel kann umfassend freigegeben werden, da seine Daten nicht vertraulich sind. Wenn Inhalte mit diesem öffentlichen Schlüssel verschlüsselt sind, können sie nur mit Ihrem privaten Schlüssel entschlüsselt werden. Weitere Informationen finden Sie unter [Public-Key-Verschlüsselungsverfahren](https://en.wikipedia.org/wiki/Public-key_cryptography).

`Get-CmsMessage` Ruft Inhalt ab, der im CMS-Format verschlüsselt wurde. Der Inhalt wird nicht entschlüsselt oder nicht geschützt. Sie können dieses Cmdlet ausführen, um Inhalte zu erhalten, die Sie durch Ausführen des `Protect-CmsMessage` Cmdlets verschlüsselt haben. Sie können den Inhalt angeben, der als Zeichenfolge oder als Pfad zum verschlüsselten Inhalt entschlüsselt werden soll. Sie können die Ergebnisse von an übergeben, `Get-CmsMessage` `Unprotect-CmsMessage` um den Inhalt zu entschlüsseln, vorausgesetzt, Sie verfügen über Informationen über das Dokument Verschlüsselungs Zertifikat, das zum Verschlüsseln des Inhalts verwendet wurde.

> [!NOTE]
> Dieses Cmdlet ist nur unter Windows verfügbar.

## BEISPIELE

### Beispiel 1: erhalten von verschlüsseltem Inhalt

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

Mit diesem Befehl werden verschlüsselte Inhalte abgerufen, die sich unter C:\Users\Test\Documents\PowerShell\Future_Plans.txt befinden.

### Beispiel 2: übergeben von verschlüsselten Inhalten an Unprotect-CmsMessage

```powershell
$Msg = Get-CmsMessage -Path "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
$Msg | Unprotect-CmsMessage -To "cn=youralias@emailaddress.com"
```

```Output
Try the new Break All command
```

Mit diesem Befehl werden die Ergebnisse des `Get-CmsMessage` Cmdlets aus Beispiel 1 an weitergeleitet `Unprotect-CmsMessage` , um die Nachricht zu entschlüsseln und in nur-Text-Text zu lesen. In diesem Fall ist der Wert des **to** -Parameters der Wert der Betreffzeile des verschlüsselnden Zertifikats. Die entschlüsselte Meldung "try the New Break all Command" ist das Ergebnis.

## PARAMETERS

### -Inhalt

Gibt eine verschlüsselte Zeichenfolge oder eine Variable an, die eine verschlüsselte Zeichenfolge enthält.

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

### -Literalpath

Gibt den Pfad zu dem verschlüsselten Inhalt an, den Sie erhalten möchten. Im Gegensatz zu **Path** wird der Wert von **LiteralPath** genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, schließen Sie jeden in einfache Anführungszeichen ein.
Einfache Anführungszeichen weisen PowerShell an, eingeschlossene Zeichen nicht als Escapezeichen zu interpretieren.

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

### -Path

Gibt den Pfad zu verschlüsseltem Inhalt an, der entschlüsselt werden soll.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Protect-CmsMessage](Protect-CmsMessage.md)

[Unprotect-CmsMessage](Unprotect-CmsMessage.md)
