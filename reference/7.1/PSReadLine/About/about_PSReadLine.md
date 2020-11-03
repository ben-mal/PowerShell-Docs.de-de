---
description: Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über psread Line
ms.openlocfilehash: 1188b8dc0b4099a7c1dcc472e3b02c2d4fa908bc
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220807"
---
# <a name="psreadline"></a><span data-ttu-id="58d12-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="58d12-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="58d12-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="58d12-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="58d12-106">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="58d12-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="58d12-107">Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="58d12-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="58d12-108">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="58d12-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="58d12-109">Psleline 2,0 bietet eine leistungsfähige Befehlszeilen Bearbeitungsfunktion für die PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="58d12-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="58d12-110">Sie bietet:</span><span class="sxs-lookup"><span data-stu-id="58d12-110">It provides:</span></span>

- <span data-ttu-id="58d12-111">Syntax Farbgebung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="58d12-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="58d12-112">Visuelle Hinweise auf Syntax Fehler</span><span class="sxs-lookup"><span data-stu-id="58d12-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="58d12-113">Bessere mehrzeilige Erfahrung (sowohl Bearbeitung als auch Verlauf)</span><span class="sxs-lookup"><span data-stu-id="58d12-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="58d12-114">Anpassbare Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="58d12-114">Customizable key bindings</span></span>
- <span data-ttu-id="58d12-115">Cmd-und Emacs-Modi</span><span class="sxs-lookup"><span data-stu-id="58d12-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="58d12-116">Viele Konfigurationsoptionen</span><span class="sxs-lookup"><span data-stu-id="58d12-116">Many configuration options</span></span>
- <span data-ttu-id="58d12-117">Bash-Stil Vervollständigung (optional im cmd-Modus, Standard im Emacs-Modus)</span><span class="sxs-lookup"><span data-stu-id="58d12-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="58d12-118">Emacs: Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="58d12-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="58d12-119">PowerShell-tokenbasierte "Wort Bewegung" und "Kill"</span><span class="sxs-lookup"><span data-stu-id="58d12-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="58d12-120">Die folgenden Funktionen sind in der-Klasse **[Microsoft. PowerShell. psconsolereadline]** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="58d12-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

> [!NOTE]
> <span data-ttu-id="58d12-121">Ab PowerShell 7,0 überspringt PowerShell das automatische Laden von psleseline unter Windows, wenn ein Bildschirm Leseprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="58d12-121">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="58d12-122">Derzeit funktioniert psread Line nicht gut mit den Bildschirmlesern.</span><span class="sxs-lookup"><span data-stu-id="58d12-122">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="58d12-123">Das Standard Rendering und die Formatierung von PowerShell 7,0 unter Windows funktionieren ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="58d12-123">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="58d12-124">Sie können das Modul ggf. manuell laden.</span><span class="sxs-lookup"><span data-stu-id="58d12-124">You can manually load the module if necessary.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="58d12-125">Grundlegende Bearbeitungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="58d12-125">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="58d12-126">Abbruch</span><span class="sxs-lookup"><span data-stu-id="58d12-126">Abort</span></span>

<span data-ttu-id="58d12-127">Abbrechen der aktuellen Aktion, z.b. inkrementelle Verlaufs Suche.</span><span class="sxs-lookup"><span data-stu-id="58d12-127">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="58d12-128">Ansehen `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="58d12-128">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="58d12-129">Akzeptandgetnext</span><span class="sxs-lookup"><span data-stu-id="58d12-129">AcceptAndGetNext</span></span>

<span data-ttu-id="58d12-130">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58d12-130">Attempt to execute the current input.</span></span> <span data-ttu-id="58d12-131">Wenn Sie ausgeführt werden kann (wie z. b. Accept Line), erinnern Sie sich beim nächsten Aufruf von "read line" an das nächste Element aus dem Verlauf.</span><span class="sxs-lookup"><span data-stu-id="58d12-131">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="58d12-132">Ansehen `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="58d12-132">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="58d12-133">Annahme</span><span class="sxs-lookup"><span data-stu-id="58d12-133">AcceptLine</span></span>

<span data-ttu-id="58d12-134">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58d12-134">Attempt to execute the current input.</span></span> <span data-ttu-id="58d12-135">Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="58d12-135">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="58d12-136">Befehl: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="58d12-136">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="58d12-137">Ansehen `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="58d12-137">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="58d12-138">VI-Einfügemodus: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="58d12-138">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="58d12-139">AddLine</span><span class="sxs-lookup"><span data-stu-id="58d12-139">AddLine</span></span>

<span data-ttu-id="58d12-140">Die Fortsetzungs Aufforderung wird in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="58d12-140">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="58d12-141">Dies ist nützlich, um mehrzeilige Eingaben als einen einzelnen Befehl einzugeben, auch wenn eine einzelne Zeile allein eine Eingabe ist.</span><span class="sxs-lookup"><span data-stu-id="58d12-141">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="58d12-142">Befehl: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="58d12-142">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="58d12-143">Ansehen `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="58d12-143">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="58d12-144">VI-Einfügemodus: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="58d12-144">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="58d12-145">VI-Befehlsmodus: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="58d12-145">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="58d12-146">Backwarddeletechar</span><span class="sxs-lookup"><span data-stu-id="58d12-146">BackwardDeleteChar</span></span>

<span data-ttu-id="58d12-147">Löschen Sie das Zeichen vor dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="58d12-147">Delete the character before the cursor.</span></span>

- <span data-ttu-id="58d12-148">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="58d12-148">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="58d12-149">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="58d12-149">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="58d12-150">VI-Einfügemodus: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="58d12-150">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="58d12-151">VI-Befehlsmodus: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="58d12-151">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="58d12-152">Backwarddelta-Eline</span><span class="sxs-lookup"><span data-stu-id="58d12-152">BackwardDeleteLine</span></span>

<span data-ttu-id="58d12-153">Wie backwardkillline löscht Text vom Punkt bis zum Anfang der Zeile, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="58d12-153">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="58d12-154">Befehl: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="58d12-154">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="58d12-155">VI-Einfügemodus: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="58d12-155">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="58d12-156">VI-Befehlsmodus: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="58d12-156">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="58d12-157">Backwarddeleteword</span><span class="sxs-lookup"><span data-stu-id="58d12-157">BackwardDeleteWord</span></span>

<span data-ttu-id="58d12-158">Löscht das vorherige Wort.</span><span class="sxs-lookup"><span data-stu-id="58d12-158">Deletes the previous word.</span></span>

- <span data-ttu-id="58d12-159">VI-Befehlsmodus: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="58d12-159">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="58d12-160">Backwardkillline</span><span class="sxs-lookup"><span data-stu-id="58d12-160">BackwardKillLine</span></span>

<span data-ttu-id="58d12-161">Löschen Sie die Eingabe vom Beginn der Eingabe in den Cursor.</span><span class="sxs-lookup"><span data-stu-id="58d12-161">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="58d12-162">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="58d12-162">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="58d12-163">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="58d12-163">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="58d12-164">Backwardkillword</span><span class="sxs-lookup"><span data-stu-id="58d12-164">BackwardKillWord</span></span>

<span data-ttu-id="58d12-165">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="58d12-165">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="58d12-166">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="58d12-166">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="58d12-167">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="58d12-167">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="58d12-168">Cmd: `<Ctrl+Backspace>` , `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="58d12-168">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="58d12-169">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="58d12-169">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="58d12-170">VI-Einfügemodus: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="58d12-170">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="58d12-171">VI-Befehlsmodus: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="58d12-171">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="58d12-172">Cancelline</span><span class="sxs-lookup"><span data-stu-id="58d12-172">CancelLine</span></span>

<span data-ttu-id="58d12-173">Brechen Sie die aktuelle Eingabe ab, belassen Sie die Eingabe auf dem Bildschirm, kehren Sie jedoch zurück zum Host, damit die Eingabeaufforderung erneut ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="58d12-173">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="58d12-174">VI-Einfügemodus: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="58d12-174">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="58d12-175">VI-Befehlsmodus: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="58d12-175">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="58d12-176">Kopieren</span><span class="sxs-lookup"><span data-stu-id="58d12-176">Copy</span></span>

<span data-ttu-id="58d12-177">Kopiert den ausgewählten Bereich in die Zwischenablage des Systems.</span><span class="sxs-lookup"><span data-stu-id="58d12-177">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="58d12-178">Wenn keine Region ausgewählt ist, kopieren Sie die gesamte Zeile.</span><span class="sxs-lookup"><span data-stu-id="58d12-178">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="58d12-179">Befehl: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="58d12-179">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="58d12-180">Copyorcancelline</span><span class="sxs-lookup"><span data-stu-id="58d12-180">CopyOrCancelLine</span></span>

<span data-ttu-id="58d12-181">Wenn Text ausgewählt ist, kopieren Sie ihn in die Zwischenablage, andernfalls brechen Sie die Zeile ab.</span><span class="sxs-lookup"><span data-stu-id="58d12-181">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="58d12-182">Befehl: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="58d12-182">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="58d12-183">Ansehen `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="58d12-183">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="58d12-184">Ausschneiden</span><span class="sxs-lookup"><span data-stu-id="58d12-184">Cut</span></span>

<span data-ttu-id="58d12-185">Löscht die ausgewählte Region, in der Gelöschter Text in der Zwischenablage des Systems</span><span class="sxs-lookup"><span data-stu-id="58d12-185">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="58d12-186">Befehl: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="58d12-186">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="58d12-187">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="58d12-187">DeleteChar</span></span>

<span data-ttu-id="58d12-188">Löschen Sie das Zeichen unter dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="58d12-188">Delete the character under the cursor.</span></span>

- <span data-ttu-id="58d12-189">Befehl: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="58d12-189">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="58d12-190">Ansehen `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="58d12-190">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="58d12-191">VI-Einfügemodus: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="58d12-191">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="58d12-192">VI-Befehlsmodus: `<Delete>` , `<x>` , `<d,l>` , `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="58d12-192">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="58d12-193">Deletecharorexit</span><span class="sxs-lookup"><span data-stu-id="58d12-193">DeleteCharOrExit</span></span>

<span data-ttu-id="58d12-194">Löschen Sie das Zeichen unter dem Cursor, oder beenden Sie den Prozess, wenn die Zeile leer ist.</span><span class="sxs-lookup"><span data-stu-id="58d12-194">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="58d12-195">Ansehen `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="58d12-195">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="58d12-196">Deleteendof Buffer</span><span class="sxs-lookup"><span data-stu-id="58d12-196">DeleteEndOfBuffer</span></span>

<span data-ttu-id="58d12-197">Löscht bis zum Ende des mehrzeiligen Puffers.</span><span class="sxs-lookup"><span data-stu-id="58d12-197">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="58d12-198">VI-Befehlsmodus: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="58d12-198">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="58d12-199">Deleteendof</span><span class="sxs-lookup"><span data-stu-id="58d12-199">DeleteEndOfWord</span></span>

