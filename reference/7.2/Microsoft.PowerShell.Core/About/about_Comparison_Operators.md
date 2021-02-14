---
description: Beschreibt die Operatoren, die Werte in PowerShell vergleichen.
Locale: en-US
ms.date: 01/20/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: 2ccd631083ddc06d25f2c3b4733223cca2e89d44
ms.sourcegitcommit: 77f6225ab0c8ea9faa1fe46b2ea15c178ec170e3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2021
ms.locfileid: "100500245"
---
# <a name="about-comparison-operators"></a>Informationen zu Vergleichs Operatoren

## <a name="short-description"></a>Kurze Beschreibung

Die Vergleichs Operatoren in PowerShell können entweder zwei Werte vergleichen oder Elemente einer Auflistung mit einem Eingabe Wert filtern.

## <a name="long-description"></a>Lange Beschreibung

Mit Vergleichs Operatoren können Sie Werte vergleichen oder Werte suchen, die den angegebenen Mustern entsprechen. PowerShell umfasst die folgenden Vergleichs Operatoren:

|    Typ     |   Operator   |              Vergleichstest              |
| ----------- | ------------ | ----------------------------------------- |
| Gleichheit    | -eq          | equals                                    |
|             | -ne          | ungleich                                |
|             | -gt          | Größer als                              |
|             | -ge          | Größer als oder gleich                     |
|             | -lt          | Kleiner als                                 |
|             | -le          | Kleiner als oder gleich                        |
| Matching    | -like        | Zeichenfolge entspricht Platzhalter Muster           |
|             | -notlike     | Zeichenfolge entspricht nicht dem Platzhalter Muster    |
|             | -match       | Zeichenfolge entspricht dem Regex-Muster              |
|             | -notmatch    | die Zeichenfolge entspricht nicht dem Regex-Muster.       |
| Ersatz | -Replace     | ersetzt Zeichen folgen, die einem Regex-Muster entsprechen |
| Containment | -contains    | die Sammlung enthält einen Wert.               |
|             | -notcontains | die Sammlung enthält keinen Wert.       |
|             | -in          | Wert ist in einer Sammlung                  |
|             | -NOTIN       | der Wert ist nicht in einer Sammlung.              |
| type        | -ist          | beide Objekte weisen denselben Typ auf.            |
|             | -IsNot       | die Objekte weisen nicht denselben Typ auf.         |

## <a name="common-features"></a>Allgemeine Funktionen

Standardmäßig wird bei allen Vergleichs Operatoren die Groß-/Kleinschreibung beachtet. Um die Groß-/Kleinschreibung für Vergleichs Operatoren zu erstellen, fügen Sie `c` nach dem ein `-` . Beispielsweise `-ceq` ist die Version von mit Beachtung der Groß-/Kleinschreibung `-eq` . Um die Groß-/Kleinschreibung nicht explizit explizit zu gestalten, fügen Sie eine `i` vor hinzu `-` . Beispielsweise `-ieq` ist die explizite Version von ohne Beachtung der Groß-/Kleinschreibung `-eq` .

Wenn die Eingabe eines Operators ein skalarer Wert ist, gibt der Operator einen **booleschen** Wert zurück. Wenn die Eingabe eine Auflistung ist, gibt der Operator die Elemente der Auflistung zurück, die dem rechten Wert des Ausdrucks entsprechen.
Wenn in der Auflistung keine Übereinstimmungen vorhanden sind, geben Vergleichs Operatoren ein leeres Array zurück. Beispiel:

```powershell
$a = (1, 2 -eq 3)
$a.GetType().Name
$a.Count
```

```output
Object[]
0
```

Es gibt ein paar Ausnahmen:

- Der Containment-und der Type-Operator geben immer einen **booleschen** Wert zurück.
- Der `-replace` Operator gibt das Ersetzungs Ergebnis zurück.
- Die `-match` `-notmatch` Operatoren und füllen auch die `$Matches` Automatische Variable auf.

## <a name="equality-operators"></a>Gleichheitsoperatoren

### <a name="-eq-and--ne"></a>-eq und -ne

Wenn die linke Seite Skalar ist, wird `-eq` **true** zurückgegeben, wenn die Rechte Seite eine genaue Entsprechung ist; andernfalls wird `-eq` **false** zurückgegeben. `-ne` hat das Gegenteil. gibt **false** zurück, wenn beide Seiten einander entsprechen. Andernfalls wird `-ne` true zurückgegeben.

