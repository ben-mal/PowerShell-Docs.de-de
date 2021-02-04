---
description: Erläutert, wie die `pwsh` Befehlszeilenschnittstelle verwendet wird. Zeigt die Befehlszeilenparameter an und beschreibt die Syntax.
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pwsh?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pwsh
ms.openlocfilehash: 6f6e7ea66aa04eaeea2b9da7c07864180210131c
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692993"
---
# <a name="about-pwsh"></a><span data-ttu-id="a177d-104">Informationen zu pwsh</span><span class="sxs-lookup"><span data-stu-id="a177d-104">About pwsh</span></span>

## <a name="short-description"></a><span data-ttu-id="a177d-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a177d-105">Short Description</span></span>
<span data-ttu-id="a177d-106">Erläutert, wie die `pwsh` Befehlszeilenschnittstelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a177d-106">Explains how to use the `pwsh` command-line interface.</span></span> <span data-ttu-id="a177d-107">Zeigt die Befehlszeilenparameter an und beschreibt die Syntax.</span><span class="sxs-lookup"><span data-stu-id="a177d-107">Displays the command-line parameters and describes the syntax.</span></span>

## <a name="long-description"></a><span data-ttu-id="a177d-108">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a177d-108">Long Description</span></span>

## <a name="syntax"></a><span data-ttu-id="a177d-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a177d-109">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="a177d-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="a177d-110">Parameters</span></span>

<span data-ttu-id="a177d-111">Bei allen Parametern wird die Groß-/Kleinschreibung beachtet</span><span class="sxs-lookup"><span data-stu-id="a177d-111">All parameters are case-insensitive.</span></span>

### <a name="-file---f"></a><span data-ttu-id="a177d-112">-Datei | -f</span><span class="sxs-lookup"><span data-stu-id="a177d-112">-File | -f</span></span>

<span data-ttu-id="a177d-113">Wenn der Wert von `File` ist `-` , wird der Befehls Text aus der Standardeingabe gelesen.</span><span class="sxs-lookup"><span data-stu-id="a177d-113">If the value of `File` is `-`, the command text is read from standard input.</span></span>
<span data-ttu-id="a177d-114">Wenn Sie `pwsh -File -` ohne umgeleitete Standardeingabe ausführen, wird eine reguläre Sitzung gestartet.</span><span class="sxs-lookup"><span data-stu-id="a177d-114">Running `pwsh -File -` without redirected standard input starts a regular session.</span></span> <span data-ttu-id="a177d-115">Dies ist das gleiche wie bei der Angabe des `File` Parameters überhaupt nicht.</span><span class="sxs-lookup"><span data-stu-id="a177d-115">This is the same as not specifying the `File` parameter at all.</span></span>

<span data-ttu-id="a177d-116">Dies ist der Standardparameter, wenn keine Parameter vorhanden sind, aber Werte in der Befehlszeile vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a177d-116">This is the default parameter if no parameters are present but values are present in the command line.</span></span> <span data-ttu-id="a177d-117">Das angegebene Skript wird im lokalen Gültigkeitsbereich ("Punkt-Source") ausgeführt, sodass die Funktionen und Variablen, die das Skript erstellt, in der aktuellen Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a177d-117">The specified script runs in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="a177d-118">Geben Sie den Pfad der Skriptdatei und Parameter an.</span><span class="sxs-lookup"><span data-stu-id="a177d-118">Enter the script file path and any parameters.</span></span> <span data-ttu-id="a177d-119">File muss der letzte Parameter im Befehl sein, da alle Zeichen, die nach dem Datei Parameternamen eingegeben werden, als Pfad der Skriptdatei gefolgt von den Skript Parametern interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="a177d-119">File must be the last parameter in the command, because all characters typed after the File parameter name are interpreted as the script file path followed by the script parameters.</span></span>

<span data-ttu-id="a177d-120">Die Switch-Parameter eines Skripts werden in der Regel entweder einbezogen oder ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="a177d-120">Typically, the switch parameters of a script are either included or omitted.</span></span>
<span data-ttu-id="a177d-121">Der folgende Befehl verwendet beispielsweise den All-Parameter der Get-Script.ps1 Skriptdatei: `-File .\Get-Script.ps1 -All`</span><span class="sxs-lookup"><span data-stu-id="a177d-121">For example, the following command uses the All parameter of the Get-Script.ps1 script file: `-File .\Get-Script.ps1 -All`</span></span>

