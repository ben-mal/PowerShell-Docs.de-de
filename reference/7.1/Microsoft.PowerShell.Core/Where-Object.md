---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Where-Object
ms.openlocfilehash: b5f4a64cceffa1f4f9884bb4de3211e129871ba7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217628"
---
# <span data-ttu-id="dbae9-103">Where-Object</span><span class="sxs-lookup"><span data-stu-id="dbae9-103">Where-Object</span></span>

## <span data-ttu-id="dbae9-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="dbae9-104">SYNOPSIS</span></span>
<span data-ttu-id="dbae9-105">Wählt Objekte aus einer Auflistung basierend auf ihren Eigenschaftswerten aus.</span><span class="sxs-lookup"><span data-stu-id="dbae9-105">Selects objects from a collection based on their property values.</span></span>

## <span data-ttu-id="dbae9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dbae9-106">SYNTAX</span></span>

### <span data-ttu-id="dbae9-107">Equalset (Standard)</span><span class="sxs-lookup"><span data-stu-id="dbae9-107">EqualSet (Default)</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-EQ]
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-108">Scriptblockset</span><span class="sxs-lookup"><span data-stu-id="dbae9-108">ScriptBlockSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-FilterScript] <ScriptBlock> [<CommonParameters>]
```

### <span data-ttu-id="dbae9-109">Matchset</span><span class="sxs-lookup"><span data-stu-id="dbae9-109">MatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Match
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-110">Casesensitiveequalset</span><span class="sxs-lookup"><span data-stu-id="dbae9-110">CaseSensitiveEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CEQ
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-111">Notequalset</span><span class="sxs-lookup"><span data-stu-id="dbae9-111">NotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NE
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-112">Casesensitivenotequalset</span><span class="sxs-lookup"><span data-stu-id="dbae9-112">CaseSensitiveNotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNE
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-113">Greaterthanset</span><span class="sxs-lookup"><span data-stu-id="dbae9-113">GreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GT
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-114">Casesensitivegreaterthanset</span><span class="sxs-lookup"><span data-stu-id="dbae9-114">CaseSensitiveGreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGT
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-115">Lessthanset</span><span class="sxs-lookup"><span data-stu-id="dbae9-115">LessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LT
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-116">Casesensitiveless thanset</span><span class="sxs-lookup"><span data-stu-id="dbae9-116">CaseSensitiveLessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLT
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-117">Greaterorequalset</span><span class="sxs-lookup"><span data-stu-id="dbae9-117">GreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GE
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-118">Casesensitivegreaterorequalset</span><span class="sxs-lookup"><span data-stu-id="dbae9-118">CaseSensitiveGreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGE
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-119">Lessorequalset</span><span class="sxs-lookup"><span data-stu-id="dbae9-119">LessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LE
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-120">Casesensitivelesorequalset</span><span class="sxs-lookup"><span data-stu-id="dbae9-120">CaseSensitiveLessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLE
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-121">Likeset</span><span class="sxs-lookup"><span data-stu-id="dbae9-121">LikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Like
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-122">Casesensitivelikeset</span><span class="sxs-lookup"><span data-stu-id="dbae9-122">CaseSensitiveLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLike
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-123">Notlikeset</span><span class="sxs-lookup"><span data-stu-id="dbae9-123">NotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotLike
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-124">Casesensitivenotlikeset</span><span class="sxs-lookup"><span data-stu-id="dbae9-124">CaseSensitiveNotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotLike
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-125">Casesensitivematchset</span><span class="sxs-lookup"><span data-stu-id="dbae9-125">CaseSensitiveMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CMatch
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-126">Notmatchset</span><span class="sxs-lookup"><span data-stu-id="dbae9-126">NotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-127">Casesensitivenotmatchset</span><span class="sxs-lookup"><span data-stu-id="dbae9-127">CaseSensitiveNotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-128">Kontainsset</span><span class="sxs-lookup"><span data-stu-id="dbae9-128">ContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Contains
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-129">Casesensitivekontainsset</span><span class="sxs-lookup"><span data-stu-id="dbae9-129">CaseSensitiveContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CContains
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-130">Notkontainsset</span><span class="sxs-lookup"><span data-stu-id="dbae9-130">NotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotContains
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-131">Casesensitivenotkontainsset</span><span class="sxs-lookup"><span data-stu-id="dbae9-131">CaseSensitiveNotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotContains
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-132">Einfügen</span><span class="sxs-lookup"><span data-stu-id="dbae9-132">InSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -In
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-133">Casesensitiveinset</span><span class="sxs-lookup"><span data-stu-id="dbae9-133">CaseSensitiveInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CIn
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-134">Notinset</span><span class="sxs-lookup"><span data-stu-id="dbae9-134">NotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotIn
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-135">Casesensitivenotinset</span><span class="sxs-lookup"><span data-stu-id="dbae9-135">CaseSensitiveNotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotIn
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-136">Isset</span><span class="sxs-lookup"><span data-stu-id="dbae9-136">IsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Is
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-137">Isnotset</span><span class="sxs-lookup"><span data-stu-id="dbae9-137">IsNotSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -IsNot
 [<CommonParameters>]
```

### <span data-ttu-id="dbae9-138">Not</span><span class="sxs-lookup"><span data-stu-id="dbae9-138">Not</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> -Not [<CommonParameters>]
```

## <span data-ttu-id="dbae9-139">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dbae9-139">DESCRIPTION</span></span>

<span data-ttu-id="dbae9-140">Das `Where-Object` Cmdlet wählt Objekte aus, die bestimmte Eigenschaftswerte aus der Auflistung von-Objekten aufweisen, die an das Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="dbae9-140">The `Where-Object` cmdlet selects objects that have particular property values from the collection of objects that are passed to it.</span></span> <span data-ttu-id="dbae9-141">Beispielsweise können Sie mit dem `Where-Object` Cmdlet Dateien auswählen, die nach einem bestimmten Datum erstellt wurden, Ereignisse mit einer bestimmten ID oder Computer, auf denen eine bestimmte Version von Windows verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dbae9-141">For example, you can use the `Where-Object` cmdlet to select files that were created after a certain date, events with a particular ID, or computers that use a particular version of Windows.</span></span>

<span data-ttu-id="dbae9-142">Ab Windows PowerShell 3,0 gibt es zwei verschiedene Möglichkeiten, einen Befehl zu erstellen `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="dbae9-142">Starting in Windows PowerShell 3.0, there are two different ways to construct a `Where-Object` command.</span></span>

