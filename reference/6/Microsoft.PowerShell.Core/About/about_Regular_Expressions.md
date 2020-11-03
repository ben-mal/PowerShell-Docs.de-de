---
description: Beschreibt reguläre Ausdrücke in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_regular_expressions?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Regular_Expressions
ms.openlocfilehash: 6112c63b6d0c1018b56df85ec6ae919a0285ffc3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221308"
---
# <a name="about-regular-expressions"></a>Informationen zu regulären Ausdrücken

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt reguläre Ausdrücke in PowerShell.

## <a name="long-description"></a>Lange Beschreibung

> [!NOTE]
> In diesem Artikel werden die Syntax und Methoden für die Verwendung regulärer Ausdrücke in PowerShell erläutert, nicht alle Syntax Themen. Einen ausführlicheren Verweis finden Sie unter [Sprache für reguläre Ausdrücke-kurz](/dotnet/standard/base-types/regular-expression-language-quick-reference)Übersicht.

Ein regulärer Ausdruck ist ein Muster, das verwendet wird, um Text zuzuordnen. Sie kann aus Literalzeichen, Operatoren und anderen Konstrukten bestehen.

Dieser Artikel veranschaulicht die Syntax regulärer Ausdrücke in PowerShell. PowerShell verfügt über mehrere Operatoren und Cmdlets, die reguläre Ausdrücke verwenden. Weitere Informationen zur Syntax und Verwendung finden Sie unter den folgenden Links.

- [Select-String](xref:Microsoft.PowerShell.Utility.Select-String)
- [-Match-und-replace-Operatoren](about_Comparison_Operators.md)
- [-Teilen](about_Split.md)
- [Switch-Anweisung mit der Option "-regex"](about_Switch.md)

Bei regulären Ausdrücken von PowerShell wird die Groß-/Kleinschreibung nicht beachtet. Jede oben gezeigte Methode bietet eine andere Möglichkeit, die Groß-/Kleinschreibung zu erzwingen.

|       Methode       |                      Groß- und Kleinschreibung                      |
| ------------------ | ---------------------------------------------------------- |
| `Select-String`    | Verwenden des `-CaseSensitive` Schalters                                |
| `switch`-Anweisung | Verwenden Sie die `-casesensitive` Option                            |
| Operatoren          | Präfix mit **"c"** ( `-cmatch` , `-csplit` oder `-creplace` ) |

### <a name="character-literals"></a>Zeichenliterale

Ein regulärer Ausdruck kann ein Literalzeichen oder eine Zeichenfolge sein. Der Ausdruck bewirkt, dass die Engine mit dem exakt angegebenen Text übereinstimmt.

```powershell
# This statement returns true because book contains the string "oo"
'book' -match 'oo'
```

### <a name="character-classes"></a>Zeichenklassen

Wenn Zeichen Literale funktionieren, wenn Sie das genaue Muster kennen, können Sie mit Zeichenklassen weniger spezifisch sein.

#### <a name="character-groups"></a>Zeichen Gruppen

`[character group]` ermöglicht es Ihnen, eine beliebige Anzahl von Zeichen einmal abzugleichen, während `[^character group]` nur Zeichen, die nicht in der Gruppe enthalten sind, übereinstimmen.

```powershell
# This expression returns true if the pattern matches big, bog, or bug.
'big' -match 'b[iou]g'
```

Wenn die Liste der zu Übereinstimmungs enden Zeichen den Bindestrich ( `-` ) enthält, muss Sie sich am Anfang oder Ende der Liste befinden, damit Sie von einem Zeichen Bereichs Ausdruck unterschieden werden kann.

#### <a name="character-ranges"></a>Zeichen Bereiche

Ein Muster kann auch ein Bereich von Zeichen sein. Die Zeichen können alphabetisch `[A-Z]` , numerisch `[0-9]` oder sogar ASCII-basiert `[ -~]` (alle druckbaren Zeichen) sein.

```powershell
# This expression returns true if the pattern matches any 2 digit number.
42 -match '[0-9][0-9]'
```

#### <a name="numbers"></a>Zahlen

Die `\d` Zeichenklasse entspricht einer beliebigen Dezimal Ziffer. Umgekehrt findet eine Entsprechung für `\D` jede nicht-dezimal Ziffer.

```powershell
# This expression returns true if it matches a server name.
# (Server-01 - Server-99).
'Server-01' -match 'Server-\d\d'
```

#### <a name="word-characters"></a>Wort Zeichen

Die `\w` Zeichenklasse entspricht einem beliebigen Wort Zeichen `[a-zA-Z_0-9]` . Verwenden Sie, um einem beliebigen nicht-Wort Zeichen zu entsprechen `\W` .

