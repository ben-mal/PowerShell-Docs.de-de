---
description: Erläutert, wie die `pwsh` Befehlszeilenschnittstelle verwendet wird. Zeigt die Befehlszeilenparameter an und beschreibt die Syntax.
keywords: powershell,cmdlet
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pwsh?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pwsh
ms.openlocfilehash: 549c99fa618e2e53aed8945d95e92f97117aa6c9
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224655"
---
# <a name="about-pwsh"></a><span data-ttu-id="4009e-105">Informationen zu pwsh</span><span class="sxs-lookup"><span data-stu-id="4009e-105">About pwsh</span></span>

## <a name="short-description"></a><span data-ttu-id="4009e-106">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4009e-106">Short Description</span></span>
<span data-ttu-id="4009e-107">Erläutert, wie die `pwsh` Befehlszeilenschnittstelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4009e-107">Explains how to use the `pwsh` command-line interface.</span></span> <span data-ttu-id="4009e-108">Zeigt die Befehlszeilenparameter an und beschreibt die Syntax.</span><span class="sxs-lookup"><span data-stu-id="4009e-108">Displays the command-line parameters and describes the syntax.</span></span>

## <a name="long-description"></a><span data-ttu-id="4009e-109">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4009e-109">Long Description</span></span>

## <a name="syntax"></a><span data-ttu-id="4009e-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="4009e-110">Syntax</span></span>

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
   [-NoExit]
   [-NoLogo]
   [-NonInteractive]
   [-NoProfile]
   [-OutputFormat {Text | XML}]
   [-SettingsFile <SettingsFilePath>]
   [-Version]
   [-WindowStyle <style>]
   [-WorkingDirectory <directoryPath>]

