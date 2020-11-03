---
description: Beschreibt Regeln für die Verwendung von einfachen und doppelten Anführungszeichen in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_quoting_rules?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Quoting_Rules
ms.openlocfilehash: 8d09171a1459a8ad03b54f2a4ef7a81c5983f6b8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222911"
---
# <a name="about-quoting-rules"></a><span data-ttu-id="1f438-104">Informationen zu Anführungs Regeln</span><span class="sxs-lookup"><span data-stu-id="1f438-104">About Quoting Rules</span></span>

## <a name="short-description"></a><span data-ttu-id="1f438-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1f438-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="1f438-106">Beschreibt Regeln für die Verwendung von einfachen und doppelten Anführungszeichen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f438-106">Describes rules for using single and double quotation marks in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="1f438-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1f438-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="1f438-108">Anführungszeichen werden verwendet, um eine Literalzeichenfolge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1f438-108">Quotation marks are used to specify a literal string.</span></span> <span data-ttu-id="1f438-109">Sie können eine Zeichenfolge in einfache Anführungszeichen ( `'` ) oder in doppelte Anführungszeichen ( `"` ) einschließen.</span><span class="sxs-lookup"><span data-stu-id="1f438-109">You can enclose a string in single quotation marks (`'`) or double quotation marks (`"`).</span></span>

<span data-ttu-id="1f438-110">Anführungszeichen werden auch verwendet, um eine here-Zeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f438-110">Quotation marks are also used to create a here-string.</span></span> <span data-ttu-id="1f438-111">Eine here-Zeichenfolge ist eine Zeichenfolge in einfachen Anführungszeichen oder in doppelten Anführungszeichen, in der Anführungszeichen buchstäblich interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f438-111">A here-string is a single-quoted or double-quoted string in which quotation marks are interpreted literally.</span></span> <span data-ttu-id="1f438-112">Eine here-Zeichenfolge kann sich über mehrere Zeilen erstrecken.</span><span class="sxs-lookup"><span data-stu-id="1f438-112">A here-string can span multiple lines.</span></span> <span data-ttu-id="1f438-113">Alle Zeilen in einer here-Zeichenfolge werden als Zeichen folgen interpretiert, auch wenn Sie nicht in Anführungszeichen eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="1f438-113">All the lines in a here-string are interpreted as strings, even though they are not enclosed in quotation marks.</span></span>

<span data-ttu-id="1f438-114">In Befehlen auf Remote Computern definieren Anführungszeichen die Teile des Befehls, die auf dem Remote Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1f438-114">In commands to remote computers, quotation marks define the parts of the command that are run on the remote computer.</span></span> <span data-ttu-id="1f438-115">In einer Remote Sitzung bestimmen Anführungszeichen auch, ob die Variablen in einem Befehl zuerst auf dem lokalen Computer oder auf dem Remote Computer interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f438-115">In a remote session, quotation marks also determine whether the variables in a command are interpreted first on the local computer or on the remote computer.</span></span>

### <a name="single-and-double-quoted-strings"></a><span data-ttu-id="1f438-116">Zeichen folgen mit einzelfacher und doppelter Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="1f438-116">SINGLE AND DOUBLE-QUOTED STRINGS</span></span>

<span data-ttu-id="1f438-117">Wenn Sie eine Zeichenfolge in doppelte Anführungszeichen (eine Zeichenfolge mit doppelten Anführungszeichen) einschließen, werden Variablennamen, denen ein Dollarzeichen () vorangestellt ist, durch `$` den Wert der Variablen ersetzt, bevor die Zeichenfolge zur Verarbeitung an den Befehl übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="1f438-117">When you enclose a string in double quotation marks (a double-quoted string), variable names that are preceded by a dollar sign (`$`) are replaced with the variable's value before the string is passed to the command for processing.</span></span>

<span data-ttu-id="1f438-118">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f438-118">For example:</span></span>

```powershell
$i = 5
"The value of $i is $i."
```

<span data-ttu-id="1f438-119">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1f438-119">The output of this command is:</span></span>

```Output
The value of 5 is 5.
```

<span data-ttu-id="1f438-120">Außerdem werden Ausdrücke in einer Zeichenfolge mit doppelten Anführungszeichen ausgewertet, und das Ergebnis wird in die Zeichenfolge eingefügt.</span><span class="sxs-lookup"><span data-stu-id="1f438-120">Also, in a double-quoted string, expressions are evaluated, and the result is inserted in the string.</span></span> <span data-ttu-id="1f438-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f438-121">For example:</span></span>

```powershell
"The value of $(2+3) is 5."
```

<span data-ttu-id="1f438-122">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1f438-122">The output of this command is:</span></span>

```Output
The value of 5 is 5.
```

