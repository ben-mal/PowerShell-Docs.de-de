---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-itemproperty?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-ItemProperty
ms.openlocfilehash: 4ce6bce60a3f1e87a8512b32166fb3e22f7d737e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211532"
---
# <span data-ttu-id="13bff-103">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="13bff-103">Rename-ItemProperty</span></span>

## <span data-ttu-id="13bff-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="13bff-104">SYNOPSIS</span></span>
<span data-ttu-id="13bff-105">Benennt die Eigenschaft eines Elements um.</span><span class="sxs-lookup"><span data-stu-id="13bff-105">Renames a property of an item.</span></span>

## <span data-ttu-id="13bff-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="13bff-106">SYNTAX</span></span>

### <span data-ttu-id="13bff-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="13bff-107">Path (Default)</span></span>

```
Rename-ItemProperty [-Path] <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="13bff-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="13bff-108">LiteralPath</span></span>

```
Rename-ItemProperty -LiteralPath <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="13bff-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="13bff-109">DESCRIPTION</span></span>

<span data-ttu-id="13bff-110">Das- `Rename-ItemProperty` Cmdlet ändert den Namen einer angegebenen Element Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="13bff-110">The `Rename-ItemProperty` cmdlet changes the name of a specified item property.</span></span>
<span data-ttu-id="13bff-111">Der Wert der Eigenschaft wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="13bff-111">The value of the property is not changed.</span></span>
<span data-ttu-id="13bff-112">Beispielsweise können Sie verwenden, `Rename-ItemProperty` um den Namen eines Registrierungs Eintrags zu ändern.</span><span class="sxs-lookup"><span data-stu-id="13bff-112">For example, you can use `Rename-ItemProperty` to change the name of a registry entry.</span></span>

## <span data-ttu-id="13bff-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="13bff-113">EXAMPLES</span></span>

### <span data-ttu-id="13bff-114">Beispiel 1: Umbenennen eines Registrierungs Eintrags</span><span class="sxs-lookup"><span data-stu-id="13bff-114">Example 1: Rename a registry entry</span></span>