pwsh[.exe] -h | -Help | -? | /?
```

## <a name="parameters"></a><span data-ttu-id="4009e-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="4009e-111">Parameters</span></span>

<span data-ttu-id="4009e-112">Bei allen Parametern wird die Groß-/Kleinschreibung beachtet</span><span class="sxs-lookup"><span data-stu-id="4009e-112">All parameters are case-insensitive.</span></span>

### <a name="-file---f"></a><span data-ttu-id="4009e-113">-Datei | -f</span><span class="sxs-lookup"><span data-stu-id="4009e-113">-File | -f</span></span>

<span data-ttu-id="4009e-114">Wenn der Wert von `File` ist `-` , wird der Befehls Text aus der Standardeingabe gelesen.</span><span class="sxs-lookup"><span data-stu-id="4009e-114">If the value of `File` is `-`, the command text is read from standard input.</span></span>
<span data-ttu-id="4009e-115">Wenn Sie `pwsh -File -` ohne umgeleitete Standardeingabe ausführen, wird eine reguläre Sitzung gestartet.</span><span class="sxs-lookup"><span data-stu-id="4009e-115">Running `pwsh -File -` without redirected standard input starts a regular session.</span></span> <span data-ttu-id="4009e-116">Dies ist das gleiche wie bei der Angabe des `File` Parameters überhaupt nicht.</span><span class="sxs-lookup"><span data-stu-id="4009e-116">This is the same as not specifying the `File` parameter at all.</span></span>

<span data-ttu-id="4009e-117">Dies ist der Standardparameter, wenn keine Parameter vorhanden sind, aber Werte in der Befehlszeile vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="4009e-117">This is the default parameter if no parameters are present but values are present in the command line.</span></span> <span data-ttu-id="4009e-118">Das angegebene Skript wird im lokalen Gültigkeitsbereich ("Punkt-Source") ausgeführt, sodass die Funktionen und Variablen, die das Skript erstellt, in der aktuellen Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4009e-118">The specified script runs in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="4009e-119">Geben Sie den Pfad der Skriptdatei und Parameter an.</span><span class="sxs-lookup"><span data-stu-id="4009e-119">Enter the script file path and any parameters.</span></span> <span data-ttu-id="4009e-120">File muss der letzte Parameter im Befehl sein, da alle Zeichen, die nach dem Datei Parameternamen eingegeben werden, als Pfad der Skriptdatei gefolgt von den Skript Parametern interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="4009e-120">File must be the last parameter in the command, because all characters typed after the File parameter name are interpreted as the script file path followed by the script parameters.</span></span>

<span data-ttu-id="4009e-121">Die Switch-Parameter eines Skripts werden in der Regel entweder einbezogen oder ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="4009e-121">Typically, the switch parameters of a script are either included or omitted.</span></span>
<span data-ttu-id="4009e-122">Der folgende Befehl verwendet beispielsweise den All-Parameter der Get-Script.ps1 Skriptdatei: `-File .\Get-Script.ps1 -All`</span><span class="sxs-lookup"><span data-stu-id="4009e-122">For example, the following command uses the All parameter of the Get-Script.ps1 script file: `-File .\Get-Script.ps1 -All`</span></span>

<span data-ttu-id="4009e-123">In seltenen Fällen müssen Sie möglicherweise einen **booleschen** Wert für einen Switch-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="4009e-123">In rare cases, you might need to provide a **Boolean** value for a switch parameter.</span></span> <span data-ttu-id="4009e-124">Um einen **booleschen** Wert für einen Switch-Parameter im Wert des **File** -Parameters anzugeben, verwenden Sie den-Parameter, der normalerweise von einem Doppelpunkt und dem booleschen Wert gefolgt wird, z `-File .\Get-Script.ps1 -All:$False` . b.:.</span><span class="sxs-lookup"><span data-stu-id="4009e-124">To provide a **Boolean** value for a switch parameter in the value of the **File** parameter, Use the parameter normally followed immediately by a colon and the boolean value, such as the following: `-File .\Get-Script.ps1 -All:$False`.</span></span>

<span data-ttu-id="4009e-125">Parameter, die an das Skript übergeben werden, werden als Zeichenfolgenliterale übergeben (nach der Interpretation durch die aktuelle Shell).</span><span class="sxs-lookup"><span data-stu-id="4009e-125">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="4009e-126">Wenn Sie z. b. `cmd.exe` verwenden und einen Umgebungsvariablen Wert übergeben möchten, verwenden Sie die folgende `cmd.exe` Syntax: `pwsh -File .\test.ps1 -TestParam %windir%`</span><span class="sxs-lookup"><span data-stu-id="4009e-126">For example, if you are in `cmd.exe` and want to pass an environment variable value, you would use the `cmd.exe` syntax: `pwsh -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="4009e-127">Im Gegensatz dazu `pwsh -File .\test.ps1 -TestParam $env:windir` führt das Ausführen von in dazu, `cmd.exe` dass das Skript die Literalzeichenfolge empfängt, `$env:windir` da es für die aktuelle Shell keine besondere Bedeutung hat `cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="4009e-127">In contrast, running `pwsh -File .\test.ps1 -TestParam $env:windir` in `cmd.exe` results in the script receiving the literal string `$env:windir` because it has no special meaning to the current `cmd.exe` shell.</span></span> <span data-ttu-id="4009e-128">Der `$env:windir` Stil der Umgebungsvariablen Referenz _kann_ innerhalb eines **Befehls** Parameters verwendet werden, da er als PowerShell-Code interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="4009e-128">The `$env:windir` style of environment variable reference _can_ be used inside a **Command** parameter, since there it is interpreted as PowerShell code.</span></span>

<span data-ttu-id="4009e-129">Wenn Sie denselben Befehl aus einem _Batch Skript_ ausführen möchten, verwenden Sie auch `%~dp0` anstelle von `.\` oder, `$PSScriptRoot` um das aktuelle Ausführungs Verzeichnis darzustellen: `pwsh -File %~dp0test.ps1 -TestParam %windir%` .</span><span class="sxs-lookup"><span data-stu-id="4009e-129">Similarly, if you want to execute the same command from a _Batch script_ , you would use `%~dp0` instead of `.\` or `$PSScriptRoot` to represent the current execution directory: `pwsh -File %~dp0test.ps1 -TestParam %windir%`.</span></span> <span data-ttu-id="4009e-130">Wenn Sie stattdessen verwenden `.\test.ps1` , löst PowerShell einen Fehler aus, da der literalpfad nicht gefunden werden kann. `.\test.ps1`</span><span class="sxs-lookup"><span data-stu-id="4009e-130">If you instead used `.\test.ps1`, PowerShell would throw an error because it cannot find the literal path `.\test.ps1`</span></span>

<span data-ttu-id="4009e-131">Wenn die Skriptdatei mit einem Befehl beendet wird `exit` , wird der Prozessexitcode auf das numerische Argument festgelegt, das mit dem Befehl verwendet wird `exit` .</span><span class="sxs-lookup"><span data-stu-id="4009e-131">When the script file terminates with an `exit` command, the process exit code is set to the numeric argument used with the `exit` command.</span></span> <span data-ttu-id="4009e-132">Beim normalen beenden ist der Exitcode immer `0` .</span><span class="sxs-lookup"><span data-stu-id="4009e-132">With normal termination, the exit code is always `0`.</span></span>

<span data-ttu-id="4009e-133">Ähnlich wie `-Command` beim Auftreten eines Fehlers mit Skript Abbruch wird der Exitcode auf festgelegt `1` .</span><span class="sxs-lookup"><span data-stu-id="4009e-133">Similar to `-Command`, when a script-terminating error occurs, the exit code is set to `1`.</span></span> <span data-ttu-id="4009e-134">Anders als bei wird `-Command` die Ausführung mit <kbd>STRG</kbd>C unterbrochen, wenn der Exitcode - <kbd>C</kbd> ist `0` .</span><span class="sxs-lookup"><span data-stu-id="4009e-134">However, unlike with `-Command`, when the execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd> the exit code is `0`.</span></span>

### <a name="-command---c"></a><span data-ttu-id="4009e-135">-Befehl | -c</span><span class="sxs-lookup"><span data-stu-id="4009e-135">-Command | -c</span></span>

<span data-ttu-id="4009e-136">Führt die angegebenen Befehle (und alle Parameter) aus, als ob Sie an der PowerShell-Eingabeaufforderung eingegeben wurden, und wird dann beendet, es sei denn, der- `NoExit` Parameter wird angegeben.</span><span class="sxs-lookup"><span data-stu-id="4009e-136">Executes the specified commands (and any parameters) as though they were typed at the PowerShell command prompt, and then exits, unless the `NoExit` parameter is specified.</span></span>

<span data-ttu-id="4009e-137">Der Wert des **Befehls** kann `-` , ein Skriptblock oder eine Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="4009e-137">The value of **Command** can be `-`, a script block, or a string.</span></span> <span data-ttu-id="4009e-138">Wenn der Wert von **Command** ist `-` , wird der Befehls Text aus der Standardeingabe gelesen.</span><span class="sxs-lookup"><span data-stu-id="4009e-138">If the value of **Command** is `-`, the command text is read from standard input.</span></span>

<span data-ttu-id="4009e-139">Der **Command** -Parameter akzeptiert nur einen Skriptblock für die Ausführung, wenn der an den **Befehl** übergebenen Wert als **ScriptBlock** -Typ erkannt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4009e-139">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to **Command** as a **ScriptBlock** type.</span></span> <span data-ttu-id="4009e-140">Dies ist _nur_ möglich, wenn `pwsh` von einem anderen PowerShell-Host ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4009e-140">This is _only_ possible when running `pwsh` from another PowerShell host.</span></span> <span data-ttu-id="4009e-141">Der **ScriptBlock** -Typ kann in einer vorhandenen-Variable enthalten, von einem Ausdruck zurückgegeben oder vom PowerShell-Host als literaler Skriptblock in geschweiften Klammern () analysiert werden, `{}` bevor er an übergeben wird `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="4009e-141">The **ScriptBlock** type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces (`{}`), before being passed to `pwsh`.</span></span>

