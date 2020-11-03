---
description: Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über psread Line
ms.openlocfilehash: 5b59ffcdfb35c2aa10f8e0caf3a3b365c5bcf93e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223692"
---
# <a name="psreadline"></a><span data-ttu-id="c85c9-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="c85c9-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="c85c9-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="c85c9-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="c85c9-106">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c85c9-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="c85c9-107">Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="c85c9-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="c85c9-108">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c85c9-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="c85c9-109">Psleline 2,0 bietet eine leistungsfähige Befehlszeilen Bearbeitungsfunktion für die PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="c85c9-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="c85c9-110">Sie bietet:</span><span class="sxs-lookup"><span data-stu-id="c85c9-110">It provides:</span></span>

- <span data-ttu-id="c85c9-111">Syntax Farbgebung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="c85c9-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="c85c9-112">Visuelle Hinweise auf Syntax Fehler</span><span class="sxs-lookup"><span data-stu-id="c85c9-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="c85c9-113">Bessere mehrzeilige Erfahrung (sowohl Bearbeitung als auch Verlauf)</span><span class="sxs-lookup"><span data-stu-id="c85c9-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="c85c9-114">Anpassbare Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="c85c9-114">Customizable key bindings</span></span>
- <span data-ttu-id="c85c9-115">Cmd-und Emacs-Modi</span><span class="sxs-lookup"><span data-stu-id="c85c9-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="c85c9-116">Viele Konfigurationsoptionen</span><span class="sxs-lookup"><span data-stu-id="c85c9-116">Many configuration options</span></span>
- <span data-ttu-id="c85c9-117">Bash-Stil Vervollständigung (optional im cmd-Modus, Standard im Emacs-Modus)</span><span class="sxs-lookup"><span data-stu-id="c85c9-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="c85c9-118">Emacs: Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="c85c9-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="c85c9-119">PowerShell-tokenbasierte "Wort Bewegung" und "Kill"</span><span class="sxs-lookup"><span data-stu-id="c85c9-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="c85c9-120">Die folgenden Funktionen sind in der-Klasse **[Microsoft. PowerShell. psconsolereadline]** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c85c9-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

> [!NOTE]
> <span data-ttu-id="c85c9-121">Ab PowerShell 7,0 überspringt PowerShell das automatische Laden von psleseline unter Windows, wenn ein Bildschirm Leseprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="c85c9-121">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="c85c9-122">Derzeit funktioniert psread Line nicht gut mit den Bildschirmlesern.</span><span class="sxs-lookup"><span data-stu-id="c85c9-122">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="c85c9-123">Das Standard Rendering und die Formatierung von PowerShell 7,0 unter Windows funktionieren ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="c85c9-123">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="c85c9-124">Sie können das Modul ggf. manuell laden.</span><span class="sxs-lookup"><span data-stu-id="c85c9-124">You can manually load the module if necessary.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="c85c9-125">Grundlegende Bearbeitungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="c85c9-125">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="c85c9-126">Abbruch</span><span class="sxs-lookup"><span data-stu-id="c85c9-126">Abort</span></span>

<span data-ttu-id="c85c9-127">Abbrechen der aktuellen Aktion, z.b. inkrementelle Verlaufs Suche.</span><span class="sxs-lookup"><span data-stu-id="c85c9-127">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="c85c9-128">Ansehen `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-128">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="c85c9-129">Akzeptandgetnext</span><span class="sxs-lookup"><span data-stu-id="c85c9-129">AcceptAndGetNext</span></span>

<span data-ttu-id="c85c9-130">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-130">Attempt to execute the current input.</span></span> <span data-ttu-id="c85c9-131">Wenn Sie ausgeführt werden kann (wie z. b. Accept Line), erinnern Sie sich beim nächsten Aufruf von "read line" an das nächste Element aus dem Verlauf.</span><span class="sxs-lookup"><span data-stu-id="c85c9-131">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="c85c9-132">Ansehen `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-132">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="c85c9-133">Annahme</span><span class="sxs-lookup"><span data-stu-id="c85c9-133">AcceptLine</span></span>

<span data-ttu-id="c85c9-134">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-134">Attempt to execute the current input.</span></span> <span data-ttu-id="c85c9-135">Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c85c9-135">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="c85c9-136">Befehl: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-136">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="c85c9-137">Ansehen `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-137">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="c85c9-138">VI-Einfügemodus: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-138">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="c85c9-139">AddLine</span><span class="sxs-lookup"><span data-stu-id="c85c9-139">AddLine</span></span>

<span data-ttu-id="c85c9-140">Die Fortsetzungs Aufforderung wird in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c85c9-140">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="c85c9-141">Dies ist nützlich, um mehrzeilige Eingaben als einen einzelnen Befehl einzugeben, auch wenn eine einzelne Zeile allein eine Eingabe ist.</span><span class="sxs-lookup"><span data-stu-id="c85c9-141">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="c85c9-142">Befehl: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-142">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="c85c9-143">Ansehen `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-143">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="c85c9-144">VI-Einfügemodus: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-144">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="c85c9-145">VI-Befehlsmodus: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-145">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="c85c9-146">Backwarddeletechar</span><span class="sxs-lookup"><span data-stu-id="c85c9-146">BackwardDeleteChar</span></span>

<span data-ttu-id="c85c9-147">Löschen Sie das Zeichen vor dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-147">Delete the character before the cursor.</span></span>

- <span data-ttu-id="c85c9-148">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-148">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="c85c9-149">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-149">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="c85c9-150">VI-Einfügemodus: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-150">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="c85c9-151">VI-Befehlsmodus: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-151">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="c85c9-152">Backwarddelta-Eline</span><span class="sxs-lookup"><span data-stu-id="c85c9-152">BackwardDeleteLine</span></span>

<span data-ttu-id="c85c9-153">Wie backwardkillline löscht Text vom Punkt bis zum Anfang der Zeile, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-153">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="c85c9-154">Befehl: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-154">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="c85c9-155">VI-Einfügemodus: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-155">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="c85c9-156">VI-Befehlsmodus: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-156">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="c85c9-157">Backwarddeleteword</span><span class="sxs-lookup"><span data-stu-id="c85c9-157">BackwardDeleteWord</span></span>

<span data-ttu-id="c85c9-158">Löscht das vorherige Wort.</span><span class="sxs-lookup"><span data-stu-id="c85c9-158">Deletes the previous word.</span></span>

- <span data-ttu-id="c85c9-159">VI-Befehlsmodus: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-159">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="c85c9-160">Backwardkillline</span><span class="sxs-lookup"><span data-stu-id="c85c9-160">BackwardKillLine</span></span>

<span data-ttu-id="c85c9-161">Löschen Sie die Eingabe vom Beginn der Eingabe in den Cursor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-161">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="c85c9-162">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-162">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="c85c9-163">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-163">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="c85c9-164">Backwardkillword</span><span class="sxs-lookup"><span data-stu-id="c85c9-164">BackwardKillWord</span></span>

<span data-ttu-id="c85c9-165">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-165">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="c85c9-166">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c85c9-166">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="c85c9-167">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-167">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="c85c9-168">Befehl: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-168">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="c85c9-169">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-169">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="c85c9-170">VI-Einfügemodus: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-170">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="c85c9-171">VI-Befehlsmodus: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-171">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="c85c9-172">Cancelline</span><span class="sxs-lookup"><span data-stu-id="c85c9-172">CancelLine</span></span>

<span data-ttu-id="c85c9-173">Brechen Sie die aktuelle Eingabe ab, belassen Sie die Eingabe auf dem Bildschirm, kehren Sie jedoch zurück zum Host, damit die Eingabeaufforderung erneut ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="c85c9-173">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="c85c9-174">VI-Einfügemodus: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-174">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="c85c9-175">VI-Befehlsmodus: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-175">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="c85c9-176">Kopieren</span><span class="sxs-lookup"><span data-stu-id="c85c9-176">Copy</span></span>

<span data-ttu-id="c85c9-177">Kopiert den ausgewählten Bereich in die Zwischenablage des Systems.</span><span class="sxs-lookup"><span data-stu-id="c85c9-177">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="c85c9-178">Wenn keine Region ausgewählt ist, kopieren Sie die gesamte Zeile.</span><span class="sxs-lookup"><span data-stu-id="c85c9-178">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="c85c9-179">Befehl: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-179">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="c85c9-180">Copyorcancelline</span><span class="sxs-lookup"><span data-stu-id="c85c9-180">CopyOrCancelLine</span></span>

<span data-ttu-id="c85c9-181">Wenn Text ausgewählt ist, kopieren Sie ihn in die Zwischenablage, andernfalls brechen Sie die Zeile ab.</span><span class="sxs-lookup"><span data-stu-id="c85c9-181">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="c85c9-182">Befehl: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-182">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="c85c9-183">Ansehen `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-183">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="c85c9-184">Ausschneiden</span><span class="sxs-lookup"><span data-stu-id="c85c9-184">Cut</span></span>

<span data-ttu-id="c85c9-185">Löscht die ausgewählte Region, in der Gelöschter Text in der Zwischenablage des Systems</span><span class="sxs-lookup"><span data-stu-id="c85c9-185">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="c85c9-186">Befehl: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-186">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="c85c9-187">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="c85c9-187">DeleteChar</span></span>

<span data-ttu-id="c85c9-188">Löschen Sie das Zeichen unter dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-188">Delete the character under the cursor.</span></span>

- <span data-ttu-id="c85c9-189">Befehl: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-189">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="c85c9-190">Ansehen `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-190">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="c85c9-191">VI-Einfügemodus: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-191">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="c85c9-192">VI-Befehlsmodus: `<Delete>` , `<x>` , `<d,l>` , `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-192">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="c85c9-193">Deletecharorexit</span><span class="sxs-lookup"><span data-stu-id="c85c9-193">DeleteCharOrExit</span></span>

