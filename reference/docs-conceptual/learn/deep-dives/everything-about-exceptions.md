---
title: Alles, was Sie schon immer über Ausnahmen wissen wollten
description: Die Fehlerbehandlung gehört beim Schreiben von Code einfach dazu.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 589e5d1decff7aa49ce36e10908e4464a768758d
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685511"
---
# <a name="everything-you-wanted-to-know-about-exceptions"></a>Alles, was Sie schon immer über Ausnahmen wissen wollten

Die Fehlerbehandlung gehört beim Schreiben von Code einfach dazu. Wir können häufig die Bedingungen für erwartetes Verhalten überprüfen und validieren. Bei unerwartetem Verhalten kommt die Ausnahmebehandlung ins Spiel. Sie können ganz einfach Ausnahmen behandeln, die durch den Code anderer Programmierer generiert werden, oder Sie können selbst Ausnahmen generieren, die andere behandeln können.

> [!NOTE]
> Die [Originalversion][] dieses Artikels ist im Blog von [@KevinMarquette][] erschienen. Das PowerShell-Team dankt Kevin Marquette, dass er diesen Inhalt mit uns teilt. Weitere Informationen finden Sie in seinem Blog auf [PowerShellExplained.com][].

## <a name="basic-terminology"></a>Grundlegende Terminologie

Wir müssen einige grundlegende Begriffe klären, bevor wir uns mit diesem Thema befassen.

### <a name="exception"></a>Ausnahme

Eine Ausnahme ist wie ein Ereignis, das ausgelöst wird, wenn die normale Fehlerbehandlung das Problem nicht beheben kann.
Der Versuch, eine Zahl durch 0 zu teilen, oder unzureichender Arbeitsspeicher sind Beispiele für Ereignisse, die eine Ausnahme erzeugen. Manchmal erstellt der Autor des Codes, den Sie verwenden, Ausnahmen für bestimmte Probleme, falls diese auftreten.

### <a name="throw-and-catch"></a>Throw und Catch

Wenn eine Ausnahme auftritt, wird dies als „Auslösen einer Ausnahme“ bezeichnet. Um eine ausgelöste Ausnahme zu behandeln, müssen Sie sie abfangen. Wenn eine Ausnahme ausgelöst und nicht abgefangen wird, wird die Ausführung des Skripts beendet.

### <a name="the-call-stack"></a>Die Aufrufliste

Die Aufrufliste ist die Liste der Funktionen, die sich gegenseitig aufgerufen haben. Wenn eine Funktion aufgerufen wird, wird sie am Anfang der Liste hinzugefügt. Eine Funktion, die beendet oder zurückgegeben wird, wird aus der Liste entfernt.

Wenn eine Ausnahme ausgelöst wird, wird diese Aufrufliste eingecheckt, damit sie von einem Ausnahmehandler abgefangen werden kann.

### <a name="terminating-and-non-terminating-errors"></a>Fehler mit und ohne Abbruch

Eine Ausnahme ist im Allgemeinen ein Fehler mit Abbruch. Eine ausgelöste Ausnahme wird entweder abgefangen oder beendet die aktuelle Ausführung. Standardmäßig wird ein Fehler ohne Abbruch durch `Write-Error` generiert, und dem Ausgabestream wird ein Fehler hinzugefügt, ohne dass eine Ausnahme ausgelöst wird.

Dies sollten Sie unbedingt beachten, da `Write-Error` und andere Fehler ohne Abbruch `catch` nicht auslösen.

### <a name="swallowing-an-exception"></a>Behalten einer Ausnahme

Dies ist das Verhalten, wenn Sie einen Fehler abfangen, um ihn zu unterdrücken. Gehen Sie dabei sehr vorsichtig vor, da dies die Problembehandlung sehr schwierig machen kann.

## <a name="basic-command-syntax"></a>Grundlegende Befehlssyntax

Im Folgenden finden Sie eine kurze Übersicht über die in PowerShell verwendete grundlegende Syntax für die Ausnahmebehandlung.

### <a name="throw"></a>Throw

Zum Erstellen unseres eigenen Ausnahmeereignisses lösen wir mit dem Schlüsselwort `throw` eine Ausnahme aus.

```powershell
function Start-Something
{
    throw "Bad thing happened"
}
```

Dadurch wird eine Laufzeitausnahme erstellt, die ein Fehler mit Abbruch ist. Sie wird von einem `catch` in einer Aufruffunktion verarbeitet oder beendet das Skript mit einer Meldung wie der folgenden.

