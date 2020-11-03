---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 291ec8f3a3958aa726fafb8032b996296272a21e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212567"
---
# <span data-ttu-id="a71bf-103">Add-Content</span><span class="sxs-lookup"><span data-stu-id="a71bf-103">Add-Content</span></span>

## <span data-ttu-id="a71bf-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a71bf-104">SYNOPSIS</span></span>
<span data-ttu-id="a71bf-105">Fügt den angegebenen Elementen Inhalt hinzu, z. B. Hinzufügen von Wörtern in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="a71bf-105">Adds content to the specified items, such as adding words to a file.</span></span>

## <span data-ttu-id="a71bf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a71bf-106">SYNTAX</span></span>

### <span data-ttu-id="a71bf-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="a71bf-107">Path (Default)</span></span>

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="a71bf-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a71bf-108">LiteralPath</span></span>

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="a71bf-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a71bf-109">DESCRIPTION</span></span>

<span data-ttu-id="a71bf-110">Das- `Add-Content` Cmdlet fügt Inhalt an ein angegebenes Element oder eine angegebene Datei an.</span><span class="sxs-lookup"><span data-stu-id="a71bf-110">The `Add-Content` cmdlet appends content to a specified item or file.</span></span> <span data-ttu-id="a71bf-111">Sie können den Inhalt angeben, indem Sie den Inhalt im Befehl eingeben oder ein Objekt angeben, das den Inhalt enthält.</span><span class="sxs-lookup"><span data-stu-id="a71bf-111">You can specify the content by typing the content in the command or by specifying an object that contains the content.</span></span>

