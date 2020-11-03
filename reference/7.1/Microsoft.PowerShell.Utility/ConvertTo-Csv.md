---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: e4cc40e7a9a5fdcd12b6a787607e4979ddbb3273
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215903"
---
# <span data-ttu-id="2bf1e-103">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="2bf1e-103">ConvertTo-Csv</span></span>

## <span data-ttu-id="2bf1e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2bf1e-104">SYNOPSIS</span></span>
<span data-ttu-id="2bf1e-105">Konvertiert .NET-Objekte in eine Reihe von CSV-Zeichen folgen (Zeichen getrennte Werte).</span><span class="sxs-lookup"><span data-stu-id="2bf1e-105">Converts .NET objects into a series of character-separated value (CSV) strings.</span></span>

## <span data-ttu-id="2bf1e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2bf1e-106">SYNTAX</span></span>

### <span data-ttu-id="2bf1e-107">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="2bf1e-107">Delimiter</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [<CommonParameters>]
```

### <span data-ttu-id="2bf1e-108">UseCulture</span><span class="sxs-lookup"><span data-stu-id="2bf1e-108">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [<CommonParameters>]
```

## <span data-ttu-id="2bf1e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2bf1e-109">DESCRIPTION</span></span>

<span data-ttu-id="2bf1e-110">Das- `ConvertTo-CSV` Cmdlet gibt eine Reihe von CSV-Zeichen folgen zurück, die die von Ihnen gesendeten Objekte darstellen.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-110">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="2bf1e-111">Sie können dann mit dem `ConvertFrom-Csv` Cmdlet Objekte aus den CSV-Zeichen folgen neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-111">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="2bf1e-112">Die aus CSV konvertierten Objekte sind Zeichen folgen Werte der ursprünglichen Objekte, die Eigenschaftswerte und keine Methoden enthalten.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-112">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="2bf1e-113">Sie können das `Export-Csv` Cmdlet verwenden, um Objekte in CSV-Zeichen folgen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-113">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="2bf1e-114">`Export-CSV` ähnelt `ConvertTo-CSV` , mit der Ausnahme, dass die CSV-Zeichen folgen in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-114">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="2bf1e-115">Das- `ConvertTo-CSV` Cmdlet verfügt über Parameter, um ein anderes Trennzeichen als ein Komma anzugeben, oder die aktuelle Kultur als Trennzeichen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-115">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="2bf1e-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2bf1e-116">EXAMPLES</span></span>

### <span data-ttu-id="2bf1e-117">Beispiel 1: Konvertieren eines Objekts in ein CSV</span><span class="sxs-lookup"><span data-stu-id="2bf1e-117">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="2bf1e-118">In diesem Beispiel wird ein **Prozess** Objekt in eine CSV-Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-118">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name pwsh | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"pwsh","8","950","2204001161216","100925440","59686912","67104", ...
```

<span data-ttu-id="2bf1e-119">Das `Get-Process` -Cmdlet ruft das **Process** -Objekt ab und verwendet den **Name** -Parameter, um den PowerShell-Prozess anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-119">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="2bf1e-120">Das Prozess Objekt wird in der Pipeline an das `ConvertTo-CSV` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-120">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="2bf1e-121">Das- `ConvertTo-CSV` Cmdlet konvertiert das Objekt in CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-121">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="2bf1e-122">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-122">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="2bf1e-123">Beispiel 2: Konvertieren eines DateTime-Objekts in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="2bf1e-123">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="2bf1e-124">In diesem Beispiel wird ein **DateTime** -Objekt in eine CSV-Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-124">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="2bf1e-125">`Get-Date`Mit dem-Cmdlet wird das **DateTime** -Objekt abgerufen und in der `$Date` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-125">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="2bf1e-126">Mit dem- `ConvertTo-Csv` Cmdlet wird das **DateTime** -Objekt in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-126">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="2bf1e-127">Der **Inputobject** -Parameter verwendet das **DateTime** -Objekt, das in der Variablen gespeichert ist `$Date` .</span><span class="sxs-lookup"><span data-stu-id="2bf1e-127">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="2bf1e-128">Mit dem **Delimiter** -Parameter wird ein Semikolon zum Trennen der Zeichen folgen Werte angegeben.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-128">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="2bf1e-129">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-129">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="2bf1e-130">Beispiel 3: Konvertieren des PowerShell-Ereignis Protokolls in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="2bf1e-130">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="2bf1e-131">In diesem Beispiel wird das Windows-Ereignisprotokoll für PowerShell in eine Reihe von CSV-Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-131">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'PowerShellCore/Operational' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error""4100","1",,"3","106","19","0","31716","PowerShellCore", ...
```

