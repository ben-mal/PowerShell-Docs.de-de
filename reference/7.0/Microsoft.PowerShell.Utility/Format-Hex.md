---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 6cb02f1c6f2583ce4146356fac3553e99a54c7c2
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211031"
---
# Format-Hex

## ZUSAMMENFASSUNG

Zeigt eine Datei oder eine andere Eingabe als hexadezimal an.

## SYNTAX

### Pfad (Standard)

```
Format-Hex [-Path] <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### LiteralPath

```
Format-Hex -LiteralPath <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### Byinputobject
```
Format-Hex -InputObject <PSObject> [-Encoding <Encoding>] [-Count <Int64>] [-Offset <Int64>] [-Raw]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Format-Hex` Cmdlet wird eine Datei oder eine andere Eingabe als hexadezimale Werte angezeigt. Um den Offset eines Zeichens aus der Ausgabe zu ermitteln, fügen Sie die Nummer am äußersten linken Rand der Zeile der Zahl am oberen Rand der Spalte für dieses Zeichen hinzu.

`Format-Hex`Mithilfe des Cmdlets können Sie den Dateityp einer beschädigten Datei oder einer Datei ermitteln, die möglicherweise keine Dateinamenerweiterung hat. Sie können dieses Cmdlet ausführen und dann die hexadezimale Ausgabe lesen, um Dateiinformationen zu erhalten.

Wenn Sie `Format-Hex` für eine Datei verwenden, ignoriert das Cmdlet Zeilen neue Zeichen und gibt den gesamten Inhalt einer Datei in einer Zeichenfolge zurück, in der die Zeilen mit dem Zeilen Abschluss beibehalten werden.

## BEISPIELE

### Beispiel 1: erhalten der hexadezimalen Darstellung einer Zeichenfolge

Dieser Befehl gibt die hexadezimalen Werte einer Zeichenfolge zurück.

```powershell
'Hello World' | Format-Hex
```

```Output
   Label: String (System.String) <2944BEC3>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 48 65 6C 6C 6F 20 57 6F 72 6C 64                Hello World
```

Die Zeichenfolge **Hallo Welt** wird über die Pipeline an das `Format-Hex` Cmdlet gesendet. Die hexadezimale Ausgabe von `Format-Hex` zeigt die Werte der einzelnen Zeichen in der Zeichenfolge an.

### Beispiel 2: Suchen eines Dateityps aus der hexadezimalen Ausgabe

In diesem Beispiel wird die hexadezimale Ausgabe verwendet, um den Dateityp zu bestimmen. Das-Cmdlet zeigt den vollständigen Pfad der Datei und die hexadezimalen Werte an.

Um den folgenden Befehl zu testen, erstellen Sie eine Kopie einer vorhandenen PDF-Datei auf dem lokalen Computer, und benennen Sie die kopierte Datei in um `File.t7f` .

```powershell
Format-Hex -Path .\File.t7f -Count 48
```

```Output
   Label: C:\Test\File.t7f

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D %PDF-1.5..%????.
0000000000000010 0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70 .1 0 obj..<</Typ
0000000000000020 65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20 e/Catalog/Pages
```

Das `Format-Hex` Cmdlet verwendet den **path** -Parameter, um einen Dateinamen im aktuellen Verzeichnis anzugeben `File.t7f` . Die Dateierweiterung `.t7f` ist nicht üblich, aber die hexadezimale Ausgabe `%PDF` zeigt, dass es sich um eine PDF-Datei handelt. In diesem Beispiel wird der **count** -Parameter verwendet, um die Ausgabe auf die ersten 48 Bytes der Datei zu beschränken.

### Beispiel 3: Formatieren eines Arrays mit unterschiedlichen Datentypen

In diesem Beispiel wird ein Array verschiedener Datentypen verwendet, um hervorzuheben, wie `Format-Hex` Sie in der Pipeline behandelt werden.

Jedes Objekt wird durch die Pipeline übergeben und einzeln verarbeitet. Wenn es sich jedoch um numerische Daten handelt und das angrenzende Objekt auch numerisch ist, werden diese in einem einzelnen Ausgabe Block gruppiert.

```powershell
'Hello world!', 1, 1138, 'foo', 'bar', 0xdeadbeef, 1gb, 0b1101011100 , $true, $false | Format-Hex
```

```Output
   Label: String (System.String) <24F1F0A3>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 48 65 6C 6C 6F 20 77 6F 72 6C 64 21             Hello world!

   Label: Int32 (System.Int32) <2EB933C5>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 72 04 00 00                         �   r�

   Label: String (System.String) <4078B66C>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 66 6F 6F                                        foo

   Label: String (System.String) <51E4A317>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 62 61 72                                        bar

   Label: Int32 (System.Int32) <5ADF167B>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 EF BE AD DE 00 00 00 40 5C 03 00 00             ï¾­Þ   @\�

   Label: Boolean (System.Boolean) <7D8C4C1D>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 00 00 00 00                         �
```

