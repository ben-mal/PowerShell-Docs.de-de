---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 64275e72f8c21942179431b3aed4a17d328aa2e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216724"
---
# <span data-ttu-id="b9d91-103">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="b9d91-103">Format-Hex</span></span>

## <span data-ttu-id="b9d91-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b9d91-104">SYNOPSIS</span></span>

<span data-ttu-id="b9d91-105">Zeigt eine Datei oder eine andere Eingabe als hexadezimal an.</span><span class="sxs-lookup"><span data-stu-id="b9d91-105">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="b9d91-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b9d91-106">SYNTAX</span></span>

### <span data-ttu-id="b9d91-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="b9d91-107">Path (Default)</span></span>

```
Format-Hex [-Path] <string[]> [-Count <long>] [-Offset <long>] [<CommonParameters>]
```

### <span data-ttu-id="b9d91-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b9d91-108">LiteralPath</span></span>

```
Format-Hex -LiteralPath <string[]> [-Count <long>] [-Offset <long>] [<CommonParameters>]
```

### <span data-ttu-id="b9d91-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="b9d91-109">InputObject</span></span>

```
Format-Hex -InputObject <psobject> [-Encoding <Encoding>] [-Count <long>] [-Offset <long>] [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="b9d91-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9d91-110">DESCRIPTION</span></span>

<span data-ttu-id="b9d91-111">Mit dem- `Format-Hex` Cmdlet wird eine Datei oder eine andere Eingabe als hexadezimale Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9d91-111">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="b9d91-112">Um den Offset eines Zeichens aus der Ausgabe zu ermitteln, fügen Sie die Nummer am äußersten linken Rand der Zeile der Zahl am oberen Rand der Spalte für dieses Zeichen hinzu.</span><span class="sxs-lookup"><span data-stu-id="b9d91-112">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="b9d91-113">`Format-Hex`Mithilfe des Cmdlets können Sie den Dateityp einer beschädigten Datei oder einer Datei ermitteln, die möglicherweise keine Dateinamenerweiterung hat.</span><span class="sxs-lookup"><span data-stu-id="b9d91-113">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="b9d91-114">Sie können dieses Cmdlet ausführen und dann die hexadezimale Ausgabe lesen, um Dateiinformationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b9d91-114">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="b9d91-115">Wenn Sie `Format-Hex` für eine Datei verwenden, ignoriert das Cmdlet Zeilen neue Zeichen und gibt den gesamten Inhalt einer Datei in einer Zeichenfolge zurück, in der die Zeilen mit dem Zeilen Abschluss beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="b9d91-115">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="b9d91-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b9d91-116">EXAMPLES</span></span>

### <span data-ttu-id="b9d91-117">Beispiel 1: erhalten der hexadezimalen Darstellung einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b9d91-117">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="b9d91-118">Dieser Befehl gibt die hexadezimalen Werte einer Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="b9d91-118">This command returns the hexadecimal values of a string.</span></span>

```powershell
'Hello World' | Format-Hex
```

```Output
           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   48 65 6C 6C 6F 20 57 6F 72 6C 64                 Hello World
```

<span data-ttu-id="b9d91-119">Die Zeichenfolge **Hallo Welt** wird über die Pipeline an das `Format-Hex` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="b9d91-119">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="b9d91-120">Die hexadezimale Ausgabe von `Format-Hex` zeigt die Werte der einzelnen Zeichen in der Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="b9d91-120">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="b9d91-121">Beispiel 2: Suchen eines Dateityps aus der hexadezimalen Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b9d91-121">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="b9d91-122">In diesem Beispiel wird die hexadezimale Ausgabe verwendet, um den Dateityp zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="b9d91-122">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="b9d91-123">Das-Cmdlet zeigt den vollständigen Pfad der Datei und die hexadezimalen Werte an.</span><span class="sxs-lookup"><span data-stu-id="b9d91-123">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="b9d91-124">Um den folgenden Befehl zu testen, erstellen Sie eine Kopie einer vorhandenen PDF-Datei auf dem lokalen Computer, und benennen Sie die kopierte Datei in um `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="b9d91-124">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to `File.t7f`.</span></span>

```powershell
Format-Hex -Path .\File.t7f
```

```Output
           Path: C:\Test\File.t7f

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D  %PDF-1.5..%????.
00000010   0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70  .1 0 obj..<</Typ
00000020   65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20  e/Catalog/Pages
```

<span data-ttu-id="b9d91-125">Das `Format-Hex` Cmdlet verwendet den **path** -Parameter, um einen Dateinamen im aktuellen Verzeichnis ( **file. T7F** ) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b9d91-125">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, **File.t7f** .</span></span> <span data-ttu-id="b9d91-126">Die Dateierweiterung **. T7F** ist nicht üblich, aber die hexadezimale Ausgabe **% PDF** zeigt, dass es sich um eine PDF-Datei handelt.</span><span class="sxs-lookup"><span data-stu-id="b9d91-126">The file extension **.t7f** is uncommon, but the hexadecimal output **%PDF** shows that it is a PDF file.</span></span>

