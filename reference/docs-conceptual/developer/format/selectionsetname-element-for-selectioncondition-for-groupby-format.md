---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für SelectionCondition für GroupBy (Format)
description: Element „SelectionSetName“ für SelectionCondition für GroupBy (Format)
ms.openlocfilehash: a4f28c1caba3790718b99f63659cb0cbed8def16
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654993"
---
# <a name="selectionsetname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="92b06-103">Element „SelectionSetName“ für SelectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="92b06-103">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="92b06-104">Gibt den Satz von .NET-Typen an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="92b06-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="92b06-105">Wenn einer der Typen in diesem Satz vorhanden ist, wird die Bedingung erfüllt, und das Objekt wird mithilfe dieses Steuer Elements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="92b06-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="92b06-106">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="92b06-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="92b06-107">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) entryselectedby-Element für customentry für GroupBy (Format) selectioncondition-Element für entryselectedby für GroupBy (Format) selectionsetname-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="92b06-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92b06-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="92b06-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92b06-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="92b06-109">Attributes and Elements</span></span>

<span data-ttu-id="92b06-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="92b06-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92b06-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="92b06-111">Attributes</span></span>

<span data-ttu-id="92b06-112">Keine</span><span class="sxs-lookup"><span data-stu-id="92b06-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92b06-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="92b06-113">Child Elements</span></span>

<span data-ttu-id="92b06-114">Keine</span><span class="sxs-lookup"><span data-stu-id="92b06-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="92b06-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="92b06-115">Parent Elements</span></span>

|<span data-ttu-id="92b06-116">Element</span><span class="sxs-lookup"><span data-stu-id="92b06-116">Element</span></span>|<span data-ttu-id="92b06-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92b06-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92b06-118">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="92b06-118">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="92b06-119">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="92b06-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="92b06-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="92b06-120">Text Value</span></span>

<span data-ttu-id="92b06-121">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="92b06-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="92b06-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="92b06-122">Remarks</span></span>

<span data-ttu-id="92b06-123">Auswahl Sätze sind allgemeine Gruppen von .NET-Objekten, die von jeder Sicht verwendet werden können, die von der Formatierungs Datei definiert wird.</span><span class="sxs-lookup"><span data-stu-id="92b06-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="92b06-124">Weitere Informationen zum Erstellen und referenzieren von Auswahl Sätzen finden Sie unter [Definieren von Auswahl Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="92b06-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="92b06-125">Wenn dieses Element angegeben ist, können Sie das [tygtame](./typename-element-for-selectioncondition-for-groupby-format.md) -Element nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="92b06-125">When this element is specified, you cannot specify the [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) element.</span></span> <span data-ttu-id="92b06-126">Weitere Informationen zum Definieren von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="92b06-126">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92b06-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92b06-127">See Also</span></span>

[<span data-ttu-id="92b06-128">Element „TypeName“ für SelectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="92b06-128">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="92b06-129">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="92b06-129">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="92b06-130">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="92b06-130">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="92b06-131">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="92b06-131">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="92b06-132">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="92b06-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
