---
description: Beschreibt, wie die `Try` -, `Catch` -und-Blöcke verwendet werden, `Finally` um abschließende Fehler zu behandeln.
Locale: en-US
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_try_catch_finally?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Try_Catch_Finally
ms.openlocfilehash: c93fa69e3badd7777950a850dfe81b79f9197f68
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595538"
---
# <a name="about-try-catch-finally"></a><span data-ttu-id="14dfd-103">Informationen zu try catch schließlich</span><span class="sxs-lookup"><span data-stu-id="14dfd-103">About Try Catch Finally</span></span>

## <a name="short-description"></a><span data-ttu-id="14dfd-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="14dfd-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="14dfd-105">Beschreibt, wie die `Try` -, `Catch` -und-Blöcke verwendet werden, `Finally` um abschließende Fehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="14dfd-105">Describes how to use the `Try`, `Catch`, and `Finally` blocks to handle terminating errors.</span></span>

## <a name="long-description"></a><span data-ttu-id="14dfd-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="14dfd-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="14dfd-107">Verwenden `Try` `Catch` `Finally` Sie die Blöcke, und, um auf abschließende Fehler in Skripts zu reagieren oder diese zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="14dfd-107">Use `Try`, `Catch`, and `Finally` blocks to respond to or handle terminating errors in scripts.</span></span> <span data-ttu-id="14dfd-108">Die- `Trap` Anweisung kann auch verwendet werden, um abschließende Fehler in Skripts zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="14dfd-108">The `Trap` statement can also be used to handle terminating errors in scripts.</span></span> <span data-ttu-id="14dfd-109">Weitere Informationen finden Sie unter [about_Trap](about_Trap.md).</span><span class="sxs-lookup"><span data-stu-id="14dfd-109">For more information, see [about_Trap](about_Trap.md).</span></span>

<span data-ttu-id="14dfd-110">Ein Beendigungs Fehler beendet die Ausführung einer-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="14dfd-110">A terminating error stops a statement from running.</span></span> <span data-ttu-id="14dfd-111">Wenn PowerShell einen Fehler mit Abbruch nicht in irgendeiner Weise behandelt, beendet PowerShell auch das Ausführen der Funktion oder des Skripts mithilfe der aktuellen Pipeline.</span><span class="sxs-lookup"><span data-stu-id="14dfd-111">If PowerShell does not handle a terminating error in some way, PowerShell also stops running the function or script using the current pipeline.</span></span> <span data-ttu-id="14dfd-112">In anderen Sprachen, wie z \# . b. C, werden abschließende Fehler als Ausnahmen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="14dfd-112">In other languages, such as C\#, terminating errors are referred to as exceptions.</span></span>

<span data-ttu-id="14dfd-113">Verwenden Sie den- `Try` Block, um einen Abschnitt eines Skripts zu definieren, in dem PowerShell auf Fehler überwachen soll.</span><span class="sxs-lookup"><span data-stu-id="14dfd-113">Use the `Try` block to define a section of a script in which you want PowerShell to monitor for errors.</span></span> <span data-ttu-id="14dfd-114">Wenn ein Fehler im- `Try` Block auftritt, wird der Fehler zuerst in der `$Error` automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="14dfd-114">When an error occurs within the `Try` block, the error is first saved to the `$Error` automatic variable.</span></span> <span data-ttu-id="14dfd-115">PowerShell sucht dann nach einem- `Catch` Block, um den Fehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="14dfd-115">PowerShell then searches for a `Catch` block to handle the error.</span></span> <span data-ttu-id="14dfd-116">Wenn die `Try` Anweisung über keinen übereinstimmenden `Catch` Block verfügt, sucht PowerShell weiterhin nach einem entsprechenden `Catch` Block oder einer entsprechenden `Trap` Anweisung in den übergeordneten Bereichen.</span><span class="sxs-lookup"><span data-stu-id="14dfd-116">If the `Try` statement does not have a matching `Catch` block, PowerShell continues to search for an appropriate `Catch` block or `Trap` statement in the parent scopes.</span></span> <span data-ttu-id="14dfd-117">Wenn ein- `Catch` Block abgeschlossen ist, oder wenn kein entsprechender `Catch` Block oder keine entsprechende `Trap` Anweisung gefunden wird, wird der- `Finally` Block ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="14dfd-117">After a `Catch` block is completed or if no appropriate `Catch` block or `Trap` statement is found, the `Finally` block is run.</span></span> <span data-ttu-id="14dfd-118">Wenn der Fehler nicht behandelt werden kann, wird der Fehler in den Fehler Datenstrom geschrieben.</span><span class="sxs-lookup"><span data-stu-id="14dfd-118">If the error cannot be handled, the error is written to the error stream.</span></span>

