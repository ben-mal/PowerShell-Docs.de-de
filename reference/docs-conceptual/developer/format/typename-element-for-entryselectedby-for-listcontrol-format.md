---
title: Tyname-Element für entryselectedby für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 5e7b73db5aa597d96141454008c5c58b1827df24
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780218"
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

|Element|BESCHREIBUNG|
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
