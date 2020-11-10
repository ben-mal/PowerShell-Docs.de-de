---
description: FileSystem
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_filesystem_provider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: FileSystem-Anbieter
ms.openlocfilehash: 3464dbcbc1a7f357cdbc5368dc7a1e4d21f5ed5e
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387592"
---
# <a name="filesystem-provider"></a><span data-ttu-id="deb3b-104">FileSystem provider</span><span class="sxs-lookup"><span data-stu-id="deb3b-104">FileSystem provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="deb3b-105">Anbietername</span><span class="sxs-lookup"><span data-stu-id="deb3b-105">Provider name</span></span>

<span data-ttu-id="deb3b-106">FileSystem</span><span class="sxs-lookup"><span data-stu-id="deb3b-106">FileSystem</span></span>

## <a name="drives"></a><span data-ttu-id="deb3b-107">Laufwerke</span><span class="sxs-lookup"><span data-stu-id="deb3b-107">Drives</span></span>

<span data-ttu-id="deb3b-108">`C:`, `D:` ...</span><span class="sxs-lookup"><span data-stu-id="deb3b-108">`C:`, `D:` ...</span></span>

## <a name="capabilities"></a><span data-ttu-id="deb3b-109">Funktionen</span><span class="sxs-lookup"><span data-stu-id="deb3b-109">Capabilities</span></span>

<span data-ttu-id="deb3b-110">**Filter** , **Schulter verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="deb3b-110">**Filter** , **ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="deb3b-111">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="deb3b-111">Short description</span></span>

<span data-ttu-id="deb3b-112">Ermöglicht den Zugriff auf Dateien und Verzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="deb3b-112">Provides access to files and directories.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="deb3b-113">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="deb3b-113">Detailed description</span></span>

<span data-ttu-id="deb3b-114">Mit dem PowerShell- **Dateisystem** Anbieter können Sie Dateien und Verzeichnisse in PowerShell erhalten, hinzufügen, ändern, löschen und löschen.</span><span class="sxs-lookup"><span data-stu-id="deb3b-114">The PowerShell **FileSystem** provider lets you get, add, change, clear, and delete files and directories in PowerShell.</span></span>

<span data-ttu-id="deb3b-115">Die **Dateisystem** Laufwerke sind ein hierarchischer Namespace, der die Verzeichnisse und Dateien auf Ihrem Computer enthält.</span><span class="sxs-lookup"><span data-stu-id="deb3b-115">The **FileSystem** drives are a hierarchical namespace containing the directories and files on your computer.</span></span> <span data-ttu-id="deb3b-116">Bei einem **Dateisystem** Laufwerk kann es sich um ein logisches oder ein phsyisches Laufwerk, ein Verzeichnis oder eine zugeordnete Netzwerkfreigabe handeln.</span><span class="sxs-lookup"><span data-stu-id="deb3b-116">A **FileSystem** drive can be a logical or phsyical drive, directory, or mapped network share.</span></span>