<span data-ttu-id="a71bf-112">Wenn Sie für die folgenden Beispiele Dateien oder Verzeichnisse erstellen müssen, finden Sie weitere Informationen unter [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="a71bf-112">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="a71bf-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a71bf-113">EXAMPLES</span></span>

### <span data-ttu-id="a71bf-114">Beispiel 1: Hinzufügen einer Zeichenfolge zu allen Textdateien mit einer Ausnahme</span><span class="sxs-lookup"><span data-stu-id="a71bf-114">Example 1: Add a string to all text files with an exception</span></span>

<span data-ttu-id="a71bf-115">In diesem Beispiel wird ein Wert an Textdateien im aktuellen Verzeichnis angehängt, die Dateien werden jedoch nicht auf Grundlage ihres Datei namens ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a71bf-115">This example appends a value to text files in the current directory but excludes files based on their file name.</span></span>

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

<span data-ttu-id="a71bf-116">Der **path** -Parameter gibt alle `.txt` Dateien im aktuellen Verzeichnis an, aber der **Exclude** -Parameter ignoriert Dateinamen, die dem angegebenen Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a71bf-116">The **Path** parameter specifies all `.txt` files in the current directory, but the **Exclude** parameter ignores file names that match the specified pattern.</span></span> <span data-ttu-id="a71bf-117">Der **value** -Parameter gibt die Text Zeichenfolge an, die in die Dateien geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="a71bf-117">The **Value** parameter specifies the text string that is written to the files.</span></span>

### <span data-ttu-id="a71bf-118">Beispiel 2: Hinzufügen eines Datums am Ende der angegebenen Dateien</span><span class="sxs-lookup"><span data-stu-id="a71bf-118">Example 2: Add a date to the end of the specified files</span></span>

<span data-ttu-id="a71bf-119">In diesem Beispiel wird das Datum an Dateien im aktuellen Verzeichnis angehängt, und das Datum wird in der PowerShell-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-119">This example appends the date to files in the current directory and displays the date in the PowerShell console.</span></span>

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

```Output
Tuesday, May 14, 2019 8:24:27 AM
Tuesday, May 14, 2019 8:24:27 AM
5/14/2019 8:24:27 AM
```

<span data-ttu-id="a71bf-120">Mit dem- `Add-Content` Cmdlet werden zwei neue Dateien im aktuellen Verzeichnis erstellt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-120">The `Add-Content` cmdlet creates two new files in the current directory.</span></span> <span data-ttu-id="a71bf-121">Der **value** -Parameter enthält die Ausgabe des `Get-Date` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a71bf-121">The **Value** parameter contains the output of the `Get-Date` cmdlet.</span></span> <span data-ttu-id="a71bf-122">Der **passthru** -Parameter gibt den hinzugefügten Inhalt an die Pipeline aus.</span><span class="sxs-lookup"><span data-stu-id="a71bf-122">The **PassThru** parameter outputs the added contents to the pipeline.</span></span>
<span data-ttu-id="a71bf-123">Da kein anderes Cmdlet zum Empfangen der Ausgabe vorhanden ist, wird es in der PowerShell-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-123">Because there is no other cmdlet to receive the output, it is displayed in the PowerShell console.</span></span>
<span data-ttu-id="a71bf-124">Das- `Get-Content` Cmdlet zeigt die aktualisierte Datei an `DateTimeFile1.log` .</span><span class="sxs-lookup"><span data-stu-id="a71bf-124">The `Get-Content` cmdlet displays the updated file, `DateTimeFile1.log`.</span></span>

### <span data-ttu-id="a71bf-125">Beispiel 3: Hinzufügen des Inhalts einer angegebenen Datei zu einer anderen Datei</span><span class="sxs-lookup"><span data-stu-id="a71bf-125">Example 3: Add the contents of a specified file to another file</span></span>

<span data-ttu-id="a71bf-126">In diesem Beispiel wird der Inhalt aus einer Datei abgerufen und der Inhalt in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a71bf-126">This example gets the content from a file and stores the content in a variable.</span></span> <span data-ttu-id="a71bf-127">Die-Variable wird verwendet, um den Inhalt an eine andere Datei anzufügen.</span><span class="sxs-lookup"><span data-stu-id="a71bf-127">The variable is used to append the content into another file.</span></span>

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

- <span data-ttu-id="a71bf-128">Mit dem `Get-Content` -Cmdlet wird der Inhalt von abgerufen `CopyFromFile.txt` und der Inhalt in der `$From` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a71bf-128">The `Get-Content` cmdlet gets the contents of `CopyFromFile.txt` and stores the contents in the `$From` variable.</span></span>
- <span data-ttu-id="a71bf-129">Das `Add-Content` Cmdlet aktualisiert die `CopyToFile.txt` Datei mit dem Inhalt der `$From` Variablen.</span><span class="sxs-lookup"><span data-stu-id="a71bf-129">The `Add-Content` cmdlet updates the `CopyToFile.txt` file using the contents of the `$From` variable.</span></span>
- <span data-ttu-id="a71bf-130">Das- `Get-Content` Cmdlet zeigt CopyToFile.txt an.</span><span class="sxs-lookup"><span data-stu-id="a71bf-130">The `Get-Content` cmdlet displays CopyToFile.txt.</span></span>

### <span data-ttu-id="a71bf-131">Beispiel 4: Hinzufügen des Inhalts einer angegebenen Datei in eine andere Datei mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="a71bf-131">Example 4: Add the contents of a specified file to another file using the pipeline</span></span>

<span data-ttu-id="a71bf-132">In diesem Beispiel wird der Inhalt aus einer Datei abgerufen und an das `Add-Content` Cmdlet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a71bf-132">This example gets the content from a file and pipes it to the `Add-Content` cmdlet.</span></span>

```powershell
Get-Content -Path .\CopyFromFile.txt | Add-Content -Path .\CopyToFile.txt
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="a71bf-133">Mit dem- `Get-Content` Cmdlet wird der Inhalt von abgerufen `CopyFromFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="a71bf-133">The `Get-Content` cmdlet gets the contents of `CopyFromFile.txt`.</span></span> <span data-ttu-id="a71bf-134">Die Ergebnisse werden an das- `Add-Content` Cmdlet weitergeleitet, das aktualisiert `CopyToFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="a71bf-134">The results are piped to the `Add-Content` cmdlet, which updates the `CopyToFile.txt`.</span></span>
<span data-ttu-id="a71bf-135">Das letzte `Get-Content` Cmdlet wird angezeigt `CopyToFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="a71bf-135">The last `Get-Content` cmdlet displays `CopyToFile.txt`.</span></span>

### <span data-ttu-id="a71bf-136">Beispiel 5: Erstellen einer neuen Datei und Kopieren von Inhalten</span><span class="sxs-lookup"><span data-stu-id="a71bf-136">Example 5: Create a new file and copy content</span></span>

<span data-ttu-id="a71bf-137">In diesem Beispiel wird eine neue Datei erstellt und der Inhalt einer vorhandenen Datei in die neue Datei kopiert.</span><span class="sxs-lookup"><span data-stu-id="a71bf-137">This example creates a new file and copies an existing file's content into the new file.</span></span>

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

- <span data-ttu-id="a71bf-138">Das `Add-Content` Cmdlet verwendet die **path** -und **value** -Parameter, um eine neue Datei im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a71bf-138">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create a new file in the current directory.</span></span>
- <span data-ttu-id="a71bf-139">`Get-Content`Mit dem-Cmdlet wird der Inhalt einer vorhandenen Datei abgerufen `CopyFromFile.txt` und an den **value** -Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="a71bf-139">The `Get-Content` cmdlet gets the contents of an existing file, `CopyFromFile.txt` and passes it to the **Value** parameter.</span></span> <span data-ttu-id="a71bf-140">Die Klammern um das `Get-Content` Cmdlet stellen sicher, dass der Befehl abgeschlossen ist, bevor der `Add-Content` Befehl beginnt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-140">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span>
- <span data-ttu-id="a71bf-141">Das- `Get-Content` Cmdlet zeigt den Inhalt der neuen Datei an `NewFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="a71bf-141">The `Get-Content` cmdlet displays the contents of the new file, `NewFile.txt`.</span></span>

### <span data-ttu-id="a71bf-142">Beispiel 6: Hinzufügen von Inhalt zu einer schreibgeschützten Datei</span><span class="sxs-lookup"><span data-stu-id="a71bf-142">Example 6: Add content to a read-only file</span></span>

<span data-ttu-id="a71bf-143">Mit diesem Befehl wird der Datei ein Wert hinzugefügt, auch wenn das Attribut " **isread only** " auf " **true** " festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a71bf-143">This command adds a value to the file even if the **IsReadOnly** file attribute is set to **True** .</span></span>
<span data-ttu-id="a71bf-144">Die Schritte zum Erstellen einer schreibgeschützten Datei sind im Beispiel enthalten.</span><span class="sxs-lookup"><span data-stu-id="a71bf-144">The steps to create a read-only file are included in the example.</span></span>

```powershell
New-Item -Path .\IsReadOnlyTextFile.txt -ItemType File
Set-ItemProperty -Path .\IsReadOnlyTextFile.txt -Name IsReadOnly -Value $True
Get-ChildItem -Path .\IsReadOnlyTextFile.txt
Add-Content -Path .\IsReadOnlyTextFile.txt -Value 'Add value to read-only text file' -Force
Get-Content -Path .\IsReadOnlyTextFile.txt
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-ar--         1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

- <span data-ttu-id="a71bf-145">Das `New-Item` Cmdlet verwendet den **path** -Parameter und den **ItemType** -Parameter, um die Datei `IsReadOnlyTextFile.txt` im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a71bf-145">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the file `IsReadOnlyTextFile.txt` in the current directory.</span></span>
- <span data-ttu-id="a71bf-146">Das `Set-ItemProperty` Cmdlet verwendet die Parameter **Name** und **value** , um die **isschreib only** -Eigenschaft der Datei in true zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a71bf-146">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to True.</span></span>
- <span data-ttu-id="a71bf-147">Das `Get-ChildItem` Cmdlet zeigt, dass die Datei leer ist (0) und das schreibgeschützte Attribut ( `r` ) aufweist.</span><span class="sxs-lookup"><span data-stu-id="a71bf-147">The `Get-ChildItem` cmdlet shows the file is empty (0) and has the read-only attribute (`r`).</span></span>
- <span data-ttu-id="a71bf-148">Das `Add-Content` Cmdlet verwendet den **path** -Parameter, um die Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a71bf-148">The `Add-Content` cmdlet uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="a71bf-149">Der **value** -Parameter enthält die Text Zeichenfolge, die an die Datei angefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a71bf-149">The **Value** parameter includes the text string to append to the file.</span></span> <span data-ttu-id="a71bf-150">Mit dem **Force** -Parameter wird der Text in die schreibgeschützte Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="a71bf-150">The **Force** parameter writes the text to the read-only file.</span></span>
- <span data-ttu-id="a71bf-151">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um den Inhalt der Datei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a71bf-151">The `Get-Content` cmdlet uses the **Path** parameter to display the file's contents.</span></span>

<span data-ttu-id="a71bf-152">Um das schreibgeschützte Attribut zu entfernen, verwenden Sie den- `Set-ItemProperty` Befehl, bei dem der **value** -Parameter auf festgelegt ist `False` .</span><span class="sxs-lookup"><span data-stu-id="a71bf-152">To remove the read-only attribute, use the `Set-ItemProperty` command with the **Value** parameter set to `False`.</span></span>

### <span data-ttu-id="a71bf-153">Beispiel 7: Verwenden von Filtern mit Add-Content</span><span class="sxs-lookup"><span data-stu-id="a71bf-153">Example 7: Use Filters with Add-Content</span></span>

<span data-ttu-id="a71bf-154">Sie können einen Filter für das `Add-Content` Cmdlet angeben.</span><span class="sxs-lookup"><span data-stu-id="a71bf-154">You can specify a filter to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="a71bf-155">Wenn Sie den **path** -Parameter mithilfe von Filtern qualifizieren, müssen Sie ein nach gestelltes Sternchen () einfügen, `*` um den Inhalt des Pfads anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a71bf-155">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="a71bf-156">Mit dem folgenden Befehl wird das Wort "Done" zum Inhalt aller `*.txt` Dateien im Verzeichnis hinzugefügt `C:\Temp` .</span><span class="sxs-lookup"><span data-stu-id="a71bf-156">The following command adds the word "Done" the content of all `*.txt` files in the `C:\Temp` directory.</span></span>

```powershell
Add-Content -Path C:\Temp\* -Filter *.txt -Value "Done"
```

## <span data-ttu-id="a71bf-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a71bf-157">PARAMETERS</span></span>

### <span data-ttu-id="a71bf-158">-Asbytestream</span><span class="sxs-lookup"><span data-stu-id="a71bf-158">-AsByteStream</span></span>

<span data-ttu-id="a71bf-159">Gibt an, dass der Inhalt als Byte Datenstrom gelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a71bf-159">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="a71bf-160">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-160">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="a71bf-161">Eine Warnung tritt auf, wenn Sie den **asbytestream** -Parameter mit dem **Encoding** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="a71bf-161">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="a71bf-162">Der **asbytestream** -Parameter ignoriert alle Codierungen, und die Ausgabe wird als Bytestream zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a71bf-162">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="a71bf-163">-Credential</span><span class="sxs-lookup"><span data-stu-id="a71bf-163">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="a71bf-164">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-164">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="a71bf-165">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="a71bf-165">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a71bf-166">-Codierung</span><span class="sxs-lookup"><span data-stu-id="a71bf-166">-Encoding</span></span>

<span data-ttu-id="a71bf-167">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="a71bf-167">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="a71bf-168">Der Standardwert ist `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="a71bf-168">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="a71bf-169">Encoding ist ein dynamischer Parameter, den der File System-Anbieter zum `Add-Content` Cmdlet hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-169">Encoding is a dynamic parameter that the FileSystem provider adds to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="a71bf-170">Dieser Parameter funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="a71bf-170">This parameter works only in file system drives.</span></span>

<span data-ttu-id="a71bf-171">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a71bf-171">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="a71bf-172">`ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="a71bf-172">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="a71bf-173">`bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="a71bf-173">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="a71bf-174">`oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="a71bf-174">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="a71bf-175">`unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="a71bf-175">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="a71bf-176">`utf7`: Codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="a71bf-176">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="a71bf-177">`utf8`: Codiert im UTF-8-Format.</span><span class="sxs-lookup"><span data-stu-id="a71bf-177">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="a71bf-178">`utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="a71bf-178">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="a71bf-179">`utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="a71bf-179">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="a71bf-180">`utf32`: Codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="a71bf-180">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="a71bf-181">Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.).</span><span class="sxs-lookup"><span data-stu-id="a71bf-181">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="a71bf-182">Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="a71bf-182">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a71bf-183">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="a71bf-183">-Exclude</span></span>

<span data-ttu-id="a71bf-184">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="a71bf-184">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="a71bf-185">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="a71bf-185">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a71bf-186">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="a71bf-186">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="a71bf-187">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a71bf-187">Wildcard characters are permitted.</span></span> <span data-ttu-id="a71bf-188">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-188">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="a71bf-189">-Filter</span><span class="sxs-lookup"><span data-stu-id="a71bf-189">-Filter</span></span>

<span data-ttu-id="a71bf-190">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="a71bf-190">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="a71bf-191">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-191">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="a71bf-192">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="a71bf-192">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="a71bf-193">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="a71bf-193">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="a71bf-194">-Force</span><span class="sxs-lookup"><span data-stu-id="a71bf-194">-Force</span></span>

<span data-ttu-id="a71bf-195">Überschreibt das Schreibschutzattribut, sodass Sie einer schreibgeschützten Datei Inhalt hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="a71bf-195">Overrides the read-only attribute, allowing you to add content to a read-only file.</span></span> <span data-ttu-id="a71bf-196">Beispielsweise überschreibt **Force** das Schreibschutzattribut oder erstellt Verzeichnisse zum Vervollständigen eines Dateipfads. Es wird jedoch nicht etwa versucht, Dateiberechtigungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a71bf-196">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="a71bf-197">-Include</span><span class="sxs-lookup"><span data-stu-id="a71bf-197">-Include</span></span>

<span data-ttu-id="a71bf-198">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-198">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="a71bf-199">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="a71bf-199">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a71bf-200">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="a71bf-200">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="a71bf-201">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a71bf-201">Wildcard characters are permitted.</span></span> <span data-ttu-id="a71bf-202">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-202">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="a71bf-203">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="a71bf-203">-LiteralPath</span></span>

<span data-ttu-id="a71bf-204">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="a71bf-204">Specifies a path to one or more locations.</span></span> <span data-ttu-id="a71bf-205">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a71bf-205">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="a71bf-206">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="a71bf-206">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="a71bf-207">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="a71bf-207">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="a71bf-208">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="a71bf-208">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="a71bf-209">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="a71bf-209">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="a71bf-210">-Nonewline</span><span class="sxs-lookup"><span data-stu-id="a71bf-210">-NoNewline</span></span>

<span data-ttu-id="a71bf-211">Gibt an, dass dieses Cmdlet keine neue Zeile oder Wagen Rücklauf zum Inhalt hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-211">Indicates that this cmdlet does not add a new line or carriage return to the content.</span></span>

<span data-ttu-id="a71bf-212">Die Zeichen folgen Darstellungen der Eingabe Objekte werden verkettet, um die Ausgabe zu bilden.</span><span class="sxs-lookup"><span data-stu-id="a71bf-212">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="a71bf-213">Zwischen den Ausgabe Zeichenfolgen werden keine Leerzeichen oder Zeilenumbrüche eingefügt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-213">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="a71bf-214">Nach der letzten Ausgabe Zeichenfolge wird kein Zeilen Vorstrich hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-214">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="a71bf-215">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a71bf-215">-PassThru</span></span>

<span data-ttu-id="a71bf-216">Gibt ein Objekt zurück, das den hinzugefügten Inhalt darstellt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-216">Returns an object representing the added content.</span></span> <span data-ttu-id="a71bf-217">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="a71bf-217">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a71bf-218">-Path</span><span class="sxs-lookup"><span data-stu-id="a71bf-218">-Path</span></span>

<span data-ttu-id="a71bf-219">Gibt den Pfad zu den Elementen an, die den zusätzlichen Inhalt erhalten.</span><span class="sxs-lookup"><span data-stu-id="a71bf-219">Specifies the path to the items that receive the additional content.</span></span>
<span data-ttu-id="a71bf-220">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a71bf-220">Wildcard characters are permitted.</span></span>
<span data-ttu-id="a71bf-221">Die Pfade müssen auf Elemente und nicht auf Container zeigen.</span><span class="sxs-lookup"><span data-stu-id="a71bf-221">The paths must be paths to items, not to containers.</span></span>
<span data-ttu-id="a71bf-222">Sie müssen beispielsweise einen Pfad zu Dateien angeben, ein Pfad zu einem Verzeichnis ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a71bf-222">For example, you must specify a path to one or more files, not a path to a directory.</span></span>
<span data-ttu-id="a71bf-223">Wenn Sie mehrere Pfade angeben, trennen Sie diese durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="a71bf-223">If you specify multiple paths, use commas to separate the paths.</span></span>

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

### <span data-ttu-id="a71bf-224">-Stream</span><span class="sxs-lookup"><span data-stu-id="a71bf-224">-Stream</span></span>

<span data-ttu-id="a71bf-225">Gibt einen alternativen Datenstrom für den Inhalt an.</span><span class="sxs-lookup"><span data-stu-id="a71bf-225">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="a71bf-226">Wenn der Datenstrom nicht vorhanden ist, wird er von diesem Cmdlet erstellt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-226">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="a71bf-227">Platzhalterzeichen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-227">Wildcard characters are not supported.</span></span>

<span data-ttu-id="a71bf-228">**Stream** ist ein dynamischer Parameter, den der File System-Anbieter hinzufügt `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="a71bf-228">**Stream** is a dynamic parameter that the FileSystem provider adds to `Add-Content`.</span></span> <span data-ttu-id="a71bf-229">Dieser Parameter funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="a71bf-229">This parameter works only in file system drives.</span></span>

<span data-ttu-id="a71bf-230">Sie können das `Add-Content` Cmdlet verwenden, um den Inhalt des alternativen Datenstroms " **Zone. Identifier** " zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a71bf-230">You can use the `Add-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="a71bf-231">Dies wird jedoch nicht empfohlen, um Sicherheitsüberprüfungen zu vermeiden, die Dateien blockieren, die aus dem Internet heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="a71bf-231">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="a71bf-232">Wenn Sie überprüfen, ob eine heruntergeladene Datei sicher ist, verwenden Sie das- `Unblock-File` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a71bf-232">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="a71bf-233">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-233">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a71bf-234">-Value</span><span class="sxs-lookup"><span data-stu-id="a71bf-234">-Value</span></span>

<span data-ttu-id="a71bf-235">Gibt den hinzuzufügenden Inhalt an.</span><span class="sxs-lookup"><span data-stu-id="a71bf-235">Specifies the content to be added.</span></span> <span data-ttu-id="a71bf-236">Geben Sie eine Zeichenfolge in Anführungszeichen ein, z. b. **diese Daten sind nur zur internen Verwendung vorgesehen** , oder geben Sie ein Objekt an, das Inhalt enthält, z. b. das **DateTime** -Objekt `Get-Date`</span><span class="sxs-lookup"><span data-stu-id="a71bf-236">Type a quoted string, such as **This data is for internal use only** , or specify an object that contains content, such as the **DateTime** object that `Get-Date` generates.</span></span>

<span data-ttu-id="a71bf-237">Sie können den Inhalt einer Datei nicht angeben, indem Sie Ihren Pfad eingeben, da der Pfad lediglich eine Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="a71bf-237">You cannot specify the contents of a file by typing its path, because the path is just a string.</span></span>
<span data-ttu-id="a71bf-238">Sie können einen `Get-Content` Befehl verwenden, um den Inhalt zu erhalten und an den **value** -Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="a71bf-238">You can use a `Get-Content` command to get the content and pass it to the **Value** parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a71bf-239">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a71bf-239">-Confirm</span></span>

<span data-ttu-id="a71bf-240">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a71bf-240">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a71bf-241">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a71bf-241">-WhatIf</span></span>

<span data-ttu-id="a71bf-242">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a71bf-242">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a71bf-243">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-243">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a71bf-244">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a71bf-244">CommonParameters</span></span>

<span data-ttu-id="a71bf-245">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="a71bf-245">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="a71bf-246">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a71bf-246">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a71bf-247">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a71bf-247">INPUTS</span></span>

### <span data-ttu-id="a71bf-248">System. Object, System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="a71bf-248">System.Object, System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="a71bf-249">Sie können Werte, Pfade oder Anmelde Informationen an übergeben `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="a71bf-249">You can pipe values, paths, or credentials to `Set-Content`.</span></span>

## <span data-ttu-id="a71bf-250">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a71bf-250">OUTPUTS</span></span>

### <span data-ttu-id="a71bf-251">None or System.String</span><span class="sxs-lookup"><span data-stu-id="a71bf-251">None or System.String</span></span>

<span data-ttu-id="a71bf-252">Wenn Sie den **passthru** -Parameter verwenden, `Add-Content` generiert ein **System. String** -Objekt, das den Inhalt darstellt.</span><span class="sxs-lookup"><span data-stu-id="a71bf-252">When you use the **PassThru** parameter, `Add-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="a71bf-253">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="a71bf-253">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a71bf-254">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a71bf-254">NOTES</span></span>

- <span data-ttu-id="a71bf-255">Wenn Sie ein Objekt an übergeben `Add-Content` , wird das Objekt in eine Zeichenfolge konvertiert, bevor es dem Element hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="a71bf-255">When you pipe an object to `Add-Content`, the object is converted to a string before it is added to the item.</span></span> <span data-ttu-id="a71bf-256">Der Objekttyp bestimmt das Zeichenfolgenformat, das Format kann jedoch von der Standardanzeige des Objekts abweichen.</span><span class="sxs-lookup"><span data-stu-id="a71bf-256">The object type determines the string format, but the format might be different than the default display of the object.</span></span> <span data-ttu-id="a71bf-257">Verwenden Sie die Formatierungsparameter des sendenden Cmdlets zum Steuern des Zeichenfolgenformats.</span><span class="sxs-lookup"><span data-stu-id="a71bf-257">To control the string format, use the formatting parameters of the sending cmdlet.</span></span>
- <span data-ttu-id="a71bf-258">Sie können auch auf den `Add-Content` integrierten Alias verweisen `ac` .</span><span class="sxs-lookup"><span data-stu-id="a71bf-258">You can also refer to `Add-Content` by its built-in alias, `ac`.</span></span> <span data-ttu-id="a71bf-259">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="a71bf-259">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="a71bf-260">Das- `Add-Content` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="a71bf-260">The `Add-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="a71bf-261">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="a71bf-261">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="a71bf-262">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="a71bf-262">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="a71bf-263">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a71bf-263">RELATED LINKS</span></span>

[<span data-ttu-id="a71bf-264">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="a71bf-264">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="a71bf-265">about_Providers</span><span class="sxs-lookup"><span data-stu-id="a71bf-265">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="a71bf-266">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="a71bf-266">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="a71bf-267">Get-Content</span><span class="sxs-lookup"><span data-stu-id="a71bf-267">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="a71bf-268">Get-Item</span><span class="sxs-lookup"><span data-stu-id="a71bf-268">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="a71bf-269">New-Item</span><span class="sxs-lookup"><span data-stu-id="a71bf-269">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="a71bf-270">Set-Content</span><span class="sxs-lookup"><span data-stu-id="a71bf-270">Set-Content</span></span>](Set-Content.md)