<span data-ttu-id="a177d-122">In seltenen Fällen müssen Sie möglicherweise einen **booleschen** Wert für einen Switch-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="a177d-122">In rare cases, you might need to provide a **Boolean** value for a switch parameter.</span></span> <span data-ttu-id="a177d-123">Um einen **booleschen** Wert für einen Switch-Parameter im Wert des **File** -Parameters anzugeben, verwenden Sie den-Parameter, der normalerweise von einem Doppelpunkt und dem booleschen Wert gefolgt wird, z `-File .\Get-Script.ps1 -All:$False` . b.:.</span><span class="sxs-lookup"><span data-stu-id="a177d-123">To provide a **Boolean** value for a switch parameter in the value of the **File** parameter, Use the parameter normally followed immediately by a colon and the boolean value, such as the following: `-File .\Get-Script.ps1 -All:$False`.</span></span>

<span data-ttu-id="a177d-124">Parameter, die an das Skript übergeben werden, werden als Zeichenfolgenliterale übergeben (nach der Interpretation durch die aktuelle Shell).</span><span class="sxs-lookup"><span data-stu-id="a177d-124">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="a177d-125">Wenn Sie z. b. `cmd.exe` verwenden und einen Umgebungsvariablen Wert übergeben möchten, verwenden Sie die folgende `cmd.exe` Syntax: `pwsh -File .\test.ps1 -TestParam %windir%`</span><span class="sxs-lookup"><span data-stu-id="a177d-125">For example, if you are in `cmd.exe` and want to pass an environment variable value, you would use the `cmd.exe` syntax: `pwsh -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="a177d-126">Im Gegensatz dazu `pwsh -File .\test.ps1 -TestParam $env:windir` führt das Ausführen von in dazu, `cmd.exe` dass das Skript die Literalzeichenfolge empfängt, `$env:windir` da es für die aktuelle Shell keine besondere Bedeutung hat `cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="a177d-126">In contrast, running `pwsh -File .\test.ps1 -TestParam $env:windir` in `cmd.exe` results in the script receiving the literal string `$env:windir` because it has no special meaning to the current `cmd.exe` shell.</span></span> <span data-ttu-id="a177d-127">Der `$env:windir` Stil der Umgebungsvariablen Referenz _kann_ innerhalb eines **Befehls** Parameters verwendet werden, da er als PowerShell-Code interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="a177d-127">The `$env:windir` style of environment variable reference _can_ be used inside a **Command** parameter, since there it is interpreted as PowerShell code.</span></span>

