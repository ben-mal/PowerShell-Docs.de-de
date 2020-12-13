---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ViewSelectedBy“ (Format)
description: Element „ViewSelectedBy“ (Format)
ms.openlocfilehash: ac3c7de299b3009a067a476a024c6a6fcb5dce02
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667707"
---
# <a name="viewselectedby-element-format"></a><span data-ttu-id="5310b-103">Element „ViewSelectedBy“ (Format)</span><span class="sxs-lookup"><span data-stu-id="5310b-103">ViewSelectedBy Element (Format)</span></span>

<span data-ttu-id="5310b-104">Definiert die .NET-Objekte, die von der Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5310b-104">Defines the .NET objects that are displayed by the view.</span></span> <span data-ttu-id="5310b-105">Jede Ansicht muss mindestens ein .NET-Objekt angeben.</span><span class="sxs-lookup"><span data-stu-id="5310b-105">Each view must specify at least one .NET object.</span></span>

<span data-ttu-id="5310b-106">Viewdefinitions-Element (Format) View-Element (Format) viewselectedby-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="5310b-106">ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5310b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5310b-107">Syntax</span></span>

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5310b-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5310b-108">Attributes and Elements</span></span>

<span data-ttu-id="5310b-109">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `ViewSelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5310b-109">The following sections describe the attributes, child elements, and parent element of the `ViewSelectedBy` element.</span></span> <span data-ttu-id="5310b-110">Dieses Element muss mindestens ein untergeordnetes- `TypeName` Element oder ein- `SelectionSetName` Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="5310b-110">This element must contain at least one `TypeName` or `SelectionSetName` child element.</span></span> <span data-ttu-id="5310b-111">Es gibt keine Beschränkung für die Anzahl der untergeordneten Elemente, die angegeben werden können, und ihre Reihenfolge ist nicht signifikant.</span><span class="sxs-lookup"><span data-stu-id="5310b-111">There is no limit to the number of child elements that can be specified nor is their order significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="5310b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="5310b-112">Attributes</span></span>

<span data-ttu-id="5310b-113">Keine</span><span class="sxs-lookup"><span data-stu-id="5310b-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5310b-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5310b-114">Child Elements</span></span>

|<span data-ttu-id="5310b-115">Element</span><span class="sxs-lookup"><span data-stu-id="5310b-115">Element</span></span>|<span data-ttu-id="5310b-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5310b-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5310b-117">Element „TypeName“ für ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5310b-117">TypeName Element for ViewSelectedBy (Format)</span></span>](./typename-element-for-viewselectedby-format.md)|<span data-ttu-id="5310b-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="5310b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="5310b-119">Gibt ein .NET-Objekt an, das von der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5310b-119">Specifies a .NET object that is displayed by the view.</span></span>|
|[<span data-ttu-id="5310b-120">Element „SelectionSetName“ für ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5310b-120">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)|<span data-ttu-id="5310b-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="5310b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="5310b-122">Gibt einen Satz von .NET-Objekten an, die von der Sicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5310b-122">Specifies a set of .NET objects that are displayed by the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5310b-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5310b-123">Parent Elements</span></span>

|<span data-ttu-id="5310b-124">Element</span><span class="sxs-lookup"><span data-stu-id="5310b-124">Element</span></span>|<span data-ttu-id="5310b-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5310b-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5310b-126">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="5310b-126">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="5310b-127">Definiert eine Ansicht, in der ein oder mehrere .NET-Objekte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5310b-127">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5310b-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5310b-128">Remarks</span></span>

<span data-ttu-id="5310b-129">Weitere Informationen zur Verwendung dieses Elements in verschiedenen Ansichten finden Sie unter [Tabellen Ansichts Komponenten](./creating-a-table-view.md), [Listen Ansichts Komponenten](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md)und [Custom Control Components](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="5310b-129">For more information about how this element is used in different views, see [Table View Components](./creating-a-table-view.md), [List View Components](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md), and [Custom Control Components](./creating-custom-controls.md).</span></span>

<span data-ttu-id="5310b-130">Das- `SelectionSetName` Element wird verwendet, wenn die Formatierungs Datei eine Reihe von-Objekten definiert, die von mehreren Sichten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5310b-130">The `SelectionSetName` element is used when the formatting file defines a set of objects that are displayed by multiple views.</span></span> <span data-ttu-id="5310b-131">Weitere Informationen zum Definieren und referenziert von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="5310b-131">For more information about how selection sets are defined and referenced, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="5310b-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5310b-132">Example</span></span>

<span data-ttu-id="5310b-133">Im folgenden Beispiel wird gezeigt, wie das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt für eine Listenansicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5310b-133">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="5310b-134">Das gleiche Schema wird für Tabellen-, breiten-und benutzerdefinierte Sichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="5310b-134">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="5310b-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5310b-135">See Also</span></span>

[<span data-ttu-id="5310b-136">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="5310b-136">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="5310b-137">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="5310b-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="5310b-138">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="5310b-138">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="5310b-139">Erstellen von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="5310b-139">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="5310b-140">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="5310b-140">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="5310b-141">Element „SelectionSetName“ für ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5310b-141">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

[<span data-ttu-id="5310b-142">Tyname-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="5310b-142">TypeName Element (Format)</span></span>](./typename-element-for-viewselectedby-format.md)

[<span data-ttu-id="5310b-143">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="5310b-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
