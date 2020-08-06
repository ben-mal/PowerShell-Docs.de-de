---
title: Customentries-Element für CustomControl für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: a52bd2368044c34a0b73da331785d55597e30260
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783703"
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

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „CustomEntry“ für CustomEntries für Controls für View (Format)](./customentry-element-for-customentries-for-controls-for-view-format.md)|Erforderliches Element.<br /><br /> Stellt eine Definition des-Steuer Elements bereit.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „CustomControl“ für Control für Controls für View (Format)](./customcontrol-element-for-control-for-controls-for-view-format.md)|Definiert das Steuerelement, das von der Ansicht verwendet wird.|

## <a name="remarks"></a>Bemerkungen

In den meisten Fällen verfügt ein Steuerelement nur über eine Definition, die in einem einzelnen `CustomEntry` Element angegeben wird. Es ist jedoch möglich, mehrere Definitionen bereitzustellen, wenn Sie das gleiche Steuerelement zum Anzeigen verschiedener .NET-Objekte verwenden möchten. In diesen Fällen können Sie ein- `CustomEntry` Element für jedes Objekt oder jede Gruppe von Objekten definieren.

## <a name="see-also"></a>Weitere Informationen

[Element „CustomEntry“ für CustomEntries für Controls für View (Format)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Element „CustomControl“ für Control für Controls für View (Format)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
