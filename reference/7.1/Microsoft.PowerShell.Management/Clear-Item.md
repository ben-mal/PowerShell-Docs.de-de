---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Item
ms.openlocfilehash: b03e6a68da933dc0da6bfce92201825f70b77b19
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217607"
---
# <span data-ttu-id="91410-103">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="91410-103">Clear-Item</span></span>

## <span data-ttu-id="91410-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="91410-104">SYNOPSIS</span></span>
<span data-ttu-id="91410-105">Löscht den Inhalt eines Elements, löscht das Element jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="91410-105">Clears the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="91410-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="91410-106">SYNTAX</span></span>

### <span data-ttu-id="91410-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="91410-107">Path (Default)</span></span>

```
Clear-Item [-Path] <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="91410-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="91410-108">LiteralPath</span></span>

```
Clear-Item -LiteralPath <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="91410-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="91410-109">DESCRIPTION</span></span>

<span data-ttu-id="91410-110">Mit dem- `Clear-Item` Cmdlet wird der Inhalt eines Elements gelöscht, aber das Element wird nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="91410-110">The `Clear-Item` cmdlet clears the content of an item, but it does not delete the item.</span></span>
<span data-ttu-id="91410-111">Beispielsweise kann das `Clear-Item` Cmdlet den Wert einer Variablen löschen, die Variable wird jedoch nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="91410-111">For example, the `Clear-Item` cmdlet can delete the value of a variable, but it does not delete the variable.</span></span> <span data-ttu-id="91410-112">Der Wert, der zum Darstellen eines gelöschten Elements verwendet wird, wird von jedem PowerShell-Anbieter definiert.</span><span class="sxs-lookup"><span data-stu-id="91410-112">The value that used to represent a cleared item is defined by each PowerShell provider.</span></span>
<span data-ttu-id="91410-113">Dieses Cmdlet ähnelt `Clear-Content` , funktioniert jedoch mit Aliasen und Variablen anstelle von-Dateien.</span><span class="sxs-lookup"><span data-stu-id="91410-113">This cmdlet is similar to `Clear-Content`, but it works on aliases and variables, instead of files.</span></span>

## <span data-ttu-id="91410-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="91410-114">EXAMPLES</span></span>

### <span data-ttu-id="91410-115">Beispiel 1: Löschen des Werts einer Variablen</span><span class="sxs-lookup"><span data-stu-id="91410-115">Example 1: Clear the value of a variable</span></span>

<span data-ttu-id="91410-116">Dieser Befehl löscht den Wert der Variablen mit dem Namen `TestVar1` .</span><span class="sxs-lookup"><span data-stu-id="91410-116">This command clears the value of the variable named `TestVar1`.</span></span>
<span data-ttu-id="91410-117">Die Variable bleibt erhalten und ist gültig, aber ihr Wert ist auf festgelegt `$null` .</span><span class="sxs-lookup"><span data-stu-id="91410-117">The variable remains and is valid, but its value is set to `$null`.</span></span>
<span data-ttu-id="91410-118">Dem Variablennamen wird das Präfix vorangestellt `Variable:` , um den PowerShell-Variablen Anbieter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="91410-118">The variable name is prefixed with `Variable:` to indicate the PowerShell Variable provider.</span></span>

<span data-ttu-id="91410-119">Die alternativen Befehle zeigen, dass Sie zum Erreichen desselben Ergebnisses zum PowerShell `Variable:` -Laufwerk wechseln und dann den Befehl ausführen können `Clear-Item` .</span><span class="sxs-lookup"><span data-stu-id="91410-119">The alternate commands show that, to get the same result, you can switch to the PowerShell `Variable:` drive and then run the `Clear-Item` command.</span></span>

```powershell
Clear-Item Variable:TestVar1
```

```
Set-Location Variable:
PS Variable:\> Clear-Item TestVar1
```

### <span data-ttu-id="91410-120">Beispiel 2: Löschen aller Registrierungseinträge</span><span class="sxs-lookup"><span data-stu-id="91410-120">Example 2: Clear all registry entries</span></span>

