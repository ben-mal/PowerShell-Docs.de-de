---
title: Entryselectedby-Element für ListEntry für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: d6ab1c08dd353da74d1a7d27c569d2fa86e083c3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774115"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="d97a1-102">Element „EntrySelectedBy“ für ListEntry für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d97a1-102">EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="d97a1-103">Definiert die .NET-Typen, die diese Listen Ansichts Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="d97a1-103">Defines the .NET types that use this list view definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="d97a1-104">In den meisten Fällen ist nur eine Definition für eine Listenansicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d97a1-104">In most cases only one definition is needed for a list view.</span></span> <span data-ttu-id="d97a1-105">Sie können jedoch mehrere Definitionen für die Listenansicht bereitstellen, wenn Sie die gleiche Listenansicht verwenden möchten, um unterschiedliche Daten für unterschiedliche Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d97a1-105">However, you can provide multiple definitions for the list view if you want to use the same list view to display different data for different objects.</span></span>

<span data-ttu-id="d97a1-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListEntry für ListControl (Format) entryselectedby-Element für ListEntry für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d97a1-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntry for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d97a1-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d97a1-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d97a1-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d97a1-108">Attributes and Elements</span></span>

<span data-ttu-id="d97a1-109">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d97a1-109">The following sections describe the attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d97a1-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="d97a1-110">Attributes</span></span>

<span data-ttu-id="d97a1-111">Keine</span><span class="sxs-lookup"><span data-stu-id="d97a1-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d97a1-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d97a1-112">Child Elements</span></span>

|<span data-ttu-id="d97a1-113">Element</span><span class="sxs-lookup"><span data-stu-id="d97a1-113">Element</span></span>|<span data-ttu-id="d97a1-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d97a1-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d97a1-115">Selectioncondition-Element für entryselectedby für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d97a1-115">SelectionCondition Element for EntrySelectedBy for ListControl  (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="d97a1-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d97a1-116">Optional element.</span></span><br /><br /> <span data-ttu-id="d97a1-117">Definiert die Bedingung, die für die Verwendung dieser Listen Ansichts Definition vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="d97a1-117">Defines the condition that must exist for this list view definition to be used.</span></span>|
|[<span data-ttu-id="d97a1-118">Element „SelectionSetName“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d97a1-118">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="d97a1-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d97a1-119">Optional element.</span></span><br /><br /> <span data-ttu-id="d97a1-120">Gibt eine Gruppe von .NET-Typen an, die diese Listen Ansichts Definition verwenden.</span><span class="sxs-lookup"><span data-stu-id="d97a1-120">Specifies a set of .NET types that use this list view definition.</span></span>|
|[<span data-ttu-id="d97a1-121">Element „TypeName“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d97a1-121">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="d97a1-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="d97a1-122">Optional element.</span></span><br /><br /> <span data-ttu-id="d97a1-123">Gibt einen .NET-Typ an, der diese Listen Ansichts Definition verwendet.</span><span class="sxs-lookup"><span data-stu-id="d97a1-123">Specifies a .NET type that uses this list view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d97a1-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d97a1-124">Parent Elements</span></span>

|<span data-ttu-id="d97a1-125">Element</span><span class="sxs-lookup"><span data-stu-id="d97a1-125">Element</span></span>|<span data-ttu-id="d97a1-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d97a1-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d97a1-127">Element „ListEntry“ für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d97a1-127">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="d97a1-128">Definiert, wie die Zeilen der Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d97a1-128">Defines how the rows of the list are displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d97a1-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d97a1-129">Remarks</span></span>

<span data-ttu-id="d97a1-130">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für eine Listen Ansichts Definition angeben.</span><span class="sxs-lookup"><span data-stu-id="d97a1-130">You must specify at least one type, selection set, or selection condition for a list view definition.</span></span> <span data-ttu-id="d97a1-131">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d97a1-131">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="d97a1-132">Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für die zu verwendende Definition vorhanden sein muss, z. b. Wenn ein Objekt über eine bestimmte Eigenschaft verfügt oder ein bestimmter Eigenschafts Wert oder ein bestimmtes Skript als ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="d97a1-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="d97a1-133">Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für den Fall, dass Daten angezeigt werden](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="d97a1-133">For more information about selection conditions, see [Defining Conditions for when Data is displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d97a1-134">Weitere Informationen zu den Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="d97a1-134">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="d97a1-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d97a1-135">Example</span></span>

<span data-ttu-id="d97a1-136">Im folgenden Beispiel wird gezeigt, wie die-Objekte für eine Listenansicht mithilfe Ihres .net-Typnamens definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d97a1-136">The following example shows how to define the objects for a list view using their .NET type name.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="d97a1-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d97a1-137">See Also</span></span>

[<span data-ttu-id="d97a1-138">Element „ListEntry“ für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d97a1-138">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="d97a1-139">Element „SelectionCondition“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d97a1-139">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="d97a1-140">Element „SelectionSetName“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d97a1-140">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="d97a1-141">Element „TypeName“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d97a1-141">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="d97a1-142">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="d97a1-142">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="d97a1-143">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="d97a1-143">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d97a1-144">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="d97a1-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
