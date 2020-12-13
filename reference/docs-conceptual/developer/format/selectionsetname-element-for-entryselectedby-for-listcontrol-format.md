---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionSetName“ für EntrySelectedBy für ListControl (Format)
description: Element „SelectionSetName“ für EntrySelectedBy für ListControl (Format)
ms.openlocfilehash: 413a77f7ba06fe952e574061e58d0b5d80c5b3c4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651832"
---
# <a name="selectionsetname-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="45640-103">Element „SelectionSetName“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="45640-103">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="45640-104">Gibt eine Gruppe von .NET-Objekten für den Listeneintrag an.</span><span class="sxs-lookup"><span data-stu-id="45640-104">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="45640-105">Es gibt keine Beschränkung für die Anzahl der Auswahl Sätze, die für einen Eintrag angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="45640-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="45640-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) entryselectedby-Element für ListEntry (Format) selectionsetname-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="45640-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="45640-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="45640-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="45640-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="45640-108">Attributes and Elements</span></span>

<span data-ttu-id="45640-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="45640-109">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="45640-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="45640-110">Attributes</span></span>

<span data-ttu-id="45640-111">Keine</span><span class="sxs-lookup"><span data-stu-id="45640-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="45640-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="45640-112">Child Elements</span></span>

<span data-ttu-id="45640-113">Keine</span><span class="sxs-lookup"><span data-stu-id="45640-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="45640-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="45640-114">Parent Elements</span></span>

|<span data-ttu-id="45640-115">Element</span><span class="sxs-lookup"><span data-stu-id="45640-115">Element</span></span>|<span data-ttu-id="45640-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45640-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45640-117">Entryselectedby-Element für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="45640-117">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="45640-118">Definiert die .NET-Typen, die diesen Listeneintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="45640-118">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="45640-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="45640-119">Text Value</span></span>

<span data-ttu-id="45640-120">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="45640-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="45640-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="45640-121">Remarks</span></span>

<span data-ttu-id="45640-122">Für jeden Listeneintrag muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.</span><span class="sxs-lookup"><span data-stu-id="45640-122">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="45640-123">Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="45640-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="45640-124">Beispielsweise können Sie eine Tabellenansicht und eine Listenansicht für denselben Satz von Objekten erstellen.</span><span class="sxs-lookup"><span data-stu-id="45640-124">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="45640-125">Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen für eine Sicht](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="45640-125">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="45640-126">Weitere Informationen zu den Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="45640-126">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="45640-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="45640-127">Example</span></span>

<span data-ttu-id="45640-128">Im folgenden Beispiel wird gezeigt, wie Sie einen Auswahl Satz für einen Eintrag einer Listenansicht angeben.</span><span class="sxs-lookup"><span data-stu-id="45640-128">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="45640-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45640-129">See Also</span></span>

[<span data-ttu-id="45640-130">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="45640-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="45640-131">Entryselectedby-Element für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="45640-131">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="45640-132">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="45640-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
