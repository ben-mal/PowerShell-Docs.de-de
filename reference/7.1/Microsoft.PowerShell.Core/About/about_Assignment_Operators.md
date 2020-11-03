---
description: Beschreibt, wie Operatoren verwendet werden, um Variablen Werte zuzuweisen.
keywords: powershell,cmdlet
ms.date: 04/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_assignment_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Assignment_Operators
ms.openlocfilehash: 06c68066b82bc4d8aec4d1a51c39e16fa52c2956
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223052"
---
# <a name="about-assignment-operators"></a>Informationen über Zuweisungs Operator

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt, wie Operatoren verwendet werden, um Variablen Werte zuzuweisen.

## <a name="long-description"></a>Lange Beschreibung

Zuweisungs Operatoren weisen einer Variablen einen oder mehrere Werte zu. Sie können vor der Zuweisung numerische Vorgänge für die Werte ausführen.

PowerShell unterstützt die folgenden Zuweisungs Operatoren.

|Operator|BESCHREIBUNG                                                  |
|--------|-------------------------------------------------------------|
|=       |Legt den Wert einer Variablen auf den angegebenen Wert fest.         |
|+=      |Erhöht den Wert einer Variablen um den angegebenen Wert, oder |
|        |Fügt den angegebenen Wert an den vorhandenen Wert an.           |
|-=      |Verringert den Wert einer Variablen um den angegebenen Wert.    |
|*=      |Multipliziert den Wert einer Variablen mit dem angegebenen Wert oder.|
|        |Fügt den angegebenen Wert an den vorhandenen Wert an.           |
|/=      |Dividiert den Wert einer Variablen durch den angegebenen Wert.      |
|%=      |Dividiert den Wert einer Variablen durch den angegebenen Wert und   |
|        |Anschließend wird der Rest (Modulus) der Variablen zugewiesen.        |
|++      |Erhöht den Wert einer Variablen, einer zustellbaren Eigenschaft oder   |
|        |Array Element um 1.                                          |
|--      |Verringert den Wert einer Variablen, einer zustellbaren Eigenschaft oder   |
|        |Array Element um 1.                                          |

## <a name="syntax"></a>Syntax

Die Syntax der Zuweisungs Operatoren lautet wie folgt:

`<assignable-expression>` `<assignment-operator>` `<value>`

Zustellbare Ausdrücke enthalten Variablen und Eigenschaften. Der Wert kann ein einzelner Wert, ein Array von Werten oder ein Befehl, ein Ausdruck oder eine Anweisung sein.

Die Inkrement-und Dekrementoperatoren sind unäre Operatoren. Jede verfügt über Präfix-und postfix Versionen.

`<assignable-expression><operator>`
`<operator><assignable-expression>`

Der Zusetz Bare Ausdruck muss eine Zahl sein, oder er muss in eine Zahl konvertiert werden können.

## <a name="assigning-values"></a>Zuweisen von Werten

Variablen werden als Speicherplätze bezeichnet, in denen Werte gespeichert werden. Sie speichern die Werte in Variablen, indem Sie den Zuweisungs Operator verwenden `=` . Der neue Wert kann den vorhandenen Wert der Variablen ersetzen, oder Sie können einen neuen Wert an den vorhandenen Wert anfügen.

Der grundlegende Zuweisungs Operator ist das Gleichheitszeichen `=` `(ASCII 61)` . Beispielsweise weist die folgende Anweisung den Wert PowerShell der Variablen zu `$MyShell` :

```powershell
$MyShell = "PowerShell"
```

Wenn Sie einer Variablen in PowerShell einen Wert zuweisen, wird die Variable erstellt, wenn Sie nicht bereits vorhanden ist. Beispielsweise erstellt die erste der beiden folgenden Zuweisungs Anweisungen die `$a` -Variable und weist den Wert 6 zu `$a` . Die zweite Zuweisungsanweisung weist den Wert 12 zu `$a` . Die erste Anweisung erstellt eine neue Variable. Die zweite Anweisung ändert nur ihren Wert:

```powershell
$a = 6
$a = 12
```

