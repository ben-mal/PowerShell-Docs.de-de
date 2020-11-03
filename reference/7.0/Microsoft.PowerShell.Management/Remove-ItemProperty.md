---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 2daf4d9dacc0f15ab5347fff4bec831be25d97a6
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209775"
---
# <span data-ttu-id="66e07-103">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="66e07-103">Remove-ItemProperty</span></span>

## <span data-ttu-id="66e07-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="66e07-104">SYNOPSIS</span></span>
<span data-ttu-id="66e07-105">Löscht die Eigenschaft und deren Wert aus einem Element.</span><span class="sxs-lookup"><span data-stu-id="66e07-105">Deletes the property and its value from an item.</span></span>

## <span data-ttu-id="66e07-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="66e07-106">SYNTAX</span></span>

### <span data-ttu-id="66e07-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="66e07-107">Path (Default)</span></span>

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="66e07-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="66e07-108">LiteralPath</span></span>

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="66e07-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="66e07-109">DESCRIPTION</span></span>

<span data-ttu-id="66e07-110">Mit dem `Remove-ItemProperty` -Cmdlet werden eine Eigenschaft und ihr Wert aus einem Element gelöscht.</span><span class="sxs-lookup"><span data-stu-id="66e07-110">The `Remove-ItemProperty` cmdlet deletes a property and its value from an item.</span></span>
<span data-ttu-id="66e07-111">Damit können Sie Registrierungswerte und darin gespeicherte Daten löschen.</span><span class="sxs-lookup"><span data-stu-id="66e07-111">You can use it to delete registry values and the data that they store.</span></span>

## <span data-ttu-id="66e07-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="66e07-112">EXAMPLES</span></span>

### <span data-ttu-id="66e07-113">Beispiel 1: Löschen eines Registrierungs Werts</span><span class="sxs-lookup"><span data-stu-id="66e07-113">Example 1: Delete a registry value</span></span>

<span data-ttu-id="66e07-114">Dieser Befehl löscht den Registrierungs Wert "smpproperty" und seine Daten aus dem Unterschlüssel "smpapplication" des `HKEY_LOCAL_MACHINE\Software` Registrierungsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="66e07-114">This command deletes the "SmpProperty" registry value, and its data, from the "SmpApplication" subkey of the `HKEY_LOCAL_MACHINE\Software` registry key.</span></span>

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

<span data-ttu-id="66e07-115">Da der Befehl von einem Dateisystem Laufwerk () ausgegeben wird `PS C:\>` , enthält er den voll qualifizierten Pfad des unter Schlüssels "smpapplication", einschließlich des Laufwerks, `HKLM:` und des Schlüssels "Software".</span><span class="sxs-lookup"><span data-stu-id="66e07-115">Because the command is issued from a file system drive (`PS C:\>`), it includes the fully qualified path of the "SmpApplication" subkey, including the drive, `HKLM:`, and the "Software" key.</span></span>

### <span data-ttu-id="66e07-116">Beispiel 2: Löschen eines Registrierungs Werts aus dem HKCU-Speicherort</span><span class="sxs-lookup"><span data-stu-id="66e07-116">Example 2: Delete a registry value from the HKCU location</span></span>

<span data-ttu-id="66e07-117">Mit diesen Befehlen werden der Registrierungs Wert "Options" und seine Daten aus dem Unterschlüssel "MyApp" von "HKEY_CURRENT_USER\Software\MyCompany" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="66e07-117">These commands delete the "Options" registry value, and its data, from the "MyApp" subkey of "HKEY_CURRENT_USER\Software\MyCompany".</span></span>

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

<span data-ttu-id="66e07-118">Der erste Befehl verwendet das `Set-Location` Cmdlet, um den aktuellen Speicherort auf das **HKEY_CURRENT_USER** Laufwerk ( `HKCU:` ) und den `Software\MyCompany\MyApp` Unterschlüssel zu ändern.</span><span class="sxs-lookup"><span data-stu-id="66e07-118">The first command uses the `Set-Location` cmdlet to change the current location to the **HKEY_CURRENT_USER** drive (`HKCU:`) and the `Software\MyCompany\MyApp` subkey.</span></span>

