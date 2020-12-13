---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Label“ für GroupBy (Format)
description: Element „Label“ für GroupBy (Format)
ms.openlocfilehash: ff4b0dec01bb5b472b1813540661791b91568eed
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649786"
---
# <a name="label-element-for-groupby-format"></a>Element „Label“ für GroupBy (Format)

Gibt eine Bezeichnung an, die beim Auftreten einer neuen Gruppe angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) Label-Element für GroupBy (Format)

## <a name="syntax"></a>Syntax

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `Label` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „GroupBy“ für View (Format)](./groupby-element-for-view-format.md)|Definiert, wie eine neue Gruppe von Objekten angezeigt wird.|

## <a name="text-value"></a>Textwert

Geben Sie den Text an, der angezeigt wird, wenn Windows PowerShell auf einen neuen Eigenschafts-oder Skript Wert stößt.

## <a name="remarks"></a>Bemerkungen

Zusätzlich zum von diesem Element angegebenen Text zeigt Windows PowerShell den neuen Wert an, der die Gruppe startet, und fügt vor und nach der Gruppe eine leere Zeile hinzu.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die Bezeichnung für eine neue Gruppe. Die angezeigte Bezeichnung sieht in etwa wie folgt aus: `Service Type: NewValueofProperty`

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

Ein Beispiel für eine komplette Formatierungs Datei, die dieses Element enthält, finden Sie unter [Wide View (GroupBy)](./wide-view-groupby.md).

## <a name="see-also"></a>Weitere Informationen

[Element „GroupBy“ für View (Format)](./groupby-element-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
