---
description: Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.
keywords: powershell
Locale: en-US
ms.date: 11/16/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über psread Line
ms.openlocfilehash: 6d52bb04118914a9ccca5d3442a9d1915c1c2818
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94692274"
---
# <a name="psreadline"></a><span data-ttu-id="b626b-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="b626b-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="b626b-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="b626b-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="b626b-106">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b626b-106">Short Description</span></span>

<span data-ttu-id="b626b-107">Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="b626b-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="b626b-108">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b626b-108">Long Description</span></span>

<span data-ttu-id="b626b-109">Psleline 2,1 bietet eine leistungsfähige Befehlszeilen Bearbeitungsfunktion für die PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="b626b-109">PSReadLine 2.1 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="b626b-110">Sie bietet:</span><span class="sxs-lookup"><span data-stu-id="b626b-110">It provides:</span></span>

- <span data-ttu-id="b626b-111">Syntax Farbgebung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="b626b-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="b626b-112">Visuelle Hinweise auf Syntax Fehler</span><span class="sxs-lookup"><span data-stu-id="b626b-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="b626b-113">Bessere mehrzeilige Erfahrung (sowohl Bearbeitung als auch Verlauf)</span><span class="sxs-lookup"><span data-stu-id="b626b-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="b626b-114">Anpassbare Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="b626b-114">Customizable key bindings</span></span>
- <span data-ttu-id="b626b-115">Cmd-und Emacs-Modi</span><span class="sxs-lookup"><span data-stu-id="b626b-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="b626b-116">Viele Konfigurationsoptionen</span><span class="sxs-lookup"><span data-stu-id="b626b-116">Many configuration options</span></span>
- <span data-ttu-id="b626b-117">Bash-Stil Vervollständigung (optional im cmd-Modus, Standard im Emacs-Modus)</span><span class="sxs-lookup"><span data-stu-id="b626b-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="b626b-118">Emacs: Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="b626b-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="b626b-119">PowerShell-tokenbasierte "Wort Bewegung" und "Kill"</span><span class="sxs-lookup"><span data-stu-id="b626b-119">PowerShell token based "word" movement and kill</span></span>
- <span data-ttu-id="b626b-120">Predictive IntelliSense</span><span class="sxs-lookup"><span data-stu-id="b626b-120">Predictive IntelliSense</span></span>

<span data-ttu-id="b626b-121">Für psread line sind PowerShell 3,0 oder höher sowie der Konsolen Host erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b626b-121">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="b626b-122">Es funktioniert nicht in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="b626b-122">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="b626b-123">Dies funktioniert in der-Konsole Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="b626b-123">It does work in the console of Visual Studio Code.</span></span>

<span data-ttu-id="b626b-124">Psread Line 2.1.0 wird mit PowerShell 7,1 ausgeliefert und wird in allen unterstützten Versionen von PowerShell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b626b-124">PSReadLine 2.1.0 ships with PowerShell 7.1 and is supported in all supported versions of PowerShell.</span></span> <span data-ttu-id="b626b-125">Es ist für die Installation über das PowerShell-Katalog verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b626b-125">It is available to install from the PowerShell Gallery.</span></span>
<span data-ttu-id="b626b-126">Führen Sie den folgenden Befehl aus, um psread Line 2.1.0 in einer unterstützten Version von PowerShell zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b626b-126">To install PSReadLine 2.1.0 in a supported version of PowerShell run the following command.</span></span>

```powershell
Install-Module -Name PSReadLine -RequiredVersion 2.1.0
```

> [!NOTE]
> <span data-ttu-id="b626b-127">Ab PowerShell 7,0 überspringt PowerShell das automatische Laden von psleseline unter Windows, wenn ein Bildschirm Leseprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="b626b-127">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="b626b-128">Derzeit funktioniert psread Line nicht gut mit den Bildschirmlesern.</span><span class="sxs-lookup"><span data-stu-id="b626b-128">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="b626b-129">Das Standard Rendering und die Formatierung von PowerShell 7,0 unter Windows funktionieren ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="b626b-129">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="b626b-130">Sie können das Modul ggf. manuell laden.</span><span class="sxs-lookup"><span data-stu-id="b626b-130">You can manually load the module if necessary.</span></span>

## <a name="predictive-intellisense"></a><span data-ttu-id="b626b-131">Predictive IntelliSense</span><span class="sxs-lookup"><span data-stu-id="b626b-131">Predictive IntelliSense</span></span>

<span data-ttu-id="b626b-132">Predictive IntelliSense ist eine Ergänzung zum Konzept der Vervollständigung mit der Tab-Taste, die dem Benutzer hilft, Befehle erfolgreich abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b626b-132">Predictive IntelliSense is an addition to the concept of tab completion that assists the user in successfully completing commands.</span></span> <span data-ttu-id="b626b-133">Sie ermöglicht Benutzern das ermitteln, bearbeiten und ausführen vollständiger Befehle basierend auf übereinstimmenden Vorhersagen aus dem Verlauf des Benutzers und zusätzlichen domänenspezifischen Plug-ins.</span><span class="sxs-lookup"><span data-stu-id="b626b-133">It enables users to discover, edit, and execute full commands based on matching predictions from the user's history and additional domain specific plugins.</span></span>

### <a name="enable-predictive-intellisense"></a><span data-ttu-id="b626b-134">Aktivieren von Predictive IntelliSense</span><span class="sxs-lookup"><span data-stu-id="b626b-134">Enable Predictive IntelliSense</span></span>

<span data-ttu-id="b626b-135">Predictive IntelliSense ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b626b-135">Predictive IntelliSense is disabled by default.</span></span> <span data-ttu-id="b626b-136">Um Vorhersagen zu aktivieren, führen Sie einfach den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b626b-136">To enable predictions, just run the following command:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource History
```

<span data-ttu-id="b626b-137">Der Parameter " **prätionsource** " kann auch Plug-Ins für domänenspezifische und benutzerdefinierte Anforderungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="b626b-137">The **PredictionSource** parameter can also accept plugins for domain specific and custom requirements.</span></span>

<span data-ttu-id="b626b-138">Um Predictive IntelliSense zu deaktivieren, führen Sie einfach Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="b626b-138">To disable Predictive IntelliSense, just run:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource None
```

<span data-ttu-id="b626b-139">Die folgenden Funktionen sind in der-Klasse **[Microsoft. PowerShell. psconsolereadline]** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b626b-139">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="b626b-140">Grundlegende Bearbeitungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="b626b-140">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="b626b-141">Abbruch</span><span class="sxs-lookup"><span data-stu-id="b626b-141">Abort</span></span>

<span data-ttu-id="b626b-142">Abbrechen der aktuellen Aktion, z.b. inkrementelle Verlaufs Suche.</span><span class="sxs-lookup"><span data-stu-id="b626b-142">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="b626b-143">Ansehen `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="b626b-143">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="b626b-144">Akzeptandgetnext</span><span class="sxs-lookup"><span data-stu-id="b626b-144">AcceptAndGetNext</span></span>

<span data-ttu-id="b626b-145">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b626b-145">Attempt to execute the current input.</span></span> <span data-ttu-id="b626b-146">Wenn Sie ausgeführt werden kann (wie z. b. Accept Line), erinnern Sie sich beim nächsten Aufruf von "read line" an das nächste Element aus dem Verlauf.</span><span class="sxs-lookup"><span data-stu-id="b626b-146">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="b626b-147">Ansehen `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="b626b-147">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="b626b-148">Annahme</span><span class="sxs-lookup"><span data-stu-id="b626b-148">AcceptLine</span></span>

<span data-ttu-id="b626b-149">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b626b-149">Attempt to execute the current input.</span></span> <span data-ttu-id="b626b-150">Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b626b-150">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="b626b-151">Befehl: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="b626b-151">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="b626b-152">Ansehen `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="b626b-152">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="b626b-153">VI-Einfügemodus: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="b626b-153">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="b626b-154">AddLine</span><span class="sxs-lookup"><span data-stu-id="b626b-154">AddLine</span></span>

<span data-ttu-id="b626b-155">Die Fortsetzungs Aufforderung wird in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b626b-155">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="b626b-156">Dies ist nützlich, um mehrzeilige Eingaben als einen einzelnen Befehl einzugeben, auch wenn eine einzelne Zeile allein eine Eingabe ist.</span><span class="sxs-lookup"><span data-stu-id="b626b-156">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="b626b-157">Befehl: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="b626b-157">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="b626b-158">Ansehen `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="b626b-158">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="b626b-159">VI-Einfügemodus: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="b626b-159">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="b626b-160">VI-Befehlsmodus: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="b626b-160">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="b626b-161">Backwarddeletechar</span><span class="sxs-lookup"><span data-stu-id="b626b-161">BackwardDeleteChar</span></span>

<span data-ttu-id="b626b-162">Löschen Sie das Zeichen vor dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="b626b-162">Delete the character before the cursor.</span></span>

- <span data-ttu-id="b626b-163">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="b626b-163">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="b626b-164">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="b626b-164">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="b626b-165">VI-Einfügemodus: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="b626b-165">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="b626b-166">VI-Befehlsmodus: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="b626b-166">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="b626b-167">Backwarddelta-Eline</span><span class="sxs-lookup"><span data-stu-id="b626b-167">BackwardDeleteLine</span></span>

<span data-ttu-id="b626b-168">Wie backwardkillline löscht Text vom Punkt bis zum Anfang der Zeile, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b626b-168">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="b626b-169">Befehl: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="b626b-169">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="b626b-170">VI-Einfügemodus: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="b626b-170">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="b626b-171">VI-Befehlsmodus: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="b626b-171">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="b626b-172">Backwarddeleteword</span><span class="sxs-lookup"><span data-stu-id="b626b-172">BackwardDeleteWord</span></span>

<span data-ttu-id="b626b-173">Löscht das vorherige Wort.</span><span class="sxs-lookup"><span data-stu-id="b626b-173">Deletes the previous word.</span></span>

- <span data-ttu-id="b626b-174">VI-Befehlsmodus: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="b626b-174">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="b626b-175">Backwardkillline</span><span class="sxs-lookup"><span data-stu-id="b626b-175">BackwardKillLine</span></span>

<span data-ttu-id="b626b-176">Löschen Sie die Eingabe vom Beginn der Eingabe in den Cursor.</span><span class="sxs-lookup"><span data-stu-id="b626b-176">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="b626b-177">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b626b-177">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="b626b-178">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="b626b-178">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="b626b-179">Backwardkillword</span><span class="sxs-lookup"><span data-stu-id="b626b-179">BackwardKillWord</span></span>

