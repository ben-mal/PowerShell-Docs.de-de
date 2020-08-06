---
title: ScriptBlock-Element für selectioncondition für entryselectedby für enumerableweiterung (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 71fd969fd3e5c0a4e39762c9a026982a8ca2a9d1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785369"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a>Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)

Gibt das Skript an, das die Bedingung auslöst.

Configuration-Element (Format) DefaultSettings-Element (Format) enumerableweiterung-Element (Format) enumerableweiterung-Element (Format) entryselectedby-Element für enumerableexpansion (Format) selectioncondition-Element für entryselectedby für enumerableweiterung (Format) ScriptBlock-Element für selectioncondition für entryselectedby für enumerableexpansion (Format)

## <a name="syntax"></a>Syntax

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|Definiert die Bedingung, die vorhanden sein muss, um die Auflistungs Objekte dieser Definition zu erweitern.|

## <a name="text-value"></a>Textwert

Geben Sie das auszuwertende Skript an.

## <a name="remarks"></a>Bemerkungen

Die Auswahlbedingung muss mindestens ein Skript oder einen Eigenschaftsnamen angeben, der ausgewertet werden soll, kann jedoch nicht beides angeben. Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Weitere Informationen

[Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md)

[Element „PropertyName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
