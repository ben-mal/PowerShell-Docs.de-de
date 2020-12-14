---
description: Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.
keywords: powershell
Locale: en-US
ms.date: 11/16/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über psread Line
ms.openlocfilehash: 25fc3a9a814728057b1ebc7e721d3fba84ae72c2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94692308"
---
# <a name="psreadline"></a><span data-ttu-id="d8b64-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="d8b64-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="d8b64-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="d8b64-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="d8b64-106">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8b64-106">Short Description</span></span>

<span data-ttu-id="d8b64-107">Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="d8b64-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="d8b64-108">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8b64-108">Long Description</span></span>

<span data-ttu-id="d8b64-109">Psleline 2,0 bietet eine leistungsfähige Befehlszeilen Bearbeitungsfunktion für die PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="d8b64-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="d8b64-110">Sie bietet:</span><span class="sxs-lookup"><span data-stu-id="d8b64-110">It provides:</span></span>

- <span data-ttu-id="d8b64-111">Syntax Farbgebung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="d8b64-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="d8b64-112">Visuelle Hinweise auf Syntax Fehler</span><span class="sxs-lookup"><span data-stu-id="d8b64-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="d8b64-113">Bessere mehrzeilige Erfahrung (sowohl Bearbeitung als auch Verlauf)</span><span class="sxs-lookup"><span data-stu-id="d8b64-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="d8b64-114">Anpassbare Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="d8b64-114">Customizable key bindings</span></span>
- <span data-ttu-id="d8b64-115">Cmd-und Emacs-Modi</span><span class="sxs-lookup"><span data-stu-id="d8b64-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="d8b64-116">Viele Konfigurationsoptionen</span><span class="sxs-lookup"><span data-stu-id="d8b64-116">Many configuration options</span></span>
- <span data-ttu-id="d8b64-117">Bash-Stil Vervollständigung (optional im cmd-Modus, Standard im Emacs-Modus)</span><span class="sxs-lookup"><span data-stu-id="d8b64-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="d8b64-118">Emacs: Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="d8b64-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="d8b64-119">PowerShell-tokenbasierte "Wort Bewegung" und "Kill"</span><span class="sxs-lookup"><span data-stu-id="d8b64-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="d8b64-120">Für psread line sind PowerShell 3,0 oder höher sowie der Konsolen Host erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d8b64-120">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="d8b64-121">Es funktioniert nicht in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="d8b64-121">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="d8b64-122">Dies funktioniert in der-Konsole Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="d8b64-122">It does work in the console of Visual Studio Code.</span></span>

<span data-ttu-id="d8b64-123">Die folgenden Funktionen sind in der-Klasse **[Microsoft. PowerShell. psconsolereadline]** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d8b64-123">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="d8b64-124">Grundlegende Bearbeitungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="d8b64-124">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="d8b64-125">Abbruch</span><span class="sxs-lookup"><span data-stu-id="d8b64-125">Abort</span></span>

<span data-ttu-id="d8b64-126">Abbrechen der aktuellen Aktion, z.b. inkrementelle Verlaufs Suche.</span><span class="sxs-lookup"><span data-stu-id="d8b64-126">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="d8b64-127">Ansehen `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-127">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="d8b64-128">Akzeptandgetnext</span><span class="sxs-lookup"><span data-stu-id="d8b64-128">AcceptAndGetNext</span></span>

<span data-ttu-id="d8b64-129">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-129">Attempt to execute the current input.</span></span> <span data-ttu-id="d8b64-130">Wenn Sie ausgeführt werden kann (wie z. b. Accept Line), erinnern Sie sich beim nächsten Aufruf von "read line" an das nächste Element aus dem Verlauf.</span><span class="sxs-lookup"><span data-stu-id="d8b64-130">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="d8b64-131">Ansehen `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-131">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="d8b64-132">Annahme</span><span class="sxs-lookup"><span data-stu-id="d8b64-132">AcceptLine</span></span>

<span data-ttu-id="d8b64-133">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-133">Attempt to execute the current input.</span></span> <span data-ttu-id="d8b64-134">Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d8b64-134">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="d8b64-135">Befehl: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-135">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="d8b64-136">Ansehen `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-136">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="d8b64-137">VI-Einfügemodus: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-137">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="d8b64-138">AddLine</span><span class="sxs-lookup"><span data-stu-id="d8b64-138">AddLine</span></span>

<span data-ttu-id="d8b64-139">Die Fortsetzungs Aufforderung wird in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d8b64-139">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="d8b64-140">Dies ist nützlich, um mehrzeilige Eingaben als einen einzelnen Befehl einzugeben, auch wenn eine einzelne Zeile allein eine Eingabe ist.</span><span class="sxs-lookup"><span data-stu-id="d8b64-140">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="d8b64-141">Befehl: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-141">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="d8b64-142">Ansehen `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-142">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="d8b64-143">VI-Einfügemodus: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-143">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="d8b64-144">VI-Befehlsmodus: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-144">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="d8b64-145">Backwarddeletechar</span><span class="sxs-lookup"><span data-stu-id="d8b64-145">BackwardDeleteChar</span></span>

<span data-ttu-id="d8b64-146">Löschen Sie das Zeichen vor dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-146">Delete the character before the cursor.</span></span>

- <span data-ttu-id="d8b64-147">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-147">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="d8b64-148">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-148">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="d8b64-149">VI-Einfügemodus: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-149">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="d8b64-150">VI-Befehlsmodus: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-150">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="d8b64-151">Backwarddelta-Eline</span><span class="sxs-lookup"><span data-stu-id="d8b64-151">BackwardDeleteLine</span></span>

<span data-ttu-id="d8b64-152">Wie backwardkillline löscht Text vom Punkt bis zum Anfang der Zeile, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-152">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="d8b64-153">Befehl: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-153">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="d8b64-154">VI-Einfügemodus: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-154">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="d8b64-155">VI-Befehlsmodus: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-155">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="d8b64-156">Backwarddeleteword</span><span class="sxs-lookup"><span data-stu-id="d8b64-156">BackwardDeleteWord</span></span>

<span data-ttu-id="d8b64-157">Löscht das vorherige Wort.</span><span class="sxs-lookup"><span data-stu-id="d8b64-157">Deletes the previous word.</span></span>

- <span data-ttu-id="d8b64-158">VI-Befehlsmodus: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-158">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="d8b64-159">Backwardkillline</span><span class="sxs-lookup"><span data-stu-id="d8b64-159">BackwardKillLine</span></span>

<span data-ttu-id="d8b64-160">Löschen Sie die Eingabe vom Beginn der Eingabe in den Cursor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-160">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="d8b64-161">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-161">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d8b64-162">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-162">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="d8b64-163">Backwardkillword</span><span class="sxs-lookup"><span data-stu-id="d8b64-163">BackwardKillWord</span></span>

<span data-ttu-id="d8b64-164">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-164">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="d8b64-165">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d8b64-165">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="d8b64-166">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-166">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d8b64-167">Befehl: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-167">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="d8b64-168">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-168">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="d8b64-169">VI-Einfügemodus: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-169">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="d8b64-170">VI-Befehlsmodus: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-170">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="d8b64-171">Cancelline</span><span class="sxs-lookup"><span data-stu-id="d8b64-171">CancelLine</span></span>

<span data-ttu-id="d8b64-172">Brechen Sie die aktuelle Eingabe ab, belassen Sie die Eingabe auf dem Bildschirm, kehren Sie jedoch zurück zum Host, damit die Eingabeaufforderung erneut ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="d8b64-172">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="d8b64-173">VI-Einfügemodus: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-173">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="d8b64-174">VI-Befehlsmodus: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-174">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="d8b64-175">Kopieren</span><span class="sxs-lookup"><span data-stu-id="d8b64-175">Copy</span></span>

<span data-ttu-id="d8b64-176">Kopiert den ausgewählten Bereich in die Zwischenablage des Systems.</span><span class="sxs-lookup"><span data-stu-id="d8b64-176">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="d8b64-177">Wenn keine Region ausgewählt ist, kopieren Sie die gesamte Zeile.</span><span class="sxs-lookup"><span data-stu-id="d8b64-177">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="d8b64-178">Befehl: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-178">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="d8b64-179">Copyorcancelline</span><span class="sxs-lookup"><span data-stu-id="d8b64-179">CopyOrCancelLine</span></span>

<span data-ttu-id="d8b64-180">Wenn Text ausgewählt ist, kopieren Sie ihn in die Zwischenablage, andernfalls brechen Sie die Zeile ab.</span><span class="sxs-lookup"><span data-stu-id="d8b64-180">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="d8b64-181">Befehl: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-181">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="d8b64-182">Ansehen `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-182">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="d8b64-183">Ausschneiden</span><span class="sxs-lookup"><span data-stu-id="d8b64-183">Cut</span></span>

<span data-ttu-id="d8b64-184">Löscht die ausgewählte Region, in der Gelöschter Text in der Zwischenablage des Systems</span><span class="sxs-lookup"><span data-stu-id="d8b64-184">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="d8b64-185">Befehl: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-185">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="d8b64-186">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="d8b64-186">DeleteChar</span></span>

<span data-ttu-id="d8b64-187">Löschen Sie das Zeichen unter dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-187">Delete the character under the cursor.</span></span>

- <span data-ttu-id="d8b64-188">Befehl: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-188">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="d8b64-189">Ansehen `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-189">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="d8b64-190">VI-Einfügemodus: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-190">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="d8b64-191">VI-Befehlsmodus: `<Delete>` , `<x>` , `<d,l>` , `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-191">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="d8b64-192">Deletecharorexit</span><span class="sxs-lookup"><span data-stu-id="d8b64-192">DeleteCharOrExit</span></span>

