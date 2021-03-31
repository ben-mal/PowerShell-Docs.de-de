---
description: Beschreibt Variablen, die Zustandsinformationen für PowerShell speichern. Diese Variablen werden von PowerShell erstellt und verwaltet.
Locale: en-US
ms.date: 03/29/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_automatic_variables?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Automatic_Variables
ms.openlocfilehash: 440b609a008f2d0d3d3a789f45348814c95f6088
ms.sourcegitcommit: bdd0fedaf9ba534645b2f7eb1fe1241481f58715
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "105936630"
---
# <a name="about-automatic-variables"></a>Informationen zu automatischen Variablen

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt Variablen, die Zustandsinformationen für PowerShell speichern. Diese Variablen werden von PowerShell erstellt und verwaltet.

## <a name="long-description"></a>Lange Beschreibung

Konzeptionell werden diese Variablen als schreibgeschützt betrachtet. Obwohl Sie in geschrieben werden **können** , sollten Sie aus Gründen der Abwärtskompatibilität **nicht** in schreiben.

Im folgenden finden Sie eine Liste der automatischen Variablen in PowerShell:

### <a name=""></a>$$

Enthält das letzte Token in der letzten Zeile, die von der Sitzung empfangen wurde.

### <a name=""></a>$?

Enthält den Ausführungs Status des letzten Befehls. Sie enthält **true** , wenn der letzte Befehl erfolgreich war, und **false** , wenn Sie fehlgeschlagen ist.

Für Cmdlets und erweiterte Funktionen, die auf mehreren Stufen in einer Pipeline ausgeführt werden (z. b. sowohl in `process` -als auch in- `end` Blöcken), wird der Aufruf `this.WriteError()` von bzw `$PSCmdlet.WriteError()` . an einem beliebigen Punkt `$?` auf **false** festgelegt, wie `this.ThrowTerminatingError()` und `$PSCmdlet.ThrowTerminatingError()` .

Das `Write-Error` Cmdlet legt `$?` nach der Ausführung immer **false** fest, wird jedoch nicht auf false festgelegt, `$?` Wenn eine Funktion aufgerufen wird: 

```powershell
function Test-WriteError
{
    Write-Error "Bad"
    $? # $false
}

Test-WriteError
$? # $true
```

Zum letzteren Zweck `$PSCmdlet.WriteError()` sollte stattdessen verwendet werden.

Bei nativen Befehlen (ausführbare Dateien) `$?` wird auf **true** festgelegt, wenn den `$LASTEXITCODE` Wert 0 hat, und auf **false** festgelegt, wenn `$LASTEXITCODE` ein beliebiger anderer Wert ist.

> [!NOTE]
> Bis PowerShell 7, das eine-Anweisung in Klammern enthält `(...)` , wird die Teil Ausdruck-Syntax `$(...)` oder der Array Ausdruck `@(...)` immer `$?` auf **true** zurückgesetzt, sodass `(Write-Error)` `$?` als **true** angezeigt wird.
> Dies wurde in PowerShell 7 geändert, sodass `$?` immer den tatsächlichen Erfolg der letzten Befehlsausführung in diesen Ausdrücken widerspiegelt.

### <a name=""></a>$^

Enthält das erste Token in der letzten Zeile, die von der Sitzung empfangen wurde.

### <a name="_"></a>$_

Wie in `$PSItem`. Enthält das aktuelle-Objekt im Pipeline Objekt. Sie können diese Variable in Befehlen verwenden, die eine Aktion für jedes Objekt oder für ausgewählte Objekte in einer Pipeline ausführen.

### <a name="args"></a>$args

Enthält ein Array von Werten für nicht deklarierte Parameter, die an eine Funktion, ein Skript oder einen Skriptblock übermittelt werden. Wenn Sie eine Funktion erstellen, können Sie die Parameter mit dem- `param` Schlüsselwort deklarieren oder indem Sie eine durch Trennzeichen getrennte Liste von Parametern nach dem Funktionsnamen in Klammern einfügen.

In einer Ereignis Aktion enthält die- `$Args` Variable-Objekte, die die Ereignis Argumente des zu verarbeitenden Ereignisses darstellen. Diese Variable wird nur innerhalb des `Action` Blocks eines Ereignis Registrierungs Befehls aufgefüllt.
Der Wert dieser Variablen befindet sich auch in der **sourceargs** -Eigenschaft des **psiebargs** -Objekts, das `Get-Event` zurückgibt.

### <a name="consolefilename"></a>$ConsoleFileName

Enthält den Pfad der Konsolen Datei ( `.psc1` ), die zuletzt in der Sitzung verwendet wurde. Diese Variable wird aufgefüllt, wenn Sie PowerShell mit dem **PsConsoleFile** -Parameter starten oder wenn Sie das `Export-Console` Cmdlet verwenden, um Snap-in-Namen in eine Konsolen Datei zu exportieren.

