---
description: Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über psread Line
ms.openlocfilehash: ad6e85a30f866cb332c89a4c36f42231f511f5ae
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224919"
---
# <a name="psreadline"></a><span data-ttu-id="df7ea-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="df7ea-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="df7ea-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="df7ea-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="df7ea-106">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="df7ea-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="df7ea-107">Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="df7ea-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="df7ea-108">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="df7ea-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="df7ea-109">Psleline 2,0 bietet eine leistungsfähige Befehlszeilen Bearbeitungsfunktion für die PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="df7ea-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="df7ea-110">Sie bietet:</span><span class="sxs-lookup"><span data-stu-id="df7ea-110">It provides:</span></span>

- <span data-ttu-id="df7ea-111">Syntax Farbgebung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="df7ea-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="df7ea-112">Visuelle Hinweise auf Syntax Fehler</span><span class="sxs-lookup"><span data-stu-id="df7ea-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="df7ea-113">Bessere mehrzeilige Erfahrung (sowohl Bearbeitung als auch Verlauf)</span><span class="sxs-lookup"><span data-stu-id="df7ea-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="df7ea-114">Anpassbare Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="df7ea-114">Customizable key bindings</span></span>
- <span data-ttu-id="df7ea-115">Cmd-und Emacs-Modi</span><span class="sxs-lookup"><span data-stu-id="df7ea-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="df7ea-116">Viele Konfigurationsoptionen</span><span class="sxs-lookup"><span data-stu-id="df7ea-116">Many configuration options</span></span>
- <span data-ttu-id="df7ea-117">Bash-Stil Vervollständigung (optional im cmd-Modus, Standard im Emacs-Modus)</span><span class="sxs-lookup"><span data-stu-id="df7ea-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="df7ea-118">Emacs: Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="df7ea-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="df7ea-119">PowerShell-tokenbasierte "Wort Bewegung" und "Kill"</span><span class="sxs-lookup"><span data-stu-id="df7ea-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="df7ea-120">Die folgenden Funktionen sind in der-Klasse **[Microsoft. PowerShell. psconsolereadline]** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="df7ea-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="df7ea-121">Grundlegende Bearbeitungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="df7ea-121">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="df7ea-122">Abbruch</span><span class="sxs-lookup"><span data-stu-id="df7ea-122">Abort</span></span>

<span data-ttu-id="df7ea-123">Abbrechen der aktuellen Aktion, z.b. inkrementelle Verlaufs Suche.</span><span class="sxs-lookup"><span data-stu-id="df7ea-123">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="df7ea-124">Ansehen `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-124">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="df7ea-125">Akzeptandgetnext</span><span class="sxs-lookup"><span data-stu-id="df7ea-125">AcceptAndGetNext</span></span>

<span data-ttu-id="df7ea-126">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-126">Attempt to execute the current input.</span></span> <span data-ttu-id="df7ea-127">Wenn Sie ausgeführt werden kann (wie z. b. Accept Line), erinnern Sie sich beim nächsten Aufruf von "read line" an das nächste Element aus dem Verlauf.</span><span class="sxs-lookup"><span data-stu-id="df7ea-127">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="df7ea-128">Ansehen `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-128">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="df7ea-129">Annahme</span><span class="sxs-lookup"><span data-stu-id="df7ea-129">AcceptLine</span></span>

<span data-ttu-id="df7ea-130">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-130">Attempt to execute the current input.</span></span> <span data-ttu-id="df7ea-131">Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="df7ea-131">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="df7ea-132">Befehl: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-132">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="df7ea-133">Ansehen `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-133">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="df7ea-134">VI-Einfügemodus: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-134">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="df7ea-135">AddLine</span><span class="sxs-lookup"><span data-stu-id="df7ea-135">AddLine</span></span>

<span data-ttu-id="df7ea-136">Die Fortsetzungs Aufforderung wird in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="df7ea-136">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="df7ea-137">Dies ist nützlich, um mehrzeilige Eingaben als einen einzelnen Befehl einzugeben, auch wenn eine einzelne Zeile allein eine Eingabe ist.</span><span class="sxs-lookup"><span data-stu-id="df7ea-137">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="df7ea-138">Befehl: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-138">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="df7ea-139">Ansehen `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-139">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="df7ea-140">VI-Einfügemodus: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-140">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="df7ea-141">VI-Befehlsmodus: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-141">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="df7ea-142">Backwarddeletechar</span><span class="sxs-lookup"><span data-stu-id="df7ea-142">BackwardDeleteChar</span></span>

<span data-ttu-id="df7ea-143">Löschen Sie das Zeichen vor dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-143">Delete the character before the cursor.</span></span>

- <span data-ttu-id="df7ea-144">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-144">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="df7ea-145">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-145">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="df7ea-146">VI-Einfügemodus: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-146">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="df7ea-147">VI-Befehlsmodus: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-147">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="df7ea-148">Backwarddelta-Eline</span><span class="sxs-lookup"><span data-stu-id="df7ea-148">BackwardDeleteLine</span></span>

<span data-ttu-id="df7ea-149">Wie backwardkillline löscht Text vom Punkt bis zum Anfang der Zeile, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-149">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="df7ea-150">Befehl: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-150">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="df7ea-151">VI-Einfügemodus: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-151">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="df7ea-152">VI-Befehlsmodus: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-152">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="df7ea-153">Backwarddeleteword</span><span class="sxs-lookup"><span data-stu-id="df7ea-153">BackwardDeleteWord</span></span>

<span data-ttu-id="df7ea-154">Löscht das vorherige Wort.</span><span class="sxs-lookup"><span data-stu-id="df7ea-154">Deletes the previous word.</span></span>

- <span data-ttu-id="df7ea-155">VI-Befehlsmodus: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-155">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="df7ea-156">Backwardkillline</span><span class="sxs-lookup"><span data-stu-id="df7ea-156">BackwardKillLine</span></span>

<span data-ttu-id="df7ea-157">Löschen Sie die Eingabe vom Beginn der Eingabe in den Cursor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-157">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="df7ea-158">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-158">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="df7ea-159">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-159">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="df7ea-160">Backwardkillword</span><span class="sxs-lookup"><span data-stu-id="df7ea-160">BackwardKillWord</span></span>

<span data-ttu-id="df7ea-161">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-161">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="df7ea-162">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="df7ea-162">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="df7ea-163">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-163">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="df7ea-164">Befehl: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-164">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="df7ea-165">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-165">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="df7ea-166">VI-Einfügemodus: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-166">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="df7ea-167">VI-Befehlsmodus: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-167">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="df7ea-168">Cancelline</span><span class="sxs-lookup"><span data-stu-id="df7ea-168">CancelLine</span></span>

<span data-ttu-id="df7ea-169">Brechen Sie die aktuelle Eingabe ab, belassen Sie die Eingabe auf dem Bildschirm, kehren Sie jedoch zurück zum Host, damit die Eingabeaufforderung erneut ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="df7ea-169">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="df7ea-170">VI-Einfügemodus: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-170">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="df7ea-171">VI-Befehlsmodus: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-171">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="df7ea-172">Kopieren</span><span class="sxs-lookup"><span data-stu-id="df7ea-172">Copy</span></span>

<span data-ttu-id="df7ea-173">Kopiert den ausgewählten Bereich in die Zwischenablage des Systems.</span><span class="sxs-lookup"><span data-stu-id="df7ea-173">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="df7ea-174">Wenn keine Region ausgewählt ist, kopieren Sie die gesamte Zeile.</span><span class="sxs-lookup"><span data-stu-id="df7ea-174">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="df7ea-175">Befehl: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-175">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="df7ea-176">Copyorcancelline</span><span class="sxs-lookup"><span data-stu-id="df7ea-176">CopyOrCancelLine</span></span>

<span data-ttu-id="df7ea-177">Wenn Text ausgewählt ist, kopieren Sie ihn in die Zwischenablage, andernfalls brechen Sie die Zeile ab.</span><span class="sxs-lookup"><span data-stu-id="df7ea-177">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="df7ea-178">Befehl: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-178">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="df7ea-179">Ansehen `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-179">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="df7ea-180">Ausschneiden</span><span class="sxs-lookup"><span data-stu-id="df7ea-180">Cut</span></span>

<span data-ttu-id="df7ea-181">Löscht die ausgewählte Region, in der Gelöschter Text in der Zwischenablage des Systems</span><span class="sxs-lookup"><span data-stu-id="df7ea-181">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="df7ea-182">Befehl: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-182">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="df7ea-183">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="df7ea-183">DeleteChar</span></span>

<span data-ttu-id="df7ea-184">Löschen Sie das Zeichen unter dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-184">Delete the character under the cursor.</span></span>

- <span data-ttu-id="df7ea-185">Befehl: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-185">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="df7ea-186">Ansehen `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-186">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="df7ea-187">VI-Einfügemodus: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-187">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="df7ea-188">VI-Befehlsmodus: `<Delete>` , `<x>` , `<d,l>` , `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-188">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="df7ea-189">Deletecharorexit</span><span class="sxs-lookup"><span data-stu-id="df7ea-189">DeleteCharOrExit</span></span>