<span data-ttu-id="b626b-180">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="b626b-180">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="b626b-181">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b626b-181">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="b626b-182">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b626b-182">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="b626b-183">Cmd: `<Ctrl+Backspace>` , `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="b626b-183">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="b626b-184">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="b626b-184">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="b626b-185">VI-Einfügemodus: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="b626b-185">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="b626b-186">VI-Befehlsmodus: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="b626b-186">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="b626b-187">Cancelline</span><span class="sxs-lookup"><span data-stu-id="b626b-187">CancelLine</span></span>

<span data-ttu-id="b626b-188">Brechen Sie die aktuelle Eingabe ab, belassen Sie die Eingabe auf dem Bildschirm, kehren Sie jedoch zurück zum Host, damit die Eingabeaufforderung erneut ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="b626b-188">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="b626b-189">VI-Einfügemodus: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="b626b-189">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="b626b-190">VI-Befehlsmodus: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="b626b-190">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="b626b-191">Kopieren</span><span class="sxs-lookup"><span data-stu-id="b626b-191">Copy</span></span>

<span data-ttu-id="b626b-192">Kopiert den ausgewählten Bereich in die Zwischenablage des Systems.</span><span class="sxs-lookup"><span data-stu-id="b626b-192">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="b626b-193">Wenn keine Region ausgewählt ist, kopieren Sie die gesamte Zeile.</span><span class="sxs-lookup"><span data-stu-id="b626b-193">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="b626b-194">Befehl: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="b626b-194">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="b626b-195">Copyorcancelline</span><span class="sxs-lookup"><span data-stu-id="b626b-195">CopyOrCancelLine</span></span>

<span data-ttu-id="b626b-196">Wenn Text ausgewählt ist, kopieren Sie ihn in die Zwischenablage, andernfalls brechen Sie die Zeile ab.</span><span class="sxs-lookup"><span data-stu-id="b626b-196">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="b626b-197">Befehl: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="b626b-197">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="b626b-198">Ansehen `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="b626b-198">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="b626b-199">Ausschneiden</span><span class="sxs-lookup"><span data-stu-id="b626b-199">Cut</span></span>

<span data-ttu-id="b626b-200">Löscht die ausgewählte Region, in der Gelöschter Text in der Zwischenablage des Systems</span><span class="sxs-lookup"><span data-stu-id="b626b-200">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="b626b-201">Befehl: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="b626b-201">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="b626b-202">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="b626b-202">DeleteChar</span></span>

<span data-ttu-id="b626b-203">Löschen Sie das Zeichen unter dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="b626b-203">Delete the character under the cursor.</span></span>

- <span data-ttu-id="b626b-204">Befehl: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="b626b-204">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="b626b-205">Ansehen `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="b626b-205">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="b626b-206">VI-Einfügemodus: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="b626b-206">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="b626b-207">VI-Befehlsmodus: `<Delete>` , `<x>` , `<d,l>` , `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="b626b-207">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="b626b-208">Deletecharorexit</span><span class="sxs-lookup"><span data-stu-id="b626b-208">DeleteCharOrExit</span></span>

<span data-ttu-id="b626b-209">Löschen Sie das Zeichen unter dem Cursor, oder beenden Sie den Prozess, wenn die Zeile leer ist.</span><span class="sxs-lookup"><span data-stu-id="b626b-209">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="b626b-210">Ansehen `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="b626b-210">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="b626b-211">Deleteendof Buffer</span><span class="sxs-lookup"><span data-stu-id="b626b-211">DeleteEndOfBuffer</span></span>

<span data-ttu-id="b626b-212">Löscht bis zum Ende des mehrzeiligen Puffers.</span><span class="sxs-lookup"><span data-stu-id="b626b-212">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="b626b-213">VI-Befehlsmodus: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="b626b-213">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="b626b-214">Deleteendof</span><span class="sxs-lookup"><span data-stu-id="b626b-214">DeleteEndOfWord</span></span>

<span data-ttu-id="b626b-215">Bis zum Ende des Worts löschen.</span><span class="sxs-lookup"><span data-stu-id="b626b-215">Delete to the end of the word.</span></span>

- <span data-ttu-id="b626b-216">VI-Befehlsmodus: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="b626b-216">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="b626b-217">"Deleteline</span><span class="sxs-lookup"><span data-stu-id="b626b-217">DeleteLine</span></span>

<span data-ttu-id="b626b-218">Löscht die aktuelle logische Zeile eines mehrzeiligen Puffers und ermöglicht Rückgängigmachen.</span><span class="sxs-lookup"><span data-stu-id="b626b-218">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="b626b-219">VI-Befehlsmodus: `<d,d>` , `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="b626b-219">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="b626b-220">Deletepreviouslines</span><span class="sxs-lookup"><span data-stu-id="b626b-220">DeletePreviousLines</span></span>

<span data-ttu-id="b626b-221">Löscht die vorherigen angeforderten logischen Zeilen und die aktuelle logische Zeile in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="b626b-221">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="b626b-222">VI-Befehlsmodus: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="b626b-222">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="b626b-223">Deleterelativelines</span><span class="sxs-lookup"><span data-stu-id="b626b-223">DeleteRelativeLines</span></span>

<span data-ttu-id="b626b-224">Löscht vom Anfang des Puffers in die aktuelle logische Zeile in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="b626b-224">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="b626b-225">Bei den meisten VI-Befehlen `<d,g,g>` kann dem Befehl ein numerisches Argument vorangestellt werden, das eine absolute Zeilennummer angibt, die in Verbindung mit der aktuellen Zeilennummer einen Bereich von Zeilen bilden, die gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b626b-225">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="b626b-226">Wenn kein Wert angegeben wird, wird das numerische Argument standardmäßig auf 1 festgelegt. Dies bezieht sich auf die erste logische Zeile in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="b626b-226">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="b626b-227">Die tatsächliche Anzahl von Zeilen, die aus der mehrzeiligen Zeile gelöscht werden sollen, wird als Differenz zwischen der aktuellen logischen Zeilennummer und dem angegebenen numerischen Argument berechnet, das daher negativ sein kann.</span><span class="sxs-lookup"><span data-stu-id="b626b-227">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="b626b-228">Daher der _relative_ Teil des Methoden namens.</span><span class="sxs-lookup"><span data-stu-id="b626b-228">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="b626b-229">VI-Befehlsmodus: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="b626b-229">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="b626b-230">Deletenextlines</span><span class="sxs-lookup"><span data-stu-id="b626b-230">DeleteNextLines</span></span>

<span data-ttu-id="b626b-231">Löscht die aktuelle logische Linie und die nächsten angeforderten logischen Zeilen in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="b626b-231">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="b626b-232">VI-Befehlsmodus: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="b626b-232">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="b626b-233">Delta-inetyp</span><span class="sxs-lookup"><span data-stu-id="b626b-233">DeleteLineToFirstChar</span></span>

<span data-ttu-id="b626b-234">Löscht Text vom Cursor zum ersten Zeichen der Zeile, das nicht leer ist.</span><span class="sxs-lookup"><span data-stu-id="b626b-234">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="b626b-235">VI-Befehlsmodus: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="b626b-235">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="b626b-236">Deletegeend</span><span class="sxs-lookup"><span data-stu-id="b626b-236">DeleteToEnd</span></span>

<span data-ttu-id="b626b-237">Bis zum Ende der Zeile löschen.</span><span class="sxs-lookup"><span data-stu-id="b626b-237">Delete to the end of the line.</span></span>

- <span data-ttu-id="b626b-238">VI-Befehlsmodus: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="b626b-238">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="b626b-239">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="b626b-239">DeleteWord</span></span>

<span data-ttu-id="b626b-240">Löschen Sie das nächste Wort.</span><span class="sxs-lookup"><span data-stu-id="b626b-240">Delete the next word.</span></span>

- <span data-ttu-id="b626b-241">VI-Befehlsmodus: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="b626b-241">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="b626b-242">Forwarddelta-Eline</span><span class="sxs-lookup"><span data-stu-id="b626b-242">ForwardDeleteLine</span></span>

<span data-ttu-id="b626b-243">Wie forwardkillline löscht Text vom Punkt bis zum Ende der Zeile, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b626b-243">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="b626b-244">Befehl: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="b626b-244">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="b626b-245">VI-Einfügemodus: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="b626b-245">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="b626b-246">VI-Befehlsmodus: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="b626b-246">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="b626b-247">Insertlineoberhalb</span><span class="sxs-lookup"><span data-stu-id="b626b-247">InsertLineAbove</span></span>

<span data-ttu-id="b626b-248">Oberhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="b626b-248">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="b626b-249">Der Cursor wechselt zum Anfang der neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="b626b-249">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="b626b-250">Befehl: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="b626b-250">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="b626b-251">Insertlinebelow</span><span class="sxs-lookup"><span data-stu-id="b626b-251">InsertLineBelow</span></span>

<span data-ttu-id="b626b-252">Unterhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="b626b-252">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="b626b-253">Der Cursor wechselt zum Anfang der neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="b626b-253">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="b626b-254">Befehl: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="b626b-254">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="b626b-255">Invertieren</span><span class="sxs-lookup"><span data-stu-id="b626b-255">InvertCase</span></span>

<span data-ttu-id="b626b-256">Kehrt die Groß-/Kleinschreibung des aktuellen Zeichens um und wechselt zum nächsten.</span><span class="sxs-lookup"><span data-stu-id="b626b-256">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="b626b-257">VI-Befehlsmodus: `<~>`</span><span class="sxs-lookup"><span data-stu-id="b626b-257">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="b626b-258">Killline</span><span class="sxs-lookup"><span data-stu-id="b626b-258">KillLine</span></span>

<span data-ttu-id="b626b-259">Löschen Sie die Eingabe vom Cursor bis zum Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="b626b-259">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="b626b-260">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b626b-260">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="b626b-261">Ansehen `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="b626b-261">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="b626b-262">Killregion</span><span class="sxs-lookup"><span data-stu-id="b626b-262">KillRegion</span></span>

<span data-ttu-id="b626b-263">Beenden Sie den Text zwischen dem Cursor und der Markierung.</span><span class="sxs-lookup"><span data-stu-id="b626b-263">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="b626b-264">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-264">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="b626b-265">Killword</span><span class="sxs-lookup"><span data-stu-id="b626b-265">KillWord</span></span>

<span data-ttu-id="b626b-266">Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts.</span><span class="sxs-lookup"><span data-stu-id="b626b-266">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="b626b-267">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b626b-267">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="b626b-268">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b626b-268">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="b626b-269">Cmd: `<Alt+d>` , `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="b626b-269">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="b626b-270">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="b626b-270">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="b626b-271">VI-Einfügemodus: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="b626b-271">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="b626b-272">VI-Befehlsmodus: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="b626b-272">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="b626b-273">Einfügen</span><span class="sxs-lookup"><span data-stu-id="b626b-273">Paste</span></span>

<span data-ttu-id="b626b-274">Fügen Sie Text aus der Zwischenablage des Systems ein.</span><span class="sxs-lookup"><span data-stu-id="b626b-274">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="b626b-275">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="b626b-275">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="b626b-276">VI-Einfügemodus: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="b626b-276">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="b626b-277">VI-Befehlsmodus: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="b626b-277">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b626b-278">Wenn Sie die Funktion **Einfügen** verwenden, wird der gesamte Inhalt des Zwischenablage Puffers in den Eingabepuffer von psread Line eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b626b-278">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="b626b-279">Der Eingabepuffer wird dann an den PowerShell-Parser übergeben.</span><span class="sxs-lookup"><span data-stu-id="b626b-279">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="b626b-280">Eingaben, die mithilfe der **Rechtsklick-Einfügemethode** der Konsolenanwendung eingefügt werden, werden jeweils ein Zeichen in den Eingabepuffer kopiert.</span><span class="sxs-lookup"><span data-stu-id="b626b-280">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="b626b-281">Der Eingabepuffer wird an den Parser übergeben, wenn ein Zeilen vorzeichensatz kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="b626b-281">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="b626b-282">Daher wird die Eingabe jeweils Zeilen gleich analysiert.</span><span class="sxs-lookup"><span data-stu-id="b626b-282">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="b626b-283">Der Unterschied zwischen den Methoden zum Einfügen führt zu einem anderen Ausführungs Verhalten.</span><span class="sxs-lookup"><span data-stu-id="b626b-283">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="b626b-284">Pasteafter</span><span class="sxs-lookup"><span data-stu-id="b626b-284">PasteAfter</span></span>

<span data-ttu-id="b626b-285">Fügen Sie die Zwischenablage nach dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.</span><span class="sxs-lookup"><span data-stu-id="b626b-285">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="b626b-286">VI-Befehlsmodus: `<p>`</span><span class="sxs-lookup"><span data-stu-id="b626b-286">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="b626b-287">Pastebefore</span><span class="sxs-lookup"><span data-stu-id="b626b-287">PasteBefore</span></span>

<span data-ttu-id="b626b-288">Fügen Sie die Zwischenablage vor dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.</span><span class="sxs-lookup"><span data-stu-id="b626b-288">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="b626b-289">VI-Befehlsmodus: `<P>`</span><span class="sxs-lookup"><span data-stu-id="b626b-289">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="b626b-290">Prepdandaccept</span><span class="sxs-lookup"><span data-stu-id="b626b-290">PrependAndAccept</span></span>

<span data-ttu-id="b626b-291">Fügen Sie ein "#" vorangesteht, und akzeptieren Sie die Zeile.</span><span class="sxs-lookup"><span data-stu-id="b626b-291">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="b626b-292">VI-Befehlsmodus: `<#>`</span><span class="sxs-lookup"><span data-stu-id="b626b-292">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="b626b-293">Wiederholen</span><span class="sxs-lookup"><span data-stu-id="b626b-293">Redo</span></span>

