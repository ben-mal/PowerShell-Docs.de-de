---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TableControl“ (Format)
description: Element „TableControl“ (Format)
ms.openlocfilehash: 93e05e22d61504d7781b6f3c07f9a3fd0b3c9e8a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651466"
---
# <a name="tablecontrol-element-format"></a>Element „TableControl“ (Format)

Definiert ein Tabellenformat für eine Sicht.

Viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TableControl` Elements beschrieben. Sie müssen die Zeilen der Tabelle angeben. Alle anderen untergeordneten Elemente sind optional.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „AutoSize“ für TableControl (Format)](./autosize-element-for-tablecontrol-format.md)|Optionales Element.<br /><br /> Gibt an, ob die Spaltengröße und die Anzahl der Spalten basierend auf der Größe der Daten angepasst werden.|
|[Hidetableheaders-Element für tablecontrol (Format)](./hidetableheaders-element-format.md)|Optionales Element.<br /><br /> Gibt an, ob der Header der Tabelle nicht angezeigt wird.|
|[TableHeaders-Element für tablecontrol (Format)](./tableheaders-element-format.md)|Erforderliches Element.<br /><br /> Definiert die Bezeichnungen, die Breite und die Ausrichtung der Daten für die Spalten der Tabellenansicht.|
|[Element „TableRowEntries“ für TableControl (Format)](./tablerowentries-element-for-tablecontrol-format.md)|Optionales Element.<br /><br /> Stellt die Definitionen der Tabellenansicht bereit.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „View“ (Format)](./view-element-format.md)|Definiert eine Ansicht, die zum Anzeigen der Member von einem oder mehreren-Objekten verwendet wird.|

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt ein- `TableControl` Element, das verwendet wird, um die Eigenschaften des [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekts anzuzeigen.

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>...</TableHeaders>
    <TableRowEntries>...</TableRowEntries>
  </TableControl>
</View>

```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Element „View“ (Format)](./view-element-format.md)

[Element „AutoSize“ für TableControl (Format)](./autosize-element-for-tablecontrol-format.md)

[Element „HideTableHeaders“ (Format)](./hidetableheaders-element-format.md)

[Element „TableHeaders“ (Format)](./tableheaders-element-format.md)

[Tablerowentries-Element (Format)](./tablerowentries-element-for-tablecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
