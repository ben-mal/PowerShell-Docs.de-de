---
description: Beschreibt eine-Anweisung, die Sie zum sofortigen Beenden von-,-,-,-oder-Anweisungen verwenden können `foreach` `for` `while` `do` `switch` `trap` .
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_break?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Break
ms.openlocfilehash: 3c418f5bae11f957880c8b53ee0bcf2fb44515ee
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604863"
---
# <a name="about-break"></a><span data-ttu-id="a994b-103">Info zur Pause</span><span class="sxs-lookup"><span data-stu-id="a994b-103">About Break</span></span>

## <a name="short-description"></a><span data-ttu-id="a994b-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a994b-104">Short description</span></span>

<span data-ttu-id="a994b-105">Beschreibt eine-Anweisung, die Sie zum sofortigen Beenden von-,-,-,-oder-Anweisungen verwenden können `foreach` `for` `while` `do` `switch` `trap` .</span><span class="sxs-lookup"><span data-stu-id="a994b-105">Describes a statement you can use to immediately exit `foreach`, `for`, `while`, `do`, `switch`, or `trap` statements.</span></span>

## <a name="long-description"></a><span data-ttu-id="a994b-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a994b-106">Long description</span></span>

<span data-ttu-id="a994b-107">Die- `break` Anweisung bietet eine Möglichkeit, den aktuellen Kontroll Block zu beenden.</span><span class="sxs-lookup"><span data-stu-id="a994b-107">The `break` statement provides a way to exit the current control block.</span></span>
<span data-ttu-id="a994b-108">Die Ausführung wird bei der nächsten Anweisung nach dem Kontroll Block fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a994b-108">Execution continues at the next statement after the control block.</span></span> <span data-ttu-id="a994b-109">Die-Anweisung unterstützt Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="a994b-109">The statement supports labels.</span></span> <span data-ttu-id="a994b-110">Eine Bezeichnung ist ein Name, den Sie einer Anweisung in einem Skript zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a994b-110">A label is a name you assign to a statement in a script.</span></span>

## <a name="using-break-in-loops"></a><span data-ttu-id="a994b-111">Verwenden von Break in-Schleifen</span><span class="sxs-lookup"><span data-stu-id="a994b-111">Using break in loops</span></span>

<span data-ttu-id="a994b-112">Wenn eine- `break` Anweisung in einer-Schleife, z. b. einer-,-,-oder-Schleife, angezeigt `foreach` `for` `do` `while` wird, beendet PowerShell sofort die Schleife.</span><span class="sxs-lookup"><span data-stu-id="a994b-112">When a `break` statement appears in a loop, such as a `foreach`, `for`, `do`, or `while` loop, PowerShell immediately exits the loop.</span></span>

<span data-ttu-id="a994b-113">Eine- `break` Anweisung kann eine Bezeichnung enthalten, mit der Sie eingebettete Schleifen beenden können.</span><span class="sxs-lookup"><span data-stu-id="a994b-113">A `break` statement can include a label that lets you exit embedded loops.</span></span> <span data-ttu-id="a994b-114">Eine Bezeichnung kann ein beliebiges Schleifen Schlüsselwort (z `foreach` `for` . b., oder) `while` in einem Skript angeben.</span><span class="sxs-lookup"><span data-stu-id="a994b-114">A label can specify any loop keyword, such as `foreach`, `for`, or `while`, in a script.</span></span>

<span data-ttu-id="a994b-115">Im folgenden Beispiel wird gezeigt, wie eine-Anweisung verwendet wird `break` , um eine-Anweisung zu beenden `for` :</span><span class="sxs-lookup"><span data-stu-id="a994b-115">The following example shows how to use a `break` statement to exit a `for` statement:</span></span>

```powershell
for($i=1; $i -le 10; $i++) {
   Write-Host $i
   break
}
```

