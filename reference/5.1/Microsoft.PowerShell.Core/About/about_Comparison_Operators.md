---
description: Beschreibt die Operatoren, die Werte in PowerShell vergleichen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: b6076e20ad3ecbe9f2def157bb20bdb3bee5b7ad
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224532"
---
# <a name="about-comparison-operators"></a>Informationen zu Vergleichs Operatoren

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt die Operatoren, die Werte in PowerShell vergleichen.

## <a name="long-description"></a>Lange Beschreibung

Mit Vergleichs Operatoren können Sie Bedingungen zum Vergleichen von Werten und suchen von Werten angeben, die den angegebenen Mustern entsprechen. Wenn Sie einen Vergleichs Operator verwenden möchten, geben Sie die Werte, die Sie miteinander vergleichen möchten, mit einem Operator an, der diese Werte trennt.

PowerShell umfasst die folgenden Vergleichs Operatoren:

| type        | Operatoren    | Beschreibung                                 |
| ----------- | ------------ | --------------------------------------------|
| Gleichheit    | -eq          | Ist gleich                                      |
|             | -ne          | ungleich                                  |
|             | -gt          | Größer als                                |
|             | -ge          | Größer als oder gleich                       |
|             | -lt          | Kleiner als                                   |
|             | -le          | Kleiner als oder gleich                          |
|             |              |                                             |
| Matching    | -like        | Gibt "true" zurück, wenn die Zeichenfolge   |
|             |              | pattern                                     |
|             | -notlike     | Gibt true zurück, wenn die Zeichenfolge nicht entspricht.     |
|             |              | Platzhalter Muster                            |
|             | -match       | Gibt true zurück, wenn die Zeichenfolge dem regulären Ausdruck entspricht      |
|             |              | Bau $Matches enthält übereinstimmende Zeichen folgen |
|             | -notmatch    | Gibt true zurück, wenn die Zeichenfolge nicht entspricht.     |
|             |              | Regex-Muster; $Matches enthält Übereinstimmungen.   |
|             |              | Zeichenfolgen                                     |
|             |              |                                             |
| Containment | -contains    | Gibt true zurück, wenn der Verweis Wert enthalten ist |
|             |              | in einer Sammlung                             |
|             | -notcontains | Gibt true zurück, wenn der Verweis Wert nicht       |
|             |              | in einer Auflistung enthalten                   |
|             | -in          | Gibt true zurück, wenn der Testwert in einer |
|             |              | collection                                  |
|             | -NOTIN       | Gibt true zurück, wenn der Testwert nicht enthalten ist.  |
|             |              | in einer Sammlung                             |
|             |              |                                             |
| Ersetzung | -Replace     | Ersetzt ein Zeichen folgen Muster                   |
|             |              |                                             |
| type        | -ist          | Gibt "true" zurück, wenn beide Objekte gleich sind.    |
|             |              | type                                        |
|             | -IsNot       | Gibt "true" zurück, wenn die Objekte nicht gleich sind.|
|             |              | type                                        |

Standardmäßig wird bei allen Vergleichs Operatoren die Groß-/Kleinschreibung beachtet. Um bei einem Vergleichs Operator die Groß-/Kleinschreibung zu beachten, stellen Sie dem Operator Namen eine vor `c` . Beispielsweise ist die Version von mit Beachtung der Groß-/Kleinschreibung `-eq` `-ceq` . Um die Groß-/Kleinschreibung explizit explizit zu machen, stellen Sie dem-Operator eine vor `i` . Beispielsweise ist die Version von, bei der die Groß-/Kleinschreibung nicht beachtet `-eq` wird `-ieq`

Wenn die Eingabe für einen Operator ein skalarer Wert ist, geben Vergleichs Operatoren einen booleschen Wert zurück. Wenn die Eingabe eine Auflistung von Werten ist, geben die Vergleichs Operatoren alle übereinstimmenden Werte zurück. Wenn keine Übereinstimmungen in einer Auflistung vorhanden sind, geben Vergleichs Operatoren ein leeres Array zurück.

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

