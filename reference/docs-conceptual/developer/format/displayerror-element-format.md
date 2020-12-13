---
ms.date: 09/13/2016
ms.topic: reference
title: Element „DisplayError“ (Format)
description: Element „DisplayError“ (Format)
ms.openlocfilehash: fb54df86a3558263687a8c417870495b7066f563
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649932"
---
# <a name="displayerror-element-format"></a>Element „DisplayError“ (Format)

Gibt an, dass die Zeichenfolge #Err angezeigt wird, wenn ein Fehler beim Anzeigen eines Daten Abschnitts auftritt.

Configuration-Element (Format) DefaultSettings-Element (Format) Display Error-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `DisplayError` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „DefaultSettings“ (Format)](./defaultsettings-element-format.md)|Definiert allgemeine Einstellungen, die für alle Sichten der Formatierungs Datei gelten.|

## <a name="remarks"></a>Bemerkungen

Wenn ein Fehler auftritt, während versucht wird, ein Datenelement anzuzeigen, wird der Speicherort der Datenstandard mäßig leer gelassen. Wenn dieses Element auf true festgelegt ist, wird die #Err Zeichenfolge angezeigt.

## <a name="see-also"></a>Weitere Informationen

[Element „DefaultSettings“ (Format)](./defaultsettings-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
