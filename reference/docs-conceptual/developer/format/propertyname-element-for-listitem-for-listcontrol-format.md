---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für ListItem für ListControl (Format)
description: Element „PropertyName“ für ListItem für ListControl (Format)
ms.openlocfilehash: 30cd48f9549e1a091776cd5f8395e1a71314ea1b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665973"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a>Element „PropertyName“ für ListItem für ListControl (Format)

Gibt die .net-Eigenschaft an, deren Wert in der Liste angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) ListItems-Element (Format) ListItem-Element (Format) propertyName-Element für ListItem (Format)

## <a name="syntax"></a>Syntax

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[ListItem-Element (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Definiert die Eigenschaft oder das Skript, dessen Wert in der Zeile der Listenansicht angezeigt wird.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen der Eigenschaft an, deren Wert angezeigt wird.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element angegeben ist, können Sie das [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) -Element nicht angeben.

Zusätzlich zum Anzeigen des Eigenschafts Werts können Sie auch eine Bezeichnung für den Wert oder eine Format Zeichenfolge angeben, die zum Ändern der Anzeige des Werts verwendet werden kann. Weitere Informationen zum Angeben von Daten in einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie die Bezeichnung und die Eigenschaft angegeben werden, deren Wert angezeigt wird.

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a>Weitere Informationen

[Element „ScriptBlock“ für ListItem für ListControl (Format)](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[Erstellen einer Listenansicht](./creating-a-list-view.md)

[ListItem-Element für ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
