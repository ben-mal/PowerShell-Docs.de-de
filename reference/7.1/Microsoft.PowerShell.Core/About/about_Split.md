---
description: Erläutert, wie der Split-Operator verwendet wird, um eine oder mehrere Zeichen folgen in Teil Zeichenfolgen aufzuteilen.
Locale: en-US
ms.date: 03/30/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_split?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Split
ms.openlocfilehash: 1e731c04a232089d10191014cf8b84bb2b4e3b17
ms.sourcegitcommit: 4d6ed6f7d747a9bbb3fcfcf6c981c5aa8a973a08
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "106072732"
---
# <a name="about-split"></a><span data-ttu-id="85a5a-103">Informationen zur Aufteilung</span><span class="sxs-lookup"><span data-stu-id="85a5a-103">About Split</span></span>

## <a name="short-description"></a><span data-ttu-id="85a5a-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="85a5a-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="85a5a-105">Erläutert, wie der Split-Operator verwendet wird, um eine oder mehrere Zeichen folgen in Teil Zeichenfolgen aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="85a5a-105">Explains how to use the Split operator to split one or more strings into substrings.</span></span>

## <a name="long-description"></a><span data-ttu-id="85a5a-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="85a5a-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="85a5a-107">Der Split-Operator teilt eine oder mehrere Zeichen folgen in Teil Zeichenfolgen auf.</span><span class="sxs-lookup"><span data-stu-id="85a5a-107">The Split operator splits one or more strings into substrings.</span></span> <span data-ttu-id="85a5a-108">Sie können die folgenden Elemente des Split-Vorgangs ändern:</span><span class="sxs-lookup"><span data-stu-id="85a5a-108">You can change the following elements of the Split operation:</span></span>

- <span data-ttu-id="85a5a-109">Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="85a5a-109">Delimiter.</span></span> <span data-ttu-id="85a5a-110">Der Standardwert ist Leerraum, aber Sie können Zeichen, Zeichen folgen, Muster oder Skriptblöcke angeben, die das Trennzeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="85a5a-110">The default is whitespace, but you can specify characters, strings, patterns, or script blocks that specify the delimiter.</span></span> <span data-ttu-id="85a5a-111">Der Split-Operator in PowerShell verwendet anstelle eines einfachen Zeichens einen regulären Ausdruck im Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="85a5a-111">The Split operator in PowerShell uses a regular expression in the delimiter, rather than a simple character.</span></span>
- <span data-ttu-id="85a5a-112">Maximale Anzahl von Teil Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="85a5a-112">Maximum number of substrings.</span></span> <span data-ttu-id="85a5a-113">Der Standardwert besteht darin, alle Teil Zeichenfolgen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="85a5a-113">The default is to return all substrings.</span></span> <span data-ttu-id="85a5a-114">Wenn Sie eine Zahl angeben, die kleiner ist als die Anzahl der Teil Zeichenfolgen, werden die restlichen Teil Zeichenfolgen in der letzten Teil Zeichenfolge verkettet.</span><span class="sxs-lookup"><span data-stu-id="85a5a-114">If you specify a number less than the number of substrings, the remaining substrings are concatenated in the last substring.</span></span>
- <span data-ttu-id="85a5a-115">Optionen, die die Bedingungen angeben, unter denen das Trennzeichen abgeglichen wird, z. b. simplematch und Multiline.</span><span class="sxs-lookup"><span data-stu-id="85a5a-115">Options that specify the conditions under which the delimiter is matched, such as SimpleMatch and Multiline.</span></span>

## <a name="syntax"></a><span data-ttu-id="85a5a-116">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="85a5a-116">SYNTAX</span></span>

<span data-ttu-id="85a5a-117">Das folgende Diagramm zeigt die Syntax für den-Split-Operator.</span><span class="sxs-lookup"><span data-stu-id="85a5a-117">The following diagram shows the syntax for the -split operator.</span></span>

<span data-ttu-id="85a5a-118">Die Parameternamen werden im Befehl nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85a5a-118">The parameter names do not appear in the command.</span></span> <span data-ttu-id="85a5a-119">Nur die Parameterwerte einschließen.</span><span class="sxs-lookup"><span data-stu-id="85a5a-119">Include only the parameter values.</span></span> <span data-ttu-id="85a5a-120">Die Werte müssen in der im Syntax Diagramm angegebenen Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="85a5a-120">The values must appear in the order specified in the syntax diagram.</span></span>