Beispiel:

```powershell
2 -eq 2                 # Output: True
2 -eq 3                 # Output: False
"abc" -eq "abc"         # Output: True
"abc" -eq "abc", "def"  # Output: False
"abc" -ne "def"         # Output: True
"abc" -ne "abc"         # Output: False
"abc" -ne "abc", "def"  # Output: True
```

Wenn die linke Seite eine Auflistung ist, gibt die Elemente zurück, die `-eq` der rechten Seite entsprechen, während `-ne` Sie von herausgefiltert werden.

Beispiel:

```powershell
1,2,3 -eq 2             # Output: 2
"abc", "def" -eq "abc"  # Output: abc
"abc", "def" -ne "abc"  # Output: def
```

Diese Operatoren verarbeiten alle Elemente der Auflistung. Beispiel:

```powershell
"zzz", "def", "zzz" -eq "zzz"
```

```output
zzz
zzz
```

Die Gleichheits Operatoren akzeptieren zwei Objekte, nicht nur einen skalaren oder eine Auflistung.
Das Vergleichs Ergebnis ist jedoch für den Endbenutzer nicht unbedingt sinnvoll.
Im folgenden Beispiel wird das Problem veranschaulicht.

```powershell
class MyFileInfoSet {
    [String]$File
    [Int64]$Size
}
$a = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$b = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$a -eq $b
```

```Output
False
```

In diesem Beispiel haben wir zwei Objekte mit identischen Eigenschaften erstellt. Das Ergebnis der Gleichheits Überprüfung ist jedoch **falsch** , da es sich um unterschiedliche Objekte handelt. Um vergleichbare Klassen zu erstellen, müssen Sie [System. IEquatable \<T> ][2] in ihrer Klasse implementieren. Im folgenden Beispiel wird die partielle Implementierung einer **myfileinfoset** -Klasse veranschaulicht, die " [System. \<T> IEquatable][2] " implementiert und zwei Eigenschaften hat: " **File** " und " **size**". Die `Equals()` -Methode gibt true zurück, wenn die Datei-und Größen Eigenschaften von zwei **myfileinfoset** -Objekten identisch sind.

```powershell
class MyFileInfoSet : System.IEquatable[Object] {
    [String]$File
    [Int64]$Size

    [bool] Equals([Object] $obj) {
        return ($this.File -eq $obj.File) -and ($this.Size -eq $obj.Size)
    }
}
$a = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$b = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$a -eq $b
```

```Output
True
```

Ein hervorragendes Beispiel für den Vergleich beliebiger Objekte besteht darin, herauszufinden, ob Sie NULL sind. Wenn Sie jedoch bestimmen müssen, ob eine Variable ist `$null` , müssen Sie `$null` auf der linken Seite des Gleichheits Operators ablegen. Wenn Sie es auf der rechten Seite platzieren, ist das nicht das, was Sie erwarten.

Beispielsweise `$a` ein Array, das NULL-Elemente enthält:

```powershell
$a = 1, 2, $null, 4, $null, 6
```

Die folgenden Tests, die `$a` nicht NULL sind.

```powershell
$null -ne $a
```

```output
False
```

Der folgende Filter filtert jedoch alle NULL-Elemente aus `$a` :

```powershell
$a -ne $null # Output: 1, 2, 4, 6
```

```output
1
2
4
6
```

### <a name="-gt--ge--lt-and--le"></a>-gt,-ge,-lt und-Le

`-gt`, `-ge` , `-lt` und `-le` Verhalten sich ähnlich. Wenn beide Seiten Skalar sind, geben Sie " **true** " oder " **false** " zurück, je nachdem, wie die beiden Seiten verglichen werden

| Betreiber | Gibt "true" zurück, wenn...                   |
| -------- | -------------------------------------- |
| -gt      | Die linke Seite ist größer.          |
| -ge      | Die linke Seite ist größer als oder gleich. |
| -lt      | Die linke Seite ist kleiner.          |
| -le      | Die linke Seite ist kleiner oder gleich. |

In den folgenden Beispielen geben alle-Anweisungen true zurück.

```powershell
8 -gt 6  # Output: True
8 -ge 8  # Output: True
6 -lt 8  # Output: True
8 -le 8  # Output: True
```

