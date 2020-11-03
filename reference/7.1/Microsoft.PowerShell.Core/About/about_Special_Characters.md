---
description: Beschreibt die Sonderzeichenfolgen, mit denen gesteuert wird, wie die nächsten Zeichen in der Sequenz von PowerShell interpretiert werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_special_characters?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Special_Characters
ms.openlocfilehash: 6856d903276f5cbe4db222ac4c5d64ce6939413e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223039"
---
# <a name="about-special-characters"></a>Informationen zu Sonderzeichen

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt die Sonderzeichenfolgen, mit denen gesteuert wird, wie die nächsten Zeichen in der Sequenz von PowerShell interpretiert werden.

## <a name="long-description"></a>Lange Beschreibung

PowerShell unterstützt eine Reihe von Sonderzeichenfolgen, die zum Darstellen von Zeichen verwendet werden, die nicht Teil des Standardzeichensatzes sind. Die _Sequenzen werden häufig als_ Escapesequenzen bezeichnet.

Escapesequenzen beginnen mit dem Graviszeichen-Zeichen, das als großes Akzent (ASCII 96) bezeichnet wird, und Unterscheidung nach Groß-/Kleinschreibung. Das Graviszeichen-Zeichen kann auch als _Escapezeichen_ bezeichnet werden.

Escapesequenzen werden nur interpretiert, wenn Sie in Zeichen folgen mit doppelten Anführungszeichen () enthalten sind `"` .

PowerShell erkennt diese Escapesequenzen:

|  Sequenz   |       BESCHREIBUNG       |
| ----------- | ----------------------- |
| `` `0 ``    | Null                    |
| `` `a ``    | Warnung                   |
| `` `b ``    | Rückschritt               |
| `` `e ``    | Escape                  |
| `` `f ``    | Seitenvorschub               |
| `` `n ``    | Zeilenwechsel                |
| `` `r ``    | Wagenrücklauf         |
| `` `t ``    | Horizontaler Tabulator          |
| `` `u{x} `` | Unicode-Escapesequenz |
| `` `v ``    | Vertikaler Tabulator            |

PowerShell verfügt auch über ein spezielles Token, um zu kennzeichnen, wo die Verarbeitung beendet werden soll. Alle Zeichen, die diesem Token folgen, werden als Literalwerte verwendet, die nicht interpretiert werden.

Spezielles erteilungstoken:

| Sequenz |            BESCHREIBUNG             |
| -------- | ---------------------------------- |
| `--%`    | Die Verarbeitung der folgenden Elemente wird beendet. |

## <a name="null-0"></a>NULL (' 0)

Das NULL- `` `0 `` Zeichen () wird als leerer Bereich in der PowerShell-Ausgabe angezeigt.
Mit dieser Funktion können Sie PowerShell verwenden, um Textdateien zu lesen und zu verarbeiten, die NULL-Zeichen verwenden, z. b. Zeichen folgen Beendigung oder Indikator Beendigungs Indikatoren. Das NULL-Sonderzeichen entspricht nicht der- `$null` Variablen, in der ein **null** -Wert gespeichert wird.

## <a name="alert-a"></a>Warnung (' a ')

Das Warn `` `a `` Zeichen () sendet ein Signal an den Sprecher des Computers.
Sie können dieses Zeichen verwenden, um einen Benutzer über eine bevorstehende Aktion zu warnen. Im folgenden Beispiel werden zwei signalsignale an den Sprecher des lokalen Computers gesendet.

```powershell
for ($i = 0; $i -le 1; $i++){"`a"}
```

## <a name="backspace-b"></a>Rücktaste (' b ')

Das RÜCKTASTE `` `b `` Zeichen () verschiebt den Cursor um ein Zeichen nach hinten, aber es werden keine Zeichen gelöscht.

Im Beispiel wird die Word- **Sicherung** geschrieben und der Cursor dann zweimal zurück verschoben.
Dann schreibt an der neuen Position ein Leerzeichen gefolgt vom Wort **out**.

```powershell
"backup`b`b out"
```

```Output
back out
```

## <a name="escape-e"></a>Escapezeichen (' e)

Das `` `e `` Escapezeichen () wird am häufigsten verwendet, um eine virtuelle Terminal Sequenz (ANSI-Escapesequenz) anzugeben, die die Farbe von Text und andere Text Attribute wie z. b. Fett und Unterstreichung ändert. Diese Sequenzen können auch zum Positionieren und Scrollen von Cursorn verwendet werden. Der PowerShell-Host muss virtuelle Terminal Sequenzen unterstützen. Sie können den booleschen Wert von überprüfen `$Host.UI.SupportsVirtualTerminal` , um zu bestimmen, ob diese ANSI-Sequenzen unterstützt werden.

Weitere Informationen zu ANSI-Escapesequenzen finden Sie unter [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).

Im folgenden Beispiel wird Text mit einer grünen Vordergrundfarbe ausgegeben.

```powershell
$fgColor = 32 # green
"`e[${fgColor}mGreen text`e[0m"
```

```Output
Green text
```

## <a name="form-feed-f"></a>Formularfeed ("f")

Der Form-Feed ( `` `f `` ) ist eine Druck Anweisung, die die aktuelle Seite auswirft und auf der nächsten Seite den Druckvorgang fortsetzt. Das Formular Vorschub Zeichen wirkt sich nur auf gedruckte Dokumente aus. Die Bildschirmausgabe wird nicht beeinträchtigt.