<span data-ttu-id="1f438-123">Wenn Sie eine Zeichenfolge in einfache Anführungszeichen einschließen (in einer Zeichenfolge mit nur einem Anführungszeichen), wird die Zeichenfolge genau wie bei der Eingabe an den Befehl übermittelt.</span><span class="sxs-lookup"><span data-stu-id="1f438-123">When you enclose a string in single-quotation marks (a single-quoted string), the string is passed to the command exactly as you type it.</span></span> <span data-ttu-id="1f438-124">Es wird keine Ersetzung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="1f438-124">No substitution is performed.</span></span> <span data-ttu-id="1f438-125">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f438-125">For example:</span></span>

```powershell
$i = 5
'The value of $i is $i.'
```

<span data-ttu-id="1f438-126">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1f438-126">The output of this command is:</span></span>

```Output
The value $i is $i.
```

<span data-ttu-id="1f438-127">Ebenso werden Ausdrücke in Zeichen folgen in einfachen Anführungszeichen nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1f438-127">Similarly, expressions in single-quoted strings are not evaluated.</span></span> <span data-ttu-id="1f438-128">Sie werden als Literale interpretiert.</span><span class="sxs-lookup"><span data-stu-id="1f438-128">They are interpreted as literals.</span></span> <span data-ttu-id="1f438-129">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f438-129">For example:</span></span>

```powershell
'The value of $(2+3) is 5.'
```

<span data-ttu-id="1f438-130">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1f438-130">The output of this command is:</span></span>

```Output
The value of $(2+3) is 5.
```

<span data-ttu-id="1f438-131">Um die Ersetzung eines Variablen Werts in einer Zeichenfolge mit doppelten Anführungszeichen zu verhindern, verwenden Sie das Graviszeichen-Zeichen ( `` ` `` ) (ASCII 96), das das PowerShell-Escapezeichen ist.</span><span class="sxs-lookup"><span data-stu-id="1f438-131">To prevent the substitution of a variable value in a double-quoted string, use the backtick character (`` ` ``)(ASCII 96), which is the PowerShell escape character.</span></span>

<span data-ttu-id="1f438-132">Im folgenden Beispiel verhindert das Graviszeichen-Zeichen, das der ersten $i Variablen vorangestellt ist, dass PowerShell den Variablennamen durch den Wert ersetzt.</span><span class="sxs-lookup"><span data-stu-id="1f438-132">In the following example, the backtick character that precedes the first $i variable prevents PowerShell from replacing the variable name with its value.</span></span>
<span data-ttu-id="1f438-133">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f438-133">For example:</span></span>

