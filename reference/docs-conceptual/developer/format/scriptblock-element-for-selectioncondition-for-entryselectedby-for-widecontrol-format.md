---
title: ScriptBlock-Element für selectioncondition für entryselectedby für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: c8f2223d4a1217786a930eb82390c24b81d2f72e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787613"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a>Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für WideControl (Format)

Gibt das Skript an, das die Bedingung auslöst. Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Breite Eingabe Definition wird verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format) selectioncondition-Element für entryselectedby für wideentry (Format) ScriptBlock-Element für selectioncondition für entryselectedby für wideentry (Format)

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
|[Selectioncondition-Element für entryselectedby für wideentry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|Definiert die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie das auszuwertende Skript an.

## <a name="remarks"></a>Bemerkungen

Die Auswahlbedingung muss mindestens ein Skript oder einen Eigenschaftsnamen angeben, der ausgewertet werden soll, kann jedoch nicht beides angeben. Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).

Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Wide View](./creating-a-wide-view.md).

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md)

[Element „PropertyName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[Selectioncondition-Element für entryselectedby für wideentry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
