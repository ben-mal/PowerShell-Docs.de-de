---
description: Beschreibt die Operatoren, die von PowerShell unterstützt werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/28/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operators
ms.openlocfilehash: a917afc1499af96f834496c22e5634826c5aeb73
ms.sourcegitcommit: c1e4739f5d52282fb05a8cff92b0f5d10e2edac1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2020
ms.locfileid: "93225292"
---
# <a name="about-operators"></a>Informationen zu Operatoren

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt die Operatoren, die von PowerShell unterstützt werden.

## <a name="long-description"></a>Lange Beschreibung

Ein Operator ist ein sprach Element, das Sie in einem Befehl oder Ausdruck verwenden können.
PowerShell unterstützt verschiedene Typen von Operatoren, die Ihnen bei der Bearbeitung von Werten helfen.

### <a name="arithmetic-operators"></a>Arithmetische Operatoren

Verwenden Sie arithmetische Operatoren ( `+` , `-` , `*` , `/` , `%` ), um Werte in einem Befehl oder Ausdruck zu berechnen. Mit diesen Operatoren können Sie Werte hinzufügen, subtrahieren, multiplizieren oder Teilen und den Rest (Modulus) einer Divisions Operation berechnen.

Der Additions Operator verkettet Elemente. Der Multiplikations Operator gibt die angegebene Anzahl von Kopien der einzelnen Elemente zurück. Sie können arithmetische Operatoren für jeden .NET-Typ verwenden, der Sie implementiert, z `Int` . b.:, `String` ,, `DateTime` `Hashtable` und Arrays.

Bitweise Operatoren ( `-band` , `-bor` , `-bxor` , `-bnot` , `-shl` , `-shr` ) verändern die Bitmuster in-Werten.

Weitere Informationen finden Sie unter [about_Arithmetic_Operators](about_Arithmetic_Operators.md).

### <a name="assignment-operators"></a>Zuweisungsoperatoren

Verwenden Sie Zuweisungs Operatoren ( `=` , `+=` , `-=` , `*=` , `/=` , `%=` ), um Variablen zuzuweisen, zu ändern oder Werte anzufügen. Sie können arithmetische Operatoren mit Zuweisung kombinieren, um das Ergebnis der arithmetischen Operation einer Variablen zuzuweisen.

Weitere Informationen finden Sie unter [about_Assignment_Operators](about_Assignment_Operators.md).

### <a name="comparison-operators"></a>Vergleichsoperatoren

Verwenden Sie Vergleichs Operatoren ( `-eq` , `-ne` , `-gt` , `-lt` , `-le` , `-ge` ), um Werte und Testbedingungen zu vergleichen. Beispielsweise können Sie zwei Zeichen folgen Werte vergleichen, um zu bestimmen, ob Sie gleich sind.

Die Vergleichs Operatoren enthalten auch Operatoren, die Textmuster suchen oder ersetzen. Die `-match` `-notmatch` Operatoren (,, `-replace` ) verwenden reguläre Ausdrücke, und ( `-like` , `-notlike` ) verwenden `*` Platzhalter.

Containment-Vergleichs Operatoren bestimmen, ob ein Testwert in einem Verweis Satz ( `-in` ,, `-notin` `-contains` ,) angezeigt wird `-notcontains` .

Typvergleichs Operatoren ( `-is` , `-isnot` ) bestimmen, ob ein Objekt einen bestimmten Typ hat.

Weitere Informationen finden Sie unter [about_Comparison_Operators](about_Comparison_Operators.md).

### <a name="logical-operators"></a>Logische Operatoren

Verwenden Sie logische Operatoren ( `-and` , `-or` , `-xor` , `-not` , `!` ), um bedingte Anweisungen mit einer einzelnen komplexen Bedingung zu verbinden. Beispielsweise können Sie einen logischen Operator verwenden `-and` , um einen Objekt Filter mit zwei verschiedenen Bedingungen zu erstellen.

Weitere Informationen finden Sie unter [about_Logical_Operators](about_logical_operators.md).

### <a name="redirection-operators"></a>Umleitungs Operatoren

