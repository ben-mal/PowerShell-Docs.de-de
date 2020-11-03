---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 9ae9c0e7c17a6a63da5487cce138ddce129b975b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214548"
---
# <span data-ttu-id="8a716-103">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="8a716-103">Remove-ItemProperty</span></span>

## <span data-ttu-id="8a716-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="8a716-104">SYNOPSIS</span></span>
<span data-ttu-id="8a716-105">Löscht die Eigenschaft und deren Wert aus einem Element.</span><span class="sxs-lookup"><span data-stu-id="8a716-105">Deletes the property and its value from an item.</span></span>

## <span data-ttu-id="8a716-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8a716-106">SYNTAX</span></span>

### <span data-ttu-id="8a716-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="8a716-107">Path (Default)</span></span>

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="8a716-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8a716-108">LiteralPath</span></span>

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="8a716-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8a716-109">DESCRIPTION</span></span>

<span data-ttu-id="8a716-110">Mit dem `Remove-ItemProperty` -Cmdlet werden eine Eigenschaft und ihr Wert aus einem Element gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8a716-110">The `Remove-ItemProperty` cmdlet deletes a property and its value from an item.</span></span>
<span data-ttu-id="8a716-111">Damit können Sie Registrierungswerte und darin gespeicherte Daten löschen.</span><span class="sxs-lookup"><span data-stu-id="8a716-111">You can use it to delete registry values and the data that they store.</span></span>

## <span data-ttu-id="8a716-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8a716-112">EXAMPLES</span></span>

### <span data-ttu-id="8a716-113">Beispiel 1: Löschen eines Registrierungs Werts</span><span class="sxs-lookup"><span data-stu-id="8a716-113">Example 1: Delete a registry value</span></span>

<span data-ttu-id="8a716-114">Dieser Befehl löscht den Registrierungs Wert "smpproperty" und seine Daten aus dem Unterschlüssel "smpapplication" des Registrierungsschlüssels "HKEY_LOCAL_MACHINE\Software".</span><span class="sxs-lookup"><span data-stu-id="8a716-114">This command deletes the "SmpProperty" registry value, and its data, from the "SmpApplication" subkey of the "HKEY_LOCAL_MACHINE\Software" registry key.</span></span>

<span data-ttu-id="8a716-115">Da der Befehl von einem Dateisystem Laufwerk () ausgegeben wird `PS C:\>` , enthält er den voll qualifizierten Pfad des unter Schlüssels "smpapplication", einschließlich des Laufwerks, `HKLM:` und des Schlüssels "Software".</span><span class="sxs-lookup"><span data-stu-id="8a716-115">Because the command is issued from a file system drive (`PS C:\>`), it includes the fully qualified path of the "SmpApplication" subkey, including the drive, `HKLM:`, and the "Software" key.</span></span>

<span data-ttu-id="8a716-116">Mit dem **Name** -Parameter wird der Registrierungs Wert identifiziert, der gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="8a716-116">It uses the **Name** parameter to identify the registry value that is being deleted.</span></span>

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

### <span data-ttu-id="8a716-117">Beispiel 2: Löschen eines Registrierungs Werts aus dem HKCU-Speicherort</span><span class="sxs-lookup"><span data-stu-id="8a716-117">Example 2: Delete a registry value from the HKCU location</span></span>

<span data-ttu-id="8a716-118">Mit diesen Befehlen werden der Registrierungs Wert "Options" und seine Daten aus dem Unterschlüssel "MyApp" von "HKEY_CURRENT_USER\Software\MyCompany" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8a716-118">These commands delete the "Options" registry value, and its data, from the "MyApp" subkey of "HKEY_CURRENT_USER\Software\MyCompany".</span></span>

<span data-ttu-id="8a716-119">Der erste Befehl verwendet das `Set-Location` Cmdlet, um den aktuellen Speicherort auf das **HKEY_CURRENT_USER** Laufwerk ( `HKCU:` ) und den Unterschlüssel "software\mycompany\myapp" zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8a716-119">The first command uses the `Set-Location` cmdlet to change the current location to the **HKEY_CURRENT_USER** drive (`HKCU:`) and the "Software\MyCompany\MyApp" subkey.</span></span>

