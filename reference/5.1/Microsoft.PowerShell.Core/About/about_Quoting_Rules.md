---
description: Beschreibt Regeln für die Verwendung von einfachen und doppelten Anführungszeichen in PowerShell.
Locale: en-US
ms.date: 12/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_quoting_rules?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Quoting_Rules
ms.openlocfilehash: b100ff8ab4be84b7117efc5724119221351ba4bf
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "97490668"
---
# <a name="about-quoting-rules"></a><span data-ttu-id="2dff0-103">Informationen zu Anführungs Regeln</span><span class="sxs-lookup"><span data-stu-id="2dff0-103">About Quoting Rules</span></span>

## <a name="short-description"></a><span data-ttu-id="2dff0-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2dff0-104">Short description</span></span>
<span data-ttu-id="2dff0-105">Beschreibt Regeln für die Verwendung von einfachen und doppelten Anführungszeichen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2dff0-105">Describes rules for using single and double quotation marks in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="2dff0-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2dff0-106">Long description</span></span>

<span data-ttu-id="2dff0-107">Anführungszeichen werden verwendet, um eine Literalzeichenfolge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2dff0-107">Quotation marks are used to specify a literal string.</span></span> <span data-ttu-id="2dff0-108">Sie können eine Zeichenfolge in einfache Anführungszeichen ( `'` ) oder in doppelte Anführungszeichen ( `"` ) einschließen.</span><span class="sxs-lookup"><span data-stu-id="2dff0-108">You can enclose a string in single quotation marks (`'`) or double quotation marks (`"`).</span></span>

<span data-ttu-id="2dff0-109">Anführungszeichen werden auch verwendet, um eine _here-Zeichenfolge_ zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2dff0-109">Quotation marks are also used to create a _here-string_.</span></span> <span data-ttu-id="2dff0-110">Eine here-Zeichenfolge ist eine Zeichenfolge in einfachen Anführungszeichen oder in doppelten Anführungszeichen, in der Anführungszeichen buchstäblich interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="2dff0-110">A here-string is a single-quoted or double-quoted string in which quotation marks are interpreted literally.</span></span> <span data-ttu-id="2dff0-111">Eine here-Zeichenfolge kann sich über mehrere Zeilen erstrecken.</span><span class="sxs-lookup"><span data-stu-id="2dff0-111">A here-string can span multiple lines.</span></span> <span data-ttu-id="2dff0-112">Alle Zeilen in einer here-Zeichenfolge werden als Zeichen folgen interpretiert, auch wenn Sie nicht in Anführungszeichen eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="2dff0-112">All the lines in a here-string are interpreted as strings, even though they are not enclosed in quotation marks.</span></span>

<span data-ttu-id="2dff0-113">In Befehlen auf Remote Computern definieren Anführungszeichen die Teile des Befehls, die auf dem Remote Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2dff0-113">In commands to remote computers, quotation marks define the parts of the command that are run on the remote computer.</span></span> <span data-ttu-id="2dff0-114">In einer Remote Sitzung bestimmen Anführungszeichen auch, ob die Variablen in einem Befehl zuerst auf dem lokalen Computer oder auf dem Remote Computer interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="2dff0-114">In a remote session, quotation marks also determine whether the variables in a command are interpreted first on the local computer or on the remote computer.</span></span>

## <a name="single-and-double-quoted-strings"></a><span data-ttu-id="2dff0-115">Zeichen folgen mit einzelfacher und doppelter Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="2dff0-115">Single and double-quoted strings</span></span>

<span data-ttu-id="2dff0-116">Eine Zeichenfolge, die in doppelte Anführungszeichen eingeschlossen ist, ist eine _erweiterbare_ Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2dff0-116">A string enclosed in double quotation marks is an _expandable_ string.</span></span> <span data-ttu-id="2dff0-117">Variablennamen, denen ein Dollarzeichen ( `$` ) vorangestellt ist, werden durch den Wert der Variablen ersetzt, bevor die Zeichenfolge zur Verarbeitung an den Befehl übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="2dff0-117">Variable names preceded by a dollar sign (`$`) are replaced with the variable's value before the string is passed to the command for processing.</span></span>

