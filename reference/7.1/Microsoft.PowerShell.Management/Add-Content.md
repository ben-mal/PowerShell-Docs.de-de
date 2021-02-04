---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: ef44fefe68ef9674eb14ce494341bf04f477d55a
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97693010"
---
# Add-Content

## ZUSAMMENFASSUNG
Fügt den angegebenen Elementen Inhalt hinzu, z. B. Hinzufügen von Wörtern in einer Datei.

## SYNTAX

### Pfad (Standard)

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### LiteralPath

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## DESCRIPTION

Das- `Add-Content` Cmdlet fügt Inhalt an ein angegebenes Element oder eine angegebene Datei an. Sie können den Inhalt angeben, indem Sie den Inhalt im Befehl eingeben oder ein Objekt angeben, das den Inhalt enthält.

Wenn Sie für die folgenden Beispiele Dateien oder Verzeichnisse erstellen müssen, finden Sie weitere Informationen unter [New-Item](New-Item.md).

## BEISPIELE

### Beispiel 1: Hinzufügen einer Zeichenfolge zu allen Textdateien mit einer Ausnahme

In diesem Beispiel wird ein Wert an Textdateien im aktuellen Verzeichnis angehängt, die Dateien werden jedoch nicht auf Grundlage ihres Datei namens ausgeschlossen.

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

Der **path** -Parameter gibt alle `.txt` Dateien im aktuellen Verzeichnis an, aber der **Exclude** -Parameter ignoriert Dateinamen, die dem angegebenen Muster entsprechen. Der **value** -Parameter gibt die Text Zeichenfolge an, die in die Dateien geschrieben wird.

### Beispiel 2: Hinzufügen eines Datums am Ende der angegebenen Dateien

In diesem Beispiel wird das Datum an Dateien im aktuellen Verzeichnis angehängt, und das Datum wird in der PowerShell-Konsole angezeigt.

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

```Output
Tuesday, May 14, 2019 8:24:27 AM
Tuesday, May 14, 2019 8:24:27 AM
5/14/2019 8:24:27 AM
```

Mit dem- `Add-Content` Cmdlet werden zwei neue Dateien im aktuellen Verzeichnis erstellt. Der **value** -Parameter enthält die Ausgabe des `Get-Date` Cmdlets. Der **passthru** -Parameter gibt den hinzugefügten Inhalt an die Pipeline aus.
Da kein anderes Cmdlet zum Empfangen der Ausgabe vorhanden ist, wird es in der PowerShell-Konsole angezeigt.
Das- `Get-Content` Cmdlet zeigt die aktualisierte Datei an `DateTimeFile1.log` .

### Beispiel 3: Hinzufügen des Inhalts einer angegebenen Datei zu einer anderen Datei

In diesem Beispiel wird der Inhalt aus einer Datei abgerufen und der Inhalt in einer Variablen gespeichert. Die-Variable wird verwendet, um den Inhalt an eine andere Datei anzufügen.

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

- Mit dem `Get-Content` -Cmdlet wird der Inhalt von abgerufen `CopyFromFile.txt` und der Inhalt in der `$From` Variablen gespeichert.
- Das `Add-Content` Cmdlet aktualisiert die `CopyToFile.txt` Datei mit dem Inhalt der `$From` Variablen.
- Das- `Get-Content` Cmdlet zeigt CopyToFile.txt an.

### Beispiel 4: Hinzufügen des Inhalts einer angegebenen Datei in eine andere Datei mithilfe der Pipeline

In diesem Beispiel wird der Inhalt aus einer Datei abgerufen und an das `Add-Content` Cmdlet weitergeleitet.

```powershell
Get-Content -Path .\CopyFromFile.txt | Add-Content -Path .\CopyToFile.txt
Get-Content -Path .\CopyToFile.txt
```

Mit dem- `Get-Content` Cmdlet wird der Inhalt von abgerufen `CopyFromFile.txt` . Die Ergebnisse werden an das- `Add-Content` Cmdlet weitergeleitet, das aktualisiert `CopyToFile.txt` .
Das letzte `Get-Content` Cmdlet wird angezeigt `CopyToFile.txt` .

### Beispiel 5: Erstellen einer neuen Datei und Kopieren von Inhalten

In diesem Beispiel wird eine neue Datei erstellt und der Inhalt einer vorhandenen Datei in die neue Datei kopiert.

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

- Das `Add-Content` Cmdlet verwendet die **path** -und **value** -Parameter, um eine neue Datei im aktuellen Verzeichnis zu erstellen.
- `Get-Content`Mit dem-Cmdlet wird der Inhalt einer vorhandenen Datei abgerufen `CopyFromFile.txt` und an den **value** -Parameter übergeben. Die Klammern um das `Get-Content` Cmdlet stellen sicher, dass der Befehl abgeschlossen ist, bevor der `Add-Content` Befehl beginnt.
- Das- `Get-Content` Cmdlet zeigt den Inhalt der neuen Datei an `NewFile.txt` .

### Beispiel 6: Hinzufügen von Inhalt zu einer schreibgeschützten Datei

Mit diesem Befehl wird der Datei ein Wert hinzugefügt, auch wenn das Attribut " **isread only** " auf " **true**" festgelegt ist.
Die Schritte zum Erstellen einer schreibgeschützten Datei sind im Beispiel enthalten.

