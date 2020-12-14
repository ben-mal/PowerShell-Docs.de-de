---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: be590368539f396f0aac694e9565674393543f2c
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913201"
---
# <span data-ttu-id="aeb3f-102">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="aeb3f-102">ConvertTo-Csv</span></span>

## <span data-ttu-id="aeb3f-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="aeb3f-103">SYNOPSIS</span></span>
<span data-ttu-id="aeb3f-104">Konvertiert .NET-Objekte in eine Reihe von CSV-Zeichen folgen (Comma-Separated Value, Komma getrennte Werte).</span><span class="sxs-lookup"><span data-stu-id="aeb3f-104">Converts .NET objects into a series of comma-separated value (CSV) strings.</span></span>

## <span data-ttu-id="aeb3f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aeb3f-105">SYNTAX</span></span>

### <span data-ttu-id="aeb3f-106">Trennzeichen (Standard)</span><span class="sxs-lookup"><span data-stu-id="aeb3f-106">Delimiter (Default)</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [[-Delimiter] <char>] [-NoTypeInformation]
 [<CommonParameters>]
```

### <span data-ttu-id="aeb3f-107">UseCulture</span><span class="sxs-lookup"><span data-stu-id="aeb3f-107">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [-UseCulture] [-NoTypeInformation] [<CommonParameters>]
```

## <span data-ttu-id="aeb3f-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aeb3f-108">DESCRIPTION</span></span>

<span data-ttu-id="aeb3f-109">Das- `ConvertTo-CSV` Cmdlet gibt eine Reihe von CSV-Zeichen folgen zurück, die die von Ihnen gesendeten Objekte darstellen.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-109">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="aeb3f-110">Sie können dann mit dem `ConvertFrom-Csv` Cmdlet Objekte aus den CSV-Zeichen folgen neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-110">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="aeb3f-111">Die aus CSV konvertierten Objekte sind Zeichen folgen Werte der ursprünglichen Objekte, die Eigenschaftswerte und keine Methoden enthalten.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-111">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="aeb3f-112">Sie können das `Export-Csv` Cmdlet verwenden, um Objekte in CSV-Zeichen folgen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-112">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="aeb3f-113">`Export-CSV` ähnelt `ConvertTo-CSV` , mit der Ausnahme, dass die CSV-Zeichen folgen in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-113">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="aeb3f-114">Das- `ConvertTo-CSV` Cmdlet verfügt über Parameter, um ein anderes Trennzeichen als ein Komma anzugeben, oder die aktuelle Kultur als Trennzeichen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-114">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="aeb3f-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="aeb3f-115">EXAMPLES</span></span>

### <span data-ttu-id="aeb3f-116">Beispiel 1: Konvertieren eines Objekts in ein CSV</span><span class="sxs-lookup"><span data-stu-id="aeb3f-116">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="aeb3f-117">In diesem Beispiel wird ein **Prozess** Objekt in eine CSV-Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-117">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name 'PowerShell' | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"powershell","11","691","2204036739072","175943680","132665344","33312", ...
```

<span data-ttu-id="aeb3f-118">Das `Get-Process` -Cmdlet ruft das **Process** -Objekt ab und verwendet den **Name** -Parameter, um den PowerShell-Prozess anzugeben.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-118">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="aeb3f-119">Das Prozess Objekt wird in der Pipeline an das `ConvertTo-CSV` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-119">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="aeb3f-120">Das- `ConvertTo-CSV` Cmdlet konvertiert das Objekt in CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-120">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="aeb3f-121">Mit dem **notypeinformation** -Parameter wird der **#Type** Informations Header aus der CSV-Ausgabe entfernt.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-121">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="aeb3f-122">Beispiel 2: Konvertieren eines DateTime-Objekts in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="aeb3f-122">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="aeb3f-123">In diesem Beispiel wird ein **DateTime** -Objekt in eine CSV-Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-123">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="aeb3f-124">`Get-Date`Mit dem-Cmdlet wird das **DateTime** -Objekt abgerufen und in der `$Date` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-124">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="aeb3f-125">Mit dem- `ConvertTo-Csv` Cmdlet wird das **DateTime** -Objekt in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-125">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="aeb3f-126">Der **Inputobject** -Parameter verwendet das **DateTime** -Objekt, das in der Variablen gespeichert ist `$Date` .</span><span class="sxs-lookup"><span data-stu-id="aeb3f-126">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="aeb3f-127">Mit dem **Delimiter** -Parameter wird ein Semikolon zum Trennen der Zeichen folgen Werte angegeben.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-127">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="aeb3f-128">Mit dem **notypeinformation** -Parameter wird der **#Type** Informations Header aus der CSV-Ausgabe entfernt.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-128">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="aeb3f-129">Beispiel 3: Konvertieren des PowerShell-Ereignis Protokolls in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="aeb3f-129">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="aeb3f-130">In diesem Beispiel wird das Windows-Ereignisprotokoll für PowerShell in eine Reihe von CSV-Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-130">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'Windows PowerShell' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error","403",,"0","4","4",,"36028797018963968","46891","PowerShell", ...
```

