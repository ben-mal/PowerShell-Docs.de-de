---
description: Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.
Locale: en-US
ms.date: 11/23/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über psread Line
ms.openlocfilehash: ddc88dda3514e4279b6d91b023e26da88f645af7
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685211"
---
# <a name="psreadline"></a><span data-ttu-id="05242-103">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="05242-103">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="05242-104">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="05242-104">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="05242-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05242-105">Short Description</span></span>

<span data-ttu-id="05242-106">Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="05242-106">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="05242-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05242-107">Long Description</span></span>

<span data-ttu-id="05242-108">Psleline 2,2 bietet eine leistungsfähige Befehlszeilen Bearbeitungsfunktion für die PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="05242-108">PSReadLine 2.2 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="05242-109">Sie bietet:</span><span class="sxs-lookup"><span data-stu-id="05242-109">It provides:</span></span>

- <span data-ttu-id="05242-110">Syntax Farbgebung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="05242-110">Syntax coloring of the command line</span></span>
- <span data-ttu-id="05242-111">Visuelle Hinweise auf Syntax Fehler</span><span class="sxs-lookup"><span data-stu-id="05242-111">A visual indication of syntax errors</span></span>
- <span data-ttu-id="05242-112">Bessere mehrzeilige Erfahrung (sowohl Bearbeitung als auch Verlauf)</span><span class="sxs-lookup"><span data-stu-id="05242-112">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="05242-113">Anpassbare Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="05242-113">Customizable key bindings</span></span>
- <span data-ttu-id="05242-114">Cmd-und Emacs-Modi</span><span class="sxs-lookup"><span data-stu-id="05242-114">Cmd and Emacs modes</span></span>
- <span data-ttu-id="05242-115">Viele Konfigurationsoptionen</span><span class="sxs-lookup"><span data-stu-id="05242-115">Many configuration options</span></span>
- <span data-ttu-id="05242-116">Bash-Stil Vervollständigung (optional im cmd-Modus, Standard im Emacs-Modus)</span><span class="sxs-lookup"><span data-stu-id="05242-116">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="05242-117">Emacs: Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="05242-117">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="05242-118">PowerShell-tokenbasierte "Wort Bewegung" und "Kill"</span><span class="sxs-lookup"><span data-stu-id="05242-118">PowerShell token based "word" movement and kill</span></span>
- <span data-ttu-id="05242-119">Predictive IntelliSense</span><span class="sxs-lookup"><span data-stu-id="05242-119">Predictive IntelliSense</span></span>

<span data-ttu-id="05242-120">Psread Line 2.2.0 Es wurden zwei neue vorhersagbare IntelliSense-Features hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="05242-120">PSReadLine 2.2.0 added two new predictive IntelliSense features:</span></span>

- <span data-ttu-id="05242-121">Der Parameter " **prätionviewstyle** " wurde hinzugefügt, um die Auswahl der neuen zu ermöglichen `ListView` .</span><span class="sxs-lookup"><span data-stu-id="05242-121">Added the **PredictionViewStyle** parameter to allow for the selection of the new `ListView`.</span></span>
- <span data-ttu-id="05242-122">Verbindung mit psread Line zu den `CommandPrediction` in PS 7,1 eingeführten APIs, damit Benutzer ein präatormodul importieren können, das die Vorschläge aus einer benutzerdefinierten Quelle darstellen kann.</span><span class="sxs-lookup"><span data-stu-id="05242-122">Connected PSReadLine to the `CommandPrediction` APIs introduced in PS 7.1 to allow a user can import a predictor module that can render the suggestions from a custom source.</span></span>

<span data-ttu-id="05242-123">Für psread Line ist PowerShell 3,0 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05242-123">PSReadLine requires PowerShell 3.0, or newer.</span></span> <span data-ttu-id="05242-124">Psleline funktioniert mit dem standardmäßigen Konsolen Host, Visual Studio Code und Fenster Terminal.</span><span class="sxs-lookup"><span data-stu-id="05242-124">PSReadLine works with default console host, Visual Studio Code, and Window Terminal.</span></span> <span data-ttu-id="05242-125">Es funktioniert nicht in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="05242-125">It does not work in PowerShell ISE.</span></span>

<span data-ttu-id="05242-126">Psread Line 2.2.0 wird mit PowerShell 7,2 ausgeliefert und wird in allen unterstützten Versionen von PowerShell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="05242-126">PSReadLine 2.2.0 ships with PowerShell 7.2 and is supported in all supported versions of PowerShell.</span></span> <span data-ttu-id="05242-127">Es ist für die Installation über das PowerShell-Katalog verfügbar.</span><span class="sxs-lookup"><span data-stu-id="05242-127">It is available to install from the PowerShell Gallery.</span></span>
<span data-ttu-id="05242-128">Führen Sie den folgenden Befehl aus, um psread Line 2.2.0 in einer unterstützten Version von PowerShell zu installieren.</span><span class="sxs-lookup"><span data-stu-id="05242-128">To install PSReadLine 2.2.0 in a supported version of PowerShell run the following command.</span></span>

```powershell
Install-Module -Name PSReadLine -AllowPrerelease
```

> [!NOTE]
> <span data-ttu-id="05242-129">Ab PowerShell 7,0 überspringt PowerShell das automatische Laden von psleseline unter Windows, wenn ein Bildschirm Leseprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="05242-129">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="05242-130">Derzeit funktioniert psread Line nicht gut mit den Bildschirmlesern.</span><span class="sxs-lookup"><span data-stu-id="05242-130">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="05242-131">Das Standard Rendering und die Formatierung von PowerShell 7,0 unter Windows funktionieren ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="05242-131">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="05242-132">Sie können das Modul ggf. manuell laden.</span><span class="sxs-lookup"><span data-stu-id="05242-132">You can manually load the module if necessary.</span></span>

## <a name="predictive-intellisense"></a><span data-ttu-id="05242-133">Predictive IntelliSense</span><span class="sxs-lookup"><span data-stu-id="05242-133">Predictive IntelliSense</span></span>

<span data-ttu-id="05242-134">Predictive IntelliSense ist eine Ergänzung zum Konzept der Vervollständigung mit der Tab-Taste, die dem Benutzer hilft, Befehle erfolgreich abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="05242-134">Predictive IntelliSense is an addition to the concept of tab completion that assists the user in successfully completing commands.</span></span> <span data-ttu-id="05242-135">Sie ermöglicht Benutzern das ermitteln, bearbeiten und ausführen vollständiger Befehle basierend auf übereinstimmenden Vorhersagen aus dem Verlauf des Benutzers und zusätzlichen domänenspezifischen Plug-ins.</span><span class="sxs-lookup"><span data-stu-id="05242-135">It enables users to discover, edit, and execute full commands based on matching predictions from the user's history and additional domain specific plugins.</span></span>

### <a name="enable-predictive-intellisense"></a><span data-ttu-id="05242-136">Aktivieren von Predictive IntelliSense</span><span class="sxs-lookup"><span data-stu-id="05242-136">Enable Predictive IntelliSense</span></span>

<span data-ttu-id="05242-137">Predictive IntelliSense ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="05242-137">Predictive IntelliSense is disabled by default.</span></span> <span data-ttu-id="05242-138">Um Vorhersagen zu aktivieren, führen Sie einfach den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="05242-138">To enable predictions, just run the following command:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource History
```

<span data-ttu-id="05242-139">Der Parameter " **prätionsource** " kann auch Plug-Ins für domänenspezifische und benutzerdefinierte Anforderungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="05242-139">The **PredictionSource** parameter can also accept plugins for domain specific and custom requirements.</span></span>

<span data-ttu-id="05242-140">Um Predictive IntelliSense zu deaktivieren, führen Sie einfach Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="05242-140">To disable Predictive IntelliSense, just run:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource None
```

<span data-ttu-id="05242-141">Die folgenden Funktionen sind in der-Klasse **[Microsoft. PowerShell. psconsolereadline]** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="05242-141">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="05242-142">Grundlegende Bearbeitungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="05242-142">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="05242-143">Abbrechen</span><span class="sxs-lookup"><span data-stu-id="05242-143">Abort</span></span>

<span data-ttu-id="05242-144">Abbrechen der aktuellen Aktion, z.b. inkrementelle Verlaufs Suche.</span><span class="sxs-lookup"><span data-stu-id="05242-144">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="05242-145">Ansehen `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="05242-145">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="05242-146">Akzeptandgetnext</span><span class="sxs-lookup"><span data-stu-id="05242-146">AcceptAndGetNext</span></span>

<span data-ttu-id="05242-147">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="05242-147">Attempt to execute the current input.</span></span> <span data-ttu-id="05242-148">Wenn Sie ausgeführt werden kann (wie z. b. Accept Line), erinnern Sie sich beim nächsten Aufruf von "read line" an das nächste Element aus dem Verlauf.</span><span class="sxs-lookup"><span data-stu-id="05242-148">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="05242-149">Ansehen `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="05242-149">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="05242-150">Annahme</span><span class="sxs-lookup"><span data-stu-id="05242-150">AcceptLine</span></span>

<span data-ttu-id="05242-151">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="05242-151">Attempt to execute the current input.</span></span> <span data-ttu-id="05242-152">Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="05242-152">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="05242-153">Befehl: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="05242-153">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="05242-154">Ansehen `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="05242-154">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="05242-155">VI-Einfügemodus: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="05242-155">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="05242-156">AddLine</span><span class="sxs-lookup"><span data-stu-id="05242-156">AddLine</span></span>

<span data-ttu-id="05242-157">Die Fortsetzungs Aufforderung wird in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="05242-157">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="05242-158">Dies ist nützlich, um mehrzeilige Eingaben als einen einzelnen Befehl einzugeben, auch wenn eine einzelne Zeile allein eine Eingabe ist.</span><span class="sxs-lookup"><span data-stu-id="05242-158">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="05242-159">Befehl: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="05242-159">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="05242-160">Ansehen `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="05242-160">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="05242-161">VI-Einfügemodus: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="05242-161">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="05242-162">VI-Befehlsmodus: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="05242-162">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="05242-163">Backwarddeletechar</span><span class="sxs-lookup"><span data-stu-id="05242-163">BackwardDeleteChar</span></span>

<span data-ttu-id="05242-164">Löschen Sie das Zeichen vor dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="05242-164">Delete the character before the cursor.</span></span>

- <span data-ttu-id="05242-165">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="05242-165">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="05242-166">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="05242-166">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="05242-167">VI-Einfügemodus: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="05242-167">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="05242-168">VI-Befehlsmodus: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="05242-168">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteinput"></a><span data-ttu-id="05242-169">Backwarddelta-eInput</span><span class="sxs-lookup"><span data-stu-id="05242-169">BackwardDeleteInput</span></span>

<span data-ttu-id="05242-170">Wie backwardkillinput: löscht Text von der Stelle bis zum Anfang der Eingabe, legt den gelöschten Text jedoch nicht in den Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="05242-170">Like BackwardKillInput - deletes text from the point to the start of the input, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="05242-171">Befehl: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="05242-171">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="05242-172">VI-Einfügemodus: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="05242-172">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="05242-173">VI-Befehlsmodus: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="05242-173">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="05242-174">Backwarddelta-Eline</span><span class="sxs-lookup"><span data-stu-id="05242-174">BackwardDeleteLine</span></span>

<span data-ttu-id="05242-175">Wie backwardkillline löscht Text vom Punkt bis zum Anfang der Zeile, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="05242-175">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="05242-176">VI-Befehlsmodus: `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="05242-176">Vi command mode: `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="05242-177">Backwarddeleteword</span><span class="sxs-lookup"><span data-stu-id="05242-177">BackwardDeleteWord</span></span>

<span data-ttu-id="05242-178">Löscht das vorherige Wort.</span><span class="sxs-lookup"><span data-stu-id="05242-178">Deletes the previous word.</span></span>

- <span data-ttu-id="05242-179">VI-Befehlsmodus: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="05242-179">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillinput"></a><span data-ttu-id="05242-180">Backwardkillinput</span><span class="sxs-lookup"><span data-stu-id="05242-180">BackwardKillInput</span></span>

<span data-ttu-id="05242-181">Löschen Sie den Text vom Beginn der Eingabe bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="05242-181">Clear the text from the start of the input to the cursor.</span></span> <span data-ttu-id="05242-182">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="05242-182">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="05242-183">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="05242-183">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="05242-184">Backwardkillline</span><span class="sxs-lookup"><span data-stu-id="05242-184">BackwardKillLine</span></span>