<span data-ttu-id="df7ea-190">Löschen Sie das Zeichen unter dem Cursor, oder beenden Sie den Prozess, wenn die Zeile leer ist.</span><span class="sxs-lookup"><span data-stu-id="df7ea-190">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="df7ea-191">Ansehen `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-191">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="df7ea-192">Deleteendof</span><span class="sxs-lookup"><span data-stu-id="df7ea-192">DeleteEndOfWord</span></span>

<span data-ttu-id="df7ea-193">Bis zum Ende des Worts löschen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-193">Delete to the end of the word.</span></span>

- <span data-ttu-id="df7ea-194">VI-Befehlsmodus: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-194">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="df7ea-195">"Deleteline</span><span class="sxs-lookup"><span data-stu-id="df7ea-195">DeleteLine</span></span>

<span data-ttu-id="df7ea-196">Löscht die aktuelle Zeile und aktiviert die Rückgängigmachen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-196">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="df7ea-197">VI-Befehlsmodus: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-197">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="df7ea-198">Delta-inetyp</span><span class="sxs-lookup"><span data-stu-id="df7ea-198">DeleteLineToFirstChar</span></span>

<span data-ttu-id="df7ea-199">Löscht Text vom Cursor zum ersten Zeichen der Zeile, das nicht leer ist.</span><span class="sxs-lookup"><span data-stu-id="df7ea-199">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="df7ea-200">VI-Befehlsmodus: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-200">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="df7ea-201">Deletegeend</span><span class="sxs-lookup"><span data-stu-id="df7ea-201">DeleteToEnd</span></span>

<span data-ttu-id="df7ea-202">Bis zum Ende der Zeile löschen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-202">Delete to the end of the line.</span></span>

- <span data-ttu-id="df7ea-203">VI-Befehlsmodus: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-203">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="df7ea-204">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="df7ea-204">DeleteWord</span></span>

<span data-ttu-id="df7ea-205">Löschen Sie das nächste Wort.</span><span class="sxs-lookup"><span data-stu-id="df7ea-205">Delete the next word.</span></span>

- <span data-ttu-id="df7ea-206">VI-Befehlsmodus: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-206">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="df7ea-207">Forwarddelta-Eline</span><span class="sxs-lookup"><span data-stu-id="df7ea-207">ForwardDeleteLine</span></span>

<span data-ttu-id="df7ea-208">Wie forwardkillline löscht Text vom Punkt bis zum Ende der Zeile, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-208">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="df7ea-209">Befehl: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-209">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="df7ea-210">VI-Einfügemodus: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-210">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="df7ea-211">VI-Befehlsmodus: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-211">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="df7ea-212">Insertlineoberhalb</span><span class="sxs-lookup"><span data-stu-id="df7ea-212">InsertLineAbove</span></span>

<span data-ttu-id="df7ea-213">Oberhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="df7ea-213">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="df7ea-214">Der Cursor wechselt zum Anfang der neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="df7ea-214">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="df7ea-215">Befehl: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-215">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="df7ea-216">Insertlinebelow</span><span class="sxs-lookup"><span data-stu-id="df7ea-216">InsertLineBelow</span></span>

<span data-ttu-id="df7ea-217">Unterhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="df7ea-217">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="df7ea-218">Der Cursor wechselt zum Anfang der neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="df7ea-218">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="df7ea-219">Befehl: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-219">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="df7ea-220">Invertieren</span><span class="sxs-lookup"><span data-stu-id="df7ea-220">InvertCase</span></span>

<span data-ttu-id="df7ea-221">Kehrt die Groß-/Kleinschreibung des aktuellen Zeichens um und wechselt zum nächsten.</span><span class="sxs-lookup"><span data-stu-id="df7ea-221">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="df7ea-222">VI-Befehlsmodus: `<~>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-222">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="df7ea-223">Killline</span><span class="sxs-lookup"><span data-stu-id="df7ea-223">KillLine</span></span>

<span data-ttu-id="df7ea-224">Löschen Sie die Eingabe vom Cursor bis zum Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="df7ea-224">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="df7ea-225">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-225">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="df7ea-226">Ansehen `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-226">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="df7ea-227">Killregion</span><span class="sxs-lookup"><span data-stu-id="df7ea-227">KillRegion</span></span>

<span data-ttu-id="df7ea-228">Beenden Sie den Text zwischen dem Cursor und der Markierung.</span><span class="sxs-lookup"><span data-stu-id="df7ea-228">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="df7ea-229">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-229">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="df7ea-230">Killword</span><span class="sxs-lookup"><span data-stu-id="df7ea-230">KillWord</span></span>

<span data-ttu-id="df7ea-231">Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts.</span><span class="sxs-lookup"><span data-stu-id="df7ea-231">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="df7ea-232">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht.</span><span class="sxs-lookup"><span data-stu-id="df7ea-232">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="df7ea-233">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-233">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="df7ea-234">Befehl: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-234">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="df7ea-235">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-235">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="df7ea-236">VI-Einfügemodus: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-236">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="df7ea-237">VI-Befehlsmodus: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-237">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="df7ea-238">Einfügen</span><span class="sxs-lookup"><span data-stu-id="df7ea-238">Paste</span></span>

<span data-ttu-id="df7ea-239">Fügen Sie Text aus der Zwischenablage des Systems ein.</span><span class="sxs-lookup"><span data-stu-id="df7ea-239">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="df7ea-240">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-240">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="df7ea-241">VI-Einfügemodus: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-241">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="df7ea-242">VI-Befehlsmodus: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-242">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df7ea-243">Wenn Sie die Funktion **Einfügen** verwenden, wird der gesamte Inhalt des Zwischenablage Puffers in den Eingabepuffer von psread Line eingefügt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-243">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="df7ea-244">Der Eingabepuffer wird dann an den PowerShell-Parser übergeben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-244">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="df7ea-245">Eingaben, die mithilfe der **Rechtsklick-Einfügemethode** der Konsolenanwendung eingefügt werden, werden jeweils ein Zeichen in den Eingabepuffer kopiert.</span><span class="sxs-lookup"><span data-stu-id="df7ea-245">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="df7ea-246">Der Eingabepuffer wird an den Parser übergeben, wenn ein Zeilen vorzeichensatz kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="df7ea-246">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="df7ea-247">Daher wird die Eingabe jeweils Zeilen gleich analysiert.</span><span class="sxs-lookup"><span data-stu-id="df7ea-247">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="df7ea-248">Der Unterschied zwischen den Methoden zum Einfügen führt zu einem anderen Ausführungs Verhalten.</span><span class="sxs-lookup"><span data-stu-id="df7ea-248">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="df7ea-249">Pasteafter</span><span class="sxs-lookup"><span data-stu-id="df7ea-249">PasteAfter</span></span>

<span data-ttu-id="df7ea-250">Fügen Sie die Zwischenablage nach dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.</span><span class="sxs-lookup"><span data-stu-id="df7ea-250">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="df7ea-251">VI-Befehlsmodus: `<p>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-251">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="df7ea-252">Pastebefore</span><span class="sxs-lookup"><span data-stu-id="df7ea-252">PasteBefore</span></span>

<span data-ttu-id="df7ea-253">Fügen Sie die Zwischenablage vor dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.</span><span class="sxs-lookup"><span data-stu-id="df7ea-253">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="df7ea-254">VI-Befehlsmodus: `<P>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-254">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="df7ea-255">Prepdandaccept</span><span class="sxs-lookup"><span data-stu-id="df7ea-255">PrependAndAccept</span></span>

<span data-ttu-id="df7ea-256">Fügen Sie ein "#" vorangesteht, und akzeptieren Sie die Zeile.</span><span class="sxs-lookup"><span data-stu-id="df7ea-256">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="df7ea-257">VI-Befehlsmodus: `<#>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-257">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="df7ea-258">Wiederholen</span><span class="sxs-lookup"><span data-stu-id="df7ea-258">Redo</span></span>

<span data-ttu-id="df7ea-259">Rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-259">Undo an undo.</span></span>

- <span data-ttu-id="df7ea-260">Befehl: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-260">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="df7ea-261">VI-Einfügemodus: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-261">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="df7ea-262">VI-Befehlsmodus: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-262">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="df7ea-263">Repeatlastcommand</span><span class="sxs-lookup"><span data-stu-id="df7ea-263">RepeatLastCommand</span></span>

<span data-ttu-id="df7ea-264">Wiederholen Sie die letzte Textänderung.</span><span class="sxs-lookup"><span data-stu-id="df7ea-264">Repeat the last text modification.</span></span>

- <span data-ttu-id="df7ea-265">VI-Befehlsmodus: `<.>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-265">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="df7ea-266">Revertline</span><span class="sxs-lookup"><span data-stu-id="df7ea-266">RevertLine</span></span>

<span data-ttu-id="df7ea-267">Kehrt alle Eingaben in die aktuelle Eingabe um.</span><span class="sxs-lookup"><span data-stu-id="df7ea-267">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="df7ea-268">Befehl: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-268">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="df7ea-269">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-269">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="df7ea-270">Shellbackwardkillword</span><span class="sxs-lookup"><span data-stu-id="df7ea-270">ShellBackwardKillWord</span></span>

<span data-ttu-id="df7ea-271">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-271">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="df7ea-272">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="df7ea-272">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="df7ea-273">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-273">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="df7ea-274">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-274">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="df7ea-275">Shellkillword</span><span class="sxs-lookup"><span data-stu-id="df7ea-275">ShellKillWord</span></span>

<span data-ttu-id="df7ea-276">Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts.</span><span class="sxs-lookup"><span data-stu-id="df7ea-276">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="df7ea-277">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht.</span><span class="sxs-lookup"><span data-stu-id="df7ea-277">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="df7ea-278">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-278">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="df7ea-279">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-279">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="df7ea-280">Austausch Zeichen</span><span class="sxs-lookup"><span data-stu-id="df7ea-280">SwapCharacters</span></span>

<span data-ttu-id="df7ea-281">Tauschen Sie das aktuelle und das aktuelle Zeichen aus.</span><span class="sxs-lookup"><span data-stu-id="df7ea-281">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="df7ea-282">Ansehen `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-282">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="df7ea-283">VI-Einfügemodus: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-283">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="df7ea-284">VI-Befehlsmodus: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-284">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="df7ea-285">Rückgängig</span><span class="sxs-lookup"><span data-stu-id="df7ea-285">Undo</span></span>

<span data-ttu-id="df7ea-286">Rückgängigmachen einer vorherigen Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="df7ea-286">Undo a previous edit.</span></span>

- <span data-ttu-id="df7ea-287">Befehl: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-287">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="df7ea-288">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-288">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="df7ea-289">VI-Einfügemodus: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-289">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="df7ea-290">VI-Befehlsmodus: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-290">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="df7ea-291">Nicht doall</span><span class="sxs-lookup"><span data-stu-id="df7ea-291">UndoAll</span></span>

<span data-ttu-id="df7ea-292">Alle vorherigen Änderungen für die Zeile rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-292">Undo all previous edits for line.</span></span>

- <span data-ttu-id="df7ea-293">VI-Befehlsmodus: `<U>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-293">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="df7ea-294">Unixwordrubout</span><span class="sxs-lookup"><span data-stu-id="df7ea-294">UnixWordRubout</span></span>

