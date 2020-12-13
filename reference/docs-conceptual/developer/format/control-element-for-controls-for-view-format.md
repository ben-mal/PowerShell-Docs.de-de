---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Control“ für Controls für View (Format)
description: Element „Control“ für Controls für View (Format)
ms.openlocfilehash: c48b8b7ecaebfde5e6ed2123b837d92561551766
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668081"
---
# <a name="control-element-for-controls-for-view--format"></a>Element „Control“ für Controls für View (Format)

Definiert ein Steuerelement, das von der Ansicht verwendet werden kann, und den Namen, der verwendet wird, um auf das Steuerelement zu verweisen.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) steuert Element (Format) Steuerelement für Steuerelemente für Ansicht (Format)

## <a name="syntax"></a>Syntax

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Control` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Name-Element für das Steuer Element für die Ansicht (Format)](./name-element-for-control-for-controls-for-view-format.md)|Erforderliches Element.<br /><br /> Gibt den Namen des Steuer Elements an.|
|[Element „CustomControl“ für Control für Controls für View (Format)](./customcontrol-element-for-control-for-controls-for-view-format.md)|Erforderliches Element.<br /><br /> Definiert das Steuerelement, das von dieser Ansicht verwendet wird.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Controls-Element (Format)](./controls-element-for-view-format.md)|Definiert die Sicht Steuerelemente, die von einer bestimmten Ansicht verwendet werden können.|

## <a name="remarks"></a>Bemerkungen

Dieses Steuerelement kann durch die folgenden Elemente angegeben werden:

- [Element „CustomControlName“ für ExpressionBinding für Controls für View (Format)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [Element „CustomControlName“ für ExpressionBinding für CustomControl für View (Format)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [Element „CustomControlName“ für GroupBy (Format)](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a>Weitere Informationen

[Element „CustomControl“ für Control für Controls für View (Format)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[Element „CustomControlName“ für ExpressionBinding für Controls für View (Format)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[Element „CustomControlName“ für ExpressionBinding für CustomControl für View (Format)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Controls-Element (Format)](./controls-element-for-view-format.md)

[Element „Name“ für Control für Controls für View (Format)](./name-element-for-control-for-controls-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
