---
ms.date: 09/13/2016
ms.topic: reference
title: Element „FormatString“ für WideItem für WideControl (Format)
description: Element „FormatString“ für WideItem für WideControl (Format)
ms.openlocfilehash: f67a18e3ec4f1323e7f9be8904db518c679d53e5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667877"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a>Element „FormatString“ für WideItem für WideControl (Format)

Gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert in der Ansicht angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element für widecontrol (Format) wideitem-Element für widecontrol (Format) FormatString-Element für wideitem für widecontrol (Format)

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

|Element|Beschreibung|
|-------------|-----------------|
|[Element „WideItem“ für WideControl (Format)](./wideitem-element-for-widecontrol-format.md)|Definiert die Eigenschaft oder das Skript, dessen Wert in einer Zeile der Listenansicht angezeigt wird.|

## <a name="text-value"></a>Textwert

Geben Sie das Muster an, das zum Formatieren der Daten verwendet wird. Beispielsweise können Sie dieses Muster verwenden, um den Wert einer beliebigen Eigenschaft vom Typ " [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: hh}: {0: mm}" zu formatieren.

## <a name="remarks"></a>Bemerkungen

Format Zeichenfolgen können beim Erstellen von Tabellen Sichten, Listen Sichten, breiten Ansichten oder benutzerdefinierten Ansichten verwendet werden. Weitere Informationen zum Formatieren eines in einer Ansicht angezeigten Werts finden Sie unter [Formatieren von angezeigten Daten](./formatting-displayed-data.md).

Weitere Informationen zum Verwenden von Format Zeichenfolgen in breiten Ansichten finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie eine Formatierungs Zeichenfolge für den Wert der-Eigenschaft definiert wird `StartTime` .

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Element „WideItem“ für WideControl (Format)](./wideitem-element-for-widecontrol-format.md)

[Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei](./writing-a-powershell-formatting-file.md)