<span data-ttu-id="df7ea-295">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-295">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="df7ea-296">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="df7ea-296">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="df7ea-297">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-297">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="df7ea-298">Ansehen `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-298">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="df7ea-299">Validateandakzeptline</span><span class="sxs-lookup"><span data-stu-id="df7ea-299">ValidateAndAcceptLine</span></span>

<span data-ttu-id="df7ea-300">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-300">Attempt to execute the current input.</span></span> <span data-ttu-id="df7ea-301">Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="df7ea-301">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="df7ea-302">Ansehen `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-302">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="df7ea-303">Viakzeptline</span><span class="sxs-lookup"><span data-stu-id="df7ea-303">ViAcceptLine</span></span>

<span data-ttu-id="df7ea-304">Akzeptieren Sie die Zeile, und wechseln Sie zum Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="df7ea-304">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="df7ea-305">VI-Befehlsmodus: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-305">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="df7ea-306">Viakzeptlineorexit</span><span class="sxs-lookup"><span data-stu-id="df7ea-306">ViAcceptLineOrExit</span></span>

<span data-ttu-id="df7ea-307">Wie deletecharorexit im Emacs-Modus, akzeptiert jedoch die Zeile, anstatt ein Zeichen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-307">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="df7ea-308">VI-Einfügemodus: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-308">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="df7ea-309">VI-Befehlsmodus: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-309">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="df7ea-310">Viappendline</span><span class="sxs-lookup"><span data-stu-id="df7ea-310">ViAppendLine</span></span>

<span data-ttu-id="df7ea-311">Unterhalb der aktuellen Zeile wird eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-311">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="df7ea-312">VI-Befehlsmodus: `<o>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-312">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="df7ea-313">Vibackwarddeleteglob</span><span class="sxs-lookup"><span data-stu-id="df7ea-313">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="df7ea-314">Löscht das vorherige Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="df7ea-314">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="df7ea-315">VI-Befehlsmodus: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-315">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="df7ea-316">Vibackwardglob</span><span class="sxs-lookup"><span data-stu-id="df7ea-316">ViBackwardGlob</span></span>

<span data-ttu-id="df7ea-317">Verschiebt den Cursor zurück an den Anfang des vorherigen Worts, wobei nur Leerraum als Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="df7ea-317">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="df7ea-318">VI-Befehlsmodus: `<B>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-318">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="df7ea-319">Videletebrace</span><span class="sxs-lookup"><span data-stu-id="df7ea-319">ViDeleteBrace</span></span>

<span data-ttu-id="df7ea-320">Suchen Sie nach der passenden geschweiften Klammer, Klammer oder eckigen Klammer, und löschen Sie alle Inhalte in, einschließlich der geschweiften Klammer.</span><span class="sxs-lookup"><span data-stu-id="df7ea-320">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="df7ea-321">VI-Befehlsmodus: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-321">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="df7ea-322">Videleteendobglob</span><span class="sxs-lookup"><span data-stu-id="df7ea-322">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="df7ea-323">Bis zum Ende des Worts löschen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-323">Delete to the end of the word.</span></span>

- <span data-ttu-id="df7ea-324">VI-Befehlsmodus: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-324">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="df7ea-325">Videleteglob</span><span class="sxs-lookup"><span data-stu-id="df7ea-325">ViDeleteGlob</span></span>

<span data-ttu-id="df7ea-326">Löschen Sie den nächsten globmuster (Leerzeichen mit Trennzeichen).</span><span class="sxs-lookup"><span data-stu-id="df7ea-326">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="df7ea-327">VI-Befehlsmodus: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-327">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="df7ea-328">Videletetobeforechar</span><span class="sxs-lookup"><span data-stu-id="df7ea-328">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="df7ea-329">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-329">Deletes until given character.</span></span>

- <span data-ttu-id="df7ea-330">VI-Befehlsmodus: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-330">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="df7ea-331">Videletebackbeforecharrückwärts</span><span class="sxs-lookup"><span data-stu-id="df7ea-331">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="df7ea-332">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-332">Deletes until given character.</span></span>

- <span data-ttu-id="df7ea-333">VI-Befehlsmodus: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-333">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="df7ea-334">Videleteto Char</span><span class="sxs-lookup"><span data-stu-id="df7ea-334">ViDeleteToChar</span></span>

<span data-ttu-id="df7ea-335">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-335">Deletes until given character.</span></span>

- <span data-ttu-id="df7ea-336">VI-Befehlsmodus: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-336">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="df7ea-337">Videletebackcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="df7ea-337">ViDeleteToCharBackward</span></span>

<span data-ttu-id="df7ea-338">Löscht rückwärts bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-338">Deletes backwards until given character.</span></span>

- <span data-ttu-id="df7ea-339">VI-Befehlsmodus: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-339">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="df7ea-340">Viinsertatbeginung</span><span class="sxs-lookup"><span data-stu-id="df7ea-340">ViInsertAtBegining</span></span>

<span data-ttu-id="df7ea-341">Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Anfang der Zeile.</span><span class="sxs-lookup"><span data-stu-id="df7ea-341">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="df7ea-342">VI-Befehlsmodus: `<I>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-342">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="df7ea-343">Viinsertatend</span><span class="sxs-lookup"><span data-stu-id="df7ea-343">ViInsertAtEnd</span></span>

<span data-ttu-id="df7ea-344">Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Ende der Zeile.</span><span class="sxs-lookup"><span data-stu-id="df7ea-344">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="df7ea-345">VI-Befehlsmodus: `<A>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-345">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="df7ea-346">Viinsertline</span><span class="sxs-lookup"><span data-stu-id="df7ea-346">ViInsertLine</span></span>

<span data-ttu-id="df7ea-347">Oberhalb der aktuellen Zeile wird eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-347">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="df7ea-348">VI-Befehlsmodus: `<O>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-348">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="df7ea-349">Viinsertwithappend</span><span class="sxs-lookup"><span data-stu-id="df7ea-349">ViInsertWithAppend</span></span>

<span data-ttu-id="df7ea-350">An der aktuellen Zeilen Position anfügen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-350">Append from the current line position.</span></span>

- <span data-ttu-id="df7ea-351">VI-Befehlsmodus: `<a>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-351">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="df7ea-352">Viinsertwithdelete</span><span class="sxs-lookup"><span data-stu-id="df7ea-352">ViInsertWithDelete</span></span>

<span data-ttu-id="df7ea-353">Löschen Sie das aktuelle Zeichen und wechseln Sie in den Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="df7ea-353">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="df7ea-354">VI-Befehlsmodus: `<s>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-354">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="df7ea-355">Vijoinlines</span><span class="sxs-lookup"><span data-stu-id="df7ea-355">ViJoinLines</span></span>

<span data-ttu-id="df7ea-356">Verbindet die aktuelle Zeile und die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="df7ea-356">Joins the current line and the next line.</span></span>