<span data-ttu-id="05242-185">Löschen Sie den Text vom Anfang der aktuellen logischen Zeile bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="05242-185">Clear the text from the start of the current logical line to the cursor.</span></span> <span data-ttu-id="05242-186">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="05242-186">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="05242-187">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-187">Function is unbound.</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="05242-188">Backwardkillword</span><span class="sxs-lookup"><span data-stu-id="05242-188">BackwardKillWord</span></span>

<span data-ttu-id="05242-189">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="05242-189">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="05242-190">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="05242-190">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="05242-191">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="05242-191">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="05242-192">Cmd: `<Ctrl+Backspace>` , `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="05242-192">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="05242-193">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="05242-193">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="05242-194">VI-Einfügemodus: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="05242-194">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="05242-195">VI-Befehlsmodus: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="05242-195">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="05242-196">Cancelline</span><span class="sxs-lookup"><span data-stu-id="05242-196">CancelLine</span></span>

<span data-ttu-id="05242-197">Brechen Sie die aktuelle Eingabe ab, belassen Sie die Eingabe auf dem Bildschirm, kehren Sie jedoch zurück zum Host, damit die Eingabeaufforderung erneut ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="05242-197">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="05242-198">VI-Einfügemodus: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="05242-198">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="05242-199">VI-Befehlsmodus: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="05242-199">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="05242-200">Kopieren</span><span class="sxs-lookup"><span data-stu-id="05242-200">Copy</span></span>

<span data-ttu-id="05242-201">Kopiert den ausgewählten Bereich in die Zwischenablage des Systems.</span><span class="sxs-lookup"><span data-stu-id="05242-201">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="05242-202">Wenn keine Region ausgewählt ist, kopieren Sie die gesamte Zeile.</span><span class="sxs-lookup"><span data-stu-id="05242-202">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="05242-203">Befehl: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="05242-203">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="05242-204">Copyorcancelline</span><span class="sxs-lookup"><span data-stu-id="05242-204">CopyOrCancelLine</span></span>

<span data-ttu-id="05242-205">Wenn Text ausgewählt ist, kopieren Sie ihn in die Zwischenablage, andernfalls brechen Sie die Zeile ab.</span><span class="sxs-lookup"><span data-stu-id="05242-205">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="05242-206">Befehl: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="05242-206">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="05242-207">Ansehen `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="05242-207">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="05242-208">Ausschneiden</span><span class="sxs-lookup"><span data-stu-id="05242-208">Cut</span></span>

<span data-ttu-id="05242-209">Löscht die ausgewählte Region, in der Gelöschter Text in der Zwischenablage des Systems</span><span class="sxs-lookup"><span data-stu-id="05242-209">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="05242-210">Befehl: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="05242-210">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="05242-211">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="05242-211">DeleteChar</span></span>

<span data-ttu-id="05242-212">Löschen Sie das Zeichen unter dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="05242-212">Delete the character under the cursor.</span></span>

- <span data-ttu-id="05242-213">Befehl: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="05242-213">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="05242-214">Ansehen `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="05242-214">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="05242-215">VI-Einfügemodus: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="05242-215">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="05242-216">VI-Befehlsmodus: `<Delete>` , `<x>` , `<d,l>` , `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="05242-216">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="05242-217">Deletecharorexit</span><span class="sxs-lookup"><span data-stu-id="05242-217">DeleteCharOrExit</span></span>

<span data-ttu-id="05242-218">Löschen Sie das Zeichen unter dem Cursor, oder beenden Sie den Prozess, wenn die Zeile leer ist.</span><span class="sxs-lookup"><span data-stu-id="05242-218">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="05242-219">Ansehen `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="05242-219">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="05242-220">Deleteendof Buffer</span><span class="sxs-lookup"><span data-stu-id="05242-220">DeleteEndOfBuffer</span></span>

<span data-ttu-id="05242-221">Löscht bis zum Ende des mehrzeiligen Puffers.</span><span class="sxs-lookup"><span data-stu-id="05242-221">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="05242-222">VI-Befehlsmodus: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="05242-222">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="05242-223">Deleteendof</span><span class="sxs-lookup"><span data-stu-id="05242-223">DeleteEndOfWord</span></span>

<span data-ttu-id="05242-224">Bis zum Ende des Worts löschen.</span><span class="sxs-lookup"><span data-stu-id="05242-224">Delete to the end of the word.</span></span>

- <span data-ttu-id="05242-225">VI-Befehlsmodus: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="05242-225">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="05242-226">"Deleteline</span><span class="sxs-lookup"><span data-stu-id="05242-226">DeleteLine</span></span>

<span data-ttu-id="05242-227">Löscht die aktuelle logische Zeile eines mehrzeiligen Puffers und ermöglicht Rückgängigmachen.</span><span class="sxs-lookup"><span data-stu-id="05242-227">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="05242-228">VI-Befehlsmodus: `<d,d>` , `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="05242-228">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="05242-229">Deletepreviouslines</span><span class="sxs-lookup"><span data-stu-id="05242-229">DeletePreviousLines</span></span>

<span data-ttu-id="05242-230">Löscht die vorherigen angeforderten logischen Zeilen und die aktuelle logische Zeile in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="05242-230">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="05242-231">VI-Befehlsmodus: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="05242-231">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="05242-232">Deleterelativelines</span><span class="sxs-lookup"><span data-stu-id="05242-232">DeleteRelativeLines</span></span>

<span data-ttu-id="05242-233">Löscht vom Anfang des Puffers in die aktuelle logische Zeile in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="05242-233">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="05242-234">Bei den meisten VI-Befehlen `<d,g,g>` kann dem Befehl ein numerisches Argument vorangestellt werden, das eine absolute Zeilennummer angibt, die in Verbindung mit der aktuellen Zeilennummer einen Bereich von Zeilen bilden, die gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="05242-234">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="05242-235">Wenn kein Wert angegeben wird, wird das numerische Argument standardmäßig auf 1 festgelegt. Dies bezieht sich auf die erste logische Zeile in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="05242-235">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="05242-236">Die tatsächliche Anzahl von Zeilen, die aus der mehrzeiligen Zeile gelöscht werden sollen, wird als Differenz zwischen der aktuellen logischen Zeilennummer und dem angegebenen numerischen Argument berechnet, das daher negativ sein kann.</span><span class="sxs-lookup"><span data-stu-id="05242-236">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="05242-237">Daher der _relative_ Teil des Methoden namens.</span><span class="sxs-lookup"><span data-stu-id="05242-237">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="05242-238">VI-Befehlsmodus: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="05242-238">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="05242-239">Deletenextlines</span><span class="sxs-lookup"><span data-stu-id="05242-239">DeleteNextLines</span></span>

<span data-ttu-id="05242-240">Löscht die aktuelle logische Linie und die nächsten angeforderten logischen Zeilen in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="05242-240">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="05242-241">VI-Befehlsmodus: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="05242-241">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="05242-242">Delta-inetyp</span><span class="sxs-lookup"><span data-stu-id="05242-242">DeleteLineToFirstChar</span></span>

<span data-ttu-id="05242-243">Löscht das erste nicht leere Zeichen der aktuellen logischen Zeile in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="05242-243">Deletes from the first non-blank character of the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="05242-244">VI-Befehlsmodus: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="05242-244">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="05242-245">Deletegeend</span><span class="sxs-lookup"><span data-stu-id="05242-245">DeleteToEnd</span></span>

<span data-ttu-id="05242-246">Bis zum Ende der Zeile löschen.</span><span class="sxs-lookup"><span data-stu-id="05242-246">Delete to the end of the line.</span></span>

- <span data-ttu-id="05242-247">VI-Befehlsmodus: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="05242-247">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="05242-248">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="05242-248">DeleteWord</span></span>

<span data-ttu-id="05242-249">Löschen Sie das nächste Wort.</span><span class="sxs-lookup"><span data-stu-id="05242-249">Delete the next word.</span></span>

- <span data-ttu-id="05242-250">VI-Befehlsmodus: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="05242-250">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteinput"></a><span data-ttu-id="05242-251">Forwarddelta eteinput</span><span class="sxs-lookup"><span data-stu-id="05242-251">ForwardDeleteInput</span></span>

<span data-ttu-id="05242-252">Wie bei "killline" wird Text vom Punkt bis zum Ende der Eingabe gelöscht, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="05242-252">Like KillLine - deletes text from the point to the end of the input, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="05242-253">Befehl: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="05242-253">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="05242-254">VI-Einfügemodus: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="05242-254">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="05242-255">VI-Befehlsmodus: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="05242-255">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="05242-256">Forwarddelta-Eline</span><span class="sxs-lookup"><span data-stu-id="05242-256">ForwardDeleteLine</span></span>

<span data-ttu-id="05242-257">Löscht Text vom Punkt bis zum Ende der aktuellen logischen Zeile, legt den gelöschten Text jedoch nicht im Kill-Ring ab.</span><span class="sxs-lookup"><span data-stu-id="05242-257">Deletes text from the point to the end of the current logical line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="05242-258">Funktion ist nicht gebunden</span><span class="sxs-lookup"><span data-stu-id="05242-258">Function is unbound</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="05242-259">Insertlineoberhalb</span><span class="sxs-lookup"><span data-stu-id="05242-259">InsertLineAbove</span></span>

<span data-ttu-id="05242-260">Oberhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="05242-260">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="05242-261">Der Cursor wechselt zum Anfang der neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="05242-261">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="05242-262">Befehl: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="05242-262">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="05242-263">Insertlinebelow</span><span class="sxs-lookup"><span data-stu-id="05242-263">InsertLineBelow</span></span>

<span data-ttu-id="05242-264">Unterhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="05242-264">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="05242-265">Der Cursor wechselt zum Anfang der neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="05242-265">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="05242-266">Befehl: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="05242-266">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="05242-267">Invertieren</span><span class="sxs-lookup"><span data-stu-id="05242-267">InvertCase</span></span>

<span data-ttu-id="05242-268">Kehrt die Groß-/Kleinschreibung des aktuellen Zeichens um und wechselt zum nächsten.</span><span class="sxs-lookup"><span data-stu-id="05242-268">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="05242-269">VI-Befehlsmodus: `<~>`</span><span class="sxs-lookup"><span data-stu-id="05242-269">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="05242-270">Killline</span><span class="sxs-lookup"><span data-stu-id="05242-270">KillLine</span></span>

<span data-ttu-id="05242-271">Löschen Sie die Eingabe vom Cursor bis zum Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="05242-271">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="05242-272">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="05242-272">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="05242-273">Ansehen `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="05242-273">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="05242-274">Killregion</span><span class="sxs-lookup"><span data-stu-id="05242-274">KillRegion</span></span>

<span data-ttu-id="05242-275">Beenden Sie den Text zwischen dem Cursor und der Markierung.</span><span class="sxs-lookup"><span data-stu-id="05242-275">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="05242-276">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-276">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="05242-277">Killword</span><span class="sxs-lookup"><span data-stu-id="05242-277">KillWord</span></span>

<span data-ttu-id="05242-278">Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts.</span><span class="sxs-lookup"><span data-stu-id="05242-278">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="05242-279">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht.</span><span class="sxs-lookup"><span data-stu-id="05242-279">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="05242-280">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="05242-280">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="05242-281">Cmd: `<Alt+d>` , `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="05242-281">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="05242-282">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="05242-282">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="05242-283">VI-Einfügemodus: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="05242-283">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="05242-284">VI-Befehlsmodus: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="05242-284">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="05242-285">Einfügen</span><span class="sxs-lookup"><span data-stu-id="05242-285">Paste</span></span>

<span data-ttu-id="05242-286">Fügen Sie Text aus der Zwischenablage des Systems ein.</span><span class="sxs-lookup"><span data-stu-id="05242-286">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="05242-287">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="05242-287">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="05242-288">VI-Einfügemodus: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="05242-288">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="05242-289">VI-Befehlsmodus: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="05242-289">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05242-290">Wenn Sie die Funktion **Einfügen** verwenden, wird der gesamte Inhalt des Zwischenablage Puffers in den Eingabepuffer von psread Line eingefügt.</span><span class="sxs-lookup"><span data-stu-id="05242-290">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="05242-291">Der Eingabepuffer wird dann an den PowerShell-Parser übergeben.</span><span class="sxs-lookup"><span data-stu-id="05242-291">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="05242-292">Eingaben, die mithilfe der **Rechtsklick-Einfügemethode** der Konsolenanwendung eingefügt werden, werden jeweils ein Zeichen in den Eingabepuffer kopiert.</span><span class="sxs-lookup"><span data-stu-id="05242-292">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="05242-293">Der Eingabepuffer wird an den Parser übergeben, wenn ein Zeilen vorzeichensatz kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="05242-293">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="05242-294">Daher wird die Eingabe jeweils Zeilen gleich analysiert.</span><span class="sxs-lookup"><span data-stu-id="05242-294">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="05242-295">Der Unterschied zwischen den Methoden zum Einfügen führt zu einem anderen Ausführungs Verhalten.</span><span class="sxs-lookup"><span data-stu-id="05242-295">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="05242-296">Pasteafter</span><span class="sxs-lookup"><span data-stu-id="05242-296">PasteAfter</span></span>