```powershell
$i = 5
"The value of `$i is $i."
```

<span data-ttu-id="1f438-134">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1f438-134">The output of this command is:</span></span>

```Output
The value $i is 5.
```

<span data-ttu-id="1f438-135">Damit doppelte Anführungszeichen in einer Zeichenfolge angezeigt werden, müssen Sie die gesamte Zeichenfolge in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="1f438-135">To make double-quotation marks appear in a string, enclose the entire string in single quotation marks.</span></span> <span data-ttu-id="1f438-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f438-136">For example:</span></span>

```powershell
'As they say, "live and learn."'
```

<span data-ttu-id="1f438-137">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1f438-137">The output of this command is:</span></span>

```Output
As they say, "live and learn."
```

<span data-ttu-id="1f438-138">Sie können auch eine Zeichenfolge in einer Zeichenfolge mit doppelten Anführungszeichen in eine Zeichenfolge mit doppelten Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="1f438-138">You can also enclose a single-quoted string in a double-quoted string.</span></span> <span data-ttu-id="1f438-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f438-139">For example:</span></span>

```powershell
"As they say, 'live and learn.'"
```

<span data-ttu-id="1f438-140">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1f438-140">The output of this command is:</span></span>

```Output
As they say, 'live and learn.'
```

<span data-ttu-id="1f438-141">Oder doppelte Anführungszeichen um einen Ausdruck mit doppelten Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="1f438-141">Or, double the quotation marks around a double-quoted phrase.</span></span> <span data-ttu-id="1f438-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f438-142">For example:</span></span>

```powershell
"As they say, ""live and learn."""
```

<span data-ttu-id="1f438-143">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1f438-143">The output of this command is:</span></span>

```Output
As they say, "live and learn."
```

<span data-ttu-id="1f438-144">Wenn Sie ein einzelnes Anführungszeichen in eine Zeichenfolge mit nur einem Anführungszeichen einschließen möchten, verwenden Sie ein zweites aufeinander folgende einfache Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="1f438-144">To include a single quotation mark in a single-quoted string, use a second consecutive single quote.</span></span> <span data-ttu-id="1f438-145">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f438-145">For example:</span></span>

```powershell
'don''t'
```

<span data-ttu-id="1f438-146">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1f438-146">The output of this command is:</span></span>

```Output
don't
```

<span data-ttu-id="1f438-147">Um zu erzwingen, dass PowerShell ein doppeltes Anführungszeichen wörtlich interpretiert, verwenden Sie ein Graviszeichen-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1f438-147">To force PowerShell to interpret a double quotation mark literally, use a backtick character.</span></span> <span data-ttu-id="1f438-148">Dadurch wird verhindert, dass PowerShell das Anführungszeichen als Zeichen folgen Trennzeichen interpretiert.</span><span class="sxs-lookup"><span data-stu-id="1f438-148">This prevents PowerShell from interpreting the quotation mark as a string delimiter.</span></span> <span data-ttu-id="1f438-149">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f438-149">For example:</span></span>

```powershell
PS> "Use a quotation mark (`") to begin a string."
Use a quotation mark (") to begin a string.
PS> 'Use a quotation mark (`") to begin a string.'
Use a quotation mark (`") to begin a string.
```

<span data-ttu-id="1f438-150">Da der Inhalt von Zeichen folgen in einfachen Anführungszeichen wörtlich interpretiert wird, wird das Graviszeichen-Zeichen als Literalzeichen behandelt und in der Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f438-150">Because the contents of single-quoted strings are interpreted literally, you the backtick character is treated as a literal character and displayed in the output.</span></span>

### <a name="here-strings"></a><span data-ttu-id="1f438-151">Here-Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="1f438-151">HERE-STRINGS</span></span>

<span data-ttu-id="1f438-152">Die Anführungszeichen Regeln für here-Zeichen folgen unterscheiden sich geringfügig.</span><span class="sxs-lookup"><span data-stu-id="1f438-152">The quotation rules for here-strings are slightly different.</span></span>

<span data-ttu-id="1f438-153">Eine here-Zeichenfolge ist eine Zeichenfolge in einfachen Anführungszeichen oder in doppelten Anführungszeichen, in der Anführungszeichen buchstäblich interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f438-153">A here-string is a single-quoted or double-quoted string in which quotation marks are interpreted literally.</span></span> <span data-ttu-id="1f438-154">Eine here-Zeichenfolge kann sich über mehrere Zeilen erstrecken.</span><span class="sxs-lookup"><span data-stu-id="1f438-154">A here-string can span multiple lines.</span></span> <span data-ttu-id="1f438-155">Alle Zeilen in einer here-Zeichenfolge werden als Zeichen folgen interpretiert, auch wenn Sie nicht in Anführungszeichen eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="1f438-155">All the lines in a here-string are interpreted as strings even though they are not enclosed in quotation marks.</span></span>

<span data-ttu-id="1f438-156">Wie reguläre Zeichen folgen werden Variablen durch ihre Werte in Zeichen folgen in doppelten Anführungszeichen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="1f438-156">Like regular strings, variables are replaced by their values in double-quoted here-strings.</span></span> <span data-ttu-id="1f438-157">In in einfachen Anführungszeichen eingeschlossenen Zeichen folgen werden Variablen nicht durch ihre Werte ersetzt.</span><span class="sxs-lookup"><span data-stu-id="1f438-157">In single-quoted here-strings, variables are not replaced by their values.</span></span>

<span data-ttu-id="1f438-158">Sie können hier Zeichen folgen für jeden beliebigen Text verwenden, Sie sind jedoch für die folgenden Arten von Text besonders nützlich:</span><span class="sxs-lookup"><span data-stu-id="1f438-158">You can use here-strings for any text, but they are particularly useful for the following kinds of text:</span></span>

- <span data-ttu-id="1f438-159">Text, der literalanführungs Zeichen enthält</span><span class="sxs-lookup"><span data-stu-id="1f438-159">Text that contains literal quotation marks</span></span>
- <span data-ttu-id="1f438-160">Mehrere Textzeilen, z. b. der Text in einem HTML-oder XML-Code</span><span class="sxs-lookup"><span data-stu-id="1f438-160">Multiple lines of text, such as the text in an HTML or XML</span></span>
- <span data-ttu-id="1f438-161">Der Hilfetext eines Skripts oder Funktions Dokuments.</span><span class="sxs-lookup"><span data-stu-id="1f438-161">The Help text for a script or function document</span></span>

<span data-ttu-id="1f438-162">Eine here-Zeichenfolge kann eines der folgenden Formate aufweisen, wobei `<Enter>` das Zeilenvorschub-oder Zeilenvorschub Zeichen darstellt, das hinzugefügt wird, wenn Sie die <kbd>Eingabe</kbd> Taste drücken.</span><span class="sxs-lookup"><span data-stu-id="1f438-162">A here-string can have either of the following formats, where `<Enter>` represents the linefeed or newline hidden character that is added when you press the <kbd>ENTER</kbd> key.</span></span>

<span data-ttu-id="1f438-163">Doppelte Anführungszeichen:</span><span class="sxs-lookup"><span data-stu-id="1f438-163">Double-quotes:</span></span>

```
@"<Enter>
<string> [string] ...<Enter>
"@
```

<span data-ttu-id="1f438-164">Einfache Anführungszeichen:</span><span class="sxs-lookup"><span data-stu-id="1f438-164">Single-quotes:</span></span>

```
@'<Enter>
<string> [string] ...<Enter>
'@
```

<span data-ttu-id="1f438-165">In beiden Formaten muss das schließende Anführungszeichen das erste Zeichen in der Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="1f438-165">In either format, the closing quotation mark must be the first character in the line.</span></span>

<span data-ttu-id="1f438-166">Eine here-Zeichenfolge enthält den gesamten Text zwischen den beiden ausgeblendeten Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1f438-166">A here-string contains all the text between the two hidden characters.</span></span> <span data-ttu-id="1f438-167">In der here-Zeichenfolge werden alle Anführungszeichen buchstäblich interpretiert.</span><span class="sxs-lookup"><span data-stu-id="1f438-167">In the here-string, all quotation marks are interpreted literally.</span></span> <span data-ttu-id="1f438-168">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f438-168">For example:</span></span>

```powershell
@"
For help, type "get-help"
"@
```

<span data-ttu-id="1f438-169">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1f438-169">The output of this command is:</span></span>

```Output
For help, type "get-help"
```

<span data-ttu-id="1f438-170">Die Verwendung einer here-Zeichenfolge kann die Verwendung einer Zeichenfolge in einem Befehl vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="1f438-170">Using a here-string can simplify using a string in a command.</span></span> <span data-ttu-id="1f438-171">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f438-171">For example:</span></span>

```powershell
@"
Use a quotation mark (') to begin a string.
"@
```

<span data-ttu-id="1f438-172">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1f438-172">The output of this command is:</span></span>

```Output
Use a quotation mark (') to begin a string.
```

<span data-ttu-id="1f438-173">In in einfachen Anführungszeichen eingeschlossenen Zeichen folgen werden Variablen buchstäblich interpretiert und exakt reproduziert.</span><span class="sxs-lookup"><span data-stu-id="1f438-173">In single-quoted here-strings, variables are interpreted literally and reproduced exactly.</span></span> <span data-ttu-id="1f438-174">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f438-174">For example:</span></span>

```powershell
@'
The $profile variable contains the path
of your PowerShell profile.
'@
```

<span data-ttu-id="1f438-175">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1f438-175">The output of this command is:</span></span>

```Output
The $profile variable contains the path
of your PowerShell profile.
```

<span data-ttu-id="1f438-176">In doppelten Anführungszeichen werden Zeichen folgen, Variablen durch ihre Werte ersetzt.</span><span class="sxs-lookup"><span data-stu-id="1f438-176">In double-quoted here-strings, variables are replaced by their values.</span></span> <span data-ttu-id="1f438-177">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f438-177">For example:</span></span>

```powershell
@"
Even if you have not created a profile,
the path of the profile file is:
$profile.
"@
```

<span data-ttu-id="1f438-178">Die Ausgabe dieses Befehls lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1f438-178">The output of this command is:</span></span>

```Output
Even if you have not created a profile,
the path of the profile file is:
C:\Users\User1\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1.
```

<span data-ttu-id="1f438-179">Here-Zeichen folgen werden normalerweise verwendet, um einer Variablen mehrere Zeilen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="1f438-179">Here-strings are typically used to assign multiple lines to a variable.</span></span> <span data-ttu-id="1f438-180">Beispielsweise weist die folgende here-Zeichenfolge der $Page Variable eine XML-Seite zu.</span><span class="sxs-lookup"><span data-stu-id="1f438-180">For example, the following here-string assigns a page of XML to the $page variable.</span></span>

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

<span data-ttu-id="1f438-181">Here-Zeichen folgen sind auch ein nützliches Format für Eingaben in das `ConvertFrom-StringData` Cmdlet, das hier Zeichen folgen in Hash Tabellen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="1f438-181">Here-strings are also a convenient format for input to the `ConvertFrom-StringData` cmdlet, which converts here-strings to hash tables.</span></span>
<span data-ttu-id="1f438-182">Weitere Informationen finden Sie unter `ConvertFrom-StringData`.</span><span class="sxs-lookup"><span data-stu-id="1f438-182">For more information, see `ConvertFrom-StringData`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f438-183">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="1f438-183">SEE ALSO</span></span>

[<span data-ttu-id="1f438-184">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="1f438-184">about_Special_Characters</span></span>](about_Special_Characters.md)

[<span data-ttu-id="1f438-185">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="1f438-185">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
