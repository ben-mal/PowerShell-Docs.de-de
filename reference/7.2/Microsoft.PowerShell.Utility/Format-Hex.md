---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: a45e7919b5a24189ca7f50661795ff035c38a037
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597574"
---
# <span data-ttu-id="3759d-102">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="3759d-102">Format-Hex</span></span>

## <span data-ttu-id="3759d-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3759d-103">SYNOPSIS</span></span>

<span data-ttu-id="3759d-104">Zeigt eine Datei oder eine andere Eingabe als hexadezimal an.</span><span class="sxs-lookup"><span data-stu-id="3759d-104">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="3759d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3759d-105">SYNTAX</span></span>

### <span data-ttu-id="3759d-106">Pfad</span><span class="sxs-lookup"><span data-stu-id="3759d-106">Path</span></span>

```
Format-Hex [-Path] <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="3759d-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3759d-107">LiteralPath</span></span>

```
Format-Hex -LiteralPath <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="3759d-108">Byinputobject</span><span class="sxs-lookup"><span data-stu-id="3759d-108">ByInputObject</span></span>

```
Format-Hex -InputObject <PSObject> [-Encoding <Encoding>] [-Count <Int64>] [-Offset <Int64>] [-Raw]
 [<CommonParameters>]
```

## <span data-ttu-id="3759d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3759d-109">DESCRIPTION</span></span>

<span data-ttu-id="3759d-110">Mit dem- `Format-Hex` Cmdlet wird eine Datei oder eine andere Eingabe als hexadezimale Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3759d-110">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="3759d-111">Um den Offset eines Zeichens aus der Ausgabe zu ermitteln, fügen Sie die Nummer am äußersten linken Rand der Zeile der Zahl am oberen Rand der Spalte für dieses Zeichen hinzu.</span><span class="sxs-lookup"><span data-stu-id="3759d-111">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="3759d-112">`Format-Hex`Mithilfe des Cmdlets können Sie den Dateityp einer beschädigten Datei oder einer Datei ermitteln, die möglicherweise keine Dateinamenerweiterung hat.</span><span class="sxs-lookup"><span data-stu-id="3759d-112">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="3759d-113">Sie können dieses Cmdlet ausführen und dann die hexadezimale Ausgabe lesen, um Dateiinformationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3759d-113">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="3759d-114">Wenn Sie `Format-Hex` für eine Datei verwenden, ignoriert das Cmdlet Zeilen neue Zeichen und gibt den gesamten Inhalt einer Datei in einer Zeichenfolge zurück, in der die Zeilen mit dem Zeilen Abschluss beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="3759d-114">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="3759d-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3759d-115">EXAMPLES</span></span>

### <span data-ttu-id="3759d-116">Beispiel 1: erhalten der hexadezimalen Darstellung einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3759d-116">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="3759d-117">Dieser Befehl gibt die hexadezimalen Werte einer Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="3759d-117">This command returns the hexadecimal values of a string.</span></span>

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

<span data-ttu-id="3759d-118">Die Zeichenfolge **Hallo Welt** wird über die Pipeline an das `Format-Hex` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="3759d-118">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="3759d-119">Die hexadezimale Ausgabe von `Format-Hex` zeigt die Werte der einzelnen Zeichen in der Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="3759d-119">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="3759d-120">Beispiel 2: Suchen eines Dateityps aus der hexadezimalen Ausgabe</span><span class="sxs-lookup"><span data-stu-id="3759d-120">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="3759d-121">In diesem Beispiel wird die hexadezimale Ausgabe verwendet, um den Dateityp zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="3759d-121">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="3759d-122">Das-Cmdlet zeigt den vollständigen Pfad der Datei und die hexadezimalen Werte an.</span><span class="sxs-lookup"><span data-stu-id="3759d-122">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="3759d-123">Um den folgenden Befehl zu testen, erstellen Sie eine Kopie einer vorhandenen PDF-Datei auf dem lokalen Computer, und benennen Sie die kopierte Datei in um `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="3759d-123">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to `File.t7f`.</span></span>

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

<span data-ttu-id="3759d-124">Das `Format-Hex` Cmdlet verwendet den **path** -Parameter, um einen Dateinamen im aktuellen Verzeichnis anzugeben `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="3759d-124">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, `File.t7f`.</span></span> <span data-ttu-id="3759d-125">Die Dateierweiterung `.t7f` ist nicht üblich, aber die hexadezimale Ausgabe `%PDF` zeigt, dass es sich um eine PDF-Datei handelt.</span><span class="sxs-lookup"><span data-stu-id="3759d-125">The file extension `.t7f` is uncommon, but the hexadecimal output `%PDF` shows that it is a PDF file.</span></span> <span data-ttu-id="3759d-126">In diesem Beispiel wird der **count** -Parameter verwendet, um die Ausgabe auf die ersten 48 Bytes der Datei zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="3759d-126">In this example, the **Count** parameter is used to limit the output to the first 48 bytes of the file.</span></span>

