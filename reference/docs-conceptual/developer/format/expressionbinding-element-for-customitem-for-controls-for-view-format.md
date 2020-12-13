---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ExpressionBinding“ für CustomItem für Controls für View (Format)
description: Element „ExpressionBinding“ für CustomItem für Controls für View (Format)
ms.openlocfilehash: da87bb26d21dcb051871e67997cc3fba7ce73c74
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649898"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a>Element „ExpressionBinding“ für CustomItem für Controls für View (Format)

Definiert die Daten, die vom-Steuerelement angezeigt werden. Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.

Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) steuert Element (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelement für Steuerelemente für Ansicht (Format) customentries-Element für customControl for View (Format) customentry-Element für customentries für Steuerelemente für View (Format) customItem-Element für customentry für Steuerelemente für Ansicht (Format) ExpressionBinding-Element für customItem für Steuerelemente für Ansicht (Format)

## <a name="syntax"></a>Syntax

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ExpressionBinding` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`CustomControl Element`|Optionales Element.<br /><br /> Definiert ein Steuerelement, das von diesem Steuerelement verwendet wird.|
|[Element „CustomControlName“ für ExpressionBinding für Controls für View (Format)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an.|
|[Element „EnumerateCollection“ für ExpressionBinding für Controls für View (Format)](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Gibt an, dass die Elemente der Auflistungen angezeigt werden.|
|[Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.|
|[Element „PropertyName“ für ExpressionBinding für Controls für View (Format)](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Gibt die .net-Eigenschaft an, deren Wert vom-Steuerelement angezeigt wird.|
|[Element „ScriptBlock“ für ExpressionBinding für Controls für View (Format)](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Gibt das Skript an, dessen Wert vom-Steuerelement angezeigt wird.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomItem“ für CustomEntry für Controls für View (Format)](./customitem-element-for-customentry-for-controls-for-view-format.md)|Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.|

## <a name="remarks"></a>Bemerkungen

## <a name="see-also"></a>Weitere Informationen

[Element „CustomItem“ für CustomEntry für Controls für View (Format)](./customitem-element-for-customentry-for-controls-for-view-format.md)

[Element „CustomControlName“ für ExpressionBinding für Controls für View (Format)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[Element „EnumerateCollection“ für ExpressionBinding für Controls für View (Format)](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[Itemselectioncondition-Element von ExpressionBinding für Steuerelemente für View (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[Element „PropertyName“ für ExpressionBinding für Controls für View (Format)](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[Element „ScriptBlock“ für ExpressionBinding für Controls für View (Format)](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
