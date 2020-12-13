---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für ListControl (Format)
description: Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für ListControl (Format)
ms.openlocfilehash: ec7691358d0ff3758411317a349221e1704a1895
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659908"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für ListControl (Format)

Gibt das Skript an, das die Bedingung auslöst. Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und der Listeneintrag wird verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) entryselectedby-Element für ListEntry (Format) selectioncondition-Element für entryselectedby für ListEntry (Format) ScriptBlock-Element für selectioncondition für entryselectedby für ListEntry (Format)

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
|[Selectioncondition-Element für entryselectedby für ListEntry (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Definiert die Bedingung, die für die Verwendung dieses Listen Eintrags vorhanden sein muss.|

## <a name="text-value"></a>Textwert

Geben Sie das auszuwertende Skript an.

## <a name="remarks"></a>Bemerkungen

Die Auswahlbedingung muss mindestens ein Skript oder einen Eigenschaftsnamen angeben, um ausgewertet zu werden, aber nicht beides. (Weitere Informationen dazu, wie Auswahl Bedingungen verwendet werden können, finden Sie unter [Definieren von Bedingungen für die Verwendung eines Ansichts Eintrags oder eines Elements](./defining-conditions-for-displaying-data.md).)

Weitere Informationen zu den anderen Komponenten einer Listenansicht finden Sie in der [Listenansicht](./creating-a-list-view.md).

## <a name="see-also"></a>Weitere Informationen

[ListEntry-Element (Format)](./listentry-element-for-listcontrol-format.md)

[PropertyName-Element für selectioncondition für entryselectedby für ListEntry (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[Selectioncondition-Element für entryselectedby für ListEntry (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[Listenansicht](./creating-a-list-view.md)

[Definieren von Bedingungen für die Verwendung eines Ansichts Eintrags oder-Elements](./defining-conditions-for-displaying-data.md)

[Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei](./writing-a-powershell-formatting-file.md)
