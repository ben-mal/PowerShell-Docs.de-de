---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ChildItem
ms.openlocfilehash: 9c613686765aa735e1e2cc58bfab533d1dc1e89f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215487"
---
# Get-ChildItem

## ZUSAMMENFASSUNG

Ruft die Elemente und untergeordneten Elemente an angegebenen Speicherorten ab.

## SYNTAX

### Elemente (Standard)

```
Get-ChildItem [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>]
 [-Recurse] [-Depth <uint32>] [-Force] [-Name] [-UseTransaction]
 [-Attributes <FlagsExpression[FileAttributes]>] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System]
 [<CommonParameters>]
```

### Literalitems

```
Get-ChildItem [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>]
 [-Exclude <string[]>] [-Recurse] [-Depth <uint32>] [-Force] [-Name] [-UseTransaction]
 [-Attributes <FlagsExpression[FileAttributes]>] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-ChildItem` Cmdlet werden die Elemente an einem oder mehreren angegebenen Speicherorten abgerufen. Wenn es sich bei dem Element um einen Container handelt, werden die darin enthaltenen (untergeordneten) Elemente abgerufen. Sie können den **recurse** -Parameter verwenden, um Elemente in allen untergeordneten Containern zu erhalten, und den **tiefen** Parameter verwenden, um die Anzahl der Ebenen auf Rekurse zu begrenzen.

`Get-ChildItem` zeigt keine leeren Verzeichnisse an. Wenn ein `Get-ChildItem` Befehl die **Tiefe** oder die **recurse** -Parameter enthält, sind leere Verzeichnisse nicht in der Ausgabe enthalten.

Standorte werden `Get-ChildItem` von PowerShell-Anbietern für verfügbar gemacht. Bei einem Speicherort kann es sich um ein Dateisystem Verzeichnis, eine Registrierungs Struktur oder einen Zertifikat Speicher handeln. Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## BEISPIELE

### Beispiel 1: erhalten von untergeordneten Elementen aus einem Dateisystem Verzeichnis

In diesem Beispiel werden die untergeordneten Elemente aus einem Dateisystem Verzeichnis abgerufen. Die Namen der Dateinamen und Unterverzeichnisse werden angezeigt. Für leere Speicherorte gibt der Befehl keine Ausgabe zurück und kehrt zur PowerShell-Eingabeaufforderung zurück.

Das- `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis anzugeben `C:\Test` .
`Get-ChildItem` zeigt die Dateien und Verzeichnisse in der PowerShell-Konsole an.

```powershell
Get-ChildItem -Path C:\Test
```

```Output
   Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     08:29                Logs
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

In der Standardeinstellung werden `Get-ChildItem` der Modus ( **Attribute** ), **lastschreitezeit** , Dateigröße ( **Länge** ) und der **Name** des Elements aufgelistet. Die Buchstaben in der **Mode** -Eigenschaft können wie folgt interpretiert werden:

- `l` Verknüpfen
- `d` befinden
- `a` archiviert
- `r` (schreibgeschützt)
- `h` verbirgt
- `s` (System).

Weitere Informationen zu den modusflags finden Sie unter [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).

### Beispiel 2: erhalten von untergeordneten Elementnamen in einem Verzeichnis

In diesem Beispiel werden nur die Namen der Elemente in einem Verzeichnis aufgelistet.

Das- `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis anzugeben `C:\Test` . Der **Name** -Parameter gibt nur die Datei-oder Verzeichnisnamen aus dem angegebenen Pfad zurück.

```powershell
Get-ChildItem -Path C:\Test -Name
```

```Output
Logs
anotherfile.txt
Command.txt
CreateTestFile.ps1
ReadOnlyFile.txt
```

### Beispiel 3: erhalten von untergeordneten Elementen im aktuellen Verzeichnis und in den Unterverzeichnissen

In diesem Beispiel werden **txt** -Dateien angezeigt, die sich im aktuellen Verzeichnis und seinen Unterverzeichnissen befinden.

```powershell
Get-ChildItem -Path C:\Test\*.txt -Recurse -Force
```

```Output
    Directory: C:\Test\Logs\Adirectory

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile4.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile4.txt

    Directory: C:\Test\Logs\Backup

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 ATextFile.txt
-a----        2/12/2019     15:50             20 LogFile3.txt

    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

