---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 8e1557bca62ade784bd5b4ed5cb170bbf079b423
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "93219676"
---
# Export-Clixml

## ZUSAMMENFASSUNG
Erstellt eine XML-basierte Darstellung eines Objekts oder von Objekten und speichert sie in einer Datei.

## SYNTAX

### Bypath (Standard)

```
Export-Clixml [-Depth <Int32>] [-Path] <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Byliteralpath

```
Export-Clixml [-Depth <Int32>] -LiteralPath <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Export-Clixml` Cmdlet erstellt eine XML-basierte Darstellung eines Common Language Infrastructure (CLI) eines Objekts oder von Objekten und speichert Sie in einer Datei. Sie können dann das- `Import-Clixml` Cmdlet verwenden, um das gespeicherte Objekt basierend auf dem Inhalt dieser Datei neu zu erstellen.
Weitere Informationen zur CLI finden Sie unter [Sprachunabhängigkeit](/dotnet/standard/language-independence).

Dieses Cmdlet ähnelt `ConvertTo-Xml` , mit der Ausnahme, dass `Export-Clixml` das resultierende XML in einer Datei speichert. `ConvertTo-XML` Gibt den XML-Code zurück, sodass Sie ihn in PowerShell weiterhin verarbeiten können.

Eine wertvolle Verwendung von `Export-Clixml` auf Windows-Computern besteht darin, Anmelde Informationen zu exportieren und Zeichen folgen sicher als XML zu schützen. Ein Beispiel finden Sie unter Beispiel 3.

## BEISPIELE

### Beispiel 1: Exportieren einer Zeichenfolge in eine XML-Datei

In diesem Beispiel wird eine XML-Datei erstellt, die im aktuellen Verzeichnis speichert, eine Darstellung der Zeichenfolge, bei der **es sich um einen Test handelt**.

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

Die Zeichenfolge `This is a test` wird an die Pipeline gesendet. `Export-Clixml` verwendet den **path** -Parameter, um eine XML-Datei `sample.xml` mit dem Namen im aktuellen Verzeichnis zu erstellen.

### Beispiel 2: Exportieren eines Objekts in eine XML-Datei

In diesem Beispiel wird veranschaulicht, wie Sie ein Objekt in eine XML-Datei exportieren können und wie Sie dann ein Objekt erstellen können, indem Sie den XML-Code aus der Datei importieren.

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

Mit dem- `Get-Acl` Cmdlet wird die Sicherheits Beschreibung der `Test.txt` Datei abgerufen. Er sendet das Objekt an die Pipeline, um die Sicherheits Beschreibung an zu übergeben `Export-Clixml` . Die XML-basierte Darstellung des-Objekts wird in einer Datei mit dem Namen gespeichert `FileACL.xml` .

Das- `Import-Clixml` Cmdlet erstellt ein Objekt aus dem XML-Code in der `FileACL.xml` Datei. Anschließend wird das Objekt in der Variablen gespeichert `$fileacl` .

### Beispiel 3: Verschlüsseln eines exportierten Anmelde Informationsobjekts unter Windows

In diesem Beispiel können Sie mit den Anmelde Informationen, die Sie `$Credential` durch Ausführen des Cmdlets in der Variablen gespeichert haben `Get-Credential` , das `Export-Clixml` Cmdlet ausführen, um die Anmelde Informationen auf dem Datenträger zu speichern.

> [!IMPORTANT]
> `Export-Clixml` exportiert nur verschlüsselte Anmelde Informationen unter Windows. Bei nicht-Windows-Betriebssystemen wie macOS und Linux werden Anmelde Informationen als nur-Text exportiert, der als Unicode-Zeichen Array gespeichert wird. Dies bietet eine gewisse Verschleierung, bietet aber keine Verschlüsselung.

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

Mit dem- `Export-Clixml` Cmdlet werden Anmelde Informationsobjekte mithilfe der Windows- [Datenschutz-API](/previous-versions/windows/apps/hh464970(v=win.10))verschlüsselt. Durch die Verschlüsselung wird sichergestellt, dass nur Ihr Benutzerkonto nur auf diesem Computer den Inhalt des Anmelde Informationsobjekts entschlüsseln kann.
Die exportierte `CLIXML` Datei kann nicht auf einem anderen Computer oder von einem anderen Benutzer verwendet werden.

Im Beispiel wird die Datei, in der die Anmelde Informationen gespeichert werden, durch dargestellt `TestScript.ps1.credential` . Ersetzen Sie **testScript** durch den Namen des Skripts, mit dem die Anmelde Informationen geladen werden.

Sie senden das Anmelde Informationen-Objekt über die Pipeline an `Export-Clixml` und speichern es in dem Pfad, `$Credxmlpath` , den Sie im ersten Befehl angegeben haben.

Führen Sie die letzten beiden Befehle aus, um die Anmelde Informationen automatisch in das Skript zu importieren. Führen `Import-Clixml` Sie aus, um das gesicherte Anmelde Informationsobjekt in das Skript zu importieren. Dieser Import vermeidet das Risiko, dass nur-Text-Kenn Wörter in Ihrem Skript verfügbar gemacht werden.

### Beispiel 4: Exportieren eines Anmelde Informationsobjekts unter Linux oder macOS

In diesem Beispiel erstellen wir mithilfe des Cmdlets eine " **PSCredential** " in der `$Credential` Variablen `Get-Credential` . Dann verwenden wir `Export-Clixml` , um die Anmelde Informationen auf dem Datenträger zu speichern.

> [!IMPORTANT]
> `Export-Clixml` exportiert nur verschlüsselte Anmelde Informationen unter Windows. Bei nicht-Windows-Betriebssystemen wie macOS und Linux werden Anmelde Informationen als nur-Text exportiert, der als Unicode-Zeichen Array gespeichert wird. Dies bietet eine gewisse Verschleierung, bietet aber keine Verschlüsselung.

```powershell
PS> $Credential = Get-Credential

