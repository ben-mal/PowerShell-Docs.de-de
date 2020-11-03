---
description: Erläutert, wie die `pwsh` Befehlszeilenschnittstelle verwendet wird. Zeigt die Befehlszeilenparameter an und beschreibt die Syntax.
keywords: powershell,cmdlet
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pwsh?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pwsh
ms.openlocfilehash: c71848e327822f7cbc659310d3fa47a5a46a37a2
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222924"
---
# <a name="about-pwsh"></a>Informationen zu pwsh

## <a name="short-description"></a>Kurze Beschreibung
Erläutert, wie die `pwsh` Befehlszeilenschnittstelle verwendet wird. Zeigt die Befehlszeilenparameter an und beschreibt die Syntax.

## <a name="long-description"></a>Lange Beschreibung

## <a name="syntax"></a>Syntax

```
pwsh[.exe]
   [[-File] <filePath> [args]]
   [-Command { - | <script-block> [-args <arg-array>]
                 | <string> [<CommandParameters>] } ]
   [-ConfigurationName <string>]
   [-CustomPipeName <string>]
   [-EncodedCommand <Base64EncodedCommand>]
   [-ExecutionPolicy <ExecutionPolicy>]
   [-InputFormat {Text | XML}]
   [-Interactive]
   [-Login]
   [-MTA]
   [-NoExit]
   [-NoLogo]
   [-NonInteractive]
   [-NoProfile]
   [-OutputFormat {Text | XML}]
   [-SettingsFile <SettingsFilePath>]
   [-SSHServerMode]
   [-STA]
   [-Version]
   [-WindowStyle <style>]
   [-WorkingDirectory <directoryPath>]

pwsh[.exe] -h | -Help | -? | /?
```

## <a name="parameters"></a>Parameter

Bei allen Parametern wird die Groß-/Kleinschreibung beachtet

### <a name="-file---f"></a>-Datei | -f

Wenn der Wert von `File` ist `-` , wird der Befehls Text aus der Standardeingabe gelesen.
Wenn Sie `pwsh -File -` ohne umgeleitete Standardeingabe ausführen, wird eine reguläre Sitzung gestartet. Dies ist das gleiche wie bei der Angabe des `File` Parameters überhaupt nicht.

Dies ist der Standardparameter, wenn keine Parameter vorhanden sind, aber Werte in der Befehlszeile vorhanden sind. Das angegebene Skript wird im lokalen Gültigkeitsbereich ("Punkt-Source") ausgeführt, sodass die Funktionen und Variablen, die das Skript erstellt, in der aktuellen Sitzung verfügbar sind. Geben Sie den Pfad der Skriptdatei und Parameter an. File muss der letzte Parameter im Befehl sein, da alle Zeichen, die nach dem Datei Parameternamen eingegeben werden, als Pfad der Skriptdatei gefolgt von den Skript Parametern interpretiert werden.

Die Switch-Parameter eines Skripts werden in der Regel entweder einbezogen oder ausgelassen.
Der folgende Befehl verwendet beispielsweise den All-Parameter der Get-Script.ps1 Skriptdatei: `-File .\Get-Script.ps1 -All`

In seltenen Fällen müssen Sie möglicherweise einen **booleschen** Wert für einen Switch-Parameter angeben. Um einen **booleschen** Wert für einen Switch-Parameter im Wert des **File** -Parameters anzugeben, verwenden Sie den-Parameter, der normalerweise von einem Doppelpunkt und dem booleschen Wert gefolgt wird, z `-File .\Get-Script.ps1 -All:$False` . b.:.

Parameter, die an das Skript übergeben werden, werden als Zeichenfolgenliterale übergeben (nach der Interpretation durch die aktuelle Shell). Wenn Sie z. b. `cmd.exe` verwenden und einen Umgebungsvariablen Wert übergeben möchten, verwenden Sie die folgende `cmd.exe` Syntax: `pwsh -File .\test.ps1 -TestParam %windir%`

