---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Item
ms.openlocfilehash: fb3f95f51578f9dc02d9f68b3c0be5a6531aca17
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597362"
---
# <span data-ttu-id="5a234-102">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="5a234-102">Clear-Item</span></span>

## <span data-ttu-id="5a234-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5a234-103">SYNOPSIS</span></span>
<span data-ttu-id="5a234-104">Löscht den Inhalt eines Elements, löscht das Element jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="5a234-104">Clears the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="5a234-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5a234-105">SYNTAX</span></span>

### <span data-ttu-id="5a234-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="5a234-106">Path (Default)</span></span>

```
Clear-Item [-Path] <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5a234-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="5a234-107">LiteralPath</span></span>

```
Clear-Item -LiteralPath <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5a234-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5a234-108">DESCRIPTION</span></span>

<span data-ttu-id="5a234-109">Mit dem- `Clear-Item` Cmdlet wird der Inhalt eines Elements gelöscht, aber das Element wird nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="5a234-109">The `Clear-Item` cmdlet clears the content of an item, but it does not delete the item.</span></span>
<span data-ttu-id="5a234-110">Beispielsweise kann das `Clear-Item` Cmdlet den Wert einer Variablen löschen, die Variable wird jedoch nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="5a234-110">For example, the `Clear-Item` cmdlet can delete the value of a variable, but it does not delete the variable.</span></span> <span data-ttu-id="5a234-111">Der Wert, der zum Darstellen eines gelöschten Elements verwendet wird, wird von jedem PowerShell-Anbieter definiert.</span><span class="sxs-lookup"><span data-stu-id="5a234-111">The value that used to represent a cleared item is defined by each PowerShell provider.</span></span>
<span data-ttu-id="5a234-112">Dieses Cmdlet ähnelt `Clear-Content` , funktioniert jedoch mit Aliasen und Variablen anstelle von-Dateien.</span><span class="sxs-lookup"><span data-stu-id="5a234-112">This cmdlet is similar to `Clear-Content`, but it works on aliases and variables, instead of files.</span></span>

## <span data-ttu-id="5a234-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5a234-113">EXAMPLES</span></span>

### <span data-ttu-id="5a234-114">Beispiel 1: Löschen des Werts einer Variablen</span><span class="sxs-lookup"><span data-stu-id="5a234-114">Example 1: Clear the value of a variable</span></span>

<span data-ttu-id="5a234-115">Dieser Befehl löscht den Wert der Variablen mit dem Namen `TestVar1` .</span><span class="sxs-lookup"><span data-stu-id="5a234-115">This command clears the value of the variable named `TestVar1`.</span></span>
<span data-ttu-id="5a234-116">Die Variable bleibt erhalten und ist gültig, aber ihr Wert ist auf festgelegt `$null` .</span><span class="sxs-lookup"><span data-stu-id="5a234-116">The variable remains and is valid, but its value is set to `$null`.</span></span>
<span data-ttu-id="5a234-117">Dem Variablennamen wird das Präfix vorangestellt `Variable:` , um den PowerShell-Variablen Anbieter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5a234-117">The variable name is prefixed with `Variable:` to indicate the PowerShell Variable provider.</span></span>

<span data-ttu-id="5a234-118">Die alternativen Befehle zeigen, dass Sie zum Erreichen desselben Ergebnisses zum PowerShell `Variable:` -Laufwerk wechseln und dann den Befehl ausführen können `Clear-Item` .</span><span class="sxs-lookup"><span data-stu-id="5a234-118">The alternate commands show that, to get the same result, you can switch to the PowerShell `Variable:` drive and then run the `Clear-Item` command.</span></span>

```powershell
Clear-Item Variable:TestVar1
```

```
Set-Location Variable:
PS Variable:\> Clear-Item TestVar1
```

### <span data-ttu-id="5a234-119">Beispiel 2: Löschen aller Registrierungseinträge</span><span class="sxs-lookup"><span data-stu-id="5a234-119">Example 2: Clear all registry entries</span></span>