```powershell
PS> Start-Something

Bad thing happened
At line:1 char:1
+ throw "Bad thing happened"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (Bad thing happened:String) [], RuntimeException
    + FullyQualifiedErrorId : Bad thing happened
```

#### <a name="write-error--erroraction-stop"></a>Write-Error: -ErrorAction Stop

Ich habe bereits erwähnt, dass `Write-Error` nicht standardmäßig einen Fehler mit Abbruch auslöst. Wenn Sie `-ErrorAction Stop` angeben, generiert `Write-Error` einen Fehler mit Abbruch, der mit einem `catch` behandelt werden kann.

```powershell
Write-Error -Message "Houston, we have a problem." -ErrorAction Stop
```

Vielen Dank an Lee Dailey, der daran erinnert hat, dass `-ErrorAction Stop` sich auch auf diese Weise verwenden lässt.

#### <a name="cmdlet--erroraction-stop"></a>Cmdlet: -ErrorAction Stop

Wenn Sie `-ErrorAction Stop` in einer beliebigen erweiterten Funktion oder einem Cmdlet angeben, werden alle `Write-Error`-Anweisungen in Fehler mit Abbruch umgewandelt, die die Ausführung anhalten oder von einem `catch` verarbeitet werden können.

```powershell
Start-Something -ErrorAction Stop
```

### <a name="trycatch"></a>Try/Catch

Die Ausnahmebehandlung in PowerShell (und vielen anderen Sprachen) funktioniert so, dass Sie zuerst einen `try`-Vorgang für einen Codeabschnitt ausführen. Wenn dadurch ein Fehler ausgelöst wird, können Sie diesen mit `catch` abfangen. Im Folgenden sehen Sie ein kurzes Beispiel.

```powershell
try
{
    Start-Something
}
catch
{
    Write-Output "Something threw an exception"
}

try
{
    Start-Something -ErrorAction Stop
}
catch
{
    Write-Output "Something threw an exception or used Write-Error"
}
```

Das `catch`-Skript wird nur ausgeführt, wenn ein Fehler mit Abbruch vorliegt. Bei korrekter Ausführung von `try` wird `catch` übersprungen.

### <a name="tryfinally"></a>Try/Finally

Es gibt Fälle, in denen Sie einen Fehler nicht behandeln müssen, aber dennoch Code benötigen, der ausgeführt wird, wenn eine Ausnahme auftritt oder nicht. Genau das macht ein `finally`-Skript.

Sehen Sie sich folgendes Beispiel an:

```powershell
$command = [System.Data.SqlClient.SqlCommand]::New(queryString, connection)
$command.Connection.Open()
$command.ExecuteNonQuery()
$command.Connection.Close()
```

Jedes Mal, wenn Sie eine Verbindung mit einer Ressource herstellen oder öffnen, sollten Sie die Verbindung auch wieder schließen. Wenn `ExecuteNonQuery()` eine Ausnahme auslöst, wird die Verbindung nicht geschlossen. Hier ist derselbe Code in einem `try/finally`-Block.

```powershell
$command = [System.Data.SqlClient.SqlCommand]::New(queryString, connection)
try
{
    $command.Connection.Open()
    $command.ExecuteNonQuery()
}
finally
{
    $command.Connection.Close()
}
```

In diesem Beispiel wird die Verbindung geschlossen, wenn ein Fehler vorliegt. Sie wird auch geschlossen, wenn kein Fehler vorliegt. Das `finally`-Skript wird jedes Mal ausgeführt.

Da die Ausnahme nicht abgefangen wird, wird sie weiterhin in der Aufrufliste nach oben weitergegeben.

### <a name="trycatchfinally"></a>Try/Catch/Finally

Es ist völlig zulässig, `catch` und `finally` in Kombination zu verwenden. In den meisten Fällen werden Sie sicher nur eine der Optionen benötigen, aber es kann durchaus Szenarien geben, in denen Sie beide verwenden.

## <a name="psitem"></a>$PSItem

So, die Grundlagen sind bekannt – jetzt können wir etwas genauer ins Detail gehen.

Innerhalb des `catch`-Blocks gibt es eine automatische Variable (`$PSItem` oder `$_`) vom Typ `ErrorRecord`, die die Details zur Ausnahme enthält. Im Folgenden sehen Sie eine kurze Übersicht über einige der wichtigsten Eigenschaften.

