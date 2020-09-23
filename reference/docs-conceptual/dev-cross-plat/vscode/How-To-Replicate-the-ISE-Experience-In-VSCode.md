---
title: Replizieren der ISE-Benutzeroberfläche in Visual Studio Code
description: Replizieren der ISE-Benutzeroberfläche in Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: 6b0b8ce054695d6cc0fc578290c554e2dc1472bc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784621"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a><span data-ttu-id="bb79b-103">Replizieren der ISE-Benutzeroberfläche in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="bb79b-103">How to replicate the ISE experience in Visual Studio Code</span></span>

<span data-ttu-id="bb79b-104">Obwohl die PowerShell-Erweiterung für VS Code keine vollständige Funktionsparität mit der PowerShell ISE anstrebt, gibt es Funktionen, die die VS Code-Benutzeroberfläche für Benutzer der ISE natürlicher gestalten.</span><span class="sxs-lookup"><span data-stu-id="bb79b-104">While the PowerShell extension for VS Code doesn't seek complete feature parity with the PowerShell ISE, there are features in place to make the VS Code experience more natural for users of the ISE.</span></span>

<span data-ttu-id="bb79b-105">In diesem Dokument sind Einstellungen aufgeführt, die Sie in VS Code konfigurieren können, um die Benutzerfreundlichkeit im Vergleich zur ISE etwas vertrauter zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="bb79b-105">This document tries to list settings you can configure in VS Code to make the user experience a bit more familiar compared to the ISE.</span></span>

## <a name="ise-mode"></a><span data-ttu-id="bb79b-106">ISE-Modus</span><span class="sxs-lookup"><span data-stu-id="bb79b-106">ISE Mode</span></span>

> [!NOTE]
> <span data-ttu-id="bb79b-107">Dieses Feature ist in der PowerShell Preview-Erweiterung seit Version 2019.12.0 und in der PowerShell-Erweiterung seit Version 2020.3.0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bb79b-107">This feature is available in the PowerShell Preview extension since version 2019.12.0 and in the PowerShell extension since version 2020.3.0.</span></span>

<span data-ttu-id="bb79b-108">Die einfachste Möglichkeit zum Replizieren der ISE-Benutzeroberfläche in Visual Studio Code ist das Aktivieren des ISE-Modus.</span><span class="sxs-lookup"><span data-stu-id="bb79b-108">The easiest way to replicate the ISE experience in Visual Studio Code is by turning on "ISE Mode".</span></span>
<span data-ttu-id="bb79b-109">Öffnen Sie hierzu die Befehlspalette (<kbd>F1</kbd> oder <kbd>STRG</kbd>+<kbd>UMSCHALT</kbd>+<kbd>P</kbd> oder <kbd>BEFEHLSTASTE</kbd>+<kbd>UMSCHALT</kbd>+<kbd>P</kbd> unter macOS), und geben Sie „ISE-Modus“ ein.</span><span class="sxs-lookup"><span data-stu-id="bb79b-109">To do this, open the command palette (<kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OR <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS) and type in "ISE Mode".</span></span> <span data-ttu-id="bb79b-110">Wählen Sie in der Liste „PowerShell: ISE-Modus aktivieren“ aus.</span><span class="sxs-lookup"><span data-stu-id="bb79b-110">Select "PowerShell: Enable ISE Mode" from the list.</span></span>

<span data-ttu-id="bb79b-111">Mit diesem Befehl werden die unten beschriebenen Einstellungen automatisch angewendet. Das Ergebnis sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="bb79b-111">This command automatically applies the settings described below The result looks like this:</span></span>

