---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-ItemProperty
ms.openlocfilehash: d6dd6d21d7c0022e8ca1ea7dbd8e1cab8a680de6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604846"
---
# <span data-ttu-id="ed3a8-102">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ed3a8-102">Copy-ItemProperty</span></span>

## <span data-ttu-id="ed3a8-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ed3a8-103">SYNOPSIS</span></span>
<span data-ttu-id="ed3a8-104">Kopiert eine Eigenschaft und einen Wert von einem bestimmten Speicherort an einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-104">Copies a property and value from a specified location to another location.</span></span>

## <span data-ttu-id="ed3a8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ed3a8-105">SYNTAX</span></span>

### <span data-ttu-id="ed3a8-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="ed3a8-106">Path (Default)</span></span>

```
Copy-ItemProperty [-Path] <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ed3a8-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ed3a8-107">LiteralPath</span></span>

```
Copy-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ed3a8-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ed3a8-108">DESCRIPTION</span></span>

<span data-ttu-id="ed3a8-109">`Copy-ItemProperty`Mit dem-Cmdlet werden eine Eigenschaft und ein Wert von einem angegebenen Speicherort an einen anderen Speicherort kopiert.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-109">The `Copy-ItemProperty` cmdlet copies a property and value from a specified location to another location.</span></span>
<span data-ttu-id="ed3a8-110">Beispielsweise können Sie mit diesem Cmdlet mindestens einen Registrierungs Eintrag aus einem Registrierungsschlüssel in einen anderen Registrierungsschlüssel kopieren.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-110">For instance, you can use this cmdlet to copy one or more registry entries from one registry key to another registry key.</span></span>

## <span data-ttu-id="ed3a8-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ed3a8-111">EXAMPLES</span></span>

### <span data-ttu-id="ed3a8-112">Beispiel 1: Kopieren einer Eigenschaft aus einem Registrierungsschlüssel in einen anderen Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="ed3a8-112">Example 1: Copy a property from a registry key to another registry key</span></span>

<span data-ttu-id="ed3a8-113">Mit diesem Befehl wird die Eigenschaft mit dem Namen "MyProperty" aus dem Registrierungsschlüssel "MyApplication" in den Registrierungsschlüssel "MyApplicationRev2" kopiert.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-113">This command copies the property named "MyProperty" from the "MyApplication" registry key to the "MyApplicationRev2" registry key.</span></span>

```powershell
Copy-ItemProperty -Path "MyApplication" -Destination "HKLM:\Software\MyApplicationRev2" -Name "MyProperty"
```

## <span data-ttu-id="ed3a8-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ed3a8-114">PARAMETERS</span></span>

### <span data-ttu-id="ed3a8-115">-Credential</span><span class="sxs-lookup"><span data-stu-id="ed3a8-115">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="ed3a8-116">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-116">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="ed3a8-117">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="ed3a8-117">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="ed3a8-118">-Destination</span><span class="sxs-lookup"><span data-stu-id="ed3a8-118">-Destination</span></span>

<span data-ttu-id="ed3a8-119">Gibt den Pfad zum Zielspeicherort an.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-119">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="ed3a8-120">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="ed3a8-120">-Exclude</span></span>

<span data-ttu-id="ed3a8-121">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-121">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="ed3a8-122">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-122">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="ed3a8-123">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="ed3a8-123">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="ed3a8-124">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-124">Wildcard characters are permitted.</span></span> <span data-ttu-id="ed3a8-125">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-125">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="ed3a8-126">-Filter</span><span class="sxs-lookup"><span data-stu-id="ed3a8-126">-Filter</span></span>

<span data-ttu-id="ed3a8-127">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-127">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="ed3a8-128">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-128">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="ed3a8-129">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="ed3a8-129">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="ed3a8-130">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-130">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="ed3a8-131">-Force</span><span class="sxs-lookup"><span data-stu-id="ed3a8-131">-Force</span></span>

<span data-ttu-id="ed3a8-132">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-132">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="ed3a8-133">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-133">Implementation varies from provider to provider.</span></span>

<span data-ttu-id="ed3a8-134">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="ed3a8-134">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="ed3a8-135">-Include</span><span class="sxs-lookup"><span data-stu-id="ed3a8-135">-Include</span></span>

<span data-ttu-id="ed3a8-136">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-136">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="ed3a8-137">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="ed3a8-138">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="ed3a8-138">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="ed3a8-139">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="ed3a8-140">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-140">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="ed3a8-141">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="ed3a8-141">-LiteralPath</span></span>

<span data-ttu-id="ed3a8-142">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-142">Specifies a path to one or more locations.</span></span> <span data-ttu-id="ed3a8-143">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-143">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="ed3a8-144">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="ed3a8-145">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ed3a8-146">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="ed3a8-147">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="ed3a8-147">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="ed3a8-148">-Name</span><span class="sxs-lookup"><span data-stu-id="ed3a8-148">-Name</span></span>

<span data-ttu-id="ed3a8-149">Gibt den Namen der zu kopierenden Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-149">Specifies the name of the property to be copied.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ed3a8-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ed3a8-150">-PassThru</span></span>

<span data-ttu-id="ed3a8-151">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-151">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="ed3a8-152">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="ed3a8-153">-Path</span><span class="sxs-lookup"><span data-stu-id="ed3a8-153">-Path</span></span>

<span data-ttu-id="ed3a8-154">Gibt als Zeichen folgen Array den Pfad zu der Eigenschaft an, die kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-154">Specifies, as a string array, the path to the property to be copied.</span></span>
<span data-ttu-id="ed3a8-155">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-155">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="ed3a8-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ed3a8-156">-Confirm</span></span>

<span data-ttu-id="ed3a8-157">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ed3a8-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ed3a8-158">-WhatIf</span></span>

<span data-ttu-id="ed3a8-159">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-159">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ed3a8-160">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ed3a8-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ed3a8-161">CommonParameters</span></span>

<span data-ttu-id="ed3a8-162">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="ed3a8-162">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="ed3a8-163">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="ed3a8-163">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="ed3a8-164">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ed3a8-164">INPUTS</span></span>

### <span data-ttu-id="ed3a8-165">System.String</span><span class="sxs-lookup"><span data-stu-id="ed3a8-165">System.String</span></span>

<span data-ttu-id="ed3a8-166">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-166">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="ed3a8-167">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ed3a8-167">OUTPUTS</span></span>

### <span data-ttu-id="ed3a8-168">None oder System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="ed3a8-168">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="ed3a8-169">Wenn Sie den **passthru** -Parameter verwenden, generiert dieses Cmdlet ein **pscustomobject-Objekt** , das die kopierte Element Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-169">When you use the **Passthru** parameter, this cmdlet generates a **PsCustomObject** representing the copied item property.</span></span> <span data-ttu-id="ed3a8-170">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-170">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ed3a8-171">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ed3a8-171">NOTES</span></span>

<span data-ttu-id="ed3a8-172">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-172">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="ed3a8-173">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="ed3a8-173">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="ed3a8-174">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="ed3a8-174">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="ed3a8-175">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ed3a8-175">RELATED LINKS</span></span>

[<span data-ttu-id="ed3a8-176">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ed3a8-176">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="ed3a8-177">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ed3a8-177">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="ed3a8-178">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ed3a8-178">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="ed3a8-179">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ed3a8-179">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="ed3a8-180">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ed3a8-180">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="ed3a8-181">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ed3a8-181">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="ed3a8-182">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="ed3a8-182">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="ed3a8-183">about_Providers</span><span class="sxs-lookup"><span data-stu-id="ed3a8-183">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

