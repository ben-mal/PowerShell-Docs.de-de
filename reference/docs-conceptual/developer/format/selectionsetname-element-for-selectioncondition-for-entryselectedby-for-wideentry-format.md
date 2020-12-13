---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)
description: Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)
ms.openlocfilehash: c6466e3ac6e1f194df9172468d26448f9630da6a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655006"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="d3559-103">Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="d3559-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="d3559-104">Gibt den Satz von .NET-Typen an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="d3559-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="d3559-105">Wenn einer der Typen in diesem Satz vorhanden ist, wird die Bedingung erfüllt, und das Objekt wird mit dieser Definition der breiten Ansicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3559-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the wide view.</span></span>

<span data-ttu-id="d3559-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format) selectioncondition-Element für entryselectedby für wideentry (Format) selectionsetname-Element für selectioncondition für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="d3559-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d3559-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3559-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d3559-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d3559-108">Attributes and Elements</span></span>

<span data-ttu-id="d3559-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d3559-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d3559-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="d3559-110">Attributes</span></span>

<span data-ttu-id="d3559-111">Keine</span><span class="sxs-lookup"><span data-stu-id="d3559-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d3559-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3559-112">Child Elements</span></span>

<span data-ttu-id="d3559-113">Keine</span><span class="sxs-lookup"><span data-stu-id="d3559-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d3559-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3559-114">Parent Elements</span></span>

|<span data-ttu-id="d3559-115">Element</span><span class="sxs-lookup"><span data-stu-id="d3559-115">Element</span></span>|<span data-ttu-id="d3559-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3559-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d3559-117">Selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="d3559-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="d3559-118">Definiert die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="d3559-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d3559-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="d3559-119">Text Value</span></span>

<span data-ttu-id="d3559-120">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="d3559-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3559-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d3559-121">Remarks</span></span>

<span data-ttu-id="d3559-122">Die Auswahlbedingung kann einen Auswahl Satz oder einen .NET-Typ angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="d3559-122">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="d3559-123">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="d3559-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d3559-124">Auswahl Sätze sind allgemeine Gruppen von .NET-Objekten, die von jeder Sicht verwendet werden können, die von der Formatierungs Datei definiert wird.</span><span class="sxs-lookup"><span data-stu-id="d3559-124">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="d3559-125">Weitere Informationen zum Erstellen und referenzieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="d3559-125">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="d3559-126">Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="d3559-126">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d3559-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3559-127">See Also</span></span>

[<span data-ttu-id="d3559-128">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="d3559-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="d3559-129">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="d3559-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d3559-130">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="d3559-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="d3559-131">Selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="d3559-131">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="d3559-132">Typname-Element für selectioncondition für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="d3559-132">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="d3559-133">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="d3559-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