### <span data-ttu-id="3759d-127">Beispiel 3: Formatieren eines Arrays mit unterschiedlichen Datentypen</span><span class="sxs-lookup"><span data-stu-id="3759d-127">Example 3: Format an array of different data types</span></span>

<span data-ttu-id="3759d-128">In diesem Beispiel wird ein Array verschiedener Datentypen verwendet, um hervorzuheben, wie `Format-Hex` Sie in der Pipeline behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="3759d-128">This example uses an array of different data types to highlight how `Format-Hex` handles them in the Pipeline.</span></span>

<span data-ttu-id="3759d-129">Jedes Objekt wird durch die Pipeline übergeben und einzeln verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="3759d-129">It will pass each object through the Pipeline and process individually.</span></span> <span data-ttu-id="3759d-130">Wenn es sich jedoch um numerische Daten handelt und das angrenzende Objekt auch numerisch ist, werden diese in einem einzelnen Ausgabe Block gruppiert.</span><span class="sxs-lookup"><span data-stu-id="3759d-130">However, if it's numeric data, and the adjacent object is also numeric, it will group them into a single output block.</span></span>

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
0000000000000000 EF BE AD DE 00 00 00 40 5C 03 00 00             ï¾-Þ   @\�

   Label: Boolean (System.Boolean) <7D8C4C1D>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 00 00 00 00                         �
```

## <span data-ttu-id="3759d-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3759d-131">PARAMETERS</span></span>

### <span data-ttu-id="3759d-132">-Codierung</span><span class="sxs-lookup"><span data-stu-id="3759d-132">-Encoding</span></span>

<span data-ttu-id="3759d-133">Gibt die Codierung der Eingabe Zeichenfolgen an.</span><span class="sxs-lookup"><span data-stu-id="3759d-133">Specifies the encoding of the input strings.</span></span> <span data-ttu-id="3759d-134">Dies gilt nur für `[string]` Eingaben.</span><span class="sxs-lookup"><span data-stu-id="3759d-134">This only applies to `[string]` input.</span></span> <span data-ttu-id="3759d-135">Der-Parameter hat keine Auswirkung auf numerische Typen.</span><span class="sxs-lookup"><span data-stu-id="3759d-135">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="3759d-136">Der Ausgabewert ist immer `utf8NoBOM` .</span><span class="sxs-lookup"><span data-stu-id="3759d-136">The output value is always `utf8NoBOM`.</span></span>

<span data-ttu-id="3759d-137">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3759d-137">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="3759d-138">`ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="3759d-138">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="3759d-139">`bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="3759d-139">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="3759d-140">`bigendianutf32`: Codiert im UTF-32-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="3759d-140">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="3759d-141">`oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="3759d-141">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="3759d-142">`unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="3759d-142">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="3759d-143">`utf7`: Codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="3759d-143">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="3759d-144">`utf8`: Codiert im UTF-8-Format.</span><span class="sxs-lookup"><span data-stu-id="3759d-144">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="3759d-145">`utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="3759d-145">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="3759d-146">`utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="3759d-146">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="3759d-147">`utf32`: Codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="3759d-147">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="3759d-148">Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.).</span><span class="sxs-lookup"><span data-stu-id="3759d-148">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="3759d-149">Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="3759d-149">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="3759d-150">**UTF-7** _ wird nicht mehr für die Verwendung von empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3759d-150">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="3759d-151">In PowerShell 7,1 wird eine Warnung geschrieben, wenn Sie `utf7` für den Parameter "_ \*Encoding\*\*" angeben.</span><span class="sxs-lookup"><span data-stu-id="3759d-151">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3759d-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3759d-152">-InputObject</span></span>

<span data-ttu-id="3759d-153">Wird für Pipeline Eingaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="3759d-153">Used for pipeline input.</span></span> <span data-ttu-id="3759d-154">Pipeline Eingaben unterstützen nur bestimmte skalare Typen und `[system.io.fileinfo]` Instanzen für die Weiterleitung von `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="3759d-154">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="3759d-155">Die folgenden skalaren Typen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="3759d-155">The supported scalar types are:</span></span>

