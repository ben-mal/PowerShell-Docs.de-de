---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomControl“ für View (Format)
description: Element „CustomControl“ für View (Format)
ms.openlocfilehash: 41352be55f0c03b2eaca0dbe2d7345e7cf804a7c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655476"
---
# <a name="customcontrol-element-for-view-format"></a>Element „CustomControl“ für View (Format)

Definiert ein benutzerdefiniertes Steuerelement Format für die Ansicht.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomControl` Elements beschrieben. Sie müssen ein untergeordnetes Element angeben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomEntries“ für CustomControl für View (Format)](./customentries-element-for-customcontrol-for-view-format.md)|Erforderliches Element.<br /><br /> Stellt die Definitionen der benutzerdefinierten Steuerelement Ansicht bereit.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „View“ (Format)](./view-element-format.md)|Definiert eine Ansicht, die verwendet wird, um ein oder mehrere .NET-Objekte anzuzeigen.|

## <a name="remarks"></a>Bemerkungen

In den meisten Fällen ist nur eine Definition für jede Steuerelement Ansicht erforderlich, aber es ist möglich, mehrere Definitionen bereitzustellen, wenn Sie die gleiche Ansicht verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen. In diesen Fällen können Sie eine separate Definition für jedes Objekt oder jede Gruppe von Objekten bereitstellen.

## <a name="see-also"></a>Weitere Informationen

[Element „CustomEntries“ für CustomControl für View (Format)](./customentries-element-for-customcontrol-for-view-format.md)

[Element „View“ (Format)](./view-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
