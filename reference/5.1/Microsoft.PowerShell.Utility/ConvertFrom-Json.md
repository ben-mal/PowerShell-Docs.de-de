---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: e1bab9250269dadf0d899f9e172e8a4a8387271d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388126"
---
# <span data-ttu-id="2e642-103">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="2e642-103">ConvertFrom-Json</span></span>

## <span data-ttu-id="2e642-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2e642-104">SYNOPSIS</span></span>
<span data-ttu-id="2e642-105">Konvertiert eine JSON-formatierte Zeichenfolge in ein benutzerdefiniertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="2e642-105">Converts a JSON-formatted string to a custom object.</span></span>

## <span data-ttu-id="2e642-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e642-106">SYNTAX</span></span>

```
ConvertFrom-Json [-InputObject] <String> [<CommonParameters>]
```

## <span data-ttu-id="2e642-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2e642-107">DESCRIPTION</span></span>

<span data-ttu-id="2e642-108">Das `ConvertFrom-Json` Cmdlet konvertiert eine JavaScript Object Notation (JSON) formatierte Zeichenfolge in ein benutzerdefiniertes **pscustomobject** -Objekt, das über eine Eigenschaft für jedes Feld in der JSON-Zeichenfolge verfügt.</span><span class="sxs-lookup"><span data-stu-id="2e642-108">The `ConvertFrom-Json` cmdlet converts a JavaScript Object Notation (JSON) formatted string to a custom **PSCustomObject** object that has a property for each field in the JSON string.</span></span> <span data-ttu-id="2e642-109">JSON wird häufig von Websites verwendet, um eine Textdarstellung der Objekte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2e642-109">JSON is commonly used by web sites to provide a textual representation of objects.</span></span> <span data-ttu-id="2e642-110">Der JSON-Standard unterstützt nicht die Verwendung, die für ein **pscustomobject** unzulässig ist.</span><span class="sxs-lookup"><span data-stu-id="2e642-110">The JSON standard does not prohibit usage that is prohibited with a **PSCustomObject**.</span></span> <span data-ttu-id="2e642-111">Wenn die JSON-Zeichenfolge z. b. doppelte Schlüssel enthält, wird nur der letzte Schlüssel von diesem Cmdlet verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e642-111">For example, if the JSON string contains duplicate keys, only the last key is used by this cmdlet.</span></span> <span data-ttu-id="2e642-112">Weitere Beispiele finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="2e642-112">See other examples below.</span></span>

