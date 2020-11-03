---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-itemproperty?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ItemProperty
ms.openlocfilehash: e3c1d1641c6f4b30b17c9f0f6703cd063663f25b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211599"
---
# <span data-ttu-id="b36c5-103">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b36c5-103">Move-ItemProperty</span></span>

## <span data-ttu-id="b36c5-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b36c5-104">Synopsis</span></span>
<span data-ttu-id="b36c5-105">Verschiebt eine Eigenschaft von einem Speicherort an einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b36c5-105">Moves a property from one location to another.</span></span>

## <span data-ttu-id="b36c5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b36c5-106">SYNTAX</span></span>

### <span data-ttu-id="b36c5-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="b36c5-107">Path (Default)</span></span>

```
Move-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b36c5-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b36c5-108">LiteralPath</span></span>

```
Move-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b36c5-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b36c5-109">Description</span></span>

<span data-ttu-id="b36c5-110">Mit dem- `Move-ItemProperty` Cmdlet wird eine Eigenschaft eines Elements von einem Element zu einem anderen Element verschoben.</span><span class="sxs-lookup"><span data-stu-id="b36c5-110">The `Move-ItemProperty` cmdlet moves a property of an item from one item to another item.</span></span>
<span data-ttu-id="b36c5-111">Beispielsweise kann ein Registrierungs Eintrag von einem Registrierungsschlüssel in einen anderen Registrierungsschlüssel verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b36c5-111">For instance, it can move a registry entry from one registry key to another registry key.</span></span>
<span data-ttu-id="b36c5-112">Beim Verschieben einer Elementeigenschaft wird diese am neuen Speicherort hinzugefügt und an ihrem ursprünglichen Speicherort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b36c5-112">When you move an item property, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="b36c5-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b36c5-113">EXAMPLES</span></span>

### <span data-ttu-id="b36c5-114">Beispiel 1: Verschieben eines Registrierungs Werts und seiner Daten in einen anderen Schlüssel</span><span class="sxs-lookup"><span data-stu-id="b36c5-114">Example 1: Move a registry value and its data to another key</span></span>

