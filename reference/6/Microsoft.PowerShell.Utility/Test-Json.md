---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: 618e00d8db5eadfa8658203ef435a23cfea25be3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216204"
---
# <span data-ttu-id="2d4d2-103">Test-Json</span><span class="sxs-lookup"><span data-stu-id="2d4d2-103">Test-Json</span></span>

## <span data-ttu-id="2d4d2-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2d4d2-104">SYNOPSIS</span></span>
<span data-ttu-id="2d4d2-105">Testet, ob eine Zeichenfolge ein gültiges JSON-Dokument ist.</span><span class="sxs-lookup"><span data-stu-id="2d4d2-105">Tests whether a string is a valid JSON document</span></span>

## <span data-ttu-id="2d4d2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2d4d2-106">SYNTAX</span></span>

```
Test-Json [-Json] <string> [[-Schema] <string>] [<CommonParameters>]
```

## <span data-ttu-id="2d4d2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2d4d2-107">DESCRIPTION</span></span>

<span data-ttu-id="2d4d2-108">Das `Test-Json` -Cmdlet testet, ob eine Zeichenfolge ein gültiges JavaScript Object Notation (JSON)-Dokument ist, und kann optional das JSON-Dokument anhand eines bereitgestellten Schemas überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2d4d2-108">The `Test-Json` cmdlet tests whether a string is a valid JavaScript Object Notation (JSON) document and can optionally verify that JSON document against a provided schema.</span></span>

<span data-ttu-id="2d4d2-109">Die überprüfte Zeichenfolge kann dann mit dem `ConvertFrom-Json` Cmdlet verwendet werden, um eine JSON-formatierte Zeichenfolge in ein JSON-Objekt zu konvertieren, das problemlos in PowerShell verwaltet oder an ein anderes Programm oder einen Webdienst gesendet wird, die auf die JSON-Eingabe zugreifen</span><span class="sxs-lookup"><span data-stu-id="2d4d2-109">The verified string can then be used with the `ConvertFrom-Json` cmdlet convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell or sent to another program or web service that access JSON input.</span></span>

<span data-ttu-id="2d4d2-110">Viele Websites verwenden JSON statt XML, um Daten für die Kommunikation zwischen Servern und webbasierten Apps zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="2d4d2-110">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="2d4d2-111">Dieses Cmdlet wurde in PowerShell 6,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2d4d2-111">This cmdlet was introduced in PowerShell 6.1</span></span>

## <span data-ttu-id="2d4d2-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2d4d2-112">EXAMPLES</span></span>

### <span data-ttu-id="2d4d2-113">Beispiel 1: testen, ob ein Objekt gültiges JSON ist</span><span class="sxs-lookup"><span data-stu-id="2d4d2-113">Example 1: Test if an object is valid JSON</span></span>

<span data-ttu-id="2d4d2-114">In diesem Beispiel wird getestet, ob die Eingabe Zeichenfolge ein gültiges JSON-Dokument ist.</span><span class="sxs-lookup"><span data-stu-id="2d4d2-114">This example tests whether the input string is a valid JSON document.</span></span>

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### <span data-ttu-id="2d4d2-115">Beispiel 2: Testen eines Objekts mit einem bereitgestellten Schema</span><span class="sxs-lookup"><span data-stu-id="2d4d2-115">Example 2: Test an object against a provided schema</span></span>

<span data-ttu-id="2d4d2-116">In diesem Beispiel wird eine Zeichenfolge mit einem JSON-Schema angenommen und mit einer Eingabe Zeichenfolge verglichen.</span><span class="sxs-lookup"><span data-stu-id="2d4d2-116">This example takes a string containing a JSON schema and compares it to an input string.</span></span>

```powershell
$schema = @'
{
  "definitions": {},
  "$schema": "http://json-schema.org/draft-07/schema#",
  "$id": "http://example.com/root.json",
  "type": "object",
  "title": "The Root Schema",
  "required": [
    "name",
    "age"
  ],
  "properties": {
    "name": {
      "$id": "#/properties/name",
      "type": "string",
      "title": "The Name Schema",
      "default": "",
      "examples": [
        "Ashley"
      ],
      "pattern": "^(.*)$"
    },
    "age": {
      "$id": "#/properties/age",
      "type": "integer",
      "title": "The Age Schema",
      "default": 0,
      "examples": [
        25
      ]
    }
  }
}
'@
"{'name': 'Ashley', 'age': '25'}" | Test-Json -Schema $schema
```

```Output
Test-Json : IntegerExpected: #/age
At line:1 char:37
+ "{'name': 'Ashley', 'age': '25'}" | Test-Json -Schema $schema
+                                     ~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidData: (:) [Test-Json], Exception
+ FullyQualifiedErrorId : InvalidJsonAgainstSchema,Microsoft.PowerShell.Commands.TestJsonCommand
False
```