Wenn Sie das `Export-Console` Cmdlet ohne Parameter verwenden, wird automatisch die Konsolen Datei aktualisiert, die zuletzt in der Sitzung verwendet wurde. Sie können diese automatische Variable verwenden, um zu bestimmen, welche Datei aktualisiert wird.

### <a name="error"></a>$Error

Enthält ein Array von Fehler Objekten, die die letzten Fehler darstellen.
Der letzte Fehler ist das erste Fehler Objekt im Array `$Error[0]` .

Um zu verhindern, dass dem Array ein Fehler hinzugefügt wird `$Error` , verwenden Sie den allgemeinen **ErrorAction** -Parameter mit dem Wert **Ignore**. Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).

### <a name="event"></a>$Event

Enthält ein **peventargs** -Objekt, das das Ereignis darstellt, das gerade verarbeitet wird. Diese Variable wird nur innerhalb des `Action` Blocks eines Ereignis Registrierungs Befehls (z. b.) aufgefüllt `Register-ObjectEvent` . Der Wert dieser Variablen ist das gleiche Objekt, das vom `Get-Event` Cmdlet zurückgegeben wird. Daher können Sie die Eigenschaften der `Event` Variablen (z. b.) `$Event.TimeGenerated` in einem `Action` Skriptblock verwenden.

### <a name="eventargs"></a>$EventArgs

Enthält ein-Objekt, das das erste Ereignis Argument darstellt, das von **EventArgs** des-Ereignisses abgeleitet wird, das gerade verarbeitet wird. Diese Variable wird nur innerhalb des `Action` Blocks eines Ereignis Registrierungs Befehls aufgefüllt.
Der Wert dieser Variablen befindet sich auch in der **sourceeventargs** -Eigenschaft des **peventargs** -Objekts, das `Get-Event` zurückgibt.

### <a name="eventsubscriber"></a>$EventSubscriber

Enthält ein **peventsubscriber** -Objekt, das den Ereignis Abonnenten des-Ereignisses darstellt, das gerade verarbeitet wird. Diese Variable wird nur innerhalb des `Action` Blocks eines Ereignis Registrierungs Befehls aufgefüllt. Der Wert dieser Variablen ist das gleiche Objekt, das vom `Get-EventSubscriber` Cmdlet zurückgegeben wird.

### <a name="executioncontext"></a>$ExecutionContext

Enthält ein **engineintrinsics** -Objekt, das den Ausführungs Kontext des PowerShell-Hosts darstellt. Sie können diese Variable verwenden, um die für Cmdlets verfügbaren Ausführungs Objekte zu finden.

### <a name="false"></a>$false

Enthält **false**. Sie können diese Variable verwenden, um **false** in Befehlen und Skripts darzustellen, anstatt die Zeichenfolge "false" zu verwenden. Die Zeichenfolge kann als **true** interpretiert werden, wenn Sie in eine nicht leere Zeichenfolge oder in eine ganze Zahl ungleich 0 (null) konvertiert wird.

### <a name="foreach"></a>$foreach

Enthält den Enumerator (nicht die resultierenden Werte) einer [foreach](about_ForEach.md) -Schleife. Die `$ForEach` Variable ist nur vorhanden, während die `ForEach` Schleife ausgeführt wird. Sie wird gelöscht, nachdem die Schleife abgeschlossen wurde.

