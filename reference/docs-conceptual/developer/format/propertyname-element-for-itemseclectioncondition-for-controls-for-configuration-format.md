---
title: PropertyName-Element für itemabclectioncondition für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 0e304af1dbe816753d6dcd1dd8149f950f2a0941
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785590"
---
# <a name="propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a>Element „PropertyName“ für ItemSeclectionCondition für Controls für Configuration (Format)

Gibt die .net-Eigenschaft an, die die Bedingung auslöst. Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet. Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.

Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl for Controls for Configuration (Format) customItem-Element für customentry für Steuerelemente für das konfigurationsexpressionbinding-Element für customItem for Controls for Configuration (Format) itemselectioncondition-Element für ExpressionBinding for Controls for Configuration (Format) propertyName-Element für itemabclectioncondition for Controls for Configuration (Format)

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
|[Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen der .net-Eigenschaft an, die die Bedingung auslöst.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element verwendet wird, können Sie das [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) -Element nicht angeben, wenn Sie die Auswahlbedingung definieren.

## <a name="see-also"></a>Weitere Informationen

[Element „ScriptBlock“ für ItemSeclectionCondition für Controls für Configuration (Format)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
