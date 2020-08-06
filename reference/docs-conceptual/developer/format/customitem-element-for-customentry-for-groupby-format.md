---
title: CustomItem-Element für customentry für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e8086c5330b6644f83316ad4ae33c33ba40d9eee
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783720"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a>Element „CustomItem“ für CustomEntry für GroupBy (Format)

Definiert, welche Daten von der benutzerdefinierten Steuerelement Ansicht und der Anzeige angezeigt werden. Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format)

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

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „ExpressionBinding“ für CustomItem für GroupBy (Format)](./expressionbinding-element-for-customitem-for-groupby-format.md)|Optionales Element.<br /><br /> Definiert die Daten, die vom-Steuerelement angezeigt werden.|
|[Element „Frame“ für CustomItem für GroupBy (Format)](./frame-element-for-customitem-for-groupby-format.md)|Optionales Element.<br /><br /> Definiert, welche Daten von der benutzerdefinierten Steuerelement Ansicht und der Anzeige angezeigt werden.|
|[Element „NewLine“ für CustomItem für GroupBy (Format)](./newline-element-for-customitem-for-groupby-format.md)|Optionales Element.<br /><br /> Fügt der Anzeige des-Steuer Elements eine leere Zeile hinzu.|
|[Element „Text“ für CustomItem für GroupBy (Format)](./text-element-for-customitem-for-groupby-format.md)|Optionales Element.<br /><br /> Gibt zusätzlichen Text zu den Daten an, die vom-Steuerelement angezeigt werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „CustomEntry“ für CustomControl für GroupBy (Format)](./customentry-element-for-customcontrol-for-groupby-format.md)|Stellt eine Definition der benutzerdefinierten Steuerelement Ansicht bereit.|

## <a name="remarks"></a>Bemerkungen

## <a name="see-also"></a>Weitere Informationen

[Element „CustomEntry“ für CustomControl für GroupBy (Format)](./customentry-element-for-customcontrol-for-groupby-format.md)

[Element „ExpressionBinding“ für CustomItem für GroupBy (Format)](./expressionbinding-element-for-customitem-for-groupby-format.md)

[Element „Frame“ für CustomItem für GroupBy (Format)](./frame-element-for-customitem-for-groupby-format.md)

[Element „NewLine“ für CustomItem für GroupBy (Format)](./newline-element-for-customitem-for-groupby-format.md)

[Element „Text“ für CustomItem für GroupBy (Format)](./text-element-for-customitem-for-groupby-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
