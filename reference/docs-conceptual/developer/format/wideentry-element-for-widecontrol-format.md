---
title: Wideentry-Element für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 13dd1f6ad7ac1e9d8d0524f0a0f18fe80ffaf8e2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780014"
---
# <a name="wideentry-element-for-widecontrol-format"></a><span data-ttu-id="e8e47-102">Element „WideEntry“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e8e47-102">WideEntry Element for WideControl (Format)</span></span>

<span data-ttu-id="e8e47-103">Stellt eine Definition der breiten Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="e8e47-103">Provides a definition of the wide view.</span></span>

<span data-ttu-id="e8e47-104">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="e8e47-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e8e47-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8e47-105">Syntax</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e8e47-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e8e47-106">Attributes and Elements</span></span>

<span data-ttu-id="e8e47-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `WideEntry` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e8e47-107">The following sections describe the attributes, child elements, and the parent element of the `WideEntry` element.</span></span> <span data-ttu-id="e8e47-108">Sie müssen ein einzelnes untergeordnetes `WideItem` Element angeben.</span><span class="sxs-lookup"><span data-stu-id="e8e47-108">You must specify a single `WideItem` child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e8e47-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="e8e47-109">Attributes</span></span>

<span data-ttu-id="e8e47-110">Keine</span><span class="sxs-lookup"><span data-stu-id="e8e47-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e8e47-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e8e47-111">Child Elements</span></span>

|<span data-ttu-id="e8e47-112">Element</span><span class="sxs-lookup"><span data-stu-id="e8e47-112">Element</span></span>|<span data-ttu-id="e8e47-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e8e47-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e8e47-114">Element „EntrySelectedBy“ für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="e8e47-114">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="e8e47-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="e8e47-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e8e47-116">Definiert die .NET-Typen, die diese Breite Eingabe Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="e8e47-116">Defines the .NET types that use this wide entry definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="e8e47-117">Wideitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="e8e47-117">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="e8e47-118">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="e8e47-118">Required element.</span></span><br /><br /> <span data-ttu-id="e8e47-119">Definiert die Eigenschaft oder das Skript, dessen Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e8e47-119">Defines the property or script whose value is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e8e47-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e8e47-120">Parent Elements</span></span>

|<span data-ttu-id="e8e47-121">Element</span><span class="sxs-lookup"><span data-stu-id="e8e47-121">Element</span></span>|<span data-ttu-id="e8e47-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e8e47-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e8e47-123">Wideentries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="e8e47-123">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="e8e47-124">Stellt die Definitionen der breiten Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="e8e47-124">Provides the definitions of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e8e47-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e8e47-125">Remarks</span></span>

<span data-ttu-id="e8e47-126">Eine breite Ansicht ist ein Listenformat, in dem ein einzelner Eigenschafts Wert oder ein Skript Wert für jedes Objekt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e8e47-126">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="e8e47-127">Im Gegensatz zu anderen Sicht Typen können Sie für jede Sicht Definition nur ein Element Element angeben.</span><span class="sxs-lookup"><span data-stu-id="e8e47-127">Unlike other types of views, you can specify only one item element for each view definition.</span></span> <span data-ttu-id="e8e47-128">Weitere Informationen zu den anderen Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="e8e47-128">For more information about the other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e8e47-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8e47-129">Example</span></span>

<span data-ttu-id="e8e47-130">Das folgende Beispiel zeigt ein- `WideEntry` Element, das ein einzelnes- `WideItem` Element definiert.</span><span class="sxs-lookup"><span data-stu-id="e8e47-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="e8e47-131">Das- `WideItem` Element definiert die-Eigenschaft, deren Wert in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e8e47-131">The `WideItem` element defines the property whose value is displayed in the view.</span></span>

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

<span data-ttu-id="e8e47-132">Ein umfassendes Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="e8e47-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e8e47-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8e47-133">See Also</span></span>

[<span data-ttu-id="e8e47-134">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="e8e47-134">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="e8e47-135">Selectioncondition-Element für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="e8e47-135">SelectionCondition Element for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="e8e47-136">Selectionsetname-Element für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="e8e47-136">SelectionSetName Element for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="e8e47-137">Tyname-Element für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="e8e47-137">TypeName Element for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="e8e47-138">Wideentries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="e8e47-138">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="e8e47-139">Wideitem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="e8e47-139">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="e8e47-140">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e8e47-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
