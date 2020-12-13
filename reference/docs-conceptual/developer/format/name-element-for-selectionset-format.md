---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Name“ für SelectionSet (Format)
description: Element „Name“ für SelectionSet (Format)
ms.openlocfilehash: 98c13be6ea352055231fbdb3a60f0eb508f661b8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666456"
---
# <a name="name-element-for-selectionset-format"></a><span data-ttu-id="2b783-103">Element „Name“ für SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="2b783-103">Name Element for SelectionSet (Format)</span></span>

<span data-ttu-id="2b783-104">Gibt den Namen an, mit dem auf den Auswahl Satz verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2b783-104">Specifies the name used to reference the selection set.</span></span>

<span data-ttu-id="2b783-105">Configuration-Element (Format) selectionsets-Element (Format) SelectionSet-Element (Format) Name-Element von SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="2b783-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Name Element of SelectionSet (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2b783-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b783-106">Syntax</span></span>

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2b783-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2b783-107">Attributes and Elements</span></span>

<span data-ttu-id="2b783-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `Name` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2b783-108">The following sections describe the attributes, child elements, and parent element of the `Name` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2b783-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="2b783-109">Attributes</span></span>

<span data-ttu-id="2b783-110">Keine</span><span class="sxs-lookup"><span data-stu-id="2b783-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2b783-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2b783-111">Child Elements</span></span>

<span data-ttu-id="2b783-112">Keine</span><span class="sxs-lookup"><span data-stu-id="2b783-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2b783-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2b783-113">Parent Elements</span></span>

|<span data-ttu-id="2b783-114">Element</span><span class="sxs-lookup"><span data-stu-id="2b783-114">Element</span></span>|<span data-ttu-id="2b783-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b783-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2b783-116">Element „SelectionSet“ (Format)</span><span class="sxs-lookup"><span data-stu-id="2b783-116">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="2b783-117">Definiert einen einzelnen Satz von .NET-Objekten, auf die durch den Namen des Satzes verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="2b783-117">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2b783-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="2b783-118">Text Value</span></span>

<span data-ttu-id="2b783-119">Geben Sie den Namen an, der auf den Auswahl Satz verweist.</span><span class="sxs-lookup"><span data-stu-id="2b783-119">Specify the name to reference the selection set.</span></span> <span data-ttu-id="2b783-120">Es gibt keine Einschränkungen, welche Zeichen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="2b783-120">There are no restrictions as to what characters can be used.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b783-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2b783-121">Remarks</span></span>

<span data-ttu-id="2b783-122">Der hier angegebene Name wird im- `SelectionSetName` Element verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b783-122">The name specified here is used in the `SelectionSetName` element.</span></span> <span data-ttu-id="2b783-123">Der Auswahl Satz, der von einer Ansicht verwendet werden kann, durch eine Definition einer Ansicht (Ansichten können mehrere Definitionen aufweisen) oder durch Angeben einer Auswahlbedingung.</span><span class="sxs-lookup"><span data-stu-id="2b783-123">The selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span> <span data-ttu-id="2b783-124">Weitere Informationen zu Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="2b783-124">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="2b783-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b783-125">Example</span></span>

<span data-ttu-id="2b783-126">Dieses Beispiel zeigt ein- `SelectionSet` Element, das vier .NET-Typen definiert.</span><span class="sxs-lookup"><span data-stu-id="2b783-126">This example shows a `SelectionSet` element that defines four .NET types.</span></span> <span data-ttu-id="2b783-127">Der Name des Auswahl Satzes lautet "filesystemtypes".</span><span class="sxs-lookup"><span data-stu-id="2b783-127">The name of the selection set is "FileSystemTypes".</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2b783-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b783-128">See Also</span></span>

[<span data-ttu-id="2b783-129">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="2b783-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="2b783-130">Element „SelectionSet“ (Format)</span><span class="sxs-lookup"><span data-stu-id="2b783-130">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="2b783-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="2b783-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