<span data-ttu-id="8a716-120">Der zweite Befehl verwendet, `Remove-ItemProperty` um den Registrierungs Wert "Optionen" und seine Daten aus dem Unterschlüssel "MyApp" zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8a716-120">The second command uses `Remove-ItemProperty` to remove the "Options" registry value, and its data, from the "MyApp" subkey.</span></span>
<span data-ttu-id="8a716-121">Da **path** erforderlich ist, verwendet der Befehl einen Punkt ("."), um den aktuellen Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8a716-121">Because **Path** is required, the command uses a dot ('.') to indicate the current location.</span></span>
<span data-ttu-id="8a716-122">Der **Name** wird verwendet, um anzugeben, welcher Registrierungs Wert gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="8a716-122">It uses **Name** to specify which registry value to delete.</span></span>
<span data-ttu-id="8a716-123">Er verwendet den **Confirm** -Parameter, um eine Benutzer Aufforderung anzufordern, bevor der Wert gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="8a716-123">It uses the **Confirm** parameter to request a user prompt before deleting the value.</span></span>

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

### <span data-ttu-id="8a716-124">Beispiel 3: Entfernen eines Registrierungs Werts mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="8a716-124">Example 3: Remove a registry value by using the pipeline</span></span>

<span data-ttu-id="8a716-125">Mit diesem Befehl werden der Registrierungs Wert "noofemployees" und seine Daten aus dem Registrierungsschlüssel "hklm\software\mycompany" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8a716-125">This command deletes the "NoOfEmployees" registry value, and its data, from the "HKLM\Software\MyCompany" registry key.</span></span>

<span data-ttu-id="8a716-126">Der Befehl verwendet das `Get-Item` Cmdlet, um ein Element zu erhalten, das den Registrierungsschlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="8a716-126">The command uses the `Get-Item` cmdlet to get an item that represents the registry key.</span></span>
<span data-ttu-id="8a716-127">Er verwendet einen Pipeline Operator ( `|` ), um das Objekt an zu senden `Remove-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="8a716-127">It uses a pipeline operator (`|`) to send the object to `Remove-ItemProperty`.</span></span>
<span data-ttu-id="8a716-128">Anschließend wird mit dem **Name** -Parameter von `Remove-ItemProperty` der Name des Registrierungs Werts angegeben.</span><span class="sxs-lookup"><span data-stu-id="8a716-128">Then, it uses the **Name** parameter of `Remove-ItemProperty` to specify the name of the registry value.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
```

## <span data-ttu-id="8a716-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8a716-129">PARAMETERS</span></span>

### <span data-ttu-id="8a716-130">-Credential</span><span class="sxs-lookup"><span data-stu-id="8a716-130">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="8a716-131">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8a716-131">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="8a716-132">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="8a716-132">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="8a716-133">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="8a716-133">-Exclude</span></span>

<span data-ttu-id="8a716-134">Gibt die Elemente an, die von diesem Cmdlet ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="8a716-134">Specifies items that this cmdlet omits.</span></span>
<span data-ttu-id="8a716-135">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="8a716-135">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="8a716-136">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="8a716-136">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="8a716-137">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="8a716-137">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="8a716-138">-Filter</span><span class="sxs-lookup"><span data-stu-id="8a716-138">-Filter</span></span>

<span data-ttu-id="8a716-139">Gibt einen Filter im Format oder in der Sprache des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="8a716-139">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="8a716-140">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="8a716-140">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="8a716-141">Die Syntax des Filters, einschließlich der Verwendung von Platzhalter Zeichen, hängt vom Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="8a716-141">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="8a716-142">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="8a716-142">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="8a716-143">-Force</span><span class="sxs-lookup"><span data-stu-id="8a716-143">-Force</span></span>

<span data-ttu-id="8a716-144">Zwingt das Cmdlet, eine Eigenschaft eines Objekts zu entfernen, auf das der Benutzer anderweitig nicht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="8a716-144">Forces the cmdlet to remove a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="8a716-145">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="8a716-145">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="8a716-146">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="8a716-146">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="8a716-147">-Include</span><span class="sxs-lookup"><span data-stu-id="8a716-147">-Include</span></span>

