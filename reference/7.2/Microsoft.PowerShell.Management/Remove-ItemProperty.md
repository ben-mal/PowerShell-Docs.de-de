---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 870d8e9797ff2cfce14034706f704c0e1c954fc2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602952"
---
# <span data-ttu-id="c23ba-102">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c23ba-102">Remove-ItemProperty</span></span>

## <span data-ttu-id="c23ba-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c23ba-103">SYNOPSIS</span></span>
<span data-ttu-id="c23ba-104">Löscht die Eigenschaft und deren Wert aus einem Element.</span><span class="sxs-lookup"><span data-stu-id="c23ba-104">Deletes the property and its value from an item.</span></span>

## <span data-ttu-id="c23ba-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c23ba-105">SYNTAX</span></span>

### <span data-ttu-id="c23ba-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="c23ba-106">Path (Default)</span></span>

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c23ba-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c23ba-107">LiteralPath</span></span>

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c23ba-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c23ba-108">DESCRIPTION</span></span>

<span data-ttu-id="c23ba-109">Mit dem `Remove-ItemProperty` -Cmdlet werden eine Eigenschaft und ihr Wert aus einem Element gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c23ba-109">The `Remove-ItemProperty` cmdlet deletes a property and its value from an item.</span></span>
<span data-ttu-id="c23ba-110">Damit können Sie Registrierungswerte und darin gespeicherte Daten löschen.</span><span class="sxs-lookup"><span data-stu-id="c23ba-110">You can use it to delete registry values and the data that they store.</span></span>

## <span data-ttu-id="c23ba-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c23ba-111">EXAMPLES</span></span>

### <span data-ttu-id="c23ba-112">Beispiel 1: Löschen eines Registrierungs Werts</span><span class="sxs-lookup"><span data-stu-id="c23ba-112">Example 1: Delete a registry value</span></span>

<span data-ttu-id="c23ba-113">Dieser Befehl löscht den Registrierungs Wert "smpproperty" und seine Daten aus dem Unterschlüssel "smpapplication" des `HKEY_LOCAL_MACHINE\Software` Registrierungsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="c23ba-113">This command deletes the "SmpProperty" registry value, and its data, from the "SmpApplication" subkey of the `HKEY_LOCAL_MACHINE\Software` registry key.</span></span>

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

<span data-ttu-id="c23ba-114">Da der Befehl von einem Dateisystem Laufwerk () ausgegeben wird `PS C:\>` , enthält er den voll qualifizierten Pfad des unter Schlüssels "smpapplication", einschließlich des Laufwerks, `HKLM:` und des Schlüssels "Software".</span><span class="sxs-lookup"><span data-stu-id="c23ba-114">Because the command is issued from a file system drive (`PS C:\>`), it includes the fully qualified path of the "SmpApplication" subkey, including the drive, `HKLM:`, and the "Software" key.</span></span>

### <span data-ttu-id="c23ba-115">Beispiel 2: Löschen eines Registrierungs Werts aus dem HKCU-Speicherort</span><span class="sxs-lookup"><span data-stu-id="c23ba-115">Example 2: Delete a registry value from the HKCU location</span></span>

<span data-ttu-id="c23ba-116">Mit diesen Befehlen werden der Registrierungs Wert "Options" und seine Daten aus dem Unterschlüssel "MyApp" von "HKEY_CURRENT_USER\Software\MyCompany" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c23ba-116">These commands delete the "Options" registry value, and its data, from the "MyApp" subkey of "HKEY_CURRENT_USER\Software\MyCompany".</span></span>

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

<span data-ttu-id="c23ba-117">Der erste Befehl verwendet das `Set-Location` Cmdlet, um den aktuellen Speicherort auf das **HKEY_CURRENT_USER** Laufwerk ( `HKCU:` ) und den `Software\MyCompany\MyApp` Unterschlüssel zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c23ba-117">The first command uses the `Set-Location` cmdlet to change the current location to the **HKEY_CURRENT_USER** drive (`HKCU:`) and the `Software\MyCompany\MyApp` subkey.</span></span>

