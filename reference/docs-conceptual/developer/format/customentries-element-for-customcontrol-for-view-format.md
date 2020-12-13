---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomEntries“ für CustomControl für View (Format)
description: Element „CustomEntries“ für CustomControl für View (Format)
ms.openlocfilehash: 6e757bccdface2503667f8786462a2b43134a07d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649983"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a>Element „CustomEntries“ für CustomControl für View (Format)

Stellt die Definitionen der benutzerdefinierten Steuerelement Ansicht bereit. Die benutzerdefinierte Steuerelement Ansicht muss mindestens eine Definition angeben.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für Ansicht (Format)

## <a name="syntax"></a>Syntax

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomControlEntries` Elements beschrieben. Sie müssen mindestens ein untergeordnetes Element angeben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Customentry-Element für customentries für View (Format)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|Erforderliches Element.<br /><br /> Stellt eine Definition der benutzerdefinierten Steuerelement Ansicht bereit.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomControl“ für View (Format)](./customcontrol-element-for-view-format.md)|Erforderliches Element.<br /><br /> Definiert ein benutzerdefiniertes Steuerelement Format für die Ansicht.|

## <a name="remarks"></a>Bemerkungen

In den meisten Fällen verfügt ein Steuerelement nur über eine Definition, die in einem einzelnen `CustomEntry` Element definiert ist. Es ist jedoch möglich, mehrere Definitionen zu verwenden, wenn Sie das gleiche Steuerelement verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen. In diesen Fällen können Sie ein- `CustomEntry` Element für jedes Objekt oder jede Gruppe von Objekten definieren.

## <a name="see-also"></a>Weitere Informationen

[Element „CustomControl“ für View (Format)](./customcontrol-element-for-view-format.md)

[Customentry-Element für customentries für View (Format)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
