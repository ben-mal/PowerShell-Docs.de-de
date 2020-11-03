---
description: Beschreibt, wie PowerShell Befehle analysiert.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parsing?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parsing
ms.openlocfilehash: d7b5af8c94ad6370c69773d2bc3796bace60ef7c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223359"
---
# <a name="about-parsing"></a><span data-ttu-id="b8836-104">Informationen zur-Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="b8836-104">About Parsing</span></span>

## <a name="short-description"></a><span data-ttu-id="b8836-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b8836-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="b8836-106">Beschreibt, wie PowerShell Befehle analysiert.</span><span class="sxs-lookup"><span data-stu-id="b8836-106">Describes how PowerShell parses commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="b8836-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b8836-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="b8836-108">Wenn Sie einen Befehl an der Eingabeaufforderung eingeben, unterbricht PowerShell den Befehls Text in eine Reihe von Segmenten, die als _Token_ bezeichnet werden, und bestimmt dann, wie die einzelnen Token interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="b8836-108">When you enter a command at the command prompt, PowerShell breaks the command text into a series of segments called _tokens_ and then determines how to interpret each token.</span></span>

<span data-ttu-id="b8836-109">Wenn Sie z. b. Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="b8836-109">For example, if you type:</span></span>

```powershell
Write-Host book
```

<span data-ttu-id="b8836-110">PowerShell unterbricht den Befehl in zwei Token `Write-Host` `book` : und, und interpretiert jedes Token unabhängig mithilfe eines der folgenden zwei wichtigen Analyse-Modi: Ausdrucks Modus und Argument Modus.</span><span class="sxs-lookup"><span data-stu-id="b8836-110">PowerShell breaks the command into two tokens, `Write-Host` and `book`, and interprets each token independently using one of two major parsing modes: expression mode and argument mode.</span></span>

