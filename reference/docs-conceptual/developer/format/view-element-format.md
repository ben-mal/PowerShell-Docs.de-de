---
title: View-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: c0c6fa373cfca3a55a62f201e1eabc6a1e308ef7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785029"
---
# <a name="view-element-format"></a><span data-ttu-id="60441-102">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-102">View Element (Format)</span></span>

<span data-ttu-id="60441-103">Definiert eine Ansicht, in der ein oder mehrere .NET-Objekte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="60441-103">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="60441-104">Es gibt keine Beschränkung für die Anzahl der Sichten, die in einer Formatierungs Datei definiert werden können.</span><span class="sxs-lookup"><span data-stu-id="60441-104">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="60441-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="60441-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="60441-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="60441-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="60441-107">Attributes and Elements</span></span>

<span data-ttu-id="60441-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `View` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="60441-108">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="60441-109">Sie müssen nur eines der untergeordneten Steuerelemente des Steuer Elements angeben, und Sie müssen den Namen der Ansicht und die Objekte, die die Sicht verwenden, angeben.</span><span class="sxs-lookup"><span data-stu-id="60441-109">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="60441-110">Definieren von benutzerdefinierten Steuerelementen, Gruppieren von Objekten und angeben, ob die Ansicht out-of-Band ist, sind optional.</span><span class="sxs-lookup"><span data-stu-id="60441-110">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="60441-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="60441-111">Attributes</span></span>

<span data-ttu-id="60441-112">Keine</span><span class="sxs-lookup"><span data-stu-id="60441-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="60441-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="60441-113">Child Elements</span></span>

|<span data-ttu-id="60441-114">Element</span><span class="sxs-lookup"><span data-stu-id="60441-114">Element</span></span>|<span data-ttu-id="60441-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="60441-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="60441-116">Element „Controls“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-116">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="60441-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="60441-117">Optional element.</span></span><br /><br /> <span data-ttu-id="60441-118">Definiert eine Gruppe von Steuerelementen, auf die über Ihren Namen in der Ansicht verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="60441-118">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="60441-119">CustomControl-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-119">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="60441-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="60441-120">Optional element.</span></span><br /><br /> <span data-ttu-id="60441-121">Definiert ein benutzerdefiniertes Steuerelement Format für die Ansicht.</span><span class="sxs-lookup"><span data-stu-id="60441-121">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="60441-122">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-122">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="60441-123">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="60441-123">Optional element.</span></span><br /><br /> <span data-ttu-id="60441-124">Definiert, wie die Member der .NET-Objekte gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="60441-124">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="60441-125">Element „ListControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-125">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="60441-126">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="60441-126">Optional element.</span></span><br /><br /> <span data-ttu-id="60441-127">Definiert ein Listenformat für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="60441-127">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="60441-128">Element „Name“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-128">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="60441-129">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="60441-129">Required element.</span></span><br /><br /> <span data-ttu-id="60441-130">Gibt den Namen an, der zum Verweisen auf die Sicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="60441-130">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="60441-131">Element „TableControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="60441-132">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="60441-132">Optional element.</span></span><br /><br /> <span data-ttu-id="60441-133">Definiert ein Tabellenformat für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="60441-133">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="60441-134">Viewselectedby-Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-134">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="60441-135">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="60441-135">Required element.</span></span><br /><br /> <span data-ttu-id="60441-136">Definiert die .NET-Objekte, die in dieser Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="60441-136">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="60441-137">Element „WideControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-137">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="60441-138">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="60441-138">Optional element.</span></span><br /><br /> <span data-ttu-id="60441-139">Definiert ein breites Listenformat (Einzelwert) für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="60441-139">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="60441-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="60441-140">Parent Elements</span></span>

|<span data-ttu-id="60441-141">Element</span><span class="sxs-lookup"><span data-stu-id="60441-141">Element</span></span>|<span data-ttu-id="60441-142">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="60441-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="60441-143">Element „ViewDefinitions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-143">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="60441-144">Definiert die Sichten, die zum Anzeigen von Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="60441-144">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="60441-145">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="60441-145">Remarks</span></span>

<span data-ttu-id="60441-146">Weitere Informationen zu den Komponenten verschiedener Sichten und benutzerdefinierte Steuerelemente finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="60441-146">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="60441-147">Tabellen Ansichts Komponenten</span><span class="sxs-lookup"><span data-stu-id="60441-147">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="60441-148">Listen Ansichts Komponenten</span><span class="sxs-lookup"><span data-stu-id="60441-148">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="60441-149">Breite Ansichts Komponenten</span><span class="sxs-lookup"><span data-stu-id="60441-149">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="60441-150">Benutzerdefinierte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="60441-150">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="60441-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60441-151">Example</span></span>

<span data-ttu-id="60441-152">Dieses Beispiel zeigt ein- `View` Element, das eine Tabellenansicht für das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt definiert.</span><span class="sxs-lookup"><span data-stu-id="60441-152">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="60441-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60441-153">See Also</span></span>

[<span data-ttu-id="60441-154">Element „ViewDefinitions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-154">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="60441-155">Element „Name“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-155">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="60441-156">Element „ViewSelectedBy“ (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-156">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="60441-157">Element „Controls“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-157">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="60441-158">Element „GroupBy“ für View (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-158">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="60441-159">Element „TableControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-159">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="60441-160">Element „ListControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-160">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="60441-161">Element „WideControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-161">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="60441-162">CustomControl-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="60441-162">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="60441-163">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="60441-163">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
