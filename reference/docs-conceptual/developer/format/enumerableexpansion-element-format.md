---
ms.date: 09/13/2016
ms.topic: reference
title: Element „EnumerableExpansion“ (Format)
description: Element „EnumerableExpansion“ (Format)
ms.openlocfilehash: 207ad99d5335e99701660159ab77279b55b0b6b5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668013"
---
# <a name="enumerableexpansion-element-format"></a>Element „EnumerableExpansion“ (Format)

Definiert, wie bestimmte .net-Auflistungs Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.

Configuration-Element (Format) DefaultSettings-Element (Format) enumerableerweiterungen-Element (Format) enumerableerweiterung-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EnumerableExpansion` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „EntrySelectedBy“ für EnumerableExpansion (Format)](./entryselectedby-element-for-enumerableexpansion-format.md)|Optionales Element.<br /><br /> Definiert, welche .net-Auflistungs Objekte durch diese Definition erweitert werden.|
|[Element „Expand“ (Format)](./expand-element-format.md)|Gibt an, wie das Sammlungsobjekt für diese Definition erweitert wird.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „EnumerableExpansions“ (Format)](./enumerableexpansions-element-format.md)|Definiert die verschiedenen Möglichkeiten, wie .net-Auflistungs Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.|

## <a name="remarks"></a>Bemerkungen

Dieses Element wird verwendet, um zu definieren, wie Auflistungs Objekte und die Objekte in der Auflistung angezeigt werden. In diesem Fall bezieht sich ein Auflistungs Objekt auf jedes Objekt, das die  **System. Collections. ICollection** -Schnittstelle unterstützt.

Standardmäßig werden nur die Eigenschaften der Objekte in der Auflistung angezeigt.

## <a name="see-also"></a>Weitere Informationen

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