<span data-ttu-id="91410-121">Mit diesem Befehl werden alle Registrierungseinträge im Unterschlüssel "MyKey" gelöscht, aber erst nach Aufforderung zur Bestätigung ihrer Absicht.</span><span class="sxs-lookup"><span data-stu-id="91410-121">This command clears all registry entries in the "MyKey" subkey, but only after prompting you to confirm your intent.</span></span>
<span data-ttu-id="91410-122">Der Unterschlüssel "MyKey" wird nicht gelöscht oder wirkt sich nicht auf andere Registrierungsschlüssel oder-Einträge aus.</span><span class="sxs-lookup"><span data-stu-id="91410-122">It does not delete the "MyKey" subkey or affect any other registry keys or entries.</span></span>
<span data-ttu-id="91410-123">Mit dem **Include** -Parameter und dem **Exclude** -Parameter können Sie bestimmte Registrierungsschlüssel angeben, Sie können damit jedoch keine Registrierungseinträge angeben.</span><span class="sxs-lookup"><span data-stu-id="91410-123">You can use the **Include** and **Exclude** parameters to identify particular registry keys, but you cannot use them to identify registry entries.</span></span>

- <span data-ttu-id="91410-124">Bestimmte Registrierungseinträge können Sie mit dem Cmdlet `Remove-ItemProperty` löschen.</span><span class="sxs-lookup"><span data-stu-id="91410-124">To delete particular registry entries, use the `Remove-ItemProperty` cmdlet.</span></span>
- <span data-ttu-id="91410-125">Zum Löschen des Werts eines Registrierungs Eintrags verwenden Sie `Clear-ItemProperty cmdlet` .</span><span class="sxs-lookup"><span data-stu-id="91410-125">To delete the value of a registry entry, use the `Clear-ItemProperty cmdlet`.</span></span>

```powershell
Clear-Item HKLM:\Software\MyCompany\MyKey -Confirm
```

## <span data-ttu-id="91410-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="91410-126">PARAMETERS</span></span>

### <span data-ttu-id="91410-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="91410-127">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="91410-128">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="91410-128">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="91410-129">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="91410-129">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="91410-130">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="91410-130">-Exclude</span></span>

<span data-ttu-id="91410-131">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="91410-131">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="91410-132">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="91410-132">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="91410-133">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="91410-133">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="91410-134">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="91410-134">Wildcard characters are permitted.</span></span> <span data-ttu-id="91410-135">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="91410-135">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="91410-136">-Filter</span><span class="sxs-lookup"><span data-stu-id="91410-136">-Filter</span></span>

<span data-ttu-id="91410-137">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="91410-137">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="91410-138">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="91410-138">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="91410-139">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="91410-139">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="91410-140">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="91410-140">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="91410-141">-Force</span><span class="sxs-lookup"><span data-stu-id="91410-141">-Force</span></span>

<span data-ttu-id="91410-142">Gibt an, dass das Cmdlet Elemente löscht, die anderweitig nicht geändert werden können, z. b. schreibgeschützte Aliase.</span><span class="sxs-lookup"><span data-stu-id="91410-142">Indicates that the cmdlet clears items that cannot otherwise be changed, such as read- only aliases.</span></span>
<span data-ttu-id="91410-143">Das Cmdlet kann keine Konstanten löschen.</span><span class="sxs-lookup"><span data-stu-id="91410-143">The cmdlet cannot clear constants.</span></span>
<span data-ttu-id="91410-144">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="91410-144">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="91410-145">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="91410-145">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="91410-146">Das Cmdlet kann Sicherheitseinschränkungen nicht außer Kraft setzen, auch wenn der **Force** -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="91410-146">The cmdlet cannot override security restrictions, even when the **Force** parameter is used.</span></span>

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

### <span data-ttu-id="91410-147">-Include</span><span class="sxs-lookup"><span data-stu-id="91410-147">-Include</span></span>

<span data-ttu-id="91410-148">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="91410-148">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="91410-149">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="91410-149">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="91410-150">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="91410-150">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="91410-151">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="91410-151">Wildcard characters are permitted.</span></span> <span data-ttu-id="91410-152">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="91410-152">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="91410-153">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="91410-153">-LiteralPath</span></span>

