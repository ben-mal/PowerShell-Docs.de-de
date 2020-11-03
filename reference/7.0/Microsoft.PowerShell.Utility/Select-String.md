---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-string?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-String
ms.openlocfilehash: 7c614314eb13ea484f5a0a5ade36aabdd6afdf58
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "93219636"
---
# Select-String

## ZUSAMMENFASSUNG
Sucht nach Text in Dateien und Zeichenfolgen.

## SYNTAX

### File (Standard)

```
Select-String [-Culture <String>] [-Pattern] <String[]> [-Path] <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### Objectraw

```
Select-String [-Culture <String>] -InputObject <PSObject> [-Pattern] <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### Object

```
Select-String [-Culture <String>] -InputObject <PSObject> [-Pattern] <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### Filteraw

```
Select-String [-Culture <String>] [-Pattern] <String[]> [-Path] <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### Literalfileraw

```
Select-String [-Culture <String>] [-Pattern] <String[]> -LiteralPath <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### Literalfile

```
Select-String [-Culture <String>] [-Pattern] <String[]> -LiteralPath <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

## DESCRIPTION

Das `Select-String` Cmdlet sucht Text-und Textmuster in Eingabe Zeichenfolgen und Dateien. Sie können `Select-String` ähnlich wie **grep** in UNIX oder **findstr.exe** in Windows verwenden.

`Select-String` basiert auf Textzeilen. Standardmäßig `Select-String` sucht die erste Übereinstimmung in jeder Zeile und zeigt für jede Übereinstimmung den Dateinamen, die Zeilennummer und den gesamten Text in der Zeile an, die die Übereinstimmung enthält. Sie können angeben, `Select-String` ob mehrere Übereinstimmungen pro Zeile gefunden werden, wie Text vor und nach der Übereinstimmung angezeigt werden soll oder ob ein boolescher Wert (true oder false) angezeigt werden soll, der angibt, ob eine Übereinstimmung gefunden wird.

`Select-String` verwendet reguläre Ausdrucks Vergleiche, aber es kann auch eine Übereinstimmung durchsucht werden, die die Eingabe nach dem angegebenen Text durchsucht.

`Select-String` kann alle Text Übereinstimmungen anzeigen oder nach der ersten Übereinstimmung in jeder Eingabedatei angehalten werden.
`Select-String` kann verwendet werden, um den gesamten Text anzuzeigen, der nicht dem angegebenen Muster entspricht.

Sie können auch angeben, dass `Select-String` eine bestimmte Zeichencodierung erwarten soll, z. b. beim Durchsuchen von Dateien mit Unicode-Text. `Select-String` verwendet die Byte Reihenfolge-Markierung (BOM), um das Codierungsformat der Datei zu erkennen. Wenn die Datei keine BOM enthält, wird davon ausgegangen, dass die Codierung UTF8 ist.

## BEISPIELE

### Beispiel 1: Suchen nach der Groß-/Kleinschreibung

In diesem Beispiel wird die Groß-/Kleinschreibung beachtet, die in der Pipeline an das `Select-String` Cmdlet gesendet wurde.

```powershell
'Hello', 'HELLO' | Select-String -Pattern 'HELLO' -CaseSensitive -SimpleMatch
```

Die Text Zeichenfolgen **Hello** und **Hello** werden über die Pipeline an das `Select-String` Cmdlet gesendet.
`Select-String` verwendet den **Pattern** -Parameter, um **Hello** anzugeben. Der **CaseSensitive** -Parameter gibt an, dass der Fall nur dem Großbuchstaben entsprechen muss. **Simplematch** ist ein optionaler Parameter, der angibt, dass die Zeichenfolge im Muster nicht als regulärer Ausdruck interpretiert wird.
`Select-String` zeigt **Hello** in der PowerShell-Konsole an.

### Beispiel 2: Suchen von Übereinstimmungen in Textdateien

Mit diesem Befehl werden alle Dateien mit der `.txt` Dateinamenerweiterung im aktuellen Verzeichnis durchsucht. Die Ausgabe zeigt die Zeilen in den Dateien an, die die angegebene Zeichenfolge enthalten.

```powershell
Get-Alias | Out-File -FilePath .\Alias.txt
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\*.txt -Pattern 'Get-'
```

