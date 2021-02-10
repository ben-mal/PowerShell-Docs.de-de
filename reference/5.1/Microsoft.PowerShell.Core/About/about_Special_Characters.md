---
description: Beschreibt die Sonderzeichenfolgen, mit denen gesteuert wird, wie die nächsten Zeichen in der Sequenz von PowerShell interpretiert werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 02/08/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_special_characters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Special_Characters
ms.openlocfilehash: 7e0ea9298dd85627c08298917464cb005f4f37ff
ms.sourcegitcommit: 364c3fe46b2069b810107d840be59fe519ea7b4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2021
ms.locfileid: "100100732"
---
# <a name="about-special-characters"></a><span data-ttu-id="e6d48-104">Informationen zu Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="e6d48-104">About Special Characters</span></span>

## <a name="short-description"></a><span data-ttu-id="e6d48-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6d48-105">Short description</span></span>

<span data-ttu-id="e6d48-106">Beschreibt die Sonderzeichenfolgen, mit denen gesteuert wird, wie die nächsten Zeichen in der Sequenz von PowerShell interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="e6d48-106">Describes the special character sequences that control how PowerShell interprets the next characters in the sequence.</span></span>

## <a name="long-description"></a><span data-ttu-id="e6d48-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6d48-107">Long description</span></span>

<span data-ttu-id="e6d48-108">PowerShell unterstützt eine Reihe von Sonderzeichenfolgen, die zum Darstellen von Zeichen verwendet werden, die nicht Teil des Standardzeichensatzes sind.</span><span class="sxs-lookup"><span data-stu-id="e6d48-108">PowerShell supports a set of special character sequences that are used to represent characters that aren't part of the standard character set.</span></span> <span data-ttu-id="e6d48-109">Die _Sequenzen werden häufig als_ Escapesequenzen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e6d48-109">The sequences are commonly known as _escape sequences_.</span></span>

<span data-ttu-id="e6d48-110">Escapesequenzen beginnen mit dem Graviszeichen-Zeichen, das als großes Akzent (ASCII 96) bezeichnet wird, und Unterscheidung nach Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="e6d48-110">Escape sequences begin with the backtick character, known as the grave accent (ASCII 96), and are case-sensitive.</span></span> <span data-ttu-id="e6d48-111">Das Graviszeichen-Zeichen kann auch als _Escapezeichen_ bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="e6d48-111">The backtick character can also be referred to as the _escape character_.</span></span>

<span data-ttu-id="e6d48-112">Escapesequenzen werden nur interpretiert, wenn Sie in Zeichen folgen mit doppelten Anführungszeichen () enthalten sind `"` .</span><span class="sxs-lookup"><span data-stu-id="e6d48-112">Escape sequences are only interpreted when contained in double-quoted (`"`) strings.</span></span>

<span data-ttu-id="e6d48-113">PowerShell erkennt diese Escapesequenzen:</span><span class="sxs-lookup"><span data-stu-id="e6d48-113">PowerShell recognizes these escape sequences:</span></span>

|  <span data-ttu-id="e6d48-114">Sequenz</span><span class="sxs-lookup"><span data-stu-id="e6d48-114">Sequence</span></span>   |       <span data-ttu-id="e6d48-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6d48-115">Description</span></span>       |
| ----------- | ----------------------- |
| `` `0 ``    | <span data-ttu-id="e6d48-116">Null</span><span class="sxs-lookup"><span data-stu-id="e6d48-116">Null</span></span>                    |
| `` `a ``    | <span data-ttu-id="e6d48-117">Warnung</span><span class="sxs-lookup"><span data-stu-id="e6d48-117">Alert</span></span>                   |
| `` `b ``    | <span data-ttu-id="e6d48-118">Rückschritt</span><span class="sxs-lookup"><span data-stu-id="e6d48-118">Backspace</span></span>               |
| `` `f ``    | <span data-ttu-id="e6d48-119">Seitenvorschub</span><span class="sxs-lookup"><span data-stu-id="e6d48-119">Form feed</span></span>               |
| `` `n ``    | <span data-ttu-id="e6d48-120">Zeilenwechsel</span><span class="sxs-lookup"><span data-stu-id="e6d48-120">New line</span></span>                |
| `` `r ``    | <span data-ttu-id="e6d48-121">Wagenrücklauf</span><span class="sxs-lookup"><span data-stu-id="e6d48-121">Carriage return</span></span>         |
| `` `t ``    | <span data-ttu-id="e6d48-122">Horizontaler Tabulator</span><span class="sxs-lookup"><span data-stu-id="e6d48-122">Horizontal tab</span></span>          |
| `` `v ``    | <span data-ttu-id="e6d48-123">Vertikaler Tabulator</span><span class="sxs-lookup"><span data-stu-id="e6d48-123">Vertical tab</span></span>            |

