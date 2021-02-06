---
description: Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.
Locale: en-US
ms.date: 11/23/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über psread Line
ms.openlocfilehash: 4836abfec465ba7cdfb6800c1e60104fba19ce08
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "99601099"
---
# <a name="psreadline"></a><span data-ttu-id="4da2b-103">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="4da2b-103">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="4da2b-104">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="4da2b-104">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="4da2b-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4da2b-105">Short Description</span></span>

<span data-ttu-id="4da2b-106">Psleline bietet eine verbesserte Befehlszeilen Bearbeitung in der PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="4da2b-106">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="4da2b-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4da2b-107">Long Description</span></span>

<span data-ttu-id="4da2b-108">Psleline 2,2 bietet eine leistungsfähige Befehlszeilen Bearbeitungsfunktion für die PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="4da2b-108">PSReadLine 2.2 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="4da2b-109">Sie bietet:</span><span class="sxs-lookup"><span data-stu-id="4da2b-109">It provides:</span></span>

- <span data-ttu-id="4da2b-110">Syntax Farbgebung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="4da2b-110">Syntax coloring of the command line</span></span>
- <span data-ttu-id="4da2b-111">Visuelle Hinweise auf Syntax Fehler</span><span class="sxs-lookup"><span data-stu-id="4da2b-111">A visual indication of syntax errors</span></span>
- <span data-ttu-id="4da2b-112">Bessere mehrzeilige Erfahrung (sowohl Bearbeitung als auch Verlauf)</span><span class="sxs-lookup"><span data-stu-id="4da2b-112">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="4da2b-113">Anpassbare Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="4da2b-113">Customizable key bindings</span></span>
- <span data-ttu-id="4da2b-114">Cmd-und Emacs-Modi</span><span class="sxs-lookup"><span data-stu-id="4da2b-114">Cmd and Emacs modes</span></span>
- <span data-ttu-id="4da2b-115">Viele Konfigurationsoptionen</span><span class="sxs-lookup"><span data-stu-id="4da2b-115">Many configuration options</span></span>
- <span data-ttu-id="4da2b-116">Bash-Stil Vervollständigung (optional im cmd-Modus, Standard im Emacs-Modus)</span><span class="sxs-lookup"><span data-stu-id="4da2b-116">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="4da2b-117">Emacs: Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="4da2b-117">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="4da2b-118">PowerShell-tokenbasierte "Wort Bewegung" und "Kill"</span><span class="sxs-lookup"><span data-stu-id="4da2b-118">PowerShell token based "word" movement and kill</span></span>
- <span data-ttu-id="4da2b-119">Predictive IntelliSense</span><span class="sxs-lookup"><span data-stu-id="4da2b-119">Predictive IntelliSense</span></span>

<span data-ttu-id="4da2b-120">Psread Line 2.2.0 Es wurden zwei neue vorhersagbare IntelliSense-Features hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="4da2b-120">PSReadLine 2.2.0 added two new predictive IntelliSense features:</span></span>

- <span data-ttu-id="4da2b-121">Der Parameter " **prätionviewstyle** " wurde hinzugefügt, um die Auswahl der neuen zu ermöglichen `ListView` .</span><span class="sxs-lookup"><span data-stu-id="4da2b-121">Added the **PredictionViewStyle** parameter to allow for the selection of the new `ListView`.</span></span>
- <span data-ttu-id="4da2b-122">Verbindung mit psread Line zu den `CommandPrediction` in PS 7,1 eingeführten APIs, damit Benutzer ein präatormodul importieren können, das die Vorschläge aus einer benutzerdefinierten Quelle darstellen kann.</span><span class="sxs-lookup"><span data-stu-id="4da2b-122">Connected PSReadLine to the `CommandPrediction` APIs introduced in PS 7.1 to allow a user can import a predictor module that can render the suggestions from a custom source.</span></span>

<span data-ttu-id="4da2b-123">Für psread Line ist PowerShell 3,0 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4da2b-123">PSReadLine requires PowerShell 3.0, or newer.</span></span> <span data-ttu-id="4da2b-124">Psleline funktioniert mit dem standardmäßigen Konsolen Host, Visual Studio Code und Fenster Terminal.</span><span class="sxs-lookup"><span data-stu-id="4da2b-124">PSReadLine works with default console host, Visual Studio Code, and Window Terminal.</span></span> <span data-ttu-id="4da2b-125">Es funktioniert nicht in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="4da2b-125">It does not work in PowerShell ISE.</span></span>

<span data-ttu-id="4da2b-126">Psread Line 2.2.0 wird mit PowerShell 7,2 ausgeliefert und wird in allen unterstützten Versionen von PowerShell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-126">PSReadLine 2.2.0 ships with PowerShell 7.2 and is supported in all supported versions of PowerShell.</span></span> <span data-ttu-id="4da2b-127">Es ist für die Installation über das PowerShell-Katalog verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4da2b-127">It is available to install from the PowerShell Gallery.</span></span>
<span data-ttu-id="4da2b-128">Führen Sie den folgenden Befehl aus, um psread Line 2.2.0 in einer unterstützten Version von PowerShell zu installieren.</span><span class="sxs-lookup"><span data-stu-id="4da2b-128">To install PSReadLine 2.2.0 in a supported version of PowerShell run the following command.</span></span>

```powershell
Install-Module -Name PSReadLine -AllowPrerelease
```

> [!NOTE]
> <span data-ttu-id="4da2b-129">Ab PowerShell 7,0 überspringt PowerShell das automatische Laden von psleseline unter Windows, wenn ein Bildschirm Leseprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="4da2b-129">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="4da2b-130">Derzeit funktioniert psread Line nicht gut mit den Bildschirmlesern.</span><span class="sxs-lookup"><span data-stu-id="4da2b-130">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="4da2b-131">Das Standard Rendering und die Formatierung von PowerShell 7,0 unter Windows funktionieren ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="4da2b-131">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="4da2b-132">Sie können das Modul ggf. manuell laden.</span><span class="sxs-lookup"><span data-stu-id="4da2b-132">You can manually load the module if necessary.</span></span>

## <a name="predictive-intellisense"></a><span data-ttu-id="4da2b-133">Predictive IntelliSense</span><span class="sxs-lookup"><span data-stu-id="4da2b-133">Predictive IntelliSense</span></span>

<span data-ttu-id="4da2b-134">Predictive IntelliSense ist eine Ergänzung zum Konzept der Vervollständigung mit der Tab-Taste, die dem Benutzer hilft, Befehle erfolgreich abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-134">Predictive IntelliSense is an addition to the concept of tab completion that assists the user in successfully completing commands.</span></span> <span data-ttu-id="4da2b-135">Sie ermöglicht Benutzern das ermitteln, bearbeiten und ausführen vollständiger Befehle basierend auf übereinstimmenden Vorhersagen aus dem Verlauf des Benutzers und zusätzlichen domänenspezifischen Plug-ins.</span><span class="sxs-lookup"><span data-stu-id="4da2b-135">It enables users to discover, edit, and execute full commands based on matching predictions from the user's history and additional domain specific plugins.</span></span>

### <a name="enable-predictive-intellisense"></a><span data-ttu-id="4da2b-136">Aktivieren von Predictive IntelliSense</span><span class="sxs-lookup"><span data-stu-id="4da2b-136">Enable Predictive IntelliSense</span></span>

<span data-ttu-id="4da2b-137">Predictive IntelliSense ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-137">Predictive IntelliSense is disabled by default.</span></span> <span data-ttu-id="4da2b-138">Um Vorhersagen zu aktivieren, führen Sie einfach den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="4da2b-138">To enable predictions, just run the following command:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource History
```

<span data-ttu-id="4da2b-139">Der Parameter " **prätionsource** " kann auch Plug-Ins für domänenspezifische und benutzerdefinierte Anforderungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="4da2b-139">The **PredictionSource** parameter can also accept plugins for domain specific and custom requirements.</span></span>

<span data-ttu-id="4da2b-140">Um Predictive IntelliSense zu deaktivieren, führen Sie einfach Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4da2b-140">To disable Predictive IntelliSense, just run:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource None
```

<span data-ttu-id="4da2b-141">Die folgenden Funktionen sind in der-Klasse **[Microsoft. PowerShell. psconsolereadline]** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4da2b-141">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="4da2b-142">Grundlegende Bearbeitungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="4da2b-142">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="4da2b-143">Abbrechen</span><span class="sxs-lookup"><span data-stu-id="4da2b-143">Abort</span></span>

<span data-ttu-id="4da2b-144">Abbrechen der aktuellen Aktion, z.b. inkrementelle Verlaufs Suche.</span><span class="sxs-lookup"><span data-stu-id="4da2b-144">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="4da2b-145">Ansehen `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-145">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="4da2b-146">Akzeptandgetnext</span><span class="sxs-lookup"><span data-stu-id="4da2b-146">AcceptAndGetNext</span></span>

<span data-ttu-id="4da2b-147">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-147">Attempt to execute the current input.</span></span> <span data-ttu-id="4da2b-148">Wenn Sie ausgeführt werden kann (wie z. b. Accept Line), erinnern Sie sich beim nächsten Aufruf von "read line" an das nächste Element aus dem Verlauf.</span><span class="sxs-lookup"><span data-stu-id="4da2b-148">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="4da2b-149">Ansehen `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-149">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="4da2b-150">Annahme</span><span class="sxs-lookup"><span data-stu-id="4da2b-150">AcceptLine</span></span>

<span data-ttu-id="4da2b-151">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-151">Attempt to execute the current input.</span></span> <span data-ttu-id="4da2b-152">Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4da2b-152">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="4da2b-153">Befehl: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-153">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="4da2b-154">Ansehen `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-154">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="4da2b-155">VI-Einfügemodus: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-155">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="4da2b-156">AddLine</span><span class="sxs-lookup"><span data-stu-id="4da2b-156">AddLine</span></span>

<span data-ttu-id="4da2b-157">Die Fortsetzungs Aufforderung wird in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4da2b-157">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="4da2b-158">Dies ist nützlich, um mehrzeilige Eingaben als einen einzelnen Befehl einzugeben, auch wenn eine einzelne Zeile allein eine Eingabe ist.</span><span class="sxs-lookup"><span data-stu-id="4da2b-158">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="4da2b-159">Befehl: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-159">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="4da2b-160">Ansehen `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-160">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="4da2b-161">VI-Einfügemodus: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-161">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="4da2b-162">VI-Befehlsmodus: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-162">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="4da2b-163">Backwarddeletechar</span><span class="sxs-lookup"><span data-stu-id="4da2b-163">BackwardDeleteChar</span></span>

<span data-ttu-id="4da2b-164">Löschen Sie das Zeichen vor dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-164">Delete the character before the cursor.</span></span>

- <span data-ttu-id="4da2b-165">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-165">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="4da2b-166">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-166">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="4da2b-167">VI-Einfügemodus: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-167">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="4da2b-168">VI-Befehlsmodus: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-168">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="4da2b-169">Backwarddelta-Eline</span><span class="sxs-lookup"><span data-stu-id="4da2b-169">BackwardDeleteLine</span></span>

<span data-ttu-id="4da2b-170">Wie backwardkillline löscht Text vom Punkt bis zum Anfang der Zeile, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-170">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="4da2b-171">Befehl: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-171">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="4da2b-172">VI-Einfügemodus: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-172">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="4da2b-173">VI-Befehlsmodus: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-173">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="4da2b-174">Backwarddeleteword</span><span class="sxs-lookup"><span data-stu-id="4da2b-174">BackwardDeleteWord</span></span>

<span data-ttu-id="4da2b-175">Löscht das vorherige Wort.</span><span class="sxs-lookup"><span data-stu-id="4da2b-175">Deletes the previous word.</span></span>

- <span data-ttu-id="4da2b-176">VI-Befehlsmodus: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-176">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="4da2b-177">Backwardkillline</span><span class="sxs-lookup"><span data-stu-id="4da2b-177">BackwardKillLine</span></span>

<span data-ttu-id="4da2b-178">Löschen Sie die Eingabe vom Beginn der Eingabe in den Cursor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-178">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="4da2b-179">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-179">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="4da2b-180">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-180">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="4da2b-181">Backwardkillword</span><span class="sxs-lookup"><span data-stu-id="4da2b-181">BackwardKillWord</span></span>

<span data-ttu-id="4da2b-182">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-182">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="4da2b-183">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4da2b-183">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="4da2b-184">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-184">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="4da2b-185">Cmd: `<Ctrl+Backspace>` , `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-185">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="4da2b-186">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-186">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="4da2b-187">VI-Einfügemodus: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-187">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="4da2b-188">VI-Befehlsmodus: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-188">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="4da2b-189">Cancelline</span><span class="sxs-lookup"><span data-stu-id="4da2b-189">CancelLine</span></span>

