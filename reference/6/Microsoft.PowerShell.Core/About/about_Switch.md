---
description: Erläutert, wie ein Schalter verwendet wird, um mehrere-Anweisungen zu verarbeiten `If` .
keywords: powershell,cmdlet
Locale: en-US
ms.date: 05/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_switch?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Switch
ms.openlocfilehash: 2b39f8e0ad49c9e5f6cab06eea34e8f27b37186b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221124"
---
# <a name="about-switch"></a><span data-ttu-id="a5bfc-104">Info zum Schalter</span><span class="sxs-lookup"><span data-stu-id="a5bfc-104">About Switch</span></span>

## <a name="short-description"></a><span data-ttu-id="a5bfc-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5bfc-105">Short description</span></span>
<span data-ttu-id="a5bfc-106">Erläutert, wie ein Schalter verwendet wird, um mehrere-Anweisungen zu verarbeiten `If` .</span><span class="sxs-lookup"><span data-stu-id="a5bfc-106">Explains how to use a switch to handle multiple `If` statements.</span></span>

## <a name="long-description"></a><span data-ttu-id="a5bfc-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5bfc-107">Long description</span></span>

<span data-ttu-id="a5bfc-108">Verwenden Sie eine-Anweisung, um eine Bedingung in einem Skript oder einer Funktion zu überprüfen `If` .</span><span class="sxs-lookup"><span data-stu-id="a5bfc-108">To check a condition in a script or function, use an `If` statement.</span></span> <span data-ttu-id="a5bfc-109">`If`Mit der-Anweisung können viele Arten von Bedingungen überprüft werden, einschließlich des Werts der Variablen und der Eigenschaften von Objekten.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-109">The `If` statement can check many types of conditions, including the value of variables and the properties of objects.</span></span>

<span data-ttu-id="a5bfc-110">Verwenden Sie eine-Anweisung, um mehrere Bedingungen zu überprüfen `Switch` .</span><span class="sxs-lookup"><span data-stu-id="a5bfc-110">To check multiple conditions, use a `Switch` statement.</span></span> <span data-ttu-id="a5bfc-111">Die- `Switch` Anweisung ist äquivalent zu einer Reihe von- `If` Anweisungen, aber Sie ist einfacher.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-111">The `Switch` statement is equivalent to a series of `If` statements, but it is simpler.</span></span> <span data-ttu-id="a5bfc-112">Die `Switch` -Anweisung listet jede Bedingung und eine optionale Aktion auf.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-112">The `Switch` statement lists each condition and an optional action.</span></span> <span data-ttu-id="a5bfc-113">Wenn eine Bedingung abgerufen wird, wird die Aktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-113">If a condition obtains, the action is performed.</span></span>

<span data-ttu-id="a5bfc-114">Die `Switch` -Anweisung kann die `$_` `$switch` automatischen Variablen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-114">The `Switch` statement can use the `$_` and `$switch` automatic variables.</span></span> <span data-ttu-id="a5bfc-115">Weitere Informationen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a5bfc-115">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="a5bfc-116">Eine Basis `Switch` Anweisung hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="a5bfc-116">A basic `Switch` statement has the following format:</span></span>

```powershell
Switch (<test-value>)
{
    <condition> {<action>}
    <condition> {<action>}
}
```

<span data-ttu-id="a5bfc-117">Beispielsweise vergleicht die folgende `Switch` Anweisung den Testwert 3 mit jeder der Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-117">For example, the following `Switch` statement compares the test value, 3, to each of the conditions.</span></span> <span data-ttu-id="a5bfc-118">Wenn der Testwert mit der Bedingung übereinstimmt, wird die Aktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-118">When the test value matches the condition, the action is performed.</span></span>

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."}
    4 {"It is four."}
}
```

```Output
It is three.
```

<span data-ttu-id="a5bfc-119">In diesem einfachen Beispiel wird der Wert mit jeder Bedingung in der Liste verglichen, auch wenn eine Entsprechung für den Wert 3 vorliegt.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-119">In this simple example, the value is compared to each condition in the list, even though there is a match for the value 3.</span></span> <span data-ttu-id="a5bfc-120">Die folgende `Switch` Anweisung hat zwei Bedingungen für den Wert 3.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-120">The following `Switch` statement has two conditions for a value of 3.</span></span> <span data-ttu-id="a5bfc-121">Es wird veranschaulicht, dass standardmäßig alle Bedingungen getestet werden.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-121">It demonstrates that, by default, all conditions are tested.</span></span>

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."}
    4 {"It is four."}
    3 {"Three again."}
}
```