<span data-ttu-id="c85c9-194">Löschen Sie das Zeichen unter dem Cursor, oder beenden Sie den Prozess, wenn die Zeile leer ist.</span><span class="sxs-lookup"><span data-stu-id="c85c9-194">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="c85c9-195">Ansehen `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-195">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="c85c9-196">Deleteendof</span><span class="sxs-lookup"><span data-stu-id="c85c9-196">DeleteEndOfWord</span></span>

<span data-ttu-id="c85c9-197">Bis zum Ende des Worts löschen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-197">Delete to the end of the word.</span></span>

- <span data-ttu-id="c85c9-198">VI-Befehlsmodus: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-198">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="c85c9-199">"Deleteline</span><span class="sxs-lookup"><span data-stu-id="c85c9-199">DeleteLine</span></span>

<span data-ttu-id="c85c9-200">Löscht die aktuelle Zeile und aktiviert die Rückgängigmachen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-200">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="c85c9-201">VI-Befehlsmodus: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-201">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="c85c9-202">Delta-inetyp</span><span class="sxs-lookup"><span data-stu-id="c85c9-202">DeleteLineToFirstChar</span></span>

<span data-ttu-id="c85c9-203">Löscht Text vom Cursor zum ersten Zeichen der Zeile, das nicht leer ist.</span><span class="sxs-lookup"><span data-stu-id="c85c9-203">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="c85c9-204">VI-Befehlsmodus: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-204">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="c85c9-205">Deletegeend</span><span class="sxs-lookup"><span data-stu-id="c85c9-205">DeleteToEnd</span></span>

<span data-ttu-id="c85c9-206">Bis zum Ende der Zeile löschen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-206">Delete to the end of the line.</span></span>

- <span data-ttu-id="c85c9-207">VI-Befehlsmodus: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-207">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="c85c9-208">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="c85c9-208">DeleteWord</span></span>

<span data-ttu-id="c85c9-209">Löschen Sie das nächste Wort.</span><span class="sxs-lookup"><span data-stu-id="c85c9-209">Delete the next word.</span></span>

- <span data-ttu-id="c85c9-210">VI-Befehlsmodus: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-210">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="c85c9-211">Forwarddelta-Eline</span><span class="sxs-lookup"><span data-stu-id="c85c9-211">ForwardDeleteLine</span></span>

<span data-ttu-id="c85c9-212">Wie forwardkillline löscht Text vom Punkt bis zum Ende der Zeile, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-212">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="c85c9-213">Befehl: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-213">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="c85c9-214">VI-Einfügemodus: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-214">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="c85c9-215">VI-Befehlsmodus: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-215">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="c85c9-216">Insertlineoberhalb</span><span class="sxs-lookup"><span data-stu-id="c85c9-216">InsertLineAbove</span></span>

<span data-ttu-id="c85c9-217">Oberhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="c85c9-217">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="c85c9-218">Der Cursor wechselt zum Anfang der neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="c85c9-218">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="c85c9-219">Befehl: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-219">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="c85c9-220">Insertlinebelow</span><span class="sxs-lookup"><span data-stu-id="c85c9-220">InsertLineBelow</span></span>

<span data-ttu-id="c85c9-221">Unterhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="c85c9-221">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="c85c9-222">Der Cursor wechselt zum Anfang der neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="c85c9-222">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="c85c9-223">Befehl: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-223">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="c85c9-224">Invertieren</span><span class="sxs-lookup"><span data-stu-id="c85c9-224">InvertCase</span></span>

<span data-ttu-id="c85c9-225">Kehrt die Groß-/Kleinschreibung des aktuellen Zeichens um und wechselt zum nächsten.</span><span class="sxs-lookup"><span data-stu-id="c85c9-225">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="c85c9-226">VI-Befehlsmodus: `<~>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-226">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="c85c9-227">Killline</span><span class="sxs-lookup"><span data-stu-id="c85c9-227">KillLine</span></span>

<span data-ttu-id="c85c9-228">Löschen Sie die Eingabe vom Cursor bis zum Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="c85c9-228">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="c85c9-229">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-229">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="c85c9-230">Ansehen `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-230">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="c85c9-231">Killregion</span><span class="sxs-lookup"><span data-stu-id="c85c9-231">KillRegion</span></span>

<span data-ttu-id="c85c9-232">Beenden Sie den Text zwischen dem Cursor und der Markierung.</span><span class="sxs-lookup"><span data-stu-id="c85c9-232">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="c85c9-233">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-233">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="c85c9-234">Killword</span><span class="sxs-lookup"><span data-stu-id="c85c9-234">KillWord</span></span>

<span data-ttu-id="c85c9-235">Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts.</span><span class="sxs-lookup"><span data-stu-id="c85c9-235">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="c85c9-236">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c85c9-236">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="c85c9-237">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-237">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="c85c9-238">Befehl: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-238">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="c85c9-239">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-239">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="c85c9-240">VI-Einfügemodus: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-240">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="c85c9-241">VI-Befehlsmodus: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-241">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="c85c9-242">Einfügen</span><span class="sxs-lookup"><span data-stu-id="c85c9-242">Paste</span></span>

<span data-ttu-id="c85c9-243">Fügen Sie Text aus der Zwischenablage des Systems ein.</span><span class="sxs-lookup"><span data-stu-id="c85c9-243">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="c85c9-244">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-244">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="c85c9-245">VI-Einfügemodus: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-245">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="c85c9-246">VI-Befehlsmodus: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-246">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c85c9-247">Wenn Sie die Funktion **Einfügen** verwenden, wird der gesamte Inhalt des Zwischenablage Puffers in den Eingabepuffer von psread Line eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-247">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="c85c9-248">Der Eingabepuffer wird dann an den PowerShell-Parser übergeben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-248">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="c85c9-249">Eingaben, die mithilfe der **Rechtsklick-Einfügemethode** der Konsolenanwendung eingefügt werden, werden jeweils ein Zeichen in den Eingabepuffer kopiert.</span><span class="sxs-lookup"><span data-stu-id="c85c9-249">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="c85c9-250">Der Eingabepuffer wird an den Parser übergeben, wenn ein Zeilen vorzeichensatz kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="c85c9-250">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="c85c9-251">Daher wird die Eingabe jeweils Zeilen gleich analysiert.</span><span class="sxs-lookup"><span data-stu-id="c85c9-251">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="c85c9-252">Der Unterschied zwischen den Methoden zum Einfügen führt zu einem anderen Ausführungs Verhalten.</span><span class="sxs-lookup"><span data-stu-id="c85c9-252">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="c85c9-253">Pasteafter</span><span class="sxs-lookup"><span data-stu-id="c85c9-253">PasteAfter</span></span>

<span data-ttu-id="c85c9-254">Fügen Sie die Zwischenablage nach dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.</span><span class="sxs-lookup"><span data-stu-id="c85c9-254">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="c85c9-255">VI-Befehlsmodus: `<p>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-255">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="c85c9-256">Pastebefore</span><span class="sxs-lookup"><span data-stu-id="c85c9-256">PasteBefore</span></span>

<span data-ttu-id="c85c9-257">Fügen Sie die Zwischenablage vor dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.</span><span class="sxs-lookup"><span data-stu-id="c85c9-257">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="c85c9-258">VI-Befehlsmodus: `<P>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-258">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="c85c9-259">Prepdandaccept</span><span class="sxs-lookup"><span data-stu-id="c85c9-259">PrependAndAccept</span></span>

<span data-ttu-id="c85c9-260">Fügen Sie ein "#" vorangesteht, und akzeptieren Sie die Zeile.</span><span class="sxs-lookup"><span data-stu-id="c85c9-260">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="c85c9-261">VI-Befehlsmodus: `<#>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-261">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="c85c9-262">Wiederholen</span><span class="sxs-lookup"><span data-stu-id="c85c9-262">Redo</span></span>

<span data-ttu-id="c85c9-263">Rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-263">Undo an undo.</span></span>

- <span data-ttu-id="c85c9-264">Befehl: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-264">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="c85c9-265">VI-Einfügemodus: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-265">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="c85c9-266">VI-Befehlsmodus: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-266">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="c85c9-267">Repeatlastcommand</span><span class="sxs-lookup"><span data-stu-id="c85c9-267">RepeatLastCommand</span></span>

<span data-ttu-id="c85c9-268">Wiederholen Sie die letzte Textänderung.</span><span class="sxs-lookup"><span data-stu-id="c85c9-268">Repeat the last text modification.</span></span>

- <span data-ttu-id="c85c9-269">VI-Befehlsmodus: `<.>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-269">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="c85c9-270">Revertline</span><span class="sxs-lookup"><span data-stu-id="c85c9-270">RevertLine</span></span>

<span data-ttu-id="c85c9-271">Kehrt alle Eingaben in die aktuelle Eingabe um.</span><span class="sxs-lookup"><span data-stu-id="c85c9-271">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="c85c9-272">Befehl: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-272">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="c85c9-273">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-273">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="c85c9-274">Shellbackwardkillword</span><span class="sxs-lookup"><span data-stu-id="c85c9-274">ShellBackwardKillWord</span></span>

<span data-ttu-id="c85c9-275">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-275">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="c85c9-276">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c85c9-276">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="c85c9-277">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-277">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="c85c9-278">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-278">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="c85c9-279">Shellkillword</span><span class="sxs-lookup"><span data-stu-id="c85c9-279">ShellKillWord</span></span>

<span data-ttu-id="c85c9-280">Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts.</span><span class="sxs-lookup"><span data-stu-id="c85c9-280">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="c85c9-281">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c85c9-281">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="c85c9-282">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-282">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="c85c9-283">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-283">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="c85c9-284">Austausch Zeichen</span><span class="sxs-lookup"><span data-stu-id="c85c9-284">SwapCharacters</span></span>

