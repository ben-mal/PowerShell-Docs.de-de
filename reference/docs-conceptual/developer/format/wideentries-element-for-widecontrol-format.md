---
ms.date: 09/13/2016
ms.topic: reference
title: Element „WideEntries“ für WideControl (Format)
description: Element „WideEntries“ für WideControl (Format)
ms.openlocfilehash: 567b8acdd0d2e8d5daaef2c31b4fe4ce38c23a47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651228"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="cb54f-103">Element „WideEntries“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="cb54f-103">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="cb54f-104">Stellt die Definitionen der breiten Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="cb54f-104">Provides the definitions of the wide view.</span></span> <span data-ttu-id="cb54f-105">In der breiten Ansicht muss mindestens eine Definition angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cb54f-105">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="cb54f-106">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) widecontrol-Element (Format) wideentries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="cb54f-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cb54f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb54f-107">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="cb54f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cb54f-108">Attributes and Elements</span></span>

<span data-ttu-id="cb54f-109">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `WideEntries` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cb54f-109">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="cb54f-110">Es muss mindestens ein untergeordnetes Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cb54f-110">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="cb54f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="cb54f-111">Attributes</span></span>

<span data-ttu-id="cb54f-112">Keine</span><span class="sxs-lookup"><span data-stu-id="cb54f-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cb54f-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cb54f-113">Child Elements</span></span>

|<span data-ttu-id="cb54f-114">Element</span><span class="sxs-lookup"><span data-stu-id="cb54f-114">Element</span></span>|<span data-ttu-id="cb54f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb54f-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cb54f-116">Wideentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="cb54f-116">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="cb54f-117">Stellt eine Definition der breiten Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="cb54f-117">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cb54f-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cb54f-118">Parent Elements</span></span>

|<span data-ttu-id="cb54f-119">Element</span><span class="sxs-lookup"><span data-stu-id="cb54f-119">Element</span></span>|<span data-ttu-id="cb54f-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb54f-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cb54f-121">Element „WideControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="cb54f-121">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="cb54f-122">Definiert ein breites Listenformat (Einzelwert) für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="cb54f-122">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cb54f-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cb54f-123">Remarks</span></span>

<span data-ttu-id="cb54f-124">Eine breite Ansicht ist ein Listenformat, in dem ein einzelner Eigenschafts Wert oder ein Skript Wert für jedes Objekt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cb54f-124">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="cb54f-125">Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Wide View Components](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="cb54f-125">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="cb54f-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb54f-126">Example</span></span>

<span data-ttu-id="cb54f-127">Das folgende Beispiel zeigt ein- `WideEntries` Element, das ein einzelnes- `WideEntry` Element definiert.</span><span class="sxs-lookup"><span data-stu-id="cb54f-127">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="cb54f-128">Das- `WideEntry` Element enthält ein einzelnes- `WideItem` Element, das definiert, welcher Eigenschafts-oder Skript Wert in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cb54f-128">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="cb54f-129">Ein umfassendes Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="cb54f-129">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cb54f-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb54f-130">See Also</span></span>

[<span data-ttu-id="cb54f-131">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="cb54f-131">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="cb54f-132">Element „WideControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="cb54f-132">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="cb54f-133">Wideentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="cb54f-133">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="cb54f-134">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="cb54f-134">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
