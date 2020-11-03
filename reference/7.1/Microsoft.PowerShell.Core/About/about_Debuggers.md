---
description: Beschreibt den PowerShell-Debugger.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 08/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_debuggers?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Debuggers
ms.openlocfilehash: 6765c33e4508e19dfca7f291f8452f1bb4730747
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222116"
---
# <a name="about-debuggers"></a><span data-ttu-id="0e754-104">Informationen zu buggern</span><span class="sxs-lookup"><span data-stu-id="0e754-104">About Debuggers</span></span>

## <a name="short-description"></a><span data-ttu-id="0e754-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0e754-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="0e754-106">Beschreibt den PowerShell-Debugger.</span><span class="sxs-lookup"><span data-stu-id="0e754-106">Describes the PowerShell debugger.</span></span>

## <a name="long-description"></a><span data-ttu-id="0e754-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0e754-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="0e754-108">Beim Debuggen wird ein Skript überprüft, während es ausgeführt wird, um Fehler in den Skript Anweisungen zu identifizieren und zu korrigieren.</span><span class="sxs-lookup"><span data-stu-id="0e754-108">Debugging is the process of examining a script while it is running to identify and correct errors in the script instructions.</span></span> <span data-ttu-id="0e754-109">Der PowerShell-Debugger unterstützt Sie bei der Untersuchung und Identifizierung von Fehlern und Ineffizienzen in Ihren Skripts, Funktionen, Befehlen, PowerShell DSC-Konfigurationen (DSC) oder Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="0e754-109">The PowerShell debugger can help you examine and identify errors and inefficiencies in your scripts, functions, commands, PowerShell Desired State Configuration (DSC) configurations, or expressions.</span></span>

<span data-ttu-id="0e754-110">Ab PowerShell 5,0 wurde der PowerShell-Debugger aktualisiert, um Skripts, Funktionen, Befehle, Konfigurationen oder Ausdrücke zu debuggen, die entweder in der-Konsole oder in Windows PowerShell ISE auf Remote Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0e754-110">Starting in PowerShell 5.0, the PowerShell debugger has been updated to debug scripts, functions, commands, configurations, or expressions that are running in either the console or Windows PowerShell ISE on remote computers.</span></span> <span data-ttu-id="0e754-111">Sie können ausführen `Enter-PSSession` , um eine interaktive PowerShell-Remote Sitzung zu starten, in der Sie Breakpoints festlegen und Skriptdateien und-Befehle auf dem Remote Computer debuggen können.</span><span class="sxs-lookup"><span data-stu-id="0e754-111">You can run `Enter-PSSession` to start an interactive remote PowerShell session in which you can set breakpoints and debug script files and commands on the remote computer.</span></span> <span data-ttu-id="0e754-112">`Enter-PSSession` die Funktionalität wurde aktualisiert, damit Sie erneut eine Verbindung mit herstellen und eine getrennte Sitzung eingeben können, die ein Skript oder einen Befehl auf einem Remote Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="0e754-112">`Enter-PSSession` functionality has been updated to let you reconnect to and enter a disconnected session that is running a script or command on a remote computer.</span></span> <span data-ttu-id="0e754-113">Wenn das Skript, das ausgeführt wird, auf einen Haltepunkt trifft, wird der Debugger automatisch von der Client Sitzung gestartet.</span><span class="sxs-lookup"><span data-stu-id="0e754-113">If the running script hits a breakpoint, your client session automatically starts the debugger.</span></span> <span data-ttu-id="0e754-114">Wenn die getrennte Sitzung, von der ein Skript ausgeführt wird, bereits einen Haltepunkt erreichen und am Haltepunkt angehalten wurde, `Enter-PSSession` startet automatisch den Befehlszeilen Debugger, nachdem Sie die Verbindung mit der Sitzung wieder hergestellt haben.</span><span class="sxs-lookup"><span data-stu-id="0e754-114">If the disconnected session that is running a script has already hit a breakpoint, and is stopped at the breakpoint, `Enter-PSSession` automatically starts the command-line debugger, after you reconnect to the session.</span></span>

<span data-ttu-id="0e754-115">Sie können die Funktionen des PowerShell-Debuggers verwenden, um ein PowerShell-Skript, eine Funktion, einen Befehl oder einen Ausdruck während der Ausführung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0e754-115">You can use the features of the PowerShell debugger to examine a PowerShell script, function, command, or expression while it is running.</span></span> <span data-ttu-id="0e754-116">Der PowerShell-Debugger enthält eine Reihe von Cmdlets, mit denen Sie Breakpoints festlegen, Breakpoints verwalten und die-aufrufsstapel anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="0e754-116">The PowerShell debugger includes a set of cmdlets that let you set breakpoints, manage breakpoints, and view the call stack.</span></span>

## <a name="debugger-cmdlets"></a><span data-ttu-id="0e754-117">Debugger-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0e754-117">Debugger Cmdlets</span></span>

<span data-ttu-id="0e754-118">Der PowerShell-Debugger umfasst die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="0e754-118">The PowerShell debugger includes the following set of cmdlets:</span></span>

- <span data-ttu-id="0e754-119">`Set-PSBreakpoint`: Legt Breakpoints für Zeilen, Variablen und Befehle fest.</span><span class="sxs-lookup"><span data-stu-id="0e754-119">`Set-PSBreakpoint`: Sets breakpoints on lines, variables, and commands.</span></span>
- <span data-ttu-id="0e754-120">`Get-PSBreakpoint`: Ruft Breakpoints in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="0e754-120">`Get-PSBreakpoint`: Gets breakpoints in the current session.</span></span>
- <span data-ttu-id="0e754-121">`Disable-PSBreakpoint`: Deaktiviert Breakpoints in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0e754-121">`Disable-PSBreakpoint`: Turns off breakpoints in the current session.</span></span>
- <span data-ttu-id="0e754-122">`Enable-PSBreakpoint`: Aktiviert Breakpoints in der aktuellen Sitzung erneut.</span><span class="sxs-lookup"><span data-stu-id="0e754-122">`Enable-PSBreakpoint`: Re-enables breakpoints in the current session.</span></span>
- <span data-ttu-id="0e754-123">`Remove-PSBreakpoint`: Löscht Haltepunkte aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0e754-123">`Remove-PSBreakpoint`: Deletes breakpoints from the current session.</span></span>
- <span data-ttu-id="0e754-124">`Get-PSCallStack`: Zeigt die aktuelle-aufrufsstapel an.</span><span class="sxs-lookup"><span data-stu-id="0e754-124">`Get-PSCallStack`: Displays the current call stack.</span></span>

## <a name="starting-and-stopping-the-debugger"></a><span data-ttu-id="0e754-125">Starten und Beenden des Debuggers</span><span class="sxs-lookup"><span data-stu-id="0e754-125">Starting and Stopping the Debugger</span></span>

<span data-ttu-id="0e754-126">Legen Sie einen oder mehrere Haltepunkte fest, um den Debugger zu starten.</span><span class="sxs-lookup"><span data-stu-id="0e754-126">To start the debugger, set one or more breakpoints.</span></span> <span data-ttu-id="0e754-127">Führen Sie dann das Skript, den Befehl oder die Funktion aus, die Sie debuggen möchten.</span><span class="sxs-lookup"><span data-stu-id="0e754-127">Then, run the script, command, or function that you want to debug.</span></span>