<span data-ttu-id="66e07-119">Der zweite Befehl verwendet, `Remove-ItemProperty` um den Registrierungs Wert "Optionen" und seine Daten aus dem Unterschlüssel "MyApp" zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="66e07-119">The second command uses `Remove-ItemProperty` to remove the "Options" registry value, and its data, from the "MyApp" subkey.</span></span> <span data-ttu-id="66e07-120">Da **path** erforderlich ist, verwendet der Befehl einen Punkt ( `.` ), um den aktuellen Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="66e07-120">Because **Path** is required, the command uses a dot (`.`) to indicate the current location.</span></span> <span data-ttu-id="66e07-121">Der **Confirm** -Parameter fordert vor dem Löschen des Werts eine Benutzereingabe Aufforderung an.</span><span class="sxs-lookup"><span data-stu-id="66e07-121">The **Confirm** parameter requests a user prompt before deleting the value.</span></span>

### <span data-ttu-id="66e07-122">Beispiel 3: Entfernen eines Registrierungs Werts mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="66e07-122">Example 3: Remove a registry value by using the pipeline</span></span>

<span data-ttu-id="66e07-123">Dieser Befehl löscht den Registrierungs Wert "noofemployees" und seine Daten aus dem `HKLM\Software\MyCompany` Registrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="66e07-123">This command deletes the "NoOfEmployees" registry value, and its data, from the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
```

<span data-ttu-id="66e07-124">Der Befehl verwendet das `Get-Item` Cmdlet, um ein Element zu erhalten, das den Registrierungsschlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="66e07-124">The command uses the `Get-Item` cmdlet to get an item that represents the registry key.</span></span>
<span data-ttu-id="66e07-125">Er verwendet einen Pipeline Operator ( `|` ), um das Objekt an zu senden `Remove-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="66e07-125">It uses a pipeline operator (`|`) to send the object to `Remove-ItemProperty`.</span></span>
<span data-ttu-id="66e07-126">Anschließend wird mit dem **Name** -Parameter von `Remove-ItemProperty` der Name des Registrierungs Werts angegeben.</span><span class="sxs-lookup"><span data-stu-id="66e07-126">Then, it uses the **Name** parameter of `Remove-ItemProperty` to specify the name of the registry value.</span></span>

## <span data-ttu-id="66e07-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="66e07-127">PARAMETERS</span></span>

### <span data-ttu-id="66e07-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="66e07-128">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="66e07-129">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="66e07-129">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="66e07-130">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="66e07-130">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="66e07-131">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="66e07-131">-Exclude</span></span>

<span data-ttu-id="66e07-132">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="66e07-132">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="66e07-133">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="66e07-133">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="66e07-134">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="66e07-134">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="66e07-135">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="66e07-135">Wildcard characters are permitted.</span></span> <span data-ttu-id="66e07-136">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="66e07-136">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="66e07-137">-Filter</span><span class="sxs-lookup"><span data-stu-id="66e07-137">-Filter</span></span>

<span data-ttu-id="66e07-138">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="66e07-138">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="66e07-139">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="66e07-139">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="66e07-140">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="66e07-140">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="66e07-141">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="66e07-141">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="66e07-142">-Force</span><span class="sxs-lookup"><span data-stu-id="66e07-142">-Force</span></span>

<span data-ttu-id="66e07-143">Zwingt das Cmdlet, eine Eigenschaft eines Objekts zu entfernen, auf das der Benutzer anderweitig nicht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="66e07-143">Forces the cmdlet to remove a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="66e07-144">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="66e07-144">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="66e07-145">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="66e07-145">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="66e07-146">-Include</span><span class="sxs-lookup"><span data-stu-id="66e07-146">-Include</span></span>

