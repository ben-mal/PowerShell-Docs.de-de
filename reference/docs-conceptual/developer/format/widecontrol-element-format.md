---
title: Widecontrol-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: b6f19cf94dcb440eeaf53547db407287e5462520
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784978"
---
# <a name="widecontrol-element-format"></a>Element „WideControl“ (Format)

Definiert ein breites Listenformat (Einzelwert) für die Sicht. Diese Ansicht zeigt einen einzelnen Eigenschafts Wert oder einen Skript Wert für jedes Objekt an.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) widecontrol-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `WideControl` Elements beschrieben. Das `AutoSize` -Element und das-Element können nicht `ColumnNumber` gleichzeitig angegeben werden.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „AutoSize“ für WideControl (Format)](./autosize-element-for-widecontrol-format.md)|Optionales Element.<br /><br /> Gibt an, ob die Spaltengröße und die Anzahl der Spalten basierend auf der Größe der Daten angepasst werden.|
|[Element „ColumnNumber“ für WideControl (Format)](./columnnumber-element-for-widecontrol-format.md)|Optionales Element.<br /><br /> Gibt die Anzahl der Spalten an, die in der breiten Ansicht angezeigt werden.|
|[Wideentries-Element (Format)](./wideentries-element-for-widecontrol-format.md)|Erforderliches Element.<br /><br /> Stellt die Definitionen der breiten Ansicht bereit.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „View“ (Format)](./view-element-format.md)|Definiert eine Ansicht, die verwendet wird, um ein oder mehrere .NET-Objekte anzuzeigen.|

## <a name="remarks"></a>Bemerkungen

Beim Definieren einer breiten Ansicht können Sie das- `AutoSize` Element oder das-Element hinzufügen, `ColumnNumber` aber Sie können nicht beides hinzufügen.

In den meisten Fällen ist nur eine Definition für jede Breite Ansicht erforderlich, aber es ist möglich, mehrere Definitionen zu verwenden, wenn Sie dieselbe Ansicht verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen. In diesen Fällen können Sie eine separate Definition für jedes Objekt oder jede Gruppe von Objekten bereitstellen.

Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Wide View Components](./creating-a-wide-view.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt ein- `WideControl` Element, das verwendet wird, um eine Eigenschaft des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts anzuzeigen.

```xml
<View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>...</WideEntries>
  </WideControl>
</View>
```

Ein umfassendes Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).

## <a name="see-also"></a>Weitere Informationen

[AutoSize-Element für widecontrol (Format)](./autosize-element-for-widecontrol-format.md)

[Element „ColumnNumber“ für WideControl (Format)](./columnnumber-element-for-widecontrol-format.md)

[Element „View“ (Format)](./view-element-format.md)

[Wideentries-Element (Format)](./wideentries-element-for-widecontrol-format.md)

[Breite Ansicht (Basic)](./wide-view-basic.md)

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
