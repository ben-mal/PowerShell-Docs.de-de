---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: bd68ee4175a5e5a3e3e544e745113255a6f7a865
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210095"
---
# <span data-ttu-id="e5234-103">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="e5234-103">ConvertTo-Json</span></span>

## <span data-ttu-id="e5234-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e5234-104">SYNOPSIS</span></span>
<span data-ttu-id="e5234-105">Konvertiert ein Objekt in eine JSON-formatierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e5234-105">Converts an object to a JSON-formatted string.</span></span>

## <span data-ttu-id="e5234-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e5234-106">SYNTAX</span></span>

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
[-EnumsAsStrings] [-AsArray] [-EscapeHandling <StringEscapeHandling>]
[<CommonParameters>]
```

## <span data-ttu-id="e5234-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e5234-107">DESCRIPTION</span></span>

<span data-ttu-id="e5234-108">Mit dem- `ConvertTo-Json` Cmdlet wird ein beliebiges .NET-Objekt in eine Zeichenfolge im JSON-Format (JavaScript Object Notation) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e5234-108">The `ConvertTo-Json` cmdlet converts any .NET object to a string in JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="e5234-109">Die Eigenschaften werden in Feldnamen konvertiert, die Feldwerte werden in Eigenschaftswerte konvertiert, und die Methoden werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="e5234-109">The properties are converted to field names, the field values are converted to property values, and the methods are removed.</span></span>

<span data-ttu-id="e5234-110">Sie können dann mit dem `ConvertFrom-Json` Cmdlet eine JSON-formatierte Zeichenfolge in ein JSON-Objekt konvertieren, das leicht in PowerShell verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e5234-110">You can then use the `ConvertFrom-Json` cmdlet to convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell.</span></span>

<span data-ttu-id="e5234-111">Viele Websites verwenden JSON statt XML, um Daten für die Kommunikation zwischen Servern und webbasierten Apps zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="e5234-111">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="e5234-112">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e5234-112">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="e5234-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e5234-113">EXAMPLES</span></span>

### <span data-ttu-id="e5234-114">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="e5234-114">Example 1</span></span>

```powershell
(Get-UICulture).Calendar | ConvertTo-Json
```

```Output
{
  "MinSupportedDateTime": "0001-01-01T00:00:00",
  "MaxSupportedDateTime": "9999-12-31T23:59:59.9999999",
  "AlgorithmType": 1,
  "CalendarType": 1,
  "Eras": [
    1
  ],
  "TwoDigitYearMax": 2029,
  "IsReadOnly": true
}
```

<span data-ttu-id="e5234-115">Dieser Befehl verwendet das `ConvertTo-Json` Cmdlet, um ein GregorianCalendar-Objekt in eine JSON-formatierte Zeichenfolge zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="e5234-115">This command uses the `ConvertTo-Json` cmdlet to convert a GregorianCalendar object to a JSON-formatted string.</span></span>

### <span data-ttu-id="e5234-116">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="e5234-116">Example 2</span></span>

```powershell
Get-Date | ConvertTo-Json; Get-Date | ConvertTo-Json -AsArray
```

```Output
{
  "value": "2018-10-12T23:07:18.8450248-05:00",
  "DisplayHint": 2,
  "DateTime": "October 12, 2018 11:07:18 PM"
}
[
  {
    "value": "2018-10-12T23:07:18.8480668-05:00",
    "DisplayHint": 2,
    "DateTime": "October 12, 2018 11:07:18 PM"
  }
]
```

<span data-ttu-id="e5234-117">Dieses Beispiel zeigt die Ausgabe des `ConvertTo-Json` Cmdlets mit und ohne den **asarray** -Switch-Parameter.</span><span class="sxs-lookup"><span data-stu-id="e5234-117">This example shows the output from `ConvertTo-Json` cmdlet with and without the **AsArray** switch parameter.</span></span> <span data-ttu-id="e5234-118">Sie können sehen, dass der zweite Teil der Ausgabe in eckige Klammern eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e5234-118">You can see the second portion of the output is wrapped in array brackets.</span></span>

### <span data-ttu-id="e5234-119">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="e5234-119">Example 3</span></span>

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

<span data-ttu-id="e5234-120">Dieser Befehl zeigt die Auswirkung der Verwendung des Parameters " **Compress** " von `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="e5234-120">This command shows the effect of using the **Compress** parameter of `ConvertTo-Json`.</span></span> <span data-ttu-id="e5234-121">Die Komprimierung wirkt sich nur auf die Darstellung der Zeichenfolge, nicht auf ihre Gültigkeit aus.</span><span class="sxs-lookup"><span data-stu-id="e5234-121">The compression affects only the appearance of the string, not its validity.</span></span>