<span data-ttu-id="2dff0-118">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2dff0-118">For example:</span></span>

```powershell
$i = 5
"The value of $i is $i."
```

<span data-ttu-id="2dff0-119">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2dff0-119">The output of this command is:</span></span>

```Output
The value of 5 is 5.
```

<span data-ttu-id="2dff0-120">Außerdem werden Ausdrücke in einer Zeichenfolge mit doppelten Anführungszeichen ausgewertet, und das Ergebnis wird in die Zeichenfolge eingefügt.</span><span class="sxs-lookup"><span data-stu-id="2dff0-120">Also, in a double-quoted string, expressions are evaluated, and the result is inserted in the string.</span></span> <span data-ttu-id="2dff0-121">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2dff0-121">For example:</span></span>

```powershell
"The value of $(2+3) is 5."
```

<span data-ttu-id="2dff0-122">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2dff0-122">The output of this command is:</span></span>

```Output
The value of 5 is 5.
```

<span data-ttu-id="2dff0-123">Eine Zeichenfolge, die in einfache Anführungszeichen eingeschlossen ist, ist eine _wörtliche_ Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2dff0-123">A string enclosed in single-quotation marks is a _verbatim_ string.</span></span> <span data-ttu-id="2dff0-124">Die Zeichenfolge wird genau wie bei der Eingabe an den Befehl übermittelt.</span><span class="sxs-lookup"><span data-stu-id="2dff0-124">The string is passed to the command exactly as you type it.</span></span> <span data-ttu-id="2dff0-125">Es wird keine Ersetzung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="2dff0-125">No substitution is performed.</span></span>
<span data-ttu-id="2dff0-126">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2dff0-126">For example:</span></span>

```powershell
$i = 5
'The value of $i is $i.'
```

<span data-ttu-id="2dff0-127">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2dff0-127">The output of this command is:</span></span>

```Output
The value $i is $i.
```

<span data-ttu-id="2dff0-128">Ebenso werden Ausdrücke in Zeichen folgen in einfachen Anführungszeichen nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="2dff0-128">Similarly, expressions in single-quoted strings are not evaluated.</span></span> <span data-ttu-id="2dff0-129">Sie werden als Literale interpretiert.</span><span class="sxs-lookup"><span data-stu-id="2dff0-129">They are interpreted as literals.</span></span> <span data-ttu-id="2dff0-130">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2dff0-130">For example:</span></span>

```powershell
'The value of $(2+3) is 5.'
```

<span data-ttu-id="2dff0-131">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2dff0-131">The output of this command is:</span></span>

```Output
The value of $(2+3) is 5.
```

<span data-ttu-id="2dff0-132">Um die Ersetzung eines Variablen Werts in einer Zeichenfolge mit doppelten Anführungszeichen zu verhindern, verwenden Sie das Graviszeichen-Zeichen ( `` ` `` ) (ASCII 96), das das PowerShell-Escapezeichen ist.</span><span class="sxs-lookup"><span data-stu-id="2dff0-132">To prevent the substitution of a variable value in a double-quoted string, use the backtick character (`` ` ``)(ASCII 96), which is the PowerShell escape character.</span></span>

<span data-ttu-id="2dff0-133">Im folgenden Beispiel verhindert das Graviszeichen-Zeichen, das der ersten Variablen vorangestellt ist, dass `$i` PowerShell den Variablennamen durch den Wert ersetzt.</span><span class="sxs-lookup"><span data-stu-id="2dff0-133">In the following example, the backtick character that precedes the first `$i` variable prevents PowerShell from replacing the variable name with its value.</span></span>
<span data-ttu-id="2dff0-134">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2dff0-134">For example:</span></span>