<span data-ttu-id="2e642-113">Verwenden Sie das-Cmdlet, um eine JSON-Zeichenfolge aus einem beliebigen Objekt zu generieren `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="2e642-113">To generate a JSON string from any object, use the `ConvertTo-Json` cmdlet.</span></span>

<span data-ttu-id="2e642-114">Dieses Cmdlet wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2e642-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="2e642-115">Dieses Cmdlet unterstützt JSON nicht mit Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="2e642-115">This cmdlet doesn't support JSON with comments.</span></span>

## <span data-ttu-id="2e642-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2e642-116">EXAMPLES</span></span>

### <span data-ttu-id="2e642-117">Beispiel 1: Konvertieren eines DateTime-Objekts in ein JSON-Objekt</span><span class="sxs-lookup"><span data-stu-id="2e642-117">Example 1: Convert a DateTime object to a JSON object</span></span>

<span data-ttu-id="2e642-118">Dieser Befehl verwendet die `ConvertTo-Json` `ConvertFrom-Json` Cmdlets und, um ein **DateTime** -Objekt aus dem `Get-Date` Cmdlet in ein JSON-Objekt in ein **pscustomobject** -Objekt zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="2e642-118">This command uses the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert a **DateTime** object from the `Get-Date` cmdlet to a JSON object then to a **PSCustomObject**.</span></span>

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

<span data-ttu-id="2e642-119">Im Beispiel wird das- `Select-Object` Cmdlet verwendet, um alle Eigenschaften des **DateTime** -Objekts zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2e642-119">The example uses the `Select-Object` cmdlet to get all of the properties of the **DateTime** object.</span></span> <span data-ttu-id="2e642-120">Er verwendet das `ConvertTo-Json` Cmdlet, um das **DateTime** -Objekt in eine Zeichenfolge zu konvertieren, die als JSON-Objekt formatiert ist, und das `ConvertFrom-Json` Cmdlet zum Konvertieren der JSON-formatierten Zeichenfolge in ein **pscustomobject** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="2e642-120">It uses the `ConvertTo-Json` cmdlet to convert the **DateTime** object to a string formatted as a JSON object and the `ConvertFrom-Json` cmdlet to convert the JSON-formatted string to a **PSCustomObject** object.</span></span>

### <span data-ttu-id="2e642-121">Beispiel 2: erhalten von JSON-Zeichen folgen aus einem Webdienst und Konvertieren der Zeichen folgen in PowerShell-Objekte</span><span class="sxs-lookup"><span data-stu-id="2e642-121">Example 2: Get JSON strings from a web service and convert them to PowerShell objects</span></span>

<span data-ttu-id="2e642-122">Dieser Befehl verwendet das `Invoke-WebRequest` Cmdlet, um JSON-Zeichen folgen von einem Webdienst zu erhalten, und verwendet dann das `ConvertFrom-Json` Cmdlet, um JSON-Inhalte in Objekte zu konvertieren, die in PowerShell verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="2e642-122">This command uses the `Invoke-WebRequest` cmdlet to get JSON strings from a web service and then it uses the `ConvertFrom-Json` cmdlet to convert JSON content to objects that can be managed in PowerShell.</span></span>

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

<span data-ttu-id="2e642-123">Sie können auch das- `Invoke-RestMethod` Cmdlet verwenden, mit dem JSON-Inhalte automatisch in-Objekte konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e642-123">You can also use the `Invoke-RestMethod` cmdlet, which automatically converts JSON content to objects.</span></span>

### <span data-ttu-id="2e642-124">Beispiel 3: Konvertieren einer JSON-Zeichenfolge in ein benutzerdefiniertes Objekt</span><span class="sxs-lookup"><span data-stu-id="2e642-124">Example 3: Convert a JSON string to a custom object</span></span>

<span data-ttu-id="2e642-125">Dieses Beispiel zeigt, wie Sie mit dem `ConvertFrom-Json` Cmdlet eine JSON-Datei in ein benutzerdefiniertes PowerShell-Objekt konvertieren.</span><span class="sxs-lookup"><span data-stu-id="2e642-125">This example shows how to use the `ConvertFrom-Json` cmdlet to convert a JSON file to a PowerShell custom object.</span></span>

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

<span data-ttu-id="2e642-126">Der Befehl verwendet Get-Content Cmdlet, um die Zeichen folgen in einer JSON-Datei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2e642-126">The command uses Get-Content cmdlet to get the strings in a JSON file.</span></span> <span data-ttu-id="2e642-127">Anschließend wird der Pipeline Operator verwendet, um die durch Trennzeichen getrennte Zeichenfolge an das- `ConvertFrom-Json` Cmdlet zu senden, das Sie in ein benutzerdefiniertes-Objekt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2e642-127">Then it uses the pipeline operator to send the delimited string to the `ConvertFrom-Json` cmdlet, which converts it to a custom object.</span></span>

## <span data-ttu-id="2e642-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e642-128">PARAMETERS</span></span>

### <span data-ttu-id="2e642-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2e642-129">-InputObject</span></span>

<span data-ttu-id="2e642-130">Gibt die JSON-Zeichenfolgen an, die in JSON-Objekte konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2e642-130">Specifies the JSON strings to convert to JSON objects.</span></span> <span data-ttu-id="2e642-131">Geben Sie eine Variable ein, die die Zeichenfolge enthält, oder geben Sie einen Befehl oder Ausdruck ein, der die Zeichenfolge abruft.</span><span class="sxs-lookup"><span data-stu-id="2e642-131">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="2e642-132">Sie können eine Zeichenfolge auch über die Pipeline an senden `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="2e642-132">You can also pipe a string to `ConvertFrom-Json`.</span></span>

<span data-ttu-id="2e642-133">Der **InputObject** -Parameter ist erforderlich, sein Wert kann jedoch eine leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="2e642-133">The **InputObject** parameter is required, but its value can be an empty string.</span></span> <span data-ttu-id="2e642-134">Wenn das Eingabe Objekt eine leere Zeichenfolge ist, `ConvertFrom-Json` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="2e642-134">When the input object is an empty string, `ConvertFrom-Json` does not generate any output.</span></span> <span data-ttu-id="2e642-135">Der **Inputobject** -Wert darf nicht sein `$null` .</span><span class="sxs-lookup"><span data-stu-id="2e642-135">The **InputObject** value cannot be `$null`.</span></span>

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

### <span data-ttu-id="2e642-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2e642-136">CommonParameters</span></span>

<span data-ttu-id="2e642-137">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2e642-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e642-138">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2e642-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2e642-139">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2e642-139">INPUTS</span></span>

### <span data-ttu-id="2e642-140">System.String</span><span class="sxs-lookup"><span data-stu-id="2e642-140">System.String</span></span>

<span data-ttu-id="2e642-141">Sie können eine JSON-Zeichenfolge an übergeben `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="2e642-141">You can pipe a JSON string to `ConvertFrom-Json`.</span></span>

## <span data-ttu-id="2e642-142">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2e642-142">OUTPUTS</span></span>

### <span data-ttu-id="2e642-143">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="2e642-143">PSCustomObject</span></span>

## <span data-ttu-id="2e642-144">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2e642-144">NOTES</span></span>

<span data-ttu-id="2e642-145">Das `ConvertFrom-Json` Cmdlet wird mithilfe der [JavaScriptSerializer-Klasse](/dotnet/api/system.web.script.serialization.javascriptserializer)implementiert.</span><span class="sxs-lookup"><span data-stu-id="2e642-145">The `ConvertFrom-Json` cmdlet is implemented using the [JavaScriptSerializer class](/dotnet/api/system.web.script.serialization.javascriptserializer).</span></span>

## <span data-ttu-id="2e642-146">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2e642-146">RELATED LINKS</span></span>

<span data-ttu-id="2e642-147">[Eine Einführung in JavaScript Object Notation (JSON) in JavaScript und .net](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="2e642-147">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="2e642-148">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="2e642-148">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="2e642-149">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="2e642-149">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="2e642-150">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="2e642-150">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