Verwenden Sie die Umleitungs Operatoren ( `>` , `>>` , `2>` , `2>>` und `2>&1` ), um die Ausgabe eines Befehls oder Ausdrucks an eine Textdatei zu senden. Die Umleitungs Operatoren arbeiten wie das `Out-File` Cmdlet (ohne Parameter), Sie ermöglichen Ihnen jedoch auch das Umleiten der Fehlerausgabe an bestimmte Dateien. Sie können auch das- `Tee-Object` Cmdlet zum Umleiten der Ausgabe verwenden.

Weitere Informationen finden Sie unter [about_Redirection](about_Redirection.md)

### <a name="split-and-join-operators"></a>Split-und Join-Operatoren

Die `-split` `-join` Operatoren und unterteilen und kombinieren Teil Zeichenfolgen. Der- `-split` Operator teilt eine Zeichenfolge in Teil Zeichenfolgen auf. Der `-join` Operator verkettet mehrere Zeichen folgen zu einer einzelnen Zeichenfolge.

Weitere Informationen finden Sie unter [about_Split](about_Split.md) und [about_Join](about_Join.md).

### <a name="type-operators"></a>Typoperatoren

Verwenden Sie die Typoperatoren ( `-is` , `-isnot` , `-as` ), um den .NET Framework Typ eines Objekts zu suchen oder zu ändern.

Weitere Informationen finden Sie unter [about_Type_Operators](about_Type_Operators.md).

### <a name="unary-operators"></a>Unäre Operatoren

Verwenden Sie unäre Operatoren, um Variablen oder Objekteigenschaften zu erhöhen oder zu verringern und um ganze Zahlen auf positive oder negative Zahlen festzulegen. Wenn Sie z. b. die Variable `$a` von `9` auf erhöhen möchten `10` , geben Sie ein `$a++` .

### <a name="special-operators"></a>Spezielle Operatoren

Spezielle Operatoren verfügen über bestimmte Anwendungsfälle, die nicht in eine andere Operator Gruppe passen. Beispielsweise können Sie mit speziellen Operatoren Befehle ausführen, den Datentyp eines Werts ändern oder Elemente aus einem Array abrufen.

#### <a name="grouping-operator--"></a>Gruppierungs Operator `( )`

Wie in anderen Sprachen, `(...)` dient zum Überschreiben der Operator Rangfolge in Ausdrücken. Beispiel: `(1 + 2) / 3`

In PowerShell gibt es jedoch zusätzliche Verhaltensweisen.

- `(...)` ermöglicht das zulassen, dass die Ausgabe eines _Befehls_ an einem Ausdruck teilnimmt. Beispiel:

  ```powershell
  PS> (Get-Item *.txt).Count -gt 10
  True
  ```

- Bei Verwendung als erstes Segment einer Pipeline bewirkt das Einschließen eines Befehls oder Ausdrucks in Klammern unweigerlich eine _Enumeration_ des Ausdrucks Ergebnisses. Wenn die Klammern einen _Befehl_ einschließen, wird die Ausführung bis zum Ende _der Ausgabe abgeschlossen_ , bevor die Ergebnisse über die Pipeline gesendet werden.

#### <a name="subexpression-operator--"></a>Subexpression-Operator `$( )`

Gibt das Ergebnis einer oder mehrerer-Anweisungen zurück. Für ein einzelnes Ergebnis wird ein Skalar zurückgegeben. Für mehrere Ergebnisse wird ein Array zurückgegeben. Verwenden Sie diese, wenn Sie einen Ausdruck in einem anderen Ausdruck verwenden möchten. Zum Einbetten der Ergebnisse des Befehls in einen Zeichen folgen Ausdruck.

```powershell
PS> "Today is $(Get-Date)"
Today is 12/02/2019 13:15:20

PS> "Folder list: $((dir c:\ -dir).Name -join ', ')"
Folder list: Program Files, Program Files (x86), Users, Windows
```

#### <a name="array-subexpression-operator--"></a>Array Teil Ausdruck-Operator `@( )`

Gibt das Ergebnis einer oder mehrerer-Anweisungen als Array zurück. Wenn nur ein Element vorhanden ist, verfügt das Array nur über einen Member.

