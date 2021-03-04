---
description: Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.
Locale: en-US
ms.date: 11/23/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über psread Line
ms.openlocfilehash: ddc88dda3514e4279b6d91b023e26da88f645af7
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685211"
---
# <a name="psreadline"></a>PSReadLine

## <a name="about_psreadline"></a>about_PSReadLine

## <a name="short-description"></a>Kurze Beschreibung

Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.

## <a name="long-description"></a>Lange Beschreibung

Psleline 2,2 bietet eine leistungsfähige Befehlszeilen Bearbeitungsfunktion für die PowerShell-Konsole. Sie bietet:

- Syntax Farbgebung der Befehlszeile
- Visuelle Hinweise auf Syntax Fehler
- Bessere mehrzeilige Erfahrung (sowohl Bearbeitung als auch Verlauf)
- Anpassbare Tastenkombinationen
- Cmd-und Emacs-Modi
- Viele Konfigurationsoptionen
- Bash-Stil Vervollständigung (optional im cmd-Modus, Standard im Emacs-Modus)
- Emacs: Yank/Kill-Ring
- PowerShell-tokenbasierte "Wort Bewegung" und "Kill"
- Predictive IntelliSense

Psread Line 2.2.0 Es wurden zwei neue vorhersagbare IntelliSense-Features hinzugefügt:

- Der Parameter " **prätionviewstyle** " wurde hinzugefügt, um die Auswahl der neuen zu ermöglichen `ListView` .
- Verbindung mit psread Line zu den `CommandPrediction` in PS 7,1 eingeführten APIs, damit Benutzer ein präatormodul importieren können, das die Vorschläge aus einer benutzerdefinierten Quelle darstellen kann.

Für psread Line ist PowerShell 3,0 oder höher erforderlich. Psleline funktioniert mit dem standardmäßigen Konsolen Host, Visual Studio Code und Fenster Terminal. Es funktioniert nicht in PowerShell ISE.

Psread Line 2.2.0 wird mit PowerShell 7,2 ausgeliefert und wird in allen unterstützten Versionen von PowerShell unterstützt. Es ist für die Installation über das PowerShell-Katalog verfügbar.
Führen Sie den folgenden Befehl aus, um psread Line 2.2.0 in einer unterstützten Version von PowerShell zu installieren.

```powershell
Install-Module -Name PSReadLine -AllowPrerelease
```

> [!NOTE]
> Ab PowerShell 7,0 überspringt PowerShell das automatische Laden von psleseline unter Windows, wenn ein Bildschirm Leseprogramm erkannt wird. Derzeit funktioniert psread Line nicht gut mit den Bildschirmlesern. Das Standard Rendering und die Formatierung von PowerShell 7,0 unter Windows funktionieren ordnungsgemäß. Sie können das Modul ggf. manuell laden.

## <a name="predictive-intellisense"></a>Predictive IntelliSense

Predictive IntelliSense ist eine Ergänzung zum Konzept der Vervollständigung mit der Tab-Taste, die dem Benutzer hilft, Befehle erfolgreich abzuschließen. Sie ermöglicht Benutzern das ermitteln, bearbeiten und ausführen vollständiger Befehle basierend auf übereinstimmenden Vorhersagen aus dem Verlauf des Benutzers und zusätzlichen domänenspezifischen Plug-ins.

### <a name="enable-predictive-intellisense"></a>Aktivieren von Predictive IntelliSense

Predictive IntelliSense ist standardmäßig deaktiviert. Um Vorhersagen zu aktivieren, führen Sie einfach den folgenden Befehl aus:

```powershell
Set-PSReadLineOption -PredictionSource History
```

Der Parameter " **prätionsource** " kann auch Plug-Ins für domänenspezifische und benutzerdefinierte Anforderungen akzeptieren.

Um Predictive IntelliSense zu deaktivieren, führen Sie einfach Folgendes aus:

```powershell
Set-PSReadLineOption -PredictionSource None
```

Die folgenden Funktionen sind in der-Klasse **[Microsoft. PowerShell. psconsolereadline]** verfügbar.

## <a name="basic-editing-functions"></a>Grundlegende Bearbeitungsfunktionen

### <a name="abort"></a>Abbrechen

Abbrechen der aktuellen Aktion, z.b. inkrementelle Verlaufs Suche.

- Ansehen `<Ctrl+g>`

### <a name="acceptandgetnext"></a>Akzeptandgetnext

Versuchen Sie, die aktuelle Eingabe auszuführen. Wenn Sie ausgeführt werden kann (wie z. b. Accept Line), erinnern Sie sich beim nächsten Aufruf von "read line" an das nächste Element aus dem Verlauf.

- Ansehen `<Ctrl+o>`

### <a name="acceptline"></a>Annahme

Versuchen Sie, die aktuelle Eingabe auszuführen. Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.

- Befehl: `<Enter>`
- Ansehen `<Enter>`
- VI-Einfügemodus: `<Enter>`

### <a name="addline"></a>AddLine

Die Fortsetzungs Aufforderung wird in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten. Dies ist nützlich, um mehrzeilige Eingaben als einen einzelnen Befehl einzugeben, auch wenn eine einzelne Zeile allein eine Eingabe ist.

- Befehl: `<Shift+Enter>`
- Ansehen `<Shift+Enter>`
- VI-Einfügemodus: `<Shift+Enter>`
- VI-Befehlsmodus: `<Shift+Enter>`

### <a name="backwarddeletechar"></a>Backwarddeletechar

Löschen Sie das Zeichen vor dem Cursor.

- Cmd: `<Backspace>` , `<Ctrl+h>`
- Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`
- VI-Einfügemodus: `<Backspace>`
- VI-Befehlsmodus: `<X>` , `<d,h>`

### <a name="backwarddeleteinput"></a>Backwarddelta-eInput

Wie backwardkillinput: löscht Text von der Stelle bis zum Anfang der Eingabe, legt den gelöschten Text jedoch nicht in den Kill-Ring.

- Befehl: `<Ctrl+Home>`
- VI-Einfügemodus: `<Ctrl+u>` , `<Ctrl+Home>`
- VI-Befehlsmodus: `<Ctrl+u>` , `<Ctrl+Home>`

### <a name="backwarddeleteline"></a>Backwarddelta-Eline

Wie backwardkillline löscht Text vom Punkt bis zum Anfang der Zeile, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.

- VI-Befehlsmodus: `<d,0>`

### <a name="backwarddeleteword"></a>Backwarddeleteword

Löscht das vorherige Wort.

- VI-Befehlsmodus: `<Ctrl+w>` , `<d,b>`

### <a name="backwardkillinput"></a>Backwardkillinput

Löschen Sie den Text vom Beginn der Eingabe bis zum Cursor. Der gelöschte Text wird in den Kill-Ring eingefügt.

- Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`

### <a name="backwardkillline"></a>Backwardkillline

Löschen Sie den Text vom Anfang der aktuellen logischen Zeile bis zum Cursor. Der gelöschte Text wird in den Kill-Ring eingefügt.

- Die Bindung der Funktion ist aufgehoben.

### <a name="backwardkillword"></a>Backwardkillword

Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor. Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht. Der gelöschte Text wird in den Kill-Ring eingefügt.

