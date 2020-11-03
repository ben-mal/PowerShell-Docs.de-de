---
description: Beschreibt den PowerShell-Debugger.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 08/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_debuggers?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Debuggers
ms.openlocfilehash: c53229752a26428ff4bc47fd5cecf039bdef7275
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223892"
---
# <a name="about-debuggers"></a>Informationen zu buggern

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt den PowerShell-Debugger.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Beim Debuggen wird ein Skript überprüft, während es ausgeführt wird, um Fehler in den Skript Anweisungen zu identifizieren und zu korrigieren. Der PowerShell-Debugger unterstützt Sie bei der Untersuchung und Identifizierung von Fehlern und Ineffizienzen in Ihren Skripts, Funktionen, Befehlen, PowerShell DSC-Konfigurationen (DSC) oder Ausdrücken.

Ab PowerShell 5,0 wurde der PowerShell-Debugger aktualisiert, um Skripts, Funktionen, Befehle, Konfigurationen oder Ausdrücke zu debuggen, die entweder in der-Konsole oder in Windows PowerShell ISE auf Remote Computern ausgeführt werden. Sie können ausführen `Enter-PSSession` , um eine interaktive PowerShell-Remote Sitzung zu starten, in der Sie Breakpoints festlegen und Skriptdateien und-Befehle auf dem Remote Computer debuggen können. `Enter-PSSession` die Funktionalität wurde aktualisiert, damit Sie erneut eine Verbindung mit herstellen und eine getrennte Sitzung eingeben können, die ein Skript oder einen Befehl auf einem Remote Computer ausführen. Wenn das Skript, das ausgeführt wird, auf einen Haltepunkt trifft, wird der Debugger automatisch von der Client Sitzung gestartet. Wenn die getrennte Sitzung, von der ein Skript ausgeführt wird, bereits einen Haltepunkt erreichen und am Haltepunkt angehalten wurde, `Enter-PSSession` startet automatisch den Befehlszeilen Debugger, nachdem Sie die Verbindung mit der Sitzung wieder hergestellt haben.

Sie können die Funktionen des PowerShell-Debuggers verwenden, um ein PowerShell-Skript, eine Funktion, einen Befehl oder einen Ausdruck während der Ausführung zu überprüfen. Der PowerShell-Debugger enthält eine Reihe von Cmdlets, mit denen Sie Breakpoints festlegen, Breakpoints verwalten und die-aufrufsstapel anzeigen können.

## <a name="debugger-cmdlets"></a>Debugger-Cmdlets

Der PowerShell-Debugger umfasst die folgenden Cmdlets:

- `Set-PSBreakpoint`: Legt Breakpoints für Zeilen, Variablen und Befehle fest.
- `Get-PSBreakpoint`: Ruft Breakpoints in der aktuellen Sitzung ab.
- `Disable-PSBreakpoint`: Deaktiviert Breakpoints in der aktuellen Sitzung.
- `Enable-PSBreakpoint`: Aktiviert Breakpoints in der aktuellen Sitzung erneut.
- `Remove-PSBreakpoint`: Löscht Haltepunkte aus der aktuellen Sitzung.
- `Get-PSCallStack`: Zeigt die aktuelle-aufrufsstapel an.

## <a name="starting-and-stopping-the-debugger"></a>Starten und Beenden des Debuggers

Legen Sie einen oder mehrere Haltepunkte fest, um den Debugger zu starten. Führen Sie dann das Skript, den Befehl oder die Funktion aus, die Sie debuggen möchten.

Wenn Sie einen Breakpoint erreichen, wird die Ausführung angehalten, und die Steuerung wird an den Debugger über geschaltet.

Um den Debugger zu beenden, führen Sie das Skript, den Befehl oder die Funktion aus, bis der Debugger fertig ist. Oder geben Sie `stop` oder ein `t` .

### <a name="debugger-commands"></a>Debugger-Befehle

Wenn Sie den Debugger in der PowerShell-Konsole verwenden, verwenden Sie die folgenden Befehle, um die Ausführung zu steuern. Verwenden Sie in Windows PowerShell ISE Befehle im Menü Debuggen.

Hinweis: Informationen zur Verwendung des Debuggers in anderen Host Anwendungen finden Sie in der Dokumentation zur Host Anwendung.

- `s`, `StepInto` : Führt die nächste Anweisung aus und hält dann an.

