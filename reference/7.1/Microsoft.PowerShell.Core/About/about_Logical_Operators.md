---
description: Beschreibt die Operatoren, die-Anweisungen in PowerShell verbinden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logical_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logical_Operators
ms.openlocfilehash: f8db290b87043451241613358a2f6d4fdf1dc342
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220447"
---
# <a name="about_logical_operators"></a><span data-ttu-id="ef477-104">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="ef477-104">about_Logical_Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="ef477-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ef477-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="ef477-106">Beschreibt die Operatoren, die-Anweisungen in PowerShell verbinden.</span><span class="sxs-lookup"><span data-stu-id="ef477-106">Describes the operators that connect statements in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="ef477-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ef477-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="ef477-108">Die logischen PowerShell-Operatoren verbinden Ausdrücke und Anweisungen, sodass Sie einen einzelnen Ausdruck verwenden können, um mehrere Bedingungen zu testen.</span><span class="sxs-lookup"><span data-stu-id="ef477-108">The PowerShell logical operators connect expressions and statements, allowing you to use a single expression to test for multiple conditions.</span></span>

<span data-ttu-id="ef477-109">Beispielsweise verwendet die folgende Anweisung den and-Operator und den or-Operator, um drei bedingte Anweisungen zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="ef477-109">For example, the following statement uses the and operator and the or operator to connect three conditional statements.</span></span> <span data-ttu-id="ef477-110">Die-Anweisung ist nur dann true, wenn der Wert von $a größer als der Wert $b ist und entweder $a oder $b kleiner als ist.</span><span class="sxs-lookup"><span data-stu-id="ef477-110">The statement is true only when the value of $a is greater than the value of $b, and either $a or $b is less than</span></span>
20.

```powershell
($a -gt $b) -and (($a -lt 20) -or ($b -lt 20))
```

<span data-ttu-id="ef477-111">PowerShell unterstützt die folgenden logischen Operatoren.</span><span class="sxs-lookup"><span data-stu-id="ef477-111">PowerShell supports the following logical operators.</span></span>

|<span data-ttu-id="ef477-112">Operator</span><span class="sxs-lookup"><span data-stu-id="ef477-112">Operator</span></span>|<span data-ttu-id="ef477-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ef477-113">Description</span></span>                        |<span data-ttu-id="ef477-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef477-114">Example</span></span>                   |
|--------|-----------------------------------|--------------------------|
|`-and`  |<span data-ttu-id="ef477-115">Logisches AND.</span><span class="sxs-lookup"><span data-stu-id="ef477-115">Logical AND.</span></span> <span data-ttu-id="ef477-116">TRUE, wenn beide</span><span class="sxs-lookup"><span data-stu-id="ef477-116">TRUE when both</span></span>        |`(1 -eq 1) -and (1 -eq 2)`|
|        |<span data-ttu-id="ef477-117">-Anweisungen sind "true".</span><span class="sxs-lookup"><span data-stu-id="ef477-117">statements are TRUE.</span></span>               |`False`                   |
|`-or`   |<span data-ttu-id="ef477-118">Logisches OR.</span><span class="sxs-lookup"><span data-stu-id="ef477-118">Logical OR.</span></span> <span data-ttu-id="ef477-119">TRUE, wenn beide</span><span class="sxs-lookup"><span data-stu-id="ef477-119">TRUE when either</span></span>       |`(1 -eq 1) -or (1 -eq 2)` |
|        |<span data-ttu-id="ef477-120">die Anweisung ist "true".</span><span class="sxs-lookup"><span data-stu-id="ef477-120">statement is TRUE.</span></span>                 |`True`                    |
|`-xor`  |<span data-ttu-id="ef477-121">Logisches exklusives OR.</span><span class="sxs-lookup"><span data-stu-id="ef477-121">Logical EXCLUSIVE OR.</span></span> <span data-ttu-id="ef477-122">TRUE, wenn</span><span class="sxs-lookup"><span data-stu-id="ef477-122">TRUE when</span></span>    |`(1 -eq 1) -xor (2 -eq 2)`|
|        |<span data-ttu-id="ef477-123">nur eine Anweisung ist "true".</span><span class="sxs-lookup"><span data-stu-id="ef477-123">only one statement is TRUE</span></span>         |`False`                   |
|`-not`  |<span data-ttu-id="ef477-124">Logisches Not.</span><span class="sxs-lookup"><span data-stu-id="ef477-124">Logical not.</span></span> <span data-ttu-id="ef477-125">Negiert die Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ef477-125">Negates the statement</span></span> |`-not (1 -eq 1)`          |
|        |<span data-ttu-id="ef477-126">Das folgt.</span><span class="sxs-lookup"><span data-stu-id="ef477-126">that follows.</span></span>                      |`False`                   |
|`!`     |<span data-ttu-id="ef477-127">Identisch mit `-not`</span><span class="sxs-lookup"><span data-stu-id="ef477-127">Same as `-not`</span></span>                     |`!(1 -eq 1)`              |
|        |                                   |`False`                   |

 <span data-ttu-id="ef477-128">Hinweis:</span><span class="sxs-lookup"><span data-stu-id="ef477-128">Note:</span></span>

