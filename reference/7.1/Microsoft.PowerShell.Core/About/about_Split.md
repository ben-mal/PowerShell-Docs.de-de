---
description: Erläutert, wie der Split-Operator verwendet wird, um eine oder mehrere Zeichen folgen in Teil Zeichenfolgen aufzuteilen.
Locale: en-US
ms.date: 03/30/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_split?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Split
ms.openlocfilehash: 1e731c04a232089d10191014cf8b84bb2b4e3b17
ms.sourcegitcommit: 4d6ed6f7d747a9bbb3fcfcf6c981c5aa8a973a08
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "106072732"
---
# <a name="about-split"></a>Informationen zur Aufteilung

## <a name="short-description"></a>KURZE BESCHREIBUNG
Erläutert, wie der Split-Operator verwendet wird, um eine oder mehrere Zeichen folgen in Teil Zeichenfolgen aufzuteilen.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Der Split-Operator teilt eine oder mehrere Zeichen folgen in Teil Zeichenfolgen auf. Sie können die folgenden Elemente des Split-Vorgangs ändern:

- Trennzeichen. Der Standardwert ist Leerraum, aber Sie können Zeichen, Zeichen folgen, Muster oder Skriptblöcke angeben, die das Trennzeichen angeben. Der Split-Operator in PowerShell verwendet anstelle eines einfachen Zeichens einen regulären Ausdruck im Trennzeichen.
- Maximale Anzahl von Teil Zeichenfolgen. Der Standardwert besteht darin, alle Teil Zeichenfolgen zurückzugeben. Wenn Sie eine Zahl angeben, die kleiner ist als die Anzahl der Teil Zeichenfolgen, werden die restlichen Teil Zeichenfolgen in der letzten Teil Zeichenfolge verkettet.
- Optionen, die die Bedingungen angeben, unter denen das Trennzeichen abgeglichen wird, z. b. simplematch und Multiline.

## <a name="syntax"></a>SYNTAX

Das folgende Diagramm zeigt die Syntax für den-Split-Operator.

Die Parameternamen werden im Befehl nicht angezeigt. Nur die Parameterwerte einschließen. Die Werte müssen in der im Syntax Diagramm angegebenen Reihenfolge angezeigt werden.

```
-Split <String>
-Split (<String[]>)
<String> -Split <Delimiter>[,<Max-substrings>[,"<Options>"]]
<String> -Split {<ScriptBlock>} [,<Max-substrings>]
```

Sie können `-iSplit` `-cSplit` `-split` in einer beliebigen binären Split-Anweisung (eine Split-Anweisung, die ein Trennzeichen oder einen Skriptblock enthält) ersetzen. Die `-iSplit` groß `-split` -/Kleinschreibung wird von den Operatoren und Der Operator unterscheidet zwischen Groß `-cSplit` -und Kleinschreibung, was bedeutet, dass der Fall beim Anwenden der Trennzeichen Regeln berücksichtigt wird.

## <a name="parameters"></a>PARAMETERS

### <a name="string-or-string"></a>\<String\> oder \<String[]\>

Gibt eine oder mehrere Zeichen folgen an, die aufgeteilt werden sollen. Wenn Sie mehrere Zeichen folgen übermitteln, werden alle Zeichen folgen mit denselben Trennzeichen Regeln aufgeteilt.

Beispiel:

```
-split "red yellow blue green"
red
yellow
blue
green
```

### \<Delimiter\>