<span data-ttu-id="d8b64-193">Löschen Sie das Zeichen unter dem Cursor, oder beenden Sie den Prozess, wenn die Zeile leer ist.</span><span class="sxs-lookup"><span data-stu-id="d8b64-193">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="d8b64-194">Ansehen `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-194">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="d8b64-195">Deleteendof</span><span class="sxs-lookup"><span data-stu-id="d8b64-195">DeleteEndOfWord</span></span>

<span data-ttu-id="d8b64-196">Bis zum Ende des Worts löschen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-196">Delete to the end of the word.</span></span>

- <span data-ttu-id="d8b64-197">VI-Befehlsmodus: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-197">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="d8b64-198">"Deleteline</span><span class="sxs-lookup"><span data-stu-id="d8b64-198">DeleteLine</span></span>

<span data-ttu-id="d8b64-199">Löscht die aktuelle Zeile und aktiviert die Rückgängigmachen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-199">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="d8b64-200">VI-Befehlsmodus: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-200">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="d8b64-201">Delta-inetyp</span><span class="sxs-lookup"><span data-stu-id="d8b64-201">DeleteLineToFirstChar</span></span>

<span data-ttu-id="d8b64-202">Löscht Text vom Cursor zum ersten Zeichen der Zeile, das nicht leer ist.</span><span class="sxs-lookup"><span data-stu-id="d8b64-202">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="d8b64-203">VI-Befehlsmodus: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-203">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="d8b64-204">Deletegeend</span><span class="sxs-lookup"><span data-stu-id="d8b64-204">DeleteToEnd</span></span>

<span data-ttu-id="d8b64-205">Bis zum Ende der Zeile löschen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-205">Delete to the end of the line.</span></span>

- <span data-ttu-id="d8b64-206">VI-Befehlsmodus: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-206">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="d8b64-207">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="d8b64-207">DeleteWord</span></span>

<span data-ttu-id="d8b64-208">Löschen Sie das nächste Wort.</span><span class="sxs-lookup"><span data-stu-id="d8b64-208">Delete the next word.</span></span>

- <span data-ttu-id="d8b64-209">VI-Befehlsmodus: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-209">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="d8b64-210">Forwarddelta-Eline</span><span class="sxs-lookup"><span data-stu-id="d8b64-210">ForwardDeleteLine</span></span>

<span data-ttu-id="d8b64-211">Wie forwardkillline löscht Text vom Punkt bis zum Ende der Zeile, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-211">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="d8b64-212">Befehl: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-212">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="d8b64-213">VI-Einfügemodus: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-213">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="d8b64-214">VI-Befehlsmodus: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-214">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="d8b64-215">Insertlineoberhalb</span><span class="sxs-lookup"><span data-stu-id="d8b64-215">InsertLineAbove</span></span>

<span data-ttu-id="d8b64-216">Oberhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="d8b64-216">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="d8b64-217">Der Cursor wechselt zum Anfang der neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="d8b64-217">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="d8b64-218">Befehl: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-218">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="d8b64-219">Insertlinebelow</span><span class="sxs-lookup"><span data-stu-id="d8b64-219">InsertLineBelow</span></span>

<span data-ttu-id="d8b64-220">Unterhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="d8b64-220">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="d8b64-221">Der Cursor wechselt zum Anfang der neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="d8b64-221">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="d8b64-222">Befehl: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-222">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="d8b64-223">Invertieren</span><span class="sxs-lookup"><span data-stu-id="d8b64-223">InvertCase</span></span>

<span data-ttu-id="d8b64-224">Kehrt die Groß-/Kleinschreibung des aktuellen Zeichens um und wechselt zum nächsten.</span><span class="sxs-lookup"><span data-stu-id="d8b64-224">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="d8b64-225">VI-Befehlsmodus: `<~>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-225">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="d8b64-226">Killline</span><span class="sxs-lookup"><span data-stu-id="d8b64-226">KillLine</span></span>

<span data-ttu-id="d8b64-227">Löschen Sie die Eingabe vom Cursor bis zum Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="d8b64-227">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="d8b64-228">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-228">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d8b64-229">Ansehen `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-229">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="d8b64-230">Killregion</span><span class="sxs-lookup"><span data-stu-id="d8b64-230">KillRegion</span></span>

<span data-ttu-id="d8b64-231">Beenden Sie den Text zwischen dem Cursor und der Markierung.</span><span class="sxs-lookup"><span data-stu-id="d8b64-231">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="d8b64-232">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-232">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="d8b64-233">Killword</span><span class="sxs-lookup"><span data-stu-id="d8b64-233">KillWord</span></span>

<span data-ttu-id="d8b64-234">Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts.</span><span class="sxs-lookup"><span data-stu-id="d8b64-234">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="d8b64-235">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d8b64-235">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="d8b64-236">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-236">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d8b64-237">Befehl: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-237">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="d8b64-238">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-238">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="d8b64-239">VI-Einfügemodus: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-239">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="d8b64-240">VI-Befehlsmodus: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-240">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="d8b64-241">Einfügen</span><span class="sxs-lookup"><span data-stu-id="d8b64-241">Paste</span></span>

<span data-ttu-id="d8b64-242">Fügen Sie Text aus der Zwischenablage des Systems ein.</span><span class="sxs-lookup"><span data-stu-id="d8b64-242">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="d8b64-243">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-243">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="d8b64-244">VI-Einfügemodus: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-244">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="d8b64-245">VI-Befehlsmodus: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-245">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8b64-246">Wenn Sie die Funktion **Einfügen** verwenden, wird der gesamte Inhalt des Zwischenablage Puffers in den Eingabepuffer von psread Line eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-246">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="d8b64-247">Der Eingabepuffer wird dann an den PowerShell-Parser übergeben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-247">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="d8b64-248">Eingaben, die mithilfe der **Rechtsklick-Einfügemethode** der Konsolenanwendung eingefügt werden, werden jeweils ein Zeichen in den Eingabepuffer kopiert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-248">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="d8b64-249">Der Eingabepuffer wird an den Parser übergeben, wenn ein Zeilen vorzeichensatz kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="d8b64-249">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="d8b64-250">Daher wird die Eingabe jeweils Zeilen gleich analysiert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-250">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="d8b64-251">Der Unterschied zwischen den Methoden zum Einfügen führt zu einem anderen Ausführungs Verhalten.</span><span class="sxs-lookup"><span data-stu-id="d8b64-251">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="d8b64-252">Pasteafter</span><span class="sxs-lookup"><span data-stu-id="d8b64-252">PasteAfter</span></span>

<span data-ttu-id="d8b64-253">Fügen Sie die Zwischenablage nach dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.</span><span class="sxs-lookup"><span data-stu-id="d8b64-253">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="d8b64-254">VI-Befehlsmodus: `<p>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-254">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="d8b64-255">Pastebefore</span><span class="sxs-lookup"><span data-stu-id="d8b64-255">PasteBefore</span></span>

<span data-ttu-id="d8b64-256">Fügen Sie die Zwischenablage vor dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.</span><span class="sxs-lookup"><span data-stu-id="d8b64-256">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="d8b64-257">VI-Befehlsmodus: `<P>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-257">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="d8b64-258">Prepdandaccept</span><span class="sxs-lookup"><span data-stu-id="d8b64-258">PrependAndAccept</span></span>

<span data-ttu-id="d8b64-259">Fügen Sie ein "#" vorangesteht, und akzeptieren Sie die Zeile.</span><span class="sxs-lookup"><span data-stu-id="d8b64-259">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="d8b64-260">VI-Befehlsmodus: `<#>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-260">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="d8b64-261">Wiederholen</span><span class="sxs-lookup"><span data-stu-id="d8b64-261">Redo</span></span>

<span data-ttu-id="d8b64-262">Rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-262">Undo an undo.</span></span>

- <span data-ttu-id="d8b64-263">Befehl: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-263">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="d8b64-264">VI-Einfügemodus: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-264">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="d8b64-265">VI-Befehlsmodus: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-265">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="d8b64-266">Repeatlastcommand</span><span class="sxs-lookup"><span data-stu-id="d8b64-266">RepeatLastCommand</span></span>

<span data-ttu-id="d8b64-267">Wiederholen Sie die letzte Textänderung.</span><span class="sxs-lookup"><span data-stu-id="d8b64-267">Repeat the last text modification.</span></span>

- <span data-ttu-id="d8b64-268">VI-Befehlsmodus: `<.>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-268">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="d8b64-269">Revertline</span><span class="sxs-lookup"><span data-stu-id="d8b64-269">RevertLine</span></span>

<span data-ttu-id="d8b64-270">Kehrt alle Eingaben in die aktuelle Eingabe um.</span><span class="sxs-lookup"><span data-stu-id="d8b64-270">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="d8b64-271">Befehl: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-271">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="d8b64-272">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-272">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="d8b64-273">Shellbackwardkillword</span><span class="sxs-lookup"><span data-stu-id="d8b64-273">ShellBackwardKillWord</span></span>

<span data-ttu-id="d8b64-274">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-274">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="d8b64-275">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d8b64-275">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="d8b64-276">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-276">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="d8b64-277">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-277">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="d8b64-278">Shellkillword</span><span class="sxs-lookup"><span data-stu-id="d8b64-278">ShellKillWord</span></span>

<span data-ttu-id="d8b64-279">Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts.</span><span class="sxs-lookup"><span data-stu-id="d8b64-279">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="d8b64-280">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d8b64-280">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="d8b64-281">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-281">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="d8b64-282">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-282">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="d8b64-283">Austausch Zeichen</span><span class="sxs-lookup"><span data-stu-id="d8b64-283">SwapCharacters</span></span>

<span data-ttu-id="d8b64-284">Tauschen Sie das aktuelle und das aktuelle Zeichen aus.</span><span class="sxs-lookup"><span data-stu-id="d8b64-284">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="d8b64-285">Ansehen `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-285">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="d8b64-286">VI-Einfügemodus: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-286">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="d8b64-287">VI-Befehlsmodus: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-287">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="d8b64-288">Rückgängig machen</span><span class="sxs-lookup"><span data-stu-id="d8b64-288">Undo</span></span>

