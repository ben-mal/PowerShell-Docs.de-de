---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Alias
ms.openlocfilehash: 9da204513ed4a17eb8dc20481b878a4a783534f6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596360"
---
# <span data-ttu-id="fbdb7-102">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="fbdb7-102">Export-Alias</span></span>

## <span data-ttu-id="fbdb7-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="fbdb7-103">SYNOPSIS</span></span>
<span data-ttu-id="fbdb7-104">Exportiert Informationen zu aktuell definierten Aliasen in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-104">Exports information about currently defined aliases to a file.</span></span>

## <span data-ttu-id="fbdb7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fbdb7-105">SYNTAX</span></span>

### <span data-ttu-id="fbdb7-106">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="fbdb7-106">ByPath (Default)</span></span>

```
Export-Alias [-Path] <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append] [-Force]
 [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fbdb7-107">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="fbdb7-107">ByLiteralPath</span></span>

```
Export-Alias -LiteralPath <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append]
 [-Force] [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fbdb7-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fbdb7-108">DESCRIPTION</span></span>

<span data-ttu-id="fbdb7-109">Das- `Export-Alias` Cmdlet exportiert die Aliase in der aktuellen Sitzung in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-109">The `Export-Alias` cmdlet exports the aliases in the current session to a file.</span></span>
<span data-ttu-id="fbdb7-110">Wenn die Ausgabedatei nicht vorhanden ist, wird sie vom Cmdlet erstellt.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-110">If the output file does not exist, the cmdlet will create it.</span></span>

<span data-ttu-id="fbdb7-111">`Export-Alias` kann die Aliase in einem bestimmten Bereich oder in allen Bereichen exportieren, kann die Daten im CSV-Format oder als eine Reihe von Set-Alias Befehlen generieren, die Sie einer Sitzung oder einem PowerShell-Profil hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-111">`Export-Alias` can export the aliases in a particular scope or all scopes, it can generate the data in CSV format or as a series of Set-Alias commands that you can add to a session or to a PowerShell profile.</span></span>

## <span data-ttu-id="fbdb7-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="fbdb7-112">EXAMPLES</span></span>

### <span data-ttu-id="fbdb7-113">Beispiel 1: Exportieren eines Alias</span><span class="sxs-lookup"><span data-stu-id="fbdb7-113">Example 1: Export an alias</span></span>

```powershell
Export-Alias -Path "alias.csv"
```

<span data-ttu-id="fbdb7-114">Dieser Befehl exportiert die aktuellen Aliasinformationen in eine Datei namens „Alias.csv“ im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-114">This command exports current alias information to a file named Alias.csv in the current directory.</span></span>

### <span data-ttu-id="fbdb7-115">Beispiel 2: Exportieren eines Alias, es sei denn, die Export Datei ist bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-115">Example 2: Export an alias unless the export file already exists</span></span>

```powershell
Export-Alias -Path "alias.csv" -NoClobber
```

<span data-ttu-id="fbdb7-116">Dieser Befehl exportiert die Aliase der aktuellen Sitzung in eine Datei namens „Alias.csv“.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-116">This command exports the aliases in the current session to an Alias.csv file.</span></span>

<span data-ttu-id="fbdb7-117">Da der **noClobber** -Parameter angegeben wird, schlägt der Befehl fehl, wenn bereits eine Alias.csv Datei im aktuellen Verzeichnis vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-117">Because the **NoClobber** parameter is specified, the command will fail if an Alias.csv file already exists in the current directory.</span></span>

### <span data-ttu-id="fbdb7-118">Beispiel 3: Anfügen von Aliasen an eine Datei</span><span class="sxs-lookup"><span data-stu-id="fbdb7-118">Example 3: Append aliases to a file</span></span>

```powershell
Export-Alias -Path "alias.csv" -Append -Description "Appended Aliases" -Force
```

<span data-ttu-id="fbdb7-119">Dieser Befehl fügt die Aliase der aktuellen Sitzung an eine Datei namens „Alias.csv“ an.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-119">This command appends the aliases in the current session to the Alias.csv file.</span></span>

<span data-ttu-id="fbdb7-120">Der Befehl verwendet den **Description** -Parameter, um den Kommentaren am Anfang der Datei eine Beschreibung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-120">The command uses the **Description** parameter to add a description to the comments at the top of the file.</span></span>

<span data-ttu-id="fbdb7-121">Der Befehl verwendet außerdem den **Force** -Parameter, um vorhandene Alias.csv Dateien zu überschreiben, auch wenn Sie über das schreibgeschützte Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-121">The command also uses the **Force** parameter to overwrite any existing Alias.csv files, even if they have the read-only attribute.</span></span>

### <span data-ttu-id="fbdb7-122">Beispiel 4: Exportieren von Aliasen als Skript</span><span class="sxs-lookup"><span data-stu-id="fbdb7-122">Example 4: Export aliases as a script</span></span>

```powershell
Export-Alias -Path "alias.ps1" -As Script
Add-Content -Path $Profile -Value (Get-Content alias.ps1)
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -FilePath .\alias.ps1
```

<span data-ttu-id="fbdb7-123">In diesem Beispiel wird gezeigt, wie das Skriptdatei Format verwendet wird, das von `Export-Alias` generiert wird.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-123">This example shows how to use the script file format that `Export-Alias` generates.</span></span>

<span data-ttu-id="fbdb7-124">Der erste Befehl exportiert die Aliase der Sitzung in die Datei „Alias.ps1“.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-124">The first command exports the aliases in the session to the Alias.ps1 file.</span></span>
<span data-ttu-id="fbdb7-125">Er verwendet den **As** -Parameter mit dem Wert "Script", um eine Datei zu generieren, die einen Set-Alias Befehl für jeden Alias enthält.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-125">It uses the **As** parameter with a value of Script to generate a file that contains a Set-Alias command for each alias.</span></span>

<span data-ttu-id="fbdb7-126">Der zweite Befehl fügt dem CurrentUser-CurrentHost-Profil die Aliase aus der Datei „Alias.ps1“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-126">The second command adds the aliases in the Alias.ps1 file to the CurrentUser-CurrentHost profile.</span></span>
<span data-ttu-id="fbdb7-127">Der Pfad zum Profil wird in der Variablen gespeichert `$Profile` .</span><span class="sxs-lookup"><span data-stu-id="fbdb7-127">The path to the profile is saved in the `$Profile` variable.</span></span>
<span data-ttu-id="fbdb7-128">Der Befehl verwendet das `Get-Content` Cmdlet, um die Aliase aus der Alias.ps1-Datei zu erhalten, und das `Add-Content` Cmdlet, um Sie dem Profil hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-128">The command uses the `Get-Content` cmdlet to get the aliases from the Alias.ps1 file and the `Add-Content` cmdlet to add them to the profile.</span></span>
<span data-ttu-id="fbdb7-129">Weitere Informationen finden Sie unter „about_Profiles“.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-129">For more information, see about_Profiles.</span></span>

<span data-ttu-id="fbdb7-130">Mit dem dritten und vierten Befehl werden die Aliase in der Alias.ps1 Datei einer Remote Sitzung auf dem Computer Server01 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-130">The third and fourth commands add the aliases in the Alias.ps1 file to a remote session on the Server01 computer.</span></span>
<span data-ttu-id="fbdb7-131">Der dritte Befehl verwendet das `New-PSSession` Cmdlet, um die Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-131">The third command uses the `New-PSSession` cmdlet to create the session.</span></span>
<span data-ttu-id="fbdb7-132">Der vierte Befehl verwendet den **FilePath** -Parameter des `Invoke-Command` Cmdlets, um die Alias.ps1 Datei in der neuen Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-132">The fourth command uses the **FilePath** parameter of the `Invoke-Command` cmdlet to run the Alias.ps1 file in the new session.</span></span>

## <span data-ttu-id="fbdb7-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fbdb7-133">PARAMETERS</span></span>

### <span data-ttu-id="fbdb7-134">-Anfügen</span><span class="sxs-lookup"><span data-stu-id="fbdb7-134">-Append</span></span>

<span data-ttu-id="fbdb7-135">Gibt an, dass dieses Cmdlet die Ausgabe an die angegebene Datei anfügt, anstatt den vorhandenen Inhalt der Datei zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-135">Indicates that this cmdlet appends the output to the specified file, rather than overwriting the existing contents of that file.</span></span>

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

### <span data-ttu-id="fbdb7-136">-AS</span><span class="sxs-lookup"><span data-stu-id="fbdb7-136">-As</span></span>

<span data-ttu-id="fbdb7-137">Gibt das Ausgabeformat an.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-137">Specifies the output format.</span></span>
<span data-ttu-id="fbdb7-138">CSV ist das Standardformat.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-138">CSV is the default.</span></span>
<span data-ttu-id="fbdb7-139">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="fbdb7-139">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fbdb7-140">CSV.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-140">CSV.</span></span>
<span data-ttu-id="fbdb7-141">Durch Trennzeichen getrenntes Format (.csv).</span><span class="sxs-lookup"><span data-stu-id="fbdb7-141">Comma-separated value (CSV) format.</span></span>
- <span data-ttu-id="fbdb7-142">Skript.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-142">Script.</span></span>
<span data-ttu-id="fbdb7-143">Erstellt einen `Set-Alias` Befehl für jeden exportierten Alias.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-143">Creates a `Set-Alias` command for each exported alias.</span></span>
<span data-ttu-id="fbdb7-144">Wenn Sie die Ausgabedatei mit der Dateierweiterung „.ps1“ benennen, können Sie sie als Skript ausführen, um die Aliase beliebigen Sitzungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-144">If you name the output file with a .ps1 file name extension, you can run it as a script to add the aliases to any session.</span></span>

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

### <span data-ttu-id="fbdb7-145">-Description</span><span class="sxs-lookup"><span data-stu-id="fbdb7-145">-Description</span></span>

<span data-ttu-id="fbdb7-146">Gibt die Beschreibung der exportierten Datei an.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-146">Specifies the description of the exported file.</span></span>
<span data-ttu-id="fbdb7-147">Die Beschreibung wird am Anfang der Datei nach den Headerinformationen als Kommentar angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-147">The description appears as a comment at the top of the file, following the header information.</span></span>

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

### <span data-ttu-id="fbdb7-148">-Force</span><span class="sxs-lookup"><span data-stu-id="fbdb7-148">-Force</span></span>

<span data-ttu-id="fbdb7-149">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-149">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="fbdb7-150">Überschreibt die Ausgabedatei, auch wenn das ReadOnly-Attribut für die Datei festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-150">Overwrites the output file, even if the read-only attribute is set on the file.</span></span>

<span data-ttu-id="fbdb7-151">Standardmäßig `Export-Alias` überschreibt Dateien ohne Warnung, es sei denn, das Read-Only-oder Hidden-Attribut wurde festgelegt, oder der **noClobber** -Parameter wird im Befehl verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-151">By default, `Export-Alias` overwrites files without warning, unless the read-only or hidden attribute is set or the **NoClobber** parameter is used in the command.</span></span>
<span data-ttu-id="fbdb7-152">Der **noClobber** -Parameter hat Vorrang vor dem **Force** -Parameter, wenn beide in einem Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-152">The **NoClobber** parameter takes precedence over the **Force** parameter when both are used in a command.</span></span>

<span data-ttu-id="fbdb7-153">Der **Force** -Parameter kann das `Export-Alias` Überschreiben von Dateien mit dem hidden-Attribut nicht erzwingen.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-153">The **Force** parameter cannot force `Export-Alias` to overwrite files with the hidden attribute.</span></span>

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

### <span data-ttu-id="fbdb7-154">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="fbdb7-154">-LiteralPath</span></span>

<span data-ttu-id="fbdb7-155">Gibt den Pfad zur Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-155">Specifies the path to the output file.</span></span>
<span data-ttu-id="fbdb7-156">Im Gegensatz zu **Path** wird der Wert des **LiteralPath**-Parameters genauso verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-156">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="fbdb7-157">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-157">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="fbdb7-158">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-158">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="fbdb7-159">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-159">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="fbdb7-160">-Name</span><span class="sxs-lookup"><span data-stu-id="fbdb7-160">-Name</span></span>

<span data-ttu-id="fbdb7-161">Gibt die Namen als Array der zu exportierenden Aliase an.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-161">Specifies the names as an array of the aliases to export.</span></span>
<span data-ttu-id="fbdb7-162">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-162">Wildcards are permitted.</span></span>

<span data-ttu-id="fbdb7-163">Standardmäßig `Export-Alias` exportiert alle Aliase in der Sitzung oder im Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-163">By default, `Export-Alias` exports all aliases in the session or scope.</span></span>

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

### <span data-ttu-id="fbdb7-164">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="fbdb7-164">-NoClobber</span></span>

<span data-ttu-id="fbdb7-165">Gibt an, dass dieses Cmdlet verhindert `Export-Alias` , dass Dateien überschrieben werden, auch wenn der **Force** -Parameter im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-165">Indicates that this cmdlet prevents `Export-Alias` from overwriting any files, even if the **Force** parameter is used in the command.</span></span>

<span data-ttu-id="fbdb7-166">Wenn der **noClobber** -Parameter weggelassen wird, `Export-Alias` wird eine vorhandene Datei ohne Warnung überschrieben, es sei denn, das schreibgeschützte Attribut wurde für die Datei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-166">If the **NoClobber** parameter is omitted, `Export-Alias` will overwrite an existing file without warning, unless the read-only attribute is set on the file.</span></span>
<span data-ttu-id="fbdb7-167">*NoClobber* hat Vorrang vor dem **Force** -Parameter, `Export-Alias` mit dem eine Datei mit dem schreibgeschützten Attribut überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-167">*NoClobber* takes precedence over the **Force** parameter, which permits `Export-Alias` to overwrite a file with the read-only attribute.</span></span>

<span data-ttu-id="fbdb7-168">*NoClobber* verhindert nicht, dass der **Append** -Parameter einer vorhandenen Dateiinhalt hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-168">*NoClobber* does not prevent the **Append** parameter from adding content to an existing file.</span></span>

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

### <span data-ttu-id="fbdb7-169">-PassThru</span><span class="sxs-lookup"><span data-stu-id="fbdb7-169">-PassThru</span></span>

<span data-ttu-id="fbdb7-170">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-170">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="fbdb7-171">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-171">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="fbdb7-172">-Path</span><span class="sxs-lookup"><span data-stu-id="fbdb7-172">-Path</span></span>

<span data-ttu-id="fbdb7-173">Gibt den Pfad zur Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-173">Specifies the path to the output file.</span></span>
<span data-ttu-id="fbdb7-174">Platzhalter sind zulässig, aber der resultierende Pfadwert muss in einen einzelnen Dateinamen aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-174">Wildcards are permitted, but the resulting path value must resolve to a single file name.</span></span>

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

### <span data-ttu-id="fbdb7-175">-Bereich</span><span class="sxs-lookup"><span data-stu-id="fbdb7-175">-Scope</span></span>

<span data-ttu-id="fbdb7-176">Gibt den Bereich an, aus dem die Aliase exportiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-176">Specifies the scope from which the aliases should be exported.</span></span>
<span data-ttu-id="fbdb7-177">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="fbdb7-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fbdb7-178">Global</span><span class="sxs-lookup"><span data-stu-id="fbdb7-178">Global</span></span>
- <span data-ttu-id="fbdb7-179">Lokal</span><span class="sxs-lookup"><span data-stu-id="fbdb7-179">Local</span></span>
- <span data-ttu-id="fbdb7-180">Skript</span><span class="sxs-lookup"><span data-stu-id="fbdb7-180">Script</span></span>
- <span data-ttu-id="fbdb7-181">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist)</span><span class="sxs-lookup"><span data-stu-id="fbdb7-181">A number relative to the current scope (0 through the number of scopes where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="fbdb7-182">Der Standardwert ist Local.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-182">The default value is Local.</span></span>
<span data-ttu-id="fbdb7-183">Weitere Informationen finden Sie unter „about_Scopes“.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-183">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="fbdb7-184">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fbdb7-184">-Confirm</span></span>

<span data-ttu-id="fbdb7-185">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-185">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fbdb7-186">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fbdb7-186">-WhatIf</span></span>

<span data-ttu-id="fbdb7-187">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-187">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="fbdb7-188">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-188">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fbdb7-189">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fbdb7-189">CommonParameters</span></span>

<span data-ttu-id="fbdb7-190">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-190">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fbdb7-191">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fbdb7-191">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fbdb7-192">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="fbdb7-192">INPUTS</span></span>

### <span data-ttu-id="fbdb7-193">Keine</span><span class="sxs-lookup"><span data-stu-id="fbdb7-193">None.</span></span>

<span data-ttu-id="fbdb7-194">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-194">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="fbdb7-195">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="fbdb7-195">OUTPUTS</span></span>

### <span data-ttu-id="fbdb7-196">None oder System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="fbdb7-196">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="fbdb7-197">Wenn Sie den **passthru** -Parameter verwenden, `Export-Alias` gibt ein **System. Management. Automation. AliasInfo** -Objekt zurück, das den Alias darstellt.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-197">When you use the **Passthru** parameter, `Export-Alias` returns a **System.Management.Automation.AliasInfo** object that represents the alias.</span></span>
<span data-ttu-id="fbdb7-198">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-198">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fbdb7-199">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="fbdb7-199">NOTES</span></span>

* <span data-ttu-id="fbdb7-200">Sie können Export-Alias nur für eine Datei ausführen.</span><span class="sxs-lookup"><span data-stu-id="fbdb7-200">You can only Export-Aliases to a file.</span></span>

## <span data-ttu-id="fbdb7-201">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="fbdb7-201">RELATED LINKS</span></span>

[<span data-ttu-id="fbdb7-202">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="fbdb7-202">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="fbdb7-203">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="fbdb7-203">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="fbdb7-204">New-Alias</span><span class="sxs-lookup"><span data-stu-id="fbdb7-204">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="fbdb7-205">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="fbdb7-205">Set-Alias</span></span>](Set-Alias.md)

