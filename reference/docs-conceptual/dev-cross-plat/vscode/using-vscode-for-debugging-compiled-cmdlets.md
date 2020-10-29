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
# <a name="using-visual-studio-code-to-debug-compiled-cmdlets"></a>Verwenden von Visual Studio Code zum Debuggen kompilierter Cmdlets

In diesem Leitfaden wird gezeigt, wie Sie den C#-Quellcode für ein kompiliertes PowerShell-Modul mithilfe von Visual Studio Code (VS Code) und der C#-Erweiterung interaktiv debuggen.

Eine gewisse Vertrautheit mit dem Visual Studio Code-Debugger wird vorausgesetzt.

- Eine allgemeine Einführung in den VS Code-Debugger finden Sie unter [Debuggen in Visual Studio Code][].

- Beispiele zum Debuggen von PowerShell-Skriptdateien und -Modulen finden Sie unter [Verwenden von Visual Studio Code für Remotebearbeitung und Remotedebuggen][].

Dieser Leitfaden setzt voraus, dass Sie die Anweisungen im Leitfaden [Schreiben von portablen Modulen][] gelesen und befolgt haben.

## <a name="creating-a-build-task"></a>Erstellen eines Buildtasks

Erstellen Sie Ihr Projekt automatisch, bevor Sie eine Debugsitzung starten. Durch die Neuerstellung ist sichergestellt, dass Sie die neueste Version Ihres Codes debuggen.

Konfigurieren eines Buildtasks:

1. Führen Sie in der **Befehlspalette** den Befehl **Configure Default Build Task** (Standardbuildtask konfigurieren) aus.

   ![Ausführen von „Configure Default Build Task“](media/using-vscode-for-debugging-compiled-cmdlets/configure-default-build-task.png)

1. Wählen Sie im Dialogfeld **Select a task to configure** (Task zum Konfigurieren auswählen) **Create tasks.json file from template** (tasks.json-Datei aus einer Vorlage erstellen) aus.

1. Wählen Sie im Dialogfeld **Select a Task Template** (Taskvorlage auswählen) **.NET Core** aus.

Es wird eine neue `tasks.json`-Datei erstellt, wenn noch keine vorhanden ist.

So testen Sie Ihren Buildtask:

1. Führen Sie in der **Befehlspalette** den Befehl **Run Build Task** (Buildtask ausführen) aus.

1. Wählen Sie im Dialogfeld **Select the build task to run** (Auszuführenden Buildtask auswählen) **build** (Erstellen) aus.

### <a name="information-about-dll-files-being-locked"></a>Informationen zu gesperrten DLL-Dateien

Standardmäßig wird für einen erfolgreichen Build keine Ausgabe im Terminalbereich angezeigt. Wenn Sie eine Ausgabe sehen, die den Text **Project file doesn't exist** (Es ist keine Projektdatei vorhanden), sollten Sie die `tasks.json`-Datei bearbeiten. Fügen Sie den expliziten Pfad zum C#-Projekt in der Form `"${workspaceFolder}/myModule"` ein. In diesem Beispiel ist `myModule` der Name des Projektordners. Dieser Eintrag muss nach dem `build`-Eintrag in der `args`-Liste stehen, wie hier zu sehen:

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

Beim Debuggen wird Ihre Modul-DLL in die PowerShell-Sitzung im VS Code-Terminal importiert. Die DLL wird gesperrt. Die folgende Meldung wird angezeigt, wenn Sie den Buildtask ausführen, ohne die Terminalsitzung zu schließen:

