---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ItemProperty
ms.openlocfilehash: 4cf883964e1ff86487bf5abca8789af62b274c8a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214623"
---
# <span data-ttu-id="2d378-103">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d378-103">Move-ItemProperty</span></span>

## <span data-ttu-id="2d378-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="2d378-104">Synopsis</span></span>
<span data-ttu-id="2d378-105">Verschiebt eine Eigenschaft von einem Speicherort an einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="2d378-105">Moves a property from one location to another.</span></span>

## <span data-ttu-id="2d378-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2d378-106">SYNTAX</span></span>

### <span data-ttu-id="2d378-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="2d378-107">Path (Default)</span></span>

```
Move-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="2d378-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2d378-108">LiteralPath</span></span>

```
Move-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="2d378-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2d378-109">Description</span></span>

<span data-ttu-id="2d378-110">Mit dem- `Move-ItemProperty` Cmdlet wird eine Eigenschaft eines Elements von einem Element zu einem anderen Element verschoben.</span><span class="sxs-lookup"><span data-stu-id="2d378-110">The `Move-ItemProperty` cmdlet moves a property of an item from one item to another item.</span></span>
<span data-ttu-id="2d378-111">Beispielsweise kann ein Registrierungs Eintrag von einem Registrierungsschlüssel in einen anderen Registrierungsschlüssel verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="2d378-111">For instance, it can move a registry entry from one registry key to another registry key.</span></span>
<span data-ttu-id="2d378-112">Beim Verschieben einer Elementeigenschaft wird diese am neuen Speicherort hinzugefügt und an ihrem ursprünglichen Speicherort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="2d378-112">When you move an item property, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="2d378-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2d378-113">EXAMPLES</span></span>

### <span data-ttu-id="2d378-114">Beispiel 1: Verschieben eines Registrierungs Werts und seiner Daten in einen anderen Schlüssel</span><span class="sxs-lookup"><span data-stu-id="2d378-114">Example 1: Move a registry value and its data to another key</span></span>

