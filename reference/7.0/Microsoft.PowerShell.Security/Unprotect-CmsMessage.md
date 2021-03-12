---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/unprotect-cmsmessage?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unprotect-CmsMessage
ms.openlocfilehash: 4c66b1785da53b3bf351e4377fef0e99076e3fcf
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194651"
---
# Unprotect-CmsMessage

## ZUSAMMENFASSUNG
Entschlüsselt Inhalt, der mithilfe des kryptografischen Nachrichten Syntax Formats verschlüsselt wurde.

## SYNTAX

### Bywinevent (Standard)

```
Unprotect-CmsMessage [-EventLogRecord] <PSObject> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

### Bycontent

```
Unprotect-CmsMessage [-Content] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### Bypath

```
Unprotect-CmsMessage [-Path] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### Byliteralpath

```
Unprotect-CmsMessage [-LiteralPath] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Unprotect-CmsMessage` Cmdlet werden Inhalte entschlüsselt, die mit dem CMS-Format (Cryptographic Message Syntax) verschlüsselt wurden.

Die CMS-Cmdlets unterstützen die Verschlüsselung und Entschlüsselung von Inhalten mithilfe des IETF-Standard Formats für kryptografisch geschützte Nachrichten, wie von [RFC5652](https://tools.ietf.org/html/rfc5652)dokumentiert.

Der CMS-Verschlüsselungsstandard verwendet die Kryptografie mit öffentlichem Schlüssel, bei der die Schlüssel zum Verschlüsseln von Inhalten (der öffentliche Schlüssel) und die Schlüssel, die zum Entschlüsseln von Inhalten (der private Schlüssel) verwendet werden, separat sind. Ihr öffentlicher Schlüssel kann umfassend freigegeben werden, da seine Daten nicht vertraulich sind. Wenn Inhalte mit diesem öffentlichen Schlüssel verschlüsselt sind, können sie nur mit Ihrem privaten Schlüssel entschlüsselt werden. Weitere Informationen finden Sie unter [Public-Key-Verschlüsselungsverfahren](https://en.wikipedia.org/wiki/Public-key_cryptography).

`Unprotect-CmsMessage` entschlüsselt Inhalte, die im CMS-Format verschlüsselt wurden. Sie können dieses Cmdlet ausführen, um Inhalte zu entschlüsseln, die Sie durch Ausführen des `Protect-CmsMessage` Cmdlets verschlüsselt haben. Sie können den Inhalt, der als Zeichenfolge entschlüsselt werden soll, durch die ID-Nummer des Verschlüsselungs Ereignisprotokoll-Datensatzes oder durch den Pfad zum verschlüsselten Inhalt angeben. Mit dem- `Unprotect-CmsMessage` Cmdlet wird der entschlüsselte Inhalt zurückgegeben.

> [!NOTE]
> Dieses Cmdlet ist nur unter Windows verfügbar.

## BEISPIELE

### Beispiel 1: Entschlüsseln einer Nachricht

Im folgenden Beispiel entschlüsseln Sie die Inhalte, die sich im literalpfad befinden `C:\Users\Test\Documents\PowerShell` . Für den Wert **des Parameters erforderlich für wird** in diesem Beispiel der Fingerabdruck des Zertifikats verwendet, das zum Durchführen der Verschlüsselung verwendet wurde. Die entschlüsselte Meldung "try the New Break all Command" ist das Ergebnis.

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
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -EventLogRecord

Gibt eine Ereignisprotokoll-Daten Satz-ID an, die einen CMS-Verschlüsselungs Vorgang darstellt.

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

### -Includecontext

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

### -Literalpath

Gibt den Pfad zu verschlüsseltem Inhalt an, der entschlüsselt werden soll. Im Gegensatz zu **Path** wird der Wert von **LiteralPath** genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

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

### -Path

Gibt den Pfad zu verschlüsseltem Inhalt an, der entschlüsselt werden soll.

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

### Bis

Gibt einen oder mehrere CMS-Nachrichtenempfänger an, die in einem der folgenden Formate identifiziert werden:

- Ein tatsächliches Zertifikat (wie vom Zertifikat Anbieter abgerufen).
- Pfad zu einer Datei, die das Zertifikat enthält.
- Pfad zu einem Verzeichnis, das das Zertifikat enthält.
- Der Fingerabdruck des Zertifikats (dient zum Suchen im Zertifikat Speicher).
- Der Antragsteller Name des Zertifikats (das zum Suchen im Zertifikat Speicher verwendet wird).

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Diagnostics. Eventing. Reader. EventLogRecord oder System. String

Sie können ein Objekt, das verschlüsselten Inhalt enthält, an die Pipeline übergeben `Unprotect-CmsMessage` .

## AUSGABEN

### System.String

Die unverschlüsselte Nachricht.

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

## VERWANDTE LINKS

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Get-CmsMessage](Get-CmsMessage.md)

[Protect-CmsMessage](Protect-CmsMessage.md)
