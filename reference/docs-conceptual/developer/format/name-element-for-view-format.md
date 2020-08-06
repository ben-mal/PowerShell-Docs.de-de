---
title: Name-Element für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 670b089f850fa4b39b7b100ca1e1ce45b05ea72d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773231"
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
