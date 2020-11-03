---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-variable?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Variable
ms.openlocfilehash: 128bdd997e006723a69997e1419efd2f012e97f6
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211452"
---
# <span data-ttu-id="39d36-103">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="39d36-103">Get-Variable</span></span>

## <span data-ttu-id="39d36-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="39d36-104">SYNOPSIS</span></span>
<span data-ttu-id="39d36-105">Ruft die Variablen in der aktuellen Konsole ab.</span><span class="sxs-lookup"><span data-stu-id="39d36-105">Gets the variables in the current console.</span></span>

## <span data-ttu-id="39d36-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="39d36-106">SYNTAX</span></span>

```
Get-Variable [[-Name] <String[]>] [-ValueOnly] [-Include <String[]>] [-Exclude <String[]>] [-Scope <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="39d36-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="39d36-107">DESCRIPTION</span></span>

<span data-ttu-id="39d36-108">Das- `Get-Variable` Cmdlet ruft die PowerShell-Variablen in der aktuellen Konsole ab.</span><span class="sxs-lookup"><span data-stu-id="39d36-108">The `Get-Variable` cmdlet gets the PowerShell variables in the current console.</span></span>
<span data-ttu-id="39d36-109">Sie können nur die Werte der Variablen abrufen, indem Sie den **ValueOnly** -Parameter angeben, und Sie können die Variablen filtern, die nach Name zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="39d36-109">You can retrieve just the values of the variables by specifying the **ValueOnly** parameter, and you can filter the variables returned by name.</span></span>

## <span data-ttu-id="39d36-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="39d36-110">EXAMPLES</span></span>

### <span data-ttu-id="39d36-111">Beispiel 1: erhalten von Variablen nach Buchstaben</span><span class="sxs-lookup"><span data-stu-id="39d36-111">Example 1: Get variables by letter</span></span>

<span data-ttu-id="39d36-112">Dieser Befehl ruft Variablen ab, deren Namen mit dem Buchstaben "m" beginnen.</span><span class="sxs-lookup"><span data-stu-id="39d36-112">This command gets variables with names that begin with the letter m.</span></span>
<span data-ttu-id="39d36-113">Der Befehl ruft auch den Wert der Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="39d36-113">The command also gets the value of the variables.</span></span>

```powershell
Get-Variable m*
```

### <span data-ttu-id="39d36-114">Beispiel 2: erhalten von Variablen Werten nach Buchstaben</span><span class="sxs-lookup"><span data-stu-id="39d36-114">Example 2: Get variable values by letter</span></span>

<span data-ttu-id="39d36-115">Dieser Befehl ruft nur die Werte der Variablen ab, deren Namen mit "m" beginnen.</span><span class="sxs-lookup"><span data-stu-id="39d36-115">This command gets only the values of the variables that have names that begin with m.</span></span>

```powershell
Get-Variable m* -ValueOnly
```

### <span data-ttu-id="39d36-116">Beispiel 3: erhalten von Variablen mit zwei Buchstaben</span><span class="sxs-lookup"><span data-stu-id="39d36-116">Example 3: Get variables by two letters</span></span>

<span data-ttu-id="39d36-117">Dieser Befehl ruft Informationen zu den Variablen ab, die entweder mit dem Buchstaben "M" oder dem Buchstaben "P" beginnen.</span><span class="sxs-lookup"><span data-stu-id="39d36-117">This command gets information about the variables that begin with either the letter M or the letter P.</span></span>

```powershell
Get-Variable -Include M*,P*
```

### <span data-ttu-id="39d36-118">Beispiel 4: erhalten von Variablen nach Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="39d36-118">Example 4: Get variables by scope</span></span>

<span data-ttu-id="39d36-119">Der erste Befehl ruft nur die Variablen ab, die im lokalen Bereich definiert sind.</span><span class="sxs-lookup"><span data-stu-id="39d36-119">The first command gets only the variables that are defined in the local scope.</span></span>
<span data-ttu-id="39d36-120">Dies entspricht `Get-Variable -Scope Local` und kann als abgekürzt werden `gv -s 0` .</span><span class="sxs-lookup"><span data-stu-id="39d36-120">It is equivalent to `Get-Variable -Scope Local` and can be abbreviated as `gv -s 0`.</span></span>

<span data-ttu-id="39d36-121">Der zweite Befehl verwendet das `Compare-Object` Cmdlet, um die Variablen zu suchen, die im übergeordneten Bereich (Bereich 1) definiert sind, jedoch nur im lokalen Gültigkeitsbereich (Bereich 0) sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="39d36-121">The second command uses the `Compare-Object` cmdlet to find the variables that are defined in the parent scope (Scope 1) but are visible only in the local scope (Scope 0).</span></span>

```powershell
Get-Variable -Scope 0
Compare-Object (Get-Variable -Scope 0) (Get-Variable -Scope 1)
```

## <span data-ttu-id="39d36-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="39d36-122">PARAMETERS</span></span>

### <span data-ttu-id="39d36-123">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="39d36-123">-Exclude</span></span>

<span data-ttu-id="39d36-124">Gibt ein Array von Elementen an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="39d36-124">Specifies an array of items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="39d36-125">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="39d36-125">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="39d36-126">-Include</span><span class="sxs-lookup"><span data-stu-id="39d36-126">-Include</span></span>

<span data-ttu-id="39d36-127">Gibt ein Array von Elementen an, auf die das Cmdlet angewendet wird. alle anderen werden ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="39d36-127">Specifies an array of items upon which the cmdlet will act, excluding all others.</span></span>
<span data-ttu-id="39d36-128">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="39d36-128">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="39d36-129">-Name</span><span class="sxs-lookup"><span data-stu-id="39d36-129">-Name</span></span>

<span data-ttu-id="39d36-130">Gibt den Namen der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="39d36-130">Specifies the name of the variable.</span></span>
<span data-ttu-id="39d36-131">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="39d36-131">Wildcards are permitted.</span></span>
<span data-ttu-id="39d36-132">Sie können einen Variablennamen auch über die Pipeline an senden `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="39d36-132">You can also pipe a variable name to `Get-Variable`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="39d36-133">-Bereich</span><span class="sxs-lookup"><span data-stu-id="39d36-133">-Scope</span></span>

