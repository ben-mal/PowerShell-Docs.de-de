---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: 897029cab790487f6834d021bfc447060fd39812
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214471"
---
# <span data-ttu-id="89ee5-103">Set-Content</span><span class="sxs-lookup"><span data-stu-id="89ee5-103">Set-Content</span></span>

## <span data-ttu-id="89ee5-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="89ee5-104">SYNOPSIS</span></span>
<span data-ttu-id="89ee5-105">Schreibt neuen Inhalt oder ersetzt vorhandene Inhalte in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="89ee5-105">Writes new content or replaces existing content in a file.</span></span>

## <span data-ttu-id="89ee5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="89ee5-106">SYNTAX</span></span>

### <span data-ttu-id="89ee5-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="89ee5-107">Path (Default)</span></span>

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### <span data-ttu-id="89ee5-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="89ee5-108">LiteralPath</span></span>

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

## <span data-ttu-id="89ee5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89ee5-109">DESCRIPTION</span></span>

<span data-ttu-id="89ee5-110">`Set-Content` ist ein Cmdlet für die Zeichen folgen Verarbeitung, das neuen Inhalt schreibt oder den Inhalt in einer Datei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-110">`Set-Content` is a string-processing cmdlet that writes new content or replaces the content in a file.</span></span> <span data-ttu-id="89ee5-111">`Set-Content` ersetzt den vorhandenen Inhalt und unterscheidet sich von dem `Add-Content` Cmdlet, das Inhalt an eine Datei anfügt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-111">`Set-Content` replaces the existing content and differs from the `Add-Content` cmdlet that appends content to a file.</span></span> <span data-ttu-id="89ee5-112">Wenn Sie Inhalte an senden möchten, `Set-Content` können Sie den **value** -Parameter in der Befehlszeile verwenden oder Inhalt über die Pipeline senden.</span><span class="sxs-lookup"><span data-stu-id="89ee5-112">To send content to `Set-Content` you can use the **Value** parameter on the command line or send content through the pipeline.</span></span>

