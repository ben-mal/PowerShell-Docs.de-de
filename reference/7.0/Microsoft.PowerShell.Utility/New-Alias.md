---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Alias
ms.openlocfilehash: f3f5f58060fb3ad0b5102eb46fe07859b426ed9c
ms.sourcegitcommit: c91f79576bc54e162bcc7adf78026417b2776687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2021
ms.locfileid: "106273895"
---
# <span data-ttu-id="e3283-103">New-Alias</span><span class="sxs-lookup"><span data-stu-id="e3283-103">New-Alias</span></span>

## <span data-ttu-id="e3283-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e3283-104">Synopsis</span></span>
<span data-ttu-id="e3283-105">Erstellt einen neuen Alias.</span><span class="sxs-lookup"><span data-stu-id="e3283-105">Creates a new alias.</span></span>

## <span data-ttu-id="e3283-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3283-106">Syntax</span></span>

```
New-Alias [-Name] <String> [-Value] <String> [-Description <String>] [-Option <ScopedItemOptions>] [-PassThru]
 [-Scope <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e3283-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e3283-107">Description</span></span>

<span data-ttu-id="e3283-108">Das- `New-Alias` Cmdlet erstellt einen neuen Alias in der aktuellen PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e3283-108">The `New-Alias` cmdlet creates a new alias in the current PowerShell session.</span></span> <span data-ttu-id="e3283-109">Aliase, die mithilfe von erstellt wurden, `New-Alias` werden nicht gespeichert, nachdem Sie die Sitzung verlassen oder PowerShell geschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="e3283-109">Aliases created by using `New-Alias` are not saved after you exit the session or close PowerShell.</span></span>
<span data-ttu-id="e3283-110">Sie können das `Export-Alias` Cmdlet verwenden, um die Alias Informationen in einer Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e3283-110">You can use the `Export-Alias` cmdlet to save your alias information to a file.</span></span> <span data-ttu-id="e3283-111">Später können Sie verwenden, `Import-Alias` um die gespeicherten Alias Informationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e3283-111">You can later use `Import-Alias` to retrieve that saved alias information.</span></span>

## <span data-ttu-id="e3283-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e3283-112">Examples</span></span>

### <span data-ttu-id="e3283-113">Beispiel 1: Erstellen eines Alias für ein Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e3283-113">Example 1: Create an alias for a cmdlet</span></span>

```
New-Alias -Name "List" Get-ChildItem
```

<span data-ttu-id="e3283-114">Dieser Befehl erstellt einen Alias mit dem Namen List, der das Get-ChildItem Cmdlet darstellt.</span><span class="sxs-lookup"><span data-stu-id="e3283-114">This command creates an alias named List to represent the Get-ChildItem cmdlet.</span></span>

### <span data-ttu-id="e3283-115">Beispiel 2: Erstellen eines schreibgeschützten Alias für ein Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e3283-115">Example 2: Create a read-only alias for a cmdlet</span></span>

```
New-Alias -Name "C" -Value Get-ChildItem -Description "quick gci alias" -Option ReadOnly
Get-Alias -Name "C" | Format-List *
```

<span data-ttu-id="e3283-116">Dieser Befehl erstellt einen Alias `C` mit dem Namen, um das `Get-ChildItem` Cmdlet darzustellen.</span><span class="sxs-lookup"><span data-stu-id="e3283-116">This command creates an alias named `C` to represent the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="e3283-117">Er erstellt eine Beschreibung, einen Quick WMI-Alias für den Alias und macht ihn als schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="e3283-117">It creates a description, quick wmi alias, for the alias and makes it read-only.</span></span> <span data-ttu-id="e3283-118">Die letzte Zeile des Befehls verwendet `Get-Alias` , um den neuen Alias zu erhalten, und leitet ihn an Format-List um alle Informationen darüber anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e3283-118">The last line of the command uses `Get-Alias` to get the new alias and pipes it to Format-List to display all of the information about it.</span></span>

## <span data-ttu-id="e3283-119">Parameter</span><span class="sxs-lookup"><span data-stu-id="e3283-119">Parameters</span></span>

### <span data-ttu-id="e3283-120">-Description</span><span class="sxs-lookup"><span data-stu-id="e3283-120">-Description</span></span>

<span data-ttu-id="e3283-121">Gibt eine Beschreibung des Alias an.</span><span class="sxs-lookup"><span data-stu-id="e3283-121">Specifies a description of the alias.</span></span> <span data-ttu-id="e3283-122">Sie können eine beliebige Zeichenfolge eingeben.</span><span class="sxs-lookup"><span data-stu-id="e3283-122">You can type any string.</span></span> <span data-ttu-id="e3283-123">Wenn die Beschreibung Leerzeichen enthält, müssen Sie sie in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="e3283-123">If the description includes spaces, enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="e3283-124">-Force</span><span class="sxs-lookup"><span data-stu-id="e3283-124">-Force</span></span>

<span data-ttu-id="e3283-125">Gibt an, dass das Cmdlet so verhält, als `Set-Alias` ob der Alias mit dem Namen bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e3283-125">Indicates that the cmdlet acts like `Set-Alias` if the alias named already exists.</span></span>

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

### <span data-ttu-id="e3283-126">-Name</span><span class="sxs-lookup"><span data-stu-id="e3283-126">-Name</span></span>

<span data-ttu-id="e3283-127">Gibt den neuen Alias an.</span><span class="sxs-lookup"><span data-stu-id="e3283-127">Specifies the new alias.</span></span> <span data-ttu-id="e3283-128">Sie können alle alphanumerischen Zeichen in einem Alias verwenden, aber das erste Zeichen darf keine Zahl sein.</span><span class="sxs-lookup"><span data-stu-id="e3283-128">You can use any alphanumeric characters in an alias, but the first character cannot be a number.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e3283-129">-Option</span><span class="sxs-lookup"><span data-stu-id="e3283-129">-Option</span></span>

<span data-ttu-id="e3283-130">Gibt den Wert der **options** -Eigenschaft des Alias an.</span><span class="sxs-lookup"><span data-stu-id="e3283-130">Specifies the value of the **Options** property of the alias.</span></span>
<span data-ttu-id="e3283-131">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="e3283-131">Valid values are:</span></span>

- <span data-ttu-id="e3283-132">`None`: Der Alias weist keine Einschränkungen auf (Standardwert).</span><span class="sxs-lookup"><span data-stu-id="e3283-132">`None`: The alias has no constraints (default value)</span></span>
- <span data-ttu-id="e3283-133">`ReadOnly`: Der Alias kann gelöscht, aber nicht geändert werden, außer mithilfe des **Force** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="e3283-133">`ReadOnly`: The alias can be deleted but cannot be changed except by using the **Force** parameter</span></span>
- <span data-ttu-id="e3283-134">`Constant`: Der Alias kann nicht gelöscht oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e3283-134">`Constant`: The alias cannot be deleted or changed</span></span>
- <span data-ttu-id="e3283-135">`Private`: Der Alias ist nur im aktuellen Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e3283-135">`Private`: The alias is available only in the current scope</span></span>
- <span data-ttu-id="e3283-136">`AllScope`: Der Alias wird in neue Bereiche kopiert, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e3283-136">`AllScope`: The alias is copied to any new scopes that are created</span></span>
- <span data-ttu-id="e3283-137">`Unspecified`: Die Option ist nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="e3283-137">`Unspecified`: The option is not specified</span></span>

<span data-ttu-id="e3283-138">Diese Werte werden als Flag-basierte Enumeration definiert.</span><span class="sxs-lookup"><span data-stu-id="e3283-138">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="e3283-139">Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e3283-139">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="e3283-140">Die Werte können als Array von Werten an den **options** Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="e3283-140">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="e3283-141">Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert.</span><span class="sxs-lookup"><span data-stu-id="e3283-141">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="e3283-142">Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e3283-142">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

<span data-ttu-id="e3283-143">Um die **options** -Eigenschaft aller Aliase in der Sitzung anzuzeigen, geben Sie ein `Get-Alias | Format-Table -Property Name, Options -AutoSize` .</span><span class="sxs-lookup"><span data-stu-id="e3283-143">To see the **Options** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -AutoSize`.</span></span>

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: [System.Management.Automation.ScopedItemOptions]::None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3283-144">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e3283-144">-PassThru</span></span>

