---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 514a66ebee3827de998622a738c75d4f8e0c7279
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214028"
---
# <span data-ttu-id="39481-103">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="39481-103">Format-Hex</span></span>

## <span data-ttu-id="39481-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="39481-104">SYNOPSIS</span></span>

<span data-ttu-id="39481-105">Zeigt eine Datei oder eine andere Eingabe als hexadezimal an.</span><span class="sxs-lookup"><span data-stu-id="39481-105">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="39481-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="39481-106">SYNTAX</span></span>

### <span data-ttu-id="39481-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="39481-107">Path (Default)</span></span>

```
Format-Hex [-Path] <string[]> [<CommonParameters>]
```

### <span data-ttu-id="39481-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="39481-108">LiteralPath</span></span>

```
Format-Hex -LiteralPath <string[]> [<CommonParameters>]
```

### <span data-ttu-id="39481-109">Byinputobject</span><span class="sxs-lookup"><span data-stu-id="39481-109">ByInputObject</span></span>

```
Format-Hex -InputObject <Object> [-Encoding <string>] [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="39481-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="39481-110">DESCRIPTION</span></span>

<span data-ttu-id="39481-111">Mit dem- `Format-Hex` Cmdlet wird eine Datei oder eine andere Eingabe als hexadezimale Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39481-111">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="39481-112">Um den Offset eines Zeichens aus der Ausgabe zu ermitteln, fügen Sie die Nummer am äußersten linken Rand der Zeile der Zahl am oberen Rand der Spalte für dieses Zeichen hinzu.</span><span class="sxs-lookup"><span data-stu-id="39481-112">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="39481-113">`Format-Hex`Mithilfe des Cmdlets können Sie den Dateityp einer beschädigten Datei oder einer Datei ermitteln, die möglicherweise keine Dateinamenerweiterung hat.</span><span class="sxs-lookup"><span data-stu-id="39481-113">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="39481-114">Sie können dieses Cmdlet ausführen und dann die hexadezimale Ausgabe lesen, um Dateiinformationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="39481-114">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="39481-115">Wenn Sie `Format-Hex` für eine Datei verwenden, ignoriert das Cmdlet Zeilen neue Zeichen und gibt den gesamten Inhalt einer Datei in einer Zeichenfolge zurück, in der die Zeilen mit dem Zeilen Abschluss beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="39481-115">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="39481-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="39481-116">EXAMPLES</span></span>

### <span data-ttu-id="39481-117">Beispiel 1: erhalten der hexadezimalen Darstellung einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="39481-117">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="39481-118">Dieser Befehl gibt die hexadezimalen Werte einer Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="39481-118">This command returns the hexadecimal values of a string.</span></span>

```powershell
'Hello World' | Format-Hex
```

```Output
           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   48 65 6C 6C 6F 20 57 6F 72 6C 64                 Hello World
```

<span data-ttu-id="39481-119">Die Zeichenfolge **Hallo Welt** wird über die Pipeline an das `Format-Hex` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="39481-119">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="39481-120">Die hexadezimale Ausgabe von `Format-Hex` zeigt die Werte der einzelnen Zeichen in der Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="39481-120">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="39481-121">Beispiel 2: Suchen eines Dateityps aus der hexadezimalen Ausgabe</span><span class="sxs-lookup"><span data-stu-id="39481-121">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="39481-122">In diesem Beispiel wird die hexadezimale Ausgabe verwendet, um den Dateityp zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="39481-122">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="39481-123">Das-Cmdlet zeigt den vollständigen Pfad der Datei und die hexadezimalen Werte an.</span><span class="sxs-lookup"><span data-stu-id="39481-123">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="39481-124">Um den folgenden Befehl zu testen, erstellen Sie eine Kopie einer vorhandenen PDF-Datei auf dem lokalen Computer, und benennen Sie die kopierte Datei in " **file. T7F** " um.</span><span class="sxs-lookup"><span data-stu-id="39481-124">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to **File.t7f** .</span></span>

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

<span data-ttu-id="39481-125">Das `Format-Hex` Cmdlet verwendet den **path** -Parameter, um einen Dateinamen im aktuellen Verzeichnis anzugeben `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="39481-125">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, `File.t7f`.</span></span> <span data-ttu-id="39481-126">Die Dateierweiterung `.t7f` ist nicht üblich, aber die hexadezimale Ausgabe `%PDF` zeigt, dass es sich um eine PDF-Datei handelt.</span><span class="sxs-lookup"><span data-stu-id="39481-126">The file extension `.t7f` is uncommon, but the hexadecimal output `%PDF` shows that it is a PDF file.</span></span>

### <span data-ttu-id="39481-127">Beispiel 3: Anzeigen der unformatierten hexadezimalen Ausgabe</span><span class="sxs-lookup"><span data-stu-id="39481-127">Example 3: Display raw hexadecimal output</span></span>