<span data-ttu-id="5a234-120">Mit diesem Befehl werden alle Registrierungseinträge im Unterschlüssel "MyKey" gelöscht, aber erst nach Aufforderung zur Bestätigung ihrer Absicht.</span><span class="sxs-lookup"><span data-stu-id="5a234-120">This command clears all registry entries in the "MyKey" subkey, but only after prompting you to confirm your intent.</span></span>
<span data-ttu-id="5a234-121">Der Unterschlüssel "MyKey" wird nicht gelöscht oder wirkt sich nicht auf andere Registrierungsschlüssel oder-Einträge aus.</span><span class="sxs-lookup"><span data-stu-id="5a234-121">It does not delete the "MyKey" subkey or affect any other registry keys or entries.</span></span>
<span data-ttu-id="5a234-122">Mit dem **Include**-Parameter und dem **Exclude**-Parameter können Sie bestimmte Registrierungsschlüssel angeben, Sie können damit jedoch keine Registrierungseinträge angeben.</span><span class="sxs-lookup"><span data-stu-id="5a234-122">You can use the **Include** and **Exclude** parameters to identify particular registry keys, but you cannot use them to identify registry entries.</span></span>

- <span data-ttu-id="5a234-123">Bestimmte Registrierungseinträge können Sie mit dem Cmdlet `Remove-ItemProperty` löschen.</span><span class="sxs-lookup"><span data-stu-id="5a234-123">To delete particular registry entries, use the `Remove-ItemProperty` cmdlet.</span></span>
- <span data-ttu-id="5a234-124">Zum Löschen des Werts eines Registrierungs Eintrags verwenden Sie `Clear-ItemProperty cmdlet` .</span><span class="sxs-lookup"><span data-stu-id="5a234-124">To delete the value of a registry entry, use the `Clear-ItemProperty cmdlet`.</span></span>

```powershell
Clear-Item HKLM:\Software\MyCompany\MyKey -Confirm
```

## <span data-ttu-id="5a234-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5a234-125">PARAMETERS</span></span>

### <span data-ttu-id="5a234-126">-Credential</span><span class="sxs-lookup"><span data-stu-id="5a234-126">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="5a234-127">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5a234-127">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="5a234-128">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="5a234-128">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="5a234-129">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="5a234-129">-Exclude</span></span>

<span data-ttu-id="5a234-130">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="5a234-130">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="5a234-131">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="5a234-131">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="5a234-132">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="5a234-132">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="5a234-133">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="5a234-133">Wildcard characters are permitted.</span></span> <span data-ttu-id="5a234-134">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="5a234-134">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="5a234-135">-Filter</span><span class="sxs-lookup"><span data-stu-id="5a234-135">-Filter</span></span>

<span data-ttu-id="5a234-136">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="5a234-136">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="5a234-137">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5a234-137">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="5a234-138">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="5a234-138">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="5a234-139">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="5a234-139">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="5a234-140">-Force</span><span class="sxs-lookup"><span data-stu-id="5a234-140">-Force</span></span>

<span data-ttu-id="5a234-141">Gibt an, dass das Cmdlet Elemente löscht, die anderweitig nicht geändert werden können, z. b. schreibgeschützte Aliase.</span><span class="sxs-lookup"><span data-stu-id="5a234-141">Indicates that the cmdlet clears items that cannot otherwise be changed, such as read- only aliases.</span></span>
<span data-ttu-id="5a234-142">Das Cmdlet kann keine Konstanten löschen.</span><span class="sxs-lookup"><span data-stu-id="5a234-142">The cmdlet cannot clear constants.</span></span>
<span data-ttu-id="5a234-143">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="5a234-143">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="5a234-144">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="5a234-144">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="5a234-145">Das Cmdlet kann Sicherheitseinschränkungen nicht außer Kraft setzen, auch wenn der **Force** -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5a234-145">The cmdlet cannot override security restrictions, even when the **Force** parameter is used.</span></span>

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

### <span data-ttu-id="5a234-146">-Include</span><span class="sxs-lookup"><span data-stu-id="5a234-146">-Include</span></span>

<span data-ttu-id="5a234-147">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="5a234-147">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="5a234-148">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="5a234-148">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="5a234-149">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="5a234-149">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="5a234-150">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="5a234-150">Wildcard characters are permitted.</span></span> <span data-ttu-id="5a234-151">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="5a234-151">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="5a234-152">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="5a234-152">-LiteralPath</span></span>

