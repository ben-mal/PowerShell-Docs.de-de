---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für ItemSeclectionCondition für ListControl (Format)
description: Element „ScriptBlock“ für ItemSeclectionCondition für ListControl (Format)
ms.openlocfilehash: 1e518f898e0e1e62ca64f9897b1323cc6dd89ae9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665060"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a>Element „ScriptBlock“ für ItemSeclectionCondition für ListControl (Format)

Gibt das Skript an, das die Bedingung auslöst. Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und das Listenelement wird verwendet. Dieses Element wird beim Definieren einer Listenansicht verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListEntries für ListControl (Format) ListItems-Element für ListEntry für ListControl (Format) ListItem-Element für ListItems für das Listen Steuerelement (Format) itemselectioncondition-Element für ListItem für ListControl (Format) ScriptBlock-Element für itemselectioncondition für ListControl (Format)

## <a name="syntax"></a>Syntax

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und die übergeordneten Elemente des- `ScriptBlock` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „ItemSelectionCondition“ für ListItem für ListControl (Format)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|Definiert die Bedingung, die vorhanden sein muss, damit dieses Listenelement verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie das auszuwertende Skript an.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element verwendet wird, können Sie das-Element nicht angeben, `PropertyName` Wenn Sie die Auswahlbedingung definieren.

## <a name="see-also"></a>Weitere Informationen

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
