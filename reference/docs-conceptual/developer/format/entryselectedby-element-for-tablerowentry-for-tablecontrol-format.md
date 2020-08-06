---
title: Entryselectedby-Element für tablerowentry für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 047a10fb6b38dfa8f78a7741fd50b781d4a14b6d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787698"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a>Element „EntrySelectedBy“ für TableRowEntry für TableControl (Format)

Definiert die .NET-Typen, die diese Definition der Tabellen Sicht verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) entryselectedby-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „SelectionCondition“ für EntrySelectedBy für TableControl (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|Optionales Element.<br /><br /> Definiert die Bedingung, die vorhanden sein muss, damit diese Tabellen Sicht Definition verwendet werden muss.|
|[Element „SelectionSetName“ für EntrySelectedBy für TableControl (Format)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|Optionales Element.<br /><br /> Gibt eine Gruppe von .NET-Typen an, die diese Tabellen Sicht Definition verwenden.|
|[Element „TypeName“ für EntrySelectedBy für TableControl (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|Optionales Element.<br /><br /> Gibt einen .NET-Typ an, der diese Tabellen Sicht Definition verwendet.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Tablerowentry-Element für tablecontrol (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|Definiert die Daten, die in einer Zeile der Tabelle angezeigt werden.|

## <a name="remarks"></a>Bemerkungen

Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für eine Tabellen Sicht Definition angeben. Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.

Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für die zu verwendende Definition vorhanden sein muss, z. b. Wenn ein Objekt über eine bestimmte Eigenschaft verfügt oder ein bestimmter Eigenschafts Wert oder ein bestimmtes Skript als ausgewertet wird `true` . Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Verwendung eines Ansichts Eintrags oder eines Elements](./defining-conditions-for-displaying-data.md).

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt ein- `TableRowEntry` Element, das verwendet wird, um die Eigenschaften des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts anzuzeigen.

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName>PropertyForFirstColumn</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName>PropertyForSecondColumn</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Element „SelectionCondition“ für EntrySelectedBy für TableControl (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[Element „SelectionSetName“ für EntrySelectedBy für TableControl (Format)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[Tablerowentry-Element für tablecontrol (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[Element „TypeName“ für EntrySelectedBy für TableControl (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