<span data-ttu-id="05242-297">Fügen Sie die Zwischenablage nach dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.</span><span class="sxs-lookup"><span data-stu-id="05242-297">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="05242-298">VI-Befehlsmodus: `<p>`</span><span class="sxs-lookup"><span data-stu-id="05242-298">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="05242-299">Pastebefore</span><span class="sxs-lookup"><span data-stu-id="05242-299">PasteBefore</span></span>

<span data-ttu-id="05242-300">Fügen Sie die Zwischenablage vor dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.</span><span class="sxs-lookup"><span data-stu-id="05242-300">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="05242-301">VI-Befehlsmodus: `<P>`</span><span class="sxs-lookup"><span data-stu-id="05242-301">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="05242-302">Prepdandaccept</span><span class="sxs-lookup"><span data-stu-id="05242-302">PrependAndAccept</span></span>

<span data-ttu-id="05242-303">Fügen Sie ein "#" vorangesteht, und akzeptieren Sie die Zeile.</span><span class="sxs-lookup"><span data-stu-id="05242-303">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="05242-304">VI-Befehlsmodus: `<#>`</span><span class="sxs-lookup"><span data-stu-id="05242-304">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="05242-305">Wiederholen</span><span class="sxs-lookup"><span data-stu-id="05242-305">Redo</span></span>

<span data-ttu-id="05242-306">Rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="05242-306">Undo an undo.</span></span>

- <span data-ttu-id="05242-307">Befehl: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="05242-307">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="05242-308">VI-Einfügemodus: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="05242-308">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="05242-309">VI-Befehlsmodus: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="05242-309">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="05242-310">Repeatlastcommand</span><span class="sxs-lookup"><span data-stu-id="05242-310">RepeatLastCommand</span></span>

<span data-ttu-id="05242-311">Wiederholen Sie die letzte Textänderung.</span><span class="sxs-lookup"><span data-stu-id="05242-311">Repeat the last text modification.</span></span>

- <span data-ttu-id="05242-312">VI-Befehlsmodus: `<.>`</span><span class="sxs-lookup"><span data-stu-id="05242-312">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="05242-313">Revertline</span><span class="sxs-lookup"><span data-stu-id="05242-313">RevertLine</span></span>

<span data-ttu-id="05242-314">Kehrt alle Eingaben in die aktuelle Eingabe um.</span><span class="sxs-lookup"><span data-stu-id="05242-314">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="05242-315">Befehl: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="05242-315">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="05242-316">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="05242-316">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="05242-317">Shellbackwardkillword</span><span class="sxs-lookup"><span data-stu-id="05242-317">ShellBackwardKillWord</span></span>

<span data-ttu-id="05242-318">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="05242-318">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="05242-319">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="05242-319">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="05242-320">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="05242-320">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="05242-321">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-321">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="05242-322">Shellkillword</span><span class="sxs-lookup"><span data-stu-id="05242-322">ShellKillWord</span></span>

<span data-ttu-id="05242-323">Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts.</span><span class="sxs-lookup"><span data-stu-id="05242-323">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="05242-324">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht.</span><span class="sxs-lookup"><span data-stu-id="05242-324">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="05242-325">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="05242-325">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="05242-326">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-326">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="05242-327">Austausch Zeichen</span><span class="sxs-lookup"><span data-stu-id="05242-327">SwapCharacters</span></span>

<span data-ttu-id="05242-328">Tauschen Sie das aktuelle und das aktuelle Zeichen aus.</span><span class="sxs-lookup"><span data-stu-id="05242-328">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="05242-329">Ansehen `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="05242-329">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="05242-330">VI-Einfügemodus: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="05242-330">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="05242-331">VI-Befehlsmodus: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="05242-331">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="05242-332">Rückgängig</span><span class="sxs-lookup"><span data-stu-id="05242-332">Undo</span></span>

<span data-ttu-id="05242-333">Rückgängigmachen einer vorherigen Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="05242-333">Undo a previous edit.</span></span>

- <span data-ttu-id="05242-334">Befehl: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="05242-334">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="05242-335">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="05242-335">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="05242-336">VI-Einfügemodus: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="05242-336">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="05242-337">VI-Befehlsmodus: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="05242-337">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="05242-338">Nicht doall</span><span class="sxs-lookup"><span data-stu-id="05242-338">UndoAll</span></span>

<span data-ttu-id="05242-339">Alle vorherigen Änderungen für die Zeile rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="05242-339">Undo all previous edits for line.</span></span>

- <span data-ttu-id="05242-340">VI-Befehlsmodus: `<U>`</span><span class="sxs-lookup"><span data-stu-id="05242-340">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="05242-341">Unixwordrubout</span><span class="sxs-lookup"><span data-stu-id="05242-341">UnixWordRubout</span></span>

<span data-ttu-id="05242-342">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="05242-342">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="05242-343">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="05242-343">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="05242-344">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="05242-344">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="05242-345">Ansehen `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="05242-345">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="05242-346">Validateandakzeptline</span><span class="sxs-lookup"><span data-stu-id="05242-346">ValidateAndAcceptLine</span></span>

<span data-ttu-id="05242-347">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="05242-347">Attempt to execute the current input.</span></span> <span data-ttu-id="05242-348">Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="05242-348">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="05242-349">Ansehen `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="05242-349">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="05242-350">Viakzeptline</span><span class="sxs-lookup"><span data-stu-id="05242-350">ViAcceptLine</span></span>

<span data-ttu-id="05242-351">Akzeptieren Sie die Zeile, und wechseln Sie zum Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="05242-351">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="05242-352">VI-Befehlsmodus: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="05242-352">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="05242-353">Viakzeptlineorexit</span><span class="sxs-lookup"><span data-stu-id="05242-353">ViAcceptLineOrExit</span></span>

<span data-ttu-id="05242-354">Wie deletecharorexit im Emacs-Modus, akzeptiert jedoch die Zeile, anstatt ein Zeichen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="05242-354">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="05242-355">VI-Einfügemodus: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="05242-355">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="05242-356">VI-Befehlsmodus: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="05242-356">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="05242-357">Viappendline</span><span class="sxs-lookup"><span data-stu-id="05242-357">ViAppendLine</span></span>

<span data-ttu-id="05242-358">Unterhalb der aktuellen Zeile wird eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="05242-358">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="05242-359">VI-Befehlsmodus: `<o>`</span><span class="sxs-lookup"><span data-stu-id="05242-359">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="05242-360">Vibackwarddeleteglob</span><span class="sxs-lookup"><span data-stu-id="05242-360">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="05242-361">Löscht das vorherige Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="05242-361">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="05242-362">VI-Befehlsmodus: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="05242-362">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="05242-363">Vibackwardglob</span><span class="sxs-lookup"><span data-stu-id="05242-363">ViBackwardGlob</span></span>

<span data-ttu-id="05242-364">Verschiebt den Cursor zurück an den Anfang des vorherigen Worts, wobei nur Leerraum als Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="05242-364">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="05242-365">VI-Befehlsmodus: `<B>`</span><span class="sxs-lookup"><span data-stu-id="05242-365">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="05242-366">Videletebrace</span><span class="sxs-lookup"><span data-stu-id="05242-366">ViDeleteBrace</span></span>

<span data-ttu-id="05242-367">Suchen Sie nach der passenden geschweiften Klammer, Klammer oder eckigen Klammer, und löschen Sie alle Inhalte in, einschließlich der geschweiften Klammer.</span><span class="sxs-lookup"><span data-stu-id="05242-367">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="05242-368">VI-Befehlsmodus: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="05242-368">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="05242-369">Videleteendobglob</span><span class="sxs-lookup"><span data-stu-id="05242-369">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="05242-370">Bis zum Ende des Worts löschen.</span><span class="sxs-lookup"><span data-stu-id="05242-370">Delete to the end of the word.</span></span>

- <span data-ttu-id="05242-371">VI-Befehlsmodus: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="05242-371">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="05242-372">Videleteglob</span><span class="sxs-lookup"><span data-stu-id="05242-372">ViDeleteGlob</span></span>

<span data-ttu-id="05242-373">Löschen Sie den nächsten globmuster (Leerzeichen mit Trennzeichen).</span><span class="sxs-lookup"><span data-stu-id="05242-373">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="05242-374">VI-Befehlsmodus: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="05242-374">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="05242-375">Videletetobeforechar</span><span class="sxs-lookup"><span data-stu-id="05242-375">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="05242-376">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="05242-376">Deletes until given character.</span></span>

- <span data-ttu-id="05242-377">VI-Befehlsmodus: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="05242-377">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="05242-378">Videletebackbeforecharrückwärts</span><span class="sxs-lookup"><span data-stu-id="05242-378">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="05242-379">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="05242-379">Deletes until given character.</span></span>

- <span data-ttu-id="05242-380">VI-Befehlsmodus: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="05242-380">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="05242-381">Videleteto Char</span><span class="sxs-lookup"><span data-stu-id="05242-381">ViDeleteToChar</span></span>

<span data-ttu-id="05242-382">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="05242-382">Deletes until given character.</span></span>

- <span data-ttu-id="05242-383">VI-Befehlsmodus: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="05242-383">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="05242-384">Videletebackcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="05242-384">ViDeleteToCharBackward</span></span>

<span data-ttu-id="05242-385">Löscht rückwärts bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="05242-385">Deletes backwards until given character.</span></span>

- <span data-ttu-id="05242-386">VI-Befehlsmodus: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="05242-386">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="05242-387">Viinsertatbeginung</span><span class="sxs-lookup"><span data-stu-id="05242-387">ViInsertAtBegining</span></span>

<span data-ttu-id="05242-388">Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Anfang der Zeile.</span><span class="sxs-lookup"><span data-stu-id="05242-388">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="05242-389">VI-Befehlsmodus: `<I>`</span><span class="sxs-lookup"><span data-stu-id="05242-389">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="05242-390">Viinsertatend</span><span class="sxs-lookup"><span data-stu-id="05242-390">ViInsertAtEnd</span></span>

<span data-ttu-id="05242-391">Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Ende der Zeile.</span><span class="sxs-lookup"><span data-stu-id="05242-391">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="05242-392">VI-Befehlsmodus: `<A>`</span><span class="sxs-lookup"><span data-stu-id="05242-392">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="05242-393">Viinsertline</span><span class="sxs-lookup"><span data-stu-id="05242-393">ViInsertLine</span></span>

<span data-ttu-id="05242-394">Oberhalb der aktuellen Zeile wird eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="05242-394">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="05242-395">VI-Befehlsmodus: `<O>`</span><span class="sxs-lookup"><span data-stu-id="05242-395">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="05242-396">Viinsertwithappend</span><span class="sxs-lookup"><span data-stu-id="05242-396">ViInsertWithAppend</span></span>

<span data-ttu-id="05242-397">An der aktuellen Zeilen Position anfügen.</span><span class="sxs-lookup"><span data-stu-id="05242-397">Append from the current line position.</span></span>

- <span data-ttu-id="05242-398">VI-Befehlsmodus: `<a>`</span><span class="sxs-lookup"><span data-stu-id="05242-398">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="05242-399">Viinsertwithdelete</span><span class="sxs-lookup"><span data-stu-id="05242-399">ViInsertWithDelete</span></span>

<span data-ttu-id="05242-400">Löschen Sie das aktuelle Zeichen und wechseln Sie in den Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="05242-400">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="05242-401">VI-Befehlsmodus: `<s>`</span><span class="sxs-lookup"><span data-stu-id="05242-401">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="05242-402">Vijoinlines</span><span class="sxs-lookup"><span data-stu-id="05242-402">ViJoinLines</span></span>

<span data-ttu-id="05242-403">Verbindet die aktuelle Zeile und die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="05242-403">Joins the current line and the next line.</span></span>

- <span data-ttu-id="05242-404">VI-Befehlsmodus: `<J>`</span><span class="sxs-lookup"><span data-stu-id="05242-404">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="05242-405">Vireplaceline</span><span class="sxs-lookup"><span data-stu-id="05242-405">ViReplaceLine</span></span>

<span data-ttu-id="05242-406">Löschen Sie die gesamte Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="05242-406">Erase the entire command line.</span></span>

- <span data-ttu-id="05242-407">VI-Befehlsmodus: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="05242-407">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="05242-408">Vireplacetobeforechar</span><span class="sxs-lookup"><span data-stu-id="05242-408">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="05242-409">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="05242-409">Replaces until given character.</span></span>

- <span data-ttu-id="05242-410">VI-Befehlsmodus: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="05242-410">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="05242-411">Vireplaceumbeforecharrückwärts</span><span class="sxs-lookup"><span data-stu-id="05242-411">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="05242-412">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="05242-412">Replaces until given character.</span></span>

- <span data-ttu-id="05242-413">VI-Befehlsmodus: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="05242-413">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="05242-414">Vireplaceumchar</span><span class="sxs-lookup"><span data-stu-id="05242-414">ViReplaceToChar</span></span>

<span data-ttu-id="05242-415">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="05242-415">Deletes until given character.</span></span>

- <span data-ttu-id="05242-416">VI-Befehlsmodus: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="05242-416">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="05242-417">Vireplacebackcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="05242-417">ViReplaceToCharBackward</span></span>

<span data-ttu-id="05242-418">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="05242-418">Replaces until given character.</span></span>

- <span data-ttu-id="05242-419">VI-Befehlsmodus: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="05242-419">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="05242-420">Viyankbeginningosline</span><span class="sxs-lookup"><span data-stu-id="05242-420">ViYankBeginningOfLine</span></span>

<span data-ttu-id="05242-421">Yank vom Anfang des Puffers bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="05242-421">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="05242-422">VI-Befehlsmodus: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="05242-422">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="05242-423">Viyankendobglob</span><span class="sxs-lookup"><span data-stu-id="05242-423">ViYankEndOfGlob</span></span>

<span data-ttu-id="05242-424">Yank vom Cursor bis zum Ende des Worts (s).</span><span class="sxs-lookup"><span data-stu-id="05242-424">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="05242-425">VI-Befehlsmodus: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="05242-425">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="05242-426">Viyankendof</span><span class="sxs-lookup"><span data-stu-id="05242-426">ViYankEndOfWord</span></span>

<span data-ttu-id="05242-427">Yank vom Cursor bis zum Ende des Worts (s).</span><span class="sxs-lookup"><span data-stu-id="05242-427">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="05242-428">VI-Befehlsmodus: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="05242-428">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="05242-429">Viyankleft</span><span class="sxs-lookup"><span data-stu-id="05242-429">ViYankLeft</span></span>

<span data-ttu-id="05242-430">Die Zeichen werden Links vom Cursor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05242-430">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="05242-431">VI-Befehlsmodus: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="05242-431">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="05242-432">Viyankline</span><span class="sxs-lookup"><span data-stu-id="05242-432">ViYankLine</span></span>

<span data-ttu-id="05242-433">Den gesamten Puffer.</span><span class="sxs-lookup"><span data-stu-id="05242-433">Yank the entire buffer.</span></span>

- <span data-ttu-id="05242-434">VI-Befehlsmodus: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="05242-434">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="05242-435">Viyanknextglob</span><span class="sxs-lookup"><span data-stu-id="05242-435">ViYankNextGlob</span></span>

<span data-ttu-id="05242-436">Yank vom Cursor bis zum Anfang des nächsten Worts (n).</span><span class="sxs-lookup"><span data-stu-id="05242-436">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="05242-437">VI-Befehlsmodus: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="05242-437">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="05242-438">Viyanknextword</span><span class="sxs-lookup"><span data-stu-id="05242-438">ViYankNextWord</span></span>

<span data-ttu-id="05242-439">Das Wort (e) nach dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="05242-439">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="05242-440">VI-Befehlsmodus: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="05242-440">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="05242-441">Viyankprozent</span><span class="sxs-lookup"><span data-stu-id="05242-441">ViYankPercent</span></span>

<span data-ttu-id="05242-442">Von der entsprechenden geschweiften geschweifter Klammer.</span><span class="sxs-lookup"><span data-stu-id="05242-442">Yank to/from matching brace.</span></span>

- <span data-ttu-id="05242-443">VI-Befehlsmodus: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="05242-443">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="05242-444">Viyankpreviousglob</span><span class="sxs-lookup"><span data-stu-id="05242-444">ViYankPreviousGlob</span></span>

<span data-ttu-id="05242-445">Yank von Anfang des Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="05242-445">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="05242-446">VI-Befehlsmodus: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="05242-446">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="05242-447">Viyankpreviousword</span><span class="sxs-lookup"><span data-stu-id="05242-447">ViYankPreviousWord</span></span>

<span data-ttu-id="05242-448">Das Wort (e) vor dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="05242-448">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="05242-449">VI-Befehlsmodus: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="05242-449">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="05242-450">Viyankright</span><span class="sxs-lookup"><span data-stu-id="05242-450">ViYankRight</span></span>

<span data-ttu-id="05242-451">(E) unter und rechts vom Cursor.</span><span class="sxs-lookup"><span data-stu-id="05242-451">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="05242-452">VI-Befehlsmodus: `<y,l>` , `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="05242-452">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="05242-453">Viyanktoendosline</span><span class="sxs-lookup"><span data-stu-id="05242-453">ViYankToEndOfLine</span></span>