Enumeratoren enthalten Eigenschaften und Methoden, mit denen Sie Schleifen Werte abrufen und die aktuelle Schleifen Iterationen ändern können. Weitere Informationen finden Sie unter [Verwenden von Enumeratoren](#using-enumerators).

### <a name="home"></a>$HOME

Enthält den vollständigen Pfad des Basisverzeichnisses des Benutzers. Diese Variable entspricht in der Regel den `"$env:homedrive$env:homepath"` Windows-Umgebungsvariablen `C:\Users\<UserName>` .

### <a name="host"></a>$Host

Enthält ein-Objekt, das die aktuelle Host Anwendung für PowerShell darstellt. Sie können diese Variable verwenden, um den aktuellen Host in Befehlen darzustellen oder um die Eigenschaften des Hosts (z. b. oder) anzuzeigen oder zu ändern `$Host.version` `$Host.CurrentCulture` `$host.ui.rawui.setbackgroundcolor("Red")` .

### <a name="input"></a>$input

Enthält einen Enumerator, der alle Eingaben auflistet, die an eine Funktion weitergegeben werden. Die `$input` -Variable ist nur für Funktionen und Skriptblöcke verfügbar (bei denen es sich um unbenannte Funktionen handelt).

- In einer Funktion ohne einen- `Begin` ,- `Process` oder- `End` Block `$input` Listet die-Variable die Auflistung aller Eingaben für die Funktion auf.

- Im- `Begin` Block enthält die- `$input` Variable keine Daten.

- Im- `Process` Block enthält die- `$input` Variable das-Objekt, das sich zurzeit in der Pipeline befindet.

- Im- `End` Block listet die- `$input` Variable die Auflistung aller Eingaben für die-Funktion auf.

  > [!NOTE]
  > Sie können die `$input` Variable nicht innerhalb des Prozess Blocks und des endblocks in derselben Funktion oder in demselben Skriptblock verwenden.

Da `$input` ein Enumerator ist, bewirkt der Zugriff auf eine der Eigenschaften, dass `$input` nicht mehr verfügbar ist. Sie können `$input` in einer anderen Variablen speichern, um die Eigenschaften wiederzuverwenden `$input` .

Enumeratoren enthalten Eigenschaften und Methoden, mit denen Sie Schleifen Werte abrufen und die aktuelle Schleifen Iterationen ändern können. Weitere Informationen finden Sie unter [Verwenden von Enumeratoren](#using-enumerators).

Die- `$input` Variable ist auch für den Befehl verfügbar, der durch den-Parameter von angegeben wird, `-Command` Wenn Sie `pwsh` von der Befehlszeile aufgerufen wird. Das folgende Beispiel wird in der Windows-Befehlsshell ausgeführt.

```CMD
echo Hello | pwsh -Command """$input World!"""
```

### <a name="iscoreclr"></a>$IsCoreCLR

Enthält, `$True` Wenn die aktuelle Sitzung auf der .net Core-Laufzeit (CoreCLR) ausgeführt wird. Andernfalls enthält `$False` .

### <a name="islinux"></a>$IsLinux

Enthält, `$True` Wenn die aktuelle Sitzung unter einem Linux-Betriebssystem ausgeführt wird.
Andernfalls enthält `$False` .

### <a name="ismacos"></a>$IsMacOS

Enthält, `$True` Wenn die aktuelle Sitzung unter einem MacOS-Betriebssystem ausgeführt wird.
Andernfalls enthält `$False` .

### <a name="iswindows"></a>$IsWindows

Enthält, `$TRUE` Wenn die aktuelle Sitzung unter einem Windows-Betriebssystem ausgeführt wird. Andernfalls enthält `$FALSE` .

### <a name="lastexitcode"></a>$LastExitCode

Enthält den Exitcode des letzten Windows-basierten Programms, das ausgeführt wurde.

### <a name="matches"></a>$Matches

Die `Matches` -Variable funktioniert mit `-match` den `-notmatch` Operatoren und.
Wenn Sie skalare Eingaben an den `-match` `-notmatch` -Operator oder den-Operator übermitteln und eine Übereinstimmung erkannt wird, wird ein boolescher Wert zurückgegeben, und die `$Matches` Automatische Variable wird mit einer Hash Tabelle mit allen übereinstimmenden Zeichen folgen Werten aufgefüllt. Die `$Matches` Hash Tabelle kann auch mit Erfassungen aufgefüllt werden, wenn Sie reguläre Ausdrücke mit dem- `-match` Operator verwenden.

Weitere Informationen zum- `-match` Operator finden Sie unter [about_Comparison_Operators](about_comparison_operators.md). Weitere Informationen zu regulären Ausdrücken finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md).

Die- `$Matches` Variable kann auch in einer- `switch` Anweisung mit dem-Parameter verwendet werden `-Regex` . Es wird auf die gleiche Weise wie die `-match` -und- `-notmatch` Operatoren aufgefüllt.
Weitere Informationen zur- `switch` Anweisung finden Sie unter [about_Switch](about_Switch.md).

### <a name="myinvocation"></a>$MyInvocation

Enthält Informationen über den aktuellen Befehl, z. b. den Namen, die Parameter, die Parameterwerte und Informationen darüber, wie der Befehl gestartet, aufgerufen oder aufgerufen wurde, z. b. der Name des Skripts, das den aktuellen Befehl aufgerufen hat.

`$MyInvocation` wird nur für Skripts, Funktionen und Skriptblöcke aufgefüllt. Sie können die Informationen im **System. Management. Automation. invocationinfo** -Objekt verwenden, das `$MyInvocation` im aktuellen Skript zurückgibt, wie z. b. den Pfad und den Dateinamen des Skripts ( `$MyInvocation.MyCommand.Path` ) oder den Namen einer Funktion ( `$MyInvocation.MyCommand.Name` ), um den aktuellen Befehl zu identifizieren. Dies ist besonders nützlich, um den Namen des aktuellen Skripts zu suchen.

Ab PowerShell 3,0 `MyInvocation` verfügt über die folgenden neuen Eigenschaften.

| Eigenschaft      | BESCHREIBUNG                                         |
| ------------- | --------------------------------------------------- |
| **PSScriptRoot**  | Enthält den vollständigen Pfad des aufgerufenen Skripts.   |
|               | der aktuelle Befehl. Der Wert dieser Eigenschaft ist  |
|               | wird nur aufgefüllt, wenn der Aufrufer ein Skript ist.         |
| **Pscommandpath** | Enthält den vollständigen Pfad und den Dateinamen des Skripts.  |
|               | , der den aktuellen Befehl aufgerufen hat. Der Wert dieses |
|               | die Eigenschaft wird nur aufgefüllt, wenn der Aufrufer ein     |
|               | „Hello World!“.                                             |

Im Gegensatz zu den `$PSScriptRoot` `$PSCommandPath` automatischen Variablen und enthalten die Eigenschaften **psscriptroot** und **pscommandpath** der `$MyInvocation` automatischen Variablen Informationen über den aufrufenden oder das aufrufende Skript, nicht über das aktuelle Skript.

### <a name="nestedpromptlevel"></a>$NestedPromptLevel

Enthält die aktuelle Eingabe Aufforderungs Ebene. Der Wert 0 gibt die ursprüngliche Eingabe Aufforderungs Ebene an. Der Wert wird erhöht, wenn Sie eine eingefügte Ebene eingeben und dekrementiert werden, wenn Sie Sie beenden.

PowerShell zeigt z. b. eine eingefügte Eingabeaufforderung an, wenn Sie die- `$Host.EnterNestedPrompt` Methode verwenden. PowerShell zeigt auch eine eingefügte Eingabeaufforderung an, wenn Sie einen Breakpoint im PowerShell-Debugger erreichen.

Wenn Sie eine eingefügte Eingabeaufforderung eingeben, hält PowerShell den aktuellen Befehl an, speichert den Ausführungs Kontext und erhöht den Wert der `$NestedPromptLevel` Variablen. Um zusätzliche Eingabe Aufforderungen für ein Eingabefenster (bis zu 128 Ebenen) zu erstellen oder zur ursprünglichen Eingabeaufforderung zurückzukehren, führen Sie den Befehl aus, oder geben Sie ein `exit` .

Die- `$NestedPromptLevel` Variable hilft Ihnen beim Nachverfolgen der Eingabe Aufforderungs Ebene. Sie können eine Alternative PowerShell-Eingabeaufforderung erstellen, die diesen Wert enthält, sodass er immer sichtbar ist.

### <a name="null"></a>$null

`$null` eine automatische Variable, die einen **null** -Wert oder einen leeren Wert enthält. Mit dieser Variablen können Sie einen fehlenden oder nicht definierten Wert in Befehlen und Skripts darstellen.

PowerShell behandelt `$null` als ein Objekt mit einem Wert, d. h. als expliziter Platzhalter, damit Sie `$null` einen leeren Wert in einer Reihe von Werten darstellen können.

Wenn z. b `$null` . in einer Auflistung enthalten ist, wird Sie als eines der-Objekte gezählt.

```powershell
$a = "one", $null, "three"
$a.count
```

```Output
3
```

Wenn Sie die `$null` Variable an das `ForEach-Object` Cmdlet weiterreichen, generiert Sie einen Wert für `$null` , genau wie für die anderen Objekte.

```powershell
"one", $null, "three" | ForEach-Object { "Hello " + $_}
```

```Output
Hello one
Hello
Hello three
```

Daher können Sie `$null` nicht verwenden, um **keinen Parameterwert** zu verwenden. Der Parameterwert `$null` überschreibt den Standardparameter Wert.

Da die Variable von PowerShell jedoch `$null` als Platzhalter behandelt wird, können Sie Sie in Skripts wie dem folgenden verwenden, was nicht funktioniert, wenn Sie `$null` ignoriert wurden.

```powershell
$calendar = @($null, $null, "Meeting", $null, $null, "Team Lunch", $null)
$days = "Sunday","Monday","Tuesday","Wednesday","Thursday",
        "Friday","Saturday"
$currentDay = 0
foreach($day in $calendar)
{
    if($day -ne $null)
    {
        "Appointment on $($days[$currentDay]): $day"
    }

    $currentDay++
}
```

```Output
Appointment on Tuesday: Meeting
Appointment on Friday: Team lunch
```

### <a name="pid"></a>$PID

Enthält die Prozess-ID (PID) des Prozesses, in dem die aktuelle PowerShell-Sitzung gehostet wird.

### <a name="profile"></a>$PROFILE

Enthält den vollständigen Pfad des PowerShell-Profils für den aktuellen Benutzer und die aktuelle Host Anwendung. Mit dieser Variablen können Sie das Profil in Befehlen darstellen. Beispielsweise können Sie ihn in einem Befehl verwenden, um zu bestimmen, ob ein Profil erstellt wurde:

```powershell
Test-Path $PROFILE
```

Oder Sie können Sie in einem Befehl verwenden, um ein Profil zu erstellen:

```powershell
New-Item -ItemType file -Path $PROFILE -Force
```

Sie können Sie in einem Befehl verwenden, um das Profil in **notepad.exe** zu öffnen:

```powershell
notepad.exe $PROFILE
```

### <a name="psboundparameters"></a>$PSBoundParameters

Enthält ein Wörterbuch mit den Parametern, die an ein Skript oder eine Funktion und ihre aktuellen Werte übermittelt werden. Diese Variable hat nur einen Wert in einem Bereich, in dem Parameter deklariert werden, z. b. ein Skript oder eine Funktion. Sie können Sie verwenden, um die aktuellen Parameterwerte anzuzeigen oder zu ändern oder um Parameterwerte an ein anderes Skript oder eine andere Funktion zu übergeben.

In diesem Beispiel übergibt die **test2** -Funktion `$PSBoundParameters` an die **test1** -Funktion. Die `$PSBoundParameters` werden im Format von **Key** und **value** angezeigt.

```powershell
function Test1 {
   param($a, $b)

   # Display the parameters in dictionary format.
   $PSBoundParameters
}

function Test2 {
   param($a, $b)

   # Run the Test1 function with $a and $b.
   Test1 @PSBoundParameters
}
```

```powershell
Test2 -a Power -b Shell
```

```Output
Key   Value
---   -----
a     Power
b     Shell
```

### <a name="pscmdlet"></a>$PSCmdlet

Enthält ein-Objekt, das das Cmdlet oder die erweiterte Funktion darstellt, die gerade ausgeführt wird.

Sie können die Eigenschaften und Methoden des-Objekts im Cmdlet oder Funktionscode verwenden, um auf die Nutzungsbedingungen zu reagieren. Beispielsweise enthält die **parametersetname** -Eigenschaft den Namen des verwendeten Parameter Satzes, und die Methode " **schuldprocess** " fügt die Parameter " **WhatIf** " und " **Confirm** " dem Cmdlet dynamisch hinzu.

Weitere Informationen über die `$PSCmdlet` Automatische Variable finden Sie unter [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) und [about_Functions_Advanced](about_Functions_Advanced.md).

### <a name="pscommandpath"></a>$PSCommandPath

Enthält den vollständigen Pfad und den Dateinamen des Skripts, das gerade ausgeführt wird. Diese Variable ist in allen Skripts gültig.

### <a name="psculture"></a>$PSCulture

Ab PowerShell 7 gibt `$PSCulture` die Kultur des aktuellen PowerShell-Runspace (Session) wieder. Wenn die Kultur in einem PowerShell-Runspace geändert wird, `$PSCulture` wird der Wert für diesen Runspace aktualisiert.

Die Kultur bestimmt das Anzeige Format von Elementen, z. b. Zahlen, Währungen und Datumsangaben, und wird in einem **System. Globalization. CultureInfo** -Objekt gespeichert. Verwenden `Get-Culture` Sie, um die Kultur des Computers anzuzeigen. `$PSCulture` enthält den Wert der **Name** -Eigenschaft.

### <a name="psdebugcontext"></a>$PSDebugContext

Beim Debuggen enthält diese Variable Informationen zur Debugumgebung. Andernfalls enthält Sie einen **null** -Wert. Daher können Sie damit angeben, ob der Debugger über Steuerelemente verfügt. Wenn Sie aufgefüllt ist, enthält Sie ein **psdebugcontext** -Objekt mit **Breakpoints** und **invocationinfo** -Eigenschaften. Die **invocationinfo** -Eigenschaft verfügt über mehrere nützliche Eigenschaften, einschließlich der **Location** -Eigenschaft. Die **Location** -Eigenschaft gibt den Pfad des Skripts an, das gedebuggt wird.

### <a name="pshome"></a>$PSHOME

Enthält den vollständigen Pfad des Installationsverzeichnisses für PowerShell (in der Regel `$env:windir\System32\PowerShell\v1.0` in Windows-Systemen). Sie können diese Variable in den Pfaden von PowerShell-Dateien verwenden. Mit dem folgenden Befehl werden z. b. die konzeptionellen Hilfe Themen nach der Word- **Variablen** durchsucht:

```powershell
Select-String -Pattern Variable -Path $pshome\*.txt
```

### <a name="psitem"></a>$PSItem

Wie in `$_`. Enthält das aktuelle-Objekt im Pipeline Objekt. Sie können diese Variable in Befehlen verwenden, die eine Aktion für jedes Objekt oder für ausgewählte Objekte in einer Pipeline ausführen.

### <a name="psscriptroot"></a>$PSScriptRoot

Enthält das Verzeichnis, in dem ein Skript ausgeführt wird.

In PowerShell 2,0 ist diese Variable nur in Skript Modulen () gültig `.psm1` .
Ab PowerShell 3,0 ist Sie in allen Skripts gültig.

### <a name="pssenderinfo"></a>$PSSenderInfo

Enthält Informationen über den Benutzer, der die PSSession gestartet hat, einschließlich der Benutzeridentität und der Zeitzone des Ursprungs Computers. Diese Variable ist nur in pssessions verfügbar.

Die `$PSSenderInfo` -Variable enthält eine vom benutzerkonfigurierbare Eigenschaft **applicationarguments**, die standardmäßig nur die `$PSVersionTable` aus der ursprünglichen Sitzung enthält. Um der **applicationarguments** -Eigenschaft Daten hinzuzufügen, verwenden Sie den **applicationarguments** -Parameter des `New-PSSessionOption` Cmdlets.

### <a name="psuiculture"></a>$PSUICulture

Enthält den Namen der Kultur der Benutzeroberfläche (UI), die derzeit im Betriebssystem verwendet wird. Die Benutzeroberflächenkultur bestimmt, welche Textzeichenfolgen für die Benutzeroberflächenelemente, z. B. Menüs und Meldungen, verwendet werden. Dies ist der Wert der **System.Globalization.CultureInfo.CurrentUICulture.Name** -Eigenschaft des Systems. Verwenden Sie das-Cmdlet, um das **System. Globalization. CultureInfo** -Objekt für das System zu erhalten `Get-UICulture` .

### <a name="psversiontable"></a>$PSVersionTable

Enthält eine schreibgeschützte Hash Tabelle, in der Details zur PowerShell-Version angezeigt werden, die in der aktuellen Sitzung ausgeführt wird. Die Tabelle enthält die folgenden Elemente:

| Eigenschaft                  | BESCHREIBUNG                                   |
| ------------------------- | --------------------------------------------- |
| **PSVersion**             | Die PowerShell-Versionsnummer                 |
| **PSEdition**             | Diese Eigenschaft hat den Wert "Desktop" für  |
|                           | PowerShell 4 und niedriger als auch PowerShell  |
|                           | 5,1 bei voll funktionsfähigen Windows-Editionen.        |
|                           | Diese Eigenschaft hat den Wert "Core" für     |
|                           | PowerShell 6 und höher sowie PowerShell  |
|                           | PowerShell 5,1 bei Editionen mit geringerer Speicherbedarf  |
|                           | wie Windows Nano Server oder Windows IOT.      |
| **Gitcomentschärd**           | Die Commit-ID der Quelldateien in GitHub |
| **Betriebssystem**                    | Beschreibung des Betriebssystems, das      |
|                           | PowerShell wird unter ausgeführt.                     |
| **Plattform**              | Plattform, auf der das Betriebssystem ausgeführt wird |
|                           | Abonnements. Der Wert unter Linux und macOS ist **UNIX**. |
|                           | Prüfen Sie `$IsMacOs` und `$IsLinux`.                |
| **Pscompatibleversions**  | Versionen von PowerShell, die kompatibel sind    |
|                           | mit der aktuellen Version                      |
| **Psremotingprotocolversion** | Die Version von PowerShell Remote      |
|                           | Verwaltungs Protokoll.                          |
| **SerializationVersion**  | Die Version der Serialisierungsmethode.       |
| **Wsmanstackversion**     | Die Versionsnummer des WS-Management Stapels |

### <a name="pwd"></a>$PWD

Enthält ein Pfad Objekt, das den vollständigen Pfad des aktuellen Verzeichnis Speicher Orts für den aktuellen PowerShell-Runspace darstellt.

> [!NOTE]
> PowerShell unterstützt mehrere Runspaces pro Prozess. Jeder Runspace verfügt über ein eigenes _Aktuelles Verzeichnis_. Dies entspricht nicht dem aktuellen Verzeichnis des Prozesses: `[System.Environment]::CurrentDirectory` .

### <a name="sender"></a>$Sender

Enthält das-Objekt, das dieses Ereignis generiert hat. Diese Variable wird nur innerhalb des Aktions Blocks eines Ereignis Registrierungs Befehls aufgefüllt. Der Wert dieser Variablen befindet sich auch in der Absender-Eigenschaft des **psiebargs** -Objekts, das `Get-Event` zurückgibt.

### <a name="shellid"></a>$ShellId

Enthält den Bezeichner der aktuellen Shell.

### <a name="stacktrace"></a>$StackTrace

Enthält eine Stapel Überwachung für den letzten Fehler.

### <a name="switch"></a>$switch

Enthält den Enumerator nicht die resultierenden Werte einer- `Switch` Anweisung. Die `$switch` Variable ist nur vorhanden, während die `Switch` Anweisung ausgeführt wird. Sie wird gelöscht, wenn die `switch` Ausführung der Anweisung abgeschlossen ist. Weitere Informationen finden Sie unter [about_Switch](about_Switch.md).

Enumeratoren enthalten Eigenschaften und Methoden, mit denen Sie Schleifen Werte abrufen und die aktuelle Schleifen Iterationen ändern können. Weitere Informationen finden Sie unter [Verwenden von Enumeratoren](#using-enumerators).

### <a name="this"></a>$this

In einem Skriptblock, der eine Skript Eigenschaft oder Skript Methode definiert, `$this` verweist die Variable auf das Objekt, das erweitert wird.

In einer benutzerdefinierten Klasse `$this` verweist die Variable auf das Klassenobjekt, das den Zugriff auf die in der-Klasse definierten Eigenschaften und Methoden zulässt.

### <a name="true"></a>$True

Enthält **true**. Sie können diese Variable verwenden, um **true** in Befehlen und Skripts darzustellen.

## <a name="using-enumerators"></a>Verwenden von Enumeratoren

Die `$input` `$foreach` Variablen, und `$switch` sind alle Enumeratoren, die zum Durchlaufen der Werte verwendet werden, die durch ihren enthaltenden Codeblock verarbeitet werden.

Ein Enumerator enthält Eigenschaften und Methoden, die Sie zum fortsetzen oder Zurücksetzen der Iterationen oder zum Abrufen von Iterations Werten verwenden können. Die direkte Bearbeitung von Enumeratoren gilt nicht als bewährte Vorgehensweise.

- In Schleifen sollten die Fluss Steuerungs Schlüsselwörter unter [brechen](about_Break.md) und [fortfahren](about_Continue.md) bevorzugt werden.
- In Funktionen, die Pipeline Eingaben akzeptieren, empfiehlt es sich, Parameter mit den Attributen **valuefrompipeline** oder **valuefrompipelinebypropertyname** zu verwenden.

  Weitere Informationen finden Sie unter [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).

### <a name="movenext"></a>MoveNext

Die [Methode "](/dotnet/api/system.collections.ienumerator.movenext) -Methode" verschiebt den Enumerator auf das nächste Element der Auflistung. " **Muvenext** " gibt " **true** " zurück, wenn der Enumerator erfolgreich erweitert wurde, " **false** ", wenn der Enumerator das Ende der Auflistung überschritten hat.

> [!NOTE]
> Der **boolesche** Wert, der My **MoveNext** zurückgibt, wird an den Ausgabestream gesendet.
> Sie können die Ausgabe unterdrücken, indem Sie Sie in Typecasting umwandeln `[void]` oder an [out-null](xref:Microsoft.PowerShell.Core.Out-Null)weiterleiten.
>
> ```powershell
> $input.MoveNext() | Out-Null
> ```
>
> ```powershell
> [void]$input.MoveNext()
> ```

### <a name="reset"></a>Reset

Die [Reset](/dotnet/api/system.collections.ienumerator.reset) -Methode legt den Enumerator auf seine anfängliche Position **vor** dem ersten Element in der Auflistung fest.

### <a name="current"></a>Aktuell

Die [Current](/dotnet/api/system.collections.ienumerator.current) -Eigenschaft ruft das-Element in der-Auflistung oder-Pipeline an der aktuellen Position des Enumerators ab.

Die **aktuelle** -Eigenschaft gibt weiterhin dieselbe Eigenschaft zurück, **bis "** " "" ".

## <a name="examples"></a>Beispiele

### <a name="example-1-using-the-input-variable"></a>Beispiel 1: Verwenden der $Input Variable

Im folgenden Beispiel löscht der Zugriff auf die- `$input` Variable die-Variable, bis der Prozess Block das nächste Mal ausgeführt wird. Bei Verwendung der **Reset** -Methode wird die `$input` Variable auf den aktuellen Pipeline Wert zurückgesetzt.

```powershell
function Test
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        "`tInput: $input"
        "`tAccess Again: $input"
        $input.Reset()
        "`tAfter Reset: $input"
    }
}

"one","two" | Test
```

```Output
Iteration: 0
    Input: one
    Access Again:
    After Reset: one
Iteration: 1
    Input: two
    Access Again:
    After Reset: two
```

Der Prozess Block setzt die Variable automatisch fort, `$input` auch wenn Sie nicht darauf zugreifen.

```powershell
$skip = $true
function Skip
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        if ($skip)
        {
            "`tSkipping"
            $skip = $false
        }
        else
        {
            "`tInput: $input"
        }
    }
}