<span data-ttu-id="4da2b-190">Brechen Sie die aktuelle Eingabe ab, belassen Sie die Eingabe auf dem Bildschirm, kehren Sie jedoch zurück zum Host, damit die Eingabeaufforderung erneut ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="4da2b-190">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="4da2b-191">VI-Einfügemodus: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-191">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="4da2b-192">VI-Befehlsmodus: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-192">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="4da2b-193">Kopieren</span><span class="sxs-lookup"><span data-stu-id="4da2b-193">Copy</span></span>

<span data-ttu-id="4da2b-194">Kopiert den ausgewählten Bereich in die Zwischenablage des Systems.</span><span class="sxs-lookup"><span data-stu-id="4da2b-194">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="4da2b-195">Wenn keine Region ausgewählt ist, kopieren Sie die gesamte Zeile.</span><span class="sxs-lookup"><span data-stu-id="4da2b-195">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="4da2b-196">Befehl: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-196">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="4da2b-197">Copyorcancelline</span><span class="sxs-lookup"><span data-stu-id="4da2b-197">CopyOrCancelLine</span></span>

<span data-ttu-id="4da2b-198">Wenn Text ausgewählt ist, kopieren Sie ihn in die Zwischenablage, andernfalls brechen Sie die Zeile ab.</span><span class="sxs-lookup"><span data-stu-id="4da2b-198">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="4da2b-199">Befehl: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-199">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="4da2b-200">Ansehen `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-200">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="4da2b-201">Ausschneiden</span><span class="sxs-lookup"><span data-stu-id="4da2b-201">Cut</span></span>

<span data-ttu-id="4da2b-202">Löscht die ausgewählte Region, in der Gelöschter Text in der Zwischenablage des Systems</span><span class="sxs-lookup"><span data-stu-id="4da2b-202">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="4da2b-203">Befehl: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-203">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="4da2b-204">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="4da2b-204">DeleteChar</span></span>

<span data-ttu-id="4da2b-205">Löschen Sie das Zeichen unter dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-205">Delete the character under the cursor.</span></span>

- <span data-ttu-id="4da2b-206">Befehl: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-206">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="4da2b-207">Ansehen `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-207">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="4da2b-208">VI-Einfügemodus: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-208">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="4da2b-209">VI-Befehlsmodus: `<Delete>` , `<x>` , `<d,l>` , `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-209">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="4da2b-210">Deletecharorexit</span><span class="sxs-lookup"><span data-stu-id="4da2b-210">DeleteCharOrExit</span></span>

<span data-ttu-id="4da2b-211">Löschen Sie das Zeichen unter dem Cursor, oder beenden Sie den Prozess, wenn die Zeile leer ist.</span><span class="sxs-lookup"><span data-stu-id="4da2b-211">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="4da2b-212">Ansehen `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-212">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="4da2b-213">Deleteendof Buffer</span><span class="sxs-lookup"><span data-stu-id="4da2b-213">DeleteEndOfBuffer</span></span>

<span data-ttu-id="4da2b-214">Löscht bis zum Ende des mehrzeiligen Puffers.</span><span class="sxs-lookup"><span data-stu-id="4da2b-214">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="4da2b-215">VI-Befehlsmodus: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-215">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="4da2b-216">Deleteendof</span><span class="sxs-lookup"><span data-stu-id="4da2b-216">DeleteEndOfWord</span></span>

<span data-ttu-id="4da2b-217">Bis zum Ende des Worts löschen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-217">Delete to the end of the word.</span></span>

- <span data-ttu-id="4da2b-218">VI-Befehlsmodus: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-218">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="4da2b-219">"Deleteline</span><span class="sxs-lookup"><span data-stu-id="4da2b-219">DeleteLine</span></span>

<span data-ttu-id="4da2b-220">Löscht die aktuelle logische Zeile eines mehrzeiligen Puffers und ermöglicht Rückgängigmachen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-220">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="4da2b-221">VI-Befehlsmodus: `<d,d>` , `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-221">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="4da2b-222">Deletepreviouslines</span><span class="sxs-lookup"><span data-stu-id="4da2b-222">DeletePreviousLines</span></span>

<span data-ttu-id="4da2b-223">Löscht die vorherigen angeforderten logischen Zeilen und die aktuelle logische Zeile in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="4da2b-223">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="4da2b-224">VI-Befehlsmodus: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-224">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="4da2b-225">Deleterelativelines</span><span class="sxs-lookup"><span data-stu-id="4da2b-225">DeleteRelativeLines</span></span>

<span data-ttu-id="4da2b-226">Löscht vom Anfang des Puffers in die aktuelle logische Zeile in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="4da2b-226">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="4da2b-227">Bei den meisten VI-Befehlen `<d,g,g>` kann dem Befehl ein numerisches Argument vorangestellt werden, das eine absolute Zeilennummer angibt, die in Verbindung mit der aktuellen Zeilennummer einen Bereich von Zeilen bilden, die gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-227">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="4da2b-228">Wenn kein Wert angegeben wird, wird das numerische Argument standardmäßig auf 1 festgelegt. Dies bezieht sich auf die erste logische Zeile in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="4da2b-228">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="4da2b-229">Die tatsächliche Anzahl von Zeilen, die aus der mehrzeiligen Zeile gelöscht werden sollen, wird als Differenz zwischen der aktuellen logischen Zeilennummer und dem angegebenen numerischen Argument berechnet, das daher negativ sein kann.</span><span class="sxs-lookup"><span data-stu-id="4da2b-229">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="4da2b-230">Daher der _relative_ Teil des Methoden namens.</span><span class="sxs-lookup"><span data-stu-id="4da2b-230">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="4da2b-231">VI-Befehlsmodus: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-231">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="4da2b-232">Deletenextlines</span><span class="sxs-lookup"><span data-stu-id="4da2b-232">DeleteNextLines</span></span>

<span data-ttu-id="4da2b-233">Löscht die aktuelle logische Linie und die nächsten angeforderten logischen Zeilen in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="4da2b-233">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="4da2b-234">VI-Befehlsmodus: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-234">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="4da2b-235">Delta-inetyp</span><span class="sxs-lookup"><span data-stu-id="4da2b-235">DeleteLineToFirstChar</span></span>

<span data-ttu-id="4da2b-236">Löscht das erste nicht leere Zeichen der aktuellen logischen Zeile in einem mehrzeiligen Puffer.</span><span class="sxs-lookup"><span data-stu-id="4da2b-236">Deletes from the first non-blank character of the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="4da2b-237">VI-Befehlsmodus: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-237">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="4da2b-238">Deletegeend</span><span class="sxs-lookup"><span data-stu-id="4da2b-238">DeleteToEnd</span></span>

<span data-ttu-id="4da2b-239">Bis zum Ende der Zeile löschen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-239">Delete to the end of the line.</span></span>

- <span data-ttu-id="4da2b-240">VI-Befehlsmodus: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-240">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="4da2b-241">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="4da2b-241">DeleteWord</span></span>

<span data-ttu-id="4da2b-242">Löschen Sie das nächste Wort.</span><span class="sxs-lookup"><span data-stu-id="4da2b-242">Delete the next word.</span></span>

- <span data-ttu-id="4da2b-243">VI-Befehlsmodus: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-243">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="4da2b-244">Forwarddelta-Eline</span><span class="sxs-lookup"><span data-stu-id="4da2b-244">ForwardDeleteLine</span></span>

<span data-ttu-id="4da2b-245">Wie forwardkillline löscht Text vom Punkt bis zum Ende der Zeile, aber der gelöschte Text wird nicht in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-245">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="4da2b-246">Befehl: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-246">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="4da2b-247">VI-Einfügemodus: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-247">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="4da2b-248">VI-Befehlsmodus: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-248">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="4da2b-249">Insertlineoberhalb</span><span class="sxs-lookup"><span data-stu-id="4da2b-249">InsertLineAbove</span></span>

<span data-ttu-id="4da2b-250">Oberhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="4da2b-250">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="4da2b-251">Der Cursor wechselt zum Anfang der neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="4da2b-251">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="4da2b-252">Befehl: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-252">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="4da2b-253">Insertlinebelow</span><span class="sxs-lookup"><span data-stu-id="4da2b-253">InsertLineBelow</span></span>

<span data-ttu-id="4da2b-254">Unterhalb der aktuellen Zeile wird eine neue leere Zeile erstellt, unabhängig davon, wo sich der Cursor in der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="4da2b-254">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="4da2b-255">Der Cursor wechselt zum Anfang der neuen Zeile.</span><span class="sxs-lookup"><span data-stu-id="4da2b-255">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="4da2b-256">Befehl: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-256">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="4da2b-257">Invertieren</span><span class="sxs-lookup"><span data-stu-id="4da2b-257">InvertCase</span></span>

<span data-ttu-id="4da2b-258">Kehrt die Groß-/Kleinschreibung des aktuellen Zeichens um und wechselt zum nächsten.</span><span class="sxs-lookup"><span data-stu-id="4da2b-258">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="4da2b-259">VI-Befehlsmodus: `<~>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-259">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="4da2b-260">Killline</span><span class="sxs-lookup"><span data-stu-id="4da2b-260">KillLine</span></span>

<span data-ttu-id="4da2b-261">Löschen Sie die Eingabe vom Cursor bis zum Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="4da2b-261">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="4da2b-262">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-262">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="4da2b-263">Ansehen `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-263">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="4da2b-264">Killregion</span><span class="sxs-lookup"><span data-stu-id="4da2b-264">KillRegion</span></span>

<span data-ttu-id="4da2b-265">Beenden Sie den Text zwischen dem Cursor und der Markierung.</span><span class="sxs-lookup"><span data-stu-id="4da2b-265">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="4da2b-266">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-266">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="4da2b-267">Killword</span><span class="sxs-lookup"><span data-stu-id="4da2b-267">KillWord</span></span>