<span data-ttu-id="e3283-145">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="e3283-145">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="e3283-146">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="e3283-146">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="e3283-147">-Bereich</span><span class="sxs-lookup"><span data-stu-id="e3283-147">-Scope</span></span>

<span data-ttu-id="e3283-148">Gibt den Bereich des neuen Alias an.</span><span class="sxs-lookup"><span data-stu-id="e3283-148">Specifies the scope of the new alias.</span></span> <span data-ttu-id="e3283-149">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="e3283-149">The acceptable values for this parameter are:</span></span>

- `Global`
- `Local`
- `Script`
- <span data-ttu-id="e3283-150">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei `0` der aktuelle Bereich und dessen über `1` geordnetes Element ist).</span><span class="sxs-lookup"><span data-stu-id="e3283-150">A number relative to the current scope (0 through the number of scopes, where `0` is the current scope and `1` is its parent).</span></span>

<span data-ttu-id="e3283-151">`Local` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="e3283-151">`Local` is the default.</span></span> <span data-ttu-id="e3283-152">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="e3283-152">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="e3283-153">-Value</span><span class="sxs-lookup"><span data-stu-id="e3283-153">-Value</span></span>

<span data-ttu-id="e3283-154">Gibt den Namen des Cmdlet- oder des Befehlselements an, dem ein Alias zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="e3283-154">Specifies the name of the cmdlet or command element that is being aliased.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e3283-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e3283-155">-Confirm</span></span>