- Cmd: `<Ctrl+Backspace>` , `<Ctrl+w>`
- Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`
- VI-Einfügemodus: `<Ctrl+Backspace>`
- VI-Befehlsmodus: `<Ctrl+Backspace>`

### <a name="cancelline"></a>Cancelline

Brechen Sie die aktuelle Eingabe ab, belassen Sie die Eingabe auf dem Bildschirm, kehren Sie jedoch zurück zum Host, damit die Eingabeaufforderung erneut ausgewertet wird.

- VI-Einfügemodus: `<Ctrl+c>`
- VI-Befehlsmodus: `<Ctrl+c>`

### <a name="copy"></a>Kopieren

Kopiert den ausgewählten Bereich in die Zwischenablage des Systems. Wenn keine Region ausgewählt ist, kopieren Sie die gesamte Zeile.

- Befehl: `<Ctrl+C>`

### <a name="copyorcancelline"></a>Copyorcancelline

Wenn Text ausgewählt ist, kopieren Sie ihn in die Zwischenablage, andernfalls brechen Sie die Zeile ab.

- Befehl: `<Ctrl+c>`
- Ansehen `<Ctrl+c>`

### <a name="cut"></a>Ausschneiden

Löscht die ausgewählte Region, in der Gelöschter Text in der Zwischenablage des Systems

- Befehl: `<Ctrl+x>`

### <a name="deletechar"></a>DeleteChar

Löschen Sie das Zeichen unter dem Cursor.

- Befehl: `<Delete>`
- Ansehen `<Delete>`
- VI-Einfügemodus: `<Delete>`
- VI-Befehlsmodus: `<Delete>` , `<x>` , `<d,l>` , `<d,Spacebar>`

### <a name="deletecharorexit"></a>Deletecharorexit

Löschen Sie das Zeichen unter dem Cursor, oder beenden Sie den Prozess, wenn die Zeile leer ist.

- Ansehen `<Ctrl+d>`

### <a name="deleteendofbuffer"></a>Deleteendof Buffer

Löscht bis zum Ende des mehrzeiligen Puffers.

- VI-Befehlsmodus: `<d,G>`

### <a name="deleteendofword"></a>Deleteendof

Bis zum Ende des Worts löschen.

- VI-Befehlsmodus: `<d,e>`

### <a name="deleteline"></a>"Deleteline

Löscht die aktuelle logische Zeile eines mehrzeiligen Puffers und ermöglicht Rückgängigmachen.

- VI-Befehlsmodus: `<d,d>` , `<d,_>`

### <a name="deletepreviouslines"></a>Deletepreviouslines

Löscht die vorherigen angeforderten logischen Zeilen und die aktuelle logische Zeile in einem mehrzeiligen Puffer.

- VI-Befehlsmodus: `<d,k>`

### <a name="deleterelativelines"></a>Deleterelativelines

Löscht vom Anfang des Puffers in die aktuelle logische Zeile in einem mehrzeiligen Puffer.

Bei den meisten VI-Befehlen `<d,g,g>` kann dem Befehl ein numerisches Argument vorangestellt werden, das eine absolute Zeilennummer angibt, die in Verbindung mit der aktuellen Zeilennummer einen Bereich von Zeilen bilden, die gelöscht werden sollen.
Wenn kein Wert angegeben wird, wird das numerische Argument standardmäßig auf 1 festgelegt. Dies bezieht sich auf die erste logische Zeile in einem mehrzeiligen Puffer.

Die tatsächliche Anzahl von Zeilen, die aus der mehrzeiligen Zeile gelöscht werden sollen, wird als Differenz zwischen der aktuellen logischen Zeilennummer und dem angegebenen numerischen Argument berechnet, das daher negativ sein kann. Daher der _relative_ Teil des Methoden namens.

- VI-Befehlsmodus: `<d,g,g>`

### <a name="deletenextlines"></a>Deletenextlines

Löscht die aktuelle logische Linie und die nächsten angeforderten logischen Zeilen in einem mehrzeiligen Puffer.

- VI-Befehlsmodus: `<d,j>`

### <a name="deletelinetofirstchar"></a>Delta-inetyp

Löscht das erste nicht leere Zeichen der aktuellen logischen Zeile in einem mehrzeiligen Puffer.

- VI-Befehlsmodus: `<d,^>`

### <a name="deletetoend"></a>Deletegeend

Bis zum Ende der Zeile löschen.

- VI-Befehlsmodus: `<D>` , `<d,$>`

### <a name="deleteword"></a>DeleteWord

Löschen Sie das nächste Wort.

- VI-Befehlsmodus: `<d,w>`

### <a name="forwarddeleteinput"></a>Forwarddelta eteinput

Wie bei "killline" wird Text vom Punkt bis zum Ende der Eingabe gelöscht, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.

- Befehl: `<Ctrl+End>`
- VI-Einfügemodus: `<Ctrl+End>`
- VI-Befehlsmodus: `<Ctrl+End>`

### <a name="forwarddeleteline"></a>Forwarddelta-Eline

Löscht Text vom Punkt bis zum Ende der aktuellen logischen Zeile, legt den gelöschten Text jedoch nicht im Kill-Ring ab.

- Funktion ist nicht gebunden

### <a name="insertlineabove"></a>Insertlineoberhalb

Oberhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet. Der Cursor wechselt zum Anfang der neuen Zeile.

- Befehl: `<Ctrl+Enter>`

### <a name="insertlinebelow"></a>Insertlinebelow

Unterhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet. Der Cursor wechselt zum Anfang der neuen Zeile.

- Befehl: `<Shift+Ctrl+Enter>`

### <a name="invertcase"></a>Invertieren

Kehrt die Groß-/Kleinschreibung des aktuellen Zeichens um und wechselt zum nächsten.

- VI-Befehlsmodus: `<~>`

### <a name="killline"></a>Killline

Löschen Sie die Eingabe vom Cursor bis zum Ende der Eingabe. Der gelöschte Text wird in den Kill-Ring eingefügt.

- Ansehen `<Ctrl+k>`

### <a name="killregion"></a>Killregion

Beenden Sie den Text zwischen dem Cursor und der Markierung.

- Die Bindung der Funktion ist aufgehoben.

### <a name="killword"></a>Killword

Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts. Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht. Der gelöschte Text wird in den Kill-Ring eingefügt.

- Cmd: `<Alt+d>` , `<Ctrl+Delete>`
- Emacs: `<Alt+d>` , `<Escape,d>`
- VI-Einfügemodus: `<Ctrl+Delete>`
- VI-Befehlsmodus: `<Ctrl+Delete>`

### <a name="paste"></a>Einfügen

Fügen Sie Text aus der Zwischenablage des Systems ein.

- Cmd: `<Ctrl+v>` , `<Shift+Insert>`
- VI-Einfügemodus: `<Ctrl+v>`
- VI-Befehlsmodus: `<Ctrl+v>`

> [!IMPORTANT]
> Wenn Sie die Funktion **Einfügen** verwenden, wird der gesamte Inhalt des Zwischenablage Puffers in den Eingabepuffer von psread Line eingefügt. Der Eingabepuffer wird dann an den PowerShell-Parser übergeben. Eingaben, die mithilfe der **Rechtsklick-Einfügemethode** der Konsolenanwendung eingefügt werden, werden jeweils ein Zeichen in den Eingabepuffer kopiert. Der Eingabepuffer wird an den Parser übergeben, wenn ein Zeilen vorzeichensatz kopiert wird. Daher wird die Eingabe jeweils Zeilen gleich analysiert. Der Unterschied zwischen den Methoden zum Einfügen führt zu einem anderen Ausführungs Verhalten.

### <a name="pasteafter"></a>Pasteafter

Fügen Sie die Zwischenablage nach dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.

- VI-Befehlsmodus: `<p>`

### <a name="pastebefore"></a>Pastebefore

Fügen Sie die Zwischenablage vor dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.

- VI-Befehlsmodus: `<P>`

### <a name="prependandaccept"></a>Prepdandaccept

Fügen Sie ein "#" vorangesteht, und akzeptieren Sie die Zeile.

- VI-Befehlsmodus: `<#>`

