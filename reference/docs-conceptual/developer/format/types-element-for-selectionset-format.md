---
title: Types-Element für SelectionSet (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 9978daefb3e97ab131774ca4dff633dde6b4dfbf
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772517"
---
# <a name="types-element-for-selectionset-format"></a>Element „Types“ für SelectionSet (Format)

Definiert die .NET-Objekte, die sich im Auswahl Satz befinden.

Configuration-Element (Format) selectionsets-Element (Format) SelectionSet-Element (Format) Types-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Types` Elements beschrieben. Es muss mindestens ein untergeordnetes Element vorhanden sein, es gibt jedoch keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die hinzugefügt werden können.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Typname-Element von Typen (Format)](./typename-element-for-types-format.md)|Erforderliches Element.<br /><br /> Gibt das .NET-Objekt an, das zum Auswahl Satz gehört.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „SelectionSet“ (Format)](./selectionset-element-format.md)|Definiert einen Satz von .NET-Objekten, auf die durch den Namen des Satzes verwiesen werden kann.|

## <a name="remarks"></a>Bemerkungen

Die von diesem Element definierten Objekte bilden einen Auswahl Satz, der von einer Ansicht, durch eine Definition einer Ansicht (Sichten können mehrere Definitionen aufweisen) oder durch Angeben einer Auswahlbedingung verwendet werden kann.  Weitere Informationen zu Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt ein- `SelectionSet` Element, das vier .NET-Typen definiert.

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

[Definieren von Objekt Sätzen](./defining-selection-sets.md)

[Element „SelectionSet“ (Format)](./selectionset-element-format.md)

[Typname-Element von Typen (Format)](./typename-element-for-types-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
