---
ms.date: 09/13/2016
ms.topic: reference
title: Element „FirstLineHanging“ für Frame für Controls für View (Format)
description: Element „FirstLineHanging“ für Frame für Controls für View (Format)
ms.openlocfilehash: a7a2aa533a74bd3c347307ab49a467d1f9844fc3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655216"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-view-format"></a>Element „FirstLineHanging“ für Frame für Controls für View (Format)

Gibt an, wie viele Zeichen die erste Zeile der Daten nach links verschoben wird. Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelemente Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelement für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für Ansicht (Format) customentry-Element für customentries für Steuerelemente für das View (Format) customItem-Element für customentry für Steuerelemente für das View (Format) Frame-Element für customItem für Steuerelemente für das View (Format) firstlinehanging-Element von Frame View-Steuerelementen (Format)

## <a name="syntax"></a>Syntax

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `FirstLineHanging` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „Frame“ für CustomItem für Controls für View (Format)](./frame-element-for-customitem-for-controls-for-view-format.md)|Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.|

## <a name="text-value"></a>Textwert

Geben Sie die Anzahl der Zeichen an, die Sie in die erste Zeile der Daten verschieben möchten.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element angegeben ist, können Sie das [firstlineingedent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) -Element nicht angeben.

## <a name="see-also"></a>Weitere Informationen

[Element „FirstLineIndent“ für Frame für Controls für View (Format)](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[Element „Frame“ für CustomItem für Controls für View (Format)](./frame-element-for-customitem-for-controls-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
