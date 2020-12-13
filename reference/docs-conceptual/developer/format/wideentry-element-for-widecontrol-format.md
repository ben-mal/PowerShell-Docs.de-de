---
ms.date: 09/13/2016
ms.topic: reference
title: Element „WideEntry“ für WideControl (Format)
description: Element „WideEntry“ für WideControl (Format)
ms.openlocfilehash: 3faaf767d11914792effd6765beed956a502c642
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664547"
---
# <a name="wideentry-element-for-widecontrol-format"></a><span data-ttu-id="82b12-103">Element „WideEntry“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="82b12-103">WideEntry Element for WideControl (Format)</span></span>

<span data-ttu-id="82b12-104">Stellt eine Definition der breiten Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="82b12-104">Provides a definition of the wide view.</span></span>

<span data-ttu-id="82b12-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="82b12-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="82b12-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="82b12-106">Syntax</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="82b12-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="82b12-107">Attributes and Elements</span></span>

<span data-ttu-id="82b12-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `WideEntry` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="82b12-108">The following sections describe the attributes, child elements, and the parent element of the `WideEntry` element.</span></span> <span data-ttu-id="82b12-109">Sie müssen ein einzelnes untergeordnetes `WideItem` Element angeben.</span><span class="sxs-lookup"><span data-stu-id="82b12-109">You must specify a single `WideItem` child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="82b12-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="82b12-110">Attributes</span></span>

<span data-ttu-id="82b12-111">Keine</span><span class="sxs-lookup"><span data-stu-id="82b12-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="82b12-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="82b12-112">Child Elements</span></span>

|<span data-ttu-id="82b12-113">Element</span><span class="sxs-lookup"><span data-stu-id="82b12-113">Element</span></span>|<span data-ttu-id="82b12-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82b12-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="82b12-115">Element „EntrySelectedBy“ für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="82b12-115">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="82b12-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="82b12-116">Optional element.</span></span><br /><br /> <span data-ttu-id="82b12-117">Definiert die .NET-Typen, die diese Breite Eingabe Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="82b12-117">Defines the .NET types that use this wide entry definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="82b12-118">Wideitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="82b12-118">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="82b12-119">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="82b12-119">Required element.</span></span><br /><br /> <span data-ttu-id="82b12-120">Definiert die Eigenschaft oder das Skript, dessen Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="82b12-120">Defines the property or script whose value is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="82b12-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="82b12-121">Parent Elements</span></span>

|<span data-ttu-id="82b12-122">Element</span><span class="sxs-lookup"><span data-stu-id="82b12-122">Element</span></span>|<span data-ttu-id="82b12-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82b12-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="82b12-124">Wideentries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="82b12-124">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="82b12-125">Stellt die Definitionen der breiten Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="82b12-125">Provides the definitions of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="82b12-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="82b12-126">Remarks</span></span>

<span data-ttu-id="82b12-127">Eine breite Ansicht ist ein Listenformat, in dem ein einzelner Eigenschafts Wert oder ein Skript Wert für jedes Objekt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="82b12-127">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="82b12-128">Im Gegensatz zu anderen Sicht Typen können Sie für jede Sicht Definition nur ein Element Element angeben.</span><span class="sxs-lookup"><span data-stu-id="82b12-128">Unlike other types of views, you can specify only one item element for each view definition.</span></span> <span data-ttu-id="82b12-129">Weitere Informationen zu den anderen Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="82b12-129">For more information about the other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="82b12-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="82b12-130">Example</span></span>

<span data-ttu-id="82b12-131">Das folgende Beispiel zeigt ein- `WideEntry` Element, das ein einzelnes- `WideItem` Element definiert.</span><span class="sxs-lookup"><span data-stu-id="82b12-131">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="82b12-132">Das- `WideItem` Element definiert die-Eigenschaft, deren Wert in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="82b12-132">The `WideItem` element defines the property whose value is displayed in the view.</span></span>

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

<span data-ttu-id="82b12-133">Ein umfassendes Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="82b12-133">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="82b12-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="82b12-134">See Also</span></span>

[<span data-ttu-id="82b12-135">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="82b12-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="82b12-136">Selectioncondition-Element für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="82b12-136">SelectionCondition Element for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="82b12-137">Selectionsetname-Element für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="82b12-137">SelectionSetName Element for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="82b12-138">Tyname-Element für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="82b12-138">TypeName Element for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="82b12-139">Wideentries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="82b12-139">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="82b12-140">Wideitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="82b12-140">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="82b12-141">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="82b12-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