```powershell
@(Get-CimInstance win32_logicalDisk)
```

#### <a name="call-operator-"></a>Calloperator `&`

Führt einen Befehl, ein Skript oder einen Skriptblock aus. Mit dem Aufruf Operator, der auch als "Aufruf Operator" bezeichnet wird, können Sie Befehle ausführen, die in Variablen gespeichert sind und durch Zeichen folgen oder Skriptblöcke dargestellt werden. Der "calloperator" wird in einem untergeordneten Bereich ausgeführt. Weitere Informationen zu Bereichen finden Sie unter [about_Scopes](about_Scopes.md).

In diesem Beispiel wird ein Befehl in einer Zeichenfolge gespeichert und mit dem-Operator aufgerufen.

```
PS> $c = "get-executionpolicy"
PS> $c
get-executionpolicy
PS> & $c
AllSigned
```

Der "calloperator" analysiert keine Zeichen folgen. Dies bedeutet, dass Sie Befehlsparameter nicht innerhalb einer Zeichenfolge verwenden können, wenn Sie den Operator "Operator" verwenden.

```
PS> $c = "Get-Service -Name Spooler"
PS> $c
Get-Service -Name Spooler
PS> & $c
& : The term 'Get-Service -Name Spooler' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of
the name, or if a path was included, verify that the path is correct and
try again.
```

Das Cmdlet "callcmdlet" kann Code ausführen [, der bei](xref:Microsoft.PowerShell.Utility.Invoke-Expression) Verwendung des Aufruf Operators Analyse-Fehler auslöst.

```
PS> & "1+1"
& : The term '1+1' is not recognized as the name of a cmdlet, function, script
file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:2
+ & "1+1"
+  ~~~~~
    + CategoryInfo          : ObjectNotFound: (1+1:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
PS> Invoke-Expression "1+1"
2
```

Sie können den calloperator verwenden, um Skripts mit ihren Dateinamen auszuführen. Das folgende Beispiel zeigt einen Skript Dateinamen, der Leerzeichen enthält. Wenn Sie versuchen, das Skript auszuführen, zeigt PowerShell stattdessen den Inhalt der Zeichenfolge in Anführungszeichen an, die den Dateinamen enthält. Mit dem Operator "calloperator" können Sie den Inhalt der Zeichenfolge mit dem Dateinamen ausführen.

```
PS C:\Scripts> Get-ChildItem

    Directory: C:\Scripts


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/28/2018   1:36 PM             58 script name with spaces.ps1

PS C:\Scripts> ".\script name with spaces.ps1"
.\script name with spaces.ps1
PS C:\Scripts> & ".\script name with spaces.ps1"
Hello World!
```

Weitere Informationen zu Skript Blöcken finden Sie unter [about_Script_Blocks](about_Script_Blocks.md).

#### <a name="background-operator-"></a>Background-Operator `&`

Führt die Pipeline vor diesem im Hintergrund in einem PowerShell-Auftrag aus. Dieser Operator verhält sich ähnlich wie der UNIX-Steuerelement Operator kaufmännisches und-Zeichen ( `&` ), das den Befehl vor der asynchronen Ausführung in der Subshell als Auftrag ausführt.

Dieser Operator ist funktionell äquivalent zu `Start-Job` . Standardmäßig startet der Hintergrund Operator die Aufträge im aktuellen Arbeitsverzeichnis des Aufrufers, der die parallelen Aufgaben gestartet hat. Im folgenden Beispiel wird die grundlegende Verwendung des Hintergrund Auftrags Operators veranschaulicht.

```powershell
Get-Process -Name pwsh &
```

Dieser Befehl ist funktional äquivalent zur folgenden Verwendung von `Start-Job` :

```powershell
Start-Job -ScriptBlock {Get-Process -Name pwsh}
```

Ebenso wie `Start-Job` gibt der `&` Background-Operator ein- `Job` Objekt zurück. Dieses Objekt kann mit und verwendet `Receive-Job` werden `Remove-Job` , genau so, als hätten Sie `Start-Job` den Auftrag gestartet.

```powershell
$job = Get-Process -Name pwsh &
Receive-Job $job -Wait
```

