---
description: Beschreibt Arrays, bei denen es sich um Datenstrukturen handelt, die zum Speichern von Element Auflistungen
keywords: powershell,cmdlet
Locale: en-US
ms.date: 08/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arrays
ms.openlocfilehash: 96e3798d4ff0a737421bb6211b809b192afa96f0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222951"
---
# <a name="about-arrays"></a>Informationen zu Arrays

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt Arrays, bei denen es sich um Datenstrukturen handelt, die zum Speichern von Element Auflistungen

## <a name="long-description"></a>Lange Beschreibung

Ein Array ist eine Datenstruktur, die zum Speichern einer Auflistung von Elementen entworfen wurde.
Die Elemente können denselben Typ oder verschiedene Typen aufweisen.

Ab Windows PowerShell 3,0 weist eine Auflistung von 0 (null) oder einem Objekt einige Eigenschaften von Arrays auf.

## <a name="creating-and-initializing-an-array"></a>Erstellen und Initialisieren eines Arrays

Weisen Sie einer Variablen mehrere Werte zu, um ein Array zu erstellen und zu initialisieren. Die im Array gespeicherten Werte werden durch ein Komma getrennt und vom Zuweisungs Operator () vom Variablennamen getrennt `=` .

Um z. b. ein Array mit dem Namen zu erstellen `$A` , das die sieben numerischen Werte (int) von 22, 5, 10, 8, 12, 9 und 80 enthält, geben Sie Folgendes ein:

```powershell
$A = 22,5,10,8,12,9,80
```

Das Komma kann auch verwendet werden, um ein einzelnes Element Array zu initialisieren, indem das Komma vor dem einzelnen Element platziert wird.

Geben Sie beispielsweise Folgendes ein, um ein einzelnes Element `$B` mit dem Namen mit dem einzelnen Wert 7 zu erstellen:

```powershell
$B = ,7
```

Sie können ein Array auch mit dem Bereichs Operator () erstellen und initialisieren `..` .
Im folgenden Beispiel wird ein Array erstellt, das die Werte 5 bis 8 enthält.

```powershell
$C = 5..8
```

Daher `$C` enthält vier Werte: 5, 6, 7 und 8.

Wenn kein Datentyp angegeben ist, erstellt PowerShell jedes Array als Objekt Array ( **System. Object []** ). Zum Ermitteln des Datentyps eines Arrays verwenden Sie die **GetType ()** -Methode. Wenn Sie z. b. den Datentyp des Arrays ermitteln möchten, geben Sie Folgendes ein `$A` :

```powershell
$A.GetType()
```

Zum Erstellen eines stark typisierten Arrays, d. h. eines Arrays, das nur Werte eines bestimmten Typs enthalten kann, wandeln Sie die Variable in einen Arraytyp um, z. b. **String []** , **Long []** oder **Int32 []**. Zum Umwandeln eines Arrays stellen Sie vor dem Variablennamen einen Arraytyp dar, der in eckige Klammern eingeschlossen ist. Um z. b. ein 32-Bit-ganz Zahl Array mit dem Namen zu erstellen, das `$ia` vier ganze Zahlen (1500, 2230, 3350 und 4000) enthält, geben Sie Folgendes ein:

```powershell
[int32[]]$ia = 1500,2230,3350,4000
```

Folglich `$ia` kann das Array nur ganze Zahlen enthalten.

Sie können Arrays erstellen, die in einen beliebigen unterstützten Typ in Microsoft .NET Framework umgewandelt werden. Beispielsweise sind die Objekte, die `Get-Process` zum Darstellen von Prozessen abruft, vom Typ " **System. Diagnostics. Process** ". Um ein stark typisiertes Array von Prozess Objekten zu erstellen, geben Sie den folgenden Befehl ein:

```powershell
[Diagnostics.Process[]]$zz = Get-Process
```

## <a name="the-array-sub-expression-operator"></a>Der Array-unter Ausdrucks Operator

Der unter Ausdrucks Operator Array erstellt ein Array aus den darin enthaltenen Anweisungen. Was die Anweisung innerhalb des Operators bewirkt, wird Sie in einem Array platzieren. Auch wenn kein-Objekt oder ein-Objekt vorhanden ist.

