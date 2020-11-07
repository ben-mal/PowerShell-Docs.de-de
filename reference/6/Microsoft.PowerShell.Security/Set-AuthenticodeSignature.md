---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-authenticodesignature?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AuthenticodeSignature
ms.openlocfilehash: 8c78366eacec964ced28aaed8ef17534df4abff4
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344812"
---
# Set-AuthenticodeSignature

## ZUSAMMENFASSUNG
Fügt einem PowerShell-Skript oder einer anderen Datei eine [Authenticode](/windows-hardware/drivers/install/authenticode) -Signatur hinzu.

## SYNTAX

### Bypath (Standard)

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] [-FilePath] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Byliteralpath

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -LiteralPath <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Bycontent

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -SourcePathOrExtension <String[]>
 -Content <Byte[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Set-AuthenticodeSignature` Cmdlet wird einer beliebigen Datei eine Authenticode-Signatur hinzugefügt, die das Subject Interface Package (SIP) unterstützt.

In einer PowerShell-Skriptdatei hat die Signatur die Form eines Textblocks, der das Ende der Anweisungen angibt, die im Skript ausgeführt werden. Wenn beim Ausführen dieses Cmdlets eine Signatur in der Datei vorhanden ist, wird die Signatur entfernt.

## BEISPIELE

### Beispiel 1: Signieren eines Skripts mit einem Zertifikat aus dem lokalen Zertifikat Speicher

Diese Befehle rufen ein Code Signaturzertifikat vom PowerShell-Zertifikat Anbieter ab und verwenden es zum Signieren eines PowerShell-Skripts.

```powershell
$cert=Get-ChildItem -Path Cert:\CurrentUser\My -CodeSigningCert
Set-AuthenticodeSignature -FilePath PsTestInternet2.ps1 -Certificate $cert
```

Der erste Befehl verwendet das `Get-ChildItem` Cmdlet und den PowerShell-Zertifikat Anbieter, um die Zertifikate im `Cert:\CurrentUser\My` Unterverzeichnis des Zertifikat Speicher zu erhalten. Das `Cert:` Laufwerk ist das Laufwerk, das vom Zertifikat Anbieter verfügbar gemacht wird. Der **codeSigningCert** -Parameter, der nur vom Zertifikat Anbieter unterstützt wird, schränkt die Zertifikate ein, die für diese Zertifikate mit Code Signatur Autorität abgerufen werden. Der Befehl speichert das Ergebnis in der `$cert` Variablen.

Der zweite Befehl verwendet das `Set-AuthenticodeSignature` Cmdlet, um das Skript zu signieren `PSTestInternet2.ps1` . Er verwendet den **FilePath** -Parameter, um den Namen des Skripts anzugeben, und den **Certificate** -Parameter, um anzugeben, dass das Zertifikat in der Variablen gespeichert wird `$cert` .

> [!NOTE]
> Wenn Sie den **codeSigningCert** -Parameter mit verwenden `Get-ChildItem` , werden nur Zertifikate zurückgegeben, die über eine Code Signatur Autorität verfügen und einen privaten Schlüssel enthalten. Wenn kein privater Schlüssel vorhanden ist, können die Zertifikate nicht zum Signieren verwendet werden.

### Beispiel 2: Signieren eines Skripts mit einem Zertifikat aus einer PFX-Datei

Diese Befehle verwenden das `Get-PfxCertificate` Cmdlet, um ein Code Signaturzertifikat zu laden. Verwenden Sie ihn anschließend zum Signieren eines PowerShell-Skripts.

```powershell
$cert = Get-PfxCertificate -FilePath C:\Test\Mysign.pfx
Set-AuthenticodeSignature -FilePath ServerProps.ps1 -Certificate $cert
```

Der erste Befehl verwendet das `Get-PfxCertificate` Cmdlet, um das c:\test\mysign.pfx-Zertifikat in die-Variable zu laden `$cert` .

Der zweite Befehl verwendet `Set-AuthenticodeSignature` , um das Skript zu signieren. Der **FilePath** -Parameter von `Set-AuthenticodeSignature` gibt den Pfad der Skriptdatei an, die signiert wird, und der **CERT** -Parameter übergibt die `$cert` Variable, die das Zertifikat enthält, an `Set-AuthenticodeSignature` .

Wenn die Zertifikat Datei Kenn Wort geschützt ist, werden Sie von PowerShell zur Eingabe des Kennworts aufgefordert.

### Beispiel 3: Hinzufügen einer Signatur, die die Stamm Zertifizierungsstelle enthält

Dieser Befehl fügt eine digitale Signatur hinzu, die die Stammzertifizierungsstelle in der Vertrauenskette enthält, und wird von einem Zeitstempelserver eines Drittanbieters signiert.

```powershell
Set-AuthenticodeSignature -FilePath c:\scripts\Remodel.ps1 -Certificate $cert -IncludeChain All -TimestampServer "http://timestamp.fabrikam.com/scripts/timstamper.dll"
```

Der Befehl verwendet den **FilePath** -Parameter, um das signierte Skript anzugeben, und den **Certificate** -Parameter, um das Zertifikat anzugeben, das in der Variablen gespeichert wird `$cert` . Er verwendet den **incluentchain** -Parameter, um alle Signaturen in der Vertrauenskette einzuschließen, einschließlich der Stamm Zertifizierungsstelle. Außerdem verwendet er den **Timestampserver** -Parameter, um der Signatur einen Zeitstempel hinzuzufügen.
Dadurch wird verhindert, dass das Skript bei Ablauf des Zertifikats einen Fehler verursacht.

## PARAMETERS

### -Zertifikat

Gibt das Zertifikat an, das verwendet wird, um das Skript oder die Datei zu signieren. Geben Sie eine Variable ein, die ein Objekt speichert, das das Zertifikat oder einen Ausdruck darstellt, der das Zertifikat abruft.

Verwenden Sie `Get-PfxCertificate` das `Get-ChildItem` Cmdlet im Zertifikat Laufwerk, oder verwenden Sie es, um ein Zertifikat zu suchen `Cert:` . Wenn das Zertifikat ungültig ist oder keine `code-signing` Autorität hat, schlägt der Befehl fehl.

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

### -FilePath

Gibt den Pfad zu einer Datei an, die signiert wird.

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

### -Force

Ermöglicht es dem Cmdlet, eine Signatur an eine schreibgeschützte Datei anzufügen. Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.

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

### -HashAlgorithm

Gibt den Hashalgorithmus an, den Windows verwendet, um die digitale Signatur für die Datei zu berechnen.

Für PowerShell 3,0 ist der Standardwert SHA256. Dies ist der Windows-Standard Hash Algorithmus. Für PowerShell 2,0 lautet der Standardwert SHA1. Dateien, die mit einem anderen Hashalgorithmus signiert sind, werden auf anderen Systemen möglicherweise nicht erkannt. Welche Algorithmen unterstützt werden, hängt von der Version des Betriebssystems ab.

Eine Liste möglicher Werte finden Sie unter [hashalgorithmname-Struktur](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties).

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

### -Incluentchain

Bestimmt, welche Zertifikate in der Zertifikatvertrauenskette in der digitalen Signatur enthalten sind.
**Notroot** ist die Standardeinstellung.

Gültige Werte sind:

- Signatur Geber: schließt nur das Zertifikat des Signatur Gebers ein.
- Notroot: schließt alle Zertifikate in der Zertifikatskette mit Ausnahme der Stamm Zertifizierungsstelle ein.
- All: schließt alle Zertifikate in der Zertifikat Kette ein.

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

### -Timestampserver

Verwendet den angegebenen Zeitstempelserver, um der Signatur einen Zeitstempel hinzuzufügen. Geben Sie die URL des Zeitstempelservers als Zeichenfolge ein.

Der Zeitstempel gibt die genaue Zeit an, zu der das Zertifikat der Datei hinzugefügt wurde. Ein Zeitstempel verhindert, dass das Skript fehlschlägt, wenn das Zertifikat abläuft, da Benutzer und Programme sicherstellen können, dass das Zertifikat beim Signieren gültig war.

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

### -Literalpath

Gibt den Pfad zu einer Datei an, die signiert wird. Im Gegensatz zu **FilePath** wird der Wert des **LiteralPath** -Parameters genau wie eingegeben verwendet. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

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

### -Sourceplthorextension

Der Pfad zur Datei oder zum Dateityp des Inhalts, dem die digitale Signatur hinzugefügt wird. Dieser Parameter wird mit **Inhalten** verwendet, bei denen der Dateiinhalt als Bytearray übergeben wird.

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

### -Inhalt

Der Inhalt einer Datei als Bytearray, für das die digitale Signatur hinzugefügt wird. Dieser Parameter muss mit dem **sourcepthorextension** -Parameter verwendet werden. Der Inhalt der Datei muss im Unicode-Format (UTF-16LE) vorliegen.

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

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

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

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine Zeichenfolge, die den Dateipfad enthält, an die Pipeline übergeben `Set-AuthenticodeSignature` .

## AUSGABEN

### System. Management. Automation. Signature

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

## VERWANDTE LINKS

[Get-AuthenticodeSignature](Get-AuthenticodeSignature.md)

[Get-ExecutionPolicy](Get-ExecutionPolicy.md)

[Get-PfxCertificate](Get-PfxCertificate.md)

[Set-ExecutionPolicy](Set-ExecutionPolicy.md)

[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md)
