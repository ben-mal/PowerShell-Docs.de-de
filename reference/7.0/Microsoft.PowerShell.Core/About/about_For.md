---
description: Beschreibt einen Sprachbefehl, den Sie verwenden können, um-Anweisungen auf der Grundlage eines bedingten Tests auszuführen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 3/4/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_for?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_For
ms.openlocfilehash: 0cc86c5969519f4c60702fdc1aed0a86ce11e1a1
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223828"
---
# <a name="about-for"></a><span data-ttu-id="bf323-104">Info zu</span><span class="sxs-lookup"><span data-stu-id="bf323-104">About For</span></span>

## <a name="short-description"></a><span data-ttu-id="bf323-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf323-105">Short description</span></span>
<span data-ttu-id="bf323-106">Beschreibt einen Sprachbefehl, den Sie verwenden können, um-Anweisungen auf der Grundlage eines bedingten Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bf323-106">Describes a language command you can use to run statements based on a conditional test.</span></span>

## <a name="long-description"></a><span data-ttu-id="bf323-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf323-107">Long description</span></span>

<span data-ttu-id="bf323-108">Die- `For` Anweisung (auch als- `For` Schleife bezeichnet) ist ein Sprachkonstrukt, mit dem Sie eine-Schleife erstellen können, die Befehle in einem Befehls Block ausführt, während eine angegebene Bedingung als ausgewertet wird `$true` .</span><span class="sxs-lookup"><span data-stu-id="bf323-108">The `For` statement (also known as a `For` loop) is a language construct you can use to create a loop that runs commands in a command block while a specified condition evaluates to `$true`.</span></span>

<span data-ttu-id="bf323-109">Eine typische Verwendung der `For` -Schleife besteht darin, ein Array von-Werten zu durchlaufen und eine Teilmenge dieser Werte zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="bf323-109">A typical use of the `For` loop is to iterate an array of values and to operate on a subset of these values.</span></span> <span data-ttu-id="bf323-110">Wenn Sie alle Werte in einem Array durchlaufen möchten, sollten Sie in den meisten Fällen eine- `Foreach` Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="bf323-110">In most cases, if you want to iterate all the values in an array, consider using a `Foreach` statement.</span></span>

### <a name="syntax"></a><span data-ttu-id="bf323-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf323-111">Syntax</span></span>

<span data-ttu-id="bf323-112">Das folgende Beispiel zeigt die- `For` Anweisungs Syntax.</span><span class="sxs-lookup"><span data-stu-id="bf323-112">The following shows the `For` statement syntax.</span></span>

```
for (<Init>; <Condition>; <Repeat>)
{
    <Statement list>
}
```

<span data-ttu-id="bf323-113">Der **Init** -Platzhalter stellt einen oder mehrere Befehle dar, die vor Beginn der Schleife ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bf323-113">The **Init** placeholder represents one or more commands that are run before the loop begins.</span></span> <span data-ttu-id="bf323-114">In der Regel verwenden Sie den **Init** -Teil der-Anweisung, um eine Variable mit einem Startwert zu erstellen und zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="bf323-114">You typically use the **Init** portion of the statement to create and initialize a variable with a starting value.</span></span>

<span data-ttu-id="bf323-115">Diese Variable ist die Grundlage für die Bedingung, die im nächsten Teil der Anweisung getestet werden soll `For` .</span><span class="sxs-lookup"><span data-stu-id="bf323-115">This variable will then be the basis for the condition to be tested in the next portion of the `For` statement.</span></span>

<span data-ttu-id="bf323-116">Der **Bedingungs Platzhalter stellt den Teil** der- `For` Anweisung dar, der zu `$true` einem `$false` **booleschen Wert oder einem booleschen** Wert aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="bf323-116">The **Condition** placeholder represents the portion of the `For` statement that resolves to a `$true` or `$false` **Boolean** value.</span></span> <span data-ttu-id="bf323-117">PowerShell wertet die Bedingung bei jeder Ausführung der `For` Schleife aus.</span><span class="sxs-lookup"><span data-stu-id="bf323-117">PowerShell evaluates the condition each time the `For` loop runs.</span></span> <span data-ttu-id="bf323-118">Wenn die-Anweisung ist `$true` , werden die Befehle im Befehls Block ausgeführt, und die-Anweisung wird erneut ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="bf323-118">If the statement is `$true`, the commands in the command block run, and the statement is evaluated again.</span></span> <span data-ttu-id="bf323-119">Wenn die Bedingung weiterhin besteht `$true` , werden die Befehle in der **Anweisungs Liste** erneut ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bf323-119">If the condition is still `$true`, the commands in the **Statement list** run again.</span></span> <span data-ttu-id="bf323-120">Die Schleife wird wiederholt, bis die Bedingung wird `$false` .</span><span class="sxs-lookup"><span data-stu-id="bf323-120">The loop is repeated until the condition becomes `$false`.</span></span>

