---
title: FirstLineIndent-Element für Frame für CustomControl für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 0d51be5b5fc04bc0ea8442ca96767b1d9d8473a4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785811"
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

|Element|BESCHREIBUNG|
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
