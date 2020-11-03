---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-ItemProperty
ms.openlocfilehash: b23db6af5d34b8a6413a21fafd34fc5e19f5690a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215559"
---
# <span data-ttu-id="5758d-103">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5758d-103">Clear-ItemProperty</span></span>

## <span data-ttu-id="5758d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5758d-104">SYNOPSIS</span></span>
<span data-ttu-id="5758d-105">Löscht den Wert einer Eigenschaft, löscht jedoch nicht die-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5758d-105">Clears the value of a property but does not delete the property.</span></span>

## <span data-ttu-id="5758d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5758d-106">SYNTAX</span></span>

### <span data-ttu-id="5758d-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="5758d-107">Path (Default)</span></span>

```
Clear-ItemProperty [-Path] <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="5758d-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="5758d-108">LiteralPath</span></span>

```
Clear-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="5758d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5758d-109">DESCRIPTION</span></span>

<span data-ttu-id="5758d-110">Mit dem- `Clear-ItemProperty` Cmdlet wird der Wert einer Eigenschaft gelöscht, die Eigenschaft wird jedoch nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="5758d-110">The `Clear-ItemProperty` cmdlet clears the value of a property, but it does not delete the property.</span></span>
<span data-ttu-id="5758d-111">Mit diesem Cmdlet können Sie die Daten aus einem Registrierungswert löschen.</span><span class="sxs-lookup"><span data-stu-id="5758d-111">You can use this cmdlet to delete the data from a registry value.</span></span>

## <span data-ttu-id="5758d-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5758d-112">EXAMPLES</span></span>

### <span data-ttu-id="5758d-113">Beispiel 1: Löschen des Werts des Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="5758d-113">Example 1: Clear the value of registry key</span></span>

<span data-ttu-id="5758d-114">Dieser Befehl löscht die Daten im Registrierungs Wert "Optionen" im Unterschlüssel "MyApp" von `HKEY_LOCAL_MACHINE\Software\MyCompany` .</span><span class="sxs-lookup"><span data-stu-id="5758d-114">This command clears the data in the "Options" registry value in the "MyApp" subkey of `HKEY_LOCAL_MACHINE\Software\MyCompany`.</span></span>

```powershell
Clear-ItemProperty -Path "HKLM:\Software\MyCompany\MyApp" -Name "Options"
```

## <span data-ttu-id="5758d-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5758d-115">PARAMETERS</span></span>

### <span data-ttu-id="5758d-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="5758d-116">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="5758d-117">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5758d-117">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="5758d-118">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="5758d-118">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="5758d-119">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="5758d-119">-Exclude</span></span>

<span data-ttu-id="5758d-120">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="5758d-120">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="5758d-121">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="5758d-121">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="5758d-122">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="5758d-122">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="5758d-123">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="5758d-123">Wildcard characters are permitted.</span></span> <span data-ttu-id="5758d-124">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="5758d-124">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="5758d-125">-Filter</span><span class="sxs-lookup"><span data-stu-id="5758d-125">-Filter</span></span>

<span data-ttu-id="5758d-126">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="5758d-126">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="5758d-127">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5758d-127">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="5758d-128">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="5758d-128">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="5758d-129">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="5758d-129">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="5758d-130">-Force</span><span class="sxs-lookup"><span data-stu-id="5758d-130">-Force</span></span>

<span data-ttu-id="5758d-131">Gibt an, dass dieses Cmdlet Eigenschaften aus Elementen löscht, auf die der Benutzer anderweitig nicht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="5758d-131">Indicates that this cmdlet deletes properties from items that cannot otherwise be accessed by the user.</span></span> <span data-ttu-id="5758d-132">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="5758d-132">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="5758d-133">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="5758d-133">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="5758d-134">-Include</span><span class="sxs-lookup"><span data-stu-id="5758d-134">-Include</span></span>

<span data-ttu-id="5758d-135">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="5758d-135">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="5758d-136">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="5758d-136">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="5758d-137">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="5758d-137">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="5758d-138">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="5758d-138">Wildcard characters are permitted.</span></span> <span data-ttu-id="5758d-139">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="5758d-139">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="5758d-140">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="5758d-140">-LiteralPath</span></span>