<span data-ttu-id="0e754-128">Wenn Sie einen Breakpoint erreichen, wird die Ausführung angehalten, und die Steuerung wird an den Debugger über geschaltet.</span><span class="sxs-lookup"><span data-stu-id="0e754-128">When you reach a breakpoint, execution stops, and control is turned over to the debugger.</span></span>

<span data-ttu-id="0e754-129">Um den Debugger zu beenden, führen Sie das Skript, den Befehl oder die Funktion aus, bis der Debugger fertig ist.</span><span class="sxs-lookup"><span data-stu-id="0e754-129">To stop the debugger, run the script, command, or function until it is complete.</span></span> <span data-ttu-id="0e754-130">Oder geben Sie `stop` oder ein `t` .</span><span class="sxs-lookup"><span data-stu-id="0e754-130">Or, type `stop` or `t`.</span></span>

### <a name="debugger-commands"></a><span data-ttu-id="0e754-131">Debugger-Befehle</span><span class="sxs-lookup"><span data-stu-id="0e754-131">Debugger Commands</span></span>

<span data-ttu-id="0e754-132">Wenn Sie den Debugger in der PowerShell-Konsole verwenden, verwenden Sie die folgenden Befehle, um die Ausführung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="0e754-132">When you use the debugger in the PowerShell console, use the following commands to control the execution.</span></span> <span data-ttu-id="0e754-133">Verwenden Sie in Windows PowerShell ISE Befehle im Menü Debuggen.</span><span class="sxs-lookup"><span data-stu-id="0e754-133">In Windows PowerShell ISE, use commands on the Debug menu.</span></span>

<span data-ttu-id="0e754-134">Hinweis: Informationen zur Verwendung des Debuggers in anderen Host Anwendungen finden Sie in der Dokumentation zur Host Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0e754-134">Note: For information about how to use the debugger in other host applications, see the host application documentation.</span></span>

- <span data-ttu-id="0e754-135">`s`, `StepInto` : Führt die nächste Anweisung aus und hält dann an.</span><span class="sxs-lookup"><span data-stu-id="0e754-135">`s`, `StepInto`: Executes the next statement and then stops.</span></span>

- <span data-ttu-id="0e754-136">`v`, `StepOver` : Führt die nächste Anweisung aus, überspringt jedoch Funktionen und Aufrufe.</span><span class="sxs-lookup"><span data-stu-id="0e754-136">`v`, `StepOver`: Executes the next statement, but skips functions and invocations.</span></span> <span data-ttu-id="0e754-137">Die übersprungenen Anweisungen werden ausgeführt, aber nicht in Einzelschritten durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="0e754-137">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="0e754-138">`Ctrl+Break`: (Alle in der ISE unterbrechen) unterbricht in ein Skript, das entweder in der PowerShell-Konsole oder in Windows PowerShell ISE ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0e754-138">`Ctrl+Break`: (Break All in ISE) Breaks into a running script within either the PowerShell console, or Windows PowerShell ISE.</span></span> <span data-ttu-id="0e754-139">Beachten Sie, dass die <kbd>STRG</kbd> + <kbd>Break</kbd> -Taste in Windows PowerShell 2,0, 3,0 und 4,0 das Programm schließt.</span><span class="sxs-lookup"><span data-stu-id="0e754-139">Note that <kbd>Ctrl</kbd>+<kbd>Break</kbd> in Windows PowerShell 2.0, 3.0, and 4.0 closes the program.</span></span> <span data-ttu-id="0e754-140">Break all funktioniert sowohl für lokale als auch Remote Skripts, die interaktiv ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0e754-140">Break All works on both local and remote interactively-running scripts.</span></span>

- <span data-ttu-id="0e754-141">`o`, `StepOut` : Führt die Schritte aus der aktuellen Funktion aus; eine Ebene nach oben, wenn Sie eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0e754-141">`o`, `StepOut`: Steps out of the current function; up one level if nested.</span></span> <span data-ttu-id="0e754-142">Wenn der Hauptteil im Hauptteil ist, wird er bis zum Ende oder zum nächsten Haltepunkt fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="0e754-142">If in the main body, it continues to the end or the next breakpoint.</span></span> <span data-ttu-id="0e754-143">Die übersprungenen Anweisungen werden ausgeführt, aber nicht in Einzelschritten durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="0e754-143">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="0e754-144">`c`, `Continue` : Wird weiterhin ausgeführt, bis das Skript beendet ist oder bis der nächste Haltepunkt erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="0e754-144">`c`, `Continue`: Continues to run until the script is complete or until the next breakpoint is reached.</span></span> <span data-ttu-id="0e754-145">Die übersprungenen Anweisungen werden ausgeführt, aber nicht in Einzelschritten durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="0e754-145">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="0e754-146">`l`, `List` : Zeigt den Teil des Skripts an, der ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0e754-146">`l`, `List`: Displays the part of the script that is executing.</span></span> <span data-ttu-id="0e754-147">Standardmäßig werden die aktuelle Zeile, fünf vorherige Zeilen und 10 nachfolgende Zeilen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e754-147">By default, it displays the current line, five previous lines, and 10 subsequent lines.</span></span>
  <span data-ttu-id="0e754-148">Drücken Sie die EINGABETASTE, um das Skript weiterhin aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="0e754-148">To continue listing the script, press ENTER.</span></span>

- <span data-ttu-id="0e754-149">`l <m>`, `List` : Zeigt 16 Zeilen des Skripts an, beginnend mit der durch angegebenen Zeilennummer `<m>` .</span><span class="sxs-lookup"><span data-stu-id="0e754-149">`l <m>`, `List`: Displays 16 lines of the script beginning with the line number specified by `<m>`.</span></span>

- <span data-ttu-id="0e754-150">`l <m> <n>`, `List` : Zeigt `<n>` Zeilen des Skripts an, beginnend mit der durch angegebenen Zeilennummer `<m>` .</span><span class="sxs-lookup"><span data-stu-id="0e754-150">`l <m> <n>`, `List`: Displays `<n>` lines of the script, beginning with the line number specified by `<m>`.</span></span>

- <span data-ttu-id="0e754-151">`q`, `Stop` , `Exit` : Beendet die Ausführung des Skripts und beendet den Debugger.</span><span class="sxs-lookup"><span data-stu-id="0e754-151">`q`, `Stop`, `Exit`: Stops executing the script, and exits the debugger.</span></span> <span data-ttu-id="0e754-152">Wenn Sie einen Auftrag durch Ausführen des Cmdlets Debuggen, wird der `Debug-Job` `Exit` Debugger vom Befehl getrennt, und der Auftrag wird weiter ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e754-152">If you are debugging a job by running the `Debug-Job` cmdlet, the `Exit` command detaches the debugger, and allows the job to continue running.</span></span>