- `v`, `StepOver` : Führt die nächste Anweisung aus, überspringt jedoch Funktionen und Aufrufe. Die übersprungenen Anweisungen werden ausgeführt, aber nicht in Einzelschritten durchlaufen.

- `Ctrl+Break`: (Alle in der ISE unterbrechen) unterbricht in ein Skript, das entweder in der PowerShell-Konsole oder in Windows PowerShell ISE ausgeführt wird. Beachten Sie, dass die <kbd>STRG</kbd> + <kbd>Break</kbd> -Taste in Windows PowerShell 2,0, 3,0 und 4,0 das Programm schließt. Break all funktioniert sowohl für lokale als auch Remote Skripts, die interaktiv ausgeführt werden.

- `o`, `StepOut` : Führt die Schritte aus der aktuellen Funktion aus; eine Ebene nach oben, wenn Sie eingefügt wird. Wenn der Hauptteil im Hauptteil ist, wird er bis zum Ende oder zum nächsten Haltepunkt fortgesetzt. Die übersprungenen Anweisungen werden ausgeführt, aber nicht in Einzelschritten durchlaufen.

- `c`, `Continue` : Wird weiterhin ausgeführt, bis das Skript beendet ist oder bis der nächste Haltepunkt erreicht ist. Die übersprungenen Anweisungen werden ausgeführt, aber nicht in Einzelschritten durchlaufen.

- `l`, `List` : Zeigt den Teil des Skripts an, der ausgeführt wird. Standardmäßig werden die aktuelle Zeile, fünf vorherige Zeilen und 10 nachfolgende Zeilen angezeigt.
  Drücken Sie die EINGABETASTE, um das Skript weiterhin aufzulisten.

- `l <m>`, `List` : Zeigt 16 Zeilen des Skripts an, beginnend mit der durch angegebenen Zeilennummer `<m>` .

- `l <m> <n>`, `List` : Zeigt `<n>` Zeilen des Skripts an, beginnend mit der durch angegebenen Zeilennummer `<m>` .

- `q`, `Stop` , `Exit` : Beendet die Ausführung des Skripts und beendet den Debugger. Wenn Sie einen Auftrag durch Ausführen des Cmdlets Debuggen, wird der `Debug-Job` `Exit` Debugger vom Befehl getrennt, und der Auftrag wird weiter ausgeführt.

- `k`, `Get-PsCallStack` : Zeigt die aktuelle-aufrufsstapel an.

- `<Enter>`: Wiederholt den letzten Befehl, wenn es sich um einen Schritt (e), einen StepOver (v) oder eine Liste (l) handelt. Andernfalls stellt eine Sendeaktion dar.

- `?`, `h` : Zeigt die Debugger-Befehls Hilfe an.

Um den Debugger zu beenden, können Sie beenden (q) verwenden.

Ab PowerShell 5,0 können Sie den Exit-Befehl ausführen, um eine gestartete Debugsitzung zu beenden, die Sie durch Ausführen von oder gestartet haben `Debug-Job` `Debug-Runspace` .

Mit diesen Debuggerbefehlen können Sie ein Skript ausführen, zu einem bestimmten Zeitpunkt anhalten, die Werte von Variablen und den Status des Systems untersuchen und das Skript weiter ausführen, bis Sie ein Problem identifiziert haben.

Hinweis: Wenn Sie eine Anweisung mit einem Umleitungs Operator (z. b. ">") schrittweise ausführen, führt der PowerShell-Debugger alle verbleibenden Anweisungen im Skript aus.

Anzeigen der Werte von Skript Variablen

Im Debugger können Sie auch Befehle eingeben, den Wert von Variablen anzeigen, Cmdlets verwenden und Skripts in der Befehlszeile ausführen.

Sie können den aktuellen Wert aller Variablen im Skript, das gedebuggt wird, mit Ausnahme der folgenden automatischen Variablen anzeigen:

```powershell
$_
$Args
$Input
$MyInvocation
$PSBoundParameters
```

Wenn Sie den Wert von einer dieser Variablen anzeigen, erhalten Sie den Wert, den diese Variablen für eine interne, vom Debugger verwendete Pipeline hat, nicht den Wert der Variablen im Skript.