```powershell
pwsh -Command {Get-WinEvent -LogName security}
```

<span data-ttu-id="4009e-142">In `cmd.exe` gibt es keinen Skriptblock (oder einen **ScriptBlock** -Typ), sodass der an den **Befehl** übergeben Wert _immer_ eine Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="4009e-142">In `cmd.exe`, there is no such thing as a script block (or **ScriptBlock** type), so the value passed to **Command** will _always_ be a string.</span></span> <span data-ttu-id="4009e-143">Sie können einen Skriptblock innerhalb der Zeichenfolge schreiben, aber anstatt ausgeführt zu werden, verhält er sich genau so, als ob Sie ihn an einer typischen PowerShell-Eingabeaufforderung eingegeben hätten, wobei der Inhalt des Skriptblocks wieder an Sie ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4009e-143">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="4009e-144">Eine an den **Befehl** weiter gegebene Zeichenfolge wird weiterhin als PowerShell-Code ausgeführt, sodass die Skriptblock geschweiften Klammern bei der Ausführung von häufig nicht erforderlich sind `cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="4009e-144">A string passed to **Command** is still executed as PowerShell code, so the script block curly braces are often not required in the first place when running from `cmd.exe`.</span></span> <span data-ttu-id="4009e-145">Zum Ausführen eines Inlineskriptblocks, der in einer Zeichenfolge definiert ist, kann der [Aufrufoperator](about_operators.md#special-operators) `&` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="4009e-145">To execute an inline script block defined inside a string, the [call operator](about_operators.md#special-operators) `&` can be used:</span></span>

