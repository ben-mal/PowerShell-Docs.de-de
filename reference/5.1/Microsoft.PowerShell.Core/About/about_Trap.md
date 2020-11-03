---
description: Beschreibt ein Schlüsselwort, das einen Abbruch Fehler behandelt.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_trap?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Trap
ms.openlocfilehash: 9627c632769cb87e790cc421c09d1103b90acf1d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222471"
---
# <a name="about-trap"></a><span data-ttu-id="ed300-104">Informationen zu Trap</span><span class="sxs-lookup"><span data-stu-id="ed300-104">About Trap</span></span>

## <a name="short-description"></a><span data-ttu-id="ed300-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed300-105">Short description</span></span>

<span data-ttu-id="ed300-106">Beschreibt ein Schlüsselwort, das einen Abbruch Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="ed300-106">Describes a keyword that handles a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="ed300-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed300-107">Long description</span></span>

<span data-ttu-id="ed300-108">Ein Beendigungs Fehler beendet die Ausführung einer-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ed300-108">A terminating error stops a statement from running.</span></span> <span data-ttu-id="ed300-109">Wenn PowerShell einen abschließenden Fehler nicht in irgendeiner Weise behandelt, beendet PowerShell auch die Ausführung der Funktion oder des Skripts in der aktuellen Pipeline.</span><span class="sxs-lookup"><span data-stu-id="ed300-109">If PowerShell does not handle a terminating error in some way, PowerShell also stops running the function or script in the current pipeline.</span></span> <span data-ttu-id="ed300-110">In anderen Sprachen, wie z. b. c#, werden abschließende Fehler als Ausnahmen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ed300-110">In other languages, such as C#, terminating errors are known as exceptions.</span></span>

<span data-ttu-id="ed300-111">Das `trap` Schlüsselwort gibt eine Liste von Anweisungen an, die beim Auftreten eines abschließenden Fehlers ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ed300-111">The `trap` keyword specifies a list of statements to run when a terminating error occurs.</span></span> <span data-ttu-id="ed300-112">`trap` -Anweisungen behandeln die abschließenden Fehler wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ed300-112">`trap` statements handle the terminating errors in the following ways:</span></span>

- <span data-ttu-id="ed300-113">Zeigen Sie den Fehler nach der Verarbeitung des `trap` Anweisungsblocks an, und setzen Sie die Ausführung des Skripts oder der Funktion mit fort `trap`</span><span class="sxs-lookup"><span data-stu-id="ed300-113">Display the error after processing the `trap` statement block and continuing execution of the script or function containing the `trap`.</span></span> <span data-ttu-id="ed300-114">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="ed300-114">This is the default behavior.</span></span>

- <span data-ttu-id="ed300-115">Zeigen Sie den Fehler an, und brechen Sie die Ausführung des Skripts oder der Funktion `trap` mit der `break` in der- `trap` Anweisung ab.</span><span class="sxs-lookup"><span data-stu-id="ed300-115">Display the error and abort execution of the script or function containing the `trap` using `break` in the `trap` statement.</span></span>

- <span data-ttu-id="ed300-116">Stillen Sie den Fehler, aber setzen Sie die Ausführung des Skripts oder der Funktion mit der `trap` `continue` in der- `trap` Anweisung fort.</span><span class="sxs-lookup"><span data-stu-id="ed300-116">Silence the error, but continue execution of the script or function containing the `trap` by using `continue` in the `trap` statement.</span></span>

<span data-ttu-id="ed300-117">Die Anweisungs Liste der `trap` kann mehrere Bedingungen oder Funktionsaufrufe enthalten.</span><span class="sxs-lookup"><span data-stu-id="ed300-117">The statement list of the `trap` can include multiple conditions or function calls.</span></span> <span data-ttu-id="ed300-118">Mit `trap` können Protokolle, Testbedingungen oder sogar ein anderes Programm geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ed300-118">A `trap` can write logs, test conditions, or even run another program.</span></span>

### <a name="syntax"></a><span data-ttu-id="ed300-119">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed300-119">Syntax</span></span>

