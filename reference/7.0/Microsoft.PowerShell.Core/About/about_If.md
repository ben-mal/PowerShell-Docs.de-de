---
description: Beschreibt einen Sprachbefehl, den Sie verwenden können, um Anweisungs Listen basierend auf den Ergebnissen von einem oder mehreren bedingten Tests auszuführen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_If
ms.openlocfilehash: f5bda1b3530c104361dba12de029219a5dd0db60
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222260"
---
# <a name="about-if"></a><span data-ttu-id="7f885-104">Informationen zu if</span><span class="sxs-lookup"><span data-stu-id="7f885-104">About If</span></span>

## <a name="short-description"></a><span data-ttu-id="7f885-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7f885-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="7f885-106">Beschreibt einen Sprachbefehl, den Sie verwenden können, um Anweisungs Listen basierend auf den Ergebnissen von einem oder mehreren bedingten Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7f885-106">Describes a language command you can use to run statement lists based on the results of one or more conditional tests.</span></span>

## <a name="long-description"></a><span data-ttu-id="7f885-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7f885-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="7f885-108">Sie können die- `If` Anweisung verwenden, um Code Blöcke auszuführen, wenn für einen angegebenen bedingten Test true ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="7f885-108">You can use the `If` statement to run code blocks if a specified conditional test evaluates to true.</span></span> <span data-ttu-id="7f885-109">Sie können auch einen oder mehrere zusätzliche bedingte Tests angeben, die ausgeführt werden sollen, wenn alle vorherigen Tests als false ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="7f885-109">You can also specify one or more additional conditional tests to run if all the prior tests evaluate to false.</span></span> <span data-ttu-id="7f885-110">Schließlich können Sie einen zusätzlichen Codeblock angeben, der ausgeführt wird, wenn kein anderer vorheriger bedingter Test zu true ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="7f885-110">Finally, you can specify an additional code block that is run if no other prior conditional test evaluates to true.</span></span>

### <a name="syntax"></a><span data-ttu-id="7f885-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f885-111">Syntax</span></span>

<span data-ttu-id="7f885-112">Das folgende Beispiel zeigt die `If` Syntax der Anweisung:</span><span class="sxs-lookup"><span data-stu-id="7f885-112">The following example shows the `If` statement syntax:</span></span>

```powershell
if (<test1>)
    {<statement list 1>}
[elseif (<test2>)
    {<statement list 2>}]
[else
    {<statement list 3>}]
```

<span data-ttu-id="7f885-113">Wenn Sie eine- `If` Anweisung ausführen, wertet PowerShell den `<test1>` bedingten Ausdruck als "true" oder "false" aus.</span><span class="sxs-lookup"><span data-stu-id="7f885-113">When you run an `If` statement, PowerShell evaluates the `<test1>` conditional expression as true or false.</span></span> <span data-ttu-id="7f885-114">Wenn `<test1>` true ist, wird ausgeführt `<statement list 1>` , und PowerShell beendet die- `If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7f885-114">If `<test1>` is true, `<statement list 1>` runs, and PowerShell exits the `If` statement.</span></span> <span data-ttu-id="7f885-115">Wenn `<test1>` den Wert false hat, wertet PowerShell die durch die `<test2>` bedingte Anweisung angegebene Bedingung aus.</span><span class="sxs-lookup"><span data-stu-id="7f885-115">If `<test1>` is false, PowerShell evaluates the condition specified by the `<test2>` conditional statement.</span></span>

<span data-ttu-id="7f885-116">Wenn `<test2>` true ist, wird ausgeführt `<statement list 2>` , und PowerShell beendet die- `If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7f885-116">If `<test2>` is true, `<statement list 2>` runs, and PowerShell exits the `If` statement.</span></span> <span data-ttu-id="7f885-117">Wenn sowohl `<test1>` als auch als `<test2>` false ausgewertet wird, wird der `<statement list 3`> Codeblock ausgeführt, und PowerShell beendet die if-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7f885-117">If both `<test1>` and `<test2>` evaluate to false, the `<statement list 3`> code block runs, and PowerShell exits the If statement.</span></span>

<span data-ttu-id="7f885-118">Sie können mehrere ElseIf-Anweisungen verwenden, um eine Reihe von bedingten Tests zu verketten.</span><span class="sxs-lookup"><span data-stu-id="7f885-118">You can use multiple Elseif statements to chain a series of conditional tests.</span></span> <span data-ttu-id="7f885-119">Daher wird jeder Test nur ausgeführt, wenn alle vorherigen Tests false sind.</span><span class="sxs-lookup"><span data-stu-id="7f885-119">So, that each test is run only if all the previous tests are false.</span></span>
<span data-ttu-id="7f885-120">Wenn Sie eine-Anweisung erstellen müssen, `If` die viele ElseIf-Anweisungen enthält, sollten Sie stattdessen eine Switch-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f885-120">If you need to create an `If` statement that contains many Elseif statements, consider using a Switch statement instead.</span></span>

<span data-ttu-id="7f885-121">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="7f885-121">Examples:</span></span>

