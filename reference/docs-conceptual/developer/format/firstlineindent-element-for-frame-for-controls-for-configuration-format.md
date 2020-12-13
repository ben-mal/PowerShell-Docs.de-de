---
ms.date: 09/13/2016
ms.topic: reference
title: Element „FirstLineIndent“ für Frame für Controls für Configuration (Format)
description: Element „FirstLineIndent“ für Frame für Controls für Configuration (Format)
ms.openlocfilehash: 59a41410160879c2414819de4d367ecdedd8e182
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660166"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-configuration-format"></a>Element „FirstLineIndent“ für Frame für Controls für Configuration (Format)

Gibt an, wie viele Zeichen die erste Zeile der Daten nach rechts verschoben wird. Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.

Konfigurationselement-Steuerelement (Format) Controls-Element des Configuration (Format)-Steuer Elements für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für Configuration (Format) customItem-Element für customentry für Steuerelemente für das Configuration Frame-Element für customItem für Steuerelemente für das Configuration (Format) FirstLineIndent-Element für Frame für Steuerelemente für die Konfiguration (Format)

## <a name="syntax"></a>Syntax

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `FirstLineIndent` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „Frame“ für CustomItem für Controls für Configuration (Format)](./frame-element-for-customitem-for-controls-for-configuration-format.md)|Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.|

## <a name="text-value"></a>Textwert

Geben Sie die Anzahl der Zeichen an, die Sie in die erste Zeile der Daten verschieben möchten.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element angegeben ist, können Sie das [firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) -Element nicht angeben.

## <a name="see-also"></a>Weitere Informationen

[Element „FirstLineHanging“ für Frame für Controls für Configuration (Format)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[Element „Frame“ für CustomItem für Controls für Configuration (Format)](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
