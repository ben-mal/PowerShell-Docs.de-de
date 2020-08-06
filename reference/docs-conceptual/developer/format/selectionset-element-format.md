---
title: SelectionSet-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: cf47229993458492c712d28e04913e75d1bde386
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783397"
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

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „Name“ für SelectionSet (Format)](./name-element-for-selectionset-format.md)|Erforderliches Element.<br /><br /> Gibt den Namen an, mit dem auf den Auswahl Satz verwiesen wird.|
|[Types-Element (Format)](./types-element-for-selectionset-format.md)|Erforderliches Element.<br /><br /> Definiert die .NET-Objekte, die sich im Auswahl Satz befinden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
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
