---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-content?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Content
ms.openlocfilehash: b6a8d0f68717849711a794c9482e03d4ea081e1d
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692653"
---
# <span data-ttu-id="37ee2-102">Get-Content</span><span class="sxs-lookup"><span data-stu-id="37ee2-102">Get-Content</span></span>

## <span data-ttu-id="37ee2-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="37ee2-103">SYNOPSIS</span></span>
<span data-ttu-id="37ee2-104">Ruft den Inhalt des Elements am angegebenen Speicherort ab.</span><span class="sxs-lookup"><span data-stu-id="37ee2-104">Gets the content of the item at the specified location.</span></span>

## <span data-ttu-id="37ee2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="37ee2-105">SYNTAX</span></span>

### <span data-ttu-id="37ee2-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="37ee2-106">Path (Default)</span></span>

```
Get-Content [-ReadCount <Int64>] [-TotalCount <Int64>] [-Tail <Int32>] [-Path] <String[]>
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Credential <PSCredential>]
 [-Delimiter <String>] [-Wait] [-Raw] [-Encoding <Encoding>] [-AsByteStream] [-Stream <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="37ee2-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="37ee2-107">LiteralPath</span></span>

```
Get-Content [-ReadCount <Int64>] [-TotalCount <Int64>] [-Tail <Int32>] -LiteralPath <String[]>
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Credential <PSCredential>]
 [-Delimiter <String>] [-Wait] [-Raw] [-Encoding <Encoding>] [-AsByteStream] [-Stream <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="37ee2-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ee2-108">DESCRIPTION</span></span>

<span data-ttu-id="37ee2-109">Mit dem- `Get-Content` Cmdlet wird der Inhalt des Elements an dem durch den Pfad angegebenen Speicherort abgerufen, z. b. der Text in einer Datei oder der Inhalt einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="37ee2-109">The `Get-Content` cmdlet gets the content of the item at the location specified by the path, such as the text in a file or the content of a function.</span></span> <span data-ttu-id="37ee2-110">Bei Dateien wird der Inhalt zeilenweise gelesen und gibt eine Auflistung von-Objekten zurück, die jeweils eine Zeile von Inhalten darstellen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-110">For files, the content is read one line at a time and returns a collection of objects, each of which represents a line of content.</span></span>

<span data-ttu-id="37ee2-111">Ab PowerShell 3,0 `Get-Content` kann auch eine angegebene Anzahl von Zeilen vom Anfang oder Ende eines Elements erhalten.</span><span class="sxs-lookup"><span data-stu-id="37ee2-111">Beginning in PowerShell 3.0, `Get-Content` can also get a specified number of lines from the beginning or end of an item.</span></span>

## <span data-ttu-id="37ee2-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="37ee2-112">EXAMPLES</span></span>

### <span data-ttu-id="37ee2-113">Beispiel 1: erhalten des Inhalts einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="37ee2-113">Example 1: Get the content of a text file</span></span>

<span data-ttu-id="37ee2-114">In diesem Beispiel wird der Inhalt einer Datei im aktuellen Verzeichnis abgerufen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-114">This example gets the content of a file in the current directory.</span></span> <span data-ttu-id="37ee2-115">Die `LineNumbers.txt` Datei enthält 100 Zeilen im Format, d. h. **Zeile X** und wird in mehreren Beispielen verwendet.</span><span class="sxs-lookup"><span data-stu-id="37ee2-115">The `LineNumbers.txt` file contains 100 lines in the format, **This is Line X** and is used in several examples.</span></span>

```powershell
1..100 | ForEach-Object { Add-Content -Path .\LineNumbers.txt -Value "This is line $_." }
Get-Content -Path .\LineNumbers.txt
```

```Output
This is Line 1
This is Line 2
...
This is line 99.
This is line 100.
```

<span data-ttu-id="37ee2-116">Die Array Werte 1-100 werden über die Pipeline an das `ForEach-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="37ee2-116">The array values 1-100 are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="37ee2-117">`ForEach-Object` verwendet einen Skriptblock mit dem- `Add-Content` Cmdlet, um die Datei zu erstellen `LineNumbers.txt` .</span><span class="sxs-lookup"><span data-stu-id="37ee2-117">`ForEach-Object` uses a script block with the `Add-Content` cmdlet to create the `LineNumbers.txt` file.</span></span> <span data-ttu-id="37ee2-118">Die-Variable `$_` stellt die Array Werte dar, wenn jedes Objekt in der Pipeline gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="37ee2-118">The variable `$_` represents the array values as each object is sent down the pipeline.</span></span> <span data-ttu-id="37ee2-119">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei anzugeben, `LineNumbers.txt` und zeigt den Inhalt in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="37ee2-119">The `Get-Content` cmdlet uses the **Path** parameter to specify the `LineNumbers.txt` file and displays the content in the PowerShell console.</span></span>

### <span data-ttu-id="37ee2-120">Beispiel 2: Begrenzen der Anzahl der Zeilen Get-Content die zurückgibt</span><span class="sxs-lookup"><span data-stu-id="37ee2-120">Example 2: Limit the number of lines Get-Content returns</span></span>

<span data-ttu-id="37ee2-121">Mit diesem Befehl werden die ersten fünf Zeilen einer Datei abgerufen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-121">This command gets the first five lines of a file.</span></span> <span data-ttu-id="37ee2-122">Der **Total count** -Parameter wird verwendet, um die ersten fünf Inhalts Zeilen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="37ee2-122">The **TotalCount** parameter is used to gets the first five lines of content.</span></span> <span data-ttu-id="37ee2-123">In diesem Beispiel wird die `LineNumbers.txt` Datei verwendet, die in Beispiel 1 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="37ee2-123">This example uses the `LineNumbers.txt` file that was created in Example 1.</span></span>

```powershell
Get-Content -Path .\LineNumbers.txt -TotalCount 5
```

```Output
This is Line 1
This is Line 2
This is Line 3
This is Line 4
This is Line 5
```

### <span data-ttu-id="37ee2-124">Beispiel 3: beziehen einer bestimmten Inhalts Zeile aus einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="37ee2-124">Example 3: Get a specific line of content from a text file</span></span>

<span data-ttu-id="37ee2-125">Mit diesem Befehl wird eine bestimmte Anzahl von Zeilen aus einer Datei abgerufen, und dann wird nur die letzte Zeile dieses Inhalts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-125">This command gets a specific number of lines from a file and then displays only the last line of that content.</span></span> <span data-ttu-id="37ee2-126">Der **Total count** -Parameter ruft die ersten 25 Inhalts Zeilen ab.</span><span class="sxs-lookup"><span data-stu-id="37ee2-126">The **TotalCount** parameter gets the first 25 lines of content.</span></span> <span data-ttu-id="37ee2-127">In diesem Beispiel wird die `LineNumbers.txt` Datei verwendet, die in Beispiel 1 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="37ee2-127">This example uses the `LineNumbers.txt` file that was created in Example 1.</span></span>

```powershell
(Get-Content -Path .\LineNumbers.txt -TotalCount 25)[-1]
```

```Output
This is Line 25
```

<span data-ttu-id="37ee2-128">Der `Get-Content` Befehl wird in Klammern eingeschlossen, sodass der Befehl abgeschlossen ist, bevor er mit dem nächsten Schritt fortfahren kann.</span><span class="sxs-lookup"><span data-stu-id="37ee2-128">The `Get-Content` command is wrapped in parentheses so that the command completes before going to the next step.</span></span> <span data-ttu-id="37ee2-129">`Get-Content`Gibt ein Array von Zeilen zurück. Dadurch können Sie die Index Notation hinter der Klammer hinzufügen, um eine bestimmte Zeilennummer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-129">`Get-Content`returns an array of lines, this allows you to add the index notation after the parenthesis to retrieve a specific line number.</span></span> <span data-ttu-id="37ee2-130">In diesem Fall gibt der `[-1]` Index den letzten Index im zurückgegebenen Array von 25 abgerufenen Zeilen an.</span><span class="sxs-lookup"><span data-stu-id="37ee2-130">In this case, the `[-1]` index specifies the last index in the returned array of 25 retrieved lines.</span></span>

### <span data-ttu-id="37ee2-131">Beispiel 4: erhalten der letzten Zeile einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="37ee2-131">Example 4: Get the last line of a text file</span></span>

<span data-ttu-id="37ee2-132">Mit diesem Befehl werden die erste Zeile und die letzte Zeile des Inhalts aus einer Datei abgerufen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-132">This command gets the first line and last line of content from a file.</span></span> <span data-ttu-id="37ee2-133">In diesem Beispiel wird die `LineNumbers.txt` Datei verwendet, die in Beispiel 1 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="37ee2-133">This example uses the `LineNumbers.txt` file that was created in Example 1.</span></span>

```powershell
Get-Item -Path .\LineNumbers.txt | Get-Content -Tail 1
```

```Output
This is Line 100
```

<span data-ttu-id="37ee2-134">In diesem Beispiel wird das- `Get-Item` Cmdlet verwendet, um zu veranschaulichen, dass Sie Dateien an den- `Get-Content` Parameter übergeben können.</span><span class="sxs-lookup"><span data-stu-id="37ee2-134">This example uses the `Get-Item` cmdlet to demonstrate that you can pipe files into the `Get-Content` parameter.</span></span> <span data-ttu-id="37ee2-135">Mit dem **Tail** -Parameter wird die letzte Zeile der Datei abgerufen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-135">The **Tail** parameter gets the last line of the file.</span></span> <span data-ttu-id="37ee2-136">Diese Methode ist schneller als das Abrufen aller Zeilen und die Verwendung der `[-1]` Index Notation.</span><span class="sxs-lookup"><span data-stu-id="37ee2-136">This method is faster than retrieving all of the lines and using the `[-1]` index notation.</span></span>

### <span data-ttu-id="37ee2-137">Beispiel 5: erhalten des Inhalts eines alternativen Datenstroms</span><span class="sxs-lookup"><span data-stu-id="37ee2-137">Example 5: Get the content of an alternate data stream</span></span>

<span data-ttu-id="37ee2-138">In diesem Beispiel wird beschrieben, wie der **Stream** -Parameter verwendet wird, um den Inhalt eines alternativen Datenstroms für Dateien zu erhalten, die auf einem Windows NTFS-Volume gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="37ee2-138">This example describes how to use the **Stream** parameter to get the content of an alternate data stream for files stored on a Windows NTFS volume.</span></span> <span data-ttu-id="37ee2-139">In diesem Beispiel wird das- `Set-Content` Cmdlet zum Erstellen von Beispiel Inhalt in einer Datei namens verwendet `Stream.txt` .</span><span class="sxs-lookup"><span data-stu-id="37ee2-139">In this example, the `Set-Content` cmdlet is used to create sample content in a file named `Stream.txt`.</span></span>

```powershell
Set-Content -Path .\Stream.txt -Value 'This is the content of the Stream.txt file'
# Specify a wildcard to the Stream parameter to display all streams of the recently created file.
Get-Item -Path .\Stream.txt -Stream *
```

```Output
PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt::$DATA
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt::$DATA
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : :$DATA
Length        : 44
```

```powershell
# Retrieve the content of the primary, or $DATA stream.
Get-Content -Path .\Stream.txt -Stream $DATA
```

```Output
This is the content of the Stream.txt file
```

```powershell
# Use the Stream parameter of Add-Content to create a new Stream containing sample content.
Add-Content -Path .\Stream.txt -Stream NewStream -Value 'Added a stream named NewStream to Stream.txt'
# Use Get-Item to verify the stream was created.
Get-Item -Path .\Stream.txt -Stream *
```

```Output
PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt::$DATA
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt::$DATA
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : :$DATA
Length        : 44

PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt:NewStream
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt:NewStream
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : NewStream
Length        : 46
```

```powershell
# Retrieve the content of your newly created Stream.
Get-Content -Path .\Stream.txt -Stream NewStream
```

```Output
Added a stream named NewStream to Stream.txt
```

<span data-ttu-id="37ee2-140">Der **Stream** -Parameter ist ein dynamischer Parameter des [File System-Anbieters](../microsoft.powershell.core/about/about_filesystem_provider.md#stream-systemstring).</span><span class="sxs-lookup"><span data-stu-id="37ee2-140">The **Stream** parameter is a dynamic parameter of the [FileSystem provider](../microsoft.powershell.core/about/about_filesystem_provider.md#stream-systemstring).</span></span>
<span data-ttu-id="37ee2-141">Standardmäßig `Get-Content` werden nur Daten aus dem Standard-oder `:$DATA` Stream abgerufen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-141">By default `Get-Content` only retrieves data from the default, or `:$DATA` stream.</span></span> <span data-ttu-id="37ee2-142">**Streams** können zum Speichern ausgeblendeter Daten verwendet werden, wie z. b. Attribute, Sicherheitseinstellungen oder andere Daten.</span><span class="sxs-lookup"><span data-stu-id="37ee2-142">**Streams** can be used to store hidden data such as attributes, security settings, or other data.</span></span> <span data-ttu-id="37ee2-143">Sie können auch in Verzeichnissen gespeichert werden, ohne dass es sich um untergeordnete Elemente handelt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-143">They can also be stored on directories without being child items.</span></span>

### <span data-ttu-id="37ee2-144">Beispiel 6: erhalten von Rohdaten</span><span class="sxs-lookup"><span data-stu-id="37ee2-144">Example 6: Get raw content</span></span>

<span data-ttu-id="37ee2-145">Mit den Befehlen in diesem Beispiel wird der Inhalt einer Datei als eine Zeichenfolge anstelle eines Arrays von Zeichen folgen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-145">The commands in this example get the contents of a file as one string, instead of an array of strings.</span></span> <span data-ttu-id="37ee2-146">Standardmäßig wird der Inhalt **ohne den** unformatierten dynamischen Parameter als Array von Zeichen folgen mit Zeilen Trennzeichen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="37ee2-146">By default, without the **Raw** dynamic parameter, content is returned as an array of newline-delimited strings.</span></span> <span data-ttu-id="37ee2-147">In diesem Beispiel wird die `LineNumbers.txt` Datei verwendet, die im Beispiel erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="37ee2-147">This example uses the `LineNumbers.txt` file that was created in Example</span></span>
1.

```powershell
$raw = Get-Content -Path .\LineNumbers.txt -Raw
$lines = Get-Content -Path .\LineNumbers.txt
Write-Host "Raw contains $($raw.Count) lines."
Write-Host "Lines contains $($lines.Count) lines."
```

```Output
Raw contains 1 lines.
Lines contains 100 lines.
```

### <span data-ttu-id="37ee2-148">Beispiel 7: Verwenden von Filtern mit Get-Content</span><span class="sxs-lookup"><span data-stu-id="37ee2-148">Example 7: Use Filters with Get-Content</span></span>

<span data-ttu-id="37ee2-149">Sie können einen Filter für das `Get-Content` Cmdlet angeben.</span><span class="sxs-lookup"><span data-stu-id="37ee2-149">You can specify a filter to the `Get-Content` cmdlet.</span></span> <span data-ttu-id="37ee2-150">Wenn Sie den **path** -Parameter mithilfe von Filtern qualifizieren, müssen Sie ein nach gestelltes Sternchen () einfügen, `*` um den Inhalt des Pfads anzugeben.</span><span class="sxs-lookup"><span data-stu-id="37ee2-150">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="37ee2-151">Mit dem folgenden Befehl wird der Inhalt aller `*.log` Dateien im `C:\Temp` Verzeichnis abgerufen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-151">The following command gets the content of all `*.log` files in the `C:\Temp` directory.</span></span>

```powershell
Get-Content -Path C:\Temp\* -Filter *.log
```

### <span data-ttu-id="37ee2-152">Beispiel 8: Dateiinhalte als Bytearray</span><span class="sxs-lookup"><span data-stu-id="37ee2-152">Example 8: Get file contents as a byte array</span></span>

<span data-ttu-id="37ee2-153">In diesem Beispiel wird veranschaulicht, wie Sie den Inhalt einer Datei als ein `[byte[]]` einzelnes Objekt als ein einzelnes Objekt erhalten.</span><span class="sxs-lookup"><span data-stu-id="37ee2-153">This example demonstrates how to get the contents of a file as a `[byte[]]` as a single object.</span></span>

```powershell
$byteArray = Get-Content -Path C:\temp\test.txt -AsByteStream -Raw
Get-Member -InputObject $bytearray
```

```Output
   TypeName: System.Byte[]

Name           MemberType            Definition
----           ----------            ----------
Count          AliasProperty         Count = Length
Add            Method                int IList.Add(System.Object value)
```

<span data-ttu-id="37ee2-154">Der erste Befehl verwendet den **asbytestream** -Parameter, um den Stream von Bytes aus der Datei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="37ee2-154">The first command uses the **AsByteStream** parameter to get the stream of bytes from the file.</span></span>
<span data-ttu-id="37ee2-155">Der **RAW** -Parameter stellt sicher, dass die Bytes als zurückgegeben werden `[System.Byte[]]` .</span><span class="sxs-lookup"><span data-stu-id="37ee2-155">The **Raw** parameter ensures that the bytes are returned as a `[System.Byte[]]`.</span></span> <span data-ttu-id="37ee2-156">Wenn der **RAW** -Parameter nicht vorhanden ist, ist der Rückgabewert ein Bytestream, der von PowerShell als interpretiert wird `[System.Object[]]` .</span><span class="sxs-lookup"><span data-stu-id="37ee2-156">If the **Raw** parameter was absent, the return value is a stream of bytes, which is interpreted by PowerShell as `[System.Object[]]`.</span></span>

## <span data-ttu-id="37ee2-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="37ee2-157">PARAMETERS</span></span>

### <span data-ttu-id="37ee2-158">-Path</span><span class="sxs-lookup"><span data-stu-id="37ee2-158">-Path</span></span>

<span data-ttu-id="37ee2-159">Gibt den Pfad zu einem Element an, in dem `Get-Content` der Inhalt abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="37ee2-159">Specifies the path to an item where `Get-Content` gets the content.</span></span> <span data-ttu-id="37ee2-160">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="37ee2-160">Wildcard characters are permitted.</span></span> <span data-ttu-id="37ee2-161">Die Pfade müssen auf Elemente und nicht auf Container zeigen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-161">The paths must be paths to items, not to containers.</span></span> <span data-ttu-id="37ee2-162">Sie müssen beispielsweise einen Pfad zu Dateien angeben, ein Pfad zu einem Verzeichnis ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="37ee2-162">For example, you must specify a path to one or more files, not a path to a directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="37ee2-163">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="37ee2-163">-LiteralPath</span></span>

<span data-ttu-id="37ee2-164">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="37ee2-164">Specifies a path to one or more locations.</span></span> <span data-ttu-id="37ee2-165">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="37ee2-165">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="37ee2-166">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="37ee2-166">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="37ee2-167">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-167">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="37ee2-168">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="37ee2-168">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="37ee2-169">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="37ee2-169">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="37ee2-170">-"-Lesen"</span><span class="sxs-lookup"><span data-stu-id="37ee2-170">-ReadCount</span></span>

<span data-ttu-id="37ee2-171">Gibt an, wie viele Zeilen mit Inhalt gleichzeitig über die Pipeline übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="37ee2-171">Specifies how many lines of content are sent through the pipeline at a time.</span></span> <span data-ttu-id="37ee2-172">Der Standardwert ist 1.</span><span class="sxs-lookup"><span data-stu-id="37ee2-172">The default value is 1.</span></span>
<span data-ttu-id="37ee2-173">Mit dem Wert %%amp;quot;0%%amp;quot; (null) wird der gesamte Inhalt auf einmal übergeben.</span><span class="sxs-lookup"><span data-stu-id="37ee2-173">A value of 0 (zero) sends all of the content at one time.</span></span>

<span data-ttu-id="37ee2-174">Dieser Parameter ändert den angezeigten Inhalt nicht, sondern wirkt sich auf die Zeit aus, die zum Anzeigen des Inhalts benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="37ee2-174">This parameter does not change the content displayed, but it does affect the time it takes to display the content.</span></span> <span data-ttu-id="37ee2-175">Je größer der Wert von **ReadCount** wird, desto länger dauert es, bis die erste Zeile zurückgegeben wird. Die erforderliche Gesamtzeit für den Vorgang hingegen verringert sich.</span><span class="sxs-lookup"><span data-stu-id="37ee2-175">As the value of **ReadCount** increases, the time it takes to return the first line increases, but the total time for the operation decreases.</span></span> <span data-ttu-id="37ee2-176">Dies kann zu einem wahrnehmbaren Unterschied in großen Elementen führen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-176">This can make a perceptible difference in large items.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="37ee2-177">-TotalCount</span><span class="sxs-lookup"><span data-stu-id="37ee2-177">-TotalCount</span></span>

<span data-ttu-id="37ee2-178">Gibt die Anzahl der Zeilen vom Anfang einer Datei oder eines anderen Elements an.</span><span class="sxs-lookup"><span data-stu-id="37ee2-178">Specifies the number of lines from the beginning of a file or other item.</span></span> <span data-ttu-id="37ee2-179">Der Standardwert ist %%amp;quot;-1%%amp;quot; (alle Zeilen).</span><span class="sxs-lookup"><span data-stu-id="37ee2-179">The default is -1 (all lines).</span></span>

<span data-ttu-id="37ee2-180">Sie können den **totalCount** -Parameternamen oder seine Aliase ( **First** oder **Head**) verwenden.</span><span class="sxs-lookup"><span data-stu-id="37ee2-180">You can use the **TotalCount** parameter name or its aliases, **First** or **Head**.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: First, Head

Required: False
Position: Named
Default value: -1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="37ee2-181">-Tail</span><span class="sxs-lookup"><span data-stu-id="37ee2-181">-Tail</span></span>

<span data-ttu-id="37ee2-182">Gibt die Anzahl der Zeilen vom Ende einer Datei oder eines anderen Elements an.</span><span class="sxs-lookup"><span data-stu-id="37ee2-182">Specifies the number of lines from the end of a file or other item.</span></span> <span data-ttu-id="37ee2-183">Sie können den Namen des **Tail** -Parameters oder den zugehörigen Alias **verwenden.**</span><span class="sxs-lookup"><span data-stu-id="37ee2-183">You can use the **Tail** parameter name or its alias, **Last**.</span></span> <span data-ttu-id="37ee2-184">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-184">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Last

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="37ee2-185">-Filter</span><span class="sxs-lookup"><span data-stu-id="37ee2-185">-Filter</span></span>

<span data-ttu-id="37ee2-186">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="37ee2-186">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="37ee2-187">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-187">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="37ee2-188">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="37ee2-188">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="37ee2-189">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="37ee2-189">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="37ee2-190">-Include</span><span class="sxs-lookup"><span data-stu-id="37ee2-190">-Include</span></span>

<span data-ttu-id="37ee2-191">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-191">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="37ee2-192">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="37ee2-192">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="37ee2-193">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="37ee2-193">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="37ee2-194">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="37ee2-194">Wildcard characters are permitted.</span></span> <span data-ttu-id="37ee2-195">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-195">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="37ee2-196">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="37ee2-196">-Exclude</span></span>

<span data-ttu-id="37ee2-197">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="37ee2-197">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span>
<span data-ttu-id="37ee2-198">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="37ee2-198">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="37ee2-199">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="37ee2-199">Enter a path element or pattern, such as `*.txt`.</span></span>
<span data-ttu-id="37ee2-200">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="37ee2-200">Wildcard characters are permitted.</span></span>

<span data-ttu-id="37ee2-201">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-201">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="37ee2-202">-Force</span><span class="sxs-lookup"><span data-stu-id="37ee2-202">-Force</span></span>

<span data-ttu-id="37ee2-203">**Force** überschreibt ein Schreib geschütztes Attribut oder erstellt Verzeichnisse, um einen Dateipfad abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-203">**Force** will override a read-only attribute or create directories to complete a file path.</span></span> <span data-ttu-id="37ee2-204">Der **Force** -Parameter versucht nicht, Dateiberechtigungen zu ändern oder Sicherheitseinschränkungen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="37ee2-204">The **Force** parameter does not attempt to change file permissions or override security restrictions.</span></span>

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

### <span data-ttu-id="37ee2-205">-Credential</span><span class="sxs-lookup"><span data-stu-id="37ee2-205">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="37ee2-206">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-206">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="37ee2-207">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="37ee2-207">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="37ee2-208">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="37ee2-208">-Delimiter</span></span>

<span data-ttu-id="37ee2-209">Gibt das Trennzeichen an, das `Get-Content` von verwendet wird, um die Datei beim Lesen in Objekte aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-209">Specifies the delimiter that `Get-Content` uses to divide the file into objects while it reads.</span></span> <span data-ttu-id="37ee2-210">Der Standardwert ist `\n` , das Zeilenendezeichen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-210">The default is `\n`, the end-of-line character.</span></span> <span data-ttu-id="37ee2-211">Gibt beim Lesen einer Textdatei `Get-Content` eine Auflistung von Zeichen folgen Objekten zurück, die jeweils mit einem Zeilenendezeichen enden.</span><span class="sxs-lookup"><span data-stu-id="37ee2-211">When reading a text file, `Get-Content` returns a collection of string objects, each of which ends with an end-of-line character.</span></span> <span data-ttu-id="37ee2-212">Wenn Sie ein Trennzeichen eingeben, das in der Datei nicht vorhanden ist, `Get-Content` gibt die gesamte Datei als einzelnes, nicht Begrenzungs Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="37ee2-212">When you enter a delimiter that does not exist in the file, `Get-Content` returns the entire file as a single, undelimited object.</span></span>

<span data-ttu-id="37ee2-213">Sie können diesen Parameter verwenden, um eine große Datei in kleinere Dateien aufzuteilen, indem Sie ein Datei Trennzeichen als Trennzeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="37ee2-213">You can use this parameter to split a large file into smaller files by specifying a file separator, as the delimiter.</span></span> <span data-ttu-id="37ee2-214">Das Trennzeichen wird beibehalten (nicht verworfen) und wird das letzte Element in jedem Dateiabschnitt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-214">The delimiter is preserved (not discarded) and becomes the last item in each file section.</span></span>

<span data-ttu-id="37ee2-215">**Delimiter** ist ein dynamischer Parameter, den der **File System** -Anbieter zum `Get-Content` Cmdlet hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-215">**Delimiter** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet.</span></span> <span data-ttu-id="37ee2-216">Dieser Parameter funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="37ee2-216">This parameter works only in file system drives.</span></span>

> [!NOTE]
> <span data-ttu-id="37ee2-217">Wenn der Wert des **Delimiter** -Parameters eine leere Zeichenfolge ist, gibt aktuell `Get-Content` nichts zurück.</span><span class="sxs-lookup"><span data-stu-id="37ee2-217">Currently, when the value of the **Delimiter** parameter is an empty string, `Get-Content` does not return anything.</span></span> <span data-ttu-id="37ee2-218">Dies ist ein bekanntes Problem.</span><span class="sxs-lookup"><span data-stu-id="37ee2-218">This is a known issue.</span></span> <span data-ttu-id="37ee2-219">, Um zu erzwingen, dass `Get-Content` die gesamte Datei als einzelne, nicht durch Trennzeichen getrennte Zeichenfolge zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="37ee2-219">To force `Get-Content` to return the entire file as a single, undelimited string.</span></span> <span data-ttu-id="37ee2-220">Geben Sie einen Wert ein, der in der Datei nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="37ee2-220">Enter a value that does not exist in the file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: End-of-line character
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37ee2-221">-Wait</span><span class="sxs-lookup"><span data-stu-id="37ee2-221">-Wait</span></span>

<span data-ttu-id="37ee2-222">Hält die Datei offen, nachdem alle vorhandenen Zeilen ausgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="37ee2-222">Keeps the file open after all existing lines have been output.</span></span> <span data-ttu-id="37ee2-223">Beim Warten `Get-Content` überprüft die Datei einmal pro Sekunde und gibt ggf. neue Zeilen aus.</span><span class="sxs-lookup"><span data-stu-id="37ee2-223">While waiting, `Get-Content` checks the file once each second and outputs new lines if present.</span></span> <span data-ttu-id="37ee2-224">Sie können den **warte** Vorgang durch Drücken von **STRG + C** unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-224">You can interrupt **Wait** by pressing **CTRL+C**.</span></span> <span data-ttu-id="37ee2-225">Warten wird auch beendet, wenn die Datei gelöscht wird. in diesem Fall wird ein Fehler ohne Abbruch gemeldet.</span><span class="sxs-lookup"><span data-stu-id="37ee2-225">Waiting also ends if the file gets deleted, in which case a non-terminating error is reported.</span></span>

<span data-ttu-id="37ee2-226">**Wait** ist ein dynamischer Parameter, den der File System-Anbieter zum `Get-Content` Cmdlet hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-226">**Wait** is a dynamic parameter that the FileSystem provider adds to the `Get-Content` cmdlet.</span></span> <span data-ttu-id="37ee2-227">Dieser Parameter funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="37ee2-227">This parameter works only in file system drives.</span></span> <span data-ttu-id="37ee2-228">Der **warte** Vorgang kann nicht mit **RAW** kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="37ee2-228">**Wait** cannot be combined with **Raw**.</span></span>

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

### <span data-ttu-id="37ee2-229">-RAW</span><span class="sxs-lookup"><span data-stu-id="37ee2-229">-Raw</span></span>

<span data-ttu-id="37ee2-230">Ignoriert Zeilen Umleitungs Zeichen und gibt den gesamten Inhalt einer Datei in einer Zeichenfolge zurück, wobei die Zeilenumbrüche beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="37ee2-230">Ignores newline characters and returns the entire contents of a file in one string with the newlines preserved.</span></span> <span data-ttu-id="37ee2-231">Standardmäßig werden Zeilen vorzeichenfolgen als Trennzeichen verwendet, um die Eingabe in ein Array von Zeichen folgen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-231">By default, newline characters in a file are used as delimiters to separate the input into an array of strings.</span></span> <span data-ttu-id="37ee2-232">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-232">This parameter was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="37ee2-233">**RAW** ist ein dynamischer Parameter, den der **File** System-Anbieter zum `Get-Content` Cmdlet hinzufügt. dieser Parameter funktioniert nur in Dateisystem Laufwerken.</span><span class="sxs-lookup"><span data-stu-id="37ee2-233">**Raw** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet This parameter works only in file system drives.</span></span>

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

### <span data-ttu-id="37ee2-234">-Codierung</span><span class="sxs-lookup"><span data-stu-id="37ee2-234">-Encoding</span></span>

<span data-ttu-id="37ee2-235">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="37ee2-235">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="37ee2-236">Der Standardwert ist `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="37ee2-236">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="37ee2-237">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="37ee2-237">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="37ee2-238">`ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="37ee2-238">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="37ee2-239">`bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="37ee2-239">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="37ee2-240">`bigendianutf32`: Codiert im UTF-32-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="37ee2-240">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="37ee2-241">`oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="37ee2-241">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="37ee2-242">`unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="37ee2-242">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="37ee2-243">`utf7`: Codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="37ee2-243">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="37ee2-244">`utf8`: Codiert im UTF-8-Format.</span><span class="sxs-lookup"><span data-stu-id="37ee2-244">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="37ee2-245">`utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="37ee2-245">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="37ee2-246">`utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="37ee2-246">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="37ee2-247">`utf32`: Codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="37ee2-247">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="37ee2-248">Encoding ist ein dynamischer Parameter, den der **File System** -Anbieter zum `Get-Content` Cmdlet hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-248">Encoding is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet.</span></span>
<span data-ttu-id="37ee2-249">Dieser Parameter ist nur in Dateisystem Laufwerken verfügbar.</span><span class="sxs-lookup"><span data-stu-id="37ee2-249">This parameter is available only in file system drives.</span></span>

<span data-ttu-id="37ee2-250">Verwenden Sie beim Lesen aus und Schreiben in Binärdateien den **asbytestream** -Parameter und den Wert 0 für den **readCount** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="37ee2-250">When reading from and writing to binary files, use the **AsByteStream** parameter and a value of 0 for the **ReadCount** parameter.</span></span> <span data-ttu-id="37ee2-251">Der **Wert 0** (null) liest die gesamte Datei in einem einzigen Lesevorgang.</span><span class="sxs-lookup"><span data-stu-id="37ee2-251">A **ReadCount** value of 0 reads the entire file in a single read operation.</span></span> <span data-ttu-id="37ee2-252">Der Standardwert von "read **count** ", 1, liest ein Byte in jedem Lesevorgang und konvertiert jedes Byte in ein separates Objekt, das zu Fehlern führt, wenn Sie das `Set-Content` Cmdlet zum Schreiben der Bytes in eine Datei verwenden, es sei denn, Sie verwenden den **asbytestream** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="37ee2-252">The default **ReadCount** value, 1, reads one byte in each read operation and converts each byte into a separate object, which causes errors when you use the `Set-Content` cmdlet to write the bytes to a file unless you use **AsByteStream** parameter.</span></span>

<span data-ttu-id="37ee2-253">Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.).</span><span class="sxs-lookup"><span data-stu-id="37ee2-253">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="37ee2-254">Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="37ee2-254">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="37ee2-255">**UTF-7** _ wird nicht mehr für die Verwendung von empfohlen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-255">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="37ee2-256">In PowerShell 7,1 wird eine Warnung geschrieben, wenn Sie `utf7` für den Parameter "_ \*Encoding\*\*" angeben.</span><span class="sxs-lookup"><span data-stu-id="37ee2-256">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37ee2-257">-Stream</span><span class="sxs-lookup"><span data-stu-id="37ee2-257">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="37ee2-258">Dieser Parameter ist nur unter Windows verfügbar.</span><span class="sxs-lookup"><span data-stu-id="37ee2-258">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="37ee2-259">Ruft die Inhalte des angegebenen alternativen NTFS-Dateidatenstroms aus der Datei ab.</span><span class="sxs-lookup"><span data-stu-id="37ee2-259">Gets the contents of the specified alternate NTFS file stream from the file.</span></span> <span data-ttu-id="37ee2-260">Geben Sie den Namen des Stroms ein.</span><span class="sxs-lookup"><span data-stu-id="37ee2-260">Enter the stream name.</span></span>
<span data-ttu-id="37ee2-261">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-261">Wildcards are not supported.</span></span>

