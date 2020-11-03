---
description: Beschreibt die Operatoren, die Arithmetik in PowerShell ausführen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arithmetic_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arithmetic_Operators
ms.openlocfilehash: 3ece7464198ff52fe6c22ccc54ceede84288bd7b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220951"
---
# <a name="about-arithmetic-operators"></a>Über arithmetische Operatoren

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt die Operatoren, die Arithmetik in PowerShell ausführen.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Arithmetische Operatoren berechnen numerische Werte. Sie können einen oder mehrere arithmetische Operatoren verwenden, um Werte hinzuzufügen, zu subtrahieren, zu multiplizieren und aufzuteilen und den Rest (Modulus) einer Divisions Operation zu berechnen.

Außerdem arbeiten der Additions Operator ( `+` ) und der Multiplikations Operator ( `*` ) auch mit Zeichen folgen, Arrays und Hash Tabellen. Der Additions Operator verkettet die Eingabe. Der Multiplikations Operator gibt mehrere Kopien der Eingabe zurück. Objekttypen können sogar in einer arithmetischen Anweisung gemischt werden. Die Methode, die zum Auswerten der Anweisung verwendet wird, wird durch den Typ des äußersten linken Objekts im Ausdruck bestimmt.

Ab PowerShell 2,0 arbeiten alle arithmetischen Operatoren mit 64-Bit-Zahlen.

Beginnend mit PowerShell 3,0 werden die `-shr` (Umschalt-Right) und `-shl` (shift-left) hinzugefügt, um bitweise Arithmetik in PowerShell zu unterstützen.

PowerShell unterstützt die folgenden arithmetischen Operatoren:

|Operator|BESCHREIBUNG                       |Beispiel                      |
|--------|----------------------------------|-----------------------------|
| +      |Fügt ganze Zahlen hinzu. verkettet       |`6 + 2`                      |
|        |Zeichen folgen, Arrays und Hash Tabellen. |`"file" + "name"`            |
|        |                                  |`@(1, "one") + @(2.0, "two")`|
|        |                                  |`@{"one" = 1} + @{"two" = 2}`|
| -      |Subtrahiert einen Wert von einem anderen.  |`6 - 2`                      |
|        |value                             |                             |
| -      |Gibt eine Zahl als negative Zahl an.  |`-6`                         |
|        |                                  |`(Get-Date).AddDays(-1)`     |
| *      |Zahlen multiplizieren oder Zeichen folgen kopieren  |`6 * 2`                      |
|        |und Arrays die angegebene Zahl.   |`@("!") * 4`                 |
|        |von Zeiten.                         |`"!" * 3`                    |
| /      |Dividiert zwei Werte.               |`6 / 2`                      |
| %      |Modulus-gibt den Rest von|`7 % 2`                      |
|        |ein Divisions Vorgang.             |                             |
|-Band   |Bitweises AND                       |`5 -band 3`                  |
|-bnot   |Bitweises NOT                       |`-bnot 5`                    |
|-Bor    |Bitweises OR                        |`5 -bor 0x03`                |
|-bxor   |Bitweises XOR                       |`5 -bxor 3`                  |
|-SHL    |Verschiebt Bits nach links           |`102 -shl 2`                 |
|-SHR    |Verschiebt Bits nach rechts.          |`102 -shr 2`                 |

Die bitweisen Operatoren können nur für ganzzahlige Typen verwendet werden.

## <a name="operator-precedence"></a>Operator Rangfolge

PowerShell verarbeitet arithmetische Operatoren in der folgenden Reihenfolge:

|Rangfolge|Operator          |BESCHREIBUNG                            |
|----------|------------------|---------------------------------------|
|1         | `()`             |Klammern                            |
|2         | `-`              |Für eine negative Zahl oder einen unären Operator|
|3         | `*`, `/`, `%`    |Für Multiplikation und Division        |
|4         | `+`, `-`         |Für Addition und Subtraktion           |
|5         | `-band`, `-bnot` |Für bitweise Operationen                 |
|5         | `-bor`, `-bxor`  |Für bitweise Operationen                 |
|5         | `-shr`, `-shl`   |Für bitweise Operationen                 |

PowerShell verarbeitet die Ausdrücke von links nach rechts gemäß den Rang Folge Regeln. Die folgenden Beispiele zeigen die Auswirkung der Rang folgen Regeln:

|expression |Ergebnis|
|-----------|------|
|`3+6/3*4`  |`11`  |
|`3+6/(3*4)`|`3.5` |
|`(3+6)/3*4`|`12`  |