<span data-ttu-id="b626b-294">Rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="b626b-294">Undo an undo.</span></span>

- <span data-ttu-id="b626b-295">Befehl: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="b626b-295">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="b626b-296">VI-Einfügemodus: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="b626b-296">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="b626b-297">VI-Befehlsmodus: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="b626b-297">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="b626b-298">Repeatlastcommand</span><span class="sxs-lookup"><span data-stu-id="b626b-298">RepeatLastCommand</span></span>

<span data-ttu-id="b626b-299">Wiederholen Sie die letzte Textänderung.</span><span class="sxs-lookup"><span data-stu-id="b626b-299">Repeat the last text modification.</span></span>

- <span data-ttu-id="b626b-300">VI-Befehlsmodus: `<.>`</span><span class="sxs-lookup"><span data-stu-id="b626b-300">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="b626b-301">Revertline</span><span class="sxs-lookup"><span data-stu-id="b626b-301">RevertLine</span></span>

<span data-ttu-id="b626b-302">Kehrt alle Eingaben in die aktuelle Eingabe um.</span><span class="sxs-lookup"><span data-stu-id="b626b-302">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="b626b-303">Befehl: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="b626b-303">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="b626b-304">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="b626b-304">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="b626b-305">Shellbackwardkillword</span><span class="sxs-lookup"><span data-stu-id="b626b-305">ShellBackwardKillWord</span></span>

<span data-ttu-id="b626b-306">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="b626b-306">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="b626b-307">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b626b-307">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="b626b-308">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b626b-308">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="b626b-309">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-309">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="b626b-310">Shellkillword</span><span class="sxs-lookup"><span data-stu-id="b626b-310">ShellKillWord</span></span>

<span data-ttu-id="b626b-311">Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts.</span><span class="sxs-lookup"><span data-stu-id="b626b-311">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="b626b-312">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b626b-312">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="b626b-313">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b626b-313">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="b626b-314">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-314">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="b626b-315">Austausch Zeichen</span><span class="sxs-lookup"><span data-stu-id="b626b-315">SwapCharacters</span></span>

<span data-ttu-id="b626b-316">Tauschen Sie das aktuelle und das aktuelle Zeichen aus.</span><span class="sxs-lookup"><span data-stu-id="b626b-316">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="b626b-317">Ansehen `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="b626b-317">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="b626b-318">VI-Einfügemodus: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="b626b-318">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="b626b-319">VI-Befehlsmodus: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="b626b-319">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="b626b-320">Rückgängig machen</span><span class="sxs-lookup"><span data-stu-id="b626b-320">Undo</span></span>

<span data-ttu-id="b626b-321">Rückgängigmachen einer vorherigen Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="b626b-321">Undo a previous edit.</span></span>

- <span data-ttu-id="b626b-322">Befehl: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="b626b-322">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="b626b-323">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="b626b-323">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="b626b-324">VI-Einfügemodus: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="b626b-324">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="b626b-325">VI-Befehlsmodus: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="b626b-325">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="b626b-326">Nicht doall</span><span class="sxs-lookup"><span data-stu-id="b626b-326">UndoAll</span></span>

<span data-ttu-id="b626b-327">Alle vorherigen Änderungen für die Zeile rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="b626b-327">Undo all previous edits for line.</span></span>

- <span data-ttu-id="b626b-328">VI-Befehlsmodus: `<U>`</span><span class="sxs-lookup"><span data-stu-id="b626b-328">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="b626b-329">Unixwordrubout</span><span class="sxs-lookup"><span data-stu-id="b626b-329">UnixWordRubout</span></span>

<span data-ttu-id="b626b-330">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="b626b-330">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="b626b-331">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b626b-331">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="b626b-332">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b626b-332">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="b626b-333">Ansehen `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="b626b-333">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="b626b-334">Validateandakzeptline</span><span class="sxs-lookup"><span data-stu-id="b626b-334">ValidateAndAcceptLine</span></span>