<span data-ttu-id="89ee5-113">Wenn Sie für die folgenden Beispiele Dateien oder Verzeichnisse erstellen müssen, finden Sie weitere Informationen unter [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="89ee5-113">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="89ee5-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="89ee5-114">EXAMPLES</span></span>

### <span data-ttu-id="89ee5-115">Beispiel 1: Ersetzen des Inhalts mehrerer Dateien in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="89ee5-115">Example 1: Replace the contents of multiple files in a directory</span></span>

<span data-ttu-id="89ee5-116">In diesem Beispiel wird der Inhalt für mehrere Dateien im aktuellen Verzeichnis ersetzt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-116">This example replaces the content for multiple files in the current directory.</span></span>

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

<span data-ttu-id="89ee5-117">Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um **txt** -Dateien aufzulisten, die mit `Test*` im aktuellen Verzeichnis beginnen.</span><span class="sxs-lookup"><span data-stu-id="89ee5-117">The `Get-ChildItem` cmdlet uses the **Path** parameter to list **.txt** files that begin with `Test*` in the current directory.</span></span> <span data-ttu-id="89ee5-118">Das `Set-Content` Cmdlet verwendet den **path** -Parameter, um die `Test*.txt` Dateien anzugeben.</span><span class="sxs-lookup"><span data-stu-id="89ee5-118">The `Set-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files.</span></span> <span data-ttu-id="89ee5-119">Der **value** -Parameter stellt die Text Zeichenfolge **Hello, World** dar, die den vorhandenen Inhalt in jeder Datei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-119">The **Value** parameter provides the text string **Hello, World** that replaces the existing content in each file.</span></span> <span data-ttu-id="89ee5-120">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Dateien anzugeben, `Test*.txt` und zeigt den Inhalt jeder Datei in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="89ee5-120">The `Get-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files and displays each file's content in the PowerShell console.</span></span>

### <span data-ttu-id="89ee5-121">Beispiel 2: Erstellen einer neuen Datei und Schreiben von Inhalten</span><span class="sxs-lookup"><span data-stu-id="89ee5-121">Example 2: Create a new file and write content</span></span>

<span data-ttu-id="89ee5-122">In diesem Beispiel wird eine neue Datei erstellt, und das aktuelle Datum und die aktuelle Uhrzeit werden in die Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="89ee5-122">This example creates a new file and writes the current date and time to the file.</span></span>

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

<span data-ttu-id="89ee5-123">`Set-Content` verwendet die **path** -und **value** -Parameter, um eine neue Datei namens **DateTime.txt** im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="89ee5-123">`Set-Content` uses the **Path** and **Value** parameters to create a new file named **DateTime.txt** in the current directory.</span></span> <span data-ttu-id="89ee5-124">Der **value** -Parameter verwendet `Get-Date` , um das aktuelle Datum und die aktuelle Uhrzeit zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="89ee5-124">The **Value** parameter uses `Get-Date` to get the current date and time.</span></span>
<span data-ttu-id="89ee5-125">`Set-Content` schreibt das **DateTime** -Objekt als Zeichenfolge in die Datei.</span><span class="sxs-lookup"><span data-stu-id="89ee5-125">`Set-Content` writes the **DateTime** object to the file as a string.</span></span> <span data-ttu-id="89ee5-126">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um den Inhalt **DateTime.txt** in der PowerShell-Konsole anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="89ee5-126">The `Get-Content` cmdlet uses the **Path** parameter to display the content of **DateTime.txt** in the PowerShell console.</span></span>

### <span data-ttu-id="89ee5-127">Beispiel 3: Ersetzen von Text in einer Datei</span><span class="sxs-lookup"><span data-stu-id="89ee5-127">Example 3: Replace text in a file</span></span>

<span data-ttu-id="89ee5-128">Dieser Befehl ersetzt alle Instanzen von Word innerhalb einer vorhandenen Datei.</span><span class="sxs-lookup"><span data-stu-id="89ee5-128">This command replaces all instances of word within an existing file.</span></span>

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

<span data-ttu-id="89ee5-129">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die **Notice.txt** Datei im aktuellen Verzeichnis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="89ee5-129">The `Get-Content` cmdlet uses the **Path** parameter to specify the **Notice.txt** file in the current directory.</span></span> <span data-ttu-id="89ee5-130">Der `Get-Content` Befehl wird in Klammern eingeschlossen, sodass der Befehl abgeschlossen ist, bevor er an die Pipeline gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="89ee5-130">The `Get-Content` command is wrapped with parentheses so that the command finishes before being sent down the pipeline.</span></span>

<span data-ttu-id="89ee5-131">Der Inhalt der **Notice.txt** Datei wird über die Pipeline an das `ForEach-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="89ee5-131">The contents of the **Notice.txt** file are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span>
<span data-ttu-id="89ee5-132">`ForEach-Object` verwendet die automatische Variable `$_` und ersetzt jedes Vorkommen von **Warning** durch **Vorsicht** .</span><span class="sxs-lookup"><span data-stu-id="89ee5-132">`ForEach-Object` uses the automatic variable `$_` and replaces each occurrence of **Warning** with **Caution** .</span></span> <span data-ttu-id="89ee5-133">Die Objekte werden über die Pipeline an das `Set-Content` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="89ee5-133">The objects are sent down the pipeline to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="89ee5-134">`Set-Content` verwendet den **path** -Parameter, um die **Notice.txt** Datei anzugeben und den aktualisierten Inhalt in die Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="89ee5-134">`Set-Content` uses the **Path** parameter to specify the **Notice.txt** file and writes the updated content to the file.</span></span>

<span data-ttu-id="89ee5-135">Das letzte `Get-Content` Cmdlet zeigt den aktualisierten Dateiinhalt in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="89ee5-135">The last `Get-Content` cmdlet displays the updated file content in the PowerShell console.</span></span>

### <span data-ttu-id="89ee5-136">Beispiel 4: Verwenden von Filtern mit Set-Content</span><span class="sxs-lookup"><span data-stu-id="89ee5-136">Example 4: Use Filters with Set-Content</span></span>

<span data-ttu-id="89ee5-137">Sie können einen Filter für das `Set-Content` Cmdlet angeben.</span><span class="sxs-lookup"><span data-stu-id="89ee5-137">You can specify a filter to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="89ee5-138">Wenn Sie den **path** -Parameter mithilfe von Filtern qualifizieren, müssen Sie ein nach gestelltes Sternchen () einfügen, `*` um den Inhalt des Pfads anzugeben.</span><span class="sxs-lookup"><span data-stu-id="89ee5-138">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="89ee5-139">Mit dem folgenden Befehl wird der Inhalt aller `*.txt` Dateien im `C:\Temp` Verzeichnis auf den leeren **Wert** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-139">The following command set the content all `*.txt` files in the `C:\Temp` directory to the **Value** empty.</span></span>

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## <span data-ttu-id="89ee5-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="89ee5-140">PARAMETERS</span></span>

### <span data-ttu-id="89ee5-141">-Credential</span><span class="sxs-lookup"><span data-stu-id="89ee5-141">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="89ee5-142">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-142">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="89ee5-143">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="89ee5-143">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="89ee5-144">-Codierung</span><span class="sxs-lookup"><span data-stu-id="89ee5-144">-Encoding</span></span>

<span data-ttu-id="89ee5-145">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="89ee5-145">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="89ee5-146">Der Standardwert ist `Default`.</span><span class="sxs-lookup"><span data-stu-id="89ee5-146">The default value is `Default`.</span></span>

<span data-ttu-id="89ee5-147">Encoding ist ein dynamischer Parameter, den der File System-Anbieter hinzufügt `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="89ee5-147">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="89ee5-148">Dieser Parameter funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="89ee5-148">This parameter works only in file system drives.</span></span>

<span data-ttu-id="89ee5-149">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="89ee5-149">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="89ee5-150">`Ascii` Verwendet den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="89ee5-150">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="89ee5-151">`BigEndianUnicode` Verwendet UTF-16 mit der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="89ee5-151">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="89ee5-152">`BigEndianUTF32` Verwendet UTF-32 mit der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="89ee5-152">`BigEndianUTF32` Uses UTF-32 with the big-endian byte order.</span></span>
- <span data-ttu-id="89ee5-153">`Byte` Codiert eine Reihe von Zeichen in eine Bytefolge.</span><span class="sxs-lookup"><span data-stu-id="89ee5-153">`Byte` Encodes a set of characters into a sequence of bytes.</span></span>
- <span data-ttu-id="89ee5-154">`Default` Verwendet die Codierung, die der aktiven Codepage des Systems entspricht (normalerweise ANSI).</span><span class="sxs-lookup"><span data-stu-id="89ee5-154">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="89ee5-155">`Oem` Verwendet die Codierung, die der aktuellen OEM-Codepage des Systems entspricht.</span><span class="sxs-lookup"><span data-stu-id="89ee5-155">`Oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="89ee5-156">`String` Identisch mit `Unicode`.</span><span class="sxs-lookup"><span data-stu-id="89ee5-156">`String` Same as `Unicode`.</span></span>
- <span data-ttu-id="89ee5-157">`Unicode` Verwendet UTF-16 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="89ee5-157">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="89ee5-158">`Unknown` Identisch mit `Unicode`.</span><span class="sxs-lookup"><span data-stu-id="89ee5-158">`Unknown` Same as `Unicode`.</span></span>
- <span data-ttu-id="89ee5-159">`UTF7` Verwendet UTF-7.</span><span class="sxs-lookup"><span data-stu-id="89ee5-159">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="89ee5-160">`UTF8` Verwendet UTF-8.</span><span class="sxs-lookup"><span data-stu-id="89ee5-160">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="89ee5-161">`UTF32` Verwendet UTF-32 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="89ee5-161">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="89ee5-162">Encoding ist ein dynamischer Parameter, den der File System-Anbieter hinzufügt `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="89ee5-162">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="89ee5-163">Dieser Parameter funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="89ee5-163">This parameter works only in file system drives.</span></span>

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

### <span data-ttu-id="89ee5-164">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="89ee5-164">-Exclude</span></span>

<span data-ttu-id="89ee5-165">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="89ee5-165">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="89ee5-166">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="89ee5-166">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="89ee5-167">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="89ee5-167">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="89ee5-168">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="89ee5-168">Wildcard characters are permitted.</span></span> <span data-ttu-id="89ee5-169">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-169">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="89ee5-170">-Filter</span><span class="sxs-lookup"><span data-stu-id="89ee5-170">-Filter</span></span>

<span data-ttu-id="89ee5-171">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="89ee5-171">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="89ee5-172">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-172">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="89ee5-173">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="89ee5-173">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="89ee5-174">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="89ee5-174">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="89ee5-175">-Force</span><span class="sxs-lookup"><span data-stu-id="89ee5-175">-Force</span></span>

<span data-ttu-id="89ee5-176">Zwingt das Cmdlet, den Inhalt einer Datei festzulegen, auch wenn die Datei schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="89ee5-176">Forces the cmdlet to set the contents of a file, even if the file is read-only.</span></span> <span data-ttu-id="89ee5-177">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="89ee5-177">Implementation varies from provider to provider.</span></span> <span data-ttu-id="89ee5-178">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="89ee5-178">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="89ee5-179">Der **Force** -Parameter überschreibt keine Sicherheitseinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="89ee5-179">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="89ee5-180">-Include</span><span class="sxs-lookup"><span data-stu-id="89ee5-180">-Include</span></span>

<span data-ttu-id="89ee5-181">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-181">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="89ee5-182">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="89ee5-182">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="89ee5-183">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="89ee5-183">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="89ee5-184">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="89ee5-184">Wildcard characters are permitted.</span></span> <span data-ttu-id="89ee5-185">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-185">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="89ee5-186">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="89ee5-186">-LiteralPath</span></span>

<span data-ttu-id="89ee5-187">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="89ee5-187">Specifies a path to one or more locations.</span></span> <span data-ttu-id="89ee5-188">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="89ee5-188">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="89ee5-189">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="89ee5-189">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="89ee5-190">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="89ee5-190">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="89ee5-191">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="89ee5-191">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="89ee5-192">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="89ee5-192">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="89ee5-193">-Nonewline</span><span class="sxs-lookup"><span data-stu-id="89ee5-193">-NoNewline</span></span>

<span data-ttu-id="89ee5-194">Die Zeichen folgen Darstellungen der Eingabe Objekte werden verkettet, um die Ausgabe zu bilden.</span><span class="sxs-lookup"><span data-stu-id="89ee5-194">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="89ee5-195">Zwischen den Ausgabe Zeichenfolgen werden keine Leerzeichen oder Zeilenumbrüche eingefügt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-195">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="89ee5-196">Nach der letzten Ausgabe Zeichenfolge wird kein Zeilen Vorstrich hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-196">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="89ee5-197">-PassThru</span><span class="sxs-lookup"><span data-stu-id="89ee5-197">-PassThru</span></span>

<span data-ttu-id="89ee5-198">Gibt ein Objekt zurück, das den Inhalt darstellt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-198">Returns an object that represents the content.</span></span> <span data-ttu-id="89ee5-199">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="89ee5-199">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="89ee5-200">-Path</span><span class="sxs-lookup"><span data-stu-id="89ee5-200">-Path</span></span>

<span data-ttu-id="89ee5-201">Gibt den Pfad des Elements an, das den Inhalt empfängt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-201">Specifies the path of the item that receives the content.</span></span>
<span data-ttu-id="89ee5-202">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="89ee5-202">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="89ee5-203">-Stream</span><span class="sxs-lookup"><span data-stu-id="89ee5-203">-Stream</span></span>

<span data-ttu-id="89ee5-204">Gibt einen alternativen Datenstrom für den Inhalt an.</span><span class="sxs-lookup"><span data-stu-id="89ee5-204">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="89ee5-205">Wenn der Datenstrom nicht vorhanden ist, wird er von diesem Cmdlet erstellt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-205">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="89ee5-206">Platzhalterzeichen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-206">Wildcard characters are not supported.</span></span>

<span data-ttu-id="89ee5-207">**Stream** ist ein dynamischer Parameter, den der **File System** -Anbieter hinzufügt `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="89ee5-207">**Stream** is a dynamic parameter that the **FileSystem** provider adds to `Set-Content`.</span></span> <span data-ttu-id="89ee5-208">Dieser Parameter funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="89ee5-208">This parameter works only in file system drives.</span></span>

<span data-ttu-id="89ee5-209">Sie können das `Set-Content` Cmdlet verwenden, um den Inhalt des alternativen Datenstroms " **Zone. Identifier** " zu ändern.</span><span class="sxs-lookup"><span data-stu-id="89ee5-209">You can use the `Set-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="89ee5-210">Dies wird jedoch nicht empfohlen, um Sicherheitsüberprüfungen zu vermeiden, die Dateien blockieren, die aus dem Internet heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="89ee5-210">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="89ee5-211">Wenn Sie überprüfen, ob eine heruntergeladene Datei sicher ist, verwenden Sie das- `Unblock-File` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="89ee5-211">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="89ee5-212">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-212">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="89ee5-213">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="89ee5-213">-UseTransaction</span></span>

<span data-ttu-id="89ee5-214">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="89ee5-214">Includes the command in the active transaction.</span></span> <span data-ttu-id="89ee5-215">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="89ee5-215">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="89ee5-216">Weitere Informationen finden Sie unter [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="89ee5-216">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="89ee5-217">-Value</span><span class="sxs-lookup"><span data-stu-id="89ee5-217">-Value</span></span>

<span data-ttu-id="89ee5-218">Gibt den neuen Inhalt für das Element an.</span><span class="sxs-lookup"><span data-stu-id="89ee5-218">Specifies the new content for the item.</span></span>

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

### <span data-ttu-id="89ee5-219">-Confirm</span><span class="sxs-lookup"><span data-stu-id="89ee5-219">-Confirm</span></span>

<span data-ttu-id="89ee5-220">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="89ee5-220">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="89ee5-221">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="89ee5-221">-WhatIf</span></span>

<span data-ttu-id="89ee5-222">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="89ee5-222">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="89ee5-223">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-223">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="89ee5-224">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="89ee5-224">CommonParameters</span></span>

<span data-ttu-id="89ee5-225">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="89ee5-225">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span>
<span data-ttu-id="89ee5-226">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="89ee5-226">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="89ee5-227">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="89ee5-227">INPUTS</span></span>

### <span data-ttu-id="89ee5-228">System.Object</span><span class="sxs-lookup"><span data-stu-id="89ee5-228">System.Object</span></span>

<span data-ttu-id="89ee5-229">Sie können ein Objekt über die Pipeline übergeben, das den neuen Wert für das Element enthält `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="89ee5-229">You can pipe an object that contains the new value for the item to `Set-Content`.</span></span>

## <span data-ttu-id="89ee5-230">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="89ee5-230">OUTPUTS</span></span>

### <span data-ttu-id="89ee5-231">None or System.String</span><span class="sxs-lookup"><span data-stu-id="89ee5-231">None or System.String</span></span>

<span data-ttu-id="89ee5-232">Wenn Sie den **passthru** -Parameter verwenden, `Set-Content` generiert ein **System. String** -Objekt, das den Inhalt darstellt.</span><span class="sxs-lookup"><span data-stu-id="89ee5-232">When you use the **PassThru** parameter, `Set-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="89ee5-233">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="89ee5-233">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="89ee5-234">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="89ee5-234">NOTES</span></span>

- <span data-ttu-id="89ee5-235">Sie können auch auf den `Set-Content` integrierten Alias verweisen `sc` .</span><span class="sxs-lookup"><span data-stu-id="89ee5-235">You can also refer to `Set-Content` by its built-in alias, `sc`.</span></span>
  <span data-ttu-id="89ee5-236">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="89ee5-236">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="89ee5-237">`Set-Content` ist für die Zeichen folgen Verarbeitung konzipiert.</span><span class="sxs-lookup"><span data-stu-id="89ee5-237">`Set-Content` is designed for string processing.</span></span> <span data-ttu-id="89ee5-238">Wenn Sie Objekte, die keine Zeichenfolge `Set-Content` sind, an übergeben, wird das Objekt vor dem Schreiben in eine Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="89ee5-238">If you pipe non-string objects to `Set-Content`, it converts the object to a string before writing it.</span></span> <span data-ttu-id="89ee5-239">Verwenden Sie, um Objekte in Dateien zu schreiben `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="89ee5-239">To write objects to files, use `Out-File`.</span></span>
- <span data-ttu-id="89ee5-240">Das- `Set-Content` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="89ee5-240">The `Set-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="89ee5-241">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="89ee5-241">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="89ee5-242">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="89ee5-242">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="89ee5-243">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="89ee5-243">RELATED LINKS</span></span>

[<span data-ttu-id="89ee5-244">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="89ee5-244">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="89ee5-245">about_Automatic_Variables. MD</span><span class="sxs-lookup"><span data-stu-id="89ee5-245">about_Automatic_Variables.md</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="89ee5-246">about_Providers</span><span class="sxs-lookup"><span data-stu-id="89ee5-246">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="89ee5-247">about_Transactions</span><span class="sxs-lookup"><span data-stu-id="89ee5-247">about_Transactions</span></span>](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[<span data-ttu-id="89ee5-248">Add-Content</span><span class="sxs-lookup"><span data-stu-id="89ee5-248">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="89ee5-249">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="89ee5-249">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="89ee5-250">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="89ee5-250">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="89ee5-251">Get-Content</span><span class="sxs-lookup"><span data-stu-id="89ee5-251">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="89ee5-252">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="89ee5-252">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="89ee5-253">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ee5-253">New-Item</span></span>](New-Item.md)
