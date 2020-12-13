---
ms.date: 09/13/2016
ms.topic: reference
title: Element „EnumerableExpansions“ (Format)
description: Element „EnumerableExpansions“ (Format)
ms.openlocfilehash: 789599e6ff368b4685c7937d5b6eb38618752f9e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660172"
---
# <a name="enumerableexpansions-element-format"></a>Element „EnumerableExpansions“ (Format)

Definiert, wie .net-Auflistungs Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.

Configuration-Element (Format) DefaultSettings-Element (Format) enumerableerweiterungen-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EnumerableExpansions` Elements beschrieben. Es gibt keine Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „EnumerableExpansion“ (Format)](./enumerableexpansion-element-format.md)|Optionales Element.<br /><br /> Definiert die spezifischen .net-Auflistungs Objekte, die erweitert werden, wenn Sie in einer Ansicht angezeigt werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „DefaultSettings“ (Format)](./defaultsettings-element-format.md)|Definiert allgemeine Einstellungen, die für alle Sichten der Formatierungs Datei gelten.|

## <a name="remarks"></a>Bemerkungen

Dieses Element wird verwendet, um zu definieren, wie Auflistungs Objekte und die Objekte in der Auflistung angezeigt werden. In diesem Fall bezieht sich ein Auflistungs Objekt auf jedes Objekt, das die  **System. Collections. ICollection** -Schnittstelle unterstützt.

## <a name="see-also"></a>Weitere Informationen

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
