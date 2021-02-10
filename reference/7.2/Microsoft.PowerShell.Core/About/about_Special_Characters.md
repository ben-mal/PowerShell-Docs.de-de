---
description: Beschreibt die Sonderzeichenfolgen, mit denen gesteuert wird, wie die nächsten Zeichen in der Sequenz von PowerShell interpretiert werden.
Locale: en-US
ms.date: 02/08/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_special_characters?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Special_Characters
ms.openlocfilehash: b21ec1eb5ed0da52cf5eff01eaf3c220d117cf55
ms.sourcegitcommit: 364c3fe46b2069b810107d840be59fe519ea7b4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2021
ms.locfileid: "100100715"
---
# <a name="about-special-characters"></a><span data-ttu-id="1babf-103">Informationen zu Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="1babf-103">About Special Characters</span></span>

## <a name="short-description"></a><span data-ttu-id="1babf-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1babf-104">Short description</span></span>

<span data-ttu-id="1babf-105">Beschreibt die Sonderzeichenfolgen, mit denen gesteuert wird, wie die nächsten Zeichen in der Sequenz von PowerShell interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="1babf-105">Describes the special character sequences that control how PowerShell interprets the next characters in the sequence.</span></span>

## <a name="long-description"></a><span data-ttu-id="1babf-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1babf-106">Long description</span></span>

<span data-ttu-id="1babf-107">PowerShell unterstützt eine Reihe von Sonderzeichenfolgen, die zum Darstellen von Zeichen verwendet werden, die nicht Teil des Standardzeichensatzes sind.</span><span class="sxs-lookup"><span data-stu-id="1babf-107">PowerShell supports a set of special character sequences that are used to represent characters that aren't part of the standard character set.</span></span> <span data-ttu-id="1babf-108">Die _Sequenzen werden häufig als_ Escapesequenzen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1babf-108">The sequences are commonly known as _escape sequences_.</span></span>

<span data-ttu-id="1babf-109">Escapesequenzen beginnen mit dem Graviszeichen-Zeichen, das als großes Akzent (ASCII 96) bezeichnet wird, und Unterscheidung nach Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="1babf-109">Escape sequences begin with the backtick character, known as the grave accent (ASCII 96), and are case-sensitive.</span></span> <span data-ttu-id="1babf-110">Das Graviszeichen-Zeichen kann auch als _Escapezeichen_ bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="1babf-110">The backtick character can also be referred to as the _escape character_.</span></span>

<span data-ttu-id="1babf-111">Escapesequenzen werden nur interpretiert, wenn Sie in Zeichen folgen mit doppelten Anführungszeichen () enthalten sind `"` .</span><span class="sxs-lookup"><span data-stu-id="1babf-111">Escape sequences are only interpreted when contained in double-quoted (`"`) strings.</span></span>

<span data-ttu-id="1babf-112">PowerShell erkennt diese Escapesequenzen:</span><span class="sxs-lookup"><span data-stu-id="1babf-112">PowerShell recognizes these escape sequences:</span></span>

|  <span data-ttu-id="1babf-113">Sequenz</span><span class="sxs-lookup"><span data-stu-id="1babf-113">Sequence</span></span>   |       <span data-ttu-id="1babf-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1babf-114">Description</span></span>       |
| ----------- | ----------------------- |
| `` `0 ``    | <span data-ttu-id="1babf-115">Null</span><span class="sxs-lookup"><span data-stu-id="1babf-115">Null</span></span>                    |
| `` `a ``    | <span data-ttu-id="1babf-116">Warnung</span><span class="sxs-lookup"><span data-stu-id="1babf-116">Alert</span></span>                   |
| `` `b ``    | <span data-ttu-id="1babf-117">Rückschritt</span><span class="sxs-lookup"><span data-stu-id="1babf-117">Backspace</span></span>               |
| `` `e ``    | <span data-ttu-id="1babf-118">Escape</span><span class="sxs-lookup"><span data-stu-id="1babf-118">Escape</span></span>                  |
| `` `f ``    | <span data-ttu-id="1babf-119">Seitenvorschub</span><span class="sxs-lookup"><span data-stu-id="1babf-119">Form feed</span></span>               |
| `` `n ``    | <span data-ttu-id="1babf-120">Zeilenwechsel</span><span class="sxs-lookup"><span data-stu-id="1babf-120">New line</span></span>                |
| `` `r ``    | <span data-ttu-id="1babf-121">Wagenrücklauf</span><span class="sxs-lookup"><span data-stu-id="1babf-121">Carriage return</span></span>         |
| `` `t ``    | <span data-ttu-id="1babf-122">Horizontaler Tabulator</span><span class="sxs-lookup"><span data-stu-id="1babf-122">Horizontal tab</span></span>          |
| `` `u{x} `` | <span data-ttu-id="1babf-123">Unicode-Escapesequenz</span><span class="sxs-lookup"><span data-stu-id="1babf-123">Unicode escape sequence</span></span> |
| `` `v ``    | <span data-ttu-id="1babf-124">Vertikaler Tabulator</span><span class="sxs-lookup"><span data-stu-id="1babf-124">Vertical tab</span></span>            |

