---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-ItemProperty
ms.openlocfilehash: 4fbd2677d6a978d4d144effe9607bceb376ad43f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600897"
---
# <span data-ttu-id="77cb1-102">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="77cb1-102">Rename-ItemProperty</span></span>

## <span data-ttu-id="77cb1-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="77cb1-103">SYNOPSIS</span></span>
<span data-ttu-id="77cb1-104">Benennt die Eigenschaft eines Elements um.</span><span class="sxs-lookup"><span data-stu-id="77cb1-104">Renames a property of an item.</span></span>

## <span data-ttu-id="77cb1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="77cb1-105">SYNTAX</span></span>

### <span data-ttu-id="77cb1-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="77cb1-106">Path (Default)</span></span>

```
Rename-ItemProperty [-Path] <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="77cb1-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="77cb1-107">LiteralPath</span></span>

```
Rename-ItemProperty -LiteralPath <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="77cb1-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="77cb1-108">DESCRIPTION</span></span>

<span data-ttu-id="77cb1-109">Das- `Rename-ItemProperty` Cmdlet ändert den Namen einer angegebenen Element Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="77cb1-109">The `Rename-ItemProperty` cmdlet changes the name of a specified item property.</span></span>
<span data-ttu-id="77cb1-110">Der Wert der Eigenschaft wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="77cb1-110">The value of the property is not changed.</span></span>
<span data-ttu-id="77cb1-111">Beispielsweise können Sie verwenden, `Rename-ItemProperty` um den Namen eines Registrierungs Eintrags zu ändern.</span><span class="sxs-lookup"><span data-stu-id="77cb1-111">For example, you can use `Rename-ItemProperty` to change the name of a registry entry.</span></span>

## <span data-ttu-id="77cb1-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="77cb1-112">EXAMPLES</span></span>

### <span data-ttu-id="77cb1-113">Beispiel 1: Umbenennen eines Registrierungs Eintrags</span><span class="sxs-lookup"><span data-stu-id="77cb1-113">Example 1: Rename a registry entry</span></span>