<span data-ttu-id="a994b-116">In diesem Beispiel wird die-Schleife durch die- `break` Anweisung beendet, `for` Wenn die- `$i` Variable 1 ist.</span><span class="sxs-lookup"><span data-stu-id="a994b-116">In this example, the `break` statement exits the `for` loop when the `$i` variable equals 1.</span></span> <span data-ttu-id="a994b-117">Obwohl die- `for` Anweisung zu **true** ausgewertet `$i` wird, bis größer als 10 ist, erreicht PowerShell die Break-Anweisung, wenn die Schleife zum ersten Mal `for` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a994b-117">Even though the `for` statement evaluates to **True** until `$i` is greater than 10, PowerShell reaches the break statement the first time the `for` loop is run.</span></span>

<span data-ttu-id="a994b-118">Häufig wird die-Anweisung in einer-Schleife verwendet, in der `break` eine innere Bedingung erfüllt werden muss.</span><span class="sxs-lookup"><span data-stu-id="a994b-118">It is more common to use the `break` statement in a loop where an inner condition must be met.</span></span> <span data-ttu-id="a994b-119">Beachten Sie das folgende Beispiel für eine `foreach` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="a994b-119">Consider the following `foreach` statement example:</span></span>

```powershell
$i=0
$varB = 10,20,30,40
foreach ($val in $varB) {
  if ($val -eq 30) {
    break
  }
  $i++
}
Write-Host "30 was found in array index $i"
```

<span data-ttu-id="a994b-120">In diesem Beispiel `foreach` iteriert die-Anweisung das `$varB` Array.</span><span class="sxs-lookup"><span data-stu-id="a994b-120">In this example, the `foreach` statement iterates the `$varB` array.</span></span> <span data-ttu-id="a994b-121">Die `if` -Anweisung wird zum ersten Mal als false ausgewertet, und die Variable `$i` wird um 1 erhöht.</span><span class="sxs-lookup"><span data-stu-id="a994b-121">The `if` statement evaluates to False the first two times the loop is run and the variable `$i` is incremented by 1.</span></span> <span data-ttu-id="a994b-122">Der dritte Zeitpunkt, an dem die Schleife ausgeführt wird, `$i` gleich 2 und die `$val` Variable gleich 30.</span><span class="sxs-lookup"><span data-stu-id="a994b-122">The third time the loop is run, `$i` equals 2, and the `$val` variable equals 30.</span></span> <span data-ttu-id="a994b-123">An diesem Punkt wird die `break` -Anweisung ausgeführt, und die- `foreach` Schleife wird beendet.</span><span class="sxs-lookup"><span data-stu-id="a994b-123">At this point, the `break` statement runs, and the `foreach` loop exits.</span></span>

### <a name="using-a-labeled-break-in-a-loop"></a><span data-ttu-id="a994b-124">Verwenden einer beschrifteten Unterbrechung in einer Schleife</span><span class="sxs-lookup"><span data-stu-id="a994b-124">Using a labeled break in a loop</span></span>

<span data-ttu-id="a994b-125">Eine- `break` Anweisung kann eine Bezeichnung enthalten.</span><span class="sxs-lookup"><span data-stu-id="a994b-125">A `break` statement can include a label.</span></span> <span data-ttu-id="a994b-126">Wenn Sie das- `break` Schlüsselwort mit einer Bezeichnung verwenden, beendet PowerShell die bezeichnete Schleife, anstatt die aktuelle Schleife zu beenden.</span><span class="sxs-lookup"><span data-stu-id="a994b-126">If you use the `break` keyword with a label, PowerShell exits the labeled loop instead of exiting the current loop.</span></span>
<span data-ttu-id="a994b-127">Die Bezeichnung ist ein Doppelpunkt, gefolgt von dem Namen, den Sie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a994b-127">The label is a colon followed by a name that you assign.</span></span> <span data-ttu-id="a994b-128">Die Bezeichnung muss das erste Token in einer-Anweisung sein, und es muss das Schleifen Schlüsselwort folgen, z `while` . b..</span><span class="sxs-lookup"><span data-stu-id="a994b-128">The label must be the first token in a statement, and it must be followed by the looping keyword, such as `while`.</span></span>