### <a name="redo"></a>Wiederholen

Rückgängig machen.

- Befehl: `<Ctrl+y>`
- VI-Einfügemodus: `<Ctrl+y>`
- VI-Befehlsmodus: `<Ctrl+y>`

### <a name="repeatlastcommand"></a>Repeatlastcommand

Wiederholen Sie die letzte Textänderung.

- VI-Befehlsmodus: `<.>`

### <a name="revertline"></a>Revertline

Kehrt alle Eingaben in die aktuelle Eingabe um.

- Befehl: `<Escape>`
- Emacs: `<Alt+r>` , `<Escape,r>`

### <a name="shellbackwardkillword"></a>Shellbackwardkillword

Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor. Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht. Der gelöschte Text wird in den Kill-Ring eingefügt.

Die Bindung der Funktion ist aufgehoben.

### <a name="shellkillword"></a>Shellkillword

Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts. Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht. Der gelöschte Text wird in den Kill-Ring eingefügt.

Die Bindung der Funktion ist aufgehoben.

### <a name="swapcharacters"></a>Austausch Zeichen

Tauschen Sie das aktuelle und das aktuelle Zeichen aus.

- Ansehen `<Ctrl+t>`
- VI-Einfügemodus: `<Ctrl+t>`
- VI-Befehlsmodus: `<Ctrl+t>`

### <a name="undo"></a>Rückgängig

Rückgängigmachen einer vorherigen Bearbeitung.

- Befehl: `<Ctrl+z>`
- Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`
- VI-Einfügemodus: `<Ctrl+z>`
- VI-Befehlsmodus: `<Ctrl+z>` , `<u>`

### <a name="undoall"></a>Nicht doall

Alle vorherigen Änderungen für die Zeile rückgängig machen.

- VI-Befehlsmodus: `<U>`

### <a name="unixwordrubout"></a>Unixwordrubout

Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor. Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht. Der gelöschte Text wird in den Kill-Ring eingefügt.

- Ansehen `<Ctrl+w>`

### <a name="validateandacceptline"></a>Validateandakzeptline

Versuchen Sie, die aktuelle Eingabe auszuführen. Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.

- Ansehen `<Ctrl+m>`

### <a name="viacceptline"></a>Viakzeptline

Akzeptieren Sie die Zeile, und wechseln Sie zum Einfügemodus.

- VI-Befehlsmodus: `<Enter>`

### <a name="viacceptlineorexit"></a>Viakzeptlineorexit

Wie deletecharorexit im Emacs-Modus, akzeptiert jedoch die Zeile, anstatt ein Zeichen zu löschen.

- VI-Einfügemodus: `<Ctrl+d>`
- VI-Befehlsmodus: `<Ctrl+d>`

### <a name="viappendline"></a>Viappendline

Unterhalb der aktuellen Zeile wird eine neue Zeile eingefügt.

- VI-Befehlsmodus: `<o>`

### <a name="vibackwarddeleteglob"></a>Vibackwarddeleteglob

Löscht das vorherige Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.

- VI-Befehlsmodus: `<d,B>`

### <a name="vibackwardglob"></a>Vibackwardglob

Verschiebt den Cursor zurück an den Anfang des vorherigen Worts, wobei nur Leerraum als Trennzeichen verwendet wird.

- VI-Befehlsmodus: `<B>`

### <a name="videletebrace"></a>Videletebrace

Suchen Sie nach der passenden geschweiften Klammer, Klammer oder eckigen Klammer, und löschen Sie alle Inhalte in, einschließlich der geschweiften Klammer.

- VI-Befehlsmodus: `<d,%>`

### <a name="videleteendofglob"></a>Videleteendobglob

Bis zum Ende des Worts löschen.

- VI-Befehlsmodus: `<d,E>`

### <a name="videleteglob"></a>Videleteglob

Löschen Sie den nächsten globmuster (Leerzeichen mit Trennzeichen).

- VI-Befehlsmodus: `<d,W>`

### <a name="videletetobeforechar"></a>Videletetobeforechar

Löscht bis zum angegebenen Zeichen.

- VI-Befehlsmodus: `<d,t>`

### <a name="videletetobeforecharbackward"></a>Videletebackbeforecharrückwärts

Löscht bis zum angegebenen Zeichen.

- VI-Befehlsmodus: `<d,T>`

### <a name="videletetochar"></a>Videleteto Char

Löscht bis zum angegebenen Zeichen.

- VI-Befehlsmodus: `<d,f>`

### <a name="videletetocharbackward"></a>Videletebackcharrückwärts

Löscht rückwärts bis zum angegebenen Zeichen.

- VI-Befehlsmodus: `<d,F>`

### <a name="viinsertatbegining"></a>Viinsertatbeginung

Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Anfang der Zeile.

- VI-Befehlsmodus: `<I>`

### <a name="viinsertatend"></a>Viinsertatend

Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Ende der Zeile.

- VI-Befehlsmodus: `<A>`

### <a name="viinsertline"></a>Viinsertline

Oberhalb der aktuellen Zeile wird eine neue Zeile eingefügt.

- VI-Befehlsmodus: `<O>`

### <a name="viinsertwithappend"></a>Viinsertwithappend

An der aktuellen Zeilen Position anfügen.

- VI-Befehlsmodus: `<a>`

### <a name="viinsertwithdelete"></a>Viinsertwithdelete

Löschen Sie das aktuelle Zeichen und wechseln Sie in den Einfügemodus.

- VI-Befehlsmodus: `<s>`

### <a name="vijoinlines"></a>Vijoinlines

Verbindet die aktuelle Zeile und die nächste Zeile.

- VI-Befehlsmodus: `<J>`

### <a name="vireplaceline"></a>Vireplaceline

Löschen Sie die gesamte Befehlszeile.

- VI-Befehlsmodus: `<S>` , `<c,c>`

### <a name="vireplacetobeforechar"></a>Vireplacetobeforechar

Ersetzt bis zum angegebenen Zeichen.

- VI-Befehlsmodus: `<c,t>`

### <a name="vireplacetobeforecharbackward"></a>Vireplaceumbeforecharrückwärts

Ersetzt bis zum angegebenen Zeichen.

- VI-Befehlsmodus: `<c,T>`

### <a name="vireplacetochar"></a>Vireplaceumchar

Löscht bis zum angegebenen Zeichen.

- VI-Befehlsmodus: `<c,f>`

### <a name="vireplacetocharbackward"></a>Vireplacebackcharrückwärts

Ersetzt bis zum angegebenen Zeichen.

- VI-Befehlsmodus: `<c,F>`

### <a name="viyankbeginningofline"></a>Viyankbeginningosline

Yank vom Anfang des Puffers bis zum Cursor.

- VI-Befehlsmodus: `<y,0>`

### <a name="viyankendofglob"></a>Viyankendobglob

Yank vom Cursor bis zum Ende des Worts (s).

- VI-Befehlsmodus: `<y,E>`

### <a name="viyankendofword"></a>Viyankendof

Yank vom Cursor bis zum Ende des Worts (s).

- VI-Befehlsmodus: `<y,e>`

### <a name="viyankleft"></a>Viyankleft

Die Zeichen werden Links vom Cursor angezeigt.

- VI-Befehlsmodus: `<y,h>`

### <a name="viyankline"></a>Viyankline

Den gesamten Puffer.

- VI-Befehlsmodus: `<y,y>`

### <a name="viyanknextglob"></a>Viyanknextglob

Yank vom Cursor bis zum Anfang des nächsten Worts (n).

- VI-Befehlsmodus: `<y,W>`

### <a name="viyanknextword"></a>Viyanknextword

Das Wort (e) nach dem Cursor.

- VI-Befehlsmodus: `<y,w>`

### <a name="viyankpercent"></a>Viyankprozent

Von der entsprechenden geschweiften geschweifter Klammer.

- VI-Befehlsmodus: `<y,%>`

### <a name="viyankpreviousglob"></a>Viyankpreviousglob

Yank von Anfang des Worts bis zum Cursor.

- VI-Befehlsmodus: `<y,B>`

### <a name="viyankpreviousword"></a>Viyankpreviousword

Das Wort (e) vor dem Cursor.

- VI-Befehlsmodus: `<y,b>`

### <a name="viyankright"></a>Viyankright

(E) unter und rechts vom Cursor.

- VI-Befehlsmodus: `<y,l>` , `<y,Spacebar>`

### <a name="viyanktoendofline"></a>Viyanktoendosline

Yank vom Cursor bis zum Ende des Puffers.

- VI-Befehlsmodus: `<y,$>`

### <a name="viyanktofirstchar"></a>Viyanktofirstchar

Yank vom ersten Zeichen, das kein Leerzeichen ist, bis zum Cursor.

- VI-Befehlsmodus: `<y,^>`

### <a name="yank"></a>Yank

Fügen Sie der Eingabe den zuletzt beendeten Text hinzu.

- Ansehen `<Ctrl+y>`

### <a name="yanklastarg"></a>Yanklastarg

Das letzte Argument aus der vorherigen Verlaufs Zeile. Mit einem Argument verhält sich das erste Mal, wenn es aufgerufen wird, wie yankntharg. Wenn Sie mehrmals aufgerufen wird, durchläuft Sie stattdessen den Verlauf, und arg legt die Richtung fest (negative Umkehrung der Richtung).

- Befehl: `<Alt+.>`
- Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`

