---
ms.date: 09/13/2016
ms.topic: reference
title: Element „FirstLineIndent“ für Frame für CustomControl für View (Format)
description: Element „FirstLineIndent“ für Frame für CustomControl für View (Format)
ms.openlocfilehash: 8dce8b4b072b754c3b7d631b3e5c321a5a3e5a3e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645887"
---
# <a name="firstlineindent-element-for-frame-for-customcontrol-for-view-format"></a>Element „FirstLineIndent“ für Frame für CustomControl für View (Format)

Gibt an, wie viele Zeichen die erste Zeile der Daten nach rechts verschoben wird. Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) customItem-Element für customentry für customcontrolview (Format)-Element "FirstLineIndent"

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
|[Element „Frame“ für CustomItem für CustomControl für View (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.|

## <a name="text-value"></a>Textwert

Geben Sie die Anzahl der Zeichen an, die Sie in die erste Zeile der Daten verschieben möchten.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element angegeben ist, können Sie das [firstlinehanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) -Element nicht angeben.

## <a name="see-also"></a>Weitere Informationen

[Element „FirstLineHanging“ für Frame für CustomControl für View (Format)](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[Element „Frame“ für CustomItem für CustomControl für View (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
