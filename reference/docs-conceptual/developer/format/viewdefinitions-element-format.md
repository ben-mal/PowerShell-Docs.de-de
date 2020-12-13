---
ms.date: 09/13/2016
ms.topic: reference
title: Element „ViewDefinitions“ (Format)
description: Element „ViewDefinitions“ (Format)
ms.openlocfilehash: fceef0e5ec91e8c59a7b2b90fd31ca422ff0c94d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664589"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="34063-103">Element „ViewDefinitions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="34063-103">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="34063-104">Definiert die Sichten, die zum Anzeigen von .NET-Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34063-104">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="34063-105">Diese Sichten können die Eigenschaften und Skript Werte eines Objekts in einem Tabellenformat, einem Listenformat, einem breiten Format und einem benutzerdefinierten Steuerelement Format anzeigen.</span><span class="sxs-lookup"><span data-stu-id="34063-105">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="34063-106">Configuration-Element (Format) viewdefinitions (Format XML)-Element</span><span class="sxs-lookup"><span data-stu-id="34063-106">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="34063-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="34063-107">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="34063-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="34063-108">Attributes and Elements</span></span>

<span data-ttu-id="34063-109">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `ViewDefinitions` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34063-109">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="34063-110">Es gibt keine Beschränkung für die Anzahl der Sichten, die in einer Formatierungs Datei definiert werden können, und Sie können in beliebiger Reihenfolge hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="34063-110">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="34063-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="34063-111">Attributes</span></span>

<span data-ttu-id="34063-112">Keine</span><span class="sxs-lookup"><span data-stu-id="34063-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="34063-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34063-113">Child Elements</span></span>

|<span data-ttu-id="34063-114">Element</span><span class="sxs-lookup"><span data-stu-id="34063-114">Element</span></span>|<span data-ttu-id="34063-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34063-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="34063-116">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="34063-116">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="34063-117">Definiert eine Ansicht, die verwendet wird, um ein oder mehrere .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="34063-117">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="34063-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34063-118">Parent Elements</span></span>

|<span data-ttu-id="34063-119">Element</span><span class="sxs-lookup"><span data-stu-id="34063-119">Element</span></span>|<span data-ttu-id="34063-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34063-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="34063-121">Element „Configuration“ (Format)</span><span class="sxs-lookup"><span data-stu-id="34063-121">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="34063-122">Stellt das Element der obersten Ebene einer Formatierungs Datei dar.</span><span class="sxs-lookup"><span data-stu-id="34063-122">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="34063-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="34063-123">Remarks</span></span>

<span data-ttu-id="34063-124">Weitere Informationen zu den Komponenten der verschiedenen Sicht Typen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="34063-124">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="34063-125">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="34063-125">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="34063-126">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="34063-126">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="34063-127">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="34063-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="34063-128">Benutzerdefinierte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="34063-128">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="34063-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34063-129">Example</span></span>

<span data-ttu-id="34063-130">Dieses Beispiel zeigt ein `ViewDefinitions` -Element, das die übergeordneten Elemente für eine Tabellenansicht und eine Listenansicht enthält.</span><span class="sxs-lookup"><span data-stu-id="34063-130">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <TableControl>...</TableControl>
    </View>
    <View>
      <ListControl>...</ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a><span data-ttu-id="34063-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34063-131">See Also</span></span>

[<span data-ttu-id="34063-132">Element „Configuration“ (Format)</span><span class="sxs-lookup"><span data-stu-id="34063-132">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="34063-133">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="34063-133">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="34063-134">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="34063-134">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="34063-135">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="34063-135">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="34063-136">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="34063-136">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="34063-137">Benutzerdefinierte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="34063-137">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="34063-138">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="34063-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