<span data-ttu-id="d8b64-289">Rückgängigmachen einer vorherigen Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="d8b64-289">Undo a previous edit.</span></span>

- <span data-ttu-id="d8b64-290">Befehl: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-290">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="d8b64-291">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-291">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="d8b64-292">VI-Einfügemodus: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-292">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="d8b64-293">VI-Befehlsmodus: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-293">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="d8b64-294">Nicht doall</span><span class="sxs-lookup"><span data-stu-id="d8b64-294">UndoAll</span></span>

<span data-ttu-id="d8b64-295">Alle vorherigen Änderungen für die Zeile rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-295">Undo all previous edits for line.</span></span>

- <span data-ttu-id="d8b64-296">VI-Befehlsmodus: `<U>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-296">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="d8b64-297">Unixwordrubout</span><span class="sxs-lookup"><span data-stu-id="d8b64-297">UnixWordRubout</span></span>

<span data-ttu-id="d8b64-298">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-298">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="d8b64-299">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d8b64-299">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="d8b64-300">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-300">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d8b64-301">Ansehen `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-301">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="d8b64-302">Validateandakzeptline</span><span class="sxs-lookup"><span data-stu-id="d8b64-302">ValidateAndAcceptLine</span></span>

<span data-ttu-id="d8b64-303">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-303">Attempt to execute the current input.</span></span> <span data-ttu-id="d8b64-304">Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d8b64-304">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="d8b64-305">Ansehen `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-305">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="d8b64-306">Viakzeptline</span><span class="sxs-lookup"><span data-stu-id="d8b64-306">ViAcceptLine</span></span>

<span data-ttu-id="d8b64-307">Akzeptieren Sie die Zeile, und wechseln Sie zum Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="d8b64-307">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="d8b64-308">VI-Befehlsmodus: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-308">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="d8b64-309">Viakzeptlineorexit</span><span class="sxs-lookup"><span data-stu-id="d8b64-309">ViAcceptLineOrExit</span></span>

<span data-ttu-id="d8b64-310">Wie deletecharorexit im Emacs-Modus, akzeptiert jedoch die Zeile, anstatt ein Zeichen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-310">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="d8b64-311">VI-Einfügemodus: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-311">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="d8b64-312">VI-Befehlsmodus: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-312">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="d8b64-313">Viappendline</span><span class="sxs-lookup"><span data-stu-id="d8b64-313">ViAppendLine</span></span>

<span data-ttu-id="d8b64-314">Unterhalb der aktuellen Zeile wird eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-314">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="d8b64-315">VI-Befehlsmodus: `<o>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-315">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="d8b64-316">Vibackwarddeleteglob</span><span class="sxs-lookup"><span data-stu-id="d8b64-316">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="d8b64-317">Löscht das vorherige Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8b64-317">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="d8b64-318">VI-Befehlsmodus: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-318">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="d8b64-319">Vibackwardglob</span><span class="sxs-lookup"><span data-stu-id="d8b64-319">ViBackwardGlob</span></span>

<span data-ttu-id="d8b64-320">Verschiebt den Cursor zurück an den Anfang des vorherigen Worts, wobei nur Leerraum als Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8b64-320">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="d8b64-321">VI-Befehlsmodus: `<B>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-321">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="d8b64-322">Videletebrace</span><span class="sxs-lookup"><span data-stu-id="d8b64-322">ViDeleteBrace</span></span>

<span data-ttu-id="d8b64-323">Suchen Sie nach der passenden geschweiften Klammer, Klammer oder eckigen Klammer, und löschen Sie alle Inhalte in, einschließlich der geschweiften Klammer.</span><span class="sxs-lookup"><span data-stu-id="d8b64-323">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="d8b64-324">VI-Befehlsmodus: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-324">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="d8b64-325">Videleteendobglob</span><span class="sxs-lookup"><span data-stu-id="d8b64-325">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="d8b64-326">Bis zum Ende des Worts löschen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-326">Delete to the end of the word.</span></span>

- <span data-ttu-id="d8b64-327">VI-Befehlsmodus: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-327">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="d8b64-328">Videleteglob</span><span class="sxs-lookup"><span data-stu-id="d8b64-328">ViDeleteGlob</span></span>

<span data-ttu-id="d8b64-329">Löschen Sie den nächsten globmuster (Leerzeichen mit Trennzeichen).</span><span class="sxs-lookup"><span data-stu-id="d8b64-329">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="d8b64-330">VI-Befehlsmodus: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-330">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="d8b64-331">Videletetobeforechar</span><span class="sxs-lookup"><span data-stu-id="d8b64-331">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="d8b64-332">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-332">Deletes until given character.</span></span>

- <span data-ttu-id="d8b64-333">VI-Befehlsmodus: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-333">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="d8b64-334">Videletebackbeforecharrückwärts</span><span class="sxs-lookup"><span data-stu-id="d8b64-334">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="d8b64-335">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-335">Deletes until given character.</span></span>

- <span data-ttu-id="d8b64-336">VI-Befehlsmodus: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-336">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="d8b64-337">Videleteto Char</span><span class="sxs-lookup"><span data-stu-id="d8b64-337">ViDeleteToChar</span></span>

<span data-ttu-id="d8b64-338">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-338">Deletes until given character.</span></span>

- <span data-ttu-id="d8b64-339">VI-Befehlsmodus: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-339">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="d8b64-340">Videletebackcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="d8b64-340">ViDeleteToCharBackward</span></span>

<span data-ttu-id="d8b64-341">Löscht rückwärts bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-341">Deletes backwards until given character.</span></span>

- <span data-ttu-id="d8b64-342">VI-Befehlsmodus: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-342">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="d8b64-343">Viinsertatbeginung</span><span class="sxs-lookup"><span data-stu-id="d8b64-343">ViInsertAtBegining</span></span>

<span data-ttu-id="d8b64-344">Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Anfang der Zeile.</span><span class="sxs-lookup"><span data-stu-id="d8b64-344">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="d8b64-345">VI-Befehlsmodus: `<I>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-345">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="d8b64-346">Viinsertatend</span><span class="sxs-lookup"><span data-stu-id="d8b64-346">ViInsertAtEnd</span></span>

<span data-ttu-id="d8b64-347">Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Ende der Zeile.</span><span class="sxs-lookup"><span data-stu-id="d8b64-347">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="d8b64-348">VI-Befehlsmodus: `<A>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-348">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="d8b64-349">Viinsertline</span><span class="sxs-lookup"><span data-stu-id="d8b64-349">ViInsertLine</span></span>

<span data-ttu-id="d8b64-350">Oberhalb der aktuellen Zeile wird eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-350">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="d8b64-351">VI-Befehlsmodus: `<O>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-351">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="d8b64-352">Viinsertwithappend</span><span class="sxs-lookup"><span data-stu-id="d8b64-352">ViInsertWithAppend</span></span>

<span data-ttu-id="d8b64-353">An der aktuellen Zeilen Position anfügen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-353">Append from the current line position.</span></span>

- <span data-ttu-id="d8b64-354">VI-Befehlsmodus: `<a>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-354">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="d8b64-355">Viinsertwithdelete</span><span class="sxs-lookup"><span data-stu-id="d8b64-355">ViInsertWithDelete</span></span>

<span data-ttu-id="d8b64-356">Löschen Sie das aktuelle Zeichen und wechseln Sie in den Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="d8b64-356">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="d8b64-357">VI-Befehlsmodus: `<s>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-357">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="d8b64-358">Vijoinlines</span><span class="sxs-lookup"><span data-stu-id="d8b64-358">ViJoinLines</span></span>

<span data-ttu-id="d8b64-359">Verbindet die aktuelle Zeile und die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="d8b64-359">Joins the current line and the next line.</span></span>