```Output
Alias.txt:8:Alias            cat -> Get-Content
Alias.txt:28:Alias           dir -> Get-ChildItem
Alias.txt:43:Alias           gal -> Get-Alias
Command.txt:966:Cmdlet       Get-Acl
Command.txt:967:Cmdlet       Get-Alias
```

In diesem Beispiel `Get-Alias` werden und `Get-Command` mit dem- `Out-File` Cmdlet zum Erstellen von zwei Textdateien im aktuellen Verzeichnis, **Alias.txt** und **Command.txt** verwendet.

`Select-String` verwendet den **path** -Parameter mit dem Platzhalter Sternchen ( `*` ), um alle Dateien im aktuellen Verzeichnis mit der Dateinamenerweiterung zu durchsuchen `.txt` . Der **Pattern** -Parameter gibt den Text an, der mit **Get-** identisch ist. `Select-String` zeigt die Ausgabe in der PowerShell-Konsole an. Der Dateiname und die Zeilennummer stehen vor jeder Inhalts Zeile, die eine Übereinstimmung für den **Pattern** -Parameter enthält.

### Beispiel 3: Suchen einer Muster Übereinstimmung

In diesem Beispiel werden mehrere Dateien durchsucht, um nach Übereinstimmungen für das angegebene Muster zu suchen. Das-Muster verwendet einen regulären Ausdrucks Quantifizierer. Weitere Informationen finden Sie unter [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md).

```powershell
Select-String -Path "$PSHOME\en-US\*.txt" -Pattern '\?'
```

```Output
C:\Program Files\PowerShell\6\en-US\default.help.txt:27:    beginning at https://go.microsoft.com/fwlink/?LinkID=108518.
C:\Program Files\PowerShell\6\en-US\default.help.txt:50:    or go to: https://go.microsoft.com/fwlink/?LinkID=210614
```

