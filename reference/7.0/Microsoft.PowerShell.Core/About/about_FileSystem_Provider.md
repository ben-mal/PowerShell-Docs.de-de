---
description: FileSystem
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_filesystem_provider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: FileSystem-Anbieter
ms.openlocfilehash: 50ce68e97937326e9dd7030145ffd417be15ed6b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223836"
---
# <a name="filesystem-provider"></a>FileSystem provider

## <a name="provider-name"></a>Anbietername
FileSystem

## <a name="drives"></a>Laufwerke

`C:`, `D:` ...

## <a name="capabilities"></a>Funktionen

**Filter** , **Schulter verarbeiten**

## <a name="short-description"></a>Kurze Beschreibung

Ermöglicht den Zugriff auf Dateien und Verzeichnisse.

## <a name="detailed-description"></a>Detaillierte Beschreibung

Mit dem PowerShell- **Dateisystem** Anbieter können Sie Dateien und Verzeichnisse in PowerShell erhalten, hinzufügen, ändern, löschen und löschen.

Die **Dateisystem** Laufwerke sind ein hierarchischer Namespace, der die Verzeichnisse und Dateien auf Ihrem Computer enthält. Bei einem **Dateisystem** Laufwerk kann es sich um ein logisches oder ein phsyisches Laufwerk, ein Verzeichnis oder eine zugeordnete Netzwerkfreigabe handeln.

Ein Laufwerk `TEMP:` mit dem Namen wird dem temporären Verzeichnispfad des Benutzers zugeordnet.

>[!NOTE]
> Der Inhalt des Temp:-Laufwerks wird nicht automatisch von PowerShell entfernt und ist für den Benutzer oder das Betriebssystem zur Verwaltung fest.

