---
title: Customcontrolname-Element für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4e3102f12cd37fa72a2de1bf1db5d1f82db31222
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783737"
---
# <a name="customcontrolname-element-for-groupby-format"></a>Element „CustomControlName“ für GroupBy (Format)

Gibt den Namen eines benutzerdefinierten Steuer Elements an, das zum Anzeigen der neuen Gruppe verwendet wird. Dieses Element wird verwendet, wenn eine Tabelle, eine Liste, eine Breite oder eine benutzerdefinierte Steuerelement Ansicht definiert wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) customcontrolname-Element von GroupBy (Format)

## <a name="syntax"></a>Syntax

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und die übergeordneten Elemente des- `CustomControlName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „GroupBy“ für View (Format)](./groupby-element-for-view-format.md)|Definiert, wie Windows PowerShell eine neue Gruppe von Objekten anzeigt.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen des benutzerdefinierten Steuer Elements an, das verwendet wird, um eine neue Gruppe anzuzeigen.

## <a name="remarks"></a>Bemerkungen

Sie können allgemeine Steuerelemente erstellen, die von allen Ansichten einer Formatierungs Datei verwendet werden können, und Sie können Ansichts Steuerelemente erstellen, die von einer bestimmten Ansicht verwendet werden können. Die folgenden Elemente geben die Namen dieser benutzerdefinierten Steuerelemente an:

- [Element „Name“ für Control für Controls für Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

- [Element „Name“ für Control für Controls für View (Format)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>Weitere Informationen

[Element „GroupBy“ für View (Format)](./groupby-element-for-view-format.md)

[Element „Name“ für Control für Controls für Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[Element „Name“ für Control für Controls für View (Format)](./name-element-for-control-for-controls-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
