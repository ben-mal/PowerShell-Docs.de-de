---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: a222044b9dc62a7b0834f7350fd32bed2e95d9a9
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224676"
---
# <span data-ttu-id="aeb26-103">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="aeb26-103">ConvertFrom-Json</span></span>

## <span data-ttu-id="aeb26-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="aeb26-104">SYNOPSIS</span></span>
<span data-ttu-id="aeb26-105">Konvertiert eine JSON-formatierte Zeichenfolge in ein benutzerdefiniertes Objekt oder eine Hash Tabelle.</span><span class="sxs-lookup"><span data-stu-id="aeb26-105">Converts a JSON-formatted string to a custom object or a hash table.</span></span>

## <span data-ttu-id="aeb26-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aeb26-106">SYNTAX</span></span>

```
ConvertFrom-Json [-InputObject] <String> [-AsHashtable] [-Depth <Int32>] [-NoEnumerate] [<CommonParameters>]
```

## <span data-ttu-id="aeb26-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aeb26-107">DESCRIPTION</span></span>

<span data-ttu-id="aeb26-108">Das `ConvertFrom-Json` Cmdlet konvertiert eine JavaScript Object Notation (JSON) formatierte Zeichenfolge in ein benutzerdefiniertes **pscustomobject** -Objekt, das über eine Eigenschaft für jedes Feld in der JSON-Zeichenfolge verfügt.</span><span class="sxs-lookup"><span data-stu-id="aeb26-108">The `ConvertFrom-Json` cmdlet converts a JavaScript Object Notation (JSON) formatted string to a custom **PSCustomObject** object that has a property for each field in the JSON string.</span></span> <span data-ttu-id="aeb26-109">JSON wird häufig von Websites verwendet, um eine Textdarstellung der Objekte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="aeb26-109">JSON is commonly used by web sites to provide a textual representation of objects.</span></span> <span data-ttu-id="aeb26-110">Der JSON-Standard unterstützt nicht die Verwendung, die für ein **pscustomobject** unzulässig ist.</span><span class="sxs-lookup"><span data-stu-id="aeb26-110">The JSON standard does not prohibit usage that is prohibited with a **PSCustomObject**.</span></span> <span data-ttu-id="aeb26-111">Wenn die JSON-Zeichenfolge z. b. doppelte Schlüssel enthält, wird nur der letzte Schlüssel von diesem Cmdlet verwendet.</span><span class="sxs-lookup"><span data-stu-id="aeb26-111">For example, if the JSON string contains duplicate keys, only the last key is used by this cmdlet.</span></span> <span data-ttu-id="aeb26-112">Weitere Beispiele finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="aeb26-112">See other examples below.</span></span>

<span data-ttu-id="aeb26-113">Verwenden Sie das-Cmdlet, um eine JSON-Zeichenfolge aus einem beliebigen Objekt zu generieren `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="aeb26-113">To generate a JSON string from any object, use the `ConvertTo-Json` cmdlet.</span></span>

<span data-ttu-id="aeb26-114">Dieses Cmdlet wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="aeb26-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="aeb26-115">Ab PowerShell 6 unterstützt dieses Cmdlet JSON mit Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="aeb26-115">Beginning with PowerShell 6, this cmdlet supports JSON with comments.</span></span> <span data-ttu-id="aeb26-116">Akzeptierte Kommentare werden mit zwei Schrägstrichen () gestartet `//` .</span><span class="sxs-lookup"><span data-stu-id="aeb26-116">Accepted comments are started with two forward slashes (`//`).</span></span> <span data-ttu-id="aeb26-117">Der Kommentar wird nicht in den Daten dargestellt und kann in die Datei geschrieben werden, ohne die Daten zu beschädigen oder wie in PowerShell 5,1 einen Fehler auszulösen.</span><span class="sxs-lookup"><span data-stu-id="aeb26-117">The comment will not be represented in the data and can be written in the file without corrupting the data or throwing an error as it did in PowerShell 5.1.</span></span>

## <span data-ttu-id="aeb26-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="aeb26-118">EXAMPLES</span></span>

### <span data-ttu-id="aeb26-119">Beispiel 1: Konvertieren eines DateTime-Objekts in ein JSON-Objekt</span><span class="sxs-lookup"><span data-stu-id="aeb26-119">Example 1: Convert a DateTime object to a JSON object</span></span>

