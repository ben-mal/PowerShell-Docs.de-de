---
title: Types-Element für SelectionSet (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 9978daefb3e97ab131774ca4dff633dde6b4dfbf
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772517"
---
# <a name="types-element-for-selectionset-format"></a><span data-ttu-id="cff1e-102">Element „Types“ für SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="cff1e-102">Types Element for SelectionSet (Format)</span></span>

<span data-ttu-id="cff1e-103">Definiert die .NET-Objekte, die sich im Auswahl Satz befinden.</span><span class="sxs-lookup"><span data-stu-id="cff1e-103">Defines the .NET objects that are in the selection set.</span></span>

<span data-ttu-id="cff1e-104">Configuration-Element (Format) selectionsets-Element (Format) SelectionSet-Element (Format) Types-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="cff1e-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cff1e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cff1e-105">Syntax</span></span>

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="cff1e-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cff1e-106">Attributes and Elements</span></span>

<span data-ttu-id="cff1e-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Types` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cff1e-107">The following sections describe the attributes, child elements, and the parent element of the `Types` element.</span></span> <span data-ttu-id="cff1e-108">Es muss mindestens ein untergeordnetes Element vorhanden sein, es gibt jedoch keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="cff1e-108">There must be at least one child element, but there is no maximum limit to the number of child elements that can be added.</span></span>

### <a name="attributes"></a><span data-ttu-id="cff1e-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="cff1e-109">Attributes</span></span>

<span data-ttu-id="cff1e-110">Keine</span><span class="sxs-lookup"><span data-stu-id="cff1e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cff1e-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cff1e-111">Child Elements</span></span>

|<span data-ttu-id="cff1e-112">Element</span><span class="sxs-lookup"><span data-stu-id="cff1e-112">Element</span></span>|<span data-ttu-id="cff1e-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cff1e-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cff1e-114">Typname-Element von Typen (Format)</span><span class="sxs-lookup"><span data-stu-id="cff1e-114">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)|<span data-ttu-id="cff1e-115">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="cff1e-115">Required element.</span></span><br /><br /> <span data-ttu-id="cff1e-116">Gibt das .NET-Objekt an, das zum Auswahl Satz gehört.</span><span class="sxs-lookup"><span data-stu-id="cff1e-116">Specifies the .NET object that belongs to the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cff1e-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cff1e-117">Parent Elements</span></span>

|<span data-ttu-id="cff1e-118">Element</span><span class="sxs-lookup"><span data-stu-id="cff1e-118">Element</span></span>|<span data-ttu-id="cff1e-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cff1e-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cff1e-120">Element „SelectionSet“ (Format)</span><span class="sxs-lookup"><span data-stu-id="cff1e-120">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="cff1e-121">Definiert einen Satz von .NET-Objekten, auf die durch den Namen des Satzes verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="cff1e-121">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cff1e-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cff1e-122">Remarks</span></span>

<span data-ttu-id="cff1e-123">Die von diesem Element definierten Objekte bilden einen Auswahl Satz, der von einer Ansicht, durch eine Definition einer Ansicht (Sichten können mehrere Definitionen aufweisen) oder durch Angeben einer Auswahlbedingung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cff1e-123">The objects defined by this element make up a selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span>  <span data-ttu-id="cff1e-124">Weitere Informationen zu Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="cff1e-124">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="cff1e-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cff1e-125">Example</span></span>

<span data-ttu-id="cff1e-126">Dieses Beispiel zeigt ein- `SelectionSet` Element, das vier .NET-Typen definiert.</span><span class="sxs-lookup"><span data-stu-id="cff1e-126">This example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cff1e-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cff1e-127">See Also</span></span>

[<span data-ttu-id="cff1e-128">Definieren von Objekt Sätzen</span><span class="sxs-lookup"><span data-stu-id="cff1e-128">Defining Sets of Objects</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="cff1e-129">Element „SelectionSet“ (Format)</span><span class="sxs-lookup"><span data-stu-id="cff1e-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="cff1e-130">Typname-Element von Typen (Format)</span><span class="sxs-lookup"><span data-stu-id="cff1e-130">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)

[<span data-ttu-id="cff1e-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="cff1e-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
