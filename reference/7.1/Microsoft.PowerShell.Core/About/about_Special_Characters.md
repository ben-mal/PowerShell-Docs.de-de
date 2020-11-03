---
description: Beschreibt die Sonderzeichenfolgen, mit denen gesteuert wird, wie die nächsten Zeichen in der Sequenz von PowerShell interpretiert werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_special_characters?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Special_Characters
ms.openlocfilehash: 6856d903276f5cbe4db222ac4c5d64ce6939413e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223039"
---
# <a name="about-special-characters"></a><span data-ttu-id="f477f-104">Informationen zu Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="f477f-104">About Special Characters</span></span>

## <a name="short-description"></a><span data-ttu-id="f477f-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f477f-105">Short description</span></span>

<span data-ttu-id="f477f-106">Beschreibt die Sonderzeichenfolgen, mit denen gesteuert wird, wie die nächsten Zeichen in der Sequenz von PowerShell interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="f477f-106">Describes the special character sequences that control how PowerShell interprets the next characters in the sequence.</span></span>

## <a name="long-description"></a><span data-ttu-id="f477f-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f477f-107">Long description</span></span>

<span data-ttu-id="f477f-108">PowerShell unterstützt eine Reihe von Sonderzeichenfolgen, die zum Darstellen von Zeichen verwendet werden, die nicht Teil des Standardzeichensatzes sind.</span><span class="sxs-lookup"><span data-stu-id="f477f-108">PowerShell supports a set of special character sequences that are used to represent characters that aren't part of the standard character set.</span></span> <span data-ttu-id="f477f-109">Die _Sequenzen werden häufig als_ Escapesequenzen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f477f-109">The sequences are commonly known as _escape sequences_.</span></span>

<span data-ttu-id="f477f-110">Escapesequenzen beginnen mit dem Graviszeichen-Zeichen, das als großes Akzent (ASCII 96) bezeichnet wird, und Unterscheidung nach Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="f477f-110">Escape sequences begin with the backtick character, known as the grave accent (ASCII 96), and are case-sensitive.</span></span> <span data-ttu-id="f477f-111">Das Graviszeichen-Zeichen kann auch als _Escapezeichen_ bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="f477f-111">The backtick character can also be referred to as the _escape character_.</span></span>

<span data-ttu-id="f477f-112">Escapesequenzen werden nur interpretiert, wenn Sie in Zeichen folgen mit doppelten Anführungszeichen () enthalten sind `"` .</span><span class="sxs-lookup"><span data-stu-id="f477f-112">Escape sequences are only interpreted when contained in double-quoted (`"`) strings.</span></span>

<span data-ttu-id="f477f-113">PowerShell erkennt diese Escapesequenzen:</span><span class="sxs-lookup"><span data-stu-id="f477f-113">PowerShell recognizes these escape sequences:</span></span>