In diesen Beispielen habe ich in `ReadAllText` einen ungültigen Pfad verwendet, um diese Ausnahme zu generieren.

```powershell
[System.IO.File]::ReadAllText( '\\test\no\filefound.log')
```

### <a name="psitemtostring"></a>PSItem.ToString()

Damit erhalten Sie eine klare und eindeutige Meldung, die Sie bei der Protokollierung und in Ausgaben ganz allgemein verwenden können. `ToString()` wird automatisch aufgerufen, wenn `$PSItem` in eine Zeichenfolge eingefügt wird.

```powershell
catch
{
    Write-Output "Ran into an issue: $($PSItem.ToString())"
}

catch
{
    Write-Output "Ran into an issue: $PSItem"
}
```

### <a name="psiteminvocationinfo"></a>$PSItem.InvocationInfo

Diese Eigenschaft enthält zusätzliche von PowerShell gesammelte Informationen über die Funktion oder das Skript, in der bzw. dem die Ausnahme ausgelöst wurde. Hier sehen Sie die `InvocationInfo` aus der Beispielausnahme, die ich erstellt habe.

```powershell
PS> $PSItem.InvocationInfo | Format-List *

MyCommand             : Get-Resource
BoundParameters       : {}
UnboundArguments      : {}
ScriptLineNumber      : 5
OffsetInLine          : 5
ScriptName            : C:\blog\throwerror.ps1
Line                  :     Get-Resource
PositionMessage       : At C:\blog\throwerror.ps1:5 char:5
                        +     Get-Resource
                        +     ~~~~~~~~~~~~
PSScriptRoot          : C:\blog
PSCommandPath         : C:\blog\throwerror.ps1
InvocationName        : Get-Resource
```

Die wichtigen Details zeigen hier den `ScriptName`, die `Line` des Codes und die `ScriptLineNumber`, wo der Aufruf begann.

### <a name="psitemscriptstacktrace"></a>$PSItem.ScriptStackTrace

Diese Eigenschaft zeigt die Reihenfolge der Funktionsaufrufe, über die Sie zu dem Code gelangen, in dem die Ausnahme generiert wurde.

```powershell
PS> $PSItem.ScriptStackTrace
at Get-Resource, C:\blog\throwerror.ps1: line 13
at Start-Something, C:\blog\throwerror.ps1: line 5
at <ScriptBlock>, C:\blog\throwerror.ps1: line 18
```

Ich führe nur Aufrufe von Funktionen im selben Skript durch, aber hiermit würden die Aufrufe nachverfolgt, wenn mehrere Skripts beteiligt wären.

### <a name="psitemexception"></a>$PSItem.Exception

Dies ist die eigentliche Ausnahme, die ausgelöst wurde.

#### <a name="psitemexceptionmessage"></a>$PSItem.Exception.Message

Hier sehen Sie die allgemeine Meldung, in der die Ausnahme beschrieben wird. Diese ist ein guter Ausgangspunkt für die Problembehandlung. Für die meisten Ausnahmen gibt es eine Standardmeldung, Sie können aber auch benutzerdefinierte Meldungen festlegen, die beim Auslösen einer Ausnahme angezeigt werden.

```powershell
PS> $PSItem.Exception.Message

Exception calling "ReadAllText" with "1" argument(s): "The network path was not found."
```

Dies ist auch die Meldung, die beim Aufrufen von `$PSItem.ToString()` zurückgegeben wird, wenn nichts im `ErrorRecord` festgelegt wurde.

#### <a name="psitemexceptioninnerexception"></a>$PSItem.Exception.InnerException

Ausnahmen können innere Ausnahmen enthalten. Dies ist häufig der Fall, wenn der aufgerufene Code eine Ausnahme abfängt und eine andere Ausnahme auslöst. Die ursprüngliche Ausnahme wird in die neue Ausnahme eingefügt.

```powershell
PS> $PSItem.Exception.InnerExceptionMessage
The network path was not found.
```

Ich werde dies später genauer erläutern, wenn es um das erneute Auslösen von Ausnahmen geht.

#### <a name="psitemexceptionstacktrace"></a>$PSItem.Exception.StackTrace

Das ist die `StackTrace` (Stapelüberwachung) für die Ausnahme. Ich habe oben eine `ScriptStackTrace` gezeigt, aber diese hier ist für die Aufrufe von verwaltetem Code vorgesehen.

