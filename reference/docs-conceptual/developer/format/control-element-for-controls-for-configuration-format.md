---
title: Control-Element für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 9447efac84cff3cc33468aeebc97a8bdd6137518
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783822"
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

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „CustomControl“ für Control für Controls für Configuration (Format)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|Erforderliches Element.<br /><br /> Definiert das Steuerelement.|
|[Name-Element für das Steuer Element für die Konfiguration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)|Erforderliches Element.<br /><br /> Gibt den Namen an, mit dem auf das Steuerelement verwiesen wird.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
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