<span data-ttu-id="58d12-200">Bis zum Ende des Worts löschen.</span><span class="sxs-lookup"><span data-stu-id="58d12-200">Delete to the end of the word.</span></span>

- <span data-ttu-id="58d12-201">VI-Befehlsmodus: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="58d12-201">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="58d12-202">"Deleteline</span><span class="sxs-lookup"><span data-stu-id="58d12-202">DeleteLine</span></span>

<span data-ttu-id="58d12-203">Löscht die aktuelle logische Zeile eines mehrzeiligen Puffers und ermöglicht Rückgängigmachen.</span><span class="sxs-lookup"><span data-stu-id="58d12-203">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="58d12-204">VI-Befehlsmodus: `<d,d>` , `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="58d12-204">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="58d12-205">Deletepreviouslines</span><span class="sxs-lookup"><span data-stu-id="58d12-205">DeletePreviousLines</span></span>

<span data-ttu-id="58d12-206">Löscht die vorherigen angeforderten logischen Zeilen und die aktuelle logische Zeile in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="58d12-206">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="58d12-207">VI-Befehlsmodus: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="58d12-207">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="58d12-208">Deleterelativelines</span><span class="sxs-lookup"><span data-stu-id="58d12-208">DeleteRelativeLines</span></span>

<span data-ttu-id="58d12-209">Löscht vom Anfang des Puffers in die aktuelle logische Zeile in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="58d12-209">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="58d12-210">Bei den meisten VI-Befehlen `<d,g,g>` kann dem Befehl ein numerisches Argument vorangestellt werden, das eine absolute Zeilennummer angibt, die in Verbindung mit der aktuellen Zeilennummer einen Bereich von Zeilen bilden, die gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="58d12-210">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="58d12-211">Wenn kein Wert angegeben wird, wird das numerische Argument standardmäßig auf 1 festgelegt. Dies bezieht sich auf die erste logische Zeile in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="58d12-211">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="58d12-212">Die tatsächliche Anzahl von Zeilen, die aus der mehrzeiligen Zeile gelöscht werden sollen, wird als Differenz zwischen der aktuellen logischen Zeilennummer und dem angegebenen numerischen Argument berechnet, das daher negativ sein kann.</span><span class="sxs-lookup"><span data-stu-id="58d12-212">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="58d12-213">Daher der _relative_ Teil des Methoden namens.</span><span class="sxs-lookup"><span data-stu-id="58d12-213">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="58d12-214">VI-Befehlsmodus: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="58d12-214">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="58d12-215">Deletenextlines</span><span class="sxs-lookup"><span data-stu-id="58d12-215">DeleteNextLines</span></span>

<span data-ttu-id="58d12-216">Löscht die aktuelle logische Linie und die nächsten angeforderten logischen Zeilen in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="58d12-216">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="58d12-217">VI-Befehlsmodus: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="58d12-217">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="58d12-218">Delta-inetyp</span><span class="sxs-lookup"><span data-stu-id="58d12-218">DeleteLineToFirstChar</span></span>

<span data-ttu-id="58d12-219">Löscht Text vom Cursor zum ersten Zeichen der Zeile, das nicht leer ist.</span><span class="sxs-lookup"><span data-stu-id="58d12-219">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="58d12-220">VI-Befehlsmodus: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="58d12-220">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="58d12-221">Deletegeend</span><span class="sxs-lookup"><span data-stu-id="58d12-221">DeleteToEnd</span></span>

<span data-ttu-id="58d12-222">Bis zum Ende der Zeile löschen.</span><span class="sxs-lookup"><span data-stu-id="58d12-222">Delete to the end of the line.</span></span>

- <span data-ttu-id="58d12-223">VI-Befehlsmodus: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="58d12-223">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="58d12-224">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="58d12-224">DeleteWord</span></span>

<span data-ttu-id="58d12-225">Löschen Sie das nächste Wort.</span><span class="sxs-lookup"><span data-stu-id="58d12-225">Delete the next word.</span></span>

- <span data-ttu-id="58d12-226">VI-Befehlsmodus: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="58d12-226">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="58d12-227">Forwarddelta-Eline</span><span class="sxs-lookup"><span data-stu-id="58d12-227">ForwardDeleteLine</span></span>

<span data-ttu-id="58d12-228">Wie forwardkillline löscht Text vom Punkt bis zum Ende der Zeile, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="58d12-228">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="58d12-229">Befehl: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="58d12-229">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="58d12-230">VI-Einfügemodus: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="58d12-230">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="58d12-231">VI-Befehlsmodus: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="58d12-231">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="58d12-232">Insertlineoberhalb</span><span class="sxs-lookup"><span data-stu-id="58d12-232">InsertLineAbove</span></span>

<span data-ttu-id="58d12-233">Oberhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="58d12-233">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="58d12-234">Der Cursor wechselt zum Anfang der neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="58d12-234">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="58d12-235">Befehl: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="58d12-235">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="58d12-236">Insertlinebelow</span><span class="sxs-lookup"><span data-stu-id="58d12-236">InsertLineBelow</span></span>

<span data-ttu-id="58d12-237">Unterhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="58d12-237">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="58d12-238">Der Cursor wechselt zum Anfang der neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="58d12-238">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="58d12-239">Befehl: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="58d12-239">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="58d12-240">Invertieren</span><span class="sxs-lookup"><span data-stu-id="58d12-240">InvertCase</span></span>

<span data-ttu-id="58d12-241">Kehrt die Groß-/Kleinschreibung des aktuellen Zeichens um und wechselt zum nächsten.</span><span class="sxs-lookup"><span data-stu-id="58d12-241">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="58d12-242">VI-Befehlsmodus: `<~>`</span><span class="sxs-lookup"><span data-stu-id="58d12-242">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="58d12-243">Killline</span><span class="sxs-lookup"><span data-stu-id="58d12-243">KillLine</span></span>

<span data-ttu-id="58d12-244">Löschen Sie die Eingabe vom Cursor bis zum Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="58d12-244">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="58d12-245">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="58d12-245">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="58d12-246">Ansehen `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="58d12-246">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="58d12-247">Killregion</span><span class="sxs-lookup"><span data-stu-id="58d12-247">KillRegion</span></span>

<span data-ttu-id="58d12-248">Beenden Sie den Text zwischen dem Cursor und der Markierung.</span><span class="sxs-lookup"><span data-stu-id="58d12-248">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="58d12-249">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-249">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="58d12-250">Killword</span><span class="sxs-lookup"><span data-stu-id="58d12-250">KillWord</span></span>

<span data-ttu-id="58d12-251">Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts.</span><span class="sxs-lookup"><span data-stu-id="58d12-251">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="58d12-252">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht.</span><span class="sxs-lookup"><span data-stu-id="58d12-252">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="58d12-253">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="58d12-253">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="58d12-254">Cmd: `<Alt+d>` , `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="58d12-254">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="58d12-255">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="58d12-255">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="58d12-256">VI-Einfügemodus: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="58d12-256">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="58d12-257">VI-Befehlsmodus: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="58d12-257">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="58d12-258">Einfügen</span><span class="sxs-lookup"><span data-stu-id="58d12-258">Paste</span></span>

<span data-ttu-id="58d12-259">Fügen Sie Text aus der Zwischenablage des Systems ein.</span><span class="sxs-lookup"><span data-stu-id="58d12-259">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="58d12-260">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="58d12-260">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="58d12-261">VI-Einfügemodus: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="58d12-261">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="58d12-262">VI-Befehlsmodus: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="58d12-262">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58d12-263">Wenn Sie die Funktion **Einfügen** verwenden, wird der gesamte Inhalt des Zwischenablage Puffers in den Eingabepuffer von psread Line eingefügt.</span><span class="sxs-lookup"><span data-stu-id="58d12-263">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="58d12-264">Der Eingabepuffer wird dann an den PowerShell-Parser übergeben.</span><span class="sxs-lookup"><span data-stu-id="58d12-264">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="58d12-265">Eingaben, die mithilfe der **Rechtsklick-Einfügemethode** der Konsolenanwendung eingefügt werden, werden jeweils ein Zeichen in den Eingabepuffer kopiert.</span><span class="sxs-lookup"><span data-stu-id="58d12-265">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="58d12-266">Der Eingabepuffer wird an den Parser übergeben, wenn ein Zeilen vorzeichensatz kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="58d12-266">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="58d12-267">Daher wird die Eingabe jeweils Zeilen gleich analysiert.</span><span class="sxs-lookup"><span data-stu-id="58d12-267">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="58d12-268">Der Unterschied zwischen den Methoden zum Einfügen führt zu einem anderen Ausführungs Verhalten.</span><span class="sxs-lookup"><span data-stu-id="58d12-268">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="58d12-269">Pasteafter</span><span class="sxs-lookup"><span data-stu-id="58d12-269">PasteAfter</span></span>

<span data-ttu-id="58d12-270">Fügen Sie die Zwischenablage nach dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.</span><span class="sxs-lookup"><span data-stu-id="58d12-270">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="58d12-271">VI-Befehlsmodus: `<p>`</span><span class="sxs-lookup"><span data-stu-id="58d12-271">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="58d12-272">Pastebefore</span><span class="sxs-lookup"><span data-stu-id="58d12-272">PasteBefore</span></span>

<span data-ttu-id="58d12-273">Fügen Sie die Zwischenablage vor dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.</span><span class="sxs-lookup"><span data-stu-id="58d12-273">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="58d12-274">VI-Befehlsmodus: `<P>`</span><span class="sxs-lookup"><span data-stu-id="58d12-274">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="58d12-275">Prepdandaccept</span><span class="sxs-lookup"><span data-stu-id="58d12-275">PrependAndAccept</span></span>

<span data-ttu-id="58d12-276">Fügen Sie ein "#" vorangesteht, und akzeptieren Sie die Zeile.</span><span class="sxs-lookup"><span data-stu-id="58d12-276">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="58d12-277">VI-Befehlsmodus: `<#>`</span><span class="sxs-lookup"><span data-stu-id="58d12-277">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="58d12-278">Wiederholen</span><span class="sxs-lookup"><span data-stu-id="58d12-278">Redo</span></span>

<span data-ttu-id="58d12-279">Rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="58d12-279">Undo an undo.</span></span>

- <span data-ttu-id="58d12-280">Befehl: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="58d12-280">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="58d12-281">VI-Einfügemodus: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="58d12-281">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="58d12-282">VI-Befehlsmodus: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="58d12-282">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="58d12-283">Repeatlastcommand</span><span class="sxs-lookup"><span data-stu-id="58d12-283">RepeatLastCommand</span></span>

<span data-ttu-id="58d12-284">Wiederholen Sie die letzte Textänderung.</span><span class="sxs-lookup"><span data-stu-id="58d12-284">Repeat the last text modification.</span></span>

- <span data-ttu-id="58d12-285">VI-Befehlsmodus: `<.>`</span><span class="sxs-lookup"><span data-stu-id="58d12-285">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="58d12-286">Revertline</span><span class="sxs-lookup"><span data-stu-id="58d12-286">RevertLine</span></span>