<span data-ttu-id="b626b-335">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b626b-335">Attempt to execute the current input.</span></span> <span data-ttu-id="b626b-336">Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b626b-336">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="b626b-337">Ansehen `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="b626b-337">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="b626b-338">Viakzeptline</span><span class="sxs-lookup"><span data-stu-id="b626b-338">ViAcceptLine</span></span>

<span data-ttu-id="b626b-339">Akzeptieren Sie die Zeile, und wechseln Sie zum Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="b626b-339">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="b626b-340">VI-Befehlsmodus: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="b626b-340">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="b626b-341">Viakzeptlineorexit</span><span class="sxs-lookup"><span data-stu-id="b626b-341">ViAcceptLineOrExit</span></span>

<span data-ttu-id="b626b-342">Wie deletecharorexit im Emacs-Modus, akzeptiert jedoch die Zeile, anstatt ein Zeichen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b626b-342">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="b626b-343">VI-Einfügemodus: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="b626b-343">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="b626b-344">VI-Befehlsmodus: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="b626b-344">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="b626b-345">Viappendline</span><span class="sxs-lookup"><span data-stu-id="b626b-345">ViAppendLine</span></span>

<span data-ttu-id="b626b-346">Unterhalb der aktuellen Zeile wird eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b626b-346">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="b626b-347">VI-Befehlsmodus: `<o>`</span><span class="sxs-lookup"><span data-stu-id="b626b-347">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="b626b-348">Vibackwarddeleteglob</span><span class="sxs-lookup"><span data-stu-id="b626b-348">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="b626b-349">Löscht das vorherige Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b626b-349">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="b626b-350">VI-Befehlsmodus: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="b626b-350">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="b626b-351">Vibackwardglob</span><span class="sxs-lookup"><span data-stu-id="b626b-351">ViBackwardGlob</span></span>

<span data-ttu-id="b626b-352">Verschiebt den Cursor zurück an den Anfang des vorherigen Worts, wobei nur Leerraum als Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b626b-352">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="b626b-353">VI-Befehlsmodus: `<B>`</span><span class="sxs-lookup"><span data-stu-id="b626b-353">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="b626b-354">Videletebrace</span><span class="sxs-lookup"><span data-stu-id="b626b-354">ViDeleteBrace</span></span>

<span data-ttu-id="b626b-355">Suchen Sie nach der passenden geschweiften Klammer, Klammer oder eckigen Klammer, und löschen Sie alle Inhalte in, einschließlich der geschweiften Klammer.</span><span class="sxs-lookup"><span data-stu-id="b626b-355">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="b626b-356">VI-Befehlsmodus: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="b626b-356">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="b626b-357">Videleteendobglob</span><span class="sxs-lookup"><span data-stu-id="b626b-357">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="b626b-358">Bis zum Ende des Worts löschen.</span><span class="sxs-lookup"><span data-stu-id="b626b-358">Delete to the end of the word.</span></span>

- <span data-ttu-id="b626b-359">VI-Befehlsmodus: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="b626b-359">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="b626b-360">Videleteglob</span><span class="sxs-lookup"><span data-stu-id="b626b-360">ViDeleteGlob</span></span>

<span data-ttu-id="b626b-361">Löschen Sie den nächsten globmuster (Leerzeichen mit Trennzeichen).</span><span class="sxs-lookup"><span data-stu-id="b626b-361">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="b626b-362">VI-Befehlsmodus: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="b626b-362">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="b626b-363">Videletetobeforechar</span><span class="sxs-lookup"><span data-stu-id="b626b-363">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="b626b-364">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b626b-364">Deletes until given character.</span></span>

- <span data-ttu-id="b626b-365">VI-Befehlsmodus: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="b626b-365">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="b626b-366">Videletebackbeforecharrückwärts</span><span class="sxs-lookup"><span data-stu-id="b626b-366">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="b626b-367">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b626b-367">Deletes until given character.</span></span>

- <span data-ttu-id="b626b-368">VI-Befehlsmodus: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="b626b-368">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="b626b-369">Videleteto Char</span><span class="sxs-lookup"><span data-stu-id="b626b-369">ViDeleteToChar</span></span>

<span data-ttu-id="b626b-370">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b626b-370">Deletes until given character.</span></span>

- <span data-ttu-id="b626b-371">VI-Befehlsmodus: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="b626b-371">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="b626b-372">Videletebackcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="b626b-372">ViDeleteToCharBackward</span></span>

<span data-ttu-id="b626b-373">Löscht rückwärts bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b626b-373">Deletes backwards until given character.</span></span>

- <span data-ttu-id="b626b-374">VI-Befehlsmodus: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="b626b-374">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="b626b-375">Viinsertatbeginung</span><span class="sxs-lookup"><span data-stu-id="b626b-375">ViInsertAtBegining</span></span>

<span data-ttu-id="b626b-376">Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Anfang der Zeile.</span><span class="sxs-lookup"><span data-stu-id="b626b-376">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="b626b-377">VI-Befehlsmodus: `<I>`</span><span class="sxs-lookup"><span data-stu-id="b626b-377">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="b626b-378">Viinsertatend</span><span class="sxs-lookup"><span data-stu-id="b626b-378">ViInsertAtEnd</span></span>

<span data-ttu-id="b626b-379">Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Ende der Zeile.</span><span class="sxs-lookup"><span data-stu-id="b626b-379">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="b626b-380">VI-Befehlsmodus: `<A>`</span><span class="sxs-lookup"><span data-stu-id="b626b-380">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="b626b-381">Viinsertline</span><span class="sxs-lookup"><span data-stu-id="b626b-381">ViInsertLine</span></span>

<span data-ttu-id="b626b-382">Oberhalb der aktuellen Zeile wird eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b626b-382">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="b626b-383">VI-Befehlsmodus: `<O>`</span><span class="sxs-lookup"><span data-stu-id="b626b-383">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="b626b-384">Viinsertwithappend</span><span class="sxs-lookup"><span data-stu-id="b626b-384">ViInsertWithAppend</span></span>

<span data-ttu-id="b626b-385">An der aktuellen Zeilen Position anfügen.</span><span class="sxs-lookup"><span data-stu-id="b626b-385">Append from the current line position.</span></span>

- <span data-ttu-id="b626b-386">VI-Befehlsmodus: `<a>`</span><span class="sxs-lookup"><span data-stu-id="b626b-386">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="b626b-387">Viinsertwithdelete</span><span class="sxs-lookup"><span data-stu-id="b626b-387">ViInsertWithDelete</span></span>

<span data-ttu-id="b626b-388">Löschen Sie das aktuelle Zeichen und wechseln Sie in den Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="b626b-388">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="b626b-389">VI-Befehlsmodus: `<s>`</span><span class="sxs-lookup"><span data-stu-id="b626b-389">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="b626b-390">Vijoinlines</span><span class="sxs-lookup"><span data-stu-id="b626b-390">ViJoinLines</span></span>

<span data-ttu-id="b626b-391">Verbindet die aktuelle Zeile und die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="b626b-391">Joins the current line and the next line.</span></span>

- <span data-ttu-id="b626b-392">VI-Befehlsmodus: `<J>`</span><span class="sxs-lookup"><span data-stu-id="b626b-392">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="b626b-393">Vireplaceline</span><span class="sxs-lookup"><span data-stu-id="b626b-393">ViReplaceLine</span></span>

<span data-ttu-id="b626b-394">Löschen Sie die gesamte Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="b626b-394">Erase the entire command line.</span></span>

- <span data-ttu-id="b626b-395">VI-Befehlsmodus: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="b626b-395">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="b626b-396">Vireplacetobeforechar</span><span class="sxs-lookup"><span data-stu-id="b626b-396">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="b626b-397">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b626b-397">Replaces until given character.</span></span>

- <span data-ttu-id="b626b-398">VI-Befehlsmodus: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="b626b-398">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="b626b-399">Vireplaceumbeforecharrückwärts</span><span class="sxs-lookup"><span data-stu-id="b626b-399">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="b626b-400">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b626b-400">Replaces until given character.</span></span>

- <span data-ttu-id="b626b-401">VI-Befehlsmodus: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="b626b-401">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="b626b-402">Vireplaceumchar</span><span class="sxs-lookup"><span data-stu-id="b626b-402">ViReplaceToChar</span></span>

<span data-ttu-id="b626b-403">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b626b-403">Deletes until given character.</span></span>

- <span data-ttu-id="b626b-404">VI-Befehlsmodus: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="b626b-404">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="b626b-405">Vireplacebackcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="b626b-405">ViReplaceToCharBackward</span></span>

<span data-ttu-id="b626b-406">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b626b-406">Replaces until given character.</span></span>

- <span data-ttu-id="b626b-407">VI-Befehlsmodus: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="b626b-407">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="b626b-408">Viyankbeginningosline</span><span class="sxs-lookup"><span data-stu-id="b626b-408">ViYankBeginningOfLine</span></span>

<span data-ttu-id="b626b-409">Yank vom Anfang des Puffers bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="b626b-409">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="b626b-410">VI-Befehlsmodus: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="b626b-410">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="b626b-411">Viyankendobglob</span><span class="sxs-lookup"><span data-stu-id="b626b-411">ViYankEndOfGlob</span></span>

<span data-ttu-id="b626b-412">Yank vom Cursor bis zum Ende des Worts (s).</span><span class="sxs-lookup"><span data-stu-id="b626b-412">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="b626b-413">VI-Befehlsmodus: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="b626b-413">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="b626b-414">Viyankendof</span><span class="sxs-lookup"><span data-stu-id="b626b-414">ViYankEndOfWord</span></span>

<span data-ttu-id="b626b-415">Yank vom Cursor bis zum Ende des Worts (s).</span><span class="sxs-lookup"><span data-stu-id="b626b-415">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="b626b-416">VI-Befehlsmodus: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="b626b-416">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="b626b-417">Viyankleft</span><span class="sxs-lookup"><span data-stu-id="b626b-417">ViYankLeft</span></span>

<span data-ttu-id="b626b-418">Die Zeichen werden Links vom Cursor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b626b-418">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="b626b-419">VI-Befehlsmodus: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="b626b-419">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="b626b-420">Viyankline</span><span class="sxs-lookup"><span data-stu-id="b626b-420">ViYankLine</span></span>

<span data-ttu-id="b626b-421">Den gesamten Puffer.</span><span class="sxs-lookup"><span data-stu-id="b626b-421">Yank the entire buffer.</span></span>

- <span data-ttu-id="b626b-422">VI-Befehlsmodus: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="b626b-422">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="b626b-423">Viyanknextglob</span><span class="sxs-lookup"><span data-stu-id="b626b-423">ViYankNextGlob</span></span>

<span data-ttu-id="b626b-424">Yank vom Cursor bis zum Anfang des nächsten Worts (n).</span><span class="sxs-lookup"><span data-stu-id="b626b-424">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="b626b-425">VI-Befehlsmodus: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="b626b-425">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="b626b-426">Viyanknextword</span><span class="sxs-lookup"><span data-stu-id="b626b-426">ViYankNextWord</span></span>

<span data-ttu-id="b626b-427">Das Wort (e) nach dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="b626b-427">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="b626b-428">VI-Befehlsmodus: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="b626b-428">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="b626b-429">Viyankprozent</span><span class="sxs-lookup"><span data-stu-id="b626b-429">ViYankPercent</span></span>

<span data-ttu-id="b626b-430">Von der entsprechenden geschweiften geschweifter Klammer.</span><span class="sxs-lookup"><span data-stu-id="b626b-430">Yank to/from matching brace.</span></span>

- <span data-ttu-id="b626b-431">VI-Befehlsmodus: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="b626b-431">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="b626b-432">Viyankpreviousglob</span><span class="sxs-lookup"><span data-stu-id="b626b-432">ViYankPreviousGlob</span></span>

<span data-ttu-id="b626b-433">Yank von Anfang des Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="b626b-433">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="b626b-434">VI-Befehlsmodus: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="b626b-434">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="b626b-435">Viyankpreviousword</span><span class="sxs-lookup"><span data-stu-id="b626b-435">ViYankPreviousWord</span></span>

<span data-ttu-id="b626b-436">Das Wort (e) vor dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="b626b-436">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="b626b-437">VI-Befehlsmodus: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="b626b-437">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="b626b-438">Viyankright</span><span class="sxs-lookup"><span data-stu-id="b626b-438">ViYankRight</span></span>

<span data-ttu-id="b626b-439">(E) unter und rechts vom Cursor.</span><span class="sxs-lookup"><span data-stu-id="b626b-439">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="b626b-440">VI-Befehlsmodus: `<y,l>` , `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="b626b-440">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="b626b-441">Viyanktoendosline</span><span class="sxs-lookup"><span data-stu-id="b626b-441">ViYankToEndOfLine</span></span>

<span data-ttu-id="b626b-442">Yank vom Cursor bis zum Ende des Puffers.</span><span class="sxs-lookup"><span data-stu-id="b626b-442">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="b626b-443">VI-Befehlsmodus: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="b626b-443">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="b626b-444">Viyanktofirstchar</span><span class="sxs-lookup"><span data-stu-id="b626b-444">ViYankToFirstChar</span></span>

<span data-ttu-id="b626b-445">Yank vom ersten Zeichen, das kein Leerzeichen ist, bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="b626b-445">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="b626b-446">VI-Befehlsmodus: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="b626b-446">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="b626b-447">Yank</span><span class="sxs-lookup"><span data-stu-id="b626b-447">Yank</span></span>

