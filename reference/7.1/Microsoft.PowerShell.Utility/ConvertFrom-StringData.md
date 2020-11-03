---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/21/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-stringdata?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-StringData
ms.openlocfilehash: 256807079f8ef47baf20cd70df326298e4ce9ed0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215908"
---
# ConvertFrom-StringData

## ZUSAMMENFASSUNG
Konvertiert eine Zeichenfolge, die mindestens ein Schlüssel-Wert-Paar enthält, in eine Hashtabelle.

## SYNTAX

### Alle

```
ConvertFrom-StringData [-StringData] <String> [[-Delimiter] <Char>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `ConvertFrom-StringData` Cmdlet wird eine Zeichenfolge, die ein oder mehrere Schlüssel-Wert-Paare enthält, in eine Hash Tabelle konvertiert. Da sich jedes Schlüssel-Wert-Paar in einer separaten Zeile befinden muss, werden diese Zeichen folgen häufig als Eingabeformat verwendet. Standardmäßig muss der **Schlüssel** von dem **Wert** durch ein Gleichheitszeichen () getrennt werden `=` .

Das- `ConvertFrom-StringData` Cmdlet gilt als sicheres Cmdlet, das im- `DATA` Abschnitt eines Skripts oder einer Funktion verwendet werden kann. Bei Verwendung in einem `DATA` Abschnitt muss der Inhalt der Zeichenfolge den Regeln für einen Daten Abschnitt entsprechen. Weitere Informationen finden Sie unter [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).

`ConvertFrom-StringData` unterstützt Escapezeichenfolgen, die von herkömmlichen maschinellen Übersetzungstools zugelassen werden. Das heißt, das Cmdlet kann umgekehrte Schrägstriche ( `\` ) als Escapezeichen in den Zeichen folgen Daten mit der [Regex. unescape-Methode und nicht](/dotnet/api/system.text.regularexpressions.regex.unescape)mit dem PowerShell-Graviszeichen-Zeichen () interpretieren, \` das normalerweise das Ende einer Zeile in einem Skript signalisiert. In der here-Zeichenfolge funktioniert das Hochkommazeichen nicht. Sie können auch einen literalen umgekehrten Schrägstrich in den Ergebnissen beibehalten, indem Sie ihn mit einem vorangehenden umgekehrten Schrägstrich versehen, wie folgt: `\\` . Umgekehrte Schrägstriche ohne Escapezeichen, wie z. B. solche, die häufig in Dateipfaden verwendet werden, können in den Ergebnissen als unzulässige Escapesequenzen gerendert werden.

PowerShell 7 fügt den **Delimiter** -Parameter hinzu.

## BEISPIELE

### Beispiel 1: Konvertieren einer here-Zeichenfolge in einfachen Anführungszeichen in eine Hash Tabelle

In diesem Beispiel wird eine here-Zeichenfolge von Benutzer Nachrichten in einfache Anführungszeichen in eine Hash Tabelle konvertiert. In einer Zeichenfolge in einfachen Anführungszeichen werden Werte nicht durch Variablen ersetzt und Ausdrücke nicht ausgewertet.
Mit dem- `ConvertFrom-StringData` Cmdlet wird der Wert in der- `$Here` Variablen in eine Hash Tabelle konvertiert.

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
ConvertFrom-StringData -StringData $Here
```

```Output
Name                           Value
----                           -----
Msg3                           The specified variable does not exist.
Msg2                           Credentials are required for this command.
Msg1                           The string parameter is required.
```

### Beispiel 2: Konvertieren von Zeichen folgen Daten mit einem anderen Trennzeichen

Dieses Beispiel zeigt, wie Zeichen folgen Daten konvertiert werden, die ein anderes Zeichen als Trennzeichen verwenden. In diesem Beispiel verwenden die Zeichen folgen Daten das senkrechter Zeichen ( `|` ) als Trennzeichen.

```powershell
$StringData = @'
color|red
model|coupe
year|1965
condition|mint
'@
$carData = ConvertFrom-StringData -StringData $StringData -Delimiter '|'
$carData
```

```Output
Name                           Value
----                           -----
condition                      mint
model                          coupe
color                          red
year                           1965
```