<span data-ttu-id="39d36-134">Gibt die Variablen im Gültigkeitsbereich an. Die zulässigen Werte für diesen Parameter sind:</span><span class="sxs-lookup"><span data-stu-id="39d36-134">Specifies the variables in the scope.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="39d36-135">**Global**</span><span class="sxs-lookup"><span data-stu-id="39d36-135">**Global**</span></span>
- <span data-ttu-id="39d36-136">**Lokal**</span><span class="sxs-lookup"><span data-stu-id="39d36-136">**Local**</span></span>
- <span data-ttu-id="39d36-137">**Skript**</span><span class="sxs-lookup"><span data-stu-id="39d36-137">**Script**</span></span>
- <span data-ttu-id="39d36-138">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist)</span><span class="sxs-lookup"><span data-stu-id="39d36-138">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="39d36-139">**Local** ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="39d36-139">**Local** is the default.</span></span>
<span data-ttu-id="39d36-140">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="39d36-140">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39d36-141">-Valueonly</span><span class="sxs-lookup"><span data-stu-id="39d36-141">-ValueOnly</span></span>

<span data-ttu-id="39d36-142">Gibt an, dass dieses Cmdlet nur den Wert der Variablen abruft.</span><span class="sxs-lookup"><span data-stu-id="39d36-142">Indicates that this cmdlet gets only the value of the variable.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39d36-143">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="39d36-143">CommonParameters</span></span>

<span data-ttu-id="39d36-144">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="39d36-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="39d36-145">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="39d36-145">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="39d36-146">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="39d36-146">INPUTS</span></span>

### <span data-ttu-id="39d36-147">System.String</span><span class="sxs-lookup"><span data-stu-id="39d36-147">System.String</span></span>

<span data-ttu-id="39d36-148">Sie können eine Zeichenfolge, die den Variablennamen enthält, über die Pipeline an übergeben `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="39d36-148">You can pipe a string that contains the variable name to `Get-Variable`.</span></span>

## <span data-ttu-id="39d36-149">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="39d36-149">OUTPUTS</span></span>

### <span data-ttu-id="39d36-150">System. Management. Automation. psvariable</span><span class="sxs-lookup"><span data-stu-id="39d36-150">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="39d36-151">Dieses Cmdlet gibt ein **System. Management. automationpsvariable** -Objekt für jede Variable zurück, die es abruft.</span><span class="sxs-lookup"><span data-stu-id="39d36-151">This cmdlet returns a **System.Management.AutomationPSVariable** object for each variable that it gets.</span></span> <span data-ttu-id="39d36-152">Der Objekttyp hängt von der Variable ab.</span><span class="sxs-lookup"><span data-stu-id="39d36-152">The object type depends on the variable.</span></span>

### <span data-ttu-id="39d36-153">System. Object []</span><span class="sxs-lookup"><span data-stu-id="39d36-153">System.Object[]</span></span>

<span data-ttu-id="39d36-154">Wenn Sie den **valueonly** -Parameter angeben und der Wert der angegebenen Variablen eine Auflistung ist, `Get-Variable` gibt einen zurück `[System.Object[]]` .</span><span class="sxs-lookup"><span data-stu-id="39d36-154">When you specify the **ValueOnly** parameter, if the specified variable's value is a collection, `Get-Variable` returns a `[System.Object[]]`.</span></span> <span data-ttu-id="39d36-155">Dieses Verhalten verhindert, dass der normale Pipeline Vorgang die Werte der Variablen einzeln verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="39d36-155">This behavior prevents normal pipeline operation from processing the variable's values one at a time.</span></span> <span data-ttu-id="39d36-156">Eine Problem Umgehung, um auflistungsenumeration zu erzwingen, besteht darin, den `Get-Variable` Befehl in Klammern einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="39d36-156">A workaround to force collection enumeration is to enclose the `Get-Variable` command in parenthesis.</span></span>

## <span data-ttu-id="39d36-157">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="39d36-157">NOTES</span></span>

- <span data-ttu-id="39d36-158">Dieses Cmdlet verwaltet keine Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="39d36-158">This cmdlet does not manage environment variables.</span></span> <span data-ttu-id="39d36-159">Zum Verwalten von Umgebungsvariablen können Sie den Umgebungsvariablenanbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="39d36-159">To manage environment variables, you can use the environment variable provider.</span></span>

## <span data-ttu-id="39d36-160">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="39d36-160">RELATED LINKS</span></span>

[<span data-ttu-id="39d36-161">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="39d36-161">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="39d36-162">New-Variable</span><span class="sxs-lookup"><span data-stu-id="39d36-162">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="39d36-163">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="39d36-163">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="39d36-164">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="39d36-164">Set-Variable</span></span>](Set-Variable.md)
