---
description: Erläutert, wie Sie eine Anpassung an die Eingabeaufforderung von PowerShell an der Konsole erstellen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_psconsolehostreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSConsoleHostReadLine
ms.openlocfilehash: 143fa763c109b5645f992c3bb0a3097a8b2d9e90
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220871"
---
# <a name="about_psconsolehostreadline"></a><span data-ttu-id="8a600-104">about_PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="8a600-104">about_PSConsoleHostReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="8a600-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8a600-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="8a600-106">Erläutert, wie Sie eine Anpassung an die Eingabeaufforderung von PowerShell an der Konsole erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a600-106">Explains how to create a customize how PowerShell reads input at the console prompt.</span></span>

## <a name="long-description"></a><span data-ttu-id="8a600-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8a600-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="8a600-108">Ab Windows PowerShell 3,0 können Sie eine Funktion mit dem Namen psconsolehostread Line schreiben, mit der die Standardmethode für die Verarbeitung der Konsolen Eingabe überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="8a600-108">Starting in Windows PowerShell 3.0, you can write a function named PSConsoleHostReadLine that overrides the default way that console input is processed.</span></span>

### <a name="examples"></a><span data-ttu-id="8a600-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8a600-109">EXAMPLES</span></span>

<span data-ttu-id="8a600-110">Im folgenden Beispiel wird Notepad gestartet und Eingaben aus einer vom Benutzer erstellten Textdatei abgerufen:</span><span class="sxs-lookup"><span data-stu-id="8a600-110">The following example launches Notepad and gets input from a text File that the user creates:</span></span>

```powershell
function PSConsoleHostReadLine
{
  $inputFile = Join-Path $env:TEMP PSConsoleHostReadLine
  Set-Content $inputFile "PS > "

  # Notepad opens. Enter your command in it, save the file, and then exit.
  notepad $inputFile | Out-Null
  $userInput = Get-Content $inputFile
  $resultingCommand = $userInput.Replace("PS >", "")
  $resultingCommand
}
```

### <a name="remarks"></a><span data-ttu-id="8a600-111">ANMERKUNGEN</span><span class="sxs-lookup"><span data-stu-id="8a600-111">REMARKS</span></span>

<span data-ttu-id="8a600-112">PowerShell liest Eingaben standardmäßig in der-Konsole, was als "gekochte Modus" bezeichnet wird. dabei verarbeitet das Windows-Konsolen Subsystem alle Tastatur drücken, F7-Menüs und andere Eingaben.</span><span class="sxs-lookup"><span data-stu-id="8a600-112">By default, PowerShell reads input from the console in what is known as "Cooked Mode" -- in which the Windows console subsystem handles all the keypresses, F7 menus, and other input.</span></span> <span data-ttu-id="8a600-113">Wenn Sie die EINGABETASTE oder die Tab-Taste drücken, erhält PowerShell den Text, den Sie bis zu diesem Punkt eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="8a600-113">When you press Enter or Tab, PowerShell gets the text that you have typed up to that point.</span></span> <span data-ttu-id="8a600-114">Es gibt keine Möglichkeit, zu wissen, dass Sie STRG + R, STRG + A, STRG + E oder andere Tasten gedrückt haben, bevor Sie die EINGABETASTE oder TAB drücken. In Windows PowerShell 3,0 löst die psconsolehostread Line-Funktion dieses Problem.</span><span class="sxs-lookup"><span data-stu-id="8a600-114">There is no way for it to know that you pressed Ctrl-R, Ctrl-A, Ctrl-E, or any other keys before pressing Enter or Tab. In Windows PowerShell 3.0, the PSConsoleHostReadLine function solves this issue.</span></span> <span data-ttu-id="8a600-115">Wenn Sie im PowerShell-Konsolen Host eine Funktion mit dem Namen psconsolehostread Line definieren, wird diese Funktion von PowerShell anstelle des Eingabe Mechanismus "gekochte Modus" aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8a600-115">When you define a function named PSConsoleHostReadline in the PowerShell console host, PowerShell calls that function instead of the "Cooked Mode" input mechanism.</span></span>

### <a name="see-also"></a><span data-ttu-id="8a600-116">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="8a600-116">SEE ALSO</span></span>

[<span data-ttu-id="8a600-117">about_Prompts</span><span class="sxs-lookup"><span data-stu-id="8a600-117">about_Prompts</span></span>](about_Prompts.md)