> [!NOTE]
> <span data-ttu-id="b8836-111">Wenn PowerShell Befehlseingaben analysiert, versucht es, die Befehlsnamen in Cmdlets oder systemeigene ausführbare Dateien aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="b8836-111">As PowerShell parses command input it tries to resolve the command names to cmdlets or native executables.</span></span> <span data-ttu-id="b8836-112">Wenn ein Befehls Name keine genaue Entsprechung hat, wird `Get-` der Befehl von PowerShell als Standard Verb vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="b8836-112">If a command name does not have an exact match, PowerShell prepends `Get-` to the command as a default verb.</span></span> <span data-ttu-id="b8836-113">Beispielsweise wird von PowerShell `Process` als analysiert `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="b8836-113">For example, PowerShell parses `Process` as `Get-Process`.</span></span> <span data-ttu-id="b8836-114">Es wird nicht empfohlen, dieses Feature aus den folgenden Gründen zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="b8836-114">It's not recommended to use this feature for the following reasons:</span></span>
>
> - <span data-ttu-id="b8836-115">Es ist ineffizient.</span><span class="sxs-lookup"><span data-stu-id="b8836-115">It's inefficient.</span></span> <span data-ttu-id="b8836-116">Dies bewirkt, dass PowerShell mehrmals durchsucht wird.</span><span class="sxs-lookup"><span data-stu-id="b8836-116">This causes PowerShell to search multiple times.</span></span>
> - <span data-ttu-id="b8836-117">Externe Programme mit dem gleichen Namen werden zuerst aufgelöst, sodass Sie das beabsichtigte Cmdlet nicht ausführen können.</span><span class="sxs-lookup"><span data-stu-id="b8836-117">External programs with the same name are resolved first, so you may not execute intended cmdlet.</span></span>
> - <span data-ttu-id="b8836-118">`Get-Help` und `Get-Command` keine Verb losen Namen erkennen.</span><span class="sxs-lookup"><span data-stu-id="b8836-118">`Get-Help` and `Get-Command` don't recognize verb-less names.</span></span>

### <a name="expression-mode"></a><span data-ttu-id="b8836-119">Ausdrucks Modus</span><span class="sxs-lookup"><span data-stu-id="b8836-119">Expression mode</span></span>

<span data-ttu-id="b8836-120">Der Ausdrucks Modus dient zum Kombinieren von Ausdrücken, die für die Bearbeitung von Werten in einer Skriptsprache erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b8836-120">Expression mode is intended for combining expressions, required for value manipulation in a scripting language.</span></span> <span data-ttu-id="b8836-121">Ausdrücke sind Darstellungen von Werten in der PowerShell-Syntax und können einfach oder zusammengesetzt sein, z. b.:</span><span class="sxs-lookup"><span data-stu-id="b8836-121">Expressions are representations of values in PowerShell syntax, and can be simple or composite, for example:</span></span>

<span data-ttu-id="b8836-122">Literale Ausdrücke sind direkte Darstellungen ihrer Werte:</span><span class="sxs-lookup"><span data-stu-id="b8836-122">Literal expressions are direct representations of their values:</span></span>

```powershell
'hello', 32
```

<span data-ttu-id="b8836-123">Variablen Ausdrücke enthalten den Wert der Variablen, auf die Sie verweisen:</span><span class="sxs-lookup"><span data-stu-id="b8836-123">Variable expressions carry the value of the variable they reference:</span></span>

```powershell
$x, $script:path
```

<span data-ttu-id="b8836-124">Operatoren kombinieren andere Ausdrücke zur Auswertung:</span><span class="sxs-lookup"><span data-stu-id="b8836-124">Operators combine other expressions for evaluation:</span></span>

```powershell
- 12, -not $Quiet, 3 + 7, $input.Length -gt 1
```

- <span data-ttu-id="b8836-125">_Zeichen folgen Literale_ müssen in Anführungszeichen stehen.</span><span class="sxs-lookup"><span data-stu-id="b8836-125">_Character string literals_ must be contained in quotation marks.</span></span>
- <span data-ttu-id="b8836-126">_Zahlen_ werden als numerische Werte und nicht als Zeichenfolge behandelt (es sei denn, Sie werden mit Escapezeichen versehen).</span><span class="sxs-lookup"><span data-stu-id="b8836-126">_Numbers_ are treated as numerical values rather than as a series of characters (unless escaped).</span></span>
- <span data-ttu-id="b8836-127">_Operatoren_ , einschließlich unärer Operatoren wie `-` und `-not` und binäre Operatoren wie `+` und `-gt` , werden als Operatoren interpretiert und wenden ihre entsprechenden Vorgänge auf ihre Argumente (Operanden) an.</span><span class="sxs-lookup"><span data-stu-id="b8836-127">_Operators_ , including unary operators like `-` and `-not` and binary operators like `+` and `-gt`, are interpreted as operators and apply their respective operations on their arguments (operands).</span></span>
- <span data-ttu-id="b8836-128">_Attribut-und Konvertierungs Ausdrücke_ werden als Ausdrücke analysiert und auf untergeordnete Ausdrücke angewendet, z. b. `[int] '7'` .</span><span class="sxs-lookup"><span data-stu-id="b8836-128">_Attribute and conversion expressions_ are parsed as expressions and applied to subordinate expressions, e.g. `[int] '7'`.</span></span>
- <span data-ttu-id="b8836-129">_Variablen Verweise_ werden auf ihre Werte ausgewertet, aber _Verteilung_ (d. h. vorgefüllte Parametersätze einfügen) ist unzulässig und verursacht einen Parserfehler.</span><span class="sxs-lookup"><span data-stu-id="b8836-129">_Variable references_ are evaluated to their values but _splatting_ (i.e. pasting prefilled parameter sets) is forbidden and causes a parser error.</span></span>
- <span data-ttu-id="b8836-130">Alles andere wird als Befehl behandelt, der aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b8836-130">Anything else will be treated as a command to be invoked.</span></span>

### <a name="argument-mode"></a><span data-ttu-id="b8836-131">Argument Modus</span><span class="sxs-lookup"><span data-stu-id="b8836-131">Argument mode</span></span>

<span data-ttu-id="b8836-132">Beim Analysieren prüft PowerShell zunächst, dass die Eingabe als Ausdruck interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="b8836-132">When parsing, PowerShell first looks to interpret input as an expression.</span></span> <span data-ttu-id="b8836-133">Wenn jedoch ein Befehls Aufruf auftritt, wird die Analyse im Argument Modus fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="b8836-133">But when a command invocation is encountered, parsing continues in argument mode.</span></span>

<span data-ttu-id="b8836-134">Der Argument Modus ist für das Parsen von Argumenten und Parametern für Befehle in einer Shellumgebung konzipiert.</span><span class="sxs-lookup"><span data-stu-id="b8836-134">Argument mode is designed for parsing arguments and parameters for commands in a shell environment.</span></span> <span data-ttu-id="b8836-135">Alle Eingaben werden als erweiterbare Zeichenfolge behandelt, es sei denn, Sie verwendet eine der folgenden Syntaxen:</span><span class="sxs-lookup"><span data-stu-id="b8836-135">All input is treated as an expandable string unless it uses one of the following syntaxes:</span></span>

- <span data-ttu-id="b8836-136">Das Dollar Zeichen ( `$` ) beginnt einen Variablen Verweis (nur, wenn ein gültiger Variablenname folgt, andernfalls wird er als Teil der erweiterbaren Zeichenfolge interpretiert).</span><span class="sxs-lookup"><span data-stu-id="b8836-136">Dollar sign (`$`) begins a variable reference (only if it is followed by a valid variable name, otherwise it is interpreted as part of the expandable string).</span></span>
- <span data-ttu-id="b8836-137">Anführungszeichen ( `'` und `"` ) Zeichen folgen Werte</span><span class="sxs-lookup"><span data-stu-id="b8836-137">Quotation marks (`'` and `"`) begin string values</span></span>
- <span data-ttu-id="b8836-138">Mit Klammern ( `(` und `)` ) werden neue Ausdrücke abgegrenzt.</span><span class="sxs-lookup"><span data-stu-id="b8836-138">Parentheses (`(` and `)`) demarcate new expressions.</span></span>
- <span data-ttu-id="b8836-139">Der subexpression-Operator ( `$(` ... `)` ) entfernt eingebettete Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="b8836-139">Subexpression operator (`$(`…`)`) demarcates embedded expressions.</span></span>
- <span data-ttu-id="b8836-140">Geschweifte Klammern ( `{` und `}` ) setzen neue Skriptblöcke um.</span><span class="sxs-lookup"><span data-stu-id="b8836-140">Braces (`{` and `}`) demarcate new script blocks.</span></span>
- <span data-ttu-id="b8836-141">Das anfängliche at-Zeichen ( `@` ) beginnt Ausdrucks Syntaxen, z. b. Verteilung ( `@args` ), Arrays ( `@(1,2,3)` ) und Hash Tabellen ( `@{a=1;b=2}` ).</span><span class="sxs-lookup"><span data-stu-id="b8836-141">Initial at sign (`@`) begins expression syntaxes such as splatting (`@args`), arrays (`@(1,2,3)`) and hash tables (`@{a=1;b=2}`).</span></span>
- <span data-ttu-id="b8836-142">Kommas ( `,` ) führen Listen ein, die als Arrays übergebenen werden, es sei denn, der aufzurufende Befehl ist eine native Anwendung. in diesem Fall werden Sie als Teil der erweiterbaren Zeichenfolge interpretiert.</span><span class="sxs-lookup"><span data-stu-id="b8836-142">Commas (`,`) introduce lists passed as arrays, except when the command to be called is a native application, in which case they are interpreted as part of the expandable string.</span></span> <span data-ttu-id="b8836-143">Anfängliche, aufeinander folgende oder nachfolgende Kommas werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b8836-143">Initial, consecutive or trailing commas are not supported.</span></span>

