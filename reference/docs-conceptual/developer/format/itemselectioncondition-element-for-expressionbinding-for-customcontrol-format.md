---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ItemSelectionCondition“ für ExpressionBinding für CustomControl (Format)
description: Element „ItemSelectionCondition“ für ExpressionBinding für CustomControl (Format)
ms.openlocfilehash: 38c88ad47e57cd20902c6b8aabdb0b8e8b682ba4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648033"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a>Element „ItemSelectionCondition“ für ExpressionBinding für CustomControl (Format)

Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss. Es gibt keine Beschränkung für die Anzahl der Auswahl Bedingungen, die für ein Steuerelement angegeben werden können. Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries for View (Format) customItem-Element für customentry für das View (Format) ExpressionBinding-Element für customItem für CustomControl für View (Format) itemselectioncondition-Element für Ausdrucks Bindung für CustomControl für View (Format)

## <a name="syntax"></a>Syntax

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ItemSelectionCondition` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[PropertyName-Element für itemselectioncondition für CustomControl für View (Format](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Gibt die .net-Eigenschaft an, die die Bedingung auslöst.|
|[Element „ScriptBlock“ für ItemSeclectionCondition für CustomControl für View (Format)](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Gibt das Skript an, das die Bedingung auslöst.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „ExpressionBinding“ für CustomItem für CustomControl für View (Format)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|Definiert die Daten, die vom-Steuerelement angezeigt werden.|

## <a name="remarks"></a>Bemerkungen

Sie können einen Eigenschaftsnamen oder ein Skript für diese Bedingung angeben, aber nicht beides angeben.

## <a name="see-also"></a>Weitere Informationen

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)

[Element „ExpressionBinding“ für CustomItem für CustomControl für View (Format)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
