---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 903c4eb784c1bb86b66766c7dfb563f586545dc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215612"
---
# <span data-ttu-id="1e641-103">Add-Content</span><span class="sxs-lookup"><span data-stu-id="1e641-103">Add-Content</span></span>

## <span data-ttu-id="1e641-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1e641-104">SYNOPSIS</span></span>
<span data-ttu-id="1e641-105">Fügt den angegebenen Elementen Inhalt hinzu, z. B. Hinzufügen von Wörtern in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="1e641-105">Adds content to the specified items, such as adding words to a file.</span></span>

## <span data-ttu-id="1e641-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1e641-106">SYNTAX</span></span>

### <span data-ttu-id="1e641-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="1e641-107">Path (Default)</span></span>

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### <span data-ttu-id="1e641-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1e641-108">LiteralPath</span></span>

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

## <span data-ttu-id="1e641-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1e641-109">DESCRIPTION</span></span>

<span data-ttu-id="1e641-110">Das- `Add-Content` Cmdlet fügt Inhalt an ein angegebenes Element oder eine angegebene Datei an.</span><span class="sxs-lookup"><span data-stu-id="1e641-110">The `Add-Content` cmdlet appends content to a specified item or file.</span></span> <span data-ttu-id="1e641-111">Sie können den Inhalt angeben, indem Sie den Inhalt im Befehl eingeben oder ein Objekt angeben, das den Inhalt enthält.</span><span class="sxs-lookup"><span data-stu-id="1e641-111">You can specify the content by typing the content in the command or by specifying an object that contains the content.</span></span>

