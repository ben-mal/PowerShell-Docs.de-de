---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Label“ für ListItem für ListControl (Format)
description: Element „Label“ für ListItem für ListControl (Format)
ms.openlocfilehash: 01ff34c4129abe2c76a0a21794e756b77bff12bf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666653"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a>Element „Label“ für ListItem für ListControl (Format)

Gibt die Bezeichnung an, die auf der linken Seite des Eigenschafts-oder Skript Werts in der Zeile angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListControl (Format) ListItems für ListEntry für das ListControl-Element (Format) ListItem-Element für ListItems für ListControl (Format) Label-Element für ListItem für ListControl (Format)

## <a name="syntax"></a>Syntax

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Label` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „ListItem“ für ListItems für ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Definiert die Eigenschaft oder das Skript, dessen Wert in einer Zeile der Listenansicht angezeigt wird.|

## <a name="text-value"></a>Textwert

Geben Sie die Bezeichnung an, die auf der linken Seite des Eigenschafts-oder Skript Werts angezeigt werden soll.

## <a name="remarks"></a>Bemerkungen

Wenn keine Bezeichnung angegeben ist, wird der Name der Eigenschaft oder des Skripts angezeigt. Weitere Informationen zum Verwenden von Bezeichnungen in einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie einer Zeile eine Bezeichnung hinzugefügt wird.

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Listenansicht](./creating-a-list-view.md)

[ListItem-Element (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
