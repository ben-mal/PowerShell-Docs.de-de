---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Alignment“ für TableColumnHeader für TableControl (Format)
description: Element „Alignment“ für TableColumnHeader für TableControl (Format)
ms.openlocfilehash: cf8b90c12c28951283b5870186e2c88d427318a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666823"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a>Element „Alignment“ für TableColumnHeader für TableControl (Format)

Definiert, wie die Daten in einem Spaltenheader angezeigt werden.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tableHeaders-Element (Format) tablecolumnheader-Element (Format) Alignment-Element für tablecolumnheader (Format)

## <a name="syntax"></a>Syntax

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `Alignment` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „TableColumnHeader“ (Format)](./tablecolumnheader-element-format.md)|Definiert eine Bezeichnung, die Breite und die Ausrichtung der Daten für eine Spalte der Tabelle.|

## <a name="text-value"></a>Textwert

Geben Sie einen der folgenden Werte an. Bei den Werten wird nicht zwischen Groß- und Kleinschreibung unterschieden.

Links richtet die in der Spalte angezeigten Daten auf der linken Seite aus. Dies ist die Standardeinstellung, wenn dieses Element nicht angegeben ist.

Rechts richtet die in der Spalte auf der rechten Seite angezeigten Daten aus.

Zentrieren zentriert die in der Spalte angezeigten Daten.

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt ein- `TableColumnHeader` Element, dessen Daten linksbündig ausgerichtet sind.

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Element „TableColumnHeader“ (Format)](./tablecolumnheader-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
