---
title: PropertyName-Element für itemselectioncondition für CustomControl für View (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 0131fa86be4be4daec1d9d24b50397fb8529f050
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785573"
---
# <a name="propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a>Element „PropertyName“ für ItemSeclectionCondition für CustomControl für View (Format)

Gibt die .net-Eigenschaft an, die die Bedingung auslöst. Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet. Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) customItem-Element für customentry für die Ansicht (Format) ExpressionBinding-Element für customItem für CustomControl für View (Format) itemselectioncondition-Element für Ausdrucks Bindung für CustomControl für View (Format) propertyName-Element für itemselectioncondition für CustomControl for View (Format

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
|[Itemselectioncondition-Element für die Ausdrucks Bindung für "CustomControl" für "View" (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen der .net-Eigenschaft an, die die Bedingung auslöst.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element verwendet wird, können Sie das [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) -Element nicht angeben, wenn Sie die Auswahlbedingung definieren.

## <a name="see-also"></a>Weitere Informationen

[Element „ScriptBlock“ für ItemSeclectionCondition für CustomControl für View (Format)](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[Itemselectioncondition-Element für die Ausdrucks Bindung für "CustomControl" für "View" (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