### <a name="yankntharg"></a>Yankntharg

Yank das erste Argument (nach dem Befehl) aus der vorherigen Verlaufs Zeile.
Bei einem Argument wird das n-te Argument (beginnend bei 0), wenn das Argument negativ ist, mit dem letzten Argument beginnen.

- Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`

### <a name="yankpop"></a>Yankpop

Wenn der vorherige Vorgang "Yank" oder "yankpop" war, ersetzen Sie den zuvor angezeigten Text durch den nächsten ausgeblendeten Text aus dem Kill-Ring.

- Emacs: `<Alt+y>` , `<Escape,y>`

## <a name="cursor-movement-functions"></a>Cursor Verschiebungs Funktionen

### <a name="backwardchar"></a>Backwardchar

Bewegen Sie den Cursor um ein Zeichen nach links. Dadurch kann der Cursor in die vorherige Zeile der mehrzeiligen Eingabe verschoben werden.

- Befehl: `<LeftArrow>`
- Emacs: `<LeftArrow>` , `<Ctrl+b>`

### <a name="backwardword"></a>Backwardword

Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt. Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.

- Befehl: `<Ctrl+LeftArrow>`
- Emacs: `<Alt+b>` , `<Escape,b>`
- VI-Einfügemodus: `<Ctrl+LeftArrow>`
- VI-Befehlsmodus: `<Ctrl+LeftArrow>`

### <a name="beginningofline"></a>Beginningosline

Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Anfang der aktuellen Zeile oder, wenn Sie sich bereits am Anfang der Zeile befinden, bis zum Anfang der Eingabe. Wenn die Eingabe über eine einzelne Zeile verfügt, wechseln Sie zum Anfang der Eingabe.

- Befehl: `<Home>`
- Emacs: `<Home>` , `<Ctrl+a>`
- VI-Einfügemodus: `<Home>`
- VI-Befehlsmodus: `<Home>`

### <a name="endofline"></a>Endosline

Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Ende der aktuellen Zeile, oder wechseln Sie, wenn Sie sich bereits am Ende der Zeile befindet, bis zum Ende der Eingabe. Wenn die Eingabe über eine einzelne Zeile verfügt, verschieben Sie das Ende der Eingabe.

- Befehl: `<End>`
- Emacs: `<End>` , `<Ctrl+e>`
- VI-Einfügemodus: `<End>`

### <a name="forwardchar"></a>Forwardchar

Bewegen Sie den Cursor um ein Zeichen nach rechts. Dadurch kann der Cursor in die nächste Zeile der mehrzeiligen Eingabe verschoben werden.

- Befehl: `<RightArrow>`
- Emacs: `<RightArrow>` , `<Ctrl+f>`

### <a name="forwardword"></a>Forwardword

Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts. Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.

- Emacs: `<Alt+f>` , `<Escape,f>`

### <a name="gotobrace"></a>GotoBrace

Wechseln Sie zur passenden geschweiften Klammer, Klammer oder eckigen Klammer.

- Befehl: `<Ctrl+]>`
- VI-Einfügemodus: `<Ctrl+]>`
- VI-Befehlsmodus: `<Ctrl+]>`

### <a name="gotocolumn"></a>Goum Column

Wechseln Sie in die Spalte, die von arg angegeben wird.

- VI-Befehlsmodus: `<|>`

### <a name="gotofirstnonblankofline"></a>Gostarfirstnonblankosline

Bewegen Sie den Cursor auf das erste nicht leere Zeichen in der Zeile.

- VI-Befehlsmodus: `<^>` , `<_>`

### <a name="movetoendofline"></a>"MUVE"

Bewegen Sie den Cursor an das Ende der Eingabe.

- VI-Befehlsmodus: `<End>` , `<$>`

### <a name="nextline"></a>Nextline

Bewegen Sie den Cursor in die nächste Zeile.

- Die Bindung der Funktion ist aufgehoben.

### <a name="nextword"></a>Nextword

Bewegen Sie den Cursor an den Anfang des nächsten Worts. Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.

- Befehl: `<Ctrl+RightArrow>`
- VI-Einfügemodus: `<Ctrl+RightArrow>`
- VI-Befehlsmodus: `<Ctrl+RightArrow>`

### <a name="nextwordend"></a>Nextwordend

Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts. Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.

- VI-Befehlsmodus: `<e>`

### <a name="previousline"></a>Previousline

Bewegen Sie den Cursor in die vorherige Zeile.

- Die Bindung der Funktion ist aufgehoben.

### <a name="shellbackwardword"></a>Shellbackwardword

Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt. Wortgrenzen werden durch PowerShell-Token definiert.

- Die Bindung der Funktion ist aufgehoben.

### <a name="shellforwardword"></a>Shellforwardword

Bewegen Sie den Cursor an den Anfang des nächsten Worts. Wortgrenzen werden durch PowerShell-Token definiert.

- Die Bindung der Funktion ist aufgehoben.

### <a name="shellnextword"></a>Shellnextword

Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts. Wortgrenzen werden durch PowerShell-Token definiert.

- Die Bindung der Funktion ist aufgehoben.

### <a name="vibackwardchar"></a>Vibackwardchar

Bewegen Sie den Cursor um ein Zeichen nach links im VI-Bearbeitungsmodus. Dadurch kann der Cursor in die vorherige Zeile der mehrzeiligen Eingabe verschoben werden.

- VI-Einfügemodus: `<LeftArrow>`
- VI-Befehlsmodus: `<LeftArrow>` , `<Backspace>` , `<h>`

### <a name="vibackwardword"></a>Vibackwardword

Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt. Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.

- VI-Befehlsmodus: `<b>`

### <a name="viforwardchar"></a>Viforwardchar

Bewegen Sie den Cursor um ein Zeichen nach rechts im VI-Bearbeitungsmodus. Dadurch kann der Cursor in die nächste Zeile der mehrzeiligen Eingabe verschoben werden.

- VI-Einfügemodus: `<RightArrow>`
- VI-Befehlsmodus: `<RightArrow>` , `<Spacebar>` , `<l>`

### <a name="viendofglob"></a>Viendobglob

Verschiebt den Cursor an das Ende des Worts und verwendet nur Leerzeichen als Trennzeichen.

- VI-Befehlsmodus: `<E>`

### <a name="viendofpreviousglob"></a>Viendof previousglob

Wechselt zum Ende des vorherigen Worts, wobei nur Leerraum als Wort Trennzeichen verwendet wird.

- Die Bindung der Funktion ist aufgehoben.

### <a name="vigotobrace"></a>Vigoumbrace

Ähnelt gotobrace, aber ist Zeichen basiert anstelle von tokenbasiert.

- VI-Befehlsmodus: `<%>`

### <a name="vinextglob"></a>Vinextglob

Wechselt zum nächsten Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.

- VI-Befehlsmodus: `<W>`

### <a name="vinextword"></a>Vinextword

Bewegen Sie den Cursor an den Anfang des nächsten Worts. Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.

- VI-Befehlsmodus: `<w>`

## <a name="history-functions"></a>Verlaufs Funktionen

### <a name="beginningofhistory"></a>Beginningof History

Wechselt zum ersten Element im Verlauf.

- Ansehen `<Alt+<>`

### <a name="clearhistory"></a>ClearHistory

Löscht den Verlauf in psleline. Dies wirkt sich nicht auf den PowerShell-Verlauf aus.

- Befehl: `<Alt+F7>`

### <a name="endofhistory"></a>EndOf History

Wechselt zum letzten Element (der aktuellen Eingabe) im Verlauf.

- Ansehen `<Alt+>>`

### <a name="forwardsearchhistory"></a>Forwardsearchhistory

Führt eine inkrementelle Forward-Suche im Verlauf durch

- Befehl: `<Ctrl+s>`
- Ansehen `<Ctrl+s>`

### <a name="historysearchbackward"></a>Historysearchrückwärts

Ersetzen Sie die aktuelle Eingabe durch das Element "Previous" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.

- Befehl: `<F8>`

### <a name="historysearchforward"></a>Historysearchforward

Ersetzen Sie die aktuelle Eingabe durch das Element "Next" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.

- Befehl: `<Shift+F8>`

### <a name="nexthistory"></a>Nexthistory

Ersetzen Sie die aktuelle Eingabe durch das "Next"-Element aus dem psleline-Verlauf.

- Befehl: `<DownArrow>`
- Emacs: `<DownArrow>` , `<Ctrl+n>`
- VI-Einfügemodus: `<DownArrow>`
- VI-Befehlsmodus: `<DownArrow>` , `<j>` , `<+>`

### <a name="previoushistory"></a>Previoushistory

Ersetzen Sie die aktuelle Eingabe durch das "Previous"-Element aus dem psleline-Verlauf.

- Befehl: `<UpArrow>`
- Emacs: `<UpArrow>` , `<Ctrl+p>`
- VI-Einfügemodus: `<UpArrow>`
- VI-Befehlsmodus: `<UpArrow>` , `<k>` , `<->`

### <a name="reversesearchhistory"></a>Reversesearchhistory

Führt eine inkrementelle Rückwärtssuche über den Verlauf durch

- Befehl: `<Ctrl+r>`
- Ansehen `<Ctrl+r>`

### <a name="visearchhistorybackward"></a>Visearchhistoryrückwärts

Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.

- VI-Einfügemodus: `<Ctrl+r>`
- VI-Befehlsmodus: `</>` , `<Ctrl+r>`

## <a name="completion-functions"></a>Vervollständigungs Funktionen

### <a name="complete"></a>Abgeschlossen

Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen. Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet. Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.

- Ansehen `<Tab>`

### <a name="menucomplete"></a>MenuComplete

Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen. Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet. Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.

- Cmd: `<Ctrl+@>` , `<Ctrl+Spacebar>`
- Ansehen `<Ctrl+Spacebar>`

### <a name="possiblecompletions"></a>Possiblecompletions

Hiermit wird die Liste der möglichen Vervollständigungen angezeigt.

- Ansehen `<Alt+=>`
- VI-Einfügemodus: `<Ctrl+Spacebar>`
- VI-Befehlsmodus: `<Ctrl+Spacebar>`

### <a name="tabcompletenext"></a>Tabcompletenext

Es wurde versucht, den Text, der den Cursor umgibt, mit der nächsten verfügbaren Beendigung abzuschließen.

- Befehl: `<Tab>`
- VI-Befehlsmodus: `<Tab>`

### <a name="tabcompleteprevious"></a>Tabcompleteprevious

Versuchen Sie, den Text, der den Cursor umgibt, mit dem vorherigen verfügbaren Abschluss abzuschließen.

- Befehl: `<Shift+Tab>`
- VI-Befehlsmodus: `<Shift+Tab>`

### <a name="vitabcompletenext"></a>Vitabcompletenext

Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompletenext auf.

- VI-Einfügemodus: `<Tab>`

### <a name="vitabcompleteprevious"></a>Vitabcompleteprevious

Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompleteprevious auf.

- VI-Einfügemodus: `<Shift+Tab>`

## <a name="prediction-functions"></a>Vorhersagefunktionen

### <a name="acceptnextsuggestionword"></a>Akzeptnextsuggestionword

Wenn Sie `InlineView` als Ansichts Stil für die Vorhersage verwenden, akzeptieren Sie das nächste Wort des Inline Vorschlags.

- Die Bindung der Funktion ist aufgehoben.

### <a name="acceptsuggestion"></a>Accept-Vorschlag

Wenn Sie `InlineView` als Ansichts Stil für Vorhersagen verwenden, müssen Sie den aktuellen Inline Vorschlag akzeptieren.

- Die Bindung der Funktion ist aufgehoben.

### <a name="nextsuggestion"></a>Nextvorschlag

Wenn Sie `ListView` als Ansichts Stil für die Vorhersage verwenden, navigieren Sie zum nächsten Vorschlag in der Liste.

- Die Bindung der Funktion ist aufgehoben.

### <a name="previoussuggestion"></a>Previousvorschlag

Wenn Sie `ListView` als Ansichts Stil für die Vorhersage verwenden, navigieren Sie zu dem vorherigen Vorschlag in der Liste.

- Die Bindung der Funktion ist aufgehoben.

### <a name="switchpredictionview"></a>Switchvorhertionview

Ändern Sie den Ansichts Stil für die Vorhersage zwischen `InlineView` und `ListView` .

- Befehl: `<F2>`

## <a name="miscellaneous-functions"></a>Sonstige Funktionen

### <a name="capturescreen"></a>CaptureScreen

Interaktive Bildschirmaufnahme starten-nach oben/nach-unten-Pfeile Select Lines, Enter kopiert markierten Text in die Zwischenablage als Text und HTML.

- Die Bindung der Funktion ist aufgehoben.

### <a name="clearscreen"></a>ClearScreen

Löschen Sie den Bildschirm, und zeichnen Sie die aktuelle Zeile am oberen Rand des Bildschirms.

- Befehl: `<Ctrl+l>`
- Ansehen `<Ctrl+l>`
- VI-Einfügemodus: `<Ctrl+l>`
- VI-Befehlsmodus: `<Ctrl+l>`

### <a name="digitargument"></a>Digitargument

Starten Sie ein neues Ziffern Argument, das an andere Funktionen übergeben werden soll.

- Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`
- Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`
- VI-Befehlsmodus: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`