```Output
at System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean
 useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs,
 String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32
 bufferSize, FileOptions options, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean
 checkHost)
at System.IO.StreamReader..ctor(String path, Encoding encoding, Boolean detectEncodingFromByteOrderMarks,
 Int32 bufferSize, Boolean checkHost)
at System.IO.File.InternalReadAllText(String path, Encoding encoding, Boolean checkHost)
at CallSite.Target(Closure , CallSite , Type , String )
```

Sie erhalten diese Stapelüberwachung nur, wenn das Ereignis durch verwalteten Code ausgelöst wird. Ich rufe direkt eine .NET Framework-Funktion auf. Das ist also alles, was wir in diesem Beispiel sehen können. Wenn Sie sich eine Stapelüberwachung ansehen, sollten Sie nach der Stelle suchen, an der Ihr Code aufhört und die Systemaufrufe beginnen.

## <a name="working-with-exceptions"></a>Arbeiten mit Ausnahmen

Das Thema Ausnahmen umfasst weit mehr als die grundlegende Syntax und Ausnahmeeigenschaften.

### <a name="catching-typed-exceptions"></a>Abfangen typisierter Ausnahmen

Sie können auswählen, welche Ausnahmen Sie abfangen wollen. Ausnahmen besitzen einen Typ, und Sie können angeben, welchen Ausnahmetyp Sie abfangen möchten.

```powershell
try
{
    Start-Something -Path $path
}
catch [System.IO.FileNotFoundException]
{
    Write-Output "Could not find $path"
}
catch [System.IO.IOException]
{
        Write-Output "IO error with the file: $path"
}
```

Der Ausnahmetyp wird für jeden `catch`-Block geprüft, bis ein Typ gefunden wird, der mit der Ausnahme übereinstimmt.
Sie müssen wissen, dass Ausnahmen von anderen Ausnahmen erben können. Im Beispiel oben erbt `FileNotFoundException` von `IOException`. Wenn also zuerst `IOException` aufgetreten ist, würde diese Ausnahme stattdessen verarbeitet. Auch bei mehreren Übereinstimmungen wird nur ein catch-Block aufgerufen.

Wenn wir beispielsweise eine `System.IO.PathTooLongException` hätten, würde die `IOException` übereinstimmen. Hätten wir aber eine `InsufficientMemoryException`, dann würde diese nicht abgefangen und stattdessen im Stapel nach oben weitergegeben werden.

### <a name="catch-multiple-types-at-once"></a>Gleichzeitiges Abfangen mehrerer Typen

Es ist möglich, mehrere Ausnahmetypen mit der gleichen `catch`-Anweisung abzufangen.

```powershell
try
{
    Start-Something -Path $path -ErrorAction Stop
}
catch [System.IO.DirectoryNotFoundException],[System.IO.FileNotFoundException]
{
    Write-Output "The path or file was not found: [$path]"
}
catch [System.IO.IOException]
{
    Write-Output "IO error with the file: [$path]"
}
```

Vielen Dank an `/u/Sheppard_Ra` für diesen Vorschlag.

### <a name="throwing-typed-exceptions"></a>Auslösen typisierter Ausnahmen

Sie können in PowerShell typisierte Ausnahmen auslösen. Anstatt wie folgt `throw` mit einer Zeichenfolge aufzurufen:

```powershell
throw "Could not find: $path"
```

Verwenden Sie stattdessen einen Ausnahmebeschleuniger wie den folgenden:

```powershell
throw [System.IO.FileNotFoundException] "Could not find: $path"
```

In diesem Fall müssen Sie jedoch eine Meldung angeben.

Sie können auch eine neue Instanz einer Ausnahme erstellen, die ausgelöst werden soll. In diesem Fall ist die Meldung optional, da das System über Standardmeldungen für alle integrierten Ausnahmen verfügt.

```powershell
throw [System.IO.FileNotFoundException]::new()
throw [System.IO.FileNotFoundException]::new("Could not find path: $path")
```

Wenn Sie nicht PowerShell 5.0 oder höher verwenden, müssen Sie den älteren Ansatz `New-Object` verwenden.

```powershell
throw (New-Object -TypeName System.IO.FileNotFoundException )
throw (New-Object -TypeName System.IO.FileNotFoundException -ArgumentList "Could not find path: $path")
```