<span data-ttu-id="66e07-147">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="66e07-147">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="66e07-148">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="66e07-148">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="66e07-149">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="66e07-149">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="66e07-150">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="66e07-150">Wildcard characters are permitted.</span></span> <span data-ttu-id="66e07-151">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="66e07-151">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="66e07-152">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="66e07-152">-LiteralPath</span></span>

<span data-ttu-id="66e07-153">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="66e07-153">Specifies a path to one or more locations.</span></span> <span data-ttu-id="66e07-154">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="66e07-154">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="66e07-155">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="66e07-155">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="66e07-156">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="66e07-156">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="66e07-157">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="66e07-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="66e07-158">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="66e07-158">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="66e07-159">-Name</span><span class="sxs-lookup"><span data-stu-id="66e07-159">-Name</span></span>

<span data-ttu-id="66e07-160">Gibt die Namen der zu entfernenden Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="66e07-160">Specifies the names of the properties to remove.</span></span>
<span data-ttu-id="66e07-161">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="66e07-161">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="66e07-162">-Path</span><span class="sxs-lookup"><span data-stu-id="66e07-162">-Path</span></span>

<span data-ttu-id="66e07-163">Gibt den Pfad des Elements an, dessen Eigenschaften entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="66e07-163">Specifies the path of the item whose properties are being removed.</span></span>
<span data-ttu-id="66e07-164">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="66e07-164">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="66e07-165">-Confirm</span><span class="sxs-lookup"><span data-stu-id="66e07-165">-Confirm</span></span>

<span data-ttu-id="66e07-166">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="66e07-166">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="66e07-167">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="66e07-167">-WhatIf</span></span>

<span data-ttu-id="66e07-168">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="66e07-168">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="66e07-169">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="66e07-169">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="66e07-170">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="66e07-170">CommonParameters</span></span>

<span data-ttu-id="66e07-171">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="66e07-171">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="66e07-172">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="66e07-172">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="66e07-173">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="66e07-173">INPUTS</span></span>

### <span data-ttu-id="66e07-174">System.String</span><span class="sxs-lookup"><span data-stu-id="66e07-174">System.String</span></span>

<span data-ttu-id="66e07-175">Sie können eine Zeichenfolge, die einen Pfad, aber keinen literalpfad enthält, an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="66e07-175">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="66e07-176">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="66e07-176">OUTPUTS</span></span>

### <span data-ttu-id="66e07-177">Keine</span><span class="sxs-lookup"><span data-stu-id="66e07-177">None</span></span>

<span data-ttu-id="66e07-178">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="66e07-178">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="66e07-179">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="66e07-179">NOTES</span></span>

- <span data-ttu-id="66e07-180">Im PowerShell-Registrierungs Anbieter werden Registrierungs Werte als Eigenschaften eines Registrierungsschlüssels oder-unter Schlüssels angesehen.</span><span class="sxs-lookup"><span data-stu-id="66e07-180">In the PowerShell Registry provider, registry values are considered to be properties of a registry key or subkey.</span></span> <span data-ttu-id="66e07-181">Sie können die **ItemProperty** -Cmdlets verwenden, um diese Werte zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="66e07-181">You can use the **ItemProperty** cmdlets to manage these values.</span></span>
- <span data-ttu-id="66e07-182">`Remove-ItemProperty` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="66e07-182">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="66e07-183">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="66e07-183">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="66e07-184">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="66e07-184">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="66e07-185">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="66e07-185">RELATED LINKS</span></span>

[<span data-ttu-id="66e07-186">Get-Item</span><span class="sxs-lookup"><span data-stu-id="66e07-186">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="66e07-187">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="66e07-187">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="66e07-188">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="66e07-188">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="66e07-189">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="66e07-189">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="66e07-190">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="66e07-190">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="66e07-191">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="66e07-191">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="66e07-192">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="66e07-192">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="66e07-193">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="66e07-193">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="66e07-194">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="66e07-194">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="66e07-195">Set-Location</span><span class="sxs-lookup"><span data-stu-id="66e07-195">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="66e07-196">about_Providers</span><span class="sxs-lookup"><span data-stu-id="66e07-196">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
