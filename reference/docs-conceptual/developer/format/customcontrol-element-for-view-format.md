---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomControl“ für View (Format)
description: Element „CustomControl“ für View (Format)
ms.openlocfilehash: 41352be55f0c03b2eaca0dbe2d7345e7cf804a7c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655476"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="4f485-103">Element „CustomControl“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="4f485-103">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="4f485-104">Definiert ein benutzerdefiniertes Steuerelement Format für die Ansicht.</span><span class="sxs-lookup"><span data-stu-id="4f485-104">Defines a custom control format for the view.</span></span>

<span data-ttu-id="4f485-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="4f485-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4f485-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f485-106">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4f485-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4f485-107">Attributes and Elements</span></span>

<span data-ttu-id="4f485-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomControl` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4f485-108">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="4f485-109">Sie müssen ein untergeordnetes Element angeben.</span><span class="sxs-lookup"><span data-stu-id="4f485-109">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4f485-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="4f485-110">Attributes</span></span>

<span data-ttu-id="4f485-111">Keine</span><span class="sxs-lookup"><span data-stu-id="4f485-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4f485-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4f485-112">Child Elements</span></span>

|<span data-ttu-id="4f485-113">Element</span><span class="sxs-lookup"><span data-stu-id="4f485-113">Element</span></span>|<span data-ttu-id="4f485-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f485-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4f485-115">Element „CustomEntries“ für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="4f485-115">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="4f485-116">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="4f485-116">Required element.</span></span><br /><br /> <span data-ttu-id="4f485-117">Stellt die Definitionen der benutzerdefinierten Steuerelement Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="4f485-117">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4f485-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4f485-118">Parent Elements</span></span>

|<span data-ttu-id="4f485-119">Element</span><span class="sxs-lookup"><span data-stu-id="4f485-119">Element</span></span>|<span data-ttu-id="4f485-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f485-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4f485-121">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="4f485-121">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="4f485-122">Definiert eine Ansicht, die verwendet wird, um ein oder mehrere .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4f485-122">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4f485-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4f485-123">Remarks</span></span>

<span data-ttu-id="4f485-124">In den meisten Fällen ist nur eine Definition für jede Steuerelement Ansicht erforderlich, aber es ist möglich, mehrere Definitionen bereitzustellen, wenn Sie die gleiche Ansicht verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4f485-124">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="4f485-125">In diesen Fällen können Sie eine separate Definition für jedes Objekt oder jede Gruppe von Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4f485-125">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f485-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f485-126">See Also</span></span>

[<span data-ttu-id="4f485-127">Element „CustomEntries“ für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="4f485-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="4f485-128">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="4f485-128">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="4f485-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="4f485-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