### <a name="invokeprompt"></a>Invokeprompt

Löscht die aktuelle Eingabeaufforderung und ruft die prompt-Funktion auf, um die Eingabeaufforderung erneut anzuzeigen. Nützlich für benutzerdefinierte Schlüssel Handler, die den Zustand ändern, z. b. Ändern des aktuellen Verzeichnisses.

- Die Bindung der Funktion ist aufgehoben.

### <a name="scrolldisplaydown"></a>Scrolldisplaydown

Scrollen Sie in der Anzeige einen Bildschirm nach unten.

- Befehl: `<PageDown>`
- Ansehen `<PageDown>`

### <a name="scrolldisplaydownline"></a>Scrolldisplaydownline

Scrollen Sie in der Anzeige um eine Zeile nach unten.

- Befehl: `<Ctrl+PageDown>`
- Ansehen `<Ctrl+PageDown>`

### <a name="scrolldisplaytocursor"></a>Scrolldisplaytcursor

Scrollen Sie in der Anzeige zum Cursor.

- Ansehen `<Ctrl+End>`

### <a name="scrolldisplaytop"></a>Scrolldisplaytop

Scrollen Sie in der Anzeige nach oben.

- Ansehen `<Ctrl+Home>`

### <a name="scrolldisplayup"></a>Scrolldisplayup

