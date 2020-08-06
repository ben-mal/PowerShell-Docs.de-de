---
title: Expand-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: deee832254bb8a774ee2c1f5bd451d3ced1bd47a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783652"
---
# <a name="expand-element-format"></a><span data-ttu-id="933f5-102">Element „Expand“ (Format)</span><span class="sxs-lookup"><span data-stu-id="933f5-102">Expand Element (Format)</span></span>

<span data-ttu-id="933f5-103">Gibt an, wie das Sammlungsobjekt für diese Definition erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="933f5-103">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="933f5-104">Configuration-Element (Format) DefaultSettings-Element (Format) enumerableexpand-Element (Format) enumerableweiterung-Element (Format) Expand Element (Format)</span><span class="sxs-lookup"><span data-stu-id="933f5-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="933f5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="933f5-105">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="933f5-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="933f5-106">Attributes and Elements</span></span>

<span data-ttu-id="933f5-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Expand` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="933f5-107">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="933f5-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="933f5-108">Attributes</span></span>

<span data-ttu-id="933f5-109">Keine</span><span class="sxs-lookup"><span data-stu-id="933f5-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="933f5-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="933f5-110">Child Elements</span></span>

<span data-ttu-id="933f5-111">Keine</span><span class="sxs-lookup"><span data-stu-id="933f5-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="933f5-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="933f5-112">Parent Elements</span></span>

|<span data-ttu-id="933f5-113">Element</span><span class="sxs-lookup"><span data-stu-id="933f5-113">Element</span></span>|<span data-ttu-id="933f5-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="933f5-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="933f5-115">Element „EnumerableExpansion“ (Format)</span><span class="sxs-lookup"><span data-stu-id="933f5-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="933f5-116">Definiert, wie bestimmte .net-Auflistungs Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="933f5-116">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="933f5-117">Textwert</span><span class="sxs-lookup"><span data-stu-id="933f5-117">Text Value</span></span>

<span data-ttu-id="933f5-118">Geben Sie einen der folgenden Werte an.</span><span class="sxs-lookup"><span data-stu-id="933f5-118">Specify one of the following values:</span></span>

- <span data-ttu-id="933f5-119">Enumonly: zeigt nur die Eigenschaften der Objekte in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="933f5-119">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="933f5-120">Coreonly: zeigt nur die Eigenschaften des Auflistungs Objekts an.</span><span class="sxs-lookup"><span data-stu-id="933f5-120">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="933f5-121">Beides: zeigt die Eigenschaften der Objekte in der Auflistung und die Eigenschaften des Auflistungs Objekts an.</span><span class="sxs-lookup"><span data-stu-id="933f5-121">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="933f5-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="933f5-122">Remarks</span></span>

<span data-ttu-id="933f5-123">Dieses Element wird verwendet, um zu definieren, wie Auflistungs Objekte und die Objekte in der Auflistung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="933f5-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="933f5-124">In diesem Fall bezieht sich ein Auflistungs Objekt auf jedes Objekt, das die **System. Collections. ICollection** -Schnittstelle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="933f5-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="933f5-125">Standardmäßig werden nur die Eigenschaften der Objekte in der Auflistung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="933f5-125">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="933f5-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="933f5-126">See Also</span></span>

[<span data-ttu-id="933f5-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="933f5-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