Das- `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um anzugeben `C:\Test\*.txt` . **Path** verwendet das Sternchen-Platzhalter Zeichen ( `*` ), um alle Dateien mit der Dateinamenerweiterung anzugeben `.txt` . Der **recurse** -Parameter durchsucht das **Pfad** Verzeichnis seiner Unterverzeichnisse, wie in den Überschriften " **Verzeichnis:** " angezeigt. Der **Force** -Parameter zeigt ausgeblendete Dateien an `hiddenfile.txt` , z. b. mit dem Modus **h** .

### Beispiel 4: Aufrufen von untergeordneten Elementen mit dem Include-Parameter

In diesem Beispiel `Get-ChildItem` wird der **include** -Parameter verwendet, um bestimmte Elemente aus dem Verzeichnis zu suchen, das durch den **path** -Parameter angegeben wird.

```powershell
# When using the -Include parameter, if you don't include an asterisk in the path
# the command returns no output.
Get-ChildItem -Path C:\Test\ -Include *.txt
```

```Output

```

```powershell
Get-ChildItem -Path C:\Test\* -Include *.txt
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis " **c:\test** " anzugeben. Der **path** -Parameter enthält einen nachfolgenden Sternchen ( `*` )-Platzhalter, um den Inhalt des Verzeichnisses anzugeben.
Der **include** -Parameter verwendet ein Sternchen-Platzhalter Zeichen ( `*` ), um alle Dateien mit der Dateinamenerweiterung **. txt** anzugeben.

Wenn der **include** -Parameter verwendet wird, benötigt der **path** -Parameter einen nachfolgenden Sternchen ( `*` )-Platzhalter, um den Inhalt des Verzeichnisses anzugeben. Beispiel: `-Path C:\Test\*`.

- Wenn der **recurse** -Parameter dem Befehl hinzugefügt wird, ist das nachfolgende Sternchen ( `*` ) im **path** -Parameter optional. Der **recurse** -Parameter ruft Elemente aus dem **Pfad** Verzeichnis und seinen Unterverzeichnissen ab. Zum Beispiel, `-Path C:\Test\ -Recurse -Include *.txt`
- Wenn ein nach gestelltes Sternchen ( `*` ) nicht im **path** -Parameter enthalten ist, gibt der Befehl keine Ausgabe zurück und kehrt zur PowerShell-Eingabeaufforderung zurück. Beispiel: `-Path C:\Test\`.

### Beispiel 5: Aufrufen von untergeordneten Elementen mit dem Exclude-Parameter

Die Ausgabe des Beispiels zeigt den Inhalt des Verzeichnisses " **c:\test\logs** ". Bei der Ausgabe handelt es sich um einen Verweis auf die anderen Befehle, die die **Exclude** -und **recurse** -Parameter verwenden.

```powershell
Get-ChildItem -Path C:\Test\Logs
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Adirectory
d-----        2/15/2019     08:28                AnEmptyDirectory
d-----        2/15/2019     13:21                Backup
-a----        2/12/2019     16:16             20 Afile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

```powershell
Get-ChildItem -Path C:\Test\Logs\* -Exclude A*
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Backup
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

Das- `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis anzugeben `C:\Test\Logs` .
Der **Exclude** -Parameter verwendet das Sternchen-Platzhalter Zeichen ( `*` ), um alle Dateien oder Verzeichnisse anzugeben, die mit **einem** oder **einem** beginnen, der aus der Ausgabe ausgeschlossen ist.

Wenn der **Exclude** -Parameter verwendet wird, ist das nachfolgende Sternchen ( `*` ) im **path** -Parameter optional. Zum Beispiel: `-Path C:\Test\Logs` oder `-Path C:\Test\Logs\*`.

