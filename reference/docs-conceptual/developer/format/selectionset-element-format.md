---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSet“ (Format)
description: Element „SelectionSet“ (Format)
ms.openlocfilehash: 944aa83569ad8ca789746a71f60e5da5c19fbf01
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647862"
---
# <a name="selectionset-element-format"></a><span data-ttu-id="b1b71-103">Element „SelectionSet“ (Format)</span><span class="sxs-lookup"><span data-stu-id="b1b71-103">SelectionSet Element (Format)</span></span>

<span data-ttu-id="b1b71-104">Definiert einen Satz von .NET-Objekten, auf die durch den Namen des Satzes verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b1b71-104">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>

<span data-ttu-id="b1b71-105">Configuration-Element (Format) selectionsets-Element (Format) SelectionSet-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="b1b71-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b1b71-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1b71-106">Syntax</span></span>

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b1b71-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b1b71-107">Attributes and Elements</span></span>

<span data-ttu-id="b1b71-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `SelectionSet` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b1b71-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSet` element.</span></span> <span data-ttu-id="b1b71-109">Jeder Auswahl Satz muss über einen Namen verfügen, und er muss die .NET-Objekte des Satzes angeben.</span><span class="sxs-lookup"><span data-stu-id="b1b71-109">Each selection set must have a name, and it must specify the .NET objects of the set.</span></span>

### <a name="attributes"></a><span data-ttu-id="b1b71-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b1b71-110">Attributes</span></span>

<span data-ttu-id="b1b71-111">Keine</span><span class="sxs-lookup"><span data-stu-id="b1b71-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b1b71-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1b71-112">Child Elements</span></span>

|<span data-ttu-id="b1b71-113">Element</span><span class="sxs-lookup"><span data-stu-id="b1b71-113">Element</span></span>|<span data-ttu-id="b1b71-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1b71-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b1b71-115">Element „Name“ für SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="b1b71-115">Name Element for SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)|<span data-ttu-id="b1b71-116">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="b1b71-116">Required element.</span></span><br /><br /> <span data-ttu-id="b1b71-117">Gibt den Namen an, mit dem auf den Auswahl Satz verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b1b71-117">Specifies the name used to reference the selection set.</span></span>|
|[<span data-ttu-id="b1b71-118">Types-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="b1b71-118">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="b1b71-119">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="b1b71-119">Required element.</span></span><br /><br /> <span data-ttu-id="b1b71-120">Definiert die .NET-Objekte, die sich im Auswahl Satz befinden.</span><span class="sxs-lookup"><span data-stu-id="b1b71-120">Defines the .NET objects that are in the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b1b71-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1b71-121">Parent Elements</span></span>

|<span data-ttu-id="b1b71-122">Element</span><span class="sxs-lookup"><span data-stu-id="b1b71-122">Element</span></span>|<span data-ttu-id="b1b71-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1b71-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b1b71-124">Selectionsets-Element Format</span><span class="sxs-lookup"><span data-stu-id="b1b71-124">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="b1b71-125">Definiert die allgemeinen Sätze von .NET-Objekten, die von allen Sichten der Formatierungs Datei verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b1b71-125">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b1b71-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b1b71-126">Remarks</span></span>

<span data-ttu-id="b1b71-127">Sie können Auswahl Sätze verwenden, wenn Sie über einen Satz verwandter Objekte verfügen, auf die Sie verweisen möchten, indem Sie einen einzelnen Namen verwenden, z. b. eine Gruppe von Objekten, die durch Vererbung verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="b1b71-127">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="b1b71-128">Wenn Sie die Ansichten definieren, können Sie den Satz von-Objekten angeben, indem Sie den Namen des Auswahl Satzes verwenden, anstatt alle Objekte in jeder Ansicht aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="b1b71-128">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="b1b71-129">Beim Definieren der Sichten der Formatierungs Datei oder der Definitionen der Sichten werden allgemeine Auswahl Sätze durch ihren Namen angegeben.</span><span class="sxs-lookup"><span data-stu-id="b1b71-129">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="b1b71-130">In diesen Fällen gibt das untergeordnete `SelectionSetName` -Element des `ViewSelectedBy` -Elements und des- `EntrySelectedBy` Elements die zu verwendende Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="b1b71-130">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="b1b71-131">Weitere Informationen zu Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b1b71-131">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="b1b71-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1b71-132">Example</span></span>

<span data-ttu-id="b1b71-133">Das folgende Beispiel zeigt ein- `SelectionSet` Element, das vier .NET-Typen definiert.</span><span class="sxs-lookup"><span data-stu-id="b1b71-133">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b1b71-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b1b71-134">See Also</span></span>

[<span data-ttu-id="b1b71-135">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="b1b71-135">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b1b71-136">Name-Element von SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="b1b71-136">Name Element of SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="b1b71-137">Element „SelectionSets“ (Format)</span><span class="sxs-lookup"><span data-stu-id="b1b71-137">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="b1b71-138">Types-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="b1b71-138">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="b1b71-139">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="b1b71-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