<span data-ttu-id="c23ba-118">Der zweite Befehl verwendet, `Remove-ItemProperty` um den Registrierungs Wert "Optionen" und seine Daten aus dem Unterschlüssel "MyApp" zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c23ba-118">The second command uses `Remove-ItemProperty` to remove the "Options" registry value, and its data, from the "MyApp" subkey.</span></span> <span data-ttu-id="c23ba-119">Da **path** erforderlich ist, verwendet der Befehl einen Punkt ( `.` ), um den aktuellen Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c23ba-119">Because **Path** is required, the command uses a dot (`.`) to indicate the current location.</span></span> <span data-ttu-id="c23ba-120">Der **Confirm** -Parameter fordert vor dem Löschen des Werts eine Benutzereingabe Aufforderung an.</span><span class="sxs-lookup"><span data-stu-id="c23ba-120">The **Confirm** parameter requests a user prompt before deleting the value.</span></span>

### <span data-ttu-id="c23ba-121">Beispiel 3: Entfernen eines Registrierungs Werts mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="c23ba-121">Example 3: Remove a registry value by using the pipeline</span></span>

<span data-ttu-id="c23ba-122">Dieser Befehl löscht den Registrierungs Wert "noofemployees" und seine Daten aus dem `HKLM\Software\MyCompany` Registrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="c23ba-122">This command deletes the "NoOfEmployees" registry value, and its data, from the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
```

<span data-ttu-id="c23ba-123">Der Befehl verwendet das `Get-Item` Cmdlet, um ein Element zu erhalten, das den Registrierungsschlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="c23ba-123">The command uses the `Get-Item` cmdlet to get an item that represents the registry key.</span></span>
<span data-ttu-id="c23ba-124">Er verwendet einen Pipeline Operator ( `|` ), um das Objekt an zu senden `Remove-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="c23ba-124">It uses a pipeline operator (`|`) to send the object to `Remove-ItemProperty`.</span></span>
<span data-ttu-id="c23ba-125">Anschließend wird mit dem **Name** -Parameter von `Remove-ItemProperty` der Name des Registrierungs Werts angegeben.</span><span class="sxs-lookup"><span data-stu-id="c23ba-125">Then, it uses the **Name** parameter of `Remove-ItemProperty` to specify the name of the registry value.</span></span>

## <span data-ttu-id="c23ba-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c23ba-126">PARAMETERS</span></span>

### <span data-ttu-id="c23ba-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="c23ba-127">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="c23ba-128">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c23ba-128">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="c23ba-129">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="c23ba-129">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="c23ba-130">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="c23ba-130">-Exclude</span></span>

<span data-ttu-id="c23ba-131">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="c23ba-131">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="c23ba-132">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="c23ba-132">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c23ba-133">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="c23ba-133">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="c23ba-134">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="c23ba-134">Wildcard characters are permitted.</span></span> <span data-ttu-id="c23ba-135">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="c23ba-135">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="c23ba-136">-Filter</span><span class="sxs-lookup"><span data-stu-id="c23ba-136">-Filter</span></span>

<span data-ttu-id="c23ba-137">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="c23ba-137">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="c23ba-138">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c23ba-138">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="c23ba-139">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="c23ba-139">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="c23ba-140">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="c23ba-140">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="c23ba-141">-Force</span><span class="sxs-lookup"><span data-stu-id="c23ba-141">-Force</span></span>

<span data-ttu-id="c23ba-142">Zwingt das Cmdlet, eine Eigenschaft eines Objekts zu entfernen, auf das der Benutzer anderweitig nicht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="c23ba-142">Forces the cmdlet to remove a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="c23ba-143">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="c23ba-143">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="c23ba-144">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="c23ba-144">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="c23ba-145">-Include</span><span class="sxs-lookup"><span data-stu-id="c23ba-145">-Include</span></span>

<span data-ttu-id="c23ba-146">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="c23ba-146">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="c23ba-147">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="c23ba-147">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c23ba-148">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="c23ba-148">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="c23ba-149">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="c23ba-149">Wildcard characters are permitted.</span></span> <span data-ttu-id="c23ba-150">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="c23ba-150">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="c23ba-151">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="c23ba-151">-LiteralPath</span></span>

