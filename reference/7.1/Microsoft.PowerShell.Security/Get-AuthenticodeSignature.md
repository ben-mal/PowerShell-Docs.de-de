---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-authenticodesignature?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AuthenticodeSignature
ms.openlocfilehash: b1b470fb1dd23cd404b7f5fea4981b39f206ae87
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685337"
---
# Get-AuthenticodeSignature

## ZUSAMMENFASSUNG
Ruft Informationen über die Authenticode-Signatur für eine Datei ab.

## SYNTAX

### Bypath (Standard)

```
Get-AuthenticodeSignature [-FilePath] <String[]> [<CommonParameters>]
```

### Byliteralpath

```
Get-AuthenticodeSignature -LiteralPath <String[]> [<CommonParameters>]
```

### Bycontent

```
Get-AuthenticodeSignature -SourcePathOrExtension <String[]> -Content <Byte[]> [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-AuthenticodeSignature` Cmdlet ruft Informationen über die Authenticode-Signatur für einen Datei-oder Dateiinhalt als Bytearray ab.
Wenn die Datei sowohl als eingebettete als auch als Windows-Katalog signierte Datei verwendet wird, wird die Windows-Katalog Signatur verwendet.
Wenn die Datei nicht signiert ist, werden die Informationen abgerufen, aber die Felder sind leer.

## BEISPIELE

### Beispiel 1: erhalten der Authenticode-Signatur für eine Datei

```powershell
Get-AuthenticodeSignature -FilePath "C:\Test\NewScript.ps1"
```

Dieser Befehl ruft Informationen über die Authenticode-Signatur in der Datei NewScript.ps1 ab. Er verwendet den **FilePath** -Parameter, um die Datei anzugeben.

### Beispiel 2: erhalten der Authenticode-Signatur für mehrere Dateien

```powershell
Get-AuthenticodeSignature test.ps1, test1.ps1, sign-file.ps1, makexml.ps1
```

Dieser Befehl ruft Informationen über die Authenticode-Signatur für die vier Dateien ab, die in der Befehlszeile aufgelistet sind. In diesem Beispiel wird der Name des **FilePath** -Parameters, der optional ist, weggelassen.

### Beispiel 3: nur gültige Authenticode-Signaturen für mehrere Dateien erhalten

```powershell
Get-ChildItem $PSHOME\*.* | ForEach-object {Get-AuthenticodeSignature $_} | Where-Object {$_.status -eq "Valid"}
```

Mit diesem Befehl werden alle Dateien im Verzeichnis aufgelistet `$PSHOME` , die über eine gültige Authenticode-Signatur verfügen. Die `$PSHOME` Automatische Variable enthält den Pfad zum PowerShell-Installationsverzeichnis.

Der Befehl verwendet das `Get-ChildItem` Cmdlet, um die Dateien im Verzeichnis zu erhalten `$PSHOME` . Dabei wird ein Muster von verwendet *.* zum Ausschließen von Verzeichnissen (obwohl auch Dateien ohne einen Punkt im Dateinamen ausgeschlossen werden).

Der Befehl verwendet einen Pipeline Operator ( `|` ), um die Dateien an `$PSHOME` das `ForEach-Object` Cmdlet zu senden, wobei `Get-AuthenticodeSignature` für jede Datei aufgerufen wird.

Die Ergebnisse des `Get-AuthenticodeSignature` Befehls werden an einen Befehl gesendet `Where-Object` , der nur die Signatur Objekte mit dem Status "valid" auswählt.

### Beispiel 4: erhalten der Authenticode-Signatur für einen Dateiinhalt, der als Bytearray angegeben ist

```powershell
Get-AuthenticodeSignature -Content (Get-Content foo.ps1 -AsByteStream) -SourcePathorExtension ps1
```

Dieser Befehl ruft Informationen über die Authenticode-Signatur für den Inhalt einer Datei ab. In diesem Beispiel wird die Dateierweiterung zusammen mit dem Inhalt der Datei angegeben.

## PARAMETERS

### -Inhalt

Der Inhalt einer Datei als Bytearray, für das die Authenticode-Signatur abgerufen wird. Dieser Parameter muss mit dem **sourcepthorextension** -Parameter verwendet werden. Der Inhalt der Datei muss im Unicode-Format (UTF-16LE) vorliegen.

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

### -FilePath

Gibt den Pfad zu der Datei an, die untersucht werden soll. Platzhalter sind zulässig, aber sie müssen auf eine einzige Datei verweisen. Es ist nicht erforderlich, **FilePath** in der Befehlszeile einzugeben, wenn Sie einen Wert für diesen Parameter angeben.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Literalpath

Gibt den Pfad zur Datei an, die überprüft wird. Im Gegensatz zu **FilePath** wird der Wert des **LiteralPath**-Parameters genau wie eingegeben verwendet. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad ein Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapezeichen zu interpretieren.

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

Der Pfad zur Datei oder zum Dateityp des Inhalts, für den die Authenticode-Signatur abgerufen wird. Dieser Parameter wird mit **Inhalten** verwendet, bei denen der Dateiinhalt als Bytearray übergeben wird.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String

Sie können eine Zeichenfolge mit einem Dateipfad an die Pipeline übergeben `Get-AuthenticodeSignature` .

## AUSGABEN

### System. Management. Automation. Signature

`Get-AuthenticodeSignature` Gibt ein Signatur Objekt für jede Signatur zurück, die es abruft.

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

Informationen zu Authenticode-Signaturen in PowerShell finden Sie unter [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).

## VERWANDTE LINKS

[Get-ExecutionPolicy](Get-ExecutionPolicy.md)

[Set-AuthenticodeSignature](Set-AuthenticodeSignature.md)

[Set-ExecutionPolicy](Set-ExecutionPolicy.md)

[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md)