<span data-ttu-id="5758d-141">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="5758d-141">Specifies a path to one or more locations.</span></span> <span data-ttu-id="5758d-142">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="5758d-142">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="5758d-143">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="5758d-143">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="5758d-144">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="5758d-144">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="5758d-145">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="5758d-145">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="5758d-146">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="5758d-146">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="5758d-147">-Name</span><span class="sxs-lookup"><span data-stu-id="5758d-147">-Name</span></span>

<span data-ttu-id="5758d-148">Gibt den Namen der zu löschenden Eigenschaft an, beispielsweise den Namen eines Registrierungswerts.</span><span class="sxs-lookup"><span data-stu-id="5758d-148">Specifies the name of the property to be cleared, such as the name of a registry value.</span></span>
<span data-ttu-id="5758d-149">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="5758d-149">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="5758d-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5758d-150">-PassThru</span></span>

<span data-ttu-id="5758d-151">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="5758d-151">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="5758d-152">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="5758d-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="5758d-153">-Path</span><span class="sxs-lookup"><span data-stu-id="5758d-153">-Path</span></span>

<span data-ttu-id="5758d-154">Gibt den Pfad zu der Eigenschaft an, die gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="5758d-154">Specifies the path to the property being cleared.</span></span>
<span data-ttu-id="5758d-155">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="5758d-155">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="5758d-156">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="5758d-156">-UseTransaction</span></span>

<span data-ttu-id="5758d-157">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="5758d-157">Includes the command in the active transaction.</span></span>
<span data-ttu-id="5758d-158">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5758d-158">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="5758d-159">Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="5758d-159">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="5758d-160">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5758d-160">-Confirm</span></span>

<span data-ttu-id="5758d-161">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="5758d-161">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5758d-162">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5758d-162">-WhatIf</span></span>

<span data-ttu-id="5758d-163">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5758d-163">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5758d-164">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5758d-164">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5758d-165">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5758d-165">CommonParameters</span></span>

<span data-ttu-id="5758d-166">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="5758d-166">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="5758d-167">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="5758d-167">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="5758d-168">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5758d-168">INPUTS</span></span>

### <span data-ttu-id="5758d-169">System.String</span><span class="sxs-lookup"><span data-stu-id="5758d-169">System.String</span></span>

<span data-ttu-id="5758d-170">Sie können eine Pfad Zeichenfolge über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="5758d-170">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="5758d-171">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5758d-171">OUTPUTS</span></span>

### <span data-ttu-id="5758d-172">None oder System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="5758d-172">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="5758d-173">Wenn Sie den *passthru* -Parameter verwenden, `Clear-ItemProperty` generiert ein **pscustomobject** -Objekt, das die gelöschte Element Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="5758d-173">When you use the *PassThru* parameter, `Clear-ItemProperty` generates a **PSCustomObject** object that represents the cleared item property.</span></span>
<span data-ttu-id="5758d-174">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="5758d-174">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5758d-175">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5758d-175">NOTES</span></span>

<span data-ttu-id="5758d-176">Sie können verwenden `Clear-ItemProperty` , um die Daten in Registrierungs Werten zu löschen, ohne den Wert zu löschen.</span><span class="sxs-lookup"><span data-stu-id="5758d-176">You can use `Clear-ItemProperty` to delete the data in registry values without deleting the value.</span></span> <span data-ttu-id="5758d-177">Wenn der Datentyp des Werts %%amp;quot;Binär%%amp;quot; oder %%amp;quot;DWORD%%amp;quot; ist, wird der Wert durch das Löschen der Daten auf %%amp;quot;0%%amp;quot; festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5758d-177">If the data type of the value is Binary or DWORD, clearing the data sets the value to zero.</span></span> <span data-ttu-id="5758d-178">Andernfalls ist der Wert leer.</span><span class="sxs-lookup"><span data-stu-id="5758d-178">Otherwise, the value is empty.</span></span>

<span data-ttu-id="5758d-179">Das- `Clear-ItemProperty` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="5758d-179">The `Clear-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="5758d-180">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="5758d-180">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="5758d-181">Weitere Informationen finden Sie unter %%amp;quot;about_Providers%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="5758d-181">For more information, see about_Providers.</span></span>

## <span data-ttu-id="5758d-182">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5758d-182">RELATED LINKS</span></span>

[<span data-ttu-id="5758d-183">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5758d-183">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="5758d-184">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5758d-184">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="5758d-185">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5758d-185">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="5758d-186">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5758d-186">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="5758d-187">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5758d-187">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="5758d-188">about_Providers</span><span class="sxs-lookup"><span data-stu-id="5758d-188">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