<span data-ttu-id="b36c5-115">Dieser Befehl verschiebt den Versions Registrierungs Wert und seine Daten aus dem Unterschlüssel "MyApp" in den newapp-Unterschlüssel des `HKLM\Software\MyCompany` Registrierungsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="b36c5-115">This command moves the Version registry value, and its data, from the "MyApp" subkey to the NewApp subkey of the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Move-ItemProperty "HKLM:\Software\MyCompany\MyApp" -Name "Version" -Destination "HKLM:\Software\MyCompany\NewApp"
```

## <span data-ttu-id="b36c5-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b36c5-116">PARAMETERS</span></span>

### <span data-ttu-id="b36c5-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="b36c5-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="b36c5-118">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b36c5-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="b36c5-119">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="b36c5-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="b36c5-120">-Destination</span><span class="sxs-lookup"><span data-stu-id="b36c5-120">-Destination</span></span>

<span data-ttu-id="b36c5-121">Gibt den Pfad zum Zielspeicherort an.</span><span class="sxs-lookup"><span data-stu-id="b36c5-121">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="b36c5-122">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="b36c5-122">-Exclude</span></span>

<span data-ttu-id="b36c5-123">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="b36c5-123">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="b36c5-124">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="b36c5-124">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="b36c5-125">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="b36c5-125">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="b36c5-126">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="b36c5-126">Wildcard characters are permitted.</span></span> <span data-ttu-id="b36c5-127">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="b36c5-127">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="b36c5-128">-Filter</span><span class="sxs-lookup"><span data-stu-id="b36c5-128">-Filter</span></span>

<span data-ttu-id="b36c5-129">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="b36c5-129">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="b36c5-130">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b36c5-130">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="b36c5-131">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="b36c5-131">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="b36c5-132">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="b36c5-132">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="b36c5-133">-Force</span><span class="sxs-lookup"><span data-stu-id="b36c5-133">-Force</span></span>

<span data-ttu-id="b36c5-134">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b36c5-134">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="b36c5-135">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="b36c5-135">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="b36c5-136">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b36c5-136">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="b36c5-137">-Include</span><span class="sxs-lookup"><span data-stu-id="b36c5-137">-Include</span></span>

<span data-ttu-id="b36c5-138">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="b36c5-138">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="b36c5-139">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="b36c5-139">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="b36c5-140">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="b36c5-140">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="b36c5-141">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="b36c5-141">Wildcard characters are permitted.</span></span> <span data-ttu-id="b36c5-142">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="b36c5-142">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="b36c5-143">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="b36c5-143">-LiteralPath</span></span>

<span data-ttu-id="b36c5-144">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="b36c5-144">Specifies a path to one or more locations.</span></span> <span data-ttu-id="b36c5-145">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b36c5-145">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="b36c5-146">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="b36c5-146">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="b36c5-147">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="b36c5-147">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="b36c5-148">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="b36c5-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="b36c5-149">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="b36c5-149">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="b36c5-150">-Name</span><span class="sxs-lookup"><span data-stu-id="b36c5-150">-Name</span></span>

<span data-ttu-id="b36c5-151">Gibt den Namen der zu verschiebenden Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="b36c5-151">Specifies the name of the property to be moved.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b36c5-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b36c5-152">-PassThru</span></span>

<span data-ttu-id="b36c5-153">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="b36c5-153">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="b36c5-154">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="b36c5-154">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b36c5-155">-Path</span><span class="sxs-lookup"><span data-stu-id="b36c5-155">-Path</span></span>

<span data-ttu-id="b36c5-156">Gibt den Pfad zum aktuellen Speicherort der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="b36c5-156">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="b36c5-157">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="b36c5-157">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b36c5-158">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b36c5-158">-Confirm</span></span>

<span data-ttu-id="b36c5-159">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b36c5-159">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b36c5-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b36c5-160">-WhatIf</span></span>

<span data-ttu-id="b36c5-161">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b36c5-161">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b36c5-162">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b36c5-162">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b36c5-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b36c5-163">CommonParameters</span></span>

<span data-ttu-id="b36c5-164">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="b36c5-164">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="b36c5-165">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b36c5-165">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b36c5-166">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b36c5-166">INPUTS</span></span>

### <span data-ttu-id="b36c5-167">System.String</span><span class="sxs-lookup"><span data-stu-id="b36c5-167">System.String</span></span>

<span data-ttu-id="b36c5-168">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="b36c5-168">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="b36c5-169">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b36c5-169">OUTPUTS</span></span>

### <span data-ttu-id="b36c5-170">None oder System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="b36c5-170">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="b36c5-171">Wenn Sie den **passthru** -Parameter verwenden, generiert dieses Cmdlet ein **pscustomobject-Objekt** , das die verschoderte Element Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="b36c5-171">When you use the **PassThru** parameter, this cmdlet generates a **PSCustomObject** representing the moved item property.</span></span> <span data-ttu-id="b36c5-172">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="b36c5-172">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b36c5-173">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b36c5-173">NOTES</span></span>

<span data-ttu-id="b36c5-174">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="b36c5-174">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="b36c5-175">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="b36c5-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="b36c5-176">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b36c5-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="b36c5-177">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b36c5-177">RELATED LINKS</span></span>

[<span data-ttu-id="b36c5-178">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b36c5-178">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="b36c5-179">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b36c5-179">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="b36c5-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b36c5-180">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="b36c5-181">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b36c5-181">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="b36c5-182">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b36c5-182">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="b36c5-183">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b36c5-183">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="b36c5-184">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b36c5-184">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="b36c5-185">about_Providers</span><span class="sxs-lookup"><span data-stu-id="b36c5-185">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

