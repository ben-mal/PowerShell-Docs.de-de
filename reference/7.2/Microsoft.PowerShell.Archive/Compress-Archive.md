---
external help file: Microsoft.PowerShell.Archive-help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 02/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/compress-archive?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compress-Archive
ms.openlocfilehash: 58807ba0745a6b09e7956547425c489b427d4f4b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601696"
---
# <span data-ttu-id="b5307-102">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="b5307-102">Compress-Archive</span></span>

## <span data-ttu-id="b5307-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b5307-103">SYNOPSIS</span></span>
<span data-ttu-id="b5307-104">Erstellt eine komprimierte oder gezippte Datei aus angegebenen Dateien und Verzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="b5307-104">Creates a compressed archive, or zipped file, from specified files and directories.</span></span>

## <span data-ttu-id="b5307-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b5307-105">SYNTAX</span></span>

### <span data-ttu-id="b5307-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="b5307-106">Path (Default)</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b5307-107">Pathwithupdate</span><span class="sxs-lookup"><span data-stu-id="b5307-107">PathWithUpdate</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Update
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b5307-108">Pathwithforce</span><span class="sxs-lookup"><span data-stu-id="b5307-108">PathWithForce</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Force
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b5307-109">Literalpathwithupdate</span><span class="sxs-lookup"><span data-stu-id="b5307-109">LiteralPathWithUpdate</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Update [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b5307-110">Literalpathwithforce</span><span class="sxs-lookup"><span data-stu-id="b5307-110">LiteralPathWithForce</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Force [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b5307-111">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b5307-111">LiteralPath</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b5307-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b5307-112">DESCRIPTION</span></span>

<span data-ttu-id="b5307-113">Mit dem- `Compress-Archive` Cmdlet wird eine komprimierte oder komprimierte Archivdatei aus einer oder mehreren angegebenen Dateien oder Verzeichnissen erstellt.</span><span class="sxs-lookup"><span data-stu-id="b5307-113">The `Compress-Archive` cmdlet creates a compressed, or zipped, archive file from one or more specified files or directories.</span></span> <span data-ttu-id="b5307-114">Ein Archiv verpackt mehrere Dateien mit optionaler Komprimierung in eine einzelne ZIP-Datei, um die Verteilung und den Speicher zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="b5307-114">An archive packages multiple files, with optional compression, into a single zipped file for easier distribution and storage.</span></span> <span data-ttu-id="b5307-115">Eine Archivdatei kann mithilfe des Komprimierungs Algorithmus komprimiert werden, der durch den **CompressionLevel** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b5307-115">An archive file can be compressed by using the compression algorithm specified by the **CompressionLevel** parameter.</span></span>

<span data-ttu-id="b5307-116">Das `Compress-Archive` Cmdlet verwendet die Microsoft .NET-API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) , um Dateien zu komprimieren.</span><span class="sxs-lookup"><span data-stu-id="b5307-116">The `Compress-Archive` cmdlet uses the Microsoft .NET API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) to compress files.</span></span>
<span data-ttu-id="b5307-117">Die maximale Dateigröße beträgt 2 GB, da die zugrunde liegende API eingeschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="b5307-117">The maximum file size is 2 GB because there's a limitation of the underlying API.</span></span>

<span data-ttu-id="b5307-118">Einige Beispiele verwenden Verteilung, um die Zeilenlänge der Codebeispiele zu verringern.</span><span class="sxs-lookup"><span data-stu-id="b5307-118">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="b5307-119">Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="b5307-119">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="b5307-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b5307-120">EXAMPLES</span></span>

### <span data-ttu-id="b5307-121">Beispiel 1: Komprimieren von Dateien zum Erstellen einer Archivdatei</span><span class="sxs-lookup"><span data-stu-id="b5307-121">Example 1: Compress files to create an archive file</span></span>

