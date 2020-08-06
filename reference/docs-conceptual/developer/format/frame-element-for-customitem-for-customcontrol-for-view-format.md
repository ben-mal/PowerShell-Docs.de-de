---
title: Frame-Element für customItem für CustomControl für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4864ea1a865f77c9de6e495d7e8296e81c19b366
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781442"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a>Element „Frame“ für CustomItem für CustomControl für View (Format)

Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts. Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) customItem-Element für customentry für customcontrolview (Format) Frame Element für customItem für CustomControl for View (Format)

## <a name="syntax"></a>Syntax

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Frame` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`CustomItem Element`|Erforderliches Element|
|[Firstlinehanging-Element](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die erste Zeile der Daten nach links verschoben wird.|
|[Firstlineingedent-Element](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die erste Zeile der Daten nach rechts verschoben wird.|
|[LeftIndent-Element](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die Daten vom linken Rand entfernt werden.|
|[RightIndent-Element](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die Daten vom rechten Rand entfernt werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[CustomItem-Element für customentry für View (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.|

## <a name="remarks"></a>Bemerkungen

Sie können die Elemente [firstlinehanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) und [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) nicht im selben Element angeben `Frame` .

## <a name="see-also"></a>Weitere Informationen

[Firstlinehanging-Element](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[Firstlineingedent-Element](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[LeftIndent-Element](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[RightIndent-Element](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[CustomItem-Element für customentry für View (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
