---
title: Wideentries-Element für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 74383b288c945008c1d7b5119363a166c04802ae
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785046"
---
# <a name="wideentries-element-for-widecontrol-format"></a>Element „WideEntries“ für WideControl (Format)

Stellt die Definitionen der breiten Ansicht bereit. In der breiten Ansicht muss mindestens eine Definition angegeben werden.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) widecontrol-Element (Format) wideentries-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `WideEntries` Elements beschrieben. Es muss mindestens ein untergeordnetes Element angegeben werden.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Wideentry-Element (Format)](./wideentry-element-for-widecontrol-format.md)|Stellt eine Definition der breiten Ansicht bereit.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „WideControl“ (Format)](./widecontrol-element-format.md)|Definiert ein breites Listenformat (Einzelwert) für die Sicht.|

## <a name="remarks"></a>Bemerkungen

Eine breite Ansicht ist ein Listenformat, in dem ein einzelner Eigenschafts Wert oder ein Skript Wert für jedes Objekt angezeigt wird. Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Wide View Components](./creating-a-wide-view.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt ein- `WideEntries` Element, das ein einzelnes- `WideEntry` Element definiert. Das- `WideEntry` Element enthält ein einzelnes- `WideItem` Element, das definiert, welcher Eigenschafts-oder Skript Wert in der Ansicht angezeigt wird.

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

Ein umfassendes Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Element „WideControl“ (Format)](./widecontrol-element-format.md)

[Wideentry-Element (Format)](./wideentry-element-for-widecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
