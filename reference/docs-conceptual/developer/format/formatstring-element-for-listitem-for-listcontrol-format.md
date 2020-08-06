---
title: FormatString-Element für ListItem für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 9ec73aa1c2e8180258722627e30344de4e67bda5
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781578"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a>Element „FormatString“ für ListItem für ListControl (Format)

Gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert angezeigt wird.

Configuration Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListControl (Format) ListItems-Element für ListControl (Format) ListItem-Element für ListControl (Format) FormatString-Element für ListItem für ListControl

## <a name="syntax"></a>Syntax

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `FormatString` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[ListItem-Element (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Definiert die Eigenschaft oder das Skript, dessen Wert in einer Zeile der Listenansicht angezeigt wird.|

## <a name="text-value"></a>Textwert

Geben Sie das Muster an, das zum Formatieren der Daten verwendet wird. Beispielsweise können Sie dieses Muster verwenden, um den Wert einer beliebigen Eigenschaft vom Typ " [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: hh}: {0: mm}" zu formatieren.

## <a name="remarks"></a>Bemerkungen

Format Zeichenfolgen können beim Erstellen von Tabellen Sichten, Listen Sichten, breiten Ansichten oder benutzerdefinierten Ansichten verwendet werden. Weitere Informationen zum Formatieren eines in einer Ansicht angezeigten Werts finden Sie unter [Formatieren von angezeigten Daten](./formatting-displayed-data.md).

Weitere Informationen zum Verwenden von Format Zeichenfolgen in Listenansichten finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie eine Formatierungs Zeichenfolge für den Wert der-Eigenschaft definiert wird `StartTime` .

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Listenansicht](./creating-a-list-view.md)

[ListItem-Element (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei](./writing-a-powershell-formatting-file.md)