<span data-ttu-id="aeb26-120">Dieser Befehl verwendet die `ConvertTo-Json` `ConvertFrom-Json` Cmdlets und, um ein **DateTime** -Objekt aus dem `Get-Date` Cmdlet in ein JSON-Objekt in ein **pscustomobject** -Objekt zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="aeb26-120">This command uses the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert a **DateTime** object from the `Get-Date` cmdlet to a JSON object then to a **PSCustomObject**.</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : Friday, January 13, 2012 8:06:31 PM
Date        : 1/13/2012 8:00:00 AM
Day         : 13
DayOfWeek   : 5
DayOfYear   : 13
Hour        : 20
Kind        : 2
Millisecond : 400
Minute      : 6
Month       : 1
Second      : 31
Ticks       : 634620819914009002
TimeOfDay   : @{Ticks=723914009002; Days=0; Hours=20; Milliseconds=400; Minutes=6; Seconds=31; TotalDays=0.83786343634490734; TotalHours=20.108722472277776; TotalMilliseconds=72391400.900200009; TotalMinutes=1206.5233483366667;TotalSeconds=72391.4009002}
Year        : 2012
```

<span data-ttu-id="aeb26-121">Im Beispiel wird das- `Select-Object` Cmdlet verwendet, um alle Eigenschaften des **DateTime** -Objekts zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="aeb26-121">The example uses the `Select-Object` cmdlet to get all of the properties of the **DateTime** object.</span></span> <span data-ttu-id="aeb26-122">Er verwendet das `ConvertTo-Json` Cmdlet, um das **DateTime** -Objekt in eine Zeichenfolge zu konvertieren, die als JSON-Objekt formatiert ist, und das `ConvertFrom-Json` Cmdlet zum Konvertieren der JSON-formatierten Zeichenfolge in ein **pscustomobject** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="aeb26-122">It uses the `ConvertTo-Json` cmdlet to convert the **DateTime** object to a string formatted as a JSON object and the `ConvertFrom-Json` cmdlet to convert the JSON-formatted string to a **PSCustomObject** object.</span></span>

### <span data-ttu-id="aeb26-123">Beispiel 2: erhalten von JSON-Zeichen folgen aus einem Webdienst und Konvertieren der Zeichen folgen in PowerShell-Objekte</span><span class="sxs-lookup"><span data-stu-id="aeb26-123">Example 2: Get JSON strings from a web service and convert them to PowerShell objects</span></span>

<span data-ttu-id="aeb26-124">Dieser Befehl verwendet das `Invoke-WebRequest` Cmdlet, um JSON-Zeichen folgen von einem Webdienst zu erhalten, und verwendet dann das `ConvertFrom-Json` Cmdlet, um JSON-Inhalte in Objekte zu konvertieren, die in PowerShell verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="aeb26-124">This command uses the `Invoke-WebRequest` cmdlet to get JSON strings from a web service and then it uses the `ConvertFrom-Json` cmdlet to convert JSON content to objects that can be managed in PowerShell.</span></span>

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

<span data-ttu-id="aeb26-125">Sie können auch das- `Invoke-RestMethod` Cmdlet verwenden, mit dem JSON-Inhalte automatisch in-Objekte konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="aeb26-125">You can also use the `Invoke-RestMethod` cmdlet, which automatically converts JSON content to objects.</span></span>

### <span data-ttu-id="aeb26-126">Beispiel 3: Konvertieren einer JSON-Zeichenfolge in ein benutzerdefiniertes Objekt</span><span class="sxs-lookup"><span data-stu-id="aeb26-126">Example 3: Convert a JSON string to a custom object</span></span>

<span data-ttu-id="aeb26-127">Dieses Beispiel zeigt, wie Sie mit dem `ConvertFrom-Json` Cmdlet eine JSON-Datei in ein benutzerdefiniertes PowerShell-Objekt konvertieren.</span><span class="sxs-lookup"><span data-stu-id="aeb26-127">This example shows how to use the `ConvertFrom-Json` cmdlet to convert a JSON file to a PowerShell custom object.</span></span>

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

<span data-ttu-id="aeb26-128">Der Befehl verwendet Get-Content Cmdlet, um die Zeichen folgen in einer JSON-Datei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="aeb26-128">The command uses Get-Content cmdlet to get the strings in a JSON file.</span></span> <span data-ttu-id="aeb26-129">Anschließend wird der Pipeline Operator verwendet, um die durch Trennzeichen getrennte Zeichenfolge an das- `ConvertFrom-Json` Cmdlet zu senden, das Sie in ein benutzerdefiniertes-Objekt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="aeb26-129">Then it uses the pipeline operator to send the delimited string to the `ConvertFrom-Json` cmdlet, which converts it to a custom object.</span></span>

### <span data-ttu-id="aeb26-130">Beispiel 4: Konvertieren einer JSON-Zeichenfolge in eine Hash Tabelle</span><span class="sxs-lookup"><span data-stu-id="aeb26-130">Example 4: Convert a JSON string to a hash table</span></span>

<span data-ttu-id="aeb26-131">Dieser Befehl zeigt ein Beispiel an, in dem der `-AsHashtable` Schalter die Einschränkungen des Befehls überwinden kann.</span><span class="sxs-lookup"><span data-stu-id="aeb26-131">This command shows an example where the `-AsHashtable` switch can overcome limitations of the command.</span></span>

```powershell
'{ "key":"value1", "Key":"value2" }' | ConvertFrom-Json -AsHashtable
```

<span data-ttu-id="aeb26-132">Die JSON-Zeichenfolge enthält zwei Schlüsselwert Paare mit Schlüsseln, die sich nur in der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="aeb26-132">The JSON string contains two key value pairs with keys that differ only in casing.</span></span> <span data-ttu-id="aeb26-133">Ohne den-Schalter hätte der Befehl einen Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="aeb26-133">Without the switch, the command would have thrown an error.</span></span>

### <span data-ttu-id="aeb26-134">Beispiel 5: Roundtrip eines einzelnen Element Arrays</span><span class="sxs-lookup"><span data-stu-id="aeb26-134">Example 5: Round-trip a single element array</span></span>

<span data-ttu-id="aeb26-135">Mit diesem Befehl wird ein Beispiel gezeigt, in dem der `-NoEnumerate` Schalter zum Roundtrip eines JSON-Arrays eines einzelnen Elements verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aeb26-135">This command shows an example where the `-NoEnumerate` switch is used to round-trip a single element JSON array.</span></span>

```powershell
Write-Output "With -NoEnumerate: $('[1]' | ConvertFrom-Json -NoEnumerate | ConvertTo-Json -Compress)"
Write-Output "Without -NoEnumerate: $('[1]' | ConvertFrom-Json | ConvertTo-Json -Compress)"
```

```Output
With -NoEnumerate: [1]
Without -NoEnumerate: 1
```

<span data-ttu-id="aeb26-136">Die JSON-Zeichenfolge enthält ein Array mit einem einzelnen Element.</span><span class="sxs-lookup"><span data-stu-id="aeb26-136">The JSON string contains an array with a single element.</span></span> <span data-ttu-id="aeb26-137">Ohne den-Schalter führt die Umstellung der JSON-Datei in ein psobject-Objekt und das anschließende zurückkehren mit dem `ConvertTo-Json` Befehl zu einer einzelnen ganzen Zahl.</span><span class="sxs-lookup"><span data-stu-id="aeb26-137">Without the switch, converting the JSON to a PSObject and then converting it back with the `ConvertTo-Json` command results in a single integer.</span></span>

## <span data-ttu-id="aeb26-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aeb26-138">PARAMETERS</span></span>

### <span data-ttu-id="aeb26-139">-Ashashtable</span><span class="sxs-lookup"><span data-stu-id="aeb26-139">-AsHashtable</span></span>

<span data-ttu-id="aeb26-140">Konvertiert den JSON-Code in ein Hash Tabellenobjekt.</span><span class="sxs-lookup"><span data-stu-id="aeb26-140">Converts the JSON to a hash table object.</span></span> <span data-ttu-id="aeb26-141">Dieser Switch wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="aeb26-141">This switch was introduced in PowerShell 6.0.</span></span> <span data-ttu-id="aeb26-142">Es gibt verschiedene Szenarien, in denen einige Einschränkungen des `ConvertFrom-Json` Cmdlets gelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="aeb26-142">There are several scenarios where it can overcome some limitations of the `ConvertFrom-Json` cmdlet.</span></span>

- <span data-ttu-id="aeb26-143">, Wenn der JSON-Code eine Liste mit Schlüsseln enthält, die sich nur in der Schreibweise unterscheiden</span><span class="sxs-lookup"><span data-stu-id="aeb26-143">If the JSON contains a list with keys that only differ in casing.</span></span> <span data-ttu-id="aeb26-144">Ohne den-Schalter werden diese Schlüssel als identische Schlüssel betrachtet, und daher wird nur die letzte verwendet.</span><span class="sxs-lookup"><span data-stu-id="aeb26-144">Without the switch, those keys would be seen as identical keys and therefore only the last one would get used.</span></span>
- <span data-ttu-id="aeb26-145">, Wenn der JSON-Code einen Schlüssel enthält, der eine leere Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="aeb26-145">If the JSON contains a key that is an empty string.</span></span> <span data-ttu-id="aeb26-146">Ohne den-Schalter löst das Cmdlet einen Fehler aus, da `PSCustomObject` dies nicht zulässt, sondern eine Hash Tabelle.</span><span class="sxs-lookup"><span data-stu-id="aeb26-146">Without the switch, the cmdlet would throw an error since a `PSCustomObject` does not allow for that but a hash table does.</span></span> <span data-ttu-id="aeb26-147">Ein Beispiel für einen Anwendungsfall, bei dem dies vorkommen kann, sind `project.lock.json` Dateien.</span><span class="sxs-lookup"><span data-stu-id="aeb26-147">An example use case where this can occurs are `project.lock.json` files.</span></span>
- <span data-ttu-id="aeb26-148">Hash Tabellen können für bestimmte Datenstrukturen schneller verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="aeb26-148">Hash tables can be processed faster for certain data structures.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aeb26-149">-Tiefe</span><span class="sxs-lookup"><span data-stu-id="aeb26-149">-Depth</span></span>

<span data-ttu-id="aeb26-150">Ruft die maximale Tiefe ab, für die die JSON-Eingabe zulässig ist, oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="aeb26-150">Gets or sets the maximum depth the JSON input is allowed to have.</span></span> <span data-ttu-id="aeb26-151">Der Standardwert ist 1024.</span><span class="sxs-lookup"><span data-stu-id="aeb26-151">By default, it is 1024.</span></span>

<span data-ttu-id="aeb26-152">Dieser Parameter wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="aeb26-152">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aeb26-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="aeb26-153">-InputObject</span></span>

<span data-ttu-id="aeb26-154">Gibt die JSON-Zeichenfolgen an, die in JSON-Objekte konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="aeb26-154">Specifies the JSON strings to convert to JSON objects.</span></span> <span data-ttu-id="aeb26-155">Geben Sie eine Variable ein, die die Zeichenfolge enthält, oder geben Sie einen Befehl oder Ausdruck ein, der die Zeichenfolge abruft.</span><span class="sxs-lookup"><span data-stu-id="aeb26-155">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="aeb26-156">Sie können eine Zeichenfolge auch über die Pipeline an senden `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="aeb26-156">You can also pipe a string to `ConvertFrom-Json`.</span></span>

