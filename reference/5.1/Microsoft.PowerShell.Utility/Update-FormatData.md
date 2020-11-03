---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-formatdata?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-FormatData
ms.openlocfilehash: 41a49ccd185cdc1ebf5c6f748833ee3f4218784b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213628"
---
# <span data-ttu-id="cce68-103">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="cce68-103">Update-FormatData</span></span>

## <span data-ttu-id="cce68-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="cce68-104">SYNOPSIS</span></span>
<span data-ttu-id="cce68-105">Aktualisiert die Formatierungsdaten in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="cce68-105">Updates the formatting data in the current session.</span></span>

## <span data-ttu-id="cce68-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cce68-106">SYNTAX</span></span>

```
Update-FormatData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="cce68-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cce68-107">DESCRIPTION</span></span>

<span data-ttu-id="cce68-108">Mit dem- `Update-FormatData` Cmdlet werden die Formatierungsdaten aus Formatierungs Dateien erneut in die aktuelle Sitzung geladen.</span><span class="sxs-lookup"><span data-stu-id="cce68-108">The `Update-FormatData` cmdlet reloads the formatting data from formatting files into the current session.</span></span> <span data-ttu-id="cce68-109">Mit diesem Cmdlet können Sie die Formatierungsdaten aktualisieren, ohne PowerShell neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="cce68-109">This cmdlet lets you update the formatting data without restarting PowerShell.</span></span>

<span data-ttu-id="cce68-110">Ohne Parameter `Update-FormatData` lädt die Formatierungs Dateien, die zuvor geladen wurden, erneut.</span><span class="sxs-lookup"><span data-stu-id="cce68-110">Without parameters, `Update-FormatData` reloads the formatting files that it loaded previously.</span></span>
<span data-ttu-id="cce68-111">Mit den Parametern von können Sie `Update-FormatData` der Sitzung neue Formatierungs Dateien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cce68-111">You can use the parameters of `Update-FormatData` to add new formatting files to the session.</span></span>

<span data-ttu-id="cce68-112">Formatieren von Dateien sind Textdateien im XML-Format mit der `format.ps1xml` Dateinamenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="cce68-112">Formatting files are text files in XML format with the `format.ps1xml` file name extension.</span></span> <span data-ttu-id="cce68-113">Die Formatierungsdaten in den Dateien definieren die Anzeige von Microsoft .NET Framework-Objekten in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="cce68-113">The formatting data in the files defines the display of Microsoft .NET Framework objects in the session.</span></span>

<span data-ttu-id="cce68-114">Beim Starten von Windows PowerShell werden die Format Daten aus den Formatierungs Dateien im PowerShell-Installationsverzeichnis ( `$pshome` ) in die Sitzung geladen.</span><span class="sxs-lookup"><span data-stu-id="cce68-114">When Windows PowerShell starts, it loads the format data from the formatting files in the PowerShell installation directory (`$pshome`) into the session.</span></span> <span data-ttu-id="cce68-115">Sie können verwenden `Update-FormatData` , um die Formatierungsdaten in der aktuellen Sitzung neu zu laden, ohne PowerShell neu starten zu müssen.</span><span class="sxs-lookup"><span data-stu-id="cce68-115">You can use `Update-FormatData` to reload the formatting data into the current session without restarting PowerShell.</span></span> <span data-ttu-id="cce68-116">Dies ist nützlich, wenn Sie eine Formatierungsdatei hinzugefügt oder geändert haben, die Sitzung aber nicht unterbrechen möchten.</span><span class="sxs-lookup"><span data-stu-id="cce68-116">This is useful when you have added or changed a formatting file, but do not want to interrupt the session.</span></span>

<span data-ttu-id="cce68-117">Weitere Informationen zum Formatieren von Dateien in PowerShell finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="cce68-117">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="cce68-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="cce68-118">EXAMPLES</span></span>

### <span data-ttu-id="cce68-119">Beispiel 1: Erneutes Laden zuvor geladener Formatierungs Dateien</span><span class="sxs-lookup"><span data-stu-id="cce68-119">Example 1: Reload previously loaded formatting files</span></span>

```powershell
Update-FormatData
```

<span data-ttu-id="cce68-120">Mit diesem Befehl werden die zuvor geladenen Formatierungsdateien erneut geladen.</span><span class="sxs-lookup"><span data-stu-id="cce68-120">This command reloads the formatting files that it loaded previously.</span></span>

### <span data-ttu-id="cce68-121">Beispiel 2: Erneutes Laden von Formatierungs Dateien und Dateien zur Ablauf Verfolgung und Protokoll Formatierung</span><span class="sxs-lookup"><span data-stu-id="cce68-121">Example 2: Reload formatting files and trace and log formatting files</span></span>

```powershell
Update-FormatData -AppendPath "trace.format.ps1xml, log.format.ps1xml"
```

<span data-ttu-id="cce68-122">Mit diesem Befehl werden die Formatierungsdateien erneut in die Sitzung geladen, einschließlich der zwei neuen Dateien „Trace.format.ps1xml“ und „Log.format.ps1xml“.</span><span class="sxs-lookup"><span data-stu-id="cce68-122">This command reloads the formatting files into the session, including two new files, Trace.format.ps1xml and Log.format.ps1xml.</span></span>

<span data-ttu-id="cce68-123">Da der Befehl den **appendpath** -Parameter verwendet, werden die Formatierungsdaten in den neuen Dateien nach den Formatierungsdaten aus den integrierten Dateien geladen.</span><span class="sxs-lookup"><span data-stu-id="cce68-123">Because the command uses the **AppendPath** parameter, the formatting data in the new files is loaded after the formatting data from the built-in files.</span></span>

<span data-ttu-id="cce68-124">Der **appendpath** -Parameter wird verwendet, da die neuen Dateien Formatierungsdaten für Objekte enthalten, auf die in den integrierten Dateien nicht verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cce68-124">The **AppendPath** parameter is used because the new files contain formatting data for objects that are not referenced in the built-in files.</span></span>

### <span data-ttu-id="cce68-125">Beispiel 3: Bearbeiten einer Formatierungs Datei und erneutes Laden</span><span class="sxs-lookup"><span data-stu-id="cce68-125">Example 3: Edit a formatting file and reload it</span></span>

```powershell
Update-FormatData -PrependPath "c:\test\NewFiles.format.ps1xml"

