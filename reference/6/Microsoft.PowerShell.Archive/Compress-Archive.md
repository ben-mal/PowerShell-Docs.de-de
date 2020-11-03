---
external help file: Microsoft.PowerShell.Archive-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 02/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/compress-archive?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compress-Archive
ms.openlocfilehash: 7bf349c82133b275f0539db7b78c3583d00da31c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215116"
---
# <span data-ttu-id="0ec66-103">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="0ec66-103">Compress-Archive</span></span>

## <span data-ttu-id="0ec66-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0ec66-104">SYNOPSIS</span></span>
<span data-ttu-id="0ec66-105">Erstellt eine komprimierte oder gezippte Datei aus angegebenen Dateien und Verzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-105">Creates a compressed archive, or zipped file, from specified files and directories.</span></span>

## <span data-ttu-id="0ec66-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0ec66-106">SYNTAX</span></span>

### <span data-ttu-id="0ec66-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="0ec66-107">Path (Default)</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0ec66-108">Pathwithupdate</span><span class="sxs-lookup"><span data-stu-id="0ec66-108">PathWithUpdate</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Update
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0ec66-109">Pathwithforce</span><span class="sxs-lookup"><span data-stu-id="0ec66-109">PathWithForce</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Force
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0ec66-110">Literalpathwithupdate</span><span class="sxs-lookup"><span data-stu-id="0ec66-110">LiteralPathWithUpdate</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Update [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0ec66-111">Literalpathwithforce</span><span class="sxs-lookup"><span data-stu-id="0ec66-111">LiteralPathWithForce</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Force [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0ec66-112">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0ec66-112">LiteralPath</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0ec66-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0ec66-113">DESCRIPTION</span></span>

<span data-ttu-id="0ec66-114">Mit dem- `Compress-Archive` Cmdlet wird eine komprimierte oder komprimierte Archivdatei aus einer oder mehreren angegebenen Dateien oder Verzeichnissen erstellt.</span><span class="sxs-lookup"><span data-stu-id="0ec66-114">The `Compress-Archive` cmdlet creates a compressed, or zipped, archive file from one or more specified files or directories.</span></span> <span data-ttu-id="0ec66-115">Ein Archiv verpackt mehrere Dateien mit optionaler Komprimierung in eine einzelne ZIP-Datei, um die Verteilung und den Speicher zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-115">An archive packages multiple files, with optional compression, into a single zipped file for easier distribution and storage.</span></span> <span data-ttu-id="0ec66-116">Eine Archivdatei kann mithilfe des Komprimierungs Algorithmus komprimiert werden, der durch den **CompressionLevel** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0ec66-116">An archive file can be compressed by using the compression algorithm specified by the **CompressionLevel** parameter.</span></span>

<span data-ttu-id="0ec66-117">Das `Compress-Archive` Cmdlet verwendet die Microsoft .NET-API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) , um Dateien zu komprimieren.</span><span class="sxs-lookup"><span data-stu-id="0ec66-117">The `Compress-Archive` cmdlet uses the Microsoft .NET API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) to compress files.</span></span>
<span data-ttu-id="0ec66-118">Die maximale Dateigröße beträgt 2 GB, da die zugrunde liegende API eingeschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="0ec66-118">The maximum file size is 2 GB because there's a limitation of the underlying API.</span></span>

<span data-ttu-id="0ec66-119">Einige Beispiele verwenden Verteilung, um die Zeilenlänge der Codebeispiele zu verringern.</span><span class="sxs-lookup"><span data-stu-id="0ec66-119">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="0ec66-120">Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="0ec66-120">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="0ec66-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0ec66-121">EXAMPLES</span></span>

### <span data-ttu-id="0ec66-122">Beispiel 1: Komprimieren von Dateien zum Erstellen einer Archivdatei</span><span class="sxs-lookup"><span data-stu-id="0ec66-122">Example 1: Compress files to create an archive file</span></span>