<span data-ttu-id="b626b-448">Fügen Sie der Eingabe den zuletzt beendeten Text hinzu.</span><span class="sxs-lookup"><span data-stu-id="b626b-448">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="b626b-449">Ansehen `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="b626b-449">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="b626b-450">Yanklastarg</span><span class="sxs-lookup"><span data-stu-id="b626b-450">YankLastArg</span></span>

<span data-ttu-id="b626b-451">Das letzte Argument aus der vorherigen Verlaufs Zeile.</span><span class="sxs-lookup"><span data-stu-id="b626b-451">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="b626b-452">Mit einem Argument verhält sich das erste Mal, wenn es aufgerufen wird, wie yankntharg.</span><span class="sxs-lookup"><span data-stu-id="b626b-452">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="b626b-453">Wenn Sie mehrmals aufgerufen wird, durchläuft Sie stattdessen den Verlauf, und arg legt die Richtung fest (negative Umkehrung der Richtung).</span><span class="sxs-lookup"><span data-stu-id="b626b-453">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="b626b-454">Befehl: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="b626b-454">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="b626b-455">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="b626b-455">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="b626b-456">Yankntharg</span><span class="sxs-lookup"><span data-stu-id="b626b-456">YankNthArg</span></span>

<span data-ttu-id="b626b-457">Yank das erste Argument (nach dem Befehl) aus der vorherigen Verlaufs Zeile.</span><span class="sxs-lookup"><span data-stu-id="b626b-457">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="b626b-458">Bei einem Argument wird das n-te Argument (beginnend bei 0), wenn das Argument negativ ist, mit dem letzten Argument beginnen.</span><span class="sxs-lookup"><span data-stu-id="b626b-458">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="b626b-459">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="b626b-459">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="b626b-460">Yankpop</span><span class="sxs-lookup"><span data-stu-id="b626b-460">YankPop</span></span>

<span data-ttu-id="b626b-461">Wenn der vorherige Vorgang "Yank" oder "yankpop" war, ersetzen Sie den zuvor angezeigten Text durch den nächsten ausgeblendeten Text aus dem Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="b626b-461">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="b626b-462">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="b626b-462">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="b626b-463">Cursor Verschiebungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="b626b-463">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="b626b-464">Backwardchar</span><span class="sxs-lookup"><span data-stu-id="b626b-464">BackwardChar</span></span>

<span data-ttu-id="b626b-465">Bewegen Sie den Cursor um ein Zeichen nach links.</span><span class="sxs-lookup"><span data-stu-id="b626b-465">Move the cursor one character to the left.</span></span> <span data-ttu-id="b626b-466">Dadurch kann der Cursor in die vorherige Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b626b-466">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="b626b-467">Befehl: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-467">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="b626b-468">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="b626b-468">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="b626b-469">Backwardword</span><span class="sxs-lookup"><span data-stu-id="b626b-469">BackwardWord</span></span>

<span data-ttu-id="b626b-470">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="b626b-470">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="b626b-471">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="b626b-471">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="b626b-472">Befehl: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-472">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="b626b-473">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="b626b-473">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="b626b-474">VI-Einfügemodus: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-474">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="b626b-475">VI-Befehlsmodus: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-475">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="b626b-476">Beginningosline</span><span class="sxs-lookup"><span data-stu-id="b626b-476">BeginningOfLine</span></span>

<span data-ttu-id="b626b-477">Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Anfang der aktuellen Zeile oder, wenn Sie sich bereits am Anfang der Zeile befinden, bis zum Anfang der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="b626b-477">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="b626b-478">Wenn die Eingabe über eine einzelne Zeile verfügt, wechseln Sie zum Anfang der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="b626b-478">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="b626b-479">Befehl: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="b626b-479">Cmd: `<Home>`</span></span>
- <span data-ttu-id="b626b-480">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="b626b-480">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="b626b-481">VI-Einfügemodus: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="b626b-481">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="b626b-482">VI-Befehlsmodus: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="b626b-482">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="b626b-483">Endosline</span><span class="sxs-lookup"><span data-stu-id="b626b-483">EndOfLine</span></span>

<span data-ttu-id="b626b-484">Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Ende der aktuellen Zeile, oder wechseln Sie, wenn Sie sich bereits am Ende der Zeile befindet, bis zum Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="b626b-484">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="b626b-485">Wenn die Eingabe über eine einzelne Zeile verfügt, verschieben Sie das Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="b626b-485">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="b626b-486">Befehl: `<End>`</span><span class="sxs-lookup"><span data-stu-id="b626b-486">Cmd: `<End>`</span></span>
- <span data-ttu-id="b626b-487">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="b626b-487">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="b626b-488">VI-Einfügemodus: `<End>`</span><span class="sxs-lookup"><span data-stu-id="b626b-488">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="b626b-489">Forwardchar</span><span class="sxs-lookup"><span data-stu-id="b626b-489">ForwardChar</span></span>

<span data-ttu-id="b626b-490">Bewegen Sie den Cursor um ein Zeichen nach rechts.</span><span class="sxs-lookup"><span data-stu-id="b626b-490">Move the cursor one character to the right.</span></span> <span data-ttu-id="b626b-491">Dadurch kann der Cursor in die nächste Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b626b-491">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="b626b-492">Befehl: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-492">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="b626b-493">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="b626b-493">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="b626b-494">Forwardword</span><span class="sxs-lookup"><span data-stu-id="b626b-494">ForwardWord</span></span>

<span data-ttu-id="b626b-495">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="b626b-495">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="b626b-496">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="b626b-496">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="b626b-497">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="b626b-497">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="b626b-498">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="b626b-498">GotoBrace</span></span>

<span data-ttu-id="b626b-499">Wechseln Sie zur passenden geschweiften Klammer, Klammer oder eckigen Klammer.</span><span class="sxs-lookup"><span data-stu-id="b626b-499">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="b626b-500">Befehl: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="b626b-500">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="b626b-501">VI-Einfügemodus: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="b626b-501">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="b626b-502">VI-Befehlsmodus: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="b626b-502">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="b626b-503">Goum Column</span><span class="sxs-lookup"><span data-stu-id="b626b-503">GotoColumn</span></span>

<span data-ttu-id="b626b-504">Wechseln Sie in die Spalte, die von arg angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b626b-504">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="b626b-505">VI-Befehlsmodus: `<|>`</span><span class="sxs-lookup"><span data-stu-id="b626b-505">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="b626b-506">Gostarfirstnonblankosline</span><span class="sxs-lookup"><span data-stu-id="b626b-506">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="b626b-507">Bewegen Sie den Cursor auf das erste nicht leere Zeichen in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="b626b-507">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="b626b-508">VI-Befehlsmodus: `<^>` , `<_>`</span><span class="sxs-lookup"><span data-stu-id="b626b-508">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="b626b-509">"MUVE"</span><span class="sxs-lookup"><span data-stu-id="b626b-509">MoveToEndOfLine</span></span>

<span data-ttu-id="b626b-510">Bewegen Sie den Cursor an das Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="b626b-510">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="b626b-511">VI-Befehlsmodus: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="b626b-511">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="b626b-512">Nextline</span><span class="sxs-lookup"><span data-stu-id="b626b-512">NextLine</span></span>

<span data-ttu-id="b626b-513">Bewegen Sie den Cursor in die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="b626b-513">Move the cursor to the next line.</span></span>

- <span data-ttu-id="b626b-514">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-514">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="b626b-515">Nextword</span><span class="sxs-lookup"><span data-stu-id="b626b-515">NextWord</span></span>

<span data-ttu-id="b626b-516">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="b626b-516">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="b626b-517">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="b626b-517">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="b626b-518">Befehl: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-518">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="b626b-519">VI-Einfügemodus: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-519">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="b626b-520">VI-Befehlsmodus: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-520">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="b626b-521">Nextwordend</span><span class="sxs-lookup"><span data-stu-id="b626b-521">NextWordEnd</span></span>

<span data-ttu-id="b626b-522">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="b626b-522">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="b626b-523">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="b626b-523">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="b626b-524">VI-Befehlsmodus: `<e>`</span><span class="sxs-lookup"><span data-stu-id="b626b-524">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="b626b-525">Previousline</span><span class="sxs-lookup"><span data-stu-id="b626b-525">PreviousLine</span></span>

<span data-ttu-id="b626b-526">Bewegen Sie den Cursor in die vorherige Zeile.</span><span class="sxs-lookup"><span data-stu-id="b626b-526">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="b626b-527">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-527">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="b626b-528">Shellbackwardword</span><span class="sxs-lookup"><span data-stu-id="b626b-528">ShellBackwardWord</span></span>

<span data-ttu-id="b626b-529">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="b626b-529">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="b626b-530">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="b626b-530">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="b626b-531">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-531">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="b626b-532">Shellforwardword</span><span class="sxs-lookup"><span data-stu-id="b626b-532">ShellForwardWord</span></span>

<span data-ttu-id="b626b-533">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="b626b-533">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="b626b-534">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="b626b-534">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="b626b-535">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-535">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="b626b-536">Shellnextword</span><span class="sxs-lookup"><span data-stu-id="b626b-536">ShellNextWord</span></span>

<span data-ttu-id="b626b-537">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="b626b-537">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="b626b-538">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="b626b-538">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="b626b-539">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-539">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="b626b-540">Vibackwardchar</span><span class="sxs-lookup"><span data-stu-id="b626b-540">ViBackwardChar</span></span>

<span data-ttu-id="b626b-541">Bewegen Sie den Cursor um ein Zeichen nach links im VI-Bearbeitungsmodus.</span><span class="sxs-lookup"><span data-stu-id="b626b-541">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="b626b-542">Dadurch kann der Cursor in die vorherige Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b626b-542">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="b626b-543">VI-Einfügemodus: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-543">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="b626b-544">VI-Befehlsmodus: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="b626b-544">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="b626b-545">Vibackwardword</span><span class="sxs-lookup"><span data-stu-id="b626b-545">ViBackwardWord</span></span>

<span data-ttu-id="b626b-546">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="b626b-546">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="b626b-547">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="b626b-547">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="b626b-548">VI-Befehlsmodus: `<b>`</span><span class="sxs-lookup"><span data-stu-id="b626b-548">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="b626b-549">Viforwardchar</span><span class="sxs-lookup"><span data-stu-id="b626b-549">ViForwardChar</span></span>

<span data-ttu-id="b626b-550">Bewegen Sie den Cursor um ein Zeichen nach rechts im VI-Bearbeitungsmodus.</span><span class="sxs-lookup"><span data-stu-id="b626b-550">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="b626b-551">Dadurch kann der Cursor in die nächste Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b626b-551">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="b626b-552">VI-Einfügemodus: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-552">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="b626b-553">VI-Befehlsmodus: `<RightArrow>` , `<Spacebar>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="b626b-553">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="b626b-554">Viendobglob</span><span class="sxs-lookup"><span data-stu-id="b626b-554">ViEndOfGlob</span></span>

<span data-ttu-id="b626b-555">Verschiebt den Cursor an das Ende des Worts und verwendet nur Leerzeichen als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="b626b-555">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="b626b-556">VI-Befehlsmodus: `<E>`</span><span class="sxs-lookup"><span data-stu-id="b626b-556">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="b626b-557">Viendof previousglob</span><span class="sxs-lookup"><span data-stu-id="b626b-557">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="b626b-558">Wechselt zum Ende des vorherigen Worts, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b626b-558">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="b626b-559">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-559">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="b626b-560">Vigoumbrace</span><span class="sxs-lookup"><span data-stu-id="b626b-560">ViGotoBrace</span></span>

<span data-ttu-id="b626b-561">Ähnelt gotobrace, aber ist Zeichen basiert anstelle von tokenbasiert.</span><span class="sxs-lookup"><span data-stu-id="b626b-561">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="b626b-562">VI-Befehlsmodus: `<%>`</span><span class="sxs-lookup"><span data-stu-id="b626b-562">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="b626b-563">Vinextglob</span><span class="sxs-lookup"><span data-stu-id="b626b-563">ViNextGlob</span></span>

<span data-ttu-id="b626b-564">Wechselt zum nächsten Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b626b-564">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="b626b-565">VI-Befehlsmodus: `<W>`</span><span class="sxs-lookup"><span data-stu-id="b626b-565">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="b626b-566">Vinextword</span><span class="sxs-lookup"><span data-stu-id="b626b-566">ViNextWord</span></span>

<span data-ttu-id="b626b-567">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="b626b-567">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="b626b-568">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="b626b-568">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="b626b-569">VI-Befehlsmodus: `<w>`</span><span class="sxs-lookup"><span data-stu-id="b626b-569">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="b626b-570">Verlaufs Funktionen</span><span class="sxs-lookup"><span data-stu-id="b626b-570">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="b626b-571">Beginningof History</span><span class="sxs-lookup"><span data-stu-id="b626b-571">BeginningOfHistory</span></span>

<span data-ttu-id="b626b-572">Wechselt zum ersten Element im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="b626b-572">Move to the first item in the history.</span></span>

- <span data-ttu-id="b626b-573">Ansehen `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="b626b-573">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="b626b-574">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="b626b-574">ClearHistory</span></span>

<span data-ttu-id="b626b-575">Löscht den Verlauf in psleline.</span><span class="sxs-lookup"><span data-stu-id="b626b-575">Clears history in PSReadLine.</span></span> <span data-ttu-id="b626b-576">Dies wirkt sich nicht auf den PowerShell-Verlauf aus.</span><span class="sxs-lookup"><span data-stu-id="b626b-576">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="b626b-577">Befehl: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="b626b-577">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="b626b-578">EndOf History</span><span class="sxs-lookup"><span data-stu-id="b626b-578">EndOfHistory</span></span>

<span data-ttu-id="b626b-579">Wechselt zum letzten Element (der aktuellen Eingabe) im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="b626b-579">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="b626b-580">Ansehen `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="b626b-580">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="b626b-581">Forwardsearchhistory</span><span class="sxs-lookup"><span data-stu-id="b626b-581">ForwardSearchHistory</span></span>

<span data-ttu-id="b626b-582">Führt eine inkrementelle Forward-Suche im Verlauf durch</span><span class="sxs-lookup"><span data-stu-id="b626b-582">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="b626b-583">Befehl: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="b626b-583">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="b626b-584">Ansehen `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="b626b-584">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="b626b-585">Historysearchrückwärts</span><span class="sxs-lookup"><span data-stu-id="b626b-585">HistorySearchBackward</span></span>

<span data-ttu-id="b626b-586">Ersetzen Sie die aktuelle Eingabe durch das Element "Previous" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.</span><span class="sxs-lookup"><span data-stu-id="b626b-586">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="b626b-587">Befehl: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="b626b-587">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="b626b-588">Historysearchforward</span><span class="sxs-lookup"><span data-stu-id="b626b-588">HistorySearchForward</span></span>

<span data-ttu-id="b626b-589">Ersetzen Sie die aktuelle Eingabe durch das Element "Next" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.</span><span class="sxs-lookup"><span data-stu-id="b626b-589">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="b626b-590">Befehl: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="b626b-590">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="b626b-591">Nexthistory</span><span class="sxs-lookup"><span data-stu-id="b626b-591">NextHistory</span></span>

<span data-ttu-id="b626b-592">Ersetzen Sie die aktuelle Eingabe durch das "Next"-Element aus dem psleline-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="b626b-592">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="b626b-593">Befehl: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-593">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="b626b-594">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="b626b-594">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="b626b-595">VI-Einfügemodus: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-595">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="b626b-596">VI-Befehlsmodus: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="b626b-596">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="b626b-597">Previoushistory</span><span class="sxs-lookup"><span data-stu-id="b626b-597">PreviousHistory</span></span>

<span data-ttu-id="b626b-598">Ersetzen Sie die aktuelle Eingabe durch das "Previous"-Element aus dem psleline-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="b626b-598">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="b626b-599">Befehl: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-599">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="b626b-600">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="b626b-600">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="b626b-601">VI-Einfügemodus: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-601">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="b626b-602">VI-Befehlsmodus: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="b626b-602">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="b626b-603">Reversesearchhistory</span><span class="sxs-lookup"><span data-stu-id="b626b-603">ReverseSearchHistory</span></span>

<span data-ttu-id="b626b-604">Führt eine inkrementelle Rückwärtssuche über den Verlauf durch</span><span class="sxs-lookup"><span data-stu-id="b626b-604">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="b626b-605">Befehl: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="b626b-605">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="b626b-606">Ansehen `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="b626b-606">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="b626b-607">Visearchhistoryrückwärts</span><span class="sxs-lookup"><span data-stu-id="b626b-607">ViSearchHistoryBackward</span></span>