<span data-ttu-id="4da2b-268">Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts.</span><span class="sxs-lookup"><span data-stu-id="4da2b-268">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="4da2b-269">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4da2b-269">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="4da2b-270">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-270">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="4da2b-271">Cmd: `<Alt+d>` , `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-271">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="4da2b-272">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-272">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="4da2b-273">VI-Einfügemodus: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-273">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="4da2b-274">VI-Befehlsmodus: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-274">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="4da2b-275">Einfügen</span><span class="sxs-lookup"><span data-stu-id="4da2b-275">Paste</span></span>

<span data-ttu-id="4da2b-276">Fügen Sie Text aus der Zwischenablage des Systems ein.</span><span class="sxs-lookup"><span data-stu-id="4da2b-276">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="4da2b-277">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-277">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="4da2b-278">VI-Einfügemodus: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-278">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="4da2b-279">VI-Befehlsmodus: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-279">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4da2b-280">Wenn Sie die Funktion **Einfügen** verwenden, wird der gesamte Inhalt des Zwischenablage Puffers in den Eingabepuffer von psread Line eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-280">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="4da2b-281">Der Eingabepuffer wird dann an den PowerShell-Parser übergeben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-281">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="4da2b-282">Eingaben, die mithilfe der **Rechtsklick-Einfügemethode** der Konsolenanwendung eingefügt werden, werden jeweils ein Zeichen in den Eingabepuffer kopiert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-282">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="4da2b-283">Der Eingabepuffer wird an den Parser übergeben, wenn ein Zeilen vorzeichensatz kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="4da2b-283">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="4da2b-284">Daher wird die Eingabe jeweils Zeilen gleich analysiert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-284">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="4da2b-285">Der Unterschied zwischen den Methoden zum Einfügen führt zu einem anderen Ausführungs Verhalten.</span><span class="sxs-lookup"><span data-stu-id="4da2b-285">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="4da2b-286">Pasteafter</span><span class="sxs-lookup"><span data-stu-id="4da2b-286">PasteAfter</span></span>

<span data-ttu-id="4da2b-287">Fügen Sie die Zwischenablage nach dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.</span><span class="sxs-lookup"><span data-stu-id="4da2b-287">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="4da2b-288">VI-Befehlsmodus: `<p>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-288">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="4da2b-289">Pastebefore</span><span class="sxs-lookup"><span data-stu-id="4da2b-289">PasteBefore</span></span>

<span data-ttu-id="4da2b-290">Fügen Sie die Zwischenablage vor dem Cursor ein, und bewegen Sie den Cursor an das Ende des eingefügten Texts.</span><span class="sxs-lookup"><span data-stu-id="4da2b-290">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="4da2b-291">VI-Befehlsmodus: `<P>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-291">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="4da2b-292">Prepdandaccept</span><span class="sxs-lookup"><span data-stu-id="4da2b-292">PrependAndAccept</span></span>

<span data-ttu-id="4da2b-293">Fügen Sie ein "#" vorangesteht, und akzeptieren Sie die Zeile.</span><span class="sxs-lookup"><span data-stu-id="4da2b-293">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="4da2b-294">VI-Befehlsmodus: `<#>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-294">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="4da2b-295">Wiederholen</span><span class="sxs-lookup"><span data-stu-id="4da2b-295">Redo</span></span>

<span data-ttu-id="4da2b-296">Rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-296">Undo an undo.</span></span>

- <span data-ttu-id="4da2b-297">Befehl: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-297">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="4da2b-298">VI-Einfügemodus: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-298">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="4da2b-299">VI-Befehlsmodus: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-299">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="4da2b-300">Repeatlastcommand</span><span class="sxs-lookup"><span data-stu-id="4da2b-300">RepeatLastCommand</span></span>

<span data-ttu-id="4da2b-301">Wiederholen Sie die letzte Textänderung.</span><span class="sxs-lookup"><span data-stu-id="4da2b-301">Repeat the last text modification.</span></span>

- <span data-ttu-id="4da2b-302">VI-Befehlsmodus: `<.>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-302">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="4da2b-303">Revertline</span><span class="sxs-lookup"><span data-stu-id="4da2b-303">RevertLine</span></span>

<span data-ttu-id="4da2b-304">Kehrt alle Eingaben in die aktuelle Eingabe um.</span><span class="sxs-lookup"><span data-stu-id="4da2b-304">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="4da2b-305">Befehl: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-305">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="4da2b-306">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-306">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="4da2b-307">Shellbackwardkillword</span><span class="sxs-lookup"><span data-stu-id="4da2b-307">ShellBackwardKillWord</span></span>

<span data-ttu-id="4da2b-308">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-308">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="4da2b-309">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4da2b-309">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="4da2b-310">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-310">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="4da2b-311">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-311">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="4da2b-312">Shellkillword</span><span class="sxs-lookup"><span data-stu-id="4da2b-312">ShellKillWord</span></span>

<span data-ttu-id="4da2b-313">Löschen Sie die Eingabe vom Cursor bis zum Ende des aktuellen Worts.</span><span class="sxs-lookup"><span data-stu-id="4da2b-313">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="4da2b-314">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Cursor bis zum Ende des nächsten Worts gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4da2b-314">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="4da2b-315">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-315">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="4da2b-316">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-316">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="4da2b-317">Austausch Zeichen</span><span class="sxs-lookup"><span data-stu-id="4da2b-317">SwapCharacters</span></span>

<span data-ttu-id="4da2b-318">Tauschen Sie das aktuelle und das aktuelle Zeichen aus.</span><span class="sxs-lookup"><span data-stu-id="4da2b-318">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="4da2b-319">Ansehen `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-319">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="4da2b-320">VI-Einfügemodus: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-320">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="4da2b-321">VI-Befehlsmodus: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-321">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="4da2b-322">Rückgängig</span><span class="sxs-lookup"><span data-stu-id="4da2b-322">Undo</span></span>

<span data-ttu-id="4da2b-323">Rückgängigmachen einer vorherigen Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="4da2b-323">Undo a previous edit.</span></span>

- <span data-ttu-id="4da2b-324">Befehl: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-324">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="4da2b-325">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-325">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="4da2b-326">VI-Einfügemodus: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-326">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="4da2b-327">VI-Befehlsmodus: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-327">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="4da2b-328">Nicht doall</span><span class="sxs-lookup"><span data-stu-id="4da2b-328">UndoAll</span></span>

<span data-ttu-id="4da2b-329">Alle vorherigen Änderungen für die Zeile rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-329">Undo all previous edits for line.</span></span>

- <span data-ttu-id="4da2b-330">VI-Befehlsmodus: `<U>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-330">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="4da2b-331">Unixwordrubout</span><span class="sxs-lookup"><span data-stu-id="4da2b-331">UnixWordRubout</span></span>

<span data-ttu-id="4da2b-332">Löschen Sie die Eingabe vom Anfang des aktuellen Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-332">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="4da2b-333">Wenn der Cursor zwischen Wörtern liegt, wird die Eingabe vom Anfang des vorherigen Worts bis zum Cursor gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4da2b-333">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="4da2b-334">Der gelöschte Text wird in den Kill-Ring eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-334">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="4da2b-335">Ansehen `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-335">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="4da2b-336">Validateandakzeptline</span><span class="sxs-lookup"><span data-stu-id="4da2b-336">ValidateAndAcceptLine</span></span>

<span data-ttu-id="4da2b-337">Versuchen Sie, die aktuelle Eingabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-337">Attempt to execute the current input.</span></span> <span data-ttu-id="4da2b-338">Wenn die aktuelle Eingabe unvollständig ist (z. b. Wenn eine schließende Klammer, eckige Klammer oder ein Anführungszeichen fehlt), wird die Fortsetzungs Aufforderung in der nächsten Zeile angezeigt, und psread Line wartet auf Schlüssel, um die aktuelle Eingabe zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4da2b-338">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="4da2b-339">Ansehen `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-339">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="4da2b-340">Viakzeptline</span><span class="sxs-lookup"><span data-stu-id="4da2b-340">ViAcceptLine</span></span>

<span data-ttu-id="4da2b-341">Akzeptieren Sie die Zeile, und wechseln Sie zum Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="4da2b-341">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="4da2b-342">VI-Befehlsmodus: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-342">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="4da2b-343">Viakzeptlineorexit</span><span class="sxs-lookup"><span data-stu-id="4da2b-343">ViAcceptLineOrExit</span></span>

<span data-ttu-id="4da2b-344">Wie deletecharorexit im Emacs-Modus, akzeptiert jedoch die Zeile, anstatt ein Zeichen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-344">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="4da2b-345">VI-Einfügemodus: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-345">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="4da2b-346">VI-Befehlsmodus: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-346">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="4da2b-347">Viappendline</span><span class="sxs-lookup"><span data-stu-id="4da2b-347">ViAppendLine</span></span>

<span data-ttu-id="4da2b-348">Unterhalb der aktuellen Zeile wird eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-348">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="4da2b-349">VI-Befehlsmodus: `<o>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-349">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="4da2b-350">Vibackwarddeleteglob</span><span class="sxs-lookup"><span data-stu-id="4da2b-350">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="4da2b-351">Löscht das vorherige Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4da2b-351">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="4da2b-352">VI-Befehlsmodus: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-352">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="4da2b-353">Vibackwardglob</span><span class="sxs-lookup"><span data-stu-id="4da2b-353">ViBackwardGlob</span></span>

<span data-ttu-id="4da2b-354">Verschiebt den Cursor zurück an den Anfang des vorherigen Worts, wobei nur Leerraum als Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4da2b-354">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="4da2b-355">VI-Befehlsmodus: `<B>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-355">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="4da2b-356">Videletebrace</span><span class="sxs-lookup"><span data-stu-id="4da2b-356">ViDeleteBrace</span></span>

<span data-ttu-id="4da2b-357">Suchen Sie nach der passenden geschweiften Klammer, Klammer oder eckigen Klammer, und löschen Sie alle Inhalte in, einschließlich der geschweiften Klammer.</span><span class="sxs-lookup"><span data-stu-id="4da2b-357">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="4da2b-358">VI-Befehlsmodus: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-358">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="4da2b-359">Videleteendobglob</span><span class="sxs-lookup"><span data-stu-id="4da2b-359">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="4da2b-360">Bis zum Ende des Worts löschen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-360">Delete to the end of the word.</span></span>

- <span data-ttu-id="4da2b-361">VI-Befehlsmodus: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-361">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="4da2b-362">Videleteglob</span><span class="sxs-lookup"><span data-stu-id="4da2b-362">ViDeleteGlob</span></span>

<span data-ttu-id="4da2b-363">Löschen Sie den nächsten globmuster (Leerzeichen mit Trennzeichen).</span><span class="sxs-lookup"><span data-stu-id="4da2b-363">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="4da2b-364">VI-Befehlsmodus: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-364">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="4da2b-365">Videletetobeforechar</span><span class="sxs-lookup"><span data-stu-id="4da2b-365">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="4da2b-366">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-366">Deletes until given character.</span></span>

- <span data-ttu-id="4da2b-367">VI-Befehlsmodus: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-367">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="4da2b-368">Videletebackbeforecharrückwärts</span><span class="sxs-lookup"><span data-stu-id="4da2b-368">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="4da2b-369">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-369">Deletes until given character.</span></span>

- <span data-ttu-id="4da2b-370">VI-Befehlsmodus: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-370">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="4da2b-371">Videleteto Char</span><span class="sxs-lookup"><span data-stu-id="4da2b-371">ViDeleteToChar</span></span>

<span data-ttu-id="4da2b-372">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-372">Deletes until given character.</span></span>

- <span data-ttu-id="4da2b-373">VI-Befehlsmodus: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-373">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="4da2b-374">Videletebackcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="4da2b-374">ViDeleteToCharBackward</span></span>

<span data-ttu-id="4da2b-375">Löscht rückwärts bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-375">Deletes backwards until given character.</span></span>

- <span data-ttu-id="4da2b-376">VI-Befehlsmodus: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-376">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="4da2b-377">Viinsertatbeginung</span><span class="sxs-lookup"><span data-stu-id="4da2b-377">ViInsertAtBegining</span></span>

<span data-ttu-id="4da2b-378">Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Anfang der Zeile.</span><span class="sxs-lookup"><span data-stu-id="4da2b-378">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="4da2b-379">VI-Befehlsmodus: `<I>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-379">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="4da2b-380">Viinsertatend</span><span class="sxs-lookup"><span data-stu-id="4da2b-380">ViInsertAtEnd</span></span>

<span data-ttu-id="4da2b-381">Wechseln Sie in den Einfügemodus, und positionieren Sie den Cursor am Ende der Zeile.</span><span class="sxs-lookup"><span data-stu-id="4da2b-381">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="4da2b-382">VI-Befehlsmodus: `<A>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-382">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="4da2b-383">Viinsertline</span><span class="sxs-lookup"><span data-stu-id="4da2b-383">ViInsertLine</span></span>