```
pwsh -Command "& {Get-WinEvent -LogName security}"
```

<span data-ttu-id="4009e-146">Wenn der Wert von " **Command** " eine Zeichenfolge ist, muss **Command** der letzte Parameter für "pwsh" sein, da alle nachfolgenden Argumente als Teil des auszuführenden Befehls interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="4009e-146">If the value of **Command** is a string, **Command** must be the last parameter for pwsh, because all arguments following it are interpreted as part of the command to execute.</span></span>

<span data-ttu-id="4009e-147">Wenn Sie innerhalb einer vorhandenen PowerShell-Sitzung aufgerufen werden, werden die Ergebnisse als deserialisierte XML-Objekte und nicht als Live-Objekte an die übergeordnete Shell zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4009e-147">When called from within an existing PowerShell session, the results are returned to the parent shell as deserialized XML objects, not live objects.</span></span> <span data-ttu-id="4009e-148">Bei anderen Shells werden die Ergebnisse als Zeichen folgen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4009e-148">For other shells, the results are returned as strings.</span></span>

<span data-ttu-id="4009e-149">Wenn der Wert von **Command** ist `-` , wird der Befehls Text aus der Standardeingabe gelesen.</span><span class="sxs-lookup"><span data-stu-id="4009e-149">If the value of **Command** is `-`, the command text is read from standard input.</span></span> <span data-ttu-id="4009e-150">Sie müssen die Standardeingabe umleiten, wenn Sie den **Command** -Parameter mit der Standardeingabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="4009e-150">You must redirect standard input when using the **Command** parameter with standard input.</span></span> <span data-ttu-id="4009e-151">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4009e-151">For example:</span></span>

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

<span data-ttu-id="4009e-152">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="4009e-152">This example produces the following output:</span></span>

```Output
in
hi there
out
```