<span data-ttu-id="05242-454">Yank vom Cursor bis zum Ende des Puffers.</span><span class="sxs-lookup"><span data-stu-id="05242-454">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="05242-455">VI-Befehlsmodus: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="05242-455">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="05242-456">Viyanktofirstchar</span><span class="sxs-lookup"><span data-stu-id="05242-456">ViYankToFirstChar</span></span>

<span data-ttu-id="05242-457">Yank vom ersten Zeichen, das kein Leerzeichen ist, bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="05242-457">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="05242-458">VI-Befehlsmodus: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="05242-458">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="05242-459">Yank</span><span class="sxs-lookup"><span data-stu-id="05242-459">Yank</span></span>

<span data-ttu-id="05242-460">Fügen Sie der Eingabe den zuletzt beendeten Text hinzu.</span><span class="sxs-lookup"><span data-stu-id="05242-460">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="05242-461">Ansehen `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="05242-461">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="05242-462">Yanklastarg</span><span class="sxs-lookup"><span data-stu-id="05242-462">YankLastArg</span></span>

<span data-ttu-id="05242-463">Das letzte Argument aus der vorherigen Verlaufs Zeile.</span><span class="sxs-lookup"><span data-stu-id="05242-463">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="05242-464">Mit einem Argument verhält sich das erste Mal, wenn es aufgerufen wird, wie yankntharg.</span><span class="sxs-lookup"><span data-stu-id="05242-464">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="05242-465">Wenn Sie mehrmals aufgerufen wird, durchläuft Sie stattdessen den Verlauf, und arg legt die Richtung fest (negative Umkehrung der Richtung).</span><span class="sxs-lookup"><span data-stu-id="05242-465">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="05242-466">Befehl: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="05242-466">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="05242-467">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="05242-467">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="05242-468">Yankntharg</span><span class="sxs-lookup"><span data-stu-id="05242-468">YankNthArg</span></span>

<span data-ttu-id="05242-469">Yank das erste Argument (nach dem Befehl) aus der vorherigen Verlaufs Zeile.</span><span class="sxs-lookup"><span data-stu-id="05242-469">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="05242-470">Bei einem Argument wird das n-te Argument (beginnend bei 0), wenn das Argument negativ ist, mit dem letzten Argument beginnen.</span><span class="sxs-lookup"><span data-stu-id="05242-470">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="05242-471">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="05242-471">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="05242-472">Yankpop</span><span class="sxs-lookup"><span data-stu-id="05242-472">YankPop</span></span>

<span data-ttu-id="05242-473">Wenn der vorherige Vorgang "Yank" oder "yankpop" war, ersetzen Sie den zuvor angezeigten Text durch den nächsten ausgeblendeten Text aus dem Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="05242-473">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="05242-474">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="05242-474">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="05242-475">Cursor Verschiebungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="05242-475">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="05242-476">Backwardchar</span><span class="sxs-lookup"><span data-stu-id="05242-476">BackwardChar</span></span>

<span data-ttu-id="05242-477">Bewegen Sie den Cursor um ein Zeichen nach links.</span><span class="sxs-lookup"><span data-stu-id="05242-477">Move the cursor one character to the left.</span></span> <span data-ttu-id="05242-478">Dadurch kann der Cursor in die vorherige Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="05242-478">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="05242-479">Befehl: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-479">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="05242-480">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="05242-480">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="05242-481">Backwardword</span><span class="sxs-lookup"><span data-stu-id="05242-481">BackwardWord</span></span>

<span data-ttu-id="05242-482">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="05242-482">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="05242-483">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="05242-483">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="05242-484">Befehl: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-484">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="05242-485">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="05242-485">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="05242-486">VI-Einfügemodus: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-486">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="05242-487">VI-Befehlsmodus: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-487">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="05242-488">Beginningosline</span><span class="sxs-lookup"><span data-stu-id="05242-488">BeginningOfLine</span></span>

<span data-ttu-id="05242-489">Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Anfang der aktuellen Zeile oder, wenn Sie sich bereits am Anfang der Zeile befinden, bis zum Anfang der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="05242-489">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="05242-490">Wenn die Eingabe über eine einzelne Zeile verfügt, wechseln Sie zum Anfang der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="05242-490">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="05242-491">Befehl: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="05242-491">Cmd: `<Home>`</span></span>
- <span data-ttu-id="05242-492">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="05242-492">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="05242-493">VI-Einfügemodus: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="05242-493">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="05242-494">VI-Befehlsmodus: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="05242-494">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="05242-495">Endosline</span><span class="sxs-lookup"><span data-stu-id="05242-495">EndOfLine</span></span>

<span data-ttu-id="05242-496">Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Ende der aktuellen Zeile, oder wechseln Sie, wenn Sie sich bereits am Ende der Zeile befindet, bis zum Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="05242-496">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="05242-497">Wenn die Eingabe über eine einzelne Zeile verfügt, verschieben Sie das Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="05242-497">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="05242-498">Befehl: `<End>`</span><span class="sxs-lookup"><span data-stu-id="05242-498">Cmd: `<End>`</span></span>
- <span data-ttu-id="05242-499">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="05242-499">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="05242-500">VI-Einfügemodus: `<End>`</span><span class="sxs-lookup"><span data-stu-id="05242-500">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="05242-501">Forwardchar</span><span class="sxs-lookup"><span data-stu-id="05242-501">ForwardChar</span></span>

<span data-ttu-id="05242-502">Bewegen Sie den Cursor um ein Zeichen nach rechts.</span><span class="sxs-lookup"><span data-stu-id="05242-502">Move the cursor one character to the right.</span></span> <span data-ttu-id="05242-503">Dadurch kann der Cursor in die nächste Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="05242-503">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="05242-504">Befehl: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-504">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="05242-505">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="05242-505">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="05242-506">Forwardword</span><span class="sxs-lookup"><span data-stu-id="05242-506">ForwardWord</span></span>

<span data-ttu-id="05242-507">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="05242-507">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="05242-508">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="05242-508">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="05242-509">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="05242-509">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="05242-510">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="05242-510">GotoBrace</span></span>

<span data-ttu-id="05242-511">Wechseln Sie zur passenden geschweiften Klammer, Klammer oder eckigen Klammer.</span><span class="sxs-lookup"><span data-stu-id="05242-511">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="05242-512">Befehl: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="05242-512">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="05242-513">VI-Einfügemodus: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="05242-513">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="05242-514">VI-Befehlsmodus: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="05242-514">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="05242-515">Goum Column</span><span class="sxs-lookup"><span data-stu-id="05242-515">GotoColumn</span></span>

<span data-ttu-id="05242-516">Wechseln Sie in die Spalte, die von arg angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="05242-516">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="05242-517">VI-Befehlsmodus: `<|>`</span><span class="sxs-lookup"><span data-stu-id="05242-517">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="05242-518">Gostarfirstnonblankosline</span><span class="sxs-lookup"><span data-stu-id="05242-518">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="05242-519">Bewegen Sie den Cursor auf das erste nicht leere Zeichen in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="05242-519">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="05242-520">VI-Befehlsmodus: `<^>` , `<_>`</span><span class="sxs-lookup"><span data-stu-id="05242-520">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="05242-521">"MUVE"</span><span class="sxs-lookup"><span data-stu-id="05242-521">MoveToEndOfLine</span></span>

<span data-ttu-id="05242-522">Bewegen Sie den Cursor an das Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="05242-522">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="05242-523">VI-Befehlsmodus: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="05242-523">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="05242-524">Nextline</span><span class="sxs-lookup"><span data-stu-id="05242-524">NextLine</span></span>

<span data-ttu-id="05242-525">Bewegen Sie den Cursor in die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="05242-525">Move the cursor to the next line.</span></span>

- <span data-ttu-id="05242-526">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-526">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="05242-527">Nextword</span><span class="sxs-lookup"><span data-stu-id="05242-527">NextWord</span></span>

<span data-ttu-id="05242-528">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="05242-528">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="05242-529">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="05242-529">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="05242-530">Befehl: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-530">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="05242-531">VI-Einfügemodus: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-531">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="05242-532">VI-Befehlsmodus: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-532">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="05242-533">Nextwordend</span><span class="sxs-lookup"><span data-stu-id="05242-533">NextWordEnd</span></span>

<span data-ttu-id="05242-534">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="05242-534">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="05242-535">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="05242-535">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="05242-536">VI-Befehlsmodus: `<e>`</span><span class="sxs-lookup"><span data-stu-id="05242-536">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="05242-537">Previousline</span><span class="sxs-lookup"><span data-stu-id="05242-537">PreviousLine</span></span>

<span data-ttu-id="05242-538">Bewegen Sie den Cursor in die vorherige Zeile.</span><span class="sxs-lookup"><span data-stu-id="05242-538">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="05242-539">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-539">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="05242-540">Shellbackwardword</span><span class="sxs-lookup"><span data-stu-id="05242-540">ShellBackwardWord</span></span>

<span data-ttu-id="05242-541">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="05242-541">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="05242-542">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="05242-542">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="05242-543">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-543">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="05242-544">Shellforwardword</span><span class="sxs-lookup"><span data-stu-id="05242-544">ShellForwardWord</span></span>

<span data-ttu-id="05242-545">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="05242-545">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="05242-546">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="05242-546">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="05242-547">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-547">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="05242-548">Shellnextword</span><span class="sxs-lookup"><span data-stu-id="05242-548">ShellNextWord</span></span>

<span data-ttu-id="05242-549">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="05242-549">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="05242-550">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="05242-550">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="05242-551">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-551">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="05242-552">Vibackwardchar</span><span class="sxs-lookup"><span data-stu-id="05242-552">ViBackwardChar</span></span>

<span data-ttu-id="05242-553">Bewegen Sie den Cursor um ein Zeichen nach links im VI-Bearbeitungsmodus.</span><span class="sxs-lookup"><span data-stu-id="05242-553">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="05242-554">Dadurch kann der Cursor in die vorherige Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="05242-554">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="05242-555">VI-Einfügemodus: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-555">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="05242-556">VI-Befehlsmodus: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="05242-556">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="05242-557">Vibackwardword</span><span class="sxs-lookup"><span data-stu-id="05242-557">ViBackwardWord</span></span>

<span data-ttu-id="05242-558">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="05242-558">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="05242-559">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="05242-559">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="05242-560">VI-Befehlsmodus: `<b>`</span><span class="sxs-lookup"><span data-stu-id="05242-560">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="05242-561">Viforwardchar</span><span class="sxs-lookup"><span data-stu-id="05242-561">ViForwardChar</span></span>

<span data-ttu-id="05242-562">Bewegen Sie den Cursor um ein Zeichen nach rechts im VI-Bearbeitungsmodus.</span><span class="sxs-lookup"><span data-stu-id="05242-562">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="05242-563">Dadurch kann der Cursor in die nächste Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="05242-563">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="05242-564">VI-Einfügemodus: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-564">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="05242-565">VI-Befehlsmodus: `<RightArrow>` , `<Spacebar>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="05242-565">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="05242-566">Viendobglob</span><span class="sxs-lookup"><span data-stu-id="05242-566">ViEndOfGlob</span></span>