```powershell
# This expression returns true.
# The pattern matches the first word character 'B'.
'Book' -match '\w'
```

#### <a name="wildcards"></a>Platzhalter

Der Zeitraum ( `.` ) ist ein Platzhalter Zeichen in regulären Ausdrücken. Es findet eine Entsprechung für jedes Zeichen außer einem Zeilen Umleitungs Zeichen ( `\n` ).

```powershell
# This expression returns true.
# The pattern matches any 4 characters except the newline.
'a1\ ' -match '....'
```

#### <a name="whitespace"></a>Leerraum

Leerraum wird mithilfe der- `\s` Zeichenklasse abgeglichen. Ein Zeichen, das kein Leerzeichen ist, wird mithilfe von abgeglichen `\S` . Literalleerzeichen `' '` können ebenfalls verwendet werden.

```powershell
# This expression returns true.
# The pattern uses both methods to match the space.
' - ' -match '\s- '
```

### <a name="quantifiers"></a>Quantifizierer

Quantifiziererer steuern, wie viele Instanzen jedes Elements in der Eingabe Zeichenfolge vorhanden sein sollten.

Im folgenden sind einige der in PowerShell verfügbaren quantifiziererer aufgeführt:

| Quantifizierer |                Beschreibung                |
| ---------- | ----------------------------------------- |
| `*`        | NULL oder mehrmals.                       |
| `+`        | Einmal oder mehrmals.                        |
| `?`        | Kein oder einmal.                         |
| `{n,m}`    | Mindestens `n` , aber nicht mehr als `m` Uhrzeiten. |

Das Sternchen ( `*` ) entspricht dem vorangehenden Element nicht oder mehrmals. Das Ergebnis ist, dass auch eine Eingabe Zeichenfolge ohne das-Element eine Entsprechung wäre.

```powershell
# This returns true for all account name strings even if the name is absent.
'ACCOUNT NAME:    Administrator' -match 'ACCOUNT NAME:\s*\w*'
```

Das Pluszeichen ( `+` ) entspricht dem vorangehenden Element einmal oder mehrmals.

```powershell
# This returns true if it matches any server name.
'DC-01' -match '[A-Z]+-\d\d'
```

Das Fragezeichen `?` entspricht dem vorangehenden Element nicht oder einmal. Ebenso wie Sternchen werden Zeichen folgen `*` , in denen das-Element nicht vorhanden ist, sogar abgeglichen.

```powershell
# This returns true for any server name, even server names without dashes.
'SERVER01' -match '[A-Z]+-?\d\d'
```

Der `{n, m}` Quantifizierer kann auf verschiedene Arten verwendet werden, um eine differenzierte Steuerung des Quantifizierers zuzulassen. Das zweite Element `m` und das Komma `,` sind optional.

| Quantifizierer |                Beschreibung                 |
| ---------- | ------------------------------------------ |
| `{n}`      | Übereinstimmung `n` mit genau der Anzahl von vorkommen.         |
| `{n,}`     | Entspricht mindestens `n` der Anzahl von vorkommen.        |
| `{n,m}`    | Vergleichen zwischen `n` und `m` der Anzahl von vorkommen. |

```powershell
# This returns true if it matches any phone number.
'111-222-3333' -match '\d{3}-\d{3}-\d{4}'
```

### <a name="anchors"></a>Anchors

Anker ermöglichen es Ihnen, eine Übereinstimmung basierend auf der übereinstimmenden Position in der Eingabe Zeichenfolge erfolgreich oder fehlerhaft zu erzeugen.

Die beiden häufig verwendeten Anker sind `^` und `$` . Die Einfügemarke `^` entspricht dem Anfang einer Zeichenfolge und `$` , die mit dem Ende einer Zeichenfolge übereinstimmt. Die Anker ermöglichen es Ihnen, Ihren Text an einer bestimmten Position abzugleichen, während unerwünschte Zeichen verworfen werden.

```powershell
# The pattern expects the string 'fish' to be the only thing on the line.
# This returns FALSE.
'fishing' -match '^fish$'
```

> [!NOTE]
> Wenn Sie einen regulären Ausdruck definieren, der einen `$` Anker enthält, achten Sie darauf, dass Sie den Regex-Ausdruck in einfache Anführungszeichen ( `'` ) statt in doppelte Anführungszeichen () einschließen, `"` oder der Ausdruck wird von PowerShell als Variable erweitert.

Wenn Sie Anker in PowerShell verwenden, sollten Sie den Unterschied zwischen den Optionen für " **SingleLine** " und " **mehrzeilige** reguläre Ausdrücke" verstehen.