- <span data-ttu-id="3759d-156">`[string]`, `[char]`</span><span class="sxs-lookup"><span data-stu-id="3759d-156">`[string]`, `[char]`</span></span>
- <span data-ttu-id="3759d-157">`[byte]`, `[sbyte]`</span><span class="sxs-lookup"><span data-stu-id="3759d-157">`[byte]`, `[sbyte]`</span></span>
- <span data-ttu-id="3759d-158">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span><span class="sxs-lookup"><span data-stu-id="3759d-158">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span></span>
- <span data-ttu-id="3759d-159">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span><span class="sxs-lookup"><span data-stu-id="3759d-159">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span></span>
- <span data-ttu-id="3759d-160">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="3759d-160">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span></span>
- <span data-ttu-id="3759d-161">`[single]`, `[float]`, `[double]`</span><span class="sxs-lookup"><span data-stu-id="3759d-161">`[single]`, `[float]`, `[double]`</span></span>
- `[boolean]`

<span data-ttu-id="3759d-162">Vor PowerShell 6,2 `Format-Hex` verarbeitet eine Pipeline Eingabe mit mehreren Eingabetypen, indem alle like-Objekte gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="3759d-162">Prior to PowerShell 6.2, `Format-Hex` would handle a Pipeline input with multiple input types by grouping all like objects together.</span></span> <span data-ttu-id="3759d-163">Nun werden die einzelnen Objekte verarbeitet, wenn Sie die Pipeline durchlaufen, und Objekte nicht gruppieren, es sei denn, die Objekte sind angrenzend.</span><span class="sxs-lookup"><span data-stu-id="3759d-163">Now, it handles each individual object as it passes through the Pipeline and won't group objects together unless like objects are adjacent.</span></span>

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

### <span data-ttu-id="3759d-164">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="3759d-164">-LiteralPath</span></span>

<span data-ttu-id="3759d-165">Gibt den kompletten Pfad zu einer Datei an.</span><span class="sxs-lookup"><span data-stu-id="3759d-165">Specifies the complete path to a file.</span></span> <span data-ttu-id="3759d-166">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3759d-166">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="3759d-167">Dieser Parameter akzeptiert keine Platzhalter Zeichen.</span><span class="sxs-lookup"><span data-stu-id="3759d-167">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="3759d-168">Wenn Sie mehrere Pfade zu Dateien angeben möchten, trennen Sie die Pfade durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="3759d-168">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="3759d-169">Wenn der **literalpath** -Parameter Escapezeichen enthält, müssen Sie den Pfad in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="3759d-169">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="3759d-170">PowerShell interpretiert keine Zeichen in einer einzelnen Zeichenfolge in Anführungszeichen als Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="3759d-170">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="3759d-171">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="3759d-171">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="3759d-172">-Path</span><span class="sxs-lookup"><span data-stu-id="3759d-172">-Path</span></span>

<span data-ttu-id="3759d-173">Gibt den Pfad zu den Dateien an.</span><span class="sxs-lookup"><span data-stu-id="3759d-173">Specifies the path to files.</span></span> <span data-ttu-id="3759d-174">Verwenden Sie einen Punkt ( `.` ), um den aktuellen Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3759d-174">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="3759d-175">Das Platzhalter Zeichen ( `*` ) wird akzeptiert und kann verwendet werden, um alle Elemente in einem Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3759d-175">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="3759d-176">Wenn der **path** -Parameter Escapezeichen enthält, müssen Sie den Pfad in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="3759d-176">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="3759d-177">Wenn Sie mehrere Pfade zu Dateien angeben möchten, trennen Sie die Pfade durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="3759d-177">To specify multiple paths to files, separate the paths with a comma.</span></span>

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

### <span data-ttu-id="3759d-178">-RAW</span><span class="sxs-lookup"><span data-stu-id="3759d-178">-Raw</span></span>

<span data-ttu-id="3759d-179">Dieser Parameter hat keine weiteren Aktionen.</span><span class="sxs-lookup"><span data-stu-id="3759d-179">This parameter no longer does anything.</span></span> <span data-ttu-id="3759d-180">Sie wird für die Skript Kompatibilität beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3759d-180">It is retained for script compatibility.</span></span>

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

### <span data-ttu-id="3759d-181">-Offset</span><span class="sxs-lookup"><span data-stu-id="3759d-181">-Offset</span></span>