Um den Wert dieser Variablen für das Skript anzuzeigen, das gedebuggt wird, weisen Sie im Skript den Wert der automatischen Variablen einer neuen Variablen zu. Anschließend können Sie den Wert der neuen Variablen anzeigen.

Ein auf ein Objekt angewendeter

```powershell
$scriptArgs = $Args
$scriptArgs
```

Im Beispiel in diesem Thema wird der Wert der- `$MyInvocation` Variablen wie folgt neu zugewiesen:

```powershell
$scriptname = $MyInvocation.MyCommand.Path
```

## <a name="the-debugger-environment"></a>Die Debugger-Umgebung

Wenn Sie einen Breakpoint erreichen, geben Sie die Debugger-Umgebung ein. Die Eingabeaufforderung ändert sich, sodass Sie mit "[dbg]:" beginnt.

Weitere Informationen zum Anpassen der Eingabeaufforderung finden Sie unter [about_Prompts](about_prompts.md).

Außerdem wird in einigen Host Anwendungen, wie z. b. der PowerShell-Konsole (aber nicht in Windows PowerShell Integrated Scripting Environment [ISE]) eine schaufnahmenaufforderung zum Debuggen geöffnet. Sie können die eingefügte Eingabeaufforderung mit den wiederholten mehr-als-Zeichen (ASCII 62) erkennen, die an der Eingabeaufforderung angezeigt werden.

Das folgende Beispiel zeigt die standardmäßige debuggingaufforderung in der PowerShell-Konsole:

```
[DBG]: PS (get-location)>>>
```

Sie können die Schachtelungs Ebene mithilfe der `$NestedPromptLevel` automatischen Variablen ermitteln.

Außerdem wird eine automatische Variable, `$PSDebugContext` , im lokalen Gültigkeitsbereich definiert. Sie können das vorhanden sein der `$PsDebugContext` Variablen verwenden, um zu bestimmen, ob Sie sich im Debugger befinden.

Beispiel:

```powershell
if ($PSDebugContext) {"Debugging"} else {"Not Debugging"}
```

Sie können den Wert der `$PSDebugContext` Variablen im Debuggen verwenden.

```
[DBG]: PS>>> $PSDebugContext.InvocationInfo

Name   CommandLineParameters  UnboundArguments  Location
----   ---------------------  ----------------  --------
=      {}                     {}                C:\ps-test\vote.ps1 (1)
```

## <a name="debugging-and-scope"></a>Debuggen und Bereich

Durch das unterbrechen in den Debugger wird der Bereich, in dem Sie arbeiten, nicht geändert. Wenn Sie jedoch einen Haltepunkt in einem Skript erreichen, wechseln Sie in den Skript Bereich. Der Skript Bereich ist ein untergeordnetes Element des Bereichs, in dem Sie den Debugger ausgeführt haben.

Um die im Skript Bereich definierten Variablen und Aliase zu suchen, verwenden Sie den Scope-Parameter der `Get-Alias` `Get-Variable` Cmdlets oder.

Beispielsweise ruft der folgende Befehl die Variablen im lokalen Bereich (Skript) ab:

```powershell
Get-Variable -scope 0
```

Sie können den Befehl wie folgt abkürzen:

```powershell
gv -s 0
```

Dies ist eine hilfreiche Möglichkeit, nur die Variablen anzuzeigen, die Sie im Skript definiert haben und die Sie beim Debuggen definiert haben.

Debuggen in der Befehlszeile

Wenn Sie einen Variablen-Haltepunkt oder einen Befehls Haltepunkt festlegen, können Sie den Breakpoint nur in einer Skriptdatei festlegen. Der Breakpoint wird jedoch standardmäßig für alle Elemente festgelegt, die in der aktuellen Sitzung ausgeführt werden.

Wenn Sie z. b. einen Haltepunkt für die `$name` Variable festlegen, unterbricht der Debugger jede beliebige `$name` Variable in allen Skripts, Befehlen, Funktionen, Skript-Cmdlets oder Ausdrücken, die Sie ausführen, bis Sie den Breakpoint deaktivieren oder entfernen.

Dadurch können Sie Ihre Skripts in einem realistischeren Kontext Debuggen, in dem Sie von Funktionen, Variablen und anderen Skripts in der Sitzung und im Profil des Benutzers betroffen sein können.

Zeilen Breakpoints sind für Skriptdateien spezifisch, sodass Sie nur in Skriptdateien festgelegt werden.