- <span data-ttu-id="d8b64-360">VI-Befehlsmodus: `<J>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-360">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="d8b64-361">Vireplaceline</span><span class="sxs-lookup"><span data-stu-id="d8b64-361">ViReplaceLine</span></span>

<span data-ttu-id="d8b64-362">Löschen Sie die gesamte Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="d8b64-362">Erase the entire command line.</span></span>

- <span data-ttu-id="d8b64-363">VI-Befehlsmodus: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-363">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="d8b64-364">Vireplacetobeforechar</span><span class="sxs-lookup"><span data-stu-id="d8b64-364">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="d8b64-365">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-365">Replaces until given character.</span></span>

- <span data-ttu-id="d8b64-366">VI-Befehlsmodus: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-366">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="d8b64-367">Vireplaceumbeforecharrückwärts</span><span class="sxs-lookup"><span data-stu-id="d8b64-367">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="d8b64-368">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-368">Replaces until given character.</span></span>

- <span data-ttu-id="d8b64-369">VI-Befehlsmodus: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-369">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="d8b64-370">Vireplaceumchar</span><span class="sxs-lookup"><span data-stu-id="d8b64-370">ViReplaceToChar</span></span>

<span data-ttu-id="d8b64-371">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-371">Deletes until given character.</span></span>

- <span data-ttu-id="d8b64-372">VI-Befehlsmodus: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-372">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="d8b64-373">Vireplacebackcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="d8b64-373">ViReplaceToCharBackward</span></span>

<span data-ttu-id="d8b64-374">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-374">Replaces until given character.</span></span>

- <span data-ttu-id="d8b64-375">VI-Befehlsmodus: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-375">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="d8b64-376">Viyankbeginningosline</span><span class="sxs-lookup"><span data-stu-id="d8b64-376">ViYankBeginningOfLine</span></span>

<span data-ttu-id="d8b64-377">Yank vom Anfang des Puffers bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-377">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="d8b64-378">VI-Befehlsmodus: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-378">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="d8b64-379">Viyankendobglob</span><span class="sxs-lookup"><span data-stu-id="d8b64-379">ViYankEndOfGlob</span></span>

<span data-ttu-id="d8b64-380">Yank vom Cursor bis zum Ende des Worts (s).</span><span class="sxs-lookup"><span data-stu-id="d8b64-380">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="d8b64-381">VI-Befehlsmodus: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-381">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="d8b64-382">Viyankendof</span><span class="sxs-lookup"><span data-stu-id="d8b64-382">ViYankEndOfWord</span></span>

<span data-ttu-id="d8b64-383">Yank vom Cursor bis zum Ende des Worts (s).</span><span class="sxs-lookup"><span data-stu-id="d8b64-383">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="d8b64-384">VI-Befehlsmodus: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-384">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="d8b64-385">Viyankleft</span><span class="sxs-lookup"><span data-stu-id="d8b64-385">ViYankLeft</span></span>

<span data-ttu-id="d8b64-386">Die Zeichen werden Links vom Cursor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-386">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="d8b64-387">VI-Befehlsmodus: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-387">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="d8b64-388">Viyankline</span><span class="sxs-lookup"><span data-stu-id="d8b64-388">ViYankLine</span></span>

<span data-ttu-id="d8b64-389">Den gesamten Puffer.</span><span class="sxs-lookup"><span data-stu-id="d8b64-389">Yank the entire buffer.</span></span>

- <span data-ttu-id="d8b64-390">VI-Befehlsmodus: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-390">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="d8b64-391">Viyanknextglob</span><span class="sxs-lookup"><span data-stu-id="d8b64-391">ViYankNextGlob</span></span>

<span data-ttu-id="d8b64-392">Yank vom Cursor bis zum Anfang des nächsten Worts (n).</span><span class="sxs-lookup"><span data-stu-id="d8b64-392">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="d8b64-393">VI-Befehlsmodus: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-393">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="d8b64-394">Viyanknextword</span><span class="sxs-lookup"><span data-stu-id="d8b64-394">ViYankNextWord</span></span>

<span data-ttu-id="d8b64-395">Das Wort (e) nach dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-395">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="d8b64-396">VI-Befehlsmodus: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-396">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="d8b64-397">Viyankprozent</span><span class="sxs-lookup"><span data-stu-id="d8b64-397">ViYankPercent</span></span>

<span data-ttu-id="d8b64-398">Von der entsprechenden geschweiften geschweifter Klammer.</span><span class="sxs-lookup"><span data-stu-id="d8b64-398">Yank to/from matching brace.</span></span>

- <span data-ttu-id="d8b64-399">VI-Befehlsmodus: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-399">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="d8b64-400">Viyankpreviousglob</span><span class="sxs-lookup"><span data-stu-id="d8b64-400">ViYankPreviousGlob</span></span>

<span data-ttu-id="d8b64-401">Yank von Anfang des Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-401">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="d8b64-402">VI-Befehlsmodus: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-402">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="d8b64-403">Viyankpreviousword</span><span class="sxs-lookup"><span data-stu-id="d8b64-403">ViYankPreviousWord</span></span>

<span data-ttu-id="d8b64-404">Das Wort (e) vor dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-404">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="d8b64-405">VI-Befehlsmodus: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-405">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="d8b64-406">Viyankright</span><span class="sxs-lookup"><span data-stu-id="d8b64-406">ViYankRight</span></span>

<span data-ttu-id="d8b64-407">(E) unter und rechts vom Cursor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-407">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="d8b64-408">VI-Befehlsmodus: `<y,l>` , `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-408">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="d8b64-409">Viyanktoendosline</span><span class="sxs-lookup"><span data-stu-id="d8b64-409">ViYankToEndOfLine</span></span>

<span data-ttu-id="d8b64-410">Yank vom Cursor bis zum Ende des Puffers.</span><span class="sxs-lookup"><span data-stu-id="d8b64-410">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="d8b64-411">VI-Befehlsmodus: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-411">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="d8b64-412">Viyanktofirstchar</span><span class="sxs-lookup"><span data-stu-id="d8b64-412">ViYankToFirstChar</span></span>

<span data-ttu-id="d8b64-413">Yank vom ersten Zeichen, das kein Leerzeichen ist, bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-413">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="d8b64-414">VI-Befehlsmodus: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-414">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="d8b64-415">Yank</span><span class="sxs-lookup"><span data-stu-id="d8b64-415">Yank</span></span>

<span data-ttu-id="d8b64-416">Fügen Sie der Eingabe den zuletzt beendeten Text hinzu.</span><span class="sxs-lookup"><span data-stu-id="d8b64-416">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="d8b64-417">Ansehen `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-417">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="d8b64-418">Yanklastarg</span><span class="sxs-lookup"><span data-stu-id="d8b64-418">YankLastArg</span></span>

<span data-ttu-id="d8b64-419">Das letzte Argument aus der vorherigen Verlaufs Zeile.</span><span class="sxs-lookup"><span data-stu-id="d8b64-419">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="d8b64-420">Mit einem Argument verhält sich das erste Mal, wenn es aufgerufen wird, wie yankntharg.</span><span class="sxs-lookup"><span data-stu-id="d8b64-420">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="d8b64-421">Wenn Sie mehrmals aufgerufen wird, durchläuft Sie stattdessen den Verlauf, und arg legt die Richtung fest (negative Umkehrung der Richtung).</span><span class="sxs-lookup"><span data-stu-id="d8b64-421">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="d8b64-422">Befehl: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-422">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="d8b64-423">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-423">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="d8b64-424">Yankntharg</span><span class="sxs-lookup"><span data-stu-id="d8b64-424">YankNthArg</span></span>

<span data-ttu-id="d8b64-425">Yank das erste Argument (nach dem Befehl) aus der vorherigen Verlaufs Zeile.</span><span class="sxs-lookup"><span data-stu-id="d8b64-425">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="d8b64-426">Bei einem Argument wird das n-te Argument (beginnend bei 0), wenn das Argument negativ ist, mit dem letzten Argument beginnen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-426">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="d8b64-427">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-427">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="d8b64-428">Yankpop</span><span class="sxs-lookup"><span data-stu-id="d8b64-428">YankPop</span></span>

<span data-ttu-id="d8b64-429">Wenn der vorherige Vorgang "Yank" oder "yankpop" war, ersetzen Sie den zuvor angezeigten Text durch den nächsten ausgeblendeten Text aus dem Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="d8b64-429">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="d8b64-430">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-430">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="d8b64-431">Cursor Verschiebungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="d8b64-431">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="d8b64-432">Backwardchar</span><span class="sxs-lookup"><span data-stu-id="d8b64-432">BackwardChar</span></span>

<span data-ttu-id="d8b64-433">Bewegen Sie den Cursor um ein Zeichen nach links.</span><span class="sxs-lookup"><span data-stu-id="d8b64-433">Move the cursor one character to the left.</span></span> <span data-ttu-id="d8b64-434">Dadurch kann der Cursor in die vorherige Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="d8b64-434">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="d8b64-435">Befehl: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-435">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="d8b64-436">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-436">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="d8b64-437">VI-Einfügemodus: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-437">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="d8b64-438">VI-Befehlsmodus: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-438">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="d8b64-439">Backwardword</span><span class="sxs-lookup"><span data-stu-id="d8b64-439">BackwardWord</span></span>

<span data-ttu-id="d8b64-440">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-440">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="d8b64-441">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-441">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d8b64-442">Befehl: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-442">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="d8b64-443">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-443">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="d8b64-444">VI-Einfügemodus: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-444">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="d8b64-445">VI-Befehlsmodus: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-445">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="d8b64-446">Beginningosline</span><span class="sxs-lookup"><span data-stu-id="d8b64-446">BeginningOfLine</span></span>

<span data-ttu-id="d8b64-447">Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Anfang der aktuellen Zeile oder, wenn Sie sich bereits am Anfang der Zeile befinden, bis zum Anfang der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="d8b64-447">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="d8b64-448">Wenn die Eingabe über eine einzelne Zeile verfügt, wechseln Sie zum Anfang der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="d8b64-448">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="d8b64-449">Befehl: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-449">Cmd: `<Home>`</span></span>
- <span data-ttu-id="d8b64-450">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-450">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="d8b64-451">VI-Einfügemodus: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-451">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="d8b64-452">VI-Befehlsmodus: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-452">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="d8b64-453">Endosline</span><span class="sxs-lookup"><span data-stu-id="d8b64-453">EndOfLine</span></span>

<span data-ttu-id="d8b64-454">Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Ende der aktuellen Zeile, oder wechseln Sie, wenn Sie sich bereits am Ende der Zeile befindet, bis zum Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="d8b64-454">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="d8b64-455">Wenn die Eingabe über eine einzelne Zeile verfügt, verschieben Sie das Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="d8b64-455">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="d8b64-456">Befehl: `<End>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-456">Cmd: `<End>`</span></span>
- <span data-ttu-id="d8b64-457">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-457">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="d8b64-458">VI-Einfügemodus: `<End>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-458">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="d8b64-459">Forwardchar</span><span class="sxs-lookup"><span data-stu-id="d8b64-459">ForwardChar</span></span>

<span data-ttu-id="d8b64-460">Bewegen Sie den Cursor um ein Zeichen nach rechts.</span><span class="sxs-lookup"><span data-stu-id="d8b64-460">Move the cursor one character to the right.</span></span> <span data-ttu-id="d8b64-461">Dadurch kann der Cursor in die nächste Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="d8b64-461">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="d8b64-462">Befehl: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-462">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="d8b64-463">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-463">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="d8b64-464">VI-Einfügemodus: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-464">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="d8b64-465">VI-Befehlsmodus: `<RightArrow>` , `<Space>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-465">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="d8b64-466">Forwardword</span><span class="sxs-lookup"><span data-stu-id="d8b64-466">ForwardWord</span></span>

