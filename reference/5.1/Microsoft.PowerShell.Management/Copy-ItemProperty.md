---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-ItemProperty
ms.openlocfilehash: 7af5a414a84bad8048c997803c94c0d94e549989
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215540"
---
# <span data-ttu-id="596be-103">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="596be-103">Copy-ItemProperty</span></span>

## <span data-ttu-id="596be-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="596be-104">SYNOPSIS</span></span>

<span data-ttu-id="596be-105">Kopiert eine Eigenschaft und einen Wert von einem bestimmten Speicherort an einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="596be-105">Copies a property and value from a specified location to another location.</span></span>

## <span data-ttu-id="596be-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="596be-106">SYNTAX</span></span>

### <span data-ttu-id="596be-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="596be-107">Path (Default)</span></span>

```
Copy-ItemProperty [-Path] <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="596be-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="596be-108">LiteralPath</span></span>

```
Copy-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="596be-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="596be-109">DESCRIPTION</span></span>

<span data-ttu-id="596be-110">`Copy-ItemProperty`Mit dem-Cmdlet werden eine Eigenschaft und ein Wert von einem angegebenen Speicherort an einen anderen Speicherort kopiert.</span><span class="sxs-lookup"><span data-stu-id="596be-110">The `Copy-ItemProperty` cmdlet copies a property and value from a specified location to another location.</span></span>
<span data-ttu-id="596be-111">Beispielsweise können Sie mit diesem Cmdlet mindestens einen Registrierungs Eintrag aus einem Registrierungsschlüssel in einen anderen Registrierungsschlüssel kopieren.</span><span class="sxs-lookup"><span data-stu-id="596be-111">For instance, you can use this cmdlet to copy one or more registry entries from one registry key to another registry key.</span></span>

## <span data-ttu-id="596be-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="596be-112">EXAMPLES</span></span>

### <span data-ttu-id="596be-113">Beispiel 1: Kopieren einer Eigenschaft aus einem Registrierungsschlüssel in einen anderen Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="596be-113">Example 1: Copy a property from a registry key to another registry key</span></span>

<span data-ttu-id="596be-114">Mit diesem Befehl wird die Eigenschaft mit dem Namen "MyProperty" aus dem Registrierungsschlüssel "MyApplication" in den Registrierungsschlüssel "MyApplicationRev2" kopiert.</span><span class="sxs-lookup"><span data-stu-id="596be-114">This command copies the property named "MyProperty" from the "MyApplication" registry key to the "MyApplicationRev2" registry key.</span></span>

```powershell
Copy-ItemProperty -Path "MyApplication" -Destination "HKLM:\Software\MyApplicationRev2" -Name "MyProperty"
```

## <span data-ttu-id="596be-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="596be-115">PARAMETERS</span></span>

### <span data-ttu-id="596be-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="596be-116">-Credential</span></span>

<span data-ttu-id="596be-117">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="596be-117">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="596be-118">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="596be-118">The default is the current user.</span></span>

<span data-ttu-id="596be-119">Geben Sie einen Benutzernamen ein, z. B. %%amp;quot;User01%%amp;quot; oder %%amp;quot;Domain01\User01%%amp;quot;, oder geben Sie ein **PSCredential** -Objekt ein, z. B. ein vom `Get-Credential`-Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="596be-119">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="596be-120">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="596be-120">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="596be-121">Dieser Parameter wird nicht von mit Windows PowerShell installierten Anbietern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="596be-121">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

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

### <span data-ttu-id="596be-122">-Destination</span><span class="sxs-lookup"><span data-stu-id="596be-122">-Destination</span></span>

<span data-ttu-id="596be-123">Gibt den Pfad zum Zielspeicherort an.</span><span class="sxs-lookup"><span data-stu-id="596be-123">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="596be-124">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="596be-124">-Exclude</span></span>

<span data-ttu-id="596be-125">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="596be-125">Specifies, as a string array, an item or items that this cmdlet excludes.</span></span>
<span data-ttu-id="596be-126">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="596be-126">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="596be-127">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="596be-127">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="596be-128">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="596be-128">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="596be-129">-Filter</span><span class="sxs-lookup"><span data-stu-id="596be-129">-Filter</span></span>

