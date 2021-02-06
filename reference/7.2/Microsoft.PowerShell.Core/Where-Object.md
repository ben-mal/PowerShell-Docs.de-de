---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Where-Object
ms.openlocfilehash: 667a503d67ac9a9a0f41187cbac079d946247618
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603118"
---
# <span data-ttu-id="876b2-102">Where-Object</span><span class="sxs-lookup"><span data-stu-id="876b2-102">Where-Object</span></span>

## <span data-ttu-id="876b2-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="876b2-103">SYNOPSIS</span></span>
<span data-ttu-id="876b2-104">Wählt Objekte aus einer Auflistung basierend auf ihren Eigenschaftswerten aus.</span><span class="sxs-lookup"><span data-stu-id="876b2-104">Selects objects from a collection based on their property values.</span></span>

## <span data-ttu-id="876b2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="876b2-105">SYNTAX</span></span>

### <span data-ttu-id="876b2-106">Equalset (Standard)</span><span class="sxs-lookup"><span data-stu-id="876b2-106">EqualSet (Default)</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-EQ]
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-107">Scriptblockset</span><span class="sxs-lookup"><span data-stu-id="876b2-107">ScriptBlockSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-FilterScript] <ScriptBlock> [<CommonParameters>]
```

### <span data-ttu-id="876b2-108">Matchset</span><span class="sxs-lookup"><span data-stu-id="876b2-108">MatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Match
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-109">Casesensitiveequalset</span><span class="sxs-lookup"><span data-stu-id="876b2-109">CaseSensitiveEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CEQ
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-110">Notequalset</span><span class="sxs-lookup"><span data-stu-id="876b2-110">NotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NE
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-111">Casesensitivenotequalset</span><span class="sxs-lookup"><span data-stu-id="876b2-111">CaseSensitiveNotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNE
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-112">Greaterthanset</span><span class="sxs-lookup"><span data-stu-id="876b2-112">GreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GT
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-113">Casesensitivegreaterthanset</span><span class="sxs-lookup"><span data-stu-id="876b2-113">CaseSensitiveGreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGT
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-114">Lessthanset</span><span class="sxs-lookup"><span data-stu-id="876b2-114">LessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LT
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-115">Casesensitiveless thanset</span><span class="sxs-lookup"><span data-stu-id="876b2-115">CaseSensitiveLessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLT
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-116">Greaterorequalset</span><span class="sxs-lookup"><span data-stu-id="876b2-116">GreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GE
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-117">Casesensitivegreaterorequalset</span><span class="sxs-lookup"><span data-stu-id="876b2-117">CaseSensitiveGreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGE
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-118">Lessorequalset</span><span class="sxs-lookup"><span data-stu-id="876b2-118">LessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LE
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-119">Casesensitivelesorequalset</span><span class="sxs-lookup"><span data-stu-id="876b2-119">CaseSensitiveLessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLE
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-120">Likeset</span><span class="sxs-lookup"><span data-stu-id="876b2-120">LikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Like
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-121">Casesensitivelikeset</span><span class="sxs-lookup"><span data-stu-id="876b2-121">CaseSensitiveLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLike
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-122">Notlikeset</span><span class="sxs-lookup"><span data-stu-id="876b2-122">NotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotLike
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-123">Casesensitivenotlikeset</span><span class="sxs-lookup"><span data-stu-id="876b2-123">CaseSensitiveNotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotLike
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-124">Casesensitivematchset</span><span class="sxs-lookup"><span data-stu-id="876b2-124">CaseSensitiveMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CMatch
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-125">Notmatchset</span><span class="sxs-lookup"><span data-stu-id="876b2-125">NotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-126">Casesensitivenotmatchset</span><span class="sxs-lookup"><span data-stu-id="876b2-126">CaseSensitiveNotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-127">Kontainsset</span><span class="sxs-lookup"><span data-stu-id="876b2-127">ContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Contains
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-128">Casesensitivekontainsset</span><span class="sxs-lookup"><span data-stu-id="876b2-128">CaseSensitiveContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CContains
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-129">Notkontainsset</span><span class="sxs-lookup"><span data-stu-id="876b2-129">NotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotContains
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-130">Casesensitivenotkontainsset</span><span class="sxs-lookup"><span data-stu-id="876b2-130">CaseSensitiveNotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotContains
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-131">Einfügen</span><span class="sxs-lookup"><span data-stu-id="876b2-131">InSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -In
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-132">Casesensitiveinset</span><span class="sxs-lookup"><span data-stu-id="876b2-132">CaseSensitiveInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CIn
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-133">Notinset</span><span class="sxs-lookup"><span data-stu-id="876b2-133">NotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotIn
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-134">Casesensitivenotinset</span><span class="sxs-lookup"><span data-stu-id="876b2-134">CaseSensitiveNotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotIn
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-135">Isset</span><span class="sxs-lookup"><span data-stu-id="876b2-135">IsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Is
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-136">Isnotset</span><span class="sxs-lookup"><span data-stu-id="876b2-136">IsNotSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -IsNot
 [<CommonParameters>]
```

### <span data-ttu-id="876b2-137">Not</span><span class="sxs-lookup"><span data-stu-id="876b2-137">Not</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> -Not [<CommonParameters>]
```

## <span data-ttu-id="876b2-138">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="876b2-138">DESCRIPTION</span></span>

<span data-ttu-id="876b2-139">Das `Where-Object` Cmdlet wählt Objekte aus, die bestimmte Eigenschaftswerte aus der Auflistung von-Objekten aufweisen, die an das Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="876b2-139">The `Where-Object` cmdlet selects objects that have particular property values from the collection of objects that are passed to it.</span></span> <span data-ttu-id="876b2-140">Beispielsweise können Sie mit dem `Where-Object` Cmdlet Dateien auswählen, die nach einem bestimmten Datum erstellt wurden, Ereignisse mit einer bestimmten ID oder Computer, auf denen eine bestimmte Version von Windows verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="876b2-140">For example, you can use the `Where-Object` cmdlet to select files that were created after a certain date, events with a particular ID, or computers that use a particular version of Windows.</span></span>

<span data-ttu-id="876b2-141">Ab Windows PowerShell 3,0 gibt es zwei verschiedene Möglichkeiten, einen Befehl zu erstellen `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="876b2-141">Starting in Windows PowerShell 3.0, there are two different ways to construct a `Where-Object` command.</span></span>

