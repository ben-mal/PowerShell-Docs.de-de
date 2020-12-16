---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: Verwenden von Erweiterung mit der TAB-TASTE
description: Erläutert die Nutzung des Features zur Erweiterung mit der TAB-TASTE in PowerShell.
ms.openlocfilehash: 658cdf5ddf78bbd6dd431c2170cd5ff643e6bf95
ms.sourcegitcommit: 7f712e12ec5b3f3f3e695da804b050ea0ce58b3a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94661340"
---
# <a name="using-tab-expansion"></a><span data-ttu-id="39091-104">Verwenden von Erweiterung mit der TAB-TASTE</span><span class="sxs-lookup"><span data-stu-id="39091-104">Using Tab Expansion</span></span>

<span data-ttu-id="39091-105">Befehlszeilenshells bieten häufig eine Möglichkeit, die Namen langer Dateien oder Befehle automatisch zu vervollständigen, wodurch die Befehlseingabe und das Bereitstellen von Hinweisen beschleunigt werden.</span><span class="sxs-lookup"><span data-stu-id="39091-105">Command-line shells often provide a way to complete the names of long files or commands automatically, speeding up command entry and providing hints.</span></span> <span data-ttu-id="39091-106">PowerShell ermöglicht Ihnen das Ausfüllen von Dateinamen und Cmdletnamen durch Drücken der <kbd>TAB-TASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="39091-106">PowerShell allows you to fill in file names and cmdlet names by pressing the <kbd>Tab</kbd> key.</span></span>

> [!NOTE]
> <span data-ttu-id="39091-107">Die Erweiterung mit der TAB-TASTE wird durch die interne Funktion „TabExpansion“ oder „TabExpansion2“ gesteuert.</span><span class="sxs-lookup"><span data-stu-id="39091-107">Tab expansion is controlled by the internal function TabExpansion or TabExpansion2.</span></span> <span data-ttu-id="39091-108">Da diese Funktion geändert oder überschrieben werden kann, ist diese Erläuterung eine Anleitung für das Verhalten der Standardkonfiguration von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39091-108">Since this function can be modified or overridden, this discussion is a guide to the behavior of the default PowerShell configuration.</span></span>

<span data-ttu-id="39091-109">Soll ein Dateiname oder Pfad automatisch aus den verfügbaren Optionen ausgefüllt werden, geben Sie einen Teil des Namens ein, und drücken Sie die <kbd>TAB-TASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="39091-109">To fill in a filename or path from the available choices automatically, type part of the name and press the <kbd>Tab</kbd> key.</span></span> <span data-ttu-id="39091-110">PowerShell erweitert den Namen automatisch entsprechend der ersten gefundenen Übereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="39091-110">PowerShell will automatically expand the name to the first match that it finds.</span></span> <span data-ttu-id="39091-111">Durch wiederholtes Drücken der <kbd>TAB-TASTE</kbd> werden alle verfügbaren Optionen durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="39091-111">Pressing the <kbd>Tab</kbd> key repeatedly will cycle through all of the available choices.</span></span>

<span data-ttu-id="39091-112">Für Cmdletnamen funktioniert Erweiterung mit der TAB-TASTE etwas anders.</span><span class="sxs-lookup"><span data-stu-id="39091-112">The tab expansion of cmdlet names is slightly different.</span></span> <span data-ttu-id="39091-113">Um Erweiterung mit der TAB-TASTE für einen Cmdletnamen zu verwenden, geben Sie den gesamten ersten Teil des Namens (das Verb) und den darauf folgenden Bindestrich ein.</span><span class="sxs-lookup"><span data-stu-id="39091-113">To use tab expansion on a cmdlet name, type the entire first part of the name (the verb) and the hyphen that follows it.</span></span> <span data-ttu-id="39091-114">Sie können weitere Zeichen des Namens für eine Teilübereinstimmung eingeben.</span><span class="sxs-lookup"><span data-stu-id="39091-114">You can fill in more of the name for a partial match.</span></span> <span data-ttu-id="39091-115">Wenn Sie beispielsweise `get-co` eingeben und dann die <kbd>TAB-TASTE</kbd> drücken, erweitert PowerShell diese Eingabe automatisch zu dem Cmdlet `Get-Command` (wie Sie sehen, wird auch die Groß-/Kleinschreibung der Buchstaben in die Standardform geändert).</span><span class="sxs-lookup"><span data-stu-id="39091-115">For example, if you type `get-co` and then press the <kbd>Tab</kbd> key, PowerShell will automatically expand this to the `Get-Command` cmdlet (notice that it also changes the case of letters to their standard form).</span></span> <span data-ttu-id="39091-116">Wenn Sie die <kbd>TAB-TASTE</kbd> erneut drücken, ersetzt PowerShell diesen Cmdletnamen durch den einzigen anderen passenden Cmdletnamen, `Get-Content`.</span><span class="sxs-lookup"><span data-stu-id="39091-116">If you press <kbd>Tab</kbd> key again, PowerShell replaces this with the only other matching cmdlet name, `Get-Content`.</span></span>

