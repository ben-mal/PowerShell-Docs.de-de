---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: 5de6a3bd28b850d3fc1632e26998986f302b78f8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216828"
---
# <span data-ttu-id="7e7dc-103">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="7e7dc-103">ConvertTo-Csv</span></span>

## <span data-ttu-id="7e7dc-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7e7dc-104">SYNOPSIS</span></span>
<span data-ttu-id="7e7dc-105">Konvertiert .NET-Objekte in eine Reihe von CSV-Zeichen folgen (Zeichen getrennte Werte).</span><span class="sxs-lookup"><span data-stu-id="7e7dc-105">Converts .NET objects into a series of character-separated value (CSV) strings.</span></span>

## <span data-ttu-id="7e7dc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7e7dc-106">SYNTAX</span></span>

### <span data-ttu-id="7e7dc-107">Delimiterpath (Standard)</span><span class="sxs-lookup"><span data-stu-id="7e7dc-107">DelimiterPath (Default)</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [-IncludeTypeInformation] [-NoTypeInformation]
 [<CommonParameters>]
```

### <span data-ttu-id="7e7dc-108">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="7e7dc-108">Delimiter</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [<CommonParameters>]
```

### <span data-ttu-id="7e7dc-109">UseCulture</span><span class="sxs-lookup"><span data-stu-id="7e7dc-109">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [<CommonParameters>]
```

## <span data-ttu-id="7e7dc-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7e7dc-110">DESCRIPTION</span></span>

<span data-ttu-id="7e7dc-111">Das- `ConvertTo-CSV` Cmdlet gibt eine Reihe von CSV-Zeichen folgen zurück, die die von Ihnen gesendeten Objekte darstellen.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-111">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="7e7dc-112">Sie können dann mit dem `ConvertFrom-Csv` Cmdlet Objekte aus den CSV-Zeichen folgen neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-112">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="7e7dc-113">Die aus CSV konvertierten Objekte sind Zeichen folgen Werte der ursprünglichen Objekte, die Eigenschaftswerte und keine Methoden enthalten.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-113">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="7e7dc-114">Sie können das `Export-Csv` Cmdlet verwenden, um Objekte in CSV-Zeichen folgen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-114">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="7e7dc-115">`Export-CSV` ähnelt `ConvertTo-CSV` , mit der Ausnahme, dass die CSV-Zeichen folgen in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-115">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="7e7dc-116">Das- `ConvertTo-CSV` Cmdlet verfügt über Parameter, um ein anderes Trennzeichen als ein Komma anzugeben, oder die aktuelle Kultur als Trennzeichen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-116">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="7e7dc-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7e7dc-117">EXAMPLES</span></span>

### <span data-ttu-id="7e7dc-118">Beispiel 1: Konvertieren eines Objekts in ein CSV</span><span class="sxs-lookup"><span data-stu-id="7e7dc-118">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="7e7dc-119">In diesem Beispiel wird ein **Prozess** Objekt in eine CSV-Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-119">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name pwsh | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"pwsh","8","950","2204001161216","100925440","59686912","67104", ...
```