<span data-ttu-id="1babf-125">PowerShell verfügt auch über ein spezielles Token, um zu kennzeichnen, wo die Verarbeitung beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1babf-125">PowerShell also has a special token to mark where you want parsing to stop.</span></span> <span data-ttu-id="1babf-126">Alle Zeichen, die diesem Token folgen, werden als Literalwerte verwendet, die nicht interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="1babf-126">All characters that follow this token are used as literal values that aren't interpreted.</span></span>

<span data-ttu-id="1babf-127">Spezielles erteilungstoken:</span><span class="sxs-lookup"><span data-stu-id="1babf-127">Special parsing token:</span></span>

| <span data-ttu-id="1babf-128">Sequenz</span><span class="sxs-lookup"><span data-stu-id="1babf-128">Sequence</span></span> |            <span data-ttu-id="1babf-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1babf-129">Description</span></span>             |
| -------- | ---------------------------------- |
| `--%`    | <span data-ttu-id="1babf-130">Die Verarbeitung der folgenden Elemente wird beendet.</span><span class="sxs-lookup"><span data-stu-id="1babf-130">Stop parsing anything that follows</span></span> |

## <a name="null-0"></a><span data-ttu-id="1babf-131">NULL (' 0)</span><span class="sxs-lookup"><span data-stu-id="1babf-131">Null (\`0)</span></span>

<span data-ttu-id="1babf-132">Das NULL- `` `0 `` Zeichen () wird als leerer Bereich in der PowerShell-Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1babf-132">The null (`` `0 ``) character appears as an empty space in PowerShell output.</span></span>
<span data-ttu-id="1babf-133">Mit dieser Funktion können Sie PowerShell verwenden, um Textdateien zu lesen und zu verarbeiten, die NULL-Zeichen verwenden, z. b. Zeichen folgen Beendigung oder Indikator Beendigungs Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="1babf-133">This functionality allows you to use PowerShell to read and process text files that use null characters, such as string termination or record termination indicators.</span></span> <span data-ttu-id="1babf-134">Das NULL-Sonderzeichen entspricht nicht der- `$null` Variablen, in der ein **null** -Wert gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="1babf-134">The null special character isn't equivalent to the `$null` variable, which stores a **null** value.</span></span>

## <a name="alert-a"></a><span data-ttu-id="1babf-135">Warnung (' a ')</span><span class="sxs-lookup"><span data-stu-id="1babf-135">Alert (\`a)</span></span>

<span data-ttu-id="1babf-136">Das Warn `` `a `` Zeichen () sendet ein Signal an den Sprecher des Computers.</span><span class="sxs-lookup"><span data-stu-id="1babf-136">The alert (`` `a ``) character sends a beep signal to the computer's speaker.</span></span>
<span data-ttu-id="1babf-137">Sie können dieses Zeichen verwenden, um einen Benutzer über eine bevorstehende Aktion zu warnen.</span><span class="sxs-lookup"><span data-stu-id="1babf-137">You can use this character to warn a user about an impending action.</span></span> <span data-ttu-id="1babf-138">Im folgenden Beispiel werden zwei signalsignale an den Sprecher des lokalen Computers gesendet.</span><span class="sxs-lookup"><span data-stu-id="1babf-138">The following example sends two beep signals to the local computer's speaker.</span></span>

