---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TypeName“ für Types (Format)
description: Element „TypeName“ für Types (Format)
ms.openlocfilehash: c656b8e7e5877b72ff2164e5b417857273cada61
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664620"
---
# <a name="typename-element-for-types-format"></a><span data-ttu-id="2144f-103">Element „TypeName“ für Types (Format)</span><span class="sxs-lookup"><span data-stu-id="2144f-103">TypeName Element for Types (Format)</span></span>

<span data-ttu-id="2144f-104">Gibt den .NET-Typ eines Objekts an, das zum Auswahl Satz gehört.</span><span class="sxs-lookup"><span data-stu-id="2144f-104">Specifies the .NET type of an object that belongs to the selection set.</span></span>

<span data-ttu-id="2144f-105">Configuration-Element (Format) selectionsets-Element (Format) SelectionSet-Element (Format) Types-Element (Format) Typname Element of Types (Format)</span><span class="sxs-lookup"><span data-stu-id="2144f-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format) TypeName Element of Types (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2144f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2144f-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2144f-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2144f-107">Attributes and Elements</span></span>

<span data-ttu-id="2144f-108">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `TypeName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2144f-108">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span> <span data-ttu-id="2144f-109">`TypeName`Im Auswahl Satz muss mindestens ein Element enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="2144f-109">At least one `TypeName` element must be included in the selection set.</span></span>

### <a name="attributes"></a><span data-ttu-id="2144f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="2144f-110">Attributes</span></span>

<span data-ttu-id="2144f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="2144f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2144f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2144f-112">Child Elements</span></span>

<span data-ttu-id="2144f-113">Keine</span><span class="sxs-lookup"><span data-stu-id="2144f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2144f-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2144f-114">Parent Elements</span></span>

|<span data-ttu-id="2144f-115">Element</span><span class="sxs-lookup"><span data-stu-id="2144f-115">Element</span></span>|<span data-ttu-id="2144f-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2144f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2144f-117">Types-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="2144f-117">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="2144f-118">Definiert die .NET-Objekte, die sich im Auswahl Satz befinden.</span><span class="sxs-lookup"><span data-stu-id="2144f-118">Defines the .NET objects that are in the selection set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2144f-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="2144f-119">Text Value</span></span>

<span data-ttu-id="2144f-120">Geben Sie den voll qualifizierten Namen des .net-Typs an.</span><span class="sxs-lookup"><span data-stu-id="2144f-120">Specify the fully qualified name for the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="2144f-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2144f-121">Remarks</span></span>

<span data-ttu-id="2144f-122">Sie können Auswahl Sätze verwenden, wenn Sie über einen Satz verwandter Objekte verfügen, auf die Sie verweisen möchten, indem Sie einen einzelnen Namen verwenden, z. b. eine Gruppe von Objekten, die durch Vererbung verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="2144f-122">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="2144f-123">Wenn Sie die Ansichten definieren, können Sie den Satz von-Objekten angeben, indem Sie den Namen des Auswahl Satzes verwenden, anstatt alle Objekte in jeder Ansicht aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="2144f-123">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="2144f-124">Allgemeine Auswahl Sätze werden durch ihren Namen angegeben, wenn die Ansichten der Formatierungs Datei definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2144f-124">Common selection sets are specified by their name when defining the views of the formatting file.</span></span> <span data-ttu-id="2144f-125">In diesen Fällen gibt das untergeordnete- `SelectionSetName` Element des- `ViewSelectedBy` Elements für die Sicht den Satz an.</span><span class="sxs-lookup"><span data-stu-id="2144f-125">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` element for the view specifies the set.</span></span> <span data-ttu-id="2144f-126">Bei verschiedenen Einträgen einer Sicht kann jedoch auch ein Auswahl Satz angegeben werden, der nur für diesen Eintrag der Sicht gilt.</span><span class="sxs-lookup"><span data-stu-id="2144f-126">However, different entries of a view can also specify a selection set that applies to only that entry of the view.</span></span> <span data-ttu-id="2144f-127">Weitere Informationen zu Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="2144f-127">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="2144f-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2144f-128">Example</span></span>

<span data-ttu-id="2144f-129">Das folgende Beispiel zeigt ein- `SelectionSet` Element, das vier .NET-Typen definiert.</span><span class="sxs-lookup"><span data-stu-id="2144f-129">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

```
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

## <a name="see-also"></a><span data-ttu-id="2144f-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2144f-130">See Also</span></span>

[<span data-ttu-id="2144f-131">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="2144f-131">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="2144f-132">Element „SelectionSet“ (Format)</span><span class="sxs-lookup"><span data-stu-id="2144f-132">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="2144f-133">Element „SelectionSets“ (Format)</span><span class="sxs-lookup"><span data-stu-id="2144f-133">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="2144f-134">Types-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="2144f-134">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="2144f-135">Schreiben einer Windows PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="2144f-135">Writing a Windows PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
