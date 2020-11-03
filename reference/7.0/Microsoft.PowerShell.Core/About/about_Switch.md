---
description: Erläutert, wie ein Schalter verwendet wird, um mehrere-Anweisungen zu verarbeiten `If` .
keywords: powershell,cmdlet
Locale: en-US
ms.date: 2/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_switch?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Switch
ms.openlocfilehash: 12a4b8412b0c490372ea73a90855e333b6bbfbf3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220535"
---
# <a name="about-switch"></a>Info zum Schalter

## <a name="short-description"></a>Kurze Beschreibung
Erläutert, wie ein Schalter verwendet wird, um mehrere-Anweisungen zu verarbeiten `If` .

## <a name="long-description"></a>Lange Beschreibung

Verwenden Sie eine-Anweisung, um eine Bedingung in einem Skript oder einer Funktion zu überprüfen `If` . `If`Mit der-Anweisung können viele Arten von Bedingungen überprüft werden, einschließlich des Werts der Variablen und der Eigenschaften von Objekten.

Verwenden Sie eine-Anweisung, um mehrere Bedingungen zu überprüfen `Switch` . Die- `Switch` Anweisung ist äquivalent zu einer Reihe von- `If` Anweisungen, aber Sie ist einfacher. Die `Switch` -Anweisung listet jede Bedingung und eine optionale Aktion auf. Wenn eine Bedingung abgerufen wird, wird die Aktion ausgeführt.

Die `Switch` -Anweisung kann die `$_` `$switch` automatischen Variablen und verwenden. Weitere Informationen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).

Eine Basis `Switch` Anweisung hat das folgende Format:

```powershell
Switch (<test-value>)
{
    <condition> {<action>}
    <condition> {<action>}
}
```

Beispielsweise vergleicht die folgende `Switch` Anweisung den Testwert 3 mit jeder der Bedingungen. Wenn der Testwert mit der Bedingung übereinstimmt, wird die Aktion ausgeführt.

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."}
    4 {"It is four."}
}
```

```Output
It is three.
```

In diesem einfachen Beispiel wird der Wert mit jeder Bedingung in der Liste verglichen, auch wenn eine Entsprechung für den Wert 3 vorliegt. Die folgende `Switch` Anweisung hat zwei Bedingungen für den Wert 3. Es wird veranschaulicht, dass standardmäßig alle Bedingungen getestet werden.

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."}
    4 {"It is four."}
    3 {"Three again."}
}
```

```Output
It is three.
Three again.
```

Verwenden Sie die-Anweisung, um den `Switch` zu unterbinden `Break` Die-Anweisung `Break` beendet die- `Switch` Anweisung.

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."; Break}
    4 {"It is four."}
    3 {"Three again."}
}
```

```Output
It is three.
```

Wenn der Testwert eine Auflistung ist, z. b. ein Array, wird jedes Element in der Auflistung in der Reihenfolge ausgewertet, in der es angezeigt wird. In den folgenden Beispielen wird 4 und dann 2 ausgewertet.

```powershell
switch (4, 2)
{
    1 {"It is one." }
    2 {"It is two." }
    3 {"It is three." }
    4 {"It is four." }
    3 {"Three again."}
}
```

```Output
It is four.
It is two.
```

Alle- `Break` Anweisungen gelten für die Auflistung, nicht für jeden Wert, wie im folgenden Beispiel gezeigt. Die- `Switch` Anweisung wird von der- `Break` Anweisung in der Bedingung von Wert 4 beendet.

```powershell
switch (4, 2)
{
    1 {"It is one."; Break}
    2 {"It is two." ; Break }
    3 {"It is three." ; Break }
    4 {"It is four." ; Break }
    3 {"Three again."}
}
```

```Output
It is four.
```

### <a name="syntax"></a>Syntax

Die Syntax der kompletten `Switch` Anweisung lautet wie folgt:

```
switch [-regex|-wildcard|-exact][-casesensitive] (<value>)
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

oder

```
switch [-regex|-wildcard|-exact][-casesensitive] -file filename
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

Wenn keine Parameter verwendet werden, `Switch` verhält sich wie bei der Verwendung des **exakten** Parameters. Die Groß-/Kleinschreibung wird für den Wert nicht beachtet. Wenn der Wert eine Auflistung ist, wird jedes Element in der Reihenfolge ausgewertet, in der es angezeigt wird.

Die `Switch` Anweisung muss mindestens eine Bedingungs Anweisung enthalten.

Die- `Default` Klausel wird ausgelöst, wenn der Wert keiner der Bedingungen entspricht. Dies entspricht einer- `Else` Klausel in einer- `If` Anweisung. `Default`In jeder Anweisung ist nur eine einzige Klausel zulässig `Switch` .

`Switch` verfügt über die folgenden Parameter:

- **Wildcard** : gibt an, dass die Bedingung eine Platzhalter Zeichenfolge ist. Wenn die Match-Klausel keine Zeichenfolge ist, wird der-Parameter ignoriert. Bei dem Vergleich wird Groß- und Kleinschreibung nicht unterschieden.
- **Exact** : gibt an, dass die Match-Klausel, wenn Sie eine Zeichenfolge ist, genau übereinstimmen muss. Wenn die Match-Klausel keine Zeichenfolge ist, wird dieser Parameter ignoriert. Bei dem Vergleich wird Groß- und Kleinschreibung nicht unterschieden.
- **CaseSensitive** : berücksichtigt die Groß-/Kleinschreibung. Wenn die Match-Klausel keine Zeichenfolge ist, wird dieser Parameter ignoriert.
- **File** : übernimmt Eingaben aus einer Datei anstelle einer Value-Anweisung. Wenn mehrere **Datei** Parameter enthalten sind, wird nur der letzte verwendet. Jede Zeile der Datei wird von der-Anweisung gelesen und ausgewertet `Switch` . Bei dem Vergleich wird Groß- und Kleinschreibung nicht unterschieden.
- **Regex** : führt einen regulären Ausdruck aus, der mit der Bedingung übereinstimmt. Wenn die Match-Klausel keine Zeichenfolge ist, wird dieser Parameter ignoriert.
  Bei dem Vergleich wird Groß- und Kleinschreibung nicht unterschieden. Die `$matches` Automatische Variable ist zur Verwendung innerhalb des entsprechenden Anweisungsblocks verfügbar.

> [!NOTE]
> Beim Angeben von in Konflikt stehenden Werten wie **Regex** und Platzhalter hat der letzte angegebene Parameter **Vorrang, und** alle in Konflikt stehenden Parameter werden ignoriert. Es sind auch mehrere Instanzen von Parametern zulässig. Allerdings ist nur der letzte verwendete Parameter gültig.

In diesem Beispiel wird ein Objekt, das keine Zeichen folgen-oder numerischen Daten ist, an das-Objekt übermittelt `Switch` . `Switch`Führt eine Zeichen folgen Umwandlung für das-Objekt aus und wertet das Ergebnis aus.

```powershell
$test = @{
    Test  = 'test'
    Test2 = 'test2'
}