<span data-ttu-id="14dfd-119">Ein- `Catch` Block kann Befehle zum Nachverfolgen des Fehlers oder zum Wiederherstellen des erwarteten Ablaufs des Skripts enthalten.</span><span class="sxs-lookup"><span data-stu-id="14dfd-119">A `Catch` block can include commands for tracking the error or for recovering the expected flow of the script.</span></span> <span data-ttu-id="14dfd-120">Ein- `Catch` Block kann angeben, welche Fehlertypen abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="14dfd-120">A `Catch` block can specify which error types it catches.</span></span> <span data-ttu-id="14dfd-121">Eine- `Try` Anweisung kann mehrere `Catch` Blöcke für verschiedene Arten von Fehlern enthalten.</span><span class="sxs-lookup"><span data-stu-id="14dfd-121">A `Try` statement can include multiple `Catch` blocks for different kinds of errors.</span></span>

<span data-ttu-id="14dfd-122">Ein- `Finally` Block kann verwendet werden, um alle Ressourcen freizugeben, die von Ihrem Skript nicht mehr benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="14dfd-122">A `Finally` block can be used to free any resources that are no longer needed by your script.</span></span>

<span data-ttu-id="14dfd-123">`Try`, und `Catch` `Finally` ähneln den `Try` Schlüsselwörtern, und, die `Catch` `Finally` in der Programmiersprache C verwendet werden \# .</span><span class="sxs-lookup"><span data-stu-id="14dfd-123">`Try`, `Catch`, and `Finally` resemble the `Try`, `Catch`, and `Finally` keywords used in the C\# programming language.</span></span>

### <a name="syntax"></a><span data-ttu-id="14dfd-124">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="14dfd-124">SYNTAX</span></span>

