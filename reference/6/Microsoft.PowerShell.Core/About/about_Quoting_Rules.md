---
description: Beschreibt Regeln für die Verwendung von einfachen und doppelten Anführungszeichen in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_quoting_rules?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Quoting_Rules
ms.openlocfilehash: d0ea2e5d9f424085fff7ec4b6d2ed830fd5c0587
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221327"
---
# <a name="about-quoting-rules"></a>Informationen zu Anführungs Regeln

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt Regeln für die Verwendung von einfachen und doppelten Anführungszeichen in PowerShell.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Anführungszeichen werden verwendet, um eine Literalzeichenfolge anzugeben. Sie können eine Zeichenfolge in einfache Anführungszeichen ( `'` ) oder in doppelte Anführungszeichen ( `"` ) einschließen.

Anführungszeichen werden auch verwendet, um eine here-Zeichenfolge zu erstellen. Eine here-Zeichenfolge ist eine Zeichenfolge in einfachen Anführungszeichen oder in doppelten Anführungszeichen, in der Anführungszeichen buchstäblich interpretiert werden. Eine here-Zeichenfolge kann sich über mehrere Zeilen erstrecken. Alle Zeilen in einer here-Zeichenfolge werden als Zeichen folgen interpretiert, auch wenn Sie nicht in Anführungszeichen eingeschlossen sind.

In Befehlen auf Remote Computern definieren Anführungszeichen die Teile des Befehls, die auf dem Remote Computer ausgeführt werden. In einer Remote Sitzung bestimmen Anführungszeichen auch, ob die Variablen in einem Befehl zuerst auf dem lokalen Computer oder auf dem Remote Computer interpretiert werden.

### <a name="single-and-double-quoted-strings"></a>Zeichen folgen mit einzelfacher und doppelter Anführungszeichen

Wenn Sie eine Zeichenfolge in doppelte Anführungszeichen (eine Zeichenfolge mit doppelten Anführungszeichen) einschließen, werden Variablennamen, denen ein Dollarzeichen () vorangestellt ist, durch `$` den Wert der Variablen ersetzt, bevor die Zeichenfolge zur Verarbeitung an den Befehl übermittelt wird.

Beispiel:

```powershell
$i = 5
"The value of $i is $i."
```

Die Ausgabe dieses Befehls lautet wie folgt:

```Output
The value of 5 is 5.
```

Außerdem werden Ausdrücke in einer Zeichenfolge mit doppelten Anführungszeichen ausgewertet, und das Ergebnis wird in die Zeichenfolge eingefügt. Beispiel:

```powershell
"The value of $(2+3) is 5."
```

Die Ausgabe dieses Befehls lautet wie folgt:

```output
The value of 5 is 5.
```

Wenn Sie eine Zeichenfolge in einfache Anführungszeichen einschließen (in einer Zeichenfolge mit nur einem Anführungszeichen), wird die Zeichenfolge genau wie bei der Eingabe an den Befehl übermittelt. Es wird keine Ersetzung durchgeführt. Beispiel:

```powershell
$i = 5
'The value of $i is $i.'
```

Die Ausgabe dieses Befehls lautet wie folgt:

```Output
The value $i is $i.
```

Ebenso werden Ausdrücke in Zeichen folgen in einfachen Anführungszeichen nicht ausgewertet. Sie werden als Literale interpretiert. Beispiel:

```powershell
'The value of $(2+3) is 5.'
```

Die Ausgabe dieses Befehls lautet wie folgt:

```Output
The value of $(2+3) is 5.
```