<span data-ttu-id="e6d48-124">PowerShell verfügt auch über ein spezielles Token, um zu kennzeichnen, wo die Verarbeitung beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e6d48-124">PowerShell also has a special token to mark where you want parsing to stop.</span></span> <span data-ttu-id="e6d48-125">Alle Zeichen, die diesem Token folgen, werden als Literalwerte verwendet, die nicht interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="e6d48-125">All characters that follow this token are used as literal values that aren't interpreted.</span></span>

<span data-ttu-id="e6d48-126">Spezielles erteilungstoken:</span><span class="sxs-lookup"><span data-stu-id="e6d48-126">Special parsing token:</span></span>

| <span data-ttu-id="e6d48-127">Sequenz</span><span class="sxs-lookup"><span data-stu-id="e6d48-127">Sequence</span></span> |            <span data-ttu-id="e6d48-128">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6d48-128">Description</span></span>             |
| -------- | ---------------------------------- |
| `--%`    | <span data-ttu-id="e6d48-129">Die Verarbeitung der folgenden Elemente wird beendet.</span><span class="sxs-lookup"><span data-stu-id="e6d48-129">Stop parsing anything that follows</span></span> |

## <a name="null-0"></a><span data-ttu-id="e6d48-130">NULL (' 0)</span><span class="sxs-lookup"><span data-stu-id="e6d48-130">Null (\`0)</span></span>

<span data-ttu-id="e6d48-131">Das NULL- `` `0 `` Zeichen () wird als leerer Bereich in der PowerShell-Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6d48-131">The null (`` `0 ``) character appears as an empty space in PowerShell output.</span></span>
<span data-ttu-id="e6d48-132">Mit dieser Funktion können Sie PowerShell verwenden, um Textdateien zu lesen und zu verarbeiten, die NULL-Zeichen verwenden, z. b. Zeichen folgen Beendigung oder Indikator Beendigungs Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="e6d48-132">This functionality allows you to use PowerShell to read and process text files that use null characters, such as string termination or record termination indicators.</span></span> <span data-ttu-id="e6d48-133">Das NULL-Sonderzeichen entspricht nicht der- `$null` Variablen, in der ein **null** -Wert gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="e6d48-133">The null special character isn't equivalent to the `$null` variable, which stores a **null** value.</span></span>

## <a name="alert-a"></a><span data-ttu-id="e6d48-134">Warnung (' a ')</span><span class="sxs-lookup"><span data-stu-id="e6d48-134">Alert (\`a)</span></span>

<span data-ttu-id="e6d48-135">Das Warn `` `a `` Zeichen () sendet ein Signal an den Sprecher des Computers.</span><span class="sxs-lookup"><span data-stu-id="e6d48-135">The alert (`` `a ``) character sends a beep signal to the computer's speaker.</span></span>
<span data-ttu-id="e6d48-136">Sie können dieses Zeichen verwenden, um einen Benutzer über eine bevorstehende Aktion zu warnen.</span><span class="sxs-lookup"><span data-stu-id="e6d48-136">You can use this character to warn a user about an impending action.</span></span> <span data-ttu-id="e6d48-137">Im folgenden Beispiel werden zwei signalsignale an den Sprecher des lokalen Computers gesendet.</span><span class="sxs-lookup"><span data-stu-id="e6d48-137">The following example sends two beep signals to the local computer's speaker.</span></span>