<span data-ttu-id="13bff-115">Mit diesem Befehl wird der Registrierungs Eintrag "config", der im `HKEY_LOCAL_MACHINE\Software\SmpApplication` Schlüssel enthalten ist, in "oldconfig" umbenannt.</span><span class="sxs-lookup"><span data-stu-id="13bff-115">This command renames the config registry entry that is contained in the `HKEY_LOCAL_MACHINE\Software\SmpApplication` key to "oldconfig".</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\Software\SmpApplication -Name config -NewName oldconfig
```

## <span data-ttu-id="13bff-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="13bff-116">PARAMETERS</span></span>

### <span data-ttu-id="13bff-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="13bff-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="13bff-118">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="13bff-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="13bff-119">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="13bff-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="13bff-120">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="13bff-120">-Exclude</span></span>

<span data-ttu-id="13bff-121">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="13bff-121">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="13bff-122">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="13bff-122">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="13bff-123">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="13bff-123">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="13bff-124">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="13bff-124">Wildcard characters are permitted.</span></span> <span data-ttu-id="13bff-125">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="13bff-125">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="13bff-126">-Filter</span><span class="sxs-lookup"><span data-stu-id="13bff-126">-Filter</span></span>

<span data-ttu-id="13bff-127">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="13bff-127">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="13bff-128">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="13bff-128">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="13bff-129">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="13bff-129">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="13bff-130">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="13bff-130">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="13bff-131">-Force</span><span class="sxs-lookup"><span data-stu-id="13bff-131">-Force</span></span>

<span data-ttu-id="13bff-132">Erzwingt, dass das Cmdlet eine Eigenschaft eines Objekts umbenennen kann, auf das der Benutzer anderweitig nicht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="13bff-132">Forces the cmdlet to rename a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="13bff-133">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="13bff-133">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="13bff-134">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="13bff-134">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="13bff-135">-Include</span><span class="sxs-lookup"><span data-stu-id="13bff-135">-Include</span></span>

<span data-ttu-id="13bff-136">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="13bff-136">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="13bff-137">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="13bff-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="13bff-138">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="13bff-138">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="13bff-139">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="13bff-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="13bff-140">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="13bff-140">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="13bff-141">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="13bff-141">-LiteralPath</span></span>

<span data-ttu-id="13bff-142">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="13bff-142">Specifies a path to one or more locations.</span></span> <span data-ttu-id="13bff-143">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="13bff-143">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="13bff-144">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="13bff-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="13bff-145">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="13bff-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="13bff-146">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="13bff-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="13bff-147">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="13bff-147">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="13bff-148">-Name</span><span class="sxs-lookup"><span data-stu-id="13bff-148">-Name</span></span>

<span data-ttu-id="13bff-149">Gibt den aktuellen Namen der umzubenennenden Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="13bff-149">Specifies the current name of the property to rename.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="13bff-150">-Newname</span><span class="sxs-lookup"><span data-stu-id="13bff-150">-NewName</span></span>

<span data-ttu-id="13bff-151">Gibt den neuen Namen für die Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="13bff-151">Specifies the new name for the property.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="13bff-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="13bff-152">-PassThru</span></span>

<span data-ttu-id="13bff-153">Gibt ein Objekt zurück, das die Element Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="13bff-153">Returns an object that represents the item property.</span></span>
<span data-ttu-id="13bff-154">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="13bff-154">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="13bff-155">-Path</span><span class="sxs-lookup"><span data-stu-id="13bff-155">-Path</span></span>

<span data-ttu-id="13bff-156">Gibt den Pfad des umzubenennenden Elements an.</span><span class="sxs-lookup"><span data-stu-id="13bff-156">Specifies the path of the item to rename.</span></span>
<span data-ttu-id="13bff-157">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="13bff-157">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="13bff-158">-Confirm</span><span class="sxs-lookup"><span data-stu-id="13bff-158">-Confirm</span></span>

<span data-ttu-id="13bff-159">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="13bff-159">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="13bff-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="13bff-160">-WhatIf</span></span>

<span data-ttu-id="13bff-161">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="13bff-161">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="13bff-162">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="13bff-162">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="13bff-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="13bff-163">CommonParameters</span></span>

<span data-ttu-id="13bff-164">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="13bff-164">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="13bff-165">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="13bff-165">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="13bff-166">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="13bff-166">INPUTS</span></span>

### <span data-ttu-id="13bff-167">System.String</span><span class="sxs-lookup"><span data-stu-id="13bff-167">System.String</span></span>

<span data-ttu-id="13bff-168">Sie können eine Zeichenfolge, die einen Pfad, aber keinen literalpfad enthält, an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="13bff-168">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="13bff-169">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="13bff-169">OUTPUTS</span></span>

### <span data-ttu-id="13bff-170">None, System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="13bff-170">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="13bff-171">Dieses Cmdlet generiert ein **pscustomobject-Objekt** , das die umbenannte Element Eigenschaft darstellt, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="13bff-171">This cmdlet generates a **PSCustomObject** that represents the renamed item property, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="13bff-172">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="13bff-172">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="13bff-173">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="13bff-173">NOTES</span></span>

<span data-ttu-id="13bff-174">`Remove-ItemProperty` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="13bff-174">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="13bff-175">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="13bff-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="13bff-176">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="13bff-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="13bff-177">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="13bff-177">RELATED LINKS</span></span>

[<span data-ttu-id="13bff-178">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="13bff-178">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="13bff-179">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="13bff-179">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="13bff-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="13bff-180">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="13bff-181">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="13bff-181">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="13bff-182">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="13bff-182">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="13bff-183">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="13bff-183">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="13bff-184">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="13bff-184">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="13bff-185">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="13bff-185">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="13bff-186">about_Providers</span><span class="sxs-lookup"><span data-stu-id="13bff-186">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