Die Zeichen, die das Ende einer Teil Zeichenfolge identifizieren. Das Standard Trennzeichen ist Leerzeichen, einschließlich Leerzeichen und nicht druckbaren Zeichen, wie z. b. Zeilen Vorschriften ( \` n) und Tab ( \` t). Wenn die Zeichen folgen aufgeteilt werden, wird das Trennzeichen in allen Teil Zeichenfolgen ausgelassen. Beispiel:

```powershell
"Lastname:FirstName:Address" -split ":"
Lastname
FirstName
Address
```

Standardmäßig wird das Trennzeichen in den Ergebnissen ausgelassen. Um das Trennzeichen vollständig oder teilweise beizubehalten, schließen Sie in Klammern den Teil ein, den Sie beibehalten möchten.
Wenn der- `<Max-substrings>` Parameter hinzugefügt wird, hat dies Vorrang, wenn der Befehl die Auflistung aufteilt. Wenn Sie ein Trennzeichen als Teil der Ausgabe einschließen möchten, gibt der Befehl das Trennzeichen als Teil der Ausgabe zurück. das Aufteilen der Zeichenfolge, um das Trennzeichen als Teil der Ausgabe zurückzugeben, wird jedoch nicht als Teilung gezählt.

Beispiele:

```powershell
"Lastname:FirstName:Address" -split "(:)"
Lastname
:
FirstName
:
Address

"Lastname/:/FirstName/:/Address" -split "/(:)/"
Lastname
:
FirstName
:
Address
```

### `<Max-substrings>`

Gibt die maximale Anzahl von Teil Zeichenfolgen an, die vom Split-Vorgang zurückgegeben werden Der Standardwert ist alle Teil Zeichenfolgen, die durch das Trennzeichen geteilt werden. Wenn weitere Teil Zeichenfolgen vorhanden sind, werden Sie mit der endgültigen Teil Zeichenfolge verkettet. Wenn weniger Teil Zeichenfolgen vorhanden sind, werden alle Teil Zeichenfolgen zurückgegeben. Der Wert 0 gibt alle Teil Zeichenfolgen zurück.

Beispiel:

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", 5
```

```Output
Mercury
Venus
Earth
Mars
Jupiter,Saturn,Uranus,Neptune
```

Wenn Sie mehr als eine Zeichenfolge (ein Array von Zeichen folgen) an den Operator übermitteln `-split` , `Max-substrings` wird die Beschränkung auf jede Zeichenfolge separat angewendet.

```powershell
$c = 'a,b,c','1,2,3,4,5'
$c -split ',', 3

a
b
c
1
2
3,4,5
```

`<Max-substrings>` gibt nicht die maximale Anzahl von Objekten an, die zurückgegeben werden. Im folgenden Beispiel `<Max-substrings>` wird auf 3 festgelegt.
Dies führt zu drei Teil Zeichenfolgen-Werten, aber insgesamt fünf Zeichen folgen in der resultierenden Ausgabe. Das Trennzeichen ist nach den Teilungen enthalten, bis das Maximum von drei Teil Zeichenfolgen erreicht wird. Zusätzliche Trennzeichen in der letzten Teil Zeichenfolge werden Teil der Teil Zeichenfolge.

```powershell
'Chocolate-Vanilla-Strawberry-Blueberry' -split '(-)', 3
```

```Output
Chocolate
-
Vanilla
-
Strawberry-Blueberry
```

Negative Werte geben die Menge der angeforderten Teil Zeichenfolgen ab dem Ende der Eingabe Zeichenfolge zurück.

> [!NOTE]
> Unterstützung für negative Werte wurde in PowerShell 7 hinzugefügt.

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", -5
```

```Output
Mercury,Venus,Earth,Mars
Jupiter
Saturn
Uranus
Neptune
```

### \<ScriptBlock\>

Ein Ausdruck, der Regeln zum Anwenden des Trenn Zeichens angibt. Der Ausdruck muss zu $true oder $false ausgewertet werden. Schließen Sie den Skriptblock in geschweifte Klammern ein.

Beispiel:

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split {$_ -eq "e" -or $_ -eq "p"}
```

```Output
M
rcury,V
nus,
arth,Mars,Ju
it
r,Saturn,Uranus,N

tun
```

### \<Options\>

Schließen Sie den Optionsnamen in Anführungszeichen ein. Optionen sind nur gültig, wenn der- \<Max-substrings\> Parameter in der-Anweisung verwendet wird.

Die Syntax für den options-Parameter lautet wie folgt:

```
"SimpleMatch [,IgnoreCase]"

"[RegexMatch] [,IgnoreCase] [,CultureInvariant]
[,IgnorePatternWhitespace] [,ExplicitCapture]
[,Singleline | ,Multiline]"
```

Die simplematch-Optionen lauten wie folgt:

- **Simplematch**: Verwenden Sie einen einfachen Zeichen folgen Vergleich, wenn Sie das Trennzeichen auswerten. Kann nicht mit RegexMatch verwendet werden.
- **IgnoreCase**: erzwingt Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung, auch wenn der-csplit-Operator angegeben wird.

Die RegexMatch-Optionen lauten wie folgt:

- **RegexMatch**: verwendet reguläre Ausdrucks Vergleiche, um das Trennzeichen auszuwerten. Dies ist das Standardverhalten. Kann nicht mit simplematch verwendet werden.
- **IgnoreCase**: erzwingt Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung, auch wenn der-csplit-Operator angegeben wird.
- **CultureInvariant**: ignoriert kulturelle Unterschiede in der Sprache, wenn das Trennzeichen angegeben wird. Nur mit RegexMatch gültig.
- **IgnorePatternWhitespace**: ignoriert Leerzeichen ohne Escapezeichen und Kommentare, die mit dem Nummern Zeichen (#) gekennzeichnet sind. Nur mit RegexMatch gültig.
- **MultiLine**: der mehrzeilige Modus erzwingt `^` und `$` , um das Anfangs Ende jeder Zeile anstelle von Anfang und Ende der Eingabe Zeichenfolge abzugleichen.
- **SingleLine**: der SingleLine-Modus behandelt die Eingabe Zeichenfolge als *SingleLine*.
  Es erzwingt `.` , dass das Zeichen jedem Zeichen (einschließlich der Zeilenumbrüche) entspricht, anstatt jedes Zeichen mit Ausnahme von Zeilenumbrüche abzugleichen `\n` .
- **Explizicapture**: ignoriert nicht benannte Übereinstimmungs Gruppen, sodass nur explizite Erfassungs Gruppen in der Ergebnisliste zurückgegeben werden. Nur mit RegexMatch gültig.

## <a name="unary-and-binary-split-operators"></a>Unäre und binäre Split-Operatoren

Der unäre Split-Operator ( `-split <string>` ) hat Vorrang vor einem Komma. Wenn Sie daher eine durch Trennzeichen getrennte Liste von Zeichen folgen an den unären Split-Operator übermitteln, wird nur die erste Zeichenfolge (vor dem ersten Komma) aufgeteilt.

Verwenden Sie eines der folgenden Muster, um mehr als eine Zeichenfolge aufzuteilen:

- Verwenden des binären Split-Operators ( \<string[]\> -Split \<delimiter\> )
- Alle Zeichen folgen in Klammern einschließen
- Speichern Sie die Zeichen folgen in einer Variablen, und senden Sie die Variable an den Split-Operator.

Betrachten Sie das folgenden Beispiel:

```
PS> -split "1 2", "a b"
1
2
a b
```

```
PS> "1 2", "a b" -split " "
1
2
a
b
```

```
PS> -split ("1 2", "a b")
1
2
a
b
```

```
PS> $a = "1 2", "a b"
PS> -split $a
1
2
a
b
```

## <a name="examples"></a>BEISPIELE

Die folgende Anweisung teilt die Zeichenfolge bei Leerraum.

```powershell
-split "Windows PowerShell 2.0`nWindows PowerShell with remoting"
```

```Output

Windows
PowerShell
2.0
Windows
PowerShell
with
remoting
```

Mit der folgenden Anweisung wird die Zeichenfolge bei jedem Komma unterteilt.

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split ','
```

```Output
Mercury
Venus
Earth
Mars
Jupiter
Saturn
Uranus
Neptune
```

Die folgende Anweisung teilt die Zeichenfolge mit dem Muster "er".

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split 'er'
```

```Output
M
cury,Venus,Earth,Mars,Jupit
,Saturn,Uranus,Neptune
```

Mit der folgenden Anweisung wird die Unterscheidung nach Groß-/Kleinschreibung beim Buchstaben "N" unterschieden.

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -cSplit 'N'
```

```Output
Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,
eptune
```

Die folgende Anweisung teilt die Zeichenfolge unter "e" und "t".

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[et]'
```

```Output
M
rcury,V
nus,
ar
h,Mars,Jupi

r,Sa
urn,Uranus,N
p
un
```

Mit der folgenden Anweisung wird die Zeichenfolge bei "e" und "r" unterteilt, aber die resultierenden Teil Zeichenfolgen werden auf sechs Teil Zeichenfolgen beschränkt.

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[er]', 6
```

```Output
M

cu
y,V
nus,
arth,Mars,Jupiter,Saturn,Uranus,Neptune
```

Die folgende Anweisung teilt eine Zeichenfolge in drei Teil Zeichenfolgen auf.

```powershell
"a,b,c,d,e,f,g,h" -split ",", 3
```

```Output
a
b
c,d,e,f,g,h
```

Mit der folgenden Anweisung wird eine Zeichenfolge beginnend am Ende der Zeichenfolge in drei Teil Zeichenfolgen unterteilt.

```powershell
"a,b,c,d,e,f,g,h" -split ",", -3
```

```Output
a,b,c,d,e,f
g
h
```

Die folgende Anweisung teilt zwei Zeichen folgen in drei Teil Zeichenfolgen auf.
(Das Limit wird unabhängig voneinander auf jede Zeichenfolge angewendet.)

```powershell
"a,b,c,d", "e,f,g,h" -split ",", 3
```

```Output
a
b
c,d
e
f
g,h
```

Die folgende Anweisung teilt jede Zeile in der here-Zeichenfolge an der ersten Ziffer. Er verwendet die Multiline-Option, um den Anfang jeder Zeile und Zeichenfolge zu erkennen.

Der Wert 0 stellt den Wert "return all" des Parameters "Max-Substrings" dar. Sie können Optionen, wie z. b. Multiline, nur verwenden, wenn der Wert Max-Substrings angegeben wird.

```powershell
$a = @'
1The first line.
2The second line.
3The third of three lines.
'@
$a -split "^\d", 0, "multiline"
```

```Output

The first line.

The second line.

The third of three lines.
```

Die folgende Anweisung verwendet den umgekehrten Schrägstrich, um das Punkt Trennzeichen (.) mit Escapezeichen zu versehen.

Mit dem Standardwert RegexMatch wird der in Anführungszeichen (".") eingeschlossene Punkt so interpretiert, dass er mit einem beliebigen Zeichen übereinstimmt, mit Ausnahme eines Zeilen Vorzeichens. Folglich gibt die Split-Anweisung für jedes Zeichen mit Ausnahme von Zeilen Freigaben eine Leerzeile zurück.

```powershell
"This.is.a.test" -split "\."
```

```Output
This
is
a
test
```

Die folgende Anweisung verwendet die simplematch-Option, um den-Split-Operator anzuweisen, das Punkt Trennzeichen (.) buchstäblich zu interpretieren.

Der Wert 0 stellt den Wert "return all" des Parameters "Max-Substrings" dar. Sie können Optionen, wie z. b. simplematch, nur verwenden, wenn der Wert Max-Substrings angegeben wird.

```powershell
"This.is.a.test" -split ".", 0, "simplematch"
```

```Output
This
is
a
test
```

Die folgende Anweisung unterteilt die Zeichenfolge in einem von zwei Trennzeichen, je nach dem Wert einer Variablen.

```powershell
$i = 1
$c = "LastName, FirstName; Address, City, State, Zip"
$c -split $(if ($i -lt 1) {","} else {";"})
```

```Output
LastName, FirstName
 Address, City, State, Zip
```

## <a name="see-also"></a>SIEHE AUCH

[Split-Path](xref:Microsoft.PowerShell.Management.Split-Path)

[about_Operators](about_Operators.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Join](about_Join.md)
