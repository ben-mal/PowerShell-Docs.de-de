---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für ViewSelectedBy (Format)
description: Element „SelectionSetName“ für ViewSelectedBy (Format)
ms.openlocfilehash: a1a1816761715a138bcb3c2bd4cb9dbbb2f9cb92
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654907"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a>Element „SelectionSetName“ für ViewSelectedBy (Format)

Gibt einen Satz von .NET-Objekten an, die von der Sicht angezeigt werden.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) viewselectedby-Element (Format) selectionsetname-Element für viewselectedby (Format)

## <a name="syntax"></a>Syntax

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „ViewSelectedBy“ (Format)](./viewselectedby-element-format.md)|Definiert die .NET-Objekte, die von der Ansicht angezeigt werden.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen des Auswahl Satzes an, der durch das- `Name` Element für den Auswahl Satz definiert wird.

## <a name="remarks"></a>Bemerkungen

Sie können Auswahl Sätze verwenden, wenn Sie über einen Satz verwandter Objekte verfügen, auf die Sie verweisen möchten, indem Sie einen einzelnen Namen verwenden, z. b. eine Gruppe von Objekten, die durch Vererbung verknüpft sind. Weitere Informationen zum Definieren und referenzieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie einen Auswahl Satz für eine Listenansicht angeben. Das gleiche Schema wird für Tabellen-, breiten-und benutzerdefinierte Sichten verwendet.

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>Weitere Informationen

[Definieren von Auswahlgruppen](./defining-selection-sets.md)

[Element „ViewSelectedBy“ (Format)](./viewselectedby-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
