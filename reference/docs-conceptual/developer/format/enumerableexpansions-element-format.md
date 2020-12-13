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
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="15e00-103">Element „EnumerableExpansions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="15e00-103">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="15e00-104">Definiert, wie .net-Auflistungs Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="15e00-104">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="15e00-105">Configuration-Element (Format) DefaultSettings-Element (Format) enumerableerweiterungen-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="15e00-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="15e00-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="15e00-106">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="15e00-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="15e00-107">Attributes and Elements</span></span>

<span data-ttu-id="15e00-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EnumerableExpansions` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="15e00-108">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="15e00-109">Es gibt keine Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="15e00-109">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="15e00-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="15e00-110">Attributes</span></span>

<span data-ttu-id="15e00-111">Keine</span><span class="sxs-lookup"><span data-stu-id="15e00-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="15e00-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15e00-112">Child Elements</span></span>

|<span data-ttu-id="15e00-113">Element</span><span class="sxs-lookup"><span data-stu-id="15e00-113">Element</span></span>|<span data-ttu-id="15e00-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15e00-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15e00-115">Element „EnumerableExpansion“ (Format)</span><span class="sxs-lookup"><span data-stu-id="15e00-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="15e00-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="15e00-116">Optional element.</span></span><br /><br /> <span data-ttu-id="15e00-117">Definiert die spezifischen .net-Auflistungs Objekte, die erweitert werden, wenn Sie in einer Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="15e00-117">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="15e00-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15e00-118">Parent Elements</span></span>

|<span data-ttu-id="15e00-119">Element</span><span class="sxs-lookup"><span data-stu-id="15e00-119">Element</span></span>|<span data-ttu-id="15e00-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15e00-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15e00-121">Element „DefaultSettings“ (Format)</span><span class="sxs-lookup"><span data-stu-id="15e00-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="15e00-122">Definiert allgemeine Einstellungen, die für alle Sichten der Formatierungs Datei gelten.</span><span class="sxs-lookup"><span data-stu-id="15e00-122">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="15e00-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="15e00-123">Remarks</span></span>

<span data-ttu-id="15e00-124">Dieses Element wird verwendet, um zu definieren, wie Auflistungs Objekte und die Objekte in der Auflistung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="15e00-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="15e00-125">In diesem Fall bezieht sich ein Auflistungs Objekt auf jedes Objekt, das die  **System. Collections. ICollection** -Schnittstelle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="15e00-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="15e00-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15e00-126">See Also</span></span>

[<span data-ttu-id="15e00-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="15e00-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