<span data-ttu-id="58d12-287">Kehrt alle Eingaben in die aktuelle Eingabe um.</span><span class="sxs-lookup"><span data-stu-id="58d12-287">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="58d12-288">Befehl: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="58d12-288">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="58d12-289">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="58d12-289">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="58d12-290">Shellbackwardkillword</span><span class="sxs-lookup"><span data-stu-id="58d12-290">ShellBackwardKillWord</span></span>

<span data-ttu-id="58d12-291">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="58d12-291">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="58d12-292">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="58d12-292">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="58d12-293">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="58d12-293">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="58d12-294">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-294">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="58d12-295">Shellkillword</span><span class="sxs-lookup"><span data-stu-id="58d12-295">ShellKillWord</span></span>

<span data-ttu-id="58d12-296">Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts.</span><span class="sxs-lookup"><span data-stu-id="58d12-296">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="58d12-297">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht.</span><span class="sxs-lookup"><span data-stu-id="58d12-297">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="58d12-298">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="58d12-298">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="58d12-299">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-299">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="58d12-300">Austausch Zeichen</span><span class="sxs-lookup"><span data-stu-id="58d12-300">SwapCharacters</span></span>

<span data-ttu-id="58d12-301">Tauschen Sie das aktuelle und das aktuelle Zeichen aus.</span><span class="sxs-lookup"><span data-stu-id="58d12-301">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="58d12-302">Ansehen `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="58d12-302">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="58d12-303">VI-Einfügemodus: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="58d12-303">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="58d12-304">VI-Befehlsmodus: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="58d12-304">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="58d12-305">Rückgängig</span><span class="sxs-lookup"><span data-stu-id="58d12-305">Undo</span></span>

<span data-ttu-id="58d12-306">Rückgängigmachen einer vorherigen Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="58d12-306">Undo a previous edit.</span></span>

- <span data-ttu-id="58d12-307">Befehl: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="58d12-307">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="58d12-308">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="58d12-308">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="58d12-309">VI-Einfügemodus: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="58d12-309">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="58d12-310">VI-Befehlsmodus: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="58d12-310">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="58d12-311">Nicht doall</span><span class="sxs-lookup"><span data-stu-id="58d12-311">UndoAll</span></span>

<span data-ttu-id="58d12-312">Alle vorherigen Änderungen für die Zeile rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="58d12-312">Undo all previous edits for line.</span></span>

- <span data-ttu-id="58d12-313">VI-Befehlsmodus: `<U>`</span><span class="sxs-lookup"><span data-stu-id="58d12-313">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="58d12-314">Unixwordrubout</span><span class="sxs-lookup"><span data-stu-id="58d12-314">UnixWordRubout</span></span>

<span data-ttu-id="58d12-315">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="58d12-315">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="58d12-316">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="58d12-316">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="58d12-317">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="58d12-317">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="58d12-318">Ansehen `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="58d12-318">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="58d12-319">Validateandakzeptline</span><span class="sxs-lookup"><span data-stu-id="58d12-319">ValidateAndAcceptLine</span></span>

<span data-ttu-id="58d12-320">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58d12-320">Attempt to execute the current input.</span></span> <span data-ttu-id="58d12-321">Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="58d12-321">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="58d12-322">Ansehen `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="58d12-322">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="58d12-323">Viakzeptline</span><span class="sxs-lookup"><span data-stu-id="58d12-323">ViAcceptLine</span></span>

<span data-ttu-id="58d12-324">Akzeptieren Sie die Zeile, und wechseln Sie zum Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="58d12-324">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="58d12-325">VI-Befehlsmodus: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="58d12-325">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="58d12-326">Viakzeptlineorexit</span><span class="sxs-lookup"><span data-stu-id="58d12-326">ViAcceptLineOrExit</span></span>

<span data-ttu-id="58d12-327">Wie deletecharorexit im Emacs-Modus, akzeptiert jedoch die Zeile, anstatt ein Zeichen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="58d12-327">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="58d12-328">VI-Einfügemodus: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="58d12-328">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="58d12-329">VI-Befehlsmodus: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="58d12-329">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="58d12-330">Viappendline</span><span class="sxs-lookup"><span data-stu-id="58d12-330">ViAppendLine</span></span>

<span data-ttu-id="58d12-331">Unterhalb der aktuellen Zeile wird eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="58d12-331">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="58d12-332">VI-Befehlsmodus: `<o>`</span><span class="sxs-lookup"><span data-stu-id="58d12-332">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="58d12-333">Vibackwarddeleteglob</span><span class="sxs-lookup"><span data-stu-id="58d12-333">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="58d12-334">Löscht das vorherige Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58d12-334">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="58d12-335">VI-Befehlsmodus: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="58d12-335">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="58d12-336">Vibackwardglob</span><span class="sxs-lookup"><span data-stu-id="58d12-336">ViBackwardGlob</span></span>

<span data-ttu-id="58d12-337">Verschiebt den Cursor zurück an den Anfang des vorherigen Worts, wobei nur Leerraum als Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58d12-337">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="58d12-338">VI-Befehlsmodus: `<B>`</span><span class="sxs-lookup"><span data-stu-id="58d12-338">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="58d12-339">Videletebrace</span><span class="sxs-lookup"><span data-stu-id="58d12-339">ViDeleteBrace</span></span>

<span data-ttu-id="58d12-340">Suchen Sie nach der passenden geschweiften Klammer, Klammer oder eckigen Klammer, und löschen Sie alle Inhalte in, einschließlich der geschweiften Klammer.</span><span class="sxs-lookup"><span data-stu-id="58d12-340">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="58d12-341">VI-Befehlsmodus: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="58d12-341">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="58d12-342">Videleteendobglob</span><span class="sxs-lookup"><span data-stu-id="58d12-342">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="58d12-343">Bis zum Ende des Worts löschen.</span><span class="sxs-lookup"><span data-stu-id="58d12-343">Delete to the end of the word.</span></span>

- <span data-ttu-id="58d12-344">VI-Befehlsmodus: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="58d12-344">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="58d12-345">Videleteglob</span><span class="sxs-lookup"><span data-stu-id="58d12-345">ViDeleteGlob</span></span>

<span data-ttu-id="58d12-346">Löschen Sie den nächsten globmuster (Leerzeichen mit Trennzeichen).</span><span class="sxs-lookup"><span data-stu-id="58d12-346">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="58d12-347">VI-Befehlsmodus: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="58d12-347">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="58d12-348">Videletetobeforechar</span><span class="sxs-lookup"><span data-stu-id="58d12-348">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="58d12-349">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="58d12-349">Deletes until given character.</span></span>

- <span data-ttu-id="58d12-350">VI-Befehlsmodus: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="58d12-350">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="58d12-351">Videletebackbeforecharrückwärts</span><span class="sxs-lookup"><span data-stu-id="58d12-351">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="58d12-352">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="58d12-352">Deletes until given character.</span></span>

- <span data-ttu-id="58d12-353">VI-Befehlsmodus: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="58d12-353">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="58d12-354">Videleteto Char</span><span class="sxs-lookup"><span data-stu-id="58d12-354">ViDeleteToChar</span></span>

<span data-ttu-id="58d12-355">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="58d12-355">Deletes until given character.</span></span>

- <span data-ttu-id="58d12-356">VI-Befehlsmodus: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="58d12-356">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="58d12-357">Videletebackcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="58d12-357">ViDeleteToCharBackward</span></span>

<span data-ttu-id="58d12-358">Löscht rückwärts bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="58d12-358">Deletes backwards until given character.</span></span>

- <span data-ttu-id="58d12-359">VI-Befehlsmodus: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="58d12-359">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="58d12-360">Viinsertatbeginung</span><span class="sxs-lookup"><span data-stu-id="58d12-360">ViInsertAtBegining</span></span>

<span data-ttu-id="58d12-361">Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Anfang der Zeile.</span><span class="sxs-lookup"><span data-stu-id="58d12-361">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="58d12-362">VI-Befehlsmodus: `<I>`</span><span class="sxs-lookup"><span data-stu-id="58d12-362">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="58d12-363">Viinsertatend</span><span class="sxs-lookup"><span data-stu-id="58d12-363">ViInsertAtEnd</span></span>

<span data-ttu-id="58d12-364">Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Ende der Zeile.</span><span class="sxs-lookup"><span data-stu-id="58d12-364">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="58d12-365">VI-Befehlsmodus: `<A>`</span><span class="sxs-lookup"><span data-stu-id="58d12-365">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="58d12-366">Viinsertline</span><span class="sxs-lookup"><span data-stu-id="58d12-366">ViInsertLine</span></span>

<span data-ttu-id="58d12-367">Oberhalb der aktuellen Zeile wird eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="58d12-367">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="58d12-368">VI-Befehlsmodus: `<O>`</span><span class="sxs-lookup"><span data-stu-id="58d12-368">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="58d12-369">Viinsertwithappend</span><span class="sxs-lookup"><span data-stu-id="58d12-369">ViInsertWithAppend</span></span>

<span data-ttu-id="58d12-370">An der aktuellen Zeilen Position anfügen.</span><span class="sxs-lookup"><span data-stu-id="58d12-370">Append from the current line position.</span></span>

- <span data-ttu-id="58d12-371">VI-Befehlsmodus: `<a>`</span><span class="sxs-lookup"><span data-stu-id="58d12-371">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="58d12-372">Viinsertwithdelete</span><span class="sxs-lookup"><span data-stu-id="58d12-372">ViInsertWithDelete</span></span>

<span data-ttu-id="58d12-373">Löschen Sie das aktuelle Zeichen und wechseln Sie in den Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="58d12-373">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="58d12-374">VI-Befehlsmodus: `<s>`</span><span class="sxs-lookup"><span data-stu-id="58d12-374">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="58d12-375">Vijoinlines</span><span class="sxs-lookup"><span data-stu-id="58d12-375">ViJoinLines</span></span>

<span data-ttu-id="58d12-376">Verbindet die aktuelle Zeile und die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="58d12-376">Joins the current line and the next line.</span></span>

- <span data-ttu-id="58d12-377">VI-Befehlsmodus: `<J>`</span><span class="sxs-lookup"><span data-stu-id="58d12-377">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="58d12-378">Vireplaceline</span><span class="sxs-lookup"><span data-stu-id="58d12-378">ViReplaceLine</span></span>

<span data-ttu-id="58d12-379">Löschen Sie die gesamte Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="58d12-379">Erase the entire command line.</span></span>

- <span data-ttu-id="58d12-380">VI-Befehlsmodus: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="58d12-380">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="58d12-381">Vireplacetobeforechar</span><span class="sxs-lookup"><span data-stu-id="58d12-381">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="58d12-382">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="58d12-382">Replaces until given character.</span></span>

- <span data-ttu-id="58d12-383">VI-Befehlsmodus: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="58d12-383">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="58d12-384">Vireplaceumbeforecharrückwärts</span><span class="sxs-lookup"><span data-stu-id="58d12-384">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="58d12-385">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="58d12-385">Replaces until given character.</span></span>

