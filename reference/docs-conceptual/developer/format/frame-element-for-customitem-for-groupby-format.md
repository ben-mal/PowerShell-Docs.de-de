---
title: Frame-Element für customItem für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 1568236ff7b6142f7e41be70a3ae5e28307cf790
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785760"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a>Element „Frame“ für CustomItem für GroupBy (Format)

Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts. Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.

Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format) Frame-Element für customItem für GroupBy (Format)

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

|Element|BESCHREIBUNG|
|-------------|-----------------|
|`CustomItem Element`|Erforderliches Element|
|[Element „FirstLineHanging“ für Frame für GroupBy (Format)](./firstlinehanging-element-for-frame-for-groupby-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die erste Zeile der Daten nach links verschoben wird.|
|[Element „FirstLineIndent“ für Frame für GroupBy (Format)](./firstlineindent-element-for-frame-for-groupby-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die erste Zeile der Daten nach rechts verschoben wird.|
|[Element „LeftIndent“ für Frame für GroupBy (Format)](./leftindent-element-for-frame-for-groupby-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die Daten vom linken Rand entfernt werden.|
|[RightIndent-Element für Frame für GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md) RightIndent-Element|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die Daten vom rechten Rand entfernt werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „CustomItem“ für CustomEntry für GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)|Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.|

## <a name="remarks"></a>Bemerkungen

Sie können die Elemente [firstlinehanging](./firstlinehanging-element-for-frame-for-groupby-format.md) und [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) nicht im selben Element angeben `Frame` .

## <a name="see-also"></a>Weitere Informationen

[Element „FirstLineHanging“ für Frame für GroupBy (Format)](./firstlinehanging-element-for-frame-for-groupby-format.md)

[Element „FirstLineIndent“ für Frame für GroupBy (Format)](./firstlineindent-element-for-frame-for-groupby-format.md)

[Element „LeftIndent“ für Frame für GroupBy (Format)](./leftindent-element-for-frame-for-groupby-format.md)

[Element „RightIndent“ für Frame für GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)

[Element „CustomItem“ für CustomEntry für GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