<span data-ttu-id="2bf1e-132">Das `Get-Culture` Cmdlet verwendet die genten Eigenschaften **TextInfo** und **ListSeparator** und zeigt das Standard Listen Trennzeichen der aktuellen Kultur an.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-132">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="2bf1e-133">`Get-WinEvent`Mit dem-Cmdlet werden die Ereignisprotokoll Objekte abgerufen, und der **logName** -Parameter wird verwendet, um den Namen der Protokolldatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-133">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="2bf1e-134">Die Ereignisprotokoll Objekte werden über die Pipeline an das `ConvertTo-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-134">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="2bf1e-135">Mit dem- `ConvertTo-Csv` Cmdlet werden die Ereignisprotokoll Objekte in eine Reihe von CSV-Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-135">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="2bf1e-136">Der **useculture** -Parameter verwendet das Standard Listen Trennzeichen der aktuellen Kultur als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-136">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="2bf1e-137">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-137">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="2bf1e-138">Beispiel 4: Konvertieren in CSV mit Anführungszeichen um zwei Spalten</span><span class="sxs-lookup"><span data-stu-id="2bf1e-138">Example 4: Convert to CSV with quotes around two columns</span></span>

<span data-ttu-id="2bf1e-139">In diesem Beispiel wird ein **DateTime** -Objekt in eine CSV-Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-139">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | ConvertTo-Csv -QuoteFields "DateTime","Date"
```

```Output
DisplayHint,"DateTime","Date",Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:27:34 AM","8/22/2019 12:00:00 AM",22,Thursday,234,11,Local,569,27,8,34,637020700545699784,11:27:34.5699784,2019
```

### <span data-ttu-id="2bf1e-140">Beispiel 4: Konvertieren in CSV nur bei Bedarf mit Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="2bf1e-140">Example 4: Convert to CSV with quotes only when needed</span></span>

<span data-ttu-id="2bf1e-141">In diesem Beispiel wird ein **DateTime** -Objekt in eine CSV-Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-141">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | ConvertTo-Csv -UseQuotes AsNeeded
```

```Output
DisplayHint,DateTime,Date,Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:31:00 AM",8/22/2019 12:00:00 AM,22,Thursday,234,11,Local,713,31,8,0,637020702607132640,11:31:00.7132640,2019
```

## <span data-ttu-id="2bf1e-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2bf1e-142">PARAMETERS</span></span>

### <span data-ttu-id="2bf1e-143">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="2bf1e-143">-Delimiter</span></span>

<span data-ttu-id="2bf1e-144">Gibt das Trennzeichen zum Trennen der Eigenschaftswerte in CSV-Zeichen folgen an.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-144">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="2bf1e-145">Der Standardwert ist ein Komma ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="2bf1e-145">The default is a comma (`,`).</span></span> <span data-ttu-id="2bf1e-146">Geben Sie ein Zeichen ein, z. b. einen Doppelpunkt ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="2bf1e-146">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="2bf1e-147">Um ein Semikolon ( `;` ) anzugeben, schließen Sie es in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-147">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2bf1e-148">-Includecotypeinformation</span><span class="sxs-lookup"><span data-stu-id="2bf1e-148">-IncludeTypeInformation</span></span>

<span data-ttu-id="2bf1e-149">Wenn dieser Parameter verwendet wird, enthält die erste Zeile der Ausgabe **#Type** , gefolgt vom voll qualifizierten Namen des Objekt Typs.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-149">When this parameter is used the first line of the output contains **#TYPE** followed by the fully qualified name of the object type.</span></span> <span data-ttu-id="2bf1e-150">#Type z. b. **System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-150">For example, **#TYPE System.Diagnostics.Process**.</span></span>

<span data-ttu-id="2bf1e-151">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-151">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ITI

Required: False
Position: Named
Default value: #TYPE <Object>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2bf1e-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2bf1e-152">-InputObject</span></span>

<span data-ttu-id="2bf1e-153">Gibt die Objekte an, die in CSV-Zeichen folgen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-153">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="2bf1e-154">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-154">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="2bf1e-155">Sie können Objekte auch über die Pipeline an übergeben `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="2bf1e-155">You can also pipe objects to `ConvertTo-CSV`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2bf1e-156">-Notypeinformation</span><span class="sxs-lookup"><span data-stu-id="2bf1e-156">-NoTypeInformation</span></span>