Die Syntax des Array-Operators lautet wie folgt:

```syntax
@( ... )
```

Sie können den Array-Operator verwenden, um ein Array von 0 (null) oder einem Objekt zu erstellen. Beispiel:

```powershell
$a = @("Hello World")
$a.Count
```

```Output
1
```

```powershell
$b = @()
$b.Count
```

```Output
0
```

Der Array-Operator ist in Skripts nützlich, wenn Sie Objekte erhalten, aber nicht wissen, wie viele Objekte Sie erhalten. Beispiel:

```powershell
$p = @(Get-Process Notepad)
```

Weitere Informationen zum Array unter Ausdruck-Operator finden Sie unter [about_Operators](about_Operators.md).

## <a name="accessing-and-using-array-elements"></a>Zugreifen auf und Verwenden von Array Elementen

### <a name="reading-an-array"></a>Lesen eines Arrays

Sie können auf ein Array verweisen, indem Sie den Variablennamen verwenden. Wenn Sie alle Elemente im Array anzeigen möchten, geben Sie den Namen des Arrays ein. Angenommen, es handelt sich um ein Array, das die ganzen Zahlen `$a` 0, 1, 2 bis 9 enthält. Geben Sie Folgendes ein:

```powershell
$a
```

```Output
0
1
2
3
4
5
6
7
8
9
```

Sie können auf die Elemente in einem Array mithilfe eines Indexes verweisen, beginnend an Position 0. Schließen Sie die Indexnummer in eckige Klammern ein. Wenn Sie z. b. das erste Element im Array anzeigen möchten, geben Sie Folgendes ein `$a` :

```powershell
$a[0]
```

```Output
0
```

Geben Sie Folgendes ein, um das dritte Element im `$a` Array anzuzeigen:

```powershell
$a[2]
```

```Output
2
```

Sie können einen Teil des Arrays mit einem Bereichs Operator für den Index abrufen. Wenn Sie z. b. das zweite bis fünfte Element des Arrays abrufen möchten, geben Sie Folgendes ein:

```powershell
$a[1..4]
```

```Output
1
2
3
4
```

Negative Zahlen werden vom Ende des Arrays gezählt. "-1" bezieht sich z. b. auf das letzte Element des Arrays. Um die letzten drei Elemente des Arrays in aufsteigender Reihenfolge aufzurufen, geben Sie Folgendes ein:

```powershell
$a = 0 .. 9
$a[-3..-1]
```

```Output
7
8
9
```

Wenn Sie negative Indizes in absteigender Reihenfolge eingeben, ändert sich Ihre Ausgabe.

```powershell
$a = 0 .. 9
$a[-1..-3]
```

```Output
9
8
7
```

Seien Sie jedoch vorsichtig, wenn Sie diese Notation verwenden. Die Notation von der Endgrenze bis zum Anfang des Arrays.

```powershell
$a = 0 .. 9
$a[2..-2]
```

```Output
2
1
0
9
8
```

Ein häufiger Fehler besteht darin, dass auf `$a[0..-2]` alle Elemente des Arrays verweist, mit Ausnahme des letzten Elements. Er verweist auf das erste, letzte und zweite Element im Array.

Sie können den Plus-Operator ( `+` ) verwenden, um einen Bereich mit einer Liste von Elementen in einem Array zu kombinieren. Wenn Sie z. b. die Elemente an den Index Positionen 0, 2 und 4 bis 6 anzeigen möchten, geben Sie Folgendes ein:

```powershell
$a = 0 .. 9
$a[0,2+4..6]
```

```Output
0
2
4
5
6
```

Außerdem können Sie zum Auflisten mehrerer Bereiche und einzelner Elemente den Plus-Operator verwenden. Um z. b. die Elemente 0 (null) bis zwei, vier bis sechs und das-Element bei einem achten positionellen Typ aufzulisten:

```powershell
$a = 0..9
$a[+0..2+4..6+8]
```

```Output
0
1
2
4
5
6
8
```

### <a name="iterations-over-array-elements"></a>Iterationen über Array Elemente

