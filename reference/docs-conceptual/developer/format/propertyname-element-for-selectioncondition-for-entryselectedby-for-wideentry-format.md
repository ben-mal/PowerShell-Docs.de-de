---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)
description: Element „PropertyName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)
ms.openlocfilehash: bda34b0c1e97fb85536132bedcec3986072801b7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665701"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a>Element „PropertyName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)

Gibt die .net-Eigenschaft an, die die Bedingung auslöst. Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Definition wird verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format) selectioncondition-Element für entryselectedby für wideentry (Format) propertyName-Element für selectioncondition für entryselectedby für wideentry (Format)

## <a name="syntax"></a>Syntax

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

```csharp

```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Selectioncondition-Element für entryselectedby für wideentry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|Definiert die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen der .net-Eigenschaft an.

## <a name="remarks"></a>Bemerkungen

Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder ein auszuwertende Skript angeben, kann jedoch nicht beides angeben. Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).

Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Wide View](./creating-a-wide-view.md).

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md)

[ScriptBlock-Element für selectioncondition für entryselectedby für wideentry (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[Selectioncondition-Element für entryselectedby für wideentry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
