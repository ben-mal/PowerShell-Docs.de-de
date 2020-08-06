---
title: Widecontrol-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: b6f19cf94dcb440eeaf53547db407287e5462520
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784978"
---
# <a name="widecontrol-element-format"></a><span data-ttu-id="cae70-102">Element „WideControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="cae70-102">WideControl Element (Format)</span></span>

<span data-ttu-id="cae70-103">Definiert ein breites Listenformat (Einzelwert) für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="cae70-103">Defines a wide (single value) list format for the view.</span></span> <span data-ttu-id="cae70-104">Diese Ansicht zeigt einen einzelnen Eigenschafts Wert oder einen Skript Wert für jedes Objekt an.</span><span class="sxs-lookup"><span data-stu-id="cae70-104">This view displays a single property value or script value for each object.</span></span>

<span data-ttu-id="cae70-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) widecontrol-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="cae70-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cae70-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="cae70-106">Syntax</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cae70-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cae70-107">Attributes and Elements</span></span>

<span data-ttu-id="cae70-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `WideControl` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cae70-108">The following sections describe the attributes, child elements, and parent element of the `WideControl` element.</span></span> <span data-ttu-id="cae70-109">Das `AutoSize` -Element und das-Element können nicht `ColumnNumber` gleichzeitig angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cae70-109">You cannot specify the `AutoSize` and `ColumnNumber` elements at the same time.</span></span>

### <a name="attributes"></a><span data-ttu-id="cae70-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="cae70-110">Attributes</span></span>

<span data-ttu-id="cae70-111">Keine</span><span class="sxs-lookup"><span data-stu-id="cae70-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cae70-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cae70-112">Child Elements</span></span>

|<span data-ttu-id="cae70-113">Element</span><span class="sxs-lookup"><span data-stu-id="cae70-113">Element</span></span>|<span data-ttu-id="cae70-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cae70-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cae70-115">Element „AutoSize“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="cae70-115">AutoSize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)|<span data-ttu-id="cae70-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="cae70-116">Optional element.</span></span><br /><br /> <span data-ttu-id="cae70-117">Gibt an, ob die Spaltengröße und die Anzahl der Spalten basierend auf der Größe der Daten angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="cae70-117">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="cae70-118">Element „ColumnNumber“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="cae70-118">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)|<span data-ttu-id="cae70-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="cae70-119">Optional element.</span></span><br /><br /> <span data-ttu-id="cae70-120">Gibt die Anzahl der Spalten an, die in der breiten Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cae70-120">Specifies the number of columns displayed in the wide view.</span></span>|
|[<span data-ttu-id="cae70-121">Wideentries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="cae70-121">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="cae70-122">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="cae70-122">Required element.</span></span><br /><br /> <span data-ttu-id="cae70-123">Stellt die Definitionen der breiten Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="cae70-123">Provides the definitions of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cae70-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cae70-124">Parent Elements</span></span>

|<span data-ttu-id="cae70-125">Element</span><span class="sxs-lookup"><span data-stu-id="cae70-125">Element</span></span>|<span data-ttu-id="cae70-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cae70-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cae70-127">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="cae70-127">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="cae70-128">Definiert eine Ansicht, die verwendet wird, um ein oder mehrere .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cae70-128">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cae70-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cae70-129">Remarks</span></span>

<span data-ttu-id="cae70-130">Beim Definieren einer breiten Ansicht können Sie das- `AutoSize` Element oder das-Element hinzufügen, `ColumnNumber` aber Sie können nicht beides hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cae70-130">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` but you cannot add both.</span></span>

<span data-ttu-id="cae70-131">In den meisten Fällen ist nur eine Definition für jede Breite Ansicht erforderlich, aber es ist möglich, mehrere Definitionen zu verwenden, wenn Sie dieselbe Ansicht verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cae70-131">In most cases, only one definition is required for each wide view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="cae70-132">In diesen Fällen können Sie eine separate Definition für jedes Objekt oder jede Gruppe von Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cae70-132">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

<span data-ttu-id="cae70-133">Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Wide View Components](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="cae70-133">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="cae70-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cae70-134">Example</span></span>

<span data-ttu-id="cae70-135">Das folgende Beispiel zeigt ein- `WideControl` Element, das verwendet wird, um eine Eigenschaft des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cae70-135">The following example shows a `WideControl` element that is used to display a property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

<span data-ttu-id="cae70-136">Ein umfassendes Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="cae70-136">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cae70-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cae70-137">See Also</span></span>

[<span data-ttu-id="cae70-138">AutoSize-Element für widecontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="cae70-138">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="cae70-139">Element „ColumnNumber“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="cae70-139">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="cae70-140">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="cae70-140">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="cae70-141">Wideentries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="cae70-141">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="cae70-142">Breite Ansicht (Basic)</span><span class="sxs-lookup"><span data-stu-id="cae70-142">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="cae70-143">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="cae70-143">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="cae70-144">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="cae70-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