> [!NOTE]
> In den meisten Programmiersprachen ist der größer-als-Operator `>` . In PowerShell wird dieses Zeichen für die Umleitung verwendet. Weitere Informationen finden Sie unter [about_Redirection][3].

Wenn die linke Seite eine Auflistung ist, vergleichen diese Operatoren jeden Member der Auflistung mit der rechten Seite. Abhängig von ihrer Logik behalten Sie den Member bei oder verwerfen ihn.

Beispiel:

```powershell
$a=5, 6, 7, 8, 9

Write-Output "Test collection:"
$a

Write-Output "`nMembers greater than 7"
$a -gt 7

Write-Output "`nMembers greater than or equal to 7"
$a -ge 7

Write-Output "`nMembers smaller than 7"
$a -lt 7

Write-Output "`nMembers smaller than or equal to 7"
$a -le 7
```

```output
Test collection:
5
6
7
8
9

Members greater than 7
8
9

Members greater than or equal to 7
7
8
9

Members smaller than 7
5
6

Members smaller than or equal to 7
5
6
7
```

Diese Operatoren arbeiten mit jeder Klasse, die [System. ivergleichbare][1]implementiert.

Beispiele:

```powershell
# Date comparison
[DateTime]'2001-11-12' -lt [DateTime]'2020-08-01' # True