<span data-ttu-id="c85c9-285">Tauschen Sie das aktuelle und das aktuelle Zeichen aus.</span><span class="sxs-lookup"><span data-stu-id="c85c9-285">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="c85c9-286">Ansehen `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-286">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="c85c9-287">VI-Einfügemodus: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-287">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="c85c9-288">VI-Befehlsmodus: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-288">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="c85c9-289">Rückgängig</span><span class="sxs-lookup"><span data-stu-id="c85c9-289">Undo</span></span>

<span data-ttu-id="c85c9-290">Rückgängigmachen einer vorherigen Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="c85c9-290">Undo a previous edit.</span></span>

- <span data-ttu-id="c85c9-291">Befehl: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-291">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="c85c9-292">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-292">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="c85c9-293">VI-Einfügemodus: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-293">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="c85c9-294">VI-Befehlsmodus: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-294">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="c85c9-295">Nicht doall</span><span class="sxs-lookup"><span data-stu-id="c85c9-295">UndoAll</span></span>

<span data-ttu-id="c85c9-296">Alle vorherigen Änderungen für die Zeile rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-296">Undo all previous edits for line.</span></span>

- <span data-ttu-id="c85c9-297">VI-Befehlsmodus: `<U>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-297">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="c85c9-298">Unixwordrubout</span><span class="sxs-lookup"><span data-stu-id="c85c9-298">UnixWordRubout</span></span>

<span data-ttu-id="c85c9-299">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-299">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="c85c9-300">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c85c9-300">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="c85c9-301">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-301">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="c85c9-302">Ansehen `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-302">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="c85c9-303">Validateandakzeptline</span><span class="sxs-lookup"><span data-stu-id="c85c9-303">ValidateAndAcceptLine</span></span>

<span data-ttu-id="c85c9-304">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-304">Attempt to execute the current input.</span></span> <span data-ttu-id="c85c9-305">Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c85c9-305">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="c85c9-306">Ansehen `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-306">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="c85c9-307">Viakzeptline</span><span class="sxs-lookup"><span data-stu-id="c85c9-307">ViAcceptLine</span></span>

<span data-ttu-id="c85c9-308">Akzeptieren Sie die Zeile, und wechseln Sie zum Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="c85c9-308">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="c85c9-309">VI-Befehlsmodus: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-309">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="c85c9-310">Viakzeptlineorexit</span><span class="sxs-lookup"><span data-stu-id="c85c9-310">ViAcceptLineOrExit</span></span>

<span data-ttu-id="c85c9-311">Wie deletecharorexit im Emacs-Modus, akzeptiert jedoch die Zeile, anstatt ein Zeichen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-311">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="c85c9-312">VI-Einfügemodus: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-312">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="c85c9-313">VI-Befehlsmodus: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-313">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="c85c9-314">Viappendline</span><span class="sxs-lookup"><span data-stu-id="c85c9-314">ViAppendLine</span></span>

<span data-ttu-id="c85c9-315">Unterhalb der aktuellen Zeile wird eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-315">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="c85c9-316">VI-Befehlsmodus: `<o>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-316">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="c85c9-317">Vibackwarddeleteglob</span><span class="sxs-lookup"><span data-stu-id="c85c9-317">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="c85c9-318">Löscht das vorherige Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c85c9-318">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="c85c9-319">VI-Befehlsmodus: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-319">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="c85c9-320">Vibackwardglob</span><span class="sxs-lookup"><span data-stu-id="c85c9-320">ViBackwardGlob</span></span>

<span data-ttu-id="c85c9-321">Verschiebt den Cursor zurück an den Anfang des vorherigen Worts, wobei nur Leerraum als Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c85c9-321">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="c85c9-322">VI-Befehlsmodus: `<B>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-322">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="c85c9-323">Videletebrace</span><span class="sxs-lookup"><span data-stu-id="c85c9-323">ViDeleteBrace</span></span>

<span data-ttu-id="c85c9-324">Suchen Sie nach der passenden geschweiften Klammer, Klammer oder eckigen Klammer, und löschen Sie alle Inhalte in, einschließlich der geschweiften Klammer.</span><span class="sxs-lookup"><span data-stu-id="c85c9-324">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="c85c9-325">VI-Befehlsmodus: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-325">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="c85c9-326">Videleteendobglob</span><span class="sxs-lookup"><span data-stu-id="c85c9-326">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="c85c9-327">Bis zum Ende des Worts löschen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-327">Delete to the end of the word.</span></span>

- <span data-ttu-id="c85c9-328">VI-Befehlsmodus: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-328">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="c85c9-329">Videleteglob</span><span class="sxs-lookup"><span data-stu-id="c85c9-329">ViDeleteGlob</span></span>

<span data-ttu-id="c85c9-330">Löschen Sie den nächsten globmuster (Leerzeichen mit Trennzeichen).</span><span class="sxs-lookup"><span data-stu-id="c85c9-330">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="c85c9-331">VI-Befehlsmodus: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-331">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="c85c9-332">Videletetobeforechar</span><span class="sxs-lookup"><span data-stu-id="c85c9-332">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="c85c9-333">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-333">Deletes until given character.</span></span>

- <span data-ttu-id="c85c9-334">VI-Befehlsmodus: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-334">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="c85c9-335">Videletebackbeforecharrückwärts</span><span class="sxs-lookup"><span data-stu-id="c85c9-335">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="c85c9-336">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-336">Deletes until given character.</span></span>

- <span data-ttu-id="c85c9-337">VI-Befehlsmodus: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-337">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="c85c9-338">Videleteto Char</span><span class="sxs-lookup"><span data-stu-id="c85c9-338">ViDeleteToChar</span></span>

<span data-ttu-id="c85c9-339">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-339">Deletes until given character.</span></span>

- <span data-ttu-id="c85c9-340">VI-Befehlsmodus: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-340">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="c85c9-341">Videletebackcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="c85c9-341">ViDeleteToCharBackward</span></span>

<span data-ttu-id="c85c9-342">Löscht rückwärts bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-342">Deletes backwards until given character.</span></span>

- <span data-ttu-id="c85c9-343">VI-Befehlsmodus: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-343">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="c85c9-344">Viinsertatbeginung</span><span class="sxs-lookup"><span data-stu-id="c85c9-344">ViInsertAtBegining</span></span>

<span data-ttu-id="c85c9-345">Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Anfang der Zeile.</span><span class="sxs-lookup"><span data-stu-id="c85c9-345">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="c85c9-346">VI-Befehlsmodus: `<I>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-346">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="c85c9-347">Viinsertatend</span><span class="sxs-lookup"><span data-stu-id="c85c9-347">ViInsertAtEnd</span></span>

<span data-ttu-id="c85c9-348">Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Ende der Zeile.</span><span class="sxs-lookup"><span data-stu-id="c85c9-348">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="c85c9-349">VI-Befehlsmodus: `<A>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-349">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="c85c9-350">Viinsertline</span><span class="sxs-lookup"><span data-stu-id="c85c9-350">ViInsertLine</span></span>

<span data-ttu-id="c85c9-351">Oberhalb der aktuellen Zeile wird eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-351">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="c85c9-352">VI-Befehlsmodus: `<O>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-352">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="c85c9-353">Viinsertwithappend</span><span class="sxs-lookup"><span data-stu-id="c85c9-353">ViInsertWithAppend</span></span>

<span data-ttu-id="c85c9-354">An der aktuellen Zeilen Position anfügen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-354">Append from the current line position.</span></span>

- <span data-ttu-id="c85c9-355">VI-Befehlsmodus: `<a>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-355">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="c85c9-356">Viinsertwithdelete</span><span class="sxs-lookup"><span data-stu-id="c85c9-356">ViInsertWithDelete</span></span>

<span data-ttu-id="c85c9-357">Löschen Sie das aktuelle Zeichen und wechseln Sie in den Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="c85c9-357">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="c85c9-358">VI-Befehlsmodus: `<s>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-358">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="c85c9-359">Vijoinlines</span><span class="sxs-lookup"><span data-stu-id="c85c9-359">ViJoinLines</span></span>

<span data-ttu-id="c85c9-360">Verbindet die aktuelle Zeile und die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="c85c9-360">Joins the current line and the next line.</span></span>