Scrollen Sie einen Bildschirm nach oben.

- Befehl: `<PageUp>`
- Ansehen `<PageUp>`

### <a name="scrolldisplayupline"></a>Scrolldisplayupline

Scrollen Sie in der Anzeige um eine Zeile nach oben.

- Befehl: `<Ctrl+PageUp>`
- Ansehen `<Ctrl+PageUp>`

### <a name="selfinsert"></a>Selfinsert

Fügen Sie den Schlüssel ein.

- Die Bindung der Funktion ist aufgehoben.

### <a name="showcommandhelp"></a>Showcommandhelp

Bietet eine Ansicht der vollständigen Cmdlet-Hilfe. Wenn sich der Cursor am Ende eines vollständig erweiterten Parameters befindet, wird durch das Drücken der `<F1>` Taste die Anzeige der Hilfe an der Position dieses Parameters positioniert.

Die Hilfe wird mithilfe eines Pager von **Microsoft. PowerShell. Pager** auf einem alternativen Bildschirm Puffer angezeigt. Wenn Sie den Pager beenden, werden Sie auf dem ursprünglichen Bildschirm an die ursprüngliche Cursorposition zurückgegeben. Dieser Pager funktioniert nur in modernen Terminalanwendungen wie z. b. [Windows-Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701).

- Befehl: `<F1>`
- Ansehen `<F1>`
- VI-Einfügemodus: `<F1>`
- VI-Befehlsmodus: `<F1>`

### <a name="showkeybindings"></a>Showkeybindungen

Alle gebundenen Schlüssel anzeigen.

- Befehl: `<Ctrl+Alt+?>`
- Ansehen `<Ctrl+Alt+?>`
- VI-Einfügemodus: `<Ctrl+Alt+?>`

### <a name="showparameterhelp"></a>Showparameterhelp

Bietet dynamische Hilfe für Parameter, indem Sie unter der aktuellen Befehlszeile wie angezeigt wird `MenuComplete` . Der Cursor muss sich am Ende des vollständig erweiterten Parameter namens befinden, wenn Sie die `<Alt+h>` Taste drücken.

- Befehl: `<Alt+h>`
- Ansehen `<Alt+h>`
- VI-Einfügemodus: `<Alt+h>`
- VI-Befehlsmodus: `<Alt+h>`

### <a name="vicommandmode"></a>Vicommandmode

Wechseln Sie in den aktuellen Betriebsmodus von Vi-Insert zu VI-Command.

- VI-Einfügemodus: `<Escape>`

### <a name="vidigitargumentinchord"></a>Vidigitargumentinchord

Startet ein neues Ziffern Argument, das in einem der VI-Akkorde an andere Funktionen übergeben werden soll.

- Die Bindung der Funktion ist aufgehoben.

### <a name="vieditvisually"></a>Vieditvisuell

Bearbeiten Sie die Befehlszeile in einem Text-Editor, der durch $ENV: Editor oder $env: Visual angegeben wird.

- Ansehen `<Ctrl+x,Ctrl+e>`
- VI-Befehlsmodus: `<v>`

### <a name="viexit"></a>Viexit

Beendet die Shell.

- Die Bindung der Funktion ist aufgehoben.

### <a name="viinsertmode"></a>Viinsertmode

Wechselt in den Einfügemodus.

- VI-Befehlsmodus: `<i>`

### <a name="whatiskey"></a>Whatiskey

Lesen Sie einen Schlüssel, und teilen Sie mir mit, wofür der Schlüssel gebunden ist.

- Befehl: `<Alt+?>`
- Ansehen `<Alt+?>`

## <a name="selection-functions"></a>Auswahl Funktionen

### <a name="exchangepointandmark"></a>Exchangepointandmark