<span data-ttu-id="0ec66-123">In diesem Beispiel werden Dateien aus unterschiedlichen Verzeichnissen komprimiert, und eine Archivdatei wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="0ec66-123">This example compresses files from different directories and creates an archive file.</span></span> <span data-ttu-id="0ec66-124">Ein Platzhalter wird verwendet, um alle Dateien mit einer bestimmten Dateierweiterung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0ec66-124">A wildcard is used to get all files with a particular file extension.</span></span> <span data-ttu-id="0ec66-125">Die Archivdatei enthält keine Verzeichnisstruktur, da der **Pfad** nur Dateinamen angibt.</span><span class="sxs-lookup"><span data-stu-id="0ec66-125">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
  Path = "C:\Reference\Draftdoc.docx", "C:\Reference\Images\*.vsd"
  CompressionLevel = "Fastest"
  DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="0ec66-126">Der **path** -Parameter akzeptiert bestimmte Dateinamen und Dateinamen mit Platzhaltern `*.vsd` .</span><span class="sxs-lookup"><span data-stu-id="0ec66-126">The **Path** parameter accepts specific file names and file names with wildcards, `*.vsd`.</span></span> <span data-ttu-id="0ec66-127">Der **Pfad** verwendet eine durch Trennzeichen getrennte Liste, um Dateien aus unterschiedlichen Verzeichnissen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-127">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="0ec66-128">Der Komprimierungs Grad ist **am schnellsten** , um die Verarbeitungszeit zu verkürzen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-128">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="0ec66-129">Der **DestinationPath** -Parameter gibt den Speicherort für die `Draft.zip` Datei an.</span><span class="sxs-lookup"><span data-stu-id="0ec66-129">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="0ec66-130">Die `Draft.zip` Datei enthält `Draftdoc.docx` und alle Dateien mit einer `.vsd` Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="0ec66-130">The `Draft.zip` file contains `Draftdoc.docx` and all the files with a `.vsd` extension.</span></span>

### <span data-ttu-id="0ec66-131">Beispiel 2: Komprimieren von Dateien mit einem literalpath</span><span class="sxs-lookup"><span data-stu-id="0ec66-131">Example 2: Compress files using a LiteralPath</span></span>

<span data-ttu-id="0ec66-132">Dieses Beispiel komprimiert bestimmte benannte Dateien und erstellt eine neue Archivdatei.</span><span class="sxs-lookup"><span data-stu-id="0ec66-132">This example compresses specific named files and creates a new archive file.</span></span> <span data-ttu-id="0ec66-133">Die Archivdatei enthält keine Verzeichnisstruktur, da der **Pfad** nur Dateinamen angibt.</span><span class="sxs-lookup"><span data-stu-id="0ec66-133">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
LiteralPath= "C:\Reference\Draft Doc.docx", "C:\Reference\Images\diagram2.vsd"
CompressionLevel = "Fastest"
DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="0ec66-134">Absolute Pfad-und Dateinamen werden verwendet, da der **literalpath** -Parameter keine Platzhalter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="0ec66-134">Absolute path and file names are used because the **LiteralPath** parameter doesn't accept wildcards.</span></span> <span data-ttu-id="0ec66-135">Der **Pfad** verwendet eine durch Trennzeichen getrennte Liste, um Dateien aus unterschiedlichen Verzeichnissen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-135">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="0ec66-136">Der Komprimierungs Grad ist **am schnellsten** , um die Verarbeitungszeit zu verkürzen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-136">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="0ec66-137">Der **DestinationPath** -Parameter gibt den Speicherort für die `Draft.zip` Datei an.</span><span class="sxs-lookup"><span data-stu-id="0ec66-137">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="0ec66-138">Die `Draft.zip` Datei enthält nur `Draftdoc.docx` und `diagram2.vsd` .</span><span class="sxs-lookup"><span data-stu-id="0ec66-138">The `Draft.zip` file only contains `Draftdoc.docx` and `diagram2.vsd`.</span></span>

### <span data-ttu-id="0ec66-139">Beispiel 3: Komprimieren eines Verzeichnisses, das das Stammverzeichnis enthält</span><span class="sxs-lookup"><span data-stu-id="0ec66-139">Example 3: Compress a directory that includes the root directory</span></span>

<span data-ttu-id="0ec66-140">In diesem Beispiel wird ein Verzeichnis komprimiert und eine Archivdatei erstellt, die das Stammverzeichnis sowie alle zugehörigen Dateien und Unterverzeichnisse **enthält** .</span><span class="sxs-lookup"><span data-stu-id="0ec66-140">This example compresses a directory and creates an archive file that **includes** the root directory, and all its files and subdirectories.</span></span> <span data-ttu-id="0ec66-141">Die Archivdatei hat eine Verzeichnisstruktur, da der **Pfad** ein Stammverzeichnis angibt.</span><span class="sxs-lookup"><span data-stu-id="0ec66-141">The archive file has a directory structure because the **Path** specifies a root directory.</span></span>