Indem Sie eine typisierte Ausnahme verwenden, können Sie (oder andere) die Ausnahme nach Typ abfangen, wie im vorherigen Abschnitt erläutert.

#### <a name="write-error--exception"></a>Write-Error: -Exception

Wir können diese typisierten Ausnahmen zu `Write-Error` hinzufügen und weiterhin einen `catch`-Vorgang für die Fehler nach Ausnahmetyp durchführen. Verwenden Sie `Write-Error` wie in diesen Beispielen:

```powershell
# with normal message
Write-Error -Message "Could not find path: $path" -Exception ([System.IO.FileNotFoundException]::new()) -ErrorAction Stop

# With message inside new exception
Write-Error -Exception ([System.IO.FileNotFoundException]::new("Could not find path: $path")) -ErrorAction Stop

# Pre PS 5.0
Write-Error -Exception ([System.IO.FileNotFoundException]"Could not find path: $path") -ErrorAction Stop

Write-Error -Message "Could not find path: $path" -Exception ( New-Object -TypeName System.IO.FileNotFoundException ) -ErrorAction Stop
```

Dann können wir sie wie folgt abfangen:

```powershell
catch [System.IO.FileNotFoundException]
{
    Write-Log $PSItem.ToString()
}
```

#### <a name="the-big-list-of-net-exceptions"></a>Die lange Liste der .NET-Ausnahmen

Ich habe mithilfe der [Reddit/r/PowerShell-Community][] eine Masterliste mit Hunderten .NET-Ausnahmen als Ergänzung für diesen Beitrag zusammengestellt.

- [Die lange Liste der .NET-Ausnahmen][]

Ich durchsuche diese Liste zunächst nach Ausnahmen, die meiner Ansicht nach gut zu meiner Situation passen. Versuchen Sie, Ausnahmen im Basis-`System`-Namespace zu verwenden.

### <a name="exceptions-are-objects"></a>Ausnahmen sind Objekte

Wenn Sie damit anfangen, viele typisierte Ausnahmen zu verwenden, behalten Sie im Hinterkopf, dass es sich um-Objekte handelt. Unterschiedliche Ausnahmen besitzen unterschiedliche Konstruktoren und Eigenschaften. Wenn Sie in der [FileNotFoundException][]-Dokumentation nach `System.IO.FileNotFoundException`suchen, sehen Sie, dass Sie eine Meldung und einen Dateipfad übergeben können.

```powershell
[System.IO.FileNotFoundException]::new("Could not find file", $path)
```

Und es gibt eine `FileName`-Eigenschaft, die diesen Dateipfad verfügbar macht.

```powershell
catch [System.IO.FileNotFoundException]
{
    Write-Output $PSItem.Exception.FileName
}
```

Weitere Konstruktoren und Objekteigenschaften finden Sie in der [.NET-Dokumentation][].

### <a name="re-throwing-an-exception"></a>Erneutes Auslösen einer Ausnahme

Wenn Sie in Ihrem `catch`-Block lediglich einen `throw`-Vorgang für dieselbe Ausnahme durchführen möchten, dann führen Sie keinen `catch`-Vorgang durch. Sie sollten nur einen `catch`-Vorgang für eine Ausnahme durchführen, die Sie behandeln oder für die Sie eine Aktion ausführen möchten, wenn sie auftritt.

Es gibt Fälle, in denen Sie eine Aktion für eine Ausnahme ausführen, die Ausnahme aber erneut auslösen möchten, damit ein nachgeschalteter Prozess sie verarbeiten kann. Wir könnten eine Meldung schreiben oder das Problem in der Nähe der Stelle protokollieren, an der wir es entdeckt haben, das Problem aber weiter oben im Stapel verarbeiten.

```powershell
catch
{
    Write-Log $PSItem.ToString()
    throw $PSItem
}
```

Interessanterweise können wir `throw` innerhalb von `catch` aufrufen, und die aktuelle Ausnahme wird erneut ausgelöst.

```powershell
catch
{
    Write-Log $PSItem.ToString()
    throw
}
```

Wir möchten die Ausnahme erneut auslösen, um die ursprünglichen Ausführungsinformationen wie Quellskript und Zeilennummer beizubehalten. Wenn wir an dieser Stelle eine neue Ausnahme auslösen, wird verborgen, wo die Ausnahme begonnen hat.

#### <a name="re-throwing-a-new-exception"></a>Erneutes Auslösen einer neuen Ausnahme