Variablen in PowerShell verfügen über keinen bestimmten Datentyp, es sei denn, Sie wandeln Sie um.
Wenn eine Variable nur ein Objekt enthält, nimmt die Variable den Datentyp des Objekts an. Wenn eine Variable eine Auflistung von-Objekten enthält, hat die Variable den System. Object-Datentyp. Daher können Sie der Auflistung jeden Objekttyp zuweisen. Das folgende Beispiel zeigt, dass Sie Prozess Objekte, Dienst Objekte, Zeichen folgen und ganze Zahlen zu einer Variablen hinzufügen können, ohne einen Fehler zu erzeugen:

```powershell
$a = Get-Process
$a += Get-Service
$a += "string"
$a += 12
```

Da der Zuweisungs Operator `=` eine niedrigere Rangfolge aufweist als der Pipeline Operator `|` , sind keine Klammern erforderlich, um das Ergebnis einer Befehls Pipeline einer Variablen zuzuweisen. Mit dem folgenden Befehl werden z. b. die Dienste auf dem Computer sortiert und dann die sortierten Dienste der `$a` Variablen zugewiesen:

```powershell
$a = Get-Service | Sort-Object -Property name
```

Sie können den von einer-Anweisung erstellten Wert auch einer Variablen zuweisen, wie im folgenden Beispiel gezeigt:

```powershell
$a = if ($b -lt 0) { 0 } else { $b }
```

In diesem Beispiel wird der-Variablen null zugewiesen, `$a` Wenn der Wert von `$b` kleiner als 0 (null) ist. Der Wert von wird dem zugewiesen `$b` , `$a` Wenn der Wert von `$b` nicht kleiner als 0 (null) ist.

### <a name="the-assignment-operator"></a>Der Zuweisungs Operator

Der Zuweisungs Operator `=` weist Variablen Werte zu. Wenn die Variable bereits über einen Wert verfügt, ersetzt der Zuweisungs Operator `=` den Wert ohne Warnung.

Die folgende Anweisung weist der Variablen den ganzzahligen Wert 6 zu `$a` :

```powershell
$a = 6
```

Wenn Sie einer Variablen einen Zeichen folgen Wert zuweisen möchten, schließen Sie den Zeichen folgen Wert in Anführungszeichen ein, wie im folgenden dargestellt:

```powershell
$a = "baseball"
```

Wenn Sie einer Variablen ein Array (mehrere Werte) zuweisen möchten, trennen Sie die Werte durch Kommas wie folgt:

```powershell
$a = "apple", "orange", "lemon", "grape"
```

Wenn Sie einer Variablen eine Hash Tabelle zuweisen möchten, verwenden Sie die standardmäßige Hash Tabellen Notation in PowerShell. Geben Sie ein-Zeichen ein `@` , gefolgt von Schlüssel-Wert-Paaren, die durch Semikolons getrennt `;` und in geschweifte Klammern eingeschlossen werden `{ }` . Wenn Sie z. b. der Variablen eine Hash Tabelle zuweisen möchten, geben Sie Folgendes ein `$a` :

```powershell
$a = @{one=1; two=2; three=3}
```

Um einer Variablen hexadezimale Werte zuzuweisen, stellen Sie dem Wert vor den Wert vor `0x` .
PowerShell konvertiert den Hexadezimalwert (0x10) in einen Dezimalwert (in diesem Fall 16) und weist diesen Wert der `$a` Variablen zu. Wenn Sie der Variablen z. b. den Wert 0x10 zuweisen möchten, geben Sie Folgendes ein `$a` :

```powershell
$a = 0x10
```

Wenn Sie einer Variablen einen exponentiellen Wert zuweisen möchten, geben Sie die Stamm Nummer, den Buchstaben `e` und eine Zahl ein, die ein Vielfaches von 10 darstellt. Geben Sie z. b. Folgendes 3,1415 ein, um die Leistungsstärke 1.000 der `$a` Variablen zuzuweisen:

```powershell
$a = 3.1415e3
```

