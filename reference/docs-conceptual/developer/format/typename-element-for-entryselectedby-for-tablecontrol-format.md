---
title: Tyname-Element für entryselectedby für tablecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: c514d3e6155278ddd3a0565c87e9377dc8419356
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780201"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a>Element „TypeName“ für EntrySelectedBy für TableControl (Format)

Gibt einen .NET-Typ an, der diesen Eintrag der Tabellenansicht verwendet. Es gibt keine Beschränkung für die Anzahl von Typen, die für einen Tabelleneintrag angegeben werden können.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) entryselectedby-Element (Format) Typname-Element für entryselectedby für tablerowentry (Format)

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
|[Entryselectedby-Element (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Definiert die .NET-Typen, die diesen Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen des .net-Typs an.

## <a name="remarks"></a>Bemerkungen

Für jeden Listeneintrag muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Entryselectedby-Element (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