## PARAMETERS

### -Codierung

Gibt die Codierung der Eingabe Zeichenfolgen an. Dies gilt nur für `[string]` Eingaben. Der-Parameter hat keine Auswirkung auf numerische Typen. Der Ausgabewert ist immer `utf8NoBOM` .

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- `ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).
- `bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.
- `oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.
- `unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.
- `utf7`: Codiert im UTF-7-Format.
- `utf8`: Codiert im UTF-8-Format.
- `utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).
- `utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).
- `utf32`: Codiert im UTF-32-Format.

Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.). Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

```yaml
Type: System.Text.Encoding
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Wird für Pipeline Eingaben verwendet. Pipeline Eingaben unterstützen nur bestimmte skalare Typen und `[system.io.fileinfo]` Instanzen für die Weiterleitung von `Get-ChildItem` .

Die folgenden skalaren Typen werden unterstützt:

- `[string]`, `[char]`
- `[byte]`, `[sbyte]`
- `[int16]`, `[uint16]`, `[short]`, `[ushort]`
- `[int]`, `[uint]`, `[int32]`, `[uint32]`,
- `[long]`, `[ulong]`, `[int64]`, `[uint64]`
- `[single]`, `[float]`, `[double]`
- `[boolean]`

Vor PowerShell 6,2 `Format-Hex` verarbeitet eine Pipeline Eingabe mit mehreren Eingabetypen, indem alle like-Objekte gruppiert werden. Nun werden die einzelnen Objekte verarbeitet, wenn Sie die Pipeline durchlaufen, und Objekte nicht gruppieren, es sei denn, die Objekte sind angrenzend.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Literalpath

Gibt den kompletten Pfad zu einer Datei an. Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.
Dieser Parameter akzeptiert keine Platzhalter Zeichen. Wenn Sie mehrere Pfade zu Dateien angeben möchten, trennen Sie die Pfade durch ein Komma. Wenn der **literalpath** -Parameter Escapezeichen enthält, müssen Sie den Pfad in einfache Anführungszeichen einschließen. PowerShell interpretiert keine Zeichen in einer einzelnen Zeichenfolge in Anführungszeichen als Escapesequenzen. Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt den Pfad zu den Dateien an. Verwenden Sie einen Punkt ( `.` ), um den aktuellen Speicherort anzugeben. Das Platzhalter Zeichen ( `*` ) wird akzeptiert und kann verwendet werden, um alle Elemente in einem Speicherort anzugeben. Wenn der **path** -Parameter Escapezeichen enthält, müssen Sie den Pfad in einfache Anführungszeichen einschließen. Wenn Sie mehrere Pfade zu Dateien angeben möchten, trennen Sie die Pfade durch ein Komma.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -RAW

Dieser Parameter hat keine weiteren Aktionen. Sie wird für die Skript Kompatibilität beibehalten.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Offset

Diese gibt die Anzahl der Bytes an, die von einem Teil der hexadezimalen Ausgabe ausgelassen werden sollen.

Dieser Parameter wurde in PowerShell 6,2 eingeführt.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Anzahl

Gibt die Anzahl der Bytes an, die in die hexadezimale Ausgabe eingeschlossen werden sollen.

Dieser Parameter wurde in PowerShell 6,2 eingeführt.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Int64.MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine Zeichenfolge über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Microsoft. PowerShell. Commands. bytecollection

Dieses Cmdlet gibt eine **bytecollection** zurück. Dieses Objekt stellt eine Auflistung von Bytes dar. Sie enthält Methoden, mit denen die Auflistung von Bytes in eine Zeichenfolge konvertiert wird, die wie jede von zurückgegebene Ausgabezeile formatiert ist `Format-Hex` . Die Ausgabe gibt auch an, welche Bytes verarbeitet werden. Wenn Sie den **path** -oder **literalpath** -Parameter angeben, enthält das-Objekt den Pfad der Datei, die jedes Byte enthält. Wenn Sie eine Zeichenfolge, einen booleschen Wert, einen ganzzahligen Wert usw. übergeben, wird dieser entsprechend gekennzeichnet.

## HINWEISE

In der äußersten rechten Spalte der Ausgabe wird versucht, die Bytes als ASCII-Zeichen zu Renderen:

Im Allgemeinen wird jedes Byte als Unicode-Codepunkt interpretiert, was Folgendes bedeutet:

- Druckbare ASCII-Zeichen werden immer korrekt gerendert.
- Mehr Byte-UTF-8-Zeichen werden nie korrekt dargestellt.
- UTF-16-Zeichen werden nur dann ordnungsgemäß dargestellt, wenn Ihr höher gestelltem Byte ist `NUL` .

## VERWANDTE LINKS

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[Format-Custom](Format-Custom.md)

[Format-List](Format-List.md)

[Format-Table](Format-Table.md)

[Format-Wide](Format-Wide.md)
