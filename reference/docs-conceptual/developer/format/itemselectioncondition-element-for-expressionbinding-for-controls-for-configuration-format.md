---
title: Itemselectioncondition-Element für ExpressionBinding für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 3bfd3efe916b4d88c024de8f959482cab515f777
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781221"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a>Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)

Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss. Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.

Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für Configuration (Format) customItem-Element für customentry für Steuerelemente für das Configuration ExpressionBinding-Element für customItem for Controls for Configuration (Format) itemselectioncondition-Element für ExpressionBinding für Steuerelemente für die Konfiguration (Format)

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
|[PropertyName-Element für itemselectioncondition für Steuerelemente für die Konfiguration (Format)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Gibt die .net-Eigenschaft an, die die Bedingung auslöst.|
|[ScriptBlock-Element für itemselectioncondition für Steuerelemente für die Konfiguration (Format)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Gibt das Skript an, das die Bedingung auslöst.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|Definiert die Daten, die vom-Steuerelement angezeigt werden.|

## <a name="remarks"></a>Bemerkungen

Sie können einen Eigenschaftsnamen oder ein Skript für diese Bedingung angeben, aber nicht beides angeben.

## <a name="see-also"></a>Weitere Informationen

[PropertyName-Element für itemselectioncondition für Steuerelemente für die Konfiguration (Format)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[ScriptBlock-Element für itemselectioncondition für Steuerelemente für die Konfiguration (Format)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