<span data-ttu-id="d8b64-467">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="d8b64-467">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="d8b64-468">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-468">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d8b64-469">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-469">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="d8b64-470">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="d8b64-470">GotoBrace</span></span>

<span data-ttu-id="d8b64-471">Wechseln Sie zur passenden geschweiften Klammer, Klammer oder eckigen Klammer.</span><span class="sxs-lookup"><span data-stu-id="d8b64-471">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="d8b64-472">Befehl: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-472">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="d8b64-473">VI-Einfügemodus: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-473">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="d8b64-474">VI-Befehlsmodus: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-474">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="d8b64-475">Goum Column</span><span class="sxs-lookup"><span data-stu-id="d8b64-475">GotoColumn</span></span>

<span data-ttu-id="d8b64-476">Wechseln Sie in die Spalte, die von arg angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d8b64-476">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="d8b64-477">VI-Befehlsmodus: `<|>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-477">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="d8b64-478">Gostarfirstnonblankosline</span><span class="sxs-lookup"><span data-stu-id="d8b64-478">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="d8b64-479">Bewegen Sie den Cursor auf das erste nicht leere Zeichen in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="d8b64-479">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="d8b64-480">VI-Befehlsmodus: `<^>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-480">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="d8b64-481">"MUVE"</span><span class="sxs-lookup"><span data-stu-id="d8b64-481">MoveToEndOfLine</span></span>

<span data-ttu-id="d8b64-482">Bewegen Sie den Cursor an das Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="d8b64-482">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="d8b64-483">VI-Befehlsmodus: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-483">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="d8b64-484">Nextline</span><span class="sxs-lookup"><span data-stu-id="d8b64-484">NextLine</span></span>

<span data-ttu-id="d8b64-485">Bewegen Sie den Cursor in die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="d8b64-485">Move the cursor to the next line.</span></span>

- <span data-ttu-id="d8b64-486">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-486">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="d8b64-487">Nextword</span><span class="sxs-lookup"><span data-stu-id="d8b64-487">NextWord</span></span>

<span data-ttu-id="d8b64-488">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="d8b64-488">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="d8b64-489">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-489">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d8b64-490">Befehl: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-490">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="d8b64-491">VI-Einfügemodus: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-491">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="d8b64-492">VI-Befehlsmodus: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-492">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="d8b64-493">Nextwordend</span><span class="sxs-lookup"><span data-stu-id="d8b64-493">NextWordEnd</span></span>

<span data-ttu-id="d8b64-494">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="d8b64-494">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="d8b64-495">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-495">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d8b64-496">VI-Befehlsmodus: `<e>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-496">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="d8b64-497">Previousline</span><span class="sxs-lookup"><span data-stu-id="d8b64-497">PreviousLine</span></span>

<span data-ttu-id="d8b64-498">Bewegen Sie den Cursor in die vorherige Zeile.</span><span class="sxs-lookup"><span data-stu-id="d8b64-498">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="d8b64-499">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-499">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="d8b64-500">Shellbackwardword</span><span class="sxs-lookup"><span data-stu-id="d8b64-500">ShellBackwardWord</span></span>

<span data-ttu-id="d8b64-501">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-501">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="d8b64-502">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-502">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="d8b64-503">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-503">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="d8b64-504">Shellforwardword</span><span class="sxs-lookup"><span data-stu-id="d8b64-504">ShellForwardWord</span></span>

<span data-ttu-id="d8b64-505">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="d8b64-505">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="d8b64-506">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-506">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="d8b64-507">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-507">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="d8b64-508">Shellnextword</span><span class="sxs-lookup"><span data-stu-id="d8b64-508">ShellNextWord</span></span>

<span data-ttu-id="d8b64-509">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="d8b64-509">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="d8b64-510">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-510">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="d8b64-511">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-511">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="d8b64-512">Vibackwardword</span><span class="sxs-lookup"><span data-stu-id="d8b64-512">ViBackwardWord</span></span>

<span data-ttu-id="d8b64-513">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-513">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="d8b64-514">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-514">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d8b64-515">VI-Befehlsmodus: `<b>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-515">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="d8b64-516">Viendobglob</span><span class="sxs-lookup"><span data-stu-id="d8b64-516">ViEndOfGlob</span></span>

<span data-ttu-id="d8b64-517">Verschiebt den Cursor an das Ende des Worts und verwendet nur Leerzeichen als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-517">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="d8b64-518">VI-Befehlsmodus: `<E>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-518">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="d8b64-519">Viendof previousglob</span><span class="sxs-lookup"><span data-stu-id="d8b64-519">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="d8b64-520">Wechselt zum Ende des vorherigen Worts, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8b64-520">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="d8b64-521">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-521">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="d8b64-522">Vigoumbrace</span><span class="sxs-lookup"><span data-stu-id="d8b64-522">ViGotoBrace</span></span>

<span data-ttu-id="d8b64-523">Ähnelt gotobrace, aber ist Zeichen basiert anstelle von tokenbasiert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-523">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="d8b64-524">VI-Befehlsmodus: `<%>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-524">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="d8b64-525">Vinextglob</span><span class="sxs-lookup"><span data-stu-id="d8b64-525">ViNextGlob</span></span>

<span data-ttu-id="d8b64-526">Wechselt zum nächsten Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8b64-526">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="d8b64-527">VI-Befehlsmodus: `<W>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-527">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="d8b64-528">Vinextword</span><span class="sxs-lookup"><span data-stu-id="d8b64-528">ViNextWord</span></span>

<span data-ttu-id="d8b64-529">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="d8b64-529">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="d8b64-530">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-530">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d8b64-531">VI-Befehlsmodus: `<w>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-531">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="d8b64-532">Verlaufs Funktionen</span><span class="sxs-lookup"><span data-stu-id="d8b64-532">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="d8b64-533">Beginningof History</span><span class="sxs-lookup"><span data-stu-id="d8b64-533">BeginningOfHistory</span></span>

<span data-ttu-id="d8b64-534">Wechselt zum ersten Element im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="d8b64-534">Move to the first item in the history.</span></span>

- <span data-ttu-id="d8b64-535">Ansehen `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="d8b64-535">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="d8b64-536">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="d8b64-536">ClearHistory</span></span>

<span data-ttu-id="d8b64-537">Löscht den Verlauf in psleline.</span><span class="sxs-lookup"><span data-stu-id="d8b64-537">Clears history in PSReadLine.</span></span> <span data-ttu-id="d8b64-538">Dies wirkt sich nicht auf den PowerShell-Verlauf aus.</span><span class="sxs-lookup"><span data-stu-id="d8b64-538">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="d8b64-539">Befehl: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-539">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="d8b64-540">EndOf History</span><span class="sxs-lookup"><span data-stu-id="d8b64-540">EndOfHistory</span></span>

<span data-ttu-id="d8b64-541">Wechselt zum letzten Element (der aktuellen Eingabe) im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="d8b64-541">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="d8b64-542">Ansehen `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-542">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="d8b64-543">Forwardsearchhistory</span><span class="sxs-lookup"><span data-stu-id="d8b64-543">ForwardSearchHistory</span></span>

<span data-ttu-id="d8b64-544">Führt eine inkrementelle Forward-Suche im Verlauf durch</span><span class="sxs-lookup"><span data-stu-id="d8b64-544">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="d8b64-545">Befehl: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-545">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="d8b64-546">Ansehen `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-546">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="d8b64-547">Historysearchrückwärts</span><span class="sxs-lookup"><span data-stu-id="d8b64-547">HistorySearchBackward</span></span>

<span data-ttu-id="d8b64-548">Ersetzen Sie die aktuelle Eingabe durch das Element "Previous" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.</span><span class="sxs-lookup"><span data-stu-id="d8b64-548">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="d8b64-549">Befehl: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-549">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="d8b64-550">Historysearchforward</span><span class="sxs-lookup"><span data-stu-id="d8b64-550">HistorySearchForward</span></span>

<span data-ttu-id="d8b64-551">Ersetzen Sie die aktuelle Eingabe durch das Element "Next" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.</span><span class="sxs-lookup"><span data-stu-id="d8b64-551">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="d8b64-552">Befehl: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-552">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="d8b64-553">Nexthistory</span><span class="sxs-lookup"><span data-stu-id="d8b64-553">NextHistory</span></span>

<span data-ttu-id="d8b64-554">Ersetzen Sie die aktuelle Eingabe durch das "Next"-Element aus dem psleline-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="d8b64-554">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="d8b64-555">Befehl: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-555">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="d8b64-556">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-556">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="d8b64-557">VI-Einfügemodus: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-557">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="d8b64-558">VI-Befehlsmodus: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-558">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="d8b64-559">Previoushistory</span><span class="sxs-lookup"><span data-stu-id="d8b64-559">PreviousHistory</span></span>

<span data-ttu-id="d8b64-560">Ersetzen Sie die aktuelle Eingabe durch das "Previous"-Element aus dem psleline-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="d8b64-560">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="d8b64-561">Befehl: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-561">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="d8b64-562">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-562">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="d8b64-563">VI-Einfügemodus: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-563">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="d8b64-564">VI-Befehlsmodus: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="d8b64-564">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="d8b64-565">Reversesearchhistory</span><span class="sxs-lookup"><span data-stu-id="d8b64-565">ReverseSearchHistory</span></span>

<span data-ttu-id="d8b64-566">Führt eine inkrementelle Rückwärtssuche über den Verlauf durch</span><span class="sxs-lookup"><span data-stu-id="d8b64-566">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="d8b64-567">Befehl: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-567">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="d8b64-568">Ansehen `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-568">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="d8b64-569">Visearchhistoryrückwärts</span><span class="sxs-lookup"><span data-stu-id="d8b64-569">ViSearchHistoryBackward</span></span>

