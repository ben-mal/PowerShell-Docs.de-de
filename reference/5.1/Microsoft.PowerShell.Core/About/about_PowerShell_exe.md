---
description: Erläutert, wie die `powershell.exe` Befehlszeilenschnittstelle verwendet wird. Zeigt die Befehlszeilenparameter an und beschreibt die Syntax.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_exe
ms.openlocfilehash: 4025630ebb3abe4c0598c85940cfce383e9c7890
ms.sourcegitcommit: 16a02ae47d1a85b01692101aa0aa6e91e1ba398e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2021
ms.locfileid: "104726654"
---
# <a name="about-powershellexe"></a>Informationen zu PowerShell.exe

## <a name="short-description"></a>Kurze Beschreibung
Erläutert, wie die `powershell.exe` Befehlszeilenschnittstelle verwendet wird. Zeigt die Befehlszeilenparameter an und beschreibt die Syntax.

## <a name="long-description"></a>Lange Beschreibung

### <a name="syntax"></a>SYNTAX

```
PowerShell[.exe]
    [-PSConsoleFile <file> | -Version <version>]
    [-NoLogo]
    [-NoExit]
    [-Sta]
    [-Mta]
    [-NoProfile]
    [-NonInteractive]
    [-InputFormat {Text | XML}]
    [-OutputFormat {Text | XML}]
    [-WindowStyle <style>]
    [-EncodedCommand <Base64EncodedCommand>]
    [-ConfigurationName <string>]
    [-File - | <filePath> <args>]
    [-ExecutionPolicy <ExecutionPolicy>]
    [-Command - | { <script-block> [-args <arg-array>] }
                | { <string> [<CommandParameters>] } ]

PowerShell[.exe] -Help | -? | /?
```

### <a name="parameters"></a>Parameter

#### <a name="-psconsolefile-filepath"></a>-PSConsoleFile \<FilePath\>

Lädt die angegebene PowerShell-Konsolendatei. Geben Sie den Pfad und Namen der Konsolendatei ein. Verwenden Sie zum Erstellen einer Konsolendatei das Cmdlet Export-Console in PowerShell.

#### <a name="-version-powershell-version"></a>-Version \<PowerShell Version\>

Startet die angegebene Version von PowerShell. Gültige Werte sind 2.0 und 3.0. Die Version, die Sie angeben, muss auf dem System installiert sein. Wenn Windows PowerShell 3,0 auf dem Computer installiert ist, ist "3,0" die Standardversion.
Andernfalls ist "2,0" die Standardversion. Weitere Informationen finden Sie unter [Installieren von PowerShell](/powershell/scripting/install/installing-windows-powershell).

#### <a name="-nologo"></a>-NoLogo

Blendet die Copyrightinformationen beim Start aus.

#### <a name="-noexit"></a>-NoExit

Nach dem Ausführen der Startbefehle erfolgt kein Beenden.

#### <a name="-sta"></a>-Sta

Startet PowerShell mit einem Singlethread-Apartment. In Windows PowerShell 2.0 ist Multithread-Apartment (MTA) die Standardeinstellung. In Windows PowerShell 3.0 ist Singlethread-Apartment (STA) die Standardeinstellung.

#### <a name="-mta"></a>-Mta

Startet PowerShell mit einem Multithread-Apartment. Dieser Parameter wird in Windows PowerShell 3.0 eingeführt. In PowerShell 2.0 stellt Multithread-Apartment (MTA) die Standardeinstellung dar. In PowerShell 3.0 ist Singlethread-Apartment (STA) die Standardeinstellung.

#### <a name="-noprofile"></a>-NoProfile

Das PowerShell-Profil wird nicht geladen.

#### <a name="-noninteractive"></a>-NonInteractive

Zeigt dem Benutzer keine interaktive Eingabeaufforderung.

#### <a name="-inputformat-text--xml"></a>-InputFormat {Text | XML}

Beschreibt das Format der Daten, die an PowerShell übermittelt werden. Gültige Werte sind "Text" (Textzeichenfolgen) oder "XML" (serialisiertes CLIXML-Format).

#### <a name="-outputformat-text--xml"></a>-OutputFormat {Text | XML}

Bestimmt, wie die Ausgabe von PowerShell formatiert ist. Gültige Werte sind "Text" (Textzeichenfolgen) oder "XML" (serialisiertes CLIXML-Format).

#### <a name="-windowstyle-window-style"></a>-WindowStyle \<Window style\>

Legt den Fensterstil für die Sitzung fest. Gültige Werte sind „Normal“, „Minimized“, „Maximized“ und „Hidden“.

#### <a name="-encodedcommand-base64encodedcommand"></a>-EncodedCommand \<Base64EncodedCommand\>

Akzeptiert eine „base-64“-codierte Zeichenfolgenversion eines Befehls. Verwenden Sie diesen Parameter, um Befehle an PowerShell zu übermitteln, die komplexe Anführungszeichen oder geschweifte Klammern erfordern. Die Zeichenfolge muss mithilfe der UTF-16LE-Zeichencodierung formatiert werden.

