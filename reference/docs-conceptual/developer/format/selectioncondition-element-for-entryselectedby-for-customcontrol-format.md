---
title: Selectioncondition-Element für entryselectedby für CustomControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 52858dba5c7a5222b5410835f3374546ce8b88a2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785352"
---
# <a name="selectioncondition-element-for-entryselectedby-for-customcontrol-format"></a>Element „SelectionCondition“ für EntrySelectedBy für CustomControl (Format)

Definiert eine Bedingung, die vorhanden sein muss, damit eine Steuerelement Definition verwendet werden muss. Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.

Konfigurationselement (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element für View (Format) customentries-Element für CustomControl for View (Format) customentry-Element für customentries für CustomControl for View (Format) customItem-Element für customentry für CustomControl für das View (Format) entryselectedby-Element für customentry für CustomControl für View (Format) selectioncondition-Element für entryselectedby für CustomControl for View (Format)

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

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „PropertyName“ für SelectionCondition für CustomControl für View (Format)](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Gibt eine .net-Eigenschaft an, die die Bedingung auslöst.|
|[Element „ScriptBlock“ für SelectionCondition für CustomControl für View (Format)](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Gibt das Skript an, das die Bedingung auslöst.|
|[Selectionsetname-Element für selectioncondition für benutzerdefiniertes Steuer Element für Ansicht (Format)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.|
|[Element „TypeName“ für SelectionCondition für CustomControl für View (Format)](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Gibt einen .NET-Typ an, der die Bedingung auslöst.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „EntrySelectedBy“ für CustomEntry für CustomControl für View (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.|

## <a name="remarks"></a>Bemerkungen

Wenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:

- Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.

- Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.

Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Weitere Informationen

[Element „PropertyName“ für SelectionCondition für CustomControl für View (Format)](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Element „ScriptBlock“ für SelectionCondition für CustomControl für View (Format)](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Selectionsetname-Element für selectioncondition für benutzerdefiniertes Steuer Element für Ansicht (Format)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Element „TypeName“ für SelectionCondition für CustomControl für View (Format)](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Element „EntrySelectedBy“ für CustomEntry für CustomControl für View (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
