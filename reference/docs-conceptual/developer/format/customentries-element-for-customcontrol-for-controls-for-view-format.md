---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomEntries“ für CustomControl für Controls für View (Format)
description: Element „CustomEntries“ für CustomControl für Controls für View (Format)
ms.openlocfilehash: 43187294a407d08f765f8c42aba25d13dba6d901
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652367"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a>Element „CustomEntries“ für CustomControl für Controls für View (Format)

Stellt die Definitionen für das-Steuerelement bereit. Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelemente Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Control für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für Steuerelemente für Ansicht (Format)

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
|[Element „CustomEntry“ für CustomEntries für Controls für View (Format)](./customentry-element-for-customentries-for-controls-for-view-format.md)|Erforderliches Element.<br /><br /> Stellt eine Definition des-Steuer Elements bereit.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomControl“ für Control für Controls für View (Format)](./customcontrol-element-for-control-for-controls-for-view-format.md)|Definiert das Steuerelement, das von der Ansicht verwendet wird.|

## <a name="remarks"></a>Bemerkungen

In den meisten Fällen verfügt ein Steuerelement nur über eine Definition, die in einem einzelnen `CustomEntry` Element angegeben wird. Es ist jedoch möglich, mehrere Definitionen bereitzustellen, wenn Sie das gleiche Steuerelement zum Anzeigen verschiedener .NET-Objekte verwenden möchten. In diesen Fällen können Sie ein- `CustomEntry` Element für jedes Objekt oder jede Gruppe von Objekten definieren.

## <a name="see-also"></a>Weitere Informationen

[Element „CustomEntry“ für CustomEntries für Controls für View (Format)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Element „CustomControl“ für Control für Controls für View (Format)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
