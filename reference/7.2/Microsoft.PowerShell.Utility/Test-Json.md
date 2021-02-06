---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: a29eab449e567f78d1e54a6716ca91d87aa08405
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600302"
---
# Test-Json

## ZUSAMMENFASSUNG
Testet, ob eine Zeichenfolge ein gültiges JSON-Dokument ist.

## SYNTAX

### __AllParameterSets (Standard)
```
Test-Json [-Json] <String> [<CommonParameters>]
```

### Schemastring
```
Test-Json [-Json] <String> [[-Schema] <String>] [<CommonParameters>]
```

### Schema file
```
Test-Json [-Json] <String> [-SchemaFile <String>] [<CommonParameters>]
```

## DESCRIPTION

Das `Test-Json` -Cmdlet testet, ob eine Zeichenfolge ein gültiges JavaScript Object Notation (JSON)-Dokument ist, und kann optional das JSON-Dokument anhand eines bereitgestellten Schemas überprüfen.

Die überprüfte Zeichenfolge kann dann mit dem `ConvertFrom-Json` Cmdlet verwendet werden, um eine JSON-formatierte Zeichenfolge in ein JSON-Objekt zu konvertieren, das problemlos in PowerShell verwaltet oder an ein anderes Programm oder einen Webdienst gesendet wird, die auf die JSON-Eingabe zugreifen

Viele Websites verwenden JSON statt XML, um Daten für die Kommunikation zwischen Servern und webbasierten Apps zu serialisieren.

Dieses Cmdlet wurde in PowerShell 6,1 eingeführt.

## BEISPIELE

### Beispiel 1: testen, ob ein Objekt gültiges JSON ist

In diesem Beispiel wird getestet, ob die Eingabe Zeichenfolge ein gültiges JSON-Dokument ist.

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### Beispiel 2: Testen eines Objekts mit einem bereitgestellten Schema

In diesem Beispiel wird eine Zeichenfolge mit einem JSON-Schema angenommen und mit einer Eingabe Zeichenfolge verglichen.

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

In diesem Beispiel erhalten wir eine Fehlermeldung, da das Schema eine ganze Zahl für das **Alter** erwartet, die JSON-Eingabe, die wir getestet haben, stattdessen einen Zeichen folgen Wert verwendet.

Weitere Informationen finden Sie unter [JSON-Schema](https://json-schema.org/).

### Beispiel 3: Testen eines Objekts anhand eines Schemas aus einer Datei

Das JSON-Schema kann mithilfe des Schlüssel Worts auf Definitionen verweisen `$ref` . Der `$ref` kann in einen URI aufgelöst werden, der auf eine andere Datei verweist. Der `SchemaFile` -Parameter akzeptiert den literalpfad zur JSON-Schema Datei und ermöglicht die Validierung von JSON-Dateien anhand solcher Schemas.

In diesem Beispiel haben wir `schema.json` die Datei, auf die verweist `definitions.json` .

```powershell
PS> Get-Content schema.json

{
  "description":"A person",
  "type":"object",
  "properties":{
    "name":{
      "$ref":"definitions.json#/definitions/name"
    },
    "hobbies":{
      "$ref":"definitions.json#/definitions/hobbies"
    }
  }
}

PS> Get-Content definitions.json

{
  "definitions":{
    "name":{
      "type":"string"
    },
    "hobbies":{
      "type":"array",
      "items":{
        "type":"string"
      }
    }
  }
}

'{"name": "James", "hobbies": [".NET", "Blogging"]}' | Test-Json -SchemaFile 'schema.json'
```

```Output
True
```

Weitere Informationen finden Sie unter [strukturieren eines komplexen Schemas](https://json-schema.org/understanding-json-schema/structuring.html).

## PARAMETERS

### -JSON

Gibt die JSON-Zeichenfolge an, deren Gültigkeit überprüft werden soll. Geben Sie eine Variable ein, die die Zeichenfolge enthält, oder geben Sie einen Befehl oder Ausdruck ein, der die Zeichenfolge abruft. Sie können eine Zeichenfolge auch über die Pipeline an senden `Test-Json` .

Der **JSON** -Parameter ist erforderlich.

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

### -Schema

Gibt ein Schema an, mit dem die JSON-Eingabe überprüft werden soll. Wenn übergeben `Test-Json` wird, wird überprüft, ob die JSON-Eingabe der durch den **Schema** -Parameter angegebenen Spezifikation entspricht und nur dann zurückgegeben wird, `$True` Wenn die Eingabe dem bereitgestellten Schema entspricht.

Weitere Informationen finden Sie unter [JSON-Schema](https://json-schema.org/).

```yaml
Type: System.String
Parameter Sets: SchemaString
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SchemaFile

Gibt eine Schema Datei an, die zum Überprüfen der JSON-Eingabe verwendet wird. Bei Verwendung von wird `Test-Json` nur dann zurückgegeben, `$True` Wenn die JSON-Eingabe dem Schema entspricht, das in der durch den **SchemaFile** -Parameter angegebenen Datei definiert ist.

Weitere Informationen finden Sie unter [JSON-Schema](https://json-schema.org/).

```yaml
Type: System.String
Parameter Sets: SchemaFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine JSON-Zeichenfolge an übergeben `Test-Json` .

## AUSGABEN

### Boolesch

## HINWEISE

Das- `Test-Json` Cmdlet wird mithilfe der [njsonschema-Klasse](https://github.com/RSuter/NJsonSchema)implementiert.

## VERWANDTE LINKS

[Eine Einführung in JavaScript Object Notation (JSON) in JavaScript und .net](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[Weitere JSON-Schema Details](https://json-schema.org/)

[ConvertTo-Json](ConvertTo-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)
