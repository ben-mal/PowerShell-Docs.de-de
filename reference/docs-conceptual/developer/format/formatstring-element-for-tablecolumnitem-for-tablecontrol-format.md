---
title: FormatString-Element für tablecolumnitem für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 848583e697d0ab7bd5b017c14c47aba3c51a3c17
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781544"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a>Element „FormatString“ für TableColumnItem für TableControl (Format)

Gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert der Tabelle angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) tablecolumnitems-Element (Format) tablecolumnitem-Element (Format) FormatString-Element für tablecolumnitem (Format)

## <a name="syntax"></a>Syntax

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `FormatString` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Tablecolumnitem-Element (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|Definiert die Eigenschaft oder das Skript, dessen Wert in der Spalte der Zeile angezeigt wird.|

## <a name="text-value"></a>Textwert

Geben Sie das Muster an, das zum Formatieren der Daten verwendet wird. Beispielsweise kann dieses Muster verwendet werden, um den Wert einer beliebigen Eigenschaft des Typs " [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: hh}: {0: mm}" zu formatieren.

## <a name="remarks"></a>Bemerkungen

Format Zeichenfolgen können beim Erstellen von Tabellen Sichten, Listen Sichten, breiten Ansichten oder benutzerdefinierten Ansichten verwendet werden. Weitere Informationen zum Formatieren eines in einer Ansicht angezeigten Werts finden Sie unter [Formatieren von angezeigten Daten](./formatting-displayed-data.md).

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Tabellen Sicht](./creating-a-table-view.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie eine Formatierungs Zeichenfolge für den Wert der-Eigenschaft definiert wird `StartTime` .

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Formatieren von angezeigten Daten](./formatting-displayed-data.md)

[Tablecolumnitem-Element (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
