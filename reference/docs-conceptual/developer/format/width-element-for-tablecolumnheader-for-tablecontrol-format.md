---
title: Width-Element für tablecolumnheader für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e9540d3d351041ad7cb98a21bb360ebea7eca117
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779912"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a>Element „Width“ für TableColumnHeader für TableControl (Format)

Definiert die Breite einer Spalte (in Zeichen).

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tableHeaders-Element für tablecontrol (Format) tablecolumnheader-Element tableHeaders für tablecontrol (Format) width-Element für tablecolumnheader für tablecontrol (Format)

## <a name="syntax"></a>Syntax

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des Elements beschrieben, das `Width` beim Definieren von Spalten Headern verwendet wird.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Tablecolumnheader-Element für tableHeaders für tablecontrol (Format)](./tablecolumnheader-element-format.md)|Definiert eine Bezeichnung, eine Breite und eine Ausrichtung der Daten für eine Spalte der Tabelle.|

## <a name="text-value"></a>Textwert

Geben Sie ggf. eine Breite (in Zeichen) an, die größer als die Länge der angezeigten Eigenschaftswerte ist.

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt ein- `TableColumnHeader` Element, dessen Breite aus 16 Zeichen besteht.

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Tablecolumnheader-Element für TableHeader für tablecontrol (Format)](./tablecolumnheader-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