- <span data-ttu-id="58d12-386">VI-Befehlsmodus: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="58d12-386">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="58d12-387">Vireplaceumchar</span><span class="sxs-lookup"><span data-stu-id="58d12-387">ViReplaceToChar</span></span>

<span data-ttu-id="58d12-388">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="58d12-388">Deletes until given character.</span></span>

- <span data-ttu-id="58d12-389">VI-Befehlsmodus: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="58d12-389">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="58d12-390">Vireplacebackcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="58d12-390">ViReplaceToCharBackward</span></span>

<span data-ttu-id="58d12-391">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="58d12-391">Replaces until given character.</span></span>

- <span data-ttu-id="58d12-392">VI-Befehlsmodus: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="58d12-392">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="58d12-393">Viyankbeginningosline</span><span class="sxs-lookup"><span data-stu-id="58d12-393">ViYankBeginningOfLine</span></span>

<span data-ttu-id="58d12-394">Yank vom Anfang des Puffers bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="58d12-394">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="58d12-395">VI-Befehlsmodus: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="58d12-395">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="58d12-396">Viyankendobglob</span><span class="sxs-lookup"><span data-stu-id="58d12-396">ViYankEndOfGlob</span></span>

<span data-ttu-id="58d12-397">Yank vom Cursor bis zum Ende des Worts (s).</span><span class="sxs-lookup"><span data-stu-id="58d12-397">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="58d12-398">VI-Befehlsmodus: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="58d12-398">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="58d12-399">Viyankendof</span><span class="sxs-lookup"><span data-stu-id="58d12-399">ViYankEndOfWord</span></span>

<span data-ttu-id="58d12-400">Yank vom Cursor bis zum Ende des Worts (s).</span><span class="sxs-lookup"><span data-stu-id="58d12-400">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="58d12-401">VI-Befehlsmodus: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="58d12-401">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="58d12-402">Viyankleft</span><span class="sxs-lookup"><span data-stu-id="58d12-402">ViYankLeft</span></span>

<span data-ttu-id="58d12-403">Die Zeichen werden Links vom Cursor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58d12-403">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="58d12-404">VI-Befehlsmodus: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="58d12-404">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="58d12-405">Viyankline</span><span class="sxs-lookup"><span data-stu-id="58d12-405">ViYankLine</span></span>

<span data-ttu-id="58d12-406">Den gesamten Puffer.</span><span class="sxs-lookup"><span data-stu-id="58d12-406">Yank the entire buffer.</span></span>

- <span data-ttu-id="58d12-407">VI-Befehlsmodus: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="58d12-407">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="58d12-408">Viyanknextglob</span><span class="sxs-lookup"><span data-stu-id="58d12-408">ViYankNextGlob</span></span>

<span data-ttu-id="58d12-409">Yank vom Cursor bis zum Anfang des nächsten Worts (n).</span><span class="sxs-lookup"><span data-stu-id="58d12-409">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="58d12-410">VI-Befehlsmodus: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="58d12-410">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="58d12-411">Viyanknextword</span><span class="sxs-lookup"><span data-stu-id="58d12-411">ViYankNextWord</span></span>

<span data-ttu-id="58d12-412">Das Wort (e) nach dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="58d12-412">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="58d12-413">VI-Befehlsmodus: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="58d12-413">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="58d12-414">Viyankprozent</span><span class="sxs-lookup"><span data-stu-id="58d12-414">ViYankPercent</span></span>

<span data-ttu-id="58d12-415">Von der entsprechenden geschweiften geschweifter Klammer.</span><span class="sxs-lookup"><span data-stu-id="58d12-415">Yank to/from matching brace.</span></span>

- <span data-ttu-id="58d12-416">VI-Befehlsmodus: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="58d12-416">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="58d12-417">Viyankpreviousglob</span><span class="sxs-lookup"><span data-stu-id="58d12-417">ViYankPreviousGlob</span></span>

<span data-ttu-id="58d12-418">Yank von Anfang des Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="58d12-418">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="58d12-419">VI-Befehlsmodus: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="58d12-419">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="58d12-420">Viyankpreviousword</span><span class="sxs-lookup"><span data-stu-id="58d12-420">ViYankPreviousWord</span></span>

<span data-ttu-id="58d12-421">Das Wort (e) vor dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="58d12-421">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="58d12-422">VI-Befehlsmodus: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="58d12-422">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="58d12-423">Viyankright</span><span class="sxs-lookup"><span data-stu-id="58d12-423">ViYankRight</span></span>

<span data-ttu-id="58d12-424">(E) unter und rechts vom Cursor.</span><span class="sxs-lookup"><span data-stu-id="58d12-424">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="58d12-425">VI-Befehlsmodus: `<y,l>` , `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="58d12-425">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="58d12-426">Viyanktoendosline</span><span class="sxs-lookup"><span data-stu-id="58d12-426">ViYankToEndOfLine</span></span>

<span data-ttu-id="58d12-427">Yank vom Cursor bis zum Ende des Puffers.</span><span class="sxs-lookup"><span data-stu-id="58d12-427">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="58d12-428">VI-Befehlsmodus: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="58d12-428">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="58d12-429">Viyanktofirstchar</span><span class="sxs-lookup"><span data-stu-id="58d12-429">ViYankToFirstChar</span></span>

<span data-ttu-id="58d12-430">Yank vom ersten Zeichen, das kein Leerzeichen ist, bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="58d12-430">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="58d12-431">VI-Befehlsmodus: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="58d12-431">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="58d12-432">Yank</span><span class="sxs-lookup"><span data-stu-id="58d12-432">Yank</span></span>

<span data-ttu-id="58d12-433">Fügen Sie der Eingabe den zuletzt beendeten Text hinzu.</span><span class="sxs-lookup"><span data-stu-id="58d12-433">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="58d12-434">Ansehen `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="58d12-434">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="58d12-435">Yanklastarg</span><span class="sxs-lookup"><span data-stu-id="58d12-435">YankLastArg</span></span>

<span data-ttu-id="58d12-436">Das letzte Argument aus der vorherigen Verlaufs Zeile.</span><span class="sxs-lookup"><span data-stu-id="58d12-436">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="58d12-437">Mit einem Argument verhält sich das erste Mal, wenn es aufgerufen wird, wie yankntharg.</span><span class="sxs-lookup"><span data-stu-id="58d12-437">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="58d12-438">Wenn Sie mehrmals aufgerufen wird, durchläuft Sie stattdessen den Verlauf, und arg legt die Richtung fest (negative Umkehrung der Richtung).</span><span class="sxs-lookup"><span data-stu-id="58d12-438">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="58d12-439">Befehl: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="58d12-439">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="58d12-440">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="58d12-440">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="58d12-441">Yankntharg</span><span class="sxs-lookup"><span data-stu-id="58d12-441">YankNthArg</span></span>

<span data-ttu-id="58d12-442">Yank das erste Argument (nach dem Befehl) aus der vorherigen Verlaufs Zeile.</span><span class="sxs-lookup"><span data-stu-id="58d12-442">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="58d12-443">Bei einem Argument wird das n-te Argument (beginnend bei 0), wenn das Argument negativ ist, mit dem letzten Argument beginnen.</span><span class="sxs-lookup"><span data-stu-id="58d12-443">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="58d12-444">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="58d12-444">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="58d12-445">Yankpop</span><span class="sxs-lookup"><span data-stu-id="58d12-445">YankPop</span></span>

<span data-ttu-id="58d12-446">Wenn der vorherige Vorgang "Yank" oder "yankpop" war, ersetzen Sie den zuvor angezeigten Text durch den nächsten ausgeblendeten Text aus dem Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="58d12-446">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="58d12-447">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="58d12-447">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="58d12-448">Cursor Verschiebungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="58d12-448">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="58d12-449">Backwardchar</span><span class="sxs-lookup"><span data-stu-id="58d12-449">BackwardChar</span></span>

<span data-ttu-id="58d12-450">Bewegen Sie den Cursor um ein Zeichen nach links.</span><span class="sxs-lookup"><span data-stu-id="58d12-450">Move the cursor one character to the left.</span></span> <span data-ttu-id="58d12-451">Dadurch kann der Cursor in die vorherige Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="58d12-451">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="58d12-452">Befehl: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-452">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="58d12-453">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="58d12-453">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="58d12-454">Backwardword</span><span class="sxs-lookup"><span data-stu-id="58d12-454">BackwardWord</span></span>

<span data-ttu-id="58d12-455">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="58d12-455">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="58d12-456">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="58d12-456">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="58d12-457">Befehl: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-457">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="58d12-458">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="58d12-458">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="58d12-459">VI-Einfügemodus: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-459">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="58d12-460">VI-Befehlsmodus: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-460">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="58d12-461">Beginningosline</span><span class="sxs-lookup"><span data-stu-id="58d12-461">BeginningOfLine</span></span>

<span data-ttu-id="58d12-462">Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Anfang der aktuellen Zeile oder, wenn Sie sich bereits am Anfang der Zeile befinden, bis zum Anfang der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="58d12-462">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="58d12-463">Wenn die Eingabe über eine einzelne Zeile verfügt, wechseln Sie zum Anfang der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="58d12-463">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="58d12-464">Befehl: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="58d12-464">Cmd: `<Home>`</span></span>
- <span data-ttu-id="58d12-465">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="58d12-465">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="58d12-466">VI-Einfügemodus: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="58d12-466">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="58d12-467">VI-Befehlsmodus: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="58d12-467">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="58d12-468">Endosline</span><span class="sxs-lookup"><span data-stu-id="58d12-468">EndOfLine</span></span>

<span data-ttu-id="58d12-469">Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Ende der aktuellen Zeile, oder wechseln Sie, wenn Sie sich bereits am Ende der Zeile befindet, bis zum Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="58d12-469">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="58d12-470">Wenn die Eingabe über eine einzelne Zeile verfügt, verschieben Sie das Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="58d12-470">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="58d12-471">Befehl: `<End>`</span><span class="sxs-lookup"><span data-stu-id="58d12-471">Cmd: `<End>`</span></span>
- <span data-ttu-id="58d12-472">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="58d12-472">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="58d12-473">VI-Einfügemodus: `<End>`</span><span class="sxs-lookup"><span data-stu-id="58d12-473">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="58d12-474">Forwardchar</span><span class="sxs-lookup"><span data-stu-id="58d12-474">ForwardChar</span></span>

<span data-ttu-id="58d12-475">Bewegen Sie den Cursor um ein Zeichen nach rechts.</span><span class="sxs-lookup"><span data-stu-id="58d12-475">Move the cursor one character to the right.</span></span> <span data-ttu-id="58d12-476">Dadurch kann der Cursor in die nächste Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="58d12-476">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="58d12-477">Befehl: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-477">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="58d12-478">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="58d12-478">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="58d12-479">Forwardword</span><span class="sxs-lookup"><span data-stu-id="58d12-479">ForwardWord</span></span>

<span data-ttu-id="58d12-480">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="58d12-480">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="58d12-481">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="58d12-481">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="58d12-482">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="58d12-482">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="58d12-483">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="58d12-483">GotoBrace</span></span>

