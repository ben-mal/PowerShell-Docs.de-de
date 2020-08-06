---
title: Typname-Element für selectioncondition für entryselectedby für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: bc58d630e65b316f9223bf3c529f928358e38ebc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787374"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>Element „TypeName“ für SelectionCondition für EntrySelectedBy für ListControl (Format)

Gibt einen .NET-Typ an, der die Bedingung auslöst. Wenn dieser Typ vorhanden ist, wird der Listeneintrag verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListEntries für ListControl (Format) entryselectedby Element für ListEntry für ListControl (Format) selectioncondition-Element für entryselectedby für ListControl (Format) Typname-Element für selectioncondition für entryselectedby für ListControl (Format)

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
|[Element „SelectionCondition“ für EntrySelectedBy für ListControl (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Definiert die Bedingung, die für die Verwendung dieses Listen Eintrags vorhanden sein muss.|

## <a name="text-value"></a>Textwert

Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..

## <a name="remarks"></a>Bemerkungen

Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben. Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).

Weitere Informationen zu anderen Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Listenansicht](./creating-a-list-view.md)

[Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md)

[Element „SelectionCondition“ für EntrySelectedBy für ListControl (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
