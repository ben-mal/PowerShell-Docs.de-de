---
title: ScriptBlock-Element für selectioncondition für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e5f4295a989307cb6ffb655c2c39596f3d1ea806
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785420"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-view-format"></a>Element „ScriptBlock“ für SelectionCondition für Controls für View (Format)

Gibt das Skript an, das die Bedingung auslöst. Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Definition wird verwendet. Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.

Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelement Steuerelement (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Control für Steuerelemente für View (Format) customentries-Element für CustomControl für Steuerelemente für View (Format) customentry-Element für customentries for Controls for View (Format) entryselectedby-Element für customentry für Steuerelemente für das View (Format) selectioncondition-Element für entryselectedby für Steuerelemente für View (Format) ScriptBlock-Element für selectioncondition für Steuerelemente für View (Format)

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
|[Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie das auszuwertende Skript an.

## <a name="remarks"></a>Bemerkungen

Die Auswahlbedingung muss mindestens ein Skript oder einen Eigenschaftsnamen angeben, um ausgewertet zu werden, aber nicht beides. Weitere Informationen zur Verwendung von Auswahl Bedingungen finden Sie unter Definieren von [Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Weitere Informationen

[Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
