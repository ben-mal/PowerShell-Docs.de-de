---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TableHeaders“ (Format)
description: Element „TableHeaders“ (Format)
ms.openlocfilehash: 5ac4dccae746c167ebf95add9f3d18030a2b3a99
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659818"
---
# <a name="tableheaders-element-format"></a>Element „TableHeaders“ (Format)

Definiert die Header für die Spalten einer Tabelle.

Viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tableHeaders-Element für tablecontrol (Format)

## <a name="syntax"></a>Syntax

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und die übergeordneten Elemente des- `TableHeaders` Elements beschrieben. Es muss ein untergeordnetes-Element für jede Eigenschaft des Objekts vorhanden sein, das angezeigt werden soll. Die Spaltenheader Informationen werden in der Reihenfolge angezeigt, in der die untergeordneten Elemente angegeben werden.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „TableColumnHeader“ (Format)](./tablecolumnheader-element-format.md)|Optionales Element.<br /><br /> Definiert die Bezeichnung, die Breite und die Ausrichtung der Daten für eine Spalte einer Tabellen Sicht.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „TableControl“ (Format)](./tablecontrol-element-format.md)|Definiert ein Tabellenformat für eine Sicht.|

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt ein- `TableHeaders` Element, das zwei Spaltenheader definiert.

```xml
<TableHeaders>
  <TableColumnHeader>
    <Label>Column 1</Label)
    <Width>16</Width>
    <Alignment>Left</Alignment>
  </TableColumnHeader>
  <TableColumnHeader>
    <Label>Column 2</Label)
    <Width>10</Width>
    <Alignment>Centered</Alignment>
  </TableColumnHeader>
</TableHeaders>
```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Element „TableColumnHeader“ (Format)](./tablecolumnheader-element-format.md)

[Element „TableControl“ (Format)](./tablecontrol-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