<span data-ttu-id="b5307-122">In diesem Beispiel werden Dateien aus unterschiedlichen Verzeichnissen komprimiert, und eine Archivdatei wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="b5307-122">This example compresses files from different directories and creates an archive file.</span></span> <span data-ttu-id="b5307-123">Ein Platzhalter wird verwendet, um alle Dateien mit einer bestimmten Dateierweiterung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b5307-123">A wildcard is used to get all files with a particular file extension.</span></span> <span data-ttu-id="b5307-124">Die Archivdatei enthält keine Verzeichnisstruktur, da der **Pfad** nur Dateinamen angibt.</span><span class="sxs-lookup"><span data-stu-id="b5307-124">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
  Path = "C:\Reference\Draftdoc.docx", "C:\Reference\Images\*.vsd"
  CompressionLevel = "Fastest"
  DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="b5307-125">Der **path** -Parameter akzeptiert bestimmte Dateinamen und Dateinamen mit Platzhaltern `*.vsd` .</span><span class="sxs-lookup"><span data-stu-id="b5307-125">The **Path** parameter accepts specific file names and file names with wildcards, `*.vsd`.</span></span> <span data-ttu-id="b5307-126">Der **Pfad** verwendet eine durch Trennzeichen getrennte Liste, um Dateien aus unterschiedlichen Verzeichnissen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b5307-126">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="b5307-127">Der Komprimierungs Grad ist **am schnellsten** , um die Verarbeitungszeit zu verkürzen.</span><span class="sxs-lookup"><span data-stu-id="b5307-127">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="b5307-128">Der **DestinationPath** -Parameter gibt den Speicherort für die `Draft.zip` Datei an.</span><span class="sxs-lookup"><span data-stu-id="b5307-128">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="b5307-129">Die `Draft.zip` Datei enthält `Draftdoc.docx` und alle Dateien mit einer `.vsd` Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="b5307-129">The `Draft.zip` file contains `Draftdoc.docx` and all the files with a `.vsd` extension.</span></span>

### <span data-ttu-id="b5307-130">Beispiel 2: Komprimieren von Dateien mit einem literalpath</span><span class="sxs-lookup"><span data-stu-id="b5307-130">Example 2: Compress files using a LiteralPath</span></span>

<span data-ttu-id="b5307-131">Dieses Beispiel komprimiert bestimmte benannte Dateien und erstellt eine neue Archivdatei.</span><span class="sxs-lookup"><span data-stu-id="b5307-131">This example compresses specific named files and creates a new archive file.</span></span> <span data-ttu-id="b5307-132">Die Archivdatei enthält keine Verzeichnisstruktur, da der **Pfad** nur Dateinamen angibt.</span><span class="sxs-lookup"><span data-stu-id="b5307-132">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
LiteralPath= "C:\Reference\Draft Doc.docx", "C:\Reference\Images\diagram2.vsd"
CompressionLevel = "Fastest"
DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="b5307-133">Absolute Pfad-und Dateinamen werden verwendet, da der **literalpath** -Parameter keine Platzhalter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="b5307-133">Absolute path and file names are used because the **LiteralPath** parameter doesn't accept wildcards.</span></span> <span data-ttu-id="b5307-134">Der **Pfad** verwendet eine durch Trennzeichen getrennte Liste, um Dateien aus unterschiedlichen Verzeichnissen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b5307-134">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="b5307-135">Der Komprimierungs Grad ist **am schnellsten** , um die Verarbeitungszeit zu verkürzen.</span><span class="sxs-lookup"><span data-stu-id="b5307-135">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="b5307-136">Der **DestinationPath** -Parameter gibt den Speicherort für die `Draft.zip` Datei an.</span><span class="sxs-lookup"><span data-stu-id="b5307-136">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="b5307-137">Die `Draft.zip` Datei enthält nur `Draftdoc.docx` und `diagram2.vsd` .</span><span class="sxs-lookup"><span data-stu-id="b5307-137">The `Draft.zip` file only contains `Draftdoc.docx` and `diagram2.vsd`.</span></span>

### <span data-ttu-id="b5307-138">Beispiel 3: Komprimieren eines Verzeichnisses, das das Stammverzeichnis enthält</span><span class="sxs-lookup"><span data-stu-id="b5307-138">Example 3: Compress a directory that includes the root directory</span></span>

<span data-ttu-id="b5307-139">In diesem Beispiel wird ein Verzeichnis komprimiert und eine Archivdatei erstellt, die das Stammverzeichnis sowie alle zugehörigen Dateien und Unterverzeichnisse **enthält** .</span><span class="sxs-lookup"><span data-stu-id="b5307-139">This example compresses a directory and creates an archive file that **includes** the root directory, and all its files and subdirectories.</span></span> <span data-ttu-id="b5307-140">Die Archivdatei hat eine Verzeichnisstruktur, da der **Pfad** ein Stammverzeichnis angibt.</span><span class="sxs-lookup"><span data-stu-id="b5307-140">The archive file has a directory structure because the **Path** specifies a root directory.</span></span>

