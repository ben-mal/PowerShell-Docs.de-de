---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-host?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Host
ms.openlocfilehash: d6707a9f5c54b736d0b917d453416ccdb0850baa
ms.sourcegitcommit: 758e6dbb428295698d4852b3e19f5d03deade037
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "93219943"
---
# Write-Host

## ZUSAMMENFASSUNG

Schreibt angepasste Ausgabe an einen Host.

## SYNTAX

```
Write-Host [[-Object] <Object>] [-NoNewline] [-Separator <Object>] [-ForegroundColor <ConsoleColor>]
 [-BackgroundColor <ConsoleColor>] [<CommonParameters>]
```

## DESCRIPTION

Der `Write-Host` primäre Zweck des Cmdlets besteht darin, die nur-(Host-) Anzeige Ausgabe zu entwickeln, z. b. das Drucken von farbigem Text, z. b. bei der Eingabeaufforderung des Benutzers in Verbindung mit [Read-Host](Read-Host.md).
`Write-Host` verwendet die Methode " [destring ()](/dotnet/api/system.object.tostring) ", um die Ausgabe zu schreiben. Verwenden Sie hingegen zum Ausgeben von Daten an die Pipeline [Write-Output](Write-Output.md) oder implizierte Ausgabe.

Mithilfe des-Parameters können Sie die Textfarbe angeben `ForegroundColor` , und Sie können die Hintergrundfarbe mit dem- `BackgroundColor` Parameter angeben. Mit dem Separator-Parameter können Sie eine Zeichenfolge angeben, die zum Trennen der angezeigten Objekte verwendet werden soll. Das jeweilige Ergebnis hängt von dem Programm ab, das PowerShell gehostet.

> [!NOTE]
> Ab Windows PowerShell 5,0 `Write-Host` ist ein Wrapper dafür, mit `Write-Information` `Write-Host` dem Sie die Ausgabe an den Informationsdaten Strom ausgeben können. Dies ermöglicht die **Erfassung** oder **Unterdrückung** von Daten, die mithilfe von geschrieben wurden, während die abwärts `Write-Host` Kompatibilität beibehalten wird.
>
> Die `$InformationPreference` Einstellungs Variable und der `InformationAction` Allgemeine Parameter wirken sich nicht auf `Write-Host` Nachrichten aus. Die Ausnahme von dieser Regel ist `-InformationAction Ignore` , wodurch die Ausgabe effektiv unterdrückt wird `Write-Host` . (siehe "Beispiel 5")

## BEISPIELE

### Beispiel 1: Schreiben in die Konsole, ohne eine neue Zeile hinzuzufügen

```powershell
Write-Host "no newline test " -NoNewline
Write-Host "second string"
```

```output
no newline test second string
```

Mit diesem Befehl wird die Zeichenfolge "No Zeilenumbruch Test" mit dem- `NoNewline` Parameter angezeigt.

Eine zweite Zeichenfolge wird geschrieben, aber Sie wird in derselben Zeile wie die erste erstellt, da die Zeichen folgen nicht durch eine neue Zeile getrennt werden.

### Beispiel 2: Schreiben in die Konsole und einschließen eines Trenn Zeichens

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", +2= "
```

```output
2, +2= 4, +2= 6, +2= 8, +2= 10, +2= 12
```

Mit diesem Befehl werden die geraden Zahlen von zwei bis zwölf angezeigt. Der **Separator** -Parameter wird verwendet, um die Zeichenfolge `, +2= ` (Komma, Leerzeichen, `+` , `2` , `=` , Leerzeichen) hinzuzufügen.

### Beispiel 3: Schreiben mit unterschiedlichen Text-und Hintergrundfarben

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", -> " -ForegroundColor DarkGreen -BackgroundColor White
```

```output
2, -> 4, -> 6, -> 8, -> 10, -> 12
```

Mit diesem Befehl werden die geraden Zahlen von zwei bis zwölf angezeigt. Er verwendet den `ForegroundColor` -Parameter, um dunkelgrünen Text auszugeben, und den- `BackgroundColor` Parameter, um einen weißen Hintergrund anzuzeigen.

### Beispiel 4: Schreiben mit unterschiedlichen Text-und Hintergrundfarben

```powershell
Write-Host "Red on white text." -ForegroundColor red -BackgroundColor white
```

```output
Red on white text.
```

Mit diesem Befehl wird die Zeichenfolge „Red on white text“ angezeigt. Der Text ist rot, wie vom- `ForegroundColor` Parameter definiert. Der Hintergrund ist weiß, wie vom- `BackgroundColor` Parameter definiert.

### Beispiel 5: Unterdrücken der Ausgabe von Write-Host

```powershell
# The following two statements can be used to effectively suppress output from Write-Host
Write-Host "I won't print" -InformationAction Ignore
Write-Host "I won't print" 6>$null
```

```output

```

Diese Befehle unterdrücken die Ausgabe des `Write-Host` Cmdlets effektiv. Der erste verwendet den- `InformationAction` Parameter mit dem- `Ignore` Wert, um die Ausgabe in den Informationsdaten Strom zu unterdrücken.
Im zweiten Beispiel wird der Informationsdaten Strom des Befehls an die `$null` -Variable umgeleitet und dadurch unterdrückt.

## PARAMETERS

### -BackgroundColor

Gibt die Hintergrundfarbe an. Es ist kein Standardwert vorhanden. Zulässige Werte für diesen Parameter:

- Schwarz
- DarkBlue
- DarkGreen
- DarkCyan
- DarkRed
- DarkMagenta
- DarkYellow
- Grau
- DarkGray
- Blau
- Grün
- Cyan
- Red
- Magenta
- Gelb
- White

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForegroundColor

Gibt die Textfarbe an. Es ist kein Standardwert vorhanden. Zulässige Werte für diesen Parameter:

- Schwarz
- DarkBlue
- DarkGreen
- DarkCyan
- DarkRed
- DarkMagenta
- DarkYellow
- Grau
- DarkGray
- Blau
- Grün
- Cyan
- Red
- Magenta
- Gelb
- White

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Objekt

Objekte, die auf dem Host angezeigt werden sollen.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg, Message

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Trennzeichen

Gibt eine Trenn Zeichenfolge an, die zwischen vom Host angezeigten Objekten eingefügt werden soll.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.Object

Sie können die an den Host zu schreibenden Objekte weiterreichen.

## AUSGABEN

### Keine

`Write-Host` sendet die Objekte an den Host. und gibt keine Objekte zurück. Der Host zeigt jedoch die Objekte an, die an den Host `Write-Host` gesendet werden.

## HINWEISE

- Beim Schreiben einer Auflistung auf den Host werden Elemente der Auflistung in derselben Zeile gedruckt, getrennt durch ein einzelnes Leerzeichen. Dies kann mit dem **Separator** -Parameter überschrieben werden.

- Nicht primitive Datentypen wie z. b. Objekte mit Eigenschaften können unerwartete Ergebnisse verursachen und keine sinnvolle Ausgabe bereitstellen. Beispielsweise `Write-Host @{a = 1; b = 2}` wird `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` auf dem Host gedruckt.

## VERWANDTE LINKS

[Clear-Host](../Microsoft.PowerShell.Core/Clear-Host.md)

[Out-Host](../Microsoft.PowerShell.Core/Out-Host.md)

[Write-Debug](Write-Debug.md)

[Schreibfehler](Write-Error.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
