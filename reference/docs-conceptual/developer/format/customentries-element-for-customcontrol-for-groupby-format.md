---
title: Customentries-Element für CustomControl für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 2221d1bb94159697ff10466e4606d6d54e117e30
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785947"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a>Element „CustomEntries“ für CustomControl für GroupBy (Format)

Stellt die Definitionen für das-Steuerelement bereit. Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format)

## <a name="syntax"></a>Syntax

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und übergeordnete Elemente des- `CustomEntries` Elements beschrieben. Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die angegeben werden können.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomEntry“ für CustomControl für GroupBy (Format)](./customentry-element-for-customcontrol-for-groupby-format.md)|Erforderliches Element.<br /><br /> Stellt eine Definition des-Steuer Elements bereit.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomControl“ für GroupBy (Format)](./customcontrol-element-for-groupby-format.md)|Definiert das benutzerdefinierte Steuerelement, das die neue Gruppe anzeigt.|

## <a name="remarks"></a>Bemerkungen

In den meisten Fällen verfügt ein Steuerelement nur über eine Definition, die in einem einzelnen `CustomEntry` Element angegeben wird. Es ist jedoch möglich, mehrere Definitionen bereitzustellen, wenn Sie das gleiche Steuerelement verwenden möchten, um unterschiedliche Gruppen anzuzeigen. In diesen Fällen können Sie ein- `CustomEntry` Element für eine Gruppe definieren.

## <a name="see-also"></a>Weitere Informationen

[Element „CustomEntry“ für CustomEntries für Controls für View (Format)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Element „CustomControl“ für GroupBy (Format)](./customcontrol-element-for-groupby-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
