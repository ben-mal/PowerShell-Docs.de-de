---
description: Beschreibt Variablen, die Zustandsinformationen für PowerShell speichern. Diese Variablen werden von PowerShell erstellt und verwaltet.
Locale: en-US
ms.date: 03/29/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_automatic_variables?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Automatic_Variables
ms.openlocfilehash: 68d67c341db46015da948fe24c2e16b305b669e9
ms.sourcegitcommit: bdd0fedaf9ba534645b2f7eb1fe1241481f58715
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "105936698"
---
# <a name="about-automatic-variables"></a><span data-ttu-id="48ae7-104">Informationen zu automatischen Variablen</span><span class="sxs-lookup"><span data-stu-id="48ae7-104">About Automatic Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="48ae7-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48ae7-105">Short description</span></span>

<span data-ttu-id="48ae7-106">Beschreibt Variablen, die Zustandsinformationen für PowerShell speichern.</span><span class="sxs-lookup"><span data-stu-id="48ae7-106">Describes variables that store state information for PowerShell.</span></span> <span data-ttu-id="48ae7-107">Diese Variablen werden von PowerShell erstellt und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="48ae7-107">These variables are created and maintained by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="48ae7-108">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48ae7-108">Long description</span></span>

<span data-ttu-id="48ae7-109">Konzeptionell werden diese Variablen als schreibgeschützt betrachtet.</span><span class="sxs-lookup"><span data-stu-id="48ae7-109">Conceptually, these variables are considered to be read-only.</span></span> <span data-ttu-id="48ae7-110">Obwohl Sie in geschrieben werden **können** , sollten Sie aus Gründen der Abwärtskompatibilität **nicht** in schreiben.</span><span class="sxs-lookup"><span data-stu-id="48ae7-110">Even though they **can** be written to, for backward compatibility they **should not** be written to.</span></span>

<span data-ttu-id="48ae7-111">Im folgenden finden Sie eine Liste der automatischen Variablen in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="48ae7-111">Here is a list of the automatic variables in PowerShell:</span></span>

### <a name=""></a>$$

<span data-ttu-id="48ae7-112">Enthält das letzte Token in der letzten Zeile, die von der Sitzung empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="48ae7-112">Contains the last token in the last line received by the session.</span></span>

### <a name=""></a><span data-ttu-id="48ae7-113">$?</span><span class="sxs-lookup"><span data-stu-id="48ae7-113">$?</span></span>

<span data-ttu-id="48ae7-114">Enthält den Ausführungs Status des letzten Befehls.</span><span class="sxs-lookup"><span data-stu-id="48ae7-114">Contains the execution status of the last command.</span></span> <span data-ttu-id="48ae7-115">Sie enthält **true** , wenn der letzte Befehl erfolgreich war, und **false** , wenn Sie fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="48ae7-115">It contains **True** if the last command succeeded and **False** if it failed.</span></span>

<span data-ttu-id="48ae7-116">Für Cmdlets und erweiterte Funktionen, die auf mehreren Stufen in einer Pipeline ausgeführt werden (z. b. sowohl in `process` -als auch in- `end` Blöcken), wird der Aufruf `this.WriteError()` von bzw `$PSCmdlet.WriteError()` . an einem beliebigen Punkt `$?` auf **false** festgelegt, wie `this.ThrowTerminatingError()` und `$PSCmdlet.ThrowTerminatingError()` .</span><span class="sxs-lookup"><span data-stu-id="48ae7-116">For cmdlets and advanced functions that are run at multiple stages in a pipeline, for example in both `process` and `end` blocks, calling `this.WriteError()` or `$PSCmdlet.WriteError()` respectively at any point will set `$?` to **False**, as will `this.ThrowTerminatingError()` and `$PSCmdlet.ThrowTerminatingError()`.</span></span>

<span data-ttu-id="48ae7-117">Das `Write-Error` Cmdlet legt `$?` nach der Ausführung immer **false** fest, wird jedoch nicht auf false festgelegt, `$?` Wenn eine Funktion aufgerufen wird: </span><span class="sxs-lookup"><span data-stu-id="48ae7-117">The `Write-Error` cmdlet always sets `$?` to **False** immediately after it is executed, but will not set `$?` to **False** for a function calling it:</span></span>

```powershell
function Test-WriteError
{
    Write-Error "Bad"
    $? # $false
}

Test-WriteError
$? # $true
```

<span data-ttu-id="48ae7-118">Zum letzteren Zweck `$PSCmdlet.WriteError()` sollte stattdessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-118">For the latter purpose, `$PSCmdlet.WriteError()` should be used instead.</span></span>

<span data-ttu-id="48ae7-119">Bei nativen Befehlen (ausführbare Dateien) `$?` wird auf **true** festgelegt, wenn den `$LASTEXITCODE` Wert 0 hat, und auf **false** festgelegt, wenn `$LASTEXITCODE` ein beliebiger anderer Wert ist.</span><span class="sxs-lookup"><span data-stu-id="48ae7-119">For native commands (executables), `$?` is set to **True** when `$LASTEXITCODE` is 0, and set to **False** when `$LASTEXITCODE` is any other value.</span></span>

> [!NOTE]
> <span data-ttu-id="48ae7-120">Bis PowerShell 7, das eine-Anweisung in Klammern enthält `(...)` , wird die Teil Ausdruck-Syntax `$(...)` oder der Array Ausdruck `@(...)` immer `$?` auf **true** zurückgesetzt, sodass `(Write-Error)` `$?` als **true** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-120">Until PowerShell 7, containing a statement within parentheses `(...)`, subexpression syntax `$(...)` or array expression `@(...)` always reset `$?` to **True**, so that `(Write-Error)` shows `$?` as **True**.</span></span>
> <span data-ttu-id="48ae7-121">Dies wurde in PowerShell 7 geändert, sodass `$?` immer den tatsächlichen Erfolg der letzten Befehlsausführung in diesen Ausdrücken widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-121">This has been changed in PowerShell 7, so that `$?` will always reflect the actual success of the last command run in these expressions.</span></span>

### <a name=""></a>$^

<span data-ttu-id="48ae7-122">Enthält das erste Token in der letzten Zeile, die von der Sitzung empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="48ae7-122">Contains the first token in the last line received by the session.</span></span>

### <a name="_"></a><span data-ttu-id="48ae7-123">$_</span><span class="sxs-lookup"><span data-stu-id="48ae7-123">$_</span></span>

<span data-ttu-id="48ae7-124">Wie in `$PSItem`.</span><span class="sxs-lookup"><span data-stu-id="48ae7-124">Same as `$PSItem`.</span></span> <span data-ttu-id="48ae7-125">Enthält das aktuelle-Objekt im Pipeline Objekt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-125">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="48ae7-126">Sie können diese Variable in Befehlen verwenden, die eine Aktion für jedes Objekt oder für ausgewählte Objekte in einer Pipeline ausführen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-126">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="args"></a><span data-ttu-id="48ae7-127">$args</span><span class="sxs-lookup"><span data-stu-id="48ae7-127">$args</span></span>

<span data-ttu-id="48ae7-128">Enthält ein Array von Werten für nicht deklarierte Parameter, die an eine Funktion, ein Skript oder einen Skriptblock übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-128">Contains an array of values for undeclared parameters that are passed to a function, script, or script block.</span></span> <span data-ttu-id="48ae7-129">Wenn Sie eine Funktion erstellen, können Sie die Parameter mit dem- `param` Schlüsselwort deklarieren oder indem Sie eine durch Trennzeichen getrennte Liste von Parametern nach dem Funktionsnamen in Klammern einfügen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-129">When you create a function, you can declare the parameters by using the `param` keyword or by adding a comma-separated list of parameters in parentheses after the function name.</span></span>

<span data-ttu-id="48ae7-130">In einer Ereignis Aktion enthält die- `$Args` Variable-Objekte, die die Ereignis Argumente des zu verarbeitenden Ereignisses darstellen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-130">In an event action, the `$Args` variable contains objects that represent the event arguments of the event that is being processed.</span></span> <span data-ttu-id="48ae7-131">Diese Variable wird nur innerhalb des `Action` Blocks eines Ereignis Registrierungs Befehls aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-131">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="48ae7-132">Der Wert dieser Variablen befindet sich auch in der **sourceargs** -Eigenschaft des **psiebargs** -Objekts, das `Get-Event` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-132">The value of this variable can also be found in the **SourceArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="consolefilename"></a><span data-ttu-id="48ae7-133">$ConsoleFileName</span><span class="sxs-lookup"><span data-stu-id="48ae7-133">$ConsoleFileName</span></span>

<span data-ttu-id="48ae7-134">Enthält den Pfad der Konsolen Datei ( `.psc1` ), die zuletzt in der Sitzung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="48ae7-134">Contains the path of the console file (`.psc1`) that was most recently used in the session.</span></span> <span data-ttu-id="48ae7-135">Diese Variable wird aufgefüllt, wenn Sie PowerShell mit dem **PsConsoleFile** -Parameter starten oder wenn Sie das `Export-Console` Cmdlet verwenden, um Snap-in-Namen in eine Konsolen Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="48ae7-135">This variable is populated when you start PowerShell with the **PSConsoleFile** parameter or when you use the `Export-Console` cmdlet to export snap-in names to a console file.</span></span>

