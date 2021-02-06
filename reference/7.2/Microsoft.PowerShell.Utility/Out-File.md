---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-file?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-File
ms.openlocfilehash: e3a066957ab1e6935049003f8ccf55aee8bb7c94
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599835"
---
# <span data-ttu-id="616d9-102">Out-File</span><span class="sxs-lookup"><span data-stu-id="616d9-102">Out-File</span></span>

## <span data-ttu-id="616d9-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="616d9-103">SYNOPSIS</span></span>
<span data-ttu-id="616d9-104">Sendet die Ausgabe an eine Datei.</span><span class="sxs-lookup"><span data-stu-id="616d9-104">Sends output to a file.</span></span>

## <span data-ttu-id="616d9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="616d9-105">SYNTAX</span></span>

### <span data-ttu-id="616d9-106">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="616d9-106">ByPath (Default)</span></span>

```
Out-File [-FilePath] <string> [[-Encoding] <Encoding>] [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="616d9-107">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="616d9-107">ByLiteralPath</span></span>

```
Out-File [[-Encoding] <Encoding>] -LiteralPath <string> [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="616d9-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="616d9-108">DESCRIPTION</span></span>

<span data-ttu-id="616d9-109">Das- `Out-File` Cmdlet sendet die Ausgabe an eine Datei.</span><span class="sxs-lookup"><span data-stu-id="616d9-109">The `Out-File` cmdlet sends output to a file.</span></span> <span data-ttu-id="616d9-110">Er verwendet implizit das-Formatierungs System von PowerShell, um in die Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="616d9-110">It implicitly uses PowerShell's formatting system to write to the file.</span></span> <span data-ttu-id="616d9-111">Die Datei erhält dieselbe Anzeige Darstellung wie das Terminal.</span><span class="sxs-lookup"><span data-stu-id="616d9-111">The file receives the same display representation as the terminal.</span></span> <span data-ttu-id="616d9-112">Dies bedeutet, dass die Ausgabe möglicherweise für die programmgesteuerte Verarbeitung nicht ideal ist, wenn nicht alle Eingabe Objekte Zeichen folgen sind.</span><span class="sxs-lookup"><span data-stu-id="616d9-112">This means that the output may not be ideal for programmatic processing unless all input objects are strings.</span></span>
<span data-ttu-id="616d9-113">Wenn Sie Parameter für die Ausgabe angeben müssen, verwenden Sie `Out-File` anstelle des Umleitungs Operators ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="616d9-113">When you need to specify parameters for the output, use `Out-File` rather than the redirection operator (`>`).</span></span> <span data-ttu-id="616d9-114">Weitere Informationen zur Umleitung finden Sie unter [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span><span class="sxs-lookup"><span data-stu-id="616d9-114">For more information about redirection, see [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span></span>

## <span data-ttu-id="616d9-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="616d9-115">EXAMPLES</span></span>

### <span data-ttu-id="616d9-116">Beispiel 1: Senden der Ausgabe und Erstellen einer Datei</span><span class="sxs-lookup"><span data-stu-id="616d9-116">Example 1: Send output and create a file</span></span>

<span data-ttu-id="616d9-117">In diesem Beispiel wird gezeigt, wie eine Liste der Prozesse des lokalen Computers an eine Datei gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="616d9-117">This example shows how to send a list of the local computer's processes to a file.</span></span> <span data-ttu-id="616d9-118">Wenn die Datei nicht vorhanden ist, `Out-File` erstellt die Datei im angegebenen Pfad.</span><span class="sxs-lookup"><span data-stu-id="616d9-118">If the file does not exist, `Out-File` creates the file in the specified path.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt
Get-Content -Path .\Process.txt
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     29    22.39      35.40      10.98   42764   9 Application
     53    99.04     113.96       0.00   32664   0 CcmExec
     27    96.62     112.43     113.00   17720   9 Code
```

<span data-ttu-id="616d9-119">Mit dem- `Get-Process` Cmdlet wird die Liste der Prozesse abgerufen, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="616d9-119">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="616d9-120">Die **Prozess** Objekte werden über die Pipeline an das `Out-File` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="616d9-120">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="616d9-121">`Out-File` verwendet den **FilePath** -Parameter und erstellt eine Datei im aktuellen Verzeichnis mit dem Namen **Process.txt**.</span><span class="sxs-lookup"><span data-stu-id="616d9-121">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="616d9-122">Der `Get-Content` Befehl ruft Inhalt aus der Datei ab und zeigt ihn in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="616d9-122">The `Get-Content` command gets content from the file and displays it in the PowerShell console.</span></span>

### <span data-ttu-id="616d9-123">Beispiel 2: verhindern, dass eine vorhandene Datei überschrieben wird</span><span class="sxs-lookup"><span data-stu-id="616d9-123">Example 2: Prevent an existing file from being overwritten</span></span>

<span data-ttu-id="616d9-124">In diesem Beispiel wird verhindert, dass eine vorhandene Datei überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="616d9-124">This example prevents an existing file from being overwritten.</span></span> <span data-ttu-id="616d9-125">Standardmäßig `Out-File` überschreibt vorhandene Dateien.</span><span class="sxs-lookup"><span data-stu-id="616d9-125">By default, `Out-File` overwrites existing files.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt -NoClobber
```

```Output
Out-File : The file 'C:\Test\Process.txt' already exists.
At line:1 char:15
+ Get-Process | Out-File -FilePath .\Process.txt -NoClobber
+               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

<span data-ttu-id="616d9-126">Mit dem- `Get-Process` Cmdlet wird die Liste der Prozesse abgerufen, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="616d9-126">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="616d9-127">Die **Prozess** Objekte werden über die Pipeline an das `Out-File` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="616d9-127">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="616d9-128">`Out-File` verwendet den **FilePath** -Parameter und versucht, in eine Datei im aktuellen Verzeichnis namens **Process.txt** zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="616d9-128">`Out-File` uses the **FilePath** parameter and attempts to write to a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="616d9-129">Der **noClobber** -Parameter verhindert, dass die Datei überschrieben wird, und zeigt eine Meldung an, dass die Datei bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="616d9-129">The **NoClobber** parameter prevents the file from being overwritten and displays a message that the file already exists.</span></span>

### <span data-ttu-id="616d9-130">Beispiel 3: Senden der Ausgabe an eine Datei im ASCII-Format</span><span class="sxs-lookup"><span data-stu-id="616d9-130">Example 3: Send output to a file in ASCII format</span></span>

<span data-ttu-id="616d9-131">Dieses Beispiel zeigt, wie Sie die Ausgabe mit einem bestimmten Codierungstyp codieren.</span><span class="sxs-lookup"><span data-stu-id="616d9-131">This example shows how to encode output with a specific encoding type.</span></span>

```powershell
$Procs = Get-Process
Out-File -FilePath .\Process.txt -InputObject $Procs -Encoding ASCII -Width 50
```

<span data-ttu-id="616d9-132">Mit dem- `Get-Process` Cmdlet wird die Liste der Prozesse abgerufen, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="616d9-132">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="616d9-133">Die **Prozess** Objekte werden in der Variablen gespeichert `$Procs` .</span><span class="sxs-lookup"><span data-stu-id="616d9-133">The **Process** objects are stored in the variable, `$Procs`.</span></span> <span data-ttu-id="616d9-134">`Out-File` verwendet den **FilePath** -Parameter und erstellt eine Datei im aktuellen Verzeichnis mit dem Namen **Process.txt**.</span><span class="sxs-lookup"><span data-stu-id="616d9-134">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="616d9-135">Der **Inputobject** -Parameter übergibt die Prozess Objekte an `$Procs` die Datei **Process.txt**.</span><span class="sxs-lookup"><span data-stu-id="616d9-135">The **InputObject** parameter passes the process objects in `$Procs` to the file **Process.txt**.</span></span> <span data-ttu-id="616d9-136">Mit dem **Encoding** -Parameter wird die Ausgabe in das **ASCII** -Format konvertiert.</span><span class="sxs-lookup"><span data-stu-id="616d9-136">The **Encoding** parameter converts the output to **ASCII** format.</span></span> <span data-ttu-id="616d9-137">Der **Width** -Parameter schränkt jede Zeile in der Datei auf 50 Zeichen ein, sodass einige Daten abgeschnitten werden können.</span><span class="sxs-lookup"><span data-stu-id="616d9-137">The **Width** parameter limits each line in the file to 50 characters so some data might be truncated.</span></span>

### <span data-ttu-id="616d9-138">Beispiel 4: Verwenden eines Anbieters und Senden der Ausgabe an eine Datei</span><span class="sxs-lookup"><span data-stu-id="616d9-138">Example 4: Use a provider and send output to a file</span></span>

<span data-ttu-id="616d9-139">In diesem Beispiel wird gezeigt, wie das `Out-File` Cmdlet verwendet wird, wenn Sie sich nicht in einem **File System** -Anbieter Laufwerk befinden.</span><span class="sxs-lookup"><span data-stu-id="616d9-139">This example shows how to use the `Out-File` cmdlet when you are not in a **FileSystem** provider drive.</span></span> <span data-ttu-id="616d9-140">Verwenden `Get-PSProvider` Sie das Cmdlet, um die Anbieter auf dem lokalen Computer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="616d9-140">Use the `Get-PSProvider` cmdlet to view the providers on your local computer.</span></span> <span data-ttu-id="616d9-141">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="616d9-141">For more information, see [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span></span>

```
PS> Set-Location -Path Alias:

PS> Get-Location

Path
----
Alias:\

PS> Get-ChildItem | Out-File -FilePath C:\TestDir\AliasNames.txt

PS> Get-Content -Path C:\TestDir\AliasNames.txt

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           cat -> Get-Content
```

<span data-ttu-id="616d9-142">Der `Set-Location` Befehl verwendet den **path** -Parameter, um den aktuellen Speicherort auf den Registrierungs Anbieter festzulegen `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="616d9-142">The `Set-Location` command uses the **Path** parameter to set the current location to the registry provider `Alias:`.</span></span> <span data-ttu-id="616d9-143">Das- `Get-Location` Cmdlet zeigt den gesamten Pfad für an `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="616d9-143">The `Get-Location` cmdlet displays the complete path for `Alias:`.</span></span>
<span data-ttu-id="616d9-144">`Get-ChildItem` sendet Objekte über die Pipeline an das `Out-File` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="616d9-144">`Get-ChildItem` sends objects down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="616d9-145">`Out-File` verwendet den **FilePath** -Parameter, um den gesamten Pfad und den Dateinamen für die Ausgabe anzugeben, **C:\TestDir\AliasNames.txt**.</span><span class="sxs-lookup"><span data-stu-id="616d9-145">`Out-File` uses the **FilePath** parameter to specify the complete path and filename for the output, **C:\TestDir\AliasNames.txt**.</span></span> <span data-ttu-id="616d9-146">Das `Get-Content` Cmdlet verwendet den **path** -Parameter und zeigt den Inhalt der Datei in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="616d9-146">The `Get-Content` cmdlet uses the **Path** parameter and displays the file's content in the PowerShell console.</span></span>

## <span data-ttu-id="616d9-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="616d9-147">PARAMETERS</span></span>

### <span data-ttu-id="616d9-148">-Anfügen</span><span class="sxs-lookup"><span data-stu-id="616d9-148">-Append</span></span>

<span data-ttu-id="616d9-149">Fügt die Ausgabe am Ende einer vorhandenen Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="616d9-149">Adds the output to the end of an existing file.</span></span>

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

### <span data-ttu-id="616d9-150">-Codierung</span><span class="sxs-lookup"><span data-stu-id="616d9-150">-Encoding</span></span>

<span data-ttu-id="616d9-151">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="616d9-151">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="616d9-152">Der Standardwert ist `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="616d9-152">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="616d9-153">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="616d9-153">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="616d9-154">`ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="616d9-154">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="616d9-155">`bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="616d9-155">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="616d9-156">`bigendianutf32`: Codiert im UTF-32-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="616d9-156">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="616d9-157">`oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="616d9-157">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="616d9-158">`unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="616d9-158">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="616d9-159">`utf7`: Codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="616d9-159">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="616d9-160">`utf8`: Codiert im UTF-8-Format.</span><span class="sxs-lookup"><span data-stu-id="616d9-160">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="616d9-161">`utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="616d9-161">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="616d9-162">`utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="616d9-162">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="616d9-163">`utf32`: Codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="616d9-163">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="616d9-164">Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.).</span><span class="sxs-lookup"><span data-stu-id="616d9-164">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="616d9-165">Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="616d9-165">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="616d9-166">**UTF-7** _ wird nicht mehr für die Verwendung von empfohlen.</span><span class="sxs-lookup"><span data-stu-id="616d9-166">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="616d9-167">In PowerShell 7,1 wird eine Warnung geschrieben, wenn Sie `utf7` für den Parameter "_ \*Encoding\*\*" angeben.</span><span class="sxs-lookup"><span data-stu-id="616d9-167">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: 1
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="616d9-168">-FilePath</span><span class="sxs-lookup"><span data-stu-id="616d9-168">-FilePath</span></span>

<span data-ttu-id="616d9-169">Gibt den Pfad zur Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="616d9-169">Specifies the path to the output file.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="616d9-170">-Force</span><span class="sxs-lookup"><span data-stu-id="616d9-170">-Force</span></span>

<span data-ttu-id="616d9-171">Überschreibt das schreibgeschützte Attribut und überschreibt eine vorhandene schreibgeschützte Datei.</span><span class="sxs-lookup"><span data-stu-id="616d9-171">Overrides the read-only attribute and overwrites an existing read-only file.</span></span> <span data-ttu-id="616d9-172">Der **Force** -Parameter überschreibt keine Sicherheitseinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="616d9-172">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="616d9-173">-InputObject</span><span class="sxs-lookup"><span data-stu-id="616d9-173">-InputObject</span></span>

<span data-ttu-id="616d9-174">Gibt die in die Datei zu schreibenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="616d9-174">Specifies the objects to be written to the file.</span></span> <span data-ttu-id="616d9-175">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="616d9-175">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="616d9-176">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="616d9-176">-LiteralPath</span></span>

<span data-ttu-id="616d9-177">Gibt den Pfad zur Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="616d9-177">Specifies the path to the output file.</span></span> <span data-ttu-id="616d9-178">Der **literalpath** -Parameter wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="616d9-178">The **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="616d9-179">Platzhalter Zeichen werden nicht akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="616d9-179">Wildcard characters are not accepted.</span></span> <span data-ttu-id="616d9-180">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="616d9-180">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="616d9-181">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="616d9-181">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="616d9-182">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="616d9-182">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="616d9-183">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="616d9-183">-NoClobber</span></span>

<span data-ttu-id="616d9-184">**NoClobber** verhindert, dass eine vorhandene Datei überschrieben wird, und zeigt eine Meldung an, dass die Datei bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="616d9-184">**NoClobber** prevents an existing file from being overwritten and displays a message that the file already exists.</span></span> <span data-ttu-id="616d9-185">Wenn eine Datei im angegebenen Pfad vorhanden ist, wird `Out-File` die Datei standardmäßig ohne Warnung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="616d9-185">By default, if a file exists in the specified path, `Out-File` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="616d9-186">-Nonewline</span><span class="sxs-lookup"><span data-stu-id="616d9-186">-NoNewline</span></span>

<span data-ttu-id="616d9-187">Gibt an, dass der Inhalt, der in die Datei geschrieben wird, nicht mit einem Zeilen Umleitungs Zeichen endet.</span><span class="sxs-lookup"><span data-stu-id="616d9-187">Specifies that the content written to the file does not end with a newline character.</span></span> <span data-ttu-id="616d9-188">Die Zeichen folgen Darstellungen der Eingabe Objekte werden verkettet, um die Ausgabe zu bilden.</span><span class="sxs-lookup"><span data-stu-id="616d9-188">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="616d9-189">Zwischen den Ausgabe Zeichenfolgen werden keine Leerzeichen oder Zeilenumbrüche eingefügt.</span><span class="sxs-lookup"><span data-stu-id="616d9-189">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="616d9-190">Nach der letzten Ausgabe Zeichenfolge wird kein Zeilen Vorstrich hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="616d9-190">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="616d9-191">-Breite</span><span class="sxs-lookup"><span data-stu-id="616d9-191">-Width</span></span>

<span data-ttu-id="616d9-192">Gibt die Anzahl der Zeichen in jeder Zeile der Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="616d9-192">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="616d9-193">Alle zusätzlichen Zeichen werden abgeschnitten und nicht umgebrochen.</span><span class="sxs-lookup"><span data-stu-id="616d9-193">Any additional characters are truncated, not wrapped.</span></span> <span data-ttu-id="616d9-194">Wenn dieser Parameter nicht verwendet wird, wird die Breite durch die Merkmale des Hosts bestimmt.</span><span class="sxs-lookup"><span data-stu-id="616d9-194">If this parameter is not used, the width is determined by the characteristics of the host.</span></span> <span data-ttu-id="616d9-195">Der Standardwert für die PowerShell-Konsole ist 80 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="616d9-195">The default for the PowerShell console is 80 characters.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="616d9-196">-Confirm</span><span class="sxs-lookup"><span data-stu-id="616d9-196">-Confirm</span></span>

<span data-ttu-id="616d9-197">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="616d9-197">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="616d9-198">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="616d9-198">-WhatIf</span></span>

<span data-ttu-id="616d9-199">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="616d9-199">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="616d9-200">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="616d9-200">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="616d9-201">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="616d9-201">CommonParameters</span></span>

<span data-ttu-id="616d9-202">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="616d9-202">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="616d9-203">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="616d9-203">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="616d9-204">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="616d9-204">INPUTS</span></span>

### <span data-ttu-id="616d9-205">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="616d9-205">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="616d9-206">Sie können jedes beliebige Objekt an die Pipeline übergeben `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="616d9-206">You can pipe any object to `Out-File`.</span></span>

## <span data-ttu-id="616d9-207">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="616d9-207">OUTPUTS</span></span>

### <span data-ttu-id="616d9-208">Keine</span><span class="sxs-lookup"><span data-stu-id="616d9-208">None</span></span>

<span data-ttu-id="616d9-209">`Out-File` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="616d9-209">`Out-File` does not generate any output.</span></span>

## <span data-ttu-id="616d9-210">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="616d9-210">NOTES</span></span>

<span data-ttu-id="616d9-211">Eingabe Objekte werden automatisch wie im Terminal formatiert, Sie können jedoch ein `Format-*` Cmdlet verwenden, um die Formatierung der Ausgabe in der Datei explizit zu steuern.</span><span class="sxs-lookup"><span data-stu-id="616d9-211">Input objects are automatically formatted as they would be in the terminal, but you can use a `Format-*` cmdlet to explicitly control the formatting of the output to the file.</span></span> <span data-ttu-id="616d9-212">Beispiel: `Get-Date | Format-List | Out-File out.txt`</span><span class="sxs-lookup"><span data-stu-id="616d9-212">For example, `Get-Date | Format-List | Out-File out.txt`</span></span>

<span data-ttu-id="616d9-213">Verwenden Sie die Pipeline, um die Ausgabe eines PowerShell-Befehls an das `Out-File` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="616d9-213">To send a PowerShell command's output to the `Out-File` cmdlet, use the pipeline.</span></span> <span data-ttu-id="616d9-214">Alternativ können Sie Daten in einer Variablen speichern und den **Inputobject** -Parameter verwenden, um Daten an das `Out-File` Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="616d9-214">Alternatively, you can store data in a variable and use the **InputObject** parameter to pass data to the `Out-File` cmdlet.</span></span>

<span data-ttu-id="616d9-215">`Out-File` speichert Daten in einer Datei, erzeugt aber keine Ausgabe Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="616d9-215">`Out-File` saves data to a file but it does not produce any output objects to the pipeline.</span></span>

## <span data-ttu-id="616d9-216">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="616d9-216">RELATED LINKS</span></span>

[<span data-ttu-id="616d9-217">about_Providers</span><span class="sxs-lookup"><span data-stu-id="616d9-217">about_Providers</span></span>](../Microsoft.Powershell.Core/About/about_Providers.md)

[<span data-ttu-id="616d9-218">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="616d9-218">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="616d9-219">Out-Default</span><span class="sxs-lookup"><span data-stu-id="616d9-219">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="616d9-220">Out-Host</span><span class="sxs-lookup"><span data-stu-id="616d9-220">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="616d9-221">Out-Null</span><span class="sxs-lookup"><span data-stu-id="616d9-221">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="616d9-222">Out-String</span><span class="sxs-lookup"><span data-stu-id="616d9-222">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="616d9-223">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="616d9-223">Tee-Object</span></span>](Tee-Object.md)

