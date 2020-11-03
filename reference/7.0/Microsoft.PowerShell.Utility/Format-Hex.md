---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 6cb02f1c6f2583ce4146356fac3553e99a54c7c2
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211031"
---
# <span data-ttu-id="fdc05-103">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="fdc05-103">Format-Hex</span></span>

## <span data-ttu-id="fdc05-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="fdc05-104">SYNOPSIS</span></span>

<span data-ttu-id="fdc05-105">Zeigt eine Datei oder eine andere Eingabe als hexadezimal an.</span><span class="sxs-lookup"><span data-stu-id="fdc05-105">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="fdc05-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fdc05-106">SYNTAX</span></span>

### <span data-ttu-id="fdc05-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="fdc05-107">Path (Default)</span></span>

```
Format-Hex [-Path] <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="fdc05-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="fdc05-108">LiteralPath</span></span>

```
Format-Hex -LiteralPath <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="fdc05-109">Byinputobject</span><span class="sxs-lookup"><span data-stu-id="fdc05-109">ByInputObject</span></span>
```
Format-Hex -InputObject <PSObject> [-Encoding <Encoding>] [-Count <Int64>] [-Offset <Int64>] [-Raw]
 [<CommonParameters>]
```

## <span data-ttu-id="fdc05-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fdc05-110">DESCRIPTION</span></span>

<span data-ttu-id="fdc05-111">Mit dem- `Format-Hex` Cmdlet wird eine Datei oder eine andere Eingabe als hexadezimale Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fdc05-111">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="fdc05-112">Um den Offset eines Zeichens aus der Ausgabe zu ermitteln, fügen Sie die Nummer am äußersten linken Rand der Zeile der Zahl am oberen Rand der Spalte für dieses Zeichen hinzu.</span><span class="sxs-lookup"><span data-stu-id="fdc05-112">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="fdc05-113">`Format-Hex`Mithilfe des Cmdlets können Sie den Dateityp einer beschädigten Datei oder einer Datei ermitteln, die möglicherweise keine Dateinamenerweiterung hat.</span><span class="sxs-lookup"><span data-stu-id="fdc05-113">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="fdc05-114">Sie können dieses Cmdlet ausführen und dann die hexadezimale Ausgabe lesen, um Dateiinformationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fdc05-114">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="fdc05-115">Wenn Sie `Format-Hex` für eine Datei verwenden, ignoriert das Cmdlet Zeilen neue Zeichen und gibt den gesamten Inhalt einer Datei in einer Zeichenfolge zurück, in der die Zeilen mit dem Zeilen Abschluss beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="fdc05-115">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="fdc05-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="fdc05-116">EXAMPLES</span></span>

### <span data-ttu-id="fdc05-117">Beispiel 1: erhalten der hexadezimalen Darstellung einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fdc05-117">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="fdc05-118">Dieser Befehl gibt die hexadezimalen Werte einer Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="fdc05-118">This command returns the hexadecimal values of a string.</span></span>

```powershell
'Hello World' | Format-Hex
```

```Output
   Label: String (System.String) <2944BEC3>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 48 65 6C 6C 6F 20 57 6F 72 6C 64                Hello World
```

<span data-ttu-id="fdc05-119">Die Zeichenfolge **Hallo Welt** wird über die Pipeline an das `Format-Hex` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="fdc05-119">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="fdc05-120">Die hexadezimale Ausgabe von `Format-Hex` zeigt die Werte der einzelnen Zeichen in der Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="fdc05-120">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="fdc05-121">Beispiel 2: Suchen eines Dateityps aus der hexadezimalen Ausgabe</span><span class="sxs-lookup"><span data-stu-id="fdc05-121">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="fdc05-122">In diesem Beispiel wird die hexadezimale Ausgabe verwendet, um den Dateityp zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="fdc05-122">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="fdc05-123">Das-Cmdlet zeigt den vollständigen Pfad der Datei und die hexadezimalen Werte an.</span><span class="sxs-lookup"><span data-stu-id="fdc05-123">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="fdc05-124">Um den folgenden Befehl zu testen, erstellen Sie eine Kopie einer vorhandenen PDF-Datei auf dem lokalen Computer, und benennen Sie die kopierte Datei in um `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="fdc05-124">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to `File.t7f`.</span></span>

```powershell
Format-Hex -Path .\File.t7f -Count 48
```

```Output
   Label: C:\Test\File.t7f

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D %PDF-1.5..%????.
0000000000000010 0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70 .1 0 obj..<</Typ
0000000000000020 65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20 e/Catalog/Pages
```

<span data-ttu-id="fdc05-125">Das `Format-Hex` Cmdlet verwendet den **path** -Parameter, um einen Dateinamen im aktuellen Verzeichnis anzugeben `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="fdc05-125">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, `File.t7f`.</span></span> <span data-ttu-id="fdc05-126">Die Dateierweiterung `.t7f` ist nicht üblich, aber die hexadezimale Ausgabe `%PDF` zeigt, dass es sich um eine PDF-Datei handelt.</span><span class="sxs-lookup"><span data-stu-id="fdc05-126">The file extension `.t7f` is uncommon, but the hexadecimal output `%PDF` shows that it is a PDF file.</span></span> <span data-ttu-id="fdc05-127">In diesem Beispiel wird der **count** -Parameter verwendet, um die Ausgabe auf die ersten 48 Bytes der Datei zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="fdc05-127">In this example, the **Count** parameter is used to limit the output to the first 48 bytes of the file.</span></span>

