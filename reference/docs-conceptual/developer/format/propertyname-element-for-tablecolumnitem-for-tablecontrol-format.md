---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für TableColumnItem für TableControl (Format)
description: Element „PropertyName“ für TableColumnItem für TableControl (Format)
ms.openlocfilehash: e83bbdb96d2755013cb9fe065cb98731ba44917f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665582"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a>Element „PropertyName“ für TableColumnItem für TableControl (Format)

Gibt die Eigenschaft an, deren Wert in der Spalte der Zeile angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) tablecolumnitems-Element (Format) tablecolumnitem-Element (Format) propertyName-Element für tablecolumnitem (Format)

## <a name="syntax"></a>Syntax

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Tablecolumnitem-Element (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|Definiert die Eigenschaft oder das Skript, dessen Wert in der Spalte der Zeile angezeigt wird.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen der Eigenschaft an, deren Wert angezeigt wird.

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt ein- `TableColumnItem` Element, das die- `Status` Eigenschaft des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts angibt.

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Tablecolumnitem-Element (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