<span data-ttu-id="4da2b-384">Oberhalb der aktuellen Zeile wird eine neue Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-384">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="4da2b-385">VI-Befehlsmodus: `<O>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-385">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="4da2b-386">Viinsertwithappend</span><span class="sxs-lookup"><span data-stu-id="4da2b-386">ViInsertWithAppend</span></span>

<span data-ttu-id="4da2b-387">An der aktuellen Zeilen Position anfügen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-387">Append from the current line position.</span></span>

- <span data-ttu-id="4da2b-388">VI-Befehlsmodus: `<a>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-388">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="4da2b-389">Viinsertwithdelete</span><span class="sxs-lookup"><span data-stu-id="4da2b-389">ViInsertWithDelete</span></span>

<span data-ttu-id="4da2b-390">Löschen Sie das aktuelle Zeichen und wechseln Sie in den Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="4da2b-390">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="4da2b-391">VI-Befehlsmodus: `<s>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-391">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="4da2b-392">Vijoinlines</span><span class="sxs-lookup"><span data-stu-id="4da2b-392">ViJoinLines</span></span>

<span data-ttu-id="4da2b-393">Verbindet die aktuelle Zeile und die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="4da2b-393">Joins the current line and the next line.</span></span>

- <span data-ttu-id="4da2b-394">VI-Befehlsmodus: `<J>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-394">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="4da2b-395">Vireplaceline</span><span class="sxs-lookup"><span data-stu-id="4da2b-395">ViReplaceLine</span></span>

<span data-ttu-id="4da2b-396">Löschen Sie die gesamte Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="4da2b-396">Erase the entire command line.</span></span>

- <span data-ttu-id="4da2b-397">VI-Befehlsmodus: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-397">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="4da2b-398">Vireplacetobeforechar</span><span class="sxs-lookup"><span data-stu-id="4da2b-398">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="4da2b-399">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-399">Replaces until given character.</span></span>

- <span data-ttu-id="4da2b-400">VI-Befehlsmodus: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-400">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="4da2b-401">Vireplaceumbeforecharrückwärts</span><span class="sxs-lookup"><span data-stu-id="4da2b-401">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="4da2b-402">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-402">Replaces until given character.</span></span>

- <span data-ttu-id="4da2b-403">VI-Befehlsmodus: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-403">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="4da2b-404">Vireplaceumchar</span><span class="sxs-lookup"><span data-stu-id="4da2b-404">ViReplaceToChar</span></span>

<span data-ttu-id="4da2b-405">Löscht bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-405">Deletes until given character.</span></span>

- <span data-ttu-id="4da2b-406">VI-Befehlsmodus: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-406">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="4da2b-407">Vireplacebackcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="4da2b-407">ViReplaceToCharBackward</span></span>

<span data-ttu-id="4da2b-408">Ersetzt bis zum angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-408">Replaces until given character.</span></span>

- <span data-ttu-id="4da2b-409">VI-Befehlsmodus: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-409">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="4da2b-410">Viyankbeginningosline</span><span class="sxs-lookup"><span data-stu-id="4da2b-410">ViYankBeginningOfLine</span></span>

<span data-ttu-id="4da2b-411">Yank vom Anfang des Puffers bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-411">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="4da2b-412">VI-Befehlsmodus: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-412">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="4da2b-413">Viyankendobglob</span><span class="sxs-lookup"><span data-stu-id="4da2b-413">ViYankEndOfGlob</span></span>

<span data-ttu-id="4da2b-414">Yank vom Cursor bis zum Ende des Worts (s).</span><span class="sxs-lookup"><span data-stu-id="4da2b-414">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="4da2b-415">VI-Befehlsmodus: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-415">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="4da2b-416">Viyankendof</span><span class="sxs-lookup"><span data-stu-id="4da2b-416">ViYankEndOfWord</span></span>

<span data-ttu-id="4da2b-417">Yank vom Cursor bis zum Ende des Worts (s).</span><span class="sxs-lookup"><span data-stu-id="4da2b-417">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="4da2b-418">VI-Befehlsmodus: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-418">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="4da2b-419">Viyankleft</span><span class="sxs-lookup"><span data-stu-id="4da2b-419">ViYankLeft</span></span>

<span data-ttu-id="4da2b-420">Die Zeichen werden Links vom Cursor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-420">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="4da2b-421">VI-Befehlsmodus: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-421">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="4da2b-422">Viyankline</span><span class="sxs-lookup"><span data-stu-id="4da2b-422">ViYankLine</span></span>

<span data-ttu-id="4da2b-423">Den gesamten Puffer.</span><span class="sxs-lookup"><span data-stu-id="4da2b-423">Yank the entire buffer.</span></span>

- <span data-ttu-id="4da2b-424">VI-Befehlsmodus: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-424">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="4da2b-425">Viyanknextglob</span><span class="sxs-lookup"><span data-stu-id="4da2b-425">ViYankNextGlob</span></span>

<span data-ttu-id="4da2b-426">Yank vom Cursor bis zum Anfang des nächsten Worts (n).</span><span class="sxs-lookup"><span data-stu-id="4da2b-426">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="4da2b-427">VI-Befehlsmodus: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-427">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="4da2b-428">Viyanknextword</span><span class="sxs-lookup"><span data-stu-id="4da2b-428">ViYankNextWord</span></span>

<span data-ttu-id="4da2b-429">Das Wort (e) nach dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-429">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="4da2b-430">VI-Befehlsmodus: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-430">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="4da2b-431">Viyankprozent</span><span class="sxs-lookup"><span data-stu-id="4da2b-431">ViYankPercent</span></span>

<span data-ttu-id="4da2b-432">Von der entsprechenden geschweiften geschweifter Klammer.</span><span class="sxs-lookup"><span data-stu-id="4da2b-432">Yank to/from matching brace.</span></span>

- <span data-ttu-id="4da2b-433">VI-Befehlsmodus: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-433">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="4da2b-434">Viyankpreviousglob</span><span class="sxs-lookup"><span data-stu-id="4da2b-434">ViYankPreviousGlob</span></span>

<span data-ttu-id="4da2b-435">Yank von Anfang des Worts bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-435">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="4da2b-436">VI-Befehlsmodus: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-436">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="4da2b-437">Viyankpreviousword</span><span class="sxs-lookup"><span data-stu-id="4da2b-437">ViYankPreviousWord</span></span>

<span data-ttu-id="4da2b-438">Das Wort (e) vor dem Cursor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-438">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="4da2b-439">VI-Befehlsmodus: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-439">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="4da2b-440">Viyankright</span><span class="sxs-lookup"><span data-stu-id="4da2b-440">ViYankRight</span></span>

<span data-ttu-id="4da2b-441">(E) unter und rechts vom Cursor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-441">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="4da2b-442">VI-Befehlsmodus: `<y,l>` , `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-442">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="4da2b-443">Viyanktoendosline</span><span class="sxs-lookup"><span data-stu-id="4da2b-443">ViYankToEndOfLine</span></span>

<span data-ttu-id="4da2b-444">Yank vom Cursor bis zum Ende des Puffers.</span><span class="sxs-lookup"><span data-stu-id="4da2b-444">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="4da2b-445">VI-Befehlsmodus: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-445">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="4da2b-446">Viyanktofirstchar</span><span class="sxs-lookup"><span data-stu-id="4da2b-446">ViYankToFirstChar</span></span>

<span data-ttu-id="4da2b-447">Yank vom ersten Zeichen, das kein Leerzeichen ist, bis zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-447">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="4da2b-448">VI-Befehlsmodus: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-448">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="4da2b-449">Yank</span><span class="sxs-lookup"><span data-stu-id="4da2b-449">Yank</span></span>

<span data-ttu-id="4da2b-450">Fügen Sie der Eingabe den zuletzt beendeten Text hinzu.</span><span class="sxs-lookup"><span data-stu-id="4da2b-450">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="4da2b-451">Ansehen `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-451">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="4da2b-452">Yanklastarg</span><span class="sxs-lookup"><span data-stu-id="4da2b-452">YankLastArg</span></span>

<span data-ttu-id="4da2b-453">Das letzte Argument aus der vorherigen Verlaufs Zeile.</span><span class="sxs-lookup"><span data-stu-id="4da2b-453">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="4da2b-454">Mit einem Argument verhält sich das erste Mal, wenn es aufgerufen wird, wie yankntharg.</span><span class="sxs-lookup"><span data-stu-id="4da2b-454">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="4da2b-455">Wenn Sie mehrmals aufgerufen wird, durchläuft Sie stattdessen den Verlauf, und arg legt die Richtung fest (negative Umkehrung der Richtung).</span><span class="sxs-lookup"><span data-stu-id="4da2b-455">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="4da2b-456">Befehl: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-456">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="4da2b-457">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-457">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="4da2b-458">Yankntharg</span><span class="sxs-lookup"><span data-stu-id="4da2b-458">YankNthArg</span></span>

<span data-ttu-id="4da2b-459">Yank das erste Argument (nach dem Befehl) aus der vorherigen Verlaufs Zeile.</span><span class="sxs-lookup"><span data-stu-id="4da2b-459">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="4da2b-460">Bei einem Argument wird das n-te Argument (beginnend bei 0), wenn das Argument negativ ist, mit dem letzten Argument beginnen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-460">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="4da2b-461">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-461">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="4da2b-462">Yankpop</span><span class="sxs-lookup"><span data-stu-id="4da2b-462">YankPop</span></span>

<span data-ttu-id="4da2b-463">Wenn der vorherige Vorgang "Yank" oder "yankpop" war, ersetzen Sie den zuvor angezeigten Text durch den nächsten ausgeblendeten Text aus dem Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="4da2b-463">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="4da2b-464">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-464">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="4da2b-465">Cursor Verschiebungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="4da2b-465">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="4da2b-466">Backwardchar</span><span class="sxs-lookup"><span data-stu-id="4da2b-466">BackwardChar</span></span>

<span data-ttu-id="4da2b-467">Bewegen Sie den Cursor um ein Zeichen nach links.</span><span class="sxs-lookup"><span data-stu-id="4da2b-467">Move the cursor one character to the left.</span></span> <span data-ttu-id="4da2b-468">Dadurch kann der Cursor in die vorherige Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="4da2b-468">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="4da2b-469">Befehl: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-469">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="4da2b-470">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-470">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="4da2b-471">Backwardword</span><span class="sxs-lookup"><span data-stu-id="4da2b-471">BackwardWord</span></span>

<span data-ttu-id="4da2b-472">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-472">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="4da2b-473">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-473">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="4da2b-474">Befehl: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-474">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="4da2b-475">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-475">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="4da2b-476">VI-Einfügemodus: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-476">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="4da2b-477">VI-Befehlsmodus: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-477">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="4da2b-478">Beginningosline</span><span class="sxs-lookup"><span data-stu-id="4da2b-478">BeginningOfLine</span></span>

<span data-ttu-id="4da2b-479">Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Anfang der aktuellen Zeile oder, wenn Sie sich bereits am Anfang der Zeile befinden, bis zum Anfang der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="4da2b-479">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="4da2b-480">Wenn die Eingabe über eine einzelne Zeile verfügt, wechseln Sie zum Anfang der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="4da2b-480">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="4da2b-481">Befehl: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-481">Cmd: `<Home>`</span></span>
- <span data-ttu-id="4da2b-482">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-482">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="4da2b-483">VI-Einfügemodus: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-483">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="4da2b-484">VI-Befehlsmodus: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-484">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="4da2b-485">Endosline</span><span class="sxs-lookup"><span data-stu-id="4da2b-485">EndOfLine</span></span>

<span data-ttu-id="4da2b-486">Wenn die Eingabe mehrere Zeilen enthält, wechseln Sie zum Ende der aktuellen Zeile, oder wechseln Sie, wenn Sie sich bereits am Ende der Zeile befindet, bis zum Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="4da2b-486">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="4da2b-487">Wenn die Eingabe über eine einzelne Zeile verfügt, verschieben Sie das Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="4da2b-487">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="4da2b-488">Befehl: `<End>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-488">Cmd: `<End>`</span></span>
- <span data-ttu-id="4da2b-489">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-489">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="4da2b-490">VI-Einfügemodus: `<End>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-490">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="4da2b-491">Forwardchar</span><span class="sxs-lookup"><span data-stu-id="4da2b-491">ForwardChar</span></span>