- <span data-ttu-id="c85c9-361">VI-Befehlsmodus: `<J>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-361">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="c85c9-362">Vireplaceline</span><span class="sxs-lookup"><span data-stu-id="c85c9-362">ViReplaceLine</span></span>

<span data-ttu-id="c85c9-363">Löschen Sie die gesamte Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="c85c9-363">Erase the entire command line.</span></span>

- <span data-ttu-id="c85c9-364">VI-Befehlsmodus: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-364">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="c85c9-365">Vireplacetobeforechar</span><span class="sxs-lookup"><span data-stu-id="c85c9-365">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="c85c9-366">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-366">Replaces until given character.</span></span>

- <span data-ttu-id="c85c9-367">VI-Befehlsmodus: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-367">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="c85c9-368">Vireplaceumbeforecharrückwärts</span><span class="sxs-lookup"><span data-stu-id="c85c9-368">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="c85c9-369">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-369">Replaces until given character.</span></span>

- <span data-ttu-id="c85c9-370">VI-Befehlsmodus: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-370">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="c85c9-371">Vireplaceumchar</span><span class="sxs-lookup"><span data-stu-id="c85c9-371">ViReplaceToChar</span></span>

<span data-ttu-id="c85c9-372">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-372">Deletes until given character.</span></span>

- <span data-ttu-id="c85c9-373">VI-Befehlsmodus: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-373">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="c85c9-374">Vireplacebackcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="c85c9-374">ViReplaceToCharBackward</span></span>

<span data-ttu-id="c85c9-375">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-375">Replaces until given character.</span></span>

- <span data-ttu-id="c85c9-376">VI-Befehlsmodus: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-376">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="c85c9-377">Viyankbeginningosline</span><span class="sxs-lookup"><span data-stu-id="c85c9-377">ViYankBeginningOfLine</span></span>

<span data-ttu-id="c85c9-378">Yank vom Anfang des Puffers bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-378">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="c85c9-379">VI-Befehlsmodus: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-379">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="c85c9-380">Viyankendobglob</span><span class="sxs-lookup"><span data-stu-id="c85c9-380">ViYankEndOfGlob</span></span>

<span data-ttu-id="c85c9-381">Yank vom Cursor bis zum Ende des Worts (s).</span><span class="sxs-lookup"><span data-stu-id="c85c9-381">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="c85c9-382">VI-Befehlsmodus: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-382">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="c85c9-383">Viyankendof</span><span class="sxs-lookup"><span data-stu-id="c85c9-383">ViYankEndOfWord</span></span>

<span data-ttu-id="c85c9-384">Yank vom Cursor bis zum Ende des Worts (s).</span><span class="sxs-lookup"><span data-stu-id="c85c9-384">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="c85c9-385">VI-Befehlsmodus: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-385">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="c85c9-386">Viyankleft</span><span class="sxs-lookup"><span data-stu-id="c85c9-386">ViYankLeft</span></span>

<span data-ttu-id="c85c9-387">Die Zeichen werden Links vom Cursor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-387">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="c85c9-388">VI-Befehlsmodus: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-388">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="c85c9-389">Viyankline</span><span class="sxs-lookup"><span data-stu-id="c85c9-389">ViYankLine</span></span>

<span data-ttu-id="c85c9-390">Den gesamten Puffer.</span><span class="sxs-lookup"><span data-stu-id="c85c9-390">Yank the entire buffer.</span></span>

- <span data-ttu-id="c85c9-391">VI-Befehlsmodus: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-391">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="c85c9-392">Viyanknextglob</span><span class="sxs-lookup"><span data-stu-id="c85c9-392">ViYankNextGlob</span></span>

<span data-ttu-id="c85c9-393">Yank vom Cursor bis zum Anfang des nächsten Worts (n).</span><span class="sxs-lookup"><span data-stu-id="c85c9-393">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="c85c9-394">VI-Befehlsmodus: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-394">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="c85c9-395">Viyanknextword</span><span class="sxs-lookup"><span data-stu-id="c85c9-395">ViYankNextWord</span></span>

<span data-ttu-id="c85c9-396">Das Wort (e) nach dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-396">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="c85c9-397">VI-Befehlsmodus: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-397">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="c85c9-398">Viyankprozent</span><span class="sxs-lookup"><span data-stu-id="c85c9-398">ViYankPercent</span></span>

<span data-ttu-id="c85c9-399">Von der entsprechenden geschweiften geschweifter Klammer.</span><span class="sxs-lookup"><span data-stu-id="c85c9-399">Yank to/from matching brace.</span></span>

- <span data-ttu-id="c85c9-400">VI-Befehlsmodus: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-400">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="c85c9-401">Viyankpreviousglob</span><span class="sxs-lookup"><span data-stu-id="c85c9-401">ViYankPreviousGlob</span></span>

<span data-ttu-id="c85c9-402">Yank von Anfang des Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-402">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="c85c9-403">VI-Befehlsmodus: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-403">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="c85c9-404">Viyankpreviousword</span><span class="sxs-lookup"><span data-stu-id="c85c9-404">ViYankPreviousWord</span></span>

<span data-ttu-id="c85c9-405">Das Wort (e) vor dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-405">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="c85c9-406">VI-Befehlsmodus: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-406">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="c85c9-407">Viyankright</span><span class="sxs-lookup"><span data-stu-id="c85c9-407">ViYankRight</span></span>

<span data-ttu-id="c85c9-408">(E) unter und rechts vom Cursor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-408">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="c85c9-409">VI-Befehlsmodus: `<y,l>` , `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-409">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="c85c9-410">Viyanktoendosline</span><span class="sxs-lookup"><span data-stu-id="c85c9-410">ViYankToEndOfLine</span></span>

<span data-ttu-id="c85c9-411">Yank vom Cursor bis zum Ende des Puffers.</span><span class="sxs-lookup"><span data-stu-id="c85c9-411">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="c85c9-412">VI-Befehlsmodus: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-412">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="c85c9-413">Viyanktofirstchar</span><span class="sxs-lookup"><span data-stu-id="c85c9-413">ViYankToFirstChar</span></span>

<span data-ttu-id="c85c9-414">Yank vom ersten Zeichen, das kein Leerzeichen ist, bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-414">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="c85c9-415">VI-Befehlsmodus: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-415">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="c85c9-416">Yank</span><span class="sxs-lookup"><span data-stu-id="c85c9-416">Yank</span></span>

<span data-ttu-id="c85c9-417">Fügen Sie der Eingabe den zuletzt beendeten Text hinzu.</span><span class="sxs-lookup"><span data-stu-id="c85c9-417">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="c85c9-418">Ansehen `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-418">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="c85c9-419">Yanklastarg</span><span class="sxs-lookup"><span data-stu-id="c85c9-419">YankLastArg</span></span>

<span data-ttu-id="c85c9-420">Das letzte Argument aus der vorherigen Verlaufs Zeile.</span><span class="sxs-lookup"><span data-stu-id="c85c9-420">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="c85c9-421">Mit einem Argument verhält sich das erste Mal, wenn es aufgerufen wird, wie yankntharg.</span><span class="sxs-lookup"><span data-stu-id="c85c9-421">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="c85c9-422">Wenn Sie mehrmals aufgerufen wird, durchläuft Sie stattdessen den Verlauf, und arg legt die Richtung fest (negative Umkehrung der Richtung).</span><span class="sxs-lookup"><span data-stu-id="c85c9-422">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="c85c9-423">Befehl: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-423">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="c85c9-424">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-424">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="c85c9-425">Yankntharg</span><span class="sxs-lookup"><span data-stu-id="c85c9-425">YankNthArg</span></span>

<span data-ttu-id="c85c9-426">Yank das erste Argument (nach dem Befehl) aus der vorherigen Verlaufs Zeile.</span><span class="sxs-lookup"><span data-stu-id="c85c9-426">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="c85c9-427">Bei einem Argument wird das n-te Argument (beginnend bei 0), wenn das Argument negativ ist, mit dem letzten Argument beginnen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-427">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="c85c9-428">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-428">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="c85c9-429">Yankpop</span><span class="sxs-lookup"><span data-stu-id="c85c9-429">YankPop</span></span>

<span data-ttu-id="c85c9-430">Wenn der vorherige Vorgang "Yank" oder "yankpop" war, ersetzen Sie den zuvor angezeigten Text durch den nächsten ausgeblendeten Text aus dem Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="c85c9-430">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="c85c9-431">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-431">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="c85c9-432">Cursor Verschiebungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="c85c9-432">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="c85c9-433">Backwardchar</span><span class="sxs-lookup"><span data-stu-id="c85c9-433">BackwardChar</span></span>

<span data-ttu-id="c85c9-434">Bewegen Sie den Cursor um ein Zeichen nach links.</span><span class="sxs-lookup"><span data-stu-id="c85c9-434">Move the cursor one character to the left.</span></span> <span data-ttu-id="c85c9-435">Dadurch kann der Cursor in die vorherige Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="c85c9-435">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="c85c9-436">Befehl: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-436">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="c85c9-437">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-437">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="c85c9-438">VI-Einfügemodus: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-438">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="c85c9-439">VI-Befehlsmodus: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-439">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="c85c9-440">Backwardword</span><span class="sxs-lookup"><span data-stu-id="c85c9-440">BackwardWord</span></span>

<span data-ttu-id="c85c9-441">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-441">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="c85c9-442">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="c85c9-442">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="c85c9-443">Befehl: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-443">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="c85c9-444">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-444">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="c85c9-445">VI-Einfügemodus: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-445">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="c85c9-446">VI-Befehlsmodus: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-446">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="c85c9-447">Beginningosline</span><span class="sxs-lookup"><span data-stu-id="c85c9-447">BeginningOfLine</span></span>

<span data-ttu-id="c85c9-448">Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Anfang der aktuellen Zeile oder, wenn Sie sich bereits am Anfang der Zeile befinden, bis zum Anfang der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="c85c9-448">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="c85c9-449">Wenn die Eingabe über eine einzelne Zeile verfügt, wechseln Sie zum Anfang der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="c85c9-449">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="c85c9-450">Befehl: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-450">Cmd: `<Home>`</span></span>
- <span data-ttu-id="c85c9-451">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-451">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="c85c9-452">VI-Einfügemodus: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-452">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="c85c9-453">VI-Befehlsmodus: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-453">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="c85c9-454">Endosline</span><span class="sxs-lookup"><span data-stu-id="c85c9-454">EndOfLine</span></span>

<span data-ttu-id="c85c9-455">Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Ende der aktuellen Zeile, oder wechseln Sie, wenn Sie sich bereits am Ende der Zeile befindet, bis zum Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="c85c9-455">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="c85c9-456">Wenn die Eingabe über eine einzelne Zeile verfügt, verschieben Sie das Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="c85c9-456">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="c85c9-457">Befehl: `<End>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-457">Cmd: `<End>`</span></span>
- <span data-ttu-id="c85c9-458">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-458">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="c85c9-459">VI-Einfügemodus: `<End>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-459">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="c85c9-460">Forwardchar</span><span class="sxs-lookup"><span data-stu-id="c85c9-460">ForwardChar</span></span>

<span data-ttu-id="c85c9-461">Bewegen Sie den Cursor um ein Zeichen nach rechts.</span><span class="sxs-lookup"><span data-stu-id="c85c9-461">Move the cursor one character to the right.</span></span> <span data-ttu-id="c85c9-462">Dadurch kann der Cursor in die nächste Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="c85c9-462">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="c85c9-463">Befehl: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-463">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="c85c9-464">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-464">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="c85c9-465">VI-Einfügemodus: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-465">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="c85c9-466">VI-Befehlsmodus: `<RightArrow>` , `<Space>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-466">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="c85c9-467">Forwardword</span><span class="sxs-lookup"><span data-stu-id="c85c9-467">ForwardWord</span></span>

<span data-ttu-id="c85c9-468">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="c85c9-468">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="c85c9-469">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="c85c9-469">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="c85c9-470">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-470">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="c85c9-471">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="c85c9-471">GotoBrace</span></span>

