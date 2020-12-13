---
ms.date: 09/13/2016
ms.topic: reference
title: Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)
description: Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)
ms.openlocfilehash: 5af4abe081ca268699d281a1b586a584107b9a83
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652357"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a><span data-ttu-id="c74fc-103">Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="c74fc-103">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="c74fc-104">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="c74fc-104">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="c74fc-105">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c74fc-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="c74fc-106">Configuration-Element (Format) viewdefinitions-Element (Format) View Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) entryselectedby-Element für customentry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="c74fc-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c74fc-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c74fc-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c74fc-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c74fc-108">Attributes and Elements</span></span>

<span data-ttu-id="c74fc-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c74fc-109">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="c74fc-110">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für eine Definition angeben.</span><span class="sxs-lookup"><span data-stu-id="c74fc-110">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="c74fc-111">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c74fc-111">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="c74fc-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c74fc-112">Attributes</span></span>

<span data-ttu-id="c74fc-113">Keine</span><span class="sxs-lookup"><span data-stu-id="c74fc-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c74fc-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c74fc-114">Child Elements</span></span>

|<span data-ttu-id="c74fc-115">Element</span><span class="sxs-lookup"><span data-stu-id="c74fc-115">Element</span></span>|<span data-ttu-id="c74fc-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c74fc-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c74fc-117">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="c74fc-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="c74fc-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="c74fc-118">Optional element.</span></span><br /><br /> <span data-ttu-id="c74fc-119">Definiert die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="c74fc-119">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="c74fc-120">Element „SelectionSetName“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="c74fc-120">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="c74fc-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="c74fc-121">Optional element.</span></span><br /><br /> <span data-ttu-id="c74fc-122">Gibt einen Satz von .NET-Typen an, die diese Definition des-Steuer Elements verwenden.</span><span class="sxs-lookup"><span data-stu-id="c74fc-122">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="c74fc-123">Element „TypeName“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="c74fc-123">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="c74fc-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="c74fc-124">Optional element.</span></span><br /><br /> <span data-ttu-id="c74fc-125">Gibt einen .NET-Typ an, der diese Definition des-Steuer Elements verwendet.</span><span class="sxs-lookup"><span data-stu-id="c74fc-125">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c74fc-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c74fc-126">Parent Elements</span></span>

|<span data-ttu-id="c74fc-127">Element</span><span class="sxs-lookup"><span data-stu-id="c74fc-127">Element</span></span>|<span data-ttu-id="c74fc-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c74fc-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c74fc-129">Element „CustomEntry“ für CustomControl für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="c74fc-129">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="c74fc-130">Stellt eine Definition des-Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="c74fc-130">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c74fc-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c74fc-131">Remarks</span></span>

<span data-ttu-id="c74fc-132">Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für die zu verwendende Definition vorhanden sein muss, z. b. Wenn ein Objekt eine bestimmte Eigenschaft hat oder wenn ein bestimmter Eigenschafts Wert oder ein Skript als ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="c74fc-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="c74fc-133">Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Verwendung eines Ansichts Eintrags oder eines Elements](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="c74fc-133">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c74fc-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c74fc-134">See Also</span></span>

[<span data-ttu-id="c74fc-135">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="c74fc-135">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="c74fc-136">Element „SelectionSetName“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="c74fc-136">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="c74fc-137">Element „TypeName“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="c74fc-137">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="c74fc-138">Element „CustomEntry“ für CustomEntries für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="c74fc-138">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="c74fc-139">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="c74fc-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
