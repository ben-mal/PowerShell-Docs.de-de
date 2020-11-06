---
ms.date: 06/12/2017
keywords: wmf,powershell,setup
title: Verbesserungen beim Debuggen von PowerShell-Skripts
description: WMF 5.0 fügt Windows PowerShell neue Features für das Debuggen hinzu.
ms.openlocfilehash: 5703343e1b85024931638e8b04a09f7208ea123c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646723"
---
# <a name="improvements-in-powershell-script-debugging"></a><span data-ttu-id="2a173-104">Verbesserungen beim Debuggen von PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="2a173-104">Improvements in PowerShell Script Debugging</span></span>

<span data-ttu-id="2a173-105">PowerShell 5.0 enthält mehrere Verbesserungen, die die Debugerfahrung erweitern.</span><span class="sxs-lookup"><span data-stu-id="2a173-105">PowerShell 5.0 includes several improvements that enhance the debugging experience.</span></span>

## <a name="break-all"></a><span data-ttu-id="2a173-106">Alle unterbrechen</span><span class="sxs-lookup"><span data-stu-id="2a173-106">Break All</span></span>

<span data-ttu-id="2a173-107">Die PowerShell-Konsole und PowerShell ISE ermöglichen Ihnen nun bei der Ausführung von Skripts, den Debugger zu unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="2a173-107">The PowerShell console and PowerShell ISE now allow you to break into the debugger for running scripts.</span></span> <span data-ttu-id="2a173-108">Dies funktioniert in lokalen und Remotesitzungen.</span><span class="sxs-lookup"><span data-stu-id="2a173-108">This works in both local and remote sessions.</span></span>

<span data-ttu-id="2a173-109">Drücken Sie in der Konsole <kbd>STRG</kbd>+<kbd>UNTBR</kbd>.</span><span class="sxs-lookup"><span data-stu-id="2a173-109">In the console, press <kbd>Ctrl</kbd>+<kbd>Break</kbd>.</span></span>

<span data-ttu-id="2a173-110">Drücken Sie in der ISE <kbd>STRG</kbd>+<kbd>B</kbd>, oder verwenden Sie den Menübefehl **Debuggen -> Alle unterbrechen**.</span><span class="sxs-lookup"><span data-stu-id="2a173-110">In ISE, press <kbd>Ctrl</kbd>+<kbd>B</kbd>, or use the **Debug -> Break All** menu command.</span></span>

## <a name="remote-debugging-and-remote-file-editing-in-powershell-ise"></a><span data-ttu-id="2a173-111">Remotedebuggen und Remotedateibearbeitung in der PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="2a173-111">Remote debugging and remote file editing in PowerShell ISE</span></span>

<span data-ttu-id="2a173-112">Die PowerShell ISE ermöglicht nun das Öffnen und Bearbeiten von Dateien in einer Remotesitzung, indem der Befehl „PSEdit“ ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2a173-112">PowerShell ISE now lets you open and edit files in a remote session by running the PSEdit command.</span></span>
<span data-ttu-id="2a173-113">Sie können z. B. eine Datei zur Bearbeitung in der Befehlszeile in einer Remotesitzung wie folgt öffnen:</span><span class="sxs-lookup"><span data-stu-id="2a173-113">For example, you can open a file for editing from the command line in a remote session as follows:</span></span>

```powershell
[RemoteComputer1]: PS C:\> PSEdit C:\DebugDemoScripts\Test-GetMutex.ps1
```

<span data-ttu-id="2a173-114">Darüber hinaus können Sie nun Bearbeitungen vornehmen und Änderungen in einer Remotedatei speichern, die in PowerShell ISE automatisch geöffnet wird, wenn ein Haltepunkt erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="2a173-114">In addition, you can now edit and save changes in a remote file that is automatically opened in PowerShell ISE when you hit a breakpoint.</span></span> <span data-ttu-id="2a173-115">Sie können nun eine Skriptdatei debuggen, die auf einem Remotecomputer ausgeführt wird, die Datei bearbeiten, um einen Fehler zu beheben, und dann das geänderte Skript erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="2a173-115">Now, you can debug a script file that is running on a remote computer, edit the file to fix an error, and then rerun the modified script.</span></span>

## <a name="advanced-script-debugging"></a><span data-ttu-id="2a173-116">Erweitertes Skriptdebugging</span><span class="sxs-lookup"><span data-stu-id="2a173-116">Advanced Script Debugging</span></span>

<span data-ttu-id="2a173-117">Es gibt neue, erweiterte Debugfunktionen, die an beliebige lokale Computerprozesse angefügt werden können, für die PowerShell geladen ist, und beliebige Runspaces im jeweiligen Prozess debuggen.</span><span class="sxs-lookup"><span data-stu-id="2a173-117">There are new, advanced debugging features that let you attach to any local computer process that has loaded PowerShell, and debug arbitrary runspaces in that process.</span></span>

### <a name="runspace-debugging"></a><span data-ttu-id="2a173-118">Debuggen von Runspaces</span><span class="sxs-lookup"><span data-stu-id="2a173-118">Runspace Debugging</span></span>

<span data-ttu-id="2a173-119">Neue Cmdlets wurden hinzugefügt, mit denen Sie aktuelle Runspaces in einem Prozess auflisten und die PowerShell-Konsole oder PowerShell ISE-Debugger an den jeweiligen Runspace zum Debuggen von Skripts anfügen können:</span><span class="sxs-lookup"><span data-stu-id="2a173-119">New cmdlets have been added that let you list current runspaces in a process, and attach the PowerShell console or PowerShell ISE debugger to that runspace for script debugging:</span></span>

- <span data-ttu-id="2a173-120">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="2a173-120">Get-Runspace</span></span>
- <span data-ttu-id="2a173-121">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="2a173-121">Debug-Runspace</span></span>
- <span data-ttu-id="2a173-122">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="2a173-122">Enable-RunspaceDebug</span></span>
- <span data-ttu-id="2a173-123">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="2a173-123">Disable-RunspaceDebug</span></span>
- <span data-ttu-id="2a173-124">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="2a173-124">Get-RunspaceDebug</span></span>

### <a name="attach-to-process-hosting-powershell"></a><span data-ttu-id="2a173-125">Anfügen an den Prozess, der PowerShell hostet</span><span class="sxs-lookup"><span data-stu-id="2a173-125">Attach to Process hosting PowerShell</span></span>

<span data-ttu-id="2a173-126">Nun ist ein Anfügen an jeden Computerprozess möglich, für den PowerShell geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="2a173-126">You can now attach to any computer process that has PowerShell loaded.</span></span> <span data-ttu-id="2a173-127">Hierzu starten Sie eine interaktive Sitzung mit dem Hostprozess.</span><span class="sxs-lookup"><span data-stu-id="2a173-127">You do this by entering into an interactive session with the host process.</span></span> <span data-ttu-id="2a173-128">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="2a173-128">For more information, see:</span></span>

- [<span data-ttu-id="2a173-129">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="2a173-129">Enter-PSHostProcess</span></span>](/powershell/module/Microsoft.PowerShell.Core/Enter-PSHostProcess)
- [<span data-ttu-id="2a173-130">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="2a173-130">Exit-PSHostProcess</span></span>](/powershell/module/Microsoft.PowerShell.Core/Exit-PSHostProcess)