<span data-ttu-id="a177d-128">Wenn Sie denselben Befehl aus einem _Batch Skript_ ausführen möchten, verwenden Sie auch `%~dp0` anstelle von `.\` oder, `$PSScriptRoot` um das aktuelle Ausführungs Verzeichnis darzustellen: `pwsh -File %~dp0test.ps1 -TestParam %windir%` .</span><span class="sxs-lookup"><span data-stu-id="a177d-128">Similarly, if you want to execute the same command from a _Batch script_, you would use `%~dp0` instead of `.\` or `$PSScriptRoot` to represent the current execution directory: `pwsh -File %~dp0test.ps1 -TestParam %windir%`.</span></span> <span data-ttu-id="a177d-129">Wenn Sie stattdessen verwenden `.\test.ps1` , löst PowerShell einen Fehler aus, da der literalpfad nicht gefunden werden kann. `.\test.ps1`</span><span class="sxs-lookup"><span data-stu-id="a177d-129">If you instead used `.\test.ps1`, PowerShell would throw an error because it cannot find the literal path `.\test.ps1`</span></span>

<span data-ttu-id="a177d-130">Wenn die Skriptdatei mit einem Befehl beendet wird `exit` , wird der Prozessexitcode auf das numerische Argument festgelegt, das mit dem Befehl verwendet wird `exit` .</span><span class="sxs-lookup"><span data-stu-id="a177d-130">When the script file terminates with an `exit` command, the process exit code is set to the numeric argument used with the `exit` command.</span></span> <span data-ttu-id="a177d-131">Beim normalen beenden ist der Exitcode immer `0` .</span><span class="sxs-lookup"><span data-stu-id="a177d-131">With normal termination, the exit code is always `0`.</span></span>

<span data-ttu-id="a177d-132">Ähnlich wie `-Command` beim Auftreten eines Fehlers mit Skript Abbruch wird der Exitcode auf festgelegt `1` .</span><span class="sxs-lookup"><span data-stu-id="a177d-132">Similar to `-Command`, when a script-terminating error occurs, the exit code is set to `1`.</span></span> <span data-ttu-id="a177d-133">Anders als bei wird `-Command` die Ausführung mit <kbd>STRG</kbd>C unterbrochen, wenn der Exitcode - <kbd></kbd> ist `0` .</span><span class="sxs-lookup"><span data-stu-id="a177d-133">However, unlike with `-Command`, when the execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd> the exit code is `0`.</span></span>

### <a name="-command---c"></a><span data-ttu-id="a177d-134">-Befehl | -c</span><span class="sxs-lookup"><span data-stu-id="a177d-134">-Command | -c</span></span>

<span data-ttu-id="a177d-135">Führt die angegebenen Befehle (und alle Parameter) aus, als ob Sie an der PowerShell-Eingabeaufforderung eingegeben wurden, und wird dann beendet, es sei denn, der- `NoExit` Parameter wird angegeben.</span><span class="sxs-lookup"><span data-stu-id="a177d-135">Executes the specified commands (and any parameters) as though they were typed at the PowerShell command prompt, and then exits, unless the `NoExit` parameter is specified.</span></span>

<span data-ttu-id="a177d-136">Der Wert des **Befehls** kann `-` , ein Skriptblock oder eine Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="a177d-136">The value of **Command** can be `-`, a script block, or a string.</span></span> <span data-ttu-id="a177d-137">Wenn der Wert von **Command** ist `-` , wird der Befehls Text aus der Standardeingabe gelesen.</span><span class="sxs-lookup"><span data-stu-id="a177d-137">If the value of **Command** is `-`, the command text is read from standard input.</span></span>

<span data-ttu-id="a177d-138">Der **Command** -Parameter akzeptiert nur einen Skriptblock für die Ausführung, wenn der an den **Befehl** übergebenen Wert als **ScriptBlock** -Typ erkannt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a177d-138">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to **Command** as a **ScriptBlock** type.</span></span> <span data-ttu-id="a177d-139">Dies ist _nur_ möglich, wenn `pwsh` von einem anderen PowerShell-Host ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a177d-139">This is _only_ possible when running `pwsh` from another PowerShell host.</span></span> <span data-ttu-id="a177d-140">Der **ScriptBlock** -Typ kann in einer vorhandenen-Variable enthalten, von einem Ausdruck zurückgegeben oder vom PowerShell-Host als literaler Skriptblock in geschweiften Klammern () analysiert werden, `{}` bevor er an übergeben wird `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="a177d-140">The **ScriptBlock** type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces (`{}`), before being passed to `pwsh`.</span></span>

```powershell
pwsh -Command {Get-WinEvent -LogName security}
```

<span data-ttu-id="a177d-141">In `cmd.exe` gibt es keinen Skriptblock (oder einen **ScriptBlock** -Typ), sodass der an den **Befehl** übergeben Wert _immer_ eine Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="a177d-141">In `cmd.exe`, there is no such thing as a script block (or **ScriptBlock** type), so the value passed to **Command** will _always_ be a string.</span></span> <span data-ttu-id="a177d-142">Sie können einen Skriptblock innerhalb der Zeichenfolge schreiben, aber anstatt ausgeführt zu werden, verhält er sich genau so, als ob Sie ihn an einer typischen PowerShell-Eingabeaufforderung eingegeben hätten, wobei der Inhalt des Skriptblocks wieder an Sie ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a177d-142">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="a177d-143">Eine an den **Befehl** weiter gegebene Zeichenfolge wird weiterhin als PowerShell-Code ausgeführt, sodass die Skriptblock geschweiften Klammern bei der Ausführung von häufig nicht erforderlich sind `cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="a177d-143">A string passed to **Command** is still executed as PowerShell code, so the script block curly braces are often not required in the first place when running from `cmd.exe`.</span></span> <span data-ttu-id="a177d-144">Zum Ausführen eines Inlineskriptblocks, der in einer Zeichenfolge definiert ist, kann der [Aufrufoperator](about_operators.md#special-operators) `&` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="a177d-144">To execute an inline script block defined inside a string, the [call operator](about_operators.md#special-operators) `&` can be used:</span></span>

```
pwsh -Command "& {Get-WinEvent -LogName security}"
```

<span data-ttu-id="a177d-145">Wenn der Wert von " **Command** " eine Zeichenfolge ist, muss **Command** der letzte Parameter für "pwsh" sein, da alle nachfolgenden Argumente als Teil des auszuführenden Befehls interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="a177d-145">If the value of **Command** is a string, **Command** must be the last parameter for pwsh, because all arguments following it are interpreted as part of the command to execute.</span></span>

