---
title: Selectionsetname-Element für selectioncondition für entryselectedby für enumerableweiterung (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e18c74bb95c658f2c3e7b7454628f78d523f7609
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787494"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a>Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)

Gibt den Satz von .NET-Typen an, die die Bedingung auslöst. Wenn einer der Typen in diesem Satz vorhanden ist, wird die Bedingung erfüllt.

Configuration-Element DefaultSettings-Element (Format) enumerableweiterung-Element (Format) enumerableerweiterungen-Element (Format) entryselectedby-Element für enumerableexpansion (Format) selectioncondition-Element für entryselectedby für enumerableweiterung (Format) selectionsetname-Element für selectioncondition für entryselectedby für enumerableexpansion (Format)

## <a name="syntax"></a>Syntax

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|Definiert die Bedingung, die vorhanden sein muss, um die Auflistungs Objekte dieser Definition zu erweitern.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen des Auswahl Satzes an.

## <a name="remarks"></a>Bemerkungen

Die Auswahlbedingung kann einen Auswahl Satz oder einen .NET-Typ angeben, kann jedoch nicht beides angeben. Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).

Auswahl Sätze sind allgemeine Gruppen von .NET-Objekten, die von jeder Sicht verwendet werden können, die von der Formatierungs Datei definiert wird. Weitere Informationen zum Erstellen und referenzieren von Auswahl Sätzen finden Sie unter [Definieren von Auswahl Sätzen](./defining-selection-sets.md).

## <a name="see-also"></a>Weitere Informationen

[Definieren von Auswahlgruppen](./defining-selection-sets.md)

[Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