<span data-ttu-id="2bf1e-157">Entfernt den **#Type** Informations Header aus der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-157">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="2bf1e-158">Dieser Parameter wurde in PowerShell 6,0 zum Standard und ist aus Gründen der Abwärtskompatibilität eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-158">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NTI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2bf1e-159">-Useculture</span><span class="sxs-lookup"><span data-stu-id="2bf1e-159">-UseCulture</span></span>

<span data-ttu-id="2bf1e-160">Verwendet das Listen Trennzeichen für die aktuelle Kultur als Element Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-160">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="2bf1e-161">Um das Listen Trennzeichen für eine Kultur zu suchen, verwenden Sie den folgenden Befehl: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="2bf1e-161">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2bf1e-162">-Quotefields</span><span class="sxs-lookup"><span data-stu-id="2bf1e-162">-QuoteFields</span></span>

<span data-ttu-id="2bf1e-163">Gibt die Namen der Spalten an, die in Anführungszeichen eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-163">Specifies the names of the columns that should be quoted.</span></span> <span data-ttu-id="2bf1e-164">Wenn dieser Parameter verwendet wird, werden nur die angegebenen Spalten in Anführungszeichen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-164">When this parameter is used only the specified columns are quoted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: QF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2bf1e-165">-Usequotes</span><span class="sxs-lookup"><span data-stu-id="2bf1e-165">-UseQuotes</span></span>

<span data-ttu-id="2bf1e-166">Gibt an, wann Anführungszeichen in den CSV-Dateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-166">Specifies when quotes are used in the CSV files.</span></span> <span data-ttu-id="2bf1e-167">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="2bf1e-167">Possible values are:</span></span>

- <span data-ttu-id="2bf1e-168">Niemals etwas angeben</span><span class="sxs-lookup"><span data-stu-id="2bf1e-168">Never - don't quote anything</span></span>
- <span data-ttu-id="2bf1e-169">Alles immer angeben (Standardverhalten)</span><span class="sxs-lookup"><span data-stu-id="2bf1e-169">Always - quote everything (default behavior)</span></span>
- <span data-ttu-id="2bf1e-170">Asbedarf-nur Anführungszeichen Felder, die ein Trennzeichen enthalten</span><span class="sxs-lookup"><span data-stu-id="2bf1e-170">AsNeeded - only quote fields that contain a delimiter character</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.BaseCsvWritingCommand+QuoteKind
Parameter Sets: (All)
Aliases: UQ

Required: False
Position: Named
Default value: Always
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2bf1e-171">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2bf1e-171">CommonParameters</span></span>

<span data-ttu-id="2bf1e-172">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2bf1e-173">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2bf1e-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2bf1e-174">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2bf1e-174">INPUTS</span></span>

### <span data-ttu-id="2bf1e-175">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="2bf1e-175">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="2bf1e-176">Sie können jedes beliebige Objekt über die Pipeline übergeben, das über einen Extended Type System (ETS)-Adapter verfügt `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="2bf1e-176">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="2bf1e-177">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2bf1e-177">OUTPUTS</span></span>

