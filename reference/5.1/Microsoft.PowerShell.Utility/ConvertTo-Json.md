---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: 9831249a9f1ffcc65fc275e44da04fde9348ae71
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388058"
---
# <span data-ttu-id="db24a-103">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="db24a-103">ConvertTo-Json</span></span>

## <span data-ttu-id="db24a-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="db24a-104">SYNOPSIS</span></span>
<span data-ttu-id="db24a-105">Konvertiert ein Objekt in eine JSON-formatierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="db24a-105">Converts an object to a JSON-formatted string.</span></span>

## <span data-ttu-id="db24a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="db24a-106">SYNTAX</span></span>

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
 [<CommonParameters>]
```

## <span data-ttu-id="db24a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="db24a-107">DESCRIPTION</span></span>

<span data-ttu-id="db24a-108">Mit dem- `ConvertTo-Json` Cmdlet wird ein beliebiges .NET-Objekt in eine Zeichenfolge im JSON-Format (JavaScript Object Notation) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="db24a-108">The `ConvertTo-Json` cmdlet converts any .NET object to a string in JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="db24a-109">Die Eigenschaften werden in Feldnamen konvertiert, die Feldwerte werden in Eigenschaftswerte konvertiert, und die Methoden werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="db24a-109">The properties are converted to field names, the field values are converted to property values, and the methods are removed.</span></span>

<span data-ttu-id="db24a-110">Sie können dann mit dem `ConvertFrom-Json` Cmdlet eine JSON-formatierte Zeichenfolge in ein JSON-Objekt konvertieren, das leicht in PowerShell verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="db24a-110">You can then use the `ConvertFrom-Json` cmdlet to convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell.</span></span>

<span data-ttu-id="db24a-111">Viele Websites verwenden JSON statt XML, um Daten für die Kommunikation zwischen Servern und webbasierten Apps zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="db24a-111">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="db24a-112">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="db24a-112">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="db24a-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="db24a-113">EXAMPLES</span></span>

### <span data-ttu-id="db24a-114">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="db24a-114">Example 1</span></span>

```powershell
(Get-UICulture).Calendar | ConvertTo-Json
```

```Output
{
    "MinSupportedDateTime":  "\/Date(-62135596800000)\/",
    "MaxSupportedDateTime":  "\/Date(253402300799999)\/",
    "AlgorithmType":  1,
    "CalendarType":  1,
    "Eras":  [
                 1
             ],
    "TwoDigitYearMax":  2029,
    "IsReadOnly":  false
}
```

<span data-ttu-id="db24a-115">Dieser Befehl verwendet das `ConvertTo-Json` Cmdlet, um ein GregorianCalendar-Objekt in eine JSON-formatierte Zeichenfolge zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="db24a-115">This command uses the `ConvertTo-Json` cmdlet to convert a GregorianCalendar object to a JSON-formatted string.</span></span>

### <span data-ttu-id="db24a-116">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="db24a-116">Example 2</span></span>

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

<span data-ttu-id="db24a-117">Dieser Befehl zeigt die Auswirkung der Verwendung des Parameters " **Compress** " von `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="db24a-117">This command shows the effect of using the **Compress** parameter of `ConvertTo-Json`.</span></span> <span data-ttu-id="db24a-118">Die Komprimierung wirkt sich nur auf die Darstellung der Zeichenfolge, nicht auf ihre Gültigkeit aus.</span><span class="sxs-lookup"><span data-stu-id="db24a-118">The compression affects only the appearance of the string, not its validity.</span></span>