"one","two" | Skip
```

```Output
Iteration: 0
    Skipping
Iteration: 1
    Input: two
```

### <a name="example-2-using-input-outside-the-process-block"></a>Beispiel 2: Verwenden von $Input außerhalb des Prozess Blocks

Außerhalb des Prozess Blocks stellt die `$input` Variable alle Werte dar, die an die Funktion weitergeleitet werden.

- Durch den Zugriff auf die `$input` Variable werden alle Werte gelöscht.
- Die **Reset** -Methode setzt die gesamte Auflistung zurück.
- Die **aktuelle** Eigenschaft wird nie aufgefüllt.
- Die Methode " **ivenext** " gibt false zurück, da die Auflistung nicht erweitert werden kann.
  - Durch **Aufrufen von** "" wird die `$input` Variable gelöscht.

```powershell
Function All
{
    "All Values: $input"
    "Access Again: $input"
    $input.Reset()
    "After Reset: $input"
    $input.MoveNext() | Out-Null
    "After MoveNext: $input"
}

"one","two","three" | All
```

```Output
All Values: one two three
Access Again:
After Reset: one two three
After MoveNext:
```

### <a name="example-3-using-the-inputcurrent-property"></a>Beispiel 3: Verwenden der $Input. Current-Eigenschaft

Mithilfe der **aktuellen** Eigenschaft kann auf den aktuellen Pipeline Wert mehrmals zugegriffen werden, ohne dass die **Reset** -Methode verwendet wird. Der Prozess Block ruft nicht automatisch die **Methode "** Methode" auf.

Die **aktuelle** Eigenschaft wird nie aufgefüllt, es sei denn, **Sie nennen nicht** explizit "". Der Zugriff auf die **aktuelle** Eigenschaft kann mehrmals innerhalb des Prozess Blocks erfolgen, ohne den Wert zu löschen.

```powershell
function Current
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        "`tBefore MoveNext: $($input.Current)"
        $input.MoveNext() | Out-Null
        "`tAfter MoveNext: $($input.Current)"
        "`tAccess Again: $($input.Current)"
    }
}

