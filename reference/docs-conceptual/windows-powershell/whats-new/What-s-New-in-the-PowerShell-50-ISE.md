---
ms.date: 09/06/2019
keywords: powershell,cmdlet
title: Neuigkeiten bei PowerShell 5.0 ISE
description: In diesem Artikel werden die neuen und aktualisierten Features vorgestellt, die in Version 5.0 der Windows PowerShell Integrated Scripting Environment (ISE) eingeführt wurden.
ms.openlocfilehash: 75d37d0dafe381c84898ac48343336cd525d2dd1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660831"
---
# <a name="whats-new-in-the-windows-powershell-50-ise"></a><span data-ttu-id="08981-104">Neuigkeiten bei Windows PowerShell 5.0 ISE</span><span class="sxs-lookup"><span data-stu-id="08981-104">What's New in the Windows PowerShell 5.0 ISE</span></span>

<span data-ttu-id="08981-105">In diesem Artikel werden die neuen und aktualisierten Features vorgestellt, die in Version 5.0 der Windows PowerShell Integrated Scripting Environment (ISE) eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="08981-105">This article explains the new and updated features that have been introduced in version 5.0 of the Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

> [!NOTE]
> <span data-ttu-id="08981-106">Die PowerShell ISE befindet sich nicht mehr in der aktiven Featureentwicklung.</span><span class="sxs-lookup"><span data-stu-id="08981-106">The PowerShell ISE is no longer in active feature development.</span></span> <span data-ttu-id="08981-107">Als in Windows enthaltene Komponente wird sie weiterhin offiziell mit Sicherheits- und Wartungsfixes hoher Priorität unterstützt.</span><span class="sxs-lookup"><span data-stu-id="08981-107">As a shipping component of Windows, it continues to be officially supported for security and high-priority servicing fixes.</span></span>
> <span data-ttu-id="08981-108">Zurzeit ist es nicht geplant, die ISE aus Windows zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="08981-108">We currently have no plans to remove the ISE from Windows.</span></span>
>
> <span data-ttu-id="08981-109">Es besteht keine Unterstützung für die ISE in PowerShell v6 oder höher.</span><span class="sxs-lookup"><span data-stu-id="08981-109">There is no support for the ISE in PowerShell v6 and beyond.</span></span> <span data-ttu-id="08981-110">Benutzer, die einen Ersatz für die ISE suchen, sollten [Visual Studio Code](https://code.visualstudio.com/) mit der [PowerShell-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell) verwenden.</span><span class="sxs-lookup"><span data-stu-id="08981-110">Users looking for replacement for the ISE should use [Visual Studio Code](https://code.visualstudio.com/) with the [PowerShell Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell).</span></span>

## <a name="feature-description"></a><span data-ttu-id="08981-111">Featurebeschreibung</span><span class="sxs-lookup"><span data-stu-id="08981-111">Feature description</span></span>

<span data-ttu-id="08981-112">Die Windows PowerShell ISE ist eine Hostanwendung, die es Ihnen ermöglicht, Skripts und Module in einer grafischen und intuitiven Umgebung zu schreiben, auszuführen und zu testen.</span><span class="sxs-lookup"><span data-stu-id="08981-112">The Windows PowerShell ISE is a host application that enables you to write, run, and test scripts and modules in a graphical and intuitive environment.</span></span> <span data-ttu-id="08981-113">Wichtige Features wie farbliche Syntaxkennzeichnung, Vervollständigung mit der TAB-Taste, visuelles Debuggen, Unicode-Kompatibilität und kontextbezogene Hilfe ermöglichen eine komfortable Skripterstellung.</span><span class="sxs-lookup"><span data-stu-id="08981-113">Key features such as syntax-coloring, tab completion, visual debugging, Unicode compliance, and context-sensitive Help provide a rich scripting experience.</span></span>

<span data-ttu-id="08981-114">Weitere Informationen finden Sie unter [Windows PowerShell ISE](../ise/Introducing-the-Windows-PowerShell-ISE.md).</span><span class="sxs-lookup"><span data-stu-id="08981-114">For more information, see [Introducing the Windows PowerShell ISE](../ise/Introducing-the-Windows-PowerShell-ISE.md).</span></span>

<span data-ttu-id="08981-115">Die folgende Tabelle enthält die neuen und geänderten Funktionen für diese Version von Windows PowerShell ISE in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08981-115">The following table lists the new and changed features for this release of Windows PowerShell ISE in Windows PowerShell.</span></span>

## <a name="intellisense"></a><span data-ttu-id="08981-116">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="08981-116">IntelliSense</span></span>

> <span data-ttu-id="08981-117">In ISE 3.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="08981-117">Added in ISE 3.0</span></span>

<span data-ttu-id="08981-118">IntelliSense ist ein Feature für die automatische Vervollständigung, das zur Windows PowerShell ISE gehört.</span><span class="sxs-lookup"><span data-stu-id="08981-118">IntelliSense is an automatic-completion assistance feature that is part of Windows PowerShell ISE.</span></span>
<span data-ttu-id="08981-119">IntelliSense zeigt während der Eingabe klickbare Menüs möglicherweise übereinstimmender Cmdlets, Parameter, Parameterwerte, Dateien oder Ordner an.</span><span class="sxs-lookup"><span data-stu-id="08981-119">IntelliSense displays clickable menus of potentially matching cmdlets, parameters, parameter values, files, or folders as you type.</span></span>

<span data-ttu-id="08981-120">**Welchen Nutzen bietet diese Änderung?**</span><span class="sxs-lookup"><span data-stu-id="08981-120">**What value does this change add?**</span></span>

<span data-ttu-id="08981-121">Durch Hinzufügen von IntelliSense ist es einfacher, Cmdlets und Syntax zu ermitteln, wenn Sie die Windows PowerShell ISE zum Erstellen von Skripts nutzen.</span><span class="sxs-lookup"><span data-stu-id="08981-121">With the addition of IntelliSense, it's easier to discover cmdlets and syntax when you use Windows PowerShell ISE to create scripts.</span></span> <span data-ttu-id="08981-122">Sie können mithilfe von Windows PowerShell ISE auch Windows PowerShell erlernen, während Sie neue Skripts erstellen.</span><span class="sxs-lookup"><span data-stu-id="08981-122">You can also use Windows PowerShell ISE to learn Windows PowerShell while you create new scripts.</span></span>

<span data-ttu-id="08981-123">**Worin bestehen die Unterschiede?**</span><span class="sxs-lookup"><span data-stu-id="08981-123">**What works differently?**</span></span>

<span data-ttu-id="08981-124">Bei Eingabe von Cmdlets in die Windows PowerShell ISE wird ein scrollfähiges und klickbares Menü angezeigt, das Ihnen das Durchsuchen und Auswählen der entsprechenden Befehle ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="08981-124">When you type cmdlets in the Windows PowerShell ISE, a scrollable and clickable menu displays, allowing you to browse and select the appropriate commands.</span></span>

## <a name="snippets"></a><span data-ttu-id="08981-125">Codeausschnitte</span><span class="sxs-lookup"><span data-stu-id="08981-125">Snippets</span></span>

> <span data-ttu-id="08981-126">In ISE 3.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="08981-126">Added in ISE 3.0</span></span>

<span data-ttu-id="08981-127">*Codeausschnitte* sind kurze Abschnitte von Windows PowerShell-Code, die Sie in die in Windows PowerShell ISE erstellten Skripts einfügen können.</span><span class="sxs-lookup"><span data-stu-id="08981-127">*Snippets* are short sections of Windows PowerShell code that you can insert into the scripts you create in Windows PowerShell ISE.</span></span> <span data-ttu-id="08981-128">Windows PowerShell ISE bietet einen Standardsatz von Codeausschnitten.</span><span class="sxs-lookup"><span data-stu-id="08981-128">Windows PowerShell ISE comes with a default set of snippets.</span></span> <span data-ttu-id="08981-129">Beim Arbeiten in der Windows PowerShell ISE können Sie Codeausschnitte mithilfe des Cmdlets `New-Snippet` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="08981-129">You can add snippets by using the `New-Snippet` cmdlet while working in Windows PowerShell ISE.</span></span>

<span data-ttu-id="08981-130">**Welchen Nutzen bietet diese Änderung?**</span><span class="sxs-lookup"><span data-stu-id="08981-130">**What value does this change add?**</span></span>

<span data-ttu-id="08981-131">Mithilfe von Codeausschnitten können Sie Skripts zum Automatisieren Ihrer Umgebung schnell zusammenstellen und erstellen.</span><span class="sxs-lookup"><span data-stu-id="08981-131">By using snippets, you can quickly assemble and create scripts to automate your environment.</span></span>

<span data-ttu-id="08981-132">**Worin bestehen die Unterschiede?**</span><span class="sxs-lookup"><span data-stu-id="08981-132">**What works differently?**</span></span>

<span data-ttu-id="08981-133">Klicken Sie zum Verwenden von Codeausschnitten in Windows PowerShell 3.0 oder höher im Menü **Bearbeiten** auf **Codeausschnitte starten** , oder drücken Sie <kbd>STRG</kbd>+<kbd>J</kbd>.</span><span class="sxs-lookup"><span data-stu-id="08981-133">To use snippets in Windows PowerShell 3.0 or later, on the **Edit** menu, click **Start Snippets** , or press <kbd>Ctrl</kbd>+<kbd>J</kbd>.</span></span>

## <a name="add-on-tools"></a><span data-ttu-id="08981-134">Add-On-Tools</span><span class="sxs-lookup"><span data-stu-id="08981-134">Add-on tools</span></span>

> <span data-ttu-id="08981-135">In PowerShell 3.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="08981-135">Added in PowerShell 3.0</span></span>

<span data-ttu-id="08981-136">Windows PowerShell ISE unterstützt jetzt Add-On-Tools, die das Objektmodell verwenden.</span><span class="sxs-lookup"><span data-stu-id="08981-136">Windows PowerShell ISE now supports add-on tools using the object model.</span></span> <span data-ttu-id="08981-137">Diese Add-Ons sind Windows Presentation Foundation-Steuerelemente (WPF), die in der Konsole als vertikaler oder horizontaler Bereich angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="08981-137">These add-ons are Windows Presentation Foundation (WPF) controls that are displayed as a vertical or horizontal pane in the console.</span></span> <span data-ttu-id="08981-138">Mehrere Add-On-Tools in einem Bereich werden als Registerkarten-Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08981-138">Multiple add-on tools in a pane are displayed as a tabbed control.</span></span> <span data-ttu-id="08981-139">Sie können auch Add-On-Tools von anderen Anbietern als Microsoft hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="08981-139">You can also add or remove add-on tools that are produced by non-Microsoft parties.</span></span> <span data-ttu-id="08981-140">Weitere Informationen finden Sie unter [Zweck des Windows PowerShell ISE-Skriptobjektmodells](../ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md).</span><span class="sxs-lookup"><span data-stu-id="08981-140">For more information, see [The Purpose of the Windows PowerShell ISE Scripting Object Model](../ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md).</span></span>

<span data-ttu-id="08981-141">**Welchen Nutzen bietet diese Änderung?**</span><span class="sxs-lookup"><span data-stu-id="08981-141">**What value does this change add?**</span></span>

<span data-ttu-id="08981-142">Add-Ons ermöglichen Ihnen das Erweitern und Anpassen der Windows PowerShell ISE mit Tools, die die Funktionalität erweitern und Ihre Skripterstellungsumgebung verbessern.</span><span class="sxs-lookup"><span data-stu-id="08981-142">Add-ons allow you to extend and customize Windows PowerShell ISE with tools that add functionality and enhance your scripting experience.</span></span>

<span data-ttu-id="08981-143">**Worin bestehen die Unterschiede?**</span><span class="sxs-lookup"><span data-stu-id="08981-143">**What works differently?**</span></span>

<span data-ttu-id="08981-144">Zum Funktionsumfang der Windows PowerShell ISE 3.0 und höher gehört das Add-On **Befehle**.</span><span class="sxs-lookup"><span data-stu-id="08981-144">Windows PowerShell ISE 3.0 and later come with the **Commands** add-on.</span></span> <span data-ttu-id="08981-145">Das Add-On **Befehle** ermöglicht das Durchsuchen von Cmdlets und das Zugreifen auf die Hilfe zu den Cmdlets. Es wird neben den Bereichen **Skript** und **Konsole** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08981-145">The **Commands** add-on allows you to browse cmdlets, and access help about the cmdlets side-by-side with the **Script** and **Console** Panes.</span></span>

<span data-ttu-id="08981-146">Zusätzliche Add-Ons finden Sie über den Befehl **Website mit Add-On-Tools öffnen** im Menü **Add-Ons**.</span><span class="sxs-lookup"><span data-stu-id="08981-146">Additional add-ons can be found by using the **Open Add-on Tools Website** command on the **Add-ons** menu.</span></span>

## <a name="restart-manager-and-auto-save"></a><span data-ttu-id="08981-147">Neustart-Manager und automatisches Speichern</span><span class="sxs-lookup"><span data-stu-id="08981-147">Restart manager and auto-save</span></span>

> <span data-ttu-id="08981-148">In PowerShell 3.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="08981-148">Added in PowerShell 3.0</span></span>

<span data-ttu-id="08981-149">Windows PowerShell ISE speichert nun Ihre geöffneten Skripts automatisch alle zwei Minuten an einem gesonderten Speicherort.</span><span class="sxs-lookup"><span data-stu-id="08981-149">Windows PowerShell ISE now automatically saves your open scripts every two minutes, in a separate location.</span></span> <span data-ttu-id="08981-150">Wenn Windows PowerShell ISE nach einem unerwarteten Absturz oder geplant neu startet, werden die in der letzten Sitzung geöffneten Skripts auch dann wiederhergestellt, wenn die Skripts nicht gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="08981-150">When Windows PowerShell ISE restarts after an unexpected crash or reboot, it recovers scripts that were open in the last session, even if the scripts weren't saved.</span></span>

<span data-ttu-id="08981-151">Führen Sie im Konsolenbereich den folgenden Befehl aus, um das Intervall für die automatische Speicherung zu ändern: `$psise.Options.AutoSaveMinuteInterval`.</span><span class="sxs-lookup"><span data-stu-id="08981-151">To change the automatic saving interval, run the following command in the Console pane: `$psise.Options.AutoSaveMinuteInterval`.</span></span>

<span data-ttu-id="08981-152">**Welchen Nutzen bietet diese Änderung?**</span><span class="sxs-lookup"><span data-stu-id="08981-152">**What value does this change add?**</span></span>

<span data-ttu-id="08981-153">Sie können jetzt mit Windows PowerShell ISE mit dem Wissen arbeiten, dass Ihre geöffneten Skripts automatisch gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="08981-153">You can now work within Windows PowerShell ISE knowing that your open scripts are automatically saved.</span></span>

<span data-ttu-id="08981-154">**Worin bestehen die Unterschiede?**</span><span class="sxs-lookup"><span data-stu-id="08981-154">**What works differently?**</span></span>

<span data-ttu-id="08981-155">In Windows PowerShell ISE 2.0 werden die Skripts nicht automatisch gespeichert.</span><span class="sxs-lookup"><span data-stu-id="08981-155">Windows PowerShell ISE 2.0 doesn't save the scripts automatically.</span></span>

## <a name="most-recently-used-list"></a><span data-ttu-id="08981-156">Liste „Zuletzt verwendet“</span><span class="sxs-lookup"><span data-stu-id="08981-156">Most-recently used list</span></span>

> <span data-ttu-id="08981-157">In PowerShell 3.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="08981-157">Added in PowerShell 3.0</span></span>

<span data-ttu-id="08981-158">Die Windows PowerShell ISE bietet jetzt eine Liste der zuletzt verwendeten Dateien.</span><span class="sxs-lookup"><span data-stu-id="08981-158">Windows PowerShell ISE now has a most-recently used list for files.</span></span> <span data-ttu-id="08981-159">Beim Öffnen einer Datei in der Windows PowerShell ISE wird die Datei der Liste „Zuletzt verwendet“ im Menü **Datei** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="08981-159">When you open a file in Windows PowerShell ISE, the file is added to the most-recently used list on the **File** menu.</span></span>

<span data-ttu-id="08981-160">Führen Sie im Konsolenbereich den folgenden Befehl aus, um die Standardanzahl von Dateien in der Liste „Zuletzt verwendet“ zu ändern: `$psise.Options.MruCount`.</span><span class="sxs-lookup"><span data-stu-id="08981-160">To change the default number of files in the most-recently used list, run the following command in the Console Pane: `$psise.Options.MruCount`.</span></span>

<span data-ttu-id="08981-161">**Welchen Nutzen bietet diese Änderung?**</span><span class="sxs-lookup"><span data-stu-id="08981-161">**What value does this change add?**</span></span>

<span data-ttu-id="08981-162">Über die Liste „Zuletzt verwendet“ können Sie nun mühelos auf die zuletzt verwendeten Dateien zugreifen.</span><span class="sxs-lookup"><span data-stu-id="08981-162">You can now use the most-recently used list to easily access your frequently used files.</span></span>

<span data-ttu-id="08981-163">**Worin bestehen die Unterschiede?**</span><span class="sxs-lookup"><span data-stu-id="08981-163">**What works differently?**</span></span>

<span data-ttu-id="08981-164">Die Windows PowerShell ISE 2.0 bietet keine solche Liste.</span><span class="sxs-lookup"><span data-stu-id="08981-164">Windows PowerShell ISE 2.0 doesn't have a most-recently used list.</span></span>

## <a name="console-pane"></a><span data-ttu-id="08981-165">Konsolenbereich</span><span class="sxs-lookup"><span data-stu-id="08981-165">Console Pane</span></span>

> <span data-ttu-id="08981-166">In PowerShell 3.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="08981-166">Added in PowerShell 3.0</span></span>

<span data-ttu-id="08981-167">Die separaten Befehls- und Ausgabebereiche, die in der ersten Version der Windows PowerShell ISE verfügbar waren, wurden in einem Konsolenbereich kombiniert.</span><span class="sxs-lookup"><span data-stu-id="08981-167">The separate Command and Output Panes that were available in the first release of Windows PowerShell ISE have been combined into a single Console Pane.</span></span> <span data-ttu-id="08981-168">Von der Funktion und Darstellung ähnelt der Konsolenbereich einer typischen Windows PowerShell-Konsole, er bietet aber die im Folgenden aufgeführten Erweiterungen:</span><span class="sxs-lookup"><span data-stu-id="08981-168">The Console Pane is similar in function and appearance to a typical Windows PowerShell console, but it includes the following enhancements:</span></span>

- <span data-ttu-id="08981-169">Syntaxfarben für Eingabetext (nicht für Ausgabetext), einschließlich XML-Syntax</span><span class="sxs-lookup"><span data-stu-id="08981-169">Syntax coloring for input text (not output text), including XML syntax</span></span>
- <span data-ttu-id="08981-170">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="08981-170">IntelliSense</span></span>
- <span data-ttu-id="08981-171">Klammernabgleich (zugehörige Klammer)</span><span class="sxs-lookup"><span data-stu-id="08981-171">Brace matching</span></span>
- <span data-ttu-id="08981-172">Fehleranzeige</span><span class="sxs-lookup"><span data-stu-id="08981-172">Error indication</span></span>
- <span data-ttu-id="08981-173">Vollständige Unicode-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="08981-173">Full Unicode support</span></span>
- <span data-ttu-id="08981-174">Kontextbezogene Hilfe über <kbd>F1</kbd></span><span class="sxs-lookup"><span data-stu-id="08981-174"><kbd>F1</kbd> context-sensitive help</span></span>
- <span data-ttu-id="08981-175">Kontextbezogene Befehlsanzeige (Show-Command) über <kbd>STRG</kbd>+<kbd>F1</kbd></span><span class="sxs-lookup"><span data-stu-id="08981-175"><kbd>Ctrl</kbd>+<kbd>F1</kbd> context-sensitive Show-Command</span></span>
- <span data-ttu-id="08981-176">Unterstützung für komplexe Skripts und Sprachen mit Leserichtung von rechts nach links</span><span class="sxs-lookup"><span data-stu-id="08981-176">Complex script and right-to-left support</span></span>
- <span data-ttu-id="08981-177">Schriftartenunterstützung</span><span class="sxs-lookup"><span data-stu-id="08981-177">Font support</span></span>
- <span data-ttu-id="08981-178">Zoom</span><span class="sxs-lookup"><span data-stu-id="08981-178">Zoom</span></span>
- <span data-ttu-id="08981-179">Modi für Linien- und Blockauswahl</span><span class="sxs-lookup"><span data-stu-id="08981-179">Line-select and block-select modes</span></span>
- <span data-ttu-id="08981-180">Beibehaltung von über die Befehlszeile eingegebenem Inhalt, wenn Sie mithilfe der <kbd>NACH-OBEN-TASTE</kbd> den Verlauf in der Konsole anzeigen</span><span class="sxs-lookup"><span data-stu-id="08981-180">Preservation of typed content at the command line when you press the <kbd>UpArrow</kbd> to view history in the console</span></span>

<span data-ttu-id="08981-181">**Welchen Nutzen bietet diese Änderung?**</span><span class="sxs-lookup"><span data-stu-id="08981-181">**What value does this change add?**</span></span>

<span data-ttu-id="08981-182">Diese Änderungen im Konsolenbereich ermöglichen eine Skripterstellungsumgebung, die mit der Konsolenschnittstelle konsistenter ist.</span><span class="sxs-lookup"><span data-stu-id="08981-182">The addition of these Console Pane changes provides a scripting experience that is more consistent with the console interface.</span></span>

<span data-ttu-id="08981-183">**Worin bestehen die Unterschiede?**</span><span class="sxs-lookup"><span data-stu-id="08981-183">**What works differently?**</span></span>

<span data-ttu-id="08981-184">Die Windows PowerShell ISE 2.0 verfügt über getrennte Befehls- und Ausgabebereiche.</span><span class="sxs-lookup"><span data-stu-id="08981-184">Windows PowerShell ISE 2.0 has separate Command and Output Panes.</span></span>

## <a name="command-line-switches"></a><span data-ttu-id="08981-185">Befehlszeilenschalter</span><span class="sxs-lookup"><span data-stu-id="08981-185">Command-line switches</span></span>

> <span data-ttu-id="08981-186">In PowerShell 3.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="08981-186">Added in PowerShell 3.0</span></span>

<span data-ttu-id="08981-187">Wenn Sie die Windows PowerShell ISE über die Befehlszeile starten (indem Sie **powershell_ise.exe** eingeben), können Sie die folgenden neuen Befehlszeilenschalter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="08981-187">If you start Windows PowerShell ISE from the command line (by typing **powershell_ise.exe** ), you can add the following new command-line switches.</span></span>

- <span data-ttu-id="08981-188">`-NoProfile`: Startet die Windows PowerShell ISE ohne Ausführung von `$profile`</span><span class="sxs-lookup"><span data-stu-id="08981-188">`-NoProfile`: Starts Windows PowerShell ISE without running `$profile`</span></span>
- <span data-ttu-id="08981-189">`-Help`: Zeigt ein Hilfefenster an.</span><span class="sxs-lookup"><span data-stu-id="08981-189">`-Help`: Displays a Help window</span></span>
- <span data-ttu-id="08981-190">`-mta`: Startet die Windows PowerShell ISE im Multithread-Apartment-Modus</span><span class="sxs-lookup"><span data-stu-id="08981-190">`-mta`: Starts Windows PowerShell ISE in multithreaded apartment mode.</span></span> <span data-ttu-id="08981-191">Der Standardbetriebsmodus der Windows PowerShell ISE ist der Singlethread-Apartment-Modus bzw. `-sta`.</span><span class="sxs-lookup"><span data-stu-id="08981-191">The default operation mode for Windows PowerShell ISE is single-threaded apartment mode, or `-sta`.</span></span>

<span data-ttu-id="08981-192">**Welchen Nutzen bietet diese Änderung?**</span><span class="sxs-lookup"><span data-stu-id="08981-192">**What value does this change add?**</span></span>

<span data-ttu-id="08981-193">Das Hinzufügen dieser Befehlszeilenschalter ermöglicht Ihnen das Steuern der Umgebung, in der die Windows PowerShell ISE ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="08981-193">The addition of these command-line switches allows you to control the environment in which the Windows PowerShell ISE runs.</span></span>

<span data-ttu-id="08981-194">**Worin bestehen die Unterschiede?**</span><span class="sxs-lookup"><span data-stu-id="08981-194">**What works differently?**</span></span>

<span data-ttu-id="08981-195">Die Windows PowerShell ISE 2.0 erkennt diese Befehlszeilenschalter nicht.</span><span class="sxs-lookup"><span data-stu-id="08981-195">Windows PowerShell ISE 2.0 doesn't recognize these command-line switches.</span></span>

## <a name="new-editor-features"></a><span data-ttu-id="08981-196">Neue Features im Editor</span><span class="sxs-lookup"><span data-stu-id="08981-196">New editor features</span></span>

> <span data-ttu-id="08981-197">In PowerShell 3.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="08981-197">Added in PowerShell 3.0</span></span>

<span data-ttu-id="08981-198">Zu den weiteren Windows PowerShell ISE-Bearbeitungsfeatures zählen:</span><span class="sxs-lookup"><span data-stu-id="08981-198">Other Windows PowerShell ISE editing features include:</span></span>

- <span data-ttu-id="08981-199">**XML-Syntaxfarben** : Windows PowerShell ISE versieht die XML-Syntax jetzt ebenso mit Farben wie die Windows PowerShell-Syntax.</span><span class="sxs-lookup"><span data-stu-id="08981-199">**XML syntax coloring** - Windows PowerShell ISE now colors XML syntax in the same way as it colors Windows PowerShell syntax.</span></span>
- <span data-ttu-id="08981-200">**Zugehörige Klammer** : Die Windows PowerShell ISE bietet die Funktion „Zugehörige Klammer (Hervorhebung)“, die wie folgt verwendet werden kann: Wenn Sie z. B. den Befehl **Gehe zu Spiel** bzw. <kbd>STRG</kbd>+<kbd>]</kbd> verwenden, wird die schließende Klammer gefunden, wenn eine öffnende Klammer ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="08981-200">**Brace matching** - Windows PowerShell ISE includes brace matching and highlighting, and can be used in the following ways: (for example, using the **Go to Match** command or <kbd>Ctrl</kbd>+<kbd>]</kbd> locates the closing brace, if you have an opening brace selected).</span></span>
- <span data-ttu-id="08981-201">**Gliederungsansicht** Der Skriptbereich unterstützt Gliederungen, sodass Codeabschnitte durch Klicken auf Plus- bzw. Minuszeichen am linken Rand auf- bzw. zugeklappt werden können.</span><span class="sxs-lookup"><span data-stu-id="08981-201">**Outline view** The Script Pane supports outlining, which allows collapsing or expanding sections of code by clicking plus or minus signs in the left margin.</span></span> <span data-ttu-id="08981-202">Sie können Klammern bzw. die Tags `#region` und `#endregion` verwenden, um den Anfang bzw. das Ende eines zuklappbaren Abschnitts zu markieren.</span><span class="sxs-lookup"><span data-stu-id="08981-202">You can use braces or the `#region` and `#endregion` tags to mark the beginning or end of a collapsible section.</span></span> <span data-ttu-id="08981-203">Drücken Sie zum Auf- bzw. Zuklappen aller Bereiche <kbd>STRG</kbd>+<kbd>M</kbd>.</span><span class="sxs-lookup"><span data-stu-id="08981-203">To expand or collapse all regions, press <kbd>Ctrl</kbd>+<kbd>M</kbd>.</span></span>
- <span data-ttu-id="08981-204">**Textbearbeitung mit Drag & Drop** : Windows PowerShell ISE unterstützt nun die Textbearbeitung mit Drag & Drop.</span><span class="sxs-lookup"><span data-stu-id="08981-204">**Drag and drop text editing** - Windows PowerShell ISE now supports drag and drop text editing.</span></span> <span data-ttu-id="08981-205">Sie können einen beliebigen Textblock auswählen und an eine andere Stelle im Editor oder in der Konsole ziehen, um den Text zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="08981-205">You can select any block of text and drag that text to another location in the editor or the console to move the text.</span></span> <span data-ttu-id="08981-206">Wenn Sie die <kbd>STRG</kbd>-Taste gedrückt halten, während Sie den markierten Text ziehen, wird der Text, sobald Sie die Maustaste loslassen, an den neuen Ort kopiert.</span><span class="sxs-lookup"><span data-stu-id="08981-206">If you hold down the <kbd>Ctrl</kbd> key while you drag the selected text, when you release the mouse button the text is copied to the new location.</span></span> <span data-ttu-id="08981-207">In dieser Version von Windows PowerShell ISE wird beim Ziehen und Ablegen von Dateien auf Windows PowerShell ISE die Datei von Windows PowerShell ISE geöffnet.</span><span class="sxs-lookup"><span data-stu-id="08981-207">In this version of Windows PowerShell ISE, when you drag and drop files onto Windows PowerShell ISE, Windows PowerShell ISE opens the file.</span></span>
- <span data-ttu-id="08981-208">**Anzeige von Analysefehlern** : Analysefehler werden rot unterstrichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08981-208">**Parse error display** - Parse errors are indicated with red underlines.</span></span> <span data-ttu-id="08981-209">Wenn Sie auf einen Fehler zeigen, wird das im Code gefundene Problem als QuickInfo angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08981-209">When you hover over an indicated error, tooltip text displays the problem that was found in the code.</span></span>
- <span data-ttu-id="08981-210">**Zoom** : Der Zoomprozentsatz des Konsoleninhalts kann mit einem Zoomschieberegler (rechts unten im Fenster der Windows PowerShell ISE) oder durch Eingabe des Befehls `$psise.options.Zoom` im Konsolenbereich festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="08981-210">**Zoom** - The zoom percentage of the console's content can be set by using the zoom slider (in the lower right corner of Windows PowerShell ISE window), or by entering the command `$psise.options.Zoom` in the Console Pane.</span></span>
- <span data-ttu-id="08981-211">**Umfassende Funktionen zum Kopieren und Einfügen von Text** : Beim Kopieren in die Zwischenablage in Windows PowerShell ISE bleiben Informationen zur Schriftart, Größe und Farbe der ursprünglichen Auswahl erhalten.</span><span class="sxs-lookup"><span data-stu-id="08981-211">**Rich text copy and paste** - Copying to the clipboard in Windows PowerShell ISE preserves the font, size, and color information of the original selection.</span></span>
- <span data-ttu-id="08981-212">**Blockauswahl** : Sie können einen Textblock auswählen, indem Sie bei gedrückter <kbd>ALT</kbd>-TASTE den Text im Skriptbereich mit der Maus auswählen, oder indem Sie <kbd>ALT</kbd>+<kbd>UMSCHALT</kbd>+<kbd>NACH-OBEN/NACH-UNTEN</kbd> drücken.</span><span class="sxs-lookup"><span data-stu-id="08981-212">**Block selection** - You can select a block of text by holding down the <kbd>ALT</kbd> key while selecting text in the Script Pane with your mouse, or by pressing <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>Arrow</kbd>.</span></span>