Der **File System** -Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)
- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Remove-ItemProperty](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [Get-Acl](xref:Microsoft.PowerShell.Security.Get-Acl)
- [Set-Acl](xref:Microsoft.PowerShell.Security.Set-Acl)
- [Get-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a>Von diesem Anbieter verfügbar gemachte Typen

Dateien sind Instanzen der [System. IO. FileInfo](/dotnet/api/system.io.fileinfo) -Klasse.  Verzeichnisse sind Instanzen der [System. IO. DirectoryInfo](/dotnet/api/system.io.directoryinfo) -Klasse.

## <a name="navigating-the-filesystem-drives"></a>Navigieren in den Dateisystem Laufwerken

Der **File System** -Anbieter macht seine Datenspeicher verfügbar, indem logische Laufwerke auf dem Computer als PowerShell-Laufwerke dargestellt werden. Wenn Sie mit einem **Dateisystem** Laufwerk arbeiten möchten, können Sie den Speicherort in ein Laufwerk ändern, auf den der Laufwerk Name folgt, gefolgt von einem Doppelpunkt ( `:` ).

```powershell
Set-Location C:
```

Sie können auch mit dem **File System** -Anbieter von jedem anderen PowerShell-Laufwerk aus arbeiten. Um auf eine Datei oder ein Verzeichnis von einem anderen Speicherort zu verweisen, verwenden Sie den Namen des Laufwerks ( `C:` , `D:` ,...) im Pfad.

> [!NOTE]
> PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten. Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="getting-files-and-directories"></a>Dateien und Verzeichnisse werden erhalten.

Mit dem- `Get-ChildItem` Cmdlet werden alle Dateien und Verzeichnisse an der aktuellen Position zurückgegeben. Sie können einen anderen Suchpfad angeben und integrierte Parameter verwenden, um die Rekursions Tiefe zu filtern und zu steuern.

```powershell
Get-ChildItem
```

Weitere Informationen zur Verwendung von Cmdlets finden Sie unter [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem).

## <a name="copying-files-and-directories"></a>Kopieren von Dateien und Verzeichnissen

`Copy-Item`Mit dem-Cmdlet werden Dateien und Verzeichnisse an einen von Ihnen angegebenen Speicherort kopiert.
Parameter sind zum Filtern und rekurdieren verfügbar, ähnlich wie `Get-ChildItem` .

Mit dem folgenden Befehl werden alle Dateien und Verzeichnisse unter dem Pfad "c:\temp \" " in den Ordner "c:\Windows\Temp" kopiert.

```powershell
Copy-Item -Path C:\temp\* -Destination C:\Windows\Temp -Recurse -File
```

`Copy-Item` überschreibt Dateien im Zielverzeichnis, ohne zur Bestätigung aufzufordern.

Mit diesem Befehl wird die `a.txt` Datei aus dem `C:\a` Verzeichnis in das `C:\a\bb` Verzeichnis kopiert.

```powershell
Copy-Item -Path C:\a\a.txt -Destination C:\a\bb\a.txt
```

Kopiert alle Verzeichnisse und Dateien im Verzeichnis in `C:\a` das `C:\c` Verzeichnis. Wenn die zu kopierenden Verzeichnisse bereits im Zielverzeichnis vorhanden sind, schlägt der Befehl fehl, es sei denn, Sie geben den Force-Parameter an.

```powershell
Copy-Item -Path C:\a\* -Destination C:\c -Recurse
```

Weitere Informationen finden Sie unter [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item).

## <a name="moving-files-and-directories"></a>Verschieben von Dateien und Verzeichnissen

Mit diesem Befehl wird die `c.txt` Datei im `C:\a` Verzeichnis in das `C:\a\aa` Verzeichnis verschoben:

```powershell
Move-Item -Path C:\a\c.txt -Destination C:\a\aa
```

Der Befehl überschreibt nicht automatisch eine vorhandene Datei, die den gleichen Namen hat. Um das Cmdlet zu zwingen, eine vorhandene Datei zu überschreiben, geben Sie den Force-Parameter an.

Ein Verzeichnis kann nicht verschoben werden, wenn das Verzeichnis der aktuelle Speicherort ist. Wenn Sie verwenden, `Move-Item` um das Verzeichnis am aktuellen Speicherort zu verschieben, wird dieser Fehler angezeigt.

```
C:\temp> Move-Item -Path C:\temp\ -Destination C:\Windows\Temp

Move-Item : Cannot move item because the item at 'C:\temp\' is in use.
At line:1 char:1
+ Move-Item C:\temp\ C:\temp2\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Move-Item], PSInvalidOperationException
    + FullyQualifiedErrorId : InvalidOperation,Microsoft.PowerShell.Commands.MoveItemCommand
```

## <a name="managing-file-content"></a>Verwalten von Dateiinhalten

### <a name="get-the-content-of-a-file"></a>Inhalt einer Datei erhalten

Mit diesem Befehl wird der Inhalt der Datei "Test.txt" abgerufen und in der-Konsole angezeigt.

```powershell
Get-Content -Path Test.txt
```

Sie können den Inhalt der Datei an ein anderes Cmdlet leiten. Der folgende Befehl liest z. b. den Inhalt der `Test.txt` Datei und stellt diese dann als Eingabe für das [ConvertTo-HTML-](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) Cmdlet bereit:

```powershell
Get-Content -Path Test.txt | ConvertTo-Html
```

Sie können den Inhalt einer Datei auch abrufen, indem Sie den Anbieter Pfad mit dem Dollarzeichen ( `$` ) versehen. Der Pfad muss in geschweifte Klammern eingeschlossen werden, da Einschränkungen für Variablen benannt werden. Weitere Informationen finden Sie unter [about_Variables](about_Variables.md).

```powershell
${C:\Windows\System32\Drivers\etc\hosts}
```

### <a name="add-content-to-a-file"></a>Hinzufügen von Inhalt zu einer Datei

Dieser Befehl fügt die Zeichenfolge "Test Content" an die `Test.txt` Datei an:

```powershell
Add-Content -Path test.txt -Value "test content"
```

Der vorhandene Inhalt in der `Test.txt` Datei wird nicht gelöscht.

### <a name="replace-the-content-of-a-file"></a>Ersetzen des Inhalts einer Datei

Dieser Befehl ersetzt den Inhalt der `Test.txt` Datei durch die Zeichenfolge "Test Content":

```powershell
Set-Content -Path test.txt -Value "test content"
```

Er überschreibt den Inhalt von `Test.txt` . Sie können den **value** -Parameter des [New-Item-](xref:Microsoft.PowerShell.Management.New-Item) Cmdlets verwenden, um einer Dateiinhalt hinzuzufügen, wenn Sie Sie erstellen.

### <a name="loop-through-the-contents-of-a-file"></a>Durchlaufen Sie den Inhalt einer Datei.

Standardmäßig verwendet das `Get-Content` Cmdlet das Zeilenendezeichen als Trennzeichen, sodass es eine Datei als eine Auflistung von Zeichen folgen erhält, wobei jede Zeile eine Zeichenfolge in der Datei ist.

Sie können den- `-Delimiter` Parameter verwenden, um ein alternatives Trennzeichen anzugeben. Wenn Sie dafür die Zeichen festlegen, die das Ende eines Abschnitts oder den Anfang des nächsten Abschnitts kennzeichnen, können Sie die Datei in logische Teile aufteilen.

Der erste Befehl ruft die `Employees.txt` Datei ab und teilt Sie in Abschnitte auf, von denen jede mit den Wörtern "End of Employee Record" endet, und speichert Sie in der `$e` Variablen.

Der zweite Befehl verwendet die Array Notation, um das erste Element in der Auflistung in zu erhalten `$e` . Es wird ein Index von 0 verwendet, da PowerShell-Arrays NULL basiert sind.

Weitere Informationen zum `Get-Content` Cmdlet finden Sie im Hilfethema zu " [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)".

Weitere Informationen zu Arrays finden Sie unter [about_Arrays](../About/about_Arrays.md).

```powershell
$e = Get-Content c:\test\employees.txt -Delimited "End Of Employee Record"
$e[0]
```

## <a name="managing-security-descriptors"></a>Verwalten von Sicherheits Deskriptoren

### <a name="view-the-acl-for-a-file"></a>Anzeigen der ACL für eine Datei

Dieser Befehl gibt ein [System. Security. AccessControl. FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) -Objekt zurück:

```powershell
Get-Acl -Path test.txt | Format-List -Property *
```

Um weitere Informationen zu diesem Objekt zu erhalten, übergeben Sie den Befehl an das Cmdlet " [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member) ". Weitere Informationen finden Sie unter "[File Security](/dotnet/api/system.security.accesscontrol.filesecurity) Class" in der MSDN (Microsoft Developer Network)-Bibliothek.

### <a name="modify-the-acl-for-a-file"></a>Ändern der ACL für eine Datei

### <a name="create-and-set-an-acl-for-a-file"></a>Erstellen und Festlegen einer ACL für eine Datei

## <a name="creating-files-and-directories"></a>Erstellen von Dateien und Verzeichnissen

### <a name="create-a-directory"></a>Erstellen eines Verzeichnisses

Mit diesem Befehl wird das `logfiles` Verzeichnis auf dem `C` Laufwerk erstellt:

```powershell
New-Item -Path c:\ -Name logfiles -Type directory
```

PowerShell enthält auch eine `mkdir` Funktion (Alias `md` ), die das Cmdlet [New-Item](xref:Microsoft.PowerShell.Management.New-Item) verwendet, um ein neues Verzeichnis zu erstellen.

### <a name="create-a-file"></a>Erstellen von Dateien

Dieser Befehl erstellt die `log2.txt` Datei im `C:\logfiles` Verzeichnis und fügt dann die Zeichenfolge "Testprotokoll" zur Datei hinzu:

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file
```

### <a name="create-a-file-with-content"></a>Erstellen einer Datei mit Inhalt

Erstellt eine Datei mit dem Namen `log2.txt` im `C:\logfiles` Verzeichnis und fügt die Zeichenfolge "Test log" zur Datei hinzu.

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file -Value "test log"
```

## <a name="renaming-files-and-directories"></a>Umbenennen von Dateien und Verzeichnissen

### <a name="rename-a-file"></a>Umbenennen einer Datei

Mit diesem Befehl wird die `a.txt` Datei im `C:\a` Verzeichnis in umbenannt `b.txt` :

```powershell
Rename-Item -Path c:\a\a.txt -NewName b.txt
```

### <a name="rename-a-directory"></a>Umbenennen eines Verzeichnisses

Mit diesem Befehl wird das `C:\a\cc` Verzeichnis in umbenannt `C:\a\dd` :

```powershell
Rename-Item -Path c:\a\cc -NewName dd
```

## <a name="deleting-files-and-directories"></a>Löschen von Dateien und Verzeichnissen

### <a name="delete-a-file"></a>Löschen von Dateien

Mit diesem Befehl wird die `Test.txt` Datei im aktuellen Verzeichnis gelöscht:

```powershell
Remove-Item -Path test.txt
```

### <a name="delete-files-using-wildcards"></a>Löschen von Dateien mithilfe von Platzhaltern

Dieser Befehl löscht alle Dateien im aktuellen Verzeichnis mit der `.xml` Dateinamenerweiterung:

```powershell
Remove-Item -Path *.xml
```

## <a name="starting-a-program-by-invoking-an-associated-file"></a>Starten eines Programms durch Aufrufen einer zugeordneten Datei

### <a name="invoke-a-file"></a>Datei aufrufen

Der erste Befehl verwendet das [Get-Service-](xref:Microsoft.PowerShell.Management.Get-Service) Cmdlet, um Informationen zu lokalen Diensten zu erhalten.

Er leitet die Informationen an das [Export-CSV-](xref:Microsoft.PowerShell.Utility.Export-Csv) Cmdlet weiter und speichert diese Informationen in der `Services.csv` Datei.

Der zweite Befehl verwendet " [aufrufen-Item](xref:Microsoft.PowerShell.Management.Invoke-Item) ", um die `services.csv` Datei in dem Programm zu öffnen, das der Erweiterung zugeordnet ist `.csv` :

```powershell
Get-Service | Export-Csv -Path services.csv
Invoke-Item -Path services.csv
```

## <a name="getting-files-and-folders-with-specified-attributes"></a>Dateien und Ordner mit den angegebenen Attributen werden erhalten.

### <a name="get-system-files"></a>System Dateien erhalten

Dieser Befehl ruft die Systemdateien im aktuellen Verzeichnis und seinen Unterverzeichnissen ab.

Er verwendet den `-File` -Parameter, um nur Dateien (keine Verzeichnisse) abzurufen, und den- `-System` Parameter, um nur Elemente mit dem "System"-Attribut abzurufen.

Er verwendet den `-Recurse` -Parameter, um die Elemente im aktuellen Verzeichnis und allen Unterverzeichnissen abzurufen.

```powershell
Get-ChildItem -File -System -Recurse
```

### <a name="get-hidden-files"></a>Ausgeblendete Dateien

Dieser Befehl ruft alle Dateien ab, einschließlich versteckte Dateien im aktuellen Verzeichnis.

Er verwendet den **Attribute** -Parameter mit zwei Werten, `!Directory+Hidden` , der verborgene Dateien abruft, und `!Directory` , die alle anderen Dateien abruft.

```powershell
Get-ChildItem -Attributes !Directory,!Directory+Hidden
```

`dir -att !d,!d+h` entspricht diesem Befehl.

### <a name="get-compressed-and-encrypted-files"></a>Komprimierte und verschlüsselte Dateien erhalten

Dieser Befehl ruft die Dateien im aktuellen Verzeichnis ab, die entweder komprimiert oder verschlüsselt sind.

Er verwendet den `-Attributes` -Parameter mit zwei Werten, `Compressed` und `Encrypted` . Die Werte werden durch ein Komma getrennt `,` , das den Operator "or" darstellt.

```powershell
Get-ChildItem -Attributes Compressed,Encrypted
```

## <a name="dynamic-parameters"></a>Dynamische Parameter

Dynamische Parameter sind Cmdlet-Parameter, die von einem PowerShell-Anbieter hinzugefügt werden und nur verfügbar sind, wenn das Cmdlet im Anbieter fähigen Laufwerk verwendet wird.

### <a name="encoding-microsoftpowershellcommandsfilesystemcmdletproviderencoding"></a>Codierung von \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\>

Gibt die Dateicodierung an. Der Standardwert ist ASCII.

- **ASCII** : verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).
- **BigEndianUnicode** : codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.
- **String** : verwendet den Codierungstyp für eine Zeichenfolge.
- **Unicode** : codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.
- **UTF7** : codiert im UTF-7-Format.
- **UTF8** : codiert im UTF-8-Format.
- **UTF8BOM** : codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).
- **UF8NOBOM** : codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).
- **UTF32** : codiert im UTF-32-Format.
- **Standard** : codiert auf der standardmäßigen installierten Codepage.
- **OEM** : verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.
- **Unbekannt** : der Codierungstyp ist unbekannt oder ungültig. Die Daten können als Binärdateien behandelt werden.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Add-Content](xref:Microsoft.PowerShell.Management.Add-Content)
- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)
- [Set-Content](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="delimiter-systemstring"></a>Delimiter \<System.String\>

Gibt das Trennzeichen an, das [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) verwendet, um die Datei in Objekte zu unterteilen, während es liest.

Der Standardwert ist `\n` , das Zeilenendezeichen.

Beim Lesen einer Textdatei gibt [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) eine Auflistung von Zeichen folgen Objekten zurück, die jeweils mit dem Trennzeichen enden.

Wenn Sie ein Trennzeichen eingeben, das in der Datei nicht vorhanden ist, gibt [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) die gesamte Datei als einzelnes, nicht durch Trennzeichen getrenntes Objekt zurück.

Sie können diesen Parameter verwenden, um eine große Datei in kleinere Dateien aufzuteilen, indem Sie ein Dateitrennzeichen, wie z. B. "End of Example", als Trennzeichen angeben. Das Trennzeichen wird beibehalten (nicht verworfen) und wird das letzte Element in jedem Dateiabschnitt.

> [!NOTE]
> Wenn der Wert des- `-Delimiter` Parameters eine leere Zeichenfolge ist, gibt [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) aktuell nichts zurück.
> Dies ist ein bekanntes Problem. Um zu erzwingen, dass [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) die gesamte Datei als eine einzelne Zeichenfolge zurückgibt, geben Sie einen Wert ein, der in der Datei nicht vorhanden ist.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="wait-systemmanagementautomationswitchparameter"></a>Wait \<System.Management.Automation.SwitchParameter\>

Wartet auf Inhalt, der an die Datei angefügt wird. Wenn Inhalt angefügt wird, wird der angefügte Inhalt zurückgegeben. Wenn der Inhalt geändert wurde, wird die gesamte Datei zurückgegeben.

In der Warteschlange überprüft [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) die Datei einmal pro Sekunde, bis Sie sie unterbrechen, indem Sie z. B. STRG + C drücken.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="attributes-flagsexpression"></a>Attributes \<FlagsExpression\>

Ruft Dateien und Ordner mit den angegebenen Attributen ab. Dieser Parameter unterstützt alle Attribute und Sie können komplexe Kombinationen von Attributen angeben.

Der- `-Attributes` Parameter wurde in Windows PowerShell 3,0 eingeführt.

Der- `-Attributes` Parameter unterstützt die folgenden Attribute:

- **Archivieren**
- **Compressed**
- **Device**
- **Verzeichnis**
- **Verschlüsselt**
- **Hidden**
- **Normal**
- **Notcontentindiziert**
- **Aufzu**
- **ReadOnly**
- **Analyse Punkt**
- **Sparpfad**
- **System**
- **Temporär**

Eine Beschreibung dieser Attribute finden Sie in der [FileAttribute](/dotnet/api/system.io.fileattributes) -Enumeration.

Verwenden Sie die folgenden Operatoren, um Attribute zu kombinieren.

- `!` -Not
- `+` Und
- `,` Oder

Zwischen einem Operator und dessen Attribut sind keine Leerzeichen zulässig. Allerdings dürfen Leerzeichen vor Kommas gesetzt werden.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="directory-systemmanagementautomationswitchparameter"></a>Directory \<System.Management.Automation.SwitchParameter\>

Ruft die Verzeichnisse (Ordner) ab.

Der- `-Directory` Parameter wurde in Windows PowerShell 3,0 eingeführt.

Um nur Verzeichnisse abzurufen, verwenden Sie den `-Directory` -Parameter, und lassen Sie den- `-File` Parameter Weg. Um Verzeichnisse auszuschließen, verwenden Sie den `-File` -Parameter, und lassen Sie den-Parameter aus `-Directory` , oder verwenden Sie den- `-Attributes` Parameter.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="file-systemmanagementautomationswitchparameter"></a>File \<System.Management.Automation.SwitchParameter\>

Ruft die Dateien ab.

Der- `-File` Parameter wurde in Windows PowerShell 3,0 eingeführt.

Um nur Dateien zu erhalten, verwenden Sie den `-File` -Parameter, und lassen Sie den- `-Directory` Parameter Weg. Um Dateien auszuschließen, verwenden Sie den `-Directory` -Parameter, und lassen Sie den-Parameter aus `-File` , oder verwenden Sie den- `-Attributes` Parameter.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="hidden-systemmanagementautomationswitchparameter"></a>Hidden \<System.Management.Automation.SwitchParameter\>

Ruft nur ausgeblendete Dateien und Verzeichnisse (Ordner) ab. Standardmäßig ruft [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) nur nicht ausgeblendete Elemente ab.

Der- `-Hidden` Parameter wurde in Windows PowerShell 3,0 eingeführt.

Um nur ausgeblendete Elemente zu erhalten, verwenden Sie den- `-Hidden` Parameter, die- `h` oder- `ah` Aliase oder den **Hidden** -Wert des- `-Attributes` Parameters. Um verborgene Elemente auszuschließen, lassen Sie den-Parameter Weg, `-Hidden` oder verwenden Sie den- `-Attributes` Parameter.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="readonly-systemmanagementautomationswitchparameter"></a>ReadOnly \<System.Management.Automation.SwitchParameter\>

Ruft nur schreibgeschützte Dateien und Verzeichnisse (Ordner) ab.

Der- `-ReadOnly` Parameter wurde in Windows PowerShell 3,0 eingeführt.

Um nur schreibgeschützte Elemente zu erhalten, verwenden Sie den- `-ReadOnly` Parameter, den `ar` Alias oder **ReadOnly** den schreibgeschützten Wert des- `-Attributes` Parameters. Um schreibgeschützte Elemente auszuschließen, verwenden Sie den- `-Attributes` Parameter.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="system-systemmanagementautomationswitchparameter"></a>System \<System.Management.Automation.SwitchParameter\>

Ruft nur die Systemdateien und -verzeichnisse (Ordner) ab.

Der- `-System` Parameter wurde in Windows PowerShell 3,0 eingeführt.

Um nur Systemdateien und Ordner zu erhalten, verwenden Sie den- `-System` Parameter, den `as` Alias oder den **System** Wert des- `-Attributes` Parameters. Um Systemdateien und Ordner auszuschließen, verwenden Sie den- `-Attributes` Parameter.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="newerthan-systemdatetime"></a>NewerThan \<System.DateTime\>

Gibt zurück, `$True` Wenn der `LastWriteTime` Wert einer Datei größer als das angegebene Datum ist. Andernfalls wird `$False`zurückgegeben.

Geben Sie ein [DateTime](/dotnet/api/system.datetime) -Objekt ein, z. b. ein Objekt, das vom [Get-Date-](xref:Microsoft.PowerShell.Utility.Get-Date) Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in ein [DateTime](/dotnet/api/system.datetime) -Objekt konvertiert werden kann, z.b. `"August 10, 2011 2:00 PM"` .

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Test-Path](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="olderthan-systemdatetime"></a>OlderThan \<System.DateTime\>

Gibt zurück, `$True` Wenn der `LastWriteTime` Wert einer Datei kleiner als das angegebene Datum ist. Andernfalls wird `$False`zurückgegeben.

Geben Sie ein [DateTime](/dotnet/api/system.datetime) -Objekt ein, z. b. ein Objekt, das vom [Get-Date-](xref:Microsoft.PowerShell.Utility.Get-Date) Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in ein [DateTime](/dotnet/api/system.datetime) -Objekt konvertiert werden kann, z.b. `"August 10, 2011 2:00 PM"` .

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Test-Path](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="stream-systemstring"></a>Stream \<System.String\>

Verwaltet alternative Datenströme. Geben Sie den Namen des Stroms ein. Platzhalter sind nur für Befehle vom Typ " [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) " und " [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item) " in einem Dateisystem Laufwerk zulässig.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Add-Content](xref:Microsoft.PowerShell.Management.Add-Content)
- [Clear-Content](xref:Microsoft.PowerShell.Management.Clear-Content)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Set-Content](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="raw-switchparameter"></a>Raw \<SwitchParameter\>

Neue Zeilenumbruchzeichen werden ignoriert. Gibt Inhalte als ein einzelnes Element zurück.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="itemtype-string"></a>ItemType \<String\>

Mit diesem Parameter können Sie die Tye des zu erstellenden Elements angeben. `New-Item`

Die verfügbaren Werte dieses Parameters hängen vom aktuellen Anbieter ab, den Sie verwenden.

In einem `FileSystem` Laufwerk sind folgende Werte zulässig:

- Datei
- Verzeichnis
- SymbolicLink
- Verbindung
- HardLink

### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a>Verwenden der Pipeline

Anbieter-Cmdlets akzeptieren Pipeline Eingaben. Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden.
Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.

## <a name="getting-help"></a>Hilfe

Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.

Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen [Get-Help-](xref:Microsoft.PowerShell.Core.Get-Help) Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den `-Path` -Parameter von [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) zum Angeben eines Dateisystem Laufwerks.

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path c:
```

## <a name="see-also"></a>Weitere Informationen:

[about_Providers](../About/about_Providers.md)