<span data-ttu-id="c85c9-472">Wechseln Sie zur passenden geschweiften Klammer, Klammer oder eckigen Klammer.</span><span class="sxs-lookup"><span data-stu-id="c85c9-472">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="c85c9-473">Befehl: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-473">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="c85c9-474">VI-Einfügemodus: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-474">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="c85c9-475">VI-Befehlsmodus: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-475">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="c85c9-476">Goum Column</span><span class="sxs-lookup"><span data-stu-id="c85c9-476">GotoColumn</span></span>

<span data-ttu-id="c85c9-477">Wechseln Sie in die Spalte, die von arg angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c85c9-477">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="c85c9-478">VI-Befehlsmodus: `<|>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-478">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="c85c9-479">Gostarfirstnonblankosline</span><span class="sxs-lookup"><span data-stu-id="c85c9-479">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="c85c9-480">Bewegen Sie den Cursor auf das erste nicht leere Zeichen in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="c85c9-480">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="c85c9-481">VI-Befehlsmodus: `<^>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-481">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="c85c9-482">"MUVE"</span><span class="sxs-lookup"><span data-stu-id="c85c9-482">MoveToEndOfLine</span></span>

<span data-ttu-id="c85c9-483">Bewegen Sie den Cursor an das Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="c85c9-483">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="c85c9-484">VI-Befehlsmodus: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-484">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="c85c9-485">Nextline</span><span class="sxs-lookup"><span data-stu-id="c85c9-485">NextLine</span></span>

<span data-ttu-id="c85c9-486">Bewegen Sie den Cursor in die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="c85c9-486">Move the cursor to the next line.</span></span>

- <span data-ttu-id="c85c9-487">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-487">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="c85c9-488">Nextword</span><span class="sxs-lookup"><span data-stu-id="c85c9-488">NextWord</span></span>

<span data-ttu-id="c85c9-489">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="c85c9-489">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="c85c9-490">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="c85c9-490">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="c85c9-491">Befehl: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-491">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="c85c9-492">VI-Einfügemodus: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-492">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="c85c9-493">VI-Befehlsmodus: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-493">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="c85c9-494">Nextwordend</span><span class="sxs-lookup"><span data-stu-id="c85c9-494">NextWordEnd</span></span>

<span data-ttu-id="c85c9-495">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="c85c9-495">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="c85c9-496">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="c85c9-496">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="c85c9-497">VI-Befehlsmodus: `<e>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-497">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="c85c9-498">Previousline</span><span class="sxs-lookup"><span data-stu-id="c85c9-498">PreviousLine</span></span>

<span data-ttu-id="c85c9-499">Bewegen Sie den Cursor in die vorherige Zeile.</span><span class="sxs-lookup"><span data-stu-id="c85c9-499">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="c85c9-500">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-500">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="c85c9-501">Shellbackwardword</span><span class="sxs-lookup"><span data-stu-id="c85c9-501">ShellBackwardWord</span></span>

<span data-ttu-id="c85c9-502">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-502">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="c85c9-503">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="c85c9-503">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="c85c9-504">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-504">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="c85c9-505">Shellforwardword</span><span class="sxs-lookup"><span data-stu-id="c85c9-505">ShellForwardWord</span></span>

<span data-ttu-id="c85c9-506">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="c85c9-506">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="c85c9-507">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="c85c9-507">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="c85c9-508">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-508">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="c85c9-509">Shellnextword</span><span class="sxs-lookup"><span data-stu-id="c85c9-509">ShellNextWord</span></span>

<span data-ttu-id="c85c9-510">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="c85c9-510">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="c85c9-511">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="c85c9-511">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="c85c9-512">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-512">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="c85c9-513">Vibackwardword</span><span class="sxs-lookup"><span data-stu-id="c85c9-513">ViBackwardWord</span></span>

<span data-ttu-id="c85c9-514">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-514">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="c85c9-515">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="c85c9-515">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="c85c9-516">VI-Befehlsmodus: `<b>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-516">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="c85c9-517">Viendobglob</span><span class="sxs-lookup"><span data-stu-id="c85c9-517">ViEndOfGlob</span></span>

<span data-ttu-id="c85c9-518">Verschiebt den Cursor an das Ende des Worts und verwendet nur Leerzeichen als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-518">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="c85c9-519">VI-Befehlsmodus: `<E>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-519">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="c85c9-520">Viendof previousglob</span><span class="sxs-lookup"><span data-stu-id="c85c9-520">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="c85c9-521">Wechselt zum Ende des vorherigen Worts, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c85c9-521">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="c85c9-522">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-522">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="c85c9-523">Vigoumbrace</span><span class="sxs-lookup"><span data-stu-id="c85c9-523">ViGotoBrace</span></span>

<span data-ttu-id="c85c9-524">Ähnelt gotobrace, aber ist Zeichen basiert anstelle von tokenbasiert.</span><span class="sxs-lookup"><span data-stu-id="c85c9-524">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="c85c9-525">VI-Befehlsmodus: `<%>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-525">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="c85c9-526">Vinextglob</span><span class="sxs-lookup"><span data-stu-id="c85c9-526">ViNextGlob</span></span>

<span data-ttu-id="c85c9-527">Wechselt zum nächsten Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c85c9-527">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="c85c9-528">VI-Befehlsmodus: `<W>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-528">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="c85c9-529">Vinextword</span><span class="sxs-lookup"><span data-stu-id="c85c9-529">ViNextWord</span></span>

<span data-ttu-id="c85c9-530">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="c85c9-530">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="c85c9-531">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="c85c9-531">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="c85c9-532">VI-Befehlsmodus: `<w>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-532">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="c85c9-533">Verlaufs Funktionen</span><span class="sxs-lookup"><span data-stu-id="c85c9-533">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="c85c9-534">Beginningof History</span><span class="sxs-lookup"><span data-stu-id="c85c9-534">BeginningOfHistory</span></span>

<span data-ttu-id="c85c9-535">Wechselt zum ersten Element im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="c85c9-535">Move to the first item in the history.</span></span>

- <span data-ttu-id="c85c9-536">Ansehen `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="c85c9-536">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="c85c9-537">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="c85c9-537">ClearHistory</span></span>

<span data-ttu-id="c85c9-538">Löscht den Verlauf in psleline.</span><span class="sxs-lookup"><span data-stu-id="c85c9-538">Clears history in PSReadLine.</span></span> <span data-ttu-id="c85c9-539">Dies wirkt sich nicht auf den PowerShell-Verlauf aus.</span><span class="sxs-lookup"><span data-stu-id="c85c9-539">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="c85c9-540">Befehl: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-540">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="c85c9-541">EndOf History</span><span class="sxs-lookup"><span data-stu-id="c85c9-541">EndOfHistory</span></span>

<span data-ttu-id="c85c9-542">Wechselt zum letzten Element (der aktuellen Eingabe) im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="c85c9-542">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="c85c9-543">Ansehen `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-543">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="c85c9-544">Forwardsearchhistory</span><span class="sxs-lookup"><span data-stu-id="c85c9-544">ForwardSearchHistory</span></span>

<span data-ttu-id="c85c9-545">Führt eine inkrementelle Forward-Suche im Verlauf durch</span><span class="sxs-lookup"><span data-stu-id="c85c9-545">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="c85c9-546">Befehl: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-546">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="c85c9-547">Ansehen `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-547">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="c85c9-548">Historysearchrückwärts</span><span class="sxs-lookup"><span data-stu-id="c85c9-548">HistorySearchBackward</span></span>

<span data-ttu-id="c85c9-549">Ersetzen Sie die aktuelle Eingabe durch das Element "Previous" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.</span><span class="sxs-lookup"><span data-stu-id="c85c9-549">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="c85c9-550">Befehl: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-550">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="c85c9-551">Historysearchforward</span><span class="sxs-lookup"><span data-stu-id="c85c9-551">HistorySearchForward</span></span>

<span data-ttu-id="c85c9-552">Ersetzen Sie die aktuelle Eingabe durch das Element "Next" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.</span><span class="sxs-lookup"><span data-stu-id="c85c9-552">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="c85c9-553">Befehl: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-553">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="c85c9-554">Nexthistory</span><span class="sxs-lookup"><span data-stu-id="c85c9-554">NextHistory</span></span>

<span data-ttu-id="c85c9-555">Ersetzen Sie die aktuelle Eingabe durch das "Next"-Element aus dem psleline-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="c85c9-555">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="c85c9-556">Befehl: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-556">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="c85c9-557">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-557">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="c85c9-558">VI-Einfügemodus: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-558">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="c85c9-559">VI-Befehlsmodus: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-559">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="c85c9-560">Previoushistory</span><span class="sxs-lookup"><span data-stu-id="c85c9-560">PreviousHistory</span></span>

<span data-ttu-id="c85c9-561">Ersetzen Sie die aktuelle Eingabe durch das "Previous"-Element aus dem psleline-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="c85c9-561">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="c85c9-562">Befehl: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-562">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="c85c9-563">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-563">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="c85c9-564">VI-Einfügemodus: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-564">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="c85c9-565">VI-Befehlsmodus: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="c85c9-565">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="c85c9-566">Reversesearchhistory</span><span class="sxs-lookup"><span data-stu-id="c85c9-566">ReverseSearchHistory</span></span>

<span data-ttu-id="c85c9-567">Führt eine inkrementelle Rückwärtssuche über den Verlauf durch</span><span class="sxs-lookup"><span data-stu-id="c85c9-567">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="c85c9-568">Befehl: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-568">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="c85c9-569">Ansehen `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-569">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="c85c9-570">Visearchhistoryrückwärts</span><span class="sxs-lookup"><span data-stu-id="c85c9-570">ViSearchHistoryBackward</span></span>

<span data-ttu-id="c85c9-571">Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.</span><span class="sxs-lookup"><span data-stu-id="c85c9-571">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="c85c9-572">VI-Einfügemodus: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-572">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="c85c9-573">VI-Befehlsmodus: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-573">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="c85c9-574">Vervollständigungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="c85c9-574">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="c85c9-575">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="c85c9-575">Complete</span></span>