```
-Split <String>
-Split (<String[]>)
<String> -Split <Delimiter>[,<Max-substrings>[,"<Options>"]]
<String> -Split {<ScriptBlock>} [,<Max-substrings>]
```

<span data-ttu-id="85a5a-121">Sie können `-iSplit` `-cSplit` `-split` in einer beliebigen binären Split-Anweisung (eine Split-Anweisung, die ein Trennzeichen oder einen Skriptblock enthält) ersetzen.</span><span class="sxs-lookup"><span data-stu-id="85a5a-121">You can substitute `-iSplit` or `-cSplit` for `-split` in any binary Split statement (a Split statement that includes a delimiter or script block).</span></span> <span data-ttu-id="85a5a-122">Die `-iSplit` groß `-split` -/Kleinschreibung wird von den Operatoren und</span><span class="sxs-lookup"><span data-stu-id="85a5a-122">The `-iSplit` and `-split` operators are case-insensitive.</span></span> <span data-ttu-id="85a5a-123">Der Operator unterscheidet zwischen Groß `-cSplit` -und Kleinschreibung, was bedeutet, dass der Fall beim Anwenden der Trennzeichen Regeln berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="85a5a-123">The `-cSplit` operator is case-sensitive, meaning that case is considered when the delimiter rules are applied.</span></span>

## <a name="parameters"></a><span data-ttu-id="85a5a-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="85a5a-124">PARAMETERS</span></span>

### <a name="string-or-string"></a><span data-ttu-id="85a5a-125">\<String\> oder \<String[]\></span><span class="sxs-lookup"><span data-stu-id="85a5a-125">\<String\> or \<String[]\></span></span>

<span data-ttu-id="85a5a-126">Gibt eine oder mehrere Zeichen folgen an, die aufgeteilt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="85a5a-126">Specifies one or more strings to be split.</span></span> <span data-ttu-id="85a5a-127">Wenn Sie mehrere Zeichen folgen übermitteln, werden alle Zeichen folgen mit denselben Trennzeichen Regeln aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="85a5a-127">If you submit multiple strings, all the strings are split using the same delimiter rules.</span></span>

<span data-ttu-id="85a5a-128">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="85a5a-128">Example:</span></span>

```
-split "red yellow blue green"
red
yellow
blue
green
```

### \<Delimiter\>