<span data-ttu-id="48ae7-136">Wenn Sie das `Export-Console` Cmdlet ohne Parameter verwenden, wird automatisch die Konsolen Datei aktualisiert, die zuletzt in der Sitzung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="48ae7-136">When you use the `Export-Console` cmdlet without parameters, it automatically updates the console file that was most recently used in the session.</span></span> <span data-ttu-id="48ae7-137">Sie können diese automatische Variable verwenden, um zu bestimmen, welche Datei aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-137">You can use this automatic variable to determine which file will be updated.</span></span>

### <a name="error"></a><span data-ttu-id="48ae7-138">$Error</span><span class="sxs-lookup"><span data-stu-id="48ae7-138">$Error</span></span>

<span data-ttu-id="48ae7-139">Enthält ein Array von Fehler Objekten, die die letzten Fehler darstellen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-139">Contains an array of error objects that represent the most recent errors.</span></span>
<span data-ttu-id="48ae7-140">Der letzte Fehler ist das erste Fehler Objekt im Array `$Error[0]` .</span><span class="sxs-lookup"><span data-stu-id="48ae7-140">The most recent error is the first error object in the array `$Error[0]`.</span></span>

<span data-ttu-id="48ae7-141">Um zu verhindern, dass dem Array ein Fehler hinzugefügt wird `$Error` , verwenden Sie den allgemeinen **ErrorAction** -Parameter mit dem Wert **Ignore**.</span><span class="sxs-lookup"><span data-stu-id="48ae7-141">To prevent an error from being added to the `$Error` array, use the **ErrorAction** common parameter with a value of **Ignore**.</span></span> <span data-ttu-id="48ae7-142">Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="48ae7-142">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

### <a name="event"></a><span data-ttu-id="48ae7-143">$Event</span><span class="sxs-lookup"><span data-stu-id="48ae7-143">$Event</span></span>

<span data-ttu-id="48ae7-144">Enthält ein **peventargs** -Objekt, das das Ereignis darstellt, das gerade verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-144">Contains a **PSEventArgs** object that represents the event that is being processed.</span></span> <span data-ttu-id="48ae7-145">Diese Variable wird nur innerhalb des `Action` Blocks eines Ereignis Registrierungs Befehls (z. b.) aufgefüllt `Register-ObjectEvent` .</span><span class="sxs-lookup"><span data-stu-id="48ae7-145">This variable is populated only within the `Action` block of an event registration command, such as `Register-ObjectEvent`.</span></span> <span data-ttu-id="48ae7-146">Der Wert dieser Variablen ist das gleiche Objekt, das vom `Get-Event` Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-146">The value of this variable is the same object that the `Get-Event` cmdlet returns.</span></span> <span data-ttu-id="48ae7-147">Daher können Sie die Eigenschaften der `Event` Variablen (z. b.) `$Event.TimeGenerated` in einem `Action` Skriptblock verwenden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-147">Therefore, you can use the properties of the `Event` variable, such as `$Event.TimeGenerated`, in an `Action` script block.</span></span>

### <a name="eventargs"></a><span data-ttu-id="48ae7-148">$EventArgs</span><span class="sxs-lookup"><span data-stu-id="48ae7-148">$EventArgs</span></span>

<span data-ttu-id="48ae7-149">Enthält ein-Objekt, das das erste Ereignis Argument darstellt, das von **EventArgs** des-Ereignisses abgeleitet wird, das gerade verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-149">Contains an object that represents the first event argument that derives from **EventArgs** of the event that is being processed.</span></span> <span data-ttu-id="48ae7-150">Diese Variable wird nur innerhalb des `Action` Blocks eines Ereignis Registrierungs Befehls aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-150">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="48ae7-151">Der Wert dieser Variablen befindet sich auch in der **sourceeventargs** -Eigenschaft des **peventargs** -Objekts, das `Get-Event` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-151">The value of this variable can also be found in the **SourceEventArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="eventsubscriber"></a><span data-ttu-id="48ae7-152">$EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="48ae7-152">$EventSubscriber</span></span>

<span data-ttu-id="48ae7-153">Enthält ein **peventsubscriber** -Objekt, das den Ereignis Abonnenten des-Ereignisses darstellt, das gerade verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-153">Contains a **PSEventSubscriber** object that represents the event subscriber of the event that is being processed.</span></span> <span data-ttu-id="48ae7-154">Diese Variable wird nur innerhalb des `Action` Blocks eines Ereignis Registrierungs Befehls aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-154">This variable is populated only within the `Action` block of an event registration command.</span></span> <span data-ttu-id="48ae7-155">Der Wert dieser Variablen ist das gleiche Objekt, das vom `Get-EventSubscriber` Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-155">The value of this variable is the same object that the `Get-EventSubscriber` cmdlet returns.</span></span>

### <a name="executioncontext"></a><span data-ttu-id="48ae7-156">$ExecutionContext</span><span class="sxs-lookup"><span data-stu-id="48ae7-156">$ExecutionContext</span></span>

<span data-ttu-id="48ae7-157">Enthält ein **engineintrinsics** -Objekt, das den Ausführungs Kontext des PowerShell-Hosts darstellt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-157">Contains an **EngineIntrinsics** object that represents the execution context of the PowerShell host.</span></span> <span data-ttu-id="48ae7-158">Sie können diese Variable verwenden, um die für Cmdlets verfügbaren Ausführungs Objekte zu finden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-158">You can use this variable to find the execution objects that are available to cmdlets.</span></span>

### <a name="false"></a><span data-ttu-id="48ae7-159">$false</span><span class="sxs-lookup"><span data-stu-id="48ae7-159">$false</span></span>

<span data-ttu-id="48ae7-160">Enthält **false**.</span><span class="sxs-lookup"><span data-stu-id="48ae7-160">Contains **False**.</span></span> <span data-ttu-id="48ae7-161">Sie können diese Variable verwenden, um **false** in Befehlen und Skripts darzustellen, anstatt die Zeichenfolge "false" zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-161">You can use this variable to represent **False** in commands and scripts instead of using the string "false".</span></span> <span data-ttu-id="48ae7-162">Die Zeichenfolge kann als **true** interpretiert werden, wenn Sie in eine nicht leere Zeichenfolge oder in eine ganze Zahl ungleich 0 (null) konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-162">The string can be interpreted as **True** if it's converted to a non-empty string or to a non-zero integer.</span></span>

### <a name="foreach"></a><span data-ttu-id="48ae7-163">$foreach</span><span class="sxs-lookup"><span data-stu-id="48ae7-163">$foreach</span></span>

<span data-ttu-id="48ae7-164">Enthält den Enumerator (nicht die resultierenden Werte) einer [foreach](about_ForEach.md) -Schleife.</span><span class="sxs-lookup"><span data-stu-id="48ae7-164">Contains the enumerator (not the resulting values) of a [ForEach](about_ForEach.md) loop.</span></span> <span data-ttu-id="48ae7-165">Die `$ForEach` Variable ist nur vorhanden, während die `ForEach` Schleife ausgeführt wird. Sie wird gelöscht, nachdem die Schleife abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="48ae7-165">The `$ForEach` variable exists only while the `ForEach` loop is running; it's deleted after the loop is completed.</span></span>

