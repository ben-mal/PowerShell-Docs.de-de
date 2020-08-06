---
title: SelectionSet-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: cf47229993458492c712d28e04913e75d1bde386
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783397"
---
# <a name="selectionset-element-format"></a><span data-ttu-id="9a3f2-102">Element „SelectionSet“ (Format)</span><span class="sxs-lookup"><span data-stu-id="9a3f2-102">SelectionSet Element (Format)</span></span>

<span data-ttu-id="9a3f2-103">Definiert einen Satz von .NET-Objekten, auf die durch den Namen des Satzes verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-103">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>

<span data-ttu-id="9a3f2-104">Configuration-Element (Format) selectionsets-Element (Format) SelectionSet-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="9a3f2-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9a3f2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a3f2-105">Syntax</span></span>

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9a3f2-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9a3f2-106">Attributes and Elements</span></span>

<span data-ttu-id="9a3f2-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `SelectionSet` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSet` element.</span></span> <span data-ttu-id="9a3f2-108">Jeder Auswahl Satz muss über einen Namen verfügen, und er muss die .NET-Objekte des Satzes angeben.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-108">Each selection set must have a name, and it must specify the .NET objects of the set.</span></span>

### <a name="attributes"></a><span data-ttu-id="9a3f2-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="9a3f2-109">Attributes</span></span>

<span data-ttu-id="9a3f2-110">Keine</span><span class="sxs-lookup"><span data-stu-id="9a3f2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9a3f2-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9a3f2-111">Child Elements</span></span>

|<span data-ttu-id="9a3f2-112">Element</span><span class="sxs-lookup"><span data-stu-id="9a3f2-112">Element</span></span>|<span data-ttu-id="9a3f2-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9a3f2-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9a3f2-114">Element „Name“ für SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="9a3f2-114">Name Element for SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)|<span data-ttu-id="9a3f2-115">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-115">Required element.</span></span><br /><br /> <span data-ttu-id="9a3f2-116">Gibt den Namen an, mit dem auf den Auswahl Satz verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-116">Specifies the name used to reference the selection set.</span></span>|
|[<span data-ttu-id="9a3f2-117">Types-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="9a3f2-117">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="9a3f2-118">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-118">Required element.</span></span><br /><br /> <span data-ttu-id="9a3f2-119">Definiert die .NET-Objekte, die sich im Auswahl Satz befinden.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-119">Defines the .NET objects that are in the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9a3f2-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9a3f2-120">Parent Elements</span></span>

|<span data-ttu-id="9a3f2-121">Element</span><span class="sxs-lookup"><span data-stu-id="9a3f2-121">Element</span></span>|<span data-ttu-id="9a3f2-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9a3f2-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9a3f2-123">Selectionsets-Element Format</span><span class="sxs-lookup"><span data-stu-id="9a3f2-123">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="9a3f2-124">Definiert die allgemeinen Sätze von .NET-Objekten, die von allen Sichten der Formatierungs Datei verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-124">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9a3f2-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9a3f2-125">Remarks</span></span>

<span data-ttu-id="9a3f2-126">Sie können Auswahl Sätze verwenden, wenn Sie über einen Satz verwandter Objekte verfügen, auf die Sie verweisen möchten, indem Sie einen einzelnen Namen verwenden, z. b. eine Gruppe von Objekten, die durch Vererbung verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-126">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="9a3f2-127">Wenn Sie die Ansichten definieren, können Sie den Satz von-Objekten angeben, indem Sie den Namen des Auswahl Satzes verwenden, anstatt alle Objekte in jeder Ansicht aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-127">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="9a3f2-128">Beim Definieren der Sichten der Formatierungs Datei oder der Definitionen der Sichten werden allgemeine Auswahl Sätze durch ihren Namen angegeben.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-128">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="9a3f2-129">In diesen Fällen gibt das untergeordnete `SelectionSetName` -Element des `ViewSelectedBy` -Elements und des- `EntrySelectedBy` Elements die zu verwendende Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-129">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="9a3f2-130">Weitere Informationen zu Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="9a3f2-130">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="9a3f2-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9a3f2-131">Example</span></span>

<span data-ttu-id="9a3f2-132">Das folgende Beispiel zeigt ein- `SelectionSet` Element, das vier .NET-Typen definiert.</span><span class="sxs-lookup"><span data-stu-id="9a3f2-132">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9a3f2-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a3f2-133">See Also</span></span>

[<span data-ttu-id="9a3f2-134">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="9a3f2-134">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="9a3f2-135">Name-Element von SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="9a3f2-135">Name Element of SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="9a3f2-136">Element „SelectionSets“ (Format)</span><span class="sxs-lookup"><span data-stu-id="9a3f2-136">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="9a3f2-137">Types-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="9a3f2-137">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="9a3f2-138">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="9a3f2-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