- **MultiLine** : der mehrzeilige Modus erzwingt `^` und `$` , um das Anfangs Ende jeder Zeile anstelle von Anfang und Ende der Eingabe Zeichenfolge abzugleichen.
- **SingleLine** : der SingleLine-Modus behandelt die Eingabe Zeichenfolge als **SingleLine**.
  Es erzwingt `.` , dass das Zeichen jedem Zeichen (einschließlich der Zeilenumbrüche) entspricht, anstatt jedes Zeichen mit Ausnahme von Zeilenumbrüche abzugleichen `\n` .

Weitere Informationen zu diesen Optionen und deren Verwendung finden Sie in der Sprache für [reguläre Ausdrücke (kurz](/dotnet/standard/base-types/regular-expression-language-quick-reference)Übersicht).

### <a name="escaping-characters"></a>Zeichen mit Escapezeichen

Der umgekehrte Schrägstrich ( `\` ) wird verwendet, um Zeichen zu Escapezeichen, sodass Sie nicht von der Engine für reguläre Ausdrücke analysiert werden.

Die folgenden Zeichen sind reserviert: `[]().\^$|?*+{}` .

Sie müssen diese Zeichen in ihren Mustern mit Escapezeichen versehen, um Sie in ihren Eingabe Zeichenfolgen abzugleichen.

```powershell
# This returns true and matches numbers with at least 2 digits of precision.
# The decimal point is escaped using the backslash.
'3.141' -match '3\.\d{2,}'
```

Es gibt eine statische Methode der Regex-Klasse, die Text mit Escapezeichen versehen kann.

```powershell
[regex]::escape('3.\d{2,}')
```

```Output
3\.\\d\{2,}
```

> [!NOTE]
> Dadurch werden alle reservierten Zeichen für reguläre Ausdrücke, einschließlich vorhandener umgekehrter Schrägstriche, in Zeichenklassen verwendet. Achten Sie darauf, dass Sie Sie nur für den Teil des Musters verwenden, den Sie mit Escapezeichen versehen müssen.

#### <a name="other-character-escapes"></a>Andere Escapezeichen

Es gibt auch reservierte Escapezeichen, die Sie verwenden können, um besondere Zeichen Typen abzugleichen.

Im folgenden finden Sie einige häufig verwendete Escapezeichen:

|Escapezeichen  |BESCHREIBUNG  |
|---------|---------|
|`\t`|Entspricht einer Registerkarte|
|`\n`|Entspricht einem Zeilen Einschluss|
|`\r`|Entspricht einem Wagen Rücklauf Zeichen|

### <a name="groups-captures-and-substitutions"></a>Gruppen, Erfassungen und Ersetzungen

Gruppierungskonstrukte trennen eine Eingabe Zeichenfolge in Teil Zeichenfolgen, die aufgezeichnet oder ignoriert werden können. Gruppierte Teil Zeichenfolgen werden als Teil Ausdrücke bezeichnet. Standard Ausdrücke werden standardmäßig in nummerierten Gruppen aufgezeichnet, aber Sie können Ihnen auch Namen zuweisen.

Ein Gruppierungs Konstrukt ist ein regulärer Ausdruck, der von Klammern umgeben ist. Jeder Text, der mit dem eingeschlossenen regulären Ausdruck übereinstimmt, wird aufgezeichnet. Im folgenden Beispiel wird der Eingabetext in zwei Erfassungs Gruppen aufgeteilt.

```powershell
'The last logged on user was CONTOSO\jsmith' -match '(.+was )(.+)'
```

```Output
True
```

Verwenden `$Matches` Sie die automatische **Hash Tabelle** -Variable, um erfassten Text abzurufen.
Der Text, der die gesamte Übereinstimmung darstellt, wird im Schlüssel gespeichert `0` .

```powershell
$Matches.0
```

```Output
The last logged on user was CONTOSO\jsmith
```

Erfassungen werden in numerischen **ganzzahligen** Schlüsseln gespeichert, die sich von links nach rechts erhöhen. Capture `1` enthält den gesamten Text bis zum Benutzernamen, die Erfassung `2` enthält lediglich den Benutzernamen.

```powershell
$Matches
```

```Output
Name                           Value
----                           -----
2                              CONTOSO\jsmith
1                              The last logged on user was
0                              The last logged on user was CONTOSO\jsmith
```

> [!IMPORTANT]
> Der `0` Schlüssel ist eine **ganze** Zahl. Sie können eine beliebige **Hash Tabellen** Methode verwenden, um auf den gespeicherten Wert zuzugreifen.
>
> ```
> PS> 'Good Dog' -match 'Dog'
> True
>
> PS> $Matches[0]
> Dog
>
> PS> $Matches.Item(0)
> Dog
>
> PS> $Matches.0
> Dog
> ```

#### <a name="named-captures"></a>Benannte Erfassungen

Standardmäßig werden Erfassungen von links nach rechts in aufsteigender numerischer Reihenfolge gespeichert.
Sie können einer Erfassungs Gruppe auch einen **Namen** zuweisen. Dieser **Name** wird ein Schlüssel für die `$Matches` automatische **Hash Tabellen** Variable.

Verwenden Sie in einer `?<keyname>` Erfassungs Gruppe, um erfasste Daten unter einem benannten Schlüssel zu speichern.

```
PS> $string = 'The last logged on user was CONTOSO\jsmith'
PS> $string -match 'was (?<domain>.+)\\(?<user>.+)'
True

PS> $Matches

Name                           Value
----                           -----
domain                         CONTOSO
user                           jsmith
0                              was CONTOSO\jsmith

PS> $Matches.domain
CONTOSO

PS> $Matches.user
jsmith
```

Im folgenden Beispiel wird der neueste Protokolleintrag im Windows-Sicherheitsprotokoll gespeichert.
Der angegebene reguläre Ausdruck extrahiert den Benutzernamen und die Domäne aus der Nachricht und speichert Sie unter den Schlüsseln: **N** für Name und **D** für die Domäne.

```powershell
$log = (Get-WinEvent -LogName Security -MaxEvents 1).message
$r = '(?s).*Account Name:\s*(?<N>.*).*Account Domain:\s*(?<D>[A-Z,0-9]*)'
$log -match $r
```

```Output
True
```

```powershell
$Matches
```

```Output
Name                           Value
----                           -----
D                              CONTOSO
N                              jsmith
0                              A process has exited....
```

Weitere Informationen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions).

#### <a name="substitutions-in-regular-expressions"></a>Ersetzungen in regulären Ausdrücken

Die Verwendung der regulären Ausdrücke mit dem- `-replace` Operator ermöglicht das dynamische Ersetzen von Text mithilfe von Erfassungs Text.

`<input> -replace <original>, <substitute>`

- `<input>`: Die zu durchsuchende Zeichenfolge.
- `<original>`: Ein regulärer Ausdruck zum Durchsuchen der Eingabe Zeichenfolge.
- `<substitute>`: Ein Ersetzungs Ausdruck für reguläre Ausdrücke zum Ersetzen der in der Eingabe Zeichenfolge gefundenen Übereinstimmungen.

> [!NOTE]
> Der `<original>` -und der- `<substitute>` Operanden unterliegen den Regeln der Engine für reguläre Ausdrücke, z. b. Escapezeichen.

In der Zeichenfolge kann auf Erfassungs Gruppen verwiesen werden `<substitute>` . Die Ersetzung erfolgt mithilfe des `$` Zeichens vor dem Gruppen Bezeichner.

Zwei Möglichkeiten, auf Erfassungs Gruppen zu verweisen, sind nach **Nummer** und **Name**.

- Nach **Zahlen** Erfassungs Gruppen werden von links nach rechts nummeriert.

  ```powershell
  'John D. Smith' -replace '(\w+) (\w+)\. (\w+)', '$1.$2.$3@contoso.com'
  ```

  ```Output
  John.D.Smith@contoso.com
  ```

- Nach **Namen** können auch nach Namen Erfassungs Gruppen verwiesen werden.

  ```powershell
  'CONTOSO\Administrator' -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  ```

  ```Output
  FABRIKAM\Administrator
  ```

Der `$&` Ausdruck stellt den gesamten übereinstimmenden Text dar.

```powershell
'Gobble' -replace 'Gobble', '$& $&'
```

```Output
Gobble Gobble
```

> [!WARNING]
> Da das `$` Zeichen bei der Zeichen folgen Erweiterung verwendet wird, müssen Sie Literalzeichenfolgen mit Ersetzung verwenden oder das `$` Zeichen mit Escapezeichen versehen.
>
> ```powershell
> 'Hello World' -replace '(\w+) \w+', '$1 Universe'
> "Hello World" -replace "(\w+) \w+", "`$1 Universe"
> ```
>
> ```Output
> Hello Universe
> Hello Universe
> ```
>
> Wenn Sie `$` als Literalzeichen verwenden möchten, verwenden Sie `$$` anstelle der normalen Escapezeichen. Wenn doppelte Anführungszeichen verwendet werden, werden trotzdem alle Instanzen von mit Escapezeichen versehen, `$` um eine falsche Ersetzung
>
> ```powershell
> '5.72' -replace '(.+)', '$$$1'
> "5.72" -replace "(.+)", "`$`$`$1"
> ```
>
> ```Output
> $5.72
> $5.72
> ```

Weitere Informationen finden Sie unter Ersetzungen [in regulären Ausdrücken](/dotnet/standard/base-types/substitutions-in-regular-expressions).

## <a name="see-also"></a>Weitere Informationen:

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Operators](about_Operators.md)
