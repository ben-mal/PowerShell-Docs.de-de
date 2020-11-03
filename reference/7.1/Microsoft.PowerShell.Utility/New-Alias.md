---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-alias?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Alias
ms.openlocfilehash: b004cae919c32078d7c2d79174637a0fa4130ab1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217415"
---
# <span data-ttu-id="0e27e-103">New-Alias</span><span class="sxs-lookup"><span data-stu-id="0e27e-103">New-Alias</span></span>

## <span data-ttu-id="0e27e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0e27e-104">SYNOPSIS</span></span>
<span data-ttu-id="0e27e-105">Erstellt einen neuen Alias.</span><span class="sxs-lookup"><span data-stu-id="0e27e-105">Creates a new alias.</span></span>

## <span data-ttu-id="0e27e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e27e-106">SYNTAX</span></span>

```
New-Alias [-Name] <String> [-Value] <String> [-Description <String>] [-Option <ScopedItemOptions>] [-PassThru]
 [-Scope <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0e27e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0e27e-107">DESCRIPTION</span></span>

<span data-ttu-id="0e27e-108">Das **New-Alias-** Cmdlet erstellt einen neuen Alias in der aktuellen PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0e27e-108">The **New-Alias** cmdlet creates a new alias in the current PowerShell session.</span></span>
<span data-ttu-id="0e27e-109">Mithilfe von **New-Alias** erstellte Aliase werden nicht gespeichert, nachdem Sie die Sitzung verlassen oder PowerShell geschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="0e27e-109">Aliases created by using **New-Alias** are not saved after you exit the session or close PowerShell.</span></span>
<span data-ttu-id="0e27e-110">Sie können das Export-Alias-Cmdlet verwenden, um die Aliasinformationen in einer Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0e27e-110">You can use the Export-Alias cmdlet to save your alias information to a file.</span></span>
<span data-ttu-id="0e27e-111">Später können Sie **Import-Alias** verwenden, um die gespeicherten Alias Informationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0e27e-111">You can later use **Import-Alias** to retrieve that saved alias information.</span></span>

## <span data-ttu-id="0e27e-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0e27e-112">EXAMPLES</span></span>

### <span data-ttu-id="0e27e-113">Beispiel 1: Erstellen eines Alias für ein Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0e27e-113">Example 1: Create an alias for a cmdlet</span></span>

```
PS C:\> New-Alias -Name "List" Get-ChildItem
```

<span data-ttu-id="0e27e-114">Dieser Befehl erstellt einen Alias mit dem Namen List, der das Get-ChildItem Cmdlet darstellt.</span><span class="sxs-lookup"><span data-stu-id="0e27e-114">This command creates an alias named List to represent the Get-ChildItem cmdlet.</span></span>

### <span data-ttu-id="0e27e-115">Beispiel 2: Erstellen eines schreibgeschützten Alias für ein Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0e27e-115">Example 2: Create a read-only alias for a cmdlet</span></span>

```
PS C:\> New-Alias -Name "W" -Value Get-WmiObject -Description "quick wmi alias" -Option ReadOnly
PS C:\> Get-Alias -Name "W" | Format-List *
```

<span data-ttu-id="0e27e-116">Dieser Befehl erstellt einen Alias mit dem Namen "W", der das Get-WmiObject Cmdlet darstellt.</span><span class="sxs-lookup"><span data-stu-id="0e27e-116">This command creates an alias named W to represent the Get-WmiObject cmdlet.</span></span>
<span data-ttu-id="0e27e-117">Er erstellt eine Beschreibung, einen Quick WMI-Alias für den Alias und macht ihn als schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="0e27e-117">It creates a description, quick wmi alias, for the alias and makes it read-only.</span></span>
<span data-ttu-id="0e27e-118">Die letzte Zeile des Befehls verwendet Get-Alias, um den neuen Alias abzurufen, und übergibt ihn an Format-List, um alle zugehörigen Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0e27e-118">The last line of the command uses Get-Alias to get the new alias and pipes it to Format-List to display all of the information about it.</span></span>

## <span data-ttu-id="0e27e-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e27e-119">PARAMETERS</span></span>

### <span data-ttu-id="0e27e-120">-Description</span><span class="sxs-lookup"><span data-stu-id="0e27e-120">-Description</span></span>

<span data-ttu-id="0e27e-121">Gibt eine Beschreibung des Alias an.</span><span class="sxs-lookup"><span data-stu-id="0e27e-121">Specifies a description of the alias.</span></span>
<span data-ttu-id="0e27e-122">Sie können eine beliebige Zeichenfolge eingeben.</span><span class="sxs-lookup"><span data-stu-id="0e27e-122">You can type any string.</span></span>
<span data-ttu-id="0e27e-123">Wenn die Beschreibung Leerzeichen enthält, müssen Sie sie in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="0e27e-123">If the description includes spaces, enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="0e27e-124">-Force</span><span class="sxs-lookup"><span data-stu-id="0e27e-124">-Force</span></span>

<span data-ttu-id="0e27e-125">Gibt an, dass das Cmdlet wie Set-Alias verhält, wenn der benannte Alias bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0e27e-125">Indicates that the cmdlet acts like Set-Alias if the alias named already exists.</span></span>

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

### <span data-ttu-id="0e27e-126">-Name</span><span class="sxs-lookup"><span data-stu-id="0e27e-126">-Name</span></span>

<span data-ttu-id="0e27e-127">Gibt den neuen Alias an.</span><span class="sxs-lookup"><span data-stu-id="0e27e-127">Specifies the new alias.</span></span>
<span data-ttu-id="0e27e-128">Sie können alle alphanumerischen Zeichen in einem Alias verwenden, aber das erste Zeichen darf keine Zahl sein.</span><span class="sxs-lookup"><span data-stu-id="0e27e-128">You can use any alphanumeric characters in an alias, but the first character cannot be a number.</span></span>

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

### <span data-ttu-id="0e27e-129">-Option</span><span class="sxs-lookup"><span data-stu-id="0e27e-129">-Option</span></span>

<span data-ttu-id="0e27e-130">Gibt den Wert der **options** -Eigenschaft des Alias an.</span><span class="sxs-lookup"><span data-stu-id="0e27e-130">Specifies the value of the **Options** property of the alias.</span></span>
<span data-ttu-id="0e27e-131">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0e27e-131">Valid values are:</span></span>

- <span data-ttu-id="0e27e-132">None: der Alias weist keine Einschränkungen auf (Standardwert).</span><span class="sxs-lookup"><span data-stu-id="0e27e-132">None: The alias has no constraints (default value)</span></span>
- <span data-ttu-id="0e27e-133">Schreibgeschützt: der Alias kann gelöscht, aber nicht geändert werden, außer mithilfe des **Force** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="0e27e-133">ReadOnly: The alias can be deleted but cannot be changed except by using the **Force** parameter</span></span>
- <span data-ttu-id="0e27e-134">Constant: der Alias kann nicht gelöscht oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0e27e-134">Constant: The alias cannot be deleted or changed</span></span>
- <span data-ttu-id="0e27e-135">Privat: der Alias ist nur im aktuellen Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0e27e-135">Private: The alias is available only in the current scope</span></span>
- <span data-ttu-id="0e27e-136">Allscope: der Alias wird in neue Bereiche kopiert, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0e27e-136">AllScope: The alias is copied to any new scopes that are created</span></span>
- <span data-ttu-id="0e27e-137">Nicht angegeben: die Option ist nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="0e27e-137">Unspecified: The option is not specified</span></span>

<span data-ttu-id="0e27e-138">Um die **options** -Eigenschaft aller Aliase in der Sitzung anzuzeigen, geben Sie ein `Get-Alias | Format-Table -Property Name, Options -AutoSize` .</span><span class="sxs-lookup"><span data-stu-id="0e27e-138">To see the **Options** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -AutoSize`.</span></span>

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

