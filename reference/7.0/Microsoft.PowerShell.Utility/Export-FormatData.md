---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-formatdata?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-FormatData
ms.openlocfilehash: d89d80b296d8800d65c5acfae37434e9b3f3bce9
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211044"
---
# <span data-ttu-id="0bf7f-103">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="0bf7f-103">Export-FormatData</span></span>

## <span data-ttu-id="0bf7f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0bf7f-104">SYNOPSIS</span></span>
<span data-ttu-id="0bf7f-105">Speichert Formatierungsdaten aus der aktuellen Sitzung in einer Formatierungsdatei.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-105">Saves formatting data from the current session in a formatting file.</span></span>

## <span data-ttu-id="0bf7f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0bf7f-106">SYNTAX</span></span>

### <span data-ttu-id="0bf7f-107">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="0bf7f-107">ByPath (Default)</span></span>

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -Path <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

### <span data-ttu-id="0bf7f-108">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="0bf7f-108">ByLiteralPath</span></span>

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -LiteralPath <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

## <span data-ttu-id="0bf7f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0bf7f-109">DESCRIPTION</span></span>

<span data-ttu-id="0bf7f-110">Mit dem- `Export-FormatData` Cmdlet werden PowerShell-Formatierungs Dateien (format.ps1XML) aus den Formatierungs Objekten in der aktuellen Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-110">The `Export-FormatData` cmdlet creates PowerShell formatting files (format.ps1xml) from the formatting objects in the current session.</span></span> <span data-ttu-id="0bf7f-111">Sie übernimmt die **extendedtypedefinition** -Objekte, die `Get-FormatData` zurückgibt, und speichert Sie in einer Datei im XML-Format.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-111">It takes the **ExtendedTypeDefinition** objects that `Get-FormatData` returns and saves them in a file in XML format.</span></span>

<span data-ttu-id="0bf7f-112">PowerShell verwendet die Daten in Formatierungs Dateien (format.ps1XML), um die Standard Anzeige von Microsoft .NET Framework-Objekten in der Sitzung zu generieren.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-112">PowerShell uses the data in formatting files (format.ps1xml) to generate the default display of Microsoft .NET Framework objects in the session.</span></span> <span data-ttu-id="0bf7f-113">Sie können die Formatierungsdateien anzeigen und bearbeiten und mit dem Update-FormatData-Cmdlet Formatierungsdaten zu einer Sitzung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-113">You can view and edit the formatting files and use the Update-FormatData cmdlet to add the formatting data to a session.</span></span>

<span data-ttu-id="0bf7f-114">Weitere Informationen zum Formatieren von Dateien in PowerShell finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="0bf7f-114">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="0bf7f-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0bf7f-115">EXAMPLES</span></span>

### <span data-ttu-id="0bf7f-116">Beispiel 1: Exportieren von Sitzungs Formatierungsdaten</span><span class="sxs-lookup"><span data-stu-id="0bf7f-116">Example 1: Export session format data</span></span>

```powershell
Get-FormatData -TypeName "*" -PowerShellVersion 5.1 | Export-FormatData -Path "allformat.ps1xml" -IncludeScriptBlock
```

<span data-ttu-id="0bf7f-117">Mit diesem Befehl werden alle Formatdaten in der Sitzung in die Datei AllFormat.ps1xml exportiert.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-117">This command exports all of the format data in the session to the AllFormat.ps1xml file.</span></span>

<span data-ttu-id="0bf7f-118">Der Befehl verwendet das `Get-FormatData` Cmdlet, um die Format Daten in der Sitzung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-118">The command uses the `Get-FormatData` cmdlet to get the format data in the session.</span></span> <span data-ttu-id="0bf7f-119">`*`Der Wert (alle) für den **tykame** -Parameter weist das Cmdlet an, alle Daten in der Sitzung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-119">A value of `*` (all) for the **TypeName** parameter directs the cmdlet to get all of the data in the session.</span></span>

<span data-ttu-id="0bf7f-120">Der Befehl verwendet einen Pipeline Operator ( `|` ), um die Format Daten vom `Get-FormatData` Befehl an das `Export-FormatData` Cmdlet zu senden, das die Format Daten in die AllFormat.ps1 Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-120">The command uses a pipeline operator (`|`) to send the format data from the `Get-FormatData` command to the `Export-FormatData` cmdlet, which exports the format data to the AllFormat.ps1 file.</span></span>