<span data-ttu-id="7e7dc-120">Das `Get-Process` -Cmdlet ruft das **Process** -Objekt ab und verwendet den **Name** -Parameter, um den PowerShell-Prozess anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-120">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="7e7dc-121">Das Prozess Objekt wird in der Pipeline an das `ConvertTo-CSV` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-121">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="7e7dc-122">Das- `ConvertTo-CSV` Cmdlet konvertiert das Objekt in CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-122">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="7e7dc-123">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-123">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="7e7dc-124">Beispiel 2: Konvertieren eines DateTime-Objekts in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="7e7dc-124">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="7e7dc-125">In diesem Beispiel wird ein **DateTime** -Objekt in eine CSV-Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-125">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="7e7dc-126">`Get-Date`Mit dem-Cmdlet wird das **DateTime** -Objekt abgerufen und in der `$Date` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-126">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="7e7dc-127">Mit dem- `ConvertTo-Csv` Cmdlet wird das **DateTime** -Objekt in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-127">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="7e7dc-128">Der **Inputobject** -Parameter verwendet das **DateTime** -Objekt, das in der Variablen gespeichert ist `$Date` .</span><span class="sxs-lookup"><span data-stu-id="7e7dc-128">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="7e7dc-129">Mit dem **Delimiter** -Parameter wird ein Semikolon zum Trennen der Zeichen folgen Werte angegeben.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-129">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="7e7dc-130">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-130">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="7e7dc-131">Beispiel 3: Konvertieren des PowerShell-Ereignis Protokolls in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="7e7dc-131">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="7e7dc-132">In diesem Beispiel wird das Windows-Ereignisprotokoll für PowerShell in eine Reihe von CSV-Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-132">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'PowerShellCore/Operational' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error""4100","1",,"3","106","19","0","31716","PowerShellCore", ...
```

<span data-ttu-id="7e7dc-133">Das `Get-Culture` Cmdlet verwendet die genten Eigenschaften **TextInfo** und **ListSeparator** und zeigt das Standard Listen Trennzeichen der aktuellen Kultur an.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-133">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="7e7dc-134">`Get-WinEvent`Mit dem-Cmdlet werden die Ereignisprotokoll Objekte abgerufen, und der **logName** -Parameter wird verwendet, um den Namen der Protokolldatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-134">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="7e7dc-135">Die Ereignisprotokoll Objekte werden über die Pipeline an das `ConvertTo-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-135">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="7e7dc-136">Mit dem- `ConvertTo-Csv` Cmdlet werden die Ereignisprotokoll Objekte in eine Reihe von CSV-Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-136">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="7e7dc-137">Der **useculture** -Parameter verwendet das Standard Listen Trennzeichen der aktuellen Kultur als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-137">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="7e7dc-138">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-138">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

## <span data-ttu-id="7e7dc-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7e7dc-139">PARAMETERS</span></span>

### <span data-ttu-id="7e7dc-140">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="7e7dc-140">-Delimiter</span></span>

<span data-ttu-id="7e7dc-141">Gibt das Trennzeichen zum Trennen der Eigenschaftswerte in CSV-Zeichen folgen an.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-141">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="7e7dc-142">Der Standardwert ist ein Komma ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="7e7dc-142">The default is a comma (`,`).</span></span> <span data-ttu-id="7e7dc-143">Geben Sie ein Zeichen ein, z. b. einen Doppelpunkt ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="7e7dc-143">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="7e7dc-144">Um ein Semikolon ( `;` ) anzugeben, schließen Sie es in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-144">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

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

### <span data-ttu-id="7e7dc-145">-Includecotypeinformation</span><span class="sxs-lookup"><span data-stu-id="7e7dc-145">-IncludeTypeInformation</span></span>

<span data-ttu-id="7e7dc-146">Wenn dieser Parameter verwendet wird, enthält die erste Zeile der Ausgabe **#Type** , gefolgt vom voll qualifizierten Namen des Objekt Typs.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-146">When this parameter is used the first line of the output contains **#TYPE** followed by the fully qualified name of the object type.</span></span> <span data-ttu-id="7e7dc-147">#Type z. b. **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="7e7dc-147">For example, **#TYPE System.Diagnostics.Process** .</span></span>

<span data-ttu-id="7e7dc-148">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-148">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="7e7dc-149">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7e7dc-149">-InputObject</span></span>

<span data-ttu-id="7e7dc-150">Gibt die Objekte an, die in CSV-Zeichen folgen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-150">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="7e7dc-151">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-151">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="7e7dc-152">Sie können Objekte auch über die Pipeline an übergeben `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="7e7dc-152">You can also pipe objects to `ConvertTo-CSV`.</span></span>

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

### <span data-ttu-id="7e7dc-153">-Notypeinformation</span><span class="sxs-lookup"><span data-stu-id="7e7dc-153">-NoTypeInformation</span></span>

<span data-ttu-id="7e7dc-154">Entfernt den **#Type** Informations Header aus der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-154">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="7e7dc-155">Dieser Parameter wurde in PowerShell 6,0 zum Standard und ist aus Gründen der Abwärtskompatibilität eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-155">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="7e7dc-156">-Useculture</span><span class="sxs-lookup"><span data-stu-id="7e7dc-156">-UseCulture</span></span>

<span data-ttu-id="7e7dc-157">Verwendet das Listen Trennzeichen für die aktuelle Kultur als Element Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-157">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="7e7dc-158">Um das Listen Trennzeichen für eine Kultur zu suchen, verwenden Sie den folgenden Befehl: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="7e7dc-158">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="7e7dc-159">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7e7dc-159">CommonParameters</span></span>

<span data-ttu-id="7e7dc-160">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-160">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7e7dc-161">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7e7dc-161">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7e7dc-162">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7e7dc-162">INPUTS</span></span>

### <span data-ttu-id="7e7dc-163">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="7e7dc-163">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="7e7dc-164">Sie können jedes beliebige Objekt über die Pipeline übergeben, das über einen Extended Type System (ETS)-Adapter verfügt `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="7e7dc-164">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="7e7dc-165">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7e7dc-165">OUTPUTS</span></span>

