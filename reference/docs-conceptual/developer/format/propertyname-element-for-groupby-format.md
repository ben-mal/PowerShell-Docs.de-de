---
title: PropertyName-Element für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e83ebd49e4f3087c817b3cc8772889dbe85113aa
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785607"
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
