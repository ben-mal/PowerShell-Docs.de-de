---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/clear-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Variable
ms.openlocfilehash: 0381b48097f75d3195a82a67225cd8d6759e7433
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596155"
---
# <span data-ttu-id="44371-102">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="44371-102">Clear-Variable</span></span>

## <span data-ttu-id="44371-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="44371-103">SYNOPSIS</span></span>
<span data-ttu-id="44371-104">Löscht den Wert einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="44371-104">Deletes the value of a variable.</span></span>

## <span data-ttu-id="44371-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="44371-105">SYNTAX</span></span>

```
Clear-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-PassThru]
 [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="44371-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44371-106">DESCRIPTION</span></span>

<span data-ttu-id="44371-107">Das **Clear-Variable-** Cmdlet löscht die in einer Variablen gespeicherten Daten, aber die Variable wird nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="44371-107">The **Clear-Variable** cmdlet deletes the data stored in a variable, but it does not delete the variable.</span></span>
<span data-ttu-id="44371-108">Daher ist der Wert der Variablen NULL (leer).</span><span class="sxs-lookup"><span data-stu-id="44371-108">As a result, the value of the variable is NULL (empty).</span></span>
<span data-ttu-id="44371-109">Wenn die Variable einen angegebenen Daten-oder Objekttyp aufweist, behält dieses Cmdlet den Typ des in der Variablen gespeicherten Objekts bei.</span><span class="sxs-lookup"><span data-stu-id="44371-109">If the variable has a specified data or object type, this cmdlet preserves the type of the object stored in the variable.</span></span>

## <span data-ttu-id="44371-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="44371-110">EXAMPLES</span></span>

### <span data-ttu-id="44371-111">Beispiel 1: Entfernen des Werts von globalen Variablen, die mit einer Such Zeichenfolge beginnen</span><span class="sxs-lookup"><span data-stu-id="44371-111">Example 1: Remove the value of global variables that begin with a search string</span></span>

```
PS C:\> Clear-Variable my* -Scope Global
```

<span data-ttu-id="44371-112">Dieser Befehl entfernt den Wert von globalen Variablen, deren Namen mit "My" beginnen.</span><span class="sxs-lookup"><span data-stu-id="44371-112">This command removes the value of global variables that have names that begin with my.</span></span>

### <span data-ttu-id="44371-113">Beispiel 2: Löschen einer Variablen in einem untergeordneten Bereich, aber nicht im übergeordneten Bereich</span><span class="sxs-lookup"><span data-stu-id="44371-113">Example 2: Clear a variable in a child scope but not the parent scope</span></span>

```
PS C:\> $a=3
PS C:\> &{ Clear-Variable a }
PS C:\> $a
3
```

<span data-ttu-id="44371-114">Diese Befehle veranschaulichen, dass durch das Löschen einer Variablen in einem untergeordneten Bereich der Wert im übergeordneten Bereich nicht gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="44371-114">These commands demonstrate that clearing a variable in a child scope does not clear the value in the parent scope.</span></span>
<span data-ttu-id="44371-115">Mit dem ersten Befehl wird der Wert der Variablen $A auf 3 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="44371-115">The first command sets the value of the variable $A to 3.</span></span>
<span data-ttu-id="44371-116">Der zweite Befehl verwendet den Aufruf Operator (&), um den **Clear-Variable-** Befehl in einem neuen Bereich auszuführen.</span><span class="sxs-lookup"><span data-stu-id="44371-116">The second command uses the invoke operator (&) to run the **Clear-Variable** command in a new scope.</span></span>
<span data-ttu-id="44371-117">Die Variable wird im untergeordneten Bereich gelöscht (obwohl sie nicht vorhanden war), aber nicht im lokalen Bereich.</span><span class="sxs-lookup"><span data-stu-id="44371-117">The variable is cleared in the child scope (although it did not exist), but it is not cleared in the local scope.</span></span>
<span data-ttu-id="44371-118">Der dritte Befehl, der den Wert von $A abruft, zeigt, dass der Wert 3 nicht beeinträchtigt ist.</span><span class="sxs-lookup"><span data-stu-id="44371-118">The third command, which gets the value of $A, shows that the value 3 is unaffected.</span></span>

### <span data-ttu-id="44371-119">Beispiel 3: Löschen des Werts der angegebenen Variablen</span><span class="sxs-lookup"><span data-stu-id="44371-119">Example 3: Delete the value of the specified variable</span></span>

```
PS C:\> Clear-Variable -Name "Processes"
```

<span data-ttu-id="44371-120">Mit diesem Befehl wird der Wert der Variablen mit dem Namen "Processes" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="44371-120">This command deletes the value of the variable named Processes.</span></span>
<span data-ttu-id="44371-121">Nachdem das Cmdlet den Vorgang abgeschlossen hat, ist die Variable namens Prozesse weiterhin vorhanden, der Wert ist jedoch NULL.</span><span class="sxs-lookup"><span data-stu-id="44371-121">After the cmdlet completes the operation, the variable named Processes still exists, but the value is null.</span></span>

## <span data-ttu-id="44371-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="44371-122">PARAMETERS</span></span>

### <span data-ttu-id="44371-123">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="44371-123">-Exclude</span></span>

<span data-ttu-id="44371-124">Gibt ein Array von Elementen an, die von diesem Cmdlet im Vorgang ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="44371-124">Specifies an array of items that this cmdlet omits in the operation.</span></span>
<span data-ttu-id="44371-125">Der Wert dieses Parameters qualifiziert den *Name* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="44371-125">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="44371-126">Geben Sie ein Namenselement oder -muster wie %%amp;quot;s\*%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="44371-126">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="44371-127">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="44371-127">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="44371-128">-Force</span><span class="sxs-lookup"><span data-stu-id="44371-128">-Force</span></span>

<span data-ttu-id="44371-129">Ermöglicht dem Cmdlet, eine Variable zu löschen, selbst wenn sie schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="44371-129">Allows the cmdlet to clear a variable even if it is read-only.</span></span>
<span data-ttu-id="44371-130">Selbst bei Verwendung des Force-Parameters kann das Cmdlet keine Konstanten löschen.</span><span class="sxs-lookup"><span data-stu-id="44371-130">Even using the Force parameter, the cmdlet cannot clear constants.</span></span>

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

### <span data-ttu-id="44371-131">-Include</span><span class="sxs-lookup"><span data-stu-id="44371-131">-Include</span></span>

<span data-ttu-id="44371-132">Gibt ein Array von Elementen an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="44371-132">Specifies an array of items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="44371-133">Der Wert dieses Parameters qualifiziert den *Name* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="44371-133">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="44371-134">Geben Sie ein Namenselement oder -muster wie %%amp;quot;s\*%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="44371-134">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="44371-135">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="44371-135">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="44371-136">-Name</span><span class="sxs-lookup"><span data-stu-id="44371-136">-Name</span></span>

<span data-ttu-id="44371-137">Gibt den Namen der zu löschenden Variablen an.</span><span class="sxs-lookup"><span data-stu-id="44371-137">Specifies the name of the variable to be cleared.</span></span>
<span data-ttu-id="44371-138">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="44371-138">Wildcards are permitted.</span></span>
<span data-ttu-id="44371-139">Dieser Parameter ist erforderlich, aber der Parametername („Name“) ist optional.</span><span class="sxs-lookup"><span data-stu-id="44371-139">This parameter is required, but the parameter name ("Name") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="44371-140">-PassThru</span><span class="sxs-lookup"><span data-stu-id="44371-140">-PassThru</span></span>

<span data-ttu-id="44371-141">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="44371-141">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="44371-142">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="44371-142">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="44371-143">-Bereich</span><span class="sxs-lookup"><span data-stu-id="44371-143">-Scope</span></span>

<span data-ttu-id="44371-144">Gibt den Bereich an, in dem dieser Alias gültig ist.</span><span class="sxs-lookup"><span data-stu-id="44371-144">Specifies the scope in which this alias is valid.</span></span>

<span data-ttu-id="44371-145">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="44371-145">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="44371-146">Global</span><span class="sxs-lookup"><span data-stu-id="44371-146">Global</span></span>
- <span data-ttu-id="44371-147">Lokal</span><span class="sxs-lookup"><span data-stu-id="44371-147">Local</span></span>
- <span data-ttu-id="44371-148">Skript</span><span class="sxs-lookup"><span data-stu-id="44371-148">Script</span></span>

<span data-ttu-id="44371-149">Sie können auch eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist) verwenden.</span><span class="sxs-lookup"><span data-stu-id="44371-149">You can also use a number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>
<span data-ttu-id="44371-150">Local ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="44371-150">Local is the default.</span></span>
<span data-ttu-id="44371-151">Weitere Informationen finden Sie unter „about_Scopes“.</span><span class="sxs-lookup"><span data-stu-id="44371-151">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="44371-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="44371-152">-Confirm</span></span>

<span data-ttu-id="44371-153">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="44371-153">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="44371-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="44371-154">-WhatIf</span></span>

<span data-ttu-id="44371-155">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="44371-155">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="44371-156">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="44371-156">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="44371-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="44371-157">CommonParameters</span></span>

<span data-ttu-id="44371-158">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="44371-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="44371-159">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="44371-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="44371-160">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="44371-160">INPUTS</span></span>

### <span data-ttu-id="44371-161">Keine</span><span class="sxs-lookup"><span data-stu-id="44371-161">None</span></span>

<span data-ttu-id="44371-162">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="44371-162">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="44371-163">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="44371-163">OUTPUTS</span></span>

### <span data-ttu-id="44371-164">None oder System. Management. Automation. psvariable</span><span class="sxs-lookup"><span data-stu-id="44371-164">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="44371-165">Wenn Sie den *passthru* -Parameter verwenden, generiert dieses Cmdlet ein **System. Management. Automation. psvariable** -Objekt, das die gelöschte Variable darstellt.</span><span class="sxs-lookup"><span data-stu-id="44371-165">When you use the *PassThru* parameter, this cmdlet generates a **System.Management.Automation.PSVariable** object representing the cleared variable.</span></span>
<span data-ttu-id="44371-166">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="44371-166">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="44371-167">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="44371-167">NOTES</span></span>

* <span data-ttu-id="44371-168">Verwenden Sie zum Löschen einer Variablen mit dem entsprechenden Wert Remove-Variable oder Remove-Item.</span><span class="sxs-lookup"><span data-stu-id="44371-168">To delete a variable, along with its value, use Remove-Variable or Remove-Item.</span></span>

  <span data-ttu-id="44371-169">Dieses Cmdlet löscht nicht die Werte von Variablen, die als Konstanten festgelegt oder im Besitz des Systems sind, auch wenn Sie den *Force* -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="44371-169">This cmdlet does not delete the values of variables that are set as constants or owned by the system, even if you use the *Force* parameter.</span></span>

  <span data-ttu-id="44371-170">Wenn die Variable, die Sie löschen, nicht vorhanden ist, hat das Cmdlet keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="44371-170">If the variable that you are clearing does not exist, the cmdlet has no effect.</span></span>
<span data-ttu-id="44371-171">Es wird keine Variable wird mit dem Wert „null“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="44371-171">It does not create a variable with a null value.</span></span>

  <span data-ttu-id="44371-172">Sie können auch über den integrierten Alias CLV auf **Clear-Variable** verweisen.</span><span class="sxs-lookup"><span data-stu-id="44371-172">You can also refer to **Clear-Variable** by its built-in alias, clv.</span></span>
<span data-ttu-id="44371-173">Weitere Informationen finden Sie unter %%amp;quot;about_Aliases%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="44371-173">For more information, see about_Aliases.</span></span>

*

## <span data-ttu-id="44371-174">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="44371-174">RELATED LINKS</span></span>

[<span data-ttu-id="44371-175">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="44371-175">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="44371-176">New-Variable</span><span class="sxs-lookup"><span data-stu-id="44371-176">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="44371-177">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="44371-177">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="44371-178">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="44371-178">Set-Variable</span></span>](Set-Variable.md)