Sie können auch Schleifen Konstrukte verwenden, z. b. foreach-, for-und while-Schleifen, um auf die Elemente in einem Array zu verweisen. Wenn Sie z. b. eine foreach-Schleife zum Anzeigen der Elemente im Array verwenden möchten, geben Sie Folgendes ein `$a` :

```powershell
$a = 0..9
foreach ($element in $a) {
  $element
}
```

```Output
0
1
2
3
4
5
6
7
8
9
```

Die foreach-Schleife durchläuft das Array und gibt jeden Wert im Array zurück, bis das Ende des Arrays erreicht ist.

Die for-Schleife ist nützlich, wenn Sie Zähler erhöhen, während Sie die Elemente in einem Array untersuchen. Wenn Sie z. b. eine for-Schleife zum Zurückgeben aller anderen Werte in einem Array verwenden möchten, geben Sie Folgendes ein:

```powershell
$a = 0..9
for ($i = 0; $i -le ($a.length - 1); $i += 2) {
  $a[$i]
}
```

```Output
0
2
4
6
8
```

Sie können eine while-Schleife verwenden, um die Elemente in einem Array anzuzeigen, bis eine definierte Bedingung nicht mehr zutrifft. Wenn Sie z. b. die Elemente im `$a` Array anzeigen möchten, während der Array Index kleiner als 4 ist, geben Sie Folgendes ein:

```powershell
$a = 0..9
$i=0
while($i -lt 4) {
  $a[$i];
  $i++
}
```

```Output
0
1
2
3
```

## <a name="properties-of-arrays"></a>Eigenschaften von Arrays

### <a name="count-or-length-or-longlength"></a>Anzahl oder Länge oder LongLength

Um zu ermitteln, wie viele Elemente sich in einem Array befinden, verwenden Sie die- `Length` Eigenschaft oder Ihren `Count` Alias. `Longlength` ist nützlich, wenn das Array mehr als 2.147.483.647 Elemente enthält.

```powershell
$a = 0..9
$a.Count
$a.Length
```

```Output
10
10
```

### <a name="rank"></a>Rang

Gibt die Anzahl der Dimensionen des Arrays zurück. Die meisten Arrays in PowerShell verfügen nur über eine einzige Dimension. Auch wenn Sie der Ansicht sind, dass Sie ein mehrdimensionales Array aufbauen, wie im folgenden Beispiel gezeigt:

