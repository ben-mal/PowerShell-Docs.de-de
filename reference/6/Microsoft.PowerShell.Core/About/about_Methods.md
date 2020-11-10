---
description: Beschreibt die Verwendung von Methoden zum Ausführen von Aktionen für Objekte in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_methods?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Methods
ms.openlocfilehash: 1acbe79deefbc21c4ce42bfc651eeb04ac189879
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387611"
---
# <a name="about-methods"></a>Informationen zu Methoden

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt die Verwendung von Methoden zum Ausführen von Aktionen für Objekte in PowerShell.

## <a name="long-description"></a>Lange Beschreibung

PowerShell verwendet Objekte zur Darstellung der Elemente in Daten speichern oder den Status des Computers. FileInfo-Objekte stellen z. b. die Dateien in Dateisystem Laufwerken dar, und ProcessInfo-Objekte stellen die Prozesse auf dem Computer dar.

-Objekte verfügen über Eigenschaften, die Daten über das Objekt speichern, und Methoden, mit denen Sie das Objekt ändern können.

Eine "Methode" ist ein Satz von Anweisungen, die eine Aktion angeben, die Sie für das Objekt ausführen können. Beispielsweise enthält das- `FileInfo` Objekt die- `CopyTo` Methode, die die Datei kopiert, die das- `FileInfo` Objekt darstellt.

Verwenden Sie das-Cmdlet, um die Methoden eines beliebigen Objekts zu erhalten `Get-Member` . Verwenden Sie die zugehörige Eigenschaft " **Membership Type** " mit dem Wert "Method". Der folgende Befehl ruft die Methoden von Process-Objekten ab.

```powershell
Get-Process | Get-Member -MemberType Method
```

```Output
TypeName: System.Diagnostics.Process

Name                      MemberType Definition
----                      ---------- ----------
BeginErrorReadLine        Method     System.Void BeginErrorReadLine()
BeginOutputReadLine       Method     System.Void BeginOutputReadLine()
...
Kill                      Method     System.Void Kill()
Refresh                   Method     System.Void Refresh()
Start                     Method     bool Start()
ToString                  Method     string ToString()
WaitForExit               Method     bool WaitForExit(int milliseconds), ...
WaitForInputIdle          Method     bool WaitForInputIdle(int millisecon...
```

Geben Sie einen Punkt (.), den Methodennamen und eine Reihe von Klammern "()" ein, um eine Methode eines Objekts auszuführen oder zu "aufrufen". Wenn die Methode über Argumente verfügt, platzieren Sie die Argument Werte in den Klammern. Die Klammern sind für jeden Methoden aufrufbedarf erforderlich, auch wenn keine Argumente vorhanden sind. Wenn die Methode mehrere Argumente annimmt, sollten Sie durch Kommas getrennt werden.

Beispielsweise ruft der folgende Befehl die Kill-Methode von Prozessen auf, um den Notepad-Prozess auf dem Computer zu beenden.

```powershell
$notepad = Get-Process notepad
$notepad.Kill()
```

Dieses Beispiel kann durch Kombinieren der obigen-Anweisungen verkürzt werden.

```powershell
(Get-Process Notepad).Kill()
```

Der `Get-Process` Befehl wird in Klammern eingeschlossen, um sicherzustellen, dass er ausgeführt wird, bevor die Kill-Methode aufgerufen wird. Die- `Kill` Methode wird dann für das zurückgegebene- `Process` Objekt aufgerufen.

Eine weitere sehr nützliche Methode ist die- `Replace` Methode von Zeichen folgen. Die- `Replace` Methode ersetzt Text in einer Zeichenfolge. Im folgenden Beispiel kann der Punkt (.) direkt nach dem endanführungs Zeichen der Zeichenfolge platziert werden.

```powershell
'this is rocket science'.Replace('rocket', 'rock')
```

```Output
this is rock science
```

Wie in den vorherigen Beispielen gezeigt, können Sie eine Methode für ein Objekt aufrufen, das Sie mit einem Befehl, einem Objekt in einer Variablen oder etwas, das zu einem Objekt führt (z. b. eine Zeichenfolge in Anführungszeichen).

Ab PowerShell 4,0 wird der Methodenaufruf mithilfe dynamischer Methodennamen unterstützt.

### <a name="learning-about-methods"></a>Erlernen von Methoden

