---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Where-Object
ms.openlocfilehash: 0d9101c751e9ebc0b0c6fe80564bb76524de8bb6
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209828"
---
# <span data-ttu-id="5b0f0-103">Where-Object</span><span class="sxs-lookup"><span data-stu-id="5b0f0-103">Where-Object</span></span>

## <span data-ttu-id="5b0f0-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5b0f0-104">SYNOPSIS</span></span>
<span data-ttu-id="5b0f0-105">Wählt Objekte aus einer Auflistung basierend auf ihren Eigenschaftswerten aus.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-105">Selects objects from a collection based on their property values.</span></span>

## <span data-ttu-id="5b0f0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5b0f0-106">SYNTAX</span></span>

### <span data-ttu-id="5b0f0-107">Equalset (Standard)</span><span class="sxs-lookup"><span data-stu-id="5b0f0-107">EqualSet (Default)</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-EQ]
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-108">Scriptblockset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-108">ScriptBlockSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-FilterScript] <ScriptBlock> [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-109">Matchset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-109">MatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Match
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-110">Casesensitiveequalset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-110">CaseSensitiveEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CEQ
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-111">Notequalset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-111">NotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NE
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-112">Casesensitivenotequalset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-112">CaseSensitiveNotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNE
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-113">Greaterthanset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-113">GreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GT
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-114">Casesensitivegreaterthanset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-114">CaseSensitiveGreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGT
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-115">Lessthanset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-115">LessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LT
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-116">Casesensitiveless thanset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-116">CaseSensitiveLessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLT
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-117">Greaterorequalset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-117">GreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GE
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-118">Casesensitivegreaterorequalset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-118">CaseSensitiveGreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGE
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-119">Lessorequalset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-119">LessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LE
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-120">Casesensitivelesorequalset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-120">CaseSensitiveLessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLE
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-121">Likeset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-121">LikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Like
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-122">Casesensitivelikeset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-122">CaseSensitiveLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLike
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-123">Notlikeset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-123">NotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotLike
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-124">Casesensitivenotlikeset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-124">CaseSensitiveNotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotLike
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-125">Casesensitivematchset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-125">CaseSensitiveMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CMatch
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-126">Notmatchset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-126">NotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-127">Casesensitivenotmatchset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-127">CaseSensitiveNotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-128">Kontainsset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-128">ContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Contains
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-129">Casesensitivekontainsset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-129">CaseSensitiveContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CContains
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-130">Notkontainsset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-130">NotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotContains
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-131">Casesensitivenotkontainsset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-131">CaseSensitiveNotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotContains
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-132">Einfügen</span><span class="sxs-lookup"><span data-stu-id="5b0f0-132">InSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -In
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-133">Casesensitiveinset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-133">CaseSensitiveInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CIn
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-134">Notinset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-134">NotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotIn
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-135">Casesensitivenotinset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-135">CaseSensitiveNotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotIn
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-136">Isset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-136">IsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Is
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-137">Isnotset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-137">IsNotSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -IsNot
 [<CommonParameters>]
```

### <span data-ttu-id="5b0f0-138">Not</span><span class="sxs-lookup"><span data-stu-id="5b0f0-138">Not</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> -Not [<CommonParameters>]
```

## <span data-ttu-id="5b0f0-139">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5b0f0-139">DESCRIPTION</span></span>

<span data-ttu-id="5b0f0-140">Das `Where-Object` Cmdlet wählt Objekte aus, die bestimmte Eigenschaftswerte aus der Auflistung von-Objekten aufweisen, die an das Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-140">The `Where-Object` cmdlet selects objects that have particular property values from the collection of objects that are passed to it.</span></span> <span data-ttu-id="5b0f0-141">Beispielsweise können Sie mit dem `Where-Object` Cmdlet Dateien auswählen, die nach einem bestimmten Datum erstellt wurden, Ereignisse mit einer bestimmten ID oder Computer, auf denen eine bestimmte Version von Windows verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-141">For example, you can use the `Where-Object` cmdlet to select files that were created after a certain date, events with a particular ID, or computers that use a particular version of Windows.</span></span>

<span data-ttu-id="5b0f0-142">Ab Windows PowerShell 3,0 gibt es zwei verschiedene Möglichkeiten, einen Befehl zu erstellen `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="5b0f0-142">Starting in Windows PowerShell 3.0, there are two different ways to construct a `Where-Object` command.</span></span>

- <span data-ttu-id="5b0f0-143">**Skriptblock** .</span><span class="sxs-lookup"><span data-stu-id="5b0f0-143">**Script block** .</span></span> <span data-ttu-id="5b0f0-144">Sie können einen Skriptblock verwenden, um den Namen der Eigenschaft, einen Vergleichsoperator und einen Eigenschaftswert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-144">You can use a script block to specify the property name, a comparison operator, and a property value.</span></span> <span data-ttu-id="5b0f0-145">`Where-Object` Gibt alle-Objekte zurück, für die die script Block-Anweisung den Wert true hat.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-145">`Where-Object` returns all objects for which the script block statement is true.</span></span>

  <span data-ttu-id="5b0f0-146">Beispielsweise ruft der folgende Befehl Prozesse in der normalen Prioritäts Klasse ab, d. h. Prozesse, bei denen der Wert der **PriorityClass** -Eigenschaft Normal ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-146">For example, the following command gets processes in the Normal priority class, that is, processes where the value of the **PriorityClass** property equals Normal.</span></span>

  `Get-Process | Where-Object {$_.PriorityClass -eq "Normal"}`

  <span data-ttu-id="5b0f0-147">Alle PowerShell-Vergleichs Operatoren sind im Skriptblock Format gültig.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-147">All PowerShell comparison operators are valid in the script block format.</span></span> <span data-ttu-id="5b0f0-148">Weitere Informationen zu Vergleichs Operatoren finden Sie unter [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="5b0f0-148">For more information about comparison operators, see [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span></span>

- <span data-ttu-id="5b0f0-149">**Vergleichs Anweisung** .</span><span class="sxs-lookup"><span data-stu-id="5b0f0-149">**Comparison statement** .</span></span> <span data-ttu-id="5b0f0-150">Sie können auch eine Vergleichsanweisung schreiben, was der natürlichen Sprache sehr viel ähnlicher ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-150">You can also write a comparison statement, which is much more like natural language.</span></span> <span data-ttu-id="5b0f0-151">Vergleichsanweisungen wurden in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-151">Comparison statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="5b0f0-152">Beispielsweise werden mit den folgenden Befehlen auch Prozesse mit der Prioritäts Klasse "Normal" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-152">For example, the following commands also get processes that have a priority class of Normal.</span></span> <span data-ttu-id="5b0f0-153">Diese Befehle sind gleichwertig und austauschbar.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-153">These commands are equivalent and can be used interchangeably.</span></span>

  `Get-Process | Where-Object -Property PriorityClass -eq -Value "Normal"`

  `Get-Process | Where-Object PriorityClass -eq "Normal"`

  <span data-ttu-id="5b0f0-154">Ab Windows PowerShell 3,0 `Where-Object` fügt Vergleichs Operatoren als Parameter in einem `Where-Object` Befehl hinzu.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-154">Starting in Windows PowerShell 3.0, `Where-Object` adds comparison operators as parameters in a `Where-Object` command.</span></span> <span data-ttu-id="5b0f0-155">Sofern nicht anders angegeben, wird bei allen Operatoren die Groß-und Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-155">Unless specified, all operators are case-insensitive.</span></span> <span data-ttu-id="5b0f0-156">Vor Windows PowerShell 3,0 konnten die Vergleichs Operatoren in der PowerShell-Sprache nur in Skript Blöcken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-156">Prior to Windows PowerShell 3.0, the comparison operators in the PowerShell language could be used only in script blocks.</span></span>

<span data-ttu-id="5b0f0-157">Wenn Sie eine einzelne **Eigenschaft** für angeben `Where-Object` , wird der Wert der Eigenschaft als boolescher Ausdruck behandelt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-157">When you provide a single **Property** to `Where-Object`, the value of the property is treated as a boolean expression.</span></span> <span data-ttu-id="5b0f0-158">Wenn der Wert von **length** nicht 0 (null) ist, wird der Ausdruck als **true** ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-158">When the value of **Length** is not zero, the expression evaluates to **True** .</span></span> <span data-ttu-id="5b0f0-159">Beispiel: `('hi', '', 'there') | Where-Object Length`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-159">For example: `('hi', '', 'there') | Where-Object Length`</span></span>

<span data-ttu-id="5b0f0-160">Das vorherige Beispiel ist funktional äquivalent zu:</span><span class="sxs-lookup"><span data-stu-id="5b0f0-160">The previous example is functionally equivalent to:</span></span>

- `('hi', '', 'there') | Where-Object Length -GT 0`
- `('hi', '', 'there') | Where-Object {$_.Length -gt 0}`

## <span data-ttu-id="5b0f0-161">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5b0f0-161">EXAMPLES</span></span>

### <span data-ttu-id="5b0f0-162">Beispiel 1: erhalten von beendeten Diensten</span><span class="sxs-lookup"><span data-stu-id="5b0f0-162">Example 1: Get stopped services</span></span>

<span data-ttu-id="5b0f0-163">Mit diesen Befehlen wird eine Liste aller Dienste angezeigt, die zurzeit beendet sind.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-163">These commands get a list of all services that are currently stopped.</span></span> <span data-ttu-id="5b0f0-164">Die `$_` Automatische Variable stellt jedes Objekt dar, das an das `Where-Object` Cmdlet übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-164">The `$_` automatic variable represents each object that is passed to the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="5b0f0-165">Der erste Befehl verwendet das Skriptblock Format, der zweite Befehl verwendet das Vergleichs Anweisungs Format.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-165">The first command uses the script block format, the second command uses the comparison statement format.</span></span> <span data-ttu-id="5b0f0-166">Diese Befehle sind gleichwertig und austauschbar.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-166">The commands are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Stopped"}
Get-Service | where Status -eq "Stopped"
```

### <span data-ttu-id="5b0f0-167">Beispiel 2: erhalten von Prozessen basierend auf dem Workingset</span><span class="sxs-lookup"><span data-stu-id="5b0f0-167">Example 2: Get processes based on working set</span></span>

<span data-ttu-id="5b0f0-168">Mit diesen Befehlen werden Prozesse aufgelistet, die über ein Workingset verfügen, das größer ist als 250 Megabyte (KB).</span><span class="sxs-lookup"><span data-stu-id="5b0f0-168">These commands list processes that have a working set greater than 250 megabytes (KB).</span></span> <span data-ttu-id="5b0f0-169">Die ScriptBlock-und die-Anweisungs Syntax sind gleichwertig und können austauschbar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-169">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -GT 250MB}
Get-Process | Where-Object WorkingSet -GT (250MB)
```

### <span data-ttu-id="5b0f0-170">Beispiel 3: erhalten von Prozessen basierend auf dem Prozessnamen</span><span class="sxs-lookup"><span data-stu-id="5b0f0-170">Example 3: Get processes based on process name</span></span>

<span data-ttu-id="5b0f0-171">Mit diesen Befehlen werden die Prozesse mit einem **ProcessName** -Eigenschafts Wert, der mit dem Buchstaben beginnt, angezeigt `p` .</span><span class="sxs-lookup"><span data-stu-id="5b0f0-171">These commands get the processes that have a **ProcessName** property value that begins with the letter `p`.</span></span> <span data-ttu-id="5b0f0-172">Mit dem **Match** -Operator können Sie reguläre Ausdrucks Übereinstimmungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-172">The **Match** operator lets you use regular expression matches.</span></span>

<span data-ttu-id="5b0f0-173">Die ScriptBlock-und die-Anweisungs Syntax sind gleichwertig und können austauschbar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-173">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.ProcessName -Match "^p.*"}
Get-Process | Where-Object ProcessName -Match "^p.*"
```

### <span data-ttu-id="5b0f0-174">Beispiel 4: Verwenden des Vergleichs Anweisungs Formats</span><span class="sxs-lookup"><span data-stu-id="5b0f0-174">Example 4: Use the comparison statement format</span></span>

<span data-ttu-id="5b0f0-175">In diesem Beispiel wird gezeigt, wie das neue Vergleichs Anweisungs Format des `Where-Object` Cmdlets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-175">This example shows how to use the new comparison statement format of the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="5b0f0-176">Der erste Befehl verwendet das Vergleichsanweisungsformat.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-176">The first command uses the comparison statement format.</span></span>
<span data-ttu-id="5b0f0-177">In diesem Befehl werden keine Aliase verwendet, und alle Parameter enthalten den Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-177">In this command, no aliases are used and all parameters include the parameter name.</span></span>

<span data-ttu-id="5b0f0-178">Der zweite Befehl stellt eine natürlichere Verwendung des Vergleichsbefehlsformats dar.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-178">The second command is the more natural use of the comparison command format.</span></span> <span data-ttu-id="5b0f0-179">Der `where` Alias wird durch den `Where-Object` Cmdlet-Namen ersetzt, und alle optionalen Parameternamen werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-179">The `where` alias is substituted for the `Where-Object` cmdlet name and all optional parameter names are omitted.</span></span>

```powershell
Get-Process | Where-Object -Property Handles -GE -Value 1000
Get-Process | where Handles -GE 1000
```

### <span data-ttu-id="5b0f0-180">Beispiel 5: Get-Befehle basierend auf Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5b0f0-180">Example 5: Get commands based on properties</span></span>

<span data-ttu-id="5b0f0-181">In diesem Beispiel wird veranschaulicht, wie Sie Befehle schreiben können, mit denen Elemente zurückgegeben werden, die „true“ oder „false“ sind oder die einen beliebigen Wert für eine angegebene Eigenschaft aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-181">This example shows how to write commands that return items that are true or false or have any value for a specified property.</span></span> <span data-ttu-id="5b0f0-182">Jedes Beispiel zeigt sowohl den Skriptblock als auch Vergleichs Anweisungs Formate für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-182">Each example shows both the script block and comparison statement formats for the command.</span></span>

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

### <span data-ttu-id="5b0f0-183">Beispiel 6: Verwenden mehrerer Bedingungen</span><span class="sxs-lookup"><span data-stu-id="5b0f0-183">Example 6: Use multiple conditions</span></span>

```powershell
Get-Module -ListAvailable | where {($_.Name -notlike "Microsoft*" -and $_.Name -notlike "PS*") -and $_.HelpInfoUri}
```

<span data-ttu-id="5b0f0-184">Dieses Beispiel zeigt, wie Sie einen `Where-Object` Befehl mit mehreren Bedingungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-184">This example shows how to create a `Where-Object` command with multiple conditions.</span></span>

<span data-ttu-id="5b0f0-185">Dieser Befehl ruft Nicht-Kern-Module ab, die die aktualisierbare Hilfefunktion unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-185">This command gets non-core modules that support the Updatable Help feature.</span></span> <span data-ttu-id="5b0f0-186">Der Befehl verwendet den **listavailable** -Parameter des `Get-Module` Cmdlets, um alle Module auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-186">The command uses the **ListAvailable** parameter of the `Get-Module` cmdlet to get all modules on the computer.</span></span> <span data-ttu-id="5b0f0-187">Ein Pipeline Operator ( `|` ) sendet die Module an das `Where-Object` Cmdlet, das Module abruft, deren Namen nicht mit Microsoft oder PS beginnen, und einen Wert für die **helpinfouri** -Eigenschaft hat, der PowerShell mitteilt, wo aktualisierte Hilfedateien für das Modul zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-187">A pipeline operator (`|`) sends the modules to the `Where-Object` cmdlet, which gets modules whose names do not begin with Microsoft or PS, and have a value for the **HelpInfoURI** property, which tells PowerShell where to find updated help files for the module.</span></span> <span data-ttu-id="5b0f0-188">Die Vergleichs Anweisungen werden durch den logischen **and-** Operator miteinander verbunden.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-188">The comparison statements are connected by the **And** logical operator.</span></span>

<span data-ttu-id="5b0f0-189">Im Beispiel wird das Skriptblock-Befehlsformat verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-189">The example uses the script block command format.</span></span> <span data-ttu-id="5b0f0-190">Logische Operatoren, wie z. b. **and** und **or** , sind nur in Skript Blöcken gültig.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-190">Logical operators, such as **And** and **Or** , are valid only in script blocks.</span></span> <span data-ttu-id="5b0f0-191">Sie können Sie nicht im Vergleichs Anweisungs Format eines `Where-Object` Befehls verwenden.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-191">You cannot use them in the comparison statement format of a `Where-Object` command.</span></span>

- <span data-ttu-id="5b0f0-192">Weitere Informationen zu logischen PowerShell-Operatoren finden Sie unter [about_Logical_Operators](./About/about_logical_operators.md).</span><span class="sxs-lookup"><span data-stu-id="5b0f0-192">For more information about PowerShell logical operators, see [about_Logical_Operators](./About/about_logical_operators.md).</span></span>
- <span data-ttu-id="5b0f0-193">Weitere Informationen zur aktualisierbaren Hilfe Funktion finden Sie unter [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="5b0f0-193">For more information about the Updatable Help feature, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

## <span data-ttu-id="5b0f0-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5b0f0-194">PARAMETERS</span></span>

### <span data-ttu-id="5b0f0-195">-Centhält</span><span class="sxs-lookup"><span data-stu-id="5b0f0-195">-CContains</span></span>

<span data-ttu-id="5b0f0-196">Gibt an, dass dieses Cmdlet Objekte aus einer Auflistung abruft, wenn der Eigenschafts Wert des Objekts eine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-196">Indicates that this cmdlet gets objects from a collection if the property value of the object is an exact match for the specified value.</span></span> <span data-ttu-id="5b0f0-197">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-197">This operation is case-sensitive.</span></span>

<span data-ttu-id="5b0f0-198">Beispiel: `Get-Process | where ProcessName -CContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-198">For example: `Get-Process | where ProcessName -CContains "svchost"`</span></span>

<span data-ttu-id="5b0f0-199">**CIS** bezieht sich auf eine Auflistung von Werten und ist true, wenn die Auflistung ein Element enthält, das eine genaue Entsprechung für den angegebenen Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-199">**CContains** refers to a collection of values and is true if the collection contains an item that is an exact match for the specified value.</span></span> <span data-ttu-id="5b0f0-200">Wenn die Eingabe ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-200">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="5b0f0-201">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-201">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-202">-Ceq</span><span class="sxs-lookup"><span data-stu-id="5b0f0-202">-CEQ</span></span>

<span data-ttu-id="5b0f0-203">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen Wert übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-203">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>
<span data-ttu-id="5b0f0-204">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-204">This operation is case-sensitive.</span></span>

<span data-ttu-id="5b0f0-205">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-205">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-206">-CGE</span><span class="sxs-lookup"><span data-stu-id="5b0f0-206">-CGE</span></span>

<span data-ttu-id="5b0f0-207">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert oder gleich dem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-207">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span> <span data-ttu-id="5b0f0-208">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-208">This operation is case-sensitive.</span></span>

<span data-ttu-id="5b0f0-209">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-209">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-210">-CGT</span><span class="sxs-lookup"><span data-stu-id="5b0f0-210">-CGT</span></span>

<span data-ttu-id="5b0f0-211">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-211">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>
<span data-ttu-id="5b0f0-212">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-212">This operation is case-sensitive.</span></span>

<span data-ttu-id="5b0f0-213">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-213">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-214">-CIN</span><span class="sxs-lookup"><span data-stu-id="5b0f0-214">-CIn</span></span>

<span data-ttu-id="5b0f0-215">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert den angegebenen Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-215">Indicates that this cmdlet gets objects if the property value includes the specified value.</span></span> <span data-ttu-id="5b0f0-216">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-216">This operation is case-sensitive.</span></span>

<span data-ttu-id="5b0f0-217">Beispiel: `Get-Process | where -Value "svchost" -CIn ProcessName`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-217">For example: `Get-Process | where -Value "svchost" -CIn ProcessName`</span></span>

<span data-ttu-id="5b0f0-218">**CIN** ähnelt **Care** , mit dem Unterschied, dass die Eigenschaften-und Wert Positionen umgekehrt werden.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-218">**CIn** resembles **CContains** , except that the property and value positions are reversed.</span></span> <span data-ttu-id="5b0f0-219">Die folgenden Anweisungen sind z. B. beide „true“.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-219">For example, the following statements are both true.</span></span>

`"abc", "def" -CContains "abc"`

`"abc" -CIn "abc", "def"`

<span data-ttu-id="5b0f0-220">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-220">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-221">-CLE</span><span class="sxs-lookup"><span data-stu-id="5b0f0-221">-CLE</span></span>

<span data-ttu-id="5b0f0-222">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner oder gleich dem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-222">Indicates that this cmdlet gets objects if the property value is less-than or equal to the specified value.</span></span> <span data-ttu-id="5b0f0-223">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-223">This operation is case-sensitive.</span></span>

<span data-ttu-id="5b0f0-224">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-224">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-225">-Clike</span><span class="sxs-lookup"><span data-stu-id="5b0f0-225">-CLike</span></span>

<span data-ttu-id="5b0f0-226">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert einem Wert entspricht, der Platzhalter Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-226">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span> <span data-ttu-id="5b0f0-227">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-227">This operation is case-sensitive.</span></span>

<span data-ttu-id="5b0f0-228">Beispiel: `Get-Process | where ProcessName -CLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-228">For example: `Get-Process | where ProcessName -CLike "*host"`</span></span>

<span data-ttu-id="5b0f0-229">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-229">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-230">-CLT</span><span class="sxs-lookup"><span data-stu-id="5b0f0-230">-CLT</span></span>

<span data-ttu-id="5b0f0-231">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner als der angegebene Wert ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-231">Indicates that this cmdlet gets objects if the property value is less-than the specified value.</span></span> <span data-ttu-id="5b0f0-232">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-232">This operation is case-sensitive.</span></span>

<span data-ttu-id="5b0f0-233">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-233">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-234">-Cmatch</span><span class="sxs-lookup"><span data-stu-id="5b0f0-234">-CMatch</span></span>

<span data-ttu-id="5b0f0-235">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen regulären Ausdruck übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-235">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="5b0f0-236">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-236">This operation is case-sensitive.</span></span> <span data-ttu-id="5b0f0-237">Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-237">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="5b0f0-238">Beispiel: `Get-Process | where ProcessName -CMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-238">For example: `Get-Process | where ProcessName -CMatch "Shell"`</span></span>

<span data-ttu-id="5b0f0-239">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-239">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-240">-CNE</span><span class="sxs-lookup"><span data-stu-id="5b0f0-240">-CNE</span></span>

<span data-ttu-id="5b0f0-241">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert sich vom angegebenen Wert unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-241">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>
<span data-ttu-id="5b0f0-242">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-242">This operation is case-sensitive.</span></span>

<span data-ttu-id="5b0f0-243">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-243">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-244">-Cnotenthält</span><span class="sxs-lookup"><span data-stu-id="5b0f0-244">-CNotContains</span></span>

<span data-ttu-id="5b0f0-245">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert des Objekts keine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-245">Indicates that this cmdlet gets objects if the property value of the object is not an exact match for the specified value.</span></span> <span data-ttu-id="5b0f0-246">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-246">This operation is case-sensitive.</span></span>

<span data-ttu-id="5b0f0-247">Beispiel: `Get-Process | where ProcessName -CNotContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-247">For example: `Get-Process | where ProcessName -CNotContains "svchost"`</span></span>

<span data-ttu-id="5b0f0-248">**Notare** und **cnotenthält** Verweise auf eine Auflistung von Werten und sind true, wenn die Auflistung keine Elemente enthält, die eine genaue Entsprechung für den angegebenen Wert sind.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-248">**NotContains** and **CNotContains** refer to a collection of values and are true when the collection does not contains any items that are an exact match for the specified value.</span></span> <span data-ttu-id="5b0f0-249">Wenn die Eingabe ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-249">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="5b0f0-250">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-250">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-251">-Cnotin</span><span class="sxs-lookup"><span data-stu-id="5b0f0-251">-CNotIn</span></span>

<span data-ttu-id="5b0f0-252">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert keine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-252">Indicates that this cmdlet gets objects if the property value is not an exact match for the specified value.</span></span> <span data-ttu-id="5b0f0-253">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-253">This operation is case-sensitive.</span></span>

<span data-ttu-id="5b0f0-254">Beispiel: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-254">For example: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span></span>

<span data-ttu-id="5b0f0-255">**NOTIN** -und **cnotin** -Operatoren ähneln **Notare** und **cnotare** , mit dem Unterschied, dass die Eigenschaften-und Wert Positionen umgekehrt werden.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-255">**NotIn** and **CNotIn** operators resemble **NotContains** and **CNotContains** , except that the property and value positions are reversed.</span></span> <span data-ttu-id="5b0f0-256">Die folgenden Anweisungen sind z. B. „true“.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-256">For example, the following statements are true.</span></span>

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

### <span data-ttu-id="5b0f0-257">-Cnotlike</span><span class="sxs-lookup"><span data-stu-id="5b0f0-257">-CNotLike</span></span>

<span data-ttu-id="5b0f0-258">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit einem Wert identisch ist, der Platzhalter Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-258">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span> <span data-ttu-id="5b0f0-259">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-259">This operation is case-sensitive.</span></span>

<span data-ttu-id="5b0f0-260">Beispiel: `Get-Process | where ProcessName -CNotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-260">For example: `Get-Process | where ProcessName -CNotLike "*host"`</span></span>

<span data-ttu-id="5b0f0-261">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-261">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-262">-Cnotmatch</span><span class="sxs-lookup"><span data-stu-id="5b0f0-262">-CNotMatch</span></span>

<span data-ttu-id="5b0f0-263">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit dem angegebenen regulären Ausdruck identisch ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-263">Indicates that this cmdlet gets objects if the property value does not match the specified regular expression.</span></span> <span data-ttu-id="5b0f0-264">Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-264">This operation is case-sensitive.</span></span> <span data-ttu-id="5b0f0-265">Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-265">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="5b0f0-266">Beispiel: `Get-Process | where ProcessName -CNotMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-266">For example: `Get-Process | where ProcessName -CNotMatch "Shell"`</span></span>

<span data-ttu-id="5b0f0-267">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-267">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-268">-Enthält</span><span class="sxs-lookup"><span data-stu-id="5b0f0-268">-Contains</span></span>

<span data-ttu-id="5b0f0-269">Gibt an, dass dieses Cmdlet Objekte abruft, wenn ein Element im Eigenschafts Wert des Objekts eine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-269">Indicates that this cmdlet gets objects if any item in the property value of the object is an exact match for the specified value.</span></span>

<span data-ttu-id="5b0f0-270">Beispiel: `Get-Process | where ProcessName -Contains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-270">For example: `Get-Process | where ProcessName -Contains "Svchost"`</span></span>

<span data-ttu-id="5b0f0-271">Wenn der Eigenschafts Wert ein einzelnes Objekt enthält, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-271">If the property value contains a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="5b0f0-272">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-272">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-273">-EQ</span><span class="sxs-lookup"><span data-stu-id="5b0f0-273">-EQ</span></span>

<span data-ttu-id="5b0f0-274">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen Wert übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-274">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>

<span data-ttu-id="5b0f0-275">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-275">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-276">-Filterscript</span><span class="sxs-lookup"><span data-stu-id="5b0f0-276">-FilterScript</span></span>

<span data-ttu-id="5b0f0-277">Gibt den Skriptblock an, der zum Filtern der Objekte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-277">Specifies the script block that is used to filter the objects.</span></span> <span data-ttu-id="5b0f0-278">Schließen Sie den Skriptblock in geschweifte Klammern ( `{}` ) ein.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-278">Enclose the script block in braces (`{}`).</span></span>

<span data-ttu-id="5b0f0-279">Der Parameter Name, **Filterscript** , ist optional.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-279">The parameter name, **FilterScript** , is optional.</span></span>

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

### <span data-ttu-id="5b0f0-280">-GE</span><span class="sxs-lookup"><span data-stu-id="5b0f0-280">-GE</span></span>

<span data-ttu-id="5b0f0-281">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert oder gleich dem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-281">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span>

<span data-ttu-id="5b0f0-282">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-282">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-283">-GT</span><span class="sxs-lookup"><span data-stu-id="5b0f0-283">-GT</span></span>

<span data-ttu-id="5b0f0-284">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-284">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>

<span data-ttu-id="5b0f0-285">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-285">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-286">-In</span><span class="sxs-lookup"><span data-stu-id="5b0f0-286">-In</span></span>

<span data-ttu-id="5b0f0-287">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit einem der angegebenen Werte übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-287">Indicates that this cmdlet gets objects if the property value matches any of the specified values.</span></span>
<span data-ttu-id="5b0f0-288">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5b0f0-288">For example:</span></span>

`Get-Process | where -Property ProcessName -in -Value "Svchost", "TaskHost", "WsmProvHost"`

<span data-ttu-id="5b0f0-289">Wenn der Wert des **value** -Parameters ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-289">If the value of the **Value** parameter is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="5b0f0-290">Wenn der Eigenschafts Wert eines Objekts ein Array ist, verwendet PowerShell die Verweis Gleichheit, um eine Übereinstimmung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-290">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="5b0f0-291">`Where-Object` Gibt das-Objekt nur dann zurück, wenn der Wert des **Property** -Parameters und der Wert des **Werts** dieselbe Instanz eines Objekts sind.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-291">`Where-Object` returns the object only if the value of the **Property** parameter and any value of **Value** are the same instance of an object.</span></span>

<span data-ttu-id="5b0f0-292">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-292">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-293">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5b0f0-293">-InputObject</span></span>

<span data-ttu-id="5b0f0-294">Gibt das zu filternde Objekt an.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-294">Specifies the objects to be filtered.</span></span> <span data-ttu-id="5b0f0-295">Sie können die Objekte auch über die Pipeline an übergeben `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="5b0f0-295">You can also pipe the objects to `Where-Object`.</span></span>

<span data-ttu-id="5b0f0-296">Wenn Sie den **Inputobject** -Parameter mit verwenden `Where-Object` , anstatt Befehls Ergebnisse an zu übergeben `Where-Object` , wird der **Inputobject** -Wert als einzelnes Objekt behandelt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-296">When you use the **InputObject** parameter with `Where-Object`, instead of piping command results to `Where-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="5b0f0-297">Dies gilt auch, wenn der Wert eine Auflistung ist, die das Ergebnis eines Befehls ist, z `-InputObject (Get-Process)` . b..</span><span class="sxs-lookup"><span data-stu-id="5b0f0-297">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span> <span data-ttu-id="5b0f0-298">Da **Inputobject** keine einzelnen Eigenschaften aus einem Array oder einer Auflistung von Objekten zurückgeben kann, wird empfohlen, dass `Where-Object` Sie in der Pipeline verwenden, wenn Sie zum Filtern einer Auflistung von Objekten für Objekte verwenden, die bestimmte Werte in definierten Eigenschaften aufweisen, `Where-Object` wie in den Beispielen in diesem Thema gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-298">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that, if you use `Where-Object` to filter a collection of objects for those objects that have specific values in defined properties, you use `Where-Object` in the pipeline, as shown in the examples in this topic.</span></span>

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

### <span data-ttu-id="5b0f0-299">-Ist</span><span class="sxs-lookup"><span data-stu-id="5b0f0-299">-Is</span></span>

<span data-ttu-id="5b0f0-300">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert eine Instanz des angegebenen .net-Typs ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-300">Indicates that this cmdlet gets objects if the property value is an instance of the specified .NET type.</span></span> <span data-ttu-id="5b0f0-301">Schließen Sie den Typnamen in eckige Klammern ein.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-301">Enclose the type name in square brackets.</span></span>

<span data-ttu-id="5b0f0-302">Zum Beispiel, `Get-Process | where StartTime -Is [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-302">For example, `Get-Process | where StartTime -Is [DateTime]`</span></span>

<span data-ttu-id="5b0f0-303">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-303">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-304">-IsNot</span><span class="sxs-lookup"><span data-stu-id="5b0f0-304">-IsNot</span></span>

<span data-ttu-id="5b0f0-305">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert keine Instanz des angegebenen .net-Typs ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-305">Indicates that this cmdlet gets objects if the property value is not an instance of the specified .NET type.</span></span>

<span data-ttu-id="5b0f0-306">Zum Beispiel, `Get-Process | where StartTime -IsNot [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-306">For example, `Get-Process | where StartTime -IsNot [DateTime]`</span></span>

<span data-ttu-id="5b0f0-307">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-307">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-308">-Le</span><span class="sxs-lookup"><span data-stu-id="5b0f0-308">-LE</span></span>

<span data-ttu-id="5b0f0-309">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner oder gleich dem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-309">Indicates that this cmdlet gets objects if the property value is less than or equal to the specified value.</span></span>

<span data-ttu-id="5b0f0-310">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-310">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-311">-Like</span><span class="sxs-lookup"><span data-stu-id="5b0f0-311">-Like</span></span>

<span data-ttu-id="5b0f0-312">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert einem Wert entspricht, der Platzhalter Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-312">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span>

<span data-ttu-id="5b0f0-313">Beispiel: `Get-Process | where ProcessName -Like "*host"`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-313">For example: `Get-Process | where ProcessName -Like "*host"`</span></span>

<span data-ttu-id="5b0f0-314">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-314">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-315">-LT</span><span class="sxs-lookup"><span data-stu-id="5b0f0-315">-LT</span></span>

<span data-ttu-id="5b0f0-316">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner als der angegebene Wert ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-316">Indicates that this cmdlet gets objects if the property value is less than the specified value.</span></span>

<span data-ttu-id="5b0f0-317">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-317">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-318">-Match</span><span class="sxs-lookup"><span data-stu-id="5b0f0-318">-Match</span></span>

<span data-ttu-id="5b0f0-319">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen regulären Ausdruck übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-319">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="5b0f0-320">Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-320">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="5b0f0-321">Beispiel: `Get-Process | where ProcessName -Match "shell"`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-321">For example: `Get-Process | where ProcessName -Match "shell"`</span></span>

<span data-ttu-id="5b0f0-322">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-322">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-323">-NE</span><span class="sxs-lookup"><span data-stu-id="5b0f0-323">-NE</span></span>

<span data-ttu-id="5b0f0-324">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert sich vom angegebenen Wert unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-324">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>

<span data-ttu-id="5b0f0-325">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-325">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-326">-Not</span><span class="sxs-lookup"><span data-stu-id="5b0f0-326">-Not</span></span>

<span data-ttu-id="5b0f0-327">Gibt an, dass dieses Cmdlet Objekte abruft, wenn die Eigenschaft nicht vorhanden ist oder den Wert NULL oder false aufweist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-327">Indicates that this cmdlet gets objects if the property does not exist or has a value of null or false.</span></span>

<span data-ttu-id="5b0f0-328">Beispiel: `Get-Service | where -Not "DependentServices"`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-328">For example: `Get-Service | where -Not "DependentServices"`</span></span>

<span data-ttu-id="5b0f0-329">Dieser Parameter wurde in Windows PowerShell 6,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-329">This parameter was introduced in Windows PowerShell 6.1.</span></span>

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

### <span data-ttu-id="5b0f0-330">-Notenthält</span><span class="sxs-lookup"><span data-stu-id="5b0f0-330">-NotContains</span></span>

<span data-ttu-id="5b0f0-331">Gibt an, dass dieses Cmdlet Objekte abruft, wenn keines der Elemente im Eigenschafts Wert eine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-331">Indicates that this cmdlet gets objects if none of the items in the property value is an exact match for the specified value.</span></span>

<span data-ttu-id="5b0f0-332">Beispiel: `Get-Process | where ProcessName -NotContains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-332">For example: `Get-Process | where ProcessName -NotContains "Svchost"`</span></span>

<span data-ttu-id="5b0f0-333">**Notare** verweist auf eine Auflistung von Werten und ist true, wenn die Auflistung keine Elemente enthält, die eine genaue Entsprechung für den angegebenen Wert sind.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-333">**NotContains** refers to a collection of values and is true if the collection does not contain any items that are an exact match for the specified value.</span></span> <span data-ttu-id="5b0f0-334">Wenn die Eingabe ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-334">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="5b0f0-335">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-335">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-336">-NOTIN</span><span class="sxs-lookup"><span data-stu-id="5b0f0-336">-NotIn</span></span>

<span data-ttu-id="5b0f0-337">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert keine genaue Entsprechung für einen der angegebenen Werte ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-337">Indicates that this cmdlet gets objects if the property value is not an exact match for any of the specified values.</span></span>

<span data-ttu-id="5b0f0-338">Beispiel: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-338">For example: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span></span>

<span data-ttu-id="5b0f0-339">Wenn der Wert von **value** ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-339">If the value of **Value** is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="5b0f0-340">Wenn der Eigenschafts Wert eines Objekts ein Array ist, verwendet PowerShell die Verweis Gleichheit, um eine Übereinstimmung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-340">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="5b0f0-341">`Where-Object` Gibt das-Objekt nur dann zurück, wenn der Wert der- **Eigenschaft** und der Wert des **Werts** nicht dieselbe Instanz eines-Objekts sind.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-341">`Where-Object` returns the object only if the value of **Property** and any value of **Value** are not the same instance of an object.</span></span>

<span data-ttu-id="5b0f0-342">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-342">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-343">-Notlike</span><span class="sxs-lookup"><span data-stu-id="5b0f0-343">-NotLike</span></span>

<span data-ttu-id="5b0f0-344">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit einem Wert identisch ist, der Platzhalter Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-344">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span>

<span data-ttu-id="5b0f0-345">Beispiel: `Get-Process | where ProcessName -NotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-345">For example: `Get-Process | where ProcessName -NotLike "*host"`</span></span>

<span data-ttu-id="5b0f0-346">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-346">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-347">-Notmatch</span><span class="sxs-lookup"><span data-stu-id="5b0f0-347">-NotMatch</span></span>

<span data-ttu-id="5b0f0-348">Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit dem angegebenen regulären Ausdruck identisch ist.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-348">Indicates that this cmdlet gets objects when the property value does not match the specified regular expression.</span></span> <span data-ttu-id="5b0f0-349">Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-349">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="5b0f0-350">Beispiel: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span><span class="sxs-lookup"><span data-stu-id="5b0f0-350">For example: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span></span>

<span data-ttu-id="5b0f0-351">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-351">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5b0f0-352">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5b0f0-352">-Property</span></span>

<span data-ttu-id="5b0f0-353">Gibt den Namen einer Objekteigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-353">Specifies the name of an object property.</span></span> <span data-ttu-id="5b0f0-354">Der Parameter Name " **Property** " ist optional.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-354">The parameter name, **Property** , is optional.</span></span>

<span data-ttu-id="5b0f0-355">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-355">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: EqualSet, CaseSensitiveNotLikeSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, LessOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet, Not
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5b0f0-356">-Value</span><span class="sxs-lookup"><span data-stu-id="5b0f0-356">-Value</span></span>

<span data-ttu-id="5b0f0-357">Gibt einen Eigenschaftswert an.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-357">Specifies a property value.</span></span> <span data-ttu-id="5b0f0-358">Der Parameter Name, **value** , ist optional.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-358">The parameter name, **Value** , is optional.</span></span> <span data-ttu-id="5b0f0-359">Dieser Parameter akzeptiert Platzhalter Zeichen, wenn er mit den folgenden vergleichsparametern verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="5b0f0-359">This parameter accepts wildcard characters when used with the following comparison parameters:</span></span>

- <span data-ttu-id="5b0f0-360">**Clike**</span><span class="sxs-lookup"><span data-stu-id="5b0f0-360">**CLike**</span></span>
- <span data-ttu-id="5b0f0-361">**Cnotlike**</span><span class="sxs-lookup"><span data-stu-id="5b0f0-361">**CNotLike**</span></span>
- <span data-ttu-id="5b0f0-362">**mögen**</span><span class="sxs-lookup"><span data-stu-id="5b0f0-362">**Like**</span></span>
- <span data-ttu-id="5b0f0-363">**NotLike**</span><span class="sxs-lookup"><span data-stu-id="5b0f0-363">**NotLike**</span></span>

<span data-ttu-id="5b0f0-364">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-364">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Object
Parameter Sets: EqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, LessOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="5b0f0-365">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5b0f0-365">CommonParameters</span></span>

<span data-ttu-id="5b0f0-366">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-366">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5b0f0-367">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5b0f0-367">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5b0f0-368">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5b0f0-368">INPUTS</span></span>

### <span data-ttu-id="5b0f0-369">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="5b0f0-369">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="5b0f0-370">Sie können die Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-370">You can pipe the objects to this cmdlet.</span></span>

## <span data-ttu-id="5b0f0-371">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5b0f0-371">OUTPUTS</span></span>

### <span data-ttu-id="5b0f0-372">Object</span><span class="sxs-lookup"><span data-stu-id="5b0f0-372">Object</span></span>

<span data-ttu-id="5b0f0-373">Mit diesem Cmdlet werden ausgewählte Elemente aus dem Eingabe Objekt Satz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-373">This cmdlet returns selected items from the input object set.</span></span>

## <span data-ttu-id="5b0f0-374">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5b0f0-374">NOTES</span></span>

<span data-ttu-id="5b0f0-375">Ab Windows PowerShell 4,0 `Where` wurden-und-Methoden für die Verwendung mit-Auflistungen `ForEach` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-375">Starting in Windows PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span>

<span data-ttu-id="5b0f0-376">Weitere Informationen zu diesen neuen Methoden finden Sie hier [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="5b0f0-376">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="5b0f0-377">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5b0f0-377">RELATED LINKS</span></span>

[<span data-ttu-id="5b0f0-378">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="5b0f0-378">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="5b0f0-379">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="5b0f0-379">ForEach-Object</span></span>](ForEach-Object.md)

[<span data-ttu-id="5b0f0-380">Group-Object</span><span class="sxs-lookup"><span data-stu-id="5b0f0-380">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="5b0f0-381">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="5b0f0-381">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="5b0f0-382">New-Object</span><span class="sxs-lookup"><span data-stu-id="5b0f0-382">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="5b0f0-383">Select-Object</span><span class="sxs-lookup"><span data-stu-id="5b0f0-383">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="5b0f0-384">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="5b0f0-384">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="5b0f0-385">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="5b0f0-385">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