```Output
It is three.
Three again.
```

<span data-ttu-id="a5bfc-122">Verwenden Sie die-Anweisung, um den `Switch` zu unterbinden `Break`</span><span class="sxs-lookup"><span data-stu-id="a5bfc-122">To direct the `Switch` to stop comparing after a match, use the `Break` statement.</span></span> <span data-ttu-id="a5bfc-123">Die-Anweisung `Break` beendet die- `Switch` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-123">The `Break` statement terminates the `Switch` statement.</span></span>

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."; Break}
    4 {"It is four."}
    3 {"Three again."}
}
```

```Output
It is three.
```

<span data-ttu-id="a5bfc-124">Wenn der Testwert eine Auflistung ist, z. b. ein Array, wird jedes Element in der Auflistung in der Reihenfolge ausgewertet, in der es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-124">If the test value is a collection, such as an array, each item in the collection is evaluated in the order in which it appears.</span></span> <span data-ttu-id="a5bfc-125">In den folgenden Beispielen wird 4 und dann 2 ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-125">The following examples evaluates 4 and then 2.</span></span>

```powershell
switch (4, 2)
{
    1 {"It is one." }
    2 {"It is two." }
    3 {"It is three." }
    4 {"It is four." }
    3 {"Three again."}
}
```

```Output
It is four.
It is two.
```

<span data-ttu-id="a5bfc-126">Alle- `Break` Anweisungen gelten für die Auflistung, nicht für jeden Wert, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-126">Any `Break` statements apply to the collection, not to each value, as shown in the following example.</span></span> <span data-ttu-id="a5bfc-127">Die- `Switch` Anweisung wird von der- `Break` Anweisung in der Bedingung von Wert 4 beendet.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-127">The `Switch` statement is terminated by the `Break` statement in the condition of value 4.</span></span>

```powershell
switch (4, 2)
{
    1 {"It is one."; Break}
    2 {"It is two." ; Break }
    3 {"It is three." ; Break }
    4 {"It is four." ; Break }
    3 {"Three again."}
}
```

```Output
It is four.
```

### <a name="syntax"></a><span data-ttu-id="a5bfc-128">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5bfc-128">Syntax</span></span>

<span data-ttu-id="a5bfc-129">Die Syntax der kompletten `Switch` Anweisung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a5bfc-129">The complete `Switch` statement syntax is as follows:</span></span>

```
switch [-regex|-wildcard|-exact][-casesensitive] (<value>)
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

<span data-ttu-id="a5bfc-130">oder</span><span class="sxs-lookup"><span data-stu-id="a5bfc-130">or</span></span>

```
switch [-regex|-wildcard|-exact][-casesensitive] -file filename
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

<span data-ttu-id="a5bfc-131">Wenn keine Parameter verwendet werden, `Switch` verhält sich wie bei der Verwendung des **exakten** Parameters.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-131">If no parameters are used, `Switch` behaves the same as using the **Exact** parameter.</span></span> <span data-ttu-id="a5bfc-132">Die Groß-/Kleinschreibung wird für den Wert nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-132">It performs a case-insensitive match for the value.</span></span> <span data-ttu-id="a5bfc-133">Wenn der Wert eine Auflistung ist, wird jedes Element in der Reihenfolge ausgewertet, in der es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-133">If the value is a collection, each element is evaluated in the order in which it appears.</span></span>

<span data-ttu-id="a5bfc-134">Die `Switch` Anweisung muss mindestens eine Bedingungs Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-134">The `Switch` statement must include at least one condition statement.</span></span>

<span data-ttu-id="a5bfc-135">Die- `Default` Klausel wird ausgelöst, wenn der Wert keiner der Bedingungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-135">The `Default` clause is triggered when the value does not match any of the conditions.</span></span> <span data-ttu-id="a5bfc-136">Dies entspricht einer- `Else` Klausel in einer- `If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-136">It is equivalent to an `Else` clause in an `If` statement.</span></span> <span data-ttu-id="a5bfc-137">`Default`In jeder Anweisung ist nur eine einzige Klausel zulässig `Switch` .</span><span class="sxs-lookup"><span data-stu-id="a5bfc-137">Only one `Default` clause is permitted in each `Switch` statement.</span></span>

