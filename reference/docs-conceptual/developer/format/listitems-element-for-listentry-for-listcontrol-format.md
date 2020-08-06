---
title: ListItems-Element für ListEntry für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 03b89a3df2ab0498533d0c00f303f643e0039b25
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781136"
---
# <a name="listitems-element-for-listentry-for-listcontrol-format"></a>Element „ListItems“ für ListEntry für ListControl (Format)

Definiert die Eigenschaften und Skripts, deren Werte in den Zeilen der Listenansicht angezeigt werden.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für Listen Steuerelement (Format) ListEntry-Element für ListControl (Format) ListItems-Element für ListControl (Format)

## <a name="syntax"></a>Syntax

```xml
<ListItems>
  <ListItem>...</ListItem>
</ListItems>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `ListItems` Elements beschrieben. Es gibt keine Beschränkung für die Anzahl der untergeordneten Elemente, die angegeben werden können. Die Reihenfolge der untergeordneten Elemente definiert die Reihenfolge, in der Werte in der Listenansicht angezeigt werden.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[ListItem-Element für ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Erforderliches Element.<br /><br /> Definiert die Eigenschaft oder das Skript, dessen Wert in der Listenansicht angezeigt wird.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „ListEntry“ für ListControl (Format)](./listentry-element-for-listcontrol-format.md)|Stellt eine Definition der Listenansicht bereit.|

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu dieser Art der Ansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt die XML-Elemente, die drei Zeilen der Listenansicht definieren.

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>.NetTypeProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>.NetTypeProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
  </ListEntry>
```

## <a name="see-also"></a>Weitere Informationen

[Element „ListEntry“ für ListControl (Format)](./listentry-element-for-listcontrol-format.md)

[ListItem-Element für ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Erstellen einer Listenansicht](./creating-a-list-view.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