<span data-ttu-id="4009e-153">Der Prozessexitcode wird durch den Status des letzten (ausgeführten) Befehls im Skriptblock bestimmt.</span><span class="sxs-lookup"><span data-stu-id="4009e-153">The process exit code is determined by status of the last (executed) command within the script block.</span></span> <span data-ttu-id="4009e-154">Der Exitcode ist, wenn den Wert hat `0` `$?` `$true` oder `1` Wenn `$?` ist `$false` .</span><span class="sxs-lookup"><span data-stu-id="4009e-154">The exit code is `0` when `$?` is `$true` or `1` when `$?` is `$false`.</span></span> <span data-ttu-id="4009e-155">Wenn der letzte Befehl ein externes Programm oder ein PowerShell-Skript ist, das explizit einen Exitcode angibt, der nicht `0` oder ist `1` , wird der Exitcode `1` für den Prozessexitcode in konvertiert.</span><span class="sxs-lookup"><span data-stu-id="4009e-155">If the last command is an external program or a PowerShell script that explicitly sets an exit code other than `0` or `1`, that exit code is converted to `1` for process exit code.</span></span> <span data-ttu-id="4009e-156">Fügen Sie der `exit $LASTEXITCODE` Befehls Zeichenfolge oder dem Skriptblock hinzu, um den spezifischen Exitcode beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="4009e-156">To preserve the specific exit code, add `exit $LASTEXITCODE` to your command string or script block.</span></span>

<span data-ttu-id="4009e-157">Entsprechend wird der Wert 1 zurückgegeben, wenn ein Fehler mit Skript Abbruch (Runspace-abschließende), wie z `throw` . `-ErrorAction Stop` b. oder, auftritt oder wenn die Ausführung durch <kbd>STRG</kbd> - <kbd>C</kbd>unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="4009e-157">Similarly, the value 1 is returned when a script-terminating (runspace-terminating) error, such as a `throw` or `-ErrorAction Stop`, occurs or when execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd>.</span></span>

### <a name="-configurationname---config"></a><span data-ttu-id="4009e-158">-ConfigurationName | -config</span><span class="sxs-lookup"><span data-stu-id="4009e-158">-ConfigurationName | -config</span></span>

<span data-ttu-id="4009e-159">Gibt einen Konfigurations Endpunkt an, in dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4009e-159">Specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="4009e-160">Dies kann ein beliebiger Endpunkt sein, der auf dem lokalen Computer registriert ist, einschließlich der standardmäßigen PowerShell-Remoting-Endpunkte oder ein benutzerdefinierter Endpunkt, der über bestimmte Benutzer Rollen</span><span class="sxs-lookup"><span data-stu-id="4009e-160">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

<span data-ttu-id="4009e-161">Beispiel: `pwsh -ConfigurationName AdminRoles`</span><span class="sxs-lookup"><span data-stu-id="4009e-161">Example: `pwsh -ConfigurationName AdminRoles`</span></span>

### <a name="-custompipename"></a><span data-ttu-id="4009e-162">-Custompipame</span><span class="sxs-lookup"><span data-stu-id="4009e-162">-CustomPipeName</span></span>

<span data-ttu-id="4009e-163">Gibt den Namen an, der für einen zusätzlichen IPC-Server (Named Pipe) verwendet wird, der für das Debuggen und andere prozessübergreifende Kommunikation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4009e-163">Specifies the name to use for an additional IPC server (named pipe) used for debugging and other cross-process communication.</span></span> <span data-ttu-id="4009e-164">Dies bietet einen vorhersagbaren Mechanismus zum Herstellen einer Verbindung mit anderen PowerShell-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="4009e-164">This offers a predictable mechanism for connecting to other PowerShell instances.</span></span> <span data-ttu-id="4009e-165">Wird normalerweise mit dem **custompipame** -Parameter in verwendet `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="4009e-165">Typically used with the **CustomPipeName** parameter on `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="4009e-166">Dieser Parameter wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4009e-166">This parameter was introduced in PowerShell 6.2.</span></span>

<span data-ttu-id="4009e-167">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4009e-167">For example:</span></span>

```powershell
# PowerShell instance 1
pwsh -CustomPipeName mydebugpipe
# PowerShell instance 2
Enter-PSHostProcess -CustomPipeName mydebugpipe
```

### <a name="-encodedcommand---e---ec"></a><span data-ttu-id="4009e-168">-Encodecodcommand | -e | -EC</span><span class="sxs-lookup"><span data-stu-id="4009e-168">-EncodedCommand | -e | -ec</span></span>

