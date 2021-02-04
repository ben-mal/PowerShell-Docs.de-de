---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: d21765541fb849aed8dc37895c167c0ea34486a3
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692830"
---
# Set-Content

## ZUSAMMENFASSUNG
Schreibt neuen Inhalt oder ersetzt vorhandene Inhalte in einer Datei.

## SYNTAX

### Pfad (Standard)

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### LiteralPath

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## DESCRIPTION

`Set-Content` ist ein Cmdlet für die Zeichen folgen Verarbeitung, das neuen Inhalt schreibt oder den Inhalt in einer Datei ersetzt. `Set-Content` ersetzt den vorhandenen Inhalt und unterscheidet sich von dem `Add-Content` Cmdlet, das Inhalt an eine Datei anfügt. Wenn Sie Inhalte an senden möchten, `Set-Content` können Sie den **value** -Parameter in der Befehlszeile verwenden oder Inhalt über die Pipeline senden.

Wenn Sie für die folgenden Beispiele Dateien oder Verzeichnisse erstellen müssen, finden Sie weitere Informationen unter [New-Item](New-Item.md).

## BEISPIELE

### Beispiel 1: Ersetzen des Inhalts mehrerer Dateien in einem Verzeichnis

In diesem Beispiel wird der Inhalt für mehrere Dateien im aktuellen Verzeichnis ersetzt.

```powershell
Get-ChildItem -Path .\Test*.txt
```

```Output
Test1.txt
Test2.txt
Test3.txt
```

```powershell
Set-Content -Path .\Test*.txt -Value 'Hello, World'
Get-Content -Path .\Test*.txt
```

```Output
Hello, World
Hello, World
Hello, World
```

Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um **txt** -Dateien aufzulisten, die mit `Test*` im aktuellen Verzeichnis beginnen. Das `Set-Content` Cmdlet verwendet den **path** -Parameter, um die `Test*.txt` Dateien anzugeben. Der **value** -Parameter stellt die Text Zeichenfolge **Hello, World** dar, die den vorhandenen Inhalt in jeder Datei ersetzt. Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Dateien anzugeben, `Test*.txt` und zeigt den Inhalt jeder Datei in der PowerShell-Konsole an.

### Beispiel 2: Erstellen einer neuen Datei und Schreiben von Inhalten

In diesem Beispiel wird eine neue Datei erstellt, und das aktuelle Datum und die aktuelle Uhrzeit werden in die Datei geschrieben.

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

`Set-Content` verwendet die **path** -und **value** -Parameter, um eine neue Datei namens **DateTime.txt** im aktuellen Verzeichnis zu erstellen. Der **value** -Parameter verwendet `Get-Date` , um das aktuelle Datum und die aktuelle Uhrzeit zu erhalten.
`Set-Content` schreibt das **DateTime** -Objekt als Zeichenfolge in die Datei. Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um den Inhalt **DateTime.txt** in der PowerShell-Konsole anzuzeigen.

### Beispiel 3: Ersetzen von Text in einer Datei

Dieser Befehl ersetzt alle Instanzen von Word innerhalb einer vorhandenen Datei.

```powershell
Get-Content -Path .\Notice.txt
```

```Output
Warning
Replace Warning with a new word.
The word Warning was replaced.
```

```powershell
(Get-Content -Path .\Notice.txt) |
    ForEach-Object {$_ -Replace 'Warning', 'Caution'} |
        Set-Content -Path .\Notice.txt
Get-Content -Path .\Notice.txt
```

```Output
Caution
Replace Caution with a new word.
The word Caution was replaced.
```

Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die **Notice.txt** Datei im aktuellen Verzeichnis anzugeben. Der `Get-Content` Befehl wird in Klammern eingeschlossen, sodass der Befehl abgeschlossen ist, bevor er an die Pipeline gesendet wird.

Der Inhalt der **Notice.txt** Datei wird über die Pipeline an das `ForEach-Object` Cmdlet gesendet.
`ForEach-Object` verwendet die automatische Variable `$_` und ersetzt jedes Vorkommen von **Warning** durch **Vorsicht**. Die Objekte werden über die Pipeline an das `Set-Content` Cmdlet gesendet. `Set-Content` verwendet den **path** -Parameter, um die **Notice.txt** Datei anzugeben und den aktualisierten Inhalt in die Datei zu schreiben.

Das letzte `Get-Content` Cmdlet zeigt den aktualisierten Dateiinhalt in der PowerShell-Konsole an.

### Beispiel 4: Verwenden von Filtern mit Set-Content

Sie können einen Filter für das `Set-Content` Cmdlet angeben. Wenn Sie den **path** -Parameter mithilfe von Filtern qualifizieren, müssen Sie ein nach gestelltes Sternchen () einfügen, `*` um den Inhalt des Pfads anzugeben.

Mit dem folgenden Befehl wird der Inhalt aller `*.txt` Dateien im `C:\Temp` Verzeichnis auf den leeren **Wert** festgelegt.

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## PARAMETERS