<span data-ttu-id="a177d-146">Wenn Sie innerhalb einer vorhandenen PowerShell-Sitzung aufgerufen werden, werden die Ergebnisse als deserialisierte XML-Objekte und nicht als Live-Objekte an die übergeordnete Shell zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a177d-146">When called from within an existing PowerShell session, the results are returned to the parent shell as deserialized XML objects, not live objects.</span></span> <span data-ttu-id="a177d-147">Bei anderen Shells werden die Ergebnisse als Zeichen folgen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a177d-147">For other shells, the results are returned as strings.</span></span>

<span data-ttu-id="a177d-148">Wenn der Wert von **Command** ist `-` , wird der Befehls Text aus der Standardeingabe gelesen.</span><span class="sxs-lookup"><span data-stu-id="a177d-148">If the value of **Command** is `-`, the command text is read from standard input.</span></span> <span data-ttu-id="a177d-149">Sie müssen die Standardeingabe umleiten, wenn Sie den **Command** -Parameter mit der Standardeingabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="a177d-149">You must redirect standard input when using the **Command** parameter with standard input.</span></span> <span data-ttu-id="a177d-150">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="a177d-150">For example:</span></span>

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

<span data-ttu-id="a177d-151">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a177d-151">This example produces the following output:</span></span>

```Output
in
hi there
out
```

<span data-ttu-id="a177d-152">Der Prozessexitcode wird durch den Status des letzten (ausgeführten) Befehls im Skriptblock bestimmt.</span><span class="sxs-lookup"><span data-stu-id="a177d-152">The process exit code is determined by status of the last (executed) command within the script block.</span></span> <span data-ttu-id="a177d-153">Der Exitcode ist, wenn den Wert hat `0` `$?` `$true` oder `1` Wenn `$?` ist `$false` .</span><span class="sxs-lookup"><span data-stu-id="a177d-153">The exit code is `0` when `$?` is `$true` or `1` when `$?` is `$false`.</span></span> <span data-ttu-id="a177d-154">Wenn der letzte Befehl ein externes Programm oder ein PowerShell-Skript ist, das explizit einen Exitcode angibt, der nicht `0` oder ist `1` , wird der Exitcode `1` für den Prozessexitcode in konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a177d-154">If the last command is an external program or a PowerShell script that explicitly sets an exit code other than `0` or `1`, that exit code is converted to `1` for process exit code.</span></span> <span data-ttu-id="a177d-155">Fügen Sie der `exit $LASTEXITCODE` Befehls Zeichenfolge oder dem Skriptblock hinzu, um den spezifischen Exitcode beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="a177d-155">To preserve the specific exit code, add `exit $LASTEXITCODE` to your command string or script block.</span></span>

<span data-ttu-id="a177d-156">Entsprechend wird der Wert 1 zurückgegeben, wenn ein Fehler mit Skript Abbruch (Runspace-abschließende), wie z `throw` . `-ErrorAction Stop` b. oder, auftritt oder wenn die Ausführung durch <kbd>STRG</kbd> - <kbd>C</kbd>unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="a177d-156">Similarly, the value 1 is returned when a script-terminating (runspace-terminating) error, such as a `throw` or `-ErrorAction Stop`, occurs or when execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd>.</span></span>

### <a name="-configurationname---config"></a><span data-ttu-id="a177d-157">-ConfigurationName | -config</span><span class="sxs-lookup"><span data-stu-id="a177d-157">-ConfigurationName | -config</span></span>

<span data-ttu-id="a177d-158">Gibt einen Konfigurations Endpunkt an, in dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a177d-158">Specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="a177d-159">Dies kann ein beliebiger Endpunkt sein, der auf dem lokalen Computer registriert ist, einschließlich der standardmäßigen PowerShell-Remoting-Endpunkte oder ein benutzerdefinierter Endpunkt, der über bestimmte Benutzer Rollen</span><span class="sxs-lookup"><span data-stu-id="a177d-159">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

<span data-ttu-id="a177d-160">Beispiel: `pwsh -ConfigurationName AdminRoles`</span><span class="sxs-lookup"><span data-stu-id="a177d-160">Example: `pwsh -ConfigurationName AdminRoles`</span></span>

### <a name="-custompipename"></a><span data-ttu-id="a177d-161">-Custompipame</span><span class="sxs-lookup"><span data-stu-id="a177d-161">-CustomPipeName</span></span>

