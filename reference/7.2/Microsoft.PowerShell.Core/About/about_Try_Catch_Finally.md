---
description: Beschreibt, wie die `Try` -, `Catch` -und-Blöcke verwendet werden, `Finally` um abschließende Fehler zu behandeln.
Locale: en-US
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_try_catch_finally?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Try_Catch_Finally
ms.openlocfilehash: c93fa69e3badd7777950a850dfe81b79f9197f68
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595538"
---
# <a name="about-try-catch-finally"></a>Informationen zu try catch schließlich

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt, wie die `Try` -, `Catch` -und-Blöcke verwendet werden, `Finally` um abschließende Fehler zu behandeln.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Verwenden `Try` `Catch` `Finally` Sie die Blöcke, und, um auf abschließende Fehler in Skripts zu reagieren oder diese zu behandeln. Die- `Trap` Anweisung kann auch verwendet werden, um abschließende Fehler in Skripts zu behandeln. Weitere Informationen finden Sie unter [about_Trap](about_Trap.md).

Ein Beendigungs Fehler beendet die Ausführung einer-Anweisung. Wenn PowerShell einen Fehler mit Abbruch nicht in irgendeiner Weise behandelt, beendet PowerShell auch das Ausführen der Funktion oder des Skripts mithilfe der aktuellen Pipeline. In anderen Sprachen, wie z \# . b. C, werden abschließende Fehler als Ausnahmen bezeichnet.

Verwenden Sie den- `Try` Block, um einen Abschnitt eines Skripts zu definieren, in dem PowerShell auf Fehler überwachen soll. Wenn ein Fehler im- `Try` Block auftritt, wird der Fehler zuerst in der `$Error` automatischen Variablen gespeichert. PowerShell sucht dann nach einem- `Catch` Block, um den Fehler zu behandeln. Wenn die `Try` Anweisung über keinen übereinstimmenden `Catch` Block verfügt, sucht PowerShell weiterhin nach einem entsprechenden `Catch` Block oder einer entsprechenden `Trap` Anweisung in den übergeordneten Bereichen. Wenn ein- `Catch` Block abgeschlossen ist, oder wenn kein entsprechender `Catch` Block oder keine entsprechende `Trap` Anweisung gefunden wird, wird der- `Finally` Block ausgeführt. Wenn der Fehler nicht behandelt werden kann, wird der Fehler in den Fehler Datenstrom geschrieben.

Ein- `Catch` Block kann Befehle zum Nachverfolgen des Fehlers oder zum Wiederherstellen des erwarteten Ablaufs des Skripts enthalten. Ein- `Catch` Block kann angeben, welche Fehlertypen abgefangen werden. Eine- `Try` Anweisung kann mehrere `Catch` Blöcke für verschiedene Arten von Fehlern enthalten.

Ein- `Finally` Block kann verwendet werden, um alle Ressourcen freizugeben, die von Ihrem Skript nicht mehr benötigt werden.

`Try`, und `Catch` `Finally` ähneln den `Try` Schlüsselwörtern, und, die `Catch` `Finally` in der Programmiersprache C verwendet werden \# .

### <a name="syntax"></a>SYNTAX

Eine- `Try` Anweisung enthält einen `Try` Block, 0 (null) oder mehr `Catch` Blöcke und keinen oder einen `Finally` Block. Eine- `Try` Anweisung muss über mindestens einen `Catch` Block oder einen `Finally` Block verfügen.

Das folgende Beispiel zeigt die `Try` Block Syntax:

```powershell
try {<statement list>}
```

`Try`Auf das Schlüsselwort folgt eine Anweisungs Liste in geschweiften Klammern. Wenn ein Abbruch Fehler auftritt, während die Anweisungen in der Anweisungs Liste ausgeführt werden, übergibt das Skript das Fehler Objekt aus dem- `Try` Block an einen entsprechenden- `Catch` Block.

Das folgende Beispiel zeigt die `Catch` Block Syntax:

```powershell
catch [[<error type>][',' <error type>]*] {<statement list>}
```

Fehlertypen werden in eckigen Klammern angezeigt. Die äußersten Klammern geben an, dass das Element optional ist.