PowerShell kann auch Kilobyte `KB` , Megabyte `MB` und Gigabyte `GB` in Bytes konvertieren. Wenn Sie z. b. der Variablen einen Wert von 10 Kilobyte zuweisen möchten, geben Sie Folgendes ein `$a` :

```powershell
$a = 10kb
```

### <a name="the-assignment-by-addition-operator"></a>Der Operator "Zuweisung durch Addition"

Der Operator "Zuweisung durch Addition" `+=` erhöht entweder den Wert einer Variablen oder fügt den angegebenen Wert an den vorhandenen Wert an. Die Aktion hängt davon ab, ob die Variable einen numerischen oder einen Zeichen Folgentyp aufweist und ob die Variable einen einzelnen Wert (Skalar) oder mehrere Werte (eine Auflistung) enthält.

Der- `+=` Operator kombiniert zwei Vorgänge. Zuerst wird hinzugefügt und dann zugewiesen.
Daher sind die folgenden Anweisungen äquivalent:

```powershell
$a += 2
$a = ($a + 2)
```

Wenn die Variable einen einzelnen numerischen Wert enthält, `+=` erhöht der Operator den vorhandenen Wert um den Betrag auf der rechten Seite des Operators. Anschließend weist der Operator den resultierenden Wert der Variablen zu. Im folgenden Beispiel wird gezeigt, wie der-Operator verwendet wird `+=` , um den Wert einer Variablen zu erhöhen:

```powershell
$a = 4
$a += 2
$a
```

```
6
```

Wenn der Wert der Variablen eine Zeichenfolge ist, wird der Wert auf der rechten Seite des Operators wie folgt an die Zeichenfolge angehängt:

```powershell
$a = "Windows"
$a += " PowerShell"
$a
```

```
Windows PowerShell
```

Wenn der Wert der Variablen ein Array ist, fügt der `+=` Operator die Werte auf der rechten Seite des Operators an das Array an. Wenn das Array nicht durch umwandeln explizit typisiert wird, können Sie einen beliebigen Werttyp wie folgt an das Array anfügen:

```powershell
$a = 1,2,3
$a += 2
$a
```

```
1
2
3
2
```

und

```powershell
$a += "String"
$a
```

```
1
2
3
2
String
```

Wenn der Wert einer Variablen eine Hash Tabelle ist, fügt der `+=` Operator den Wert auf der rechten Seite des Operators an die Hash Tabelle an. Da der einzige Typ, den Sie einer Hash Tabelle hinzufügen können, eine andere Hash Tabelle ist, schlagen alle anderen Zuweisungen jedoch fehl.

Der folgende Befehl weist z. b. der Variablen eine Hash Tabelle zu `$a` .
Anschließend wird der-Operator verwendet, `+=` um eine andere Hash Tabelle an die vorhandene Hash Tabelle anzufügen, wodurch der vorhandenen Hash Tabelle ein neues Schlüssel-Wert-Paar hinzugefügt wird.
Dieser Befehl ist erfolgreich, wie in der Ausgabe gezeigt:

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += @{mode = "write"}
$a
```

```
Name                           Value
----                           -----
a                              1
b                              2
mode                           write
c                              3
```

Der folgende Befehl versucht, eine Ganzzahl "1" an die Hash Tabelle in der Variablen anzufügen `$a` . Dieser Befehl schlägt fehl:

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += 1
```

```
You can add another hash table only to a hash table.
At line:1 char:6
+ $a += <<<<  1
```

### <a name="the-assignment-by-subtraction-operator"></a>Zuweisung durch Subtraktions Operator

Der Zuweisungs Operator für die Subtraktion verringert `-=` den Wert einer Variablen um den Wert, der auf der rechten Seite des Operators angegeben wird. Dieser Operator kann nicht mit Zeichen folgen Variablen verwendet werden und kann nicht verwendet werden, um ein Element aus einer Auflistung zu entfernen.

Der- `-=` Operator kombiniert zwei Vorgänge. Zuerst wird subtrahiert und dann zugewiesen. Daher sind die folgenden Anweisungen äquivalent:

```powershell
$a -= 2
$a = ($a - 2)
```