- <span data-ttu-id="dbae9-143">**Skriptblock**.</span><span class="sxs-lookup"><span data-stu-id="dbae9-143">**Script block**.</span></span> <span data-ttu-id="dbae9-144">Sie können einen Skriptblock verwenden, um den Namen der Eigenschaft, einen Vergleichsoperator und einen Eigenschaftswert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dbae9-144">You can use a script block to specify the property name, a comparison operator, and a property value.</span></span> <span data-ttu-id="dbae9-145">`Where-Object` Gibt alle-Objekte zurück, für die die script Block-Anweisung den Wert true hat.</span><span class="sxs-lookup"><span data-stu-id="dbae9-145">`Where-Object` returns all objects for which the script block statement is true.</span></span>

  <span data-ttu-id="dbae9-146">Beispielsweise ruft der folgende Befehl Prozesse in der normalen Prioritäts Klasse ab, d. h. Prozesse, bei denen der Wert der **PriorityClass** -Eigenschaft Normal ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-146">For example, the following command gets processes in the Normal priority class, that is, processes where the value of the **PriorityClass** property equals Normal.</span></span>

  `Get-Process | Where-Object {$_.PriorityClass -eq "Normal"}`

  <span data-ttu-id="dbae9-147">Alle PowerShell-Vergleichs Operatoren sind im Skriptblock Format gültig.</span><span class="sxs-lookup"><span data-stu-id="dbae9-147">All PowerShell comparison operators are valid in the script block format.</span></span> <span data-ttu-id="dbae9-148">Weitere Informationen zu Vergleichs Operatoren finden Sie unter [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="dbae9-148">For more information about comparison operators, see [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span></span>

- <span data-ttu-id="dbae9-149">**Vergleichs Anweisung**.</span><span class="sxs-lookup"><span data-stu-id="dbae9-149">**Comparison statement**.</span></span> <span data-ttu-id="dbae9-150">Sie können auch eine Vergleichsanweisung schreiben, was der natürlichen Sprache sehr viel ähnlicher ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-150">You can also write a comparison statement, which is much more like natural language.</span></span> <span data-ttu-id="dbae9-151">Vergleichsanweisungen wurden in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-151">Comparison statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="dbae9-152">Beispielsweise werden mit den folgenden Befehlen auch Prozesse mit der Prioritäts Klasse "Normal" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-152">For example, the following commands also get processes that have a priority class of Normal.</span></span> <span data-ttu-id="dbae9-153">Diese Befehle sind gleichwertig und austauschbar.</span><span class="sxs-lookup"><span data-stu-id="dbae9-153">These commands are equivalent and can be used interchangeably.</span></span>

  `Get-Process | Where-Object -Property PriorityClass -eq -Value "Normal"`

  `Get-Process | Where-Object PriorityClass -eq "Normal"`

  <span data-ttu-id="dbae9-154">Ab Windows PowerShell 3,0 `Where-Object` fügt Vergleichs Operatoren als Parameter in einem `Where-Object` Befehl hinzu.</span><span class="sxs-lookup"><span data-stu-id="dbae9-154">Starting in Windows PowerShell 3.0, `Where-Object` adds comparison operators as parameters in a `Where-Object` command.</span></span> <span data-ttu-id="dbae9-155">Sofern nicht anders angegeben, wird bei allen Operatoren die Groß-und Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-155">Unless specified, all operators are case-insensitive.</span></span> <span data-ttu-id="dbae9-156">Vor Windows PowerShell 3,0 konnten die Vergleichs Operatoren in der PowerShell-Sprache nur in Skript Blöcken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dbae9-156">Prior to Windows PowerShell 3.0, the comparison operators in the PowerShell language could be used only in script blocks.</span></span>

<span data-ttu-id="dbae9-157">Wenn Sie eine einzelne **Eigenschaft** für angeben `Where-Object` , wird der Wert der Eigenschaft als boolescher Ausdruck behandelt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-157">When you provide a single **Property** to `Where-Object`, the value of the property is treated as a boolean expression.</span></span> <span data-ttu-id="dbae9-158">Wenn der Wert von **length** nicht 0 (null) ist, wird der Ausdruck als **true** ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-158">When the value of **Length** is not zero, the expression evaluates to **True**.</span></span> <span data-ttu-id="dbae9-159">Beispiel: `('hi', '', 'there') | Where-Object Length`</span><span class="sxs-lookup"><span data-stu-id="dbae9-159">For example: `('hi', '', 'there') | Where-Object Length`</span></span>

<span data-ttu-id="dbae9-160">Das vorherige Beispiel ist funktional äquivalent zu:</span><span class="sxs-lookup"><span data-stu-id="dbae9-160">The previous example is functionally equivalent to:</span></span>

- `('hi', '', 'there') | Where-Object Length -GT 0`
- `('hi', '', 'there') | Where-Object {$_.Length -gt 0}`

## <span data-ttu-id="dbae9-161">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="dbae9-161">EXAMPLES</span></span>

### <span data-ttu-id="dbae9-162">Beispiel 1: erhalten von beendeten Diensten</span><span class="sxs-lookup"><span data-stu-id="dbae9-162">Example 1: Get stopped services</span></span>

<span data-ttu-id="dbae9-163">Mit diesen Befehlen wird eine Liste aller Dienste angezeigt, die zurzeit beendet sind.</span><span class="sxs-lookup"><span data-stu-id="dbae9-163">These commands get a list of all services that are currently stopped.</span></span> <span data-ttu-id="dbae9-164">Die `$_` Automatische Variable stellt jedes Objekt dar, das an das `Where-Object` Cmdlet übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="dbae9-164">The `$_` automatic variable represents each object that is passed to the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="dbae9-165">Der erste Befehl verwendet das Skriptblock Format, der zweite Befehl verwendet das Vergleichs Anweisungs Format.</span><span class="sxs-lookup"><span data-stu-id="dbae9-165">The first command uses the script block format, the second command uses the comparison statement format.</span></span> <span data-ttu-id="dbae9-166">Diese Befehle sind gleichwertig und austauschbar.</span><span class="sxs-lookup"><span data-stu-id="dbae9-166">The commands are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Stopped"}
Get-Service | where Status -eq "Stopped"
```

### <span data-ttu-id="dbae9-167">Beispiel 2: erhalten von Prozessen basierend auf dem Workingset</span><span class="sxs-lookup"><span data-stu-id="dbae9-167">Example 2: Get processes based on working set</span></span>

<span data-ttu-id="dbae9-168">Mit diesen Befehlen werden Prozesse aufgelistet, die über ein Workingset verfügen, das größer ist als 250 Megabyte (KB).</span><span class="sxs-lookup"><span data-stu-id="dbae9-168">These commands list processes that have a working set greater than 250 megabytes (KB).</span></span> <span data-ttu-id="dbae9-169">Die ScriptBlock-und die-Anweisungs Syntax sind gleichwertig und können austauschbar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dbae9-169">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -GT 250MB}
Get-Process | Where-Object WorkingSet -GT (250MB)
```

### <span data-ttu-id="dbae9-170">Beispiel 3: erhalten von Prozessen basierend auf dem Prozessnamen</span><span class="sxs-lookup"><span data-stu-id="dbae9-170">Example 3: Get processes based on process name</span></span>

<span data-ttu-id="dbae9-171">Mit diesen Befehlen werden die Prozesse mit einem **ProcessName** -Eigenschafts Wert, der mit dem Buchstaben beginnt, angezeigt `p` .</span><span class="sxs-lookup"><span data-stu-id="dbae9-171">These commands get the processes that have a **ProcessName** property value that begins with the letter `p`.</span></span> <span data-ttu-id="dbae9-172">Mit dem **Match** -Operator können Sie reguläre Ausdrucks Übereinstimmungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="dbae9-172">The **Match** operator lets you use regular expression matches.</span></span>

<span data-ttu-id="dbae9-173">Die ScriptBlock-und die-Anweisungs Syntax sind gleichwertig und können austauschbar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dbae9-173">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.ProcessName -Match "^p.*"}
Get-Process | Where-Object ProcessName -Match "^p.*"
```

### <span data-ttu-id="dbae9-174">Beispiel 4: Verwenden des Vergleichs Anweisungs Formats</span><span class="sxs-lookup"><span data-stu-id="dbae9-174">Example 4: Use the comparison statement format</span></span>

<span data-ttu-id="dbae9-175">In diesem Beispiel wird gezeigt, wie das neue Vergleichs Anweisungs Format des `Where-Object` Cmdlets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dbae9-175">This example shows how to use the new comparison statement format of the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="dbae9-176">Der erste Befehl verwendet das Vergleichsanweisungsformat.</span><span class="sxs-lookup"><span data-stu-id="dbae9-176">The first command uses the comparison statement format.</span></span>
<span data-ttu-id="dbae9-177">In diesem Befehl werden keine Aliase verwendet, und alle Parameter enthalten den Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="dbae9-177">In this command, no aliases are used and all parameters include the parameter name.</span></span>

<span data-ttu-id="dbae9-178">Der zweite Befehl stellt eine natürlichere Verwendung des Vergleichsbefehlsformats dar.</span><span class="sxs-lookup"><span data-stu-id="dbae9-178">The second command is the more natural use of the comparison command format.</span></span> <span data-ttu-id="dbae9-179">Der `where` Alias wird durch den `Where-Object` Cmdlet-Namen ersetzt, und alle optionalen Parameternamen werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="dbae9-179">The `where` alias is substituted for the `Where-Object` cmdlet name and all optional parameter names are omitted.</span></span>

```powershell
Get-Process | Where-Object -Property Handles -GE -Value 1000
Get-Process | where Handles -GE 1000
```

### <span data-ttu-id="dbae9-180">Beispiel 5: Get-Befehle basierend auf Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dbae9-180">Example 5: Get commands based on properties</span></span>

<span data-ttu-id="dbae9-181">In diesem Beispiel wird veranschaulicht, wie Sie Befehle schreiben können, mit denen Elemente zurückgegeben werden, die „true“ oder „false“ sind oder die einen beliebigen Wert für eine angegebene Eigenschaft aufweisen.</span><span class="sxs-lookup"><span data-stu-id="dbae9-181">This example shows how to write commands that return items that are true or false or have any value for a specified property.</span></span> <span data-ttu-id="dbae9-182">Jedes Beispiel zeigt sowohl den Skriptblock als auch Vergleichs Anweisungs Formate für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="dbae9-182">Each example shows both the script block and comparison statement formats for the command.</span></span>

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

### <span data-ttu-id="dbae9-183">Beispiel 6: Verwenden mehrerer Bedingungen</span><span class="sxs-lookup"><span data-stu-id="dbae9-183">Example 6: Use multiple conditions</span></span>

```powershell
Get-Module -ListAvailable | where {($_.Name -notlike "Microsoft*" -and $_.Name -notlike "PS*") -and $_.HelpInfoUri}
```

<span data-ttu-id="dbae9-184">Dieses Beispiel zeigt, wie Sie einen `Where-Object` Befehl mit mehreren Bedingungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="dbae9-184">This example shows how to create a `Where-Object` command with multiple conditions.</span></span>

<span data-ttu-id="dbae9-185">Dieser Befehl ruft Nicht-Kern-Module ab, die die aktualisierbare Hilfefunktion unterstützen.</span><span class="sxs-lookup"><span data-stu-id="dbae9-185">This command gets non-core modules that support the Updatable Help feature.</span></span> <span data-ttu-id="dbae9-186">Der Befehl verwendet den **listavailable** -Parameter des `Get-Module` Cmdlets, um alle Module auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="dbae9-186">The command uses the **ListAvailable** parameter of the `Get-Module` cmdlet to get all modules on the computer.</span></span> <span data-ttu-id="dbae9-187">Ein Pipeline Operator ( `|` ) sendet die Module an das `Where-Object` Cmdlet, das Module abruft, deren Namen nicht mit Microsoft oder PS beginnen, und einen Wert für die **helpinfouri** -Eigenschaft hat, der PowerShell mitteilt, wo aktualisierte Hilfedateien für das Modul zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="dbae9-187">A pipeline operator (`|`) sends the modules to the `Where-Object` cmdlet, which gets modules whose names do not begin with Microsoft or PS, and have a value for the **HelpInfoURI** property, which tells PowerShell where to find updated help files for the module.</span></span> <span data-ttu-id="dbae9-188">Die Vergleichs Anweisungen werden durch den logischen **and-** Operator miteinander verbunden.</span><span class="sxs-lookup"><span data-stu-id="dbae9-188">The comparison statements are connected by the **And** logical operator.</span></span>

<span data-ttu-id="dbae9-189">Im Beispiel wird das Skriptblock-Befehlsformat verwendet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-189">The example uses the script block command format.</span></span> <span data-ttu-id="dbae9-190">Logische Operatoren, wie z. b. **and** und **or** , sind nur in Skript Blöcken gültig.</span><span class="sxs-lookup"><span data-stu-id="dbae9-190">Logical operators, such as **And** and **Or** , are valid only in script blocks.</span></span> <span data-ttu-id="dbae9-191">Sie können Sie nicht im Vergleichs Anweisungs Format eines `Where-Object` Befehls verwenden.</span><span class="sxs-lookup"><span data-stu-id="dbae9-191">You cannot use them in the comparison statement format of a `Where-Object` command.</span></span>

- <span data-ttu-id="dbae9-192">Weitere Informationen zu logischen PowerShell-Operatoren finden Sie unter [about_Logical_Operators](./About/about_logical_operators.md).</span><span class="sxs-lookup"><span data-stu-id="dbae9-192">For more information about PowerShell logical operators, see [about_Logical_Operators](./About/about_logical_operators.md).</span></span>
- <span data-ttu-id="dbae9-193">Weitere Informationen zur aktualisierbaren Hilfe Funktion finden Sie unter [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="dbae9-193">For more information about the Updatable Help feature, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

## <span data-ttu-id="dbae9-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dbae9-194">PARAMETERS</span></span>

### <span data-ttu-id="dbae9-195">-Centhält</span><span class="sxs-lookup"><span data-stu-id="dbae9-195">-CContains</span></span>

<span data-ttu-id="dbae9-196">Gibt an, dass dieses Cmdlet Objekte aus einer Auflistung abruft, wenn der Eigenschafts Wert des Objekts eine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-196">Indicates that this cmdlet gets objects from a collection if the property value of the object is an exact match for the specified value.</span></span> <span data-ttu-id="dbae9-197">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-197">This operation is case-sensitive.</span></span>

<span data-ttu-id="dbae9-198">Beispiel: `Get-Process | where ProcessName -CContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="dbae9-198">For example: `Get-Process | where ProcessName -CContains "svchost"`</span></span>

<span data-ttu-id="dbae9-199">**CIS** bezieht sich auf eine Auflistung von Werten und ist true, wenn die Auflistung ein Element enthält, das eine genaue Entsprechung für den angegebenen Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-199">**CContains** refers to a collection of values and is true if the collection contains an item that is an exact match for the specified value.</span></span> <span data-ttu-id="dbae9-200">Wenn die Eingabe ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-200">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="dbae9-201">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-201">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-202">-Ceq</span><span class="sxs-lookup"><span data-stu-id="dbae9-202">-CEQ</span></span>

<span data-ttu-id="dbae9-203">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen Wert übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-203">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>
<span data-ttu-id="dbae9-204">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-204">This operation is case-sensitive.</span></span>

<span data-ttu-id="dbae9-205">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-205">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-206">-CGE</span><span class="sxs-lookup"><span data-stu-id="dbae9-206">-CGE</span></span>

<span data-ttu-id="dbae9-207">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert oder gleich dem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-207">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span> <span data-ttu-id="dbae9-208">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-208">This operation is case-sensitive.</span></span>

<span data-ttu-id="dbae9-209">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-209">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-210">-CGT</span><span class="sxs-lookup"><span data-stu-id="dbae9-210">-CGT</span></span>

<span data-ttu-id="dbae9-211">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-211">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>
<span data-ttu-id="dbae9-212">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-212">This operation is case-sensitive.</span></span>

<span data-ttu-id="dbae9-213">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-213">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-214">-CIN</span><span class="sxs-lookup"><span data-stu-id="dbae9-214">-CIn</span></span>

<span data-ttu-id="dbae9-215">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert den angegebenen Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="dbae9-215">Indicates that this cmdlet gets objects if the property value includes the specified value.</span></span> <span data-ttu-id="dbae9-216">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-216">This operation is case-sensitive.</span></span>

<span data-ttu-id="dbae9-217">Beispiel: `Get-Process | where -Value "svchost" -CIn ProcessName`</span><span class="sxs-lookup"><span data-stu-id="dbae9-217">For example: `Get-Process | where -Value "svchost" -CIn ProcessName`</span></span>

<span data-ttu-id="dbae9-218">**CIN** ähnelt **Care** , mit dem Unterschied, dass die Eigenschaften-und Wert Positionen umgekehrt werden.</span><span class="sxs-lookup"><span data-stu-id="dbae9-218">**CIn** resembles **CContains** , except that the property and value positions are reversed.</span></span> <span data-ttu-id="dbae9-219">Die folgenden Anweisungen sind z. B. beide „true“.</span><span class="sxs-lookup"><span data-stu-id="dbae9-219">For example, the following statements are both true.</span></span>

`"abc", "def" -CContains "abc"`

`"abc" -CIn "abc", "def"`

<span data-ttu-id="dbae9-220">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-220">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-221">-CLE</span><span class="sxs-lookup"><span data-stu-id="dbae9-221">-CLE</span></span>

<span data-ttu-id="dbae9-222">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner oder gleich dem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-222">Indicates that this cmdlet gets objects if the property value is less-than or equal to the specified value.</span></span> <span data-ttu-id="dbae9-223">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-223">This operation is case-sensitive.</span></span>

<span data-ttu-id="dbae9-224">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-224">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-225">-Clike</span><span class="sxs-lookup"><span data-stu-id="dbae9-225">-CLike</span></span>

<span data-ttu-id="dbae9-226">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert einem Wert entspricht, der Platzhalter Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="dbae9-226">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span> <span data-ttu-id="dbae9-227">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-227">This operation is case-sensitive.</span></span>

<span data-ttu-id="dbae9-228">Beispiel: `Get-Process | where ProcessName -CLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="dbae9-228">For example: `Get-Process | where ProcessName -CLike "*host"`</span></span>

<span data-ttu-id="dbae9-229">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-229">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-230">-CLT</span><span class="sxs-lookup"><span data-stu-id="dbae9-230">-CLT</span></span>

<span data-ttu-id="dbae9-231">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner als der angegebene Wert ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-231">Indicates that this cmdlet gets objects if the property value is less-than the specified value.</span></span> <span data-ttu-id="dbae9-232">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-232">This operation is case-sensitive.</span></span>

<span data-ttu-id="dbae9-233">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-233">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-234">-Cmatch</span><span class="sxs-lookup"><span data-stu-id="dbae9-234">-CMatch</span></span>

<span data-ttu-id="dbae9-235">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen regulären Ausdruck übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-235">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="dbae9-236">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-236">This operation is case-sensitive.</span></span> <span data-ttu-id="dbae9-237">Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dbae9-237">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="dbae9-238">Beispiel: `Get-Process | where ProcessName -CMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="dbae9-238">For example: `Get-Process | where ProcessName -CMatch "Shell"`</span></span>

<span data-ttu-id="dbae9-239">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-239">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-240">-CNE</span><span class="sxs-lookup"><span data-stu-id="dbae9-240">-CNE</span></span>

<span data-ttu-id="dbae9-241">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert sich vom angegebenen Wert unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-241">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>
<span data-ttu-id="dbae9-242">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-242">This operation is case-sensitive.</span></span>

<span data-ttu-id="dbae9-243">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-243">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-244">-Cnotenthält</span><span class="sxs-lookup"><span data-stu-id="dbae9-244">-CNotContains</span></span>

<span data-ttu-id="dbae9-245">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert des Objekts keine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-245">Indicates that this cmdlet gets objects if the property value of the object is not an exact match for the specified value.</span></span> <span data-ttu-id="dbae9-246">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-246">This operation is case-sensitive.</span></span>

<span data-ttu-id="dbae9-247">Beispiel: `Get-Process | where ProcessName -CNotContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="dbae9-247">For example: `Get-Process | where ProcessName -CNotContains "svchost"`</span></span>

<span data-ttu-id="dbae9-248">**Notare** und **cnotenthält** Verweise auf eine Auflistung von Werten und sind true, wenn die Auflistung keine Elemente enthält, die eine genaue Entsprechung für den angegebenen Wert sind.</span><span class="sxs-lookup"><span data-stu-id="dbae9-248">**NotContains** and **CNotContains** refer to a collection of values and are true when the collection does not contains any items that are an exact match for the specified value.</span></span> <span data-ttu-id="dbae9-249">Wenn die Eingabe ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-249">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="dbae9-250">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-250">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-251">-Cnotin</span><span class="sxs-lookup"><span data-stu-id="dbae9-251">-CNotIn</span></span>

<span data-ttu-id="dbae9-252">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert keine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-252">Indicates that this cmdlet gets objects if the property value is not an exact match for the specified value.</span></span> <span data-ttu-id="dbae9-253">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-253">This operation is case-sensitive.</span></span>

<span data-ttu-id="dbae9-254">Beispiel: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="dbae9-254">For example: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span></span>

<span data-ttu-id="dbae9-255">**NOTIN** -und **cnotin** -Operatoren ähneln **Notare** und **cnotare** , mit dem Unterschied, dass die Eigenschaften-und Wert Positionen umgekehrt werden.</span><span class="sxs-lookup"><span data-stu-id="dbae9-255">**NotIn** and **CNotIn** operators resemble **NotContains** and **CNotContains** , except that the property and value positions are reversed.</span></span> <span data-ttu-id="dbae9-256">Die folgenden Anweisungen sind z. B. „true“.</span><span class="sxs-lookup"><span data-stu-id="dbae9-256">For example, the following statements are true.</span></span>

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

### <span data-ttu-id="dbae9-257">-Cnotlike</span><span class="sxs-lookup"><span data-stu-id="dbae9-257">-CNotLike</span></span>

<span data-ttu-id="dbae9-258">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit einem Wert identisch ist, der Platzhalter Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="dbae9-258">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span> <span data-ttu-id="dbae9-259">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-259">This operation is case-sensitive.</span></span>

<span data-ttu-id="dbae9-260">Beispiel: `Get-Process | where ProcessName -CNotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="dbae9-260">For example: `Get-Process | where ProcessName -CNotLike "*host"`</span></span>

<span data-ttu-id="dbae9-261">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-261">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-262">-Cnotmatch</span><span class="sxs-lookup"><span data-stu-id="dbae9-262">-CNotMatch</span></span>

<span data-ttu-id="dbae9-263">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit dem angegebenen regulären Ausdruck identisch ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-263">Indicates that this cmdlet gets objects if the property value does not match the specified regular expression.</span></span> <span data-ttu-id="dbae9-264">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-264">This operation is case-sensitive.</span></span> <span data-ttu-id="dbae9-265">Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dbae9-265">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="dbae9-266">Beispiel: `Get-Process | where ProcessName -CNotMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="dbae9-266">For example: `Get-Process | where ProcessName -CNotMatch "Shell"`</span></span>

<span data-ttu-id="dbae9-267">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-267">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-268">-Enthält</span><span class="sxs-lookup"><span data-stu-id="dbae9-268">-Contains</span></span>

<span data-ttu-id="dbae9-269">Gibt an, dass dieses Cmdlet Objekte abruft, wenn ein Element im Eigenschafts Wert des Objekts eine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-269">Indicates that this cmdlet gets objects if any item in the property value of the object is an exact match for the specified value.</span></span>

<span data-ttu-id="dbae9-270">Beispiel: `Get-Process | where ProcessName -Contains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="dbae9-270">For example: `Get-Process | where ProcessName -Contains "Svchost"`</span></span>

<span data-ttu-id="dbae9-271">Wenn der Eigenschafts Wert ein einzelnes Objekt enthält, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-271">If the property value contains a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="dbae9-272">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-272">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-273">-EQ</span><span class="sxs-lookup"><span data-stu-id="dbae9-273">-EQ</span></span>

<span data-ttu-id="dbae9-274">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen Wert übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-274">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>

<span data-ttu-id="dbae9-275">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-275">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-276">-Filterscript</span><span class="sxs-lookup"><span data-stu-id="dbae9-276">-FilterScript</span></span>

<span data-ttu-id="dbae9-277">Gibt den Skriptblock an, der zum Filtern der Objekte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dbae9-277">Specifies the script block that is used to filter the objects.</span></span> <span data-ttu-id="dbae9-278">Schließen Sie den Skriptblock in geschweifte Klammern ( `{}` ) ein.</span><span class="sxs-lookup"><span data-stu-id="dbae9-278">Enclose the script block in braces (`{}`).</span></span>

<span data-ttu-id="dbae9-279">Der Parameter Name, **Filterscript** , ist optional.</span><span class="sxs-lookup"><span data-stu-id="dbae9-279">The parameter name, **FilterScript** , is optional.</span></span>

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

### <span data-ttu-id="dbae9-280">-GE</span><span class="sxs-lookup"><span data-stu-id="dbae9-280">-GE</span></span>

<span data-ttu-id="dbae9-281">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert oder gleich dem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-281">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span>

<span data-ttu-id="dbae9-282">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-282">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-283">-GT</span><span class="sxs-lookup"><span data-stu-id="dbae9-283">-GT</span></span>

<span data-ttu-id="dbae9-284">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-284">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>

<span data-ttu-id="dbae9-285">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-285">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-286">-In</span><span class="sxs-lookup"><span data-stu-id="dbae9-286">-In</span></span>

<span data-ttu-id="dbae9-287">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit einem der angegebenen Werte übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-287">Indicates that this cmdlet gets objects if the property value matches any of the specified values.</span></span>
<span data-ttu-id="dbae9-288">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dbae9-288">For example:</span></span>

`Get-Process | where -Property ProcessName -in -Value "Svchost", "TaskHost", "WsmProvHost"`

<span data-ttu-id="dbae9-289">Wenn der Wert des **value** -Parameters ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-289">If the value of the **Value** parameter is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="dbae9-290">Wenn der Eigenschafts Wert eines Objekts ein Array ist, verwendet PowerShell die Verweis Gleichheit, um eine Übereinstimmung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="dbae9-290">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="dbae9-291">`Where-Object` Gibt das-Objekt nur dann zurück, wenn der Wert des **Property** -Parameters und der Wert des **Werts** dieselbe Instanz eines Objekts sind.</span><span class="sxs-lookup"><span data-stu-id="dbae9-291">`Where-Object` returns the object only if the value of the **Property** parameter and any value of **Value** are the same instance of an object.</span></span>

<span data-ttu-id="dbae9-292">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-292">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-293">-InputObject</span><span class="sxs-lookup"><span data-stu-id="dbae9-293">-InputObject</span></span>

<span data-ttu-id="dbae9-294">Gibt das zu filternde Objekt an.</span><span class="sxs-lookup"><span data-stu-id="dbae9-294">Specifies the objects to be filtered.</span></span> <span data-ttu-id="dbae9-295">Sie können die Objekte auch über die Pipeline an übergeben `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="dbae9-295">You can also pipe the objects to `Where-Object`.</span></span>

<span data-ttu-id="dbae9-296">Wenn Sie den **Inputobject** -Parameter mit verwenden `Where-Object` , anstatt Befehls Ergebnisse an zu übergeben `Where-Object` , wird der **Inputobject** -Wert als einzelnes Objekt behandelt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-296">When you use the **InputObject** parameter with `Where-Object`, instead of piping command results to `Where-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="dbae9-297">Dies gilt auch, wenn der Wert eine Auflistung ist, die das Ergebnis eines Befehls ist, z `-InputObject (Get-Process)` . b..</span><span class="sxs-lookup"><span data-stu-id="dbae9-297">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span> <span data-ttu-id="dbae9-298">Da **Inputobject** keine einzelnen Eigenschaften aus einem Array oder einer Auflistung von Objekten zurückgeben kann, wird empfohlen, dass `Where-Object` Sie in der Pipeline verwenden, wenn Sie zum Filtern einer Auflistung von Objekten für Objekte verwenden, die bestimmte Werte in definierten Eigenschaften aufweisen, `Where-Object` wie in den Beispielen in diesem Thema gezeigt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-298">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that, if you use `Where-Object` to filter a collection of objects for those objects that have specific values in defined properties, you use `Where-Object` in the pipeline, as shown in the examples in this topic.</span></span>

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

### <span data-ttu-id="dbae9-299">-Ist</span><span class="sxs-lookup"><span data-stu-id="dbae9-299">-Is</span></span>

<span data-ttu-id="dbae9-300">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert eine Instanz des angegebenen .net-Typs ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-300">Indicates that this cmdlet gets objects if the property value is an instance of the specified .NET type.</span></span> <span data-ttu-id="dbae9-301">Schließen Sie den Typnamen in eckige Klammern ein.</span><span class="sxs-lookup"><span data-stu-id="dbae9-301">Enclose the type name in square brackets.</span></span>

<span data-ttu-id="dbae9-302">Zum Beispiel, `Get-Process | where StartTime -Is [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="dbae9-302">For example, `Get-Process | where StartTime -Is [DateTime]`</span></span>

<span data-ttu-id="dbae9-303">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-303">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-304">-IsNot</span><span class="sxs-lookup"><span data-stu-id="dbae9-304">-IsNot</span></span>

<span data-ttu-id="dbae9-305">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert keine Instanz des angegebenen .net-Typs ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-305">Indicates that this cmdlet gets objects if the property value is not an instance of the specified .NET type.</span></span>

<span data-ttu-id="dbae9-306">Zum Beispiel, `Get-Process | where StartTime -IsNot [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="dbae9-306">For example, `Get-Process | where StartTime -IsNot [DateTime]`</span></span>

<span data-ttu-id="dbae9-307">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-307">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-308">-Le</span><span class="sxs-lookup"><span data-stu-id="dbae9-308">-LE</span></span>

<span data-ttu-id="dbae9-309">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner oder gleich dem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-309">Indicates that this cmdlet gets objects if the property value is less than or equal to the specified value.</span></span>

<span data-ttu-id="dbae9-310">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-310">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-311">-Like</span><span class="sxs-lookup"><span data-stu-id="dbae9-311">-Like</span></span>

<span data-ttu-id="dbae9-312">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert einem Wert entspricht, der Platzhalter Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="dbae9-312">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span>

<span data-ttu-id="dbae9-313">Beispiel: `Get-Process | where ProcessName -Like "*host"`</span><span class="sxs-lookup"><span data-stu-id="dbae9-313">For example: `Get-Process | where ProcessName -Like "*host"`</span></span>

<span data-ttu-id="dbae9-314">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-314">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-315">-LT</span><span class="sxs-lookup"><span data-stu-id="dbae9-315">-LT</span></span>

<span data-ttu-id="dbae9-316">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner als der angegebene Wert ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-316">Indicates that this cmdlet gets objects if the property value is less than the specified value.</span></span>

<span data-ttu-id="dbae9-317">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-317">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-318">-Match</span><span class="sxs-lookup"><span data-stu-id="dbae9-318">-Match</span></span>

<span data-ttu-id="dbae9-319">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen regulären Ausdruck übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-319">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="dbae9-320">Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dbae9-320">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="dbae9-321">Beispiel: `Get-Process | where ProcessName -Match "shell"`</span><span class="sxs-lookup"><span data-stu-id="dbae9-321">For example: `Get-Process | where ProcessName -Match "shell"`</span></span>

<span data-ttu-id="dbae9-322">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-322">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-323">-NE</span><span class="sxs-lookup"><span data-stu-id="dbae9-323">-NE</span></span>

<span data-ttu-id="dbae9-324">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert sich vom angegebenen Wert unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="dbae9-324">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>

<span data-ttu-id="dbae9-325">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-325">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-326">-Not</span><span class="sxs-lookup"><span data-stu-id="dbae9-326">-Not</span></span>

<span data-ttu-id="dbae9-327">Gibt an, dass dieses Cmdlet Objekte abruft, wenn die Eigenschaft nicht vorhanden ist oder den Wert NULL oder false aufweist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-327">Indicates that this cmdlet gets objects if the property does not exist or has a value of null or false.</span></span>

<span data-ttu-id="dbae9-328">Beispiel: `Get-Service | where -Not "DependentServices"`</span><span class="sxs-lookup"><span data-stu-id="dbae9-328">For example: `Get-Service | where -Not "DependentServices"`</span></span>

<span data-ttu-id="dbae9-329">Dieser Parameter wurde in Windows PowerShell 6,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-329">This parameter was introduced in Windows PowerShell 6.1.</span></span>

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

### <span data-ttu-id="dbae9-330">-Notenthält</span><span class="sxs-lookup"><span data-stu-id="dbae9-330">-NotContains</span></span>

<span data-ttu-id="dbae9-331">Gibt an, dass dieses Cmdlet Objekte abruft, wenn keines der Elemente im Eigenschafts Wert eine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-331">Indicates that this cmdlet gets objects if none of the items in the property value is an exact match for the specified value.</span></span>

<span data-ttu-id="dbae9-332">Beispiel: `Get-Process | where ProcessName -NotContains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="dbae9-332">For example: `Get-Process | where ProcessName -NotContains "Svchost"`</span></span>

<span data-ttu-id="dbae9-333">**Notare** verweist auf eine Auflistung von Werten und ist true, wenn die Auflistung keine Elemente enthält, die eine genaue Entsprechung für den angegebenen Wert sind.</span><span class="sxs-lookup"><span data-stu-id="dbae9-333">**NotContains** refers to a collection of values and is true if the collection does not contain any items that are an exact match for the specified value.</span></span> <span data-ttu-id="dbae9-334">Wenn die Eingabe ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-334">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="dbae9-335">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-335">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-336">-NOTIN</span><span class="sxs-lookup"><span data-stu-id="dbae9-336">-NotIn</span></span>

<span data-ttu-id="dbae9-337">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert keine genaue Entsprechung für einen der angegebenen Werte ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-337">Indicates that this cmdlet gets objects if the property value is not an exact match for any of the specified values.</span></span>

<span data-ttu-id="dbae9-338">Beispiel: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="dbae9-338">For example: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span></span>

<span data-ttu-id="dbae9-339">Wenn der Wert von **value** ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-339">If the value of **Value** is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="dbae9-340">Wenn der Eigenschafts Wert eines Objekts ein Array ist, verwendet PowerShell die Verweis Gleichheit, um eine Übereinstimmung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="dbae9-340">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="dbae9-341">`Where-Object` Gibt das-Objekt nur dann zurück, wenn der Wert der- **Eigenschaft** und der Wert des **Werts** nicht dieselbe Instanz eines-Objekts sind.</span><span class="sxs-lookup"><span data-stu-id="dbae9-341">`Where-Object` returns the object only if the value of **Property** and any value of **Value** are not the same instance of an object.</span></span>

<span data-ttu-id="dbae9-342">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-342">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-343">-Notlike</span><span class="sxs-lookup"><span data-stu-id="dbae9-343">-NotLike</span></span>

<span data-ttu-id="dbae9-344">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit einem Wert identisch ist, der Platzhalter Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="dbae9-344">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span>

<span data-ttu-id="dbae9-345">Beispiel: `Get-Process | where ProcessName -NotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="dbae9-345">For example: `Get-Process | where ProcessName -NotLike "*host"`</span></span>

<span data-ttu-id="dbae9-346">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-346">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-347">-Notmatch</span><span class="sxs-lookup"><span data-stu-id="dbae9-347">-NotMatch</span></span>

<span data-ttu-id="dbae9-348">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit dem angegebenen regulären Ausdruck identisch ist.</span><span class="sxs-lookup"><span data-stu-id="dbae9-348">Indicates that this cmdlet gets objects when the property value does not match the specified regular expression.</span></span> <span data-ttu-id="dbae9-349">Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dbae9-349">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="dbae9-350">Beispiel: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span><span class="sxs-lookup"><span data-stu-id="dbae9-350">For example: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span></span>

<span data-ttu-id="dbae9-351">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-351">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-352">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dbae9-352">-Property</span></span>

<span data-ttu-id="dbae9-353">Gibt den Namen einer Objekteigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="dbae9-353">Specifies the name of an object property.</span></span> <span data-ttu-id="dbae9-354">Der Parameter Name " **Property** " ist optional.</span><span class="sxs-lookup"><span data-stu-id="dbae9-354">The parameter name, **Property** , is optional.</span></span>

<span data-ttu-id="dbae9-355">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-355">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-356">-Value</span><span class="sxs-lookup"><span data-stu-id="dbae9-356">-Value</span></span>

<span data-ttu-id="dbae9-357">Gibt einen Eigenschaftswert an.</span><span class="sxs-lookup"><span data-stu-id="dbae9-357">Specifies a property value.</span></span> <span data-ttu-id="dbae9-358">Der Parameter Name, **value** , ist optional.</span><span class="sxs-lookup"><span data-stu-id="dbae9-358">The parameter name, **Value** , is optional.</span></span> <span data-ttu-id="dbae9-359">Dieser Parameter akzeptiert Platzhalter Zeichen, wenn er mit den folgenden vergleichsparametern verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="dbae9-359">This parameter accepts wildcard characters when used with the following comparison parameters:</span></span>

- <span data-ttu-id="dbae9-360">**Clike**</span><span class="sxs-lookup"><span data-stu-id="dbae9-360">**CLike**</span></span>
- <span data-ttu-id="dbae9-361">**Cnotlike**</span><span class="sxs-lookup"><span data-stu-id="dbae9-361">**CNotLike**</span></span>
- <span data-ttu-id="dbae9-362">**mögen**</span><span class="sxs-lookup"><span data-stu-id="dbae9-362">**Like**</span></span>
- <span data-ttu-id="dbae9-363">**NotLike**</span><span class="sxs-lookup"><span data-stu-id="dbae9-363">**NotLike**</span></span>

<span data-ttu-id="dbae9-364">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-364">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dbae9-365">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dbae9-365">CommonParameters</span></span>

<span data-ttu-id="dbae9-366">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dbae9-366">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dbae9-367">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dbae9-367">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dbae9-368">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="dbae9-368">INPUTS</span></span>

### <span data-ttu-id="dbae9-369">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="dbae9-369">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="dbae9-370">Sie können die Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="dbae9-370">You can pipe the objects to this cmdlet.</span></span>

## <span data-ttu-id="dbae9-371">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="dbae9-371">OUTPUTS</span></span>

### <span data-ttu-id="dbae9-372">Object</span><span class="sxs-lookup"><span data-stu-id="dbae9-372">Object</span></span>

<span data-ttu-id="dbae9-373">Mit diesem Cmdlet werden ausgewählte Elemente aus dem Eingabe Objekt Satz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dbae9-373">This cmdlet returns selected items from the input object set.</span></span>

## <span data-ttu-id="dbae9-374">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="dbae9-374">NOTES</span></span>

<span data-ttu-id="dbae9-375">Ab Windows PowerShell 4,0 `Where` wurden-und-Methoden für die Verwendung mit-Auflistungen `ForEach` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dbae9-375">Starting in Windows PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span>

<span data-ttu-id="dbae9-376">Weitere Informationen zu diesen neuen Methoden finden Sie hier [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="dbae9-376">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="dbae9-377">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="dbae9-377">RELATED LINKS</span></span>

[<span data-ttu-id="dbae9-378">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="dbae9-378">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="dbae9-379">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="dbae9-379">ForEach-Object</span></span>](ForEach-Object.md)

[<span data-ttu-id="dbae9-380">Group-Object</span><span class="sxs-lookup"><span data-stu-id="dbae9-380">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="dbae9-381">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="dbae9-381">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="dbae9-382">New-Object</span><span class="sxs-lookup"><span data-stu-id="dbae9-382">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="dbae9-383">Select-Object</span><span class="sxs-lookup"><span data-stu-id="dbae9-383">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="dbae9-384">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="dbae9-384">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="dbae9-385">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="dbae9-385">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)