Die Reihenfolge, in der PowerShell Ausdrücke auswertet, kann sich von anderen Programmier-und Skriptsprachen unterscheiden, die Sie verwendet haben. Im folgenden Beispiel wird eine komplizierte Zuweisungsanweisung gezeigt.

```powershell
$a = 0
$b = @(1,2)
$c = @(-1,-2)

$b[$a] = $c[$a++]
```

In diesem Beispiel wird der Ausdruck `$a++` vor ausgewertet `$b[$a]` .
Beim Auswerten `$a++` von wird der Wert von geändert `$a` , nachdem er in der-Anweisung verwendet `$c[$a++]` wurde, aber bevor er in verwendet wird `$b[$a]` . Die- `$a` Variable `$b[$a]` in `1` ist, nicht `0` . Daher weist die-Anweisung einen Wert zu `$b[1]` , nicht zu `$b[0]` .

Der obige Code entspricht:

```powershell
$a = 0
$b = @(1,2)
$c = @(-1,-2)

$tmp = $c[$a]
$a = $a + 1
$b[$a] = $tmp
```

## <a name="division-and-rounding"></a>Division und Rundung

Wenn der Quotienten einer Divisions Operation eine ganze Zahl ist, rundet PowerShell den Wert auf die nächste ganze Zahl auf. Wenn der Wert ist `.5` , wird der Wert auf die nächste gerade ganze Zahl gerundet.

Das folgende Beispiel zeigt die Auswirkung der Rundung auf die nächste gerade ganze Zahl.

|expression      |Ergebnis|
|----------------|------|
|`[int]( 5 / 2 )`|`2`   |
|`[int]( 7 / 2 )`|`4`   |

Beachten Sie, dass **_5/2_ = 2,5** auf **2** gerundet wird. **_7/2_ = 3,5** wird jedoch auf **4** gerundet.

Sie können die- `[Math]` Klasse verwenden, um ein anderes Rundungs Verhalten zu erzielen.

|                          expression                          | Ergebnis |
| ------------------------------------------------------------ | ------ |
| `[int][Math]::Round(5 / 2,[MidpointRounding]::AwayFromZero)` | `3`    |
| `[int][Math]::Ceiling(5 / 2)`                                | `3`    |
| `[int][Math]::Floor(5 / 2)`                                  | `2`    |

Weitere Informationen finden Sie unter der [Math. Round](/dotnet/api/system.math.round) -Methode.

## <a name="adding-and-multiplying-non-numeric-types"></a>Hinzufügen und Multiplizieren von nicht numerischen Typen

Sie können Zahlen, Zeichen folgen, Arrays und Hash Tabellen hinzufügen. Und Sie können Zahlen, Zeichen folgen und Arrays multiplizieren. Hash Tabellen können jedoch nicht multipliziert werden.

Wenn Sie Zeichen folgen, Arrays oder Hash Tabellen hinzufügen, werden die Elemente verkettet. Wenn Sie Auflistungen (z. b. Arrays oder Hash Tabellen) verketten, wird ein neues-Objekt erstellt, das die Objekte aus beiden Auflistungen enthält. Wenn Sie versuchen, Hash Tabellen mit demselben Schlüssel zu verketten, schlägt der Vorgang fehl.

Beispielsweise werden mit den folgenden Befehlen zwei Arrays erstellt und dann hinzugefügt:

```powershell
$a = 1,2,3
$b = "A","B","C"
$a + $b
```

```output
1
2
3
A
B
C
```

Sie können auch arithmetische Operationen für Objekte unterschiedlicher Typen durchführen.
Der von PowerShell ausgeführten Vorgang wird durch den Microsoft .net Frameworktyp des äußersten linken Objekts im Vorgang bestimmt. PowerShell versucht, alle Objekte im Vorgang in den .NET Framework Typ des ersten Objekts zu konvertieren. Wenn die Objekte erfolgreich umgerechnet werden, wird der entsprechende Vorgang für den .NET Framework Typ des ersten Objekts ausgeführt. Wenn ein Objekt nicht konvertiert werden kann, schlägt der Vorgang fehl.

In den folgenden Beispielen wird die Verwendung der Additions-und Multiplikations Operatoren veranschaulicht. in Vorgängen, die unterschiedliche Objekttypen enthalten. Angenommen `$array = 1,2,3` :

|expression       |Ergebnis                 |
|-----------------|-----------------------|
|`"file" + 16`    |`file16`               |
|`$array + 16`    |`1`,`2`,`3`,`16`       |
|`$array + "file"`|`1`,`2`,`3`,`file`     |
|`$array * 2`     |`1`,`2`,`3`,`1`,`2`,`3`|
|`"file" * 3`     |`filefilefile`         |