```powershell
$a = @(
  @(0,1),
  @("b", "c"),
  @(Get-Process)
)

[int]$r = $a.Rank
"`$a rank: $r"
```

```Output
$a rank: 1
```

Im folgenden Beispiel wird gezeigt, wie ein wirklich mehrdimensionales Array mithilfe von .NET Framework erstellt wird.

```powershell
[int[,]]$rank2 = [int[,]]::new(5,5)
$rank2.rank
```

```Output
2
```

## <a name="methods-of-arrays"></a>Methoden von Arrays

### <a name="clear"></a>Clear

Legt alle Element Werte auf den _Standardwert_ des Elementtyps des Arrays fest.
Die Clear ()-Methode setzt nicht die Größe des Arrays zurück.

Im folgenden Beispiel `$a` ist ein Array von-Objekten.

```powershell
$a = 1, 2, 3
$a.Clear()
$a | % { $null -eq $_ }
```

```Output
True
True
True
```

In diesem Beispiel `$intA` ist explizit typisiert, um ganze Zahlen zu enthalten.

```powershell
[int[]] $intA = 1, 2, 3
$intA.Clear()
$intA
```

```Output
0
0
0
```

### <a name="foreach"></a>ForEach

Ermöglicht das Durchlaufen aller Elemente im Array und das Ausführen eines bestimmten Vorgangs für jedes Element des Arrays.

Die foreach-Methode verfügt über mehrere über Ladungen, die verschiedene Vorgänge ausführen.

```
ForEach(scriptblock expression)
ForEach(scriptblock expression, object[] arguments)
ForEach(type convertToType)
ForEach(string propertyName)
ForEach(string propertyName, object[] newValue)
ForEach(string methodName)
ForEach(string methodName, object[] arguments)
```

#### <a name="foreachscriptblock-expression"></a>Foreach (ScriptBlock-Ausdruck)

#### <a name="foreachscriptblock-expression-object-arguments"></a>Foreach (ScriptBlock-Ausdruck, Object []-Argumente)

Diese Methode wurde in PowerShell V4 hinzugefügt.

> [!NOTE]
> Die Syntax erfordert die Verwendung eines Skript Blocks. Klammern sind optional, wenn ScriptBlock der einzige Parameter ist. Außerdem darf kein Leerzeichen zwischen der-Methode und der öffnenden Klammer oder geschweiften Klammer vorhanden sein.

Im folgenden Beispiel wird gezeigt, wie die foreach-Methode verwendet wird. In diesem Fall ist es beabsichtigt, den quadratischen Wert der Elemente im Array zu generieren.

```powershell
$a = @(0 .. 3)
$a.ForEach({ $_ * $_})
```

```Output
0
1
4
9
```

Genau wie der- `-ArgumentList` Parameter von `ForEach-Object` ermöglicht der- `arguments` Parameter das Übergeben eines Arrays von Argumenten an einen Skriptblock, der für die Annahme konfiguriert ist.

Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about_Splatting.md#splatting-with-arrays).

#### <a name="foreachtype-converttotype"></a>Foreach (ConvertToType-Typ)

Die- `ForEach` Methode kann verwendet werden, um die Elemente schnell in einen anderen Typ umzuwandeln. im folgenden Beispiel wird gezeigt, wie eine Liste von Zeichen folgen Datumsangaben in den Typ konvertiert wird `[DateTime]` .

```powershell
@("1/1/2017", "2/1/2017", "3/1/2017").ForEach([datetime])
```

```Output

Sunday, January 1, 2017 12:00:00 AM
Wednesday, February 1, 2017 12:00:00 AM
Wednesday, March 1, 2017 12:00:00 AM
```

#### <a name="foreachstring-propertyname"></a>Foreach (String propertyName)

#### <a name="foreachstring-propertyname-object-newvalue"></a>Foreach (String propertyName, Object [] newValue)

Die- `ForEach` Methode kann auch verwendet werden, um die Eigenschaftswerte für jedes Element in der Auflistung schnell abzurufen oder festzulegen.

```powershell
# Set all LastAccessTime properties of files to the current date.
(dir 'C:\Temp').ForEach('LastAccessTime', (Get-Date))
# View the newly set LastAccessTime of all items, and find Unique entries.
(dir 'C:\Temp').ForEach('LastAccessTime') | Get-Unique
```

```Output
Wednesday, June 20, 2018 9:21:57 AM
```

#### <a name="foreachstring-methodname"></a>Foreach (Zeichenfolge MethodName)

#### <a name="foreachstring-methodname-object-arguments"></a>Foreach (String MethodName, Object []-Argumente)

Schließlich `ForEach` können Methoden verwendet werden, um eine Methode für jedes Element in der Auflistung auszuführen.

```powershell
("one", "two", "three").ForEach("ToUpper")
```

```Output
ONE
TWO
THREE
```

Genau wie der- `-ArgumentList` Parameter von `ForEach-Object` ermöglicht der- `arguments` Parameter das Übergeben eines Arrays von Argumenten an einen Skriptblock, der für die Annahme konfiguriert ist.

> [!NOTE]
> Ab Windows PowerShell 3,0 kann das Abrufen von Eigenschaften und das Ausführen von Methoden für jedes Element in einer Auflistung auch mithilfe von "Methoden von skalaren Objekten und Auflistungen" durchgeführt werden. Weitere Informationen hierzu [about_methods](about_methods.md)finden Sie hier.

### <a name="where"></a>Hierbei gilt:

Ermöglicht das Filtern oder auswählen der Elemente des Arrays. Das Skript muss zu einem beliebigen anderen Ergebnis als: NULL (0), leere Zeichenfolge `$false` oder `$null` für das Element angezeigt werden, das nach dem `Where`

Es gibt eine Definition für die- `Where` Methode.

```
Where(scriptblock expression[, WhereOperatorSelectionMode mode
                            [, int numberToReturn]])