<span data-ttu-id="85a5a-129">Die Zeichen, die das Ende einer Teil Zeichenfolge identifizieren.</span><span class="sxs-lookup"><span data-stu-id="85a5a-129">The characters that identify the end of a substring.</span></span> <span data-ttu-id="85a5a-130">Das Standard Trennzeichen ist Leerzeichen, einschließlich Leerzeichen und nicht druckbaren Zeichen, wie z. b. Zeilen Vorschriften ( \` n) und Tab ( \` t).</span><span class="sxs-lookup"><span data-stu-id="85a5a-130">The default delimiter is whitespace, including spaces and non-printable characters, such as newline (\`n) and tab (\`t).</span></span> <span data-ttu-id="85a5a-131">Wenn die Zeichen folgen aufgeteilt werden, wird das Trennzeichen in allen Teil Zeichenfolgen ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="85a5a-131">When the strings are split, the delimiter is omitted from all the substrings.</span></span> <span data-ttu-id="85a5a-132">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="85a5a-132">Example:</span></span>

```powershell
"Lastname:FirstName:Address" -split ":"
Lastname
FirstName
Address
```

<span data-ttu-id="85a5a-133">Standardmäßig wird das Trennzeichen in den Ergebnissen ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="85a5a-133">By default, the delimiter is omitted from the results.</span></span> <span data-ttu-id="85a5a-134">Um das Trennzeichen vollständig oder teilweise beizubehalten, schließen Sie in Klammern den Teil ein, den Sie beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="85a5a-134">To preserve all or part of the delimiter, enclose in parentheses the part that you want to preserve.</span></span>
<span data-ttu-id="85a5a-135">Wenn der- `<Max-substrings>` Parameter hinzugefügt wird, hat dies Vorrang, wenn der Befehl die Auflistung aufteilt.</span><span class="sxs-lookup"><span data-stu-id="85a5a-135">If the `<Max-substrings>` parameter is added, this takes precedence when your command splits up the collection.</span></span> <span data-ttu-id="85a5a-136">Wenn Sie ein Trennzeichen als Teil der Ausgabe einschließen möchten, gibt der Befehl das Trennzeichen als Teil der Ausgabe zurück. das Aufteilen der Zeichenfolge, um das Trennzeichen als Teil der Ausgabe zurückzugeben, wird jedoch nicht als Teilung gezählt.</span><span class="sxs-lookup"><span data-stu-id="85a5a-136">If you opt to include a delimiter as part of the output, the command returns the delimiter as part of the output; however, splitting the string to return the delimiter as part of output does not count as a split.</span></span>

<span data-ttu-id="85a5a-137">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="85a5a-137">Examples:</span></span>

```powershell
"Lastname:FirstName:Address" -split "(:)"
Lastname
:
FirstName
:
Address

"Lastname/:/FirstName/:/Address" -split "/(:)/"
Lastname
:
FirstName
:
Address
```

### `<Max-substrings>`

<span data-ttu-id="85a5a-138">Gibt die maximale Anzahl von Teil Zeichenfolgen an, die vom Split-Vorgang zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="85a5a-138">Specifies the maximum number of substrings returned by the split operation.</span></span> <span data-ttu-id="85a5a-139">Der Standardwert ist alle Teil Zeichenfolgen, die durch das Trennzeichen geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="85a5a-139">The default is all substrings split by the delimiter.</span></span> <span data-ttu-id="85a5a-140">Wenn weitere Teil Zeichenfolgen vorhanden sind, werden Sie mit der endgültigen Teil Zeichenfolge verkettet.</span><span class="sxs-lookup"><span data-stu-id="85a5a-140">If there are more substrings, they are concatenated to the final substring.</span></span> <span data-ttu-id="85a5a-141">Wenn weniger Teil Zeichenfolgen vorhanden sind, werden alle Teil Zeichenfolgen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="85a5a-141">If there are fewer substrings, all substrings are returned.</span></span> <span data-ttu-id="85a5a-142">Der Wert 0 gibt alle Teil Zeichenfolgen zurück.</span><span class="sxs-lookup"><span data-stu-id="85a5a-142">A value of 0 returns all the substrings.</span></span>

<span data-ttu-id="85a5a-143">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="85a5a-143">Example:</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", 5
```

```Output
Mercury
Venus
Earth
Mars
Jupiter,Saturn,Uranus,Neptune
```

<span data-ttu-id="85a5a-144">Wenn Sie mehr als eine Zeichenfolge (ein Array von Zeichen folgen) an den Operator übermitteln `-split` , `Max-substrings` wird die Beschränkung auf jede Zeichenfolge separat angewendet.</span><span class="sxs-lookup"><span data-stu-id="85a5a-144">If you submit more than one string (an array of strings) to the `-split` operator, the `Max-substrings` limit is applied to each string separately.</span></span>

```powershell
$c = 'a,b,c','1,2,3,4,5'
$c -split ',', 3

a
b
c
1
2
3,4,5
```

<span data-ttu-id="85a5a-145">`<Max-substrings>` gibt nicht die maximale Anzahl von Objekten an, die zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="85a5a-145">`<Max-substrings>` does not specify the maximum number of objects that are returned.</span></span> <span data-ttu-id="85a5a-146">Im folgenden Beispiel `<Max-substrings>` wird auf 3 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="85a5a-146">In the following example, `<Max-substrings>` is set to 3.</span></span>
<span data-ttu-id="85a5a-147">Dies führt zu drei Teil Zeichenfolgen-Werten, aber insgesamt fünf Zeichen folgen in der resultierenden Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="85a5a-147">This results in three substring values, but a total of five strings in the resulting output.</span></span> <span data-ttu-id="85a5a-148">Das Trennzeichen ist nach den Teilungen enthalten, bis das Maximum von drei Teil Zeichenfolgen erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="85a5a-148">The delimiter is included after the splits until the maximum of three substrings is reached.</span></span> <span data-ttu-id="85a5a-149">Zusätzliche Trennzeichen in der letzten Teil Zeichenfolge werden Teil der Teil Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="85a5a-149">Additional delimiters in the final substring become part of the substring.</span></span>

```powershell
'Chocolate-Vanilla-Strawberry-Blueberry' -split '(-)', 3
```

```Output
Chocolate
-
Vanilla
-
Strawberry-Blueberry
```

<span data-ttu-id="85a5a-150">Negative Werte geben die Menge der angeforderten Teil Zeichenfolgen ab dem Ende der Eingabe Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="85a5a-150">Negative values return the amount of substrings requested starting from the end of the input string.</span></span>

> [!NOTE]
> <span data-ttu-id="85a5a-151">Unterstützung für negative Werte wurde in PowerShell 7 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="85a5a-151">Support for negative values was added in PowerShell 7.</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", -5
```

```Output
Mercury,Venus,Earth,Mars
Jupiter
Saturn
Uranus
Neptune
```

### \<ScriptBlock\>

<span data-ttu-id="85a5a-152">Ein Ausdruck, der Regeln zum Anwenden des Trenn Zeichens angibt.</span><span class="sxs-lookup"><span data-stu-id="85a5a-152">An expression that specifies rules for applying the delimiter.</span></span> <span data-ttu-id="85a5a-153">Der Ausdruck muss zu $true oder $false ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="85a5a-153">The expression must evaluate to $true or $false.</span></span> <span data-ttu-id="85a5a-154">Schließen Sie den Skriptblock in geschweifte Klammern ein.</span><span class="sxs-lookup"><span data-stu-id="85a5a-154">Enclose the script block in braces.</span></span>

<span data-ttu-id="85a5a-155">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="85a5a-155">Example:</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split {$_ -eq "e" -or $_ -eq "p"}
```

```Output
M
rcury,V
nus,
arth,Mars,Ju
it
r,Saturn,Uranus,N

tun
```

### \<Options\>

<span data-ttu-id="85a5a-156">Schließen Sie den Optionsnamen in Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="85a5a-156">Enclose the option name in quotation marks.</span></span> <span data-ttu-id="85a5a-157">Optionen sind nur gültig, wenn der- \<Max-substrings\> Parameter in der-Anweisung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="85a5a-157">Options are valid only when the \<Max-substrings\> parameter is used in the statement.</span></span>

<span data-ttu-id="85a5a-158">Die Syntax für den options-Parameter lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="85a5a-158">The syntax for the Options parameter is:</span></span>

```
"SimpleMatch [,IgnoreCase]"

"[RegexMatch] [,IgnoreCase] [,CultureInvariant]
[,IgnorePatternWhitespace] [,ExplicitCapture]
[,Singleline | ,Multiline]"
```

<span data-ttu-id="85a5a-159">Die simplematch-Optionen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="85a5a-159">The SimpleMatch options are:</span></span>

- <span data-ttu-id="85a5a-160">**Simplematch**: Verwenden Sie einen einfachen Zeichen folgen Vergleich, wenn Sie das Trennzeichen auswerten.</span><span class="sxs-lookup"><span data-stu-id="85a5a-160">**SimpleMatch**: Use simple string comparison when evaluating the delimiter.</span></span> <span data-ttu-id="85a5a-161">Kann nicht mit RegexMatch verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="85a5a-161">Cannot be used with RegexMatch.</span></span>
- <span data-ttu-id="85a5a-162">**IgnoreCase**: erzwingt Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung, auch wenn der-csplit-Operator angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="85a5a-162">**IgnoreCase**: Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>

<span data-ttu-id="85a5a-163">Die RegexMatch-Optionen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="85a5a-163">The RegexMatch options are:</span></span>

- <span data-ttu-id="85a5a-164">**RegexMatch**: verwendet reguläre Ausdrucks Vergleiche, um das Trennzeichen auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="85a5a-164">**RegexMatch**: Use regular expression matching to evaluate the delimiter.</span></span> <span data-ttu-id="85a5a-165">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="85a5a-165">This is the default behavior.</span></span> <span data-ttu-id="85a5a-166">Kann nicht mit simplematch verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="85a5a-166">Cannot be used with SimpleMatch.</span></span>
- <span data-ttu-id="85a5a-167">**IgnoreCase**: erzwingt Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung, auch wenn der-csplit-Operator angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="85a5a-167">**IgnoreCase**: Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>
- <span data-ttu-id="85a5a-168">**CultureInvariant**: ignoriert kulturelle Unterschiede in der Sprache, wenn das Trennzeichen angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="85a5a-168">**CultureInvariant**: Ignores cultural differences in language when evaluting the delimiter.</span></span> <span data-ttu-id="85a5a-169">Nur mit RegexMatch gültig.</span><span class="sxs-lookup"><span data-stu-id="85a5a-169">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="85a5a-170">**IgnorePatternWhitespace**: ignoriert Leerzeichen ohne Escapezeichen und Kommentare, die mit dem Nummern Zeichen (#) gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="85a5a-170">**IgnorePatternWhitespace**: Ignores unescaped whitespace and comments marked with the number sign (#).</span></span> <span data-ttu-id="85a5a-171">Nur mit RegexMatch gültig.</span><span class="sxs-lookup"><span data-stu-id="85a5a-171">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="85a5a-172">**MultiLine**: der mehrzeilige Modus erzwingt `^` und `$` , um das Anfangs Ende jeder Zeile anstelle von Anfang und Ende der Eingabe Zeichenfolge abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="85a5a-172">**Multiline**: Multiline mode forces `^` and `$` to match the beginning end of every line instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="85a5a-173">**SingleLine**: der SingleLine-Modus behandelt die Eingabe Zeichenfolge als *SingleLine*.</span><span class="sxs-lookup"><span data-stu-id="85a5a-173">**Singleline**: Singleline mode treats the input string as a *SingleLine*.</span></span>
  <span data-ttu-id="85a5a-174">Es erzwingt `.` , dass das Zeichen jedem Zeichen (einschließlich der Zeilenumbrüche) entspricht, anstatt jedes Zeichen mit Ausnahme von Zeilenumbrüche abzugleichen `\n` .</span><span class="sxs-lookup"><span data-stu-id="85a5a-174">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>
- <span data-ttu-id="85a5a-175">**Explizicapture**: ignoriert nicht benannte Übereinstimmungs Gruppen, sodass nur explizite Erfassungs Gruppen in der Ergebnisliste zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="85a5a-175">**ExplicitCapture**: Ignores non-named match groups so that only explicit capture groups are returned in the result list.</span></span> <span data-ttu-id="85a5a-176">Nur mit RegexMatch gültig.</span><span class="sxs-lookup"><span data-stu-id="85a5a-176">Valid only with RegexMatch.</span></span>

## <a name="unary-and-binary-split-operators"></a><span data-ttu-id="85a5a-177">Unäre und binäre Split-Operatoren</span><span class="sxs-lookup"><span data-stu-id="85a5a-177">UNARY and BINARY SPLIT OPERATORS</span></span>

<span data-ttu-id="85a5a-178">Der unäre Split-Operator ( `-split <string>` ) hat Vorrang vor einem Komma.</span><span class="sxs-lookup"><span data-stu-id="85a5a-178">The unary split operator (`-split <string>`) has higher precedence than a comma.</span></span> <span data-ttu-id="85a5a-179">Wenn Sie daher eine durch Trennzeichen getrennte Liste von Zeichen folgen an den unären Split-Operator übermitteln, wird nur die erste Zeichenfolge (vor dem ersten Komma) aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="85a5a-179">As a result, if you submit a comma-separated list of strings to the unary split operator, only the first string (before the first comma) is split.</span></span>

<span data-ttu-id="85a5a-180">Verwenden Sie eines der folgenden Muster, um mehr als eine Zeichenfolge aufzuteilen:</span><span class="sxs-lookup"><span data-stu-id="85a5a-180">Use one of the following patterns to split more than one string:</span></span>

- <span data-ttu-id="85a5a-181">Verwenden des binären Split-Operators ( \<string[]\> -Split \<delimiter\> )</span><span class="sxs-lookup"><span data-stu-id="85a5a-181">Use the binary split operator (\<string[]\> -split \<delimiter\>)</span></span>
- <span data-ttu-id="85a5a-182">Alle Zeichen folgen in Klammern einschließen</span><span class="sxs-lookup"><span data-stu-id="85a5a-182">Enclose all the strings in parentheses</span></span>
- <span data-ttu-id="85a5a-183">Speichern Sie die Zeichen folgen in einer Variablen, und senden Sie die Variable an den Split-Operator.</span><span class="sxs-lookup"><span data-stu-id="85a5a-183">Store the strings in a variable then submit the variable to the split operator</span></span>

<span data-ttu-id="85a5a-184">Betrachten Sie das folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="85a5a-184">Consider the following example:</span></span>

```
PS> -split "1 2", "a b"
1
2
a b
```

```
PS> "1 2", "a b" -split " "
1
2
a
b
```

```
PS> -split ("1 2", "a b")
1
2
a
b
```

```
PS> $a = "1 2", "a b"
PS> -split $a
1
2
a
b
```

## <a name="examples"></a><span data-ttu-id="85a5a-185">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="85a5a-185">EXAMPLES</span></span>

<span data-ttu-id="85a5a-186">Die folgende Anweisung teilt die Zeichenfolge bei Leerraum.</span><span class="sxs-lookup"><span data-stu-id="85a5a-186">The following statement splits the string at whitespace.</span></span>

```powershell
-split "Windows PowerShell 2.0`nWindows PowerShell with remoting"
```

```Output

Windows
PowerShell
2.0
Windows
PowerShell
with
remoting
```

<span data-ttu-id="85a5a-187">Mit der folgenden Anweisung wird die Zeichenfolge bei jedem Komma unterteilt.</span><span class="sxs-lookup"><span data-stu-id="85a5a-187">The following statement splits the string at any comma.</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split ','
```

```Output
Mercury
Venus
Earth
Mars
Jupiter
Saturn
Uranus
Neptune
```

<span data-ttu-id="85a5a-188">Die folgende Anweisung teilt die Zeichenfolge mit dem Muster "er".</span><span class="sxs-lookup"><span data-stu-id="85a5a-188">The following statement splits the string at the pattern "er".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split 'er'
```

```Output
M
cury,Venus,Earth,Mars,Jupit
,Saturn,Uranus,Neptune
```

<span data-ttu-id="85a5a-189">Mit der folgenden Anweisung wird die Unterscheidung nach Groß-/Kleinschreibung beim Buchstaben "N" unterschieden.</span><span class="sxs-lookup"><span data-stu-id="85a5a-189">The following statement performs a case-sensitive split at the letter "N".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -cSplit 'N'
```

```Output
Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,
eptune
```

<span data-ttu-id="85a5a-190">Die folgende Anweisung teilt die Zeichenfolge unter "e" und "t".</span><span class="sxs-lookup"><span data-stu-id="85a5a-190">The following statement splits the string at "e" and "t".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[et]'
```

```Output
M
rcury,V
nus,
ar
h,Mars,Jupi

r,Sa
urn,Uranus,N
p
un
```

<span data-ttu-id="85a5a-191">Mit der folgenden Anweisung wird die Zeichenfolge bei "e" und "r" unterteilt, aber die resultierenden Teil Zeichenfolgen werden auf sechs Teil Zeichenfolgen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="85a5a-191">The following statement splits the string at "e" and "r", but limits the resulting substrings to six substrings.</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[er]', 6
```

```Output
M

cu
y,V
nus,
arth,Mars,Jupiter,Saturn,Uranus,Neptune
```

<span data-ttu-id="85a5a-192">Die folgende Anweisung teilt eine Zeichenfolge in drei Teil Zeichenfolgen auf.</span><span class="sxs-lookup"><span data-stu-id="85a5a-192">The following statement splits a string into three substrings.</span></span>

```powershell
"a,b,c,d,e,f,g,h" -split ",", 3
```

```Output
a
b
c,d,e,f,g,h
```

<span data-ttu-id="85a5a-193">Mit der folgenden Anweisung wird eine Zeichenfolge beginnend am Ende der Zeichenfolge in drei Teil Zeichenfolgen unterteilt.</span><span class="sxs-lookup"><span data-stu-id="85a5a-193">The following statement splits a string into three substrings starting from the end of the string.</span></span>

```powershell
"a,b,c,d,e,f,g,h" -split ",", -3
```

```Output
a,b,c,d,e,f
g
h
```

<span data-ttu-id="85a5a-194">Die folgende Anweisung teilt zwei Zeichen folgen in drei Teil Zeichenfolgen auf.</span><span class="sxs-lookup"><span data-stu-id="85a5a-194">The following statement splits two strings into three substrings.</span></span>
<span data-ttu-id="85a5a-195">(Das Limit wird unabhängig voneinander auf jede Zeichenfolge angewendet.)</span><span class="sxs-lookup"><span data-stu-id="85a5a-195">(The limit is applied to each string independently.)</span></span>

```powershell
"a,b,c,d", "e,f,g,h" -split ",", 3
```

```Output
a
b
c,d
e
f
g,h
```

<span data-ttu-id="85a5a-196">Die folgende Anweisung teilt jede Zeile in der here-Zeichenfolge an der ersten Ziffer.</span><span class="sxs-lookup"><span data-stu-id="85a5a-196">The following statement splits each line in the here-string at the first digit.</span></span> <span data-ttu-id="85a5a-197">Er verwendet die Multiline-Option, um den Anfang jeder Zeile und Zeichenfolge zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="85a5a-197">It uses the Multiline option to recognize the beginning of each line and string.</span></span>

<span data-ttu-id="85a5a-198">Der Wert 0 stellt den Wert "return all" des Parameters "Max-Substrings" dar.</span><span class="sxs-lookup"><span data-stu-id="85a5a-198">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="85a5a-199">Sie können Optionen, wie z. b. Multiline, nur verwenden, wenn der Wert Max-Substrings angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="85a5a-199">You can use options, such as Multiline, only when the Max-substrings value is specified.</span></span>

```powershell
$a = @'
1The first line.
2The second line.
3The third of three lines.
'@
$a -split "^\d", 0, "multiline"
```

```Output

The first line.

The second line.

The third of three lines.
```

<span data-ttu-id="85a5a-200">Die folgende Anweisung verwendet den umgekehrten Schrägstrich, um das Punkt Trennzeichen (.) mit Escapezeichen zu versehen.</span><span class="sxs-lookup"><span data-stu-id="85a5a-200">The following statement uses the backslash character to escape the dot (.) delimiter.</span></span>

<span data-ttu-id="85a5a-201">Mit dem Standardwert RegexMatch wird der in Anführungszeichen (".") eingeschlossene Punkt so interpretiert, dass er mit einem beliebigen Zeichen übereinstimmt, mit Ausnahme eines Zeilen Vorzeichens.</span><span class="sxs-lookup"><span data-stu-id="85a5a-201">With the default, RegexMatch, the dot enclosed in quotation marks (".") is interpreted to match any character except for a newline character.</span></span> <span data-ttu-id="85a5a-202">Folglich gibt die Split-Anweisung für jedes Zeichen mit Ausnahme von Zeilen Freigaben eine Leerzeile zurück.</span><span class="sxs-lookup"><span data-stu-id="85a5a-202">As a result, the Split statement returns a blank line for every character except newline.</span></span>

```powershell
"This.is.a.test" -split "\."
```

```Output
This
is
a
test
```

<span data-ttu-id="85a5a-203">Die folgende Anweisung verwendet die simplematch-Option, um den-Split-Operator anzuweisen, das Punkt Trennzeichen (.) buchstäblich zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="85a5a-203">The following statement uses the SimpleMatch option to direct the -split operator to interpret the dot (.) delimiter literally.</span></span>

<span data-ttu-id="85a5a-204">Der Wert 0 stellt den Wert "return all" des Parameters "Max-Substrings" dar.</span><span class="sxs-lookup"><span data-stu-id="85a5a-204">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="85a5a-205">Sie können Optionen, wie z. b. simplematch, nur verwenden, wenn der Wert Max-Substrings angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="85a5a-205">You can use options, such as SimpleMatch, only when the Max-substrings value is specified.</span></span>

```powershell
"This.is.a.test" -split ".", 0, "simplematch"
```

```Output
This
is
a
test
```

<span data-ttu-id="85a5a-206">Die folgende Anweisung unterteilt die Zeichenfolge in einem von zwei Trennzeichen, je nach dem Wert einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="85a5a-206">The following statement splits the string at one of two delimiters, depending on the value of a variable.</span></span>

```powershell
$i = 1
$c = "LastName, FirstName; Address, City, State, Zip"
$c -split $(if ($i -lt 1) {","} else {";"})
```

```Output
LastName, FirstName
 Address, City, State, Zip
```

## <a name="see-also"></a><span data-ttu-id="85a5a-207">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="85a5a-207">SEE ALSO</span></span>

[<span data-ttu-id="85a5a-208">Split-Path</span><span class="sxs-lookup"><span data-stu-id="85a5a-208">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)

[<span data-ttu-id="85a5a-209">about_Operators</span><span class="sxs-lookup"><span data-stu-id="85a5a-209">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="85a5a-210">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="85a5a-210">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="85a5a-211">about_Join</span><span class="sxs-lookup"><span data-stu-id="85a5a-211">about_Join</span></span>](about_Join.md)
