---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-ItemProperty
ms.openlocfilehash: fc454095f9610e8712af18bfe1558e275324cefe
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602108"
---
# <span data-ttu-id="a9f2f-102">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a9f2f-102">Clear-ItemProperty</span></span>

## <span data-ttu-id="a9f2f-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a9f2f-103">SYNOPSIS</span></span>
<span data-ttu-id="a9f2f-104">Löscht den Wert einer Eigenschaft, löscht jedoch nicht die-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-104">Clears the value of a property but does not delete the property.</span></span>

## <span data-ttu-id="a9f2f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a9f2f-105">SYNTAX</span></span>

### <span data-ttu-id="a9f2f-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="a9f2f-106">Path (Default)</span></span>

```
Clear-ItemProperty [-Path] <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a9f2f-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a9f2f-107">LiteralPath</span></span>

```
Clear-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a9f2f-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a9f2f-108">DESCRIPTION</span></span>

<span data-ttu-id="a9f2f-109">Mit dem- `Clear-ItemProperty` Cmdlet wird der Wert einer Eigenschaft gelöscht, die Eigenschaft wird jedoch nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-109">The `Clear-ItemProperty` cmdlet clears the value of a property, but it does not delete the property.</span></span>
<span data-ttu-id="a9f2f-110">Mit diesem Cmdlet können Sie die Daten aus einem Registrierungswert löschen.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-110">You can use this cmdlet to delete the data from a registry value.</span></span>

## <span data-ttu-id="a9f2f-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a9f2f-111">EXAMPLES</span></span>

### <span data-ttu-id="a9f2f-112">Beispiel 1: Löschen des Werts des Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="a9f2f-112">Example 1: Clear the value of registry key</span></span>

<span data-ttu-id="a9f2f-113">Dieser Befehl löscht die Daten im Registrierungs Wert "Optionen" im Unterschlüssel "MyApp" von `HKEY_LOCAL_MACHINE\Software\MyCompany` .</span><span class="sxs-lookup"><span data-stu-id="a9f2f-113">This command clears the data in the "Options" registry value in the "MyApp" subkey of `HKEY_LOCAL_MACHINE\Software\MyCompany`.</span></span>

```powershell
Clear-ItemProperty -Path "HKLM:\Software\MyCompany\MyApp" -Name "Options"
```

## <span data-ttu-id="a9f2f-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a9f2f-114">PARAMETERS</span></span>

### <span data-ttu-id="a9f2f-115">-Credential</span><span class="sxs-lookup"><span data-stu-id="a9f2f-115">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="a9f2f-116">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-116">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="a9f2f-117">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="a9f2f-117">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="a9f2f-118">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="a9f2f-118">-Exclude</span></span>

<span data-ttu-id="a9f2f-119">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-119">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="a9f2f-120">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-120">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a9f2f-121">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="a9f2f-121">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="a9f2f-122">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-122">Wildcard characters are permitted.</span></span> <span data-ttu-id="a9f2f-123">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-123">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="a9f2f-124">-Filter</span><span class="sxs-lookup"><span data-stu-id="a9f2f-124">-Filter</span></span>

<span data-ttu-id="a9f2f-125">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-125">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="a9f2f-126">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-126">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="a9f2f-127">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="a9f2f-127">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="a9f2f-128">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-128">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="a9f2f-129">-Force</span><span class="sxs-lookup"><span data-stu-id="a9f2f-129">-Force</span></span>

<span data-ttu-id="a9f2f-130">Gibt an, dass dieses Cmdlet Eigenschaften aus Elementen löscht, auf die der Benutzer anderweitig nicht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-130">Indicates that this cmdlet deletes properties from items that cannot otherwise be accessed by the user.</span></span> <span data-ttu-id="a9f2f-131">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-131">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="a9f2f-132">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="a9f2f-132">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="a9f2f-133">-Include</span><span class="sxs-lookup"><span data-stu-id="a9f2f-133">-Include</span></span>

<span data-ttu-id="a9f2f-134">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-134">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="a9f2f-135">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-135">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a9f2f-136">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="a9f2f-136">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="a9f2f-137">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-137">Wildcard characters are permitted.</span></span> <span data-ttu-id="a9f2f-138">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-138">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="a9f2f-139">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="a9f2f-139">-LiteralPath</span></span>