## <span data-ttu-id="b9d91-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b9d91-127">PARAMETERS</span></span>

### <span data-ttu-id="b9d91-128">-Codierung</span><span class="sxs-lookup"><span data-stu-id="b9d91-128">-Encoding</span></span>

<span data-ttu-id="b9d91-129">Gibt die Codierung der Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="b9d91-129">Specifies the encoding of the output.</span></span> <span data-ttu-id="b9d91-130">Dies gilt nur für `[string]` Eingaben.</span><span class="sxs-lookup"><span data-stu-id="b9d91-130">This only applies to `[string]` input.</span></span> <span data-ttu-id="b9d91-131">Der-Parameter hat keine Auswirkung auf numerische Typen.</span><span class="sxs-lookup"><span data-stu-id="b9d91-131">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="b9d91-132">Der Standardwert ist `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="b9d91-132">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="b9d91-133">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b9d91-133">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="b9d91-134">`ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="b9d91-134">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="b9d91-135">`bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="b9d91-135">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="b9d91-136">`oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="b9d91-136">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="b9d91-137">`unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="b9d91-137">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="b9d91-138">`utf7`: Codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="b9d91-138">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="b9d91-139">`utf8`: Codiert im UTF-8-Format.</span><span class="sxs-lookup"><span data-stu-id="b9d91-139">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="b9d91-140">`utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="b9d91-140">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="b9d91-141">`utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="b9d91-141">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="b9d91-142">`utf32`: Codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="b9d91-142">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="b9d91-143">Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.).</span><span class="sxs-lookup"><span data-stu-id="b9d91-143">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="b9d91-144">Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="b9d91-144">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: Encoding
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b9d91-145">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b9d91-145">-InputObject</span></span>

<span data-ttu-id="b9d91-146">Wird für Pipeline Eingaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9d91-146">Used for pipeline input.</span></span> <span data-ttu-id="b9d91-147">Pipeline Eingaben unterstützen nur bestimmte skalare Typen und `[system.io.fileinfo]` Instanzen für die Weiterleitung von `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="b9d91-147">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="b9d91-148">Die folgenden skalaren Typen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="b9d91-148">The supported scalar types are:</span></span>

- <span data-ttu-id="b9d91-149">`[string]`, `[char]`</span><span class="sxs-lookup"><span data-stu-id="b9d91-149">`[string]`, `[char]`</span></span>
- <span data-ttu-id="b9d91-150">`[byte]`, `[sbyte]`</span><span class="sxs-lookup"><span data-stu-id="b9d91-150">`[byte]`, `[sbyte]`</span></span>
- <span data-ttu-id="b9d91-151">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span><span class="sxs-lookup"><span data-stu-id="b9d91-151">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span></span>
- <span data-ttu-id="b9d91-152">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span><span class="sxs-lookup"><span data-stu-id="b9d91-152">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span></span>
- <span data-ttu-id="b9d91-153">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="b9d91-153">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span></span>
- <span data-ttu-id="b9d91-154">`[single]`, `[float]`, `[double]`</span><span class="sxs-lookup"><span data-stu-id="b9d91-154">`[single]`, `[float]`, `[double]`</span></span>

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

### <span data-ttu-id="b9d91-155">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="b9d91-155">-LiteralPath</span></span>

<span data-ttu-id="b9d91-156">Gibt den kompletten Pfad zu einer Datei an.</span><span class="sxs-lookup"><span data-stu-id="b9d91-156">Specifies the complete path to a file.</span></span> <span data-ttu-id="b9d91-157">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b9d91-157">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="b9d91-158">Dieser Parameter akzeptiert keine Platzhalter Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b9d91-158">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="b9d91-159">Wenn Sie mehrere Pfade zu Dateien angeben möchten, trennen Sie die Pfade durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="b9d91-159">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="b9d91-160">Wenn der **literalpath** -Parameter Escapezeichen enthält, müssen Sie den Pfad in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="b9d91-160">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="b9d91-161">PowerShell interpretiert keine Zeichen in einer einzelnen Zeichenfolge in Anführungszeichen als Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="b9d91-161">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="b9d91-162">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="b9d91-162">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="b9d91-163">-Path</span><span class="sxs-lookup"><span data-stu-id="b9d91-163">-Path</span></span>

<span data-ttu-id="b9d91-164">Gibt den Pfad zu den Dateien an.</span><span class="sxs-lookup"><span data-stu-id="b9d91-164">Specifies the path to files.</span></span> <span data-ttu-id="b9d91-165">Verwenden Sie einen Punkt ( `.` ), um den aktuellen Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b9d91-165">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="b9d91-166">Das Platzhalter Zeichen ( `*` ) wird akzeptiert und kann verwendet werden, um alle Elemente in einem Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b9d91-166">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="b9d91-167">Wenn der **path** -Parameter Escapezeichen enthält, müssen Sie den Pfad in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="b9d91-167">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="b9d91-168">Wenn Sie mehrere Pfade zu Dateien angeben möchten, trennen Sie die Pfade durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="b9d91-168">To specify multiple paths to files, separate the paths with a comma.</span></span>

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

