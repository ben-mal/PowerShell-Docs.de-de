---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Types“ für SelectionSet (Format)
description: Element „Types“ für SelectionSet (Format)
ms.openlocfilehash: ff3c24e7f52f862dc416b88d50983196ce907012
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645449"
---
# <a name="types-element-for-selectionset-format"></a><span data-ttu-id="3467d-103">Element „Types“ für SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="3467d-103">Types Element for SelectionSet (Format)</span></span>

<span data-ttu-id="3467d-104">Definiert die .NET-Objekte, die sich im Auswahl Satz befinden.</span><span class="sxs-lookup"><span data-stu-id="3467d-104">Defines the .NET objects that are in the selection set.</span></span>

<span data-ttu-id="3467d-105">Configuration-Element (Format) selectionsets-Element (Format) SelectionSet-Element (Format) Types-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="3467d-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3467d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3467d-106">Syntax</span></span>

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="3467d-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3467d-107">Attributes and Elements</span></span>

<span data-ttu-id="3467d-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Types` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3467d-108">The following sections describe the attributes, child elements, and the parent element of the `Types` element.</span></span> <span data-ttu-id="3467d-109">Es muss mindestens ein untergeordnetes Element vorhanden sein, es gibt jedoch keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="3467d-109">There must be at least one child element, but there is no maximum limit to the number of child elements that can be added.</span></span>

### <a name="attributes"></a><span data-ttu-id="3467d-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="3467d-110">Attributes</span></span>

<span data-ttu-id="3467d-111">Keine</span><span class="sxs-lookup"><span data-stu-id="3467d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3467d-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3467d-112">Child Elements</span></span>

|<span data-ttu-id="3467d-113">Element</span><span class="sxs-lookup"><span data-stu-id="3467d-113">Element</span></span>|<span data-ttu-id="3467d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3467d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3467d-115">Typname-Element von Typen (Format)</span><span class="sxs-lookup"><span data-stu-id="3467d-115">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)|<span data-ttu-id="3467d-116">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="3467d-116">Required element.</span></span><br /><br /> <span data-ttu-id="3467d-117">Gibt das .NET-Objekt an, das zum Auswahl Satz gehört.</span><span class="sxs-lookup"><span data-stu-id="3467d-117">Specifies the .NET object that belongs to the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3467d-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3467d-118">Parent Elements</span></span>

|<span data-ttu-id="3467d-119">Element</span><span class="sxs-lookup"><span data-stu-id="3467d-119">Element</span></span>|<span data-ttu-id="3467d-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3467d-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3467d-121">Element „SelectionSet“ (Format)</span><span class="sxs-lookup"><span data-stu-id="3467d-121">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="3467d-122">Definiert einen Satz von .NET-Objekten, auf die durch den Namen des Satzes verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3467d-122">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3467d-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3467d-123">Remarks</span></span>

<span data-ttu-id="3467d-124">Die von diesem Element definierten Objekte bilden einen Auswahl Satz, der von einer Ansicht, durch eine Definition einer Ansicht (Sichten können mehrere Definitionen aufweisen) oder durch Angeben einer Auswahlbedingung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3467d-124">The objects defined by this element make up a selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span>  <span data-ttu-id="3467d-125">Weitere Informationen zu Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="3467d-125">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="3467d-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3467d-126">Example</span></span>

<span data-ttu-id="3467d-127">Dieses Beispiel zeigt ein- `SelectionSet` Element, das vier .NET-Typen definiert.</span><span class="sxs-lookup"><span data-stu-id="3467d-127">This example shows a `SelectionSet` element that defines four .NET types.</span></span>

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

## <a name="see-also"></a><span data-ttu-id="3467d-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3467d-128">See Also</span></span>

[<span data-ttu-id="3467d-129">Definieren von Objekt Sätzen</span><span class="sxs-lookup"><span data-stu-id="3467d-129">Defining Sets of Objects</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="3467d-130">Element „SelectionSet“ (Format)</span><span class="sxs-lookup"><span data-stu-id="3467d-130">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="3467d-131">Typname-Element von Typen (Format)</span><span class="sxs-lookup"><span data-stu-id="3467d-131">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)

[<span data-ttu-id="3467d-132">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="3467d-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
