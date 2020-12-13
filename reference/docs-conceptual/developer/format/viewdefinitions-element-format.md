---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ViewDefinitions“ (Format)
description: Element „ViewDefinitions“ (Format)
ms.openlocfilehash: fceef0e5ec91e8c59a7b2b90fd31ca422ff0c94d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664589"
---
# <a name="viewdefinitions-element-format"></a>Element „ViewDefinitions“ (Format)

Definiert die Sichten, die zum Anzeigen von .NET-Objekten verwendet werden. Diese Sichten können die Eigenschaften und Skript Werte eines Objekts in einem Tabellenformat, einem Listenformat, einem breiten Format und einem benutzerdefinierten Steuerelement Format anzeigen.

Configuration-Element (Format) viewdefinitions (Format XML)-Element

## <a name="syntax"></a>Syntax

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `ViewDefinitions` Elements beschrieben. Es gibt keine Beschränkung für die Anzahl der Sichten, die in einer Formatierungs Datei definiert werden können, und Sie können in beliebiger Reihenfolge hinzugefügt werden.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „View“ (Format)](./view-element-format.md)|Definiert eine Ansicht, die verwendet wird, um ein oder mehrere .NET-Objekte anzuzeigen.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „Configuration“ (Format)](./configuration-element-format.md)|Stellt das Element der obersten Ebene einer Formatierungs Datei dar.|

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu den Komponenten der verschiedenen Sicht Typen finden Sie in den folgenden Themen:

- [Erstellen einer Tabellenansicht](./creating-a-table-view.md)

- [Erstellen einer Listenansicht](./creating-a-list-view.md)

- [Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

- [Benutzerdefinierte Steuerelemente](./creating-custom-controls.md)

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt ein `ViewDefinitions` -Element, das die übergeordneten Elemente für eine Tabellenansicht und eine Listenansicht enthält.

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <TableControl>...</TableControl>
    </View>
    <View>
      <ListControl>...</ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a>Weitere Informationen

[Element „Configuration“ (Format)](./configuration-element-format.md)

[Element „View“ (Format)](./view-element-format.md)

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Erstellen einer Listenansicht](./creating-a-list-view.md)

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Benutzerdefinierte Steuerelemente](./creating-custom-controls.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