### <span data-ttu-id="fdc05-128">Beispiel 3: Formatieren eines Arrays mit unterschiedlichen Datentypen</span><span class="sxs-lookup"><span data-stu-id="fdc05-128">Example 3: Format an array of different data types</span></span>

<span data-ttu-id="fdc05-129">In diesem Beispiel wird ein Array verschiedener Datentypen verwendet, um hervorzuheben, wie `Format-Hex` Sie in der Pipeline behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="fdc05-129">This example uses an array of different data types to highlight how `Format-Hex` handles them in the Pipeline.</span></span>

<span data-ttu-id="fdc05-130">Jedes Objekt wird durch die Pipeline übergeben und einzeln verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="fdc05-130">It will pass each object through the Pipeline and process individually.</span></span> <span data-ttu-id="fdc05-131">Wenn es sich jedoch um numerische Daten handelt und das angrenzende Objekt auch numerisch ist, werden diese in einem einzelnen Ausgabe Block gruppiert.</span><span class="sxs-lookup"><span data-stu-id="fdc05-131">However, if it's numeric data, and the adjacent object is also numeric, it will group them into a single output block.</span></span>

```powershell
'Hello world!', 1, 1138, 'foo', 'bar', 0xdeadbeef, 1gb, 0b1101011100 , $true, $false | Format-Hex
```

```Output
   Label: String (System.String) <24F1F0A3>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 48 65 6C 6C 6F 20 77 6F 72 6C 64 21             Hello world!

   Label: Int32 (System.Int32) <2EB933C5>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 72 04 00 00                         �   r�

   Label: String (System.String) <4078B66C>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 66 6F 6F                                        foo

   Label: String (System.String) <51E4A317>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 62 61 72                                        bar

   Label: Int32 (System.Int32) <5ADF167B>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 EF BE AD DE 00 00 00 40 5C 03 00 00             ï¾­Þ   @\�

   Label: Boolean (System.Boolean) <7D8C4C1D>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 00 00 00 00                         �
```

## <span data-ttu-id="fdc05-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fdc05-132">PARAMETERS</span></span>

### <span data-ttu-id="fdc05-133">-Codierung</span><span class="sxs-lookup"><span data-stu-id="fdc05-133">-Encoding</span></span>

<span data-ttu-id="fdc05-134">Gibt die Codierung der Eingabe Zeichenfolgen an.</span><span class="sxs-lookup"><span data-stu-id="fdc05-134">Specifies the encoding of the input strings.</span></span> <span data-ttu-id="fdc05-135">Dies gilt nur für `[string]` Eingaben.</span><span class="sxs-lookup"><span data-stu-id="fdc05-135">This only applies to `[string]` input.</span></span> <span data-ttu-id="fdc05-136">Der-Parameter hat keine Auswirkung auf numerische Typen.</span><span class="sxs-lookup"><span data-stu-id="fdc05-136">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="fdc05-137">Der Ausgabewert ist immer `utf8NoBOM` .</span><span class="sxs-lookup"><span data-stu-id="fdc05-137">The output value is always `utf8NoBOM`.</span></span>

<span data-ttu-id="fdc05-138">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fdc05-138">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="fdc05-139">`ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="fdc05-139">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="fdc05-140">`bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="fdc05-140">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="fdc05-141">`oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="fdc05-141">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="fdc05-142">`unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="fdc05-142">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="fdc05-143">`utf7`: Codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="fdc05-143">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="fdc05-144">`utf8`: Codiert im UTF-8-Format.</span><span class="sxs-lookup"><span data-stu-id="fdc05-144">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="fdc05-145">`utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="fdc05-145">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="fdc05-146">`utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="fdc05-146">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="fdc05-147">`utf32`: Codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="fdc05-147">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="fdc05-148">Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.).</span><span class="sxs-lookup"><span data-stu-id="fdc05-148">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="fdc05-149">Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="fdc05-149">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fdc05-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fdc05-150">-InputObject</span></span>