```powershell
Compress-Archive -Path C:\Reference -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="b5307-141">`Compress-Archive` verwendet den **path** -Parameter, um das Stammverzeichnis anzugeben `C:\Reference` .</span><span class="sxs-lookup"><span data-stu-id="b5307-141">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference`.</span></span> <span data-ttu-id="b5307-142">Der **DestinationPath** -Parameter gibt den Speicherort für die Archivdatei an.</span><span class="sxs-lookup"><span data-stu-id="b5307-142">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="b5307-143">Das `Draft.zip` Archiv enthält das Stamm `Reference` Verzeichnis und alle zugehörigen Dateien und Unterverzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="b5307-143">The `Draft.zip` archive includes the `Reference` root directory, and all its files and subdirectories.</span></span>

### <span data-ttu-id="b5307-144">Beispiel 4: Komprimieren eines Verzeichnisses, das das Stammverzeichnis ausschließt</span><span class="sxs-lookup"><span data-stu-id="b5307-144">Example 4: Compress a directory that excludes the root directory</span></span>

<span data-ttu-id="b5307-145">In diesem Beispiel wird ein Verzeichnis komprimiert und eine Archivdatei erstellt, die das Stammverzeichnis **ausschließt** , da der **Pfad** ein Sternchen-Platzhalter ( `*` ) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b5307-145">This example compresses a directory and creates an archive file that **excludes** the root directory because the **Path** uses an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="b5307-146">Das Archiv enthält eine Verzeichnisstruktur, die die Dateien und Unterverzeichnisse des Stamm Verzeichnisses enthält.</span><span class="sxs-lookup"><span data-stu-id="b5307-146">The archive contains a directory structure that contains the root directory's files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference\* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="b5307-147">`Compress-Archive` verwendet den **path** -Parameter, um das Stammverzeichnis `C:\Reference` mit einem Platzhalter Zeichen ( `*` ) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b5307-147">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="b5307-148">Der **DestinationPath** -Parameter gibt den Speicherort für die Archivdatei an.</span><span class="sxs-lookup"><span data-stu-id="b5307-148">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="b5307-149">Das `Draft.zip` Archiv enthält die Dateien und Unterverzeichnisse des Stamm Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="b5307-149">The `Draft.zip` archive contains the root directory's files and subdirectories.</span></span> <span data-ttu-id="b5307-150">Das Stamm `Reference` Verzeichnis wird aus dem Archiv ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b5307-150">The `Reference` root directory is excluded from the archive.</span></span>

### <span data-ttu-id="b5307-151">Beispiel 5: komprimieren nur der Dateien in einem Stammverzeichnis</span><span class="sxs-lookup"><span data-stu-id="b5307-151">Example 5: Compress only the files in a root directory</span></span>

<span data-ttu-id="b5307-152">In diesem Beispiel werden nur die Dateien in einem Stammverzeichnis komprimiert, und eine Archivdatei wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="b5307-152">This example compresses only the files in a root directory and creates an archive file.</span></span> <span data-ttu-id="b5307-153">Das Archiv enthält keine Verzeichnisstruktur, da nur Dateien komprimiert werden.</span><span class="sxs-lookup"><span data-stu-id="b5307-153">There's no directory structure in the archive because only files are compressed.</span></span>

```powershell
Compress-Archive -Path C:\Reference\*.* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="b5307-154">`Compress-Archive` verwendet den **path** -Parameter, um das Stammverzeichnis mit einem Platzhalter vom Typ `C:\Reference` **Star-dot-Star** ( `*.*` ) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b5307-154">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with a **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="b5307-155">Der **DestinationPath** -Parameter gibt den Speicherort für die Archivdatei an.</span><span class="sxs-lookup"><span data-stu-id="b5307-155">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="b5307-156">Das `Draft.zip` Archiv enthält nur die `Reference` Dateien des Stamm Verzeichnisses, und das Stammverzeichnis wird ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b5307-156">The `Draft.zip` archive only contains the `Reference` root directory's files and the root directory is excluded.</span></span>

### <span data-ttu-id="b5307-157">Beispiel 6: Verwenden der Pipeline zum Archivieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="b5307-157">Example 6: Use the pipeline to archive files</span></span>

<span data-ttu-id="b5307-158">In diesem Beispiel werden Dateien über die Pipeline gesendet, um ein Archiv zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b5307-158">This example sends files down the pipeline to create an archive.</span></span> <span data-ttu-id="b5307-159">Die Archivdatei enthält keine Verzeichnisstruktur, da der **Pfad** nur Dateinamen angibt.</span><span class="sxs-lookup"><span data-stu-id="b5307-159">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
Get-ChildItem -Path C:\Reference\Afile.txt, C:\Reference\Images\Bfile.txt |
  Compress-Archive -DestinationPath C:\Archives\PipelineFiles.zip
```