<span data-ttu-id="08981-213">**Welchen Nutzen bietet diese Änderung?**</span><span class="sxs-lookup"><span data-stu-id="08981-213">**What value does this change add?**</span></span>

<span data-ttu-id="08981-214">Die zusätzlichen Bearbeitungsfeatures bieten eine konsistentere und leistungsstärkere Bearbeitungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="08981-214">The additional editing features provide a more consistent and powerful editing environment.</span></span>

<span data-ttu-id="08981-215">**Worin bestehen die Unterschiede?**</span><span class="sxs-lookup"><span data-stu-id="08981-215">**What works differently?**</span></span>

<span data-ttu-id="08981-216">In Windows PowerShell ISE 2.0 waren diese Bearbeitungsoptimierungen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="08981-216">These editing enhancements weren't present in Windows PowerShell ISE 2.0.</span></span>

## <a name="new-help-viewer-window"></a><span data-ttu-id="08981-217">Neues Anzeigefenster für Hilfe</span><span class="sxs-lookup"><span data-stu-id="08981-217">New Help viewer window</span></span>

> <span data-ttu-id="08981-218">In PowerShell 3.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="08981-218">Added in PowerShell 3.0</span></span>

<span data-ttu-id="08981-219">Wenn Sie <kbd>F1</kbd> drücken, während sich der Cursor in einem Cmdlet befindet oder Sie einen Teil eines Cmdlets hervorgehoben haben, wird im neuen Anzeigefenster für Hilfe eine kontextbezogene Hilfe zum hervorgehobenen Cmdlet geöffnet.</span><span class="sxs-lookup"><span data-stu-id="08981-219">If you press <kbd>F1</kbd> when your cursor is in a cmdlet, or you have part of a cmdlet highlighted, the new Help viewer opens context-sensitive Help about the highlighted cmdlet.</span></span> <span data-ttu-id="08981-220">Um die **konzeptionelle Hilfe** für Windows PowerShell ISE anzuzeigen, geben Sie im Konsolenbereich `operators` ein, und drücken Sie dann <kbd>F1</kbd>.</span><span class="sxs-lookup"><span data-stu-id="08981-220">To display Windows PowerShell **About** help, type `operators` in the console pane, and then press <kbd>F1</kbd>.</span></span>