<span data-ttu-id="aeb26-157">Der **InputObject** -Parameter ist erforderlich, sein Wert kann jedoch eine leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="aeb26-157">The **InputObject** parameter is required, but its value can be an empty string.</span></span> <span data-ttu-id="aeb26-158">Wenn das Eingabe Objekt eine leere Zeichenfolge ist, `ConvertFrom-Json` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="aeb26-158">When the input object is an empty string, `ConvertFrom-Json` does not generate any output.</span></span> <span data-ttu-id="aeb26-159">Der **Inputobject** -Wert darf nicht sein `$null` .</span><span class="sxs-lookup"><span data-stu-id="aeb26-159">The **InputObject** value cannot be `$null`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="aeb26-160">-Noenumerate</span><span class="sxs-lookup"><span data-stu-id="aeb26-160">-NoEnumerate</span></span>

<span data-ttu-id="aeb26-161">Gibt an, dass die Ausgabe nicht aufgezählt wird.</span><span class="sxs-lookup"><span data-stu-id="aeb26-161">Specifies that output is not enumerated.</span></span>

<span data-ttu-id="aeb26-162">Das Festlegen dieses Parameters bewirkt, dass Arrays als einzelnes Objekt gesendet werden, statt jedes Element separat zu senden.</span><span class="sxs-lookup"><span data-stu-id="aeb26-162">Setting this parameter causes arrays to be sent as a single object instead of sending every element separately.</span></span> <span data-ttu-id="aeb26-163">Dadurch wird sichergestellt, dass JSON über eine Roundtrip-Schleife erfolgen kann `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="aeb26-163">This guarantees that JSON can be round-tripped via `ConvertTo-Json`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aeb26-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aeb26-164">CommonParameters</span></span>

<span data-ttu-id="aeb26-165">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aeb26-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aeb26-166">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aeb26-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aeb26-167">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="aeb26-167">INPUTS</span></span>

### <span data-ttu-id="aeb26-168">System.String</span><span class="sxs-lookup"><span data-stu-id="aeb26-168">System.String</span></span>

<span data-ttu-id="aeb26-169">Sie können eine JSON-Zeichenfolge an übergeben `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="aeb26-169">You can pipe a JSON string to `ConvertFrom-Json`.</span></span>