<span data-ttu-id="ed300-120">Die- `trap` Anweisung weist die folgende Syntax auf:</span><span class="sxs-lookup"><span data-stu-id="ed300-120">The `trap` statement has the following syntax:</span></span>

```powershell
trap [[<error type>]] {<statement list>}
```

<span data-ttu-id="ed300-121">Die- `trap` Anweisung enthält eine Liste von-Anweisungen, die ausgeführt werden sollen, wenn ein Abbruch Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="ed300-121">The `trap` statement includes a list of statements to run when a terminating error occurs.</span></span> <span data-ttu-id="ed300-122">Eine- `trap` Anweisung besteht aus dem `trap` Schlüsselwort, optional gefolgt von einem Typausdruck, und dem Anweisungsblock, der die Liste der Anweisungen enthält, die ausgeführt werden sollen, wenn ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ed300-122">A `trap` statement consists of the `trap` keyword, optionally followed by a type expression, and the statement block containing the list of statements to run when an error is trapped.</span></span> <span data-ttu-id="ed300-123">Der Typausdruck verfeinert die Typen von Fehlern, die von abgefangen werden `trap` .</span><span class="sxs-lookup"><span data-stu-id="ed300-123">The type expression refines the types of errors the `trap` catches.</span></span>

<span data-ttu-id="ed300-124">Skripts oder Befehle können mehrere- `trap` Anweisungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ed300-124">A script or command can have multiple `trap` statements.</span></span> <span data-ttu-id="ed300-125">`trap` -Anweisungen können an beliebiger Stelle im Skript oder Befehl angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ed300-125">`trap` statements can appear anywhere in the script or command.</span></span>

### <a name="trapping-all-terminating-errors"></a><span data-ttu-id="ed300-126">Alle abschließenden Fehler werden abfangen.</span><span class="sxs-lookup"><span data-stu-id="ed300-126">Trapping all terminating errors</span></span>

<span data-ttu-id="ed300-127">Wenn ein Abbruch Fehler auftritt, der in einem Skript oder Befehl nicht auf andere Weise behandelt wird, prüft PowerShell, `trap` ob eine Anweisung den Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="ed300-127">When a terminating error occurs that is not handled in another way in a script or command, PowerShell checks for a `trap` statement that handles the error.</span></span> <span data-ttu-id="ed300-128">Wenn eine- `trap` Anweisung vorhanden ist, führt PowerShell die Ausführung des Skripts oder Befehls in der `trap` Anweisung fort.</span><span class="sxs-lookup"><span data-stu-id="ed300-128">If a `trap` statement is present, PowerShell continues running the script or command in the `trap` statement.</span></span>

<span data-ttu-id="ed300-129">Das folgende Beispiel ist eine sehr einfache `trap` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="ed300-129">The following example is a very simple `trap` statement:</span></span>

```powershell
trap {"Error found."}
```

<span data-ttu-id="ed300-130">Diese `trap` Anweisung fängt jeden Beendigungs Fehler ein.</span><span class="sxs-lookup"><span data-stu-id="ed300-130">This `trap` statement traps any terminating error.</span></span>

<span data-ttu-id="ed300-131">Im folgenden Beispiel enthält die-Funktion eine Unsinn-Zeichenfolge, die einen Laufzeitfehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="ed300-131">In the following example, the function includes a nonsense string that causes a runtime error.</span></span>

```powershell
function TrapTest {
    trap {"Error found."}
    nonsenseString
}

TrapTest
```

<span data-ttu-id="ed300-132">Durch das Ausführen dieser Funktion wird Folgendes zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="ed300-132">Running this function returns the following:</span></span>

```Output
Error found.
nonsenseString : The term 'nonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:3 char:5
+     nonsenseString
+     ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (nonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="ed300-133">Das folgende Beispiel enthält eine- `trap` Anweisung, die den Fehler mit der `$_` automatischen Variablen anzeigt:</span><span class="sxs-lookup"><span data-stu-id="ed300-133">The following example includes a `trap` statement that displays the error by using the `$_` automatic variable:</span></span>

```powershell
function TrapTest {
    trap {"Error found: $_"}
    nonsenseString
}