"one","two" | Current
```

```Output
Iteration: 0
    Before MoveNext:
    After MoveNext: one
    Access Again: one
Iteration: 1
    Before MoveNext:
    After MoveNext: two
    Access Again: two
```

### <a name="example-4-using-the-foreach-variable"></a>Beispiel 4: Verwenden der $foreach Variable

Anders als die- `$input` Variable `$foreach` stellt die-Variable immer alle Elemente in der Auflistung dar, wenn direkt darauf zugegriffen wird. Verwenden Sie die **aktuelle** -Eigenschaft, um auf das aktuelle Auflistungs Element zuzugreifen **, und die** **Reset** -Methode und die-Methode, um den Wert zu ändern.

> [!NOTE]
> Jede Iterations `foreach` Schleife ruft automatisch die Methode " **ivenext** " auf.

Die folgende-Schleife wird nur zweimal ausgeführt. In der zweiten Iterationen wird die Auflistung vor Abschluss der Iterationen auf das dritte Element verschoben. Nach der zweiten Iterations Zeit sind nun keine weiteren Werte zum Durchlaufen vorhanden, und die Schleife wird beendet.

Die Eigenschaft " **ivenext** " wirkt sich nicht auf die Variable aus, die zum Durchlaufen der Auflistung ausgewählt wurde ( `$Num` ).

```powershell
$i = 0
foreach ($num in ("one","two","three"))
{
    "Iteration: $i"
    $i++
    "`tNum: $num"
    "`tCurrent: $($foreach.Current)"

    if ($foreach.Current -eq "two")
    {
        "Before MoveNext (Current): $($foreach.Current)"
        $foreach.MoveNext() | Out-Null
        "After MoveNext (Current): $($foreach.Current)"
        "Num has not changed: $num"
    }
}
```

```Output
Iteration: 0
        Num: one
        Current: one