<span data-ttu-id="a994b-129">`break` Verschiebt die Ausführung aus der gekennzeichneten Schleife.</span><span class="sxs-lookup"><span data-stu-id="a994b-129">`break` moves execution out of the labeled loop.</span></span> <span data-ttu-id="a994b-130">In eingebetteten Schleifen hat dies ein anderes Ergebnis als das- `break` Schlüsselwort, wenn es von sich selbst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a994b-130">In embedded loops, this has a different result than the `break` keyword has when it is used by itself.</span></span> <span data-ttu-id="a994b-131">Dieses Beispiel enthält eine- `while` Anweisung mit einer- `for` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="a994b-131">This example has a `while` statement with a `for` statement:</span></span>

```powershell
:myLabel while (<condition 1>) {
  for ($item in $items) {
    if (<condition 2>) {
      break myLabel
    }
    $item = $x   # A statement inside the For-loop
  }
}
$a = $c  # A statement after the labeled While-loop
```

<span data-ttu-id="a994b-132">Wenn Bedingung 2 als **true** ausgewertet wird, wird die Ausführung des Skripts nach der gekennzeichneten Schleife auf die Anweisung überspringt.</span><span class="sxs-lookup"><span data-stu-id="a994b-132">If condition 2 evaluates to **True**, the execution of the script skips down to the statement after the labeled loop.</span></span> <span data-ttu-id="a994b-133">Im Beispiel beginnt die Ausführung erneut mit der-Anweisung `$a = $c` .</span><span class="sxs-lookup"><span data-stu-id="a994b-133">In the example, execution starts again with the statement `$a = $c`.</span></span>

<span data-ttu-id="a994b-134">Sie können viele bezeichnete Schleifen schachteln, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a994b-134">You can nest many labeled loops, as shown in the following example.</span></span>

```powershell
:red while (<condition1>) {
  :yellow while (<condition2>) {
    while (<condition3>) {
      if ($a) {break}
      if ($b) {break red}
      if ($c) {break yellow}
    }
    Write-Host "After innermost loop"
  }
  Write-Host "After yellow loop"
}
Write-Host "After red loop"
```

<span data-ttu-id="a994b-135">Wenn die `$b` Variable als true ausgewertet wird, wird die Ausführung des Skripts nach der Schleife mit der Bezeichnung "Red" fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a994b-135">If the `$b` variable evaluates to True, execution of the script resumes after the loop that is labeled "red".</span></span> <span data-ttu-id="a994b-136">Wenn die Auswertung der `$c` Variablen true ergibt, wird die Ausführung des Skript Steuer Elements nach der als "gelb" bezeichneten Schleife fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a994b-136">If the `$c` variable evaluates to True, execution of the script control resumes after the loop that is labeled "yellow".</span></span>

<span data-ttu-id="a994b-137">Wenn die `$a` Variable als true ausgewertet wird, wird die Ausführung nach der innersten Schleife fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a994b-137">If the `$a` variable evaluates to True, execution resumes after the innermost loop.</span></span> <span data-ttu-id="a994b-138">Es ist keine Bezeichnung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a994b-138">No label is needed.</span></span>

<span data-ttu-id="a994b-139">PowerShell beschränkt nicht, wie weit Bezeichnungen die Ausführung fortsetzen können.</span><span class="sxs-lookup"><span data-stu-id="a994b-139">PowerShell does not limit how far labels can resume execution.</span></span> <span data-ttu-id="a994b-140">Die Bezeichnung kann sogar die Steuerung über Skript-und Funktionsaufrufe hinweg übergeben.</span><span class="sxs-lookup"><span data-stu-id="a994b-140">The label can even pass control across script and function call boundaries.</span></span>

## <a name="using-break-in-a-switch-statement"></a><span data-ttu-id="a994b-141">Verwenden von Break in einer Switch-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a994b-141">Using break in a switch statement</span></span>

<span data-ttu-id="a994b-142">In einem `switch` Konstrukt bewirkt, dass `break` PowerShell den `switch` Codeblock verlässt.</span><span class="sxs-lookup"><span data-stu-id="a994b-142">In a `switch`construct, `break` causes PowerShell to exit the `switch` code block.</span></span>