<span data-ttu-id="a5bfc-138">`Switch` verfügt über die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="a5bfc-138">`Switch` has the following parameters:</span></span>

- <span data-ttu-id="a5bfc-139">**Wildcard** : gibt an, dass die Bedingung eine Platzhalter Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-139">**Wildcard** - Indicates that the condition is a wildcard string.</span></span> <span data-ttu-id="a5bfc-140">Wenn die Match-Klausel keine Zeichenfolge ist, wird der-Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-140">If the match clause is not a string, the parameter is ignored.</span></span> <span data-ttu-id="a5bfc-141">Bei dem Vergleich wird Groß- und Kleinschreibung nicht unterschieden.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-141">The comparison is case-insensitive.</span></span>
- <span data-ttu-id="a5bfc-142">**Exact** : gibt an, dass die Match-Klausel, wenn Sie eine Zeichenfolge ist, genau übereinstimmen muss.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-142">**Exact** - Indicates that the match clause, if it is a string, must match exactly.</span></span> <span data-ttu-id="a5bfc-143">Wenn die Match-Klausel keine Zeichenfolge ist, wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-143">If the match clause is not a string, this parameter is ignored.</span></span> <span data-ttu-id="a5bfc-144">Bei dem Vergleich wird Groß- und Kleinschreibung nicht unterschieden.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-144">The comparison is case-insensitive.</span></span>
- <span data-ttu-id="a5bfc-145">**CaseSensitive** : berücksichtigt die Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-145">**CaseSensitive** - Performs a case-sensitive match.</span></span> <span data-ttu-id="a5bfc-146">Wenn die Match-Klausel keine Zeichenfolge ist, wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-146">If the match clause is not a string, this parameter is ignored.</span></span>
- <span data-ttu-id="a5bfc-147">**File** : übernimmt Eingaben aus einer Datei anstelle einer Value-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-147">**File** - Takes input from a file rather than a value statement.</span></span> <span data-ttu-id="a5bfc-148">Wenn mehrere **Datei** Parameter enthalten sind, wird nur der letzte verwendet.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-148">If multiple **File** parameters are included, only the last one is used.</span></span> <span data-ttu-id="a5bfc-149">Jede Zeile der Datei wird von der-Anweisung gelesen und ausgewertet `Switch` .</span><span class="sxs-lookup"><span data-stu-id="a5bfc-149">Each line of the file is read and evaluated by the `Switch` statement.</span></span> <span data-ttu-id="a5bfc-150">Bei dem Vergleich wird Groß- und Kleinschreibung nicht unterschieden.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-150">The comparison is case-insensitive.</span></span>
- <span data-ttu-id="a5bfc-151">**Regex** : führt einen regulären Ausdruck aus, der mit der Bedingung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-151">**Regex** - Performs regular expression matching of the value to the condition.</span></span> <span data-ttu-id="a5bfc-152">Wenn die Match-Klausel keine Zeichenfolge ist, wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-152">If the match clause is not a string, this parameter is ignored.</span></span>
  <span data-ttu-id="a5bfc-153">Bei dem Vergleich wird Groß- und Kleinschreibung nicht unterschieden.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-153">The comparison is case-insensitive.</span></span> <span data-ttu-id="a5bfc-154">Die `$matches` Automatische Variable ist zur Verwendung innerhalb des entsprechenden Anweisungsblocks verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-154">The `$matches` automatic variable is available for use within the matching statement block.</span></span>