<span data-ttu-id="4009e-169">Akzeptiert eine Base64-codierte Zeichen folgen Version eines Befehls.</span><span class="sxs-lookup"><span data-stu-id="4009e-169">Accepts a Base64-encoded string version of a command.</span></span> <span data-ttu-id="4009e-170">Verwenden Sie diesen Parameter, um Befehle an PowerShell zu übermitteln, die komplexe, in Anführungszeichen eingefügte Zitate</span><span class="sxs-lookup"><span data-stu-id="4009e-170">Use this parameter to submit commands to PowerShell that require complex, nested quoting.</span></span> <span data-ttu-id="4009e-171">Die Base64-Darstellung muss eine UTF-16-codierte Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="4009e-171">The Base64 representation must be a UTF-16 encoded string.</span></span>

<span data-ttu-id="4009e-172">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4009e-172">For example:</span></span>

```powershell
$command = 'dir "c:\program files" '
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
pwsh -encodedcommand $encodedCommand
```

### <a name="-executionpolicy---ex---ep"></a><span data-ttu-id="4009e-173">-ExecutionPolicy | -Ex | -EP</span><span class="sxs-lookup"><span data-stu-id="4009e-173">-ExecutionPolicy | -ex | -ep</span></span>

<span data-ttu-id="4009e-174">Legt die Standard Ausführungs Richtlinie für die aktuelle Sitzung fest und speichert Sie in der `$env:PSExecutionPolicyPreference` Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="4009e-174">Sets the default execution policy for the current session and saves it in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="4009e-175">Dieser Parameter ändert nicht die permanent konfigurierten Ausführungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="4009e-175">This parameter does not change the persistently configured execution policies.</span></span>

<span data-ttu-id="4009e-176">Dieser Parameter gilt nur für Windows-Computer.</span><span class="sxs-lookup"><span data-stu-id="4009e-176">This parameter only applies to Windows computers.</span></span> <span data-ttu-id="4009e-177">Die `$env:PSExecutionPolicyPreference` Umgebungsvariable ist auf nicht-Windows-Plattformen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4009e-177">The `$env:PSExecutionPolicyPreference` environment variable does not exist on non-Windows platforms.</span></span>

### <a name="-inputformat---in---if"></a><span data-ttu-id="4009e-178">-Input Format | -in | -if</span><span class="sxs-lookup"><span data-stu-id="4009e-178">-InputFormat | -in | -if</span></span>

<span data-ttu-id="4009e-179">Beschreibt das Format der Daten, die an PowerShell übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="4009e-179">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="4009e-180">Gültige Werte sind "Text" (Textzeichenfolgen) oder "XML" (serialisiertes CLIXML-Format).</span><span class="sxs-lookup"><span data-stu-id="4009e-180">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-interactive---i"></a><span data-ttu-id="4009e-181">-Interaktiv | -i</span><span class="sxs-lookup"><span data-stu-id="4009e-181">-Interactive | -i</span></span>

<span data-ttu-id="4009e-182">Stellen Sie eine interaktive Eingabeaufforderung für den Benutzer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4009e-182">Present an interactive prompt to the user.</span></span> <span data-ttu-id="4009e-183">Umgekehrt für den nicht interaktiven Parameter.</span><span class="sxs-lookup"><span data-stu-id="4009e-183">Inverse for NonInteractive parameter.</span></span>

### <a name="-noexit---noe"></a><span data-ttu-id="4009e-184">-NoExit | -Noe</span><span class="sxs-lookup"><span data-stu-id="4009e-184">-NoExit | -noe</span></span>

<span data-ttu-id="4009e-185">Nach dem Ausführen der Startbefehle erfolgt kein Beenden.</span><span class="sxs-lookup"><span data-stu-id="4009e-185">Does not exit after running startup commands.</span></span>

<span data-ttu-id="4009e-186">Beispiel: `pwsh -NoExit -Command Get-Date`</span><span class="sxs-lookup"><span data-stu-id="4009e-186">Example: `pwsh -NoExit -Command Get-Date`</span></span>

### <a name="-nologo---nol"></a><span data-ttu-id="4009e-187">-Nologo | -Nol</span><span class="sxs-lookup"><span data-stu-id="4009e-187">-NoLogo | -nol</span></span>

