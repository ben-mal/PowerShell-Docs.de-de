---
ms.date: 09/12/2016
ms.topic: reference
title: Ablegen der kommentarbasierten Hilfe in Skripts
description: Ablegen der kommentarbasierten Hilfe in Skripts
ms.openlocfilehash: b0d32b7ab063269085899a643b0c3a17da2073fc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645441"
---
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="f05b2-103">Ablegen der kommentarbasierten Hilfe in Skripts</span><span class="sxs-lookup"><span data-stu-id="f05b2-103">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="f05b2-104">In diesem Thema wird erläutert, wo Sie eine Kommentar basierte Hilfe für ein Skript platzieren können, damit das `Get-Help` Cmdlet das Kommentar basierte Hilfethema Skripts und keine Funktionen zuordnet, die möglicherweise im Skript vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f05b2-104">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="f05b2-105">Speicherort Comment-Based Hilfe für ein Skript</span><span class="sxs-lookup"><span data-stu-id="f05b2-105">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="f05b2-106">Am Anfang der Skriptdatei.</span><span class="sxs-lookup"><span data-stu-id="f05b2-106">At the beginning of the script file.</span></span>

  <span data-ttu-id="f05b2-107">Der Skript Hilfe kann das Skript nur durch Kommentare und leere Zeilen vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f05b2-107">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="f05b2-108">Am Ende der Skriptdatei.</span><span class="sxs-lookup"><span data-stu-id="f05b2-108">At the end of the script file.</span></span>

  <span data-ttu-id="f05b2-109">Wenn das erste Element im Skript Text (nach der Hilfe) eine Funktionsdeklaration ist, müssen zwischen dem Ende der Skript Hilfe und der Funktionsdeklaration mindestens zwei Leerzeilen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="f05b2-109">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="f05b2-110">Andernfalls wird die Hilfe als Hilfe für die Funktion interpretiert, nicht als Hilfe für das Skript.</span><span class="sxs-lookup"><span data-stu-id="f05b2-110">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="f05b2-111">Beispiele für die Platzierung von Hilfe in einem Skript</span><span class="sxs-lookup"><span data-stu-id="f05b2-111">Examples of Help Placement in a Script</span></span>

<span data-ttu-id="f05b2-112">In den folgenden Beispielen werden die einzelnen Platzierungs Optionen für die Kommentar basierte Hilfe eines Skripts gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f05b2-112">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="f05b2-113">Hilfe zu Beginn eines Skripts</span><span class="sxs-lookup"><span data-stu-id="f05b2-113">Help at the Beginning of a Script</span></span>

<span data-ttu-id="f05b2-114">Das folgende Beispiel zeigt einen Kommentar basierten am Anfang eines Skripts.</span><span class="sxs-lookup"><span data-stu-id="f05b2-114">The following example shows comment-based at the beginning of a script.</span></span>

```powershell
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="f05b2-115">Hilfe am Ende eines Skripts</span><span class="sxs-lookup"><span data-stu-id="f05b2-115">Help at the End of a Script</span></span>

 <span data-ttu-id="f05b2-116">Das folgende Beispiel zeigt am Ende eines Skripts eine Kommentar basierte.</span><span class="sxs-lookup"><span data-stu-id="f05b2-116">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>
```
