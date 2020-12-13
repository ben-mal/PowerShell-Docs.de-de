---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSets“ (Format)
description: Element „SelectionSets“ (Format)
ms.openlocfilehash: e5c928dfb82bc6963b4a87aef9ec06d34cacfdcb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654923"
---
# <a name="selectionsets-element-format"></a><span data-ttu-id="818ff-103">Element „SelectionSets“ (Format)</span><span class="sxs-lookup"><span data-stu-id="818ff-103">SelectionSets Element (Format)</span></span>

<span data-ttu-id="818ff-104">Definiert die allgemeinen Sätze von .NET-Objekten, die von allen Sichten der Formatierungs Datei verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="818ff-104">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span> <span data-ttu-id="818ff-105">Die Sichten und Steuerelemente der Formatierungs Datei können auf den gesamten Satz von Objekten verweisen, indem Sie nur den Namen des Auswahl Satzes verwenden.</span><span class="sxs-lookup"><span data-stu-id="818ff-105">The views and controls of the formatting file can reference the complete set of objects by using only the name of the selection set.</span></span>

<span data-ttu-id="818ff-106">Konfigurationselement selectionsets-Element Format</span><span class="sxs-lookup"><span data-stu-id="818ff-106">Configuration Element SelectionSets Element Format</span></span>

## <a name="syntax"></a><span data-ttu-id="818ff-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="818ff-107">Syntax</span></span>

```xml
<SelectionSets>
  <SelectionSet>...</SelectionSet>
</SelectionSets>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="818ff-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="818ff-108">Attributes and Elements</span></span>

<span data-ttu-id="818ff-109">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `SelectionSets` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="818ff-109">The following sections describe the attributes, child elements, and parent element of the `SelectionSets` element.</span></span> <span data-ttu-id="818ff-110">Jedes untergeordnete Element definiert einen Satz von Objekten, auf die durch den Namen des Satzes verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="818ff-110">Each child element defines a set of objects that can be referenced by the name of the set.</span></span> <span data-ttu-id="818ff-111">Die Reihenfolge der untergeordneten Elemente ist nicht signifikant.</span><span class="sxs-lookup"><span data-stu-id="818ff-111">The order of the child elements is not significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="818ff-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="818ff-112">Attributes</span></span>

<span data-ttu-id="818ff-113">Keine</span><span class="sxs-lookup"><span data-stu-id="818ff-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="818ff-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="818ff-114">Child Elements</span></span>

|<span data-ttu-id="818ff-115">Element</span><span class="sxs-lookup"><span data-stu-id="818ff-115">Element</span></span>|<span data-ttu-id="818ff-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="818ff-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="818ff-117">Element „SelectionSet“ (Format)</span><span class="sxs-lookup"><span data-stu-id="818ff-117">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="818ff-118">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="818ff-118">Required element.</span></span><br /><br /> <span data-ttu-id="818ff-119">Definiert einen einzelnen Satz von .NET-Objekten, auf die durch den Namen des Satzes verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="818ff-119">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="818ff-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="818ff-120">Parent Elements</span></span>

|<span data-ttu-id="818ff-121">Element</span><span class="sxs-lookup"><span data-stu-id="818ff-121">Element</span></span>|<span data-ttu-id="818ff-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="818ff-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="818ff-123">Configuration-Element</span><span class="sxs-lookup"><span data-stu-id="818ff-123">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="818ff-124">Stellt das Element der obersten Ebene einer Formatierungs Datei dar.</span><span class="sxs-lookup"><span data-stu-id="818ff-124">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="818ff-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="818ff-125">Remarks</span></span>

<span data-ttu-id="818ff-126">Sie können Auswahl Sätze verwenden, wenn Sie über einen Satz verwandter Objekte verfügen, auf die Sie verweisen möchten, indem Sie einen einzelnen Namen verwenden, z. b. eine Gruppe von Objekten, die durch Vererbung verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="818ff-126">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="818ff-127">Wenn Sie die Ansichten definieren, können Sie den Satz von-Objekten angeben, indem Sie den Namen des Auswahl Satzes verwenden, anstatt alle Objekte in jeder Ansicht aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="818ff-127">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="818ff-128">Beim Definieren der Sichten der Formatierungs Datei oder der Definitionen der Sichten werden allgemeine Auswahl Sätze durch ihren Namen angegeben.</span><span class="sxs-lookup"><span data-stu-id="818ff-128">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="818ff-129">In diesen Fällen gibt das untergeordnete `SelectionSetName` -Element des `ViewSelectedBy` -Elements und des- `EntrySelectedBy` Elements die zu verwendende Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="818ff-129">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="818ff-130">Weitere Informationen zu Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="818ff-130">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="818ff-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="818ff-131">See Also</span></span>

[<span data-ttu-id="818ff-132">Konfigurationselement</span><span class="sxs-lookup"><span data-stu-id="818ff-132">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="818ff-133">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="818ff-133">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="818ff-134">Element „SelectionSet“ (Format)</span><span class="sxs-lookup"><span data-stu-id="818ff-134">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="818ff-135">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="818ff-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
