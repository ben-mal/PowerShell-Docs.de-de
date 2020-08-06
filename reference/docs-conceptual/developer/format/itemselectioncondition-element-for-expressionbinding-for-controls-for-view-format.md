---
title: Itemselectioncondition-Element für ExpressionBinding für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e8e3ea64fd947fbb2b98c410ac08533f386c9505
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781204"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a>Element „ItemSelectionCondition“ für ExpressionBinding für Controls für View (Format)

Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss. Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.

Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelemente Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelement für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für Steuerelemente für das View (Format) customItem-Element für customentry für Steuerelemente für das View (Format) ExpressionBinding-Element für customItem for Controls for View (Format) itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)

## <a name="syntax"></a>Syntax

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ItemSelectionCondition` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Gibt die .net-Eigenschaft an, die die Bedingung auslöst.|
|[Element „ScriptBlock“ für ItemSeclectionCondition für Controls für View (Format)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Gibt das Skript an, das die Bedingung auslöst.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „ExpressionBinding“ für CustomItem für Controls für View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|Definiert die Daten, die vom-Steuerelement angezeigt werden.|

## <a name="remarks"></a>Bemerkungen

Sie können einen Eigenschaftsnamen oder ein Skript für diese Bedingung angeben, aber nicht beides angeben.

## <a name="see-also"></a>Weitere Informationen

[Element „PropertyName“ für ItemSeclectionCondition für Controls für View (Format)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Element „ScriptBlock“ für ItemSeclectionCondition für Controls für View (Format)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Element „ExpressionBinding“ für CustomItem für Controls für View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