<span data-ttu-id="c23ba-152">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="c23ba-152">Specifies a path to one or more locations.</span></span> <span data-ttu-id="c23ba-153">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c23ba-153">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="c23ba-154">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="c23ba-154">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="c23ba-155">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="c23ba-155">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="c23ba-156">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="c23ba-156">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="c23ba-157">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="c23ba-157">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="c23ba-158">-Name</span><span class="sxs-lookup"><span data-stu-id="c23ba-158">-Name</span></span>

<span data-ttu-id="c23ba-159">Gibt die Namen der zu entfernenden Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="c23ba-159">Specifies the names of the properties to remove.</span></span>
<span data-ttu-id="c23ba-160">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="c23ba-160">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="c23ba-161">-Path</span><span class="sxs-lookup"><span data-stu-id="c23ba-161">-Path</span></span>

<span data-ttu-id="c23ba-162">Gibt den Pfad des Elements an, dessen Eigenschaften entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="c23ba-162">Specifies the path of the item whose properties are being removed.</span></span>
<span data-ttu-id="c23ba-163">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="c23ba-163">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="c23ba-164">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c23ba-164">-Confirm</span></span>

<span data-ttu-id="c23ba-165">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="c23ba-165">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c23ba-166">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c23ba-166">-WhatIf</span></span>

<span data-ttu-id="c23ba-167">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c23ba-167">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c23ba-168">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c23ba-168">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c23ba-169">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c23ba-169">CommonParameters</span></span>

<span data-ttu-id="c23ba-170">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="c23ba-170">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="c23ba-171">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="c23ba-171">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="c23ba-172">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c23ba-172">INPUTS</span></span>

### <span data-ttu-id="c23ba-173">System.String</span><span class="sxs-lookup"><span data-stu-id="c23ba-173">System.String</span></span>

<span data-ttu-id="c23ba-174">Sie können eine Zeichenfolge, die einen Pfad, aber keinen literalpfad enthält, an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="c23ba-174">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="c23ba-175">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c23ba-175">OUTPUTS</span></span>

### <span data-ttu-id="c23ba-176">Keine</span><span class="sxs-lookup"><span data-stu-id="c23ba-176">None</span></span>

<span data-ttu-id="c23ba-177">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="c23ba-177">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="c23ba-178">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c23ba-178">NOTES</span></span>

- <span data-ttu-id="c23ba-179">Im PowerShell-Registrierungs Anbieter werden Registrierungs Werte als Eigenschaften eines Registrierungsschlüssels oder-unter Schlüssels angesehen.</span><span class="sxs-lookup"><span data-stu-id="c23ba-179">In the PowerShell Registry provider, registry values are considered to be properties of a registry key or subkey.</span></span> <span data-ttu-id="c23ba-180">Sie können die **ItemProperty** -Cmdlets verwenden, um diese Werte zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c23ba-180">You can use the **ItemProperty** cmdlets to manage these values.</span></span>
- <span data-ttu-id="c23ba-181">`Remove-ItemProperty` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="c23ba-181">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="c23ba-182">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="c23ba-182">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="c23ba-183">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="c23ba-183">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="c23ba-184">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c23ba-184">RELATED LINKS</span></span>

[<span data-ttu-id="c23ba-185">Get-Item</span><span class="sxs-lookup"><span data-stu-id="c23ba-185">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="c23ba-186">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c23ba-186">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="c23ba-187">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c23ba-187">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="c23ba-188">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c23ba-188">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="c23ba-189">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c23ba-189">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="c23ba-190">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c23ba-190">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="c23ba-191">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="c23ba-191">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="c23ba-192">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c23ba-192">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="c23ba-193">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c23ba-193">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="c23ba-194">Set-Location</span><span class="sxs-lookup"><span data-stu-id="c23ba-194">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="c23ba-195">about_Providers</span><span class="sxs-lookup"><span data-stu-id="c23ba-195">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