<span data-ttu-id="14dfd-125">Eine- `Try` Anweisung enthält einen `Try` Block, 0 (null) oder mehr `Catch` Blöcke und keinen oder einen `Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="14dfd-125">A `Try` statement contains a `Try` block, zero or more `Catch` blocks, and zero or one `Finally` block.</span></span> <span data-ttu-id="14dfd-126">Eine- `Try` Anweisung muss über mindestens einen `Catch` Block oder einen `Finally` Block verfügen.</span><span class="sxs-lookup"><span data-stu-id="14dfd-126">A `Try` statement must have at least one `Catch` block or one `Finally` block.</span></span>

<span data-ttu-id="14dfd-127">Das folgende Beispiel zeigt die `Try` Block Syntax:</span><span class="sxs-lookup"><span data-stu-id="14dfd-127">The following shows the `Try` block syntax:</span></span>

```powershell
try {<statement list>}
```

<span data-ttu-id="14dfd-128">`Try`Auf das Schlüsselwort folgt eine Anweisungs Liste in geschweiften Klammern.</span><span class="sxs-lookup"><span data-stu-id="14dfd-128">The `Try` keyword is followed by a statement list in braces.</span></span> <span data-ttu-id="14dfd-129">Wenn ein Abbruch Fehler auftritt, während die Anweisungen in der Anweisungs Liste ausgeführt werden, übergibt das Skript das Fehler Objekt aus dem- `Try` Block an einen entsprechenden- `Catch` Block.</span><span class="sxs-lookup"><span data-stu-id="14dfd-129">If a terminating error occurs while the statements in the statement list are being run, the script passes the error object from the `Try` block to an appropriate `Catch` block.</span></span>

<span data-ttu-id="14dfd-130">Das folgende Beispiel zeigt die `Catch` Block Syntax:</span><span class="sxs-lookup"><span data-stu-id="14dfd-130">The following shows the `Catch` block syntax:</span></span>

```powershell
catch [[<error type>][',' <error type>]*] {<statement list>}
```

<span data-ttu-id="14dfd-131">Fehlertypen werden in eckigen Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14dfd-131">Error types appear in brackets.</span></span> <span data-ttu-id="14dfd-132">Die äußersten Klammern geben an, dass das Element optional ist.</span><span class="sxs-lookup"><span data-stu-id="14dfd-132">The outermost brackets indicate the element is optional.</span></span>

<span data-ttu-id="14dfd-133">Auf das `Catch` Schlüsselwort folgt eine optionale Liste der Fehlertyp Spezifikationen und eine Anweisungs Liste.</span><span class="sxs-lookup"><span data-stu-id="14dfd-133">The `Catch` keyword is followed by an optional list of error type specifications and a statement list.</span></span> <span data-ttu-id="14dfd-134">Wenn im-Block ein Abbruch Fehler auftritt `Try` , sucht PowerShell nach einem entsprechenden- `Catch` Block.</span><span class="sxs-lookup"><span data-stu-id="14dfd-134">If a terminating error occurs in the `Try` block, PowerShell searches for an appropriate `Catch` block.</span></span> <span data-ttu-id="14dfd-135">Wenn ein solcher gefunden wird, werden die Anweisungen im- `Catch` Block ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="14dfd-135">If one is found, the statements in the `Catch` block are executed.</span></span>

<span data-ttu-id="14dfd-136">Der- `Catch` Block kann einen oder mehrere Fehlertypen angeben.</span><span class="sxs-lookup"><span data-stu-id="14dfd-136">The `Catch` block can specify one or more error types.</span></span> <span data-ttu-id="14dfd-137">Ein Fehlertyp ist eine Microsoft .NET Framework-Ausnahme oder eine Ausnahme, die von einer .NET Framework Ausnahme abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="14dfd-137">An error type is a Microsoft .NET Framework exception or an exception that is derived from a .NET Framework exception.</span></span> <span data-ttu-id="14dfd-138">Ein- `Catch` Block verarbeitet Fehler der angegebenen .NET Framework Ausnahme Klasse oder einer beliebigen Klasse, die von der angegebenen Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="14dfd-138">A `Catch` block handles errors of the specified .NET Framework exception class or of any class that derives from the specified class.</span></span>

<span data-ttu-id="14dfd-139">Wenn ein- `Catch` Block einen Fehlertyp angibt, `Catch` verarbeitet dieser Block diese Art von Fehler.</span><span class="sxs-lookup"><span data-stu-id="14dfd-139">If a `Catch` block specifies an error type, that `Catch` block handles that type of error.</span></span> <span data-ttu-id="14dfd-140">Wenn ein- `Catch` Block keinen Fehlertyp angibt, behandelt dieser `Catch` Block jeden im-Block gefundenen Fehler `Try` .</span><span class="sxs-lookup"><span data-stu-id="14dfd-140">If a `Catch` block does not specify an error type, that `Catch` block handles any error encountered in the `Try` block.</span></span> <span data-ttu-id="14dfd-141">Eine- `Try` Anweisung kann mehrere `Catch` Blöcke für die unterschiedlichen angegebenen Fehlertypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="14dfd-141">A `Try` statement can include multiple `Catch` blocks for the different specified error types.</span></span>

<span data-ttu-id="14dfd-142">Das folgende Beispiel zeigt die `Finally` Block Syntax:</span><span class="sxs-lookup"><span data-stu-id="14dfd-142">The following shows the `Finally` block syntax:</span></span>

```powershell
finally {<statement list>}
```

<span data-ttu-id="14dfd-143">`Finally`Auf das Schlüsselwort folgt eine Anweisungs Liste, die jedes Mal ausgeführt wird, wenn das Skript ausgeführt wird, auch wenn die `Try` Anweisung fehlerfrei ausgeführt wurde oder ein Fehler in einer Anweisung abgefangen wurde `Catch` .</span><span class="sxs-lookup"><span data-stu-id="14dfd-143">The `Finally` keyword is followed by a statement list that runs every time the script is run, even if the `Try` statement ran without error or an error was caught in a `Catch` statement.</span></span>

<span data-ttu-id="14dfd-144">Beachten Sie, dass durch Drücken von <kbd>STRG</kbd> + <kbd>C</kbd> die Pipeline beendet wird.</span><span class="sxs-lookup"><span data-stu-id="14dfd-144">Note that pressing <kbd>CTRL</kbd>+<kbd>C</kbd> stops the pipeline.</span></span> <span data-ttu-id="14dfd-145">Objekte, die an die Pipeline gesendet werden, werden nicht als Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14dfd-145">Objects that are sent to the pipeline will not be displayed as output.</span></span> <span data-ttu-id="14dfd-146">Wenn Sie also eine anzuzeigende Anweisung einschließen, z. b. "der letzte Block wurde ausgeführt", wird Sie nicht angezeigt, nachdem Sie <kbd>STRG</kbd> + <kbd>C</kbd>gedrückt haben, auch wenn der Block ausgeführt wurde `Finally` .</span><span class="sxs-lookup"><span data-stu-id="14dfd-146">Therefore, if you include a statement to be displayed, such as "Finally block has run", it will not be displayed after you press <kbd>CTRL</kbd>+<kbd>C</kbd>, even if the `Finally` block ran.</span></span>

### <a name="catching-errors"></a><span data-ttu-id="14dfd-147">Abfangen von Fehlern</span><span class="sxs-lookup"><span data-stu-id="14dfd-147">CATCHING ERRORS</span></span>

<span data-ttu-id="14dfd-148">Das folgende Beispielskript zeigt einen `Try` Block mit einem- `Catch` Block:</span><span class="sxs-lookup"><span data-stu-id="14dfd-148">The following sample script shows a `Try` block with a `Catch` block:</span></span>

```powershell
try { NonsenseString }
catch { "An error occurred." }
```

<span data-ttu-id="14dfd-149">Das `Catch` Schlüsselwort muss direkt auf den `Try` Block oder einen anderen `Catch` Block folgen.</span><span class="sxs-lookup"><span data-stu-id="14dfd-149">The `Catch` keyword must immediately follow the `Try` block or another `Catch` block.</span></span>

<span data-ttu-id="14dfd-150">PowerShell erkennt nicht "nonsenabstring" als Cmdlet oder ein anderes Element.</span><span class="sxs-lookup"><span data-stu-id="14dfd-150">PowerShell does not recognize "NonsenseString" as a cmdlet or other item.</span></span>
<span data-ttu-id="14dfd-151">Durch das Ausführen dieses Skripts wird folgendes Ergebnis zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="14dfd-151">Running this script returns the following result:</span></span>

```powershell
An error occurred.
```

<span data-ttu-id="14dfd-152">Wenn im Skript "nonsenenstring" auftritt, wird ein Abbruch Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="14dfd-152">When the script encounters "NonsenseString", it causes a terminating error.</span></span> <span data-ttu-id="14dfd-153">Der- `Catch` Block verarbeitet den Fehler, indem die-Anweisungs Liste im-Block ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="14dfd-153">The `Catch` block handles the error by running the statement list inside the block.</span></span>

### <a name="using-multiple-catch-statements"></a><span data-ttu-id="14dfd-154">Verwenden von mehreren catch-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="14dfd-154">USING MULTIPLE CATCH STATEMENTS</span></span>

<span data-ttu-id="14dfd-155">Eine- `Try` Anweisung kann eine beliebige Anzahl von `Catch` Blöcken aufweisen.</span><span class="sxs-lookup"><span data-stu-id="14dfd-155">A `Try` statement can have any number of `Catch` blocks.</span></span> <span data-ttu-id="14dfd-156">Das folgende Skript enthält z. b. einen Block, der `Try` herunterlädt `MyDoc.doc` und zwei `Catch` Blöcke enthält:</span><span class="sxs-lookup"><span data-stu-id="14dfd-156">For example, the following script has a `Try` block that downloads `MyDoc.doc`, and it contains two `Catch` blocks:</span></span>

```powershell
try {
   $wc = new-object System.Net.WebClient
   $wc.DownloadFile("http://www.contoso.com/MyDoc.doc","c:\temp\MyDoc.doc")
}
catch [System.Net.WebException],[System.IO.IOException] {
    "Unable to download MyDoc.doc from http://www.contoso.com."
}
catch {
    "An error occurred that could not be resolved."
}

