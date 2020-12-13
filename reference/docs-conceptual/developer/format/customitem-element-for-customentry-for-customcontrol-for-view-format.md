---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomItem“ für CustomEntry für CustomControl für View (Format)
description: Element „CustomItem“ für CustomEntry für CustomControl für View (Format)
ms.openlocfilehash: 9090a3ada5316ba5ddb4a9c46eee37c11982ae6e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666738"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a>Element „CustomItem“ für CustomEntry für CustomControl für View (Format)

Definiert, welche Daten von der benutzerdefinierten Steuerelement Ansicht und der Anzeige angezeigt werden. Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) customItem-Element für customentry for View (Format)

## <a name="syntax"></a>Syntax

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomItem` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „ExpressionBinding“ für CustomItem für CustomControl für View (Format)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Definiert die Daten, die vom-Steuerelement angezeigt werden.|
|[Element „Frame“ für CustomItem für CustomControl für View (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Definiert, welche Daten von der benutzerdefinierten Steuerelement Ansicht und der Anzeige angezeigt werden.|
|[NewLine-Element für customItem für benutzerdefiniertes Steuer Element für Ansicht (Format)](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Fügt der Anzeige des-Steuer Elements eine leere Zeile hinzu.|
|[Text-Element für customItem für CustomControl für Ansicht (Format)](./text-element-for-customitem-for-customview-for-view-format.md)|Optionales Element.<br /><br /> Gibt zusätzlichen Text zu den Daten an, die vom-Steuerelement angezeigt werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomEntry“ für CustomEntries für CustomControl für View (Format)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|Stellt eine Definition der benutzerdefinierten Steuerelement Ansicht bereit.|

## <a name="remarks"></a>Bemerkungen

## <a name="see-also"></a>Weitere Informationen

[Customentry-Element für customentries für View (Format)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[Element „ExpressionBinding“ für CustomItem für CustomControl für View (Format)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[Element „Frame“ für CustomItem für CustomControl für View (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[Element „NewLine“ für CustomItem für CustomControl für View (Format)](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[Text-Element für customItem für CustomControl für Ansicht (Format)](./text-element-for-customitem-for-customview-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
