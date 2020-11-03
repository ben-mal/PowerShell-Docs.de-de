---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: 2e3d49700adb8115bf24ae505fbb00c14a774f15
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211383"
---
# <span data-ttu-id="4e323-103">Test-Json</span><span class="sxs-lookup"><span data-stu-id="4e323-103">Test-Json</span></span>

## <span data-ttu-id="4e323-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4e323-104">SYNOPSIS</span></span>
<span data-ttu-id="4e323-105">Testet, ob eine Zeichenfolge ein gültiges JSON-Dokument ist.</span><span class="sxs-lookup"><span data-stu-id="4e323-105">Tests whether a string is a valid JSON document</span></span>

## <span data-ttu-id="4e323-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4e323-106">SYNTAX</span></span>

```
Test-Json [-Json] <string> [[-Schema] <string>] [<CommonParameters>]
```

## <span data-ttu-id="4e323-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4e323-107">DESCRIPTION</span></span>

<span data-ttu-id="4e323-108">Das `Test-Json` -Cmdlet testet, ob eine Zeichenfolge ein gültiges JavaScript Object Notation (JSON)-Dokument ist, und kann optional das JSON-Dokument anhand eines bereitgestellten Schemas überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4e323-108">The `Test-Json` cmdlet tests whether a string is a valid JavaScript Object Notation (JSON) document and can optionally verify that JSON document against a provided schema.</span></span>

<span data-ttu-id="4e323-109">Die überprüfte Zeichenfolge kann dann mit dem `ConvertFrom-Json` Cmdlet verwendet werden, um eine JSON-formatierte Zeichenfolge in ein JSON-Objekt zu konvertieren, das problemlos in PowerShell verwaltet oder an ein anderes Programm oder einen Webdienst gesendet wird, die auf die JSON-Eingabe zugreifen</span><span class="sxs-lookup"><span data-stu-id="4e323-109">The verified string can then be used with the `ConvertFrom-Json` cmdlet convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell or sent to another program or web service that access JSON input.</span></span>

<span data-ttu-id="4e323-110">Viele Websites verwenden JSON statt XML, um Daten für die Kommunikation zwischen Servern und webbasierten Apps zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="4e323-110">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="4e323-111">Dieses Cmdlet wurde in PowerShell 6,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4e323-111">This cmdlet was introduced in PowerShell 6.1</span></span>

## <span data-ttu-id="4e323-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4e323-112">EXAMPLES</span></span>

### <span data-ttu-id="4e323-113">Beispiel 1: testen, ob ein Objekt gültiges JSON ist</span><span class="sxs-lookup"><span data-stu-id="4e323-113">Example 1: Test if an object is valid JSON</span></span>

<span data-ttu-id="4e323-114">In diesem Beispiel wird getestet, ob die Eingabe Zeichenfolge ein gültiges JSON-Dokument ist.</span><span class="sxs-lookup"><span data-stu-id="4e323-114">This example tests whether the input string is a valid JSON document.</span></span>

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### <span data-ttu-id="4e323-115">Beispiel 2: Testen eines Objekts mit einem bereitgestellten Schema</span><span class="sxs-lookup"><span data-stu-id="4e323-115">Example 2: Test an object against a provided schema</span></span>

<span data-ttu-id="4e323-116">In diesem Beispiel wird eine Zeichenfolge mit einem JSON-Schema angenommen und mit einer Eingabe Zeichenfolge verglichen.</span><span class="sxs-lookup"><span data-stu-id="4e323-116">This example takes a string containing a JSON schema and compares it to an input string.</span></span>

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

<span data-ttu-id="4e323-117">In diesem Beispiel erhalten wir eine Fehlermeldung, da das Schema eine ganze Zahl für das **Alter** erwartet, die JSON-Eingabe, die wir getestet haben, stattdessen einen Zeichen folgen Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e323-117">In this example, we get an error because the schema expects an integer for **age** but the JSON input we tested uses a string value instead.</span></span>