<span data-ttu-id="0bf7f-121">Der `Export-FormatData` Befehl verwendet den **includescriptblock** -Parameter, um Skriptblöcke in die Format Daten in der Datei einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-121">The `Export-FormatData` command uses the **IncludeScriptBlock** parameter to include script blocks in the format data in the file.</span></span>

### <span data-ttu-id="0bf7f-122">Beispiel 2: Exportieren von Format Daten für einen Typ</span><span class="sxs-lookup"><span data-stu-id="0bf7f-122">Example 2: Export format data for a type</span></span>

```powershell
$F = Get-FormatData -TypeName "helpinfoshort" -PowerShellVersion 5.1
Export-FormatData -InputObject $F -Path "c:\test\help.format.ps1xml" -IncludeScriptBlock
```

<span data-ttu-id="0bf7f-123">Diese Befehle exportieren die Format Daten für den **helpinfoshort** -Typ in die Help.format.ps1-XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-123">These commands export the format data for the **HelpInfoShort** type to the Help.format.ps1xml file.</span></span>

<span data-ttu-id="0bf7f-124">Der erste Befehl verwendet das `Get-FormatData` Cmdlet, um die Format Daten für den **helpinfoshort** -Typ zu erhalten, und speichert Sie in der `$F` Variablen.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-124">The first command uses the `Get-FormatData` cmdlet to get the format data for the **HelpInfoShort** type, and it saves it in the `$F` variable.</span></span>

<span data-ttu-id="0bf7f-125">Der zweite Befehl verwendet den **Inputobject** -Parameter des `Export-FormatData` Cmdlets, um die in der Variablen gespeicherten Format Daten einzugeben `$F` .</span><span class="sxs-lookup"><span data-stu-id="0bf7f-125">The second command uses the **InputObject** parameter of the `Export-FormatData` cmdlet to enter the format data saved in the `$F` variable.</span></span> <span data-ttu-id="0bf7f-126">Er verwendet auch den **includescriptblock** -Parameter, um Skriptblöcke in der Ausgabe einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-126">It also uses the **IncludeScriptBlock** parameter to include script blocks in the output.</span></span>

### <span data-ttu-id="0bf7f-127">Beispiel 3: Exportieren von Format Daten ohne Skriptblock</span><span class="sxs-lookup"><span data-stu-id="0bf7f-127">Example 3: Export format data without a script block</span></span>

```powershell
Get-FormatData -TypeName "System.Diagnostics.Process" -PowerShellVersion 5.1 | Export-FormatData -Path process.format.ps1xml
Update-FormatData -PrependPath ".\process.format.ps1xml"
Get-Process p*
```

```Output
Handles  NPM(K)  PM(K)  WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------  -----  ----- -----   ------    -- -----------
323                                       5600 powershell
336                                       3900 powershell_ise
138                                       4076 PresentationFontCache
```

