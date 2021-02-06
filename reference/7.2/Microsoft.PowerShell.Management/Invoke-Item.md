---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Item
ms.openlocfilehash: ebb79f16447aef2dd194505d805a34353f710e69
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601909"
---
# <span data-ttu-id="e7066-102">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="e7066-102">Invoke-Item</span></span>

## <span data-ttu-id="e7066-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e7066-103">SYNOPSIS</span></span>
<span data-ttu-id="e7066-104">Führt die Standardaktion für das angegebene Element aus.</span><span class="sxs-lookup"><span data-stu-id="e7066-104">Performs the default action on the specified item.</span></span>

## <span data-ttu-id="e7066-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e7066-105">SYNTAX</span></span>

### <span data-ttu-id="e7066-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="e7066-106">Path (Default)</span></span>

```
Invoke-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e7066-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e7066-107">LiteralPath</span></span>

```
Invoke-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e7066-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e7066-108">DESCRIPTION</span></span>

<span data-ttu-id="e7066-109">Das- `Invoke-Item` Cmdlet führt die Standardaktion für das angegebene Element aus.</span><span class="sxs-lookup"><span data-stu-id="e7066-109">The `Invoke-Item` cmdlet performs the default action on the specified item.</span></span>
<span data-ttu-id="e7066-110">Beispielsweise wird eine ausführbare Datei ausgeführt oder eine Dokumentdatei in der Anwendung geöffnet, die dem Dokumentdateityp zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e7066-110">For example, it runs an executable file or opens a document file in the application associated with the document file type.</span></span>
<span data-ttu-id="e7066-111">Die Standardaktion hängt vom Typ des Elements ab und wird vom PowerShell-Anbieter bestimmt, der den Zugriff auf die Daten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e7066-111">The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.</span></span>

## <span data-ttu-id="e7066-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e7066-112">EXAMPLES</span></span>

### <span data-ttu-id="e7066-113">Beispiel 1: Öffnen einer Datei</span><span class="sxs-lookup"><span data-stu-id="e7066-113">Example 1: Open a file</span></span>

<span data-ttu-id="e7066-114">Mit diesem Befehl wird die Datei "aliasApr04.doc" in Microsoft Office Word geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e7066-114">This command opens the file "aliasApr04.doc" in Microsoft Office Word.</span></span>
<span data-ttu-id="e7066-115">In diesem Fall ist das Öffnen in Word die Standardaktion für doc-Dateien.</span><span class="sxs-lookup"><span data-stu-id="e7066-115">In this case, opening in Word is the default action for ".doc" files.</span></span>

```powershell
Invoke-Item "C:\Test\aliasApr04.doc"
```

### <span data-ttu-id="e7066-116">Beispiel 2: Öffnen aller Dateien eines bestimmten Typs</span><span class="sxs-lookup"><span data-stu-id="e7066-116">Example 2: Open all files of a specific type</span></span>

<span data-ttu-id="e7066-117">Dieser Befehl öffnet alle Microsoft Office Excel-Arbeitsblätter im `C:\Documents and
Settings\Lister\My Documents` Ordner.</span><span class="sxs-lookup"><span data-stu-id="e7066-117">This command opens all of the Microsoft Office Excel spreadsheets in the `C:\Documents and
Settings\Lister\My Documents` folder.</span></span> <span data-ttu-id="e7066-118">Jede Tabelle wird in einer neuen Excel-Instanz geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e7066-118">Each spreadsheet is opened in a new instance of Excel.</span></span>
<span data-ttu-id="e7066-119">In diesem Fall ist das Öffnen in Excel die Standardaktion für `.xls` Dateien.</span><span class="sxs-lookup"><span data-stu-id="e7066-119">In this case, opening in Excel is the default action for `.xls` files.</span></span>

```powershell
Invoke-Item "C:\Documents and Settings\Lister\My Documents\*.xls"
```

## <span data-ttu-id="e7066-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e7066-120">PARAMETERS</span></span>

### <span data-ttu-id="e7066-121">-Credential</span><span class="sxs-lookup"><span data-stu-id="e7066-121">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="e7066-122">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e7066-122">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="e7066-123">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="e7066-123">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="e7066-124">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="e7066-124">-Exclude</span></span>