- <span data-ttu-id="876b2-142">**Skriptblock**.</span><span class="sxs-lookup"><span data-stu-id="876b2-142">**Script block**.</span></span> <span data-ttu-id="876b2-143">Sie können einen Skriptblock verwenden, um den Namen der Eigenschaft, einen Vergleichsoperator und einen Eigenschaftswert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="876b2-143">You can use a script block to specify the property name, a comparison operator, and a property value.</span></span> <span data-ttu-id="876b2-144">`Where-Object` Gibt alle-Objekte zurück, für die die script Block-Anweisung den Wert true hat.</span><span class="sxs-lookup"><span data-stu-id="876b2-144">`Where-Object` returns all objects for which the script block statement is true.</span></span>

  <span data-ttu-id="876b2-145">Beispielsweise ruft der folgende Befehl Prozesse in der normalen Prioritäts Klasse ab, d. h. Prozesse, bei denen der Wert der **PriorityClass** -Eigenschaft Normal ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-145">For example, the following command gets processes in the Normal priority class, that is, processes where the value of the **PriorityClass** property equals Normal.</span></span>

  `Get-Process | Where-Object {$_.PriorityClass -eq "Normal"}`

  <span data-ttu-id="876b2-146">Alle PowerShell-Vergleichs Operatoren sind im Skriptblock Format gültig.</span><span class="sxs-lookup"><span data-stu-id="876b2-146">All PowerShell comparison operators are valid in the script block format.</span></span> <span data-ttu-id="876b2-147">Weitere Informationen zu Vergleichs Operatoren finden Sie unter [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="876b2-147">For more information about comparison operators, see [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span></span>

- <span data-ttu-id="876b2-148">**Vergleichs Anweisung**.</span><span class="sxs-lookup"><span data-stu-id="876b2-148">**Comparison statement**.</span></span> <span data-ttu-id="876b2-149">Sie können auch eine Vergleichsanweisung schreiben, was der natürlichen Sprache sehr viel ähnlicher ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-149">You can also write a comparison statement, which is much more like natural language.</span></span> <span data-ttu-id="876b2-150">Vergleichsanweisungen wurden in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-150">Comparison statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="876b2-151">Beispielsweise werden mit den folgenden Befehlen auch Prozesse mit der Prioritäts Klasse "Normal" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="876b2-151">For example, the following commands also get processes that have a priority class of Normal.</span></span> <span data-ttu-id="876b2-152">Diese Befehle sind gleichwertig und austauschbar.</span><span class="sxs-lookup"><span data-stu-id="876b2-152">These commands are equivalent and can be used interchangeably.</span></span>

  `Get-Process | Where-Object -Property PriorityClass -eq -Value "Normal"`

  `Get-Process | Where-Object PriorityClass -eq "Normal"`

  <span data-ttu-id="876b2-153">Ab Windows PowerShell 3,0 `Where-Object` fügt Vergleichs Operatoren als Parameter in einem `Where-Object` Befehl hinzu.</span><span class="sxs-lookup"><span data-stu-id="876b2-153">Starting in Windows PowerShell 3.0, `Where-Object` adds comparison operators as parameters in a `Where-Object` command.</span></span> <span data-ttu-id="876b2-154">Sofern nicht anders angegeben, wird bei allen Operatoren die Groß-und Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="876b2-154">Unless specified, all operators are case-insensitive.</span></span> <span data-ttu-id="876b2-155">Vor Windows PowerShell 3,0 konnten die Vergleichs Operatoren in der PowerShell-Sprache nur in Skript Blöcken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="876b2-155">Prior to Windows PowerShell 3.0, the comparison operators in the PowerShell language could be used only in script blocks.</span></span>

<span data-ttu-id="876b2-156">Wenn Sie eine einzelne **Eigenschaft** für angeben `Where-Object` , wird der Wert der Eigenschaft als boolescher Ausdruck behandelt.</span><span class="sxs-lookup"><span data-stu-id="876b2-156">When you provide a single **Property** to `Where-Object`, the value of the property is treated as a boolean expression.</span></span> <span data-ttu-id="876b2-157">Wenn der Wert von **length** nicht 0 (null) ist, wird der Ausdruck als **true** ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="876b2-157">When the value of **Length** is not zero, the expression evaluates to **True**.</span></span> <span data-ttu-id="876b2-158">Beispiel: `('hi', '', 'there') | Where-Object Length`</span><span class="sxs-lookup"><span data-stu-id="876b2-158">For example: `('hi', '', 'there') | Where-Object Length`</span></span>

<span data-ttu-id="876b2-159">Das vorherige Beispiel ist funktional äquivalent zu:</span><span class="sxs-lookup"><span data-stu-id="876b2-159">The previous example is functionally equivalent to:</span></span>

- `('hi', '', 'there') | Where-Object Length -GT 0`
- `('hi', '', 'there') | Where-Object {$_.Length -gt 0}`

## <span data-ttu-id="876b2-160">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="876b2-160">EXAMPLES</span></span>

### <span data-ttu-id="876b2-161">Beispiel 1: erhalten von beendeten Diensten</span><span class="sxs-lookup"><span data-stu-id="876b2-161">Example 1: Get stopped services</span></span>

<span data-ttu-id="876b2-162">Mit diesen Befehlen wird eine Liste aller Dienste angezeigt, die zurzeit beendet sind.</span><span class="sxs-lookup"><span data-stu-id="876b2-162">These commands get a list of all services that are currently stopped.</span></span> <span data-ttu-id="876b2-163">Die `$_` Automatische Variable stellt jedes Objekt dar, das an das `Where-Object` Cmdlet übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="876b2-163">The `$_` automatic variable represents each object that is passed to the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="876b2-164">Der erste Befehl verwendet das Skriptblock Format, der zweite Befehl verwendet das Vergleichs Anweisungs Format.</span><span class="sxs-lookup"><span data-stu-id="876b2-164">The first command uses the script block format, the second command uses the comparison statement format.</span></span> <span data-ttu-id="876b2-165">Diese Befehle sind gleichwertig und austauschbar.</span><span class="sxs-lookup"><span data-stu-id="876b2-165">The commands are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Stopped"}
Get-Service | where Status -eq "Stopped"
```

### <span data-ttu-id="876b2-166">Beispiel 2: erhalten von Prozessen basierend auf dem Workingset</span><span class="sxs-lookup"><span data-stu-id="876b2-166">Example 2: Get processes based on working set</span></span>

<span data-ttu-id="876b2-167">Mit diesen Befehlen werden Prozesse aufgelistet, die über ein Workingset verfügen, das größer ist als 250 Megabyte (KB).</span><span class="sxs-lookup"><span data-stu-id="876b2-167">These commands list processes that have a working set greater than 250 megabytes (KB).</span></span> <span data-ttu-id="876b2-168">Die ScriptBlock-und die-Anweisungs Syntax sind gleichwertig und können austauschbar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="876b2-168">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -GT 250MB}
Get-Process | Where-Object WorkingSet -GT (250MB)
```

### <span data-ttu-id="876b2-169">Beispiel 3: erhalten von Prozessen basierend auf dem Prozessnamen</span><span class="sxs-lookup"><span data-stu-id="876b2-169">Example 3: Get processes based on process name</span></span>

<span data-ttu-id="876b2-170">Mit diesen Befehlen werden die Prozesse mit einem **ProcessName** -Eigenschafts Wert, der mit dem Buchstaben beginnt, angezeigt `p` .</span><span class="sxs-lookup"><span data-stu-id="876b2-170">These commands get the processes that have a **ProcessName** property value that begins with the letter `p`.</span></span> <span data-ttu-id="876b2-171">Mit dem **Match** -Operator können Sie reguläre Ausdrucks Übereinstimmungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="876b2-171">The **Match** operator lets you use regular expression matches.</span></span>

<span data-ttu-id="876b2-172">Die ScriptBlock-und die-Anweisungs Syntax sind gleichwertig und können austauschbar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="876b2-172">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.ProcessName -Match "^p.*"}
Get-Process | Where-Object ProcessName -Match "^p.*"
```

### <span data-ttu-id="876b2-173">Beispiel 4: Verwenden des Vergleichs Anweisungs Formats</span><span class="sxs-lookup"><span data-stu-id="876b2-173">Example 4: Use the comparison statement format</span></span>

<span data-ttu-id="876b2-174">In diesem Beispiel wird gezeigt, wie das neue Vergleichs Anweisungs Format des `Where-Object` Cmdlets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="876b2-174">This example shows how to use the new comparison statement format of the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="876b2-175">Der erste Befehl verwendet das Vergleichsanweisungsformat.</span><span class="sxs-lookup"><span data-stu-id="876b2-175">The first command uses the comparison statement format.</span></span>
<span data-ttu-id="876b2-176">In diesem Befehl werden keine Aliase verwendet, und alle Parameter enthalten den Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="876b2-176">In this command, no aliases are used and all parameters include the parameter name.</span></span>

<span data-ttu-id="876b2-177">Der zweite Befehl stellt eine natürlichere Verwendung des Vergleichsbefehlsformats dar.</span><span class="sxs-lookup"><span data-stu-id="876b2-177">The second command is the more natural use of the comparison command format.</span></span> <span data-ttu-id="876b2-178">Der `where` Alias wird durch den `Where-Object` Cmdlet-Namen ersetzt, und alle optionalen Parameternamen werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="876b2-178">The `where` alias is substituted for the `Where-Object` cmdlet name and all optional parameter names are omitted.</span></span>

```powershell
Get-Process | Where-Object -Property Handles -GE -Value 1000
Get-Process | where Handles -GE 1000
```

### <span data-ttu-id="876b2-179">Beispiel 5: Get-Befehle basierend auf Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="876b2-179">Example 5: Get commands based on properties</span></span>

<span data-ttu-id="876b2-180">In diesem Beispiel wird veranschaulicht, wie Sie Befehle schreiben können, mit denen Elemente zurückgegeben werden, die „true“ oder „false“ sind oder die einen beliebigen Wert für eine angegebene Eigenschaft aufweisen.</span><span class="sxs-lookup"><span data-stu-id="876b2-180">This example shows how to write commands that return items that are true or false or have any value for a specified property.</span></span> <span data-ttu-id="876b2-181">Jedes Beispiel zeigt sowohl den Skriptblock als auch Vergleichs Anweisungs Formate für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="876b2-181">Each example shows both the script block and comparison statement formats for the command.</span></span>

```powershell
# Use Where-Object to get commands that have any value for the OutputType property of the command.
# This omits commands that do not have an OutputType property and those that have an OutputType property, but no property value.
Get-Command | where OutputType
Get-Command | where {$_.OutputType}
```

```powershell
# Use Where-Object to get objects that are containers.
# This gets objects that have the **PSIsContainer** property with a value of $True and excludes all others.
Get-ChildItem | where PSIsContainer
Get-ChildItem | where {$_.PSIsContainer}
```

```powershell
# Finally, use the Not operator (!) to get objects that are not containers.
# This gets objects that do have the **PSIsContainer** property and those that have a value of $False for the **PSIsContainer** property.
Get-ChildItem | where {!$_.PSIsContainer}
# You cannot use the Not operator (!) in the comparison statement format of the command.
Get-ChildItem | where PSIsContainer -eq $False
```

### <span data-ttu-id="876b2-182">Beispiel 6: Verwenden mehrerer Bedingungen</span><span class="sxs-lookup"><span data-stu-id="876b2-182">Example 6: Use multiple conditions</span></span>

```powershell
Get-Module -ListAvailable | where {($_.Name -notlike "Microsoft*" -and $_.Name -notlike "PS*") -and $_.HelpInfoUri}
```

<span data-ttu-id="876b2-183">Dieses Beispiel zeigt, wie Sie einen `Where-Object` Befehl mit mehreren Bedingungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="876b2-183">This example shows how to create a `Where-Object` command with multiple conditions.</span></span>

<span data-ttu-id="876b2-184">Dieser Befehl ruft Nicht-Kern-Module ab, die die aktualisierbare Hilfefunktion unterstützen.</span><span class="sxs-lookup"><span data-stu-id="876b2-184">This command gets non-core modules that support the Updatable Help feature.</span></span> <span data-ttu-id="876b2-185">Der Befehl verwendet den **listavailable** -Parameter des `Get-Module` Cmdlets, um alle Module auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="876b2-185">The command uses the **ListAvailable** parameter of the `Get-Module` cmdlet to get all modules on the computer.</span></span> <span data-ttu-id="876b2-186">Ein Pipeline Operator ( `|` ) sendet die Module an das `Where-Object` Cmdlet, das Module abruft, deren Namen nicht mit Microsoft oder PS beginnen, und einen Wert für die **helpinfouri** -Eigenschaft hat, der PowerShell mitteilt, wo aktualisierte Hilfedateien für das Modul zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="876b2-186">A pipeline operator (`|`) sends the modules to the `Where-Object` cmdlet, which gets modules whose names do not begin with Microsoft or PS, and have a value for the **HelpInfoURI** property, which tells PowerShell where to find updated help files for the module.</span></span> <span data-ttu-id="876b2-187">Die Vergleichs Anweisungen werden durch den logischen **and-** Operator miteinander verbunden.</span><span class="sxs-lookup"><span data-stu-id="876b2-187">The comparison statements are connected by the **And** logical operator.</span></span>

<span data-ttu-id="876b2-188">Im Beispiel wird das Skriptblock-Befehlsformat verwendet.</span><span class="sxs-lookup"><span data-stu-id="876b2-188">The example uses the script block command format.</span></span> <span data-ttu-id="876b2-189">Logische Operatoren, wie z. b. **and** und **or**, sind nur in Skript Blöcken gültig.</span><span class="sxs-lookup"><span data-stu-id="876b2-189">Logical operators, such as **And** and **Or**, are valid only in script blocks.</span></span> <span data-ttu-id="876b2-190">Sie können Sie nicht im Vergleichs Anweisungs Format eines `Where-Object` Befehls verwenden.</span><span class="sxs-lookup"><span data-stu-id="876b2-190">You cannot use them in the comparison statement format of a `Where-Object` command.</span></span>

- <span data-ttu-id="876b2-191">Weitere Informationen zu logischen PowerShell-Operatoren finden Sie unter [about_Logical_Operators](./About/about_logical_operators.md).</span><span class="sxs-lookup"><span data-stu-id="876b2-191">For more information about PowerShell logical operators, see [about_Logical_Operators](./About/about_logical_operators.md).</span></span>
- <span data-ttu-id="876b2-192">Weitere Informationen zur aktualisierbaren Hilfe Funktion finden Sie unter [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="876b2-192">For more information about the Updatable Help feature, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

## <span data-ttu-id="876b2-193">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="876b2-193">PARAMETERS</span></span>

### <span data-ttu-id="876b2-194">-Centhält</span><span class="sxs-lookup"><span data-stu-id="876b2-194">-CContains</span></span>

<span data-ttu-id="876b2-195">Gibt an, dass dieses Cmdlet Objekte aus einer Auflistung abruft, wenn der Eigenschafts Wert des Objekts eine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-195">Indicates that this cmdlet gets objects from a collection if the property value of the object is an exact match for the specified value.</span></span> <span data-ttu-id="876b2-196">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="876b2-196">This operation is case-sensitive.</span></span>

<span data-ttu-id="876b2-197">Beispiel: `Get-Process | where ProcessName -CContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="876b2-197">For example: `Get-Process | where ProcessName -CContains "svchost"`</span></span>

<span data-ttu-id="876b2-198">**CIS** bezieht sich auf eine Auflistung von Werten und ist true, wenn die Auflistung ein Element enthält, das eine genaue Entsprechung für den angegebenen Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="876b2-198">**CContains** refers to a collection of values and is true if the collection contains an item that is an exact match for the specified value.</span></span> <span data-ttu-id="876b2-199">Wenn die Eingabe ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="876b2-199">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="876b2-200">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-200">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-201">-Ceq</span><span class="sxs-lookup"><span data-stu-id="876b2-201">-CEQ</span></span>

<span data-ttu-id="876b2-202">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen Wert übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="876b2-202">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>
<span data-ttu-id="876b2-203">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="876b2-203">This operation is case-sensitive.</span></span>

<span data-ttu-id="876b2-204">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-204">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-205">-CGE</span><span class="sxs-lookup"><span data-stu-id="876b2-205">-CGE</span></span>

<span data-ttu-id="876b2-206">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert oder gleich dem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-206">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span> <span data-ttu-id="876b2-207">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="876b2-207">This operation is case-sensitive.</span></span>

<span data-ttu-id="876b2-208">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-209">-CGT</span><span class="sxs-lookup"><span data-stu-id="876b2-209">-CGT</span></span>

<span data-ttu-id="876b2-210">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-210">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>
<span data-ttu-id="876b2-211">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="876b2-211">This operation is case-sensitive.</span></span>

<span data-ttu-id="876b2-212">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-212">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-213">-CIN</span><span class="sxs-lookup"><span data-stu-id="876b2-213">-CIn</span></span>

<span data-ttu-id="876b2-214">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert den angegebenen Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="876b2-214">Indicates that this cmdlet gets objects if the property value includes the specified value.</span></span> <span data-ttu-id="876b2-215">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="876b2-215">This operation is case-sensitive.</span></span>

<span data-ttu-id="876b2-216">Beispiel: `Get-Process | where -Value "svchost" -CIn ProcessName`</span><span class="sxs-lookup"><span data-stu-id="876b2-216">For example: `Get-Process | where -Value "svchost" -CIn ProcessName`</span></span>

<span data-ttu-id="876b2-217">**CIN** ähnelt **Care**, mit dem Unterschied, dass die Eigenschaften-und Wert Positionen umgekehrt werden.</span><span class="sxs-lookup"><span data-stu-id="876b2-217">**CIn** resembles **CContains**, except that the property and value positions are reversed.</span></span> <span data-ttu-id="876b2-218">Die folgenden Anweisungen sind z. B. beide „true“.</span><span class="sxs-lookup"><span data-stu-id="876b2-218">For example, the following statements are both true.</span></span>

`"abc", "def" -CContains "abc"`

`"abc" -CIn "abc", "def"`

<span data-ttu-id="876b2-219">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-219">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-220">-CLE</span><span class="sxs-lookup"><span data-stu-id="876b2-220">-CLE</span></span>

<span data-ttu-id="876b2-221">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner oder gleich dem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-221">Indicates that this cmdlet gets objects if the property value is less-than or equal to the specified value.</span></span> <span data-ttu-id="876b2-222">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="876b2-222">This operation is case-sensitive.</span></span>

<span data-ttu-id="876b2-223">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-223">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-224">-Clike</span><span class="sxs-lookup"><span data-stu-id="876b2-224">-CLike</span></span>

<span data-ttu-id="876b2-225">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert einem Wert entspricht, der Platzhalter Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="876b2-225">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span> <span data-ttu-id="876b2-226">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="876b2-226">This operation is case-sensitive.</span></span>

<span data-ttu-id="876b2-227">Beispiel: `Get-Process | where ProcessName -CLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="876b2-227">For example: `Get-Process | where ProcessName -CLike "*host"`</span></span>

<span data-ttu-id="876b2-228">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-229">-CLT</span><span class="sxs-lookup"><span data-stu-id="876b2-229">-CLT</span></span>

<span data-ttu-id="876b2-230">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner als der angegebene Wert ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-230">Indicates that this cmdlet gets objects if the property value is less-than the specified value.</span></span> <span data-ttu-id="876b2-231">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="876b2-231">This operation is case-sensitive.</span></span>

<span data-ttu-id="876b2-232">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-232">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-233">-Cmatch</span><span class="sxs-lookup"><span data-stu-id="876b2-233">-CMatch</span></span>

<span data-ttu-id="876b2-234">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen regulären Ausdruck übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="876b2-234">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="876b2-235">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="876b2-235">This operation is case-sensitive.</span></span> <span data-ttu-id="876b2-236">Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="876b2-236">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="876b2-237">Beispiel: `Get-Process | where ProcessName -CMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="876b2-237">For example: `Get-Process | where ProcessName -CMatch "Shell"`</span></span>

<span data-ttu-id="876b2-238">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-238">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-239">-CNE</span><span class="sxs-lookup"><span data-stu-id="876b2-239">-CNE</span></span>

<span data-ttu-id="876b2-240">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert sich vom angegebenen Wert unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="876b2-240">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>
<span data-ttu-id="876b2-241">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="876b2-241">This operation is case-sensitive.</span></span>

<span data-ttu-id="876b2-242">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-242">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-243">-Cnotenthält</span><span class="sxs-lookup"><span data-stu-id="876b2-243">-CNotContains</span></span>

<span data-ttu-id="876b2-244">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert des Objekts keine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-244">Indicates that this cmdlet gets objects if the property value of the object is not an exact match for the specified value.</span></span> <span data-ttu-id="876b2-245">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="876b2-245">This operation is case-sensitive.</span></span>

<span data-ttu-id="876b2-246">Beispiel: `Get-Process | where ProcessName -CNotContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="876b2-246">For example: `Get-Process | where ProcessName -CNotContains "svchost"`</span></span>

<span data-ttu-id="876b2-247">**Notare** und **cnotenthält** Verweise auf eine Auflistung von Werten und sind true, wenn die Auflistung keine Elemente enthält, die eine genaue Entsprechung für den angegebenen Wert sind.</span><span class="sxs-lookup"><span data-stu-id="876b2-247">**NotContains** and **CNotContains** refer to a collection of values and are true when the collection does not contains any items that are an exact match for the specified value.</span></span> <span data-ttu-id="876b2-248">Wenn die Eingabe ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="876b2-248">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="876b2-249">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-249">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-250">-Cnotin</span><span class="sxs-lookup"><span data-stu-id="876b2-250">-CNotIn</span></span>

<span data-ttu-id="876b2-251">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert keine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-251">Indicates that this cmdlet gets objects if the property value is not an exact match for the specified value.</span></span> <span data-ttu-id="876b2-252">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="876b2-252">This operation is case-sensitive.</span></span>

<span data-ttu-id="876b2-253">Beispiel: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="876b2-253">For example: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span></span>

<span data-ttu-id="876b2-254">**NOTIN** -und **cnotin** -Operatoren ähneln **Notare** und **cnotare**, mit dem Unterschied, dass die Eigenschaften-und Wert Positionen umgekehrt werden.</span><span class="sxs-lookup"><span data-stu-id="876b2-254">**NotIn** and **CNotIn** operators resemble **NotContains** and **CNotContains**, except that the property and value positions are reversed.</span></span> <span data-ttu-id="876b2-255">Die folgenden Anweisungen sind z. B. „true“.</span><span class="sxs-lookup"><span data-stu-id="876b2-255">For example, the following statements are true.</span></span>

`"abc", "def" -CNotContains "Abc"`

`"abc" -CNotIn "Abc", "def"`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-256">-Cnotlike</span><span class="sxs-lookup"><span data-stu-id="876b2-256">-CNotLike</span></span>

<span data-ttu-id="876b2-257">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit einem Wert identisch ist, der Platzhalter Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="876b2-257">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span> <span data-ttu-id="876b2-258">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="876b2-258">This operation is case-sensitive.</span></span>

<span data-ttu-id="876b2-259">Beispiel: `Get-Process | where ProcessName -CNotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="876b2-259">For example: `Get-Process | where ProcessName -CNotLike "*host"`</span></span>

<span data-ttu-id="876b2-260">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-260">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-261">-Cnotmatch</span><span class="sxs-lookup"><span data-stu-id="876b2-261">-CNotMatch</span></span>

<span data-ttu-id="876b2-262">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit dem angegebenen regulären Ausdruck identisch ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-262">Indicates that this cmdlet gets objects if the property value does not match the specified regular expression.</span></span> <span data-ttu-id="876b2-263">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="876b2-263">This operation is case-sensitive.</span></span> <span data-ttu-id="876b2-264">Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="876b2-264">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="876b2-265">Beispiel: `Get-Process | where ProcessName -CNotMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="876b2-265">For example: `Get-Process | where ProcessName -CNotMatch "Shell"`</span></span>

<span data-ttu-id="876b2-266">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-266">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-267">-Enthält</span><span class="sxs-lookup"><span data-stu-id="876b2-267">-Contains</span></span>

<span data-ttu-id="876b2-268">Gibt an, dass dieses Cmdlet Objekte abruft, wenn ein Element im Eigenschafts Wert des Objekts eine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-268">Indicates that this cmdlet gets objects if any item in the property value of the object is an exact match for the specified value.</span></span>

<span data-ttu-id="876b2-269">Beispiel: `Get-Process | where ProcessName -Contains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="876b2-269">For example: `Get-Process | where ProcessName -Contains "Svchost"`</span></span>

<span data-ttu-id="876b2-270">Wenn der Eigenschafts Wert ein einzelnes Objekt enthält, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="876b2-270">If the property value contains a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="876b2-271">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainsSet
Aliases: IContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-272">-EQ</span><span class="sxs-lookup"><span data-stu-id="876b2-272">-EQ</span></span>

<span data-ttu-id="876b2-273">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen Wert übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="876b2-273">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>

<span data-ttu-id="876b2-274">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-274">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EqualSet
Aliases: IEQ

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-275">-Filterscript</span><span class="sxs-lookup"><span data-stu-id="876b2-275">-FilterScript</span></span>

<span data-ttu-id="876b2-276">Gibt den Skriptblock an, der zum Filtern der Objekte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="876b2-276">Specifies the script block that is used to filter the objects.</span></span> <span data-ttu-id="876b2-277">Schließen Sie den Skriptblock in geschweifte Klammern ( `{}` ) ein.</span><span class="sxs-lookup"><span data-stu-id="876b2-277">Enclose the script block in braces (`{}`).</span></span>

<span data-ttu-id="876b2-278">Der Parameter Name, **Filterscript**, ist optional.</span><span class="sxs-lookup"><span data-stu-id="876b2-278">The parameter name, **FilterScript**, is optional.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-279">-GE</span><span class="sxs-lookup"><span data-stu-id="876b2-279">-GE</span></span>

<span data-ttu-id="876b2-280">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert oder gleich dem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-280">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span>

<span data-ttu-id="876b2-281">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-281">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterOrEqualSet
Aliases: IGE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-282">-GT</span><span class="sxs-lookup"><span data-stu-id="876b2-282">-GT</span></span>

<span data-ttu-id="876b2-283">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-283">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>

<span data-ttu-id="876b2-284">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-284">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterThanSet
Aliases: IGT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-285">-In</span><span class="sxs-lookup"><span data-stu-id="876b2-285">-In</span></span>

<span data-ttu-id="876b2-286">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit einem der angegebenen Werte übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="876b2-286">Indicates that this cmdlet gets objects if the property value matches any of the specified values.</span></span>
<span data-ttu-id="876b2-287">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="876b2-287">For example:</span></span>

`Get-Process | where -Property ProcessName -in -Value "Svchost", "TaskHost", "WsmProvHost"`

<span data-ttu-id="876b2-288">Wenn der Wert des **value** -Parameters ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="876b2-288">If the value of the **Value** parameter is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="876b2-289">Wenn der Eigenschafts Wert eines Objekts ein Array ist, verwendet PowerShell die Verweis Gleichheit, um eine Übereinstimmung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="876b2-289">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="876b2-290">`Where-Object` Gibt das-Objekt nur dann zurück, wenn der Wert des **Property** -Parameters und der Wert des **Werts** dieselbe Instanz eines Objekts sind.</span><span class="sxs-lookup"><span data-stu-id="876b2-290">`Where-Object` returns the object only if the value of the **Property** parameter and any value of **Value** are the same instance of an object.</span></span>

<span data-ttu-id="876b2-291">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-291">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InSet
Aliases: IIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-292">-InputObject</span><span class="sxs-lookup"><span data-stu-id="876b2-292">-InputObject</span></span>

<span data-ttu-id="876b2-293">Gibt das zu filternde Objekt an.</span><span class="sxs-lookup"><span data-stu-id="876b2-293">Specifies the objects to be filtered.</span></span> <span data-ttu-id="876b2-294">Sie können die Objekte auch über die Pipeline an übergeben `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="876b2-294">You can also pipe the objects to `Where-Object`.</span></span>

<span data-ttu-id="876b2-295">Wenn Sie den **Inputobject** -Parameter mit verwenden `Where-Object` , anstatt Befehls Ergebnisse an zu übergeben `Where-Object` , wird der **Inputobject** -Wert als einzelnes Objekt behandelt.</span><span class="sxs-lookup"><span data-stu-id="876b2-295">When you use the **InputObject** parameter with `Where-Object`, instead of piping command results to `Where-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="876b2-296">Dies gilt auch, wenn der Wert eine Auflistung ist, die das Ergebnis eines Befehls ist, z `-InputObject (Get-Process)` . b..</span><span class="sxs-lookup"><span data-stu-id="876b2-296">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span> <span data-ttu-id="876b2-297">Da **Inputobject** keine einzelnen Eigenschaften aus einem Array oder einer Auflistung von Objekten zurückgeben kann, wird empfohlen, dass `Where-Object` Sie in der Pipeline verwenden, wenn Sie zum Filtern einer Auflistung von Objekten für Objekte verwenden, die bestimmte Werte in definierten Eigenschaften aufweisen, `Where-Object` wie in den Beispielen in diesem Thema gezeigt.</span><span class="sxs-lookup"><span data-stu-id="876b2-297">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that, if you use `Where-Object` to filter a collection of objects for those objects that have specific values in defined properties, you use `Where-Object` in the pipeline, as shown in the examples in this topic.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-298">-Ist</span><span class="sxs-lookup"><span data-stu-id="876b2-298">-Is</span></span>

<span data-ttu-id="876b2-299">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert eine Instanz des angegebenen .net-Typs ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-299">Indicates that this cmdlet gets objects if the property value is an instance of the specified .NET type.</span></span> <span data-ttu-id="876b2-300">Schließen Sie den Typnamen in eckige Klammern ein.</span><span class="sxs-lookup"><span data-stu-id="876b2-300">Enclose the type name in square brackets.</span></span>

<span data-ttu-id="876b2-301">Beispiel: `Get-Process | where StartTime -Is [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="876b2-301">For example, `Get-Process | where StartTime -Is [DateTime]`</span></span>

<span data-ttu-id="876b2-302">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-302">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-303">-IsNot</span><span class="sxs-lookup"><span data-stu-id="876b2-303">-IsNot</span></span>

<span data-ttu-id="876b2-304">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert keine Instanz des angegebenen .net-Typs ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-304">Indicates that this cmdlet gets objects if the property value is not an instance of the specified .NET type.</span></span>

<span data-ttu-id="876b2-305">Beispiel: `Get-Process | where StartTime -IsNot [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="876b2-305">For example, `Get-Process | where StartTime -IsNot [DateTime]`</span></span>

<span data-ttu-id="876b2-306">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-306">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsNotSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-307">-Le</span><span class="sxs-lookup"><span data-stu-id="876b2-307">-LE</span></span>

<span data-ttu-id="876b2-308">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner oder gleich dem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-308">Indicates that this cmdlet gets objects if the property value is less than or equal to the specified value.</span></span>

<span data-ttu-id="876b2-309">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-309">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessOrEqualSet
Aliases: ILE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-310">-Like</span><span class="sxs-lookup"><span data-stu-id="876b2-310">-Like</span></span>

<span data-ttu-id="876b2-311">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert einem Wert entspricht, der Platzhalter Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="876b2-311">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span>

<span data-ttu-id="876b2-312">Beispiel: `Get-Process | where ProcessName -Like "*host"`</span><span class="sxs-lookup"><span data-stu-id="876b2-312">For example: `Get-Process | where ProcessName -Like "*host"`</span></span>

<span data-ttu-id="876b2-313">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-313">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LikeSet
Aliases: ILike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-314">-LT</span><span class="sxs-lookup"><span data-stu-id="876b2-314">-LT</span></span>

<span data-ttu-id="876b2-315">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner als der angegebene Wert ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-315">Indicates that this cmdlet gets objects if the property value is less than the specified value.</span></span>

<span data-ttu-id="876b2-316">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-316">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessThanSet
Aliases: ILT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-317">-Match</span><span class="sxs-lookup"><span data-stu-id="876b2-317">-Match</span></span>

<span data-ttu-id="876b2-318">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen regulären Ausdruck übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="876b2-318">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="876b2-319">Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="876b2-319">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="876b2-320">Beispiel: `Get-Process | where ProcessName -Match "shell"`</span><span class="sxs-lookup"><span data-stu-id="876b2-320">For example: `Get-Process | where ProcessName -Match "shell"`</span></span>

<span data-ttu-id="876b2-321">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-321">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MatchSet
Aliases: IMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-322">-NE</span><span class="sxs-lookup"><span data-stu-id="876b2-322">-NE</span></span>

<span data-ttu-id="876b2-323">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert sich vom angegebenen Wert unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="876b2-323">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>

<span data-ttu-id="876b2-324">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-324">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotEqualSet
Aliases: INE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-325">-Not</span><span class="sxs-lookup"><span data-stu-id="876b2-325">-Not</span></span>

<span data-ttu-id="876b2-326">Gibt an, dass dieses Cmdlet Objekte abruft, wenn die Eigenschaft nicht vorhanden ist oder den Wert NULL oder false aufweist.</span><span class="sxs-lookup"><span data-stu-id="876b2-326">Indicates that this cmdlet gets objects if the property does not exist or has a value of null or false.</span></span>

<span data-ttu-id="876b2-327">Beispiel: `Get-Service | where -Not "DependentServices"`</span><span class="sxs-lookup"><span data-stu-id="876b2-327">For example: `Get-Service | where -Not "DependentServices"`</span></span>

<span data-ttu-id="876b2-328">Dieser Parameter wurde in Windows PowerShell 6,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-328">This parameter was introduced in Windows PowerShell 6.1.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Not
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-329">-Notenthält</span><span class="sxs-lookup"><span data-stu-id="876b2-329">-NotContains</span></span>

<span data-ttu-id="876b2-330">Gibt an, dass dieses Cmdlet Objekte abruft, wenn keines der Elemente im Eigenschafts Wert eine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-330">Indicates that this cmdlet gets objects if none of the items in the property value is an exact match for the specified value.</span></span>

<span data-ttu-id="876b2-331">Beispiel: `Get-Process | where ProcessName -NotContains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="876b2-331">For example: `Get-Process | where ProcessName -NotContains "Svchost"`</span></span>

<span data-ttu-id="876b2-332">**Notare** verweist auf eine Auflistung von Werten und ist true, wenn die Auflistung keine Elemente enthält, die eine genaue Entsprechung für den angegebenen Wert sind.</span><span class="sxs-lookup"><span data-stu-id="876b2-332">**NotContains** refers to a collection of values and is true if the collection does not contain any items that are an exact match for the specified value.</span></span> <span data-ttu-id="876b2-333">Wenn die Eingabe ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="876b2-333">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="876b2-334">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-334">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotContainsSet
Aliases: INotContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-335">-NOTIN</span><span class="sxs-lookup"><span data-stu-id="876b2-335">-NotIn</span></span>

<span data-ttu-id="876b2-336">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert keine genaue Entsprechung für einen der angegebenen Werte ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-336">Indicates that this cmdlet gets objects if the property value is not an exact match for any of the specified values.</span></span>

<span data-ttu-id="876b2-337">Beispiel: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="876b2-337">For example: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span></span>

<span data-ttu-id="876b2-338">Wenn der Wert von **value** ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="876b2-338">If the value of **Value** is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="876b2-339">Wenn der Eigenschafts Wert eines Objekts ein Array ist, verwendet PowerShell die Verweis Gleichheit, um eine Übereinstimmung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="876b2-339">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="876b2-340">`Where-Object` Gibt das-Objekt nur dann zurück, wenn der Wert der- **Eigenschaft** und der Wert des **Werts** nicht dieselbe Instanz eines-Objekts sind.</span><span class="sxs-lookup"><span data-stu-id="876b2-340">`Where-Object` returns the object only if the value of **Property** and any value of **Value** are not the same instance of an object.</span></span>

<span data-ttu-id="876b2-341">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-341">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotInSet
Aliases: INotIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-342">-Notlike</span><span class="sxs-lookup"><span data-stu-id="876b2-342">-NotLike</span></span>

<span data-ttu-id="876b2-343">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit einem Wert identisch ist, der Platzhalter Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="876b2-343">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span>

<span data-ttu-id="876b2-344">Beispiel: `Get-Process | where ProcessName -NotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="876b2-344">For example: `Get-Process | where ProcessName -NotLike "*host"`</span></span>

<span data-ttu-id="876b2-345">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-345">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotLikeSet
Aliases: INotLike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-346">-Notmatch</span><span class="sxs-lookup"><span data-stu-id="876b2-346">-NotMatch</span></span>

<span data-ttu-id="876b2-347">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit dem angegebenen regulären Ausdruck identisch ist.</span><span class="sxs-lookup"><span data-stu-id="876b2-347">Indicates that this cmdlet gets objects when the property value does not match the specified regular expression.</span></span> <span data-ttu-id="876b2-348">Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="876b2-348">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="876b2-349">Beispiel: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span><span class="sxs-lookup"><span data-stu-id="876b2-349">For example: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span></span>

<span data-ttu-id="876b2-350">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-350">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotMatchSet
Aliases: INotMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-351">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="876b2-351">-Property</span></span>

<span data-ttu-id="876b2-352">Gibt den Namen einer Objekteigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="876b2-352">Specifies the name of an object property.</span></span> <span data-ttu-id="876b2-353">Der Parameter Name " **Property**" ist optional.</span><span class="sxs-lookup"><span data-stu-id="876b2-353">The parameter name, **Property**, is optional.</span></span>

<span data-ttu-id="876b2-354">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-354">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: EqualSet, LessOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet, Not
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="876b2-355">-Value</span><span class="sxs-lookup"><span data-stu-id="876b2-355">-Value</span></span>

<span data-ttu-id="876b2-356">Gibt einen Eigenschaftswert an.</span><span class="sxs-lookup"><span data-stu-id="876b2-356">Specifies a property value.</span></span> <span data-ttu-id="876b2-357">Der Parameter Name, **value**, ist optional.</span><span class="sxs-lookup"><span data-stu-id="876b2-357">The parameter name, **Value**, is optional.</span></span> <span data-ttu-id="876b2-358">Dieser Parameter akzeptiert Platzhalter Zeichen, wenn er mit den folgenden vergleichsparametern verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="876b2-358">This parameter accepts wildcard characters when used with the following comparison parameters:</span></span>

- <span data-ttu-id="876b2-359">**Clike**</span><span class="sxs-lookup"><span data-stu-id="876b2-359">**CLike**</span></span>
- <span data-ttu-id="876b2-360">**Cnotlike**</span><span class="sxs-lookup"><span data-stu-id="876b2-360">**CNotLike**</span></span>
- <span data-ttu-id="876b2-361">**mögen**</span><span class="sxs-lookup"><span data-stu-id="876b2-361">**Like**</span></span>
- <span data-ttu-id="876b2-362">**NotLike**</span><span class="sxs-lookup"><span data-stu-id="876b2-362">**NotLike**</span></span>

<span data-ttu-id="876b2-363">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="876b2-363">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: EqualSet, LessOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="876b2-364">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="876b2-364">CommonParameters</span></span>

<span data-ttu-id="876b2-365">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="876b2-365">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="876b2-366">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="876b2-366">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="876b2-367">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="876b2-367">INPUTS</span></span>

### <span data-ttu-id="876b2-368">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="876b2-368">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="876b2-369">Sie können die Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="876b2-369">You can pipe the objects to this cmdlet.</span></span>

## <span data-ttu-id="876b2-370">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="876b2-370">OUTPUTS</span></span>

### <span data-ttu-id="876b2-371">Object</span><span class="sxs-lookup"><span data-stu-id="876b2-371">Object</span></span>

<span data-ttu-id="876b2-372">Mit diesem Cmdlet werden ausgewählte Elemente aus dem Eingabe Objekt Satz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="876b2-372">This cmdlet returns selected items from the input object set.</span></span>

## <span data-ttu-id="876b2-373">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="876b2-373">NOTES</span></span>

<span data-ttu-id="876b2-374">Ab Windows PowerShell 4,0 `Where` wurden-und-Methoden für die Verwendung mit-Auflistungen `ForEach` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="876b2-374">Starting in Windows PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span>

<span data-ttu-id="876b2-375">Weitere Informationen zu diesen neuen Methoden finden Sie hier [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="876b2-375">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="876b2-376">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="876b2-376">RELATED LINKS</span></span>

[<span data-ttu-id="876b2-377">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="876b2-377">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="876b2-378">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="876b2-378">ForEach-Object</span></span>](ForEach-Object.md)

[<span data-ttu-id="876b2-379">Group-Object</span><span class="sxs-lookup"><span data-stu-id="876b2-379">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="876b2-380">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="876b2-380">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="876b2-381">New-Object</span><span class="sxs-lookup"><span data-stu-id="876b2-381">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="876b2-382">Select-Object</span><span class="sxs-lookup"><span data-stu-id="876b2-382">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="876b2-383">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="876b2-383">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="876b2-384">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="876b2-384">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)