```Output

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
      0     0.00     221.16      25.90    6988 988 pwsh
      0     0.00     140.12      29.87   14845 845 pwsh
      0     0.00      85.51       0.91   19639 988 pwsh

```

```powershell
Remove-Job $job
```

Der `&` Background-Operator ist auch ein Anweisungs Abschluss Zeichen, genauso wie der UNIX-Steuerelement Operator kaufmännisches und-Zeichen ( `&` ). Dies ermöglicht es Ihnen, zusätzliche Befehle nach dem `&` Hintergrund Operator aufzurufen. Im folgenden Beispiel wird der Aufruf zusätzlicher Befehle nach dem Background- `&` Operator veranschaulicht.

```powershell
$job = Get-Process -Name pwsh & Receive-Job $job -Wait
```

```Output

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
      0     0.00     221.16      25.90    6988 988 pwsh
      0     0.00     140.12      29.87   14845 845 pwsh
      0     0.00      85.51       0.91   19639 988 pwsh

```

Dies entspricht dem folgenden Skript:

```powershell
$job = Start-Job -ScriptBlock {Get-Process -Name pwsh}
Receive-Job $job -Wait
```

Wenn Sie mehrere Befehle ausführen möchten, die sich jeweils in einem eigenen Hintergrundprozess, aber alle in einer Zeile befinden, können Sie einfach `&` zwischen und nach jedem der Befehle platzieren.

```powershell
Get-Process -Name pwsh & Get-Service -Name BITS & Get-CimInstance -ClassName Win32_ComputerSystem &
```

Weitere Informationen zu PowerShell-Aufträgen finden Sie unter [about_Jobs](about_Jobs.md).

#### <a name="cast-operator--"></a>Cast-Operator `[ ]`

Konvertiert Objekte in den angegebenen Typ oder schränkt diese ein. Wenn die Objekte nicht konvertiert werden können, generiert PowerShell einen Fehler.

```powershell
[DateTime]"2/20/88" - [DateTime]"1/20/88"
[Int] (7/2)
[String] 1 + 0
[Int] '1' + 0
```

Eine Umwandlung kann auch ausgeführt werden, wenn eine Variable mithilfe von [Cast Notation](about_Variables.md)zugewiesen wird.

#### <a name="comma-operator-"></a>Komma-Operator `,`

Als binärer Operator erstellt das Komma ein Array oder wird an das Array angehängt, das erstellt wird. Im Ausdrucks Modus erstellt das Komma als unärer Operator ein Array mit nur einem Member. Platzieren Sie das Komma vor dem Member.

```powershell
$myArray = 1,2,3
$SingleArray = ,1
Write-Output (,1)
```

Da `Write-Object` ein Argument erwartet, muss der Ausdruck in Klammern gesetzt werden.

#### <a name="dot-sourcing-operator-"></a>Punkt-Sourcing-Operator `.`

Führt ein Skript im aktuellen Bereich aus, sodass alle Funktionen, Aliase und Variablen, die das Skript erstellt, dem aktuellen Gültigkeitsbereich hinzugefügt werden und vorhandene überschreiben. Vom Skript deklarierte Parameter werden zu Variablen. Parameter, für die kein Wert angegeben wurde, werden zu Variablen ohne Wert. Die automatische Variable wird jedoch `$args` beibehalten.

```powershell
. c:\scripts\sample.ps1 1 2 -Also:3
```

> [!NOTE]
> Auf den Punkt-Sourcing-Operator folgt ein Leerzeichen. Verwenden Sie den Leerraum, um den Punkt vom Punkt Symbol () zu unterscheiden `.` , das das aktuelle Verzeichnis darstellt.
>
> Im folgenden Beispiel wird das Sample.ps1 Skript im aktuellen Verzeichnis im aktuellen Bereich ausgeführt.
>
> ```powershell
> . .\sample.ps1
> ```

#### <a name="format-operator--f"></a>Format-Operator `-f`

Formatiert Zeichen folgen mithilfe der Format-Methode von Zeichen folgen Objekten. Geben Sie die Format Zeichenfolge auf der linken Seite des Operators und die Objekte ein, die auf der rechten Seite des Operators formatiert werden sollen.

