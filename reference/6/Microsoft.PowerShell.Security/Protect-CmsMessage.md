---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/protect-cmsmessage?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Protect-CmsMessage
ms.openlocfilehash: d148a9d1013de20885cd9914f283b85a2a7acd3f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216892"
---
# Protect-CmsMessage

## ZUSAMMENFASSUNG
Verschlüsselt Inhalt mithilfe des kryptografischen Nachrichten Syntax Formats.

## SYNTAX

### Bycontent (Standard)

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Content] <PSObject> [[-OutFile] <String>]
 [<CommonParameters>]
```

### Bypath

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Path] <String> [[-OutFile] <String>] [<CommonParameters>]
```

### Byliteralpath

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-LiteralPath] <String> [[-OutFile] <String>]
 [<CommonParameters>]
```

## DESCRIPTION

Das `Protect-CmsMessage` Cmdlet verschlüsselt Inhalte mithilfe des CMS-Formats (Cryptographic Message Syntax).

Die CMS-Cmdlets unterstützen die Verschlüsselung und Entschlüsselung von Inhalten mithilfe des IETF-Formats, wie von [RFC5652](https://tools.ietf.org/html/rfc5652.html)dokumentiert.

Der CMS-Verschlüsselungsstandard verwendet die Kryptografie mit öffentlichem Schlüssel, bei der die Schlüssel zum Verschlüsseln von Inhalten (der öffentliche Schlüssel) und die Schlüssel, die zum Entschlüsseln von Inhalten (der private Schlüssel) verwendet werden, separat sind. Ihr öffentlicher Schlüssel kann umfassend freigegeben werden, da seine Daten nicht vertraulich sind. Wenn Inhalte mit diesem öffentlichen Schlüssel verschlüsselt sind, können sie nur mit Ihrem privaten Schlüssel entschlüsselt werden. Weitere Informationen finden Sie unter [Public-Key-Verschlüsselungsverfahren](https://en.wikipedia.org/wiki/Public-key_cryptography).

Bevor Sie das `Protect-CmsMessage` Cmdlet ausführen können, müssen Sie ein Verschlüsselungs Zertifikat eingerichtet haben.
Um in PowerShell erkannt zu werden, benötigen Verschlüsselungs Zertifikate eine eindeutige[EKU](/windows/desktop/SecCrypto/eku)-ID (Extended Key Usage), um Sie als Daten Verschlüsselungs Zertifikate zu identifizieren (z. b. die IDs für Code Signierung und verschlüsselte e-Mail). Ein Beispiel für ein Zertifikat, das für die Dokument Verschlüsselung funktioniert, finden Sie in Beispiel 1 in diesem Thema.

> [!NOTE]
> Dieses Cmdlet ist nur unter Windows verfügbar.

## BEISPIELE

### Beispiel 1: Erstellen eines Zertifikats zum Verschlüsseln von Inhalten

Bevor Sie das `Protect-CmsMessage` Cmdlet ausführen können, müssen Sie ein Verschlüsselungs Zertifikat erstellen. Ändern Sie den Namen in der Betreffzeile unter Verwendung des folgenden Texts in ihren Namen, Ihre e-Mail-Adresse oder einen anderen Bezeichner, und speichern Sie das Zertifikat in einer Datei (z `DocumentEncryption.inf` . b., wie in diesem Beispiel gezeigt).

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

### Beispiel 2: Verschlüsseln einer per e-Mail gesendeten Nachricht

```powershell
$Protected = "Hello World" | Protect-CmsMessage -To "*youralias@emailaddress.com*"
```

Im folgenden Beispiel verschlüsseln Sie die Meldung "Hallo Welt", indem Sie Sie an das `Protect-CmsMessage` Cmdlet weiterleiten, und speichern dann die verschlüsselte Nachricht in einer Variablen. Der **to** -Parameter verwendet den Wert der Betreffzeile im Zertifikat.

### Beispiel 3: Anzeigen von Dokumenten Verschlüsselungs Zertifikaten

```
PS C:\> cd Cert:\CurrentUser\My
PS Cert:\CurrentUser\My> Get-ChildItem -DocumentEncryptionCert
```

Um Dokument Verschlüsselungs Zertifikate im Zertifikat Anbieter anzuzeigen, können Sie den dynamischen **documentverschlüsseltioncert** -Parameter von [Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md)hinzufügen, der nur verfügbar ist, wenn der Zertifikat Anbieter geladen wird.

## PARAMETERS

### -Inhalt

Gibt ein **psobject** an, das Inhalte enthält, die Sie verschlüsseln möchten. Beispielsweise können Sie den Inhalt einer Ereignis Nachricht verschlüsseln und dann die Variable mit der Meldung ( `$Event` in diesem Beispiel) als Wert für den **Content** -Parameter verwenden: `$event = Get-WinEvent -ProviderName "PowerShell" -MaxEvents 1` . Sie können auch das- `Get-Content` Cmdlet verwenden, um den Inhalt einer Datei, z. b. ein Microsoft Word-Dokument, zu erhalten und den Inhalt in einer Variablen zu speichern, die Sie als Wert des **Content** -Parameters verwenden.

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

### -Literalpath

Gibt den Pfad zu den zu verschlüsselnden Inhalten an. Im Gegensatz zu **Path** wird der Wert von **LiteralPath** genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

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

### -Outfile

Gibt den Pfad und den Dateinamen einer Datei an, an die der verschlüsselte Inhalt gesendet werden soll.

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

### -Path

Gibt den Pfad zu den zu verschlüsselnden Inhalten an.

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

### Bis

Gibt einen oder mehrere CMS-Nachrichtenempfänger an, die in einem der folgenden Formate identifiziert werden:

- Ein tatsächliches Zertifikat (wie vom Zertifikat Anbieter abgerufen).
- Der Pfad zu der Datei, die das Zertifikat enthält.
- Pfad zu einem Verzeichnis, das das Zertifikat enthält.
- Der Fingerabdruck des Zertifikats (dient zum Suchen im Zertifikat Speicher).
- Der Antragsteller Name des Zertifikats (das zum Suchen im Zertifikat Speicher verwendet wird).

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

### CommonParameters

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` . Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Get-CmsMessage](Get-CmsMessage.md)

[Unprotect-CmsMessage](Unprotect-CmsMessage.md)