<span data-ttu-id="a994b-143">Das- `break` Schlüsselwort wird verwendet, um das-Konstrukt zu verlassen `switch` .</span><span class="sxs-lookup"><span data-stu-id="a994b-143">The `break` keyword is used to leave the `switch` construct.</span></span> <span data-ttu-id="a994b-144">Beispielsweise verwendet die folgende `switch` Anweisung- `break` Anweisungen, um die spezifischsten Bedingungen zu testen:</span><span class="sxs-lookup"><span data-stu-id="a994b-144">For example, the following `switch` statement uses `break` statements to test for the most specific condition:</span></span>

```powershell
$var = "word2"
switch -regex ($var) {
    "word2" {
      Write-Host "Exact" $_
      break
    }

    "word.*" {
      Write-Host "Match on the prefix" $_
      break
    }

    "w.*" {
      Write-Host "Match on at least the first letter" $_
      break
    }

    default {
      Write-Host "No match" $_
      break
    }
}
```

<span data-ttu-id="a994b-145">In diesem Beispiel wird die `$var` -Variable erstellt und mit einem Zeichen folgen Wert initialisiert `word2` .</span><span class="sxs-lookup"><span data-stu-id="a994b-145">In this example, the `$var` variable is created and initialized to a string value of `word2`.</span></span> <span data-ttu-id="a994b-146">Die `switch` Anweisung verwendet die **Regex** -Klasse, um den Variablen Wert zuerst mit dem Begriff abzugleichen `word2` .</span><span class="sxs-lookup"><span data-stu-id="a994b-146">The `switch` statement uses the **Regex** class to match the variable value first with the term `word2`.</span></span> <span data-ttu-id="a994b-147">Da der Variablen Wert und der erste Test in der `switch` Anweisung Stimmen, wird der erste Codeblock in der `switch` Anweisung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a994b-147">Because the variable value and the first test in the `switch` statement match, the first code block in the `switch` statement runs.</span></span>

<span data-ttu-id="a994b-148">Wenn PowerShell die erste `break` Anweisung erreicht, wird die- `switch` Anweisung beendet.</span><span class="sxs-lookup"><span data-stu-id="a994b-148">When PowerShell reaches the first `break` statement, the `switch` statement exits.</span></span> <span data-ttu-id="a994b-149">Wenn die vier `break` Anweisungen aus dem Beispiel entfernt werden, sind alle vier Bedingungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="a994b-149">If the four `break` statements are removed from the example, all four conditions are met.</span></span> <span data-ttu-id="a994b-150">In diesem Beispiel wird die- `break` Anweisung verwendet, um Ergebnisse anzuzeigen, wenn die spezifischsten Bedingungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="a994b-150">This example uses the `break` statement to display results when the most specific condition is met.</span></span>

## <a name="using-break-in-a-trap-statement"></a><span data-ttu-id="a994b-151">Verwenden von Break in einer Trap-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a994b-151">Using break in a trap statement</span></span>

<span data-ttu-id="a994b-152">Wenn die letzte im Text einer-Anweisung ausgeführte Anweisung `trap` ist `break` , wird das Fehler Objekt unterdrückt, und die Ausnahme wird erneut ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a994b-152">If the final statement executed in the body of a `trap` statement is `break`, the error object is suppressed and the exception is re-thrown.</span></span>

<span data-ttu-id="a994b-153">Im folgenden Beispiel wird eine **DivideByZeroException** -Ausnahme erstellt, die mithilfe der-Anweisung eingefangen wird `trap` .</span><span class="sxs-lookup"><span data-stu-id="a994b-153">The following example create a **DivideByZeroException** exception that is trapped using the `trap` statement.</span></span>

```powershell
function test {
  trap [DivideByZeroException] {
    Write-Host 'divide by zero trapped'
    break
  }

  $i = 3
  'Before loop'
  while ($true) {
     "1 / $i = " + (1 / $i--)
  }
  'After loop'
}
test
```

