---
ms.date: 09/13/2016
ms.topic: reference
title: Element „WideControl“ (Format)
description: Element „WideControl“ (Format)
ms.openlocfilehash: f88e1ce18f87e5e47de473298b3ecf070b71c192
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651275"
---
# <a name="widecontrol-element-format"></a><span data-ttu-id="fbecb-103">Element „WideControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="fbecb-103">WideControl Element (Format)</span></span>

<span data-ttu-id="fbecb-104">Definiert ein breites Listenformat (Einzelwert) für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="fbecb-104">Defines a wide (single value) list format for the view.</span></span> <span data-ttu-id="fbecb-105">Diese Ansicht zeigt einen einzelnen Eigenschafts Wert oder einen Skript Wert für jedes Objekt an.</span><span class="sxs-lookup"><span data-stu-id="fbecb-105">This view displays a single property value or script value for each object.</span></span>

<span data-ttu-id="fbecb-106">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) widecontrol-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="fbecb-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fbecb-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="fbecb-107">Syntax</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fbecb-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fbecb-108">Attributes and Elements</span></span>

<span data-ttu-id="fbecb-109">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `WideControl` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fbecb-109">The following sections describe the attributes, child elements, and parent element of the `WideControl` element.</span></span> <span data-ttu-id="fbecb-110">Das `AutoSize` -Element und das-Element können nicht `ColumnNumber` gleichzeitig angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fbecb-110">You cannot specify the `AutoSize` and `ColumnNumber` elements at the same time.</span></span>

### <a name="attributes"></a><span data-ttu-id="fbecb-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="fbecb-111">Attributes</span></span>

<span data-ttu-id="fbecb-112">Keine</span><span class="sxs-lookup"><span data-stu-id="fbecb-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fbecb-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fbecb-113">Child Elements</span></span>

|<span data-ttu-id="fbecb-114">Element</span><span class="sxs-lookup"><span data-stu-id="fbecb-114">Element</span></span>|<span data-ttu-id="fbecb-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbecb-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fbecb-116">Element „AutoSize“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="fbecb-116">AutoSize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)|<span data-ttu-id="fbecb-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="fbecb-117">Optional element.</span></span><br /><br /> <span data-ttu-id="fbecb-118">Gibt an, ob die Spaltengröße und die Anzahl der Spalten basierend auf der Größe der Daten angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="fbecb-118">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="fbecb-119">Element „ColumnNumber“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="fbecb-119">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)|<span data-ttu-id="fbecb-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="fbecb-120">Optional element.</span></span><br /><br /> <span data-ttu-id="fbecb-121">Gibt die Anzahl der Spalten an, die in der breiten Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fbecb-121">Specifies the number of columns displayed in the wide view.</span></span>|
|[<span data-ttu-id="fbecb-122">Wideentries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="fbecb-122">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="fbecb-123">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="fbecb-123">Required element.</span></span><br /><br /> <span data-ttu-id="fbecb-124">Stellt die Definitionen der breiten Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="fbecb-124">Provides the definitions of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fbecb-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fbecb-125">Parent Elements</span></span>

|<span data-ttu-id="fbecb-126">Element</span><span class="sxs-lookup"><span data-stu-id="fbecb-126">Element</span></span>|<span data-ttu-id="fbecb-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbecb-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fbecb-128">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="fbecb-128">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="fbecb-129">Definiert eine Ansicht, die verwendet wird, um ein oder mehrere .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fbecb-129">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fbecb-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fbecb-130">Remarks</span></span>

<span data-ttu-id="fbecb-131">Beim Definieren einer breiten Ansicht können Sie das- `AutoSize` Element oder das-Element hinzufügen, `ColumnNumber` aber Sie können nicht beides hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fbecb-131">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` but you cannot add both.</span></span>

<span data-ttu-id="fbecb-132">In den meisten Fällen ist nur eine Definition für jede Breite Ansicht erforderlich, aber es ist möglich, mehrere Definitionen zu verwenden, wenn Sie dieselbe Ansicht verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fbecb-132">In most cases, only one definition is required for each wide view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="fbecb-133">In diesen Fällen können Sie eine separate Definition für jedes Objekt oder jede Gruppe von Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fbecb-133">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

<span data-ttu-id="fbecb-134">Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Wide View Components](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="fbecb-134">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="fbecb-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fbecb-135">Example</span></span>

<span data-ttu-id="fbecb-136">Das folgende Beispiel zeigt ein- `WideControl` Element, das verwendet wird, um eine Eigenschaft des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fbecb-136">The following example shows a `WideControl` element that is used to display a property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>...</WideEntries>
  </WideControl>
</View>
```

<span data-ttu-id="fbecb-137">Ein umfassendes Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="fbecb-137">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fbecb-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fbecb-138">See Also</span></span>

[<span data-ttu-id="fbecb-139">AutoSize-Element für widecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="fbecb-139">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="fbecb-140">Element „ColumnNumber“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="fbecb-140">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="fbecb-141">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="fbecb-141">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="fbecb-142">Wideentries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="fbecb-142">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="fbecb-143">Breite Ansicht (Basic)</span><span class="sxs-lookup"><span data-stu-id="fbecb-143">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="fbecb-144">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="fbecb-144">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="fbecb-145">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="fbecb-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