### <span data-ttu-id="0e27e-139">-PassThru</span><span class="sxs-lookup"><span data-stu-id="0e27e-139">-PassThru</span></span>

<span data-ttu-id="0e27e-140">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="0e27e-140">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="0e27e-141">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="0e27e-141">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="0e27e-142">-Bereich</span><span class="sxs-lookup"><span data-stu-id="0e27e-142">-Scope</span></span>

<span data-ttu-id="0e27e-143">Gibt den Bereich des neuen Alias an.</span><span class="sxs-lookup"><span data-stu-id="0e27e-143">Specifies the scope of the new alias.</span></span>
<span data-ttu-id="0e27e-144">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="0e27e-144">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0e27e-145">Global</span><span class="sxs-lookup"><span data-stu-id="0e27e-145">Global</span></span>
- <span data-ttu-id="0e27e-146">Lokal</span><span class="sxs-lookup"><span data-stu-id="0e27e-146">Local</span></span>
- <span data-ttu-id="0e27e-147">Skript</span><span class="sxs-lookup"><span data-stu-id="0e27e-147">Script</span></span>
- <span data-ttu-id="0e27e-148">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist).</span><span class="sxs-lookup"><span data-stu-id="0e27e-148">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>

<span data-ttu-id="0e27e-149">Local ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="0e27e-149">Local is the default.</span></span>
<span data-ttu-id="0e27e-150">Weitere Informationen finden Sie unter „about_Scopes“.</span><span class="sxs-lookup"><span data-stu-id="0e27e-150">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="0e27e-151">-Value</span><span class="sxs-lookup"><span data-stu-id="0e27e-151">-Value</span></span>