Die Ausnahmen sind die Containment-Operatoren, die in-Operatoren und die Typoperatoren, die immer einen **booleschen** Wert zurückgeben.

> [!NOTE]
> Wenn Sie einen Wert mit vergleichen müssen, `$null` sollten Sie `$null` auf der linken Seite des Vergleichs platzieren. Wenn Sie `$null` mit einem **Objekt []** vergleichen, ist das Ergebnis " **false** ", da das Vergleichs Objekt ein Array ist. Wenn Sie ein Array mit vergleichen `$null` , filtert der Vergleich alle `$null` im Array gespeicherten Werte heraus. Beispiel:
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

### <a name="equality-operators"></a>Gleichheitsoperatoren

Die Gleichheits Operatoren ( `-eq` , `-ne` ) geben den Wert true oder die Übereinstimmungen zurück, wenn mindestens ein Eingabe Wert mit dem angegebenen Muster identisch ist. Das gesamte Muster muss mit einem ganzen Wert identisch sein.

Beispiel:

#### <a name="-eq"></a>-eq

Description: entspricht. Schließt einen identischen Wert ein.

Beispiel:

```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2
PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```

#### <a name="-ne"></a>-ne

Description: nicht gleich. Enthält einen anderen Wert.

Beispiel:

```powershell
PS> "abc" -ne "def"
True

PS> "abc" -ne "abc"
False

PS> "abc" -ne "abc", "def"
True

PS> "abc", "def" -ne "abc"
def
```

#### <a name="-gt"></a>-gt

Beschreibung: größer als.

Beispiel:

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> Dies sollte nicht mit `>` dem Operator "größer als" in vielen anderen Programmiersprachen verwechselt werden. In PowerShell `>` wird für die Umleitung verwendet. Weitere Informationen finden Sie unter [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).

#### <a name="-ge"></a>-ge

Description: größer als oder gleich.

Beispiel:

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

#### <a name="-lt"></a>-lt

Beschreibung: kleiner als.

Beispiel:

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

#### <a name="-le"></a>-le

Description: kleiner als oder gleich.

Beispiel:

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

### <a name="matching-operators"></a>Vergleichs Operatoren

Die LIKE-Operatoren ( `-like` und `-notlike` ) suchen nach Elementen, die einem angegebenen Muster unter Verwendung von Platzhalter Ausdrücken entsprechen oder nicht.

Die Syntax ist:

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

Die Vergleichs Operatoren ( `-match` und `-notmatch` ) suchen nach Elementen, die einem angegebenen Muster entsprechen oder nicht mit regulären Ausdrücken identisch sind.

Die Match-Operatoren füllen die `$Matches` Automatische Variable auf, wenn die Eingabe (das linke Argument) für den Operator ein einzelnes skalares Objekt ist. Wenn die Eingabe Skalar ist, `-match` geben die `-notmatch` Operatoren und einen booleschen Wert zurück und legen den Wert der `$Matches` automatischen Variablen auf die übereinstimmenden Komponenten des Arguments fest.

Die Syntax ist:

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

#### <a name="-like"></a>-like

Description: Match mit dem Platzhalter Zeichen ( \* ).

Beispiel:

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

#### <a name="-notlike"></a>-notlike

Beschreibung: entspricht nicht der Verwendung des Platzhalter Zeichens ( \* ).

Beispiel:

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a>-match

Description: entspricht einer Zeichenfolge unter Verwendung regulärer Ausdrücke. Wenn die Eingabe Skalar ist, füllt Sie die `$Matches` Automatische Variable auf.

Wenn es sich bei der Eingabe um eine Auflistung handelt, `-match` `-notmatch` geben die Operatoren und die übereinstimmenden Member dieser Auflistung zurück, aber der Operator füllt nicht die `$Matches` Variable auf.

