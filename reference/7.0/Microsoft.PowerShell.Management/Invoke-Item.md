---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Item
ms.openlocfilehash: bbd3ca9a3a4df8930a75ecc395765e70fc7ccf7b
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209996"
---
# <span data-ttu-id="bcb52-103">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="bcb52-103">Invoke-Item</span></span>

## <span data-ttu-id="bcb52-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bcb52-104">SYNOPSIS</span></span>
<span data-ttu-id="bcb52-105">Führt die Standardaktion für das angegebene Element aus.</span><span class="sxs-lookup"><span data-stu-id="bcb52-105">Performs the default action on the specified item.</span></span>

## <span data-ttu-id="bcb52-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bcb52-106">SYNTAX</span></span>

### <span data-ttu-id="bcb52-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="bcb52-107">Path (Default)</span></span>

```
Invoke-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bcb52-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="bcb52-108">LiteralPath</span></span>

```
Invoke-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bcb52-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bcb52-109">DESCRIPTION</span></span>

<span data-ttu-id="bcb52-110">Das- `Invoke-Item` Cmdlet führt die Standardaktion für das angegebene Element aus.</span><span class="sxs-lookup"><span data-stu-id="bcb52-110">The `Invoke-Item` cmdlet performs the default action on the specified item.</span></span>
<span data-ttu-id="bcb52-111">Beispielsweise wird eine ausführbare Datei ausgeführt oder eine Dokumentdatei in der Anwendung geöffnet, die dem Dokumentdateityp zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="bcb52-111">For example, it runs an executable file or opens a document file in the application associated with the document file type.</span></span>
<span data-ttu-id="bcb52-112">Die Standardaktion hängt vom Typ des Elements ab und wird vom PowerShell-Anbieter bestimmt, der den Zugriff auf die Daten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="bcb52-112">The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.</span></span>

## <span data-ttu-id="bcb52-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bcb52-113">EXAMPLES</span></span>

### <span data-ttu-id="bcb52-114">Beispiel 1: Öffnen einer Datei</span><span class="sxs-lookup"><span data-stu-id="bcb52-114">Example 1: Open a file</span></span>

<span data-ttu-id="bcb52-115">Mit diesem Befehl wird die Datei "aliasApr04.doc" in Microsoft Office Word geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bcb52-115">This command opens the file "aliasApr04.doc" in Microsoft Office Word.</span></span>
<span data-ttu-id="bcb52-116">In diesem Fall ist das Öffnen in Word die Standardaktion für doc-Dateien.</span><span class="sxs-lookup"><span data-stu-id="bcb52-116">In this case, opening in Word is the default action for ".doc" files.</span></span>

```powershell
Invoke-Item "C:\Test\aliasApr04.doc"
```

### <span data-ttu-id="bcb52-117">Beispiel 2: Öffnen aller Dateien eines bestimmten Typs</span><span class="sxs-lookup"><span data-stu-id="bcb52-117">Example 2: Open all files of a specific type</span></span>

<span data-ttu-id="bcb52-118">Dieser Befehl öffnet alle Microsoft Office Excel-Arbeitsblätter im `C:\Documents and
Settings\Lister\My Documents` Ordner.</span><span class="sxs-lookup"><span data-stu-id="bcb52-118">This command opens all of the Microsoft Office Excel spreadsheets in the `C:\Documents and
Settings\Lister\My Documents` folder.</span></span> <span data-ttu-id="bcb52-119">Jede Tabelle wird in einer neuen Excel-Instanz geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bcb52-119">Each spreadsheet is opened in a new instance of Excel.</span></span>
<span data-ttu-id="bcb52-120">In diesem Fall ist das Öffnen in Excel die Standardaktion für `.xls` Dateien.</span><span class="sxs-lookup"><span data-stu-id="bcb52-120">In this case, opening in Excel is the default action for `.xls` files.</span></span>

```powershell
Invoke-Item "C:\Documents and Settings\Lister\My Documents\*.xls"
```

## <span data-ttu-id="bcb52-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bcb52-121">PARAMETERS</span></span>

### <span data-ttu-id="bcb52-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="bcb52-122">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="bcb52-123">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bcb52-123">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="bcb52-124">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="bcb52-124">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="bcb52-125">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="bcb52-125">-Exclude</span></span>