### Beispiel 3: Konvertieren einer here-Zeichenfolge mit einem Kommentar

In diesem Beispiel wird eine here-Zeichenfolge, die einen Kommentar und mehrere Schlüssel-Wert-Paare enthält, in eine Hash Tabelle konvertiert.

```powershell
ConvertFrom-StringData -StringData @'
Name = Disks.ps1

# Category is optional.

Category = Storage
Cost = Free
'@
```

```Output
Name                           Value
----                           -----
Cost                           Free
Category                       Storage
Name                           Disks.ps1
```

Der Wert des **StringData** -Parameters ist eine here-Zeichenfolge anstelle einer Variablen, die eine here-Zeichenfolge enthält. Beide Formate sind gültig. Die here-Zeichenfolge enthält einen Kommentar zu einer der Zeichenfolgen.
`ConvertFrom-StringData` ignoriert einzeilige Kommentare, aber das `#` Zeichen muss das erste Zeichen in der Zeile sein, das kein Leerzeichen ist. Alle Zeichen in der Zeile nach dem `#` werden ignoriert.

### Beispiel 4: Konvertieren einer Zeichenfolge in eine Hash Tabelle

In diesem Beispiel wird eine reguläre Zeichenfolge in doppelten Anführungszeichen (keine here-Zeichenfolge) in eine Hash Tabelle konvertiert und in der `$A` Variablen gespeichert.

```powershell
$A = ConvertFrom-StringData -StringData "Top = Red `n Bottom = Blue"
$A
```

```Output
Name             Value
----             -----
Bottom           Blue
Top              Red
```

Um die Bedingung zu erfüllen, dass sich jedes Schlüssel-Wert-Paar in einer separaten Zeile befinden muss, verwendet die Zeichenfolge das PowerShell-Zeilen vorformat ( \` n), um die Paare voneinander zu trennen.

### Beispiel 5: Verwenden von ConvertFrom-StringData im Daten Abschnitt eines Skripts

Dieses Beispiel zeigt einen `ConvertFrom-StringData` Befehl, der im Daten Abschnitt eines Skripts verwendet wird.
Die Anweisungen unter dem DATA-Abschnitt zeigen den Text für den Benutzer an.

```powershell
$TextMsgs = DATA {
ConvertFrom-StringData @'
Text001 = The $Notebook variable contains the name of the user's system notebook.
Text002 = The $MyNotebook variable contains the name of the user's private notebook.
'@
}
$TextMsgs
```

```Output
Name             Value
----             -----
Text001          The $Notebook variable contains the name of the user's system notebook.
Text002          The $MyNotebook variable contains the name of the user's private notebook.
```

Da der Text Variablennamen enthält, muss er in einer Zeichenfolge in einfachen Anführungszeichen eingeschlossen werden, damit die Variablen wörtlich interpretiert und nicht erweitert werden. Variablen sind im **Data** -Abschnitt nicht zulässig.

### Beispiel 6: Verwenden des Pipeline-Operators zum Übergeben einer Zeichenfolge

Dieses Beispiel zeigt, dass Sie einen Pipeline Operator () verwenden können, um `|` eine Zeichenfolge an zu senden `ConvertFrom-StringData` . Der Wert der `$Here` Variablen wird an weitergeleitet `ConvertFrom-StringData` und das Ergebnis in der `$Hash` Variablen.

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
$Hash = $Here | ConvertFrom-StringData
$Hash
```

```Output
Name     Value
----     -----
Msg3     The specified variable does not exist.
Msg2     Credentials are required for this command.
Msg1     The string parameter is required.
```

### Beispiel 7: Verwenden von Escapezeichen zum Hinzufügen neuer Zeilen und Zurückgeben von Zeichen

Dieses Beispiel zeigt die Verwendung von Escapezeichen zum Erstellen neuer Zeilen und zum Zurückgeben von Zeichen in den Quelldaten. Die Escapesequenz `\n` wird verwendet, um neue Zeilen in einem TextBlock zu erstellen, der mit einem Namen oder einem Element in der resultierenden Hash Tabelle verknüpft ist.