<span data-ttu-id="0bf7f-128">In diesem Beispiel wird gezeigt, wie sich der **includescriptblock** -Parameter in einem Befehl auslässt `Export-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="0bf7f-128">This example shows the effect of omitting the **IncludeScriptBlock** parameter from an `Export-FormatData` command.</span></span>

<span data-ttu-id="0bf7f-129">Der erste Befehl verwendet das `Get-FormatData` Cmdlet, um die Format Daten für das **System. Diagnostics. Process** -Objekt zu erhalten, das vom Cmdlet "Get-Process" zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-129">The first command uses the `Get-FormatData` cmdlet to get the format data for the **System.Diagnostics.Process** object that the Get-Process cmdlet returns.</span></span> <span data-ttu-id="0bf7f-130">Der Befehl verwendet einen Pipeline Operator ( `|` ), um die Formatierungsdaten an das `Export-FormatData` Cmdlet zu senden, das Sie in die Process.format.ps1XML-Datei im aktuellen Verzeichnis exportiert.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-130">The command uses a pipeline operator (`|`) to send the formatting data to the `Export-FormatData` cmdlet, which exports it to the Process.format.ps1xml file in the current directory.</span></span>

<span data-ttu-id="0bf7f-131">In diesem Fall verwendet der `Export-FormatData` Befehl nicht den **includescriptblock** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-131">In this case, the `Export-FormatData` command does not use the **IncludeScriptBlock** parameter.</span></span>

<span data-ttu-id="0bf7f-132">Der zweite Befehl verwendet das `Update-FormatData` Cmdlet, um der aktuellen Sitzung die Process.format.ps1XML-Datei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-132">The second command uses the `Update-FormatData` cmdlet to add the Process.format.ps1xml file to the current session.</span></span> <span data-ttu-id="0bf7f-133">Der Befehl verwendet den **prepdpath** -Parameter, um sicherzustellen, dass die Formatierungsdaten für Prozess Objekte in der Process.format.ps1-XML-Datei vor den Standard Formatierungsdaten für Prozess Objekte gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-133">The command uses the **PrependPath** parameter to ensure that the formatting data for process objects in the Process.format.ps1xml file is found before the standard formatting data for process objects.</span></span>

<span data-ttu-id="0bf7f-134">Der dritte Befehl zeigt die Auswirkungen dieser Änderung.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-134">The third command shows the effects of this change.</span></span> <span data-ttu-id="0bf7f-135">Der Befehl verwendet das `Get-Process` Cmdlet zum Ausführen von Prozessen, deren Namen mit "P" beginnen. Die Ausgabe zeigt, dass Eigenschaftswerte, die mithilfe von Skript Blöcken berechnet werden, in der Anzeige fehlen.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-135">The command uses the `Get-Process` cmdlet to get processes that have names that begin with P. The output shows that property values that are calculated by using script blocks are missing from the display.</span></span>

## <span data-ttu-id="0bf7f-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0bf7f-136">PARAMETERS</span></span>

### <span data-ttu-id="0bf7f-137">-Force</span><span class="sxs-lookup"><span data-stu-id="0bf7f-137">-Force</span></span>

<span data-ttu-id="0bf7f-138">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-138">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="0bf7f-139">-Includescriptblock</span><span class="sxs-lookup"><span data-stu-id="0bf7f-139">-IncludeScriptBlock</span></span>

<span data-ttu-id="0bf7f-140">Gibt an, ob Skriptblöcke in den Format Daten exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-140">Indicates whether script blocks in the format data are exported.</span></span>

<span data-ttu-id="0bf7f-141">Da Skriptblöcke Code enthalten und böswillig verwendet werden können, werden sie standardmäßig nicht exportiert.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-141">Because script blocks contain code and can be used maliciously, they are not exported by default.</span></span>

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

### <span data-ttu-id="0bf7f-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0bf7f-142">-InputObject</span></span>

<span data-ttu-id="0bf7f-143">Gibt die Formatdatenobjekte an, die exportiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-143">Specifies the format data objects to be exported.</span></span> <span data-ttu-id="0bf7f-144">Geben Sie eine Variable ein, die die Objekte enthält, oder einen Befehl, der die Objekte abruft, z `Get-FormatData` . b. einen Befehl.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-144">Enter a variable that contains the objects or a command that gets the objects, such as a `Get-FormatData` command.</span></span> <span data-ttu-id="0bf7f-145">Sie können die Objekte auch über die Pipeline `Get-FormatData` an senden `Export-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="0bf7f-145">You can also pipe the objects from `Get-FormatData` to `Export-FormatData`.</span></span>