<span data-ttu-id="4da2b-492">Bewegen Sie den Cursor um ein Zeichen nach rechts.</span><span class="sxs-lookup"><span data-stu-id="4da2b-492">Move the cursor one character to the right.</span></span> <span data-ttu-id="4da2b-493">Dadurch kann der Cursor in die nächste Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="4da2b-493">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="4da2b-494">Befehl: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-494">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="4da2b-495">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-495">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="4da2b-496">Forwardword</span><span class="sxs-lookup"><span data-stu-id="4da2b-496">ForwardWord</span></span>

<span data-ttu-id="4da2b-497">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="4da2b-497">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="4da2b-498">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-498">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="4da2b-499">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-499">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="4da2b-500">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="4da2b-500">GotoBrace</span></span>

<span data-ttu-id="4da2b-501">Wechseln Sie zur passenden geschweiften Klammer, Klammer oder eckigen Klammer.</span><span class="sxs-lookup"><span data-stu-id="4da2b-501">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="4da2b-502">Befehl: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-502">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="4da2b-503">VI-Einfügemodus: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-503">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="4da2b-504">VI-Befehlsmodus: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-504">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="4da2b-505">Goum Column</span><span class="sxs-lookup"><span data-stu-id="4da2b-505">GotoColumn</span></span>

<span data-ttu-id="4da2b-506">Wechseln Sie in die Spalte, die von arg angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4da2b-506">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="4da2b-507">VI-Befehlsmodus: `<|>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-507">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="4da2b-508">Gostarfirstnonblankosline</span><span class="sxs-lookup"><span data-stu-id="4da2b-508">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="4da2b-509">Bewegen Sie den Cursor auf das erste nicht leere Zeichen in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="4da2b-509">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="4da2b-510">VI-Befehlsmodus: `<^>` , `<_>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-510">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="4da2b-511">"MUVE"</span><span class="sxs-lookup"><span data-stu-id="4da2b-511">MoveToEndOfLine</span></span>

<span data-ttu-id="4da2b-512">Bewegen Sie den Cursor an das Ende der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="4da2b-512">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="4da2b-513">VI-Befehlsmodus: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-513">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="4da2b-514">Nextline</span><span class="sxs-lookup"><span data-stu-id="4da2b-514">NextLine</span></span>

<span data-ttu-id="4da2b-515">Bewegen Sie den Cursor in die nächste Zeile.</span><span class="sxs-lookup"><span data-stu-id="4da2b-515">Move the cursor to the next line.</span></span>

- <span data-ttu-id="4da2b-516">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-516">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="4da2b-517">Nextword</span><span class="sxs-lookup"><span data-stu-id="4da2b-517">NextWord</span></span>

<span data-ttu-id="4da2b-518">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="4da2b-518">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="4da2b-519">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-519">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="4da2b-520">Befehl: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-520">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="4da2b-521">VI-Einfügemodus: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-521">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="4da2b-522">VI-Befehlsmodus: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-522">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="4da2b-523">Nextwordend</span><span class="sxs-lookup"><span data-stu-id="4da2b-523">NextWordEnd</span></span>

<span data-ttu-id="4da2b-524">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="4da2b-524">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="4da2b-525">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-525">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="4da2b-526">VI-Befehlsmodus: `<e>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-526">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="4da2b-527">Previousline</span><span class="sxs-lookup"><span data-stu-id="4da2b-527">PreviousLine</span></span>

<span data-ttu-id="4da2b-528">Bewegen Sie den Cursor in die vorherige Zeile.</span><span class="sxs-lookup"><span data-stu-id="4da2b-528">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="4da2b-529">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-529">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="4da2b-530">Shellbackwardword</span><span class="sxs-lookup"><span data-stu-id="4da2b-530">ShellBackwardWord</span></span>

<span data-ttu-id="4da2b-531">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-531">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="4da2b-532">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-532">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="4da2b-533">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-533">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="4da2b-534">Shellforwardword</span><span class="sxs-lookup"><span data-stu-id="4da2b-534">ShellForwardWord</span></span>

<span data-ttu-id="4da2b-535">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="4da2b-535">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="4da2b-536">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-536">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="4da2b-537">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-537">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="4da2b-538">Shellnextword</span><span class="sxs-lookup"><span data-stu-id="4da2b-538">ShellNextWord</span></span>

<span data-ttu-id="4da2b-539">Bewegen Sie den Cursor an das Ende des aktuellen Worts oder, wenn zwischen den Wörtern, bis zum Ende des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="4da2b-539">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="4da2b-540">Wortgrenzen werden durch PowerShell-Token definiert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-540">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="4da2b-541">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-541">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="4da2b-542">Vibackwardchar</span><span class="sxs-lookup"><span data-stu-id="4da2b-542">ViBackwardChar</span></span>

<span data-ttu-id="4da2b-543">Bewegen Sie den Cursor um ein Zeichen nach links im VI-Bearbeitungsmodus.</span><span class="sxs-lookup"><span data-stu-id="4da2b-543">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="4da2b-544">Dadurch kann der Cursor in die vorherige Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="4da2b-544">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="4da2b-545">VI-Einfügemodus: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-545">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="4da2b-546">VI-Befehlsmodus: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-546">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="4da2b-547">Vibackwardword</span><span class="sxs-lookup"><span data-stu-id="4da2b-547">ViBackwardWord</span></span>

<span data-ttu-id="4da2b-548">Bewegen Sie den Cursor zurück zum Anfang des aktuellen Worts oder, wenn der Anfang des vorherigen Worts zwischen Wörtern liegt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-548">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="4da2b-549">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-549">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="4da2b-550">VI-Befehlsmodus: `<b>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-550">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="4da2b-551">Viforwardchar</span><span class="sxs-lookup"><span data-stu-id="4da2b-551">ViForwardChar</span></span>

<span data-ttu-id="4da2b-552">Bewegen Sie den Cursor um ein Zeichen nach rechts im VI-Bearbeitungsmodus.</span><span class="sxs-lookup"><span data-stu-id="4da2b-552">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="4da2b-553">Dadurch kann der Cursor in die nächste Zeile der mehrzeiligen Eingabe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="4da2b-553">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="4da2b-554">VI-Einfügemodus: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-554">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="4da2b-555">VI-Befehlsmodus: `<RightArrow>` , `<Spacebar>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-555">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="4da2b-556">Viendobglob</span><span class="sxs-lookup"><span data-stu-id="4da2b-556">ViEndOfGlob</span></span>

<span data-ttu-id="4da2b-557">Verschiebt den Cursor an das Ende des Worts und verwendet nur Leerzeichen als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-557">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="4da2b-558">VI-Befehlsmodus: `<E>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-558">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="4da2b-559">Viendof previousglob</span><span class="sxs-lookup"><span data-stu-id="4da2b-559">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="4da2b-560">Wechselt zum Ende des vorherigen Worts, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4da2b-560">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="4da2b-561">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-561">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="4da2b-562">Vigoumbrace</span><span class="sxs-lookup"><span data-stu-id="4da2b-562">ViGotoBrace</span></span>

<span data-ttu-id="4da2b-563">Ähnelt gotobrace, aber ist Zeichen basiert anstelle von tokenbasiert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-563">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="4da2b-564">VI-Befehlsmodus: `<%>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-564">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="4da2b-565">Vinextglob</span><span class="sxs-lookup"><span data-stu-id="4da2b-565">ViNextGlob</span></span>

<span data-ttu-id="4da2b-566">Wechselt zum nächsten Wort, wobei nur Leerraum als Wort Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4da2b-566">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="4da2b-567">VI-Befehlsmodus: `<W>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-567">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="4da2b-568">Vinextword</span><span class="sxs-lookup"><span data-stu-id="4da2b-568">ViNextWord</span></span>

<span data-ttu-id="4da2b-569">Bewegen Sie den Cursor an den Anfang des nächsten Worts.</span><span class="sxs-lookup"><span data-stu-id="4da2b-569">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="4da2b-570">Wortgrenzen werden durch einen konfigurierbaren Satz von Zeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-570">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="4da2b-571">VI-Befehlsmodus: `<w>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-571">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="4da2b-572">Verlaufs Funktionen</span><span class="sxs-lookup"><span data-stu-id="4da2b-572">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="4da2b-573">Beginningof History</span><span class="sxs-lookup"><span data-stu-id="4da2b-573">BeginningOfHistory</span></span>

<span data-ttu-id="4da2b-574">Wechselt zum ersten Element im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="4da2b-574">Move to the first item in the history.</span></span>

- <span data-ttu-id="4da2b-575">Ansehen `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-575">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="4da2b-576">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="4da2b-576">ClearHistory</span></span>

<span data-ttu-id="4da2b-577">Löscht den Verlauf in psleline.</span><span class="sxs-lookup"><span data-stu-id="4da2b-577">Clears history in PSReadLine.</span></span> <span data-ttu-id="4da2b-578">Dies wirkt sich nicht auf den PowerShell-Verlauf aus.</span><span class="sxs-lookup"><span data-stu-id="4da2b-578">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="4da2b-579">Befehl: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-579">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="4da2b-580">EndOf History</span><span class="sxs-lookup"><span data-stu-id="4da2b-580">EndOfHistory</span></span>

<span data-ttu-id="4da2b-581">Wechselt zum letzten Element (der aktuellen Eingabe) im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="4da2b-581">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="4da2b-582">Ansehen `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-582">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="4da2b-583">Forwardsearchhistory</span><span class="sxs-lookup"><span data-stu-id="4da2b-583">ForwardSearchHistory</span></span>

<span data-ttu-id="4da2b-584">Führt eine inkrementelle Forward-Suche im Verlauf durch</span><span class="sxs-lookup"><span data-stu-id="4da2b-584">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="4da2b-585">Befehl: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-585">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="4da2b-586">Ansehen `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-586">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="4da2b-587">Historysearchrückwärts</span><span class="sxs-lookup"><span data-stu-id="4da2b-587">HistorySearchBackward</span></span>

<span data-ttu-id="4da2b-588">Ersetzen Sie die aktuelle Eingabe durch das Element "Previous" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.</span><span class="sxs-lookup"><span data-stu-id="4da2b-588">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="4da2b-589">Befehl: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-589">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="4da2b-590">Historysearchforward</span><span class="sxs-lookup"><span data-stu-id="4da2b-590">HistorySearchForward</span></span>

<span data-ttu-id="4da2b-591">Ersetzen Sie die aktuelle Eingabe durch das Element "Next" aus dem pslelinienverlauf, der den Zeichen zwischen dem Start und der Eingabe und dem Cursor entspricht.</span><span class="sxs-lookup"><span data-stu-id="4da2b-591">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="4da2b-592">Befehl: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-592">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="4da2b-593">Nexthistory</span><span class="sxs-lookup"><span data-stu-id="4da2b-593">NextHistory</span></span>

<span data-ttu-id="4da2b-594">Ersetzen Sie die aktuelle Eingabe durch das "Next"-Element aus dem psleline-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="4da2b-594">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="4da2b-595">Befehl: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-595">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="4da2b-596">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-596">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="4da2b-597">VI-Einfügemodus: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-597">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="4da2b-598">VI-Befehlsmodus: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-598">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="4da2b-599">Previoushistory</span><span class="sxs-lookup"><span data-stu-id="4da2b-599">PreviousHistory</span></span>

