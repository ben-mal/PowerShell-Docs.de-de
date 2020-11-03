---
external help file: Microsoft.PowerShell.Archive-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 07/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/expand-archive?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Expand-Archive
ms.openlocfilehash: 3775cea92ee32a54921bd9441de2c3e0f5915d1d
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "93218055"
---
# <span data-ttu-id="a9f38-103">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="a9f38-103">Expand-Archive</span></span>

## <span data-ttu-id="a9f38-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a9f38-104">SYNOPSIS</span></span>
<span data-ttu-id="a9f38-105">Extrahiert Dateien aus einer angegebenen Archivdatei (ZIP-Datei).</span><span class="sxs-lookup"><span data-stu-id="a9f38-105">Extracts files from a specified archive (zipped) file.</span></span>

## <span data-ttu-id="a9f38-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a9f38-106">SYNTAX</span></span>

### <span data-ttu-id="a9f38-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="a9f38-107">Path (Default)</span></span>

```
Expand-Archive [-Path] <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a9f38-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a9f38-108">LiteralPath</span></span>

```
Expand-Archive -LiteralPath <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a9f38-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a9f38-109">DESCRIPTION</span></span>

<span data-ttu-id="a9f38-110">Mit dem- `Expand-Archive` Cmdlet werden Dateien aus einer angegebenen ZIP-Archivdatei in einen angegebenen Zielordner extrahiert.</span><span class="sxs-lookup"><span data-stu-id="a9f38-110">The `Expand-Archive` cmdlet extracts files from a specified zipped archive file to a specified destination folder.</span></span> <span data-ttu-id="a9f38-111">Eine Archivdatei ermöglicht das Verpacken und optional komprimieren mehrerer Dateien in einer einzigen ZIP-Datei, um die Verteilung und Speicherung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="a9f38-111">An archive file allows multiple files to be packaged, and optionally compressed, into a single zipped file for easier distribution and storage.</span></span>

## <span data-ttu-id="a9f38-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a9f38-112">EXAMPLES</span></span>

### <span data-ttu-id="a9f38-113">Beispiel 1: Extrahieren des Inhalts eines Archivs</span><span class="sxs-lookup"><span data-stu-id="a9f38-113">Example 1: Extract the contents of an archive</span></span>

<span data-ttu-id="a9f38-114">In diesem Beispiel wird der Inhalt einer vorhandenen Archivdatei in den Ordner extrahiert, der durch den **DestinationPath** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a9f38-114">This example extracts the contents of an existing archive file into the folder specified by the **DestinationPath** parameter.</span></span>

```powershell
Expand-Archive -LiteralPath 'C:\Archives\Draft[v1].Zip' -DestinationPath C:\Reference
```

<span data-ttu-id="a9f38-115">In diesem Beispiel wird der **literalpath** -Parameter verwendet, da der Dateiname Zeichen enthält, die als Platzhalter interpretiert werden können.</span><span class="sxs-lookup"><span data-stu-id="a9f38-115">In this example, the **LiteralPath** parameter is used because the filename contains characters that could be interpreted as wildcards.</span></span>

### <span data-ttu-id="a9f38-116">Beispiel 2: Extrahieren des Inhalts eines Archivs im aktuellen Ordner</span><span class="sxs-lookup"><span data-stu-id="a9f38-116">Example 2: Extract the contents of an archive in the current folder</span></span>

<span data-ttu-id="a9f38-117">In diesem Beispiel wird der Inhalt einer vorhandenen Archivdatei im aktuellen Ordner in den Ordner extrahiert, der durch den **DestinationPath** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a9f38-117">This example extracts the contents of an existing archive file in the current folder into the folder specified by the **DestinationPath** parameter.</span></span>

```powershell
Expand-Archive -Path Draftv2.Zip -DestinationPath C:\Reference
```

## <span data-ttu-id="a9f38-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a9f38-118">PARAMETERS</span></span>

### <span data-ttu-id="a9f38-119">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="a9f38-119">-DestinationPath</span></span>

<span data-ttu-id="a9f38-120">Standardmäßig `Expand-Archive` wird von ein Ordner am aktuellen Speicherort erstellt, der dem Namen der ZIP-Datei entspricht.</span><span class="sxs-lookup"><span data-stu-id="a9f38-120">By default, `Expand-Archive` creates a folder in the current location that is the same name as the ZIP file.</span></span> <span data-ttu-id="a9f38-121">Der-Parameter ermöglicht es Ihnen, den Pfad zu einem anderen Ordner anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a9f38-121">The parameter allows you to specify the path to a different folder.</span></span> <span data-ttu-id="a9f38-122">Der Zielordner wird erstellt, wenn er nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a9f38-122">The target folder is created if it does not exist.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: A folder in the current location
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a9f38-123">-Force</span><span class="sxs-lookup"><span data-stu-id="a9f38-123">-Force</span></span>

