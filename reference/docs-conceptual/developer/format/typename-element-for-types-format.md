---
title: Typname-Element für Typen (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 40fad73c66124d6c3b0d969b4268713a492c963a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772534"
---
# <a name="typename-element-for-types-format"></a>Element „TypeName“ für Types (Format)

Gibt den .NET-Typ eines Objekts an, das zum Auswahl Satz gehört.

Configuration-Element (Format) selectionsets-Element (Format) SelectionSet-Element (Format) Types-Element (Format) Typname Element of Types (Format)

## <a name="syntax"></a>Syntax

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben. `TypeName`Im Auswahl Satz muss mindestens ein Element enthalten sein.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Types-Element (Format)](./types-element-for-selectionset-format.md)|Definiert die .NET-Objekte, die sich im Auswahl Satz befinden.|

## <a name="text-value"></a>Textwert

Geben Sie den voll qualifizierten Namen des .net-Typs an.

## <a name="remarks"></a>Bemerkungen

Sie können Auswahl Sätze verwenden, wenn Sie über einen Satz verwandter Objekte verfügen, auf die Sie verweisen möchten, indem Sie einen einzelnen Namen verwenden, z. b. eine Gruppe von Objekten, die durch Vererbung verknüpft sind. Wenn Sie die Ansichten definieren, können Sie den Satz von-Objekten angeben, indem Sie den Namen des Auswahl Satzes verwenden, anstatt alle Objekte in jeder Ansicht aufzulisten.

Allgemeine Auswahl Sätze werden durch ihren Namen angegeben, wenn die Ansichten der Formatierungs Datei definiert werden. In diesen Fällen gibt das untergeordnete- `SelectionSetName` Element des- `ViewSelectedBy` Elements für die Sicht den Satz an. Bei verschiedenen Einträgen einer Sicht kann jedoch auch ein Auswahl Satz angegeben werden, der nur für diesen Eintrag der Sicht gilt. Weitere Informationen zu Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt ein- `SelectionSet` Element, das vier .NET-Typen definiert.

```
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

[Element „SelectionSet“ (Format)](./selectionset-element-format.md)

[Element „SelectionSets“ (Format)](./selectionsets-element-format.md)

[Types-Element (Format)](./types-element-for-selectionset-format.md)

[Schreiben einer Windows PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