Im Gegensatz dazu `pwsh -File .\test.ps1 -TestParam $env:windir` führt das Ausführen von in dazu, `cmd.exe` dass das Skript die Literalzeichenfolge empfängt, `$env:windir` da es für die aktuelle Shell keine besondere Bedeutung hat `cmd.exe` . Der `$env:windir` Stil der Umgebungsvariablen Referenz _kann_ innerhalb eines **Befehls** Parameters verwendet werden, da er als PowerShell-Code interpretiert wird.

Wenn Sie denselben Befehl aus einem _Batch Skript_ ausführen möchten, verwenden Sie auch `%~dp0` anstelle von `.\` oder, `$PSScriptRoot` um das aktuelle Ausführungs Verzeichnis darzustellen: `pwsh -File %~dp0test.ps1 -TestParam %windir%` . Wenn Sie stattdessen verwenden `.\test.ps1` , löst PowerShell einen Fehler aus, da der literalpfad nicht gefunden werden kann. `.\test.ps1`

Wenn die Skriptdatei mit einem Befehl beendet wird `exit` , wird der Prozessexitcode auf das numerische Argument festgelegt, das mit dem Befehl verwendet wird `exit` . Beim normalen beenden ist der Exitcode immer `0` .

Ähnlich wie `-Command` beim Auftreten eines Fehlers mit Skript Abbruch wird der Exitcode auf festgelegt `1` . Anders als bei wird `-Command` die Ausführung mit <kbd>STRG</kbd>C unterbrochen, wenn der Exitcode - <kbd>C</kbd> ist `0` .

### <a name="-command---c"></a>-Befehl | -c

Führt die angegebenen Befehle (und alle Parameter) aus, als ob Sie an der PowerShell-Eingabeaufforderung eingegeben wurden, und wird dann beendet, es sei denn, der- `NoExit` Parameter wird angegeben.

Der Wert des **Befehls** kann `-` , ein Skriptblock oder eine Zeichenfolge sein. Wenn der Wert von **Command** ist `-` , wird der Befehls Text aus der Standardeingabe gelesen.

Der **Command** -Parameter akzeptiert nur einen Skriptblock für die Ausführung, wenn der an den **Befehl** übergebenen Wert als **ScriptBlock** -Typ erkannt werden kann. Dies ist _nur_ möglich, wenn `pwsh` von einem anderen PowerShell-Host ausgeführt wird. Der **ScriptBlock** -Typ kann in einer vorhandenen-Variable enthalten, von einem Ausdruck zurückgegeben oder vom PowerShell-Host als literaler Skriptblock in geschweiften Klammern () analysiert werden, `{}` bevor er an übergeben wird `pwsh` .

```powershell
pwsh -Command {Get-WinEvent -LogName security}
```

In `cmd.exe` gibt es keinen Skriptblock (oder einen **ScriptBlock** -Typ), sodass der an den **Befehl** übergeben Wert _immer_ eine Zeichenfolge ist. Sie können einen Skriptblock innerhalb der Zeichenfolge schreiben, aber anstatt ausgeführt zu werden, verhält er sich genau so, als ob Sie ihn an einer typischen PowerShell-Eingabeaufforderung eingegeben hätten, wobei der Inhalt des Skriptblocks wieder an Sie ausgegeben wird.

Eine an den **Befehl** weiter gegebene Zeichenfolge wird weiterhin als PowerShell-Code ausgeführt, sodass die Skriptblock geschweiften Klammern bei der Ausführung von häufig nicht erforderlich sind `cmd.exe` . Zum Ausführen eines Inlineskriptblocks, der in einer Zeichenfolge definiert ist, kann der [Aufrufoperator](about_operators.md#special-operators) `&` verwendet werden:

```
pwsh -Command "& {Get-WinEvent -LogName security}"
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

### <a name="-configurationname---config"></a>-ConfigurationName | -config

Gibt einen Konfigurations Endpunkt an, in dem PowerShell ausgeführt wird. Dies kann ein beliebiger Endpunkt sein, der auf dem lokalen Computer registriert ist, einschließlich der standardmäßigen PowerShell-Remoting-Endpunkte oder ein benutzerdefinierter Endpunkt, der über bestimmte Benutzer Rollen

