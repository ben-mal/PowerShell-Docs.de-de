---
description: Beschreibt ein Schlüsselwort, das einen Abbruch Fehler behandelt.
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_trap?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Trap
ms.openlocfilehash: 30b03235cbc2338de3786e37416d1c1ce1d660e3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602511"
---
# <a name="about-trap"></a>Informationen zu Trap

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt ein Schlüsselwort, das einen Abbruch Fehler behandelt.

## <a name="long-description"></a>Lange Beschreibung

Ein Beendigungs Fehler beendet die Ausführung einer-Anweisung. Wenn PowerShell einen abschließenden Fehler nicht in irgendeiner Weise behandelt, beendet PowerShell auch die Ausführung der Funktion oder des Skripts in der aktuellen Pipeline. In anderen Sprachen, wie z. b. c#, werden abschließende Fehler als Ausnahmen bezeichnet.

Das `trap` Schlüsselwort gibt eine Liste von Anweisungen an, die beim Auftreten eines abschließenden Fehlers ausgeführt werden sollen. `trap` -Anweisungen behandeln die abschließenden Fehler wie folgt:

- Zeigen Sie den Fehler nach der Verarbeitung des `trap` Anweisungsblocks an, und setzen Sie die Ausführung des Skripts oder der Funktion mit fort `trap` Dies ist das Standardverhalten.

- Zeigen Sie den Fehler an, und brechen Sie die Ausführung des Skripts oder der Funktion `trap` mit der `break` in der- `trap` Anweisung ab.

- Stillen Sie den Fehler, aber setzen Sie die Ausführung des Skripts oder der Funktion mit der `trap` `continue` in der- `trap` Anweisung fort.

Die Anweisungs Liste der `trap` kann mehrere Bedingungen oder Funktionsaufrufe enthalten. Mit `trap` können Protokolle, Testbedingungen oder sogar ein anderes Programm geschrieben werden.

### <a name="syntax"></a>Syntax

Die- `trap` Anweisung weist die folgende Syntax auf:

```powershell
trap [[<error type>]] {<statement list>}
```

Die- `trap` Anweisung enthält eine Liste von-Anweisungen, die ausgeführt werden sollen, wenn ein Abbruch Fehler auftritt. Eine- `trap` Anweisung besteht aus dem `trap` Schlüsselwort, optional gefolgt von einem Typausdruck, und dem Anweisungsblock, der die Liste der Anweisungen enthält, die ausgeführt werden sollen, wenn ein Fehler aufgetreten ist. Der Typausdruck verfeinert die Typen von Fehlern, die von abgefangen werden `trap` .

Skripts oder Befehle können mehrere- `trap` Anweisungen aufweisen. `trap` -Anweisungen können an beliebiger Stelle im Skript oder Befehl angezeigt werden.

### <a name="trapping-all-terminating-errors"></a>Alle abschließenden Fehler werden abfangen.

Wenn ein Abbruch Fehler auftritt, der in einem Skript oder Befehl nicht auf andere Weise behandelt wird, prüft PowerShell, `trap` ob eine Anweisung den Fehler behandelt. Wenn eine- `trap` Anweisung vorhanden ist, führt PowerShell die Ausführung des Skripts oder Befehls in der `trap` Anweisung fort.

Das folgende Beispiel ist eine sehr einfache `trap` Anweisung:

```powershell
trap {"Error found."}
```

Diese `trap` Anweisung fängt jeden Beendigungs Fehler ein.

Im folgenden Beispiel enthält die-Funktion eine Unsinn-Zeichenfolge, die einen Laufzeitfehler verursacht.

```powershell
function TrapTest {
    trap {"Error found."}
    nonsenseString
}

TrapTest
```

Durch das Ausführen dieser Funktion wird Folgendes zurückgegeben:

```Output
Error found.
nonsenseString:
Line |
   3 |      nonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

Das folgende Beispiel enthält eine- `trap` Anweisung, die den Fehler mit der `$_` automatischen Variablen anzeigt:

```powershell
function TrapTest {
    trap {"Error found: $_"}
    nonsenseString
}

TrapTest
```

Wenn Sie diese Version der Funktion ausführen, wird Folgendes zurückgegeben:

```Output
Error found: The term 'nonsenseString' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of the
name, or if a path was included, verify that the path is correct and try again.
nonsenseString:
Line |
   3 |      nonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

> [!IMPORTANT]
> `trap` -Anweisungen können an beliebiger Stelle innerhalb eines bestimmten Bereichs definiert werden, gelten jedoch immer für alle Anweisungen in diesem Bereich. Zur Laufzeit `trap` werden Anweisungen in einem-Block definiert, bevor andere Anweisungen ausgeführt werden. In JavaScript wird dies als " [Hosting](https://wikipedia.org/wiki/JavaScript_syntax#hoisting)" bezeichnet. Dies bedeutet, dass- `trap` Anweisungen für alle Anweisungen in diesem Block gelten, auch wenn die Ausführung nicht hinter dem Punkt liegt, an dem Sie definiert sind. Wenn Sie z. b `trap` . eine am Ende eines Skripts definieren und in der ersten Anweisung einen Fehler auslösen, wird dies weiterhin ausgelöst `trap` .

