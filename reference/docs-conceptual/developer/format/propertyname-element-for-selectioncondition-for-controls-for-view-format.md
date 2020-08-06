---
title: PropertyName-Element für selectioncondition für Steuerelemente für View (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 251fc129896cfa4a6255330e23854b014675ac5f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780813"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-view-format"></a>Element „PropertyName“ für SelectionCondition für Controls für View (Format)

Gibt die .net-Eigenschaft an, die die Bedingung auslöst. Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und der Eintrag wird verwendet. Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.

Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelement Steuerelement (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Control für Steuerelemente für View (Format) customentries-Element für CustomControl für Steuerelemente für View (Format) customentry-Element für customentries for Controls for View (Format) entryselectedby-Element für customentry für Steuerelemente für das View (Format) selectioncondition-Element für entryselectedby für Steuerelemente für View (Format) propertyName-Element für selectioncondition für Steuerelemente für View (Format)

## <a name="syntax"></a>Syntax

```xml
<PropertyName>.NetTypeProperty</PropertyName>
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
|[Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen der .net-Eigenschaft an.

## <a name="remarks"></a>Bemerkungen

Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder ein Skript angeben, kann jedoch nicht beides angeben. Weitere Informationen zur Verwendung von Auswahl Bedingungen finden Sie unter Definieren von [Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Weitere Informationen

[Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