<span data-ttu-id="b626b-608">Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.</span><span class="sxs-lookup"><span data-stu-id="b626b-608">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="b626b-609">VI-Einfügemodus: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="b626b-609">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="b626b-610">VI-Befehlsmodus: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="b626b-610">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="b626b-611">Vervollständigungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="b626b-611">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="b626b-612">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="b626b-612">Complete</span></span>

<span data-ttu-id="b626b-613">Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b626b-613">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="b626b-614">Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet.</span><span class="sxs-lookup"><span data-stu-id="b626b-614">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="b626b-615">Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b626b-615">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="b626b-616">Ansehen `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="b626b-616">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="b626b-617">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="b626b-617">MenuComplete</span></span>

<span data-ttu-id="b626b-618">Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b626b-618">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="b626b-619">Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet.</span><span class="sxs-lookup"><span data-stu-id="b626b-619">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="b626b-620">Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b626b-620">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="b626b-621">Cmd: `<Ctrl+@>` , `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="b626b-621">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="b626b-622">Ansehen `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="b626b-622">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="b626b-623">Possiblecompletions</span><span class="sxs-lookup"><span data-stu-id="b626b-623">PossibleCompletions</span></span>

<span data-ttu-id="b626b-624">Hiermit wird die Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b626b-624">Display the list of possible completions.</span></span>

- <span data-ttu-id="b626b-625">Ansehen `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="b626b-625">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="b626b-626">VI-Einfügemodus: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="b626b-626">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="b626b-627">VI-Befehlsmodus: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="b626b-627">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="b626b-628">Tabcompletenext</span><span class="sxs-lookup"><span data-stu-id="b626b-628">TabCompleteNext</span></span>

<span data-ttu-id="b626b-629">Es wurde versucht, den Text, der den Cursor umgibt, mit der nächsten verfügbaren Beendigung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b626b-629">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="b626b-630">Befehl: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="b626b-630">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="b626b-631">VI-Befehlsmodus: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="b626b-631">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="b626b-632">Tabcompleteprevious</span><span class="sxs-lookup"><span data-stu-id="b626b-632">TabCompletePrevious</span></span>

<span data-ttu-id="b626b-633">Versuchen Sie, den Text, der den Cursor umgibt, mit dem vorherigen verfügbaren Abschluss abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b626b-633">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="b626b-634">Befehl: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="b626b-634">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="b626b-635">VI-Befehlsmodus: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="b626b-635">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="b626b-636">Vitabcompletenext</span><span class="sxs-lookup"><span data-stu-id="b626b-636">ViTabCompleteNext</span></span>

<span data-ttu-id="b626b-637">Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompletenext auf.</span><span class="sxs-lookup"><span data-stu-id="b626b-637">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="b626b-638">VI-Einfügemodus: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="b626b-638">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="b626b-639">Vitabcompleteprevious</span><span class="sxs-lookup"><span data-stu-id="b626b-639">ViTabCompletePrevious</span></span>

<span data-ttu-id="b626b-640">Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompleteprevious auf.</span><span class="sxs-lookup"><span data-stu-id="b626b-640">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="b626b-641">VI-Einfügemodus: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="b626b-641">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="b626b-642">Sonstige Funktionen</span><span class="sxs-lookup"><span data-stu-id="b626b-642">Miscellaneous functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="b626b-643">Akzeptnextsuggestionword</span><span class="sxs-lookup"><span data-stu-id="b626b-643">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="b626b-644">Akzeptieren Sie das nächste Wort des Inline-oder ausgewählten Vorschlags.</span><span class="sxs-lookup"><span data-stu-id="b626b-644">Accept the next word of the inline or selected suggestion.</span></span>

- <span data-ttu-id="b626b-645">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-645">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="b626b-646">Accept-Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b626b-646">AcceptSuggestion</span></span>

<span data-ttu-id="b626b-647">Akzeptieren Sie den aktuellen Inline-oder ausgewählten Vorschlag.</span><span class="sxs-lookup"><span data-stu-id="b626b-647">Accept the current inline or selected suggestion.</span></span>

- <span data-ttu-id="b626b-648">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-648">Function is unbound.</span></span>

### <a name="capturescreen"></a><span data-ttu-id="b626b-649">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="b626b-649">CaptureScreen</span></span>

<span data-ttu-id="b626b-650">Interaktive Bildschirmaufnahme starten-nach oben/nach-unten-Pfeile Select Lines, Enter kopiert markierten Text in die Zwischenablage als Text und HTML.</span><span class="sxs-lookup"><span data-stu-id="b626b-650">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="b626b-651">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-651">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="b626b-652">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="b626b-652">ClearScreen</span></span>

<span data-ttu-id="b626b-653">Löschen Sie den Bildschirm, und zeichnen Sie die aktuelle Zeile am oberen Rand des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="b626b-653">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="b626b-654">Befehl: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="b626b-654">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="b626b-655">Ansehen `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="b626b-655">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="b626b-656">VI-Einfügemodus: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="b626b-656">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="b626b-657">VI-Befehlsmodus: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="b626b-657">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="b626b-658">Digitargument</span><span class="sxs-lookup"><span data-stu-id="b626b-658">DigitArgument</span></span>

<span data-ttu-id="b626b-659">Starten Sie ein neues Ziffern Argument, das an andere Funktionen übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="b626b-659">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="b626b-660">Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="b626b-660">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="b626b-661">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="b626b-661">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="b626b-662">VI-Befehlsmodus: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="b626b-662">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="b626b-663">Invokeprompt</span><span class="sxs-lookup"><span data-stu-id="b626b-663">InvokePrompt</span></span>

<span data-ttu-id="b626b-664">Löscht die aktuelle Eingabeaufforderung und ruft die prompt-Funktion auf, um die Eingabeaufforderung erneut anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b626b-664">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="b626b-665">Nützlich für benutzerdefinierte Schlüssel Handler, die den Zustand ändern, z. b. Ändern des aktuellen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="b626b-665">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="b626b-666">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-666">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="b626b-667">Scrolldisplaydown</span><span class="sxs-lookup"><span data-stu-id="b626b-667">ScrollDisplayDown</span></span>

<span data-ttu-id="b626b-668">Scrollen Sie in der Anzeige einen Bildschirm nach unten.</span><span class="sxs-lookup"><span data-stu-id="b626b-668">Scroll the display down one screen.</span></span>

- <span data-ttu-id="b626b-669">Befehl: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="b626b-669">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="b626b-670">Ansehen `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="b626b-670">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="b626b-671">Scrolldisplaydownline</span><span class="sxs-lookup"><span data-stu-id="b626b-671">ScrollDisplayDownLine</span></span>

<span data-ttu-id="b626b-672">Scrollen Sie in der Anzeige um eine Zeile nach unten.</span><span class="sxs-lookup"><span data-stu-id="b626b-672">Scroll the display down one line.</span></span>

- <span data-ttu-id="b626b-673">Befehl: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="b626b-673">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="b626b-674">Ansehen `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="b626b-674">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="b626b-675">Scrolldisplaytcursor</span><span class="sxs-lookup"><span data-stu-id="b626b-675">ScrollDisplayToCursor</span></span>

<span data-ttu-id="b626b-676">Scrollen Sie in der Anzeige zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="b626b-676">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="b626b-677">Ansehen `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="b626b-677">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="b626b-678">Scrolldisplaytop</span><span class="sxs-lookup"><span data-stu-id="b626b-678">ScrollDisplayTop</span></span>

<span data-ttu-id="b626b-679">Scrollen Sie in der Anzeige nach oben.</span><span class="sxs-lookup"><span data-stu-id="b626b-679">Scroll the display to the top.</span></span>

- <span data-ttu-id="b626b-680">Ansehen `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="b626b-680">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="b626b-681">Scrolldisplayup</span><span class="sxs-lookup"><span data-stu-id="b626b-681">ScrollDisplayUp</span></span>

<span data-ttu-id="b626b-682">Scrollen Sie einen Bildschirm nach oben.</span><span class="sxs-lookup"><span data-stu-id="b626b-682">Scroll the display up one screen.</span></span>

- <span data-ttu-id="b626b-683">Befehl: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="b626b-683">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="b626b-684">Ansehen `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="b626b-684">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="b626b-685">Scrolldisplayupline</span><span class="sxs-lookup"><span data-stu-id="b626b-685">ScrollDisplayUpLine</span></span>

<span data-ttu-id="b626b-686">Scrollen Sie in der Anzeige um eine Zeile nach oben.</span><span class="sxs-lookup"><span data-stu-id="b626b-686">Scroll the display up one line.</span></span>

- <span data-ttu-id="b626b-687">Befehl: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="b626b-687">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="b626b-688">Ansehen `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="b626b-688">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="b626b-689">Selfinsert</span><span class="sxs-lookup"><span data-stu-id="b626b-689">SelfInsert</span></span>

<span data-ttu-id="b626b-690">Fügen Sie den Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="b626b-690">Insert the key.</span></span>

- <span data-ttu-id="b626b-691">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-691">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="b626b-692">Showkeybindungen</span><span class="sxs-lookup"><span data-stu-id="b626b-692">ShowKeyBindings</span></span>

<span data-ttu-id="b626b-693">Alle gebundenen Schlüssel anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b626b-693">Show all bound keys.</span></span>

- <span data-ttu-id="b626b-694">Befehl: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="b626b-694">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="b626b-695">Ansehen `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="b626b-695">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="b626b-696">VI-Einfügemodus: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="b626b-696">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="b626b-697">Vicommandmode</span><span class="sxs-lookup"><span data-stu-id="b626b-697">ViCommandMode</span></span>

<span data-ttu-id="b626b-698">Wechseln Sie in den aktuellen Betriebsmodus von Vi-Insert zu VI-Command.</span><span class="sxs-lookup"><span data-stu-id="b626b-698">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="b626b-699">VI-Einfügemodus: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="b626b-699">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="b626b-700">Vidigitargumentinchord</span><span class="sxs-lookup"><span data-stu-id="b626b-700">ViDigitArgumentInChord</span></span>

<span data-ttu-id="b626b-701">Startet ein neues Ziffern Argument, das in einem der VI-Akkorde an andere Funktionen übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="b626b-701">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="b626b-702">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-702">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="b626b-703">Vieditvisuell</span><span class="sxs-lookup"><span data-stu-id="b626b-703">ViEditVisually</span></span>

<span data-ttu-id="b626b-704">Bearbeiten Sie die Befehlszeile in einem Text-Editor, der durch $ENV: Editor oder $env: Visual angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b626b-704">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="b626b-705">Ansehen `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="b626b-705">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="b626b-706">VI-Befehlsmodus: `<v>`</span><span class="sxs-lookup"><span data-stu-id="b626b-706">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="b626b-707">Viexit</span><span class="sxs-lookup"><span data-stu-id="b626b-707">ViExit</span></span>

