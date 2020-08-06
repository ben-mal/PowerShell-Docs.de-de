---
title: PropertyName-Element für ListItem für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 9ee466d7f73e53b129f8d46f49a21549683bb32c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780830"
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