<span data-ttu-id="05242-567">Verschiebt den Cursor an das Ende des Worts und verwendet nur Leerzeichen als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="05242-567">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="05242-568">VI-Befehlsmodus: `<E>`</span><span class="sxs-lookup"><span data-stu-id="05242-568">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="05242-569">Viendof previousglob</span><span class="sxs-lookup"><span data-stu-id="05242-569">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="05242-570">Wechselt zum Ende des vorherigen Worts, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="05242-570">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="05242-571">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-571">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="05242-572">Vigoumbrace</span><span class="sxs-lookup"><span data-stu-id="05242-572">ViGotoBrace</span></span>

<span data-ttu-id="05242-573">Ähnelt gotobrace, aber ist Zeichen basiert anstelle von tokenbasiert.</span><span class="sxs-lookup"><span data-stu-id="05242-573">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="05242-574">VI-Befehlsmodus: `<%>`</span><span class="sxs-lookup"><span data-stu-id="05242-574">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="05242-575">Vinextglob</span><span class="sxs-lookup"><span data-stu-id="05242-575">ViNextGlob</span></span>

<span data-ttu-id="05242-576">Wechselt zum nächsten Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="05242-576">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="05242-577">VI-Befehlsmodus: `<W>`</span><span class="sxs-lookup"><span data-stu-id="05242-577">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="05242-578">Vinextword</span><span class="sxs-lookup"><span data-stu-id="05242-578">ViNextWord</span></span>

<span data-ttu-id="05242-579">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="05242-579">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="05242-580">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="05242-580">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="05242-581">VI-Befehlsmodus: `<w>`</span><span class="sxs-lookup"><span data-stu-id="05242-581">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="05242-582">Verlaufs Funktionen</span><span class="sxs-lookup"><span data-stu-id="05242-582">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="05242-583">Beginningof History</span><span class="sxs-lookup"><span data-stu-id="05242-583">BeginningOfHistory</span></span>

<span data-ttu-id="05242-584">Wechselt zum ersten Element im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="05242-584">Move to the first item in the history.</span></span>

- <span data-ttu-id="05242-585">Ansehen `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="05242-585">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="05242-586">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="05242-586">ClearHistory</span></span>

<span data-ttu-id="05242-587">Löscht den Verlauf in psleline.</span><span class="sxs-lookup"><span data-stu-id="05242-587">Clears history in PSReadLine.</span></span> <span data-ttu-id="05242-588">Dies wirkt sich nicht auf den PowerShell-Verlauf aus.</span><span class="sxs-lookup"><span data-stu-id="05242-588">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="05242-589">Befehl: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="05242-589">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="05242-590">EndOf History</span><span class="sxs-lookup"><span data-stu-id="05242-590">EndOfHistory</span></span>

<span data-ttu-id="05242-591">Wechselt zum letzten Element (der aktuellen Eingabe) im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="05242-591">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="05242-592">Ansehen `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="05242-592">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="05242-593">Forwardsearchhistory</span><span class="sxs-lookup"><span data-stu-id="05242-593">ForwardSearchHistory</span></span>

<span data-ttu-id="05242-594">Führt eine inkrementelle Forward-Suche im Verlauf durch</span><span class="sxs-lookup"><span data-stu-id="05242-594">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="05242-595">Befehl: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="05242-595">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="05242-596">Ansehen `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="05242-596">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="05242-597">Historysearchrückwärts</span><span class="sxs-lookup"><span data-stu-id="05242-597">HistorySearchBackward</span></span>

<span data-ttu-id="05242-598">Ersetzen Sie die aktuelle Eingabe durch das Element "Previous" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.</span><span class="sxs-lookup"><span data-stu-id="05242-598">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="05242-599">Befehl: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="05242-599">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="05242-600">Historysearchforward</span><span class="sxs-lookup"><span data-stu-id="05242-600">HistorySearchForward</span></span>

<span data-ttu-id="05242-601">Ersetzen Sie die aktuelle Eingabe durch das Element "Next" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.</span><span class="sxs-lookup"><span data-stu-id="05242-601">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="05242-602">Befehl: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="05242-602">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="05242-603">Nexthistory</span><span class="sxs-lookup"><span data-stu-id="05242-603">NextHistory</span></span>

<span data-ttu-id="05242-604">Ersetzen Sie die aktuelle Eingabe durch das "Next"-Element aus dem psleline-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="05242-604">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="05242-605">Befehl: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-605">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="05242-606">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="05242-606">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="05242-607">VI-Einfügemodus: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-607">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="05242-608">VI-Befehlsmodus: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="05242-608">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="05242-609">Previoushistory</span><span class="sxs-lookup"><span data-stu-id="05242-609">PreviousHistory</span></span>

<span data-ttu-id="05242-610">Ersetzen Sie die aktuelle Eingabe durch das "Previous"-Element aus dem psleline-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="05242-610">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="05242-611">Befehl: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-611">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="05242-612">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="05242-612">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="05242-613">VI-Einfügemodus: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-613">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="05242-614">VI-Befehlsmodus: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="05242-614">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="05242-615">Reversesearchhistory</span><span class="sxs-lookup"><span data-stu-id="05242-615">ReverseSearchHistory</span></span>

<span data-ttu-id="05242-616">Führt eine inkrementelle Rückwärtssuche über den Verlauf durch</span><span class="sxs-lookup"><span data-stu-id="05242-616">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="05242-617">Befehl: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="05242-617">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="05242-618">Ansehen `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="05242-618">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="05242-619">Visearchhistoryrückwärts</span><span class="sxs-lookup"><span data-stu-id="05242-619">ViSearchHistoryBackward</span></span>

<span data-ttu-id="05242-620">Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.</span><span class="sxs-lookup"><span data-stu-id="05242-620">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="05242-621">VI-Einfügemodus: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="05242-621">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="05242-622">VI-Befehlsmodus: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="05242-622">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="05242-623">Vervollständigungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="05242-623">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="05242-624">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="05242-624">Complete</span></span>

<span data-ttu-id="05242-625">Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="05242-625">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="05242-626">Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet.</span><span class="sxs-lookup"><span data-stu-id="05242-626">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="05242-627">Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05242-627">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="05242-628">Ansehen `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="05242-628">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="05242-629">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="05242-629">MenuComplete</span></span>

<span data-ttu-id="05242-630">Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="05242-630">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="05242-631">Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet.</span><span class="sxs-lookup"><span data-stu-id="05242-631">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="05242-632">Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05242-632">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="05242-633">Cmd: `<Ctrl+@>` , `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="05242-633">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="05242-634">Ansehen `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="05242-634">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="05242-635">Possiblecompletions</span><span class="sxs-lookup"><span data-stu-id="05242-635">PossibleCompletions</span></span>

<span data-ttu-id="05242-636">Hiermit wird die Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05242-636">Display the list of possible completions.</span></span>