<span data-ttu-id="2d378-115">Dieser Befehl verschiebt den Versions Registrierungs Wert und seine Daten aus dem Unterschlüssel "MyApp" in den newapp-Unterschlüssel des `HKLM\Software\MyCompany` Registrierungsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="2d378-115">This command moves the Version registry value, and its data, from the "MyApp" subkey to the NewApp subkey of the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Move-ItemProperty "HKLM:\Software\MyCompany\MyApp" -Name "Version" -Destination "HKLM:\Software\MyCompany\NewApp"
```

## <span data-ttu-id="2d378-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2d378-116">PARAMETERS</span></span>

### <span data-ttu-id="2d378-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="2d378-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="2d378-118">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2d378-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="2d378-119">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="2d378-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="2d378-120">-Destination</span><span class="sxs-lookup"><span data-stu-id="2d378-120">-Destination</span></span>

<span data-ttu-id="2d378-121">Gibt den Pfad zum Zielspeicherort an.</span><span class="sxs-lookup"><span data-stu-id="2d378-121">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="2d378-122">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="2d378-122">-Exclude</span></span>

<span data-ttu-id="2d378-123">Gibt als Zeichen folgen Array eine Eigenschaft oder eine Eigenschaft an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="2d378-123">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="2d378-124">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="2d378-124">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="2d378-125">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="2d378-125">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="2d378-126">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="2d378-126">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="2d378-127">-Filter</span><span class="sxs-lookup"><span data-stu-id="2d378-127">-Filter</span></span>

<span data-ttu-id="2d378-128">Gibt einen Filter im Format oder in der Sprache des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="2d378-128">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="2d378-129">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="2d378-129">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="2d378-130">Die Syntax des Filters, einschließlich der Verwendung von Platzhalter Zeichen, hängt vom Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="2d378-130">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="2d378-131">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="2d378-131">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="2d378-132">-Force</span><span class="sxs-lookup"><span data-stu-id="2d378-132">-Force</span></span>

<span data-ttu-id="2d378-133">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2d378-133">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="2d378-134">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="2d378-134">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="2d378-135">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="2d378-135">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="2d378-136">-Include</span><span class="sxs-lookup"><span data-stu-id="2d378-136">-Include</span></span>

<span data-ttu-id="2d378-137">Gibt als Zeichen folgen Array eine Eigenschaft oder eine Eigenschaft an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="2d378-137">Specifies, as a string array, a property or property that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="2d378-138">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="2d378-138">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="2d378-139">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="2d378-139">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="2d378-140">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="2d378-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="2d378-141">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="2d378-141">-LiteralPath</span></span>

<span data-ttu-id="2d378-142">Gibt den Pfad zum aktuellen Speicherort der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="2d378-142">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="2d378-143">Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2d378-143">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="2d378-144">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="2d378-144">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="2d378-145">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="2d378-145">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="2d378-146">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="2d378-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="2d378-147">-Name</span><span class="sxs-lookup"><span data-stu-id="2d378-147">-Name</span></span>

<span data-ttu-id="2d378-148">Gibt den Namen der zu verschiebenden Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="2d378-148">Specifies the name of the property to be moved.</span></span>

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

### <span data-ttu-id="2d378-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2d378-149">-PassThru</span></span>

<span data-ttu-id="2d378-150">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="2d378-150">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="2d378-151">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="2d378-151">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="2d378-152">-Path</span><span class="sxs-lookup"><span data-stu-id="2d378-152">-Path</span></span>

<span data-ttu-id="2d378-153">Gibt den Pfad zum aktuellen Speicherort der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="2d378-153">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="2d378-154">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="2d378-154">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="2d378-155">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="2d378-155">-UseTransaction</span></span>

<span data-ttu-id="2d378-156">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="2d378-156">Includes the command in the active transaction.</span></span>
<span data-ttu-id="2d378-157">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d378-157">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="2d378-158">Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="2d378-158">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="2d378-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2d378-159">-Confirm</span></span>

<span data-ttu-id="2d378-160">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="2d378-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2d378-161">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2d378-161">-WhatIf</span></span>

<span data-ttu-id="2d378-162">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d378-162">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2d378-163">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d378-163">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2d378-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2d378-164">CommonParameters</span></span>

<span data-ttu-id="2d378-165">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="2d378-165">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="2d378-166">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="2d378-166">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="2d378-167">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2d378-167">INPUTS</span></span>

### <span data-ttu-id="2d378-168">System.String</span><span class="sxs-lookup"><span data-stu-id="2d378-168">System.String</span></span>

<span data-ttu-id="2d378-169">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="2d378-169">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="2d378-170">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2d378-170">OUTPUTS</span></span>

### <span data-ttu-id="2d378-171">None oder System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="2d378-171">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="2d378-172">Wenn Sie den **passthru** -Parameter verwenden, generiert dieses Cmdlet ein **pscustomobject-Objekt** , das die verschoderte Element Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="2d378-172">When you use the **PassThru** parameter, this cmdlet generates a **PSCustomObject** representing the moved item property.</span></span>
<span data-ttu-id="2d378-173">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="2d378-173">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2d378-174">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2d378-174">NOTES</span></span>

<span data-ttu-id="2d378-175">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="2d378-175">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="2d378-176">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="2d378-176">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="2d378-177">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="2d378-177">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="2d378-178">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2d378-178">RELATED LINKS</span></span>

[<span data-ttu-id="2d378-179">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d378-179">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="2d378-180">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d378-180">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="2d378-181">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d378-181">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="2d378-182">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d378-182">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="2d378-183">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d378-183">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="2d378-184">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d378-184">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="2d378-185">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2d378-185">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="2d378-186">about_Providers</span><span class="sxs-lookup"><span data-stu-id="2d378-186">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