```powershell
Compress-Archive -Path C:\Reference -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="0ec66-142">`Compress-Archive` verwendet den **path** -Parameter, um das Stammverzeichnis anzugeben `C:\Reference` .</span><span class="sxs-lookup"><span data-stu-id="0ec66-142">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference`.</span></span> <span data-ttu-id="0ec66-143">Der **DestinationPath** -Parameter gibt den Speicherort für die Archivdatei an.</span><span class="sxs-lookup"><span data-stu-id="0ec66-143">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="0ec66-144">Das `Draft.zip` Archiv enthält das Stamm `Reference` Verzeichnis und alle zugehörigen Dateien und Unterverzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="0ec66-144">The `Draft.zip` archive includes the `Reference` root directory, and all its files and subdirectories.</span></span>

### <span data-ttu-id="0ec66-145">Beispiel 4: Komprimieren eines Verzeichnisses, das das Stammverzeichnis ausschließt</span><span class="sxs-lookup"><span data-stu-id="0ec66-145">Example 4: Compress a directory that excludes the root directory</span></span>

<span data-ttu-id="0ec66-146">In diesem Beispiel wird ein Verzeichnis komprimiert und eine Archivdatei erstellt, die das Stammverzeichnis **ausschließt** , da der **Pfad** ein Sternchen-Platzhalter ( `*` ) verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ec66-146">This example compresses a directory and creates an archive file that **excludes** the root directory because the **Path** uses an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="0ec66-147">Das Archiv enthält eine Verzeichnisstruktur, die die Dateien und Unterverzeichnisse des Stamm Verzeichnisses enthält.</span><span class="sxs-lookup"><span data-stu-id="0ec66-147">The archive contains a directory structure that contains the root directory's files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference\* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="0ec66-148">`Compress-Archive` verwendet den **path** -Parameter, um das Stammverzeichnis `C:\Reference` mit einem Platzhalter Zeichen ( `*` ) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0ec66-148">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="0ec66-149">Der **DestinationPath** -Parameter gibt den Speicherort für die Archivdatei an.</span><span class="sxs-lookup"><span data-stu-id="0ec66-149">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="0ec66-150">Das `Draft.zip` Archiv enthält die Dateien und Unterverzeichnisse des Stamm Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="0ec66-150">The `Draft.zip` archive contains the root directory's files and subdirectories.</span></span> <span data-ttu-id="0ec66-151">Das Stamm `Reference` Verzeichnis wird aus dem Archiv ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-151">The `Reference` root directory is excluded from the archive.</span></span>

### <span data-ttu-id="0ec66-152">Beispiel 5: komprimieren nur der Dateien in einem Stammverzeichnis</span><span class="sxs-lookup"><span data-stu-id="0ec66-152">Example 5: Compress only the files in a root directory</span></span>

<span data-ttu-id="0ec66-153">In diesem Beispiel werden nur die Dateien in einem Stammverzeichnis komprimiert, und eine Archivdatei wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="0ec66-153">This example compresses only the files in a root directory and creates an archive file.</span></span> <span data-ttu-id="0ec66-154">Das Archiv enthält keine Verzeichnisstruktur, da nur Dateien komprimiert werden.</span><span class="sxs-lookup"><span data-stu-id="0ec66-154">There's no directory structure in the archive because only files are compressed.</span></span>

```powershell
Compress-Archive -Path C:\Reference\*.* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="0ec66-155">`Compress-Archive` verwendet den **path** -Parameter, um das Stammverzeichnis mit einem Platzhalter vom Typ `C:\Reference` **Star-dot-Star** ( `*.*` ) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0ec66-155">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with a **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="0ec66-156">Der **DestinationPath** -Parameter gibt den Speicherort für die Archivdatei an.</span><span class="sxs-lookup"><span data-stu-id="0ec66-156">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="0ec66-157">Das `Draft.zip` Archiv enthält nur die `Reference` Dateien des Stamm Verzeichnisses, und das Stammverzeichnis wird ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-157">The `Draft.zip` archive only contains the `Reference` root directory's files and the root directory is excluded.</span></span>

### <span data-ttu-id="0ec66-158">Beispiel 6: Verwenden der Pipeline zum Archivieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="0ec66-158">Example 6: Use the pipeline to archive files</span></span>

<span data-ttu-id="0ec66-159">In diesem Beispiel werden Dateien über die Pipeline gesendet, um ein Archiv zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-159">This example sends files down the pipeline to create an archive.</span></span> <span data-ttu-id="0ec66-160">Die Archivdatei enthält keine Verzeichnisstruktur, da der **Pfad** nur Dateinamen angibt.</span><span class="sxs-lookup"><span data-stu-id="0ec66-160">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
Get-ChildItem -Path C:\Reference\Afile.txt, C:\Reference\Images\Bfile.txt |
  Compress-Archive -DestinationPath C:\Archives\PipelineFiles.zip
```