<span data-ttu-id="c85c9-576">Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-576">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="c85c9-577">Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet.</span><span class="sxs-lookup"><span data-stu-id="c85c9-577">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="c85c9-578">Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-578">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="c85c9-579">Ansehen `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-579">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="c85c9-580">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="c85c9-580">MenuComplete</span></span>

<span data-ttu-id="c85c9-581">Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-581">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="c85c9-582">Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet.</span><span class="sxs-lookup"><span data-stu-id="c85c9-582">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="c85c9-583">Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-583">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="c85c9-584">Befehl: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-584">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="c85c9-585">Ansehen `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-585">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="c85c9-586">Possiblecompletions</span><span class="sxs-lookup"><span data-stu-id="c85c9-586">PossibleCompletions</span></span>

<span data-ttu-id="c85c9-587">Hiermit wird die Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-587">Display the list of possible completions.</span></span>

- <span data-ttu-id="c85c9-588">Ansehen `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-588">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="c85c9-589">VI-Einfügemodus: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-589">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="c85c9-590">VI-Befehlsmodus: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-590">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="c85c9-591">Tabcompletenext</span><span class="sxs-lookup"><span data-stu-id="c85c9-591">TabCompleteNext</span></span>

<span data-ttu-id="c85c9-592">Es wurde versucht, den Text, der den Cursor umgibt, mit der nächsten verfügbaren Beendigung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-592">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="c85c9-593">Befehl: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-593">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="c85c9-594">VI-Befehlsmodus: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-594">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="c85c9-595">Tabcompleteprevious</span><span class="sxs-lookup"><span data-stu-id="c85c9-595">TabCompletePrevious</span></span>

<span data-ttu-id="c85c9-596">Versuchen Sie, den Text, der den Cursor umgibt, mit dem vorherigen verfügbaren Abschluss abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-596">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="c85c9-597">Befehl: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-597">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="c85c9-598">VI-Befehlsmodus: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-598">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="c85c9-599">Vitabcompletenext</span><span class="sxs-lookup"><span data-stu-id="c85c9-599">ViTabCompleteNext</span></span>

<span data-ttu-id="c85c9-600">Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompletenext auf.</span><span class="sxs-lookup"><span data-stu-id="c85c9-600">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="c85c9-601">VI-Einfügemodus: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-601">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="c85c9-602">Vitabcompleteprevious</span><span class="sxs-lookup"><span data-stu-id="c85c9-602">ViTabCompletePrevious</span></span>

<span data-ttu-id="c85c9-603">Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompleteprevious auf.</span><span class="sxs-lookup"><span data-stu-id="c85c9-603">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="c85c9-604">VI-Einfügemodus: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-604">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="c85c9-605">Sonstige Funktionen</span><span class="sxs-lookup"><span data-stu-id="c85c9-605">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="c85c9-606">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="c85c9-606">CaptureScreen</span></span>

<span data-ttu-id="c85c9-607">Interaktive Bildschirmaufnahme starten-nach oben/nach-unten-Pfeile Select Lines, Enter kopiert markierten Text in die Zwischenablage als Text und HTML.</span><span class="sxs-lookup"><span data-stu-id="c85c9-607">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="c85c9-608">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-608">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="c85c9-609">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="c85c9-609">ClearScreen</span></span>

<span data-ttu-id="c85c9-610">Löschen Sie den Bildschirm, und zeichnen Sie die aktuelle Zeile am oberen Rand des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="c85c9-610">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="c85c9-611">Befehl: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-611">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="c85c9-612">Ansehen `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-612">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="c85c9-613">VI-Einfügemodus: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-613">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="c85c9-614">VI-Befehlsmodus: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-614">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="c85c9-615">Digitargument</span><span class="sxs-lookup"><span data-stu-id="c85c9-615">DigitArgument</span></span>

<span data-ttu-id="c85c9-616">Starten Sie ein neues Ziffern Argument, das an andere Funktionen übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="c85c9-616">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="c85c9-617">Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="c85c9-617">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="c85c9-618">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="c85c9-618">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="c85c9-619">VI-Befehlsmodus: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-619">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="c85c9-620">Invokeprompt</span><span class="sxs-lookup"><span data-stu-id="c85c9-620">InvokePrompt</span></span>

<span data-ttu-id="c85c9-621">Löscht die aktuelle Eingabeaufforderung und ruft die prompt-Funktion auf, um die Eingabeaufforderung erneut anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-621">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="c85c9-622">Nützlich für benutzerdefinierte Schlüssel Handler, die den Zustand ändern, z. b. Ändern des aktuellen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="c85c9-622">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="c85c9-623">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-623">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="c85c9-624">Scrolldisplaydown</span><span class="sxs-lookup"><span data-stu-id="c85c9-624">ScrollDisplayDown</span></span>

<span data-ttu-id="c85c9-625">Scrollen Sie in der Anzeige einen Bildschirm nach unten.</span><span class="sxs-lookup"><span data-stu-id="c85c9-625">Scroll the display down one screen.</span></span>

- <span data-ttu-id="c85c9-626">Befehl: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-626">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="c85c9-627">Ansehen `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-627">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="c85c9-628">Scrolldisplaydownline</span><span class="sxs-lookup"><span data-stu-id="c85c9-628">ScrollDisplayDownLine</span></span>

<span data-ttu-id="c85c9-629">Scrollen Sie in der Anzeige um eine Zeile nach unten.</span><span class="sxs-lookup"><span data-stu-id="c85c9-629">Scroll the display down one line.</span></span>

- <span data-ttu-id="c85c9-630">Befehl: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-630">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="c85c9-631">Ansehen `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-631">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="c85c9-632">Scrolldisplaytcursor</span><span class="sxs-lookup"><span data-stu-id="c85c9-632">ScrollDisplayToCursor</span></span>

<span data-ttu-id="c85c9-633">Scrollen Sie in der Anzeige zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-633">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="c85c9-634">Ansehen `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-634">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="c85c9-635">Scrolldisplaytop</span><span class="sxs-lookup"><span data-stu-id="c85c9-635">ScrollDisplayTop</span></span>

<span data-ttu-id="c85c9-636">Scrollen Sie in der Anzeige nach oben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-636">Scroll the display to the top.</span></span>

- <span data-ttu-id="c85c9-637">Ansehen `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-637">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="c85c9-638">Scrolldisplayup</span><span class="sxs-lookup"><span data-stu-id="c85c9-638">ScrollDisplayUp</span></span>

<span data-ttu-id="c85c9-639">Scrollen Sie einen Bildschirm nach oben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-639">Scroll the display up one screen.</span></span>

- <span data-ttu-id="c85c9-640">Befehl: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-640">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="c85c9-641">Ansehen `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-641">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="c85c9-642">Scrolldisplayupline</span><span class="sxs-lookup"><span data-stu-id="c85c9-642">ScrollDisplayUpLine</span></span>

<span data-ttu-id="c85c9-643">Scrollen Sie in der Anzeige um eine Zeile nach oben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-643">Scroll the display up one line.</span></span>

- <span data-ttu-id="c85c9-644">Befehl: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-644">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="c85c9-645">Ansehen `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-645">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="c85c9-646">Selfinsert</span><span class="sxs-lookup"><span data-stu-id="c85c9-646">SelfInsert</span></span>

<span data-ttu-id="c85c9-647">Fügen Sie den Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="c85c9-647">Insert the key.</span></span>

- <span data-ttu-id="c85c9-648">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-648">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="c85c9-649">Showkeybindungen</span><span class="sxs-lookup"><span data-stu-id="c85c9-649">ShowKeyBindings</span></span>

<span data-ttu-id="c85c9-650">Alle gebundenen Schlüssel anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-650">Show all bound keys.</span></span>

- <span data-ttu-id="c85c9-651">Befehl: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-651">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="c85c9-652">Ansehen `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-652">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="c85c9-653">VI-Einfügemodus: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-653">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="c85c9-654">Vicommandmode</span><span class="sxs-lookup"><span data-stu-id="c85c9-654">ViCommandMode</span></span>

<span data-ttu-id="c85c9-655">Wechseln Sie in den aktuellen Betriebsmodus von Vi-Insert zu VI-Command.</span><span class="sxs-lookup"><span data-stu-id="c85c9-655">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="c85c9-656">VI-Einfügemodus: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-656">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="c85c9-657">Vidigitargumentinchord</span><span class="sxs-lookup"><span data-stu-id="c85c9-657">ViDigitArgumentInChord</span></span>

<span data-ttu-id="c85c9-658">Startet ein neues Ziffern Argument, das in einem der VI-Akkorde an andere Funktionen übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="c85c9-658">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="c85c9-659">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-659">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="c85c9-660">Vieditvisuell</span><span class="sxs-lookup"><span data-stu-id="c85c9-660">ViEditVisually</span></span>

<span data-ttu-id="c85c9-661">Bearbeiten Sie die Befehlszeile in einem Text-Editor, der durch $ENV: Editor oder $env: Visual angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c85c9-661">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="c85c9-662">Ansehen `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-662">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="c85c9-663">VI-Befehlsmodus: `<v>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-663">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="c85c9-664">Viexit</span><span class="sxs-lookup"><span data-stu-id="c85c9-664">ViExit</span></span>

<span data-ttu-id="c85c9-665">Beendet die Shell.</span><span class="sxs-lookup"><span data-stu-id="c85c9-665">Exits the shell.</span></span>

- <span data-ttu-id="c85c9-666">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-666">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="c85c9-667">Viinsertmode</span><span class="sxs-lookup"><span data-stu-id="c85c9-667">ViInsertMode</span></span>

<span data-ttu-id="c85c9-668">Wechselt in den Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="c85c9-668">Switch to Insert mode.</span></span>

- <span data-ttu-id="c85c9-669">VI-Befehlsmodus: `<i>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-669">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="c85c9-670">Whatiskey</span><span class="sxs-lookup"><span data-stu-id="c85c9-670">WhatIsKey</span></span>