## <a name="debugging-functions"></a>Debugfunktionen

Wenn Sie einen Breakpoint für eine Funktion mit den `Begin` Abschnitten, `Process` und festlegen `End` , wird der Debugger in der ersten Zeile jedes Abschnitts unterbrochen.

Beispiel:

```powershell
function test-cmdlet {
    begin {
        write-output "Begin"
    }
    process {
        write-output "Process"
    }
    end {
        write-output "End"
    }
}

C:\PS> Set-PSBreakpoint -command test-cmdlet

C:\PS> test-cmdlet

Begin
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

[DBG]: C:\PS> c
Process
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

[DBG]: C:\PS> c
End
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

# [DBG]: C:\PS>
```

## <a name="debugging-remote-scripts"></a>Debugging von Remote Skripts

Ab PowerShell 5,0 können Sie den PowerShell-Debugger in einer Remote Sitzung ausführen, entweder in der-Konsole oder in Windows PowerShell ISE.
`Enter-PSSession` die Funktionalität wurde aktualisiert, damit Sie erneut eine Verbindung mit herstellen und eine getrennte Sitzung eingeben können, die auf einem Remote Computer ausgeführt wird und derzeit ein Skript ausgeführt wird. Wenn das Skript, das ausgeführt wird, auf einen Haltepunkt trifft, wird der Debugger automatisch von der Client Sitzung gestartet.

Im folgenden Beispiel wird gezeigt, wie dies funktioniert, wobei Breakpoints in einem Skript in den Zeilen 6, 11, 22 und 25 festgelegt sind. Beachten Sie, dass im Beispiel beim Start des Debuggers zwei identifizierende Eingabe Aufforderungen vorhanden sind: der Name des Computers, auf dem die Sitzung ausgeführt wird, und die dbg-Eingabeaufforderung, die Sie darüber informiert, dass Sie sich im Debugmodus befinden.

```powershell
Enter-Pssession -Cn localhost
[localhost]: PS C:\psscripts> Set-PSBreakpoint .\ttest19.ps1 6,11,22,25

ID Script          Line     Command          Variable          Action
-- ------          ----     -------          --------          ------
0 ttest19.ps1          6
1 ttest19.ps1          11
2 ttest19.ps1          22
3 ttest19.ps1          25

[localhost]: PS C:\psscripts> .\ttest19.ps1
Hit Line breakpoint on 'C:\psscripts\ttest19.ps1:11'

At C:\psscripts\ttest19.ps1:11 char:1
+ $winRMName = "WinRM"
# + ~

[localhost]: [DBG]: PS C:\psscripts>> list

6:      1..5 | foreach { sleep 1; Write-Output "hello2day $_" }
7:  }
# 8:

9:  $count = 10
10:  $psName = "PowerShell"
11:* $winRMName = "WinRM"
12:  $myVar = 102
# 13:

14:  for ($i=0; $i -lt $count; $i++)
15:  {
16:      sleep 1
17:      Write-Output "Loop iteration is: $i"
18:      Write-Output "MyVar is $myVar"
# 19:

20:      hello2day
# 21:


[localhost]: [DBG]: PS C:\psscripts>> stepover
At C:\psscripts\ttest19.ps1:12 char:1
+ $myVar = 102
# + ~

[localhost]: [DBG]: PS C:\psscripts>> quit
[localhost]: PS C:\psscripts> Exit-PSSession
PS C:\psscripts>
```

## <a name="examples"></a>Beispiele

Dieses Testskript erkennt die Version des Betriebssystems und zeigt eine System entsprechende Meldung an. Sie enthält eine Funktion, einen Funktions aufrufund eine Variable.

Der folgende Befehl zeigt den Inhalt der Testskript Datei an:

```powershell
PS C:\PS-test>  Get-Content test.ps1

function psversion {
  "PowerShell " + $PSVersionTable.PSVersion
  if ($PSVersionTable.PSVersion.Major -lt 6) {
    "Upgrade to PowerShell 6.0!"
  }
  else {
    "Have you run a background job today (start-job)?"
  }
}

$scriptName = $MyInvocation.MyCommand.Path
psversion
"Done $scriptName."
```

Legen Sie zum Starten einen Haltepunkt an einem Point of Interest im Skript fest, z. b. eine Zeile, einen Befehl, eine Variable oder eine Funktion.

