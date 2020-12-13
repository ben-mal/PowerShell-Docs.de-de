---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Configuration“ (Format)
description: Element „Configuration“ (Format)
ms.openlocfilehash: 0524736d40dd7a7acb0b6fb61d1438b75672c240
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655688"
---
# <a name="configuration-element-format"></a>Element „Configuration“ (Format)

Stellt das Element der obersten Ebene einer Formatierungs Datei dar.

Konfigurationselement

## <a name="syntax"></a>Syntax

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Configuration` Elements beschrieben. Dieses Element muss das root-Element für jede Formatierungs Datei sein, und dieses Element muss mindestens ein untergeordnetes Element enthalten.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „Controls“ für Configuration (Format)](./controls-element-for-configuration-format.md)|Optionales Element.<br /><br /> Definiert die allgemeinen Steuerelemente, die von allen Ansichten der Formatierungs Datei verwendet werden können.|
|[Element „DefaultSettings“ (Format)](./defaultsettings-element-format.md)|Optionales Element.<br /><br /> Definiert allgemeine Einstellungen, die für alle Sichten der Formatierungs Datei gelten.|
|[Selectionsets-Element Format](./selectionsets-element-format.md)|Optionales Element.<br /><br /> Definiert die allgemeinen Sätze von .NET-Objekten, die von allen Sichten der Formatierungs Datei verwendet werden können.|
|[Element „ViewDefinitions“ (Format)](./viewdefinitions-element-format.md)|Optionales Element.<br /><br /> Definiert die Sichten, die zum Anzeigen von Objekten verwendet werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

Keine.

## <a name="remarks"></a>Bemerkungen

Formatieren von Dateien definieren, wie Objekte angezeigt werden. In den meisten Fällen enthält dieses root-Element ein [viewdefinitions](./viewdefinitions-element-format.md) -Element, das die Tabellen-, Listen-und breiten Ansichten der Formatierungs Datei definiert. Zusätzlich zu den Sicht Definitionen kann die Formatierungs Datei allgemeine Auswahl Sätze, Einstellungen und Steuerelemente definieren, die diese Sichten verwenden können.

## <a name="see-also"></a>Weitere Informationen

[Element „Controls“ für Configuration (Format)](./controls-element-for-configuration-format.md)

[Element „DefaultSettings“ (Format)](./defaultsettings-element-format.md)

[Element „SelectionSets“ (Format)](./selectionsets-element-format.md)

[Element „ViewDefinitions“ (Format)](./viewdefinitions-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