# Edit the NewFiles.format.ps1 file.

Update-FormatData
```

<span data-ttu-id="cce68-126">In diesem Beispiel wird veranschaulicht, wie eine Formatierungsdatei nach dem Bearbeiten erneut geladen wird.</span><span class="sxs-lookup"><span data-stu-id="cce68-126">This example shows how to reload a formatting file after you have edited it.</span></span>

<span data-ttu-id="cce68-127">Mit dem ersten Befehl wird die Datei „NewFiles.format.ps1xml“ zur Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cce68-127">The first command adds the NewFiles.format.ps1xml file to the session.</span></span> <span data-ttu-id="cce68-128">Dabei wird der **prepdpath** -Parameter verwendet, da die Datei Formatierungsdaten für Objekte enthält, auf die in den integrierten Dateien verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cce68-128">It uses the **PrependPath** parameter because the file contains formatting data for objects that are referenced in the built-in files.</span></span>

<span data-ttu-id="cce68-129">Nachdem Sie die NewFiles.format.ps1XML-Datei hinzugefügt und in diesen Sitzungen getestet haben, bearbeitet der Autor die Datei.</span><span class="sxs-lookup"><span data-stu-id="cce68-129">After adding the NewFiles.format.ps1xml file and testing it in these sessions, the author edits the file.</span></span>

<span data-ttu-id="cce68-130">Der zweite Befehl verwendet das `Update-FormatData` Cmdlet, um die Formatierungs Dateien erneut zu laden.</span><span class="sxs-lookup"><span data-stu-id="cce68-130">The second command uses the `Update-FormatData` cmdlet to reload the formatting files.</span></span> <span data-ttu-id="cce68-131">Da die NewFiles.format.ps1-XML-Datei zuvor bereits geladen wurde, wird `Update-FormatData` Sie von automatisch erneut geladen, ohne Parameter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cce68-131">Because the NewFiles.format.ps1xml file was previously loaded, `Update-FormatData` automatically reloads it without using parameters.</span></span>

## <span data-ttu-id="cce68-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cce68-132">PARAMETERS</span></span>

### <span data-ttu-id="cce68-133">-Appendpath</span><span class="sxs-lookup"><span data-stu-id="cce68-133">-AppendPath</span></span>

<span data-ttu-id="cce68-134">Gibt Formatierungs Dateien an, die von diesem Cmdlet der Sitzung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cce68-134">Specifies formatting files that this cmdlet adds to the session.</span></span> <span data-ttu-id="cce68-135">Die Dateien werden geladen, nachdem PowerShell die integrierten Formatierungs Dateien geladen hat.</span><span class="sxs-lookup"><span data-stu-id="cce68-135">The files are loaded after PowerShell loads the built-in formatting files.</span></span>

<span data-ttu-id="cce68-136">Beim Formatieren von .NET-Objekten verwendet Windows PowerShell die erste Formatierungs Definition, die für jeden .NET-Typ gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="cce68-136">When formatting .NET objects,Windows PowerShell uses the first formatting definition that it finds for each .NET type.</span></span> <span data-ttu-id="cce68-137">Wenn Sie den **appendpath** -Parameter verwenden, durchsucht Windows PowerShell die Daten aus den integrierten Dateien, bevor die Formatierungsdaten gefunden werden, die Sie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cce68-137">If you use the **AppendPath** parameter, Windows PowerShell searches the data from the built-in files before it encounters the formatting data that you are adding.</span></span>

<span data-ttu-id="cce68-138">Verwenden Sie diesen Parameter zum Hinzufügen einer Datei, die ein .NET-Objekt formatiert, auf das nicht in den integrierten Formatierungsdateien verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cce68-138">Use this parameter to add a file that formats a .NET object that is not referenced in the built-in formatting files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath, Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="cce68-139">-Prepdpath</span><span class="sxs-lookup"><span data-stu-id="cce68-139">-PrependPath</span></span>

<span data-ttu-id="cce68-140">Gibt Formatierungs Dateien an, die von diesem Cmdlet der Sitzung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cce68-140">Specifies formatting files that this cmdlet adds to the session.</span></span> <span data-ttu-id="cce68-141">Die Dateien werden geladen, bevor PowerShell die integrierten Formatierungs Dateien lädt.</span><span class="sxs-lookup"><span data-stu-id="cce68-141">The files are loaded before PowerShell loads the built-in formatting files.</span></span>

<span data-ttu-id="cce68-142">Beim Formatieren von .NET-Objekten verwendet Windows PowerShell die erste Formatierungsdefinition, die für die einzelnen .NET-Typen gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="cce68-142">When formatting .NET objects, Windows PowerShell uses the first formatting definition that it finds for each .NET type.</span></span> <span data-ttu-id="cce68-143">Wenn Sie den **prepdpath** -Parameter verwenden, durchsucht Windows PowerShell die Daten aus den Dateien, die Sie hinzufügen, bevor die Formatierungsdaten aus den integrierten Dateien gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="cce68-143">If you use the **PrependPath** parameter, Windows PowerShell searches the data from the files that you are adding before it encounters the formatting data from the built-in files.</span></span>

<span data-ttu-id="cce68-144">Verwenden Sie diesen Parameter zum Hinzufügen einer Datei, die ein .NET-Objekt formatiert, auf das auch in den integrierten Formatierungsdateien verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cce68-144">Use this parameter to add a file that formats a .NET object that is also referenced in the built-in formatting files.</span></span>

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

### <span data-ttu-id="cce68-145">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cce68-145">-Confirm</span></span>

<span data-ttu-id="cce68-146">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="cce68-146">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="cce68-147">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cce68-147">-WhatIf</span></span>

<span data-ttu-id="cce68-148">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cce68-148">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="cce68-149">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cce68-149">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="cce68-150">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cce68-150">CommonParameters</span></span>

<span data-ttu-id="cce68-151">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cce68-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cce68-152">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cce68-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cce68-153">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="cce68-153">INPUTS</span></span>

### <span data-ttu-id="cce68-154">System.String</span><span class="sxs-lookup"><span data-stu-id="cce68-154">System.String</span></span>

<span data-ttu-id="cce68-155">Sie können eine Zeichenfolge, die den Anfüge Pfad enthält, über die Pipeline an übergeben `Update-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="cce68-155">You can pipe a string that contains the append path to `Update-FormatData`.</span></span>

