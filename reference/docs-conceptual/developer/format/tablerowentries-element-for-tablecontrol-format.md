---
title: Tablerowentries-Element für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4cc5d354df3e552e181a95148caa020f0041db92
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785114"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a>Element „TableRowEntries“ für TableControl (Format)

Definiert die Zeilen der Tabelle.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element für tablecontrol (Format)

## <a name="syntax"></a>Syntax

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `TableRowEntries` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „TableRowEntry“ für TableRowEntries für TableControl (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|Erforderliches Element.<br /><br /> Definiert die Daten, die in einer Zeile der Tabelle angezeigt werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „TableControl“ (Format)](./tablecontrol-element-format.md)|Definiert ein Tabellenformat für eine Sicht.|

## <a name="remarks"></a>Bemerkungen

Sie müssen mindestens ein `TableRowEntry` Element für die Tabellenansicht angeben. Es gibt keine maximale Beschränkung für die Anzahl der `TableRowEntry` Elemente, die hinzugefügt werden können, und deren Reihenfolge nicht signifikant ist.

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt ein- `TableRowEntries` Element, das eine Zeile definiert, in der die Werte von zwei Eigenschaften des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts angezeigt werden.

```xml
<TableRowEntries>
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
</TableRowEntries>

```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Element „TableControl“ (Format)](./tablecontrol-element-format.md)

[Tablerowentry-Element (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