```powershell
$i = 5
"The value of `$i is $i."
```

<span data-ttu-id="2dff0-135">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2dff0-135">The output of this command is:</span></span>

```Output
The value $i is 5.
```

<span data-ttu-id="2dff0-136">Damit doppelte Anführungszeichen in einer Zeichenfolge angezeigt werden, müssen Sie die gesamte Zeichenfolge in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="2dff0-136">To make double-quotation marks appear in a string, enclose the entire string in single quotation marks.</span></span> <span data-ttu-id="2dff0-137">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2dff0-137">For example:</span></span>

```powershell
'As they say, "live and learn."'
```

<span data-ttu-id="2dff0-138">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2dff0-138">The output of this command is:</span></span>

```Output
As they say, "live and learn."
```

<span data-ttu-id="2dff0-139">Sie können auch eine Zeichenfolge in einer Zeichenfolge mit doppelten Anführungszeichen in eine Zeichenfolge mit doppelten Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="2dff0-139">You can also enclose a single-quoted string in a double-quoted string.</span></span> <span data-ttu-id="2dff0-140">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2dff0-140">For example:</span></span>

```powershell
"As they say, 'live and learn.'"
```

<span data-ttu-id="2dff0-141">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2dff0-141">The output of this command is:</span></span>

```Output
As they say, 'live and learn.'
```

<span data-ttu-id="2dff0-142">Oder doppelte Anführungszeichen um einen Ausdruck mit doppelten Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="2dff0-142">Or, double the quotation marks around a double-quoted phrase.</span></span> <span data-ttu-id="2dff0-143">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2dff0-143">For example:</span></span>

```powershell
"As they say, ""live and learn."""
```

<span data-ttu-id="2dff0-144">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2dff0-144">The output of this command is:</span></span>

```Output
As they say, "live and learn."
```

<span data-ttu-id="2dff0-145">Wenn Sie ein einzelnes Anführungszeichen in eine Zeichenfolge mit nur einem Anführungszeichen einschließen möchten, verwenden Sie ein zweites aufeinander folgende einfache Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="2dff0-145">To include a single quotation mark in a single-quoted string, use a second consecutive single quote.</span></span> <span data-ttu-id="2dff0-146">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2dff0-146">For example:</span></span>

```powershell
'don''t'
```

<span data-ttu-id="2dff0-147">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2dff0-147">The output of this command is:</span></span>

```Output
don't
```

<span data-ttu-id="2dff0-148">Um zu erzwingen, dass PowerShell ein doppeltes Anführungszeichen wörtlich interpretiert, verwenden Sie ein Graviszeichen-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2dff0-148">To force PowerShell to interpret a double quotation mark literally, use a backtick character.</span></span> <span data-ttu-id="2dff0-149">Dadurch wird verhindert, dass PowerShell das Anführungszeichen als Zeichen folgen Trennzeichen interpretiert.</span><span class="sxs-lookup"><span data-stu-id="2dff0-149">This prevents PowerShell from interpreting the quotation mark as a string delimiter.</span></span> <span data-ttu-id="2dff0-150">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2dff0-150">For example:</span></span>

```powershell
PS> "Use a quotation mark (`") to begin a string."
Use a quotation mark (") to begin a string.
PS> 'Use a quotation mark (`") to begin a string.'
Use a quotation mark (`") to begin a string.
```

<span data-ttu-id="2dff0-151">Da der Inhalt von Zeichen folgen in einfachen Anführungszeichen wörtlich interpretiert wird, wird das Graviszeichen-Zeichen als Literalzeichen behandelt und in der Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2dff0-151">Because the contents of single-quoted strings are interpreted literally, you the backtick character is treated as a literal character and displayed in the output.</span></span>

## <a name="here-strings"></a><span data-ttu-id="2dff0-152">Here-Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="2dff0-152">Here-strings</span></span>

<span data-ttu-id="2dff0-153">Die Anführungszeichen Regeln für here-Zeichen folgen unterscheiden sich geringfügig.</span><span class="sxs-lookup"><span data-stu-id="2dff0-153">The quotation rules for here-strings are slightly different.</span></span>

<span data-ttu-id="2dff0-154">Eine here-Zeichenfolge ist eine Zeichenfolge in einfachen Anführungszeichen oder in doppelten Anführungszeichen, in der Anführungszeichen buchstäblich interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="2dff0-154">A here-string is a single-quoted or double-quoted string in which quotation marks are interpreted literally.</span></span> <span data-ttu-id="2dff0-155">Eine here-Zeichenfolge kann sich über mehrere Zeilen erstrecken.</span><span class="sxs-lookup"><span data-stu-id="2dff0-155">A here-string can span multiple lines.</span></span> <span data-ttu-id="2dff0-156">Alle Zeilen in einer here-Zeichenfolge werden als Zeichen folgen interpretiert, auch wenn Sie nicht in Anführungszeichen eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="2dff0-156">All the lines in a here-string are interpreted as strings even though they are not enclosed in quotation marks.</span></span>

<span data-ttu-id="2dff0-157">Wie reguläre Zeichen folgen werden Variablen durch ihre Werte in Zeichen folgen in doppelten Anführungszeichen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="2dff0-157">Like regular strings, variables are replaced by their values in double-quoted here-strings.</span></span> <span data-ttu-id="2dff0-158">In in einfachen Anführungszeichen eingeschlossenen Zeichen folgen werden Variablen nicht durch ihre Werte ersetzt.</span><span class="sxs-lookup"><span data-stu-id="2dff0-158">In single-quoted here-strings, variables are not replaced by their values.</span></span>

<span data-ttu-id="2dff0-159">Sie können hier Zeichen folgen für jeden beliebigen Text verwenden, Sie sind jedoch für die folgenden Arten von Text besonders nützlich:</span><span class="sxs-lookup"><span data-stu-id="2dff0-159">You can use here-strings for any text, but they are particularly useful for the following kinds of text:</span></span>

- <span data-ttu-id="2dff0-160">Text, der literalanführungs Zeichen enthält</span><span class="sxs-lookup"><span data-stu-id="2dff0-160">Text that contains literal quotation marks</span></span>
- <span data-ttu-id="2dff0-161">Mehrere Textzeilen, z. b. der Text in einem HTML-oder XML-Code</span><span class="sxs-lookup"><span data-stu-id="2dff0-161">Multiple lines of text, such as the text in an HTML or XML</span></span>
- <span data-ttu-id="2dff0-162">Der Hilfetext eines Skripts oder Funktions Dokuments.</span><span class="sxs-lookup"><span data-stu-id="2dff0-162">The Help text for a script or function document</span></span>

<span data-ttu-id="2dff0-163">Eine here-Zeichenfolge kann eines der folgenden Formate aufweisen, wobei `<Enter>` das Zeilenvorschub-oder Zeilenvorschub Zeichen darstellt, das hinzugefügt wird, wenn Sie die <kbd>Eingabe</kbd> Taste drücken.</span><span class="sxs-lookup"><span data-stu-id="2dff0-163">A here-string can have either of the following formats, where `<Enter>` represents the linefeed or newline hidden character that is added when you press the <kbd>ENTER</kbd> key.</span></span>

<span data-ttu-id="2dff0-164">Doppelte Anführungszeichen:</span><span class="sxs-lookup"><span data-stu-id="2dff0-164">Double-quotes:</span></span>

```
@"<Enter>
<string> [string] ...<Enter>
"@
```

<span data-ttu-id="2dff0-165">Einfache Anführungszeichen:</span><span class="sxs-lookup"><span data-stu-id="2dff0-165">Single-quotes:</span></span>

```
@'<Enter>
<string> [string] ...<Enter>
'@
```

<span data-ttu-id="2dff0-166">In beiden Formaten muss das schließende Anführungszeichen das erste Zeichen in der Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="2dff0-166">In either format, the closing quotation mark must be the first character in the line.</span></span>

<span data-ttu-id="2dff0-167">Eine here-Zeichenfolge enthält den gesamten Text zwischen den beiden ausgeblendeten Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2dff0-167">A here-string contains all the text between the two hidden characters.</span></span> <span data-ttu-id="2dff0-168">In der here-Zeichenfolge werden alle Anführungszeichen buchstäblich interpretiert.</span><span class="sxs-lookup"><span data-stu-id="2dff0-168">In the here-string, all quotation marks are interpreted literally.</span></span> <span data-ttu-id="2dff0-169">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2dff0-169">For example:</span></span>

```powershell
@"
For help, type "get-help"
"@
```

<span data-ttu-id="2dff0-170">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2dff0-170">The output of this command is:</span></span>

```Output
For help, type "get-help"
```

<span data-ttu-id="2dff0-171">Die Verwendung einer here-Zeichenfolge kann die Verwendung einer Zeichenfolge in einem Befehl vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="2dff0-171">Using a here-string can simplify using a string in a command.</span></span> <span data-ttu-id="2dff0-172">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2dff0-172">For example:</span></span>

```powershell
@"
Use a quotation mark (') to begin a string.
"@
```

<span data-ttu-id="2dff0-173">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2dff0-173">The output of this command is:</span></span>

```Output
Use a quotation mark (') to begin a string.
```

<span data-ttu-id="2dff0-174">In in einfachen Anführungszeichen eingeschlossenen Zeichen folgen werden Variablen buchstäblich interpretiert und exakt reproduziert.</span><span class="sxs-lookup"><span data-stu-id="2dff0-174">In single-quoted here-strings, variables are interpreted literally and reproduced exactly.</span></span> <span data-ttu-id="2dff0-175">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2dff0-175">For example:</span></span>

```powershell
@'
The $profile variable contains the path
of your PowerShell profile.
'@
```

<span data-ttu-id="2dff0-176">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2dff0-176">The output of this command is:</span></span>

```Output
The $profile variable contains the path
of your PowerShell profile.
```

<span data-ttu-id="2dff0-177">In doppelten Anführungszeichen werden Zeichen folgen, Variablen durch ihre Werte ersetzt.</span><span class="sxs-lookup"><span data-stu-id="2dff0-177">In double-quoted here-strings, variables are replaced by their values.</span></span> <span data-ttu-id="2dff0-178">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2dff0-178">For example:</span></span>

```powershell
@"
Even if you have not created a profile,
the path of the profile file is:
$profile.
"@
```

<span data-ttu-id="2dff0-179">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2dff0-179">The output of this command is:</span></span>

```Output
Even if you have not created a profile,
the path of the profile file is:
C:\Users\User1\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1.
```

<span data-ttu-id="2dff0-180">Here-Zeichen folgen werden normalerweise verwendet, um einer Variablen mehrere Zeilen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="2dff0-180">Here-strings are typically used to assign multiple lines to a variable.</span></span> <span data-ttu-id="2dff0-181">Beispielsweise weist die folgende here-Zeichenfolge der $Page Variable eine XML-Seite zu.</span><span class="sxs-lookup"><span data-stu-id="2dff0-181">For example, the following here-string assigns a page of XML to the $page variable.</span></span>

```powershell
$page = [XML] @"
<command:command xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
<command:details>
        <command:name>
               Format-Table
        </command:name>
        <maml:description>
            <maml:para>Formats the output as a table.</maml:para>
        </maml:description>
        <command:verb>format</command:verb>
        <command:noun>table</command:noun>
        <dev:version></dev:version>
</command:details>
...
</command:command>
"@
```

<span data-ttu-id="2dff0-182">Here-Zeichen folgen sind auch ein nützliches Format für Eingaben in das `ConvertFrom-StringData` Cmdlet, das hier Zeichen folgen in Hash Tabellen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2dff0-182">Here-strings are also a convenient format for input to the `ConvertFrom-StringData` cmdlet, which converts here-strings to hash tables.</span></span>
<span data-ttu-id="2dff0-183">Weitere Informationen finden Sie unter `ConvertFrom-StringData`.</span><span class="sxs-lookup"><span data-stu-id="2dff0-183">For more information, see `ConvertFrom-StringData`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2dff0-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2dff0-184">See also</span></span>

[<span data-ttu-id="2dff0-185">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="2dff0-185">about_Special_Characters</span></span>](about_Special_Characters.md)

[<span data-ttu-id="2dff0-186">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="2dff0-186">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
