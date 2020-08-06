---
title: ScriptBlock-Element für ListItem für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 249d3e36b4246b7baa410815122f8e30340f1862
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785454"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a>Element „ScriptBlock“ für ListItem für ListControl (Format)

Gibt das Skript an, dessen Wert in der Zeile angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListEntries für ListControl (Format) ListItems-Element für ListEntry für ListControl (Format) ListItem-Element für ListItems für ListControl (Format) ScriptBlock-Element für ListItem für ListControl (Format)

## <a name="syntax"></a>Syntax

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[ListItem-Element (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Definiert die Eigenschaft oder das Skript, dessen Wert in einer Zeile der Listenansicht angezeigt wird.|

## <a name="text-value"></a>Textwert

Geben Sie das Skript an, dessen Wert in der Zeile angezeigt wird.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element angegeben ist, können Sie das [propertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) -Element nicht angeben.

Weitere Informationen zum Angeben von Skripts in einer Listenansicht finden Sie in der [Listenansicht](./creating-a-list-view.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie die-Eigenschaft angegeben wird, deren Wert angezeigt wird.

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a>Weitere Informationen

[Element „PropertyName“ für ListItem für ListControl (Format)](./propertyname-element-for-listitem-for-listcontrol-format.md)

[Erstellen einer Listenansicht](./creating-a-list-view.md)

[Element „ListItem“ für ListItems für ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