```powershell
for ($i = 0; $i -le 1; $i++){"`a"}
```

## <a name="backspace-b"></a><span data-ttu-id="1babf-139">Rücktaste (' b ')</span><span class="sxs-lookup"><span data-stu-id="1babf-139">Backspace (\`b)</span></span>

<span data-ttu-id="1babf-140">Das RÜCKTASTE `` `b `` Zeichen () verschiebt den Cursor um ein Zeichen nach hinten, aber es werden keine Zeichen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1babf-140">The backspace (`` `b ``) character moves the cursor back one character, but it doesn't delete any characters.</span></span>

<span data-ttu-id="1babf-141">Im Beispiel wird die Word- **Sicherung** geschrieben und der Cursor dann zweimal zurück verschoben.</span><span class="sxs-lookup"><span data-stu-id="1babf-141">The example writes the word **backup** and then moves the cursor back twice.</span></span>
<span data-ttu-id="1babf-142">Dann schreibt an der neuen Position ein Leerzeichen gefolgt vom Wort **out**.</span><span class="sxs-lookup"><span data-stu-id="1babf-142">Then, at the new position, writes a space followed by the word **out**.</span></span>

```powershell
"backup`b`b out"
```

```Output
back out
```

## <a name="escape-e"></a><span data-ttu-id="1babf-143">Escapezeichen (' e)</span><span class="sxs-lookup"><span data-stu-id="1babf-143">Escape (\`e)</span></span>

<span data-ttu-id="1babf-144">Das `` `e `` Escapezeichen () wird am häufigsten verwendet, um eine virtuelle Terminal Sequenz (ANSI-Escapesequenz) anzugeben, die die Farbe von Text und andere Text Attribute wie z. b. Fett und Unterstreichung ändert.</span><span class="sxs-lookup"><span data-stu-id="1babf-144">The escape (`` `e ``) character is most commonly used to specify a virtual terminal sequence (ANSI escape sequence) that modifies the color of text and other text attributes such as bolding and underlining.</span></span> <span data-ttu-id="1babf-145">Diese Sequenzen können auch zum Positionieren und Scrollen von Cursorn verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1babf-145">These sequences can also be used for cursor positioning and scrolling.</span></span> <span data-ttu-id="1babf-146">Der PowerShell-Host muss virtuelle Terminal Sequenzen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1babf-146">The PowerShell host must support virtual terminal sequences.</span></span> <span data-ttu-id="1babf-147">Sie können den booleschen Wert von überprüfen `$Host.UI.SupportsVirtualTerminal` , um zu bestimmen, ob diese ANSI-Sequenzen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1babf-147">You can check the boolean value of `$Host.UI.SupportsVirtualTerminal` to determine if these ANSI sequences are supported.</span></span>

