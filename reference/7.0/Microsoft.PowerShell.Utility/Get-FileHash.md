---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-filehash?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FileHash
ms.openlocfilehash: 6b6b0bdfe635ba0d11c4694efa8af6c23d9acdcd
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210796"
---
# Get-FileHash

## ZUSAMMENFASSUNG
Berechnet den Hashwert für eine Datei mit einem angegebenen Hashalgorithmus.

## SYNTAX

### Pfad (Standard)

```
Get-FileHash [-Path] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### LiteralPath

```
Get-FileHash [-LiteralPath] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### Streamparameterset

```
Get-FileHash [-InputStream] <Stream> [[-Algorithm] <String>] [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-FileHash` Cmdlet berechnet den Hashwert für eine Datei mithilfe eines angegebenen Hash Algorithmus.
Ein Hashwert ist ein eindeutiger Wert, der dem Inhalt der Datei entspricht. Anstatt den Inhalt einer Datei anhand des Dateinamens, der Erweiterung oder einer anderen Bezeichnung zu identifizieren, weist ein Hash dem Inhalt einer Datei einen eindeutigen Wert zu. Dateinamen und Erweiterungen können geändert werden, ohne den Inhalt der Datei und ohne den Hashwert zu ändern. Ebenso kann der Inhalt der Datei geändert werden, ohne den Namen oder die Erweiterung zu ändern. Durch die bloße Änderung eines einzelnen Zeichens im Inhalt einer Datei ändert sich jedoch auch deren Hashwert.

Hashwerte bieten eine im Hinblick auf die Kryptografie sichere Möglichkeit, zu gewährleisten, dass der Inhalt einer Datei nicht geändert wurde. Obwohl einige Hash Algorithmen, einschließlich MD5 und SHA1, nicht mehr als sicher gegen Angriffe angesehen werden, besteht das Ziel eines sicheren Hash Algorithmus darin, den Inhalt einer Datei nicht zu ändern, entweder versehentlich oder durch böswillige oder nicht autorisierte Versuche, und denselben Hashwert beizubehalten. Mithilfe von Hashwerten können Sie auch bestimmen, ob zwei unterschiedliche Dateien genau den gleichen Inhalt aufweisen. Wenn die Hashwerte von zwei Dateien identisch sind, sind die Inhalte der Dateien ebenfalls identisch.

Standardmäßig verwendet das `Get-FileHash` Cmdlet den SHA256-Algorithmus, obwohl alle vom Ziel Betriebssystem unterstützten Hash Algorithmen verwendet werden können.

## BEISPIELE

### Beispiel 1: Berechnen des Hashwerts für eine Datei

In diesem Beispiel wird das- `Get-FileHash` Cmdlet verwendet, um den Hashwert für die Datei zu berechnen `/etc/apt/sources.list` . Der verwendete Hash Algorithmus ist die Standardeinstellung, **SHA256** . Die Ausgabe wird an das `Format-List` Cmdlet weitergeleitet, um die Ausgabe als Liste zu formatieren.

```powershell
Get-FileHash /etc/apt/sources.list | Format-List
```

```Output
Algorithm : SHA256
Hash      : 3CBCFDDEC145E3382D592266BE193E5BE53443138EE6AB6CA09FF20DF609E268
Path      : /etc/apt/sources.list
```

### Beispiel 2: Berechnen des Hashwerts für eine ISO-Datei

In diesem Beispiel wird das `Get-FileHash` -Cmdlet und der **SHA384** -Algorithmus zum Berechnen des Hashwerts für eine ISO-Datei verwendet, die ein Administrator aus dem Internet heruntergeladen hat. Die Ausgabe wird an das `Format-List` Cmdlet weitergeleitet, um die Ausgabe als Liste zu formatieren.

```powershell
Get-FileHash C:\Users\user1\Downloads\Contoso8_1_ENT.iso -Algorithm SHA384 | Format-List
```