- Wenn ein nach gestelltes Sternchen ( `*` ) nicht im **path** -Parameter enthalten ist, wird der Inhalt des **path** -Parameters angezeigt. Ausnahmen sind Dateinamen oder Unterverzeichnis Namen, die dem Wert des **Exclude** -Parameters entsprechen.
- Wenn ein nach gestelltes Sternchen ( `*` ) im **path** -Parameter enthalten ist, wird der Befehl in die Unterverzeichnisse des **path** -Parameters rekurdieren. Ausnahmen sind Dateinamen oder Unterverzeichnis Namen, die dem Wert des **Exclude** -Parameters entsprechen.
- Wenn der **recurse** -Parameter dem Befehl hinzugefügt wird, ist die Rekursions Ausgabe gleich, unabhängig davon, ob der **path** -Parameter ein nach gestelltes Sternchen ( `*` ) enthält.

### Beispiel 6: erhalten der Registrierungsschlüssel aus einer Registrierungs Struktur

In diesem Beispiel werden alle Registrierungsschlüssel aus abgerufen `HKEY_LOCAL_MACHINE\HARDWARE` .

`Get-ChildItem` verwendet den **path** -Parameter, um den Registrierungsschlüssel anzugeben `HKLM:\HARDWARE` . Der Hive-Pfad und die oberste Ebene der Registrierungsschlüssel werden in der PowerShell-Konsole angezeigt.

Weitere Informationen finden Sie unter [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).

```powershell
Get-ChildItem -Path HKLM:\HARDWARE
```

```Output
    Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name             Property
----             --------
ACPI
DESCRIPTION
DEVICEMAP
RESOURCEMAP
UEFI
```

```powershell
Get-ChildItem -Path HKLM:\HARDWARE -Exclude D*
```

```Output
   Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name                           Property
----                           --------
ACPI
RESOURCEMAP
```

Der erste Befehl zeigt den Inhalt des `HKLM:\HARDWARE` Registrierungsschlüssels an. Der **Exclude** -Parameter weist `Get-ChildItem` an, keine Unterschlüssel zurückzugeben, die mit beginnen `D*` . Derzeit funktioniert der **Exclude** -Parameter nur für Unterschlüssel, nicht für Element Eigenschaften.

### Beispiel 7: alle Zertifikate mit Code Signatur Stelle erhalten

In diesem Beispiel werden alle Zertifikate im PowerShell-Zertifikat " **CERT:** " abgerufen, das über Code Signatur Autorität verfügt.

Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um den **CERT:** -Anbieter anzugeben. Der **recurse** -Parameter durchsucht das Verzeichnis, das von **path** und seinen Unterverzeichnissen angegeben wird. Mit dem **codeSigningCert** -Parameter werden nur Zertifikate abgerufen, die über eine Code Signatur Berechtigung verfügen.

```powershell
Get-ChildItem -Path Cert:\* -Recurse -CodeSigningCert
```

Weitere Informationen zum Zertifikat Anbieter und zum CERT:-Laufwerk finden Sie unter [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).

### Beispiel 8: Get Items using the Tiefe Parameter

In diesem Beispiel werden die Elemente in einem Verzeichnis und seinen Unterverzeichnissen angezeigt. Der **tiefen** Parameter bestimmt die Anzahl der Unterverzeichnis Ebenen, die in die Rekursion eingeschlossen werden sollen. Leere Verzeichnisse werden aus der Ausgabe ausgeschlossen.

```powershell
Get-ChildItem -Path C:\Parent -Depth 2
```

```Output
    Directory: C:\Parent

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level1
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level2
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1\SubDir_Level2

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:22                SubDir_Level3
-a----        2/13/2019     08:55             26 file.txt
```

Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um **c:\parent** anzugeben. Der **tiefen** Parameter gibt zwei Rekursions Ebenen an. `Get-ChildItem` zeigt den Inhalt des Verzeichnisses an, das durch den **path** -Parameter und die beiden Ebenen der Unterverzeichnisse angegeben wird.