> [!NOTE]
> <span data-ttu-id="a5bfc-155">Beim Angeben von in Konflikt stehenden Werten wie **Regex** und Platzhalter hat der letzte angegebene Parameter **Vorrang, und** alle in Konflikt stehenden Parameter werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-155">When specifying conflicting values, like **Regex** and **Wildcard** , the last parameter specified takes precedence, and all conflicting parameters are ignored.</span></span> <span data-ttu-id="a5bfc-156">Es sind auch mehrere Instanzen von Parametern zulässig.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-156">Multiple instances of parameters are also permitted.</span></span> <span data-ttu-id="a5bfc-157">Allerdings ist nur der letzte verwendete Parameter gültig.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-157">However, only the last parameter used is effective.</span></span>

<span data-ttu-id="a5bfc-158">In diesem Beispiel wird ein Objekt, das keine Zeichen folgen-oder numerischen Daten ist, an das-Objekt übermittelt `Switch` .</span><span class="sxs-lookup"><span data-stu-id="a5bfc-158">In this example, an object that's not a string or numerical data is passed to the `Switch`.</span></span> <span data-ttu-id="a5bfc-159">`Switch`Führt eine Zeichen folgen Umwandlung für das-Objekt aus und wertet das Ergebnis aus.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-159">The `Switch` performs a string coercion on the object and evaluates the outcome.</span></span>

```powershell
$test = @{
    Test  = 'test'
    Test2 = 'test2'
}

$test.ToString()

switch -Exact ($test)
{
    'System.Collections.Hashtable'
    {
        'Hashtable string coercion'
    }
    'test'
    {
        'Hashtable value'
    }
}
```

```Output
System.Collections.Hashtable
Hashtable string coercion
```

<span data-ttu-id="a5bfc-160">In diesem Beispiel gibt es keine übereinstimmende Groß-/Kleinschreibung, sodass keine Ausgabe vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-160">In this example, there is no matching case so there is no output.</span></span>

```powershell
switch ("fourteen")
{
    1 {"It is one."; Break}
    2 {"It is two."; Break}
    3 {"It is three."; Break}
    4 {"It is four."; Break}
    "fo*" {"That's too many."}
}
```

<span data-ttu-id="a5bfc-161">Durch Hinzufügen der- `Default` Klausel können Sie eine Aktion ausführen, wenn keine anderen Bedingungen erfolgreich sind.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-161">By adding the `Default` clause, you can perform an action when no other conditions succeed.</span></span>

```powershell
switch ("fourteen")
{
    1 {"It is one."; Break}
    2 {"It is two."; Break}
    3 {"It is three."; Break}
    4 {"It is four."; Break}
    "fo*" {"That's too many."}
    Default {
        "No matches"
    }
}
```

```Output
No matches
```

<span data-ttu-id="a5bfc-162">Damit das Wort "14" einem Fall entspricht, müssen Sie den- `-Wildcard` Parameter oder den- `-Regex` Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-162">For the word "fourteen" to match a case you must use the `-Wildcard` or `-Regex` parameter.</span></span>

```powershell
   PS> switch -Wildcard ("fourteen")
       {
           1 {"It is one."; Break}
           2 {"It is two."; Break}
           3 {"It is three."; Break}
           4 {"It is four."; Break}
           "fo*" {"That's too many."}
       }
 ```

```Output
That's too many.
```

<span data-ttu-id="a5bfc-163">Im folgenden Beispiel wird der- `-Regex` Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-163">The following example uses the `-Regex` parameter.</span></span>

```powershell
$target = 'https://bing.com'
switch -Regex ($target)
{
    '^ftp\://.*$' { "$_ is an ftp address"; Break }
    '^\w+@\w+\.com|edu|org$' { "$_ is an email address"; Break }
    '^(http[s]?)\://.*$' { "$_ is a web address that uses $($matches[1])"; Break }
}
```

```Output
https://bing.com is a web address that uses https
```

<span data-ttu-id="a5bfc-164">Eine Switch-Anweisungs Bedingung kann wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="a5bfc-164">A Switch statement condition may be either:</span></span>