```powershell
for ($i = 0; $i -le 1; $i++){"`a"}
```

## <a name="backspace-b"></a><span data-ttu-id="e6d48-138">Rücktaste (' b ')</span><span class="sxs-lookup"><span data-stu-id="e6d48-138">Backspace (\`b)</span></span>

<span data-ttu-id="e6d48-139">Das RÜCKTASTE `` `b `` Zeichen () verschiebt den Cursor um ein Zeichen nach hinten, aber es werden keine Zeichen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="e6d48-139">The backspace (`` `b ``) character moves the cursor back one character, but it doesn't delete any characters.</span></span>

<span data-ttu-id="e6d48-140">Im Beispiel wird die Word- **Sicherung** geschrieben und der Cursor dann zweimal zurück verschoben.</span><span class="sxs-lookup"><span data-stu-id="e6d48-140">The example writes the word **backup** and then moves the cursor back twice.</span></span>
<span data-ttu-id="e6d48-141">Dann schreibt an der neuen Position ein Leerzeichen gefolgt vom Wort **out**.</span><span class="sxs-lookup"><span data-stu-id="e6d48-141">Then, at the new position, writes a space followed by the word **out**.</span></span>

```powershell
"backup`b`b out"
```

```Output
back out
```

## <a name="form-feed-f"></a><span data-ttu-id="e6d48-142">Formularfeed ("f")</span><span class="sxs-lookup"><span data-stu-id="e6d48-142">Form feed (\`f)</span></span>

<span data-ttu-id="e6d48-143">Der Form-Feed ( `` `f `` ) ist eine Druck Anweisung, die die aktuelle Seite auswirft und auf der nächsten Seite den Druckvorgang fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="e6d48-143">The form feed (`` `f ``) character is a print instruction that ejects the current page and continues printing on the next page.</span></span> <span data-ttu-id="e6d48-144">Das Formular Vorschub Zeichen wirkt sich nur auf gedruckte Dokumente aus.</span><span class="sxs-lookup"><span data-stu-id="e6d48-144">The form feed character only affects printed documents.</span></span> <span data-ttu-id="e6d48-145">Die Bildschirmausgabe wird nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="e6d48-145">It doesn't affect screen output.</span></span>

## <a name="new-line-n"></a><span data-ttu-id="e6d48-146">Neue Zeile (' n)</span><span class="sxs-lookup"><span data-stu-id="e6d48-146">New line (\`n)</span></span>

<span data-ttu-id="e6d48-147">Das neue Zeilen `` `n `` Umbruch Zeichen () fügt einen Zeilenumbruch direkt hinter das Zeichen ein.</span><span class="sxs-lookup"><span data-stu-id="e6d48-147">The new line (`` `n ``) character inserts a line break immediately after the character.</span></span>

<span data-ttu-id="e6d48-148">In diesem Beispiel wird gezeigt, wie Sie mit dem Zeilenendezeichen Zeilenumbrüche in einem `Write-Host` Befehl erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6d48-148">This example shows how to use the new line character to create line breaks in a `Write-Host` command.</span></span>

```powershell
"There are two line breaks to create a blank line`n`nbetween the words."
```

```Output
There are two line breaks to create a blank line

between the words.
```

## <a name="carriage-return-r"></a><span data-ttu-id="e6d48-149">Wagen Rücklauf ("r")</span><span class="sxs-lookup"><span data-stu-id="e6d48-149">Carriage return (\`r)</span></span>

<span data-ttu-id="e6d48-150">Das Wagen Rücklauf `` `r `` Zeichen () verschiebt den Ausgabe Cursor an den Anfang der aktuellen Zeile und setzt das Schreiben fort.</span><span class="sxs-lookup"><span data-stu-id="e6d48-150">The carriage return (`` `r ``) character moves the output cursor to the beginning of the current line and continues writing.</span></span> <span data-ttu-id="e6d48-151">Alle Zeichen in der aktuellen Zeile werden überschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6d48-151">Any characters on the current line are overwritten.</span></span>

<span data-ttu-id="e6d48-152">In diesem Beispiel wird der Text vor dem Wagen Rücklauf überschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6d48-152">In this example, the text before the carriage return is overwritten.</span></span>

```powershell
Write-Host "These characters are overwritten.`rI want this text instead "
```

<span data-ttu-id="e6d48-153">Beachten Sie, dass der Text vor dem `` `r `` Zeichen nicht gelöscht wird. er wird überschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6d48-153">Notice that the text before the `` `r `` character is not deleted, it is overwritten.</span></span>

```Output
I want this text instead written.
```

## <a name="horizontal-tab-t"></a><span data-ttu-id="e6d48-154">Horizontale Registerkarte ('t)</span><span class="sxs-lookup"><span data-stu-id="e6d48-154">Horizontal tab (\`t)</span></span>

<span data-ttu-id="e6d48-155">Das horizontale Tabulator `` `t `` Zeichen () wechselt zum nächsten Tabstopp und setzt den Schreibvorgang an diesem Punkt fort.</span><span class="sxs-lookup"><span data-stu-id="e6d48-155">The horizontal tab (`` `t ``) character advances to the next tab stop and continues writing at that point.</span></span> <span data-ttu-id="e6d48-156">Standardmäßig verfügt die PowerShell-Konsole über einen Tabstopp in jedem achten Bereich.</span><span class="sxs-lookup"><span data-stu-id="e6d48-156">By default, the PowerShell console has a tab stop at every eighth space.</span></span>

<span data-ttu-id="e6d48-157">In diesem Beispiel werden zwei Registerkarten zwischen den einzelnen Spalten eingefügt.</span><span class="sxs-lookup"><span data-stu-id="e6d48-157">This example inserts two tabs between each column.</span></span>

```powershell
"Column1`t`tColumn2`t`tColumn3"
```

```Output
Column1         Column2         Column3
```

## <a name="vertical-tab-v"></a><span data-ttu-id="e6d48-158">Senkrechter Tabulator (' v)</span><span class="sxs-lookup"><span data-stu-id="e6d48-158">Vertical tab (\`v)</span></span>

<span data-ttu-id="e6d48-159">Der senkrechte `` `v `` Tabstopp Zeichen () wechselt zum nächsten vertikalen Tabstopp und schreibt die verbleibende Ausgabe an diesem Punkt.</span><span class="sxs-lookup"><span data-stu-id="e6d48-159">The vertical tab (`` `v ``) character advances to the next vertical tab stop and writes the remaining output at that point.</span></span> <span data-ttu-id="e6d48-160">Das Rendering der vertikalen Registerkarte ist Gerät und Terminal abhängig.</span><span class="sxs-lookup"><span data-stu-id="e6d48-160">The rendering of the the vertical tab is device and terminal dependent.</span></span>

```powershell
Write-Host "There is a vertical tab`vbetween the words."
```

<span data-ttu-id="e6d48-161">In den folgenden Beispielen wird die gerenderte Ausgabe der vertikalen Registerkarte in einigen gängigen Umgebungen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e6d48-161">The following examples show the rendered output of the vertical tab in some common environments.</span></span>

<span data-ttu-id="e6d48-162">In der Windows-Konsolen Host Anwendung wird ( `` `v `` ) als Sonderzeichen interpretiert, und es wird kein zusätzlicher Abstand hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e6d48-162">The Windows Console host application interprets (`` `v ``) as a special character with no extra spacing added.</span></span>