Wenn Sie eine Ausnahme abfangen, aber eine andere auslösen möchten, sollten Sie die ursprüngliche Ausnahme in der neuen Ausnahme schachteln. Dadurch kann weiter unten im Stapel als `$PSItem.Exception.InnerException` darauf zugegriffen werden.

```powershell
catch
{
    throw [System.MissingFieldException]::new('Could not access field',$PSItem.Exception)
}
```

#### <a name="pscmdletthrowterminatingerror"></a>$PSCmdlet.ThrowTerminatingError()

Das Einzige, was mir an der Verwendung von `throw` für unformatierte Ausnahmen nicht gefällt, ist die Tatsache, dass die Fehlermeldung auf die `throw`-Anweisung zeigt und angibt, dass sich das Problem in dieser Zeile befindet.

```Output
Unable to find the specified file.
At line:31 char:9
+         throw [System.IO.FileNotFoundException]::new()
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (:) [], FileNotFoundException
    + FullyQualifiedErrorId : Unable to find the specified file.
```

Eine Meldung zu einem Fehler im Skript aufgrund des Aufrufs von `throw` in Zeile 31 ist für die Benutzer Ihres Skripts nicht wirklich brauchbar. Sie erhalten dadurch keine hilfreichen Informationen.

Dexter Dhami hat darauf hingewiesen, dass ich `ThrowTerminatingError()` verwenden kann, um dies zu korrigieren.

```powershell
$PSCmdlet.ThrowTerminatingError(
    [System.Management.Automation.ErrorRecord]::new(
        ([System.IO.FileNotFoundException]"Could not find $Path"),
        'My.ID',
        [System.Management.Automation.ErrorCategory]::OpenError,
        $MyObject
    )
)
```

Wenn wir davon ausgehen, dass `ThrowTerminatingError()` in einer Funktion namens `Get-Resource` aufgerufen wurde, sollten wir den folgenden Fehler sehen.

```Output
Get-Resource : Could not find C:\Program Files (x86)\Reference
Assemblies\Microsoft\Framework\.NETPortable\v4.6\System.IO.xml
At line:6 char:5
+     Get-Resource -Path $Path
+     ~~~~~~~~~~~~
    + CategoryInfo          : OpenError: (:) [Get-Resource], FileNotFoundException
    + FullyQualifiedErrorId : My.ID,Get-Resource
```

Sehen Sie, wie auf die `Get-Resource`-Funktion als Quelle des Problems verwiesen wird? Das sind hilfreiche Informationen für Benutzer.

Da `$PSItem` ein `ErrorRecord` ist, können wir auch `ThrowTerminatingError` auf diese Weise zum erneuten Auslösen verwenden.

```powershell
catch
{
    $PSCmdlet.ThrowTerminatingError($PSItem)
}
```

Dadurch wird die Fehlerquelle für das Cmdlet geändert, und die Interna Ihrer Funktion werden vor den Benutzern Ihres Cmdlets verborgen.

## <a name="try-can-create-terminating-errors"></a>„try“ kann Fehler mit Abbruch erstellen

Kirk Munro weist darauf hin, dass einige Ausnahmen nur bei Ausführung in einem `try/catch`-Block Fehler mit Abbruch sind. Er hat mir das folgende Beispiel zur Verfügung gestellt, das eine Laufzeitausnahme aufgrund einer Division durch Null generiert.

```powershell
function Start-Something { 1/(1-1) }
```

Führen Sie den Aufruf wie folgt aus. Sie werden sehen, dass der Fehler generiert und die Meldung trotzdem ausgegeben wird.

```powershell
&{ Start-Something; Write-Output "We did it. Send Email" }
```

Wenn Sie jedoch denselben Code in einem `try/catch`-Block einfügen, passiert etwas anderes.

```powershell
try
{
    &{ Start-Something; Write-Output "We did it. Send Email" }
}
catch
{
    Write-Output "Notify Admin to fix error and send email"
}
```

Der Fehler wird zu einem Fehler mit Abbruch, und die erste Meldung wird nicht ausgegeben. Ein Aspekt gefällt mir hier allerdings nicht: Sie können diesen Code in einer Funktion einsetzen, und er verhält sich anders, wenn jemand `try/catch`verwendet.

Ich selbst hatte damit keine Probleme, aber es ist ein – wenngleich seltener – Fall, den Sie kennen müssen.

### <a name="pscmdletthrowterminatingerror-inside-trycatch"></a>$PSCmdlet.ThrowTerminatingError() in „try/catch“

