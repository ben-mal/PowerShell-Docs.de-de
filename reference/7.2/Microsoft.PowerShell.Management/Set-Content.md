---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: d85e0219c325de998c5874224a33ac4263b787a3
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "99601917"
---
# <span data-ttu-id="95b70-102">Set-Content</span><span class="sxs-lookup"><span data-stu-id="95b70-102">Set-Content</span></span>

## <span data-ttu-id="95b70-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="95b70-103">SYNOPSIS</span></span>
<span data-ttu-id="95b70-104">Schreibt neuen Inhalt oder ersetzt vorhandene Inhalte in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="95b70-104">Writes new content or replaces existing content in a file.</span></span>

## <span data-ttu-id="95b70-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="95b70-105">SYNTAX</span></span>

### <span data-ttu-id="95b70-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="95b70-106">Path (Default)</span></span>

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="95b70-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="95b70-107">LiteralPath</span></span>

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="95b70-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="95b70-108">DESCRIPTION</span></span>

<span data-ttu-id="95b70-109">`Set-Content` ist ein Cmdlet für die Zeichen folgen Verarbeitung, das neuen Inhalt schreibt oder den Inhalt in einer Datei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="95b70-109">`Set-Content` is a string-processing cmdlet that writes new content or replaces the content in a file.</span></span> <span data-ttu-id="95b70-110">`Set-Content` ersetzt den vorhandenen Inhalt und unterscheidet sich von dem `Add-Content` Cmdlet, das Inhalt an eine Datei anfügt.</span><span class="sxs-lookup"><span data-stu-id="95b70-110">`Set-Content` replaces the existing content and differs from the `Add-Content` cmdlet that appends content to a file.</span></span> <span data-ttu-id="95b70-111">Wenn Sie Inhalte an senden möchten, `Set-Content` können Sie den **value** -Parameter in der Befehlszeile verwenden oder Inhalt über die Pipeline senden.</span><span class="sxs-lookup"><span data-stu-id="95b70-111">To send content to `Set-Content` you can use the **Value** parameter on the command line or send content through the pipeline.</span></span>