Der Cursor wird an der Position der Markierung platziert, und die Markierung wird an die Position des Cursors verschoben.

- Ansehen `<Ctrl+x,Ctrl+x>`

### <a name="selectall"></a>SelectAll

Wählen Sie die gesamte Zeile aus.

- Befehl: `<Ctrl+a>`

### <a name="selectbackwardchar"></a>Selectbackwardchar

Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Zeichen einschließt.

- Befehl: `<Shift+LeftArrow>`
- Ansehen `<Shift+LeftArrow>`

### <a name="selectbackwardsline"></a>Selectbackwardsline

Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an den Anfang der Zeile eingeschlossen wird.

- Befehl: `<Shift+Home>`
- Ansehen `<Shift+Home>`

### <a name="selectbackwardword"></a>Selectbackwardword

Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort enthält.

- Befehl: `<Shift+Ctrl+LeftArrow>`
- Ansehen `<Alt+B>`

### <a name="selectcommandargument"></a>Selectcommandargument

Erstellen Sie die visuelle Auswahl der Befehlsargumente. Die Auswahl von Argumenten wird in einem Skriptblock festgelegt. Basierend auf der Cursorposition wird vom innersten Skriptblock nach dem äußersten Skriptblock gesucht und beendet, wenn Argumente in einem Skriptblock Bereich gefunden werden.

Diese Funktion berücksichtigt digitargument. Die positiven oder negativen Argument Werte werden als vorwärts-oder rückwärts Offsets vom aktuell ausgewählten Argument oder von der aktuellen Cursorposition, wenn kein Argument ausgewählt ist, behandelt.

- Befehl: `<Alt+a>`
- Ansehen `<Alt+a>`

### <a name="selectforwardchar"></a>Selectforwardchar

Passen Sie die aktuelle Auswahl an, um das nächste Zeichen einzuschließen.

- Befehl: `<Shift+RightArrow>`
- Ansehen `<Shift+RightArrow>`

### <a name="selectforwardword"></a>Selectforwardword

Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mit forwardword einschließt.

- Ansehen `<Alt+F>`

### <a name="selectline"></a>SelectLine

Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an das Ende der Zeile eingeschlossen wird.

- Befehl: `<Shift+End>`
- Ansehen `<Shift+End>`

### <a name="selectnextword"></a>Selectnextword

Passen Sie die aktuelle Auswahl an das nächste Wort an.

- Befehl: `<Shift+Ctrl+RightArrow>`

### <a name="selectshellbackwardword"></a>Selectshellbackwardword

Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort mithilfe von shellbackwardword einschließt.

- Die Bindung der Funktion ist aufgehoben.

### <a name="selectshellforwardword"></a>Selectshellforwardword

Passen Sie die aktuelle Auswahl so an, dass das nächste Wort mithilfe von shellforwardword eingeschlossen wird.

- Die Bindung der Funktion ist aufgehoben.

### <a name="selectshellnextword"></a>Selectshellnextword

Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mithilfe von shellnextword einschließt.

- Die Bindung der Funktion ist aufgehoben.

### <a name="setmark"></a>Setmark

Markieren Sie die aktuelle Position des Cursors für die Verwendung in einem nachfolgenden Bearbeitungs Befehl.

- Ansehen `<Ctrl+@>`

## <a name="predictive-intellisense-functions"></a>Predictive IntelliSense-Funktionen

> [!NOTE]
> Predictive IntelliSense muss aktiviert werden, damit diese Funktionen verwendet werden können.

### <a name="acceptnextwordsuggestion"></a>Accept-nextwordsuggestion

Akzeptiert das nächste Wort des Inline Vorschlags aus Predictive IntelliSense.
Diese Funktion kann mit <kbd>STRG</kbd> + <kbd>F</kbd> gebunden werden, indem der folgende Befehl ausgeführt wird.

```powershell
Set-PSReadLineKeyHandler -Chord "Ctrl+f" -Function ForwardWord
```

### <a name="acceptsuggestion"></a>Accept-Vorschlag

Akzeptiert den aktuellen Inline Vorschlag von Predictive IntelliSense durch Drücken von <kbd>RIGHTARROW</kbd> , wenn sich der Cursor am Ende der aktuellen Zeile befindet.

## <a name="search-functions"></a>Suchfunktionen

### <a name="charactersearch"></a>Merkmal Suche

Lesen Sie ein Zeichen, und suchen Sie nach dem nächsten Vorkommen dieses Zeichens.
Wenn ein Argument angegeben ist, suchen Sie nach vorn (oder rückwärts, wenn negativ) für das n-te vorkommen.

- Befehl: `<F3>`
- Ansehen `<Ctrl+]>`
- VI-Einfügemodus: `<F3>`
- VI-Befehlsmodus: `<F3>`

### <a name="charactersearchbackward"></a>Merkmal searchrückwärts

Liest ein Zeichen und sucht rückwärts nach dem nächsten Vorkommen dieses Zeichens. Wenn ein Argument angegeben wird, suchen Sie nach hinten (oder vorwärts, wenn negativ).

- Befehl: `<Shift+F3>`
- Ansehen `<Ctrl+Alt+]>`
- VI-Einfügemodus: `<Shift+F3>`
- VI-Befehlsmodus: `<Shift+F3>`

### <a name="repeatlastcharsearch"></a>Repeatlastcharsearch

Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche.

- VI-Befehlsmodus: `<;>`

### <a name="repeatlastcharsearchbackwards"></a>Repeatlastcharsearchabwärts

Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche, aber in umgekehrter Richtung.

- VI-Befehlsmodus: `<,>`

### <a name="repeatsearch"></a>Repeatsearch

Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.

- VI-Befehlsmodus: `<n>`

### <a name="repeatsearchbackward"></a>Repeatsearchrückwärts

Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.

- VI-Befehlsmodus: `<N>`

### <a name="searchchar"></a>Searchchar

Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück. Dies ist für die Funktion 't verfügbar.

- VI-Befehlsmodus: `<f>`

### <a name="searchcharbackward"></a>Searchcharrückwärts

Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück. Dies ist für die Funktion 't verfügbar.

- VI-Befehlsmodus: `<F>`

### <a name="searchcharbackwardwithbackoff"></a>Searchcharbackwardwithbackoff

Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück. Dies ist für die Funktion 't verfügbar.

- VI-Befehlsmodus: `<T>`

### <a name="searchcharwithbackoff"></a>Searchcharwithbackoff

Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück. Dies ist für die Funktion 't verfügbar.

- VI-Befehlsmodus: `<t>`

### <a name="searchforward"></a>SearchForward

Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.

- VI-Einfügemodus: `<Ctrl+s>`
- VI-Befehlsmodus: `<?>` , `<Ctrl+s>`

## <a name="custom-key-bindings"></a>Benutzerdefinierte Tastenbindungen

Psread Line unterstützt benutzerdefinierte Tastenbindungen mithilfe des Cmdlets `Set-PSReadLineKeyHandler` . Die meisten benutzerdefinierten Tastenbindungen wenden eine der oben genannten Funktionen an, z. b.

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

Sie können einen ScriptBlock an einen Schlüssel binden. Der ScriptBlock kann beliebig viele Aufgaben erledigen. Einige nützliche Beispiele sind u.a.