<span data-ttu-id="8a716-148">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="8a716-148">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="8a716-149">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="8a716-149">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="8a716-150">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="8a716-150">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="8a716-151">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="8a716-151">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="8a716-152">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="8a716-152">-LiteralPath</span></span>

<span data-ttu-id="8a716-153">Gibt den Pfad zum aktuellen Speicherort der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="8a716-153">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="8a716-154">Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8a716-154">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="8a716-155">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="8a716-155">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="8a716-156">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="8a716-156">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="8a716-157">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="8a716-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8a716-158">-Name</span><span class="sxs-lookup"><span data-stu-id="8a716-158">-Name</span></span>

<span data-ttu-id="8a716-159">Gibt die Namen der zu entfernenden Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="8a716-159">Specifies the names of the properties to remove.</span></span>
<span data-ttu-id="8a716-160">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="8a716-160">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="8a716-161">-Path</span><span class="sxs-lookup"><span data-stu-id="8a716-161">-Path</span></span>

<span data-ttu-id="8a716-162">Gibt den Pfad des Elements an, dessen Eigenschaften entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="8a716-162">Specifies the path of the item whose properties are being removed.</span></span>
<span data-ttu-id="8a716-163">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="8a716-163">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="8a716-164">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="8a716-164">-UseTransaction</span></span>

<span data-ttu-id="8a716-165">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="8a716-165">Includes the command in the active transaction.</span></span>
<span data-ttu-id="8a716-166">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8a716-166">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="8a716-167">Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="8a716-167">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a716-168">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8a716-168">-Confirm</span></span>

<span data-ttu-id="8a716-169">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="8a716-169">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8a716-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8a716-170">-WhatIf</span></span>

<span data-ttu-id="8a716-171">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8a716-171">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8a716-172">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8a716-172">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8a716-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8a716-173">CommonParameters</span></span>

<span data-ttu-id="8a716-174">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="8a716-174">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="8a716-175">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8a716-175">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="8a716-176">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="8a716-176">INPUTS</span></span>

### <span data-ttu-id="8a716-177">System.String</span><span class="sxs-lookup"><span data-stu-id="8a716-177">System.String</span></span>

<span data-ttu-id="8a716-178">Sie können eine Zeichenfolge, die einen Pfad, aber keinen literalpfad enthält, an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="8a716-178">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="8a716-179">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="8a716-179">OUTPUTS</span></span>

### <span data-ttu-id="8a716-180">Keine</span><span class="sxs-lookup"><span data-stu-id="8a716-180">None</span></span>

<span data-ttu-id="8a716-181">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="8a716-181">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="8a716-182">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="8a716-182">NOTES</span></span>

<span data-ttu-id="8a716-183">Im PowerShell-Registrierungs Anbieter werden Registrierungs Werte als Eigenschaften eines Registrierungsschlüssels oder-unter Schlüssels angesehen.</span><span class="sxs-lookup"><span data-stu-id="8a716-183">In the PowerShell Registry provider, registry values are considered to be properties of a registry key or subkey.</span></span> <span data-ttu-id="8a716-184">Sie können die **ItemProperty** -Cmdlets verwenden, um diese Werte zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="8a716-184">You can use the **ItemProperty** cmdlets to manage these values.</span></span>

<span data-ttu-id="8a716-185">`Remove-ItemProperty` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="8a716-185">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="8a716-186">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="8a716-186">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="8a716-187">Weitere Informationen finden Sie unter %%amp;quot;about_Providers%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="8a716-187">For more information, see about_Providers.</span></span>

## <span data-ttu-id="8a716-188">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="8a716-188">RELATED LINKS</span></span>

[<span data-ttu-id="8a716-189">Get-Item</span><span class="sxs-lookup"><span data-stu-id="8a716-189">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="8a716-190">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="8a716-190">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="8a716-191">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="8a716-191">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="8a716-192">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="8a716-192">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="8a716-193">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="8a716-193">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="8a716-194">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="8a716-194">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="8a716-195">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="8a716-195">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="8a716-196">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="8a716-196">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="8a716-197">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="8a716-197">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="8a716-198">about_Providers</span><span class="sxs-lookup"><span data-stu-id="8a716-198">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
