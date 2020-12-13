---
ms.date: 09/13/2016
ms.topic: reference
title: Element „EntrySelectedBy“ für EnumerableExpansion (Format)
description: Element „EntrySelectedBy“ für EnumerableExpansion (Format)
ms.openlocfilehash: 8b2fff2d0b14d0622d0be2c5af3a95194c733a73
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652318"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a><span data-ttu-id="5145c-103">Element „EntrySelectedBy“ für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="5145c-103">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="5145c-104">Definiert die .NET-Typen, die diese Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="5145c-104">Defines the .NET types that use this definition or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="5145c-105">Configuration-Element (Format) DefaultSettings-Element (Format) enumerableerweiterungen-Element (Format) enumerableweiterung-Element (Format) entryselectedby-Element für enumerableweiterung (Format)</span><span class="sxs-lookup"><span data-stu-id="5145c-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5145c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5145c-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5145c-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5145c-107">Attributes and Elements</span></span>

<span data-ttu-id="5145c-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5145c-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5145c-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="5145c-109">Attributes</span></span>

<span data-ttu-id="5145c-110">Keine</span><span class="sxs-lookup"><span data-stu-id="5145c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5145c-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5145c-111">Child Elements</span></span>

|<span data-ttu-id="5145c-112">Element</span><span class="sxs-lookup"><span data-stu-id="5145c-112">Element</span></span>|<span data-ttu-id="5145c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5145c-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5145c-114">Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="5145c-114">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="5145c-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="5145c-115">Optional element.</span></span><br /><br /> <span data-ttu-id="5145c-116">Definiert die Bedingung, die vorhanden sein muss, um die Auflistungs Objekte dieser Definition zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="5145c-116">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|
|[<span data-ttu-id="5145c-117">Element „SelectionSetName“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="5145c-117">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="5145c-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="5145c-118">Optional element.</span></span><br /><br /> <span data-ttu-id="5145c-119">Gibt eine Gruppe von .NET-Typen an, die diese Definition der Erweiterung von Auflistungs Objekten verwenden.</span><span class="sxs-lookup"><span data-stu-id="5145c-119">Specifies a set of .NET types that use this definition of how collection objects are expanded.</span></span>|
|[<span data-ttu-id="5145c-120">Element „TypeName“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="5145c-120">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="5145c-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="5145c-121">Optional element.</span></span><br /><br /> <span data-ttu-id="5145c-122">Gibt einen .NET-Typ an, der diese Definition der Erweiterung von Auflistungs Objekten verwendet.</span><span class="sxs-lookup"><span data-stu-id="5145c-122">Specifies a .NET type that uses this definition of how collection objects are expanded.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5145c-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5145c-123">Parent Elements</span></span>

|<span data-ttu-id="5145c-124">Element</span><span class="sxs-lookup"><span data-stu-id="5145c-124">Element</span></span>|<span data-ttu-id="5145c-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5145c-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5145c-126">Element „EnumerableExpansion“ (Format)</span><span class="sxs-lookup"><span data-stu-id="5145c-126">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="5145c-127">Definiert, wie bestimmte .net-Auflistungs Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5145c-127">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5145c-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5145c-128">Remarks</span></span>

<span data-ttu-id="5145c-129">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für einen Definitions Eintrag angeben.</span><span class="sxs-lookup"><span data-stu-id="5145c-129">You must specify at least one type, selection set, or selection condition for a definition entry.</span></span> <span data-ttu-id="5145c-130">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5145c-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="5145c-131">Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für die zu verwendende Definition vorhanden sein muss, z. b. Wenn ein Objekt über eine bestimmte Eigenschaft verfügt oder ein bestimmter Eigenschafts Wert oder ein bestimmtes Skript als ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="5145c-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="5145c-132">Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="5145c-132">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5145c-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5145c-133">See Also</span></span>

[<span data-ttu-id="5145c-134">Definieren von Bedingungen für die Datenanzeige</span><span class="sxs-lookup"><span data-stu-id="5145c-134">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="5145c-135">Element „EnumerableExpansion“ (Format)</span><span class="sxs-lookup"><span data-stu-id="5145c-135">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)

[<span data-ttu-id="5145c-136">Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="5145c-136">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="5145c-137">Element „SelectionSetName“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="5145c-137">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="5145c-138">Element „TypeName“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="5145c-138">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="5145c-139">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="5145c-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
