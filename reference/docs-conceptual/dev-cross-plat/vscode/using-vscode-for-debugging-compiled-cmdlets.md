---
ms.date: 10/19/2020
keywords: powershell,cmdlet,debuggen
title: Verwenden von Visual Studio Code zum Debuggen kompilierter Cmdlets
description: Festlegen einer Buildtask- und Startkonfiguration für ein PSModule-Projekt in .NET Core
ms.openlocfilehash: b51a69110c64b386f5c3ccf2527d1e184ef89257
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501642"
---
# <a name="using-visual-studio-code-to-debug-compiled-cmdlets"></a><span data-ttu-id="98c54-104">Verwenden von Visual Studio Code zum Debuggen kompilierter Cmdlets</span><span class="sxs-lookup"><span data-stu-id="98c54-104">Using Visual Studio Code to debug compiled cmdlets</span></span>

<span data-ttu-id="98c54-105">In diesem Leitfaden wird gezeigt, wie Sie den C#-Quellcode für ein kompiliertes PowerShell-Modul mithilfe von Visual Studio Code (VS Code) und der C#-Erweiterung interaktiv debuggen.</span><span class="sxs-lookup"><span data-stu-id="98c54-105">This guide shows you how to interactively debug C# source code for a compiled PowerShell module using Visual Studio Code (VS Code) and the C# extension.</span></span>

<span data-ttu-id="98c54-106">Eine gewisse Vertrautheit mit dem Visual Studio Code-Debugger wird vorausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="98c54-106">Some familiarity with the Visual Studio Code debugger is assumed.</span></span>

- <span data-ttu-id="98c54-107">Eine allgemeine Einführung in den VS Code-Debugger finden Sie unter [Debuggen in Visual Studio Code][].</span><span class="sxs-lookup"><span data-stu-id="98c54-107">For a general introduction to the VS Code debugger, see [Debugging in Visual Studio Code][].</span></span>

- <span data-ttu-id="98c54-108">Beispiele zum Debuggen von PowerShell-Skriptdateien und -Modulen finden Sie unter [Verwenden von Visual Studio Code für Remotebearbeitung und Remotedebuggen][].</span><span class="sxs-lookup"><span data-stu-id="98c54-108">For examples of debugging PowerShell script files and modules, see [Using Visual Studio Code for remote editing and debugging][].</span></span>

<span data-ttu-id="98c54-109">Dieser Leitfaden setzt voraus, dass Sie die Anweisungen im Leitfaden [Schreiben von portablen Modulen][] gelesen und befolgt haben.</span><span class="sxs-lookup"><span data-stu-id="98c54-109">This guide assumes you have read and followed the instructions in the [Writing Portable Modules][] guide.</span></span>

## <a name="creating-a-build-task"></a><span data-ttu-id="98c54-110">Erstellen eines Buildtasks</span><span class="sxs-lookup"><span data-stu-id="98c54-110">Creating a build task</span></span>

<span data-ttu-id="98c54-111">Erstellen Sie Ihr Projekt automatisch, bevor Sie eine Debugsitzung starten.</span><span class="sxs-lookup"><span data-stu-id="98c54-111">Build your project automatically before launching a debugging session.</span></span> <span data-ttu-id="98c54-112">Durch die Neuerstellung ist sichergestellt, dass Sie die neueste Version Ihres Codes debuggen.</span><span class="sxs-lookup"><span data-stu-id="98c54-112">Rebuilding ensures that you debug the latest version of your code.</span></span>

<span data-ttu-id="98c54-113">Konfigurieren eines Buildtasks:</span><span class="sxs-lookup"><span data-stu-id="98c54-113">Configure a build task:</span></span>

1. <span data-ttu-id="98c54-114">Führen Sie in der **Befehlspalette** den Befehl **Configure Default Build Task** (Standardbuildtask konfigurieren) aus.</span><span class="sxs-lookup"><span data-stu-id="98c54-114">In the **Command Palette** , run the **Configure Default Build Task** command.</span></span>

   ![Ausführen von „Configure Default Build Task“](media/using-vscode-for-debugging-compiled-cmdlets/configure-default-build-task.png)

1. <span data-ttu-id="98c54-116">Wählen Sie im Dialogfeld **Select a task to configure** (Task zum Konfigurieren auswählen) **Create tasks.json file from template** (tasks.json-Datei aus einer Vorlage erstellen) aus.</span><span class="sxs-lookup"><span data-stu-id="98c54-116">In the **Select a task to configure** dialog, choose **Create tasks.json file from template** .</span></span>