<span data-ttu-id="08981-221">Laden Sie die aktuelle Version der Windows PowerShell-Hilfethemen von der Microsoft-Website herunter, bevor Sie dieses Feature verwenden.</span><span class="sxs-lookup"><span data-stu-id="08981-221">Before you use this feature, download the most current version of Windows PowerShell Help topics from the Microsoft website.</span></span> <span data-ttu-id="08981-222">Die einfachste Methode zum Herunterladen der Hilfethemen ist die Ausführung des Cmdlets `Update-Help` im Konsolenbereich, wenn Sie die Windows PowerShell ISE als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="08981-222">The simplest method for downloading the Help topics is to run the `Update-Help` cmdlet in the Console Pane when running Windows PowerShell ISE as administrator.</span></span>

<span data-ttu-id="08981-223">Sie können ändern, wo über die Taste <kbd>F1</kbd> nach Hilfe gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="08981-223">You can alter where the <kbd>F1</kbd> key looks for Help.</span></span> <span data-ttu-id="08981-224">Im Menü **Extras**/**Optionen** können Sie auf der Registerkarte **Allgemeine Einstellungen** unter **Andere Einstellungen** das Kontrollkästchen **Lokale Hilfe anstatt Onlineinhalt verwenden** aktivieren bzw. deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="08981-224">In the **Tools**/**Options** menu, on the **General Settings** tab, under **Other Settings** , you can set or clear the checkbox **Use local help content instead of online content**.</span></span> <span data-ttu-id="08981-225">Wenn aktiviert, sucht der Client die Cmdlet-Hilfe in der heruntergeladenen Hilfe im Ordner „modules“.</span><span class="sxs-lookup"><span data-stu-id="08981-225">When checked, the client looks for the cmdlet Help in the downloaded Help found in the modules folder.</span></span> <span data-ttu-id="08981-226">Wenn das Kontrollkästchen deaktiviert ist, sucht der Client online nach der Hilfe.</span><span class="sxs-lookup"><span data-stu-id="08981-226">If the checkbox is cleared, the client looks for help online.</span></span>

