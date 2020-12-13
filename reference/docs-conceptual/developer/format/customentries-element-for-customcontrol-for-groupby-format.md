---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomEntries“ für CustomControl für GroupBy (Format)
description: Element „CustomEntries“ für CustomControl für GroupBy (Format)
ms.openlocfilehash: cde59d38b83930cb64a3a0040891783e4ab96723
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666789"
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
