---
description: Beschreibt, wie Befehle im Befehlsverlauf ausgeführt und ausgeführt werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_history?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_History
ms.openlocfilehash: 64a8fac4f25ac60be58aca8549748b9e4dde6c3b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223455"
---
# <a name="about-history"></a><span data-ttu-id="0ee1f-104">Informationen zum Verlauf</span><span class="sxs-lookup"><span data-stu-id="0ee1f-104">About History</span></span>

## <a name="short-description"></a><span data-ttu-id="0ee1f-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ee1f-105">Short Description</span></span>
<span data-ttu-id="0ee1f-106">Beschreibt, wie Befehle im Befehlsverlauf ausgeführt und ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-106">Describes how to get and run commands in the command history.</span></span>

## <a name="long-description"></a><span data-ttu-id="0ee1f-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ee1f-107">Long Description</span></span>

<span data-ttu-id="0ee1f-108">Wenn Sie einen Befehl an der Eingabeaufforderung eingeben, speichert PowerShell den Befehl im Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-108">When you enter a command at the command prompt, PowerShell saves the command in the command history.</span></span> <span data-ttu-id="0ee1f-109">Sie können die Befehle im Verlauf als Datensatz Ihrer Arbeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-109">You can use the commands in the history as a record of your work.</span></span> <span data-ttu-id="0ee1f-110">Sie können die Befehle auch abrufen und aus dem Befehlsverlauf ausführen.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-110">And, you can recall and run the commands from the command history.</span></span>

<span data-ttu-id="0ee1f-111">PowerShell verfügt über zwei verschiedene Verlaufs Anbieter: den integrierten Verlauf und den vom **psread Line** -Modul verwalteten Verlauf.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-111">PowerShell has two different history providers: the built-in history and the history managed by the **PSReadLine** module.</span></span> <span data-ttu-id="0ee1f-112">Die Verläufe werden separat verwaltet, aber beide Verläufe sind in Sitzungen verfügbar, in denen **psread Line** geladen wird.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-112">The histories are managed separately, but both histories are available in sessions where **PSReadLine** is loaded.</span></span>

## <a name="using-the-psreadline-history"></a><span data-ttu-id="0ee1f-113">Verwenden des psread Line-Verlaufs</span><span class="sxs-lookup"><span data-stu-id="0ee1f-113">Using the PSReadLine history</span></span>