- <span data-ttu-id="df7ea-357">VI-Befehlsmodus: `<J>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-357">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="df7ea-358">Vireplaceline</span><span class="sxs-lookup"><span data-stu-id="df7ea-358">ViReplaceLine</span></span>

<span data-ttu-id="df7ea-359">Löschen Sie die gesamte Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="df7ea-359">Erase the entire command line.</span></span>

- <span data-ttu-id="df7ea-360">VI-Befehlsmodus: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-360">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="df7ea-361">Vireplacetobeforechar</span><span class="sxs-lookup"><span data-stu-id="df7ea-361">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="df7ea-362">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-362">Replaces until given character.</span></span>

- <span data-ttu-id="df7ea-363">VI-Befehlsmodus: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-363">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="df7ea-364">Vireplaceumbeforecharrückwärts</span><span class="sxs-lookup"><span data-stu-id="df7ea-364">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="df7ea-365">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-365">Replaces until given character.</span></span>

- <span data-ttu-id="df7ea-366">VI-Befehlsmodus: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-366">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="df7ea-367">Vireplaceumchar</span><span class="sxs-lookup"><span data-stu-id="df7ea-367">ViReplaceToChar</span></span>

<span data-ttu-id="df7ea-368">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-368">Deletes until given character.</span></span>

- <span data-ttu-id="df7ea-369">VI-Befehlsmodus: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-369">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="df7ea-370">Vireplacebackcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="df7ea-370">ViReplaceToCharBackward</span></span>

<span data-ttu-id="df7ea-371">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-371">Replaces until given character.</span></span>

- <span data-ttu-id="df7ea-372">VI-Befehlsmodus: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-372">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="df7ea-373">Viyankbeginningosline</span><span class="sxs-lookup"><span data-stu-id="df7ea-373">ViYankBeginningOfLine</span></span>

<span data-ttu-id="df7ea-374">Yank vom Anfang des Puffers bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-374">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="df7ea-375">VI-Befehlsmodus: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-375">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="df7ea-376">Viyankendobglob</span><span class="sxs-lookup"><span data-stu-id="df7ea-376">ViYankEndOfGlob</span></span>

<span data-ttu-id="df7ea-377">Yank vom Cursor bis zum Ende des Worts (s).</span><span class="sxs-lookup"><span data-stu-id="df7ea-377">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="df7ea-378">VI-Befehlsmodus: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-378">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="df7ea-379">Viyankendof</span><span class="sxs-lookup"><span data-stu-id="df7ea-379">ViYankEndOfWord</span></span>

<span data-ttu-id="df7ea-380">Yank vom Cursor bis zum Ende des Worts (s).</span><span class="sxs-lookup"><span data-stu-id="df7ea-380">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="df7ea-381">VI-Befehlsmodus: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-381">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="df7ea-382">Viyankleft</span><span class="sxs-lookup"><span data-stu-id="df7ea-382">ViYankLeft</span></span>

<span data-ttu-id="df7ea-383">Die Zeichen werden Links vom Cursor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-383">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="df7ea-384">VI-Befehlsmodus: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-384">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="df7ea-385">Viyankline</span><span class="sxs-lookup"><span data-stu-id="df7ea-385">ViYankLine</span></span>

<span data-ttu-id="df7ea-386">Den gesamten Puffer.</span><span class="sxs-lookup"><span data-stu-id="df7ea-386">Yank the entire buffer.</span></span>

- <span data-ttu-id="df7ea-387">VI-Befehlsmodus: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-387">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="df7ea-388">Viyanknextglob</span><span class="sxs-lookup"><span data-stu-id="df7ea-388">ViYankNextGlob</span></span>

<span data-ttu-id="df7ea-389">Yank vom Cursor bis zum Anfang des nächsten Worts (n).</span><span class="sxs-lookup"><span data-stu-id="df7ea-389">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="df7ea-390">VI-Befehlsmodus: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-390">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="df7ea-391">Viyanknextword</span><span class="sxs-lookup"><span data-stu-id="df7ea-391">ViYankNextWord</span></span>

<span data-ttu-id="df7ea-392">Das Wort (e) nach dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-392">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="df7ea-393">VI-Befehlsmodus: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-393">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="df7ea-394">Viyankprozent</span><span class="sxs-lookup"><span data-stu-id="df7ea-394">ViYankPercent</span></span>

<span data-ttu-id="df7ea-395">Von der entsprechenden geschweiften geschweifter Klammer.</span><span class="sxs-lookup"><span data-stu-id="df7ea-395">Yank to/from matching brace.</span></span>

- <span data-ttu-id="df7ea-396">VI-Befehlsmodus: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-396">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="df7ea-397">Viyankpreviousglob</span><span class="sxs-lookup"><span data-stu-id="df7ea-397">ViYankPreviousGlob</span></span>

<span data-ttu-id="df7ea-398">Yank von Anfang des Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-398">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="df7ea-399">VI-Befehlsmodus: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-399">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="df7ea-400">Viyankpreviousword</span><span class="sxs-lookup"><span data-stu-id="df7ea-400">ViYankPreviousWord</span></span>

<span data-ttu-id="df7ea-401">Das Wort (e) vor dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-401">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="df7ea-402">VI-Befehlsmodus: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-402">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="df7ea-403">Viyankright</span><span class="sxs-lookup"><span data-stu-id="df7ea-403">ViYankRight</span></span>

<span data-ttu-id="df7ea-404">(E) unter und rechts vom Cursor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-404">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="df7ea-405">VI-Befehlsmodus: `<y,l>` , `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-405">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="df7ea-406">Viyanktoendosline</span><span class="sxs-lookup"><span data-stu-id="df7ea-406">ViYankToEndOfLine</span></span>

<span data-ttu-id="df7ea-407">Yank vom Cursor bis zum Ende des Puffers.</span><span class="sxs-lookup"><span data-stu-id="df7ea-407">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="df7ea-408">VI-Befehlsmodus: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-408">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="df7ea-409">Viyanktofirstchar</span><span class="sxs-lookup"><span data-stu-id="df7ea-409">ViYankToFirstChar</span></span>

<span data-ttu-id="df7ea-410">Yank vom ersten Zeichen, das kein Leerzeichen ist, bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-410">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="df7ea-411">VI-Befehlsmodus: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-411">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="df7ea-412">Yank</span><span class="sxs-lookup"><span data-stu-id="df7ea-412">Yank</span></span>

<span data-ttu-id="df7ea-413">Fügen Sie der Eingabe den zuletzt beendeten Text hinzu.</span><span class="sxs-lookup"><span data-stu-id="df7ea-413">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="df7ea-414">Ansehen `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-414">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="df7ea-415">Yanklastarg</span><span class="sxs-lookup"><span data-stu-id="df7ea-415">YankLastArg</span></span>

<span data-ttu-id="df7ea-416">Das letzte Argument aus der vorherigen Verlaufs Zeile.</span><span class="sxs-lookup"><span data-stu-id="df7ea-416">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="df7ea-417">Mit einem Argument verhält sich das erste Mal, wenn es aufgerufen wird, wie yankntharg.</span><span class="sxs-lookup"><span data-stu-id="df7ea-417">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="df7ea-418">Wenn Sie mehrmals aufgerufen wird, durchläuft Sie stattdessen den Verlauf, und arg legt die Richtung fest (negative Umkehrung der Richtung).</span><span class="sxs-lookup"><span data-stu-id="df7ea-418">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="df7ea-419">Befehl: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-419">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="df7ea-420">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-420">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="df7ea-421">Yankntharg</span><span class="sxs-lookup"><span data-stu-id="df7ea-421">YankNthArg</span></span>

<span data-ttu-id="df7ea-422">Yank das erste Argument (nach dem Befehl) aus der vorherigen Verlaufs Zeile.</span><span class="sxs-lookup"><span data-stu-id="df7ea-422">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="df7ea-423">Bei einem Argument wird das n-te Argument (beginnend bei 0), wenn das Argument negativ ist, mit dem letzten Argument beginnen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-423">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="df7ea-424">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-424">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="df7ea-425">Yankpop</span><span class="sxs-lookup"><span data-stu-id="df7ea-425">YankPop</span></span>

<span data-ttu-id="df7ea-426">Wenn der vorherige Vorgang "Yank" oder "yankpop" war, ersetzen Sie den zuvor angezeigten Text durch den nächsten ausgeblendeten Text aus dem Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="df7ea-426">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="df7ea-427">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-427">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="df7ea-428">Cursor Verschiebungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="df7ea-428">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="df7ea-429">Backwardchar</span><span class="sxs-lookup"><span data-stu-id="df7ea-429">BackwardChar</span></span>

<span data-ttu-id="df7ea-430">Bewegen Sie den Cursor um ein Zeichen nach links.</span><span class="sxs-lookup"><span data-stu-id="df7ea-430">Move the cursor one character to the left.</span></span> <span data-ttu-id="df7ea-431">Dadurch kann der Cursor in die vorherige Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="df7ea-431">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="df7ea-432">Befehl: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-432">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="df7ea-433">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-433">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="df7ea-434">VI-Einfügemodus: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-434">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="df7ea-435">VI-Befehlsmodus: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-435">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="df7ea-436">Backwardword</span><span class="sxs-lookup"><span data-stu-id="df7ea-436">BackwardWord</span></span>

<span data-ttu-id="df7ea-437">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-437">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="df7ea-438">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="df7ea-438">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="df7ea-439">Befehl: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-439">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="df7ea-440">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-440">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="df7ea-441">VI-Einfügemodus: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-441">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="df7ea-442">VI-Befehlsmodus: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-442">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="df7ea-443">Beginningosline</span><span class="sxs-lookup"><span data-stu-id="df7ea-443">BeginningOfLine</span></span>

<span data-ttu-id="df7ea-444">Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Anfang der aktuellen Zeile oder, wenn Sie sich bereits am Anfang der Zeile befinden, bis zum Anfang der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="df7ea-444">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="df7ea-445">Wenn die Eingabe über eine einzelne Zeile verfügt, wechseln Sie zum Anfang der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="df7ea-445">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="df7ea-446">Befehl: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-446">Cmd: `<Home>`</span></span>
- <span data-ttu-id="df7ea-447">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-447">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="df7ea-448">VI-Einfügemodus: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-448">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="df7ea-449">VI-Befehlsmodus: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-449">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="df7ea-450">Endosline</span><span class="sxs-lookup"><span data-stu-id="df7ea-450">EndOfLine</span></span>

<span data-ttu-id="df7ea-451">Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Ende der aktuellen Zeile, oder wechseln Sie, wenn Sie sich bereits am Ende der Zeile befindet, bis zum Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="df7ea-451">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="df7ea-452">Wenn die Eingabe über eine einzelne Zeile verfügt, verschieben Sie das Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="df7ea-452">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="df7ea-453">Befehl: `<End>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-453">Cmd: `<End>`</span></span>
- <span data-ttu-id="df7ea-454">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-454">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="df7ea-455">VI-Einfügemodus: `<End>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-455">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="df7ea-456">Forwardchar</span><span class="sxs-lookup"><span data-stu-id="df7ea-456">ForwardChar</span></span>

<span data-ttu-id="df7ea-457">Bewegen Sie den Cursor um ein Zeichen nach rechts.</span><span class="sxs-lookup"><span data-stu-id="df7ea-457">Move the cursor one character to the right.</span></span> <span data-ttu-id="df7ea-458">Dadurch kann der Cursor in die nächste Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="df7ea-458">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="df7ea-459">Befehl: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-459">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="df7ea-460">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-460">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="df7ea-461">VI-Einfügemodus: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-461">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="df7ea-462">VI-Befehlsmodus: `<RightArrow>` , `<Space>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-462">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="df7ea-463">Forwardword</span><span class="sxs-lookup"><span data-stu-id="df7ea-463">ForwardWord</span></span>

<span data-ttu-id="df7ea-464">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="df7ea-464">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="df7ea-465">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="df7ea-465">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="df7ea-466">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-466">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="df7ea-467">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="df7ea-467">GotoBrace</span></span>

<span data-ttu-id="df7ea-468">Wechseln Sie zur passenden geschweiften Klammer, Klammer oder eckigen Klammer.</span><span class="sxs-lookup"><span data-stu-id="df7ea-468">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="df7ea-469">Befehl: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-469">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="df7ea-470">VI-Einfügemodus: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-470">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="df7ea-471">VI-Befehlsmodus: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-471">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="df7ea-472">Goum Column</span><span class="sxs-lookup"><span data-stu-id="df7ea-472">GotoColumn</span></span>