### <span data-ttu-id="2bf1e-178">System.String</span><span class="sxs-lookup"><span data-stu-id="2bf1e-178">System.String</span></span>

<span data-ttu-id="2bf1e-179">Die CSV-Ausgabe wird als Auflistung von Zeichenfolgen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-179">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="2bf1e-180">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2bf1e-180">NOTES</span></span>

<span data-ttu-id="2bf1e-181">Im CSV-Format wird jedes Objekt durch eine durch Trennzeichen getrennte Liste seiner Eigenschaftswerte dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-181">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="2bf1e-182">Die Eigenschaftswerte werden mithilfe der Methode "$ **String ()** " des Objekts in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-182">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="2bf1e-183">Die Zeichen folgen werden durch den Namen des Eigenschafts Werts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-183">The strings are represented by the property value name.</span></span> <span data-ttu-id="2bf1e-184">`ConvertTo-CSV` exportiert nicht die Methoden des Objekts.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-184">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="2bf1e-185">Die CSV-Zeichen folgen werden wie folgt ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="2bf1e-185">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="2bf1e-186">Wenn **includetypeinformation** verwendet wird, besteht die erste Zeichenfolge aus **#Type** gefolgt vom voll qualifizierten Namen des Objekt Typs.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-186">If **IncludeTypeInformation** is used, the first string consists of **#TYPE** followed by the object type's fully qualified name.</span></span> <span data-ttu-id="2bf1e-187">#Type z. b. **System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-187">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="2bf1e-188">Wenn **include TypeInformation** nicht verwendet wird, enthält die erste Zeichenfolge die Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-188">If **IncludeTypeInformation** is not used the first string includes the column headers.</span></span> <span data-ttu-id="2bf1e-189">Die Header enthalten die Eigenschaftsnamen des ersten Objekts als durch Trennzeichen getrennte Liste.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-189">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="2bf1e-190">Die übrigen Zeichen folgen enthalten durch Trennzeichen getrennte Listen der Eigenschaftswerte jedes Objekts.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-190">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="2bf1e-191">Ab PowerShell 6,0 ist das Standardverhalten von `ConvertTo-CSV` , wenn die **#Type** Informationen in das CSV nicht eingeschlossen werden und **notypeinformation** impliziert ist.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-191">Beginning with PowerShell 6.0 the default behavior of `ConvertTo-CSV` is to not include the **#TYPE** information in the CSV and **NoTypeInformation** is implied.</span></span> <span data-ttu-id="2bf1e-192">**Includetypeinformation** kann verwendet werden, um die **#Type** Informationen einzuschließen und das Standardverhalten von `ConvertTo-CSV` vor PowerShell 6,0 zu emulieren.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-192">**IncludeTypeInformation** can be used to include the **#TYPE** information and emulate the default behavior of `ConvertTo-CSV` prior to PowerShell 6.0.</span></span>

<span data-ttu-id="2bf1e-193">Wenn Sie mehrere Objekte an senden `ConvertTo-CSV` , `ConvertTo-CSV` ordnet die Zeichen folgen auf der Grundlage der Eigenschaften des ersten von Ihnen gesendeten Objekts zu.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-193">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="2bf1e-194">Wenn die übrigen Objekte nicht über eine der angegebenen Eigenschaften verfügen, ist der Eigenschafts Wert dieses Objekts NULL, was durch zwei aufeinander folgende Kommas dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-194">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="2bf1e-195">Wenn die übrigen Objekte zusätzliche Eigenschaften aufweisen, werden diese Eigenschaftswerte ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2bf1e-195">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="2bf1e-196">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2bf1e-196">RELATED LINKS</span></span>

[<span data-ttu-id="2bf1e-197">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="2bf1e-197">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="2bf1e-198">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="2bf1e-198">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="2bf1e-199">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="2bf1e-199">Import-Csv</span></span>](Import-Csv.md)