### <span data-ttu-id="b9d91-169">-RAW</span><span class="sxs-lookup"><span data-stu-id="b9d91-169">-Raw</span></span>

<span data-ttu-id="b9d91-170">Dieser Parameter hat keine weiteren Aktionen.</span><span class="sxs-lookup"><span data-stu-id="b9d91-170">This parameter no longer does anything.</span></span> <span data-ttu-id="b9d91-171">Sie wird für die Skript Kompatibilität beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b9d91-171">It is retained for script compatibility.</span></span>

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

### <span data-ttu-id="b9d91-172">-Offset</span><span class="sxs-lookup"><span data-stu-id="b9d91-172">-Offset</span></span>

<span data-ttu-id="b9d91-173">Diese gibt die Anzahl der Bytes an, die von einem Teil der hexadezimalen Ausgabe ausgelassen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b9d91-173">This represents the number of bytes to skip from being part of the hex output.</span></span>

<span data-ttu-id="b9d91-174">Dieser Parameter wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b9d91-174">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="b9d91-175">-Anzahl</span><span class="sxs-lookup"><span data-stu-id="b9d91-175">-Count</span></span>

<span data-ttu-id="b9d91-176">Gibt die Anzahl der Bytes an, die in die hexadezimale Ausgabe eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b9d91-176">This represents the number of bytes to include in the hex output.</span></span>

<span data-ttu-id="b9d91-177">Dieser Parameter wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b9d91-177">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="b9d91-178">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b9d91-178">CommonParameters</span></span>

<span data-ttu-id="b9d91-179">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b9d91-179">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b9d91-180">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b9d91-180">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b9d91-181">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b9d91-181">INPUTS</span></span>

### <span data-ttu-id="b9d91-182">System.String</span><span class="sxs-lookup"><span data-stu-id="b9d91-182">System.String</span></span>

<span data-ttu-id="b9d91-183">Sie können eine Zeichenfolge über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="b9d91-183">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="b9d91-184">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b9d91-184">OUTPUTS</span></span>

### <span data-ttu-id="b9d91-185">Microsoft. PowerShell. Commands. bytecollection</span><span class="sxs-lookup"><span data-stu-id="b9d91-185">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="b9d91-186">Dieses Cmdlet gibt eine **bytecollection** zurück.</span><span class="sxs-lookup"><span data-stu-id="b9d91-186">This cmdlet returns a **ByteCollection** .</span></span> <span data-ttu-id="b9d91-187">Dieses Objekt stellt eine Auflistung von Bytes dar.</span><span class="sxs-lookup"><span data-stu-id="b9d91-187">This object represents a collection of bytes.</span></span> <span data-ttu-id="b9d91-188">Sie enthält Methoden, mit denen die Auflistung von Bytes in eine Zeichenfolge konvertiert wird, die wie jede von zurückgegebene Ausgabezeile formatiert ist `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="b9d91-188">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="b9d91-189">Wenn Sie den **path** -oder **literalpath** -Parameter angeben, enthält das-Objekt auch den Pfad der Datei, die jedes Byte enthält.</span><span class="sxs-lookup"><span data-stu-id="b9d91-189">If you specify the **Path** or **LiteralPath** parameter, the object also contains the path of the file that contains each byte.</span></span>

## <span data-ttu-id="b9d91-190">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b9d91-190">NOTES</span></span>

<span data-ttu-id="b9d91-191">In der äußersten rechten Spalte der Ausgabe wird versucht, die Bytes als ASCII-Zeichen zu Renderen:</span><span class="sxs-lookup"><span data-stu-id="b9d91-191">The right-most column of output tries to render the bytes as ASCII characters:</span></span>

<span data-ttu-id="b9d91-192">Im Allgemeinen wird jedes Byte als Unicode-Codepunkt interpretiert, was Folgendes bedeutet:</span><span class="sxs-lookup"><span data-stu-id="b9d91-192">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="b9d91-193">Druckbare ASCII-Zeichen werden immer korrekt gerendert.</span><span class="sxs-lookup"><span data-stu-id="b9d91-193">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="b9d91-194">Mehr Byte-UTF-8-Zeichen werden nie korrekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b9d91-194">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="b9d91-195">UTF-16-Zeichen werden nur dann ordnungsgemäß dargestellt, wenn Ihr höher gestelltem Byte ist `NUL` .</span><span class="sxs-lookup"><span data-stu-id="b9d91-195">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="b9d91-196">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b9d91-196">RELATED LINKS</span></span>

[<span data-ttu-id="b9d91-197">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="b9d91-197">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="b9d91-198">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="b9d91-198">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="b9d91-199">Format-List</span><span class="sxs-lookup"><span data-stu-id="b9d91-199">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="b9d91-200">Format-Table</span><span class="sxs-lookup"><span data-stu-id="b9d91-200">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="b9d91-201">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="b9d91-201">Format-Wide</span></span>](Format-Wide.md)