|  <span data-ttu-id="f477f-114">Sequenz</span><span class="sxs-lookup"><span data-stu-id="f477f-114">Sequence</span></span>   |       <span data-ttu-id="f477f-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f477f-115">Description</span></span>       |
| ----------- | ----------------------- |
| `` `0 ``    | <span data-ttu-id="f477f-116">Null</span><span class="sxs-lookup"><span data-stu-id="f477f-116">Null</span></span>                    |
| `` `a ``    | <span data-ttu-id="f477f-117">Warnung</span><span class="sxs-lookup"><span data-stu-id="f477f-117">Alert</span></span>                   |
| `` `b ``    | <span data-ttu-id="f477f-118">Rückschritt</span><span class="sxs-lookup"><span data-stu-id="f477f-118">Backspace</span></span>               |
| `` `e ``    | <span data-ttu-id="f477f-119">Escape</span><span class="sxs-lookup"><span data-stu-id="f477f-119">Escape</span></span>                  |
| `` `f ``    | <span data-ttu-id="f477f-120">Seitenvorschub</span><span class="sxs-lookup"><span data-stu-id="f477f-120">Form feed</span></span>               |
| `` `n ``    | <span data-ttu-id="f477f-121">Zeilenwechsel</span><span class="sxs-lookup"><span data-stu-id="f477f-121">New line</span></span>                |
| `` `r ``    | <span data-ttu-id="f477f-122">Wagenrücklauf</span><span class="sxs-lookup"><span data-stu-id="f477f-122">Carriage return</span></span>         |
| `` `t ``    | <span data-ttu-id="f477f-123">Horizontaler Tabulator</span><span class="sxs-lookup"><span data-stu-id="f477f-123">Horizontal tab</span></span>          |
| `` `u{x} `` | <span data-ttu-id="f477f-124">Unicode-Escapesequenz</span><span class="sxs-lookup"><span data-stu-id="f477f-124">Unicode escape sequence</span></span> |
| `` `v ``    | <span data-ttu-id="f477f-125">Vertikaler Tabulator</span><span class="sxs-lookup"><span data-stu-id="f477f-125">Vertical tab</span></span>            |

<span data-ttu-id="f477f-126">PowerShell verfügt auch über ein spezielles Token, um zu kennzeichnen, wo die Verarbeitung beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f477f-126">PowerShell also has a special token to mark where you want parsing to stop.</span></span> <span data-ttu-id="f477f-127">Alle Zeichen, die diesem Token folgen, werden als Literalwerte verwendet, die nicht interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="f477f-127">All characters that follow this token are used as literal values that aren't interpreted.</span></span>

<span data-ttu-id="f477f-128">Spezielles erteilungstoken:</span><span class="sxs-lookup"><span data-stu-id="f477f-128">Special parsing token:</span></span>

| <span data-ttu-id="f477f-129">Sequenz</span><span class="sxs-lookup"><span data-stu-id="f477f-129">Sequence</span></span> |            <span data-ttu-id="f477f-130">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f477f-130">Description</span></span>             |
| -------- | ---------------------------------- |
| `--%`    | <span data-ttu-id="f477f-131">Die Verarbeitung der folgenden Elemente wird beendet.</span><span class="sxs-lookup"><span data-stu-id="f477f-131">Stop parsing anything that follows</span></span> |

## <a name="null-0"></a><span data-ttu-id="f477f-132">NULL (' 0)</span><span class="sxs-lookup"><span data-stu-id="f477f-132">Null (\`0)</span></span>

<span data-ttu-id="f477f-133">Das NULL- `` `0 `` Zeichen () wird als leerer Bereich in der PowerShell-Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f477f-133">The null (`` `0 ``) character appears as an empty space in PowerShell output.</span></span>
<span data-ttu-id="f477f-134">Mit dieser Funktion können Sie PowerShell verwenden, um Textdateien zu lesen und zu verarbeiten, die NULL-Zeichen verwenden, z. b. Zeichen folgen Beendigung oder Indikator Beendigungs Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="f477f-134">This functionality allows you to use PowerShell to read and process text files that use null characters, such as string termination or record termination indicators.</span></span> <span data-ttu-id="f477f-135">Das NULL-Sonderzeichen entspricht nicht der- `$null` Variablen, in der ein **null** -Wert gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f477f-135">The null special character isn't equivalent to the `$null` variable, which stores a **null** value.</span></span>

## <a name="alert-a"></a><span data-ttu-id="f477f-136">Warnung (' a ')</span><span class="sxs-lookup"><span data-stu-id="f477f-136">Alert (\`a)</span></span>