<span data-ttu-id="aeb3f-131">Das `Get-Culture` Cmdlet verwendet die genten Eigenschaften **TextInfo** und **ListSeparator** und zeigt das Standard Listen Trennzeichen der aktuellen Kultur an.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-131">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="aeb3f-132">`Get-WinEvent`Mit dem-Cmdlet werden die Ereignisprotokoll Objekte abgerufen, und der **logName** -Parameter wird verwendet, um den Namen der Protokolldatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-132">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="aeb3f-133">Die Ereignisprotokoll Objekte werden über die Pipeline an das `ConvertTo-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-133">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="aeb3f-134">Mit dem- `ConvertTo-Csv` Cmdlet werden die Ereignisprotokoll Objekte in eine Reihe von CSV-Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-134">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="aeb3f-135">Der **useculture** -Parameter verwendet das Standard Listen Trennzeichen der aktuellen Kultur als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-135">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="aeb3f-136">Mit dem **notypeinformation** -Parameter wird der **#Type** Informations Header aus der CSV-Ausgabe entfernt.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-136">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

## <span data-ttu-id="aeb3f-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aeb3f-137">PARAMETERS</span></span>

### <span data-ttu-id="aeb3f-138">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="aeb3f-138">-Delimiter</span></span>

<span data-ttu-id="aeb3f-139">Gibt das Trennzeichen zum Trennen der Eigenschaftswerte in CSV-Zeichen folgen an.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-139">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="aeb3f-140">Der Standardwert ist ein Komma ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="aeb3f-140">The default is a comma (`,`).</span></span> <span data-ttu-id="aeb3f-141">Geben Sie ein Zeichen ein, z. b. einen Doppelpunkt ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="aeb3f-141">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="aeb3f-142">Um ein Semikolon ( `;` ) anzugeben, schließen Sie es in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-142">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

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

### <span data-ttu-id="aeb3f-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="aeb3f-143">-InputObject</span></span>

<span data-ttu-id="aeb3f-144">Gibt die Objekte an, die in CSV-Zeichen folgen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-144">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="aeb3f-145">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-145">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="aeb3f-146">Sie können Objekte auch über die Pipeline an übergeben `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="aeb3f-146">You can also pipe objects to `ConvertTo-CSV`.</span></span>

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

### <span data-ttu-id="aeb3f-147">-Notypeinformation</span><span class="sxs-lookup"><span data-stu-id="aeb3f-147">-NoTypeInformation</span></span>

<span data-ttu-id="aeb3f-148">Entfernt den **#Type** Informations Header aus der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-148">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="aeb3f-149">Dieser Parameter wurde in PowerShell 6,0 zum Standard und ist aus Gründen der Abwärtskompatibilität eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-149">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="aeb3f-150">-Useculture</span><span class="sxs-lookup"><span data-stu-id="aeb3f-150">-UseCulture</span></span>

