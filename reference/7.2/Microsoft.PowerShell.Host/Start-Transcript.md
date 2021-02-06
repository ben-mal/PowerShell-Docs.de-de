---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 01/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/start-transcript?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transcript
ms.openlocfilehash: d0987c77e3c2bb8cee08e67610cd6fe4fedc36e4
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "99600696"
---
# <span data-ttu-id="1afb8-102">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="1afb8-102">Start-Transcript</span></span>

## <span data-ttu-id="1afb8-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="1afb8-103">Synopsis</span></span>
<span data-ttu-id="1afb8-104">Erstellt einen Datensatz einer gesamten oder eines Teils einer PowerShell-Sitzung in einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="1afb8-104">Creates a record of all or part of a PowerShell session to a text file.</span></span>

## <span data-ttu-id="1afb8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1afb8-105">Syntax</span></span>

### <span data-ttu-id="1afb8-106">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="1afb8-106">ByPath (Default)</span></span>

```
Start-Transcript [[-Path] <String>] [-Append] [-Force] [-NoClobber] [-IncludeInvocationHeader]
 [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="1afb8-107">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="1afb8-107">ByLiteralPath</span></span>

```
Start-Transcript [[-LiteralPath] <String>] [-Append] [-Force] [-NoClobber]
 [-IncludeInvocationHeader] [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="1afb8-108">Byoutputdirectory</span><span class="sxs-lookup"><span data-stu-id="1afb8-108">ByOutputDirectory</span></span>

```
Start-Transcript [[-OutputDirectory] <String>] [-Append] [-Force] [-NoClobber]
 [-IncludeInvocationHeader] [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="1afb8-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1afb8-109">Description</span></span>

<span data-ttu-id="1afb8-110">Das- `Start-Transcript` Cmdlet erstellt einen Datensatz einer gesamten oder eines Teils einer PowerShell-Sitzung in einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="1afb8-110">The `Start-Transcript` cmdlet creates a record of all or part of a PowerShell session to a text file.</span></span> <span data-ttu-id="1afb8-111">Die Aufzeichnung enthält alle Befehle, die der Benutzer eingibt, und alle Ausgaben, die auf der Konsole angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1afb8-111">The transcript includes all command that the user types and all output that appears on the console.</span></span>

<span data-ttu-id="1afb8-112">Ab Windows PowerShell 5,0 `Start-Transcript` schließt den Hostnamen in den generierten Dateinamen aller Transkriptionen ein.</span><span class="sxs-lookup"><span data-stu-id="1afb8-112">Starting in Windows PowerShell 5.0, `Start-Transcript` includes the hostname in the generated file name of all transcripts.</span></span> <span data-ttu-id="1afb8-113">Dies ist besonders nützlich, wenn die Protokollierung Ihres Unternehmens zentralisiert ist.</span><span class="sxs-lookup"><span data-stu-id="1afb8-113">This is especially useful when your enterprise's logging is centralized.</span></span>
<span data-ttu-id="1afb8-114">Dateien, die vom `Start-Transcript` Cmdlet erstellt werden, enthalten zufällige Zeichen in Namen, um potenzielle über schreibungen oder Duplizierungen zu vermeiden, wenn zwei oder mehr Transkriptionen gleichzeitig gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="1afb8-114">Files that are created by the `Start-Transcript` cmdlet include random characters in names to prevent potential overwrites or duplication when two or more transcripts are started simultaneously.</span></span>
<span data-ttu-id="1afb8-115">Dies verhindert auch eine nicht autorisierte Ermittlung von Transkriptionen, die in einer zentralisierten Dateifreigabe gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="1afb8-115">This also prevents unauthorized discovery of transcripts that are stored in a centralized file share.</span></span>

<span data-ttu-id="1afb8-116">Wenn die Zieldatei nicht über eine Byte Reihenfolge-Marke (BOM) verfügt, wird `Start-Transcript` standardmäßig `Utf8NoBom` die Codierung in der Zieldatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="1afb8-116">If the target file doesn't have a Byte Order Mark (BOM), `Start-Transcript` defaults to `Utf8NoBom` encoding in the target file.</span></span>

## <span data-ttu-id="1afb8-117">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1afb8-117">Examples</span></span>

### <span data-ttu-id="1afb8-118">Beispiel 1: Starten einer Transkriptions Datei mit Standardeinstellungen</span><span class="sxs-lookup"><span data-stu-id="1afb8-118">Example 1: Start a transcript file with default settings</span></span>

```powershell
Start-Transcript
```

<span data-ttu-id="1afb8-119">Dieser Befehl startet eine Aufzeichnung am Standarddateispeicherort.</span><span class="sxs-lookup"><span data-stu-id="1afb8-119">This command starts a transcript in the default file location.</span></span>

### <span data-ttu-id="1afb8-120">Beispiel 2: Starten einer Transkriptions Datei an einem bestimmten Speicherort</span><span class="sxs-lookup"><span data-stu-id="1afb8-120">Example 2: Start a transcript file at a specific location</span></span>

```powershell
Start-Transcript -Path "C:\transcripts\transcript0.txt" -NoClobber
```

<span data-ttu-id="1afb8-121">Dieser Befehl startet eine Aufzeichnung in der `Transcript0.txt` Datei in `C:\transcripts` .</span><span class="sxs-lookup"><span data-stu-id="1afb8-121">This command starts a transcript in the `Transcript0.txt` file in `C:\transcripts`.</span></span> <span data-ttu-id="1afb8-122">Da der **noClobber** -Parameter verwendet wird, verhindert der Befehl, dass vorhandene Dateien überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="1afb8-122">Since the **NoClobber** parameter is used, the command prevents any existing files from being overwritten.</span></span> <span data-ttu-id="1afb8-123">Wenn die `Transcript0.txt` Datei bereits vorhanden ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="1afb8-123">If the `Transcript0.txt` file already exists, the command fails.</span></span>

## <span data-ttu-id="1afb8-124">Parameter</span><span class="sxs-lookup"><span data-stu-id="1afb8-124">Parameters</span></span>

### <span data-ttu-id="1afb8-125">-Anfügen</span><span class="sxs-lookup"><span data-stu-id="1afb8-125">-Append</span></span>

<span data-ttu-id="1afb8-126">Gibt an, dass dieses Cmdlet die neue Aufzeichnung am Ende einer vorhandenen Datei hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="1afb8-126">Indicates that this cmdlet adds the new transcript to the end of an existing file.</span></span> <span data-ttu-id="1afb8-127">Verwenden Sie den **path** -Parameter, um die Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1afb8-127">Use the **Path** parameter to specify the file.</span></span>

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

### <span data-ttu-id="1afb8-128">-Force</span><span class="sxs-lookup"><span data-stu-id="1afb8-128">-Force</span></span>

<span data-ttu-id="1afb8-129">Erlaubt dem Cmdlet, die Aufzeichnung an eine vorhandene schreibgeschützte Datei anzuhängen.</span><span class="sxs-lookup"><span data-stu-id="1afb8-129">Allows the cmdlet to append the transcript to an existing read-only file.</span></span> <span data-ttu-id="1afb8-130">Bei Anwendung auf eine schreibgeschützte Datei ändert das Cmdlet die Dateiberechtigung in „Lesen/Schreiben“.</span><span class="sxs-lookup"><span data-stu-id="1afb8-130">When used on a read-only file, the cmdlet changes the file permission to read-write.</span></span> <span data-ttu-id="1afb8-131">Das Cmdlet kann Sicherheitseinschränkungen nicht überschreiben, wenn dieser Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1afb8-131">The cmdlet cannot override security restrictions when this parameter is used.</span></span>

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

### <span data-ttu-id="1afb8-132">-Includeinvocationheader</span><span class="sxs-lookup"><span data-stu-id="1afb8-132">-IncludeInvocationHeader</span></span>

<span data-ttu-id="1afb8-133">Gibt an, dass dieses Cmdlet den Zeitstempel beim Ausführen von Befehlen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="1afb8-133">Indicates that this cmdlet logs the time stamp when commands are run.</span></span>

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

### <span data-ttu-id="1afb8-134">-Useminimalheader</span><span class="sxs-lookup"><span data-stu-id="1afb8-134">-UseMinimalHeader</span></span>

<span data-ttu-id="1afb8-135">Fügen Sie dem Transkripts anstelle des standardmäßig enthaltenen ausführlichen Headers einen kurzen Header vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="1afb8-135">Prepend a short header to the transcript, instead of the detailed header included by default.</span></span> <span data-ttu-id="1afb8-136">Dieser Parameter wurde in PowerShell 6,2 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1afb8-136">This parameter was added in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="1afb8-137">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="1afb8-137">-LiteralPath</span></span>

<span data-ttu-id="1afb8-138">Gibt einen Speicherort für die Transkriptions Datei an.</span><span class="sxs-lookup"><span data-stu-id="1afb8-138">Specifies a location to the transcript file.</span></span> <span data-ttu-id="1afb8-139">Im Gegensatz zum **Path**-Parameter wird der Wert des **LiteralPath**-Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="1afb8-139">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="1afb8-140">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="1afb8-140">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="1afb8-141">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="1afb8-141">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="1afb8-142">Einfache Anführungszeichen informieren PowerShell darüber, dass keine Zeichen als Escapesequenzen interpretiert werden können.</span><span class="sxs-lookup"><span data-stu-id="1afb8-142">Single quotation marks inform PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1afb8-143">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="1afb8-143">-NoClobber</span></span>

<span data-ttu-id="1afb8-144">Gibt an, dass von diesem Cmdlet keine vorhandene Datei überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="1afb8-144">Indicates that this cmdlet will not overwrite of an existing file.</span></span> <span data-ttu-id="1afb8-145">Wenn eine Transkriptions Datei im angegebenen Pfad vorhanden ist, wird `Start-Transcript` die Datei standardmäßig ohne Warnung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="1afb8-145">By default, if a transcript file exists in the specified path, `Start-Transcript` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="1afb8-146">-OutputDirectory</span><span class="sxs-lookup"><span data-stu-id="1afb8-146">-OutputDirectory</span></span>

<span data-ttu-id="1afb8-147">Gibt einen bestimmten Pfad und Ordner an, in dem ein Transkript gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1afb8-147">Specifies a specific path and folder in which to save a transcript.</span></span> <span data-ttu-id="1afb8-148">Der Transkriptions Name wird von PowerShell automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="1afb8-148">PowerShell automatically assigns the transcript name.</span></span>

```yaml
Type: System.String
Parameter Sets: ByOutputDirectory
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1afb8-149">-Path</span><span class="sxs-lookup"><span data-stu-id="1afb8-149">-Path</span></span>

<span data-ttu-id="1afb8-150">Gibt einen Speicherort für die Transkriptions Datei an.</span><span class="sxs-lookup"><span data-stu-id="1afb8-150">Specifies a location to the transcript file.</span></span> <span data-ttu-id="1afb8-151">Geben Sie einen Pfad zu einer `.txt` Datei ein.</span><span class="sxs-lookup"><span data-stu-id="1afb8-151">Enter a path to a `.txt` file.</span></span> <span data-ttu-id="1afb8-152">Platzhalter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1afb8-152">Wildcards are not permitted.</span></span>

<span data-ttu-id="1afb8-153">Wenn Sie keinen Pfad angeben, `Start-Transcript` verwendet den Pfad im Wert der `$Transcript` globalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="1afb8-153">If you do not specify a path, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="1afb8-154">Wenn Sie diese Variable nicht erstellt haben, `Start-Transcript` speichert die Transkriptionen in den `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` Dateien.</span><span class="sxs-lookup"><span data-stu-id="1afb8-154">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` files.</span></span>

<span data-ttu-id="1afb8-155">Wenn eines der Verzeichnisse im Pfad nicht vorhanden ist, tritt bei der Ausführung des Befehls ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="1afb8-155">If any of the directories in the path do not exist, the command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1afb8-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1afb8-156">-Confirm</span></span>

<span data-ttu-id="1afb8-157">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="1afb8-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1afb8-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1afb8-158">-WhatIf</span></span>

<span data-ttu-id="1afb8-159">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1afb8-159">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1afb8-160">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1afb8-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1afb8-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1afb8-161">CommonParameters</span></span>

<span data-ttu-id="1afb8-162">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1afb8-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1afb8-163">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1afb8-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1afb8-164">Eingaben</span><span class="sxs-lookup"><span data-stu-id="1afb8-164">Inputs</span></span>

### <span data-ttu-id="1afb8-165">Keine</span><span class="sxs-lookup"><span data-stu-id="1afb8-165">None</span></span>

<span data-ttu-id="1afb8-166">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="1afb8-166">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="1afb8-167">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="1afb8-167">Outputs</span></span>

### <span data-ttu-id="1afb8-168">System.String</span><span class="sxs-lookup"><span data-stu-id="1afb8-168">System.String</span></span>

<span data-ttu-id="1afb8-169">Dieses Cmdlet gibt eine Zeichenfolge zurück, die eine Bestätigungsmeldung und den Pfad zur Ausgabedatei enthält.</span><span class="sxs-lookup"><span data-stu-id="1afb8-169">This cmdlet returns a string that contains a confirmation message and the path to the output file.</span></span>

## <span data-ttu-id="1afb8-170">Notizen</span><span class="sxs-lookup"><span data-stu-id="1afb8-170">Notes</span></span>

<span data-ttu-id="1afb8-171">Verwenden Sie das-Cmdlet, um eine Aufzeichnung zu verhindern `Stop-Transcript` .</span><span class="sxs-lookup"><span data-stu-id="1afb8-171">To stop a transcript, use the `Stop-Transcript` cmdlet.</span></span>

<span data-ttu-id="1afb8-172">Fügen Sie dem Profil den Befehl hinzu, um eine ganze Sitzung aufzuzeichnen `Start-Transcript` .</span><span class="sxs-lookup"><span data-stu-id="1afb8-172">To record an entire session, add the `Start-Transcript` command to your profile.</span></span> <span data-ttu-id="1afb8-173">Weitere Informationen finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1afb8-173">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

## <span data-ttu-id="1afb8-174">Ähnliche Themen</span><span class="sxs-lookup"><span data-stu-id="1afb8-174">Related Links</span></span>

[<span data-ttu-id="1afb8-175">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="1afb8-175">Stop-Transcript</span></span>](Stop-Transcript.md)