<span data-ttu-id="f477f-137">Das Warn `` `a `` Zeichen () sendet ein Signal an den Sprecher des Computers.</span><span class="sxs-lookup"><span data-stu-id="f477f-137">The alert (`` `a ``) character sends a beep signal to the computer's speaker.</span></span>
<span data-ttu-id="f477f-138">Sie können dieses Zeichen verwenden, um einen Benutzer über eine bevorstehende Aktion zu warnen.</span><span class="sxs-lookup"><span data-stu-id="f477f-138">You can use this character to warn a user about an impending action.</span></span> <span data-ttu-id="f477f-139">Im folgenden Beispiel werden zwei signalsignale an den Sprecher des lokalen Computers gesendet.</span><span class="sxs-lookup"><span data-stu-id="f477f-139">The following example sends two beep signals to the local computer's speaker.</span></span>

```powershell
for ($i = 0; $i -le 1; $i++){"`a"}
```

## <a name="backspace-b"></a><span data-ttu-id="f477f-140">Rücktaste (' b ')</span><span class="sxs-lookup"><span data-stu-id="f477f-140">Backspace (\`b)</span></span>

<span data-ttu-id="f477f-141">Das RÜCKTASTE `` `b `` Zeichen () verschiebt den Cursor um ein Zeichen nach hinten, aber es werden keine Zeichen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f477f-141">The backspace (`` `b ``) character moves the cursor back one character, but it doesn't delete any characters.</span></span>

<span data-ttu-id="f477f-142">Im Beispiel wird die Word- **Sicherung** geschrieben und der Cursor dann zweimal zurück verschoben.</span><span class="sxs-lookup"><span data-stu-id="f477f-142">The example writes the word **backup** and then moves the cursor back twice.</span></span>
<span data-ttu-id="f477f-143">Dann schreibt an der neuen Position ein Leerzeichen gefolgt vom Wort **out**.</span><span class="sxs-lookup"><span data-stu-id="f477f-143">Then, at the new position, writes a space followed by the word **out**.</span></span>

```powershell
"backup`b`b out"
```

```Output
back out
```

## <a name="escape-e"></a><span data-ttu-id="f477f-144">Escapezeichen (' e)</span><span class="sxs-lookup"><span data-stu-id="f477f-144">Escape (\`e)</span></span>

<span data-ttu-id="f477f-145">Das `` `e `` Escapezeichen () wird am häufigsten verwendet, um eine virtuelle Terminal Sequenz (ANSI-Escapesequenz) anzugeben, die die Farbe von Text und andere Text Attribute wie z. b. Fett und Unterstreichung ändert.</span><span class="sxs-lookup"><span data-stu-id="f477f-145">The escape (`` `e ``) character is most commonly used to specify a virtual terminal sequence (ANSI escape sequence) that modifies the color of text and other text attributes such as bolding and underlining.</span></span> <span data-ttu-id="f477f-146">Diese Sequenzen können auch zum Positionieren und Scrollen von Cursorn verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f477f-146">These sequences can also be used for cursor positioning and scrolling.</span></span> <span data-ttu-id="f477f-147">Der PowerShell-Host muss virtuelle Terminal Sequenzen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f477f-147">The PowerShell host must support virtual terminal sequences.</span></span> <span data-ttu-id="f477f-148">Sie können den booleschen Wert von überprüfen `$Host.UI.SupportsVirtualTerminal` , um zu bestimmen, ob diese ANSI-Sequenzen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f477f-148">You can check the boolean value of `$Host.UI.SupportsVirtualTerminal` to determine if these ANSI sequences are supported.</span></span>