### -Asbytestream

Gibt an, dass der Inhalt als Byte Datenstrom gelesen werden soll. Dieser Parameter wurde in PowerShell 6,0 eingeführt.

Eine Warnung tritt auf, wenn Sie den **asbytestream** -Parameter mit dem **Encoding** -Parameter verwenden. Der **asbytestream** -Parameter ignoriert alle Codierungen, und die Ausgabe wird als Bytestream zurückgegeben.

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

### -Credential

> [!NOTE]
> Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.
> Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Codierung

Gibt den Typ der Codierung für die Zieldatei an. Der Standardwert ist `utf8NoBOM`.

Encoding ist ein dynamischer Parameter, den der File System-Anbieter hinzufügt `Set-Content` . Dieser Parameter funktioniert nur in Dateisystemlaufwerken.

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- `ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).
- `bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.
- `bigendianutf32`: Codiert im UTF-32-Format unter Verwendung der Big-Endian-Byte Reihenfolge.
- `oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.
- `unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.
- `utf7`: Codiert im UTF-7-Format.
- `utf8`: Codiert im UTF-8-Format.
- `utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).
- `utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).
- `utf32`: Codiert im UTF-32-Format.

Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.). Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

> [!NOTE]
> **UTF-7** _ wird nicht mehr für die Verwendung von empfohlen. In PowerShell 7,1 wird eine Warnung geschrieben, wenn Sie `utf7` für den Parameter "_ *Encoding**" angeben.

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ausschließen

Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden. Der Wert dieses Parameters qualifiziert den **Path**-Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b.. Platzhalterzeichen sind zulässig. Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Filter

Gibt einen Filter zum Qualifizieren des **path** -Parameters an. Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt. Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).
Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

Zwingt das Cmdlet, den Inhalt einer Datei festzulegen, auch wenn die Datei schreibgeschützt ist. Die Implementierung unterscheidet sich bei den einzelnen Anbietern. Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).
Der **Force** -Parameter überschreibt keine Sicherheitseinschränkungen.

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

### -Include

Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt. Der Wert dieses Parameters qualifiziert den **Path**-Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b.. Platzhalterzeichen sind zulässig. Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Literalpath

Gibt einen Pfad zu einem oder mehreren Speicherorten an. Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nonewline

Die Zeichen folgen Darstellungen der Eingabe Objekte werden verkettet, um die Ausgabe zu bilden. Zwischen den Ausgabe Zeichenfolgen werden keine Leerzeichen oder Zeilenumbrüche eingefügt. Nach der letzten Ausgabe Zeichenfolge wird kein Zeilen Vorstrich hinzugefügt.

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

### -PassThru

Gibt ein Objekt zurück, das den Inhalt darstellt. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### -Path

Gibt den Pfad des Elements an, das den Inhalt empfängt.
Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Stream

> [!NOTE]
> Dieser Parameter ist nur unter Windows verfügbar.

Gibt einen alternativen Datenstrom für den Inhalt an. Wenn der Datenstrom nicht vorhanden ist, wird er von diesem Cmdlet erstellt. Platzhalterzeichen werden nicht unterstützt.

**Stream** ist ein dynamischer Parameter, den der **File System** -Anbieter hinzufügt `Set-Content` . Dieser Parameter funktioniert nur in Dateisystemlaufwerken.

Sie können das `Set-Content` Cmdlet verwenden, um den Inhalt eines beliebigen Alternativen Datenstroms zu erstellen oder zu aktualisieren, z `Zone.Identifier` . b.. Dies wird jedoch nicht empfohlen, um Sicherheitsüberprüfungen zu vermeiden, die Dateien blockieren, die aus dem Internet heruntergeladen werden. Wenn Sie überprüfen, ob eine heruntergeladene Datei sicher ist, verwenden Sie das- `Unblock-File` Cmdlet.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

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

### -Value

Gibt den neuen Inhalt für das Element an.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### System.Object

Sie können ein Objekt über die Pipeline übergeben, das den neuen Wert für das Element enthält `Set-Content` .

## AUSGABEN

### None or System.String

Wenn Sie den **passthru** -Parameter verwenden, `Set-Content` generiert ein **System. String** -Objekt, das den Inhalt darstellt. Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

- Sie können auch auf den `Set-Content` integrierten Alias verweisen `sc` .
  Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- `Set-Content` ist für die Zeichen folgen Verarbeitung konzipiert. Wenn Sie Objekte, die keine Zeichenfolge `Set-Content` sind, an übergeben, wird das Objekt vor dem Schreiben in eine Zeichenfolge konvertiert. Verwenden Sie, um Objekte in Dateien zu schreiben `Out-File` .
- Das- `Set-Content` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Automatic_Variables. MD](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Add-Content](Add-Content.md)

[Clear-Content](Clear-Content.md)

[Get-ChildItem](Get-ChildItem.md)

[Get-Content](Get-Content.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[New-Item](New-Item.md)