Im folgenden Beispiel wird gezeigt, wie der- `-=` Operator verwendet wird, um den Wert einer Variablen zu verringern:

```powershell
$a = 8
$a -= 2
$a
```

```
6
```

Sie können auch den `-=` Zuweisungs Operator verwenden, um den Wert eines Members eines numerischen Arrays zu verringern. Geben Sie hierzu den Index des Array Elements an, das Sie ändern möchten. Im folgenden Beispiel wird der Wert des dritten Elements eines Arrays (Element 2) um 1 verringert:

```powershell
$a = 1,2,3
$a[2] -= 1
$a
```

```
1
2
2
```

Der-Operator kann nicht `-=` zum Löschen der Werte einer Variablen verwendet werden. Um alle Werte zu löschen, die einer Variablen zugewiesen sind, verwenden Sie die Cmdlets [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item) oder [Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable) , um `$null` `""` der Variablen den Wert oder zuzuweisen.

```powershell
$a = $null
```

Um einen bestimmten Wert aus einem Array zu löschen, verwenden Sie die Array Notation, um `$null` dem jeweiligen Element den Wert zuzuweisen. Die folgende Anweisung löscht z. b. den zweiten Wert (Indexposition 1) aus einem Array:

```powershell
$a = 1,2,3
$a
```

```
1
2
3
```

```powershell
$a[1] = $null
$a
```

```
1
3
```

Verwenden Sie das Cmdlet [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) , um eine Variable zu löschen. Diese Methode ist nützlich, wenn die Variable explizit in einen bestimmten Datentyp umgewandelt wird und Sie eine nicht typisierte Variable benötigen. Der folgende Befehl löscht die- `$a` Variable:

```powershell
Remove-Variable -Name a
```

### <a name="the-assignment-by-multiplication-operator"></a>Der Operator "Zuweisung durch Multiplikation"

Der Operator "Zuweisung durch Multiplikation" `*=` multipliziert einen numerischen Wert oder fügt die angegebene Anzahl von Kopien des Zeichen folgen Werts einer Variablen an.

Wenn eine Variable einen einzelnen numerischen Wert enthält, wird dieser Wert mit dem Wert auf der rechten Seite des Operators multipliziert. Das folgende Beispiel zeigt beispielsweise, wie der-Operator verwendet wird, `*=` um den Wert einer Variablen zu multiplizieren:

```powershell
$a = 3
$a *= 4
$a
```

```
12
```

In diesem Fall kombiniert der `*=` Operator zwei Vorgänge. Zuerst wird multipliziert und dann zugewiesen. Daher sind die folgenden Anweisungen äquivalent:

```powershell
$a *= 2
$a = ($a * 2)
```

Wenn eine Variable einen Zeichen folgen Wert enthält, fügt PowerShell die angegebene Anzahl von Zeichen folgen wie folgt an den-Wert an:

```powershell
$a = "file"
$a *= 4
$a
```

```
filefilefilefile
```

Um ein Element eines Arrays zu multiplizieren, verwenden Sie einen Index, um das Element zu identifizieren, das Sie multiplizieren möchten. Mit dem folgenden Befehl wird z. b. das erste Element im Array (Indexposition 0) um 2 multipliziert:

```powershell
$a[0] *= 2
```

### <a name="the-assignment-by-division-operator"></a>Der Operator für die Zuweisung durch Division

Der Operator "Zuweisung durch Division" `/=` dividiert einen numerischen Wert durch den Wert, der auf der rechten Seite des Operators angegeben wird. Der Operator kann nicht mit Zeichen folgen Variablen verwendet werden.

Der- `/=` Operator kombiniert zwei Vorgänge. Zuerst wird Sie unterteilt und dann zugewiesen. Daher sind die folgenden beiden Anweisungen äquivalent:

```powershell
$a /= 2
$a = ($a / 2)
```

Der folgende Befehl verwendet z. b. den- `/=` Operator, um den Wert einer Variablen zu unterteilen:

```powershell
$a = 8
$a /=2
$a
```

```
4
```