```Output
There is a vertical tab♂between the words.
```

<span data-ttu-id="e6d48-163">Das [Windows-Terminal](https://www.microsoft.com/p/windows-terminal/9n0dx20hk701) rendert das vertikale Tabstopp Zeichen als Wagen Rücklauf-und Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="e6d48-163">The [Windows Terminal](https://www.microsoft.com/p/windows-terminal/9n0dx20hk701) renders the vertical tab character as a carriage return and line feed.</span></span> <span data-ttu-id="e6d48-164">Der Rest der Ausgabe wird am Anfang der nächsten Zeile ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="e6d48-164">The rest of the output is printed at the beginning of the next line.</span></span>

```Output
There is a vertical tab
between the words.
```

<span data-ttu-id="e6d48-165">Auf Druckern oder UNIX-basierten Konsolen wechselt das vertikale Tabstopp Zeichen zur nächsten Zeile und schreibt die verbleibende Ausgabe an diesem Punkt.</span><span class="sxs-lookup"><span data-stu-id="e6d48-165">On printers or in a unix-based consoles, the vertical tab character advances to the next line and writes the remaining output at that point.</span></span>

```Output
There is a vertical tab
                       between the words.
```

## <a name="stop-parsing-token---"></a><span data-ttu-id="e6d48-166">Stoppt das-Element (--%).</span><span class="sxs-lookup"><span data-stu-id="e6d48-166">Stop-parsing token (--%)</span></span>

<span data-ttu-id="e6d48-167">Das Token zum Verhindern von Stopps ( `--%` ) verhindert, dass PowerShell Zeichen folgen als PowerShell-Befehle und-Ausdrücke interpretiert.</span><span class="sxs-lookup"><span data-stu-id="e6d48-167">The stop-parsing (`--%`) token prevents PowerShell from interpreting strings as PowerShell commands and expressions.</span></span> <span data-ttu-id="e6d48-168">Dadurch können diese Zeichen folgen zur Interpretation an andere Programme übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="e6d48-168">This allows those strings to be passed to other programs for interpretation.</span></span>

<span data-ttu-id="e6d48-169">Platzieren Sie das Ende-Parsing-Token nach dem Programmnamen und vor Programm Argumenten, die möglicherweise Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="e6d48-169">Place the stop-parsing token after the program name and before program arguments that might cause errors.</span></span>

<span data-ttu-id="e6d48-170">In diesem Beispiel verwendet der `Icacls` Befehl das Ende-Element-Token.</span><span class="sxs-lookup"><span data-stu-id="e6d48-170">In this example, the `Icacls` command uses the stop-parsing token.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="e6d48-171">PowerShell sendet die folgende Zeichenfolge an `Icacls` .</span><span class="sxs-lookup"><span data-stu-id="e6d48-171">PowerShell sends the following string to `Icacls`.</span></span>

```
X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="e6d48-172">Im Folgenden ist ein weiteres Beispiel angegeben.</span><span class="sxs-lookup"><span data-stu-id="e6d48-172">Here is another example.</span></span> <span data-ttu-id="e6d48-173">Die **showargs** -Funktion gibt die an Sie über gebenden Werte aus.</span><span class="sxs-lookup"><span data-stu-id="e6d48-173">The **showArgs** function outputs the values passed to it.</span></span> <span data-ttu-id="e6d48-174">In diesem Beispiel übergeben wir die-Variable mit dem Namen `$HOME` zweimal an die-Funktion.</span><span class="sxs-lookup"><span data-stu-id="e6d48-174">In this example, we pass the variable named `$HOME` to the function twice.</span></span>

```powershell
function showArgs {
  "`$args = " + ($args -join '|')
}

showArgs $HOME --% $HOME
```

Sie können in der Ausgabe sehen, dass die Variable für den ersten Parameter `$HOME` von PowerShell interpretiert wird, sodass der Wert der Variablen an die Funktion übergeben wird. <span data-ttu-id="e6d48-176">Die zweite Verwendung von `$HOME` erfolgt nach dem Token zum Verhindern von Stopps, sodass die Zeichenfolge "$Home" ohne Interpretation an die Funktion übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="e6d48-176">The second use of `$HOME` comes after the stop-parsing token, so the string "$HOME" is passed to the function without interpretation.</span></span>

```Output
$args = C:\Users\username|--%|$HOME
```

<span data-ttu-id="e6d48-177">Weitere Informationen zum Token zum Verhindern von Stopps finden Sie unter [about_Parsing](about_Parsing.md).</span><span class="sxs-lookup"><span data-stu-id="e6d48-177">For more information about the stop-parsing token, see [about_Parsing](about_Parsing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e6d48-178">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e6d48-178">See also</span></span>

[<span data-ttu-id="e6d48-179">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="e6d48-179">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)