<span data-ttu-id="a177d-162">Gibt den Namen an, der für einen zusätzlichen IPC-Server (Named Pipe) verwendet wird, der für das Debuggen und andere prozessübergreifende Kommunikation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a177d-162">Specifies the name to use for an additional IPC server (named pipe) used for debugging and other cross-process communication.</span></span> <span data-ttu-id="a177d-163">Dies bietet einen vorhersagbaren Mechanismus zum Herstellen einer Verbindung mit anderen PowerShell-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="a177d-163">This offers a predictable mechanism for connecting to other PowerShell instances.</span></span> <span data-ttu-id="a177d-164">Wird normalerweise mit dem **custompipame** -Parameter in verwendet `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="a177d-164">Typically used with the **CustomPipeName** parameter on `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="a177d-165">Dieser Parameter wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a177d-165">This parameter was introduced in PowerShell 6.2.</span></span>

<span data-ttu-id="a177d-166">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="a177d-166">For example:</span></span>

```powershell
# PowerShell instance 1
pwsh -CustomPipeName mydebugpipe
# PowerShell instance 2
Enter-PSHostProcess -CustomPipeName mydebugpipe
```

### <a name="-encodedcommand---e---ec"></a><span data-ttu-id="a177d-167">-Encodecodcommand | -e | -EC</span><span class="sxs-lookup"><span data-stu-id="a177d-167">-EncodedCommand | -e | -ec</span></span>

<span data-ttu-id="a177d-168">Akzeptiert eine Base64-codierte Zeichen folgen Version eines Befehls.</span><span class="sxs-lookup"><span data-stu-id="a177d-168">Accepts a Base64-encoded string version of a command.</span></span> <span data-ttu-id="a177d-169">Verwenden Sie diesen Parameter, um Befehle an PowerShell zu übermitteln, die komplexe, in Anführungszeichen eingefügte Zitate</span><span class="sxs-lookup"><span data-stu-id="a177d-169">Use this parameter to submit commands to PowerShell that require complex, nested quoting.</span></span> <span data-ttu-id="a177d-170">Die Base64-Darstellung muss eine UTF-16LE-codierte Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="a177d-170">The Base64 representation must be a UTF-16LE encoded string.</span></span>

<span data-ttu-id="a177d-171">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="a177d-171">For example:</span></span>

```powershell
$command = 'dir "c:\program files" '
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
pwsh -encodedcommand $encodedCommand
```

### <a name="-executionpolicy---ex---ep"></a><span data-ttu-id="a177d-172">-ExecutionPolicy | -Ex | -EP</span><span class="sxs-lookup"><span data-stu-id="a177d-172">-ExecutionPolicy | -ex | -ep</span></span>

<span data-ttu-id="a177d-173">Legt die Standard Ausführungs Richtlinie für die aktuelle Sitzung fest und speichert Sie in der `$env:PSExecutionPolicyPreference` Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="a177d-173">Sets the default execution policy for the current session and saves it in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="a177d-174">Dieser Parameter ändert nicht die permanent konfigurierten Ausführungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="a177d-174">This parameter does not change the persistently configured execution policies.</span></span>

<span data-ttu-id="a177d-175">Dieser Parameter gilt nur für Windows-Computer.</span><span class="sxs-lookup"><span data-stu-id="a177d-175">This parameter only applies to Windows computers.</span></span> <span data-ttu-id="a177d-176">Die `$env:PSExecutionPolicyPreference` Umgebungsvariable ist auf nicht-Windows-Plattformen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a177d-176">The `$env:PSExecutionPolicyPreference` environment variable does not exist on non-Windows platforms.</span></span>

### <a name="-inputformat---inp---if"></a><span data-ttu-id="a177d-177">-Input Format | -INP | -if</span><span class="sxs-lookup"><span data-stu-id="a177d-177">-InputFormat | -inp | -if</span></span>

<span data-ttu-id="a177d-178">Beschreibt das Format der Daten, die an PowerShell übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="a177d-178">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="a177d-179">Gültige Werte sind "Text" (Textzeichenfolgen) oder "XML" (serialisiertes CLIXML-Format).</span><span class="sxs-lookup"><span data-stu-id="a177d-179">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-interactive---i"></a><span data-ttu-id="a177d-180">-Interaktiv | -i</span><span class="sxs-lookup"><span data-stu-id="a177d-180">-Interactive | -i</span></span>

<span data-ttu-id="a177d-181">Stellen Sie eine interaktive Eingabeaufforderung für den Benutzer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a177d-181">Present an interactive prompt to the user.</span></span> <span data-ttu-id="a177d-182">Umgekehrt für den nicht interaktiven Parameter.</span><span class="sxs-lookup"><span data-stu-id="a177d-182">Inverse for NonInteractive parameter.</span></span>

### <a name="-login---l"></a><span data-ttu-id="a177d-183">-Login | -l</span><span class="sxs-lookup"><span data-stu-id="a177d-183">-Login | -l</span></span>

