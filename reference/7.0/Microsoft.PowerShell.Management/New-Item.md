---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: f24988833faaf56395b95e08430bbcc9fb6d2746
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210972"
---
# <span data-ttu-id="d3726-103">New-Item</span><span class="sxs-lookup"><span data-stu-id="d3726-103">New-Item</span></span>

## <span data-ttu-id="d3726-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d3726-104">SYNOPSIS</span></span>
<span data-ttu-id="d3726-105">Erstellt ein neues Element.</span><span class="sxs-lookup"><span data-stu-id="d3726-105">Creates a new item.</span></span>

## <span data-ttu-id="d3726-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d3726-106">SYNTAX</span></span>

### <span data-ttu-id="d3726-107">pfadsatz (Standard)</span><span class="sxs-lookup"><span data-stu-id="d3726-107">pathSet (Default)</span></span>

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d3726-108">nameset</span><span class="sxs-lookup"><span data-stu-id="d3726-108">nameSet</span></span>

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d3726-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d3726-109">DESCRIPTION</span></span>

<span data-ttu-id="d3726-110">Das `New-Item` Cmdlet erstellt ein neues Element und legt seinen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="d3726-110">The `New-Item` cmdlet creates a new item and sets its value.</span></span> <span data-ttu-id="d3726-111">Die Typen der Elemente, die erstellt werden können, hängen vom Speicherort des Elements ab.</span><span class="sxs-lookup"><span data-stu-id="d3726-111">The types of items that can be created depend on the location of the item.</span></span> <span data-ttu-id="d3726-112">Beispielsweise werden im Dateisystem `New-Item` Dateien und Ordner erstellt.</span><span class="sxs-lookup"><span data-stu-id="d3726-112">For example, in the file system, `New-Item` creates files and folders.</span></span> <span data-ttu-id="d3726-113">In der Registrierung `New-Item` erstellt Registrierungsschlüssel und-Einträge.</span><span class="sxs-lookup"><span data-stu-id="d3726-113">In the registry, `New-Item` creates registry keys and entries.</span></span>

<span data-ttu-id="d3726-114">`New-Item` kann auch den Wert der erstellten Elemente festlegen.</span><span class="sxs-lookup"><span data-stu-id="d3726-114">`New-Item` can also set the value of the items that it creates.</span></span> <span data-ttu-id="d3726-115">Wenn beispielsweise eine neue Datei erstellt wird, `New-Item` kann der Datei anfänglicher Inhalt hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d3726-115">For example, when it creates a new file, `New-Item` can add initial content to the file.</span></span>

## <span data-ttu-id="d3726-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d3726-116">EXAMPLES</span></span>

### <span data-ttu-id="d3726-117">Beispiel 1: Erstellen einer Datei im aktuellen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="d3726-117">Example 1: Create a file in the current directory</span></span>

<span data-ttu-id="d3726-118">Mit diesem Befehl wird eine Textdatei mit dem Namen "testfile1.txt" im aktuellen Verzeichnis erstellt.</span><span class="sxs-lookup"><span data-stu-id="d3726-118">This command creates a text file that is named "testfile1.txt" in the current directory.</span></span> <span data-ttu-id="d3726-119">Der Punkt (".") im Wert des **path** -Parameters gibt das aktuelle Verzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="d3726-119">The dot ('.') in the value of the **Path** parameter indicates the current directory.</span></span> <span data-ttu-id="d3726-120">Der Text in Anführungszeichen, der auf den **value** -Parameter folgt, wird der Datei als Inhalt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d3726-120">The quoted text that follows the **Value** parameter is added to the file as content.</span></span>

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### <span data-ttu-id="d3726-121">Beispiel 2: Erstellen eines Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="d3726-121">Example 2: Create a directory</span></span>

<span data-ttu-id="d3726-122">Mit diesem Befehl wird ein Verzeichnis mit dem Namen "Logfiles" im `C:` Laufwerk erstellt.</span><span class="sxs-lookup"><span data-stu-id="d3726-122">This command creates a directory named "Logfiles" in the `C:` drive.</span></span> <span data-ttu-id="d3726-123">Der **ItemType** -Parameter gibt an, dass das neue Element ein Verzeichnis und keine Datei oder ein anderes Dateisystem Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="d3726-123">The **ItemType** parameter specifies that the new item is a directory, not a file or other file system object.</span></span>

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### <span data-ttu-id="d3726-124">Beispiel 3: Erstellen eines Profils</span><span class="sxs-lookup"><span data-stu-id="d3726-124">Example 3: Create a profile</span></span>