<span data-ttu-id="5a234-153">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="5a234-153">Specifies a path to one or more locations.</span></span> <span data-ttu-id="5a234-154">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="5a234-154">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="5a234-155">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="5a234-155">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="5a234-156">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="5a234-156">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="5a234-157">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="5a234-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="5a234-158">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="5a234-158">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="5a234-159">-Path</span><span class="sxs-lookup"><span data-stu-id="5a234-159">-Path</span></span>

<span data-ttu-id="5a234-160">Gibt den Pfad zu den Elementen an, die gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="5a234-160">Specifies the path to the items being cleared.</span></span>
<span data-ttu-id="5a234-161">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="5a234-161">Wildcard characters are permitted.</span></span>
<span data-ttu-id="5a234-162">Dieser Parameter ist erforderlich, aber der Parameter Name **path** ist optional.</span><span class="sxs-lookup"><span data-stu-id="5a234-162">This parameter is required, but the parameter name **Path** is optional.</span></span>

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

### <span data-ttu-id="5a234-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5a234-163">-Confirm</span></span>

<span data-ttu-id="5a234-164">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="5a234-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5a234-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5a234-165">-WhatIf</span></span>

<span data-ttu-id="5a234-166">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5a234-166">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5a234-167">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5a234-167">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5a234-168">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5a234-168">CommonParameters</span></span>

<span data-ttu-id="5a234-169">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="5a234-169">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="5a234-170">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="5a234-170">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="5a234-171">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5a234-171">INPUTS</span></span>

### <span data-ttu-id="5a234-172">System.String</span><span class="sxs-lookup"><span data-stu-id="5a234-172">System.String</span></span>

<span data-ttu-id="5a234-173">Sie können eine Pfad Zeichenfolge über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="5a234-173">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="5a234-174">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5a234-174">OUTPUTS</span></span>

### <span data-ttu-id="5a234-175">Keine</span><span class="sxs-lookup"><span data-stu-id="5a234-175">None</span></span>

<span data-ttu-id="5a234-176">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5a234-176">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5a234-177">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5a234-177">NOTES</span></span>

- <span data-ttu-id="5a234-178">Das- `Clear-Item` Cmdlet wird nur von mehreren PowerShell-Anbietern unterstützt, einschließlich **Alias**, **Umgebung**, **Funktion**, **Registrierung** und **Variablen** Anbietern.</span><span class="sxs-lookup"><span data-stu-id="5a234-178">The `Clear-Item` cmdlet is supported only by several PowerShell providers, including the **Alias**, **Environment**, **Function**, **Registry**, and **Variable** providers.</span></span> <span data-ttu-id="5a234-179">Daher können Sie verwenden, `Clear-Item` um den Inhalt von Elementen in den anbiefenamespaces zu löschen.</span><span class="sxs-lookup"><span data-stu-id="5a234-179">As such, you can use `Clear-Item` to delete the content of items in the provider namespaces.</span></span> <span data-ttu-id="5a234-180">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="5a234-180">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="5a234-181">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="5a234-181">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
- <span data-ttu-id="5a234-182">Sie können nicht verwenden `Clear-Item` , um den Inhalt einer Datei zu löschen, da der PowerShell-Dateisystem Anbieter dieses Cmdlet nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5a234-182">You cannot use `Clear-Item` to delete the contents of a file, because the PowerShell FileSystem provider does not support this cmdlet.</span></span> <span data-ttu-id="5a234-183">Um Dateien zu löschen, verwenden Sie die `Clear-Content` .</span><span class="sxs-lookup"><span data-stu-id="5a234-183">To clear files, use the `Clear-Content`.</span></span>

## <span data-ttu-id="5a234-184">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5a234-184">RELATED LINKS</span></span>

[<span data-ttu-id="5a234-185">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="5a234-185">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="5a234-186">Get-Item</span><span class="sxs-lookup"><span data-stu-id="5a234-186">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="5a234-187">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="5a234-187">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="5a234-188">Move-Item</span><span class="sxs-lookup"><span data-stu-id="5a234-188">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="5a234-189">New-Item</span><span class="sxs-lookup"><span data-stu-id="5a234-189">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="5a234-190">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="5a234-190">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="5a234-191">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="5a234-191">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="5a234-192">Set-Item</span><span class="sxs-lookup"><span data-stu-id="5a234-192">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="5a234-193">about_Providers</span><span class="sxs-lookup"><span data-stu-id="5a234-193">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