Auf das `Catch` Schlüsselwort folgt eine optionale Liste der Fehlertyp Spezifikationen und eine Anweisungs Liste. Wenn im-Block ein Abbruch Fehler auftritt `Try` , sucht PowerShell nach einem entsprechenden- `Catch` Block. Wenn ein solcher gefunden wird, werden die Anweisungen im- `Catch` Block ausgeführt.

Der- `Catch` Block kann einen oder mehrere Fehlertypen angeben. Ein Fehlertyp ist eine Microsoft .NET Framework-Ausnahme oder eine Ausnahme, die von einer .NET Framework Ausnahme abgeleitet ist. Ein- `Catch` Block verarbeitet Fehler der angegebenen .NET Framework Ausnahme Klasse oder einer beliebigen Klasse, die von der angegebenen Klasse abgeleitet ist.

Wenn ein- `Catch` Block einen Fehlertyp angibt, `Catch` verarbeitet dieser Block diese Art von Fehler. Wenn ein- `Catch` Block keinen Fehlertyp angibt, behandelt dieser `Catch` Block jeden im-Block gefundenen Fehler `Try` . Eine- `Try` Anweisung kann mehrere `Catch` Blöcke für die unterschiedlichen angegebenen Fehlertypen enthalten.

Das folgende Beispiel zeigt die `Finally` Block Syntax:

```powershell
finally {<statement list>}
```

`Finally`Auf das Schlüsselwort folgt eine Anweisungs Liste, die jedes Mal ausgeführt wird, wenn das Skript ausgeführt wird, auch wenn die `Try` Anweisung fehlerfrei ausgeführt wurde oder ein Fehler in einer Anweisung abgefangen wurde `Catch` .

Beachten Sie, dass durch Drücken von <kbd>STRG</kbd> + <kbd>C</kbd> die Pipeline beendet wird. Objekte, die an die Pipeline gesendet werden, werden nicht als Ausgabe angezeigt. Wenn Sie also eine anzuzeigende Anweisung einschließen, z. b. "der letzte Block wurde ausgeführt", wird Sie nicht angezeigt, nachdem Sie <kbd>STRG</kbd> + <kbd>C</kbd>gedrückt haben, auch wenn der Block ausgeführt wurde `Finally` .

### <a name="catching-errors"></a>Abfangen von Fehlern

Das folgende Beispielskript zeigt einen `Try` Block mit einem- `Catch` Block:

```powershell
try { NonsenseString }
catch { "An error occurred." }
```

Das `Catch` Schlüsselwort muss direkt auf den `Try` Block oder einen anderen `Catch` Block folgen.

PowerShell erkennt nicht "nonsenabstring" als Cmdlet oder ein anderes Element.
Durch das Ausführen dieses Skripts wird folgendes Ergebnis zurückgegeben:

```powershell
An error occurred.
```

Wenn im Skript "nonsenenstring" auftritt, wird ein Abbruch Fehler verursacht. Der- `Catch` Block verarbeitet den Fehler, indem die-Anweisungs Liste im-Block ausgeführt wird.

### <a name="using-multiple-catch-statements"></a>Verwenden von mehreren catch-Anweisungen

Eine- `Try` Anweisung kann eine beliebige Anzahl von `Catch` Blöcken aufweisen. Das folgende Skript enthält z. b. einen Block, der `Try` herunterlädt `MyDoc.doc` und zwei `Catch` Blöcke enthält:

```powershell
try {
   $wc = new-object System.Net.WebClient
   $wc.DownloadFile("http://www.contoso.com/MyDoc.doc","c:\temp\MyDoc.doc")
}
catch [System.Net.WebException],[System.IO.IOException] {
    "Unable to download MyDoc.doc from http://www.contoso.com."
}
catch {
    "An error occurred that could not be resolved."
}

```

Der erste `Catch` Block verarbeitet Fehler des **System .net. WebException** -und des **System. IO. IOException** -Typs. Der zweite- `Catch` Block gibt keinen Fehlertyp an. Der zweite- `Catch` Block behandelt alle anderen auftretenden Abbruch Fehler.