- <span data-ttu-id="0e754-153">`k`, `Get-PsCallStack` : Zeigt die aktuelle-aufrufsstapel an.</span><span class="sxs-lookup"><span data-stu-id="0e754-153">`k`, `Get-PsCallStack`: Displays the current call stack.</span></span>

- <span data-ttu-id="0e754-154">`<Enter>`: Wiederholt den letzten Befehl, wenn es sich um einen Schritt (e), einen StepOver (v) oder eine Liste (l) handelt.</span><span class="sxs-lookup"><span data-stu-id="0e754-154">`<Enter>`: Repeats the last command if it was Step (s), StepOver (v), or List (l).</span></span> <span data-ttu-id="0e754-155">Andernfalls stellt eine Sendeaktion dar.</span><span class="sxs-lookup"><span data-stu-id="0e754-155">Otherwise, represents a submit action.</span></span>

- <span data-ttu-id="0e754-156">`?`, `h` : Zeigt die Debugger-Befehls Hilfe an.</span><span class="sxs-lookup"><span data-stu-id="0e754-156">`?`, `h`: Displays the debugger command Help.</span></span>

<span data-ttu-id="0e754-157">Um den Debugger zu beenden, können Sie beenden (q) verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e754-157">To exit the debugger, you can use Stop (q).</span></span>

<span data-ttu-id="0e754-158">Ab PowerShell 5,0 können Sie den Exit-Befehl ausführen, um eine gestartete Debugsitzung zu beenden, die Sie durch Ausführen von oder gestartet haben `Debug-Job` `Debug-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="0e754-158">Starting in PowerShell 5.0, you can run the Exit command to exit a nested debugging session that you started by running either `Debug-Job` or `Debug-Runspace`.</span></span>

<span data-ttu-id="0e754-159">Mit diesen Debuggerbefehlen können Sie ein Skript ausführen, zu einem bestimmten Zeitpunkt anhalten, die Werte von Variablen und den Status des Systems untersuchen und das Skript weiter ausführen, bis Sie ein Problem identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="0e754-159">By using these debugger commands, you can run a script, stop on a point of concern, examine the values of variables and the state of the system, and continue running the script until you have identified a problem.</span></span>

<span data-ttu-id="0e754-160">Hinweis: Wenn Sie eine Anweisung mit einem Umleitungs Operator (z. b. ">") schrittweise ausführen, führt der PowerShell-Debugger alle verbleibenden Anweisungen im Skript aus.</span><span class="sxs-lookup"><span data-stu-id="0e754-160">NOTE: If you step into a statement with a redirection operator, such as ">", the PowerShell debugger steps over all remaining statements in the script.</span></span>

<span data-ttu-id="0e754-161">Anzeigen der Werte von Skript Variablen</span><span class="sxs-lookup"><span data-stu-id="0e754-161">Displaying the Values of script Variables</span></span>

<span data-ttu-id="0e754-162">Im Debugger können Sie auch Befehle eingeben, den Wert von Variablen anzeigen, Cmdlets verwenden und Skripts in der Befehlszeile ausführen.</span><span class="sxs-lookup"><span data-stu-id="0e754-162">While you are in the debugger, you can also enter commands, display the value of variables, use cmdlets, and run scripts at the command line.</span></span>

<span data-ttu-id="0e754-163">Sie können den aktuellen Wert aller Variablen im Skript, das gedebuggt wird, mit Ausnahme der folgenden automatischen Variablen anzeigen:</span><span class="sxs-lookup"><span data-stu-id="0e754-163">You can display the current value of all variables in the script that is being debugged, except for the following automatic variables:</span></span>

```powershell
$_
$Args
$Input
$MyInvocation
$PSBoundParameters
```

<span data-ttu-id="0e754-164">Wenn Sie den Wert von einer dieser Variablen anzeigen, erhalten Sie den Wert, den diese Variablen für eine interne, vom Debugger verwendete Pipeline hat, nicht den Wert der Variablen im Skript.</span><span class="sxs-lookup"><span data-stu-id="0e754-164">If you try to display the value of any of these variables, you get the value of that variable for in an internal pipeline the debugger uses, not the value of the variable in the script.</span></span>

<span data-ttu-id="0e754-165">Um den Wert dieser Variablen für das Skript anzuzeigen, das gedebuggt wird, weisen Sie im Skript den Wert der automatischen Variablen einer neuen Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="0e754-165">To display the value these variables for the script that is being debugged, in the script, assign the value of the automatic variable to a new variable.</span></span> <span data-ttu-id="0e754-166">Anschließend können Sie den Wert der neuen Variablen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0e754-166">Then you can display the value of the new variable.</span></span>

<span data-ttu-id="0e754-167">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="0e754-167">For example,</span></span>

```powershell
$scriptArgs = $Args
$scriptArgs
```

<span data-ttu-id="0e754-168">Im Beispiel in diesem Thema wird der Wert der- `$MyInvocation` Variablen wie folgt neu zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="0e754-168">In the example in this topic, the value of the `$MyInvocation` variable is reassigned as follows:</span></span>

```powershell
$scriptname = $MyInvocation.MyCommand.Path
```

## <a name="the-debugger-environment"></a><span data-ttu-id="0e754-169">Die Debugger-Umgebung</span><span class="sxs-lookup"><span data-stu-id="0e754-169">The Debugger Environment</span></span>

<span data-ttu-id="0e754-170">Wenn Sie einen Breakpoint erreichen, geben Sie die Debugger-Umgebung ein.</span><span class="sxs-lookup"><span data-stu-id="0e754-170">When you reach a breakpoint, you enter the debugger environment.</span></span> <span data-ttu-id="0e754-171">Die Eingabeaufforderung ändert sich, sodass Sie mit "[dbg]:" beginnt.</span><span class="sxs-lookup"><span data-stu-id="0e754-171">The command prompt changes so that it begins with "[DBG]:".</span></span>

<span data-ttu-id="0e754-172">Weitere Informationen zum Anpassen der Eingabeaufforderung finden Sie unter [about_Prompts](about_prompts.md).</span><span class="sxs-lookup"><span data-stu-id="0e754-172">For more information about customizing the prompt, see [about_Prompts](about_prompts.md).</span></span>

<span data-ttu-id="0e754-173">Außerdem wird in einigen Host Anwendungen, wie z. b. der PowerShell-Konsole (aber nicht in Windows PowerShell Integrated Scripting Environment [ISE]) eine schaufnahmenaufforderung zum Debuggen geöffnet.</span><span class="sxs-lookup"><span data-stu-id="0e754-173">Also, in some host applications, such as the PowerShell console, (but not in Windows PowerShell Integrated Scripting Environment [ISE]), a nested prompt opens for debugging.</span></span> <span data-ttu-id="0e754-174">Sie können die eingefügte Eingabeaufforderung mit den wiederholten mehr-als-Zeichen (ASCII 62) erkennen, die an der Eingabeaufforderung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0e754-174">You can detect the nested prompt by the repeating greater-than characters (ASCII 62) that appear at the command prompt.</span></span>

<span data-ttu-id="0e754-175">Das folgende Beispiel zeigt die standardmäßige debuggingaufforderung in der PowerShell-Konsole:</span><span class="sxs-lookup"><span data-stu-id="0e754-175">For example, the following is the default debugging prompt in the PowerShell console:</span></span>

```
[DBG]: PS (get-location)>>>
```

<span data-ttu-id="0e754-176">Sie können die Schachtelungs Ebene mithilfe der `$NestedPromptLevel` automatischen Variablen ermitteln.</span><span class="sxs-lookup"><span data-stu-id="0e754-176">You can find the nesting level by using the `$NestedPromptLevel` automatic variable.</span></span>

<span data-ttu-id="0e754-177">Außerdem wird eine automatische Variable, `$PSDebugContext` , im lokalen Gültigkeitsbereich definiert.</span><span class="sxs-lookup"><span data-stu-id="0e754-177">Additionally, an automatic variable, `$PSDebugContext`, is defined in the local scope.</span></span> <span data-ttu-id="0e754-178">Sie können das vorhanden sein der `$PsDebugContext` Variablen verwenden, um zu bestimmen, ob Sie sich im Debugger befinden.</span><span class="sxs-lookup"><span data-stu-id="0e754-178">You can use the presence of the `$PsDebugContext` variable to determine whether you are in the debugger.</span></span>

<span data-ttu-id="0e754-179">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0e754-179">For example:</span></span>

```powershell
if ($PSDebugContext) {"Debugging"} else {"Not Debugging"}
```

<span data-ttu-id="0e754-180">Sie können den Wert der `$PSDebugContext` Variablen im Debuggen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e754-180">You can use the value of the `$PSDebugContext` variable in your debugging.</span></span>

```
[DBG]: PS>>> $PSDebugContext.InvocationInfo

