---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)
description: Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)
ms.openlocfilehash: 3967be86a1d6c12c7215ef19d50bac9fafd5ad6d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648282"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a>Element „CustomEntry“ für CustomControl für Controls für Configuration (Format)

Stellt eine Definition des allgemeinen Steuer Elements bereit. Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.

Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für die Konfiguration (Format)

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
|[Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Definiert die .NET-Typen, die die Definition des allgemeinen Steuer Elements oder die Bedingung verwenden, die für die Verwendung dieses Steuer Elements vorhanden sein muss.|
|[CustomItem-Element für customentry für Steuerelemente für die Konfiguration](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|Erforderliches Element.<br /><br /> Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Customentries-Element für CustomControl für Configuration (Format)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|Stellt die Definitionen des allgemeinen Steuer Elements bereit.|

## <a name="remarks"></a>Bemerkungen

In den meisten Fällen ist nur eine Definition für jedes gängige benutzerdefinierte Steuerelement erforderlich, aber es ist möglich, mehrere Definitionen zu verwenden, wenn Sie das gleiche Steuerelement verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen. In diesen Fällen können Sie eine separate Definition für jedes Objekt oder jede Gruppe von Objekten bereitstellen.

## <a name="see-also"></a>Weitere Informationen

[Customentries-Element für CustomControl für Configuration (Format)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[CustomItem-Element für customentry für Steuerelemente für die Konfiguration](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