<span data-ttu-id="d3726-125">Mit diesem Befehl wird ein PowerShell-Profil in dem Pfad erstellt, der durch die Variable angegeben wird `$profile` .</span><span class="sxs-lookup"><span data-stu-id="d3726-125">This command creates a PowerShell profile in the path that is specified by the `$profile` variable.</span></span>

<span data-ttu-id="d3726-126">Mit Profilen können Sie PowerShell anpassen.</span><span class="sxs-lookup"><span data-stu-id="d3726-126">You can use profiles to customize PowerShell.</span></span> <span data-ttu-id="d3726-127">`$profile` ist eine automatische (integrierte) Variable, die den Pfad und den Dateinamen des Profils "CurrentUser/Currency Thost" speichert.</span><span class="sxs-lookup"><span data-stu-id="d3726-127">`$profile` is an automatic (built-in) variable that stores the path and file name of the "CurrentUser/CurrentHost" profile.</span></span> <span data-ttu-id="d3726-128">Standardmäßig ist das Profil nicht vorhanden, auch wenn von PowerShell ein Pfad und ein Dateiname für das Profil gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d3726-128">By default, the profile does not exist, even though PowerShell stores a path and file name for it.</span></span>

<span data-ttu-id="d3726-129">In diesem Befehl stellt die `$profile` Variable den Pfad der Datei dar.</span><span class="sxs-lookup"><span data-stu-id="d3726-129">In this command, the `$profile` variable represents the path of the file.</span></span> <span data-ttu-id="d3726-130">Der **ItemType** -Parameter gibt an, dass der Befehl eine Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="d3726-130">**ItemType** parameter specifies that the command creates a file.</span></span> <span data-ttu-id="d3726-131">Mit dem **Force** -Parameter können Sie eine Datei im Profilpfad erstellen, selbst wenn die Verzeichnisse im Pfad nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d3726-131">The **Force** parameter lets you create a file in the profile path, even when the directories in the path do not exist.</span></span>

<span data-ttu-id="d3726-132">Nachdem Sie ein Profil erstellt haben, können Sie Aliase, Funktionen und Skripts im Profil eingeben, um die Shell anzupassen.</span><span class="sxs-lookup"><span data-stu-id="d3726-132">After you create a profile, you can enter aliases, functions, and scripts in the profile to customize your shell.</span></span>