Name   CommandLineParameters  UnboundArguments  Location
----   ---------------------  ----------------  --------
=      {}                     {}                C:\ps-test\vote.ps1 (1)
```

## <a name="debugging-and-scope"></a><span data-ttu-id="0e754-181">Debuggen und Bereich</span><span class="sxs-lookup"><span data-stu-id="0e754-181">Debugging and Scope</span></span>

<span data-ttu-id="0e754-182">Durch das unterbrechen in den Debugger wird der Bereich, in dem Sie arbeiten, nicht geändert. Wenn Sie jedoch einen Haltepunkt in einem Skript erreichen, wechseln Sie in den Skript Bereich.</span><span class="sxs-lookup"><span data-stu-id="0e754-182">Breaking into the debugger does not change the scope in which you are operating, but when you reach a breakpoint in a script, you move into the script scope.</span></span> <span data-ttu-id="0e754-183">Der Skript Bereich ist ein untergeordnetes Element des Bereichs, in dem Sie den Debugger ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="0e754-183">The script scope is a child of the scope in which you ran the debugger.</span></span>

<span data-ttu-id="0e754-184">Um die im Skript Bereich definierten Variablen und Aliase zu suchen, verwenden Sie den Scope-Parameter der `Get-Alias` `Get-Variable` Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="0e754-184">To find the variables and aliases that are defined in the script scope, use the Scope parameter of the `Get-Alias` or `Get-Variable` cmdlets.</span></span>

<span data-ttu-id="0e754-185">Beispielsweise ruft der folgende Befehl die Variablen im lokalen Bereich (Skript) ab:</span><span class="sxs-lookup"><span data-stu-id="0e754-185">For example, the following command gets the variables in the local (script) scope:</span></span>

```powershell
Get-Variable -scope 0
```

<span data-ttu-id="0e754-186">Sie können den Befehl wie folgt abkürzen:</span><span class="sxs-lookup"><span data-stu-id="0e754-186">You can abbreviate the command as:</span></span>

```powershell
gv -s 0
```

<span data-ttu-id="0e754-187">Dies ist eine hilfreiche Möglichkeit, nur die Variablen anzuzeigen, die Sie im Skript definiert haben und die Sie beim Debuggen definiert haben.</span><span class="sxs-lookup"><span data-stu-id="0e754-187">This is a useful way to see only the variables that you defined in the script and that you defined while debugging.</span></span>

<span data-ttu-id="0e754-188">Debuggen in der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="0e754-188">Debugging at the Command Line</span></span>

<span data-ttu-id="0e754-189">Wenn Sie einen Variablen-Haltepunkt oder einen Befehls Haltepunkt festlegen, können Sie den Breakpoint nur in einer Skriptdatei festlegen.</span><span class="sxs-lookup"><span data-stu-id="0e754-189">When you set a variable breakpoint or a command breakpoint, you can set the breakpoint only in a script file.</span></span> <span data-ttu-id="0e754-190">Der Breakpoint wird jedoch standardmäßig für alle Elemente festgelegt, die in der aktuellen Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0e754-190">However, by default, the breakpoint is set on anything that runs in the current session.</span></span>

<span data-ttu-id="0e754-191">Wenn Sie z. b. einen Haltepunkt für die `$name` Variable festlegen, unterbricht der Debugger jede beliebige `$name` Variable in allen Skripts, Befehlen, Funktionen, Skript-Cmdlets oder Ausdrücken, die Sie ausführen, bis Sie den Breakpoint deaktivieren oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="0e754-191">For example, if you set a breakpoint on the `$name` variable, the debugger breaks on any `$name` variable in any script, command, function, script cmdlet or expression that you run until you disable or remove the breakpoint.</span></span>

<span data-ttu-id="0e754-192">Dadurch können Sie Ihre Skripts in einem realistischeren Kontext Debuggen, in dem Sie von Funktionen, Variablen und anderen Skripts in der Sitzung und im Profil des Benutzers betroffen sein können.</span><span class="sxs-lookup"><span data-stu-id="0e754-192">This allows you to debug your scripts in a more realistic context in which they might be affected by functions, variables, and other scripts in the session and in the user's profile.</span></span>

<span data-ttu-id="0e754-193">Zeilen Breakpoints sind für Skriptdateien spezifisch, sodass Sie nur in Skriptdateien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0e754-193">Line breakpoints are specific to script files, so they are set only in script files.</span></span>

## <a name="debugging-functions"></a><span data-ttu-id="0e754-194">Debugfunktionen</span><span class="sxs-lookup"><span data-stu-id="0e754-194">Debugging Functions</span></span>

<span data-ttu-id="0e754-195">Wenn Sie einen Breakpoint für eine Funktion mit den `Begin` Abschnitten, `Process` und festlegen `End` , wird der Debugger in der ersten Zeile jedes Abschnitts unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="0e754-195">When you set a breakpoint on a function that has `Begin`, `Process`, and `End` sections, the debugger breaks at the first line of each section.</span></span>

<span data-ttu-id="0e754-196">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0e754-196">For example:</span></span>

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

## <a name="debugging-remote-scripts"></a><span data-ttu-id="0e754-197">Debugging von Remote Skripts</span><span class="sxs-lookup"><span data-stu-id="0e754-197">Debugging Remote Scripts</span></span>

<span data-ttu-id="0e754-198">Ab PowerShell 5,0 können Sie den PowerShell-Debugger in einer Remote Sitzung ausführen, entweder in der-Konsole oder in Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="0e754-198">Starting in PowerShell 5.0, you can run the PowerShell debugger in a remote session, in either the console, or Windows PowerShell ISE.</span></span>
<span data-ttu-id="0e754-199">`Enter-PSSession` die Funktionalität wurde aktualisiert, damit Sie erneut eine Verbindung mit herstellen und eine getrennte Sitzung eingeben können, die auf einem Remote Computer ausgeführt wird und derzeit ein Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0e754-199">`Enter-PSSession` functionality has been updated to let you reconnect to and enter a disconnected session that is running on a remote computer, and currently running a script.</span></span> <span data-ttu-id="0e754-200">Wenn das Skript, das ausgeführt wird, auf einen Haltepunkt trifft, wird der Debugger automatisch von der Client Sitzung gestartet.</span><span class="sxs-lookup"><span data-stu-id="0e754-200">If the running script hits a breakpoint, your client session automatically starts the debugger.</span></span>

<span data-ttu-id="0e754-201">Im folgenden Beispiel wird gezeigt, wie dies funktioniert, wobei Breakpoints in einem Skript in den Zeilen 6, 11, 22 und 25 festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="0e754-201">The following is an example that shows how this works, with breakpoints set in a script at lines 6, 11, 22, and 25.</span></span> <span data-ttu-id="0e754-202">Beachten Sie, dass im Beispiel beim Start des Debuggers zwei identifizierende Eingabe Aufforderungen vorhanden sind: der Name des Computers, auf dem die Sitzung ausgeführt wird, und die dbg-Eingabeaufforderung, die Sie darüber informiert, dass Sie sich im Debugmodus befinden.</span><span class="sxs-lookup"><span data-stu-id="0e754-202">Note that in the example, when the debugger starts, there are two identifying prompts: the name of the computer on which the session is running, and the DBG prompt that lets you know you are in debugging mode.</span></span>

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

## <a name="examples"></a><span data-ttu-id="0e754-203">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0e754-203">Examples</span></span>

<span data-ttu-id="0e754-204">Dieses Testskript erkennt die Version des Betriebssystems und zeigt eine System entsprechende Meldung an.</span><span class="sxs-lookup"><span data-stu-id="0e754-204">This test script detects the version of the operating system and displays a system-appropriate message.</span></span> <span data-ttu-id="0e754-205">Sie enthält eine Funktion, einen Funktions aufrufund eine Variable.</span><span class="sxs-lookup"><span data-stu-id="0e754-205">It includes a function, a function call, and a variable.</span></span>

<span data-ttu-id="0e754-206">Der folgende Befehl zeigt den Inhalt der Testskript Datei an:</span><span class="sxs-lookup"><span data-stu-id="0e754-206">The following command displays the contents of the test script file:</span></span>

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

<span data-ttu-id="0e754-207">Legen Sie zum Starten einen Haltepunkt an einem Point of Interest im Skript fest, z. b. eine Zeile, einen Befehl, eine Variable oder eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="0e754-207">To start, set a breakpoint at a point of interest in the script, such as a line, command, variable, or function.</span></span>

<span data-ttu-id="0e754-208">Beginnen Sie mit dem Erstellen eines Zeilen halte Punkts in der ersten Zeile des Test.ps1 Skripts im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0e754-208">Start by creating a line breakpoint on the first line of the Test.ps1 script in the current directory.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -line 1 -script test.ps1
```

