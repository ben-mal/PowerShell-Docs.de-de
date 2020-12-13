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
# <a name="enumerableexpansion-element-format"></a><span data-ttu-id="8c30b-103">Element „EnumerableExpansion“ (Format)</span><span class="sxs-lookup"><span data-stu-id="8c30b-103">EnumerableExpansion Element (Format)</span></span>

<span data-ttu-id="8c30b-104">Definiert, wie bestimmte .net-Auflistungs Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8c30b-104">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="8c30b-105">Configuration-Element (Format) DefaultSettings-Element (Format) enumerableerweiterungen-Element (Format) enumerableerweiterung-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="8c30b-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8c30b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c30b-106">Syntax</span></span>

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8c30b-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8c30b-107">Attributes and Elements</span></span>

<span data-ttu-id="8c30b-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EnumerableExpansion` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8c30b-108">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansion` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8c30b-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="8c30b-109">Attributes</span></span>

<span data-ttu-id="8c30b-110">Keine</span><span class="sxs-lookup"><span data-stu-id="8c30b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8c30b-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8c30b-111">Child Elements</span></span>

|<span data-ttu-id="8c30b-112">Element</span><span class="sxs-lookup"><span data-stu-id="8c30b-112">Element</span></span>|<span data-ttu-id="8c30b-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c30b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8c30b-114">Element „EntrySelectedBy“ für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="8c30b-114">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="8c30b-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="8c30b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="8c30b-116">Definiert, welche .net-Auflistungs Objekte durch diese Definition erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="8c30b-116">Defines which .NET collection objects are expanded by this definition.</span></span>|
|[<span data-ttu-id="8c30b-117">Element „Expand“ (Format)</span><span class="sxs-lookup"><span data-stu-id="8c30b-117">Expand Element (Format)</span></span>](./expand-element-format.md)|<span data-ttu-id="8c30b-118">Gibt an, wie das Sammlungsobjekt für diese Definition erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="8c30b-118">Specifies how the collection object is expanded for this definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8c30b-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8c30b-119">Parent Elements</span></span>

|<span data-ttu-id="8c30b-120">Element</span><span class="sxs-lookup"><span data-stu-id="8c30b-120">Element</span></span>|<span data-ttu-id="8c30b-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c30b-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8c30b-122">Element „EnumerableExpansions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="8c30b-122">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="8c30b-123">Definiert die verschiedenen Möglichkeiten, wie .net-Auflistungs Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8c30b-123">Defines the different ways that .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8c30b-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8c30b-124">Remarks</span></span>

<span data-ttu-id="8c30b-125">Dieses Element wird verwendet, um zu definieren, wie Auflistungs Objekte und die Objekte in der Auflistung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8c30b-125">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="8c30b-126">In diesem Fall bezieht sich ein Auflistungs Objekt auf jedes Objekt, das die  **System. Collections. ICollection** -Schnittstelle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8c30b-126">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="8c30b-127">Standardmäßig werden nur die Eigenschaften der Objekte in der Auflistung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c30b-127">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c30b-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c30b-128">See Also</span></span>

[<span data-ttu-id="8c30b-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="8c30b-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