### <a name="trapping-specific-errors"></a>Abfangen von bestimmten Fehlern

Skripts oder Befehle können mehrere- `trap` Anweisungen aufweisen. Eine `trap` kann definiert werden, um bestimmte Fehler zu behandeln.

Das folgende Beispiel ist eine- `trap` Anweisung, die den spezifischen Fehler **commandnotfoundexception** abgefangen:

```powershell
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
```

Wenn eine Funktion oder ein Skript auf eine Zeichenfolge trifft, die nicht mit einem bekannten Befehl identisch ist, wird in dieser `trap` Anweisung die Zeichenfolge "Befehls Fehler gefangen" angezeigt.
Nach dem Ausführen der `trap` Anweisungs Liste schreibt PowerShell das Fehler Objekt in den Fehler Datenstrom und setzt das Skript dann fort.

PowerShell verwendet .NET-Ausnahme Typen. Im folgenden Beispiel wird der **System. Exception** -Fehlertyp angegeben:

```powershell
trap [System.Exception] {"An error trapped"}
```

Der **commandnotfoundexception** -Fehlertyp erbt vom **System. Exception** -Typ. Diese Anweisung fängt einen Fehler ab, der von einem unbekannten Befehl erstellt wird. Außerdem werden andere Fehlertypen abgefangen.

Sie können mehr als eine `trap` Anweisung in einem Skript erstellen. Jeder Fehlertyp kann nur von einer Anweisung eingefangen werden `trap` . Wenn ein Abbruch Fehler auftritt, sucht PowerShell nach dem `trap` mit der spezifischsten Übereinstimmung, beginnend mit dem aktuellen Ausführungs Bereich.

Das folgende Beispielskript enthält einen Fehler. Das Skript enthält eine allgemeine `trap` Anweisung, die alle abschließenden Fehler und eine bestimmte `trap` Anweisung, die den **commandnotfoundexception** -Typ angibt, abgefangen.

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException] {
  "Command error trapped"
}
nonsenseString
```

Das Ausführen dieses Skripts führt zu folgendem Ergebnis:

```Output
Command error trapped
nonsenseString:
Line |
   5 |  nonsenseString
     |  ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

Da PowerShell "nonsenabstring" nicht als Cmdlet oder ein anderes Element erkennt, wird ein **commandnotfoundexception** -Fehler zurückgegeben. Dieser abschließende Fehler wird von der jeweiligen `trap` Anweisung erfasst.

Das folgende Skript Beispiel enthält die gleichen `trap` Anweisungen mit einem anderen Fehler:

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
1/$null
```

Das Ausführen dieses Skripts führt zu folgendem Ergebnis:

```Output
Other terminating error trapped
RuntimeException:
Line |
   4 |  1/$null
     |  ~~~~~~~
     | Attempted to divide by zero.
```

Der Versuch, eine Division durch 0 (null) auszuführen, erstellt keinen **commandnotfoundexception** -Fehler. Stattdessen wird dieser Fehler von der anderen- `trap` Anweisung abgefangen, die alle abschließenden Fehler abgefangen.

### <a name="trapping-errors-and-scope"></a>Abfangen von Fehlern und Gültigkeitsbereich

Wenn im gleichen Bereich wie die-Anweisung ein Abbruch Fehler auftritt `trap` , führt PowerShell die Liste der Anweisungen aus, die von definiert werden `trap` . Die Ausführung wird bei der Anweisung nach dem Fehler fortgesetzt. Wenn sich die- `trap` Anweisung in einem anderen Bereich als der Fehler befindet, wird die Ausführung bei der nächsten Anweisung fortgesetzt, die sich im gleichen Bereich wie die- `trap` Anweisung befindet.

Wenn beispielsweise ein Fehler in einer Funktion auftritt und die- `trap` Anweisung in der-Funktion ist, wird das Skript bei der nächsten Anweisung fortgesetzt. Das folgende Skript enthält einen Fehler und eine- `trap` Anweisung:

```powershell
function function1 {
    trap { "An error: " }
    NonsenseString
    "function1 was completed"
}

function1
```

Das Ausführen dieses Skripts führt zu folgendem Ergebnis:

```Output
An error:
NonsenseString:
Line |
   3 |      NonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'NonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