```

<span data-ttu-id="14dfd-157">Der erste `Catch` Block verarbeitet Fehler des **System .net. WebException** -und des **System. IO. IOException** -Typs.</span><span class="sxs-lookup"><span data-stu-id="14dfd-157">The first `Catch` block handles errors of the **System.Net.WebException** and **System.IO.IOException** types.</span></span> <span data-ttu-id="14dfd-158">Der zweite- `Catch` Block gibt keinen Fehlertyp an.</span><span class="sxs-lookup"><span data-stu-id="14dfd-158">The second `Catch` block does not specify an error type.</span></span> <span data-ttu-id="14dfd-159">Der zweite- `Catch` Block behandelt alle anderen auftretenden Abbruch Fehler.</span><span class="sxs-lookup"><span data-stu-id="14dfd-159">The second `Catch` block handles any other terminating errors that occur.</span></span>

<span data-ttu-id="14dfd-160">PowerShell gleicht Fehlertypen nach Vererbung ab.</span><span class="sxs-lookup"><span data-stu-id="14dfd-160">PowerShell matches error types by inheritance.</span></span> <span data-ttu-id="14dfd-161">Ein- `Catch` Block verarbeitet Fehler der angegebenen .NET Framework Ausnahme Klasse oder einer beliebigen Klasse, die von der angegebenen Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="14dfd-161">A `Catch` block handles errors of the specified .NET Framework exception class or of any class that derives from the specified class.</span></span> <span data-ttu-id="14dfd-162">Das folgende Beispiel enthält einen- `Catch` Block, der den Fehler "Befehl wurde nicht gefunden" abfängt:</span><span class="sxs-lookup"><span data-stu-id="14dfd-162">The following example contains a `Catch` block that catches a "Command Not Found" error:</span></span>

```powershell
catch [System.Management.Automation.CommandNotFoundException]
{"Inherited Exception" }
```

<span data-ttu-id="14dfd-163">Der angegebene Fehlertyp **commandnotfoundexception** erbt vom **System.Systemexception** -Typ.</span><span class="sxs-lookup"><span data-stu-id="14dfd-163">The specified error type, **CommandNotFoundException**, inherits from the **System.SystemException** type.</span></span> <span data-ttu-id="14dfd-164">Im folgenden Beispiel wird auch der Fehler "Befehl nicht gefunden" abgefangen:</span><span class="sxs-lookup"><span data-stu-id="14dfd-164">The following example also catches a Command Not Found error:</span></span>

```powershell
catch [System.SystemException] {"Base Exception" }
```

<span data-ttu-id="14dfd-165">Dieser `Catch` Block behandelt den Fehler "Befehl nicht gefunden" und andere Fehler, die vom Typ **"SystemException** " erben.</span><span class="sxs-lookup"><span data-stu-id="14dfd-165">This `Catch` block handles the "Command Not Found" error and other errors that inherit from the **SystemException** type.</span></span>

<span data-ttu-id="14dfd-166">Wenn Sie eine Fehler Klasse und eine der abgeleiteten Klassen angeben, platzieren Sie den- `Catch` Block für die abgeleitete Klasse vor dem- `Catch` Block für die allgemeine-Klasse.</span><span class="sxs-lookup"><span data-stu-id="14dfd-166">If you specify an error class and one of its derived classes, place the `Catch` block for the derived class before the `Catch` block for the general class.</span></span>

### <a name="using-traps-in-a-try-catch"></a><span data-ttu-id="14dfd-167">Verwenden von Traps in einem try-catch</span><span class="sxs-lookup"><span data-stu-id="14dfd-167">Using Traps in a Try Catch</span></span>

<span data-ttu-id="14dfd-168">Wenn ein Beendigungs Fehler in einem- `Try` Block auftritt `Trap` , der ein-Element im-Block definiert ist, `Try` `Catch` übernimmt die-Anweisung die-Anweisung, selbst wenn ein entsprechender-Block vorhanden ist `Trap` .</span><span class="sxs-lookup"><span data-stu-id="14dfd-168">When a terminating error occurs in a `Try` block with a `Trap` defined within the `Try` block, even if there is a matching `Catch` block, the `Trap` statement takes control.</span></span>

<span data-ttu-id="14dfd-169">Wenn ein `Trap` in einem höheren Block als vorhanden `Try` ist und es keinen übereinstimmenden `Catch` Block innerhalb des aktuellen Gültigkeits Bereichs gibt, `Trap` übernimmt auch dann die Steuerung, wenn ein übergeordneter Bereich über einen übereinstimmenden `Catch` Block verfügt.</span><span class="sxs-lookup"><span data-stu-id="14dfd-169">If a `Trap` exists at a higher block than the `Try`, and there is no matching `Catch` block within the current scope, the `Trap` will take control, even if any parent scope has a matching `Catch` block.</span></span>

### <a name="accessing-exception-information"></a><span data-ttu-id="14dfd-170">Zugreifen auf Ausnahme Informationen</span><span class="sxs-lookup"><span data-stu-id="14dfd-170">ACCESSING EXCEPTION INFORMATION</span></span>

<span data-ttu-id="14dfd-171">Innerhalb eines- `Catch` Blocks kann auf den aktuellen Fehler mithilfe von zugegriffen werden `$_` . Dies wird auch als bezeichnet `$PSItem` .</span><span class="sxs-lookup"><span data-stu-id="14dfd-171">Within a `Catch` block, the current error can be accessed using `$_`, which is also known as `$PSItem`.</span></span> <span data-ttu-id="14dfd-172">Das Objekt ist vom Typ **ErrorRecord**.</span><span class="sxs-lookup"><span data-stu-id="14dfd-172">The object is of type **ErrorRecord**.</span></span>

```powershell
try { NonsenseString }
catch {
  Write-Host "An error occurred:"
  Write-Host $_
}
```

<span data-ttu-id="14dfd-173">Durch das Ausführen dieses Skripts wird folgendes Ergebnis zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="14dfd-173">Running this script returns the following result:</span></span>

```Output
An Error occurred:
The term 'NonsenseString' is not recognized as the name of a cmdlet, function,
script file, or operable program. Check the spelling of the name, or if a path
was included, verify that the path is correct and try again.
```

<span data-ttu-id="14dfd-174">Es gibt weitere Eigenschaften, auf die zugegriffen werden kann, z. **b. scriptstacktrace**, **Exception** und **errorDetails**.</span><span class="sxs-lookup"><span data-stu-id="14dfd-174">There are additional properties that can be accessed, such as **ScriptStackTrace**, **Exception**, and **ErrorDetails**.</span></span>  <span data-ttu-id="14dfd-175">Angenommen, das Skript wird wie folgt geändert:</span><span class="sxs-lookup"><span data-stu-id="14dfd-175">For example, if we change the script to the following:</span></span>

```powershell
try { NonsenseString }
catch {
  Write-Host "An error occurred:"
  Write-Host $_.ScriptStackTrace
}
```

<span data-ttu-id="14dfd-176">Das Ergebnis sieht in etwa wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="14dfd-176">The result will be similar to:</span></span>

```
An Error occurred:
at <ScriptBlock>, <No file>: line 2
```

### <a name="freeing-resources-by-using-finally"></a><span data-ttu-id="14dfd-177">Freigeben von Ressourcen mithilfe von</span><span class="sxs-lookup"><span data-stu-id="14dfd-177">FREEING RESOURCES BY USING FINALLY</span></span>

<span data-ttu-id="14dfd-178">Um von einem Skript verwendete Ressourcen freizugeben, fügen Sie `Finally` nach den `Try` -und-Blöcken einen-Block hinzu `Catch` .</span><span class="sxs-lookup"><span data-stu-id="14dfd-178">To free resources used by a script, add a `Finally` block after the `Try` and `Catch` blocks.</span></span> <span data-ttu-id="14dfd-179">Die `Finally` Block-Anweisungen werden unabhängig davon ausgeführt, ob der-Block einen Beendigungs Fehler feststellt `Try` .</span><span class="sxs-lookup"><span data-stu-id="14dfd-179">The `Finally` block statements run regardless of whether the `Try` block encounters a terminating error.</span></span> <span data-ttu-id="14dfd-180">PowerShell führt den `Finally` Block aus, bevor das Skript beendet wird, oder bevor der aktuelle Block den Gültigkeitsbereich verlässt.</span><span class="sxs-lookup"><span data-stu-id="14dfd-180">PowerShell runs the `Finally` block before the script terminates or before the current block goes out of scope.</span></span>

<span data-ttu-id="14dfd-181">Ein- `Finally` Block wird auch dann ausgeführt, wenn Sie <kbd>STRG</kbd> + <kbd>C</kbd> zum Abbrechen des Skripts verwenden.</span><span class="sxs-lookup"><span data-stu-id="14dfd-181">A `Finally` block runs even if you use <kbd>CTRL</kbd>+<kbd>C</kbd> to stop the script.</span></span> <span data-ttu-id="14dfd-182">Ein- `Finally` Block wird auch ausgeführt, wenn ein Exit-Schlüsselwort das Skript innerhalb eines- `Catch` Blocks beendet.</span><span class="sxs-lookup"><span data-stu-id="14dfd-182">A `Finally` block also runs if an Exit keyword stops the script from within a `Catch` block.</span></span>

### <a name="see-also"></a><span data-ttu-id="14dfd-183">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="14dfd-183">SEE ALSO</span></span>

[<span data-ttu-id="14dfd-184">about_Break</span><span class="sxs-lookup"><span data-stu-id="14dfd-184">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="14dfd-185">about_Continue</span><span class="sxs-lookup"><span data-stu-id="14dfd-185">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="14dfd-186">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="14dfd-186">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="14dfd-187">about_Throw</span><span class="sxs-lookup"><span data-stu-id="14dfd-187">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="14dfd-188">about_Trap</span><span class="sxs-lookup"><span data-stu-id="14dfd-188">about_Trap</span></span>](about_Trap.md)

