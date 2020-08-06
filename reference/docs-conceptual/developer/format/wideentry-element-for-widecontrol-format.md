---
title: Wideentry-Element für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 13dd1f6ad7ac1e9d8d0524f0a0f18fe80ffaf8e2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780014"
---
# <a name="wideentry-element-for-widecontrol-format"></a>Element „WideEntry“ für WideControl (Format)

Stellt eine Definition der breiten Ansicht bereit.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `WideEntry` Elements beschrieben. Sie müssen ein einzelnes untergeordnetes `WideItem` Element angeben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „EntrySelectedBy“ für WideEntry (Format)](./entryselectedby-element-for-wideentry-format.md)|Optionales Element.<br /><br /> Definiert die .NET-Typen, die diese Breite Eingabe Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.|
|[Wideitem-Element (Format)](./wideitem-element-for-widecontrol-format.md)|Erforderliches Element.<br /><br /> Definiert die Eigenschaft oder das Skript, dessen Wert angezeigt wird.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Wideentries-Element (Format)](./wideentries-element-for-widecontrol-format.md)|Stellt die Definitionen der breiten Ansicht bereit.|

## <a name="remarks"></a>Bemerkungen

Eine breite Ansicht ist ein Listenformat, in dem ein einzelner Eigenschafts Wert oder ein Skript Wert für jedes Objekt angezeigt wird. Im Gegensatz zu anderen Sicht Typen können Sie für jede Sicht Definition nur ein Element Element angeben. Weitere Informationen zu den anderen Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt ein- `WideEntry` Element, das ein einzelnes- `WideItem` Element definiert. Das- `WideItem` Element definiert die-Eigenschaft, deren Wert in der Ansicht angezeigt wird.

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

Ein umfassendes Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Selectioncondition-Element für wideentry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Selectionsetname-Element für wideentry (Format)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[Tyname-Element für wideentry (Format)](./typename-element-for-entryselectedby-for-wideentry-format.md)

[Wideentries-Element (Format)](./wideentries-element-for-widecontrol-format.md)

[Wideitem-Element (Format)](./wideitem-element-for-widecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
