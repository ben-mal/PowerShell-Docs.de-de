---
title: about_Character_Encoding
description: Beschreibt, wie PowerShell die Zeichencodierung für die Eingabe und Ausgabe von Zeichen folgen Daten verwendet.
ms.date: 10/21/2020
Locale: en-US
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_character_encoding?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
ms.openlocfilehash: 6e2f515f774d7bc333baf6346cd6c8bd517cb6fa
ms.sourcegitcommit: df80c558e9a4b89c9798f084bd04012ece15155c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2020
ms.locfileid: "93225151"
---
# <a name="about_character_encoding"></a>about_Character_Encoding

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt, wie PowerShell die Zeichencodierung für die Eingabe und Ausgabe von Zeichen folgen Daten verwendet.

## <a name="long-description"></a>Lange Beschreibung

Unicode ist ein weltweiter Zeichen Codierungsstandard. Das System verwendet Unicode exklusiv für Zeichen-und Zeichen folgen Bearbeitung. Eine ausführliche Beschreibung aller Aspekte von Unicode finden Sie unter Unicode- [Standard](https://www.unicode.org/standard/standard.html).

Windows unterstützt Unicode-und herkömmliche Zeichensätze. Herkömmliche Zeichensätze, wie z. b. Windows-Codepages, verwenden 8-Bit-Werte oder Kombinationen von 8-Bit-Werten, um die in einer bestimmten Sprache oder in geografischen Regions Einstellungen verwendeten Zeichen darzustellen.

PowerShell verwendet standardmäßig einen Unicode-Zeichensatz. Mehrere Cmdlets verfügen jedoch über einen **Codierungs** Parameter, mit dem die Codierung für einen anderen Zeichensatz angegeben werden kann. Mit diesem Parameter können Sie die jeweilige Zeichencodierung auswählen, die für die Interoperabilität mit anderen Systemen und Anwendungen erforderlich ist.

Die folgenden Cmdlets haben den **Codierungs** Parameter:

- Microsoft.PowerShell.Management
  - Add-Content
  - Get-Content
  - Set-Content
- Microsoft.PowerShell.Utility
  - Export-Clixml
  - Export-Csv
  - Export-PSSession
  - Format-Hex
  - Import-Csv
  - Out-File
  - Select-String
  - Send-MailMessage

## <a name="the-byte-order-mark"></a>Byte-Reihenfolge Markierung

Byte-Order-Mark (BOM) ist eine _Unicode-Signatur_ in den ersten Bytes einer Datei oder eines Textstreams, die angeben, welche Unicode-Codierung für die Daten verwendet wird. Weitere Informationen finden Sie im Artikel zur [Byte Reihenfolge-Markierung](https://wikipedia.org/wiki/Byte_order_mark) in Wikipedia.

In Windows PowerShell erstellt jede Unicode-Codierung, außer `UTF7` , immer eine BOM. PowerShell Core wird standardmäßig `utf8NoBOM` für die gesamte Textausgabe verwendet.

Vermeiden Sie die Verwendung von BOMs in UTF-8-Dateien, um eine optimale Gesamt Kompatibilität zu erzielen. Auf Windows-Plattformen verwendete UNIX-und UNIX-Dienstprogramme unterstützen BOMs nicht.

Ebenso `UTF7` sollte die Codierung vermieden werden. UTF-7 ist keine standardmäßige Unicode-Codierung und wird in allen Versionen von PowerShell ohne eine BOM geschrieben.

Das Erstellen von PowerShell-Skripts auf einer Unix-ähnlichen Plattform oder die Verwendung eines plattformübergreifenden Editors unter Windows, z. b. Visual Studio Code, führt zu einer Datei, die mit codiert ist `UTF8NoBOM` Diese Dateien funktionieren in PowerShell Core einwandfrei, können aber in Windows PowerShell unterbrechen, wenn die Datei nicht-ASCII-Zeichen enthält.

Wenn Sie nicht-ASCII-Zeichen in Ihren Skripts verwenden müssen, speichern Sie Sie als UTF-8 mit BOM. Ohne die BOM interpretiert Windows PowerShell das Skript so, als dass es auf der Legacy-Codepage "ANSI" codiert wird. Im Gegensatz dazu können Dateien, die die UTF-8-BOM aufweisen, auf Unix-ähnlichen Plattformen problematisch sein. Viele Unix-Tools wie `cat` , `sed` , `awk` und einige Editoren, wie z `gedit` . b., wissen nicht, wie die BOM behandelt werden kann.

## <a name="character-encoding-in-windows-powershell"></a>Zeichencodierung in Windows PowerShell

In PowerShell 5,1 unterstützt der **Encoding** -Parameter die folgenden Werte:

- `Ascii` Verwendet den ASCII-Zeichensatz (7-Bit).
- `BigEndianUnicode` Verwendet UTF-16 mit der Big-Endian-Byte Reihenfolge.
- `BigEndianUTF32` Verwendet UTF-32 mit der Big-Endian-Byte Reihenfolge.
- `Byte` Codiert eine Reihe von Zeichen in eine Bytefolge.
- `Default` Verwendet die Codierung, die der aktiven Codepage des Systems entspricht (normalerweise ANSI).
- `Oem` Verwendet die Codierung, die der aktuellen OEM-Codepage des Systems entspricht.
- `String` Identisch mit `Unicode`.
- `Unicode` Verwendet UTF-16 mit der Little-Endian-Byte Reihenfolge.
- `Unknown` Identisch mit `Unicode`.
- `UTF32` Verwendet UTF-32 mit der Little-Endian-Byte Reihenfolge.
- `UTF7` Verwendet UTF-7.
- `UTF8` Verwendet UTF-8 (mit BOM).

Im Allgemeinen verwendet Windows PowerShell standardmäßig die [UTF-16LE-Unicode-](https://wikipedia.org/wiki/UTF-16) Codierung. Die Standard Codierung, die von Cmdlets in Windows PowerShell verwendet wird, ist jedoch nicht konsistent.

> [!NOTE]
> Bei Verwendung einer beliebigen Unicode-Codierung, mit Ausnahme von `UTF7` , wird immer eine BOM erstellt.

Für Cmdlets, die die Ausgabe in Dateien schreiben:

- `Out-File` und die Umleitungs Operatoren `>` und `>>` Erstellen UTF-16LE, die sich insbesondere von und unterscheiden `Set-Content` `Add-Content` .

- `New-ModuleManifest``Export-CliXml`außerdem werden UTF-16LE-Dateien erstellt.

- Wenn die Zieldatei leer ist oder nicht vorhanden ist, verwenden Sie die `Set-Content` - `Add-Content` `Default` Codierung. `Default` die durch die ANSI-Legacy Codepage des aktiven System Gebiets Schemas angegebene Codierung.

- `Export-Csv` erstellt `Ascii` Dateien, verwendet jedoch unterschiedliche Codierungen, wenn der **Append** -Parameter verwendet wird (siehe unten).

- `Export-PSSession` erstellt standardmäßig UTF-8-Dateien mit BOM.

- `New-Item -Type File -Value` erstellt eine BOM-lose UTF-8-Datei.

- `Send-MailMessage` verwendet `Default` standardmäßig die Codierung.

- `Start-Transcript` erstellt `Utf8` Dateien mit einer BOM. Wenn der **Append** -Parameter verwendet wird, kann die Codierung abweichen (siehe unten).

Für Befehle, die an eine vorhandene Datei anfügen:

- `Out-File -Append` und der `>>` Umleitungs Operator versuchen nicht, die Codierung des Inhalts der vorhandenen Zieldatei abzugleichen. Stattdessen verwenden Sie die Standard Codierung, es sei denn, der **Encoding** -Parameter wird verwendet. Sie müssen die ursprünglichen Codierungs Dateien verwenden, wenn Sie Inhalt anfügen.

- Wenn kein expliziter **Codierungs** Parameter vorhanden ist, wird `Add-Content` die vorhandene Codierung von erkannt und automatisch auf den neuen Inhalt angewendet. Wenn für den vorhandenen Inhalt keine BOM vorhanden ist, `Default` wird die ANSI-Codierung verwendet. Das Verhalten von `Add-Content` ist in PowerShell Core (V6 und höher) identisch, mit dem Unterschied, dass die Standard Codierung ist `Utf8` .

- `Export-Csv -Append` entspricht der vorhandenen Codierung, wenn die Zieldatei eine BOM enthält. Wenn keine BOM vorhanden ist, wird die `Utf8` Codierung verwendet.

- `Start-Transcript -Append` entspricht der vorhandenen Codierung von Dateien, die eine BOM enthalten. Wenn keine BOM vorhanden ist, wird standardmäßig die `Ascii` Codierung verwendet. Diese Codierung kann zu Datenverlusten oder Zeichen Beschädigungen führen, wenn die Daten in der Aufzeichnung Multibytezeichen enthalten.

Für Cmdlets, die Zeichen folgen Daten lesen, wenn keine BOM vorhanden ist:

- `Get-Content` und `Import-PowerShellDataFile` verwenden die `Default` ANSI-Codierung. ANSI ist auch das, was die PowerShell-Engine verwendet, wenn Sie Quellcode aus Dateien liest.

- `Import-Csv`, `Import-CliXml` und `Select-String` gehen davon aus, dass `Utf8` keine BOM vorhanden ist.

## <a name="character-encoding-in-powershell-core"></a>Zeichencodierung in PowerShell Core

In PowerShell Core (V6 und höher) unterstützt der **Encoding** -Parameter die folgenden Werte:

- `ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).
- `bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.
- `oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.
- `unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.
- `utf7`: Codiert im UTF-7-Format.
- `utf8`: Codiert im UTF-8-Format (keine BOM).
- `utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).
- `utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).
- `utf32`: Codiert im UTF-32-Format.

PowerShell Core wird standardmäßig `utf8NoBOM` für alle Ausgaben verwendet.

Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.). Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage).

