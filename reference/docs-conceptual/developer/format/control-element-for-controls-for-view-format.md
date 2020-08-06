---
title: Control-Element für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 13ea2f09aec7fea8e5460197f133b5f5219cd369
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783805"
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

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Name-Element für das Steuer Element für die Ansicht (Format)](./name-element-for-control-for-controls-for-view-format.md)|Erforderliches Element.<br /><br /> Gibt den Namen des Steuer Elements an.|
|[Element „CustomControl“ für Control für Controls für View (Format)](./customcontrol-element-for-control-for-controls-for-view-format.md)|Erforderliches Element.<br /><br /> Definiert das Steuerelement, das von dieser Ansicht verwendet wird.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
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