### <span data-ttu-id="e5234-122">Beispiel 4</span><span class="sxs-lookup"><span data-stu-id="e5234-122">Example 4</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json
```

```Output
{
  "DisplayHint": 2,
  "DateTime": "October 12, 2018 10:55:32 PM",
  "Date": "2018-10-12T00:00:00-05:00",
  "Day": 12,
  "DayOfWeek": 5,
  "DayOfYear": 285,
  "Hour": 22,
  "Kind": 2,
  "Millisecond": 639,
  "Minute": 55,
  "Month": 10,
  "Second": 32,
  "Ticks": 636749817326397744,
  "TimeOfDay": {
    "Ticks": 825326397744,
    "Days": 0,
    "Hours": 22,
    "Milliseconds": 639,
    "Minutes": 55,
    "Seconds": 32,
    "TotalDays": 0.95523888627777775,
    "TotalHours": 22.925733270666665,
    "TotalMilliseconds": 82532639.774400011,
    "TotalMinutes": 1375.54399624,
    "TotalSeconds": 82532.6397744
  },
  "Year": 2018
}
```

<span data-ttu-id="e5234-123">In diesem Beispiel wird das- `ConvertTo-Json` Cmdlet zum Konvertieren eines **System. DateTime** -Objekts aus dem `Get-Date` Cmdlet in eine JSON-formatierte Zeichenfolge verwendet.</span><span class="sxs-lookup"><span data-stu-id="e5234-123">This example uses the `ConvertTo-Json` cmdlet to convert a **System.DateTime** object from the `Get-Date` cmdlet to a JSON-formatted string.</span></span> <span data-ttu-id="e5234-124">Der Befehl verwendet das `Select-Object` Cmdlet, um alle ( `*` ) der Eigenschaften des **DateTime** -Objekts zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e5234-124">The command uses the `Select-Object` cmdlet to get all (`*`) of the properties of the **DateTime** object.</span></span> <span data-ttu-id="e5234-125">Die Ausgabe zeigt die JSON-Zeichenfolge, die `ConvertTo-Json` zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="e5234-125">The output shows the JSON string that `ConvertTo-Json` returned.</span></span>

### <span data-ttu-id="e5234-126">Beispiel 5</span><span class="sxs-lookup"><span data-stu-id="e5234-126">Example 5</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : October 12, 2018 10:55:52 PM
Date        : 2018-10-12 12:00:00 AM
Day         : 12
DayOfWeek   : 5
DayOfYear   : 285
Hour        : 22
Kind        : 2
Millisecond : 768
Minute      : 55
Month       : 10
Second      : 52
Ticks       : 636749817527683372
TimeOfDay   : @{Ticks=825527683372; Days=0; Hours=22; Milliseconds=768; Minutes=55; Seconds=52;
              TotalDays=0.95547185575463; TotalHours=22.9313245381111; TotalMilliseconds=82552768.3372;
              TotalMinutes=1375.87947228667; TotalSeconds=82552.7683372}
Year        : 2018
```

<span data-ttu-id="e5234-127">In diesem Beispiel wird gezeigt, wie `ConvertTo-Json` die `ConvertFrom-Json` Cmdlets und verwendet werden, um ein Objekt in eine JSON-Zeichenfolge und ein JSON-Objekt zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="e5234-127">This example shows how to use the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert an object to a JSON string and a JSON object.</span></span>

## <span data-ttu-id="e5234-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e5234-128">PARAMETERS</span></span>

### <span data-ttu-id="e5234-129">-Asarray</span><span class="sxs-lookup"><span data-stu-id="e5234-129">-AsArray</span></span>

<span data-ttu-id="e5234-130">Gibt das-Objekt in Array Klammern aus, auch wenn die Eingabe ein einzelnes Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="e5234-130">Outputs the object in array brackets, even if the input is a single object.</span></span>

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

### <span data-ttu-id="e5234-131">-Komprimieren</span><span class="sxs-lookup"><span data-stu-id="e5234-131">-Compress</span></span>

<span data-ttu-id="e5234-132">Lässt Leerstellen und eingerückte Formatierungen in der Ausgabezeichenfolge aus.</span><span class="sxs-lookup"><span data-stu-id="e5234-132">Omits white space and indented formatting in the output string.</span></span>

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

### <span data-ttu-id="e5234-133">-Tiefe</span><span class="sxs-lookup"><span data-stu-id="e5234-133">-Depth</span></span>

<span data-ttu-id="e5234-134">Gibt an, wie viele Ebenen der enthaltenen Objekte in der JSON-Darstellung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e5234-134">Specifies how many levels of contained objects are included in the JSON representation.</span></span> <span data-ttu-id="e5234-135">Der Standardwert ist 2.</span><span class="sxs-lookup"><span data-stu-id="e5234-135">The default value is 2.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5234-136">-Enumsasstrings</span><span class="sxs-lookup"><span data-stu-id="e5234-136">-EnumsAsStrings</span></span>

<span data-ttu-id="e5234-137">Stellt eine Alternative Serialisierungsoption bereit, die alle Enumerationen in ihre Zeichen folgen Darstellung konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e5234-137">Provides an alternative serialization option that converts all enumerations to their string representation.</span></span>

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

