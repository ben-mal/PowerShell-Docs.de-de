---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)
description: Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)
ms.openlocfilehash: 0c9372113a79f75cfbda67acf869164fde894ee3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651594"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="a119a-103">Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="a119a-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="a119a-104">Gibt den Satz von .NET-Typen an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="a119a-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="a119a-105">Wenn einer der Typen in diesem Satz vorhanden ist, wird die Bedingung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="a119a-105">When any of the types in this set are present, the condition is met.</span></span>

<span data-ttu-id="a119a-106">Configuration-Element DefaultSettings-Element (Format) enumerableweiterung-Element (Format) enumerableerweiterungen-Element (Format) entryselectedby-Element für enumerableexpansion (Format) selectioncondition-Element für entryselectedby für enumerableweiterung (Format) selectionsetname-Element für selectioncondition für entryselectedby für enumerableexpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="a119a-106">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a119a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a119a-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a119a-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a119a-108">Attributes and Elements</span></span>

<span data-ttu-id="a119a-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a119a-109">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a119a-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a119a-110">Attributes</span></span>

<span data-ttu-id="a119a-111">Keine</span><span class="sxs-lookup"><span data-stu-id="a119a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a119a-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a119a-112">Child Elements</span></span>

<span data-ttu-id="a119a-113">Keine</span><span class="sxs-lookup"><span data-stu-id="a119a-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a119a-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a119a-114">Parent Elements</span></span>

|<span data-ttu-id="a119a-115">Element</span><span class="sxs-lookup"><span data-stu-id="a119a-115">Element</span></span>|<span data-ttu-id="a119a-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a119a-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a119a-117">Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="a119a-117">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="a119a-118">Definiert die Bedingung, die vorhanden sein muss, um die Auflistungs Objekte dieser Definition zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a119a-118">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a119a-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="a119a-119">Text Value</span></span>

<span data-ttu-id="a119a-120">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="a119a-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="a119a-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a119a-121">Remarks</span></span>

<span data-ttu-id="a119a-122">Die Auswahlbedingung kann einen Auswahl Satz oder einen .NET-Typ angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="a119a-122">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="a119a-123">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a119a-123">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="a119a-124">Auswahl Sätze sind allgemeine Gruppen von .NET-Objekten, die von jeder Sicht verwendet werden können, die von der Formatierungs Datei definiert wird.</span><span class="sxs-lookup"><span data-stu-id="a119a-124">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="a119a-125">Weitere Informationen zum Erstellen und referenzieren von Auswahl Sätzen finden Sie unter [Definieren von Auswahl Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="a119a-125">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a119a-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a119a-126">See Also</span></span>

[<span data-ttu-id="a119a-127">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="a119a-127">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="a119a-128">Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="a119a-128">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="a119a-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="a119a-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