TrapTest
```

<span data-ttu-id="ed300-134">Wenn Sie diese Version der Funktion ausführen, wird Folgendes zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="ed300-134">Running this version of the function returns the following:</span></span>

```Output
Error found: The term 'nonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
nonsenseString : The term 'nonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:3 char:5
+     nonsenseString
+     ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (nonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

> [!IMPORTANT]
> <span data-ttu-id="ed300-135">`trap` -Anweisungen können an beliebiger Stelle innerhalb eines bestimmten Bereichs definiert werden, gelten jedoch immer für alle Anweisungen in diesem Bereich.</span><span class="sxs-lookup"><span data-stu-id="ed300-135">`trap` statements may be defined anywhere within a given scope, but always apply to all statements in that scope.</span></span> <span data-ttu-id="ed300-136">Zur Laufzeit `trap` werden Anweisungen in einem-Block definiert, bevor andere Anweisungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ed300-136">At runtime, `trap` statements in a block are defined before any other statements are executed.</span></span> <span data-ttu-id="ed300-137">In JavaScript wird dies als " [Hosting](https://wikipedia.org/wiki/JavaScript_syntax#hoisting)" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ed300-137">In JavaScript, this is known as [hoisting](https://wikipedia.org/wiki/JavaScript_syntax#hoisting).</span></span> <span data-ttu-id="ed300-138">Dies bedeutet, dass- `trap` Anweisungen für alle Anweisungen in diesem Block gelten, auch wenn die Ausführung nicht hinter dem Punkt liegt, an dem Sie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ed300-138">This means that `trap` statements apply to all statements in that block even if execution has not advanced past the point at which they are defined.</span></span> <span data-ttu-id="ed300-139">Wenn Sie z. b `trap` . eine am Ende eines Skripts definieren und in der ersten Anweisung einen Fehler auslösen, wird dies weiterhin ausgelöst `trap` .</span><span class="sxs-lookup"><span data-stu-id="ed300-139">For example, defining a `trap` at the end of a script and throwing an error in the first statement still triggers that `trap`.</span></span>

### <a name="trapping-specific-errors"></a><span data-ttu-id="ed300-140">Abfangen von bestimmten Fehlern</span><span class="sxs-lookup"><span data-stu-id="ed300-140">Trapping specific errors</span></span>

<span data-ttu-id="ed300-141">Skripts oder Befehle können mehrere- `trap` Anweisungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ed300-141">A script or command can have multiple `trap` statements.</span></span> <span data-ttu-id="ed300-142">Eine `trap` kann definiert werden, um bestimmte Fehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="ed300-142">A `trap` can be defined to handle specific errors.</span></span>

<span data-ttu-id="ed300-143">Das folgende Beispiel ist eine- `trap` Anweisung, die den spezifischen Fehler **commandnotfoundexception** abgefangen:</span><span class="sxs-lookup"><span data-stu-id="ed300-143">The following example is a `trap` statement that traps the specific error **CommandNotFoundException** :</span></span>

```powershell
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
```

<span data-ttu-id="ed300-144">Wenn eine Funktion oder ein Skript auf eine Zeichenfolge trifft, die nicht mit einem bekannten Befehl identisch ist, wird in dieser `trap` Anweisung die Zeichenfolge "Befehls Fehler gefangen" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ed300-144">When a function or script encounters a string that does not match a known command, this `trap` statement displays the "Command error trapped" string.</span></span>
<span data-ttu-id="ed300-145">Nach dem Ausführen der `trap` Anweisungs Liste schreibt PowerShell das Fehler Objekt in den Fehler Datenstrom und setzt das Skript dann fort.</span><span class="sxs-lookup"><span data-stu-id="ed300-145">After running the `trap` statement list, PowerShell writes the error object to the error stream and then continues the script.</span></span>

<span data-ttu-id="ed300-146">PowerShell verwendet .NET-Ausnahme Typen.</span><span class="sxs-lookup"><span data-stu-id="ed300-146">PowerShell uses .NET exception types.</span></span> <span data-ttu-id="ed300-147">Im folgenden Beispiel wird der **System. Exception** -Fehlertyp angegeben:</span><span class="sxs-lookup"><span data-stu-id="ed300-147">The following example specifies the **System.Exception** error type:</span></span>

```powershell
trap [System.Exception] {"An error trapped"}
```

<span data-ttu-id="ed300-148">Der **commandnotfoundexception** -Fehlertyp erbt vom **System. Exception** -Typ.</span><span class="sxs-lookup"><span data-stu-id="ed300-148">The **CommandNotFoundException** error type inherits from the **System.Exception** type.</span></span> <span data-ttu-id="ed300-149">Diese Anweisung fängt einen Fehler ab, der von einem unbekannten Befehl erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ed300-149">This statement traps an error that is created by an unknown command.</span></span> <span data-ttu-id="ed300-150">Außerdem werden andere Fehlertypen abgefangen.</span><span class="sxs-lookup"><span data-stu-id="ed300-150">It also traps other error types.</span></span>

<span data-ttu-id="ed300-151">Sie können mehr als eine `trap` Anweisung in einem Skript erstellen.</span><span class="sxs-lookup"><span data-stu-id="ed300-151">You can have more than one `trap` statement in a script.</span></span> <span data-ttu-id="ed300-152">Jeder Fehlertyp kann nur von einer Anweisung eingefangen werden `trap` .</span><span class="sxs-lookup"><span data-stu-id="ed300-152">Each error type can be trapped by only one `trap` statement.</span></span> <span data-ttu-id="ed300-153">Wenn ein Abbruch Fehler auftritt, sucht PowerShell nach dem `trap` mit der spezifischsten Übereinstimmung, beginnend mit dem aktuellen Ausführungs Bereich.</span><span class="sxs-lookup"><span data-stu-id="ed300-153">When a terminating error occurs, PowerShell searches for the `trap` with the most specific match, starting in the current scope of execution.</span></span>

<span data-ttu-id="ed300-154">Das folgende Beispielskript enthält einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="ed300-154">The following script example contains an error.</span></span> <span data-ttu-id="ed300-155">Das Skript enthält eine allgemeine `trap` Anweisung, die alle abschließenden Fehler und eine bestimmte `trap` Anweisung, die den **commandnotfoundexception** -Typ angibt, abgefangen.</span><span class="sxs-lookup"><span data-stu-id="ed300-155">The script includes a general `trap` statement that traps any terminating error and a specific `trap` statement that specifies the **CommandNotFoundException** type.</span></span>

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException] {
  "Command error trapped"
}
nonsenseString
```

<span data-ttu-id="ed300-156">Das Ausführen dieses Skripts führt zu folgendem Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="ed300-156">Running this script produces the following result:</span></span>

```Output
Command error trapped
nonsenseString : The term 'nonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At C:\Temp\traptest.ps1:5 char:1
+ nonsenseString
+ ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (nonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="ed300-157">Da PowerShell "nonsenabstring" nicht als Cmdlet oder ein anderes Element erkennt, wird ein **commandnotfoundexception** -Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ed300-157">Because PowerShell does not recognize "nonsenseString" as a cmdlet or other item, it returns a **CommandNotFoundException** error.</span></span> <span data-ttu-id="ed300-158">Dieser abschließende Fehler wird von der jeweiligen `trap` Anweisung erfasst.</span><span class="sxs-lookup"><span data-stu-id="ed300-158">This terminating error is trapped by the specific `trap` statement.</span></span>

<span data-ttu-id="ed300-159">Das folgende Skript Beispiel enthält die gleichen `trap` Anweisungen mit einem anderen Fehler:</span><span class="sxs-lookup"><span data-stu-id="ed300-159">The following script example contains the same `trap` statements with a different error:</span></span>

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
1/$null
```

<span data-ttu-id="ed300-160">Das Ausführen dieses Skripts führt zu folgendem Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="ed300-160">Running this script produces the following result:</span></span>

```Output
Attempted to divide by zero.
At C:\temp\traptest.ps1:4 char:1
+ 1/$null
+ ~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], RuntimeException
    + FullyQualifiedErrorId : RuntimeException
```

<span data-ttu-id="ed300-161">Der Versuch, eine Division durch 0 (null) auszuführen, erstellt keinen **commandnotfoundexception** -Fehler.</span><span class="sxs-lookup"><span data-stu-id="ed300-161">The attempt to divide by zero does not create a **CommandNotFoundException** error.</span></span> <span data-ttu-id="ed300-162">Stattdessen wird dieser Fehler von der anderen- `trap` Anweisung abgefangen, die alle abschließenden Fehler abgefangen.</span><span class="sxs-lookup"><span data-stu-id="ed300-162">Instead, that error is trapped by the other `trap` statement, which traps any terminating error.</span></span>

### <a name="trapping-errors-and-scope"></a><span data-ttu-id="ed300-163">Abfangen von Fehlern und Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="ed300-163">Trapping errors and scope</span></span>

<span data-ttu-id="ed300-164">Wenn im gleichen Bereich wie die-Anweisung ein Abbruch Fehler auftritt `trap` , führt PowerShell die Liste der Anweisungen aus, die von definiert werden `trap` .</span><span class="sxs-lookup"><span data-stu-id="ed300-164">If a terminating error occurs in the same scope as the `trap` statement, PowerShell runs the list of statements defined by the `trap`.</span></span> <span data-ttu-id="ed300-165">Die Ausführung wird bei der Anweisung nach dem Fehler fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ed300-165">Execution continues at the statement after the error.</span></span> <span data-ttu-id="ed300-166">Wenn sich die- `trap` Anweisung in einem anderen Bereich als der Fehler befindet, wird die Ausführung bei der nächsten Anweisung fortgesetzt, die sich im gleichen Bereich wie die- `trap` Anweisung befindet.</span><span class="sxs-lookup"><span data-stu-id="ed300-166">If the `trap` statement is in a different scope from the error, execution continues at the next statement that is in the same scope as the `trap` statement.</span></span>

<span data-ttu-id="ed300-167">Wenn beispielsweise ein Fehler in einer Funktion auftritt und die- `trap` Anweisung in der-Funktion ist, wird das Skript bei der nächsten Anweisung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ed300-167">For example, if an error occurs in a function, and the `trap` statement is in the function, the script continues at the next statement.</span></span> <span data-ttu-id="ed300-168">Das folgende Skript enthält einen Fehler und eine- `trap` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="ed300-168">The following script contains an error and a `trap` statement:</span></span>

```powershell
function function1 {
    trap { "An error: " }
    NonsenseString
    "function1 was completed"
}

function1
```

<span data-ttu-id="ed300-169">Das Ausführen dieses Skripts führt zu folgendem Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="ed300-169">Running this script produces the following result:</span></span>

```Output
An error:
NonsenseString : The term 'NonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:3 char:5
+     NonsenseString
+     ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (NonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

function1 was completed
```

<span data-ttu-id="ed300-170">Die- `trap` Anweisung in der Funktion fängt den Fehler ab.</span><span class="sxs-lookup"><span data-stu-id="ed300-170">The `trap` statement in the function traps the error.</span></span> <span data-ttu-id="ed300-171">Nach dem Anzeigen der Meldung wird die Ausführung der Funktion von PowerShell fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ed300-171">After displaying the message, PowerShell resumes running the function.</span></span> <span data-ttu-id="ed300-172">Beachten Sie, dass `Function1` abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="ed300-172">Note that `Function1` was completed.</span></span>

<span data-ttu-id="ed300-173">Vergleichen Sie dies mit dem folgenden Beispiel, das denselben Fehler und dieselbe `trap` Anweisung aufweist.</span><span class="sxs-lookup"><span data-stu-id="ed300-173">Compare this with the following example, which has the same error and `trap` statement.</span></span> <span data-ttu-id="ed300-174">In diesem Beispiel tritt die- `trap` Anweisung außerhalb der-Funktion auf:</span><span class="sxs-lookup"><span data-stu-id="ed300-174">In this example, the `trap` statement occurs outside the function:</span></span>

```powershell
function function2 {
    NonsenseString
    "function2 was completed"
}

trap { "An error: " }

function2
```

<span data-ttu-id="ed300-175">Das Ausführen der `Function2` Funktion führt zu folgendem Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="ed300-175">Running the `Function2` function produces the following result:</span></span>

```Output
An error:
NonsenseString : The term 'NonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At C:\temp\traptest.ps1:2 char:5
+     NonsenseString
+     ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (NonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="ed300-176">In diesem Beispiel wurde der Befehl "Funktion2 wurde abgeschlossen" nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed300-176">In this example, the "function2 was completed" command was not run.</span></span> <span data-ttu-id="ed300-177">In beiden Beispielen tritt der abschließende Fehler innerhalb der-Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="ed300-177">In both examples, the terminating error occurs within the function.</span></span> <span data-ttu-id="ed300-178">In diesem Beispiel befindet sich die- `trap` Anweisung jedoch außerhalb der-Funktion.</span><span class="sxs-lookup"><span data-stu-id="ed300-178">In this example, however, the `trap` statement is outside the function.</span></span> <span data-ttu-id="ed300-179">PowerShell wechselt nicht wieder in die Funktion, nachdem die-Anweisung ausgeführt wurde `trap` .</span><span class="sxs-lookup"><span data-stu-id="ed300-179">PowerShell does not go back into the function after the `trap` statement runs.</span></span>

> [!CAUTION]
> <span data-ttu-id="ed300-180">Wenn für die gleiche Fehlerbedingung mehrere Traps definiert sind, wird der erste, `trap` lexikalisch (höchste im Gültigkeitsbereich), verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed300-180">When multiple traps are defined for the same error condition, the first `trap` defined lexically (highest in the scope) is used.</span></span>

<span data-ttu-id="ed300-181">Im folgenden Beispiel wird nur der `trap` mit "Whoops 1" ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed300-181">In the following example, only the `trap` with "whoops 1" is run.</span></span>

```powershell
Remove-Item -ErrorAction Stop ThisFileDoesNotExist
trap { "whoops 1"; continue }
trap { "whoops 2"; continue }
```

> [!IMPORTANT]
> <span data-ttu-id="ed300-182">Eine Trap-Anweisung bezieht sich auf den Speicherort, an dem Sie kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="ed300-182">A Trap statement is scoped to where it compiles.</span></span> <span data-ttu-id="ed300-183">Wenn Sie über eine- `trap` Anweisung innerhalb einer Funktion oder eines Punkt-/punktskripts verfügen, `trap` werden alle Anweisungen in entfernt, wenn die Funktion oder das Punkt-Source-Skript beendet wird.</span><span class="sxs-lookup"><span data-stu-id="ed300-183">If you have a `trap` statement inside a function or dot sourced script, when the function or dot sourced script exits, all `trap` statements inside are removed.</span></span>

### <a name="using-the-break-and-continue-keywords"></a><span data-ttu-id="ed300-184">Verwenden der Schlüsselwörter Break und Continue</span><span class="sxs-lookup"><span data-stu-id="ed300-184">Using the break and continue keywords</span></span>

<span data-ttu-id="ed300-185">Sie können die `break` `continue` Schlüsselwörter und in einer- `trap` Anweisung verwenden, um zu bestimmen, ob ein Skript oder ein Befehl nach einem Beendigungs Fehler weiterhin ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ed300-185">You can use the `break` and `continue` keywords in a `trap` statement to determine whether a script or command continues to run after a terminating error.</span></span>

<span data-ttu-id="ed300-186">Wenn Sie eine- `break` Anweisung in eine `trap` Anweisungs Liste einschließen, hält PowerShell die Funktion oder das Skript an.</span><span class="sxs-lookup"><span data-stu-id="ed300-186">If you include a `break` statement in a `trap` statement list, PowerShell stops the function or script.</span></span> <span data-ttu-id="ed300-187">Die folgende Beispiel Funktion verwendet das- `break` Schlüsselwort in einer- `trap` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="ed300-187">The following sample function uses the `break` keyword in a `trap` statement:</span></span>

```powershell
function break_example {
    trap {
        "Error trapped"
        break
    }
    1/$null
    "Function completed."
}

break_example
```

```Output
Error trapped
Attempted to divide by zero.
At line:6 char:5
+     1/$null
+     ~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], ParentContainsErrorRecordException
    + FullyQualifiedErrorId : RuntimeException
```

<span data-ttu-id="ed300-188">Da die- `trap` Anweisung das- `break` Schlüsselwort enthielt, wird die Funktion nicht weiter ausgeführt, und die Zeile "Funktion abgeschlossen" wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed300-188">Because the `trap` statement included the `break` keyword, the function does not continue to run, and the "Function completed" line is not run.</span></span>

<span data-ttu-id="ed300-189">Wenn Sie ein `continue` Schlüsselwort in eine- `trap` Anweisung einfügen, wird PowerShell nach der Anweisung, die den Fehler verursacht hat, genauso wie ohne oder fortgesetzt `break` `continue` .</span><span class="sxs-lookup"><span data-stu-id="ed300-189">If you include a `continue` keyword in a `trap` statement, PowerShell resumes after the statement that caused the error, just as it would without `break` or `continue`.</span></span> <span data-ttu-id="ed300-190">Mit dem- `continue` Schlüsselwort schreibt PowerShell jedoch keinen Fehler in den Fehler Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="ed300-190">With the `continue` keyword, however, PowerShell does not write an error to the error stream.</span></span>

<span data-ttu-id="ed300-191">Die folgende Beispiel Funktion verwendet das- `continue` Schlüsselwort in einer- `trap` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="ed300-191">The following sample function uses the `continue` keyword in a `trap` statement:</span></span>

```powershell
function continue_example {
    trap {
        "Error trapped"
        continue
    }
    1/$null
    "Function completed."
}

continue_example
```

```Output
Error trapped
Function completed.
```

<span data-ttu-id="ed300-192">Die Funktion wird fortgesetzt, nachdem der Fehler aufgetreten ist, und die Anweisung "Function abgeschlossene" wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed300-192">The function resumes after the error is trapped, and the "Function completed" statement runs.</span></span> <span data-ttu-id="ed300-193">Es wird kein Fehler in den Fehler Datenstrom geschrieben.</span><span class="sxs-lookup"><span data-stu-id="ed300-193">No error is written to the error stream.</span></span>

## <a name="notes"></a><span data-ttu-id="ed300-194">Notizen</span><span class="sxs-lookup"><span data-stu-id="ed300-194">Notes</span></span>

<span data-ttu-id="ed300-195">`trap` -Anweisungen bieten eine einfache Möglichkeit, um umfassend sicherzustellen, dass alle abschließenden Fehler innerhalb eines Bereichs behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="ed300-195">`trap` statements provide a simple way to broadly ensure all terminating errors within a scope are handled.</span></span> <span data-ttu-id="ed300-196">Verwenden Sie für eine differenziertere Fehlerbehandlung `try` / `catch` Blöcke, bei denen Traps mithilfe von-Anweisungen definiert werden `catch` .</span><span class="sxs-lookup"><span data-stu-id="ed300-196">For more finer-grained error handling, use `try`/`catch` blocks where traps are defined using `catch` statements.</span></span> <span data-ttu-id="ed300-197">Die- `catch` Anweisungen gelten nur für den Code in der zugeordneten- `try` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ed300-197">The `catch` statements only apply to the code inside the associated `try` statement.</span></span> <span data-ttu-id="ed300-198">Weitere Informationen finden Sie unter [about_Try_Catch_Finally](about_Try_Catch_Finally.md).</span><span class="sxs-lookup"><span data-stu-id="ed300-198">For more information, see [about_Try_Catch_Finally](about_Try_Catch_Finally.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ed300-199">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="ed300-199">See also</span></span>

[<span data-ttu-id="ed300-200">about_Break</span><span class="sxs-lookup"><span data-stu-id="ed300-200">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="ed300-201">about_Continue</span><span class="sxs-lookup"><span data-stu-id="ed300-201">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="ed300-202">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="ed300-202">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="ed300-203">about_Throw</span><span class="sxs-lookup"><span data-stu-id="ed300-203">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="ed300-204">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="ed300-204">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)