#### <a name="-configurationname-string"></a>-ConfigurationName \<string\>

Gibt einen Konfigurations Endpunkt an, in dem PowerShell ausgeführt wird. Dies kann ein beliebiger Endpunkt sein, der auf dem lokalen Computer registriert ist, einschließlich der standardmäßigen PowerShell-Remoting-Endpunkte oder ein benutzerdefinierter Endpunkt, der über bestimmte Benutzer Rollen

#### <a name="-file----filepath-args"></a>-File-| \<filePath\>\<args\>

Wenn der Wert der **Datei** "-" ist, wird der Befehls Text aus der Standardeingabe gelesen.
Wenn Sie `powershell -File -` ohne umgeleitete Standardeingabe ausführen, wird eine reguläre Sitzung gestartet. Dies ist das gleiche wie bei der Angabe des **Datei** Parameters.

Wenn der Wert der **Datei** ein Dateipfad ist, wird das Skript im lokalen Gültigkeitsbereich ("Punkt-Source") ausgeführt, sodass die Funktionen und Variablen, die das Skript erstellt, in der aktuellen Sitzung verfügbar sind. Geben Sie den Pfad der Skriptdatei und Parameter an. **File** muss der letzte Parameter im Befehl sein. Alle Werte, die nach dem **File** -Parameter eingegeben werden, werden als Pfad der Skriptdatei und Parameter interpretiert, die an das Skript übergeben werden.

Parameter, die an das Skript übergeben werden, werden als Zeichenfolgenliterale übergeben (nach der Interpretation durch die aktuelle Shell). Wenn Sie z. b. **cmd.exe** haben und einen Umgebungsvariablen Wert übergeben möchten, verwenden Sie die **cmd.exe** -Syntax: `powershell.exe -File .\test.ps1 -TestParam %windir%`

Im Gegensatz dazu `powershell.exe -File .\test.ps1 -TestParam $env:windir` führt das Ausführen von in **cmd.exe** dazu, dass das Skript die Literalzeichenfolge empfängt, `$env:windir` da es für die aktuelle **cmd.exe** Shell keine besondere Bedeutung hat. Der `$env:windir` Stil der Umgebungsvariablen Referenz _kann_ innerhalb eines **Befehls** Parameters verwendet werden, da er als PowerShell-Code interpretiert wird.