<span data-ttu-id="4009e-188">Blendet das Copyright Banner beim Start interaktiver Sitzungen aus.</span><span class="sxs-lookup"><span data-stu-id="4009e-188">Hides the copyright banner at startup of interactive sessions.</span></span>

### <a name="-noninteractive---noni"></a><span data-ttu-id="4009e-189">-Nicht interaktiv | -Noni</span><span class="sxs-lookup"><span data-stu-id="4009e-189">-NonInteractive | -noni</span></span>

<span data-ttu-id="4009e-190">Zeigt dem Benutzer keine interaktive Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="4009e-190">Does not present an interactive prompt to the user.</span></span> <span data-ttu-id="4009e-191">Alle Versuche, interaktive Features zu verwenden, wie z `Read-Host` . b. oder Bestätigungs Aufforderungen, führen zu Fehlern bei der Anweisungs Beendigung.</span><span class="sxs-lookup"><span data-stu-id="4009e-191">Any attempts to use interactive features, like `Read-Host` or confirmation prompts, result in statement-terminating errors.</span></span>

### <a name="-noprofile---nop"></a><span data-ttu-id="4009e-192">-NoProfile | -NOP</span><span class="sxs-lookup"><span data-stu-id="4009e-192">-NoProfile | -nop</span></span>

<span data-ttu-id="4009e-193">Die PowerShell-Profile werden nicht geladen.</span><span class="sxs-lookup"><span data-stu-id="4009e-193">Does not load the PowerShell profiles.</span></span>

### <a name="-outputformat---o---of"></a><span data-ttu-id="4009e-194">-OutputFormat | -o | -von</span><span class="sxs-lookup"><span data-stu-id="4009e-194">-OutputFormat | -o | -of</span></span>

<span data-ttu-id="4009e-195">Bestimmt, wie die Ausgabe von PowerShell formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="4009e-195">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="4009e-196">Gültige Werte sind "Text" (Textzeichenfolgen) oder "XML" (serialisiertes CLIXML-Format).</span><span class="sxs-lookup"><span data-stu-id="4009e-196">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

<span data-ttu-id="4009e-197">Beispiel: `pwsh -o XML -c Get-Date`</span><span class="sxs-lookup"><span data-stu-id="4009e-197">Example: `pwsh -o XML -c Get-Date`</span></span>

<span data-ttu-id="4009e-198">Wenn eine PowerShell-Sitzung aufgerufen wird, erhalten Sie deserialisierte Objekte als Ausgabe Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="4009e-198">When called withing a PowerShell session, you get deserialized objects as output rather plain strings.</span></span> <span data-ttu-id="4009e-199">Wenn die Ausgabe aus anderen Shells aufgerufen wird, werden Zeichen folgen Daten als CliXML-Text formatiert.</span><span class="sxs-lookup"><span data-stu-id="4009e-199">When called from other shells, the output is string data formatted as CLIXML text.</span></span>

### <a name="-settingsfile---settings"></a><span data-ttu-id="4009e-200">-SettingsFile | -Einstellungen</span><span class="sxs-lookup"><span data-stu-id="4009e-200">-SettingsFile | -settings</span></span>

<span data-ttu-id="4009e-201">Überschreibt die systemweite `powershell.config.json` Einstellungsdatei für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4009e-201">Overrides the system-wide `powershell.config.json` settings file for the session.</span></span> <span data-ttu-id="4009e-202">Standardmäßig werden systemweite Einstellungen aus dem `powershell.config.json` im `$PSHOME` Verzeichnis gelesen.</span><span class="sxs-lookup"><span data-stu-id="4009e-202">By default, system-wide settings are read from the `powershell.config.json` in the `$PSHOME` directory.</span></span>

<span data-ttu-id="4009e-203">Beachten Sie, dass diese Einstellungen nicht von dem Endpunkt verwendet werden, der durch das-Argument angegeben wird `-ConfigurationName` .</span><span class="sxs-lookup"><span data-stu-id="4009e-203">Note that these settings are not used by the endpoint specified by the `-ConfigurationName` argument.</span></span>

