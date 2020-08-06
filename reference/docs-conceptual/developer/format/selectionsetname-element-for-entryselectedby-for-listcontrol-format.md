---
title: Selectionsetname-Element für entryselectedby für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4315d81da4ceeb7a5b171087434ae15fb09e6592
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785267"
---
# <a name="selectionsetname-element-for-entryselectedby-for-listcontrol-format"></a>Element „SelectionSetName“ für EntrySelectedBy für ListControl (Format)

Gibt eine Gruppe von .NET-Objekten für den Listeneintrag an. Es gibt keine Beschränkung für die Anzahl der Auswahl Sätze, die für einen Eintrag angegeben werden können.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) entryselectedby-Element für ListEntry (Format) selectionsetname-Element für entryselectedby für ListEntry (Format)

## <a name="syntax"></a>Syntax

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Entryselectedby-Element für ListEntry (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|Definiert die .NET-Typen, die diesen Listeneintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen des Auswahl Satzes an.

## <a name="remarks"></a>Bemerkungen

Für jeden Listeneintrag muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.

Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden. Beispielsweise können Sie eine Tabellenansicht und eine Listenansicht für denselben Satz von Objekten erstellen. Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen für eine Sicht](./defining-selection-sets.md).

Weitere Informationen zu den Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie einen Auswahl Satz für einen Eintrag einer Listenansicht angeben.

```xml
<ListEntry>
  <EntrySelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Listenansicht](./creating-a-list-view.md)

[Entryselectedby-Element für ListEntry (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
