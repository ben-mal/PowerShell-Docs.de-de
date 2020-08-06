---
title: Selectioncondition-Element für entryselectedby für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 1c14b2638249bdbfe25f7a96e917d66ea10ed239
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787579"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a>Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)

Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss. Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.

Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) steuert Element (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelemente für das View (Format) customentries-Element für CustomControl für Steuerelemente View (Format) customentry-Element für customentries für Steuerelemente für das View (Format) entryselectedby-Element für customentry für Steuerelemente für View (Format) selectioncondition-Element für entryselectedby für Steuerelemente für View (Format)

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
|[Element „PropertyName“ für SelectionCondition für Controls für View (Format)](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Gibt eine .net-Eigenschaft an, die die Bedingung auslöst.|
|[Element „ScriptBlock“ für SelectionCondition für Controls für View (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Gibt das Skript an, das die Bedingung auslöst.|
|[Element „SelectionSetName“ für SelectionCondition für Controls für View (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.|
|[Element „TypeName“ für SelectionCondition für Controls für View (Format)](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Gibt einen .NET-Typ an, der die Bedingung auslöst.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „EntrySelectedBy“ für CustomEntry für Controls für View (Format)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.|

## <a name="remarks"></a>Bemerkungen

Wenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:

- Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.

- Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.

Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Weitere Informationen

[Element „PropertyName“ für SelectionCondition für Controls für View (Format)](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[Element „ScriptBlock“ für SelectionCondition für Controls für View (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[Element „SelectionSetName“ für SelectionCondition für Controls für View (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[Element „TypeName“ für SelectionCondition für Controls für View (Format)](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[Element „EntrySelectedBy“ für CustomEntry für Controls für View (Format)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