<span data-ttu-id="4009e-204">Beispiel: `pwsh -SettingsFile c:\myproject\powershell.config.json`</span><span class="sxs-lookup"><span data-stu-id="4009e-204">Example: `pwsh -SettingsFile c:\myproject\powershell.config.json`</span></span>

### <a name="-sshservermode---sshs"></a><span data-ttu-id="4009e-205">-Sshservermode | -SSHS</span><span class="sxs-lookup"><span data-stu-id="4009e-205">-SSHServerMode | -sshs</span></span>

<span data-ttu-id="4009e-206">Wird in sshd_config zum Ausführen von PowerShell als SSH-Subsystem verwendet.</span><span class="sxs-lookup"><span data-stu-id="4009e-206">Used in sshd_config for running PowerShell as an SSH subsystem.</span></span> <span data-ttu-id="4009e-207">Sie ist nicht für andere Zwecke vorgesehen oder wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4009e-207">It is not intended or supported for any other use.</span></span>

### <a name="-version---v"></a><span data-ttu-id="4009e-208">-Version | -v</span><span class="sxs-lookup"><span data-stu-id="4009e-208">-Version | -v</span></span>

<span data-ttu-id="4009e-209">Zeigt die Version von PowerShell an.</span><span class="sxs-lookup"><span data-stu-id="4009e-209">Displays the version of PowerShell.</span></span> <span data-ttu-id="4009e-210">Zusätzliche Parameter werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="4009e-210">Additional parameters are ignored.</span></span>

### <a name="-windowstyle---w"></a><span data-ttu-id="4009e-211">-WindowStyle | -w</span><span class="sxs-lookup"><span data-stu-id="4009e-211">-WindowStyle | -w</span></span>

<span data-ttu-id="4009e-212">Legt den Fensterstil für die Sitzung fest.</span><span class="sxs-lookup"><span data-stu-id="4009e-212">Sets the window style for the session.</span></span> <span data-ttu-id="4009e-213">Gültige Werte sind „Normal“, „Minimized“, „Maximized“ und „Hidden“.</span><span class="sxs-lookup"><span data-stu-id="4009e-213">Valid values are Normal, Minimized, Maximized and Hidden.</span></span>

### <a name="-workingdirectory---wd"></a><span data-ttu-id="4009e-214">-WorkingDirectory | -WD</span><span class="sxs-lookup"><span data-stu-id="4009e-214">-WorkingDirectory | -wd</span></span>

<span data-ttu-id="4009e-215">Legt das anfängliche Arbeitsverzeichnis fest, indem beim Start ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4009e-215">Sets the initial working directory by executing at startup.</span></span> <span data-ttu-id="4009e-216">Jeder gültige PowerShell-Dateipfad wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4009e-216">Any valid PowerShell file path is supported.</span></span>

<span data-ttu-id="4009e-217">Verwenden Sie Folgendes, um PowerShell in Ihrem Basisverzeichnis zu starten: `pwsh -WorkingDirectory ~`</span><span class="sxs-lookup"><span data-stu-id="4009e-217">To start PowerShell in your home directory, use: `pwsh -WorkingDirectory ~`</span></span>

### <a name="-help---"></a><span data-ttu-id="4009e-218">-Help, -?, /?</span><span class="sxs-lookup"><span data-stu-id="4009e-218">-Help, -?, /?</span></span>

<span data-ttu-id="4009e-219">Zeigt die Hilfe für an `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="4009e-219">Displays help for `pwsh`.</span></span> <span data-ttu-id="4009e-220">Wenn Sie einen pwsh-Befehl in PowerShell eingeben, stellen Sie den Befehlsparametern einen Bindestrich ( `-` ) und keinen Schrägstrich () voran `/` .</span><span class="sxs-lookup"><span data-stu-id="4009e-220">If you are typing a pwsh command in PowerShell, prepend the command parameters with a hyphen (`-`), not a forward slash (`/`).</span></span>
