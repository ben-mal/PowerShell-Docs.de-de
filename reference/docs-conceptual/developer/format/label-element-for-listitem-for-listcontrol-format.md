---
title: Label-Element für ListItem für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: ad80cc0478e7567b12d264ab661d843248ba48e1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783635"
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
