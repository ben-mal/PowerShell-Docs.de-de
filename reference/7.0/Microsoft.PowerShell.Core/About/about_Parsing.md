---
description: Beschreibt, wie PowerShell Befehle analysiert.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parsing?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parsing
ms.openlocfilehash: 538da6bd84fb652620e97703346225174bac211a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223148"
---
# <a name="about-parsing"></a>Informationen zur-Verarbeitung

## <a name="short-description"></a>KURZE BESCHREIBUNG

Beschreibt, wie PowerShell Befehle analysiert.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Wenn Sie einen Befehl an der Eingabeaufforderung eingeben, unterbricht PowerShell den Befehls Text in eine Reihe von Segmenten, die als _Token_ bezeichnet werden, und bestimmt dann, wie die einzelnen Token interpretiert werden.

Wenn Sie z. b. Folgendes eingeben:

```powershell
Write-Host book
```

PowerShell unterbricht den Befehl in zwei Token `Write-Host` `book` : und, und interpretiert jedes Token unabhängig mithilfe eines der folgenden zwei wichtigen Analyse-Modi: Ausdrucks Modus und Argument Modus.

> [!NOTE]
> Wenn PowerShell Befehlseingaben analysiert, versucht es, die Befehlsnamen in Cmdlets oder systemeigene ausführbare Dateien aufzulösen. Wenn ein Befehls Name keine genaue Entsprechung hat, wird `Get-` der Befehl von PowerShell als Standard Verb vorangestellt. Beispielsweise wird von PowerShell `Process` als analysiert `Get-Process` . Es wird nicht empfohlen, dieses Feature aus den folgenden Gründen zu verwenden:
>
> - Es ist ineffizient. Dies bewirkt, dass PowerShell mehrmals durchsucht wird.
> - Externe Programme mit dem gleichen Namen werden zuerst aufgelöst, sodass Sie das beabsichtigte Cmdlet nicht ausführen können.
> - `Get-Help` und `Get-Command` keine Verb losen Namen erkennen.

### <a name="expression-mode"></a>Ausdrucks Modus

Der Ausdrucks Modus dient zum Kombinieren von Ausdrücken, die für die Bearbeitung von Werten in einer Skriptsprache erforderlich sind. Ausdrücke sind Darstellungen von Werten in der PowerShell-Syntax und können einfach oder zusammengesetzt sein, z. b.:

Literale Ausdrücke sind direkte Darstellungen ihrer Werte: 

```powershell
'hello', 32
```

Variablen Ausdrücke enthalten den Wert der Variablen, auf die Sie verweisen: 

```powershell
$x, $script:path
```
Operatoren kombinieren andere Ausdrücke zur Auswertung: 

```powershell
- 12, -not $Quiet, 3 + 7, $input.Length -gt 1
```

- _Zeichen folgen Literale_ müssen in Anführungszeichen stehen.
- _Zahlen_ werden als numerische Werte und nicht als Zeichenfolge behandelt (es sei denn, Sie werden mit Escapezeichen versehen).
- _Operatoren_ , einschließlich unärer Operatoren wie `-` und `-not` und binäre Operatoren wie `+` und `-gt` , werden als Operatoren interpretiert und wenden ihre entsprechenden Vorgänge auf ihre Argumente (Operanden) an.
- _Attribut-und Konvertierungs Ausdrücke_ werden als Ausdrücke analysiert und auf untergeordnete Ausdrücke angewendet, z. b. `[int] '7'` .
- _Variablen Verweise_ werden auf ihre Werte ausgewertet, aber _Verteilung_ (d. h. vorgefüllte Parametersätze einfügen) ist unzulässig und verursacht einen Parserfehler.
- Alles andere wird als Befehl behandelt, der aufgerufen werden soll.

### <a name="argument-mode"></a>Argument Modus

Beim Analysieren prüft PowerShell zunächst, dass die Eingabe als Ausdruck interpretiert wird. Wenn jedoch ein Befehls Aufruf auftritt, wird die Analyse im Argument Modus fortgesetzt.

Der Argument Modus ist für das Parsen von Argumenten und Parametern für Befehle in in einer Shellumgebung konzipiert.  Alle Eingaben werden als erweiterbare Zeichenfolge behandelt, es sei denn, Sie verwendet eine der folgenden Syntaxen:

- Das Dollar Zeichen ( `$` ) beginnt einen Variablen Verweis (nur, wenn ein gültiger Variablenname folgt, andernfalls wird er als Teil der erweiterbaren Zeichenfolge interpretiert).
- Anführungszeichen ( `'` und `"` ) Zeichen folgen Werte
- Mit Klammern ( `(` und `)` ) werden neue Ausdrücke abgegrenzt.
- Der subexpression-Operator ( `$(` ... `)` ) entfernt eingebettete Ausdrücke.
- Geschweifte Klammern ( `{` und `}` ) setzen neue Skriptblöcke um.
- Das anfängliche at-Zeichen ( `@` ) beginnt Ausdrucks Syntaxen, z. b. Verteilung ( `@args` ), Arrays ( `@(1,2,3)` ) und Hash Tabellen ( `@{a=1;b=2}` ).
- Kommas ( `,` ) führen Listen ein, die als Arrays übergebenen werden, es sei denn, der aufzurufende Befehl ist eine native Anwendung. in diesem Fall werden Sie als Teil der erweiterbaren Zeichenfolge interpretiert. Anfängliche, aufeinander folgende oder nachfolgende Kommas werden nicht unterstützt.