<span data-ttu-id="1e641-112">Wenn Sie für die folgenden Beispiele Dateien oder Verzeichnisse erstellen müssen, finden Sie weitere Informationen unter [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="1e641-112">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="1e641-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1e641-113">EXAMPLES</span></span>

### <span data-ttu-id="1e641-114">Beispiel 1: Hinzufügen einer Zeichenfolge zu allen Textdateien mit einer Ausnahme</span><span class="sxs-lookup"><span data-stu-id="1e641-114">Example 1: Add a string to all text files with an exception</span></span>

<span data-ttu-id="1e641-115">In diesem Beispiel wird ein Wert an Textdateien im aktuellen Verzeichnis angehängt, die Dateien werden jedoch nicht auf Grundlage ihres Datei namens ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1e641-115">This example appends a value to text files in the current directory but excludes files based on their file name.</span></span>

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

<span data-ttu-id="1e641-116">Das `Add-Content` Cmdlet verwendet den **path** -Parameter, um alle txt-Dateien im aktuellen Verzeichnis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1e641-116">The `Add-Content` cmdlet uses the **Path** parameter to specify all .txt files in the current directory.</span></span> <span data-ttu-id="1e641-117">Mit dem **Exclude** -Parameter werden Dateinamen ignoriert, die dem angegebenen Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1e641-117">The **Exclude** parameter ignores file names that match the specified pattern.</span></span> <span data-ttu-id="1e641-118">Der **value** -Parameter gibt die Text Zeichenfolge an, die in die Dateien geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="1e641-118">The **Value** parameter specifies the text string that is written to the files.</span></span>

<span data-ttu-id="1e641-119">Verwenden [Sie Get-Content](Get-Content.md) , um den Inhalt dieser Dateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1e641-119">Use [Get-Content](Get-Content.md) to display the contents of these files.</span></span>

### <span data-ttu-id="1e641-120">Beispiel 2: Hinzufügen eines Datums am Ende der angegebenen Dateien</span><span class="sxs-lookup"><span data-stu-id="1e641-120">Example 2: Add a date to the end of the specified files</span></span>

<span data-ttu-id="1e641-121">In diesem Beispiel wird das Datum an Dateien im aktuellen Verzeichnis angehängt, und das Datum wird in der PowerShell-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e641-121">This example appends the date to files in the current directory and displays the date in the PowerShell console.</span></span>

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

<span data-ttu-id="1e641-122">Das `Add-Content` Cmdlet verwendet die **path** -und **value** -Parameter, um zwei neue Dateien im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e641-122">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create two new files in the current directory.</span></span> <span data-ttu-id="1e641-123">Der **value** -Parameter gibt das `Get-Date` Cmdlet an, um das Datum zu erhalten, und übergibt das Datum an `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="1e641-123">The **Value** parameter specifies the `Get-Date` cmdlet to get the date and passes the date to `Add-Content`.</span></span> <span data-ttu-id="1e641-124">Mit dem- `Add-Content` Cmdlet wird das Datum in jede Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="1e641-124">The `Add-Content` cmdlet writes the date to each file.</span></span> <span data-ttu-id="1e641-125">Der **passthru** -Parameter übergibt ein Objekt, das das Date-Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="1e641-125">The **PassThru** parameter passes an object that represents the date object.</span></span> <span data-ttu-id="1e641-126">Da kein anderes Cmdlet vorhanden ist, um das über gegebene Objekt zu empfangen, wird es in der PowerShell-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e641-126">Because there is no other cmdlet to receive the passed object, it is displayed in the PowerShell console.</span></span> <span data-ttu-id="1e641-127">Mit dem- `Get-Content` Cmdlet wird die aktualisierte Datei DateTimeFile1. Log angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e641-127">The `Get-Content` cmdlet displays the updated file, DateTimeFile1.log.</span></span>

### <span data-ttu-id="1e641-128">Beispiel 3: Hinzufügen des Inhalts einer angegebenen Datei zu einer anderen Datei</span><span class="sxs-lookup"><span data-stu-id="1e641-128">Example 3: Add the contents of a specified file to another file</span></span>

<span data-ttu-id="1e641-129">In diesem Beispiel wird der Inhalt aus einer Datei abgerufen, und dieser Inhalt wird an eine andere Datei angehängt.</span><span class="sxs-lookup"><span data-stu-id="1e641-129">This example gets the content from a file and appends that content into another file.</span></span>

```powershell
Add-Content -Path .\CopyToFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="1e641-130">Das `Add-Content` Cmdlet verwendet den **path** -Parameter, um die neue Datei im aktuellen Verzeichnis anzugeben, CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="1e641-130">The `Add-Content` cmdlet uses the **Path** parameter to specify the new file in the current directory, CopyToFile.txt.</span></span> <span data-ttu-id="1e641-131">Der **value** -Parameter verwendet das- `Get-Content` Cmdlet, um den Inhalt der Datei CopyFromFile.txt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1e641-131">The **Value** parameter uses the `Get-Content` cmdlet to get the contents of the file, CopyFromFile.txt.</span></span> <span data-ttu-id="1e641-132">Die Klammern um das `Get-Content` Cmdlet stellen sicher, dass der Befehl abgeschlossen ist, bevor der `Add-Content` Befehl beginnt.</span><span class="sxs-lookup"><span data-stu-id="1e641-132">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span> <span data-ttu-id="1e641-133">Der **value** -Parameter wird an übergeben `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="1e641-133">The **Value** parameter is passed to `Add-Content`.</span></span> <span data-ttu-id="1e641-134">Das- `Add-Content` Cmdlet fügt die Daten an die CopyToFile.txt Datei an.</span><span class="sxs-lookup"><span data-stu-id="1e641-134">The `Add-Content` cmdlet appends the data to the CopyToFile.txt file.</span></span> <span data-ttu-id="1e641-135">Das- `Get-Content` Cmdlet zeigt die aktualisierte Datei an, CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="1e641-135">The `Get-Content` cmdlet displays the updated file, CopyToFile.txt.</span></span>

### <span data-ttu-id="1e641-136">Beispiel 4: Verwenden einer Variablen zum Hinzufügen des Inhalts einer angegebenen Datei zu einer anderen Datei</span><span class="sxs-lookup"><span data-stu-id="1e641-136">Example 4: Use a variable to add the contents of a specified file to another file</span></span>

<span data-ttu-id="1e641-137">In diesem Beispiel wird der Inhalt aus einer Datei abgerufen und der Inhalt in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1e641-137">This example gets the content from a file and stores the content in a variable.</span></span> <span data-ttu-id="1e641-138">Die-Variable wird verwendet, um den Inhalt an eine andere Datei anzufügen.</span><span class="sxs-lookup"><span data-stu-id="1e641-138">The variable is used to append the content into another file.</span></span>

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="1e641-139">Mit dem `Get-Content` -Cmdlet wird der Inhalt CopyFromFile.txt abgerufen und der Inhalt in der `$From` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1e641-139">The `Get-Content` cmdlet gets the contents of CopyFromFile.txt and stores the contents in the `$From` variable.</span></span> <span data-ttu-id="1e641-140">Das `Add-Content` Cmdlet verwendet den **path** -Parameter, um die CopyToFile.txt Datei im aktuellen Verzeichnis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1e641-140">The `Add-Content` cmdlet uses the **Path** parameter to specify the CopyToFile.txt file in the current directory.</span></span> <span data-ttu-id="1e641-141">Der **value** -Parameter verwendet die `$From` -Variable und übergibt den Inhalt an `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="1e641-141">The **Value** parameter uses the `$From` variable and passes the content to `Add-Content`.</span></span> <span data-ttu-id="1e641-142">Mit dem- `Add-Content` Cmdlet wird die CopyToFile.txt Datei aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="1e641-142">The `Add-Content` cmdlet updates the CopyToFile.txt file.</span></span> <span data-ttu-id="1e641-143">Das- `Get-Content` Cmdlet zeigt CopyToFile.txt an.</span><span class="sxs-lookup"><span data-stu-id="1e641-143">The `Get-Content` cmdlet displays CopyToFile.txt.</span></span>

### <span data-ttu-id="1e641-144">Beispiel 5: Erstellen einer neuen Datei und Kopieren von Inhalten</span><span class="sxs-lookup"><span data-stu-id="1e641-144">Example 5: Create a new file and copy content</span></span>

<span data-ttu-id="1e641-145">In diesem Beispiel wird eine neue Datei erstellt und der Inhalt einer vorhandenen Datei in die neue Datei kopiert.</span><span class="sxs-lookup"><span data-stu-id="1e641-145">This example creates a new file and copies an existing file's content into the new file.</span></span>

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

<span data-ttu-id="1e641-146">Das `Add-Content` Cmdlet verwendet die **path** -und **value** -Parameter, um eine neue Datei im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e641-146">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create a new file in the current directory.</span></span> <span data-ttu-id="1e641-147">Der **value** -Parameter verwendet das- `Get-Content` Cmdlet, um den Inhalt einer vorhandenen Datei, CopyFromFile.txt, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1e641-147">The **Value** parameter uses the `Get-Content` cmdlet to get the contents of an existing file, CopyFromFile.txt.</span></span> <span data-ttu-id="1e641-148">Die Klammern um das `Get-Content` Cmdlet stellen sicher, dass der Befehl abgeschlossen ist, bevor der `Add-Content` Befehl beginnt.</span><span class="sxs-lookup"><span data-stu-id="1e641-148">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span> <span data-ttu-id="1e641-149">Der **value** -Parameter übergibt den Inhalt, an `Add-Content` den die NewFile.txt Datei aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="1e641-149">The **Value** parameter passes the content to `Add-Content` which updates the NewFile.txt file.</span></span> <span data-ttu-id="1e641-150">Das- `Get-Content` Cmdlet zeigt den Inhalt der neuen Datei an, NewFile.txt.</span><span class="sxs-lookup"><span data-stu-id="1e641-150">The `Get-Content` cmdlet displays the contents of the new file, NewFile.txt.</span></span>

### <span data-ttu-id="1e641-151">Beispiel 6: Hinzufügen von Inhalt zu einer schreibgeschützten Datei</span><span class="sxs-lookup"><span data-stu-id="1e641-151">Example 6: Add content to a read-only file</span></span>

<span data-ttu-id="1e641-152">Mit diesem Befehl wird der Datei der Wert hinzugefügt, auch wenn das Attribut " **isread only** " auf "true" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1e641-152">This command adds the value to the file even if the **IsReadOnly** file attribute is set to True.</span></span>
<span data-ttu-id="1e641-153">Die Schritte zum Erstellen einer schreibgeschützten Datei sind im Beispiel enthalten.</span><span class="sxs-lookup"><span data-stu-id="1e641-153">The steps to create a read-only file are included in the example.</span></span>

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
-ar---        1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

<span data-ttu-id="1e641-154">Das `New-Item` Cmdlet verwendet den **path** -Parameter und den **ItemType** -Parameter, um die Datei IsReadOnlyTextFile.txt im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e641-154">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the file IsReadOnlyTextFile.txt in the current directory.</span></span> <span data-ttu-id="1e641-155">Das `Set-ItemProperty` Cmdlet verwendet die Parameter **Name** und **value** , um die **isschreib only** -Eigenschaft der Datei in true zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1e641-155">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to True.</span></span> <span data-ttu-id="1e641-156">Das `Get-ChildItem` Cmdlet zeigt, dass die Datei leer ist (0) und das schreibgeschützte Attribut ( `r` ) aufweist.</span><span class="sxs-lookup"><span data-stu-id="1e641-156">The `Get-ChildItem` cmdlet shows the file is empty (0) and has the read-only attribute (`r`).</span></span> <span data-ttu-id="1e641-157">Das `Add-Content` Cmdlet verwendet den **path** -Parameter, um die Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1e641-157">The `Add-Content` cmdlet uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="1e641-158">Der **value** -Parameter enthält die Text Zeichenfolge, die an die Datei angefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1e641-158">The **Value** parameter includes the text string to append to the file.</span></span> <span data-ttu-id="1e641-159">Mit dem **Force** -Parameter wird der Text in die schreibgeschützte Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="1e641-159">The **Force** parameter writes the text to the read-only file.</span></span> <span data-ttu-id="1e641-160">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um den Inhalt der Datei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1e641-160">The `Get-Content` cmdlet uses the **Path** parameter to display the file's contents.</span></span>

<span data-ttu-id="1e641-161">Um das schreibgeschützte Attribut zu entfernen, verwenden Sie den- `Set-ItemProperty` Befehl, bei dem der **value** -Parameter auf festgelegt ist `False` .</span><span class="sxs-lookup"><span data-stu-id="1e641-161">To remove the read-only attribute, use the `Set-ItemProperty` command with the **Value** parameter set to `False`.</span></span>

## <span data-ttu-id="1e641-162">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1e641-162">PARAMETERS</span></span>

### <span data-ttu-id="1e641-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1e641-163">-Confirm</span></span>

<span data-ttu-id="1e641-164">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="1e641-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1e641-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="1e641-165">-Credential</span></span>

<span data-ttu-id="1e641-166">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="1e641-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="1e641-167">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1e641-167">The default is the current user.</span></span>

<span data-ttu-id="1e641-168">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="1e641-168">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="1e641-169">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="1e641-169">If you type a user name, you will be prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="1e641-170">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1e641-170">This parameter is not supported by any providers installed with PowerShell.</span></span>

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

### <span data-ttu-id="1e641-171">-Codierung</span><span class="sxs-lookup"><span data-stu-id="1e641-171">-Encoding</span></span>

<span data-ttu-id="1e641-172">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="1e641-172">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="1e641-173">Der Standardwert ist `Default`.</span><span class="sxs-lookup"><span data-stu-id="1e641-173">The default value is `Default`.</span></span>

<span data-ttu-id="1e641-174">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1e641-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="1e641-175">`Ascii` Verwendet den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="1e641-175">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="1e641-176">`BigEndianUnicode` Verwendet UTF-16 mit der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="1e641-176">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="1e641-177">`BigEndianUTF32` Verwendet UTF-32 mit der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="1e641-177">`BigEndianUTF32` Uses UTF-32 with the big-endian byte order.</span></span>
- <span data-ttu-id="1e641-178">`Byte` Codiert eine Reihe von Zeichen in eine Bytefolge.</span><span class="sxs-lookup"><span data-stu-id="1e641-178">`Byte` Encodes a set of characters into a sequence of bytes.</span></span>
- <span data-ttu-id="1e641-179">`Default` Verwendet die Codierung, die der aktiven Codepage des Systems entspricht (normalerweise ANSI).</span><span class="sxs-lookup"><span data-stu-id="1e641-179">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="1e641-180">`Oem` Verwendet die Codierung, die der aktuellen OEM-Codepage des Systems entspricht.</span><span class="sxs-lookup"><span data-stu-id="1e641-180">`Oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="1e641-181">`String` Identisch mit **Unicode** .</span><span class="sxs-lookup"><span data-stu-id="1e641-181">`String` Same as **Unicode** .</span></span>
- <span data-ttu-id="1e641-182">`Unicode` Verwendet UTF-16 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="1e641-182">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="1e641-183">`Unknown` Identisch mit **Unicode** .</span><span class="sxs-lookup"><span data-stu-id="1e641-183">`Unknown` Same as **Unicode** .</span></span>
- <span data-ttu-id="1e641-184">`UTF7` Verwendet UTF-7.</span><span class="sxs-lookup"><span data-stu-id="1e641-184">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="1e641-185">`UTF8` Verwendet UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1e641-185">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="1e641-186">`UTF32` Verwendet UTF-32 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="1e641-186">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="1e641-187">Encoding ist ein dynamischer Parameter, den der File System-Anbieter zum `Add-Content` Cmdlet hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="1e641-187">Encoding is a dynamic parameter that the FileSystem provider adds to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="1e641-188">Dieser Parameter funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="1e641-188">This parameter works only in file system drives.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, Byte, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e641-189">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="1e641-189">-Exclude</span></span>

<span data-ttu-id="1e641-190">Lässt die angegebenen Elemente aus.</span><span class="sxs-lookup"><span data-stu-id="1e641-190">Omits the specified items.</span></span> <span data-ttu-id="1e641-191">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="1e641-191">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="1e641-192">Geben Sie ein Pfad Element oder-Muster ein, z. b **\* . txt** .</span><span class="sxs-lookup"><span data-stu-id="1e641-192">Enter a path element or pattern, such as **\*.txt** .</span></span> <span data-ttu-id="1e641-193">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="1e641-193">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="1e641-194">-Filter</span><span class="sxs-lookup"><span data-stu-id="1e641-194">-Filter</span></span>

<span data-ttu-id="1e641-195">Gibt einen Filter im Format oder in der Sprache des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="1e641-195">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="1e641-196">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="1e641-196">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="1e641-197">Die Syntax des Filters einschließlich der Verwendung von Platzhaltern ist vom Anbieter abhängig.</span><span class="sxs-lookup"><span data-stu-id="1e641-197">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="1e641-198">**Filter** sind effizienter als andere Parameter, da der Anbieter beim Abrufen von Objekten Filter anwendet.</span><span class="sxs-lookup"><span data-stu-id="1e641-198">**Filters** are more efficient than other parameters because the provider applies filters when objects are retrieved.</span></span> <span data-ttu-id="1e641-199">Andernfalls verarbeitet PowerShell Filter, nachdem die Objekte abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="1e641-199">Otherwise, PowerShell processes filters after the objects are retrieved.</span></span>

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

### <span data-ttu-id="1e641-200">-Force</span><span class="sxs-lookup"><span data-stu-id="1e641-200">-Force</span></span>

<span data-ttu-id="1e641-201">Überschreibt das Schreibschutzattribut, sodass Sie einer schreibgeschützten Datei Inhalt hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="1e641-201">Overrides the read-only attribute, allowing you to add content to a read-only file.</span></span> <span data-ttu-id="1e641-202">Beispielsweise überschreibt **Force** das Schreibschutzattribut oder erstellt Verzeichnisse zum Vervollständigen eines Dateipfads. Es wird jedoch nicht etwa versucht, Dateiberechtigungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1e641-202">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="1e641-203">-Include</span><span class="sxs-lookup"><span data-stu-id="1e641-203">-Include</span></span>

<span data-ttu-id="1e641-204">Fügt nur die angegebenen Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="1e641-204">Adds only the specified items.</span></span> <span data-ttu-id="1e641-205">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="1e641-205">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="1e641-206">Geben Sie ein Pfad Element oder-Muster ein, z. b **\* . txt** .</span><span class="sxs-lookup"><span data-stu-id="1e641-206">Enter a path element or pattern, such as **\*.txt** .</span></span> <span data-ttu-id="1e641-207">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="1e641-207">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="1e641-208">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="1e641-208">-LiteralPath</span></span>

<span data-ttu-id="1e641-209">Gibt den Pfad zu den Elementen an, die den zusätzlichen Inhalt erhalten.</span><span class="sxs-lookup"><span data-stu-id="1e641-209">Specifies the path to the items that receive the additional content.</span></span> <span data-ttu-id="1e641-210">Im Gegensatz zu **Path** wird der Wert von **LiteralPath** genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="1e641-210">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="1e641-211">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="1e641-211">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="1e641-212">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="1e641-212">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="1e641-213">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="1e641-213">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1e641-214">-Nonewline</span><span class="sxs-lookup"><span data-stu-id="1e641-214">-NoNewline</span></span>

<span data-ttu-id="1e641-215">Gibt an, dass dieses Cmdlet keine neue Zeile oder Wagen Rücklauf zum Inhalt hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="1e641-215">Indicates that this cmdlet does not add a new line or carriage return to the content.</span></span>

<span data-ttu-id="1e641-216">Die Zeichen folgen Darstellungen der Eingabe Objekte werden verkettet, um die Ausgabe zu bilden.</span><span class="sxs-lookup"><span data-stu-id="1e641-216">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="1e641-217">Zwischen den Ausgabe Zeichenfolgen werden keine Leerzeichen oder Zeilenumbrüche eingefügt.</span><span class="sxs-lookup"><span data-stu-id="1e641-217">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="1e641-218">Nach der letzten Ausgabe Zeichenfolge wird kein Zeilen Vorstrich hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1e641-218">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="1e641-219">-PassThru</span><span class="sxs-lookup"><span data-stu-id="1e641-219">-PassThru</span></span>

<span data-ttu-id="1e641-220">Gibt ein Objekt zurück, das den hinzugefügten Inhalt darstellt.</span><span class="sxs-lookup"><span data-stu-id="1e641-220">Returns an object representing the added content.</span></span> <span data-ttu-id="1e641-221">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="1e641-221">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="1e641-222">-Path</span><span class="sxs-lookup"><span data-stu-id="1e641-222">-Path</span></span>

<span data-ttu-id="1e641-223">Gibt den Pfad zu den Elementen an, die den zusätzlichen Inhalt erhalten.</span><span class="sxs-lookup"><span data-stu-id="1e641-223">Specifies the path to the items that receive the additional content.</span></span> <span data-ttu-id="1e641-224">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="1e641-224">Wildcards are permitted.</span></span> <span data-ttu-id="1e641-225">Wenn Sie mehrere Pfade angeben, trennen Sie diese durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="1e641-225">If you specify multiple paths, use commas to separate the paths.</span></span>

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

### <span data-ttu-id="1e641-226">-Stream</span><span class="sxs-lookup"><span data-stu-id="1e641-226">-Stream</span></span>

<span data-ttu-id="1e641-227">Gibt einen alternativen Datenstrom für den Inhalt an.</span><span class="sxs-lookup"><span data-stu-id="1e641-227">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="1e641-228">Wenn der Datenstrom nicht vorhanden ist, wird er von diesem Cmdlet erstellt.</span><span class="sxs-lookup"><span data-stu-id="1e641-228">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="1e641-229">Platzhalterzeichen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1e641-229">Wildcard characters are not supported.</span></span>

<span data-ttu-id="1e641-230">**Stream** ist ein dynamischer Parameter, den der File System-Anbieter hinzufügt `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="1e641-230">**Stream** is a dynamic parameter that the FileSystem provider adds to `Add-Content`.</span></span> <span data-ttu-id="1e641-231">Dieser Parameter funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="1e641-231">This parameter works only in file system drives.</span></span>

<span data-ttu-id="1e641-232">Sie können das `Add-Content` Cmdlet verwenden, um den Inhalt des alternativen Datenstroms " **Zone. Identifier** " zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1e641-232">You can use the `Add-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="1e641-233">Dies wird jedoch nicht empfohlen, um Sicherheitsüberprüfungen zu vermeiden, die Dateien blockieren, die aus dem Internet heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="1e641-233">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="1e641-234">Wenn Sie überprüfen, ob eine heruntergeladene Datei sicher ist, verwenden Sie das- `Unblock-File` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e641-234">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="1e641-235">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1e641-235">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="1e641-236">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="1e641-236">-UseTransaction</span></span>

<span data-ttu-id="1e641-237">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="1e641-237">Includes the command in the active transaction.</span></span> <span data-ttu-id="1e641-238">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1e641-238">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="1e641-239">Weitere Informationen finden Sie unter [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="1e641-239">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e641-240">-Value</span><span class="sxs-lookup"><span data-stu-id="1e641-240">-Value</span></span>

<span data-ttu-id="1e641-241">Gibt den hinzuzufügenden Inhalt an.</span><span class="sxs-lookup"><span data-stu-id="1e641-241">Specifies the content to be added.</span></span> <span data-ttu-id="1e641-242">Geben Sie eine Zeichenfolge in Anführungszeichen ein, z. b. **diese Daten sind nur zur internen Verwendung vorgesehen** , oder geben Sie ein Objekt an, das Inhalt enthält, z. b. das **DateTime** -Objekt `Get-Date`</span><span class="sxs-lookup"><span data-stu-id="1e641-242">Type a quoted string, such as **This data is for internal use only** , or specify an object that contains content, such as the **DateTime** object that `Get-Date` generates.</span></span>

<span data-ttu-id="1e641-243">Sie können den Inhalt einer Datei nicht angeben, indem Sie Ihren Pfad eingeben, da der Pfad lediglich eine Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="1e641-243">You cannot specify the contents of a file by typing its path, because the path is just a string.</span></span>
<span data-ttu-id="1e641-244">Sie können einen `Get-Content` Befehl verwenden, um den Inhalt zu erhalten und an den **value** -Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="1e641-244">You can use a `Get-Content` command to get the content and pass it to the **Value** parameter.</span></span>

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

### <span data-ttu-id="1e641-245">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1e641-245">-WhatIf</span></span>

<span data-ttu-id="1e641-246">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1e641-246">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1e641-247">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1e641-247">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1e641-248">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1e641-248">CommonParameters</span></span>

<span data-ttu-id="1e641-249">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="1e641-249">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="1e641-250">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1e641-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1e641-251">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1e641-251">INPUTS</span></span>

### <span data-ttu-id="1e641-252">System. Object, System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="1e641-252">System.Object, System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="1e641-253">Sie können Werte, Pfade oder Anmelde Informationen an übergeben `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="1e641-253">You can pipe values, paths, or credentials to `Set-Content`.</span></span>

## <span data-ttu-id="1e641-254">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1e641-254">OUTPUTS</span></span>

### <span data-ttu-id="1e641-255">None or System.String</span><span class="sxs-lookup"><span data-stu-id="1e641-255">None or System.String</span></span>

<span data-ttu-id="1e641-256">Wenn Sie den **passthru** -Parameter verwenden, `Add-Content` generiert ein **System. String** -Objekt, das den Inhalt darstellt.</span><span class="sxs-lookup"><span data-stu-id="1e641-256">When you use the **PassThru** parameter, `Add-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="1e641-257">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="1e641-257">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1e641-258">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1e641-258">NOTES</span></span>

<span data-ttu-id="1e641-259">Wenn Sie ein Objekt an übergeben `Add-Content` , wird das Objekt in eine Zeichenfolge konvertiert, bevor es dem Element hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="1e641-259">When you pipe an object to `Add-Content`, the object is converted to a string before it is added to the item.</span></span> <span data-ttu-id="1e641-260">Der Objekttyp bestimmt das Zeichenfolgenformat, das Format kann jedoch von der Standardanzeige des Objekts abweichen.</span><span class="sxs-lookup"><span data-stu-id="1e641-260">The object type determines the string format, but the format might be different than the default display of the object.</span></span> <span data-ttu-id="1e641-261">Verwenden Sie die Formatierungsparameter des sendenden Cmdlets zum Steuern des Zeichenfolgenformats.</span><span class="sxs-lookup"><span data-stu-id="1e641-261">To control the string format, use the formatting parameters of the sending cmdlet.</span></span>

<span data-ttu-id="1e641-262">Sie können auch auf den `Add-Content` integrierten Alias verweisen `ac` .</span><span class="sxs-lookup"><span data-stu-id="1e641-262">You can also refer to `Add-Content` by its built-in alias, `ac`.</span></span> <span data-ttu-id="1e641-263">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="1e641-263">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="1e641-264">Das- `Add-Content` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="1e641-264">The `Add-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="1e641-265">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="1e641-265">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="1e641-266">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="1e641-266">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="1e641-267">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1e641-267">RELATED LINKS</span></span>

[<span data-ttu-id="1e641-268">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="1e641-268">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="1e641-269">about_Providers</span><span class="sxs-lookup"><span data-stu-id="1e641-269">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="1e641-270">about_Transactions</span><span class="sxs-lookup"><span data-stu-id="1e641-270">about_Transactions</span></span>](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[<span data-ttu-id="1e641-271">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="1e641-271">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="1e641-272">Get-Content</span><span class="sxs-lookup"><span data-stu-id="1e641-272">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="1e641-273">Get-Item</span><span class="sxs-lookup"><span data-stu-id="1e641-273">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="1e641-274">New-Item</span><span class="sxs-lookup"><span data-stu-id="1e641-274">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="1e641-275">Set-Content</span><span class="sxs-lookup"><span data-stu-id="1e641-275">Set-Content</span></span>](Set-Content.md)
