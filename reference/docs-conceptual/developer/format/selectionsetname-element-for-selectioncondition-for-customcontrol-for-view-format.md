---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für SelectionCondition für CustomControl für View (Format)
description: Element „SelectionSetName“ für SelectionCondition für CustomControl für View (Format)
ms.openlocfilehash: 839032048739e529057d7066fb3bc6aa2fbc5037
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651611"
---
# <a name="selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="e3b5d-103">Element „SelectionSetName“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3b5d-103">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="e3b5d-104">Gibt den Satz von .NET-Typen an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="e3b5d-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="e3b5d-105">Wenn einer der Typen in diesem Satz vorhanden ist, wird die Bedingung erfüllt, und das Objekt wird mithilfe dieses Steuer Elements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3b5d-105">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="e3b5d-106">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3b5d-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="e3b5d-107">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) entryselectedby-Element für customentry for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3b5d-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e3b5d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3b5d-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e3b5d-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e3b5d-109">Attributes and Elements</span></span>

<span data-ttu-id="e3b5d-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e3b5d-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e3b5d-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e3b5d-111">Attributes</span></span>

<span data-ttu-id="e3b5d-112">Keine</span><span class="sxs-lookup"><span data-stu-id="e3b5d-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e3b5d-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e3b5d-113">Child Elements</span></span>

<span data-ttu-id="e3b5d-114">Keine</span><span class="sxs-lookup"><span data-stu-id="e3b5d-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e3b5d-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e3b5d-115">Parent Elements</span></span>

|<span data-ttu-id="e3b5d-116">Element</span><span class="sxs-lookup"><span data-stu-id="e3b5d-116">Element</span></span>|<span data-ttu-id="e3b5d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3b5d-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3b5d-118">Selectioncondition-Element für entryselectedby für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3b5d-118">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="e3b5d-119">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="e3b5d-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e3b5d-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="e3b5d-120">Text Value</span></span>

<span data-ttu-id="e3b5d-121">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="e3b5d-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3b5d-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e3b5d-122">Remarks</span></span>

<span data-ttu-id="e3b5d-123">Auswahl Sätze sind allgemeine Gruppen von .NET-Objekten, die von jeder Sicht verwendet werden können, die von der Formatierungs Datei definiert wird.</span><span class="sxs-lookup"><span data-stu-id="e3b5d-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="e3b5d-124">Weitere Informationen zum Erstellen und referenzieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="e3b5d-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="e3b5d-125">Die Auswahlbedingung kann einen Auswahl Satz oder einen .NET-Typ angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="e3b5d-125">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="e3b5d-126">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="e3b5d-126">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e3b5d-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3b5d-127">See Also</span></span>

[<span data-ttu-id="e3b5d-128">Selectioncondition-Element für entryselectedby für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e3b5d-128">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="e3b5d-129">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="e3b5d-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="e3b5d-130">Definieren von Auswahlgruppen</span><span class="sxs-lookup"><span data-stu-id="e3b5d-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="e3b5d-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e3b5d-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
