---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/clear-variable?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Variable
ms.openlocfilehash: 6208e9c1b7124c8faec1e3e87a6e815540d2b962
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211415"
---
# <span data-ttu-id="ab85f-103">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="ab85f-103">Clear-Variable</span></span>

## <span data-ttu-id="ab85f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ab85f-104">SYNOPSIS</span></span>
<span data-ttu-id="ab85f-105">Löscht den Wert einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="ab85f-105">Deletes the value of a variable.</span></span>

## <span data-ttu-id="ab85f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ab85f-106">SYNTAX</span></span>

```
Clear-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-PassThru]
 [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ab85f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ab85f-107">DESCRIPTION</span></span>

<span data-ttu-id="ab85f-108">Das **Clear-Variable-** Cmdlet löscht die in einer Variablen gespeicherten Daten, aber die Variable wird nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ab85f-108">The **Clear-Variable** cmdlet deletes the data stored in a variable, but it does not delete the variable.</span></span>
<span data-ttu-id="ab85f-109">Daher ist der Wert der Variablen NULL (leer).</span><span class="sxs-lookup"><span data-stu-id="ab85f-109">As a result, the value of the variable is NULL (empty).</span></span>
<span data-ttu-id="ab85f-110">Wenn die Variable einen angegebenen Daten-oder Objekttyp aufweist, behält dieses Cmdlet den Typ des in der Variablen gespeicherten Objekts bei.</span><span class="sxs-lookup"><span data-stu-id="ab85f-110">If the variable has a specified data or object type, this cmdlet preserves the type of the object stored in the variable.</span></span>

## <span data-ttu-id="ab85f-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ab85f-111">EXAMPLES</span></span>

### <span data-ttu-id="ab85f-112">Beispiel 1: Entfernen des Werts von globalen Variablen, die mit einer Such Zeichenfolge beginnen</span><span class="sxs-lookup"><span data-stu-id="ab85f-112">Example 1: Remove the value of global variables that begin with a search string</span></span>

```
PS C:\> Clear-Variable my* -Scope Global
```

<span data-ttu-id="ab85f-113">Dieser Befehl entfernt den Wert von globalen Variablen, deren Namen mit "My" beginnen.</span><span class="sxs-lookup"><span data-stu-id="ab85f-113">This command removes the value of global variables that have names that begin with my.</span></span>

### <span data-ttu-id="ab85f-114">Beispiel 2: Löschen einer Variablen in einem untergeordneten Bereich, aber nicht im übergeordneten Bereich</span><span class="sxs-lookup"><span data-stu-id="ab85f-114">Example 2: Clear a variable in a child scope but not the parent scope</span></span>

```
PS C:\> $a=3
PS C:\> &{ Clear-Variable a }
PS C:\> $a
3
```

<span data-ttu-id="ab85f-115">Diese Befehle veranschaulichen, dass durch das Löschen einer Variablen in einem untergeordneten Bereich der Wert im übergeordneten Bereich nicht gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="ab85f-115">These commands demonstrate that clearing a variable in a child scope does not clear the value in the parent scope.</span></span>
<span data-ttu-id="ab85f-116">Mit dem ersten Befehl wird der Wert der Variablen $A auf 3 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ab85f-116">The first command sets the value of the variable $A to 3.</span></span>
<span data-ttu-id="ab85f-117">Der zweite Befehl verwendet den Aufruf Operator (&), um den **Clear-Variable-** Befehl in einem neuen Bereich auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ab85f-117">The second command uses the invoke operator (&) to run the **Clear-Variable** command in a new scope.</span></span>
<span data-ttu-id="ab85f-118">Die Variable wird im untergeordneten Bereich gelöscht (obwohl sie nicht vorhanden war), aber nicht im lokalen Bereich.</span><span class="sxs-lookup"><span data-stu-id="ab85f-118">The variable is cleared in the child scope (although it did not exist), but it is not cleared in the local scope.</span></span>
<span data-ttu-id="ab85f-119">Der dritte Befehl, der den Wert von $A abruft, zeigt, dass der Wert 3 nicht beeinträchtigt ist.</span><span class="sxs-lookup"><span data-stu-id="ab85f-119">The third command, which gets the value of $A, shows that the value 3 is unaffected.</span></span>

### <span data-ttu-id="ab85f-120">Beispiel 3: Löschen des Werts der angegebenen Variablen</span><span class="sxs-lookup"><span data-stu-id="ab85f-120">Example 3: Delete the value of the specified variable</span></span>

```
PS C:\> Clear-Variable -Name "Processes"
```

<span data-ttu-id="ab85f-121">Mit diesem Befehl wird der Wert der Variablen mit dem Namen "Processes" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ab85f-121">This command deletes the value of the variable named Processes.</span></span>
<span data-ttu-id="ab85f-122">Nachdem das Cmdlet den Vorgang abgeschlossen hat, ist die Variable namens Prozesse weiterhin vorhanden, der Wert ist jedoch NULL.</span><span class="sxs-lookup"><span data-stu-id="ab85f-122">After the cmdlet completes the operation, the variable named Processes still exists, but the value is null.</span></span>

## <span data-ttu-id="ab85f-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ab85f-123">PARAMETERS</span></span>

### <span data-ttu-id="ab85f-124">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="ab85f-124">-Exclude</span></span>

<span data-ttu-id="ab85f-125">Gibt ein Array von Elementen an, die von diesem Cmdlet im Vorgang ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="ab85f-125">Specifies an array of items that this cmdlet omits in the operation.</span></span>
<span data-ttu-id="ab85f-126">Der Wert dieses Parameters qualifiziert den *Name* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="ab85f-126">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="ab85f-127">Geben Sie ein Namenselement oder -muster wie %%amp;quot;s\*%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="ab85f-127">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="ab85f-128">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ab85f-128">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="ab85f-129">-Force</span><span class="sxs-lookup"><span data-stu-id="ab85f-129">-Force</span></span>

<span data-ttu-id="ab85f-130">Ermöglicht dem Cmdlet, eine Variable zu löschen, selbst wenn sie schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="ab85f-130">Allows the cmdlet to clear a variable even if it is read-only.</span></span>
<span data-ttu-id="ab85f-131">Selbst bei Verwendung des Force-Parameters kann das Cmdlet keine Konstanten löschen.</span><span class="sxs-lookup"><span data-stu-id="ab85f-131">Even using the Force parameter, the cmdlet cannot clear constants.</span></span>

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

### <span data-ttu-id="ab85f-132">-Include</span><span class="sxs-lookup"><span data-stu-id="ab85f-132">-Include</span></span>

<span data-ttu-id="ab85f-133">Gibt ein Array von Elementen an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="ab85f-133">Specifies an array of items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="ab85f-134">Der Wert dieses Parameters qualifiziert den *Name* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="ab85f-134">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="ab85f-135">Geben Sie ein Namenselement oder -muster wie %%amp;quot;s\*%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="ab85f-135">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="ab85f-136">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ab85f-136">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="ab85f-137">-Name</span><span class="sxs-lookup"><span data-stu-id="ab85f-137">-Name</span></span>

<span data-ttu-id="ab85f-138">Gibt den Namen der zu löschenden Variablen an.</span><span class="sxs-lookup"><span data-stu-id="ab85f-138">Specifies the name of the variable to be cleared.</span></span>
<span data-ttu-id="ab85f-139">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ab85f-139">Wildcards are permitted.</span></span>
<span data-ttu-id="ab85f-140">Dieser Parameter ist erforderlich, aber der Parametername („Name“) ist optional.</span><span class="sxs-lookup"><span data-stu-id="ab85f-140">This parameter is required, but the parameter name ("Name") is optional.</span></span>

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

### <span data-ttu-id="ab85f-141">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ab85f-141">-PassThru</span></span>

<span data-ttu-id="ab85f-142">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="ab85f-142">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="ab85f-143">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="ab85f-143">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="ab85f-144">-Bereich</span><span class="sxs-lookup"><span data-stu-id="ab85f-144">-Scope</span></span>

<span data-ttu-id="ab85f-145">Gibt den Bereich an, in dem dieser Alias gültig ist.</span><span class="sxs-lookup"><span data-stu-id="ab85f-145">Specifies the scope in which this alias is valid.</span></span>

<span data-ttu-id="ab85f-146">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="ab85f-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ab85f-147">Global</span><span class="sxs-lookup"><span data-stu-id="ab85f-147">Global</span></span>
- <span data-ttu-id="ab85f-148">Lokal</span><span class="sxs-lookup"><span data-stu-id="ab85f-148">Local</span></span>
- <span data-ttu-id="ab85f-149">Skript</span><span class="sxs-lookup"><span data-stu-id="ab85f-149">Script</span></span>

<span data-ttu-id="ab85f-150">Sie können auch eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist) verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab85f-150">You can also use a number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>
<span data-ttu-id="ab85f-151">Local ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="ab85f-151">Local is the default.</span></span>
<span data-ttu-id="ab85f-152">Weitere Informationen finden Sie unter „about_Scopes“.</span><span class="sxs-lookup"><span data-stu-id="ab85f-152">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="ab85f-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ab85f-153">-Confirm</span></span>

<span data-ttu-id="ab85f-154">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ab85f-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ab85f-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ab85f-155">-WhatIf</span></span>

<span data-ttu-id="ab85f-156">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab85f-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ab85f-157">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ab85f-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ab85f-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ab85f-158">CommonParameters</span></span>

<span data-ttu-id="ab85f-159">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ab85f-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ab85f-160">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ab85f-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ab85f-161">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ab85f-161">INPUTS</span></span>

### <span data-ttu-id="ab85f-162">Keine</span><span class="sxs-lookup"><span data-stu-id="ab85f-162">None</span></span>

<span data-ttu-id="ab85f-163">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="ab85f-163">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="ab85f-164">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ab85f-164">OUTPUTS</span></span>

### <span data-ttu-id="ab85f-165">None oder System. Management. Automation. psvariable</span><span class="sxs-lookup"><span data-stu-id="ab85f-165">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="ab85f-166">Wenn Sie den *passthru* -Parameter verwenden, generiert dieses Cmdlet ein **System. Management. Automation. psvariable** -Objekt, das die gelöschte Variable darstellt.</span><span class="sxs-lookup"><span data-stu-id="ab85f-166">When you use the *PassThru* parameter, this cmdlet generates a **System.Management.Automation.PSVariable** object representing the cleared variable.</span></span>
<span data-ttu-id="ab85f-167">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="ab85f-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ab85f-168">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ab85f-168">NOTES</span></span>

* <span data-ttu-id="ab85f-169">Verwenden Sie zum Löschen einer Variablen mit dem entsprechenden Wert Remove-Variable oder Remove-Item.</span><span class="sxs-lookup"><span data-stu-id="ab85f-169">To delete a variable, along with its value, use Remove-Variable or Remove-Item.</span></span>

  <span data-ttu-id="ab85f-170">Dieses Cmdlet löscht nicht die Werte von Variablen, die als Konstanten festgelegt oder im Besitz des Systems sind, auch wenn Sie den *Force* -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab85f-170">This cmdlet does not delete the values of variables that are set as constants or owned by the system, even if you use the *Force* parameter.</span></span>

  <span data-ttu-id="ab85f-171">Wenn die Variable, die Sie löschen, nicht vorhanden ist, hat das Cmdlet keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="ab85f-171">If the variable that you are clearing does not exist, the cmdlet has no effect.</span></span>
<span data-ttu-id="ab85f-172">Es wird keine Variable wird mit dem Wert „null“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="ab85f-172">It does not create a variable with a null value.</span></span>

  <span data-ttu-id="ab85f-173">Sie können auch über den integrierten Alias CLV auf **Clear-Variable** verweisen.</span><span class="sxs-lookup"><span data-stu-id="ab85f-173">You can also refer to **Clear-Variable** by its built-in alias, clv.</span></span>
<span data-ttu-id="ab85f-174">Weitere Informationen finden Sie unter %%amp;quot;about_Aliases%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="ab85f-174">For more information, see about_Aliases.</span></span>

*

## <span data-ttu-id="ab85f-175">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ab85f-175">RELATED LINKS</span></span>

[<span data-ttu-id="ab85f-176">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="ab85f-176">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="ab85f-177">New-Variable</span><span class="sxs-lookup"><span data-stu-id="ab85f-177">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="ab85f-178">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="ab85f-178">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="ab85f-179">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="ab85f-179">Set-Variable</span></span>](Set-Variable.md)