<span data-ttu-id="77cb1-114">Mit diesem Befehl wird der Registrierungs Eintrag "config", der im `HKEY_LOCAL_MACHINE\Software\SmpApplication` Schlüssel enthalten ist, in "oldconfig" umbenannt.</span><span class="sxs-lookup"><span data-stu-id="77cb1-114">This command renames the config registry entry that is contained in the `HKEY_LOCAL_MACHINE\Software\SmpApplication` key to "oldconfig".</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\Software\SmpApplication -Name config -NewName oldconfig
```

## <span data-ttu-id="77cb1-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="77cb1-115">PARAMETERS</span></span>

### <span data-ttu-id="77cb1-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="77cb1-116">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="77cb1-117">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="77cb1-117">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="77cb1-118">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="77cb1-118">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="77cb1-119">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="77cb1-119">-Exclude</span></span>

<span data-ttu-id="77cb1-120">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="77cb1-120">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="77cb1-121">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="77cb1-121">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="77cb1-122">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="77cb1-122">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="77cb1-123">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="77cb1-123">Wildcard characters are permitted.</span></span> <span data-ttu-id="77cb1-124">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="77cb1-124">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="77cb1-125">-Filter</span><span class="sxs-lookup"><span data-stu-id="77cb1-125">-Filter</span></span>

<span data-ttu-id="77cb1-126">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="77cb1-126">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="77cb1-127">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="77cb1-127">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="77cb1-128">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="77cb1-128">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="77cb1-129">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="77cb1-129">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="77cb1-130">-Force</span><span class="sxs-lookup"><span data-stu-id="77cb1-130">-Force</span></span>

<span data-ttu-id="77cb1-131">Erzwingt, dass das Cmdlet eine Eigenschaft eines Objekts umbenennen kann, auf das der Benutzer anderweitig nicht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="77cb1-131">Forces the cmdlet to rename a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="77cb1-132">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="77cb1-132">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="77cb1-133">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="77cb1-133">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="77cb1-134">-Include</span><span class="sxs-lookup"><span data-stu-id="77cb1-134">-Include</span></span>

<span data-ttu-id="77cb1-135">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="77cb1-135">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="77cb1-136">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="77cb1-136">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="77cb1-137">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="77cb1-137">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="77cb1-138">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="77cb1-138">Wildcard characters are permitted.</span></span> <span data-ttu-id="77cb1-139">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="77cb1-139">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="77cb1-140">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="77cb1-140">-LiteralPath</span></span>

<span data-ttu-id="77cb1-141">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="77cb1-141">Specifies a path to one or more locations.</span></span> <span data-ttu-id="77cb1-142">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="77cb1-142">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="77cb1-143">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="77cb1-143">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="77cb1-144">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="77cb1-144">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="77cb1-145">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="77cb1-145">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="77cb1-146">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="77cb1-146">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="77cb1-147">-Name</span><span class="sxs-lookup"><span data-stu-id="77cb1-147">-Name</span></span>

<span data-ttu-id="77cb1-148">Gibt den aktuellen Namen der umzubenennenden Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="77cb1-148">Specifies the current name of the property to rename.</span></span>

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

### <span data-ttu-id="77cb1-149">-Newname</span><span class="sxs-lookup"><span data-stu-id="77cb1-149">-NewName</span></span>

<span data-ttu-id="77cb1-150">Gibt den neuen Namen für die Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="77cb1-150">Specifies the new name for the property.</span></span>

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

### <span data-ttu-id="77cb1-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="77cb1-151">-PassThru</span></span>

<span data-ttu-id="77cb1-152">Gibt ein Objekt zurück, das die Element Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="77cb1-152">Returns an object that represents the item property.</span></span>
<span data-ttu-id="77cb1-153">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="77cb1-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="77cb1-154">-Path</span><span class="sxs-lookup"><span data-stu-id="77cb1-154">-Path</span></span>

<span data-ttu-id="77cb1-155">Gibt den Pfad des umzubenennenden Elements an.</span><span class="sxs-lookup"><span data-stu-id="77cb1-155">Specifies the path of the item to rename.</span></span>
<span data-ttu-id="77cb1-156">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="77cb1-156">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="77cb1-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="77cb1-157">-Confirm</span></span>

<span data-ttu-id="77cb1-158">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="77cb1-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="77cb1-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="77cb1-159">-WhatIf</span></span>

<span data-ttu-id="77cb1-160">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="77cb1-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="77cb1-161">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="77cb1-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="77cb1-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="77cb1-162">CommonParameters</span></span>

<span data-ttu-id="77cb1-163">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="77cb1-163">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="77cb1-164">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="77cb1-164">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="77cb1-165">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="77cb1-165">INPUTS</span></span>

### <span data-ttu-id="77cb1-166">System.String</span><span class="sxs-lookup"><span data-stu-id="77cb1-166">System.String</span></span>

<span data-ttu-id="77cb1-167">Sie können eine Zeichenfolge, die einen Pfad, aber keinen literalpfad enthält, an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="77cb1-167">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="77cb1-168">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="77cb1-168">OUTPUTS</span></span>

### <span data-ttu-id="77cb1-169">None, System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="77cb1-169">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="77cb1-170">Dieses Cmdlet generiert ein **pscustomobject-Objekt** , das die umbenannte Element Eigenschaft darstellt, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="77cb1-170">This cmdlet generates a **PSCustomObject** that represents the renamed item property, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="77cb1-171">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="77cb1-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="77cb1-172">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="77cb1-172">NOTES</span></span>

<span data-ttu-id="77cb1-173">`Remove-ItemProperty` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="77cb1-173">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="77cb1-174">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="77cb1-174">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="77cb1-175">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="77cb1-175">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="77cb1-176">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="77cb1-176">RELATED LINKS</span></span>

[<span data-ttu-id="77cb1-177">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="77cb1-177">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="77cb1-178">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="77cb1-178">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="77cb1-179">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="77cb1-179">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="77cb1-180">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="77cb1-180">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="77cb1-181">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="77cb1-181">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="77cb1-182">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="77cb1-182">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="77cb1-183">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="77cb1-183">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="77cb1-184">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="77cb1-184">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="77cb1-185">about_Providers</span><span class="sxs-lookup"><span data-stu-id="77cb1-185">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