Beachten Sie, dass die Ausführung bei der Ausnahme beendet wird. <span data-ttu-id="a994b-155">Der `After loop` wird niemals erreicht.</span><span class="sxs-lookup"><span data-stu-id="a994b-155">The `After loop` is never reached.</span></span>
<span data-ttu-id="a994b-156">Die Ausnahme wird erneut ausgelöst, nachdem `trap` ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a994b-156">The exception is re-thrown after the `trap` executes.</span></span>

```Output
Before loop
1 / 3 = 0.333333333333333
1 / 2 = 0.5
1 / 1 = 1
divide by zero trapped
ParentContainsErrorRecordException:
Line |
  10 |       "1 / $i = " + (1 / $i--)
     |       ~~~~~~~~~~~~~~~~~~~~~~~~
     | Attempted to divide by zero.
```

## <a name="do-not-use-break-outside-of-a-loop-switch-or-trap"></a><span data-ttu-id="a994b-157">Verwenden Sie keine Unterbrechung außerhalb einer Schleife, eines Schalters oder eines Trap</span><span class="sxs-lookup"><span data-stu-id="a994b-157">Do not use break outside of a loop, switch, or trap</span></span>

<span data-ttu-id="a994b-158">Wenn `break` außerhalb eines Konstrukts verwendet wird, das es direkt unterstützt (Schleifen, `switch` , `trap` ), sucht PowerShell _die-aufrufsstapel_ nach einem einschließenden Konstrukt.</span><span class="sxs-lookup"><span data-stu-id="a994b-158">When `break` is used outside of a construct that directly supports it (loops, `switch`, `trap`), PowerShell looks _up the call stack_ for an enclosing construct.</span></span> <span data-ttu-id="a994b-159">Wenn kein einschließendes Konstrukt gefunden werden kann, wird der aktuelle Runspace ruhig beendet.</span><span class="sxs-lookup"><span data-stu-id="a994b-159">If it can't find an enclosing construct, the current runspace is quietly terminated.</span></span>

<span data-ttu-id="a994b-160">Dies bedeutet, dass Funktionen und Skripts, die versehentlich einen `break` außerhalb eines einschließenden Konstrukts verwenden, das es unterstützt, ihre Aufrufer versehentlich beenden können.</span><span class="sxs-lookup"><span data-stu-id="a994b-160">This means that functions and scripts that inadvertently use a `break` outside of an enclosing construct that supports it can inadvertently terminate their _callers_.</span></span>

<span data-ttu-id="a994b-161">Durch die Verwendung von `break` in einer Pipeline `break` , wie z. b. einem `ForEach-Object` Skriptblock, wird die Pipeline nicht nur beendet, sondern der gesamte Runspace wird möglicherweise beendet.</span><span class="sxs-lookup"><span data-stu-id="a994b-161">Using `break` inside a pipeline `break`, such as a `ForEach-Object` script block, not only exits the pipeline, it potentially terminates the entire runspace.</span></span>

## <a name="see-also"></a><span data-ttu-id="a994b-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a994b-162">See also</span></span>

[<span data-ttu-id="a994b-163">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="a994b-163">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="a994b-164">about_Continue</span><span class="sxs-lookup"><span data-stu-id="a994b-164">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="a994b-165">about_For</span><span class="sxs-lookup"><span data-stu-id="a994b-165">about_For</span></span>](about_For.md)

[<span data-ttu-id="a994b-166">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="a994b-166">about_Foreach</span></span>](about_Foreach.md)

[<span data-ttu-id="a994b-167">about_Switch</span><span class="sxs-lookup"><span data-stu-id="a994b-167">about_Switch</span></span>](about_Switch.md)

[<span data-ttu-id="a994b-168">about_Throw</span><span class="sxs-lookup"><span data-stu-id="a994b-168">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="a994b-169">about_Trap</span><span class="sxs-lookup"><span data-stu-id="a994b-169">about_Trap</span></span>](about_Trap.md)

[<span data-ttu-id="a994b-170">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="a994b-170">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)

[<span data-ttu-id="a994b-171">about_While</span><span class="sxs-lookup"><span data-stu-id="a994b-171">about_While</span></span>](about_While.md)