```

> [!NOTE]
> Die Syntax erfordert die Verwendung eines Skript Blocks. Klammern sind optional, wenn ScriptBlock der einzige Parameter ist. Außerdem darf kein Leerzeichen zwischen der-Methode und der öffnenden Klammer oder geschweiften Klammer vorhanden sein.

Der `Expression` ist ScriptBlock, der für das Filtern erforderlich ist, das `mode` optionale-Argument ermöglicht zusätzliche Auswahlmöglichkeiten, und das `numberToReturn` optionale-Argument ermöglicht die Beschränkung, wie viele Elemente vom Filter zurückgegeben werden.

Die zulässigen Werte für lauten `mode` :

- Standard (0)-alle Elemente zurückgeben
- First (1): gibt das erste Element zurück.
- Last (2): Zurückgeben des letzten Elements
- Skipuntil (3): überspringen Sie Elemente, bis die Bedingung erfüllt ist, und geben Sie die restlichen Elemente zurück.
- Bis (4)-alle Elemente zurückgeben, bis die Bedingung erfüllt ist
- Split (5): Rückgabe eines Arrays mit zwei Elementen
  - Das erste Element enthält übereinstimmende Elemente.
  - Das zweite Element enthält die übrigen Elemente.

Im folgenden Beispiel wird gezeigt, wie alle ungeraden Zahlen aus dem Array ausgewählt werden.

```powershell
(0..9).Where{ $_ % 2 }
```

```Output
1
3
5
7
9
```

In diesem Beispiel wird gezeigt, wie die Zeichen folgen ausgewählt werden, die nicht leer sind.

```powershell
('hi', '', 'there').Where({$_.Length})
```

```Output
hi
there
```

#### <a name="default"></a>Standard

Der `Default` Modus filtert Elemente mithilfe von `Expression` ScriptBlock.

Wenn eine `numberToReturn` bereitgestellt wird, gibt Sie die maximale Anzahl von Elementen an, die zurückgegeben werden sollen.

```powershell
# Get the zip files in the current users profile, sorted by LastAccessTime.
$Zips = dir $env:userprofile -Recurse '*.zip' | Sort-Object LastAccessTime
# Get the least accessed file over 100MB
$Zips.Where({$_.Length -gt 100MB}, 'Default', 1)
```

> [!NOTE]
> Sowohl der `Default` Modus als auch der `First` Modus geben die ersten `numberToReturn` Elemente () zurück und können austauschbar verwendet werden.

#### <a name="last"></a>Letzter

```powershell
$h = (Get-Date).AddHours(-1)
$logs = dir 'C:\' -Recurse '*.log' | Sort-Object CreationTime
# Find the last 5 log files created in the past hour.
$logs.Where({$_.CreationTime -gt $h}, 'Last', 5)
```

#### <a name="skipuntil"></a>Überspringen bis

Der `SkipUntil` Modus überspringt alle Objekte in einer Auflistung, bis ein Objekt den Filter für den Skriptblock Ausdruck übergibt. Anschließend werden **alle** verbleibenden Sammel Elemente zurückgegeben, ohne Sie zu testen. _Nur ein Element, das übergeben wird, wird getestet_.

Dies bedeutet, dass die zurückgegebene _Auflistung sowohl übergebene als auch_ _nicht weiter_ gegebene Elemente enthält, die nicht getestet wurden.

Die Anzahl der zurückgegebenen Elemente kann eingeschränkt werden, indem ein-Wert an das-Argument übergeben wird `numberToReturn` .

```powershell
$computers = "Server01", "Server02", "Server03", "localhost", "Server04"
# Find the first available online server.
$computers.Where({ Test-Connection $_ }, 'SkipUntil', 1)
```

```Output
localhost
```

#### <a name="until"></a>Until

Der Modus `Until` kehrt in den `SkipUntil` Modus um.  **Alle** Elemente in einer Auflistung werden zurückgegeben, bis ein Element den Skriptblock Ausdruck übergibt. Wenn ein Element den ScriptBlock-Ausdruck _übergibt_ , `Where` beendet die Methode die Verarbeitung von Elementen.

Dies bedeutet, dass Sie den ersten Satz _nicht weiter übergebenen_ Elemente von der- `Where` Methode erhalten. _Nachdem_ ein Element weitergegeben wurde, wird der Rest nicht getestet oder zurückgegeben.

Die Anzahl der zurückgegebenen Elemente kann eingeschränkt werden, indem ein-Wert an das-Argument übergeben wird `numberToReturn` .

```powershell
# Retrieve the first set of numbers less than or equal to 10.
(1..50).Where({$_ -gt 10}, 'Until')
# This would perform the same operation.
(1..50).Where({$_ -le 10})
```

```Output
1
2
3
4
5
6
7
8
9
10
```

> [!NOTE]
> Sowohl `Until` als auch `SkipUntil` arbeiten unter der Voraussetzung, dass kein Batch von Elementen getestet wird.
>
> `Until` Gibt die Elemente **vor** dem ersten _Durchlauf_ zurück.
>
> `SkipUntil` Gibt alle Elemente **nach** dem ersten _Durchlauf_ zurück, einschließlich des ersten Elements, das übergeben wird.

#### <a name="split"></a>Split

Der `Split` Modus teilt oder gruppiert Auflistungs Elemente in zwei separate Auflistungen. Die, die den ScriptBlock-Ausdruck übergeben, und diejenigen, die dies nicht tun.

Wenn eine `numberToReturn` angegeben wird, enthält die erste Auflistung die _Übergabe_ Elemente, sodass der angegebene Wert nicht überschritten wird.

Die übrigen Objekte, auch jene, die den Ausdrucks Filter **passieren** , werden in der zweiten Auflistung zurückgegeben.

```powershell
$running, $stopped = (Get-Service).Where({$_.Status -eq 'Running'}, 'Split')
$running
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  AudioEndpointBu... Windows Audio Endpoint Builder
Running  Audiosrv           Windows Audio
...
```

```powershell
$stopped
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
...
```

## <a name="get-the-members-of-an-array"></a>Mitglieder eines Arrays erhalten

Verwenden Sie den **Inputobject** -Parameter des Cmdlets, um die Eigenschaften und Methoden eines Arrays zu erhalten, z. b. die length-Eigenschaft und die **SetValue** -Methode `Get-Member` .

Wenn Sie ein Array an übergeben `Get-Member` , sendet PowerShell die Elemente nacheinander und `Get-Member` gibt den Typ der einzelnen Elemente im Array zurück (wobei Duplikate ignoriert werden).

Wenn Sie den **Inputobject** -Parameter verwenden, `Get-Member` gibt die Elemente des Arrays zurück.

Beispielsweise ruft der folgende Befehl die Member der `$a` Array Variablen ab.

```powershell
Get-Member -InputObject $a
```

Sie können auch die Member eines Arrays aufrufen, indem Sie ein Komma (,) vor dem Wert eingeben, der an das `Get-Member` Cmdlet weitergeleitet wird. Das Komma bewirkt, dass das Array das zweite Element in einem Array von Arrays ist. PowerShell übergibt die Arrays nacheinander und `Get-Member` gibt die Elemente des Arrays zurück. Wie in den folgenden beiden Beispielen gezeigt.

```powershell
,$a | Get-Member