<span data-ttu-id="a9f38-124">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a9f38-124">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="a9f38-125">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="a9f38-125">-LiteralPath</span></span>

<span data-ttu-id="a9f38-126">Gibt den Pfad zu einer Archivdatei an.</span><span class="sxs-lookup"><span data-stu-id="a9f38-126">Specifies the path to an archive file.</span></span> <span data-ttu-id="a9f38-127">Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a9f38-127">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="a9f38-128">Platzhalterzeichen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a9f38-128">Wildcard characters are not supported.</span></span> <span data-ttu-id="a9f38-129">Wenn der Pfad Escapezeichen enthält, schließen Sie jedes Escapezeichen in einfache Anführungszeichen ein, um PowerShell anzuweisen, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="a9f38-129">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a9f38-130">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a9f38-130">-PassThru</span></span>

<span data-ttu-id="a9f38-131">Bewirkt, dass das Cmdlet eine Liste der aus dem Archiv erweiterten Dateien ausgibt.</span><span class="sxs-lookup"><span data-stu-id="a9f38-131">Causes the cmdlet to output a list of the files expanded from the archive.</span></span>

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

### <span data-ttu-id="a9f38-132">-Path</span><span class="sxs-lookup"><span data-stu-id="a9f38-132">-Path</span></span>

<span data-ttu-id="a9f38-133">Gibt den Pfad zur Archivdatei an.</span><span class="sxs-lookup"><span data-stu-id="a9f38-133">Specifies the path to the archive file.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a9f38-134">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a9f38-134">-Confirm</span></span>

<span data-ttu-id="a9f38-135">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a9f38-135">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a9f38-136">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a9f38-136">-WhatIf</span></span>

<span data-ttu-id="a9f38-137">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9f38-137">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a9f38-138">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a9f38-138">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a9f38-139">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a9f38-139">CommonParameters</span></span>
<span data-ttu-id="a9f38-140">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a9f38-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a9f38-141">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a9f38-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a9f38-142">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a9f38-142">INPUTS</span></span>

### <span data-ttu-id="a9f38-143">System.String</span><span class="sxs-lookup"><span data-stu-id="a9f38-143">System.String</span></span>

<span data-ttu-id="a9f38-144">Sie können eine Zeichenfolge, die einen Pfad enthält, über die Pipeline an eine vorhandene Archivdatei übergeben.</span><span class="sxs-lookup"><span data-stu-id="a9f38-144">You can pipe a string that contains a path to an existing archive file.</span></span>

## <span data-ttu-id="a9f38-145">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a9f38-145">OUTPUTS</span></span>

### <span data-ttu-id="a9f38-146">System. IO. FileSystemInfo</span><span class="sxs-lookup"><span data-stu-id="a9f38-146">System.IO.FileSystemInfo</span></span>

<span data-ttu-id="a9f38-147">Wenn der- `-PassThru` Parameter verwendet wird, gibt das Cmdlet eine Liste der Dateien aus, die aus dem Archiv erweitert wurden.</span><span class="sxs-lookup"><span data-stu-id="a9f38-147">When the `-PassThru` parameter is used, the cmdlet outputs a list of files that were expanded from the archive.</span></span>

## <span data-ttu-id="a9f38-148">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a9f38-148">NOTES</span></span>

<span data-ttu-id="a9f38-149">Die [ZIP-Datei Spezifikation](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) gibt keine Standardmethode zum Codieren von Dateinamen an, die nicht-ASCII-Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="a9f38-149">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="a9f38-150">Das `Compress-Archive` Cmdlet verwendet UTF-8-Codierung.</span><span class="sxs-lookup"><span data-stu-id="a9f38-150">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="a9f38-151">Andere ZIP-Archiv Tools verwenden möglicherweise ein anderes Codierungsschema.</span><span class="sxs-lookup"><span data-stu-id="a9f38-151">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="a9f38-152">Beim Extrahieren von Dateien mit Dateinamen, die nicht mit UTF-8-Codierung gespeichert werden, `Expand-Archive` verwendet den im Archiv gefundenen Rohwert.</span><span class="sxs-lookup"><span data-stu-id="a9f38-152">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="a9f38-153">Dies kann zu einem Dateinamen führen, der sich von dem im Archiv gespeicherten Quell Dateinamen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="a9f38-153">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="a9f38-154">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a9f38-154">RELATED LINKS</span></span>

[<span data-ttu-id="a9f38-155">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="a9f38-155">Compress-Archive</span></span>](compress-archive.md)