Um ein Element eines Arrays aufzuteilen, verwenden Sie einen Index, um das Element zu identifizieren, das Sie ändern möchten. Mit dem folgenden Befehl wird z. b. das zweite Element im Array (Indexposition 1) um 2 dividiert:

```powershell
$a[1] /= 2
```

### <a name="the-assignment-by-modulus-operator"></a>Der Operator "Zuweisung durch Modulo"

Der Operator "Zuweisung durch Modulo" `%=` dividiert den Wert einer Variablen durch den Wert auf der rechten Seite des Operators. Anschließend weist der `%=` Operator den Rest (als Modulus bezeichnet) der Variablen zu. Dieser Operator kann nur verwendet werden, wenn eine Variable einen einzelnen numerischen Wert enthält. Dieser Operator kann nicht verwendet werden, wenn eine Variable eine Zeichen folgen Variable oder ein Array enthält.

Der- `%=` Operator kombiniert zwei Vorgänge. Zuerst wird der Rest dividiert und bestimmt, und dann wird der Rest der Variablen zugewiesen. Daher sind die folgenden Anweisungen äquivalent:

```powershell
$a %= 2
$a = ($a % 2)
```

Im folgenden Beispiel wird gezeigt, wie der-Operator verwendet wird `%=` , um den Modulo eines Quotienten zu speichern:

```powershell
$a = 7
$a %= 4
$a
```

```
3
```

## <a name="the-increment-and-decrement-operators"></a>Die Inkrement-und Dekrementoperatoren

Der Inkrement-Operator `++` erhöht den Wert einer Variablen um 1. Wenn Sie den Inkrement-Operator in einer einfachen Anweisung verwenden, wird kein Wert zurückgegeben. Um das Ergebnis anzuzeigen, zeigen Sie den Wert der Variablen wie folgt an:

```powershell
$a = 7
++$a
$a
```

```
8
```

Um zu erzwingen, dass ein Wert zurückgegeben wird, schließen Sie die-Variable und den-Operator wie folgt in Klammern ein:

```powershell
$a = 7
(++$a)
```

```
8
```

Der Inkrementoperator kann vor (Präfix) oder nach (postfix) einer Variablen eingefügt werden. Die Präfix Version des Operators erhöht eine Variable, bevor ihr Wert in der Anweisung wie folgt verwendet wird:

```powershell
$a = 7
$c = ++$a
$a
```

```
8
```

```powershell
$c
```

```
8
```

Die Postfix-Version des-Operators erhöht eine Variable, nachdem deren Wert in der-Anweisung verwendet wurde. Im folgenden Beispiel `$c` verfügen die Variablen und `$a` über unterschiedliche Werte, da der Wert vor den `$c` Änderungen zugewiesen wird `$a` :

```powershell
$a = 7
$c = $a++
$a
```

```
8
```

```powershell
$c
```

```
7
```

Der Dekrementoperator `--` verringert den Wert einer Variablen um 1. Wie beim Inkrement-Operator wird kein Wert zurückgegeben, wenn Sie den-Operator in einer einfachen-Anweisung verwenden. Verwenden Sie Klammern wie folgt, um einen Wert zurückzugeben:

```powershell
$a = 7
--$a
$a
```

```
6
```

```powershell
(--$a)
```

```
5
```

Die Präfix Version des-Operators dekrementierungen eine Variable, bevor ihr Wert in der-Anweisung verwendet wird, wie im folgenden dargestellt:

```powershell
$a = 7
$c = --$a
$a
```

```
6
```

```powershell
$c
```

```
6
```

Die Postfix-Version des-Operators dekrementierungen eine Variable, nachdem deren Wert in der-Anweisung verwendet wurde. Im folgenden Beispiel `$d` verfügen die Variablen und `$a` über unterschiedliche Werte, da der Wert vor den `$d` Änderungen zugewiesen wird `$a` :

```powershell
$a = 7
$d = $a--
$a
```

```
6
```

```powershell
$d
```

```
7
```

## <a name="microsoft-net-framework-types"></a>Microsoft .NET Framework-Typen