<span data-ttu-id="deb3b-117">Der **File System** -Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="deb3b-117">The **FileSystem** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="deb3b-118">Get-Location</span><span class="sxs-lookup"><span data-stu-id="deb3b-118">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="deb3b-119">Set-Location</span><span class="sxs-lookup"><span data-stu-id="deb3b-119">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="deb3b-120">Get-Item</span><span class="sxs-lookup"><span data-stu-id="deb3b-120">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="deb3b-121">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="deb3b-121">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="deb3b-122">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="deb3b-122">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="deb3b-123">Move-Item</span><span class="sxs-lookup"><span data-stu-id="deb3b-123">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="deb3b-124">New-Item</span><span class="sxs-lookup"><span data-stu-id="deb3b-124">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="deb3b-125">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="deb3b-125">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="deb3b-126">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="deb3b-126">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="deb3b-127">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="deb3b-127">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="deb3b-128">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="deb3b-128">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="deb3b-129">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="deb3b-129">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="deb3b-130">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="deb3b-130">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="deb3b-131">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="deb3b-131">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="deb3b-132">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="deb3b-132">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="deb3b-133">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="deb3b-133">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)
- [<span data-ttu-id="deb3b-134">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="deb3b-134">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [<span data-ttu-id="deb3b-135">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="deb3b-135">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="deb3b-136">Von diesem Anbieter verfügbar gemachte Typen</span><span class="sxs-lookup"><span data-stu-id="deb3b-136">Types exposed by this provider</span></span>

<span data-ttu-id="deb3b-137">Dateien sind Instanzen der [System. IO. FileInfo](/dotnet/api/system.io.fileinfo) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="deb3b-137">Files are instances of the [System.IO.FileInfo](/dotnet/api/system.io.fileinfo) class.</span></span>  <span data-ttu-id="deb3b-138">Verzeichnisse sind Instanzen der [System. IO. DirectoryInfo](/dotnet/api/system.io.directoryinfo) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="deb3b-138">Directories are instances of the [System.IO.DirectoryInfo](/dotnet/api/system.io.directoryinfo) class.</span></span>

## <a name="navigating-the-filesystem-drives"></a><span data-ttu-id="deb3b-139">Navigieren in den Dateisystem Laufwerken</span><span class="sxs-lookup"><span data-stu-id="deb3b-139">Navigating the FileSystem drives</span></span>

<span data-ttu-id="deb3b-140">Der **File System** -Anbieter macht seine Datenspeicher verfügbar, indem logische Laufwerke auf dem Computer als PowerShell-Laufwerke dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="deb3b-140">The **FileSystem** provider exposes its data stores by mapping any logical drives on the computer as PowerShell drives.</span></span> <span data-ttu-id="deb3b-141">Wenn Sie mit einem **Dateisystem** Laufwerk arbeiten möchten, können Sie den Speicherort in ein Laufwerk ändern, auf den der Laufwerk Name folgt, gefolgt von einem Doppelpunkt ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="deb3b-141">To work with a **FileSystem** drive you can change your location to a drive uing the drive name followed by a colon (`:`).</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="deb3b-142">Sie können auch mit dem **File System** -Anbieter von jedem anderen PowerShell-Laufwerk aus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="deb3b-142">You can also work with the **FileSystem** provider from any other PowerShell drive.</span></span> <span data-ttu-id="deb3b-143">Um auf eine Datei oder ein Verzeichnis von einem anderen Speicherort zu verweisen, verwenden Sie den Namen des Laufwerks ( `C:` , `D:` ,...) im Pfad.</span><span class="sxs-lookup"><span data-stu-id="deb3b-143">To reference a file or directory from another location, use the drive name (`C:`, `D:`, ...) in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="deb3b-144">PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten.</span><span class="sxs-lookup"><span data-stu-id="deb3b-144">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="deb3b-145">Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="deb3b-145">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="deb3b-146">und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="deb3b-146">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-files-and-directories"></a><span data-ttu-id="deb3b-147">Dateien und Verzeichnisse werden erhalten.</span><span class="sxs-lookup"><span data-stu-id="deb3b-147">Getting files and directories</span></span>

<span data-ttu-id="deb3b-148">Mit dem- `Get-ChildItem` Cmdlet werden alle Dateien und Verzeichnisse an der aktuellen Position zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="deb3b-148">The `Get-ChildItem` cmdlet returns all files and directories in the current location.</span></span> <span data-ttu-id="deb3b-149">Sie können einen anderen Suchpfad angeben und integrierte Parameter verwenden, um die Rekursions Tiefe zu filtern und zu steuern.</span><span class="sxs-lookup"><span data-stu-id="deb3b-149">You can specify a different path to search and use built in parameters to filter and control the recursion depth.</span></span>

```powershell
Get-ChildItem
```

<span data-ttu-id="deb3b-150">Weitere Informationen zur Verwendung von Cmdlets finden Sie unter [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem).</span><span class="sxs-lookup"><span data-stu-id="deb3b-150">To read more about cmdlet usage, see [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem).</span></span>

## <a name="copying-files-and-directories"></a><span data-ttu-id="deb3b-151">Kopieren von Dateien und Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="deb3b-151">Copying files and directories</span></span>

<span data-ttu-id="deb3b-152">`Copy-Item`Mit dem-Cmdlet werden Dateien und Verzeichnisse an einen von Ihnen angegebenen Speicherort kopiert.</span><span class="sxs-lookup"><span data-stu-id="deb3b-152">The `Copy-Item` cmdlet copies files and directories to a location you specify.</span></span>
<span data-ttu-id="deb3b-153">Parameter sind zum Filtern und rekurdieren verfügbar, ähnlich wie `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="deb3b-153">Parameters are available to filter and recurse, similar to `Get-ChildItem`.</span></span>

<span data-ttu-id="deb3b-154">Mit dem folgenden Befehl werden alle Dateien und Verzeichnisse unter dem Pfad "c:\temp \" " in den Ordner "c:\Windows\Temp" kopiert.</span><span class="sxs-lookup"><span data-stu-id="deb3b-154">The following command copies all of the files and directories under the path "C:\temp\" to the folder "C:\Windows\Temp".</span></span>

```powershell
Copy-Item -Path C:\temp\* -Destination C:\Windows\Temp -Recurse -File
```

<span data-ttu-id="deb3b-155">`Copy-Item` überschreibt Dateien im Zielverzeichnis, ohne zur Bestätigung aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="deb3b-155">`Copy-Item` overwrites files in the destination directory without prompting for confirmation.</span></span>

<span data-ttu-id="deb3b-156">Mit diesem Befehl wird die `a.txt` Datei aus dem `C:\a` Verzeichnis in das `C:\a\bb` Verzeichnis kopiert.</span><span class="sxs-lookup"><span data-stu-id="deb3b-156">This command copies the `a.txt` file from the `C:\a` directory to the `C:\a\bb` directory.</span></span>

```powershell
Copy-Item -Path C:\a\a.txt -Destination C:\a\bb\a.txt
```

<span data-ttu-id="deb3b-157">Kopiert alle Verzeichnisse und Dateien im Verzeichnis in `C:\a` das `C:\c` Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="deb3b-157">Copies all the directories and files in the `C:\a` directory to the `C:\c` directory.</span></span> <span data-ttu-id="deb3b-158">Wenn die zu kopierenden Verzeichnisse bereits im Zielverzeichnis vorhanden sind, schlägt der Befehl fehl, es sei denn, Sie geben den Force-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="deb3b-158">If any of the directories to copy already exist in the destination directory, the command will fail unless you specify the Force parameter.</span></span>

```powershell
Copy-Item -Path C:\a\* -Destination C:\c -Recurse
```

<span data-ttu-id="deb3b-159">Weitere Informationen finden Sie unter [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item).</span><span class="sxs-lookup"><span data-stu-id="deb3b-159">For more information, see [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item).</span></span>

## <a name="moving-files-and-directories"></a><span data-ttu-id="deb3b-160">Verschieben von Dateien und Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="deb3b-160">Moving files and directories</span></span>

<span data-ttu-id="deb3b-161">Mit diesem Befehl wird die `c.txt` Datei im `C:\a` Verzeichnis in das `C:\a\aa` Verzeichnis verschoben:</span><span class="sxs-lookup"><span data-stu-id="deb3b-161">This command moves the `c.txt` file in the `C:\a` directory to the `C:\a\aa` directory:</span></span>

```powershell
Move-Item -Path C:\a\c.txt -Destination C:\a\aa
```

<span data-ttu-id="deb3b-162">Der Befehl überschreibt nicht automatisch eine vorhandene Datei, die den gleichen Namen hat.</span><span class="sxs-lookup"><span data-stu-id="deb3b-162">The command will not automatically overwrite an existing file that has the same name.</span></span> <span data-ttu-id="deb3b-163">Um das Cmdlet zu zwingen, eine vorhandene Datei zu überschreiben, geben Sie den Force-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="deb3b-163">To force the cmdlet to overwrite an existing file, specify the Force parameter.</span></span>

<span data-ttu-id="deb3b-164">Ein Verzeichnis kann nicht verschoben werden, wenn das Verzeichnis der aktuelle Speicherort ist.</span><span class="sxs-lookup"><span data-stu-id="deb3b-164">You cannot move a directory when that directory is the current location.</span></span> <span data-ttu-id="deb3b-165">Wenn Sie verwenden, `Move-Item` um das Verzeichnis am aktuellen Speicherort zu verschieben, wird dieser Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="deb3b-165">When you use `Move-Item` to move the directory at the current location, you see this error.</span></span>

```
C:\temp> Move-Item -Path C:\temp\ -Destination C:\Windows\Temp

Move-Item : Cannot move item because the item at 'C:\temp\' is in use.
At line:1 char:1
+ Move-Item C:\temp\ C:\temp2\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Move-Item], PSInvalidOperationException
    + FullyQualifiedErrorId : InvalidOperation,Microsoft.PowerShell.Commands.MoveItemCommand
```

## <a name="managing-file-content"></a><span data-ttu-id="deb3b-166">Verwalten von Dateiinhalten</span><span class="sxs-lookup"><span data-stu-id="deb3b-166">Managing file content</span></span>

### <a name="get-the-content-of-a-file"></a><span data-ttu-id="deb3b-167">Inhalt einer Datei erhalten</span><span class="sxs-lookup"><span data-stu-id="deb3b-167">Get the content of a file</span></span>

<span data-ttu-id="deb3b-168">Mit diesem Befehl wird der Inhalt der Datei "Test.txt" abgerufen und in der-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="deb3b-168">This command gets the contents of the "Test.txt" file and displays them in the console.</span></span>

```powershell
Get-Content -Path Test.txt
```

<span data-ttu-id="deb3b-169">Sie können den Inhalt der Datei an ein anderes Cmdlet leiten.</span><span class="sxs-lookup"><span data-stu-id="deb3b-169">You can pipe the contents of the file to another cmdlet.</span></span> <span data-ttu-id="deb3b-170">Der folgende Befehl liest z. b. den Inhalt der `Test.txt` Datei und stellt diese dann als Eingabe für das [ConvertTo-HTML-](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) Cmdlet bereit:</span><span class="sxs-lookup"><span data-stu-id="deb3b-170">For example, the following command reads the contents of the `Test.txt` file and then supplies them as input to the [ConvertTo-Html](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) cmdlet:</span></span>

```powershell
Get-Content -Path Test.txt | ConvertTo-Html
```

<span data-ttu-id="deb3b-171">Sie können den Inhalt einer Datei auch abrufen, indem Sie den Anbieter Pfad mit dem Dollarzeichen ( `$` ) versehen.</span><span class="sxs-lookup"><span data-stu-id="deb3b-171">You can also retrieve the content of a file by prefixing its provider path with the dollar sign (`$`).</span></span> <span data-ttu-id="deb3b-172">Der Pfad muss in geschweifte Klammern eingeschlossen werden, da Einschränkungen für Variablen benannt werden.</span><span class="sxs-lookup"><span data-stu-id="deb3b-172">The path must be enclosed in curly braces due to variable naming restrictions.</span></span> <span data-ttu-id="deb3b-173">Weitere Informationen finden Sie unter [about_Variables](about_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="deb3b-173">For more information, see [about_Variables](about_Variables.md).</span></span>

```powershell
${C:\Windows\System32\Drivers\etc\hosts}
```

### <a name="add-content-to-a-file"></a><span data-ttu-id="deb3b-174">Hinzufügen von Inhalt zu einer Datei</span><span class="sxs-lookup"><span data-stu-id="deb3b-174">Add content to a file</span></span>

<span data-ttu-id="deb3b-175">Dieser Befehl fügt die Zeichenfolge "Test Content" an die `Test.txt` Datei an:</span><span class="sxs-lookup"><span data-stu-id="deb3b-175">This command appends the "test content" string to the `Test.txt` file:</span></span>

```powershell
Add-Content -Path test.txt -Value "test content"
```

<span data-ttu-id="deb3b-176">Der vorhandene Inhalt in der `Test.txt` Datei wird nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="deb3b-176">The existing content in the `Test.txt` file is not deleted.</span></span>

### <a name="replace-the-content-of-a-file"></a><span data-ttu-id="deb3b-177">Ersetzen des Inhalts einer Datei</span><span class="sxs-lookup"><span data-stu-id="deb3b-177">Replace the content of a file</span></span>

<span data-ttu-id="deb3b-178">Dieser Befehl ersetzt den Inhalt der `Test.txt` Datei durch die Zeichenfolge "Test Content":</span><span class="sxs-lookup"><span data-stu-id="deb3b-178">This command replaces the contents of the `Test.txt` file with the "test content" string:</span></span>

```powershell
Set-Content -Path test.txt -Value "test content"
```

<span data-ttu-id="deb3b-179">Er überschreibt den Inhalt von `Test.txt` .</span><span class="sxs-lookup"><span data-stu-id="deb3b-179">It overwrites the contents of `Test.txt`.</span></span> <span data-ttu-id="deb3b-180">Sie können den **value** -Parameter des [New-Item-](xref:Microsoft.PowerShell.Management.New-Item) Cmdlets verwenden, um einer Dateiinhalt hinzuzufügen, wenn Sie Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="deb3b-180">You can use the **Value** parameter of the [New-Item](xref:Microsoft.PowerShell.Management.New-Item) cmdlet to add content to a file when you create it.</span></span>

### <a name="loop-through-the-contents-of-a-file"></a><span data-ttu-id="deb3b-181">Durchlaufen Sie den Inhalt einer Datei.</span><span class="sxs-lookup"><span data-stu-id="deb3b-181">Loop through the contents of a file</span></span>

<span data-ttu-id="deb3b-182">Standardmäßig verwendet das `Get-Content` Cmdlet das Zeilenendezeichen als Trennzeichen, sodass es eine Datei als eine Auflistung von Zeichen folgen erhält, wobei jede Zeile eine Zeichenfolge in der Datei ist.</span><span class="sxs-lookup"><span data-stu-id="deb3b-182">By default, the `Get-Content` cmdlet uses the end-of-line character as its delimiter, so it gets a file as a collection of strings, with each line as one string in the file.</span></span>

<span data-ttu-id="deb3b-183">Sie können den- `-Delimiter` Parameter verwenden, um ein alternatives Trennzeichen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="deb3b-183">You can use the `-Delimiter` parameter to specify an alternate delimiter.</span></span> <span data-ttu-id="deb3b-184">Wenn Sie dafür die Zeichen festlegen, die das Ende eines Abschnitts oder den Anfang des nächsten Abschnitts kennzeichnen, können Sie die Datei in logische Teile aufteilen.</span><span class="sxs-lookup"><span data-stu-id="deb3b-184">If you set it to the characters that denote the end of a section or the beginning of the next section, you can split the file into logical parts.</span></span>

<span data-ttu-id="deb3b-185">Der erste Befehl ruft die `Employees.txt` Datei ab und teilt Sie in Abschnitte auf, von denen jede mit den Wörtern "End of Employee Record" endet, und speichert Sie in der `$e` Variablen.</span><span class="sxs-lookup"><span data-stu-id="deb3b-185">The first command gets the `Employees.txt` file and splits it into sections, each of which ends with the words "End of Employee Record" and it saves it in the `$e` variable.</span></span>

<span data-ttu-id="deb3b-186">Der zweite Befehl verwendet die Array Notation, um das erste Element in der Auflistung in zu erhalten `$e` .</span><span class="sxs-lookup"><span data-stu-id="deb3b-186">The second command uses array notation to get the first item in the collection in `$e`.</span></span> <span data-ttu-id="deb3b-187">Es wird ein Index von 0 verwendet, da PowerShell-Arrays NULL basiert sind.</span><span class="sxs-lookup"><span data-stu-id="deb3b-187">It uses an index of 0, because PowerShell arrays are zero-based.</span></span>

<span data-ttu-id="deb3b-188">Weitere Informationen zum `Get-Content` Cmdlet finden Sie im Hilfethema zu " [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)".</span><span class="sxs-lookup"><span data-stu-id="deb3b-188">For more information about `Get-Content` cmdlet, see the help topic for the [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content).</span></span>

<span data-ttu-id="deb3b-189">Weitere Informationen zu Arrays finden Sie unter [about_Arrays](../About/about_Arrays.md).</span><span class="sxs-lookup"><span data-stu-id="deb3b-189">For more information about arrays, see [about_Arrays](../About/about_Arrays.md).</span></span>

```powershell
$e = Get-Content c:\test\employees.txt -Delimited "End Of Employee Record"
$e[0]
```

## <a name="managing-security-descriptors"></a><span data-ttu-id="deb3b-190">Verwalten von Sicherheits Deskriptoren</span><span class="sxs-lookup"><span data-stu-id="deb3b-190">Managing security descriptors</span></span>

### <a name="view-the-acl-for-a-file"></a><span data-ttu-id="deb3b-191">Anzeigen der ACL für eine Datei</span><span class="sxs-lookup"><span data-stu-id="deb3b-191">View the ACL for a file</span></span>

<span data-ttu-id="deb3b-192">Dieser Befehl gibt ein [System. Security. AccessControl. FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) -Objekt zurück:</span><span class="sxs-lookup"><span data-stu-id="deb3b-192">This command returns a [System.Security.AccessControl.FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) object:</span></span>

```powershell
Get-Acl -Path test.txt | Format-List -Property *
```

<span data-ttu-id="deb3b-193">Um weitere Informationen zu diesem Objekt zu erhalten, übergeben Sie den Befehl an das Cmdlet " [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member) ".</span><span class="sxs-lookup"><span data-stu-id="deb3b-193">For more information about this object, pipe the command to the [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member) cmdlet.</span></span> <span data-ttu-id="deb3b-194">Oder siehe [FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="deb3b-194">Or, see [FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) Class.</span></span>

### <a name="modify-the-acl-for-a-file"></a><span data-ttu-id="deb3b-195">Ändern der ACL für eine Datei</span><span class="sxs-lookup"><span data-stu-id="deb3b-195">Modify the ACL for a file</span></span>

### <a name="create-and-set-an-acl-for-a-file"></a><span data-ttu-id="deb3b-196">Erstellen und Festlegen einer ACL für eine Datei</span><span class="sxs-lookup"><span data-stu-id="deb3b-196">Create and set an ACL for a file</span></span>

## <a name="creating-files-and-directories"></a><span data-ttu-id="deb3b-197">Erstellen von Dateien und Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="deb3b-197">Creating files and directories</span></span>

### <a name="create-a-directory"></a><span data-ttu-id="deb3b-198">Erstellen eines Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="deb3b-198">Create a directory</span></span>

<span data-ttu-id="deb3b-199">Mit diesem Befehl wird das `logfiles` Verzeichnis auf dem `C` Laufwerk erstellt:</span><span class="sxs-lookup"><span data-stu-id="deb3b-199">This command creates the `logfiles` directory on the `C` drive:</span></span>

```powershell
New-Item -Path c:\ -Name logfiles -Type directory
```

<span data-ttu-id="deb3b-200">PowerShell enthält auch eine `mkdir` Funktion (Alias `md` ), die das Cmdlet [New-Item](xref:Microsoft.PowerShell.Management.New-Item) verwendet, um ein neues Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="deb3b-200">PowerShell also includes a `mkdir` function (alias `md`) that uses the [New-Item](xref:Microsoft.PowerShell.Management.New-Item) cmdlet to create a new directory.</span></span>

### <a name="create-a-file"></a><span data-ttu-id="deb3b-201">Erstellen von Dateien</span><span class="sxs-lookup"><span data-stu-id="deb3b-201">Create a file</span></span>

<span data-ttu-id="deb3b-202">Dieser Befehl erstellt die `log2.txt` Datei im `C:\logfiles` Verzeichnis und fügt dann die Zeichenfolge "Testprotokoll" zur Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="deb3b-202">This command creates the `log2.txt` file in the `C:\logfiles` directory and then adds the "test log" string to the file:</span></span>

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file
```

### <a name="create-a-file-with-content"></a><span data-ttu-id="deb3b-203">Erstellen einer Datei mit Inhalt</span><span class="sxs-lookup"><span data-stu-id="deb3b-203">Create a file with content</span></span>

<span data-ttu-id="deb3b-204">Erstellt eine Datei mit dem Namen `log2.txt` im `C:\logfiles` Verzeichnis und fügt die Zeichenfolge "Test log" zur Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="deb3b-204">Creates a file called `log2.txt` in the `C:\logfiles` directory and adds the string "test log" to the file.</span></span>

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file -Value "test log"
```

## <a name="renaming-files-and-directories"></a><span data-ttu-id="deb3b-205">Umbenennen von Dateien und Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="deb3b-205">Renaming files and directories</span></span>

### <a name="rename-a-file"></a><span data-ttu-id="deb3b-206">Umbenennen einer Datei</span><span class="sxs-lookup"><span data-stu-id="deb3b-206">Rename a file</span></span>

<span data-ttu-id="deb3b-207">Mit diesem Befehl wird die `a.txt` Datei im `C:\a` Verzeichnis in umbenannt `b.txt` :</span><span class="sxs-lookup"><span data-stu-id="deb3b-207">This command renames the `a.txt` file in the `C:\a` directory to `b.txt`:</span></span>

```powershell
Rename-Item -Path c:\a\a.txt -NewName b.txt
```

### <a name="rename-a-directory"></a><span data-ttu-id="deb3b-208">Umbenennen eines Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="deb3b-208">Rename a directory</span></span>

<span data-ttu-id="deb3b-209">Mit diesem Befehl wird das `C:\a\cc` Verzeichnis in umbenannt `C:\a\dd` :</span><span class="sxs-lookup"><span data-stu-id="deb3b-209">This command renames the `C:\a\cc` directory to `C:\a\dd`:</span></span>

```powershell
Rename-Item -Path c:\a\cc -NewName dd
```

## <a name="deleting-files-and-directories"></a><span data-ttu-id="deb3b-210">Löschen von Dateien und Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="deb3b-210">Deleting files and directories</span></span>

### <a name="delete-a-file"></a><span data-ttu-id="deb3b-211">Löschen von Dateien</span><span class="sxs-lookup"><span data-stu-id="deb3b-211">Delete a file</span></span>

<span data-ttu-id="deb3b-212">Mit diesem Befehl wird die `Test.txt` Datei im aktuellen Verzeichnis gelöscht:</span><span class="sxs-lookup"><span data-stu-id="deb3b-212">This command deletes the `Test.txt` file in the current directory:</span></span>

```powershell
Remove-Item -Path test.txt
```

### <a name="delete-files-using-wildcards"></a><span data-ttu-id="deb3b-213">Löschen von Dateien mithilfe von Platzhaltern</span><span class="sxs-lookup"><span data-stu-id="deb3b-213">Delete files using wildcards</span></span>

<span data-ttu-id="deb3b-214">Dieser Befehl löscht alle Dateien im aktuellen Verzeichnis mit der `.xml` Dateinamenerweiterung:</span><span class="sxs-lookup"><span data-stu-id="deb3b-214">This command deletes all the files in the current directory that have the `.xml` file name extension:</span></span>

```powershell
Remove-Item -Path *.xml
```

## <a name="starting-a-program-by-invoking-an-associated-file"></a><span data-ttu-id="deb3b-215">Starten eines Programms durch Aufrufen einer zugeordneten Datei</span><span class="sxs-lookup"><span data-stu-id="deb3b-215">Starting a program by invoking an associated file</span></span>

### <a name="invoke-a-file"></a><span data-ttu-id="deb3b-216">Datei aufrufen</span><span class="sxs-lookup"><span data-stu-id="deb3b-216">Invoke a file</span></span>

<span data-ttu-id="deb3b-217">Der erste Befehl verwendet das [Get-Service-](xref:Microsoft.PowerShell.Management.Get-Service) Cmdlet, um Informationen zu lokalen Diensten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="deb3b-217">The first command uses the [Get-Service](xref:Microsoft.PowerShell.Management.Get-Service) cmdlet to get information about local services.</span></span>

<span data-ttu-id="deb3b-218">Er leitet die Informationen an das [Export-CSV-](xref:Microsoft.PowerShell.Utility.Export-Csv) Cmdlet weiter und speichert diese Informationen in der `Services.csv` Datei.</span><span class="sxs-lookup"><span data-stu-id="deb3b-218">It pipes the information to the [Export-Csv](xref:Microsoft.PowerShell.Utility.Export-Csv) cmdlet and then stores that information in the `Services.csv` file.</span></span>

<span data-ttu-id="deb3b-219">Der zweite Befehl verwendet " [aufrufen-Item](xref:Microsoft.PowerShell.Management.Invoke-Item) ", um die `services.csv` Datei in dem Programm zu öffnen, das der Erweiterung zugeordnet ist `.csv` :</span><span class="sxs-lookup"><span data-stu-id="deb3b-219">The second command uses [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item) to open the `services.csv` file in the program associated with the `.csv` extension:</span></span>

```powershell
Get-Service | Export-Csv -Path services.csv
Invoke-Item -Path services.csv
```

## <a name="getting-files-and-folders-with-specified-attributes"></a><span data-ttu-id="deb3b-220">Dateien und Ordner mit den angegebenen Attributen werden erhalten.</span><span class="sxs-lookup"><span data-stu-id="deb3b-220">Getting files and folders with specified attributes</span></span>

### <a name="get-system-files"></a><span data-ttu-id="deb3b-221">System Dateien erhalten</span><span class="sxs-lookup"><span data-stu-id="deb3b-221">Get System files</span></span>

<span data-ttu-id="deb3b-222">Dieser Befehl ruft die Systemdateien im aktuellen Verzeichnis und seinen Unterverzeichnissen ab.</span><span class="sxs-lookup"><span data-stu-id="deb3b-222">This command gets system files in the current directory and its subdirectories.</span></span>

<span data-ttu-id="deb3b-223">Er verwendet den `-File` -Parameter, um nur Dateien (keine Verzeichnisse) abzurufen, und den- `-System` Parameter, um nur Elemente mit dem "System"-Attribut abzurufen.</span><span class="sxs-lookup"><span data-stu-id="deb3b-223">It uses the `-File` parameter to get only files (not directories) and the `-System` parameter to get only items with the "system" attribute.</span></span>

<span data-ttu-id="deb3b-224">Er verwendet den `-Recurse` -Parameter, um die Elemente im aktuellen Verzeichnis und allen Unterverzeichnissen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="deb3b-224">It uses the `-Recurse` parameter to get the items in the current directory and all subdirectories.</span></span>

```powershell
Get-ChildItem -File -System -Recurse
```

### <a name="get-hidden-files"></a><span data-ttu-id="deb3b-225">Ausgeblendete Dateien</span><span class="sxs-lookup"><span data-stu-id="deb3b-225">Get Hidden files</span></span>

<span data-ttu-id="deb3b-226">Dieser Befehl ruft alle Dateien ab, einschließlich versteckte Dateien im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="deb3b-226">This command gets all files, including hidden files, in the current directory.</span></span>

<span data-ttu-id="deb3b-227">Er verwendet den **Attribute** -Parameter mit zwei Werten, `!Directory+Hidden` , der verborgene Dateien abruft, und `!Directory` , die alle anderen Dateien abruft.</span><span class="sxs-lookup"><span data-stu-id="deb3b-227">It uses the **Attributes** parameter with two values, `!Directory+Hidden`, which gets hidden files, and `!Directory`, which gets all other files.</span></span>

```powershell
Get-ChildItem -Attributes !Directory,!Directory+Hidden
```

<span data-ttu-id="deb3b-228">`dir -att !d,!d+h` entspricht diesem Befehl.</span><span class="sxs-lookup"><span data-stu-id="deb3b-228">`dir -att !d,!d+h` is the equivalent of this command.</span></span>

### <a name="get-compressed-and-encrypted-files"></a><span data-ttu-id="deb3b-229">Komprimierte und verschlüsselte Dateien erhalten</span><span class="sxs-lookup"><span data-stu-id="deb3b-229">Get Compressed and Encrypted files</span></span>

<span data-ttu-id="deb3b-230">Dieser Befehl ruft die Dateien im aktuellen Verzeichnis ab, die entweder komprimiert oder verschlüsselt sind.</span><span class="sxs-lookup"><span data-stu-id="deb3b-230">This command gets files in the current directory that are either compressed or encrypted.</span></span>

<span data-ttu-id="deb3b-231">Er verwendet den `-Attributes` -Parameter mit zwei Werten, `Compressed` und `Encrypted` .</span><span class="sxs-lookup"><span data-stu-id="deb3b-231">It uses the `-Attributes` parameter with two values, `Compressed` and `Encrypted`.</span></span> <span data-ttu-id="deb3b-232">Die Werte werden durch ein Komma getrennt `,` , das den Operator "or" darstellt.</span><span class="sxs-lookup"><span data-stu-id="deb3b-232">The values are separated by a comma `,` which represents the "OR" operator.</span></span>

```powershell
Get-ChildItem -Attributes Compressed,Encrypted
```

## <a name="dynamic-parameters"></a><span data-ttu-id="deb3b-233">Dynamische Parameter</span><span class="sxs-lookup"><span data-stu-id="deb3b-233">Dynamic parameters</span></span>

<span data-ttu-id="deb3b-234">Dynamische Parameter sind Cmdlet-Parameter, die von einem PowerShell-Anbieter hinzugefügt werden und nur verfügbar sind, wenn das Cmdlet im Anbieter fähigen Laufwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="deb3b-234">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="encoding-microsoftpowershellcommandsfilesystemcmdletproviderencoding"></a><span data-ttu-id="deb3b-235">Codierung von \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\></span><span class="sxs-lookup"><span data-stu-id="deb3b-235">Encoding \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\></span></span>

<span data-ttu-id="deb3b-236">Gibt die Dateicodierung an.</span><span class="sxs-lookup"><span data-stu-id="deb3b-236">Specifies the file encoding.</span></span> <span data-ttu-id="deb3b-237">Der Standardwert ist ASCII.</span><span class="sxs-lookup"><span data-stu-id="deb3b-237">The default is ASCII.</span></span>

- <span data-ttu-id="deb3b-238">**ASCII** : verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="deb3b-238">**ASCII** :  Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="deb3b-239">**BigEndianUnicode** : codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="deb3b-239">**BigEndianUnicode** :  Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="deb3b-240">**String** : verwendet den Codierungstyp für eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="deb3b-240">**String** :  Uses the encoding type for a string.</span></span>
- <span data-ttu-id="deb3b-241">**Unicode** : codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="deb3b-241">**Unicode** :  Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="deb3b-242">**UTF7** : codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="deb3b-242">**UTF7** :   Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="deb3b-243">**UTF8** : codiert im UTF-8-Format.</span><span class="sxs-lookup"><span data-stu-id="deb3b-243">**UTF8** :  Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="deb3b-244">**UTF8BOM** : codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="deb3b-244">**UTF8BOM** : Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="deb3b-245">**UF8NOBOM** : codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="deb3b-245">**UF8NOBOM** : Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="deb3b-246">**UTF32** : codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="deb3b-246">**UTF32** :  Encodes in UTF-32 format.</span></span>
- <span data-ttu-id="deb3b-247">**Standard** : codiert auf der standardmäßigen installierten Codepage.</span><span class="sxs-lookup"><span data-stu-id="deb3b-247">**Default** : Encodes in the default installed code page.</span></span>
- <span data-ttu-id="deb3b-248">**OEM** : verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="deb3b-248">**OEM** : Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="deb3b-249">**Unbekannt** : der Codierungstyp ist unbekannt oder ungültig.</span><span class="sxs-lookup"><span data-stu-id="deb3b-249">**Unknown** :  The encoding type is unknown or invalid.</span></span> <span data-ttu-id="deb3b-250">Die Daten können als Binärdateien behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="deb3b-250">The data can be treated as binary.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="deb3b-251">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="deb3b-251">Cmdlets supported</span></span>

- [<span data-ttu-id="deb3b-252">Add-Content</span><span class="sxs-lookup"><span data-stu-id="deb3b-252">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="deb3b-253">Get-Content</span><span class="sxs-lookup"><span data-stu-id="deb3b-253">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="deb3b-254">Set-Content</span><span class="sxs-lookup"><span data-stu-id="deb3b-254">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="delimiter-systemstring"></a><span data-ttu-id="deb3b-255">Delimiter \<System.String\></span><span class="sxs-lookup"><span data-stu-id="deb3b-255">Delimiter \<System.String\></span></span>

<span data-ttu-id="deb3b-256">Gibt das Trennzeichen an, das [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) verwendet, um die Datei in Objekte zu unterteilen, während es liest.</span><span class="sxs-lookup"><span data-stu-id="deb3b-256">Specifies the delimiter that [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) uses to divide the file into objects while it reads.</span></span>

<span data-ttu-id="deb3b-257">Der Standardwert ist `\n` , das Zeilenendezeichen.</span><span class="sxs-lookup"><span data-stu-id="deb3b-257">The default is `\n`, the end-of-line character.</span></span>

<span data-ttu-id="deb3b-258">Beim Lesen einer Textdatei gibt [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) eine Auflistung von Zeichen folgen Objekten zurück, die jeweils mit dem Trennzeichen enden.</span><span class="sxs-lookup"><span data-stu-id="deb3b-258">When reading a text file, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) returns a collection of string objects, each of which ends with the delimiter character.</span></span>

<span data-ttu-id="deb3b-259">Wenn Sie ein Trennzeichen eingeben, das in der Datei nicht vorhanden ist, gibt [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) die gesamte Datei als einzelnes, nicht durch Trennzeichen getrenntes Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="deb3b-259">Entering a delimiter that does not exist in the file, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) returns the entire file as a single, un-delimited object.</span></span>

<span data-ttu-id="deb3b-260">Sie können diesen Parameter verwenden, um eine große Datei in kleinere Dateien aufzuteilen, indem Sie ein Dateitrennzeichen, wie z. B. "End of Example", als Trennzeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="deb3b-260">You can use this parameter to split a large file into smaller files by specifying a file separator, such as "End of Example", as the delimiter.</span></span> <span data-ttu-id="deb3b-261">Das Trennzeichen wird beibehalten (nicht verworfen) und wird das letzte Element in jedem Dateiabschnitt.</span><span class="sxs-lookup"><span data-stu-id="deb3b-261">The delimiter is preserved (not discarded) and becomes the last item in each file section.</span></span>

> [!NOTE]
> <span data-ttu-id="deb3b-262">Wenn der Wert des- `-Delimiter` Parameters eine leere Zeichenfolge ist, gibt [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) aktuell nichts zurück.</span><span class="sxs-lookup"><span data-stu-id="deb3b-262">Currently, when the value of the `-Delimiter` parameter is an empty string, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) does not return anything.</span></span>
> <span data-ttu-id="deb3b-263">Dies ist ein bekanntes Problem.</span><span class="sxs-lookup"><span data-stu-id="deb3b-263">This is a known issue.</span></span> <span data-ttu-id="deb3b-264">Um zu erzwingen, dass [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) die gesamte Datei als eine einzelne Zeichenfolge zurückgibt, geben Sie einen Wert ein, der in der Datei nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="deb3b-264">To force [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) to return the entire file as a single, undelimited string, enter a value that does not exist in the file.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="deb3b-265">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="deb3b-265">Cmdlets supported</span></span>

- [<span data-ttu-id="deb3b-266">Get-Content</span><span class="sxs-lookup"><span data-stu-id="deb3b-266">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="wait-systemmanagementautomationswitchparameter"></a><span data-ttu-id="deb3b-267">Wait \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="deb3b-267">Wait \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="deb3b-268">Wartet auf Inhalt, der an die Datei angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="deb3b-268">Waits for content to be appended to the file.</span></span> <span data-ttu-id="deb3b-269">Wenn Inhalt angefügt wird, wird der angefügte Inhalt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="deb3b-269">If content is appended, it returns the appended content.</span></span> <span data-ttu-id="deb3b-270">Wenn der Inhalt geändert wurde, wird die gesamte Datei zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="deb3b-270">If the content has changed, it returns the entire file.</span></span>

<span data-ttu-id="deb3b-271">In der Warteschlange überprüft [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) die Datei einmal pro Sekunde, bis Sie sie unterbrechen, indem Sie z. B. STRG + C drücken.</span><span class="sxs-lookup"><span data-stu-id="deb3b-271">When waiting, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) checks the file once each second until you interrupt it, such as by pressing CTRL+C.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="deb3b-272">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="deb3b-272">Cmdlets supported</span></span>

- [<span data-ttu-id="deb3b-273">Get-Content</span><span class="sxs-lookup"><span data-stu-id="deb3b-273">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="attributes-flagsexpression"></a><span data-ttu-id="deb3b-274">Attributes \<FlagsExpression\></span><span class="sxs-lookup"><span data-stu-id="deb3b-274">Attributes \<FlagsExpression\></span></span>

<span data-ttu-id="deb3b-275">Ruft Dateien und Ordner mit den angegebenen Attributen ab.</span><span class="sxs-lookup"><span data-stu-id="deb3b-275">Gets files and folders with the specified attributes.</span></span> <span data-ttu-id="deb3b-276">Dieser Parameter unterstützt alle Attribute und Sie können komplexe Kombinationen von Attributen angeben.</span><span class="sxs-lookup"><span data-stu-id="deb3b-276">This parameter supports all attributes and lets you specify complex combinations of attributes.</span></span>

<span data-ttu-id="deb3b-277">Der- `-Attributes` Parameter wurde in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deb3b-277">The `-Attributes` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="deb3b-278">Der- `-Attributes` Parameter unterstützt die folgenden Attribute:</span><span class="sxs-lookup"><span data-stu-id="deb3b-278">The `-Attributes` parameter supports the following attributes:</span></span>

- <span data-ttu-id="deb3b-279">**Archivieren**</span><span class="sxs-lookup"><span data-stu-id="deb3b-279">**Archive**</span></span>
- <span data-ttu-id="deb3b-280">**Compressed**</span><span class="sxs-lookup"><span data-stu-id="deb3b-280">**Compressed**</span></span>
- <span data-ttu-id="deb3b-281">**Device**</span><span class="sxs-lookup"><span data-stu-id="deb3b-281">**Device**</span></span>
- <span data-ttu-id="deb3b-282">**Verzeichnis**</span><span class="sxs-lookup"><span data-stu-id="deb3b-282">**Directory**</span></span>
- <span data-ttu-id="deb3b-283">**Verschlüsselt**</span><span class="sxs-lookup"><span data-stu-id="deb3b-283">**Encrypted**</span></span>
- <span data-ttu-id="deb3b-284">**Hidden**</span><span class="sxs-lookup"><span data-stu-id="deb3b-284">**Hidden**</span></span>
- <span data-ttu-id="deb3b-285">**Normal**</span><span class="sxs-lookup"><span data-stu-id="deb3b-285">**Normal**</span></span>
- <span data-ttu-id="deb3b-286">**Notcontentindiziert**</span><span class="sxs-lookup"><span data-stu-id="deb3b-286">**NotContentIndexed**</span></span>
- <span data-ttu-id="deb3b-287">**Aufzu**</span><span class="sxs-lookup"><span data-stu-id="deb3b-287">**Offline**</span></span>
- <span data-ttu-id="deb3b-288">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="deb3b-288">**ReadOnly**</span></span>
- <span data-ttu-id="deb3b-289">**Analyse Punkt**</span><span class="sxs-lookup"><span data-stu-id="deb3b-289">**ReparsePoint**</span></span>
- <span data-ttu-id="deb3b-290">**Sparpfad**</span><span class="sxs-lookup"><span data-stu-id="deb3b-290">**SparseFile**</span></span>
- <span data-ttu-id="deb3b-291">**System**</span><span class="sxs-lookup"><span data-stu-id="deb3b-291">**System**</span></span>
- <span data-ttu-id="deb3b-292">**Temporär**</span><span class="sxs-lookup"><span data-stu-id="deb3b-292">**Temporary**</span></span>

<span data-ttu-id="deb3b-293">Eine Beschreibung dieser Attribute finden Sie in der [FileAttribute](/dotnet/api/system.io.fileattributes) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="deb3b-293">For a description of these attributes, see the [FileAttributes](/dotnet/api/system.io.fileattributes) enumeration.</span></span>

<span data-ttu-id="deb3b-294">Verwenden Sie die folgenden Operatoren, um Attribute zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="deb3b-294">Use the following operators to combine attributes.</span></span>

- <span data-ttu-id="deb3b-295">`!` -Not</span><span class="sxs-lookup"><span data-stu-id="deb3b-295">`!` - NOT</span></span>
- <span data-ttu-id="deb3b-296">`+` Und</span><span class="sxs-lookup"><span data-stu-id="deb3b-296">`+` - AND</span></span>
- <span data-ttu-id="deb3b-297">`,` Oder</span><span class="sxs-lookup"><span data-stu-id="deb3b-297">`,` - OR</span></span>

<span data-ttu-id="deb3b-298">Zwischen einem Operator und dessen Attribut sind keine Leerzeichen zulässig.</span><span class="sxs-lookup"><span data-stu-id="deb3b-298">No spaces are permitted between an operator and its attribute.</span></span> <span data-ttu-id="deb3b-299">Allerdings dürfen Leerzeichen vor Kommas gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="deb3b-299">However, spaces are permitted before commas.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="deb3b-300">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="deb3b-300">Cmdlets supported</span></span>

- [<span data-ttu-id="deb3b-301">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="deb3b-301">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="directory-systemmanagementautomationswitchparameter"></a><span data-ttu-id="deb3b-302">Directory \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="deb3b-302">Directory \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="deb3b-303">Ruft die Verzeichnisse (Ordner) ab.</span><span class="sxs-lookup"><span data-stu-id="deb3b-303">Gets directories (folders).</span></span>

<span data-ttu-id="deb3b-304">Der- `-Directory` Parameter wurde in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deb3b-304">The `-Directory` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="deb3b-305">Um nur Verzeichnisse abzurufen, verwenden Sie den `-Directory` -Parameter, und lassen Sie den- `-File` Parameter Weg.</span><span class="sxs-lookup"><span data-stu-id="deb3b-305">To get only directories, use the `-Directory` parameter and omit the `-File` parameter.</span></span> <span data-ttu-id="deb3b-306">Um Verzeichnisse auszuschließen, verwenden Sie den `-File` -Parameter, und lassen Sie den-Parameter aus `-Directory` , oder verwenden Sie den- `-Attributes` Parameter.</span><span class="sxs-lookup"><span data-stu-id="deb3b-306">To exclude directories, use the `-File` parameter and omit the `-Directory` parameter, or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="deb3b-307">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="deb3b-307">Cmdlets supported</span></span>

- [<span data-ttu-id="deb3b-308">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="deb3b-308">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="file-systemmanagementautomationswitchparameter"></a><span data-ttu-id="deb3b-309">File \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="deb3b-309">File \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="deb3b-310">Ruft die Dateien ab.</span><span class="sxs-lookup"><span data-stu-id="deb3b-310">Gets files.</span></span>

<span data-ttu-id="deb3b-311">Der- `-File` Parameter wurde in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deb3b-311">The `-File` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="deb3b-312">Um nur Dateien zu erhalten, verwenden Sie den `-File` -Parameter, und lassen Sie den- `-Directory` Parameter Weg.</span><span class="sxs-lookup"><span data-stu-id="deb3b-312">To get only files, use the `-File` parameter and omit the `-Directory` parameter.</span></span> <span data-ttu-id="deb3b-313">Um Dateien auszuschließen, verwenden Sie den `-Directory` -Parameter, und lassen Sie den-Parameter aus `-File` , oder verwenden Sie den- `-Attributes` Parameter.</span><span class="sxs-lookup"><span data-stu-id="deb3b-313">To exclude files, use the `-Directory` parameter and omit the `-File` parameter, or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="deb3b-314">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="deb3b-314">Cmdlets supported</span></span>

- [<span data-ttu-id="deb3b-315">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="deb3b-315">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="hidden-systemmanagementautomationswitchparameter"></a><span data-ttu-id="deb3b-316">Hidden \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="deb3b-316">Hidden \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="deb3b-317">Ruft nur ausgeblendete Dateien und Verzeichnisse (Ordner) ab.</span><span class="sxs-lookup"><span data-stu-id="deb3b-317">Gets only hidden files and directories (folders).</span></span> <span data-ttu-id="deb3b-318">Standardmäßig ruft [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) nur nicht ausgeblendete Elemente ab.</span><span class="sxs-lookup"><span data-stu-id="deb3b-318">By default, [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) gets only non-hidden items.</span></span>

<span data-ttu-id="deb3b-319">Der- `-Hidden` Parameter wurde in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deb3b-319">The `-Hidden` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="deb3b-320">Um nur ausgeblendete Elemente zu erhalten, verwenden Sie den- `-Hidden` Parameter, die- `h` oder- `ah` Aliase oder den **Hidden** -Wert des- `-Attributes` Parameters.</span><span class="sxs-lookup"><span data-stu-id="deb3b-320">To get only hidden items, use the `-Hidden` parameter, its `h` or `ah` aliases, or the **Hidden** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="deb3b-321">Um verborgene Elemente auszuschließen, lassen Sie den-Parameter Weg, `-Hidden` oder verwenden Sie den- `-Attributes` Parameter.</span><span class="sxs-lookup"><span data-stu-id="deb3b-321">To exclude hidden items, omit the `-Hidden` parameter or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="deb3b-322">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="deb3b-322">Cmdlets supported</span></span>

- [<span data-ttu-id="deb3b-323">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="deb3b-323">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="readonly-systemmanagementautomationswitchparameter"></a><span data-ttu-id="deb3b-324">ReadOnly \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="deb3b-324">ReadOnly \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="deb3b-325">Ruft nur schreibgeschützte Dateien und Verzeichnisse (Ordner) ab.</span><span class="sxs-lookup"><span data-stu-id="deb3b-325">Gets only read-only files and directories (folders).</span></span>

<span data-ttu-id="deb3b-326">Der- `-ReadOnly` Parameter wurde in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deb3b-326">The `-ReadOnly` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="deb3b-327">Um nur schreibgeschützte Elemente zu erhalten, verwenden Sie den- `-ReadOnly` Parameter, den `ar` Alias oder **ReadOnly** den schreibgeschützten Wert des- `-Attributes` Parameters.</span><span class="sxs-lookup"><span data-stu-id="deb3b-327">To get only read-only items, use the `-ReadOnly` parameter, its `ar` alias, or the **ReadOnly** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="deb3b-328">Um schreibgeschützte Elemente auszuschließen, verwenden Sie den- `-Attributes` Parameter.</span><span class="sxs-lookup"><span data-stu-id="deb3b-328">To exclude read-only items, use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="deb3b-329">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="deb3b-329">Cmdlets supported</span></span>

- [<span data-ttu-id="deb3b-330">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="deb3b-330">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="system-systemmanagementautomationswitchparameter"></a><span data-ttu-id="deb3b-331">System \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="deb3b-331">System \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="deb3b-332">Ruft nur die Systemdateien und -verzeichnisse (Ordner) ab.</span><span class="sxs-lookup"><span data-stu-id="deb3b-332">Gets only system files and directories (folders).</span></span>

<span data-ttu-id="deb3b-333">Der- `-System` Parameter wurde in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deb3b-333">The `-System` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="deb3b-334">Um nur Systemdateien und Ordner zu erhalten, verwenden Sie den- `-System` Parameter, den `as` Alias oder den **System** Wert des- `-Attributes` Parameters.</span><span class="sxs-lookup"><span data-stu-id="deb3b-334">To get only system files and folders, use the `-System` parameter, its `as` alias, or the **System** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="deb3b-335">Um Systemdateien und Ordner auszuschließen, verwenden Sie den- `-Attributes` Parameter.</span><span class="sxs-lookup"><span data-stu-id="deb3b-335">To exclude system files and folders, use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="deb3b-336">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="deb3b-336">Cmdlets supported</span></span>

- [<span data-ttu-id="deb3b-337">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="deb3b-337">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="newerthan-systemdatetime"></a><span data-ttu-id="deb3b-338">NewerThan \<System.DateTime\></span><span class="sxs-lookup"><span data-stu-id="deb3b-338">NewerThan \<System.DateTime\></span></span>

<span data-ttu-id="deb3b-339">Gibt zurück, `$True` Wenn der `LastWriteTime` Wert einer Datei größer als das angegebene Datum ist.</span><span class="sxs-lookup"><span data-stu-id="deb3b-339">Returns `$True` when the `LastWriteTime` value of a file is greater than the specified date.</span></span> <span data-ttu-id="deb3b-340">Andernfalls wird `$False`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="deb3b-340">Otherwise, it returns `$False`.</span></span>

<span data-ttu-id="deb3b-341">Geben Sie ein [DateTime](/dotnet/api/system.datetime) -Objekt ein, z. b. ein Objekt, das vom [Get-Date-](xref:Microsoft.PowerShell.Utility.Get-Date) Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in ein [DateTime](/dotnet/api/system.datetime) -Objekt konvertiert werden kann, z.b. `"August 10, 2011 2:00 PM"` .</span><span class="sxs-lookup"><span data-stu-id="deb3b-341">Enter a [DateTime](/dotnet/api/system.datetime) object, such as one that the [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet returns, or a string that can be converted to a [DateTime](/dotnet/api/system.datetime) object, such as `"August 10, 2011 2:00 PM"`.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="deb3b-342">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="deb3b-342">Cmdlets supported</span></span>

- [<span data-ttu-id="deb3b-343">Test-Path</span><span class="sxs-lookup"><span data-stu-id="deb3b-343">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="olderthan-systemdatetime"></a><span data-ttu-id="deb3b-344">OlderThan \<System.DateTime\></span><span class="sxs-lookup"><span data-stu-id="deb3b-344">OlderThan \<System.DateTime\></span></span>

<span data-ttu-id="deb3b-345">Gibt zurück, `$True` Wenn der `LastWriteTime` Wert einer Datei kleiner als das angegebene Datum ist.</span><span class="sxs-lookup"><span data-stu-id="deb3b-345">Returns `$True` when the `LastWriteTime` value of a file is less than the specified date.</span></span> <span data-ttu-id="deb3b-346">Andernfalls wird `$False`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="deb3b-346">Otherwise, it returns `$False`.</span></span>

<span data-ttu-id="deb3b-347">Geben Sie ein [DateTime](/dotnet/api/system.datetime) -Objekt ein, z. b. ein Objekt, das vom [Get-Date-](xref:Microsoft.PowerShell.Utility.Get-Date) Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in ein [DateTime](/dotnet/api/system.datetime) -Objekt konvertiert werden kann, z.b. `"August 10, 2011 2:00 PM"` .</span><span class="sxs-lookup"><span data-stu-id="deb3b-347">Enter a [DateTime](/dotnet/api/system.datetime) object, such as one that the [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet returns, or a string that can be converted to a [DateTime](/dotnet/api/system.datetime) object, such as `"August 10, 2011 2:00 PM"`.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="deb3b-348">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="deb3b-348">Cmdlets supported</span></span>

- [<span data-ttu-id="deb3b-349">Test-Path</span><span class="sxs-lookup"><span data-stu-id="deb3b-349">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="stream-systemstring"></a><span data-ttu-id="deb3b-350">Stream \<System.String\></span><span class="sxs-lookup"><span data-stu-id="deb3b-350">Stream \<System.String\></span></span>

<span data-ttu-id="deb3b-351">Verwaltet alternative Datenströme.</span><span class="sxs-lookup"><span data-stu-id="deb3b-351">Manages alternate data streams.</span></span> <span data-ttu-id="deb3b-352">Geben Sie den Namen des Stroms ein.</span><span class="sxs-lookup"><span data-stu-id="deb3b-352">Enter the stream name.</span></span> <span data-ttu-id="deb3b-353">Platzhalter sind nur für Befehle vom Typ " [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) " und " [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item) " in einem Dateisystem Laufwerk zulässig.</span><span class="sxs-lookup"><span data-stu-id="deb3b-353">Wildcards are permitted only in [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) for and [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item) commands in a file system drive.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="deb3b-354">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="deb3b-354">Cmdlets supported</span></span>

- [<span data-ttu-id="deb3b-355">Add-Content</span><span class="sxs-lookup"><span data-stu-id="deb3b-355">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="deb3b-356">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="deb3b-356">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="deb3b-357">Get-Item</span><span class="sxs-lookup"><span data-stu-id="deb3b-357">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="deb3b-358">Get-Content</span><span class="sxs-lookup"><span data-stu-id="deb3b-358">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="deb3b-359">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="deb3b-359">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="deb3b-360">Set-Content</span><span class="sxs-lookup"><span data-stu-id="deb3b-360">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="raw-switchparameter"></a><span data-ttu-id="deb3b-361">Raw \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="deb3b-361">Raw \<SwitchParameter\></span></span>

<span data-ttu-id="deb3b-362">Neue Zeilenumbruchzeichen werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="deb3b-362">Ignores newline characters.</span></span> <span data-ttu-id="deb3b-363">Gibt Inhalte als ein einzelnes Element zurück.</span><span class="sxs-lookup"><span data-stu-id="deb3b-363">Returns contents as a single item.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="deb3b-364">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="deb3b-364">Cmdlets supported</span></span>

- [<span data-ttu-id="deb3b-365">Get-Content</span><span class="sxs-lookup"><span data-stu-id="deb3b-365">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="itemtype-string"></a><span data-ttu-id="deb3b-366">ItemType \<String\></span><span class="sxs-lookup"><span data-stu-id="deb3b-366">ItemType \<String\></span></span>

<span data-ttu-id="deb3b-367">Mit diesem Parameter können Sie die Tye des zu erstellenden Elements angeben. `New-Item`</span><span class="sxs-lookup"><span data-stu-id="deb3b-367">This parameter allows you to specify the tye of item to create with `New-Item`</span></span>

<span data-ttu-id="deb3b-368">Die verfügbaren Werte dieses Parameters hängen vom aktuellen Anbieter ab, den Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="deb3b-368">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="deb3b-369">In einem `FileSystem` Laufwerk sind folgende Werte zulässig:</span><span class="sxs-lookup"><span data-stu-id="deb3b-369">In a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="deb3b-370">Datei</span><span class="sxs-lookup"><span data-stu-id="deb3b-370">File</span></span>
- <span data-ttu-id="deb3b-371">Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="deb3b-371">Directory</span></span>
- <span data-ttu-id="deb3b-372">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="deb3b-372">SymbolicLink</span></span>
- <span data-ttu-id="deb3b-373">Verbindung</span><span class="sxs-lookup"><span data-stu-id="deb3b-373">Junction</span></span>
- <span data-ttu-id="deb3b-374">HardLink</span><span class="sxs-lookup"><span data-stu-id="deb3b-374">HardLink</span></span>

### <a name="cmdlets-supported"></a><span data-ttu-id="deb3b-375">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="deb3b-375">Cmdlets supported</span></span>

- [<span data-ttu-id="deb3b-376">New-Item</span><span class="sxs-lookup"><span data-stu-id="deb3b-376">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="deb3b-377">Verwenden der Pipeline</span><span class="sxs-lookup"><span data-stu-id="deb3b-377">Using the pipeline</span></span>

<span data-ttu-id="deb3b-378">Anbieter-Cmdlets akzeptieren Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="deb3b-378">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="deb3b-379">Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="deb3b-379">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="deb3b-380">Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="deb3b-380">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="deb3b-381">Hilfe</span><span class="sxs-lookup"><span data-stu-id="deb3b-381">Getting help</span></span>

<span data-ttu-id="deb3b-382">Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.</span><span class="sxs-lookup"><span data-stu-id="deb3b-382">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="deb3b-383">Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen [Get-Help-](xref:Microsoft.PowerShell.Core.Get-Help) Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den `-Path` -Parameter von [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) zum Angeben eines Dateisystem Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="deb3b-383">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path c:
```

## <a name="see-also"></a><span data-ttu-id="deb3b-384">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="deb3b-384">See also</span></span>

[<span data-ttu-id="deb3b-385">about_Providers</span><span class="sxs-lookup"><span data-stu-id="deb3b-385">about_Providers</span></span>](../About/about_Providers.md)