function1 was completed
```

Die- `trap` Anweisung in der Funktion fängt den Fehler ab. Nach dem Anzeigen der Meldung wird die Ausführung der Funktion von PowerShell fortgesetzt. Beachten Sie, dass `Function1` abgeschlossen wurde.

Vergleichen Sie dies mit dem folgenden Beispiel, das denselben Fehler und dieselbe `trap` Anweisung aufweist. In diesem Beispiel tritt die- `trap` Anweisung außerhalb der-Funktion auf:

```powershell
function function2 {
    NonsenseString
    "function2 was completed"
}

trap { "An error: " }

function2
```

Das Ausführen der `Function2` Funktion führt zu folgendem Ergebnis:

```Output
An error:
NonsenseString:
Line |
   2 |      NonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'NonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

In diesem Beispiel wurde der Befehl "Funktion2 wurde abgeschlossen" nicht ausgeführt. In beiden Beispielen tritt der abschließende Fehler innerhalb der-Funktion auf. In diesem Beispiel befindet sich die- `trap` Anweisung jedoch außerhalb der-Funktion. PowerShell wechselt nicht wieder in die Funktion, nachdem die-Anweisung ausgeführt wurde `trap` .

> [!CAUTION]
> Wenn für die gleiche Fehlerbedingung mehrere Traps definiert sind, wird der erste, `trap` lexikalisch (höchste im Gültigkeitsbereich), verwendet.

Im folgenden Beispiel wird nur der `trap` mit "Whoops 1" ausgeführt.

```powershell
Remove-Item -ErrorAction Stop ThisFileDoesNotExist
trap { "whoops 1"; continue }
trap { "whoops 2"; continue }
```

> [!IMPORTANT]
> Eine Trap-Anweisung bezieht sich auf den Speicherort, an dem Sie kompiliert wird. Wenn Sie über eine- `trap` Anweisung innerhalb einer Funktion oder eines Punkt-/punktskripts verfügen, `trap` werden alle Anweisungen in entfernt, wenn die Funktion oder das Punkt-Source-Skript beendet wird.

### <a name="using-the-break-and-continue-keywords"></a>Verwenden der Schlüsselwörter Break und Continue

Sie können die `break` `continue` Schlüsselwörter und in einer- `trap` Anweisung verwenden, um zu bestimmen, ob ein Skript oder ein Befehl nach einem Beendigungs Fehler weiterhin ausgeführt wird.

Wenn Sie eine- `break` Anweisung in eine `trap` Anweisungs Liste einschließen, hält PowerShell die Funktion oder das Skript an. Die folgende Beispiel Funktion verwendet das- `break` Schlüsselwort in einer- `trap` Anweisung:

```powershell
function break_example {
    trap {
        "Error trapped"
        break
    }
    1/$null
    "Function completed."
}

break_example
```

```Output
Error trapped
ParentContainsErrorRecordException:
Line |
   6 |      1/$null
     |      ~~~~~~~
     | Attempted to divide by zero.
```

Da die- `trap` Anweisung das- `break` Schlüsselwort enthielt, wird die Funktion nicht weiter ausgeführt, und die Zeile "Funktion abgeschlossen" wird nicht ausgeführt.

Wenn Sie ein `continue` Schlüsselwort in eine- `trap` Anweisung einfügen, wird PowerShell nach der Anweisung, die den Fehler verursacht hat, genauso wie ohne oder fortgesetzt `break` `continue` . Mit dem- `continue` Schlüsselwort schreibt PowerShell jedoch keinen Fehler in den Fehler Datenstrom.

Die folgende Beispiel Funktion verwendet das- `continue` Schlüsselwort in einer- `trap` Anweisung:

```powershell
function continue_example {
    trap {
        "Error trapped"
        continue
    }
    1/$null
    "Function completed."
}

continue_example
```

```Output
Error trapped
Function completed.
```

Die Funktion wird fortgesetzt, nachdem der Fehler aufgetreten ist, und die Anweisung "Function abgeschlossene" wird ausgeführt. Es wird kein Fehler in den Fehler Datenstrom geschrieben.

## <a name="notes"></a>Notizen

`trap` -Anweisungen bieten eine einfache Möglichkeit, um umfassend sicherzustellen, dass alle abschließenden Fehler innerhalb eines Bereichs behandelt werden. Verwenden Sie für eine differenziertere Fehlerbehandlung `try` / `catch` Blöcke, bei denen Traps mithilfe von-Anweisungen definiert werden `catch` . Die- `catch` Anweisungen gelten nur für den Code in der zugeordneten- `try` Anweisung. Weitere Informationen finden Sie unter [about_Try_Catch_Finally](about_Try_Catch_Finally.md).

## <a name="see-also"></a>Weitere Informationen

[about_Break](about_Break.md)

[about_Continue](about_Continue.md)

[about_Scopes](about_Scopes.md)

[about_Throw](about_Throw.md)

[about_Try_Catch_Finally](about_Try_Catch_Finally.md)
