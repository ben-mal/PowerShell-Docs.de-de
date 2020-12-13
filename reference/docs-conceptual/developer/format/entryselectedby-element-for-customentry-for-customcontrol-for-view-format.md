---
ms.date: 09/13/2016
ms.topic: reference
title: Element „EntrySelectedBy“ für CustomEntry für CustomControl für View (Format)
description: Element „EntrySelectedBy“ für CustomEntry für CustomControl für View (Format)
ms.openlocfilehash: 4821f22560f35034f90d018e5a109004f331441f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655358"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="abad8-103">Element „EntrySelectedBy“ für CustomEntry für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="abad8-103">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="abad8-104">Definiert die .NET-Typen, die diesen benutzerdefinierten Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="abad8-104">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="abad8-105">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) entryselectedby-Element für customentry for View (Format)</span><span class="sxs-lookup"><span data-stu-id="abad8-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="abad8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="abad8-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="abad8-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="abad8-107">Attributes and Elements</span></span>

<span data-ttu-id="abad8-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="abad8-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="abad8-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="abad8-109">Attributes</span></span>

<span data-ttu-id="abad8-110">Keine</span><span class="sxs-lookup"><span data-stu-id="abad8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="abad8-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="abad8-111">Child Elements</span></span>

|<span data-ttu-id="abad8-112">Element</span><span class="sxs-lookup"><span data-stu-id="abad8-112">Element</span></span>|<span data-ttu-id="abad8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="abad8-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="abad8-114">Selectioncondition-Element für entryselectedby für customentry (Format)</span><span class="sxs-lookup"><span data-stu-id="abad8-114">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="abad8-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="abad8-115">Optional element.</span></span><br /><br /> <span data-ttu-id="abad8-116">Definiert die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="abad8-116">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="abad8-117">Selectionsetname-Element für entryselectedby für customentry (Format)</span><span class="sxs-lookup"><span data-stu-id="abad8-117">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="abad8-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="abad8-118">Optional element.</span></span><br /><br /> <span data-ttu-id="abad8-119">Gibt einen Satz von .NET-Typen an, die diese Definition der Steuerelement Ansicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="abad8-119">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="abad8-120">Typname-Element für entryselectedby für customentry (Format)</span><span class="sxs-lookup"><span data-stu-id="abad8-120">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="abad8-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="abad8-121">Optional element.</span></span><br /><br /> <span data-ttu-id="abad8-122">Gibt einen .NET-Typ an, der diese Definition der Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="abad8-122">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="abad8-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="abad8-123">Parent Elements</span></span>

|<span data-ttu-id="abad8-124">Element</span><span class="sxs-lookup"><span data-stu-id="abad8-124">Element</span></span>|<span data-ttu-id="abad8-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="abad8-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="abad8-126">Customentry-Element für customentries für View (Format)</span><span class="sxs-lookup"><span data-stu-id="abad8-126">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="abad8-127">Definiert die Steuerelemente, die von bestimmten .NET-Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="abad8-127">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="abad8-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="abad8-128">Remarks</span></span>

<span data-ttu-id="abad8-129">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für einen Eintrag angeben.</span><span class="sxs-lookup"><span data-stu-id="abad8-129">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="abad8-130">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="abad8-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="abad8-131">Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für den zu verwendenden Eintrag vorhanden sein muss, z. b. Wenn ein Objekt eine bestimmte Eigenschaft hat oder wenn ein bestimmter Eigenschafts Wert oder ein Skript als ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="abad8-131">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="abad8-132">Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Verwendung eines Ansichts Eintrags oder eines Elements](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="abad8-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="abad8-133">Weitere Informationen zu den Komponenten einer benutzerdefinierten Steuerelement Ansicht finden Sie unter [benutzerdefinierte Steuerelement Ansicht](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="abad8-133">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="abad8-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="abad8-134">See Also</span></span>

[<span data-ttu-id="abad8-135">Selectioncondition-Element für entryselectedby für customentry (Format)</span><span class="sxs-lookup"><span data-stu-id="abad8-135">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="abad8-136">Selectionsetname-Element für entryselectedby für customentry (Format)</span><span class="sxs-lookup"><span data-stu-id="abad8-136">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="abad8-137">Typname-Element für entryselectedby für customentry (Format)</span><span class="sxs-lookup"><span data-stu-id="abad8-137">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="abad8-138">Customentry-Element für customentries für View (Format)</span><span class="sxs-lookup"><span data-stu-id="abad8-138">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="abad8-139">Benutzerdefinierte Steuerelement Ansicht</span><span class="sxs-lookup"><span data-stu-id="abad8-139">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="abad8-140">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="abad8-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