- Bearbeiten der Befehlszeile
- Öffnen eines neuen Fensters (z. b. "Hilfe")
- Ändern der Verzeichnisse ohne Änderung der Befehlszeile

Der ScriptBlock empfängt zwei Argumente:

- `$key` -Ein **[ConsoleKeyInfo]** -Objekt, das der Schlüssel ist, der die benutzerdefinierte Bindung ausgelöst hat. Wenn Sie denselben ScriptBlock an mehrere Schlüssel binden und abhängig vom Schlüssel verschiedene Aktionen ausführen müssen, können Sie $Key überprüfen. Viele benutzerdefinierte Bindungen ignorieren dieses Argument.

- `$arg` -Ein beliebiges Argument. In den meisten Fällen ist dies ein ganzzahliges Argument, das der Benutzer von den Schlüsselbindungen digitargument übergibt. Wenn die Bindung keine Argumente akzeptiert, ist es sinnvoll, dieses Argument zu ignorieren.

Sehen wir uns ein Beispiel an, in dem eine Befehlszeile zum Verlauf hinzugefügt wird, ohne sie auszuführen. Dies ist nützlich, wenn Sie vergessen haben, etwas zu tun, ohne die Befehlszeile, die Sie bereits eingegeben haben, erneut eingeben zu müssen.

```powershell
$parameters = @{
    Key = 'Alt+w'
    BriefDescription = 'SaveInHistory'
    LongDescription = 'Save current line in history but do not execute'
    ScriptBlock = {
      param($key, $arg)   # The arguments are ignored in this example

      # GetBufferState gives us the command line (with the cursor position)
      $line = $null
      $cursor = $null
      [Microsoft.PowerShell.PSConsoleReadLine]::GetBufferState([ref]$line,
        [ref]$cursor)

      # AddToHistory saves the line in history, but does not execute it.
      [Microsoft.PowerShell.PSConsoleReadLine]::AddToHistory($line)

      # RevertLine is like pressing Escape.
      [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
  }
}
Set-PSReadLineKeyHandler @parameters
```

In der Datei `SamplePSReadLineProfile.ps1` , die im psread Line-Modul Ordner installiert ist, werden viele weitere Beispiele angezeigt.

Die meisten Tastenbindungen verwenden einige Hilfsfunktionen zum Bearbeiten der Befehlszeile.
Diese APIs werden im nächsten Abschnitt dokumentiert.

## <a name="custom-key-binding-support-apis"></a>APIs für die benutzerdefinierte Schlüssel Bindungs Unterstützung

Die folgenden Funktionen sind in Microsoft. PowerShell. psconsolereadline öffentlich, können jedoch nicht direkt an einen Schlüssel gebunden werden. Die meisten sind in benutzerdefinierten Tastenkombinationen nützlich.

```csharp
void AddToHistory(string command)
```

Fügen Sie eine Befehlszeile zum Verlauf hinzu, ohne sie auszuführen.

```csharp
void ClearKillRing()
```

Löschen Sie den Kill-Ring.  Dies wird größtenteils zum Testen verwendet.

```csharp
void Delete(int start, int length)
```

Löschen Sie die Längen Zeichen aus dem Startmenü.  Dieser Vorgang unterstützt rückgängig/wiederholen.

```csharp
void Ding()
```

Führen Sie die Aktion "Ding" basierend auf der Benutzereinstellung aus.

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

Diese beiden Funktionen rufen nützliche Informationen über den aktuellen Status des Eingabe Puffers ab.  Der erste wird häufiger für einfache Fälle verwendet.  Die zweite wird verwendet, wenn ihre Bindung einen fortgeschrittenen Vorgang mit der AST bewirkt.

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

Diese beiden Funktionen werden von verwendet `Get-PSReadLineKeyHandler` . Der erste wird verwendet, um alle Tastenbindungen zu erhalten. Die zweite wird verwendet, um bestimmte Tastenbindungen zu erhalten.

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

Diese Funktion wird von Get-PSReadLineOption verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

Wenn in der Befehlszeile keine Auswahl vorhanden ist, wird-1 sowohl in Start als auch in der Länge zurückgegeben. Wenn eine Auswahl in der Befehlszeile vorhanden ist, werden Start und Länge der Auswahl zurückgegeben.

```csharp
void Insert(char c)
void Insert(string s)
```

Fügen Sie am Cursor ein Zeichen oder eine Zeichenfolge ein.  Dieser Vorgang unterstützt rückgängig/wiederholen.

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

Dies ist der Haupteinstiegspunkt für psread Line. Sie unterstützt keine Rekursion und ist daher in einer benutzerdefinierten schlüsselbindung nicht nützlich.

```csharp
void RemoveKeyHandler(string[] key)
```

Diese Funktion wird von Remove-PSReadLineKeyHandler verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.

```csharp
void Replace(int start, int length, string replacement)
```

Ersetzen Sie einige der Eingaben. Dieser Vorgang unterstützt rückgängig/wiederholen. Dies wird als "Delete", gefolgt von INSERT, bevorzugt, da es als einzelne Aktion für "Rückgängig" behandelt wird.

```csharp
void SetCursorPosition(int cursor)
```

Bewegen Sie den Cursor in den angegebenen Offset. Cursor Bewegung wird nicht für Rückgängigmachen nachverfolgt.

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

Bei dieser Funktion handelt es sich um eine Hilfsmethode, die vom Cmdlet Set-psread lineoption verwendet wird. Sie kann jedoch für eine benutzerdefinierte schlüsselbindung nützlich sein, die eine Einstellung vorübergehend ändern möchte.

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

Diese Hilfsmethode wird für benutzerdefinierte Bindungen verwendet, die digitargument berücksichtigen. Ein typischer-Rückruf sieht wie folgt aus

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="notes"></a>Notizen

### <a name="command-history"></a>Befehlsverlauf

Psleseline verwaltet eine Verlaufs Datei, die alle Befehle und Daten enthält, die Sie in der Befehlszeile eingegeben haben. Dies kann vertrauliche Daten einschließlich Kenn Wörtern enthalten. Wenn Sie z. b. das `ConvertTo-SecureString` Cmdlet verwenden, wird das Kennwort als nur-Text in der Verlaufs Datei protokolliert. Die Verlaufs Dateien sind eine Datei mit dem Namen `$($host.Name)_history.txt` . Auf Windows-Systemen wird die Verlaufs Datei unter gespeichert `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` . Auf nicht-Windows-Systemen werden die Verlaufs Dateien unter `$env:XDG_DATA_HOME/powershell/PSReadLine` oder gespeichert `$env:HOME/.local/share/powershell/PSReadLine` .

### <a name="feedback--contributing-to-psreadline"></a>Feedback & zu psread Line beitragen

[Psread Line auf GitHub](https://github.com/PowerShell/PSReadLine)

Sie können auf der GitHub-Seite eine Pull Request einreichen oder Feedback einreichen.

## <a name="see-also"></a>Weitere Informationen

"Psread Line" wird stark von der GNU-Bibliothek für die [Zeilen](https://tiswww.case.edu/php/chet/readline/rltop.html) Übereinstimmung beeinflusst
