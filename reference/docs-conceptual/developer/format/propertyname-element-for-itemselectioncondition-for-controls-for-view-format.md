---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)
description: Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)
ms.openlocfilehash: 9fb7a21e19338dbf59dab14291e1b02736835040
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645816"
---
# <a name="propertyname-element-for-itemselectioncondition-for-controls-for-view-format"></a>Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)

Gibt die .net-Eigenschaft an, die die Bedingung auslöst. Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet. Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.

Konfigurationselement (Format) viewdefinitions-Element (Format) View Element (Format) steuert Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für Steuerelemente für Ansicht (Format) customItem-Element für customentry für Steuerelemente für das View (Format) ExpressionBinding-Element für customItem für Steuerelemente für View (Format) itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format) propertyName-Element für itemselectioncondition für Steuerelemente für View (Format)

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
|[Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen der .net-Eigenschaft an, die die Bedingung auslöst.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element verwendet wird, können Sie das [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) -Element nicht angeben, wenn Sie die Auswahlbedingung definieren.

## <a name="see-also"></a>Weitere Informationen

[Element „ScriptBlock“ für ItemSeclectionCondition für Controls für View (Format)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
