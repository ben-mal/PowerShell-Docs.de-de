---
description: Beschreibt eine sprach Anweisung, mit der Sie einen Befehls Block auf der Grundlage der Ergebnisse eines bedingten Tests ausführen können.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_while?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_While
ms.openlocfilehash: 0adc435eeba6b07e1f16aec5dd1328ddd80c4612
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221044"
---
# <a name="about-while"></a><span data-ttu-id="57820-104">Ungefähr while</span><span class="sxs-lookup"><span data-stu-id="57820-104">About While</span></span>

## <a name="short-description"></a><span data-ttu-id="57820-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="57820-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="57820-106">Beschreibt eine sprach Anweisung, mit der Sie einen Befehls Block auf der Grundlage der Ergebnisse eines bedingten Tests ausführen können.</span><span class="sxs-lookup"><span data-stu-id="57820-106">Describes a language statement that you can use to run a command block based on the results of a conditional test.</span></span>

## <a name="long-description"></a><span data-ttu-id="57820-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="57820-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="57820-108">Bei der while-Anweisung (auch als while-Schleife bezeichnet) handelt es sich um ein Sprachkonstrukt zum Erstellen einer Schleife, die Befehle in einem Befehls Block ausführt, solange ein bedingter Test als true ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="57820-108">The While statement (also known as a While loop) is a language construct for creating a loop that runs commands in a command block as long as a conditional test evaluates to true.</span></span> <span data-ttu-id="57820-109">Die while-Anweisung ist einfacher zu konstruieren als eine for-Anweisung, da die Syntax weniger kompliziert ist.</span><span class="sxs-lookup"><span data-stu-id="57820-109">The While statement is easier to construct than a For statement because its syntax is less complicated.</span></span> <span data-ttu-id="57820-110">Außerdem ist er flexibler als die foreach-Anweisung, da Sie einen bedingten Test in der while-Anweisung angeben, um zu steuern, wie oft die Schleife ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="57820-110">In addition, it is more flexible than the Foreach statement because you specify a conditional test in the While statement to control how many times the loop runs.</span></span>

<span data-ttu-id="57820-111">Das folgende Beispiel zeigt die Syntax der while-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="57820-111">The following shows the While statement syntax:</span></span>

```powershell
while (<condition>){<statement list>}
```

<span data-ttu-id="57820-112">Wenn Sie eine while-Anweisung ausführen, wertet PowerShell den `<condition>` Abschnitt der Anweisung aus, bevor Sie in den `<statement list>` Abschnitt wechseln.</span><span class="sxs-lookup"><span data-stu-id="57820-112">When you run a While statement, PowerShell evaluates the `<condition>` section of the statement before entering the `<statement list>` section.</span></span> <span data-ttu-id="57820-113">Der Bedingungs Teil der-Anweisung wird entweder in true oder false aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="57820-113">The condition portion of the statement resolves to either true or false.</span></span> <span data-ttu-id="57820-114">Solange die Bedingung weiterhin zutrifft, führt PowerShell den Abschnitt erneut aus `<statement list>` .</span><span class="sxs-lookup"><span data-stu-id="57820-114">As long as the condition remains true, PowerShell reruns the `<statement list>` section.</span></span>

<span data-ttu-id="57820-115">Der- `<statement list>` Abschnitt der-Anweisung enthält mindestens einen Befehl, der jedes Mal ausgeführt wird, wenn die Schleife eingegeben oder wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="57820-115">The `<statement list>` section of the statement contains one or more commands that are run each time the loop is entered or repeated.</span></span>

<span data-ttu-id="57820-116">In der folgenden while-Anweisung werden z. b. die Zahlen 1 bis 3 angezeigt, wenn die $Val Variable nicht erstellt wurde oder wenn die $Val Variable erstellt und mit 0 initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="57820-116">For example, the following While statement displays the numbers 1 through 3 if the $val variable has not been created or if the $val variable has been created and initialized to 0.</span></span>

```powershell
while($val -ne 3)
{
    $val++
    Write-Host $val
}
```

<span data-ttu-id="57820-117">In diesem Beispiel ist die Bedingung ($Val nicht gleich 3), die $Val \= 0, 1, 2.</span><span class="sxs-lookup"><span data-stu-id="57820-117">In this example, the condition ($val is not equal to 3) is true while $val \= 0, 1, 2.</span></span> <span data-ttu-id="57820-118">Jedes Mal, wenn die Schleife durchlaufen wird, wird $Val mit dem \+ \+ unären Inkrementoperator ($Val) um 1 erhöht \+ \+ .</span><span class="sxs-lookup"><span data-stu-id="57820-118">Each time through the loop, $val is incremented by 1 using the \+\+ unary increment operator ($val\+\+).</span></span> <span data-ttu-id="57820-119">Das letzte Mal durch die Schleife, $Val \= 3.</span><span class="sxs-lookup"><span data-stu-id="57820-119">The last time through the loop, $val \= 3.</span></span> <span data-ttu-id="57820-120">Wenn $Val 3 entspricht, wird die Bedingungs Anweisung als false ausgewertet, und die Schleife wird beendet.</span><span class="sxs-lookup"><span data-stu-id="57820-120">When $val equals 3, the condition statement evaluates to false, and the loop exits.</span></span>

<span data-ttu-id="57820-121">Wenn Sie diesen Befehl an der PowerShell-Eingabeaufforderung bequem schreiben möchten, können Sie ihn wie folgt eingeben:</span><span class="sxs-lookup"><span data-stu-id="57820-121">To conveniently write this command at the PowerShell command prompt, you can enter it in the following way:</span></span>

```powershell
while($val -ne 3){$val++; Write-Host $val}
```

<span data-ttu-id="57820-122">Beachten Sie, dass das Semikolon den ersten Befehl, der 1 hinzufügt, $Val aus dem zweiten Befehl trennt, der den Wert $Val in die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="57820-122">Notice that the semicolon separates the first command that adds 1 to $val from the second command that writes the value of $val to the console.</span></span>

## <a name="see-also"></a><span data-ttu-id="57820-123">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="57820-123">SEE ALSO</span></span>

[<span data-ttu-id="57820-124">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="57820-124">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="57820-125">about_Do</span><span class="sxs-lookup"><span data-stu-id="57820-125">about_Do</span></span>](about_Do.md)

[<span data-ttu-id="57820-126">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="57820-126">about_Foreach</span></span>](about_Foreach.md)

[<span data-ttu-id="57820-127">about_For</span><span class="sxs-lookup"><span data-stu-id="57820-127">about_For</span></span>](about_For.md)

[<span data-ttu-id="57820-128">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="57820-128">about_Language_Keywords</span></span>](about_Language_Keywords.md)
