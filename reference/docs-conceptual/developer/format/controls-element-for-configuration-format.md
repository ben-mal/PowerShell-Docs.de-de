---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Controls“ für Configuration (Format)
description: Element „Controls“ für Configuration (Format)
ms.openlocfilehash: 53f874ddccf3b4f1f0a23aad608e786524bde830
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668098"
---
# <a name="controls-element-for-configuration-format"></a>Element „Controls“ für Configuration (Format)

Definiert die allgemeinen Steuerelemente, die von allen Ansichten der Formatierungs Datei verwendet werden können.

Configuration-Element (Format) steuert Element der Konfiguration (Format)

## <a name="syntax"></a>Syntax

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Controls` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „Control“ für Controls für Configuration (Format)](./control-element-for-controls-for-configuration-format.md)|Erforderliches Element.<br /><br /> Definiert ein gängiges Steuerelement, das von allen Ansichten der Formatierungs Datei verwendet werden kann.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „Configuration“ (Format)](./configuration-element-format.md)|Stellt das Element der obersten Ebene einer Formatierungs Datei dar.|

## <a name="remarks"></a>Bemerkungen

Sie können eine beliebige Anzahl von allgemeinen Steuerelementen erstellen. Für jedes Steuerelement müssen Sie den Namen angeben, der zum Verweisen auf das Steuerelement und die Komponenten des Steuer Elements verwendet wird.

## <a name="see-also"></a>Weitere Informationen

[Element „Configuration“ (Format)](./configuration-element-format.md)

[Element „Control“ für Controls für Configuration (Format)](./control-element-for-controls-for-configuration-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