<span data-ttu-id="58d12-484">Wechseln Sie zur passenden geschweiften Klammer, Klammer oder eckigen Klammer.</span><span class="sxs-lookup"><span data-stu-id="58d12-484">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="58d12-485">Befehl: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="58d12-485">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="58d12-486">VI-Einfügemodus: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="58d12-486">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="58d12-487">VI-Befehlsmodus: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="58d12-487">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="58d12-488">Goum Column</span><span class="sxs-lookup"><span data-stu-id="58d12-488">GotoColumn</span></span>

<span data-ttu-id="58d12-489">Wechseln Sie in die Spalte, die von arg angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="58d12-489">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="58d12-490">VI-Befehlsmodus: `<|>`</span><span class="sxs-lookup"><span data-stu-id="58d12-490">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="58d12-491">Gostarfirstnonblankosline</span><span class="sxs-lookup"><span data-stu-id="58d12-491">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="58d12-492">Bewegen Sie den Cursor auf das erste nicht leere Zeichen in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="58d12-492">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="58d12-493">VI-Befehlsmodus: `<^>` , `<_>`</span><span class="sxs-lookup"><span data-stu-id="58d12-493">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="58d12-494">"MUVE"</span><span class="sxs-lookup"><span data-stu-id="58d12-494">MoveToEndOfLine</span></span>

<span data-ttu-id="58d12-495">Bewegen Sie den Cursor an das Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="58d12-495">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="58d12-496">VI-Befehlsmodus: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="58d12-496">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="58d12-497">Nextline</span><span class="sxs-lookup"><span data-stu-id="58d12-497">NextLine</span></span>

<span data-ttu-id="58d12-498">Bewegen Sie den Cursor in die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="58d12-498">Move the cursor to the next line.</span></span>

- <span data-ttu-id="58d12-499">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-499">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="58d12-500">Nextword</span><span class="sxs-lookup"><span data-stu-id="58d12-500">NextWord</span></span>

<span data-ttu-id="58d12-501">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="58d12-501">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="58d12-502">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="58d12-502">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="58d12-503">Befehl: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-503">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="58d12-504">VI-Einfügemodus: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-504">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="58d12-505">VI-Befehlsmodus: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-505">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="58d12-506">Nextwordend</span><span class="sxs-lookup"><span data-stu-id="58d12-506">NextWordEnd</span></span>

<span data-ttu-id="58d12-507">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="58d12-507">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="58d12-508">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="58d12-508">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="58d12-509">VI-Befehlsmodus: `<e>`</span><span class="sxs-lookup"><span data-stu-id="58d12-509">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="58d12-510">Previousline</span><span class="sxs-lookup"><span data-stu-id="58d12-510">PreviousLine</span></span>

<span data-ttu-id="58d12-511">Bewegen Sie den Cursor in die vorherige Zeile.</span><span class="sxs-lookup"><span data-stu-id="58d12-511">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="58d12-512">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-512">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="58d12-513">Shellbackwardword</span><span class="sxs-lookup"><span data-stu-id="58d12-513">ShellBackwardWord</span></span>

<span data-ttu-id="58d12-514">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="58d12-514">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="58d12-515">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="58d12-515">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="58d12-516">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-516">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="58d12-517">Shellforwardword</span><span class="sxs-lookup"><span data-stu-id="58d12-517">ShellForwardWord</span></span>

<span data-ttu-id="58d12-518">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="58d12-518">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="58d12-519">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="58d12-519">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="58d12-520">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-520">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="58d12-521">Shellnextword</span><span class="sxs-lookup"><span data-stu-id="58d12-521">ShellNextWord</span></span>

<span data-ttu-id="58d12-522">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="58d12-522">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="58d12-523">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="58d12-523">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="58d12-524">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-524">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="58d12-525">Vibackwardchar</span><span class="sxs-lookup"><span data-stu-id="58d12-525">ViBackwardChar</span></span>

<span data-ttu-id="58d12-526">Bewegen Sie den Cursor um ein Zeichen nach links im VI-Bearbeitungsmodus.</span><span class="sxs-lookup"><span data-stu-id="58d12-526">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="58d12-527">Dadurch kann der Cursor in die vorherige Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="58d12-527">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="58d12-528">VI-Einfügemodus: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-528">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="58d12-529">VI-Befehlsmodus: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="58d12-529">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="58d12-530">Vibackwardword</span><span class="sxs-lookup"><span data-stu-id="58d12-530">ViBackwardWord</span></span>

<span data-ttu-id="58d12-531">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="58d12-531">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="58d12-532">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="58d12-532">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="58d12-533">VI-Befehlsmodus: `<b>`</span><span class="sxs-lookup"><span data-stu-id="58d12-533">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="58d12-534">Viforwardchar</span><span class="sxs-lookup"><span data-stu-id="58d12-534">ViForwardChar</span></span>

<span data-ttu-id="58d12-535">Bewegen Sie den Cursor um ein Zeichen nach rechts im VI-Bearbeitungsmodus.</span><span class="sxs-lookup"><span data-stu-id="58d12-535">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="58d12-536">Dadurch kann der Cursor in die nächste Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="58d12-536">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="58d12-537">VI-Einfügemodus: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-537">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="58d12-538">VI-Befehlsmodus: `<RightArrow>` , `<Spacebar>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="58d12-538">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="58d12-539">Viendobglob</span><span class="sxs-lookup"><span data-stu-id="58d12-539">ViEndOfGlob</span></span>

<span data-ttu-id="58d12-540">Verschiebt den Cursor an das Ende des Worts und verwendet nur Leerzeichen als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="58d12-540">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="58d12-541">VI-Befehlsmodus: `<E>`</span><span class="sxs-lookup"><span data-stu-id="58d12-541">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="58d12-542">Viendof previousglob</span><span class="sxs-lookup"><span data-stu-id="58d12-542">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="58d12-543">Wechselt zum Ende des vorherigen Worts, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58d12-543">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="58d12-544">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-544">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="58d12-545">Vigoumbrace</span><span class="sxs-lookup"><span data-stu-id="58d12-545">ViGotoBrace</span></span>

<span data-ttu-id="58d12-546">Ähnelt gotobrace, aber ist Zeichen basiert anstelle von tokenbasiert.</span><span class="sxs-lookup"><span data-stu-id="58d12-546">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="58d12-547">VI-Befehlsmodus: `<%>`</span><span class="sxs-lookup"><span data-stu-id="58d12-547">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="58d12-548">Vinextglob</span><span class="sxs-lookup"><span data-stu-id="58d12-548">ViNextGlob</span></span>

<span data-ttu-id="58d12-549">Wechselt zum nächsten Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58d12-549">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="58d12-550">VI-Befehlsmodus: `<W>`</span><span class="sxs-lookup"><span data-stu-id="58d12-550">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="58d12-551">Vinextword</span><span class="sxs-lookup"><span data-stu-id="58d12-551">ViNextWord</span></span>

<span data-ttu-id="58d12-552">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="58d12-552">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="58d12-553">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="58d12-553">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="58d12-554">VI-Befehlsmodus: `<w>`</span><span class="sxs-lookup"><span data-stu-id="58d12-554">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="58d12-555">Verlaufs Funktionen</span><span class="sxs-lookup"><span data-stu-id="58d12-555">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="58d12-556">Beginningof History</span><span class="sxs-lookup"><span data-stu-id="58d12-556">BeginningOfHistory</span></span>

<span data-ttu-id="58d12-557">Wechselt zum ersten Element im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="58d12-557">Move to the first item in the history.</span></span>

- <span data-ttu-id="58d12-558">Ansehen `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="58d12-558">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="58d12-559">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="58d12-559">ClearHistory</span></span>

<span data-ttu-id="58d12-560">Löscht den Verlauf in psleline.</span><span class="sxs-lookup"><span data-stu-id="58d12-560">Clears history in PSReadLine.</span></span> <span data-ttu-id="58d12-561">Dies wirkt sich nicht auf den PowerShell-Verlauf aus.</span><span class="sxs-lookup"><span data-stu-id="58d12-561">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="58d12-562">Befehl: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="58d12-562">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="58d12-563">EndOf History</span><span class="sxs-lookup"><span data-stu-id="58d12-563">EndOfHistory</span></span>

<span data-ttu-id="58d12-564">Wechselt zum letzten Element (der aktuellen Eingabe) im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="58d12-564">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="58d12-565">Ansehen `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="58d12-565">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="58d12-566">Forwardsearchhistory</span><span class="sxs-lookup"><span data-stu-id="58d12-566">ForwardSearchHistory</span></span>

<span data-ttu-id="58d12-567">Führt eine inkrementelle Forward-Suche im Verlauf durch</span><span class="sxs-lookup"><span data-stu-id="58d12-567">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="58d12-568">Befehl: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="58d12-568">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="58d12-569">Ansehen `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="58d12-569">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="58d12-570">Historysearchrückwärts</span><span class="sxs-lookup"><span data-stu-id="58d12-570">HistorySearchBackward</span></span>

<span data-ttu-id="58d12-571">Ersetzen Sie die aktuelle Eingabe durch das Element "Previous" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.</span><span class="sxs-lookup"><span data-stu-id="58d12-571">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="58d12-572">Befehl: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="58d12-572">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="58d12-573">Historysearchforward</span><span class="sxs-lookup"><span data-stu-id="58d12-573">HistorySearchForward</span></span>

<span data-ttu-id="58d12-574">Ersetzen Sie die aktuelle Eingabe durch das Element "Next" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.</span><span class="sxs-lookup"><span data-stu-id="58d12-574">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="58d12-575">Befehl: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="58d12-575">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="58d12-576">Nexthistory</span><span class="sxs-lookup"><span data-stu-id="58d12-576">NextHistory</span></span>

<span data-ttu-id="58d12-577">Ersetzen Sie die aktuelle Eingabe durch das "Next"-Element aus dem psleline-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="58d12-577">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="58d12-578">Befehl: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-578">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="58d12-579">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="58d12-579">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="58d12-580">VI-Einfügemodus: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-580">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="58d12-581">VI-Befehlsmodus: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="58d12-581">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="58d12-582">Previoushistory</span><span class="sxs-lookup"><span data-stu-id="58d12-582">PreviousHistory</span></span>

<span data-ttu-id="58d12-583">Ersetzen Sie die aktuelle Eingabe durch das "Previous"-Element aus dem psleline-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="58d12-583">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="58d12-584">Befehl: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-584">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="58d12-585">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="58d12-585">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="58d12-586">VI-Einfügemodus: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-586">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="58d12-587">VI-Befehlsmodus: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="58d12-587">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="58d12-588">Reversesearchhistory</span><span class="sxs-lookup"><span data-stu-id="58d12-588">ReverseSearchHistory</span></span>

<span data-ttu-id="58d12-589">Führt eine inkrementelle Rückwärtssuche über den Verlauf durch</span><span class="sxs-lookup"><span data-stu-id="58d12-589">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="58d12-590">Befehl: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="58d12-590">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="58d12-591">Ansehen `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="58d12-591">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="58d12-592">Visearchhistoryrückwärts</span><span class="sxs-lookup"><span data-stu-id="58d12-592">ViSearchHistoryBackward</span></span>