<span data-ttu-id="39481-128">Standardmäßig `Format-Hex` verwendet OPTs für die Compact-Ausgabe numerischer Datentypen: Single-Byte-oder Double-Byte-Sequenzen werden verwendet, wenn der Wert klein genug ist.</span><span class="sxs-lookup"><span data-stu-id="39481-128">By default `Format-Hex` opts for compact output of numeric data types: single-byte or double-byte sequences are used if the value is small enough.</span></span> <span data-ttu-id="39481-129">Der **RAW** -Parameter deaktiviert dieses Verhalten.</span><span class="sxs-lookup"><span data-stu-id="39481-129">The **Raw** parameter deactivates this behavior.</span></span>

```
PS> 1,2,3,1000 | Format-Hex

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 02 03 E8 03                                   ...è.


PS> 1,2,3,1000 | Format-Hex -Raw

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 00 00 00 02 00 00 00 03 00 00 00 E8 03 00 00  ............è...
```

<span data-ttu-id="39481-130">Beachten Sie den Unterschied in der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="39481-130">Notice the difference in output.</span></span> <span data-ttu-id="39481-131">Der **RAW** -Parameter zeigt die Zahlen als 4-Byte-Werte an, true für Ihre **Int32** -Typen.</span><span class="sxs-lookup"><span data-stu-id="39481-131">The **Raw** parameter displays the numbers as 4-byte values, true to their **Int32** types.</span></span>

## <span data-ttu-id="39481-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="39481-132">PARAMETERS</span></span>

### <span data-ttu-id="39481-133">-Codierung</span><span class="sxs-lookup"><span data-stu-id="39481-133">-Encoding</span></span>

<span data-ttu-id="39481-134">Gibt die Codierung der Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="39481-134">Specifies the encoding of the output.</span></span> <span data-ttu-id="39481-135">Dies gilt nur für `[string]` Eingaben.</span><span class="sxs-lookup"><span data-stu-id="39481-135">This only applies to `[string]` input.</span></span> <span data-ttu-id="39481-136">Der-Parameter hat keine Auswirkung auf numerische Typen.</span><span class="sxs-lookup"><span data-stu-id="39481-136">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="39481-137">Der Standardwert ist `ASCII`.</span><span class="sxs-lookup"><span data-stu-id="39481-137">The default value is `ASCII`.</span></span>

<span data-ttu-id="39481-138">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="39481-138">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="39481-139">`Ascii` Verwendet den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="39481-139">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="39481-140">`BigEndianUnicode` Verwendet UTF-16 mit der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="39481-140">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="39481-141">`Unicode` Verwendet UTF-16 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="39481-141">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="39481-142">`UTF7` Verwendet UTF-7.</span><span class="sxs-lookup"><span data-stu-id="39481-142">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="39481-143">`UTF8` Verwendet UTF-8.</span><span class="sxs-lookup"><span data-stu-id="39481-143">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="39481-144">`UTF32` Verwendet UTF-32 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="39481-144">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="39481-145">Nicht-ASCII-Zeichen in der Eingabe werden als Literalzeichen ausgegeben, `?` was zu einem Verlust von Informationen führt.</span><span class="sxs-lookup"><span data-stu-id="39481-145">Non-ASCII characters in the input are output as literal `?` characters resulting in a loss of information.</span></span>

```yaml
Type: System.String
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: ASCII
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39481-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="39481-146">-InputObject</span></span>

<span data-ttu-id="39481-147">Wird für Pipeline Eingaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="39481-147">Used for pipeline input.</span></span> <span data-ttu-id="39481-148">Pipeline Eingaben unterstützen nur bestimmte skalare Typen und `[system.io.fileinfo]` Instanzen für die Weiterleitung von `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="39481-148">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="39481-149">Die folgenden skalaren Typen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="39481-149">The supported scalar types are:</span></span>

- `[string]`
- `[byte]`
- <span data-ttu-id="39481-150">`[int]`, `[int32]`</span><span class="sxs-lookup"><span data-stu-id="39481-150">`[int]`, `[int32]`</span></span>
- <span data-ttu-id="39481-151">`[long]`, `[int64]`</span><span class="sxs-lookup"><span data-stu-id="39481-151">`[long]`, `[int64]`</span></span>