<span data-ttu-id="fdc05-151">Wird für Pipeline Eingaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="fdc05-151">Used for pipeline input.</span></span> <span data-ttu-id="fdc05-152">Pipeline Eingaben unterstützen nur bestimmte skalare Typen und `[system.io.fileinfo]` Instanzen für die Weiterleitung von `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="fdc05-152">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="fdc05-153">Die folgenden skalaren Typen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="fdc05-153">The supported scalar types are:</span></span>

- <span data-ttu-id="fdc05-154">`[string]`, `[char]`</span><span class="sxs-lookup"><span data-stu-id="fdc05-154">`[string]`, `[char]`</span></span>
- <span data-ttu-id="fdc05-155">`[byte]`, `[sbyte]`</span><span class="sxs-lookup"><span data-stu-id="fdc05-155">`[byte]`, `[sbyte]`</span></span>
- <span data-ttu-id="fdc05-156">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span><span class="sxs-lookup"><span data-stu-id="fdc05-156">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span></span>
- <span data-ttu-id="fdc05-157">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span><span class="sxs-lookup"><span data-stu-id="fdc05-157">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span></span>
- <span data-ttu-id="fdc05-158">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="fdc05-158">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span></span>
- <span data-ttu-id="fdc05-159">`[single]`, `[float]`, `[double]`</span><span class="sxs-lookup"><span data-stu-id="fdc05-159">`[single]`, `[float]`, `[double]`</span></span>
- `[boolean]`

<span data-ttu-id="fdc05-160">Vor PowerShell 6,2 `Format-Hex` verarbeitet eine Pipeline Eingabe mit mehreren Eingabetypen, indem alle like-Objekte gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="fdc05-160">Prior to PowerShell 6.2, `Format-Hex` would handle a Pipeline input with multiple input types by grouping all like objects together.</span></span> <span data-ttu-id="fdc05-161">Nun werden die einzelnen Objekte verarbeitet, wenn Sie die Pipeline durchlaufen, und Objekte nicht gruppieren, es sei denn, die Objekte sind angrenzend.</span><span class="sxs-lookup"><span data-stu-id="fdc05-161">Now, it handles each individual object as it passes through the Pipeline and won't group objects together unless like objects are adjacent.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fdc05-162">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="fdc05-162">-LiteralPath</span></span>

<span data-ttu-id="fdc05-163">Gibt den kompletten Pfad zu einer Datei an.</span><span class="sxs-lookup"><span data-stu-id="fdc05-163">Specifies the complete path to a file.</span></span> <span data-ttu-id="fdc05-164">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="fdc05-164">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="fdc05-165">Dieser Parameter akzeptiert keine Platzhalter Zeichen.</span><span class="sxs-lookup"><span data-stu-id="fdc05-165">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="fdc05-166">Wenn Sie mehrere Pfade zu Dateien angeben möchten, trennen Sie die Pfade durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="fdc05-166">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="fdc05-167">Wenn der **literalpath** -Parameter Escapezeichen enthält, müssen Sie den Pfad in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="fdc05-167">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="fdc05-168">PowerShell interpretiert keine Zeichen in einer einzelnen Zeichenfolge in Anführungszeichen als Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="fdc05-168">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="fdc05-169">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="fdc05-169">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fdc05-170">-Path</span><span class="sxs-lookup"><span data-stu-id="fdc05-170">-Path</span></span>

<span data-ttu-id="fdc05-171">Gibt den Pfad zu den Dateien an.</span><span class="sxs-lookup"><span data-stu-id="fdc05-171">Specifies the path to files.</span></span> <span data-ttu-id="fdc05-172">Verwenden Sie einen Punkt ( `.` ), um den aktuellen Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fdc05-172">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="fdc05-173">Das Platzhalter Zeichen ( `*` ) wird akzeptiert und kann verwendet werden, um alle Elemente in einem Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fdc05-173">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="fdc05-174">Wenn der **path** -Parameter Escapezeichen enthält, müssen Sie den Pfad in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="fdc05-174">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="fdc05-175">Wenn Sie mehrere Pfade zu Dateien angeben möchten, trennen Sie die Pfade durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="fdc05-175">To specify multiple paths to files, separate the paths with a comma.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="fdc05-176">-RAW</span><span class="sxs-lookup"><span data-stu-id="fdc05-176">-Raw</span></span>

<span data-ttu-id="fdc05-177">Dieser Parameter hat keine weiteren Aktionen.</span><span class="sxs-lookup"><span data-stu-id="fdc05-177">This parameter no longer does anything.</span></span> <span data-ttu-id="fdc05-178">Sie wird für die Skript Kompatibilität beibehalten.</span><span class="sxs-lookup"><span data-stu-id="fdc05-178">It is retained for script compatibility.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fdc05-179">-Offset</span><span class="sxs-lookup"><span data-stu-id="fdc05-179">-Offset</span></span>

<span data-ttu-id="fdc05-180">Diese gibt die Anzahl der Bytes an, die von einem Teil der hexadezimalen Ausgabe ausgelassen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fdc05-180">This represents the number of bytes to skip from being part of the hex output.</span></span>

<span data-ttu-id="fdc05-181">Dieser Parameter wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fdc05-181">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fdc05-182">-Anzahl</span><span class="sxs-lookup"><span data-stu-id="fdc05-182">-Count</span></span>

<span data-ttu-id="fdc05-183">Gibt die Anzahl der Bytes an, die in die hexadezimale Ausgabe eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fdc05-183">This represents the number of bytes to include in the hex output.</span></span>

<span data-ttu-id="fdc05-184">Dieser Parameter wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fdc05-184">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Int64.MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fdc05-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fdc05-185">CommonParameters</span></span>

<span data-ttu-id="fdc05-186">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fdc05-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fdc05-187">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fdc05-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fdc05-188">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="fdc05-188">INPUTS</span></span>

### <span data-ttu-id="fdc05-189">System.String</span><span class="sxs-lookup"><span data-stu-id="fdc05-189">System.String</span></span>

<span data-ttu-id="fdc05-190">Sie können eine Zeichenfolge über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="fdc05-190">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="fdc05-191">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="fdc05-191">OUTPUTS</span></span>

### <span data-ttu-id="fdc05-192">Microsoft. PowerShell. Commands. bytecollection</span><span class="sxs-lookup"><span data-stu-id="fdc05-192">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="fdc05-193">Dieses Cmdlet gibt eine **bytecollection** zurück.</span><span class="sxs-lookup"><span data-stu-id="fdc05-193">This cmdlet returns a **ByteCollection** .</span></span> <span data-ttu-id="fdc05-194">Dieses Objekt stellt eine Auflistung von Bytes dar.</span><span class="sxs-lookup"><span data-stu-id="fdc05-194">This object represents a collection of bytes.</span></span> <span data-ttu-id="fdc05-195">Sie enthält Methoden, mit denen die Auflistung von Bytes in eine Zeichenfolge konvertiert wird, die wie jede von zurückgegebene Ausgabezeile formatiert ist `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="fdc05-195">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="fdc05-196">Die Ausgabe gibt auch an, welche Bytes verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="fdc05-196">The output also states they type of bytes being processed.</span></span> <span data-ttu-id="fdc05-197">Wenn Sie den **path** -oder **literalpath** -Parameter angeben, enthält das-Objekt den Pfad der Datei, die jedes Byte enthält.</span><span class="sxs-lookup"><span data-stu-id="fdc05-197">If you specify the **Path** or **LiteralPath** parameter, the object contains the path of the file that contains each byte.</span></span> <span data-ttu-id="fdc05-198">Wenn Sie eine Zeichenfolge, einen booleschen Wert, einen ganzzahligen Wert usw. übergeben, wird dieser entsprechend gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="fdc05-198">If you pass a string, boolean, integer, etc, it will be labeled appropriately.</span></span>

