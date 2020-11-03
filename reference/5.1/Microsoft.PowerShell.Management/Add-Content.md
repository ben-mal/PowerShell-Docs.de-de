---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 903c4eb784c1bb86b66766c7dfb563f586545dc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215612"
---
# Add-Content

## ZUSAMMENFASSUNG
Fügt den angegebenen Elementen Inhalt hinzu, z. B. Hinzufügen von Wörtern in einer Datei.

## SYNTAX

### Pfad (Standard)

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### LiteralPath

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
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

Das `Add-Content` Cmdlet verwendet den **path** -Parameter, um alle txt-Dateien im aktuellen Verzeichnis anzugeben. Mit dem **Exclude** -Parameter werden Dateinamen ignoriert, die dem angegebenen Muster entsprechen. Der **value** -Parameter gibt die Text Zeichenfolge an, die in die Dateien geschrieben wird.

Verwenden [Sie Get-Content](Get-Content.md) , um den Inhalt dieser Dateien anzuzeigen.

### Beispiel 2: Hinzufügen eines Datums am Ende der angegebenen Dateien

In diesem Beispiel wird das Datum an Dateien im aktuellen Verzeichnis angehängt, und das Datum wird in der PowerShell-Konsole angezeigt.

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

Das `Add-Content` Cmdlet verwendet die **path** -und **value** -Parameter, um zwei neue Dateien im aktuellen Verzeichnis zu erstellen. Der **value** -Parameter gibt das `Get-Date` Cmdlet an, um das Datum zu erhalten, und übergibt das Datum an `Add-Content` . Mit dem- `Add-Content` Cmdlet wird das Datum in jede Datei geschrieben. Der **passthru** -Parameter übergibt ein Objekt, das das Date-Objekt darstellt. Da kein anderes Cmdlet vorhanden ist, um das über gegebene Objekt zu empfangen, wird es in der PowerShell-Konsole angezeigt. Mit dem- `Get-Content` Cmdlet wird die aktualisierte Datei DateTimeFile1. Log angezeigt.

### Beispiel 3: Hinzufügen des Inhalts einer angegebenen Datei zu einer anderen Datei

In diesem Beispiel wird der Inhalt aus einer Datei abgerufen, und dieser Inhalt wird an eine andere Datei angehängt.

```powershell
Add-Content -Path .\CopyToFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\CopyToFile.txt
```

Das `Add-Content` Cmdlet verwendet den **path** -Parameter, um die neue Datei im aktuellen Verzeichnis anzugeben, CopyToFile.txt. Der **value** -Parameter verwendet das- `Get-Content` Cmdlet, um den Inhalt der Datei CopyFromFile.txt zu erhalten. Die Klammern um das `Get-Content` Cmdlet stellen sicher, dass der Befehl abgeschlossen ist, bevor der `Add-Content` Befehl beginnt. Der **value** -Parameter wird an übergeben `Add-Content` . Das- `Add-Content` Cmdlet fügt die Daten an die CopyToFile.txt Datei an. Das- `Get-Content` Cmdlet zeigt die aktualisierte Datei an, CopyToFile.txt.

### Beispiel 4: Verwenden einer Variablen zum Hinzufügen des Inhalts einer angegebenen Datei zu einer anderen Datei

In diesem Beispiel wird der Inhalt aus einer Datei abgerufen und der Inhalt in einer Variablen gespeichert. Die-Variable wird verwendet, um den Inhalt an eine andere Datei anzufügen.

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

Mit dem `Get-Content` -Cmdlet wird der Inhalt CopyFromFile.txt abgerufen und der Inhalt in der `$From` Variablen gespeichert. Das `Add-Content` Cmdlet verwendet den **path** -Parameter, um die CopyToFile.txt Datei im aktuellen Verzeichnis anzugeben. Der **value** -Parameter verwendet die `$From` -Variable und übergibt den Inhalt an `Add-Content` . Mit dem- `Add-Content` Cmdlet wird die CopyToFile.txt Datei aktualisiert. Das- `Get-Content` Cmdlet zeigt CopyToFile.txt an.

### Beispiel 5: Erstellen einer neuen Datei und Kopieren von Inhalten

In diesem Beispiel wird eine neue Datei erstellt und der Inhalt einer vorhandenen Datei in die neue Datei kopiert.

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

Das `Add-Content` Cmdlet verwendet die **path** -und **value** -Parameter, um eine neue Datei im aktuellen Verzeichnis zu erstellen. Der **value** -Parameter verwendet das- `Get-Content` Cmdlet, um den Inhalt einer vorhandenen Datei, CopyFromFile.txt, zu erhalten. Die Klammern um das `Get-Content` Cmdlet stellen sicher, dass der Befehl abgeschlossen ist, bevor der `Add-Content` Befehl beginnt. Der **value** -Parameter übergibt den Inhalt, an `Add-Content` den die NewFile.txt Datei aktualisiert wird. Das- `Get-Content` Cmdlet zeigt den Inhalt der neuen Datei an, NewFile.txt.

### Beispiel 6: Hinzufügen von Inhalt zu einer schreibgeschützten Datei

Mit diesem Befehl wird der Datei der Wert hinzugefügt, auch wenn das Attribut " **isread only** " auf "true" festgelegt ist.
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
-ar---        1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