<span data-ttu-id="a177d-184">Unter Linux und macOS startet PowerShell als Anmeldungs-Shell, wobei/bin/sh zum Ausführen von Anmelde Profilen verwendet wird, z. b./etc/profile und ~/.profile.</span><span class="sxs-lookup"><span data-stu-id="a177d-184">On Linux and macOS, starts PowerShell as a login shell, using /bin/sh to execute login profiles such as /etc/profile and ~/.profile.</span></span>
<span data-ttu-id="a177d-185">Unter Windows führt dieser Switch keine Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="a177d-185">On Windows, this switch does nothing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a177d-186">Dieser Parameter muss zuerst als Anmeldungs-Shell gestartet werden, um PowerShell zu starten.</span><span class="sxs-lookup"><span data-stu-id="a177d-186">This parameter must come first to start PowerShell as a login shell.</span></span>
> <span data-ttu-id="a177d-187">Das übergeben dieses Parameters an einer anderen Position wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a177d-187">Passing this parameter in another position will be ignored.</span></span>

<span data-ttu-id="a177d-188">So richten Sie `pwsh` als Anmeldungs-Shell auf Unix-ähnlichen Betriebssystemen ein:</span><span class="sxs-lookup"><span data-stu-id="a177d-188">To set up `pwsh` as the login shell on UNIX-like operating systems:</span></span>

- <span data-ttu-id="a177d-189">Überprüfen Sie, ob der vollständige absolute Pfad zu `pwsh` unter aufgeführt ist. `/etc/shells`</span><span class="sxs-lookup"><span data-stu-id="a177d-189">Verify that the full absolute path to `pwsh` is listed under `/etc/shells`</span></span>
  - <span data-ttu-id="a177d-190">Dieser Pfad ist in der Regel etwas wie `/usr/bin/pwsh` unter Linux oder `/usr/local/bin/pwsh` macOS.</span><span class="sxs-lookup"><span data-stu-id="a177d-190">This path is usually something like `/usr/bin/pwsh` on Linux or `/usr/local/bin/pwsh` on macOS</span></span>
  - <span data-ttu-id="a177d-191">Bei einigen Installationsmethoden wird dieser Eintrag automatisch zum Installations Zeitpunkt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a177d-191">With some installation methods, this entry will be added automatically at installation time</span></span>
  - <span data-ttu-id="a177d-192">Wenn `pwsh` nicht in vorhanden ist `/etc/shells` , verwenden Sie einen Editor, um den Pfad in `pwsh` der letzten Zeile an anzufügen.</span><span class="sxs-lookup"><span data-stu-id="a177d-192">If `pwsh` is not present in `/etc/shells`, use an editor to append the path to `pwsh` on the last line.</span></span> <span data-ttu-id="a177d-193">Hierfür sind erweiterte Berechtigungen erforderlich, um zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="a177d-193">This requires elevated privileges to edit.</span></span>