<span data-ttu-id="58d12-593">Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.</span><span class="sxs-lookup"><span data-stu-id="58d12-593">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="58d12-594">VI-Einfügemodus: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="58d12-594">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="58d12-595">VI-Befehlsmodus: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="58d12-595">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="58d12-596">Vervollständigungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="58d12-596">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="58d12-597">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="58d12-597">Complete</span></span>

<span data-ttu-id="58d12-598">Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="58d12-598">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="58d12-599">Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet.</span><span class="sxs-lookup"><span data-stu-id="58d12-599">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="58d12-600">Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58d12-600">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="58d12-601">Ansehen `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="58d12-601">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="58d12-602">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="58d12-602">MenuComplete</span></span>

<span data-ttu-id="58d12-603">Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="58d12-603">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="58d12-604">Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet.</span><span class="sxs-lookup"><span data-stu-id="58d12-604">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="58d12-605">Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58d12-605">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="58d12-606">Cmd: `<Ctrl+@>` , `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="58d12-606">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="58d12-607">Ansehen `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="58d12-607">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="58d12-608">Possiblecompletions</span><span class="sxs-lookup"><span data-stu-id="58d12-608">PossibleCompletions</span></span>

<span data-ttu-id="58d12-609">Hiermit wird die Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58d12-609">Display the list of possible completions.</span></span>

- <span data-ttu-id="58d12-610">Ansehen `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="58d12-610">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="58d12-611">VI-Einfügemodus: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="58d12-611">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="58d12-612">VI-Befehlsmodus: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="58d12-612">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="58d12-613">Tabcompletenext</span><span class="sxs-lookup"><span data-stu-id="58d12-613">TabCompleteNext</span></span>

<span data-ttu-id="58d12-614">Es wurde versucht, den Text, der den Cursor umgibt, mit der nächsten verfügbaren Beendigung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="58d12-614">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="58d12-615">Befehl: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="58d12-615">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="58d12-616">VI-Befehlsmodus: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="58d12-616">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="58d12-617">Tabcompleteprevious</span><span class="sxs-lookup"><span data-stu-id="58d12-617">TabCompletePrevious</span></span>

<span data-ttu-id="58d12-618">Versuchen Sie, den Text, der den Cursor umgibt, mit dem vorherigen verfügbaren Abschluss abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="58d12-618">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="58d12-619">Befehl: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="58d12-619">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="58d12-620">VI-Befehlsmodus: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="58d12-620">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="58d12-621">Vitabcompletenext</span><span class="sxs-lookup"><span data-stu-id="58d12-621">ViTabCompleteNext</span></span>

<span data-ttu-id="58d12-622">Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompletenext auf.</span><span class="sxs-lookup"><span data-stu-id="58d12-622">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="58d12-623">VI-Einfügemodus: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="58d12-623">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="58d12-624">Vitabcompleteprevious</span><span class="sxs-lookup"><span data-stu-id="58d12-624">ViTabCompletePrevious</span></span>

<span data-ttu-id="58d12-625">Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompleteprevious auf.</span><span class="sxs-lookup"><span data-stu-id="58d12-625">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="58d12-626">VI-Einfügemodus: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="58d12-626">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="58d12-627">Sonstige Funktionen</span><span class="sxs-lookup"><span data-stu-id="58d12-627">Miscellaneous functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="58d12-628">Akzeptnextsuggestionword</span><span class="sxs-lookup"><span data-stu-id="58d12-628">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="58d12-629">Akzeptieren Sie das nächste Wort des Inline-oder ausgewählten Vorschlags.</span><span class="sxs-lookup"><span data-stu-id="58d12-629">Accept the next word of the inline or selected suggestion.</span></span>

- <span data-ttu-id="58d12-630">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-630">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="58d12-631">Accept-Vorschlag</span><span class="sxs-lookup"><span data-stu-id="58d12-631">AcceptSuggestion</span></span>

<span data-ttu-id="58d12-632">Akzeptieren Sie den aktuellen Inline-oder ausgewählten Vorschlag.</span><span class="sxs-lookup"><span data-stu-id="58d12-632">Accept the current inline or selected suggestion.</span></span>

- <span data-ttu-id="58d12-633">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-633">Function is unbound.</span></span>

### <a name="capturescreen"></a><span data-ttu-id="58d12-634">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="58d12-634">CaptureScreen</span></span>

<span data-ttu-id="58d12-635">Interaktive Bildschirmaufnahme starten-nach oben/nach-unten-Pfeile Select Lines, Enter kopiert markierten Text in die Zwischenablage als Text und HTML.</span><span class="sxs-lookup"><span data-stu-id="58d12-635">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="58d12-636">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-636">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="58d12-637">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="58d12-637">ClearScreen</span></span>

<span data-ttu-id="58d12-638">Löschen Sie den Bildschirm, und zeichnen Sie die aktuelle Zeile am oberen Rand des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="58d12-638">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="58d12-639">Befehl: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="58d12-639">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="58d12-640">Ansehen `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="58d12-640">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="58d12-641">VI-Einfügemodus: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="58d12-641">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="58d12-642">VI-Befehlsmodus: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="58d12-642">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="58d12-643">Digitargument</span><span class="sxs-lookup"><span data-stu-id="58d12-643">DigitArgument</span></span>

<span data-ttu-id="58d12-644">Starten Sie ein neues Ziffern Argument, das an andere Funktionen übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="58d12-644">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="58d12-645">Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="58d12-645">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="58d12-646">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="58d12-646">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="58d12-647">VI-Befehlsmodus: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="58d12-647">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="58d12-648">Invokeprompt</span><span class="sxs-lookup"><span data-stu-id="58d12-648">InvokePrompt</span></span>

<span data-ttu-id="58d12-649">Löscht die aktuelle Eingabeaufforderung und ruft die prompt-Funktion auf, um die Eingabeaufforderung erneut anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="58d12-649">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="58d12-650">Nützlich für benutzerdefinierte Schlüssel Handler, die den Zustand ändern, z. b. Ändern des aktuellen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="58d12-650">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="58d12-651">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-651">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="58d12-652">Scrolldisplaydown</span><span class="sxs-lookup"><span data-stu-id="58d12-652">ScrollDisplayDown</span></span>

<span data-ttu-id="58d12-653">Scrollen Sie in der Anzeige einen Bildschirm nach unten.</span><span class="sxs-lookup"><span data-stu-id="58d12-653">Scroll the display down one screen.</span></span>

- <span data-ttu-id="58d12-654">Befehl: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="58d12-654">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="58d12-655">Ansehen `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="58d12-655">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="58d12-656">Scrolldisplaydownline</span><span class="sxs-lookup"><span data-stu-id="58d12-656">ScrollDisplayDownLine</span></span>

<span data-ttu-id="58d12-657">Scrollen Sie in der Anzeige um eine Zeile nach unten.</span><span class="sxs-lookup"><span data-stu-id="58d12-657">Scroll the display down one line.</span></span>

- <span data-ttu-id="58d12-658">Befehl: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="58d12-658">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="58d12-659">Ansehen `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="58d12-659">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="58d12-660">Scrolldisplaytcursor</span><span class="sxs-lookup"><span data-stu-id="58d12-660">ScrollDisplayToCursor</span></span>

<span data-ttu-id="58d12-661">Scrollen Sie in der Anzeige zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="58d12-661">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="58d12-662">Ansehen `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="58d12-662">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="58d12-663">Scrolldisplaytop</span><span class="sxs-lookup"><span data-stu-id="58d12-663">ScrollDisplayTop</span></span>

<span data-ttu-id="58d12-664">Scrollen Sie in der Anzeige nach oben.</span><span class="sxs-lookup"><span data-stu-id="58d12-664">Scroll the display to the top.</span></span>

- <span data-ttu-id="58d12-665">Ansehen `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="58d12-665">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="58d12-666">Scrolldisplayup</span><span class="sxs-lookup"><span data-stu-id="58d12-666">ScrollDisplayUp</span></span>

<span data-ttu-id="58d12-667">Scrollen Sie einen Bildschirm nach oben.</span><span class="sxs-lookup"><span data-stu-id="58d12-667">Scroll the display up one screen.</span></span>

- <span data-ttu-id="58d12-668">Befehl: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="58d12-668">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="58d12-669">Ansehen `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="58d12-669">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="58d12-670">Scrolldisplayupline</span><span class="sxs-lookup"><span data-stu-id="58d12-670">ScrollDisplayUpLine</span></span>

<span data-ttu-id="58d12-671">Scrollen Sie in der Anzeige um eine Zeile nach oben.</span><span class="sxs-lookup"><span data-stu-id="58d12-671">Scroll the display up one line.</span></span>

- <span data-ttu-id="58d12-672">Befehl: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="58d12-672">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="58d12-673">Ansehen `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="58d12-673">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="58d12-674">Selfinsert</span><span class="sxs-lookup"><span data-stu-id="58d12-674">SelfInsert</span></span>

<span data-ttu-id="58d12-675">Fügen Sie den Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="58d12-675">Insert the key.</span></span>

- <span data-ttu-id="58d12-676">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-676">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="58d12-677">Showkeybindungen</span><span class="sxs-lookup"><span data-stu-id="58d12-677">ShowKeyBindings</span></span>

<span data-ttu-id="58d12-678">Alle gebundenen Schlüssel anzeigen.</span><span class="sxs-lookup"><span data-stu-id="58d12-678">Show all bound keys.</span></span>

- <span data-ttu-id="58d12-679">Befehl: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="58d12-679">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="58d12-680">Ansehen `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="58d12-680">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="58d12-681">VI-Einfügemodus: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="58d12-681">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="58d12-682">Vicommandmode</span><span class="sxs-lookup"><span data-stu-id="58d12-682">ViCommandMode</span></span>

<span data-ttu-id="58d12-683">Wechseln Sie in den aktuellen Betriebsmodus von Vi-Insert zu VI-Command.</span><span class="sxs-lookup"><span data-stu-id="58d12-683">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="58d12-684">VI-Einfügemodus: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="58d12-684">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="58d12-685">Vidigitargumentinchord</span><span class="sxs-lookup"><span data-stu-id="58d12-685">ViDigitArgumentInChord</span></span>

<span data-ttu-id="58d12-686">Startet ein neues Ziffern Argument, das in einem der VI-Akkorde an andere Funktionen übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="58d12-686">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="58d12-687">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-687">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="58d12-688">Vieditvisuell</span><span class="sxs-lookup"><span data-stu-id="58d12-688">ViEditVisually</span></span>

<span data-ttu-id="58d12-689">Bearbeiten Sie die Befehlszeile in einem Text-Editor, der durch $ENV: Editor oder $env: Visual angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="58d12-689">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="58d12-690">Ansehen `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="58d12-690">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="58d12-691">VI-Befehlsmodus: `<v>`</span><span class="sxs-lookup"><span data-stu-id="58d12-691">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="58d12-692">Viexit</span><span class="sxs-lookup"><span data-stu-id="58d12-692">ViExit</span></span>