<span data-ttu-id="c85c9-671">Lesen Sie einen Schlüssel, und teilen Sie mir mit, wofür der Schlüssel gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="c85c9-671">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="c85c9-672">Befehl: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-672">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="c85c9-673">Ansehen `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-673">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="c85c9-674">Auswahl Funktionen</span><span class="sxs-lookup"><span data-stu-id="c85c9-674">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="c85c9-675">Exchangepointandmark</span><span class="sxs-lookup"><span data-stu-id="c85c9-675">ExchangePointAndMark</span></span>

<span data-ttu-id="c85c9-676">Der Cursor wird an der Position der Markierung platziert, und die Markierung wird an die Position des Cursors verschoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-676">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="c85c9-677">Ansehen `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-677">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="c85c9-678">SelectAll</span><span class="sxs-lookup"><span data-stu-id="c85c9-678">SelectAll</span></span>

<span data-ttu-id="c85c9-679">Wählen Sie die gesamte Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="c85c9-679">Select the entire line.</span></span>

- <span data-ttu-id="c85c9-680">Befehl: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-680">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="c85c9-681">Selectbackwardchar</span><span class="sxs-lookup"><span data-stu-id="c85c9-681">SelectBackwardChar</span></span>

<span data-ttu-id="c85c9-682">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Zeichen einschließt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-682">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="c85c9-683">Befehl: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-683">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="c85c9-684">Ansehen `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-684">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="c85c9-685">Selectbackwardsline</span><span class="sxs-lookup"><span data-stu-id="c85c9-685">SelectBackwardsLine</span></span>

<span data-ttu-id="c85c9-686">Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an den Anfang der Zeile eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="c85c9-686">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="c85c9-687">Befehl: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-687">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="c85c9-688">Ansehen `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-688">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="c85c9-689">Selectbackwardword</span><span class="sxs-lookup"><span data-stu-id="c85c9-689">SelectBackwardWord</span></span>

<span data-ttu-id="c85c9-690">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort enthält.</span><span class="sxs-lookup"><span data-stu-id="c85c9-690">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="c85c9-691">Befehl: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-691">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="c85c9-692">Ansehen `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-692">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="c85c9-693">Selectforwardchar</span><span class="sxs-lookup"><span data-stu-id="c85c9-693">SelectForwardChar</span></span>

<span data-ttu-id="c85c9-694">Passen Sie die aktuelle Auswahl an, um das nächste Zeichen einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-694">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="c85c9-695">Befehl: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-695">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="c85c9-696">Ansehen `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-696">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="c85c9-697">Selectforwardword</span><span class="sxs-lookup"><span data-stu-id="c85c9-697">SelectForwardWord</span></span>

<span data-ttu-id="c85c9-698">Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mit forwardword einschließt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-698">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="c85c9-699">Ansehen `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-699">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="c85c9-700">SelectLine</span><span class="sxs-lookup"><span data-stu-id="c85c9-700">SelectLine</span></span>

<span data-ttu-id="c85c9-701">Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an das Ende der Zeile eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="c85c9-701">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="c85c9-702">Befehl: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-702">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="c85c9-703">Ansehen `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-703">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="c85c9-704">Selectnextword</span><span class="sxs-lookup"><span data-stu-id="c85c9-704">SelectNextWord</span></span>

<span data-ttu-id="c85c9-705">Passen Sie die aktuelle Auswahl an das nächste Wort an.</span><span class="sxs-lookup"><span data-stu-id="c85c9-705">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="c85c9-706">Befehl: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-706">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="c85c9-707">Selectshellbackwardword</span><span class="sxs-lookup"><span data-stu-id="c85c9-707">SelectShellBackwardWord</span></span>

<span data-ttu-id="c85c9-708">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort mithilfe von shellbackwardword einschließt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-708">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="c85c9-709">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-709">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="c85c9-710">Selectshellforwardword</span><span class="sxs-lookup"><span data-stu-id="c85c9-710">SelectShellForwardWord</span></span>

<span data-ttu-id="c85c9-711">Passen Sie die aktuelle Auswahl so an, dass das nächste Wort mithilfe von shellforwardword eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="c85c9-711">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="c85c9-712">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-712">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="c85c9-713">Selectshellnextword</span><span class="sxs-lookup"><span data-stu-id="c85c9-713">SelectShellNextWord</span></span>

<span data-ttu-id="c85c9-714">Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mithilfe von shellnextword einschließt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-714">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="c85c9-715">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-715">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="c85c9-716">Setmark</span><span class="sxs-lookup"><span data-stu-id="c85c9-716">SetMark</span></span>

<span data-ttu-id="c85c9-717">Markieren Sie die aktuelle Position des Cursors für die Verwendung in einem nachfolgenden Bearbeitungs Befehl.</span><span class="sxs-lookup"><span data-stu-id="c85c9-717">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="c85c9-718">Ansehen `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="c85c9-718">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="c85c9-719">Suchfunktionen</span><span class="sxs-lookup"><span data-stu-id="c85c9-719">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="c85c9-720">Merkmal Suche</span><span class="sxs-lookup"><span data-stu-id="c85c9-720">CharacterSearch</span></span>

<span data-ttu-id="c85c9-721">Lesen Sie ein Zeichen, und suchen Sie nach dem nächsten Vorkommen dieses Zeichens.</span><span class="sxs-lookup"><span data-stu-id="c85c9-721">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="c85c9-722">Wenn ein Argument angegeben ist, suchen Sie nach vorn (oder rückwärts, wenn negativ) für das n-te vorkommen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-722">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="c85c9-723">Befehl: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-723">Cmd: `<F3>`</span></span>
- <span data-ttu-id="c85c9-724">Ansehen `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-724">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="c85c9-725">VI-Einfügemodus: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-725">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="c85c9-726">VI-Befehlsmodus: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-726">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="c85c9-727">Merkmal searchrückwärts</span><span class="sxs-lookup"><span data-stu-id="c85c9-727">CharacterSearchBackward</span></span>

<span data-ttu-id="c85c9-728">Liest ein Zeichen und sucht rückwärts nach dem nächsten Vorkommen dieses Zeichens.</span><span class="sxs-lookup"><span data-stu-id="c85c9-728">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="c85c9-729">Wenn ein Argument angegeben wird, suchen Sie nach hinten (oder vorwärts, wenn negativ).</span><span class="sxs-lookup"><span data-stu-id="c85c9-729">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="c85c9-730">Befehl: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-730">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="c85c9-731">Ansehen `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-731">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="c85c9-732">VI-Einfügemodus: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-732">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="c85c9-733">VI-Befehlsmodus: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-733">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="c85c9-734">Repeatlastcharsearch</span><span class="sxs-lookup"><span data-stu-id="c85c9-734">RepeatLastCharSearch</span></span>

<span data-ttu-id="c85c9-735">Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche.</span><span class="sxs-lookup"><span data-stu-id="c85c9-735">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="c85c9-736">VI-Befehlsmodus: `<;>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-736">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="c85c9-737">Repeatlastcharsearchabwärts</span><span class="sxs-lookup"><span data-stu-id="c85c9-737">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="c85c9-738">Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche, aber in umgekehrter Richtung.</span><span class="sxs-lookup"><span data-stu-id="c85c9-738">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="c85c9-739">VI-Befehlsmodus: `<,>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-739">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="c85c9-740">Repeatsearch</span><span class="sxs-lookup"><span data-stu-id="c85c9-740">RepeatSearch</span></span>

<span data-ttu-id="c85c9-741">Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-741">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="c85c9-742">VI-Befehlsmodus: `<n>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-742">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="c85c9-743">Repeatsearchrückwärts</span><span class="sxs-lookup"><span data-stu-id="c85c9-743">RepeatSearchBackward</span></span>

<span data-ttu-id="c85c9-744">Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="c85c9-744">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="c85c9-745">VI-Befehlsmodus: `<N>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-745">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="c85c9-746">Searchchar</span><span class="sxs-lookup"><span data-stu-id="c85c9-746">SearchChar</span></span>

<span data-ttu-id="c85c9-747">Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="c85c9-747">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="c85c9-748">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c85c9-748">This is for 't' functionality.</span></span>

- <span data-ttu-id="c85c9-749">VI-Befehlsmodus: `<f>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-749">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="c85c9-750">Searchcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="c85c9-750">SearchCharBackward</span></span>

<span data-ttu-id="c85c9-751">Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück.</span><span class="sxs-lookup"><span data-stu-id="c85c9-751">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="c85c9-752">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c85c9-752">This is for 'T' functionality.</span></span>

- <span data-ttu-id="c85c9-753">VI-Befehlsmodus: `<F>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-753">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="c85c9-754">Searchcharbackwardwithbackoff</span><span class="sxs-lookup"><span data-stu-id="c85c9-754">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="c85c9-755">Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück.</span><span class="sxs-lookup"><span data-stu-id="c85c9-755">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="c85c9-756">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c85c9-756">This is for 'T' functionality.</span></span>

- <span data-ttu-id="c85c9-757">VI-Befehlsmodus: `<T>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-757">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="c85c9-758">Searchcharwithbackoff</span><span class="sxs-lookup"><span data-stu-id="c85c9-758">SearchCharWithBackoff</span></span>

<span data-ttu-id="c85c9-759">Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="c85c9-759">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="c85c9-760">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c85c9-760">This is for 't' functionality.</span></span>

