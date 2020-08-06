---
title: Customcontrolname-Element für ExpressionBinding für CustomControl für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 6f1ffca045b7efcecb4dce4e788a8c508fa6ef08
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783754"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a>Element „CustomControlName“ für ExpressionBinding für CustomControl für View (Format)

Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an. Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.

Konfigurationselement (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element für View (Format) customentries-Element für CustomControl for View (Format) customentry-Element für customentries for View (Format) customItem-Element für customentry für das View (Format) ExpressionBinding-Element für das customItem (Format) customcontrolname-Element für die Ausdrucks Bindung für customItem (Format)

## <a name="syntax"></a>Syntax

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomControlName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[ExpressionBinding-Element für customItem (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|Definiert die Daten, die vom-Steuerelement angezeigt werden.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen des Steuer Elements an.

## <a name="remarks"></a>Bemerkungen

Sie können allgemeine Steuerelemente erstellen, die von allen Ansichten einer Formatierungs Datei verwendet werden können, und Sie können Ansichts Steuerelemente erstellen, die von einer bestimmten Ansicht verwendet werden können. Die Namen dieser Steuerelemente werden durch die folgenden Elemente angegeben.

- [Element „Name“ für Control für Controls für Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

- [Element „Name“ für Control für Controls für View (Format)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>Weitere Informationen

[Element „Name“ für Control für Controls für Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[Element „Name“ für Control für Controls für View (Format)](./name-element-for-control-for-controls-for-view-format.md)

[ExpressionBinding-Element für customItem (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