```yaml
Type: System.Management.Automation.ExtendedTypeDefinition[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0bf7f-146">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="0bf7f-146">-LiteralPath</span></span>

<span data-ttu-id="0bf7f-147">Gibt einen Speicherort für die Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-147">Specifies a location for the output file.</span></span> <span data-ttu-id="0bf7f-148">Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-148">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="0bf7f-149">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-149">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0bf7f-150">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-150">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="0bf7f-151">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-151">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bf7f-152">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="0bf7f-152">-NoClobber</span></span>

<span data-ttu-id="0bf7f-153">Gibt an, dass das Cmdlet vorhandene Dateien nicht überschreibt.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-153">Indicates that the cmdlet does not overwrite existing files.</span></span> <span data-ttu-id="0bf7f-154">Standardmäßig werden `Export-FormatData` Dateien ohne Warnung überschrieben, es sei denn, die Datei verfügt über das Read-only-Attribut.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-154">By default, `Export-FormatData` overwrites files without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="0bf7f-155">`Export-FormatData`Verwenden Sie den **Force** -Parameter, um zu steuern, dass schreibgeschützte Dateien überschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-155">To direct `Export-FormatData` to overwrite read-only files, use the **Force** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bf7f-156">-Path</span><span class="sxs-lookup"><span data-stu-id="0bf7f-156">-Path</span></span>

<span data-ttu-id="0bf7f-157">Gibt einen Speicherort für die Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-157">Specifies a location for the output file.</span></span>
<span data-ttu-id="0bf7f-158">Geben Sie einen Pfad (optional) und Dateinamen mit der Dateinamenerweiterung format.ps1xml ein.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-158">Enter a path (optional) and file name with a format.ps1xml file name extension.</span></span>
<span data-ttu-id="0bf7f-159">Wenn Sie den Pfad weglassen, `Export-FormatData` erstellt die Datei im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-159">If you omit the path, `Export-FormatData` creates the file in the current directory.</span></span>

<span data-ttu-id="0bf7f-160">Wenn Sie eine andere Dateinamenerweiterung als. ps1xml verwenden, `Update-FormatData` wird die Datei vom Cmdlet nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-160">If you use a file name extension other than .ps1xml, the `Update-FormatData` cmdlet will not recognize the file.</span></span>

<span data-ttu-id="0bf7f-161">Wenn Sie eine vorhandene Datei angeben, wird `Export-FormatData` die Datei ohne Warnung überschrieben, es sei denn, die Datei verfügt über das Read-only-Attribut.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-161">If you specify an existing file, `Export-FormatData` overwrites the file without warning, unless the file has the read-only attribute.</span></span> <span data-ttu-id="0bf7f-162">Verwenden Sie den **Force** -Parameter, um eine schreibgeschützte Datei zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-162">To overwrite a read-only file, use the **Force** parameter.</span></span> <span data-ttu-id="0bf7f-163">Verwenden Sie den **noClobber** -Parameter, um zu verhindern, dass Dateien überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-163">To prevent files from being overwritten, use the **NoClobber** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: FilePath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bf7f-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0bf7f-164">CommonParameters</span></span>

<span data-ttu-id="0bf7f-165">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0bf7f-166">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0bf7f-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0bf7f-167">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0bf7f-167">INPUTS</span></span>

### <span data-ttu-id="0bf7f-168">System. Management. Automation. extendedtypedefinition</span><span class="sxs-lookup"><span data-stu-id="0bf7f-168">System.Management.Automation.ExtendedTypeDefinition</span></span>

<span data-ttu-id="0bf7f-169">Sie können **extendedtypedefinition** -Objekte von `Get-FormatData` an über die Pipeline übergeben `Export-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="0bf7f-169">You can pipe **ExtendedTypeDefinition** objects from `Get-FormatData` to `Export-FormatData`.</span></span>

## <span data-ttu-id="0bf7f-170">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0bf7f-170">OUTPUTS</span></span>

### <span data-ttu-id="0bf7f-171">Keine</span><span class="sxs-lookup"><span data-stu-id="0bf7f-171">None</span></span>

<span data-ttu-id="0bf7f-172">`Export-FormatData` gibt keine-Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-172">`Export-FormatData` does not return any objects.</span></span>
<span data-ttu-id="0bf7f-173">Es generiert eine Datei und speichert sie im angegebenen Pfad.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-173">It generates a file and saves it in the specified path.</span></span>

## <span data-ttu-id="0bf7f-174">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0bf7f-174">NOTES</span></span>

- <span data-ttu-id="0bf7f-175">Um eine beliebige Formatierungsdatei zu verwenden, einschließlich einer exportierten Formatierungsdatei, muss die Ausführungsrichtlinie für die Sitzung die Ausführung von Skripten und Konfigurationsdateien zulassen.</span><span class="sxs-lookup"><span data-stu-id="0bf7f-175">To use any formatting file, including an exported formatting file, the execution policy for the session must allow scripts and configuration files to run.</span></span> <span data-ttu-id="0bf7f-176">Weitere Informationen finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="0bf7f-176">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="0bf7f-177">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0bf7f-177">RELATED LINKS</span></span>

[<span data-ttu-id="0bf7f-178">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="0bf7f-178">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="0bf7f-179">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="0bf7f-179">Update-FormatData</span></span>](Update-FormatData.md)