<span data-ttu-id="d3726-133">Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) und [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d3726-133">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) and [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

### <span data-ttu-id="d3726-134">Beispiel 4: Erstellen eines Verzeichnisses in einem anderen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="d3726-134">Example 4: Create a directory in a different directory</span></span>

<span data-ttu-id="d3726-135">In diesem Beispiel wird ein neues Scripts-Verzeichnis im Verzeichnis "c:\ps-Test" erstellt.</span><span class="sxs-lookup"><span data-stu-id="d3726-135">This example creates a new Scripts directory in the "C:\PS-Test" directory.</span></span>

<span data-ttu-id="d3726-136">Der Name des neuen Verzeichnis Elements "Scripts" ist im Wert des **path** -Parameters enthalten, anstatt im Wert von " **Name** " angegeben zu werden.</span><span class="sxs-lookup"><span data-stu-id="d3726-136">The name of the new directory item, "Scripts", is included in the value of **Path** parameter, instead of being specified in the value of **Name** .</span></span> <span data-ttu-id="d3726-137">Gemäß Syntax kann der Befehl auf beide Weisen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d3726-137">As indicated by the syntax, either command form is valid.</span></span>

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### <span data-ttu-id="d3726-138">Beispiel 5: Erstellen mehrerer Dateien</span><span class="sxs-lookup"><span data-stu-id="d3726-138">Example 5: Create multiple files</span></span>

<span data-ttu-id="d3726-139">In diesem Beispiel werden Dateien in zwei verschiedenen Verzeichnissen erstellt.</span><span class="sxs-lookup"><span data-stu-id="d3726-139">This example creates files in two different directories.</span></span> <span data-ttu-id="d3726-140">Da der **Pfad** mehrere Zeichen folgen annimmt, können Sie ihn verwenden, um mehrere Elemente zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d3726-140">Because **Path** takes multiple strings, you can use it to create multiple items.</span></span>

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### <span data-ttu-id="d3726-141">Beispiel 6: Verwenden von Platzhaltern zum Erstellen von Dateien in mehreren Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="d3726-141">Example 6: Use wildcards to create files in multiple directories</span></span>

<span data-ttu-id="d3726-142">Das `New-Item` Cmdlet unterstützt Platzhalter im **path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d3726-142">The `New-Item` cmdlet supports wildcards in the **Path** parameter.</span></span> <span data-ttu-id="d3726-143">Der folgende Befehl erstellt eine `temp.txt` Datei in allen Verzeichnissen, die durch die Platzhalter im **path** -Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d3726-143">The following command creates a `temp.txt` file in all of the directories specified by the wildcards in the **Path** parameter.</span></span>

```powershell
Get-ChildItem -Path C:\Temp\
```

```Output
    Directory:  C:\Temp

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d-----        5/15/2019   6:45 AM        1   One
d-----        5/15/2019   6:45 AM        1   Two
d-----        5/15/2019   6:45 AM        1   Three
```

```powershell
New-Item -Path * -Name temp.txt -ItemType File | Select-Object FullName
```

```Output
FullName
--------
C:\Temp\One\temp.txt
C:\Temp\Three\temp.txt
C:\Temp\Two\temp.txt
```

<span data-ttu-id="d3726-144">Das- `Get-ChildItem` Cmdlet zeigt drei Verzeichnisse unter dem `C:\Temp` Verzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="d3726-144">The `Get-ChildItem` cmdlet shows three directories under the `C:\Temp` directory.</span></span> <span data-ttu-id="d3726-145">Wenn Sie Platzhalter verwenden, `New-Item` erstellt das Cmdlet eine `temp.txt` Datei in allen Verzeichnissen im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d3726-145">Using wildcards the `New-Item` cmdlet creates a `temp.txt` file in all of the directories under the current directory.</span></span> <span data-ttu-id="d3726-146">Das- `New-Item` Cmdlet gibt die Elemente aus, die Sie erstellt haben und an die weitergeleitet werden, `Select-Object` um die Pfade der neu erstellten Dateien zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d3726-146">The `New-Item` cmdlet outputs the items you created, which is piped to `Select-Object` to verify the paths of the newly created files.</span></span>

### <span data-ttu-id="d3726-147">Beispiel 7: Erstellen eines symbolischen Links zu einer Datei oder einem Ordner</span><span class="sxs-lookup"><span data-stu-id="d3726-147">Example 7: Create a symbolic link to a file or folder</span></span>

<span data-ttu-id="d3726-148">In diesem Beispiel wird eine symbolische Verknüpfung mit der Notice.txt-Datei im aktuellen Ordner erstellt.</span><span class="sxs-lookup"><span data-stu-id="d3726-148">This example creates a symbolic link to the Notice.txt file in the current folder.</span></span>

```powershell
$link = New-Item -ItemType SymbolicLink -Path .\link -Target .\Notice.txt
$link | Select-Object LinkType, Target
```

```Output
LinkType     Target
--------     ------
SymbolicLink {.\Notice.txt}
```

<span data-ttu-id="d3726-149">In diesem Beispiel ist **target** ein Alias für den **value** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d3726-149">In this example, **Target** is an alias for the **Value** parameter.</span></span> <span data-ttu-id="d3726-150">Das Ziel der symbolischen Verknüpfung kann ein relativer Pfad sein.</span><span class="sxs-lookup"><span data-stu-id="d3726-150">The target of the symbolic link can be a relative path.</span></span> <span data-ttu-id="d3726-151">Vor PowerShell-Version 6.2 muss das Ziel ein voll qualifizierter Pfad sein.</span><span class="sxs-lookup"><span data-stu-id="d3726-151">Prior to PowerShell v6.2, the target must be a fully-qualified path.</span></span>

> [!CAUTION]
> <span data-ttu-id="d3726-152">Wenn Sie ein **SymbolicLink** in einem Ordner unter Windows erstellen, müssen Sie einen voll qualifizierten Pfad verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3726-152">If you are creating a **SymbolicLink** to a folder on Windows, you must use a fully-qualified path.</span></span> <span data-ttu-id="d3726-153">Wenn Sie einen relativen Pfad verwenden, wird der Link als Dateityp-Link anstelle eines Directory-Type-Links erstellt.</span><span class="sxs-lookup"><span data-stu-id="d3726-153">If you use a relative path, the link is created as a file-type link instead of a directory-type link.</span></span>

### <span data-ttu-id="d3726-154">Beispiel 8: Verwenden des Parameters "-Force" zum Erstellen von Ordnern</span><span class="sxs-lookup"><span data-stu-id="d3726-154">Example 8: Use the -Force parameter to attempt to recreate folders</span></span>

<span data-ttu-id="d3726-155">In diesem Beispiel wird ein Ordner mit einer Datei in erstellt.</span><span class="sxs-lookup"><span data-stu-id="d3726-155">This example creates a folder with a file inside.</span></span> <span data-ttu-id="d3726-156">Anschließend versucht, mithilfe von denselben Ordner zu erstellen `-Force` .</span><span class="sxs-lookup"><span data-stu-id="d3726-156">Then, attempts to create the same folder using `-Force`.</span></span> <span data-ttu-id="d3726-157">Der Ordner wird nicht überschrieben, sondern es wird einfach das vorhandene Ordner Objekt mit der Datei zurückgegeben, die intakt erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d3726-157">It will not overwrite the folder but simply return the existing folder object with the file created intact.</span></span>

```powershell
PS> New-Item -Path .\TestFolder -ItemType Directory
PS> New-Item -Path .\TestFolder\TestFile.txt -ItemType File

PS> New-Item -Path .\TestFolder -ItemType Directory -Force

    Directory: C:\
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         5/1/2020   8:03 AM                TestFolder

PS> Get-ChildItem .\TestFolder\

    Directory: C:\TestFolder
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:03 AM              0 TestFile.txt
```

### <span data-ttu-id="d3726-158">Beispiel 9: Verwenden des Parameters "-Force" zum Überschreiben vorhandener Dateien</span><span class="sxs-lookup"><span data-stu-id="d3726-158">Example 9: Use the -Force parameter to overwrite existing files</span></span>

<span data-ttu-id="d3726-159">In diesem Beispiel wird eine Datei mit einem Wert erstellt und die Datei dann mithilfe von neu erstellt `-Force` .</span><span class="sxs-lookup"><span data-stu-id="d3726-159">This example creates a file with a value and then recreates the file using `-Force`.</span></span> <span data-ttu-id="d3726-160">Dadurch wird die vorhandene Datei überschrieben, und der Inhalt wird wie durch die length-Eigenschaft angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3726-160">This overwrites The existing file and it will lose it's content as you can see by the length property</span></span>

```powershell
PS> New-Item ./TestFile.txt -ItemType File -Value 'This is just a test file'

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM             24 TestFile.txt

New-Item ./TestFile.txt -ItemType File -Force

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM              0 TestFile.txt
```

> [!NOTE]
> <span data-ttu-id="d3726-161">Wenn Sie `New-Item` mit dem- `-Force` Schalter verwenden, um Registrierungsschlüssel zu erstellen, verhält sich der Befehl identisch mit dem, wenn eine Datei überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="d3726-161">When using `New-Item` with the `-Force` switch to create registry keys, the command will behave the same as when overwriting a file.</span></span> <span data-ttu-id="d3726-162">Wenn der Registrierungsschlüssel bereits vorhanden ist, werden der Schlüssel und alle Eigenschaften und Werte mit einem leeren Registrierungsschlüssel überschrieben.</span><span class="sxs-lookup"><span data-stu-id="d3726-162">If the registry key already exists, the key and all properties and values will be overwritten with an empty registry key.</span></span>

## <span data-ttu-id="d3726-163">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d3726-163">PARAMETERS</span></span>

### <span data-ttu-id="d3726-164">-Credential</span><span class="sxs-lookup"><span data-stu-id="d3726-164">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="d3726-165">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d3726-165">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="d3726-166">Verwenden Sie, um die Identität eines anderen Benutzers anzunehmen oder die Anmelde Informationen beim Ausführen dieses Cmdlets zu erhöhen `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="d3726-166">To impersonate another user or elevate your credentials when running this cmdlet, use `Invoke-Command`.</span></span>

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

### <span data-ttu-id="d3726-167">-Force</span><span class="sxs-lookup"><span data-stu-id="d3726-167">-Force</span></span>

<span data-ttu-id="d3726-168">Erzwingt, dass dieses Cmdlet ein Element erstellt, das ein vorhandenes Schreib geschütztes Element überschreibt.</span><span class="sxs-lookup"><span data-stu-id="d3726-168">Forces this cmdlet to create an item that writes over an existing read-only item.</span></span> <span data-ttu-id="d3726-169">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="d3726-169">Implementation varies from provider to provider.</span></span> <span data-ttu-id="d3726-170">Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="d3726-170">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="d3726-171">-ItemType</span><span class="sxs-lookup"><span data-stu-id="d3726-171">-ItemType</span></span>

<span data-ttu-id="d3726-172">Gibt den vom Anbieter angegebenen Typ des neuen Elements an.</span><span class="sxs-lookup"><span data-stu-id="d3726-172">Specifies the provider-specified type of the new item.</span></span> <span data-ttu-id="d3726-173">Die verfügbaren Werte dieses Parameters hängen vom aktuellen Anbieter ab, den Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3726-173">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="d3726-174">Wenn sich ihr Speicherort in einem `FileSystem` Laufwerk befindet, sind folgende Werte zulässig:</span><span class="sxs-lookup"><span data-stu-id="d3726-174">If your location is in a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="d3726-175">Datei</span><span class="sxs-lookup"><span data-stu-id="d3726-175">File</span></span>
- <span data-ttu-id="d3726-176">Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="d3726-176">Directory</span></span>
- <span data-ttu-id="d3726-177">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="d3726-177">SymbolicLink</span></span>
- <span data-ttu-id="d3726-178">Verbindung</span><span class="sxs-lookup"><span data-stu-id="d3726-178">Junction</span></span>
- <span data-ttu-id="d3726-179">HardLink</span><span class="sxs-lookup"><span data-stu-id="d3726-179">HardLink</span></span>

> [!NOTE]
> <span data-ttu-id="d3726-180">Zum Erstellen eines Windows-Typs ist eine `SymbolicLink` Erhöhung als Administrator erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d3726-180">Creating a `SymbolicLink` type on Windows requires elevation as administrator.</span></span> <span data-ttu-id="d3726-181">Allerdings erfordert Windows 10 (Build 14972 oder höher) mit aktiviertem Entwicklermodus nicht mehr die Erhöhung von symbolischen Verknüpfungen.</span><span class="sxs-lookup"><span data-stu-id="d3726-181">However, Windows 10 (build 14972 or newer) with Developer Mode enabled no longer requires elevation creating symbolic links.</span></span>

<span data-ttu-id="d3726-182">In einem `Certificate` Laufwerk sind dies die Werte, die Sie angeben können:</span><span class="sxs-lookup"><span data-stu-id="d3726-182">In a `Certificate` drive, these are the values you can specify:</span></span>

- <span data-ttu-id="d3726-183">Zertifikat-Anbieter</span><span class="sxs-lookup"><span data-stu-id="d3726-183">Certificate Provider</span></span>
- <span data-ttu-id="d3726-184">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="d3726-184">Certificate</span></span>
- <span data-ttu-id="d3726-185">Speicher</span><span class="sxs-lookup"><span data-stu-id="d3726-185">Store</span></span>
- <span data-ttu-id="d3726-186">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="d3726-186">StoreLocation</span></span>

<span data-ttu-id="d3726-187">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d3726-187">For more information see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d3726-188">-Name</span><span class="sxs-lookup"><span data-stu-id="d3726-188">-Name</span></span>

<span data-ttu-id="d3726-189">Gibt den Namen des neuen Elements an.</span><span class="sxs-lookup"><span data-stu-id="d3726-189">Specifies the name of the new item.</span></span> <span data-ttu-id="d3726-190">Sie können den Namen des neuen Elements im **Name** -oder **path** -Parameterwert angeben, und Sie können den Pfad des neuen Elements im **Name** -oder **path** -Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="d3726-190">You can specify the name of the new item in the **Name** or **Path** parameter value, and you can specify the path of the new item in **Name** or **Path** value.</span></span> <span data-ttu-id="d3726-191">Elementnamen, die mit dem **Name** -Parameter übergeben werden, werden relativ zum Wert des **path** -Parameters erstellt.</span><span class="sxs-lookup"><span data-stu-id="d3726-191">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: nameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d3726-192">-Path</span><span class="sxs-lookup"><span data-stu-id="d3726-192">-Path</span></span>

<span data-ttu-id="d3726-193">Gibt den Pfad zum Speicherort des neuen Elements an.</span><span class="sxs-lookup"><span data-stu-id="d3726-193">Specifies the path of the location of the new item.</span></span> <span data-ttu-id="d3726-194">Der Standardwert ist der aktuelle Speicherort, wenn der **Pfad** weggelassen wird.</span><span class="sxs-lookup"><span data-stu-id="d3726-194">The default is the current location when **Path** is omitted.</span></span> <span data-ttu-id="d3726-195">Sie können den Namen des neuen Elements im **Namen** angeben oder ihn in **path** einschließen.</span><span class="sxs-lookup"><span data-stu-id="d3726-195">You can specify the name of the new item in **Name** , or include it in **Path** .</span></span> <span data-ttu-id="d3726-196">Elementnamen, die mit dem **Name** -Parameter übergeben werden, werden relativ zum Wert des **path** -Parameters erstellt.</span><span class="sxs-lookup"><span data-stu-id="d3726-196">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

<span data-ttu-id="d3726-197">Für dieses Cmdlet funktioniert der **path** -Parameter wie der **literalpath** -Parameter anderer Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="d3726-197">For this cmdlet, the **Path** parameter works like the **LiteralPath** parameter of other cmdlets.</span></span>
<span data-ttu-id="d3726-198">Platzhalter Zeichen werden nicht interpretiert.</span><span class="sxs-lookup"><span data-stu-id="d3726-198">Wildcard characters are not interpreted.</span></span> <span data-ttu-id="d3726-199">Alle Zeichen werden an den Anbieter des Speicher Orts übermittelt.</span><span class="sxs-lookup"><span data-stu-id="d3726-199">All characters are passed to the location's provider.</span></span> <span data-ttu-id="d3726-200">Der Anbieter unterstützt möglicherweise nicht alle Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d3726-200">The provider may not support all characters.</span></span> <span data-ttu-id="d3726-201">Beispielsweise können Sie keinen Dateinamen erstellen, der ein Sternchen ( `*` ) enthält.</span><span class="sxs-lookup"><span data-stu-id="d3726-201">For example, you cannot create a filename that contains an asterisk (`*`) character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: pathSet, nameSet
Aliases:

Required: True (pathSet), False (nameSet)
Position: 0
Default value: Current location
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d3726-202">-Value</span><span class="sxs-lookup"><span data-stu-id="d3726-202">-Value</span></span>

<span data-ttu-id="d3726-203">Gibt den Wert des neuen Elements an.</span><span class="sxs-lookup"><span data-stu-id="d3726-203">Specifies the value of the new item.</span></span> <span data-ttu-id="d3726-204">Sie können einen Wert auch über die Pipeline an übergeben `New-Item` .</span><span class="sxs-lookup"><span data-stu-id="d3726-204">You can also pipe a value to `New-Item`.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Target

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d3726-205">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d3726-205">-Confirm</span></span>

<span data-ttu-id="d3726-206">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d3726-206">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d3726-207">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d3726-207">-WhatIf</span></span>

<span data-ttu-id="d3726-208">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d3726-208">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d3726-209">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d3726-209">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d3726-210">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d3726-210">CommonParameters</span></span>

<span data-ttu-id="d3726-211">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="d3726-211">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="d3726-212">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d3726-212">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d3726-213">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d3726-213">INPUTS</span></span>

### <span data-ttu-id="d3726-214">System.Object</span><span class="sxs-lookup"><span data-stu-id="d3726-214">System.Object</span></span>

<span data-ttu-id="d3726-215">Sie können einen Wert für das neue Element über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="d3726-215">You can pipe a value for the new item to this cmdlet.</span></span>

## <span data-ttu-id="d3726-216">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d3726-216">OUTPUTS</span></span>

### <span data-ttu-id="d3726-217">System.Object</span><span class="sxs-lookup"><span data-stu-id="d3726-217">System.Object</span></span>

<span data-ttu-id="d3726-218">Dieses Cmdlet gibt das Element zurück, das es erstellt.</span><span class="sxs-lookup"><span data-stu-id="d3726-218">This cmdlet returns the item that it creates.</span></span>

## <span data-ttu-id="d3726-219">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d3726-219">NOTES</span></span>

<span data-ttu-id="d3726-220">`New-Item` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d3726-220">`New-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d3726-221">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="d3726-221">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="d3726-222">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d3726-222">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="d3726-223">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d3726-223">RELATED LINKS</span></span>

[<span data-ttu-id="d3726-224">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="d3726-224">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="d3726-225">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="d3726-225">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="d3726-226">Get-Item</span><span class="sxs-lookup"><span data-stu-id="d3726-226">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="d3726-227">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="d3726-227">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="d3726-228">Move-Item</span><span class="sxs-lookup"><span data-stu-id="d3726-228">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="d3726-229">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d3726-229">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="d3726-230">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="d3726-230">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="d3726-231">Set-Item</span><span class="sxs-lookup"><span data-stu-id="d3726-231">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="d3726-232">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d3726-232">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
