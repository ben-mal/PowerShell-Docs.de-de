---
title: TableHeaders-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: b3176cbe1316d5b30cb61831d9915a80389709a5
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787426"
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

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „TableColumnHeader“ (Format)](./tablecolumnheader-element-format.md)|Optionales Element.<br /><br /> Definiert die Bezeichnung, die Breite und die Ausrichtung der Daten für eine Spalte einer Tabellen Sicht.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
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
