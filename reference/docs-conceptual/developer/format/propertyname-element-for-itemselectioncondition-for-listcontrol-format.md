---
title: PropertyName-Element für itemselectioncondition für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 8bdbb05326f7ff5ccffa46215631a5c954080dc1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780864"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a>Element „PropertyName“ für ItemSeclectionCondition für ListControl (Format)

Gibt die .net-Eigenschaft an, die die Bedingung auslöst. Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Ansicht wird verwendet. Dieses Element wird beim Definieren einer Listenansicht verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element für ListControl (Format) ListItems-Element für ListEntry für ListControl (Format) ListItem-Element für ListItems für ListControl (Format) itemselectioncondition-Element für ListItem für ListControls propertyName-Element für itemselectioncondition für ListControl (Format)

## <a name="syntax"></a>Syntax

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und die übergeordneten Elemente des- `PropertyName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „ItemSelectionCondition“ für ListItem für ListControl (Format)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a>Textwert

Geben Sie den Namen der Eigenschaft an, deren Wert angezeigt wird.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element verwendet wird, können Sie das [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) -Element nicht angeben, wenn Sie die Auswahlbedingung definieren.

## <a name="see-also"></a>Weitere Informationen

[ScriptBlock-Element für itemselectioncondition für listicontrol (Format)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[Element „ItemSelectionCondition“ für ListItem für ListControl (Format)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