<span data-ttu-id="b5307-160">`Get-ChildItem` verwendet den **path** -Parameter, um zwei Dateien aus unterschiedlichen Verzeichnissen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b5307-160">`Get-ChildItem` uses the **Path** parameter to specify two files from different directories.</span></span> <span data-ttu-id="b5307-161">Jede Datei wird durch ein **FileInfo** -Objekt dargestellt und an die Pipeline gesendet `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="b5307-161">Each file is represented by a **FileInfo** object and is sent down the pipeline to `Compress-Archive`.</span></span>
<span data-ttu-id="b5307-162">Die beiden angegebenen Dateien werden in archiviert `PipelineFiles.zip` .</span><span class="sxs-lookup"><span data-stu-id="b5307-162">The two specified files are archived in `PipelineFiles.zip`.</span></span>

### <span data-ttu-id="b5307-163">Beispiel 7: Verwenden der Pipeline zum Archivieren eines Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="b5307-163">Example 7: Use the pipeline to archive a directory</span></span>

<span data-ttu-id="b5307-164">In diesem Beispiel wird ein Verzeichnis nach unten in der Pipeline gesendet, um ein Archiv zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b5307-164">This example sends a directory down the pipeline to create an archive.</span></span> <span data-ttu-id="b5307-165">Dateien werden als **FileInfo** -Objekte und-Verzeichnisse als **DirectoryInfo** -Objekte gesendet.</span><span class="sxs-lookup"><span data-stu-id="b5307-165">Files are sent as **FileInfo** objects and directories as **DirectoryInfo** objects.</span></span> <span data-ttu-id="b5307-166">Die Verzeichnisstruktur des Archivs enthält nicht das Stammverzeichnis, aber seine Dateien und Unterverzeichnisse sind im Archiv enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5307-166">The archive's directory structure doesn't include the root directory, but its files and subdirectories are included in the archive.</span></span>

```powershell
Get-ChildItem -Path C:\LogFiles | Compress-Archive -DestinationPath C:\Archives\PipelineDir.zip
```

<span data-ttu-id="b5307-167">`Get-ChildItem` verwendet den **path** -Parameter, um das Stamm `C:\LogFiles` Verzeichnis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b5307-167">`Get-ChildItem` uses the **Path** parameter to specify the `C:\LogFiles` root directory.</span></span> <span data-ttu-id="b5307-168">Jedes " **FileInfo** "-und " **DirectoryInfo** "-Objekt wird über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="b5307-168">Each **FileInfo** and **DirectoryInfo** object is sent down the pipeline.</span></span>

<span data-ttu-id="b5307-169">`Compress-Archive` Fügt dem Archiv jedes Objekt hinzu `PipelineDir.zip` .</span><span class="sxs-lookup"><span data-stu-id="b5307-169">`Compress-Archive` adds each object to the `PipelineDir.zip` archive.</span></span> <span data-ttu-id="b5307-170">Der **path** -Parameter ist nicht angegeben, da die Pipeline Objekte in der Parameter Position 0 empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="b5307-170">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

### <span data-ttu-id="b5307-171">Beispiel 8: so wirkt sich die Rekursion auf Archive aus</span><span class="sxs-lookup"><span data-stu-id="b5307-171">Example 8: How recursion can affect archives</span></span>

<span data-ttu-id="b5307-172">Dieses Beispiel zeigt, wie die Rekursion Dateien im Archiv duplizieren kann.</span><span class="sxs-lookup"><span data-stu-id="b5307-172">This example shows how recursion can duplicate files in your archive.</span></span> <span data-ttu-id="b5307-173">Wenn Sie z `Get-ChildItem` . b. mit dem **recurse** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5307-173">For example, if you use `Get-ChildItem` with the **Recurse** parameter.</span></span> <span data-ttu-id="b5307-174">Bei Rekursions Prozessen werden alle **FileInfo** -und **DirectoryInfo** -Objekte über die Pipeline gesendet und dem Archiv hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b5307-174">As recursion processes, each **FileInfo** and **DirectoryInfo** object is sent down the pipeline and added to the archive.</span></span>

```powershell
Get-ChildItem -Path C:\TestLog -Recurse |
  Compress-Archive -DestinationPath C:\Archives\PipelineRecurse.zip
```