<span data-ttu-id="0e754-209">Sie können diesen Befehl wie folgt abkürzen:</span><span class="sxs-lookup"><span data-stu-id="0e754-209">You can abbreviate this command as:</span></span>

```powershell
PS C:\ps-test> spb 1 -s test.ps1
```

<span data-ttu-id="0e754-210">Der Befehl gibt ein Zeilen Haltepunkt Objekt ( **System. Management. Automation. linebreakpoint** ) zurück.</span><span class="sxs-lookup"><span data-stu-id="0e754-210">The command returns a line-breakpoint object ( **System.Management.Automation.LineBreakpoint** ).</span></span>

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

<span data-ttu-id="0e754-211">Starten Sie nun das Skript.</span><span class="sxs-lookup"><span data-stu-id="0e754-211">Now, start the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
```

<span data-ttu-id="0e754-212">Wenn das Skript den ersten Breakpoint erreicht, gibt die breakpointmeldung an, dass der Debugger aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="0e754-212">When the script reaches the first breakpoint, the breakpoint message indicates that the debugger is active.</span></span> <span data-ttu-id="0e754-213">Es beschreibt den Haltepunkt und zeigt die erste Zeile des Skripts an, eine Funktionsdeklaration.</span><span class="sxs-lookup"><span data-stu-id="0e754-213">It describes the breakpoint and previews the first line of the script, which is a function declaration.</span></span> <span data-ttu-id="0e754-214">Die Eingabeaufforderung ändert sich auch, um anzugeben, dass der Debugger über die Steuerung verfügt.</span><span class="sxs-lookup"><span data-stu-id="0e754-214">The command prompt also changes to indicate that the debugger has control.</span></span>

<span data-ttu-id="0e754-215">Die vorschauzeile enthält den Skriptnamen und die Zeilennummer des in der Vorschau angezeigten Befehls.</span><span class="sxs-lookup"><span data-stu-id="0e754-215">The preview line includes the script name and the line number of the previewed command.</span></span>

```powershell
Entering debug mode. Use h or ? for help.

Hit Line breakpoint on 'C:\ps-test\test.ps1:1'

