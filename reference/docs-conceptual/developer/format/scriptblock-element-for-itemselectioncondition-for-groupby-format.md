---
title: ScriptBlock-Element für itemselectioncondition für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 7738b180f328c7360275058cdb9dea01df6ea285
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787647"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a>Element „ScriptBlock“ für ItemSeclectionCondition für GroupBy (Format)

Gibt das Skript an, das die Bedingung auslöst. Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet. Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format) ExpressionBinding-Element für customItem für GroupBy (Format) itemselectioncondition-Element für ExpressionBinding für GroupBy (Format) ScriptBlock-Element für itemselectioncondition für GroupBy (Format)

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
|[Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie das auszuwertende Skript an.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element verwendet wird, können Sie beim Definieren der Auswahlbedingung nicht das [propertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) -Element angeben.

## <a name="see-also"></a>Weitere Informationen

[Element „ItemSelectionCondition“ für ExpressionBinding für GroupBy (Format)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[Element „PropertyName“ für ItemSeclectionCondition für GroupBy (Format)](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