![Visual Studio Code im ISE-Modus](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

## <a name="ise-mode-configuration-settings"></a><span data-ttu-id="bb79b-113">ISE-Modus-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="bb79b-113">ISE Mode configuration settings</span></span>

<span data-ttu-id="bb79b-114">Der ISE-Modus nimmt die folgenden Änderungen an den VS Code-Einstellungen vor.</span><span class="sxs-lookup"><span data-stu-id="bb79b-114">ISE Mode makes the following changes to VS Code settings.</span></span>

- <span data-ttu-id="bb79b-115">Schlüsselbindungen</span><span class="sxs-lookup"><span data-stu-id="bb79b-115">Key bindings</span></span>

  |               <span data-ttu-id="bb79b-116">Funktion</span><span class="sxs-lookup"><span data-stu-id="bb79b-116">Function</span></span>                |         <span data-ttu-id="bb79b-117">ISE-Bindung</span><span class="sxs-lookup"><span data-stu-id="bb79b-117">ISE Binding</span></span>          |              <span data-ttu-id="bb79b-118">VS Code-Bindung</span><span class="sxs-lookup"><span data-stu-id="bb79b-118">VS Code Binding</span></span>                |
  | ------------------------------------- | ---------------------------- | ------------------------------------------- |
  | <span data-ttu-id="bb79b-119">Unterbrechen und Pausieren des Debuggers</span><span class="sxs-lookup"><span data-stu-id="bb79b-119">Interrupt and break debugger</span></span>          | <span data-ttu-id="bb79b-120"><kbd>STRG</kbd>+<kbd>B</kbd></span><span class="sxs-lookup"><span data-stu-id="bb79b-120"><kbd>Ctrl</kbd>+<kbd>B</kbd></span></span> | <span data-ttu-id="bb79b-121"><kbd>F6</kbd></span><span class="sxs-lookup"><span data-stu-id="bb79b-121"><kbd>F6</kbd></span></span>                               |
  | <span data-ttu-id="bb79b-122">Ausführen der aktuellen Zeile/des hervorgehobenen Texts</span><span class="sxs-lookup"><span data-stu-id="bb79b-122">Execute current line/highlighted text</span></span> | <span data-ttu-id="bb79b-123"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="bb79b-123"><kbd>F8</kbd></span></span>                | <span data-ttu-id="bb79b-124"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="bb79b-124"><kbd>F8</kbd></span></span>                               |
  | <span data-ttu-id="bb79b-125">Auflisten verfügbarer Codeausschnitte</span><span class="sxs-lookup"><span data-stu-id="bb79b-125">List available snippets</span></span>               | <span data-ttu-id="bb79b-126"><kbd>STRG</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="bb79b-126"><kbd>Ctrl</kbd>+<kbd>J</kbd></span></span> | <span data-ttu-id="bb79b-127"><kbd>STRG</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="bb79b-127"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span></span> |

  > [!NOTE]
  > <span data-ttu-id="bb79b-128">Sie können in VS Code auch [Ihre eigenen Schlüsselbindungen konfigurieren](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings).</span><span class="sxs-lookup"><span data-stu-id="bb79b-128">You can [configure your own key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) in VS Code as well.</span></span>

- <span data-ttu-id="bb79b-129">Vereinfachte, ISE-ähnliche Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="bb79b-129">Simplified ISE-like UI</span></span>

  <span data-ttu-id="bb79b-130">Wenn Sie nach einer Möglichkeit zur Vereinfachung der Visual Studio Code-Benutzeroberfläche suchen, damit diese der ISE-Benutzeroberfläche ähnelt, wenden Sie diese zwei Einstellungen an:</span><span class="sxs-lookup"><span data-stu-id="bb79b-130">If you're looking to simplify the Visual Studio Code UI to look more closely to the UI of the ISE, apply these two settings:</span></span>

  ```json
  "workbench.activityBar.visible": false,
  "debug.openDebug": "neverOpen",
  ```

  <span data-ttu-id="bb79b-131">Durch diese Einstellungen werden die Aktivitätsleiste und die Seitenleiste zum Debuggen innerhalb des unten gezeigten roten Kastens verborgen:</span><span class="sxs-lookup"><span data-stu-id="bb79b-131">These settings hide the "Activity Bar" and the "Debug Side Bar" sections shown inside the red box below:</span></span>

  ![Hervorgehobener Abschnitt mit Aktivitätsleiste und Seitenleiste zum Debuggen](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

  <span data-ttu-id="bb79b-133">Das Endergebnis sieht so aus:</span><span class="sxs-lookup"><span data-stu-id="bb79b-133">The end result looks like this:</span></span>

  ![Vereinfachte Ansicht von VS Code](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

- <span data-ttu-id="bb79b-135">Registerkartenvervollständigung</span><span class="sxs-lookup"><span data-stu-id="bb79b-135">Tab completion</span></span>

  <span data-ttu-id="bb79b-136">Fügen Sie die folgende Einstellung hinzu, um Vervollständigung mit der TAB-TASTE zu erzielen, die der ISE ähnlicher ist:</span><span class="sxs-lookup"><span data-stu-id="bb79b-136">To enable more ISE-like tab completion, add this setting:</span></span>

  ```json
  "editor.tabCompletion": "on",
  ```

- <span data-ttu-id="bb79b-137">Kein Fokus auf der Konsole beim Ausführen</span><span class="sxs-lookup"><span data-stu-id="bb79b-137">No focus on console when executing</span></span>

  <span data-ttu-id="bb79b-138">So bleibt der Fokus bei der Ausführung mit <kbd>F8</kbd> im Editor:</span><span class="sxs-lookup"><span data-stu-id="bb79b-138">To keep the focus in the editor when you execute with <kbd>F8</kbd>:</span></span>

  ```json
  "powershell.integratedConsole.focusConsoleOnExecute": false
  ```

  <span data-ttu-id="bb79b-139">Der Standardwert lautet aus Gründen der Barrierefreiheit `true`.</span><span class="sxs-lookup"><span data-stu-id="bb79b-139">The default is `true` for accessibility purposes.</span></span>

- <span data-ttu-id="bb79b-140">Integrierte Konsole beim Start nicht starten</span><span class="sxs-lookup"><span data-stu-id="bb79b-140">Don't start integrated console on startup</span></span>

  <span data-ttu-id="bb79b-141">Legen Sie Folgendes fest, um die integrierte Konsole beim Start zu beenden:</span><span class="sxs-lookup"><span data-stu-id="bb79b-141">To stop the integrated console on startup, set:</span></span>

  ```json
  "powershell.integratedConsole.showOnStartup": false
  ```

  > [!NOTE]
  > <span data-ttu-id="bb79b-142">Der PowerShell-Hintergrundprozess stellt dennoch IntelliSense, Skriptanalyse, Symbolnavigation usw. bereit. Die Konsole wird jedoch nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb79b-142">The background PowerShell process still starts to provide IntelliSense, script analysis, symbol navigation, etc., but the console won't be shown.</span></span>

- <span data-ttu-id="bb79b-143">Standardmäßige Annahme, dass es sich um PowerShell-Dateien handelt</span><span class="sxs-lookup"><span data-stu-id="bb79b-143">Assume files are PowerShell by default</span></span>

  <span data-ttu-id="bb79b-144">Um neue/unbenannte Dateien zu erstellen, registrieren Sie sie standardmäßig als PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bb79b-144">To make new/untitled files, register as PowerShell by default:</span></span>

  ```json
  "files.defaultLanguage": "powershell",
  ```

- <span data-ttu-id="bb79b-145">Farbschema</span><span class="sxs-lookup"><span data-stu-id="bb79b-145">Color scheme</span></span>

  <span data-ttu-id="bb79b-146">Für VS Code stehen eine Reihe von ISE-Designs zur Verfügung, damit die Darstellung des Editors deutlich mehr der ISE ähnelt.</span><span class="sxs-lookup"><span data-stu-id="bb79b-146">There are a number of ISE themes available for VS Code to make the editor look much more like the ISE.</span></span>

  <span data-ttu-id="bb79b-147">Geben Sie `theme` in der [Befehlspalette][] ein, um `Preferences: Color Theme` abzurufen, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="bb79b-147">In the [Command Palette][] type `theme` to get `Preferences: Color Theme` and press <kbd>Enter</kbd>.</span></span> <span data-ttu-id="bb79b-148">Wählen Sie in der Dropdownliste `PowerShell ISE` aus.</span><span class="sxs-lookup"><span data-stu-id="bb79b-148">In the drop-down list, select `PowerShell ISE`.</span></span>

  <span data-ttu-id="bb79b-149">Sie können dieses Design in den Einstellungen wie folgt festlegen:</span><span class="sxs-lookup"><span data-stu-id="bb79b-149">You can set this theme in the settings with:</span></span>

  ```json
  "workbench.colorTheme": "PowerShell ISE",
  ```

- <span data-ttu-id="bb79b-150">PowerShell-Befehls-Explorer</span><span class="sxs-lookup"><span data-stu-id="bb79b-150">PowerShell Command Explorer</span></span>

  <span data-ttu-id="bb79b-151">Dank der Arbeit von [@corbob](https://github.com/corbob) weist die PowerShell-Erweiterung Anfänge eines eigenen Befehls-Explorers auf.</span><span class="sxs-lookup"><span data-stu-id="bb79b-151">Thanks to the work of [@corbob](https://github.com/corbob), the PowerShell extension has the beginnings of its own command explorer.</span></span>

  <span data-ttu-id="bb79b-152">Geben Sie `PowerShell Command Explorer` in der [Befehlspalette][] ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="bb79b-152">In the [Command Palette][], enter `PowerShell Command Explorer` and press <kbd>Enter</kbd>.</span></span>

- <span data-ttu-id="bb79b-153">Öffnen in der ISE</span><span class="sxs-lookup"><span data-stu-id="bb79b-153">Open in the ISE</span></span>

  <span data-ttu-id="bb79b-154">Wenn Sie dennoch eine Datei in der Windows PowerShell ISE öffnen möchten, öffnen Sie die [Befehlspalette][], suchen Sie nach „in ISE öffnen“, und wählen Sie **PowerShell: aktuelle Datei in PowerShell ISE öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="bb79b-154">If you want to open a file in the Windows PowerShell ISE anyway, open the [Command Palette][], search for "open in ise", then select **PowerShell: Open Current File in PowerShell ISE**.</span></span>

## <a name="other-resources"></a><span data-ttu-id="bb79b-155">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="bb79b-155">Other resources</span></span>

- <span data-ttu-id="bb79b-156">4sysops bietet [einen großartigen Artikel][4sysops] zur Konfiguration von VS Code, um der ISE ähnlicher zu sein.</span><span class="sxs-lookup"><span data-stu-id="bb79b-156">4sysops has [a great article][4sysops] on configuring VS Code to be more like the ISE.</span></span>
- <span data-ttu-id="bb79b-157">Mike F. Robbins hat [einen hervorragenden Beitrag][mikefrobbins] zum Einrichten von VS Code verfasst.</span><span class="sxs-lookup"><span data-stu-id="bb79b-157">Mike F Robbins has [a great post][mikefrobbins] on setting up VS Code.</span></span>
<!-- - Learn PowerShell has [an excellent write up][learnpwsh] setup for PowerShell. -->

## <a name="vs-code-tips"></a><span data-ttu-id="bb79b-158">Tipps für VS Code</span><span class="sxs-lookup"><span data-stu-id="bb79b-158">VS Code Tips</span></span>

- <span data-ttu-id="bb79b-159">Befehlspalette</span><span class="sxs-lookup"><span data-stu-id="bb79b-159">Command Palette</span></span>

  <span data-ttu-id="bb79b-160">Die Befehlspalette ist ein äußerst nützliches Tool zum Ausführen von Befehlen in VS Code.</span><span class="sxs-lookup"><span data-stu-id="bb79b-160">The Command Palette is handy way of executing commands in VS Code.</span></span> <span data-ttu-id="bb79b-161">Unter macOS öffnen Sie die Befehlspalette über <kbd>F1</kbd> oder <kbd>STRG</kbd>+<kbd>UMSCHALT</kbd>+<kbd>P</kbd> oder <kbd>BEFEHLSTASTE</kbd>+<kbd>UMSCHALT</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="bb79b-161">Open the command palette using <kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OR <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS.</span></span>

  <span data-ttu-id="bb79b-162">Weitere Informationen finden Sie in der [Dokumentation zu VS Code][vsc-docs].</span><span class="sxs-lookup"><span data-stu-id="bb79b-162">For more information, see [the VS Code documentation][vsc-docs].</span></span>

- <span data-ttu-id="bb79b-163">Deaktivieren der Debugging-Konsole</span><span class="sxs-lookup"><span data-stu-id="bb79b-163">Disable the Debug Console</span></span>

  <span data-ttu-id="bb79b-164">Wenn Sie VS Code für die PowerShell-Skripterstellung verwenden möchten, können Sie die **Debugging-Konsole** deaktivieren (sie wird nicht von der PowerShell-Erweiterung verwendet).</span><span class="sxs-lookup"><span data-stu-id="bb79b-164">If you only plan on using VS Code for PowerShell scripting, you can hide the **Debug Console** since it is not used by the PowerShell extension.</span></span> <span data-ttu-id="bb79b-165">Klicken Sie dazu mit der rechten Maustaste auf **Debugging-Konsole**, und klicken Sie dann auf das Häkchen zum Ausblenden der Konsole.</span><span class="sxs-lookup"><span data-stu-id="bb79b-165">To do so, right click on **Debug Console** then click on the check mark to hide it.</span></span>

## <a name="more-settings"></a><span data-ttu-id="bb79b-166">Weitere Einstellungen</span><span class="sxs-lookup"><span data-stu-id="bb79b-166">More settings</span></span>

<span data-ttu-id="bb79b-167">Wenn Sie weitere Möglichkeiten kennen, wie Sie VS Code für ISE-Benutzer vertrauter gestalten können, tragen Sie zu diesem Dokument bei. Wenn Sie nach einer Kompatibilitätskonfiguration suchen, aber keine Möglichkeit finden, diese zu aktivieren, [legen Sie ein Issue an][], und fragen Sie nach einer Lösung!</span><span class="sxs-lookup"><span data-stu-id="bb79b-167">If you know of more ways to make VS Code feel more familiar for ISE users, contribute to this doc. If there's a compatibility configuration you're looking for, but you can't find any way to enable it, [open an issue][] and ask away!</span></span>

<span data-ttu-id="bb79b-168">Wir freuen uns immer über PRs und Beiträge!</span><span class="sxs-lookup"><span data-stu-id="bb79b-168">We're always happy to accept PRs and contributions as well!</span></span>

<!-- link references -->
[vsc-docs]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette
[Befehlspalette]: #vs-code-tips
[Command Palette]: #vs-code-tips
[Problem erstellen]: https://github.com/PowerShell/VSCode-powershell/issues/new/choose
[open an issue]: https://github.com/PowerShell/VSCode-powershell/issues/new/choose

[4sysops]: https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/
[mikefrobbins]: https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/
[learnpwsh]: https://www.learnpwsh.com/setup-vs-code-for-powershell/