```powershell
"{0} {1,-10} {2:N}" -f 1,"hello",[math]::pi
```

```output
1 hello      3.14
```

Wenn Sie die geschweiften Klammern ( `{}` ) in der formatierten Zeichenfolge aufbewahren müssen, können Sie Sie mit Escapezeichen versehen, indem Sie die geschweiften Klammern verdoppeln.

```powershell
"{0} vs. {{0}}" -f 'foo'
```

```Output
foo vs. {0}
```

Weitere Informationen finden Sie in der [String. Format](/dotnet/api/system.string.format) -Methode und in der zusammen [gesetzten Formatierung](/dotnet/standard/base-types/composite-formatting).

#### <a name="index-operator--"></a>Index-Operator `[ ]`

Wählt Objekte aus indizierten Auflistungen aus, z. b. Arrays und Hash Tabellen. Array Indizes sind NULL basiert, sodass das erste Objekt als indiziert wird `[0]` . Für Arrays (nur) können Sie auch negative Indizes verwenden, um die letzten Werte zu erhalten. Hash Tabellen werden nach Schlüsselwert indiziert.

```
PS> $a = 1, 2, 3
PS> $a[0]
1
PS> $a[-1]
3
```

```powershell
(Get-HotFix | Sort-Object installedOn)[-1]
```

```powershell
$h = @{key="value"; name="PowerShell"; version="2.0"}
$h["name"]
```

```output
PowerShell
```

```powershell
$x = [xml]"<doc><intro>Once upon a time...</intro></doc>"
$x["doc"]
```

```output
intro
-----
Once upon a time...
```

#### <a name="pipeline-operator-"></a>Pipeline-Operator `|`

Sendet ("Pipes") die Ausgabe des Befehls, der diesem vorangestellt ist, an den darauf folgenden Befehl. Wenn die Ausgabe mehr als ein Objekt (eine "Auflistung") enthält, sendet der Pipeline Operator die Objekte nacheinander.

```powershell
Get-Process | Get-Member
Get-Service | Where-Object {$_.StartType -eq 'Automatic'}
```

#### <a name="pipeline-chain-operators--and-"></a>Pipeline Ketten Operatoren `&&` und `||`

Führen Sie die auf der rechten Seite basierende Pipeline bedingt basierend auf dem Erfolg der linken Pipeline aus.

```powershell
# If Get-Process successfully finds a process called notepad,
# Stop-Process -Name notepad is called
Get-Process notepad && Stop-Process -Name notepad
```

```powershell
# If npm install fails, the node_modules directory is removed
npm install || Remove-Item -Recurse ./node_modules
```

Weitere Informationen finden Sie unter [About_Pipeline_Chain_Operators](About_Pipeline_Chain_Operators.md).

#### <a name="range-operator-"></a>Bereichs Operator `..`

Stellt die sequenziellen Ganzzahlen in einem ganzzahligen Array dar, wenn eine obere und untere Grenze angegeben ist.

```powershell
1..10
foreach ($a in 1..$max) {Write-Host $a}
```

Sie können Bereiche auch in umgekehrter Reihenfolge erstellen.

```powershell
10..1
5..-5 | ForEach-Object {Write-Output $_}
```

Beginnend mit PowerShell 6 verwendet der Bereichs Operator sowohl **Zeichen** als auch **ganze** Zahlen.

Um einen Zeichenbereich zu erstellen, müssen Sie die Begrenzungs Zeichen in Anführungszeichen einschließen.

```powershell
PS> 'a'..'f'
a
b
c
d
e
f
```

```powershell
PS> 'F'..'A'
F
E
D
C
B
A
```

#### <a name="member-access-operator-"></a>Member Access-Operator `.`

Greift auf die Eigenschaften und Methoden eines Objekts zu. Der Elementname kann ein Ausdruck sein.

```powershell
$myProcess.peakWorkingSet
(Get-Process PowerShell).kill()
'OS', 'Platform' | Foreach-Object { $PSVersionTable. $_ }
```

#### <a name="static-member-operator-"></a>Statischer Member-Operator `::`

