---
title: Selectioncondition-Element für entryselectedby für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4a829f9daef22c4b3fd6b21dfb3af2f8539bdeb3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780286"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a>Element „SelectionCondition“ für EntrySelectedBy für TableControl (Format)

Definiert die Bedingung, die für die Verwendung in dieser Definition der Tabellenansicht vorhanden sein muss. Es gibt keine Beschränkung für die Anzahl der Auswahl Bedingungen, die für eine Tabellendefinition angegeben werden können.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) entryselectedby-Element für tablerowentry (Format) selectioncondition-Element für entryselectedby für tablerowentry (Format)

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

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des selectioncondition-Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „PropertyName“ für SelectionCondition für EntrySelectedBy für TableRowEntry (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|Optionales Element.<br /><br /> Gibt die .net-Eigenschaft an, die die Bedingung auslöst.|
|[ScriptBlock-Element für selectioncondition für entryselectedby für tablerowentry (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|Optionales Element.<br /><br /> Gibt das Skript an, das die Bedingung auslöst.|
|[Selectionsetname-Element für selectioncondition für entryselectedby für tablerowentry (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|Optionales Element.<br /><br /> Gibt den Satz von .NET-Typen an, die die Bedingung auslöst.|
|[Typname-Element für selectioncondition für entryselectedby für tablerowentry (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|Optionales Element.<br /><br /> Gibt einen .NET-Typ an, der die Bedingung auslöst.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Entryselectedby-Element für tablerowentry (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Definiert die .NET-Typen, die diesen Tabelleneintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.|

## <a name="remarks"></a>Bemerkungen

Für jeden Listeneintrag muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.

Wenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:

- Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.

- Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.

Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter Definieren von Bedingungen für den Fall, [dass ein Ansichts Eintrag oder Element verwendet wird](./defining-conditions-for-displaying-data.md).

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md)

[Entryselectedby-Element (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Element „PropertyName“ für SelectionCondition für EntrySelectedBy für TableRowEntry (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[ScriptBlock-Element für selectioncondition für entryselectedby für tablerowentry (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Selectionsetname-Element für selectioncondition für entryselectedby für tablerowentry (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Typname-Element für selectioncondition für entryselectedby für tablerowentry (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei](./writing-a-powershell-formatting-file.md)
