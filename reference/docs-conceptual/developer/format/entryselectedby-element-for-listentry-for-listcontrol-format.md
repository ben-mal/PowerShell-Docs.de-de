---
ms.date: 09/13/2016
ms.topic: reference
title: Element „EntrySelectedBy“ für ListEntry für ListControl (Format)
description: Element „EntrySelectedBy“ für ListEntry für ListControl (Format)
ms.openlocfilehash: 1981c8fae65f494504d6cdd9f59337d555350b07
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652283"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a>Element „EntrySelectedBy“ für ListEntry für ListControl (Format)

Definiert die .NET-Typen, die diese Listen Ansichts Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss. In den meisten Fällen ist nur eine Definition für eine Listenansicht erforderlich. Sie können jedoch mehrere Definitionen für die Listenansicht bereitstellen, wenn Sie die gleiche Listenansicht verwenden möchten, um unterschiedliche Daten für unterschiedliche Objekte anzuzeigen.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListEntry für ListControl (Format) entryselectedby-Element für ListEntry für ListControl (Format)

## <a name="syntax"></a>Syntax

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Selectioncondition-Element für entryselectedby für ListControl (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Optionales Element.<br /><br /> Definiert die Bedingung, die für die Verwendung dieser Listen Ansichts Definition vorhanden sein muss.|
|[Element „SelectionSetName“ für EntrySelectedBy für ListControl (Format)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|Optionales Element.<br /><br /> Gibt eine Gruppe von .NET-Typen an, die diese Listen Ansichts Definition verwenden.|
|[Element „TypeName“ für EntrySelectedBy für ListControl (Format)](./typename-element-for-entryselectedby-for-listcontrol-format.md)|Optionales Element.<br /><br /> Gibt einen .NET-Typ an, der diese Listen Ansichts Definition verwendet.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „ListEntry“ für ListControl (Format)](./listentry-element-for-listcontrol-format.md)|Definiert, wie die Zeilen der Liste angezeigt werden.|

## <a name="remarks"></a>Bemerkungen

Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für eine Listen Ansichts Definition angeben. Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.

Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für die zu verwendende Definition vorhanden sein muss, z. b. Wenn ein Objekt über eine bestimmte Eigenschaft verfügt oder ein bestimmter Eigenschafts Wert oder ein bestimmtes Skript als ausgewertet wird `true` . Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für den Fall, dass Daten angezeigt werden](./defining-conditions-for-displaying-data.md).

Weitere Informationen zu den Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie die-Objekte für eine Listenansicht mithilfe Ihres .net-Typnamens definiert werden.

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a>Weitere Informationen

[Element „ListEntry“ für ListControl (Format)](./listentry-element-for-listcontrol-format.md)

[Element „SelectionCondition“ für EntrySelectedBy für ListControl (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[Element „SelectionSetName“ für EntrySelectedBy für ListControl (Format)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[Element „TypeName“ für EntrySelectedBy für ListControl (Format)](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[Erstellen einer Listenansicht](./creating-a-list-view.md)

[Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