<span data-ttu-id="bcb52-126">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="bcb52-126">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="bcb52-127">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bcb52-127">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="bcb52-128">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="bcb52-128">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="bcb52-129">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="bcb52-129">Wildcard characters are permitted.</span></span> <span data-ttu-id="bcb52-130">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="bcb52-130">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="bcb52-131">-Filter</span><span class="sxs-lookup"><span data-stu-id="bcb52-131">-Filter</span></span>

<span data-ttu-id="bcb52-132">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="bcb52-132">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="bcb52-133">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bcb52-133">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="bcb52-134">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="bcb52-134">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="bcb52-135">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="bcb52-135">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="bcb52-136">-Include</span><span class="sxs-lookup"><span data-stu-id="bcb52-136">-Include</span></span>

<span data-ttu-id="bcb52-137">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="bcb52-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="bcb52-138">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bcb52-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="bcb52-139">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="bcb52-139">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="bcb52-140">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="bcb52-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="bcb52-141">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="bcb52-141">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="bcb52-142">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="bcb52-142">-LiteralPath</span></span>

<span data-ttu-id="bcb52-143">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="bcb52-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="bcb52-144">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="bcb52-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="bcb52-145">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="bcb52-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="bcb52-146">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="bcb52-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="bcb52-147">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="bcb52-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="bcb52-148">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="bcb52-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="bcb52-149">-Path</span><span class="sxs-lookup"><span data-stu-id="bcb52-149">-Path</span></span>

<span data-ttu-id="bcb52-150">Gibt den Pfad zum ausgewählten Element an.</span><span class="sxs-lookup"><span data-stu-id="bcb52-150">Specifies the path to the selected item.</span></span>
<span data-ttu-id="bcb52-151">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="bcb52-151">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="bcb52-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bcb52-152">-Confirm</span></span>

<span data-ttu-id="bcb52-153">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="bcb52-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bcb52-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bcb52-154">-WhatIf</span></span>

<span data-ttu-id="bcb52-155">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bcb52-155">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bcb52-156">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bcb52-156">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bcb52-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bcb52-157">CommonParameters</span></span>

<span data-ttu-id="bcb52-158">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="bcb52-158">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="bcb52-159">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="bcb52-159">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="bcb52-160">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bcb52-160">INPUTS</span></span>

### <span data-ttu-id="bcb52-161">System.String</span><span class="sxs-lookup"><span data-stu-id="bcb52-161">System.String</span></span>

<span data-ttu-id="bcb52-162">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="bcb52-162">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="bcb52-163">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bcb52-163">OUTPUTS</span></span>

### <span data-ttu-id="bcb52-164">Keine</span><span class="sxs-lookup"><span data-stu-id="bcb52-164">None</span></span>

<span data-ttu-id="bcb52-165">Der Befehl generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="bcb52-165">The command does not generate any output.</span></span>
<span data-ttu-id="bcb52-166">Das Element, das vom Befehl aufgerufen wird, kann jedoch eine Ausgabe generieren.</span><span class="sxs-lookup"><span data-stu-id="bcb52-166">However, output might be generated by the item that it invokes.</span></span>

## <span data-ttu-id="bcb52-167">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bcb52-167">NOTES</span></span>

<span data-ttu-id="bcb52-168">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="bcb52-168">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="bcb52-169">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="bcb52-169">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="bcb52-170">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="bcb52-170">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="bcb52-171">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bcb52-171">RELATED LINKS</span></span>

[<span data-ttu-id="bcb52-172">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="bcb52-172">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="bcb52-173">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="bcb52-173">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="bcb52-174">Get-Item</span><span class="sxs-lookup"><span data-stu-id="bcb52-174">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="bcb52-175">Move-Item</span><span class="sxs-lookup"><span data-stu-id="bcb52-175">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="bcb52-176">New-Item</span><span class="sxs-lookup"><span data-stu-id="bcb52-176">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="bcb52-177">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="bcb52-177">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="bcb52-178">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="bcb52-178">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="bcb52-179">Set-Item</span><span class="sxs-lookup"><span data-stu-id="bcb52-179">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="bcb52-180">about_Providers</span><span class="sxs-lookup"><span data-stu-id="bcb52-180">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