<span data-ttu-id="0ec66-161">`Get-ChildItem` verwendet den **path** -Parameter, um zwei Dateien aus unterschiedlichen Verzeichnissen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0ec66-161">`Get-ChildItem` uses the **Path** parameter to specify two files from different directories.</span></span> <span data-ttu-id="0ec66-162">Jede Datei wird durch ein **FileInfo** -Objekt dargestellt und an die Pipeline gesendet `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="0ec66-162">Each file is represented by a **FileInfo** object and is sent down the pipeline to `Compress-Archive`.</span></span>
<span data-ttu-id="0ec66-163">Die beiden angegebenen Dateien werden in archiviert `PipelineFiles.zip` .</span><span class="sxs-lookup"><span data-stu-id="0ec66-163">The two specified files are archived in `PipelineFiles.zip`.</span></span>

### <span data-ttu-id="0ec66-164">Beispiel 7: Verwenden der Pipeline zum Archivieren eines Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="0ec66-164">Example 7: Use the pipeline to archive a directory</span></span>

<span data-ttu-id="0ec66-165">In diesem Beispiel wird ein Verzeichnis nach unten in der Pipeline gesendet, um ein Archiv zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-165">This example sends a directory down the pipeline to create an archive.</span></span> <span data-ttu-id="0ec66-166">Dateien werden als **FileInfo** -Objekte und-Verzeichnisse als **DirectoryInfo** -Objekte gesendet.</span><span class="sxs-lookup"><span data-stu-id="0ec66-166">Files are sent as **FileInfo** objects and directories as **DirectoryInfo** objects.</span></span> <span data-ttu-id="0ec66-167">Die Verzeichnisstruktur des Archivs enthält nicht das Stammverzeichnis, aber seine Dateien und Unterverzeichnisse sind im Archiv enthalten.</span><span class="sxs-lookup"><span data-stu-id="0ec66-167">The archive's directory structure doesn't include the root directory, but its files and subdirectories are included in the archive.</span></span>

```powershell
Get-ChildItem -Path C:\LogFiles | Compress-Archive -DestinationPath C:\Archives\PipelineDir.zip
```

<span data-ttu-id="0ec66-168">`Get-ChildItem` verwendet den **path** -Parameter, um das Stamm `C:\LogFiles` Verzeichnis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0ec66-168">`Get-ChildItem` uses the **Path** parameter to specify the `C:\LogFiles` root directory.</span></span> <span data-ttu-id="0ec66-169">Jedes " **FileInfo** "-und " **DirectoryInfo** "-Objekt wird über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="0ec66-169">Each **FileInfo** and **DirectoryInfo** object is sent down the pipeline.</span></span>

<span data-ttu-id="0ec66-170">`Compress-Archive` Fügt dem Archiv jedes Objekt hinzu `PipelineDir.zip` .</span><span class="sxs-lookup"><span data-stu-id="0ec66-170">`Compress-Archive` adds each object to the `PipelineDir.zip` archive.</span></span> <span data-ttu-id="0ec66-171">Der **path** -Parameter ist nicht angegeben, da die Pipeline Objekte in der Parameter Position 0 empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="0ec66-171">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

### <span data-ttu-id="0ec66-172">Beispiel 8: so wirkt sich die Rekursion auf Archive aus</span><span class="sxs-lookup"><span data-stu-id="0ec66-172">Example 8: How recursion can affect archives</span></span>

<span data-ttu-id="0ec66-173">Dieses Beispiel zeigt, wie die Rekursion Dateien im Archiv duplizieren kann.</span><span class="sxs-lookup"><span data-stu-id="0ec66-173">This example shows how recursion can duplicate files in your archive.</span></span> <span data-ttu-id="0ec66-174">Wenn Sie z `Get-ChildItem` . b. mit dem **recurse** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ec66-174">For example, if you use `Get-ChildItem` with the **Recurse** parameter.</span></span> <span data-ttu-id="0ec66-175">Bei Rekursions Prozessen werden alle **FileInfo** -und **DirectoryInfo** -Objekte über die Pipeline gesendet und dem Archiv hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0ec66-175">As recursion processes, each **FileInfo** and **DirectoryInfo** object is sent down the pipeline and added to the archive.</span></span>

```powershell
Get-ChildItem -Path C:\TestLog -Recurse |
  Compress-Archive -DestinationPath C:\Archives\PipelineRecurse.zip
```