Wenn Sie denselben Befehl aus einem **Batch Skript** ausführen möchten, verwenden Sie auch `%~dp0` anstelle von `.\` oder, `$PSScriptRoot` um das aktuelle Ausführungs Verzeichnis darzustellen: `powershell.exe -File %~dp0test.ps1 -TestParam %windir%` .
Wenn Sie stattdessen verwenden `.\test.ps1` , löst PowerShell einen Fehler aus, da der literalpfad nicht gefunden werden kann. `.\test.ps1`

Wenn der Wert der **Datei** ein Dateipfad ist, _muss_ **File** der letzte Parameter im Befehl sein, da alle Zeichen, die nach dem **Datei** Parameternamen eingegeben werden, als Pfad der Skriptdatei gefolgt von den Skript Parametern interpretiert werden.

Sie können die Skript Parameter und-Werte in den Wert des **File** -Parameters einschließen. Beispiel: `-File .\Get-Script.ps1 -Domain Central`

Die Switch-Parameter eines Skripts werden in der Regel entweder einbezogen oder ausgelassen.
Der folgende Befehl verwendet beispielsweise den **all** -Parameter der `Get-Script.ps1` Skriptdatei: `-File .\Get-Script.ps1 -All`

In seltenen Fällen müssen Sie möglicherweise einen **booleschen** Wert für einen Parameter angeben.
Beim Ausführen eines Skripts auf diese Weise ist es nicht möglich, einen expliziten booleschen Wert für einen Switch-Parameter zu übergeben. Diese Einschränkung wurde in PowerShell 6 ( `pwsh.exe` ) entfernt.

#### <a name="-executionpolicy-executionpolicy"></a>-ExecutionPolicy \<ExecutionPolicy\>

Legt die Standard Ausführungs Richtlinie für die aktuelle Sitzung fest und speichert Sie in der `$env:PSExecutionPolicyPreference` Umgebungsvariablen. Dieser Parameter ändert nicht die PowerShell-Ausführungsrichtlinie, die in der Registrierung festgelegt ist. Weitere Informationen zu PowerShell-Ausführungsrichtlinien (einschließlich einer Liste gültiger Werte) finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).

#### <a name="-command"></a>-Command

Führt die angegebenen Befehle (und alle Parameter) aus, als ob Sie an der PowerShell-Eingabeaufforderung eingegeben wurden, und wird dann beendet, es sei denn, der- `NoExit` Parameter wird angegeben.

Der Wert des **Befehls** kann `-` , ein Skriptblock oder eine Zeichenfolge sein. Wenn der Wert von **Command** ist `-` , wird der Befehls Text aus der Standardeingabe gelesen.

Der **Command** -Parameter akzeptiert nur einen Skriptblock für die Ausführung, wenn der an den **Befehl** übergebenen Wert als **ScriptBlock** -Typ erkannt werden kann. Dies ist _nur_ möglich, wenn `powershell.exe` von einem anderen PowerShell-Host ausgeführt wird. Der **ScriptBlock** -Typ kann in einer vorhandenen-Variable enthalten, von einem Ausdruck zurückgegeben oder vom PowerShell-Host als literaler Skriptblock in geschweiften Klammern () analysiert werden, `{}` bevor er an übergeben wird `powershell.exe` .

```powershell
powershell -Command {Get-WinEvent -LogName security}
```

In `cmd.exe` gibt es keinen Skriptblock (oder einen **ScriptBlock** -Typ), sodass der an den **Befehl** übergeben Wert _immer_ eine Zeichenfolge ist. Sie können einen Skriptblock innerhalb der Zeichenfolge schreiben, aber anstatt ausgeführt zu werden, verhält er sich genau so, als ob Sie ihn an einer typischen PowerShell-Eingabeaufforderung eingegeben hätten, wobei der Inhalt des Skriptblocks wieder an Sie ausgegeben wird.

Eine an den **Befehl** weiter gegebene Zeichenfolge wird weiterhin als PowerShell-Code ausgeführt, sodass die Skriptblock geschweiften Klammern bei der Ausführung von häufig nicht erforderlich sind `cmd.exe` . Zum Ausführen eines Inlineskriptblocks, der in einer Zeichenfolge definiert ist, kann der [Aufrufoperator](about_operators.md#special-operators) `&` verwendet werden:

```cmd
powershell.exe -Command "& {Get-WinEvent -LogName security}"
```

Wenn der Wert von " **Command** " eine Zeichenfolge ist, muss **Command** der letzte Parameter für "pwsh" sein, da alle nachfolgenden Argumente als Teil des auszuführenden Befehls interpretiert werden.

Wenn Sie innerhalb einer vorhandenen PowerShell-Sitzung aufgerufen werden, werden die Ergebnisse als deserialisierte XML-Objekte und nicht als Live-Objekte an die übergeordnete Shell zurückgegeben. Bei anderen Shells werden die Ergebnisse als Zeichen folgen zurückgegeben.

Wenn der Wert von **Command** ist `-` , wird der Befehls Text aus der Standardeingabe gelesen. Sie müssen die Standardeingabe umleiten, wenn Sie den **Command** -Parameter mit der Standardeingabe verwenden. Beispiel:

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

Dieses Beispiel erzeugt die folgende Ausgabe:

```Output
in
hi there
out
```

Der Prozessexitcode wird durch den Status des letzten (ausgeführten) Befehls im Skriptblock bestimmt. Der Exitcode ist, wenn den Wert hat `0` `$?` `$true` oder `1` Wenn `$?` ist `$false` . Wenn der letzte Befehl ein externes Programm oder ein PowerShell-Skript ist, das explizit einen Exitcode angibt, der nicht `0` oder ist `1` , wird der Exitcode `1` für den Prozessexitcode in konvertiert. Fügen Sie der `exit $LASTEXITCODE` Befehls Zeichenfolge oder dem Skriptblock hinzu, um den spezifischen Exitcode beizubehalten.

Entsprechend wird der Wert 1 zurückgegeben, wenn ein Fehler mit Skript Abbruch (Runspace-abschließende), wie z `throw` . `-ErrorAction Stop` b. oder, auftritt oder wenn die Ausführung durch <kbd>STRG</kbd> - <kbd>C</kbd>unterbrochen wird.

#### <a name="-help---"></a>-Help, -?, /?

Zeigt die Hilfe für **PowerShell.exe** an. Wenn Sie einen **PowerShell.exe** Befehl in einer PowerShell-Sitzung eingeben, stellen Sie den Befehlsparametern einen Bindestrich (-) und keinen Schrägstrich (/) voran. In **cmd.exe** können Sie entweder einen Bindestrich oder einen Schrägstrich verwenden.

### <a name="remarks"></a>ANMERKUNGEN

Hinweis zur Problembehandlung: in PowerShell 2,0 tritt beim Starten einiger Programme über die PowerShell-Konsole ein Fehler mit dem **lastexitcode** "0xc0000142" auf.

### <a name="examples"></a>BEISPIELE

```powershell
# Create a new PowerShell session and load a saved console file
PowerShell -PSConsoleFile sqlsnapin.psc1

# Create a new PowerShell V2 session with text input, XML output, and no logo
PowerShell -Version 2.0 -NoLogo -InputFormat text -OutputFormat XML

# Execute a PowerShell Command in a session
PowerShell -Command "Get-EventLog -LogName security"

# Run a script block in a session
PowerShell -Command {Get-EventLog -LogName security}

# An alternate way to run a command in a new session
PowerShell -Command "& {Get-EventLog -LogName security}"

# To use the -EncodedCommand parameter:
$command = "dir 'c:\program files' "
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
powershell.exe -encodedCommand $encodedCommand
```