1. <span data-ttu-id="98c54-117">Wählen Sie im Dialogfeld **Select a Task Template** (Taskvorlage auswählen) **.NET Core** aus.</span><span class="sxs-lookup"><span data-stu-id="98c54-117">In the **Select a Task Template** dialog, choose **.NET Core** .</span></span>

<span data-ttu-id="98c54-118">Es wird eine neue `tasks.json`-Datei erstellt, wenn noch keine vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="98c54-118">A new `tasks.json` file is created if one doesn't exist yet.</span></span>

<span data-ttu-id="98c54-119">So testen Sie Ihren Buildtask:</span><span class="sxs-lookup"><span data-stu-id="98c54-119">To test your build task:</span></span>

1. <span data-ttu-id="98c54-120">Führen Sie in der **Befehlspalette** den Befehl **Run Build Task** (Buildtask ausführen) aus.</span><span class="sxs-lookup"><span data-stu-id="98c54-120">In the **Command Palette** , run the **Run Build Task** command.</span></span>

1. <span data-ttu-id="98c54-121">Wählen Sie im Dialogfeld **Select the build task to run** (Auszuführenden Buildtask auswählen) **build** (Erstellen) aus.</span><span class="sxs-lookup"><span data-stu-id="98c54-121">In the **Select the build task to run** dialog, choose **build** .</span></span>

### <a name="information-about-dll-files-being-locked"></a><span data-ttu-id="98c54-122">Informationen zu gesperrten DLL-Dateien</span><span class="sxs-lookup"><span data-stu-id="98c54-122">Information about DLL files being locked</span></span>

<span data-ttu-id="98c54-123">Standardmäßig wird für einen erfolgreichen Build keine Ausgabe im Terminalbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98c54-123">By default, a successful build doesn't show output in the terminal pane.</span></span> <span data-ttu-id="98c54-124">Wenn Sie eine Ausgabe sehen, die den Text **Project file doesn't exist** (Es ist keine Projektdatei vorhanden), sollten Sie die `tasks.json`-Datei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="98c54-124">If you see output that contains the text **Project file doesn't exist** , you should edit the `tasks.json` file.</span></span> <span data-ttu-id="98c54-125">Fügen Sie den expliziten Pfad zum C#-Projekt in der Form `"${workspaceFolder}/myModule"` ein.</span><span class="sxs-lookup"><span data-stu-id="98c54-125">Include the explicit path to the C# project expressed as `"${workspaceFolder}/myModule"`.</span></span> <span data-ttu-id="98c54-126">In diesem Beispiel ist `myModule` der Name des Projektordners.</span><span class="sxs-lookup"><span data-stu-id="98c54-126">In this example, `myModule` is the name of the project folder.</span></span> <span data-ttu-id="98c54-127">Dieser Eintrag muss nach dem `build`-Eintrag in der `args`-Liste stehen, wie hier zu sehen:</span><span class="sxs-lookup"><span data-stu-id="98c54-127">This entry must go after the `build` entry in the `args` list as follows:</span></span>

```json
    {
        "label": "build",
        "command": "dotnet",
        "type": "shell",
        "args": [
            "build",
            "${workspaceFolder}/myModule",
            // Ask dotnet build to generate full paths for file names.
            "/property:GenerateFullPaths=true",
            // Do not generate summary otherwise it leads to duplicate errors in Problems panel
            "/consoleloggerparameters:NoSummary",
        ],
        "group": "build",
        "presentation": {
            "reveal": "silent"
        },
        "problemMatcher": "$msCompile"
    }
```

<span data-ttu-id="98c54-128">Beim Debuggen wird Ihre Modul-DLL in die PowerShell-Sitzung im VS Code-Terminal importiert.</span><span class="sxs-lookup"><span data-stu-id="98c54-128">When debugging, your module DLL is imported into the PowerShell session in the VS Code terminal.</span></span> <span data-ttu-id="98c54-129">Die DLL wird gesperrt.</span><span class="sxs-lookup"><span data-stu-id="98c54-129">The DLL becomes locked.</span></span> <span data-ttu-id="98c54-130">Die folgende Meldung wird angezeigt, wenn Sie den Buildtask ausführen, ohne die Terminalsitzung zu schließen:</span><span class="sxs-lookup"><span data-stu-id="98c54-130">The following message is displayed when you run the build task without closing the terminal session:</span></span>

