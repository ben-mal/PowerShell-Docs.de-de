---
description: Beschreibt Variablen, die Zustandsinformationen für PowerShell speichern. Diese Variablen werden von PowerShell erstellt und verwaltet.
Locale: en-US
ms.date: 03/29/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_automatic_variables?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Automatic_Variables
ms.openlocfilehash: 49c1a311c13078b4e625fbcb450817f1d5039e0d
ms.sourcegitcommit: bdd0fedaf9ba534645b2f7eb1fe1241481f58715
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "105936651"
---
# <a name="about-automatic-variables"></a><span data-ttu-id="910ad-104">Informationen zu automatischen Variablen</span><span class="sxs-lookup"><span data-stu-id="910ad-104">About Automatic Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="910ad-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="910ad-105">Short description</span></span>

<span data-ttu-id="910ad-106">Beschreibt Variablen, die Zustandsinformationen für PowerShell speichern.</span><span class="sxs-lookup"><span data-stu-id="910ad-106">Describes variables that store state information for PowerShell.</span></span> <span data-ttu-id="910ad-107">Diese Variablen werden von PowerShell erstellt und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="910ad-107">These variables are created and maintained by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="910ad-108">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="910ad-108">Long description</span></span>

<span data-ttu-id="910ad-109">Konzeptionell werden diese Variablen als schreibgeschützt betrachtet.</span><span class="sxs-lookup"><span data-stu-id="910ad-109">Conceptually, these variables are considered to be read-only.</span></span> <span data-ttu-id="910ad-110">Obwohl Sie in geschrieben werden **können** , sollten Sie aus Gründen der Abwärtskompatibilität **nicht** in schreiben.</span><span class="sxs-lookup"><span data-stu-id="910ad-110">Even though they **can** be written to, for backward compatibility they **should not** be written to.</span></span>

<span data-ttu-id="910ad-111">Im folgenden finden Sie eine Liste der automatischen Variablen in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="910ad-111">Here is a list of the automatic variables in PowerShell:</span></span>

### <a name=""></a>$$

<span data-ttu-id="910ad-112">Enthält das letzte Token in der letzten Zeile, die von der Sitzung empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="910ad-112">Contains the last token in the last line received by the session.</span></span>

### <a name=""></a><span data-ttu-id="910ad-113">$?</span><span class="sxs-lookup"><span data-stu-id="910ad-113">$?</span></span>

<span data-ttu-id="910ad-114">Enthält den Ausführungs Status des letzten Befehls.</span><span class="sxs-lookup"><span data-stu-id="910ad-114">Contains the execution status of the last command.</span></span> <span data-ttu-id="910ad-115">Sie enthält **true** , wenn der letzte Befehl erfolgreich war, und **false** , wenn Sie fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="910ad-115">It contains **True** if the last command succeeded and **False** if it failed.</span></span>

<span data-ttu-id="910ad-116">Für Cmdlets und erweiterte Funktionen, die auf mehreren Stufen in einer Pipeline ausgeführt werden (z. b. sowohl in `process` -als auch in- `end` Blöcken), wird der Aufruf `this.WriteError()` von bzw `$PSCmdlet.WriteError()` . an einem beliebigen Punkt `$?` auf **false** festgelegt, wie `this.ThrowTerminatingError()` und `$PSCmdlet.ThrowTerminatingError()` .</span><span class="sxs-lookup"><span data-stu-id="910ad-116">For cmdlets and advanced functions that are run at multiple stages in a pipeline, for example in both `process` and `end` blocks, calling `this.WriteError()` or `$PSCmdlet.WriteError()` respectively at any point will set `$?` to **False**, as will `this.ThrowTerminatingError()` and `$PSCmdlet.ThrowTerminatingError()`.</span></span>

<span data-ttu-id="910ad-117">Das `Write-Error` Cmdlet legt `$?` nach der Ausführung immer **false** fest, wird jedoch nicht auf false festgelegt, `$?` Wenn eine Funktion aufgerufen wird: </span><span class="sxs-lookup"><span data-stu-id="910ad-117">The `Write-Error` cmdlet always sets `$?` to **False** immediately after it is executed, but will not set `$?` to **False** for a function calling it:</span></span>

```powershell
function Test-WriteError
{
    Write-Error "Bad"
    $? # $false
}

Test-WriteError
$? # $true
```

<span data-ttu-id="910ad-118">Zum letzteren Zweck `$PSCmdlet.WriteError()` sollte stattdessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="910ad-118">For the latter purpose, `$PSCmdlet.WriteError()` should be used instead.</span></span>

<span data-ttu-id="910ad-119">Bei nativen Befehlen (ausführbare Dateien) `$?` wird auf **true** festgelegt, wenn den `$LASTEXITCODE` Wert 0 hat, und auf **false** festgelegt, wenn `$LASTEXITCODE` ein beliebiger anderer Wert ist.</span><span class="sxs-lookup"><span data-stu-id="910ad-119">For native commands (executables), `$?` is set to **True** when `$LASTEXITCODE` is 0, and set to **False** when `$LASTEXITCODE` is any other value.</span></span>

> [!NOTE]
> <span data-ttu-id="910ad-120">Bis PowerShell 7, das eine-Anweisung in Klammern enthält `(...)` , wird die Teil Ausdruck-Syntax `$(...)` oder der Array Ausdruck `@(...)` immer `$?` auf **true** zurückgesetzt, sodass `(Write-Error)` `$?` als **true** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-120">Until PowerShell 7, containing a statement within parentheses `(...)`, subexpression syntax `$(...)` or array expression `@(...)` always reset `$?` to **True**, so that `(Write-Error)` shows `$?` as **True**.</span></span>
> <span data-ttu-id="910ad-121">Dies wurde in PowerShell 7 geändert, sodass `$?` immer den tatsächlichen Erfolg der letzten Befehlsausführung in diesen Ausdrücken widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="910ad-121">This has been changed in PowerShell 7, so that `$?` will always reflect the actual success of the last command run in these expressions.</span></span>

### <a name=""></a>$^

<span data-ttu-id="910ad-122">Enthält das erste Token in der letzten Zeile, die von der Sitzung empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="910ad-122">Contains the first token in the last line received by the session.</span></span>

### <a name="_"></a><span data-ttu-id="910ad-123">$_</span><span class="sxs-lookup"><span data-stu-id="910ad-123">$_</span></span>

<span data-ttu-id="910ad-124">Wie in `$PSItem`.</span><span class="sxs-lookup"><span data-stu-id="910ad-124">Same as `$PSItem`.</span></span> <span data-ttu-id="910ad-125">Enthält das aktuelle-Objekt im Pipeline Objekt.</span><span class="sxs-lookup"><span data-stu-id="910ad-125">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="910ad-126">Sie können diese Variable in Befehlen verwenden, die eine Aktion für jedes Objekt oder für ausgewählte Objekte in einer Pipeline ausführen.</span><span class="sxs-lookup"><span data-stu-id="910ad-126">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="args"></a><span data-ttu-id="910ad-127">$args</span><span class="sxs-lookup"><span data-stu-id="910ad-127">$args</span></span>

<span data-ttu-id="910ad-128">Enthält ein Array von Werten für nicht deklarierte Parameter, die an eine Funktion, ein Skript oder einen Skriptblock übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="910ad-128">Contains an array of values for undeclared parameters that are passed to a function, script, or script block.</span></span> <span data-ttu-id="910ad-129">Wenn Sie eine Funktion erstellen, können Sie die Parameter mit dem- `param` Schlüsselwort deklarieren oder indem Sie eine durch Trennzeichen getrennte Liste von Parametern nach dem Funktionsnamen in Klammern einfügen.</span><span class="sxs-lookup"><span data-stu-id="910ad-129">When you create a function, you can declare the parameters by using the `param` keyword or by adding a comma-separated list of parameters in parentheses after the function name.</span></span>

<span data-ttu-id="910ad-130">In einer Ereignis Aktion enthält die- `$Args` Variable-Objekte, die die Ereignis Argumente des zu verarbeitenden Ereignisses darstellen.</span><span class="sxs-lookup"><span data-stu-id="910ad-130">In an event action, the `$Args` variable contains objects that represent the event arguments of the event that is being processed.</span></span> <span data-ttu-id="910ad-131">Diese Variable wird nur innerhalb des `Action` Blocks eines Ereignis Registrierungs Befehls aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="910ad-131">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="910ad-132">Der Wert dieser Variablen befindet sich auch in der **sourceargs** -Eigenschaft des **psiebargs** -Objekts, das `Get-Event` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="910ad-132">The value of this variable can also be found in the **SourceArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="consolefilename"></a><span data-ttu-id="910ad-133">$ConsoleFileName</span><span class="sxs-lookup"><span data-stu-id="910ad-133">$ConsoleFileName</span></span>

<span data-ttu-id="910ad-134">Enthält den Pfad der Konsolen Datei ( `.psc1` ), die zuletzt in der Sitzung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="910ad-134">Contains the path of the console file (`.psc1`) that was most recently used in the session.</span></span> <span data-ttu-id="910ad-135">Diese Variable wird aufgefüllt, wenn Sie PowerShell mit dem **PsConsoleFile** -Parameter starten oder wenn Sie das `Export-Console` Cmdlet verwenden, um Snap-in-Namen in eine Konsolen Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="910ad-135">This variable is populated when you start PowerShell with the **PSConsoleFile** parameter or when you use the `Export-Console` cmdlet to export snap-in names to a console file.</span></span>

<span data-ttu-id="910ad-136">Wenn Sie das `Export-Console` Cmdlet ohne Parameter verwenden, wird automatisch die Konsolen Datei aktualisiert, die zuletzt in der Sitzung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="910ad-136">When you use the `Export-Console` cmdlet without parameters, it automatically updates the console file that was most recently used in the session.</span></span> <span data-ttu-id="910ad-137">Sie können diese automatische Variable verwenden, um zu bestimmen, welche Datei aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-137">You can use this automatic variable to determine which file will be updated.</span></span>

### <a name="error"></a><span data-ttu-id="910ad-138">$Error</span><span class="sxs-lookup"><span data-stu-id="910ad-138">$Error</span></span>

<span data-ttu-id="910ad-139">Enthält ein Array von Fehler Objekten, die die letzten Fehler darstellen.</span><span class="sxs-lookup"><span data-stu-id="910ad-139">Contains an array of error objects that represent the most recent errors.</span></span>
<span data-ttu-id="910ad-140">Der letzte Fehler ist das erste Fehler Objekt im Array `$Error[0]` .</span><span class="sxs-lookup"><span data-stu-id="910ad-140">The most recent error is the first error object in the array `$Error[0]`.</span></span>

