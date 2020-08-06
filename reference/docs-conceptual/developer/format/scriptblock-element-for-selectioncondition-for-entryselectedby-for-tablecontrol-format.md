---
title: ScriptBlock-Element für selectioncondition für entryselectedby für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: a23d3515749393e9f5a2053634a44d1a817ebf38
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783448"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a>Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für TableControl (Format)

Gibt den Skriptblock an, der die Bedingung auslöst. Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und der Tabelleneintrag wird verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) entryselectedby-Element für tablerowentry (Format) selectioncondition-Element für entryselectedby für tablerowentry (Format) ScriptBlock-Element für selectioncondition für entryselectedby für tablerowentry (Format)

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

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Selectioncondition-Element für entryselectedby für tablerowentry (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|Definiert die Bedingung, die für die Verwendung dieses Tabellen Eintrags vorhanden sein muss.|

## <a name="text-value"></a>Textwert

Geben Sie das auszuwertende Skript an.

## <a name="remarks"></a>Bemerkungen

In der Auswahlbedingung muss mindestens ein Skriptblock oder ein Eigenschaftsname angegeben werden, es können jedoch nicht beide angegeben werden. Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter Definieren von Bedingungen für den Fall, [dass ein Ansichts Eintrag oder Element verwendet wird](./defining-conditions-for-displaying-data.md).

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md)

[Element „PropertyName“ für SelectionCondition für EntrySelectedBy für TableRowEntry (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[Selectioncondition-Element für entryselectedby für tablerowentry (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
