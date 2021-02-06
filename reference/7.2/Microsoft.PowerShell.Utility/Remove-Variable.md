---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 07/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Variable
ms.openlocfilehash: 6b9d351b5092d96d7698a28d3de63a493d566c6d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600507"
---
# <span data-ttu-id="ecef9-102">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="ecef9-102">Remove-Variable</span></span>

## <span data-ttu-id="ecef9-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ecef9-103">SYNOPSIS</span></span>
<span data-ttu-id="ecef9-104">Löscht eine Variable und ihren Wert.</span><span class="sxs-lookup"><span data-stu-id="ecef9-104">Deletes a variable and its value.</span></span>

## <span data-ttu-id="ecef9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ecef9-105">SYNTAX</span></span>

```
Remove-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Scope <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ecef9-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ecef9-106">DESCRIPTION</span></span>

<span data-ttu-id="ecef9-107">Das `Remove-Variable` -Cmdlet löscht eine Variable und ihren Wert aus dem Gültigkeitsbereich, in dem Sie definiert ist, z. b. die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ecef9-107">The `Remove-Variable` cmdlet deletes a variable and its value from the scope in which it is defined, such as the current session.</span></span> <span data-ttu-id="ecef9-108">Mit diesem Cmdlet können Sie Variablen löschen, die als Konstanten festgelegt sind, oder solche, die dem System gehören.</span><span class="sxs-lookup"><span data-stu-id="ecef9-108">You cannot use this cmdlet to delete variables that are set as constants or those that are owned by the system.</span></span>

## <span data-ttu-id="ecef9-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ecef9-109">EXAMPLES</span></span>

### <span data-ttu-id="ecef9-110">Beispiel 1: Entfernen einer Variablen</span><span class="sxs-lookup"><span data-stu-id="ecef9-110">Example 1: Remove a variable</span></span>

```powershell
Remove-Variable Smp
```

<span data-ttu-id="ecef9-111">Mit diesem Befehl wird die `$Smp` Variable gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ecef9-111">This command deletes the `$Smp` variable.</span></span>

## <span data-ttu-id="ecef9-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ecef9-112">PARAMETERS</span></span>

### <span data-ttu-id="ecef9-113">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="ecef9-113">-Exclude</span></span>

<span data-ttu-id="ecef9-114">Gibt ein Array von Elementen an, die von diesem Cmdlet aus dem Vorgang ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="ecef9-114">Specifies an array of items that this cmdlet omits from the operation.</span></span> <span data-ttu-id="ecef9-115">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecef9-115">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="ecef9-116">Geben Sie ein Namenselement oder -muster wie %%amp;quot;s\*%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="ecef9-116">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="ecef9-117">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ecef9-117">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="ecef9-118">-Force</span><span class="sxs-lookup"><span data-stu-id="ecef9-118">-Force</span></span>

<span data-ttu-id="ecef9-119">Gibt an, dass das Cmdlet eine Variable entfernt, auch wenn Sie schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="ecef9-119">Indicates that the cmdlet removes a variable even if it is read-only.</span></span> <span data-ttu-id="ecef9-120">Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Konstante entfernen.</span><span class="sxs-lookup"><span data-stu-id="ecef9-120">Even using the **Force** parameter, the cmdlet cannot remove a constant.</span></span>

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

### <span data-ttu-id="ecef9-121">-Include</span><span class="sxs-lookup"><span data-stu-id="ecef9-121">-Include</span></span>

<span data-ttu-id="ecef9-122">Gibt ein Array von Elementen an, die dieses Cmdlet im Vorgang löscht.</span><span class="sxs-lookup"><span data-stu-id="ecef9-122">Specifies an array of items that this cmdlet deletes in the operation.</span></span> <span data-ttu-id="ecef9-123">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecef9-123">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="ecef9-124">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="ecef9-124">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="ecef9-125">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ecef9-125">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="ecef9-126">-Name</span><span class="sxs-lookup"><span data-stu-id="ecef9-126">-Name</span></span>

<span data-ttu-id="ecef9-127">Gibt den Namen der zu entfernenden Variablen an.</span><span class="sxs-lookup"><span data-stu-id="ecef9-127">Specifies the name of the variable to be removed.</span></span> <span data-ttu-id="ecef9-128">Der Parameter Name (**Name**) ist optional.</span><span class="sxs-lookup"><span data-stu-id="ecef9-128">The parameter name (**Name**) is optional.</span></span>
<span data-ttu-id="ecef9-129">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ecef9-129">Wildcards are permitted</span></span>

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

### <span data-ttu-id="ecef9-130">-Bereich</span><span class="sxs-lookup"><span data-stu-id="ecef9-130">-Scope</span></span>

<span data-ttu-id="ecef9-131">Ruft nur die Variablen im angegebenen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="ecef9-131">Gets only the variables in the specified scope.</span></span> <span data-ttu-id="ecef9-132">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="ecef9-132">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ecef9-133">Global</span><span class="sxs-lookup"><span data-stu-id="ecef9-133">Global</span></span>
- <span data-ttu-id="ecef9-134">Lokal</span><span class="sxs-lookup"><span data-stu-id="ecef9-134">Local</span></span>
- <span data-ttu-id="ecef9-135">Skript</span><span class="sxs-lookup"><span data-stu-id="ecef9-135">Script</span></span>
- <span data-ttu-id="ecef9-136">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist)</span><span class="sxs-lookup"><span data-stu-id="ecef9-136">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="ecef9-137">Local ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="ecef9-137">Local is the default.</span></span> <span data-ttu-id="ecef9-138">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="ecef9-138">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="ecef9-139">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ecef9-139">-Confirm</span></span>

<span data-ttu-id="ecef9-140">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ecef9-140">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ecef9-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ecef9-141">-WhatIf</span></span>

<span data-ttu-id="ecef9-142">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ecef9-142">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="ecef9-143">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ecef9-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ecef9-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ecef9-144">CommonParameters</span></span>

<span data-ttu-id="ecef9-145">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ecef9-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ecef9-146">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ecef9-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ecef9-147">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ecef9-147">INPUTS</span></span>

### <span data-ttu-id="ecef9-148">System. Management. Automation. psvariable</span><span class="sxs-lookup"><span data-stu-id="ecef9-148">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="ecef9-149">Sie können ein Variablen Objekt an übergeben `Remove-Variable` .</span><span class="sxs-lookup"><span data-stu-id="ecef9-149">You can pipe a variable object to `Remove-Variable`.</span></span>

## <span data-ttu-id="ecef9-150">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ecef9-150">OUTPUTS</span></span>

### <span data-ttu-id="ecef9-151">Keine</span><span class="sxs-lookup"><span data-stu-id="ecef9-151">None</span></span>

<span data-ttu-id="ecef9-152">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="ecef9-152">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="ecef9-153">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ecef9-153">NOTES</span></span>

- <span data-ttu-id="ecef9-154">Änderungen wirken sich nur auf den aktuellen Bereich aus, z. B. eine Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ecef9-154">Changes affect only the current scope, such as a session.</span></span> <span data-ttu-id="ecef9-155">Um eine Variable aus allen Sitzungen zu löschen, fügen Sie `Remove-Variable` Ihrem PowerShell-Profil einen Befehl hinzu.</span><span class="sxs-lookup"><span data-stu-id="ecef9-155">To delete a variable from all sessions, add a `Remove-Variable` command to your PowerShell profile.</span></span>

- <span data-ttu-id="ecef9-156">Sie können auch auf den `Remove-Variable` integrierten Alias verweisen `rv` .</span><span class="sxs-lookup"><span data-stu-id="ecef9-156">You can also refer to `Remove-Variable` by its built-in alias, `rv`.</span></span> <span data-ttu-id="ecef9-157">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="ecef9-157">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

## <span data-ttu-id="ecef9-158">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ecef9-158">RELATED LINKS</span></span>

[<span data-ttu-id="ecef9-159">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="ecef9-159">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="ecef9-160">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="ecef9-160">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="ecef9-161">New-Variable</span><span class="sxs-lookup"><span data-stu-id="ecef9-161">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="ecef9-162">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="ecef9-162">Set-Variable</span></span>](Set-Variable.md)