$test.ToString()

switch -Exact ($test)
{
    'System.Collections.Hashtable'
    {
        'Hashtable string coercion'
    }
    'test'
    {
        'Hashtable value'
    }
}
```

```Output
System.Collections.Hashtable
Hashtable string coercion
```

In diesem Beispiel gibt es keine übereinstimmende Groß-/Kleinschreibung, sodass keine Ausgabe vorhanden ist.

```powershell
switch ("fourteen")
{
    1 {"It is one."; Break}
    2 {"It is two."; Break}
    3 {"It is three."; Break}
    4 {"It is four."; Break}
    "fo*" {"That's too many."}
}
```

Durch Hinzufügen der- `Default` Klausel können Sie eine Aktion ausführen, wenn keine anderen Bedingungen erfolgreich sind.

```powershell
switch ("fourteen")
{
    1 {"It is one."; Break}
    2 {"It is two."; Break}
    3 {"It is three."; Break}
    4 {"It is four."; Break}
    "fo*" {"That's too many."}
    Default {
        "No matches"
    }
}
```

```Output
No matches
```

Damit das Wort "14" einem Fall entspricht, müssen Sie den- `-Wildcard` Parameter oder den- `-Regex` Parameter verwenden.

```powershell
   PS> switch -Wildcard ("fourteen")
       {
           1 {"It is one."; Break}
           2 {"It is two."; Break}
           3 {"It is three."; Break}
           4 {"It is four."; Break}
           "fo*" {"That's too many."}
       }
 ```

```Output
That's too many.
```

Im folgenden Beispiel wird der- `-Regex` Parameter verwendet.

```powershell
$target = 'https://bing.com'
switch -Regex ($target)
{
    '^ftp\://.*$' { "$_ is an ftp address"; Break }
    '^\w+@\w+\.com|edu|org$' { "$_ is an email address"; Break }
    '^(http[s]?)\://.*$' { "$_ is a web address that uses $($matches[1])"; Break }
}
```

```Output
https://bing.com is a web address that uses https
```

Eine Switch-Anweisungs Bedingung kann wie folgt lauten:

- Ein Ausdruck, dessen Wert mit dem Eingabe Wert verglichen wird.
- Ein Skriptblock, der zurückgeben sollte, `$true` Wenn eine Bedingung erfüllt ist.

Die `$_` Automatische Variable enthält den Wert, der an die Switch-Anweisung übermittelt wurde, und ist für die Auswertung und Verwendung im Bereich der Bedingungs Anweisungen verfügbar.

Die Aktion für jede Bedingung ist unabhängig von den Aktionen in anderen Bedingungen.

Im folgenden Beispiel wird veranschaulicht, wie Skriptblöcke als `Switch` Anweisungs Bedingungen verwendet werden.

```powershell
switch ("Test")
{
    {$_ -is [String]} {
        "Found a string"
    }
    "Test" {
        "This $_ executes as well"
    }
}
```

```Output
Found a string
This Test executes as well
```

Wenn der Wert mehreren Bedingungen entspricht, wird die Aktion für jede Bedingung ausgeführt. Um dieses Verhalten zu ändern, verwenden Sie die `Break` `Continue` Schlüsselwörter oder.

Das `Break` -Schlüsselwort beendet die Verarbeitung und beendet die- `Switch` Anweisung.

Das- `Continue` Schlüsselwort beendet die Verarbeitung des aktuellen Werts, setzt aber die Verarbeitung aller nachfolgenden Werte fort.

Im folgenden Beispiel wird ein Array von Zahlen verarbeitet und angezeigt, wenn Sie ungerade oder gerade sind. Negative Zahlen werden mit dem- `Continue` Schlüsselwort übersprungen. Wenn eine nicht--Zahl gefunden wird, wird die Ausführung mit dem- `Break` Schlüsselwort beendet.

```powershell
switch (1,4,-1,3,"Hello",2,1)
{
    {$_ -lt 0} { Continue }
    {$_ -isnot [Int32]} { Break }
    {$_ % 2} {
        "$_ is Odd"
    }
    {-not ($_ % 2)} {
        "$_ is Even"
    }
}
```

```Output
1 is Odd
4 is Even
3 is Odd
```

## <a name="see-also"></a>Weitere Informationen:

[about_Break](about_Break.md)

[about_Continue](about_Continue.md)

[about_If](about_If.md)

[about_Script_Blocks](about_Script_Blocks.md)