Wenn eine Variable nur über einen Wert verfügt, bestimmt der Wert, der der Variablen zugewiesen ist, den Datentyp der Variablen standardmäßig. Der folgende Befehl erstellt z. b. eine Variable mit dem Typ "Integer" (System. Int32):

```powershell
$a = 6
```

Um den .NET Framework Typ einer Variablen zu suchen, verwenden Sie die **GetType** -Methode und die zugehörige **FullName** -Eigenschaft wie folgt. Stellen Sie sicher, dass Sie die Klammern nach dem Namen der **GetType** -Methode einschließen, obwohl der Methoden aufrufnicht über Argumente verfügt:

```powershell
$a = 6
$a.GetType().FullName
```

```
System.Int32
```

Um eine Variable zu erstellen, die eine Zeichenfolge enthält, weisen Sie der Variablen einen Zeichen folgen Wert zu. Um anzugeben, dass der Wert eine Zeichenfolge ist, müssen Sie Sie wie folgt in Anführungszeichen einschließen:

```powershell
$a = "6"
$a.GetType().FullName
```

```
System.String
```

Wenn der erste Wert, der der Variablen zugewiesen ist, eine Zeichenfolge ist, behandelt PowerShell alle Vorgänge als Zeichen folgen Vorgänge und wandelt neue Werte in Zeichen folgen um.
Dies geschieht im folgenden Beispiel:

```powershell
$a = "file"
$a += 3
$a
```

```
file3
```

Wenn der erste Wert eine ganze Zahl ist, behandelt PowerShell alle Vorgänge als ganzzahlige Vorgänge und wandelt neue Werte in ganze Zahlen um. Dies geschieht im folgenden Beispiel:

```powershell
$a = 6
$a += "3"
$a
```

```
9
```

Sie können eine neue skalare Variable in beliebige .NET Framework Typen umwandeln, indem Sie den Typnamen in eckige Klammern platzieren, die entweder dem Variablennamen oder dem ersten Zuweisungs Wert vorangestellt sind. Wenn Sie eine Variable umwandeln, können Sie die Datentypen bestimmen, die in der Variablen gespeichert werden können. Und Sie können bestimmen, wie sich die Variable verhält, wenn Sie Sie bearbeiten.

Beispielsweise wandelt der folgende Befehl die Variable in einen Zeichen Folgentyp um:

```powershell
[string]$a = 27
$a += 3
$a
```

```
273
```

Im folgenden Beispiel wird der erste Wert umgewandelt, anstelle der Variablen:

```powershell
$a = [string]27
```

Wenn Sie eine Variable in einen bestimmten Typ umwandeln, besteht die gängige Konvention darin, die Variable und nicht den Wert zu konvertieren. Allerdings können Sie den Datentyp einer vorhandenen Variablen nicht umgestalten, wenn der Wert nicht in den neuen Datentyp konvertiert werden kann. Um den Datentyp zu ändern, müssen Sie seinen Wert wie folgt ersetzen:

```powershell
$a = "string"
[int]$a
```

```
Cannot convert value "string" to type "System.Int32". Error: "Input string was
not in a correct format." At line:1 char:8 + [int]$a <<<<
```

```powershell
[int]$a = 3
```

Wenn Sie einem Variablennamen einen Datentyp voranstellen, wird der Typ dieser Variablen außerdem gesperrt, es sei denn, Sie überschreiben den Typ explizit durch Angabe eines anderen Datentyps. Wenn Sie versuchen, einen Wert zuzuweisen, der nicht mit dem vorhandenen Typ kompatibel ist, und Sie den Typ nicht explizit überschreiben, zeigt PowerShell einen Fehler an, wie im folgenden Beispiel gezeigt:

```powershell
$a = 3
$a = "string"
[int]$a = 3
$a = "string"
```

```
Cannot convert value "string" to type "System.Int32". Error: "Input
string was not in a correct format."
At line:1 char:3
+ $a <<<<  = "string"
```

```powershell
[string]$a = "string"
```

