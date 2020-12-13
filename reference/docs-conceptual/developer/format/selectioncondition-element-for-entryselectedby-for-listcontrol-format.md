---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionCondition“ für EntrySelectedBy für ListControl (Format)
description: Element „SelectionCondition“ für EntrySelectedBy für ListControl (Format)
ms.openlocfilehash: e93499691dd0046265e43abd26497b2974546083
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655097"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="45c85-103">Element „SelectionCondition“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="45c85-103">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="45c85-104">Definiert die Bedingung, die vorhanden sein muss, um diese Definition der Listenansicht zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="45c85-104">Defines the condition that must exist to use this definition of the list view.</span></span> <span data-ttu-id="45c85-105">Es gibt keine Beschränkung für die Anzahl der Auswahl Bedingungen, die für eine Listen Definition angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="45c85-105">There is no limit to the number of selection conditions that can be specified for a list definition.</span></span>

<span data-ttu-id="45c85-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) entryselectedby-Element für ListEntry (Format) selectioncondition-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="45c85-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="45c85-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="45c85-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="45c85-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="45c85-108">Attributes and Elements</span></span>

<span data-ttu-id="45c85-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="45c85-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="45c85-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="45c85-110">Attributes</span></span>

<span data-ttu-id="45c85-111">Keine</span><span class="sxs-lookup"><span data-stu-id="45c85-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="45c85-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="45c85-112">Child Elements</span></span>

|<span data-ttu-id="45c85-113">Element</span><span class="sxs-lookup"><span data-stu-id="45c85-113">Element</span></span>|<span data-ttu-id="45c85-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45c85-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45c85-115">PropertyName-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="45c85-115">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="45c85-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="45c85-116">Optional element.</span></span><br /><br /> <span data-ttu-id="45c85-117">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="45c85-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="45c85-118">ScriptBlock-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="45c85-118">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="45c85-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="45c85-119">Optional element.</span></span><br /><br /> <span data-ttu-id="45c85-120">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="45c85-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="45c85-121">Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="45c85-121">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|<span data-ttu-id="45c85-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="45c85-122">Optional element.</span></span><br /><br /> <span data-ttu-id="45c85-123">Gibt den Satz von .NET-Typen an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="45c85-123">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="45c85-124">Typname-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="45c85-124">TypeName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="45c85-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="45c85-125">Optional element.</span></span><br /><br /> <span data-ttu-id="45c85-126">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="45c85-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="45c85-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="45c85-127">Parent Elements</span></span>

|<span data-ttu-id="45c85-128">Element</span><span class="sxs-lookup"><span data-stu-id="45c85-128">Element</span></span>|<span data-ttu-id="45c85-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45c85-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45c85-130">Entryselectedby-Element für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="45c85-130">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="45c85-131">Definiert die .NET-Typen, die diesen Tabelleneintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="45c85-131">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="45c85-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="45c85-132">Remarks</span></span>

<span data-ttu-id="45c85-133">lWenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="45c85-133">lWhen you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="45c85-134">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="45c85-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="45c85-135">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="45c85-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="45c85-136">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="45c85-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="45c85-137">Weitere Informationen zu anderen Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="45c85-137">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="45c85-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45c85-138">See Also</span></span>

[<span data-ttu-id="45c85-139">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="45c85-139">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="45c85-140">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="45c85-140">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="45c85-141">ListEntry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="45c85-141">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="45c85-142">Selectionsetname-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="45c85-142">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="45c85-143">Typname-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="45c85-143">TypeName Element for EntrySelectedBy for ListEntry (Format)</span></span>](/powershell/scripting/developer/format/typename-element-for-entryselectedby-for-listcontrol-format)

[<span data-ttu-id="45c85-144">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="45c85-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
