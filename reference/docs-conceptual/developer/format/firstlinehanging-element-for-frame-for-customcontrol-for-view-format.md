---
ms.date: 09/13/2016
ms.topic: reference
title: Element „FirstLineHanging“ für Frame für CustomControl für View (Format)
description: Element „FirstLineHanging“ für Frame für CustomControl für View (Format)
ms.openlocfilehash: 8b9601b2afd7ab5523e339fb45119f5cf9f4a535
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648148"
---
# <a name="firstlinehanging-element-for-frame-for-customcontrol-for-view-format"></a>Element „FirstLineHanging“ für Frame für CustomControl für View (Format)

Gibt an, wie viele Zeichen die erste Zeile der Daten nach links verschoben wird. Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries for View (Format) customItem-Element für customentry für customcontrolview (Format) Frame-Element für customItem für CustomControl für View (Format) firstlinehanging-Element für Frame für CustomControl für Ansicht (Format)

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
|[Element „Frame“ für CustomItem für CustomControl für View (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.|

## <a name="text-value"></a>Textwert

Geben Sie die Anzahl der Zeichen an, die Sie in die erste Zeile der Daten verschieben möchten.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element angegeben ist, können Sie das [firstlineingedent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) -Element nicht angeben.

## <a name="see-also"></a>Weitere Informationen

[Element „FirstLineIndent“ für Frame für CustomControl für View (Format)](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[Element „Frame“ für CustomItem für CustomControl für View (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