<span data-ttu-id="95b70-112">Wenn Sie für die folgenden Beispiele Dateien oder Verzeichnisse erstellen müssen, finden Sie weitere Informationen unter [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="95b70-112">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="95b70-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="95b70-113">EXAMPLES</span></span>

### <span data-ttu-id="95b70-114">Beispiel 1: Ersetzen des Inhalts mehrerer Dateien in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="95b70-114">Example 1: Replace the contents of multiple files in a directory</span></span>

<span data-ttu-id="95b70-115">In diesem Beispiel wird der Inhalt für mehrere Dateien im aktuellen Verzeichnis ersetzt.</span><span class="sxs-lookup"><span data-stu-id="95b70-115">This example replaces the content for multiple files in the current directory.</span></span>

```powershell
Get-ChildItem -Path .\Test*.txt
```

```Output
Test1.txt
Test2.txt
Test3.txt
```

```powershell
Set-Content -Path .\Test*.txt -Value 'Hello, World'
Get-Content -Path .\Test*.txt
```

```Output
Hello, World
Hello, World
Hello, World
```

<span data-ttu-id="95b70-116">Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um **txt** -Dateien aufzulisten, die mit `Test*` im aktuellen Verzeichnis beginnen.</span><span class="sxs-lookup"><span data-stu-id="95b70-116">The `Get-ChildItem` cmdlet uses the **Path** parameter to list **.txt** files that begin with `Test*` in the current directory.</span></span> <span data-ttu-id="95b70-117">Das `Set-Content` Cmdlet verwendet den **path** -Parameter, um die `Test*.txt` Dateien anzugeben.</span><span class="sxs-lookup"><span data-stu-id="95b70-117">The `Set-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files.</span></span> <span data-ttu-id="95b70-118">Der **value** -Parameter stellt die Text Zeichenfolge **Hello, World** dar, die den vorhandenen Inhalt in jeder Datei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="95b70-118">The **Value** parameter provides the text string **Hello, World** that replaces the existing content in each file.</span></span> <span data-ttu-id="95b70-119">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Dateien anzugeben, `Test*.txt` und zeigt den Inhalt jeder Datei in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="95b70-119">The `Get-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files and displays each file's content in the PowerShell console.</span></span>

### <span data-ttu-id="95b70-120">Beispiel 2: Erstellen einer neuen Datei und Schreiben von Inhalten</span><span class="sxs-lookup"><span data-stu-id="95b70-120">Example 2: Create a new file and write content</span></span>

<span data-ttu-id="95b70-121">In diesem Beispiel wird eine neue Datei erstellt, und das aktuelle Datum und die aktuelle Uhrzeit werden in die Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="95b70-121">This example creates a new file and writes the current date and time to the file.</span></span>

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

<span data-ttu-id="95b70-122">`Set-Content` verwendet die **path** -und **value** -Parameter, um eine neue Datei namens **DateTime.txt** im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="95b70-122">`Set-Content` uses the **Path** and **Value** parameters to create a new file named **DateTime.txt** in the current directory.</span></span> <span data-ttu-id="95b70-123">Der **value** -Parameter verwendet `Get-Date` , um das aktuelle Datum und die aktuelle Uhrzeit zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="95b70-123">The **Value** parameter uses `Get-Date` to get the current date and time.</span></span>
<span data-ttu-id="95b70-124">`Set-Content` schreibt das **DateTime** -Objekt als Zeichenfolge in die Datei.</span><span class="sxs-lookup"><span data-stu-id="95b70-124">`Set-Content` writes the **DateTime** object to the file as a string.</span></span> <span data-ttu-id="95b70-125">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um den Inhalt **DateTime.txt** in der PowerShell-Konsole anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="95b70-125">The `Get-Content` cmdlet uses the **Path** parameter to display the content of **DateTime.txt** in the PowerShell console.</span></span>

### <span data-ttu-id="95b70-126">Beispiel 3: Ersetzen von Text in einer Datei</span><span class="sxs-lookup"><span data-stu-id="95b70-126">Example 3: Replace text in a file</span></span>

<span data-ttu-id="95b70-127">Dieser Befehl ersetzt alle Instanzen von Word innerhalb einer vorhandenen Datei.</span><span class="sxs-lookup"><span data-stu-id="95b70-127">This command replaces all instances of word within an existing file.</span></span>

```powershell
Get-Content -Path .\Notice.txt
```

```Output
Warning
Replace Warning with a new word.
The word Warning was replaced.
```

```powershell
(Get-Content -Path .\Notice.txt) |
    ForEach-Object {$_ -Replace 'Warning', 'Caution'} |
        Set-Content -Path .\Notice.txt
Get-Content -Path .\Notice.txt
```

```Output
Caution
Replace Caution with a new word.
The word Caution was replaced.
```

<span data-ttu-id="95b70-128">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die **Notice.txt** Datei im aktuellen Verzeichnis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="95b70-128">The `Get-Content` cmdlet uses the **Path** parameter to specify the **Notice.txt** file in the current directory.</span></span> <span data-ttu-id="95b70-129">Der `Get-Content` Befehl wird in Klammern eingeschlossen, sodass der Befehl abgeschlossen ist, bevor er an die Pipeline gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="95b70-129">The `Get-Content` command is wrapped with parentheses so that the command finishes before being sent down the pipeline.</span></span>

<span data-ttu-id="95b70-130">Der Inhalt der **Notice.txt** Datei wird über die Pipeline an das `ForEach-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="95b70-130">The contents of the **Notice.txt** file are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span>
<span data-ttu-id="95b70-131">`ForEach-Object` verwendet die automatische Variable `$_` und ersetzt jedes Vorkommen von **Warning** durch **Vorsicht**.</span><span class="sxs-lookup"><span data-stu-id="95b70-131">`ForEach-Object` uses the automatic variable `$_` and replaces each occurrence of **Warning** with **Caution**.</span></span> <span data-ttu-id="95b70-132">Die Objekte werden über die Pipeline an das `Set-Content` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="95b70-132">The objects are sent down the pipeline to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="95b70-133">`Set-Content` verwendet den **path** -Parameter, um die **Notice.txt** Datei anzugeben und den aktualisierten Inhalt in die Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="95b70-133">`Set-Content` uses the **Path** parameter to specify the **Notice.txt** file and writes the updated content to the file.</span></span>

<span data-ttu-id="95b70-134">Das letzte `Get-Content` Cmdlet zeigt den aktualisierten Dateiinhalt in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="95b70-134">The last `Get-Content` cmdlet displays the updated file content in the PowerShell console.</span></span>

### <span data-ttu-id="95b70-135">Beispiel 4: Verwenden von Filtern mit Set-Content</span><span class="sxs-lookup"><span data-stu-id="95b70-135">Example 4: Use Filters with Set-Content</span></span>

<span data-ttu-id="95b70-136">Sie können einen Filter für das `Set-Content` Cmdlet angeben.</span><span class="sxs-lookup"><span data-stu-id="95b70-136">You can specify a filter to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="95b70-137">Wenn Sie den **path** -Parameter mithilfe von Filtern qualifizieren, müssen Sie ein nach gestelltes Sternchen () einfügen, `*` um den Inhalt des Pfads anzugeben.</span><span class="sxs-lookup"><span data-stu-id="95b70-137">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="95b70-138">Mit dem folgenden Befehl wird der Inhalt aller `*.txt` Dateien im `C:\Temp` Verzeichnis auf den leeren **Wert** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="95b70-138">The following command set the content all `*.txt` files in the `C:\Temp` directory to the **Value** empty.</span></span>

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## <span data-ttu-id="95b70-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="95b70-139">PARAMETERS</span></span>

### <span data-ttu-id="95b70-140">-Asbytestream</span><span class="sxs-lookup"><span data-stu-id="95b70-140">-AsByteStream</span></span>

<span data-ttu-id="95b70-141">Gibt an, dass der Inhalt als Byte Datenstrom gelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="95b70-141">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="95b70-142">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="95b70-142">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="95b70-143">Eine Warnung tritt auf, wenn Sie den **asbytestream** -Parameter mit dem **Encoding** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="95b70-143">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="95b70-144">Der **asbytestream** -Parameter ignoriert alle Codierungen, und die Ausgabe wird als Bytestream zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="95b70-144">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="95b70-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="95b70-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="95b70-146">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="95b70-146">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="95b70-147">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="95b70-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="95b70-148">-Codierung</span><span class="sxs-lookup"><span data-stu-id="95b70-148">-Encoding</span></span>

<span data-ttu-id="95b70-149">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="95b70-149">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="95b70-150">Der Standardwert ist `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="95b70-150">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="95b70-151">Encoding ist ein dynamischer Parameter, den der File System-Anbieter hinzufügt `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="95b70-151">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="95b70-152">Dieser Parameter funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="95b70-152">This parameter works only in file system drives.</span></span>

<span data-ttu-id="95b70-153">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="95b70-153">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="95b70-154">`ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="95b70-154">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="95b70-155">`bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="95b70-155">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="95b70-156">`bigendianutf32`: Codiert im UTF-32-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="95b70-156">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="95b70-157">`oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="95b70-157">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="95b70-158">`unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="95b70-158">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="95b70-159">`utf7`: Codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="95b70-159">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="95b70-160">`utf8`: Codiert im UTF-8-Format.</span><span class="sxs-lookup"><span data-stu-id="95b70-160">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="95b70-161">`utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="95b70-161">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="95b70-162">`utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="95b70-162">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="95b70-163">`utf32`: Codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="95b70-163">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="95b70-164">Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.).</span><span class="sxs-lookup"><span data-stu-id="95b70-164">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="95b70-165">Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="95b70-165">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="95b70-166">**UTF-7** _ wird nicht mehr für die Verwendung von empfohlen.</span><span class="sxs-lookup"><span data-stu-id="95b70-166">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="95b70-167">In PowerShell 7,1 wird eine Warnung geschrieben, wenn Sie `utf7` für den Parameter "_ \*Encoding\*\*" angeben.</span><span class="sxs-lookup"><span data-stu-id="95b70-167">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

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

### <span data-ttu-id="95b70-168">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="95b70-168">-Exclude</span></span>

<span data-ttu-id="95b70-169">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="95b70-169">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="95b70-170">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="95b70-170">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="95b70-171">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="95b70-171">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="95b70-172">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="95b70-172">Wildcard characters are permitted.</span></span> <span data-ttu-id="95b70-173">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="95b70-173">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="95b70-174">-Filter</span><span class="sxs-lookup"><span data-stu-id="95b70-174">-Filter</span></span>

<span data-ttu-id="95b70-175">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="95b70-175">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="95b70-176">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="95b70-176">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="95b70-177">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="95b70-177">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="95b70-178">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="95b70-178">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="95b70-179">-Force</span><span class="sxs-lookup"><span data-stu-id="95b70-179">-Force</span></span>

<span data-ttu-id="95b70-180">Zwingt das Cmdlet, den Inhalt einer Datei festzulegen, auch wenn die Datei schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="95b70-180">Forces the cmdlet to set the contents of a file, even if the file is read-only.</span></span> <span data-ttu-id="95b70-181">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="95b70-181">Implementation varies from provider to provider.</span></span> <span data-ttu-id="95b70-182">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="95b70-182">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="95b70-183">Der **Force** -Parameter überschreibt keine Sicherheitseinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="95b70-183">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="95b70-184">-Include</span><span class="sxs-lookup"><span data-stu-id="95b70-184">-Include</span></span>

<span data-ttu-id="95b70-185">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="95b70-185">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="95b70-186">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="95b70-186">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="95b70-187">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="95b70-187">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="95b70-188">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="95b70-188">Wildcard characters are permitted.</span></span> <span data-ttu-id="95b70-189">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="95b70-189">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="95b70-190">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="95b70-190">-LiteralPath</span></span>

<span data-ttu-id="95b70-191">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="95b70-191">Specifies a path to one or more locations.</span></span> <span data-ttu-id="95b70-192">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="95b70-192">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="95b70-193">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="95b70-193">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="95b70-194">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="95b70-194">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="95b70-195">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="95b70-195">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="95b70-196">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="95b70-196">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="95b70-197">-Nonewline</span><span class="sxs-lookup"><span data-stu-id="95b70-197">-NoNewline</span></span>

<span data-ttu-id="95b70-198">Die Zeichen folgen Darstellungen der Eingabe Objekte werden verkettet, um die Ausgabe zu bilden.</span><span class="sxs-lookup"><span data-stu-id="95b70-198">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="95b70-199">Zwischen den Ausgabe Zeichenfolgen werden keine Leerzeichen oder Zeilenumbrüche eingefügt.</span><span class="sxs-lookup"><span data-stu-id="95b70-199">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="95b70-200">Nach der letzten Ausgabe Zeichenfolge wird kein Zeilen Vorstrich hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="95b70-200">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="95b70-201">-PassThru</span><span class="sxs-lookup"><span data-stu-id="95b70-201">-PassThru</span></span>

<span data-ttu-id="95b70-202">Gibt ein Objekt zurück, das den Inhalt darstellt.</span><span class="sxs-lookup"><span data-stu-id="95b70-202">Returns an object that represents the content.</span></span> <span data-ttu-id="95b70-203">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="95b70-203">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="95b70-204">-Path</span><span class="sxs-lookup"><span data-stu-id="95b70-204">-Path</span></span>

<span data-ttu-id="95b70-205">Gibt den Pfad des Elements an, das den Inhalt empfängt.</span><span class="sxs-lookup"><span data-stu-id="95b70-205">Specifies the path of the item that receives the content.</span></span>
<span data-ttu-id="95b70-206">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="95b70-206">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="95b70-207">-Stream</span><span class="sxs-lookup"><span data-stu-id="95b70-207">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="95b70-208">Dieser Parameter ist nur unter Windows verfügbar.</span><span class="sxs-lookup"><span data-stu-id="95b70-208">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="95b70-209">Gibt einen alternativen Datenstrom für den Inhalt an.</span><span class="sxs-lookup"><span data-stu-id="95b70-209">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="95b70-210">Wenn der Datenstrom nicht vorhanden ist, wird er von diesem Cmdlet erstellt.</span><span class="sxs-lookup"><span data-stu-id="95b70-210">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="95b70-211">Platzhalterzeichen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="95b70-211">Wildcard characters are not supported.</span></span>

<span data-ttu-id="95b70-212">**Stream** ist ein dynamischer Parameter, den der **File System** -Anbieter hinzufügt `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="95b70-212">**Stream** is a dynamic parameter that the **FileSystem** provider adds to `Set-Content`.</span></span> <span data-ttu-id="95b70-213">Dieser Parameter funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="95b70-213">This parameter works only in file system drives.</span></span>

<span data-ttu-id="95b70-214">Sie können das `Set-Content` Cmdlet verwenden, um den Inhalt eines beliebigen Alternativen Datenstroms zu erstellen oder zu aktualisieren, z `Zone.Identifier` . b..</span><span class="sxs-lookup"><span data-stu-id="95b70-214">You can use the `Set-Content` cmdlet to create or update the content of any alternate data stream, such as `Zone.Identifier`.</span></span> <span data-ttu-id="95b70-215">Dies wird jedoch nicht empfohlen, um Sicherheitsüberprüfungen zu vermeiden, die Dateien blockieren, die aus dem Internet heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="95b70-215">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="95b70-216">Wenn Sie überprüfen, ob eine heruntergeladene Datei sicher ist, verwenden Sie das- `Unblock-File` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="95b70-216">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="95b70-217">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="95b70-217">This parameter was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="95b70-218">Ab PowerShell 7,2 `Set-Content` kann der Inhalt alternativer Datenströme aus Verzeichnissen und Dateien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="95b70-218">As of PowerShell 7.2, `Set-Content` can set the content of alternative data streams from directories as well as files.</span></span>

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

### <span data-ttu-id="95b70-219">-Value</span><span class="sxs-lookup"><span data-stu-id="95b70-219">-Value</span></span>

<span data-ttu-id="95b70-220">Gibt den neuen Inhalt für das Element an.</span><span class="sxs-lookup"><span data-stu-id="95b70-220">Specifies the new content for the item.</span></span>

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

### <span data-ttu-id="95b70-221">-Confirm</span><span class="sxs-lookup"><span data-stu-id="95b70-221">-Confirm</span></span>

<span data-ttu-id="95b70-222">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="95b70-222">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="95b70-223">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="95b70-223">-WhatIf</span></span>

<span data-ttu-id="95b70-224">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="95b70-224">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="95b70-225">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="95b70-225">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="95b70-226">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="95b70-226">CommonParameters</span></span>

<span data-ttu-id="95b70-227">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="95b70-227">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="95b70-228">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="95b70-228">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="95b70-229">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="95b70-229">INPUTS</span></span>

### <span data-ttu-id="95b70-230">System.Object</span><span class="sxs-lookup"><span data-stu-id="95b70-230">System.Object</span></span>

<span data-ttu-id="95b70-231">Sie können ein Objekt über die Pipeline übergeben, das den neuen Wert für das Element enthält `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="95b70-231">You can pipe an object that contains the new value for the item to `Set-Content`.</span></span>

## <span data-ttu-id="95b70-232">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="95b70-232">OUTPUTS</span></span>

### <span data-ttu-id="95b70-233">None or System.String</span><span class="sxs-lookup"><span data-stu-id="95b70-233">None or System.String</span></span>

<span data-ttu-id="95b70-234">Wenn Sie den **passthru** -Parameter verwenden, `Set-Content` generiert ein **System. String** -Objekt, das den Inhalt darstellt.</span><span class="sxs-lookup"><span data-stu-id="95b70-234">When you use the **PassThru** parameter, `Set-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="95b70-235">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="95b70-235">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="95b70-236">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="95b70-236">NOTES</span></span>

- <span data-ttu-id="95b70-237">Sie können auch auf den `Set-Content` integrierten Alias verweisen `sc` .</span><span class="sxs-lookup"><span data-stu-id="95b70-237">You can also refer to `Set-Content` by its built-in alias, `sc`.</span></span>
  <span data-ttu-id="95b70-238">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="95b70-238">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="95b70-239">`Set-Content` ist für die Zeichen folgen Verarbeitung konzipiert.</span><span class="sxs-lookup"><span data-stu-id="95b70-239">`Set-Content` is designed for string processing.</span></span> <span data-ttu-id="95b70-240">Wenn Sie Objekte, die keine Zeichenfolge `Set-Content` sind, an übergeben, wird das Objekt vor dem Schreiben in eine Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="95b70-240">If you pipe non-string objects to `Set-Content`, it converts the object to a string before writing it.</span></span> <span data-ttu-id="95b70-241">Verwenden Sie, um Objekte in Dateien zu schreiben `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="95b70-241">To write objects to files, use `Out-File`.</span></span>
- <span data-ttu-id="95b70-242">Das- `Set-Content` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="95b70-242">The `Set-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="95b70-243">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="95b70-243">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="95b70-244">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="95b70-244">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="95b70-245">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="95b70-245">RELATED LINKS</span></span>

[<span data-ttu-id="95b70-246">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="95b70-246">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="95b70-247">about_Automatic_Variables. MD</span><span class="sxs-lookup"><span data-stu-id="95b70-247">about_Automatic_Variables.md</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="95b70-248">about_Providers</span><span class="sxs-lookup"><span data-stu-id="95b70-248">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="95b70-249">Add-Content</span><span class="sxs-lookup"><span data-stu-id="95b70-249">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="95b70-250">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="95b70-250">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="95b70-251">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="95b70-251">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="95b70-252">Get-Content</span><span class="sxs-lookup"><span data-stu-id="95b70-252">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="95b70-253">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="95b70-253">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="95b70-254">New-Item</span><span class="sxs-lookup"><span data-stu-id="95b70-254">New-Item</span></span>](New-Item.md)