Beispiel: `pwsh -ConfigurationName AdminRoles`

### <a name="-custompipename"></a>-Custompipame

Gibt den Namen an, der für einen zusätzlichen IPC-Server (Named Pipe) verwendet wird, der für das Debuggen und andere prozessübergreifende Kommunikation verwendet wird. Dies bietet einen vorhersagbaren Mechanismus zum Herstellen einer Verbindung mit anderen PowerShell-Instanzen. Wird normalerweise mit dem **custompipame** -Parameter in verwendet `Enter-PSHostProcess` .

Dieser Parameter wurde in PowerShell 6,2 eingeführt.

Beispiel:

```powershell
# PowerShell instance 1
pwsh -CustomPipeName mydebugpipe
# PowerShell instance 2
Enter-PSHostProcess -CustomPipeName mydebugpipe
```

### <a name="-encodedcommand---e---ec"></a>-Encodecodcommand | -e | -EC

Akzeptiert eine Base64-codierte Zeichen folgen Version eines Befehls. Verwenden Sie diesen Parameter, um Befehle an PowerShell zu übermitteln, die komplexe, in Anführungszeichen eingefügte Zitate Die Base64-Darstellung muss eine UTF-16-codierte Zeichenfolge sein.

Beispiel:

```powershell
$command = 'dir "c:\program files" '
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
pwsh -encodedcommand $encodedCommand
```

### <a name="-executionpolicy---ex---ep"></a>-ExecutionPolicy | -Ex | -EP

Legt die Standard Ausführungs Richtlinie für die aktuelle Sitzung fest und speichert Sie in der `$env:PSExecutionPolicyPreference` Umgebungsvariablen. Dieser Parameter ändert nicht die permanent konfigurierten Ausführungsrichtlinien.

Dieser Parameter gilt nur für Windows-Computer. Die `$env:PSExecutionPolicyPreference` Umgebungsvariable ist auf nicht-Windows-Plattformen nicht vorhanden.

### <a name="-inputformat---inp---if"></a>-Input Format | -INP | -if

Beschreibt das Format der Daten, die an PowerShell übermittelt werden. Gültige Werte sind "Text" (Textzeichenfolgen) oder "XML" (serialisiertes CLIXML-Format).

### <a name="-interactive---i"></a>-Interaktiv | -i

Stellen Sie eine interaktive Eingabeaufforderung für den Benutzer zur Verfügung. Umgekehrt für den nicht interaktiven Parameter.

### <a name="-login---l"></a>-Login | -l

Unter Linux und macOS startet PowerShell als Anmeldungs-Shell, wobei/bin/sh zum Ausführen von Anmelde Profilen verwendet wird, z. b./etc/profile und ~/.profile.
Unter Windows führt dieser Switch keine Aktion aus.

> [!IMPORTANT]
> Dieser Parameter muss zuerst als Anmeldungs-Shell gestartet werden, um PowerShell zu starten.
> Das übergeben dieses Parameters an einer anderen Position wird ignoriert.

So richten Sie `pwsh` als Anmeldungs-Shell auf Unix-ähnlichen Betriebssystemen ein:

- Überprüfen Sie, ob der vollständige absolute Pfad zu `pwsh` unter aufgeführt ist. `/etc/shells`
  - Dieser Pfad ist in der Regel etwas wie `/usr/bin/pwsh` unter Linux oder `/usr/local/bin/pwsh` macOS.
  - Bei einigen Installationsmethoden wird dieser Eintrag automatisch zum Installations Zeitpunkt hinzugefügt.
  - Wenn `pwsh` nicht in vorhanden ist `/etc/shells` , verwenden Sie einen Editor, um den Pfad in `pwsh` der letzten Zeile an anzufügen. Hierfür sind erweiterte Berechtigungen erforderlich, um zu bearbeiten.
- Verwenden Sie das Hilfsprogramm " [CHSH](https://linux.die.net/man/1/chsh) ", um die Shell des aktuellen Benutzers auf festzulegen `pwsh` :

  ```sh
  chsh -s /usr/bin/pwsh
  ```

