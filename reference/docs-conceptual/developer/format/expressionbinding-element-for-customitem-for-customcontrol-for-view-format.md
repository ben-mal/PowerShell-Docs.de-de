---
title: ExpressionBinding-Element für customItem für CustomControl für View (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 1885a2820c0cb250aa6fda80544f58d06136cfeb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773792"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a>Element „ExpressionBinding“ für CustomItem für CustomControl für View (Format)

Definiert die Daten, die vom-Steuerelement angezeigt werden. Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.

Konfigurationselement (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element für View (Format) customentries-Element für CustomControl for View (Format) customentry-Element für customentries für CustomControl for View (Format) customItem-Element für customentry für CustomControl für View (Format) ExpressionBinding-Element für customItem

## <a name="syntax"></a>Syntax

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ExpressionBinding` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`CustomControl Element`|Optionales Element.<br /><br /> Definiert ein Steuerelement, das von diesem Steuerelement verwendet wird.|
|[Element „CustomControlName“ für ExpressionBinding für CustomControl für View (Format)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an.|
|[Element „EnumerateCollection“ für ExpressionBinding für CustomControl für View (Format)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Gibt an, dass die Elemente der Auflistungen angezeigt werden.|
|[Itemselectioncondition-Element für ExpressionBinding für die Ansicht (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|Optionales Element.<br /><br /> Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.|
|[Element „PropertyName“ für ExpressionBinding für CustomControl für View (Format)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Gibt die .net-Eigenschaft an, deren Wert vom-Steuerelement angezeigt wird.|
|[ScriptBlock-Element für ExpressionBinding für customcustomcontrol für View (Format)](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Optionales Element.<br /><br /> Gibt das Skript an, dessen Wert vom-Steuerelement angezeigt wird.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomItem“ für CustomEntry für CustomControl für View (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Definiert, welche Daten von der benutzerdefinierten Steuerelement Ansicht und der Anzeige angezeigt werden.|

## <a name="remarks"></a>Bemerkungen

## <a name="see-also"></a>Weitere Informationen

[Element „CustomControlName“ für ExpressionBinding für CustomControl für View (Format)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Element „EnumerateCollection“ für ExpressionBinding für CustomControl für View (Format)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Itemselectioncondition-Element für ExpressionBinding für die Ansicht (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[Element „PropertyName“ für ExpressionBinding für CustomControl für View (Format)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Element „ScriptBlock“ für ExpressionBinding für CustomControl für View (Format)](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Element „CustomItem“ für CustomEntry für CustomControl für View (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