Um Definitionen der Methoden eines Objekts zu suchen, navigieren Sie zu Hilfe Themen für den Objekttyp, und suchen Sie nach der entsprechenden Methoden Seite. Auf der folgenden Seite werden z. b. die Methoden von Process Objects [System. Diagnostics. Process](/dotnet/api/system.diagnostics.process#methods)beschrieben.

Überprüfen Sie die Methoden Definition, die dem Syntax Diagramm eines PowerShell-Cmdlets ähnelt, um die Argumente einer Methode zu bestimmen.

Eine Methoden Definition kann mindestens eine Methoden Signatur aufweisen, die den Parametersätzen von PowerShell-Cmdlets ähnelt. Die Signaturen zeigen alle gültigen Formate von Befehlen zum Aufrufen der Methode an.

Beispielsweise enthält die- `CopyTo` Methode der- `FileInfo` Klasse die folgenden beiden Methoden Signaturen:

```
    CopyTo(String destFileName)
    CopyTo(String destFileName, Boolean overwrite)
```

Die erste Methoden Signatur nimmt den Namen der Ziel Datei (und einen Pfad). Im folgenden Beispiel wird die erste `CopyTo` Methode verwendet, um die `Final.txt` Datei in das Verzeichnis zu kopieren `C:\Bin` .

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt")
```

> [!NOTE]
> Im Gegensatz zum- _Argument_ Modus von PowerShell werden Objektmethoden im _Ausdrucks_ Modus ausgeführt. Hierbei handelt es sich um eine Pass-Through-Version von .NET Framework, auf der PowerShell basiert. Im _Ausdrucks_ Modus sind **bareword** -Argumente (Zeichen folgen ohne Anführungszeichen) nicht zulässig. Dieser Unterschied wird angezeigt, wenn Sie einen Pfad als Parameter und den Pfad als Argument verwenden. Weitere Informationen finden Sie unter [about_Parsing](about_Parsing.md)

Die zweite Methoden Signatur nimmt einen Ziel Dateinamen und einen booleschen Wert an, der bestimmt, ob die Zieldatei überschrieben werden soll, falls Sie bereits vorhanden ist.

Im folgenden Beispiel wird die zweite Methode verwendet, um `CopyTo` die `Final.txt` Datei in das Verzeichnis zu kopieren `C:\Bin` und vorhandene Dateien zu überschreiben.

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt", $true)
```

### <a name="methods-of-scalar-objects-and-collections"></a>Methoden von skalaren Objekten und Auflistungen

Die Methoden eines Objekts ("Skalar") eines bestimmten Typs unterscheiden sich häufig von den Methoden einer Auflistung von Objekten desselben Typs.

Beispielsweise verfügt jeder Prozess über eine- `Kill` Methode, aber eine Auflistung von Prozessen weist keine Kill-Methode auf.

Ab PowerShell 3,0 versucht PowerShell, Skript Fehler zu verhindern, die sich aus den unterschiedlichen Methoden von skalaren Objekten und Auflistungen ergeben.

Wenn Sie eine Sammlung übermitteln, aber eine Methode anfordern, die nur in einzelnen (skalaren) Objekten vorhanden ist, ruft PowerShell die-Methode für jedes Objekt in der Auflistung auf.

Wenn die-Methode für die einzelnen Objekte und für die Auflistung vorhanden ist, wird nur die-Methode der-Auflistung aufgerufen.

Diese Funktion funktioniert auch mit Eigenschaften von skalaren Objekten und Auflistungen. Weitere Informationen finden Sie unter [about_Properties](about_Properties.md).

### <a name="examples"></a>Beispiele

Im folgenden Beispiel wird die **Kill** -Methode einzelner Prozess Objekte in einer Auflistung von-Objekten ausgeführt.

Der erste Befehl startet drei Instanzen des Notepad-Prozesses. `Get-Process` Ruft alle drei Instanzen des Notepad-Prozesses ab und speichert Sie in der `$p` Variablen.

```powershell
Notepad; Notepad; Notepad
$p = Get-Process Notepad
$p.Count
```

```Output
3
```

Der nächste Befehl führt die **Kill** -Methode für alle drei Prozesse in der `$p` Variablen aus. Dieser Befehl funktioniert, obwohl eine Auflistung von Prozessen keine-Methode besitzt `Kill` .

```powershell
$p.Kill()
Get-Process Notepad
```

Der- `Get-Process` Befehl bestätigt, dass die- `Kill` Methode funktioniert hat.

```Output
Get-Process : Cannot find a process with the name "notepad". Verify the proc
ess name and call the cmdlet again.
At line:1 char:12
+ Get-Process <<<<  notepad
    + CategoryInfo          : ObjectNotFound: (notepad:String) [Get-Process]
, ProcessCommandException
    + FullyQualifiedErrorId : NoProcessFoundForGivenName,Microsoft.PowerShel
l.Commands.GetProcessCommand
```

Dieses Beispiel ist funktional äquivalent zur Verwendung des- `Foreach-Object` Cmdlets, um die-Methode für jedes Objekt in der Auflistung auszuführen.

```powershell
$p | ForEach-Object {$_.Kill()}
```

### <a name="foreach-and-where-methods"></a>Foreach-Methode und Where-Methode

Ab PowerShell 4,0 wird das Filtern von Sammlungen mithilfe einer Methoden Syntax unterstützt. Dies ermöglicht die Verwendung von zwei neuen Methoden beim Umgang mit Sammlungen `ForEach` und `Where` .

Weitere Informationen zu diesen Methoden finden Sie unter [about_arrays](about_arrays.md).

### <a name="calling-a-specific-method-when-multiple-overloads-exist"></a>Aufrufen einer bestimmten Methode, wenn mehrere über Ladungen vorhanden sind

Beachten Sie das folgende Szenario, wenn Sie .NET-Methoden aufrufen. Wenn eine Methode ein-Objekt akzeptiert, aber über eine-Schnittstelle verfügt, die einen spezifischeren Typ annimmt, wählt PowerShell die Methode aus, die das Objekt akzeptiert, es sei denn, Sie haben es explizit in diese Schnittstelle umgewandelt.

```powershell
Add-Type -TypeDefinition @'

   // Interface
   public interface IFoo {
     string Bar(int p);
   }

   // Type that implements the interface
   public class Foo : IFoo {

   // Direct member method named 'Bar'
   public string Bar(object p) { return $"object: {p}"; }

   // *Explicit* implementation of IFoo's 'Bar' method().
   string IFoo.Bar(int p) {
       return $"int: {p}";
   }

}
'@
```

In diesem Beispiel wurde die weniger spezifische Überladung der `object` **Bar** -Methode ausgewählt.

```powershell
[Foo]::new().Bar(1)
```

```Output
object: 1
```

In diesem Beispiel konvertieren wir die-Methode in die-Schnittstelle **IFoo** , um die spezifischere Überlastung der **Bar** -Methode auszuwählen.

```powershell
([IFoo] [Foo]::new()).Bar(1)
```

```Output
int: 1
```

## <a name="see-also"></a>Weitere Informationen

[about_Objects](about_Objects.md)

[about_Properties](about_Properties.md)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)