<span data-ttu-id="df7ea-473">Wechseln Sie in die Spalte, die von arg angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="df7ea-473">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="df7ea-474">VI-Befehlsmodus: `<|>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-474">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="df7ea-475">Gostarfirstnonblankosline</span><span class="sxs-lookup"><span data-stu-id="df7ea-475">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="df7ea-476">Bewegen Sie den Cursor auf das erste nicht leere Zeichen in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="df7ea-476">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="df7ea-477">VI-Befehlsmodus: `<^>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-477">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="df7ea-478">"MUVE"</span><span class="sxs-lookup"><span data-stu-id="df7ea-478">MoveToEndOfLine</span></span>

<span data-ttu-id="df7ea-479">Bewegen Sie den Cursor an das Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="df7ea-479">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="df7ea-480">VI-Befehlsmodus: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-480">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="df7ea-481">Nextline</span><span class="sxs-lookup"><span data-stu-id="df7ea-481">NextLine</span></span>

<span data-ttu-id="df7ea-482">Bewegen Sie den Cursor in die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="df7ea-482">Move the cursor to the next line.</span></span>

- <span data-ttu-id="df7ea-483">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-483">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="df7ea-484">Nextword</span><span class="sxs-lookup"><span data-stu-id="df7ea-484">NextWord</span></span>

<span data-ttu-id="df7ea-485">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="df7ea-485">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="df7ea-486">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="df7ea-486">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="df7ea-487">Befehl: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-487">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="df7ea-488">VI-Einfügemodus: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-488">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="df7ea-489">VI-Befehlsmodus: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-489">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="df7ea-490">Nextwordend</span><span class="sxs-lookup"><span data-stu-id="df7ea-490">NextWordEnd</span></span>

<span data-ttu-id="df7ea-491">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="df7ea-491">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="df7ea-492">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="df7ea-492">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="df7ea-493">VI-Befehlsmodus: `<e>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-493">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="df7ea-494">Previousline</span><span class="sxs-lookup"><span data-stu-id="df7ea-494">PreviousLine</span></span>

<span data-ttu-id="df7ea-495">Bewegen Sie den Cursor in die vorherige Zeile.</span><span class="sxs-lookup"><span data-stu-id="df7ea-495">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="df7ea-496">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-496">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="df7ea-497">Shellbackwardword</span><span class="sxs-lookup"><span data-stu-id="df7ea-497">ShellBackwardWord</span></span>

<span data-ttu-id="df7ea-498">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-498">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="df7ea-499">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="df7ea-499">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="df7ea-500">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-500">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="df7ea-501">Shellforwardword</span><span class="sxs-lookup"><span data-stu-id="df7ea-501">ShellForwardWord</span></span>

<span data-ttu-id="df7ea-502">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="df7ea-502">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="df7ea-503">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="df7ea-503">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="df7ea-504">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-504">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="df7ea-505">Shellnextword</span><span class="sxs-lookup"><span data-stu-id="df7ea-505">ShellNextWord</span></span>

<span data-ttu-id="df7ea-506">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="df7ea-506">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="df7ea-507">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="df7ea-507">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="df7ea-508">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-508">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="df7ea-509">Vibackwardword</span><span class="sxs-lookup"><span data-stu-id="df7ea-509">ViBackwardWord</span></span>

<span data-ttu-id="df7ea-510">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-510">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="df7ea-511">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="df7ea-511">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="df7ea-512">VI-Befehlsmodus: `<b>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-512">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="df7ea-513">Viendobglob</span><span class="sxs-lookup"><span data-stu-id="df7ea-513">ViEndOfGlob</span></span>

<span data-ttu-id="df7ea-514">Verschiebt den Cursor an das Ende des Worts und verwendet nur Leerzeichen als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-514">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="df7ea-515">VI-Befehlsmodus: `<E>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-515">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="df7ea-516">Viendof previousglob</span><span class="sxs-lookup"><span data-stu-id="df7ea-516">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="df7ea-517">Wechselt zum Ende des vorherigen Worts, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="df7ea-517">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="df7ea-518">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-518">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="df7ea-519">Vigoumbrace</span><span class="sxs-lookup"><span data-stu-id="df7ea-519">ViGotoBrace</span></span>

<span data-ttu-id="df7ea-520">Ähnelt gotobrace, aber ist Zeichen basiert anstelle von tokenbasiert.</span><span class="sxs-lookup"><span data-stu-id="df7ea-520">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="df7ea-521">VI-Befehlsmodus: `<%>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-521">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="df7ea-522">Vinextglob</span><span class="sxs-lookup"><span data-stu-id="df7ea-522">ViNextGlob</span></span>

<span data-ttu-id="df7ea-523">Wechselt zum nächsten Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="df7ea-523">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="df7ea-524">VI-Befehlsmodus: `<W>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-524">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="df7ea-525">Vinextword</span><span class="sxs-lookup"><span data-stu-id="df7ea-525">ViNextWord</span></span>

<span data-ttu-id="df7ea-526">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="df7ea-526">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="df7ea-527">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="df7ea-527">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="df7ea-528">VI-Befehlsmodus: `<w>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-528">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="df7ea-529">Verlaufs Funktionen</span><span class="sxs-lookup"><span data-stu-id="df7ea-529">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="df7ea-530">Beginningof History</span><span class="sxs-lookup"><span data-stu-id="df7ea-530">BeginningOfHistory</span></span>

<span data-ttu-id="df7ea-531">Wechselt zum ersten Element im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="df7ea-531">Move to the first item in the history.</span></span>

- <span data-ttu-id="df7ea-532">Ansehen `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="df7ea-532">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="df7ea-533">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="df7ea-533">ClearHistory</span></span>

<span data-ttu-id="df7ea-534">Löscht den Verlauf in psleline.</span><span class="sxs-lookup"><span data-stu-id="df7ea-534">Clears history in PSReadLine.</span></span> <span data-ttu-id="df7ea-535">Dies wirkt sich nicht auf den PowerShell-Verlauf aus.</span><span class="sxs-lookup"><span data-stu-id="df7ea-535">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="df7ea-536">Befehl: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-536">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="df7ea-537">EndOf History</span><span class="sxs-lookup"><span data-stu-id="df7ea-537">EndOfHistory</span></span>

<span data-ttu-id="df7ea-538">Wechselt zum letzten Element (der aktuellen Eingabe) im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="df7ea-538">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="df7ea-539">Ansehen `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-539">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="df7ea-540">Forwardsearchhistory</span><span class="sxs-lookup"><span data-stu-id="df7ea-540">ForwardSearchHistory</span></span>

<span data-ttu-id="df7ea-541">Führt eine inkrementelle Forward-Suche im Verlauf durch</span><span class="sxs-lookup"><span data-stu-id="df7ea-541">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="df7ea-542">Befehl: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-542">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="df7ea-543">Ansehen `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-543">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="df7ea-544">Historysearchrückwärts</span><span class="sxs-lookup"><span data-stu-id="df7ea-544">HistorySearchBackward</span></span>

<span data-ttu-id="df7ea-545">Ersetzen Sie die aktuelle Eingabe durch das Element "Previous" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.</span><span class="sxs-lookup"><span data-stu-id="df7ea-545">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="df7ea-546">Befehl: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-546">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="df7ea-547">Historysearchforward</span><span class="sxs-lookup"><span data-stu-id="df7ea-547">HistorySearchForward</span></span>

<span data-ttu-id="df7ea-548">Ersetzen Sie die aktuelle Eingabe durch das Element "Next" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.</span><span class="sxs-lookup"><span data-stu-id="df7ea-548">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="df7ea-549">Befehl: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-549">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="df7ea-550">Nexthistory</span><span class="sxs-lookup"><span data-stu-id="df7ea-550">NextHistory</span></span>

<span data-ttu-id="df7ea-551">Ersetzen Sie die aktuelle Eingabe durch das "Next"-Element aus dem psleline-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="df7ea-551">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="df7ea-552">Befehl: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-552">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="df7ea-553">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-553">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="df7ea-554">VI-Einfügemodus: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-554">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="df7ea-555">VI-Befehlsmodus: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-555">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="df7ea-556">Previoushistory</span><span class="sxs-lookup"><span data-stu-id="df7ea-556">PreviousHistory</span></span>

<span data-ttu-id="df7ea-557">Ersetzen Sie die aktuelle Eingabe durch das "Previous"-Element aus dem psleline-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="df7ea-557">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="df7ea-558">Befehl: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-558">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="df7ea-559">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-559">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="df7ea-560">VI-Einfügemodus: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-560">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="df7ea-561">VI-Befehlsmodus: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="df7ea-561">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="df7ea-562">Reversesearchhistory</span><span class="sxs-lookup"><span data-stu-id="df7ea-562">ReverseSearchHistory</span></span>

<span data-ttu-id="df7ea-563">Führt eine inkrementelle Rückwärtssuche über den Verlauf durch</span><span class="sxs-lookup"><span data-stu-id="df7ea-563">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="df7ea-564">Befehl: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-564">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="df7ea-565">Ansehen `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-565">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="df7ea-566">Visearchhistoryrückwärts</span><span class="sxs-lookup"><span data-stu-id="df7ea-566">ViSearchHistoryBackward</span></span>

<span data-ttu-id="df7ea-567">Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.</span><span class="sxs-lookup"><span data-stu-id="df7ea-567">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="df7ea-568">VI-Einfügemodus: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-568">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="df7ea-569">VI-Befehlsmodus: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-569">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="df7ea-570">Vervollständigungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="df7ea-570">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="df7ea-571">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="df7ea-571">Complete</span></span>

<span data-ttu-id="df7ea-572">Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-572">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="df7ea-573">Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet.</span><span class="sxs-lookup"><span data-stu-id="df7ea-573">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="df7ea-574">Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-574">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="df7ea-575">Ansehen `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-575">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="df7ea-576">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="df7ea-576">MenuComplete</span></span>

<span data-ttu-id="df7ea-577">Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-577">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="df7ea-578">Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet.</span><span class="sxs-lookup"><span data-stu-id="df7ea-578">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="df7ea-579">Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-579">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="df7ea-580">Befehl: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-580">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="df7ea-581">Ansehen `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-581">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="df7ea-582">Possiblecompletions</span><span class="sxs-lookup"><span data-stu-id="df7ea-582">PossibleCompletions</span></span>