<span data-ttu-id="08981-227">**Welchen Nutzen bietet diese Änderung?**</span><span class="sxs-lookup"><span data-stu-id="08981-227">**What value does this change add?**</span></span>

<span data-ttu-id="08981-228">Durch eine kontextbezogene Hilfe ohne Verlassen des aktuellen Cmdlets oder Skripts machen Sie eine integrierte Lernerfahrung.</span><span class="sxs-lookup"><span data-stu-id="08981-228">Context-sensitive Help without leaving your current cmdlet or script provides an integrated learning experience.</span></span>

<span data-ttu-id="08981-229">**Worin bestehen die Unterschiede?**</span><span class="sxs-lookup"><span data-stu-id="08981-229">**What works differently?**</span></span>

<span data-ttu-id="08981-230">Durch Drücken von <kbd>F1</kbd> in früheren Versionen von Windows PowerShell ISE wurde die Hilfedatei auf dem lokalen Computer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="08981-230">Pressing <kbd>F1</kbd> in previous versions of Windows PowerShell ISE opened the help file on the local computer.</span></span> <span data-ttu-id="08981-231">In Windows PowerShell ISE 3.0 und höher wird ein Fenster geöffnet, das die Hilfe für das Cmdlet enthält, die durchsuchbar und konfigurierbar ist.</span><span class="sxs-lookup"><span data-stu-id="08981-231">In Windows PowerShell ISE 3.0 and later, a window opens that contains the help for the cmdlet that is searchable and configurable.</span></span> <span data-ttu-id="08981-232">Diese Hilfe ist in Windows PowerShell ISE 3.0 neu. Die aktualisierbare Hilfe ist in Windows PowerShell 3.0 neu.</span><span class="sxs-lookup"><span data-stu-id="08981-232">This Help experience is new for Windows PowerShell ISE 3.0, and Updatable Help is new for Windows PowerShell 3.0.</span></span>