<span data-ttu-id="4da2b-600">Ersetzen Sie die aktuelle Eingabe durch das "Previous"-Element aus dem psleline-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="4da2b-600">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="4da2b-601">Befehl: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-601">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="4da2b-602">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-602">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="4da2b-603">VI-Einfügemodus: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-603">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="4da2b-604">VI-Befehlsmodus: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="4da2b-604">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="4da2b-605">Reversesearchhistory</span><span class="sxs-lookup"><span data-stu-id="4da2b-605">ReverseSearchHistory</span></span>

<span data-ttu-id="4da2b-606">Führt eine inkrementelle Rückwärtssuche über den Verlauf durch</span><span class="sxs-lookup"><span data-stu-id="4da2b-606">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="4da2b-607">Befehl: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-607">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="4da2b-608">Ansehen `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-608">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="4da2b-609">Visearchhistoryrückwärts</span><span class="sxs-lookup"><span data-stu-id="4da2b-609">ViSearchHistoryBackward</span></span>

<span data-ttu-id="4da2b-610">Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.</span><span class="sxs-lookup"><span data-stu-id="4da2b-610">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="4da2b-611">VI-Einfügemodus: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-611">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="4da2b-612">VI-Befehlsmodus: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-612">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="4da2b-613">Vervollständigungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="4da2b-613">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="4da2b-614">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="4da2b-614">Complete</span></span>

<span data-ttu-id="4da2b-615">Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-615">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="4da2b-616">Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet.</span><span class="sxs-lookup"><span data-stu-id="4da2b-616">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="4da2b-617">Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-617">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="4da2b-618">Ansehen `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-618">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="4da2b-619">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="4da2b-619">MenuComplete</span></span>

<span data-ttu-id="4da2b-620">Es wurde versucht, den Text, der den Cursor umgibt, abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-620">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="4da2b-621">Wenn mehrere mögliche Vervollständigungen vorhanden sind, wird für den Abschluss das längste eindeutige Präfix verwendet.</span><span class="sxs-lookup"><span data-stu-id="4da2b-621">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="4da2b-622">Wenn Sie versuchen, den längsten eindeutigen Abschluss abzuschließen, wird eine Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-622">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="4da2b-623">Cmd: `<Ctrl+@>` , `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-623">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="4da2b-624">Ansehen `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-624">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="4da2b-625">Possiblecompletions</span><span class="sxs-lookup"><span data-stu-id="4da2b-625">PossibleCompletions</span></span>

<span data-ttu-id="4da2b-626">Hiermit wird die Liste der möglichen Vervollständigungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-626">Display the list of possible completions.</span></span>

- <span data-ttu-id="4da2b-627">Ansehen `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-627">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="4da2b-628">VI-Einfügemodus: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-628">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="4da2b-629">VI-Befehlsmodus: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-629">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="4da2b-630">Tabcompletenext</span><span class="sxs-lookup"><span data-stu-id="4da2b-630">TabCompleteNext</span></span>

<span data-ttu-id="4da2b-631">Es wurde versucht, den Text, der den Cursor umgibt, mit der nächsten verfügbaren Beendigung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-631">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="4da2b-632">Befehl: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-632">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="4da2b-633">VI-Befehlsmodus: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-633">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="4da2b-634">Tabcompleteprevious</span><span class="sxs-lookup"><span data-stu-id="4da2b-634">TabCompletePrevious</span></span>

<span data-ttu-id="4da2b-635">Versuchen Sie, den Text, der den Cursor umgibt, mit dem vorherigen verfügbaren Abschluss abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-635">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="4da2b-636">Befehl: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-636">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="4da2b-637">VI-Befehlsmodus: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-637">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="4da2b-638">Vitabcompletenext</span><span class="sxs-lookup"><span data-stu-id="4da2b-638">ViTabCompleteNext</span></span>

<span data-ttu-id="4da2b-639">Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompletenext auf.</span><span class="sxs-lookup"><span data-stu-id="4da2b-639">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="4da2b-640">VI-Einfügemodus: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-640">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="4da2b-641">Vitabcompleteprevious</span><span class="sxs-lookup"><span data-stu-id="4da2b-641">ViTabCompletePrevious</span></span>

<span data-ttu-id="4da2b-642">Beendet die aktuelle Bearbeitungs Gruppe, falls erforderlich, und ruft tabcompleteprevious auf.</span><span class="sxs-lookup"><span data-stu-id="4da2b-642">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="4da2b-643">VI-Einfügemodus: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-643">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="4da2b-644">Sonstige Funktionen</span><span class="sxs-lookup"><span data-stu-id="4da2b-644">Miscellaneous functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="4da2b-645">Akzeptnextsuggestionword</span><span class="sxs-lookup"><span data-stu-id="4da2b-645">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="4da2b-646">Akzeptieren Sie das nächste Wort des Inline-oder ausgewählten Vorschlags.</span><span class="sxs-lookup"><span data-stu-id="4da2b-646">Accept the next word of the inline or selected suggestion.</span></span>

- <span data-ttu-id="4da2b-647">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-647">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="4da2b-648">Accept-Vorschlag</span><span class="sxs-lookup"><span data-stu-id="4da2b-648">AcceptSuggestion</span></span>

<span data-ttu-id="4da2b-649">Akzeptieren Sie den aktuellen Inline-oder ausgewählten Vorschlag.</span><span class="sxs-lookup"><span data-stu-id="4da2b-649">Accept the current inline or selected suggestion.</span></span>

- <span data-ttu-id="4da2b-650">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-650">Function is unbound.</span></span>

### <a name="capturescreen"></a><span data-ttu-id="4da2b-651">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="4da2b-651">CaptureScreen</span></span>

<span data-ttu-id="4da2b-652">Interaktive Bildschirmaufnahme starten-nach oben/nach-unten-Pfeile Select Lines, Enter kopiert markierten Text in die Zwischenablage als Text und HTML.</span><span class="sxs-lookup"><span data-stu-id="4da2b-652">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="4da2b-653">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-653">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="4da2b-654">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="4da2b-654">ClearScreen</span></span>

<span data-ttu-id="4da2b-655">Löschen Sie den Bildschirm, und zeichnen Sie die aktuelle Zeile am oberen Rand des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="4da2b-655">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="4da2b-656">Befehl: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-656">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="4da2b-657">Ansehen `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-657">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="4da2b-658">VI-Einfügemodus: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-658">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="4da2b-659">VI-Befehlsmodus: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-659">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="4da2b-660">Digitargument</span><span class="sxs-lookup"><span data-stu-id="4da2b-660">DigitArgument</span></span>

<span data-ttu-id="4da2b-661">Starten Sie ein neues Ziffern Argument, das an andere Funktionen übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="4da2b-661">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="4da2b-662">Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="4da2b-662">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="4da2b-663">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="4da2b-663">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="4da2b-664">VI-Befehlsmodus: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-664">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="4da2b-665">Invokeprompt</span><span class="sxs-lookup"><span data-stu-id="4da2b-665">InvokePrompt</span></span>

<span data-ttu-id="4da2b-666">Löscht die aktuelle Eingabeaufforderung und ruft die prompt-Funktion auf, um die Eingabeaufforderung erneut anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-666">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="4da2b-667">Nützlich für benutzerdefinierte Schlüssel Handler, die den Zustand ändern, z. b. Ändern des aktuellen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="4da2b-667">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="4da2b-668">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-668">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="4da2b-669">Scrolldisplaydown</span><span class="sxs-lookup"><span data-stu-id="4da2b-669">ScrollDisplayDown</span></span>

<span data-ttu-id="4da2b-670">Scrollen Sie in der Anzeige einen Bildschirm nach unten.</span><span class="sxs-lookup"><span data-stu-id="4da2b-670">Scroll the display down one screen.</span></span>

- <span data-ttu-id="4da2b-671">Befehl: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-671">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="4da2b-672">Ansehen `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-672">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="4da2b-673">Scrolldisplaydownline</span><span class="sxs-lookup"><span data-stu-id="4da2b-673">ScrollDisplayDownLine</span></span>

<span data-ttu-id="4da2b-674">Scrollen Sie in der Anzeige um eine Zeile nach unten.</span><span class="sxs-lookup"><span data-stu-id="4da2b-674">Scroll the display down one line.</span></span>

- <span data-ttu-id="4da2b-675">Befehl: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-675">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="4da2b-676">Ansehen `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-676">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="4da2b-677">Scrolldisplaytcursor</span><span class="sxs-lookup"><span data-stu-id="4da2b-677">ScrollDisplayToCursor</span></span>

<span data-ttu-id="4da2b-678">Scrollen Sie in der Anzeige zum Cursor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-678">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="4da2b-679">Ansehen `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-679">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="4da2b-680">Scrolldisplaytop</span><span class="sxs-lookup"><span data-stu-id="4da2b-680">ScrollDisplayTop</span></span>

<span data-ttu-id="4da2b-681">Scrollen Sie in der Anzeige nach oben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-681">Scroll the display to the top.</span></span>

- <span data-ttu-id="4da2b-682">Ansehen `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-682">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="4da2b-683">Scrolldisplayup</span><span class="sxs-lookup"><span data-stu-id="4da2b-683">ScrollDisplayUp</span></span>

<span data-ttu-id="4da2b-684">Scrollen Sie einen Bildschirm nach oben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-684">Scroll the display up one screen.</span></span>

- <span data-ttu-id="4da2b-685">Befehl: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-685">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="4da2b-686">Ansehen `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-686">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="4da2b-687">Scrolldisplayupline</span><span class="sxs-lookup"><span data-stu-id="4da2b-687">ScrollDisplayUpLine</span></span>

<span data-ttu-id="4da2b-688">Scrollen Sie in der Anzeige um eine Zeile nach oben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-688">Scroll the display up one line.</span></span>

- <span data-ttu-id="4da2b-689">Befehl: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-689">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="4da2b-690">Ansehen `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-690">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="4da2b-691">Selfinsert</span><span class="sxs-lookup"><span data-stu-id="4da2b-691">SelfInsert</span></span>

<span data-ttu-id="4da2b-692">Fügen Sie den Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="4da2b-692">Insert the key.</span></span>

- <span data-ttu-id="4da2b-693">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-693">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="4da2b-694">Showkeybindungen</span><span class="sxs-lookup"><span data-stu-id="4da2b-694">ShowKeyBindings</span></span>

<span data-ttu-id="4da2b-695">Alle gebundenen Schlüssel anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-695">Show all bound keys.</span></span>

- <span data-ttu-id="4da2b-696">Befehl: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-696">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="4da2b-697">Ansehen `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-697">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="4da2b-698">VI-Einfügemodus: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-698">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="4da2b-699">Vicommandmode</span><span class="sxs-lookup"><span data-stu-id="4da2b-699">ViCommandMode</span></span>

<span data-ttu-id="4da2b-700">Wechseln Sie in den aktuellen Betriebsmodus von Vi-Insert zu VI-Command.</span><span class="sxs-lookup"><span data-stu-id="4da2b-700">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="4da2b-701">VI-Einfügemodus: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-701">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="4da2b-702">Vidigitargumentinchord</span><span class="sxs-lookup"><span data-stu-id="4da2b-702">ViDigitArgumentInChord</span></span>

<span data-ttu-id="4da2b-703">Startet ein neues Ziffern Argument, das in einem der VI-Akkorde an andere Funktionen übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="4da2b-703">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="4da2b-704">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-704">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="4da2b-705">Vieditvisuell</span><span class="sxs-lookup"><span data-stu-id="4da2b-705">ViEditVisually</span></span>

