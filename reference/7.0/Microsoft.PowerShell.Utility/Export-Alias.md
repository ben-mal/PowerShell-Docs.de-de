---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Alias
ms.openlocfilehash: 4ddc9af276f1d24cc687652d96ffba77897305f0
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210204"
---
# <span data-ttu-id="15848-103">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="15848-103">Export-Alias</span></span>

## <span data-ttu-id="15848-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="15848-104">SYNOPSIS</span></span>
<span data-ttu-id="15848-105">Exportiert Informationen zu aktuell definierten Aliasen in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="15848-105">Exports information about currently defined aliases to a file.</span></span>

## <span data-ttu-id="15848-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="15848-106">SYNTAX</span></span>

### <span data-ttu-id="15848-107">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="15848-107">ByPath (Default)</span></span>

```
Export-Alias [-Path] <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append] [-Force]
 [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="15848-108">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="15848-108">ByLiteralPath</span></span>

```
Export-Alias -LiteralPath <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append]
 [-Force] [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="15848-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="15848-109">DESCRIPTION</span></span>

<span data-ttu-id="15848-110">Das- `Export-Alias` Cmdlet exportiert die Aliase in der aktuellen Sitzung in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="15848-110">The `Export-Alias` cmdlet exports the aliases in the current session to a file.</span></span>
<span data-ttu-id="15848-111">Wenn die Ausgabedatei nicht vorhanden ist, wird sie vom Cmdlet erstellt.</span><span class="sxs-lookup"><span data-stu-id="15848-111">If the output file does not exist, the cmdlet will create it.</span></span>

<span data-ttu-id="15848-112">`Export-Alias` kann die Aliase in einem bestimmten Bereich oder in allen Bereichen exportieren, kann die Daten im CSV-Format oder als eine Reihe von Set-Alias Befehlen generieren, die Sie einer Sitzung oder einem PowerShell-Profil hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="15848-112">`Export-Alias` can export the aliases in a particular scope or all scopes, it can generate the data in CSV format or as a series of Set-Alias commands that you can add to a session or to a PowerShell profile.</span></span>

## <span data-ttu-id="15848-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="15848-113">EXAMPLES</span></span>

### <span data-ttu-id="15848-114">Beispiel 1: Exportieren eines Alias</span><span class="sxs-lookup"><span data-stu-id="15848-114">Example 1: Export an alias</span></span>

```powershell
Export-Alias -Path "alias.csv"
```

<span data-ttu-id="15848-115">Dieser Befehl exportiert die aktuellen Aliasinformationen in eine Datei namens „Alias.csv“ im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="15848-115">This command exports current alias information to a file named Alias.csv in the current directory.</span></span>

### <span data-ttu-id="15848-116">Beispiel 2: Exportieren eines Alias, es sei denn, die Export Datei ist bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="15848-116">Example 2: Export an alias unless the export file already exists</span></span>

```powershell
Export-Alias -Path "alias.csv" -NoClobber
```

<span data-ttu-id="15848-117">Dieser Befehl exportiert die Aliase der aktuellen Sitzung in eine Datei namens „Alias.csv“.</span><span class="sxs-lookup"><span data-stu-id="15848-117">This command exports the aliases in the current session to an Alias.csv file.</span></span>

<span data-ttu-id="15848-118">Da der **noClobber** -Parameter angegeben wird, schlägt der Befehl fehl, wenn bereits eine Alias.csv Datei im aktuellen Verzeichnis vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="15848-118">Because the **NoClobber** parameter is specified, the command will fail if an Alias.csv file already exists in the current directory.</span></span>

### <span data-ttu-id="15848-119">Beispiel 3: Anfügen von Aliasen an eine Datei</span><span class="sxs-lookup"><span data-stu-id="15848-119">Example 3: Append aliases to a file</span></span>

```powershell
Export-Alias -Path "alias.csv" -Append -Description "Appended Aliases" -Force
```

<span data-ttu-id="15848-120">Dieser Befehl fügt die Aliase der aktuellen Sitzung an eine Datei namens „Alias.csv“ an.</span><span class="sxs-lookup"><span data-stu-id="15848-120">This command appends the aliases in the current session to the Alias.csv file.</span></span>

<span data-ttu-id="15848-121">Der Befehl verwendet den **Description** -Parameter, um den Kommentaren am Anfang der Datei eine Beschreibung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="15848-121">The command uses the **Description** parameter to add a description to the comments at the top of the file.</span></span>

<span data-ttu-id="15848-122">Der Befehl verwendet außerdem den **Force** -Parameter, um vorhandene Alias.csv Dateien zu überschreiben, auch wenn Sie über das schreibgeschützte Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="15848-122">The command also uses the **Force** parameter to overwrite any existing Alias.csv files, even if they have the read-only attribute.</span></span>

### <span data-ttu-id="15848-123">Beispiel 4: Exportieren von Aliasen als Skript</span><span class="sxs-lookup"><span data-stu-id="15848-123">Example 4: Export aliases as a script</span></span>

```powershell
Export-Alias -Path "alias.ps1" -As Script
Add-Content -Path $Profile -Value (Get-Content alias.ps1)
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -FilePath .\alias.ps1
```

<span data-ttu-id="15848-124">In diesem Beispiel wird gezeigt, wie das Skriptdatei Format verwendet wird, das von `Export-Alias` generiert wird.</span><span class="sxs-lookup"><span data-stu-id="15848-124">This example shows how to use the script file format that `Export-Alias` generates.</span></span>

<span data-ttu-id="15848-125">Der erste Befehl exportiert die Aliase der Sitzung in die Datei „Alias.ps1“.</span><span class="sxs-lookup"><span data-stu-id="15848-125">The first command exports the aliases in the session to the Alias.ps1 file.</span></span>
<span data-ttu-id="15848-126">Er verwendet den **As** -Parameter mit dem Wert "Script", um eine Datei zu generieren, die einen Set-Alias Befehl für jeden Alias enthält.</span><span class="sxs-lookup"><span data-stu-id="15848-126">It uses the **As** parameter with a value of Script to generate a file that contains a Set-Alias command for each alias.</span></span>

<span data-ttu-id="15848-127">Der zweite Befehl fügt dem CurrentUser-CurrentHost-Profil die Aliase aus der Datei „Alias.ps1“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="15848-127">The second command adds the aliases in the Alias.ps1 file to the CurrentUser-CurrentHost profile.</span></span>
<span data-ttu-id="15848-128">Der Pfad zum Profil wird in der Variablen gespeichert `$Profile` .</span><span class="sxs-lookup"><span data-stu-id="15848-128">The path to the profile is saved in the `$Profile` variable.</span></span>
<span data-ttu-id="15848-129">Der Befehl verwendet das `Get-Content` Cmdlet, um die Aliase aus der Alias.ps1-Datei zu erhalten, und das `Add-Content` Cmdlet, um Sie dem Profil hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="15848-129">The command uses the `Get-Content` cmdlet to get the aliases from the Alias.ps1 file and the `Add-Content` cmdlet to add them to the profile.</span></span>
<span data-ttu-id="15848-130">Weitere Informationen finden Sie unter „about_Profiles“.</span><span class="sxs-lookup"><span data-stu-id="15848-130">For more information, see about_Profiles.</span></span>

<span data-ttu-id="15848-131">Mit dem dritten und vierten Befehl werden die Aliase in der Alias.ps1 Datei einer Remote Sitzung auf dem Computer Server01 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="15848-131">The third and fourth commands add the aliases in the Alias.ps1 file to a remote session on the Server01 computer.</span></span>
<span data-ttu-id="15848-132">Der dritte Befehl verwendet das `New-PSSession` Cmdlet, um die Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="15848-132">The third command uses the `New-PSSession` cmdlet to create the session.</span></span>
<span data-ttu-id="15848-133">Der vierte Befehl verwendet den **FilePath** -Parameter des `Invoke-Command` Cmdlets, um die Alias.ps1 Datei in der neuen Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="15848-133">The fourth command uses the **FilePath** parameter of the `Invoke-Command` cmdlet to run the Alias.ps1 file in the new session.</span></span>

## <span data-ttu-id="15848-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="15848-134">PARAMETERS</span></span>

### <span data-ttu-id="15848-135">-Anfügen</span><span class="sxs-lookup"><span data-stu-id="15848-135">-Append</span></span>

<span data-ttu-id="15848-136">Gibt an, dass dieses Cmdlet die Ausgabe an die angegebene Datei anfügt, anstatt den vorhandenen Inhalt der Datei zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="15848-136">Indicates that this cmdlet appends the output to the specified file, rather than overwriting the existing contents of that file.</span></span>

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

### <span data-ttu-id="15848-137">-AS</span><span class="sxs-lookup"><span data-stu-id="15848-137">-As</span></span>

<span data-ttu-id="15848-138">Gibt das Ausgabeformat an.</span><span class="sxs-lookup"><span data-stu-id="15848-138">Specifies the output format.</span></span>
<span data-ttu-id="15848-139">CSV ist das Standardformat.</span><span class="sxs-lookup"><span data-stu-id="15848-139">CSV is the default.</span></span>
<span data-ttu-id="15848-140">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="15848-140">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="15848-141">CSV.</span><span class="sxs-lookup"><span data-stu-id="15848-141">CSV.</span></span>
<span data-ttu-id="15848-142">Durch Trennzeichen getrenntes Format (.csv).</span><span class="sxs-lookup"><span data-stu-id="15848-142">Comma-separated value (CSV) format.</span></span>
- <span data-ttu-id="15848-143">Skript.</span><span class="sxs-lookup"><span data-stu-id="15848-143">Script.</span></span>
<span data-ttu-id="15848-144">Erstellt einen `Set-Alias` Befehl für jeden exportierten Alias.</span><span class="sxs-lookup"><span data-stu-id="15848-144">Creates a `Set-Alias` command for each exported alias.</span></span>
<span data-ttu-id="15848-145">Wenn Sie die Ausgabedatei mit der Dateierweiterung „.ps1“ benennen, können Sie sie als Skript ausführen, um die Aliase beliebigen Sitzungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="15848-145">If you name the output file with a .ps1 file name extension, you can run it as a script to add the aliases to any session.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ExportAliasFormat
Parameter Sets: (All)
Aliases:
Accepted values: Csv, Script

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15848-146">-Description</span><span class="sxs-lookup"><span data-stu-id="15848-146">-Description</span></span>

<span data-ttu-id="15848-147">Gibt die Beschreibung der exportierten Datei an.</span><span class="sxs-lookup"><span data-stu-id="15848-147">Specifies the description of the exported file.</span></span>
<span data-ttu-id="15848-148">Die Beschreibung wird am Anfang der Datei nach den Headerinformationen als Kommentar angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15848-148">The description appears as a comment at the top of the file, following the header information.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15848-149">-Force</span><span class="sxs-lookup"><span data-stu-id="15848-149">-Force</span></span>

<span data-ttu-id="15848-150">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="15848-150">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="15848-151">Überschreibt die Ausgabedatei, auch wenn das ReadOnly-Attribut für die Datei festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="15848-151">Overwrites the output file, even if the read-only attribute is set on the file.</span></span>

<span data-ttu-id="15848-152">Standardmäßig `Export-Alias` überschreibt Dateien ohne Warnung, es sei denn, das Read-Only-oder Hidden-Attribut wurde festgelegt, oder der **noClobber** -Parameter wird im Befehl verwendet.</span><span class="sxs-lookup"><span data-stu-id="15848-152">By default, `Export-Alias` overwrites files without warning, unless the read-only or hidden attribute is set or the **NoClobber** parameter is used in the command.</span></span>
<span data-ttu-id="15848-153">Der **noClobber** -Parameter hat Vorrang vor dem **Force** -Parameter, wenn beide in einem Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="15848-153">The **NoClobber** parameter takes precedence over the **Force** parameter when both are used in a command.</span></span>

<span data-ttu-id="15848-154">Der **Force** -Parameter kann das `Export-Alias` Überschreiben von Dateien mit dem hidden-Attribut nicht erzwingen.</span><span class="sxs-lookup"><span data-stu-id="15848-154">The **Force** parameter cannot force `Export-Alias` to overwrite files with the hidden attribute.</span></span>

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

### <span data-ttu-id="15848-155">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="15848-155">-LiteralPath</span></span>

<span data-ttu-id="15848-156">Gibt den Pfad zur Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="15848-156">Specifies the path to the output file.</span></span>
<span data-ttu-id="15848-157">Im Gegensatz zu **Path** wird der Wert des **LiteralPath** -Parameters genauso verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="15848-157">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="15848-158">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="15848-158">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="15848-159">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="15848-159">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="15848-160">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="15848-160">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="15848-161">-Name</span><span class="sxs-lookup"><span data-stu-id="15848-161">-Name</span></span>

<span data-ttu-id="15848-162">Gibt die Namen als Array der zu exportierenden Aliase an.</span><span class="sxs-lookup"><span data-stu-id="15848-162">Specifies the names as an array of the aliases to export.</span></span>
<span data-ttu-id="15848-163">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="15848-163">Wildcards are permitted.</span></span>

<span data-ttu-id="15848-164">Standardmäßig `Export-Alias` exportiert alle Aliase in der Sitzung oder im Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="15848-164">By default, `Export-Alias` exports all aliases in the session or scope.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="15848-165">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="15848-165">-NoClobber</span></span>

<span data-ttu-id="15848-166">Gibt an, dass dieses Cmdlet verhindert `Export-Alias` , dass Dateien überschrieben werden, auch wenn der **Force** -Parameter im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="15848-166">Indicates that this cmdlet prevents `Export-Alias` from overwriting any files, even if the **Force** parameter is used in the command.</span></span>

<span data-ttu-id="15848-167">Wenn der **noClobber** -Parameter weggelassen wird, `Export-Alias` wird eine vorhandene Datei ohne Warnung überschrieben, es sei denn, das schreibgeschützte Attribut wurde für die Datei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="15848-167">If the **NoClobber** parameter is omitted, `Export-Alias` will overwrite an existing file without warning, unless the read-only attribute is set on the file.</span></span>
<span data-ttu-id="15848-168">*NoClobber* hat Vorrang vor dem **Force** -Parameter, `Export-Alias` mit dem eine Datei mit dem schreibgeschützten Attribut überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="15848-168">*NoClobber* takes precedence over the **Force** parameter, which permits `Export-Alias` to overwrite a file with the read-only attribute.</span></span>

<span data-ttu-id="15848-169">*NoClobber* verhindert nicht, dass der **Append** -Parameter einer vorhandenen Dateiinhalt hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="15848-169">*NoClobber* does not prevent the **Append** parameter from adding content to an existing file.</span></span>

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

### <span data-ttu-id="15848-170">-PassThru</span><span class="sxs-lookup"><span data-stu-id="15848-170">-PassThru</span></span>

<span data-ttu-id="15848-171">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="15848-171">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="15848-172">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="15848-172">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="15848-173">-Path</span><span class="sxs-lookup"><span data-stu-id="15848-173">-Path</span></span>

<span data-ttu-id="15848-174">Gibt den Pfad zur Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="15848-174">Specifies the path to the output file.</span></span>
<span data-ttu-id="15848-175">Platzhalter sind zulässig, aber der resultierende Pfadwert muss in einen einzelnen Dateinamen aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="15848-175">Wildcards are permitted, but the resulting path value must resolve to a single file name.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="15848-176">-Bereich</span><span class="sxs-lookup"><span data-stu-id="15848-176">-Scope</span></span>

<span data-ttu-id="15848-177">Gibt den Bereich an, aus dem die Aliase exportiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="15848-177">Specifies the scope from which the aliases should be exported.</span></span>
<span data-ttu-id="15848-178">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="15848-178">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="15848-179">Global</span><span class="sxs-lookup"><span data-stu-id="15848-179">Global</span></span>
- <span data-ttu-id="15848-180">Lokal</span><span class="sxs-lookup"><span data-stu-id="15848-180">Local</span></span>
- <span data-ttu-id="15848-181">Skript</span><span class="sxs-lookup"><span data-stu-id="15848-181">Script</span></span>
- <span data-ttu-id="15848-182">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist)</span><span class="sxs-lookup"><span data-stu-id="15848-182">A number relative to the current scope (0 through the number of scopes where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="15848-183">Der Standardwert ist Local.</span><span class="sxs-lookup"><span data-stu-id="15848-183">The default value is Local.</span></span>
<span data-ttu-id="15848-184">Weitere Informationen finden Sie unter „about_Scopes“.</span><span class="sxs-lookup"><span data-stu-id="15848-184">For more information, see about_Scopes.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15848-185">-Confirm</span><span class="sxs-lookup"><span data-stu-id="15848-185">-Confirm</span></span>

<span data-ttu-id="15848-186">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="15848-186">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="15848-187">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="15848-187">-WhatIf</span></span>

<span data-ttu-id="15848-188">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="15848-188">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="15848-189">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="15848-189">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="15848-190">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="15848-190">CommonParameters</span></span>

<span data-ttu-id="15848-191">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="15848-191">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="15848-192">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="15848-192">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="15848-193">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="15848-193">INPUTS</span></span>

### <span data-ttu-id="15848-194">Keine</span><span class="sxs-lookup"><span data-stu-id="15848-194">None.</span></span>

<span data-ttu-id="15848-195">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="15848-195">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="15848-196">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="15848-196">OUTPUTS</span></span>

### <span data-ttu-id="15848-197">None oder System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="15848-197">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="15848-198">Wenn Sie den **passthru** -Parameter verwenden, `Export-Alias` gibt ein **System. Management. Automation. AliasInfo** -Objekt zurück, das den Alias darstellt.</span><span class="sxs-lookup"><span data-stu-id="15848-198">When you use the **Passthru** parameter, `Export-Alias` returns a **System.Management.Automation.AliasInfo** object that represents the alias.</span></span>
<span data-ttu-id="15848-199">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="15848-199">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="15848-200">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="15848-200">NOTES</span></span>

* <span data-ttu-id="15848-201">Sie können Export-Alias nur für eine Datei ausführen.</span><span class="sxs-lookup"><span data-stu-id="15848-201">You can only Export-Aliases to a file.</span></span>

## <span data-ttu-id="15848-202">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="15848-202">RELATED LINKS</span></span>

[<span data-ttu-id="15848-203">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="15848-203">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="15848-204">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="15848-204">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="15848-205">New-Alias</span><span class="sxs-lookup"><span data-stu-id="15848-205">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="15848-206">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="15848-206">Set-Alias</span></span>](Set-Alias.md)