Beginnen Sie mit dem Erstellen eines Zeilen halte Punkts in der ersten Zeile des Test.ps1 Skripts im aktuellen Verzeichnis.

```powershell
PS C:\ps-test> Set-PSBreakpoint -line 1 -script test.ps1
```

Sie können diesen Befehl wie folgt abkürzen:

```powershell
PS C:\ps-test> spb 1 -s test.ps1
```

Der Befehl gibt ein Zeilen Haltepunkt Objekt ( **System. Management. Automation. linebreakpoint** ) zurück.

```
Column     : 0
Line       : 1
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\test.ps1
ScriptName : C:\ps-test\test.ps1
```

Starten Sie nun das Skript.

```powershell
PS C:\ps-test> .\test.ps1
```

Wenn das Skript den ersten Breakpoint erreicht, gibt die breakpointmeldung an, dass der Debugger aktiv ist. Es beschreibt den Haltepunkt und zeigt die erste Zeile des Skripts an, eine Funktionsdeklaration. Die Eingabeaufforderung ändert sich auch, um anzugeben, dass der Debugger über die Steuerung verfügt.

Die vorschauzeile enthält den Skriptnamen und die Zeilennummer des in der Vorschau angezeigten Befehls.

```powershell
Entering debug mode. Use h or ? for help.

Hit Line breakpoint on 'C:\ps-test\test.ps1:1'

test.ps1:1   function psversion {
# DBG>
```

Verwenden Sie den Schritt Befehl (e), um die erste Anweisung im Skript auszuführen und eine Vorschau der nächsten Anweisung anzuzeigen. Die nächste Anweisung verwendet die `$MyInvocation` Automatische Variable, um den Wert der `$scriptName` Variablen auf den Pfad und den Dateinamen der Skriptdatei festzulegen.

```powershell
DBG> s
test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
```

An diesem Punkt wird die `$scriptName` Variable nicht aufgefüllt, aber Sie können den Wert der Variablen durch anzeigen ihres Werts überprüfen. In diesem Fall handelt es sich um den Wert `$null`.

```powershell
DBG> $scriptname
# DBG>
```

Verwenden Sie einen anderen Schritt Befehl (en), um die aktuelle Anweisung auszuführen und eine Vorschau der nächsten Anweisung im Skript anzuzeigen. Die nächste Anweisung ruft die psversion-Funktion auf.

```powershell
DBG> s
test.ps1:12  psversion
```

An diesem Punkt wird die `$scriptName` Variable aufgefüllt, aber Sie überprüfen den Wert der Variablen, indem Sie Ihren Wert anzeigen. In diesem Fall wird der Wert auf den Skript Pfad festgelegt.

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```

Verwenden Sie einen anderen Schritt Befehl zum Ausführen des Funktions Aufrufes. Drücken Sie die EINGABETASTE, oder geben Sie "s" für Schritt ein.

```powershell
DBG> s
test.ps1:2       "PowerShell " + $PSVersionTable.PSVersion
```

Die Debugmeldung enthält eine Vorschau der Anweisung in der Funktion. Zum Ausführen dieser Anweisung und zum Anzeigen einer Vorschau der nächsten Anweisung in der Funktion können Sie einen- `Step` Befehl verwenden. Verwenden Sie in diesem Fall jedoch einen StepOut-Befehl (o). Dadurch wird die Ausführung der Funktion abgeschlossen (es sei denn, Sie erreicht einen Haltepunkt), und es werden Schritte zur nächsten Anweisung im Skript ausgeführt.

```powershell
DBG> o
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

Da wir die letzte Anweisung im Skript haben, haben die Befehle Step, StepOut und continue dieselbe Wirkung. Verwenden Sie in diesem Fall "StepOut (o)".

```powershell
Done C:\ps-test\test.ps1
PS C:\ps-test>
```

Der Befehl "StepOut" führt den letzten Befehl aus. Die Standardeingabe Aufforderung zeigt an, dass der Debugger beendet wurde und die Steuerung an den Befehlsprozessor zurückgegeben hat.

Führen Sie den Debugger nun erneut aus. Verwenden Sie zum Löschen des aktuellen Breakpoints zunächst die `Get-PsBreakpoint` `Remove-PsBreakpoint` Cmdlets und. (Wenn Sie vermuten, dass Sie den Breakpoint wieder verwenden, verwenden Sie das- `Disable-PsBreakpoint` Cmdlet anstelle von `Remove-PsBreakpoint` .)

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