<span data-ttu-id="e3283-156">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="e3283-156">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e3283-157">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e3283-157">-WhatIf</span></span>

<span data-ttu-id="e3283-158">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e3283-158">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e3283-159">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e3283-159">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e3283-160">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e3283-160">CommonParameters</span></span>

<span data-ttu-id="e3283-161">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e3283-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e3283-162">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e3283-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e3283-163">Eingaben</span><span class="sxs-lookup"><span data-stu-id="e3283-163">Inputs</span></span>

### <span data-ttu-id="e3283-164">Keine</span><span class="sxs-lookup"><span data-stu-id="e3283-164">None</span></span>

<span data-ttu-id="e3283-165">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="e3283-165">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="e3283-166">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="e3283-166">Outputs</span></span>

### <span data-ttu-id="e3283-167">None oder System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="e3283-167">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="e3283-168">Wenn Sie den **passthru** -Parameter verwenden, `New-Alias` generiert ein **System. Management. Automation. AliasInfo** -Objekt, das den neuen Alias darstellt.</span><span class="sxs-lookup"><span data-stu-id="e3283-168">When you use the **Passthru** parameter, `New-Alias` generates a **System.Management.Automation.AliasInfo** object representing the new alias.</span></span> <span data-ttu-id="e3283-169">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="e3283-169">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e3283-170">Notizen</span><span class="sxs-lookup"><span data-stu-id="e3283-170">Notes</span></span>

- <span data-ttu-id="e3283-171">Um einen neuen Alias zu erstellen, verwenden Sie `Set-Alias` oder `New-Alias` .</span><span class="sxs-lookup"><span data-stu-id="e3283-171">To create a new alias, use `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="e3283-172">Um einen Alias zu ändern, verwenden Sie `Set-Alias` .</span><span class="sxs-lookup"><span data-stu-id="e3283-172">To change an alias, use `Set-Alias`.</span></span> <span data-ttu-id="e3283-173">Verwenden Sie zum Löschen eines Alias `Remove-Item` .</span><span class="sxs-lookup"><span data-stu-id="e3283-173">To delete an alias, use `Remove-Item`.</span></span>

## <span data-ttu-id="e3283-174">Ähnliche Themen</span><span class="sxs-lookup"><span data-stu-id="e3283-174">Related Links</span></span>

[<span data-ttu-id="e3283-175">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="e3283-175">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="e3283-176">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="e3283-176">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="e3283-177">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="e3283-177">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="e3283-178">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="e3283-178">Set-Alias</span></span>](Set-Alias.md)
