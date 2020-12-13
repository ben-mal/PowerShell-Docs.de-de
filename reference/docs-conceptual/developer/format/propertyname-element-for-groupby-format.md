---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für GroupBy (Format)
description: Element „PropertyName“ für GroupBy (Format)
ms.openlocfilehash: 44351c46ff2386f967644fef4f423b3858dc1619
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666143"
---
# <a name="propertyname-element-for-groupby-format"></a>Element „PropertyName“ für GroupBy (Format)

Gibt die .net-Eigenschaft an, die eine neue Gruppe startet, wenn sich der Wert ändert.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) propertyName-Element für GroupBy (Format)

## <a name="syntax"></a>Syntax

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „GroupBy“ für View (Format)](./groupby-element-for-view-format.md)|Definiert, wie eine Gruppe von .NET-Objekten angezeigt wird.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen der .net-Eigenschaft an.

## <a name="remarks"></a>Bemerkungen

Windows PowerShell startet eine neue Gruppe, wenn der Wert dieser Eigenschaft geändert wird.

Wenn dieses Element angegeben ist, können Sie das [ScriptBlock](./scriptblock-element-for-groupby-format.md) -Element nicht angeben, um eine neue Gruppe zu starten.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie eine neue Gruppe gestartet wird, wenn sich der Wert einer Eigenschaft ändert.

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

Ein Beispiel für eine komplette Formatierungs Datei, die dieses Element enthält, finden Sie unter [Wide View (GroupBy)](./wide-view-groupby.md).

## <a name="see-also"></a>Weitere Informationen

[Element „GroupBy“ für View (Format)](./groupby-element-for-view-format.md)

[Element „ScriptBlock“ für GroupBy (Format)](./scriptblock-element-for-groupby-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
