---
ms.date: 09/13/2016
ms.topic: reference
title: Element „EntrySelectedBy“ für ListEntry für ListControl (Format)
description: Element „EntrySelectedBy“ für ListEntry für ListControl (Format)
ms.openlocfilehash: 1981c8fae65f494504d6cdd9f59337d555350b07
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652283"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="ea706-103">Element „EntrySelectedBy“ für ListEntry für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea706-103">EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="ea706-104">Definiert die .NET-Typen, die diese Listen Ansichts Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="ea706-104">Defines the .NET types that use this list view definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="ea706-105">In den meisten Fällen ist nur eine Definition für eine Listenansicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ea706-105">In most cases only one definition is needed for a list view.</span></span> <span data-ttu-id="ea706-106">Sie können jedoch mehrere Definitionen für die Listenansicht bereitstellen, wenn Sie die gleiche Listenansicht verwenden möchten, um unterschiedliche Daten für unterschiedliche Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ea706-106">However, you can provide multiple definitions for the list view if you want to use the same list view to display different data for different objects.</span></span>

<span data-ttu-id="ea706-107">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListEntry für ListControl (Format) entryselectedby-Element für ListEntry für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea706-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntry for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ea706-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea706-108">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ea706-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ea706-109">Attributes and Elements</span></span>

<span data-ttu-id="ea706-110">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ea706-110">The following sections describe the attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ea706-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ea706-111">Attributes</span></span>

<span data-ttu-id="ea706-112">Keine</span><span class="sxs-lookup"><span data-stu-id="ea706-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ea706-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ea706-113">Child Elements</span></span>

|<span data-ttu-id="ea706-114">Element</span><span class="sxs-lookup"><span data-stu-id="ea706-114">Element</span></span>|<span data-ttu-id="ea706-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea706-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ea706-116">Selectioncondition-Element für entryselectedby für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea706-116">SelectionCondition Element for EntrySelectedBy for ListControl  (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="ea706-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ea706-117">Optional element.</span></span><br /><br /> <span data-ttu-id="ea706-118">Definiert die Bedingung, die für die Verwendung dieser Listen Ansichts Definition vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="ea706-118">Defines the condition that must exist for this list view definition to be used.</span></span>|
|[<span data-ttu-id="ea706-119">Element „SelectionSetName“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea706-119">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="ea706-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ea706-120">Optional element.</span></span><br /><br /> <span data-ttu-id="ea706-121">Gibt eine Gruppe von .NET-Typen an, die diese Listen Ansichts Definition verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea706-121">Specifies a set of .NET types that use this list view definition.</span></span>|
|[<span data-ttu-id="ea706-122">Element „TypeName“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea706-122">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="ea706-123">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ea706-123">Optional element.</span></span><br /><br /> <span data-ttu-id="ea706-124">Gibt einen .NET-Typ an, der diese Listen Ansichts Definition verwendet.</span><span class="sxs-lookup"><span data-stu-id="ea706-124">Specifies a .NET type that uses this list view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ea706-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ea706-125">Parent Elements</span></span>

|<span data-ttu-id="ea706-126">Element</span><span class="sxs-lookup"><span data-stu-id="ea706-126">Element</span></span>|<span data-ttu-id="ea706-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea706-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ea706-128">Element „ListEntry“ für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea706-128">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="ea706-129">Definiert, wie die Zeilen der Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ea706-129">Defines how the rows of the list are displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ea706-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ea706-130">Remarks</span></span>

<span data-ttu-id="ea706-131">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für eine Listen Ansichts Definition angeben.</span><span class="sxs-lookup"><span data-stu-id="ea706-131">You must specify at least one type, selection set, or selection condition for a list view definition.</span></span> <span data-ttu-id="ea706-132">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ea706-132">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="ea706-133">Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für die zu verwendende Definition vorhanden sein muss, z. b. Wenn ein Objekt über eine bestimmte Eigenschaft verfügt oder ein bestimmter Eigenschafts Wert oder ein bestimmtes Skript als ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="ea706-133">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="ea706-134">Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für den Fall, dass Daten angezeigt werden](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="ea706-134">For more information about selection conditions, see [Defining Conditions for when Data is displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="ea706-135">Weitere Informationen zu den Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="ea706-135">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ea706-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ea706-136">Example</span></span>

<span data-ttu-id="ea706-137">Im folgenden Beispiel wird gezeigt, wie die-Objekte für eine Listenansicht mithilfe Ihres .net-Typnamens definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ea706-137">The following example shows how to define the objects for a list view using their .NET type name.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="ea706-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea706-138">See Also</span></span>

[<span data-ttu-id="ea706-139">Element „ListEntry“ für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea706-139">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="ea706-140">Element „SelectionCondition“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea706-140">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="ea706-141">Element „SelectionSetName“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea706-141">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="ea706-142">Element „TypeName“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea706-142">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="ea706-143">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="ea706-143">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="ea706-144">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="ea706-144">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="ea706-145">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="ea706-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
