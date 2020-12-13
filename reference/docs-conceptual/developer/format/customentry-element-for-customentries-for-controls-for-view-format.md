---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomEntry“ für CustomEntries für Controls für View (Format)
description: Element „CustomEntry“ für CustomEntries für Controls für View (Format)
ms.openlocfilehash: a525b198c8f595e04dc0804d36b5533b94f43c6b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646082"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a>Element „CustomEntry“ für CustomEntries für Controls für View (Format)

Stellt eine Definition des-Steuer Elements bereit. Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelemente Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Control für Steuerelemente für View (Format) customentries-Element für CustomControl for View (Format) customentry-Element für customentries für View (Format)

## <a name="syntax"></a>Syntax

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und die übergeordneten Elemente des- `CustomEntry` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „EntrySelectedBy“ für CustomEntry für Controls für View (Format)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|Optionales Element.<br /><br /> Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.|
|[Element „CustomItem“ für CustomEntry für Controls für View (Format)](./customitem-element-for-customentry-for-controls-for-view-format.md)|Erforderliches Element.<br /><br /> Definiert, wie das-Steuerelement die Daten anzeigt.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomEntries“ für CustomControl für View (Format)](./customentries-element-for-customcontrol-for-view-format.md)|Stellt die Definitionen für das-Steuerelement bereit.|

## <a name="remarks"></a>Bemerkungen

## <a name="see-also"></a>Weitere Informationen

[Element „CustomEntries“ für CustomControl für View (Format)](./customentries-element-for-customcontrol-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
