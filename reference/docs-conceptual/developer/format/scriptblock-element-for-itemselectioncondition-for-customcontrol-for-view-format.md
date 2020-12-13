---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ScriptBlock“ für ItemSeclectionCondition für CustomControl für View (Format)
description: Element „ScriptBlock“ für ItemSeclectionCondition für CustomControl für View (Format)
ms.openlocfilehash: d762f400f5bb52af314093079fe94223c56d3f31
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665119"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a>Element „ScriptBlock“ für ItemSeclectionCondition für CustomControl für View (Format)

Gibt das Skript an, das die Bedingung auslöst. Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und das-Steuerelement wird verwendet. Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) customItem-Element für customentry für die Ansicht (Format) ExpressionBinding-Element für customItem für CustomControl für View (Format) itemselectioncondition-Element für Ausdrucks Bindung für CustomControl for View (Format) ScriptBlock-Element für itemselectioncondition für CustomControl for View (Format)

## <a name="syntax"></a>Syntax

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Itemselectioncondition-Element für die Ausdrucks Bindung für "CustomControl" für "View" (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie das auszuwertende Skript an.

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element verwendet wird, können Sie beim Definieren der Auswahlbedingung nicht das [propertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) -Element angeben.

## <a name="see-also"></a>Weitere Informationen

[Element „PropertyName“ für ItemSeclectionCondition für CustomControl für View (Format)](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[Itemselectioncondition-Element für die Ausdrucks Bindung für "CustomControl" für "View" (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