<span data-ttu-id="bf323-121">Der **Wiederholungs** Platzhalter stellt einen oder mehrere durch Kommas getrennte Befehle dar, die jedes Mal ausgeführt werden, wenn die Schleife wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="bf323-121">The **Repeat** placeholder represents one or more commands, separated by commas, that are executed each time the loop repeats.</span></span> <span data-ttu-id="bf323-122">In der Regel wird dies verwendet, um eine Variable zu ändern, die innerhalb des **Bedingungs Teils der** Anweisung getestet wird.</span><span class="sxs-lookup"><span data-stu-id="bf323-122">Typically, this is used to modify a variable that is tested inside the **Condition** part of the statement.</span></span>

<span data-ttu-id="bf323-123">Der Platzhalter der **Anweisungs Liste** stellt einen Satz von mindestens einem Befehl dar, der jedes Mal ausgeführt wird, wenn die Schleife eingegeben oder wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="bf323-123">The **Statement list** placeholder represents a set of one or more commands that are run each time the loop is entered or repeated.</span></span> <span data-ttu-id="bf323-124">Der Inhalt der **Anweisungs Liste** wird durch geschweifte Klammern eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bf323-124">The contents of the **Statement list** are surrounded by braces.</span></span>

### <a name="support-for-multiple-operations"></a><span data-ttu-id="bf323-125">Unterstützung für mehrere Vorgänge</span><span class="sxs-lookup"><span data-stu-id="bf323-125">Support for multiple operations</span></span>

<span data-ttu-id="bf323-126">Die folgenden Syntaxen werden für mehrere Zuweisungs Vorgänge in der **Init** -Anweisung unterstützt:</span><span class="sxs-lookup"><span data-stu-id="bf323-126">The following syntaxes are supported for multiple assignment operations in the **Init** statement:</span></span>

```powershell
# Comma separated assignment expressions enclosed in parenthesis.
for (($i = 0), ($j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}

# Sub-expression using the semicolon to separate statements.
for ($($i = 0;$j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}
```

<span data-ttu-id="bf323-127">Die folgenden Syntaxen werden bei mehreren Zuweisungs Vorgängen in der **Repeat** -Anweisung unterstützt:</span><span class="sxs-lookup"><span data-stu-id="bf323-127">The following syntaxes are supported for multiple assignment operations in the **Repeat** statement:</span></span>

```powershell
# Comma separated assignment expressions.
for (($i = 0), ($j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}

# Comma separated assignment expressions enclosed in parenthesis.
for (($i = 0), ($j = 0); $i -lt 10; ($i++), ($j++))
{
    "`$i:$i"
    "`$j:$j"
}

