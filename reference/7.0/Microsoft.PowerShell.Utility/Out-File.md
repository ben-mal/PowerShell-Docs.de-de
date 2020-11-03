---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-file?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-File
ms.openlocfilehash: e7437505bbe5fbbcfb38e9957f75ac45287d9b26
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "93220039"
---
# Out-File

## ZUSAMMENFASSUNG
Sendet die Ausgabe an eine Datei.

## SYNTAX

### Bypath (Standard)

```
Out-File [-FilePath] <string> [[-Encoding] <Encoding>] [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Byliteralpath

```
Out-File [[-Encoding] <Encoding>] -LiteralPath <string> [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Out-File` Cmdlet sendet die Ausgabe an eine Datei. Er verwendet implizit das-Formatierungs System von PowerShell, um in die Datei zu schreiben. Die Datei erhält dieselbe Anzeige Darstellung wie das Terminal. Dies bedeutet, dass die Ausgabe möglicherweise für die programmgesteuerte Verarbeitung nicht ideal ist, wenn nicht alle Eingabe Objekte Zeichen folgen sind.
Wenn Sie Parameter für die Ausgabe angeben müssen, verwenden Sie `Out-File` anstelle des Umleitungs Operators ( `>` ). Weitere Informationen zur Umleitung finden Sie unter [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).

## BEISPIELE

### Beispiel 1: Senden der Ausgabe und Erstellen einer Datei

In diesem Beispiel wird gezeigt, wie eine Liste der Prozesse des lokalen Computers an eine Datei gesendet wird. Wenn die Datei nicht vorhanden ist, `Out-File` erstellt die Datei im angegebenen Pfad.

```powershell
Get-Process | Out-File -FilePath .\Process.txt
Get-Content -Path .\Process.txt
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     29    22.39      35.40      10.98   42764   9 Application
     53    99.04     113.96       0.00   32664   0 CcmExec
     27    96.62     112.43     113.00   17720   9 Code
```

Mit dem- `Get-Process` Cmdlet wird die Liste der Prozesse abgerufen, die auf dem lokalen Computer ausgeführt werden. Die **Prozess** Objekte werden über die Pipeline an das `Out-File` Cmdlet gesendet. `Out-File` verwendet den **FilePath** -Parameter und erstellt eine Datei im aktuellen Verzeichnis mit dem Namen **Process.txt**. Der `Get-Content` Befehl ruft Inhalt aus der Datei ab und zeigt ihn in der PowerShell-Konsole an.

### Beispiel 2: verhindern, dass eine vorhandene Datei überschrieben wird

In diesem Beispiel wird verhindert, dass eine vorhandene Datei überschrieben wird. Standardmäßig `Out-File` überschreibt vorhandene Dateien.

```powershell
Get-Process | Out-File -FilePath .\Process.txt -NoClobber
```

```Output
Out-File : The file 'C:\Test\Process.txt' already exists.
At line:1 char:15
+ Get-Process | Out-File -FilePath .\Process.txt -NoClobber
+               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

Mit dem- `Get-Process` Cmdlet wird die Liste der Prozesse abgerufen, die auf dem lokalen Computer ausgeführt werden. Die **Prozess** Objekte werden über die Pipeline an das `Out-File` Cmdlet gesendet. `Out-File` verwendet den **FilePath** -Parameter und versucht, in eine Datei im aktuellen Verzeichnis namens **Process.txt** zu schreiben. Der **noClobber** -Parameter verhindert, dass die Datei überschrieben wird, und zeigt eine Meldung an, dass die Datei bereits vorhanden ist.

### Beispiel 3: Senden der Ausgabe an eine Datei im ASCII-Format

Dieses Beispiel zeigt, wie Sie die Ausgabe mit einem bestimmten Codierungstyp codieren.

```powershell
$Procs = Get-Process
Out-File -FilePath .\Process.txt -InputObject $Procs -Encoding ASCII -Width 50
```

Mit dem- `Get-Process` Cmdlet wird die Liste der Prozesse abgerufen, die auf dem lokalen Computer ausgeführt werden. Die **Prozess** Objekte werden in der Variablen gespeichert `$Procs` . `Out-File` verwendet den **FilePath** -Parameter und erstellt eine Datei im aktuellen Verzeichnis mit dem Namen **Process.txt**. Der **Inputobject** -Parameter übergibt die Prozess Objekte an `$Procs` die Datei **Process.txt**. Mit dem **Encoding** -Parameter wird die Ausgabe in das **ASCII** -Format konvertiert. Der **Width** -Parameter schränkt jede Zeile in der Datei auf 50 Zeichen ein, sodass einige Daten abgeschnitten werden können.

### Beispiel 4: Verwenden eines Anbieters und Senden der Ausgabe an eine Datei

In diesem Beispiel wird gezeigt, wie das `Out-File` Cmdlet verwendet wird, wenn Sie sich nicht in einem **File System** -Anbieter Laufwerk befinden. Verwenden `Get-PSProvider` Sie das Cmdlet, um die Anbieter auf dem lokalen Computer anzuzeigen. Weitere Informationen finden Sie unter [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).

```
PS> Set-Location -Path Alias:

PS> Get-Location

Path
----
Alias:\

PS> Get-ChildItem | Out-File -FilePath C:\TestDir\AliasNames.txt

PS> Get-Content -Path C:\TestDir\AliasNames.txt

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           cat -> Get-Content
```

Der `Set-Location` Befehl verwendet den **path** -Parameter, um den aktuellen Speicherort auf den Registrierungs Anbieter festzulegen `Alias:` . Das- `Get-Location` Cmdlet zeigt den gesamten Pfad für an `Alias:` .
`Get-ChildItem` sendet Objekte über die Pipeline an das `Out-File` Cmdlet. `Out-File` verwendet den **FilePath** -Parameter, um den gesamten Pfad und den Dateinamen für die Ausgabe anzugeben, **C:\TestDir\AliasNames.txt**. Das `Get-Content` Cmdlet verwendet den **path** -Parameter und zeigt den Inhalt der Datei in der PowerShell-Konsole an.

## PARAMETERS

### -Anfügen

Fügt die Ausgabe am Ende einer vorhandenen Datei hinzu.

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

### -Codierung

Gibt den Typ der Codierung für die Zieldatei an. Der Standardwert ist `utf8NoBOM`.

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
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: 1
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Gibt den Pfad zur Ausgabedatei an.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Überschreibt das schreibgeschützte Attribut und überschreibt eine vorhandene schreibgeschützte Datei. Der **Force** -Parameter überschreibt keine Sicherheitseinschränkungen.

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

### -InputObject

Gibt die in die Datei zu schreibenden Objekte an. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Literalpath

Gibt den Pfad zur Ausgabedatei an. Der **literalpath** -Parameter wird genau so verwendet, wie er eingegeben wurde.
Platzhalter Zeichen werden nicht akzeptiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren. Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoClobber

**NoClobber** verhindert, dass eine vorhandene Datei überschrieben wird, und zeigt eine Meldung an, dass die Datei bereits vorhanden ist. Wenn eine Datei im angegebenen Pfad vorhanden ist, wird `Out-File` die Datei standardmäßig ohne Warnung überschrieben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nonewline

Gibt an, dass der Inhalt, der in die Datei geschrieben wird, nicht mit einem Zeilen Umleitungs Zeichen endet. Die Zeichen folgen Darstellungen der Eingabe Objekte werden verkettet, um die Ausgabe zu bilden. Zwischen den Ausgabe Zeichenfolgen werden keine Leerzeichen oder Zeilenumbrüche eingefügt. Nach der letzten Ausgabe Zeichenfolge wird kein Zeilen Vorstrich hinzugefügt.

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

### -Breite

Gibt die Anzahl der Zeichen in jeder Zeile der Ausgabe an. Alle zusätzlichen Zeichen werden abgeschnitten und nicht umgebrochen. Wenn dieser Parameter nicht verwendet wird, wird die Breite durch die Merkmale des Hosts bestimmt. Der Standardwert für die PowerShell-Konsole ist 80 Zeichen.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### System. Management. Automation. psobject

Sie können jedes beliebige Objekt an die Pipeline übergeben `Out-File` .

## AUSGABEN

### Keine

`Out-File` generiert keine Ausgabe.

## HINWEISE

Eingabe Objekte werden automatisch wie im Terminal formatiert, Sie können jedoch ein `Format-*` Cmdlet verwenden, um die Formatierung der Ausgabe in der Datei explizit zu steuern. Zum Beispiel, `Get-Date | Format-List | Out-File out.txt`

Verwenden Sie die Pipeline, um die Ausgabe eines PowerShell-Befehls an das `Out-File` Cmdlet zu senden. Alternativ können Sie Daten in einer Variablen speichern und den **Inputobject** -Parameter verwenden, um Daten an das `Out-File` Cmdlet zu übergeben.

`Out-File` speichert Daten in einer Datei, erzeugt aber keine Ausgabe Objekte in der Pipeline.

## VERWANDTE LINKS

[about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md)

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[Out-Default](../Microsoft.PowerShell.Core/Out-Default.md)

[Out-Host](../Microsoft.PowerShell.Core/Out-Host.md)

[Out-Null](../Microsoft.PowerShell.Core/Out-Null.md)

[Out-String](Out-String.md)

[Tee-Object](Tee-Object.md)