Da die Methode, die zum Auswerten von-Anweisungen verwendet wird, durch das äußteste-Objekt bestimmt wird, sind Addition und Multiplikation in PowerShell nicht streng kommutativ. Beispielsweise ist `(a + b)` nicht immer gleich `(b + a)` , und `(ab)` ist nicht immer gleich `(ba)` .

Die folgenden Beispiele veranschaulichen dieses Prinzip:

|expression   |Ergebnis                                               |
|-------------|-----------------------------------------------------|
|`"file" + 16`|`file16`                                             |
|`16 + "file"`|`Cannot convert value "file" to type "System.Int32".`|
|             |`Error: "Input string was not in a correct format."` |
|             |`At line:1 char:1`                                   |
|             |+ 16 + "Datei" "                                       |

Bei Hash Tabellen handelt es sich um einen etwas anderen Fall. Sie können Hash Tabellen einer anderen Hash Tabelle hinzufügen, solange die hinzugefügten Hash Tabellen nicht über doppelte Schlüssel verfügen.

Im folgenden Beispiel wird gezeigt, wie Hash Tabellen einander hinzugefügt werden.

```powershell
$hash1 = @{a=1; b=2; c=3}
$hash2 = @{c1="Server01"; c2="Server02"}
$hash1 + $hash2
```

```output
Name                           Value
----                           -----
c2                             Server02
a                              1
b                              2
c1                             Server01
c                              3
```

Im folgenden Beispiel wird ein Fehler ausgelöst, da einer der Schlüssel in beiden Hash Tabellen dupliziert wird.

```powershell
$hash1 = @{a=1; b=2; c=3}
$hash2 = @{c1="Server01"; c="Server02"}
$hash1 + $hash2
```

```output
Item has already been added. Key in dictionary: 'c'  Key being added: 'c'
At line:3 char:1
+ $hash1 + $hash2
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (:) [], ArgumentException
    + FullyQualifiedErrorId : System.ArgumentException
```

Außerdem können Sie einem Array eine Hash Tabelle hinzufügen. Außerdem wird die gesamte Hash Tabelle zu einem Element im Array.

```powershell
$array1 = @(0, "Hello World", [datetime]::Now)
$hash1 = @{a=1; b=2}
$array2 = $array1 + $hash1
$array2
```

```output
0
Hello World

Monday, June 12, 2017 3:05:46 PM

Key   : a
Value : 1
Name  : a

Key   : b
Value : 2
Name  : b
```

Es ist jedoch nicht möglich, einer Hash Tabelle einen anderen Typ hinzuzufügen.

```powershell
$hash1 + 2
```

```output
A hash table can only be added to another hash table.
At line:3 char:1
+ $hash1 + 2
```

Obwohl die Additions Operatoren sehr nützlich sind, verwenden Sie die Zuweisungs Operatoren zum Hinzufügen von Elementen zu Hash Tabellen und Arrays. Weitere Informationen finden Sie unter [about_assignment_operators](about_Assignment_Operators.md). In den folgenden Beispielen wird der `+=` Zuweisungs Operator zum Hinzufügen von Elementen zu einem Array verwendet:

```powershell
$array = @()
(0..9).foreach{ $array += $_ }
$array
```

```output
0
1
2
```

## <a name="type-conversion-to-accommodate-result"></a>Typkonvertierung, um das Ergebnis zu erfüllen

PowerShell wählt automatisch den .NET Framework numerischen Typ aus, der das Ergebnis am besten ausdrückt, ohne die Genauigkeit zu verlieren. Beispiel:

```powershell
2 + 3.1

(2). GetType().FullName
(2 + 3.1).GetType().FullName
```

```output
5.1
System.Int32
System.Double
```

Wenn das Ergebnis eines Vorgangs für den Typ zu groß ist, wird der Ergebnistyp um das Ergebnis erweitert, wie im folgenden Beispiel gezeigt:

```powershell
(512MB).GetType().FullName
(512MB * 512MB).GetType().FullName
```

```output
System.Int32
System.Double
```

Der Ergebnistyp ist nicht notwendigerweise identisch mit einem der Operanden. Im folgenden Beispiel kann der negative Wert nicht in eine ganze Zahl ohne Vorzeichen umgewandelt werden, und die Ganzzahl ohne Vorzeichen ist zu groß, um in umgewandelt zu werden `Int32` :

```powershell
([int32]::minvalue + [uint32]::maxvalue).gettype().fullname
```

```output
System.Int64
```

In diesem Beispiel `Int64` kann beide Typen aufnehmen.

