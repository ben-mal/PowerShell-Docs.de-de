---
title: Itemselectioncondition-Element für ListItem für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: f5c388928668e03b96923130fb5849f637548f12
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783618"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a>Element „ItemSelectionCondition“ für ListItem für ListControl (Format)

Definiert die Bedingung, die vorhanden sein muss, damit dieses Listenelement verwendet werden muss.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListEntries für ListControl (Format) ListItems-Element für ListEntry für ListControl (Format) ListItem-Element für ListItems für ListControl (Format) itemselectioncondition-Element für ListItem für ListControl (Format)

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
|[Element „PropertyName“ für ItemSeclectionCondition für ListControl (Format)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|Optionales Element.<br /><br /> Gibt die .net-Eigenschaft an, die die Bedingung auslöst.|
|[Element „ScriptBlock“ für ItemSeclectionCondition für ListControl (Format)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|Optionales Element.<br /><br /> Gibt das Skript an, das die Bedingung auslöst.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „ListItem“ für ListItems für ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Definiert die Eigenschaft oder das Skript, dessen Wert in einer Zeile der Listenansicht angezeigt wird.|

## <a name="remarks"></a>Bemerkungen

Sie können einen Eigenschaftsnamen oder ein Skript für diese Bedingung angeben, aber nicht beides angeben.

## <a name="see-also"></a>Weitere Informationen

[Element „ListItem“ für ListItems für ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Element „PropertyName“ für ItemSeclectionCondition für ListControl (Format)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[Element „ScriptBlock“ für ItemSeclectionCondition für ListControl (Format)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