<span data-ttu-id="4e323-118">Weitere Informationen finden Sie unter [JSON-Schema](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="4e323-118">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

## <span data-ttu-id="4e323-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4e323-119">PARAMETERS</span></span>

### <span data-ttu-id="4e323-120">-JSON</span><span class="sxs-lookup"><span data-stu-id="4e323-120">-Json</span></span>

<span data-ttu-id="4e323-121">Gibt die JSON-Zeichenfolge an, deren Gültigkeit überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="4e323-121">Specifies the JSON string to test for validity.</span></span> <span data-ttu-id="4e323-122">Geben Sie eine Variable ein, die die Zeichenfolge enthält, oder geben Sie einen Befehl oder Ausdruck ein, der die Zeichenfolge abruft.</span><span class="sxs-lookup"><span data-stu-id="4e323-122">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="4e323-123">Sie können eine Zeichenfolge auch über die Pipeline an senden `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="4e323-123">You can also pipe a string to `Test-Json`.</span></span>

<span data-ttu-id="4e323-124">Der **JSON** -Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4e323-124">The **Json** parameter is required.</span></span>

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

### <span data-ttu-id="4e323-125">-Schema</span><span class="sxs-lookup"><span data-stu-id="4e323-125">-Schema</span></span>

<span data-ttu-id="4e323-126">Gibt ein Schema an, mit dem die JSON-Eingabe überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="4e323-126">Specifies a Schema to validate the JSON input against.</span></span> <span data-ttu-id="4e323-127">Wenn übergeben `Test-Json` wird, wird überprüft, ob die JSON-Eingabe der durch den **Schema** -Parameter angegebenen Spezifikation entspricht und nur dann zurückgegeben wird, `$True` Wenn die Eingabe dem bereitgestellten Schema entspricht.</span><span class="sxs-lookup"><span data-stu-id="4e323-127">If passed `Test-Json` will validate that the Json input conforms to the spec specified by the **Schema** parameter and return `$True` only if the input conforms to the provided Schema.</span></span>

<span data-ttu-id="4e323-128">Weitere Informationen finden Sie unter [JSON-Schema](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="4e323-128">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

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

### <span data-ttu-id="4e323-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4e323-129">CommonParameters</span></span>

<span data-ttu-id="4e323-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4e323-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4e323-131">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4e323-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4e323-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4e323-132">INPUTS</span></span>

### <span data-ttu-id="4e323-133">System.String</span><span class="sxs-lookup"><span data-stu-id="4e323-133">System.String</span></span>

<span data-ttu-id="4e323-134">Sie können eine JSON-Zeichenfolge an übergeben `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="4e323-134">You can pipe a JSON string to `Test-Json`.</span></span>

## <span data-ttu-id="4e323-135">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4e323-135">OUTPUTS</span></span>

### <span data-ttu-id="4e323-136">Boolean</span><span class="sxs-lookup"><span data-stu-id="4e323-136">Boolean</span></span>

## <span data-ttu-id="4e323-137">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4e323-137">NOTES</span></span>

<span data-ttu-id="4e323-138">Das- `Test-Json` Cmdlet wird mithilfe der [njsonschema-Klasse](https://github.com/RSuter/NJsonSchema)implementiert.</span><span class="sxs-lookup"><span data-stu-id="4e323-138">The `Test-Json` cmdlet is implemented by using the [NJsonSchema Class](https://github.com/RSuter/NJsonSchema).</span></span>

## <span data-ttu-id="4e323-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4e323-139">RELATED LINKS</span></span>

<span data-ttu-id="4e323-140">[Eine Einführung in JavaScript Object Notation (JSON) in JavaScript und .net](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="4e323-140">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="4e323-141">Weitere JSON-Schema Details</span><span class="sxs-lookup"><span data-stu-id="4e323-141">Additional JSON Schema Details</span></span>](https://json-schema.org/)

[<span data-ttu-id="4e323-142">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="4e323-142">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="4e323-143">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="4e323-143">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="4e323-144">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="4e323-144">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
