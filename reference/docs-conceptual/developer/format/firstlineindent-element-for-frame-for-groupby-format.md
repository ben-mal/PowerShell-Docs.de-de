---
ms.date: 09/13/2016
ms.topic: reference
title: Element „FirstLineIndent“ für Frame für GroupBy (Format)
description: Element „FirstLineIndent“ für Frame für GroupBy (Format)
ms.openlocfilehash: 391a6f338e264fd9fdd1948ded74bf022cb114d1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645792"
---
# <a name="firstlineindent-element-for-frame-for-groupby-format"></a>Element „FirstLineIndent“ für Frame für GroupBy (Format)

Gibt an, wie viele Zeichen die erste Zeile der Daten nach rechts verschoben wird. Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format) Frame-Element für customItem für GroupBy (Format) FirstLineIndent-Element für Frame für GroupBy (Format)

## <a name="syntax"></a>Syntax

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `FirstLineIndent` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „Frame“ für CustomItem für GroupBy (Format)](./frame-element-for-customitem-for-groupby-format.md)|Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.|

## <a name="text-value"></a>Textwert

Geben Sie die Anzahl der Zeichen an, die Sie in die erste Zeile der Daten verschieben möchten.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element angegeben ist, können Sie das [firstlinehanging](./firstlinehanging-element-for-frame-for-groupby-format.md) -Element nicht angeben.

## <a name="see-also"></a>Weitere Informationen

[Element „FirstLineHanging“ für Frame für GroupBy (Format)](./firstlinehanging-element-for-frame-for-groupby-format.md)

[Element „Frame“ für CustomItem für GroupBy (Format)](./frame-element-for-customitem-for-groupby-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