<span data-ttu-id="596be-130">Gibt einen Filter im Format oder in der Sprache des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="596be-130">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="596be-131">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="596be-131">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="596be-132">Die Syntax des Filters, einschließlich der Verwendung von Platzhalter Zeichen, hängt vom Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="596be-132">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="596be-133">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="596be-133">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="596be-134">-Force</span><span class="sxs-lookup"><span data-stu-id="596be-134">-Force</span></span>

<span data-ttu-id="596be-135">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="596be-135">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="596be-136">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="596be-136">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="596be-137">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="596be-137">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="596be-138">-Include</span><span class="sxs-lookup"><span data-stu-id="596be-138">-Include</span></span>

<span data-ttu-id="596be-139">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="596be-139">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="596be-140">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="596be-140">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="596be-141">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="596be-141">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="596be-142">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="596be-142">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="596be-143">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="596be-143">-LiteralPath</span></span>

<span data-ttu-id="596be-144">Gibt den Pfad zum aktuellen Speicherort der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="596be-144">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="596be-145">Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="596be-145">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="596be-146">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="596be-146">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="596be-147">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="596be-147">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="596be-148">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="596be-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="596be-149">-Name</span><span class="sxs-lookup"><span data-stu-id="596be-149">-Name</span></span>

<span data-ttu-id="596be-150">Gibt den Namen der zu kopierenden Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="596be-150">Specifies the name of the property to be copied.</span></span>

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

### <span data-ttu-id="596be-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="596be-151">-PassThru</span></span>

<span data-ttu-id="596be-152">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="596be-152">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="596be-153">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="596be-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="596be-154">-Path</span><span class="sxs-lookup"><span data-stu-id="596be-154">-Path</span></span>

<span data-ttu-id="596be-155">Gibt als Zeichen folgen Array den Pfad zu der Eigenschaft an, die kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="596be-155">Specifies, as a string array, the path to the property to be copied.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="596be-156">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="596be-156">-UseTransaction</span></span>
<span data-ttu-id="596be-157">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="596be-157">Includes the command in the active transaction.</span></span>
<span data-ttu-id="596be-158">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="596be-158">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="596be-159">Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="596be-159">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="596be-160">-Confirm</span><span class="sxs-lookup"><span data-stu-id="596be-160">-Confirm</span></span>
<span data-ttu-id="596be-161">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="596be-161">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="596be-162">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="596be-162">-WhatIf</span></span>

<span data-ttu-id="596be-163">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="596be-163">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="596be-164">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="596be-164">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="596be-165">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="596be-165">CommonParameters</span></span>

<span data-ttu-id="596be-166">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="596be-166">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="596be-167">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="596be-167">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="596be-168">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="596be-168">INPUTS</span></span>

### <span data-ttu-id="596be-169">System.String</span><span class="sxs-lookup"><span data-stu-id="596be-169">System.String</span></span>

<span data-ttu-id="596be-170">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="596be-170">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="596be-171">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="596be-171">OUTPUTS</span></span>

### <span data-ttu-id="596be-172">None oder System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="596be-172">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="596be-173">Wenn Sie den **passthru** -Parameter verwenden, generiert dieses Cmdlet ein **pscustomobject-Objekt** , das die kopierte Element Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="596be-173">When you use the **Passthru** parameter, this cmdlet generates a **PsCustomObject** representing the copied item property.</span></span>
<span data-ttu-id="596be-174">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="596be-174">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="596be-175">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="596be-175">NOTES</span></span>

<span data-ttu-id="596be-176">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="596be-176">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="596be-177">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="596be-177">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="596be-178">Weitere Informationen finden Sie unter %%amp;quot;about_Providers%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="596be-178">For more information, see about_Providers.</span></span>

## <span data-ttu-id="596be-179">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="596be-179">RELATED LINKS</span></span>

[<span data-ttu-id="596be-180">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="596be-180">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="596be-181">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="596be-181">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="596be-182">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="596be-182">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="596be-183">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="596be-183">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="596be-184">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="596be-184">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="596be-185">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="596be-185">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="596be-186">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="596be-186">Get-PSProvider</span></span>](Get-PSProvider.md)