# Sorting order comparison
'a' -lt 'z'           # True; 'a' comes before 'z'
'macOS' -ilt 'MacOS'  # False
'MacOS' -ilt 'macOS'  # False
'macOS' -clt 'MacOS'  # True; 'm' comes before 'M'
```

Im folgenden Beispiel wird veranschaulicht, dass kein Symbol auf einer American QWERTY-Tastatur vorhanden ist, die nach "a" sortiert wird. Er fügt eine Menge, die alle Symbole enthält, an den `-gt` Operator an, um Sie mit "a" zu vergleichen. Die Ausgabe ist ein leeres Array.

```powershell
$a=' ','`','~','!','@','#','$','%','^','&','*','(',')','_','+','-','=',
   '{','}','[',']',':',';','"','''','\','|','/','?','.','>',',','<'
$a -gt 'a'
# Output: Nothing
```

Wenn die beiden Seiten der Operatoren nicht angemessen vergleichbar sind, wird ein Fehler ohne Abbruch ausgegeben.

## <a name="matching-operators"></a>Vergleichs Operatoren

Die übereinstimmenden Operatoren ( `-like` , `-notlike` , `-match` und `-notmatch` ) suchen Elemente, die mit einem angegebenen Muster übereinstimmen oder nicht übereinstimmen. Das Muster für `-like` und `-notlike` ist ein Platzhalter Ausdruck (mit `*` , `?` und `[ ]` ), während `-match` und `-notmatch` einen regulären Ausdruck (Regex) akzeptieren.

Die Syntax ist:

```
<string[]> -like    <wildcard-expression>
<string[]> -notlike <wildcard-expression>
<string[]> -match    <regular-expression>
<string[]> -notmatch <regular-expression>
```

Wenn die Eingabe dieser Operatoren ein skalarer Wert ist, wird ein **boolescher** Wert zurückgegeben. Wenn die Eingabe eine Auflistung von Werten ist, geben die Operatoren alle übereinstimmenden Member zurück. Wenn keine Übereinstimmungen in einer Auflistung vorhanden sind, geben die Operatoren ein leeres Array zurück.

### <a name="-like-and--notlike"></a>-like und-notlike

`-like`und `-notlike` Verhalten sich ähnlich wie `-eq` und `-ne` , aber die Rechte Seite könnte eine Zeichenfolge sein, [](about_Wildcards.md)die Platzhalter enthält.

Beispiel:

```powershell
"PowerShell" -like    "*shell"           # Output: True
"PowerShell" -notlike "*shell"           # Output: False
"PowerShell" -like    "Power?hell"       # Output: True
"PowerShell" -notlike "Power?hell"       # Output: False
"PowerShell" -like    "Power[p-w]hell"   # Output: True
"PowerShell" -notlike "Power[p-w]hell"   # Output: False

"PowerShell", "Server" -like "*shell"    # Output: PowerShell
"PowerShell", "Server" -notlike "*shell" # Output: Server
```

### <a name="-match-and--notmatch"></a>-Match und-notmatch

`-match` und `-notmatch` verwenden reguläre Ausdrücke, um in den linksseitigen Werten nach Mustern zu suchen. Reguläre Ausdrücke können komplexe Muster wie e-Mail-Adressen, UNC-Pfade oder formatierte Telefonnummern erfüllen. Die Zeichenfolge auf der rechten Seite muss den Regeln für [reguläre Ausdrücke](about_Regular_Expressions.md) entsprechen.

Skalare Beispiele:

```powershell
# Partial match test, showing how differently -match and -like behave
"PowerShell" -match 'shell'        # Output: True
"PowerShell" -like  'shell'        # Output: False

# Regex syntax test
"PowerShell" -match    '^Power\w+' # Output: True
'bag'        -notmatch 'b[iou]g'   # Output: True
```

Wenn es sich bei der Eingabe um eine Auflistung handelt, geben die Operatoren die übereinstimmenden Member der Auflistung zurück.

Beispiele für Sammlungen:

```powershell
"PowerShell", "Super PowerShell", "Power's hell" -match '^Power\w+'
# Output: PowerShell

"Rhell", "Chell", "Mel", "Smell", "Shell" -match "hell"
# Output: Rhell, Chell, Shell

"Bag", "Beg", "Big", "Bog", "Bug"  -match 'b[iou]g'
#Output: Big, Bog, Bug

"Bag", "Beg", "Big", "Bog", "Bug"  -notmatch 'b[iou]g'
#Output: Bag, Beg
```

`-match` und `-notmatch` unterstützen Regex-Erfassungs Gruppen. Jedes Mal, wenn Sie ausgeführt werden, überschreiben Sie die `$Matches` Automatische Variable. Wenn `<input>` eine Auflistung ist, `$Matches` ist die Variable `$null` . `$Matches` ist eine **Hash Tabelle** , die immer über einen Schlüssel mit dem Namen ' 0 ' verfügt, der die gesamte Entsprechung speichert. Wenn der reguläre Ausdruck Erfassungs Gruppen enthält, `$Matches` enthält die zusätzliche Schlüssel für jede Gruppe.

Beispiel:

```powershell
$string = 'The last logged on user was CONTOSO\jsmith'
$string -match 'was (?<domain>.+)\\(?<user>.+)'

$Matches

Write-Output "`nDomain name:"
$Matches.domain

Write-Output "`nUser name:"
$Matches.user
```

```output
True

Name                           Value
----                           -----
domain                         CONTOSO
user                           jsmith
0                              was CONTOSO\jsmith

Domain name:
CONTOSO

User name:
jsmith
```

Weitere Informationen finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md).

## <a name="replacement-operator"></a>Ersatz Operator

### <a name="replacement-with-regular-expressions"></a>Ersetzung durch reguläre Ausdrücke

Ebenso `-match` verwendet der- `-replace` Operator reguläre Ausdrücke, um nach dem angegebenen Muster zu suchen. Im Gegensatz `-match` dazu werden die Übereinstimmungen durch einen anderen angegebenen Wert ersetzt.

Syntax:

```
<input> -replace <regular-expression>, <substitute>
```

Der-Operator ersetzt den gesamten oder einen Teil eines Werts durch den angegebenen Wert mithilfe regulärer Ausdrücke. Sie können den-Operator für viele Verwaltungsaufgaben verwenden, z. b. das Umbenennen von Dateien. Der folgende Befehl ändert z. b. die Dateinamen Erweiterungen aller `.txt` Dateien in `.log` :

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

Standardmäßig `-replace` wird bei dem Operator die Groß-/Kleinschreibung nicht beachtet. Verwenden Sie, um die Groß-/Kleinschreibung zu beachten `-creplace` Verwenden Sie, um die Groß-/Kleinschreibung explizit zu Unternehmen `-ireplace` .

Beispiele:

```powershell
"book" -ireplace "B", "C" # Case insensitive
"book" -creplace "B", "C" # Case-sensitive; hence, nothing to replace
```

```Output
Cook
book
```

### <a name="regular-expressions-substitutions"></a>Reguläre Ausdrucks Ersetzungen

Es ist auch möglich, reguläre Ausdrücke zum dynamischen Ersetzen von Text mithilfe von Erfassungs Gruppen und Ersetzungen zu verwenden. Auf Erfassungs Gruppen kann in der `<substitute>` Zeichenfolge mit dem Dollarzeichen ( `$` ) vor der Gruppen Kennung verwiesen werden.

Im folgenden Beispiel `-replace` akzeptiert der-Operator einen Benutzernamen in der Form `DomainName\Username` und konvertiert in das- `Username@DomainName` Format:

```powershell
$SearchExp = '^(?<DomainName>[\w-.]+)\\(?<Username>[\w-.]+)$'
$ReplaceExp = '${Username}@${DomainName}'

'Contoso.local\John.Doe' -replace $SearchExp,$ReplaceExp
```

```output
John.Doe@Contoso.local
```

> [!WARNING]
> Das `$` Zeichen verfügt über syntatic-Rollen in PowerShell und regulären Ausdrücken:
>
> - In PowerShell werden zwischen doppelten Anführungszeichen Variablen festgelegt und als Teil Ausdruck bezeichnet.
> - In Regex-Such Zeichenfolgen gibt es das Ende der Zeile an.
> - In Regex-Ersetzungs Zeichenfolgen bezeichnet sie erfasste Gruppen. Stellen Sie sicher, dass Sie die regulären Ausdrücke zwischen einfachen Anführungszeichen platzieren, oder fügen Sie vor Ihnen ein Graviszeichen- `` ` `` Zeichen () ein.

Beispiel:

```powershell
$1 = 'Goodbye'

'Hello World' -replace '(\w+) \w+', "$1 Universe"
# Output: Goodbye Universe

'Hello World' -replace '(\w+) \w+', '$1 Universe'
# Output: Hello Universe
```

`$$` in Regex steht für einen Literalwert `$` . Dies `$$` in der Ersetzungs Zeichenfolge zum Einschließen eines Literals `$` in den resultierenden Austausch. Beispiel:

```powershell
'5.72' -replace '(.+)', '$ $1' # Output: $ 5.72
'5.72' -replace '(.+)', '$$$1' # Output: $5.72
'5.72' -replace '(.+)', '$$1'  # Output: $1
```

Weitere Informationen finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md) und Ersetzungen [in regulären Ausdrücken][4].

### <a name="substituting-in-a-collection"></a>Ersetzen in einer Auflistung

Wenn der `<input>` für den `-replace` Operator eine Auflistung ist, wendet PowerShell die Ersetzung auf jeden Wert in der Auflistung an. Beispiel:

```powershell
"B1","B2","B3","B4","B5" -replace "B", 'a'
a1
a2
a3
a4
a5
```

### <a name="replacement-with-a-script-block"></a>Ersetzung durch einen Skriptblock

In PowerShell 6 und höher akzeptiert der `-replace` Operator auch einen Skriptblock, der die Ersetzung durchführt. Der Skriptblock wird bei jeder Übereinstimmung einmal ausgeführt.

Syntax:

```powershell
<String> -replace <regular-expression>, {<Script-block>}
```

Verwenden Sie im Skriptblock die `$_` Automatische Variable, um auf den zu ersetzenden Eingabetext und andere nützliche Informationen zuzugreifen. Der Klassentyp dieser Variablen ist [System. Text. RegularExpressions. Match][2].

Im folgenden Beispiel wird jede Sequenz von drei Ziffern durch die Zeichen Entsprechungen ersetzt. Der Skriptblock wird für jeden Satz von drei Ziffern ausgeführt, die ersetzt werden müssen.

```powershell
"072101108108111" -replace "\d{3}", {return [char][int]$_.Value}
```

```output
Hello
```

## <a name="containment-operators"></a>Containment-Operatoren

Die Containment-Operatoren ( `-contains` , `-notcontains` , `-in` und `-notin` ) ähneln den Gleichheits Operatoren, mit dem Unterschied, dass Sie immer einen **booleschen** Wert zurückgeben, auch wenn die Eingabe eine Auflistung ist. Diese Operatoren enden den Vergleich ab, sobald die erste Übereinstimmung erkannt wird, während die Gleichheits Operatoren alle Eingabeelemente auswerten. In einer sehr großen Auflistung geben diese Operatoren schneller zurück als die Gleichheits Operatoren.

Syntax:

```
<Collection> -contains <Test-object>
<Collection> -notcontains <Test-object>
<Test-object> -in <Collection>
<Test-object> -notin <Collection>
```

### <a name="-contains-and--notcontains"></a>-enthält und-notenthält

Diese Operatoren erkennen, ob ein Satz ein bestimmtes Element enthält. `-contains` gibt true zurück, wenn die Rechte Seite (Testobjekt) mit einem der Elemente in der Menge übereinstimmt. `-notcontains` gibt stattdessen false zurück. Wenn das Testobjekt eine Auflistung ist, verwenden diese Operatoren Verweis Gleichheit, d. h. Sie überprüfen, ob eines der Elemente des Satzes dieselbe Instanz des Testobjekts ist.

Beispiele:

```powershell
"abc", "def" -contains "def"                  # Output: True
"abc", "def" -notcontains "def"               # Output: False
"Windows", "PowerShell" -contains "Shell"     # Output: False
"Windows", "PowerShell" -notcontains "Shell"  # Output: True
"abc", "def", "ghi" -contains "abc", "def"    # Output: False
"abc", "def", "ghi" -notcontains "abc", "def" # Output: True
```

Komplexere Beispiele:

```powershell
$DomainServers = "ContosoDC1","ContosoDC2","ContosoFileServer","ContosoDNS",
                 "ContosoDHCP","ContosoWSUS"
$thisComputer  = "ContosoDC2"

$DomainServers -contains $thisComputer
# Output: True

$a = "abc", "def"
"abc", "def", "ghi" -contains $a # Output: False
$a, "ghi" -contains $a           # Output: True
```

### <a name="-in-and--notin"></a>-in und-NOTIN

Die `-in` `notin` Operatoren und wurden in PowerShell 3 als syntaktische Umkehrung der der `contains` Operatoren und eingeführt `-notcontain` . `-in` gibt **true** zurück, wenn die linke Seite `<test-object>` mit einem der Elemente in der Menge übereinstimmt. `-notin` gibt stattdessen **false** zurück. Wenn das Testobjekt eine Menge ist, verwenden diese Operatoren Verweis Gleichheit, um zu überprüfen, ob eines der Elemente der Gruppe dieselbe Instanz des Testobjekts ist.

In den folgenden Beispielen werden dieselben Schritte wie in den Beispielen für `-contain` und `-notcontain` durchzuführen, aber Sie werden `-in` stattdessen mit und geschrieben `-notin` .

```powershell
"def" -in "abc", "def"                  # Output: True
"def" -notin "abc", "def"               # Output: False
"Shell" -in "Windows", "PowerShell"     # Output: False
"Shell" -notin "Windows", "PowerShell"  # Output: True
"abc", "def" -in "abc", "def", "ghi"    # Output: False
"abc", "def" -notin "abc", "def", "ghi" # Output: True
```

Komplexere Beispiele:

```powershell
$DomainServers = "ContosoDC1","ContosoDC2","ContosoFileServer","ContosoDNS",
                 "ContosoDHCP","ContosoWSUS"
$thisComputer  = "ContosoDC2"

$thisComputer -in $DomainServers
# Output: True

$a = "abc", "def"
$a -in "abc", "def", "ghi" # Output: False
$a -in $a, "ghi"           # Output: True
```

## <a name="type-comparison"></a>Typvergleich

Die typvergleichs Operatoren ( `-is` und `-isnot` ) werden verwendet, um zu bestimmen, ob es sich bei einem Objekt um einen bestimmten Typ handelt.

Syntax:

```powershell
<object> -is <type-reference>
<object> -isnot <type-reference>
```

Beispiel:

```powershell
$a = 1
$b = "1"
$a -is [int]           # Output: True
$a -is $b.GetType()    # Output: False
$b -isnot [int]        # Output: True
$a -isnot $b.GetType() # Output: True
```

## <a name="see-also"></a>SIEHE AUCH

- [about_Operators](about_Operators.md)
- [about_Regular_Expressions](about_Regular_Expressions.md)
- [about_Wildcards](about_Wildcards.md)
- [Compare-Object](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [ForEach-Objekt](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [Where-Object](xref:Microsoft.PowerShell.Core.Where-Object)

[1]: /dotnet/api/system.icomparable
[2]: /dotnet/api/system.iequatable-1
[3]: /dotnet/api/system.text.regularexpressions.match
[4]: about_Redirection.md#potential-confusion-with-comparison-operators
[5]: /dotnet/standard/base-types/substitutions-in-regular-expressions