<span data-ttu-id="b626b-708">Beendet die Shell.</span><span class="sxs-lookup"><span data-stu-id="b626b-708">Exits the shell.</span></span>

- <span data-ttu-id="b626b-709">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-709">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="b626b-710">Viinsertmode</span><span class="sxs-lookup"><span data-stu-id="b626b-710">ViInsertMode</span></span>

<span data-ttu-id="b626b-711">Wechselt in den Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="b626b-711">Switch to Insert mode.</span></span>

- <span data-ttu-id="b626b-712">VI-Befehlsmodus: `<i>`</span><span class="sxs-lookup"><span data-stu-id="b626b-712">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="b626b-713">Whatiskey</span><span class="sxs-lookup"><span data-stu-id="b626b-713">WhatIsKey</span></span>

<span data-ttu-id="b626b-714">Lesen Sie einen Schlüssel, und teilen Sie mir mit, wofür der Schlüssel gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="b626b-714">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="b626b-715">Befehl: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="b626b-715">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="b626b-716">Ansehen `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="b626b-716">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="b626b-717">Auswahl Funktionen</span><span class="sxs-lookup"><span data-stu-id="b626b-717">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="b626b-718">Exchangepointandmark</span><span class="sxs-lookup"><span data-stu-id="b626b-718">ExchangePointAndMark</span></span>

<span data-ttu-id="b626b-719">Der Cursor wird an der Position der Markierung platziert, und die Markierung wird an die Position des Cursors verschoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-719">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="b626b-720">Ansehen `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="b626b-720">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="b626b-721">SelectAll</span><span class="sxs-lookup"><span data-stu-id="b626b-721">SelectAll</span></span>

<span data-ttu-id="b626b-722">Wählen Sie die gesamte Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="b626b-722">Select the entire line.</span></span>

- <span data-ttu-id="b626b-723">Befehl: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="b626b-723">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="b626b-724">Selectbackwardchar</span><span class="sxs-lookup"><span data-stu-id="b626b-724">SelectBackwardChar</span></span>

<span data-ttu-id="b626b-725">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Zeichen einschließt.</span><span class="sxs-lookup"><span data-stu-id="b626b-725">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="b626b-726">Befehl: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-726">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="b626b-727">Ansehen `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-727">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="b626b-728">Selectbackwardsline</span><span class="sxs-lookup"><span data-stu-id="b626b-728">SelectBackwardsLine</span></span>

<span data-ttu-id="b626b-729">Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an den Anfang der Zeile eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="b626b-729">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="b626b-730">Befehl: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="b626b-730">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="b626b-731">Ansehen `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="b626b-731">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="b626b-732">Selectbackwardword</span><span class="sxs-lookup"><span data-stu-id="b626b-732">SelectBackwardWord</span></span>

<span data-ttu-id="b626b-733">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort enthält.</span><span class="sxs-lookup"><span data-stu-id="b626b-733">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="b626b-734">Befehl: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-734">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="b626b-735">Ansehen `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="b626b-735">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="b626b-736">Selectforwardchar</span><span class="sxs-lookup"><span data-stu-id="b626b-736">SelectForwardChar</span></span>

<span data-ttu-id="b626b-737">Passen Sie die aktuelle Auswahl an, um das nächste Zeichen einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b626b-737">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="b626b-738">Befehl: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-738">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="b626b-739">Ansehen `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-739">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="b626b-740">Selectforwardword</span><span class="sxs-lookup"><span data-stu-id="b626b-740">SelectForwardWord</span></span>

<span data-ttu-id="b626b-741">Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mit forwardword einschließt.</span><span class="sxs-lookup"><span data-stu-id="b626b-741">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="b626b-742">Ansehen `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="b626b-742">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="b626b-743">SelectLine</span><span class="sxs-lookup"><span data-stu-id="b626b-743">SelectLine</span></span>

<span data-ttu-id="b626b-744">Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an das Ende der Zeile eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="b626b-744">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="b626b-745">Befehl: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="b626b-745">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="b626b-746">Ansehen `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="b626b-746">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="b626b-747">Selectnextword</span><span class="sxs-lookup"><span data-stu-id="b626b-747">SelectNextWord</span></span>

<span data-ttu-id="b626b-748">Passen Sie die aktuelle Auswahl an das nächste Wort an.</span><span class="sxs-lookup"><span data-stu-id="b626b-748">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="b626b-749">Befehl: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="b626b-749">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="b626b-750">Selectshellbackwardword</span><span class="sxs-lookup"><span data-stu-id="b626b-750">SelectShellBackwardWord</span></span>

<span data-ttu-id="b626b-751">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort mithilfe von shellbackwardword einschließt.</span><span class="sxs-lookup"><span data-stu-id="b626b-751">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="b626b-752">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-752">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="b626b-753">Selectshellforwardword</span><span class="sxs-lookup"><span data-stu-id="b626b-753">SelectShellForwardWord</span></span>

<span data-ttu-id="b626b-754">Passen Sie die aktuelle Auswahl so an, dass das nächste Wort mithilfe von shellforwardword eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="b626b-754">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="b626b-755">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-755">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="b626b-756">Selectshellnextword</span><span class="sxs-lookup"><span data-stu-id="b626b-756">SelectShellNextWord</span></span>

<span data-ttu-id="b626b-757">Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mithilfe von shellnextword einschließt.</span><span class="sxs-lookup"><span data-stu-id="b626b-757">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="b626b-758">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="b626b-758">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="b626b-759">Setmark</span><span class="sxs-lookup"><span data-stu-id="b626b-759">SetMark</span></span>

<span data-ttu-id="b626b-760">Markieren Sie die aktuelle Position des Cursors für die Verwendung in einem nachfolgenden Bearbeitungs Befehl.</span><span class="sxs-lookup"><span data-stu-id="b626b-760">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="b626b-761">Ansehen `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="b626b-761">Emacs: `<Ctrl+@>`</span></span>

## <a name="predictive-intellisense-functions"></a><span data-ttu-id="b626b-762">Predictive IntelliSense-Funktionen</span><span class="sxs-lookup"><span data-stu-id="b626b-762">Predictive IntelliSense functions</span></span>

> [!NOTE]
> <span data-ttu-id="b626b-763">Predictive IntelliSense muss aktiviert werden, damit diese Funktionen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b626b-763">Predictive IntelliSense needs to be enabled to use these functions.</span></span>

### <a name="acceptnextwordsuggestion"></a><span data-ttu-id="b626b-764">Accept-nextwordsuggestion</span><span class="sxs-lookup"><span data-stu-id="b626b-764">AcceptNextWordSuggestion</span></span>

<span data-ttu-id="b626b-765">Akzeptiert das nächste Wort des Inline Vorschlags aus Predictive IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="b626b-765">Accepts the next word of the inline suggestion from Predictive IntelliSense.</span></span>
<span data-ttu-id="b626b-766">Diese Funktion kann mit <kbd>STRG</kbd> + <kbd>F</kbd> gebunden werden, indem der folgende Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b626b-766">This function can be bound with <kbd>Ctrl</kbd>+<kbd>F</kbd> by running the following command.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord "Ctrl+f" -Function ForwardWord
```

### <a name="acceptsuggestion"></a><span data-ttu-id="b626b-767">Accept-Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b626b-767">AcceptSuggestion</span></span>

<span data-ttu-id="b626b-768">Akzeptiert den aktuellen Inline Vorschlag von Predictive IntelliSense durch Drücken von <kbd>RIGHTARROW</kbd> , wenn sich der Cursor am Ende der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="b626b-768">Accepts the current inline suggestion from Predictive IntelliSense by pressing <kbd>RightArrow</kbd> when the cursor is at the end of the current line.</span></span>

## <a name="search-functions"></a><span data-ttu-id="b626b-769">Suchfunktionen</span><span class="sxs-lookup"><span data-stu-id="b626b-769">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="b626b-770">Merkmal Suche</span><span class="sxs-lookup"><span data-stu-id="b626b-770">CharacterSearch</span></span>

<span data-ttu-id="b626b-771">Lesen Sie ein Zeichen, und suchen Sie nach dem nächsten Vorkommen dieses Zeichens.</span><span class="sxs-lookup"><span data-stu-id="b626b-771">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="b626b-772">Wenn ein Argument angegeben ist, suchen Sie nach vorn (oder rückwärts, wenn negativ) für das n-te vorkommen.</span><span class="sxs-lookup"><span data-stu-id="b626b-772">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="b626b-773">Befehl: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="b626b-773">Cmd: `<F3>`</span></span>
- <span data-ttu-id="b626b-774">Ansehen `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="b626b-774">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="b626b-775">VI-Einfügemodus: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="b626b-775">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="b626b-776">VI-Befehlsmodus: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="b626b-776">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="b626b-777">Merkmal searchrückwärts</span><span class="sxs-lookup"><span data-stu-id="b626b-777">CharacterSearchBackward</span></span>

<span data-ttu-id="b626b-778">Liest ein Zeichen und sucht rückwärts nach dem nächsten Vorkommen dieses Zeichens.</span><span class="sxs-lookup"><span data-stu-id="b626b-778">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="b626b-779">Wenn ein Argument angegeben wird, suchen Sie nach hinten (oder vorwärts, wenn negativ).</span><span class="sxs-lookup"><span data-stu-id="b626b-779">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="b626b-780">Befehl: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="b626b-780">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="b626b-781">Ansehen `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="b626b-781">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="b626b-782">VI-Einfügemodus: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="b626b-782">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="b626b-783">VI-Befehlsmodus: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="b626b-783">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="b626b-784">Repeatlastcharsearch</span><span class="sxs-lookup"><span data-stu-id="b626b-784">RepeatLastCharSearch</span></span>

<span data-ttu-id="b626b-785">Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche.</span><span class="sxs-lookup"><span data-stu-id="b626b-785">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="b626b-786">VI-Befehlsmodus: `<;>`</span><span class="sxs-lookup"><span data-stu-id="b626b-786">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="b626b-787">Repeatlastcharsearchabwärts</span><span class="sxs-lookup"><span data-stu-id="b626b-787">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="b626b-788">Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche, aber in umgekehrter Richtung.</span><span class="sxs-lookup"><span data-stu-id="b626b-788">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="b626b-789">VI-Befehlsmodus: `<,>`</span><span class="sxs-lookup"><span data-stu-id="b626b-789">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="b626b-790">Repeatsearch</span><span class="sxs-lookup"><span data-stu-id="b626b-790">RepeatSearch</span></span>

<span data-ttu-id="b626b-791">Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="b626b-791">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="b626b-792">VI-Befehlsmodus: `<n>`</span><span class="sxs-lookup"><span data-stu-id="b626b-792">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="b626b-793">Repeatsearchrückwärts</span><span class="sxs-lookup"><span data-stu-id="b626b-793">RepeatSearchBackward</span></span>

<span data-ttu-id="b626b-794">Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="b626b-794">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="b626b-795">VI-Befehlsmodus: `<N>`</span><span class="sxs-lookup"><span data-stu-id="b626b-795">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="b626b-796">Searchchar</span><span class="sxs-lookup"><span data-stu-id="b626b-796">SearchChar</span></span>

<span data-ttu-id="b626b-797">Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="b626b-797">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="b626b-798">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b626b-798">This is for 't' functionality.</span></span>

- <span data-ttu-id="b626b-799">VI-Befehlsmodus: `<f>`</span><span class="sxs-lookup"><span data-stu-id="b626b-799">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="b626b-800">Searchcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="b626b-800">SearchCharBackward</span></span>

<span data-ttu-id="b626b-801">Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück.</span><span class="sxs-lookup"><span data-stu-id="b626b-801">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="b626b-802">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b626b-802">This is for 'T' functionality.</span></span>

- <span data-ttu-id="b626b-803">VI-Befehlsmodus: `<F>`</span><span class="sxs-lookup"><span data-stu-id="b626b-803">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="b626b-804">Searchcharbackwardwithbackoff</span><span class="sxs-lookup"><span data-stu-id="b626b-804">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="b626b-805">Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück.</span><span class="sxs-lookup"><span data-stu-id="b626b-805">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="b626b-806">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b626b-806">This is for 'T' functionality.</span></span>

- <span data-ttu-id="b626b-807">VI-Befehlsmodus: `<T>`</span><span class="sxs-lookup"><span data-stu-id="b626b-807">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="b626b-808">Searchcharwithbackoff</span><span class="sxs-lookup"><span data-stu-id="b626b-808">SearchCharWithBackoff</span></span>

<span data-ttu-id="b626b-809">Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="b626b-809">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="b626b-810">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b626b-810">This is for 't' functionality.</span></span>

- <span data-ttu-id="b626b-811">VI-Befehlsmodus: `<t>`</span><span class="sxs-lookup"><span data-stu-id="b626b-811">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="b626b-812">SearchForward</span><span class="sxs-lookup"><span data-stu-id="b626b-812">SearchForward</span></span>

<span data-ttu-id="b626b-813">Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.</span><span class="sxs-lookup"><span data-stu-id="b626b-813">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="b626b-814">VI-Einfügemodus: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="b626b-814">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="b626b-815">VI-Befehlsmodus: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="b626b-815">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="b626b-816">Benutzerdefinierte Tastenbindungen</span><span class="sxs-lookup"><span data-stu-id="b626b-816">Custom Key Bindings</span></span>

<span data-ttu-id="b626b-817">Psread Line unterstützt benutzerdefinierte Tastenbindungen mithilfe des Cmdlets `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="b626b-817">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="b626b-818">Die meisten benutzerdefinierten Tastenbindungen wenden eine der oben genannten Funktionen an, z. b.</span><span class="sxs-lookup"><span data-stu-id="b626b-818">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="b626b-819">Sie können einen ScriptBlock an einen Schlüssel binden.</span><span class="sxs-lookup"><span data-stu-id="b626b-819">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="b626b-820">Der ScriptBlock kann beliebig viele Aufgaben erledigen.</span><span class="sxs-lookup"><span data-stu-id="b626b-820">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="b626b-821">Einige nützliche Beispiele sind u.a.</span><span class="sxs-lookup"><span data-stu-id="b626b-821">Some useful examples include</span></span>

