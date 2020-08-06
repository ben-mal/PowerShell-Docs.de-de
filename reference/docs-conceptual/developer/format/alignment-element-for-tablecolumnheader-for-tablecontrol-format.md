---
title: Alignment-Element für tablecolumnheader für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 1bf395b84af90d725c14b2f0ef569f72b5fcc613
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783924"
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

|Element|BESCHREIBUNG|
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
