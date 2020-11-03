---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-xml?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Xml
ms.openlocfilehash: 09e962d96bffc1c890a4532502e1f3461180caae
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216780"
---
# ConvertTo-Xml

## ZUSAMMENFASSUNG
Erstellt eine XML-basierte Darstellung eines Objekts.

## SYNTAX

```
ConvertTo-Xml [-Depth <Int32>] [-InputObject] <PSObject> [-NoTypeInformation] [-As <String>]
 [<CommonParameters>]
```

## DESCRIPTION

Das `ConvertTo-Xml` -Cmdlet erstellt eine [XML-basierte](/dotnet/api/system.xml.xmldocument) Darstellung eines oder mehrerer .NET-Objekte. Um dieses Cmdlet zu verwenden, übergeben Sie ein oder mehrere Objekte an das Cmdlet, oder verwenden Sie den **Inputobject** -Parameter, um das Objekt anzugeben.

Wenn Sie mehrere Objekte an übergeben `ConvertTo-Xml` oder den **Inputobject** -Parameter verwenden, um mehrere Objekte zu senden, `ConvertTo-Xml` gibt ein einzelnes XML-Dokument im Arbeitsspeicher zurück, das Darstellungen aller Objekte enthält.

Dieses Cmdlet ähnelt [Export-CliXML](./Export-Clixml.md) , mit der Ausnahme, dass `Export-Clixml` das resultierende XML in einer XML-Datei mit [Common Language Infrastructure (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm) speichert, die als Objekte mit [Import-CliXML](./Import-Clixml.md)erneut importiert werden kann. `ConvertTo-Xml` gibt eine Speicher interne Darstellung eines XML-Dokuments zurück, sodass Sie die Verarbeitung in PowerShell fortsetzen können. `ConvertTo-Xml` bietet keine Option zum Konvertieren von Objekten in die CLI-XML.

## BEISPIELE

### Beispiel 1: Konvertieren eines Datums in XML

```
PS C:\> Get-Date | ConvertTo-Xml
```

Dieser Befehl konvertiert das aktuelle Datum (ein **DateTime** -Objekt) in XML.

### Beispiel 2: Konvertieren von Prozessen in XML

```
PS C:\> ConvertTo-Xml -As "Document" -InputObject (Get-Process) -Depth 3
```

Mit diesem Befehl werden die Prozessobjekte, die alle Prozesse auf dem Computer darstellen, in ein XML-Dokument konvertiert. Die Objekte werden auf eine Tiefe von drei Ebenen erweitert.

## PARAMETERS

### -AS

Bestimmt das Ausgabeformat.
Zulässige Werte für diesen Parameter:

- Eine Zeichenfolge.
Gibt eine einzelne Zeichenfolge zurück.
- Stream.
Gibt ein Array von Zeichenfolgen zurück.
- Dokument.
Gibt ein **XmlDocument** -Objekt zurück.

Der Standardwert ist "Document".

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Stream, String, Document

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tiefe

Gibt an, wie viele Ebenen der enthaltenen Objekte in der XML-Darstellung enthalten sind. Der Standardwert ist 1.

Wenn beispielsweise die Eigenschaften des Objekts ebenfalls Objekte enthalten, müssen Sie eine Tiefe von 2 angeben, um eine XML-Darstellung der Eigenschaften der enthaltenen Objekte zu speichern.

Der Standardwert kann für den Objekttyp in den Dateien „Types.ps1xml“ überschrieben werden. Weitere Informationen finden Sie unter „about_Types.ps1xml“.

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

### -InputObject

Gibt das zu konvertierende Objekt an. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden. Sie können Objekte auch über die Pipeline an **ConvertTo-XML** übergeben.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Notypeinformation

Lässt das Type-Attribute in den Objektknoten aus.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können jedes beliebige Objekt über die Pipeline an **ConvertTo-XML** übergeben.

## AUSGABEN

### System. String-oder System.Xml.Xml-Dokument

Der Wert des *As* -Parameters bestimmt den von **ConvertTo-XML** zurückgegebenen Objekttyp.

## HINWEISE

## VERWANDTE LINKS

[ConvertTo-Csv](ConvertTo-Csv.md)

[ConvertTo-Html](ConvertTo-Html.md)

[Export-Clixml](Export-Clixml.md)

[Get-Date](Get-Date.md)

[Import-Clixml](Import-Clixml.md)