<span data-ttu-id="b8836-144">Werte eingebetteter Ausdrücke werden in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="b8836-144">Values of embedded expressions are converted to strings.</span></span>

<span data-ttu-id="b8836-145">Die folgende Tabelle enthält einige Beispiele für Werte, die im Ausdrucks Modus und im Argument Modus verarbeitet werden, sowie für die Auswertung dieser Werte.</span><span class="sxs-lookup"><span data-stu-id="b8836-145">The following table provides several examples of values processed in expression mode and argument mode and the evaluation of those values.</span></span> <span data-ttu-id="b8836-146">Wir gehen davon aus, dass der Wert der-Variablen `a` ist `4` .</span><span class="sxs-lookup"><span data-stu-id="b8836-146">We assume that the value of the variable `a` is `4`.</span></span>

|       <span data-ttu-id="b8836-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8836-147">Example</span></span>        |    <span data-ttu-id="b8836-148">Mode</span><span class="sxs-lookup"><span data-stu-id="b8836-148">Mode</span></span>    |      <span data-ttu-id="b8836-149">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="b8836-149">Result</span></span>       |
| -------------------- | ---------- | ----------------- |
| `2`                  | <span data-ttu-id="b8836-150">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b8836-150">Expression</span></span> | <span data-ttu-id="b8836-151">2 (ganze Zahl)</span><span class="sxs-lookup"><span data-stu-id="b8836-151">2 (integer)</span></span>       |
| `` `2``              | <span data-ttu-id="b8836-152">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b8836-152">Expression</span></span> | <span data-ttu-id="b8836-153">"2" (Befehl)</span><span class="sxs-lookup"><span data-stu-id="b8836-153">"2" (command)</span></span>     |
| `echo 2`             | <span data-ttu-id="b8836-154">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b8836-154">Expression</span></span> | <span data-ttu-id="b8836-155">2 (ganze Zahl)</span><span class="sxs-lookup"><span data-stu-id="b8836-155">2 (integer)</span></span>       |
| `2+2`                | <span data-ttu-id="b8836-156">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b8836-156">Expression</span></span> | <span data-ttu-id="b8836-157">4 (ganze Zahl)</span><span class="sxs-lookup"><span data-stu-id="b8836-157">4 (integer)</span></span>       |
| `echo 2+2`           | <span data-ttu-id="b8836-158">Argument</span><span class="sxs-lookup"><span data-stu-id="b8836-158">Argument</span></span>   | <span data-ttu-id="b8836-159">"2 + 2" (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b8836-159">"2+2" (string)</span></span>    |
| `echo(2+2)`          | <span data-ttu-id="b8836-160">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b8836-160">Expression</span></span> | <span data-ttu-id="b8836-161">4 (ganze Zahl)</span><span class="sxs-lookup"><span data-stu-id="b8836-161">4 (integer)</span></span>       |
| `$a`                 | <span data-ttu-id="b8836-162">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b8836-162">Expression</span></span> | <span data-ttu-id="b8836-163">4 (ganze Zahl)</span><span class="sxs-lookup"><span data-stu-id="b8836-163">4 (integer)</span></span>       |
| `echo $a`            | <span data-ttu-id="b8836-164">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b8836-164">Expression</span></span> | <span data-ttu-id="b8836-165">4 (ganze Zahl)</span><span class="sxs-lookup"><span data-stu-id="b8836-165">4 (integer)</span></span>       |
| `$a+2`               | <span data-ttu-id="b8836-166">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b8836-166">Expression</span></span> | <span data-ttu-id="b8836-167">6 (ganze Zahl)</span><span class="sxs-lookup"><span data-stu-id="b8836-167">6 (integer)</span></span>       |
| `echo $a+2`          | <span data-ttu-id="b8836-168">Argument</span><span class="sxs-lookup"><span data-stu-id="b8836-168">Argument</span></span>   | <span data-ttu-id="b8836-169">4 + 2 (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b8836-169">4+2 (string)</span></span>      |
| `$-`                 | <span data-ttu-id="b8836-170">Argument</span><span class="sxs-lookup"><span data-stu-id="b8836-170">Argument</span></span>   | <span data-ttu-id="b8836-171">"$-" (Befehl)</span><span class="sxs-lookup"><span data-stu-id="b8836-171">"$-" (command)</span></span>    |
| `echo $-`            | <span data-ttu-id="b8836-172">Argument</span><span class="sxs-lookup"><span data-stu-id="b8836-172">Argument</span></span>   | <span data-ttu-id="b8836-173">"$-" (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b8836-173">"$-" (string)</span></span>     |
| `a$a`                | <span data-ttu-id="b8836-174">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b8836-174">Expression</span></span> | <span data-ttu-id="b8836-175">"a $ a" (Befehl)</span><span class="sxs-lookup"><span data-stu-id="b8836-175">"a$a" (command)</span></span>   |
| `echo a$a`           | <span data-ttu-id="b8836-176">Argument</span><span class="sxs-lookup"><span data-stu-id="b8836-176">Argument</span></span>   | <span data-ttu-id="b8836-177">"A4" (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b8836-177">"a4" (string)</span></span>     |
| `a'$a'`              | <span data-ttu-id="b8836-178">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b8836-178">Expression</span></span> | <span data-ttu-id="b8836-179">"a $ a" (Befehl)</span><span class="sxs-lookup"><span data-stu-id="b8836-179">"a$a" (command)</span></span>   |
| `echo a'$a'`         | <span data-ttu-id="b8836-180">Argument</span><span class="sxs-lookup"><span data-stu-id="b8836-180">Argument</span></span>   | <span data-ttu-id="b8836-181">"a $ a" (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b8836-181">"a$a" (string)</span></span>    |
| `a"$a"`              | <span data-ttu-id="b8836-182">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b8836-182">Expression</span></span> | <span data-ttu-id="b8836-183">"a $ a" (Befehl)</span><span class="sxs-lookup"><span data-stu-id="b8836-183">"a$a" (command)</span></span>   |
| `echo a"$a"`         | <span data-ttu-id="b8836-184">Argument</span><span class="sxs-lookup"><span data-stu-id="b8836-184">Argument</span></span>   | <span data-ttu-id="b8836-185">"A4" (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b8836-185">"a4" (string)</span></span>     |
| `a$(2)`              | <span data-ttu-id="b8836-186">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b8836-186">Expression</span></span> | <span data-ttu-id="b8836-187">"a $ (2)" (Befehl)</span><span class="sxs-lookup"><span data-stu-id="b8836-187">"a$(2)" (command)</span></span> |
| `echo a$(2)`         | <span data-ttu-id="b8836-188">Argument</span><span class="sxs-lookup"><span data-stu-id="b8836-188">Argument</span></span>   | <span data-ttu-id="b8836-189">"a2" (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b8836-189">"a2" (string)</span></span>     |

<span data-ttu-id="b8836-190">Jedes Token kann als Objekttyp, z. b. boolescher Wert oder Zeichenfolge, interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="b8836-190">Every token can be interpreted as some kind of object type, such as Boolean or string.</span></span> <span data-ttu-id="b8836-191">PowerShell versucht, den Objekttyp aus dem Ausdruck zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="b8836-191">PowerShell attempts to determine the object type from the expression.</span></span>
<span data-ttu-id="b8836-192">Der Objekttyp hängt vom Typ des Parameters ab, den ein Befehl erwartet, und darüber, ob PowerShell weiß, wie das Argument in den richtigen Typ konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b8836-192">The object type depends on the type of parameter a command expects and on whether PowerShell knows how to convert the argument to the correct type.</span></span> <span data-ttu-id="b8836-193">In der folgenden Tabelle sind einige Beispiele für die Typen aufgeführt, die von den Ausdrücken zurückgegebenen Werten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b8836-193">The following table shows several examples of the types assigned to values returned by the expressions.</span></span>

|       <span data-ttu-id="b8836-194">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8836-194">Example</span></span>          |    <span data-ttu-id="b8836-195">Mode</span><span class="sxs-lookup"><span data-stu-id="b8836-195">Mode</span></span>    |     <span data-ttu-id="b8836-196">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="b8836-196">Result</span></span>      |
| ---------------------- | ---------- | --------------- |
| `Write-Output !1`      | <span data-ttu-id="b8836-197">Argument</span><span class="sxs-lookup"><span data-stu-id="b8836-197">argument</span></span>   | <span data-ttu-id="b8836-198">"! 1" (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b8836-198">"!1" (string)</span></span>   |
| `Write-Output (!1)`    | <span data-ttu-id="b8836-199">expression</span><span class="sxs-lookup"><span data-stu-id="b8836-199">expression</span></span> | <span data-ttu-id="b8836-200">False (Boolean)</span><span class="sxs-lookup"><span data-stu-id="b8836-200">False (Boolean)</span></span> |
| `Write-Output (2)`     | <span data-ttu-id="b8836-201">expression</span><span class="sxs-lookup"><span data-stu-id="b8836-201">expression</span></span> | <span data-ttu-id="b8836-202">2 (ganze Zahl)</span><span class="sxs-lookup"><span data-stu-id="b8836-202">2 (integer)</span></span>     |
| `Set-Variable AB A,B`  | <span data-ttu-id="b8836-203">Argument</span><span class="sxs-lookup"><span data-stu-id="b8836-203">argument</span></span>   | <span data-ttu-id="b8836-204">"A", "B" (Array)</span><span class="sxs-lookup"><span data-stu-id="b8836-204">'A','B' (array)</span></span> |
| `CMD /CECHO A,B`       | <span data-ttu-id="b8836-205">Argument</span><span class="sxs-lookup"><span data-stu-id="b8836-205">argument</span></span>   | <span data-ttu-id="b8836-206">"A, B" (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b8836-206">'A,B' (string)</span></span>  |
| `CMD /CECHO $AB`       | <span data-ttu-id="b8836-207">expression</span><span class="sxs-lookup"><span data-stu-id="b8836-207">expression</span></span> | <span data-ttu-id="b8836-208">"A", "B" (Array)</span><span class="sxs-lookup"><span data-stu-id="b8836-208">'A','B' (array)</span></span> |
| `CMD /CECHO :$AB`      | <span data-ttu-id="b8836-209">Argument</span><span class="sxs-lookup"><span data-stu-id="b8836-209">argument</span></span>   | <span data-ttu-id="b8836-210">': A B ' (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b8836-210">':A B' (string)</span></span> |

<span data-ttu-id="b8836-211">Das `--%` in PowerShell 3,0 eingeführte Symbol für die Beendigung der Ausführung () weist PowerShell an, die Eingaben nicht als PowerShell-Befehle oder-Ausdrücke zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="b8836-211">The stop-parsing symbol (`--%`), introduced in PowerShell 3.0, directs PowerShell to refrain from interpreting input as PowerShell commands or expressions.</span></span>

<span data-ttu-id="b8836-212">Wenn Sie ein ausführbares Programm in PowerShell aufrufen, platzieren Sie das Symbol für die Beendigung der Programmierung vor den Programm Argumenten.</span><span class="sxs-lookup"><span data-stu-id="b8836-212">When calling an executable program in PowerShell, place the stop-parsing symbol before the program arguments.</span></span> <span data-ttu-id="b8836-213">Diese Methode ist viel einfacher als die Verwendung von Escapezeichen, um eine Fehlinterpretation zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="b8836-213">This technique is much easier than using escape characters to prevent misinterpretation.</span></span>

<span data-ttu-id="b8836-214">Wenn ein Symbol für die Beendigung gefunden wird, behandelt PowerShell die restlichen Zeichen in der Zeile als Literalzeichen.</span><span class="sxs-lookup"><span data-stu-id="b8836-214">When it encounters a stop-parsing symbol, PowerShell treats the remaining characters in the line as a literal.</span></span> <span data-ttu-id="b8836-215">Die einzige Interpretation besteht darin, Werte für Umgebungsvariablen zu ersetzen, die eine standardmäßige Windows-Notation verwenden, z `%USERPROFILE%` . b..</span><span class="sxs-lookup"><span data-stu-id="b8836-215">The only interpretation it performs is to substitute values for environment variables that use standard Windows notation, such as `%USERPROFILE%`.</span></span>

<span data-ttu-id="b8836-216">Das Symbol für die Beendigung der Ausführung wird nur bis zum nächsten Zeilen-oder Pipeline Zeichen wirksam.</span><span class="sxs-lookup"><span data-stu-id="b8836-216">The stop-parsing symbol is effective only until the next newline or pipeline character.</span></span> <span data-ttu-id="b8836-217">Sie können kein Fortsetzungs Zeichen ( `` ` `` ) verwenden, um den Effekt zu erweitern, oder ein Befehls Trennzeichen ( `;` ) verwenden, um den Effekt zu beenden.</span><span class="sxs-lookup"><span data-stu-id="b8836-217">You cannot use a continuation character (`` ` ``) to extend its effect or use a command delimiter (`;`) to terminate its effect.</span></span>

<span data-ttu-id="b8836-218">Der folgende Befehl ruft beispielsweise das **icacls** -Programm auf.</span><span class="sxs-lookup"><span data-stu-id="b8836-218">For example, the following command calls the **Icacls** program.</span></span>

```powershell
icacls X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="b8836-219">Zum Ausführen dieses Befehls in PowerShell 2,0 müssen Sie Escapezeichen verwenden, um zu verhindern, dass PowerShell die Klammern falsch interpretiert.</span><span class="sxs-lookup"><span data-stu-id="b8836-219">To run this command in PowerShell 2.0, you must use escape characters to prevent PowerShell from misinterpreting the parentheses.</span></span>

```powershell
icacls X:\VMS /grant Dom\HVAdmin:`(CI`)`(OI`)F
```

<span data-ttu-id="b8836-220">Ab PowerShell 3,0 können Sie das Symbol für die Beendigung der Ausführung verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8836-220">Beginning in PowerShell 3.0, you can use the stop-parsing symbol.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="b8836-221">PowerShell sendet die folgende Befehls Zeichenfolge an das **icacls** -Programm:</span><span class="sxs-lookup"><span data-stu-id="b8836-221">PowerShell sends the following command string to the **Icacls** program:</span></span>

`X:\VMS /grant Dom\HVAdmin:(CI)(OI)F`

## <a name="see-also"></a><span data-ttu-id="b8836-222">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="b8836-222">SEE ALSO</span></span>

[<span data-ttu-id="b8836-223">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="b8836-223">about_Command_Syntax</span></span>](about_Command_Syntax.md)
