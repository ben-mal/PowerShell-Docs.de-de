---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für EntrySelectedBy für CustomEntry für View (Format)
description: Element „TypeName“ für EntrySelectedBy für CustomEntry für View (Format)
ms.openlocfilehash: 72bb88bccc2bbd62f7ed160b820cf9169cb69341
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645752"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a>Element „TypeName“ für EntrySelectedBy für CustomEntry für View (Format)

Gibt einen .NET-Typ an, der diese Definition der benutzerdefinierten Steuerelement Ansicht verwendet. Es gibt keine Beschränkung für die Anzahl von Typen, die für eine Definition angegeben werden können.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) entryselectedby-Element für customentry für View (Format) tykame-Element für entryselectedby für customentry

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
|[Entryselectedby-Element für customentry für View (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Definiert die .NET-Typen, die diese Definition für die benutzerdefinierte Steuerelement Ansicht oder die Bedingung verwenden, die für die Verwendung dieser Definition vorhanden sein muss.|

## <a name="text-value"></a>Textwert

Geben Sie den voll qualifizierten Namen des .net-Typs an, z `System.IO.DirectoryInfo` . b..

## <a name="remarks"></a>Bemerkungen

Für jede Definition einer benutzerdefinierten Steuerelement Ansicht muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.

Weitere Informationen zu den Komponenten einer benutzerdefinierten Steuerelement Ansicht finden Sie unter [Erstellen von benutzerdefinierten Steuerelementen](./creating-custom-controls.md).

## <a name="see-also"></a>Weitere Informationen

[Erstellen von benutzerdefinierten Steuerelementen](./creating-custom-controls.md)

[Entryselectedby-Element für customentry für View (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