<span data-ttu-id="48ae7-166">Enumeratoren enthalten Eigenschaften und Methoden, mit denen Sie Schleifen Werte abrufen und die aktuelle Schleifen Iterationen ändern können.</span><span class="sxs-lookup"><span data-stu-id="48ae7-166">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="48ae7-167">Weitere Informationen finden Sie unter [Verwenden von Enumeratoren](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="48ae7-167">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="home"></a><span data-ttu-id="48ae7-168">$HOME</span><span class="sxs-lookup"><span data-stu-id="48ae7-168">$HOME</span></span>

<span data-ttu-id="48ae7-169">Enthält den vollständigen Pfad des Basisverzeichnisses des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="48ae7-169">Contains the full path of the user's home directory.</span></span> <span data-ttu-id="48ae7-170">Diese Variable entspricht in der Regel den `"$env:homedrive$env:homepath"` Windows-Umgebungsvariablen `C:\Users\<UserName>` .</span><span class="sxs-lookup"><span data-stu-id="48ae7-170">This variable is the equivalent of the `"$env:homedrive$env:homepath"` Windows environment variables, typically `C:\Users\<UserName>`.</span></span>

### <a name="host"></a><span data-ttu-id="48ae7-171">$Host</span><span class="sxs-lookup"><span data-stu-id="48ae7-171">$Host</span></span>

<span data-ttu-id="48ae7-172">Enthält ein-Objekt, das die aktuelle Host Anwendung für PowerShell darstellt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-172">Contains an object that represents the current host application for PowerShell.</span></span> <span data-ttu-id="48ae7-173">Sie können diese Variable verwenden, um den aktuellen Host in Befehlen darzustellen oder um die Eigenschaften des Hosts (z. b. oder) anzuzeigen oder zu ändern `$Host.version` `$Host.CurrentCulture` `$host.ui.rawui.setbackgroundcolor("Red")` .</span><span class="sxs-lookup"><span data-stu-id="48ae7-173">You can use this variable to represent the current host in commands or to display or change the properties of the host, such as `$Host.version` or `$Host.CurrentCulture`, or `$host.ui.rawui.setbackgroundcolor("Red")`.</span></span>

### <a name="input"></a><span data-ttu-id="48ae7-174">$input</span><span class="sxs-lookup"><span data-stu-id="48ae7-174">$input</span></span>

<span data-ttu-id="48ae7-175">Enthält einen Enumerator, der alle Eingaben auflistet, die an eine Funktion weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-175">Contains an enumerator that enumerates all input that is passed to a function.</span></span> <span data-ttu-id="48ae7-176">Die `$input` -Variable ist nur für Funktionen und Skriptblöcke verfügbar (bei denen es sich um unbenannte Funktionen handelt).</span><span class="sxs-lookup"><span data-stu-id="48ae7-176">The `$input` variable is available only to functions and script blocks (which are unnamed functions).</span></span>

- <span data-ttu-id="48ae7-177">In einer Funktion ohne einen- `Begin` ,- `Process` oder- `End` Block `$input` Listet die-Variable die Auflistung aller Eingaben für die Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="48ae7-177">In a function without a `Begin`, `Process`, or `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

- <span data-ttu-id="48ae7-178">Im- `Begin` Block enthält die- `$input` Variable keine Daten.</span><span class="sxs-lookup"><span data-stu-id="48ae7-178">In the `Begin` block, the `$input` variable contains no data.</span></span>

- <span data-ttu-id="48ae7-179">Im- `Process` Block enthält die- `$input` Variable das-Objekt, das sich zurzeit in der Pipeline befindet.</span><span class="sxs-lookup"><span data-stu-id="48ae7-179">In the `Process` block, the `$input` variable contains the object that is currently in the pipeline.</span></span>

- <span data-ttu-id="48ae7-180">Im- `End` Block listet die- `$input` Variable die Auflistung aller Eingaben für die-Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="48ae7-180">In the `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

  > [!NOTE]
  > <span data-ttu-id="48ae7-181">Sie können die `$input` Variable nicht innerhalb des Prozess Blocks und des endblocks in derselben Funktion oder in demselben Skriptblock verwenden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-181">You cannot use the `$input` variable inside both the Process block and the End block in the same function or script block.</span></span>

<span data-ttu-id="48ae7-182">Da `$input` ein Enumerator ist, bewirkt der Zugriff auf eine der Eigenschaften, dass `$input` nicht mehr verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="48ae7-182">Since `$input` is an enumerator, accessing any of it's properties causes `$input` to no longer be available.</span></span> <span data-ttu-id="48ae7-183">Sie können `$input` in einer anderen Variablen speichern, um die Eigenschaften wiederzuverwenden `$input` .</span><span class="sxs-lookup"><span data-stu-id="48ae7-183">You can store `$input` in another variable to reuse the `$input` properties.</span></span>

<span data-ttu-id="48ae7-184">Enumeratoren enthalten Eigenschaften und Methoden, mit denen Sie Schleifen Werte abrufen und die aktuelle Schleifen Iterationen ändern können.</span><span class="sxs-lookup"><span data-stu-id="48ae7-184">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="48ae7-185">Weitere Informationen finden Sie unter [Verwenden von Enumeratoren](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="48ae7-185">For more information, see [Using Enumerators](#using-enumerators).</span></span>

<span data-ttu-id="48ae7-186">Die- `$input` Variable ist auch für den Befehl verfügbar, der durch den-Parameter von angegeben wird, `-Command` Wenn Sie `pwsh` von der Befehlszeile aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-186">The `$input` variable is also available to the command specified by the `-Command` parameter of `pwsh` when invoked from the command line.</span></span> <span data-ttu-id="48ae7-187">Das folgende Beispiel wird in der Windows-Befehlsshell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-187">The following example is run from the Windows Command shell.</span></span>

```CMD
echo Hello | powershell -Command """$input World!"""
```

### <a name="lastexitcode"></a><span data-ttu-id="48ae7-188">$LastExitCode</span><span class="sxs-lookup"><span data-stu-id="48ae7-188">$LastExitCode</span></span>

<span data-ttu-id="48ae7-189">Enthält den Exitcode des letzten Windows-basierten Programms, das ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="48ae7-189">Contains the exit code of the last Windows-based program that was run.</span></span>

### <a name="matches"></a><span data-ttu-id="48ae7-190">$Matches</span><span class="sxs-lookup"><span data-stu-id="48ae7-190">$Matches</span></span>

<span data-ttu-id="48ae7-191">Die `$Matches` -Variable funktioniert mit `-match` den `-notmatch` Operatoren und.</span><span class="sxs-lookup"><span data-stu-id="48ae7-191">The `$Matches` variable works with the `-match` and `-notmatch` operators.</span></span>
<span data-ttu-id="48ae7-192">Wenn Sie skalare Eingaben an den `-match` `-notmatch` -Operator oder den-Operator übermitteln und eine Übereinstimmung erkannt wird, wird ein boolescher Wert zurückgegeben, und die `$Matches` Automatische Variable wird mit einer Hash Tabelle mit allen übereinstimmenden Zeichen folgen Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-192">When you submit scalar input to the `-match` or `-notmatch` operator, and either one detects a match, they return a Boolean value and populate the `$Matches` automatic variable with a hash table of any string values that were matched.</span></span> <span data-ttu-id="48ae7-193">Die `$Matches` Hash Tabelle kann auch mit Erfassungen aufgefüllt werden, wenn Sie reguläre Ausdrücke mit dem- `-match` Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-193">The `$Matches` hash table can also be populated with captures when you use regular expressions with the `-match` operator.</span></span>

<span data-ttu-id="48ae7-194">Weitere Informationen zum- `-match` Operator finden Sie unter [about_Comparison_Operators](about_comparison_operators.md).</span><span class="sxs-lookup"><span data-stu-id="48ae7-194">For more information about the `-match` operator, see [about_Comparison_Operators](about_comparison_operators.md).</span></span> <span data-ttu-id="48ae7-195">Weitere Informationen zu regulären Ausdrücken finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="48ae7-195">For more information on regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

<span data-ttu-id="48ae7-196">Die- `$Matches` Variable kann auch in einer- `switch` Anweisung mit dem-Parameter verwendet werden `-Regex` .</span><span class="sxs-lookup"><span data-stu-id="48ae7-196">The `$Matches` variable also works in a `switch` statement with the `-Regex` parameter.</span></span> <span data-ttu-id="48ae7-197">Es wird auf die gleiche Weise wie die `-match` -und- `-notmatch` Operatoren aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-197">It's populated the same way as the `-match` and `-notmatch` operators.</span></span>
<span data-ttu-id="48ae7-198">Weitere Informationen zur- `switch` Anweisung finden Sie unter [about_Switch](about_Switch.md).</span><span class="sxs-lookup"><span data-stu-id="48ae7-198">For more information about the `switch` statement, see [about_Switch](about_Switch.md).</span></span>

### <a name="myinvocation"></a><span data-ttu-id="48ae7-199">$MyInvocation</span><span class="sxs-lookup"><span data-stu-id="48ae7-199">$MyInvocation</span></span>

<span data-ttu-id="48ae7-200">Enthält Informationen über den aktuellen Befehl, z. b. den Namen, die Parameter, die Parameterwerte und Informationen darüber, wie der Befehl gestartet, aufgerufen oder aufgerufen wurde, z. b. der Name des Skripts, das den aktuellen Befehl aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="48ae7-200">Contains information about the current command, such as the name, parameters, parameter values, and information about how the command was started, called, or invoked, such as the name of the script that called the current command.</span></span>

<span data-ttu-id="48ae7-201">`$MyInvocation` wird nur für Skripts, Funktionen und Skriptblöcke aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-201">`$MyInvocation` is populated only for scripts, function, and script blocks.</span></span> <span data-ttu-id="48ae7-202">Sie können die Informationen im **System. Management. Automation. invocationinfo** -Objekt verwenden, das `$MyInvocation` im aktuellen Skript zurückgibt, wie z. b. den Pfad und den Dateinamen des Skripts ( `$MyInvocation.MyCommand.Path` ) oder den Namen einer Funktion ( `$MyInvocation.MyCommand.Name` ), um den aktuellen Befehl zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="48ae7-202">You can use the information in the **System.Management.Automation.InvocationInfo** object that `$MyInvocation` returns in the current script, such as the path and file name of the script (`$MyInvocation.MyCommand.Path`) or the name of a function (`$MyInvocation.MyCommand.Name`) to identify the current command.</span></span> <span data-ttu-id="48ae7-203">Dies ist besonders nützlich, um den Namen des aktuellen Skripts zu suchen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-203">This is particularly useful for finding the name of the current script.</span></span>

<span data-ttu-id="48ae7-204">Ab PowerShell 3,0 `MyInvocation` verfügt über die folgenden neuen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="48ae7-204">Beginning in PowerShell 3.0, `MyInvocation` has the following new properties.</span></span>

| <span data-ttu-id="48ae7-205">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="48ae7-205">Property</span></span>      | <span data-ttu-id="48ae7-206">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48ae7-206">Description</span></span>                                         |
| ------------- | --------------------------------------------------- |
| <span data-ttu-id="48ae7-207">**PSScriptRoot**</span><span class="sxs-lookup"><span data-stu-id="48ae7-207">**PSScriptRoot**</span></span>  | <span data-ttu-id="48ae7-208">Enthält den vollständigen Pfad des aufgerufenen Skripts.</span><span class="sxs-lookup"><span data-stu-id="48ae7-208">Contains the full path to the script that invoked</span></span>   |
|               | <span data-ttu-id="48ae7-209">der aktuelle Befehl.</span><span class="sxs-lookup"><span data-stu-id="48ae7-209">the current command.</span></span> <span data-ttu-id="48ae7-210">Der Wert dieser Eigenschaft ist</span><span class="sxs-lookup"><span data-stu-id="48ae7-210">The value of this property is</span></span>  |
|               | <span data-ttu-id="48ae7-211">wird nur aufgefüllt, wenn der Aufrufer ein Skript ist.</span><span class="sxs-lookup"><span data-stu-id="48ae7-211">populated only when the caller is a script.</span></span>         |
| <span data-ttu-id="48ae7-212">**Pscommandpath**</span><span class="sxs-lookup"><span data-stu-id="48ae7-212">**PSCommandPath**</span></span> | <span data-ttu-id="48ae7-213">Enthält den vollständigen Pfad und den Dateinamen des Skripts.</span><span class="sxs-lookup"><span data-stu-id="48ae7-213">Contains the full path and file name of the script</span></span>  |
|               | <span data-ttu-id="48ae7-214">, der den aktuellen Befehl aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="48ae7-214">that invoked the current command.</span></span> <span data-ttu-id="48ae7-215">Der Wert dieses</span><span class="sxs-lookup"><span data-stu-id="48ae7-215">The value of this</span></span> |
|               | <span data-ttu-id="48ae7-216">die Eigenschaft wird nur aufgefüllt, wenn der Aufrufer ein</span><span class="sxs-lookup"><span data-stu-id="48ae7-216">property is populated only when the caller is a</span></span>     |
|               | <span data-ttu-id="48ae7-217">„Hello World!“.</span><span class="sxs-lookup"><span data-stu-id="48ae7-217">script.</span></span>                                             |

<span data-ttu-id="48ae7-218">Im Gegensatz zu den `$PSScriptRoot` `$PSCommandPath` automatischen Variablen und enthalten die Eigenschaften **psscriptroot** und **pscommandpath** der `$MyInvocation` automatischen Variablen Informationen über den aufrufenden oder das aufrufende Skript, nicht über das aktuelle Skript.</span><span class="sxs-lookup"><span data-stu-id="48ae7-218">Unlike the `$PSScriptRoot` and `$PSCommandPath` automatic variables, the **PSScriptRoot** and **PSCommandPath** properties of the `$MyInvocation` automatic variable contain information about the invoker or calling script, not the current script.</span></span>

### <a name="nestedpromptlevel"></a><span data-ttu-id="48ae7-219">$NestedPromptLevel</span><span class="sxs-lookup"><span data-stu-id="48ae7-219">$NestedPromptLevel</span></span>

<span data-ttu-id="48ae7-220">Enthält die aktuelle Eingabe Aufforderungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="48ae7-220">Contains the current prompt level.</span></span> <span data-ttu-id="48ae7-221">Der Wert 0 gibt die ursprüngliche Eingabe Aufforderungs Ebene an.</span><span class="sxs-lookup"><span data-stu-id="48ae7-221">A value of 0 indicates the original prompt level.</span></span> <span data-ttu-id="48ae7-222">Der Wert wird erhöht, wenn Sie eine eingefügte Ebene eingeben und dekrementiert werden, wenn Sie Sie beenden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-222">The value is incremented when you enter a nested level and decremented when you exit it.</span></span>

<span data-ttu-id="48ae7-223">PowerShell zeigt z. b. eine eingefügte Eingabeaufforderung an, wenn Sie die- `$Host.EnterNestedPrompt` Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-223">For example, PowerShell presents a nested command prompt when you use the `$Host.EnterNestedPrompt` method.</span></span> <span data-ttu-id="48ae7-224">PowerShell zeigt auch eine eingefügte Eingabeaufforderung an, wenn Sie einen Breakpoint im PowerShell-Debugger erreichen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-224">PowerShell also presents a nested command prompt when you reach a breakpoint in the PowerShell debugger.</span></span>

<span data-ttu-id="48ae7-225">Wenn Sie eine eingefügte Eingabeaufforderung eingeben, hält PowerShell den aktuellen Befehl an, speichert den Ausführungs Kontext und erhöht den Wert der `$NestedPromptLevel` Variablen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-225">When you enter a nested prompt, PowerShell pauses the current command, saves the execution context, and increments the value of the `$NestedPromptLevel` variable.</span></span> <span data-ttu-id="48ae7-226">Um zusätzliche Eingabe Aufforderungen für ein Eingabefenster (bis zu 128 Ebenen) zu erstellen oder zur ursprünglichen Eingabeaufforderung zurückzukehren, führen Sie den Befehl aus, oder geben Sie ein `exit` .</span><span class="sxs-lookup"><span data-stu-id="48ae7-226">To create additional nested command prompts (up to 128 levels) or to return to the original command prompt, complete the command, or type `exit`.</span></span>

<span data-ttu-id="48ae7-227">Die- `$NestedPromptLevel` Variable hilft Ihnen beim Nachverfolgen der Eingabe Aufforderungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="48ae7-227">The `$NestedPromptLevel` variable helps you track the prompt level.</span></span> <span data-ttu-id="48ae7-228">Sie können eine Alternative PowerShell-Eingabeaufforderung erstellen, die diesen Wert enthält, sodass er immer sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="48ae7-228">You can create an alternative PowerShell command prompt that includes this value so that it's always visible.</span></span>

### <a name="null"></a><span data-ttu-id="48ae7-229">$null</span><span class="sxs-lookup"><span data-stu-id="48ae7-229">$null</span></span>

<span data-ttu-id="48ae7-230">`$null` eine automatische Variable, die einen **null** -Wert oder einen leeren Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="48ae7-230">`$null` is an automatic variable that contains a **null** or empty value.</span></span> <span data-ttu-id="48ae7-231">Mit dieser Variablen können Sie einen fehlenden oder nicht definierten Wert in Befehlen und Skripts darstellen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-231">You can use this variable to represent an absent or undefined value in commands and scripts.</span></span>

<span data-ttu-id="48ae7-232">PowerShell behandelt `$null` als ein Objekt mit einem Wert, d. h. als expliziter Platzhalter, damit Sie `$null` einen leeren Wert in einer Reihe von Werten darstellen können.</span><span class="sxs-lookup"><span data-stu-id="48ae7-232">PowerShell treats `$null` as an object with a value, that is, as an explicit placeholder, so you can use `$null` to represent an empty value in a series of values.</span></span>

<span data-ttu-id="48ae7-233">Wenn z. b `$null` . in einer Auflistung enthalten ist, wird Sie als eines der-Objekte gezählt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-233">For example, when `$null` is included in a collection, it's counted as one of the objects.</span></span>

```powershell
$a = "one", $null, "three"
$a.count
```

```Output
3
```

<span data-ttu-id="48ae7-234">Wenn Sie die `$null` Variable an das `ForEach-Object` Cmdlet weiterreichen, generiert Sie einen Wert für `$null` , genau wie für die anderen Objekte.</span><span class="sxs-lookup"><span data-stu-id="48ae7-234">If you pipe the `$null` variable to the `ForEach-Object` cmdlet, it generates a value for `$null`, just as it does for the other objects</span></span>

```powershell
"one", $null, "three" | ForEach-Object { "Hello " + $_}
```

```Output
Hello one
Hello
Hello three
```

<span data-ttu-id="48ae7-235">Daher können Sie `$null` nicht verwenden, um **keinen Parameterwert** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-235">As a result, you can't use `$null` to mean **no parameter value**.</span></span> <span data-ttu-id="48ae7-236">Der Parameterwert `$null` überschreibt den Standardparameter Wert.</span><span class="sxs-lookup"><span data-stu-id="48ae7-236">A parameter value of `$null` overrides the default parameter value.</span></span>

<span data-ttu-id="48ae7-237">Da die Variable von PowerShell jedoch `$null` als Platzhalter behandelt wird, können Sie Sie in Skripts wie dem folgenden verwenden, was nicht funktioniert, wenn Sie `$null` ignoriert wurden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-237">However, because PowerShell treats the `$null` variable as a placeholder, you can use it in scripts like the following one, which wouldn't work if `$null` were ignored.</span></span>

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

### <a name="pid"></a><span data-ttu-id="48ae7-238">$PID</span><span class="sxs-lookup"><span data-stu-id="48ae7-238">$PID</span></span>

<span data-ttu-id="48ae7-239">Enthält die Prozess-ID (PID) des Prozesses, in dem die aktuelle PowerShell-Sitzung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-239">Contains the process identifier (PID) of the process that is hosting the current PowerShell session.</span></span>

### <a name="profile"></a><span data-ttu-id="48ae7-240">$PROFILE</span><span class="sxs-lookup"><span data-stu-id="48ae7-240">$PROFILE</span></span>

<span data-ttu-id="48ae7-241">Enthält den vollständigen Pfad des PowerShell-Profils für den aktuellen Benutzer und die aktuelle Host Anwendung.</span><span class="sxs-lookup"><span data-stu-id="48ae7-241">Contains the full path of the PowerShell profile for the current user and the current host application.</span></span> <span data-ttu-id="48ae7-242">Mit dieser Variablen können Sie das Profil in Befehlen darstellen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-242">You can use this variable to represent the profile in commands.</span></span> <span data-ttu-id="48ae7-243">Beispielsweise können Sie ihn in einem Befehl verwenden, um zu bestimmen, ob ein Profil erstellt wurde:</span><span class="sxs-lookup"><span data-stu-id="48ae7-243">For example, you can use it in a command to determine whether a profile has been created:</span></span>

```powershell
Test-Path $PROFILE
```

<span data-ttu-id="48ae7-244">Oder Sie können Sie in einem Befehl verwenden, um ein Profil zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="48ae7-244">Or, you can use it in a command to create a profile:</span></span>

```powershell
New-Item -ItemType file -Path $PROFILE -Force
```

<span data-ttu-id="48ae7-245">Sie können Sie in einem Befehl verwenden, um das Profil in **notepad.exe** zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="48ae7-245">You can use it in a command to open the profile in **notepad.exe**:</span></span>

```powershell
notepad.exe $PROFILE
```

### <a name="psboundparameters"></a><span data-ttu-id="48ae7-246">$PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="48ae7-246">$PSBoundParameters</span></span>

<span data-ttu-id="48ae7-247">Enthält ein Wörterbuch mit den Parametern, die an ein Skript oder eine Funktion und ihre aktuellen Werte übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-247">Contains a dictionary of the parameters that are passed to a script or function and their current values.</span></span> <span data-ttu-id="48ae7-248">Diese Variable hat nur einen Wert in einem Bereich, in dem Parameter deklariert werden, z. b. ein Skript oder eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="48ae7-248">This variable has a value only in a scope where parameters are declared, such as a script or function.</span></span> <span data-ttu-id="48ae7-249">Sie können Sie verwenden, um die aktuellen Parameterwerte anzuzeigen oder zu ändern oder um Parameterwerte an ein anderes Skript oder eine andere Funktion zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="48ae7-249">You can use it to display or change the current values of parameters or to pass parameter values to another script or function.</span></span>

<span data-ttu-id="48ae7-250">In diesem Beispiel übergibt die **test2** -Funktion `$PSBoundParameters` an die **test1** -Funktion.</span><span class="sxs-lookup"><span data-stu-id="48ae7-250">In this example, the **Test2** function passes the `$PSBoundParameters` to the **Test1** function.</span></span> <span data-ttu-id="48ae7-251">Die `$PSBoundParameters` werden im Format von **Key** und **value** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-251">The `$PSBoundParameters` are displayed in the format of **Key** and **Value**.</span></span>

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

### <a name="pscmdlet"></a><span data-ttu-id="48ae7-252">$PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="48ae7-252">$PSCmdlet</span></span>

<span data-ttu-id="48ae7-253">Enthält ein-Objekt, das das Cmdlet oder die erweiterte Funktion darstellt, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-253">Contains an object that represents the cmdlet or advanced function that's being run.</span></span>

<span data-ttu-id="48ae7-254">Sie können die Eigenschaften und Methoden des-Objekts im Cmdlet oder Funktionscode verwenden, um auf die Nutzungsbedingungen zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="48ae7-254">You can use the properties and methods of the object in your cmdlet or function code to respond to the conditions of use.</span></span> <span data-ttu-id="48ae7-255">Beispielsweise enthält die **parametersetname** -Eigenschaft den Namen des verwendeten Parameter Satzes, und die Methode " **schuldprocess** " fügt die Parameter " **WhatIf** " und " **Confirm** " dem Cmdlet dynamisch hinzu.</span><span class="sxs-lookup"><span data-stu-id="48ae7-255">For example, the **ParameterSetName** property contains the name of the parameter set that's being used, and the **ShouldProcess** method adds the **WhatIf** and **Confirm** parameters to the cmdlet dynamically.</span></span>

<span data-ttu-id="48ae7-256">Weitere Informationen über die `$PSCmdlet` Automatische Variable finden Sie unter [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) und [about_Functions_Advanced](about_Functions_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="48ae7-256">For more information about the `$PSCmdlet` automatic variable, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) and [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

### <a name="pscommandpath"></a><span data-ttu-id="48ae7-257">$PSCommandPath</span><span class="sxs-lookup"><span data-stu-id="48ae7-257">$PSCommandPath</span></span>

<span data-ttu-id="48ae7-258">Enthält den vollständigen Pfad und den Dateinamen des Skripts, das gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-258">Contains the full path and file name of the script that's being run.</span></span> <span data-ttu-id="48ae7-259">Diese Variable ist in allen Skripts gültig.</span><span class="sxs-lookup"><span data-stu-id="48ae7-259">This variable is valid in all scripts.</span></span>

### <a name="psculture"></a><span data-ttu-id="48ae7-260">$PSCulture</span><span class="sxs-lookup"><span data-stu-id="48ae7-260">$PSCulture</span></span>

<span data-ttu-id="48ae7-261">Enthält den Namen der Kultur, die derzeit im Betriebssystem verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-261">Contains the name of the culture currently in use in the operating system.</span></span> <span data-ttu-id="48ae7-262">Die Kultur bestimmt das Anzeige Format von Elementen, z. b. Zahlen, Währungen und Datumsangaben, und wird in einem **System. Globalization. CultureInfo** -Objekt gespeichert.</span><span class="sxs-lookup"><span data-stu-id="48ae7-262">The culture determines the display format of items such as numbers, currency, and dates, and is stored in a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="48ae7-263">Verwenden `Get-Culture` Sie, um die Kultur des Computers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-263">Use `Get-Culture` to display the computer's culture.</span></span> <span data-ttu-id="48ae7-264">`$PSCulture` enthält den Wert der **Name** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="48ae7-264">`$PSCulture` contains the **Name** property's value.</span></span>

### <a name="psdebugcontext"></a><span data-ttu-id="48ae7-265">$PSDebugContext</span><span class="sxs-lookup"><span data-stu-id="48ae7-265">$PSDebugContext</span></span>

<span data-ttu-id="48ae7-266">Beim Debuggen enthält diese Variable Informationen zur Debugumgebung.</span><span class="sxs-lookup"><span data-stu-id="48ae7-266">While debugging, this variable contains information about the debugging environment.</span></span> <span data-ttu-id="48ae7-267">Andernfalls enthält Sie einen **null** -Wert.</span><span class="sxs-lookup"><span data-stu-id="48ae7-267">Otherwise, it contains a **null** value.</span></span> <span data-ttu-id="48ae7-268">Daher können Sie damit angeben, ob der Debugger über Steuerelemente verfügt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-268">As a result, you can use it to indicate whether the debugger has control.</span></span> <span data-ttu-id="48ae7-269">Wenn Sie aufgefüllt ist, enthält Sie ein **psdebugcontext** -Objekt mit **Breakpoints** und **invocationinfo** -Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="48ae7-269">When populated, it contains a **PsDebugContext** object that has **Breakpoints** and **InvocationInfo** properties.</span></span> <span data-ttu-id="48ae7-270">Die **invocationinfo** -Eigenschaft verfügt über mehrere nützliche Eigenschaften, einschließlich der **Location** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="48ae7-270">The **InvocationInfo** property has several useful properties, including the **Location** property.</span></span> <span data-ttu-id="48ae7-271">Die **Location** -Eigenschaft gibt den Pfad des Skripts an, das gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-271">The **Location** property indicates the path of the script that is being debugged.</span></span>

### <a name="pshome"></a><span data-ttu-id="48ae7-272">$PSHOME</span><span class="sxs-lookup"><span data-stu-id="48ae7-272">$PSHOME</span></span>

<span data-ttu-id="48ae7-273">Enthält den vollständigen Pfad des Installationsverzeichnisses für PowerShell (in der Regel `$env:windir\System32\PowerShell\v1.0` in Windows-Systemen).</span><span class="sxs-lookup"><span data-stu-id="48ae7-273">Contains the full path of the installation directory for PowerShell, typically, `$env:windir\System32\PowerShell\v1.0` in Windows systems.</span></span> <span data-ttu-id="48ae7-274">Sie können diese Variable in den Pfaden von PowerShell-Dateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-274">You can use this variable in the paths of PowerShell files.</span></span> <span data-ttu-id="48ae7-275">Mit dem folgenden Befehl werden z. b. die konzeptionellen Hilfe Themen nach der Word- **Variablen** durchsucht:</span><span class="sxs-lookup"><span data-stu-id="48ae7-275">For example, the following command searches the conceptual Help topics for the word **variable**:</span></span>

```powershell
Select-String -Pattern Variable -Path $pshome\*.txt
```

### <a name="psitem"></a><span data-ttu-id="48ae7-276">$PSItem</span><span class="sxs-lookup"><span data-stu-id="48ae7-276">$PSItem</span></span>

<span data-ttu-id="48ae7-277">Wie in `$_`.</span><span class="sxs-lookup"><span data-stu-id="48ae7-277">Same as `$_`.</span></span> <span data-ttu-id="48ae7-278">Enthält das aktuelle-Objekt im Pipeline Objekt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-278">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="48ae7-279">Sie können diese Variable in Befehlen verwenden, die eine Aktion für jedes Objekt oder für ausgewählte Objekte in einer Pipeline ausführen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-279">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="psscriptroot"></a><span data-ttu-id="48ae7-280">$PSScriptRoot</span><span class="sxs-lookup"><span data-stu-id="48ae7-280">$PSScriptRoot</span></span>

<span data-ttu-id="48ae7-281">Enthält das Verzeichnis, in dem ein Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-281">Contains the directory from which a script is being run.</span></span>

<span data-ttu-id="48ae7-282">In PowerShell 2,0 ist diese Variable nur in Skript Modulen () gültig `.psm1` .</span><span class="sxs-lookup"><span data-stu-id="48ae7-282">In PowerShell 2.0, this variable is valid only in script modules (`.psm1`).</span></span>
<span data-ttu-id="48ae7-283">Ab PowerShell 3,0 ist Sie in allen Skripts gültig.</span><span class="sxs-lookup"><span data-stu-id="48ae7-283">Beginning in PowerShell 3.0, it's valid in all scripts.</span></span>

### <a name="pssenderinfo"></a><span data-ttu-id="48ae7-284">$PSSenderInfo</span><span class="sxs-lookup"><span data-stu-id="48ae7-284">$PSSenderInfo</span></span>

<span data-ttu-id="48ae7-285">Enthält Informationen über den Benutzer, der die PSSession gestartet hat, einschließlich der Benutzeridentität und der Zeitzone des Ursprungs Computers.</span><span class="sxs-lookup"><span data-stu-id="48ae7-285">Contains information about the user who started the PSSession, including the user identity and the time zone of the originating computer.</span></span> <span data-ttu-id="48ae7-286">Diese Variable ist nur in pssessions verfügbar.</span><span class="sxs-lookup"><span data-stu-id="48ae7-286">This variable is available only in PSSessions.</span></span>

<span data-ttu-id="48ae7-287">Die `$PSSenderInfo` -Variable enthält eine vom benutzerkonfigurierbare Eigenschaft **applicationarguments**, die standardmäßig nur die `$PSVersionTable` aus der ursprünglichen Sitzung enthält.</span><span class="sxs-lookup"><span data-stu-id="48ae7-287">The `$PSSenderInfo` variable includes a user-configurable property, **ApplicationArguments**, that by default, contains only the `$PSVersionTable` from the originating session.</span></span> <span data-ttu-id="48ae7-288">Um der **applicationarguments** -Eigenschaft Daten hinzuzufügen, verwenden Sie den **applicationarguments** -Parameter des `New-PSSessionOption` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="48ae7-288">To add data to the **ApplicationArguments** property, use the **ApplicationArguments** parameter of the `New-PSSessionOption` cmdlet.</span></span>

### <a name="psuiculture"></a><span data-ttu-id="48ae7-289">$PSUICulture</span><span class="sxs-lookup"><span data-stu-id="48ae7-289">$PSUICulture</span></span>

<span data-ttu-id="48ae7-290">Enthält den Namen der Kultur der Benutzeroberfläche (UI), die derzeit im Betriebssystem verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-290">Contains the name of the user interface (UI) culture that's currently in use in the operating system.</span></span> <span data-ttu-id="48ae7-291">Die Benutzeroberflächenkultur bestimmt, welche Textzeichenfolgen für die Benutzeroberflächenelemente, z. B. Menüs und Meldungen, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-291">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span> <span data-ttu-id="48ae7-292">Dies ist der Wert der **System.Globalization.CultureInfo.CurrentUICulture.Name** -Eigenschaft des Systems.</span><span class="sxs-lookup"><span data-stu-id="48ae7-292">This is the value of the **System.Globalization.CultureInfo.CurrentUICulture.Name** property of the system.</span></span> <span data-ttu-id="48ae7-293">Verwenden Sie das-Cmdlet, um das **System. Globalization. CultureInfo** -Objekt für das System zu erhalten `Get-UICulture` .</span><span class="sxs-lookup"><span data-stu-id="48ae7-293">To get the **System.Globalization.CultureInfo** object for the system, use the `Get-UICulture` cmdlet.</span></span>

### <a name="psversiontable"></a><span data-ttu-id="48ae7-294">$PSVersionTable</span><span class="sxs-lookup"><span data-stu-id="48ae7-294">$PSVersionTable</span></span>

<span data-ttu-id="48ae7-295">Enthält eine schreibgeschützte Hash Tabelle, in der Details zur PowerShell-Version angezeigt werden, die in der aktuellen Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-295">Contains a read-only hash table that displays details about the version of PowerShell that is running in the current session.</span></span> <span data-ttu-id="48ae7-296">Die Tabelle enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="48ae7-296">The table includes the following items:</span></span>

| <span data-ttu-id="48ae7-297">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="48ae7-297">Property</span></span>                  | <span data-ttu-id="48ae7-298">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48ae7-298">Description</span></span>                                   |
| ------------------------- | --------------------------------------------- |
| <span data-ttu-id="48ae7-299">**BuildVersion**</span><span class="sxs-lookup"><span data-stu-id="48ae7-299">**BuildVersion**</span></span>          | <span data-ttu-id="48ae7-300">Die Buildnummer der aktuellen Version.</span><span class="sxs-lookup"><span data-stu-id="48ae7-300">The build number of the current version</span></span>       |
| <span data-ttu-id="48ae7-301">**CLRVersion**</span><span class="sxs-lookup"><span data-stu-id="48ae7-301">**CLRVersion**</span></span>            | <span data-ttu-id="48ae7-302">Die Version des Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="48ae7-302">The version of the common language runtime</span></span>    |
|                           | <span data-ttu-id="48ae7-303">CLR</span><span class="sxs-lookup"><span data-stu-id="48ae7-303">(CLR)</span></span>                                         |
| <span data-ttu-id="48ae7-304">**Pscompatibleversions**</span><span class="sxs-lookup"><span data-stu-id="48ae7-304">**PSCompatibleVersions**</span></span>  | <span data-ttu-id="48ae7-305">Versionen von PowerShell, die kompatibel sind</span><span class="sxs-lookup"><span data-stu-id="48ae7-305">Versions of PowerShell that are compatible</span></span>    |
|                           | <span data-ttu-id="48ae7-306">mit der aktuellen Version</span><span class="sxs-lookup"><span data-stu-id="48ae7-306">with the current version</span></span>                      |
| <span data-ttu-id="48ae7-307">**PSEdition**</span><span class="sxs-lookup"><span data-stu-id="48ae7-307">**PSEdition**</span></span>             | <span data-ttu-id="48ae7-308">Diese Eigenschaft hat den Wert "Desktop", für</span><span class="sxs-lookup"><span data-stu-id="48ae7-308">This property has the value of 'Desktop', for</span></span> |
|                           | <span data-ttu-id="48ae7-309">Windows Server-und Windows-Client Versionen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-309">Windows Server and Windows client versions.</span></span>   |
|                           | <span data-ttu-id="48ae7-310">Diese Eigenschaft hat den Wert "Core" für</span><span class="sxs-lookup"><span data-stu-id="48ae7-310">This property has the value of 'Core' for</span></span>     |
|                           | <span data-ttu-id="48ae7-311">PowerShell wird unter Nano Server oder</span><span class="sxs-lookup"><span data-stu-id="48ae7-311">PowerShell running under Nano Server or</span></span>       |
|                           | <span data-ttu-id="48ae7-312">Windows IOT.</span><span class="sxs-lookup"><span data-stu-id="48ae7-312">Windows IOT.</span></span>                                  |
| <span data-ttu-id="48ae7-313">**Psremotingprotocolversion**</span><span class="sxs-lookup"><span data-stu-id="48ae7-313">**PSRemotingProtocolVersion**</span></span> | <span data-ttu-id="48ae7-314">Die Version von PowerShell Remote</span><span class="sxs-lookup"><span data-stu-id="48ae7-314">The version of the PowerShell remote</span></span>      |
|                           | <span data-ttu-id="48ae7-315">Verwaltungs Protokoll.</span><span class="sxs-lookup"><span data-stu-id="48ae7-315">management protocol.</span></span>                          |
| <span data-ttu-id="48ae7-316">**PSVersion**</span><span class="sxs-lookup"><span data-stu-id="48ae7-316">**PSVersion**</span></span>             | <span data-ttu-id="48ae7-317">Die PowerShell-Versionsnummer</span><span class="sxs-lookup"><span data-stu-id="48ae7-317">The PowerShell version number</span></span>                 |
| <span data-ttu-id="48ae7-318">**SerializationVersion**</span><span class="sxs-lookup"><span data-stu-id="48ae7-318">**SerializationVersion**</span></span>  | <span data-ttu-id="48ae7-319">Die Version der Serialisierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="48ae7-319">The version of the serialization method</span></span>       |
| <span data-ttu-id="48ae7-320">**Wsmanstackversion**</span><span class="sxs-lookup"><span data-stu-id="48ae7-320">**WSManStackVersion**</span></span>     | <span data-ttu-id="48ae7-321">Die Versionsnummer des WS-Management Stapels</span><span class="sxs-lookup"><span data-stu-id="48ae7-321">The version number of the WS-Management stack</span></span> |

### <a name="pwd"></a><span data-ttu-id="48ae7-322">$PWD</span><span class="sxs-lookup"><span data-stu-id="48ae7-322">$PWD</span></span>

<span data-ttu-id="48ae7-323">Enthält ein Pfad Objekt, das den vollständigen Pfad des aktuellen Verzeichnis Speicher Orts für den aktuellen PowerShell-Runspace darstellt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-323">Contains a path object that represents the full path of the current directory location for the current PowerShell runspace.</span></span>

> [!NOTE]
> <span data-ttu-id="48ae7-324">PowerShell unterstützt mehrere Runspaces pro Prozess.</span><span class="sxs-lookup"><span data-stu-id="48ae7-324">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="48ae7-325">Jeder Runspace verfügt über ein eigenes _Aktuelles Verzeichnis_.</span><span class="sxs-lookup"><span data-stu-id="48ae7-325">Each runspace has its own _current directory_.</span></span> <span data-ttu-id="48ae7-326">Dies entspricht nicht dem aktuellen Verzeichnis des Prozesses: `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="48ae7-326">This is not the same as the current directory of the process: `[System.Environment]::CurrentDirectory`.</span></span>

### <a name="sender"></a><span data-ttu-id="48ae7-327">$Sender</span><span class="sxs-lookup"><span data-stu-id="48ae7-327">$Sender</span></span>

<span data-ttu-id="48ae7-328">Enthält das-Objekt, das dieses Ereignis generiert hat.</span><span class="sxs-lookup"><span data-stu-id="48ae7-328">Contains the object that generated this event.</span></span> <span data-ttu-id="48ae7-329">Diese Variable wird nur innerhalb des Aktions Blocks eines Ereignis Registrierungs Befehls aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-329">This variable is populated only within the Action block of an event registration command.</span></span> <span data-ttu-id="48ae7-330">Der Wert dieser Variablen befindet sich auch in der Absender-Eigenschaft des **psiebargs** -Objekts, das `Get-Event` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-330">The value of this variable can also be found in the Sender property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="shellid"></a><span data-ttu-id="48ae7-331">$ShellId</span><span class="sxs-lookup"><span data-stu-id="48ae7-331">$ShellId</span></span>

<span data-ttu-id="48ae7-332">Enthält den Bezeichner der aktuellen Shell.</span><span class="sxs-lookup"><span data-stu-id="48ae7-332">Contains the identifier of the current shell.</span></span>

### <a name="stacktrace"></a><span data-ttu-id="48ae7-333">$StackTrace</span><span class="sxs-lookup"><span data-stu-id="48ae7-333">$StackTrace</span></span>

<span data-ttu-id="48ae7-334">Enthält eine Stapel Überwachung für den letzten Fehler.</span><span class="sxs-lookup"><span data-stu-id="48ae7-334">Contains a stack trace for the most recent error.</span></span>

### <a name="switch"></a><span data-ttu-id="48ae7-335">$switch</span><span class="sxs-lookup"><span data-stu-id="48ae7-335">$switch</span></span>

<span data-ttu-id="48ae7-336">Enthält den Enumerator nicht die resultierenden Werte einer- `Switch` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="48ae7-336">Contains the enumerator not the resulting values of a `Switch` statement.</span></span> <span data-ttu-id="48ae7-337">Die `$switch` Variable ist nur vorhanden, während die `Switch` Anweisung ausgeführt wird. Sie wird gelöscht, wenn die `switch` Ausführung der Anweisung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="48ae7-337">The `$switch` variable exists only while the `Switch` statement is running; it's deleted when the `switch` statement completes execution.</span></span> <span data-ttu-id="48ae7-338">Weitere Informationen finden Sie unter [about_Switch](about_Switch.md).</span><span class="sxs-lookup"><span data-stu-id="48ae7-338">For more information, see [about_Switch](about_Switch.md).</span></span>

<span data-ttu-id="48ae7-339">Enumeratoren enthalten Eigenschaften und Methoden, mit denen Sie Schleifen Werte abrufen und die aktuelle Schleifen Iterationen ändern können.</span><span class="sxs-lookup"><span data-stu-id="48ae7-339">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="48ae7-340">Weitere Informationen finden Sie unter [Verwenden von Enumeratoren](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="48ae7-340">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="this"></a><span data-ttu-id="48ae7-341">$this</span><span class="sxs-lookup"><span data-stu-id="48ae7-341">$this</span></span>

<span data-ttu-id="48ae7-342">In einem Skriptblock, der eine Skript Eigenschaft oder Skript Methode definiert, `$this` verweist die Variable auf das Objekt, das erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-342">In a script block that defines a script property or script method, the `$this` variable refers to the object that is being extended.</span></span>

<span data-ttu-id="48ae7-343">In einer benutzerdefinierten Klasse `$this` verweist die Variable auf das Klassenobjekt, das den Zugriff auf die in der-Klasse definierten Eigenschaften und Methoden zulässt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-343">In a custom class, the `$this` variable refers to the class object itself allowing access to properties and methods defined in the class.</span></span>

### <a name="true"></a><span data-ttu-id="48ae7-344">$True</span><span class="sxs-lookup"><span data-stu-id="48ae7-344">$true</span></span>

<span data-ttu-id="48ae7-345">Enthält **true**.</span><span class="sxs-lookup"><span data-stu-id="48ae7-345">Contains **True**.</span></span> <span data-ttu-id="48ae7-346">Sie können diese Variable verwenden, um **true** in Befehlen und Skripts darzustellen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-346">You can use this variable to represent **True** in commands and scripts.</span></span>

## <a name="using-enumerators"></a><span data-ttu-id="48ae7-347">Verwenden von Enumeratoren</span><span class="sxs-lookup"><span data-stu-id="48ae7-347">Using Enumerators</span></span>

<span data-ttu-id="48ae7-348">Die `$input` `$foreach` Variablen, und `$switch` sind alle Enumeratoren, die zum Durchlaufen der Werte verwendet werden, die durch ihren enthaltenden Codeblock verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-348">The `$input`, `$foreach`, and `$switch` variables are all enumerators used to iterate through the values processed by their containing code block.</span></span>

<span data-ttu-id="48ae7-349">Ein Enumerator enthält Eigenschaften und Methoden, die Sie zum fortsetzen oder Zurücksetzen der Iterationen oder zum Abrufen von Iterations Werten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="48ae7-349">An enumerator contains properties and methods you can use to advance or reset iteration, or retrieve iteration values.</span></span> <span data-ttu-id="48ae7-350">Die direkte Bearbeitung von Enumeratoren gilt nicht als bewährte Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="48ae7-350">Directly manipulating enumerators isn't considered best practice.</span></span>

- <span data-ttu-id="48ae7-351">In Schleifen sollten die Fluss Steuerungs Schlüsselwörter unter [brechen](about_Break.md) und [fortfahren](about_Continue.md) bevorzugt werden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-351">Within loops, flow control keywords [break](about_Break.md) and [continue](about_Continue.md) should be preferred.</span></span>
- <span data-ttu-id="48ae7-352">In Funktionen, die Pipeline Eingaben akzeptieren, empfiehlt es sich, Parameter mit den Attributen **valuefrompipeline** oder **valuefrompipelinebypropertyname** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-352">Within functions that accept pipeline input, it's best practice to use Parameters with the **ValueFromPipeline** or **ValueFromPipelineByPropertyName** attributes.</span></span>

  <span data-ttu-id="48ae7-353">Weitere Informationen finden Sie unter [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="48ae7-353">For more information, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="movenext"></a><span data-ttu-id="48ae7-354">MoveNext</span><span class="sxs-lookup"><span data-stu-id="48ae7-354">MoveNext</span></span>

<span data-ttu-id="48ae7-355">Die [Methode "](/dotnet/api/system.collections.ienumerator.movenext) -Methode" verschiebt den Enumerator auf das nächste Element der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="48ae7-355">The [MoveNext](/dotnet/api/system.collections.ienumerator.movenext) method advances the enumerator to the next element of the collection.</span></span> <span data-ttu-id="48ae7-356">" **Muvenext** " gibt " **true** " zurück, wenn der Enumerator erfolgreich erweitert wurde, " **false** ", wenn der Enumerator das Ende der Auflistung überschritten hat.</span><span class="sxs-lookup"><span data-stu-id="48ae7-356">**MoveNext** returns **True** if the enumerator was successfully advanced, **False** if the enumerator has passed the end of the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="48ae7-357">Der **boolesche** Wert, der My **MoveNext** zurückgibt, wird an den Ausgabestream gesendet.</span><span class="sxs-lookup"><span data-stu-id="48ae7-357">The **Boolean** value returned my **MoveNext** is sent to the output stream.</span></span>
> <span data-ttu-id="48ae7-358">Sie können die Ausgabe unterdrücken, indem Sie Sie in Typecasting umwandeln `[void]` oder an [out-null](xref:Microsoft.PowerShell.Core.Out-Null)weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="48ae7-358">You can suppress the output by typecasting it to `[void]` or piping it to [Out-Null](xref:Microsoft.PowerShell.Core.Out-Null).</span></span>
>
> ```powershell
> $input.MoveNext() | Out-Null
> ```
>
> ```powershell
> [void]$input.MoveNext()
> ```

### <a name="reset"></a><span data-ttu-id="48ae7-359">Reset</span><span class="sxs-lookup"><span data-stu-id="48ae7-359">Reset</span></span>

<span data-ttu-id="48ae7-360">Die [Reset](/dotnet/api/system.collections.ienumerator.reset) -Methode legt den Enumerator auf seine anfängliche Position **vor** dem ersten Element in der Auflistung fest.</span><span class="sxs-lookup"><span data-stu-id="48ae7-360">The [Reset](/dotnet/api/system.collections.ienumerator.reset) method sets the enumerator to its initial position, which is **before** the first element in the collection.</span></span>

### <a name="current"></a><span data-ttu-id="48ae7-361">Aktuell</span><span class="sxs-lookup"><span data-stu-id="48ae7-361">Current</span></span>

<span data-ttu-id="48ae7-362">Die [Current](/dotnet/api/system.collections.ienumerator.current) -Eigenschaft ruft das-Element in der-Auflistung oder-Pipeline an der aktuellen Position des Enumerators ab.</span><span class="sxs-lookup"><span data-stu-id="48ae7-362">The [Current](/dotnet/api/system.collections.ienumerator.current) property gets the element in the collection, or pipeline, at the current position of the enumerator.</span></span>

<span data-ttu-id="48ae7-363">Die **aktuelle** -Eigenschaft gibt weiterhin dieselbe Eigenschaft zurück, **bis "** " "" ".</span><span class="sxs-lookup"><span data-stu-id="48ae7-363">The **Current** property continues to return the same property until **MoveNext** is called.</span></span>

## <a name="examples"></a><span data-ttu-id="48ae7-364">Beispiele</span><span class="sxs-lookup"><span data-stu-id="48ae7-364">Examples</span></span>

### <a name="example-1-using-the-input-variable"></a><span data-ttu-id="48ae7-365">Beispiel 1: Verwenden der $Input Variable</span><span class="sxs-lookup"><span data-stu-id="48ae7-365">Example 1: Using the $input variable</span></span>

<span data-ttu-id="48ae7-366">Im folgenden Beispiel löscht der Zugriff auf die- `$input` Variable die-Variable, bis der Prozess Block das nächste Mal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-366">In the following example, accessing the `$input` variable clears the variable until the next time the process block executes.</span></span> <span data-ttu-id="48ae7-367">Bei Verwendung der **Reset** -Methode wird die `$input` Variable auf den aktuellen Pipeline Wert zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-367">Using the **Reset** method resets the `$input` variable to the current pipeline value.</span></span>

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

<span data-ttu-id="48ae7-368">Der Prozess Block setzt die Variable automatisch fort, `$input` auch wenn Sie nicht darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-368">The process block automatically advances the `$input` variable even if you don't access it.</span></span>

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

### <a name="example-2-using-input-outside-the-process-block"></a><span data-ttu-id="48ae7-369">Beispiel 2: Verwenden von $Input außerhalb des Prozess Blocks</span><span class="sxs-lookup"><span data-stu-id="48ae7-369">Example 2: Using $input outside the process block</span></span>

<span data-ttu-id="48ae7-370">Außerhalb des Prozess Blocks stellt die `$input` Variable alle Werte dar, die an die Funktion weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="48ae7-370">Outside of the process block the `$input` variable represents all the values piped into the function.</span></span>

- <span data-ttu-id="48ae7-371">Durch den Zugriff auf die `$input` Variable werden alle Werte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="48ae7-371">Accessing the `$input` variable clears all values.</span></span>
- <span data-ttu-id="48ae7-372">Die **Reset** -Methode setzt die gesamte Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="48ae7-372">The **Reset** method resets the entire collection.</span></span>
- <span data-ttu-id="48ae7-373">Die **aktuelle** Eigenschaft wird nie aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-373">The **Current** property is never populated.</span></span>
- <span data-ttu-id="48ae7-374">Die Methode " **ivenext** " gibt false zurück, da die Auflistung nicht erweitert werden kann.</span><span class="sxs-lookup"><span data-stu-id="48ae7-374">The **MoveNext** method returns false because the collection can't be advanced.</span></span>
  - <span data-ttu-id="48ae7-375">Durch **Aufrufen von** "" wird die `$input` Variable gelöscht.</span><span class="sxs-lookup"><span data-stu-id="48ae7-375">Calling **MoveNext** clears out the `$input` variable.</span></span>

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

### <a name="example-3-using-the-inputcurrent-property"></a><span data-ttu-id="48ae7-376">Beispiel 3: Verwenden der $Input. Current-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="48ae7-376">Example 3: Using the $input.Current property</span></span>

<span data-ttu-id="48ae7-377">Mithilfe der **aktuellen** Eigenschaft kann auf den aktuellen Pipeline Wert mehrmals zugegriffen werden, ohne dass die **Reset** -Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-377">By using the **Current** property, the current pipeline value can be accessed multiple times without using the **Reset** method.</span></span> <span data-ttu-id="48ae7-378">Der Prozess Block ruft nicht automatisch die **Methode "** Methode" auf.</span><span class="sxs-lookup"><span data-stu-id="48ae7-378">The process block doesn't automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="48ae7-379">Die **aktuelle** Eigenschaft wird nie aufgefüllt, es sei denn, **Sie nennen nicht** explizit "".</span><span class="sxs-lookup"><span data-stu-id="48ae7-379">The **Current** property will never be populated unless you explicitly call **MoveNext**.</span></span> <span data-ttu-id="48ae7-380">Der Zugriff auf die **aktuelle** Eigenschaft kann mehrmals innerhalb des Prozess Blocks erfolgen, ohne den Wert zu löschen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-380">The **Current** property can be accessed multiple times inside the process block without clearing its value.</span></span>

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

### <a name="example-4-using-the-foreach-variable"></a><span data-ttu-id="48ae7-381">Beispiel 4: Verwenden der $foreach Variable</span><span class="sxs-lookup"><span data-stu-id="48ae7-381">Example 4: Using the $foreach variable</span></span>

<span data-ttu-id="48ae7-382">Anders als die- `$input` Variable `$foreach` stellt die-Variable immer alle Elemente in der Auflistung dar, wenn direkt darauf zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-382">Unlike the `$input` variable, the `$foreach` variable always represents all items in the collection when accessed directly.</span></span> <span data-ttu-id="48ae7-383">Verwenden Sie die **aktuelle** -Eigenschaft, um auf das aktuelle Auflistungs Element zuzugreifen **, und die** **Reset** -Methode und die-Methode, um den Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="48ae7-383">Use the **Current** property to access the current collection element, and the **Reset** and **MoveNext** methods to change its value.</span></span>

> [!NOTE]
> <span data-ttu-id="48ae7-384">Jede Iterations `foreach` Schleife ruft automatisch die Methode " **ivenext** " auf.</span><span class="sxs-lookup"><span data-stu-id="48ae7-384">Each iteration of the `foreach` loop will automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="48ae7-385">Die folgende-Schleife wird nur zweimal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-385">The following loop only executes twice.</span></span> <span data-ttu-id="48ae7-386">In der zweiten Iterationen wird die Auflistung vor Abschluss der Iterationen auf das dritte Element verschoben.</span><span class="sxs-lookup"><span data-stu-id="48ae7-386">In the second iteration, the collection is moved to the third element before the iteration is complete.</span></span> <span data-ttu-id="48ae7-387">Nach der zweiten Iterations Zeit sind nun keine weiteren Werte zum Durchlaufen vorhanden, und die Schleife wird beendet.</span><span class="sxs-lookup"><span data-stu-id="48ae7-387">After the second iteration, there are now no more values to iterate, and the loop terminates.</span></span>

<span data-ttu-id="48ae7-388">Die Eigenschaft " **ivenext** " wirkt sich nicht auf die Variable aus, die zum Durchlaufen der Auflistung ausgewählt wurde ( `$Num` ).</span><span class="sxs-lookup"><span data-stu-id="48ae7-388">The **MoveNext** property doesn't affect the variable chosen to iterate through the collection (`$Num`).</span></span>

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

<span data-ttu-id="48ae7-389">Bei Verwendung der Reset-Methode wird das aktuelle Element in der Auflistung zurück **gesetzt** .</span><span class="sxs-lookup"><span data-stu-id="48ae7-389">Using the **Reset** method resets the current element in the collection.</span></span> <span data-ttu-id="48ae7-390">Im folgenden Beispiel werden die ersten beiden Elemente **zweimal** durchlaufen, da die **Reset** -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="48ae7-390">The following example loops through the first two elements **twice** because the **Reset** method is called.</span></span> <span data-ttu-id="48ae7-391">Nach den ersten beiden Schleifen schlägt die `if` Anweisung fehl, und die Schleife durchläuft alle drei Elemente in der Regel.</span><span class="sxs-lookup"><span data-stu-id="48ae7-391">After the first two loops, the `if` statement fails and the loop iterates through all three elements normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48ae7-392">Dies kann zu einer Endlosschleife führen.</span><span class="sxs-lookup"><span data-stu-id="48ae7-392">This could result in an infinite loop.</span></span>

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

### <a name="example-5-using-the-switch-variable"></a><span data-ttu-id="48ae7-393">Beispiel 5: Verwenden der $Switch Variable</span><span class="sxs-lookup"><span data-stu-id="48ae7-393">Example 5: Using the $switch variable</span></span>

<span data-ttu-id="48ae7-394">Die `$switch` Variable verfügt über die exakt gleichen Regeln wie die `$foreach` Variable.</span><span class="sxs-lookup"><span data-stu-id="48ae7-394">The `$switch` variable has the exact same rules as the `$foreach` variable.</span></span>
<span data-ttu-id="48ae7-395">Im folgenden Beispiel werden alle enumeratorkonzepte veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="48ae7-395">The following example demonstrates all the enumerator concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="48ae7-396">Beachten Sie, dass der **notevaluated** -Fall nie ausgeführt wird, auch wenn es keine- `break`  Anweisung nach der-Methode von "-Methode" gibt.</span><span class="sxs-lookup"><span data-stu-id="48ae7-396">Note how the **NotEvaluated** case is never executed, even though there's no `break` statement after the **MoveNext** method.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="48ae7-397">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="48ae7-397">See also</span></span>

[<span data-ttu-id="48ae7-398">about_Functions</span><span class="sxs-lookup"><span data-stu-id="48ae7-398">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="48ae7-399">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="48ae7-399">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="48ae7-400">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="48ae7-400">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="48ae7-401">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="48ae7-401">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="48ae7-402">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="48ae7-402">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="48ae7-403">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="48ae7-403">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="48ae7-404">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="48ae7-404">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="48ae7-405">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="48ae7-405">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="48ae7-406">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="48ae7-406">about_Splatting</span></span>](about_Splatting.md)

[<span data-ttu-id="48ae7-407">about_Variables</span><span class="sxs-lookup"><span data-stu-id="48ae7-407">about_Variables</span></span>](about_Variables.md)