<span data-ttu-id="3759d-182">Diese gibt die Anzahl der Bytes an, die von einem Teil der hexadezimalen Ausgabe ausgelassen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3759d-182">This represents the number of bytes to skip from being part of the hex output.</span></span>

<span data-ttu-id="3759d-183">Dieser Parameter wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3759d-183">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="3759d-184">-Anzahl</span><span class="sxs-lookup"><span data-stu-id="3759d-184">-Count</span></span>

<span data-ttu-id="3759d-185">Gibt die Anzahl der Bytes an, die in die hexadezimale Ausgabe eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3759d-185">This represents the number of bytes to include in the hex output.</span></span>

<span data-ttu-id="3759d-186">Dieser Parameter wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3759d-186">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="3759d-187">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3759d-187">CommonParameters</span></span>

<span data-ttu-id="3759d-188">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3759d-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3759d-189">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3759d-189">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3759d-190">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3759d-190">INPUTS</span></span>

### <span data-ttu-id="3759d-191">System.String</span><span class="sxs-lookup"><span data-stu-id="3759d-191">System.String</span></span>

<span data-ttu-id="3759d-192">Sie können eine Zeichenfolge über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="3759d-192">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="3759d-193">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3759d-193">OUTPUTS</span></span>

### <span data-ttu-id="3759d-194">Microsoft. PowerShell. Commands. bytecollection</span><span class="sxs-lookup"><span data-stu-id="3759d-194">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="3759d-195">Dieses Cmdlet gibt eine **bytecollection** zurück.</span><span class="sxs-lookup"><span data-stu-id="3759d-195">This cmdlet returns a **ByteCollection**.</span></span> <span data-ttu-id="3759d-196">Dieses Objekt stellt eine Auflistung von Bytes dar.</span><span class="sxs-lookup"><span data-stu-id="3759d-196">This object represents a collection of bytes.</span></span> <span data-ttu-id="3759d-197">Sie enthält Methoden, mit denen die Auflistung von Bytes in eine Zeichenfolge konvertiert wird, die wie jede von zurückgegebene Ausgabezeile formatiert ist `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="3759d-197">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="3759d-198">Die Ausgabe gibt auch an, welche Bytes verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3759d-198">The output also states they type of bytes being processed.</span></span> <span data-ttu-id="3759d-199">Wenn Sie den **path** -oder **literalpath** -Parameter angeben, enthält das-Objekt den Pfad der Datei, die jedes Byte enthält.</span><span class="sxs-lookup"><span data-stu-id="3759d-199">If you specify the **Path** or **LiteralPath** parameter, the object contains the path of the file that contains each byte.</span></span> <span data-ttu-id="3759d-200">Wenn Sie eine Zeichenfolge, einen booleschen Wert, einen ganzzahligen Wert usw. übergeben, wird dieser entsprechend gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="3759d-200">If you pass a string, boolean, integer, etc, it will be labeled appropriately.</span></span>

## <span data-ttu-id="3759d-201">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3759d-201">NOTES</span></span>

<span data-ttu-id="3759d-202">In der äußersten rechten Spalte der Ausgabe wird versucht, die Bytes als ASCII-Zeichen zu Renderen:</span><span class="sxs-lookup"><span data-stu-id="3759d-202">The right-most column of output tries to render the bytes as ASCII characters:</span></span>

<span data-ttu-id="3759d-203">Im Allgemeinen wird jedes Byte als Unicode-Codepunkt interpretiert, was Folgendes bedeutet:</span><span class="sxs-lookup"><span data-stu-id="3759d-203">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="3759d-204">Druckbare ASCII-Zeichen werden immer korrekt gerendert.</span><span class="sxs-lookup"><span data-stu-id="3759d-204">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="3759d-205">Mehr Byte-UTF-8-Zeichen werden nie korrekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3759d-205">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="3759d-206">UTF-16-Zeichen werden nur dann ordnungsgemäß dargestellt, wenn Ihr höher gestelltem Byte ist `NUL` .</span><span class="sxs-lookup"><span data-stu-id="3759d-206">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="3759d-207">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3759d-207">RELATED LINKS</span></span>

[<span data-ttu-id="3759d-208">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="3759d-208">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="3759d-209">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="3759d-209">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="3759d-210">Format-List</span><span class="sxs-lookup"><span data-stu-id="3759d-210">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="3759d-211">Format-Table</span><span class="sxs-lookup"><span data-stu-id="3759d-211">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="3759d-212">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="3759d-212">Format-Wide</span></span>](Format-Wide.md)