## <a name="show-command-cmdlet"></a><span data-ttu-id="08981-233">Cmdlet „Show-Command“</span><span class="sxs-lookup"><span data-stu-id="08981-233">Show-Command cmdlet</span></span>

> <span data-ttu-id="08981-234">In PowerShell 3.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="08981-234">Added in PowerShell 3.0</span></span>

<span data-ttu-id="08981-235">Das Cmdlet `Show-Command` ermöglicht das Erstellen und Ausführen eines Cmdlets oder einer Funktion, indem ein grafisches Formular ausgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="08981-235">The `Show-Command` cmdlet enables you to compose or run a cmdlet or function by filling in a graphical form.</span></span> <span data-ttu-id="08981-236">Das Formular ermöglicht Benutzern das Arbeiten mit Windows PowerShell in einer grafischen Umgebung.</span><span class="sxs-lookup"><span data-stu-id="08981-236">The form lets users work with Windows PowerShell in a graphical environment.</span></span>
<span data-ttu-id="08981-237">Mit `Show-Command` können erfahrene Skriptentwickler schnell eine Windows PowerShell-basierte grafische Benutzeroberfläche (GUI) erstellen.</span><span class="sxs-lookup"><span data-stu-id="08981-237">`Show-Command` also enables advanced scripters to create a quick Windows PowerShell-based GUI.</span></span>

