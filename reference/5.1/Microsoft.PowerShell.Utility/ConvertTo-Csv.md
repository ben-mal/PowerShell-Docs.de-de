---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: 7d399661e4514c0a39ad00601d554c41c2897ff9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214135"
---
# <span data-ttu-id="a05e7-103">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="a05e7-103">ConvertTo-Csv</span></span>

## <span data-ttu-id="a05e7-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a05e7-104">SYNOPSIS</span></span>
<span data-ttu-id="a05e7-105">Konvertiert .NET-Objekte in eine Reihe von CSV-Zeichen folgen (Comma-Separated Value, Komma getrennte Werte).</span><span class="sxs-lookup"><span data-stu-id="a05e7-105">Converts .NET objects into a series of comma-separated value (CSV) strings.</span></span>

## <span data-ttu-id="a05e7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a05e7-106">SYNTAX</span></span>

### <span data-ttu-id="a05e7-107">Trennzeichen (Standard)</span><span class="sxs-lookup"><span data-stu-id="a05e7-107">Delimiter (Default)</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [[-Delimiter] <char>] [-NoTypeInformation]
 [<CommonParameters>]
```

### <span data-ttu-id="a05e7-108">UseCulture</span><span class="sxs-lookup"><span data-stu-id="a05e7-108">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [-UseCulture] [-NoTypeInformation] [<CommonParameters>]
```

## <span data-ttu-id="a05e7-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a05e7-109">DESCRIPTION</span></span>

<span data-ttu-id="a05e7-110">Das- `ConvertTo-CSV` Cmdlet gibt eine Reihe von CSV-Zeichen folgen zurück, die die von Ihnen gesendeten Objekte darstellen.</span><span class="sxs-lookup"><span data-stu-id="a05e7-110">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="a05e7-111">Sie können dann mit dem `ConvertFrom-Csv` Cmdlet Objekte aus den CSV-Zeichen folgen neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a05e7-111">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="a05e7-112">Die aus CSV konvertierten Objekte sind Zeichen folgen Werte der ursprünglichen Objekte, die Eigenschaftswerte und keine Methoden enthalten.</span><span class="sxs-lookup"><span data-stu-id="a05e7-112">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="a05e7-113">Sie können das `Export-Csv` Cmdlet verwenden, um Objekte in CSV-Zeichen folgen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="a05e7-113">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="a05e7-114">`Export-CSV` ähnelt `ConvertTo-CSV` , mit der Ausnahme, dass die CSV-Zeichen folgen in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="a05e7-114">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="a05e7-115">Das- `ConvertTo-CSV` Cmdlet verfügt über Parameter, um ein anderes Trennzeichen als ein Komma anzugeben, oder die aktuelle Kultur als Trennzeichen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a05e7-115">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="a05e7-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a05e7-116">EXAMPLES</span></span>

### <span data-ttu-id="a05e7-117">Beispiel 1: Konvertieren eines Objekts in ein CSV</span><span class="sxs-lookup"><span data-stu-id="a05e7-117">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="a05e7-118">In diesem Beispiel wird ein **Prozess** Objekt in eine CSV-Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a05e7-118">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name 'PowerShell' | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"powershell","11","691","2204036739072","175943680","132665344","33312", ...
```

<span data-ttu-id="a05e7-119">Das `Get-Process` -Cmdlet ruft das **Process** -Objekt ab und verwendet den **Name** -Parameter, um den PowerShell-Prozess anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a05e7-119">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="a05e7-120">Das Prozess Objekt wird in der Pipeline an das `ConvertTo-CSV` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="a05e7-120">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="a05e7-121">Das- `ConvertTo-CSV` Cmdlet konvertiert das Objekt in CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="a05e7-121">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="a05e7-122">Mit dem **notypeinformation** -Parameter wird der **#Type** Informations Header aus der CSV-Ausgabe entfernt.</span><span class="sxs-lookup"><span data-stu-id="a05e7-122">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="a05e7-123">Beispiel 2: Konvertieren eines DateTime-Objekts in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="a05e7-123">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="a05e7-124">In diesem Beispiel wird ein **DateTime** -Objekt in eine CSV-Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a05e7-124">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="a05e7-125">`Get-Date`Mit dem-Cmdlet wird das **DateTime** -Objekt abgerufen und in der `$Date` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a05e7-125">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="a05e7-126">Mit dem- `ConvertTo-Csv` Cmdlet wird das **DateTime** -Objekt in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a05e7-126">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="a05e7-127">Der **Inputobject** -Parameter verwendet das **DateTime** -Objekt, das in der Variablen gespeichert ist `$Date` .</span><span class="sxs-lookup"><span data-stu-id="a05e7-127">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="a05e7-128">Mit dem **Delimiter** -Parameter wird ein Semikolon zum Trennen der Zeichen folgen Werte angegeben.</span><span class="sxs-lookup"><span data-stu-id="a05e7-128">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="a05e7-129">Mit dem **notypeinformation** -Parameter wird der **#Type** Informations Header aus der CSV-Ausgabe entfernt.</span><span class="sxs-lookup"><span data-stu-id="a05e7-129">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="a05e7-130">Beispiel 3: Konvertieren des PowerShell-Ereignis Protokolls in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="a05e7-130">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="a05e7-131">In diesem Beispiel wird das Windows-Ereignisprotokoll für PowerShell in eine Reihe von CSV-Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a05e7-131">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'Windows PowerShell' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error","403",,"0","4","4",,"36028797018963968","46891","PowerShell", ...
```

