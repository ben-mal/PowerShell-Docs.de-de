---
title: CustomControl-Element für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 660e8fd6531862790a2af7ab27a82e073c230693
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786049"
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