### <span data-ttu-id="e5234-138">-Escapehanding</span><span class="sxs-lookup"><span data-stu-id="e5234-138">-EscapeHandling</span></span>

<span data-ttu-id="e5234-139">Steuert, wie bestimmte Zeichen in der resultierenden JSON-Ausgabe mit Escapezeichen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="e5234-139">Controls how certain characters are escaped in the resulting JSON output.</span></span> <span data-ttu-id="e5234-140">Standardmäßig werden nur Steuerzeichen mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="e5234-140">By default, only control characters (like newline) are escaped.</span></span>

<span data-ttu-id="e5234-141">Zulässige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="e5234-141">Acceptable values are:</span></span>

- <span data-ttu-id="e5234-142">Nur-Standard Steuerzeichen werden mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="e5234-142">Default - Only control characters are escaped.</span></span>
- <span data-ttu-id="e5234-143">Escapesonascii-alle nicht-ASCII-und-Steuerzeichen werden mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="e5234-143">EscapeNonAscii - All non-ASCII and control characters are escaped.</span></span>
- <span data-ttu-id="e5234-144">EscapeHtml-HTML ( `<` , `>` , `&` , `'` , `"` ) und Steuerzeichen werden mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="e5234-144">EscapeHtml - HTML (`<`, `>`, `&`, `'`, `"`) and control characters are escaped.</span></span>

<span data-ttu-id="e5234-145">Dieser Parameter wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e5234-145">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: Newtonsoft.Json.StringEscapeHandling
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5234-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e5234-146">-InputObject</span></span>

<span data-ttu-id="e5234-147">Gibt die Objekte an, die in das JSON-Format konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e5234-147">Specifies the objects to convert to JSON format.</span></span> <span data-ttu-id="e5234-148">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e5234-148">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="e5234-149">Sie können ein Objekt auch über die Pipeline an übergeben `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="e5234-149">You can also pipe an object to `ConvertTo-Json`.</span></span>

<span data-ttu-id="e5234-150">Der **Inputobject** -Parameter ist erforderlich, aber sein Wert kann NULL ( `$null` ) oder eine leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="e5234-150">The **InputObject** parameter is required, but its value can be null (`$null`) or an empty string.</span></span>
<span data-ttu-id="e5234-151">Wenn das Eingabe Objekt ist `$null` , `ConvertTo-Json` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e5234-151">When the input object is `$null`, `ConvertTo-Json` does not generate any output.</span></span> <span data-ttu-id="e5234-152">Wenn das Eingabe Objekt eine leere Zeichenfolge ist, wird `ConvertTo-Json` eine leere Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e5234-152">When the input object is an empty string, `ConvertTo-Json` returns an empty string.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e5234-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e5234-153">CommonParameters</span></span>

<span data-ttu-id="e5234-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e5234-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e5234-155">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e5234-155">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e5234-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e5234-156">INPUTS</span></span>

### <span data-ttu-id="e5234-157">System.Object</span><span class="sxs-lookup"><span data-stu-id="e5234-157">System.Object</span></span>

<span data-ttu-id="e5234-158">Sie können jedes beliebige Objekt an die Pipeline übergeben `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="e5234-158">You can pipe any object to `ConvertTo-Json`.</span></span>

## <span data-ttu-id="e5234-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e5234-159">OUTPUTS</span></span>

### <span data-ttu-id="e5234-160">System.String</span><span class="sxs-lookup"><span data-stu-id="e5234-160">System.String</span></span>

## <span data-ttu-id="e5234-161">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e5234-161">NOTES</span></span>

<span data-ttu-id="e5234-162">Das `ConvertTo-Json` Cmdlet wird mithilfe von [newtonsoft JSON.net](https://www.newtonsoft.com/json)implementiert.</span><span class="sxs-lookup"><span data-stu-id="e5234-162">The `ConvertTo-Json` cmdlet is implemented using [Newtonsoft Json.NET](https://www.newtonsoft.com/json).</span></span>

## <span data-ttu-id="e5234-163">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e5234-163">RELATED LINKS</span></span>

<span data-ttu-id="e5234-164">[Eine Einführung in JavaScript Object Notation (JSON) in JavaScript und .net](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="e5234-164">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="e5234-165">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="e5234-165">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="e5234-166">Get-Content</span><span class="sxs-lookup"><span data-stu-id="e5234-166">Get-Content</span></span>](../Microsoft.PowerShell.Management/Get-Content.md)

[<span data-ttu-id="e5234-167">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="e5234-167">Get-UICulture</span></span>](Get-UICulture.md)

[<span data-ttu-id="e5234-168">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="e5234-168">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="e5234-169">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="e5234-169">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="e5234-170">NewtonSoft.Js. Stringescapehanding</span><span class="sxs-lookup"><span data-stu-id="e5234-170">NewtonSoft.Json.StringEscapeHandling</span></span>](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm)