<span data-ttu-id="ef477-129">In den vorherigen Beispielen wird auch der Gleichheits Operator verwendet `-eq` .</span><span class="sxs-lookup"><span data-stu-id="ef477-129">The previous examples also use the equal to comparison operator `-eq`.</span></span> <span data-ttu-id="ef477-130">Weitere Informationen finden Sie unter [about_Comparison_Operators](about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="ef477-130">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span> <span data-ttu-id="ef477-131">In den Beispielen werden auch die booleschen Werte von Ganzzahlen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ef477-131">The examples also use the Boolean values of integers.</span></span> <span data-ttu-id="ef477-132">Die Ganzzahl 0 hat den Wert false.</span><span class="sxs-lookup"><span data-stu-id="ef477-132">The integer 0 has a value of FALSE.</span></span> <span data-ttu-id="ef477-133">Alle anderen Ganzzahlen haben den Wert "true".</span><span class="sxs-lookup"><span data-stu-id="ef477-133">All other integers have a value of TRUE.</span></span>

<span data-ttu-id="ef477-134">Die Syntax der logischen Operatoren lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ef477-134">The syntax of the logical operators is as follows:</span></span>

```
<statement> {-AND | -OR | -XOR} <statement>
{! | -NOT} <statement>
```

<span data-ttu-id="ef477-135">Anweisungen, die die logischen Operatoren verwenden, geben boolesche Werte (true oder false) zurück.</span><span class="sxs-lookup"><span data-stu-id="ef477-135">Statements that use the logical operators return Boolean (TRUE or FALSE) values.</span></span>

<span data-ttu-id="ef477-136">Die logischen Operatoren von PowerShell Werten nur die Anweisungen aus, die erforderlich sind, um den Wahrheitswert der Anweisung zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ef477-136">The PowerShell logical operators evaluate only the statements required to determine the truth value of the statement.</span></span> <span data-ttu-id="ef477-137">Wenn der linke Operand in einer-Anweisung, die den and-Operator enthält, false ist, wird der rechte Operand nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="ef477-137">If the left operand in a statement that contains the and operator is FALSE, the right operand is not evaluated.</span></span>
<span data-ttu-id="ef477-138">Wenn der linke Operand in einer-Anweisung, die die-oder-Anweisung enthält, true ist, wird der rechte Operand nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="ef477-138">If the left operand in a statement that contains the or statement is TRUE, the right operand is not evaluated.</span></span> <span data-ttu-id="ef477-139">Daher können Sie diese Anweisungen auf die gleiche Weise wie die- `If` Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef477-139">As a result, you can use these statements in the same way that you would use the `If` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef477-140">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="ef477-140">SEE ALSO</span></span>

[<span data-ttu-id="ef477-141">about_Operators</span><span class="sxs-lookup"><span data-stu-id="ef477-141">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="ef477-142">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="ef477-142">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)

[<span data-ttu-id="ef477-143">about_Comparison_operators</span><span class="sxs-lookup"><span data-stu-id="ef477-143">about_Comparison_operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="ef477-144">about_If</span><span class="sxs-lookup"><span data-stu-id="ef477-144">about_If</span></span>](about_If.md)

