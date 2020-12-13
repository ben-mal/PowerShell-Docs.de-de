---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Name“ für View (Format)
description: Element „Name“ für View (Format)
ms.openlocfilehash: 5781bcdf7a0e1eb5e9c7e97bb6acc0a383dc0262
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666455"
---
# <a name="name-element-for-view-format"></a>Element „Name“ für View (Format)

Gibt den Namen an, der zum Identifizieren der Sicht verwendet wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Name-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Name` Elements beschrieben. `Name`Für jede Ansicht ist nur ein-Element zulässig.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „View“ (Format)](./view-element-format.md)|Definiert eine Ansicht, die zum Anzeigen der Member von einem oder mehreren .NET-Objekten verwendet wird.|

## <a name="text-value"></a>Textwert

Geben Sie einen eindeutigen anzeigen Amen für die Ansicht an. Dieser Name kann einen Verweis auf den Typ der Sicht enthalten (z. b. eine Tabellen-oder Listenansicht), welches Objekt oder welche Gruppe von Objekten die Sicht verwenden, welcher Befehl die Objekte zurückgibt, oder eine Kombination dieser Elemente.

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu den verschiedenen Sicht Typen finden Sie in den folgenden Themen: [Tabellenansicht](./creating-a-table-view.md), [Listenansicht](./creating-a-list-view.md), [Breite Ansicht](./creating-a-wide-view.md)und [benutzerdefinierte Sicht](./creating-custom-controls.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt ein- `View` Element, das eine Tabellenansicht für das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt definiert. Der Name der Sicht lautet "Service".

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Listenansicht](./creating-a-list-view.md)

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Erstellen von benutzerdefinierten Steuerelementen](./creating-custom-controls.md)

[Element „View“ (Format)](./view-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