# Sub-expression using the semicolon to separate statements.
for ($($i = 0;$j = 0); $i -lt 10; $($i++;$j++))
{
    "`$i:$i"
    "`$j:$j"
}
```

> [!NOTE]
> <span data-ttu-id="bf323-128">Andere Vorgänge als Pre-oder Post-Inkrement funktionieren möglicherweise nicht für alle Syntaxen.</span><span class="sxs-lookup"><span data-stu-id="bf323-128">Operations other than pre or post increment may not work with all syntaxes.</span></span>

<span data-ttu-id="bf323-129">Verwenden Sie für mehrere **Bedingungen** logische Operatoren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf323-129">For multiple **Conditions** use logical operators as demonstrated by the following example.</span></span>

```powershell
for (($i = 0), ($j = 0); $i -lt 10 -and $j -lt 10; $i++,$j++)
{
    "`$i:$i"
    "`$j:$j"
}
```

<span data-ttu-id="bf323-130">Weitere Informationen finden Sie unter [about_Logical_Operators](about_Logical_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="bf323-130">For more information, see [about_Logical_Operators](about_Logical_Operators.md).</span></span>

### <a name="examples"></a><span data-ttu-id="bf323-131">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bf323-131">Examples</span></span>

<span data-ttu-id="bf323-132">Eine- `For` Anweisung erfordert mindestens die Klammer, die die Initialisierungs **Init** -, Bedingungs-und **Wiederholungs** Teile der Anweisung umgibt, sowie einen Befehl, der von geschweiften Klammern im **Anweisungs Listen** Teil der Anweisung umgeben **ist**.</span><span class="sxs-lookup"><span data-stu-id="bf323-132">At a minimum, a `For` statement requires the parenthesis surrounding the **Init** , **Condition** , and **Repeat** part of the statement and a command surrounded by braces in the **Statement list** part of the statement.</span></span>

<span data-ttu-id="bf323-133">Beachten Sie, dass in den bevorstehenden Beispielen absichtlich Code außerhalb der-Anweisung angezeigt wird `For` .</span><span class="sxs-lookup"><span data-stu-id="bf323-133">Note that the upcoming examples intentionally show code outside the `For` statement.</span></span> <span data-ttu-id="bf323-134">In späteren Beispielen ist Code in die- `For` Anweisung integriert.</span><span class="sxs-lookup"><span data-stu-id="bf323-134">In later examples, code is integrated into the `For` statement.</span></span>

<span data-ttu-id="bf323-135">Beispielsweise zeigt die folgende `For` Anweisung den Wert der Variablen kontinuierlich an, `$i` bis Sie den Befehl manuell verlassen, indem Sie STRG + C drücken.</span><span class="sxs-lookup"><span data-stu-id="bf323-135">For example, the following `For` statement continually displays the value of the `$i` variable until you manually break out of the command by pressing CTRL+C.</span></span>

```powershell
$i = 1
for (;;)
{
    Write-Host $i
}
```

<span data-ttu-id="bf323-136">Sie können der Anweisungs Liste zusätzliche Befehle hinzufügen, sodass der Wert von `$i` bei jedem Ausführen der Schleife um 1 erhöht wird, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf323-136">You can add additional commands to the statement list so that the value of `$i` is incremented by 1 each time the loop is run, as the following example shows.</span></span>

```powershell
for (;;)
{
    $i++; Write-Host $i
}
```

<span data-ttu-id="bf323-137">Bis Sie den Befehl durch Drücken von STRG + C verlassen, zeigt diese Anweisung fortlaufend den Wert der Variablen an, `$i` da Sie bei jedem Ausführen der Schleife um 1 erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="bf323-137">Until you break out of the command by pressing CTRL+C, this statement will continually display the value of the `$i` variable as it is incremented by 1 each time the loop is run.</span></span>

<span data-ttu-id="bf323-138">Anstatt den Wert der Variablen im Anweisungs Listen Teil der Anweisung zu ändern `For` , können Sie stattdessen den **Wiederholungs** Teil der `For` Anweisung wie folgt verwenden.</span><span class="sxs-lookup"><span data-stu-id="bf323-138">Rather than change the value of the variable in the statement list part of the `For` statement, you can use the **Repeat** portion of the `For` statement instead, as follows.</span></span>

```powershell
$i=1
for (;;$i++)
{
    Write-Host $i
}
```

<span data-ttu-id="bf323-139">Diese Anweisung wird nach wie vor unbegrenzt wiederholt, bis Sie den Befehl durch Drücken von STRG + C aufbrechen.</span><span class="sxs-lookup"><span data-stu-id="bf323-139">This statement will still repeat indefinitely until you break out of the command by pressing CTRL+C.</span></span>

<span data-ttu-id="bf323-140">Sie können die `For` Schleife mit einer *Bedingung* beenden.</span><span class="sxs-lookup"><span data-stu-id="bf323-140">You can terminate the `For` loop using a *condition*.</span></span> <span data-ttu-id="bf323-141">Sie können **eine Bedingung mithilfe des Bedingungs Teils der** Anweisung platzieren `For` .</span><span class="sxs-lookup"><span data-stu-id="bf323-141">You can place a condition using the **Condition** portion of the `For` statement.</span></span> <span data-ttu-id="bf323-142">Die- `For` Schleife wird beendet, wenn die Bedingung als ausgewertet wird `$false` .</span><span class="sxs-lookup"><span data-stu-id="bf323-142">The `For` loop terminates when the condition evaluates to `$false`.</span></span>

<span data-ttu-id="bf323-143">Im folgenden Beispiel wird die- `For` Schleife ausgeführt, während der Wert von `$i` kleiner oder gleich 10 ist.</span><span class="sxs-lookup"><span data-stu-id="bf323-143">In the following example, the `For` loop runs while the value of `$i` is less than or equal to 10.</span></span>

```powershell
$i=1
for(;$i -le 10;$i++)
{
    Write-Host $i
}
```

<span data-ttu-id="bf323-144">Anstatt die Variable außerhalb der-Anweisung zu erstellen und `For` zu initialisieren, können Sie diese Aufgabe innerhalb der-Schleife ausführen, `For` indem Sie den **Init** -Teil der- `For` Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="bf323-144">Instead of creating and initializing the variable outside the `For` statement, you can perform this task inside the `For` loop by using the **Init** portion of the `For` statement.</span></span>

```powershell
for($i=1; $i -le 10; $i++){Write-Host $i}
```

<span data-ttu-id="bf323-145">Sie können Wagen Rückläufe anstelle von Semikolons verwenden, um die **Init** -, **Condition** -und **Repeat** -Teile der Anweisung zu begrenzen `For` .</span><span class="sxs-lookup"><span data-stu-id="bf323-145">You can use carriage returns instead of semicolons to delimit the **Init** , **Condition** , and **Repeat** portions of the `For` statement.</span></span> <span data-ttu-id="bf323-146">Das folgende Beispiel zeigt einen `For` , der diese alternative Syntax verwendet.</span><span class="sxs-lookup"><span data-stu-id="bf323-146">The following example shows a `For` that uses this alternative syntax.</span></span>

```powershell
for ($i = 0
  $i -lt 10
  $i++){
  $i
}
```

<span data-ttu-id="bf323-147">Diese alternative Form der `For` -Anweisung funktioniert in PowerShell-Skriptdateien und an der PowerShell-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="bf323-147">This alternative form of the `For` statement works in PowerShell script files and at the PowerShell command prompt.</span></span> <span data-ttu-id="bf323-148">Es ist jedoch einfacher, die `For` Anweisungs Syntax mit Semikolons zu verwenden, wenn Sie interaktive Befehle an der Eingabeaufforderung eingeben.</span><span class="sxs-lookup"><span data-stu-id="bf323-148">However, it is easier to use the `For` statement syntax with semicolons when you enter interactive commands at the command prompt.</span></span>

<span data-ttu-id="bf323-149">Die- `For` Schleife ist flexibler als die- `Foreach` Schleife, da Sie das Inkrement von Werten in einem Array oder einer Auflistung mithilfe von Mustern ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="bf323-149">The `For` loop is more flexible than the `Foreach` loop because it allows you to increment values in an array or collection by using patterns.</span></span> <span data-ttu-id="bf323-150">Im folgenden Beispiel wird die- `$i` Variable im **Wiederholungs** Abschnitt der-Anweisung um 2 erhöht `For` .</span><span class="sxs-lookup"><span data-stu-id="bf323-150">In the following example, the `$i` variable is incremented by 2 in the **Repeat** portion of the `For` statement.</span></span>

```powershell
for ($i = 0; $i -le 20; $i += 2)
{
    Write-Host $i
}
```

<span data-ttu-id="bf323-151">Die- `For` Schleife kann auch in einer Zeile geschrieben werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf323-151">The `For` loop can also be written on one line as in the following example.</span></span>

```powershell
for ($i = 0; $i -lt 10; $i++) { Write-Host $i }
```

## <a name="see-also"></a><span data-ttu-id="bf323-152">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="bf323-152">SEE ALSO</span></span>

[<span data-ttu-id="bf323-153">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="bf323-153">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="bf323-154">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="bf323-154">about_Foreach</span></span>](about_Foreach.md)