<span data-ttu-id="0e27e-152">Gibt den Namen des Cmdlet- oder des Befehlselements an, dem ein Alias zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="0e27e-152">Specifies the name of the cmdlet or command element that is being aliased.</span></span>

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

### <span data-ttu-id="0e27e-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0e27e-153">-Confirm</span></span>

<span data-ttu-id="0e27e-154">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="0e27e-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0e27e-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0e27e-155">-WhatIf</span></span>

<span data-ttu-id="0e27e-156">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0e27e-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0e27e-157">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e27e-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0e27e-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0e27e-158">CommonParameters</span></span>

<span data-ttu-id="0e27e-159">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0e27e-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0e27e-160">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0e27e-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0e27e-161">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0e27e-161">INPUTS</span></span>

### <span data-ttu-id="0e27e-162">Keine</span><span class="sxs-lookup"><span data-stu-id="0e27e-162">None</span></span>

<span data-ttu-id="0e27e-163">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="0e27e-163">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="0e27e-164">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0e27e-164">OUTPUTS</span></span>

### <span data-ttu-id="0e27e-165">None oder System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="0e27e-165">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="0e27e-166">Wenn Sie den *passthru* -Parameter verwenden, generiert **New-Alias** ein **System. Management. Automation. AliasInfo** -Objekt, das den neuen Alias darstellt.</span><span class="sxs-lookup"><span data-stu-id="0e27e-166">When you use the *Passthru* parameter, **New-Alias** generates a **System.Management.Automation.AliasInfo** object representing the new alias.</span></span>
<span data-ttu-id="0e27e-167">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="0e27e-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0e27e-168">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0e27e-168">NOTES</span></span>

* <span data-ttu-id="0e27e-169">Um einen neuen Alias zu erstellen, verwenden Sie `Set-Alias` oder `New-Alias` .</span><span class="sxs-lookup"><span data-stu-id="0e27e-169">To create a new alias, use `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="0e27e-170">Um einen Alias zu ändern, verwenden Sie `Set-Alias` .</span><span class="sxs-lookup"><span data-stu-id="0e27e-170">To change an alias, use `Set-Alias`.</span></span> <span data-ttu-id="0e27e-171">Verwenden Sie zum Löschen eines Alias `Remove-Item` .</span><span class="sxs-lookup"><span data-stu-id="0e27e-171">To delete an alias, use `Remove-Item`.</span></span>

## <span data-ttu-id="0e27e-172">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0e27e-172">RELATED LINKS</span></span>

[<span data-ttu-id="0e27e-173">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="0e27e-173">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="0e27e-174">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="0e27e-174">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="0e27e-175">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="0e27e-175">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="0e27e-176">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="0e27e-176">Set-Alias</span></span>](Set-Alias.md)

