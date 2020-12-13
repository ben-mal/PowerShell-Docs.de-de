---
ms.date: 09/13/2016
ms.topic: reference
title: Element „EntrySelectedBy“ für WideEntry (Format)
description: Element „EntrySelectedBy“ für WideEntry (Format)
ms.openlocfilehash: 246a1967300ab0551f376c4799deac275068308c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660254"
---
# <a name="entryselectedby-element-for-wideentry-format"></a>Element „EntrySelectedBy“ für WideEntry (Format)

Definiert die .NET-Typen, die diese Definition der breiten Ansicht verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format)

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
|[Selectioncondition-Element für entryselectedby für wideentry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|Optionales Element.<br /><br /> Definiert die Bedingung, die vorhanden sein muss, damit diese Breite Sicht Definition verwendet werden muss.|
|[Selectionsetname-Element für entryselectedby für wideentry (Format)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|Optionales Element.<br /><br /> Gibt einen Satz von .NET-Typen an, die diese Breite Sicht Definition verwenden.|
|[Element „TypeName“ für EntrySelectedBy für WideEntry (Format)](./typename-element-for-entryselectedby-for-wideentry-format.md)|Optionales Element.<br /><br /> Gibt einen .NET-Typ an, der diese Breite Sicht Definition verwendet.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Wideentry-Element (Format)](./wideentry-element-for-widecontrol-format.md)|Stellt eine Definition der breiten Ansicht bereit.|

## <a name="remarks"></a>Bemerkungen

Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für eine breite Sicht Definition angeben. Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.

Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für die zu verwendende Definition vorhanden sein muss, z. b. Wenn ein Objekt über eine bestimmte Eigenschaft verfügt oder für einen bestimmten Eigenschafts Wert oder Skript Wert ausgewertet wird `true` . Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).

Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).

## <a name="see-also"></a>Weitere Informationen

[Wideentry-Element (Format)](./wideentry-element-for-widecontrol-format.md)

[Selectioncondition-Element für entryselectedby für wideentry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Selectionsetname-Element für entryselectedby für wideentry (Format)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[Element „TypeName“ für EntrySelectedBy für WideEntry (Format)](./typename-element-for-entryselectedby-for-wideentry-format.md)

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Definieren von Bedingungen für die Datenanzeige](./defining-conditions-for-displaying-data.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