- <span data-ttu-id="c85c9-761">VI-Befehlsmodus: `<t>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-761">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="c85c9-762">SearchForward</span><span class="sxs-lookup"><span data-stu-id="c85c9-762">SearchForward</span></span>

<span data-ttu-id="c85c9-763">Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.</span><span class="sxs-lookup"><span data-stu-id="c85c9-763">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="c85c9-764">VI-Einfügemodus: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-764">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="c85c9-765">VI-Befehlsmodus: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="c85c9-765">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="c85c9-766">Benutzerdefinierte Tastenbindungen</span><span class="sxs-lookup"><span data-stu-id="c85c9-766">Custom Key Bindings</span></span>

<span data-ttu-id="c85c9-767">Psread Line unterstützt benutzerdefinierte Tastenbindungen mithilfe des Cmdlets `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="c85c9-767">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="c85c9-768">Die meisten benutzerdefinierten Tastenbindungen wenden eine der oben genannten Funktionen an, z. b.</span><span class="sxs-lookup"><span data-stu-id="c85c9-768">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="c85c9-769">Sie können einen ScriptBlock an einen Schlüssel binden.</span><span class="sxs-lookup"><span data-stu-id="c85c9-769">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="c85c9-770">Der ScriptBlock kann beliebig viele Aufgaben erledigen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-770">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="c85c9-771">Einige nützliche Beispiele sind u.a.</span><span class="sxs-lookup"><span data-stu-id="c85c9-771">Some useful examples include</span></span>

- <span data-ttu-id="c85c9-772">Bearbeiten der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="c85c9-772">edit the command line</span></span>
- <span data-ttu-id="c85c9-773">Öffnen eines neuen Fensters (z. b. "Hilfe")</span><span class="sxs-lookup"><span data-stu-id="c85c9-773">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="c85c9-774">Ändern der Verzeichnisse ohne Änderung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="c85c9-774">change directories without changing the command line</span></span>

<span data-ttu-id="c85c9-775">Der ScriptBlock empfängt zwei Argumente:</span><span class="sxs-lookup"><span data-stu-id="c85c9-775">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="c85c9-776">`$key` -Ein **[ConsoleKeyInfo]** -Objekt, das der Schlüssel ist, der die benutzerdefinierte Bindung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="c85c9-776">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="c85c9-777">Wenn Sie denselben ScriptBlock an mehrere Schlüssel binden und abhängig vom Schlüssel verschiedene Aktionen ausführen müssen, können Sie $Key überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-777">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="c85c9-778">Viele benutzerdefinierte Bindungen ignorieren dieses Argument.</span><span class="sxs-lookup"><span data-stu-id="c85c9-778">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="c85c9-779">`$arg` -Ein beliebiges Argument.</span><span class="sxs-lookup"><span data-stu-id="c85c9-779">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="c85c9-780">In den meisten Fällen ist dies ein ganzzahliges Argument, das der Benutzer von den Schlüsselbindungen digitargument übergibt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-780">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="c85c9-781">Wenn die Bindung keine Argumente akzeptiert, ist es sinnvoll, dieses Argument zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="c85c9-781">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="c85c9-782">Sehen wir uns ein Beispiel an, in dem eine Befehlszeile zum Verlauf hinzugefügt wird, ohne sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-782">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="c85c9-783">Dies ist nützlich, wenn Sie vergessen haben, etwas zu tun, ohne die Befehlszeile, die Sie bereits eingegeben haben, erneut eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-783">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="c85c9-784">In der Datei `SamplePSReadLineProfile.ps1` , die im psread Line-Modul Ordner installiert ist, werden viele weitere Beispiele angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-784">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="c85c9-785">Die meisten Tastenbindungen verwenden einige Hilfsfunktionen zum Bearbeiten der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="c85c9-785">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="c85c9-786">Diese APIs werden im nächsten Abschnitt dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="c85c9-786">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="c85c9-787">APIs für die benutzerdefinierte Schlüssel Bindungs Unterstützung</span><span class="sxs-lookup"><span data-stu-id="c85c9-787">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="c85c9-788">Die folgenden Funktionen sind in Microsoft. PowerShell. psconsolereadline öffentlich, können jedoch nicht direkt an einen Schlüssel gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="c85c9-788">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="c85c9-789">Die meisten sind in benutzerdefinierten Tastenkombinationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="c85c9-789">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="c85c9-790">Fügen Sie eine Befehlszeile zum Verlauf hinzu, ohne sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-790">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="c85c9-791">Löschen Sie den Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="c85c9-791">Clear the kill-ring.</span></span>  <span data-ttu-id="c85c9-792">Dies wird größtenteils zum Testen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c85c9-792">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="c85c9-793">Löschen Sie die Längen Zeichen aus dem Startmenü.</span><span class="sxs-lookup"><span data-stu-id="c85c9-793">Delete length characters from start.</span></span>  <span data-ttu-id="c85c9-794">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-794">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="c85c9-795">Führen Sie die Aktion "Ding" basierend auf der Benutzereinstellung aus.</span><span class="sxs-lookup"><span data-stu-id="c85c9-795">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="c85c9-796">Diese beiden Funktionen rufen nützliche Informationen über den aktuellen Status des Eingabe Puffers ab.</span><span class="sxs-lookup"><span data-stu-id="c85c9-796">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="c85c9-797">Der erste wird häufiger für einfache Fälle verwendet.</span><span class="sxs-lookup"><span data-stu-id="c85c9-797">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="c85c9-798">Die zweite wird verwendet, wenn ihre Bindung einen fortgeschrittenen Vorgang mit der AST bewirkt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-798">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="c85c9-799">Diese Funktion wird von Get-PSReadLineKeyHandler verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht nützlich.</span><span class="sxs-lookup"><span data-stu-id="c85c9-799">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="c85c9-800">Diese Funktion wird von Get-PSReadLineOption verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.</span><span class="sxs-lookup"><span data-stu-id="c85c9-800">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="c85c9-801">Wenn in der Befehlszeile keine Auswahl vorhanden ist, wird-1 sowohl in Start als auch in der Länge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-801">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="c85c9-802">Wenn eine Auswahl in der Befehlszeile vorhanden ist, werden Start und Länge der Auswahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-802">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="c85c9-803">Fügen Sie am Cursor ein Zeichen oder eine Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="c85c9-803">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="c85c9-804">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-804">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="c85c9-805">Dies ist der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="c85c9-805">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="c85c9-806">Sie unterstützt keine Rekursion und ist daher in einer benutzerdefinierten schlüsselbindung nicht nützlich.</span><span class="sxs-lookup"><span data-stu-id="c85c9-806">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="c85c9-807">Diese Funktion wird von Remove-PSReadLineKeyHandler verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.</span><span class="sxs-lookup"><span data-stu-id="c85c9-807">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="c85c9-808">Ersetzen Sie einige der Eingaben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-808">Replace some of the input.</span></span> <span data-ttu-id="c85c9-809">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-809">This operation supports undo/redo.</span></span> <span data-ttu-id="c85c9-810">Dies wird als "Delete", gefolgt von INSERT, bevorzugt, da es als einzelne Aktion für "Rückgängig" behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="c85c9-810">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="c85c9-811">Bewegen Sie den Cursor in den angegebenen Offset.</span><span class="sxs-lookup"><span data-stu-id="c85c9-811">Move the cursor to the given offset.</span></span> <span data-ttu-id="c85c9-812">Cursor Bewegung wird nicht für Rückgängigmachen nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="c85c9-812">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="c85c9-813">Bei dieser Funktion handelt es sich um eine Hilfsmethode, die vom Cmdlet Set-psread lineoption verwendet wird. Sie kann jedoch für eine benutzerdefinierte schlüsselbindung nützlich sein, die eine Einstellung vorübergehend ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="c85c9-813">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="c85c9-814">Diese Hilfsmethode wird für benutzerdefinierte Bindungen verwendet, die digitargument berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-814">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="c85c9-815">Ein typischer-Rückruf sieht wie folgt aus</span><span class="sxs-lookup"><span data-stu-id="c85c9-815">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="c85c9-816">HINWEIS</span><span class="sxs-lookup"><span data-stu-id="c85c9-816">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="c85c9-817">PowerShell-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="c85c9-817">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="c85c9-818">Für psread line sind PowerShell 3,0 oder höher sowie der Konsolen Host erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c85c9-818">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="c85c9-819">Es funktioniert nicht in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="c85c9-819">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="c85c9-820">Dies funktioniert in der-Konsole Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="c85c9-820">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="c85c9-821">Befehlsverlauf</span><span class="sxs-lookup"><span data-stu-id="c85c9-821">COMMAND HISTORY</span></span>

<span data-ttu-id="c85c9-822">Psleseline verwaltet eine Verlaufs Datei, die alle Befehle und Daten enthält, die Sie in der Befehlszeile eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="c85c9-822">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="c85c9-823">Dies kann vertrauliche Daten einschließlich Kenn Wörtern enthalten.</span><span class="sxs-lookup"><span data-stu-id="c85c9-823">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="c85c9-824">Wenn Sie z. b. das `ConvertTo-SecureString` Cmdlet verwenden, wird das Kennwort als nur-Text in der Verlaufs Datei protokolliert.</span><span class="sxs-lookup"><span data-stu-id="c85c9-824">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="c85c9-825">Die Verlaufs Dateien sind eine Datei mit dem Namen `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="c85c9-825">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="c85c9-826">Auf Windows-Systemen wird die Verlaufs Datei unter gespeichert `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="c85c9-826">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="c85c9-827">Auf nicht-Windows-Systemen werden die Verlaufs Dateien unter `$env:XDG_DATA_HOME/powershell/PSReadLine` oder gespeichert `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="c85c9-827">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="c85c9-828">Feedback & zu psread Line beitragen</span><span class="sxs-lookup"><span data-stu-id="c85c9-828">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="c85c9-829">Psread Line auf GitHub</span><span class="sxs-lookup"><span data-stu-id="c85c9-829">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="c85c9-830">Sie können auf der GitHub-Seite eine Pull Request einreichen oder Feedback einreichen.</span><span class="sxs-lookup"><span data-stu-id="c85c9-830">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="c85c9-831">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="c85c9-831">SEE ALSO</span></span>

<span data-ttu-id="c85c9-832">"Psread Line" wird stark von der GNU-Bibliothek für die [Zeilen](https://tiswww.case.edu/php/chet/readline/rltop.html) Übereinstimmung beeinflusst</span><span class="sxs-lookup"><span data-stu-id="c85c9-832">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