> [!WARNING]
> `pwsh`Die Einstellung als Anmeldungs-Shell wird derzeit nicht unter Windows-Subsystem für Linux (WSL) unterstützt, und der Versuch, `pwsh` als Anmeldungs-Shell festzulegen, kann dazu führen, dass WSL nicht interaktiv gestartet werden kann.

### <a name="-mta"></a>-MTA

Starten Sie PowerShell mit einem Multithread-Apartment. Dieser Schalter ist nur unter Windows verfügbar.

### <a name="-noexit---noe"></a>-NoExit | -Noe

Nach dem Ausführen der Startbefehle erfolgt kein Beenden.

Beispiel: `pwsh -NoExit -Command Get-Date`

### <a name="-nologo---nol"></a>-Nologo | -Nol

Blendet das Copyright Banner beim Start interaktiver Sitzungen aus.

### <a name="-noninteractive---noni"></a>-Nicht interaktiv | -Noni

Zeigt dem Benutzer keine interaktive Eingabeaufforderung. Alle Versuche, interaktive Features zu verwenden, wie z `Read-Host` . b. oder Bestätigungs Aufforderungen, führen zu Fehlern bei der Anweisungs Beendigung.

### <a name="-noprofile---nop"></a>-NoProfile | -NOP

Die PowerShell-Profile werden nicht geladen.

### <a name="-outputformat---o---of"></a>-OutputFormat | -o | -von

Bestimmt, wie die Ausgabe von PowerShell formatiert ist. Gültige Werte sind "Text" (Textzeichenfolgen) oder "XML" (serialisiertes CLIXML-Format).

Beispiel: `pwsh -o XML -c Get-Date`

Wenn eine PowerShell-Sitzung aufgerufen wird, erhalten Sie deserialisierte Objekte als Ausgabe Zeichen folgen. Wenn die Ausgabe aus anderen Shells aufgerufen wird, werden Zeichen folgen Daten als CliXML-Text formatiert.

### <a name="-settingsfile---settings"></a>-SettingsFile | -Einstellungen

Überschreibt die systemweite `powershell.config.json` Einstellungsdatei für die Sitzung. Standardmäßig werden systemweite Einstellungen aus dem `powershell.config.json` im `$PSHOME` Verzeichnis gelesen.

Beachten Sie, dass diese Einstellungen nicht von dem Endpunkt verwendet werden, der durch das-Argument angegeben wird `-ConfigurationName` .

Beispiel: `pwsh -SettingsFile c:\myproject\powershell.config.json`

### <a name="-sshservermode---sshs"></a>-Sshservermode | -SSHS

Wird in sshd_config zum Ausführen von PowerShell als SSH-Subsystem verwendet. Sie ist nicht für andere Zwecke vorgesehen oder wird nicht unterstützt.

### <a name="-sta"></a>-STA

Starten Sie PowerShell mit einem Single Thread-Apartment. Dies ist die Standardoption. Dieser Schalter ist nur unter Windows verfügbar.

### <a name="-version---v"></a>-Version | -v

Zeigt die Version von PowerShell an. Zusätzliche Parameter werden ignoriert.

### <a name="-windowstyle---w"></a>-WindowStyle | -w

Legt den Fensterstil für die Sitzung fest. Gültige Werte sind „Normal“, „Minimized“, „Maximized“ und „Hidden“.

### <a name="-workingdirectory---wd"></a>-WorkingDirectory | -WD

Legt das anfängliche Arbeitsverzeichnis fest, indem beim Start ausgeführt wird. Jeder gültige PowerShell-Dateipfad wird unterstützt.

Verwenden Sie Folgendes, um PowerShell in Ihrem Basisverzeichnis zu starten: `pwsh -WorkingDirectory ~`

### <a name="-help---"></a>-Help, -?, /?

Zeigt die Hilfe für an `pwsh` . Wenn Sie einen pwsh-Befehl in PowerShell eingeben, stellen Sie den Befehlsparametern einen Bindestrich ( `-` ) und keinen Schrägstrich () voran `/` .