```yaml
Type: System.Object
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="39481-152">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="39481-152">-LiteralPath</span></span>

<span data-ttu-id="39481-153">Gibt den kompletten Pfad zu einer Datei an.</span><span class="sxs-lookup"><span data-stu-id="39481-153">Specifies the complete path to a file.</span></span> <span data-ttu-id="39481-154">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="39481-154">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="39481-155">Dieser Parameter akzeptiert keine Platzhalter Zeichen.</span><span class="sxs-lookup"><span data-stu-id="39481-155">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="39481-156">Wenn Sie mehrere Pfade zu Dateien angeben möchten, trennen Sie die Pfade durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="39481-156">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="39481-157">Wenn der **literalpath** -Parameter Escapezeichen enthält, müssen Sie den Pfad in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="39481-157">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="39481-158">PowerShell interpretiert keine Zeichen in einer einzelnen Zeichenfolge in Anführungszeichen als Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="39481-158">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="39481-159">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="39481-159">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39481-160">-Path</span><span class="sxs-lookup"><span data-stu-id="39481-160">-Path</span></span>

<span data-ttu-id="39481-161">Gibt den Pfad zu den Dateien an.</span><span class="sxs-lookup"><span data-stu-id="39481-161">Specifies the path to files.</span></span> <span data-ttu-id="39481-162">Verwenden Sie einen Punkt ( `.` ), um den aktuellen Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="39481-162">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="39481-163">Das Platzhalter Zeichen ( `*` ) wird akzeptiert und kann verwendet werden, um alle Elemente in einem Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="39481-163">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="39481-164">Wenn der **path** -Parameter Escapezeichen enthält, müssen Sie den Pfad in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="39481-164">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="39481-165">Wenn Sie mehrere Pfade zu Dateien angeben möchten, trennen Sie die Pfade durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="39481-165">To specify multiple paths to files, separate the paths with a comma.</span></span>

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

### <span data-ttu-id="39481-166">-RAW</span><span class="sxs-lookup"><span data-stu-id="39481-166">-Raw</span></span>

<span data-ttu-id="39481-167">Standardmäßig `Format-Hex` verwendet OPTs für die Compact-Ausgabe numerischer Datentypen: Single-Byte-oder Double-Byte-Sequenzen werden verwendet, wenn der Wert klein genug ist.</span><span class="sxs-lookup"><span data-stu-id="39481-167">By default `Format-Hex` opts for compact output of numeric data types: single-byte or double-byte sequences are used if the value is small enough.</span></span> <span data-ttu-id="39481-168">Der **RAW** -Parameter deaktiviert dieses Verhalten.</span><span class="sxs-lookup"><span data-stu-id="39481-168">The **Raw** parameter deactivates this behavior.</span></span>

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

### <span data-ttu-id="39481-169">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="39481-169">CommonParameters</span></span>

<span data-ttu-id="39481-170">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="39481-170">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="39481-171">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="39481-171">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="39481-172">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="39481-172">INPUTS</span></span>

### <span data-ttu-id="39481-173">System.String</span><span class="sxs-lookup"><span data-stu-id="39481-173">System.String</span></span>

<span data-ttu-id="39481-174">Sie können eine Zeichenfolge über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="39481-174">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="39481-175">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="39481-175">OUTPUTS</span></span>

### <span data-ttu-id="39481-176">Microsoft. PowerShell. Commands. bytecollection</span><span class="sxs-lookup"><span data-stu-id="39481-176">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="39481-177">Dieses Cmdlet gibt eine **bytecollection** zurück.</span><span class="sxs-lookup"><span data-stu-id="39481-177">This cmdlet returns a **ByteCollection** .</span></span> <span data-ttu-id="39481-178">Dieses Objekt stellt eine Auflistung von Bytes dar.</span><span class="sxs-lookup"><span data-stu-id="39481-178">This object represents a collection of bytes.</span></span> <span data-ttu-id="39481-179">Sie enthält Methoden, mit denen die Auflistung von Bytes in eine Zeichenfolge konvertiert wird, die wie jede von zurückgegebene Ausgabezeile formatiert ist `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="39481-179">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="39481-180">Wenn Sie den **path** -oder **literalpath** -Parameter angeben, enthält das-Objekt auch den Pfad der Datei, die jedes Byte enthält.</span><span class="sxs-lookup"><span data-stu-id="39481-180">If you specify the **Path** or **LiteralPath** parameter, the object also contains the path of the file that contains each byte.</span></span>

## <span data-ttu-id="39481-181">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="39481-181">NOTES</span></span>

<span data-ttu-id="39481-182">In der äußersten rechten Spalte der Ausgabe wird versucht, die Bytes als Zeichen zu rendernen:</span><span class="sxs-lookup"><span data-stu-id="39481-182">The right-most column of output tries to render the bytes as characters:</span></span>

<span data-ttu-id="39481-183">Im Allgemeinen wird jedes Byte als Unicode-Codepunkt interpretiert, was Folgendes bedeutet:</span><span class="sxs-lookup"><span data-stu-id="39481-183">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="39481-184">Druckbare ASCII-Zeichen werden immer korrekt gerendert.</span><span class="sxs-lookup"><span data-stu-id="39481-184">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="39481-185">Mehr Byte-UTF-8-Zeichen werden nie korrekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="39481-185">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="39481-186">UTF-16-Zeichen werden nur dann ordnungsgemäß dargestellt, wenn Ihr höher gestelltem Byte ist `NUL` .</span><span class="sxs-lookup"><span data-stu-id="39481-186">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="39481-187">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="39481-187">RELATED LINKS</span></span>

[<span data-ttu-id="39481-188">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="39481-188">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="39481-189">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="39481-189">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="39481-190">Format-List</span><span class="sxs-lookup"><span data-stu-id="39481-190">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="39481-191">Format-Table</span><span class="sxs-lookup"><span data-stu-id="39481-191">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="39481-192">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="39481-192">Format-Wide</span></span>](Format-Wide.md)