In PowerShell werden die Datentypen von Variablen, die mehrere Elemente in einem Array enthalten, anders behandelt als die Datentypen von Variablen, die ein einzelnes Element enthalten. Wenn ein-Datentyp nicht speziell einer Array Variablen zugewiesen ist, ist der Datentyp immer `System.Object []` . Dieser Datentyp ist spezifisch für Arrays.

Manchmal können Sie den Standardtyp überschreiben, indem Sie einen anderen Typ angeben. Beispielsweise wandelt der folgende Befehl die Variable in einen `string []` Arraytyp um:

```powershell
[string []] $a = "one", "two", "three"
```

PowerShell-Variablen können beliebige .NET Framework Datentyps sein. Außerdem können Sie jeden voll qualifizierten .NET Framework Datentyp zuweisen, der im aktuellen Prozess verfügbar ist. Der folgende Befehl gibt z. b. einen- `System.DateTime` Datentyp an:

```powershell
[System.DateTime]$a = "5/31/2005"
```

Der Variablen wird ein Wert zugewiesen, der dem `System.DateTime` Datentyp entspricht. Der Wert der Variablen lautet wie `$a` folgt:

```
Tuesday, May 31, 2005 12:00:00 AM
```

## <a name="assigning-multiple-variables"></a>Zuweisen von mehreren Variablen

In PowerShell können Sie mithilfe eines einzelnen Befehls mehreren Variablen Werte zuweisen. Das erste Element des Zuweisungs Werts wird der ersten Variablen zugewiesen, das zweite Element wird der zweiten Variablen zugewiesen, das dritte Element der dritten Variablen usw. Der folgende Befehl weist z. b. den Wert 1 der Variablen `$a` , den Wert 2 der `$b` Variablen und den Wert 3 der `$c` Variablen zu:

```powershell
$a, $b, $c = 1, 2, 3
```

Wenn der Zuweisungs Wert mehr Elemente als Variablen enthält, werden alle verbleibenden Werte der letzten Variablen zugewiesen. Der folgende Befehl enthält z. b. drei Variablen und fünf Werte:

```powershell
$a, $b, $c = 1, 2, 3, 4, 5
```

Daher weist PowerShell den Wert 1 der `$a` Variablen und den Wert 2 der `$b` Variablen zu. Die Werte 3, 4 und 5 werden der `$c` Variablen zugewiesen.
Verwenden Sie das folgende Format, um die Werte in der `$c` Variablen drei anderen Variablen zuzuweisen:

```powershell
$d, $e, $f = $c
```

Dieser Befehl weist den Wert 3 der Variablen `$d` , den Wert 4 der `$e` Variablen und den Wert 5 der `$f` Variablen zu.

Wenn der Zuweisungs Wert weniger Elemente als Variablen enthält, werden allen verbleibenden Variablen am Ende keine Werte zugewiesen. Der folgende Befehl enthält z. b. drei Variablen und zwei Werte:

```powershell
$a, $b, $c = 1, 2
```

Daher weist PowerShell den Wert 1 der `$a` Variablen und den Wert 2 der `$b` Variablen zu. Der Variablen wird kein Wert zugewiesen `$c` .

Sie können einem einzelnen Wert auch mehrere Variablen zuweisen, indem Sie die Variablen verketten. Beispielsweise weist der folgende Befehl allen vier Variablen den Wert "drei" zu:

```powershell
$a = $b = $c = $d = "three"
```

## <a name="variable-related-cmdlets"></a>Variablen bezogene Cmdlets

Zusätzlich zur Verwendung einer Zuweisungs Operation zum Festlegen eines Variablen Werts können Sie auch das [Set-Variable-](xref:Microsoft.PowerShell.Utility.Set-Variable) Cmdlet verwenden. Der folgende Befehl verwendet z. b `Set-Variable` ., um ein Array von 1, 2, 3 der `$a` Variablen zuzuweisen.

```powershell
Set-Variable -Name a -Value 1, 2, 3
```

## <a name="see-also"></a>Weitere Informationen:

[about_Arrays](about_Arrays.md)

[about_Hash_Tables](about_Hash_Tables.md)

[about_Variables](about_Variables.md)

[Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable)

[Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable)

[Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable)