<span data-ttu-id="aeb3f-151">Verwendet das Listen Trennzeichen für die aktuelle Kultur als Element Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-151">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="aeb3f-152">Um das Listen Trennzeichen für eine Kultur zu suchen, verwenden Sie den folgenden Befehl: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="aeb3f-152">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="aeb3f-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aeb3f-153">CommonParameters</span></span>

<span data-ttu-id="aeb3f-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aeb3f-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aeb3f-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aeb3f-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="aeb3f-156">INPUTS</span></span>

### <span data-ttu-id="aeb3f-157">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="aeb3f-157">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="aeb3f-158">Sie können jedes beliebige Objekt über die Pipeline übergeben, das über einen Extended Type System (ETS)-Adapter verfügt `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="aeb3f-158">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="aeb3f-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="aeb3f-159">OUTPUTS</span></span>

### <span data-ttu-id="aeb3f-160">System.String</span><span class="sxs-lookup"><span data-stu-id="aeb3f-160">System.String</span></span>

<span data-ttu-id="aeb3f-161">Die CSV-Ausgabe wird als Auflistung von Zeichenfolgen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-161">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="aeb3f-162">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="aeb3f-162">NOTES</span></span>

<span data-ttu-id="aeb3f-163">Im CSV-Format wird jedes Objekt durch eine durch Trennzeichen getrennte Liste seiner Eigenschaftswerte dargestellt.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-163">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="aeb3f-164">Die Eigenschaftswerte werden mithilfe der Methode "$ **String ()** " des Objekts in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-164">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="aeb3f-165">Die Zeichen folgen werden durch den Namen des Eigenschafts Werts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-165">The strings are represented by the property value name.</span></span> <span data-ttu-id="aeb3f-166">`ConvertTo-CSV` exportiert nicht die Methoden des Objekts.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-166">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="aeb3f-167">Die CSV-Zeichen folgen werden wie folgt ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="aeb3f-167">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="aeb3f-168">Standardmäßig enthält die erste Zeichenfolge den **#Type** Informations Header, gefolgt vom voll qualifizierten Namen des Objekt Typs.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-168">By default the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span> <span data-ttu-id="aeb3f-169">#Type z. b. **System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-169">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="aeb3f-170">Wenn **notypeinformation** verwendet wird, enthält die erste Zeichenfolge die Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-170">If **NoTypeInformation** is used the first string includes the column headers.</span></span> <span data-ttu-id="aeb3f-171">Die Header enthalten die Eigenschaftsnamen des ersten Objekts als durch Trennzeichen getrennte Liste.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-171">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="aeb3f-172">Die übrigen Zeichen folgen enthalten durch Trennzeichen getrennte Listen der Eigenschaftswerte jedes Objekts.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-172">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="aeb3f-173">Wenn Sie mehrere Objekte an senden `ConvertTo-CSV` , `ConvertTo-CSV` ordnet die Zeichen folgen auf der Grundlage der Eigenschaften des ersten von Ihnen gesendeten Objekts zu.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-173">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="aeb3f-174">Wenn die übrigen Objekte nicht über eine der angegebenen Eigenschaften verfügen, ist der Eigenschafts Wert dieses Objekts NULL, was durch zwei aufeinander folgende Kommas dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-174">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="aeb3f-175">Wenn die übrigen Objekte zusätzliche Eigenschaften aufweisen, werden diese Eigenschaftswerte ignoriert.</span><span class="sxs-lookup"><span data-stu-id="aeb3f-175">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="aeb3f-176">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="aeb3f-176">RELATED LINKS</span></span>

[<span data-ttu-id="aeb3f-177">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="aeb3f-177">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="aeb3f-178">Export-CSV</span><span class="sxs-lookup"><span data-stu-id="aeb3f-178">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="aeb3f-179">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="aeb3f-179">Import-Csv</span></span>](Import-Csv.md)