Der folgende Befehl übermittelt z. b. eine Auflistung von Zeichen folgen an den- `-match` Operator. Der- `-match` Operator gibt die Elemente in der Auflistung zurück, die mit identisch sind. Die automatische Variable wird nicht aufgefüllt `$Matches` .

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

Im Gegensatz dazu übermittelt der folgende Befehl eine einzelne Zeichenfolge an den- `-match` Operator. Der `-match` -Operator gibt einen booleschen Wert zurück und füllt die `$Matches` Automatische Variable auf. Die `$Matches` Automatische Variable ist eine **Hash Tabelle**. Wenn keine Gruppierung oder Erfassung verwendet wird, wird nur ein Schlüssel aufgefüllt.
Der `0` Schlüssel stellt den gesamten Text dar, der abgeglichen wurde. Weitere Informationen zum Gruppieren und erfassen mithilfe regulärer Ausdrücke finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md).

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

Beachten Sie unbedingt, dass die `$Matches` Hash Tabelle nur das erste Vorkommen eines übereinstimmenden Musters enthält.

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> Der `0` Schlüssel ist eine **ganze** Zahl. Sie können eine beliebige **Hash Tabellen** Methode verwenden, um auf den gespeicherten Wert zuzugreifen.
>
> ```powershell
> PS> "Good Dog" -match "Dog"
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

Der `-notmatch` Operator füllt die `$Matches` Automatische Variable auf, wenn die Eingabe Skalar ist, und das Ergebnis ist false, d. h., wenn eine Entsprechung erkannt wird.

```powershell
PS> "Sunday" -notmatch "rain"
True

PS> $matches
PS>

PS> "Sunday" -notmatch "day"
False

PS> $matches

Name                           Value
----                           -----
0                              day
```

#### <a name="-notmatch"></a>-notmatch

Beschreibung: stimmt nicht mit einer Zeichenfolge. Verwendet reguläre Ausdrücke. Wenn die Eingabe Skalar ist, füllt Sie die `$Matches` Automatische Variable auf.

Beispiel:

```powershell
PS> "Sunday" -notmatch "sun"
False

PS> $matches
Name Value
---- -----
0    sun

PS> "Sunday", "Monday" -notmatch "sun"
Monday
```

### <a name="containment-operators"></a>Containment-Operatoren

Die Containment-Operatoren ( `-contains` und `-notcontains` ) ähneln den Gleichheits Operatoren. Der Containment-Operator gibt jedoch immer einen booleschen Wert zurück, auch wenn die Eingabe eine Auflistung ist.

Außerdem geben die Einschluss Operatoren im Gegensatz zu den Gleichheits Operatoren einen Wert zurück, sobald Sie die erste Übereinstimmung erkennen. Die Gleichheits Operatoren Werten alle Eingaben aus und geben dann alle Übereinstimmungen in der Auflistung zurück.

#### <a name="-contains"></a>-contains

Description: Containment-Operator. Gibt an, ob eine Auflistung von Verweis Werten einen einzelnen Testwert enthält. Gibt immer einen booleschen Wert zurück. Gibt nur dann true zurück, wenn der Testwert genau mit mindestens einem der Verweis Werte übereinstimmt.

Wenn der Testwert eine Auflistung ist, verwendet der enthält-Operator Verweis Gleichheit. Sie gibt nur dann true zurück, wenn einer der Verweis Werte dieselbe Instanz des Test Wert Objekts ist.

In einer sehr großen Auflistung gibt der `-contains` Operator Ergebnisse schneller zurück, als der Operator gleich ist.

Syntax:

`<Reference-values> -contains <Test-value>`

Beispiele:

```powershell
PS> "abc", "def" -contains "def"
True

PS> "Windows", "PowerShell" -contains "Shell"
False  #Not an exact match

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $DomainServers -contains $thisComputer
True

PS> "abc", "def", "ghi" -contains "abc", "def"
False