Das `New-Item` Cmdlet verwendet den **path** -Parameter und den **ItemType** -Parameter, um die Datei IsReadOnlyTextFile.txt im aktuellen Verzeichnis zu erstellen. Das `Set-ItemProperty` Cmdlet verwendet die Parameter **Name** und **value** , um die **isschreib only** -Eigenschaft der Datei in true zu ändern. Das `Get-ChildItem` Cmdlet zeigt, dass die Datei leer ist (0) und das schreibgeschützte Attribut ( `r` ) aufweist. Das `Add-Content` Cmdlet verwendet den **path** -Parameter, um die Datei anzugeben. Der **value** -Parameter enthält die Text Zeichenfolge, die an die Datei angefügt werden soll. Mit dem **Force** -Parameter wird der Text in die schreibgeschützte Datei geschrieben. Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um den Inhalt der Datei anzuzeigen.

Um das schreibgeschützte Attribut zu entfernen, verwenden Sie den- `Set-ItemProperty` Befehl, bei dem der **value** -Parameter auf festgelegt ist `False` .

## PARAMETERS

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

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.

> [!WARNING]
> Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.

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

Gibt den Typ der Codierung für die Zieldatei an. Der Standardwert ist `Default`.

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- `Ascii` Verwendet den ASCII-Zeichensatz (7-Bit).
- `BigEndianUnicode` Verwendet UTF-16 mit der Big-Endian-Byte Reihenfolge.
- `BigEndianUTF32` Verwendet UTF-32 mit der Big-Endian-Byte Reihenfolge.
- `Byte` Codiert eine Reihe von Zeichen in eine Bytefolge.
- `Default` Verwendet die Codierung, die der aktiven Codepage des Systems entspricht (normalerweise ANSI).
- `Oem` Verwendet die Codierung, die der aktuellen OEM-Codepage des Systems entspricht.
- `String` Identisch mit **Unicode** .
- `Unicode` Verwendet UTF-16 mit der Little-Endian-Byte Reihenfolge.
- `Unknown` Identisch mit **Unicode** .
- `UTF7` Verwendet UTF-7.
- `UTF8` Verwendet UTF-8.
- `UTF32` Verwendet UTF-32 mit der Little-Endian-Byte Reihenfolge.

Encoding ist ein dynamischer Parameter, den der File System-Anbieter zum `Add-Content` Cmdlet hinzufügt. Dieser Parameter funktioniert nur in Dateisystemlaufwerken.

```yaml
Type: Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, Byte, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ausschließen

Lässt die angegebenen Elemente aus. Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Geben Sie ein Pfad Element oder-Muster ein, z. b **\* . txt** . Platzhalter sind zulässig.

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

Gibt einen Filter im Format oder in der Sprache des Anbieters an. Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Die Syntax des Filters einschließlich der Verwendung von Platzhaltern ist vom Anbieter abhängig. **Filter** sind effizienter als andere Parameter, da der Anbieter beim Abrufen von Objekten Filter anwendet. Andernfalls verarbeitet PowerShell Filter, nachdem die Objekte abgerufen wurden.

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

Fügt nur die angegebenen Elemente hinzu. Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Geben Sie ein Pfad Element oder-Muster ein, z. b **\* . txt** . Platzhalter sind zulässig.

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

Gibt den Pfad zu den Elementen an, die den zusätzlichen Inhalt erhalten. Im Gegensatz zu **Path** wird der Wert von **LiteralPath** genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

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

Gibt den Pfad zu den Elementen an, die den zusätzlichen Inhalt erhalten. Platzhalter sind zulässig. Wenn Sie mehrere Pfade angeben, trennen Sie diese durch Kommas.

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

Gibt einen alternativen Datenstrom für den Inhalt an. Wenn der Datenstrom nicht vorhanden ist, wird er von diesem Cmdlet erstellt. Platzhalterzeichen werden nicht unterstützt.

**Stream** ist ein dynamischer Parameter, den der File System-Anbieter hinzufügt `Add-Content` . Dieser Parameter funktioniert nur in Dateisystemlaufwerken.

Sie können das `Add-Content` Cmdlet verwenden, um den Inhalt des alternativen Datenstroms " **Zone. Identifier** " zu ändern. Dies wird jedoch nicht empfohlen, um Sicherheitsüberprüfungen zu vermeiden, die Dateien blockieren, die aus dem Internet heruntergeladen werden. Wenn Sie überprüfen, ob eine heruntergeladene Datei sicher ist, verwenden Sie das- `Unblock-File` Cmdlet.

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

### -UseTransaction

Schließt den Befehl in die aktive Transaktion ein. Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird. Weitere Informationen finden Sie unter [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Gibt den hinzuzufügenden Inhalt an. Geben Sie eine Zeichenfolge in Anführungszeichen ein, z. b. **diese Daten sind nur zur internen Verwendung vorgesehen** , oder geben Sie ein Objekt an, das Inhalt enthält, z. b. das **DateTime** -Objekt `Get-Date`

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

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` . Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Object, System. Management. Automation. PSCredential

Sie können Werte, Pfade oder Anmelde Informationen an übergeben `Set-Content` .

## AUSGABEN

### None or System.String

Wenn Sie den **passthru** -Parameter verwenden, `Add-Content` generiert ein **System. String** -Objekt, das den Inhalt darstellt. Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

Wenn Sie ein Objekt an übergeben `Add-Content` , wird das Objekt in eine Zeichenfolge konvertiert, bevor es dem Element hinzugefügt wird. Der Objekttyp bestimmt das Zeichenfolgenformat, das Format kann jedoch von der Standardanzeige des Objekts abweichen. Verwenden Sie die Formatierungsparameter des sendenden Cmdlets zum Steuern des Zeichenfolgenformats.

Sie können auch auf den `Add-Content` integrierten Alias verweisen `ac` . Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Das- `Add-Content` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[Clear-Content](Clear-Content.md)

[Get-Content](Get-Content.md)

[Get-Item](Get-Item.md)

[New-Item](New-Item.md)

[Set-Content](Set-Content.md)