<span data-ttu-id="910ad-141">Um zu verhindern, dass dem Array ein Fehler hinzugefügt wird `$Error` , verwenden Sie den allgemeinen **ErrorAction** -Parameter mit dem Wert **Ignore**.</span><span class="sxs-lookup"><span data-stu-id="910ad-141">To prevent an error from being added to the `$Error` array, use the **ErrorAction** common parameter with a value of **Ignore**.</span></span> <span data-ttu-id="910ad-142">Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="910ad-142">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

### <a name="event"></a><span data-ttu-id="910ad-143">$Event</span><span class="sxs-lookup"><span data-stu-id="910ad-143">$Event</span></span>

<span data-ttu-id="910ad-144">Enthält ein **peventargs** -Objekt, das das Ereignis darstellt, das gerade verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-144">Contains a **PSEventArgs** object that represents the event that is being processed.</span></span> <span data-ttu-id="910ad-145">Diese Variable wird nur innerhalb des `Action` Blocks eines Ereignis Registrierungs Befehls (z. b.) aufgefüllt `Register-ObjectEvent` .</span><span class="sxs-lookup"><span data-stu-id="910ad-145">This variable is populated only within the `Action` block of an event registration command, such as `Register-ObjectEvent`.</span></span> <span data-ttu-id="910ad-146">Der Wert dieser Variablen ist das gleiche Objekt, das vom `Get-Event` Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-146">The value of this variable is the same object that the `Get-Event` cmdlet returns.</span></span> <span data-ttu-id="910ad-147">Daher können Sie die Eigenschaften der `Event` Variablen (z. b.) `$Event.TimeGenerated` in einem `Action` Skriptblock verwenden.</span><span class="sxs-lookup"><span data-stu-id="910ad-147">Therefore, you can use the properties of the `Event` variable, such as `$Event.TimeGenerated`, in an `Action` script block.</span></span>

### <a name="eventargs"></a><span data-ttu-id="910ad-148">$EventArgs</span><span class="sxs-lookup"><span data-stu-id="910ad-148">$EventArgs</span></span>

<span data-ttu-id="910ad-149">Enthält ein-Objekt, das das erste Ereignis Argument darstellt, das von **EventArgs** des-Ereignisses abgeleitet wird, das gerade verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-149">Contains an object that represents the first event argument that derives from **EventArgs** of the event that is being processed.</span></span> <span data-ttu-id="910ad-150">Diese Variable wird nur innerhalb des `Action` Blocks eines Ereignis Registrierungs Befehls aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="910ad-150">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="910ad-151">Der Wert dieser Variablen befindet sich auch in der **sourceeventargs** -Eigenschaft des **peventargs** -Objekts, das `Get-Event` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="910ad-151">The value of this variable can also be found in the **SourceEventArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="eventsubscriber"></a><span data-ttu-id="910ad-152">$EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="910ad-152">$EventSubscriber</span></span>

<span data-ttu-id="910ad-153">Enthält ein **peventsubscriber** -Objekt, das den Ereignis Abonnenten des-Ereignisses darstellt, das gerade verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-153">Contains a **PSEventSubscriber** object that represents the event subscriber of the event that is being processed.</span></span> <span data-ttu-id="910ad-154">Diese Variable wird nur innerhalb des `Action` Blocks eines Ereignis Registrierungs Befehls aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="910ad-154">This variable is populated only within the `Action` block of an event registration command.</span></span> <span data-ttu-id="910ad-155">Der Wert dieser Variablen ist das gleiche Objekt, das vom `Get-EventSubscriber` Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-155">The value of this variable is the same object that the `Get-EventSubscriber` cmdlet returns.</span></span>

### <a name="executioncontext"></a><span data-ttu-id="910ad-156">$ExecutionContext</span><span class="sxs-lookup"><span data-stu-id="910ad-156">$ExecutionContext</span></span>

<span data-ttu-id="910ad-157">Enthält ein **engineintrinsics** -Objekt, das den Ausführungs Kontext des PowerShell-Hosts darstellt.</span><span class="sxs-lookup"><span data-stu-id="910ad-157">Contains an **EngineIntrinsics** object that represents the execution context of the PowerShell host.</span></span> <span data-ttu-id="910ad-158">Sie können diese Variable verwenden, um die für Cmdlets verfügbaren Ausführungs Objekte zu finden.</span><span class="sxs-lookup"><span data-stu-id="910ad-158">You can use this variable to find the execution objects that are available to cmdlets.</span></span>

### <a name="false"></a><span data-ttu-id="910ad-159">$false</span><span class="sxs-lookup"><span data-stu-id="910ad-159">$false</span></span>

<span data-ttu-id="910ad-160">Enthält **false**.</span><span class="sxs-lookup"><span data-stu-id="910ad-160">Contains **False**.</span></span> <span data-ttu-id="910ad-161">Sie können diese Variable verwenden, um **false** in Befehlen und Skripts darzustellen, anstatt die Zeichenfolge "false" zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="910ad-161">You can use this variable to represent **False** in commands and scripts instead of using the string "false".</span></span> <span data-ttu-id="910ad-162">Die Zeichenfolge kann als **true** interpretiert werden, wenn Sie in eine nicht leere Zeichenfolge oder in eine ganze Zahl ungleich 0 (null) konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-162">The string can be interpreted as **True** if it's converted to a non-empty string or to a non-zero integer.</span></span>

### <a name="foreach"></a><span data-ttu-id="910ad-163">$foreach</span><span class="sxs-lookup"><span data-stu-id="910ad-163">$foreach</span></span>

<span data-ttu-id="910ad-164">Enthält den Enumerator (nicht die resultierenden Werte) einer [foreach](about_ForEach.md) -Schleife.</span><span class="sxs-lookup"><span data-stu-id="910ad-164">Contains the enumerator (not the resulting values) of a [ForEach](about_ForEach.md) loop.</span></span> <span data-ttu-id="910ad-165">Die `$ForEach` Variable ist nur vorhanden, während die `ForEach` Schleife ausgeführt wird. Sie wird gelöscht, nachdem die Schleife abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="910ad-165">The `$ForEach` variable exists only while the `ForEach` loop is running; it's deleted after the loop is completed.</span></span>

