---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)
description: Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)
ms.openlocfilehash: ce00cdf868a3075875043aeb59f2cb8a17d049a9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645785"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a>Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)

Definiert eine Bedingung, die vorhanden sein muss, damit eine allgemeine Steuerelement Definition verwendet werden muss. Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.

Konfigurationselement (Format) Controls-Element des Configuration (Format)-Steuer Elements für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Steuerelemente für Konfiguration (Format) customentry-Element für CustomControl für Steuerelemente für das Configuration (Format) entryselectedby-Element für customentry for Controls for Configuration (Format) selectioncondition-Element für entryselectedby für customentry for Configuration (Format)

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

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionCondition` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „PropertyName“ für SelectionCondition für Controls für Configuration (Format)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Gibt eine .net-Eigenschaft an, die die Bedingung auslöst.|
|[Element „ScriptBlock“ für SelectionCondition für Controls für Configuration (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Gibt das Skript an, das die Bedingung auslöst.|
|[Element „SelectionSetName“ für SelectionCondition für Controls für Configuration (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.|
|[Element „TypeName“ für SelectionCondition für Controls für Configuration (Format)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Gibt einen .NET-Typ an, der die Bedingung auslöst.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|Definiert die .NET-Typen, die diesen Eintrag der allgemeinen Steuerelement Definition verwenden.|

## <a name="remarks"></a>Bemerkungen

Die folgenden Richtlinien müssen befolgt werden, wenn eine Auswahlbedingung definiert wird:

- Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.

- Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.

Weitere Informationen zur Verwendung von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Weitere Informationen

[Element „PropertyName“ für SelectionCondition für Controls für Configuration (Format)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Element „ScriptBlock“ für SelectionCondition für Controls für Configuration (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Element „SelectionSetName“ für SelectionCondition für Controls für Configuration (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Element „TypeName“ für SelectionCondition für Controls für Configuration (Format)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei](./writing-a-powershell-formatting-file.md)
