---
description: Erläutert, wie Sie eine Anpassung an die Eingabeaufforderung von PowerShell an der Konsole erstellen.
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_psconsolehostreadline?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSConsoleHostReadLine
ms.openlocfilehash: 2f69cd4c0c8f65f4a963eae561647d6de30a067e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600718"
---
# <a name="about_psconsolehostreadline"></a><span data-ttu-id="2508c-103">about_PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="2508c-103">about_PSConsoleHostReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="2508c-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2508c-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="2508c-105">Erläutert, wie Sie eine Anpassung an die Eingabeaufforderung von PowerShell an der Konsole erstellen.</span><span class="sxs-lookup"><span data-stu-id="2508c-105">Explains how to create a customize how PowerShell reads input at the console prompt.</span></span>

## <a name="long-description"></a><span data-ttu-id="2508c-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2508c-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="2508c-107">Ab Windows PowerShell 3,0 können Sie eine Funktion mit dem Namen psconsolehostread Line schreiben, mit der die Standardmethode für die Verarbeitung der Konsolen Eingabe überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="2508c-107">Starting in Windows PowerShell 3.0, you can write a function named PSConsoleHostReadLine that overrides the default way that console input is processed.</span></span>

### <a name="examples"></a><span data-ttu-id="2508c-108">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2508c-108">EXAMPLES</span></span>

<span data-ttu-id="2508c-109">Im folgenden Beispiel wird Notepad gestartet und Eingaben aus einer vom Benutzer erstellten Textdatei abgerufen:</span><span class="sxs-lookup"><span data-stu-id="2508c-109">The following example launches Notepad and gets input from a text File that the user creates:</span></span>

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

### <a name="remarks"></a><span data-ttu-id="2508c-110">ANMERKUNGEN</span><span class="sxs-lookup"><span data-stu-id="2508c-110">REMARKS</span></span>

<span data-ttu-id="2508c-111">PowerShell liest Eingaben standardmäßig in der-Konsole, was als "gekochte Modus" bezeichnet wird. dabei verarbeitet das Windows-Konsolen Subsystem alle Tastatur drücken, F7-Menüs und andere Eingaben.</span><span class="sxs-lookup"><span data-stu-id="2508c-111">By default, PowerShell reads input from the console in what is known as "Cooked Mode" -- in which the Windows console subsystem handles all the keypresses, F7 menus, and other input.</span></span> <span data-ttu-id="2508c-112">Wenn Sie die EINGABETASTE oder die Tab-Taste drücken, erhält PowerShell den Text, den Sie bis zu diesem Punkt eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="2508c-112">When you press Enter or Tab, PowerShell gets the text that you have typed up to that point.</span></span> <span data-ttu-id="2508c-113">Es gibt keine Möglichkeit, zu wissen, dass Sie STRG + R, STRG + A, STRG + E oder andere Tasten gedrückt haben, bevor Sie die EINGABETASTE oder TAB drücken. In Windows PowerShell 3,0 löst die psconsolehostread Line-Funktion dieses Problem.</span><span class="sxs-lookup"><span data-stu-id="2508c-113">There is no way for it to know that you pressed Ctrl-R, Ctrl-A, Ctrl-E, or any other keys before pressing Enter or Tab. In Windows PowerShell 3.0, the PSConsoleHostReadLine function solves this issue.</span></span> <span data-ttu-id="2508c-114">Wenn Sie im PowerShell-Konsolen Host eine Funktion mit dem Namen psconsolehostread Line definieren, wird diese Funktion von PowerShell anstelle des Eingabe Mechanismus "gekochte Modus" aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="2508c-114">When you define a function named PSConsoleHostReadline in the PowerShell console host, PowerShell calls that function instead of the "Cooked Mode" input mechanism.</span></span>

### <a name="see-also"></a><span data-ttu-id="2508c-115">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="2508c-115">SEE ALSO</span></span>

[<span data-ttu-id="2508c-116">about_Prompts</span><span class="sxs-lookup"><span data-stu-id="2508c-116">about_Prompts</span></span>](about_Prompts.md)