<span data-ttu-id="d8b64-570">Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.</span><span class="sxs-lookup"><span data-stu-id="d8b64-570">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="d8b64-571">VI-Einfügemodus: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-571">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="d8b64-572">VI-Befehlsmodus: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-572">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="d8b64-573">Vervollständigungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="d8b64-573">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="d8b64-574">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="d8b64-574">Complete</span></span>

<span data-ttu-id="d8b64-575">Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-575">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="d8b64-576">Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8b64-576">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="d8b64-577">Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-577">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="d8b64-578">Ansehen `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-578">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="d8b64-579">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="d8b64-579">MenuComplete</span></span>

<span data-ttu-id="d8b64-580">Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-580">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="d8b64-581">Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8b64-581">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="d8b64-582">Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-582">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="d8b64-583">Befehl: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-583">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="d8b64-584">Ansehen `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-584">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="d8b64-585">Possiblecompletions</span><span class="sxs-lookup"><span data-stu-id="d8b64-585">PossibleCompletions</span></span>

<span data-ttu-id="d8b64-586">Hiermit wird die Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-586">Display the list of possible completions.</span></span>

- <span data-ttu-id="d8b64-587">Ansehen `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-587">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="d8b64-588">VI-Einfügemodus: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-588">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="d8b64-589">VI-Befehlsmodus: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-589">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="d8b64-590">Tabcompletenext</span><span class="sxs-lookup"><span data-stu-id="d8b64-590">TabCompleteNext</span></span>

<span data-ttu-id="d8b64-591">Es wurde versucht, den Text, der den Cursor umgibt, mit der nächsten verfügbaren Beendigung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-591">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="d8b64-592">Befehl: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-592">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="d8b64-593">VI-Befehlsmodus: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-593">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="d8b64-594">Tabcompleteprevious</span><span class="sxs-lookup"><span data-stu-id="d8b64-594">TabCompletePrevious</span></span>

<span data-ttu-id="d8b64-595">Versuchen Sie, den Text, der den Cursor umgibt, mit dem vorherigen verfügbaren Abschluss abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-595">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="d8b64-596">Befehl: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-596">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="d8b64-597">VI-Befehlsmodus: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-597">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="d8b64-598">Vitabcompletenext</span><span class="sxs-lookup"><span data-stu-id="d8b64-598">ViTabCompleteNext</span></span>

<span data-ttu-id="d8b64-599">Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompletenext auf.</span><span class="sxs-lookup"><span data-stu-id="d8b64-599">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="d8b64-600">VI-Einfügemodus: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-600">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="d8b64-601">Vitabcompleteprevious</span><span class="sxs-lookup"><span data-stu-id="d8b64-601">ViTabCompletePrevious</span></span>

<span data-ttu-id="d8b64-602">Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompleteprevious auf.</span><span class="sxs-lookup"><span data-stu-id="d8b64-602">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="d8b64-603">VI-Einfügemodus: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-603">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="d8b64-604">Sonstige Funktionen</span><span class="sxs-lookup"><span data-stu-id="d8b64-604">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="d8b64-605">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="d8b64-605">CaptureScreen</span></span>

<span data-ttu-id="d8b64-606">Interaktive Bildschirmaufnahme starten-nach oben/nach-unten-Pfeile Select Lines, Enter kopiert markierten Text in die Zwischenablage als Text und HTML.</span><span class="sxs-lookup"><span data-stu-id="d8b64-606">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="d8b64-607">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-607">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="d8b64-608">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="d8b64-608">ClearScreen</span></span>

<span data-ttu-id="d8b64-609">Löschen Sie den Bildschirm, und zeichnen Sie die aktuelle Zeile am oberen Rand des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="d8b64-609">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="d8b64-610">Befehl: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-610">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="d8b64-611">Ansehen `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-611">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="d8b64-612">VI-Einfügemodus: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-612">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="d8b64-613">VI-Befehlsmodus: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-613">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="d8b64-614">Digitargument</span><span class="sxs-lookup"><span data-stu-id="d8b64-614">DigitArgument</span></span>

<span data-ttu-id="d8b64-615">Starten Sie ein neues Ziffern Argument, das an andere Funktionen übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8b64-615">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="d8b64-616">Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="d8b64-616">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="d8b64-617">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="d8b64-617">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="d8b64-618">VI-Befehlsmodus: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-618">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="d8b64-619">Invokeprompt</span><span class="sxs-lookup"><span data-stu-id="d8b64-619">InvokePrompt</span></span>

<span data-ttu-id="d8b64-620">Löscht die aktuelle Eingabeaufforderung und ruft die prompt-Funktion auf, um die Eingabeaufforderung erneut anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-620">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="d8b64-621">Nützlich für benutzerdefinierte Schlüssel Handler, die den Zustand ändern, z. b. Ändern des aktuellen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="d8b64-621">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="d8b64-622">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-622">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="d8b64-623">Scrolldisplaydown</span><span class="sxs-lookup"><span data-stu-id="d8b64-623">ScrollDisplayDown</span></span>

<span data-ttu-id="d8b64-624">Scrollen Sie in der Anzeige einen Bildschirm nach unten.</span><span class="sxs-lookup"><span data-stu-id="d8b64-624">Scroll the display down one screen.</span></span>

- <span data-ttu-id="d8b64-625">Befehl: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-625">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="d8b64-626">Ansehen `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-626">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="d8b64-627">Scrolldisplaydownline</span><span class="sxs-lookup"><span data-stu-id="d8b64-627">ScrollDisplayDownLine</span></span>

<span data-ttu-id="d8b64-628">Scrollen Sie in der Anzeige um eine Zeile nach unten.</span><span class="sxs-lookup"><span data-stu-id="d8b64-628">Scroll the display down one line.</span></span>

- <span data-ttu-id="d8b64-629">Befehl: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-629">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="d8b64-630">Ansehen `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-630">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="d8b64-631">Scrolldisplaytcursor</span><span class="sxs-lookup"><span data-stu-id="d8b64-631">ScrollDisplayToCursor</span></span>

<span data-ttu-id="d8b64-632">Scrollen Sie in der Anzeige zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-632">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="d8b64-633">Ansehen `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-633">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="d8b64-634">Scrolldisplaytop</span><span class="sxs-lookup"><span data-stu-id="d8b64-634">ScrollDisplayTop</span></span>

<span data-ttu-id="d8b64-635">Scrollen Sie in der Anzeige nach oben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-635">Scroll the display to the top.</span></span>

- <span data-ttu-id="d8b64-636">Ansehen `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-636">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="d8b64-637">Scrolldisplayup</span><span class="sxs-lookup"><span data-stu-id="d8b64-637">ScrollDisplayUp</span></span>

<span data-ttu-id="d8b64-638">Scrollen Sie einen Bildschirm nach oben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-638">Scroll the display up one screen.</span></span>

- <span data-ttu-id="d8b64-639">Befehl: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-639">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="d8b64-640">Ansehen `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-640">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="d8b64-641">Scrolldisplayupline</span><span class="sxs-lookup"><span data-stu-id="d8b64-641">ScrollDisplayUpLine</span></span>

<span data-ttu-id="d8b64-642">Scrollen Sie in der Anzeige um eine Zeile nach oben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-642">Scroll the display up one line.</span></span>

- <span data-ttu-id="d8b64-643">Befehl: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-643">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="d8b64-644">Ansehen `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-644">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="d8b64-645">Selfinsert</span><span class="sxs-lookup"><span data-stu-id="d8b64-645">SelfInsert</span></span>

<span data-ttu-id="d8b64-646">Fügen Sie den Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="d8b64-646">Insert the key.</span></span>

- <span data-ttu-id="d8b64-647">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-647">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="d8b64-648">Showkeybindungen</span><span class="sxs-lookup"><span data-stu-id="d8b64-648">ShowKeyBindings</span></span>

<span data-ttu-id="d8b64-649">Alle gebundenen Schlüssel anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-649">Show all bound keys.</span></span>

- <span data-ttu-id="d8b64-650">Befehl: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-650">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="d8b64-651">Ansehen `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-651">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="d8b64-652">VI-Einfügemodus: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-652">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="d8b64-653">Vicommandmode</span><span class="sxs-lookup"><span data-stu-id="d8b64-653">ViCommandMode</span></span>

<span data-ttu-id="d8b64-654">Wechseln Sie in den aktuellen Betriebsmodus von Vi-Insert zu VI-Command.</span><span class="sxs-lookup"><span data-stu-id="d8b64-654">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="d8b64-655">VI-Einfügemodus: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-655">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="d8b64-656">Vidigitargumentinchord</span><span class="sxs-lookup"><span data-stu-id="d8b64-656">ViDigitArgumentInChord</span></span>

<span data-ttu-id="d8b64-657">Startet ein neues Ziffern Argument, das in einem der VI-Akkorde an andere Funktionen übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8b64-657">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="d8b64-658">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-658">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="d8b64-659">Vieditvisuell</span><span class="sxs-lookup"><span data-stu-id="d8b64-659">ViEditVisually</span></span>

<span data-ttu-id="d8b64-660">Bearbeiten Sie die Befehlszeile in einem Text-Editor, der durch $ENV: Editor oder $env: Visual angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d8b64-660">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="d8b64-661">Ansehen `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-661">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="d8b64-662">VI-Befehlsmodus: `<v>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-662">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="d8b64-663">Viexit</span><span class="sxs-lookup"><span data-stu-id="d8b64-663">ViExit</span></span>

<span data-ttu-id="d8b64-664">Beendet die Shell.</span><span class="sxs-lookup"><span data-stu-id="d8b64-664">Exits the shell.</span></span>

- <span data-ttu-id="d8b64-665">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-665">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="d8b64-666">Viinsertmode</span><span class="sxs-lookup"><span data-stu-id="d8b64-666">ViInsertMode</span></span>

<span data-ttu-id="d8b64-667">Wechselt in den Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="d8b64-667">Switch to Insert mode.</span></span>

- <span data-ttu-id="d8b64-668">VI-Befehlsmodus: `<i>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-668">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="d8b64-669">Whatiskey</span><span class="sxs-lookup"><span data-stu-id="d8b64-669">WhatIsKey</span></span>