- <span data-ttu-id="05242-637">Ansehen `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="05242-637">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="05242-638">VI-Einfügemodus: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="05242-638">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="05242-639">VI-Befehlsmodus: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="05242-639">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="05242-640">Tabcompletenext</span><span class="sxs-lookup"><span data-stu-id="05242-640">TabCompleteNext</span></span>

<span data-ttu-id="05242-641">Es wurde versucht, den Text, der den Cursor umgibt, mit der nächsten verfügbaren Beendigung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="05242-641">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="05242-642">Befehl: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="05242-642">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="05242-643">VI-Befehlsmodus: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="05242-643">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="05242-644">Tabcompleteprevious</span><span class="sxs-lookup"><span data-stu-id="05242-644">TabCompletePrevious</span></span>

<span data-ttu-id="05242-645">Versuchen Sie, den Text, der den Cursor umgibt, mit dem vorherigen verfügbaren Abschluss abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="05242-645">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="05242-646">Befehl: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="05242-646">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="05242-647">VI-Befehlsmodus: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="05242-647">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="05242-648">Vitabcompletenext</span><span class="sxs-lookup"><span data-stu-id="05242-648">ViTabCompleteNext</span></span>

<span data-ttu-id="05242-649">Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompletenext auf.</span><span class="sxs-lookup"><span data-stu-id="05242-649">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="05242-650">VI-Einfügemodus: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="05242-650">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="05242-651">Vitabcompleteprevious</span><span class="sxs-lookup"><span data-stu-id="05242-651">ViTabCompletePrevious</span></span>

<span data-ttu-id="05242-652">Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompleteprevious auf.</span><span class="sxs-lookup"><span data-stu-id="05242-652">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="05242-653">VI-Einfügemodus: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="05242-653">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="prediction-functions"></a><span data-ttu-id="05242-654">Vorhersagefunktionen</span><span class="sxs-lookup"><span data-stu-id="05242-654">Prediction functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="05242-655">Akzeptnextsuggestionword</span><span class="sxs-lookup"><span data-stu-id="05242-655">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="05242-656">Wenn Sie `InlineView` als Ansichts Stil für die Vorhersage verwenden, akzeptieren Sie das nächste Wort des Inline Vorschlags.</span><span class="sxs-lookup"><span data-stu-id="05242-656">When using `InlineView` as the view style for prediction, accept the next word of the inline suggestion.</span></span>

- <span data-ttu-id="05242-657">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-657">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="05242-658">Accept-Vorschlag</span><span class="sxs-lookup"><span data-stu-id="05242-658">AcceptSuggestion</span></span>

<span data-ttu-id="05242-659">Wenn Sie `InlineView` als Ansichts Stil für Vorhersagen verwenden, müssen Sie den aktuellen Inline Vorschlag akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="05242-659">When using `InlineView` as the view style for prediction, accept the current inline suggestion.</span></span>

- <span data-ttu-id="05242-660">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-660">Function is unbound.</span></span>

### <a name="nextsuggestion"></a><span data-ttu-id="05242-661">Nextvorschlag</span><span class="sxs-lookup"><span data-stu-id="05242-661">NextSuggestion</span></span>

<span data-ttu-id="05242-662">Wenn Sie `ListView` als Ansichts Stil für die Vorhersage verwenden, navigieren Sie zum nächsten Vorschlag in der Liste.</span><span class="sxs-lookup"><span data-stu-id="05242-662">When using `ListView` as the view style for prediction, navigate to the next suggestion in the list.</span></span>

- <span data-ttu-id="05242-663">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-663">Function is unbound.</span></span>

### <a name="previoussuggestion"></a><span data-ttu-id="05242-664">Previousvorschlag</span><span class="sxs-lookup"><span data-stu-id="05242-664">PreviousSuggestion</span></span>

<span data-ttu-id="05242-665">Wenn Sie `ListView` als Ansichts Stil für die Vorhersage verwenden, navigieren Sie zu dem vorherigen Vorschlag in der Liste.</span><span class="sxs-lookup"><span data-stu-id="05242-665">When using `ListView` as the view style for prediction, navigate to the previous suggestion in the list.</span></span>

- <span data-ttu-id="05242-666">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-666">Function is unbound.</span></span>

### <a name="switchpredictionview"></a><span data-ttu-id="05242-667">Switchvorhertionview</span><span class="sxs-lookup"><span data-stu-id="05242-667">SwitchPredictionView</span></span>

<span data-ttu-id="05242-668">Ändern Sie den Ansichts Stil für die Vorhersage zwischen `InlineView` und `ListView` .</span><span class="sxs-lookup"><span data-stu-id="05242-668">Switch the view style for prediction between `InlineView` and `ListView`.</span></span>

- <span data-ttu-id="05242-669">Befehl: `<F2>`</span><span class="sxs-lookup"><span data-stu-id="05242-669">Cmd: `<F2>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="05242-670">Sonstige Funktionen</span><span class="sxs-lookup"><span data-stu-id="05242-670">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="05242-671">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="05242-671">CaptureScreen</span></span>

<span data-ttu-id="05242-672">Interaktive Bildschirmaufnahme starten-nach oben/nach-unten-Pfeile Select Lines, Enter kopiert markierten Text in die Zwischenablage als Text und HTML.</span><span class="sxs-lookup"><span data-stu-id="05242-672">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="05242-673">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-673">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="05242-674">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="05242-674">ClearScreen</span></span>

<span data-ttu-id="05242-675">Löschen Sie den Bildschirm, und zeichnen Sie die aktuelle Zeile am oberen Rand des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="05242-675">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="05242-676">Befehl: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="05242-676">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="05242-677">Ansehen `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="05242-677">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="05242-678">VI-Einfügemodus: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="05242-678">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="05242-679">VI-Befehlsmodus: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="05242-679">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="05242-680">Digitargument</span><span class="sxs-lookup"><span data-stu-id="05242-680">DigitArgument</span></span>

<span data-ttu-id="05242-681">Starten Sie ein neues Ziffern Argument, das an andere Funktionen übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="05242-681">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="05242-682">Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="05242-682">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="05242-683">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="05242-683">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="05242-684">VI-Befehlsmodus: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="05242-684">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="05242-685">Invokeprompt</span><span class="sxs-lookup"><span data-stu-id="05242-685">InvokePrompt</span></span>

<span data-ttu-id="05242-686">Löscht die aktuelle Eingabeaufforderung und ruft die prompt-Funktion auf, um die Eingabeaufforderung erneut anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="05242-686">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="05242-687">Nützlich für benutzerdefinierte Schlüssel Handler, die den Zustand ändern, z. b. Ändern des aktuellen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="05242-687">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="05242-688">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-688">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="05242-689">Scrolldisplaydown</span><span class="sxs-lookup"><span data-stu-id="05242-689">ScrollDisplayDown</span></span>

<span data-ttu-id="05242-690">Scrollen Sie in der Anzeige einen Bildschirm nach unten.</span><span class="sxs-lookup"><span data-stu-id="05242-690">Scroll the display down one screen.</span></span>

- <span data-ttu-id="05242-691">Befehl: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="05242-691">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="05242-692">Ansehen `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="05242-692">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="05242-693">Scrolldisplaydownline</span><span class="sxs-lookup"><span data-stu-id="05242-693">ScrollDisplayDownLine</span></span>

<span data-ttu-id="05242-694">Scrollen Sie in der Anzeige um eine Zeile nach unten.</span><span class="sxs-lookup"><span data-stu-id="05242-694">Scroll the display down one line.</span></span>

- <span data-ttu-id="05242-695">Befehl: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="05242-695">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="05242-696">Ansehen `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="05242-696">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="05242-697">Scrolldisplaytcursor</span><span class="sxs-lookup"><span data-stu-id="05242-697">ScrollDisplayToCursor</span></span>

<span data-ttu-id="05242-698">Scrollen Sie in der Anzeige zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="05242-698">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="05242-699">Ansehen `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="05242-699">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="05242-700">Scrolldisplaytop</span><span class="sxs-lookup"><span data-stu-id="05242-700">ScrollDisplayTop</span></span>

<span data-ttu-id="05242-701">Scrollen Sie in der Anzeige nach oben.</span><span class="sxs-lookup"><span data-stu-id="05242-701">Scroll the display to the top.</span></span>

- <span data-ttu-id="05242-702">Ansehen `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="05242-702">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="05242-703">Scrolldisplayup</span><span class="sxs-lookup"><span data-stu-id="05242-703">ScrollDisplayUp</span></span>

<span data-ttu-id="05242-704">Scrollen Sie einen Bildschirm nach oben.</span><span class="sxs-lookup"><span data-stu-id="05242-704">Scroll the display up one screen.</span></span>

- <span data-ttu-id="05242-705">Befehl: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="05242-705">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="05242-706">Ansehen `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="05242-706">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="05242-707">Scrolldisplayupline</span><span class="sxs-lookup"><span data-stu-id="05242-707">ScrollDisplayUpLine</span></span>

<span data-ttu-id="05242-708">Scrollen Sie in der Anzeige um eine Zeile nach oben.</span><span class="sxs-lookup"><span data-stu-id="05242-708">Scroll the display up one line.</span></span>

- <span data-ttu-id="05242-709">Befehl: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="05242-709">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="05242-710">Ansehen `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="05242-710">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="05242-711">Selfinsert</span><span class="sxs-lookup"><span data-stu-id="05242-711">SelfInsert</span></span>

<span data-ttu-id="05242-712">Fügen Sie den Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="05242-712">Insert the key.</span></span>

- <span data-ttu-id="05242-713">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-713">Function is unbound.</span></span>

### <a name="showcommandhelp"></a><span data-ttu-id="05242-714">Showcommandhelp</span><span class="sxs-lookup"><span data-stu-id="05242-714">ShowCommandHelp</span></span>

<span data-ttu-id="05242-715">Bietet eine Ansicht der vollständigen Cmdlet-Hilfe.</span><span class="sxs-lookup"><span data-stu-id="05242-715">Provides a view of full cmdlet help.</span></span> <span data-ttu-id="05242-716">Wenn sich der Cursor am Ende eines vollständig erweiterten Parameters befindet, wird durch das Drücken der `<F1>` Taste die Anzeige der Hilfe an der Position dieses Parameters positioniert.</span><span class="sxs-lookup"><span data-stu-id="05242-716">When the cursor is at the end of a fully-expanded parameter, hitting the `<F1>` key positions the display of help at the location of that parameter.</span></span>

<span data-ttu-id="05242-717">Die Hilfe wird mithilfe eines Pager von **Microsoft. PowerShell. Pager** auf einem alternativen Bildschirm Puffer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05242-717">The help is displayed on an alternate screen buffer using a Pager from **Microsoft.PowerShell.Pager**.</span></span> <span data-ttu-id="05242-718">Wenn Sie den Pager beenden, werden Sie auf dem ursprünglichen Bildschirm an die ursprüngliche Cursorposition zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="05242-718">When you exit the pager you are returned to the original cursor position on the original screen.</span></span> <span data-ttu-id="05242-719">Dieser Pager funktioniert nur in modernen Terminalanwendungen wie z. b. [Windows-Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701).</span><span class="sxs-lookup"><span data-stu-id="05242-719">This pager only works in modern terminal applications such as [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701).</span></span>

- <span data-ttu-id="05242-720">Befehl: `<F1>`</span><span class="sxs-lookup"><span data-stu-id="05242-720">Cmd: `<F1>`</span></span>
- <span data-ttu-id="05242-721">Ansehen `<F1>`</span><span class="sxs-lookup"><span data-stu-id="05242-721">Emacs: `<F1>`</span></span>
- <span data-ttu-id="05242-722">VI-Einfügemodus: `<F1>`</span><span class="sxs-lookup"><span data-stu-id="05242-722">Vi insert mode: `<F1>`</span></span>
- <span data-ttu-id="05242-723">VI-Befehlsmodus: `<F1>`</span><span class="sxs-lookup"><span data-stu-id="05242-723">Vi command mode: `<F1>`</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="05242-724">Showkeybindungen</span><span class="sxs-lookup"><span data-stu-id="05242-724">ShowKeyBindings</span></span>

<span data-ttu-id="05242-725">Alle gebundenen Schlüssel anzeigen.</span><span class="sxs-lookup"><span data-stu-id="05242-725">Show all bound keys.</span></span>

- <span data-ttu-id="05242-726">Befehl: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="05242-726">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="05242-727">Ansehen `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="05242-727">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="05242-728">VI-Einfügemodus: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="05242-728">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="showparameterhelp"></a><span data-ttu-id="05242-729">Showparameterhelp</span><span class="sxs-lookup"><span data-stu-id="05242-729">ShowParameterHelp</span></span>

<span data-ttu-id="05242-730">Bietet dynamische Hilfe für Parameter, indem Sie unter der aktuellen Befehlszeile wie angezeigt wird `MenuComplete` .</span><span class="sxs-lookup"><span data-stu-id="05242-730">Provides dynamic help for parameters by showing it below the current command line like `MenuComplete`.</span></span> <span data-ttu-id="05242-731">Der Cursor muss sich am Ende des vollständig erweiterten Parameter namens befinden, wenn Sie die `<Alt+h>` Taste drücken.</span><span class="sxs-lookup"><span data-stu-id="05242-731">The cursor must be at the end of the fully-expanded parameter name when you press the `<Alt+h>` key.</span></span>

- <span data-ttu-id="05242-732">Befehl: `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="05242-732">Cmd: `<Alt+h>`</span></span>
- <span data-ttu-id="05242-733">Ansehen `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="05242-733">Emacs: `<Alt+h>`</span></span>
- <span data-ttu-id="05242-734">VI-Einfügemodus: `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="05242-734">Vi insert mode: `<Alt+h>`</span></span>
- <span data-ttu-id="05242-735">VI-Befehlsmodus: `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="05242-735">Vi command mode: `<Alt+h>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="05242-736">Vicommandmode</span><span class="sxs-lookup"><span data-stu-id="05242-736">ViCommandMode</span></span>

<span data-ttu-id="05242-737">Wechseln Sie in den aktuellen Betriebsmodus von Vi-Insert zu VI-Command.</span><span class="sxs-lookup"><span data-stu-id="05242-737">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="05242-738">VI-Einfügemodus: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="05242-738">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="05242-739">Vidigitargumentinchord</span><span class="sxs-lookup"><span data-stu-id="05242-739">ViDigitArgumentInChord</span></span>

<span data-ttu-id="05242-740">Startet ein neues Ziffern Argument, das in einem der VI-Akkorde an andere Funktionen übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="05242-740">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="05242-741">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-741">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="05242-742">Vieditvisuell</span><span class="sxs-lookup"><span data-stu-id="05242-742">ViEditVisually</span></span>

<span data-ttu-id="05242-743">Bearbeiten Sie die Befehlszeile in einem Text-Editor, der durch $ENV: Editor oder $env: Visual angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="05242-743">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="05242-744">Ansehen `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="05242-744">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="05242-745">VI-Befehlsmodus: `<v>`</span><span class="sxs-lookup"><span data-stu-id="05242-745">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="05242-746">Viexit</span><span class="sxs-lookup"><span data-stu-id="05242-746">ViExit</span></span>