<span data-ttu-id="08981-238">**Welchen Nutzen bietet diese Änderung?**</span><span class="sxs-lookup"><span data-stu-id="08981-238">**What value does this change add?**</span></span>

<span data-ttu-id="08981-239">Durch das Verwenden von `Show-Command` in Ihren Windows PowerShell-Skripts können Sie Ihren Benutzern die grafische Umgebung bereitstellen, mit der sie vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="08981-239">By using `Show-Command` in your Windows PowerShell scripts, you can provide your users with the graphical environment with which they're familiar.</span></span> <span data-ttu-id="08981-240">`Show-Command` hilft darüber hinaus Einsteigern beim Erlernen von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08981-240">`Show-Command` can also help introductory users learn Windows PowerShell.</span></span>

<span data-ttu-id="08981-241">**Worin bestehen die Unterschiede?**</span><span class="sxs-lookup"><span data-stu-id="08981-241">**What works differently?**</span></span>

<span data-ttu-id="08981-242">`Show-Command` ist neu in Windows PowerShell ISE 3.0.</span><span class="sxs-lookup"><span data-stu-id="08981-242">`Show-Command` is new Windows PowerShell ISE 3.0.</span></span>

## <a name="see-also"></a><span data-ttu-id="08981-243">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08981-243">See also</span></span>

<span data-ttu-id="08981-244">Weitere Informationen über die Verwendung von Windows PowerShell ISE finden Sie unter [Kennenlernen der Windows PowerShell ISE](../ise/exploring-the-windows-powershell-ise.md).</span><span class="sxs-lookup"><span data-stu-id="08981-244">For more information about using Windows PowerShell ISE, see [Exploring the Windows PowerShell Integrated Scripting Environment](../ise/exploring-the-windows-powershell-ise.md).</span></span>
