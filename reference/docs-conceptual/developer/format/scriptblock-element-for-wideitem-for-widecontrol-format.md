---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für WideItem für WideControl (Format)
description: Element „ScriptBlock“ für WideItem für WideControl (Format)
ms.openlocfilehash: 68e47926e5e6b846c8a0a3dbc16d1f0d59f11dee
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659867"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a>Element „ScriptBlock“ für WideItem für WideControl (Format)

Gibt das Skript an, dessen Wert in der breiten Ansicht angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) wideitem-Element (Format) ScriptBlock-Element für wideitem (Format)

## <a name="syntax"></a>Syntax

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Wideitem-Element (Format)](./wideitem-element-for-widecontrol-format.md)|Definiert den Eigenschafts-oder Skriptblock, dessen Wert in der breiten Ansicht angezeigt wird.|

## <a name="text-value"></a>Textwert

Geben Sie das Skript an, dessen Wert angezeigt wird.

## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt ein- `WideItem` Element, das ein Skript definiert, dessen Wert in der Ansicht angezeigt wird.

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a>Weitere Informationen

[Wideitem-Element (Format)](./wideitem-element-for-widecontrol-format.md)

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