<span data-ttu-id="b5307-175">Das `C:\TestLog` Verzeichnis enthält keine Dateien.</span><span class="sxs-lookup"><span data-stu-id="b5307-175">The `C:\TestLog` directory doesn't contain any files.</span></span> <span data-ttu-id="b5307-176">Sie enthält ein Unterverzeichnis mit `testsub` dem Namen, das die `testlog.txt` Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="b5307-176">It does contain a subdirectory named `testsub` that contains the `testlog.txt` file.</span></span>

<span data-ttu-id="b5307-177">`Get-ChildItem` verwendet den **path** -Parameter, um das Stammverzeichnis anzugeben `C:\TestLog` .</span><span class="sxs-lookup"><span data-stu-id="b5307-177">`Get-ChildItem` uses the **Path** parameter to specify the root directory, `C:\TestLog`.</span></span> <span data-ttu-id="b5307-178">Der **recurse** -Parameter verarbeitet die Dateien und Verzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="b5307-178">The **Recurse** parameter processes the files and directories.</span></span> <span data-ttu-id="b5307-179">Ein **DirectoryInfo** -Objekt wird für `testsub` und ein **FileInfo** -Objekt erstellt `testlog.txt` .</span><span class="sxs-lookup"><span data-stu-id="b5307-179">A **DirectoryInfo** object is created for `testsub` and a **FileInfo** object `testlog.txt`.</span></span>

<span data-ttu-id="b5307-180">Jedes Objekt wird über die Pipeline an gesendet `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="b5307-180">Each object is sent down the pipeline to `Compress-Archive`.</span></span> <span data-ttu-id="b5307-181">Der **DestinationPath** gibt den Speicherort für die Archivdatei an.</span><span class="sxs-lookup"><span data-stu-id="b5307-181">The **DestinationPath** specifies the location for the archive file.</span></span> <span data-ttu-id="b5307-182">Der **path** -Parameter ist nicht angegeben, da die Pipeline Objekte in der Parameter Position 0 empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="b5307-182">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

<span data-ttu-id="b5307-183">In der folgenden Zusammenfassung werden die `PipelineRecurse.zip` Inhalte des Archivs beschrieben, die eine doppelte Datei enthalten:</span><span class="sxs-lookup"><span data-stu-id="b5307-183">The following summary describes the `PipelineRecurse.zip` archive's contents that contains a duplicate file:</span></span>

- <span data-ttu-id="b5307-184">Das **DirectoryInfo** -Objekt erstellt das `testsub` Verzeichnis und enthält die `testlog.txt` Datei, die die ursprüngliche Verzeichnisstruktur widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="b5307-184">The **DirectoryInfo** object creates the `testsub` directory and contains the `testlog.txt` file, which reflects the original directory structure.</span></span>
- <span data-ttu-id="b5307-185">Das **FileInfo** -Objekt erstellt ein Duplikat `testlog.txt` im Stamm des Archivs.</span><span class="sxs-lookup"><span data-stu-id="b5307-185">The **FileInfo** object creates a duplicate `testlog.txt` in the archive's root.</span></span> <span data-ttu-id="b5307-186">Die doppelte Datei wird erstellt, da die Rekursion ein Datei Objekt an gesendet hat `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="b5307-186">The duplicate file is created because recursion sent a file object to `Compress-Archive`.</span></span> <span data-ttu-id="b5307-187">Dieses Verhalten wird erwartet, da jedes an die Pipeline gesendete Objekt dem Archiv hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b5307-187">This behavior is expected because each object sent down the pipeline is added to the archive.</span></span>

### <span data-ttu-id="b5307-188">Beispiel 9: Aktualisieren einer vorhandenen Archivdatei</span><span class="sxs-lookup"><span data-stu-id="b5307-188">Example 9: Update an existing archive file</span></span>