<span data-ttu-id="a05e7-132">Das `Get-Culture` Cmdlet verwendet die genten Eigenschaften **TextInfo** und **ListSeparator** und zeigt das Standard Listen Trennzeichen der aktuellen Kultur an.</span><span class="sxs-lookup"><span data-stu-id="a05e7-132">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="a05e7-133">`Get-WinEvent`Mit dem-Cmdlet werden die Ereignisprotokoll Objekte abgerufen, und der **logName** -Parameter wird verwendet, um den Namen der Protokolldatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a05e7-133">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="a05e7-134">Die Ereignisprotokoll Objekte werden über die Pipeline an das `ConvertTo-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="a05e7-134">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="a05e7-135">Mit dem- `ConvertTo-Csv` Cmdlet werden die Ereignisprotokoll Objekte in eine Reihe von CSV-Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a05e7-135">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="a05e7-136">Der **useculture** -Parameter verwendet das Standard Listen Trennzeichen der aktuellen Kultur als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="a05e7-136">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="a05e7-137">Mit dem **notypeinformation** -Parameter wird der **#Type** Informations Header aus der CSV-Ausgabe entfernt.</span><span class="sxs-lookup"><span data-stu-id="a05e7-137">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

## <span data-ttu-id="a05e7-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a05e7-138">PARAMETERS</span></span>

### <span data-ttu-id="a05e7-139">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="a05e7-139">-Delimiter</span></span>

<span data-ttu-id="a05e7-140">Gibt das Trennzeichen zum Trennen der Eigenschaftswerte in CSV-Zeichen folgen an.</span><span class="sxs-lookup"><span data-stu-id="a05e7-140">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="a05e7-141">Der Standardwert ist ein Komma ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="a05e7-141">The default is a comma (`,`).</span></span> <span data-ttu-id="a05e7-142">Geben Sie ein Zeichen ein, z. b. einen Doppelpunkt ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="a05e7-142">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="a05e7-143">Um ein Semikolon ( `;` ) anzugeben, schließen Sie es in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="a05e7-143">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

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

### <span data-ttu-id="a05e7-144">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a05e7-144">-InputObject</span></span>

<span data-ttu-id="a05e7-145">Gibt die Objekte an, die in CSV-Zeichen folgen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="a05e7-145">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="a05e7-146">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a05e7-146">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="a05e7-147">Sie können Objekte auch über die Pipeline an übergeben `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="a05e7-147">You can also pipe objects to `ConvertTo-CSV`.</span></span>

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

### <span data-ttu-id="a05e7-148">-Notypeinformation</span><span class="sxs-lookup"><span data-stu-id="a05e7-148">-NoTypeInformation</span></span>

<span data-ttu-id="a05e7-149">Entfernt den **#Type** Informations Header aus der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="a05e7-149">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="a05e7-150">Dieser Parameter wurde in PowerShell 6,0 zum Standard und ist aus Gründen der Abwärtskompatibilität eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a05e7-150">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="a05e7-151">-Useculture</span><span class="sxs-lookup"><span data-stu-id="a05e7-151">-UseCulture</span></span>