<span data-ttu-id="e7066-125">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="e7066-125">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="e7066-126">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="e7066-126">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="e7066-127">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="e7066-127">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="e7066-128">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="e7066-128">Wildcard characters are permitted.</span></span> <span data-ttu-id="e7066-129">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="e7066-129">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="e7066-130">-Filter</span><span class="sxs-lookup"><span data-stu-id="e7066-130">-Filter</span></span>

<span data-ttu-id="e7066-131">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="e7066-131">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="e7066-132">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e7066-132">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="e7066-133">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="e7066-133">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="e7066-134">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="e7066-134">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="e7066-135">-Include</span><span class="sxs-lookup"><span data-stu-id="e7066-135">-Include</span></span>

<span data-ttu-id="e7066-136">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="e7066-136">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="e7066-137">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="e7066-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="e7066-138">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="e7066-138">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="e7066-139">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="e7066-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="e7066-140">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="e7066-140">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="e7066-141">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="e7066-141">-LiteralPath</span></span>

<span data-ttu-id="e7066-142">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="e7066-142">Specifies a path to one or more locations.</span></span> <span data-ttu-id="e7066-143">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="e7066-143">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="e7066-144">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="e7066-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="e7066-145">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="e7066-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="e7066-146">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="e7066-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="e7066-147">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="e7066-147">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="e7066-148">-Path</span><span class="sxs-lookup"><span data-stu-id="e7066-148">-Path</span></span>

<span data-ttu-id="e7066-149">Gibt den Pfad zum ausgewählten Element an.</span><span class="sxs-lookup"><span data-stu-id="e7066-149">Specifies the path to the selected item.</span></span>
<span data-ttu-id="e7066-150">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="e7066-150">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e7066-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e7066-151">-Confirm</span></span>

<span data-ttu-id="e7066-152">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="e7066-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e7066-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e7066-153">-WhatIf</span></span>

<span data-ttu-id="e7066-154">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7066-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e7066-155">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e7066-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e7066-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e7066-156">CommonParameters</span></span>

<span data-ttu-id="e7066-157">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="e7066-157">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="e7066-158">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e7066-158">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e7066-159">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e7066-159">INPUTS</span></span>

### <span data-ttu-id="e7066-160">System.String</span><span class="sxs-lookup"><span data-stu-id="e7066-160">System.String</span></span>

<span data-ttu-id="e7066-161">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="e7066-161">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="e7066-162">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e7066-162">OUTPUTS</span></span>

### <span data-ttu-id="e7066-163">Keine</span><span class="sxs-lookup"><span data-stu-id="e7066-163">None</span></span>

<span data-ttu-id="e7066-164">Der Befehl generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e7066-164">The command does not generate any output.</span></span>
<span data-ttu-id="e7066-165">Das Element, das vom Befehl aufgerufen wird, kann jedoch eine Ausgabe generieren.</span><span class="sxs-lookup"><span data-stu-id="e7066-165">However, output might be generated by the item that it invokes.</span></span>

## <span data-ttu-id="e7066-166">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e7066-166">NOTES</span></span>

<span data-ttu-id="e7066-167">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="e7066-167">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="e7066-168">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="e7066-168">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="e7066-169">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="e7066-169">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="e7066-170">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e7066-170">RELATED LINKS</span></span>

[<span data-ttu-id="e7066-171">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="e7066-171">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="e7066-172">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="e7066-172">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="e7066-173">Get-Item</span><span class="sxs-lookup"><span data-stu-id="e7066-173">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="e7066-174">Move-Item</span><span class="sxs-lookup"><span data-stu-id="e7066-174">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="e7066-175">New-Item</span><span class="sxs-lookup"><span data-stu-id="e7066-175">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="e7066-176">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="e7066-176">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="e7066-177">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="e7066-177">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="e7066-178">Set-Item</span><span class="sxs-lookup"><span data-stu-id="e7066-178">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="e7066-179">about_Providers</span><span class="sxs-lookup"><span data-stu-id="e7066-179">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