- <span data-ttu-id="b626b-822">Bearbeiten der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="b626b-822">edit the command line</span></span>
- <span data-ttu-id="b626b-823">Öffnen eines neuen Fensters (z. b. "Hilfe")</span><span class="sxs-lookup"><span data-stu-id="b626b-823">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="b626b-824">Ändern der Verzeichnisse ohne Änderung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="b626b-824">change directories without changing the command line</span></span>

<span data-ttu-id="b626b-825">Der ScriptBlock empfängt zwei Argumente:</span><span class="sxs-lookup"><span data-stu-id="b626b-825">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="b626b-826">`$key` -Ein **[ConsoleKeyInfo]** -Objekt, das der Schlüssel ist, der die benutzerdefinierte Bindung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="b626b-826">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="b626b-827">Wenn Sie denselben ScriptBlock an mehrere Schlüssel binden und abhängig vom Schlüssel verschiedene Aktionen ausführen müssen, können Sie $Key überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b626b-827">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="b626b-828">Viele benutzerdefinierte Bindungen ignorieren dieses Argument.</span><span class="sxs-lookup"><span data-stu-id="b626b-828">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="b626b-829">`$arg` -Ein beliebiges Argument.</span><span class="sxs-lookup"><span data-stu-id="b626b-829">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="b626b-830">In den meisten Fällen ist dies ein ganzzahliges Argument, das der Benutzer von den Schlüsselbindungen digitargument übergibt.</span><span class="sxs-lookup"><span data-stu-id="b626b-830">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="b626b-831">Wenn die Bindung keine Argumente akzeptiert, ist es sinnvoll, dieses Argument zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="b626b-831">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="b626b-832">Sehen wir uns ein Beispiel an, in dem eine Befehlszeile zum Verlauf hinzugefügt wird, ohne sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b626b-832">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="b626b-833">Dies ist nützlich, wenn Sie vergessen haben, etwas zu tun, ohne die Befehlszeile, die Sie bereits eingegeben haben, erneut eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="b626b-833">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="b626b-834">In der Datei `SamplePSReadLineProfile.ps1` , die im psread Line-Modul Ordner installiert ist, werden viele weitere Beispiele angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b626b-834">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="b626b-835">Die meisten Tastenbindungen verwenden einige Hilfsfunktionen zum Bearbeiten der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="b626b-835">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="b626b-836">Diese APIs werden im nächsten Abschnitt dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="b626b-836">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="b626b-837">APIs für die benutzerdefinierte Schlüssel Bindungs Unterstützung</span><span class="sxs-lookup"><span data-stu-id="b626b-837">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="b626b-838">Die folgenden Funktionen sind in Microsoft. PowerShell. psconsolereadline öffentlich, können jedoch nicht direkt an einen Schlüssel gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="b626b-838">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="b626b-839">Die meisten sind in benutzerdefinierten Tastenkombinationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="b626b-839">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="b626b-840">Fügen Sie eine Befehlszeile zum Verlauf hinzu, ohne sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b626b-840">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="b626b-841">Löschen Sie den Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="b626b-841">Clear the kill-ring.</span></span>  <span data-ttu-id="b626b-842">Dies wird größtenteils zum Testen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b626b-842">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="b626b-843">Löschen Sie die Längen Zeichen aus dem Startmenü.</span><span class="sxs-lookup"><span data-stu-id="b626b-843">Delete length characters from start.</span></span>  <span data-ttu-id="b626b-844">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="b626b-844">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="b626b-845">Führen Sie die Aktion "Ding" basierend auf der Benutzereinstellung aus.</span><span class="sxs-lookup"><span data-stu-id="b626b-845">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="b626b-846">Diese beiden Funktionen rufen nützliche Informationen über den aktuellen Status des Eingabe Puffers ab.</span><span class="sxs-lookup"><span data-stu-id="b626b-846">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="b626b-847">Der erste wird häufiger für einfache Fälle verwendet.</span><span class="sxs-lookup"><span data-stu-id="b626b-847">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="b626b-848">Die zweite wird verwendet, wenn ihre Bindung einen fortgeschrittenen Vorgang mit der AST bewirkt.</span><span class="sxs-lookup"><span data-stu-id="b626b-848">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="b626b-849">Diese beiden Funktionen werden von verwendet `Get-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="b626b-849">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="b626b-850">Der erste wird verwendet, um alle Tastenbindungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b626b-850">The first is used to get all key bindings.</span></span> <span data-ttu-id="b626b-851">Die zweite wird verwendet, um bestimmte Tastenbindungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b626b-851">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="b626b-852">Diese Funktion wird von Get-PSReadLineOption verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.</span><span class="sxs-lookup"><span data-stu-id="b626b-852">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="b626b-853">Wenn in der Befehlszeile keine Auswahl vorhanden ist, wird-1 sowohl in Start als auch in der Länge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b626b-853">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="b626b-854">Wenn eine Auswahl in der Befehlszeile vorhanden ist, werden Start und Länge der Auswahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b626b-854">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="b626b-855">Fügen Sie am Cursor ein Zeichen oder eine Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="b626b-855">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="b626b-856">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="b626b-856">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="b626b-857">Dies ist der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="b626b-857">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="b626b-858">Sie unterstützt keine Rekursion und ist daher in einer benutzerdefinierten schlüsselbindung nicht nützlich.</span><span class="sxs-lookup"><span data-stu-id="b626b-858">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="b626b-859">Diese Funktion wird von Remove-PSReadLineKeyHandler verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.</span><span class="sxs-lookup"><span data-stu-id="b626b-859">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="b626b-860">Ersetzen Sie einige der Eingaben.</span><span class="sxs-lookup"><span data-stu-id="b626b-860">Replace some of the input.</span></span> <span data-ttu-id="b626b-861">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="b626b-861">This operation supports undo/redo.</span></span> <span data-ttu-id="b626b-862">Dies wird als "Delete", gefolgt von INSERT, bevorzugt, da es als einzelne Aktion für "Rückgängig" behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="b626b-862">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="b626b-863">Bewegen Sie den Cursor in den angegebenen Offset.</span><span class="sxs-lookup"><span data-stu-id="b626b-863">Move the cursor to the given offset.</span></span> <span data-ttu-id="b626b-864">Cursor Bewegung wird nicht für Rückgängigmachen nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="b626b-864">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="b626b-865">Bei dieser Funktion handelt es sich um eine Hilfsmethode, die vom Cmdlet Set-psread lineoption verwendet wird. Sie kann jedoch für eine benutzerdefinierte schlüsselbindung nützlich sein, die eine Einstellung vorübergehend ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="b626b-865">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="b626b-866">Diese Hilfsmethode wird für benutzerdefinierte Bindungen verwendet, die digitargument berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="b626b-866">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="b626b-867">Ein typischer-Rückruf sieht wie folgt aus</span><span class="sxs-lookup"><span data-stu-id="b626b-867">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="b626b-868">Hinweis</span><span class="sxs-lookup"><span data-stu-id="b626b-868">Note</span></span>

### <a name="command-history"></a><span data-ttu-id="b626b-869">Befehlsverlauf</span><span class="sxs-lookup"><span data-stu-id="b626b-869">Command History</span></span>

<span data-ttu-id="b626b-870">Psleseline verwaltet eine Verlaufs Datei, die alle Befehle und Daten enthält, die Sie in der Befehlszeile eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="b626b-870">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="b626b-871">Dies kann vertrauliche Daten einschließlich Kenn Wörtern enthalten.</span><span class="sxs-lookup"><span data-stu-id="b626b-871">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="b626b-872">Wenn Sie z. b. das `ConvertTo-SecureString` Cmdlet verwenden, wird das Kennwort als nur-Text in der Verlaufs Datei protokolliert.</span><span class="sxs-lookup"><span data-stu-id="b626b-872">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="b626b-873">Die Verlaufs Dateien sind eine Datei mit dem Namen `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="b626b-873">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="b626b-874">Auf Windows-Systemen wird die Verlaufs Datei unter gespeichert `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="b626b-874">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="b626b-875">Auf nicht-Windows-Systemen werden die Verlaufs Dateien unter `$env:XDG_DATA_HOME/powershell/PSReadLine` oder gespeichert `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="b626b-875">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="b626b-876">Feedback & zu psread Line beitragen</span><span class="sxs-lookup"><span data-stu-id="b626b-876">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="b626b-877">Psread Line auf GitHub</span><span class="sxs-lookup"><span data-stu-id="b626b-877">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="b626b-878">Sie können auf der GitHub-Seite eine Pull Request einreichen oder Feedback einreichen.</span><span class="sxs-lookup"><span data-stu-id="b626b-878">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="b626b-879">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b626b-879">See Also</span></span>

<span data-ttu-id="b626b-880">"Psread Line" wird stark von der GNU-Bibliothek für die [Zeilen](https://tiswww.case.edu/php/chet/readline/rltop.html) Übereinstimmung beeinflusst</span><span class="sxs-lookup"><span data-stu-id="b626b-880">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
