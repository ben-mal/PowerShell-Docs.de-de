---
title: Customentry-Element für CustomControl für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4df8e5b96868b3814c6d84fa329950bb5345ef6e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785913"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a>Element „CustomEntry“ für CustomControl für GroupBy (Format)

Stellt eine Definition des-Steuer Elements bereit. Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format)

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
|[Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)](./entryselectedby-element-for-customentry-for-groupby-format.md)|Optionales Element.<br /><br /> Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.|
|[Element „CustomItem“ für CustomEntry für GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)|Erforderliches Element.<br /><br /> Definiert, wie das-Steuerelement die Daten anzeigt.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomEntries“ für CustomControl für GroupBy (Format)](./customentries-element-for-customcontrol-for-groupby-format.md)|Stellt die Definitionen für das-Steuerelement bereit.|

## <a name="remarks"></a>Bemerkungen

## <a name="see-also"></a>Weitere Informationen

[Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[Element „CustomItem“ für CustomEntry für GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)

[Element „CustomEntries“ für CustomControl für GroupBy (Format)](./customentries-element-for-customcontrol-for-groupby-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