<span data-ttu-id="df7ea-583">Hiermit wird die Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-583">Display the list of possible completions.</span></span>

- <span data-ttu-id="df7ea-584">Ansehen `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-584">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="df7ea-585">VI-Einfügemodus: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-585">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="df7ea-586">VI-Befehlsmodus: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-586">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="df7ea-587">Tabcompletenext</span><span class="sxs-lookup"><span data-stu-id="df7ea-587">TabCompleteNext</span></span>

<span data-ttu-id="df7ea-588">Es wurde versucht, den Text, der den Cursor umgibt, mit der nächsten verfügbaren Beendigung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-588">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="df7ea-589">Befehl: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-589">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="df7ea-590">VI-Befehlsmodus: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-590">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="df7ea-591">Tabcompleteprevious</span><span class="sxs-lookup"><span data-stu-id="df7ea-591">TabCompletePrevious</span></span>

<span data-ttu-id="df7ea-592">Versuchen Sie, den Text, der den Cursor umgibt, mit dem vorherigen verfügbaren Abschluss abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-592">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="df7ea-593">Befehl: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-593">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="df7ea-594">VI-Befehlsmodus: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-594">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="df7ea-595">Vitabcompletenext</span><span class="sxs-lookup"><span data-stu-id="df7ea-595">ViTabCompleteNext</span></span>

<span data-ttu-id="df7ea-596">Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompletenext auf.</span><span class="sxs-lookup"><span data-stu-id="df7ea-596">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="df7ea-597">VI-Einfügemodus: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-597">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="df7ea-598">Vitabcompleteprevious</span><span class="sxs-lookup"><span data-stu-id="df7ea-598">ViTabCompletePrevious</span></span>

<span data-ttu-id="df7ea-599">Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompleteprevious auf.</span><span class="sxs-lookup"><span data-stu-id="df7ea-599">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="df7ea-600">VI-Einfügemodus: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-600">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="df7ea-601">Sonstige Funktionen</span><span class="sxs-lookup"><span data-stu-id="df7ea-601">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="df7ea-602">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="df7ea-602">CaptureScreen</span></span>

<span data-ttu-id="df7ea-603">Interaktive Bildschirmaufnahme starten-nach oben/nach-unten-Pfeile Select Lines, Enter kopiert markierten Text in die Zwischenablage als Text und HTML.</span><span class="sxs-lookup"><span data-stu-id="df7ea-603">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="df7ea-604">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-604">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="df7ea-605">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="df7ea-605">ClearScreen</span></span>

<span data-ttu-id="df7ea-606">Löschen Sie den Bildschirm, und zeichnen Sie die aktuelle Zeile am oberen Rand des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="df7ea-606">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="df7ea-607">Befehl: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-607">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="df7ea-608">Ansehen `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-608">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="df7ea-609">VI-Einfügemodus: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-609">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="df7ea-610">VI-Befehlsmodus: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-610">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="df7ea-611">Digitargument</span><span class="sxs-lookup"><span data-stu-id="df7ea-611">DigitArgument</span></span>

<span data-ttu-id="df7ea-612">Starten Sie ein neues Ziffern Argument, das an andere Funktionen übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="df7ea-612">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="df7ea-613">Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="df7ea-613">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="df7ea-614">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="df7ea-614">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="df7ea-615">VI-Befehlsmodus: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-615">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="df7ea-616">Invokeprompt</span><span class="sxs-lookup"><span data-stu-id="df7ea-616">InvokePrompt</span></span>

<span data-ttu-id="df7ea-617">Löscht die aktuelle Eingabeaufforderung und ruft die prompt-Funktion auf, um die Eingabeaufforderung erneut anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-617">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="df7ea-618">Nützlich für benutzerdefinierte Schlüssel Handler, die den Zustand ändern, z. b. Ändern des aktuellen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="df7ea-618">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="df7ea-619">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-619">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="df7ea-620">Scrolldisplaydown</span><span class="sxs-lookup"><span data-stu-id="df7ea-620">ScrollDisplayDown</span></span>

<span data-ttu-id="df7ea-621">Scrollen Sie in der Anzeige einen Bildschirm nach unten.</span><span class="sxs-lookup"><span data-stu-id="df7ea-621">Scroll the display down one screen.</span></span>

- <span data-ttu-id="df7ea-622">Befehl: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-622">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="df7ea-623">Ansehen `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-623">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="df7ea-624">Scrolldisplaydownline</span><span class="sxs-lookup"><span data-stu-id="df7ea-624">ScrollDisplayDownLine</span></span>

<span data-ttu-id="df7ea-625">Scrollen Sie in der Anzeige um eine Zeile nach unten.</span><span class="sxs-lookup"><span data-stu-id="df7ea-625">Scroll the display down one line.</span></span>

- <span data-ttu-id="df7ea-626">Befehl: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-626">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="df7ea-627">Ansehen `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-627">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="df7ea-628">Scrolldisplaytcursor</span><span class="sxs-lookup"><span data-stu-id="df7ea-628">ScrollDisplayToCursor</span></span>

<span data-ttu-id="df7ea-629">Scrollen Sie in der Anzeige zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-629">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="df7ea-630">Ansehen `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-630">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="df7ea-631">Scrolldisplaytop</span><span class="sxs-lookup"><span data-stu-id="df7ea-631">ScrollDisplayTop</span></span>

<span data-ttu-id="df7ea-632">Scrollen Sie in der Anzeige nach oben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-632">Scroll the display to the top.</span></span>

- <span data-ttu-id="df7ea-633">Ansehen `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-633">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="df7ea-634">Scrolldisplayup</span><span class="sxs-lookup"><span data-stu-id="df7ea-634">ScrollDisplayUp</span></span>

<span data-ttu-id="df7ea-635">Scrollen Sie einen Bildschirm nach oben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-635">Scroll the display up one screen.</span></span>

- <span data-ttu-id="df7ea-636">Befehl: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-636">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="df7ea-637">Ansehen `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-637">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="df7ea-638">Scrolldisplayupline</span><span class="sxs-lookup"><span data-stu-id="df7ea-638">ScrollDisplayUpLine</span></span>

<span data-ttu-id="df7ea-639">Scrollen Sie in der Anzeige um eine Zeile nach oben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-639">Scroll the display up one line.</span></span>

- <span data-ttu-id="df7ea-640">Befehl: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-640">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="df7ea-641">Ansehen `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-641">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="df7ea-642">Selfinsert</span><span class="sxs-lookup"><span data-stu-id="df7ea-642">SelfInsert</span></span>

<span data-ttu-id="df7ea-643">Fügen Sie den Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="df7ea-643">Insert the key.</span></span>

- <span data-ttu-id="df7ea-644">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-644">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="df7ea-645">Showkeybindungen</span><span class="sxs-lookup"><span data-stu-id="df7ea-645">ShowKeyBindings</span></span>

<span data-ttu-id="df7ea-646">Alle gebundenen Schlüssel anzeigen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-646">Show all bound keys.</span></span>

- <span data-ttu-id="df7ea-647">Befehl: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-647">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="df7ea-648">Ansehen `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-648">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="df7ea-649">VI-Einfügemodus: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-649">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="df7ea-650">Vicommandmode</span><span class="sxs-lookup"><span data-stu-id="df7ea-650">ViCommandMode</span></span>

<span data-ttu-id="df7ea-651">Wechseln Sie in den aktuellen Betriebsmodus von Vi-Insert zu VI-Command.</span><span class="sxs-lookup"><span data-stu-id="df7ea-651">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="df7ea-652">VI-Einfügemodus: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-652">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="df7ea-653">Vidigitargumentinchord</span><span class="sxs-lookup"><span data-stu-id="df7ea-653">ViDigitArgumentInChord</span></span>

<span data-ttu-id="df7ea-654">Startet ein neues Ziffern Argument, das in einem der VI-Akkorde an andere Funktionen übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="df7ea-654">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="df7ea-655">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-655">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="df7ea-656">Vieditvisuell</span><span class="sxs-lookup"><span data-stu-id="df7ea-656">ViEditVisually</span></span>

<span data-ttu-id="df7ea-657">Bearbeiten Sie die Befehlszeile in einem Text-Editor, der durch $ENV: Editor oder $env: Visual angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="df7ea-657">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="df7ea-658">Ansehen `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-658">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="df7ea-659">VI-Befehlsmodus: `<v>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-659">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="df7ea-660">Viexit</span><span class="sxs-lookup"><span data-stu-id="df7ea-660">ViExit</span></span>

<span data-ttu-id="df7ea-661">Beendet die Shell.</span><span class="sxs-lookup"><span data-stu-id="df7ea-661">Exits the shell.</span></span>

- <span data-ttu-id="df7ea-662">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-662">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="df7ea-663">Viinsertmode</span><span class="sxs-lookup"><span data-stu-id="df7ea-663">ViInsertMode</span></span>

<span data-ttu-id="df7ea-664">Wechselt in den Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="df7ea-664">Switch to Insert mode.</span></span>

- <span data-ttu-id="df7ea-665">VI-Befehlsmodus: `<i>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-665">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="df7ea-666">Whatiskey</span><span class="sxs-lookup"><span data-stu-id="df7ea-666">WhatIsKey</span></span>

<span data-ttu-id="df7ea-667">Lesen Sie einen Schlüssel, und teilen Sie mir mit, wofür der Schlüssel gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="df7ea-667">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="df7ea-668">Befehl: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-668">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="df7ea-669">Ansehen `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-669">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="df7ea-670">Auswahl Funktionen</span><span class="sxs-lookup"><span data-stu-id="df7ea-670">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="df7ea-671">Exchangepointandmark</span><span class="sxs-lookup"><span data-stu-id="df7ea-671">ExchangePointAndMark</span></span>