<span data-ttu-id="0ec66-176">Das `C:\TestLog` Verzeichnis enthält keine Dateien.</span><span class="sxs-lookup"><span data-stu-id="0ec66-176">The `C:\TestLog` directory doesn't contain any files.</span></span> <span data-ttu-id="0ec66-177">Sie enthält ein Unterverzeichnis mit `testsub` dem Namen, das die `testlog.txt` Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="0ec66-177">It does contain a subdirectory named `testsub` that contains the `testlog.txt` file.</span></span>

<span data-ttu-id="0ec66-178">`Get-ChildItem` verwendet den **path** -Parameter, um das Stammverzeichnis anzugeben `C:\TestLog` .</span><span class="sxs-lookup"><span data-stu-id="0ec66-178">`Get-ChildItem` uses the **Path** parameter to specify the root directory, `C:\TestLog`.</span></span> <span data-ttu-id="0ec66-179">Der **recurse** -Parameter verarbeitet die Dateien und Verzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="0ec66-179">The **Recurse** parameter processes the files and directories.</span></span> <span data-ttu-id="0ec66-180">Ein **DirectoryInfo** -Objekt wird für `testsub` und ein **FileInfo** -Objekt erstellt `testlog.txt` .</span><span class="sxs-lookup"><span data-stu-id="0ec66-180">A **DirectoryInfo** object is created for `testsub` and a **FileInfo** object `testlog.txt`.</span></span>

<span data-ttu-id="0ec66-181">Jedes Objekt wird über die Pipeline an gesendet `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="0ec66-181">Each object is sent down the pipeline to `Compress-Archive`.</span></span> <span data-ttu-id="0ec66-182">Der **DestinationPath** gibt den Speicherort für die Archivdatei an.</span><span class="sxs-lookup"><span data-stu-id="0ec66-182">The **DestinationPath** specifies the location for the archive file.</span></span> <span data-ttu-id="0ec66-183">Der **path** -Parameter ist nicht angegeben, da die Pipeline Objekte in der Parameter Position 0 empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="0ec66-183">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

<span data-ttu-id="0ec66-184">In der folgenden Zusammenfassung werden die `PipelineRecurse.zip` Inhalte des Archivs beschrieben, die eine doppelte Datei enthalten:</span><span class="sxs-lookup"><span data-stu-id="0ec66-184">The following summary describes the `PipelineRecurse.zip` archive's contents that contains a duplicate file:</span></span>

- <span data-ttu-id="0ec66-185">Das **DirectoryInfo** -Objekt erstellt das `testsub` Verzeichnis und enthält die `testlog.txt` Datei, die die ursprüngliche Verzeichnisstruktur widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="0ec66-185">The **DirectoryInfo** object creates the `testsub` directory and contains the `testlog.txt` file, which reflects the original directory structure.</span></span>
- <span data-ttu-id="0ec66-186">Das **FileInfo** -Objekt erstellt ein Duplikat `testlog.txt` im Stamm des Archivs.</span><span class="sxs-lookup"><span data-stu-id="0ec66-186">The **FileInfo** object creates a duplicate `testlog.txt` in the archive's root.</span></span> <span data-ttu-id="0ec66-187">Die doppelte Datei wird erstellt, da die Rekursion ein Datei Objekt an gesendet hat `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="0ec66-187">The duplicate file is created because recursion sent a file object to `Compress-Archive`.</span></span> <span data-ttu-id="0ec66-188">Dieses Verhalten wird erwartet, da jedes an die Pipeline gesendete Objekt dem Archiv hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0ec66-188">This behavior is expected because each object sent down the pipeline is added to the archive.</span></span>

### <span data-ttu-id="0ec66-189">Beispiel 9: Aktualisieren einer vorhandenen Archivdatei</span><span class="sxs-lookup"><span data-stu-id="0ec66-189">Example 9: Update an existing archive file</span></span>