```Output
Algorithm : SHA384
Hash      : 20AB1C2EE19FC96A7C66E33917D191A24E3CE9DAC99DB7C786ACCE31E559144FEAFC695C58E508E2EBBC9D3C96F21FA3
Path      : C:\Users\user1\Downloads\Contoso8_1_ENT.iso
```

### Beispiel 3: Berechnen des Hashwerts eines Streams

In diesem Beispiel verwenden wir **System .net. WebClient** , um ein Paket von der [PowerShell-releaseseite](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4)herunterzuladen. Auf der releaseseite wird auch der SHA256-Hash der einzelnen Paketdateien dokumentiert. Wir können den veröffentlichten Hashwert mit dem Wert vergleichen, den wir mit berechnen `Get-FileHash` .

```powershell
$wc = [System.Net.WebClient]::new()
$pkgurl = 'https://github.com/PowerShell/PowerShell/releases/download/v6.2.4/powershell_6.2.4-1.debian.9_amd64.deb'
$publishedHash = '8E28E54D601F0751922DE24632C1E716B4684876255CF82304A9B19E89A9CCAC'
$FileHash = Get-FileHash -InputStream ($wc.OpenRead($pkgurl))
$FileHash.Hash -eq $publishedHash
```

```Output
True
```

### Beispiel 4: Berechnen des Hashwerts einer Zeichenfolge

PowerShell bietet kein Cmdlet, um den Hash einer Zeichenfolge zu berechnen. Sie können jedoch eine Zeichenfolge in einen Stream schreiben und den **InputStream** -Parameter von verwenden `Get-FileHash` , um den Hashwert zu erhalten.

```powershell
$stringAsStream = [System.IO.MemoryStream]::new()
$writer = [System.IO.StreamWriter]::new($stringAsStream)
$writer.write("Hello world")
$writer.Flush()
$stringAsStream.Position = 0
Get-FileHash -InputStream $stringAsStream | Select-Object Hash
```

```Output
Hash
----
64EC88CA00B268E5BA1A35678A1B5316D212F4F366B2477232534A8AECA37F3C
```

## PARAMETERS

### -Algorithmus

Gibt die kryptografische Hash Funktion an, die zum Berechnen des Hashwerts des Inhalts der angegebenen Datei bzw. des angegebenen Streams verwendet werden soll. Eine kryptografische Hash Funktion hat die-Eigenschaft, dass Sie nicht gefunden werden kann, um zwei verschiedene Dateien mit demselben Hashwert zu suchen. Hashfunktionen werden häufig bei digitalen Signaturen und für die Datenintegrität verwendet. Zulässige Werte für diesen Parameter:

- SHA1
- SHA256
- SHA384
- SHA512
- MD5

Wenn kein Wert angegeben oder der Parameter weggelassen wird, ist der Standardwert SHA256.

MD5 und SHA1, die nicht mehr als sicher eingestuft werden, sollten aus Sicherheitsgründen nur zur einfachen Überprüfung von Änderungen verwendet werden und nicht zum Generieren von Hashwerten für Dateien, die vor Angriffen oder Manipulation geschützt werden müssen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: SHA1, SHA256, SHA384, SHA512, MD5

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputStream

Gibt den Eingabestream an.

```yaml
Type: System.IO.Stream
Parameter Sets: StreamParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Literalpath

Gibt den Pfad zu einer Datei an. Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen weisen PowerShell an, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Gibt den Pfad zu einer oder mehreren Dateien als Array an. Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine Zeichenfolge über die Pipeline an das `Get-FileHash` Cmdlet übergeben, das einen Pfad zu einer oder mehreren Dateien enthält.

## AUSGABEN

### Microsoft. PowerShell. Utility. flehash

`Get-FileHash` Gibt ein Objekt zurück, das den Pfad zur angegebenen Datei, den Wert des berechneten Hashs und den zum Berechnen des Hashs verwendeten Algorithmus darstellt.

## HINWEISE

## VERWANDTE LINKS

[Format-List](Format-List.md)