## <span data-ttu-id="cce68-156">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="cce68-156">OUTPUTS</span></span>

### <span data-ttu-id="cce68-157">Keine</span><span class="sxs-lookup"><span data-stu-id="cce68-157">None</span></span>

<span data-ttu-id="cce68-158">Das Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="cce68-158">The cmdlet does not return any output.</span></span>

## <span data-ttu-id="cce68-159">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="cce68-159">NOTES</span></span>

- <span data-ttu-id="cce68-160">`Update-FormatData` aktualisiert auch die Formatierungsdaten für Befehle in der Sitzung, die aus Modulen importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="cce68-160">`Update-FormatData` also updates the formatting data for commands in the session that were imported from modules.</span></span> <span data-ttu-id="cce68-161">Wenn die Formatierungs Datei für ein Modul geändert wird, können Sie einen Befehl ausführen, `Update-FormatData` um die Formatierungsdaten für importierte Befehle zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="cce68-161">If the formatting file for a module changes, you can run an `Update-FormatData` command to update the formatting data for imported commands.</span></span> <span data-ttu-id="cce68-162">Sie müssen das Modul nicht erneut importieren.</span><span class="sxs-lookup"><span data-stu-id="cce68-162">You do not need to import the module again.</span></span>

## <span data-ttu-id="cce68-163">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="cce68-163">RELATED LINKS</span></span>

[<span data-ttu-id="cce68-164">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="cce68-164">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="cce68-165">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="cce68-165">Export-FormatData</span></span>](Export-FormatData.md)