Sie können diesen Befehl wie folgt abkürzen:

```powershell
PS C:\ps-test> gbp | rbp
```

Oder führen Sie den Befehl aus, indem Sie eine Funktion schreiben, z. b. die folgende Funktion:

```powershell
function delbr { gbp | rbp }
```

Erstellen Sie nun einen Haltepunkt für die `$scriptname` Variable.

```powershell
PS C:\ps-test> Set-PSBreakpoint -variable scriptname -script test.ps1
```

Sie können den Befehl wie folgt abkürzen:

```powershell
PS C:\ps-test> sbp -v scriptname -s test.ps1
```

Starten Sie nun das Skript. Das Skript erreicht den Variablen-Breakpoint. Der Standardmodus ist "Write", sodass die Ausführung unmittelbar vor der-Anweisung angehalten wird, die den Wert der Variablen ändert.

```powershell
PS C:\ps-test> .\test.ps1
Hit Variable breakpoint on 'C:\ps-test\test.ps1:$scriptName'
(Write access)

test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
# DBG>
```

Zeigt den aktuellen Wert der `$scriptName` Variablen an, der ist `$null` .

```powershell
DBG> $scriptName
# DBG>
```

Verwenden Sie einen Schritt Befehl (e), um die Anweisung auszuführen, die die Variable auffüllt.
Zeigen Sie dann den neuen Wert der `$scriptName` Variablen an.

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```powershell

Use a Step command (s) to preview the next statement in the script.

```powershell
DBG> s
test.ps1:12  psversion
```

Die nächste Anweisung ist ein Aufrufder psversion-Funktion. Um die Funktion zu überspringen, aber trotzdem auszuführen, verwenden Sie einen Befehl "StepOver" (v). Wenn Sie sich bereits in der-Funktion befinden, wenn Sie StepOver verwenden, ist dies nicht effektiv. Der Funktions aufrufwird zwar angezeigt, aber nicht ausgeführt.

```powershell
DBG> v
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

Der Befehl "StepOver" führt die Funktion aus und zeigt eine Vorschau der nächsten Anweisung im Skript an, die die letzte Zeile ausgibt.

Beenden Sie den Debugger mithilfe eines Beendigungs Befehls (t). Die Eingabeaufforderung kehrt zur Standardeingabe Aufforderung zurück.

```powershell
C:\ps-test>
```

Um die Breakpoints zu löschen, verwenden Sie die `Get-PsBreakpoint` `Remove-PsBreakpoint` Cmdlets und.

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

Erstellen Sie einen neuen Befehls Haltepunkt in der psversion-Funktion.

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1
```

Sie können diesen Befehl wie folgt abkürzen:

```powershell
PS C:\ps-test> sbp -c psversion -s test.ps1
```

Führen Sie nun das Skript aus.

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
# DBG>
```

Das Skript erreicht den Haltepunkt beim Funktions aufzurufen. An diesem Punkt wurde die-Funktion noch nicht aufgerufen. Dadurch haben Sie die Möglichkeit, den Action-Parameter von `Set-PSBreakpoint` zu verwenden, um Bedingungen für die Ausführung des Breakpoints festzulegen oder um Vorbereitungs-oder Diagnoseaufgaben auszuführen, z. b. das Starten eines Protokolls oder das Aufrufen eines Diagnose-oder Sicherheits Skripts.

Um eine Aktion festzulegen, verwenden Sie einen Continue-Befehl (c), um das Skript zu beenden, und einen `Remove-PsBreakpoint` Befehl zum Löschen des aktuellen Breakpoints. (Breakpoints sind schreibgeschützt, sodass Sie dem aktuellen Haltepunkt keine Aktion hinzufügen können.)

```powershell
DBG> c
Windows PowerShell 2.0
Have you run a background job today (start-job)?
Done C:\ps-test\test.ps1

PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
PS C:\ps-test>
```

