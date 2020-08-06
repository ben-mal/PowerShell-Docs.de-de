---
title: ScriptBlock-Element für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e761e02a7910cd598449d564e827889162da9f25
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787681"
---
# <a name="scriptblock-element-for-groupby-format"></a>Element „ScriptBlock“ für GroupBy (Format)

Gibt das Skript an, das eine neue Gruppe startet, wenn sich der Wert ändert.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) ScriptBlock-Element für GroupBy (Format)

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
|[Element „GroupBy“ für View (Format)](./groupby-element-for-view-format.md)|Definiert, wie eine Gruppe von .NET-Objekten angezeigt wird.|

## <a name="text-value"></a>Textwert

Geben Sie das auszuwertende Skript an.

## <a name="remarks"></a>Bemerkungen

PowerShell startet immer dann eine neue Gruppe, wenn der Wert dieses Skripts geändert wird.

Wenn dieses Element angegeben ist, können Sie das [propertyName](propertyname-element-for-groupby-format.md) -Element nicht angeben, um eine neue Gruppe zu starten.

## <a name="see-also"></a>Weitere Informationen

[Element „PropertyName“ für GroupBy (Format)](propertyname-element-for-groupby-format.md)

[Element „GroupBy“ für View (Format)](groupby-element-for-view-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](writing-a-powershell-formatting-file.md)