Das `Select-String` Cmdlet verwendet zwei Parameter: **path** und **Pattern**. Der **path** -Parameter verwendet die-Variable `$PSHOME` , die das PowerShell-Verzeichnis angibt. Der Rest des Pfads enthält das Unterverzeichnis **en-US** und gibt jede `*.txt` Datei im Verzeichnis an. Der **Pattern** -Parameter gibt an, dass in jeder Datei ein Fragezeichen () gefunden werden soll `?` . Ein umgekehrter Schrägstrich ( `\` ) wird als Escapezeichen verwendet und ist erforderlich, da das Fragezeichen ( `?` ) ein Quantifizierer für reguläre Ausdrücke ist. `Select-String` zeigt die Ausgabe in der PowerShell-Konsole an. Der Dateiname und die Zeilennummer stehen vor jeder Inhalts Zeile, die eine Übereinstimmung für den **Pattern** -Parameter enthält.

### Beispiel 4: Verwenden von Select-String in einer Funktion

In diesem Beispiel wird eine Funktion erstellt, um in den PowerShell-Hilfedateien nach einem Muster zu suchen. In diesem Beispiel ist die Funktion nur in der PowerShell-Sitzung vorhanden. Wenn die PowerShell-Sitzung geschlossen ist, wird die Funktion gelöscht. Weitere Informationen finden Sie unter [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md).

```
PS> Function Search-Help
>> {
>> $PSHelp = "$PSHOME\en-US\*.txt"
>> Select-String -Path $PSHelp -Pattern 'About_'
>> }
PS>

PS> Search-Help

C:\Program Files\PowerShell\6\en-US\default.help.txt:67:    The titles of conceptual topics begin with "About_".
C:\Program Files\PowerShell\6\en-US\default.help.txt:70:    Get-Help About_<topic-name>
C:\Program Files\PowerShell\6\en-US\default.help.txt:93:    Get-Help About_Modules : Displays help about PowerShell modules.
C:\Program Files\PowerShell\6\en-US\default.help.txt:97:    about_Updatable_Help
```

Die-Funktion wird in der PowerShell-Befehlszeile erstellt. Der `Function` Befehl verwendet den Namen **Search-Help**. Drücken **Sie die Eingabe** Taste, um der Funktion Anweisungen hinzuzufügen. `>>`Fügen Sie in der Eingabeaufforderung jede-Anweisung hinzu, und drücken **Sie die Eingabe** Taste, wie im Beispiel gezeigt. Nachdem die schließende Klammer hinzugefügt wurde, werden Sie an eine PowerShell-Eingabeaufforderung zurückgegeben.

Die Funktion enthält zwei Befehle. Die `$PSHelp` Variable speichert den Pfad zu den PowerShell-Hilfedateien. `$PSHOME` ist das PowerShell-Installationsverzeichnis mit dem Unterverzeichnis " **en-US** ", das jede `*.txt` Datei im Verzeichnis angibt.

Der `Select-String` -Befehl in der-Funktion verwendet die **path** -und **Pattern** -Parameter. Der **path** -Parameter verwendet die- `$PSHelp` Variable, um den Pfad zu erhalten. Der **Pattern** -Parameter verwendet die Zeichenfolge **About_** als Suchkriterium.

Geben Sie ein, um die Funktion auszuführen `Search-Help` . Der Befehl der Funktion `Select-String` zeigt die Ausgabe in der PowerShell-Konsole an.

### Beispiel 5: Suchen nach einer Zeichenfolge in einem Windows-Ereignisprotokoll

Dieses Beispiel sucht nach einer Zeichenfolge in einem Windows-Ereignisprotokoll. Die-Variable `$_` stellt das aktuelle Objekt in der Pipeline dar. Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

```powershell
$Events = Get-WinEvent -LogName Application -MaxEvents 50
$Events | Select-String -InputObject {$_.message} -Pattern 'Failed'
```

Das- `Get-WinEvent` Cmdlet verwendet den **logName** -Parameter, um das Anwendungsprotokoll anzugeben. Der **maxevents** -Parameter ruft die letzten 50-Ereignisse aus dem Protokoll ab. Der Protokoll Inhalt wird in der Variablen mit dem Namen gespeichert `$Events` .

Die `$Events` Variable wird an das Cmdlet über die Pipeline gesendet `Select-String` . `Select-String` verwendet den **Inputobject** -Parameter. Die `$_` -Variable stellt das aktuelle-Objekt dar und `message` ist eine Eigenschaft des-Ereignisses. Die **Muster** Parameter Arten der Zeichenfolge ist **fehlgeschlagen** , und in wird nach Übereinstimmungen gesucht `$_.message` . `Select-String` zeigt die Ausgabe in der PowerShell-Konsole an.

### Beispiel 6: Suchen nach einer Zeichenfolge in Unterverzeichnissen

In diesem Beispiel werden ein Verzeichnis und alle Unterverzeichnisse für eine bestimmte Text Zeichenfolge durchsucht.

```powershell
Get-ChildItem -Path C:\Windows\System32\*.txt -Recurse | Select-String -Pattern 'Microsoft' -CaseSensitive
```

`Get-ChildItem` verwendet den **path** -Parameter, um **c:\Windows\System32 \* . txt** anzugeben. Der **recurse** -Parameter enthält die Unterverzeichnisse. Die Objekte werden über die Pipeline an gesendet `Select-String` .

`Select-String` verwendet den **Pattern** -Parameter und gibt die Zeichenfolge **Microsoft** an. Der **CaseSensitive** -Parameter wird verwendet, um die exakte Groß-/Kleinschreibung der Zeichenfolge abzugleichen. `Select-String` zeigt die Ausgabe in der PowerShell-Konsole an.

> [!NOTE]
> Abhängig von ihren Berechtigungen werden in der Ausgabe möglicherweise die Meldung " **Zugriff verweigert** " angezeigt.

### Beispiel 7: Suchen nach Zeichen folgen, die nicht mit einem Muster in Einklang stehen

In diesem Beispiel wird gezeigt, wie Daten Zeilen ausgeschlossen werden, die nicht mit einem Muster zu vergleichen sind.

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get', 'Set'  -NotMatch
```

Das- `Get-Command` Cmdlet sendet Objekte über die Pipeline an den `Out-File` , um die **Command.txt** Datei im aktuellen Verzeichnis zu erstellen. `Select-String` verwendet den **path** -Parameter, um die **Command.txt** Datei anzugeben. Der **Pattern** -Parameter gibt **Get** und **set** als Suchmuster an. Der **notmatch** -Parameter schließt **Get** und **set** aus den Ergebnissen aus.
`Select-String` zeigt die Ausgabe in der PowerShell-Konsole an, die " **Get** " oder " **set** " nicht enthält.

### Beispiel 8: Suchen nach Zeilen vor und nach einer Entsprechung

Dieses Beispiel zeigt, wie Sie die Zeilen vor und nach dem übereinstimmenden Muster erhalten.

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get-Computer' -Context 2, 3
```

```Output
  Command.txt:986:Cmdlet          Get-CmsMessage           6.1.0.0    Microsoft.PowerShell.Security
  Command.txt:987:Cmdlet          Get-Command              6.1.2.0    Microsoft.PowerShell.Core
> Command.txt:988:Cmdlet          Get-ComputerInfo         6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:990:Cmdlet          Get-Content              6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:991:Cmdlet          Get-ControlPanelItem     3.1.0.0    Microsoft.PowerShell.Management
  Command.txt:992:Cmdlet          Get-Credential           6.1.0.0    Microsoft.PowerShell.Security
```

Das- `Get-Command` Cmdlet sendet Objekte über die Pipeline an den `Out-File` , um die **Command.txt** Datei im aktuellen Verzeichnis zu erstellen. `Select-String` verwendet den **path** -Parameter, um die **Command.txt** Datei anzugeben. Der **Pattern** -Parameter gibt **Get-Computer** als Suchmuster an. Der **Kontext** Parameter verwendet zwei Werte, vor und nach, und markiert Muster Übereinstimmungen in der Ausgabe mit einer Spitze Klammer ( `>` ). Der **Kontext** Parameter gibt die zwei Zeilen vor der ersten Muster Übereinstimmung und drei Zeilen nach der letzten Muster Übereinstimmung aus.

### Beispiel 9: Suchen aller Muster Übereinstimmungen

Dieses Beispiel zeigt, wie der **allmatches** -Parameter jede Muster Übereinstimmung in einer Textzeile findet. Standardmäßig `Select-String` findet nur das erste Vorkommen eines Musters in einer Textzeile. In diesem Beispiel werden Objekteigenschaften verwendet, die mit dem- `Get-Member` Cmdlet gefunden werden.

```
PS> $A = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell'

PS> $A

C:\Program Files\PowerShell\6\en-US\default.help.txt:3:    PowerShell Help System
C:\Program Files\PowerShell\6\en-US\default.help.txt:6:    Displays help about PowerShell cmdlets and concepts.
C:\Program Files\PowerShell\6\en-US\default.help.txt:9:    PowerShell Help describes PowerShell cmdlets

PS> $A.Matches

Groups   : {0}
Success  : True
Name     : 0
Captures : {0}
Index    : 4
Length   : 10
Value    : PowerShell

PS> $A.Matches.Length

8

PS> $B = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell' -AllMatches

PS> $B.Matches.Length

9
```

Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter. Der **path** -Parameter verwendet die-Variable `$PSHOME` , die das PowerShell-Verzeichnis angibt. Der Rest des Pfads enthält das Unterverzeichnis **en-US** und gibt jede `*.txt` Datei im Verzeichnis an. Die- `Get-ChildItem` Objekte werden in der- `$A` Variable gespeichert. Die `$A` Variable wird an das Cmdlet über die Pipeline gesendet `Select-String` . `Select-String` verwendet den **Pattern** -Parameter, um jede Datei nach der **PowerShell** -Zeichenfolge zu durchsuchen.

In der PowerShell-Befehlszeile `$A` werden der Inhalt der Variablen angezeigt. Es gibt eine Zeile, die zwei Vorkommen der Zeichenfolge **PowerShell** enthält.

Die- `$A.Matches` Eigenschaft listet das erste Vorkommen des Musters von **PowerShell** in jeder Zeile auf.

Die- `$A.Matches.Length` Eigenschaft zählt das erste Vorkommen des Musters von **PowerShell** in jeder Zeile.

Die `$B` -Variable verwendet die gleichen `Get-ChildItem` -und- `Select-String` Cmdlets, fügt jedoch den **allmatches** -Parameter hinzu. **Allmatches** findet jedes Vorkommen des Musters von **PowerShell** in jeder Zeile. Die in den `$A` Variablen und gespeicherten Objekte `$B` sind identisch.

Die- `$B.Matches.Length` Eigenschaft erhöht sich, weil für jede Zeile jedes Vorkommen des Musters **PowerShell** gezählt wird.

## PARAMETERS

### -Allmatches

Gibt an, dass das Cmdlet in jeder Textzeile mehr als eine Übereinstimmung sucht. Ohne diesen Parameter `Select-String` findet nur die erste Übereinstimmung in jeder Textzeile.

Wenn `Select-String` in einer Textzeile mehr als eine Übereinstimmung findet, gibt Sie immer noch nur ein **matchinfo** -Objekt für die Zeile aus, aber die **Matches** -Eigenschaft des-Objekts enthält alle Übereinstimmungen.

> [!NOTE]
> Dieser Parameter wird ignoriert, wenn er in Kombination mit dem **simplematch** -Parameter verwendet wird. Wenn Sie alle Übereinstimmungen zurückgeben möchten und das gesuchte Muster reguläre Ausdruckszeichen enthält, müssen Sie diese Zeichen mit Escapezeichen versehen, anstatt **simplematch** zu verwenden. Weitere Informationen zum Escapezeichen für reguläre Ausdrücke finden Sie unter [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) .

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

### -CaseSensitive

Gibt an, dass die Groß-/Kleinschreibung der Cmdlet-Übereinstimmungen beachtet Standardmäßig wird die Groß-/Kleinschreibung nicht beachtet.

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

### -Context

Erfasst die angegebene Anzahl von Zeilen vor und nach der Zeile, die mit dem Muster übereinstimmt.

Wenn Sie eine Zahl als Wert dieses Parameters eingeben, bestimmt diese Zahl die Anzahl der vor und nach der Übereinstimmung erfassten Zeilen. Wenn Sie zwei Zahlen als Wert eingeben, bestimmt die erste Zahl die Anzahl der Zeilen vor der Übereinstimmung und die zweite Zahl die Anzahl der Zeilen nach der Übereinstimmung. Beispiel: `-Context 2,3`.

In der Standard Anzeige werden Zeilen mit einer Entsprechung durch eine schließende spitze Klammer ( `>` ) (ASCII 62) in der ersten Spalte der Anzeige angegeben. Nicht gekennzeichnete Zeilen stehen für Kontext.

Der **Kontext** Parameter ändert nicht die Anzahl der Objekte, die von generiert werden `Select-String` .
`Select-String` generiert ein [matchinfo](/dotnet/api/microsoft.powershell.commands.matchinfo) -Objekt für jede Entsprechung. Der Kontext wird als Zeichen folgen Array in der **context** -Eigenschaft des Objekts gespeichert.

Wenn die Ausgabe eines `Select-String` Befehls in der Pipeline an einen anderen Befehl gesendet wird `Select-String` , durchsucht der empfangende Befehl nur den Text in der übereinstimmenden Zeile. Die übereinstimmende Zeile ist der Wert der **Line** -Eigenschaft des **matchinfo** -Objekts und nicht der Text in den Kontext Zeilen. Folglich ist der **Kontext** Parameter im empfangenden Befehl nicht gültig `Select-String` .

Wenn der Kontext eine Entsprechung enthält, enthält das **matchinfo** -Objekt für jede Übereinstimmung alle Kontext Zeilen, aber die überlappenden Zeilen werden nur einmal in der Anzeige angezeigt.

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kultur

Gibt einen Kultur Namen an, der dem angegebenen Muster entspricht. Der **Culture** -Parameter muss mit dem **simplematch** -Parameter verwendet werden. Das Standardverhalten verwendet die Kultur des aktuellen PowerShell-Runspace (Session).

Um eine Liste aller unterstützten Kulturen zu erhalten, verwenden Sie den `Get-Culture -ListAvailable` Befehl.

Außerdem akzeptiert dieser Parameter die folgenden Argumente:

- CurrentCulture, das ist die Standardeinstellung.
- Ordinal, bei dem es sich um einen nicht linguistischen binären Vergleich handelt.
- Invariant, das ist ein Kultur unabhängiger Vergleich.

Mit dem `Select-String -Culture Ordinal -CaseSensitive -SimpleMatch` Befehl erhalten Sie den schnellsten binären Vergleich.

Der **Culture** -Parameter verwendet die Vervollständigung mit der Tab-Taste, um durch die Liste der Argumente, die die verfügbaren Kulturen angeben Um alle verfügbaren Argumente aufzulisten, verwenden Sie den folgenden Befehl:

`(Get-Command Select-String).Parameters.Culture.Attributes.ValidValues`

Weitere Informationen zur .net CultureInfo.Name-Eigenschaft finden Sie unter [CultureInfo.Name](/dotnet/api//system.globalization.cultureinfo.name).

Der **Culture** -Parameter wurde in PowerShell 7 eingeführt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Culture of the current PowerShell session
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
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ausschließen

Schließen Sie die angegebenen Elemente aus. Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b.. Platzhalter sind zulässig.

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

### -Include

Schließt die angegebenen Elemente ein. Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b.. Platzhalter sind zulässig.

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

### -InputObject

Gibt den zu durchsuchenden Text an. Geben Sie eine Variable ein, die den Text enthält, oder geben Sie einen Befehl oder Ausdruck ein, der den Text abruft.

Die Verwendung des **Inputobject** -Parameters entspricht nicht dem Senden von Zeichen folgen in der Pipeline an `Select-String` .

Wenn Sie mehr als eine Zeichenfolge an das `Select-String` Cmdlet übergeben, sucht Sie in jeder Zeichenfolge nach dem angegebenen Text und gibt jede Zeichenfolge zurück, die den Suchtext enthält.

Wenn Sie den **Inputobject** -Parameter verwenden, um eine Auflistung von Zeichen folgen zu senden, `Select-String` behandelt die Auflistung als einzelne kombinierte Zeichenfolge. `Select-String` Gibt die Zeichen folgen als Einheit zurück, wenn der Suchtext in einer beliebigen Zeichenfolge gefunden wird.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ObjectRaw, Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -List

Nur die erste Instanz von übereinstimmenden Text wird von jeder Eingabedatei zurückgegeben. Dies ist die effizienteste Methode zum Abrufen einer Liste von Dateien, die Inhalte enthalten, die mit dem regulären Ausdruck übereinstimmen.

Standardmäßig `Select-String` gibt ein **matchinfo** -Objekt für jede gefundene Entsprechung zurück.

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

### -Literalpath

Gibt den Pfad zu den Dateien an, die durchsucht werden sollen. Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren. Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralFileRaw, LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nohervorzuheben

Standardmäßig wird `Select-String` die Zeichenfolge, die mit dem Muster übereinstimmt, das **Pattern** Sie nach dem Muster Parameter gesucht haben, hervorgehoben Der **noakzente** -Parameter deaktiviert die Hervorhebung.

Der Schwerpunkt verwendet negative Farben basierend auf Ihren PowerShell-Hintergrund-und Textfarben. Wenn Ihre PowerShell-Farben beispielsweise ein schwarzer Hintergrund mit weißem Text sind. Der Schwerpunkt liegt auf einem weißen Hintergrund mit schwarzem Text.

Dieser Parameter wurde in PowerShell 7 eingeführt.

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

### -Notmatch

Der **notmatch** -Parameter sucht nach Text, der nicht dem angegebenen Muster entspricht.

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

### -Path

Gibt den Pfad zu den Dateien an, die durchsucht werden sollen. Platzhalter sind zulässig. Der Standardspeicherort ist das lokale Verzeichnis.

Geben Sie Dateien im Verzeichnis an, z `log1.txt` `*.doc` . b., oder `*.*` . Wenn Sie nur das Verzeichnis angeben, führt der Befehl zu einem Fehler.

```yaml
Type: System.String[]
Parameter Sets: File, FileRaw
Aliases:

Required: True
Position: 1
Default value: Local directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Muster

Gibt den Text an, der in jeder Zeile gesucht werden soll. Der Pattern-Wert wird als regulärer Ausdruck behandelt.

Informationen zu regulären Ausdrücken finden Sie unter [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Quiet

Gibt an, dass das Cmdlet einen booleschen Wert (true oder false) anstelle eines **matchinfo** -Objekts zurückgibt. Der Wert ist "true", wenn das Muster gefunden wurde. Andernfalls ist der Wert false.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File, Object, LiteralFile
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RAW

Bewirkt, dass das Cmdlet nur die übereinstimmenden Zeichen folgen anstelle von **matchinfo** -Objekten ausgibt. Dies ist das Verhalten, das den Befehlen von UNIX **grep** oder Windows **findstr.exe** am ähnlichsten ist.

Dieser Parameter wurde in PowerShell 7 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ObjectRaw, FileRaw, LiteralFileRaw
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Simplematch

Gibt an, dass das Cmdlet anstelle einer regulären Ausdrucks Übereinstimmung eine einfache Entsprechung verwendet. In einer einfachen `Select-String` Suche durchsucht die Eingabe nach dem Text im **Pattern** -Parameter. Er interpretiert den Wert des **Pattern** -Parameters nicht als Anweisung für reguläre Ausdrücke.

Wenn **simplematch** verwendet wird, ist auch die **Matches** -Eigenschaft des zurückgegebenen **matchinfo** -Objekts leer.

> [!NOTE]
> Wenn dieser Parameter mit dem **allmatches** -Parameter verwendet wird, wird **allmatches** ignoriert.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können jedes beliebige Objekt über die Pipeline **ToString** an übergeben `Select-String` .

## AUSGABEN

### Microsoft. PowerShell. Commands. matchinfo, System. Boolean, System. String

Standardmäßig handelt es sich bei der Ausgabe um einen Satz von **matchinfo** -Objekten mit einer für jede gefundene Entsprechung. Wenn Sie den **quiet** -Parameter verwenden, ist die Ausgabe ein **boolescher** Wert, der angibt, ob das Muster gefunden wurde.
Wenn Sie den **RAW** -Parameter verwenden, handelt es sich bei der Ausgabe um einen Satz von **Zeichen** folgen Objekten, die dem Muster entsprechen.

## HINWEISE

`Select-String` ähnelt **grep** in UNIX oder **findstr.exe** in Windows.

Der **SLS** -Alias für das `Select-String` Cmdlet wurde in PowerShell 3,0 eingeführt.

> [!NOTE]
> Gemäß [genehmigten Verben für PowerShell-Befehle](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands)ist das offizielle Alias Präfix für `Select-*` Cmdlets `sc` , nicht `sl` . Daher sollte der richtige Alias für `Select-String` lauten `scs` , nicht `sls` . Dies ist eine Ausnahme von dieser Regel.

`Select-String`Wenn Sie verwenden möchten, geben Sie den Text ein, der als Wert des **Pattern** -Parameters gesucht werden soll. Um den zu durchsuchenden Text anzugeben, verwenden Sie die folgenden Kriterien:

- Geben Sie den Text in eine Zeichenfolge in Anführungszeichen ein, und übergeben Sie ihn dann an `Select-String` .
- Speichern Sie eine Text Zeichenfolge in einer Variablen, und geben Sie dann die Variable als Wert des **Inputobject** -Parameters an.
- Wenn der Text in Dateien gespeichert wird, verwenden Sie den **path** -Parameter, um den Pfad zu den Dateien anzugeben.

Standardmäßig `Select-String` interpretiert den Wert des **Pattern** -Parameters als regulären Ausdruck. Weitere Informationen finden Sie unter [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md). Sie können den **simplematch** -Parameter verwenden, um den übereinstimmenden regulären Ausdruck zu überschreiben. Der **simplematch** -Parameter sucht in der Eingabe nach Instanzen des Werts des **Pattern** -Parameters.

Die Standardausgabe von `Select-String` ist ein **matchinfo** -Objekt, das ausführliche Informationen zu den Übereinstimmungen enthält. Die Informationen im-Objekt sind nützlich, wenn Sie in Dateien nach Text suchen, da **matchinfo** -Objekte über Eigenschaften wie **Dateiname** und **Zeile** verfügen. Wenn die Eingabe nicht aus der Datei besteht, ist der Wert dieser Parameter **InputStream**.

Wenn Sie die Informationen im **matchinfo** -Objekt nicht benötigen, verwenden Sie den **quiet** -Parameter. Der **quiet** -Parameter gibt einen booleschen Wert (true oder false) zurück, um anzugeben, ob eine Entsprechung gefunden wurde, anstelle eines **matchinfo** -Objekts.

Beim Abgleichen `Select-String` von Ausdrücken verwendet die aktuelle Kultur, die für das System festgelegt ist. Verwenden Sie das-Cmdlet, um die aktuelle Kultur zu ermitteln `Get-Culture` .

Um die Eigenschaften eines **matchinfo** -Objekts zu ermitteln, geben Sie den folgenden Befehl ein:

`Select-String -Path test.txt -Pattern 'test' | Get-Member | Format-List -Property *`

## VERWANDTE LINKS

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md)

[about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md)

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)

[Get-Alias](Get-Alias.md)

[Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[Get-Command](../Microsoft.PowerShell.Core/Get-Command.md)

[Get-Member](Get-Member.md)

[Get-WinEvent](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[Out-File](Out-File.md)
