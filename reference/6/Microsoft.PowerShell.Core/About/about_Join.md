---
description: Beschreibt, wie der Joinoperator (-Join) mehrere Zeichen folgen zu einer einzelnen Zeichenfolge kombiniert.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_join?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Join
ms.openlocfilehash: adc65e688894ce71ea386fd2b21799612df789a0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221548"
---
# <a name="about-join"></a><span data-ttu-id="6b75f-104">Informationen zum Join</span><span class="sxs-lookup"><span data-stu-id="6b75f-104">About join</span></span>

## <a name="short-description"></a><span data-ttu-id="6b75f-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6b75f-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="6b75f-106">Beschreibt, wie der Joinoperator (-Join) mehrere Zeichen folgen zu einer einzelnen Zeichenfolge kombiniert.</span><span class="sxs-lookup"><span data-stu-id="6b75f-106">Describes how the join operator (-join) combines multiple strings into a single string.</span></span>

## <a name="long-description"></a><span data-ttu-id="6b75f-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6b75f-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="6b75f-108">Der Join-Operator verkettet eine Reihe von Zeichen folgen zu einer einzelnen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6b75f-108">The join operator concatenates a set of strings into a single string.</span></span> <span data-ttu-id="6b75f-109">Die Zeichen folgen werden in der Reihenfolge, in der Sie im Befehl angezeigt werden, an die resultierende Zeichenfolge angehängt.</span><span class="sxs-lookup"><span data-stu-id="6b75f-109">The strings are appended to the resulting string in the order that they appear in the command.</span></span>

### <a name="syntax"></a><span data-ttu-id="6b75f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b75f-110">Syntax</span></span>

<span data-ttu-id="6b75f-111">Das folgende Diagramm zeigt die Syntax für den Join-Operator.</span><span class="sxs-lookup"><span data-stu-id="6b75f-111">The following diagram shows the syntax for the join operator.</span></span>

```powershell
-Join <String[]>
<String[]> -Join <Delimiter>
```

#### <a name="parameters"></a><span data-ttu-id="6b75f-112">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b75f-112">Parameters</span></span>

<span data-ttu-id="6b75f-113">String []: gibt eine oder mehrere Zeichen folgen an, die verknüpft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6b75f-113">String[] - Specifies one or more strings to be joined.</span></span>

<span data-ttu-id="6b75f-114">Delimiter: gibt ein oder mehrere Zeichen an, die zwischen den verketteten Zeichen folgen platziert werden.</span><span class="sxs-lookup"><span data-stu-id="6b75f-114">Delimiter - Specifies one or more characters placed between the concatenated strings.</span></span> <span data-ttu-id="6b75f-115">Der Standardwert ist kein Trennzeichen ("").</span><span class="sxs-lookup"><span data-stu-id="6b75f-115">The default is no delimiter ("").</span></span>

<span data-ttu-id="6b75f-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b75f-116">Remarks</span></span>

<span data-ttu-id="6b75f-117">Der unäre Joinoperator (-Join <String [] >) hat Vorrang vor einem Komma.</span><span class="sxs-lookup"><span data-stu-id="6b75f-117">The unary join operator (-join <string[]>) has higher precedence than a comma.</span></span> <span data-ttu-id="6b75f-118">Wenn Sie daher eine durch Trennzeichen getrennte Liste von Zeichen folgen an den unären Joinoperator übermitteln, wird nur die erste Zeichenfolge (vor dem ersten Komma) an den Join-Operator übermittelt.</span><span class="sxs-lookup"><span data-stu-id="6b75f-118">As a result, if you submit a comma-separated list of strings to the unary join operator, only the first string (before the first comma) is submitted to the join operator.</span></span>

<span data-ttu-id="6b75f-119">Um den unären Join-Operator zu verwenden, schließen Sie die Zeichen folgen in Klammern ein, oder speichern Sie die Zeichen folgen in einer Variablen, und senden Sie dann die Variable an Join.</span><span class="sxs-lookup"><span data-stu-id="6b75f-119">To use the unary join operator, enclose the strings in parentheses, or store the strings in a variable, and then submit the variable to join.</span></span>

<span data-ttu-id="6b75f-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6b75f-120">For example:</span></span>

```powershell
-join "a", "b", "c"
a
b
c

-join ("a", "b", "c")
abc

$z = "a", "b", "c"
-join $z
abc
```

### <a name="examples"></a><span data-ttu-id="6b75f-121">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6b75f-121">Examples</span></span>

<span data-ttu-id="6b75f-122">Die folgende Anweisung verbindet drei Zeichen folgen:</span><span class="sxs-lookup"><span data-stu-id="6b75f-122">The following statement joins three strings:</span></span>

```powershell
-join ("Windows", "PowerShell", "2.0")
WindowsPowerShell2.0
```

<span data-ttu-id="6b75f-123">Die folgende Anweisung verbindet drei Zeichen folgen, die durch ein Leerzeichen voneinander getrennt sind:</span><span class="sxs-lookup"><span data-stu-id="6b75f-123">The following statement joins three strings delimited by a space:</span></span>

```powershell
"Windows", "PowerShell", "2.0" -join " "
Windows PowerShell 2.0
```

<span data-ttu-id="6b75f-124">In den folgenden Anweisungen wird ein Trennzeichen für mehrere Zeichen verwendet, um drei Zeichen folgen zu verknüpfen:</span><span class="sxs-lookup"><span data-stu-id="6b75f-124">The following statements use a multiple-character delimiter to join three strings:</span></span>

```powershell
$a = "WIND", "S P", "ERSHELL"
$a -join "OW"
WINDOWS POWERSHELL
```

<span data-ttu-id="6b75f-125">Die folgende Anweisung verbindet die Zeilen in einer here-Zeichenfolge mit einer einzelnen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6b75f-125">The following statement joins the lines in a here-string into a single string.</span></span> <span data-ttu-id="6b75f-126">Da eine here-Zeichenfolge eine Zeichenfolge ist, müssen die Zeilen in der here-Zeichenfolge aufgeteilt werden, bevor Sie verknüpft werden können.</span><span class="sxs-lookup"><span data-stu-id="6b75f-126">Because a here-string is one string, the lines in the here-string must be split before they can be joined.</span></span> <span data-ttu-id="6b75f-127">Sie können diese Methode verwenden, um die Zeichen folgen in einer XML-Datei, die in einer here-Zeichenfolge gespeichert wurde, erneut hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="6b75f-127">You can use this method to rejoin the strings in an XML file that has been saved in a here-string:</span></span>

```powershell
$a = @'
a
b
c
'@

(-split $a) -join " "
a b c
```

## <a name="see-also"></a><span data-ttu-id="6b75f-128">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="6b75f-128">SEE ALSO</span></span>

[<span data-ttu-id="6b75f-129">about_Operators</span><span class="sxs-lookup"><span data-stu-id="6b75f-129">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="6b75f-130">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="6b75f-130">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="6b75f-131">about_Split</span><span class="sxs-lookup"><span data-stu-id="6b75f-131">about_Split</span></span>](about_Split.md)
