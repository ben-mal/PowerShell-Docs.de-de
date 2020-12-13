---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für EntrySelectedBy für EnumerableExpansion (Format)
description: Element „SelectionSetName“ für EntrySelectedBy für EnumerableExpansion (Format)
ms.openlocfilehash: 074f810f5a3cbad61ee8be69408967758f0591df
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651877"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="c1189-103">Element „SelectionSetName“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="c1189-103">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="c1189-104">Gibt den Satz von .NET-Typen an, die durch diese Definition erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="c1189-104">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="c1189-105">Configuration-Element (Format) DefaultSettings-Element (Format) enumerableerweiterungen-Element (Format) enumerableweiterung-Element (Format) entryselectedby-Element für enumerableexpansion (Format) selectionsetname-Element für entryselectedby für enumerableexpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="c1189-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c1189-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1189-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="c1189-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1189-107">Attributes and Elements</span></span>

<span data-ttu-id="c1189-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1189-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c1189-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="c1189-109">Attributes</span></span>

<span data-ttu-id="c1189-110">Keine</span><span class="sxs-lookup"><span data-stu-id="c1189-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c1189-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1189-111">Child Elements</span></span>

<span data-ttu-id="c1189-112">Keine</span><span class="sxs-lookup"><span data-stu-id="c1189-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c1189-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1189-113">Parent Elements</span></span>

|<span data-ttu-id="c1189-114">Element</span><span class="sxs-lookup"><span data-stu-id="c1189-114">Element</span></span>|<span data-ttu-id="c1189-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1189-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c1189-116">Element „EntrySelectedBy“ für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="c1189-116">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="c1189-117">Definiert die .net-Auflistungs Objekte, die durch diese Definition erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="c1189-117">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c1189-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="c1189-118">Text Value</span></span>

<span data-ttu-id="c1189-119">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="c1189-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1189-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c1189-120">Remarks</span></span>

<span data-ttu-id="c1189-121">Jede Definition muss einen oder mehrere Typnamen, einen Auswahl Satz oder eine Auswahlbedingung angeben.</span><span class="sxs-lookup"><span data-stu-id="c1189-121">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="c1189-122">Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c1189-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="c1189-123">Beispielsweise können Sie eine Tabellenansicht und eine Listenansicht für denselben Satz von Objekten erstellen.</span><span class="sxs-lookup"><span data-stu-id="c1189-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="c1189-124">Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen für eine Sicht](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="c1189-124">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c1189-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1189-125">See Also</span></span>

[<span data-ttu-id="c1189-126">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="c1189-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="c1189-127">Element „EntrySelectedBy“ für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="c1189-127">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="c1189-128">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="c1189-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
