---
description: Beschreibt die Schlüsselwörter in der PowerShell-Skriptsprache.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_language_keywords?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Language_Keywords
ms.openlocfilehash: 09b0414a962cce3f9f5c90b28aa871f4c09f76e2
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222223"
---
# <a name="about-language-keywords"></a>Informationen zu Schlüsselwörtern

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt die Schlüsselwörter in der PowerShell-Skriptsprache.

## <a name="long-description"></a>LANGE BESCHREIBUNG

PowerShell verfügt über die folgenden sprach Schlüsselwörter. Weitere Informationen finden Sie im Thema Info zum Schlüsselwort und den Informationen, die der Tabelle folgen.

Schlüsselwort     | Verweis
---         | ---
Starten       | [about_Functions](about_Functions.md) [about_Functions_Advanced](about_Functions_Advanced.md)
Problemfindung       | [about_Break](about_Break.md) [about_Trap](about_Trap.md)
Catch       | [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
Klasse       | [about_Classes](about_Classes.md)
Weiter    | [about_Continue](about_Continue.md) [about_Trap](about_Trap.md)
Daten        | [about_Data_Sections](about_Data_Sections.md)
Definieren      | Für die zukünftige Verwendung reserviert
Empfohlen          | [about_Do](about_Do.md) [about_While](about_While.md)
Dynamicparam| [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)
Else        | [about_If](about_If.md)
Elseif      | [about_If](about_If.md)
Ende         | [about_Functions](about_Functions.md) [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)
Enumeration        | [about_Enum](about_Enum.md)
Beenden        | [Wird in diesem Thema beschrieben.](#exit)
Filter      | [about_Functions](about_Functions.md)
Finally     | [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
Für         | [about_For](about_For.md)
ForEach     | [about_ForEach](about_ForEach.md)
From        | Für die zukünftige Verwendung reserviert
Funktion    | [about_Functions](about_Functions.md) [about_Functions_Advanced](about_Functions_Advanced.md)
Ausgeblendet      | [about_Hidden](about_Hidden.md)
If          | [about_If](about_If.md)
In          | [about_ForEach](about_ForEach.md)
Parameter       | [about_Functions](about_Functions.md)
Prozess     | [about_Functions](about_Functions.md) [about_Functions_Advanced](about_Functions_Advanced.md)
Rückgabewert      | [about_Return](about_Return.md)
Statisch      | [about_Classes](about_Classes.md)
Schalter      | [about_Switch](about_Switch.md)
Throw       | [about_Throw](about_Throw.md) [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)
Trap        | [about_Trap](about_Trap.md), [about_Break](about_Break.md) [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
Testen         | [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
Until       | [about_Do](about_Do.md)
Verwenden       | [about_Using](about_Using.md) [about_Classes](about_Classes.md)
Var         | Für die zukünftige Verwendung reserviert
While       | [about_While](about_While.md) [about_Do](about_Do.md)

Sprachschlüsselwörter

### <a name="begin"></a>Starten

Gibt einen Teil des Texts einer Funktion zusammen mit den `DynamicParam` `Process` Schlüsselwörtern, und an `End` . Die `Begin` Anweisungs Liste wird einmal ausgeführt, bevor Objekte von der Pipeline empfangen werden.

Syntax:

```Syntax
function <name> {
    DynamicParam {<statement list>}
    begin {<statement list>}
    process {<statement list>}
    end {<statement list>}
}
```

### <a name="break"></a>Problemfindung

Bewirkt, dass ein Skript eine Schleife verlässt.

Syntax:

```Syntax
while (<condition>) {
   <statements>
   ...

   break
   ...

   <statements>
}
```

### <a name="catch"></a>Catch

Gibt eine Anweisungs Liste an, die ausgeführt wird, wenn ein Fehler in der zugehörigen try-Anweisungs Liste auftritt. Ein Fehlertyp erfordert eckige Klammern. Das zweite Klammer paar gibt an, dass der Fehlertyp optional ist.

Syntax:

```Syntax
try {<statement list>}
catch [[<error type>]] {<statement list>}
```

### <a name="class"></a>Klasse

Gibt eine neue Klasse in PowerShell an.

Syntax:

```Syntax
class <class-name> {
    [[hidden] [static] <property-definition> ...]
    [<class-name>([argument-list>]) {<constructor-statement-list>} ...]
    [[hidden] [static] <method-definition> ...]
}
```

### <a name="continue"></a>Weiter

Bewirkt, dass ein Skript die Ausführung einer Schleife beendet und zur Bedingung zurück wechselt. Wenn die Bedingung erfüllt ist, beginnt das Skript erneut mit der Schleife.

Syntax:

```Syntax
while (<condition>) {
   <statements>
   ...

   continue
   ...

   <statements>
}
```

### <a name="data"></a>Daten

Definiert in einem Skript einen Abschnitt, in dem Daten von der Skript Logik isoliert werden. Kann auch `If` -Anweisungen und einige eingeschränkte Befehle enthalten.

Syntax:

```Syntax
data <variable> [-supportedCommand <cmdlet-name>] {<permitted content>}
```

### <a name="do"></a>Empfohlen

Wird mit dem `While` - `Until` Schlüsselwort oder als Schleifen Konstrukt verwendet. PowerShell führt die Anweisungs Liste mindestens einmal aus, im Gegensatz zu einer Schleife, die verwendet `While` .

Syntax für `While`:

```Syntax
do {<statement list>} while (<condition>)
```

Syntax für `Until`:

```Syntax
do {<statement list>} until (<condition>)
```

### <a name="dynamicparam"></a>Dynamicparam

Gibt einen Teil des Texts einer Funktion zusammen mit den `Begin` `Process` Schlüsselwörtern, und an `End` . Dynamische Parameter werden zur Laufzeit hinzugefügt.

Syntax:

```Syntax
function <name> {
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

### <a name="else"></a>Else

Wird mit dem- `If` Schlüsselwort verwendet, um die Standard Anweisungs Liste anzugeben.

Syntax:

```Syntax
if (<condition>) {<statement list>}
else {<statement list>}
```

### <a name="elseif"></a>Elseif

Wird mit den `If` `Else` Schlüsselwörtern und verwendet, um weitere Bedingungen anzugeben. Das `Else` Schlüsselwort ist optional.

Syntax:

```Syntax
if (<condition>) {<statement list>}
elseif (<condition>) {<statement list>}
else {<statement list>}
```

### <a name="end"></a>Ende

Gibt einen Teil des Texts einer Funktion zusammen mit den `DynamicParam` `Begin` Schlüsselwörtern, und an `End` . Die `End` Anweisungs Liste wird einmal ausgeführt, nachdem alle Objekte von der Pipeline empfangen wurden.

Syntax:

```Syntax
function <name> {
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

### <a name="enum"></a>Enumeration

`enum` wird verwendet, um eine Enumeration zu deklarieren. ein eindeutiger Typ, der aus einem Satz benannter Bezeichnungen besteht, die als Enumeratorliste bezeichnet werden.

Syntax:

```Syntax
enum <enum-name> {
    <label> [= <int-value>]
    ...
}
```

### <a name="exit"></a>Beenden

Bewirkt, dass PowerShell ein Skript oder eine PowerShell-Instanz beendet.

Syntax:

```Syntax
exit
exit <exitcode>
```

Wenn Sie `pwsh` mit dem **File** -Parameter verwenden, `.ps1` sollte die Datei (Skript) selbst Anweisungen zum Behandeln von Fehlern oder Ausnahmen enthalten, die auftreten, während das Skript ausgeführt wird. Sie sollten die `exit` -Anweisung nur verwenden, um den Status des Skripts nach der Ausführung anzugeben.

Unter Windows ist eine beliebige Zahl zwischen `[int]::MinValue` und `[int]::MaxValue` zulässig.

Unter Unix sind nur positive Zahlen zwischen `[byte]::MinValue` und `[byte]::MaxValue` zulässig. Eine negative Zahl im Bereich von `-1` bis `-255` wird durch Hinzufügen von 256 automatisch in eine positive Zahl übersetzt. Beispielsweise `-2` wird in umgewandelt `254` .

In PowerShell legt die- `exit` Anweisung den Wert der- `$LASTEXITCODE` Variablen fest. In der Windows-Befehlsshell (cmd.exe) legt die Exit-Anweisung den Wert der `%ERRORLEVEL%` Umgebungsvariablen fest.

Jedes Argument, das nicht numerisch oder außerhalb des plattformspezifischen Bereichs ist, wird in den Wert von übersetzt `0` .

Im folgenden Beispiel legt der Benutzer den Fehler Pegel Variablen Wert auf 4 fest, indem er `exit 4` der Skriptdatei hinzugefügt wird `test.ps1` .

```cmd
C:\scripts\test>type test.ps1
1
2
3
exit 4

C:\scripts\test>pwsh -file ./test.ps1
1
2
3

C:\scripts\test>echo %ERRORLEVEL%
4
```

Wenn Sie Ausführen `pwsh.exe -File <path to a script>` und die Skriptdatei mit einem Befehl beendet wird `exit` , wird der Exitcode auf das numerische Argument festgelegt, das mit dem Befehl verwendet wird `exit` . Wenn das Skript keine- `exit` Anweisung aufweist, ist der Exitcode immer, `0` Wenn das Skript ohne Fehler abgeschlossen wird oder `1` Wenn das Skript mit einer nicht behandelten Ausnahme beendet wird.

### <a name="filter"></a>Filter

Gibt eine Funktion an, in der die Anweisungs Liste einmal für jedes Eingabe Objekt ausgeführt wird. Sie hat denselben Effekt wie eine Funktion, die nur einen Prozess Block enthält.

Syntax:

```Syntax
filter <name> {<statement list>}
```

### <a name="finally"></a>Finally

Definiert eine Anweisungs Liste, die nach-Anweisungen ausgeführt wird, die try und Catch zugeordnet sind. Eine `Finally` Anweisungs Liste wird auch dann ausgeführt, wenn Sie drücken `CTRL+C` , um ein Skript zu verlassen, oder wenn Sie das Exit-Schlüsselwort im Skript verwenden.

Syntax:

```Syntax
try {<statement list>}
catch [<error type>] {<statement list>}
finally {<statement list>}
```

### <a name="for"></a>Für

Definiert eine Schleife mit einer Bedingung.

Syntax:

```Syntax
for (<initialize>; <condition>; <iterate>) { <statement list> }
```

### <a name="foreach"></a>ForEach

Definiert eine Schleife mit jedem Member einer Auflistung.

Syntax:

```Syntax
ForEach (<item> in <collection>) { <statement list> }
```

### <a name="from"></a>From

Für zukünftige Verwendung reserviert.

### <a name="function"></a>Funktion

Erstellt eine benannte Anweisungs Liste mit wiederverwendbarem Code. Sie können den Bereich benennen, zu dem eine Funktion gehört. Und Sie können einen oder mehrere benannte Parameter mit dem- `Param` Schlüsselwort angeben. In der Funktions Anweisungs Liste können Sie `DynamicParam` -, `Begin` -, `Process` -und- `End` Anweisungs Listen einschließen.

Syntax:

```Syntax
function [<scope:>]<name> {
   param ([type]<$pname1> [, [type]<$pname2>])
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

Sie haben auch die Möglichkeit, einen oder mehrere Parameter außerhalb der Anweisungs Liste nach dem Funktionsnamen zu definieren.

Syntax:

```Syntax
function [<scope:>]<name> [([type]<$pname1>, [[type]<$pname2>])] {
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

### <a name="if"></a>If

Definiert eine bedingte.

Syntax:

```Syntax
if (<condition>) {<statement list>}
```

### <a name="hidden"></a>Ausgeblendet

Blendet Klassenmember aus den Standard Ergebnissen des `Get-Member` Cmdlets und aus den Ergebnissen der IntelliSense-und Registerkarten Vervollständigung aus.

Syntax:

```Syntax
Hidden [data type] $member_name
```

### <a name="in"></a>In

Wird in einer- `ForEach` Anweisung verwendet, um eine Schleife zu erstellen, die jedes Element einer Auflistung verwendet.

Syntax:

```Syntax
ForEach (<item> in <collection>){<statement list>}
```

### <a name="inlinescript"></a>InlineScript

Führt Workflow Befehle in einer freigegebenen PowerShell-Sitzung aus. Dieses Schlüsselwort ist nur in einem PowerShell-Workflow gültig.

Syntax:

```Syntax
workflow <verb>-<noun>
{
   InlineScript
   {
      <Command/Expression>
      ...

   }
}
```

Das- `InlineScript` Schlüsselwort gibt eine- `InlineScript` Aktivität an, die Befehle in einer freigegebenen Standard Sitzung (Non-Workflow) ausführt. Sie können das `InlineScript` Schlüsselwort verwenden, um Befehle auszuführen, die in einem Workflow nicht anderweitig gültig sind, und um Befehle auszuführen, die Daten gemeinsam nutzen. Standardmäßig werden die Befehle in einem InlineScript-Skriptblock in einem separaten Prozess ausgeführt.

Weitere Informationen finden Sie unter [Ausführen von PowerShell-Befehlen in einem Workflow](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574197(v=ws.11)).

### <a name="param"></a>Parameter

Definiert die Parameter in einer Funktion.

Syntax:

```Syntax
function [<scope:>]<name> {
   param ([type]<$pname1>[, [[type]<$pname2>]])
   <statement list>
}
```

### <a name="process"></a>Prozess

Gibt einen Teil des Texts einer Funktion zusammen mit den `DynamicParam` `Begin` Schlüsselwörtern, und an `End` . Wenn eine `Process` Anweisungs Liste Eingaben von der Pipeline empfängt, wird die `Process` Anweisungs Liste einmal für jedes Element aus der Pipeline ausgeführt. Wenn die Pipeline keine Objekte bereitstellt, wird die `Process` Anweisungs Liste nicht ausgeführt. Wenn der Befehl der erste Befehl in der Pipeline ist, wird die `Process` Anweisungs Liste einmal ausgeführt.

Syntax:

```Syntax
function <name> {
   DynamicParam {<statement list>}
   begin {<statement list>}
   process {<statement list>}
   end {<statement list>}
}
```

### <a name="return"></a>Rückgabewert

Bewirkt, dass PowerShell den aktuellen Gültigkeitsbereich verlässt, z. b. ein Skript oder eine Funktion, und schreibt den optionalen Ausdruck in die Ausgabe.

Syntax:

```Syntax
return [<expression>]
```

### <a name="static"></a>Statisch

Gibt an, dass die definierte Eigenschaft oder Methode allen Instanzen der Klasse, in der definiert ist, gemeinsam ist.

Informationen `Class` zu Verwendungs Beispielen finden Sie unter.

### <a name="switch"></a>Schalter

Verwenden Sie eine-Anweisung, um mehrere Bedingungen zu überprüfen `Switch` . Die- `Switch` Anweisung ist äquivalent zu einer Reihe von- `If` Anweisungen, aber Sie ist einfacher.

Die `Switch` -Anweisung listet jede Bedingung und eine optionale Aktion auf. Wenn eine Bedingung abgerufen wird, wird die Aktion ausgeführt.

Syntax 1:

```Syntax
switch [-regex|-wildcard|-exact][-casesensitive] ( <value> )
{
   <string>|<number>|<variable>|{ <expression> } {<statement list>}
   <string>|<number>|<variable>|{ <expression> } {<statement list>}
   ...

   default {<statement list>}
}
```

Syntax 2:

```Syntax
switch [-regex|-wildcard|-exact][-casesensitive] -file <filename>
{
   <string>|<number>|<variable>|{ <expression> } {<statement list>}
   <string>|<number>|<variable>|{ <expression> } {<statement list>}
   ...

   default {<statement list>}
}
```

### <a name="throw"></a>Throw

Löst ein-Objekt als Fehler aus.

Syntax:

```Syntax
throw [<object>]
```

### <a name="trap"></a>Trap

Definiert eine Anweisungs Liste, die ausgeführt werden soll, wenn ein Fehler auftritt. Ein Fehlertyp erfordert eckige Klammern. Das zweite Klammer paar gibt an, dass der Fehlertyp optional ist.

Syntax:

```Syntax
trap [[<error type>]] {<statement list>}
```

### <a name="try"></a>Testen

Definiert eine Anweisungs Liste, die beim Ausführen der-Anweisungen auf Fehler geprüft werden soll. Wenn ein Fehler auftritt, wird PowerShell weiterhin in einer- `Catch` oder- `Finally` Anweisung ausgeführt. Ein Fehlertyp erfordert eckige Klammern. Das zweite Klammer paar gibt an, dass der Fehlertyp optional ist.

Syntax:

```Syntax
try {<statement list>}
catch [[<error type>]] {<statement list>}
finally {<statement list>}
```

### <a name="until"></a>Until

Wird in einer- `Do` Anweisung als Schleifen Konstrukt verwendet, bei dem die Anweisungs Liste mindestens einmal ausgeführt wird.

Syntax:

```Syntax
do {<statement list>} until (<condition>)
```

### <a name="using"></a>Verwenden

Ermöglicht, anzugeben, welche Namespaces in der Sitzung verwendet werden. Klassen und Member erfordern weniger Typisierung, um Sie zu erwähnen. Sie können auch Klassen aus Modulen einschließen.

Syntax #1:

```Syntax
using namespace <.Net-framework-namespace>
```

Syntax #2:

```Syntax
using module <module-name>
```

### <a name="while"></a>While

Die- `while` Anweisung ist ein Schleifen Konstrukt, bei dem die Bedingung getestet wird, bevor die Anweisungen ausgeführt werden. Wenn die Bedingung false ist, werden die Anweisungen nicht ausgeführt.

Syntax der Anweisung:

```Syntax
while (<condition>) {
   <statements>
 }
```

Wenn Sie in einer-Anweisung verwendet wird `Do` , `while` ist Teil eines Schleifen Konstrukts, in dem die Anweisungs Liste mindestens einmal ausgeführt wird.

Syntax der Do-Schleife:

```Syntax
do {<statement list>} while (<condition>)
```

## <a name="see-also"></a>SIEHE AUCH

- [about_Special_Characters](about_Special_Characters.md)
- [about_Wildcards](about_Wildcards.md)
