---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-file?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-File
ms.openlocfilehash: 3a3d431276074d7c2b66b442307071076fdfebd5
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "93220036"
---
# <span data-ttu-id="ecf08-103">Out-File</span><span class="sxs-lookup"><span data-stu-id="ecf08-103">Out-File</span></span>

## <span data-ttu-id="ecf08-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ecf08-104">SYNOPSIS</span></span>
<span data-ttu-id="ecf08-105">Sendet die Ausgabe an eine Datei.</span><span class="sxs-lookup"><span data-stu-id="ecf08-105">Sends output to a file.</span></span>

## <span data-ttu-id="ecf08-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ecf08-106">SYNTAX</span></span>

### <span data-ttu-id="ecf08-107">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="ecf08-107">ByPath (Default)</span></span>

```
Out-File [-FilePath] <string> [[-Encoding] <Encoding>] [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ecf08-108">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="ecf08-108">ByLiteralPath</span></span>

```
Out-File [[-Encoding] <Encoding>] -LiteralPath <string> [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ecf08-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ecf08-109">DESCRIPTION</span></span>

<span data-ttu-id="ecf08-110">Das- `Out-File` Cmdlet sendet die Ausgabe an eine Datei.</span><span class="sxs-lookup"><span data-stu-id="ecf08-110">The `Out-File` cmdlet sends output to a file.</span></span> <span data-ttu-id="ecf08-111">Er verwendet implizit das-Formatierungs System von PowerShell, um in die Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="ecf08-111">It implicitly uses PowerShell's formatting system to write to the file.</span></span> <span data-ttu-id="ecf08-112">Die Datei erhält dieselbe Anzeige Darstellung wie das Terminal.</span><span class="sxs-lookup"><span data-stu-id="ecf08-112">The file receives the same display representation as the terminal.</span></span> <span data-ttu-id="ecf08-113">Dies bedeutet, dass die Ausgabe möglicherweise für die programmgesteuerte Verarbeitung nicht ideal ist, wenn nicht alle Eingabe Objekte Zeichen folgen sind.</span><span class="sxs-lookup"><span data-stu-id="ecf08-113">This means that the output may not be ideal for programmatic processing unless all input objects are strings.</span></span>
<span data-ttu-id="ecf08-114">Wenn Sie Parameter für die Ausgabe angeben müssen, verwenden Sie `Out-File` anstelle des Umleitungs Operators ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="ecf08-114">When you need to specify parameters for the output, use `Out-File` rather than the redirection operator (`>`).</span></span> <span data-ttu-id="ecf08-115">Weitere Informationen zur Umleitung finden Sie unter [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span><span class="sxs-lookup"><span data-stu-id="ecf08-115">For more information about redirection, see [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span></span>

## <span data-ttu-id="ecf08-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ecf08-116">EXAMPLES</span></span>

### <span data-ttu-id="ecf08-117">Beispiel 1: Senden der Ausgabe und Erstellen einer Datei</span><span class="sxs-lookup"><span data-stu-id="ecf08-117">Example 1: Send output and create a file</span></span>

<span data-ttu-id="ecf08-118">In diesem Beispiel wird gezeigt, wie eine Liste der Prozesse des lokalen Computers an eine Datei gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="ecf08-118">This example shows how to send a list of the local computer's processes to a file.</span></span> <span data-ttu-id="ecf08-119">Wenn die Datei nicht vorhanden ist, `Out-File` erstellt die Datei im angegebenen Pfad.</span><span class="sxs-lookup"><span data-stu-id="ecf08-119">If the file does not exist, `Out-File` creates the file in the specified path.</span></span>

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

<span data-ttu-id="ecf08-120">Mit dem- `Get-Process` Cmdlet wird die Liste der Prozesse abgerufen, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ecf08-120">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="ecf08-121">Die **Prozess** Objekte werden über die Pipeline an das `Out-File` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="ecf08-121">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="ecf08-122">`Out-File` verwendet den **FilePath** -Parameter und erstellt eine Datei im aktuellen Verzeichnis mit dem Namen **Process.txt**.</span><span class="sxs-lookup"><span data-stu-id="ecf08-122">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="ecf08-123">Der `Get-Content` Befehl ruft Inhalt aus der Datei ab und zeigt ihn in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="ecf08-123">The `Get-Content` command gets content from the file and displays it in the PowerShell console.</span></span>

### <span data-ttu-id="ecf08-124">Beispiel 2: verhindern, dass eine vorhandene Datei überschrieben wird</span><span class="sxs-lookup"><span data-stu-id="ecf08-124">Example 2: Prevent an existing file from being overwritten</span></span>

<span data-ttu-id="ecf08-125">In diesem Beispiel wird verhindert, dass eine vorhandene Datei überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="ecf08-125">This example prevents an existing file from being overwritten.</span></span> <span data-ttu-id="ecf08-126">Standardmäßig `Out-File` überschreibt vorhandene Dateien.</span><span class="sxs-lookup"><span data-stu-id="ecf08-126">By default, `Out-File` overwrites existing files.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt -NoClobber
```

```Output
Out-File : The file 'C:\Test\Process.txt' already exists.
At line:1 char:15
+ Get-Process | Out-File -FilePath .\Process.txt -NoClobber
+               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

<span data-ttu-id="ecf08-127">Mit dem- `Get-Process` Cmdlet wird die Liste der Prozesse abgerufen, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ecf08-127">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="ecf08-128">Die **Prozess** Objekte werden über die Pipeline an das `Out-File` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="ecf08-128">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="ecf08-129">`Out-File` verwendet den **FilePath** -Parameter und versucht, in eine Datei im aktuellen Verzeichnis namens **Process.txt** zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="ecf08-129">`Out-File` uses the **FilePath** parameter and attempts to write to a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="ecf08-130">Der **noClobber** -Parameter verhindert, dass die Datei überschrieben wird, und zeigt eine Meldung an, dass die Datei bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ecf08-130">The **NoClobber** parameter prevents the file from being overwritten and displays a message that the file already exists.</span></span>

### <span data-ttu-id="ecf08-131">Beispiel 3: Senden der Ausgabe an eine Datei im ASCII-Format</span><span class="sxs-lookup"><span data-stu-id="ecf08-131">Example 3: Send output to a file in ASCII format</span></span>

<span data-ttu-id="ecf08-132">Dieses Beispiel zeigt, wie Sie die Ausgabe mit einem bestimmten Codierungstyp codieren.</span><span class="sxs-lookup"><span data-stu-id="ecf08-132">This example shows how to encode output with a specific encoding type.</span></span>

```powershell
$Procs = Get-Process
Out-File -FilePath .\Process.txt -InputObject $Procs -Encoding ASCII -Width 50
```

<span data-ttu-id="ecf08-133">Mit dem- `Get-Process` Cmdlet wird die Liste der Prozesse abgerufen, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ecf08-133">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="ecf08-134">Die **Prozess** Objekte werden in der Variablen gespeichert `$Procs` .</span><span class="sxs-lookup"><span data-stu-id="ecf08-134">The **Process** objects are stored in the variable, `$Procs`.</span></span> <span data-ttu-id="ecf08-135">`Out-File` verwendet den **FilePath** -Parameter und erstellt eine Datei im aktuellen Verzeichnis mit dem Namen **Process.txt**.</span><span class="sxs-lookup"><span data-stu-id="ecf08-135">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="ecf08-136">Der **Inputobject** -Parameter übergibt die Prozess Objekte an `$Procs` die Datei **Process.txt**.</span><span class="sxs-lookup"><span data-stu-id="ecf08-136">The **InputObject** parameter passes the process objects in `$Procs` to the file **Process.txt**.</span></span> <span data-ttu-id="ecf08-137">Mit dem **Encoding** -Parameter wird die Ausgabe in das **ASCII** -Format konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ecf08-137">The **Encoding** parameter converts the output to **ASCII** format.</span></span> <span data-ttu-id="ecf08-138">Der **Width** -Parameter schränkt jede Zeile in der Datei auf 50 Zeichen ein, sodass einige Daten abgeschnitten werden können.</span><span class="sxs-lookup"><span data-stu-id="ecf08-138">The **Width** parameter limits each line in the file to 50 characters so some data might be truncated.</span></span>

### <span data-ttu-id="ecf08-139">Beispiel 4: Verwenden eines Anbieters und Senden der Ausgabe an eine Datei</span><span class="sxs-lookup"><span data-stu-id="ecf08-139">Example 4: Use a provider and send output to a file</span></span>

<span data-ttu-id="ecf08-140">In diesem Beispiel wird gezeigt, wie das `Out-File` Cmdlet verwendet wird, wenn Sie sich nicht in einem **File System** -Anbieter Laufwerk befinden.</span><span class="sxs-lookup"><span data-stu-id="ecf08-140">This example shows how to use the `Out-File` cmdlet when you are not in a **FileSystem** provider drive.</span></span> <span data-ttu-id="ecf08-141">Verwenden `Get-PSProvider` Sie das Cmdlet, um die Anbieter auf dem lokalen Computer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ecf08-141">Use the `Get-PSProvider` cmdlet to view the providers on your local computer.</span></span> <span data-ttu-id="ecf08-142">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="ecf08-142">For more information, see [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span></span>

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

<span data-ttu-id="ecf08-143">Der `Set-Location` Befehl verwendet den **path** -Parameter, um den aktuellen Speicherort auf den Registrierungs Anbieter festzulegen `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="ecf08-143">The `Set-Location` command uses the **Path** parameter to set the current location to the registry provider `Alias:`.</span></span> <span data-ttu-id="ecf08-144">Das- `Get-Location` Cmdlet zeigt den gesamten Pfad für an `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="ecf08-144">The `Get-Location` cmdlet displays the complete path for `Alias:`.</span></span>
<span data-ttu-id="ecf08-145">`Get-ChildItem` sendet Objekte über die Pipeline an das `Out-File` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ecf08-145">`Get-ChildItem` sends objects down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="ecf08-146">`Out-File` verwendet den **FilePath** -Parameter, um den gesamten Pfad und den Dateinamen für die Ausgabe anzugeben, **C:\TestDir\AliasNames.txt**.</span><span class="sxs-lookup"><span data-stu-id="ecf08-146">`Out-File` uses the **FilePath** parameter to specify the complete path and filename for the output, **C:\TestDir\AliasNames.txt**.</span></span> <span data-ttu-id="ecf08-147">Das `Get-Content` Cmdlet verwendet den **path** -Parameter und zeigt den Inhalt der Datei in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="ecf08-147">The `Get-Content` cmdlet uses the **Path** parameter and displays the file's content in the PowerShell console.</span></span>

## <span data-ttu-id="ecf08-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ecf08-148">PARAMETERS</span></span>

### <span data-ttu-id="ecf08-149">-Anfügen</span><span class="sxs-lookup"><span data-stu-id="ecf08-149">-Append</span></span>

<span data-ttu-id="ecf08-150">Fügt die Ausgabe am Ende einer vorhandenen Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="ecf08-150">Adds the output to the end of an existing file.</span></span>

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

### <span data-ttu-id="ecf08-151">-Codierung</span><span class="sxs-lookup"><span data-stu-id="ecf08-151">-Encoding</span></span>

<span data-ttu-id="ecf08-152">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="ecf08-152">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="ecf08-153">Der Standardwert ist `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="ecf08-153">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="ecf08-154">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ecf08-154">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="ecf08-155">`ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="ecf08-155">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="ecf08-156">`bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="ecf08-156">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="ecf08-157">`bigendianutf32`: Codiert im UTF-32-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="ecf08-157">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="ecf08-158">`oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="ecf08-158">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="ecf08-159">`unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="ecf08-159">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="ecf08-160">`utf7`: Codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="ecf08-160">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="ecf08-161">`utf8`: Codiert im UTF-8-Format.</span><span class="sxs-lookup"><span data-stu-id="ecf08-161">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="ecf08-162">`utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="ecf08-162">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="ecf08-163">`utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="ecf08-163">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="ecf08-164">`utf32`: Codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="ecf08-164">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="ecf08-165">Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.).</span><span class="sxs-lookup"><span data-stu-id="ecf08-165">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="ecf08-166">Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="ecf08-166">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="ecf08-167">**UTF-7** \* wird nicht mehr zur Verwendung von empfohlen.</span><span class="sxs-lookup"><span data-stu-id="ecf08-167">**UTF-7** \* is no longer recommended to use.</span></span> <span data-ttu-id="ecf08-168">In PowerShell 7,1 wird eine Warnung geschrieben, wenn Sie `utf7` für den **Encoding** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="ecf08-168">In PowerShell 7.1, a warning is written if you specify `utf7` for the **Encoding** parameter.</span></span>

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

### <span data-ttu-id="ecf08-169">-FilePath</span><span class="sxs-lookup"><span data-stu-id="ecf08-169">-FilePath</span></span>

<span data-ttu-id="ecf08-170">Gibt den Pfad zur Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="ecf08-170">Specifies the path to the output file.</span></span>

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

### <span data-ttu-id="ecf08-171">-Force</span><span class="sxs-lookup"><span data-stu-id="ecf08-171">-Force</span></span>

<span data-ttu-id="ecf08-172">Überschreibt das schreibgeschützte Attribut und überschreibt eine vorhandene schreibgeschützte Datei.</span><span class="sxs-lookup"><span data-stu-id="ecf08-172">Overrides the read-only attribute and overwrites an existing read-only file.</span></span> <span data-ttu-id="ecf08-173">Der **Force** -Parameter überschreibt keine Sicherheitseinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="ecf08-173">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="ecf08-174">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ecf08-174">-InputObject</span></span>

<span data-ttu-id="ecf08-175">Gibt die in die Datei zu schreibenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="ecf08-175">Specifies the objects to be written to the file.</span></span> <span data-ttu-id="ecf08-176">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ecf08-176">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="ecf08-177">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="ecf08-177">-LiteralPath</span></span>

<span data-ttu-id="ecf08-178">Gibt den Pfad zur Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="ecf08-178">Specifies the path to the output file.</span></span> <span data-ttu-id="ecf08-179">Der **literalpath** -Parameter wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="ecf08-179">The **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="ecf08-180">Platzhalter Zeichen werden nicht akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="ecf08-180">Wildcard characters are not accepted.</span></span> <span data-ttu-id="ecf08-181">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="ecf08-181">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ecf08-182">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="ecf08-182">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="ecf08-183">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="ecf08-183">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="ecf08-184">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="ecf08-184">-NoClobber</span></span>

<span data-ttu-id="ecf08-185">**NoClobber** verhindert, dass eine vorhandene Datei überschrieben wird, und zeigt eine Meldung an, dass die Datei bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ecf08-185">**NoClobber** prevents an existing file from being overwritten and displays a message that the file already exists.</span></span> <span data-ttu-id="ecf08-186">Wenn eine Datei im angegebenen Pfad vorhanden ist, wird `Out-File` die Datei standardmäßig ohne Warnung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="ecf08-186">By default, if a file exists in the specified path, `Out-File` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="ecf08-187">-Nonewline</span><span class="sxs-lookup"><span data-stu-id="ecf08-187">-NoNewline</span></span>

<span data-ttu-id="ecf08-188">Gibt an, dass der Inhalt, der in die Datei geschrieben wird, nicht mit einem Zeilen Umleitungs Zeichen endet.</span><span class="sxs-lookup"><span data-stu-id="ecf08-188">Specifies that the content written to the file does not end with a newline character.</span></span> <span data-ttu-id="ecf08-189">Die Zeichen folgen Darstellungen der Eingabe Objekte werden verkettet, um die Ausgabe zu bilden.</span><span class="sxs-lookup"><span data-stu-id="ecf08-189">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="ecf08-190">Zwischen den Ausgabe Zeichenfolgen werden keine Leerzeichen oder Zeilenumbrüche eingefügt.</span><span class="sxs-lookup"><span data-stu-id="ecf08-190">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="ecf08-191">Nach der letzten Ausgabe Zeichenfolge wird kein Zeilen Vorstrich hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ecf08-191">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="ecf08-192">-Breite</span><span class="sxs-lookup"><span data-stu-id="ecf08-192">-Width</span></span>

<span data-ttu-id="ecf08-193">Gibt die Anzahl der Zeichen in jeder Zeile der Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="ecf08-193">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="ecf08-194">Alle zusätzlichen Zeichen werden abgeschnitten und nicht umgebrochen.</span><span class="sxs-lookup"><span data-stu-id="ecf08-194">Any additional characters are truncated, not wrapped.</span></span> <span data-ttu-id="ecf08-195">Wenn dieser Parameter nicht verwendet wird, wird die Breite durch die Merkmale des Hosts bestimmt.</span><span class="sxs-lookup"><span data-stu-id="ecf08-195">If this parameter is not used, the width is determined by the characteristics of the host.</span></span> <span data-ttu-id="ecf08-196">Der Standardwert für die PowerShell-Konsole ist 80 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ecf08-196">The default for the PowerShell console is 80 characters.</span></span>

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

### <span data-ttu-id="ecf08-197">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ecf08-197">-Confirm</span></span>

<span data-ttu-id="ecf08-198">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ecf08-198">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ecf08-199">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ecf08-199">-WhatIf</span></span>

<span data-ttu-id="ecf08-200">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ecf08-200">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="ecf08-201">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ecf08-201">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ecf08-202">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ecf08-202">CommonParameters</span></span>

<span data-ttu-id="ecf08-203">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ecf08-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ecf08-204">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ecf08-204">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ecf08-205">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ecf08-205">INPUTS</span></span>

### <span data-ttu-id="ecf08-206">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="ecf08-206">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="ecf08-207">Sie können jedes beliebige Objekt an die Pipeline übergeben `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="ecf08-207">You can pipe any object to `Out-File`.</span></span>

## <span data-ttu-id="ecf08-208">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ecf08-208">OUTPUTS</span></span>

### <span data-ttu-id="ecf08-209">Keine</span><span class="sxs-lookup"><span data-stu-id="ecf08-209">None</span></span>

<span data-ttu-id="ecf08-210">`Out-File` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ecf08-210">`Out-File` does not generate any output.</span></span>

## <span data-ttu-id="ecf08-211">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ecf08-211">NOTES</span></span>

<span data-ttu-id="ecf08-212">Eingabe Objekte werden automatisch wie im Terminal formatiert, Sie können jedoch ein `Format-*` Cmdlet verwenden, um die Formatierung der Ausgabe in der Datei explizit zu steuern.</span><span class="sxs-lookup"><span data-stu-id="ecf08-212">Input objects are automatically formatted as they would be in the terminal, but you can use a `Format-*` cmdlet to explicitly control the formatting of the output to the file.</span></span> <span data-ttu-id="ecf08-213">Zum Beispiel, `Get-Date | Format-List | Out-File out.txt`</span><span class="sxs-lookup"><span data-stu-id="ecf08-213">For example, `Get-Date | Format-List | Out-File out.txt`</span></span>

<span data-ttu-id="ecf08-214">Verwenden Sie die Pipeline, um die Ausgabe eines PowerShell-Befehls an das `Out-File` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="ecf08-214">To send a PowerShell command's output to the `Out-File` cmdlet, use the pipeline.</span></span> <span data-ttu-id="ecf08-215">Alternativ können Sie Daten in einer Variablen speichern und den **Inputobject** -Parameter verwenden, um Daten an das `Out-File` Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="ecf08-215">Alternatively, you can store data in a variable and use the **InputObject** parameter to pass data to the `Out-File` cmdlet.</span></span>

<span data-ttu-id="ecf08-216">`Out-File` speichert Daten in einer Datei, erzeugt aber keine Ausgabe Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="ecf08-216">`Out-File` saves data to a file but it does not produce any output objects to the pipeline.</span></span>

## <span data-ttu-id="ecf08-217">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ecf08-217">RELATED LINKS</span></span>

[<span data-ttu-id="ecf08-218">about_Providers</span><span class="sxs-lookup"><span data-stu-id="ecf08-218">about_Providers</span></span>](../Microsoft.Powershell.Core/About/about_Providers.md)

[<span data-ttu-id="ecf08-219">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="ecf08-219">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="ecf08-220">Out-Default</span><span class="sxs-lookup"><span data-stu-id="ecf08-220">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="ecf08-221">Out-Host</span><span class="sxs-lookup"><span data-stu-id="ecf08-221">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="ecf08-222">Out-Null</span><span class="sxs-lookup"><span data-stu-id="ecf08-222">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="ecf08-223">Out-String</span><span class="sxs-lookup"><span data-stu-id="ecf08-223">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="ecf08-224">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="ecf08-224">Tee-Object</span></span>](Tee-Object.md)