## <span data-ttu-id="aeb26-170">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="aeb26-170">OUTPUTS</span></span>

### <span data-ttu-id="aeb26-171">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="aeb26-171">PSCustomObject</span></span>

### <span data-ttu-id="aeb26-172">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="aeb26-172">System.Collections.Hashtable</span></span>

## <span data-ttu-id="aeb26-173">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="aeb26-173">NOTES</span></span>

<span data-ttu-id="aeb26-174">Dieses Cmdlet wird mithilfe von [newtonsoft JSON.net](https://www.newtonsoft.com/json)implementiert.</span><span class="sxs-lookup"><span data-stu-id="aeb26-174">This cmdlet is implemented using [Newtonsoft Json.NET](https://www.newtonsoft.com/json).</span></span>

<span data-ttu-id="aeb26-175">Ab PowerShell 6 versucht, Zeichen folgen, `ConvertTo-Json` die als Zeitstempel formatiert sind, in **DateTime** -Werte zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="aeb26-175">Beginning in PowerShell 6, `ConvertTo-Json` attempts to convert strings formatted as timestamps to **DateTime** values.</span></span> <span data-ttu-id="aeb26-176">Der konvertierte Wert ist eine-Instanz, deren- `[datetime]` `Kind` Eigenschaft wie folgt festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="aeb26-176">The converted value is a `[datetime]` instance with a `Kind` property set as follows:</span></span>

- <span data-ttu-id="aeb26-177">`Unspecified`, wenn keine Zeitzoneninformationen in der Eingabe Zeichenfolge vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="aeb26-177">`Unspecified`, if there is no time zone information in the input string.</span></span>
- <span data-ttu-id="aeb26-178">`Utc`, wenn die Zeitzoneninformationen eine nachfolgende ist `Z` .</span><span class="sxs-lookup"><span data-stu-id="aeb26-178">`Utc`, if the time zone information is a trailing `Z`.</span></span>
- <span data-ttu-id="aeb26-179">`Local`, wenn die Zeitzoneninformationen als nachfolg _Ende UTC-_ Abweichung wie angegeben werden `+02:00` .</span><span class="sxs-lookup"><span data-stu-id="aeb26-179">`Local`, if the time zone information is given as a trailing UTC _offset_ like `+02:00`.</span></span> <span data-ttu-id="aeb26-180">Der Offset wird ordnungsgemäß in die konfigurierte Zeitzone des Aufrufers konvertiert.</span><span class="sxs-lookup"><span data-stu-id="aeb26-180">The offset is properly converted to the caller's configured time zone.</span></span> <span data-ttu-id="aeb26-181">Die Standardausgabe Formatierung weist nicht auf den ursprünglichen Zeit Zonen Offset hin.</span><span class="sxs-lookup"><span data-stu-id="aeb26-181">The default output formatting does not indicate the original time zone offset.</span></span>

## <span data-ttu-id="aeb26-182">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="aeb26-182">RELATED LINKS</span></span>

<span data-ttu-id="aeb26-183">[Eine Einführung in JavaScript Object Notation (JSON) in JavaScript und .net](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="aeb26-183">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="aeb26-184">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="aeb26-184">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="aeb26-185">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="aeb26-185">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="aeb26-186">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="aeb26-186">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