- <span data-ttu-id="a5bfc-165">Ein Ausdruck, dessen Wert mit dem Eingabe Wert verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-165">An expression whose value is compared to the input value</span></span>
- <span data-ttu-id="a5bfc-166">Ein Skriptblock, der zurückgeben sollte, `$true` Wenn eine Bedingung erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-166">A script block which should return `$true` if a condition is met.</span></span>

<span data-ttu-id="a5bfc-167">Die `$_` Automatische Variable enthält den Wert, der an die Switch-Anweisung übermittelt wurde, und ist für die Auswertung und Verwendung im Bereich der Bedingungs Anweisungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-167">The `$_` automatic variable contains the value passed to the switch statement and is available for evaluation and use within the scope of the condition statements.</span></span>

<span data-ttu-id="a5bfc-168">Die Aktion für jede Bedingung ist unabhängig von den Aktionen in anderen Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-168">The action for each condition is independent of the actions in other conditions.</span></span>

<span data-ttu-id="a5bfc-169">Im folgenden Beispiel wird veranschaulicht, wie Skriptblöcke als `Switch` Anweisungs Bedingungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-169">The following example demonstrates the use of script blocks as `Switch` statement conditions.</span></span>

```powershell
switch ("Test")
{
    {$_ -is [String]} {
        "Found a string"
    }
    "Test" {
        "This $_ executes as well"
    }
}
```

```Output
Found a string
This Test executes as well
```

<span data-ttu-id="a5bfc-170">Wenn der Wert mehreren Bedingungen entspricht, wird die Aktion für jede Bedingung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-170">If the value matches multiple conditions, the action for each condition is executed.</span></span> <span data-ttu-id="a5bfc-171">Um dieses Verhalten zu ändern, verwenden Sie die `Break` `Continue` Schlüsselwörter oder.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-171">To change this behavior, use the `Break` or `Continue` keywords.</span></span>

<span data-ttu-id="a5bfc-172">Das `Break` -Schlüsselwort beendet die Verarbeitung und beendet die- `Switch` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-172">The `Break` keyword stops processing and exits the `Switch` statement.</span></span>

<span data-ttu-id="a5bfc-173">Das- `Continue` Schlüsselwort beendet die Verarbeitung des aktuellen Werts, setzt aber die Verarbeitung aller nachfolgenden Werte fort.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-173">The `Continue` keyword stops processing the current value, but continues processing any subsequent values.</span></span>

<span data-ttu-id="a5bfc-174">Im folgenden Beispiel wird ein Array von Zahlen verarbeitet und angezeigt, wenn Sie ungerade oder gerade sind.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-174">The following example processes an array of numbers and displays if they are odd or even.</span></span> <span data-ttu-id="a5bfc-175">Negative Zahlen werden mit dem- `Continue` Schlüsselwort übersprungen.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-175">Negative numbers are skipped with the `Continue` keyword.</span></span> <span data-ttu-id="a5bfc-176">Wenn eine nicht--Zahl gefunden wird, wird die Ausführung mit dem- `Break` Schlüsselwort beendet.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-176">If a non-number is encountered, execution is terminated with the `Break` keyword.</span></span>

```powershell
switch (1,4,-1,3,"Hello",2,1)
{
    {$_ -lt 0} { Continue }
    {$_ -isnot [Int32]} { Break }
    {$_ % 2} {
        "$_ is Odd"
    }
    {-not ($_ % 2)} {
        "$_ is Even"
    }
}
```

```Output
1 is Odd
4 is Even
3 is Odd
```

## <a name="see-also"></a><span data-ttu-id="a5bfc-177">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a5bfc-177">See also</span></span>

[<span data-ttu-id="a5bfc-178">about_Break</span><span class="sxs-lookup"><span data-stu-id="a5bfc-178">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="a5bfc-179">about_Continue</span><span class="sxs-lookup"><span data-stu-id="a5bfc-179">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="a5bfc-180">about_If</span><span class="sxs-lookup"><span data-stu-id="a5bfc-180">about_If</span></span>](about_If.md)

[<span data-ttu-id="a5bfc-181">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="a5bfc-181">about_Script_Blocks</span></span>](about_Script_Blocks.md)