<span data-ttu-id="f477f-149">Weitere Informationen zu ANSI-Escapesequenzen finden Sie unter [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="f477f-149">For more information about ANSI escape sequences, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

<span data-ttu-id="f477f-150">Im folgenden Beispiel wird Text mit einer grünen Vordergrundfarbe ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="f477f-150">The following example outputs text with a green foreground color.</span></span>

```powershell
$fgColor = 32 # green
"`e[${fgColor}mGreen text`e[0m"
```

```Output
Green text
```

## <a name="form-feed-f"></a><span data-ttu-id="f477f-151">Formularfeed ("f")</span><span class="sxs-lookup"><span data-stu-id="f477f-151">Form feed (\`f)</span></span>

<span data-ttu-id="f477f-152">Der Form-Feed ( `` `f `` ) ist eine Druck Anweisung, die die aktuelle Seite auswirft und auf der nächsten Seite den Druckvorgang fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="f477f-152">The form feed (`` `f ``) character is a print instruction that ejects the current page and continues printing on the next page.</span></span> <span data-ttu-id="f477f-153">Das Formular Vorschub Zeichen wirkt sich nur auf gedruckte Dokumente aus.</span><span class="sxs-lookup"><span data-stu-id="f477f-153">The form feed character only affects printed documents.</span></span> <span data-ttu-id="f477f-154">Die Bildschirmausgabe wird nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="f477f-154">It doesn't affect screen output.</span></span>

## <a name="new-line-n"></a><span data-ttu-id="f477f-155">Neue Zeile (' n)</span><span class="sxs-lookup"><span data-stu-id="f477f-155">New line (\`n)</span></span>

<span data-ttu-id="f477f-156">Das neue Zeilen `` `n `` Umbruch Zeichen () fügt einen Zeilenumbruch direkt hinter das Zeichen ein.</span><span class="sxs-lookup"><span data-stu-id="f477f-156">The new line (`` `n ``) character inserts a line break immediately after the character.</span></span>

<span data-ttu-id="f477f-157">In diesem Beispiel wird gezeigt, wie Sie mit dem Zeilenendezeichen Zeilenumbrüche in einem `Write-Host` Befehl erstellen.</span><span class="sxs-lookup"><span data-stu-id="f477f-157">This example shows how to use the new line character to create line breaks in a `Write-Host` command.</span></span>

```powershell
"There are two line breaks to create a blank line`n`nbetween the words."
```

```Output
There are two line breaks to create a blank line

between the words.
```

## <a name="carriage-return-r"></a><span data-ttu-id="f477f-158">Wagen Rücklauf ("r")</span><span class="sxs-lookup"><span data-stu-id="f477f-158">Carriage return (\`r)</span></span>

<span data-ttu-id="f477f-159">Das Wagen Rücklauf `` `r `` Zeichen () verschiebt den Ausgabe Cursor an den Anfang der aktuellen Zeile und setzt das Schreiben fort.</span><span class="sxs-lookup"><span data-stu-id="f477f-159">The carriage return (`` `r ``) character moves the output cursor to the beginning of the current line and continues writing.</span></span> <span data-ttu-id="f477f-160">Alle Zeichen in der aktuellen Zeile werden überschrieben.</span><span class="sxs-lookup"><span data-stu-id="f477f-160">Any characters on the current line are overwritten.</span></span>

<span data-ttu-id="f477f-161">In diesem Beispiel wird der Text vor dem Wagen Rücklauf überschrieben.</span><span class="sxs-lookup"><span data-stu-id="f477f-161">In this example, the text before the carriage return is overwritten.</span></span>

