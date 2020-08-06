---
title: ScriptBlock-Element für itemselectioncondition für Steuerelemente für View (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 74b3e23005f595c4c550320849cac5b196e9d479
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787664"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a>Element „ScriptBlock“ für ItemSeclectionCondition für Controls für View (Format)

Gibt das Skript an, das die Bedingung auslöst. Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet. Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.

Konfigurationselement (Format) viewdefinitions-Element (Format) View Element (Format) steuert Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für Steuerelemente für Ansicht (Format) customItem-Element für customentry für Steuerelemente für das View (Format) ExpressionBinding-Element für customItem für Steuerelemente für View (Format) itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format) ScriptBlock-Element für itemselectioncondition für Steuerelemente für View (Format)

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
|[Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie das auszuwertende Skript an.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element verwendet wird, können Sie beim Definieren der Auswahlbedingung nicht das [propertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) -Element angeben.

## <a name="see-also"></a>Weitere Informationen

[Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