<span data-ttu-id="4da2b-706">Bearbeiten Sie die Befehlszeile in einem Text-Editor, der durch $ENV: Editor oder $env: Visual angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4da2b-706">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="4da2b-707">Ansehen `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-707">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="4da2b-708">VI-Befehlsmodus: `<v>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-708">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="4da2b-709">Viexit</span><span class="sxs-lookup"><span data-stu-id="4da2b-709">ViExit</span></span>

<span data-ttu-id="4da2b-710">Beendet die Shell.</span><span class="sxs-lookup"><span data-stu-id="4da2b-710">Exits the shell.</span></span>

- <span data-ttu-id="4da2b-711">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-711">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="4da2b-712">Viinsertmode</span><span class="sxs-lookup"><span data-stu-id="4da2b-712">ViInsertMode</span></span>

<span data-ttu-id="4da2b-713">Wechselt in den Einfügemodus.</span><span class="sxs-lookup"><span data-stu-id="4da2b-713">Switch to Insert mode.</span></span>

- <span data-ttu-id="4da2b-714">VI-Befehlsmodus: `<i>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-714">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="4da2b-715">Whatiskey</span><span class="sxs-lookup"><span data-stu-id="4da2b-715">WhatIsKey</span></span>

<span data-ttu-id="4da2b-716">Lesen Sie einen Schlüssel, und teilen Sie mir mit, wofür der Schlüssel gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="4da2b-716">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="4da2b-717">Befehl: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-717">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="4da2b-718">Ansehen `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-718">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="4da2b-719">Auswahl Funktionen</span><span class="sxs-lookup"><span data-stu-id="4da2b-719">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="4da2b-720">Exchangepointandmark</span><span class="sxs-lookup"><span data-stu-id="4da2b-720">ExchangePointAndMark</span></span>

<span data-ttu-id="4da2b-721">Der Cursor wird an der Position der Markierung platziert, und die Markierung wird an die Position des Cursors verschoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-721">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="4da2b-722">Ansehen `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-722">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="4da2b-723">SelectAll</span><span class="sxs-lookup"><span data-stu-id="4da2b-723">SelectAll</span></span>

<span data-ttu-id="4da2b-724">Wählen Sie die gesamte Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="4da2b-724">Select the entire line.</span></span>

- <span data-ttu-id="4da2b-725">Befehl: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-725">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="4da2b-726">Selectbackwardchar</span><span class="sxs-lookup"><span data-stu-id="4da2b-726">SelectBackwardChar</span></span>

<span data-ttu-id="4da2b-727">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Zeichen einschließt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-727">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="4da2b-728">Befehl: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-728">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="4da2b-729">Ansehen `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-729">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="4da2b-730">Selectbackwardsline</span><span class="sxs-lookup"><span data-stu-id="4da2b-730">SelectBackwardsLine</span></span>

<span data-ttu-id="4da2b-731">Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an den Anfang der Zeile eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="4da2b-731">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="4da2b-732">Befehl: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-732">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="4da2b-733">Ansehen `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-733">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="4da2b-734">Selectbackwardword</span><span class="sxs-lookup"><span data-stu-id="4da2b-734">SelectBackwardWord</span></span>

<span data-ttu-id="4da2b-735">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort enthält.</span><span class="sxs-lookup"><span data-stu-id="4da2b-735">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="4da2b-736">Befehl: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-736">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="4da2b-737">Ansehen `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-737">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="4da2b-738">Selectforwardchar</span><span class="sxs-lookup"><span data-stu-id="4da2b-738">SelectForwardChar</span></span>

<span data-ttu-id="4da2b-739">Passen Sie die aktuelle Auswahl an, um das nächste Zeichen einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-739">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="4da2b-740">Befehl: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-740">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="4da2b-741">Ansehen `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-741">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="4da2b-742">Selectforwardword</span><span class="sxs-lookup"><span data-stu-id="4da2b-742">SelectForwardWord</span></span>

<span data-ttu-id="4da2b-743">Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mit forwardword einschließt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-743">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="4da2b-744">Ansehen `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-744">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="4da2b-745">SelectLine</span><span class="sxs-lookup"><span data-stu-id="4da2b-745">SelectLine</span></span>

<span data-ttu-id="4da2b-746">Passen Sie die aktuelle Auswahl so an, dass Sie vom Cursor an das Ende der Zeile eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="4da2b-746">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="4da2b-747">Befehl: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-747">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="4da2b-748">Ansehen `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-748">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="4da2b-749">Selectnextword</span><span class="sxs-lookup"><span data-stu-id="4da2b-749">SelectNextWord</span></span>

<span data-ttu-id="4da2b-750">Passen Sie die aktuelle Auswahl an das nächste Wort an.</span><span class="sxs-lookup"><span data-stu-id="4da2b-750">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="4da2b-751">Befehl: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-751">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="4da2b-752">Selectshellbackwardword</span><span class="sxs-lookup"><span data-stu-id="4da2b-752">SelectShellBackwardWord</span></span>

<span data-ttu-id="4da2b-753">Passen Sie die aktuelle Auswahl so an, dass Sie das vorherige Wort mithilfe von shellbackwardword einschließt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-753">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="4da2b-754">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-754">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="4da2b-755">Selectshellforwardword</span><span class="sxs-lookup"><span data-stu-id="4da2b-755">SelectShellForwardWord</span></span>

<span data-ttu-id="4da2b-756">Passen Sie die aktuelle Auswahl so an, dass das nächste Wort mithilfe von shellforwardword eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="4da2b-756">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="4da2b-757">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-757">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="4da2b-758">Selectshellnextword</span><span class="sxs-lookup"><span data-stu-id="4da2b-758">SelectShellNextWord</span></span>

<span data-ttu-id="4da2b-759">Passen Sie die aktuelle Auswahl so an, dass Sie das nächste Wort mithilfe von shellnextword einschließt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-759">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="4da2b-760">Die Bindung der Funktion ist aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-760">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="4da2b-761">Setmark</span><span class="sxs-lookup"><span data-stu-id="4da2b-761">SetMark</span></span>

<span data-ttu-id="4da2b-762">Markieren Sie die aktuelle Position des Cursors für die Verwendung in einem nachfolgenden Bearbeitungs Befehl.</span><span class="sxs-lookup"><span data-stu-id="4da2b-762">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="4da2b-763">Ansehen `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-763">Emacs: `<Ctrl+@>`</span></span>

## <a name="predictive-intellisense-functions"></a><span data-ttu-id="4da2b-764">Predictive IntelliSense-Funktionen</span><span class="sxs-lookup"><span data-stu-id="4da2b-764">Predictive IntelliSense functions</span></span>

> [!NOTE]
> <span data-ttu-id="4da2b-765">Predictive IntelliSense muss aktiviert werden, damit diese Funktionen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4da2b-765">Predictive IntelliSense needs to be enabled to use these functions.</span></span>

### <a name="acceptnextwordsuggestion"></a><span data-ttu-id="4da2b-766">Accept-nextwordsuggestion</span><span class="sxs-lookup"><span data-stu-id="4da2b-766">AcceptNextWordSuggestion</span></span>

<span data-ttu-id="4da2b-767">Akzeptiert das nächste Wort des Inline Vorschlags aus Predictive IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4da2b-767">Accepts the next word of the inline suggestion from Predictive IntelliSense.</span></span>
<span data-ttu-id="4da2b-768">Diese Funktion kann mit <kbd>STRG</kbd> + <kbd>F</kbd> gebunden werden, indem der folgende Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4da2b-768">This function can be bound with <kbd>Ctrl</kbd>+<kbd>F</kbd> by running the following command.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord "Ctrl+f" -Function ForwardWord
```

### <a name="acceptsuggestion"></a><span data-ttu-id="4da2b-769">Accept-Vorschlag</span><span class="sxs-lookup"><span data-stu-id="4da2b-769">AcceptSuggestion</span></span>

<span data-ttu-id="4da2b-770">Akzeptiert den aktuellen Inline Vorschlag von Predictive IntelliSense durch Drücken von <kbd>RIGHTARROW</kbd> , wenn sich der Cursor am Ende der aktuellen Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="4da2b-770">Accepts the current inline suggestion from Predictive IntelliSense by pressing <kbd>RightArrow</kbd> when the cursor is at the end of the current line.</span></span>

## <a name="search-functions"></a><span data-ttu-id="4da2b-771">Suchfunktionen</span><span class="sxs-lookup"><span data-stu-id="4da2b-771">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="4da2b-772">Merkmal Suche</span><span class="sxs-lookup"><span data-stu-id="4da2b-772">CharacterSearch</span></span>

<span data-ttu-id="4da2b-773">Lesen Sie ein Zeichen, und suchen Sie nach dem nächsten Vorkommen dieses Zeichens.</span><span class="sxs-lookup"><span data-stu-id="4da2b-773">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="4da2b-774">Wenn ein Argument angegeben ist, suchen Sie nach vorn (oder rückwärts, wenn negativ) für das n-te vorkommen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-774">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="4da2b-775">Befehl: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-775">Cmd: `<F3>`</span></span>
- <span data-ttu-id="4da2b-776">Ansehen `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-776">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="4da2b-777">VI-Einfügemodus: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-777">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="4da2b-778">VI-Befehlsmodus: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-778">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="4da2b-779">Merkmal searchrückwärts</span><span class="sxs-lookup"><span data-stu-id="4da2b-779">CharacterSearchBackward</span></span>

<span data-ttu-id="4da2b-780">Liest ein Zeichen und sucht rückwärts nach dem nächsten Vorkommen dieses Zeichens.</span><span class="sxs-lookup"><span data-stu-id="4da2b-780">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="4da2b-781">Wenn ein Argument angegeben wird, suchen Sie nach hinten (oder vorwärts, wenn negativ).</span><span class="sxs-lookup"><span data-stu-id="4da2b-781">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="4da2b-782">Befehl: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-782">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="4da2b-783">Ansehen `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-783">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="4da2b-784">VI-Einfügemodus: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-784">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="4da2b-785">VI-Befehlsmodus: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-785">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="4da2b-786">Repeatlastcharsearch</span><span class="sxs-lookup"><span data-stu-id="4da2b-786">RepeatLastCharSearch</span></span>

<span data-ttu-id="4da2b-787">Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche.</span><span class="sxs-lookup"><span data-stu-id="4da2b-787">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="4da2b-788">VI-Befehlsmodus: `<;>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-788">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="4da2b-789">Repeatlastcharsearchabwärts</span><span class="sxs-lookup"><span data-stu-id="4da2b-789">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="4da2b-790">Wiederholen Sie die zuletzt aufgezeichnete Zeichen Suche, aber in umgekehrter Richtung.</span><span class="sxs-lookup"><span data-stu-id="4da2b-790">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="4da2b-791">VI-Befehlsmodus: `<,>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-791">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="4da2b-792">Repeatsearch</span><span class="sxs-lookup"><span data-stu-id="4da2b-792">RepeatSearch</span></span>

<span data-ttu-id="4da2b-793">Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-793">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="4da2b-794">VI-Befehlsmodus: `<n>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-794">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="4da2b-795">Repeatsearchrückwärts</span><span class="sxs-lookup"><span data-stu-id="4da2b-795">RepeatSearchBackward</span></span>

<span data-ttu-id="4da2b-796">Wiederholen Sie die letzte Suche in der gleichen Richtung wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="4da2b-796">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="4da2b-797">VI-Befehlsmodus: `<N>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-797">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="4da2b-798">Searchchar</span><span class="sxs-lookup"><span data-stu-id="4da2b-798">SearchChar</span></span>

<span data-ttu-id="4da2b-799">Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="4da2b-799">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="4da2b-800">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4da2b-800">This is for 't' functionality.</span></span>

- <span data-ttu-id="4da2b-801">VI-Befehlsmodus: `<f>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-801">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="4da2b-802">Searchcharrückwärts</span><span class="sxs-lookup"><span data-stu-id="4da2b-802">SearchCharBackward</span></span>

