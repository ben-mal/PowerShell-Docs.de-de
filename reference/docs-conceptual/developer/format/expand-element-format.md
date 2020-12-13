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
# <a name="expand-element-format"></a><span data-ttu-id="1ecd3-103">Element „Expand“ (Format)</span><span class="sxs-lookup"><span data-stu-id="1ecd3-103">Expand Element (Format)</span></span>

<span data-ttu-id="1ecd3-104">Gibt an, wie das Sammlungsobjekt für diese Definition erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="1ecd3-104">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="1ecd3-105">Configuration-Element (Format) DefaultSettings-Element (Format) enumerableexpand-Element (Format) enumerableweiterung-Element (Format) Expand Element (Format)</span><span class="sxs-lookup"><span data-stu-id="1ecd3-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1ecd3-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ecd3-106">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1ecd3-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1ecd3-107">Attributes and Elements</span></span>

<span data-ttu-id="1ecd3-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Expand` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1ecd3-108">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1ecd3-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="1ecd3-109">Attributes</span></span>

<span data-ttu-id="1ecd3-110">Keine</span><span class="sxs-lookup"><span data-stu-id="1ecd3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1ecd3-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ecd3-111">Child Elements</span></span>

<span data-ttu-id="1ecd3-112">Keine</span><span class="sxs-lookup"><span data-stu-id="1ecd3-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1ecd3-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ecd3-113">Parent Elements</span></span>

|<span data-ttu-id="1ecd3-114">Element</span><span class="sxs-lookup"><span data-stu-id="1ecd3-114">Element</span></span>|<span data-ttu-id="1ecd3-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ecd3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1ecd3-116">Element „EnumerableExpansion“ (Format)</span><span class="sxs-lookup"><span data-stu-id="1ecd3-116">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="1ecd3-117">Definiert, wie bestimmte .net-Auflistungs Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1ecd3-117">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1ecd3-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="1ecd3-118">Text Value</span></span>

<span data-ttu-id="1ecd3-119">Geben Sie einen der folgenden Werte an.</span><span class="sxs-lookup"><span data-stu-id="1ecd3-119">Specify one of the following values:</span></span>

- <span data-ttu-id="1ecd3-120">Enumonly: zeigt nur die Eigenschaften der Objekte in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="1ecd3-120">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="1ecd3-121">Coreonly: zeigt nur die Eigenschaften des Auflistungs Objekts an.</span><span class="sxs-lookup"><span data-stu-id="1ecd3-121">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="1ecd3-122">Beides: zeigt die Eigenschaften der Objekte in der Auflistung und die Eigenschaften des Auflistungs Objekts an.</span><span class="sxs-lookup"><span data-stu-id="1ecd3-122">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ecd3-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1ecd3-123">Remarks</span></span>

<span data-ttu-id="1ecd3-124">Dieses Element wird verwendet, um zu definieren, wie Auflistungs Objekte und die Objekte in der Auflistung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1ecd3-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="1ecd3-125">In diesem Fall bezieht sich ein Auflistungs Objekt auf jedes Objekt, das die  **System. Collections. ICollection** -Schnittstelle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1ecd3-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="1ecd3-126">Standardmäßig werden nur die Eigenschaften der Objekte in der Auflistung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ecd3-126">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ecd3-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ecd3-127">See Also</span></span>

[<span data-ttu-id="1ecd3-128">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="1ecd3-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