<span data-ttu-id="b5307-189">In diesem Beispiel wird eine vorhandene Archivdatei, `Draft.Zip` , im `C:\Archives` Verzeichnis aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b5307-189">This example updates an existing archive file, `Draft.Zip`, in the `C:\Archives` directory.</span></span> <span data-ttu-id="b5307-190">In diesem Beispiel enthält die vorhandene Archivdatei das Stammverzeichnis und seine Dateien und Unterverzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="b5307-190">In this example, the existing archive file contains the root directory, and its files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference -Update -DestinationPath C:\Archives\Draft.Zip
```

<span data-ttu-id="b5307-191">Der Befehl wird `Draft.Zip` mit neueren Versionen vorhandener Dateien im `C:\Reference` Verzeichnis und seinen Unterverzeichnissen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b5307-191">The command updates `Draft.Zip` with newer versions of existing files in the `C:\Reference` directory and its subdirectories.</span></span> <span data-ttu-id="b5307-192">Außerdem sind neue Dateien, die bzw. den Unterverzeichnissen hinzugefügt wurden, `C:\Reference` im aktualisierten `Draft.Zip` Archiv enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5307-192">And, new files that were added to `C:\Reference` or its subdirectories are included in the updated `Draft.Zip` archive.</span></span>

## <span data-ttu-id="b5307-193">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b5307-193">PARAMETERS</span></span>

### <span data-ttu-id="b5307-194">-CompressionLevel</span><span class="sxs-lookup"><span data-stu-id="b5307-194">-CompressionLevel</span></span>

<span data-ttu-id="b5307-195">Gibt an, wie viel Komprimierung beim Erstellen der Archivdatei angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b5307-195">Specifies how much compression to apply when you're creating the archive file.</span></span> <span data-ttu-id="b5307-196">Die schnellere Komprimierung erfordert weniger Zeit zum Erstellen der Datei, kann jedoch zu größeren Dateigrößen führen.</span><span class="sxs-lookup"><span data-stu-id="b5307-196">Faster compression requires less time to create the file, but can result in larger file sizes.</span></span>

<span data-ttu-id="b5307-197">Wenn dieser Parameter nicht angegeben wird, verwendet der Befehl den Standardwert, **optimal**.</span><span class="sxs-lookup"><span data-stu-id="b5307-197">If this parameter isn't specified, the command uses the default value, **Optimal**.</span></span>

<span data-ttu-id="b5307-198">Im folgenden sind die zulässigen Werte für diesen Parameter aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="b5307-198">The following are the acceptable values for this parameter:</span></span>

- <span data-ttu-id="b5307-199">**Schnellste**.</span><span class="sxs-lookup"><span data-stu-id="b5307-199">**Fastest**.</span></span> <span data-ttu-id="b5307-200">Verwenden Sie die schnellste Komprimierungs Methode, um die Verarbeitungszeit zu verkürzen.</span><span class="sxs-lookup"><span data-stu-id="b5307-200">Use the fastest compression method available to reduce processing time.</span></span> <span data-ttu-id="b5307-201">Eine schnellere Komprimierung kann zu größeren Dateigrößen führen.</span><span class="sxs-lookup"><span data-stu-id="b5307-201">Faster compression can result in larger file sizes.</span></span>
- <span data-ttu-id="b5307-202">**NoCompression**.</span><span class="sxs-lookup"><span data-stu-id="b5307-202">**NoCompression**.</span></span> <span data-ttu-id="b5307-203">Die Quelldateien werden nicht komprimiert.</span><span class="sxs-lookup"><span data-stu-id="b5307-203">Doesn't compress the source files.</span></span>
- <span data-ttu-id="b5307-204">**Optimal**.</span><span class="sxs-lookup"><span data-stu-id="b5307-204">**Optimal**.</span></span> <span data-ttu-id="b5307-205">Die Verarbeitungszeit hängt von der Dateigröße ab.</span><span class="sxs-lookup"><span data-stu-id="b5307-205">Processing time is dependent on file size.</span></span>

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

### <span data-ttu-id="b5307-206">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b5307-206">-Confirm</span></span>

<span data-ttu-id="b5307-207">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b5307-207">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b5307-208">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="b5307-208">-DestinationPath</span></span>

<span data-ttu-id="b5307-209">Dieser Parameter ist erforderlich und gibt den Pfad zur Archiv Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="b5307-209">This parameter is required and specifies the path to the archive output file.</span></span> <span data-ttu-id="b5307-210">Der **DestinationPath** muss den Namen der gezippten Datei und entweder den absoluten oder relativen Pfad zur ZIP-Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5307-210">The **DestinationPath** should include the name of the zipped file, and either the absolute or relative path to the zipped file.</span></span>

<span data-ttu-id="b5307-211">Wenn der Dateiname in **DestinationPath** keine `.zip` Dateinamenerweiterung hat, fügt das Cmdlet die `.zip` Dateinamenerweiterung hinzu.</span><span class="sxs-lookup"><span data-stu-id="b5307-211">If the file name in **DestinationPath** doesn't have a `.zip` file name extension, the cmdlet adds the `.zip` file name extension.</span></span>

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

### <span data-ttu-id="b5307-212">-Force</span><span class="sxs-lookup"><span data-stu-id="b5307-212">-Force</span></span>

<span data-ttu-id="b5307-213">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b5307-213">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="b5307-214">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="b5307-214">-LiteralPath</span></span>

<span data-ttu-id="b5307-215">Gibt den Pfad oder die Pfade zu den Dateien an, die Sie der gezippten ZIP-Datei hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="b5307-215">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="b5307-216">Im Gegensatz zum **path** -Parameter wird der Wert von **literalpath** genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b5307-216">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="b5307-217">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="b5307-217">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="b5307-218">Wenn der Pfad Escapezeichen enthält, schließen Sie jedes Escapezeichen in einfache Anführungszeichen ein, um PowerShell anzuweisen, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="b5307-218">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>
<span data-ttu-id="b5307-219">Wenn Sie mehrere Pfade angeben und Dateien an mehreren Speicherorten in der ZIP-Ausgabedatei einschließen möchten, trennen Sie die Pfade durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="b5307-219">To specify multiple paths, and include files in multiple locations in your output zipped file, use commas to separate the paths.</span></span>

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

### <span data-ttu-id="b5307-220">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b5307-220">-PassThru</span></span>

<span data-ttu-id="b5307-221">Bewirkt, dass das Cmdlet ein Datei Objekt ausgibt, das die erstellte Archivdatei darstellt.</span><span class="sxs-lookup"><span data-stu-id="b5307-221">Causes the cmdlet to output a file object representing the archive file created.</span></span>

<span data-ttu-id="b5307-222">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b5307-222">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="b5307-223">-Path</span><span class="sxs-lookup"><span data-stu-id="b5307-223">-Path</span></span>

<span data-ttu-id="b5307-224">Gibt den Pfad oder die Pfade zu den Dateien an, die Sie der gezippten ZIP-Datei hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="b5307-224">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="b5307-225">Wenn Sie mehrere Pfade angeben und Dateien an mehreren Speicherorten einschließen möchten, verwenden Sie Kommas, um die Pfade voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="b5307-225">To specify multiple paths, and include files in multiple locations, use commas to separate the paths.</span></span>

<span data-ttu-id="b5307-226">Dieser Parameter akzeptiert Platzhalter Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b5307-226">This parameter accepts wildcard characters.</span></span> <span data-ttu-id="b5307-227">Mit Platzhalter Zeichen können Sie Ihrer Archivdatei alle Dateien in einem Verzeichnis hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b5307-227">Wildcard characters allow you to add all files in a directory to your archive file.</span></span>

<span data-ttu-id="b5307-228">Die Verwendung von Platzhaltern mit einem Stammverzeichnis wirkt sich auf den Inhalt des Archivs aus:</span><span class="sxs-lookup"><span data-stu-id="b5307-228">Using wildcards with a root directory affects the archive's contents:</span></span>

- <span data-ttu-id="b5307-229">Um ein Archiv zu erstellen, das das Stammverzeichnis und alle zugehörigen Dateien und Unterverzeichnisse **enthält** , geben Sie das Stammverzeichnis im **Pfad** ohne Platzhalter an.</span><span class="sxs-lookup"><span data-stu-id="b5307-229">To create an archive that **includes** the root directory, and all its files and subdirectories, specify the root directory in the **Path** without wildcards.</span></span> <span data-ttu-id="b5307-230">Beispiel: `-Path C:\Reference`</span><span class="sxs-lookup"><span data-stu-id="b5307-230">For example: `-Path C:\Reference`</span></span>
- <span data-ttu-id="b5307-231">Um ein Archiv zu erstellen, das das Stammverzeichnis **ausschließt** , aber alle Dateien und Unterverzeichnisse zippt, verwenden Sie das Platzhalter Zeichen ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="b5307-231">To create an archive that **excludes** the root directory, but zips all its files and subdirectories, use the asterisk (`*`) wildcard.</span></span> <span data-ttu-id="b5307-232">Beispiel: `-Path C:\Reference\*`</span><span class="sxs-lookup"><span data-stu-id="b5307-232">For example: `-Path C:\Reference\*`</span></span>
- <span data-ttu-id="b5307-233">Um ein Archiv zu erstellen, das nur die Dateien im Stammverzeichnis zippt, verwenden Sie den Platzhalter **Star-dot-Star** ( `*.*` ).</span><span class="sxs-lookup"><span data-stu-id="b5307-233">To create an archive that only zips the files in the root directory, use the **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="b5307-234">Unterverzeichnisse des Stamms sind nicht im Archiv enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5307-234">Subdirectories of the root aren't included in the archive.</span></span> <span data-ttu-id="b5307-235">Beispiel: `-Path C:\Reference\*.*`</span><span class="sxs-lookup"><span data-stu-id="b5307-235">For example: `-Path C:\Reference\*.*`</span></span>

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

### <span data-ttu-id="b5307-236">-Aktualisieren</span><span class="sxs-lookup"><span data-stu-id="b5307-236">-Update</span></span>

<span data-ttu-id="b5307-237">Aktualisiert das angegebene Archiv, indem ältere Dateiversionen im Archiv durch neuere Dateiversionen ersetzt werden, die die gleichen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b5307-237">Updates the specified archive by replacing older file versions in the archive with newer file versions that have the same names.</span></span> <span data-ttu-id="b5307-238">Sie können diesen Parameter auch hinzufügen, um einem vorhandenen Archivdateien hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b5307-238">You can also add this parameter to add files to an existing archive.</span></span>

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

### <span data-ttu-id="b5307-239">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b5307-239">-WhatIf</span></span>

<span data-ttu-id="b5307-240">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b5307-240">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b5307-241">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b5307-241">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="b5307-242">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b5307-242">CommonParameters</span></span>

<span data-ttu-id="b5307-243">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b5307-243">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b5307-244">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b5307-244">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b5307-245">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b5307-245">INPUTS</span></span>

### <span data-ttu-id="b5307-246">System.String</span><span class="sxs-lookup"><span data-stu-id="b5307-246">System.String</span></span>

<span data-ttu-id="b5307-247">Sie können eine Zeichenfolge, die einen Pfad enthält, über die Pipeline an eine oder mehrere Dateien übergeben.</span><span class="sxs-lookup"><span data-stu-id="b5307-247">You can pipe a string that contains a path to one or more files.</span></span>

## <span data-ttu-id="b5307-248">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b5307-248">OUTPUTS</span></span>

### <span data-ttu-id="b5307-249">System. IO. fileingefo</span><span class="sxs-lookup"><span data-stu-id="b5307-249">System.IO.FileInfo</span></span>

<span data-ttu-id="b5307-250">Das Cmdlet gibt nur ein **FileInfo** -Objekt zurück, wenn Sie den **passthru** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5307-250">The cmdlet only returns a **FileInfo** object when you use the **PassThru** parameter.</span></span>

## <span data-ttu-id="b5307-251">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b5307-251">NOTES</span></span>

<span data-ttu-id="b5307-252">Durch die Verwendung von Rekursion und das Senden von Objekten in der Pipeline können Dateien im Archiv dupliziert werden.</span><span class="sxs-lookup"><span data-stu-id="b5307-252">Using recursion and sending objects down the pipeline can duplicate files in your archive.</span></span> <span data-ttu-id="b5307-253">Wenn Sie z. b. `Get-ChildItem` mit dem **recurse** -Parameter verwenden, werden alle **FileInfo** -und **DirectoryInfo** -Objekte, die über die Pipeline gesendet werden, dem Archiv hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b5307-253">For example, if you use `Get-ChildItem` with the **Recurse** parameter, each **FileInfo** and **DirectoryInfo** object that's sent down the pipeline is added to the archive.</span></span>

<span data-ttu-id="b5307-254">Die [ZIP-Datei Spezifikation](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) gibt keine Standardmethode zum Codieren von Dateinamen an, die nicht-ASCII-Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5307-254">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="b5307-255">Das `Compress-Archive` Cmdlet verwendet UTF-8-Codierung.</span><span class="sxs-lookup"><span data-stu-id="b5307-255">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="b5307-256">Andere ZIP-Archiv Tools verwenden möglicherweise ein anderes Codierungsschema.</span><span class="sxs-lookup"><span data-stu-id="b5307-256">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="b5307-257">Beim Extrahieren von Dateien mit Dateinamen, die nicht mit UTF-8-Codierung gespeichert werden, `Expand-Archive` verwendet den im Archiv gefundenen Rohwert.</span><span class="sxs-lookup"><span data-stu-id="b5307-257">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="b5307-258">Dies kann zu einem Dateinamen führen, der sich von dem im Archiv gespeicherten Quell Dateinamen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="b5307-258">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="b5307-259">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b5307-259">RELATED LINKS</span></span>

[<span data-ttu-id="b5307-260">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="b5307-260">Expand-Archive</span></span>](Expand-Archive.md)

[<span data-ttu-id="b5307-261">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b5307-261">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