<span data-ttu-id="37ee2-262">**Stream** ist ein dynamischer Parameter, den der **File System** -Anbieter zum `Get-Content` Cmdlet hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-262">**Stream** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet.</span></span>
<span data-ttu-id="37ee2-263">Dieser Parameter funktioniert nur in Dateisystem Laufwerken auf Windows-Systemen.</span><span class="sxs-lookup"><span data-stu-id="37ee2-263">This parameter works only in file system drives on Windows systems.</span></span> <span data-ttu-id="37ee2-264">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-264">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="37ee2-265">-Asbytestream</span><span class="sxs-lookup"><span data-stu-id="37ee2-265">-AsByteStream</span></span>

<span data-ttu-id="37ee2-266">Gibt an, dass der Inhalt als Byte Datenstrom gelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="37ee2-266">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="37ee2-267">Der **asbytestream** -Parameter wurde in Windows PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="37ee2-267">The **AsByteStream** parameter was introduced in Windows PowerShell 6.0.</span></span>

<span data-ttu-id="37ee2-268">Eine Warnung tritt auf, wenn Sie den **asbytestream** -Parameter mit dem **Encoding** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="37ee2-268">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="37ee2-269">Der **asbytestream** -Parameter ignoriert alle Codierungen, und die Ausgabe wird als Bytestream zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="37ee2-269">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="37ee2-270">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="37ee2-270">CommonParameters</span></span>