```powershell
ConvertFrom-StringData @"
Vincentio = Heaven doth with us as we with torches do,\nNot light them for themselves; for if our virtues\nDid not go forth of us, 'twere all alike\nAs if we had them not.
Angelo = Let there be some more test made of my metal,\nBefore so noble and so great a figure\nBe stamp'd upon it.
"@ | Format-List
```

```Output
Name  : Angelo
Value : Let there be some more test made of my metal,
        Before so noble and so great a figure
        Be stamp'd upon it.

Name  : Vincentio
Value : Heaven doth with us as we with torches do,
        Not light them for themselves; for if our virtues
        Did not go forth of us, 'twere all alike
        As if we had them not.
```

### Beispiel 8: Verwenden eines umgekehrten Schrägstrichs zum ordnungsgemäßen Rendering eines Dateipfads

In diesem Beispiel wird gezeigt, wie der umgekehrte Schrägstrich-Escapezeichen in den Zeichen folgen Daten verwendet wird, damit ein Dateipfad in der resultierenden Hash Tabelle ordnungsgemäß dargestellt werden kann `ConvertFrom-StringData` . Der doppelte umgekehrte Schrägstrich stellt sicher, dass der umgekehrte Literalschrägstrich in der Ausgabe der Hashtabelle ordnungsgemäß gerendert wird.

```powershell
ConvertFrom-StringData "Message=Look in c:\\Windows\\System32"
```

```Output
Name                           Value
----                           -----
Message                        Look in c:\Windows\System32
```

## PARAMETERS

### -StringData

Gibt die zu konvertierende Zeichenfolge an. Sie können diesen Parameter verwenden oder eine Zeichenfolge an die Pipeline übergeben `ConvertFrom-StringData` . Der Parametername ist optional.

Der Wert dieses Parameters muss eine Zeichenfolge sein, die mindestens ein Schlüssel-Wert-Paar enthält. Jedes Schlüssel-Wert-Paar muss sich in einer separaten Zeile befinden, oder jedes Paar muss durch Zeilen vorzeichenzeichen ( \` n) getrennt werden.

Sie können Kommentare in die Zeichenfolge einschließen, aber die Kommentare dürfen sich nicht in derselben Zeile wie ein Schlüssel-Wert-Paar befinden. `ConvertFrom-StringData` ignoriert einzeilige Kommentare. Das `#` Zeichen muss das erste Zeichen in der Zeile sein, das kein Leerzeichen ist. Alle Zeichen in der Zeile nach dem `#` werden ignoriert. Die Kommentare sind nicht in der Hashtabelle enthalten.

Eine here-Zeichenfolge ist eine Zeichenfolge, die aus einer oder mehreren Zeilen besteht. Anführungszeichen in der here-Zeichenfolge werden buchstäblich als Teil der Zeichen folgen Daten interpretiert. Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Delimiter

Das Zeichen, mit dem der **Schlüssel** von den **Wertdaten** in der zu konvertierenden Zeichenfolge getrennt wird.
Das Standard Trennzeichen ist das Gleichheitszeichen ( `=` ). Dieser Parameter wurde in PowerShell 7 hinzugefügt.

```yaml
Type: System.Char
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: '='
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String

Sie können eine Zeichenfolge mit einem Schlüssel-Wert-Paar über die Pipeline an übergeben `ConvertFrom-StringData` .

## AUSGABEN

### System.Collections.Hashtable

Dieses Cmdlet gibt eine Hash Tabelle zurück, die aus den Schlüssel-Wert-Paaren erstellt wird.

## HINWEISE

Eine here-Zeichenfolge ist eine Zeichenfolge, die aus mindestens einer Zeile besteht und in der Anführungszeichen als solche interpretiert werden.

Dieses Cmdlet kann in Skripts hilfreich sein, in denen Benutzer Meldungen in mehreren gesprochenen Sprachen angezeigt werden. Sie können die wörterbuchähnlichen Hashtabellen verwenden, um Textzeichenfolgen z. B. in Ressourcendateien von Code zu isolieren und die Textzeichenfolgen für die Verwendung in Übersetzungstools zu formatieren.

## VERWANDTE LINKS