## Parameter

### -Attribute

Ruft Dateien und Ordner mit den angegebenen Attributen ab. Dieser Parameter unterstützt alle Attribute und Sie können komplexe Kombinationen von Attributen angeben.

Geben Sie z. B. Folgendes ein, um Nicht-Systemdateien (keine Verzeichnisse) zu erhalten, die verschlüsselt oder komprimiert sind:

`Get-ChildItem -Attributes !Directory+!System+Encrypted, !Directory+!System+Compressed`

Um Dateien und Ordner mit häufig verwendeten Attributen zu suchen, verwenden Sie den **Attribute** -Parameter. Oder, das Parameter **Verzeichnis** , **Datei** , **ausgeblendet** , **schreibgeschützt und** **System** .

Der **Attribute** -Parameter unterstützt die folgenden Eigenschaften:

- **Archivieren**
- **Compressed**
- **Device**
- **Verzeichnis**
- **Verschlüsselt**
- **Hidden**
- **Integritystream**
- **Normal**
- **Noscrubdata**
- **Notcontentindiziert**
- **Aufzu**
- **ReadOnly**
- **Analyse Punkt**
- **Sparpfad**
- **System**
- **Temporär**

Eine Beschreibung dieser Attribute finden Sie in der [FileAttribute-Enumeration](/dotnet/api/system.io.fileattributes).

Verwenden Sie die folgenden Operatoren, um Attribute zu kombinieren:

- `!` Hätten
- `+` Immer
- `,` Noch

Verwenden Sie keine Leerzeichen zwischen einem Operator und dessen Attribut. Leerzeichen werden nach Kommas akzeptiert.

Verwenden Sie für allgemeine Attribute die folgenden Abkürzungen:

- `D` Befinden
- `H` Verbirgt
- `R` (Schreibgeschützt)
- `S` Anlage

```yaml
Type: System.Management.Automation.FlagsExpression`1[System.IO.FileAttributes]
Parameter Sets: (All)
Aliases:
Accepted values: Archive, Compressed, Device, Directory, Encrypted, Hidden, IntegrityStream, Normal, NoScrubData, NotContentIndexed, Offline, ReadOnly, ReparsePoint, SparseFile, System, Temporary

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tiefe

Dieser Parameter wurde in PowerShell 5,0 hinzugefügt und ermöglicht es Ihnen, die Tiefe der Rekursion zu steuern. In der Standardeinstellung wird `Get-ChildItem` der Inhalt des übergeordneten Verzeichnisses angezeigt. Der **tiefen** Parameter bestimmt die Anzahl der Unterverzeichnis Ebenen, die in der Rekursion enthalten sind, und zeigt die Inhalte an.

Beispielsweise `Depth 2` enthält das Verzeichnis des **path** -Parameters, die erste Ebene der Unterverzeichnisse und die zweite Ebene der Unterverzeichnisse. Standardmäßig sind Verzeichnisnamen und Dateinamen in der Ausgabe enthalten.

> [!NOTE]
> Auf einem Windows-Computer aus PowerShell oder **cmd.exe** können Sie eine grafische Ansicht einer Verzeichnisstruktur mit dem **Tree.com** -Befehl anzeigen.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Directory

Zum Aufrufen einer Liste von Verzeichnissen verwenden Sie den **Directory** -Parameter oder **den Parameters** -Parameter mit der **Directory** -Eigenschaft. Sie können den **recurse** -Parameter mit **Directory** verwenden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ad, d

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ausschließen