<span data-ttu-id="37ee2-271">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="37ee2-271">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="37ee2-272">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="37ee2-272">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="37ee2-273">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="37ee2-273">INPUTS</span></span>

### <span data-ttu-id="37ee2-274">System.Int64, System.String[], System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="37ee2-274">System.Int64, System.String[], System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="37ee2-275">Sie können die Anzahl von Lese-, Gesamt-, Pfad-oder Anmelde Informationen an über die Pipeline übergeben `Get-Content` .</span><span class="sxs-lookup"><span data-stu-id="37ee2-275">You can pipe the read count, total count, paths, or credentials to `Get-Content`.</span></span>

## <span data-ttu-id="37ee2-276">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="37ee2-276">OUTPUTS</span></span>

### <span data-ttu-id="37ee2-277">System. Byte, System. String</span><span class="sxs-lookup"><span data-stu-id="37ee2-277">System.Byte, System.String</span></span>

<span data-ttu-id="37ee2-278">`Get-Content` gibt Zeichen folgen oder Bytes zurück.</span><span class="sxs-lookup"><span data-stu-id="37ee2-278">`Get-Content` returns strings or bytes.</span></span> <span data-ttu-id="37ee2-279">Der Ausgabetyp ist abhängig vom Typ des Inhalts, den Sie als Eingabe angeben.</span><span class="sxs-lookup"><span data-stu-id="37ee2-279">The output type depends upon the type of content that you specify as input.</span></span>

## <span data-ttu-id="37ee2-280">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="37ee2-280">NOTES</span></span>

<span data-ttu-id="37ee2-281">Das- `Get-Content` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="37ee2-281">The `Get-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="37ee2-282">Verwenden Sie das-Cmdlet, um die Anbieter in Ihrer Sitzung zu erhalten `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="37ee2-282">To get the providers in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="37ee2-283">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="37ee2-283">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="37ee2-284">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="37ee2-284">RELATED LINKS</span></span>

[<span data-ttu-id="37ee2-285">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="37ee2-285">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="37ee2-286">about_Providers</span><span class="sxs-lookup"><span data-stu-id="37ee2-286">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="37ee2-287">Add-Content</span><span class="sxs-lookup"><span data-stu-id="37ee2-287">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="37ee2-288">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="37ee2-288">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="37ee2-289">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="37ee2-289">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="37ee2-290">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="37ee2-290">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="37ee2-291">Set-Content</span><span class="sxs-lookup"><span data-stu-id="37ee2-291">Set-Content</span></span>](Set-Content.md)
