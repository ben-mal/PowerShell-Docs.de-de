---
title: Enumerableweiterung-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 81a8959c19502a2e56f4cfa48a1e480509d84b6e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774047"
---
# <a name="enumerableexpansion-element-format"></a><span data-ttu-id="433e7-102">Element „EnumerableExpansion“ (Format)</span><span class="sxs-lookup"><span data-stu-id="433e7-102">EnumerableExpansion Element (Format)</span></span>

<span data-ttu-id="433e7-103">Definiert, wie bestimmte .net-Auflistungs Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="433e7-103">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="433e7-104">Configuration-Element (Format) DefaultSettings-Element (Format) enumerableerweiterungen-Element (Format) enumerableerweiterung-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="433e7-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="433e7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="433e7-105">Syntax</span></span>

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="433e7-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="433e7-106">Attributes and Elements</span></span>

<span data-ttu-id="433e7-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EnumerableExpansion` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="433e7-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansion` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="433e7-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="433e7-108">Attributes</span></span>

<span data-ttu-id="433e7-109">Keine</span><span class="sxs-lookup"><span data-stu-id="433e7-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="433e7-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="433e7-110">Child Elements</span></span>

|<span data-ttu-id="433e7-111">Element</span><span class="sxs-lookup"><span data-stu-id="433e7-111">Element</span></span>|<span data-ttu-id="433e7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="433e7-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="433e7-113">Element „EntrySelectedBy“ für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="433e7-113">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="433e7-114">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="433e7-114">Optional element.</span></span><br /><br /> <span data-ttu-id="433e7-115">Definiert, welche .net-Auflistungs Objekte durch diese Definition erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="433e7-115">Defines which .NET collection objects are expanded by this definition.</span></span>|
|[<span data-ttu-id="433e7-116">Element „Expand“ (Format)</span><span class="sxs-lookup"><span data-stu-id="433e7-116">Expand Element (Format)</span></span>](./expand-element-format.md)|<span data-ttu-id="433e7-117">Gibt an, wie das Sammlungsobjekt für diese Definition erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="433e7-117">Specifies how the collection object is expanded for this definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="433e7-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="433e7-118">Parent Elements</span></span>

|<span data-ttu-id="433e7-119">Element</span><span class="sxs-lookup"><span data-stu-id="433e7-119">Element</span></span>|<span data-ttu-id="433e7-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="433e7-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="433e7-121">Element „EnumerableExpansions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="433e7-121">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="433e7-122">Definiert die verschiedenen Möglichkeiten, wie .net-Auflistungs Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="433e7-122">Defines the different ways that .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="433e7-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="433e7-123">Remarks</span></span>

<span data-ttu-id="433e7-124">Dieses Element wird verwendet, um zu definieren, wie Auflistungs Objekte und die Objekte in der Auflistung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="433e7-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="433e7-125">In diesem Fall bezieht sich ein Auflistungs Objekt auf jedes Objekt, das die **System. Collections. ICollection** -Schnittstelle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="433e7-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="433e7-126">Standardmäßig werden nur die Eigenschaften der Objekte in der Auflistung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="433e7-126">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="433e7-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="433e7-127">See Also</span></span>

[<span data-ttu-id="433e7-128">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="433e7-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