test.ps1:1   function psversion {
# DBG>
```

<span data-ttu-id="0e754-216">Verwenden Sie den Schritt Befehl (e), um die erste Anweisung im Skript auszuführen und eine Vorschau der nächsten Anweisung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0e754-216">Use the Step command (s) to execute the first statement in the script and to preview the next statement.</span></span> <span data-ttu-id="0e754-217">Die nächste Anweisung verwendet die `$MyInvocation` Automatische Variable, um den Wert der `$scriptName` Variablen auf den Pfad und den Dateinamen der Skriptdatei festzulegen.</span><span class="sxs-lookup"><span data-stu-id="0e754-217">The next statement uses the `$MyInvocation` automatic variable to set the value of the `$scriptName` variable to the path and file name of the script file.</span></span>

```powershell
DBG> s
test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
```

<span data-ttu-id="0e754-218">An diesem Punkt wird die `$scriptName` Variable nicht aufgefüllt, aber Sie können den Wert der Variablen durch anzeigen ihres Werts überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0e754-218">At this point, the `$scriptName` variable is not populated, but you can verify the value of the variable by displaying its value.</span></span> <span data-ttu-id="0e754-219">In diesem Fall handelt es sich um den Wert `$null`.</span><span class="sxs-lookup"><span data-stu-id="0e754-219">In this case, the value is `$null`.</span></span>

```powershell
DBG> $scriptname
# DBG>
```

<span data-ttu-id="0e754-220">Verwenden Sie einen anderen Schritt Befehl (en), um die aktuelle Anweisung auszuführen und eine Vorschau der nächsten Anweisung im Skript anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0e754-220">Use another Step command (s) to execute the current statement and to preview the next statement in the script.</span></span> <span data-ttu-id="0e754-221">Die nächste Anweisung ruft die psversion-Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="0e754-221">The next statement calls the PsVersion function.</span></span>

```powershell
DBG> s
test.ps1:12  psversion
```

<span data-ttu-id="0e754-222">An diesem Punkt wird die `$scriptName` Variable aufgefüllt, aber Sie überprüfen den Wert der Variablen, indem Sie Ihren Wert anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0e754-222">At this point, the `$scriptName` variable is populated, but you verify the value of the variable by displaying its value.</span></span> <span data-ttu-id="0e754-223">In diesem Fall wird der Wert auf den Skript Pfad festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0e754-223">In this case, the value is set to the script path.</span></span>

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```

<span data-ttu-id="0e754-224">Verwenden Sie einen anderen Schritt Befehl zum Ausführen des Funktions Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="0e754-224">Use another Step command to execute the function call.</span></span> <span data-ttu-id="0e754-225">Drücken Sie die EINGABETASTE, oder geben Sie "s" für Schritt ein.</span><span class="sxs-lookup"><span data-stu-id="0e754-225">Press ENTER, or type "s" for Step.</span></span>

```powershell
DBG> s
test.ps1:2       "PowerShell " + $PSVersionTable.PSVersion
```

<span data-ttu-id="0e754-226">Die Debugmeldung enthält eine Vorschau der Anweisung in der Funktion.</span><span class="sxs-lookup"><span data-stu-id="0e754-226">The debug message includes a preview of the statement in the function.</span></span> <span data-ttu-id="0e754-227">Zum Ausführen dieser Anweisung und zum Anzeigen einer Vorschau der nächsten Anweisung in der Funktion können Sie einen- `Step` Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e754-227">To execute this statement and to preview the next statement in the function, you can use a `Step` command.</span></span> <span data-ttu-id="0e754-228">Verwenden Sie in diesem Fall jedoch einen StepOut-Befehl (o).</span><span class="sxs-lookup"><span data-stu-id="0e754-228">But, in this case, use a StepOut command (o).</span></span> <span data-ttu-id="0e754-229">Dadurch wird die Ausführung der Funktion abgeschlossen (es sei denn, Sie erreicht einen Haltepunkt), und es werden Schritte zur nächsten Anweisung im Skript ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e754-229">It completes the execution of the function (unless it reaches a breakpoint) and steps to the next statement in the script.</span></span>

```powershell
DBG> o
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

<span data-ttu-id="0e754-230">Da wir die letzte Anweisung im Skript haben, haben die Befehle Step, StepOut und continue dieselbe Wirkung.</span><span class="sxs-lookup"><span data-stu-id="0e754-230">Because we are on the last statement in the script, the Step, StepOut, and Continue commands have the same effect.</span></span> <span data-ttu-id="0e754-231">Verwenden Sie in diesem Fall "StepOut (o)".</span><span class="sxs-lookup"><span data-stu-id="0e754-231">In this case, use StepOut (o).</span></span>

```powershell
Done C:\ps-test\test.ps1
PS C:\ps-test>
```

<span data-ttu-id="0e754-232">Der Befehl "StepOut" führt den letzten Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="0e754-232">The StepOut command executes the last command.</span></span> <span data-ttu-id="0e754-233">Die Standardeingabe Aufforderung zeigt an, dass der Debugger beendet wurde und die Steuerung an den Befehlsprozessor zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="0e754-233">The standard command prompt indicates that the debugger has exited and returned control to the command processor.</span></span>

<span data-ttu-id="0e754-234">Führen Sie den Debugger nun erneut aus.</span><span class="sxs-lookup"><span data-stu-id="0e754-234">Now, run the debugger again.</span></span> <span data-ttu-id="0e754-235">Verwenden Sie zum Löschen des aktuellen Breakpoints zunächst die `Get-PsBreakpoint` `Remove-PsBreakpoint` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="0e754-235">First, to delete the current breakpoint, use the `Get-PsBreakpoint` and `Remove-PsBreakpoint` cmdlets.</span></span> <span data-ttu-id="0e754-236">(Wenn Sie vermuten, dass Sie den Breakpoint wieder verwenden, verwenden Sie das- `Disable-PsBreakpoint` Cmdlet anstelle von `Remove-PsBreakpoint` .)</span><span class="sxs-lookup"><span data-stu-id="0e754-236">(If you think you might reuse the breakpoint, use the `Disable-PsBreakpoint` cmdlet instead of `Remove-PsBreakpoint`.)</span></span>

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

<span data-ttu-id="0e754-237">Sie können diesen Befehl wie folgt abkürzen:</span><span class="sxs-lookup"><span data-stu-id="0e754-237">You can abbreviate this command as:</span></span>

```powershell
PS C:\ps-test> gbp | rbp
```

<span data-ttu-id="0e754-238">Oder führen Sie den Befehl aus, indem Sie eine Funktion schreiben, z. b. die folgende Funktion:</span><span class="sxs-lookup"><span data-stu-id="0e754-238">Or, run the command by writing a function, such as the following function:</span></span>

```powershell
function delbr { gbp | rbp }
```

<span data-ttu-id="0e754-239">Erstellen Sie nun einen Haltepunkt für die `$scriptname` Variable.</span><span class="sxs-lookup"><span data-stu-id="0e754-239">Now, create a breakpoint on the `$scriptname` variable.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -variable scriptname -script test.ps1
```

<span data-ttu-id="0e754-240">Sie können den Befehl wie folgt abkürzen:</span><span class="sxs-lookup"><span data-stu-id="0e754-240">You can abbreviate the command as:</span></span>

```powershell
PS C:\ps-test> sbp -v scriptname -s test.ps1
```

<span data-ttu-id="0e754-241">Starten Sie nun das Skript.</span><span class="sxs-lookup"><span data-stu-id="0e754-241">Now, start the script.</span></span> <span data-ttu-id="0e754-242">Das Skript erreicht den Variablen-Breakpoint.</span><span class="sxs-lookup"><span data-stu-id="0e754-242">The script reaches the variable breakpoint.</span></span> <span data-ttu-id="0e754-243">Der Standardmodus ist "Write", sodass die Ausführung unmittelbar vor der-Anweisung angehalten wird, die den Wert der Variablen ändert.</span><span class="sxs-lookup"><span data-stu-id="0e754-243">The default mode is Write, so execution stops just before the statement that changes the value of the variable.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Variable breakpoint on 'C:\ps-test\test.ps1:$scriptName'
(Write access)

test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
# DBG>
```

<span data-ttu-id="0e754-244">Zeigt den aktuellen Wert der `$scriptName` Variablen an, der ist `$null` .</span><span class="sxs-lookup"><span data-stu-id="0e754-244">Display the current value of the `$scriptName` variable, which is `$null`.</span></span>

```powershell
DBG> $scriptName
# DBG>
```

<span data-ttu-id="0e754-245">Verwenden Sie einen Schritt Befehl (e), um die Anweisung auszuführen, die die Variable auffüllt.</span><span class="sxs-lookup"><span data-stu-id="0e754-245">Use a Step command (s) to execute the statement that populates the variable.</span></span>
<span data-ttu-id="0e754-246">Zeigen Sie dann den neuen Wert der `$scriptName` Variablen an.</span><span class="sxs-lookup"><span data-stu-id="0e754-246">Then, display the new value of the `$scriptName` variable.</span></span>

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```powershell

Use a Step command (s) to preview the next statement in the script.

```powershell
DBG> s
test.ps1:12  psversion
```

<span data-ttu-id="0e754-247">Die nächste Anweisung ist ein Aufrufder psversion-Funktion.</span><span class="sxs-lookup"><span data-stu-id="0e754-247">The next statement is a call to the PsVersion function.</span></span> <span data-ttu-id="0e754-248">Um die Funktion zu überspringen, aber trotzdem auszuführen, verwenden Sie einen Befehl "StepOver" (v).</span><span class="sxs-lookup"><span data-stu-id="0e754-248">To skip the function but still execute it, use a StepOver command (v).</span></span> <span data-ttu-id="0e754-249">Wenn Sie sich bereits in der-Funktion befinden, wenn Sie StepOver verwenden, ist dies nicht effektiv.</span><span class="sxs-lookup"><span data-stu-id="0e754-249">If you are already in the function when you use StepOver, it is not effective.</span></span> <span data-ttu-id="0e754-250">Der Funktions aufrufwird zwar angezeigt, aber nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e754-250">The function call is displayed, but it is not executed.</span></span>

```powershell
DBG> v
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

<span data-ttu-id="0e754-251">Der Befehl "StepOver" führt die Funktion aus und zeigt eine Vorschau der nächsten Anweisung im Skript an, die die letzte Zeile ausgibt.</span><span class="sxs-lookup"><span data-stu-id="0e754-251">The StepOver command executes the function, and it previews the next statement in the script, which prints the final line.</span></span>

<span data-ttu-id="0e754-252">Beenden Sie den Debugger mithilfe eines Beendigungs Befehls (t).</span><span class="sxs-lookup"><span data-stu-id="0e754-252">Use a Stop command (t) to exit the debugger.</span></span> <span data-ttu-id="0e754-253">Die Eingabeaufforderung kehrt zur Standardeingabe Aufforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="0e754-253">The command prompt reverts to the standard command prompt.</span></span>

```powershell
C:\ps-test>
```

<span data-ttu-id="0e754-254">Um die Breakpoints zu löschen, verwenden Sie die `Get-PsBreakpoint` `Remove-PsBreakpoint` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="0e754-254">To delete the breakpoints, use the `Get-PsBreakpoint` and `Remove-PsBreakpoint` cmdlets.</span></span>

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

<span data-ttu-id="0e754-255">Erstellen Sie einen neuen Befehls Haltepunkt in der psversion-Funktion.</span><span class="sxs-lookup"><span data-stu-id="0e754-255">Create a new command breakpoint on the PsVersion function.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1
```

<span data-ttu-id="0e754-256">Sie können diesen Befehl wie folgt abkürzen:</span><span class="sxs-lookup"><span data-stu-id="0e754-256">You can abbreviate this command to:</span></span>

```powershell
PS C:\ps-test> sbp -c psversion -s test.ps1
```

<span data-ttu-id="0e754-257">Führen Sie nun das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="0e754-257">Now, run the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
# DBG>
```

<span data-ttu-id="0e754-258">Das Skript erreicht den Haltepunkt beim Funktions aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0e754-258">The script reaches the breakpoint at the function call.</span></span> <span data-ttu-id="0e754-259">An diesem Punkt wurde die-Funktion noch nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0e754-259">At this point, the function has not yet been called.</span></span> <span data-ttu-id="0e754-260">Dadurch haben Sie die Möglichkeit, den Action-Parameter von `Set-PSBreakpoint` zu verwenden, um Bedingungen für die Ausführung des Breakpoints festzulegen oder um Vorbereitungs-oder Diagnoseaufgaben auszuführen, z. b. das Starten eines Protokolls oder das Aufrufen eines Diagnose-oder Sicherheits Skripts.</span><span class="sxs-lookup"><span data-stu-id="0e754-260">This gives you the opportunity to use the Action parameter of `Set-PSBreakpoint` to set conditions for the execution of the breakpoint or to perform preparatory or diagnostic tasks, such as starting a log or invoking a diagnostic or security script.</span></span>

<span data-ttu-id="0e754-261">Um eine Aktion festzulegen, verwenden Sie einen Continue-Befehl (c), um das Skript zu beenden, und einen `Remove-PsBreakpoint` Befehl zum Löschen des aktuellen Breakpoints.</span><span class="sxs-lookup"><span data-stu-id="0e754-261">To set an action, use a Continue command (c) to exit the script, and a `Remove-PsBreakpoint` command to delete the current breakpoint.</span></span> <span data-ttu-id="0e754-262">(Breakpoints sind schreibgeschützt, sodass Sie dem aktuellen Haltepunkt keine Aktion hinzufügen können.)</span><span class="sxs-lookup"><span data-stu-id="0e754-262">(Breakpoints are read-only, so you cannot add an action to the current breakpoint.)</span></span>

```powershell
DBG> c
Windows PowerShell 2.0
Have you run a background job today (start-job)?
Done C:\ps-test\test.ps1

PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
PS C:\ps-test>
```

<span data-ttu-id="0e754-263">Erstellen Sie nun einen neuen Befehls Haltepunkt mit einer Aktion.</span><span class="sxs-lookup"><span data-stu-id="0e754-263">Now, create a new command breakpoint with an action.</span></span> <span data-ttu-id="0e754-264">Der folgende Befehl legt einen Befehls Haltepunkt mit einer Aktion fest, die den Wert der `$scriptName` Variablen protokolliert, wenn die-Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0e754-264">The following command sets a command breakpoint with an action that logs the value of the `$scriptName` variable when the function is called.</span></span> <span data-ttu-id="0e754-265">Da das break-Schlüsselwort in der Aktion nicht verwendet wird, wird die Ausführung nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="0e754-265">Because the Break keyword is not used in the action, execution does not stop.</span></span> <span data-ttu-id="0e754-266">(Das Graviszeichen (') ist das Zeilen Fortsetzungs Zeichen.)</span><span class="sxs-lookup"><span data-stu-id="0e754-266">(The backtick (\`) is the line-continuation character.)</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1  `
-action { add-content "The value of `$scriptName is $scriptName." `
-path action.log}
```

<span data-ttu-id="0e754-267">Sie können auch Aktionen hinzufügen, die Bedingungen für den Haltepunkt festlegen.</span><span class="sxs-lookup"><span data-stu-id="0e754-267">You can also add actions that set conditions for the breakpoint.</span></span> <span data-ttu-id="0e754-268">Im folgenden Befehl wird der Befehls Haltepunkt nur ausgeführt, wenn die Ausführungs Richtlinie auf RemoteSigned festgelegt ist. Dies ist die restriktivste Richtlinie, mit der Sie weiterhin Skripts ausführen können.</span><span class="sxs-lookup"><span data-stu-id="0e754-268">In the following command, the command breakpoint is executed only if the execution policy is set to RemoteSigned, the most restrictive policy that still permits you to run scripts.</span></span> <span data-ttu-id="0e754-269">(Das Graviszeichen (') ist das Fortsetzungs Zeichen.)</span><span class="sxs-lookup"><span data-stu-id="0e754-269">(The backtick (\`) is the continuation character.)</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -script test.ps1 -command psversion `
-action { if ((Get-ExecutionPolicy) -eq "RemoteSigned") { break }}
```

<span data-ttu-id="0e754-270">Das break-Schlüsselwort in der Aktion weist den Debugger an, den Breakpoint auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0e754-270">The Break keyword in the action directs the debugger to execute the breakpoint.</span></span>
<span data-ttu-id="0e754-271">Sie können auch das Continue-Schlüsselwort verwenden, um den Debugger zur Ausführung ohne Unterbrechung zu leiten.</span><span class="sxs-lookup"><span data-stu-id="0e754-271">You can also use the Continue keyword to direct the debugger to execute without breaking.</span></span> <span data-ttu-id="0e754-272">Da das Default-Schlüsselwort Continue lautet, müssen Sie "Break" angeben, um die Ausführung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="0e754-272">Because the default keyword is Continue, you must specify Break to stop execution.</span></span>

<span data-ttu-id="0e754-273">Führen Sie nun das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="0e754-273">Now, run the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
```

<span data-ttu-id="0e754-274">Da die Ausführungs Richtlinie auf " **RemoteSigned** " festgelegt ist, wird die Ausführung beim Funktions aufzurufen angehalten.</span><span class="sxs-lookup"><span data-stu-id="0e754-274">Because the execution policy is set to **RemoteSigned** , execution stops at the function call.</span></span>

<span data-ttu-id="0e754-275">An diesem Punkt können Sie die aufrufsstapel überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0e754-275">At this point, you might want to check the call stack.</span></span> <span data-ttu-id="0e754-276">Verwenden Sie das `Get-PsCallStack` Cmdlet oder den `Get-PsCallStack` Debugger-Befehl (k).</span><span class="sxs-lookup"><span data-stu-id="0e754-276">Use the `Get-PsCallStack` cmdlet or the `Get-PsCallStack` debugger command (k).</span></span> <span data-ttu-id="0e754-277">Der folgende Befehl ruft die aktuelle-Rückruf Stapel ab.</span><span class="sxs-lookup"><span data-stu-id="0e754-277">The following command gets the current call stack.</span></span>

```powershell
DBG> k
2: prompt
1: .\test.ps1: $args=[]
0: prompt: $args=[]
```

<span data-ttu-id="0e754-278">Dieses Beispiel zeigt nur einige der vielen Möglichkeiten, den PowerShell-Debugger zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e754-278">This example demonstrates just a few of the many ways to use the PowerShell debugger.</span></span>

<span data-ttu-id="0e754-279">Geben Sie den folgenden Befehl ein, um weitere Informationen zu den Debugger-Cmdlets zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="0e754-279">For more information about the debugger cmdlets, type the following command:</span></span>

```powershell
help <cmdlet-name> -full
```

<span data-ttu-id="0e754-280">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0e754-280">For example, type:</span></span>

```powershell
help Set-PSBreakpoint -full
```

## <a name="other-debugging-features-in-powershell"></a><span data-ttu-id="0e754-281">Weitere Debuggingfunktionen in PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e754-281">Other Debugging Features in PowerShell</span></span>

<span data-ttu-id="0e754-282">Zusätzlich zum PowerShell-Debugger enthält PowerShell einige weitere Funktionen, die Sie zum Debuggen von Skripts und Funktionen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0e754-282">In addition to the PowerShell debugger, PowerShell includes several other features that you can use to debug scripts and functions.</span></span>

- <span data-ttu-id="0e754-283">Windows PowerShell ISE enthält einen interaktiven grafischen Debugger.</span><span class="sxs-lookup"><span data-stu-id="0e754-283">Windows PowerShell ISE includes an interactive graphical debugger.</span></span> <span data-ttu-id="0e754-284">Um weitere Informationen zu erhalten, starten Sie Windows PowerShell ISE, und drücken Sie F1.</span><span class="sxs-lookup"><span data-stu-id="0e754-284">For more information, start Windows PowerShell ISE and press F1.</span></span>

- <span data-ttu-id="0e754-285">Das `Set-PSDebug` -Cmdlet bietet sehr grundlegende Skripts zum Debuggen, einschließlich schrittweise und Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="0e754-285">The `Set-PSDebug` cmdlet offers very basic script debugging features, including stepping and tracing.</span></span>

- <span data-ttu-id="0e754-286">Verwenden `Set-StrictMode` Sie das Cmdlet, um Verweise auf nicht initialisierte Variablen, Verweise auf nicht vorhandene Eigenschaften eines Objekts und ungültige Funktions Syntax zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="0e754-286">Use the `Set-StrictMode` cmdlet to detect references to uninitialized variables, to references to non-existent properties of an object, and to function syntax that is not valid.</span></span>

- <span data-ttu-id="0e754-287">Fügen Sie einem Skript Diagnose Anweisungen hinzu, z. b. Anweisungen, die den Wert von Variablen anzeigen, Anweisungen, die Eingaben aus der Befehlszeile lesen, oder Anweisungen, die die aktuelle Anweisung melden.</span><span class="sxs-lookup"><span data-stu-id="0e754-287">Add diagnostic statements to a script, such as statements that display the value of variables, statements that read input from the command line, or statements that report the current instruction.</span></span> <span data-ttu-id="0e754-288">Verwenden Sie die-Cmdlets, die das Schreib Verb für diese Aufgabe enthalten, z `Write-Host` `Write-Debug` . b.,, `Write-Warning` und `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="0e754-288">Use the cmdlets that contain the Write verb for this task, such as `Write-Host`, `Write-Debug`, `Write-Warning`, and `Write-Verbose`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e754-289">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="0e754-289">SEE ALSO</span></span>

- [<span data-ttu-id="0e754-290">Deaktivieren-psbreakpoint</span><span class="sxs-lookup"><span data-stu-id="0e754-290">Disable-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Disable-PSBreakpoint)
- [<span data-ttu-id="0e754-291">Enable-psbreakpoint</span><span class="sxs-lookup"><span data-stu-id="0e754-291">Enable-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Enable-PSBreakpoint)
- [<span data-ttu-id="0e754-292">Get-psbreakpoint</span><span class="sxs-lookup"><span data-stu-id="0e754-292">Get-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Get-PSBreakpoint)
- [<span data-ttu-id="0e754-293">Get-pscallstack</span><span class="sxs-lookup"><span data-stu-id="0e754-293">Get-PsCallStack</span></span>](xref:Microsoft.PowerShell.Utility.Get-PSCallStack)
- [<span data-ttu-id="0e754-294">Remove-psbreakpoint</span><span class="sxs-lookup"><span data-stu-id="0e754-294">Remove-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Remove-PSBreakpoint)
- [<span data-ttu-id="0e754-295">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="0e754-295">Set-PSBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Set-PSBreakpoint)
- [<span data-ttu-id="0e754-296">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="0e754-296">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [<span data-ttu-id="0e754-297">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="0e754-297">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)

