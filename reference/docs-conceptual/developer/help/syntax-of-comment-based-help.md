---
ms.date: 09/12/2016
ms.topic: reference
title: Syntax der kommentarbasierten Hilfe
description: Syntax der kommentarbasierten Hilfe
ms.openlocfilehash: 3866f25b40fc970e8d219af6f423b7a25f5b875c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659521"
---
# <a name="syntax-of-comment-based-help"></a><span data-ttu-id="e9f4d-103">Syntax der kommentarbasierten Hilfe</span><span class="sxs-lookup"><span data-stu-id="e9f4d-103">Syntax of Comment-Based Help</span></span>

<span data-ttu-id="e9f4d-104">In diesem Abschnitt wird die Syntax der Kommentar basierten Hilfe beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9f4d-104">This section describes the syntax of comment-based help.</span></span>

## <a name="syntax-diagram"></a><span data-ttu-id="e9f4d-105">Syntax Diagramm</span><span class="sxs-lookup"><span data-stu-id="e9f4d-105">Syntax Diagram</span></span>

 <span data-ttu-id="e9f4d-106">Die Syntax für die Kommentar basierte Hilfe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e9f4d-106">The syntax for comment-based Help is as follows:</span></span>

```
# .< help keyword>
# <help content>

-or -

<#
.< help keyword>
< help content>
#>
```

## <a name="syntax-description"></a><span data-ttu-id="e9f4d-107">Syntaxbeschreibung</span><span class="sxs-lookup"><span data-stu-id="e9f4d-107">Syntax Description</span></span>

 <span data-ttu-id="e9f4d-108">Die Kommentar basierte Hilfe wird als eine Reihe von Kommentaren geschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9f4d-108">Comment-based Help is written as a series of comments.</span></span> <span data-ttu-id="e9f4d-109">Sie können `#` vor jeder Zeile von Kommentaren ein Kommentar Symbol () eingeben, oder Sie können das-Symbol und das-Symbol verwenden, `<#` `#>` um einen Kommentar Block zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e9f4d-109">You can type a comment symbol (`#`) before each line of comments, or you can use the `<#` and `#>` symbols to create a comment block.</span></span> <span data-ttu-id="e9f4d-110">Alle Zeilen innerhalb des Kommentar Blocks werden als Kommentare interpretiert.</span><span class="sxs-lookup"><span data-stu-id="e9f4d-110">All the lines within the comment block are interpreted as comments.</span></span>

 <span data-ttu-id="e9f4d-111">Jeder Abschnitt der Kommentar basierten Hilfe wird durch ein Schlüsselwort definiert, und jedem Schlüsselwort wird ein Punkt ( `.` ) vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="e9f4d-111">Each section of comment-based Help is defined by a keyword and each keyword is preceded by a dot (`.`).</span></span> <span data-ttu-id="e9f4d-112">Die Schlüsselwörter können in beliebiger Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e9f4d-112">The keywords can appear in any order.</span></span> <span data-ttu-id="e9f4d-113">Beim Schlüsselwort Namen wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="e9f4d-113">The keyword names are not case-sensitive.</span></span>

 <span data-ttu-id="e9f4d-114">Ein Kommentar Block muss mindestens ein Hilfe Schlüsselwort enthalten.</span><span class="sxs-lookup"><span data-stu-id="e9f4d-114">A comment block must contain at least one help keyword.</span></span> <span data-ttu-id="e9f4d-115">Einige der Schlüsselwörter (z. b. **beispielsweise**) können mehrmals im gleichen Kommentar Block vorkommen.</span><span class="sxs-lookup"><span data-stu-id="e9f4d-115">Some of the keywords, such as **EXAMPLE**, can appear many times in the same comment block.</span></span> <span data-ttu-id="e9f4d-116">Der Hilfe Inhalt für jedes Schlüsselwort beginnt in der Zeile nach dem-Schlüsselwort und kann sich über mehrere Zeilen erstrecken.</span><span class="sxs-lookup"><span data-stu-id="e9f4d-116">The Help content for each keyword begins on the line after the keyword and can span multiple lines.</span></span>

 <span data-ttu-id="e9f4d-117">Alle Zeilen in einem Kommentar basierten Hilfethema müssen zusammenhängend sein.</span><span class="sxs-lookup"><span data-stu-id="e9f4d-117">All of the lines in a comment-based Help topic must be contiguous.</span></span> <span data-ttu-id="e9f4d-118">Wenn ein Kommentar basiertes Hilfethema einem Kommentar folgt, der nicht Teil des Hilfe Themas ist, muss mindestens eine Leerzeile zwischen der letzten nicht-Hilfe Kommentarzeile und dem Anfang der Kommentar basierten Hilfe vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="e9f4d-118">If a comment-based Help topic follows a comment that is not part of the Help topic, there must be at least one blank line between the last non-Help comment line and the beginning of the comment-based Help.</span></span>

 <span data-ttu-id="e9f4d-119">Beispielsweise enthält das folgende Kommentar basierte Hilfethema die. Description-Schlüsselwort und sein Wert, eine Beschreibung einer Funktion oder eines Skripts.</span><span class="sxs-lookup"><span data-stu-id="e9f4d-119">For example, the following comment-based help topic contains the .Description keyword and its value, which is a description of a function or script.</span></span>

```powershell
<#
    .Description
    The Get-Function function displays the name and syntax of all functions in the session.
#>
```