<span data-ttu-id="91410-154">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="91410-154">Specifies a path to one or more locations.</span></span> <span data-ttu-id="91410-155">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="91410-155">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="91410-156">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="91410-156">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="91410-157">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="91410-157">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="91410-158">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="91410-158">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="91410-159">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="91410-159">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="91410-160">-Path</span><span class="sxs-lookup"><span data-stu-id="91410-160">-Path</span></span>

<span data-ttu-id="91410-161">Gibt den Pfad zu den Elementen an, die gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="91410-161">Specifies the path to the items being cleared.</span></span>
<span data-ttu-id="91410-162">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="91410-162">Wildcard characters are permitted.</span></span>
<span data-ttu-id="91410-163">Dieser Parameter ist erforderlich, aber der Parameter Name **path** ist optional.</span><span class="sxs-lookup"><span data-stu-id="91410-163">This parameter is required, but the parameter name **Path** is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="91410-164">-Confirm</span><span class="sxs-lookup"><span data-stu-id="91410-164">-Confirm</span></span>

<span data-ttu-id="91410-165">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="91410-165">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="91410-166">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="91410-166">-WhatIf</span></span>

<span data-ttu-id="91410-167">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="91410-167">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="91410-168">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="91410-168">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="91410-169">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="91410-169">CommonParameters</span></span>

<span data-ttu-id="91410-170">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="91410-170">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="91410-171">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="91410-171">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="91410-172">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="91410-172">INPUTS</span></span>

### <span data-ttu-id="91410-173">System.String</span><span class="sxs-lookup"><span data-stu-id="91410-173">System.String</span></span>

<span data-ttu-id="91410-174">Sie können eine Pfad Zeichenfolge über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="91410-174">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="91410-175">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="91410-175">OUTPUTS</span></span>

### <span data-ttu-id="91410-176">Keine</span><span class="sxs-lookup"><span data-stu-id="91410-176">None</span></span>

<span data-ttu-id="91410-177">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="91410-177">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="91410-178">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="91410-178">NOTES</span></span>

- <span data-ttu-id="91410-179">Das- `Clear-Item` Cmdlet wird nur von mehreren PowerShell-Anbietern unterstützt, einschließlich **Alias** , **Umgebung** , **Funktion** , **Registrierung** und **Variablen** Anbietern.</span><span class="sxs-lookup"><span data-stu-id="91410-179">The `Clear-Item` cmdlet is supported only by several PowerShell providers, including the **Alias** , **Environment** , **Function** , **Registry** , and **Variable** providers.</span></span> <span data-ttu-id="91410-180">Daher können Sie verwenden, `Clear-Item` um den Inhalt von Elementen in den anbiefenamespaces zu löschen.</span><span class="sxs-lookup"><span data-stu-id="91410-180">As such, you can use `Clear-Item` to delete the content of items in the provider namespaces.</span></span> <span data-ttu-id="91410-181">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="91410-181">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="91410-182">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="91410-182">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
- <span data-ttu-id="91410-183">Sie können nicht verwenden `Clear-Item` , um den Inhalt einer Datei zu löschen, da der PowerShell-Dateisystem Anbieter dieses Cmdlet nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="91410-183">You cannot use `Clear-Item` to delete the contents of a file, because the PowerShell FileSystem provider does not support this cmdlet.</span></span> <span data-ttu-id="91410-184">Um Dateien zu löschen, verwenden Sie die `Clear-Content` .</span><span class="sxs-lookup"><span data-stu-id="91410-184">To clear files, use the `Clear-Content`.</span></span>

## <span data-ttu-id="91410-185">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="91410-185">RELATED LINKS</span></span>

[<span data-ttu-id="91410-186">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="91410-186">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="91410-187">Get-Item</span><span class="sxs-lookup"><span data-stu-id="91410-187">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="91410-188">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="91410-188">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="91410-189">Move-Item</span><span class="sxs-lookup"><span data-stu-id="91410-189">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="91410-190">New-Item</span><span class="sxs-lookup"><span data-stu-id="91410-190">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="91410-191">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="91410-191">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="91410-192">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="91410-192">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="91410-193">Set-Item</span><span class="sxs-lookup"><span data-stu-id="91410-193">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="91410-194">about_Providers</span><span class="sxs-lookup"><span data-stu-id="91410-194">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

