---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Control“ für Controls für Configuration (Format)
description: Element „Control“ für Controls für Configuration (Format)
ms.openlocfilehash: 43424de025cb89d81533e973abd7c39c09533747
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655651"
---
# <a name="control-element-for-controls-for-configuration-format"></a>Element „Control“ für Controls für Configuration (Format)

Definiert ein gängiges Steuerelement, das von allen Ansichten der Formatierungs Datei und dem Namen, der zum Verweisen auf das Steuerelement verwendet wird, verwendet werden kann.

Configuration-Element (Format) Controls-Element des Configuration (Format)-Steuer Elements für Steuerelemente für die Konfiguration (Format)

## <a name="syntax"></a>Syntax

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete-Element für das- `Control` Element beschrieben. Sie müssen nur eines der einzelnen untergeordneten Elemente angeben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomControl“ für Control für Controls für Configuration (Format)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|Erforderliches Element.<br /><br /> Definiert das Steuerelement.|
|[Name-Element für das Steuer Element für die Konfiguration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)|Erforderliches Element.<br /><br /> Gibt den Namen an, mit dem auf das Steuerelement verwiesen wird.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Controls-Element der Konfiguration (Format)](./controls-element-for-configuration-format.md)|Definiert die allgemeinen Steuerelemente, die von allen Ansichten der Formatierungs Datei oder von anderen Steuerelementen verwendet werden können.|

## <a name="remarks"></a>Bemerkungen

Auf den Namen, den dieses Steuerelement erhält, kann in den folgenden Elementen verwiesen werden:

- [ExpressionBinding-Element für customItem (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [GroupBy-Element für Ansicht (Format)](./groupby-element-for-view-format.md)

## <a name="see-also"></a>Weitere Informationen

[Controls-Element der Konfiguration (Format)](./controls-element-for-configuration-format.md)

[CustomControl-Element für das Steuerelement für die Konfiguration (Format)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[ExpressionBinding-Element für customItem (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[GroupBy-Element für Ansicht (Format)](./groupby-element-for-view-format.md)

[Element „Name“ für Control für Controls für Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