<span data-ttu-id="0ec66-190">In diesem Beispiel wird eine vorhandene Archivdatei, `Draft.Zip` , im `C:\Archives` Verzeichnis aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0ec66-190">This example updates an existing archive file, `Draft.Zip`, in the `C:\Archives` directory.</span></span> <span data-ttu-id="0ec66-191">In diesem Beispiel enthält die vorhandene Archivdatei das Stammverzeichnis und seine Dateien und Unterverzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="0ec66-191">In this example, the existing archive file contains the root directory, and its files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference -Update -DestinationPath C:\Archives\Draft.Zip
```

<span data-ttu-id="0ec66-192">Der Befehl wird `Draft.Zip` mit neueren Versionen vorhandener Dateien im `C:\Reference` Verzeichnis und seinen Unterverzeichnissen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0ec66-192">The command updates `Draft.Zip` with newer versions of existing files in the `C:\Reference` directory and its subdirectories.</span></span> <span data-ttu-id="0ec66-193">Außerdem sind neue Dateien, die bzw. den Unterverzeichnissen hinzugefügt wurden, `C:\Reference` im aktualisierten `Draft.Zip` Archiv enthalten.</span><span class="sxs-lookup"><span data-stu-id="0ec66-193">And, new files that were added to `C:\Reference` or its subdirectories are included in the updated `Draft.Zip` archive.</span></span>

## <span data-ttu-id="0ec66-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0ec66-194">PARAMETERS</span></span>

### <span data-ttu-id="0ec66-195">-CompressionLevel</span><span class="sxs-lookup"><span data-stu-id="0ec66-195">-CompressionLevel</span></span>

<span data-ttu-id="0ec66-196">Gibt an, wie viel Komprimierung beim Erstellen der Archivdatei angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0ec66-196">Specifies how much compression to apply when you're creating the archive file.</span></span> <span data-ttu-id="0ec66-197">Die schnellere Komprimierung erfordert weniger Zeit zum Erstellen der Datei, kann jedoch zu größeren Dateigrößen führen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-197">Faster compression requires less time to create the file, but can result in larger file sizes.</span></span>

<span data-ttu-id="0ec66-198">Wenn dieser Parameter nicht angegeben wird, verwendet der Befehl den Standardwert, **optimal** .</span><span class="sxs-lookup"><span data-stu-id="0ec66-198">If this parameter isn't specified, the command uses the default value, **Optimal** .</span></span>

<span data-ttu-id="0ec66-199">Im folgenden sind die zulässigen Werte für diesen Parameter aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="0ec66-199">The following are the acceptable values for this parameter:</span></span>

- <span data-ttu-id="0ec66-200">**Schnellste** .</span><span class="sxs-lookup"><span data-stu-id="0ec66-200">**Fastest** .</span></span> <span data-ttu-id="0ec66-201">Verwenden Sie die schnellste Komprimierungs Methode, um die Verarbeitungszeit zu verkürzen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-201">Use the fastest compression method available to reduce processing time.</span></span> <span data-ttu-id="0ec66-202">Eine schnellere Komprimierung kann zu größeren Dateigrößen führen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-202">Faster compression can result in larger file sizes.</span></span>
- <span data-ttu-id="0ec66-203">**NoCompression** .</span><span class="sxs-lookup"><span data-stu-id="0ec66-203">**NoCompression** .</span></span> <span data-ttu-id="0ec66-204">Die Quelldateien werden nicht komprimiert.</span><span class="sxs-lookup"><span data-stu-id="0ec66-204">Doesn't compress the source files.</span></span>
- <span data-ttu-id="0ec66-205">**Optimal** .</span><span class="sxs-lookup"><span data-stu-id="0ec66-205">**Optimal** .</span></span> <span data-ttu-id="0ec66-206">Die Verarbeitungszeit hängt von der Dateigröße ab.</span><span class="sxs-lookup"><span data-stu-id="0ec66-206">Processing time is dependent on file size.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Optimal, NoCompression, Fastest

Required: False
Position: Named
Default value: Optimal
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ec66-207">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0ec66-207">-Confirm</span></span>

<span data-ttu-id="0ec66-208">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="0ec66-208">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0ec66-209">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="0ec66-209">-DestinationPath</span></span>

<span data-ttu-id="0ec66-210">Dieser Parameter ist erforderlich und gibt den Pfad zur Archiv Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="0ec66-210">This parameter is required and specifies the path to the archive output file.</span></span> <span data-ttu-id="0ec66-211">Der **DestinationPath** muss den Namen der gezippten Datei und entweder den absoluten oder relativen Pfad zur ZIP-Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="0ec66-211">The **DestinationPath** should include the name of the zipped file, and either the absolute or relative path to the zipped file.</span></span>

<span data-ttu-id="0ec66-212">Wenn der Dateiname in **DestinationPath** keine `.zip` Dateinamenerweiterung hat, fügt das Cmdlet die `.zip` Dateinamenerweiterung hinzu.</span><span class="sxs-lookup"><span data-stu-id="0ec66-212">If the file name in **DestinationPath** doesn't have a `.zip` file name extension, the cmdlet adds the `.zip` file name extension.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ec66-213">-Force</span><span class="sxs-lookup"><span data-stu-id="0ec66-213">-Force</span></span>

<span data-ttu-id="0ec66-214">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0ec66-214">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithForce, LiteralPathWithForce
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ec66-215">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="0ec66-215">-LiteralPath</span></span>

<span data-ttu-id="0ec66-216">Gibt den Pfad oder die Pfade zu den Dateien an, die Sie der gezippten ZIP-Datei hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="0ec66-216">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="0ec66-217">Im Gegensatz zum **path** -Parameter wird der Wert von **literalpath** genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0ec66-217">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="0ec66-218">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="0ec66-218">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0ec66-219">Wenn der Pfad Escapezeichen enthält, schließen Sie jedes Escapezeichen in einfache Anführungszeichen ein, um PowerShell anzuweisen, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="0ec66-219">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>
<span data-ttu-id="0ec66-220">Wenn Sie mehrere Pfade angeben und Dateien an mehreren Speicherorten in der ZIP-Ausgabedatei einschließen möchten, trennen Sie die Pfade durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="0ec66-220">To specify multiple paths, and include files in multiple locations in your output zipped file, use commas to separate the paths.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPathWithUpdate, LiteralPathWithForce, LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0ec66-221">-PassThru</span><span class="sxs-lookup"><span data-stu-id="0ec66-221">-PassThru</span></span>

<span data-ttu-id="0ec66-222">Bewirkt, dass das Cmdlet ein Datei Objekt ausgibt, das die erstellte Archivdatei darstellt.</span><span class="sxs-lookup"><span data-stu-id="0ec66-222">Causes the cmdlet to output a file object representing the archive file created.</span></span>

<span data-ttu-id="0ec66-223">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="0ec66-223">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="0ec66-224">-Path</span><span class="sxs-lookup"><span data-stu-id="0ec66-224">-Path</span></span>

<span data-ttu-id="0ec66-225">Gibt den Pfad oder die Pfade zu den Dateien an, die Sie der gezippten ZIP-Datei hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="0ec66-225">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="0ec66-226">Wenn Sie mehrere Pfade angeben und Dateien an mehreren Speicherorten einschließen möchten, verwenden Sie Kommas, um die Pfade voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-226">To specify multiple paths, and include files in multiple locations, use commas to separate the paths.</span></span>

<span data-ttu-id="0ec66-227">Dieser Parameter akzeptiert Platzhalter Zeichen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-227">This parameter accepts wildcard characters.</span></span> <span data-ttu-id="0ec66-228">Mit Platzhalter Zeichen können Sie Ihrer Archivdatei alle Dateien in einem Verzeichnis hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-228">Wildcard characters allow you to add all files in a directory to your archive file.</span></span>

<span data-ttu-id="0ec66-229">Die Verwendung von Platzhaltern mit einem Stammverzeichnis wirkt sich auf den Inhalt des Archivs aus:</span><span class="sxs-lookup"><span data-stu-id="0ec66-229">Using wildcards with a root directory affects the archive's contents:</span></span>

- <span data-ttu-id="0ec66-230">Um ein Archiv zu erstellen, das das Stammverzeichnis und alle zugehörigen Dateien und Unterverzeichnisse **enthält** , geben Sie das Stammverzeichnis im **Pfad** ohne Platzhalter an.</span><span class="sxs-lookup"><span data-stu-id="0ec66-230">To create an archive that **includes** the root directory, and all its files and subdirectories, specify the root directory in the **Path** without wildcards.</span></span> <span data-ttu-id="0ec66-231">Beispiel: `-Path C:\Reference`</span><span class="sxs-lookup"><span data-stu-id="0ec66-231">For example: `-Path C:\Reference`</span></span>
- <span data-ttu-id="0ec66-232">Um ein Archiv zu erstellen, das das Stammverzeichnis **ausschließt** , aber alle Dateien und Unterverzeichnisse zippt, verwenden Sie das Platzhalter Zeichen ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="0ec66-232">To create an archive that **excludes** the root directory, but zips all its files and subdirectories, use the asterisk (`*`) wildcard.</span></span> <span data-ttu-id="0ec66-233">Beispiel: `-Path C:\Reference\*`</span><span class="sxs-lookup"><span data-stu-id="0ec66-233">For example: `-Path C:\Reference\*`</span></span>
- <span data-ttu-id="0ec66-234">Um ein Archiv zu erstellen, das nur die Dateien im Stammverzeichnis zippt, verwenden Sie den Platzhalter **Star-dot-Star** ( `*.*` ).</span><span class="sxs-lookup"><span data-stu-id="0ec66-234">To create an archive that only zips the files in the root directory, use the **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="0ec66-235">Unterverzeichnisse des Stamms sind nicht im Archiv enthalten.</span><span class="sxs-lookup"><span data-stu-id="0ec66-235">Subdirectories of the root aren't included in the archive.</span></span> <span data-ttu-id="0ec66-236">Beispiel: `-Path C:\Reference\*.*`</span><span class="sxs-lookup"><span data-stu-id="0ec66-236">For example: `-Path C:\Reference\*.*`</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path, PathWithUpdate, PathWithForce
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="0ec66-237">-Aktualisieren</span><span class="sxs-lookup"><span data-stu-id="0ec66-237">-Update</span></span>

<span data-ttu-id="0ec66-238">Aktualisiert das angegebene Archiv, indem ältere Dateiversionen im Archiv durch neuere Dateiversionen ersetzt werden, die die gleichen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-238">Updates the specified archive by replacing older file versions in the archive with newer file versions that have the same names.</span></span> <span data-ttu-id="0ec66-239">Sie können diesen Parameter auch hinzufügen, um einem vorhandenen Archivdateien hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0ec66-239">You can also add this parameter to add files to an existing archive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithUpdate, LiteralPathWithUpdate
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ec66-240">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0ec66-240">-WhatIf</span></span>

<span data-ttu-id="0ec66-241">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0ec66-241">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0ec66-242">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0ec66-242">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="0ec66-243">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0ec66-243">CommonParameters</span></span>

<span data-ttu-id="0ec66-244">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0ec66-244">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0ec66-245">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0ec66-245">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0ec66-246">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0ec66-246">INPUTS</span></span>

### <span data-ttu-id="0ec66-247">System.String</span><span class="sxs-lookup"><span data-stu-id="0ec66-247">System.String</span></span>

<span data-ttu-id="0ec66-248">Sie können eine Zeichenfolge, die einen Pfad enthält, über die Pipeline an eine oder mehrere Dateien übergeben.</span><span class="sxs-lookup"><span data-stu-id="0ec66-248">You can pipe a string that contains a path to one or more files.</span></span>

## <span data-ttu-id="0ec66-249">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0ec66-249">OUTPUTS</span></span>

### <span data-ttu-id="0ec66-250">System. IO. fileingefo</span><span class="sxs-lookup"><span data-stu-id="0ec66-250">System.IO.FileInfo</span></span>

<span data-ttu-id="0ec66-251">Das Cmdlet gibt nur ein **FileInfo** -Objekt zurück, wenn Sie den **passthru** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ec66-251">The cmdlet only returns a **FileInfo** object when you use the **PassThru** parameter.</span></span>

## <span data-ttu-id="0ec66-252">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0ec66-252">NOTES</span></span>

<span data-ttu-id="0ec66-253">Durch die Verwendung von Rekursion und das Senden von Objekten in der Pipeline können Dateien im Archiv dupliziert werden.</span><span class="sxs-lookup"><span data-stu-id="0ec66-253">Using recursion and sending objects down the pipeline can duplicate files in your archive.</span></span> <span data-ttu-id="0ec66-254">Wenn Sie z. b. `Get-ChildItem` mit dem **recurse** -Parameter verwenden, werden alle **FileInfo** -und **DirectoryInfo** -Objekte, die über die Pipeline gesendet werden, dem Archiv hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0ec66-254">For example, if you use `Get-ChildItem` with the **Recurse** parameter, each **FileInfo** and **DirectoryInfo** object that's sent down the pipeline is added to the archive.</span></span>

<span data-ttu-id="0ec66-255">Die [ZIP-Datei Spezifikation](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) gibt keine Standardmethode zum Codieren von Dateinamen an, die nicht-ASCII-Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0ec66-255">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="0ec66-256">Das `Compress-Archive` Cmdlet verwendet UTF-8-Codierung.</span><span class="sxs-lookup"><span data-stu-id="0ec66-256">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="0ec66-257">Andere ZIP-Archiv Tools verwenden möglicherweise ein anderes Codierungsschema.</span><span class="sxs-lookup"><span data-stu-id="0ec66-257">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="0ec66-258">Beim Extrahieren von Dateien mit Dateinamen, die nicht mit UTF-8-Codierung gespeichert werden, `Expand-Archive` verwendet den im Archiv gefundenen Rohwert.</span><span class="sxs-lookup"><span data-stu-id="0ec66-258">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="0ec66-259">Dies kann zu einem Dateinamen führen, der sich von dem im Archiv gespeicherten Quell Dateinamen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="0ec66-259">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="0ec66-260">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0ec66-260">RELATED LINKS</span></span>

[<span data-ttu-id="0ec66-261">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="0ec66-261">Expand-Archive</span></span>](Expand-Archive.md)

[<span data-ttu-id="0ec66-262">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="0ec66-262">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)