```powershell
New-Item -Path .\IsReadOnlyTextFile.txt -ItemType File
Set-ItemProperty -Path .\IsReadOnlyTextFile.txt -Name IsReadOnly -Value $True
Get-ChildItem -Path .\IsReadOnlyTextFile.txt
Add-Content -Path .\IsReadOnlyTextFile.txt -Value 'Add value to read-only text file' -Force
Get-Content -Path .\IsReadOnlyTextFile.txt
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-ar--         1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

- Das `New-Item` Cmdlet verwendet den **path** -Parameter und den **ItemType** -Parameter, um die Datei `IsReadOnlyTextFile.txt` im aktuellen Verzeichnis zu erstellen.
- Das `Set-ItemProperty` Cmdlet verwendet die Parameter **Name** und **value** , um die **isschreib only** -Eigenschaft der Datei in true zu ändern.
- Das `Get-ChildItem` Cmdlet zeigt, dass die Datei leer ist (0) und das schreibgeschützte Attribut ( `r` ) aufweist.
- Das `Add-Content` Cmdlet verwendet den **path** -Parameter, um die Datei anzugeben. Der **value** -Parameter enthält die Text Zeichenfolge, die an die Datei angefügt werden soll. Mit dem **Force** -Parameter wird der Text in die schreibgeschützte Datei geschrieben.
- Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um den Inhalt der Datei anzuzeigen.

Um das schreibgeschützte Attribut zu entfernen, verwenden Sie den- `Set-ItemProperty` Befehl, bei dem der **value** -Parameter auf festgelegt ist `False` .

### Beispiel 7: Verwenden von Filtern mit Add-Content

Sie können einen Filter für das `Add-Content` Cmdlet angeben. Wenn Sie den **path** -Parameter mithilfe von Filtern qualifizieren, müssen Sie ein nach gestelltes Sternchen () einfügen, `*` um den Inhalt des Pfads anzugeben.

Mit dem folgenden Befehl wird das Wort "Done" zum Inhalt aller `*.txt` Dateien im Verzeichnis hinzugefügt `C:\Temp` .

```powershell
Add-Content -Path C:\Temp\* -Filter *.txt -Value "Done"
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

Encoding ist ein dynamischer Parameter, den der File System-Anbieter zum `Add-Content` Cmdlet hinzufügt. Dieser Parameter funktioniert nur in Dateisystemlaufwerken.

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

Überschreibt das Schreibschutzattribut, sodass Sie einer schreibgeschützten Datei Inhalt hinzufügen können. Beispielsweise überschreibt **Force** das Schreibschutzattribut oder erstellt Verzeichnisse zum Vervollständigen eines Dateipfads. Es wird jedoch nicht etwa versucht, Dateiberechtigungen zu ändern.

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

Gibt an, dass dieses Cmdlet keine neue Zeile oder Wagen Rücklauf zum Inhalt hinzufügt.

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

Gibt ein Objekt zurück, das den hinzugefügten Inhalt darstellt. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

Gibt den Pfad zu den Elementen an, die den zusätzlichen Inhalt erhalten.
Platzhalterzeichen sind zulässig.
Die Pfade müssen auf Elemente und nicht auf Container zeigen.
Sie müssen beispielsweise einen Pfad zu Dateien angeben, ein Pfad zu einem Verzeichnis ist nicht zulässig.
Wenn Sie mehrere Pfade angeben, trennen Sie diese durch Kommas.

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

**Stream** ist ein dynamischer Parameter, den der File System-Anbieter hinzufügt `Add-Content` . Dieser Parameter funktioniert nur in Dateisystemlaufwerken.

Sie können das `Add-Content` Cmdlet verwenden, um den Inhalt eines beliebigen Alternativen Datenstroms zu ändern, z `Zone.Identifier` . b.. Dies wird jedoch nicht empfohlen, um Sicherheitsüberprüfungen zu vermeiden, die Dateien blockieren, die aus dem Internet heruntergeladen werden. Wenn Sie überprüfen, ob eine heruntergeladene Datei sicher ist, verwenden Sie das- `Unblock-File` Cmdlet.

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

Gibt den hinzuzufügenden Inhalt an. Geben Sie eine Zeichenfolge in Anführungszeichen ein, z. b. **diese Daten sind nur zur internen Verwendung vorgesehen**, oder geben Sie ein Objekt an, das Inhalt enthält, z. b. das **DateTime** -Objekt `Get-Date`

Sie können den Inhalt einer Datei nicht angeben, indem Sie Ihren Pfad eingeben, da der Pfad lediglich eine Zeichenfolge ist.
Sie können einen `Get-Content` Befehl verwenden, um den Inhalt zu erhalten und an den **value** -Parameter zu übergeben.

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

### System. Object, System. Management. Automation. PSCredential

Sie können Werte, Pfade oder Anmelde Informationen an übergeben `Set-Content` .

## AUSGABEN

### None or System.String

Wenn Sie den **passthru** -Parameter verwenden, `Add-Content` generiert ein **System. String** -Objekt, das den Inhalt darstellt. Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

- Wenn Sie ein Objekt an übergeben `Add-Content` , wird das Objekt in eine Zeichenfolge konvertiert, bevor es dem Element hinzugefügt wird. Der Objekttyp bestimmt das Zeichenfolgenformat, das Format kann jedoch von der Standardanzeige des Objekts abweichen. Verwenden Sie die Formatierungsparameter des sendenden Cmdlets zum Steuern des Zeichenfolgenformats.
- Sie können auch auf den `Add-Content` integrierten Alias verweisen `ac` . Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- Das- `Add-Content` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Clear-Content](Clear-Content.md)

[Get-Content](Get-Content.md)

[Get-Item](Get-Item.md)

[New-Item](New-Item.md)

[Set-Content](Set-Content.md)
