---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TableRowEntry“ für TableRowEntries für TableControl (Format)
description: Element „TableRowEntry“ für TableRowEntries für TableControl (Format)
ms.openlocfilehash: 60d64b7c14b40e87825ada36e19f52a66fe8b6cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659763"
---
# <a name="tablerowentry-element-for-tablerowentries-for-tablecontrol-format"></a>Element „TableRowEntry“ für TableRowEntries für TableControl (Format)

Definiert die Daten, die in einer Zeile der Tabelle angezeigt werden.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element für tablecontrol (Format) tablerowentry-Element für tablerowentries für tablecontrol (Format)

## <a name="syntax"></a>Syntax

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TableRowEntry` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Entryselectedby-Element für tablerowentry für tablecontrol (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Erforderliches Element.<br /><br /> Definiert die Objekte, deren Eigenschaftswerte in der Zeile angezeigt werden.|
|[Element „TableColumnItems“ für TableRowEntry für TableControl (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|Erforderliches Element.<br /><br /> Definiert die Eigenschaften oder Skripts, deren Werte angezeigt werden.|
|[Wrap-Element für tablerowentry für tablecontrol (Format)](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)|Optionales Element.<br /><br /> Gibt an, dass der Text, der die Spaltenbreite überschreitet, in der nächsten Zeile angezeigt wird.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „TableRowEntries“ für TableControl (Format)](./tablerowentries-element-for-tablecontrol-format.md)|Definiert die Zeilen der Tabelle.|

## <a name="remarks"></a>Bemerkungen

Ein `TableColumnItems` -Element und ein- `EntrySelectedBy` Element müssen angegeben werden.

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt ein- `TableRowEntry` Element, das eine Zeile definiert, in der die Werte von zwei Eigenschaften des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts angezeigt werden.

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName> Property for first column</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName> Property for second column</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Entryselectedby-Element für tablerowentry für tablecontrol (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Element „TableColumnItems“ für TableRowEntry für TableControl (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[Element „TableRowEntries“ für TableControl (Format)](./tablerowentries-element-for-tablecontrol-format.md)

[Wrap-Element für tablerowentry für tablecontrol (Format)](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