### <span data-ttu-id="7e7dc-166">System.String</span><span class="sxs-lookup"><span data-stu-id="7e7dc-166">System.String</span></span>

<span data-ttu-id="7e7dc-167">Die CSV-Ausgabe wird als Auflistung von Zeichenfolgen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-167">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="7e7dc-168">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7e7dc-168">NOTES</span></span>

<span data-ttu-id="7e7dc-169">Im CSV-Format wird jedes Objekt durch eine durch Trennzeichen getrennte Liste seiner Eigenschaftswerte dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-169">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="7e7dc-170">Die Eigenschaftswerte werden mithilfe der Methode "$ **String ()** " des Objekts in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-170">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="7e7dc-171">Die Zeichen folgen werden durch den Namen des Eigenschafts Werts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-171">The strings are represented by the property value name.</span></span> <span data-ttu-id="7e7dc-172">`ConvertTo-CSV` exportiert nicht die Methoden des Objekts.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-172">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="7e7dc-173">Die CSV-Zeichen folgen werden wie folgt ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="7e7dc-173">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="7e7dc-174">Wenn **includetypeinformation** verwendet wird, besteht die erste Zeichenfolge aus **#Type** gefolgt vom voll qualifizierten Namen des Objekt Typs.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-174">If **IncludeTypeInformation** is used, the first string consists of **#TYPE** followed by the object type's fully qualified name.</span></span> <span data-ttu-id="7e7dc-175">#Type z. b. **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="7e7dc-175">For example, **#TYPE System.Diagnostics.Process** .</span></span>
- <span data-ttu-id="7e7dc-176">Wenn **include TypeInformation** nicht verwendet wird, enthält die erste Zeichenfolge die Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-176">If **IncludeTypeInformation** is not used the first string includes the column headers.</span></span> <span data-ttu-id="7e7dc-177">Die Header enthalten die Eigenschaftsnamen des ersten Objekts als durch Trennzeichen getrennte Liste.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-177">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="7e7dc-178">Die übrigen Zeichen folgen enthalten durch Trennzeichen getrennte Listen der Eigenschaftswerte jedes Objekts.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-178">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="7e7dc-179">Ab PowerShell 6,0 ist das Standardverhalten von `ConvertTo-CSV` , wenn die **#Type** Informationen in das CSV nicht eingeschlossen werden und **notypeinformation** impliziert ist.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-179">Beginning with PowerShell 6.0 the default behavior of `ConvertTo-CSV` is to not include the **#TYPE** information in the CSV and **NoTypeInformation** is implied.</span></span> <span data-ttu-id="7e7dc-180">**Includetypeinformation** kann verwendet werden, um die **#Type** Informationen einzuschließen und das Standardverhalten von `ConvertTo-CSV` vor PowerShell 6,0 zu emulieren.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-180">**IncludeTypeInformation** can be used to include the **#TYPE** information and emulate the default behavior of `ConvertTo-CSV` prior to PowerShell 6.0.</span></span>

<span data-ttu-id="7e7dc-181">Wenn Sie mehrere Objekte an senden `ConvertTo-CSV` , `ConvertTo-CSV` ordnet die Zeichen folgen auf der Grundlage der Eigenschaften des ersten von Ihnen gesendeten Objekts zu.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-181">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="7e7dc-182">Wenn die übrigen Objekte nicht über eine der angegebenen Eigenschaften verfügen, ist der Eigenschafts Wert dieses Objekts NULL, was durch zwei aufeinander folgende Kommas dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-182">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="7e7dc-183">Wenn die übrigen Objekte zusätzliche Eigenschaften aufweisen, werden diese Eigenschaftswerte ignoriert.</span><span class="sxs-lookup"><span data-stu-id="7e7dc-183">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="7e7dc-184">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7e7dc-184">RELATED LINKS</span></span>

[<span data-ttu-id="7e7dc-185">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="7e7dc-185">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="7e7dc-186">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="7e7dc-186">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="7e7dc-187">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="7e7dc-187">Import-Csv</span></span>](Import-Csv.md)