PowerShell credential request
Enter your credentials.
User: User1
Password for user User1: ********

PS> $Credential | Export-Clixml ./cred2.xml
PS> Get-Content ./cred2.xml

...
    <Props>
      <S N="UserName">User1</S>
      <SS N="Password">700061007300730077006f0072006400</SS>
    </Props>
...

PS> 'password' | Format-Hex -Encoding unicode

   Label: String (System.String) <52D60C91>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 70 00 61 00 73 00 73 00 77 00 6F 00 72 00 64 00 p a s s w o r d
```

Die Ausgabe von `Get-Content` in diesem Beispiel wurde abgeschnitten, um sich auf die Anmelde Informationen in der XML-Datei zu konzentrieren. Beachten Sie, dass der nur-Text-Wert des Kennworts in der XML-Datei als Unicode-Zeichen Array gespeichert wird, wie von nachgewiesen `Format-Hex` . Daher ist der Wert codiert, jedoch nicht verschlüsselt.

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

### -Tiefe

Gibt an, wie viele Ebenen der enthaltenen Objekte in der XML-Darstellung enthalten sind. Der Standardwert ist `2`.

Der Standardwert kann für den Objekttyp in den Dateien überschrieben werden `Types.ps1xml` . Weitere Informationen finden Sie unter [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### -Codierung

Gibt den Typ der Codierung für die Zieldatei an. Der Standardwert ist `utf8NoBOM`.

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
> **UTF-7** * wird nicht mehr zur Verwendung von empfohlen. In PowerShell 7,1 wird eine Warnung geschrieben, wenn Sie `utf7` für den **Encoding** -Parameter angeben.

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

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.

Bewirkt, dass das Cmdlet das Schreibschutzattribut der Ausgabedatei bei Bedarf deaktiviert. Das Cmdlet versucht, das Schreibschutzattribut zurückzusetzen, wenn der Befehl abgeschlossen ist.

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

### -InputObject

Gibt das zu konvertierende Objekt an. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden. Sie können Objekte auch über die Pipeline an übergeben `Export-Clixml` .

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Literalpath

Gibt den Pfad zur Datei an, wo die XML-Darstellung des Objekts gespeichert wird. Im Gegensatz zu **path** wird der Wert des **literalpath** -Parameters genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoClobber

Gibt an, dass das Cmdlet den Inhalt einer vorhandenen Datei nicht überschreibt. Wenn eine Datei im angegebenen Pfad vorhanden ist, wird `Export-Clixml` die Datei standardmäßig ohne Warnung überschrieben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt den Pfad zur Datei an, wo die XML-Darstellung des Objekts gespeichert wird.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
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

### System. Management. Automation. psobject

Sie können ein beliebiges Objekt an die Pipeline angleichen `Export-Clixml` .

## AUSGABEN

### System. IO. fileingefo

`Export-Clixml` erstellt eine Datei, die den XML-Code enthält.

## HINWEISE

## VERWANDTE LINKS

[ConvertTo-Html](ConvertTo-Html.md)

[ConvertTo-Xml](ConvertTo-Xml.md)

[Export-Csv](Export-Csv.md)

[Import-Clixml](Import-Clixml.md)

[Join-Path](../Microsoft.PowerShell.Management/Join-Path.md)

[Anmelde Informationen auf dem Datenträger sicher speichern](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[Verwenden von PowerShell zum Übergeben von Anmelde Informationen an Legacy Systeme](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)

[Windows.Security.Cryptography.DataProtection](/uwp/api/windows.security.cryptography.dataprotection)