<span data-ttu-id="58d12-693">Beendet die Shell.</span><span class="sxs-lookup"><span data-stu-id="58d12-693">Exits the shell.</span></span>

- <span data-ttu-id="58d12-694">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-694">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="58d12-695">Viinsertmode</span><span class="sxs-lookup"><span data-stu-id="58d12-695">ViInsertMode</span></span>

<span data-ttu-id="58d12-696">Wechselt in den Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="58d12-696">Switch to Insert mode.</span></span>

- <span data-ttu-id="58d12-697">VI-Befehlsmodus: `<i>`</span><span class="sxs-lookup"><span data-stu-id="58d12-697">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="58d12-698">Whatiskey</span><span class="sxs-lookup"><span data-stu-id="58d12-698">WhatIsKey</span></span>

<span data-ttu-id="58d12-699">Lesen Sie einen Schlüssel, und teilen Sie mir mit, wofür der Schlüssel gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="58d12-699">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="58d12-700">Befehl: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="58d12-700">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="58d12-701">Ansehen `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="58d12-701">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="58d12-702">Auswahl Funktionen</span><span class="sxs-lookup"><span data-stu-id="58d12-702">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="58d12-703">Exchangepointandmark</span><span class="sxs-lookup"><span data-stu-id="58d12-703">ExchangePointAndMark</span></span>

<span data-ttu-id="58d12-704">Der Cursor wird an der Position der Markierung platziert, und die Markierung wird an die Position des Cursors verschoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-704">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="58d12-705">Ansehen `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="58d12-705">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="58d12-706">SelectAll</span><span class="sxs-lookup"><span data-stu-id="58d12-706">SelectAll</span></span>

<span data-ttu-id="58d12-707">Wählen Sie die gesamte Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="58d12-707">Select the entire line.</span></span>

- <span data-ttu-id="58d12-708">Befehl: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="58d12-708">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="58d12-709">Selectbackwardchar</span><span class="sxs-lookup"><span data-stu-id="58d12-709">SelectBackwardChar</span></span>

<span data-ttu-id="58d12-710">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Zeichen einschließt.</span><span class="sxs-lookup"><span data-stu-id="58d12-710">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="58d12-711">Befehl: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-711">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="58d12-712">Ansehen `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-712">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="58d12-713">Selectbackwardsline</span><span class="sxs-lookup"><span data-stu-id="58d12-713">SelectBackwardsLine</span></span>

<span data-ttu-id="58d12-714">Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an den Anfang der Zeile eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="58d12-714">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="58d12-715">Befehl: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="58d12-715">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="58d12-716">Ansehen `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="58d12-716">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="58d12-717">Selectbackwardword</span><span class="sxs-lookup"><span data-stu-id="58d12-717">SelectBackwardWord</span></span>

<span data-ttu-id="58d12-718">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort enthält.</span><span class="sxs-lookup"><span data-stu-id="58d12-718">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="58d12-719">Befehl: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-719">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="58d12-720">Ansehen `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="58d12-720">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="58d12-721">Selectforwardchar</span><span class="sxs-lookup"><span data-stu-id="58d12-721">SelectForwardChar</span></span>

<span data-ttu-id="58d12-722">Passen Sie die aktuelle Auswahl an, um das nächste Zeichen einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="58d12-722">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="58d12-723">Befehl: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-723">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="58d12-724">Ansehen `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-724">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="58d12-725">Selectforwardword</span><span class="sxs-lookup"><span data-stu-id="58d12-725">SelectForwardWord</span></span>

<span data-ttu-id="58d12-726">Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mit forwardword einschließt.</span><span class="sxs-lookup"><span data-stu-id="58d12-726">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="58d12-727">Ansehen `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="58d12-727">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="58d12-728">SelectLine</span><span class="sxs-lookup"><span data-stu-id="58d12-728">SelectLine</span></span>

<span data-ttu-id="58d12-729">Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an das Ende der Zeile eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="58d12-729">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="58d12-730">Befehl: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="58d12-730">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="58d12-731">Ansehen `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="58d12-731">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="58d12-732">Selectnextword</span><span class="sxs-lookup"><span data-stu-id="58d12-732">SelectNextWord</span></span>

<span data-ttu-id="58d12-733">Passen Sie die aktuelle Auswahl an das nächste Wort an.</span><span class="sxs-lookup"><span data-stu-id="58d12-733">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="58d12-734">Befehl: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="58d12-734">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="58d12-735">Selectshellbackwardword</span><span class="sxs-lookup"><span data-stu-id="58d12-735">SelectShellBackwardWord</span></span>

<span data-ttu-id="58d12-736">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort mithilfe von shellbackwardword einschließt.</span><span class="sxs-lookup"><span data-stu-id="58d12-736">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="58d12-737">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-737">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="58d12-738">Selectshellforwardword</span><span class="sxs-lookup"><span data-stu-id="58d12-738">SelectShellForwardWord</span></span>

<span data-ttu-id="58d12-739">Passen Sie die aktuelle Auswahl so an, dass das nächste Wort mithilfe von shellforwardword eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="58d12-739">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="58d12-740">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-740">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="58d12-741">Selectshellnextword</span><span class="sxs-lookup"><span data-stu-id="58d12-741">SelectShellNextWord</span></span>

<span data-ttu-id="58d12-742">Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mithilfe von shellnextword einschließt.</span><span class="sxs-lookup"><span data-stu-id="58d12-742">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="58d12-743">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="58d12-743">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="58d12-744">Setmark</span><span class="sxs-lookup"><span data-stu-id="58d12-744">SetMark</span></span>

<span data-ttu-id="58d12-745">Markieren Sie die aktuelle Position des Cursors für die Verwendung in einem nachfolgenden Bearbeitungs Befehl.</span><span class="sxs-lookup"><span data-stu-id="58d12-745">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="58d12-746">Ansehen `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="58d12-746">Emacs: `<Ctrl+@>`</span></span>

## <a name="search-functions"></a><span data-ttu-id="58d12-747">Suchfunktionen</span><span class="sxs-lookup"><span data-stu-id="58d12-747">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="58d12-748">Merkmal Suche</span><span class="sxs-lookup"><span data-stu-id="58d12-748">CharacterSearch</span></span>

<span data-ttu-id="58d12-749">Lesen Sie ein Zeichen, und suchen Sie nach dem nächsten Vorkommen dieses Zeichens.</span><span class="sxs-lookup"><span data-stu-id="58d12-749">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="58d12-750">Wenn ein Argument angegeben ist, suchen Sie nach vorn (oder rückwärts, wenn negativ) für das n-te vorkommen.</span><span class="sxs-lookup"><span data-stu-id="58d12-750">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="58d12-751">Befehl: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="58d12-751">Cmd: `<F3>`</span></span>
- <span data-ttu-id="58d12-752">Ansehen `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="58d12-752">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="58d12-753">VI-Einfügemodus: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="58d12-753">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="58d12-754">VI-Befehlsmodus: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="58d12-754">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="58d12-755">Merkmal searchrückwärts</span><span class="sxs-lookup"><span data-stu-id="58d12-755">CharacterSearchBackward</span></span>

<span data-ttu-id="58d12-756">Liest ein Zeichen und sucht rückwärts nach dem nächsten Vorkommen dieses Zeichens.</span><span class="sxs-lookup"><span data-stu-id="58d12-756">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="58d12-757">Wenn ein Argument angegeben wird, suchen Sie nach hinten (oder vorwärts, wenn negativ).</span><span class="sxs-lookup"><span data-stu-id="58d12-757">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="58d12-758">Befehl: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="58d12-758">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="58d12-759">Ansehen `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="58d12-759">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="58d12-760">VI-Einfügemodus: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="58d12-760">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="58d12-761">VI-Befehlsmodus: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="58d12-761">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="58d12-762">Repeatlastcharsearch</span><span class="sxs-lookup"><span data-stu-id="58d12-762">RepeatLastCharSearch</span></span>

<span data-ttu-id="58d12-763">Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche.</span><span class="sxs-lookup"><span data-stu-id="58d12-763">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="58d12-764">VI-Befehlsmodus: `<;>`</span><span class="sxs-lookup"><span data-stu-id="58d12-764">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="58d12-765">Repeatlastcharsearchabwärts</span><span class="sxs-lookup"><span data-stu-id="58d12-765">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="58d12-766">Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche, aber in umgekehrter Richtung.</span><span class="sxs-lookup"><span data-stu-id="58d12-766">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="58d12-767">VI-Befehlsmodus: `<,>`</span><span class="sxs-lookup"><span data-stu-id="58d12-767">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="58d12-768">Repeatsearch</span><span class="sxs-lookup"><span data-stu-id="58d12-768">RepeatSearch</span></span>

<span data-ttu-id="58d12-769">Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="58d12-769">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="58d12-770">VI-Befehlsmodus: `<n>`</span><span class="sxs-lookup"><span data-stu-id="58d12-770">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="58d12-771">Repeatsearchrückwärts</span><span class="sxs-lookup"><span data-stu-id="58d12-771">RepeatSearchBackward</span></span>

<span data-ttu-id="58d12-772">Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="58d12-772">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="58d12-773">VI-Befehlsmodus: `<N>`</span><span class="sxs-lookup"><span data-stu-id="58d12-773">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="58d12-774">Searchchar</span><span class="sxs-lookup"><span data-stu-id="58d12-774">SearchChar</span></span>

<span data-ttu-id="58d12-775">Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="58d12-775">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="58d12-776">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="58d12-776">This is for 't' functionality.</span></span>

- <span data-ttu-id="58d12-777">VI-Befehlsmodus: `<f>`</span><span class="sxs-lookup"><span data-stu-id="58d12-777">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="58d12-778">Searchcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="58d12-778">SearchCharBackward</span></span>

<span data-ttu-id="58d12-779">Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück.</span><span class="sxs-lookup"><span data-stu-id="58d12-779">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="58d12-780">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="58d12-780">This is for 'T' functionality.</span></span>

- <span data-ttu-id="58d12-781">VI-Befehlsmodus: `<F>`</span><span class="sxs-lookup"><span data-stu-id="58d12-781">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="58d12-782">Searchcharbackwardwithbackoff</span><span class="sxs-lookup"><span data-stu-id="58d12-782">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="58d12-783">Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück.</span><span class="sxs-lookup"><span data-stu-id="58d12-783">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="58d12-784">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="58d12-784">This is for 'T' functionality.</span></span>

- <span data-ttu-id="58d12-785">VI-Befehlsmodus: `<T>`</span><span class="sxs-lookup"><span data-stu-id="58d12-785">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="58d12-786">Searchcharwithbackoff</span><span class="sxs-lookup"><span data-stu-id="58d12-786">SearchCharWithBackoff</span></span>

<span data-ttu-id="58d12-787">Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="58d12-787">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="58d12-788">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="58d12-788">This is for 't' functionality.</span></span>

- <span data-ttu-id="58d12-789">VI-Befehlsmodus: `<t>`</span><span class="sxs-lookup"><span data-stu-id="58d12-789">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="58d12-790">SearchForward</span><span class="sxs-lookup"><span data-stu-id="58d12-790">SearchForward</span></span>

<span data-ttu-id="58d12-791">Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.</span><span class="sxs-lookup"><span data-stu-id="58d12-791">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="58d12-792">VI-Einfügemodus: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="58d12-792">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="58d12-793">VI-Befehlsmodus: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="58d12-793">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="58d12-794">Benutzerdefinierte Tastenbindungen</span><span class="sxs-lookup"><span data-stu-id="58d12-794">Custom Key Bindings</span></span>

<span data-ttu-id="58d12-795">Psread Line unterstützt benutzerdefinierte Tastenbindungen mithilfe des Cmdlets `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="58d12-795">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="58d12-796">Die meisten benutzerdefinierten Tastenbindungen wenden eine der oben genannten Funktionen an, z. b.</span><span class="sxs-lookup"><span data-stu-id="58d12-796">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="58d12-797">Sie können einen ScriptBlock an einen Schlüssel binden.</span><span class="sxs-lookup"><span data-stu-id="58d12-797">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="58d12-798">Der ScriptBlock kann beliebig viele Aufgaben erledigen.</span><span class="sxs-lookup"><span data-stu-id="58d12-798">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="58d12-799">Einige nützliche Beispiele sind u.a.</span><span class="sxs-lookup"><span data-stu-id="58d12-799">Some useful examples include</span></span>