```powershell
Write-Host "These characters are overwritten.`rI want this text instead "
```

<span data-ttu-id="f477f-162">Beachten Sie, dass der Text vor dem `` `r `` Zeichen nicht gelöscht wird. er wird überschrieben.</span><span class="sxs-lookup"><span data-stu-id="f477f-162">Notice that the text before the `` `r `` character is not deleted, it is overwritten.</span></span>

```Output
I want this text instead written.
```

## <a name="horizontal-tab-t"></a><span data-ttu-id="f477f-163">Horizontale Registerkarte ('t)</span><span class="sxs-lookup"><span data-stu-id="f477f-163">Horizontal tab (\`t)</span></span>

<span data-ttu-id="f477f-164">Das horizontale Tabulator `` `t `` Zeichen () wechselt zum nächsten Tabstopp und setzt den Schreibvorgang an diesem Punkt fort.</span><span class="sxs-lookup"><span data-stu-id="f477f-164">The horizontal tab (`` `t ``) character advances to the next tab stop and continues writing at that point.</span></span> <span data-ttu-id="f477f-165">Standardmäßig verfügt die PowerShell-Konsole über einen Tabstopp in jedem achten Bereich.</span><span class="sxs-lookup"><span data-stu-id="f477f-165">By default, the PowerShell console has a tab stop at every eighth space.</span></span>

<span data-ttu-id="f477f-166">In diesem Beispiel werden zwei Registerkarten zwischen den einzelnen Spalten eingefügt.</span><span class="sxs-lookup"><span data-stu-id="f477f-166">This example inserts two tabs between each column.</span></span>

```powershell
"Column1`t`tColumn2`t`tColumn3"
```

```Output
Column1         Column2         Column3
```

## <a name="unicode-character-ux"></a><span data-ttu-id="f477f-167">Unicode-Zeichen (' u {x})</span><span class="sxs-lookup"><span data-stu-id="f477f-167">Unicode character (\`u{x})</span></span>

<span data-ttu-id="f477f-168">Die Unicode-Escapesequenz ( `` `u{x} `` ) ermöglicht es Ihnen, ein beliebiges Unicode-Zeichen durch die hexadezimale Darstellung des zugehörigen Code Punkts anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f477f-168">The Unicode escape sequence (`` `u{x} ``) allows you to specify any Unicode character by the hexadecimal representation of its code point.</span></span> <span data-ttu-id="f477f-169">Dies schließt Unicode-Zeichen oberhalb der grundlegenden mehrsprachigen Ebene (> `0xFFFF` ) ein, die Emoji-Zeichen wie das " **Thumbs up** ()"-Zeichen enthält `` `u{1F44D} `` .</span><span class="sxs-lookup"><span data-stu-id="f477f-169">This includes Unicode characters above the Basic Multilingual Plane (> `0xFFFF`) which includes emoji characters such as the **thumbs up** (`` `u{1F44D} ``) character.</span></span> <span data-ttu-id="f477f-170">Die Unicode-Escapesequenz erfordert mindestens eine hexadezimale Ziffer und unterstützt bis zu sechs hexadezimale Ziffern.</span><span class="sxs-lookup"><span data-stu-id="f477f-170">The Unicode escape sequence requires at least one hexadecimal digit and supports up to six hexadecimal digits.</span></span> <span data-ttu-id="f477f-171">Der maximale Hexadezimalwert für die Sequenz ist `10FFFF` .</span><span class="sxs-lookup"><span data-stu-id="f477f-171">The maximum hexadecimal value for the sequence is `10FFFF`.</span></span>