<span data-ttu-id="df7ea-672">Der Cursor wird an der Position der Markierung platziert, und die Markierung wird an die Position des Cursors verschoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-672">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="df7ea-673">Ansehen `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-673">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="df7ea-674">SelectAll</span><span class="sxs-lookup"><span data-stu-id="df7ea-674">SelectAll</span></span>

<span data-ttu-id="df7ea-675">Wählen Sie die gesamte Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="df7ea-675">Select the entire line.</span></span>

- <span data-ttu-id="df7ea-676">Befehl: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-676">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="df7ea-677">Selectbackwardchar</span><span class="sxs-lookup"><span data-stu-id="df7ea-677">SelectBackwardChar</span></span>

<span data-ttu-id="df7ea-678">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Zeichen einschließt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-678">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="df7ea-679">Befehl: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-679">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="df7ea-680">Ansehen `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-680">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="df7ea-681">Selectbackwardsline</span><span class="sxs-lookup"><span data-stu-id="df7ea-681">SelectBackwardsLine</span></span>

<span data-ttu-id="df7ea-682">Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an den Anfang der Zeile eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="df7ea-682">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="df7ea-683">Befehl: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-683">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="df7ea-684">Ansehen `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-684">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="df7ea-685">Selectbackwardword</span><span class="sxs-lookup"><span data-stu-id="df7ea-685">SelectBackwardWord</span></span>

<span data-ttu-id="df7ea-686">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort enthält.</span><span class="sxs-lookup"><span data-stu-id="df7ea-686">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="df7ea-687">Befehl: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-687">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="df7ea-688">Ansehen `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-688">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="df7ea-689">Selectforwardchar</span><span class="sxs-lookup"><span data-stu-id="df7ea-689">SelectForwardChar</span></span>

<span data-ttu-id="df7ea-690">Passen Sie die aktuelle Auswahl an, um das nächste Zeichen einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-690">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="df7ea-691">Befehl: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-691">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="df7ea-692">Ansehen `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-692">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="df7ea-693">Selectforwardword</span><span class="sxs-lookup"><span data-stu-id="df7ea-693">SelectForwardWord</span></span>

<span data-ttu-id="df7ea-694">Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mit forwardword einschließt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-694">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="df7ea-695">Ansehen `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-695">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="df7ea-696">SelectLine</span><span class="sxs-lookup"><span data-stu-id="df7ea-696">SelectLine</span></span>

<span data-ttu-id="df7ea-697">Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an das Ende der Zeile eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="df7ea-697">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="df7ea-698">Befehl: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-698">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="df7ea-699">Ansehen `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-699">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="df7ea-700">Selectnextword</span><span class="sxs-lookup"><span data-stu-id="df7ea-700">SelectNextWord</span></span>

<span data-ttu-id="df7ea-701">Passen Sie die aktuelle Auswahl an das nächste Wort an.</span><span class="sxs-lookup"><span data-stu-id="df7ea-701">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="df7ea-702">Befehl: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-702">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="df7ea-703">Selectshellbackwardword</span><span class="sxs-lookup"><span data-stu-id="df7ea-703">SelectShellBackwardWord</span></span>

<span data-ttu-id="df7ea-704">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort mithilfe von shellbackwardword einschließt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-704">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="df7ea-705">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-705">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="df7ea-706">Selectshellforwardword</span><span class="sxs-lookup"><span data-stu-id="df7ea-706">SelectShellForwardWord</span></span>

<span data-ttu-id="df7ea-707">Passen Sie die aktuelle Auswahl so an, dass das nächste Wort mithilfe von shellforwardword eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="df7ea-707">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="df7ea-708">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-708">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="df7ea-709">Selectshellnextword</span><span class="sxs-lookup"><span data-stu-id="df7ea-709">SelectShellNextWord</span></span>

<span data-ttu-id="df7ea-710">Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mithilfe von shellnextword einschließt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-710">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="df7ea-711">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-711">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="df7ea-712">Setmark</span><span class="sxs-lookup"><span data-stu-id="df7ea-712">SetMark</span></span>

<span data-ttu-id="df7ea-713">Markieren Sie die aktuelle Position des Cursors für die Verwendung in einem nachfolgenden Bearbeitungs Befehl.</span><span class="sxs-lookup"><span data-stu-id="df7ea-713">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="df7ea-714">Ansehen `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="df7ea-714">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="df7ea-715">Suchfunktionen</span><span class="sxs-lookup"><span data-stu-id="df7ea-715">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="df7ea-716">Merkmal Suche</span><span class="sxs-lookup"><span data-stu-id="df7ea-716">CharacterSearch</span></span>

<span data-ttu-id="df7ea-717">Lesen Sie ein Zeichen, und suchen Sie nach dem nächsten Vorkommen dieses Zeichens.</span><span class="sxs-lookup"><span data-stu-id="df7ea-717">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="df7ea-718">Wenn ein Argument angegeben ist, suchen Sie nach vorn (oder rückwärts, wenn negativ) für das n-te vorkommen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-718">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="df7ea-719">Befehl: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-719">Cmd: `<F3>`</span></span>
- <span data-ttu-id="df7ea-720">Ansehen `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-720">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="df7ea-721">VI-Einfügemodus: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-721">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="df7ea-722">VI-Befehlsmodus: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-722">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="df7ea-723">Merkmal searchrückwärts</span><span class="sxs-lookup"><span data-stu-id="df7ea-723">CharacterSearchBackward</span></span>

<span data-ttu-id="df7ea-724">Liest ein Zeichen und sucht rückwärts nach dem nächsten Vorkommen dieses Zeichens.</span><span class="sxs-lookup"><span data-stu-id="df7ea-724">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="df7ea-725">Wenn ein Argument angegeben wird, suchen Sie nach hinten (oder vorwärts, wenn negativ).</span><span class="sxs-lookup"><span data-stu-id="df7ea-725">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="df7ea-726">Befehl: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-726">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="df7ea-727">Ansehen `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-727">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="df7ea-728">VI-Einfügemodus: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-728">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="df7ea-729">VI-Befehlsmodus: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-729">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="df7ea-730">Repeatlastcharsearch</span><span class="sxs-lookup"><span data-stu-id="df7ea-730">RepeatLastCharSearch</span></span>

<span data-ttu-id="df7ea-731">Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche.</span><span class="sxs-lookup"><span data-stu-id="df7ea-731">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="df7ea-732">VI-Befehlsmodus: `<;>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-732">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="df7ea-733">Repeatlastcharsearchabwärts</span><span class="sxs-lookup"><span data-stu-id="df7ea-733">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="df7ea-734">Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche, aber in umgekehrter Richtung.</span><span class="sxs-lookup"><span data-stu-id="df7ea-734">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="df7ea-735">VI-Befehlsmodus: `<,>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-735">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="df7ea-736">Repeatsearch</span><span class="sxs-lookup"><span data-stu-id="df7ea-736">RepeatSearch</span></span>

<span data-ttu-id="df7ea-737">Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-737">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="df7ea-738">VI-Befehlsmodus: `<n>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-738">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="df7ea-739">Repeatsearchrückwärts</span><span class="sxs-lookup"><span data-stu-id="df7ea-739">RepeatSearchBackward</span></span>

<span data-ttu-id="df7ea-740">Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="df7ea-740">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="df7ea-741">VI-Befehlsmodus: `<N>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-741">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="df7ea-742">Searchchar</span><span class="sxs-lookup"><span data-stu-id="df7ea-742">SearchChar</span></span>

<span data-ttu-id="df7ea-743">Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="df7ea-743">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="df7ea-744">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="df7ea-744">This is for 't' functionality.</span></span>

- <span data-ttu-id="df7ea-745">VI-Befehlsmodus: `<f>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-745">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="df7ea-746">Searchcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="df7ea-746">SearchCharBackward</span></span>

<span data-ttu-id="df7ea-747">Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück.</span><span class="sxs-lookup"><span data-stu-id="df7ea-747">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="df7ea-748">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="df7ea-748">This is for 'T' functionality.</span></span>

- <span data-ttu-id="df7ea-749">VI-Befehlsmodus: `<F>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-749">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="df7ea-750">Searchcharbackwardwithbackoff</span><span class="sxs-lookup"><span data-stu-id="df7ea-750">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="df7ea-751">Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück.</span><span class="sxs-lookup"><span data-stu-id="df7ea-751">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="df7ea-752">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="df7ea-752">This is for 'T' functionality.</span></span>

- <span data-ttu-id="df7ea-753">VI-Befehlsmodus: `<T>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-753">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="df7ea-754">Searchcharwithbackoff</span><span class="sxs-lookup"><span data-stu-id="df7ea-754">SearchCharWithBackoff</span></span>

<span data-ttu-id="df7ea-755">Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="df7ea-755">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="df7ea-756">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="df7ea-756">This is for 't' functionality.</span></span>

- <span data-ttu-id="df7ea-757">VI-Befehlsmodus: `<t>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-757">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="df7ea-758">SearchForward</span><span class="sxs-lookup"><span data-stu-id="df7ea-758">SearchForward</span></span>

<span data-ttu-id="df7ea-759">Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.</span><span class="sxs-lookup"><span data-stu-id="df7ea-759">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="df7ea-760">VI-Einfügemodus: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-760">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="df7ea-761">VI-Befehlsmodus: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="df7ea-761">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="df7ea-762">Benutzerdefinierte Tastenbindungen</span><span class="sxs-lookup"><span data-stu-id="df7ea-762">Custom Key Bindings</span></span>

<span data-ttu-id="df7ea-763">Psread Line unterstützt benutzerdefinierte Tastenbindungen mithilfe des Cmdlets `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="df7ea-763">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="df7ea-764">Die meisten benutzerdefinierten Tastenbindungen wenden eine der oben genannten Funktionen an, z. b.</span><span class="sxs-lookup"><span data-stu-id="df7ea-764">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="df7ea-765">Sie können einen ScriptBlock an einen Schlüssel binden.</span><span class="sxs-lookup"><span data-stu-id="df7ea-765">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="df7ea-766">Der ScriptBlock kann beliebig viele Aufgaben erledigen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-766">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="df7ea-767">Einige nützliche Beispiele sind u.a.</span><span class="sxs-lookup"><span data-stu-id="df7ea-767">Some useful examples include</span></span>