<span data-ttu-id="0ee1f-114">Der pslelinienverlauf verfolgt die Befehle, die in allen PowerShell-Sitzungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-114">The PSReadLine history tracks the commands used in all PowerShell sessions.</span></span>
<span data-ttu-id="0ee1f-115">Der Verlauf wird pro Host in eine zentrale Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-115">The history is written to a central file per host.</span></span> <span data-ttu-id="0ee1f-116">Diese Verlaufs Datei ist für alle Sitzungen verfügbar und enthält den bisherigen Verlauf.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-116">That history file is available to all sessions and contains all past history.</span></span> <span data-ttu-id="0ee1f-117">Der Verlauf wird nicht gelöscht, wenn die Sitzung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-117">The history is not deleted when the session ends.</span></span> <span data-ttu-id="0ee1f-118">Außerdem kann dieser Verlauf nicht durch die `*-History` Cmdlets verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-118">Also, that history cannot be managed by the `*-History` cmdlets.</span></span> <span data-ttu-id="0ee1f-119">Weitere Informationen finden Sie unter [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="0ee1f-119">For more information, see [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span></span>

## <a name="using-the-built-in-session-history"></a><span data-ttu-id="0ee1f-120">Verwenden des integrierten Sitzungs Verlaufs</span><span class="sxs-lookup"><span data-stu-id="0ee1f-120">Using the built-in session history</span></span>

<span data-ttu-id="0ee1f-121">Der integrierte Verlauf verfolgt nur die Befehle nach, die in der aktuellen Sitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-121">The built-in history only tracks the commands used in the current session.</span></span> <span data-ttu-id="0ee1f-122">Der Verlauf ist für andere Sitzungen nicht verfügbar und wird gelöscht, wenn die Sitzung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-122">The history is not available to other sessions and is deleted when the session ends.</span></span>

### <a name="history-cmdlets"></a><span data-ttu-id="0ee1f-123">History-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0ee1f-123">History Cmdlets</span></span>

<span data-ttu-id="0ee1f-124">PowerShell verfügt über eine Reihe von Cmdlets, die den Befehlsverlauf verwalten.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-124">PowerShell has a set of cmdlets that manage the command history.</span></span>

| <span data-ttu-id="0ee1f-125">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0ee1f-125">Cmdlet</span></span>           | <span data-ttu-id="0ee1f-126">Alias</span><span class="sxs-lookup"><span data-stu-id="0ee1f-126">Alias</span></span>  | <span data-ttu-id="0ee1f-127">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0ee1f-127">Description</span></span>                                |
| ---------------- | ------ | ------------------------------------------ |
| `Get-History`    | `h`    | <span data-ttu-id="0ee1f-128">Ruft den Befehlsverlauf ab.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-128">Gets the command history.</span></span>                  |
| `Invoke-History` | `r`    | <span data-ttu-id="0ee1f-129">Führt einen Befehl im Befehlsverlauf aus.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-129">Runs a command in the command history.</span></span>     |
| `Add-History`    |        | <span data-ttu-id="0ee1f-130">Fügt dem Befehlsverlauf einen Befehl hinzu.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-130">Adds a command to the command history.</span></span>     |
| `Clear-History`  | `clhy` | <span data-ttu-id="0ee1f-131">Löscht Befehle aus dem Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-131">Deletes commands from the command history.</span></span> |

### <a name="keyboard-shortcuts-for-managing-history"></a><span data-ttu-id="0ee1f-132">Tastenkombinationen zum Verwalten des Verlaufs</span><span class="sxs-lookup"><span data-stu-id="0ee1f-132">Keyboard Shortcuts for Managing History</span></span>

<span data-ttu-id="0ee1f-133">In der PowerShell-Konsole können Sie die folgenden Tastenkombinationen verwenden, um den Befehlsverlauf zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-133">In the PowerShell console, you can use the following shortcuts to manage the command history.</span></span>

- <span data-ttu-id="0ee1f-134"><kbd>Ubirow</kbd> -zeigt den vorherigen Befehl an.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-134"><kbd>UpArrow</kbd> - Displays the previous command.</span></span>
- <span data-ttu-id="0ee1f-135"><kbd>Downpfeil</kbd> : zeigt den nächsten Befehl an.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-135"><kbd>DownArrow</kbd> - Displays the next command.</span></span>
- <span data-ttu-id="0ee1f-136"><kbd>F7</kbd> -zeigt den Befehlsverlauf an.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-136"><kbd>F7</kbd> - Displays the command history.</span></span>
- <span data-ttu-id="0ee1f-137"><kbd>ESC</kbd> , um den Verlauf auszublenden.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-137"><kbd>ESC</kbd> - To hide the history.</span></span>
- <span data-ttu-id="0ee1f-138"><kbd>F8</kbd> -findet einen Befehl.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-138"><kbd>F8</kbd> - Finds a command.</span></span> <span data-ttu-id="0ee1f-139">Geben Sie ein oder mehrere Zeichen ein, und drücken Sie <kbd>F8</kbd>.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-139">Type one or more characters then press <kbd>F8</kbd>.</span></span> <span data-ttu-id="0ee1f-140">Drücken Sie die nächste Instanz erneut mit <kbd>F8</kbd> .</span><span class="sxs-lookup"><span data-stu-id="0ee1f-140">Press <kbd>F8</kbd> again the next instance.</span></span>
- <span data-ttu-id="0ee1f-141"><kbd>F9</kbd> -Suchen eines Befehls anhand der Verlaufs-ID.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-141"><kbd>F9</kbd> - Find a command by history ID.</span></span> <span data-ttu-id="0ee1f-142">Geben Sie die Verlauf-ID ein, und drücken Sie <kbd>F9</kbd></span><span class="sxs-lookup"><span data-stu-id="0ee1f-142">Type the history ID then press <kbd>F9</kbd>.</span></span> <span data-ttu-id="0ee1f-143">Drücken Sie <kbd>F7</kbd> , um die ID zu suchen.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-143">Press <kbd>F7</kbd> to find the ID.</span></span>
- <span data-ttu-id="0ee1f-144"><kbd>#</kbd>`<string>`</kbd><kbd>Tab</kbd> : Durchsuchen Sie den Verlauf nach, `*<string>*` und gibt die letzte Übereinstimmung zurück.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-144"><kbd>#</kbd>`<string>`</kbd><kbd>Tab</kbd> - Search the history for `*<string>*` and returns the most recent match.</span></span> <span data-ttu-id="0ee1f-145">Wenn Sie die <kbd>Tab</kbd> -Taste wiederholt drücken, durchläuft Sie die übereinstimmenden Elemente im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-145">If you press <kbd>Tab</kbd> repeatedly, it cycles through the matching items in your history.</span></span>

> [!NOTE]
> <span data-ttu-id="0ee1f-146">Diese Tastenbindungen werden von der Konsolen Host Anwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-146">These key bindings are implemented by the console host application.</span></span> <span data-ttu-id="0ee1f-147">Andere Anwendungen, wie z. b. Visual Studio Code oder Windows-Terminal, können unterschiedliche Tastenbindungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-147">Other applications, such as Visual Studio Code or Windows Terminal, can have different key bindings.</span></span> <span data-ttu-id="0ee1f-148">Die Bindungen können vom psread Line-Modul überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-148">The bindings can be overridden by the PSReadLine module.</span></span> <span data-ttu-id="0ee1f-149">Psread Line wird automatisch geladen, wenn Sie eine PowerShell-Sitzung starten.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-149">PSReadLine loads automatically when you start a PowerShell session.</span></span>
> <span data-ttu-id="0ee1f-150">Wenn psread Line geladen ist, sind <kbd>F7</kbd> und <kbd>F9</kbd> nicht an eine Funktion gebunden.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-150">With PSReadLine loaded, <kbd>F7</kbd> and <kbd>F9</kbd> are not bound to any function.</span></span> <span data-ttu-id="0ee1f-151">Psread Line bietet keine äquivalente Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-151">PSReadLine does not provide equivalent functionality.</span></span> <span data-ttu-id="0ee1f-152">Weitere Informationen finden Sie unter [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="0ee1f-152">For more information, see [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span></span>

### <a name="maximumhistorycount"></a><span data-ttu-id="0ee1f-153">MaximumHistoryCount</span><span class="sxs-lookup"><span data-stu-id="0ee1f-153">MaximumHistoryCount</span></span>

<span data-ttu-id="0ee1f-154">Die Einstellungs `$MaximumHistoryCount` Variable bestimmt die maximale Anzahl von Befehlen, die von PowerShell im Befehlsverlauf gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-154">The `$MaximumHistoryCount` preference variable determines the maximum number of commands that PowerShell saves in the command history.</span></span> <span data-ttu-id="0ee1f-155">Der Standardwert lautet</span><span class="sxs-lookup"><span data-stu-id="0ee1f-155">The default value is</span></span>
4096.

<span data-ttu-id="0ee1f-156">Mit dem folgenden Befehl werden z. b. die `$MaximumHistoryCount` auf 100-Befehle gesenkt:</span><span class="sxs-lookup"><span data-stu-id="0ee1f-156">For example, the following command lowers the `$MaximumHistoryCount` to 100 commands:</span></span>

```powershell
$MaximumHistoryCount = 100
```

<span data-ttu-id="0ee1f-157">Starten Sie PowerShell neu, um die Einstellung zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-157">To apply the setting, restart PowerShell.</span></span>

<span data-ttu-id="0ee1f-158">Um den neuen Variablen Wert für alle PowerShell-Sitzungen zu speichern, fügen Sie die Zuweisungsanweisung einem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-158">To save the new variable value for all your PowerShell sessions, add the assignment statement to a PowerShell profile.</span></span> <span data-ttu-id="0ee1f-159">Weitere Informationen zu Profilen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0ee1f-159">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="0ee1f-160">Weitere Informationen zur Einstellungs `$MaximumHistoryCount` Variablen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="0ee1f-160">For more information about the `$MaximumHistoryCount` preference variable, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

### <a name="order-of-commands-in-the-history"></a><span data-ttu-id="0ee1f-161">Reihenfolge der Befehle im Verlauf</span><span class="sxs-lookup"><span data-stu-id="0ee1f-161">Order of Commands in the History</span></span>

<span data-ttu-id="0ee1f-162">Befehle werden dem Verlauf hinzugefügt, wenn die Ausführung des Befehls abgeschlossen ist, und nicht, wenn der Befehl eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-162">Commands are added to the history when the command finishes executing, not when the command is entered.</span></span> <span data-ttu-id="0ee1f-163">Wenn die Ausführung von Befehlen einige Zeit in Anspruch nimmt oder die Befehle in einer eingefügten Eingabeaufforderung ausgeführt werden, scheinen die Befehle im Verlauf nicht in der richtigen Reihenfolge zu sein.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-163">If commands take some time to be completed, or if the commands are executing in a nested prompt, the commands might appear to be out of order in the history.</span></span> <span data-ttu-id="0ee1f-164">Befehle, die in einer eingefügten Eingabeaufforderung ausgeführt werden, werden nur abgeschlossen, wenn Sie die Eingabe Aufforderungs Ebene beenden.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-164">Commands that are executing in a nested prompt are completed only when you exit the prompt level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ee1f-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ee1f-165">See Also</span></span>

- [<span data-ttu-id="0ee1f-166">about_Line_Editing</span><span class="sxs-lookup"><span data-stu-id="0ee1f-166">about_Line_Editing</span></span>](about_Line_Editing.md)
- [<span data-ttu-id="0ee1f-167">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="0ee1f-167">about_Preference_Variables</span></span>](about_Preference_Variables.md)
- [<span data-ttu-id="0ee1f-168">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="0ee1f-168">about_Profiles</span></span>](about_Profiles.md)
- [<span data-ttu-id="0ee1f-169">about_Variables</span><span class="sxs-lookup"><span data-stu-id="0ee1f-169">about_Variables</span></span>](about_Variables.md)
- [<span data-ttu-id="0ee1f-170">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="0ee1f-170">about_PSReadLine</span></span>](../../PSReadLine/About/about_PSReadLine.md)
