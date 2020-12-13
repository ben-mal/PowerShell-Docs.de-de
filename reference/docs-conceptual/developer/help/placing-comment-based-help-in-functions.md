---
ms.date: 09/12/2016
ms.topic: reference
title: Ablegen der kommentarbasierten Hilfe in Funktionen
description: Ablegen der kommentarbasierten Hilfe in Funktionen
ms.openlocfilehash: 3bd72f0c71d8f6ad54c43c99f044423c072fdeeb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658199"
---
# <a name="placing-comment-based-help-in-functions"></a><span data-ttu-id="79d7c-103">Ablegen der kommentarbasierten Hilfe in Funktionen</span><span class="sxs-lookup"><span data-stu-id="79d7c-103">Placing Comment-Based Help in Functions</span></span>

<span data-ttu-id="79d7c-104">In diesem Thema wird erläutert, wo Sie eine Kommentar basierte Hilfe für eine Funktion platzieren können, damit das `Get-Help` Cmdlet das Kommentar basierte Hilfethema der richtigen Funktion zuordnet.</span><span class="sxs-lookup"><span data-stu-id="79d7c-104">This topic explains where to place comment-based help for a function so that the `Get-Help` cmdlet associates the comment-based help topic with the correct function.</span></span>

## <a name="where-to-place-comment-based-help-for-a-function"></a><span data-ttu-id="79d7c-105">Speicherort Comment-Based Hilfe für eine Funktion</span><span class="sxs-lookup"><span data-stu-id="79d7c-105">Where to Place Comment-Based Help for a Function</span></span>

- <span data-ttu-id="79d7c-106">Am Anfang des Funktions Texts.</span><span class="sxs-lookup"><span data-stu-id="79d7c-106">At the beginning of the function body.</span></span>

- <span data-ttu-id="79d7c-107">Am Ende des Funktions Texts.</span><span class="sxs-lookup"><span data-stu-id="79d7c-107">At the end of the function body.</span></span>

- <span data-ttu-id="79d7c-108">Vor dem- `Function` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="79d7c-108">Before the `Function` keyword.</span></span> <span data-ttu-id="79d7c-109">Wenn sich die Funktion in einem Skript-oder Skript Modul befindet, darf zwischen der letzten Zeile der Kommentar basierten Hilfe und dem-Schlüsselwort nicht mehr als eine Leerzeile vorhanden sein `Function` .</span><span class="sxs-lookup"><span data-stu-id="79d7c-109">When the function is in a script or script module, there cannot be more than one blank line between the last line of the comment-based help and the `Function` keyword.</span></span> <span data-ttu-id="79d7c-110">Andernfalls ordnet die `Get-Help` Hilfe dem Skript und nicht der-Funktion zu.</span><span class="sxs-lookup"><span data-stu-id="79d7c-110">Otherwise, `Get-Help` associates the help with the script, not with the function.</span></span>

## <a name="examples-of-help-placement-in-a-function"></a><span data-ttu-id="79d7c-111">Beispiele für die Platzierung von Hilfe in einer Funktion</span><span class="sxs-lookup"><span data-stu-id="79d7c-111">Examples of Help Placement in a Function</span></span>

<span data-ttu-id="79d7c-112">Die folgenden Beispiele zeigen jede der drei Platzierungs Optionen für die Kommentar basierte Hilfe für eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="79d7c-112">The following examples show each of the three placement options for comment-based help for a function.</span></span>

### <a name="help-at-the-beginning-of-a-function-body"></a><span data-ttu-id="79d7c-113">Hilfe am Anfang eines Funktions Texts</span><span class="sxs-lookup"><span data-stu-id="79d7c-113">Help at the Beginning of a Function Body</span></span>

<span data-ttu-id="79d7c-114">Das folgende Beispiel zeigt einen Kommentar basierten am Anfang eines Funktions Texts.</span><span class="sxs-lookup"><span data-stu-id="79d7c-114">The following example shows comment-based at the beginning of a function body.</span></span>

```powershell
function MyProcess
{
    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>

    Get-Process powershell
}
```

### <a name="help-at-the-end-of-a-function-body"></a><span data-ttu-id="79d7c-115">Hilfe am Ende eines Funktions Texts</span><span class="sxs-lookup"><span data-stu-id="79d7c-115">Help at the End of a Function Body</span></span>

 <span data-ttu-id="79d7c-116">Das folgende Beispiel zeigt am Ende eines Funktions Texts einen Kommentar basierten Text.</span><span class="sxs-lookup"><span data-stu-id="79d7c-116">The following example shows comment-based at the end of a function body.</span></span>

```powershell
function MyFunction
{
    Get-Process powershell

    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>
}
```

### <a name="help-before-the-function-keyword"></a><span data-ttu-id="79d7c-117">Hilfe vor dem Function-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="79d7c-117">Help Before the Function Keyword</span></span>

 <span data-ttu-id="79d7c-118">In den folgenden Beispielen wird die Kommentar basierte Zeile vor dem Function-Schlüsselwort gezeigt.</span><span class="sxs-lookup"><span data-stu-id="79d7c-118">The following examples shows comment-based on the line before the function keyword.</span></span>

```powershell
<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}
```