<span data-ttu-id="f477f-172">In diesem Beispiel wird das **nach-unten-Pfeil** Symbol (&#x2195;) ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="f477f-172">This example outputs the **up down arrow** (&#x2195;) symbol.</span></span>

```powershell
"`u{2195}"
```

## <a name="vertical-tab-v"></a><span data-ttu-id="f477f-173">Senkrechter Tabulator (' v)</span><span class="sxs-lookup"><span data-stu-id="f477f-173">Vertical tab (\`v)</span></span>

<span data-ttu-id="f477f-174">Das horizontale `` `v `` Tabstopp Zeichen () wechselt zum nächsten vertikalen Tabstopp und schreibt die verbleibende Ausgabe an diesem Punkt.</span><span class="sxs-lookup"><span data-stu-id="f477f-174">The horizontal tab (`` `v ``) character advances to the next vertical tab stop and writes the remaining output at that point.</span></span> <span data-ttu-id="f477f-175">Dies hat keine Auswirkungen auf die standardmäßige Windows-Konsole.</span><span class="sxs-lookup"><span data-stu-id="f477f-175">This has no effect in the default Windows console.</span></span>

```powershell
Write-Host "There is a vertical tab`vbetween the words."
```

<span data-ttu-id="f477f-176">Das folgende Beispiel zeigt die Ausgabe, die Sie auf einem Drucker oder einem anderen Konsolen Host erhalten.</span><span class="sxs-lookup"><span data-stu-id="f477f-176">The following example shows the output you would get on a printer or in a different console host.</span></span>

```Output
There is a vertical tab
                       between the words.
```

## <a name="stop-parsing-token---"></a><span data-ttu-id="f477f-177">Stoppt das-Element (--%).</span><span class="sxs-lookup"><span data-stu-id="f477f-177">Stop-parsing token (--%)</span></span>

<span data-ttu-id="f477f-178">Das Token zum Verhindern von Stopps ( `--%` ) verhindert, dass PowerShell Zeichen folgen als PowerShell-Befehle und-Ausdrücke interpretiert.</span><span class="sxs-lookup"><span data-stu-id="f477f-178">The stop-parsing (`--%`) token prevents PowerShell from interpreting strings as PowerShell commands and expressions.</span></span> <span data-ttu-id="f477f-179">Dadurch können diese Zeichen folgen zur Interpretation an andere Programme übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="f477f-179">This allows those strings to be passed to other programs for interpretation.</span></span>

<span data-ttu-id="f477f-180">Platzieren Sie das Ende-Parsing-Token nach dem Programmnamen und vor Programm Argumenten, die möglicherweise Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="f477f-180">Place the stop-parsing token after the program name and before program arguments that might cause errors.</span></span>

<span data-ttu-id="f477f-181">In diesem Beispiel verwendet der `Icacls` Befehl das Ende-Element-Token.</span><span class="sxs-lookup"><span data-stu-id="f477f-181">In this example, the `Icacls` command uses the stop-parsing token.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="f477f-182">PowerShell sendet die folgende Zeichenfolge an `Icacls` .</span><span class="sxs-lookup"><span data-stu-id="f477f-182">PowerShell sends the following string to `Icacls`.</span></span>

```
X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="f477f-183">Hier ist ein weiteres Beispiel angegeben.</span><span class="sxs-lookup"><span data-stu-id="f477f-183">Here is another example.</span></span> <span data-ttu-id="f477f-184">Die **showargs** -Funktion gibt die an Sie über gebenden Werte aus.</span><span class="sxs-lookup"><span data-stu-id="f477f-184">The **showArgs** function outputs the values passed to it.</span></span> <span data-ttu-id="f477f-185">In diesem Beispiel übergeben wir die-Variable mit dem Namen `$HOME` zweimal an die-Funktion.</span><span class="sxs-lookup"><span data-stu-id="f477f-185">In this example, we pass the variable named `$HOME` to the function twice.</span></span>

```powershell
function showArgs {
  "`$args = " + ($args -join '|')
}

showArgs $HOME --% $HOME
```

Sie können in der Ausgabe sehen, dass die Variable für den ersten Parameter `$HOME` von PowerShell interpretiert wird, sodass der Wert der Variablen an die Funktion übergeben wird. <span data-ttu-id="f477f-187">Die zweite Verwendung von `$HOME` erfolgt nach dem Token zum Verhindern von Stopps, sodass die Zeichenfolge "$Home" ohne Interpretation an die Funktion übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="f477f-187">The second use of `$HOME` comes after the stop-parsing token, so the string "$HOME" is passed to the function without interpretation.</span></span>

```Output
$args = C:\Users\username|--%|$HOME
```

<span data-ttu-id="f477f-188">Weitere Informationen zum Token zum Verhindern von Stopps finden Sie unter [about_Parsing](about_Parsing.md).</span><span class="sxs-lookup"><span data-stu-id="f477f-188">For more information about the stop-parsing token, see [about_Parsing](about_Parsing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f477f-189">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="f477f-189">See also</span></span>

[<span data-ttu-id="f477f-190">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="f477f-190">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

