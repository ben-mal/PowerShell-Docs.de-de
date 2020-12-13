---
ms.date: 09/13/2016
ms.topic: reference
title: Element „View“ (Format)
description: Element „View“ (Format)
ms.openlocfilehash: 6fed1304d94339cc90b6ae53e06483c08d937c12
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649745"
---
# <a name="view-element-format"></a><span data-ttu-id="eb807-103">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-103">View Element (Format)</span></span>

<span data-ttu-id="eb807-104">Definiert eine Ansicht, in der ein oder mehrere .NET-Objekte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eb807-104">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="eb807-105">Es gibt keine Beschränkung für die Anzahl der Sichten, die in einer Formatierungs Datei definiert werden können.</span><span class="sxs-lookup"><span data-stu-id="eb807-105">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="eb807-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="eb807-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb807-107">Syntax</span></span>

```xml
<View>
  <Name>Friendly name of view.</Name>
  <ViewSelectedBy>...</ViewSelectedBy>
  <Controls>...</Controls>
  <GroupBy>...</GroupBy>
  <TableControl>...</TableControl>
  <ListControl>...</ListControl>
  <WideControl>...</WideControl>
  <CustomControl>...</CustomControl>
</View>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="eb807-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eb807-108">Attributes and Elements</span></span>

<span data-ttu-id="eb807-109">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `View` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb807-109">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="eb807-110">Sie müssen nur eines der untergeordneten Steuerelemente des Steuer Elements angeben, und Sie müssen den Namen der Ansicht und die Objekte, die die Sicht verwenden, angeben.</span><span class="sxs-lookup"><span data-stu-id="eb807-110">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="eb807-111">Definieren von benutzerdefinierten Steuerelementen, Gruppieren von Objekten und angeben, ob die Ansicht out-of-Band ist, sind optional.</span><span class="sxs-lookup"><span data-stu-id="eb807-111">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="eb807-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb807-112">Attributes</span></span>

<span data-ttu-id="eb807-113">Keine</span><span class="sxs-lookup"><span data-stu-id="eb807-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="eb807-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb807-114">Child Elements</span></span>

|<span data-ttu-id="eb807-115">Element</span><span class="sxs-lookup"><span data-stu-id="eb807-115">Element</span></span>|<span data-ttu-id="eb807-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb807-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="eb807-117">Element „Controls“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-117">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="eb807-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="eb807-118">Optional element.</span></span><br /><br /> <span data-ttu-id="eb807-119">Definiert eine Gruppe von Steuerelementen, auf die über Ihren Namen in der Ansicht verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="eb807-119">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="eb807-120">CustomControl-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-120">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="eb807-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="eb807-121">Optional element.</span></span><br /><br /> <span data-ttu-id="eb807-122">Definiert ein benutzerdefiniertes Steuerelement Format für die Ansicht.</span><span class="sxs-lookup"><span data-stu-id="eb807-122">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="eb807-123">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-123">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="eb807-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="eb807-124">Optional element.</span></span><br /><br /> <span data-ttu-id="eb807-125">Definiert, wie die Member der .NET-Objekte gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="eb807-125">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="eb807-126">Element „ListControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-126">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="eb807-127">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="eb807-127">Optional element.</span></span><br /><br /> <span data-ttu-id="eb807-128">Definiert ein Listenformat für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="eb807-128">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="eb807-129">Element „Name“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-129">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="eb807-130">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="eb807-130">Required element.</span></span><br /><br /> <span data-ttu-id="eb807-131">Gibt den Namen an, der zum Verweisen auf die Sicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eb807-131">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="eb807-132">Element „TableControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-132">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="eb807-133">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="eb807-133">Optional element.</span></span><br /><br /> <span data-ttu-id="eb807-134">Definiert ein Tabellenformat für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="eb807-134">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="eb807-135">Viewselectedby-Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-135">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="eb807-136">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="eb807-136">Required element.</span></span><br /><br /> <span data-ttu-id="eb807-137">Definiert die .NET-Objekte, die in dieser Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eb807-137">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="eb807-138">Element „WideControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-138">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="eb807-139">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="eb807-139">Optional element.</span></span><br /><br /> <span data-ttu-id="eb807-140">Definiert ein breites Listenformat (Einzelwert) für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="eb807-140">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="eb807-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb807-141">Parent Elements</span></span>

|<span data-ttu-id="eb807-142">Element</span><span class="sxs-lookup"><span data-stu-id="eb807-142">Element</span></span>|<span data-ttu-id="eb807-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb807-143">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="eb807-144">Element „ViewDefinitions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-144">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="eb807-145">Definiert die Sichten, die zum Anzeigen von Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eb807-145">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="eb807-146">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="eb807-146">Remarks</span></span>

<span data-ttu-id="eb807-147">Weitere Informationen zu den Komponenten verschiedener Sichten und benutzerdefinierte Steuerelemente finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="eb807-147">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="eb807-148">Tabellen Ansichts Komponenten</span><span class="sxs-lookup"><span data-stu-id="eb807-148">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="eb807-149">Listen Ansichts Komponenten</span><span class="sxs-lookup"><span data-stu-id="eb807-149">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="eb807-150">Breite Ansichts Komponenten</span><span class="sxs-lookup"><span data-stu-id="eb807-150">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="eb807-151">Benutzerdefinierte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="eb807-151">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="eb807-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eb807-152">Example</span></span>

<span data-ttu-id="eb807-153">Dieses Beispiel zeigt ein- `View` Element, das eine Tabellenansicht für das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt definiert.</span><span class="sxs-lookup"><span data-stu-id="eb807-153">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>service</Name>
    <ViewSelectedBy>
      <TypeName>System.ServiceProcess.ServiceController</TypeName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="eb807-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb807-154">See Also</span></span>

[<span data-ttu-id="eb807-155">Element „ViewDefinitions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-155">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="eb807-156">Element „Name“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-156">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="eb807-157">Element „ViewSelectedBy“ (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-157">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="eb807-158">Element „Controls“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-158">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="eb807-159">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-159">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="eb807-160">Element „TableControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-160">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="eb807-161">Element „ListControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-161">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="eb807-162">Element „WideControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-162">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="eb807-163">CustomControl-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="eb807-163">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="eb807-164">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="eb807-164">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