<span data-ttu-id="05242-747">Beendet die Shell.</span><span class="sxs-lookup"><span data-stu-id="05242-747">Exits the shell.</span></span>

- <span data-ttu-id="05242-748">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-748">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="05242-749">Viinsertmode</span><span class="sxs-lookup"><span data-stu-id="05242-749">ViInsertMode</span></span>

<span data-ttu-id="05242-750">Wechselt in den Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="05242-750">Switch to Insert mode.</span></span>

- <span data-ttu-id="05242-751">VI-Befehlsmodus: `<i>`</span><span class="sxs-lookup"><span data-stu-id="05242-751">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="05242-752">Whatiskey</span><span class="sxs-lookup"><span data-stu-id="05242-752">WhatIsKey</span></span>

<span data-ttu-id="05242-753">Lesen Sie einen Schlüssel, und teilen Sie mir mit, wofür der Schlüssel gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="05242-753">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="05242-754">Befehl: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="05242-754">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="05242-755">Ansehen `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="05242-755">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="05242-756">Auswahl Funktionen</span><span class="sxs-lookup"><span data-stu-id="05242-756">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="05242-757">Exchangepointandmark</span><span class="sxs-lookup"><span data-stu-id="05242-757">ExchangePointAndMark</span></span>

<span data-ttu-id="05242-758">Der Cursor wird an der Position der Markierung platziert, und die Markierung wird an die Position des Cursors verschoben.</span><span class="sxs-lookup"><span data-stu-id="05242-758">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="05242-759">Ansehen `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="05242-759">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="05242-760">SelectAll</span><span class="sxs-lookup"><span data-stu-id="05242-760">SelectAll</span></span>

<span data-ttu-id="05242-761">Wählen Sie die gesamte Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="05242-761">Select the entire line.</span></span>

- <span data-ttu-id="05242-762">Befehl: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="05242-762">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="05242-763">Selectbackwardchar</span><span class="sxs-lookup"><span data-stu-id="05242-763">SelectBackwardChar</span></span>

<span data-ttu-id="05242-764">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Zeichen einschließt.</span><span class="sxs-lookup"><span data-stu-id="05242-764">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="05242-765">Befehl: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-765">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="05242-766">Ansehen `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-766">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="05242-767">Selectbackwardsline</span><span class="sxs-lookup"><span data-stu-id="05242-767">SelectBackwardsLine</span></span>

<span data-ttu-id="05242-768">Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an den Anfang der Zeile eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="05242-768">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="05242-769">Befehl: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="05242-769">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="05242-770">Ansehen `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="05242-770">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="05242-771">Selectbackwardword</span><span class="sxs-lookup"><span data-stu-id="05242-771">SelectBackwardWord</span></span>

<span data-ttu-id="05242-772">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort enthält.</span><span class="sxs-lookup"><span data-stu-id="05242-772">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="05242-773">Befehl: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-773">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="05242-774">Ansehen `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="05242-774">Emacs: `<Alt+B>`</span></span>

### <a name="selectcommandargument"></a><span data-ttu-id="05242-775">Selectcommandargument</span><span class="sxs-lookup"><span data-stu-id="05242-775">SelectCommandArgument</span></span>

<span data-ttu-id="05242-776">Erstellen Sie die visuelle Auswahl der Befehlsargumente.</span><span class="sxs-lookup"><span data-stu-id="05242-776">Make visual selection of the command arguments.</span></span> <span data-ttu-id="05242-777">Die Auswahl von Argumenten wird in einem Skriptblock festgelegt.</span><span class="sxs-lookup"><span data-stu-id="05242-777">Selection of arguments is scoped within a script block.</span></span> <span data-ttu-id="05242-778">Basierend auf der Cursorposition wird vom innersten Skriptblock nach dem äußersten Skriptblock gesucht und beendet, wenn Argumente in einem Skriptblock Bereich gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="05242-778">Based on the cursor position, it searches from the innermost script block to the outmost script block, and stops when it finds any arguments in a script block scope.</span></span>

<span data-ttu-id="05242-779">Diese Funktion berücksichtigt digitargument.</span><span class="sxs-lookup"><span data-stu-id="05242-779">This function honors DigitArgument.</span></span> <span data-ttu-id="05242-780">Die positiven oder negativen Argument Werte werden als vorwärts-oder rückwärts Offsets vom aktuell ausgewählten Argument oder von der aktuellen Cursorposition, wenn kein Argument ausgewählt ist, behandelt.</span><span class="sxs-lookup"><span data-stu-id="05242-780">It treats the positive or negative argument values as the forward or backward offsets from the currently selected argument, or from the current cursor position when no argument is selected.</span></span>

- <span data-ttu-id="05242-781">Befehl: `<Alt+a>`</span><span class="sxs-lookup"><span data-stu-id="05242-781">Cmd: `<Alt+a>`</span></span>
- <span data-ttu-id="05242-782">Ansehen `<Alt+a>`</span><span class="sxs-lookup"><span data-stu-id="05242-782">Emacs: `<Alt+a>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="05242-783">Selectforwardchar</span><span class="sxs-lookup"><span data-stu-id="05242-783">SelectForwardChar</span></span>

<span data-ttu-id="05242-784">Passen Sie die aktuelle Auswahl an, um das nächste Zeichen einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="05242-784">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="05242-785">Befehl: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-785">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="05242-786">Ansehen `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-786">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="05242-787">Selectforwardword</span><span class="sxs-lookup"><span data-stu-id="05242-787">SelectForwardWord</span></span>

<span data-ttu-id="05242-788">Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mit forwardword einschließt.</span><span class="sxs-lookup"><span data-stu-id="05242-788">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="05242-789">Ansehen `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="05242-789">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="05242-790">SelectLine</span><span class="sxs-lookup"><span data-stu-id="05242-790">SelectLine</span></span>

<span data-ttu-id="05242-791">Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an das Ende der Zeile eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="05242-791">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="05242-792">Befehl: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="05242-792">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="05242-793">Ansehen `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="05242-793">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="05242-794">Selectnextword</span><span class="sxs-lookup"><span data-stu-id="05242-794">SelectNextWord</span></span>

<span data-ttu-id="05242-795">Passen Sie die aktuelle Auswahl an das nächste Wort an.</span><span class="sxs-lookup"><span data-stu-id="05242-795">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="05242-796">Befehl: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="05242-796">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="05242-797">Selectshellbackwardword</span><span class="sxs-lookup"><span data-stu-id="05242-797">SelectShellBackwardWord</span></span>

<span data-ttu-id="05242-798">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort mithilfe von shellbackwardword einschließt.</span><span class="sxs-lookup"><span data-stu-id="05242-798">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="05242-799">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-799">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="05242-800">Selectshellforwardword</span><span class="sxs-lookup"><span data-stu-id="05242-800">SelectShellForwardWord</span></span>

<span data-ttu-id="05242-801">Passen Sie die aktuelle Auswahl so an, dass das nächste Wort mithilfe von shellforwardword eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="05242-801">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="05242-802">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-802">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="05242-803">Selectshellnextword</span><span class="sxs-lookup"><span data-stu-id="05242-803">SelectShellNextWord</span></span>

<span data-ttu-id="05242-804">Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mithilfe von shellnextword einschließt.</span><span class="sxs-lookup"><span data-stu-id="05242-804">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="05242-805">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="05242-805">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="05242-806">Setmark</span><span class="sxs-lookup"><span data-stu-id="05242-806">SetMark</span></span>

<span data-ttu-id="05242-807">Markieren Sie die aktuelle Position des Cursors für die Verwendung in einem nachfolgenden Bearbeitungs Befehl.</span><span class="sxs-lookup"><span data-stu-id="05242-807">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="05242-808">Ansehen `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="05242-808">Emacs: `<Ctrl+@>`</span></span>

## <a name="predictive-intellisense-functions"></a><span data-ttu-id="05242-809">Predictive IntelliSense-Funktionen</span><span class="sxs-lookup"><span data-stu-id="05242-809">Predictive IntelliSense functions</span></span>

> [!NOTE]
> <span data-ttu-id="05242-810">Predictive IntelliSense muss aktiviert werden, damit diese Funktionen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="05242-810">Predictive IntelliSense needs to be enabled to use these functions.</span></span>

### <a name="acceptnextwordsuggestion"></a><span data-ttu-id="05242-811">Accept-nextwordsuggestion</span><span class="sxs-lookup"><span data-stu-id="05242-811">AcceptNextWordSuggestion</span></span>

<span data-ttu-id="05242-812">Akzeptiert das nächste Wort des Inline Vorschlags aus Predictive IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="05242-812">Accepts the next word of the inline suggestion from Predictive IntelliSense.</span></span>
<span data-ttu-id="05242-813">Diese Funktion kann mit <kbd>STRG</kbd> + <kbd>F</kbd> gebunden werden, indem der folgende Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="05242-813">This function can be bound with <kbd>Ctrl</kbd>+<kbd>F</kbd> by running the following command.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord "Ctrl+f" -Function ForwardWord
```

### <a name="acceptsuggestion"></a><span data-ttu-id="05242-814">Accept-Vorschlag</span><span class="sxs-lookup"><span data-stu-id="05242-814">AcceptSuggestion</span></span>

<span data-ttu-id="05242-815">Akzeptiert den aktuellen Inline Vorschlag von Predictive IntelliSense durch Drücken von <kbd>RIGHTARROW</kbd> , wenn sich der Cursor am Ende der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="05242-815">Accepts the current inline suggestion from Predictive IntelliSense by pressing <kbd>RightArrow</kbd> when the cursor is at the end of the current line.</span></span>

## <a name="search-functions"></a><span data-ttu-id="05242-816">Suchfunktionen</span><span class="sxs-lookup"><span data-stu-id="05242-816">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="05242-817">Merkmal Suche</span><span class="sxs-lookup"><span data-stu-id="05242-817">CharacterSearch</span></span>

<span data-ttu-id="05242-818">Lesen Sie ein Zeichen, und suchen Sie nach dem nächsten Vorkommen dieses Zeichens.</span><span class="sxs-lookup"><span data-stu-id="05242-818">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="05242-819">Wenn ein Argument angegeben ist, suchen Sie nach vorn (oder rückwärts, wenn negativ) für das n-te vorkommen.</span><span class="sxs-lookup"><span data-stu-id="05242-819">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="05242-820">Befehl: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="05242-820">Cmd: `<F3>`</span></span>
- <span data-ttu-id="05242-821">Ansehen `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="05242-821">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="05242-822">VI-Einfügemodus: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="05242-822">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="05242-823">VI-Befehlsmodus: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="05242-823">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="05242-824">Merkmal searchrückwärts</span><span class="sxs-lookup"><span data-stu-id="05242-824">CharacterSearchBackward</span></span>

<span data-ttu-id="05242-825">Liest ein Zeichen und sucht rückwärts nach dem nächsten Vorkommen dieses Zeichens.</span><span class="sxs-lookup"><span data-stu-id="05242-825">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="05242-826">Wenn ein Argument angegeben wird, suchen Sie nach hinten (oder vorwärts, wenn negativ).</span><span class="sxs-lookup"><span data-stu-id="05242-826">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="05242-827">Befehl: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="05242-827">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="05242-828">Ansehen `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="05242-828">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="05242-829">VI-Einfügemodus: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="05242-829">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="05242-830">VI-Befehlsmodus: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="05242-830">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="05242-831">Repeatlastcharsearch</span><span class="sxs-lookup"><span data-stu-id="05242-831">RepeatLastCharSearch</span></span>

<span data-ttu-id="05242-832">Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche.</span><span class="sxs-lookup"><span data-stu-id="05242-832">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="05242-833">VI-Befehlsmodus: `<;>`</span><span class="sxs-lookup"><span data-stu-id="05242-833">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="05242-834">Repeatlastcharsearchabwärts</span><span class="sxs-lookup"><span data-stu-id="05242-834">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="05242-835">Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche, aber in umgekehrter Richtung.</span><span class="sxs-lookup"><span data-stu-id="05242-835">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="05242-836">VI-Befehlsmodus: `<,>`</span><span class="sxs-lookup"><span data-stu-id="05242-836">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="05242-837">Repeatsearch</span><span class="sxs-lookup"><span data-stu-id="05242-837">RepeatSearch</span></span>