<span data-ttu-id="910ad-166">Enumeratoren enthalten Eigenschaften und Methoden, mit denen Sie Schleifen Werte abrufen und die aktuelle Schleifen Iterationen ändern können.</span><span class="sxs-lookup"><span data-stu-id="910ad-166">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="910ad-167">Weitere Informationen finden Sie unter [Verwenden von Enumeratoren](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="910ad-167">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="home"></a><span data-ttu-id="910ad-168">$HOME</span><span class="sxs-lookup"><span data-stu-id="910ad-168">$HOME</span></span>

<span data-ttu-id="910ad-169">Enthält den vollständigen Pfad des Basisverzeichnisses des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="910ad-169">Contains the full path of the user's home directory.</span></span> <span data-ttu-id="910ad-170">Diese Variable entspricht in der Regel den `"$env:homedrive$env:homepath"` Windows-Umgebungsvariablen `C:\Users\<UserName>` .</span><span class="sxs-lookup"><span data-stu-id="910ad-170">This variable is the equivalent of the `"$env:homedrive$env:homepath"` Windows environment variables, typically `C:\Users\<UserName>`.</span></span>

### <a name="host"></a><span data-ttu-id="910ad-171">$Host</span><span class="sxs-lookup"><span data-stu-id="910ad-171">$Host</span></span>

<span data-ttu-id="910ad-172">Enthält ein-Objekt, das die aktuelle Host Anwendung für PowerShell darstellt.</span><span class="sxs-lookup"><span data-stu-id="910ad-172">Contains an object that represents the current host application for PowerShell.</span></span> <span data-ttu-id="910ad-173">Sie können diese Variable verwenden, um den aktuellen Host in Befehlen darzustellen oder um die Eigenschaften des Hosts (z. b. oder) anzuzeigen oder zu ändern `$Host.version` `$Host.CurrentCulture` `$host.ui.rawui.setbackgroundcolor("Red")` .</span><span class="sxs-lookup"><span data-stu-id="910ad-173">You can use this variable to represent the current host in commands or to display or change the properties of the host, such as `$Host.version` or `$Host.CurrentCulture`, or `$host.ui.rawui.setbackgroundcolor("Red")`.</span></span>

### <a name="input"></a><span data-ttu-id="910ad-174">$input</span><span class="sxs-lookup"><span data-stu-id="910ad-174">$input</span></span>

<span data-ttu-id="910ad-175">Enthält einen Enumerator, der alle Eingaben auflistet, die an eine Funktion weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="910ad-175">Contains an enumerator that enumerates all input that is passed to a function.</span></span> <span data-ttu-id="910ad-176">Die `$input` -Variable ist nur für Funktionen und Skriptblöcke verfügbar (bei denen es sich um unbenannte Funktionen handelt).</span><span class="sxs-lookup"><span data-stu-id="910ad-176">The `$input` variable is available only to functions and script blocks (which are unnamed functions).</span></span>

- <span data-ttu-id="910ad-177">In einer Funktion ohne einen- `Begin` ,- `Process` oder- `End` Block `$input` Listet die-Variable die Auflistung aller Eingaben für die Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="910ad-177">In a function without a `Begin`, `Process`, or `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

- <span data-ttu-id="910ad-178">Im- `Begin` Block enthält die- `$input` Variable keine Daten.</span><span class="sxs-lookup"><span data-stu-id="910ad-178">In the `Begin` block, the `$input` variable contains no data.</span></span>

- <span data-ttu-id="910ad-179">Im- `Process` Block enthält die- `$input` Variable das-Objekt, das sich zurzeit in der Pipeline befindet.</span><span class="sxs-lookup"><span data-stu-id="910ad-179">In the `Process` block, the `$input` variable contains the object that is currently in the pipeline.</span></span>

- <span data-ttu-id="910ad-180">Im- `End` Block listet die- `$input` Variable die Auflistung aller Eingaben für die-Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="910ad-180">In the `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

  > [!NOTE]
  > <span data-ttu-id="910ad-181">Sie können die `$input` Variable nicht innerhalb des Prozess Blocks und des endblocks in derselben Funktion oder in demselben Skriptblock verwenden.</span><span class="sxs-lookup"><span data-stu-id="910ad-181">You cannot use the `$input` variable inside both the Process block and the End block in the same function or script block.</span></span>

<span data-ttu-id="910ad-182">Da `$input` ein Enumerator ist, bewirkt der Zugriff auf eine der Eigenschaften, dass `$input` nicht mehr verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="910ad-182">Since `$input` is an enumerator, accessing any of it's properties causes `$input` to no longer be available.</span></span> <span data-ttu-id="910ad-183">Sie können `$input` in einer anderen Variablen speichern, um die Eigenschaften wiederzuverwenden `$input` .</span><span class="sxs-lookup"><span data-stu-id="910ad-183">You can store `$input` in another variable to reuse the `$input` properties.</span></span>

<span data-ttu-id="910ad-184">Enumeratoren enthalten Eigenschaften und Methoden, mit denen Sie Schleifen Werte abrufen und die aktuelle Schleifen Iterationen ändern können.</span><span class="sxs-lookup"><span data-stu-id="910ad-184">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="910ad-185">Weitere Informationen finden Sie unter [Verwenden von Enumeratoren](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="910ad-185">For more information, see [Using Enumerators](#using-enumerators).</span></span>

<span data-ttu-id="910ad-186">Die- `$input` Variable ist auch für den Befehl verfügbar, der durch den-Parameter von angegeben wird, `-Command` Wenn Sie `pwsh` von der Befehlszeile aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-186">The `$input` variable is also available to the command specified by the `-Command` parameter of `pwsh` when invoked from the command line.</span></span> <span data-ttu-id="910ad-187">Das folgende Beispiel wird in der Windows-Befehlsshell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="910ad-187">The following example is run from the Windows Command shell.</span></span>

```CMD
echo Hello | pwsh -Command """$input World!"""
```

### <a name="iscoreclr"></a><span data-ttu-id="910ad-188">$IsCoreCLR</span><span class="sxs-lookup"><span data-stu-id="910ad-188">$IsCoreCLR</span></span>

<span data-ttu-id="910ad-189">Enthält, `$True` Wenn die aktuelle Sitzung auf der .net Core-Laufzeit (CoreCLR) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-189">Contains `$True` if the current session is running on the .NET Core Runtime (CoreCLR).</span></span> <span data-ttu-id="910ad-190">Andernfalls enthält `$False` .</span><span class="sxs-lookup"><span data-stu-id="910ad-190">Otherwise contains `$False`.</span></span>

### <a name="islinux"></a><span data-ttu-id="910ad-191">$IsLinux</span><span class="sxs-lookup"><span data-stu-id="910ad-191">$IsLinux</span></span>

<span data-ttu-id="910ad-192">Enthält, `$True` Wenn die aktuelle Sitzung unter einem Linux-Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-192">Contains `$True` if the current session is running on a Linux operating system.</span></span>
<span data-ttu-id="910ad-193">Andernfalls enthält `$False` .</span><span class="sxs-lookup"><span data-stu-id="910ad-193">Otherwise contains `$False`.</span></span>

### <a name="ismacos"></a><span data-ttu-id="910ad-194">$IsMacOS</span><span class="sxs-lookup"><span data-stu-id="910ad-194">$IsMacOS</span></span>

<span data-ttu-id="910ad-195">Enthält, `$True` Wenn die aktuelle Sitzung unter einem MacOS-Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-195">Contains `$True` if the current session is running on a MacOS operating system.</span></span>
<span data-ttu-id="910ad-196">Andernfalls enthält `$False` .</span><span class="sxs-lookup"><span data-stu-id="910ad-196">Otherwise contains `$False`.</span></span>

### <a name="iswindows"></a><span data-ttu-id="910ad-197">$IsWindows</span><span class="sxs-lookup"><span data-stu-id="910ad-197">$IsWindows</span></span>

<span data-ttu-id="910ad-198">Enthält, `$TRUE` Wenn die aktuelle Sitzung unter einem Windows-Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-198">Contains `$TRUE` if the current session is running on a Windows operating system.</span></span> <span data-ttu-id="910ad-199">Andernfalls enthält `$FALSE` .</span><span class="sxs-lookup"><span data-stu-id="910ad-199">Otherwise contains `$FALSE`.</span></span>

### <a name="lastexitcode"></a><span data-ttu-id="910ad-200">$LastExitCode</span><span class="sxs-lookup"><span data-stu-id="910ad-200">$LastExitCode</span></span>

<span data-ttu-id="910ad-201">Enthält den Exitcode des letzten Windows-basierten Programms, das ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="910ad-201">Contains the exit code of the last Windows-based program that was run.</span></span>

### <a name="matches"></a><span data-ttu-id="910ad-202">$Matches</span><span class="sxs-lookup"><span data-stu-id="910ad-202">$Matches</span></span>

<span data-ttu-id="910ad-203">Die `Matches` -Variable funktioniert mit `-match` den `-notmatch` Operatoren und.</span><span class="sxs-lookup"><span data-stu-id="910ad-203">The `Matches` variable works with the `-match` and `-notmatch` operators.</span></span>
<span data-ttu-id="910ad-204">Wenn Sie skalare Eingaben an den `-match` `-notmatch` -Operator oder den-Operator übermitteln und eine Übereinstimmung erkannt wird, wird ein boolescher Wert zurückgegeben, und die `$Matches` Automatische Variable wird mit einer Hash Tabelle mit allen übereinstimmenden Zeichen folgen Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="910ad-204">When you submit scalar input to the `-match` or `-notmatch` operator, and either one detects a match, they return a Boolean value and populate the `$Matches` automatic variable with a hash table of any string values that were matched.</span></span> <span data-ttu-id="910ad-205">Die `$Matches` Hash Tabelle kann auch mit Erfassungen aufgefüllt werden, wenn Sie reguläre Ausdrücke mit dem- `-match` Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="910ad-205">The `$Matches` hash table can also be populated with captures when you use regular expressions with the `-match` operator.</span></span>

<span data-ttu-id="910ad-206">Weitere Informationen zum- `-match` Operator finden Sie unter [about_Comparison_Operators](about_comparison_operators.md).</span><span class="sxs-lookup"><span data-stu-id="910ad-206">For more information about the `-match` operator, see [about_Comparison_Operators](about_comparison_operators.md).</span></span> <span data-ttu-id="910ad-207">Weitere Informationen zu regulären Ausdrücken finden Sie unter [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="910ad-207">For more information on regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

<span data-ttu-id="910ad-208">Die- `$Matches` Variable kann auch in einer- `switch` Anweisung mit dem-Parameter verwendet werden `-Regex` .</span><span class="sxs-lookup"><span data-stu-id="910ad-208">The `$Matches` variable also works in a `switch` statement with the `-Regex` parameter.</span></span> <span data-ttu-id="910ad-209">Es wird auf die gleiche Weise wie die `-match` -und- `-notmatch` Operatoren aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="910ad-209">It's populated the same way as the `-match` and `-notmatch` operators.</span></span>
<span data-ttu-id="910ad-210">Weitere Informationen zur- `switch` Anweisung finden Sie unter [about_Switch](about_Switch.md).</span><span class="sxs-lookup"><span data-stu-id="910ad-210">For more information about the `switch` statement, see [about_Switch](about_Switch.md).</span></span>

### <a name="myinvocation"></a><span data-ttu-id="910ad-211">$MyInvocation</span><span class="sxs-lookup"><span data-stu-id="910ad-211">$MyInvocation</span></span>

<span data-ttu-id="910ad-212">Enthält Informationen über den aktuellen Befehl, z. b. den Namen, die Parameter, die Parameterwerte und Informationen darüber, wie der Befehl gestartet, aufgerufen oder aufgerufen wurde, z. b. der Name des Skripts, das den aktuellen Befehl aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="910ad-212">Contains information about the current command, such as the name, parameters, parameter values, and information about how the command was started, called, or invoked, such as the name of the script that called the current command.</span></span>

<span data-ttu-id="910ad-213">`$MyInvocation` wird nur für Skripts, Funktionen und Skriptblöcke aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="910ad-213">`$MyInvocation` is populated only for scripts, function, and script blocks.</span></span> <span data-ttu-id="910ad-214">Sie können die Informationen im **System. Management. Automation. invocationinfo** -Objekt verwenden, das `$MyInvocation` im aktuellen Skript zurückgibt, wie z. b. den Pfad und den Dateinamen des Skripts ( `$MyInvocation.MyCommand.Path` ) oder den Namen einer Funktion ( `$MyInvocation.MyCommand.Name` ), um den aktuellen Befehl zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="910ad-214">You can use the information in the **System.Management.Automation.InvocationInfo** object that `$MyInvocation` returns in the current script, such as the path and file name of the script (`$MyInvocation.MyCommand.Path`) or the name of a function (`$MyInvocation.MyCommand.Name`) to identify the current command.</span></span> <span data-ttu-id="910ad-215">Dies ist besonders nützlich, um den Namen des aktuellen Skripts zu suchen.</span><span class="sxs-lookup"><span data-stu-id="910ad-215">This is particularly useful for finding the name of the current script.</span></span>

<span data-ttu-id="910ad-216">Ab PowerShell 3,0 `MyInvocation` verfügt über die folgenden neuen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="910ad-216">Beginning in PowerShell 3.0, `MyInvocation` has the following new properties.</span></span>

- <span data-ttu-id="910ad-217">**Psscriptroot** : enthält den vollständigen Pfad zu dem Skript, das den aktuellen Befehl aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="910ad-217">**PSScriptRoot** - Contains the full path to the script that invoked the current command.</span></span> <span data-ttu-id="910ad-218">Der Wert dieser Eigenschaft wird nur aufgefüllt, wenn der Aufrufer ein Skript ist.</span><span class="sxs-lookup"><span data-stu-id="910ad-218">The value of this property is populated only when the caller is a script.</span></span>
- <span data-ttu-id="910ad-219">**Pscommandpath** : enthält den vollständigen Pfad und den Dateinamen des Skripts, das den aktuellen Befehl aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="910ad-219">**PSCommandPath** - Contains the full path and file name of the script that invoked the current command.</span></span> <span data-ttu-id="910ad-220">Der Wert dieser Eigenschaft wird nur aufgefüllt, wenn der Aufrufer ein Skript ist.</span><span class="sxs-lookup"><span data-stu-id="910ad-220">The value of this property is populated only when the caller is a script.</span></span>

<span data-ttu-id="910ad-221">Im Gegensatz zu den `$PSScriptRoot` `$PSCommandPath` automatischen Variablen und enthalten die Eigenschaften **psscriptroot** und **pscommandpath** der `$MyInvocation` automatischen Variablen Informationen über den aufrufenden oder das aufrufende Skript, nicht über das aktuelle Skript.</span><span class="sxs-lookup"><span data-stu-id="910ad-221">Unlike the `$PSScriptRoot` and `$PSCommandPath` automatic variables, the **PSScriptRoot** and **PSCommandPath** properties of the `$MyInvocation` automatic variable contain information about the invoker or calling script, not the current script.</span></span>

### <a name="nestedpromptlevel"></a><span data-ttu-id="910ad-222">$NestedPromptLevel</span><span class="sxs-lookup"><span data-stu-id="910ad-222">$NestedPromptLevel</span></span>

<span data-ttu-id="910ad-223">Enthält die aktuelle Eingabe Aufforderungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="910ad-223">Contains the current prompt level.</span></span> <span data-ttu-id="910ad-224">Der Wert 0 gibt die ursprüngliche Eingabe Aufforderungs Ebene an.</span><span class="sxs-lookup"><span data-stu-id="910ad-224">A value of 0 indicates the original prompt level.</span></span> <span data-ttu-id="910ad-225">Der Wert wird erhöht, wenn Sie eine eingefügte Ebene eingeben und dekrementiert werden, wenn Sie Sie beenden.</span><span class="sxs-lookup"><span data-stu-id="910ad-225">The value is incremented when you enter a nested level and decremented when you exit it.</span></span>

<span data-ttu-id="910ad-226">PowerShell zeigt z. b. eine eingefügte Eingabeaufforderung an, wenn Sie die- `$Host.EnterNestedPrompt` Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="910ad-226">For example, PowerShell presents a nested command prompt when you use the `$Host.EnterNestedPrompt` method.</span></span> <span data-ttu-id="910ad-227">PowerShell zeigt auch eine eingefügte Eingabeaufforderung an, wenn Sie einen Breakpoint im PowerShell-Debugger erreichen.</span><span class="sxs-lookup"><span data-stu-id="910ad-227">PowerShell also presents a nested command prompt when you reach a breakpoint in the PowerShell debugger.</span></span>

<span data-ttu-id="910ad-228">Wenn Sie eine eingefügte Eingabeaufforderung eingeben, hält PowerShell den aktuellen Befehl an, speichert den Ausführungs Kontext und erhöht den Wert der `$NestedPromptLevel` Variablen.</span><span class="sxs-lookup"><span data-stu-id="910ad-228">When you enter a nested prompt, PowerShell pauses the current command, saves the execution context, and increments the value of the `$NestedPromptLevel` variable.</span></span> <span data-ttu-id="910ad-229">Um zusätzliche Eingabe Aufforderungen für ein Eingabefenster (bis zu 128 Ebenen) zu erstellen oder zur ursprünglichen Eingabeaufforderung zurückzukehren, führen Sie den Befehl aus, oder geben Sie ein `exit` .</span><span class="sxs-lookup"><span data-stu-id="910ad-229">To create additional nested command prompts (up to 128 levels) or to return to the original command prompt, complete the command, or type `exit`.</span></span>

<span data-ttu-id="910ad-230">Die- `$NestedPromptLevel` Variable hilft Ihnen beim Nachverfolgen der Eingabe Aufforderungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="910ad-230">The `$NestedPromptLevel` variable helps you track the prompt level.</span></span> <span data-ttu-id="910ad-231">Sie können eine Alternative PowerShell-Eingabeaufforderung erstellen, die diesen Wert enthält, sodass er immer sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="910ad-231">You can create an alternative PowerShell command prompt that includes this value so that it's always visible.</span></span>

### <a name="null"></a><span data-ttu-id="910ad-232">$null</span><span class="sxs-lookup"><span data-stu-id="910ad-232">$null</span></span>

<span data-ttu-id="910ad-233">`$null` eine automatische Variable, die einen **null** -Wert oder einen leeren Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="910ad-233">`$null` is an automatic variable that contains a **null** or empty value.</span></span> <span data-ttu-id="910ad-234">Mit dieser Variablen können Sie einen fehlenden oder nicht definierten Wert in Befehlen und Skripts darstellen.</span><span class="sxs-lookup"><span data-stu-id="910ad-234">You can use this variable to represent an absent or undefined value in commands and scripts.</span></span>

<span data-ttu-id="910ad-235">PowerShell behandelt `$null` als ein Objekt mit einem Wert, d. h. als expliziter Platzhalter, damit Sie `$null` einen leeren Wert in einer Reihe von Werten darstellen können.</span><span class="sxs-lookup"><span data-stu-id="910ad-235">PowerShell treats `$null` as an object with a value, that is, as an explicit placeholder, so you can use `$null` to represent an empty value in a series of values.</span></span>

<span data-ttu-id="910ad-236">Wenn z. b `$null` . in einer Auflistung enthalten ist, wird Sie als eines der-Objekte gezählt.</span><span class="sxs-lookup"><span data-stu-id="910ad-236">For example, when `$null` is included in a collection, it's counted as one of the objects.</span></span>

```powershell
$a = "one", $null, "three"
$a.count
```

```Output
3
```

<span data-ttu-id="910ad-237">Wenn Sie die `$null` Variable an das `ForEach-Object` Cmdlet weiterreichen, generiert Sie einen Wert für `$null` , genau wie für die anderen Objekte.</span><span class="sxs-lookup"><span data-stu-id="910ad-237">If you pipe the `$null` variable to the `ForEach-Object` cmdlet, it generates a value for `$null`, just as it does for the other objects</span></span>

```powershell
"one", $null, "three" | ForEach-Object { "Hello " + $_}
```

```Output
Hello one
Hello
Hello three
```

<span data-ttu-id="910ad-238">Daher können Sie `$null` nicht verwenden, um **keinen Parameterwert** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="910ad-238">As a result, you can't use `$null` to mean **no parameter value**.</span></span> <span data-ttu-id="910ad-239">Der Parameterwert `$null` überschreibt den Standardparameter Wert.</span><span class="sxs-lookup"><span data-stu-id="910ad-239">A parameter value of `$null` overrides the default parameter value.</span></span>

<span data-ttu-id="910ad-240">Da die Variable von PowerShell jedoch `$null` als Platzhalter behandelt wird, können Sie Sie in Skripts wie dem folgenden verwenden, was nicht funktioniert, wenn Sie `$null` ignoriert wurden.</span><span class="sxs-lookup"><span data-stu-id="910ad-240">However, because PowerShell treats the `$null` variable as a placeholder, you can use it in scripts like the following one, which wouldn't work if `$null` were ignored.</span></span>

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

### <a name="pid"></a><span data-ttu-id="910ad-241">$PID</span><span class="sxs-lookup"><span data-stu-id="910ad-241">$PID</span></span>

<span data-ttu-id="910ad-242">Enthält die Prozess-ID (PID) des Prozesses, in dem die aktuelle PowerShell-Sitzung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-242">Contains the process identifier (PID) of the process that is hosting the current PowerShell session.</span></span>

### <a name="profile"></a><span data-ttu-id="910ad-243">$PROFILE</span><span class="sxs-lookup"><span data-stu-id="910ad-243">$PROFILE</span></span>

<span data-ttu-id="910ad-244">Enthält den vollständigen Pfad des PowerShell-Profils für den aktuellen Benutzer und die aktuelle Host Anwendung.</span><span class="sxs-lookup"><span data-stu-id="910ad-244">Contains the full path of the PowerShell profile for the current user and the current host application.</span></span> <span data-ttu-id="910ad-245">Mit dieser Variablen können Sie das Profil in Befehlen darstellen.</span><span class="sxs-lookup"><span data-stu-id="910ad-245">You can use this variable to represent the profile in commands.</span></span> <span data-ttu-id="910ad-246">Beispielsweise können Sie ihn in einem Befehl verwenden, um zu bestimmen, ob ein Profil erstellt wurde:</span><span class="sxs-lookup"><span data-stu-id="910ad-246">For example, you can use it in a command to determine whether a profile has been created:</span></span>

```powershell
Test-Path $PROFILE
```

<span data-ttu-id="910ad-247">Oder Sie können Sie in einem Befehl verwenden, um ein Profil zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="910ad-247">Or, you can use it in a command to create a profile:</span></span>

```powershell
New-Item -ItemType file -Path $PROFILE -Force
```

<span data-ttu-id="910ad-248">Sie können Sie in einem Befehl verwenden, um das Profil in **notepad.exe** zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="910ad-248">You can use it in a command to open the profile in **notepad.exe**:</span></span>

```powershell
notepad.exe $PROFILE
```

### <a name="psboundparameters"></a><span data-ttu-id="910ad-249">$PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="910ad-249">$PSBoundParameters</span></span>

<span data-ttu-id="910ad-250">Enthält ein Wörterbuch mit den Parametern, die an ein Skript oder eine Funktion und ihre aktuellen Werte übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="910ad-250">Contains a dictionary of the parameters that are passed to a script or function and their current values.</span></span> <span data-ttu-id="910ad-251">Diese Variable hat nur einen Wert in einem Bereich, in dem Parameter deklariert werden, z. b. ein Skript oder eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="910ad-251">This variable has a value only in a scope where parameters are declared, such as a script or function.</span></span> <span data-ttu-id="910ad-252">Sie können Sie verwenden, um die aktuellen Parameterwerte anzuzeigen oder zu ändern oder um Parameterwerte an ein anderes Skript oder eine andere Funktion zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="910ad-252">You can use it to display or change the current values of parameters or to pass parameter values to another script or function.</span></span>

<span data-ttu-id="910ad-253">In diesem Beispiel übergibt die **test2** -Funktion `$PSBoundParameters` an die **test1** -Funktion.</span><span class="sxs-lookup"><span data-stu-id="910ad-253">In this example, the **Test2** function passes the `$PSBoundParameters` to the **Test1** function.</span></span> <span data-ttu-id="910ad-254">Die `$PSBoundParameters` werden im Format von **Key** und **value** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="910ad-254">The `$PSBoundParameters` are displayed in the format of **Key** and **Value**.</span></span>

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

### <a name="pscmdlet"></a><span data-ttu-id="910ad-255">$PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="910ad-255">$PSCmdlet</span></span>

<span data-ttu-id="910ad-256">Enthält ein-Objekt, das das Cmdlet oder die erweiterte Funktion darstellt, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-256">Contains an object that represents the cmdlet or advanced function that's being run.</span></span>

<span data-ttu-id="910ad-257">Sie können die Eigenschaften und Methoden des-Objekts im Cmdlet oder Funktionscode verwenden, um auf die Nutzungsbedingungen zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="910ad-257">You can use the properties and methods of the object in your cmdlet or function code to respond to the conditions of use.</span></span> <span data-ttu-id="910ad-258">Beispielsweise enthält die **parametersetname** -Eigenschaft den Namen des verwendeten Parameter Satzes, und die Methode " **schuldprocess** " fügt die Parameter " **WhatIf** " und " **Confirm** " dem Cmdlet dynamisch hinzu.</span><span class="sxs-lookup"><span data-stu-id="910ad-258">For example, the **ParameterSetName** property contains the name of the parameter set that's being used, and the **ShouldProcess** method adds the **WhatIf** and **Confirm** parameters to the cmdlet dynamically.</span></span>

<span data-ttu-id="910ad-259">Weitere Informationen über die `$PSCmdlet` Automatische Variable finden Sie unter [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) und [about_Functions_Advanced](about_Functions_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="910ad-259">For more information about the `$PSCmdlet` automatic variable, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) and [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

### <a name="pscommandpath"></a><span data-ttu-id="910ad-260">$PSCommandPath</span><span class="sxs-lookup"><span data-stu-id="910ad-260">$PSCommandPath</span></span>

<span data-ttu-id="910ad-261">Enthält den vollständigen Pfad und den Dateinamen des Skripts, das gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-261">Contains the full path and file name of the script that's being run.</span></span> <span data-ttu-id="910ad-262">Diese Variable ist in allen Skripts gültig.</span><span class="sxs-lookup"><span data-stu-id="910ad-262">This variable is valid in all scripts.</span></span>

### <a name="psculture"></a><span data-ttu-id="910ad-263">$PSCulture</span><span class="sxs-lookup"><span data-stu-id="910ad-263">$PSCulture</span></span>

<span data-ttu-id="910ad-264">Ab PowerShell 7 gibt `$PSCulture` die Kultur des aktuellen PowerShell-Runspace (Session) wieder.</span><span class="sxs-lookup"><span data-stu-id="910ad-264">Beginning in PowerShell 7, `$PSCulture` reflects the culture of the current PowerShell runspace (session).</span></span> <span data-ttu-id="910ad-265">Wenn die Kultur in einem PowerShell-Runspace geändert wird, `$PSCulture` wird der Wert für diesen Runspace aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="910ad-265">If the culture is changed in a PowerShell runspace, the `$PSCulture` value for that runspace is updated.</span></span>

<span data-ttu-id="910ad-266">Die Kultur bestimmt das Anzeige Format von Elementen, z. b. Zahlen, Währungen und Datumsangaben, und wird in einem **System. Globalization. CultureInfo** -Objekt gespeichert.</span><span class="sxs-lookup"><span data-stu-id="910ad-266">The culture determines the display format of items such as numbers, currency, and dates, and is stored in a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="910ad-267">Verwenden `Get-Culture` Sie, um die Kultur des Computers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="910ad-267">Use `Get-Culture` to display the computer's culture.</span></span> <span data-ttu-id="910ad-268">`$PSCulture` enthält den Wert der **Name** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="910ad-268">`$PSCulture` contains the **Name** property's value.</span></span>

### <a name="psdebugcontext"></a><span data-ttu-id="910ad-269">$PSDebugContext</span><span class="sxs-lookup"><span data-stu-id="910ad-269">$PSDebugContext</span></span>

<span data-ttu-id="910ad-270">Beim Debuggen enthält diese Variable Informationen zur Debugumgebung.</span><span class="sxs-lookup"><span data-stu-id="910ad-270">While debugging, this variable contains information about the debugging environment.</span></span> <span data-ttu-id="910ad-271">Andernfalls enthält Sie einen **null** -Wert.</span><span class="sxs-lookup"><span data-stu-id="910ad-271">Otherwise, it contains a **null** value.</span></span> <span data-ttu-id="910ad-272">Daher können Sie damit angeben, ob der Debugger über Steuerelemente verfügt.</span><span class="sxs-lookup"><span data-stu-id="910ad-272">As a result, you can use it to indicate whether the debugger has control.</span></span> <span data-ttu-id="910ad-273">Wenn Sie aufgefüllt ist, enthält Sie ein **psdebugcontext** -Objekt mit **Breakpoints** und **invocationinfo** -Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="910ad-273">When populated, it contains a **PsDebugContext** object that has **Breakpoints** and **InvocationInfo** properties.</span></span> <span data-ttu-id="910ad-274">Die **invocationinfo** -Eigenschaft verfügt über mehrere nützliche Eigenschaften, einschließlich der **Location** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="910ad-274">The **InvocationInfo** property has several useful properties, including the **Location** property.</span></span> <span data-ttu-id="910ad-275">Die **Location** -Eigenschaft gibt den Pfad des Skripts an, das gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-275">The **Location** property indicates the path of the script that is being debugged.</span></span>

### <a name="pshome"></a><span data-ttu-id="910ad-276">$PSHOME</span><span class="sxs-lookup"><span data-stu-id="910ad-276">$PSHOME</span></span>

<span data-ttu-id="910ad-277">Enthält den vollständigen Pfad des Installationsverzeichnisses für PowerShell (in der Regel `$env:windir\System32\PowerShell\v1.0` in Windows-Systemen).</span><span class="sxs-lookup"><span data-stu-id="910ad-277">Contains the full path of the installation directory for PowerShell, typically, `$env:windir\System32\PowerShell\v1.0` in Windows systems.</span></span> <span data-ttu-id="910ad-278">Sie können diese Variable in den Pfaden von PowerShell-Dateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="910ad-278">You can use this variable in the paths of PowerShell files.</span></span> <span data-ttu-id="910ad-279">Mit dem folgenden Befehl werden z. b. die konzeptionellen Hilfe Themen nach der Word- **Variablen** durchsucht:</span><span class="sxs-lookup"><span data-stu-id="910ad-279">For example, the following command searches the conceptual Help topics for the word **variable**:</span></span>

```powershell
Select-String -Pattern Variable -Path $pshome\*.txt
```

### <a name="psitem"></a><span data-ttu-id="910ad-280">$PSItem</span><span class="sxs-lookup"><span data-stu-id="910ad-280">$PSItem</span></span>

<span data-ttu-id="910ad-281">Wie in `$_`.</span><span class="sxs-lookup"><span data-stu-id="910ad-281">Same as `$_`.</span></span> <span data-ttu-id="910ad-282">Enthält das aktuelle-Objekt im Pipeline Objekt.</span><span class="sxs-lookup"><span data-stu-id="910ad-282">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="910ad-283">Sie können diese Variable in Befehlen verwenden, die eine Aktion für jedes Objekt oder für ausgewählte Objekte in einer Pipeline ausführen.</span><span class="sxs-lookup"><span data-stu-id="910ad-283">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="psscriptroot"></a><span data-ttu-id="910ad-284">$PSScriptRoot</span><span class="sxs-lookup"><span data-stu-id="910ad-284">$PSScriptRoot</span></span>

<span data-ttu-id="910ad-285">Enthält das Verzeichnis, in dem ein Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-285">Contains the directory from which a script is being run.</span></span>

<span data-ttu-id="910ad-286">In PowerShell 2,0 ist diese Variable nur in Skript Modulen () gültig `.psm1` .</span><span class="sxs-lookup"><span data-stu-id="910ad-286">In PowerShell 2.0, this variable is valid only in script modules (`.psm1`).</span></span>
<span data-ttu-id="910ad-287">Ab PowerShell 3,0 ist Sie in allen Skripts gültig.</span><span class="sxs-lookup"><span data-stu-id="910ad-287">Beginning in PowerShell 3.0, it's valid in all scripts.</span></span>

### <a name="pssenderinfo"></a><span data-ttu-id="910ad-288">$PSSenderInfo</span><span class="sxs-lookup"><span data-stu-id="910ad-288">$PSSenderInfo</span></span>

<span data-ttu-id="910ad-289">Enthält Informationen über den Benutzer, der die PSSession gestartet hat, einschließlich der Benutzeridentität und der Zeitzone des Ursprungs Computers.</span><span class="sxs-lookup"><span data-stu-id="910ad-289">Contains information about the user who started the PSSession, including the user identity and the time zone of the originating computer.</span></span> <span data-ttu-id="910ad-290">Diese Variable ist nur in pssessions verfügbar.</span><span class="sxs-lookup"><span data-stu-id="910ad-290">This variable is available only in PSSessions.</span></span>

<span data-ttu-id="910ad-291">Die `$PSSenderInfo` -Variable enthält eine vom benutzerkonfigurierbare Eigenschaft **applicationarguments**, die standardmäßig nur die `$PSVersionTable` aus der ursprünglichen Sitzung enthält.</span><span class="sxs-lookup"><span data-stu-id="910ad-291">The `$PSSenderInfo` variable includes a user-configurable property, **ApplicationArguments**, that by default, contains only the `$PSVersionTable` from the originating session.</span></span> <span data-ttu-id="910ad-292">Um der **applicationarguments** -Eigenschaft Daten hinzuzufügen, verwenden Sie den **applicationarguments** -Parameter des `New-PSSessionOption` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="910ad-292">To add data to the **ApplicationArguments** property, use the **ApplicationArguments** parameter of the `New-PSSessionOption` cmdlet.</span></span>

### <a name="psstyle"></a><span data-ttu-id="910ad-293">$PSStyle</span><span class="sxs-lookup"><span data-stu-id="910ad-293">$PSStyle</span></span>

> [!NOTE]
> <span data-ttu-id="910ad-294">Diese Variable ist nur verfügbar, wenn die `PSAnsiRendering` experimentelle Funktion aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="910ad-294">This variable is only available when the `PSAnsiRendering` experimental feature ia enabled.</span></span> <span data-ttu-id="910ad-295">Weitere Informationen finden Sie unter [about_Experimental_Features](about_Experimental_Features.md) und [Verwenden von experimentellen Features](/powershell/scripting/learn/experimental-features).</span><span class="sxs-lookup"><span data-stu-id="910ad-295">For more information, see [about_Experimental_Features](about_Experimental_Features.md) and [Using experimental features](/powershell/scripting/learn/experimental-features).</span></span>

<span data-ttu-id="910ad-296">Ab PowerShell 7,2 können Sie nun `$PSStyle` auf die automatische Variable zugreifen, um das Rendering der ANSI-Zeichen folgen Ausgabe anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="910ad-296">As of PowerShell 7.2 you can now access the `$PSStyle` automatic variable to view and change the rendering of ANSI string output.</span></span> <span data-ttu-id="910ad-297">Die-Variable enthält die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="910ad-297">The variable contains the following properties:</span></span>

- <span data-ttu-id="910ad-298">**Reset** : deaktiviert alle Dekorationen</span><span class="sxs-lookup"><span data-stu-id="910ad-298">**Reset** - Turns off all decorations</span></span>
- <span data-ttu-id="910ad-299">Im **Hintergrund** vorgesteueretes Objekt zum Steuern der Hintergrund Färbung</span><span class="sxs-lookup"><span data-stu-id="910ad-299">**Background** - Nested object to control background coloring</span></span>
- <span data-ttu-id="910ad-300">**Blink** blinkt</span><span class="sxs-lookup"><span data-stu-id="910ad-300">**Blink** - Turns Blink on</span></span>
- <span data-ttu-id="910ad-301">**Blinkoff** -blinkt ausschalten</span><span class="sxs-lookup"><span data-stu-id="910ad-301">**BlinkOff** - Turns Blink off</span></span>
- <span data-ttu-id="910ad-302">**Fett** formatiert: fett formatiert</span><span class="sxs-lookup"><span data-stu-id="910ad-302">**Bold** - Turns Bold on</span></span>
- <span data-ttu-id="910ad-303">**Boldoff** -wird fett formatiert</span><span class="sxs-lookup"><span data-stu-id="910ad-303">**BoldOff** - Turns Bold off</span></span>
- <span data-ttu-id="910ad-304">**Vordergrund** : das Objekt zum Steuern der Vordergrundfarbe.</span><span class="sxs-lookup"><span data-stu-id="910ad-304">**Foreground** - Nested object to control foreground coloring</span></span>
- <span data-ttu-id="910ad-305">**Formatierung** : steuert die Standard Formatierung für Ausgabestreams.</span><span class="sxs-lookup"><span data-stu-id="910ad-305">**Formatting** - Controls default formatting for output streams</span></span>
- <span data-ttu-id="910ad-306">**Ausgeblendet** : wird ausgeblendet am</span><span class="sxs-lookup"><span data-stu-id="910ad-306">**Hidden** - Turns Hidden on</span></span>
- <span data-ttu-id="910ad-307">**Hiddenoff** -schaltet ausgeblendet</span><span class="sxs-lookup"><span data-stu-id="910ad-307">**HiddenOff** - Turns Hidden off</span></span>
- <span data-ttu-id="910ad-308">**Outputrends** -steuern, wann das Ausgabe Rendering verwendet wird</span><span class="sxs-lookup"><span data-stu-id="910ad-308">**OutputRendering** - Control when output rendering is used</span></span>
- <span data-ttu-id="910ad-309">**Umgekehrtes** umkehren</span><span class="sxs-lookup"><span data-stu-id="910ad-309">**Reverse** - Turns Reverse on</span></span>
- <span data-ttu-id="910ad-310">**Reverseoff** -schaltet umkehren</span><span class="sxs-lookup"><span data-stu-id="910ad-310">**ReverseOff** - Turns Reverse off</span></span>
- <span data-ttu-id="910ad-311">**Kursiv** -kursiv formatiert</span><span class="sxs-lookup"><span data-stu-id="910ad-311">**Italic** - Turns Italic on</span></span>
- <span data-ttu-id="910ad-312">**Italicoff** -kursiv formatiert</span><span class="sxs-lookup"><span data-stu-id="910ad-312">**ItalicOff** - Turns Italic off</span></span>
- <span data-ttu-id="910ad-313">Unter **Streichung: unter** Streichung wird unterstrichen</span><span class="sxs-lookup"><span data-stu-id="910ad-313">**Underline** - Turns underlining on</span></span>
- <span data-ttu-id="910ad-314">**Underlineoff-unter** Streichung wird deaktiviert</span><span class="sxs-lookup"><span data-stu-id="910ad-314">**UnderlineOff** - Turns underlining off</span></span>

<span data-ttu-id="910ad-315">Die Basismember geben Zeichenfolgen von ANSI-Escapesequenzen zurück, die ihren Namen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="910ad-315">The base members return strings of ANSI escape sequences mapped to their names.</span></span>
<span data-ttu-id="910ad-316">Die Werte können beliebig angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="910ad-316">The values are settable to allow customization.</span></span> <span data-ttu-id="910ad-317">Beispielsweise können Sie Fett in unterstrichen ändern.</span><span class="sxs-lookup"><span data-stu-id="910ad-317">For example, you could change bold to underlined.</span></span> <span data-ttu-id="910ad-318">Die Eigenschaften Namen erleichtern Ihnen das Erstellen von ergänzten Zeichen folgen mithilfe der Vervollständigung mit der Tab-Taste:</span><span class="sxs-lookup"><span data-stu-id="910ad-318">The property names makes it easier for you to create decorated strings using tab completion:</span></span>

```powershell
"$($PSStyle.Background.LightCyan)Power$($PSStyle.Underline)$($PSStyle.Bold)Shell$($PSStyle.Reset)"
```

<span data-ttu-id="910ad-319">Das `$PSStyle.Background` -Element und das-Element `$PSStyle.Foreground` sind Zeichen folgen, die die ANSI-Escapesequenzen für die 16 Standard Konsolen Farben und eine- `Rgb()` Methode zum Angeben von 24-Bit-Farben enthalten.</span><span class="sxs-lookup"><span data-stu-id="910ad-319">The `$PSStyle.Background` and `$PSStyle.Foreground` members are strings that contain the ANSI escape sequences for the 16 standard console colors as well as an `Rgb()` method to specify 24-bit color.</span></span> <span data-ttu-id="910ad-320">Die Werte sind feststellbar und können beliebig viele ANSI-Escapesequenzen enthalten.</span><span class="sxs-lookup"><span data-stu-id="910ad-320">The values are settable and can contain any number of ANSI escape sequences.</span></span>

<span data-ttu-id="910ad-321">`$PSStyle.Formatting` ist ein gespeichertes Objekt zum Steuern der Standard Formatierung von Debug-, Fehler-, verbose-und Warnmeldungen.</span><span class="sxs-lookup"><span data-stu-id="910ad-321">`$PSStyle.Formatting` is a nested object to control default formatting of debug, error, verbose, and warning messages.</span></span> <span data-ttu-id="910ad-322">Sie können auch Attribute wie fett formatieren und unterstreichen steuern.</span><span class="sxs-lookup"><span data-stu-id="910ad-322">You can also control attributes like bolding and underlining.</span></span> <span data-ttu-id="910ad-323">Es ersetzt `$Host.PrivateData` die Methode zum Verwalten von Farben für das Formatieren von Rendering.</span><span class="sxs-lookup"><span data-stu-id="910ad-323">It replaces `$Host.PrivateData` as the way to manage colors for formatting rendering.</span></span> <span data-ttu-id="910ad-324">`$Host.PrivateData` ist weiterhin aus Gründen der Abwärtskompatibilität vorhanden, ist jedoch nicht mit verbunden `$PSStyle.Formatting` .</span><span class="sxs-lookup"><span data-stu-id="910ad-324">`$Host.PrivateData` continues to exist for backwards compatibility but is not connected to `$PSStyle.Formatting`.</span></span>

<span data-ttu-id="910ad-325">`$PSStyle.OutputRendering` ist eine Enumeration `System.Management.Automation.OutputRendering` mit den Werten:</span><span class="sxs-lookup"><span data-stu-id="910ad-325">`$PSStyle.OutputRendering` is a `System.Management.Automation.OutputRendering` enum with the values:</span></span>

- <span data-ttu-id="910ad-326">**Automatisch**: Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="910ad-326">**Automatic**: This is the default.</span></span> <span data-ttu-id="910ad-327">Wenn der Host virtualterminal unterstützt, wird ANSI immer unverändert weitergegeben, andernfalls Klartext.</span><span class="sxs-lookup"><span data-stu-id="910ad-327">If the host supports VirtualTerminal, then ANSI is always passed as-is, otherwise plaintext</span></span>
- <span data-ttu-id="910ad-328">**ANSI**: ANSI wird immer unverändert durchlaufen</span><span class="sxs-lookup"><span data-stu-id="910ad-328">**ANSI**: ANSI is always passed through as-is</span></span>
- <span data-ttu-id="910ad-329">**Klartext**: ANSI-Escapesequenzen werden immer entfernt, sodass es nur nur-Text ist.</span><span class="sxs-lookup"><span data-stu-id="910ad-329">**PlainText**: ANSI escape sequences are always stripped so that it is only plain text</span></span>
- <span data-ttu-id="910ad-330">**Hostonly**: Dies ist das macOS-Verhalten, bei dem die ANSI-Escapesequenzen in der umgeleiteten oder weitergeleiteten Ausgabe entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="910ad-330">**HostOnly**: This would be the macOS behavior where the ANSI escape sequences are removed in redirected or piped output.</span></span>

### <a name="psuiculture"></a><span data-ttu-id="910ad-331">$PSUICulture</span><span class="sxs-lookup"><span data-stu-id="910ad-331">$PSUICulture</span></span>

<span data-ttu-id="910ad-332">Enthält den Namen der Kultur der Benutzeroberfläche (UI), die derzeit im Betriebssystem verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-332">Contains the name of the user interface (UI) culture that's currently in use in the operating system.</span></span> <span data-ttu-id="910ad-333">Die Benutzeroberflächenkultur bestimmt, welche Textzeichenfolgen für die Benutzeroberflächenelemente, z. B. Menüs und Meldungen, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="910ad-333">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span> <span data-ttu-id="910ad-334">Dies ist der Wert der **System.Globalization.CultureInfo.CurrentUICulture.Name** -Eigenschaft des Systems.</span><span class="sxs-lookup"><span data-stu-id="910ad-334">This is the value of the **System.Globalization.CultureInfo.CurrentUICulture.Name** property of the system.</span></span> <span data-ttu-id="910ad-335">Verwenden Sie das-Cmdlet, um das **System. Globalization. CultureInfo** -Objekt für das System zu erhalten `Get-UICulture` .</span><span class="sxs-lookup"><span data-stu-id="910ad-335">To get the **System.Globalization.CultureInfo** object for the system, use the `Get-UICulture` cmdlet.</span></span>

### <a name="psversiontable"></a><span data-ttu-id="910ad-336">$PSVersionTable</span><span class="sxs-lookup"><span data-stu-id="910ad-336">$PSVersionTable</span></span>

<span data-ttu-id="910ad-337">Enthält eine schreibgeschützte Hash Tabelle, in der Details zur PowerShell-Version angezeigt werden, die in der aktuellen Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-337">Contains a read-only hash table that displays details about the version of PowerShell that is running in the current session.</span></span> <span data-ttu-id="910ad-338">Die Tabelle enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="910ad-338">The table includes the following items:</span></span>

- <span data-ttu-id="910ad-339">**Psversion** : die PowerShell-Versionsnummer</span><span class="sxs-lookup"><span data-stu-id="910ad-339">**PSVersion** - The PowerShell version number</span></span>
- <span data-ttu-id="910ad-340">**Pabdition** : Diese Eigenschaft hat den Wert "Desktop" für PowerShell 4 und niedriger sowie PowerShell 5,1 in voll funktionsfähigen Windows-Editionen.</span><span class="sxs-lookup"><span data-stu-id="910ad-340">**PSEdition** - This property has the value of 'Desktop' for PowerShell 4 and below as well as PowerShell 5.1 on full-featured Windows editions.</span></span> <span data-ttu-id="910ad-341">Diese Eigenschaft hat den Wert "Core" für PowerShell 6 und höher sowie PowerShell PowerShell 5,1 auf Editionen mit eingeschränktem Speicherbedarf wie Windows Nano Server oder Windows IOT.</span><span class="sxs-lookup"><span data-stu-id="910ad-341">This property has the value of 'Core' for PowerShell 6 and above as well as PowerShell PowerShell 5.1 on reduced-footprint editions like Windows Nano Server or Windows IoT.</span></span>
- <span data-ttu-id="910ad-342">**Gitcomentschärd** : die Commit-ID der Quelldateien in GitHub</span><span class="sxs-lookup"><span data-stu-id="910ad-342">**GitCommitId** - The commit Id of the source files, in GitHub,</span></span>
- <span data-ttu-id="910ad-343">**Betriebssystem** : Beschreibung des Betriebssystems, auf dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-343">**OS** - Description of the operating system that PowerShell is running on.</span></span>
- <span data-ttu-id="910ad-344">**Platt Form** Plattform, auf der das Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-344">**Platform** - Platform that the operating system is running on.</span></span> <span data-ttu-id="910ad-345">Der Wert unter Linux und macOS ist **UNIX**.</span><span class="sxs-lookup"><span data-stu-id="910ad-345">The value on Linux and macOS is **Unix**.</span></span> <span data-ttu-id="910ad-346">Prüfen Sie `$IsMacOs` und `$IsLinux`.</span><span class="sxs-lookup"><span data-stu-id="910ad-346">See `$IsMacOs` and `$IsLinux`.</span></span>
- <span data-ttu-id="910ad-347">**Pscompatibleversions** : PowerShell-Versionen, die mit der aktuellen Version kompatibel sind</span><span class="sxs-lookup"><span data-stu-id="910ad-347">**PSCompatibleVersions** - Versions of PowerShell that are compatible with the current version</span></span>
- <span data-ttu-id="910ad-348">**Psremotingprotocolversion** : die Version des PowerShell-Remote Verwaltungs Protokolls.</span><span class="sxs-lookup"><span data-stu-id="910ad-348">**PSRemotingProtocolVersion** - The version of the PowerShell remote management protocol.</span></span>
- <span data-ttu-id="910ad-349">**SerializationVersion** : die Version der Serialisierungsmethode</span><span class="sxs-lookup"><span data-stu-id="910ad-349">**SerializationVersion** - The version of the serialization method</span></span>
- <span data-ttu-id="910ad-350">**Wsmanstackversion** : die Versionsnummer des WS-Management Stapels</span><span class="sxs-lookup"><span data-stu-id="910ad-350">**WSManStackVersion** - The version number of the WS-Management stack</span></span>

### <a name="pwd"></a><span data-ttu-id="910ad-351">$PWD</span><span class="sxs-lookup"><span data-stu-id="910ad-351">$PWD</span></span>

<span data-ttu-id="910ad-352">Enthält ein Pfad Objekt, das den vollständigen Pfad des aktuellen Verzeichnis Speicher Orts für den aktuellen PowerShell-Runspace darstellt.</span><span class="sxs-lookup"><span data-stu-id="910ad-352">Contains a path object that represents the full path of the current directory location for the current PowerShell runspace.</span></span>

> [!NOTE]
> <span data-ttu-id="910ad-353">PowerShell unterstützt mehrere Runspaces pro Prozess.</span><span class="sxs-lookup"><span data-stu-id="910ad-353">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="910ad-354">Jeder Runspace verfügt über ein eigenes _Aktuelles Verzeichnis_.</span><span class="sxs-lookup"><span data-stu-id="910ad-354">Each runspace has its own _current directory_.</span></span> <span data-ttu-id="910ad-355">Dies entspricht nicht dem aktuellen Verzeichnis des Prozesses: `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="910ad-355">This is not the same as the current directory of the process: `[System.Environment]::CurrentDirectory`.</span></span>

### <a name="sender"></a><span data-ttu-id="910ad-356">$Sender</span><span class="sxs-lookup"><span data-stu-id="910ad-356">$Sender</span></span>

<span data-ttu-id="910ad-357">Enthält das-Objekt, das dieses Ereignis generiert hat.</span><span class="sxs-lookup"><span data-stu-id="910ad-357">Contains the object that generated this event.</span></span> <span data-ttu-id="910ad-358">Diese Variable wird nur innerhalb des Aktions Blocks eines Ereignis Registrierungs Befehls aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="910ad-358">This variable is populated only within the Action block of an event registration command.</span></span> <span data-ttu-id="910ad-359">Der Wert dieser Variablen befindet sich auch in der Absender-Eigenschaft des **psiebargs** -Objekts, das `Get-Event` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="910ad-359">The value of this variable can also be found in the Sender property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="shellid"></a><span data-ttu-id="910ad-360">$ShellId</span><span class="sxs-lookup"><span data-stu-id="910ad-360">$ShellId</span></span>

<span data-ttu-id="910ad-361">Enthält den Bezeichner der aktuellen Shell.</span><span class="sxs-lookup"><span data-stu-id="910ad-361">Contains the identifier of the current shell.</span></span>

### <a name="stacktrace"></a><span data-ttu-id="910ad-362">$StackTrace</span><span class="sxs-lookup"><span data-stu-id="910ad-362">$StackTrace</span></span>

<span data-ttu-id="910ad-363">Enthält eine Stapel Überwachung für den letzten Fehler.</span><span class="sxs-lookup"><span data-stu-id="910ad-363">Contains a stack trace for the most recent error.</span></span>

### <a name="switch"></a><span data-ttu-id="910ad-364">$switch</span><span class="sxs-lookup"><span data-stu-id="910ad-364">$switch</span></span>

<span data-ttu-id="910ad-365">Enthält den Enumerator nicht die resultierenden Werte einer- `Switch` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="910ad-365">Contains the enumerator not the resulting values of a `Switch` statement.</span></span> <span data-ttu-id="910ad-366">Die `$switch` Variable ist nur vorhanden, während die `Switch` Anweisung ausgeführt wird. Sie wird gelöscht, wenn die `switch` Ausführung der Anweisung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="910ad-366">The `$switch` variable exists only while the `Switch` statement is running; it's deleted when the `switch` statement completes execution.</span></span> <span data-ttu-id="910ad-367">Weitere Informationen finden Sie unter [about_Switch](about_Switch.md).</span><span class="sxs-lookup"><span data-stu-id="910ad-367">For more information, see [about_Switch](about_Switch.md).</span></span>

<span data-ttu-id="910ad-368">Enumeratoren enthalten Eigenschaften und Methoden, mit denen Sie Schleifen Werte abrufen und die aktuelle Schleifen Iterationen ändern können.</span><span class="sxs-lookup"><span data-stu-id="910ad-368">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="910ad-369">Weitere Informationen finden Sie unter [Verwenden von Enumeratoren](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="910ad-369">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="this"></a><span data-ttu-id="910ad-370">$this</span><span class="sxs-lookup"><span data-stu-id="910ad-370">$this</span></span>

<span data-ttu-id="910ad-371">In einem Skriptblock, der eine Skript Eigenschaft oder Skript Methode definiert, `$this` verweist die Variable auf das Objekt, das erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-371">In a script block that defines a script property or script method, the `$this` variable refers to the object that is being extended.</span></span>

<span data-ttu-id="910ad-372">In einer benutzerdefinierten Klasse `$this` verweist die Variable auf das Klassenobjekt, das den Zugriff auf die in der-Klasse definierten Eigenschaften und Methoden zulässt.</span><span class="sxs-lookup"><span data-stu-id="910ad-372">In a custom class, the `$this` variable refers to the class object itself allowing access to properties and methods defined in the class.</span></span>

### <a name="true"></a><span data-ttu-id="910ad-373">$True</span><span class="sxs-lookup"><span data-stu-id="910ad-373">$true</span></span>

<span data-ttu-id="910ad-374">Enthält **true**.</span><span class="sxs-lookup"><span data-stu-id="910ad-374">Contains **True**.</span></span> <span data-ttu-id="910ad-375">Sie können diese Variable verwenden, um **true** in Befehlen und Skripts darzustellen.</span><span class="sxs-lookup"><span data-stu-id="910ad-375">You can use this variable to represent **True** in commands and scripts.</span></span>

## <a name="using-enumerators"></a><span data-ttu-id="910ad-376">Verwenden von Enumeratoren</span><span class="sxs-lookup"><span data-stu-id="910ad-376">Using Enumerators</span></span>

<span data-ttu-id="910ad-377">Die `$input` `$foreach` Variablen, und `$switch` sind alle Enumeratoren, die zum Durchlaufen der Werte verwendet werden, die durch ihren enthaltenden Codeblock verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="910ad-377">The `$input`, `$foreach`, and `$switch` variables are all enumerators used to iterate through the values processed by their containing code block.</span></span>

<span data-ttu-id="910ad-378">Ein Enumerator enthält Eigenschaften und Methoden, die Sie zum fortsetzen oder Zurücksetzen der Iterationen oder zum Abrufen von Iterations Werten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="910ad-378">An enumerator contains properties and methods you can use to advance or reset iteration, or retrieve iteration values.</span></span> <span data-ttu-id="910ad-379">Die direkte Bearbeitung von Enumeratoren gilt nicht als bewährte Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="910ad-379">Directly manipulating enumerators isn't considered best practice.</span></span>

- <span data-ttu-id="910ad-380">In Schleifen sollten die Fluss Steuerungs Schlüsselwörter unter [brechen](about_Break.md) und [fortfahren](about_Continue.md) bevorzugt werden.</span><span class="sxs-lookup"><span data-stu-id="910ad-380">Within loops, flow control keywords [break](about_Break.md) and [continue](about_Continue.md) should be preferred.</span></span>
- <span data-ttu-id="910ad-381">In Funktionen, die Pipeline Eingaben akzeptieren, empfiehlt es sich, Parameter mit den Attributen **valuefrompipeline** oder **valuefrompipelinebypropertyname** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="910ad-381">Within functions that accept pipeline input, it's best practice to use Parameters with the **ValueFromPipeline** or **ValueFromPipelineByPropertyName** attributes.</span></span>

  <span data-ttu-id="910ad-382">Weitere Informationen finden Sie unter [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="910ad-382">For more information, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="movenext"></a><span data-ttu-id="910ad-383">MoveNext</span><span class="sxs-lookup"><span data-stu-id="910ad-383">MoveNext</span></span>

<span data-ttu-id="910ad-384">Die [Methode "](/dotnet/api/system.collections.ienumerator.movenext) -Methode" verschiebt den Enumerator auf das nächste Element der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="910ad-384">The [MoveNext](/dotnet/api/system.collections.ienumerator.movenext) method advances the enumerator to the next element of the collection.</span></span> <span data-ttu-id="910ad-385">" **Muvenext** " gibt " **true** " zurück, wenn der Enumerator erfolgreich erweitert wurde, " **false** ", wenn der Enumerator das Ende der Auflistung überschritten hat.</span><span class="sxs-lookup"><span data-stu-id="910ad-385">**MoveNext** returns **True** if the enumerator was successfully advanced, **False** if the enumerator has passed the end of the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="910ad-386">Der **boolesche** Wert, der My **MoveNext** zurückgibt, wird an den Ausgabestream gesendet.</span><span class="sxs-lookup"><span data-stu-id="910ad-386">The **Boolean** value returned my **MoveNext** is sent to the output stream.</span></span>
> <span data-ttu-id="910ad-387">Sie können die Ausgabe unterdrücken, indem Sie Sie in Typecasting umwandeln `[void]` oder an [out-null](xref:Microsoft.PowerShell.Core.Out-Null)weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="910ad-387">You can suppress the output by typecasting it to `[void]` or piping it to [Out-Null](xref:Microsoft.PowerShell.Core.Out-Null).</span></span>
>
> ```powershell
> $input.MoveNext() | Out-Null
> ```
>
> ```powershell
> [void]$input.MoveNext()
> ```

### <a name="reset"></a><span data-ttu-id="910ad-388">Reset</span><span class="sxs-lookup"><span data-stu-id="910ad-388">Reset</span></span>

<span data-ttu-id="910ad-389">Die [Reset](/dotnet/api/system.collections.ienumerator.reset) -Methode legt den Enumerator auf seine anfängliche Position **vor** dem ersten Element in der Auflistung fest.</span><span class="sxs-lookup"><span data-stu-id="910ad-389">The [Reset](/dotnet/api/system.collections.ienumerator.reset) method sets the enumerator to its initial position, which is **before** the first element in the collection.</span></span>

### <a name="current"></a><span data-ttu-id="910ad-390">Aktuell</span><span class="sxs-lookup"><span data-stu-id="910ad-390">Current</span></span>

<span data-ttu-id="910ad-391">Die [Current](/dotnet/api/system.collections.ienumerator.current) -Eigenschaft ruft das-Element in der-Auflistung oder-Pipeline an der aktuellen Position des Enumerators ab.</span><span class="sxs-lookup"><span data-stu-id="910ad-391">The [Current](/dotnet/api/system.collections.ienumerator.current) property gets the element in the collection, or pipeline, at the current position of the enumerator.</span></span>

<span data-ttu-id="910ad-392">Die **aktuelle** -Eigenschaft gibt weiterhin dieselbe Eigenschaft zurück, **bis "** " "" ".</span><span class="sxs-lookup"><span data-stu-id="910ad-392">The **Current** property continues to return the same property until **MoveNext** is called.</span></span>

## <a name="examples"></a><span data-ttu-id="910ad-393">Beispiele</span><span class="sxs-lookup"><span data-stu-id="910ad-393">Examples</span></span>

### <a name="example-1-using-the-input-variable"></a><span data-ttu-id="910ad-394">Beispiel 1: Verwenden der $Input Variable</span><span class="sxs-lookup"><span data-stu-id="910ad-394">Example 1: Using the $input variable</span></span>

<span data-ttu-id="910ad-395">Im folgenden Beispiel löscht der Zugriff auf die- `$input` Variable die-Variable, bis der Prozess Block das nächste Mal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-395">In the following example, accessing the `$input` variable clears the variable until the next time the process block executes.</span></span> <span data-ttu-id="910ad-396">Bei Verwendung der **Reset** -Methode wird die `$input` Variable auf den aktuellen Pipeline Wert zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="910ad-396">Using the **Reset** method resets the `$input` variable to the current pipeline value.</span></span>

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

<span data-ttu-id="910ad-397">Der Prozess Block setzt die Variable automatisch fort, `$input` auch wenn Sie nicht darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="910ad-397">The process block automatically advances the `$input` variable even if you don't access it.</span></span>

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

### <a name="example-2-using-input-outside-the-process-block"></a><span data-ttu-id="910ad-398">Beispiel 2: Verwenden von $Input außerhalb des Prozess Blocks</span><span class="sxs-lookup"><span data-stu-id="910ad-398">Example 2: Using $input outside the process block</span></span>

<span data-ttu-id="910ad-399">Außerhalb des Prozess Blocks stellt die `$input` Variable alle Werte dar, die an die Funktion weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="910ad-399">Outside of the process block the `$input` variable represents all the values piped into the function.</span></span>

- <span data-ttu-id="910ad-400">Durch den Zugriff auf die `$input` Variable werden alle Werte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="910ad-400">Accessing the `$input` variable clears all values.</span></span>
- <span data-ttu-id="910ad-401">Die **Reset** -Methode setzt die gesamte Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="910ad-401">The **Reset** method resets the entire collection.</span></span>
- <span data-ttu-id="910ad-402">Die **aktuelle** Eigenschaft wird nie aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="910ad-402">The **Current** property is never populated.</span></span>
- <span data-ttu-id="910ad-403">Die Methode " **ivenext** " gibt false zurück, da die Auflistung nicht erweitert werden kann.</span><span class="sxs-lookup"><span data-stu-id="910ad-403">The **MoveNext** method returns false because the collection can't be advanced.</span></span>
  - <span data-ttu-id="910ad-404">Durch **Aufrufen von** "" wird die `$input` Variable gelöscht.</span><span class="sxs-lookup"><span data-stu-id="910ad-404">Calling **MoveNext** clears out the `$input` variable.</span></span>

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

### <a name="example-3-using-the-inputcurrent-property"></a><span data-ttu-id="910ad-405">Beispiel 3: Verwenden der $Input. Current-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="910ad-405">Example 3: Using the $input.Current property</span></span>

<span data-ttu-id="910ad-406">Mithilfe der **aktuellen** Eigenschaft kann auf den aktuellen Pipeline Wert mehrmals zugegriffen werden, ohne dass die **Reset** -Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-406">By using the **Current** property, the current pipeline value can be accessed multiple times without using the **Reset** method.</span></span> <span data-ttu-id="910ad-407">Der Prozess Block ruft nicht automatisch die **Methode "** Methode" auf.</span><span class="sxs-lookup"><span data-stu-id="910ad-407">The process block doesn't automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="910ad-408">Die **aktuelle** Eigenschaft wird nie aufgefüllt, es sei denn, **Sie nennen nicht** explizit "".</span><span class="sxs-lookup"><span data-stu-id="910ad-408">The **Current** property will never be populated unless you explicitly call **MoveNext**.</span></span> <span data-ttu-id="910ad-409">Der Zugriff auf die **aktuelle** Eigenschaft kann mehrmals innerhalb des Prozess Blocks erfolgen, ohne den Wert zu löschen.</span><span class="sxs-lookup"><span data-stu-id="910ad-409">The **Current** property can be accessed multiple times inside the process block without clearing its value.</span></span>

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

### <a name="example-4-using-the-foreach-variable"></a><span data-ttu-id="910ad-410">Beispiel 4: Verwenden der $foreach Variable</span><span class="sxs-lookup"><span data-stu-id="910ad-410">Example 4: Using the $foreach variable</span></span>

<span data-ttu-id="910ad-411">Anders als die- `$input` Variable `$foreach` stellt die-Variable immer alle Elemente in der Auflistung dar, wenn direkt darauf zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-411">Unlike the `$input` variable, the `$foreach` variable always represents all items in the collection when accessed directly.</span></span> <span data-ttu-id="910ad-412">Verwenden Sie die **aktuelle** -Eigenschaft, um auf das aktuelle Auflistungs Element zuzugreifen **, und die** **Reset** -Methode und die-Methode, um den Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="910ad-412">Use the **Current** property to access the current collection element, and the **Reset** and **MoveNext** methods to change its value.</span></span>

> [!NOTE]
> <span data-ttu-id="910ad-413">Jede Iterations `foreach` Schleife ruft automatisch die Methode " **ivenext** " auf.</span><span class="sxs-lookup"><span data-stu-id="910ad-413">Each iteration of the `foreach` loop will automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="910ad-414">Die folgende-Schleife wird nur zweimal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="910ad-414">The following loop only executes twice.</span></span> <span data-ttu-id="910ad-415">In der zweiten Iterationen wird die Auflistung vor Abschluss der Iterationen auf das dritte Element verschoben.</span><span class="sxs-lookup"><span data-stu-id="910ad-415">In the second iteration, the collection is moved to the third element before the iteration is complete.</span></span> <span data-ttu-id="910ad-416">Nach der zweiten Iterations Zeit sind nun keine weiteren Werte zum Durchlaufen vorhanden, und die Schleife wird beendet.</span><span class="sxs-lookup"><span data-stu-id="910ad-416">After the second iteration, there are now no more values to iterate, and the loop terminates.</span></span>

<span data-ttu-id="910ad-417">Die Eigenschaft " **ivenext** " wirkt sich nicht auf die Variable aus, die zum Durchlaufen der Auflistung ausgewählt wurde ( `$Num` ).</span><span class="sxs-lookup"><span data-stu-id="910ad-417">The **MoveNext** property doesn't affect the variable chosen to iterate through the collection (`$Num`).</span></span>

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

<span data-ttu-id="910ad-418">Bei Verwendung der Reset-Methode wird das aktuelle Element in der Auflistung zurück **gesetzt** .</span><span class="sxs-lookup"><span data-stu-id="910ad-418">Using the **Reset** method resets the current element in the collection.</span></span> <span data-ttu-id="910ad-419">Im folgenden Beispiel werden die ersten beiden Elemente **zweimal** durchlaufen, da die **Reset** -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="910ad-419">The following example loops through the first two elements **twice** because the **Reset** method is called.</span></span> <span data-ttu-id="910ad-420">Nach den ersten beiden Schleifen schlägt die `if` Anweisung fehl, und die Schleife durchläuft alle drei Elemente in der Regel.</span><span class="sxs-lookup"><span data-stu-id="910ad-420">After the first two loops, the `if` statement fails and the loop iterates through all three elements normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="910ad-421">Dies kann zu einer Endlosschleife führen.</span><span class="sxs-lookup"><span data-stu-id="910ad-421">This could result in an infinite loop.</span></span>

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

### <a name="example-5-using-the-switch-variable"></a><span data-ttu-id="910ad-422">Beispiel 5: Verwenden der $Switch Variable</span><span class="sxs-lookup"><span data-stu-id="910ad-422">Example 5: Using the $switch variable</span></span>

<span data-ttu-id="910ad-423">Die `$switch` Variable verfügt über die exakt gleichen Regeln wie die `$foreach` Variable.</span><span class="sxs-lookup"><span data-stu-id="910ad-423">The `$switch` variable has the exact same rules as the `$foreach` variable.</span></span>
<span data-ttu-id="910ad-424">Im folgenden Beispiel werden alle enumeratorkonzepte veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="910ad-424">The following example demonstrates all the enumerator concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="910ad-425">Beachten Sie, dass der **notevaluated** -Fall nie ausgeführt wird, auch wenn es keine- `break`  Anweisung nach der-Methode von "-Methode" gibt.</span><span class="sxs-lookup"><span data-stu-id="910ad-425">Note how the **NotEvaluated** case is never executed, even though there's no `break` statement after the **MoveNext** method.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="910ad-426">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="910ad-426">See also</span></span>

[<span data-ttu-id="910ad-427">about_Functions</span><span class="sxs-lookup"><span data-stu-id="910ad-427">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="910ad-428">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="910ad-428">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="910ad-429">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="910ad-429">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="910ad-430">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="910ad-430">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="910ad-431">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="910ad-431">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="910ad-432">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="910ad-432">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="910ad-433">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="910ad-433">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="910ad-434">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="910ad-434">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="910ad-435">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="910ad-435">about_Splatting</span></span>](about_Splatting.md)

[<span data-ttu-id="910ad-436">about_Variables</span><span class="sxs-lookup"><span data-stu-id="910ad-436">about_Variables</span></span>](about_Variables.md)