Gibt als Zeichen folgen Array eine Eigenschaft oder eine Eigenschaft an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen wird.
Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` `A*` . b. oder. Platzhalterzeichen werden akzeptiert.

Ein nach gestelltes Sternchen ( `*` ) im **path** -Parameter ist optional. Zum Beispiel: `-Path C:\Test\Logs` oder `-Path C:\Test\Logs\*`. Wenn ein nach gestelltes Sternchen ( `*` ) eingeschlossen ist, wird der Befehl in die Unterverzeichnisse des **path** -Parameters rekurdieren. Ohne das Sternchen ( `*` ) wird der Inhalt des **path** -Parameters angezeigt. Weitere Informationen finden Sie in Beispiel 5 und im Abschnitt "Hinweise".

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

### -File

Verwenden Sie den **File** -Parameter, um eine Liste mit Dateien zu erhalten. Sie können den **recurse** -Parameter mit **File** verwenden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: af

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter

Gibt einen Filter zum Qualifizieren des **path** -Parameters an. Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der Filter unterstützt. Filter sind effizienter als andere Parameter. Der Anbieter wendet den Filter an, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert. Die Filter Zeichenfolge wird an die .NET-API zum Aufzählen von Dateien übermittelt. Die API unterstützt nur `*` -und-Platzhalter `?` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

Ermöglicht es dem Cmdlet, Elemente zu erhalten, auf die der Benutzer anderweitig nicht zugreifen kann, z. b. ausgeblendete Dateien oder Systemdateien. Der **Force** -Parameter überschreibt keine Sicherheitseinschränkungen. Die Implementierung unterscheidet sich bei den einzelnen Anbietern. Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

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

### -Hidden

Um nur ausgeblendete Elemente zu erhalten, verwenden Sie den **Hidden** -Parameter oder den **Attribute** -Parameter mit der **Hidden** -Eigenschaft. Standardmäßig zeigt keine ausgeblendeten `Get-ChildItem` Elemente an. Verwenden Sie den **Force** -Parameter, um verborgene Elemente zu erhalten.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ah, h

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Include

Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt. Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b.. Platzhalterzeichen sind zulässig. Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.

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
Parameter Sets: LiteralItems
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Ruft nur die Namen der Elemente am Speicherort ab. Bei der Ausgabe handelt es sich um ein Zeichen folgen Objekt, das über die Pipeline an andere Befehle gesendet werden kann. Platzhalter sind zulässig.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Path

Gibt einen Pfad zu einem oder mehreren Speicherorten an. Platzhalter werden akzeptiert. Der Standard Speicherort ist das aktuelle Verzeichnis ( `.` ).

```yaml
Type: System.String[]
Parameter Sets: Items
Aliases:

Required: False
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -ReadOnly

Um nur schreibgeschützte Elemente zu erhalten, verwenden Sie den Parameter "read **only** " oder **die Eigenschaft "** **Attributparameter** schreibgeschützt".

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ar

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Recurse

Ruft die Elemente an den angegebenen Speicherorten und alle untergeordneten Elemente der Speicherorte ab.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: s

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -System

Ruft nur Systemdateien und Verzeichnisse ab. Um nur Systemdateien und Ordner zu erhalten, verwenden **System** Sie die System Eigenschaft System **Parameter oder** **Attribute** des Parameters.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: as

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine Zeichenfolge über die Pipeline übergeben, die einen Pfad zu enthält `Get-ChildItem` .

## AUSGABEN

### System.Object

Der Typ des zurückgegebenen Objekts `Get-ChildItem` wird von den Objekten im Pfad des Anbieter Laufwerks bestimmt.

### System.String

Wenn Sie den **Name** -Parameter verwenden, werden `Get-ChildItem` die Objektnamen als Zeichen folgen zurückgegeben.

## HINWEISE

- `Get-ChildItem` kann mithilfe einer der integrierten Aliase, `ls` , und ausgeführt werden `dir` `gci` . Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- `Get-ChildItem` Standardmäßig werden keine ausgeblendeten Elemente erhalten. Wenn Sie ausgeblendete Elemente abrufen möchten, verwenden Sie den **Force** -Parameter.
- Das- `Get-ChildItem` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .
  Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Get-Alias](../Microsoft.PowerShell.Utility/Get-Alias.md)

[Get-Item](Get-Item.md)

[Get-Location](Get-Location.md)

[Get-Process](Get-Process.md)

[Get-PSProvider](Get-PSProvider.md)

[Split-Path](Split-Path.md)