## <span data-ttu-id="fdc05-199">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="fdc05-199">NOTES</span></span>

<span data-ttu-id="fdc05-200">In der äußersten rechten Spalte der Ausgabe wird versucht, die Bytes als ASCII-Zeichen zu Renderen:</span><span class="sxs-lookup"><span data-stu-id="fdc05-200">The right-most column of output tries to render the bytes as ASCII characters:</span></span>

<span data-ttu-id="fdc05-201">Im Allgemeinen wird jedes Byte als Unicode-Codepunkt interpretiert, was Folgendes bedeutet:</span><span class="sxs-lookup"><span data-stu-id="fdc05-201">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="fdc05-202">Druckbare ASCII-Zeichen werden immer korrekt gerendert.</span><span class="sxs-lookup"><span data-stu-id="fdc05-202">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="fdc05-203">Mehr Byte-UTF-8-Zeichen werden nie korrekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="fdc05-203">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="fdc05-204">UTF-16-Zeichen werden nur dann ordnungsgemäß dargestellt, wenn Ihr höher gestelltem Byte ist `NUL` .</span><span class="sxs-lookup"><span data-stu-id="fdc05-204">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="fdc05-205">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="fdc05-205">RELATED LINKS</span></span>

[<span data-ttu-id="fdc05-206">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="fdc05-206">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="fdc05-207">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="fdc05-207">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="fdc05-208">Format-List</span><span class="sxs-lookup"><span data-stu-id="fdc05-208">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="fdc05-209">Format-Table</span><span class="sxs-lookup"><span data-stu-id="fdc05-209">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="fdc05-210">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="fdc05-210">Format-Wide</span></span>](Format-Wide.md)
