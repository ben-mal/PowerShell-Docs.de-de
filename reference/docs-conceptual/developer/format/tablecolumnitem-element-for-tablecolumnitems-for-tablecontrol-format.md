---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TableColumnItem“ für TableColumnItems für TableControl (Format)
description: Element „TableColumnItem“ für TableColumnItems für TableControl (Format)
ms.openlocfilehash: 8ef5158c9bb9f074d5c58190d4d3b20c10c83744
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659852"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a>Element „TableColumnItem“ für TableColumnItems für TableControl (Format)

Definiert die Eigenschaft oder das Skript, dessen Wert in der Spalte der Zeile angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element für tablecontrol (Format) tablerowentry-Element für tableroweinträge für tablecontrol (Format) tablecolumnitems-Element für tablecontrolentry für tablecontrol (Format) tablecolumnitem-Element für tablecolumnitems für tablecontrol (Format)

## <a name="syntax"></a>Syntax

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `TableColumnItem` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „Alignment“ für TableColumnItem für TableControl (Format)](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|Optionales Element.<br /><br /> Definiert, wie die Daten in einer Spalte der Zeile angezeigt werden.|
|[Element „FormatString“ für TableColumnItem für TableControl (Format)](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|Gibt ein Format Muster an, das zum Formatieren der Daten in der Spalte der Zeile verwendet wird.|
|[Element „PropertyName“ für TableColumnItem für TableControl (Format)](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|Optionales Element.<br /><br /> Gibt den Namen der Eigenschaft an, deren Wert angezeigt wird.|
|[Element „ScriptBlock“ für TableColumnItem für TableControl (Format)](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|Optionales Element.<br /><br /> Gibt das Skript an, dessen Wert in der Spalte einer Zeile angezeigt wird.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Tablecolumnitems-Element für tablecontrolentry für tablecontrol (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|Definiert die Eigenschaften oder Skripts, deren Werte in der Zeile angezeigt werden.|

## <a name="remarks"></a>Bemerkungen

Sie können in jeder Spalte der Zeile eine Eigenschaft eines Objekts oder eines Skripts angeben. Wenn keine untergeordneten Elemente angegeben werden, ist das Element ein Platzhalter, und es werden keine Daten angezeigt.

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt ein- `TableColumnItem` Element, das den Wert der- `Status` Eigenschaft des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts anzeigt.

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Element „Alignment“ für TableColumnItem für TableControl (Format)](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Tablecolumnitems-Element (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[Element „FormatString“ für TableColumnItem für TableControl (Format)](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Element „PropertyName“ für TableColumnItem für TableControl (Format)](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Element „ScriptBlock“ für TableColumnItem für TableControl (Format)](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
