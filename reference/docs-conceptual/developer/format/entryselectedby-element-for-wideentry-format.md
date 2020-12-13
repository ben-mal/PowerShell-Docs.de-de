---
ms.date: 09/13/2016
ms.topic: reference
title: Element „EntrySelectedBy“ für WideEntry (Format)
description: Element „EntrySelectedBy“ für WideEntry (Format)
ms.openlocfilehash: 246a1967300ab0551f376c4799deac275068308c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660254"
---
# <a name="entryselectedby-element-for-wideentry-format"></a><span data-ttu-id="bc839-103">Element „EntrySelectedBy“ für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="bc839-103">EntrySelectedBy Element for WideEntry (Format)</span></span>

<span data-ttu-id="bc839-104">Definiert die .NET-Typen, die diese Definition der breiten Ansicht verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="bc839-104">Defines the .NET types that use this definition of the wide view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="bc839-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="bc839-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bc839-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc839-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bc839-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bc839-107">Attributes and Elements</span></span>

<span data-ttu-id="bc839-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc839-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bc839-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="bc839-109">Attributes</span></span>

<span data-ttu-id="bc839-110">Keine</span><span class="sxs-lookup"><span data-stu-id="bc839-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bc839-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bc839-111">Child Elements</span></span>

|<span data-ttu-id="bc839-112">Element</span><span class="sxs-lookup"><span data-stu-id="bc839-112">Element</span></span>|<span data-ttu-id="bc839-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc839-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bc839-114">Selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="bc839-114">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="bc839-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="bc839-115">Optional element.</span></span><br /><br /> <span data-ttu-id="bc839-116">Definiert die Bedingung, die vorhanden sein muss, damit diese Breite Sicht Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="bc839-116">Defines the condition that must exist for this wide view definition to be used.</span></span>|
|[<span data-ttu-id="bc839-117">Selectionsetname-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="bc839-117">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="bc839-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="bc839-118">Optional element.</span></span><br /><br /> <span data-ttu-id="bc839-119">Gibt einen Satz von .NET-Typen an, die diese Breite Sicht Definition verwenden.</span><span class="sxs-lookup"><span data-stu-id="bc839-119">Specifies a set of .NET types that use this wide view definition.</span></span>|
|[<span data-ttu-id="bc839-120">Element „TypeName“ für EntrySelectedBy für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="bc839-120">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="bc839-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="bc839-121">Optional element.</span></span><br /><br /> <span data-ttu-id="bc839-122">Gibt einen .NET-Typ an, der diese Breite Sicht Definition verwendet.</span><span class="sxs-lookup"><span data-stu-id="bc839-122">Specifies a .NET type that uses this wide view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bc839-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bc839-123">Parent Elements</span></span>

|<span data-ttu-id="bc839-124">Element</span><span class="sxs-lookup"><span data-stu-id="bc839-124">Element</span></span>|<span data-ttu-id="bc839-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc839-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bc839-126">Wideentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="bc839-126">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="bc839-127">Stellt eine Definition der breiten Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="bc839-127">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bc839-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bc839-128">Remarks</span></span>

<span data-ttu-id="bc839-129">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für eine breite Sicht Definition angeben.</span><span class="sxs-lookup"><span data-stu-id="bc839-129">You must specify at least one type, selection set, or selection condition for a wide view definition.</span></span> <span data-ttu-id="bc839-130">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="bc839-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="bc839-131">Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für die zu verwendende Definition vorhanden sein muss, z. b. Wenn ein Objekt über eine bestimmte Eigenschaft verfügt oder für einen bestimmten Eigenschafts Wert oder Skript Wert ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="bc839-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script value evaluates to `true`.</span></span> <span data-ttu-id="bc839-132">Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="bc839-132">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="bc839-133">Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="bc839-133">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bc839-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc839-134">See Also</span></span>

[<span data-ttu-id="bc839-135">Wideentry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="bc839-135">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="bc839-136">Selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="bc839-136">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="bc839-137">Selectionsetname-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="bc839-137">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="bc839-138">Element „TypeName“ für EntrySelectedBy für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="bc839-138">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="bc839-139">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="bc839-139">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="bc839-140">Definieren von Bedingungen für die Datenanzeige</span><span class="sxs-lookup"><span data-stu-id="bc839-140">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="bc839-141">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="bc839-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