<span data-ttu-id="a05e7-152">Verwendet das Listen Trennzeichen für die aktuelle Kultur als Element Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="a05e7-152">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="a05e7-153">Um das Listen Trennzeichen für eine Kultur zu suchen, verwenden Sie den folgenden Befehl: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="a05e7-153">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="a05e7-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a05e7-154">CommonParameters</span></span>

<span data-ttu-id="a05e7-155">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a05e7-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a05e7-156">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a05e7-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a05e7-157">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a05e7-157">INPUTS</span></span>

### <span data-ttu-id="a05e7-158">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="a05e7-158">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="a05e7-159">Sie können jedes beliebige Objekt über die Pipeline übergeben, das über einen Extended Type System (ETS)-Adapter verfügt `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="a05e7-159">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="a05e7-160">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a05e7-160">OUTPUTS</span></span>

### <span data-ttu-id="a05e7-161">System.String</span><span class="sxs-lookup"><span data-stu-id="a05e7-161">System.String</span></span>

<span data-ttu-id="a05e7-162">Die CSV-Ausgabe wird als Auflistung von Zeichenfolgen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a05e7-162">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="a05e7-163">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a05e7-163">NOTES</span></span>

<span data-ttu-id="a05e7-164">Im CSV-Format wird jedes Objekt durch eine durch Trennzeichen getrennte Liste seiner Eigenschaftswerte dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a05e7-164">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="a05e7-165">Die Eigenschaftswerte werden mithilfe der Methode "$ **String ()** " des Objekts in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a05e7-165">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="a05e7-166">Die Zeichen folgen werden durch den Namen des Eigenschafts Werts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a05e7-166">The strings are represented by the property value name.</span></span> <span data-ttu-id="a05e7-167">`ConvertTo-CSV` exportiert nicht die Methoden des Objekts.</span><span class="sxs-lookup"><span data-stu-id="a05e7-167">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="a05e7-168">Die CSV-Zeichen folgen werden wie folgt ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="a05e7-168">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="a05e7-169">Standardmäßig enthält die erste Zeichenfolge den **#Type** Informations Header, gefolgt vom voll qualifizierten Namen des Objekt Typs.</span><span class="sxs-lookup"><span data-stu-id="a05e7-169">By default the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span> <span data-ttu-id="a05e7-170">#Type z. b. **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="a05e7-170">For example, **#TYPE System.Diagnostics.Process** .</span></span>
- <span data-ttu-id="a05e7-171">Wenn **notypeinformation** verwendet wird, enthält die erste Zeichenfolge die Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="a05e7-171">If **NoTypeInformation** is used the first string includes the column headers.</span></span> <span data-ttu-id="a05e7-172">Die Header enthalten die Eigenschaftsnamen des ersten Objekts als durch Trennzeichen getrennte Liste.</span><span class="sxs-lookup"><span data-stu-id="a05e7-172">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="a05e7-173">Die übrigen Zeichen folgen enthalten durch Trennzeichen getrennte Listen der Eigenschaftswerte jedes Objekts.</span><span class="sxs-lookup"><span data-stu-id="a05e7-173">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="a05e7-174">Wenn Sie mehrere Objekte an senden `ConvertTo-CSV` , `ConvertTo-CSV` ordnet die Zeichen folgen auf der Grundlage der Eigenschaften des ersten von Ihnen gesendeten Objekts zu.</span><span class="sxs-lookup"><span data-stu-id="a05e7-174">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="a05e7-175">Wenn die übrigen Objekte nicht über eine der angegebenen Eigenschaften verfügen, ist der Eigenschafts Wert dieses Objekts NULL, was durch zwei aufeinander folgende Kommas dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a05e7-175">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="a05e7-176">Wenn die übrigen Objekte zusätzliche Eigenschaften aufweisen, werden diese Eigenschaftswerte ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a05e7-176">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="a05e7-177">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a05e7-177">RELATED LINKS</span></span>

[<span data-ttu-id="a05e7-178">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="a05e7-178">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="a05e7-179">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="a05e7-179">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="a05e7-180">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="a05e7-180">Import-Csv</span></span>](Import-Csv.md)