Erstellen Sie nun einen neuen Befehls Haltepunkt mit einer Aktion. Der folgende Befehl legt einen Befehls Haltepunkt mit einer Aktion fest, die den Wert der `$scriptName` Variablen protokolliert, wenn die-Funktion aufgerufen wird. Da das break-Schlüsselwort in der Aktion nicht verwendet wird, wird die Ausführung nicht beendet. (Das Graviszeichen (') ist das Zeilen Fortsetzungs Zeichen.)

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1  `
-action { add-content "The value of `$scriptName is $scriptName." `
-path action.log}
```

Sie können auch Aktionen hinzufügen, die Bedingungen für den Haltepunkt festlegen. Im folgenden Befehl wird der Befehls Haltepunkt nur ausgeführt, wenn die Ausführungs Richtlinie auf RemoteSigned festgelegt ist. Dies ist die restriktivste Richtlinie, mit der Sie weiterhin Skripts ausführen können. (Das Graviszeichen (') ist das Fortsetzungs Zeichen.)

```powershell
PS C:\ps-test> Set-PSBreakpoint -script test.ps1 -command psversion `
-action { if ((Get-ExecutionPolicy) -eq "RemoteSigned") { break }}
```

Das break-Schlüsselwort in der Aktion weist den Debugger an, den Breakpoint auszuführen.
Sie können auch das Continue-Schlüsselwort verwenden, um den Debugger zur Ausführung ohne Unterbrechung zu leiten. Da das Default-Schlüsselwort Continue lautet, müssen Sie "Break" angeben, um die Ausführung zu verhindern.

Führen Sie nun das Skript aus.

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
```

Da die Ausführungs Richtlinie auf " **RemoteSigned** " festgelegt ist, wird die Ausführung beim Funktions aufzurufen angehalten.

An diesem Punkt können Sie die aufrufsstapel überprüfen. Verwenden Sie das `Get-PsCallStack` Cmdlet oder den `Get-PsCallStack` Debugger-Befehl (k). Der folgende Befehl ruft die aktuelle-Rückruf Stapel ab.

```powershell
DBG> k
2: prompt
1: .\test.ps1: $args=[]
0: prompt: $args=[]
```

Dieses Beispiel zeigt nur einige der vielen Möglichkeiten, den PowerShell-Debugger zu verwenden.

Geben Sie den folgenden Befehl ein, um weitere Informationen zu den Debugger-Cmdlets zu erhalten:

```powershell
help <cmdlet-name> -full
```

Beispiel:

```powershell
help Set-PSBreakpoint -full
```

## <a name="other-debugging-features-in-powershell"></a>Weitere Debuggingfunktionen in PowerShell

Zusätzlich zum PowerShell-Debugger enthält PowerShell einige weitere Funktionen, die Sie zum Debuggen von Skripts und Funktionen verwenden können.

- Windows PowerShell ISE enthält einen interaktiven grafischen Debugger. Um weitere Informationen zu erhalten, starten Sie Windows PowerShell ISE, und drücken Sie F1.

- Das `Set-PSDebug` -Cmdlet bietet sehr grundlegende Skripts zum Debuggen, einschließlich schrittweise und Ablauf Verfolgung.

- Verwenden `Set-StrictMode` Sie das Cmdlet, um Verweise auf nicht initialisierte Variablen, Verweise auf nicht vorhandene Eigenschaften eines Objekts und ungültige Funktions Syntax zu erkennen.

- Fügen Sie einem Skript Diagnose Anweisungen hinzu, z. b. Anweisungen, die den Wert von Variablen anzeigen, Anweisungen, die Eingaben aus der Befehlszeile lesen, oder Anweisungen, die die aktuelle Anweisung melden. Verwenden Sie die-Cmdlets, die das Schreib Verb für diese Aufgabe enthalten, z `Write-Host` `Write-Debug` . b.,, `Write-Warning` und `Write-Verbose` .

## <a name="see-also"></a>SIEHE AUCH

- [Deaktivieren-psbreakpoint](xref:Microsoft.PowerShell.Utility.Disable-PSBreakpoint)
- [Enable-psbreakpoint](xref:Microsoft.PowerShell.Utility.Enable-PSBreakpoint)
- [Get-psbreakpoint](xref:Microsoft.PowerShell.Utility.Get-PSBreakpoint)
- [Get-pscallstack](xref:Microsoft.PowerShell.Utility.Get-PSCallStack)
- [Remove-psbreakpoint](xref:Microsoft.PowerShell.Utility.Remove-PSBreakpoint)
- [Set-PSBreakpoint](xref:Microsoft.PowerShell.Utility.Set-PSBreakpoint)
- [Write-Debug](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose)
