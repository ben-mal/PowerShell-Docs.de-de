---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomEntry“ für CustomEntries für CustomControl für View (Format)
description: Element „CustomEntry“ für CustomEntries für CustomControl für View (Format)
ms.openlocfilehash: ff481f13e6f16267bdda4c3053faebc96d9a6d3a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646045"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a>Element „CustomEntry“ für CustomEntries für CustomControl für View (Format)

Stellt eine Definition der benutzerdefinierten Steuerelement Ansicht bereit.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries for View (Format)

## <a name="syntax"></a>Syntax

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomEntry` Elements beschrieben. Sie müssen die Elemente angeben, die in der Definition angezeigt werden.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Entryselectedby-Element für customentry für View (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Definiert die .NET-Typen, die die Definition der benutzerdefinierten Steuerelement Ansicht oder die Bedingung verwenden, die für die Verwendung dieser Definition vorhanden sein muss.|
|[CustomItem-Element für customentry für View (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Definiert ein Steuerelement für die benutzerdefinierte Steuerelement Definition.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomEntries“ für CustomControl für View (Format)](./customentries-element-for-customcontrol-for-view-format.md)|Stellt die Definitionen der benutzerdefinierten Steuerelement Ansicht bereit. Die benutzerdefinierte Steuerelement Ansicht muss mindestens eine Definition angeben.|

## <a name="remarks"></a>Bemerkungen

In den meisten Fällen ist nur eine Definition für jede benutzerdefinierte Steuerelement Ansicht erforderlich, aber es ist möglich, mehrere Definitionen zu verwenden, wenn Sie dieselbe Ansicht verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen. In diesen Fällen können Sie eine separate Definition für jedes Objekt oder jede Gruppe von Objekten bereitstellen.

## <a name="see-also"></a>Weitere Informationen

[Element „CustomControl“ für View (Format)](./customcontrol-element-for-view-format.md)

[CustomItem-Element für customentry für View (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Entryselectedby-Element für customentry für View (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