<span data-ttu-id="d8b64-670">Lesen Sie einen Schlüssel, und teilen Sie mir mit, wofür der Schlüssel gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="d8b64-670">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="d8b64-671">Befehl: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-671">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="d8b64-672">Ansehen `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-672">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="d8b64-673">Auswahl Funktionen</span><span class="sxs-lookup"><span data-stu-id="d8b64-673">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="d8b64-674">Exchangepointandmark</span><span class="sxs-lookup"><span data-stu-id="d8b64-674">ExchangePointAndMark</span></span>

<span data-ttu-id="d8b64-675">Der Cursor wird an der Position der Markierung platziert, und die Markierung wird an die Position des Cursors verschoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-675">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="d8b64-676">Ansehen `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-676">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="d8b64-677">SelectAll</span><span class="sxs-lookup"><span data-stu-id="d8b64-677">SelectAll</span></span>

<span data-ttu-id="d8b64-678">Wählen Sie die gesamte Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="d8b64-678">Select the entire line.</span></span>

- <span data-ttu-id="d8b64-679">Befehl: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-679">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="d8b64-680">Selectbackwardchar</span><span class="sxs-lookup"><span data-stu-id="d8b64-680">SelectBackwardChar</span></span>

<span data-ttu-id="d8b64-681">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Zeichen einschließt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-681">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="d8b64-682">Befehl: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-682">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="d8b64-683">Ansehen `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-683">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="d8b64-684">Selectbackwardsline</span><span class="sxs-lookup"><span data-stu-id="d8b64-684">SelectBackwardsLine</span></span>

<span data-ttu-id="d8b64-685">Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an den Anfang der Zeile eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="d8b64-685">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="d8b64-686">Befehl: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-686">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="d8b64-687">Ansehen `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-687">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="d8b64-688">Selectbackwardword</span><span class="sxs-lookup"><span data-stu-id="d8b64-688">SelectBackwardWord</span></span>

<span data-ttu-id="d8b64-689">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort enthält.</span><span class="sxs-lookup"><span data-stu-id="d8b64-689">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="d8b64-690">Befehl: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-690">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="d8b64-691">Ansehen `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-691">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="d8b64-692">Selectforwardchar</span><span class="sxs-lookup"><span data-stu-id="d8b64-692">SelectForwardChar</span></span>

<span data-ttu-id="d8b64-693">Passen Sie die aktuelle Auswahl an, um das nächste Zeichen einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-693">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="d8b64-694">Befehl: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-694">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="d8b64-695">Ansehen `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-695">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="d8b64-696">Selectforwardword</span><span class="sxs-lookup"><span data-stu-id="d8b64-696">SelectForwardWord</span></span>

<span data-ttu-id="d8b64-697">Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mit forwardword einschließt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-697">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="d8b64-698">Ansehen `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-698">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="d8b64-699">SelectLine</span><span class="sxs-lookup"><span data-stu-id="d8b64-699">SelectLine</span></span>

<span data-ttu-id="d8b64-700">Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an das Ende der Zeile eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="d8b64-700">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="d8b64-701">Befehl: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-701">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="d8b64-702">Ansehen `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-702">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="d8b64-703">Selectnextword</span><span class="sxs-lookup"><span data-stu-id="d8b64-703">SelectNextWord</span></span>

<span data-ttu-id="d8b64-704">Passen Sie die aktuelle Auswahl an das nächste Wort an.</span><span class="sxs-lookup"><span data-stu-id="d8b64-704">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="d8b64-705">Befehl: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-705">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="d8b64-706">Selectshellbackwardword</span><span class="sxs-lookup"><span data-stu-id="d8b64-706">SelectShellBackwardWord</span></span>

<span data-ttu-id="d8b64-707">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort mithilfe von shellbackwardword einschließt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-707">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="d8b64-708">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-708">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="d8b64-709">Selectshellforwardword</span><span class="sxs-lookup"><span data-stu-id="d8b64-709">SelectShellForwardWord</span></span>

<span data-ttu-id="d8b64-710">Passen Sie die aktuelle Auswahl so an, dass das nächste Wort mithilfe von shellforwardword eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="d8b64-710">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="d8b64-711">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-711">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="d8b64-712">Selectshellnextword</span><span class="sxs-lookup"><span data-stu-id="d8b64-712">SelectShellNextWord</span></span>

<span data-ttu-id="d8b64-713">Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mithilfe von shellnextword einschließt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-713">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="d8b64-714">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-714">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="d8b64-715">Setmark</span><span class="sxs-lookup"><span data-stu-id="d8b64-715">SetMark</span></span>

<span data-ttu-id="d8b64-716">Markieren Sie die aktuelle Position des Cursors für die Verwendung in einem nachfolgenden Bearbeitungs Befehl.</span><span class="sxs-lookup"><span data-stu-id="d8b64-716">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="d8b64-717">Ansehen `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="d8b64-717">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="d8b64-718">Suchfunktionen</span><span class="sxs-lookup"><span data-stu-id="d8b64-718">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="d8b64-719">Merkmal Suche</span><span class="sxs-lookup"><span data-stu-id="d8b64-719">CharacterSearch</span></span>

<span data-ttu-id="d8b64-720">Lesen Sie ein Zeichen, und suchen Sie nach dem nächsten Vorkommen dieses Zeichens.</span><span class="sxs-lookup"><span data-stu-id="d8b64-720">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="d8b64-721">Wenn ein Argument angegeben ist, suchen Sie nach vorn (oder rückwärts, wenn negativ) für das n-te vorkommen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-721">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="d8b64-722">Befehl: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-722">Cmd: `<F3>`</span></span>
- <span data-ttu-id="d8b64-723">Ansehen `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-723">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="d8b64-724">VI-Einfügemodus: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-724">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="d8b64-725">VI-Befehlsmodus: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-725">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="d8b64-726">Merkmal searchrückwärts</span><span class="sxs-lookup"><span data-stu-id="d8b64-726">CharacterSearchBackward</span></span>

<span data-ttu-id="d8b64-727">Liest ein Zeichen und sucht rückwärts nach dem nächsten Vorkommen dieses Zeichens.</span><span class="sxs-lookup"><span data-stu-id="d8b64-727">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="d8b64-728">Wenn ein Argument angegeben wird, suchen Sie nach hinten (oder vorwärts, wenn negativ).</span><span class="sxs-lookup"><span data-stu-id="d8b64-728">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="d8b64-729">Befehl: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-729">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="d8b64-730">Ansehen `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-730">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="d8b64-731">VI-Einfügemodus: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-731">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="d8b64-732">VI-Befehlsmodus: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-732">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="d8b64-733">Repeatlastcharsearch</span><span class="sxs-lookup"><span data-stu-id="d8b64-733">RepeatLastCharSearch</span></span>

<span data-ttu-id="d8b64-734">Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche.</span><span class="sxs-lookup"><span data-stu-id="d8b64-734">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="d8b64-735">VI-Befehlsmodus: `<;>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-735">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="d8b64-736">Repeatlastcharsearchabwärts</span><span class="sxs-lookup"><span data-stu-id="d8b64-736">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="d8b64-737">Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche, aber in umgekehrter Richtung.</span><span class="sxs-lookup"><span data-stu-id="d8b64-737">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="d8b64-738">VI-Befehlsmodus: `<,>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-738">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="d8b64-739">Repeatsearch</span><span class="sxs-lookup"><span data-stu-id="d8b64-739">RepeatSearch</span></span>

<span data-ttu-id="d8b64-740">Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-740">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="d8b64-741">VI-Befehlsmodus: `<n>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-741">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="d8b64-742">Repeatsearchrückwärts</span><span class="sxs-lookup"><span data-stu-id="d8b64-742">RepeatSearchBackward</span></span>

<span data-ttu-id="d8b64-743">Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="d8b64-743">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="d8b64-744">VI-Befehlsmodus: `<N>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-744">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="d8b64-745">Searchchar</span><span class="sxs-lookup"><span data-stu-id="d8b64-745">SearchChar</span></span>

<span data-ttu-id="d8b64-746">Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="d8b64-746">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="d8b64-747">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d8b64-747">This is for 't' functionality.</span></span>

- <span data-ttu-id="d8b64-748">VI-Befehlsmodus: `<f>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-748">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="d8b64-749">Searchcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="d8b64-749">SearchCharBackward</span></span>

<span data-ttu-id="d8b64-750">Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück.</span><span class="sxs-lookup"><span data-stu-id="d8b64-750">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="d8b64-751">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d8b64-751">This is for 'T' functionality.</span></span>

- <span data-ttu-id="d8b64-752">VI-Befehlsmodus: `<F>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-752">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="d8b64-753">Searchcharbackwardwithbackoff</span><span class="sxs-lookup"><span data-stu-id="d8b64-753">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="d8b64-754">Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück.</span><span class="sxs-lookup"><span data-stu-id="d8b64-754">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="d8b64-755">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d8b64-755">This is for 'T' functionality.</span></span>

- <span data-ttu-id="d8b64-756">VI-Befehlsmodus: `<T>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-756">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="d8b64-757">Searchcharwithbackoff</span><span class="sxs-lookup"><span data-stu-id="d8b64-757">SearchCharWithBackoff</span></span>

<span data-ttu-id="d8b64-758">Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="d8b64-758">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="d8b64-759">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d8b64-759">This is for 't' functionality.</span></span>