<span data-ttu-id="a9f2f-140">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-140">Specifies a path to one or more locations.</span></span> <span data-ttu-id="a9f2f-141">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-141">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="a9f2f-142">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-142">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="a9f2f-143">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-143">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="a9f2f-144">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-144">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="a9f2f-145">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="a9f2f-145">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="a9f2f-146">-Name</span><span class="sxs-lookup"><span data-stu-id="a9f2f-146">-Name</span></span>

<span data-ttu-id="a9f2f-147">Gibt den Namen der zu löschenden Eigenschaft an, beispielsweise den Namen eines Registrierungswerts.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-147">Specifies the name of the property to be cleared, such as the name of a registry value.</span></span>
<span data-ttu-id="a9f2f-148">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-148">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a9f2f-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a9f2f-149">-PassThru</span></span>

<span data-ttu-id="a9f2f-150">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-150">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="a9f2f-151">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-151">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a9f2f-152">-Path</span><span class="sxs-lookup"><span data-stu-id="a9f2f-152">-Path</span></span>

<span data-ttu-id="a9f2f-153">Gibt den Pfad zu der Eigenschaft an, die gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-153">Specifies the path to the property being cleared.</span></span>
<span data-ttu-id="a9f2f-154">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-154">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a9f2f-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a9f2f-155">-Confirm</span></span>

<span data-ttu-id="a9f2f-156">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-156">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a9f2f-157">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a9f2f-157">-WhatIf</span></span>

<span data-ttu-id="a9f2f-158">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-158">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a9f2f-159">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-159">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a9f2f-160">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a9f2f-160">CommonParameters</span></span>

<span data-ttu-id="a9f2f-161">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="a9f2f-161">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="a9f2f-162">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a9f2f-162">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a9f2f-163">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a9f2f-163">INPUTS</span></span>

### <span data-ttu-id="a9f2f-164">System.String</span><span class="sxs-lookup"><span data-stu-id="a9f2f-164">System.String</span></span>

<span data-ttu-id="a9f2f-165">Sie können eine Pfad Zeichenfolge über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-165">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="a9f2f-166">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a9f2f-166">OUTPUTS</span></span>

### <span data-ttu-id="a9f2f-167">None oder System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="a9f2f-167">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="a9f2f-168">Wenn Sie den **passthru** -Parameter verwenden, `Clear-ItemProperty` generiert ein **pscustomobject** -Objekt, das die gelöschte Element Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-168">When you use the **PassThru** parameter, `Clear-ItemProperty` generates a **PSCustomObject** object that represents the cleared item property.</span></span> <span data-ttu-id="a9f2f-169">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-169">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a9f2f-170">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a9f2f-170">NOTES</span></span>

- <span data-ttu-id="a9f2f-171">Sie können verwenden `Clear-ItemProperty` , um die Daten in Registrierungs Werten zu löschen, ohne den Wert zu löschen.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-171">You can use `Clear-ItemProperty` to delete the data in registry values without deleting the value.</span></span>
  <span data-ttu-id="a9f2f-172">Wenn der Datentyp des Werts %%amp;quot;Binär%%amp;quot; oder %%amp;quot;DWORD%%amp;quot; ist, wird der Wert durch das Löschen der Daten auf %%amp;quot;0%%amp;quot; festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-172">If the data type of the value is Binary or DWORD, clearing the data sets the value to zero.</span></span>
  <span data-ttu-id="a9f2f-173">Andernfalls ist der Wert leer.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-173">Otherwise, the value is empty.</span></span>
- <span data-ttu-id="a9f2f-174">Das- `Clear-ItemProperty` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="a9f2f-174">The `Clear-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="a9f2f-175">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="a9f2f-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="a9f2f-176">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="a9f2f-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="a9f2f-177">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a9f2f-177">RELATED LINKS</span></span>

[<span data-ttu-id="a9f2f-178">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a9f2f-178">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="a9f2f-179">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a9f2f-179">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="a9f2f-180">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a9f2f-180">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="a9f2f-181">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a9f2f-181">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="a9f2f-182">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a9f2f-182">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="a9f2f-183">about_Providers</span><span class="sxs-lookup"><span data-stu-id="a9f2f-183">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

