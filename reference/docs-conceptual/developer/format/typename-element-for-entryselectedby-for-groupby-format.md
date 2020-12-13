---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für EntrySelectedBy für GroupBy (Format)
description: Element „TypeName“ für EntrySelectedBy für GroupBy (Format)
ms.openlocfilehash: 07cc92e9c501aa0eb2d219e416851be0fcd80f47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645715"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a>Element „TypeName“ für EntrySelectedBy für GroupBy (Format)

Gibt einen .NET-Typ an, der diese Definition des benutzerdefinierten Steuer Elements verwendet. Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) entryselectedby-Element für customentry für GroupBy (Format) tykename-Element für entryselectedby für GroupBy (Format)

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
|[Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)](./entryselectedby-element-for-customentry-for-groupby-format.md)|Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..

## <a name="remarks"></a>Bemerkungen

Für jede Steuerelement Definition muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.

Weitere Informationen zu den Komponenten einer benutzerdefinierten Steuerelement Ansicht finden Sie unter [Erstellen von benutzerdefinierten Steuerelementen](./creating-custom-controls.md).

## <a name="see-also"></a>Weitere Informationen

[Erstellen von benutzerdefinierten Steuerelementen](./creating-custom-controls.md)

[Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