Um die Ersetzung eines Variablen Werts in einer Zeichenfolge mit doppelten Anführungszeichen zu verhindern, verwenden Sie das Graviszeichen-Zeichen ( `` ` `` ) (ASCII 96), das das PowerShell-Escapezeichen ist.

Im folgenden Beispiel verhindert das Graviszeichen-Zeichen, das der ersten $i Variablen vorangestellt ist, dass PowerShell den Variablennamen durch den Wert ersetzt.
Beispiel:

```powershell
$i = 5
"The value of `$i is $i."
```

Die Ausgabe dieses Befehls lautet wie folgt:

```Output
The value $i is 5.
```

Damit doppelte Anführungszeichen in einer Zeichenfolge angezeigt werden, müssen Sie die gesamte Zeichenfolge in einfache Anführungszeichen einschließen. Beispiel:

```powershell
'As they say, "live and learn."'
```

Die Ausgabe dieses Befehls lautet wie folgt:

```Output
As they say, "live and learn."
```

Sie können auch eine Zeichenfolge in einer Zeichenfolge mit doppelten Anführungszeichen in eine Zeichenfolge mit doppelten Anführungszeichen einschließen. Beispiel:

```powershell
"As they say, 'live and learn.'"
```

Die Ausgabe dieses Befehls lautet wie folgt:

```Output
As they say, 'live and learn.'
```

Oder doppelte Anführungszeichen um einen Ausdruck mit doppelten Anführungszeichen. Beispiel:

```powershell
"As they say, ""live and learn."""
```

Die Ausgabe dieses Befehls lautet wie folgt:

```Output
As they say, "live and learn."
```

Wenn Sie ein einzelnes Anführungszeichen in eine Zeichenfolge mit nur einem Anführungszeichen einschließen möchten, verwenden Sie ein zweites aufeinander folgende einfache Anführungszeichen. Beispiel:

```powershell
'don''t'
```

Die Ausgabe dieses Befehls lautet wie folgt:

```Output
don't
```

Um zu erzwingen, dass PowerShell ein doppeltes Anführungszeichen wörtlich interpretiert, verwenden Sie ein Graviszeichen-Zeichen. Dadurch wird verhindert, dass PowerShell das Anführungszeichen als Zeichen folgen Trennzeichen interpretiert. Beispiel:

```powershell
PS> "Use a quotation mark (`") to begin a string."
Use a quotation mark (") to begin a string.
PS> 'Use a quotation mark (`") to begin a string.'
Use a quotation mark (`") to begin a string.
```

Da der Inhalt von Zeichen folgen in einfachen Anführungszeichen wörtlich interpretiert wird, wird das Graviszeichen-Zeichen als Literalzeichen behandelt und in der Ausgabe angezeigt.

### <a name="here-strings"></a>Here-Zeichen folgen

Die Anführungszeichen Regeln für here-Zeichen folgen unterscheiden sich geringfügig.

Eine here-Zeichenfolge ist eine Zeichenfolge in einfachen Anführungszeichen oder in doppelten Anführungszeichen, in der Anführungszeichen buchstäblich interpretiert werden. Eine here-Zeichenfolge kann sich über mehrere Zeilen erstrecken. Alle Zeilen in einer here-Zeichenfolge werden als Zeichen folgen interpretiert, auch wenn Sie nicht in Anführungszeichen eingeschlossen sind.

Wie reguläre Zeichen folgen werden Variablen durch ihre Werte in Zeichen folgen in doppelten Anführungszeichen ersetzt. In in einfachen Anführungszeichen eingeschlossenen Zeichen folgen werden Variablen nicht durch ihre Werte ersetzt.

Sie können hier Zeichen folgen für jeden beliebigen Text verwenden, Sie sind jedoch für die folgenden Arten von Text besonders nützlich:

- Text, der literalanführungs Zeichen enthält
- Mehrere Textzeilen, z. b. der Text in einem HTML-oder XML-Code
- Der Hilfetext eines Skripts oder Funktions Dokuments.

Eine here-Zeichenfolge kann eines der folgenden Formate aufweisen, wobei `<Enter>` das Zeilenvorschub-oder Zeilenvorschub Zeichen darstellt, das hinzugefügt wird, wenn Sie die <kbd>Eingabe</kbd> Taste drücken.

Doppelte Anführungszeichen:

```
@"<Enter>
<string> [string] ...<Enter>
"@
```

Einfache Anführungszeichen:

```
@'<Enter>
<string> [string] ...<Enter>
'@
```

In beiden Formaten muss das schließende Anführungszeichen das erste Zeichen in der Zeile sein.

Eine here-Zeichenfolge enthält den gesamten Text zwischen den beiden ausgeblendeten Zeichen. In der here-Zeichenfolge werden alle Anführungszeichen buchstäblich interpretiert. Beispiel:

```powershell
@"
For help, type "get-help"
"@
```

Die Ausgabe dieses Befehls lautet wie folgt:

```Output
For help, type "get-help"
```

Die Verwendung einer here-Zeichenfolge kann die Verwendung einer Zeichenfolge in einem Befehl vereinfachen. Beispiel:

```powershell
@"
Use a quotation mark (') to begin a string.
"@
```

Die Ausgabe dieses Befehls lautet wie folgt:

```Output
Use a quotation mark (') to begin a string.
```

In in einfachen Anführungszeichen eingeschlossenen Zeichen folgen werden Variablen buchstäblich interpretiert und exakt reproduziert. Beispiel:

```powershell
@'
The $profile variable contains the path
of your PowerShell profile.
'@
```

Die Ausgabe dieses Befehls lautet wie folgt:

```Output
The $profile variable contains the path
of your PowerShell profile.
```

In doppelten Anführungszeichen werden Zeichen folgen, Variablen durch ihre Werte ersetzt. Beispiel:

```powershell
@"
Even if you have not created a profile,
the path of the profile file is:
$profile.
"@
```

Die Ausgabe dieses Befehls lautet wie folgt:

```Output
Even if you have not created a profile,
the path of the profile file is:
C:\Users\User1\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1.
```

Here-Zeichen folgen werden normalerweise verwendet, um einer Variablen mehrere Zeilen zuzuweisen. Beispielsweise weist die folgende here-Zeichenfolge der $Page Variable eine XML-Seite zu.

```powershell
$page = [XML] @"
<command:command xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
<command:details>
        <command:name>
               Format-Table
        </command:name>
        <maml:description>
            <maml:para>Formats the output as a table.</maml:para>
        </maml:description>
        <command:verb>format</command:verb>
        <command:noun>table</command:noun>
        <dev:version></dev:version>
</command:details>
...
</command:command>
"@
```

Here-Zeichen folgen sind auch ein nützliches Format für Eingaben in das `ConvertFrom-StringData` Cmdlet, das hier Zeichen folgen in Hash Tabellen konvertiert.
Weitere Informationen finden Sie unter `ConvertFrom-StringData`.

## <a name="see-also"></a>SIEHE AUCH

[about_Special_Characters](about_Special_Characters.md)

[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
