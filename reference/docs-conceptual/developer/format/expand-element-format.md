---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Expand“ (Format)
description: Element „Expand“ (Format)
ms.openlocfilehash: 518e132e3e74b921d4e51966fc60088a22ef63f1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667945"
---
# <a name="expand-element-format"></a>Element „Expand“ (Format)

Gibt an, wie das Sammlungsobjekt für diese Definition erweitert wird.

Configuration-Element (Format) DefaultSettings-Element (Format) enumerableexpand-Element (Format) enumerableweiterung-Element (Format) Expand Element (Format)

## <a name="syntax"></a>Syntax

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Expand` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „EnumerableExpansion“ (Format)](./enumerableexpansion-element-format.md)|Definiert, wie bestimmte .net-Auflistungs Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.|

## <a name="text-value"></a>Textwert

Geben Sie einen der folgenden Werte an.

- Enumonly: zeigt nur die Eigenschaften der Objekte in der Auflistung an.

- Coreonly: zeigt nur die Eigenschaften des Auflistungs Objekts an.

- Beides: zeigt die Eigenschaften der Objekte in der Auflistung und die Eigenschaften des Auflistungs Objekts an.

## <a name="remarks"></a>Bemerkungen

Dieses Element wird verwendet, um zu definieren, wie Auflistungs Objekte und die Objekte in der Auflistung angezeigt werden. In diesem Fall bezieht sich ein Auflistungs Objekt auf jedes Objekt, das die  **System. Collections. ICollection** -Schnittstelle unterstützt.

Standardmäßig werden nur die Eigenschaften der Objekte in der Auflistung angezeigt.

## <a name="see-also"></a>Weitere Informationen

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