Ruft die statischen Eigenschaften und Methoden einer .NET Framework Klasse auf. Verwenden Sie den static-Parameter des Cmdlets, um die statischen Eigenschaften und Methoden eines Objekts zu suchen `Get-Member` .  Der Elementname kann ein Ausdruck sein.

```powershell
[datetime]::Now
'MinValue', 'MaxValue' | Foreach-Object { [int]:: $_ }
```

#### <a name="ternary-operator--if-true--if-false"></a>Ternärer Operator `? <if-true> : <if-false>`

Der ternäre Operator kann als Ersatz für die- `if-else` Anweisung in einfachen bedingten Fällen verwendet werden.

Weitere Informationen finden Sie unter [about_If](about_If.md).

#### <a name="null-coalescing-operator-"></a>NULL-Sammel Operator `??`

Der NULL-Sammeloperator `??` gibt den Wert seines linken Operanden zurück, wenn er nicht NULL ist. Andernfalls wertet er den rechten Operanden aus und gibt sein Ergebnis zurück. Der Operator `??` wertet seinen rechten Operanden nicht aus, wenn der linke Operand mit ungleich NULL auswertet wird.

```powershell
$x = $null
$x ?? 100
```

```Output
100
```

Im folgenden Beispiel wird der rechte Operand nicht ausgewertet.

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ?? (Get-Date).ToShortDateString()
```

```Output
1/10/2020
```

#### <a name="null-coalescing-assignment-operator-"></a>NULL-Sammel Zuweisungs Operator `??=`

Der NULL-Sammel Zuweisungs Operator `??=` weist den Wert des rechten Operanden dem linken Operanden nur zu, wenn der linke Operand als NULL ausgewertet wird. Der Operator `??=` wertet seinen rechten Operanden nicht aus, wenn der linke Operand mit ungleich NULL auswertet wird.

```powershell
$x = $null
$x ??= 100
$x
```

```Output
100
```

Im folgenden Beispiel wird der rechte Operand nicht ausgewertet.

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ??= (Get-Date).ToShortDateString()
```

```Output
1/10/2020
```

#### <a name="null-conditional-operators--and-"></a>NULL-bedingte Operatoren `?.` und `?[]`

> [!NOTE]
> Diese Funktion wurde in PowerShell 7,1 von "experimentell" in "Mainstream" verlagert.

Ein NULL Bedingter Operator wendet einen Element Zugriffs-,- `?.` oder-Element Zugriff,- `?[]` Vorgang auf seinen Operanden nur an, wenn der Operand zu einem anderen Wert als NULL ausgewertet wird; andernfalls wird NULL zurückgegeben.

Da PowerShell erlaubt, dass `?` Teil des Variablennamens ist, ist für die Verwendung dieser Operatoren die formale Angabe des Variablennamens erforderlich. Daher ist es nötig, `{}` um die Variablennamen herum zu platzieren, wie z. B. `${a}` oder wenn `?` Teil des Variablennamens `${a?}` ist.

Im folgenden Beispiel wird der Wert von " **propName** " zurückgegeben.

```powershell
$a = @{ PropName = 100 }
${a}?.PropName
```

```Output
100
```

Im folgenden Beispiel wird NULL zurückgegeben, ohne dass versucht wird, auf den Elementnamen **propName** zuzugreifen.

```powershell
$a = $null
${a}?.PropName
```

Entsprechend wird der Wert des-Elements zurückgegeben.

```powershell
$a = 1..10
${a}?[0]
```

```Output
1
```

Wenn der Operand NULL ist, wird auf das Element nicht zugegriffen und NULL zurückgegeben.

```PowerShell
$a = $null
${a}?[0]
```

## <a name="see-also"></a>Weitere Informationen:

[about_Arithmetic_Operators](about_Arithmetic_Operators.md)

[about_Assignment_Operators](about_Assignment_Operators.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Logical_Operators](about_logical_operators.md)

[about_Operator_Precedence](about_operator_precedence.md)

[about_Type_Operators](about_Type_Operators.md)

[about_Pipeline_Chain_Operators](about_Pipeline_Chain_Operators.md)

[about_Split](about_Split.md)

[about_Join](about_Join.md)

[about_Redirection](about_Redirection.md)