PS> $a = "abc", "def"
PS> "abc", "def", "ghi" -contains $a
False
PS> $a, "ghi" -contains $a
True
```

#### <a name="-notcontains"></a>-notcontains

Description: Containment-Operator. Gibt an, ob eine Auflistung von Verweis Werten einen einzelnen Testwert enthält. Gibt immer einen booleschen Wert zurück. Gibt true zurück, wenn der Testwert keine exakten Übereinstimmungen für mindestens einen der Verweis Werte ist.

Wenn der Testwert eine Auflistung ist, verwendet der Notare-Operator Verweis Gleichheit.

Syntax:

`<Reference-values> -notcontains <Test-value>`

Beispiele:

```powershell
PS> "Windows", "PowerShell" -notcontains "Shell"
True  #Not an exact match

# Get cmdlet parameters, but exclude common parameters
function get-parms ($cmdlet)
{
    $Common = "Verbose", "Debug", "WarningAction", "WarningVariable",
      "ErrorAction", "ErrorVariable", "OutVariable", "OutBuffer"

    $allparms = (Get-Command $Cmdlet).parametersets |
      foreach {$_.Parameters} |
        foreach {$_.Name} | Sort-Object | Get-Unique

    $allparms | where {$Common -notcontains $_ }
}

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $myVerbs = Get-Command -Module MyModule | foreach {$_.verb}
PS> $myVerbs | where {$ApprovedVerbs -notcontains $_}
ForEach
Sort
Tee
Where
```

#### <a name="-in"></a>-in

Description: in-Operator. Gibt an, ob ein Testwert in einer Auflistung von Verweis Werten angezeigt wird. Gibt immer als booleschen Wert zurück. Gibt nur dann true zurück, wenn der Testwert genau mit mindestens einem der Verweis Werte übereinstimmt.

Wenn der Testwert eine Auflistung ist, verwendet der in-Operator Verweis Gleichheit.
Sie gibt nur dann true zurück, wenn einer der Verweis Werte dieselbe Instanz des Test Wert Objekts ist.

Der `-in` Operator wurde in PowerShell 3,0 eingeführt.

Syntax:

`<Test-value> -in <Reference-values>`

Beispiele:

```powershell
PS> "def" -in "abc", "def"
True

PS> "Shell" -in "Windows", "PowerShell"
False  #Not an exact match

PS> "Windows" -in "Windows", "PowerShell"
True  #An exact match

PS> "Windows", "PowerShell" -in "Windows", "PowerShell", "ServerManager"
False  #Using reference equality

PS> $a = "Windows", "PowerShell"
PS> $a -in $a, "ServerManager"
True  #Using reference equality

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $thisComputer -in  $domainServers
True
```

#### <a name="-notin"></a>-NOTIN

Description: gibt an, ob ein Testwert in einer Auflistung von Verweis Werten angezeigt wird. Gibt immer einen booleschen Wert zurück. Gibt true zurück, wenn der Testwert keine genaue Entsprechung für mindestens einen der Verweis Werte ist.

Wenn der Testwert eine Auflistung ist, verwendet der in-Operator Verweis Gleichheit.
Sie gibt nur dann true zurück, wenn einer der Verweis Werte dieselbe Instanz des Test Wert Objekts ist.

Der `-notin` Operator wurde in PowerShell 3,0 eingeführt.

Syntax:

`<Test-value> -notin <Reference-values>`

Beispiele:

```powershell
PS> "def" -notin "abc", "def"
False

PS> "ghi" -notin "abc", "def"
True

PS> "Shell" -notin "Windows", "PowerShell"
True  #Not an exact match

PS> "Windows" -notin "Windows", "PowerShell"
False  #An exact match

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $MyVerbs = Get-Command -Module MyModule | foreach {$_.verb}