## <a name="new-line-n"></a>Neue Zeile (' n)

Das neue Zeilen `` `n `` Umbruch Zeichen () fügt einen Zeilenumbruch direkt hinter das Zeichen ein.

In diesem Beispiel wird gezeigt, wie Sie mit dem Zeilenendezeichen Zeilenumbrüche in einem `Write-Host` Befehl erstellen.

```powershell
"There are two line breaks to create a blank line`n`nbetween the words."
```

```Output
There are two line breaks to create a blank line

between the words.
```

## <a name="carriage-return-r"></a>Wagen Rücklauf ("r")

Das Wagen Rücklauf `` `r `` Zeichen () verschiebt den Ausgabe Cursor an den Anfang der aktuellen Zeile und setzt das Schreiben fort. Alle Zeichen in der aktuellen Zeile werden überschrieben.

In diesem Beispiel wird der Text vor dem Wagen Rücklauf überschrieben.

```powershell
Write-Host "These characters are overwritten.`rI want this text instead "
```

Beachten Sie, dass der Text vor dem `` `r `` Zeichen nicht gelöscht wird. er wird überschrieben.

```Output
I want this text instead written.
```

## <a name="horizontal-tab-t"></a>Horizontale Registerkarte ('t)

Das horizontale Tabulator `` `t `` Zeichen () wechselt zum nächsten Tabstopp und setzt den Schreibvorgang an diesem Punkt fort. Standardmäßig verfügt die PowerShell-Konsole über einen Tabstopp in jedem achten Bereich.

In diesem Beispiel werden zwei Registerkarten zwischen den einzelnen Spalten eingefügt.

```powershell
"Column1`t`tColumn2`t`tColumn3"
```

```Output
Column1         Column2         Column3
```

## <a name="unicode-character-ux"></a>Unicode-Zeichen (' u {x})

Die Unicode-Escapesequenz ( `` `u{x} `` ) ermöglicht es Ihnen, ein beliebiges Unicode-Zeichen durch die hexadezimale Darstellung des zugehörigen Code Punkts anzugeben. Dies schließt Unicode-Zeichen oberhalb der grundlegenden mehrsprachigen Ebene (> `0xFFFF` ) ein, die Emoji-Zeichen wie das " **Thumbs up** ()"-Zeichen enthält `` `u{1F44D} `` . Die Unicode-Escapesequenz erfordert mindestens eine hexadezimale Ziffer und unterstützt bis zu sechs hexadezimale Ziffern. Der maximale Hexadezimalwert für die Sequenz ist `10FFFF` .

In diesem Beispiel wird das **nach-unten-Pfeil** Symbol (&#x2195;) ausgegeben.

```powershell
"`u{2195}"
```

## <a name="vertical-tab-v"></a>Senkrechter Tabulator (' v)

Das horizontale `` `v `` Tabstopp Zeichen () wechselt zum nächsten vertikalen Tabstopp und schreibt die verbleibende Ausgabe an diesem Punkt. Dies hat keine Auswirkungen auf die standardmäßige Windows-Konsole.

```powershell
Write-Host "There is a vertical tab`vbetween the words."
```

Das folgende Beispiel zeigt die Ausgabe, die Sie auf einem Drucker oder einem anderen Konsolen Host erhalten.

```Output
There is a vertical tab
                       between the words.
```

## <a name="stop-parsing-token---"></a>Stoppt das-Element (--%).

Das Token zum Verhindern von Stopps ( `--%` ) verhindert, dass PowerShell Zeichen folgen als PowerShell-Befehle und-Ausdrücke interpretiert. Dadurch können diese Zeichen folgen zur Interpretation an andere Programme übermittelt werden.

Platzieren Sie das Ende-Parsing-Token nach dem Programmnamen und vor Programm Argumenten, die möglicherweise Fehler verursachen.

In diesem Beispiel verwendet der `Icacls` Befehl das Ende-Element-Token.

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

PowerShell sendet die folgende Zeichenfolge an `Icacls` .

```
X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

Hier ist ein weiteres Beispiel angegeben. Die **showargs** -Funktion gibt die an Sie über gebenden Werte aus. In diesem Beispiel übergeben wir die-Variable mit dem Namen `$HOME` zweimal an die-Funktion.

```powershell
function showArgs {
  "`$args = " + ($args -join '|')
}

showArgs $HOME --% $HOME
```

Sie können in der Ausgabe sehen, dass die Variable für den ersten Parameter `$HOME` von PowerShell interpretiert wird, sodass der Wert der Variablen an die Funktion übergeben wird. Die zweite Verwendung von `$HOME` erfolgt nach dem Token zum Verhindern von Stopps, sodass die Zeichenfolge "$Home" ohne Interpretation an die Funktion übermittelt wird.

```Output
$args = C:\Users\username|--%|$HOME
```

Weitere Informationen zum Token zum Verhindern von Stopps finden Sie unter [about_Parsing](about_Parsing.md).

## <a name="see-also"></a>Weitere Informationen:

[about_Quoting_Rules](about_Quoting_Rules.md)

