---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSet“ (Format)
description: Element „SelectionSet“ (Format)
ms.openlocfilehash: 944aa83569ad8ca789746a71f60e5da5c19fbf01
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647862"
---
# <a name="selectionset-element-format"></a>Element „SelectionSet“ (Format)

Definiert einen Satz von .NET-Objekten, auf die durch den Namen des Satzes verwiesen werden kann.

Configuration-Element (Format) selectionsets-Element (Format) SelectionSet-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `SelectionSet` Elements beschrieben. Jeder Auswahl Satz muss über einen Namen verfügen, und er muss die .NET-Objekte des Satzes angeben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „Name“ für SelectionSet (Format)](./name-element-for-selectionset-format.md)|Erforderliches Element.<br /><br /> Gibt den Namen an, mit dem auf den Auswahl Satz verwiesen wird.|
|[Types-Element (Format)](./types-element-for-selectionset-format.md)|Erforderliches Element.<br /><br /> Definiert die .NET-Objekte, die sich im Auswahl Satz befinden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Selectionsets-Element Format](./selectionsets-element-format.md)|Definiert die allgemeinen Sätze von .NET-Objekten, die von allen Sichten der Formatierungs Datei verwendet werden können.|

## <a name="remarks"></a>Bemerkungen

Sie können Auswahl Sätze verwenden, wenn Sie über einen Satz verwandter Objekte verfügen, auf die Sie verweisen möchten, indem Sie einen einzelnen Namen verwenden, z. b. eine Gruppe von Objekten, die durch Vererbung verknüpft sind. Wenn Sie die Ansichten definieren, können Sie den Satz von-Objekten angeben, indem Sie den Namen des Auswahl Satzes verwenden, anstatt alle Objekte in jeder Ansicht aufzulisten.

Beim Definieren der Sichten der Formatierungs Datei oder der Definitionen der Sichten werden allgemeine Auswahl Sätze durch ihren Namen angegeben. In diesen Fällen gibt das untergeordnete `SelectionSetName` -Element des `ViewSelectedBy` -Elements und des- `EntrySelectedBy` Elements die zu verwendende Gruppe an. Weitere Informationen zu Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt ein- `SelectionSet` Element, das vier .NET-Typen definiert.

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

## <a name="see-also"></a>Weitere Informationen

[Definieren von Auswahlgruppen](./defining-selection-sets.md)

[Name-Element von SelectionSet (Format)](./name-element-for-selectionset-format.md)

[Element „SelectionSets“ (Format)](./selectionsets-element-format.md)

[Types-Element (Format)](./types-element-for-selectionset-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
