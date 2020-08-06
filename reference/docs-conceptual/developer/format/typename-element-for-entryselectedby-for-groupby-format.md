---
title: Tyname-Element für entryselectedby für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e62762cf142bd2d20b21ad8f4249285bd3679280
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780266"
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

|Element|BESCHREIBUNG|
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
