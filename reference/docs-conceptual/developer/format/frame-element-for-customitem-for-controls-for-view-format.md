---
title: Frame-Element für customItem für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 5ade36c183a026cb9001a2abbe91d31638a87108
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773452"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a>Element „Frame“ für CustomItem für Controls für View (Format)

Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts. Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.

Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) steuert Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelement für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für Steuerelemente für View (Format) customItem-Element für customentry für Steuerelemente für Ansicht (Format) Frame Element für customItem für die Ansicht (Format)

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
|[Firstlinehanging-Element von Frame der Steuerelemente der Ansicht (Format)](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die erste Zeile nach links verschoben wird.|
|[FirstLineIndent-Element von Frame der Steuerelemente der Ansicht (Format)](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die erste Zeile nach rechts verschoben wird.|
|[LeftIndent-Element von Frame der Steuerelemente der Ansicht (Format)](./leftindent-element-for-frame-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die Daten vom linken Rand entfernt werden.|
|[RightIndent-Element von Frame-Steuerelementen der Ansicht (Format)](./rightindent-element-for-frame-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die Daten vom rechten Rand entfernt werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomItem“ für CustomEntry für Controls für View (Format)](./customitem-element-for-customentry-for-controls-for-view-format.md)|Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.|

## <a name="remarks"></a>Bemerkungen

Sie können die Elemente [firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) und [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) nicht im selben Element angeben `Frame` .

## <a name="see-also"></a>Weitere Informationen

[Firstlinehanging-Element von Frame der Steuerelemente der Ansicht (Format)](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[FirstLineIndent-Element von Frame der Steuerelemente der Ansicht (Format)](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[LeftIndent-Element von Frame der Steuerelemente der Ansicht (Format)](./leftindent-element-for-frame-for-controls-for-view-format.md)

[RightIndent-Element von Frame-Steuerelementen der Ansicht (Format)](./rightindent-element-for-frame-for-controls-for-view-format.md)

[Element „CustomItem“ für CustomEntry für Controls für View (Format)](./customitem-element-for-customentry-for-controls-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