> [!NOTE]
> <span data-ttu-id="39091-117">Ab PowerShell 7.0 werden mit <kbd>Tab</kbd> auch abgekürzte Cmdlets und Funktionen erweitert.</span><span class="sxs-lookup"><span data-stu-id="39091-117">As of PowerShell 7.0, <kbd>Tab</kbd> will also expand abbreviated cmdlets and functions.</span></span> <span data-ttu-id="39091-118">`i-psdf<tab>` gibt beispielsweise `Import-PowerShellDataFile` zurück.</span><span class="sxs-lookup"><span data-stu-id="39091-118">For example, `i-psdf<tab>` returns `Import-PowerShellDataFile`.</span></span>

<span data-ttu-id="39091-119">Sie können Erweiterung mit der TAB-TASTE wiederholt in derselben Zeile verwenden.</span><span class="sxs-lookup"><span data-stu-id="39091-119">You can use tab expansion repeatedly on the same line.</span></span> <span data-ttu-id="39091-120">Beispielsweise können Sie die Erweiterung mit der TAB-TASTE für den Namen des Cmdlets `Get-Content` verwenden, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="39091-120">For example, you can use tab expansion on the name of the `Get-Content` cmdlet by entering:</span></span>

```
PS> Get-Con<Tab>
```

<span data-ttu-id="39091-121">Wenn Sie die <kbd>TAB-TASTE</kbd> drücken, wird der Befehlsname erweitert zu:</span><span class="sxs-lookup"><span data-stu-id="39091-121">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content
```

<span data-ttu-id="39091-122">Sie können dann den Pfad zur Protokolldatei für das aktive Setup teilweise eingeben und erneut Erweiterung mit der TAB-TASTE verwenden:</span><span class="sxs-lookup"><span data-stu-id="39091-122">You can then partially specify the path to the Active Setup log file and use tab expansion again:</span></span>

```
PS> Get-Content c:\windows\acts<Tab>
```

<span data-ttu-id="39091-123">Wenn Sie die <kbd>TAB-TASTE</kbd> drücken, wird der Befehlsname erweitert zu:</span><span class="sxs-lookup"><span data-stu-id="39091-123">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content C:\windows\actsetup.log
```

> [!NOTE]
> <span data-ttu-id="39091-124">Eine Einschränkung für Erweiterung mit der TAB-TASTE besteht darin, dass Tabulatorzeichen immer als Versuche interpretiert werden, ein Wort zu vervollständigen.</span><span class="sxs-lookup"><span data-stu-id="39091-124">One limitation of the tab expansion process is that tabs are always interpreted as attempts to complete a word.</span></span> <span data-ttu-id="39091-125">Wenn Sie ein Befehlsbeispiel kopieren und in einer PowerShell-Konsole einfügen, sollten Sie sich vergewissern, dass das Beispiel keine Tabulatorzeichen enthält. Andernfalls sind die Ergebnisse unvorhersehbar und entsprechen mit großer Wahrscheinlichkeit nicht dem, was Sie beabsichtigen.</span><span class="sxs-lookup"><span data-stu-id="39091-125">If you copy and paste command examples into a PowerShell console, make sure that the sample does not contain tabs; if it does, the results will be unpredictable and will almost certainly not be what you intended.</span></span>