<span data-ttu-id="05242-838">Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="05242-838">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="05242-839">VI-Befehlsmodus: `<n>`</span><span class="sxs-lookup"><span data-stu-id="05242-839">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="05242-840">Repeatsearchrückwärts</span><span class="sxs-lookup"><span data-stu-id="05242-840">RepeatSearchBackward</span></span>

<span data-ttu-id="05242-841">Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="05242-841">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="05242-842">VI-Befehlsmodus: `<N>`</span><span class="sxs-lookup"><span data-stu-id="05242-842">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="05242-843">Searchchar</span><span class="sxs-lookup"><span data-stu-id="05242-843">SearchChar</span></span>

<span data-ttu-id="05242-844">Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="05242-844">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="05242-845">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="05242-845">This is for 't' functionality.</span></span>

- <span data-ttu-id="05242-846">VI-Befehlsmodus: `<f>`</span><span class="sxs-lookup"><span data-stu-id="05242-846">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="05242-847">Searchcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="05242-847">SearchCharBackward</span></span>

<span data-ttu-id="05242-848">Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück.</span><span class="sxs-lookup"><span data-stu-id="05242-848">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="05242-849">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="05242-849">This is for 'T' functionality.</span></span>

- <span data-ttu-id="05242-850">VI-Befehlsmodus: `<F>`</span><span class="sxs-lookup"><span data-stu-id="05242-850">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="05242-851">Searchcharbackwardwithbackoff</span><span class="sxs-lookup"><span data-stu-id="05242-851">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="05242-852">Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück.</span><span class="sxs-lookup"><span data-stu-id="05242-852">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="05242-853">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="05242-853">This is for 'T' functionality.</span></span>

- <span data-ttu-id="05242-854">VI-Befehlsmodus: `<T>`</span><span class="sxs-lookup"><span data-stu-id="05242-854">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="05242-855">Searchcharwithbackoff</span><span class="sxs-lookup"><span data-stu-id="05242-855">SearchCharWithBackoff</span></span>

<span data-ttu-id="05242-856">Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="05242-856">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="05242-857">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="05242-857">This is for 't' functionality.</span></span>

- <span data-ttu-id="05242-858">VI-Befehlsmodus: `<t>`</span><span class="sxs-lookup"><span data-stu-id="05242-858">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="05242-859">SearchForward</span><span class="sxs-lookup"><span data-stu-id="05242-859">SearchForward</span></span>

<span data-ttu-id="05242-860">Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.</span><span class="sxs-lookup"><span data-stu-id="05242-860">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="05242-861">VI-Einfügemodus: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="05242-861">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="05242-862">VI-Befehlsmodus: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="05242-862">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="05242-863">Benutzerdefinierte Tastenbindungen</span><span class="sxs-lookup"><span data-stu-id="05242-863">Custom Key Bindings</span></span>

<span data-ttu-id="05242-864">Psread Line unterstützt benutzerdefinierte Tastenbindungen mithilfe des Cmdlets `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="05242-864">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="05242-865">Die meisten benutzerdefinierten Tastenbindungen wenden eine der oben genannten Funktionen an, z. b.</span><span class="sxs-lookup"><span data-stu-id="05242-865">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="05242-866">Sie können einen ScriptBlock an einen Schlüssel binden.</span><span class="sxs-lookup"><span data-stu-id="05242-866">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="05242-867">Der ScriptBlock kann beliebig viele Aufgaben erledigen.</span><span class="sxs-lookup"><span data-stu-id="05242-867">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="05242-868">Einige nützliche Beispiele sind u.a.</span><span class="sxs-lookup"><span data-stu-id="05242-868">Some useful examples include</span></span>

- <span data-ttu-id="05242-869">Bearbeiten der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="05242-869">edit the command line</span></span>
- <span data-ttu-id="05242-870">Öffnen eines neuen Fensters (z. b. "Hilfe")</span><span class="sxs-lookup"><span data-stu-id="05242-870">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="05242-871">Ändern der Verzeichnisse ohne Änderung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="05242-871">change directories without changing the command line</span></span>

<span data-ttu-id="05242-872">Der ScriptBlock empfängt zwei Argumente:</span><span class="sxs-lookup"><span data-stu-id="05242-872">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="05242-873">`$key` -Ein **[ConsoleKeyInfo]** -Objekt, das der Schlüssel ist, der die benutzerdefinierte Bindung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="05242-873">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="05242-874">Wenn Sie denselben ScriptBlock an mehrere Schlüssel binden und abhängig vom Schlüssel verschiedene Aktionen ausführen müssen, können Sie $Key überprüfen.</span><span class="sxs-lookup"><span data-stu-id="05242-874">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="05242-875">Viele benutzerdefinierte Bindungen ignorieren dieses Argument.</span><span class="sxs-lookup"><span data-stu-id="05242-875">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="05242-876">`$arg` -Ein beliebiges Argument.</span><span class="sxs-lookup"><span data-stu-id="05242-876">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="05242-877">In den meisten Fällen ist dies ein ganzzahliges Argument, das der Benutzer von den Schlüsselbindungen digitargument übergibt.</span><span class="sxs-lookup"><span data-stu-id="05242-877">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="05242-878">Wenn die Bindung keine Argumente akzeptiert, ist es sinnvoll, dieses Argument zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="05242-878">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="05242-879">Sehen wir uns ein Beispiel an, in dem eine Befehlszeile zum Verlauf hinzugefügt wird, ohne sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="05242-879">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="05242-880">Dies ist nützlich, wenn Sie vergessen haben, etwas zu tun, ohne die Befehlszeile, die Sie bereits eingegeben haben, erneut eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="05242-880">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="05242-881">In der Datei `SamplePSReadLineProfile.ps1` , die im psread Line-Modul Ordner installiert ist, werden viele weitere Beispiele angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05242-881">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="05242-882">Die meisten Tastenbindungen verwenden einige Hilfsfunktionen zum Bearbeiten der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="05242-882">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="05242-883">Diese APIs werden im nächsten Abschnitt dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="05242-883">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="05242-884">APIs für die benutzerdefinierte Schlüssel Bindungs Unterstützung</span><span class="sxs-lookup"><span data-stu-id="05242-884">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="05242-885">Die folgenden Funktionen sind in Microsoft. PowerShell. psconsolereadline öffentlich, können jedoch nicht direkt an einen Schlüssel gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="05242-885">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="05242-886">Die meisten sind in benutzerdefinierten Tastenkombinationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="05242-886">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="05242-887">Fügen Sie eine Befehlszeile zum Verlauf hinzu, ohne sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="05242-887">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="05242-888">Löschen Sie den Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="05242-888">Clear the kill-ring.</span></span>  <span data-ttu-id="05242-889">Dies wird größtenteils zum Testen verwendet.</span><span class="sxs-lookup"><span data-stu-id="05242-889">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="05242-890">Löschen Sie die Längen Zeichen aus dem Startmenü.</span><span class="sxs-lookup"><span data-stu-id="05242-890">Delete length characters from start.</span></span>  <span data-ttu-id="05242-891">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="05242-891">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="05242-892">Führen Sie die Aktion "Ding" basierend auf der Benutzereinstellung aus.</span><span class="sxs-lookup"><span data-stu-id="05242-892">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="05242-893">Diese beiden Funktionen rufen nützliche Informationen über den aktuellen Status des Eingabe Puffers ab.</span><span class="sxs-lookup"><span data-stu-id="05242-893">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="05242-894">Der erste wird häufiger für einfache Fälle verwendet.</span><span class="sxs-lookup"><span data-stu-id="05242-894">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="05242-895">Die zweite wird verwendet, wenn ihre Bindung einen fortgeschrittenen Vorgang mit der AST bewirkt.</span><span class="sxs-lookup"><span data-stu-id="05242-895">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="05242-896">Diese beiden Funktionen werden von verwendet `Get-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="05242-896">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="05242-897">Der erste wird verwendet, um alle Tastenbindungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="05242-897">The first is used to get all key bindings.</span></span> <span data-ttu-id="05242-898">Die zweite wird verwendet, um bestimmte Tastenbindungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="05242-898">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="05242-899">Diese Funktion wird von Get-PSReadLineOption verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.</span><span class="sxs-lookup"><span data-stu-id="05242-899">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="05242-900">Wenn in der Befehlszeile keine Auswahl vorhanden ist, wird-1 sowohl in Start als auch in der Länge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="05242-900">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="05242-901">Wenn eine Auswahl in der Befehlszeile vorhanden ist, werden Start und Länge der Auswahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="05242-901">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="05242-902">Fügen Sie am Cursor ein Zeichen oder eine Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="05242-902">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="05242-903">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="05242-903">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="05242-904">Dies ist der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="05242-904">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="05242-905">Sie unterstützt keine Rekursion und ist daher in einer benutzerdefinierten schlüsselbindung nicht nützlich.</span><span class="sxs-lookup"><span data-stu-id="05242-905">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="05242-906">Diese Funktion wird von Remove-PSReadLineKeyHandler verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.</span><span class="sxs-lookup"><span data-stu-id="05242-906">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="05242-907">Ersetzen Sie einige der Eingaben.</span><span class="sxs-lookup"><span data-stu-id="05242-907">Replace some of the input.</span></span> <span data-ttu-id="05242-908">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="05242-908">This operation supports undo/redo.</span></span> <span data-ttu-id="05242-909">Dies wird als "Delete", gefolgt von INSERT, bevorzugt, da es als einzelne Aktion für "Rückgängig" behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="05242-909">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="05242-910">Bewegen Sie den Cursor in den angegebenen Offset.</span><span class="sxs-lookup"><span data-stu-id="05242-910">Move the cursor to the given offset.</span></span> <span data-ttu-id="05242-911">Cursor Bewegung wird nicht für Rückgängigmachen nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="05242-911">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="05242-912">Bei dieser Funktion handelt es sich um eine Hilfsmethode, die vom Cmdlet Set-psread lineoption verwendet wird. Sie kann jedoch für eine benutzerdefinierte schlüsselbindung nützlich sein, die eine Einstellung vorübergehend ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="05242-912">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="05242-913">Diese Hilfsmethode wird für benutzerdefinierte Bindungen verwendet, die digitargument berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="05242-913">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="05242-914">Ein typischer-Rückruf sieht wie folgt aus</span><span class="sxs-lookup"><span data-stu-id="05242-914">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="notes"></a><span data-ttu-id="05242-915">Notizen</span><span class="sxs-lookup"><span data-stu-id="05242-915">Notes</span></span>

### <a name="command-history"></a><span data-ttu-id="05242-916">Befehlsverlauf</span><span class="sxs-lookup"><span data-stu-id="05242-916">Command History</span></span>

<span data-ttu-id="05242-917">Psleseline verwaltet eine Verlaufs Datei, die alle Befehle und Daten enthält, die Sie in der Befehlszeile eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="05242-917">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="05242-918">Dies kann vertrauliche Daten einschließlich Kenn Wörtern enthalten.</span><span class="sxs-lookup"><span data-stu-id="05242-918">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="05242-919">Wenn Sie z. b. das `ConvertTo-SecureString` Cmdlet verwenden, wird das Kennwort als nur-Text in der Verlaufs Datei protokolliert.</span><span class="sxs-lookup"><span data-stu-id="05242-919">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="05242-920">Die Verlaufs Dateien sind eine Datei mit dem Namen `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="05242-920">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="05242-921">Auf Windows-Systemen wird die Verlaufs Datei unter gespeichert `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="05242-921">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="05242-922">Auf nicht-Windows-Systemen werden die Verlaufs Dateien unter `$env:XDG_DATA_HOME/powershell/PSReadLine` oder gespeichert `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="05242-922">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="05242-923">Feedback & zu psread Line beitragen</span><span class="sxs-lookup"><span data-stu-id="05242-923">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="05242-924">Psread Line auf GitHub</span><span class="sxs-lookup"><span data-stu-id="05242-924">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="05242-925">Sie können auf der GitHub-Seite eine Pull Request einreichen oder Feedback einreichen.</span><span class="sxs-lookup"><span data-stu-id="05242-925">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="05242-926">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05242-926">See Also</span></span>

<span data-ttu-id="05242-927">"Psread Line" wird stark von der GNU-Bibliothek für die [Zeilen](https://tiswww.case.edu/php/chet/readline/rltop.html) Übereinstimmung beeinflusst</span><span class="sxs-lookup"><span data-stu-id="05242-927">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
