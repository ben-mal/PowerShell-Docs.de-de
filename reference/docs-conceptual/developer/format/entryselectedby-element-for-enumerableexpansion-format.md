---
title: Entryselectedby-Element für enumerableexpansion (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 031bf10cfb1aed2c737fdd53fa4f20f025351d40
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783669"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a>Element „EntrySelectedBy“ für EnumerableExpansion (Format)

Definiert die .NET-Typen, die diese Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.

Configuration-Element (Format) DefaultSettings-Element (Format) enumerableerweiterungen-Element (Format) enumerableweiterung-Element (Format) entryselectedby-Element für enumerableweiterung (Format)

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

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|Optionales Element.<br /><br /> Definiert die Bedingung, die vorhanden sein muss, um die Auflistungs Objekte dieser Definition zu erweitern.|
|[Element „SelectionSetName“ für EntrySelectedBy für EnumerableExpansion (Format)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|Optionales Element.<br /><br /> Gibt eine Gruppe von .NET-Typen an, die diese Definition der Erweiterung von Auflistungs Objekten verwenden.|
|[Element „TypeName“ für EntrySelectedBy für EnumerableExpansion (Format)](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|Optionales Element.<br /><br /> Gibt einen .NET-Typ an, der diese Definition der Erweiterung von Auflistungs Objekten verwendet.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „EnumerableExpansion“ (Format)](./enumerableexpansion-element-format.md)|Definiert, wie bestimmte .net-Auflistungs Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.|

## <a name="remarks"></a>Bemerkungen

Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für einen Definitions Eintrag angeben. Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.

Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für die zu verwendende Definition vorhanden sein muss, z. b. Wenn ein Objekt über eine bestimmte Eigenschaft verfügt oder ein bestimmter Eigenschafts Wert oder ein bestimmtes Skript als ausgewertet wird `true` . Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Weitere Informationen

[Definieren von Bedingungen für die Datenanzeige](./defining-conditions-for-displaying-data.md)

[Element „EnumerableExpansion“ (Format)](./enumerableexpansion-element-format.md)

[Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Element „SelectionSetName“ für EntrySelectedBy für EnumerableExpansion (Format)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Element „TypeName“ für EntrySelectedBy für EnumerableExpansion (Format)](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