Der `System.Decimal` Typ ist eine Ausnahme. Wenn einer der beiden Operanden den Decimal-Typ aufweist, ist das Ergebnis vom Decimal-Typ. Wenn das Ergebnis für den Decimal-Typ zu groß ist, wird es nicht in double umgewandelt. Stattdessen wird ein Fehler ausgegeben.

|expression               |Ergebnis                                         |
|-------------------------|-----------------------------------------------|
|`[Decimal]::maxvalue`    |`79228162514264337593543950335`                |
|`[Decimal]::maxvalue + 1`|`Value was either too large or too small for a`|
|                         |`Decimal.`                                     |

## <a name="arithmetic-operators-and-variables"></a>arithmetische Operatoren und Variablen

Sie können auch arithmetische Operatoren mit Variablen verwenden. Die Operatoren wirken sich auf die Werte der Variablen aus. Die folgenden Beispiele veranschaulichen die Verwendung arithmetischer Operatoren mit Variablen:

| expression                                    |Ergebnis      |
|-----------------------------------------------|------------|
|`$intA = 6`<br/>`$intB = 4`<br/>`$intA + $intB`|`10`        |
|`$a = "Power"`<br/>`$b = "Shell"`<br/>`$a + $b`|`PowerShell`|

## <a name="arithmetic-operators-and-commands"></a>arithmetische Operatoren und Befehle

In der Regel verwenden Sie die arithmetischen Operatoren in Ausdrücken mit Zahlen, Zeichen folgen und Arrays. Sie können jedoch auch arithmetische Operatoren mit den Objekten verwenden, die von Befehlen zurückgegeben werden, sowie mit den Eigenschaften dieser Objekte.

In den folgenden Beispielen wird gezeigt, wie die arithmetischen Operatoren in Ausdrücken mit PowerShell-Befehlen verwendet werden:

```powershell
(get-date) + (new-timespan -day 1)
```

Der Klammer Operator erzwingt die Auswertung des `get-date` Cmdlets und die Auswertung des `new-timespan -day 1` Cmdlet-Ausdrucks in dieser Reihenfolge. Beide Ergebnisse werden dann mit dem- `+` Operator hinzugefügt.

```powershell
Get-Process | Where-Object { ($_.ws * 2) -gt 50mb }
```

```output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
   1896      39    50968      30620   264 1,572.55   1104 explorer
  12802      78   188468      81032   753 3,676.39   5676 OUTLOOK
    660       9    36168      26956   143    12.20    988 PowerShell
    561      14     6592      28144   110 1,010.09    496 services
   3476      80    34664      26092   234 ...45.69    876 svchost
    967      30    58804      59496   416   930.97   2508 WINWORD
```

Im obigen Ausdruck wird jeder Prozess Arbeitsbereich ( `$_.ws` ) mit multipliziert, `2` und das Ergebnis wird mit verglichen, `50mb` um festzustellen, ob es größer als das ist.

## <a name="bitwise-operators"></a>Bitweise Operatoren

PowerShell unterstützt die standardmäßigen bitweisen Operatoren, einschließlich bitweiser and ( `-bAnd` ), der inklusiven und exklusiven bitweisen OR-Operatoren ( `-bOr` and `-bXor` ) und bitweises NOT ( `-bNot` ).

Beginnend mit PowerShell 2,0 arbeiten alle bitweisen Operatoren mit 64-Bit-Ganzzahlen.

Beginnend mit PowerShell 3,0 werden die `-shr` (Umschalt-Right) und `-shl` (shift-left) eingeführt, um bitweise Arithmetik in PowerShell zu unterstützen.

PowerShell unterstützt die folgenden bitweisen Operatoren.

| Operator | BESCHREIBUNG            | Ausdruck   | Ergebnis |
| -------- | ---------------------- | ------------ | ------ |
| `-band`  | Bitweises AND            | `10 -band 3` | 2      |
| `-bor`   | Bitweises OR (inklusiv) | `10 -bor 3`  | 11     |
| `-bxor`  | Bitweises OR (exklusiv) | `10 -bxor 3` | 9      |
| `-bnot`  | Bitweises NOT            | `-bNot 10`   | -11    |
| `-shl`   | UMSCHALT nach links             | `102 -shl 2` | 408    |
| `-shr`   | Shift-right            | `102 -shr 1` | 51     |

Bitweise Operatoren agieren auf das binäre Format eines-Werts. Beispielsweise ist die bitstruktur für die Zahl 10 00001010 (basierend auf 1 Byte), und die bitstruktur für die Zahl 3 ist 00000011. Wenn Sie einen bitweisen Operator zum Vergleichen von 10 mit 3 verwenden, werden die einzelnen Bits in jedem Byte verglichen.