PowerShell gleicht Fehlertypen nach Vererbung ab. Ein- `Catch` Block verarbeitet Fehler der angegebenen .NET Framework Ausnahme Klasse oder einer beliebigen Klasse, die von der angegebenen Klasse abgeleitet ist. Das folgende Beispiel enthält einen- `Catch` Block, der den Fehler "Befehl wurde nicht gefunden" abfängt:

```powershell
catch [System.Management.Automation.CommandNotFoundException]
{"Inherited Exception" }
```

Der angegebene Fehlertyp **commandnotfoundexception** erbt vom **System.Systemexception** -Typ. Im folgenden Beispiel wird auch der Fehler "Befehl nicht gefunden" abgefangen:

```powershell
catch [System.SystemException] {"Base Exception" }
```

Dieser `Catch` Block behandelt den Fehler "Befehl nicht gefunden" und andere Fehler, die vom Typ **"SystemException** " erben.

Wenn Sie eine Fehler Klasse und eine der abgeleiteten Klassen angeben, platzieren Sie den- `Catch` Block für die abgeleitete Klasse vor dem- `Catch` Block für die allgemeine-Klasse.

### <a name="using-traps-in-a-try-catch"></a>Verwenden von Traps in einem try-catch

Wenn ein Beendigungs Fehler in einem- `Try` Block auftritt `Trap` , der ein-Element im-Block definiert ist, `Try` `Catch` übernimmt die-Anweisung die-Anweisung, selbst wenn ein entsprechender-Block vorhanden ist `Trap` .

Wenn ein `Trap` in einem höheren Block als vorhanden `Try` ist und es keinen übereinstimmenden `Catch` Block innerhalb des aktuellen Gültigkeits Bereichs gibt, `Trap` übernimmt auch dann die Steuerung, wenn ein übergeordneter Bereich über einen übereinstimmenden `Catch` Block verfügt.

### <a name="accessing-exception-information"></a>Zugreifen auf Ausnahme Informationen

Innerhalb eines- `Catch` Blocks kann auf den aktuellen Fehler mithilfe von zugegriffen werden `$_` . Dies wird auch als bezeichnet `$PSItem` . Das Objekt ist vom Typ **ErrorRecord**.

```powershell
try { NonsenseString }
catch {
  Write-Host "An error occurred:"
  Write-Host $_
}
```

Durch das Ausführen dieses Skripts wird folgendes Ergebnis zurückgegeben:

```Output
An Error occurred:
The term 'NonsenseString' is not recognized as the name of a cmdlet, function,
script file, or operable program. Check the spelling of the name, or if a path
was included, verify that the path is correct and try again.
```

Es gibt weitere Eigenschaften, auf die zugegriffen werden kann, z. **b. scriptstacktrace**, **Exception** und **errorDetails**.  Angenommen, das Skript wird wie folgt geändert:

```powershell
try { NonsenseString }
catch {
  Write-Host "An error occurred:"
  Write-Host $_.ScriptStackTrace
}
```

Das Ergebnis sieht in etwa wie folgt aus:

```
An Error occurred:
at <ScriptBlock>, <No file>: line 2
```

### <a name="freeing-resources-by-using-finally"></a>Freigeben von Ressourcen mithilfe von

Um von einem Skript verwendete Ressourcen freizugeben, fügen Sie `Finally` nach den `Try` -und-Blöcken einen-Block hinzu `Catch` . Die `Finally` Block-Anweisungen werden unabhängig davon ausgeführt, ob der-Block einen Beendigungs Fehler feststellt `Try` . PowerShell führt den `Finally` Block aus, bevor das Skript beendet wird, oder bevor der aktuelle Block den Gültigkeitsbereich verlässt.

Ein- `Finally` Block wird auch dann ausgeführt, wenn Sie <kbd>STRG</kbd> + <kbd>C</kbd> zum Abbrechen des Skripts verwenden. Ein- `Finally` Block wird auch ausgeführt, wenn ein Exit-Schlüsselwort das Skript innerhalb eines- `Catch` Blocks beendet.

### <a name="see-also"></a>SIEHE AUCH

[about_Break](about_Break.md)

[about_Continue](about_Continue.md)

[about_Scopes](about_Scopes.md)

[about_Throw](about_Throw.md)

[about_Trap](about_Trap.md)