### <span data-ttu-id="db24a-119">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="db24a-119">Example 3</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json
```

```Output
{
    "DisplayHint":  2,
    "DateTime":  "Friday, January 13, 2012 8:06:16 PM",
    "Date":  "\/Date(1326441600000)\/",
    "Day":  13,
    "DayOfWeek":  5,
    "DayOfYear":  13,
    "Hour":  20,
    "Kind":  2,
    "Millisecond":  221,
    "Minute":  6,
    "Month":  1,
    "Second":  16,
    "Ticks":  634620819762218083,
    "TimeOfDay":  {
                      "Ticks":  723762218083,
                      "Days":  0,
                      "Hours":  20,
                      "Milliseconds":  221,
                      "Minutes":  6,
                      "Seconds":  16,
                      "TotalDays":  0.83768775241087956,
                      "TotalHours":  20.104506057861109,
                      "TotalMilliseconds":  72376221.8083,
                      "TotalMinutes":  1206.2703634716668,
                      "TotalSeconds":  72376.22180829999
                  },
    "Year":  2012
}
```

<span data-ttu-id="db24a-120">In diesem Beispiel wird das- `ConvertTo-Json` Cmdlet zum Konvertieren eines **System. DateTime** -Objekts aus dem `Get-Date` Cmdlet in eine JSON-formatierte Zeichenfolge verwendet.</span><span class="sxs-lookup"><span data-stu-id="db24a-120">This example uses the `ConvertTo-Json` cmdlet to convert a **System.DateTime** object from the `Get-Date` cmdlet to a JSON-formatted string.</span></span> <span data-ttu-id="db24a-121">Der Befehl verwendet das `Select-Object` Cmdlet, um alle ( `*` ) der Eigenschaften des **DateTime** -Objekts zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="db24a-121">The command uses the `Select-Object` cmdlet to get all (`*`) of the properties of the **DateTime** object.</span></span> <span data-ttu-id="db24a-122">Die Ausgabe zeigt die JSON-Zeichenfolge, die `ConvertTo-Json` zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="db24a-122">The output shows the JSON string that `ConvertTo-Json` returned.</span></span>

### <span data-ttu-id="db24a-123">Beispiel 4</span><span class="sxs-lookup"><span data-stu-id="db24a-123">Example 4</span></span>

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

<span data-ttu-id="db24a-124">In diesem Beispiel wird gezeigt, wie `ConvertTo-Json` die `ConvertFrom-Json` Cmdlets und verwendet werden, um ein Objekt in eine JSON-Zeichenfolge und ein JSON-Objekt zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="db24a-124">This example shows how to use the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert an object to a JSON string and a JSON object.</span></span>

## <span data-ttu-id="db24a-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="db24a-125">PARAMETERS</span></span>

### <span data-ttu-id="db24a-126">-Komprimieren</span><span class="sxs-lookup"><span data-stu-id="db24a-126">-Compress</span></span>

<span data-ttu-id="db24a-127">Lässt Leerstellen und eingerückte Formatierungen in der Ausgabezeichenfolge aus.</span><span class="sxs-lookup"><span data-stu-id="db24a-127">Omits white space and indented formatting in the output string.</span></span>

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

### <span data-ttu-id="db24a-128">-Tiefe</span><span class="sxs-lookup"><span data-stu-id="db24a-128">-Depth</span></span>

<span data-ttu-id="db24a-129">Gibt an, wie viele Ebenen der enthaltenen Objekte in der JSON-Darstellung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="db24a-129">Specifies how many levels of contained objects are included in the JSON representation.</span></span> <span data-ttu-id="db24a-130">Der Standardwert ist 2.</span><span class="sxs-lookup"><span data-stu-id="db24a-130">The default value is 2.</span></span>

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

### <span data-ttu-id="db24a-131">-InputObject</span><span class="sxs-lookup"><span data-stu-id="db24a-131">-InputObject</span></span>

<span data-ttu-id="db24a-132">Gibt die Objekte an, die in das JSON-Format konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="db24a-132">Specifies the objects to convert to JSON format.</span></span> <span data-ttu-id="db24a-133">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="db24a-133">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="db24a-134">Sie können ein Objekt auch über die Pipeline an übergeben `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="db24a-134">You can also pipe an object to `ConvertTo-Json`.</span></span>

<span data-ttu-id="db24a-135">Der **Inputobject** -Parameter ist erforderlich, aber sein Wert kann NULL ( `$null` ) oder eine leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="db24a-135">The **InputObject** parameter is required, but its value can be null (`$null`) or an empty string.</span></span>
<span data-ttu-id="db24a-136">Wenn das Eingabe Objekt ist `$null` , `ConvertTo-Json` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="db24a-136">When the input object is `$null`, `ConvertTo-Json` does not generate any output.</span></span> <span data-ttu-id="db24a-137">Wenn das Eingabe Objekt eine leere Zeichenfolge ist, wird `ConvertTo-Json` eine leere Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="db24a-137">When the input object is an empty string, `ConvertTo-Json` returns an empty string.</span></span>

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

### <span data-ttu-id="db24a-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="db24a-138">CommonParameters</span></span>

<span data-ttu-id="db24a-139">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="db24a-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="db24a-140">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="db24a-140">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="db24a-141">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="db24a-141">INPUTS</span></span>

### <span data-ttu-id="db24a-142">System.Object</span><span class="sxs-lookup"><span data-stu-id="db24a-142">System.Object</span></span>

<span data-ttu-id="db24a-143">Sie können jedes beliebige Objekt an die Pipeline übergeben `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="db24a-143">You can pipe any object to `ConvertTo-Json`.</span></span>

## <span data-ttu-id="db24a-144">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="db24a-144">OUTPUTS</span></span>

### <span data-ttu-id="db24a-145">System.String</span><span class="sxs-lookup"><span data-stu-id="db24a-145">System.String</span></span>

## <span data-ttu-id="db24a-146">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="db24a-146">NOTES</span></span>

<span data-ttu-id="db24a-147">Das `ConvertTo-Json` Cmdlet wird mithilfe der [JavaScriptSerializer-Klasse](/dotnet/api/system.web.script.serialization.javascriptserializer)implementiert.</span><span class="sxs-lookup"><span data-stu-id="db24a-147">The `ConvertTo-Json` cmdlet is implemented using the [JavaScriptSerializer class](/dotnet/api/system.web.script.serialization.javascriptserializer).</span></span>

## <span data-ttu-id="db24a-148">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="db24a-148">RELATED LINKS</span></span>

<span data-ttu-id="db24a-149">[Eine Einführung in JavaScript Object Notation (JSON) in JavaScript und .net](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="db24a-149">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="db24a-150">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="db24a-150">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="db24a-151">Get-Content</span><span class="sxs-lookup"><span data-stu-id="db24a-151">Get-Content</span></span>](../Microsoft.PowerShell.Management/Get-Content.md)

[<span data-ttu-id="db24a-152">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="db24a-152">Get-UICulture</span></span>](Get-UICulture.md)

[<span data-ttu-id="db24a-153">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="db24a-153">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="db24a-154">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="db24a-154">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
