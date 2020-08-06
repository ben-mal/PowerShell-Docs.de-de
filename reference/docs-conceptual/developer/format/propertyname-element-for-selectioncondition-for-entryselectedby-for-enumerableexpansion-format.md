---
title: PropertyName-Element für selectioncondition für entryselectedby für enumerableweiterung (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: c0081cb724ccaf1c04241aafa177880d7c0e5dbe
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783465"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a>Element „PropertyName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)

Gibt die .net-Eigenschaft an, die die Bedingung auslöst. Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Definition wird verwendet.

Configuration-Element (Format) DefaultSettings-Element (Format) enumerableweiterung-Element (Format) enumerableweiterung-Element (Format) entryselectedby-Element für enumerableexpansion (Format) selectioncondition-Element für entryselectedby für enumerableweiterung (Format) propertyName-Element für selectioncondition für entryselectedby für enumerableexpansion (Format)

## <a name="syntax"></a>Syntax

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|Definiert die Bedingung, die vorhanden sein muss, um die Auflistungs Objekte dieser Definition zu erweitern.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen der .net-Eigenschaft an.

## <a name="remarks"></a>Bemerkungen

Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder ein auszuwertende Skript angeben, kann jedoch nicht beides angeben. Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Weitere Informationen

[Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md)

[Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
