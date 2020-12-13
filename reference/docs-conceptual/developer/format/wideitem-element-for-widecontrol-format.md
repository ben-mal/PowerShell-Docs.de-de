---
ms.date: 09/13/2016
ms.topic: reference
title: Element „WideItem“ für WideControl (Format)
description: Element „WideItem“ für WideControl (Format)
ms.openlocfilehash: b9c416bbe3befcd689b8a2c0b72a8ff1301b9659
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647804"
---
# <a name="wideitem-element-for-widecontrol-format"></a>Element „WideItem“ für WideControl (Format)

Definiert die Eigenschaft oder das Skript, dessen Wert angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) wideitem-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `WideItem` Elements beschrieben. Das `FormatString`-Element ist optional. Sie müssen jedoch ein- `PropertyName` oder- `ScriptBlock` Element angeben, aber Sie können nicht beides angeben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „FormatString“ für WideItem für WideControl (Format)](./formatstring-element-for-wideitem-for-widecontrol-format.md)|Optionales Element.<br /><br /> Gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert in der Ansicht angezeigt wird.|
|[PropertyName-Element für wideitem (Format)](./propertyname-element-for-wideitem-for-widecontrol-format.md)|Gibt die-Eigenschaft des-Objekts an, dessen Wert in der breiten Ansicht angezeigt wird.|
|[ScriptBlock-Element für wideitem (Format)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|Gibt das Skript an, dessen Wert in der breiten Ansicht angezeigt wird.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Wideentry-Element (Format)](./wideentry-element-for-widecontrol-format.md)|Stellt eine Definition der breiten Ansicht bereit.|

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Wide View](./creating-a-wide-view.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt ein- `WideEntry` Element, das ein einzelnes- `WideItem` Element definiert. Das- `WideItem` Element definiert die Eigenschaft oder das Skript, dessen Wert in der Ansicht angezeigt wird.

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

Ein umfassendes Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).

## <a name="see-also"></a>Weitere Informationen

[Element „FormatString“ für WideItem für WideControl (Format)](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[PropertyName-Element für wideitem (Format)](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[ScriptBlock-Element für wideitem (Format)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[Wideentry-Element (Format)](./wideentry-element-for-widecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
