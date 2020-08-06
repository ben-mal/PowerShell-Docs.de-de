---
title: Tablecolumnitems-Element für tablerowentry für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 661b938e8db0e68e10dc05f552e4f3a14608bc55
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785148"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a>Element „TableColumnItems“ für TableRowEntry für TableControl (Format)

Definiert die Eigenschaften oder Skripts, deren Werte in einer Zeile angezeigt werden.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element für tablecontrol (Format) tablerowentry-Element für tablerowentries für tablecontrol (Format) tablecolumnitems-Element für tablecontrolentry für tablecontrol (Format)

## <a name="syntax"></a>Syntax

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `TableColumnItems` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „TableColumnItem“ für TableColumnItems für TableControl (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|Erforderliches Element.<br /><br /> Definiert die Eigenschaft oder das Skript, dessen Wert in einer Spalte der Zeile angezeigt wird.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „TableRowEntry“ für TableRowEntries für TableControl (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|Definiert die Daten, die in einer Zeile der Tabelle angezeigt werden.|

## <a name="remarks"></a>Bemerkungen

`TableColumnItem`Für jede Spalte der Zeile ist ein-Element erforderlich. Der erste Eintrag wird in der ersten Spalte angezeigt, der zweite Eintrag in der zweiten Spalte usw.

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt ein- `TableColumnItems` Element, das drei Eigenschaften des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts definiert.

```xml
<TableColumnItems>
  <TableColumnItem>
    <PropertyName>Status</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>Name</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>DisplayName</PropertyName>
  </TableColumnItem>
</TableColumnItems>

```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Tablecolumnitem-Element (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[Tablerowentry-Element (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
