---
description: Führt eine Anweisungs Liste einmal oder mehrmals aus, je nach while-oder until-Bedingung.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_do?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Do
ms.openlocfilehash: 9c5a7c561fde4d96401771870cf4e85d78591593
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223532"
---
# <a name="about-do"></a><span data-ttu-id="e7f48-104">Informationen zu do</span><span class="sxs-lookup"><span data-stu-id="e7f48-104">About Do</span></span>

## <a name="short-description"></a><span data-ttu-id="e7f48-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e7f48-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="e7f48-106">Führt eine Anweisungs Liste einmal oder mehrmals aus, je nach while-oder until-Bedingung.</span><span class="sxs-lookup"><span data-stu-id="e7f48-106">Runs a statement list one or more times, subject to a While or Until condition.</span></span>

## <a name="long-description"></a><span data-ttu-id="e7f48-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e7f48-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="e7f48-108">Das do-Schlüsselwort funktioniert mit dem while-Schlüsselwort oder dem until-Schlüsselwort, um die Anweisungen in einem Skriptblock auszuführen, je nach Bedingung.</span><span class="sxs-lookup"><span data-stu-id="e7f48-108">The Do keyword works with the While keyword or the Until keyword to run the statements in a script block, subject to a condition.</span></span> <span data-ttu-id="e7f48-109">Anders als bei der zugehörigen while-Schleife wird der Skriptblock in einer Do-Schleife immer mindestens einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e7f48-109">Unlike the related While loop, the script block in a Do loop always runs at least once.</span></span>

<span data-ttu-id="e7f48-110">Eine **do-while-** Schleife ist eine Vielzahl der while-Schleife.</span><span class="sxs-lookup"><span data-stu-id="e7f48-110">A **Do-While** loop is a variety of the While loop.</span></span> <span data-ttu-id="e7f48-111">In einer **do-while-** Schleife wird die Bedingung ausgewertet, nachdem der Skriptblock ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e7f48-111">In a **Do-While** loop, the condition is evaluated after the script block has run.</span></span> <span data-ttu-id="e7f48-112">Wie in einer while-Schleife wird der Skriptblock wiederholt, solange die Bedingung als true ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="e7f48-112">As in a While loop, the script block is repeated as long as the condition evaluates to true.</span></span>

<span data-ttu-id="e7f48-113">Wie eine **do-while-** Schleife wird eine **Do-Until-** Schleife immer mindestens einmal ausgeführt, bevor die Bedingung ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="e7f48-113">Like a **Do-While** loop, a **Do-Until** loop always runs at least once before the condition is evaluated.</span></span> <span data-ttu-id="e7f48-114">Der Skriptblock wird jedoch nur ausgeführt, während die Bedingung false ist.</span><span class="sxs-lookup"><span data-stu-id="e7f48-114">However, the script block runs only while the condition is false.</span></span>

<span data-ttu-id="e7f48-115">Die Schlüsselwörter für die Fluss Steuerung " *Continue* " und " *break* " können in einer **do-while-** Schleife oder in einer **Do-Until-** Schleife verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7f48-115">The *Continue* and *Break* flow control keywords can be used in a **Do-While** loop or in a **Do-Until** loop.</span></span>

### <a name="syntax"></a><span data-ttu-id="e7f48-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7f48-116">Syntax</span></span>

<span data-ttu-id="e7f48-117">Das folgende Beispiel zeigt die Syntax der **do-while-** Anweisung:</span><span class="sxs-lookup"><span data-stu-id="e7f48-117">The following shows the syntax of the **Do-While** statement:</span></span>

```powershell
do {<statement list>} while (<condition>)
```

<span data-ttu-id="e7f48-118">Das folgende Beispiel zeigt die Syntax der **Do-Until-** Anweisung:</span><span class="sxs-lookup"><span data-stu-id="e7f48-118">The following shows the syntax of the **Do-Until** statement:</span></span>

```powershell
do {<statement list>} until (<condition>)
```

<span data-ttu-id="e7f48-119">Die Anweisungs Liste enthält eine oder mehrere-Anweisungen, die jedes Mal ausgeführt werden, wenn die Schleife eingegeben oder wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="e7f48-119">The statement list contains one or more statements that run each time the loop is entered or repeated.</span></span>

<span data-ttu-id="e7f48-120">Der Bedingungs Teil der-Anweisung wird in true oder false aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="e7f48-120">The condition portion of the statement resolves to true or false.</span></span>

### <a name="example"></a><span data-ttu-id="e7f48-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7f48-121">Example</span></span>

<span data-ttu-id="e7f48-122">Das folgende Beispiel einer Do-Anweisung zählt die Elemente in einem Array, bis Sie ein Element mit dem Wert 0 erreicht.</span><span class="sxs-lookup"><span data-stu-id="e7f48-122">The following example of a Do statement counts the items in an array until it reaches an item with a value of 0.</span></span>

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } while ($x[$a] -ne 0)
C:\PS> $count
3
```

<span data-ttu-id="e7f48-123">Im folgenden Beispiel wird das until-Schlüsselwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="e7f48-123">The following example uses the Until keyword.</span></span> <span data-ttu-id="e7f48-124">Beachten Sie, dass der ungleich-Operator ( `-ne` ) durch den Gleichheits Operator () ersetzt wird `-eq` .</span><span class="sxs-lookup"><span data-stu-id="e7f48-124">Notice that the not equal to operator (`-ne`) is replaced by the equal to operator (`-eq`).</span></span>

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } until ($x[$a] -eq 0)
C:\PS> $count
3
```

<span data-ttu-id="e7f48-125">Im folgenden Beispiel werden alle Werte eines Arrays geschrieben, wobei jeder Wert übersprungen wird, der kleiner als 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="e7f48-125">The following example writes all the values of an array, skipping any value that is less than zero.</span></span>

```powershell
do {
  if ($x[$a] -lt 0) { continue }
  Write-Host $x[$a]
}
while (++$a -lt 10)
```

## <a name="see-also"></a><span data-ttu-id="e7f48-126">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="e7f48-126">SEE ALSO</span></span>

[<span data-ttu-id="e7f48-127">about_While</span><span class="sxs-lookup"><span data-stu-id="e7f48-127">about_While</span></span>](about_While.md)

[<span data-ttu-id="e7f48-128">about_Operators</span><span class="sxs-lookup"><span data-stu-id="e7f48-128">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="e7f48-129">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="e7f48-129">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="e7f48-130">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="e7f48-130">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="e7f48-131">about_Break</span><span class="sxs-lookup"><span data-stu-id="e7f48-131">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="e7f48-132">about_Continue</span><span class="sxs-lookup"><span data-stu-id="e7f48-132">about_Continue</span></span>](about_Continue.md)