<span data-ttu-id="7f885-122">Die einfachste `If` Anweisung enthält einen einzelnen Befehl, der keine ElseIf-Anweisungen oder andere Anweisungen enthält.</span><span class="sxs-lookup"><span data-stu-id="7f885-122">The simplest `If` statement contains a single command and does not contain any Elseif statements or any Else statements.</span></span> <span data-ttu-id="7f885-123">Das folgende Beispiel zeigt die einfachste Form der- `If` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="7f885-123">The following example shows the simplest form of the `If` statement:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
```

<span data-ttu-id="7f885-124">Wenn die $a Variable in diesem Beispiel größer als 2 ist, wird die Bedingung als "true" ausgewertet, und die Anweisungs Liste wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f885-124">In this example, if the $a variable is greater than 2, the condition evaluates to true, and the statement list runs.</span></span> <span data-ttu-id="7f885-125">Wenn $a jedoch kleiner oder gleich 2 ist oder keine vorhandene Variable ist, `If` zeigt die Anweisung keine Meldung an.</span><span class="sxs-lookup"><span data-stu-id="7f885-125">However, if $a is less than or equal to 2 or is not an existing variable, the `If` statement does not display a message.</span></span>

<span data-ttu-id="7f885-126">Wenn eine Else-Anweisung hinzugefügt wird, wird eine Meldung angezeigt, wenn $a kleiner oder gleich 2 ist.</span><span class="sxs-lookup"><span data-stu-id="7f885-126">By adding an Else statement, a message is displayed when $a is less than or equal to 2.</span></span> <span data-ttu-id="7f885-127">Das nächste Beispiel zeigt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7f885-127">As the next example shows:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
else {
    Write-Host ("The value $a is less than or equal to 2," +
        " is not created or is not initialized.")
}
```

<span data-ttu-id="7f885-128">Zum weiteren verfeinern dieses Beispiels können Sie die ElseIf-Anweisung verwenden, um eine Meldung anzuzeigen, wenn der Wert von $a gleich 2 ist.</span><span class="sxs-lookup"><span data-stu-id="7f885-128">To further refine this example, you can use the Elseif statement to display a message when the value of $a is equal to 2.</span></span> <span data-ttu-id="7f885-129">Das nächste Beispiel zeigt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7f885-129">As the next example shows:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
elseif ($a -eq 2) {
    Write-Host "The value $a is equal to 2."
}
else {
    Write-Host ("The value $a is less than 2 or" +
        " was not created or initialized.")
}
```

### <a name="using-the-ternary-operator-syntax"></a><span data-ttu-id="7f885-130">Verwenden der ternären Operator Syntax</span><span class="sxs-lookup"><span data-stu-id="7f885-130">Using the ternary operator syntax</span></span>

<span data-ttu-id="7f885-131">PowerShell 7,0 hat mit dem ternären Operator eine neue Syntax eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7f885-131">PowerShell 7.0 introduced a new syntax using the ternary operator.</span></span> <span data-ttu-id="7f885-132">Er folgt der c#-Syntax für Ternäre Operatoren:</span><span class="sxs-lookup"><span data-stu-id="7f885-132">It follows the C# ternary operator syntax:</span></span>

```Syntax
<condition> ? <if-true> : <if-false>
```

<span data-ttu-id="7f885-133">Der ternäre Operator verhält sich wie die vereinfachte- `if-else` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7f885-133">The ternary operator behaves like the simplified `if-else` statement.</span></span> <span data-ttu-id="7f885-134">Der `<condition>` Ausdruck wird ausgewertet, und das Ergebnis wird in einen booleschen Wert konvertiert, um zu bestimmen, welcher Branch als nächstes ausgewertet werden soll:</span><span class="sxs-lookup"><span data-stu-id="7f885-134">The `<condition>` expression is evaluated and the result is converted to a boolean to determine which branch should be evaluated next:</span></span>

- <span data-ttu-id="7f885-135">Der Ausdruck `<if-true>` wird ausgeführt, wenn der Ausdruck `<condition>` TRUE ist.</span><span class="sxs-lookup"><span data-stu-id="7f885-135">The `<if-true>` expression is executed if the `<condition>` expression is true</span></span>
- <span data-ttu-id="7f885-136">Der Ausdruck `<if-false>` wird ausgeführt, wenn der Ausdruck `<condition>` FALSE ist.</span><span class="sxs-lookup"><span data-stu-id="7f885-136">The `<if-false>` expression is executed if the `<condition>` expression is false</span></span>

<span data-ttu-id="7f885-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7f885-137">For example:</span></span>

```powershell
$message = (Test-Path $path) ? "Path exists" : "Path not found"
```

<span data-ttu-id="7f885-138">In diesem Beispiel ist der Wert von `$message` "Path vorhanden", wenn `Test-Path` zurückgibt `$true` .</span><span class="sxs-lookup"><span data-stu-id="7f885-138">In this example, the value of `$message` is "Path exists" when `Test-Path` returns `$true`.</span></span> <span data-ttu-id="7f885-139">Wenn `Test-Path` zurückgibt `$false` , lautet der Wert von `$message` "Pfad nicht gefunden".</span><span class="sxs-lookup"><span data-stu-id="7f885-139">When `Test-Path` returns `$false`, the value of `$message` is "Path not found".</span></span>

```powershell
$service = Get-Service BITS
$service.Status -eq 'Running' ? (Stop-Service $service) : (Start-Service $service)
```

<span data-ttu-id="7f885-140">Wenn der Dienst in diesem Beispiel ausgeführt wird, wird er beendet, und wenn sein Status nicht **ausgeführt** wird, wird er gestartet.</span><span class="sxs-lookup"><span data-stu-id="7f885-140">In this example, if the service is running, it is stopped, and if its status is not **Running** , it is started.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f885-141">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="7f885-141">SEE ALSO</span></span>

[<span data-ttu-id="7f885-142">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="7f885-142">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="7f885-143">about_Switch</span><span class="sxs-lookup"><span data-stu-id="7f885-143">about_Switch</span></span>](about_Switch.md)
