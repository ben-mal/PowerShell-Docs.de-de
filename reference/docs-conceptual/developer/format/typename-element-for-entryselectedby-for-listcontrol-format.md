---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für EntrySelectedBy für ListControl (Format)
description: Element „TypeName“ für EntrySelectedBy für ListControl (Format)
ms.openlocfilehash: 6fc5a2385fde3140abbc984e3da6a4dda483b2a8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645655"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a>Element „TypeName“ für EntrySelectedBy für ListControl (Format)

Gibt einen .NET-Typ an, der diesen Eintrag in der Listenansicht verwendet. Es gibt keine Beschränkung für die Anzahl von Typen, die für einen Listeneintrag angegeben werden können.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) entryselectedby-Element für ListEntry (Format) Typname-Element für entryselectedby für ListControl (Format)

## <a name="syntax"></a>Syntax

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Entryselectedby-Element für ListEntry (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|Definiert die .NET-Typen, die diesen Listeneintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.|

## <a name="text-value"></a>Textwert

Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..

## <a name="remarks"></a>Bemerkungen

Für jeden Listeneintrag muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.

Weitere Informationen zur Verwendung dieses Elements in einer Listenansicht finden Sie in der [Listenansicht](./creating-a-list-view.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie einen Auswahl Satz für einen Eintrag einer Listenansicht angeben.

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Listenansicht](./creating-a-list-view.md)

[Entryselectedby-Element für ListEntry (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[Selectionsetname-Element für entryselectedby für ListEntry (Format)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