```Output
Could not copy "obj\Debug\netstandard2.0\myModule.dll" to "bin\Debug\netstandard2.0\myModule.dll"`.
```

Terminalsitzungen müssen geschlossen werden, bevor Sie Neuerstellungen durchführen.

## <a name="setting-up-the-debugger"></a>Einrichten des Debuggers

Zum Debuggen des PowerShell-Cmdlets müssen Sie eine benutzerdefinierte Startkonfiguration einrichten. Diese Konfiguration wird für Folgendes verwendet:

- Erstellen Ihres Quellcodes
- Starten von PowerShell mit dem geladenen Modul
- PowerShell im Terminalbereich geöffnet lassen

Wenn Sie Ihr Cmdlet in der Terminalsitzung aufrufen, hält der Debugger an allen Breakpoints an, die Sie in Ihrem Quellcode festgelegt haben.

### <a name="configuring-launchjson-for-powershell-core"></a>Konfigurieren von „launch.json“ für PowerShell Core

1. Installieren Sie die [C# für Visual Studio Code][]-Erweiterung

1. Fügen Sie im Debugbereich eine Debugkonfiguration hinzu

1. Wählen Sie im Dialogfeld `Select environment` `.NET Core` aus

1. Die `launch.json`-Datei wird im Editor geöffnet. Wenn Sie der Cursor im `configurations`-Array befindet, sehen Sie die `configuration`-Auswahl. Wenn diese Liste nicht angezeigt wird, wählen Sie **Add Configuration** (Konfiguration hinzufügen) aus.

1. Zum Erstellen einer Debug-Standardkonfiguration wählen Sie **Launch .NET Core Console App** (.NET Core-Konsolenanwendung starten) aus:

   ![Starten der .NET Core-Konsolenanwendung](media/using-vscode-for-debugging-compiled-cmdlets/add-configuration-dialog.png)

1. Bearbeiten Sie die Felder `name`, `program`, `args` und `console` wie hier gezeigt:

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

Das Feld `program` wird zum Starten von `pwsh` verwendet, damit das aktuell debuggte Cmdlet ausgeführt werden kann. Das `-NoExit`-Argument verhindert, dass die PowerShell-Sitzung beendet wird, sobald das Modul importiert wird.
Der Pfad im `Import-Module`-Argument ist der Build-Standardausgabepfad, wenn Sie den Leitfaden [Schreiben von portablen Modulen][] befolgt haben. Wenn Sie ein Modulmanifest (`.psd1`-Datei) erstellt haben, sollten Sie stattdessen den Pfad zu diesem angeben. Das Pfadtrennzeichen `/` funktioniert unter Windows, Linux und macOS. Sie müssen das integrierte Terminal zum Ausführen der PowerShell-Befehle verwenden, die Sie debuggen möchten.

> [!NOTE]
> Wenn der Debugger an keinen Haltepunkten hält, suchen Sie in der Debugging-Konsole von Visual Studio Code nach einer Zeile, die lautet:
>
> ```
> Loaded '/path/to/myModule.dll'. Skipped loading symbols. Module is optimized and the debugger option 'Just My Code' is enabled.
> ```
>
> Wenn Sie diese Zeile sehen, fügen Sie `"justMyCode": false` zu Ihrer Startkonfiguration hinzu (auf der gleichen Ebene wie `"console": "integratedTerminal"`.

### <a name="configuring-launchjson-for-windows-powershell"></a>Konfigurieren von launch.json für Windows PowerShell

Diese Startkonfiguration funktioniert zum Testen Ihrer Cmdlets in Windows PowerShell (`powershell.exe`).
Erstellen Sie eine zweite Startkonfiguration mit den folgenden Änderungen:

1. `name` sollte `PowerShell cmdlets: powershell` entsprechen

1. `type` sollte `clr` entsprechen

1. `program` sollte `powershell` entsprechen

   Diese sollte wie folgt aussehen:

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

## <a name="launching-a-debugging-session"></a>Starten einer Debugsitzung

Jetzt ist alles bereit, um mit dem Debuggen zu beginnen.

- Platzieren Sie im Quellcode einen Haltepunkt für das Cmdlet, das Sie debuggen möchten:

  ![Ein Haltepunkt wird als roter Punkt am Seitenrand angezeigt](media/using-vscode-for-debugging-compiled-cmdlets/set-breakpoint.png)

- Achten Sie darauf, dass die relevante Konfiguration für **PowerShell-Cmdlets** im Konfigurations-Dropdownmenü in der **Debug** -Ansicht ausgewählt ist:

  ![Auswählen der Startkonfiguration](media/using-vscode-for-debugging-compiled-cmdlets/select-launch-configuration.png)

- Drücken Sie <kbd>F5</kbd>, oder klicken Sie auf die Schaltfläche **Debuggen starten** .

- Wechseln Sie zum Terminalbereich, und rufen Sie das Cmdlet auf:

  ![Aufrufen des Cmdlets](media/using-vscode-for-debugging-compiled-cmdlets/invoke-the-cmdlet.png)

- Die Ausführung wird am Haltepunkt angehalten:

  ![Die Ausführung hält am Haltepunkt an](media/using-vscode-for-debugging-compiled-cmdlets/stopped-at-breakpoint.png)

Sie können den Quellcode schrittweise durchlaufen, Variablen überprüfen und die Aufrufliste untersuchen.

Wenn Sie das Debuggen beenden möchten, klicken Sie in der Symbolleiste „Debuggen“ auf **Stop** , oder drücken Sie <kbd>UMSCHALT</kbd>-<kbd>F5</kbd>. Die für das Debuggen verwendete Shell wird beendet und gibt die Sperre für die kompilierte DLL-Datei frei.

<!-- reference links -->
[Debuggen in Visual Studio Code]: https://code.visualstudio.com/docs/editor/debugging
[Verwenden von Visual Studio Code für Remotebearbeitung und Remotedebuggen]: using-vscode-for-remote-editing-and-debugging.md
[Schreiben von portablen Modulen]: ../writing-portable-modules.md
[C# für Visual Studio Code]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