- <span data-ttu-id="58d12-800">Bearbeiten der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="58d12-800">edit the command line</span></span>
- <span data-ttu-id="58d12-801">Öffnen eines neuen Fensters (z. b. "Hilfe")</span><span class="sxs-lookup"><span data-stu-id="58d12-801">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="58d12-802">Ändern der Verzeichnisse ohne Änderung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="58d12-802">change directories without changing the command line</span></span>

<span data-ttu-id="58d12-803">Der ScriptBlock empfängt zwei Argumente:</span><span class="sxs-lookup"><span data-stu-id="58d12-803">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="58d12-804">`$key` -Ein **[ConsoleKeyInfo]** -Objekt, das der Schlüssel ist, der die benutzerdefinierte Bindung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="58d12-804">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="58d12-805">Wenn Sie denselben ScriptBlock an mehrere Schlüssel binden und abhängig vom Schlüssel verschiedene Aktionen ausführen müssen, können Sie $Key überprüfen.</span><span class="sxs-lookup"><span data-stu-id="58d12-805">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="58d12-806">Viele benutzerdefinierte Bindungen ignorieren dieses Argument.</span><span class="sxs-lookup"><span data-stu-id="58d12-806">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="58d12-807">`$arg` -Ein beliebiges Argument.</span><span class="sxs-lookup"><span data-stu-id="58d12-807">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="58d12-808">In den meisten Fällen ist dies ein ganzzahliges Argument, das der Benutzer von den Schlüsselbindungen digitargument übergibt.</span><span class="sxs-lookup"><span data-stu-id="58d12-808">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="58d12-809">Wenn die Bindung keine Argumente akzeptiert, ist es sinnvoll, dieses Argument zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="58d12-809">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="58d12-810">Sehen wir uns ein Beispiel an, in dem eine Befehlszeile zum Verlauf hinzugefügt wird, ohne sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58d12-810">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="58d12-811">Dies ist nützlich, wenn Sie vergessen haben, etwas zu tun, ohne die Befehlszeile, die Sie bereits eingegeben haben, erneut eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="58d12-811">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="58d12-812">In der Datei `SamplePSReadLineProfile.ps1` , die im psread Line-Modul Ordner installiert ist, werden viele weitere Beispiele angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58d12-812">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="58d12-813">Die meisten Tastenbindungen verwenden einige Hilfsfunktionen zum Bearbeiten der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="58d12-813">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="58d12-814">Diese APIs werden im nächsten Abschnitt dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="58d12-814">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="58d12-815">APIs für die benutzerdefinierte Schlüssel Bindungs Unterstützung</span><span class="sxs-lookup"><span data-stu-id="58d12-815">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="58d12-816">Die folgenden Funktionen sind in Microsoft. PowerShell. psconsolereadline öffentlich, können jedoch nicht direkt an einen Schlüssel gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="58d12-816">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="58d12-817">Die meisten sind in benutzerdefinierten Tastenkombinationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="58d12-817">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="58d12-818">Fügen Sie eine Befehlszeile zum Verlauf hinzu, ohne sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58d12-818">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="58d12-819">Löschen Sie den Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="58d12-819">Clear the kill-ring.</span></span>  <span data-ttu-id="58d12-820">Dies wird größtenteils zum Testen verwendet.</span><span class="sxs-lookup"><span data-stu-id="58d12-820">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="58d12-821">Löschen Sie die Längen Zeichen aus dem Startmenü.</span><span class="sxs-lookup"><span data-stu-id="58d12-821">Delete length characters from start.</span></span>  <span data-ttu-id="58d12-822">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="58d12-822">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="58d12-823">Führen Sie die Aktion "Ding" basierend auf der Benutzereinstellung aus.</span><span class="sxs-lookup"><span data-stu-id="58d12-823">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="58d12-824">Diese beiden Funktionen rufen nützliche Informationen über den aktuellen Status des Eingabe Puffers ab.</span><span class="sxs-lookup"><span data-stu-id="58d12-824">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="58d12-825">Der erste wird häufiger für einfache Fälle verwendet.</span><span class="sxs-lookup"><span data-stu-id="58d12-825">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="58d12-826">Die zweite wird verwendet, wenn ihre Bindung einen fortgeschrittenen Vorgang mit der AST bewirkt.</span><span class="sxs-lookup"><span data-stu-id="58d12-826">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="58d12-827">Diese beiden Funktionen werden von verwendet `Get-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="58d12-827">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="58d12-828">Der erste wird verwendet, um alle Tastenbindungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="58d12-828">The first is used to get all key bindings.</span></span> <span data-ttu-id="58d12-829">Die zweite wird verwendet, um bestimmte Tastenbindungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="58d12-829">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="58d12-830">Diese Funktion wird von Get-PSReadLineOption verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.</span><span class="sxs-lookup"><span data-stu-id="58d12-830">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="58d12-831">Wenn in der Befehlszeile keine Auswahl vorhanden ist, wird-1 sowohl in Start als auch in der Länge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="58d12-831">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="58d12-832">Wenn eine Auswahl in der Befehlszeile vorhanden ist, werden Start und Länge der Auswahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="58d12-832">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="58d12-833">Fügen Sie am Cursor ein Zeichen oder eine Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="58d12-833">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="58d12-834">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="58d12-834">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="58d12-835">Dies ist der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="58d12-835">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="58d12-836">Sie unterstützt keine Rekursion und ist daher in einer benutzerdefinierten schlüsselbindung nicht nützlich.</span><span class="sxs-lookup"><span data-stu-id="58d12-836">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="58d12-837">Diese Funktion wird von Remove-PSReadLineKeyHandler verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.</span><span class="sxs-lookup"><span data-stu-id="58d12-837">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="58d12-838">Ersetzen Sie einige der Eingaben.</span><span class="sxs-lookup"><span data-stu-id="58d12-838">Replace some of the input.</span></span> <span data-ttu-id="58d12-839">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="58d12-839">This operation supports undo/redo.</span></span> <span data-ttu-id="58d12-840">Dies wird als "Delete", gefolgt von INSERT, bevorzugt, da es als einzelne Aktion für "Rückgängig" behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="58d12-840">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="58d12-841">Bewegen Sie den Cursor in den angegebenen Offset.</span><span class="sxs-lookup"><span data-stu-id="58d12-841">Move the cursor to the given offset.</span></span> <span data-ttu-id="58d12-842">Cursor Bewegung wird nicht für Rückgängigmachen nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="58d12-842">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="58d12-843">Bei dieser Funktion handelt es sich um eine Hilfsmethode, die vom Cmdlet Set-psread lineoption verwendet wird. Sie kann jedoch für eine benutzerdefinierte schlüsselbindung nützlich sein, die eine Einstellung vorübergehend ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="58d12-843">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="58d12-844">Diese Hilfsmethode wird für benutzerdefinierte Bindungen verwendet, die digitargument berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="58d12-844">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="58d12-845">Ein typischer-Rückruf sieht wie folgt aus</span><span class="sxs-lookup"><span data-stu-id="58d12-845">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="58d12-846">HINWEIS</span><span class="sxs-lookup"><span data-stu-id="58d12-846">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="58d12-847">PowerShell-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="58d12-847">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="58d12-848">Für psread line sind PowerShell 3,0 oder höher sowie der Konsolen Host erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58d12-848">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="58d12-849">Es funktioniert nicht in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="58d12-849">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="58d12-850">Dies funktioniert in der-Konsole Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="58d12-850">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="58d12-851">Befehlsverlauf</span><span class="sxs-lookup"><span data-stu-id="58d12-851">COMMAND HISTORY</span></span>

<span data-ttu-id="58d12-852">Psleseline verwaltet eine Verlaufs Datei, die alle Befehle und Daten enthält, die Sie in der Befehlszeile eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="58d12-852">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="58d12-853">Dies kann vertrauliche Daten einschließlich Kenn Wörtern enthalten.</span><span class="sxs-lookup"><span data-stu-id="58d12-853">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="58d12-854">Wenn Sie z. b. das `ConvertTo-SecureString` Cmdlet verwenden, wird das Kennwort als nur-Text in der Verlaufs Datei protokolliert.</span><span class="sxs-lookup"><span data-stu-id="58d12-854">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="58d12-855">Die Verlaufs Dateien sind eine Datei mit dem Namen `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="58d12-855">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="58d12-856">Auf Windows-Systemen wird die Verlaufs Datei unter gespeichert `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="58d12-856">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="58d12-857">Auf nicht-Windows-Systemen werden die Verlaufs Dateien unter `$env:XDG_DATA_HOME/powershell/PSReadLine` oder gespeichert `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="58d12-857">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="58d12-858">Feedback & zu psread Line beitragen</span><span class="sxs-lookup"><span data-stu-id="58d12-858">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="58d12-859">Psread Line auf GitHub</span><span class="sxs-lookup"><span data-stu-id="58d12-859">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="58d12-860">Sie können auf der GitHub-Seite eine Pull Request einreichen oder Feedback einreichen.</span><span class="sxs-lookup"><span data-stu-id="58d12-860">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="58d12-861">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="58d12-861">SEE ALSO</span></span>

<span data-ttu-id="58d12-862">"Psread Line" wird stark von der GNU-Bibliothek für die [Zeilen](https://tiswww.case.edu/php/chet/readline/rltop.html) Übereinstimmung beeinflusst</span><span class="sxs-lookup"><span data-stu-id="58d12-862">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>