```Output
Could not copy "obj\Debug\netstandard2.0\myModule.dll" to "bin\Debug\netstandard2.0\myModule.dll"`.
```

<span data-ttu-id="98c54-131">Terminalsitzungen müssen geschlossen werden, bevor Sie Neuerstellungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="98c54-131">Terminal sessions must be closed before you rebuild.</span></span>

## <a name="setting-up-the-debugger"></a><span data-ttu-id="98c54-132">Einrichten des Debuggers</span><span class="sxs-lookup"><span data-stu-id="98c54-132">Setting up the debugger</span></span>

<span data-ttu-id="98c54-133">Zum Debuggen des PowerShell-Cmdlets müssen Sie eine benutzerdefinierte Startkonfiguration einrichten.</span><span class="sxs-lookup"><span data-stu-id="98c54-133">To debug the PowerShell cmdlet, you need to set up a custom launch configuration.</span></span> <span data-ttu-id="98c54-134">Diese Konfiguration wird für Folgendes verwendet:</span><span class="sxs-lookup"><span data-stu-id="98c54-134">This configuration is used to:</span></span>

- <span data-ttu-id="98c54-135">Erstellen Ihres Quellcodes</span><span class="sxs-lookup"><span data-stu-id="98c54-135">Build your source code</span></span>
- <span data-ttu-id="98c54-136">Starten von PowerShell mit dem geladenen Modul</span><span class="sxs-lookup"><span data-stu-id="98c54-136">Start PowerShell with your module loaded</span></span>
- <span data-ttu-id="98c54-137">PowerShell im Terminalbereich geöffnet lassen</span><span class="sxs-lookup"><span data-stu-id="98c54-137">Leave PowerShell open in the terminal pane</span></span>

<span data-ttu-id="98c54-138">Wenn Sie Ihr Cmdlet in der Terminalsitzung aufrufen, hält der Debugger an allen Breakpoints an, die Sie in Ihrem Quellcode festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="98c54-138">When you invoke your cmdlet in the terminal session, the debugger stops at any breakpoints set in your source code.</span></span>

### <a name="configuring-launchjson-for-powershell-core"></a><span data-ttu-id="98c54-139">Konfigurieren von „launch.json“ für PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="98c54-139">Configuring launch.json for PowerShell Core</span></span>

1. <span data-ttu-id="98c54-140">Installieren Sie die [C# für Visual Studio Code][]-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="98c54-140">Install the [C# for Visual Studio Code][] extension</span></span>

1. <span data-ttu-id="98c54-141">Fügen Sie im Debugbereich eine Debugkonfiguration hinzu</span><span class="sxs-lookup"><span data-stu-id="98c54-141">In the Debug pane, add a debug configuration</span></span>

1. <span data-ttu-id="98c54-142">Wählen Sie im Dialogfeld `Select environment` `.NET Core` aus</span><span class="sxs-lookup"><span data-stu-id="98c54-142">In the `Select environment` dialog, choose `.NET Core`</span></span>

1. <span data-ttu-id="98c54-143">Die `launch.json`-Datei wird im Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="98c54-143">The `launch.json` file is opened in the editor.</span></span> <span data-ttu-id="98c54-144">Wenn Sie der Cursor im `configurations`-Array befindet, sehen Sie die `configuration`-Auswahl.</span><span class="sxs-lookup"><span data-stu-id="98c54-144">With your cursor inside the `configurations` array, you see the `configuration` picker.</span></span> <span data-ttu-id="98c54-145">Wenn diese Liste nicht angezeigt wird, wählen Sie **Add Configuration** (Konfiguration hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="98c54-145">If you don't see this list, select **Add Configuration** .</span></span>

1. <span data-ttu-id="98c54-146">Zum Erstellen einer Debug-Standardkonfiguration wählen Sie **Launch .NET Core Console App** (.NET Core-Konsolenanwendung starten) aus:</span><span class="sxs-lookup"><span data-stu-id="98c54-146">To create a default debug configuration, select **Launch .NET Core Console App** :</span></span>

   ![Starten der .NET Core-Konsolenanwendung](media/using-vscode-for-debugging-compiled-cmdlets/add-configuration-dialog.png)

1. <span data-ttu-id="98c54-148">Bearbeiten Sie die Felder `name`, `program`, `args` und `console` wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="98c54-148">Edit the `name`, `program`, `args`, and `console` fields as follows:</span></span>

   ```json
    {
        "name": "PowerShell cmdlets: pwsh",
        "type": "coreclr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "pwsh",
        "args": [
            "-NoExit",
            "-NoProfile",
            "-Command",
            "Import-Module ${workspaceFolder}/myModule/bin/Debug/netstandard2.0/myModule.dll",
        ],
        "cwd": "${workspaceFolder}",
        "stopAtEntry": false,
        "console": "integratedTerminal"
    }
   ```

<span data-ttu-id="98c54-149">Das Feld `program` wird zum Starten von `pwsh` verwendet, damit das aktuell debuggte Cmdlet ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="98c54-149">The `program` field is used to launch `pwsh` so that the cmdlet being debugged can be run.</span></span> <span data-ttu-id="98c54-150">Das `-NoExit`-Argument verhindert, dass die PowerShell-Sitzung beendet wird, sobald das Modul importiert wird.</span><span class="sxs-lookup"><span data-stu-id="98c54-150">The `-NoExit` argument prevents the PowerShell session from exiting as soon as the module is imported.</span></span>
<span data-ttu-id="98c54-151">Der Pfad im `Import-Module`-Argument ist der Build-Standardausgabepfad, wenn Sie den Leitfaden [Schreiben von portablen Modulen][] befolgt haben.</span><span class="sxs-lookup"><span data-stu-id="98c54-151">The path in the `Import-Module` argument is the default build output path when you've followed the [Writing Portable Modules][] guide.</span></span> <span data-ttu-id="98c54-152">Wenn Sie ein Modulmanifest (`.psd1`-Datei) erstellt haben, sollten Sie stattdessen den Pfad zu diesem angeben.</span><span class="sxs-lookup"><span data-stu-id="98c54-152">If you've created a module manifest (`.psd1` file), you should use the path to that instead.</span></span> <span data-ttu-id="98c54-153">Das Pfadtrennzeichen `/` funktioniert unter Windows, Linux und macOS.</span><span class="sxs-lookup"><span data-stu-id="98c54-153">The `/` path separator works on Windows, Linux, and macOS.</span></span> <span data-ttu-id="98c54-154">Sie müssen das integrierte Terminal zum Ausführen der PowerShell-Befehle verwenden, die Sie debuggen möchten.</span><span class="sxs-lookup"><span data-stu-id="98c54-154">You must use the integrated terminal to run the PowerShell commands you want to debug.</span></span>

> [!NOTE]
> <span data-ttu-id="98c54-155">Wenn der Debugger an keinen Haltepunkten hält, suchen Sie in der Debugging-Konsole von Visual Studio Code nach einer Zeile, die lautet:</span><span class="sxs-lookup"><span data-stu-id="98c54-155">If the debugger doesn't stop at any breakpoints, look in the Visual Studio Code Debug Console for a line that says:</span></span>
>
> ```
> Loaded '/path/to/myModule.dll'. Skipped loading symbols. Module is optimized and the debugger option 'Just My Code' is enabled.
> ```
>
> <span data-ttu-id="98c54-156">Wenn Sie diese Zeile sehen, fügen Sie `"justMyCode": false` zu Ihrer Startkonfiguration hinzu (auf der gleichen Ebene wie `"console": "integratedTerminal"`.</span><span class="sxs-lookup"><span data-stu-id="98c54-156">If you see this, add `"justMyCode": false` to your launch config (at the same level as `"console": "integratedTerminal"`.</span></span>

### <a name="configuring-launchjson-for-windows-powershell"></a><span data-ttu-id="98c54-157">Konfigurieren von launch.json für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="98c54-157">Configuring launch.json for Windows PowerShell</span></span>

<span data-ttu-id="98c54-158">Diese Startkonfiguration funktioniert zum Testen Ihrer Cmdlets in Windows PowerShell (`powershell.exe`).</span><span class="sxs-lookup"><span data-stu-id="98c54-158">This launch configuration works for testing your cmdlets in Windows PowerShell (`powershell.exe`).</span></span>
<span data-ttu-id="98c54-159">Erstellen Sie eine zweite Startkonfiguration mit den folgenden Änderungen:</span><span class="sxs-lookup"><span data-stu-id="98c54-159">Create a second launch configuration with the following changes:</span></span>

1. <span data-ttu-id="98c54-160">`name` sollte `PowerShell cmdlets: powershell` entsprechen</span><span class="sxs-lookup"><span data-stu-id="98c54-160">`name` should be `PowerShell cmdlets: powershell`</span></span>

1. <span data-ttu-id="98c54-161">`type` sollte `clr` entsprechen</span><span class="sxs-lookup"><span data-stu-id="98c54-161">`type` should be `clr`</span></span>

1. <span data-ttu-id="98c54-162">`program` sollte `powershell` entsprechen</span><span class="sxs-lookup"><span data-stu-id="98c54-162">`program` should be `powershell`</span></span>

   <span data-ttu-id="98c54-163">Diese sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="98c54-163">It should look like this:</span></span>

   ```json
    {
        "name": "PowerShell cmdlets: powershell",
        "type": "clr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "powershell",
        "args": [
            "-NoExit",
            "-NoProfile",
            "-Command",
            "Import-Module ${workspaceFolder}/myModule/bin/Debug/netstandard2.0/myModule.dll",
        ],
        "cwd": "${workspaceFolder}",
        "stopAtEntry": false,
        "console": "integratedTerminal"
    }
   ```

## <a name="launching-a-debugging-session"></a><span data-ttu-id="98c54-164">Starten einer Debugsitzung</span><span class="sxs-lookup"><span data-stu-id="98c54-164">Launching a debugging session</span></span>

<span data-ttu-id="98c54-165">Jetzt ist alles bereit, um mit dem Debuggen zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="98c54-165">Now everything is ready to begin debugging.</span></span>

- <span data-ttu-id="98c54-166">Platzieren Sie im Quellcode einen Haltepunkt für das Cmdlet, das Sie debuggen möchten:</span><span class="sxs-lookup"><span data-stu-id="98c54-166">Place a breakpoint in the source code for the cmdlet you want to debug:</span></span>

  ![Ein Haltepunkt wird als roter Punkt am Seitenrand angezeigt](media/using-vscode-for-debugging-compiled-cmdlets/set-breakpoint.png)

- <span data-ttu-id="98c54-168">Achten Sie darauf, dass die relevante Konfiguration für **PowerShell-Cmdlets** im Konfigurations-Dropdownmenü in der **Debug** -Ansicht ausgewählt ist:</span><span class="sxs-lookup"><span data-stu-id="98c54-168">Ensure that the relevant **PowerShell cmdlets** configuration is selected in the configuration drop-down menu in the **Debug** view:</span></span>

  ![Auswählen der Startkonfiguration](media/using-vscode-for-debugging-compiled-cmdlets/select-launch-configuration.png)

- <span data-ttu-id="98c54-170">Drücken Sie <kbd>F5</kbd>, oder klicken Sie auf die Schaltfläche **Debuggen starten** .</span><span class="sxs-lookup"><span data-stu-id="98c54-170">Press <kbd>F5</kbd> or click on the **Start Debugging** button</span></span>

- <span data-ttu-id="98c54-171">Wechseln Sie zum Terminalbereich, und rufen Sie das Cmdlet auf:</span><span class="sxs-lookup"><span data-stu-id="98c54-171">Switch to the terminal pane and invoke your cmdlet:</span></span>

  ![Aufrufen des Cmdlets](media/using-vscode-for-debugging-compiled-cmdlets/invoke-the-cmdlet.png)

- <span data-ttu-id="98c54-173">Die Ausführung wird am Haltepunkt angehalten:</span><span class="sxs-lookup"><span data-stu-id="98c54-173">Execution stops at the breakpoint:</span></span>

  ![Die Ausführung hält am Haltepunkt an](media/using-vscode-for-debugging-compiled-cmdlets/stopped-at-breakpoint.png)

<span data-ttu-id="98c54-175">Sie können den Quellcode schrittweise durchlaufen, Variablen überprüfen und die Aufrufliste untersuchen.</span><span class="sxs-lookup"><span data-stu-id="98c54-175">You can step through the source code, inspect variables, and inspect the call stack.</span></span>

<span data-ttu-id="98c54-176">Wenn Sie das Debuggen beenden möchten, klicken Sie in der Symbolleiste „Debuggen“ auf **Stop** , oder drücken Sie <kbd>UMSCHALT</kbd>-<kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="98c54-176">To end debugging, click **Stop** in the debug toolbar or press <kbd>Shift</kbd>-<kbd>F5</kbd>.</span></span> <span data-ttu-id="98c54-177">Die für das Debuggen verwendete Shell wird beendet und gibt die Sperre für die kompilierte DLL-Datei frei.</span><span class="sxs-lookup"><span data-stu-id="98c54-177">The shell used for debugging exits and releases the lock on the compiled DLL file.</span></span>

<!-- reference links -->
[Debuggen in Visual Studio Code]: https://code.visualstudio.com/docs/editor/debugging
[Debugging in Visual Studio Code]: https://code.visualstudio.com/docs/editor/debugging
[Verwenden von Visual Studio Code für Remotebearbeitung und Remotedebuggen]: using-vscode-for-remote-editing-and-debugging.md
[Using Visual Studio Code for remote editing and debugging]: using-vscode-for-remote-editing-and-debugging.md
[Schreiben von portablen Modulen]: ../writing-portable-modules.md
[Writing Portable Modules]: ../writing-portable-modules.md
[C# für Visual Studio Code]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
[C# for Visual Studio Code]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