- <span data-ttu-id="a177d-194">Verwenden Sie das Hilfsprogramm " [CHSH](https://linux.die.net/man/1/chsh) ", um die Shell des aktuellen Benutzers auf festzulegen `pwsh` :</span><span class="sxs-lookup"><span data-stu-id="a177d-194">Use the [chsh](https://linux.die.net/man/1/chsh) utility to set your current user's shell to `pwsh`:</span></span>

  ```sh
  chsh -s /usr/bin/pwsh
  ```

> [!WARNING]
> <span data-ttu-id="a177d-195">`pwsh`Die Einstellung als Anmeldungs-Shell wird derzeit nicht unter Windows-Subsystem für Linux (WSL) unterstützt, und der Versuch, `pwsh` als Anmeldungs-Shell festzulegen, kann dazu führen, dass WSL nicht interaktiv gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a177d-195">Setting `pwsh` as the login shell is currently not supported on Windows Subsystem for Linux (WSL), and attempting to set `pwsh` as the login shell there may lead to being unable to start WSL interactively.</span></span>

### <a name="-mta"></a><span data-ttu-id="a177d-196">-MTA</span><span class="sxs-lookup"><span data-stu-id="a177d-196">-MTA</span></span>

<span data-ttu-id="a177d-197">Starten Sie PowerShell mit einem Multithread-Apartment.</span><span class="sxs-lookup"><span data-stu-id="a177d-197">Start PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="a177d-198">Dieser Schalter ist nur unter Windows verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a177d-198">This switch is only available on Windows.</span></span>

### <a name="-noexit---noe"></a><span data-ttu-id="a177d-199">-NoExit | -Noe</span><span class="sxs-lookup"><span data-stu-id="a177d-199">-NoExit | -noe</span></span>

<span data-ttu-id="a177d-200">Nach dem Ausführen der Startbefehle erfolgt kein Beenden.</span><span class="sxs-lookup"><span data-stu-id="a177d-200">Does not exit after running startup commands.</span></span>

<span data-ttu-id="a177d-201">Beispiel: `pwsh -NoExit -Command Get-Date`</span><span class="sxs-lookup"><span data-stu-id="a177d-201">Example: `pwsh -NoExit -Command Get-Date`</span></span>

### <a name="-nologo---nol"></a><span data-ttu-id="a177d-202">-Nologo | -Nol</span><span class="sxs-lookup"><span data-stu-id="a177d-202">-NoLogo | -nol</span></span>

<span data-ttu-id="a177d-203">Blendet das Copyright Banner beim Start interaktiver Sitzungen aus.</span><span class="sxs-lookup"><span data-stu-id="a177d-203">Hides the copyright banner at startup of interactive sessions.</span></span>

### <a name="-noninteractive---noni"></a><span data-ttu-id="a177d-204">-Nicht interaktiv | -Noni</span><span class="sxs-lookup"><span data-stu-id="a177d-204">-NonInteractive | -noni</span></span>

<span data-ttu-id="a177d-205">Zeigt dem Benutzer keine interaktive Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="a177d-205">Does not present an interactive prompt to the user.</span></span> <span data-ttu-id="a177d-206">Alle Versuche, interaktive Features zu verwenden, wie z `Read-Host` . b. oder Bestätigungs Aufforderungen, führen zu Fehlern bei der Anweisungs Beendigung.</span><span class="sxs-lookup"><span data-stu-id="a177d-206">Any attempts to use interactive features, like `Read-Host` or confirmation prompts, result in statement-terminating errors.</span></span>

### <a name="-noprofile---nop"></a><span data-ttu-id="a177d-207">-NoProfile | -NOP</span><span class="sxs-lookup"><span data-stu-id="a177d-207">-NoProfile | -nop</span></span>

<span data-ttu-id="a177d-208">Die PowerShell-Profile werden nicht geladen.</span><span class="sxs-lookup"><span data-stu-id="a177d-208">Does not load the PowerShell profiles.</span></span>

### <a name="-outputformat---o---of"></a><span data-ttu-id="a177d-209">-OutputFormat | -o | -von</span><span class="sxs-lookup"><span data-stu-id="a177d-209">-OutputFormat | -o | -of</span></span>

<span data-ttu-id="a177d-210">Bestimmt, wie die Ausgabe von PowerShell formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="a177d-210">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="a177d-211">Gültige Werte sind "Text" (Textzeichenfolgen) oder "XML" (serialisiertes CLIXML-Format).</span><span class="sxs-lookup"><span data-stu-id="a177d-211">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

<span data-ttu-id="a177d-212">Beispiel: `pwsh -o XML -c Get-Date`</span><span class="sxs-lookup"><span data-stu-id="a177d-212">Example: `pwsh -o XML -c Get-Date`</span></span>

<span data-ttu-id="a177d-213">Wenn eine PowerShell-Sitzung aufgerufen wird, erhalten Sie deserialisierte Objekte als Ausgabe Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="a177d-213">When called withing a PowerShell session, you get deserialized objects as output rather plain strings.</span></span> <span data-ttu-id="a177d-214">Wenn die Ausgabe aus anderen Shells aufgerufen wird, werden Zeichen folgen Daten als CliXML-Text formatiert.</span><span class="sxs-lookup"><span data-stu-id="a177d-214">When called from other shells, the output is string data formatted as CLIXML text.</span></span>

### <a name="-settingsfile---settings"></a><span data-ttu-id="a177d-215">-SettingsFile | -Einstellungen</span><span class="sxs-lookup"><span data-stu-id="a177d-215">-SettingsFile | -settings</span></span>

<span data-ttu-id="a177d-216">Überschreibt die systemweite `powershell.config.json` Einstellungsdatei für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a177d-216">Overrides the system-wide `powershell.config.json` settings file for the session.</span></span> <span data-ttu-id="a177d-217">Standardmäßig werden systemweite Einstellungen aus dem `powershell.config.json` im `$PSHOME` Verzeichnis gelesen.</span><span class="sxs-lookup"><span data-stu-id="a177d-217">By default, system-wide settings are read from the `powershell.config.json` in the `$PSHOME` directory.</span></span>

<span data-ttu-id="a177d-218">Beachten Sie, dass diese Einstellungen nicht von dem Endpunkt verwendet werden, der durch das-Argument angegeben wird `-ConfigurationName` .</span><span class="sxs-lookup"><span data-stu-id="a177d-218">Note that these settings are not used by the endpoint specified by the `-ConfigurationName` argument.</span></span>

<span data-ttu-id="a177d-219">Beispiel: `pwsh -SettingsFile c:\myproject\powershell.config.json`</span><span class="sxs-lookup"><span data-stu-id="a177d-219">Example: `pwsh -SettingsFile c:\myproject\powershell.config.json`</span></span>

### <a name="-sshservermode---sshs"></a><span data-ttu-id="a177d-220">-Sshservermode | -SSHS</span><span class="sxs-lookup"><span data-stu-id="a177d-220">-SSHServerMode | -sshs</span></span>

<span data-ttu-id="a177d-221">Wird in sshd_config zum Ausführen von PowerShell als SSH-Subsystem verwendet.</span><span class="sxs-lookup"><span data-stu-id="a177d-221">Used in sshd_config for running PowerShell as an SSH subsystem.</span></span> <span data-ttu-id="a177d-222">Sie ist nicht für andere Zwecke vorgesehen oder wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a177d-222">It is not intended or supported for any other use.</span></span>

### <a name="-sta"></a><span data-ttu-id="a177d-223">-STA</span><span class="sxs-lookup"><span data-stu-id="a177d-223">-STA</span></span>

<span data-ttu-id="a177d-224">Starten Sie PowerShell mit einem Single Thread-Apartment.</span><span class="sxs-lookup"><span data-stu-id="a177d-224">Start PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="a177d-225">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="a177d-225">This is the default.</span></span> <span data-ttu-id="a177d-226">Dieser Schalter ist nur unter Windows verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a177d-226">This switch is only available on Windows.</span></span>

### <a name="-version---v"></a><span data-ttu-id="a177d-227">-Version | -v</span><span class="sxs-lookup"><span data-stu-id="a177d-227">-Version | -v</span></span>

<span data-ttu-id="a177d-228">Zeigt die Version von PowerShell an.</span><span class="sxs-lookup"><span data-stu-id="a177d-228">Displays the version of PowerShell.</span></span> <span data-ttu-id="a177d-229">Zusätzliche Parameter werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a177d-229">Additional parameters are ignored.</span></span>

### <a name="-windowstyle---w"></a><span data-ttu-id="a177d-230">-WindowStyle | -w</span><span class="sxs-lookup"><span data-stu-id="a177d-230">-WindowStyle | -w</span></span>

<span data-ttu-id="a177d-231">Legt den Fensterstil für die Sitzung fest.</span><span class="sxs-lookup"><span data-stu-id="a177d-231">Sets the window style for the session.</span></span> <span data-ttu-id="a177d-232">Gültige Werte sind „Normal“, „Minimized“, „Maximized“ und „Hidden“.</span><span class="sxs-lookup"><span data-stu-id="a177d-232">Valid values are Normal, Minimized, Maximized and Hidden.</span></span>

### <a name="-workingdirectory---wd"></a><span data-ttu-id="a177d-233">-WorkingDirectory | -WD</span><span class="sxs-lookup"><span data-stu-id="a177d-233">-WorkingDirectory | -wd</span></span>

<span data-ttu-id="a177d-234">Legt das anfängliche Arbeitsverzeichnis fest, indem beim Start ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a177d-234">Sets the initial working directory by executing at startup.</span></span> <span data-ttu-id="a177d-235">Jeder gültige PowerShell-Dateipfad wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a177d-235">Any valid PowerShell file path is supported.</span></span>

<span data-ttu-id="a177d-236">Verwenden Sie Folgendes, um PowerShell in Ihrem Basisverzeichnis zu starten: `pwsh -WorkingDirectory ~`</span><span class="sxs-lookup"><span data-stu-id="a177d-236">To start PowerShell in your home directory, use: `pwsh -WorkingDirectory ~`</span></span>

### <a name="-help---"></a><span data-ttu-id="a177d-237">-Help, -?, /?</span><span class="sxs-lookup"><span data-stu-id="a177d-237">-Help, -?, /?</span></span>

<span data-ttu-id="a177d-238">Zeigt die Hilfe für an `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="a177d-238">Displays help for `pwsh`.</span></span> <span data-ttu-id="a177d-239">Wenn Sie einen pwsh-Befehl in PowerShell eingeben, stellen Sie den Befehlsparametern einen Bindestrich ( `-` ) und keinen Schrägstrich () voran `/` .</span><span class="sxs-lookup"><span data-stu-id="a177d-239">If you are typing a pwsh command in PowerShell, prepend the command parameters with a hyphen (`-`), not a forward slash (`/`).</span></span>