,(1,2,3) | Get-Member
```

## <a name="manipulating-an-array"></a>Bearbeiten eines Arrays

Sie können die Elemente in einem Array ändern, ein Element zu einem Array hinzufügen und die Werte von zwei Arrays zu einem dritten Array kombinieren.

Um den Wert eines bestimmten Elements in einem Array zu ändern, geben Sie den Namen des Arrays und den Index des Elements an, das Sie ändern möchten, und verwenden Sie dann den Zuweisungs Operator ( `=` ), um einen neuen Wert für das Element anzugeben. Um z. b. den Wert des zweiten Elements im `$a` Array (Indexposition 1) auf 10 zu ändern, geben Sie Folgendes ein:

```powershell
$a[1] = 10
```

Sie können auch die **SetValue** -Methode eines Arrays verwenden, um einen Wert zu ändern. Im folgenden Beispiel wird der zweite Wert (Indexposition 1) des `$a` Arrays in 500 geändert:

```powershell
$a.SetValue(500,1)
```

Sie können den- `+=` Operator verwenden, um einem Array ein Element hinzuzufügen. Im folgenden Beispiel wird gezeigt, wie dem Array ein Element hinzugefügt wird `$a` .

```powershell
$a = @(0..4)
$a += 5
```

> [!NOTE]
> Wenn Sie den- `+=` Operator verwenden, erstellt PowerShell tatsächlich ein neues Array mit den Werten des ursprünglichen Arrays und dem hinzugefügten Wert. Dies kann zu Leistungsproblemen führen, wenn der Vorgang mehrmals wiederholt oder die Größe des Arrays zu groß ist.

Es ist nicht einfach, Elemente aus einem Array zu löschen. Sie können jedoch ein neues Array erstellen, das nur ausgewählte Elemente eines vorhandenen Arrays enthält. Wenn Sie z. b. das `$t` Array mit allen Elementen im `$a` Array mit Ausnahme des Werts an der Indexposition 2 erstellen möchten, geben Sie Folgendes ein:

```powershell
$t = $a[0,1 + 3..($a.length - 1)]
```

Um zwei Arrays zu einem einzelnen Array zu kombinieren, verwenden Sie den Plus-Operator ( `+` ). Im folgenden Beispiel werden zwei Arrays erstellt, kombiniert und dann das resultierende kombinierte Array angezeigt.

```powershell
$x = 1,3
$y = 5,9
$z = $x + $y
```

Folglich `$z` enthält das Array 1, 3, 5 und 9.

Zum Löschen eines Arrays weisen `$null` Sie dem Array einen Wert von zu. Der folgende Befehl löscht das Array in der `$a` Variablen.

`$a = $null`

Sie können auch das- `Remove-Item` Cmdlet verwenden, aber das Zuweisen eines Werts von `$null` ist schneller, insbesondere bei großen Arrays.

## <a name="arrays-of-zero-or-one"></a>Arrays von 0 (null) oder 1

Ab Windows PowerShell 3,0 weist eine Auflistung von 0 (null) oder ein-Objekt die count-und length-Eigenschaft auf. Außerdem können Sie einen Index in ein Array von einem Objekt indizieren. Diese Funktion hilft Ihnen, Skript Fehler zu vermeiden, die auftreten, wenn ein Befehl, der eine Auflistung erwartet, weniger als zwei Elemente erhält.

Diese Funktion wird in den folgenden Beispielen veranschaulicht.

### <a name="zero-objects"></a>Null-Objekte

```powershell
$a = $null
$a.Count
$a.Length
```

```Output
0
0
```

### <a name="one-object"></a>Ein Objekt

```powershell
$a = 4
$a.Count
$a.Length
$a[0]
$a[-1]
```

```Output
1
1
4
4
```

## <a name="indexing-support-for-systemtuple-objects"></a>Indizierungs Unterstützung für System. Tuple-Objekte

PowerShell 6,1 hat die Unterstützung für den indizierten Zugriff von **tupelobjekten** ähnlich wie Arrays hinzugefügt.
Beispiel:

```powershell
PS> $tuple = [Tuple]::Create(1, 'test')
PS> $tuple[0]
1
PS> $tuple[1]
test
PS> $tuple[0..1]
1
test
PS> $tuple[-1]
test
```

Im Gegensatz zu Arrays und anderen Auflistungs Objekten werden **tupelobjekte** beim Durchlaufen der Pipeline oder durch Parameter, die Arrays von Objekten unterstützen, als einzelnes Objekt behandelt.

Weitere Informationen finden Sie unter [System. Tupel](/dotnet/api/system.tuple).

## <a name="see-also"></a>Weitere Informationen:

- [about_Assignment_Operators](about_Assignment_Operators.md)
- [about_Hash_Tables](about_Hash_Tables.md)
- [about_Operators](about_Operators.md)
- [about_For](about_For.md)
- [about_Foreach](about_Foreach.md)
- [about_While](about_While.md)