PS> $MyVerbs | where {$_ -notin $ApprovedVerbs}
ForEach
Sort
Tee
Where
```

### <a name="replacement-operator"></a>Ersatz Operator

Der- `-replace` Operator ersetzt den gesamten oder einen Teil eines Werts durch den angegebenen Wert mithilfe regulärer Ausdrücke. Sie können den- `-replace` Operator für viele Verwaltungsaufgaben verwenden, z. b. das Umbenennen von Dateien. Der folgende Befehl ändert z. b. die Dateinamen Erweiterungen aller txt-Dateien in. log:

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

Die Syntax des- `-replace` Operators lautet wie folgt, wobei der `<original>` Platzhalter die zu ersetzenden Zeichen darstellt und der `<substitute>` Platzhalter die Zeichen darstellt, die Sie ersetzen:

`<input> <operator> <original>, <substitute>`

Standardmäßig `-replace` wird bei dem Operator die Groß-/Kleinschreibung nicht beachtet. Verwenden Sie, um die Groß-/Kleinschreibung zu beachten `-creplace` Verwenden Sie, um die Groß-/Kleinschreibung explizit zu Unternehmen `-ireplace` .

Betrachten Sie die folgenden Beispiele:

```powershell
PS> "book" -replace "B", "C"
```

```Output
Cook
```

```powershell
"book" -ireplace "B", "C"
```

```Output
Cook
```

```powershell
"book" -creplace "B", "C"
```

```Output
book
```

Es ist auch möglich, reguläre Ausdrücke zum dynamischen Ersetzen von Text mithilfe von Erfassungs Gruppen und Ersetzungen zu verwenden. Weitere Informationen finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md).

#### <a name="substitutions-in-regular-expressions"></a>Ersetzungen in regulären Ausdrücken

Außerdem kann in der Zeichenfolge auf Erfassungs Gruppen verwiesen werden \<substitute\> .
Dies erfolgt mithilfe des `$` Zeichens vor dem Gruppen Bezeichner.

Zwei Möglichkeiten, auf Erfassungs Gruppen zu verweisen, sind nach **Nummer** und **Name** .

- Nach **Zahlen** -
   Erfassungs Gruppen werden von links nach rechts nummeriert.

  ```powershell
  "John D. Smith" -replace "(\w+) (\w+)\. (\w+)", '$1.$2.$3@contoso.com'
  ```

  ```Output
  John.D.Smith@contoso.com
  ```

- Nach **Namen** -
   können Sie auch nach Namen Erfassungs Gruppen referenziert werden.

  ```powershell
  "CONTOSO\Administrator" -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  ```

  ```Output
  FABRIKOM\Administrator
  ```

> [!WARNING]
> Da das `$` Zeichen bei der Zeichen folgen Erweiterung verwendet wird, müssen Sie Literalzeichenfolgen mit Ersetzung verwenden oder das `$` Zeichen mit Escapezeichen versehen.
>
> ```powershell
> 'Hello World' -replace '(\w+) \w+', "`$1 Universe"
> ```
>
> ```Output
> Hello Universe
> ```
>
> Da das `$` Zeichen in der Ersetzung verwendet wird, müssen Sie außerdem alle Instanzen in der Zeichenfolge mit Escapezeichen versehen.
>
> ```powershell
> '5.72' -replace '(.+)', '$$$1'
> ```
>
> ```Output
> $5.72
> ```

Weitere Informationen finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md) und Ersetzungen [in regulären Ausdrücken](/dotnet/standard/base-types/substitutions-in-regular-expressions) .

### <a name="type-comparison"></a>Typvergleich

Die typvergleichs Operatoren ( `-is` und `-isnot` ) werden verwendet, um zu bestimmen, ob es sich bei einem Objekt um einen bestimmten Typ handelt.

#### <a name="-is"></a>-ist

Syntax:

`<object> -is <type reference>`

Beispiel:

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

#### <a name="-isnot"></a>-IsNot

Syntax:

`<object> -isnot <type reference>`

Beispiel:

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a>SIEHE AUCH

- [about_Operators](about_Operators.md)
- [about_Regular_Expressions](about_Regular_Expressions.md)
- [about_Wildcards](about_Wildcards.md)
- [Compare-Object](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [ForEach-Objekt](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [Where-Object](xref:Microsoft.PowerShell.Core.Where-Object)