Iteration: 1
        Num: two
        Current: two
Before MoveNext (Current): two
After MoveNext (Current): three
Num has not changed: two
```

Bei Verwendung der Reset-Methode wird das aktuelle Element in der Auflistung zurück **gesetzt** . Im folgenden Beispiel werden die ersten beiden Elemente **zweimal** durchlaufen, da die **Reset** -Methode aufgerufen wird. Nach den ersten beiden Schleifen schlägt die `if` Anweisung fehl, und die Schleife durchläuft alle drei Elemente in der Regel.

> [!IMPORTANT]
> Dies kann zu einer Endlosschleife führen.

```powershell
$stopLoop = 0
foreach ($num in ("one","two", "three"))
{
    ("`t" * $stopLoop) + "Current: $($foreach.Current)"

    if ($num -eq "two" -and $stopLoop -lt 2)
    {
        $foreach.Reset() | Out-Null
        ("`t" * $stopLoop) + "Reset Loop: $stopLoop"
        $stopLoop++
    }
}
```

```Output
Current: one
Current: two
Reset Loop: 0
        Current: one
        Current: two
        Reset Loop: 1
                Current: one
                Current: two
                Current: three
```

### <a name="example-5-using-the-switch-variable"></a>Beispiel 5: Verwenden der $Switch Variable

Die `$switch` Variable verfügt über die exakt gleichen Regeln wie die `$foreach` Variable.
Im folgenden Beispiel werden alle enumeratorkonzepte veranschaulicht.

> [!NOTE]
> Beachten Sie, dass der **notevaluated** -Fall nie ausgeführt wird, auch wenn es keine- `break`  Anweisung nach der-Methode von "-Methode" gibt.

```powershell
$values = "Start", "MoveNext", "NotEvaluated", "Reset", "End"
$stopInfinite = $false
switch ($values)
{
    "MoveNext" {
        "`tMoveNext"
        $switch.MoveNext() | Out-Null
        "`tAfter MoveNext: $($switch.Current)"
    }
    # This case is never evaluated.
    "NotEvaluated" {
        "`tAfterMoveNext: $($switch.Current)"
    }

    "Reset" {
        if (!$stopInfinite)
        {
            "`tReset"
            $switch.Reset()
            $stopInfinite = $true
        }
    }

    default {
        "Default (Current): $($switch.Current)"
    }
}
```

```Output
Default (Current): Start
    MoveNext
    After MoveNext: NotEvaluated
    Reset
Default (Current): Start
    MoveNext
    After MoveNext: NotEvaluated
Default (Current): End
```

## <a name="see-also"></a>Siehe auch

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Hash_Tables](about_Hash_Tables.md)

[about_Preference_Variables](about_Preference_Variables.md)

[about_Splatting](about_Splatting.md)

[about_Variables](about_Variables.md)