<span data-ttu-id="4da2b-803">Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück.</span><span class="sxs-lookup"><span data-stu-id="4da2b-803">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="4da2b-804">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4da2b-804">This is for 'T' functionality.</span></span>

- <span data-ttu-id="4da2b-805">VI-Befehlsmodus: `<F>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-805">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="4da2b-806">Searchcharbackwardwithbackoff</span><span class="sxs-lookup"><span data-stu-id="4da2b-806">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="4da2b-807">Lesen Sie das nächste Zeichen, und suchen Sie es nach hinten, und kehren Sie dann zurück.</span><span class="sxs-lookup"><span data-stu-id="4da2b-807">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="4da2b-808">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4da2b-808">This is for 'T' functionality.</span></span>

- <span data-ttu-id="4da2b-809">VI-Befehlsmodus: `<T>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-809">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="4da2b-810">Searchcharwithbackoff</span><span class="sxs-lookup"><span data-stu-id="4da2b-810">SearchCharWithBackoff</span></span>

<span data-ttu-id="4da2b-811">Lesen Sie das nächste Zeichen und suchen Sie es, und kehren Sie dann zu einem Zeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="4da2b-811">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="4da2b-812">Dies ist für die Funktion 't verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4da2b-812">This is for 't' functionality.</span></span>

- <span data-ttu-id="4da2b-813">VI-Befehlsmodus: `<t>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-813">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="4da2b-814">SearchForward</span><span class="sxs-lookup"><span data-stu-id="4da2b-814">SearchForward</span></span>

<span data-ttu-id="4da2b-815">Fordert eine Such Zeichenfolge an und initiiert die Suche nach Accept Line.</span><span class="sxs-lookup"><span data-stu-id="4da2b-815">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="4da2b-816">VI-Einfügemodus: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-816">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="4da2b-817">VI-Befehlsmodus: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="4da2b-817">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="4da2b-818">Benutzerdefinierte Tastenbindungen</span><span class="sxs-lookup"><span data-stu-id="4da2b-818">Custom Key Bindings</span></span>

<span data-ttu-id="4da2b-819">Psread Line unterstützt benutzerdefinierte Tastenbindungen mithilfe des Cmdlets `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="4da2b-819">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="4da2b-820">Die meisten benutzerdefinierten Tastenbindungen wenden eine der oben genannten Funktionen an, z. b.</span><span class="sxs-lookup"><span data-stu-id="4da2b-820">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="4da2b-821">Sie können einen ScriptBlock an einen Schlüssel binden.</span><span class="sxs-lookup"><span data-stu-id="4da2b-821">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="4da2b-822">Der ScriptBlock kann beliebig viele Aufgaben erledigen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-822">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="4da2b-823">Einige nützliche Beispiele sind u.a.</span><span class="sxs-lookup"><span data-stu-id="4da2b-823">Some useful examples include</span></span>

- <span data-ttu-id="4da2b-824">Bearbeiten der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="4da2b-824">edit the command line</span></span>
- <span data-ttu-id="4da2b-825">Öffnen eines neuen Fensters (z. b. "Hilfe")</span><span class="sxs-lookup"><span data-stu-id="4da2b-825">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="4da2b-826">Ändern der Verzeichnisse ohne Änderung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="4da2b-826">change directories without changing the command line</span></span>

<span data-ttu-id="4da2b-827">Der ScriptBlock empfängt zwei Argumente:</span><span class="sxs-lookup"><span data-stu-id="4da2b-827">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="4da2b-828">`$key` -Ein **[ConsoleKeyInfo]** -Objekt, das der Schlüssel ist, der die benutzerdefinierte Bindung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="4da2b-828">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="4da2b-829">Wenn Sie denselben ScriptBlock an mehrere Schlüssel binden und abhängig vom Schlüssel verschiedene Aktionen ausführen müssen, können Sie $Key überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-829">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="4da2b-830">Viele benutzerdefinierte Bindungen ignorieren dieses Argument.</span><span class="sxs-lookup"><span data-stu-id="4da2b-830">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="4da2b-831">`$arg` -Ein beliebiges Argument.</span><span class="sxs-lookup"><span data-stu-id="4da2b-831">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="4da2b-832">In den meisten Fällen ist dies ein ganzzahliges Argument, das der Benutzer von den Schlüsselbindungen digitargument übergibt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-832">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="4da2b-833">Wenn die Bindung keine Argumente akzeptiert, ist es sinnvoll, dieses Argument zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="4da2b-833">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="4da2b-834">Sehen wir uns ein Beispiel an, in dem eine Befehlszeile zum Verlauf hinzugefügt wird, ohne sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-834">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="4da2b-835">Dies ist nützlich, wenn Sie vergessen haben, etwas zu tun, ohne die Befehlszeile, die Sie bereits eingegeben haben, erneut eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-835">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="4da2b-836">In der Datei `SamplePSReadLineProfile.ps1` , die im psread Line-Modul Ordner installiert ist, werden viele weitere Beispiele angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-836">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="4da2b-837">Die meisten Tastenbindungen verwenden einige Hilfsfunktionen zum Bearbeiten der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="4da2b-837">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="4da2b-838">Diese APIs werden im nächsten Abschnitt dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-838">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="4da2b-839">APIs für die benutzerdefinierte Schlüssel Bindungs Unterstützung</span><span class="sxs-lookup"><span data-stu-id="4da2b-839">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="4da2b-840">Die folgenden Funktionen sind in Microsoft. PowerShell. psconsolereadline öffentlich, können jedoch nicht direkt an einen Schlüssel gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="4da2b-840">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="4da2b-841">Die meisten sind in benutzerdefinierten Tastenkombinationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="4da2b-841">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="4da2b-842">Fügen Sie eine Befehlszeile zum Verlauf hinzu, ohne sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-842">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="4da2b-843">Löschen Sie den Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="4da2b-843">Clear the kill-ring.</span></span>  <span data-ttu-id="4da2b-844">Dies wird größtenteils zum Testen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4da2b-844">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="4da2b-845">Löschen Sie die Längen Zeichen aus dem Startmenü.</span><span class="sxs-lookup"><span data-stu-id="4da2b-845">Delete length characters from start.</span></span>  <span data-ttu-id="4da2b-846">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-846">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="4da2b-847">Führen Sie die Aktion "Ding" basierend auf der Benutzereinstellung aus.</span><span class="sxs-lookup"><span data-stu-id="4da2b-847">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="4da2b-848">Diese beiden Funktionen rufen nützliche Informationen über den aktuellen Status des Eingabe Puffers ab.</span><span class="sxs-lookup"><span data-stu-id="4da2b-848">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="4da2b-849">Der erste wird häufiger für einfache Fälle verwendet.</span><span class="sxs-lookup"><span data-stu-id="4da2b-849">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="4da2b-850">Die zweite wird verwendet, wenn ihre Bindung einen fortgeschrittenen Vorgang mit der AST bewirkt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-850">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="4da2b-851">Diese beiden Funktionen werden von verwendet `Get-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="4da2b-851">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="4da2b-852">Der erste wird verwendet, um alle Tastenbindungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4da2b-852">The first is used to get all key bindings.</span></span> <span data-ttu-id="4da2b-853">Die zweite wird verwendet, um bestimmte Tastenbindungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4da2b-853">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="4da2b-854">Diese Funktion wird von Get-PSReadLineOption verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.</span><span class="sxs-lookup"><span data-stu-id="4da2b-854">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="4da2b-855">Wenn in der Befehlszeile keine Auswahl vorhanden ist, wird-1 sowohl in Start als auch in der Länge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-855">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="4da2b-856">Wenn eine Auswahl in der Befehlszeile vorhanden ist, werden Start und Länge der Auswahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-856">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="4da2b-857">Fügen Sie am Cursor ein Zeichen oder eine Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="4da2b-857">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="4da2b-858">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-858">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="4da2b-859">Dies ist der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="4da2b-859">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="4da2b-860">Sie unterstützt keine Rekursion und ist daher in einer benutzerdefinierten schlüsselbindung nicht nützlich.</span><span class="sxs-lookup"><span data-stu-id="4da2b-860">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="4da2b-861">Diese Funktion wird von Remove-PSReadLineKeyHandler verwendet und ist in einer benutzerdefinierten schlüsselbindung wahrscheinlich nicht zu nützlich.</span><span class="sxs-lookup"><span data-stu-id="4da2b-861">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="4da2b-862">Ersetzen Sie einige der Eingaben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-862">Replace some of the input.</span></span> <span data-ttu-id="4da2b-863">Dieser Vorgang unterstützt rückgängig/wiederholen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-863">This operation supports undo/redo.</span></span> <span data-ttu-id="4da2b-864">Dies wird als "Delete", gefolgt von INSERT, bevorzugt, da es als einzelne Aktion für "Rückgängig" behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="4da2b-864">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="4da2b-865">Bewegen Sie den Cursor in den angegebenen Offset.</span><span class="sxs-lookup"><span data-stu-id="4da2b-865">Move the cursor to the given offset.</span></span> <span data-ttu-id="4da2b-866">Cursor Bewegung wird nicht für Rückgängigmachen nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="4da2b-866">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="4da2b-867">Bei dieser Funktion handelt es sich um eine Hilfsmethode, die vom Cmdlet Set-psread lineoption verwendet wird. Sie kann jedoch für eine benutzerdefinierte schlüsselbindung nützlich sein, die eine Einstellung vorübergehend ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="4da2b-867">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="4da2b-868">Diese Hilfsmethode wird für benutzerdefinierte Bindungen verwendet, die digitargument berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-868">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="4da2b-869">Ein typischer-Rückruf sieht wie folgt aus</span><span class="sxs-lookup"><span data-stu-id="4da2b-869">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="notes"></a><span data-ttu-id="4da2b-870">Notizen</span><span class="sxs-lookup"><span data-stu-id="4da2b-870">Notes</span></span>

### <a name="command-history"></a><span data-ttu-id="4da2b-871">Befehlsverlauf</span><span class="sxs-lookup"><span data-stu-id="4da2b-871">Command History</span></span>

<span data-ttu-id="4da2b-872">Psleseline verwaltet eine Verlaufs Datei, die alle Befehle und Daten enthält, die Sie in der Befehlszeile eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="4da2b-872">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="4da2b-873">Dies kann vertrauliche Daten einschließlich Kenn Wörtern enthalten.</span><span class="sxs-lookup"><span data-stu-id="4da2b-873">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="4da2b-874">Wenn Sie z. b. das `ConvertTo-SecureString` Cmdlet verwenden, wird das Kennwort als nur-Text in der Verlaufs Datei protokolliert.</span><span class="sxs-lookup"><span data-stu-id="4da2b-874">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="4da2b-875">Die Verlaufs Dateien sind eine Datei mit dem Namen `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="4da2b-875">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="4da2b-876">Auf Windows-Systemen wird die Verlaufs Datei unter gespeichert `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="4da2b-876">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="4da2b-877">Auf nicht-Windows-Systemen werden die Verlaufs Dateien unter `$env:XDG_DATA_HOME/powershell/PSReadLine` oder gespeichert `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="4da2b-877">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="4da2b-878">Feedback & zu psread Line beitragen</span><span class="sxs-lookup"><span data-stu-id="4da2b-878">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="4da2b-879">Psread Line auf GitHub</span><span class="sxs-lookup"><span data-stu-id="4da2b-879">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="4da2b-880">Sie können auf der GitHub-Seite eine Pull Request einreichen oder Feedback einreichen.</span><span class="sxs-lookup"><span data-stu-id="4da2b-880">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="4da2b-881">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4da2b-881">See Also</span></span>

<span data-ttu-id="4da2b-882">"Psread Line" wird stark von der GNU-Bibliothek für die [Zeilen](https://tiswww.case.edu/php/chet/readline/rltop.html) Übereinstimmung beeinflusst</span><span class="sxs-lookup"><span data-stu-id="4da2b-882">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