In einer bitweisen and-Operation wird das resultierende Bit nur dann auf 1 festgelegt, wenn beide Eingabe Bits 1 sind.

```
1010      (10)
0011      ( 3)
--------------  bAND
0010      ( 2)
```

Bei einem bitweisen OR-Vorgang (inklusiv) wird das resultierende Bit auf 1 festgelegt, wenn entweder oder beide Eingabe Bits 1 sind. Das resultierende Bit wird nur dann auf 0 festgelegt, wenn beide Eingabe Bits auf 0 festgelegt sind.

```
1010      (10)
0011      ( 3)
--------------  bOR (inclusive)
1011      (11)
```

Bei einem bitweisen OR-Vorgang (exklusiv) wird das resultierende Bit nur dann auf 1 festgelegt, wenn ein Eingabe Bit 1 ist.

```
1010      (10)
0011      ( 3)
--------------  bXOR (exclusive)
1001      ( 9)
```

Der bitweise NOT-Operator ist ein unärer Operator, der das binäre Komplement des Werts erzeugt. Ein Bit von 1 wird auf 0 festgelegt, und ein Bit von 0 wird auf 1 festgelegt.

Beispielsweise ist das binäre Komplement von 0-1, die maximale Ganzzahl ohne Vorzeichen (0xFFFFFFFF) und das binäre Komplement von-1 0.

```powershell
-bNot 10
```

```Output
-11
```

```
0000 0000 0000 1010  (10)
------------------------- bNOT
1111 1111 1111 0101  (-11, xfffffff5)
```

Bei einem bitweisen Shift-Left-Vorgang werden alle Bits "n" nach links verschoben, wobei "n" der Wert des rechten Operanden ist. An dieser Stelle wird ein NULL-Wert eingefügt.

Wenn der linke Operand ein ganzzahliger Wert (32 Bit) ist, bestimmen die unteren 5 Bits des rechten Operanden, wie viele Bits des linken Operanden verschoben werden.

Wenn der linke Operand ein Long (64-Bit)-Wert ist, bestimmen die unteren 6 Bits des rechten Operanden, wie viele Bits des linken Operanden verschoben werden.

|expression |Ergebnis|Binäres Ergebnis|
|-----------|------|-------------|
|`21 -shl 0`|21    |0001 0101    |
|`21 -shl 1`|42    |0010 1010    |
|`21 -shl 2`|84    |0101 0100    |

Bei einem bitweisen shift-right-Vorgang werden alle Bits "n" nach rechts verschoben, wobei "n" durch den rechten Operanden angegeben wird. Der SHIFT-RIGHT-Operator (-SHR) Fügt am äußersten linken Speicherort eine NULL ein, wenn ein positiver oder nicht signierter Wert nach rechts verschoben wird.

Wenn der linke Operand ein ganzzahliger Wert (32 Bit) ist, bestimmen die unteren 5 Bits des rechten Operanden, wie viele Bits des linken Operanden verschoben werden.

Wenn der linke Operand ein Long (64-Bit)-Wert ist, bestimmen die unteren 6 Bits des rechten Operanden, wie viele Bits des linken Operanden verschoben werden.

|expression              |Ergebnis      |Binary     |Hex         |
|------------------------|------------|-----------|------------|
|`21 -shr 0`             | 21         | 0001 0101 | 0x15       |
|`21 -shr 1`             | 10         | 0000 1010 | 0x0A       |
|`21 -shr 2`             | 5          | 0000 0101 | 0x05       |
|`21 -shr 31`            | 0          | 0000 0000 | 0x00       |
|`21 -shr 32`            | 21         | 0001 0101 | 0x15       |
|`21 -shr 64`            | 21         | 0001 0101 | 0x15       |
|`21 -shr 65`            | 10         | 0000 1010 | 0x0A       |
|`21 -shr 66`            | 5          | 0000 0101 | 0x05       |
|`[int]::MaxValue -shr 1`| 1073741823 |           | 0x3fffffff |
|`[int]::MinValue -shr 1`| -1073741824|           | 0xC0000000 |
|`-1 -shr 1`             | -1         |           | 0xFFFFFFFF |

## <a name="see-also"></a>SIEHE AUCH

- [about_arrays](about_Arrays.md)
- [about_assignment_operators](about_Assignment_Operators.md)
- [about_comparison_operators](about_Comparison_Operators.md)
- [about_hash_tables](about_Hash_Tables.md)
- [about_operators](about_Operators.md)
- [about_variables](about_Variables.md)
- [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date)
- [New-TimeSpan](xref:Microsoft.PowerShell.Utility.New-TimeSpan)