<span data-ttu-id="2d4d2-117">In diesem Beispiel erhalten wir eine Fehlermeldung, da das Schema eine ganze Zahl für das **Alter** erwartet, die JSON-Eingabe, die wir getestet haben, stattdessen einen Zeichen folgen Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d4d2-117">In this example, we get an error because the schema expects an integer for **age** but the JSON input we tested uses a string value instead.</span></span>

<span data-ttu-id="2d4d2-118">Weitere Informationen finden Sie unter [JSON-Schema](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="2d4d2-118">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

## <span data-ttu-id="2d4d2-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2d4d2-119">PARAMETERS</span></span>

### <span data-ttu-id="2d4d2-120">-JSON</span><span class="sxs-lookup"><span data-stu-id="2d4d2-120">-Json</span></span>

<span data-ttu-id="2d4d2-121">Gibt die JSON-Zeichenfolge an, deren Gültigkeit überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d4d2-121">Specifies the JSON string to test for validity.</span></span> <span data-ttu-id="2d4d2-122">Geben Sie eine Variable ein, die die Zeichenfolge enthält, oder geben Sie einen Befehl oder Ausdruck ein, der die Zeichenfolge abruft.</span><span class="sxs-lookup"><span data-stu-id="2d4d2-122">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="2d4d2-123">Sie können eine Zeichenfolge auch über die Pipeline an senden `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="2d4d2-123">You can also pipe a string to `Test-Json`.</span></span>

<span data-ttu-id="2d4d2-124">Der **JSON** -Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2d4d2-124">The **Json** parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2d4d2-125">-Schema</span><span class="sxs-lookup"><span data-stu-id="2d4d2-125">-Schema</span></span>

<span data-ttu-id="2d4d2-126">Gibt ein Schema an, mit dem die JSON-Eingabe überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d4d2-126">Specifies a Schema to validate the JSON input against.</span></span> <span data-ttu-id="2d4d2-127">Wenn übergeben `Test-Json` wird, wird überprüft, ob die JSON-Eingabe der durch den **Schema** -Parameter angegebenen Spezifikation entspricht und nur dann zurückgegeben wird, `$True` Wenn die Eingabe dem bereitgestellten Schema entspricht.</span><span class="sxs-lookup"><span data-stu-id="2d4d2-127">If passed `Test-Json` will validate that the Json input conforms to the spec specified by the **Schema** parameter and return `$True` only if the input conforms to the provided Schema.</span></span>

<span data-ttu-id="2d4d2-128">Weitere Informationen finden Sie unter [JSON-Schema](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="2d4d2-128">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d4d2-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2d4d2-129">CommonParameters</span></span>

<span data-ttu-id="2d4d2-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2d4d2-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2d4d2-131">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2d4d2-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2d4d2-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2d4d2-132">INPUTS</span></span>

### <span data-ttu-id="2d4d2-133">System.String</span><span class="sxs-lookup"><span data-stu-id="2d4d2-133">System.String</span></span>

<span data-ttu-id="2d4d2-134">Sie können eine JSON-Zeichenfolge an übergeben `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="2d4d2-134">You can pipe a JSON string to `Test-Json`.</span></span>

## <span data-ttu-id="2d4d2-135">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2d4d2-135">OUTPUTS</span></span>

### <span data-ttu-id="2d4d2-136">Boolean</span><span class="sxs-lookup"><span data-stu-id="2d4d2-136">Boolean</span></span>

## <span data-ttu-id="2d4d2-137">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2d4d2-137">NOTES</span></span>

<span data-ttu-id="2d4d2-138">Das- `Test-Json` Cmdlet wird mithilfe der [njsonschema-Klasse](https://github.com/RSuter/NJsonSchema)implementiert.</span><span class="sxs-lookup"><span data-stu-id="2d4d2-138">The `Test-Json` cmdlet is implemented by using the [NJsonSchema Class](https://github.com/RSuter/NJsonSchema).</span></span>

## <span data-ttu-id="2d4d2-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2d4d2-139">RELATED LINKS</span></span>

<span data-ttu-id="2d4d2-140">[Eine Einführung in JavaScript Object Notation (JSON) in JavaScript und .net](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="2d4d2-140">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="2d4d2-141">Weitere JSON-Schema Details</span><span class="sxs-lookup"><span data-stu-id="2d4d2-141">Additional JSON Schema Details</span></span>](https://json-schema.org/)

[<span data-ttu-id="2d4d2-142">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="2d4d2-142">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="2d4d2-143">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="2d4d2-143">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="2d4d2-144">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="2d4d2-144">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