<span data-ttu-id="1babf-148">Weitere Informationen zu ANSI-Escapesequenzen finden Sie unter [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="1babf-148">For more information about ANSI escape sequences, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

<span data-ttu-id="1babf-149">Im folgenden Beispiel wird Text mit einer grünen Vordergrundfarbe ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="1babf-149">The following example outputs text with a green foreground color.</span></span>

```powershell
$fgColor = 32 # green
"`e[${fgColor}mGreen text`e[0m"
```

```Output
Green text
```

## <a name="form-feed-f"></a><span data-ttu-id="1babf-150">Formularfeed ("f")</span><span class="sxs-lookup"><span data-stu-id="1babf-150">Form feed (\`f)</span></span>

<span data-ttu-id="1babf-151">Der Form-Feed ( `` `f `` ) ist eine Druck Anweisung, die die aktuelle Seite auswirft und auf der nächsten Seite den Druckvorgang fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="1babf-151">The form feed (`` `f ``) character is a print instruction that ejects the current page and continues printing on the next page.</span></span> <span data-ttu-id="1babf-152">Das Formular Vorschub Zeichen wirkt sich nur auf gedruckte Dokumente aus.</span><span class="sxs-lookup"><span data-stu-id="1babf-152">The form feed character only affects printed documents.</span></span> <span data-ttu-id="1babf-153">Die Bildschirmausgabe wird nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="1babf-153">It doesn't affect screen output.</span></span>

## <a name="new-line-n"></a><span data-ttu-id="1babf-154">Neue Zeile (' n)</span><span class="sxs-lookup"><span data-stu-id="1babf-154">New line (\`n)</span></span>

<span data-ttu-id="1babf-155">Das neue Zeilen `` `n `` Umbruch Zeichen () fügt einen Zeilenumbruch direkt hinter das Zeichen ein.</span><span class="sxs-lookup"><span data-stu-id="1babf-155">The new line (`` `n ``) character inserts a line break immediately after the character.</span></span>

<span data-ttu-id="1babf-156">In diesem Beispiel wird gezeigt, wie Sie mit dem Zeilenendezeichen Zeilenumbrüche in einem `Write-Host` Befehl erstellen.</span><span class="sxs-lookup"><span data-stu-id="1babf-156">This example shows how to use the new line character to create line breaks in a `Write-Host` command.</span></span>

```powershell
"There are two line breaks to create a blank line`n`nbetween the words."
```

```Output
There are two line breaks to create a blank line

between the words.
```

## <a name="carriage-return-r"></a><span data-ttu-id="1babf-157">Wagen Rücklauf ("r")</span><span class="sxs-lookup"><span data-stu-id="1babf-157">Carriage return (\`r)</span></span>

<span data-ttu-id="1babf-158">Das Wagen Rücklauf `` `r `` Zeichen () verschiebt den Ausgabe Cursor an den Anfang der aktuellen Zeile und setzt das Schreiben fort.</span><span class="sxs-lookup"><span data-stu-id="1babf-158">The carriage return (`` `r ``) character moves the output cursor to the beginning of the current line and continues writing.</span></span> <span data-ttu-id="1babf-159">Alle Zeichen in der aktuellen Zeile werden überschrieben.</span><span class="sxs-lookup"><span data-stu-id="1babf-159">Any characters on the current line are overwritten.</span></span>

<span data-ttu-id="1babf-160">In diesem Beispiel wird der Text vor dem Wagen Rücklauf überschrieben.</span><span class="sxs-lookup"><span data-stu-id="1babf-160">In this example, the text before the carriage return is overwritten.</span></span>

```powershell
Write-Host "These characters are overwritten.`rI want this text instead "
```

<span data-ttu-id="1babf-161">Beachten Sie, dass der Text vor dem `` `r `` Zeichen nicht gelöscht wird. er wird überschrieben.</span><span class="sxs-lookup"><span data-stu-id="1babf-161">Notice that the text before the `` `r `` character is not deleted, it is overwritten.</span></span>

```Output
I want this text instead written.
```

## <a name="horizontal-tab-t"></a><span data-ttu-id="1babf-162">Horizontale Registerkarte ('t)</span><span class="sxs-lookup"><span data-stu-id="1babf-162">Horizontal tab (\`t)</span></span>

<span data-ttu-id="1babf-163">Das horizontale Tabulator `` `t `` Zeichen () wechselt zum nächsten Tabstopp und setzt den Schreibvorgang an diesem Punkt fort.</span><span class="sxs-lookup"><span data-stu-id="1babf-163">The horizontal tab (`` `t ``) character advances to the next tab stop and continues writing at that point.</span></span> <span data-ttu-id="1babf-164">Standardmäßig verfügt die PowerShell-Konsole über einen Tabstopp in jedem achten Bereich.</span><span class="sxs-lookup"><span data-stu-id="1babf-164">By default, the PowerShell console has a tab stop at every eighth space.</span></span>

<span data-ttu-id="1babf-165">In diesem Beispiel werden zwei Registerkarten zwischen den einzelnen Spalten eingefügt.</span><span class="sxs-lookup"><span data-stu-id="1babf-165">This example inserts two tabs between each column.</span></span>

```powershell
"Column1`t`tColumn2`t`tColumn3"
```

```Output
Column1         Column2         Column3
```

## <a name="unicode-character-ux"></a><span data-ttu-id="1babf-166">Unicode-Zeichen (' u {x})</span><span class="sxs-lookup"><span data-stu-id="1babf-166">Unicode character (\`u{x})</span></span>

<span data-ttu-id="1babf-167">Die Unicode-Escapesequenz ( `` `u{x} `` ) ermöglicht es Ihnen, ein beliebiges Unicode-Zeichen durch die hexadezimale Darstellung des zugehörigen Code Punkts anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1babf-167">The Unicode escape sequence (`` `u{x} ``) allows you to specify any Unicode character by the hexadecimal representation of its code point.</span></span> <span data-ttu-id="1babf-168">Dies schließt Unicode-Zeichen oberhalb der grundlegenden mehrsprachigen Ebene (> `0xFFFF` ) ein, die Emoji-Zeichen wie das " **Thumbs up** ()"-Zeichen enthält `` `u{1F44D} `` .</span><span class="sxs-lookup"><span data-stu-id="1babf-168">This includes Unicode characters above the Basic Multilingual Plane (> `0xFFFF`) which includes emoji characters such as the **thumbs up** (`` `u{1F44D} ``) character.</span></span> <span data-ttu-id="1babf-169">Die Unicode-Escapesequenz erfordert mindestens eine hexadezimale Ziffer und unterstützt bis zu sechs hexadezimale Ziffern.</span><span class="sxs-lookup"><span data-stu-id="1babf-169">The Unicode escape sequence requires at least one hexadecimal digit and supports up to six hexadecimal digits.</span></span> <span data-ttu-id="1babf-170">Der maximale Hexadezimalwert für die Sequenz ist `10FFFF` .</span><span class="sxs-lookup"><span data-stu-id="1babf-170">The maximum hexadecimal value for the sequence is `10FFFF`.</span></span>