Eine Besonderheit von `$PSCmdlet.ThrowTerminatingError()` besteht darin, dass ein Fehler mit Abbruch innerhalb Ihres Cmdlets erstellt wird, der jedoch nach Verlassen des Cmdlets in einen Fehler ohne Abbruch umgewandelt wird. Dadurch muss der Aufrufer Ihrer Funktion entscheiden, wie der Fehler behandelt werden soll. Der Fehler kann mit `-ErrorAction Stop` wieder in einen Fehler mit Abbruch umgewandelt oder in `try{...}catch{...}` aufgerufen werden.

### <a name="public-function-templates"></a>Öffentliche Funktionsvorlagen

Eine letzte Information, die ich aus meinem Gespräch mit Kirk Munro mitgenommen habe: Er platziert einen `try{...}catch{...}`-Block um jeden `begin`-, `process`- und `end`-Block in all seinen erweiterten Funktionen. In diesen allgemeinen Catch-Blöcken verwendet er eine einzige Zeile mit `$PSCmdlet.ThrowTerminatingError($PSItem)`, um alle Ausnahmen zu behandeln, die seine Funktionen verlassen.

```powershell
function Start-Something
{
    [CmdletBinding()]
    param()

    process
    {
        try
        {
            ...
        }
        catch
        {
            $PSCmdlet.ThrowTerminatingError($PSItem)
        }
    }
}
```

Da sich alles in einer `try`-Anweisung innerhalb seiner Funktionen befindet, ist die gesamte Verarbeitung konsistent. Dadurch erhält der Endbenutzer auch eindeutige Fehler, die den internen Code aus dem generierten Fehler ausblenden.

## <a name="trap"></a>Trap

Ich habe mich hier auf den `try/catch`-Aspekt von Ausnahmen konzentriert. Es gibt jedoch ein älteres Feature, das ich erwähnen muss, bevor wir zum Ende kommen.

Ein `trap` wird in ein Skript oder eine Funktion platziert, um alle Ausnahmen abzufangen, die in diesem Gültigkeitsbereich auftreten. Wenn eine Ausnahme auftritt, wird der Code im `trap` ausgeführt, und anschließend wird der normale Code fortgesetzt. Wenn mehrere Ausnahmen auftreten, wird das Trap immer wieder aufgerufen.

```powershell
trap
{
    Write-Log $PSItem.ToString()
}

throw [System.Exception]::new('first')
throw [System.Exception]::new('second')
throw [System.Exception]::new('third')
```

Ich persönlich habe diesen Ansatz nie verwendet, kann aber den Nutzen in Admin- oder Controllerskripts sehen, die jede einzelne Ausnahme protokollieren und dann trotzdem weiter ausgeführt werden.

## <a name="closing-remarks"></a>Abschließende Hinweise

Mit einer vernünftigen Ausnahmebehandlung werden Ihre Skripts nicht nur stabiler, sondern Sie können Probleme mit diesen Ausnahmen auch einfacher beheben.

Ich habe `throw` sehr ausführlich erläutert, weil es eins der Kernkonzepte der Ausnahmebehandlung ist. PowerShell bietet auch `Write-Error` zum Verarbeiten aller Situationen, in denen Sie `throw` verwenden würden. Denken Sie also nach der Lektüre dieses Artikels nicht, dass Sie `throw` unbedingt verwenden müssen.

Nachdem ich die Ausnahmebehandlung so ausführlich beschrieben habe, werde ich jetzt `Write-Error -Stop` verwenden, um Fehler in meinem Code zu generieren. Ich werde auch den Rat von Kirk beherzigen und `ThrowTerminatingError` als bevorzugten Ausnahmehandler für jede Funktion verwenden.

<!-- link references -->
[powershellexplained.com]: https://powershellexplained.com/
[Originalversion]: https://powershellexplained.com/2017-04-10-Powershell-exceptions-everything-you-ever-wanted-to-know/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Reddit/r/PowerShell-Community]: https://www.reddit.com/r/PowerShell/comments/64866o/kevmar_all_net_46_exceptions_list_for_use_with/
[Die lange Liste der .NET-Ausnahmen]: https://powershellexplained.com/2017-04-07-all-dotnet-exception-list
[FileNotFoundException]: /dotnet/api/System.IO.FileNotFoundException
[.NET-Dokumentation]: /dotnet/api