Werte eingebetteter Ausdrücke werden in Zeichen folgen konvertiert.

Die folgende Tabelle enthält einige Beispiele für Werte, die im Ausdrucks Modus und im Argument Modus verarbeitet werden, sowie für die Auswertung dieser Werte. Wir gehen davon aus, dass der Wert der-Variablen `a` ist `4` .

|       Beispiel        |    Mode    |      Ergebnis       |
| -------------------- | ---------- | ----------------- |
| `2`                  | Ausdruck | 2 (ganze Zahl)       |
| `` `2``              | Ausdruck | "2" (Befehl)     |
| `echo 2`             | Ausdruck | 2 (ganze Zahl)       |
| `2+2`                | Ausdruck | 4 (ganze Zahl)       |
| `echo 2+2`           | Argument   | "2 + 2" (Zeichenfolge)    |
| `echo(2+2)`          | Ausdruck | 4 (ganze Zahl)       |
| `$a`                 | Ausdruck | 4 (ganze Zahl)       |
| `echo $a`            | Ausdruck | 4 (ganze Zahl)       |
| `$a+2`               | Ausdruck | 6 (ganze Zahl)       |
| `echo $a+2`          | Argument   | 4 + 2 (Zeichenfolge)      |
| `$-`                 | Argument   | "$-" (Befehl)    |
| `echo $-`            | Argument   | "$-" (Zeichenfolge)     |
| `a$a`                | Ausdruck | "a $ a" (Befehl)   |
| `echo a$a`           | Argument   | "A4" (Zeichenfolge)     |
| `a'$a'`              | Ausdruck | "a $ a" (Befehl)   |
| `echo a'$a'`         | Argument   | "a $ a" (Zeichenfolge)    |
| `a"$a"`              | Ausdruck | "a $ a" (Befehl)   |
| `echo a"$a"`         | Argument   | "A4" (Zeichenfolge)     |
| `a$(2)`              | Ausdruck | "a $ (2)" (Befehl) |
| `echo a$(2)`         | Argument   | "a2" (Zeichenfolge)     |

Jedes Token kann als Objekttyp, z. b. boolescher Wert oder Zeichenfolge, interpretiert werden. PowerShell versucht, den Objekttyp aus dem Ausdruck zu ermitteln.
Der Objekttyp hängt vom Typ des Parameters ab, den ein Befehl erwartet, und darüber, ob PowerShell weiß, wie das Argument in den richtigen Typ konvertiert werden kann. In der folgenden Tabelle sind einige Beispiele für die Typen aufgeführt, die von den Ausdrücken zurückgegebenen Werten zugewiesen werden.

|       Beispiel          |    Mode    |     Ergebnis      |
| ---------------------- | ---------- | --------------- |
| `Write-Output !1`      | Argument   | "! 1" (Zeichenfolge)   |
| `Write-Output (!1)`    | expression | False (Boolean) |
| `Write-Output (2)`     | expression | 2 (ganze Zahl)     |
| `Set-Variable AB A,B`  | Argument   | "A", "B" (Array) |
| `CMD /CECHO A,B`       | Argument   | "A, B" (Zeichenfolge)  |
| `CMD /CECHO $AB`       | expression | "A", "B" (Array) |
| `CMD /CECHO :$AB`      | Argument   | ': A B ' (Zeichenfolge) |

Das `--%` in PowerShell 3,0 eingeführte Symbol für die Beendigung der Ausführung () weist PowerShell an, die Eingaben nicht als PowerShell-Befehle oder-Ausdrücke zu interpretieren.

Wenn Sie ein ausführbares Programm in PowerShell aufrufen, platzieren Sie das Symbol für die Beendigung der Programmierung vor den Programm Argumenten. Diese Methode ist viel einfacher als die Verwendung von Escapezeichen, um eine Fehlinterpretation zu verhindern.

Wenn ein Symbol für die Beendigung gefunden wird, behandelt PowerShell die restlichen Zeichen in der Zeile als Literalzeichen. Die einzige Interpretation besteht darin, Werte für Umgebungsvariablen zu ersetzen, die eine standardmäßige Windows-Notation verwenden, z `%USERPROFILE%` . b..

Das Symbol für die Beendigung der Ausführung wird nur bis zum nächsten Zeilen-oder Pipeline Zeichen wirksam. Sie können kein Fortsetzungs Zeichen ( `` ` `` ) verwenden, um den Effekt zu erweitern, oder ein Befehls Trennzeichen ( `;` ) verwenden, um den Effekt zu beenden.

Der folgende Befehl ruft beispielsweise das **icacls** -Programm auf.

```powershell
icacls X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

Zum Ausführen dieses Befehls in PowerShell 2,0 müssen Sie Escapezeichen verwenden, um zu verhindern, dass PowerShell die Klammern falsch interpretiert.

```powershell
icacls X:\VMS /grant Dom\HVAdmin:`(CI`)`(OI`)F
```

Ab PowerShell 3,0 können Sie das Symbol für die Beendigung der Ausführung verwenden.

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

PowerShell sendet die folgende Befehls Zeichenfolge an das **icacls** -Programm:

`X:\VMS /grant Dom\HVAdmin:(CI)(OI)F`

> [!NOTE]
> Das Symbol für die Beendigung der Ausführung ist nur für die Verwendung auf Windows-Plattformen vorgesehen.

## <a name="see-also"></a>SIEHE AUCH

[about_Command_Syntax](about_Command_Syntax.md)
