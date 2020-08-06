---
title: Wideentries-Element für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 74383b288c945008c1d7b5119363a166c04802ae
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785046"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="15200-102">Element „WideEntries“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="15200-102">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="15200-103">Stellt die Definitionen der breiten Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="15200-103">Provides the definitions of the wide view.</span></span> <span data-ttu-id="15200-104">In der breiten Ansicht muss mindestens eine Definition angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="15200-104">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="15200-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) widecontrol-Element (Format) wideentries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="15200-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="15200-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="15200-106">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="15200-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="15200-107">Attributes and Elements</span></span>

<span data-ttu-id="15200-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `WideEntries` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="15200-108">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="15200-109">Es muss mindestens ein untergeordnetes Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="15200-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="15200-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="15200-110">Attributes</span></span>

<span data-ttu-id="15200-111">Keine</span><span class="sxs-lookup"><span data-stu-id="15200-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="15200-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15200-112">Child Elements</span></span>

|<span data-ttu-id="15200-113">Element</span><span class="sxs-lookup"><span data-stu-id="15200-113">Element</span></span>|<span data-ttu-id="15200-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15200-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15200-115">Wideentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="15200-115">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="15200-116">Stellt eine Definition der breiten Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="15200-116">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="15200-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15200-117">Parent Elements</span></span>

|<span data-ttu-id="15200-118">Element</span><span class="sxs-lookup"><span data-stu-id="15200-118">Element</span></span>|<span data-ttu-id="15200-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15200-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15200-120">Element „WideControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="15200-120">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="15200-121">Definiert ein breites Listenformat (Einzelwert) für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="15200-121">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="15200-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="15200-122">Remarks</span></span>

<span data-ttu-id="15200-123">Eine breite Ansicht ist ein Listenformat, in dem ein einzelner Eigenschafts Wert oder ein Skript Wert für jedes Objekt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="15200-123">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="15200-124">Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Wide View Components](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="15200-124">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="15200-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="15200-125">Example</span></span>

<span data-ttu-id="15200-126">Das folgende Beispiel zeigt ein- `WideEntries` Element, das ein einzelnes- `WideEntry` Element definiert.</span><span class="sxs-lookup"><span data-stu-id="15200-126">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="15200-127">Das- `WideEntry` Element enthält ein einzelnes- `WideItem` Element, das definiert, welcher Eigenschafts-oder Skript Wert in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="15200-127">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="15200-128">Ein umfassendes Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="15200-128">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="15200-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15200-129">See Also</span></span>

[<span data-ttu-id="15200-130">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="15200-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="15200-131">Element „WideControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="15200-131">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="15200-132">Wideentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="15200-132">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="15200-133">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="15200-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