- <span data-ttu-id="df7ea-768">Bearbeiten der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="df7ea-768">edit the command line</span></span>
- <span data-ttu-id="df7ea-769">Öffnen eines neuen Fensters (z. b. "Hilfe")</span><span class="sxs-lookup"><span data-stu-id="df7ea-769">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="df7ea-770">Ändern der Verzeichnisse ohne Änderung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="df7ea-770">change directories without changing the command line</span></span>

<span data-ttu-id="df7ea-771">Der ScriptBlock empfängt zwei Argumente:</span><span class="sxs-lookup"><span data-stu-id="df7ea-771">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="df7ea-772">`$key` -Ein **[ConsoleKeyInfo]** -Objekt, das der Schlüssel ist, der die benutzerdefinierte Bindung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="df7ea-772">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="df7ea-773">Wenn Sie denselben ScriptBlock an mehrere Schlüssel binden und abhängig vom Schlüssel verschiedene Aktionen ausführen müssen, können Sie $Key überprüfen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-773">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="df7ea-774">Viele benutzerdefinierte Bindungen ignorieren dieses Argument.</span><span class="sxs-lookup"><span data-stu-id="df7ea-774">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="df7ea-775">`$arg` -Ein beliebiges Argument.</span><span class="sxs-lookup"><span data-stu-id="df7ea-775">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="df7ea-776">In den meisten Fällen ist dies ein ganzzahliges Argument, das der Benutzer von den Schlüsselbindungen digitargument übergibt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-776">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="df7ea-777">Wenn die Bindung keine Argumente akzeptiert, ist es sinnvoll, dieses Argument zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="df7ea-777">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="df7ea-778">Sehen wir uns ein Beispiel an, in dem eine Befehlszeile zum Verlauf hinzugefügt wird, ohne sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-778">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="df7ea-779">Dies ist nützlich, wenn Sie vergessen haben, etwas zu tun, ohne die Befehlszeile, die Sie bereits eingegeben haben, erneut eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-779">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

```powershell
$parameters = @{
    Key = 'Alt+w'
    BriefDescription = 'SaveInHistory'
    LongDescription = 'Save current line in history but do not execute'
    ScriptBlock = {
      param($key, $arg)   # The arguments are ignored in this example

      # GetBufferState gives us the command line (with the cursor position)
      $line = $null
      $cursor = $null
      [Microsoft.PowerShell.PSConsoleReadLine]::GetBufferState([ref]$line,
        [ref]$cursor)

      # AddToHistory saves the line in history, but does not execute it.
      [Microsoft.PowerShell.PSConsoleReadLine]::AddToHistory($line)

      # RevertLine is like pressing Escape.
      [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
  }
}
Set-PSReadLineKeyHandler @parameters
```

<span data-ttu-id="df7ea-780">In der Datei `SamplePSReadLineProfile.ps1` , die im psread Line-Modul Ordner installiert ist, werden viele weitere Beispiele angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-780">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="df7ea-781">Die meisten Tastenbindungen verwenden einige Hilfsfunktionen zum Bearbeiten der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="df7ea-781">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="df7ea-782">Diese APIs werden im nächsten Abschnitt dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="df7ea-782">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="df7ea-783">APIs für die benutzerdefinierte Schlüssel Bindungs Unterstützung</span><span class="sxs-lookup"><span data-stu-id="df7ea-783">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="df7ea-784">Die folgenden Funktionen sind in Microsoft. PowerShell. psconsolereadline öffentlich, können jedoch nicht direkt an einen Schlüssel gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="df7ea-784">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="df7ea-785">Die meisten sind in benutzerdefinierten Tastenkombinationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="df7ea-785">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="df7ea-786">Fügen Sie eine Befehlszeile zum Verlauf hinzu, ohne sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-786">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="df7ea-787">Löschen Sie den Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="df7ea-787">Clear the kill-ring.</span></span>  <span data-ttu-id="df7ea-788">Dies wird größtenteils zum Testen verwendet.</span><span class="sxs-lookup"><span data-stu-id="df7ea-788">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="df7ea-789">Löschen Sie die Längen Zeichen aus dem Startmenü.</span><span class="sxs-lookup"><span data-stu-id="df7ea-789">Delete length characters from start.</span></span>  <span data-ttu-id="df7ea-790">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-790">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="df7ea-791">Führen Sie die Aktion "Ding" basierend auf der Benutzereinstellung aus.</span><span class="sxs-lookup"><span data-stu-id="df7ea-791">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="df7ea-792">Diese beiden Funktionen rufen nützliche Informationen über den aktuellen Status des Eingabe Puffers ab.</span><span class="sxs-lookup"><span data-stu-id="df7ea-792">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="df7ea-793">Der erste wird häufiger für einfache Fälle verwendet.</span><span class="sxs-lookup"><span data-stu-id="df7ea-793">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="df7ea-794">Die zweite wird verwendet, wenn ihre Bindung einen fortgeschrittenen Vorgang mit der AST bewirkt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-794">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="df7ea-795">Diese Funktion wird von Get-PSReadLineKeyHandler verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht nützlich.</span><span class="sxs-lookup"><span data-stu-id="df7ea-795">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="df7ea-796">Diese Funktion wird von Get-PSReadLineOption verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.</span><span class="sxs-lookup"><span data-stu-id="df7ea-796">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="df7ea-797">Wenn in der Befehlszeile keine Auswahl vorhanden ist, wird-1 sowohl in Start als auch in der Länge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-797">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="df7ea-798">Wenn eine Auswahl in der Befehlszeile vorhanden ist, werden Start und Länge der Auswahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-798">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="df7ea-799">Fügen Sie am Cursor ein Zeichen oder eine Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="df7ea-799">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="df7ea-800">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-800">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="df7ea-801">Dies ist der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="df7ea-801">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="df7ea-802">Sie unterstützt keine Rekursion und ist daher in einer benutzerdefinierten schlüsselbindung nicht nützlich.</span><span class="sxs-lookup"><span data-stu-id="df7ea-802">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="df7ea-803">Diese Funktion wird von Remove-PSReadLineKeyHandler verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.</span><span class="sxs-lookup"><span data-stu-id="df7ea-803">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="df7ea-804">Ersetzen Sie einige der Eingaben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-804">Replace some of the input.</span></span> <span data-ttu-id="df7ea-805">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-805">This operation supports undo/redo.</span></span> <span data-ttu-id="df7ea-806">Dies wird als "Delete", gefolgt von INSERT, bevorzugt, da es als einzelne Aktion für "Rückgängig" behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="df7ea-806">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="df7ea-807">Bewegen Sie den Cursor in den angegebenen Offset.</span><span class="sxs-lookup"><span data-stu-id="df7ea-807">Move the cursor to the given offset.</span></span> <span data-ttu-id="df7ea-808">Cursor Bewegung wird nicht für Rückgängigmachen nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="df7ea-808">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="df7ea-809">Bei dieser Funktion handelt es sich um eine Hilfsmethode, die vom Cmdlet Set-psread lineoption verwendet wird. Sie kann jedoch für eine benutzerdefinierte schlüsselbindung nützlich sein, die eine Einstellung vorübergehend ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="df7ea-809">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="df7ea-810">Diese Hilfsmethode wird für benutzerdefinierte Bindungen verwendet, die digitargument berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-810">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="df7ea-811">Ein typischer-Rückruf sieht wie folgt aus</span><span class="sxs-lookup"><span data-stu-id="df7ea-811">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="df7ea-812">HINWEIS</span><span class="sxs-lookup"><span data-stu-id="df7ea-812">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="df7ea-813">PowerShell-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="df7ea-813">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="df7ea-814">Für psread line sind PowerShell 3,0 oder höher sowie der Konsolen Host erforderlich.</span><span class="sxs-lookup"><span data-stu-id="df7ea-814">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="df7ea-815">Es funktioniert nicht in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="df7ea-815">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="df7ea-816">Dies funktioniert in der-Konsole Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="df7ea-816">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="df7ea-817">Befehlsverlauf</span><span class="sxs-lookup"><span data-stu-id="df7ea-817">COMMAND HISTORY</span></span>

<span data-ttu-id="df7ea-818">Psleseline verwaltet eine Verlaufs Datei, die alle Befehle und Daten enthält, die Sie in der Befehlszeile eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="df7ea-818">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="df7ea-819">Dies kann vertrauliche Daten einschließlich Kenn Wörtern enthalten.</span><span class="sxs-lookup"><span data-stu-id="df7ea-819">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="df7ea-820">Wenn Sie z. b. das `ConvertTo-SecureString` Cmdlet verwenden, wird das Kennwort als nur-Text in der Verlaufs Datei protokolliert.</span><span class="sxs-lookup"><span data-stu-id="df7ea-820">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="df7ea-821">Die Verlaufs Dateien sind eine Datei mit dem Namen `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="df7ea-821">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="df7ea-822">Auf Windows-Systemen wird die Verlaufs Datei unter gespeichert `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="df7ea-822">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="df7ea-823">Feedback & zu psread Line beitragen</span><span class="sxs-lookup"><span data-stu-id="df7ea-823">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="df7ea-824">Psread Line auf GitHub</span><span class="sxs-lookup"><span data-stu-id="df7ea-824">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="df7ea-825">Sie können auf der GitHub-Seite eine Pull Request einreichen oder Feedback einreichen.</span><span class="sxs-lookup"><span data-stu-id="df7ea-825">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="df7ea-826">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="df7ea-826">SEE ALSO</span></span>

<span data-ttu-id="df7ea-827">"Psread Line" wird stark von der GNU-Bibliothek für die [Zeilen](https://tiswww.case.edu/php/chet/readline/rltop.html) Übereinstimmung beeinflusst</span><span class="sxs-lookup"><span data-stu-id="df7ea-827">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