- <span data-ttu-id="d8b64-760">VI-Befehlsmodus: `<t>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-760">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="d8b64-761">SearchForward</span><span class="sxs-lookup"><span data-stu-id="d8b64-761">SearchForward</span></span>

<span data-ttu-id="d8b64-762">Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.</span><span class="sxs-lookup"><span data-stu-id="d8b64-762">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="d8b64-763">VI-Einfügemodus: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-763">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="d8b64-764">VI-Befehlsmodus: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="d8b64-764">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="d8b64-765">Benutzerdefinierte Tastenbindungen</span><span class="sxs-lookup"><span data-stu-id="d8b64-765">Custom Key Bindings</span></span>

<span data-ttu-id="d8b64-766">Psread Line unterstützt benutzerdefinierte Tastenbindungen mithilfe des Cmdlets `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="d8b64-766">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="d8b64-767">Die meisten benutzerdefinierten Tastenbindungen wenden eine der oben genannten Funktionen an, z. b.</span><span class="sxs-lookup"><span data-stu-id="d8b64-767">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="d8b64-768">Sie können einen ScriptBlock an einen Schlüssel binden.</span><span class="sxs-lookup"><span data-stu-id="d8b64-768">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="d8b64-769">Der ScriptBlock kann beliebig viele Aufgaben erledigen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-769">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="d8b64-770">Einige nützliche Beispiele sind u.a.</span><span class="sxs-lookup"><span data-stu-id="d8b64-770">Some useful examples include</span></span>

- <span data-ttu-id="d8b64-771">Bearbeiten der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="d8b64-771">edit the command line</span></span>
- <span data-ttu-id="d8b64-772">Öffnen eines neuen Fensters (z. b. "Hilfe")</span><span class="sxs-lookup"><span data-stu-id="d8b64-772">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="d8b64-773">Ändern der Verzeichnisse ohne Änderung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="d8b64-773">change directories without changing the command line</span></span>

<span data-ttu-id="d8b64-774">Der ScriptBlock empfängt zwei Argumente:</span><span class="sxs-lookup"><span data-stu-id="d8b64-774">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="d8b64-775">`$key` -Ein **[ConsoleKeyInfo]** -Objekt, das der Schlüssel ist, der die benutzerdefinierte Bindung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="d8b64-775">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="d8b64-776">Wenn Sie denselben ScriptBlock an mehrere Schlüssel binden und abhängig vom Schlüssel verschiedene Aktionen ausführen müssen, können Sie $Key überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-776">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="d8b64-777">Viele benutzerdefinierte Bindungen ignorieren dieses Argument.</span><span class="sxs-lookup"><span data-stu-id="d8b64-777">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="d8b64-778">`$arg` -Ein beliebiges Argument.</span><span class="sxs-lookup"><span data-stu-id="d8b64-778">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="d8b64-779">In den meisten Fällen ist dies ein ganzzahliges Argument, das der Benutzer von den Schlüsselbindungen digitargument übergibt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-779">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="d8b64-780">Wenn die Bindung keine Argumente akzeptiert, ist es sinnvoll, dieses Argument zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="d8b64-780">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="d8b64-781">Sehen wir uns ein Beispiel an, in dem eine Befehlszeile zum Verlauf hinzugefügt wird, ohne sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-781">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="d8b64-782">Dies ist nützlich, wenn Sie vergessen haben, etwas zu tun, ohne die Befehlszeile, die Sie bereits eingegeben haben, erneut eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-782">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="d8b64-783">In der Datei `SamplePSReadLineProfile.ps1` , die im psread Line-Modul Ordner installiert ist, werden viele weitere Beispiele angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-783">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="d8b64-784">Die meisten Tastenbindungen verwenden einige Hilfsfunktionen zum Bearbeiten der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="d8b64-784">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="d8b64-785">Diese APIs werden im nächsten Abschnitt dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-785">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="d8b64-786">APIs für die benutzerdefinierte Schlüssel Bindungs Unterstützung</span><span class="sxs-lookup"><span data-stu-id="d8b64-786">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="d8b64-787">Die folgenden Funktionen sind in Microsoft. PowerShell. psconsolereadline öffentlich, können jedoch nicht direkt an einen Schlüssel gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="d8b64-787">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="d8b64-788">Die meisten sind in benutzerdefinierten Tastenkombinationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="d8b64-788">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="d8b64-789">Fügen Sie eine Befehlszeile zum Verlauf hinzu, ohne sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-789">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="d8b64-790">Löschen Sie den Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="d8b64-790">Clear the kill-ring.</span></span>  <span data-ttu-id="d8b64-791">Dies wird größtenteils zum Testen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8b64-791">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="d8b64-792">Löschen Sie die Längen Zeichen aus dem Startmenü.</span><span class="sxs-lookup"><span data-stu-id="d8b64-792">Delete length characters from start.</span></span>  <span data-ttu-id="d8b64-793">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-793">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="d8b64-794">Führen Sie die Aktion "Ding" basierend auf der Benutzereinstellung aus.</span><span class="sxs-lookup"><span data-stu-id="d8b64-794">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="d8b64-795">Diese beiden Funktionen rufen nützliche Informationen über den aktuellen Status des Eingabe Puffers ab.</span><span class="sxs-lookup"><span data-stu-id="d8b64-795">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="d8b64-796">Der erste wird häufiger für einfache Fälle verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8b64-796">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="d8b64-797">Die zweite wird verwendet, wenn ihre Bindung einen fortgeschrittenen Vorgang mit der AST bewirkt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-797">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="d8b64-798">Diese Funktion wird von Get-PSReadLineKeyHandler verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht nützlich.</span><span class="sxs-lookup"><span data-stu-id="d8b64-798">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="d8b64-799">Diese Funktion wird von Get-PSReadLineOption verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.</span><span class="sxs-lookup"><span data-stu-id="d8b64-799">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="d8b64-800">Wenn in der Befehlszeile keine Auswahl vorhanden ist, wird-1 sowohl in Start als auch in der Länge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-800">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="d8b64-801">Wenn eine Auswahl in der Befehlszeile vorhanden ist, werden Start und Länge der Auswahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-801">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="d8b64-802">Fügen Sie am Cursor ein Zeichen oder eine Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="d8b64-802">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="d8b64-803">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-803">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="d8b64-804">Dies ist der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="d8b64-804">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="d8b64-805">Sie unterstützt keine Rekursion und ist daher in einer benutzerdefinierten schlüsselbindung nicht nützlich.</span><span class="sxs-lookup"><span data-stu-id="d8b64-805">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="d8b64-806">Diese Funktion wird von Remove-PSReadLineKeyHandler verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.</span><span class="sxs-lookup"><span data-stu-id="d8b64-806">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="d8b64-807">Ersetzen Sie einige der Eingaben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-807">Replace some of the input.</span></span> <span data-ttu-id="d8b64-808">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-808">This operation supports undo/redo.</span></span> <span data-ttu-id="d8b64-809">Dies wird als "Delete", gefolgt von INSERT, bevorzugt, da es als einzelne Aktion für "Rückgängig" behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="d8b64-809">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="d8b64-810">Bewegen Sie den Cursor in den angegebenen Offset.</span><span class="sxs-lookup"><span data-stu-id="d8b64-810">Move the cursor to the given offset.</span></span> <span data-ttu-id="d8b64-811">Cursor Bewegung wird nicht für Rückgängigmachen nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="d8b64-811">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="d8b64-812">Bei dieser Funktion handelt es sich um eine Hilfsmethode, die vom Cmdlet Set-psread lineoption verwendet wird. Sie kann jedoch für eine benutzerdefinierte schlüsselbindung nützlich sein, die eine Einstellung vorübergehend ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="d8b64-812">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="d8b64-813">Diese Hilfsmethode wird für benutzerdefinierte Bindungen verwendet, die digitargument berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-813">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="d8b64-814">Ein typischer-Rückruf sieht wie folgt aus</span><span class="sxs-lookup"><span data-stu-id="d8b64-814">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="d8b64-815">Hinweis</span><span class="sxs-lookup"><span data-stu-id="d8b64-815">Note</span></span>

### <a name="command-history"></a><span data-ttu-id="d8b64-816">Befehlsverlauf</span><span class="sxs-lookup"><span data-stu-id="d8b64-816">Command History</span></span>

<span data-ttu-id="d8b64-817">Psleseline verwaltet eine Verlaufs Datei, die alle Befehle und Daten enthält, die Sie in der Befehlszeile eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="d8b64-817">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="d8b64-818">Dies kann vertrauliche Daten einschließlich Kenn Wörtern enthalten.</span><span class="sxs-lookup"><span data-stu-id="d8b64-818">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="d8b64-819">Wenn Sie z. b. das `ConvertTo-SecureString` Cmdlet verwenden, wird das Kennwort als nur-Text in der Verlaufs Datei protokolliert.</span><span class="sxs-lookup"><span data-stu-id="d8b64-819">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="d8b64-820">Die Verlaufs Dateien sind eine Datei mit dem Namen `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="d8b64-820">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="d8b64-821">Auf Windows-Systemen wird die Verlaufs Datei unter gespeichert `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="d8b64-821">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="d8b64-822">Feedback & zu psread Line beitragen</span><span class="sxs-lookup"><span data-stu-id="d8b64-822">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="d8b64-823">Psread Line auf GitHub</span><span class="sxs-lookup"><span data-stu-id="d8b64-823">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="d8b64-824">Sie können auf der GitHub-Seite eine Pull Request einreichen oder Feedback einreichen.</span><span class="sxs-lookup"><span data-stu-id="d8b64-824">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8b64-825">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8b64-825">See Also</span></span>

<span data-ttu-id="d8b64-826">"Psread Line" wird stark von der GNU-Bibliothek für die [Zeilen](https://tiswww.case.edu/php/chet/readline/rltop.html) Übereinstimmung beeinflusst</span><span class="sxs-lookup"><span data-stu-id="d8b64-826">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
