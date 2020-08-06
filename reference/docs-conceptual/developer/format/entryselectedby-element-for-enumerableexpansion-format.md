---
title: Entryselectedby-Element für enumerableexpansion (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 031bf10cfb1aed2c737fdd53fa4f20f025351d40
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783669"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a><span data-ttu-id="0cdda-102">Element „EntrySelectedBy“ für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="0cdda-102">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="0cdda-103">Definiert die .NET-Typen, die diese Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="0cdda-103">Defines the .NET types that use this definition or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="0cdda-104">Configuration-Element (Format) DefaultSettings-Element (Format) enumerableerweiterungen-Element (Format) enumerableweiterung-Element (Format) entryselectedby-Element für enumerableweiterung (Format)</span><span class="sxs-lookup"><span data-stu-id="0cdda-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0cdda-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0cdda-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0cdda-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0cdda-106">Attributes and Elements</span></span>

<span data-ttu-id="0cdda-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0cdda-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0cdda-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="0cdda-108">Attributes</span></span>

<span data-ttu-id="0cdda-109">Keine</span><span class="sxs-lookup"><span data-stu-id="0cdda-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0cdda-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0cdda-110">Child Elements</span></span>

|<span data-ttu-id="0cdda-111">Element</span><span class="sxs-lookup"><span data-stu-id="0cdda-111">Element</span></span>|<span data-ttu-id="0cdda-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0cdda-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0cdda-113">Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="0cdda-113">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="0cdda-114">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="0cdda-114">Optional element.</span></span><br /><br /> <span data-ttu-id="0cdda-115">Definiert die Bedingung, die vorhanden sein muss, um die Auflistungs Objekte dieser Definition zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="0cdda-115">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|
|[<span data-ttu-id="0cdda-116">Element „SelectionSetName“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="0cdda-116">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="0cdda-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="0cdda-117">Optional element.</span></span><br /><br /> <span data-ttu-id="0cdda-118">Gibt eine Gruppe von .NET-Typen an, die diese Definition der Erweiterung von Auflistungs Objekten verwenden.</span><span class="sxs-lookup"><span data-stu-id="0cdda-118">Specifies a set of .NET types that use this definition of how collection objects are expanded.</span></span>|
|[<span data-ttu-id="0cdda-119">Element „TypeName“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="0cdda-119">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="0cdda-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="0cdda-120">Optional element.</span></span><br /><br /> <span data-ttu-id="0cdda-121">Gibt einen .NET-Typ an, der diese Definition der Erweiterung von Auflistungs Objekten verwendet.</span><span class="sxs-lookup"><span data-stu-id="0cdda-121">Specifies a .NET type that uses this definition of how collection objects are expanded.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0cdda-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0cdda-122">Parent Elements</span></span>

|<span data-ttu-id="0cdda-123">Element</span><span class="sxs-lookup"><span data-stu-id="0cdda-123">Element</span></span>|<span data-ttu-id="0cdda-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0cdda-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0cdda-125">Element „EnumerableExpansion“ (Format)</span><span class="sxs-lookup"><span data-stu-id="0cdda-125">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="0cdda-126">Definiert, wie bestimmte .net-Auflistungs Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0cdda-126">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0cdda-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0cdda-127">Remarks</span></span>

<span data-ttu-id="0cdda-128">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für einen Definitions Eintrag angeben.</span><span class="sxs-lookup"><span data-stu-id="0cdda-128">You must specify at least one type, selection set, or selection condition for a definition entry.</span></span> <span data-ttu-id="0cdda-129">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0cdda-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="0cdda-130">Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für die zu verwendende Definition vorhanden sein muss, z. b. Wenn ein Objekt über eine bestimmte Eigenschaft verfügt oder ein bestimmter Eigenschafts Wert oder ein bestimmtes Skript als ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="0cdda-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="0cdda-131">Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="0cdda-131">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0cdda-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0cdda-132">See Also</span></span>

[<span data-ttu-id="0cdda-133">Definieren von Bedingungen für die Datenanzeige</span><span class="sxs-lookup"><span data-stu-id="0cdda-133">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="0cdda-134">Element „EnumerableExpansion“ (Format)</span><span class="sxs-lookup"><span data-stu-id="0cdda-134">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)

[<span data-ttu-id="0cdda-135">Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="0cdda-135">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="0cdda-136">Element „SelectionSetName“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="0cdda-136">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="0cdda-137">Element „TypeName“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="0cdda-137">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="0cdda-138">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="0cdda-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