## <a name="changing-the-default-encoding"></a>Ändern der Standard Codierung

PowerShell verfügt über zwei Standardvariablen, mit denen das Standard Codierungs Verhalten geändert werden kann.

- `$PSDefaultParameterValues`
- `$OutputEncoding`

Weitere Informationen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).

Ab PowerShell 5,1 wird das-Cmdlet von den Umleitungs Operatoren ( `>` und `>>` ) aufgerufen `Out-File` . Daher können Sie die Standard Codierung für diese mithilfe der Preference- `$PSDefaultParameterValues` Variablen festlegen, wie im folgenden Beispiel gezeigt:

```powershell
$PSDefaultParameterValues['Out-File:Encoding'] = 'utf8'
```

Verwenden Sie die folgende Anweisung, um die Standard Codierung für alle Cmdlets zu ändern, die über den **Encoding** -Parameter verfügen.

```powershell
$PSDefaultParameterValues['*:Encoding'] = 'utf8'
```

> [!IMPORTANT]
> Wenn Sie diesen Befehl in das PowerShell-Profil einfügen, ist dies eine Einstellung für eine Sitzungs globale Einstellung, die sich auf alle Befehle und Skripts auswirkt, die nicht explizit eine Codierung angeben.
>
> Ebenso sollten Sie solche Befehle in Ihre Skripts oder Module einschließen, die Sie auf dieselbe Weise Verhalten möchten. Wenn Sie diese Befehle verwenden, stellen Sie sicher, dass sich Cmdlets auch dann Verhalten, wenn Sie von einem anderen Benutzer, einem anderen Computer oder einer anderen Version von PowerShell ausgeführt werden.

Die automatische Variable `$OutputEncoding` wirkt sich auf die Codierung aus, die von PowerShell zur Kommunikation mit externen Programmen verwendet wird. Dies hat keine Auswirkung auf die Codierung, die von den Ausgabe Umleitungs Operatoren und PowerShell-Cmdlets zum Speichern in Dateien verwendet wird.

## <a name="see-also"></a>Siehe auch

- [Einführung in die Zeichencodierung in .NET](/dotnet/standard/base-types/character-encoding-introduction)
- [Codepages-Win32-apps](/windows/win32/intl/code-pages)
- [Der Unicode-Standard](https://www.unicode.org/standard/standard.html)
- [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage)
- [UTF-16LE](https://wikipedia.org/wiki/UTF-16)
- [Byte Reihenfolge Markierung](https://wikipedia.org/wiki/Byte_order_mark)
- [about_Preference_Variables](about_Preference_Variables.md)
