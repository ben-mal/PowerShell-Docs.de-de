---
title: Selectioncondition-Element für entryselectedby für enumerableexpansion (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: d5858145e092dc962174a776889a4f62db366d71
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785335"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a>Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)

Definiert die Bedingung, die vorhanden sein muss, um die Auflistungs Objekte dieser Definition zu erweitern.

Configuration-Element (Format) DefaultSettings-Element (Format) enumerableweiterung-Element (Format) enumerableweiterung-Element (Format) entryselectedby-Element für enumerableexpansion (Format) selectioncondition-Element für entryselectedby für enumerableexpansion (Format)

## <a name="syntax"></a>Syntax

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionCondition` Elements beschrieben. Sie müssen ein einzelnes- `PropertyName` oder- `ScriptBlock` Element angeben. Das `SelectionSetName` -Element und das- `TypeName` Element sind optional. Sie können eines der beiden Elemente angeben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „PropertyName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|Optionales Element.<br /><br /> Gibt die .net-Eigenschaft an, die die Bedingung auslöst.|
|[Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|Optionales Element.<br /><br /> Gibt das Skript an, das die Bedingung auslöst.|
|[Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|Optionales Element.<br /><br /> Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.|
|[Element „TypeName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|Optionales Element.<br /><br /> Gibt einen .NET-Typ an, der die Bedingung auslöst.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „EntrySelectedBy“ für EnumerableExpansion (Format)](./entryselectedby-element-for-enumerableexpansion-format.md)|Definiert, welche .net-Auflistungs Objekte durch diese Definition erweitert werden.|

## <a name="remarks"></a>Bemerkungen

Für jede Definition muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.

Wenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:

- Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.

- Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.

Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Wiedergabe von Daten](./defining-conditions-for-displaying-data.md).

Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Wide View](./creating-a-wide-view.md).

## <a name="see-also"></a>Weitere Informationen

[Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