<span data-ttu-id="1babf-171">In diesem Beispiel wird das **nach-unten-Pfeil** Symbol (&#x2195;) ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="1babf-171">This example outputs the **up down arrow** (&#x2195;) symbol.</span></span>

```powershell
"`u{2195}"
```

## <a name="vertical-tab-v"></a><span data-ttu-id="1babf-172">Senkrechter Tabulator (' v)</span><span class="sxs-lookup"><span data-stu-id="1babf-172">Vertical tab (\`v)</span></span>

<span data-ttu-id="1babf-173">Der senkrechte `` `v `` Tabstopp Zeichen () wechselt zum nächsten vertikalen Tabstopp und schreibt die verbleibende Ausgabe an diesem Punkt.</span><span class="sxs-lookup"><span data-stu-id="1babf-173">The vertical tab (`` `v ``) character advances to the next vertical tab stop and writes the remaining output at that point.</span></span> <span data-ttu-id="1babf-174">Das Rendering der vertikalen Registerkarte ist Gerät und Terminal abhängig.</span><span class="sxs-lookup"><span data-stu-id="1babf-174">The rendering of the the vertical tab is device and terminal dependent.</span></span>

```powershell
Write-Host "There is a vertical tab`vbetween the words."
```

<span data-ttu-id="1babf-175">In den folgenden Beispielen wird die gerenderte Ausgabe der vertikalen Registerkarte in einigen gängigen Umgebungen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1babf-175">The following examples show the rendered output of the vertical tab in some common environments.</span></span>

<span data-ttu-id="1babf-176">In der Windows-Konsolen Host Anwendung wird ( `` `v `` ) als Sonderzeichen interpretiert, und es wird kein zusätzlicher Abstand hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1babf-176">The Windows Console host application interprets (`` `v ``) as a special character with no extra spacing added.</span></span>

```Output
There is a vertical tab♂between the words.
```

<span data-ttu-id="1babf-177">Das [Windows-Terminal](https://www.microsoft.com/p/windows-terminal/9n0dx20hk701) rendert das vertikale Tabstopp Zeichen als Wagen Rücklauf-und Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="1babf-177">The [Windows Terminal](https://www.microsoft.com/p/windows-terminal/9n0dx20hk701) renders the vertical tab character as a carriage return and line feed.</span></span> <span data-ttu-id="1babf-178">Der Rest der Ausgabe wird am Anfang der nächsten Zeile ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="1babf-178">The rest of the output is printed at the beginning of the next line.</span></span>

```Output
There is a vertical tab
between the words.
```

<span data-ttu-id="1babf-179">Auf Druckern oder UNIX-basierten Konsolen wechselt das vertikale Tabstopp Zeichen zur nächsten Zeile und schreibt die verbleibende Ausgabe an diesem Punkt.</span><span class="sxs-lookup"><span data-stu-id="1babf-179">On printers or in a unix-based consoles, the vertical tab character advances to the next line and writes the remaining output at that point.</span></span>

```Output
There is a vertical tab
                       between the words.
```

## <a name="stop-parsing-token---"></a><span data-ttu-id="1babf-180">Stoppt das-Element (--%).</span><span class="sxs-lookup"><span data-stu-id="1babf-180">Stop-parsing token (--%)</span></span>

<span data-ttu-id="1babf-181">Das Token zum Verhindern von Stopps ( `--%` ) verhindert, dass PowerShell Zeichen folgen als PowerShell-Befehle und-Ausdrücke interpretiert.</span><span class="sxs-lookup"><span data-stu-id="1babf-181">The stop-parsing (`--%`) token prevents PowerShell from interpreting strings as PowerShell commands and expressions.</span></span> <span data-ttu-id="1babf-182">Dadurch können diese Zeichen folgen zur Interpretation an andere Programme übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="1babf-182">This allows those strings to be passed to other programs for interpretation.</span></span>

<span data-ttu-id="1babf-183">Platzieren Sie das Ende-Parsing-Token nach dem Programmnamen und vor Programm Argumenten, die möglicherweise Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="1babf-183">Place the stop-parsing token after the program name and before program arguments that might cause errors.</span></span>

<span data-ttu-id="1babf-184">In diesem Beispiel verwendet der `Icacls` Befehl das Ende-Element-Token.</span><span class="sxs-lookup"><span data-stu-id="1babf-184">In this example, the `Icacls` command uses the stop-parsing token.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="1babf-185">PowerShell sendet die folgende Zeichenfolge an `Icacls` .</span><span class="sxs-lookup"><span data-stu-id="1babf-185">PowerShell sends the following string to `Icacls`.</span></span>

```
X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="1babf-186">Im Folgenden ist ein weiteres Beispiel angegeben.</span><span class="sxs-lookup"><span data-stu-id="1babf-186">Here is another example.</span></span> <span data-ttu-id="1babf-187">Die **showargs** -Funktion gibt die an Sie über gebenden Werte aus.</span><span class="sxs-lookup"><span data-stu-id="1babf-187">The **showArgs** function outputs the values passed to it.</span></span> <span data-ttu-id="1babf-188">In diesem Beispiel übergeben wir die-Variable mit dem Namen `$HOME` zweimal an die-Funktion.</span><span class="sxs-lookup"><span data-stu-id="1babf-188">In this example, we pass the variable named `$HOME` to the function twice.</span></span>

```powershell
function showArgs {
  "`$args = " + ($args -join '|')
}

showArgs $HOME --% $HOME
```

Sie können in der Ausgabe sehen, dass die Variable für den ersten Parameter `$HOME` von PowerShell interpretiert wird, sodass der Wert der Variablen an die Funktion übergeben wird. <span data-ttu-id="1babf-190">Die zweite Verwendung von `$HOME` erfolgt nach dem Token zum Verhindern von Stopps, sodass die Zeichenfolge "$Home" ohne Interpretation an die Funktion übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="1babf-190">The second use of `$HOME` comes after the stop-parsing token, so the string "$HOME" is passed to the function without interpretation.</span></span>

```Output
$args = C:\Users\username|--%|$HOME
```

<span data-ttu-id="1babf-191">Weitere Informationen zum Token zum Verhindern von Stopps finden Sie unter [about_Parsing](about_Parsing.md).</span><span class="sxs-lookup"><span data-stu-id="1babf-191">For more information about the stop-parsing token, see [about_Parsing](about_Parsing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1babf-192">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1babf-192">See also</span></span>

[<span data-ttu-id="1babf-193">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="1babf-193">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

